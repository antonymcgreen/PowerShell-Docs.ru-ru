---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
title: Трассировка сценариев и ведения журналов для них
ms.openlocfilehash: 6b7e5022cb4c974da5ddb3d670b5808dc9fb7bdc
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "71147804"
---
# <a name="script-tracing-and-logging"></a><span data-ttu-id="c4b83-103">Трассировка сценариев и ведения журналов для них</span><span class="sxs-lookup"><span data-stu-id="c4b83-103">Script Tracing and Logging</span></span>

<span data-ttu-id="c4b83-104">Хотя PowerShell уже имеет параметр групповой политики **LogPipelineExecutionDetails** для регистрации вызовов командлетов, язык сценариев PowerShell имеет несколько функций, для которых может потребоваться ведение журнала или аудит.</span><span class="sxs-lookup"><span data-stu-id="c4b83-104">While PowerShell already has the **LogPipelineExecutionDetails** Group Policy setting to log the invocation of cmdlets, PowerShell's scripting language has several features that you might want to log and audit.</span></span> <span data-ttu-id="c4b83-105">Новая функция подробной трассировки сценариев обеспечивает подробное отслеживание и анализ для используемых в системе сценариев PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c4b83-105">The new Detailed Script Tracing feature provides detailed tracking and analysis of PowerShell script activity on a system.</span></span> <span data-ttu-id="c4b83-106">После включения этой функции PowerShell регистрирует все блоки сценариев в журнале трассировки событий Windows — **Microsoft-Windows-PowerShell/Operational**.</span><span class="sxs-lookup"><span data-stu-id="c4b83-106">After enabling detailed script tracing, PowerShell logs all script blocks to the ETW event log, **Microsoft-Windows-PowerShell/Operational**.</span></span> <span data-ttu-id="c4b83-107">Если блок сценария создает другой блок сценария, например путем вызова `Invoke-Expression`, вызванный блок сценария также регистрируется.</span><span class="sxs-lookup"><span data-stu-id="c4b83-107">If a script block creates another script block, for example, by calling `Invoke-Expression`, the invoked script block also logged.</span></span>

<span data-ttu-id="c4b83-108">Ведение журнала можно включить с помощью параметра групповой политики **Включить регистрацию блоков сценариев PowerShell** (**Административные шаблоны** -> **Компоненты Windows** -> **Windows PowerShell**).</span><span class="sxs-lookup"><span data-stu-id="c4b83-108">Logging is enabled through the **Turn on PowerShell Script Block Logging** Group Policy setting in **Administrative Templates** -> **Windows Components** -> **Windows PowerShell**.</span></span>

<span data-ttu-id="c4b83-109">Доступны следующие события.</span><span class="sxs-lookup"><span data-stu-id="c4b83-109">The events are:</span></span>

| <span data-ttu-id="c4b83-110">Канал</span><span class="sxs-lookup"><span data-stu-id="c4b83-110">Channel</span></span> |                               <span data-ttu-id="c4b83-111">Operational</span><span class="sxs-lookup"><span data-stu-id="c4b83-111">Operational</span></span>                               |
| ------- | ----------------------------------------------------------------------- |
| <span data-ttu-id="c4b83-112">Уровень</span><span class="sxs-lookup"><span data-stu-id="c4b83-112">Level</span></span>   | <span data-ttu-id="c4b83-113">Verbose</span><span class="sxs-lookup"><span data-stu-id="c4b83-113">Verbose</span></span>                                                                 |
| <span data-ttu-id="c4b83-114">Код операции</span><span class="sxs-lookup"><span data-stu-id="c4b83-114">Opcode</span></span>  | <span data-ttu-id="c4b83-115">Создать</span><span class="sxs-lookup"><span data-stu-id="c4b83-115">Create</span></span>                                                                  |
| <span data-ttu-id="c4b83-116">Задача</span><span class="sxs-lookup"><span data-stu-id="c4b83-116">Task</span></span>    | <span data-ttu-id="c4b83-117">CommandStart</span><span class="sxs-lookup"><span data-stu-id="c4b83-117">CommandStart</span></span>                                                            |
| <span data-ttu-id="c4b83-118">Ключевое слово</span><span class="sxs-lookup"><span data-stu-id="c4b83-118">Keyword</span></span> | <span data-ttu-id="c4b83-119">Пространство выполнения</span><span class="sxs-lookup"><span data-stu-id="c4b83-119">Runspace</span></span>                                                                |
| <span data-ttu-id="c4b83-120">Код события</span><span class="sxs-lookup"><span data-stu-id="c4b83-120">EventId</span></span> | <span data-ttu-id="c4b83-121">Engine_ScriptBlockCompiled (0x1008 = 4104)</span><span class="sxs-lookup"><span data-stu-id="c4b83-121">Engine_ScriptBlockCompiled (0x1008 = 4104)</span></span>                              |
| <span data-ttu-id="c4b83-122">Сообщение</span><span class="sxs-lookup"><span data-stu-id="c4b83-122">Message</span></span> | <span data-ttu-id="c4b83-123">Создание текста Scriptblock (%1 из %2):</span><span class="sxs-lookup"><span data-stu-id="c4b83-123">Creating Scriptblock text (%1 of %2):</span></span> </br> <span data-ttu-id="c4b83-124">%3</span><span class="sxs-lookup"><span data-stu-id="c4b83-124">%3</span></span> </br> <span data-ttu-id="c4b83-125">ИД ScriptBlock: %4</span><span class="sxs-lookup"><span data-stu-id="c4b83-125">ScriptBlock ID: %4</span></span> |


