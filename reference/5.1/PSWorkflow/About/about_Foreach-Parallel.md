---
description: Описание `ForEach -Parallel` языковой конструкции в рабочем процессе Windows PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 07/10/2019
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_foreach-parallel?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Foreach параллельно
ms.openlocfilehash: 1012b45396b65d424dacac067c2af8d3b6823f92
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231618"
---
# <a name="about-foreach-parallel"></a><span data-ttu-id="c490a-104">О Foreach-Parallel</span><span class="sxs-lookup"><span data-stu-id="c490a-104">About Foreach-Parallel</span></span>

## <a name="short-description"></a><span data-ttu-id="c490a-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="c490a-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="c490a-106">Описание `ForEach -Parallel` языковой конструкции в рабочем процессе Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c490a-106">Describes the `ForEach -Parallel` language construct in Windows PowerShell Workflow.</span></span>

## <a name="long-description"></a><span data-ttu-id="c490a-107">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="c490a-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="c490a-108">Параметр **Parallel** `ForEach` ключевого слова выполняет команды в `ForEach` блоке скрипта один раз для каждого элемента в указанной коллекции.</span><span class="sxs-lookup"><span data-stu-id="c490a-108">The **Parallel** parameter of the `ForEach` keyword runs the commands in a `ForEach` script block once for each item in a specified collection.</span></span>

<span data-ttu-id="c490a-109">Элементы в коллекции, такие как диск в коллекции дисков, обрабатываются параллельно.</span><span class="sxs-lookup"><span data-stu-id="c490a-109">The items in the collection, such as a disk in a collection of disks, are processed in parallel.</span></span> <span data-ttu-id="c490a-110">Команды в блоке скрипта выполняются последовательно для каждого элемента в коллекции.</span><span class="sxs-lookup"><span data-stu-id="c490a-110">The commands in the script block run sequentially on each item in the collection.</span></span>

<span data-ttu-id="c490a-111">`ForEach -Parallel` допустимо только в рабочем процессе Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c490a-111">`ForEach -Parallel` is valid only in a Windows PowerShell Workflow.</span></span>

### <a name="syntax"></a><span data-ttu-id="c490a-112">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c490a-112">SYNTAX</span></span>

```
ForEach -Parallel ($<item> in $<collection>)
{
    [<Activity1>]
    [<Activity2>]
    ...
}
```

### <a name="detailed-description"></a><span data-ttu-id="c490a-113">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="c490a-113">DETAILED DESCRIPTION</span></span>

<span data-ttu-id="c490a-114">Как и в случае с инструкцией ForEach в Windows PowerShell, переменная, содержащая коллекцию, `$<collection>` должна быть определена перед `ForEach -Parallel` инструкцией, но переменная, представляющая текущий элемент, `$<item>` определяется в `ForEach -Parallel` инструкции.</span><span class="sxs-lookup"><span data-stu-id="c490a-114">Like the ForEach statement in Windows PowerShell, the variable that contains collection `$<collection>` must be defined before the `ForEach -Parallel` statement, but the variable that represents the current item `$<item>` is defined in the `ForEach -Parallel` statement.</span></span>

<span data-ttu-id="c490a-115">`ForEach -Parallel`Конструкция отличается от `ForEach` ключевого слова и **параллельного** параметра.</span><span class="sxs-lookup"><span data-stu-id="c490a-115">The `ForEach -Parallel` construct is different from the `ForEach` keyword and the **Parallel** parameter.</span></span> <span data-ttu-id="c490a-116">`ForEach`Ключевое слово обрабатывает элементы в коллекции последовательно.</span><span class="sxs-lookup"><span data-stu-id="c490a-116">The `ForEach` keyword processes the items in the collection in sequence.</span></span> <span data-ttu-id="c490a-117">**Параллельный** параметр выполняет команды в блоке скрипта параллельно.</span><span class="sxs-lookup"><span data-stu-id="c490a-117">The **Parallel** parameter runs commands in a script block in parallel.</span></span> <span data-ttu-id="c490a-118">Блок параллельного скрипта можно заключить в `ForEach -Parallel` блок скрипта.</span><span class="sxs-lookup"><span data-stu-id="c490a-118">You can enclose a Parallel script block in a `ForEach -Parallel` script block.</span></span>

