---
title: Элемент ItemSelectionCondition для ListItem для ListControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d2668aea-37e9-4753-a4e9-7980ae5ec2eb
caps.latest.revision: 10
ms.openlocfilehash: 6bc0ccbcc5bd62429f63ed220da66dc66f44f7ca
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065450"
---
# <a name="itemselectioncondition-element-for-listitem-for-listcontrol-format"></a><span data-ttu-id="87c84-102">Элемент ItemSelectionCondition для элемента ListItem для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="87c84-102">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>

<span data-ttu-id="87c84-103">Определяет условие, которое должен существовать для данного элемента списка для использования.</span><span class="sxs-lookup"><span data-stu-id="87c84-103">Defines the condition that must exist for this list item to be used.</span></span>

<span data-ttu-id="87c84-104">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) элемента ListControl (формат) ListEntries элемента конфигурации для элемента ListControl (формат) ListEntry ListEntries для элемента ListControl (формат) ListItems ListEntry для элемента ListControl (формат) ListItem ListItems для элемента ListControl (формат) ItemSelectionCondition ListItem для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="87c84-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for ListControl (Format) ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="87c84-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="87c84-105">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="87c84-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="87c84-106">Attributes and Elements</span></span>

<span data-ttu-id="87c84-107">Ниже описаны атрибуты, дочерние элементы и родительский элемент `ItemSelectionCondition` элемент.</span><span class="sxs-lookup"><span data-stu-id="87c84-107">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="87c84-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="87c84-108">Attributes</span></span>

<span data-ttu-id="87c84-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="87c84-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="87c84-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="87c84-110">Child Elements</span></span>

|<span data-ttu-id="87c84-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="87c84-111">Element</span></span>|<span data-ttu-id="87c84-112">Описание</span><span class="sxs-lookup"><span data-stu-id="87c84-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="87c84-113">Элемент PropertyName для ItemSelectionCondition для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="87c84-113">PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-listcontrol-format.md)|<span data-ttu-id="87c84-114">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="87c84-114">Optional element.</span></span><br /><br /> <span data-ttu-id="87c84-115">Задает свойство .NET, которое активирует условие.</span><span class="sxs-lookup"><span data-stu-id="87c84-115">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="87c84-116">Элемент ScriptBlock для ItemSelectionCondition для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="87c84-116">ScriptBlock Element for ItemSelectionCondition for ListControl (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)|<span data-ttu-id="87c84-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="87c84-117">Optional element.</span></span><br /><br /> <span data-ttu-id="87c84-118">Указывает сценарий, который активирует условие.</span><span class="sxs-lookup"><span data-stu-id="87c84-118">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="87c84-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="87c84-119">Parent Elements</span></span>

|<span data-ttu-id="87c84-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="87c84-120">Element</span></span>|<span data-ttu-id="87c84-121">Описание</span><span class="sxs-lookup"><span data-stu-id="87c84-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="87c84-122">Элемент ListItem для ListItems для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="87c84-122">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="87c84-123">Определяет свойство или скрипта, значение которого отображается в строке в представлении списка.</span><span class="sxs-lookup"><span data-stu-id="87c84-123">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="87c84-124">Замечания</span><span class="sxs-lookup"><span data-stu-id="87c84-124">Remarks</span></span>

<span data-ttu-id="87c84-125">Можно указать одно имя свойства или сценарий для данного условия, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="87c84-125">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="87c84-126">См. также</span><span class="sxs-lookup"><span data-stu-id="87c84-126">See Also</span></span>

[<span data-ttu-id="87c84-127">Элемент ListItem для ListItems для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="87c84-127">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="87c84-128">Элемент PropertyName для ItemSelectionCondition для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="87c84-128">PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-listcontrol-format.md)

[<span data-ttu-id="87c84-129">Элемент ScriptBlock для ItemSelectionCondition для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="87c84-129">ScriptBlock Element for ItemSelectionCondition for ListControl (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)

[<span data-ttu-id="87c84-130">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="87c84-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
