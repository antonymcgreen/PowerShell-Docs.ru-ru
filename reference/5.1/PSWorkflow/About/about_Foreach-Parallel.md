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
# <a name="about-foreach-parallel"></a>О Foreach-Parallel

## <a name="short-description"></a>КРАТКОЕ ОПИСАНИЕ
Описание `ForEach -Parallel` языковой конструкции в рабочем процессе Windows PowerShell.

## <a name="long-description"></a>ПОДРОБНОЕ ОПИСАНИЕ

Параметр **Parallel** `ForEach` ключевого слова выполняет команды в `ForEach` блоке скрипта один раз для каждого элемента в указанной коллекции.

Элементы в коллекции, такие как диск в коллекции дисков, обрабатываются параллельно. Команды в блоке скрипта выполняются последовательно для каждого элемента в коллекции.

`ForEach -Parallel` допустимо только в рабочем процессе Windows PowerShell.

### <a name="syntax"></a>SYNTAX

```
ForEach -Parallel ($<item> in $<collection>)
{
    [<Activity1>]
    [<Activity2>]
    ...
}
```

### <a name="detailed-description"></a>ПОДРОБНОЕ ОПИСАНИЕ

Как и в случае с инструкцией ForEach в Windows PowerShell, переменная, содержащая коллекцию, `$<collection>` должна быть определена перед `ForEach -Parallel` инструкцией, но переменная, представляющая текущий элемент, `$<item>` определяется в `ForEach -Parallel` инструкции.

`ForEach -Parallel`Конструкция отличается от `ForEach` ключевого слова и **параллельного** параметра. `ForEach`Ключевое слово обрабатывает элементы в коллекции последовательно. **Параллельный** параметр выполняет команды в блоке скрипта параллельно. Блок параллельного скрипта можно заключить в `ForEach -Parallel` блок скрипта.

Целевые компьютеры в рабочем процессе, такие как указанные в общем параметре рабочего процесса **PSComputerName** , всегда обрабатываются параллельно.
`ForEach -Parallel`Для этой цели не нужно указывать ключевое слово.

### <a name="examples"></a>Примеры

Следующий рабочий процесс содержит `ForEach -Parallel` инструкцию, которая обрабатывает диски, которые `Get-Disk` получает действие. Команды в `ForEach -Parallel` блоке скрипта выполняются последовательно, но выполняются на дисках параллельно. Диски могут обрабатываться параллельно и в любом порядке.

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

## <a name="see-also"></a>СМ. ТАКЖЕ

[Writing a Script Workflow](/previous-versions/powershell/scripting/developer/workflow/creating-a-workflow-by-using-a-windows-powershell-script)

[about_ForEach](../../Microsoft.PowerShell.Core/About/about_ForEach.md)

[about_Language_Keywords](../../Microsoft.PowerShell.Core/About/about_Language_Keywords.md)

[about_Parallel](about_Parallel.md)

[about_Workflows](about_Workflows.md)
