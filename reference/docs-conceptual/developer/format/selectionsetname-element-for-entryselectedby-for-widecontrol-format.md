---
title: Элемент Селектионсетнаме для Ентриселектедби для Видеконтрол (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c9c6e18f-6cca-465c-bd20-3969e7897a96
caps.latest.revision: 10
ms.openlocfilehash: 6b6a4a4647412d11d947f1dc4ea12d1e05ff536e
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361983"
---
# <a name="selectionsetname-element-for-entryselectedby-for-widecontrol-format"></a><span data-ttu-id="4cefa-102">Элемент SelectionSetName для элемента EntrySelectedBy для элемента WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="4cefa-102">SelectionSetName Element for EntrySelectedBy for WideControl (Format)</span></span>

<span data-ttu-id="4cefa-103">Задает набор объектов .NET для определения.</span><span class="sxs-lookup"><span data-stu-id="4cefa-103">Specifies a set of .NET objects for the definition.</span></span> <span data-ttu-id="4cefa-104">Определение используется при каждом отображении одного из этих объектов.</span><span class="sxs-lookup"><span data-stu-id="4cefa-104">The definition is used whenever one of these objects is displayed.</span></span>

<span data-ttu-id="4cefa-105">Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) Видеконтрол элемент (Format) Видинтриес элемент (Format) Видинтри элемент (Format) Ентриселектедби для Видинтри (Format) Селектионсетнаме элемент для Ентриселектедби для Видинтри (формат)</span><span class="sxs-lookup"><span data-stu-id="4cefa-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionSetName Element for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4cefa-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4cefa-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="4cefa-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4cefa-107">Attributes and Elements</span></span>

<span data-ttu-id="4cefa-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `SelectionSetName`.</span><span class="sxs-lookup"><span data-stu-id="4cefa-108">The following sections describe the attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="4cefa-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4cefa-109">Attributes</span></span>

<span data-ttu-id="4cefa-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="4cefa-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4cefa-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4cefa-111">Child Elements</span></span>

<span data-ttu-id="4cefa-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="4cefa-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="4cefa-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4cefa-113">Parent Elements</span></span>

|<span data-ttu-id="4cefa-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="4cefa-114">Element</span></span>|<span data-ttu-id="4cefa-115">Описание</span><span class="sxs-lookup"><span data-stu-id="4cefa-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4cefa-116">Элемент Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="4cefa-116">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)|<span data-ttu-id="4cefa-117">Определяет типы .NET, которые используют эту расширенную запись или условие, которое должно существовать для использования этой записи.</span><span class="sxs-lookup"><span data-stu-id="4cefa-117">Defines the .NET types that use this wide entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="4cefa-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="4cefa-118">Text Value</span></span>

<span data-ttu-id="4cefa-119">Укажите имя набора выбора.</span><span class="sxs-lookup"><span data-stu-id="4cefa-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="4cefa-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="4cefa-120">Remarks</span></span>

<span data-ttu-id="4cefa-121">Каждое определение должно содержать одно имя типа, набор выбора или условие выбора.</span><span class="sxs-lookup"><span data-stu-id="4cefa-121">Each definition must specify one type name, selection set, or selection condition.</span></span>

<span data-ttu-id="4cefa-122">Наборы выбора обычно используются, если требуется определить группу объектов, используемых в нескольких представлениях.</span><span class="sxs-lookup"><span data-stu-id="4cefa-122">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="4cefa-123">Например, может потребоваться создать табличное представление и представление списка для одного и того же набора объектов.</span><span class="sxs-lookup"><span data-stu-id="4cefa-123">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="4cefa-124">Дополнительные сведения об определении наборов выбора см. [в разделе Определение наборов объектов для представления](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="4cefa-124">For more information about defining selection sets, see [Defining Sets of Objects for a View](./defining-selection-sets.md).</span></span>

<span data-ttu-id="4cefa-125">Дополнительные сведения о других компонентах расширенного представления см. [в разделе Создание расширенного представления](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="4cefa-125">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4cefa-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="4cefa-126">See Also</span></span>

[<span data-ttu-id="4cefa-127">Создание расширенного представления</span><span class="sxs-lookup"><span data-stu-id="4cefa-127">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="4cefa-128">Определение наборов выбора</span><span class="sxs-lookup"><span data-stu-id="4cefa-128">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="4cefa-129">Элемент Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="4cefa-129">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)

[<span data-ttu-id="4cefa-130">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="4cefa-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
