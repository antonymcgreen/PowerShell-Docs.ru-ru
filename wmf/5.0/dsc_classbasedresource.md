---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.openlocfilehash: 42f323590609319388e9a0a2c7c305dfa80c2d49
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
---
# <a name="class-based-dsc-resources"></a><span data-ttu-id="700bf-102">Ресурсы DSC, основанные на классах</span><span class="sxs-lookup"><span data-stu-id="700bf-102">Class-based DSC Resources</span></span>

## <a name="defining-dsc-resources-with-classes"></a><span data-ttu-id="700bf-103">Определение ресурсов DSC с помощью классов</span><span class="sxs-lookup"><span data-stu-id="700bf-103">Defining DSC resources with classes</span></span>

<span data-ttu-id="700bf-104">Основываясь на полученных отзывах, мы упростили создание и использование ресурсов DSC на основе классов.</span><span class="sxs-lookup"><span data-stu-id="700bf-104">Based on feedback, we’ve made authoring class-based DSC resources simpler and easier to understand.</span></span>
<span data-ttu-id="700bf-105">Ресурс DSC на основе класса и поставщик ресурсов DSC командлета имеют следующие отличия.</span><span class="sxs-lookup"><span data-stu-id="700bf-105">The major differences between a class-based DSC resource and a cmdlet DSC resource provider are:</span></span>

* <span data-ttu-id="700bf-106">MOF-файл для схемы не требуется.</span><span class="sxs-lookup"><span data-stu-id="700bf-106">A MOF file for the schema is not required.</span></span>
* <span data-ttu-id="700bf-107">Вложенная папка **DSCResource** в папке модуля не требуется.</span><span class="sxs-lookup"><span data-stu-id="700bf-107">A **DSCResource** subfolder in the module folder is not required.</span></span>
* <span data-ttu-id="700bf-108">Файл модуля PowerShell может содержать несколько классов ресурсов DSC.</span><span class="sxs-lookup"><span data-stu-id="700bf-108">A PowerShell module file can contain multiple DSC resource classes.</span></span>

<span data-ttu-id="700bf-109">Дополнительные сведения см. в разделе [Написание пользовательских ресурсов DSC с использованием классов PowerShell](https://msdn.microsoft.com/powershell/dsc/authoringresource).</span><span class="sxs-lookup"><span data-stu-id="700bf-109">For more information, see [Writing a custom DSC resource with PowerShell classes](https://msdn.microsoft.com/powershell/dsc/authoringresource).</span></span>
