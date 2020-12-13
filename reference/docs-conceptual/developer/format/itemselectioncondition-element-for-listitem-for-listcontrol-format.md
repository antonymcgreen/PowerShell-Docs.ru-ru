---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент ItemSelectionCondition для элемента ListItem для элемента ListControl (формат)
description: Элемент ItemSelectionCondition для элемента ListItem для элемента ListControl (формат)
ms.openlocfilehash: 13d925da10c2386123983d52b109c03a0c3c63ab
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667816"
---
# <a name="itemselectioncondition-element-for-listitem-for-listcontrol-format"></a><span data-ttu-id="df11e-103">Элемент ItemSelectionCondition для элемента ListItem для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="df11e-103">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>

<span data-ttu-id="df11e-104">Определяет условие, которое должно существовать для использования этого элемента списка.</span><span class="sxs-lookup"><span data-stu-id="df11e-104">Defines the condition that must exist for this list item to be used.</span></span>

<span data-ttu-id="df11e-105">Элемент конфигурации (Format) Виевдефинитионс элемент (Format) элемент представления (формат) ListControl элемент (Format) Листентриес для ListControl (Format) Листентри элемент для Листентриес для ListControl (Format) элемент ListItem для листентри для элементов ListItem в ListControl (формат) ListControl для элемента SPListItem (формат) элемент для элементов ListItem для итемселектионкондитион (формат)</span><span class="sxs-lookup"><span data-stu-id="df11e-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for ListControl (Format) ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="df11e-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="df11e-106">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="df11e-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="df11e-107">Attributes and Elements</span></span>

<span data-ttu-id="df11e-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ItemSelectionCondition` элемента.</span><span class="sxs-lookup"><span data-stu-id="df11e-108">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="df11e-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="df11e-109">Attributes</span></span>

<span data-ttu-id="df11e-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="df11e-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="df11e-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="df11e-111">Child Elements</span></span>

|<span data-ttu-id="df11e-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="df11e-112">Element</span></span>|<span data-ttu-id="df11e-113">Описание</span><span class="sxs-lookup"><span data-stu-id="df11e-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="df11e-114">Элемент PropertyName для элемента ItemSelectionCondition для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="df11e-114">PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-listcontrol-format.md)|<span data-ttu-id="df11e-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="df11e-115">Optional element.</span></span><br /><br /> <span data-ttu-id="df11e-116">Указывает свойство .NET, которое запускает условие.</span><span class="sxs-lookup"><span data-stu-id="df11e-116">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="df11e-117">Элемент ScriptBlock для элемента ItemSelectionCondition для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="df11e-117">ScriptBlock Element for ItemSelectionCondition for ListControl (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)|<span data-ttu-id="df11e-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="df11e-118">Optional element.</span></span><br /><br /> <span data-ttu-id="df11e-119">Указывает скрипт, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="df11e-119">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="df11e-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="df11e-120">Parent Elements</span></span>

|<span data-ttu-id="df11e-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="df11e-121">Element</span></span>|<span data-ttu-id="df11e-122">Описание</span><span class="sxs-lookup"><span data-stu-id="df11e-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="df11e-123">Элемент ListItem для элемента ListItems для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="df11e-123">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="df11e-124">Определяет свойство или скрипт, значение которого отображается в строке представления списка.</span><span class="sxs-lookup"><span data-stu-id="df11e-124">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="df11e-125">Комментарии</span><span class="sxs-lookup"><span data-stu-id="df11e-125">Remarks</span></span>

<span data-ttu-id="df11e-126">Можно указать одно имя свойства или скрипт для этого условия, но не указывать оба значения.</span><span class="sxs-lookup"><span data-stu-id="df11e-126">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="df11e-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="df11e-127">See Also</span></span>

[<span data-ttu-id="df11e-128">Элемент ListItem для элемента ListItems для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="df11e-128">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="df11e-129">Элемент PropertyName для элемента ItemSelectionCondition для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="df11e-129">PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-listcontrol-format.md)

[<span data-ttu-id="df11e-130">Элемент ScriptBlock для элемента ItemSelectionCondition для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="df11e-130">ScriptBlock Element for ItemSelectionCondition for ListControl (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)

[<span data-ttu-id="df11e-131">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="df11e-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
