---
title: Элемент Селектионсетнаме для Селектионкондитион для ошибка customcontrol для представления (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a52b05a9-762e-4f1c-ad57-9d1710149722
caps.latest.revision: 10
ms.openlocfilehash: 25d46665ca5df3ddf49af5718d513b84c77988c8
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368273"
---
# <a name="selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format"></a><span data-ttu-id="ad175-102">Элемент SelectionSetName для элемента SelectionCondition для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="ad175-102">SelectionSetName Element for SelectionCondition for CustomControl for View (Format)</span></span>

<span data-ttu-id="ad175-103">Указывает набор типов .NET, которые активируют условие.</span><span class="sxs-lookup"><span data-stu-id="ad175-103">Specifies the set of .NET types that trigger the condition.</span></span> <span data-ttu-id="ad175-104">При наличии любого из типов в этом наборе условие выполняется, и объект отображается с помощью этого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ad175-104">When any of the types in this set are present, the condition is met and the object is displayed using this control.</span></span> <span data-ttu-id="ad175-105">Этот элемент используется при определении пользовательского представления элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ad175-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="ad175-106">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ошибка customcontrol элемент (Format) Кустоментриес для ошибка customcontrol для элемента представления (Format) Кустоментри для Кустоментриес для представления (Format) Ентриселектедби Элемент для Кустоментри представления (Format)</span><span class="sxs-lookup"><span data-stu-id="ad175-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Element for CustomEntry for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ad175-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ad175-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ad175-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ad175-108">Attributes and Elements</span></span>

<span data-ttu-id="ad175-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `SelectionSetName`.</span><span class="sxs-lookup"><span data-stu-id="ad175-109">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ad175-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ad175-110">Attributes</span></span>

<span data-ttu-id="ad175-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="ad175-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ad175-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ad175-112">Child Elements</span></span>

<span data-ttu-id="ad175-113">Нет.</span><span class="sxs-lookup"><span data-stu-id="ad175-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ad175-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ad175-114">Parent Elements</span></span>

|<span data-ttu-id="ad175-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="ad175-115">Element</span></span>|<span data-ttu-id="ad175-116">Описание</span><span class="sxs-lookup"><span data-stu-id="ad175-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ad175-117">Элемент Селектионкондитион для Ентриселектедби для ошибка customcontrol для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="ad175-117">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|<span data-ttu-id="ad175-118">Определяет условие, которое должно существовать для использования определения элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ad175-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="ad175-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="ad175-119">Text Value</span></span>

<span data-ttu-id="ad175-120">Укажите имя набора выбора.</span><span class="sxs-lookup"><span data-stu-id="ad175-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="ad175-121">Замечания</span><span class="sxs-lookup"><span data-stu-id="ad175-121">Remarks</span></span>

<span data-ttu-id="ad175-122">Наборы выбора — это распространенные группы объектов .NET, которые могут использоваться любым представлением, определяемым файлом форматирования.</span><span class="sxs-lookup"><span data-stu-id="ad175-122">Selection sets are common groups of .NET objects that can be used by any view that the formatting file defines.</span></span> <span data-ttu-id="ad175-123">Дополнительные сведения о создании и ссылке на наборы выбора см. в разделе [Определение наборов объектов](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="ad175-123">For more information about creating and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

<span data-ttu-id="ad175-124">Условие выбора может указывать набор выбора или тип .NET, но не может одновременно указывать оба значения.</span><span class="sxs-lookup"><span data-stu-id="ad175-124">The selection condition can specify a selection set or .NET type, but cannot specify both.</span></span> <span data-ttu-id="ad175-125">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="ad175-125">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ad175-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="ad175-126">See Also</span></span>

[<span data-ttu-id="ad175-127">Элемент Селектионкондитион для Ентриселектедби для ошибка customcontrol для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="ad175-127">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[<span data-ttu-id="ad175-128">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="ad175-128">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="ad175-129">Определение наборов выбора</span><span class="sxs-lookup"><span data-stu-id="ad175-129">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="ad175-130">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="ad175-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
