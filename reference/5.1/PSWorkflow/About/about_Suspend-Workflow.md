---
description: Описывает `Suspend-Workflow` действие, которое приостанавливает рабочий процесс, в котором отображается действие.
keywords: powershell,командлет
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_suspend-workflow?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Рабочий процесс about_Suspend
ms.openlocfilehash: cbe5386ae5aa4bd863079fde240ddf2ce5384727
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231597"
---
# <a name="about-suspend-workflow"></a><span data-ttu-id="ae25a-104">О Suspend-Workflow</span><span class="sxs-lookup"><span data-stu-id="ae25a-104">About Suspend-Workflow</span></span>

## <a name="short-description"></a><span data-ttu-id="ae25a-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="ae25a-105">Short description</span></span>

<span data-ttu-id="ae25a-106">Описывает `Suspend-Workflow` действие, которое приостанавливает рабочий процесс, в котором отображается действие.</span><span class="sxs-lookup"><span data-stu-id="ae25a-106">Describes the `Suspend-Workflow` activity, which suspends the workflow in which the activity appears.</span></span>

## <a name="long-description"></a><span data-ttu-id="ae25a-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="ae25a-107">Long description</span></span>

<span data-ttu-id="ae25a-108">`Suspend-Workflow`Действие временно останавливает обработку рабочего процесса в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="ae25a-108">The `Suspend-Workflow` activity temporarily stops workflow processing from within the workflow.</span></span> <span data-ttu-id="ae25a-109">Перед приостановкой рабочий процесс Windows PowerShell принимает контрольную точку, поэтому состояние и данные рабочего процесса сохраняются, а рабочий процесс может возобновить работу с точки приостановки.</span><span class="sxs-lookup"><span data-stu-id="ae25a-109">Before suspending, Windows PowerShell Workflow takes a checkpoint so the workflow's state and data are preserved and the workflow can resume from the suspension point.</span></span>

<span data-ttu-id="ae25a-110">Для возобновления рабочего процесса пользователь, запускающий рабочий процесс, использует `Resume-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="ae25a-110">To resume the workflow, the user running the workflow uses the `Resume-Job` cmdlet.</span></span> <span data-ttu-id="ae25a-111">Вы не можете возобновить рабочий процесс в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="ae25a-111">You can't resume a workflow from within the workflow.</span></span>

## <a name="syntax"></a><span data-ttu-id="ae25a-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ae25a-112">Syntax</span></span>

```
workflow <Verb-Noun>
{
    Suspend-Workflow
}
```

## <a name="detailed-description"></a><span data-ttu-id="ae25a-113">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="ae25a-113">Detailed description</span></span>

<span data-ttu-id="ae25a-114">`Suspend-Workflow`Временная остановка рабочего процесса и возврат объекта задания, представляющего задание рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="ae25a-114">The `Suspend-Workflow` temporarily stops the workflow and returns a job object that represents the workflow job.</span></span> <span data-ttu-id="ae25a-115">Объект задания возвращается, даже если рабочий процесс не был запущен в качестве задания.</span><span class="sxs-lookup"><span data-stu-id="ae25a-115">A job object is returned even if you didn't run the workflow as a job.</span></span> <span data-ttu-id="ae25a-116">Например, например, с помощью общего параметра рабочего процесса **AsJob** .</span><span class="sxs-lookup"><span data-stu-id="ae25a-116">For example, such as by using the **AsJob** workflow common parameter.</span></span> <span data-ttu-id="ae25a-117">Состояние задания — **suspended**.</span><span class="sxs-lookup"><span data-stu-id="ae25a-117">The job state is **Suspended**.</span></span>

<span data-ttu-id="ae25a-118">Командлеты задания можно использовать для управления приостановленным заданием рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="ae25a-118">You can use the job cmdlets to manage the suspended workflow job.</span></span> <span data-ttu-id="ae25a-119">Чтобы возобновить задание рабочего процесса, используйте `Resume-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="ae25a-119">To resume the workflow job, use the `Resume-Job` cmdlet.</span></span>

<span data-ttu-id="ae25a-120">При возобновлении задания рабочего процесса Рабочий процесс возобновляет выполнение команды, следующей за `Suspend-Workflow` действием.</span><span class="sxs-lookup"><span data-stu-id="ae25a-120">When you resume the workflow job, the workflow resumes at the command that follows the `Suspend-Workflow` activity.</span></span>

<span data-ttu-id="ae25a-121">Например, следующий рабочий процесс включает `Suspend-Workflow` действие.</span><span class="sxs-lookup"><span data-stu-id="ae25a-121">For example, the following workflow includes the `Suspend-Workflow` activity.</span></span>
<span data-ttu-id="ae25a-122">При запуске рабочий процесс запускает `Get-Date` действие, сохраняет его выходные данные в `$a` переменной, а затем приостанавливает рабочий процесс и возвращает объект задания, представляющий приостановленный рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="ae25a-122">When you run the workflow, it runs the `Get-Date` activity, saves its output in the `$a` variable, and then suspends the workflow, and returns a job object that represents the suspended workflow.</span></span> <span data-ttu-id="ae25a-123">Тип задания — **псворкфловжоб**.</span><span class="sxs-lookup"><span data-stu-id="ae25a-123">The job type is **PSWorkflowJob**.</span></span>

