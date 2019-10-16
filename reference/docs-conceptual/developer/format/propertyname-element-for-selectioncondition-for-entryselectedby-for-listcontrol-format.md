---
title: Элемент PropertyName для Селектионкондитион для Ентриселектедби для ListControl (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 71c3f1f6-6fe2-42f1-8260-6974d3871748
caps.latest.revision: 11
ms.openlocfilehash: 7d526372cf80327b3fb9b79b6e83429c57780183
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362293"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="ed414-102">Элемент PropertyName для элемента SelectionCondition для элемента EntrySelectedBy для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="ed414-102">PropertyName Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="ed414-103">Указывает свойство .NET, которое запускает условие.</span><span class="sxs-lookup"><span data-stu-id="ed414-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="ed414-104">Если это свойство имеется или если оно имеет значение `true`, условие выполняется, и используется запись списка.</span><span class="sxs-lookup"><span data-stu-id="ed414-104">When this property is present or when it evaluates to `true`, the condition is met, and the list entry is used.</span></span>

<span data-ttu-id="ed414-105">Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) ListControl элемент (Format) Листентриес элемент (Format) Листентри элемент (Format) Ентриселектедби для Листентри (Format) Селектионкондитион элемент для Ентриселектедби для Листентри (Format) PropertyName элемент для Селектионкондитион для Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="ed414-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ed414-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ed414-106">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ed414-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ed414-107">Attributes and Elements</span></span>

<span data-ttu-id="ed414-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `PropertyName`.</span><span class="sxs-lookup"><span data-stu-id="ed414-108">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ed414-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ed414-109">Attributes</span></span>

<span data-ttu-id="ed414-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="ed414-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ed414-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ed414-111">Child Elements</span></span>

<span data-ttu-id="ed414-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="ed414-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ed414-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ed414-113">Parent Elements</span></span>

|<span data-ttu-id="ed414-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="ed414-114">Element</span></span>|<span data-ttu-id="ed414-115">Описание</span><span class="sxs-lookup"><span data-stu-id="ed414-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ed414-116">Элемент Селектионкондитион для Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="ed414-116">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="ed414-117">Определяет условие, которое должно существовать для использования этой записи списка.</span><span class="sxs-lookup"><span data-stu-id="ed414-117">Defines the condition that must exist for this list entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="ed414-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="ed414-118">Text Value</span></span>

<span data-ttu-id="ed414-119">Укажите имя свойства .NET.</span><span class="sxs-lookup"><span data-stu-id="ed414-119">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="ed414-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="ed414-120">Remarks</span></span>

<span data-ttu-id="ed414-121">Условие выбора должно указывать по крайней мере одно имя свойства или блок скрипта, но не может одновременно указывать оба значения.</span><span class="sxs-lookup"><span data-stu-id="ed414-121">The selection condition must specify at least one property name or a script block, but cannot specify both.</span></span> <span data-ttu-id="ed414-122">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для, когда используется запись или элемент представления](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="ed414-122">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="ed414-123">Дополнительные сведения о других компонентах представления списка см. в разделе [Создание представления списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="ed414-123">For more information about other components of a list view, see [Creating List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ed414-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="ed414-124">See Also</span></span>

[<span data-ttu-id="ed414-125">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="ed414-125">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="ed414-126">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="ed414-126">Defining Conditions for When Data is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="ed414-127">Элемент Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="ed414-127">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="ed414-128">Элемент ScriptBlock для Селектионкондитион для Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="ed414-128">ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="ed414-129">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="ed414-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
