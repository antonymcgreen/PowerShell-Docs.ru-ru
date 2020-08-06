---
title: Элемент Селектионсетнаме для Селектионкондитион для Ентриселектедби для Енумерабликспансион (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: e18c74bb95c658f2c3e7b7454628f78d523f7609
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787501"
---
# <a name="selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="2fdf1-102">Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="2fdf1-102">SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="2fdf1-103">Указывает набор типов .NET, которые активируют условие.</span><span class="sxs-lookup"><span data-stu-id="2fdf1-103">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="2fdf1-104">При наличии любого из типов в этом наборе условие будет выполнено.</span><span class="sxs-lookup"><span data-stu-id="2fdf1-104">When any of the types in this set are present, the condition is met.</span></span>

<span data-ttu-id="2fdf1-105">Элемент конфигурации Дефаултсеттингс элемент (Format) Енумерабликспансионс элемент (Format) Енумерабликспансионс элемент (Format) Ентриселектедби элемент для енумерабликспансион (Format) SelectionCondition для EntrySelectedBy для EnumerableExpansion (Format) SelectionSetName для SelectionCondition в EntrySelectedBy (Format)</span><span class="sxs-lookup"><span data-stu-id="2fdf1-105">Configuration Element DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansions Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format) SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2fdf1-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2fdf1-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2fdf1-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2fdf1-107">Attributes and Elements</span></span>

<span data-ttu-id="2fdf1-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `SelectionSetName` элемента.</span><span class="sxs-lookup"><span data-stu-id="2fdf1-108">The following sections describe attributes, child elements, and parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="2fdf1-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2fdf1-109">Attributes</span></span>

<span data-ttu-id="2fdf1-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="2fdf1-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2fdf1-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2fdf1-111">Child Elements</span></span>

<span data-ttu-id="2fdf1-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="2fdf1-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2fdf1-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2fdf1-113">Parent Elements</span></span>

|<span data-ttu-id="2fdf1-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="2fdf1-114">Element</span></span>|<span data-ttu-id="2fdf1-115">Описание</span><span class="sxs-lookup"><span data-stu-id="2fdf1-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2fdf1-116">Элемент SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="2fdf1-116">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="2fdf1-117">Определяет условие, которое должно существовать для расширения объектов коллекции этого определения.</span><span class="sxs-lookup"><span data-stu-id="2fdf1-117">Defines the condition that must exist to expand the collection objects of this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="2fdf1-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="2fdf1-118">Text Value</span></span>

<span data-ttu-id="2fdf1-119">Укажите имя набора выбора.</span><span class="sxs-lookup"><span data-stu-id="2fdf1-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="2fdf1-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="2fdf1-120">Remarks</span></span>

<span data-ttu-id="2fdf1-121">Условие выбора может указывать набор выбора или тип .NET, но не может одновременно указывать оба значения.</span><span class="sxs-lookup"><span data-stu-id="2fdf1-121">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="2fdf1-122">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="2fdf1-122">For more information about how to use selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="2fdf1-123">Наборы выбора — это распространенные группы объектов .NET, которые могут использоваться любым представлением, определяемым файлом форматирования.</span><span class="sxs-lookup"><span data-stu-id="2fdf1-123">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="2fdf1-124">Дополнительные сведения о создании и ссылке на наборы выбора см. в разделе [Определение наборов выбора](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="2fdf1-124">For more information about creating and referencing selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2fdf1-125">См. также</span><span class="sxs-lookup"><span data-stu-id="2fdf1-125">See Also</span></span>

[<span data-ttu-id="2fdf1-126">Определение наборов выделенных фрагментов</span><span class="sxs-lookup"><span data-stu-id="2fdf1-126">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="2fdf1-127">Элемент SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="2fdf1-127">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="2fdf1-128">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="2fdf1-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
