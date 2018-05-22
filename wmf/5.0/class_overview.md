---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
ms.openlocfilehash: dfc171f9a3471f8fe7801283dd4a9b06860781a2
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
---
# <a name="creating-custom-types-using-powershell-classes"></a><span data-ttu-id="f6913-102">Создание настраиваемых типов с помощью классов PowerShell</span><span class="sxs-lookup"><span data-stu-id="f6913-102">Creating Custom Types using PowerShell Classes</span></span>

<span data-ttu-id="f6913-103">Мы улучшили язык PowerShell для определения классов и других определяемых пользователем типов благодаря использованию формального синтаксиса и семантики, которые похожи на другие объектно-ориентированные языки программирования.</span><span class="sxs-lookup"><span data-stu-id="f6913-103">We’ve improved the PowerShell language for defining classes and other user-defined types by using formal syntax and semantics that are similar to other object-oriented programming languages.</span></span> <span data-ttu-id="f6913-104">Целью этого шага является расширение вариантов использования PowerShell, доступных разработчикам и ИТ-специалистам, упрощение разработки артефактов PowerShell (например, ресурсов DSC) и ускорение освоения поверхностей управления.</span><span class="sxs-lookup"><span data-stu-id="f6913-104">The goal is to enable developers and IT professionals to embrace PowerShell for a wider range of use cases, simplify development of PowerShell artifacts (such as DSC resources), and accelerate coverage of management surfaces.</span></span>

## <a name="supported-scenarios-in-this-release"></a><span data-ttu-id="f6913-105">Поддерживаемые сценарии в этом выпуске</span><span class="sxs-lookup"><span data-stu-id="f6913-105">Supported scenarios in this release</span></span>

-   <span data-ttu-id="f6913-106">Определение ресурсов DSC и связанных с ними типов с помощью языка PowerShell</span><span class="sxs-lookup"><span data-stu-id="f6913-106">Define DSC resources and their associated types by using the PowerShell language</span></span>
-   <span data-ttu-id="f6913-107">Определение настраиваемых типов в PowerShell с помощью знакомых конструкций объектно-ориентированного программирования, таких как классы, свойства, методы и т. п.</span><span class="sxs-lookup"><span data-stu-id="f6913-107">Define custom types in PowerShell by using familiar object-oriented programming constructs, such as classes, properties, methods, etc.</span></span>
-   <span data-ttu-id="f6913-108">Поддержка наследования с помощью класса в PowerShell и базового ресурса DSC класса</span><span class="sxs-lookup"><span data-stu-id="f6913-108">Inheritance support with class in PowerShell and class base DSC resource</span></span>
-   <span data-ttu-id="f6913-109">Отладка типов с помощью языка PowerShell</span><span class="sxs-lookup"><span data-stu-id="f6913-109">Debug types by using the PowerShell language</span></span>
-   <span data-ttu-id="f6913-110">Создание и обработка исключений с помощью формальных механизмов и на нужном уровне</span><span class="sxs-lookup"><span data-stu-id="f6913-110">Generate and handle exceptions by using formal mechanisms, and at the right level</span></span>
