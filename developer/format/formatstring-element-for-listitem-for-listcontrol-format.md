---
title: Элемент FormatString для ListItem для ListControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd2cac66-88bb-449f-9d47-bd2cd4fe1801
caps.latest.revision: 13
ms.openlocfilehash: e6024ec4f7fc490c92408047c8c15c775e45bf9d
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065627"
---
# <a name="formatstring-element-for-listitem-for-listcontrol--format"></a><span data-ttu-id="9f674-102">Элемент FormatString для элемента ListItem для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="9f674-102">FormatString Element for ListItem for ListControl  (Format)</span></span>

<span data-ttu-id="9f674-103">Задает шаблон формата, который определяет способ отображения значения свойства или скрипт.</span><span class="sxs-lookup"><span data-stu-id="9f674-103">Specifies a format pattern that defines how the property or script value is displayed.</span></span>

<span data-ttu-id="9f674-104">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) элемента ListControl (формат) ListEntries элемента конфигурации для элемента ListEntry ListControl (формат) для элемента ListControl (формат) ListItems ListControl (формат) Элемент ListItem для элемента ListControl (формат) FormatString ListItem для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="9f674-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListControl (Format) ListItems Element for ListControl (Format) ListItem Element for ListControl (Format) FormatString Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9f674-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9f674-105">Syntax</span></span>

```xml
<FormatString>PropertyPattern</FormatString>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9f674-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9f674-106">Attributes and Elements</span></span>

<span data-ttu-id="9f674-107">В следующих разделах атрибуты, дочерние элементы и родительский элемент `FormatString` элемент.</span><span class="sxs-lookup"><span data-stu-id="9f674-107">The following sections describe the attributes, child elements, and the parent element of the `FormatString` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9f674-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9f674-108">Attributes</span></span>

<span data-ttu-id="9f674-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="9f674-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9f674-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9f674-110">Child Elements</span></span>

<span data-ttu-id="9f674-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="9f674-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="9f674-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9f674-112">Parent Elements</span></span>

|<span data-ttu-id="9f674-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="9f674-113">Element</span></span>|<span data-ttu-id="9f674-114">Описание</span><span class="sxs-lookup"><span data-stu-id="9f674-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9f674-115">Элемент ListItem (формат)</span><span class="sxs-lookup"><span data-stu-id="9f674-115">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="9f674-116">Определяет свойство или скрипта, значение которого отображается в строке в представлении списка.</span><span class="sxs-lookup"><span data-stu-id="9f674-116">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="9f674-117">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="9f674-117">Text Value</span></span>

<span data-ttu-id="9f674-118">Укажите шаблон, используемый для форматирования данных.</span><span class="sxs-lookup"><span data-stu-id="9f674-118">Specify the pattern that is used to format the data.</span></span> <span data-ttu-id="9f674-119">Например, можно использовать этот шаблон для форматирования значения любого свойства, который относится к типу [System.Timespan](/dotnet/api/System.TimeSpan): {0: MMM} {0:dd} {0:HH}: {0: mm}.</span><span class="sxs-lookup"><span data-stu-id="9f674-119">For example, you can use this pattern to format the value of any property that is of type [System.Timespan](/dotnet/api/System.TimeSpan): {0:MMM}{0:dd}{0:HH}:{0:mm}.</span></span>

## <a name="remarks"></a><span data-ttu-id="9f674-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="9f674-120">Remarks</span></span>

<span data-ttu-id="9f674-121">Строки формата может использоваться при создании представления таблиц, представлений списков, широкие представления или представления.</span><span class="sxs-lookup"><span data-stu-id="9f674-121">Format strings can be used when creating table views, list views, wide views, or custom views.</span></span> <span data-ttu-id="9f674-122">Дополнительные сведения о форматировании значения, отображаемого в представлении см. в разделе [форматирования отображаемых данных](./formatting-displayed-data.md).</span><span class="sxs-lookup"><span data-stu-id="9f674-122">For more information about formatting a value displayed in a view, see [Formatting Displayed Data](./formatting-displayed-data.md).</span></span>

<span data-ttu-id="9f674-123">Дополнительные сведения об использовании строк формата в представлениях списка см. в разделе [Создание представления списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="9f674-123">For more information about using format strings in list views, see [Creating List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="9f674-124">Пример</span><span class="sxs-lookup"><span data-stu-id="9f674-124">Example</span></span>

<span data-ttu-id="9f674-125">Приведенный ниже показано, как определить строку форматирования для значения `StartTime` свойство.</span><span class="sxs-lookup"><span data-stu-id="9f674-125">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<ListItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</ListItem>
```

## <a name="see-also"></a><span data-ttu-id="9f674-126">См. также</span><span class="sxs-lookup"><span data-stu-id="9f674-126">See Also</span></span>

[<span data-ttu-id="9f674-127">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="9f674-127">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="9f674-128">Элемент ListItem (формат)</span><span class="sxs-lookup"><span data-stu-id="9f674-128">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="9f674-129">Написание форматирования Windows PowerShell и типы файлов</span><span class="sxs-lookup"><span data-stu-id="9f674-129">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
