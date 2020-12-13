---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент ScriptBlock для элемента SelectionCondition для элемента EntrySelectedBy для элемента ListControl (формат)
description: Элемент ScriptBlock для элемента SelectionCondition для элемента EntrySelectedBy для элемента ListControl (формат)
ms.openlocfilehash: ec7691358d0ff3758411317a349221e1704a1895
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659904"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="f405b-103">Элемент ScriptBlock для элемента SelectionCondition для элемента EntrySelectedBy для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="f405b-103">ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="f405b-104">Указывает скрипт, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="f405b-104">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="f405b-105">При вычислении этого скрипта выполняется `true` условие, и используется запись списка.</span><span class="sxs-lookup"><span data-stu-id="f405b-105">When this script is evaluated to `true`, the condition is met, and the list entry is used.</span></span>

<span data-ttu-id="f405b-106">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ListControl элемент (Format) Листентриес элемент (Format) Листентри элемент (Format) Ентриселектедби для Листентри (Format) Селектионкондитион для EntrySelectedBy в ListEntry для SelectionCondition в EntrySelectedBy (Format)</span><span class="sxs-lookup"><span data-stu-id="f405b-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f405b-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f405b-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f405b-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f405b-108">Attributes and Elements</span></span>

<span data-ttu-id="f405b-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ScriptBlock` элемента.</span><span class="sxs-lookup"><span data-stu-id="f405b-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f405b-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f405b-110">Attributes</span></span>

<span data-ttu-id="f405b-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f405b-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f405b-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f405b-112">Child Elements</span></span>

<span data-ttu-id="f405b-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f405b-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f405b-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f405b-114">Parent Elements</span></span>

|<span data-ttu-id="f405b-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="f405b-115">Element</span></span>|<span data-ttu-id="f405b-116">Описание</span><span class="sxs-lookup"><span data-stu-id="f405b-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f405b-117">Элемент Селектионкондитион для Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="f405b-117">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="f405b-118">Определяет условие, которое должно существовать для использования этой записи списка.</span><span class="sxs-lookup"><span data-stu-id="f405b-118">Defines the condition that must exist for this list entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f405b-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="f405b-119">Text Value</span></span>

<span data-ttu-id="f405b-120">Укажите оцениваемый скрипт.</span><span class="sxs-lookup"><span data-stu-id="f405b-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="f405b-121">Комментарии</span><span class="sxs-lookup"><span data-stu-id="f405b-121">Remarks</span></span>

<span data-ttu-id="f405b-122">Условие выбора должно указывать по крайней мере один имя скрипта или свойства для вычисления, но не может одновременно указывать оба значения.</span><span class="sxs-lookup"><span data-stu-id="f405b-122">The selection condition must specify a least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="f405b-123">(Дополнительные сведения о том, как можно использовать условия выбора, см. в разделе [Определение условий для использования записи или элемента представления](./defining-conditions-for-displaying-data.md).)</span><span class="sxs-lookup"><span data-stu-id="f405b-123">(For more information about how selection conditions can be used, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).)</span></span>

<span data-ttu-id="f405b-124">Дополнительные сведения о других компонентах представления списка см. в разделе [представление списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="f405b-124">For more information about the other components of a list view, see [List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f405b-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="f405b-125">See Also</span></span>

[<span data-ttu-id="f405b-126">Элемент Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="f405b-126">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="f405b-127">Элемент PropertyName для Селектионкондитион для Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="f405b-127">PropertyName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="f405b-128">Элемент Селектионкондитион для Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="f405b-128">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="f405b-129">Представление списка</span><span class="sxs-lookup"><span data-stu-id="f405b-129">List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="f405b-130">Определение условий для использования записи или элемента представления</span><span class="sxs-lookup"><span data-stu-id="f405b-130">Defining Conditions for when a View Entry or Item is Used</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="f405b-131">Создание файла форматирования и типов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f405b-131">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
