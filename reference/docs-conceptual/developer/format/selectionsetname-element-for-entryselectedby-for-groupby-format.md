---
title: Элемент Селектионсетнаме для Ентриселектедби для GroupBy (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 362f7844c09a52494387a62e329adfb309767427
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785291"
---
# <a name="selectionsetname-element-for-entryselectedby-for-groupby-format"></a><span data-ttu-id="f16a8-102">Элемент SelectionSetName для элемента EntrySelectedBy для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="f16a8-102">SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>

<span data-ttu-id="f16a8-103">Задает набор объектов .NET для записи списка.</span><span class="sxs-lookup"><span data-stu-id="f16a8-103">Specifies a set of .NET objects for the list entry.</span></span> <span data-ttu-id="f16a8-104">Количество наборов выбора, которые можно указать для записи, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="f16a8-104">There is no limit to the number of selection sets that can be specified for an entry.</span></span> <span data-ttu-id="f16a8-105">Этот элемент используется при определении того, как отображается новая группа объектов.</span><span class="sxs-lookup"><span data-stu-id="f16a8-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="f16a8-106">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент GroupBy для элемента "View" (Format) ошибка customcontrol для элемента GroupBy (Format) Кустоментриес для ошибка customcontrol for GroupBy (формат) кустоментри для ошибка customcontrol for GroupBy (формат) ентриселектедби для кустоментри for GroupBy (Format) селектионсетнаме для EntrySelectedBy for GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="f16a8-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f16a8-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f16a8-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f16a8-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f16a8-108">Attributes and Elements</span></span>

<span data-ttu-id="f16a8-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `SelectionSetName` элемента.</span><span class="sxs-lookup"><span data-stu-id="f16a8-109">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f16a8-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f16a8-110">Attributes</span></span>

<span data-ttu-id="f16a8-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f16a8-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f16a8-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f16a8-112">Child Elements</span></span>

<span data-ttu-id="f16a8-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f16a8-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f16a8-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f16a8-114">Parent Elements</span></span>

|<span data-ttu-id="f16a8-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="f16a8-115">Element</span></span>|<span data-ttu-id="f16a8-116">Описание</span><span class="sxs-lookup"><span data-stu-id="f16a8-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f16a8-117">Элемент EntrySelectedBy для элемента CustomEntry для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="f16a8-117">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="f16a8-118">Определяет типы .NET, которые используют эту настраиваемую запись, или условие, которое должно существовать для использования этой записи.</span><span class="sxs-lookup"><span data-stu-id="f16a8-118">Defines the .NET types that use this custom entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f16a8-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="f16a8-119">Text Value</span></span>

<span data-ttu-id="f16a8-120">Укажите имя набора выбора.</span><span class="sxs-lookup"><span data-stu-id="f16a8-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="f16a8-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="f16a8-121">Remarks</span></span>

<span data-ttu-id="f16a8-122">Для каждого определения пользовательского элемента управления должно быть определено по крайней мере одно имя типа, набор выбора или условие выбора.</span><span class="sxs-lookup"><span data-stu-id="f16a8-122">Each custom control definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="f16a8-123">Наборы выбора обычно используются, если требуется определить группу объектов, используемых в нескольких представлениях.</span><span class="sxs-lookup"><span data-stu-id="f16a8-123">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="f16a8-124">Например, может потребоваться создать табличное представление и представление списка для одного и того же набора объектов.</span><span class="sxs-lookup"><span data-stu-id="f16a8-124">For example, you may want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="f16a8-125">Дополнительные сведения об определении наборов выбора см. в разделе [Определение наборов выбора](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="f16a8-125">For more information about defining selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

<span data-ttu-id="f16a8-126">Дополнительные сведения о компонентах представления пользовательского элемента управления см. в разделе [Создание пользовательских элементов управления](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="f16a8-126">For more information about the components of a custom control view, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f16a8-127">См. также</span><span class="sxs-lookup"><span data-stu-id="f16a8-127">See Also</span></span>

[<span data-ttu-id="f16a8-128">Элемент EntrySelectedBy для элемента CustomEntry для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="f16a8-128">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="f16a8-129">Создание пользовательских элементов управления</span><span class="sxs-lookup"><span data-stu-id="f16a8-129">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="f16a8-130">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="f16a8-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
