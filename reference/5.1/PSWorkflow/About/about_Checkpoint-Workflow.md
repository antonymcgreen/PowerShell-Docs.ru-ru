---
description: Описывает действие Checkpoint-Workflow, которое принимает контрольную точку в рабочем процессе.
keywords: powershell,командлет
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_checkpoint-workflow?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Рабочий процесс about_Checkpoint
ms.openlocfilehash: 223deb07ff6ed387cf04736116ea0ce3f998bb59
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231621"
---
# <a name="about-checkpoint-workflow"></a><span data-ttu-id="3be58-104">О Checkpoint-Workflow</span><span class="sxs-lookup"><span data-stu-id="3be58-104">About Checkpoint-Workflow</span></span>

## <a name="short-description"></a><span data-ttu-id="3be58-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="3be58-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="3be58-106">Описывает действие Checkpoint-Workflow, которое принимает контрольную точку в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="3be58-106">Describes the Checkpoint-Workflow activity, which takes a checkpoint in a workflow.</span></span>

## <a name="long-description"></a><span data-ttu-id="3be58-107">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="3be58-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="3be58-108">Действие Checkpoint-Workflow принимает контрольную точку, которая сохраняет состояние и данные в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="3be58-108">The Checkpoint-Workflow activity takes a checkpoint, which saves state and data in the workflow.</span></span> <span data-ttu-id="3be58-109">Если рабочий процесс приостановлен или прерван, его можно возобновить с самой последней контрольной точки, а не перезапускать.</span><span class="sxs-lookup"><span data-stu-id="3be58-109">If the workflow is suspended or interrupted, it can be resumed from the most recent checkpoint, rather than having to be restarted.</span></span>

<span data-ttu-id="3be58-110">Действие Checkpoint-Workflow допустимо только в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="3be58-110">The Checkpoint-Workflow activity is valid only in a workflow.</span></span>

### <a name="syntax"></a><span data-ttu-id="3be58-111">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3be58-111">SYNTAX</span></span>

```
Workflow <Verb-Noun>
{
    Checkpoint-Workflow
}
```

<span data-ttu-id="3be58-112">Действие Checkpoint-Workflow не принимает никаких параметров, включая общие параметры и общие параметры рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="3be58-112">The Checkpoint-Workflow activity does not accept any parameters, including common parameters and workflow common parameters.</span></span>

<span data-ttu-id="3be58-113">Вы можете поместить контрольную точку Checkpoint-Activity в любое место в рабочем процессе после инструкции CmdletBinding или param.</span><span class="sxs-lookup"><span data-stu-id="3be58-113">You can place the Checkpoint-Activity checkpoint anywhere in a workflow after the CmdletBinding or Param statement.</span></span> <span data-ttu-id="3be58-114">Однако при размещении контрольных точек учитывайте затраты на производительность при сборе данных и записи на диск на компьютере, на котором выполняется рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="3be58-114">However, when placing checkpoints, consider the performance cost of collecting the data and writing it to disk on the computer that is running the workflow.</span></span>

<span data-ttu-id="3be58-115">Убедитесь, что время, необходимое для перезапуска раздела рабочего процесса в случае его прерывания, больше, чем время, которое занимает запись состояния и данных контрольной точки на диск.</span><span class="sxs-lookup"><span data-stu-id="3be58-115">Be sure that the time it takes to rerun a section of the workflow if it is interrupted is greater than the time it takes to write the checkpoint state and data to disk.</span></span>

<span data-ttu-id="3be58-116">Рассмотрите возможность создания контрольных точек после критических действий, чтобы рабочий процесс можно было возобновить, а не перезапускать.</span><span class="sxs-lookup"><span data-stu-id="3be58-116">Consider taking checkpoints after critical steps so the workflow can be resumed rather than restarted.</span></span> <span data-ttu-id="3be58-117">Например, создавайте контрольную точку после команд, которые не идемпотентными.</span><span class="sxs-lookup"><span data-stu-id="3be58-117">For example, take a checkpoint after commands that are not idempotent.</span></span>

### <a name="about-checkpoints"></a><span data-ttu-id="3be58-118">О КОНТРОЛЬНЫХ ТОЧКАХ</span><span class="sxs-lookup"><span data-stu-id="3be58-118">ABOUT CHECKPOINTS</span></span>

