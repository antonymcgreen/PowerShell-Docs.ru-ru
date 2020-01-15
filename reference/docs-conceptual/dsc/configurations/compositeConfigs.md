---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Вложение конфигураций
ms.openlocfilehash: 07e4fb5b9d406153d2fbb4285e28b8d1f0dfdcf5
ms.sourcegitcommit: 1b88c280dd0799f225242608f0cbdab485357633
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75417867"
---
# <a name="nesting-dsc-configurations"></a>Вложение конфигураций DSC

Вложенная конфигурация (также называемая составной конфигурацией) — это конфигурация, которая вызывается в составе другой конфигурации подобно ресурсу. Обе конфигурации должны быть определены в одном файле.

Давайте рассмотрим простой пример:

```powershell
Configuration FileConfig
{
    param (
        [Parameter(Mandatory = $true)]
        [String] $CopyFrom,

        [Parameter(Mandatory = $true)]
        [String] $CopyTo
    )

    Import-DscResource -ModuleName PSDesiredStateConfiguration

    File FileTest
    {
        SourcePath = $CopyFrom
        DestinationPath = $CopyTo
        Ensure = 'Present'
    }
}

Configuration NestedFileConfig
{
    Node localhost
    {
        FileConfig NestedConfig
        {
            CopyFrom = 'C:\Test\TestFile.txt'
            CopyTo = 'C:\Test2'
        }
    }
}
```

В этом примере `FileConfig` принимает два обязательных параметра — **CopyFrom** и **CopyTo**, — которые используются как значения для свойств **SourcePath** и **DestinationPath** в блоке ресурсов `File`. Конфигурация `NestedConfig` вызывает конфигурацию `FileConfig`, как будто это ресурс. Свойства в блоке ресурсов `NestedConfig` (**CopyFrom** и **CopyTo**) — параметры конфигурации `FileConfig`.

Сейчас DSC не поддерживает вложенные конфигурации во вложенных конфигурациях. Допускается только один уровень вложенности конфигурации.

## <a name="see-also"></a>См. также:

- [Составные ресурсы: использование DSC как ресурса](../resources/authoringResourceComposite.md)