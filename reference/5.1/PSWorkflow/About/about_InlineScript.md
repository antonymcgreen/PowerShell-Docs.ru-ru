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
# <a name="about-inlinescript"></a>О InlineScript

## <a name="short-description"></a>Краткое описание

Описывает `InlineScript` действие, которое запускает команды PowerShell в рабочем процессе.

## <a name="long-description"></a>Подробное описание

`InlineScript`Действие выполняет команды в рабочем процессе общего сеанса PowerShell. `InlineScript` допустимо только в рабочих процессах.

## <a name="syntax"></a>Синтаксис

```
InlineScript {<script block>} <ActivityCommonParameters>
```

## <a name="detailed-description"></a>Подробное описание

`InlineScript`Действие выполняет команды в общем сеансе PowerShell. Его можно включить в рабочий процесс для выполнения команд, которые совместно используют данные и команды, которые в рабочем процессе не являются допустимыми.

`InlineScript`Блок скрипта может включать все допустимые команды и выражения PowerShell. Поскольку команды и выражения в `InlineScript` блоке сценария выполняются в одном сеансе, они совместно используют все данные о состоянии и данных, включая импортированные модули и значения переменных.

Действие можно разместить `InlineScript` в любом месте рабочего процесса или вложенного рабочего процесса, включая внутри цикла или оператора управления или блока сценариев Parallel или Sequence.

`InlineScript`Действие имеет общие параметры действия, включая **псперсист**. Однако команды и выражения в `InlineScript` блоке скрипта не имеют таких функций рабочего процесса, как контрольные точки, сохраняемость и общие параметры рабочего процесса или действия. Дополнительные сведения см. в разделе [about_ActivityCommonParameters](about_ActivityCommonParameters.md).

## <a name="inlinescript-variables"></a>Переменные InlineScript

По умолчанию переменные, определенные в рабочем процессе, не видны командам в `InlineScript` блоке script. Чтобы сделать переменные рабочего процесса видимыми для `InlineScript` , используйте `$Using` Модификатор области. `$Using`Модификатор области требуется только один раз для каждой переменной в `InlineScript` .

Дополнительные сведения об `$Using` модификаторе области см. в разделе [about_Remote_Variables](../../Microsoft.PowerShell.Core/About/about_Remote_Variables.md).

В следующем примере показано, что `$Using` Модификатор области делает значение `$a` переменной рабочего процесса верхнего уровня доступным для команд в `InlineScript` блоке script.

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

## <a name="returning-variables-in-inlinescript"></a>Возвращение переменных в InlineScript

`InlineScript` команды могут изменять значение переменной, импортированной из области действия рабочего процесса, но изменения не отображаются в области рабочего процесса. Чтобы они стали доступны, нужно вернуть измененное значение в область рабочего процесса, как показано в следующем примере.

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
> Инструкция с `$Using` модификатором области должна появляться перед любым использованием переменной в `InlineScript` блоке script.

## <a name="running-in-process"></a>Выполнение внутри процесса

Для повышения надежности команды в `InlineScript` блоке скрипта выполняются в собственном процессе, отдельно от процесса, в котором выполняется рабочий процесс, а затем возвращаются выходные данные в рабочий процесс.

Чтобы направить PowerShell для выполнения `InlineScript` действия в рабочем процессе, удалите `InlineScript` значение из свойства **аутофпроцессактивити** конфигурации сеанса, например с помощью `New-PSWorkflowExecutionOption` командлета.

### <a name="example"></a>Пример

`InlineScript`В следующем рабочем процессе содержатся команды, допустимые в PowerShell, но недопустимые в рабочих процессах. Например, `New-Object` командлет с параметром **ComObject** .

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

## <a name="see-also"></a>См. также статью

[about_ActivityCommonParameters](about_ActivityCommonParameters.md)

[about_Remote_Variables](../../Microsoft.PowerShell.Core/About/about_Remote_Variables.md)

[about_WorkflowCommonParameters](about_WorkflowCommonParameters.md)

Командлеты [PSWorkflow](xref:PSWorkflow)

[Руководство по рабочим процессам](/previous-versions/powershell/scripting/components/workflows-guide)

[Запись рабочего процесса Windows PowerShell](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow)
