---
ms.date: 11/13/2018
keywords: powershell,командлет
title: Декодирование команды PowerShell из выполняемого процесса
author: randomnote1
ms.openlocfilehash: a0602070a8c5b60ce0bb09e227690f48d970a868
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "55680764"
---
# <a name="decode-a-powershell-command-from-a-running-process"></a><span data-ttu-id="f92ea-103">Декодирование команды PowerShell из выполняемого процесса</span><span class="sxs-lookup"><span data-stu-id="f92ea-103">Decode a PowerShell command from a running process</span></span>

<span data-ttu-id="f92ea-104">В некоторых случаях возможно, PowerShell, процесс, запущенный, занимает большой процент ресурсов.</span><span class="sxs-lookup"><span data-stu-id="f92ea-104">At times, you may have a PowerShell process running that is taking up a large amount of resources.</span></span>
<span data-ttu-id="f92ea-105">Этот процесс может быть запущен в контексте [Планировщик заданий][] задания или [Агент SQL Server][] задания.</span><span class="sxs-lookup"><span data-stu-id="f92ea-105">This process could be running in the context of a [Task Scheduler][] job or a [SQL Server Agent][] job.</span></span> <span data-ttu-id="f92ea-106">Если выполнять несколько процессов PowerShell, может быть сложно предсказать, какой процесс представляет проблему.</span><span class="sxs-lookup"><span data-stu-id="f92ea-106">Where there are multiple PowerShell processes running, it can be difficult to know which process represents the problem.</span></span> <span data-ttu-id="f92ea-107">В этой статье показано, как декодировать блок скрипта, который в данный момент выполняется процесс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f92ea-107">This article shows how to decode a script block that a PowerShell process is currently running.</span></span>

## <a name="create-a-long-running-process"></a><span data-ttu-id="f92ea-108">Создание длительный процесс</span><span class="sxs-lookup"><span data-stu-id="f92ea-108">Create a long running process</span></span>

<span data-ttu-id="f92ea-109">Для демонстрации этого сценария, откройте новое окно PowerShell и выполните следующий код.</span><span class="sxs-lookup"><span data-stu-id="f92ea-109">To demonstrate this scenario, open a new PowerShell window and run the following code.</span></span> <span data-ttu-id="f92ea-110">Он выполняет команду PowerShell, которая выводит число каждую минуту в течение 10 минут.</span><span class="sxs-lookup"><span data-stu-id="f92ea-110">It executes a PowerShell command that outputs a number every minute for 10 minutes.</span></span>

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

## <a name="view-the-process"></a><span data-ttu-id="f92ea-111">Просмотр процесса</span><span class="sxs-lookup"><span data-stu-id="f92ea-111">View the process</span></span>

<span data-ttu-id="f92ea-112">Текст команды, которая выполняется PowerShell хранится в **CommandLine** свойство [Win32_Process][] класса.</span><span class="sxs-lookup"><span data-stu-id="f92ea-112">The body of the command which PowerShell is executing is stored in the **CommandLine** property of the [Win32_Process][] class.</span></span> <span data-ttu-id="f92ea-113">Если команда является [Команда кодировке][], **CommandLine** свойство содержит строку «EncodedCommand».</span><span class="sxs-lookup"><span data-stu-id="f92ea-113">If the command is an [encoded command][], the **CommandLine** property contains the string "EncodedCommand".</span></span> <span data-ttu-id="f92ea-114">Используя эту информацию, закодированное команда может быть раскрываемое с помощью следующей процедуры.</span><span class="sxs-lookup"><span data-stu-id="f92ea-114">Using this information, the encoded command can be de-obfuscated via the following process.</span></span>

<span data-ttu-id="f92ea-115">Запустите PowerShell от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="f92ea-115">Start PowerShell as Administrator.</span></span> <span data-ttu-id="f92ea-116">Крайне важно, что PowerShell выполняется от имени администратора, в противном случае результаты не возвращаются при запросе запущенных процессов.</span><span class="sxs-lookup"><span data-stu-id="f92ea-116">It is vital that PowerShell is running as administrator, otherwise no results are returned when querying the running processes.</span></span>

<span data-ttu-id="f92ea-117">Выполните следующую команду, чтобы получить все процессы PowerShell, которые содержит закодированный команды:</span><span class="sxs-lookup"><span data-stu-id="f92ea-117">Execute the following command to get all of the PowerShell processes that have an encoded command:</span></span>

```powershell
$powerShellProcesses = Get-CimInstance -ClassName Win32_Process -Filter 'CommandLine LIKE "%EncodedCommand%"'
```

<span data-ttu-id="f92ea-118">Следующая команда создает пользовательский объект PowerShell, содержит идентификатор процесса и команда кодировке.</span><span class="sxs-lookup"><span data-stu-id="f92ea-118">The following command creates a custom PowerShell object that contains the process ID and the encoded command.</span></span>

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

<span data-ttu-id="f92ea-119">Теперь закодированный команда может быть декодирован.</span><span class="sxs-lookup"><span data-stu-id="f92ea-119">Now the encoded command can be decoded.</span></span> <span data-ttu-id="f92ea-120">Следующий фрагмент кода выполняет итерацию по объект сведений команда, раскодирует закодированный команды и добавляет декодированные команды к объекту для получения более подробных сведений.</span><span class="sxs-lookup"><span data-stu-id="f92ea-120">The following snippet iterates over the command details object, decodes the encoded command, and adds the decoded command back to the object for further investigation.</span></span>

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

<span data-ttu-id="f92ea-121">Теперь декодированные команды можно просмотреть, выбрав свойство декодированный command.</span><span class="sxs-lookup"><span data-stu-id="f92ea-121">The decoded command can now be reviewed by selecting the decoded command property.</span></span>

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
[Команда кодировке]: /powershell/scripting/core-powershell/console/powershell.exe-command-line-help#-encodedcommand-
[encoded command]: /powershell/scripting/core-powershell/console/powershell.exe-command-line-help#-encodedcommand-
