---
title: Элемент ExpressionBinding для CustomItem для GroupBy (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5eae5088-7605-4ef2-a703-faf3e5a5fc94
caps.latest.revision: 8
ms.openlocfilehash: 4714bfd1530585aa80aabc010b86d25bf0c7f9c4
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854930"
---
# <a name="expressionbinding-element-for-customitem-for-groupby-format"></a><span data-ttu-id="46e72-102">Элемент ExpressionBinding для элемента CustomItem для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="46e72-102">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>

<span data-ttu-id="46e72-103">Определяет данные, отображаемые элементом управления.</span><span class="sxs-lookup"><span data-stu-id="46e72-103">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="46e72-104">Этот элемент используется при определении того, как отображается группу объектов.</span><span class="sxs-lookup"><span data-stu-id="46e72-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="46e72-105">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) GroupBy элемента конфигурации для элемента представления (формат) пользовательский элемент управления для элемента CustomEntries GroupBy (формат) пользовательский элемент управления для элемента CustomEntry GroupBy (формат) Пользовательский элемент управления для элемента CustomItem GroupBy (формат) для CustomEntry элемента ExpressionBinding GroupBy (формат) для CustomItem для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="46e72-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="46e72-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="46e72-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="46e72-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="46e72-107">Attributes and Elements</span></span>

<span data-ttu-id="46e72-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `ExpressionBinding` элемент.</span><span class="sxs-lookup"><span data-stu-id="46e72-108">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="46e72-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="46e72-109">Attributes</span></span>

<span data-ttu-id="46e72-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="46e72-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="46e72-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="46e72-111">Child Elements</span></span>

|<span data-ttu-id="46e72-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="46e72-112">Element</span></span>|<span data-ttu-id="46e72-113">Описание</span><span class="sxs-lookup"><span data-stu-id="46e72-113">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="46e72-114">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="46e72-114">Optional element.</span></span><br /><br /> <span data-ttu-id="46e72-115">Определяет элемент управления, который используется в этом элементе управления.</span><span class="sxs-lookup"><span data-stu-id="46e72-115">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="46e72-116">Элемент CustomControlName для ExpressionBinding для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="46e72-116">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="46e72-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="46e72-117">Optional element.</span></span><br /><br /> <span data-ttu-id="46e72-118">Указывает имя общего элемента управления или элемент управления.</span><span class="sxs-lookup"><span data-stu-id="46e72-118">Specifies the name of a common control or a view control.</span></span>|
|<span data-ttu-id="46e72-119">[Элемент EnumerateCollection для ExpressionBinding для GroupBy (формат)](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md)EnumerateCollection-элемент для ExpressionBinding для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="46e72-119">[EnumerateCollection Element for ExpressionBinding for GroupBy (Format)](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md)EnumerateCollection Element for ExpressionBinding for GroupBy (Format)</span></span>|<span data-ttu-id="46e72-120">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="46e72-120">Optional element.</span></span><br /><br /> <span data-ttu-id="46e72-121">Указано, что отображаются элементы коллекции.</span><span class="sxs-lookup"><span data-stu-id="46e72-121">Specified that the elements of collections are displayed.</span></span>|
|[<span data-ttu-id="46e72-122">Элемент ItemSelectionCondition для ExpressionBinding для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="46e72-122">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="46e72-123">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="46e72-123">Optional element.</span></span><br /><br /> <span data-ttu-id="46e72-124">Определяет условие, которое должен существовать для данного элемента управления для использования.</span><span class="sxs-lookup"><span data-stu-id="46e72-124">Defines the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="46e72-125">Элемент PropertyName для ExpressionBinding для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="46e72-125">PropertyName Element for ExpressionBinding for GroupBy (Format)</span></span>](./propertyname-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="46e72-126">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="46e72-126">Optional element.</span></span><br /><br /> <span data-ttu-id="46e72-127">Задает свойство .NET, значение которого отображается элементом управления.</span><span class="sxs-lookup"><span data-stu-id="46e72-127">Specifies the .NET property whose value is displayed by the control.</span></span>|
|[<span data-ttu-id="46e72-128">Элемент ScriptBlock для ExpressionBinding для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="46e72-128">ScriptBlock Element for ExpressionBinding for GroupBy (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="46e72-129">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="46e72-129">Optional element.</span></span><br /><br /> <span data-ttu-id="46e72-130">Указывает сценарий, значение которого отображается элементом управления.</span><span class="sxs-lookup"><span data-stu-id="46e72-130">Specifies the script whose value is displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="46e72-131">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="46e72-131">Parent Elements</span></span>

|<span data-ttu-id="46e72-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="46e72-132">Element</span></span>|<span data-ttu-id="46e72-133">Описание</span><span class="sxs-lookup"><span data-stu-id="46e72-133">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="46e72-134">Элемент CustomItem для CustomEntry для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="46e72-134">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="46e72-135">Определяет, какие данные отображаются в представлении пользовательского элемента управления и как он отображается.</span><span class="sxs-lookup"><span data-stu-id="46e72-135">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|

## <a name="see-also"></a><span data-ttu-id="46e72-136">См. также</span><span class="sxs-lookup"><span data-stu-id="46e72-136">See Also</span></span>

[<span data-ttu-id="46e72-137">Элемент CustomControlName для ExpressionBinding для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="46e72-137">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="46e72-138">Элемент EnumerateCollection для ExpressionBinding для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="46e72-138">EnumerateCollection Element for ExpressionBinding for GroupBy (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="46e72-139">Элемент ItemSelectionCondition для ExpressionBinding для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="46e72-139">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="46e72-140">Элемент PropertyName для ExpressionBinding для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="46e72-140">PropertyName Element for ExpressionBinding for GroupBy (Format)</span></span>](./propertyname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="46e72-141">Элемент ScriptBlock для ExpressionBinding для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="46e72-141">ScriptBlock Element for ExpressionBinding for GroupBy (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="46e72-142">Элемент CustomItem для CustomEntry для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="46e72-142">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="46e72-143">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="46e72-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