<span data-ttu-id="c490a-119">Целевые компьютеры в рабочем процессе, такие как указанные в общем параметре рабочего процесса **PSComputerName** , всегда обрабатываются параллельно.</span><span class="sxs-lookup"><span data-stu-id="c490a-119">The target computers in a workflow, such as those specified by the **PSComputerName** workflow common parameter, are always processed in parallel.</span></span>
<span data-ttu-id="c490a-120">`ForEach -Parallel`Для этой цели не нужно указывать ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="c490a-120">You do not need to specify the `ForEach -Parallel` keyword for this purpose.</span></span>

### <a name="examples"></a><span data-ttu-id="c490a-121">Примеры</span><span class="sxs-lookup"><span data-stu-id="c490a-121">EXAMPLES</span></span>

<span data-ttu-id="c490a-122">Следующий рабочий процесс содержит `ForEach -Parallel` инструкцию, которая обрабатывает диски, которые `Get-Disk` получает действие.</span><span class="sxs-lookup"><span data-stu-id="c490a-122">The following workflow contains a `ForEach -Parallel` statement that processes the disks that the `Get-Disk` activity gets.</span></span> <span data-ttu-id="c490a-123">Команды в `ForEach -Parallel` блоке скрипта выполняются последовательно, но выполняются на дисках параллельно.</span><span class="sxs-lookup"><span data-stu-id="c490a-123">The commands in the `ForEach -Parallel` script block run sequentially, but they run on the disks in parallel.</span></span> <span data-ttu-id="c490a-124">Диски могут обрабатываться параллельно и в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="c490a-124">The disks might be processed concurrently and in any order.</span></span>

```powershell
workflow Test-Workflow
{
    $Disks = Get-Disk

    # The disks are processed in parallel.
    ForEach -Parallel ($Disk in $Disks)
    {
        # The commands run sequentially on each disk.
        $DiskPath = $Disk.Path
        $Disk | Initialize-Disk
        Set-Disk -Path $DiskPath
    }
}

workflow Test-Workflow
{
    #Run commands in parallel.
    Parallel
    {
        Get-Process
        Get-Service
    }

   $Disks = Get-Disk

   # The disks are processed in parallel.
   ForEach -Parallel ($Disk in $Disks)
   {
       # The commands run in parallel on each disk.
       Parallel
       {
           Initialize-Disk
           InlineScript {.\Get-DiskInventory}
       }
   }
}
```

## <a name="see-also"></a><span data-ttu-id="c490a-125">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="c490a-125">SEE ALSO</span></span>

[<span data-ttu-id="c490a-126">Writing a Script Workflow</span><span class="sxs-lookup"><span data-stu-id="c490a-126">Writing a Script Workflow</span></span>](/previous-versions/powershell/scripting/developer/workflow/creating-a-workflow-by-using-a-windows-powershell-script)

[<span data-ttu-id="c490a-127">about_ForEach</span><span class="sxs-lookup"><span data-stu-id="c490a-127">about_ForEach</span></span>](../../Microsoft.PowerShell.Core/About/about_ForEach.md)

[<span data-ttu-id="c490a-128">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="c490a-128">about_Language_Keywords</span></span>](../../Microsoft.PowerShell.Core/About/about_Language_Keywords.md)

[<span data-ttu-id="c490a-129">about_Parallel</span><span class="sxs-lookup"><span data-stu-id="c490a-129">about_Parallel</span></span>](about_Parallel.md)

[<span data-ttu-id="c490a-130">about_Workflows</span><span class="sxs-lookup"><span data-stu-id="c490a-130">about_Workflows</span></span>](about_Workflows.md)