<span data-ttu-id="c4b83-126">Текст, внедренный в сообщение, является экстентом скомпилированного блока скрипта.</span><span class="sxs-lookup"><span data-stu-id="c4b83-126">The text embedded in the message is the extent of the script block compiled.</span></span> <span data-ttu-id="c4b83-127">Идентификатор — это GUID, который хранится в течение жизненного цикла блока скрипта.</span><span class="sxs-lookup"><span data-stu-id="c4b83-127">The ID is a GUID that is retained for the life of the script block.</span></span>

<span data-ttu-id="c4b83-128">При включении подробного ведения журналов функция записывает начальный и конечный маркеры:</span><span class="sxs-lookup"><span data-stu-id="c4b83-128">When you enable verbose logging, the feature writes begin and end markers:</span></span>

| <span data-ttu-id="c4b83-129">Канал</span><span class="sxs-lookup"><span data-stu-id="c4b83-129">Channel</span></span> |                                 <span data-ttu-id="c4b83-130">Operational</span><span class="sxs-lookup"><span data-stu-id="c4b83-130">Operational</span></span>                                |
| ------- | -------------------------------------------------------------------------- |
| <span data-ttu-id="c4b83-131">Уровень</span><span class="sxs-lookup"><span data-stu-id="c4b83-131">Level</span></span>   | <span data-ttu-id="c4b83-132">Verbose</span><span class="sxs-lookup"><span data-stu-id="c4b83-132">Verbose</span></span>                                                                    |
| <span data-ttu-id="c4b83-133">Код операции</span><span class="sxs-lookup"><span data-stu-id="c4b83-133">Opcode</span></span>  | <span data-ttu-id="c4b83-134">Открыть / Закрыть</span><span class="sxs-lookup"><span data-stu-id="c4b83-134">Open / Close</span></span>                                                               |
| <span data-ttu-id="c4b83-135">Задача</span><span class="sxs-lookup"><span data-stu-id="c4b83-135">Task</span></span>    | <span data-ttu-id="c4b83-136">CommandStart / CommandStop</span><span class="sxs-lookup"><span data-stu-id="c4b83-136">CommandStart / CommandStop</span></span>                                                 |
| <span data-ttu-id="c4b83-137">Ключевое слово</span><span class="sxs-lookup"><span data-stu-id="c4b83-137">Keyword</span></span> | <span data-ttu-id="c4b83-138">Пространство выполнения</span><span class="sxs-lookup"><span data-stu-id="c4b83-138">Runspace</span></span>                                                                   |
| <span data-ttu-id="c4b83-139">Код события</span><span class="sxs-lookup"><span data-stu-id="c4b83-139">EventId</span></span> | <span data-ttu-id="c4b83-140">ScriptBlock\_Invoke\_Start\_Detail (0x1009 = 4105) /</span><span class="sxs-lookup"><span data-stu-id="c4b83-140">ScriptBlock\_Invoke\_Start\_Detail (0x1009 = 4105) /</span></span> </br> <span data-ttu-id="c4b83-141">ScriptBlock\_Invoke\_Complete\_Detail (0x100A = 4106)</span><span class="sxs-lookup"><span data-stu-id="c4b83-141">ScriptBlock\_Invoke\_Complete\_Detail (0x100A = 4106)</span></span> |
| <span data-ttu-id="c4b83-142">Сообщение</span><span class="sxs-lookup"><span data-stu-id="c4b83-142">Message</span></span> | <span data-ttu-id="c4b83-143">Запущен/Завершен вызов ИД ScriptBlock: %1</span><span class="sxs-lookup"><span data-stu-id="c4b83-143">Started / Completed invocation of ScriptBlock ID: %1</span></span> </br> <span data-ttu-id="c4b83-144">ИД пространства выполнения: %2</span><span class="sxs-lookup"><span data-stu-id="c4b83-144">Runspace ID: %2</span></span> |

<span data-ttu-id="c4b83-145">Идентификатор — это GUID, представляющий блок сценария (который может быть связан с идентификатором событиями 0x1008), а идентификатор пространства выполнения представляет пространство, в котором был запущен этот блок скрипта.</span><span class="sxs-lookup"><span data-stu-id="c4b83-145">The ID is the GUID representing the script block (that can be correlated with event ID 0x1008), and the Runspace ID represents the runspace in which this script block was run.</span></span>

