---
title: Элемент ExpressionBinding для Кустомитем для GroupBy (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5eae5088-7605-4ef2-a703-faf3e5a5fc94
caps.latest.revision: 8
ms.openlocfilehash: 4714bfd1530585aa80aabc010b86d25bf0c7f9c4
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368633"
---
# <a name="expressionbinding-element-for-customitem-for-groupby-format"></a><span data-ttu-id="59220-102">Элемент ExpressionBinding для элемента CustomItem для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="59220-102">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>

<span data-ttu-id="59220-103">Определяет данные, отображаемые элементом управления.</span><span class="sxs-lookup"><span data-stu-id="59220-103">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="59220-104">Этот элемент используется при определении того, как отображается новая группа объектов.</span><span class="sxs-lookup"><span data-stu-id="59220-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="59220-105">Элемент конфигурации (Format) Виевдефинитионс элемент (Format) элемент представления (формат) элемент GroupBy для элемента Ошибка customcontrol представления (Format) для элемента Кустоментриес (Format) для ошибка customcontrol для элемента GroupBy (Format) Кустоментри для Ошибка customcontrol для элемента Кустомитем GroupBy для Кустоментри для GroupBy (Format) ExpressionBinding элемента для Кустомитем для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="59220-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="59220-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="59220-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="59220-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="59220-107">Attributes and Elements</span></span>

<span data-ttu-id="59220-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `ExpressionBinding`.</span><span class="sxs-lookup"><span data-stu-id="59220-108">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="59220-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="59220-109">Attributes</span></span>

<span data-ttu-id="59220-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="59220-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="59220-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="59220-111">Child Elements</span></span>

|<span data-ttu-id="59220-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="59220-112">Element</span></span>|<span data-ttu-id="59220-113">Описание</span><span class="sxs-lookup"><span data-stu-id="59220-113">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="59220-114">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="59220-114">Optional element.</span></span><br /><br /> <span data-ttu-id="59220-115">Определяет элемент управления, используемый этим элементом управления.</span><span class="sxs-lookup"><span data-stu-id="59220-115">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="59220-116">Элемент Кустомконтролнаме для ExpressionBinding для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="59220-116">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="59220-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="59220-117">Optional element.</span></span><br /><br /> <span data-ttu-id="59220-118">Указывает имя общего элемента управления или элемента управления представления.</span><span class="sxs-lookup"><span data-stu-id="59220-118">Specifies the name of a common control or a view control.</span></span>|
|<span data-ttu-id="59220-119">[Элемент енумератеколлектион для ExpressionBinding для GroupBy (Format)](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md) Элемент Енумератеколлектион для ExpressionBinding для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="59220-119">[EnumerateCollection Element for ExpressionBinding for GroupBy (Format)](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md)EnumerateCollection Element for ExpressionBinding for GroupBy (Format)</span></span>|<span data-ttu-id="59220-120">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="59220-120">Optional element.</span></span><br /><br /> <span data-ttu-id="59220-121">Указывает, что отображаются элементы коллекций.</span><span class="sxs-lookup"><span data-stu-id="59220-121">Specified that the elements of collections are displayed.</span></span>|
|[<span data-ttu-id="59220-122">Элемент Итемселектионкондитион для ExpressionBinding для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="59220-122">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="59220-123">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="59220-123">Optional element.</span></span><br /><br /> <span data-ttu-id="59220-124">Определяет условие, которое должно существовать для использования этого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="59220-124">Defines the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="59220-125">Элемент PropertyName для ExpressionBinding для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="59220-125">PropertyName Element for ExpressionBinding for GroupBy (Format)</span></span>](./propertyname-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="59220-126">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="59220-126">Optional element.</span></span><br /><br /> <span data-ttu-id="59220-127">Указывает свойство .NET, значение которого отображается элементом управления.</span><span class="sxs-lookup"><span data-stu-id="59220-127">Specifies the .NET property whose value is displayed by the control.</span></span>|
|[<span data-ttu-id="59220-128">Элемент ScriptBlock для ExpressionBinding для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="59220-128">ScriptBlock Element for ExpressionBinding for GroupBy (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="59220-129">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="59220-129">Optional element.</span></span><br /><br /> <span data-ttu-id="59220-130">Задает скрипт, значение которого отображается элементом управления.</span><span class="sxs-lookup"><span data-stu-id="59220-130">Specifies the script whose value is displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="59220-131">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="59220-131">Parent Elements</span></span>

|<span data-ttu-id="59220-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="59220-132">Element</span></span>|<span data-ttu-id="59220-133">Описание</span><span class="sxs-lookup"><span data-stu-id="59220-133">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="59220-134">Элемент Кустомитем для Кустоментри для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="59220-134">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="59220-135">Определяет, какие данные отображаются в представлении пользовательского элемента управления и как они отображаются.</span><span class="sxs-lookup"><span data-stu-id="59220-135">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|

## <a name="see-also"></a><span data-ttu-id="59220-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="59220-136">See Also</span></span>

[<span data-ttu-id="59220-137">Элемент Кустомконтролнаме для ExpressionBinding для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="59220-137">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="59220-138">Элемент Енумератеколлектион для ExpressionBinding для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="59220-138">EnumerateCollection Element for ExpressionBinding for GroupBy (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="59220-139">Элемент Итемселектионкондитион для ExpressionBinding для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="59220-139">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="59220-140">Элемент PropertyName для ExpressionBinding для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="59220-140">PropertyName Element for ExpressionBinding for GroupBy (Format)</span></span>](./propertyname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="59220-141">Элемент ScriptBlock для ExpressionBinding для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="59220-141">ScriptBlock Element for ExpressionBinding for GroupBy (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="59220-142">Элемент Кустомитем для Кустоментри для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="59220-142">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="59220-143">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="59220-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
