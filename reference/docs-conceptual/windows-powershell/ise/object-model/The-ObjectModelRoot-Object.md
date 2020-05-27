---
ms.date: 08/25/2017
keywords: powershell,командлет
title: Объект ObjectModelRoot
ms.openlocfilehash: cd94e69de2e62f7ce9fac413e15458ae9986540e
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2020
ms.locfileid: "83809570"
---
# <a name="the-objectmodelroot-object"></a><span data-ttu-id="f22fd-103">Объект ObjectModelRoot</span><span class="sxs-lookup"><span data-stu-id="f22fd-103">The ObjectModelRoot Object</span></span>

<span data-ttu-id="f22fd-104">Объект `$psISE`, который является основным корневым объектом в интегрированной среде сценариев Windows PowerShell® (ISE), — это экземпляр класса Microsoft.PowerShell.Host.ISE.ObjectModelRoot.</span><span class="sxs-lookup"><span data-stu-id="f22fd-104">The `$psISE` object, which is the principal root object in Windows PowerShell® Integrated Scripting Environment (ISE) is an instance of the Microsoft.PowerShell.Host.ISE.ObjectModelRoot class.</span></span> <span data-ttu-id="f22fd-105">В этом разделе описаны свойства объекта **ObjectModelRoot**.</span><span class="sxs-lookup"><span data-stu-id="f22fd-105">This topic describes the properties of the **ObjectModelRoot** object.</span></span>

## <a name="properties"></a><span data-ttu-id="f22fd-106">Свойства</span><span class="sxs-lookup"><span data-stu-id="f22fd-106">Properties</span></span>

### <a name="currentfile"></a><span data-ttu-id="f22fd-107">CurrentFile</span><span class="sxs-lookup"><span data-stu-id="f22fd-107">CurrentFile</span></span>

> <span data-ttu-id="f22fd-108">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="f22fd-108">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="f22fd-109">Свойство только для чтения, которое получает файл, связанный с этим объектом узла, находящимся в данный момент в фокусе.</span><span class="sxs-lookup"><span data-stu-id="f22fd-109">The read-only property that gets the file, which is associated with this host object that currently has the focus.</span></span>

### <a name="currentpowershelltab"></a><span data-ttu-id="f22fd-110">CurrentPowerShellTab</span><span class="sxs-lookup"><span data-stu-id="f22fd-110">CurrentPowerShellTab</span></span>

> <span data-ttu-id="f22fd-111">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="f22fd-111">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="f22fd-112">Свойство только для чтения, которое получает вкладку PowerShell, находящуюся в фокусе.</span><span class="sxs-lookup"><span data-stu-id="f22fd-112">The read-only property that gets the PowerShell tab that has the focus.</span></span>

### <a name="currentvisiblehorizontaltool"></a><span data-ttu-id="f22fd-113">CurrentVisibleHorizontalTool</span><span class="sxs-lookup"><span data-stu-id="f22fd-113">CurrentVisibleHorizontalTool</span></span>

> <span data-ttu-id="f22fd-114">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="f22fd-114">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="f22fd-115">Свойство только для чтения, которое получает видимую в данный момент надстройку интегрированной среды сценариев Windows PowerShell, которая находится в горизонтальной области инструментов в нижней части редактора.</span><span class="sxs-lookup"><span data-stu-id="f22fd-115">The read-only property that gets the currently visible Windows PowerShell ISE add-on tool that is located in the horizontal tool pane at the bottom of the editor.</span></span>

### <a name="currentvisibleverticaltool"></a><span data-ttu-id="f22fd-116">CurrentVisibleVerticalTool</span><span class="sxs-lookup"><span data-stu-id="f22fd-116">CurrentVisibleVerticalTool</span></span>

> <span data-ttu-id="f22fd-117">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="f22fd-117">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="f22fd-118">Свойство только для чтения, которое получает видимую в данный момент надстройку интегрированной среды сценариев Windows PowerShell, которая находится в вертикальной области инструментов в правой части редактора.</span><span class="sxs-lookup"><span data-stu-id="f22fd-118">The read-only property that gets the currently visible Windows PowerShell ISE add-on tool that is located in the vertical tool pane on the right side of the editor.</span></span>

### <a name="options"></a><span data-ttu-id="f22fd-119">Параметры</span><span class="sxs-lookup"><span data-stu-id="f22fd-119">Options</span></span>

> <span data-ttu-id="f22fd-120">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="f22fd-120">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="f22fd-121">Свойство только для чтения, которое получает различные параметры, изменяющие настройки в интегрированной среде сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f22fd-121">The read-only property that gets the various options that can change settings in Windows PowerShell ISE.</span></span>

### <a name="powershelltabs"></a><span data-ttu-id="f22fd-122">PowerShellTabs</span><span class="sxs-lookup"><span data-stu-id="f22fd-122">PowerShellTabs</span></span>

> <span data-ttu-id="f22fd-123">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="f22fd-123">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="f22fd-124">Свойство только для чтения, которое получает коллекцию вкладок PowerShell, открытых в интегрированной среде сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f22fd-124">The read-only property that gets the collection of the PowerShell tabs, which are open in Windows PowerShell ISE.</span></span> <span data-ttu-id="f22fd-125">По умолчанию этот объект содержит одну вкладку PowerShell. Тем не менее можно добавить в этот объект больше вкладок PowerShell с помощью сценариев или меню в интегрированной среде сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f22fd-125">By default, this object contains one PowerShell tab. However, you can add more PowerShell tabs to this object by using scripts or by using the menus in Windows PowerShell ISE.</span></span>

## <a name="see-also"></a><span data-ttu-id="f22fd-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="f22fd-126">See Also</span></span>

- [<span data-ttu-id="f22fd-127">Назначение объектной модели скриптов интегрированной среды скриптов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f22fd-127">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="f22fd-128">Иерархия объектной модели интегрированной среды скриптов</span><span class="sxs-lookup"><span data-stu-id="f22fd-128">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
