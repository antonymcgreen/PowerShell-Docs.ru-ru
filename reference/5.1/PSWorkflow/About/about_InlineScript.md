---
description: Описывает `InlineScript` действие, которое запускает команды PowerShell в рабочем процессе.
keywords: powershell,командлет
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_inlinescript?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_InlineScript
ms.openlocfilehash: 2eaeb02c6441865551b586e27a39c4000826752b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231617"
---
# <a name="about-inlinescript"></a><span data-ttu-id="70b20-104">О InlineScript</span><span class="sxs-lookup"><span data-stu-id="70b20-104">About InlineScript</span></span>

## <a name="short-description"></a><span data-ttu-id="70b20-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="70b20-105">Short description</span></span>

<span data-ttu-id="70b20-106">Описывает `InlineScript` действие, которое запускает команды PowerShell в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="70b20-106">Describes the `InlineScript` activity, that runs PowerShell commands in a workflow.</span></span>

## <a name="long-description"></a><span data-ttu-id="70b20-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="70b20-107">Long description</span></span>

<span data-ttu-id="70b20-108">`InlineScript`Действие выполняет команды в рабочем процессе общего сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="70b20-108">The `InlineScript` activity runs commands in a shared PowerShell session's workflow.</span></span> <span data-ttu-id="70b20-109">`InlineScript` допустимо только в рабочих процессах.</span><span class="sxs-lookup"><span data-stu-id="70b20-109">`InlineScript` is only valid in workflows.</span></span>

## <a name="syntax"></a><span data-ttu-id="70b20-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="70b20-110">Syntax</span></span>

```
InlineScript {<script block>} <ActivityCommonParameters>
```

## <a name="detailed-description"></a><span data-ttu-id="70b20-111">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="70b20-111">Detailed description</span></span>

<span data-ttu-id="70b20-112">`InlineScript`Действие выполняет команды в общем сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="70b20-112">The `InlineScript` activity runs commands in a shared PowerShell session.</span></span> <span data-ttu-id="70b20-113">Его можно включить в рабочий процесс для выполнения команд, которые совместно используют данные и команды, которые в рабочем процессе не являются допустимыми.</span><span class="sxs-lookup"><span data-stu-id="70b20-113">You can include it in a workflow to run commands that share data and commands that aren't otherwise valid in a workflow.</span></span>

<span data-ttu-id="70b20-114">`InlineScript`Блок скрипта может включать все допустимые команды и выражения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="70b20-114">The `InlineScript` script block can include all valid PowerShell commands and expressions.</span></span> <span data-ttu-id="70b20-115">Поскольку команды и выражения в `InlineScript` блоке сценария выполняются в одном сеансе, они совместно используют все данные о состоянии и данных, включая импортированные модули и значения переменных.</span><span class="sxs-lookup"><span data-stu-id="70b20-115">Because the commands and expressions in an `InlineScript` script block run in the same session, they share all state and data, including imported modules and the values of variables.</span></span>

<span data-ttu-id="70b20-116">Действие можно разместить `InlineScript` в любом месте рабочего процесса или вложенного рабочего процесса, включая внутри цикла или оператора управления или блока сценариев Parallel или Sequence.</span><span class="sxs-lookup"><span data-stu-id="70b20-116">You can place an `InlineScript` activity anywhere in a workflow or nested workflow, including inside a loop or control statement or a Parallel or Sequence script block.</span></span>

<span data-ttu-id="70b20-117">`InlineScript`Действие имеет общие параметры действия, включая **псперсист**.</span><span class="sxs-lookup"><span data-stu-id="70b20-117">The `InlineScript` activity has the activity common parameters, including **PSPersist**.</span></span> <span data-ttu-id="70b20-118">Однако команды и выражения в `InlineScript` блоке скрипта не имеют таких функций рабочего процесса, как контрольные точки, сохраняемость и общие параметры рабочего процесса или действия.</span><span class="sxs-lookup"><span data-stu-id="70b20-118">However, the commands and expressions in an `InlineScript` script block don't have the workflow features such as checkpointing, or persistence, and workflow or activity common parameters.</span></span> <span data-ttu-id="70b20-119">Дополнительные сведения см. в разделе [about_ActivityCommonParameters](about_ActivityCommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="70b20-119">For more information, see [about_ActivityCommonParameters](about_ActivityCommonParameters.md).</span></span>

