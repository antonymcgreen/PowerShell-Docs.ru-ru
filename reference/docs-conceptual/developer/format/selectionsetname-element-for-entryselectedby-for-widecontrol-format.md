---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент SelectionSetName для элемента EntrySelectedBy для элемента WideControl (формат)
description: Элемент SelectionSetName для элемента EntrySelectedBy для элемента WideControl (формат)
ms.openlocfilehash: bf6a44bb733421f36a9140d0ec10e61aedfbda6a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651699"
---
# <a name="selectionsetname-element-for-entryselectedby-for-widecontrol-format"></a><span data-ttu-id="78c5a-103">Элемент SelectionSetName для элемента EntrySelectedBy для элемента WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="78c5a-103">SelectionSetName Element for EntrySelectedBy for WideControl (Format)</span></span>

<span data-ttu-id="78c5a-104">Задает набор объектов .NET для определения.</span><span class="sxs-lookup"><span data-stu-id="78c5a-104">Specifies a set of .NET objects for the definition.</span></span> <span data-ttu-id="78c5a-105">Определение используется при каждом отображении одного из этих объектов.</span><span class="sxs-lookup"><span data-stu-id="78c5a-105">The definition is used whenever one of these objects is displayed.</span></span>

<span data-ttu-id="78c5a-106">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Видеконтрол элемент (Format) Видинтриес элемент (Format) Видинтри элемент (Format) Ентриселектедби для видинтри (Format) Селектионсетнаме для EntrySelectedBy в WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="78c5a-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionSetName Element for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="78c5a-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="78c5a-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="78c5a-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="78c5a-108">Attributes and Elements</span></span>

<span data-ttu-id="78c5a-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `SelectionSetName` элемента.</span><span class="sxs-lookup"><span data-stu-id="78c5a-109">The following sections describe the attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="78c5a-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="78c5a-110">Attributes</span></span>

<span data-ttu-id="78c5a-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="78c5a-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="78c5a-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="78c5a-112">Child Elements</span></span>

<span data-ttu-id="78c5a-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="78c5a-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="78c5a-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="78c5a-114">Parent Elements</span></span>

|<span data-ttu-id="78c5a-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="78c5a-115">Element</span></span>|<span data-ttu-id="78c5a-116">Описание</span><span class="sxs-lookup"><span data-stu-id="78c5a-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="78c5a-117">Элемент EntrySelectedBy для элемента WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="78c5a-117">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)|<span data-ttu-id="78c5a-118">Определяет типы .NET, которые используют эту расширенную запись или условие, которое должно существовать для использования этой записи.</span><span class="sxs-lookup"><span data-stu-id="78c5a-118">Defines the .NET types that use this wide entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="78c5a-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="78c5a-119">Text Value</span></span>

<span data-ttu-id="78c5a-120">Укажите имя набора выбора.</span><span class="sxs-lookup"><span data-stu-id="78c5a-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="78c5a-121">Комментарии</span><span class="sxs-lookup"><span data-stu-id="78c5a-121">Remarks</span></span>

<span data-ttu-id="78c5a-122">Каждое определение должно содержать одно имя типа, набор выбора или условие выбора.</span><span class="sxs-lookup"><span data-stu-id="78c5a-122">Each definition must specify one type name, selection set, or selection condition.</span></span>

<span data-ttu-id="78c5a-123">Наборы выбора обычно используются, если требуется определить группу объектов, используемых в нескольких представлениях.</span><span class="sxs-lookup"><span data-stu-id="78c5a-123">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="78c5a-124">Например, может потребоваться создать табличное представление и представление списка для одного и того же набора объектов.</span><span class="sxs-lookup"><span data-stu-id="78c5a-124">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="78c5a-125">Дополнительные сведения об определении наборов выбора см. [в разделе Определение наборов объектов для представления](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="78c5a-125">For more information about defining selection sets, see [Defining Sets of Objects for a View](./defining-selection-sets.md).</span></span>

<span data-ttu-id="78c5a-126">Дополнительные сведения о других компонентах расширенного представления см. [в разделе Создание расширенного представления](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="78c5a-126">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="78c5a-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="78c5a-127">See Also</span></span>

[<span data-ttu-id="78c5a-128">Создание широкого представления</span><span class="sxs-lookup"><span data-stu-id="78c5a-128">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="78c5a-129">Определение наборов выделенных фрагментов</span><span class="sxs-lookup"><span data-stu-id="78c5a-129">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="78c5a-130">Элемент EntrySelectedBy для элемента WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="78c5a-130">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)

[<span data-ttu-id="78c5a-131">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="78c5a-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
