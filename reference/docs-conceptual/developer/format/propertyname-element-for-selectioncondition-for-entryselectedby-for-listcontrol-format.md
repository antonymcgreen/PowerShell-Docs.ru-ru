---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент PropertyName для элемента SelectionCondition для элемента EntrySelectedBy для элемента ListControl (формат)
description: Элемент PropertyName для элемента SelectionCondition для элемента EntrySelectedBy для элемента ListControl (формат)
ms.openlocfilehash: 1e318e3a29f07b157b9ae7343ba08759db8efbb5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665827"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="9ba8b-103">Элемент PropertyName для элемента SelectionCondition для элемента EntrySelectedBy для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="9ba8b-103">PropertyName Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="9ba8b-104">Указывает свойство .NET, которое запускает условие.</span><span class="sxs-lookup"><span data-stu-id="9ba8b-104">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="9ba8b-105">При наличии этого свойства или при его вычислении `true` условие выполняется, и используется запись списка.</span><span class="sxs-lookup"><span data-stu-id="9ba8b-105">When this property is present or when it evaluates to `true`, the condition is met, and the list entry is used.</span></span>

<span data-ttu-id="9ba8b-106">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ListControl элемент (Format) Листентриес элемент (Format) Листентри элемент (Format) Ентриселектедби для листентри (Format) Селектионкондитион для EntrySelectedBy в ListEntry для SelectionCondition в EntrySelectedBy (Format)</span><span class="sxs-lookup"><span data-stu-id="9ba8b-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9ba8b-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9ba8b-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9ba8b-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9ba8b-108">Attributes and Elements</span></span>

<span data-ttu-id="9ba8b-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `PropertyName` элемента.</span><span class="sxs-lookup"><span data-stu-id="9ba8b-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9ba8b-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9ba8b-110">Attributes</span></span>

<span data-ttu-id="9ba8b-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="9ba8b-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9ba8b-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9ba8b-112">Child Elements</span></span>

<span data-ttu-id="9ba8b-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="9ba8b-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="9ba8b-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9ba8b-114">Parent Elements</span></span>

|<span data-ttu-id="9ba8b-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="9ba8b-115">Element</span></span>|<span data-ttu-id="9ba8b-116">Описание</span><span class="sxs-lookup"><span data-stu-id="9ba8b-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9ba8b-117">Элемент Селектионкондитион для Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="9ba8b-117">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="9ba8b-118">Определяет условие, которое должно существовать для использования этой записи списка.</span><span class="sxs-lookup"><span data-stu-id="9ba8b-118">Defines the condition that must exist for this list entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="9ba8b-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="9ba8b-119">Text Value</span></span>

<span data-ttu-id="9ba8b-120">Укажите имя свойства .NET.</span><span class="sxs-lookup"><span data-stu-id="9ba8b-120">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="9ba8b-121">Комментарии</span><span class="sxs-lookup"><span data-stu-id="9ba8b-121">Remarks</span></span>

<span data-ttu-id="9ba8b-122">Условие выбора должно указывать по крайней мере одно имя свойства или блок скрипта, но не может одновременно указывать оба значения.</span><span class="sxs-lookup"><span data-stu-id="9ba8b-122">The selection condition must specify at least one property name or a script block, but cannot specify both.</span></span> <span data-ttu-id="9ba8b-123">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для, когда используется запись или элемент представления](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="9ba8b-123">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="9ba8b-124">Дополнительные сведения о других компонентах представления списка см. в разделе [Создание представления списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="9ba8b-124">For more information about other components of a list view, see [Creating List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9ba8b-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="9ba8b-125">See Also</span></span>

[<span data-ttu-id="9ba8b-126">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="9ba8b-126">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="9ba8b-127">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="9ba8b-127">Defining Conditions for When Data is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="9ba8b-128">Элемент Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="9ba8b-128">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="9ba8b-129">Элемент ScriptBlock для Селектионкондитион для Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="9ba8b-129">ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="9ba8b-130">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="9ba8b-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
