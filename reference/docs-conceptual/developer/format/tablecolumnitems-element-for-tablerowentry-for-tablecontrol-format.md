---
title: Элемент Таблеколумнитемс для Таблеровентри для Таблеконтрол (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 661b938e8db0e68e10dc05f552e4f3a14608bc55
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785155"
---
# <a name="tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format"></a><span data-ttu-id="ca929-102">Элемент TableColumnItems для элемента TableRowEntry для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="ca929-102">TableColumnItems Element for TableRowEntry for TableControl (Format)</span></span>

<span data-ttu-id="ca929-103">Определяет свойства или скрипты, значения которых отображаются в строке.</span><span class="sxs-lookup"><span data-stu-id="ca929-103">Defines the properties or scripts whose values are displayed in a row.</span></span>

<span data-ttu-id="ca929-104">Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент Таблеконтрол (Format) элемент Таблеровентриес для Таблеконтрол (Format) Таблеровентри для таблеровентриес для TableControl (Format) TableColumnItems для TableControlEntry в TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="ca929-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element for TableControl (Format) TableRowEntry Element for TableRowEntries for TableControl (Format) TableColumnItems Element for TableControlEntry for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ca929-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ca929-105">Syntax</span></span>

```xml
TableColumnItems>
  <TableColumnItem>...</TableColumnItem>
</TableColumnItems>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ca929-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ca929-106">Attributes and Elements</span></span>

<span data-ttu-id="ca929-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `TableColumnItems` элемента.</span><span class="sxs-lookup"><span data-stu-id="ca929-107">The following sections describe the attributes, child elements, and parent element of the `TableColumnItems` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ca929-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ca929-108">Attributes</span></span>

<span data-ttu-id="ca929-109">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ca929-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ca929-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ca929-110">Child Elements</span></span>

|<span data-ttu-id="ca929-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="ca929-111">Element</span></span>|<span data-ttu-id="ca929-112">Описание</span><span class="sxs-lookup"><span data-stu-id="ca929-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ca929-113">Элемент TableColumnItem для элемента TableColumnItems для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="ca929-113">TableColumnItem Element for TableColumnItems for TableControl (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|<span data-ttu-id="ca929-114">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="ca929-114">Required element.</span></span><br /><br /> <span data-ttu-id="ca929-115">Определяет свойство или скрипт, значение которого отображается в столбце строки.</span><span class="sxs-lookup"><span data-stu-id="ca929-115">Defines the property or script whose value is displayed in a column of the row.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="ca929-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ca929-116">Parent Elements</span></span>

|<span data-ttu-id="ca929-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="ca929-117">Element</span></span>|<span data-ttu-id="ca929-118">Описание</span><span class="sxs-lookup"><span data-stu-id="ca929-118">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ca929-119">Элемент TableRowEntry для элемента TableRowEntries для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="ca929-119">TableRowEntry Element for TableRowEntries for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)|<span data-ttu-id="ca929-120">Определяет данные, отображаемые в строке таблицы.</span><span class="sxs-lookup"><span data-stu-id="ca929-120">Defines the data that is displayed in a row of the table.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ca929-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="ca929-121">Remarks</span></span>

<span data-ttu-id="ca929-122">`TableColumnItem`Для каждого столбца строки требуется элемент.</span><span class="sxs-lookup"><span data-stu-id="ca929-122">A `TableColumnItem` element is required for each column of the row.</span></span> <span data-ttu-id="ca929-123">Первая запись отображается в первом столбце, второй элемент во втором столбце и т. д.</span><span class="sxs-lookup"><span data-stu-id="ca929-123">The first entry is displayed in first column, the second entry in the second column, and so on.</span></span>

<span data-ttu-id="ca929-124">Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="ca929-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="ca929-125">Пример</span><span class="sxs-lookup"><span data-stu-id="ca929-125">Example</span></span>

<span data-ttu-id="ca929-126">В следующем примере показан `TableColumnItems` элемент, определяющий три свойства объекта [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .</span><span class="sxs-lookup"><span data-stu-id="ca929-126">The following example shows a `TableColumnItems` element that defines three properties of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableColumnItems>
  <TableColumnItem>
    <PropertyName>Status</PropertyName>
  </TableColumnItem>
  <TableColumnItem>
    <PropertyName>Name</PropertyName>
  </TableColumnItem>
  <TableColumnItem>
    <PropertyName>DisplayName</PropertyName>
  </TableColumnItem>
</TableColumnItems>

```

## <a name="see-also"></a><span data-ttu-id="ca929-127">См. также</span><span class="sxs-lookup"><span data-stu-id="ca929-127">See Also</span></span>

[<span data-ttu-id="ca929-128">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="ca929-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="ca929-129">Элемент Таблеколумнитем (Format)</span><span class="sxs-lookup"><span data-stu-id="ca929-129">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[<span data-ttu-id="ca929-130">Элемент Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="ca929-130">TableRowEntry Element (Format)</span></span>](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md)

[<span data-ttu-id="ca929-131">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="ca929-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
