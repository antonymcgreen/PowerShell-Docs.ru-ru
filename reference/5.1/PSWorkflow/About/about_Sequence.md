---
description: Описывает `Sequence` ключевое слово, которое последовательно запускает выбранные действия.
keywords: powershell,командлет
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_sequence?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Sequence
ms.openlocfilehash: a9dd4fb24274fe4e1478ca69c734b43a2f196792
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231606"
---
# <a name="about-sequence"></a><span data-ttu-id="d817f-104">О последовательности</span><span class="sxs-lookup"><span data-stu-id="d817f-104">About Sequence</span></span>

## <a name="short-description"></a><span data-ttu-id="d817f-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="d817f-105">Short description</span></span>

<span data-ttu-id="d817f-106">Описывает `Sequence` ключевое слово, которое последовательно запускает выбранные действия.</span><span class="sxs-lookup"><span data-stu-id="d817f-106">Describes the `Sequence` keyword that runs selected activities sequentially.</span></span>

## <a name="long-description"></a><span data-ttu-id="d817f-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="d817f-107">Long description</span></span>

<span data-ttu-id="d817f-108">`Sequence`Ключевое слово выполняет выбранные действия рабочего процесса последовательно.</span><span class="sxs-lookup"><span data-stu-id="d817f-108">The `Sequence` keyword runs selected workflow activities sequentially.</span></span> <span data-ttu-id="d817f-109">Действия рабочего процесса выполняются в том порядке, в котором они отображаются, и не выполняются одновременно.</span><span class="sxs-lookup"><span data-stu-id="d817f-109">Workflow activities run in the order that they appear and do not run concurrently.</span></span> <span data-ttu-id="d817f-110">`Sequence`Ключевое слово допустимо только в рабочем процессе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d817f-110">The `Sequence` keyword is only valid in a PowerShell Workflow.</span></span>

<span data-ttu-id="d817f-111">`Sequence`Ключевое слово используется в `Parallel` блоке сценария для последовательного выполнения выбранных команд.</span><span class="sxs-lookup"><span data-stu-id="d817f-111">The `Sequence` keyword is used in a `Parallel` script block to run selected commands sequentially.</span></span>

<span data-ttu-id="d817f-112">Поскольку действия рабочего процесса последовательно выполняются по умолчанию, `Sequence` ключевое слово действует только в `Parallel` блоке script.</span><span class="sxs-lookup"><span data-stu-id="d817f-112">Because workflow activities run sequentially by default, the `Sequence` keyword is only effective in a `Parallel` script block.</span></span> <span data-ttu-id="d817f-113">Если `Sequence` ключевое слово не включается в `Parallel` блок сценария, оно является допустимым, но неэффективным.</span><span class="sxs-lookup"><span data-stu-id="d817f-113">If the `Sequence` keyword isn't included in a `Parallel` script block, it's valid but ineffective.</span></span>

<span data-ttu-id="d817f-114">`Sequence`Блок скрипта позволяет выполнять несколько команд параллельно, позволяя последовательно выполнять зависимые команды.</span><span class="sxs-lookup"><span data-stu-id="d817f-114">The `Sequence` script block lets you run more commands in parallel by allowing you to run dependent commands sequentially.</span></span>

## <a name="syntax"></a><span data-ttu-id="d817f-115">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d817f-115">Syntax</span></span>

### <a name="workflow-using-sequence"></a><span data-ttu-id="d817f-116">Рабочий процесс с использованием последовательности</span><span class="sxs-lookup"><span data-stu-id="d817f-116">Workflow using Sequence</span></span>

```
workflow <Verb-Noun>
{
    Sequence
    {
        [<Activity>]
        [<Activity>]
        # ...
    }
}
```

### <a name="workflow-using-parallel-and-sequence"></a><span data-ttu-id="d817f-117">Рабочий процесс с использованием параллельных и последовательных операций</span><span class="sxs-lookup"><span data-stu-id="d817f-117">Workflow using Parallel and Sequence</span></span>

```
workflow <Verb-Noun>
{
    Parallel
    {
        [<Activity>]
        Sequence
        {
            [<Activity>]
            [<Activity>]
            # ...
        }
    }
}
```

## <a name="detailed-description"></a><span data-ttu-id="d817f-118">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="d817f-118">Detailed description</span></span>

<span data-ttu-id="d817f-119">Команды в блоке сценария `Parallel` могут выполняться одновременно.</span><span class="sxs-lookup"><span data-stu-id="d817f-119">The commands in a `Parallel` script block can run concurrently.</span></span> <span data-ttu-id="d817f-120">Порядок их запуска не определен.</span><span class="sxs-lookup"><span data-stu-id="d817f-120">The order in which they run is not determined.</span></span> <span data-ttu-id="d817f-121">Эта функция повышает производительность рабочего процесса скрипта.</span><span class="sxs-lookup"><span data-stu-id="d817f-121">This feature improves the performance of a script workflow.</span></span>

