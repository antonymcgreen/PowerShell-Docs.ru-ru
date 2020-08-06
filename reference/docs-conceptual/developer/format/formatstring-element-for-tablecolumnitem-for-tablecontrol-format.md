---
title: Элемент FormatString для Таблеколумнитем для Таблеконтрол (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 848583e697d0ab7bd5b017c14c47aba3c51a3c17
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781551"
---
# <a name="formatstring-element-for-tablecolumnitem-for-tablecontrol-format"></a><span data-ttu-id="dcafe-102">Элемент FormatString для элемента TableColumnItem для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="dcafe-102">FormatString Element for TableColumnItem for TableControl (Format)</span></span>

<span data-ttu-id="dcafe-103">Задает шаблон формата, определяющий способ отображения значения свойства или скрипта таблицы.</span><span class="sxs-lookup"><span data-stu-id="dcafe-103">Specifies a format pattern that defines how the property or script value of the table is displayed.</span></span>

<span data-ttu-id="dcafe-104">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Таблеконтрол элемент (Format) Таблеровентриес элемент (Format) Таблеровентри элемент (Format) Таблеколумнитемс элемент (Format) Таблеколумнитем элемент (формат) элемент FormatString для TableColumnItem (Format)</span><span class="sxs-lookup"><span data-stu-id="dcafe-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) TableColumnItems Element (Format) TableColumnItem Element (Format) FormatString Element for TableColumnItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="dcafe-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dcafe-105">Syntax</span></span>

```xml
<FormatString>FormatPattern</FormatString>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="dcafe-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="dcafe-106">Attributes and Elements</span></span>

<span data-ttu-id="dcafe-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `FormatString` элемента.</span><span class="sxs-lookup"><span data-stu-id="dcafe-107">The following sections describe attributes, child elements, and the parent element of the `FormatString` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="dcafe-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="dcafe-108">Attributes</span></span>

<span data-ttu-id="dcafe-109">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="dcafe-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="dcafe-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="dcafe-110">Child Elements</span></span>

<span data-ttu-id="dcafe-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="dcafe-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="dcafe-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="dcafe-112">Parent Elements</span></span>

|<span data-ttu-id="dcafe-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="dcafe-113">Element</span></span>|<span data-ttu-id="dcafe-114">Описание</span><span class="sxs-lookup"><span data-stu-id="dcafe-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="dcafe-115">Элемент Таблеколумнитем (Format)</span><span class="sxs-lookup"><span data-stu-id="dcafe-115">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|<span data-ttu-id="dcafe-116">Определяет свойство или скрипт, значение которого отображается в столбце строки.</span><span class="sxs-lookup"><span data-stu-id="dcafe-116">Defines the property or script whose value is displayed in the column of the row.</span></span>|

## <a name="text-value"></a><span data-ttu-id="dcafe-117">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="dcafe-117">Text Value</span></span>

<span data-ttu-id="dcafe-118">Укажите шаблон, используемый для форматирования данных.</span><span class="sxs-lookup"><span data-stu-id="dcafe-118">Specify the pattern that is used to format the data.</span></span> <span data-ttu-id="dcafe-119">Например, этот шаблон можно использовать для форматирования значения любого свойства типа [System. TimeSpan](/dotnet/api/System.TimeSpan): {0: MMM} {0: DD} {0: HH}: {0: mm}.</span><span class="sxs-lookup"><span data-stu-id="dcafe-119">For example, this pattern can be used to format the value of any property that is of type [System.Timespan](/dotnet/api/System.TimeSpan): {0:MMM}{0:dd}{0:HH}:{0:mm}.</span></span>

## <a name="remarks"></a><span data-ttu-id="dcafe-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="dcafe-120">Remarks</span></span>

<span data-ttu-id="dcafe-121">Строки формата можно использовать при создании табличных представлений, представлений списков, расширенных представлений или пользовательских представлений.</span><span class="sxs-lookup"><span data-stu-id="dcafe-121">Format strings can be used when creating table views, list views, wide views, or custom views.</span></span> <span data-ttu-id="dcafe-122">Дополнительные сведения о форматировании значения, отображаемого в представлении, см. в разделе [Форматирование отображаемых данных](./formatting-displayed-data.md).</span><span class="sxs-lookup"><span data-stu-id="dcafe-122">For more information about formatting a value displayed in a view, see [Formatting Displayed Data](./formatting-displayed-data.md).</span></span>

<span data-ttu-id="dcafe-123">Дополнительные сведения о компонентах табличного представления см. в разделе [табличное представление](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="dcafe-123">For more information about the components of a table view, see [Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="dcafe-124">Пример</span><span class="sxs-lookup"><span data-stu-id="dcafe-124">Example</span></span>

<span data-ttu-id="dcafe-125">В следующем примере показано, как определить строку форматирования для значения `StartTime` Свойства.</span><span class="sxs-lookup"><span data-stu-id="dcafe-125">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<TableColumnItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</TableColumnItem>
```

## <a name="see-also"></a><span data-ttu-id="dcafe-126">См. также</span><span class="sxs-lookup"><span data-stu-id="dcafe-126">See Also</span></span>

[<span data-ttu-id="dcafe-127">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="dcafe-127">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="dcafe-128">Форматирование отображаемых данных</span><span class="sxs-lookup"><span data-stu-id="dcafe-128">Formatting Displayed Data</span></span>](./formatting-displayed-data.md)

[<span data-ttu-id="dcafe-129">Элемент Таблеколумнитем (Format)</span><span class="sxs-lookup"><span data-stu-id="dcafe-129">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[<span data-ttu-id="dcafe-130">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="dcafe-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
