---
title: Элемент Итемселектионкондитион для ExpressionBinding для ошибка customcontrol (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 6a5c66a63c02980b16c2d2d9dd689410c8aec51c
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781194"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-customcontrol-format"></a><span data-ttu-id="6a9f2-102">Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента CustomControl (формат)</span><span class="sxs-lookup"><span data-stu-id="6a9f2-102">ItemSelectionCondition Element for ExpressionBinding for CustomControl (Format)</span></span>

<span data-ttu-id="6a9f2-103">Определяет условие, которое должно существовать для использования этого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="6a9f2-103">Defines the condition that must exist for this control to be used.</span></span> <span data-ttu-id="6a9f2-104">Количество условий выбора, которое можно указать для элемента управления, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="6a9f2-104">There is no limit to the number of selection conditions that can be specified for a control item.</span></span> <span data-ttu-id="6a9f2-105">Этот элемент используется при определении пользовательского представления элемента управления.</span><span class="sxs-lookup"><span data-stu-id="6a9f2-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="6a9f2-106">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ошибка customcontrol элемент (Format) Кустоментриес для ошибка customcontrol для элемента кустоментри представления (Format) кустоментриес для кустомитем для представления (Format) в кустоментри для ExpressionBinding для кустомитем для представления (формат) ошибка customcontrol для элемента for View (формат) ItemSelectionCondition.</span><span class="sxs-lookup"><span data-stu-id="6a9f2-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for View (Format) ExpressionBinding Element for CustomItem for CustomControl for View (Format) ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="6a9f2-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6a9f2-107">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6a9f2-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6a9f2-108">Attributes and Elements</span></span>

<span data-ttu-id="6a9f2-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ItemSelectionCondition` элемента.</span><span class="sxs-lookup"><span data-stu-id="6a9f2-109">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="6a9f2-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6a9f2-110">Attributes</span></span>

<span data-ttu-id="6a9f2-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="6a9f2-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="6a9f2-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6a9f2-112">Child Elements</span></span>

|<span data-ttu-id="6a9f2-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="6a9f2-113">Element</span></span>|<span data-ttu-id="6a9f2-114">Описание</span><span class="sxs-lookup"><span data-stu-id="6a9f2-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6a9f2-115">Элемент PropertyName для Итемселектионкондитион для ошибка customcontrol в представлении (Format</span><span class="sxs-lookup"><span data-stu-id="6a9f2-115">PropertyName Element for ItemSelectionCondition for CustomControl for View (Format</span></span>](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="6a9f2-116">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="6a9f2-116">Optional element.</span></span><br /><br /> <span data-ttu-id="6a9f2-117">Указывает свойство .NET, которое запускает условие.</span><span class="sxs-lookup"><span data-stu-id="6a9f2-117">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="6a9f2-118">Элемент ScriptBlock для элемента ItemSelectionCondition для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="6a9f2-118">ScriptBlock Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="6a9f2-119">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="6a9f2-119">Optional element.</span></span><br /><br /> <span data-ttu-id="6a9f2-120">Указывает скрипт, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="6a9f2-120">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="6a9f2-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6a9f2-121">Parent Elements</span></span>

|<span data-ttu-id="6a9f2-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="6a9f2-122">Element</span></span>|<span data-ttu-id="6a9f2-123">Описание</span><span class="sxs-lookup"><span data-stu-id="6a9f2-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6a9f2-124">Элемент ExpressionBinding для элемента CustomItem для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="6a9f2-124">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="6a9f2-125">Определяет данные, отображаемые элементом управления.</span><span class="sxs-lookup"><span data-stu-id="6a9f2-125">Defines the data that is displayed by the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="6a9f2-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="6a9f2-126">Remarks</span></span>

<span data-ttu-id="6a9f2-127">Можно указать одно имя свойства или скрипт для этого условия, но не указывать оба значения.</span><span class="sxs-lookup"><span data-stu-id="6a9f2-127">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="6a9f2-128">См. также</span><span class="sxs-lookup"><span data-stu-id="6a9f2-128">See Also</span></span>

[<span data-ttu-id="6a9f2-129">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="6a9f2-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)

[<span data-ttu-id="6a9f2-130">Элемент ExpressionBinding для элемента CustomItem для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="6a9f2-130">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)
