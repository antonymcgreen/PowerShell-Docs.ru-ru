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
# <a name="nesting-dsc-configurations"></a><span data-ttu-id="47482-103">Вложение конфигураций DSC</span><span class="sxs-lookup"><span data-stu-id="47482-103">Nesting DSC configurations</span></span>

<span data-ttu-id="47482-104">Вложенная конфигурация (также называемая составной конфигурацией) — это конфигурация, которая вызывается в составе другой конфигурации подобно ресурсу.</span><span class="sxs-lookup"><span data-stu-id="47482-104">A nested configuration (also called composite configuration) is a configuration that's called within another configuration as if it were a resource.</span></span> <span data-ttu-id="47482-105">Обе конфигурации должны быть определены в одном файле.</span><span class="sxs-lookup"><span data-stu-id="47482-105">Both configurations must be defined in the same file.</span></span>

<span data-ttu-id="47482-106">Давайте рассмотрим простой пример:</span><span class="sxs-lookup"><span data-stu-id="47482-106">Let's look at a simple example:</span></span>

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

<span data-ttu-id="47482-107">В этом примере `FileConfig` принимает два обязательных параметра — **CopyFrom** и **CopyTo**, — которые используются как значения для свойств **SourcePath** и **DestinationPath** в блоке ресурсов `File`.</span><span class="sxs-lookup"><span data-stu-id="47482-107">In this example, `FileConfig` takes two mandatory parameters, **CopyFrom** and **CopyTo**, which are used as the values for the **SourcePath** and **DestinationPath** properties in the `File` resource block.</span></span> <span data-ttu-id="47482-108">Конфигурация `NestedConfig` вызывает конфигурацию `FileConfig`, как будто это ресурс.</span><span class="sxs-lookup"><span data-stu-id="47482-108">The `NestedConfig` configuration calls `FileConfig` as if it were a resource.</span></span> <span data-ttu-id="47482-109">Свойства в блоке ресурсов `NestedConfig` (**CopyFrom** и **CopyTo**) — параметры конфигурации `FileConfig`.</span><span class="sxs-lookup"><span data-stu-id="47482-109">The properties in the `NestedConfig` resource block (**CopyFrom** and **CopyTo**) are the parameters of the `FileConfig` configuration.</span></span>

<span data-ttu-id="47482-110">Сейчас DSC не поддерживает вложенные конфигурации во вложенных конфигурациях.</span><span class="sxs-lookup"><span data-stu-id="47482-110">DSC doesn't currently support nesting configurations within nested configurations.</span></span> <span data-ttu-id="47482-111">Допускается только один уровень вложенности конфигурации.</span><span class="sxs-lookup"><span data-stu-id="47482-111">You can only nest a configuration one layer deep.</span></span>

## <a name="see-also"></a><span data-ttu-id="47482-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="47482-112">See Also</span></span>

- [<span data-ttu-id="47482-113">Составные ресурсы: использование DSC как ресурса</span><span class="sxs-lookup"><span data-stu-id="47482-113">Composite resources--Using a DSC configuration as a resource</span></span>](../resources/authoringResourceComposite.md)