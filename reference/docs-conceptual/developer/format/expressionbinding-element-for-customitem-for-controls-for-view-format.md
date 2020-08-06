---
title: Элемент ExpressionBinding для Кустомитем элементов управления для представления (формат) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 6760bf17be58411948ecb3437bf18bce40073954
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773816"
---
# <a name="expressionbinding-element-for-customitem-for-controls-for-view-format"></a><span data-ttu-id="64ea3-102">Элемент ExpressionBinding для элемента CustomItem для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="64ea3-102">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>

<span data-ttu-id="64ea3-103">Определяет данные, отображаемые элементом управления.</span><span class="sxs-lookup"><span data-stu-id="64ea3-103">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="64ea3-104">Этот элемент используется при определении элементов управления, которые могут использоваться представлением.</span><span class="sxs-lookup"><span data-stu-id="64ea3-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="64ea3-105">Элемент Configuration (Format) Виевдефинитионс элемент (формат) элемент представления (Format) управляет управляющий элемент (Format) элемент управления для элементов управления представления (Format) ошибка customcontrol для элементов управления элемента Кустоментриес View (формат). для элемента Ошибка customcontrol для представления (Format) Кустоментри для Кустоментриес элементов управления для элемента Controls представления (Format) Кустомитем для Кустоментри для элементов управления представления (Format) ExpressionBinding для Кустомитем элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="64ea3-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="64ea3-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="64ea3-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="64ea3-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="64ea3-107">Attributes and Elements</span></span>

<span data-ttu-id="64ea3-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ExpressionBinding` элемента.</span><span class="sxs-lookup"><span data-stu-id="64ea3-108">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="64ea3-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="64ea3-109">Attributes</span></span>

<span data-ttu-id="64ea3-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="64ea3-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="64ea3-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="64ea3-111">Child Elements</span></span>

|<span data-ttu-id="64ea3-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="64ea3-112">Element</span></span>|<span data-ttu-id="64ea3-113">Описание</span><span class="sxs-lookup"><span data-stu-id="64ea3-113">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="64ea3-114">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="64ea3-114">Optional element.</span></span><br /><br /> <span data-ttu-id="64ea3-115">Определяет элемент управления, используемый этим элементом управления.</span><span class="sxs-lookup"><span data-stu-id="64ea3-115">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="64ea3-116">Элемент CustomControlName для элемента ExpressionBinding для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="64ea3-116">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="64ea3-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="64ea3-117">Optional element.</span></span><br /><br /> <span data-ttu-id="64ea3-118">Указывает имя общего элемента управления или элемента управления представления.</span><span class="sxs-lookup"><span data-stu-id="64ea3-118">Specifies the name of a common control or a view control.</span></span>|
|[<span data-ttu-id="64ea3-119">Элемент EnumerateCollection для элемента ExpressionBinding для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="64ea3-119">EnumerateCollection Element for ExpressionBinding for Controls for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="64ea3-120">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="64ea3-120">Optional element.</span></span><br /><br /> <span data-ttu-id="64ea3-121">Указывает, что элементы коллекций отображаются.</span><span class="sxs-lookup"><span data-stu-id="64ea3-121">Specifies that the elements of collections are displayed.</span></span>|
|[<span data-ttu-id="64ea3-122">Элемент Итемселектионкондитион элемента ExpressionBinding для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="64ea3-122">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="64ea3-123">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="64ea3-123">Optional element.</span></span><br /><br /> <span data-ttu-id="64ea3-124">Определяет условие, которое должно существовать для использования этого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="64ea3-124">Defines the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="64ea3-125">Элемент PropertyName для элемента ExpressionBinding для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="64ea3-125">PropertyName Element for ExpressionBinding for Controls for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="64ea3-126">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="64ea3-126">Optional element.</span></span><br /><br /> <span data-ttu-id="64ea3-127">Указывает свойство .NET, значение которого отображается элементом управления.</span><span class="sxs-lookup"><span data-stu-id="64ea3-127">Specifies the .NET property whose value is displayed by the control.</span></span>|
|[<span data-ttu-id="64ea3-128">Элемент ScriptBlock для элемента ExpressionBinding для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="64ea3-128">ScriptBlock Element for ExpressionBinding for Controls for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="64ea3-129">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="64ea3-129">Optional element.</span></span><br /><br /> <span data-ttu-id="64ea3-130">Задает скрипт, значение которого отображается элементом управления.</span><span class="sxs-lookup"><span data-stu-id="64ea3-130">Specifies the script whose value is displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="64ea3-131">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="64ea3-131">Parent Elements</span></span>

|<span data-ttu-id="64ea3-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="64ea3-132">Element</span></span>|<span data-ttu-id="64ea3-133">Описание</span><span class="sxs-lookup"><span data-stu-id="64ea3-133">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="64ea3-134">Элемент CustomItem для элемента CustomEntry для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="64ea3-134">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="64ea3-135">Определяет, какие данные отображаются элементом управления и как они отображаются.</span><span class="sxs-lookup"><span data-stu-id="64ea3-135">Defines what data is displayed by the control and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="64ea3-136">Примечания</span><span class="sxs-lookup"><span data-stu-id="64ea3-136">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="64ea3-137">См. также</span><span class="sxs-lookup"><span data-stu-id="64ea3-137">See Also</span></span>

[<span data-ttu-id="64ea3-138">Элемент CustomItem для элемента CustomEntry для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="64ea3-138">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)

[<span data-ttu-id="64ea3-139">Элемент CustomControlName для элемента ExpressionBinding для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="64ea3-139">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="64ea3-140">Элемент EnumerateCollection для элемента ExpressionBinding для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="64ea3-140">EnumerateCollection Element for ExpressionBinding for Controls for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="64ea3-141">Элемент Итемселектионкондитион элемента ExpressionBinding для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="64ea3-141">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="64ea3-142">Элемент PropertyName для элемента ExpressionBinding для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="64ea3-142">PropertyName Element for ExpressionBinding for Controls for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="64ea3-143">Элемент ScriptBlock для элемента ExpressionBinding для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="64ea3-143">ScriptBlock Element for ExpressionBinding for Controls for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="64ea3-144">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="64ea3-144">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