<span data-ttu-id="d817f-122">Можно использовать `Sequence` блок сценария для последовательного выполнения выбранных действий, даже если они отображаются в `Parallel` блоке сценария.</span><span class="sxs-lookup"><span data-stu-id="d817f-122">You can use a `Sequence` script block to run selected activities sequentially, even though the activities appear in a `Parallel` script block.</span></span>

<span data-ttu-id="d817f-123">Действия в `Sequence` блоке сценария выполняются последовательно в том порядке, в котором они перечислены.</span><span class="sxs-lookup"><span data-stu-id="d817f-123">The activities in a `Sequence` script block run consecutively in the order that they are listed.</span></span> <span data-ttu-id="d817f-124">Действие в `Sequence` блоке скрипта начинается только после завершения предыдущего действия.</span><span class="sxs-lookup"><span data-stu-id="d817f-124">An activity in a `Sequence` script block starts only after the previous activity completes.</span></span>

<span data-ttu-id="d817f-125">Однако если блок скрипта `Sequence` появляется в `Parallel` блоке скрипта, порядок `Sequence` выполнения блока скрипта не определяется.</span><span class="sxs-lookup"><span data-stu-id="d817f-125">However, when the `Sequence` script block appears in a `Parallel` script block, the order in which the `Sequence` script block runs isn't determined.</span></span> <span data-ttu-id="d817f-126">Он может выполняться до, после или параллельно с другими действиями в `Parallel` блоке script.</span><span class="sxs-lookup"><span data-stu-id="d817f-126">It might run before, after, or concurrent with other activities in the `Parallel` script block.</span></span>

<span data-ttu-id="d817f-127">Например, следующий рабочий процесс включает `Parallel` блок сценария, который запускает действия, получающие процессы и службы на компьютере.</span><span class="sxs-lookup"><span data-stu-id="d817f-127">For example, the following workflow includes a `Parallel` script block that runs activities that get processes and services on the computer.</span></span> <span data-ttu-id="d817f-128">`Parallel`Блок скрипта содержит `Sequence` блок скрипта, который получает сведения из файла и использует эти сведения в качестве входных данных для скрипта.</span><span class="sxs-lookup"><span data-stu-id="d817f-128">The `Parallel` script block contains a `Sequence` script block that gets information from a file and uses the information as input to a script.</span></span>

<span data-ttu-id="d817f-129">`Get-Process`Команды, `Get-Service` и, связанные с исправлениями, не зависят друг от друга.</span><span class="sxs-lookup"><span data-stu-id="d817f-129">The `Get-Process`, `Get-Service`, and hotfix-related commands are independent of each other.</span></span> <span data-ttu-id="d817f-130">Команды могут выполняться параллельно или в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="d817f-130">The commands can run concurrently or in any order.</span></span> <span data-ttu-id="d817f-131">Но команда, которая получает сведения об исправлении, должна выполняться перед командой, которая ее использует.</span><span class="sxs-lookup"><span data-stu-id="d817f-131">But, the command that gets the hotfix information must run before the command that uses it.</span></span>

```powershell
workflow Test-Workflow
{
    Parallel
    {
    Get-Process
    Get-Service

    Sequence
    {
        $Hotfix = Get-Content 'D:\HotFixes\Required.txt'
        Foreach ($h in $Hotfix) {'D:\Scripts\Verify-Hotfix' -Hotfix $h}
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="d817f-132">См. также статью</span><span class="sxs-lookup"><span data-stu-id="d817f-132">See also</span></span>

[<span data-ttu-id="d817f-133">about_ForEach</span><span class="sxs-lookup"><span data-stu-id="d817f-133">about_ForEach</span></span>](../../Microsoft.PowerShell.Core/About/about_Foreach.md)

[<span data-ttu-id="d817f-134">about_ForEach параллельно</span><span class="sxs-lookup"><span data-stu-id="d817f-134">about_ForEach-Parallel</span></span>](about_ForEach-Parallel.md)

[<span data-ttu-id="d817f-135">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="d817f-135">about_Language_Keywords</span></span>](../../Microsoft.PowerShell.Core/About/about_Language_Keywords.md)

[<span data-ttu-id="d817f-136">about_Parallel</span><span class="sxs-lookup"><span data-stu-id="d817f-136">about_Parallel</span></span>](about_Parallel.md)

[<span data-ttu-id="d817f-137">about_Workflows</span><span class="sxs-lookup"><span data-stu-id="d817f-137">about_Workflows</span></span>](about_Workflows.md)

[<span data-ttu-id="d817f-138">Создание рабочего процесса с помощью сценария Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d817f-138">Creating a Workflow by Using a Windows PowerShell Script</span></span>](/previous-versions/powershell/scripting/developer/workflow/creating-a-workflow-by-using-a-windows-powershell-script)
