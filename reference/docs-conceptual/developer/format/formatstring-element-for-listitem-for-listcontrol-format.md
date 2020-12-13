---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент FormatString для элемента ListItem для элемента ListControl (формат)
description: Элемент FormatString для элемента ListItem для элемента ListControl (формат)
ms.openlocfilehash: 1c16da92928ea632241942f4f2c63390c4fea706
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667918"
---
# <a name="formatstring-element-for-listitem-for-listcontrol--format"></a><span data-ttu-id="cdc4a-103">Элемент FormatString для элемента ListItem для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="cdc4a-103">FormatString Element for ListItem for ListControl  (Format)</span></span>

<span data-ttu-id="cdc4a-104">Задает шаблон формата, определяющий способ отображения значения свойства или скрипта.</span><span class="sxs-lookup"><span data-stu-id="cdc4a-104">Specifies a format pattern that defines how the property or script value is displayed.</span></span>

<span data-ttu-id="cdc4a-105">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ListControl элемент (Format) Листентриес для ListControl (Format) Листентри элемент для ListControl (Format) элемент списка элементов для ListControl (формат) элемента ListItem для ListControl (Format) элемент списка (формат) для элемента списка (Format) ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="cdc4a-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListControl (Format) ListItems Element for ListControl (Format) ListItem Element for ListControl (Format) FormatString Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="cdc4a-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cdc4a-106">Syntax</span></span>

```xml
<FormatString>PropertyPattern</FormatString>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="cdc4a-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="cdc4a-107">Attributes and Elements</span></span>

<span data-ttu-id="cdc4a-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `FormatString` элемента.</span><span class="sxs-lookup"><span data-stu-id="cdc4a-108">The following sections describe the attributes, child elements, and the parent element of the `FormatString` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="cdc4a-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="cdc4a-109">Attributes</span></span>

<span data-ttu-id="cdc4a-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="cdc4a-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="cdc4a-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="cdc4a-111">Child Elements</span></span>

<span data-ttu-id="cdc4a-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="cdc4a-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="cdc4a-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="cdc4a-113">Parent Elements</span></span>

|<span data-ttu-id="cdc4a-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="cdc4a-114">Element</span></span>|<span data-ttu-id="cdc4a-115">Описание</span><span class="sxs-lookup"><span data-stu-id="cdc4a-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cdc4a-116">Элемент ListItem (Format)</span><span class="sxs-lookup"><span data-stu-id="cdc4a-116">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="cdc4a-117">Определяет свойство или скрипт, значение которого отображается в строке представления списка.</span><span class="sxs-lookup"><span data-stu-id="cdc4a-117">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="cdc4a-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="cdc4a-118">Text Value</span></span>

<span data-ttu-id="cdc4a-119">Укажите шаблон, используемый для форматирования данных.</span><span class="sxs-lookup"><span data-stu-id="cdc4a-119">Specify the pattern that is used to format the data.</span></span> <span data-ttu-id="cdc4a-120">Например, этот шаблон можно использовать для форматирования значения любого свойства типа [System. TimeSpan](/dotnet/api/System.TimeSpan): {0: MMM} {0: DD} {0: HH}: {0: mm}.</span><span class="sxs-lookup"><span data-stu-id="cdc4a-120">For example, you can use this pattern to format the value of any property that is of type [System.Timespan](/dotnet/api/System.TimeSpan): {0:MMM}{0:dd}{0:HH}:{0:mm}.</span></span>

## <a name="remarks"></a><span data-ttu-id="cdc4a-121">Комментарии</span><span class="sxs-lookup"><span data-stu-id="cdc4a-121">Remarks</span></span>

<span data-ttu-id="cdc4a-122">Строки формата можно использовать при создании табличных представлений, представлений списков, расширенных представлений или пользовательских представлений.</span><span class="sxs-lookup"><span data-stu-id="cdc4a-122">Format strings can be used when creating table views, list views, wide views, or custom views.</span></span> <span data-ttu-id="cdc4a-123">Дополнительные сведения о форматировании значения, отображаемого в представлении, см. в разделе [Форматирование отображаемых данных](./formatting-displayed-data.md).</span><span class="sxs-lookup"><span data-stu-id="cdc4a-123">For more information about formatting a value displayed in a view, see [Formatting Displayed Data](./formatting-displayed-data.md).</span></span>

<span data-ttu-id="cdc4a-124">Дополнительные сведения об использовании строк форматирования в представлениях списков см. в разделе [Создание представления списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="cdc4a-124">For more information about using format strings in list views, see [Creating List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="cdc4a-125">Пример</span><span class="sxs-lookup"><span data-stu-id="cdc4a-125">Example</span></span>

<span data-ttu-id="cdc4a-126">В следующем примере показано, как определить строку форматирования для значения `StartTime` Свойства.</span><span class="sxs-lookup"><span data-stu-id="cdc4a-126">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<ListItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</ListItem>
```

## <a name="see-also"></a><span data-ttu-id="cdc4a-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="cdc4a-127">See Also</span></span>

[<span data-ttu-id="cdc4a-128">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="cdc4a-128">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="cdc4a-129">Элемент ListItem (Format)</span><span class="sxs-lookup"><span data-stu-id="cdc4a-129">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="cdc4a-130">Создание файла форматирования и типов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cdc4a-130">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
