---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента CustomControl (формат)
description: Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента CustomControl (формат)
ms.openlocfilehash: 38c88ad47e57cd20902c6b8aabdb0b8e8b682ba4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648043"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-customcontrol-format"></a><span data-ttu-id="373fd-103">Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента CustomControl (формат)</span><span class="sxs-lookup"><span data-stu-id="373fd-103">ItemSelectionCondition Element for ExpressionBinding for CustomControl (Format)</span></span>

<span data-ttu-id="373fd-104">Определяет условие, которое должно существовать для использования этого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="373fd-104">Defines the condition that must exist for this control to be used.</span></span> <span data-ttu-id="373fd-105">Количество условий выбора, которое можно указать для элемента управления, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="373fd-105">There is no limit to the number of selection conditions that can be specified for a control item.</span></span> <span data-ttu-id="373fd-106">Этот элемент используется при определении пользовательского представления элемента управления.</span><span class="sxs-lookup"><span data-stu-id="373fd-106">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="373fd-107">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ошибка customcontrol элемент (Format) Кустоментриес для ошибка customcontrol для элемента кустоментри представления (Format) кустоментриес для кустомитем для представления (Format) в кустоментри для ExpressionBinding для кустомитем для представления (формат) ошибка customcontrol для элемента for View (формат) ItemSelectionCondition.</span><span class="sxs-lookup"><span data-stu-id="373fd-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for View (Format) ExpressionBinding Element for CustomItem for CustomControl for View (Format) ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="373fd-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="373fd-108">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="373fd-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="373fd-109">Attributes and Elements</span></span>

<span data-ttu-id="373fd-110">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ItemSelectionCondition` элемента.</span><span class="sxs-lookup"><span data-stu-id="373fd-110">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="373fd-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="373fd-111">Attributes</span></span>

<span data-ttu-id="373fd-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="373fd-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="373fd-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="373fd-113">Child Elements</span></span>

|<span data-ttu-id="373fd-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="373fd-114">Element</span></span>|<span data-ttu-id="373fd-115">Описание</span><span class="sxs-lookup"><span data-stu-id="373fd-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="373fd-116">Элемент PropertyName для Итемселектионкондитион для ошибка customcontrol в представлении (Format</span><span class="sxs-lookup"><span data-stu-id="373fd-116">PropertyName Element for ItemSelectionCondition for CustomControl for View (Format</span></span>](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="373fd-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="373fd-117">Optional element.</span></span><br /><br /> <span data-ttu-id="373fd-118">Указывает свойство .NET, которое запускает условие.</span><span class="sxs-lookup"><span data-stu-id="373fd-118">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="373fd-119">Элемент ScriptBlock для элемента ItemSelectionCondition для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="373fd-119">ScriptBlock Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="373fd-120">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="373fd-120">Optional element.</span></span><br /><br /> <span data-ttu-id="373fd-121">Указывает скрипт, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="373fd-121">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="373fd-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="373fd-122">Parent Elements</span></span>

|<span data-ttu-id="373fd-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="373fd-123">Element</span></span>|<span data-ttu-id="373fd-124">Описание</span><span class="sxs-lookup"><span data-stu-id="373fd-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="373fd-125">Элемент ExpressionBinding для элемента CustomItem для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="373fd-125">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="373fd-126">Определяет данные, отображаемые элементом управления.</span><span class="sxs-lookup"><span data-stu-id="373fd-126">Defines the data that is displayed by the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="373fd-127">Комментарии</span><span class="sxs-lookup"><span data-stu-id="373fd-127">Remarks</span></span>

<span data-ttu-id="373fd-128">Можно указать одно имя свойства или скрипт для этого условия, но не указывать оба значения.</span><span class="sxs-lookup"><span data-stu-id="373fd-128">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="373fd-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="373fd-129">See Also</span></span>

[<span data-ttu-id="373fd-130">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="373fd-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)

[<span data-ttu-id="373fd-131">Элемент ExpressionBinding для элемента CustomItem для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="373fd-131">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)
