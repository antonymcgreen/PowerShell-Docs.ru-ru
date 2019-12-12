---
title: Элемент ScriptBlock для Селектионкондитион для Ентриселектедби для ListControl (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4a1adad7-e864-4892-9d26-a6476a9698d2
caps.latest.revision: 7
ms.openlocfilehash: b65d953169f6daf15fb617ce4d0303cf4cb584ee
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368593"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="21807-102">Элемент ScriptBlock для элемента SelectionCondition для элемента EntrySelectedBy для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="21807-102">ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="21807-103">Указывает скрипт, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="21807-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="21807-104">При вычислении этого скрипта на `true`условие выполняется, и используется запись списка.</span><span class="sxs-lookup"><span data-stu-id="21807-104">When this script is evaluated to `true`, the condition is met, and the list entry is used.</span></span>

<span data-ttu-id="21807-105">Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) ListControl элемент (Format) Листентриес элемент (Format) Листентри элемент (Format) Ентриселектедби для Листентри (Format) Селектионкондитион элемент для Ентриселектедби для Листентри (Format) элемент ScriptBlock для Селектионкондитион для Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="21807-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="21807-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="21807-106">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="21807-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="21807-107">Attributes and Elements</span></span>

<span data-ttu-id="21807-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `ScriptBlock`.</span><span class="sxs-lookup"><span data-stu-id="21807-108">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="21807-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="21807-109">Attributes</span></span>

<span data-ttu-id="21807-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="21807-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="21807-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="21807-111">Child Elements</span></span>

<span data-ttu-id="21807-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="21807-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="21807-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="21807-113">Parent Elements</span></span>

|<span data-ttu-id="21807-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="21807-114">Element</span></span>|<span data-ttu-id="21807-115">Описание</span><span class="sxs-lookup"><span data-stu-id="21807-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="21807-116">Элемент Селектионкондитион для Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="21807-116">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="21807-117">Определяет условие, которое должно существовать для использования этой записи списка.</span><span class="sxs-lookup"><span data-stu-id="21807-117">Defines the condition that must exist for this list entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="21807-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="21807-118">Text Value</span></span>

<span data-ttu-id="21807-119">Укажите оцениваемый скрипт.</span><span class="sxs-lookup"><span data-stu-id="21807-119">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="21807-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="21807-120">Remarks</span></span>

<span data-ttu-id="21807-121">Условие выбора должно указывать по крайней мере один имя скрипта или свойства для вычисления, но не может одновременно указывать оба значения.</span><span class="sxs-lookup"><span data-stu-id="21807-121">The selection condition must specify a least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="21807-122">(Дополнительные сведения о том, как можно использовать условия выбора, см. в разделе [Определение условий для использования записи или элемента представления](./defining-conditions-for-displaying-data.md).)</span><span class="sxs-lookup"><span data-stu-id="21807-122">(For more information about how selection conditions can be used, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).)</span></span>

<span data-ttu-id="21807-123">Дополнительные сведения о других компонентах представления списка см. в разделе [представление списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="21807-123">For more information about the other components of a list view, see [List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="21807-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="21807-124">See Also</span></span>

[<span data-ttu-id="21807-125">Элемент Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="21807-125">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="21807-126">Элемент PropertyName для Селектионкондитион для Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="21807-126">PropertyName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="21807-127">Элемент Селектионкондитион для Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="21807-127">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="21807-128">Представление списка</span><span class="sxs-lookup"><span data-stu-id="21807-128">List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="21807-129">Определение условий для использования записи или элемента представления</span><span class="sxs-lookup"><span data-stu-id="21807-129">Defining Conditions for when a View Entry or Item is Used</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="21807-130">Создание файла форматирования и типов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="21807-130">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
