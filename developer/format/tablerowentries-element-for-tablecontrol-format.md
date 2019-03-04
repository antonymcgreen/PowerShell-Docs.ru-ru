---
title: Элемент TableRowEntries для TableControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d10b68ca-256c-4c58-b503-73f7777b39ae
caps.latest.revision: 15
ms.openlocfilehash: d93750f919c1075f173dc9ac70324cc003e36879
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862190"
---
# <a name="tablerowentries-element-for-tablecontrol-format"></a><span data-ttu-id="3a7d0-102">Элемент TableRowEntries для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="3a7d0-102">TableRowEntries Element for TableControl (Format)</span></span>

<span data-ttu-id="3a7d0-103">Определяет строки таблицы.</span><span class="sxs-lookup"><span data-stu-id="3a7d0-103">Defines the rows of the table.</span></span>

<span data-ttu-id="3a7d0-104">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) TableControl-элемент (формат) TableRowEntries элемент конфигурации для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="3a7d0-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="3a7d0-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3a7d0-105">Syntax</span></span>

```xml
<TableRowEntries>
  <TableRowEntry>...</TableRowEntry>
</TableRowEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3a7d0-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3a7d0-106">Attributes and Elements</span></span>

<span data-ttu-id="3a7d0-107">В следующих разделах атрибуты, дочерние элементы и родительский элемент `TableRowEntries` элемент.</span><span class="sxs-lookup"><span data-stu-id="3a7d0-107">The following sections describe the attributes, child elements, and parent element of the `TableRowEntries` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="3a7d0-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3a7d0-108">Attributes</span></span>

<span data-ttu-id="3a7d0-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="3a7d0-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="3a7d0-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3a7d0-110">Child Elements</span></span>

|<span data-ttu-id="3a7d0-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="3a7d0-111">Element</span></span>|<span data-ttu-id="3a7d0-112">Описание</span><span class="sxs-lookup"><span data-stu-id="3a7d0-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3a7d0-113">Элемент TableRowEntry для TableRowEntries для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="3a7d0-113">TableRowEntry Element for TableRowEntries for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentroes-for-tablecontrol-format.md)|<span data-ttu-id="3a7d0-114">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="3a7d0-114">Required element.</span></span><br /><br /> <span data-ttu-id="3a7d0-115">Определяет данные, которые отображаются в строке таблицы.</span><span class="sxs-lookup"><span data-stu-id="3a7d0-115">Defines the data that is displayed in a row of the table.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="3a7d0-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3a7d0-116">Parent Elements</span></span>

|<span data-ttu-id="3a7d0-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="3a7d0-117">Element</span></span>|<span data-ttu-id="3a7d0-118">Описание</span><span class="sxs-lookup"><span data-stu-id="3a7d0-118">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3a7d0-119">TableControl-элемент (формат)</span><span class="sxs-lookup"><span data-stu-id="3a7d0-119">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)|<span data-ttu-id="3a7d0-120">Определяет формат таблицы для представления.</span><span class="sxs-lookup"><span data-stu-id="3a7d0-120">Defines a table format for a view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="3a7d0-121">Замечания</span><span class="sxs-lookup"><span data-stu-id="3a7d0-121">Remarks</span></span>

<span data-ttu-id="3a7d0-122">Необходимо указать один или несколько `TableRowEntry` элементы для представления таблицы.</span><span class="sxs-lookup"><span data-stu-id="3a7d0-122">You must specify one or more `TableRowEntry` elements for the table view.</span></span> <span data-ttu-id="3a7d0-123">Не ограничено максимальное число `TableRowEntry` элементы, которые могут быть добавлены и не важен их порядок.</span><span class="sxs-lookup"><span data-stu-id="3a7d0-123">There is no maximum limit to the number of `TableRowEntry` elements that can be added nor is their order significant.</span></span>

<span data-ttu-id="3a7d0-124">Дополнительные сведения о компонентах в табличное представление, см. в разделе [Создание представления таблицы](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="3a7d0-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="3a7d0-125">Пример</span><span class="sxs-lookup"><span data-stu-id="3a7d0-125">Example</span></span>

<span data-ttu-id="3a7d0-126">В следующем примере показан `TableRowEntries` элемент, который определяет строку, отображающую значения двух свойств [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) объекта.</span><span class="sxs-lookup"><span data-stu-id="3a7d0-126">The following example shows a `TableRowEntries` element that defines a row that displays the values of two properties of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableRowEntries>
  <TableRowEntry>
    <EntrySelectedBy>
      <TypeName>System.Diagnostics.Process</TypeName>
    </EntrySelectedBy>
    <TableColumnItems>
      <TableColumnItem>
        <PropertyName> Property for first column</PropertyName>
      </TableColumnItem>
      <TableColumnItem>
        <PropertyName> Property for second column</PropertyName>
      </TableColumnItem>
    </TableColumnItems>
  </TableRowEntry>
</TableRowEntries>

```

## <a name="see-also"></a><span data-ttu-id="3a7d0-127">См. также</span><span class="sxs-lookup"><span data-stu-id="3a7d0-127">See Also</span></span>

[<span data-ttu-id="3a7d0-128">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="3a7d0-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="3a7d0-129">TableControl-элемент (формат)</span><span class="sxs-lookup"><span data-stu-id="3a7d0-129">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)

[<span data-ttu-id="3a7d0-130">Элемент TableRowEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="3a7d0-130">TableRowEntry Element (Format)</span></span>](./tablerowentry-element-for-tablerowentroes-for-tablecontrol-format.md)

[<span data-ttu-id="3a7d0-131">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="3a7d0-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