<span data-ttu-id="3be58-119">Контрольная точка — это моментальный снимок текущего состояния рабочего процесса, включая текущие значения переменных и любые выходные данные, созданные на этот момент, который сохраняется на диске.</span><span class="sxs-lookup"><span data-stu-id="3be58-119">A checkpoint is a snapshot of the current state of the workflow, including the current values of variables, and any output generated up to that point, and it saves it to disk.</span></span>

<span data-ttu-id="3be58-120">Если рабочий процесс был прерван, намеренно или непреднамеренно, Рабочий процесс Windows PowerShell автоматически использует данные в последней контрольной точке для восстановления и возобновления рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="3be58-120">If a workflow is interrupted, intentionally or unintentionally, Windows PowerShell Workflow automatically uses the data in newest checkpoint to recover and resume the workflow.</span></span>

<span data-ttu-id="3be58-121">При запуске рабочего процесса в качестве задания, например с помощью общего параметра рабочего процесса AsJob, контрольные точки рабочих процессов сохраняются до тех пор, пока не будет удалено задание, например с помощью командлета Remove-Job.</span><span class="sxs-lookup"><span data-stu-id="3be58-121">When you run the workflow as a job, such as by using the AsJob workflow common parameter, the workflow checkpoints are retained until you delete the job, such as by using the Remove-Job cmdlet.</span></span>
<span data-ttu-id="3be58-122">В противном случае контрольные точки рабочих процессов удаляются после завершения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="3be58-122">Otherwise, workflow checkpoints are deleted when the workflow completes.</span></span>

### <a name="other-checkpointing-techniques"></a><span data-ttu-id="3be58-123">ДРУГИЕ МЕТОДЫ СОЗДАНИЯ КОНТРОЛЬНЫХ ТОЧЕК</span><span class="sxs-lookup"><span data-stu-id="3be58-123">OTHER CHECKPOINTING TECHNIQUES</span></span>

<span data-ttu-id="3be58-124">Помимо Checkpoint-Workflow действия, Рабочий процесс Windows PowerShell поддерживает другие методы создания контрольных точек, включая следующие.</span><span class="sxs-lookup"><span data-stu-id="3be58-124">In addition to the Checkpoint-Workflow activity, Windows PowerShell Workflow supports other checkpointing techniques, including the following:</span></span>

- <span data-ttu-id="3be58-125">Общий параметр рабочего процесса PSPersist</span><span class="sxs-lookup"><span data-stu-id="3be58-125">PSPersist workflow common parameter</span></span>
- <span data-ttu-id="3be58-126">Общий параметр действия PSPersist</span><span class="sxs-lookup"><span data-stu-id="3be58-126">PSPersist activity common parameter</span></span>
- <span data-ttu-id="3be58-127">Переменная Псперсистпреференце (в рабочем процессе)</span><span class="sxs-lookup"><span data-stu-id="3be58-127">PSPersistPreference variable (in a workflow)</span></span>

<span data-ttu-id="3be58-128">Дополнительные сведения о добавлении контрольной точки в рабочий процесс см. в разделе "Добавление контрольных точек в рабочий процесс".</span><span class="sxs-lookup"><span data-stu-id="3be58-128">For more information about adding a checkpoint to a workflow, see "How to Add Checkpoints to a Workflow."</span></span>

## <a name="examples"></a><span data-ttu-id="3be58-129">Примеры</span><span class="sxs-lookup"><span data-stu-id="3be58-129">EXAMPLES</span></span>

<span data-ttu-id="3be58-130">Следующий рабочий процесс включает вызов действия Checkpoint-Workflow после завершения длительной функции и скрипта, который совместно используют данные.</span><span class="sxs-lookup"><span data-stu-id="3be58-130">The following workflow includes a call to the Checkpoint-Workflow activity after completing a long-running function and a script that share data.</span></span>

```powershell
Workflow Test-Workflow
{
    $a = Invoke-LongRunningFunction
    InlineScript { \\Server\Share\Get-DataPacks.ps1 $Using:a}
    Checkpoint-Workflow

    Invoke-LongRunningFunction
    {
        ...
    }
}
```

## <a name="see-also"></a><span data-ttu-id="3be58-131">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="3be58-131">SEE ALSO</span></span>

[<span data-ttu-id="3be58-132">Запись рабочего процесса Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3be58-132">Writing a Windows PowerShell Workflow</span></span>](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow)
