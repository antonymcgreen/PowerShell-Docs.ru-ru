---
title: Элемент Итемселектионкондитион для ListItem для ListControl (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d2668aea-37e9-4753-a4e9-7980ae5ec2eb
caps.latest.revision: 10
ms.openlocfilehash: 6bc0ccbcc5bd62429f63ed220da66dc66f44f7ca
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72365193"
---
# <a name="itemselectioncondition-element-for-listitem-for-listcontrol-format"></a><span data-ttu-id="22372-102">Элемент ItemSelectionCondition для элемента ListItem для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="22372-102">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>

<span data-ttu-id="22372-103">Определяет условие, которое должно существовать для использования этого элемента списка.</span><span class="sxs-lookup"><span data-stu-id="22372-103">Defines the condition that must exist for this list item to be used.</span></span>

<span data-ttu-id="22372-104">Элемент Configuration (Format) Виевдефинитионс элемент представления (Format) элемент ListControl (Format) элемент Листентриес для ListControl (Format) Листентри для Листентриес для ListControl (Format) элемент ListItems для Листентри Элемент ListControl (Format) ListItem для элементов ListItem для ListControl (Format) Итемселектионкондитион для элемента ListItem для ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="22372-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for ListControl (Format) ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="22372-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="22372-105">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="22372-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="22372-106">Attributes and Elements</span></span>

<span data-ttu-id="22372-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `ItemSelectionCondition`.</span><span class="sxs-lookup"><span data-stu-id="22372-107">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="22372-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="22372-108">Attributes</span></span>

<span data-ttu-id="22372-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="22372-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="22372-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="22372-110">Child Elements</span></span>

|<span data-ttu-id="22372-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="22372-111">Element</span></span>|<span data-ttu-id="22372-112">Описание</span><span class="sxs-lookup"><span data-stu-id="22372-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="22372-113">Элемент PropertyName для Итемселектионкондитион для ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="22372-113">PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-listcontrol-format.md)|<span data-ttu-id="22372-114">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="22372-114">Optional element.</span></span><br /><br /> <span data-ttu-id="22372-115">Указывает свойство .NET, которое запускает условие.</span><span class="sxs-lookup"><span data-stu-id="22372-115">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="22372-116">Элемент ScriptBlock для Итемселектионкондитион для ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="22372-116">ScriptBlock Element for ItemSelectionCondition for ListControl (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)|<span data-ttu-id="22372-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="22372-117">Optional element.</span></span><br /><br /> <span data-ttu-id="22372-118">Указывает скрипт, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="22372-118">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="22372-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="22372-119">Parent Elements</span></span>

|<span data-ttu-id="22372-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="22372-120">Element</span></span>|<span data-ttu-id="22372-121">Описание</span><span class="sxs-lookup"><span data-stu-id="22372-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="22372-122">Элемент ListItem для элементов ListItem для ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="22372-122">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="22372-123">Определяет свойство или скрипт, значение которого отображается в строке представления списка.</span><span class="sxs-lookup"><span data-stu-id="22372-123">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="22372-124">Замечания</span><span class="sxs-lookup"><span data-stu-id="22372-124">Remarks</span></span>

<span data-ttu-id="22372-125">Можно указать одно имя свойства или скрипт для этого условия, но не указывать оба значения.</span><span class="sxs-lookup"><span data-stu-id="22372-125">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="22372-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="22372-126">See Also</span></span>

[<span data-ttu-id="22372-127">Элемент ListItem для элементов ListItem для ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="22372-127">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="22372-128">Элемент PropertyName для Итемселектионкондитион для ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="22372-128">PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-listcontrol-format.md)

[<span data-ttu-id="22372-129">Элемент ScriptBlock для Итемселектионкондитион для ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="22372-129">ScriptBlock Element for ItemSelectionCondition for ListControl (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)

[<span data-ttu-id="22372-130">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="22372-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
