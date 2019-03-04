---
title: Элемент PropertyName для TableColumnItem для TableControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb26d72c-2f77-4801-badf-0537ccc55e31
caps.latest.revision: 10
ms.openlocfilehash: 6e86b6a0874b385703121802bc8108a0410442cd
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859470"
---
# <a name="propertyname-element-for-tablecolumnitem-for-tablecontrol-format"></a><span data-ttu-id="6834a-102">Элемент PropertyName для элемента TableColumnItem для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="6834a-102">PropertyName Element for TableColumnItem for TableControl (Format)</span></span>

<span data-ttu-id="6834a-103">Задает свойство, значение которого отображается в столбце строки.</span><span class="sxs-lookup"><span data-stu-id="6834a-103">Specifies the property whose value is displayed in the column of the row.</span></span>

<span data-ttu-id="6834a-104">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) TableControl-элемент (формат) элемент TableRowEntries (формат) элемент TableRowEntry (формат) элемент TableColumnItems (формат) TableColumnItem элемент конфигурации (формат) Элемент PropertyName для TableColumnItem (формат)</span><span class="sxs-lookup"><span data-stu-id="6834a-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) TableColumnItems Element (Format) TableColumnItem Element (Format) PropertyName Element for TableColumnItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="6834a-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6834a-105">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6834a-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6834a-106">Attributes and Elements</span></span>

<span data-ttu-id="6834a-107">Ниже описаны атрибуты, дочерние элементы и родительский элемент `PropertyName` элемент.</span><span class="sxs-lookup"><span data-stu-id="6834a-107">The following sections describe attributes, child elements, and parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="6834a-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6834a-108">Attributes</span></span>

<span data-ttu-id="6834a-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="6834a-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="6834a-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6834a-110">Child Elements</span></span>

<span data-ttu-id="6834a-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="6834a-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="6834a-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6834a-112">Parent Elements</span></span>

|<span data-ttu-id="6834a-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="6834a-113">Element</span></span>|<span data-ttu-id="6834a-114">Описание</span><span class="sxs-lookup"><span data-stu-id="6834a-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6834a-115">Элемент TableColumnItem (формат)</span><span class="sxs-lookup"><span data-stu-id="6834a-115">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|<span data-ttu-id="6834a-116">Определяет свойство или скрипта, значение которого отображается в столбце строки.</span><span class="sxs-lookup"><span data-stu-id="6834a-116">Defines the property or script whose value is displayed in the column of the row.</span></span>|

## <a name="text-value"></a><span data-ttu-id="6834a-117">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="6834a-117">Text Value</span></span>

<span data-ttu-id="6834a-118">Укажите имя свойства, значение которого отображается.</span><span class="sxs-lookup"><span data-stu-id="6834a-118">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="6834a-119">Замечания</span><span class="sxs-lookup"><span data-stu-id="6834a-119">Remarks</span></span>

<span data-ttu-id="6834a-120">Дополнительные сведения о компонентах в табличное представление, см. в разделе [Создание представления таблицы](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="6834a-120">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="6834a-121">Пример</span><span class="sxs-lookup"><span data-stu-id="6834a-121">Example</span></span>

<span data-ttu-id="6834a-122">В этом примере показано `TableColumnItem` элемент, который задает `Status` свойство [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) объекта.</span><span class="sxs-lookup"><span data-stu-id="6834a-122">This example shows a `TableColumnItem` element that specifies the `Status` property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableColumnItem>
   <Alignment>Centered</Alignment>
  <PropertyName>Status</PropertyName>
</TableColumnItem>

```

## <a name="see-also"></a><span data-ttu-id="6834a-123">См. также</span><span class="sxs-lookup"><span data-stu-id="6834a-123">See Also</span></span>

[<span data-ttu-id="6834a-124">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="6834a-124">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="6834a-125">Элемент TableColumnItem (формат)</span><span class="sxs-lookup"><span data-stu-id="6834a-125">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[<span data-ttu-id="6834a-126">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="6834a-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
