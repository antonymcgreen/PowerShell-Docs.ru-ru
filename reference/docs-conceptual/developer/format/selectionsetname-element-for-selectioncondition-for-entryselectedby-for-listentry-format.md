---
title: Элемент Селектионсетнаме для Селектионкондитион для Ентриселектедби для Листентри (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 3666888f149f176126d9a19bdbad62469ca9f064
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787484"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-listentry-format"></a><span data-ttu-id="72a07-102">Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента ListEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="72a07-102">SelectionSetName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

<span data-ttu-id="72a07-103">Указывает набор типов .NET, которые активируют условие.</span><span class="sxs-lookup"><span data-stu-id="72a07-103">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="72a07-104">При наличии любого из типов в этом наборе условие выполняется, и объект отображается с помощью этого определения представления списка.</span><span class="sxs-lookup"><span data-stu-id="72a07-104">When any of the types in this set are present, the condition is met, and the object is displayed by using this definition of the list view.</span></span>

<span data-ttu-id="72a07-105">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ListControl элемент (Format) Листентриес элемент (Format) Листентри элемент (Format) Ентриселектедби для листентри (Format) селектионкондитион для EntrySelectedBy для ListEntry в SelectionSetName для SelectionCondition (формат)</span><span class="sxs-lookup"><span data-stu-id="72a07-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format) SelectionSetName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="72a07-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="72a07-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="72a07-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="72a07-107">Attributes and Elements</span></span>

<span data-ttu-id="72a07-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `SelectionSetName` элемента.</span><span class="sxs-lookup"><span data-stu-id="72a07-108">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="72a07-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="72a07-109">Attributes</span></span>

<span data-ttu-id="72a07-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="72a07-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="72a07-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="72a07-111">Child Elements</span></span>

<span data-ttu-id="72a07-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="72a07-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="72a07-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="72a07-113">Parent Elements</span></span>

|<span data-ttu-id="72a07-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="72a07-114">Element</span></span>|<span data-ttu-id="72a07-115">Описание</span><span class="sxs-lookup"><span data-stu-id="72a07-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="72a07-116">Элемент Селектионкондитион для Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="72a07-116">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="72a07-117">Определяет условие, которое должно существовать для использования этого определения представления списка.</span><span class="sxs-lookup"><span data-stu-id="72a07-117">Defines the condition that must exist to use this definition of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="72a07-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="72a07-118">Text Value</span></span>

<span data-ttu-id="72a07-119">Укажите имя набора выбора.</span><span class="sxs-lookup"><span data-stu-id="72a07-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="72a07-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="72a07-120">Remarks</span></span>

<span data-ttu-id="72a07-121">Условие выбора может указывать набор выбора или тип .NET, но не может одновременно указывать оба значения.</span><span class="sxs-lookup"><span data-stu-id="72a07-121">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="72a07-122">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="72a07-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="72a07-123">Наборы выбора — это распространенные группы объектов .NET, которые могут использоваться любым представлением, определяемым файлом форматирования.</span><span class="sxs-lookup"><span data-stu-id="72a07-123">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="72a07-124">Дополнительные сведения о создании и ссылке на наборы выбора см. в разделе [Определение наборов объектов](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="72a07-124">For more information about creating and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

<span data-ttu-id="72a07-125">Дополнительные сведения о других компонентах представления списка см. в разделе [Создание представления списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="72a07-125">For more information about other components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="72a07-126">См. также</span><span class="sxs-lookup"><span data-stu-id="72a07-126">See Also</span></span>

[<span data-ttu-id="72a07-127">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="72a07-127">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="72a07-128">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="72a07-128">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="72a07-129">Элемент Селектионкондитион для Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="72a07-129">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="72a07-130">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="72a07-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
