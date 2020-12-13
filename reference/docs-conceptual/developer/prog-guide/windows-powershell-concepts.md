---
ms.date: 06/12/2019
ms.topic: reference
title: Основные понятия Windows PowerShell
description: Основные понятия Windows PowerShell
ms.openlocfilehash: a9b88a2e575b7ff7c036ce0fcbc035f0b55d0f5f
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "93355364"
---
# <a name="windows-powershell-concepts"></a><span data-ttu-id="60416-103">Основные понятия Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="60416-103">Windows PowerShell Concepts</span></span>

<span data-ttu-id="60416-104">В этом разделе содержатся общие сведения, которые помогут вам понять, как работает PowerShell с точки зрения разработчика.</span><span class="sxs-lookup"><span data-stu-id="60416-104">This section contains conceptual information that will help you understand PowerShell from a developer's viewpoint.</span></span>

|<span data-ttu-id="60416-105">Имя раздела</span><span class="sxs-lookup"><span data-stu-id="60416-105">Topic Name</span></span>|<span data-ttu-id="60416-106">Описание</span><span class="sxs-lookup"><span data-stu-id="60416-106">Description</span></span>|
|----------------|-----------------|
|[<span data-ttu-id="60416-107">about_Objects</span><span class="sxs-lookup"><span data-stu-id="60416-107">about_Objects</span></span>](/powershell/module/microsoft.powershell.core/about/about_objects)|<span data-ttu-id="60416-108">Описание объектов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="60416-108">Description of PowerShell objects.</span></span> <span data-ttu-id="60416-109">Дополнительные сведения см. в разделе [о создании объектов](/powershell/module/microsoft.powershell.core/about/about_object_creation) .</span><span class="sxs-lookup"><span data-stu-id="60416-109">For more information, see [About Object Creation](/powershell/module/microsoft.powershell.core/about/about_object_creation)</span></span>|
|[<span data-ttu-id="60416-110">Создание пространств выполнения</span><span class="sxs-lookup"><span data-stu-id="60416-110">Creating Runspaces</span></span>](../hosting/creating-runspaces.md)|<span data-ttu-id="60416-111">Операционные среды, в которых обрабатываются команды.</span><span class="sxs-lookup"><span data-stu-id="60416-111">The operating environments where commands are processed.</span></span> <span data-ttu-id="60416-112">Дополнительные сведения см. в разделе [пространство выполнения класса](/dotnet/api/system.management.automation.runspaces.runspace).</span><span class="sxs-lookup"><span data-stu-id="60416-112">For more information, see [Runspace Class](/dotnet/api/system.management.automation.runspaces.runspace).</span></span>|
|[<span data-ttu-id="60416-113">Расширение объектов выходных данных</span><span class="sxs-lookup"><span data-stu-id="60416-113">Extending Output Objects</span></span>](../cmdlet/extending-output-objects.md)|<span data-ttu-id="60416-114">Как расширять объекты PowerShell.</span><span class="sxs-lookup"><span data-stu-id="60416-114">How to extend PowerShell objects.</span></span> <span data-ttu-id="60416-115">Дополнительные сведения см. в разделе [About Types.ps1XML](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml) .</span><span class="sxs-lookup"><span data-stu-id="60416-115">For more information, see [About Types.ps1xml](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml)</span></span>|
|[<span data-ttu-id="60416-116">Регистрация командлетов</span><span class="sxs-lookup"><span data-stu-id="60416-116">Registering Cmdlets</span></span>](../cmdlet/registering-cmdlets.md)|<span data-ttu-id="60416-117">Как сделать модули и оснастки доступными в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="60416-117">How to make modules and snap-ins available in PowerShell.</span></span> <span data-ttu-id="60416-118">Дополнительные сведения см. в разделе [модули и оснастки](../cmdlet/modules-and-snap-ins.md).</span><span class="sxs-lookup"><span data-stu-id="60416-118">For more information, see [Modules and Snap-ins](../cmdlet/modules-and-snap-ins.md).</span></span>|
|[<span data-ttu-id="60416-119">Запрос на подтверждение от командлетов</span><span class="sxs-lookup"><span data-stu-id="60416-119">Requesting Confirmation from Cmdlets</span></span>](../cmdlet/requesting-confirmation-from-cmdlets.md)|<span data-ttu-id="60416-120">Как командлеты и поставщики запрашивают отзыв от пользователя перед выполнением действия.</span><span class="sxs-lookup"><span data-stu-id="60416-120">How cmdlets and providers request feedback from the user before an action is taken.</span></span>|
|[<span data-ttu-id="60416-121">Класс Рунтимедефинедпараметер</span><span class="sxs-lookup"><span data-stu-id="60416-121">RuntimeDefinedParameter Class</span></span>](/dotnet/api/system.management.automation.runtimedefinedparameter)|<span data-ttu-id="60416-122">Объявления параметров среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="60416-122">Runtime parameter declarations.</span></span>|
|[<span data-ttu-id="60416-123">Пространство имен System. Management. Automation</span><span class="sxs-lookup"><span data-stu-id="60416-123">System.Management.Automation Namespace</span></span>](/dotnet/api/System.Management.Automation)|<span data-ttu-id="60416-124">Общие сведения о пространствах имен API PowerShell.</span><span class="sxs-lookup"><span data-stu-id="60416-124">Overview of PowerShell API namespaces.</span></span>|
|[<span data-ttu-id="60416-125">Общие сведения о поставщиках Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="60416-125">Windows PowerShell Provider Overview</span></span>](../provider/windows-powershell-provider-overview.md)|<span data-ttu-id="60416-126">Общие сведения о поставщиках PowerShell, которые используются для доступа к хранилищам данных.</span><span class="sxs-lookup"><span data-stu-id="60416-126">Overview about PowerShell providers that are used to access data stores.</span></span>|
|[<span data-ttu-id="60416-127">Написание справки для командлетов PowerShell</span><span class="sxs-lookup"><span data-stu-id="60416-127">Writing Help for PowerShell Cmdlets</span></span>](../help/writing-help-for-windows-powershell-cmdlets.md)|<span data-ttu-id="60416-128">Написание справки по командлетам PowerShell.</span><span class="sxs-lookup"><span data-stu-id="60416-128">How to write PowerShell cmdlet Help.</span></span>|

## <a name="see-also"></a><span data-ttu-id="60416-129">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="60416-129">See also</span></span>

[<span data-ttu-id="60416-130">Класс PowerShell</span><span class="sxs-lookup"><span data-stu-id="60416-130">PowerShell Class</span></span>](/dotnet/api/system.management.automation.powershell)

[<span data-ttu-id="60416-131">Справочник по API PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="60416-131">PowerShell Core API Reference</span></span>](/dotnet/api/?view=pscore-6.2.0&preserve-view=true)

[<span data-ttu-id="60416-132">Руководство программиста по Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="60416-132">Windows PowerShell Programmer's Guide</span></span>](windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="60416-133">Написание справки для модулей Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="60416-133">Writing Help for Windows PowerShell Modules</span></span>](../module/writing-help-for-windows-powershell-modules.md)

[<span data-ttu-id="60416-134">Написание поставщика Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="60416-134">Writing a Windows Powershell Provider</span></span>](../provider/writing-a-windows-powershell-provider.md)

[<span data-ttu-id="60416-135">Справочник по API Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="60416-135">Windows PowerShell API Reference</span></span>](/dotnet/api/?view=powershellsdk-1.1.0&preserve-view=true)

[<span data-ttu-id="60416-136">Справочник по Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="60416-136">Windows PowerShell Reference</span></span>](../windows-powershell-reference.md)
