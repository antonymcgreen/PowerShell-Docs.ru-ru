---
title: Элемент ScriptBlock для Селектионкондитион для Ентриселектедби для Таблеконтрол (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: a23d3515749393e9f5a2053634a44d1a817ebf38
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783455"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="7d73c-102">Элемент ScriptBlock для элемента SelectionCondition для элемента EntrySelectedBy для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="7d73c-102">ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="7d73c-103">Указывает блок скрипта, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="7d73c-103">Specifies the script block that triggers the condition.</span></span> <span data-ttu-id="7d73c-104">При вычислении этого скрипта `true` выполняется условие, и используется запись в таблице.</span><span class="sxs-lookup"><span data-stu-id="7d73c-104">When this script is evaluated to `true`, the condition is met, and the table entry is used.</span></span>

<span data-ttu-id="7d73c-105">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Таблеконтрол элемент (Format) Таблеровентриес элемент (Format) Таблеровентри элемент (Format) Ентриселектедби для Таблеровентри (Format) SelectionCondition для EntrySelectedBy в TableRowEntry для SelectionCondition в EntrySelectedBy (Format)</span><span class="sxs-lookup"><span data-stu-id="7d73c-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7d73c-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7d73c-106">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7d73c-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7d73c-107">Attributes and Elements</span></span>

<span data-ttu-id="7d73c-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ScriptBlock` элемента.</span><span class="sxs-lookup"><span data-stu-id="7d73c-108">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="7d73c-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7d73c-109">Attributes</span></span>

<span data-ttu-id="7d73c-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="7d73c-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7d73c-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7d73c-111">Child Elements</span></span>

<span data-ttu-id="7d73c-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="7d73c-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7d73c-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7d73c-113">Parent Elements</span></span>

|<span data-ttu-id="7d73c-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="7d73c-114">Element</span></span>|<span data-ttu-id="7d73c-115">Описание</span><span class="sxs-lookup"><span data-stu-id="7d73c-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7d73c-116">Элемент Селектионкондитион для Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="7d73c-116">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="7d73c-117">Определяет условие, которое должно существовать для использования этой записи таблицы.</span><span class="sxs-lookup"><span data-stu-id="7d73c-117">Defines the condition that must exist for this table entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="7d73c-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="7d73c-118">Text Value</span></span>

<span data-ttu-id="7d73c-119">Укажите оцениваемый скрипт.</span><span class="sxs-lookup"><span data-stu-id="7d73c-119">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="7d73c-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="7d73c-120">Remarks</span></span>

<span data-ttu-id="7d73c-121">Условие выбора должно указывать по крайней мере один блок скрипта или имя свойства, но не может одновременно указывать оба значения.</span><span class="sxs-lookup"><span data-stu-id="7d73c-121">The selection condition must specify at least one script block or property name, but cannot specify both.</span></span> <span data-ttu-id="7d73c-122">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для, когда используется запись или элемент представления](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="7d73c-122">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="7d73c-123">Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="7d73c-123">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7d73c-124">См. также</span><span class="sxs-lookup"><span data-stu-id="7d73c-124">See Also</span></span>

[<span data-ttu-id="7d73c-125">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="7d73c-125">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="7d73c-126">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="7d73c-126">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="7d73c-127">Элемент PropertyName для элемента SelectionCondition для элемента EntrySelectedBy для элемента TableRowEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="7d73c-127">PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)

[<span data-ttu-id="7d73c-128">Элемент Селектионкондитион для Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="7d73c-128">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="7d73c-129">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="7d73c-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
