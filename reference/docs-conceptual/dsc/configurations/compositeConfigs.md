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
# <a name="nesting-dsc-configurations"></a><span data-ttu-id="414b1-104">Вложение конфигураций DSC</span><span class="sxs-lookup"><span data-stu-id="414b1-104">Nesting DSC configurations</span></span>

<span data-ttu-id="414b1-105">Вложенная конфигурация (также называемая составной конфигурацией) — это конфигурация, которая вызывается в составе другой конфигурации подобно ресурсу.</span><span class="sxs-lookup"><span data-stu-id="414b1-105">A nested configuration (also called composite configuration) is a configuration that's called within another configuration as if it were a resource.</span></span> <span data-ttu-id="414b1-106">Обе конфигурации должны быть определены в одном файле.</span><span class="sxs-lookup"><span data-stu-id="414b1-106">Both configurations must be defined in the same file.</span></span>

<span data-ttu-id="414b1-107">Давайте рассмотрим простой пример:</span><span class="sxs-lookup"><span data-stu-id="414b1-107">Let's look at a simple example:</span></span>

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

<span data-ttu-id="414b1-108">В этом примере `FileConfig` принимает два обязательных параметра — **CopyFrom** и **CopyTo** , — которые используются как значения для свойств **SourcePath** и **DestinationPath** в блоке ресурсов `File`.</span><span class="sxs-lookup"><span data-stu-id="414b1-108">In this example, `FileConfig` takes two mandatory parameters, **CopyFrom** and **CopyTo** , which are used as the values for the **SourcePath** and **DestinationPath** properties in the `File` resource block.</span></span> <span data-ttu-id="414b1-109">Конфигурация `NestedConfig` вызывает конфигурацию `FileConfig`, как будто это ресурс.</span><span class="sxs-lookup"><span data-stu-id="414b1-109">The `NestedConfig` configuration calls `FileConfig` as if it were a resource.</span></span> <span data-ttu-id="414b1-110">Свойства в блоке ресурсов `NestedConfig` ( **CopyFrom** и **CopyTo** ) — параметры конфигурации `FileConfig`.</span><span class="sxs-lookup"><span data-stu-id="414b1-110">The properties in the `NestedConfig` resource block ( **CopyFrom** and **CopyTo** ) are the parameters of the `FileConfig` configuration.</span></span>

<span data-ttu-id="414b1-111">Сейчас DSC не поддерживает вложенные конфигурации во вложенных конфигурациях.</span><span class="sxs-lookup"><span data-stu-id="414b1-111">DSC doesn't currently support nesting configurations within nested configurations.</span></span> <span data-ttu-id="414b1-112">Допускается только один уровень вложенности конфигурации.</span><span class="sxs-lookup"><span data-stu-id="414b1-112">You can only nest a configuration one layer deep.</span></span>

## <a name="see-also"></a><span data-ttu-id="414b1-113">См. также</span><span class="sxs-lookup"><span data-stu-id="414b1-113">See Also</span></span>

- [<span data-ttu-id="414b1-114">Составные ресурсы: использование DSC как ресурса</span><span class="sxs-lookup"><span data-stu-id="414b1-114">Composite resources--Using a DSC configuration as a resource</span></span>](../resources/authoringResourceComposite.md)
