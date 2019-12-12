---
title: Элемент FormatString для ListItem для ListControl (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd2cac66-88bb-449f-9d47-bd2cd4fe1801
caps.latest.revision: 13
ms.openlocfilehash: e6024ec4f7fc490c92408047c8c15c775e45bf9d
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363023"
---
# <a name="formatstring-element-for-listitem-for-listcontrol--format"></a><span data-ttu-id="ecdf3-102">Элемент FormatString для элемента ListItem для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="ecdf3-102">FormatString Element for ListItem for ListControl  (Format)</span></span>

<span data-ttu-id="ecdf3-103">Задает шаблон формата, определяющий способ отображения значения свойства или скрипта.</span><span class="sxs-lookup"><span data-stu-id="ecdf3-103">Specifies a format pattern that defines how the property or script value is displayed.</span></span>

<span data-ttu-id="ecdf3-104">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ListControl элемент (Format) Листентриес для ListControl (Format) Листентри элемента для ListControl (Format) элемент ListItems для ListControl (Format) Элемент ListItem для ListControl (Format) элемент FormatString для элемента ListItem для ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="ecdf3-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListControl (Format) ListItems Element for ListControl (Format) ListItem Element for ListControl (Format) FormatString Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ecdf3-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ecdf3-105">Syntax</span></span>

```xml
<FormatString>PropertyPattern</FormatString>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ecdf3-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ecdf3-106">Attributes and Elements</span></span>

<span data-ttu-id="ecdf3-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `FormatString`.</span><span class="sxs-lookup"><span data-stu-id="ecdf3-107">The following sections describe the attributes, child elements, and the parent element of the `FormatString` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ecdf3-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ecdf3-108">Attributes</span></span>

<span data-ttu-id="ecdf3-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="ecdf3-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ecdf3-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ecdf3-110">Child Elements</span></span>

<span data-ttu-id="ecdf3-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="ecdf3-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ecdf3-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ecdf3-112">Parent Elements</span></span>

|<span data-ttu-id="ecdf3-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="ecdf3-113">Element</span></span>|<span data-ttu-id="ecdf3-114">Описание</span><span class="sxs-lookup"><span data-stu-id="ecdf3-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ecdf3-115">Элемент ListItem (Format)</span><span class="sxs-lookup"><span data-stu-id="ecdf3-115">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="ecdf3-116">Определяет свойство или скрипт, значение которого отображается в строке представления списка.</span><span class="sxs-lookup"><span data-stu-id="ecdf3-116">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="ecdf3-117">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="ecdf3-117">Text Value</span></span>

<span data-ttu-id="ecdf3-118">Укажите шаблон, используемый для форматирования данных.</span><span class="sxs-lookup"><span data-stu-id="ecdf3-118">Specify the pattern that is used to format the data.</span></span> <span data-ttu-id="ecdf3-119">Например, этот шаблон можно использовать для форматирования значения любого свойства типа [System. TimeSpan](/dotnet/api/System.TimeSpan): {0: MMM} {0: DD} {0: HH}: {0: mm}.</span><span class="sxs-lookup"><span data-stu-id="ecdf3-119">For example, you can use this pattern to format the value of any property that is of type [System.Timespan](/dotnet/api/System.TimeSpan): {0:MMM}{0:dd}{0:HH}:{0:mm}.</span></span>

## <a name="remarks"></a><span data-ttu-id="ecdf3-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="ecdf3-120">Remarks</span></span>

<span data-ttu-id="ecdf3-121">Строки формата можно использовать при создании табличных представлений, представлений списков, расширенных представлений или пользовательских представлений.</span><span class="sxs-lookup"><span data-stu-id="ecdf3-121">Format strings can be used when creating table views, list views, wide views, or custom views.</span></span> <span data-ttu-id="ecdf3-122">Дополнительные сведения о форматировании значения, отображаемого в представлении, см. в разделе [Форматирование отображаемых данных](./formatting-displayed-data.md).</span><span class="sxs-lookup"><span data-stu-id="ecdf3-122">For more information about formatting a value displayed in a view, see [Formatting Displayed Data](./formatting-displayed-data.md).</span></span>

<span data-ttu-id="ecdf3-123">Дополнительные сведения об использовании строк форматирования в представлениях списков см. в разделе [Создание представления списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="ecdf3-123">For more information about using format strings in list views, see [Creating List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="ecdf3-124">Пример</span><span class="sxs-lookup"><span data-stu-id="ecdf3-124">Example</span></span>

<span data-ttu-id="ecdf3-125">В следующем примере показано, как определить строку форматирования для значения свойства `StartTime`.</span><span class="sxs-lookup"><span data-stu-id="ecdf3-125">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<ListItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</ListItem>
```

## <a name="see-also"></a><span data-ttu-id="ecdf3-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="ecdf3-126">See Also</span></span>

[<span data-ttu-id="ecdf3-127">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="ecdf3-127">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="ecdf3-128">Элемент ListItem (Format)</span><span class="sxs-lookup"><span data-stu-id="ecdf3-128">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="ecdf3-129">Создание файла форматирования и типов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ecdf3-129">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
