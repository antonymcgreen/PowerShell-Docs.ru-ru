---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент ExpressionBinding для элемента CustomItem для элемента CustomControl для элемента View (формат)
description: Элемент ExpressionBinding для элемента CustomItem для элемента CustomControl для элемента View (формат)
ms.openlocfilehash: 8f4bfef4f6c65c6dabc7a776dda1083bac11fdf7
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648198"
---
# <a name="expressionbinding-element-for-customitem-for-customcontrol-for-view-format"></a><span data-ttu-id="3d8e4-103">Элемент ExpressionBinding для элемента CustomItem для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="3d8e4-103">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>

<span data-ttu-id="3d8e4-104">Определяет данные, отображаемые элементом управления.</span><span class="sxs-lookup"><span data-stu-id="3d8e4-104">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="3d8e4-105">Этот элемент используется при определении пользовательского представления элемента управления.</span><span class="sxs-lookup"><span data-stu-id="3d8e4-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="3d8e4-106">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ошибка customcontrol для элемента Кустоментриес представления (Format) Кустоментри для Кустоментриес для ошибка customcontrol для представления (Format) кустомитем для кустоментри for ошибка customcontrol для представления (Format) ExpressionBinding для кустомитем для ошибка customcontrol для представления (формат).</span><span class="sxs-lookup"><span data-stu-id="3d8e4-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for CustomControl for View (Format) CustomItem Element for CustomEntry for CustomControl for View (Format) ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="3d8e4-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3d8e4-107">Syntax</span></span>

```xml
<ExpressionBinding>
  <CustomControl>...</CustomControl>
  <CustomControlName>NameofCommonCustomControl</CustomControlName>
  <EnumerateCollection/>
  <ItemSelectionCondition>...</ItemSelectionCondition>
  <PropertyName>Nameof.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate></ScriptBlock>
</ExpressionBinding>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3d8e4-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3d8e4-108">Attributes and Elements</span></span>

<span data-ttu-id="3d8e4-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ExpressionBinding` элемента.</span><span class="sxs-lookup"><span data-stu-id="3d8e4-109">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="3d8e4-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3d8e4-110">Attributes</span></span>

<span data-ttu-id="3d8e4-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="3d8e4-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="3d8e4-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3d8e4-112">Child Elements</span></span>

|<span data-ttu-id="3d8e4-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="3d8e4-113">Element</span></span>|<span data-ttu-id="3d8e4-114">Описание</span><span class="sxs-lookup"><span data-stu-id="3d8e4-114">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="3d8e4-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="3d8e4-115">Optional element.</span></span><br /><br /> <span data-ttu-id="3d8e4-116">Определяет элемент управления, используемый этим элементом управления.</span><span class="sxs-lookup"><span data-stu-id="3d8e4-116">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="3d8e4-117">Элемент CustomControlName для элемента ExpressionBinding для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="3d8e4-117">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="3d8e4-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="3d8e4-118">Optional element.</span></span><br /><br /> <span data-ttu-id="3d8e4-119">Указывает имя общего элемента управления или элемента управления представления.</span><span class="sxs-lookup"><span data-stu-id="3d8e4-119">Specifies the name of a common control or a view control.</span></span>|
|[<span data-ttu-id="3d8e4-120">Элемент EnumerateCollection для элемента ExpressionBinding для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="3d8e4-120">EnumerateCollection Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="3d8e4-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="3d8e4-121">Optional element.</span></span><br /><br /> <span data-ttu-id="3d8e4-122">Указывает, что отображаются элементы коллекций.</span><span class="sxs-lookup"><span data-stu-id="3d8e4-122">Specified that the elements of collections are displayed.</span></span>|
|[<span data-ttu-id="3d8e4-123">Элемент Итемселектионкондитион для ExpressionBinding для ошибка customcontrol для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="3d8e4-123">ItemSelectionCondition Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)|<span data-ttu-id="3d8e4-124">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="3d8e4-124">Optional element.</span></span><br /><br /> <span data-ttu-id="3d8e4-125">Определяет условие, которое должно существовать для использования этого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="3d8e4-125">Defines the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="3d8e4-126">Элемент PropertyName для элемента ExpressionBinding для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="3d8e4-126">PropertyName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="3d8e4-127">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="3d8e4-127">Optional element.</span></span><br /><br /> <span data-ttu-id="3d8e4-128">Указывает свойство .NET, значение которого отображается элементом управления.</span><span class="sxs-lookup"><span data-stu-id="3d8e4-128">Specifies the .NET property whose value is displayed by the control.</span></span>|
|[<span data-ttu-id="3d8e4-129">Элемент ScriptBlock для ExpressionBinding для Кустомкустомконтрол для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="3d8e4-129">ScriptBlock Element for ExpressionBinding for CustomCustomControl for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="3d8e4-130">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="3d8e4-130">Optional element.</span></span><br /><br /> <span data-ttu-id="3d8e4-131">Задает скрипт, значение которого отображается элементом управления.</span><span class="sxs-lookup"><span data-stu-id="3d8e4-131">Specifies the script whose value is displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="3d8e4-132">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3d8e4-132">Parent Elements</span></span>

|<span data-ttu-id="3d8e4-133">Элемент</span><span class="sxs-lookup"><span data-stu-id="3d8e4-133">Element</span></span>|<span data-ttu-id="3d8e4-134">Описание</span><span class="sxs-lookup"><span data-stu-id="3d8e4-134">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3d8e4-135">Элемент CustomItem для элемента CustomEntry для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="3d8e4-135">CustomItem Element for CustomEntry for CustomControl for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="3d8e4-136">Определяет, какие данные отображаются в представлении пользовательского элемента управления и как они отображаются.</span><span class="sxs-lookup"><span data-stu-id="3d8e4-136">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="3d8e4-137">Комментарии</span><span class="sxs-lookup"><span data-stu-id="3d8e4-137">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="3d8e4-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="3d8e4-138">See Also</span></span>

[<span data-ttu-id="3d8e4-139">Элемент CustomControlName для элемента ExpressionBinding для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="3d8e4-139">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="3d8e4-140">Элемент EnumerateCollection для элемента ExpressionBinding для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="3d8e4-140">EnumerateCollection Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="3d8e4-141">Элемент Итемселектионкондитион для ExpressionBinding для ошибка customcontrol для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="3d8e4-141">ItemSelectionCondition Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

[<span data-ttu-id="3d8e4-142">Элемент PropertyName для элемента ExpressionBinding для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="3d8e4-142">PropertyName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="3d8e4-143">Элемент ScriptBlock для элемента ExpressionBinding для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="3d8e4-143">ScriptBlock Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="3d8e4-144">Элемент CustomItem для элемента CustomEntry для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="3d8e4-144">CustomItem Element for CustomEntry for CustomControl for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="3d8e4-145">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="3d8e4-145">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
