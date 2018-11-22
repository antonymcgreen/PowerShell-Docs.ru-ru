---
ms.date: 11/13/2018
keywords: powershell,командлет
title: Декодирование команды PowerShell из выполняемого процесса
author: randomnote1
ms.openlocfilehash: a0602070a8c5b60ce0bb09e227690f48d970a868
ms.sourcegitcommit: 91786b03704fbd2d185f674df0bc67faddfb6288
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2018
ms.locfileid: "51619218"
---
# <a name="decode-a-powershell-command-from-a-running-process"></a>Декодирование команды PowerShell из выполняемого процесса

В некоторых случаях возможно, PowerShell, процесс, запущенный, занимает большой процент ресурсов.
Этот процесс может быть запущен в контексте [Планировщик заданий][] задания или [Агент SQL Server][] задания. Если выполнять несколько процессов PowerShell, может быть сложно предсказать, какой процесс представляет проблему. В этой статье показано, как декодировать блок скрипта, который в данный момент выполняется процесс PowerShell.

## <a name="create-a-long-running-process"></a>Создание длительный процесс

Для демонстрации этого сценария, откройте новое окно PowerShell и выполните следующий код. Он выполняет команду PowerShell, которая выводит число каждую минуту в течение 10 минут.

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

## <a name="view-the-process"></a>Просмотр процесса

Текст команды, которая выполняется PowerShell хранится в **CommandLine** свойство [Win32_Process][] класса. Если команда является [Команда кодировке][], **CommandLine** свойство содержит строку «EncodedCommand». Используя эту информацию, закодированное команда может быть раскрываемое с помощью следующей процедуры.

Запустите PowerShell от имени администратора. Крайне важно, что PowerShell выполняется от имени администратора, в противном случае результаты не возвращаются при запросе запущенных процессов.

Выполните следующую команду, чтобы получить все процессы PowerShell, которые содержит закодированный команды:

```powershell
$powerShellProcesses = Get-CimInstance -ClassName Win32_Process -Filter 'CommandLine LIKE "%EncodedCommand%"'
```

Следующая команда создает пользовательский объект PowerShell, содержит идентификатор процесса и команда кодировке.

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

Теперь закодированный команда может быть декодирован. Следующий фрагмент кода выполняет итерацию по объект сведений команда, раскодирует закодированный команды и добавляет декодированные команды к объекту для получения более подробных сведений.

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

Теперь декодированные команды можно просмотреть, выбрав свойство декодированный command.

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
[Команда кодировке]: /powershell/scripting/core-powershell/console/powershell.exe-command-line-help#-encodedcommand-
