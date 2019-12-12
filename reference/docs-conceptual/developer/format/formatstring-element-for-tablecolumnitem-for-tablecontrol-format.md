---
title: Элемент FormatString для Таблеколумнитем для Таблеконтрол (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8a150731-d4b4-4d63-8db5-f14d463c8c37
caps.latest.revision: 13
ms.openlocfilehash: b7e1d0adc43254141056a729e1c1cc9699b6ac9b
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363713"
---
# <a name="formatstring-element-for-tablecolumnitem-for-tablecontrol-format"></a><span data-ttu-id="41be3-102">Элемент FormatString для элемента TableColumnItem для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="41be3-102">FormatString Element for TableColumnItem for TableControl (Format)</span></span>

<span data-ttu-id="41be3-103">Задает шаблон формата, определяющий способ отображения значения свойства или скрипта таблицы.</span><span class="sxs-lookup"><span data-stu-id="41be3-103">Specifies a format pattern that defines how the property or script value of the table is displayed.</span></span>

<span data-ttu-id="41be3-104">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Таблеконтрол элемент (Format) Таблеровентриес элемент (Format) Таблеровентри элемент (Format) Таблеколумнитемс элемент (Format) Таблеколумнитем элемент (Format) Элемент FormatString для Таблеколумнитем (Format)</span><span class="sxs-lookup"><span data-stu-id="41be3-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) TableColumnItems Element (Format) TableColumnItem Element (Format) FormatString Element for TableColumnItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="41be3-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="41be3-105">Syntax</span></span>

```xml
<FormatString>FormatPattern</FormatString>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="41be3-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="41be3-106">Attributes and Elements</span></span>

<span data-ttu-id="41be3-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `FormatString`.</span><span class="sxs-lookup"><span data-stu-id="41be3-107">The following sections describe attributes, child elements, and the parent element of the `FormatString` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="41be3-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="41be3-108">Attributes</span></span>

<span data-ttu-id="41be3-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="41be3-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="41be3-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="41be3-110">Child Elements</span></span>

<span data-ttu-id="41be3-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="41be3-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="41be3-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="41be3-112">Parent Elements</span></span>

|<span data-ttu-id="41be3-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="41be3-113">Element</span></span>|<span data-ttu-id="41be3-114">Описание</span><span class="sxs-lookup"><span data-stu-id="41be3-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="41be3-115">Элемент Таблеколумнитем (Format)</span><span class="sxs-lookup"><span data-stu-id="41be3-115">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|<span data-ttu-id="41be3-116">Определяет свойство или скрипт, значение которого отображается в столбце строки.</span><span class="sxs-lookup"><span data-stu-id="41be3-116">Defines the property or script whose value is displayed in the column of the row.</span></span>|

## <a name="text-value"></a><span data-ttu-id="41be3-117">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="41be3-117">Text Value</span></span>

<span data-ttu-id="41be3-118">Укажите шаблон, используемый для форматирования данных.</span><span class="sxs-lookup"><span data-stu-id="41be3-118">Specify the pattern that is used to format the data.</span></span> <span data-ttu-id="41be3-119">Например, этот шаблон можно использовать для форматирования значения любого свойства типа [System. TimeSpan](/dotnet/api/System.TimeSpan): {0: MMM} {0: DD} {0: HH}: {0: mm}.</span><span class="sxs-lookup"><span data-stu-id="41be3-119">For example, this pattern can be used to format the value of any property that is of type [System.Timespan](/dotnet/api/System.TimeSpan): {0:MMM}{0:dd}{0:HH}:{0:mm}.</span></span>

## <a name="remarks"></a><span data-ttu-id="41be3-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="41be3-120">Remarks</span></span>

<span data-ttu-id="41be3-121">Строки формата можно использовать при создании табличных представлений, представлений списков, расширенных представлений или пользовательских представлений.</span><span class="sxs-lookup"><span data-stu-id="41be3-121">Format strings can be used when creating table views, list views, wide views, or custom views.</span></span> <span data-ttu-id="41be3-122">Дополнительные сведения о форматировании значения, отображаемого в представлении, см. в разделе [Форматирование отображаемых данных](./formatting-displayed-data.md).</span><span class="sxs-lookup"><span data-stu-id="41be3-122">For more information about formatting a value displayed in a view, see [Formatting Displayed Data](./formatting-displayed-data.md).</span></span>

<span data-ttu-id="41be3-123">Дополнительные сведения о компонентах табличного представления см. в разделе [табличное представление](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="41be3-123">For more information about the components of a table view, see [Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="41be3-124">Пример</span><span class="sxs-lookup"><span data-stu-id="41be3-124">Example</span></span>

<span data-ttu-id="41be3-125">В следующем примере показано, как определить строку форматирования для значения свойства `StartTime`.</span><span class="sxs-lookup"><span data-stu-id="41be3-125">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<TableColumnItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</TableColumnItem>
```

## <a name="see-also"></a><span data-ttu-id="41be3-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="41be3-126">See Also</span></span>

[<span data-ttu-id="41be3-127">Создание табличного представления</span><span class="sxs-lookup"><span data-stu-id="41be3-127">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="41be3-128">Форматирование отображаемых данных</span><span class="sxs-lookup"><span data-stu-id="41be3-128">Formatting Displayed Data</span></span>](./formatting-displayed-data.md)

[<span data-ttu-id="41be3-129">Элемент Таблеколумнитем (Format)</span><span class="sxs-lookup"><span data-stu-id="41be3-129">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[<span data-ttu-id="41be3-130">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="41be3-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
