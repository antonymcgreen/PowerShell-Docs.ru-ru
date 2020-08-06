---
title: Элемент Селектионсетнаме для Ентриселектедби для ошибка customcontrol для представления (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 3728a1886d5406b8fa4888125d1c031d0f9b1b03
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785308"
---
# <a name="selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format"></a><span data-ttu-id="aef86-102">Элемент SelectionSetName для элемента EntrySelectedBy для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="aef86-102">SelectionSetName Element for EntrySelectedBy for CustomControl for View (Format)</span></span>

<span data-ttu-id="aef86-103">Задает набор объектов .NET для записи списка.</span><span class="sxs-lookup"><span data-stu-id="aef86-103">Specifies a set of .NET objects for the list entry.</span></span> <span data-ttu-id="aef86-104">Количество наборов выбора, которые можно указать для записи, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="aef86-104">There is no limit to the number of selection sets that can be specified for an entry.</span></span>

<span data-ttu-id="aef86-105">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ошибка customcontrol элемент (Format) Кустоментриес для ошибка customcontrol для элемента кустоментри представления для кустоментриес для представления (Format) ентриселектедби для кустоментри для SelectionSetName for EntrySelectedBy (формат).</span><span class="sxs-lookup"><span data-stu-id="aef86-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Element for CustomEntry for View (Format) SelectionSetName Element for EntrySelectedBy for CustomEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="aef86-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aef86-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="aef86-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="aef86-107">Attributes and Elements</span></span>

<span data-ttu-id="aef86-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `SelectionSetName` элемента.</span><span class="sxs-lookup"><span data-stu-id="aef86-108">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="aef86-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="aef86-109">Attributes</span></span>

<span data-ttu-id="aef86-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="aef86-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="aef86-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="aef86-111">Child Elements</span></span>

<span data-ttu-id="aef86-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="aef86-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="aef86-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="aef86-113">Parent Elements</span></span>

|<span data-ttu-id="aef86-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="aef86-114">Element</span></span>|<span data-ttu-id="aef86-115">Описание</span><span class="sxs-lookup"><span data-stu-id="aef86-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="aef86-116">Элемент Ентриселектедби для Кустоментри для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="aef86-116">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="aef86-117">Определяет типы .NET, которые используют эту настраиваемую запись, или условие, которое должно существовать для использования этой записи.</span><span class="sxs-lookup"><span data-stu-id="aef86-117">Defines the .NET types that use this custom entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="aef86-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="aef86-118">Text Value</span></span>

<span data-ttu-id="aef86-119">Укажите имя набора выбора.</span><span class="sxs-lookup"><span data-stu-id="aef86-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="aef86-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="aef86-120">Remarks</span></span>

<span data-ttu-id="aef86-121">Для каждой записи пользовательского элемента управления должно быть определено по крайней мере одно имя типа, набор выбора или условие выбора.</span><span class="sxs-lookup"><span data-stu-id="aef86-121">Each custom control entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="aef86-122">Наборы выбора обычно используются, если требуется определить группу объектов, используемых в нескольких представлениях.</span><span class="sxs-lookup"><span data-stu-id="aef86-122">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="aef86-123">Например, может потребоваться создать табличное представление и представление списка для одного и того же набора объектов.</span><span class="sxs-lookup"><span data-stu-id="aef86-123">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="aef86-124">Дополнительные сведения об определении наборов выбора см. в разделе [Определение наборов выбора](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="aef86-124">For more information about defining selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

<span data-ttu-id="aef86-125">Дополнительные сведения о компонентах представления пользовательского элемента управления см. в разделе [Создание пользовательских элементов управления](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="aef86-125">For more information about the components of a custom control view, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="aef86-126">См. также</span><span class="sxs-lookup"><span data-stu-id="aef86-126">See Also</span></span>

[<span data-ttu-id="aef86-127">Элемент Ентриселектедби для Кустоментри для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="aef86-127">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="aef86-128">Представление пользовательского элемента управления</span><span class="sxs-lookup"><span data-stu-id="aef86-128">Custom Control View</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="aef86-129">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="aef86-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
