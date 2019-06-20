---
title: Основные понятия Windows PowerShell | Документация Майкрософт
ms.custom: ''
ms.date: 6/12/2019
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3dd5608e-50b6-4c6a-aee3-dde0e86032bc
caps.latest.revision: 7
ms.openlocfilehash: 4410b1f9c80afefd5479fa68154f9947b805edcf
ms.sourcegitcommit: 13f24786ed39ca1c07eff2b73a1974c366e31cb8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2019
ms.locfileid: "67263857"
---
# <a name="windows-powershell-concepts"></a><span data-ttu-id="26faf-102">Основные понятия Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="26faf-102">Windows PowerShell Concepts</span></span>

<span data-ttu-id="26faf-103">Этот раздел содержит общие сведения, которые помогут вам понять PowerShell с точки зрения разработчика.</span><span class="sxs-lookup"><span data-stu-id="26faf-103">This section contains conceptual information that will help you understand PowerShell from a developer's viewpoint.</span></span>

|<span data-ttu-id="26faf-104">Имя раздела</span><span class="sxs-lookup"><span data-stu-id="26faf-104">Topic Name</span></span>|<span data-ttu-id="26faf-105">Описание</span><span class="sxs-lookup"><span data-stu-id="26faf-105">Description</span></span>|
|----------------|-----------------|
|[<span data-ttu-id="26faf-106">about_Objects</span><span class="sxs-lookup"><span data-stu-id="26faf-106">about_Objects</span></span>](/powershell/module/microsoft.powershell.core/about/about_objects)|<span data-ttu-id="26faf-107">Описание объектов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="26faf-107">Description of PowerShell objects.</span></span> <span data-ttu-id="26faf-108">Дополнительные сведения см. в разделе [о создании объекта](/powershell/module/microsoft.powershell.core/about/about_object_creation)</span><span class="sxs-lookup"><span data-stu-id="26faf-108">For more information, see [About Object Creation](/powershell/module/microsoft.powershell.core/about/about_object_creation)</span></span>|
|[<span data-ttu-id="26faf-109">Создание пространства выполнения</span><span class="sxs-lookup"><span data-stu-id="26faf-109">Creating Runspaces</span></span>](../hosting/creating-runspaces.md)|<span data-ttu-id="26faf-110">Рабочие среды, где команды обрабатываются.</span><span class="sxs-lookup"><span data-stu-id="26faf-110">The operating environments where commands are processed.</span></span> <span data-ttu-id="26faf-111">Дополнительные сведения см. в разделе [класс пространства выполнения](/dotnet/api/system.management.automation.runspaces.runspace).</span><span class="sxs-lookup"><span data-stu-id="26faf-111">For more information, see [Runspace Class](/dotnet/api/system.management.automation.runspaces.runspace).</span></span>|
|[<span data-ttu-id="26faf-112">Расширение объектов выходных данных</span><span class="sxs-lookup"><span data-stu-id="26faf-112">Extending Output Objects</span></span>](../cmdlet/extending-output-objects.md)|<span data-ttu-id="26faf-113">Как расширить объекты PowerShell.</span><span class="sxs-lookup"><span data-stu-id="26faf-113">How to extend PowerShell objects.</span></span> <span data-ttu-id="26faf-114">Дополнительные сведения см. в разделе [о Types.ps1xml](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml)</span><span class="sxs-lookup"><span data-stu-id="26faf-114">For more information, see [About Types.ps1xml](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml)</span></span>|
|[<span data-ttu-id="26faf-115">Регистрация командлетов</span><span class="sxs-lookup"><span data-stu-id="26faf-115">Registering Cmdlets</span></span>](../cmdlet/registering-cmdlets.md)|<span data-ttu-id="26faf-116">Как сделать доступными в PowerShell модули и оснастки.</span><span class="sxs-lookup"><span data-stu-id="26faf-116">How to make modules and snap-ins available in PowerShell.</span></span> <span data-ttu-id="26faf-117">Дополнительные сведения см. в разделе [модули и оснастки](../cmdlet/modules-and-snap-ins.md).</span><span class="sxs-lookup"><span data-stu-id="26faf-117">For more information, see [Modules and Snap-ins](../cmdlet/modules-and-snap-ins.md).</span></span>|
|[<span data-ttu-id="26faf-118">Запрос на подтверждение из командлетов</span><span class="sxs-lookup"><span data-stu-id="26faf-118">Requesting Confirmation from Cmdlets</span></span>](../cmdlet/requesting-confirmation-from-cmdlets.md)|<span data-ttu-id="26faf-119">Как командлеты и поставщики запросить отзывы у пользователя до выполнения действия.</span><span class="sxs-lookup"><span data-stu-id="26faf-119">How cmdlets and providers request feedback from the user before an action is taken.</span></span>|
|[<span data-ttu-id="26faf-120">Класс RuntimeDefinedParameter</span><span class="sxs-lookup"><span data-stu-id="26faf-120">RuntimeDefinedParameter Class</span></span>](/dotnet/api/system.management.automation.runtimedefinedparameter)|<span data-ttu-id="26faf-121">Объявления параметров среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="26faf-121">Runtime parameter declarations.</span></span>|
|[<span data-ttu-id="26faf-122">Пространство имен System.Management.Automation</span><span class="sxs-lookup"><span data-stu-id="26faf-122">System.Management.Automation Namespace</span></span>](/dotnet/api/System.Management.Automation)|<span data-ttu-id="26faf-123">Общие сведения о пространствах имен PowerShell API.</span><span class="sxs-lookup"><span data-stu-id="26faf-123">Overview of PowerShell API namespaces.</span></span>|
|[<span data-ttu-id="26faf-124">Общие сведения о поставщике PowerShell Windows</span><span class="sxs-lookup"><span data-stu-id="26faf-124">Windows PowerShell Provider Overview</span></span>](../provider/windows-powershell-provider-overview.md)|<span data-ttu-id="26faf-125">Хранит сведения о поставщиках PowerShell, которые используются для доступа к данным.</span><span class="sxs-lookup"><span data-stu-id="26faf-125">Overview about PowerShell providers that are used to access data stores.</span></span>|
|[<span data-ttu-id="26faf-126">Написание справки для командлетов PowerShell</span><span class="sxs-lookup"><span data-stu-id="26faf-126">Writing Help for PowerShell Cmdlets</span></span>](../help/writing-help-for-windows-powershell-cmdlets.md)|<span data-ttu-id="26faf-127">Как написать справки по командлетам PowerShell.</span><span class="sxs-lookup"><span data-stu-id="26faf-127">How to write PowerShell cmdlet Help.</span></span>|

