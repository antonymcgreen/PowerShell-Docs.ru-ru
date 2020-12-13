---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент ExpressionBinding для элемента CustomItem для элемента Controls для элемента View (формат)
description: Элемент ExpressionBinding для элемента CustomItem для элемента Controls для элемента View (формат)
ms.openlocfilehash: da87bb26d21dcb051871e67997cc3fba7ce73c74
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649894"
---
# <a name="expressionbinding-element-for-customitem-for-controls-for-view-format"></a><span data-ttu-id="ddee9-103">Элемент ExpressionBinding для элемента CustomItem для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="ddee9-103">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>

<span data-ttu-id="ddee9-104">Определяет данные, отображаемые элементом управления.</span><span class="sxs-lookup"><span data-stu-id="ddee9-104">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="ddee9-105">Этот элемент используется при определении элементов управления, которые могут использоваться представлением.</span><span class="sxs-lookup"><span data-stu-id="ddee9-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="ddee9-106">Элемент Configuration (Format) Виевдефинитионс элемент (формат) элемент представления (Format) управляет управляющий элемент (Format) элемент управления для элементов управления представления (Format) ошибка customcontrol для элементов управления элемента Кустоментриес View (формат). для элемента Ошибка customcontrol для представления (Format) Кустоментри для Кустоментриес элементов управления для элемента Controls представления (Format) Кустомитем для Кустоментри для элементов управления представления (Format) ExpressionBinding для Кустомитем элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="ddee9-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ddee9-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ddee9-107">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="ddee9-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ddee9-108">Attributes and Elements</span></span>

<span data-ttu-id="ddee9-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ExpressionBinding` элемента.</span><span class="sxs-lookup"><span data-stu-id="ddee9-109">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ddee9-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ddee9-110">Attributes</span></span>

<span data-ttu-id="ddee9-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ddee9-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ddee9-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ddee9-112">Child Elements</span></span>

|<span data-ttu-id="ddee9-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="ddee9-113">Element</span></span>|<span data-ttu-id="ddee9-114">Описание</span><span class="sxs-lookup"><span data-stu-id="ddee9-114">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="ddee9-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="ddee9-115">Optional element.</span></span><br /><br /> <span data-ttu-id="ddee9-116">Определяет элемент управления, используемый этим элементом управления.</span><span class="sxs-lookup"><span data-stu-id="ddee9-116">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="ddee9-117">Элемент CustomControlName для элемента ExpressionBinding для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="ddee9-117">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="ddee9-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="ddee9-118">Optional element.</span></span><br /><br /> <span data-ttu-id="ddee9-119">Указывает имя общего элемента управления или элемента управления представления.</span><span class="sxs-lookup"><span data-stu-id="ddee9-119">Specifies the name of a common control or a view control.</span></span>|
|[<span data-ttu-id="ddee9-120">Элемент EnumerateCollection для элемента ExpressionBinding для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="ddee9-120">EnumerateCollection Element for ExpressionBinding for Controls for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="ddee9-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="ddee9-121">Optional element.</span></span><br /><br /> <span data-ttu-id="ddee9-122">Указывает, что элементы коллекций отображаются.</span><span class="sxs-lookup"><span data-stu-id="ddee9-122">Specifies that the elements of collections are displayed.</span></span>|
|[<span data-ttu-id="ddee9-123">Элемент Итемселектионкондитион элемента ExpressionBinding для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="ddee9-123">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="ddee9-124">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="ddee9-124">Optional element.</span></span><br /><br /> <span data-ttu-id="ddee9-125">Определяет условие, которое должно существовать для использования этого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ddee9-125">Defines the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="ddee9-126">Элемент PropertyName для элемента ExpressionBinding для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="ddee9-126">PropertyName Element for ExpressionBinding for Controls for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="ddee9-127">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="ddee9-127">Optional element.</span></span><br /><br /> <span data-ttu-id="ddee9-128">Указывает свойство .NET, значение которого отображается элементом управления.</span><span class="sxs-lookup"><span data-stu-id="ddee9-128">Specifies the .NET property whose value is displayed by the control.</span></span>|
|[<span data-ttu-id="ddee9-129">Элемент ScriptBlock для элемента ExpressionBinding для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="ddee9-129">ScriptBlock Element for ExpressionBinding for Controls for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="ddee9-130">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="ddee9-130">Optional element.</span></span><br /><br /> <span data-ttu-id="ddee9-131">Задает скрипт, значение которого отображается элементом управления.</span><span class="sxs-lookup"><span data-stu-id="ddee9-131">Specifies the script whose value is displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="ddee9-132">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ddee9-132">Parent Elements</span></span>

|<span data-ttu-id="ddee9-133">Элемент</span><span class="sxs-lookup"><span data-stu-id="ddee9-133">Element</span></span>|<span data-ttu-id="ddee9-134">Описание</span><span class="sxs-lookup"><span data-stu-id="ddee9-134">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ddee9-135">Элемент CustomItem для элемента CustomEntry для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="ddee9-135">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="ddee9-136">Определяет, какие данные отображаются элементом управления и как они отображаются.</span><span class="sxs-lookup"><span data-stu-id="ddee9-136">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ddee9-137">Комментарии</span><span class="sxs-lookup"><span data-stu-id="ddee9-137">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="ddee9-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="ddee9-138">See Also</span></span>

[<span data-ttu-id="ddee9-139">Элемент CustomItem для элемента CustomEntry для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="ddee9-139">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)

[<span data-ttu-id="ddee9-140">Элемент CustomControlName для элемента ExpressionBinding для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="ddee9-140">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="ddee9-141">Элемент EnumerateCollection для элемента ExpressionBinding для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="ddee9-141">EnumerateCollection Element for ExpressionBinding for Controls for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="ddee9-142">Элемент Итемселектионкондитион элемента ExpressionBinding для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="ddee9-142">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="ddee9-143">Элемент PropertyName для элемента ExpressionBinding для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="ddee9-143">PropertyName Element for ExpressionBinding for Controls for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="ddee9-144">Элемент ScriptBlock для элемента ExpressionBinding для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="ddee9-144">ScriptBlock Element for ExpressionBinding for Controls for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="ddee9-145">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="ddee9-145">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
