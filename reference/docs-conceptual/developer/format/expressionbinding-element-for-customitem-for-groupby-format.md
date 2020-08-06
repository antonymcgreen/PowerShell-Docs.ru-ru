---
title: Элемент ExpressionBinding для Кустомитем для GroupBy (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 5b0017e487aab4ffcbf901cd44aad9b275b22832
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773731"
---
# <a name="expressionbinding-element-for-customitem-for-groupby-format"></a><span data-ttu-id="04eef-102">Элемент ExpressionBinding для элемента CustomItem для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="04eef-102">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>

<span data-ttu-id="04eef-103">Определяет данные, отображаемые элементом управления.</span><span class="sxs-lookup"><span data-stu-id="04eef-103">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="04eef-104">Этот элемент используется при определении того, как отображается новая группа объектов.</span><span class="sxs-lookup"><span data-stu-id="04eef-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="04eef-105">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент GroupBy для элемента "View" (Format) ошибка customcontrol для элемента GroupBy (Format) Кустоментриес для ошибка customcontrol for GroupBy (формат) кустоментри для ошибка customcontrol for GroupBy (формат) кустомитем для кустоментри for GroupBy (Format) ExpressionBinding для кустомитем for GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="04eef-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="04eef-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="04eef-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="04eef-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="04eef-107">Attributes and Elements</span></span>

<span data-ttu-id="04eef-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ExpressionBinding` элемента.</span><span class="sxs-lookup"><span data-stu-id="04eef-108">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="04eef-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="04eef-109">Attributes</span></span>

<span data-ttu-id="04eef-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="04eef-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="04eef-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="04eef-111">Child Elements</span></span>

|<span data-ttu-id="04eef-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="04eef-112">Element</span></span>|<span data-ttu-id="04eef-113">Описание</span><span class="sxs-lookup"><span data-stu-id="04eef-113">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="04eef-114">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="04eef-114">Optional element.</span></span><br /><br /> <span data-ttu-id="04eef-115">Определяет элемент управления, используемый этим элементом управления.</span><span class="sxs-lookup"><span data-stu-id="04eef-115">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="04eef-116">Элемент CustomControlName для элемента ExpressionBinding для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="04eef-116">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="04eef-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="04eef-117">Optional element.</span></span><br /><br /> <span data-ttu-id="04eef-118">Указывает имя общего элемента управления или элемента управления представления.</span><span class="sxs-lookup"><span data-stu-id="04eef-118">Specifies the name of a common control or a view control.</span></span>|
|<span data-ttu-id="04eef-119">[Элемент енумератеколлектион для ExpressionBinding для GroupBy (Format)](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md) Элемент Енумератеколлектион для ExpressionBinding для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="04eef-119">[EnumerateCollection Element for ExpressionBinding for GroupBy (Format)](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md)EnumerateCollection Element for ExpressionBinding for GroupBy (Format)</span></span>|<span data-ttu-id="04eef-120">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="04eef-120">Optional element.</span></span><br /><br /> <span data-ttu-id="04eef-121">Указывает, что отображаются элементы коллекций.</span><span class="sxs-lookup"><span data-stu-id="04eef-121">Specified that the elements of collections are displayed.</span></span>|
|[<span data-ttu-id="04eef-122">Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="04eef-122">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="04eef-123">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="04eef-123">Optional element.</span></span><br /><br /> <span data-ttu-id="04eef-124">Определяет условие, которое должно существовать для использования этого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="04eef-124">Defines the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="04eef-125">Элемент PropertyName для элемента ExpressionBinding для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="04eef-125">PropertyName Element for ExpressionBinding for GroupBy (Format)</span></span>](./propertyname-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="04eef-126">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="04eef-126">Optional element.</span></span><br /><br /> <span data-ttu-id="04eef-127">Указывает свойство .NET, значение которого отображается элементом управления.</span><span class="sxs-lookup"><span data-stu-id="04eef-127">Specifies the .NET property whose value is displayed by the control.</span></span>|
|[<span data-ttu-id="04eef-128">Элемент ScriptBlock для элемента ExpressionBinding для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="04eef-128">ScriptBlock Element for ExpressionBinding for GroupBy (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="04eef-129">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="04eef-129">Optional element.</span></span><br /><br /> <span data-ttu-id="04eef-130">Задает скрипт, значение которого отображается элементом управления.</span><span class="sxs-lookup"><span data-stu-id="04eef-130">Specifies the script whose value is displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="04eef-131">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="04eef-131">Parent Elements</span></span>

|<span data-ttu-id="04eef-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="04eef-132">Element</span></span>|<span data-ttu-id="04eef-133">Описание</span><span class="sxs-lookup"><span data-stu-id="04eef-133">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="04eef-134">Элемент CustomItem для элемента CustomEntry для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="04eef-134">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="04eef-135">Определяет, какие данные отображаются в представлении пользовательского элемента управления и как они отображаются.</span><span class="sxs-lookup"><span data-stu-id="04eef-135">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|

## <a name="see-also"></a><span data-ttu-id="04eef-136">См. также</span><span class="sxs-lookup"><span data-stu-id="04eef-136">See Also</span></span>

[<span data-ttu-id="04eef-137">Элемент CustomControlName для элемента ExpressionBinding для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="04eef-137">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="04eef-138">Элемент EnumerateCollection для элемента ExpressionBinding для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="04eef-138">EnumerateCollection Element for ExpressionBinding for GroupBy (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="04eef-139">Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="04eef-139">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="04eef-140">Элемент PropertyName для элемента ExpressionBinding для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="04eef-140">PropertyName Element for ExpressionBinding for GroupBy (Format)</span></span>](./propertyname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="04eef-141">Элемент ScriptBlock для элемента ExpressionBinding для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="04eef-141">ScriptBlock Element for ExpressionBinding for GroupBy (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="04eef-142">Элемент CustomItem для элемента CustomEntry для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="04eef-142">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="04eef-143">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="04eef-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
