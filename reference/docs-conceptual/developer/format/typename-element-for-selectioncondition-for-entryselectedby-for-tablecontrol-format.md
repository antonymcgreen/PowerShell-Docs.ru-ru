---
title: Элемент TypeName для Селектионкондитион для Ентриселектедби для Таблеконтрол (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: b9367f0ea659b9dce8fe200a5a08873d53bc03a8
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772592"
---
# <a name="typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="50f00-102">Элемент TypeName для элемента SelectionCondition для элемента EntrySelectedBy для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="50f00-102">TypeName Element for SelectionCondition for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="50f00-103">Указывает тип .NET, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="50f00-103">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="50f00-104">При наличии этого типа условие выполняется, и используется строка таблицы.</span><span class="sxs-lookup"><span data-stu-id="50f00-104">When this type is present, the condition is met, and the table row is used.</span></span>

<span data-ttu-id="50f00-105">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Таблеконтрол элемент (Format) Таблеровентриес элемент (Format) Таблеровентри элемент (Format) Ентриселектедби для таблеровентри (Format) SelectionCondition для EntrySelectedBy в TableRowEntry для SelectionCondition (Format).</span><span class="sxs-lookup"><span data-stu-id="50f00-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format) TypeName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="50f00-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="50f00-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="50f00-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="50f00-107">Attributes and Elements</span></span>

<span data-ttu-id="50f00-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `TypeName` элемента.</span><span class="sxs-lookup"><span data-stu-id="50f00-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="50f00-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="50f00-109">Attributes</span></span>

<span data-ttu-id="50f00-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="50f00-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="50f00-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="50f00-111">Child Elements</span></span>

<span data-ttu-id="50f00-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="50f00-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="50f00-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="50f00-113">Parent Elements</span></span>

|<span data-ttu-id="50f00-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="50f00-114">Element</span></span>|<span data-ttu-id="50f00-115">Описание</span><span class="sxs-lookup"><span data-stu-id="50f00-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="50f00-116">Элемент Селектионкондитион для Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="50f00-116">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="50f00-117">Определяет условие, которое должно существовать для использования этой строки таблицы.</span><span class="sxs-lookup"><span data-stu-id="50f00-117">Defines the condition that must exist for this table row to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="50f00-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="50f00-118">Text Value</span></span>

<span data-ttu-id="50f00-119">Укажите полное имя типа .NET, например `System.IO.DirectoryInfo` .</span><span class="sxs-lookup"><span data-stu-id="50f00-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="50f00-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="50f00-120">Remarks</span></span>

<span data-ttu-id="50f00-121">Условие выбора может указывать любое количество типов .NET или наборов выбора, но не может одновременно указывать оба типа.</span><span class="sxs-lookup"><span data-stu-id="50f00-121">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span> <span data-ttu-id="50f00-122">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для, когда используется запись или элемент представления](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="50f00-122">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="50f00-123">Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="50f00-123">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="50f00-124">См. также</span><span class="sxs-lookup"><span data-stu-id="50f00-124">See Also</span></span>

[<span data-ttu-id="50f00-125">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="50f00-125">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="50f00-126">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="50f00-126">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="50f00-127">Элемент Селектионкондитион для Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="50f00-127">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="50f00-128">Элемент Селектионсетнаме для Селектионкондитион для Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="50f00-128">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="50f00-129">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="50f00-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
