---
title: Элемент FormatString для Видеитем для Видеконтрол (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5bc6ea26-3ca6-4bab-8a13-29189821ba15
caps.latest.revision: 7
ms.openlocfilehash: a1dc145864a6904fd4af6c3b9187819c49e224b0
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363033"
---
# <a name="formatstring-element-for-wideitem-for-widecontrol-format"></a><span data-ttu-id="9e370-102">Элемент FormatString для элемента WideItem для элемента WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="9e370-102">FormatString Element for WideItem for WideControl (Format)</span></span>

<span data-ttu-id="9e370-103">Задает шаблон формата, определяющий способ отображения значения свойства или скрипта в представлении.</span><span class="sxs-lookup"><span data-stu-id="9e370-103">Specifies a format pattern that defines how the property or script value is displayed in the view.</span></span>

<span data-ttu-id="9e370-104">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Видеконтрол элемент (Format) Видинтриес элемент (Format) Видинтри элемент для видеконтрол (Format) Видеитем для элемента видеконтрол (Format) FormatString для Видеитем для Видеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="9e370-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element for WideControl (Format) WideItem Element for WideControl (Format) FormatString Element for WideItem for WideControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9e370-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9e370-105">Syntax</span></span>

```xml
<FormatString>PropertyPattern</FormatString>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9e370-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9e370-106">Attributes and Elements</span></span>

<span data-ttu-id="9e370-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `FormatString`.</span><span class="sxs-lookup"><span data-stu-id="9e370-107">The following sections describe the attributes, child elements, and the parent element of the `FormatString` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9e370-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9e370-108">Attributes</span></span>

<span data-ttu-id="9e370-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="9e370-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9e370-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9e370-110">Child Elements</span></span>

<span data-ttu-id="9e370-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="9e370-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="9e370-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9e370-112">Parent Elements</span></span>

|<span data-ttu-id="9e370-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="9e370-113">Element</span></span>|<span data-ttu-id="9e370-114">Описание</span><span class="sxs-lookup"><span data-stu-id="9e370-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9e370-115">Элемент Видеитем для Видеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="9e370-115">WideItem Element for WideControl (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="9e370-116">Определяет свойство или скрипт, значение которого отображается в строке представления списка.</span><span class="sxs-lookup"><span data-stu-id="9e370-116">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="9e370-117">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="9e370-117">Text Value</span></span>

<span data-ttu-id="9e370-118">Укажите шаблон, используемый для форматирования данных.</span><span class="sxs-lookup"><span data-stu-id="9e370-118">Specify the pattern that is used to format the data.</span></span> <span data-ttu-id="9e370-119">Например, этот шаблон можно использовать для форматирования значения любого свойства типа [System. TimeSpan](/dotnet/api/System.TimeSpan): {0: MMM} {0: DD} {0: HH}: {0: mm}.</span><span class="sxs-lookup"><span data-stu-id="9e370-119">For example, you can use this pattern to format the value of any property that is of type [System.Timespan](/dotnet/api/System.TimeSpan): {0:MMM}{0:dd}{0:HH}:{0:mm}.</span></span>

## <a name="remarks"></a><span data-ttu-id="9e370-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="9e370-120">Remarks</span></span>

<span data-ttu-id="9e370-121">Строки формата можно использовать при создании табличных представлений, представлений списков, расширенных представлений или пользовательских представлений.</span><span class="sxs-lookup"><span data-stu-id="9e370-121">Format strings can be used when creating table views, list views, wide views, or custom views.</span></span> <span data-ttu-id="9e370-122">Дополнительные сведения о форматировании значения, отображаемого в представлении, см. в разделе [Форматирование отображаемых данных](./formatting-displayed-data.md).</span><span class="sxs-lookup"><span data-stu-id="9e370-122">For more information about formatting a value displayed in a view, see [Formatting Displayed Data](./formatting-displayed-data.md).</span></span>

<span data-ttu-id="9e370-123">Дополнительные сведения об использовании строк формата в широких представлениях см. в разделе [Создание расширенного представления](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="9e370-123">For more information about using format strings in wide views, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="9e370-124">Пример</span><span class="sxs-lookup"><span data-stu-id="9e370-124">Example</span></span>

<span data-ttu-id="9e370-125">В следующем примере показано, как определить строку форматирования для значения свойства `StartTime`.</span><span class="sxs-lookup"><span data-stu-id="9e370-125">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<WideItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</WideItem>
```

## <a name="see-also"></a><span data-ttu-id="9e370-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="9e370-126">See Also</span></span>

[<span data-ttu-id="9e370-127">Создание расширенного представления</span><span class="sxs-lookup"><span data-stu-id="9e370-127">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="9e370-128">Элемент Видеитем для Видеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="9e370-128">WideItem Element for WideControl (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="9e370-129">Создание файла форматирования и типов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9e370-129">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
