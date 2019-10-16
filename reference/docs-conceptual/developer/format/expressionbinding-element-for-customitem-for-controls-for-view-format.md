---
title: Элемент ExpressionBinding для Кустомитем элементов управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2b9da6c5-548b-480f-86ae-6de6fecabaca
caps.latest.revision: 8
ms.openlocfilehash: 06089730008839f18c471711a4b4411722f99c38
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363783"
---
# <a name="expressionbinding-element-for-customitem-for-controls-for-view-format"></a><span data-ttu-id="2e78f-102">Элемент ExpressionBinding для элемента CustomItem для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="2e78f-102">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>

<span data-ttu-id="2e78f-103">Определяет данные, отображаемые элементом управления.</span><span class="sxs-lookup"><span data-stu-id="2e78f-103">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="2e78f-104">Этот элемент используется при определении элементов управления, которые могут использоваться представлением.</span><span class="sxs-lookup"><span data-stu-id="2e78f-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="2e78f-105">Элемент Configuration (Format) Виевдефинитионс элемент (формат) элемент представления (Format) управляет управляющий элемент (Format) элемент управления для элементов управления представления (Format) ошибка customcontrol для элементов управления элемента Кустоментриес представления (Format) для Ошибка customcontrol для элемента Кустоментри представления (Format) для Кустоментриес для элементов управления для представления (Format) Кустомитем элемента для Кустоментри для элементов управления для представления (Format) ExpressionBinding для Кустомитем элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="2e78f-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2e78f-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2e78f-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="2e78f-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2e78f-107">Attributes and Elements</span></span>

<span data-ttu-id="2e78f-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `ExpressionBinding`.</span><span class="sxs-lookup"><span data-stu-id="2e78f-108">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="2e78f-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2e78f-109">Attributes</span></span>

<span data-ttu-id="2e78f-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="2e78f-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2e78f-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2e78f-111">Child Elements</span></span>

|<span data-ttu-id="2e78f-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="2e78f-112">Element</span></span>|<span data-ttu-id="2e78f-113">Описание</span><span class="sxs-lookup"><span data-stu-id="2e78f-113">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="2e78f-114">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="2e78f-114">Optional element.</span></span><br /><br /> <span data-ttu-id="2e78f-115">Определяет элемент управления, используемый этим элементом управления.</span><span class="sxs-lookup"><span data-stu-id="2e78f-115">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="2e78f-116">Элемент Кустомконтролнаме для ExpressionBinding элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="2e78f-116">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="2e78f-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="2e78f-117">Optional element.</span></span><br /><br /> <span data-ttu-id="2e78f-118">Указывает имя общего элемента управления или элемента управления представления.</span><span class="sxs-lookup"><span data-stu-id="2e78f-118">Specifies the name of a common control or a view control.</span></span>|
|[<span data-ttu-id="2e78f-119">Элемент Енумератеколлектион для ExpressionBinding элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="2e78f-119">EnumerateCollection Element for ExpressionBinding for Controls for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="2e78f-120">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="2e78f-120">Optional element.</span></span><br /><br /> <span data-ttu-id="2e78f-121">Указывает, что элементы коллекций отображаются.</span><span class="sxs-lookup"><span data-stu-id="2e78f-121">Specifies that the elements of collections are displayed.</span></span>|
|[<span data-ttu-id="2e78f-122">Элемент Итемселектионкондитион элемента ExpressionBinding для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="2e78f-122">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="2e78f-123">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="2e78f-123">Optional element.</span></span><br /><br /> <span data-ttu-id="2e78f-124">Определяет условие, которое должно существовать для использования этого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="2e78f-124">Defines the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="2e78f-125">Элемент PropertyName для ExpressionBinding элементов управления для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="2e78f-125">PropertyName Element for ExpressionBinding for Controls for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="2e78f-126">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="2e78f-126">Optional element.</span></span><br /><br /> <span data-ttu-id="2e78f-127">Указывает свойство .NET, значение которого отображается элементом управления.</span><span class="sxs-lookup"><span data-stu-id="2e78f-127">Specifies the .NET property whose value is displayed by the control.</span></span>|
|[<span data-ttu-id="2e78f-128">Элемент ScriptBlock для ExpressionBinding элементов управления для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="2e78f-128">ScriptBlock Element for ExpressionBinding for Controls for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="2e78f-129">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="2e78f-129">Optional element.</span></span><br /><br /> <span data-ttu-id="2e78f-130">Задает скрипт, значение которого отображается элементом управления.</span><span class="sxs-lookup"><span data-stu-id="2e78f-130">Specifies the script whose value is displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="2e78f-131">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2e78f-131">Parent Elements</span></span>

|<span data-ttu-id="2e78f-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="2e78f-132">Element</span></span>|<span data-ttu-id="2e78f-133">Описание</span><span class="sxs-lookup"><span data-stu-id="2e78f-133">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2e78f-134">Элемент Кустомитем для Кустоментри элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="2e78f-134">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="2e78f-135">Определяет, какие данные отображаются элементом управления и как они отображаются.</span><span class="sxs-lookup"><span data-stu-id="2e78f-135">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="2e78f-136">Замечания</span><span class="sxs-lookup"><span data-stu-id="2e78f-136">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="2e78f-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="2e78f-137">See Also</span></span>

[<span data-ttu-id="2e78f-138">Элемент Кустомитем для Кустоментри элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="2e78f-138">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)

[<span data-ttu-id="2e78f-139">Элемент Кустомконтролнаме для ExpressionBinding элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="2e78f-139">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="2e78f-140">Элемент Енумератеколлектион для ExpressionBinding элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="2e78f-140">EnumerateCollection Element for ExpressionBinding for Controls for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="2e78f-141">Элемент Итемселектионкондитион элемента ExpressionBinding для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="2e78f-141">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="2e78f-142">Элемент PropertyName для ExpressionBinding элементов управления для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="2e78f-142">PropertyName Element for ExpressionBinding for Controls for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="2e78f-143">Элемент ScriptBlock для ExpressionBinding элементов управления для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="2e78f-143">ScriptBlock Element for ExpressionBinding for Controls for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="2e78f-144">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="2e78f-144">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
