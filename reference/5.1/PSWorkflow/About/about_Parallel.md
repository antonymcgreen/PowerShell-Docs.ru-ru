---
description: Описывает ключевое слово Parallel, которое запускает действия в рабочем процессе в параллельном режиме.
keywords: powershell,командлет
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_parallel?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Parallel
ms.openlocfilehash: 402e93672bbea4ec9b6bfda8d608f266f6c40a21
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231610"
---
# <a name="about-parallel"></a>О программе Parallel

## <a name="short-description"></a>КРАТКОЕ ОПИСАНИЕ
Описывает ключевое слово Parallel, которое запускает действия в рабочем процессе в параллельном режиме.

## <a name="long-description"></a>ПОДРОБНОЕ ОПИСАНИЕ

Ключевое слово Parallel параллельно запускает действия рабочего процесса. Это ключевое слово допустимо только в рабочем процессе Windows PowerShell.

### <a name="syntax"></a>SYNTAX

```
workflow <Verb-Noun>
{
     Parallel
     {
          [<Activity>]
          [<Activity>]
        ...
     }
 }
```

## <a name="detailed-description"></a>ПОДРОБНОЕ ОПИСАНИЕ

Команды в блоке сценария Parallel могут выполняться одновременно. Порядок их запуска не определен.

Например, в следующем рабочем процессе имеется блок сценария Parallel, в котором выполняются действия, обращающиеся к процессам и службам на компьютере. Так как команды Get-Process и Get-Service независимы друг от друга, они могут выполняться параллельно и в любом порядке.

```powershell
workflow Test-Workflow
{
    Parallel
    {
         Get-Process
         Get-Service
    }
}
```

Параллельно выполняемые команды очень эффективны и сокращают время, необходимое для значительного выполнения рабочего процесса.

Для выполнения выбранных команд в блоке параллельного сценария в последовательном порядке используйте ключевое слово Sequence. Дополнительные сведения см. в разделе about_Sequence.

Чтобы выполнить параллельный блок скрипта для элементов в коллекции, используйте ключевые слова ForEach или ForEach-Parallel.

## <a name="see-also"></a>СМ. ТАКЖЕ

["Запись рабочего процесса скрипта"](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj574157(v=ws.11))

[about_ForEach](../../Microsoft.PowerShell.Core/About/about_Foreach.md)

[about_ForEach параллельно](about_ForEach-Parallel.md)

[about_Language_Keywords](../../Microsoft.PowerShell.Core/About/about_Language_Keywords.md)

[about_Sequence](about_Sequence.md)

[about_Workflows](about_workflows.md)
