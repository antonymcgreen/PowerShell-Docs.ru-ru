---
ms.date: 08/25/2017
title: Объект ObjectModelRoot
description: Объект $psISE, который является основным корневым объектом в PowerShell ISE, представляет собой экземпляр класса Microsoft.PowerShell.Host.ISE.ObjectModelRoot. В этом разделе описаны свойства объекта ObjectModelRoot.
ms.openlocfilehash: c8ae703c2663256ca037090fd3b1eb239cfc431a
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92660938"
---
# <a name="the-objectmodelroot-object"></a><span data-ttu-id="ba4da-104">Объект ObjectModelRoot</span><span class="sxs-lookup"><span data-stu-id="ba4da-104">The ObjectModelRoot Object</span></span>

<span data-ttu-id="ba4da-105">Объект `$psISE`, который является основным корневым объектом в интегрированной среде сценариев Windows PowerShell&reg; (ISE), представляет собой экземпляр класса Microsoft.PowerShell.Host.ISE.ObjectModelRoot.</span><span class="sxs-lookup"><span data-stu-id="ba4da-105">The `$psISE` object, which is the principal root object in Windows PowerShell&reg; Integrated Scripting Environment (ISE) is an instance of the Microsoft.PowerShell.Host.ISE.ObjectModelRoot class.</span></span> <span data-ttu-id="ba4da-106">В этом разделе описаны свойства объекта **ObjectModelRoot**.</span><span class="sxs-lookup"><span data-stu-id="ba4da-106">This topic describes the properties of the **ObjectModelRoot** object.</span></span>

## <a name="properties"></a><span data-ttu-id="ba4da-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="ba4da-107">Properties</span></span>

### <a name="currentfile"></a><span data-ttu-id="ba4da-108">CurrentFile</span><span class="sxs-lookup"><span data-stu-id="ba4da-108">CurrentFile</span></span>

> <span data-ttu-id="ba4da-109">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="ba4da-109">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="ba4da-110">Свойство только для чтения, которое получает файл, связанный с этим объектом узла, находящимся в данный момент в фокусе.</span><span class="sxs-lookup"><span data-stu-id="ba4da-110">The read-only property that gets the file, which is associated with this host object that currently has the focus.</span></span>

### <a name="currentpowershelltab"></a><span data-ttu-id="ba4da-111">CurrentPowerShellTab</span><span class="sxs-lookup"><span data-stu-id="ba4da-111">CurrentPowerShellTab</span></span>

> <span data-ttu-id="ba4da-112">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="ba4da-112">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="ba4da-113">Свойство только для чтения, которое получает вкладку PowerShell, находящуюся в фокусе.</span><span class="sxs-lookup"><span data-stu-id="ba4da-113">The read-only property that gets the PowerShell tab that has the focus.</span></span>

### <a name="currentvisiblehorizontaltool"></a><span data-ttu-id="ba4da-114">CurrentVisibleHorizontalTool</span><span class="sxs-lookup"><span data-stu-id="ba4da-114">CurrentVisibleHorizontalTool</span></span>

> <span data-ttu-id="ba4da-115">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="ba4da-115">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="ba4da-116">Свойство только для чтения, которое получает видимую в данный момент надстройку интегрированной среды сценариев Windows PowerShell, которая находится в горизонтальной области инструментов в нижней части редактора.</span><span class="sxs-lookup"><span data-stu-id="ba4da-116">The read-only property that gets the currently visible Windows PowerShell ISE add-on tool that is located in the horizontal tool pane at the bottom of the editor.</span></span>

### <a name="currentvisibleverticaltool"></a><span data-ttu-id="ba4da-117">CurrentVisibleVerticalTool</span><span class="sxs-lookup"><span data-stu-id="ba4da-117">CurrentVisibleVerticalTool</span></span>

> <span data-ttu-id="ba4da-118">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="ba4da-118">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="ba4da-119">Свойство только для чтения, которое получает видимую в данный момент надстройку интегрированной среды сценариев Windows PowerShell, которая находится в вертикальной области инструментов в правой части редактора.</span><span class="sxs-lookup"><span data-stu-id="ba4da-119">The read-only property that gets the currently visible Windows PowerShell ISE add-on tool that is located in the vertical tool pane on the right side of the editor.</span></span>

### <a name="options"></a><span data-ttu-id="ba4da-120">Варианты</span><span class="sxs-lookup"><span data-stu-id="ba4da-120">Options</span></span>

> <span data-ttu-id="ba4da-121">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="ba4da-121">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="ba4da-122">Свойство только для чтения, которое получает различные параметры, изменяющие настройки в интегрированной среде сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ba4da-122">The read-only property that gets the various options that can change settings in Windows PowerShell ISE.</span></span>

### <a name="powershelltabs"></a><span data-ttu-id="ba4da-123">PowerShellTabs</span><span class="sxs-lookup"><span data-stu-id="ba4da-123">PowerShellTabs</span></span>

> <span data-ttu-id="ba4da-124">Поддерживается в интегрированной среде сценариев Windows PowerShell 2.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="ba4da-124">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="ba4da-125">Свойство только для чтения, которое получает коллекцию вкладок PowerShell, открытых в интегрированной среде сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ba4da-125">The read-only property that gets the collection of the PowerShell tabs, which are open in Windows PowerShell ISE.</span></span> <span data-ttu-id="ba4da-126">По умолчанию этот объект содержит одну вкладку PowerShell. Тем не менее можно добавить в этот объект больше вкладок PowerShell с помощью сценариев или меню в интегрированной среде сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ba4da-126">By default, this object contains one PowerShell tab. However, you can add more PowerShell tabs to this object by using scripts or by using the menus in Windows PowerShell ISE.</span></span>

## <a name="see-also"></a><span data-ttu-id="ba4da-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="ba4da-127">See Also</span></span>

- [<span data-ttu-id="ba4da-128">Назначение объектной модели сценариев интегрированной среды сценариев Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ba4da-128">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="ba4da-129">Иерархия объектной модели интегрированной среды скриптов</span><span class="sxs-lookup"><span data-stu-id="ba4da-129">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
