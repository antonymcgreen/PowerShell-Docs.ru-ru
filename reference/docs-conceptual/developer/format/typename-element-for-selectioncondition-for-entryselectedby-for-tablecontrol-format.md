---
title: Элемент TypeName для Селектионкондитион для Ентриселектедби для Таблеконтрол (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e97d56fb-4e35-447a-9282-26f10d0a4609
caps.latest.revision: 11
ms.openlocfilehash: fe65ac95cead7df0069ffdae666fb34b7309fbb6
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361473"
---
# <a name="typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="e8215-102">Элемент TypeName для элемента SelectionCondition для элемента EntrySelectedBy для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="e8215-102">TypeName Element for SelectionCondition for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="e8215-103">Указывает тип .NET, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="e8215-103">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="e8215-104">При наличии этого типа условие выполняется, и используется строка таблицы.</span><span class="sxs-lookup"><span data-stu-id="e8215-104">When this type is present, the condition is met, and the table row is used.</span></span>

<span data-ttu-id="e8215-105">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Таблеконтрол элемент (Format) Таблеровентриес элемент (Format) Таблеровентри элемент (Format) Ентриселектедби для Таблеровентри (Format) Элемент Селектионкондитион для Ентриселектедби для элемента TypeName Таблеровентри (Format) для Селектионкондитион для Ентриселектедби в TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="e8215-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format) TypeName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e8215-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e8215-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e8215-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e8215-107">Attributes and Elements</span></span>

<span data-ttu-id="e8215-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `TypeName`.</span><span class="sxs-lookup"><span data-stu-id="e8215-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e8215-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e8215-109">Attributes</span></span>

<span data-ttu-id="e8215-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="e8215-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e8215-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e8215-111">Child Elements</span></span>

<span data-ttu-id="e8215-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="e8215-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e8215-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e8215-113">Parent Elements</span></span>

|<span data-ttu-id="e8215-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="e8215-114">Element</span></span>|<span data-ttu-id="e8215-115">Описание</span><span class="sxs-lookup"><span data-stu-id="e8215-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e8215-116">Элемент Селектионкондитион для Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="e8215-116">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="e8215-117">Определяет условие, которое должно существовать для использования этой строки таблицы.</span><span class="sxs-lookup"><span data-stu-id="e8215-117">Defines the condition that must exist for this table row to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="e8215-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="e8215-118">Text Value</span></span>

<span data-ttu-id="e8215-119">Укажите полное имя типа .NET, например `System.IO.DirectoryInfo`.</span><span class="sxs-lookup"><span data-stu-id="e8215-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="e8215-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="e8215-120">Remarks</span></span>

<span data-ttu-id="e8215-121">Условие выбора может указывать любое количество типов .NET или наборов выбора, но не может одновременно указывать оба типа.</span><span class="sxs-lookup"><span data-stu-id="e8215-121">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span> <span data-ttu-id="e8215-122">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для, когда используется запись или элемент представления](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="e8215-122">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="e8215-123">Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="e8215-123">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e8215-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="e8215-124">See Also</span></span>

[<span data-ttu-id="e8215-125">Создание табличного представления</span><span class="sxs-lookup"><span data-stu-id="e8215-125">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="e8215-126">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="e8215-126">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="e8215-127">Элемент Селектионкондитион для Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="e8215-127">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="e8215-128">Элемент Селектионсетнаме для Селектионкондитион для Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="e8215-128">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="e8215-129">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="e8215-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
