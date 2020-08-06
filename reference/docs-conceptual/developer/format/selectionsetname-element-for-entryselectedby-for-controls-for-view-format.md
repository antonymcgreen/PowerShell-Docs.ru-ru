---
title: Элемент Селектионсетнаме для Ентриселектедби элементов управления для представления (формат) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 5c762a626fff746266919d1f7fcb991a8cdbcdf2
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787552"
---
# <a name="selectionsetname-element-for-entryselectedby-for-controls-for-view-format"></a><span data-ttu-id="13940-102">Элемент SelectionSetName для элемента EntrySelectedBy для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="13940-102">SelectionSetName Element for EntrySelectedBy for Controls for View (Format)</span></span>

<span data-ttu-id="13940-103">Задает набор типов .NET, использующих это определение элемента управления.</span><span class="sxs-lookup"><span data-stu-id="13940-103">Specifies a set of .NET types that use this definition of the control.</span></span> <span data-ttu-id="13940-104">Этот элемент используется при определении элементов управления, которые могут использоваться представлением.</span><span class="sxs-lookup"><span data-stu-id="13940-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="13940-105">Элемент Configuration (Format) Виевдефинитионс элемент (формат) элемент представления (Format) управляет управляющий элемент (Format) элемент управления для элементов управления представления (Format) ошибка customcontrol для элементов управления элемента Кустоментриес представления (Format) для ошибка customcontrol для элементов управления для элемента Кустоментри представления (Format) Кустоментриес для элементов управления для представления (Format) Ентриселектедби элемента для Кустоментри для элементов управления для представления (Format) SelectionSetName в EntrySelectedBy для элементов управления представления (формат)</span><span class="sxs-lookup"><span data-stu-id="13940-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format) SelectionSetName Element for EntrySelectedBy for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="13940-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="13940-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="13940-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="13940-107">Attributes and Elements</span></span>

<span data-ttu-id="13940-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `SelectionSetName` элемента.</span><span class="sxs-lookup"><span data-stu-id="13940-108">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="13940-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="13940-109">Attributes</span></span>

<span data-ttu-id="13940-110">Нет</span><span class="sxs-lookup"><span data-stu-id="13940-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="13940-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="13940-111">Child Elements</span></span>

<span data-ttu-id="13940-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="13940-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="13940-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="13940-113">Parent Elements</span></span>

|<span data-ttu-id="13940-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="13940-114">Element</span></span>|<span data-ttu-id="13940-115">Описание</span><span class="sxs-lookup"><span data-stu-id="13940-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="13940-116">Элемент EntrySelectedBy для элемента CustomEntry для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="13940-116">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="13940-117">Определяет типы .NET, которые используют это определение элемента управления или условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="13940-117">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="13940-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="13940-118">Text Value</span></span>

<span data-ttu-id="13940-119">Укажите имя набора выбора.</span><span class="sxs-lookup"><span data-stu-id="13940-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="13940-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="13940-120">Remarks</span></span>

<span data-ttu-id="13940-121">Для каждого определения элемента управления должно быть определено по крайней мере одно имя типа, набор выбора или условие выбора.</span><span class="sxs-lookup"><span data-stu-id="13940-121">Each control definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="13940-122">Наборы выбора обычно используются, если требуется определить группу объектов, используемых в нескольких представлениях.</span><span class="sxs-lookup"><span data-stu-id="13940-122">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="13940-123">Дополнительные сведения об определении наборов выбора см. в разделе [Определение наборов выбора](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="13940-123">For more information about defining selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="13940-124">См. также</span><span class="sxs-lookup"><span data-stu-id="13940-124">See Also</span></span>

[<span data-ttu-id="13940-125">Элемент EntrySelectedBy для элемента CustomEntry для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="13940-125">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)

[<span data-ttu-id="13940-126">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="13940-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
