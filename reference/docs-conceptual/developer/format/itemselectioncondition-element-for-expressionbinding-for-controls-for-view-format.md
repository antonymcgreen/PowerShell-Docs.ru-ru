---
title: Элемент Итемселектионкондитион для ExpressionBinding элементов управления для представления (формат) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: e8e3ea64fd947fbb2b98c410ac08533f386c9505
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781211"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format"></a><span data-ttu-id="f8342-102">Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="f8342-102">ItemSelectionCondition Element for ExpressionBinding for Controls for View (Format)</span></span>

<span data-ttu-id="f8342-103">Определяет условие, которое должно существовать для использования этого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="f8342-103">Defines the condition that must exist for this control to be used.</span></span> <span data-ttu-id="f8342-104">Этот элемент используется при определении элементов управления, которые могут использоваться представлением.</span><span class="sxs-lookup"><span data-stu-id="f8342-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="f8342-105">Элемент Configuration (Format) Виевдефинитионс элемент (формат) элемент представления (Format) управляет элементом управления "элемент (Format)" для элементов управления в элементе "View" (Format) ошибка customcontrol для элемента управления элементов формат). элемент Кустоментри для Кустоментриес для элементов управления для элемента Кустомитем представления (Format) для Кустоментри для элементов управления для элемента "View" (формат) ExpressionBinding для Кустомитем для элементов управления для представления (Format) ItemSelectionCondition элемента ExpressionBinding для элементов управления представления (формат)</span><span class="sxs-lookup"><span data-stu-id="f8342-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format) ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f8342-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f8342-106">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f8342-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f8342-107">Attributes and Elements</span></span>

<span data-ttu-id="f8342-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ItemSelectionCondition` элемента.</span><span class="sxs-lookup"><span data-stu-id="f8342-108">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f8342-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f8342-109">Attributes</span></span>

<span data-ttu-id="f8342-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f8342-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f8342-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f8342-111">Child Elements</span></span>

|<span data-ttu-id="f8342-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="f8342-112">Element</span></span>|<span data-ttu-id="f8342-113">Описание</span><span class="sxs-lookup"><span data-stu-id="f8342-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f8342-114">Элемент PropertyName для элемента ItemSelectionCondition для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="f8342-114">PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="f8342-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="f8342-115">Optional element.</span></span><br /><br /> <span data-ttu-id="f8342-116">Указывает свойство .NET, которое запускает условие.</span><span class="sxs-lookup"><span data-stu-id="f8342-116">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="f8342-117">Элемент ScriptBlock для элемента ItemSelectionCondition для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="f8342-117">ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="f8342-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="f8342-118">Optional element.</span></span><br /><br /> <span data-ttu-id="f8342-119">Указывает скрипт, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="f8342-119">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="f8342-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f8342-120">Parent Elements</span></span>

|<span data-ttu-id="f8342-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="f8342-121">Element</span></span>|<span data-ttu-id="f8342-122">Описание</span><span class="sxs-lookup"><span data-stu-id="f8342-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f8342-123">Элемент ExpressionBinding для элемента CustomItem для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="f8342-123">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="f8342-124">Определяет данные, отображаемые элементом управления.</span><span class="sxs-lookup"><span data-stu-id="f8342-124">Defines the data that is displayed by the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f8342-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="f8342-125">Remarks</span></span>

<span data-ttu-id="f8342-126">Можно указать одно имя свойства или скрипт для этого условия, но не указывать оба значения.</span><span class="sxs-lookup"><span data-stu-id="f8342-126">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="f8342-127">См. также</span><span class="sxs-lookup"><span data-stu-id="f8342-127">See Also</span></span>

[<span data-ttu-id="f8342-128">Элемент PropertyName для элемента ItemSelectionCondition для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="f8342-128">PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="f8342-129">Элемент ScriptBlock для элемента ItemSelectionCondition для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="f8342-129">ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="f8342-130">Элемент ExpressionBinding для элемента CustomItem для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="f8342-130">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="f8342-131">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="f8342-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
