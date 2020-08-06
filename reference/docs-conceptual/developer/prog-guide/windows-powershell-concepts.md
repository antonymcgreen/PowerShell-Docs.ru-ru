---
title: Основные понятия Windows PowerShell | Документация Майкрософт
ms.date: 6/12/2019
ms.openlocfilehash: a31c1df784b7b5f872c4647aece8fafa535db66b
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786957"
---
# <a name="windows-powershell-concepts"></a><span data-ttu-id="f493e-102">Основные понятия Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f493e-102">Windows PowerShell Concepts</span></span>

<span data-ttu-id="f493e-103">В этом разделе содержатся общие сведения, которые помогут вам понять, как работает PowerShell с точки зрения разработчика.</span><span class="sxs-lookup"><span data-stu-id="f493e-103">This section contains conceptual information that will help you understand PowerShell from a developer's viewpoint.</span></span>

|<span data-ttu-id="f493e-104">Имя раздела</span><span class="sxs-lookup"><span data-stu-id="f493e-104">Topic Name</span></span>|<span data-ttu-id="f493e-105">Описание</span><span class="sxs-lookup"><span data-stu-id="f493e-105">Description</span></span>|
|----------------|-----------------|
|[<span data-ttu-id="f493e-106">about_Objects</span><span class="sxs-lookup"><span data-stu-id="f493e-106">about_Objects</span></span>](/powershell/module/microsoft.powershell.core/about/about_objects)|<span data-ttu-id="f493e-107">Описание объектов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f493e-107">Description of PowerShell objects.</span></span> <span data-ttu-id="f493e-108">Дополнительные сведения см. в разделе [о создании объектов](/powershell/module/microsoft.powershell.core/about/about_object_creation) .</span><span class="sxs-lookup"><span data-stu-id="f493e-108">For more information, see [About Object Creation](/powershell/module/microsoft.powershell.core/about/about_object_creation)</span></span>|
|[<span data-ttu-id="f493e-109">Создание пространств выполнения</span><span class="sxs-lookup"><span data-stu-id="f493e-109">Creating Runspaces</span></span>](../hosting/creating-runspaces.md)|<span data-ttu-id="f493e-110">Операционные среды, в которых обрабатываются команды.</span><span class="sxs-lookup"><span data-stu-id="f493e-110">The operating environments where commands are processed.</span></span> <span data-ttu-id="f493e-111">Дополнительные сведения см. в разделе [пространство выполнения класса](/dotnet/api/system.management.automation.runspaces.runspace).</span><span class="sxs-lookup"><span data-stu-id="f493e-111">For more information, see [Runspace Class](/dotnet/api/system.management.automation.runspaces.runspace).</span></span>|
|[<span data-ttu-id="f493e-112">Расширение объектов выходных данных</span><span class="sxs-lookup"><span data-stu-id="f493e-112">Extending Output Objects</span></span>](../cmdlet/extending-output-objects.md)|<span data-ttu-id="f493e-113">Как расширять объекты PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f493e-113">How to extend PowerShell objects.</span></span> <span data-ttu-id="f493e-114">Дополнительные сведения см. в разделе [About Types.ps1XML](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml) .</span><span class="sxs-lookup"><span data-stu-id="f493e-114">For more information, see [About Types.ps1xml](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml)</span></span>|
|[<span data-ttu-id="f493e-115">Регистрация командлетов</span><span class="sxs-lookup"><span data-stu-id="f493e-115">Registering Cmdlets</span></span>](../cmdlet/registering-cmdlets.md)|<span data-ttu-id="f493e-116">Как сделать модули и оснастки доступными в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f493e-116">How to make modules and snap-ins available in PowerShell.</span></span> <span data-ttu-id="f493e-117">Дополнительные сведения см. в разделе [модули и оснастки](../cmdlet/modules-and-snap-ins.md).</span><span class="sxs-lookup"><span data-stu-id="f493e-117">For more information, see [Modules and Snap-ins](../cmdlet/modules-and-snap-ins.md).</span></span>|
|[<span data-ttu-id="f493e-118">Запрос на подтверждение от командлетов</span><span class="sxs-lookup"><span data-stu-id="f493e-118">Requesting Confirmation from Cmdlets</span></span>](../cmdlet/requesting-confirmation-from-cmdlets.md)|<span data-ttu-id="f493e-119">Как командлеты и поставщики запрашивают отзыв от пользователя перед выполнением действия.</span><span class="sxs-lookup"><span data-stu-id="f493e-119">How cmdlets and providers request feedback from the user before an action is taken.</span></span>|
|[<span data-ttu-id="f493e-120">Класс Рунтимедефинедпараметер</span><span class="sxs-lookup"><span data-stu-id="f493e-120">RuntimeDefinedParameter Class</span></span>](/dotnet/api/system.management.automation.runtimedefinedparameter)|<span data-ttu-id="f493e-121">Объявления параметров среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="f493e-121">Runtime parameter declarations.</span></span>|
|[<span data-ttu-id="f493e-122">Пространство имен System. Management. Automation</span><span class="sxs-lookup"><span data-stu-id="f493e-122">System.Management.Automation Namespace</span></span>](/dotnet/api/System.Management.Automation)|<span data-ttu-id="f493e-123">Общие сведения о пространствах имен API PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f493e-123">Overview of PowerShell API namespaces.</span></span>|
|[<span data-ttu-id="f493e-124">Общие сведения о поставщиках Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f493e-124">Windows PowerShell Provider Overview</span></span>](../provider/windows-powershell-provider-overview.md)|<span data-ttu-id="f493e-125">Общие сведения о поставщиках PowerShell, которые используются для доступа к хранилищам данных.</span><span class="sxs-lookup"><span data-stu-id="f493e-125">Overview about PowerShell providers that are used to access data stores.</span></span>|
|[<span data-ttu-id="f493e-126">Написание справки по командлетам PowerShell</span><span class="sxs-lookup"><span data-stu-id="f493e-126">Writing Help for PowerShell Cmdlets</span></span>](../help/writing-help-for-windows-powershell-cmdlets.md)|<span data-ttu-id="f493e-127">Написание справки по командлетам PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f493e-127">How to write PowerShell cmdlet Help.</span></span>|

## <a name="see-also"></a><span data-ttu-id="f493e-128">См. также</span><span class="sxs-lookup"><span data-stu-id="f493e-128">See also</span></span>

[<span data-ttu-id="f493e-129">Класс PowerShell</span><span class="sxs-lookup"><span data-stu-id="f493e-129">PowerShell Class</span></span>](/dotnet/api/system.management.automation.powershell)

[<span data-ttu-id="f493e-130">Справочник по API PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="f493e-130">PowerShell Core API Reference</span></span>](/dotnet/api/?view=pscore-6.2.0)

[<span data-ttu-id="f493e-131">Руководство программиста по Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f493e-131">Windows PowerShell Programmer's Guide</span></span>](windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="f493e-132">Написание справки для модулей Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f493e-132">Writing Help for Windows PowerShell Modules</span></span>](../module/writing-help-for-windows-powershell-modules.md)

[<span data-ttu-id="f493e-133">Написание поставщика Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f493e-133">Writing a Windows Powershell Provider</span></span>](../provider/writing-a-windows-powershell-provider.md)

[<span data-ttu-id="f493e-134">Справочник по API Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f493e-134">Windows PowerShell API Reference</span></span>](/dotnet/api/?view=powershellsdk-1.1.0)

[<span data-ttu-id="f493e-135">Справочник по Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f493e-135">Windows PowerShell Reference</span></span>](../windows-powershell-reference.md)
