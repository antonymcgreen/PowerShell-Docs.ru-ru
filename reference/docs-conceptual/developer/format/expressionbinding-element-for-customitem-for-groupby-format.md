---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент ExpressionBinding для элемента CustomItem для элемента GroupBy (формат)
description: Элемент ExpressionBinding для элемента CustomItem для элемента GroupBy (формат)
ms.openlocfilehash: 742d9f081a674dc3ee4c84d600933aaf57b2aa6b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655298"
---
# <a name="expressionbinding-element-for-customitem-for-groupby-format"></a><span data-ttu-id="113c5-103">Элемент ExpressionBinding для элемента CustomItem для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="113c5-103">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>

<span data-ttu-id="113c5-104">Определяет данные, отображаемые элементом управления.</span><span class="sxs-lookup"><span data-stu-id="113c5-104">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="113c5-105">Этот элемент используется при определении того, как отображается новая группа объектов.</span><span class="sxs-lookup"><span data-stu-id="113c5-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="113c5-106">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент GroupBy для элемента "View" (Format) ошибка customcontrol для элемента GroupBy (Format) Кустоментриес для ошибка customcontrol for GroupBy (формат) кустоментри для ошибка customcontrol for GroupBy (формат) кустомитем для кустоментри for GroupBy (Format) ExpressionBinding для кустомитем for GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="113c5-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="113c5-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="113c5-107">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="113c5-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="113c5-108">Attributes and Elements</span></span>

<span data-ttu-id="113c5-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ExpressionBinding` элемента.</span><span class="sxs-lookup"><span data-stu-id="113c5-109">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="113c5-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="113c5-110">Attributes</span></span>

<span data-ttu-id="113c5-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="113c5-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="113c5-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="113c5-112">Child Elements</span></span>

|<span data-ttu-id="113c5-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="113c5-113">Element</span></span>|<span data-ttu-id="113c5-114">Описание</span><span class="sxs-lookup"><span data-stu-id="113c5-114">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="113c5-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="113c5-115">Optional element.</span></span><br /><br /> <span data-ttu-id="113c5-116">Определяет элемент управления, используемый этим элементом управления.</span><span class="sxs-lookup"><span data-stu-id="113c5-116">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="113c5-117">Элемент CustomControlName для элемента ExpressionBinding для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="113c5-117">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="113c5-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="113c5-118">Optional element.</span></span><br /><br /> <span data-ttu-id="113c5-119">Указывает имя общего элемента управления или элемента управления представления.</span><span class="sxs-lookup"><span data-stu-id="113c5-119">Specifies the name of a common control or a view control.</span></span>|
|<span data-ttu-id="113c5-120">[Элемент енумератеколлектион для ExpressionBinding для GroupBy (Format)](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md) Элемент Енумератеколлектион для ExpressionBinding для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="113c5-120">[EnumerateCollection Element for ExpressionBinding for GroupBy (Format)](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md)EnumerateCollection Element for ExpressionBinding for GroupBy (Format)</span></span>|<span data-ttu-id="113c5-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="113c5-121">Optional element.</span></span><br /><br /> <span data-ttu-id="113c5-122">Указывает, что отображаются элементы коллекций.</span><span class="sxs-lookup"><span data-stu-id="113c5-122">Specified that the elements of collections are displayed.</span></span>|
|[<span data-ttu-id="113c5-123">Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="113c5-123">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="113c5-124">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="113c5-124">Optional element.</span></span><br /><br /> <span data-ttu-id="113c5-125">Определяет условие, которое должно существовать для использования этого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="113c5-125">Defines the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="113c5-126">Элемент PropertyName для элемента ExpressionBinding для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="113c5-126">PropertyName Element for ExpressionBinding for GroupBy (Format)</span></span>](./propertyname-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="113c5-127">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="113c5-127">Optional element.</span></span><br /><br /> <span data-ttu-id="113c5-128">Указывает свойство .NET, значение которого отображается элементом управления.</span><span class="sxs-lookup"><span data-stu-id="113c5-128">Specifies the .NET property whose value is displayed by the control.</span></span>|
|[<span data-ttu-id="113c5-129">Элемент ScriptBlock для элемента ExpressionBinding для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="113c5-129">ScriptBlock Element for ExpressionBinding for GroupBy (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="113c5-130">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="113c5-130">Optional element.</span></span><br /><br /> <span data-ttu-id="113c5-131">Задает скрипт, значение которого отображается элементом управления.</span><span class="sxs-lookup"><span data-stu-id="113c5-131">Specifies the script whose value is displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="113c5-132">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="113c5-132">Parent Elements</span></span>

|<span data-ttu-id="113c5-133">Элемент</span><span class="sxs-lookup"><span data-stu-id="113c5-133">Element</span></span>|<span data-ttu-id="113c5-134">Описание</span><span class="sxs-lookup"><span data-stu-id="113c5-134">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="113c5-135">Элемент CustomItem для элемента CustomEntry для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="113c5-135">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="113c5-136">Определяет, какие данные отображаются в представлении пользовательского элемента управления и как они отображаются.</span><span class="sxs-lookup"><span data-stu-id="113c5-136">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|

## <a name="see-also"></a><span data-ttu-id="113c5-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="113c5-137">See Also</span></span>

[<span data-ttu-id="113c5-138">Элемент CustomControlName для элемента ExpressionBinding для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="113c5-138">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="113c5-139">Элемент EnumerateCollection для элемента ExpressionBinding для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="113c5-139">EnumerateCollection Element for ExpressionBinding for GroupBy (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="113c5-140">Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="113c5-140">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="113c5-141">Элемент PropertyName для элемента ExpressionBinding для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="113c5-141">PropertyName Element for ExpressionBinding for GroupBy (Format)</span></span>](./propertyname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="113c5-142">Элемент ScriptBlock для элемента ExpressionBinding для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="113c5-142">ScriptBlock Element for ExpressionBinding for GroupBy (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="113c5-143">Элемент CustomItem для элемента CustomEntry для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="113c5-143">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="113c5-144">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="113c5-144">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