## <a name="see-also"></a><span data-ttu-id="26faf-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="26faf-128">See also</span></span>

[<span data-ttu-id="26faf-129">Класс PowerShell</span><span class="sxs-lookup"><span data-stu-id="26faf-129">PowerShell Class</span></span>](/dotnet/api/system.management.automation.powershell)

[<span data-ttu-id="26faf-130">Справочник по API PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="26faf-130">PowerShell Core API Reference</span></span>](/dotnet/api/?view=pscore-6.2.0)

[<span data-ttu-id="26faf-131">Руководство программиста Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="26faf-131">Windows PowerShell Programmer's Guide</span></span>](windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="26faf-132">Написание справки для модулей Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="26faf-132">Writing Help for Windows PowerShell Modules</span></span>](../module/writing-help-for-windows-powershell-modules.md)

[<span data-ttu-id="26faf-133">Разработка поставщика Windows Powershell</span><span class="sxs-lookup"><span data-stu-id="26faf-133">Writing a Windows Powershell Provider</span></span>](../provider/writing-a-windows-powershell-provider.md)

[<span data-ttu-id="26faf-134">Справочник по API Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="26faf-134">Windows PowerShell API Reference</span></span>](/dotnet/api/?view=powershellsdk-1.1.0)

[<span data-ttu-id="26faf-135">Справочник по Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="26faf-135">Windows PowerShell Reference</span></span>](../windows-powershell-reference.md)