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
# <a name="about-sequence"></a>О последовательности

## <a name="short-description"></a>Краткое описание

Описывает `Sequence` ключевое слово, которое последовательно запускает выбранные действия.

## <a name="long-description"></a>Подробное описание

`Sequence`Ключевое слово выполняет выбранные действия рабочего процесса последовательно. Действия рабочего процесса выполняются в том порядке, в котором они отображаются, и не выполняются одновременно. `Sequence`Ключевое слово допустимо только в рабочем процессе PowerShell.

`Sequence`Ключевое слово используется в `Parallel` блоке сценария для последовательного выполнения выбранных команд.

Поскольку действия рабочего процесса последовательно выполняются по умолчанию, `Sequence` ключевое слово действует только в `Parallel` блоке script. Если `Sequence` ключевое слово не включается в `Parallel` блок сценария, оно является допустимым, но неэффективным.

`Sequence`Блок скрипта позволяет выполнять несколько команд параллельно, позволяя последовательно выполнять зависимые команды.

## <a name="syntax"></a>Синтаксис

### <a name="workflow-using-sequence"></a>Рабочий процесс с использованием последовательности

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

### <a name="workflow-using-parallel-and-sequence"></a>Рабочий процесс с использованием параллельных и последовательных операций

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

## <a name="detailed-description"></a>Подробное описание

Команды в блоке сценария `Parallel` могут выполняться одновременно. Порядок их запуска не определен. Эта функция повышает производительность рабочего процесса скрипта.

Можно использовать `Sequence` блок сценария для последовательного выполнения выбранных действий, даже если они отображаются в `Parallel` блоке сценария.

Действия в `Sequence` блоке сценария выполняются последовательно в том порядке, в котором они перечислены. Действие в `Sequence` блоке скрипта начинается только после завершения предыдущего действия.

Однако если блок скрипта `Sequence` появляется в `Parallel` блоке скрипта, порядок `Sequence` выполнения блока скрипта не определяется. Он может выполняться до, после или параллельно с другими действиями в `Parallel` блоке script.

Например, следующий рабочий процесс включает `Parallel` блок сценария, который запускает действия, получающие процессы и службы на компьютере. `Parallel`Блок скрипта содержит `Sequence` блок скрипта, который получает сведения из файла и использует эти сведения в качестве входных данных для скрипта.

`Get-Process`Команды, `Get-Service` и, связанные с исправлениями, не зависят друг от друга. Команды могут выполняться параллельно или в любом порядке. Но команда, которая получает сведения об исправлении, должна выполняться перед командой, которая ее использует.

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

## <a name="see-also"></a>См. также статью

[about_ForEach](../../Microsoft.PowerShell.Core/About/about_Foreach.md)

[about_ForEach параллельно](about_ForEach-Parallel.md)

[about_Language_Keywords](../../Microsoft.PowerShell.Core/About/about_Language_Keywords.md)

[about_Parallel](about_Parallel.md)

[about_Workflows](about_Workflows.md)

[Создание рабочего процесса с помощью сценария Windows PowerShell](/previous-versions/powershell/scripting/developer/workflow/creating-a-workflow-by-using-a-windows-powershell-script)
