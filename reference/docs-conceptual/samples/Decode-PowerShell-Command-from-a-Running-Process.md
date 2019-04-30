---
ms.date: 11/13/2018
keywords: powershell,командлет
title: Декодирование команды PowerShell из выполняемого процесса
author: randomnote1
ms.openlocfilehash: a0602070a8c5b60ce0bb09e227690f48d970a868
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62086244"
---
# <a name="decode-a-powershell-command-from-a-running-process"></a>Декодирование команды PowerShell из выполняемого процесса

Иногда у вас может быть запущен процесс PowerShell, который потребляет большое количество ресурсов.
Этот процесс может быть запущен в контексте задания [Планировщик заданий][] или задания [Агент SQL Server][]. Если запущено несколько процессов PowerShell, может быть трудно определить, какой процесс представляет проблему. В этой статье показано, как декодировать блок скрипта, который в данный момент выполняется процессом PowerShell.

## <a name="create-a-long-running-process"></a>Создание длительного процесса

Для демонстрации этого сценария откройте новое окно PowerShell и выполните следующий код. Он выполняет команду PowerShell, которая выводит число каждую минуту в течение 10 минут.

```powershell
powershell.exe -Command {
    $i = 1
    while ( $i -le 10 )
    {
        Write-Output -InputObject $i
        Start-Sleep -Seconds 60
        $i++
    }
}
```

## <a name="view-the-process"></a>Представление процесса

Текст команды, которая выполняется в PowerShell, хранится в свойстве **CommandLine** класса [Win32_Process][]. Если команда является [Зашифрованная команда][], свойство **CommandLine** содержит строку EncodedCommand. Используя эту информацию, зашифрованная команда может быть удалена с помощью следующего процесса.

Запустите PowerShell от имени администратора. Крайне важно, чтобы PowerShell запускался от имени администратора, иначе при запросе запущенных процессов результаты не возвращаются.

Выполните следующую команду, чтобы получить все процессы PowerShell, которые содержат зашифрованную команду.

```powershell
$powerShellProcesses = Get-CimInstance -ClassName Win32_Process -Filter 'CommandLine LIKE "%EncodedCommand%"'
```

Следующая команда создает пользовательский объект PowerShell, который содержит идентификатор процесса и зашифрованную команду.

```powershell
$commandDetails = $powerShellProcesses | Select-Object -Property ProcessId,
@{
    name       = 'EncodedCommand'
    expression = {
        if ( $_.CommandLine -match 'encodedCommand (.*) -inputFormat' )
        {
            return $matches[1]
        }
    }
}
```

Теперь зашифрованная команда может быть декодирована. Следующий фрагмент перебирает объект сведений о команде, декодирует зашифрованную команду и добавляет декодированную команду обратно к объекту для дальнейшего изучения.

```powershell
$commandDetails | ForEach-Object -Process {
    # Get the current process
    $currentProcess = $_

    # Convert the Base 64 string to a Byte Array
    $commandBytes = [System.Convert]::FromBase64String($currentProcess.EncodedCommand)

    # Convert the Byte Array to a string
    $decodedCommand = [System.Text.Encoding]::Unicode.GetString($commandBytes)

    # Add the decoded command back to the object
    $commandDetails |
        Where-Object -FilterScript { $_.ProcessId -eq $_.ProcessId } |
        Add-Member -MemberType NoteProperty -Name DecodedCommand -Value $decodedCommand
}
$commandDetails[0]
```

Теперь можно просмотреть декодированную команду, выбрав ее свойство.

```output
ProcessId      : 8752
EncodedCommand : IAAKAAoACgAgAAoAIAAgACAAIAAkAGkAIAA9ACAAMQAgAAoACgAKACAACgAgACAAIAAgAHcAaABpAGwAZQAgACgAIAAkAGkAIAAtAG
                 wAZQAgADEAMAAgACkAIAAKAAoACgAgAAoAIAAgACAAIAB7ACAACgAKAAoAIAAKACAAIAAgACAAIAAgACAAIABXAHIAaQB0AGUALQBP
                 AHUAdABwAHUAdAAgAC0ASQBuAHAAdQB0AE8AYgBqAGUAYwB0ACAAJABpACAACgAKAAoAIAAKACAAIAAgACAAIAAgACAAIABTAHQAYQ
                 ByAHQALQBTAGwAZQBlAHAAIAAtAFMAZQBjAG8AbgBkAHMAIAA2ADAAIAAKAAoACgAgAAoAIAAgACAAIAAgACAAIAAgACQAaQArACsA
                 IAAKAAoACgAgAAoAIAAgACAAIAB9ACAACgAKAAoAIAAKAA==
DecodedCommand :
                     $i = 1

                     while ( $i -le 10 )

                     {

                         Write-Output -InputObject $i

                         Start-Sleep -Seconds 60

                         $i++

                     }
```

[Планировщик заданий]: /windows/desktop/TaskSchd/task-scheduler-start-page
[Агент SQL Server]: /sql/ssms/agent/sql-server-agent
[Win32_Process]: /windows/desktop/CIMWin32Prov/win32-process
[Зашифрованная команда]: /powershell/scripting/core-powershell/console/powershell.exe-command-line-help#-encodedcommand-
