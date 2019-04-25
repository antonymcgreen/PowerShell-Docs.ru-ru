---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.openlocfilehash: 5b31fe833fb0f9d0f3f2733e777e4608a697d583
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62057933"
---
# <a name="side-by-side-module-versioning-support-for-dsc-resources"></a><span data-ttu-id="39a19-102">Поддержка параллельного управления версиями модулей для ресурсов DSC</span><span class="sxs-lookup"><span data-stu-id="39a19-102">Side-By-Side Module Versioning Support for DSC Resources</span></span>

<span data-ttu-id="39a19-103">Модули, содержащие ресурсы DSC, могут быть установлены параллельно, а конфигурации DSC могут использовать конкретную версию ресурса, установленного в системе.</span><span class="sxs-lookup"><span data-stu-id="39a19-103">Modules containing DSC resources can be installed side-by-side, and DSC configurations can use a specific version of the resource that is installed on the system.</span></span>

<span data-ttu-id="39a19-104">Дополнительные сведения см. в разделе [Использование ресурсов с несколькими версиями](https://msdn.microsoft.com/powershell/dsc/sxsresource).</span><span class="sxs-lookup"><span data-stu-id="39a19-104">For more information, see [Using resources with multiple versions](https://msdn.microsoft.com/powershell/dsc/sxsresource).</span></span>

## <a name="known-issues"></a><span data-ttu-id="39a19-105">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="39a19-105">Known issues</span></span>

<span data-ttu-id="39a19-106">Ниже перечислены известные с параллельной установкой в этом выпуске:</span><span class="sxs-lookup"><span data-stu-id="39a19-106">In this release, the following are known issues of side-by-side installation:</span></span>

-   <span data-ttu-id="39a19-107">Использование двух различных версий ресурса DSC в одной конфигурации не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="39a19-107">Using two different versions of the DSC resource within the same configuration is not supported.</span></span>
