---
ms.date: 11/13/2018
keywords: powershell,командлет
title: Декодирование команды PowerShell из выполняемого процесса
author: randomnote1
ms.openlocfilehash: a6c01d8edf67aba6c47350a97cc0ceec4801ad29
ms.sourcegitcommit: bc42c9166857147a1ecf9924b718d4a48eb901e3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/03/2019
ms.locfileid: "66470968"
---
# <a name="decode-a-powershell-command-from-a-running-process"></a><span data-ttu-id="672dc-103">Декодирование команды PowerShell из выполняемого процесса</span><span class="sxs-lookup"><span data-stu-id="672dc-103">Decode a PowerShell command from a running process</span></span>

<span data-ttu-id="672dc-104">Иногда у вас может быть запущен процесс PowerShell, который потребляет большое количество ресурсов.</span><span class="sxs-lookup"><span data-stu-id="672dc-104">At times, you may have a PowerShell process running that is taking up a large amount of resources.</span></span>
<span data-ttu-id="672dc-105">Этот процесс может быть запущен в контексте задания [Планировщик заданий][] или задания [Агент SQL Server][].</span><span class="sxs-lookup"><span data-stu-id="672dc-105">This process could be running in the context of a [Task Scheduler][] job or a [SQL Server Agent][] job.</span></span> <span data-ttu-id="672dc-106">Если запущено несколько процессов PowerShell, может быть трудно определить, какой процесс представляет проблему.</span><span class="sxs-lookup"><span data-stu-id="672dc-106">Where there are multiple PowerShell processes running, it can be difficult to know which process represents the problem.</span></span> <span data-ttu-id="672dc-107">В этой статье показано, как декодировать блок скрипта, который в данный момент выполняется процессом PowerShell.</span><span class="sxs-lookup"><span data-stu-id="672dc-107">This article shows how to decode a script block that a PowerShell process is currently running.</span></span>

## <a name="create-a-long-running-process"></a><span data-ttu-id="672dc-108">Создание длительного процесса</span><span class="sxs-lookup"><span data-stu-id="672dc-108">Create a long running process</span></span>

<span data-ttu-id="672dc-109">Для демонстрации этого сценария откройте новое окно PowerShell и выполните следующий код.</span><span class="sxs-lookup"><span data-stu-id="672dc-109">To demonstrate this scenario, open a new PowerShell window and run the following code.</span></span> <span data-ttu-id="672dc-110">Он выполняет команду PowerShell, которая выводит число каждую минуту в течение 10 минут.</span><span class="sxs-lookup"><span data-stu-id="672dc-110">It executes a PowerShell command that outputs a number every minute for 10 minutes.</span></span>

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

## <a name="view-the-process"></a><span data-ttu-id="672dc-111">Представление процесса</span><span class="sxs-lookup"><span data-stu-id="672dc-111">View the process</span></span>

<span data-ttu-id="672dc-112">Текст команды, которая выполняется в PowerShell, хранится в свойстве **CommandLine** класса [Win32_Process][].</span><span class="sxs-lookup"><span data-stu-id="672dc-112">The body of the command which PowerShell is executing is stored in the **CommandLine** property of the [Win32_Process][] class.</span></span> <span data-ttu-id="672dc-113">Если команда является зашифрованной, свойство **CommandLine** содержит строку EncodedCommand.</span><span class="sxs-lookup"><span data-stu-id="672dc-113">If the command is an encoded command, the **CommandLine** property contains the string "EncodedCommand".</span></span> <span data-ttu-id="672dc-114">Используя эту информацию, зашифрованная команда может быть удалена с помощью следующего процесса.</span><span class="sxs-lookup"><span data-stu-id="672dc-114">Using this information, the encoded command can be de-obfuscated via the following process.</span></span>

<span data-ttu-id="672dc-115">Запустите PowerShell от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="672dc-115">Start PowerShell as Administrator.</span></span> <span data-ttu-id="672dc-116">Крайне важно, чтобы PowerShell запускался от имени администратора, иначе при запросе запущенных процессов результаты не возвращаются.</span><span class="sxs-lookup"><span data-stu-id="672dc-116">It is vital that PowerShell is running as administrator, otherwise no results are returned when querying the running processes.</span></span>

<span data-ttu-id="672dc-117">Выполните следующую команду, чтобы получить все процессы PowerShell, которые содержат зашифрованную команду.</span><span class="sxs-lookup"><span data-stu-id="672dc-117">Execute the following command to get all of the PowerShell processes that have an encoded command:</span></span>

```powershell
$powerShellProcesses = Get-CimInstance -ClassName Win32_Process -Filter 'CommandLine LIKE "%EncodedCommand%"'
```

<span data-ttu-id="672dc-118">Следующая команда создает пользовательский объект PowerShell, который содержит идентификатор процесса и зашифрованную команду.</span><span class="sxs-lookup"><span data-stu-id="672dc-118">The following command creates a custom PowerShell object that contains the process ID and the encoded command.</span></span>

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

<span data-ttu-id="672dc-119">Теперь зашифрованная команда может быть декодирована.</span><span class="sxs-lookup"><span data-stu-id="672dc-119">Now the encoded command can be decoded.</span></span> <span data-ttu-id="672dc-120">Следующий фрагмент перебирает объект сведений о команде, декодирует зашифрованную команду и добавляет декодированную команду обратно к объекту для дальнейшего изучения.</span><span class="sxs-lookup"><span data-stu-id="672dc-120">The following snippet iterates over the command details object, decodes the encoded command, and adds the decoded command back to the object for further investigation.</span></span>

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

<span data-ttu-id="672dc-121">Теперь можно просмотреть декодированную команду, выбрав ее свойство.</span><span class="sxs-lookup"><span data-stu-id="672dc-121">The decoded command can now be reviewed by selecting the decoded command property.</span></span>

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
[Task Scheduler]: /windows/desktop/TaskSchd/task-scheduler-start-page
[Агент SQL Server]: /sql/ssms/agent/sql-server-agent
[SQL Server Agent]: /sql/ssms/agent/sql-server-agent
[Win32_Process]: /windows/desktop/CIMWin32Prov/win32-process
