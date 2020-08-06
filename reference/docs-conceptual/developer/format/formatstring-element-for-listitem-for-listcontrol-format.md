---
title: Элемент FormatString для ListItem для ListControl (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 9ec73aa1c2e8180258722627e30344de4e67bda5
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781585"
---
# <a name="formatstring-element-for-listitem-for-listcontrol--format"></a><span data-ttu-id="53fe0-102">Элемент FormatString для элемента ListItem для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="53fe0-102">FormatString Element for ListItem for ListControl  (Format)</span></span>

<span data-ttu-id="53fe0-103">Задает шаблон формата, определяющий способ отображения значения свойства или скрипта.</span><span class="sxs-lookup"><span data-stu-id="53fe0-103">Specifies a format pattern that defines how the property or script value is displayed.</span></span>

<span data-ttu-id="53fe0-104">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ListControl элемент (Format) Листентриес для ListControl (Format) Листентри элемент для ListControl (Format) элемент списка элементов для ListControl (формат) элемента ListItem для ListControl (Format) элемент списка (формат) для элемента списка (Format) ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="53fe0-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListControl (Format) ListItems Element for ListControl (Format) ListItem Element for ListControl (Format) FormatString Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="53fe0-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="53fe0-105">Syntax</span></span>

```xml
<FormatString>PropertyPattern</FormatString>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="53fe0-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="53fe0-106">Attributes and Elements</span></span>

<span data-ttu-id="53fe0-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `FormatString` элемента.</span><span class="sxs-lookup"><span data-stu-id="53fe0-107">The following sections describe the attributes, child elements, and the parent element of the `FormatString` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="53fe0-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="53fe0-108">Attributes</span></span>

<span data-ttu-id="53fe0-109">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="53fe0-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="53fe0-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="53fe0-110">Child Elements</span></span>

<span data-ttu-id="53fe0-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="53fe0-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="53fe0-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="53fe0-112">Parent Elements</span></span>

|<span data-ttu-id="53fe0-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="53fe0-113">Element</span></span>|<span data-ttu-id="53fe0-114">Описание</span><span class="sxs-lookup"><span data-stu-id="53fe0-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="53fe0-115">Элемент ListItem (Format)</span><span class="sxs-lookup"><span data-stu-id="53fe0-115">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="53fe0-116">Определяет свойство или скрипт, значение которого отображается в строке представления списка.</span><span class="sxs-lookup"><span data-stu-id="53fe0-116">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="53fe0-117">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="53fe0-117">Text Value</span></span>

<span data-ttu-id="53fe0-118">Укажите шаблон, используемый для форматирования данных.</span><span class="sxs-lookup"><span data-stu-id="53fe0-118">Specify the pattern that is used to format the data.</span></span> <span data-ttu-id="53fe0-119">Например, этот шаблон можно использовать для форматирования значения любого свойства типа [System. TimeSpan](/dotnet/api/System.TimeSpan): {0: MMM} {0: DD} {0: HH}: {0: mm}.</span><span class="sxs-lookup"><span data-stu-id="53fe0-119">For example, you can use this pattern to format the value of any property that is of type [System.Timespan](/dotnet/api/System.TimeSpan): {0:MMM}{0:dd}{0:HH}:{0:mm}.</span></span>

## <a name="remarks"></a><span data-ttu-id="53fe0-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="53fe0-120">Remarks</span></span>

<span data-ttu-id="53fe0-121">Строки формата можно использовать при создании табличных представлений, представлений списков, расширенных представлений или пользовательских представлений.</span><span class="sxs-lookup"><span data-stu-id="53fe0-121">Format strings can be used when creating table views, list views, wide views, or custom views.</span></span> <span data-ttu-id="53fe0-122">Дополнительные сведения о форматировании значения, отображаемого в представлении, см. в разделе [Форматирование отображаемых данных](./formatting-displayed-data.md).</span><span class="sxs-lookup"><span data-stu-id="53fe0-122">For more information about formatting a value displayed in a view, see [Formatting Displayed Data](./formatting-displayed-data.md).</span></span>

<span data-ttu-id="53fe0-123">Дополнительные сведения об использовании строк форматирования в представлениях списков см. в разделе [Создание представления списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="53fe0-123">For more information about using format strings in list views, see [Creating List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="53fe0-124">Пример</span><span class="sxs-lookup"><span data-stu-id="53fe0-124">Example</span></span>

<span data-ttu-id="53fe0-125">В следующем примере показано, как определить строку форматирования для значения `StartTime` Свойства.</span><span class="sxs-lookup"><span data-stu-id="53fe0-125">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<ListItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</ListItem>
```

## <a name="see-also"></a><span data-ttu-id="53fe0-126">См. также</span><span class="sxs-lookup"><span data-stu-id="53fe0-126">See Also</span></span>

[<span data-ttu-id="53fe0-127">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="53fe0-127">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="53fe0-128">Элемент ListItem (Format)</span><span class="sxs-lookup"><span data-stu-id="53fe0-128">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="53fe0-129">Создание файла форматирования и типов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="53fe0-129">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
