---
title: Элемент PropertyName для Селектионкондитион для Ентриселектедби для Таблеровентри (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: bec8377fb13b8f288196a809e7aa4e7f46c66e31
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785546"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format"></a><span data-ttu-id="c16cc-102">Элемент PropertyName для элемента SelectionCondition для элемента EntrySelectedBy для элемента TableRowEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="c16cc-102">PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>

<span data-ttu-id="c16cc-103">Указывает свойство .NET, которое запускает условие.</span><span class="sxs-lookup"><span data-stu-id="c16cc-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="c16cc-104">Если это свойство имеется или если оно имеет значение `true` , условие выполняется и используется запись таблицы.</span><span class="sxs-lookup"><span data-stu-id="c16cc-104">When this property is present or when it evaluates to `true`, the condition is met, and the table entry is used.</span></span>

<span data-ttu-id="c16cc-105">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Таблеконтрол элемент (Format) Таблеровентриес элемент (Format) Таблеровентри элемент (Format) Ентриселектедби для таблеровентри (Format) SelectionCondition для EntrySelectedBy в TableRowEntry для SelectionCondition в EntrySelectedBy (Format)</span><span class="sxs-lookup"><span data-stu-id="c16cc-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c16cc-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c16cc-106">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c16cc-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c16cc-107">Attributes and Elements</span></span>

<span data-ttu-id="c16cc-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `PropertyName` элемента.</span><span class="sxs-lookup"><span data-stu-id="c16cc-108">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="c16cc-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c16cc-109">Attributes</span></span>

<span data-ttu-id="c16cc-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="c16cc-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c16cc-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c16cc-111">Child Elements</span></span>

<span data-ttu-id="c16cc-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="c16cc-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="c16cc-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c16cc-113">Parent Elements</span></span>

|<span data-ttu-id="c16cc-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="c16cc-114">Element</span></span>|<span data-ttu-id="c16cc-115">Описание</span><span class="sxs-lookup"><span data-stu-id="c16cc-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c16cc-116">Элемент Селектионкондитион для Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="c16cc-116">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="c16cc-117">Определяет условие, которое должно существовать для использования этой записи таблицы.</span><span class="sxs-lookup"><span data-stu-id="c16cc-117">Defines the condition that must exist for this table entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="c16cc-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="c16cc-118">Text Value</span></span>

<span data-ttu-id="c16cc-119">Укажите имя свойства .NET.</span><span class="sxs-lookup"><span data-stu-id="c16cc-119">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="c16cc-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="c16cc-120">Remarks</span></span>

<span data-ttu-id="c16cc-121">Условие выбора должно указывать по крайней мере одно имя свойства или блок скрипта, но не может одновременно указывать оба значения.</span><span class="sxs-lookup"><span data-stu-id="c16cc-121">The selection condition must specify at least one property name or a script block, but cannot specify both.</span></span> <span data-ttu-id="c16cc-122">Дополнительные сведения о том, как можно использовать условия выбора, см. в разделе [Определение условий для, когда используется запись или элемент представления](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="c16cc-122">For more information about how selection conditions can be used, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="c16cc-123">Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="c16cc-123">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c16cc-124">См. также</span><span class="sxs-lookup"><span data-stu-id="c16cc-124">See Also</span></span>

[<span data-ttu-id="c16cc-125">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="c16cc-125">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="c16cc-126">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="c16cc-126">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="c16cc-127">Элемент ScriptBlock для Селектионкондитион для Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="c16cc-127">ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="c16cc-128">Элемент Селектионкондитион для Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="c16cc-128">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="c16cc-129">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="c16cc-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