<span data-ttu-id="c4b83-146">Знаки процента в сообщении вызова представляют структурированные свойства трассировки событий Windows.</span><span class="sxs-lookup"><span data-stu-id="c4b83-146">Percent signs in the invocation message represent structured ETW properties.</span></span> <span data-ttu-id="c4b83-147">Хотя они заменяются фактическими значениями в тексте сообщения, более надежным способом доступа к ним является получение сообщения с помощью командлета Get-WinEvent с последующим использованием массива **Properties** сообщения.</span><span class="sxs-lookup"><span data-stu-id="c4b83-147">While they are replaced with the actual values in the message text, a more robust way to access them is to retrieve the message with the Get-WinEvent cmdlet, and then use the **Properties** array of the message.</span></span>

<span data-ttu-id="c4b83-148">Ниже приведен пример того, как эта функциональность помогает раскрыть злонамеренную попытку шифрования и маскировки сценария:</span><span class="sxs-lookup"><span data-stu-id="c4b83-148">Here's an example of how this functionality can help unwrap a malicious attempt to encrypt and obfuscate a script:</span></span>

```powershell
## Malware
function SuperDecrypt
{
    param($script)
    $bytes = [Convert]::FromBase64String($script)

    ## XOR "encryption"
    $xorKey = 0x42
    for($counter = 0; $counter -lt $bytes.Length; $counter++)
    {
        $bytes[$counter] = $bytes[$counter] -bxor $xorKey
    }
    [System.Text.Encoding]::Unicode.GetString($bytes)
}

$decrypted = SuperDecrypt "FUIwQitCNkInQm9CCkItQjFCNkJiQmVCEkI1QixCJkJlQg=="
Invoke-Expression $decrypted
```

<span data-ttu-id="c4b83-149">При выполнении этого кода создаются следующие записи журнала:</span><span class="sxs-lookup"><span data-stu-id="c4b83-149">Running this generates the following log entries:</span></span>

```Output
Compiling Scriptblock text (1 of 1):
function SuperDecrypt
{
    param($script)
    $bytes = [Convert]::FromBase64String($script)
    ## XOR "encryption"
    $xorKey = 0x42
    for($counter = 0; $counter -lt $bytes.Length; $counter++)
    {
        $bytes[$counter] = $bytes[$counter] -bxor $xorKey
    }
    [System.Text.Encoding]::Unicode.GetString($bytes)

}
ScriptBlock ID: ad8ae740-1f33-42aa-8dfc-1314411877e3

Compiling Scriptblock text (1 of 1):
$decrypted = SuperDecrypt "FUIwQitCNkInQm9CCkItQjFCNkJiQmVCEkI1QixCJkJlQg=="
ScriptBlock ID: ba11c155-d34c-4004-88e3-6502ecb50f52

Compiling Scriptblock text (1 of 1):
Invoke-Expression $decrypted
ScriptBlock ID: 856c01ca-85d7-4989-b47f-e6a09ee4eeb3

Compiling Scriptblock text (1 of 1):
Write-Host 'Pwnd'
ScriptBlock ID: 5e618414-4e77-48e3-8f65-9a863f54b4c8
```

Если длина блока сценария превышает емкость одного события, PowerShell разбивает сценарий на несколько частей. <span data-ttu-id="c4b83-151">Ниже приведен пример кода для воссоединения сценария из сообщений журнала:</span><span class="sxs-lookup"><span data-stu-id="c4b83-151">Here is sample code to recombine a script from its log messages:</span></span>

```powershell
$created = Get-WinEvent -FilterHashtable @{ ProviderName="Microsoft-Windows-PowerShell"; Id = 4104 } |
  Where-Object { $_.<...> }
$sortedScripts = $created | sort { $_.Properties[0].Value }
$mergedScript = -join ($sortedScripts | % { $_.Properties[2].Value })
```

<span data-ttu-id="c4b83-152">Как и в случае со всеми системами ведения журнала с ограниченным буфером хранения, единственный способ атаковать эту инфраструктуру заключается в переполнении журнала ложными событиями для сокрытия полученных ранее свидетельств.</span><span class="sxs-lookup"><span data-stu-id="c4b83-152">As with all logging systems that have a limited retention buffer, one way to attack this infrastructure is to flood the log with spurious events to hide earlier evidence.</span></span> <span data-ttu-id="c4b83-153">Для защиты от такой атаки убедитесь, что настроена определенная форма сбора данных из журналов событий (например, пересылка событий Windows).</span><span class="sxs-lookup"><span data-stu-id="c4b83-153">To protect yourself from this attack, ensure that you have some form of event log collection set up Windows Event Forwarding.</span></span> <span data-ttu-id="c4b83-154">Дополнительные сведения см. в статье о [выявлении злоумышленника с помощью мониторинга журналов событий Windows](https://apps.nsa.gov/iaarchive/library/reports/spotting-the-adversary-with-windows-event-log-monitoring.cfm).</span><span class="sxs-lookup"><span data-stu-id="c4b83-154">For more information, see [Spotting the Adversary with Windows Event Log Monitoring](https://apps.nsa.gov/iaarchive/library/reports/spotting-the-adversary-with-windows-event-log-monitoring.cfm).</span></span>