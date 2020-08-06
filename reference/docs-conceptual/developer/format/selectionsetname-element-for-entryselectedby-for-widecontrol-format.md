---
title: Элемент Селектионсетнаме для Ентриселектедби для Видеконтрол (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 546225b0619ebec83d04a7e27bbc298ffef0a14d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785257"
---
# <a name="selectionsetname-element-for-entryselectedby-for-widecontrol-format"></a><span data-ttu-id="0f628-102">Элемент SelectionSetName для элемента EntrySelectedBy для элемента WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="0f628-102">SelectionSetName Element for EntrySelectedBy for WideControl (Format)</span></span>

<span data-ttu-id="0f628-103">Задает набор объектов .NET для определения.</span><span class="sxs-lookup"><span data-stu-id="0f628-103">Specifies a set of .NET objects for the definition.</span></span> <span data-ttu-id="0f628-104">Определение используется при каждом отображении одного из этих объектов.</span><span class="sxs-lookup"><span data-stu-id="0f628-104">The definition is used whenever one of these objects is displayed.</span></span>

<span data-ttu-id="0f628-105">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Видеконтрол элемент (Format) Видинтриес элемент (Format) Видинтри элемент (Format) Ентриселектедби для видинтри (Format) Селектионсетнаме для EntrySelectedBy в WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="0f628-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionSetName Element for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="0f628-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0f628-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="0f628-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0f628-107">Attributes and Elements</span></span>

<span data-ttu-id="0f628-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `SelectionSetName` элемента.</span><span class="sxs-lookup"><span data-stu-id="0f628-108">The following sections describe the attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="0f628-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0f628-109">Attributes</span></span>

<span data-ttu-id="0f628-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0f628-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="0f628-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0f628-111">Child Elements</span></span>

<span data-ttu-id="0f628-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0f628-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="0f628-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0f628-113">Parent Elements</span></span>

|<span data-ttu-id="0f628-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="0f628-114">Element</span></span>|<span data-ttu-id="0f628-115">Описание</span><span class="sxs-lookup"><span data-stu-id="0f628-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0f628-116">Элемент EntrySelectedBy для элемента WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="0f628-116">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)|<span data-ttu-id="0f628-117">Определяет типы .NET, которые используют эту расширенную запись или условие, которое должно существовать для использования этой записи.</span><span class="sxs-lookup"><span data-stu-id="0f628-117">Defines the .NET types that use this wide entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="0f628-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="0f628-118">Text Value</span></span>

<span data-ttu-id="0f628-119">Укажите имя набора выбора.</span><span class="sxs-lookup"><span data-stu-id="0f628-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="0f628-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="0f628-120">Remarks</span></span>

<span data-ttu-id="0f628-121">Каждое определение должно содержать одно имя типа, набор выбора или условие выбора.</span><span class="sxs-lookup"><span data-stu-id="0f628-121">Each definition must specify one type name, selection set, or selection condition.</span></span>

<span data-ttu-id="0f628-122">Наборы выбора обычно используются, если требуется определить группу объектов, используемых в нескольких представлениях.</span><span class="sxs-lookup"><span data-stu-id="0f628-122">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="0f628-123">Например, может потребоваться создать табличное представление и представление списка для одного и того же набора объектов.</span><span class="sxs-lookup"><span data-stu-id="0f628-123">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="0f628-124">Дополнительные сведения об определении наборов выбора см. [в разделе Определение наборов объектов для представления](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="0f628-124">For more information about defining selection sets, see [Defining Sets of Objects for a View](./defining-selection-sets.md).</span></span>

<span data-ttu-id="0f628-125">Дополнительные сведения о других компонентах расширенного представления см. [в разделе Создание расширенного представления](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="0f628-125">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0f628-126">См. также</span><span class="sxs-lookup"><span data-stu-id="0f628-126">See Also</span></span>

[<span data-ttu-id="0f628-127">Создание широкого представления</span><span class="sxs-lookup"><span data-stu-id="0f628-127">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="0f628-128">Определение наборов выделенных фрагментов</span><span class="sxs-lookup"><span data-stu-id="0f628-128">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="0f628-129">Элемент EntrySelectedBy для элемента WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="0f628-129">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)

[<span data-ttu-id="0f628-130">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="0f628-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