## <a name="inlinescript-variables"></a><span data-ttu-id="70b20-120">Переменные InlineScript</span><span class="sxs-lookup"><span data-stu-id="70b20-120">InlineScript Variables</span></span>

<span data-ttu-id="70b20-121">По умолчанию переменные, определенные в рабочем процессе, не видны командам в `InlineScript` блоке script.</span><span class="sxs-lookup"><span data-stu-id="70b20-121">By default, the variables that are defined in a workflow aren't visible to the commands in the `InlineScript` script block.</span></span> <span data-ttu-id="70b20-122">Чтобы сделать переменные рабочего процесса видимыми для `InlineScript` , используйте `$Using` Модификатор области.</span><span class="sxs-lookup"><span data-stu-id="70b20-122">To make workflow variables visible to the `InlineScript`, use the `$Using` scope modifier.</span></span> <span data-ttu-id="70b20-123">`$Using`Модификатор области требуется только один раз для каждой переменной в `InlineScript` .</span><span class="sxs-lookup"><span data-stu-id="70b20-123">The `$Using` scope modifier is required only once for each variable in the `InlineScript`.</span></span>

<span data-ttu-id="70b20-124">Дополнительные сведения об `$Using` модификаторе области см. в разделе [about_Remote_Variables](../../Microsoft.PowerShell.Core/About/about_Remote_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="70b20-124">For more information about the `$Using` scope modifier, see [about_Remote_Variables](../../Microsoft.PowerShell.Core/About/about_Remote_Variables.md).</span></span>

<span data-ttu-id="70b20-125">В следующем примере показано, что `$Using` Модификатор области делает значение `$a` переменной рабочего процесса верхнего уровня доступным для команд в `InlineScript` блоке script.</span><span class="sxs-lookup"><span data-stu-id="70b20-125">The following example shows that the `$Using` scope modifier makes the value of the `$a` top-level workflow variable available to the commands in the `InlineScript` script block.</span></span>

```powershell
workflow Test-Workflow {
  $a = 3

  ## Without $Using, the $a workflow variable isn't visible
  ## in inline script.
  InlineScript {"Inline A0 = $a"}

  ## $Using imports the variable and its current value.
  InlineScript {"Inline A1 = $Using:a"}
}

Test-Workflow
```

```output
Inline A0 =
Inline A1 = 3
```

## <a name="returning-variables-in-inlinescript"></a><span data-ttu-id="70b20-126">Возвращение переменных в InlineScript</span><span class="sxs-lookup"><span data-stu-id="70b20-126">Returning variables in InlineScript</span></span>

<span data-ttu-id="70b20-127">`InlineScript` команды могут изменять значение переменной, импортированной из области действия рабочего процесса, но изменения не отображаются в области рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="70b20-127">`InlineScript` commands can change the value of the variable that was imported from workflow scope, but the changes aren't visible in workflow scope.</span></span> <span data-ttu-id="70b20-128">Чтобы они стали доступны, нужно вернуть измененное значение в область рабочего процесса, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="70b20-128">To make them visible, return the changed value to the workflow scope, as shown in the following example.</span></span>

```powershell
workflow Test-Workflow {
  $a = 3

  ##  Changes to the InlineScript variable value don't
  ##  change the workflow variable.
  InlineScript {
    $a = $Using:a+1;
    "Inline A = $a"
  }
  "Workflow A = $a"

  ##  To change the variable in workflow scope, return the
  ##  new value.
  $a = InlineScript {$b = $Using:a+1; $b}
  "Workflow New A = $a"
}

Test-Workflow
```

```output
Inline A = 4
Workflow A = 3
Workflow New A = 4
```

> [!NOTE]
> <span data-ttu-id="70b20-129">Инструкция с `$Using` модификатором области должна появляться перед любым использованием переменной в `InlineScript` блоке script.</span><span class="sxs-lookup"><span data-stu-id="70b20-129">A statement with the `$Using` scope modifier should appear before any use of the variable in the `InlineScript` script block.</span></span>

## <a name="running-in-process"></a><span data-ttu-id="70b20-130">Выполнение внутри процесса</span><span class="sxs-lookup"><span data-stu-id="70b20-130">Running in-process</span></span>

<span data-ttu-id="70b20-131">Для повышения надежности команды в `InlineScript` блоке скрипта выполняются в собственном процессе, отдельно от процесса, в котором выполняется рабочий процесс, а затем возвращаются выходные данные в рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="70b20-131">To improve reliability, the commands in the `InlineScript` script block run in their own process, separate from the process in which the workflow runs, and then return their output to the workflow process.</span></span>

<span data-ttu-id="70b20-132">Чтобы направить PowerShell для выполнения `InlineScript` действия в рабочем процессе, удалите `InlineScript` значение из свойства **аутофпроцессактивити** конфигурации сеанса, например с помощью `New-PSWorkflowExecutionOption` командлета.</span><span class="sxs-lookup"><span data-stu-id="70b20-132">To direct PowerShell to run the `InlineScript` activity in the workflow process, remove the `InlineScript` value from the **OutOfProcessActivity** property of the session configuration, such as by using the `New-PSWorkflowExecutionOption` cmdlet.</span></span>

### <a name="example"></a><span data-ttu-id="70b20-133">Пример</span><span class="sxs-lookup"><span data-stu-id="70b20-133">Example</span></span>

<span data-ttu-id="70b20-134">`InlineScript`В следующем рабочем процессе содержатся команды, допустимые в PowerShell, но недопустимые в рабочих процессах.</span><span class="sxs-lookup"><span data-stu-id="70b20-134">The `InlineScript` in the following workflow includes commands that are valid in PowerShell but aren't valid in workflows.</span></span> <span data-ttu-id="70b20-135">Например, `New-Object` командлет с параметром **ComObject** .</span><span class="sxs-lookup"><span data-stu-id="70b20-135">For example, the `New-Object` cmdlet with the **ComObject** parameter.</span></span>

```powershell
workflow Test-Workflow
{
  $ie = InlineScript {
    $ie = New-Object -ComObject InternetExplorer.Application -Property @{navigate2="www.microsoft.com"}

    $ie.Visible = $true
  }

  $ie
}

Test-Workflow
```

## <a name="see-also"></a><span data-ttu-id="70b20-136">См. также статью</span><span class="sxs-lookup"><span data-stu-id="70b20-136">See also</span></span>

[<span data-ttu-id="70b20-137">about_ActivityCommonParameters</span><span class="sxs-lookup"><span data-stu-id="70b20-137">about_ActivityCommonParameters</span></span>](about_ActivityCommonParameters.md)

[<span data-ttu-id="70b20-138">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="70b20-138">about_Remote_Variables</span></span>](../../Microsoft.PowerShell.Core/About/about_Remote_Variables.md)

[<span data-ttu-id="70b20-139">about_WorkflowCommonParameters</span><span class="sxs-lookup"><span data-stu-id="70b20-139">about_WorkflowCommonParameters</span></span>](about_WorkflowCommonParameters.md)

<span data-ttu-id="70b20-140">Командлеты [PSWorkflow](xref:PSWorkflow)</span><span class="sxs-lookup"><span data-stu-id="70b20-140">[PSWorkflow](xref:PSWorkflow) cmdlets</span></span>

[<span data-ttu-id="70b20-141">Руководство по рабочим процессам</span><span class="sxs-lookup"><span data-stu-id="70b20-141">Workflows Guide</span></span>](/previous-versions/powershell/scripting/components/workflows-guide)

[<span data-ttu-id="70b20-142">Запись рабочего процесса Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="70b20-142">Writing a Windows PowerShell Workflow</span></span>](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow)
