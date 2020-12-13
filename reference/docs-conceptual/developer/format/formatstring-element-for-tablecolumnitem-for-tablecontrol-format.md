---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент FormatString для элемента TableColumnItem для элемента TableControl (формат)
description: Элемент FormatString для элемента TableColumnItem для элемента TableControl (формат)
ms.openlocfilehash: 3d386e61ac321c05e0b298019c2298f76b391b21
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667901"
---
# <a name="formatstring-element-for-tablecolumnitem-for-tablecontrol-format"></a><span data-ttu-id="35784-103">Элемент FormatString для элемента TableColumnItem для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="35784-103">FormatString Element for TableColumnItem for TableControl (Format)</span></span>

<span data-ttu-id="35784-104">Задает шаблон формата, определяющий способ отображения значения свойства или скрипта таблицы.</span><span class="sxs-lookup"><span data-stu-id="35784-104">Specifies a format pattern that defines how the property or script value of the table is displayed.</span></span>

<span data-ttu-id="35784-105">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Таблеконтрол элемент (Format) Таблеровентриес элемент (Format) Таблеровентри элемент (Format) Таблеколумнитемс элемент (Format) Таблеколумнитем элемент (формат) элемент FormatString для TableColumnItem (Format)</span><span class="sxs-lookup"><span data-stu-id="35784-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) TableColumnItems Element (Format) TableColumnItem Element (Format) FormatString Element for TableColumnItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="35784-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="35784-106">Syntax</span></span>

```xml
<FormatString>FormatPattern</FormatString>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="35784-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="35784-107">Attributes and Elements</span></span>

<span data-ttu-id="35784-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `FormatString` элемента.</span><span class="sxs-lookup"><span data-stu-id="35784-108">The following sections describe attributes, child elements, and the parent element of the `FormatString` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="35784-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="35784-109">Attributes</span></span>

<span data-ttu-id="35784-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="35784-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="35784-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="35784-111">Child Elements</span></span>

<span data-ttu-id="35784-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="35784-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="35784-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="35784-113">Parent Elements</span></span>

|<span data-ttu-id="35784-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="35784-114">Element</span></span>|<span data-ttu-id="35784-115">Описание</span><span class="sxs-lookup"><span data-stu-id="35784-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="35784-116">Элемент Таблеколумнитем (Format)</span><span class="sxs-lookup"><span data-stu-id="35784-116">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|<span data-ttu-id="35784-117">Определяет свойство или скрипт, значение которого отображается в столбце строки.</span><span class="sxs-lookup"><span data-stu-id="35784-117">Defines the property or script whose value is displayed in the column of the row.</span></span>|

## <a name="text-value"></a><span data-ttu-id="35784-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="35784-118">Text Value</span></span>

<span data-ttu-id="35784-119">Укажите шаблон, используемый для форматирования данных.</span><span class="sxs-lookup"><span data-stu-id="35784-119">Specify the pattern that is used to format the data.</span></span> <span data-ttu-id="35784-120">Например, этот шаблон можно использовать для форматирования значения любого свойства типа [System. TimeSpan](/dotnet/api/System.TimeSpan): {0: MMM} {0: DD} {0: HH}: {0: mm}.</span><span class="sxs-lookup"><span data-stu-id="35784-120">For example, this pattern can be used to format the value of any property that is of type [System.Timespan](/dotnet/api/System.TimeSpan): {0:MMM}{0:dd}{0:HH}:{0:mm}.</span></span>

## <a name="remarks"></a><span data-ttu-id="35784-121">Комментарии</span><span class="sxs-lookup"><span data-stu-id="35784-121">Remarks</span></span>

<span data-ttu-id="35784-122">Строки формата можно использовать при создании табличных представлений, представлений списков, расширенных представлений или пользовательских представлений.</span><span class="sxs-lookup"><span data-stu-id="35784-122">Format strings can be used when creating table views, list views, wide views, or custom views.</span></span> <span data-ttu-id="35784-123">Дополнительные сведения о форматировании значения, отображаемого в представлении, см. в разделе [Форматирование отображаемых данных](./formatting-displayed-data.md).</span><span class="sxs-lookup"><span data-stu-id="35784-123">For more information about formatting a value displayed in a view, see [Formatting Displayed Data](./formatting-displayed-data.md).</span></span>

<span data-ttu-id="35784-124">Дополнительные сведения о компонентах табличного представления см. в разделе [табличное представление](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="35784-124">For more information about the components of a table view, see [Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="35784-125">Пример</span><span class="sxs-lookup"><span data-stu-id="35784-125">Example</span></span>

<span data-ttu-id="35784-126">В следующем примере показано, как определить строку форматирования для значения `StartTime` Свойства.</span><span class="sxs-lookup"><span data-stu-id="35784-126">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<TableColumnItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</TableColumnItem>
```

## <a name="see-also"></a><span data-ttu-id="35784-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="35784-127">See Also</span></span>

[<span data-ttu-id="35784-128">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="35784-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="35784-129">Форматирование отображаемых данных</span><span class="sxs-lookup"><span data-stu-id="35784-129">Formatting Displayed Data</span></span>](./formatting-displayed-data.md)

[<span data-ttu-id="35784-130">Элемент Таблеколумнитем (Format)</span><span class="sxs-lookup"><span data-stu-id="35784-130">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[<span data-ttu-id="35784-131">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="35784-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
