---
title: Элемент SelectionSetName для EntrySelectedBy для WideControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c9c6e18f-6cca-465c-bd20-3969e7897a96
caps.latest.revision: 10
ms.openlocfilehash: 6b6a4a4647412d11d947f1dc4ea12d1e05ff536e
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856800"
---
# <a name="selectionsetname-element-for-entryselectedby-for-widecontrol-format"></a><span data-ttu-id="8c446-102">Элемент SelectionSetName для элемента EntrySelectedBy для элемента WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="8c446-102">SelectionSetName Element for EntrySelectedBy for WideControl (Format)</span></span>

<span data-ttu-id="8c446-103">Задает набор объектов .NET, для определения.</span><span class="sxs-lookup"><span data-stu-id="8c446-103">Specifies a set of .NET objects for the definition.</span></span> <span data-ttu-id="8c446-104">Определение используется в том случае, когда отображается одно из этих объектов.</span><span class="sxs-lookup"><span data-stu-id="8c446-104">The definition is used whenever one of these objects is displayed.</span></span>

<span data-ttu-id="8c446-105">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) элемент WideControl (формат) элемент WideEntries (формат) элемент WideEntry (формат) EntrySelectedBy элемент конфигурации для элемент SelectionSetName WideEntry (формат) для EntrySelectedBy для WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="8c446-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionSetName Element for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="8c446-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8c446-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="8c446-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8c446-107">Attributes and Elements</span></span>

<span data-ttu-id="8c446-108">В следующих разделах атрибуты, дочерние элементы и родительский элемент `SelectionSetName` элемент.</span><span class="sxs-lookup"><span data-stu-id="8c446-108">The following sections describe the attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="8c446-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8c446-109">Attributes</span></span>

<span data-ttu-id="8c446-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="8c446-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8c446-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8c446-111">Child Elements</span></span>

<span data-ttu-id="8c446-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="8c446-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="8c446-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8c446-113">Parent Elements</span></span>

|<span data-ttu-id="8c446-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="8c446-114">Element</span></span>|<span data-ttu-id="8c446-115">Описание</span><span class="sxs-lookup"><span data-stu-id="8c446-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8c446-116">Элемент EntrySelectedBy для WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="8c446-116">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)|<span data-ttu-id="8c446-117">Определяет типы .NET, использующих эту запись широкий или условие, которое должен существовать для данной записи для использования.</span><span class="sxs-lookup"><span data-stu-id="8c446-117">Defines the .NET types that use this wide entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="8c446-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="8c446-118">Text Value</span></span>

<span data-ttu-id="8c446-119">Укажите имя набора выбора.</span><span class="sxs-lookup"><span data-stu-id="8c446-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="8c446-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="8c446-120">Remarks</span></span>

<span data-ttu-id="8c446-121">Каждое определение необходимо указать одно имя типа, выбора или условию выбора.</span><span class="sxs-lookup"><span data-stu-id="8c446-121">Each definition must specify one type name, selection set, or selection condition.</span></span>

<span data-ttu-id="8c446-122">Выбор наборов обычно используются, когда необходимо определить группу объектов, которые используются в нескольких представлениях.</span><span class="sxs-lookup"><span data-stu-id="8c446-122">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="8c446-123">Например можно создать представление таблицы и представления списка для одного набора объектов.</span><span class="sxs-lookup"><span data-stu-id="8c446-123">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="8c446-124">Дополнительные сведения об определении наборов выбора см. в разделе [определение задает объектов для представления](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="8c446-124">For more information about defining selection sets, see [Defining Sets of Objects for a View](./defining-selection-sets.md).</span></span>

<span data-ttu-id="8c446-125">Дополнительные сведения о других компонентах широкое представление, см. в разделе [Создание широкое представление](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="8c446-125">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8c446-126">См. также</span><span class="sxs-lookup"><span data-stu-id="8c446-126">See Also</span></span>

[<span data-ttu-id="8c446-127">Создание широкое представление</span><span class="sxs-lookup"><span data-stu-id="8c446-127">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="8c446-128">Определение наборов Выбор</span><span class="sxs-lookup"><span data-stu-id="8c446-128">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="8c446-129">Элемент EntrySelectedBy для WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="8c446-129">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)

[<span data-ttu-id="8c446-130">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="8c446-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
