---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент PropertyName для элемента TableColumnItem для элемента TableControl (формат)
description: Элемент PropertyName для элемента TableColumnItem для элемента TableControl (формат)
ms.openlocfilehash: e83bbdb96d2755013cb9fe065cb98731ba44917f
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665589"
---
# <a name="propertyname-element-for-tablecolumnitem-for-tablecontrol-format"></a><span data-ttu-id="3a669-103">Элемент PropertyName для элемента TableColumnItem для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="3a669-103">PropertyName Element for TableColumnItem for TableControl (Format)</span></span>

<span data-ttu-id="3a669-104">Указывает свойство, значение которого отображается в столбце строки.</span><span class="sxs-lookup"><span data-stu-id="3a669-104">Specifies the property whose value is displayed in the column of the row.</span></span>

<span data-ttu-id="3a669-105">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Таблеконтрол элемент (Format) Таблеровентриес элемент (Format) Таблеровентри элемент (Format) Таблеколумнитемс элемент (Format) Таблеколумнитем элемент (Format) PropertyName элемент для TableColumnItem (Format)</span><span class="sxs-lookup"><span data-stu-id="3a669-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) TableColumnItems Element (Format) TableColumnItem Element (Format) PropertyName Element for TableColumnItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="3a669-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3a669-106">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3a669-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3a669-107">Attributes and Elements</span></span>

<span data-ttu-id="3a669-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `PropertyName` элемента.</span><span class="sxs-lookup"><span data-stu-id="3a669-108">The following sections describe attributes, child elements, and parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="3a669-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3a669-109">Attributes</span></span>

<span data-ttu-id="3a669-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="3a669-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="3a669-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3a669-111">Child Elements</span></span>

<span data-ttu-id="3a669-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="3a669-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="3a669-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3a669-113">Parent Elements</span></span>

|<span data-ttu-id="3a669-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="3a669-114">Element</span></span>|<span data-ttu-id="3a669-115">Описание</span><span class="sxs-lookup"><span data-stu-id="3a669-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3a669-116">Элемент Таблеколумнитем (Format)</span><span class="sxs-lookup"><span data-stu-id="3a669-116">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|<span data-ttu-id="3a669-117">Определяет свойство или скрипт, значение которого отображается в столбце строки.</span><span class="sxs-lookup"><span data-stu-id="3a669-117">Defines the property or script whose value is displayed in the column of the row.</span></span>|

## <a name="text-value"></a><span data-ttu-id="3a669-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="3a669-118">Text Value</span></span>

<span data-ttu-id="3a669-119">Укажите имя свойства, значение которого отображается.</span><span class="sxs-lookup"><span data-stu-id="3a669-119">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="3a669-120">Комментарии</span><span class="sxs-lookup"><span data-stu-id="3a669-120">Remarks</span></span>

<span data-ttu-id="3a669-121">Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="3a669-121">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="3a669-122">Пример</span><span class="sxs-lookup"><span data-stu-id="3a669-122">Example</span></span>

<span data-ttu-id="3a669-123">В этом примере показан `TableColumnItem` элемент, указывающий `Status` свойство объекта [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .</span><span class="sxs-lookup"><span data-stu-id="3a669-123">This example shows a `TableColumnItem` element that specifies the `Status` property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableColumnItem>
   <Alignment>Centered</Alignment>
  <PropertyName>Status</PropertyName>
</TableColumnItem>

```

## <a name="see-also"></a><span data-ttu-id="3a669-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="3a669-124">See Also</span></span>

[<span data-ttu-id="3a669-125">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="3a669-125">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="3a669-126">Элемент Таблеколумнитем (Format)</span><span class="sxs-lookup"><span data-stu-id="3a669-126">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[<span data-ttu-id="3a669-127">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="3a669-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
