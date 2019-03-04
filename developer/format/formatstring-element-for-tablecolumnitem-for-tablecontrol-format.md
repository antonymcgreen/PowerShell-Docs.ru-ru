---
title: Элемент FormatString для TableColumnItem для TableControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8a150731-d4b4-4d63-8db5-f14d463c8c37
caps.latest.revision: 13
ms.openlocfilehash: b7e1d0adc43254141056a729e1c1cc9699b6ac9b
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854330"
---
# <a name="formatstring-element-for-tablecolumnitem-for-tablecontrol-format"></a><span data-ttu-id="860ab-102">Элемент FormatString для элемента TableColumnItem для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="860ab-102">FormatString Element for TableColumnItem for TableControl (Format)</span></span>

<span data-ttu-id="860ab-103">Задает шаблон формата, который определяет способ отображения значения свойства или скрипт таблицы.</span><span class="sxs-lookup"><span data-stu-id="860ab-103">Specifies a format pattern that defines how the property or script value of the table is displayed.</span></span>

<span data-ttu-id="860ab-104">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) TableControl-элемент (формат) элемент TableRowEntries (формат) элемент TableRowEntry (формат) элемент TableColumnItems (формат) TableColumnItem элемент конфигурации (формат) Элемент FormatString для TableColumnItem (формат)</span><span class="sxs-lookup"><span data-stu-id="860ab-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) TableColumnItems Element (Format) TableColumnItem Element (Format) FormatString Element for TableColumnItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="860ab-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="860ab-105">Syntax</span></span>

```xml
<FormatString>FormatPattern</FormatString>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="860ab-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="860ab-106">Attributes and Elements</span></span>

<span data-ttu-id="860ab-107">Ниже описаны атрибуты, дочерние элементы и родительский элемент `FormatString` элемент.</span><span class="sxs-lookup"><span data-stu-id="860ab-107">The following sections describe attributes, child elements, and the parent element of the `FormatString` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="860ab-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="860ab-108">Attributes</span></span>

<span data-ttu-id="860ab-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="860ab-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="860ab-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="860ab-110">Child Elements</span></span>

<span data-ttu-id="860ab-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="860ab-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="860ab-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="860ab-112">Parent Elements</span></span>

|<span data-ttu-id="860ab-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="860ab-113">Element</span></span>|<span data-ttu-id="860ab-114">Описание</span><span class="sxs-lookup"><span data-stu-id="860ab-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="860ab-115">Элемент TableColumnItem (формат)</span><span class="sxs-lookup"><span data-stu-id="860ab-115">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|<span data-ttu-id="860ab-116">Определяет свойство или скрипта, значение которого отображается в столбце строки.</span><span class="sxs-lookup"><span data-stu-id="860ab-116">Defines the property or script whose value is displayed in the column of the row.</span></span>|

## <a name="text-value"></a><span data-ttu-id="860ab-117">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="860ab-117">Text Value</span></span>

<span data-ttu-id="860ab-118">Укажите шаблон, используемый для форматирования данных.</span><span class="sxs-lookup"><span data-stu-id="860ab-118">Specify the pattern that is used to format the data.</span></span> <span data-ttu-id="860ab-119">Например, этот шаблон можно использовать для форматирования значения любого свойства, который относится к типу [System.Timespan](/dotnet/api/System.TimeSpan): {0: MMM} {0:dd} {0:HH}: {0: mm}.</span><span class="sxs-lookup"><span data-stu-id="860ab-119">For example, this pattern can be used to format the value of any property that is of type [System.Timespan](/dotnet/api/System.TimeSpan): {0:MMM}{0:dd}{0:HH}:{0:mm}.</span></span>

## <a name="remarks"></a><span data-ttu-id="860ab-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="860ab-120">Remarks</span></span>

<span data-ttu-id="860ab-121">Строки формата может использоваться при создании представления таблиц, представлений списков, широкие представления или представления.</span><span class="sxs-lookup"><span data-stu-id="860ab-121">Format strings can be used when creating table views, list views, wide views, or custom views.</span></span> <span data-ttu-id="860ab-122">Дополнительные сведения о форматировании значения, отображаемого в представлении см. в разделе [форматирования отображаемых данных](./formatting-displayed-data.md).</span><span class="sxs-lookup"><span data-stu-id="860ab-122">For more information about formatting a value displayed in a view, see [Formatting Displayed Data](./formatting-displayed-data.md).</span></span>

<span data-ttu-id="860ab-123">Дополнительные сведения о компонентах в табличное представление, см. в разделе [табличное представление](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="860ab-123">For more information about the components of a table view, see [Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="860ab-124">Пример</span><span class="sxs-lookup"><span data-stu-id="860ab-124">Example</span></span>

<span data-ttu-id="860ab-125">Приведенный ниже показано, как определить строку форматирования для значения `StartTime` свойство.</span><span class="sxs-lookup"><span data-stu-id="860ab-125">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<TableColumnItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</TableColumnItem>
```

## <a name="see-also"></a><span data-ttu-id="860ab-126">См. также</span><span class="sxs-lookup"><span data-stu-id="860ab-126">See Also</span></span>

[<span data-ttu-id="860ab-127">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="860ab-127">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="860ab-128">Форматирование отображаемых данных</span><span class="sxs-lookup"><span data-stu-id="860ab-128">Formatting Displayed Data</span></span>](./formatting-displayed-data.md)

[<span data-ttu-id="860ab-129">Элемент TableColumnItem (формат)</span><span class="sxs-lookup"><span data-stu-id="860ab-129">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[<span data-ttu-id="860ab-130">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="860ab-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
