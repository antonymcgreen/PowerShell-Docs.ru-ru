---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Вложение конфигураций
description: DSC позволяет создавать составные конфигурации путем вложения конфигурации в другую конфигурацию.
ms.openlocfilehash: d7a81cb9673126e92e9185aacf19c5c7c17da8ca
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92667425"
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

В этом примере `FileConfig` принимает два обязательных параметра — **CopyFrom** и **CopyTo** , — которые используются как значения для свойств **SourcePath** и **DestinationPath** в блоке ресурсов `File`. Конфигурация `NestedConfig` вызывает конфигурацию `FileConfig`, как будто это ресурс. Свойства в блоке ресурсов `NestedConfig` ( **CopyFrom** и **CopyTo** ) — параметры конфигурации `FileConfig`.

Сейчас DSC не поддерживает вложенные конфигурации во вложенных конфигурациях. Допускается только один уровень вложенности конфигурации.

## <a name="see-also"></a>См. также

- [Составные ресурсы: использование DSC как ресурса](../resources/authoringResourceComposite.md)
