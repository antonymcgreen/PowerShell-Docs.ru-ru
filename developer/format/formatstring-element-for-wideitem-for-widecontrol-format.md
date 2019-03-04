---
title: Элемент FormatString для WideItem для WideControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5bc6ea26-3ca6-4bab-8a13-29189821ba15
caps.latest.revision: 7
ms.openlocfilehash: a1dc145864a6904fd4af6c3b9187819c49e224b0
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860940"
---
# <a name="formatstring-element-for-wideitem-for-widecontrol-format"></a><span data-ttu-id="308be-102">Элемент FormatString для элемента WideItem для элемента WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="308be-102">FormatString Element for WideItem for WideControl (Format)</span></span>

<span data-ttu-id="308be-103">Задает шаблон формата, который определяет способ отображения значения свойства или скрипт в представлении.</span><span class="sxs-lookup"><span data-stu-id="308be-103">Specifies a format pattern that defines how the property or script value is displayed in the view.</span></span>

<span data-ttu-id="308be-104">Элемент (формат) элемент ViewDefinitions (формат) представление элемент (формат) элемент WideControl (формат) элемент WideEntries (формат) WideEntry элемент конфигурации для элемента WideItem WideControl (формат) элемент FormatString WideControl (формат) для WideItem для WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="308be-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element for WideControl (Format) WideItem Element for WideControl (Format) FormatString Element for WideItem for WideControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="308be-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="308be-105">Syntax</span></span>

```xml
<FormatString>PropertyPattern</FormatString>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="308be-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="308be-106">Attributes and Elements</span></span>

<span data-ttu-id="308be-107">В следующих разделах атрибуты, дочерние элементы и родительский элемент `FormatString` элемент.</span><span class="sxs-lookup"><span data-stu-id="308be-107">The following sections describe the attributes, child elements, and the parent element of the `FormatString` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="308be-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="308be-108">Attributes</span></span>

<span data-ttu-id="308be-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="308be-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="308be-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="308be-110">Child Elements</span></span>

<span data-ttu-id="308be-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="308be-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="308be-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="308be-112">Parent Elements</span></span>

|<span data-ttu-id="308be-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="308be-113">Element</span></span>|<span data-ttu-id="308be-114">Описание</span><span class="sxs-lookup"><span data-stu-id="308be-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="308be-115">Элемент WideItem для WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="308be-115">WideItem Element for WideControl (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="308be-116">Определяет свойство или скрипта, значение которого отображается в строке в представлении списка.</span><span class="sxs-lookup"><span data-stu-id="308be-116">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="308be-117">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="308be-117">Text Value</span></span>

<span data-ttu-id="308be-118">Укажите шаблон, используемый для форматирования данных.</span><span class="sxs-lookup"><span data-stu-id="308be-118">Specify the pattern that is used to format the data.</span></span> <span data-ttu-id="308be-119">Например, можно использовать этот шаблон для форматирования значения любого свойства, который относится к типу [System.Timespan](/dotnet/api/System.TimeSpan): {0: MMM} {0:dd} {0:HH}: {0: mm}.</span><span class="sxs-lookup"><span data-stu-id="308be-119">For example, you can use this pattern to format the value of any property that is of type [System.Timespan](/dotnet/api/System.TimeSpan): {0:MMM}{0:dd}{0:HH}:{0:mm}.</span></span>

## <a name="remarks"></a><span data-ttu-id="308be-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="308be-120">Remarks</span></span>

<span data-ttu-id="308be-121">Строки формата может использоваться при создании представления таблиц, представлений списков, широкие представления или представления.</span><span class="sxs-lookup"><span data-stu-id="308be-121">Format strings can be used when creating table views, list views, wide views, or custom views.</span></span> <span data-ttu-id="308be-122">Дополнительные сведения о форматировании значения, отображаемого в представлении см. в разделе [форматирования отображаемых данных](./formatting-displayed-data.md).</span><span class="sxs-lookup"><span data-stu-id="308be-122">For more information about formatting a value displayed in a view, see [Formatting Displayed Data](./formatting-displayed-data.md).</span></span>

<span data-ttu-id="308be-123">Дополнительные сведения об использовании строки формата в широкие представления см. в разделе [Создание широкое представление](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="308be-123">For more information about using format strings in wide views, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="308be-124">Пример</span><span class="sxs-lookup"><span data-stu-id="308be-124">Example</span></span>

<span data-ttu-id="308be-125">Приведенный ниже показано, как определить строку форматирования для значения `StartTime` свойство.</span><span class="sxs-lookup"><span data-stu-id="308be-125">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<WideItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</WideItem>
```

## <a name="see-also"></a><span data-ttu-id="308be-126">См. также</span><span class="sxs-lookup"><span data-stu-id="308be-126">See Also</span></span>

[<span data-ttu-id="308be-127">Создание широкое представление</span><span class="sxs-lookup"><span data-stu-id="308be-127">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="308be-128">Элемент WideItem для WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="308be-128">WideItem Element for WideControl (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="308be-129">Написание форматирования Windows PowerShell и типы файлов</span><span class="sxs-lookup"><span data-stu-id="308be-129">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