<span data-ttu-id="ae25a-124">Для управления заданием рабочего процесса можно использовать командлеты задания, такие как `Get-Job` .</span><span class="sxs-lookup"><span data-stu-id="ae25a-124">You can use the job cmdlets, such as `Get-Job`, to manage the workflow job.</span></span>

```powershell
Workflow Test-Suspend
{
    $a = Get-Date
    Suspend-Workflow
    (Get-Date)- $a
}

Test-Suspend
```

```Output
Id  Name  PSJobTypeName  State      HasMoreData  Location  Command
--  ----  -------------  -----      -----------  --------  -------
8   Job8  PSWorkflowJob  Suspended  True         localhost Test-Suspend
```

## <a name="resuming-a-workflow-job"></a><span data-ttu-id="ae25a-125">Возобновление задания рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="ae25a-125">Resuming a workflow job</span></span>

<span data-ttu-id="ae25a-126">Чтобы возобновить задание рабочего процесса, используйте `Resume-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="ae25a-126">To resume the workflow job, use the `Resume-Job` cmdlet.</span></span> <span data-ttu-id="ae25a-127">Командлет `Resume-Job` возвращает объект задания рабочего процесса немедленно, даже если он еще не возобновлен.</span><span class="sxs-lookup"><span data-stu-id="ae25a-127">The `Resume-Job` cmdlet returns the workflow job object immediately, even though it might not yet be resumed.</span></span> <span data-ttu-id="ae25a-128">Чтобы дождаться возобновления задания, используйте параметр **Wait** или используйте `Get-Job` командлет для получения текущего объекта задания.</span><span class="sxs-lookup"><span data-stu-id="ae25a-128">To wait for the job to be resumed, use the **Wait** parameter, or use the `Get-Job` cmdlet to get the current job object.</span></span>

```powershell
Resume-Job -Name Job8
```

```Output
Id  Name  PSJobTypeName  State    HasMoreData  Location  Command
--  ----  -------------  -----    -----------  --------  -------
8   Job8  PSWorkflowJob  Running  True         localhost Test-Suspend
```

```powershell
Get-Job -Name Job8
```

```Output
Id  Name  PSJobTypeName  State      HasMoreData  Location  Command
--  ----  -------------  -----      -----------  --------  -------
8   Job8  PSWorkflowJob  Completed  True         localhost Test-Suspend
```

## <a name="getting-the-output-of-a-workflow-job"></a><span data-ttu-id="ae25a-129">Получение выходных данных задания рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="ae25a-129">Getting the output of a workflow job</span></span>

<span data-ttu-id="ae25a-130">Чтобы получить выходные данные задания рабочего процесса, используйте `Receive-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="ae25a-130">To get the output of a workflow job, use the `Receive-Job` cmdlet.</span></span> <span data-ttu-id="ae25a-131">Выходные данные показывают, что рабочий процесс возобновил выполнение команды, после которой был выполнен `Suspend-Workflow` командлет.</span><span class="sxs-lookup"><span data-stu-id="ae25a-131">The output shows that the workflow resumed at the command that followed the `Suspend-Workflow` cmdlet.</span></span> <span data-ttu-id="ae25a-132">Значение `$a` переменной, заполненное до приостановки, доступно рабочему процессу при его возобновлении.</span><span class="sxs-lookup"><span data-stu-id="ae25a-132">The value of the `$a` variable, which was populated before the suspension, is available to the workflow when it resumes.</span></span>

```powershell
Get-Job -Name Job8 | Receive-Job
```

```Output
Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 19
Milliseconds      : 823
Ticks             : 198230041
TotalDays         : 0.000229432917824074
TotalHours        : 0.00550639002777778
TotalMinutes      : 0.330383401666667
TotalSeconds      : 19.8230041
TotalMilliseconds : 19823.0041
PSComputerName    : localhost
```

## <a name="see-also"></a><span data-ttu-id="ae25a-133">См. также статью</span><span class="sxs-lookup"><span data-stu-id="ae25a-133">See also</span></span>

[<span data-ttu-id="ae25a-134">about_Workflows</span><span class="sxs-lookup"><span data-stu-id="ae25a-134">about_Workflows</span></span>](about_Workflows.md)

[<span data-ttu-id="ae25a-135">about_WorkflowCommonParameters</span><span class="sxs-lookup"><span data-stu-id="ae25a-135">about_WorkflowCommonParameters</span></span>](about_WorkflowCommonParameters.md)

<span data-ttu-id="ae25a-136">Командлеты [PSWorkflow](xref:PSWorkflow)</span><span class="sxs-lookup"><span data-stu-id="ae25a-136">[PSWorkflow](xref:PSWorkflow) cmdlets</span></span>

[<span data-ttu-id="ae25a-137">Руководство по рабочим процессам</span><span class="sxs-lookup"><span data-stu-id="ae25a-137">Workflows Guide</span></span>](/previous-versions/powershell/scripting/components/workflows-guide)

[<span data-ttu-id="ae25a-138">Запись рабочего процесса Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ae25a-138">Writing a Windows PowerShell Workflow</span></span>](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow)
