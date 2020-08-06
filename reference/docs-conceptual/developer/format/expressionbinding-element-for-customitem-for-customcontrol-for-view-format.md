---
title: Элемент ExpressionBinding для Кустомитем для ошибка customcontrol для представления (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 1885a2820c0cb250aa6fda80544f58d06136cfeb
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773799"
---
# <a name="expressionbinding-element-for-customitem-for-customcontrol-for-view-format"></a><span data-ttu-id="e9b9e-102">Элемент ExpressionBinding для элемента CustomItem для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="e9b9e-102">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>

<span data-ttu-id="e9b9e-103">Определяет данные, отображаемые элементом управления.</span><span class="sxs-lookup"><span data-stu-id="e9b9e-103">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="e9b9e-104">Этот элемент используется при определении пользовательского представления элемента управления.</span><span class="sxs-lookup"><span data-stu-id="e9b9e-104">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="e9b9e-105">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ошибка customcontrol для элемента Кустоментриес представления (Format) Кустоментри для Кустоментриес для ошибка customcontrol для представления (Format) кустомитем для кустоментри for ошибка customcontrol для представления (Format) ExpressionBinding для кустомитем для ошибка customcontrol для представления (формат).</span><span class="sxs-lookup"><span data-stu-id="e9b9e-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for CustomControl for View (Format) CustomItem Element for CustomEntry for CustomControl for View (Format) ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e9b9e-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e9b9e-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="e9b9e-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e9b9e-107">Attributes and Elements</span></span>

<span data-ttu-id="e9b9e-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ExpressionBinding` элемента.</span><span class="sxs-lookup"><span data-stu-id="e9b9e-108">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e9b9e-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e9b9e-109">Attributes</span></span>

<span data-ttu-id="e9b9e-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e9b9e-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e9b9e-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e9b9e-111">Child Elements</span></span>

|<span data-ttu-id="e9b9e-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="e9b9e-112">Element</span></span>|<span data-ttu-id="e9b9e-113">Описание</span><span class="sxs-lookup"><span data-stu-id="e9b9e-113">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="e9b9e-114">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="e9b9e-114">Optional element.</span></span><br /><br /> <span data-ttu-id="e9b9e-115">Определяет элемент управления, используемый этим элементом управления.</span><span class="sxs-lookup"><span data-stu-id="e9b9e-115">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="e9b9e-116">Элемент CustomControlName для элемента ExpressionBinding для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="e9b9e-116">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="e9b9e-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="e9b9e-117">Optional element.</span></span><br /><br /> <span data-ttu-id="e9b9e-118">Указывает имя общего элемента управления или элемента управления представления.</span><span class="sxs-lookup"><span data-stu-id="e9b9e-118">Specifies the name of a common control or a view control.</span></span>|
|[<span data-ttu-id="e9b9e-119">Элемент EnumerateCollection для элемента ExpressionBinding для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="e9b9e-119">EnumerateCollection Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="e9b9e-120">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="e9b9e-120">Optional element.</span></span><br /><br /> <span data-ttu-id="e9b9e-121">Указывает, что отображаются элементы коллекций.</span><span class="sxs-lookup"><span data-stu-id="e9b9e-121">Specified that the elements of collections are displayed.</span></span>|
|[<span data-ttu-id="e9b9e-122">Элемент Итемселектионкондитион для ExpressionBinding для ошибка customcontrol для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="e9b9e-122">ItemSelectionCondition Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)|<span data-ttu-id="e9b9e-123">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="e9b9e-123">Optional element.</span></span><br /><br /> <span data-ttu-id="e9b9e-124">Определяет условие, которое должно существовать для использования этого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="e9b9e-124">Defines the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="e9b9e-125">Элемент PropertyName для элемента ExpressionBinding для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="e9b9e-125">PropertyName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="e9b9e-126">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="e9b9e-126">Optional element.</span></span><br /><br /> <span data-ttu-id="e9b9e-127">Указывает свойство .NET, значение которого отображается элементом управления.</span><span class="sxs-lookup"><span data-stu-id="e9b9e-127">Specifies the .NET property whose value is displayed by the control.</span></span>|
|[<span data-ttu-id="e9b9e-128">Элемент ScriptBlock для ExpressionBinding для Кустомкустомконтрол для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="e9b9e-128">ScriptBlock Element for ExpressionBinding for CustomCustomControl for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-customcontrol-for-view-format.md)|<span data-ttu-id="e9b9e-129">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="e9b9e-129">Optional element.</span></span><br /><br /> <span data-ttu-id="e9b9e-130">Задает скрипт, значение которого отображается элементом управления.</span><span class="sxs-lookup"><span data-stu-id="e9b9e-130">Specifies the script whose value is displayed by the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e9b9e-131">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e9b9e-131">Parent Elements</span></span>

|<span data-ttu-id="e9b9e-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="e9b9e-132">Element</span></span>|<span data-ttu-id="e9b9e-133">Описание</span><span class="sxs-lookup"><span data-stu-id="e9b9e-133">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e9b9e-134">Элемент CustomItem для элемента CustomEntry для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="e9b9e-134">CustomItem Element for CustomEntry for CustomControl for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="e9b9e-135">Определяет, какие данные отображаются в представлении пользовательского элемента управления и как они отображаются.</span><span class="sxs-lookup"><span data-stu-id="e9b9e-135">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e9b9e-136">Примечания</span><span class="sxs-lookup"><span data-stu-id="e9b9e-136">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="e9b9e-137">См. также</span><span class="sxs-lookup"><span data-stu-id="e9b9e-137">See Also</span></span>

[<span data-ttu-id="e9b9e-138">Элемент CustomControlName для элемента ExpressionBinding для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="e9b9e-138">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="e9b9e-139">Элемент EnumerateCollection для элемента ExpressionBinding для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="e9b9e-139">EnumerateCollection Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="e9b9e-140">Элемент Итемселектионкондитион для ExpressionBinding для ошибка customcontrol для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="e9b9e-140">ItemSelectionCondition Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

[<span data-ttu-id="e9b9e-141">Элемент PropertyName для элемента ExpressionBinding для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="e9b9e-141">PropertyName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./propertyname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="e9b9e-142">Элемент ScriptBlock для элемента ExpressionBinding для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="e9b9e-142">ScriptBlock Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="e9b9e-143">Элемент CustomItem для элемента CustomEntry для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="e9b9e-143">CustomItem Element for CustomEntry for CustomControl for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="e9b9e-144">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="e9b9e-144">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
