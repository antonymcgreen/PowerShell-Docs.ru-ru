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
# <a name="about-suspend-workflow"></a>О Suspend-Workflow

## <a name="short-description"></a>Краткое описание

Описывает `Suspend-Workflow` действие, которое приостанавливает рабочий процесс, в котором отображается действие.

## <a name="long-description"></a>Подробное описание

`Suspend-Workflow`Действие временно останавливает обработку рабочего процесса в рабочем процессе. Перед приостановкой рабочий процесс Windows PowerShell принимает контрольную точку, поэтому состояние и данные рабочего процесса сохраняются, а рабочий процесс может возобновить работу с точки приостановки.

Для возобновления рабочего процесса пользователь, запускающий рабочий процесс, использует `Resume-Job` командлет. Вы не можете возобновить рабочий процесс в рабочем процессе.

## <a name="syntax"></a>Синтаксис

```
workflow <Verb-Noun>
{
    Suspend-Workflow
}
```

## <a name="detailed-description"></a>Подробное описание

`Suspend-Workflow`Временная остановка рабочего процесса и возврат объекта задания, представляющего задание рабочего процесса. Объект задания возвращается, даже если рабочий процесс не был запущен в качестве задания. Например, например, с помощью общего параметра рабочего процесса **AsJob** . Состояние задания — **suspended**.

Командлеты задания можно использовать для управления приостановленным заданием рабочего процесса. Чтобы возобновить задание рабочего процесса, используйте `Resume-Job` командлет.

При возобновлении задания рабочего процесса Рабочий процесс возобновляет выполнение команды, следующей за `Suspend-Workflow` действием.

Например, следующий рабочий процесс включает `Suspend-Workflow` действие.
При запуске рабочий процесс запускает `Get-Date` действие, сохраняет его выходные данные в `$a` переменной, а затем приостанавливает рабочий процесс и возвращает объект задания, представляющий приостановленный рабочий процесс. Тип задания — **псворкфловжоб**.

Для управления заданием рабочего процесса можно использовать командлеты задания, такие как `Get-Job` .

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

## <a name="resuming-a-workflow-job"></a>Возобновление задания рабочего процесса

Чтобы возобновить задание рабочего процесса, используйте `Resume-Job` командлет. Командлет `Resume-Job` возвращает объект задания рабочего процесса немедленно, даже если он еще не возобновлен. Чтобы дождаться возобновления задания, используйте параметр **Wait** или используйте `Get-Job` командлет для получения текущего объекта задания.

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

## <a name="getting-the-output-of-a-workflow-job"></a>Получение выходных данных задания рабочего процесса

Чтобы получить выходные данные задания рабочего процесса, используйте `Receive-Job` командлет. Выходные данные показывают, что рабочий процесс возобновил выполнение команды, после которой был выполнен `Suspend-Workflow` командлет. Значение `$a` переменной, заполненное до приостановки, доступно рабочему процессу при его возобновлении.

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

## <a name="see-also"></a>См. также статью

[about_Workflows](about_Workflows.md)

[about_WorkflowCommonParameters](about_WorkflowCommonParameters.md)

Командлеты [PSWorkflow](xref:PSWorkflow)

[Руководство по рабочим процессам](/previous-versions/powershell/scripting/components/workflows-guide)

[Запись рабочего процесса Windows PowerShell](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow)
