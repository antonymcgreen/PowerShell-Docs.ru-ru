---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент FormatString для элемента WideItem для элемента WideControl (формат)
description: Элемент FormatString для элемента WideItem для элемента WideControl (формат)
ms.openlocfilehash: f67a18e3ec4f1323e7f9be8904db518c679d53e5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667884"
---
# <a name="formatstring-element-for-wideitem-for-widecontrol-format"></a><span data-ttu-id="2fcfe-103">Элемент FormatString для элемента WideItem для элемента WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="2fcfe-103">FormatString Element for WideItem for WideControl (Format)</span></span>

<span data-ttu-id="2fcfe-104">Задает шаблон формата, определяющий способ отображения значения свойства или скрипта в представлении.</span><span class="sxs-lookup"><span data-stu-id="2fcfe-104">Specifies a format pattern that defines how the property or script value is displayed in the view.</span></span>

<span data-ttu-id="2fcfe-105">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Видеконтрол элемент (Format) Видинтриес элемент (Format) Видинтри элемент для видеконтрол (Format) Видеитем для элемента видеконтрол (Format) для WideItem в WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="2fcfe-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element for WideControl (Format) WideItem Element for WideControl (Format) FormatString Element for WideItem for WideControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2fcfe-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2fcfe-106">Syntax</span></span>

```xml
<FormatString>PropertyPattern</FormatString>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2fcfe-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2fcfe-107">Attributes and Elements</span></span>

<span data-ttu-id="2fcfe-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `FormatString` элемента.</span><span class="sxs-lookup"><span data-stu-id="2fcfe-108">The following sections describe the attributes, child elements, and the parent element of the `FormatString` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="2fcfe-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2fcfe-109">Attributes</span></span>

<span data-ttu-id="2fcfe-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="2fcfe-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2fcfe-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2fcfe-111">Child Elements</span></span>

<span data-ttu-id="2fcfe-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="2fcfe-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2fcfe-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2fcfe-113">Parent Elements</span></span>

|<span data-ttu-id="2fcfe-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="2fcfe-114">Element</span></span>|<span data-ttu-id="2fcfe-115">Описание</span><span class="sxs-lookup"><span data-stu-id="2fcfe-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2fcfe-116">Элемент WideItem для WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="2fcfe-116">WideItem Element for WideControl (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="2fcfe-117">Определяет свойство или скрипт, значение которого отображается в строке представления списка.</span><span class="sxs-lookup"><span data-stu-id="2fcfe-117">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="2fcfe-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="2fcfe-118">Text Value</span></span>

<span data-ttu-id="2fcfe-119">Укажите шаблон, используемый для форматирования данных.</span><span class="sxs-lookup"><span data-stu-id="2fcfe-119">Specify the pattern that is used to format the data.</span></span> <span data-ttu-id="2fcfe-120">Например, этот шаблон можно использовать для форматирования значения любого свойства типа [System. TimeSpan](/dotnet/api/System.TimeSpan): {0: MMM} {0: DD} {0: HH}: {0: mm}.</span><span class="sxs-lookup"><span data-stu-id="2fcfe-120">For example, you can use this pattern to format the value of any property that is of type [System.Timespan](/dotnet/api/System.TimeSpan): {0:MMM}{0:dd}{0:HH}:{0:mm}.</span></span>

## <a name="remarks"></a><span data-ttu-id="2fcfe-121">Комментарии</span><span class="sxs-lookup"><span data-stu-id="2fcfe-121">Remarks</span></span>

<span data-ttu-id="2fcfe-122">Строки формата можно использовать при создании табличных представлений, представлений списков, расширенных представлений или пользовательских представлений.</span><span class="sxs-lookup"><span data-stu-id="2fcfe-122">Format strings can be used when creating table views, list views, wide views, or custom views.</span></span> <span data-ttu-id="2fcfe-123">Дополнительные сведения о форматировании значения, отображаемого в представлении, см. в разделе [Форматирование отображаемых данных](./formatting-displayed-data.md).</span><span class="sxs-lookup"><span data-stu-id="2fcfe-123">For more information about formatting a value displayed in a view, see [Formatting Displayed Data](./formatting-displayed-data.md).</span></span>

<span data-ttu-id="2fcfe-124">Дополнительные сведения об использовании строк формата в широких представлениях см. в разделе [Создание расширенного представления](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="2fcfe-124">For more information about using format strings in wide views, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="2fcfe-125">Пример</span><span class="sxs-lookup"><span data-stu-id="2fcfe-125">Example</span></span>

<span data-ttu-id="2fcfe-126">В следующем примере показано, как определить строку форматирования для значения `StartTime` Свойства.</span><span class="sxs-lookup"><span data-stu-id="2fcfe-126">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<WideItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</WideItem>
```

## <a name="see-also"></a><span data-ttu-id="2fcfe-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="2fcfe-127">See Also</span></span>

[<span data-ttu-id="2fcfe-128">Создание широкого представления</span><span class="sxs-lookup"><span data-stu-id="2fcfe-128">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="2fcfe-129">Элемент WideItem для WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="2fcfe-129">WideItem Element for WideControl (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="2fcfe-130">Создание файла форматирования и типов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2fcfe-130">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
