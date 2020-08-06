---
title: Элемент PropertyName для Таблеколумнитем для Таблеконтрол (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: bf267eeb83aef59abea2d945af12e849252309c8
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772983"
---
# <a name="propertyname-element-for-tablecolumnitem-for-tablecontrol-format"></a><span data-ttu-id="b6e7f-102">Элемент PropertyName для элемента TableColumnItem для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="b6e7f-102">PropertyName Element for TableColumnItem for TableControl (Format)</span></span>

<span data-ttu-id="b6e7f-103">Указывает свойство, значение которого отображается в столбце строки.</span><span class="sxs-lookup"><span data-stu-id="b6e7f-103">Specifies the property whose value is displayed in the column of the row.</span></span>

<span data-ttu-id="b6e7f-104">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Таблеконтрол элемент (Format) Таблеровентриес элемент (Format) Таблеровентри элемент (Format) Таблеколумнитемс элемент (Format) Таблеколумнитем элемент (Format) PropertyName элемент для TableColumnItem (Format)</span><span class="sxs-lookup"><span data-stu-id="b6e7f-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) TableColumnItems Element (Format) TableColumnItem Element (Format) PropertyName Element for TableColumnItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b6e7f-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b6e7f-105">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b6e7f-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b6e7f-106">Attributes and Elements</span></span>

<span data-ttu-id="b6e7f-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `PropertyName` элемента.</span><span class="sxs-lookup"><span data-stu-id="b6e7f-107">The following sections describe attributes, child elements, and parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b6e7f-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b6e7f-108">Attributes</span></span>

<span data-ttu-id="b6e7f-109">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b6e7f-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b6e7f-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b6e7f-110">Child Elements</span></span>

<span data-ttu-id="b6e7f-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b6e7f-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b6e7f-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b6e7f-112">Parent Elements</span></span>

|<span data-ttu-id="b6e7f-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="b6e7f-113">Element</span></span>|<span data-ttu-id="b6e7f-114">Описание</span><span class="sxs-lookup"><span data-stu-id="b6e7f-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b6e7f-115">Элемент Таблеколумнитем (Format)</span><span class="sxs-lookup"><span data-stu-id="b6e7f-115">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|<span data-ttu-id="b6e7f-116">Определяет свойство или скрипт, значение которого отображается в столбце строки.</span><span class="sxs-lookup"><span data-stu-id="b6e7f-116">Defines the property or script whose value is displayed in the column of the row.</span></span>|

## <a name="text-value"></a><span data-ttu-id="b6e7f-117">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="b6e7f-117">Text Value</span></span>

<span data-ttu-id="b6e7f-118">Укажите имя свойства, значение которого отображается.</span><span class="sxs-lookup"><span data-stu-id="b6e7f-118">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="b6e7f-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="b6e7f-119">Remarks</span></span>

<span data-ttu-id="b6e7f-120">Дополнительные сведения о компонентах табличного представления см. в разделе [Создание табличного представления](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="b6e7f-120">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="b6e7f-121">Пример</span><span class="sxs-lookup"><span data-stu-id="b6e7f-121">Example</span></span>

<span data-ttu-id="b6e7f-122">В этом примере показан `TableColumnItem` элемент, указывающий `Status` свойство объекта [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .</span><span class="sxs-lookup"><span data-stu-id="b6e7f-122">This example shows a `TableColumnItem` element that specifies the `Status` property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableColumnItem>
   <Alignment>Centered</Alignment>
  <PropertyName>Status</PropertyName>
</TableColumnItem>

```

## <a name="see-also"></a><span data-ttu-id="b6e7f-123">См. также</span><span class="sxs-lookup"><span data-stu-id="b6e7f-123">See Also</span></span>

[<span data-ttu-id="b6e7f-124">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="b6e7f-124">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="b6e7f-125">Элемент Таблеколумнитем (Format)</span><span class="sxs-lookup"><span data-stu-id="b6e7f-125">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[<span data-ttu-id="b6e7f-126">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="b6e7f-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
