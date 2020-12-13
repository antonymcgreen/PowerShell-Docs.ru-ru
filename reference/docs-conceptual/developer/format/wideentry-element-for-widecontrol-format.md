---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент WideEntry для WideControl (формат)
description: Элемент WideEntry для WideControl (формат)
ms.openlocfilehash: 3faaf767d11914792effd6765beed956a502c642
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664540"
---
# <a name="wideentry-element-for-widecontrol-format"></a><span data-ttu-id="ccd01-103">Элемент WideEntry для WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="ccd01-103">WideEntry Element for WideControl (Format)</span></span>

<span data-ttu-id="ccd01-104">Предоставляет определение расширенного представления.</span><span class="sxs-lookup"><span data-stu-id="ccd01-104">Provides a definition of the wide view.</span></span>

<span data-ttu-id="ccd01-105">Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) Видеконтрол элемент (Format) Видинтриес элемент (Format) Видинтри элемент (Format)</span><span class="sxs-lookup"><span data-stu-id="ccd01-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ccd01-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ccd01-106">Syntax</span></span>

```xml
<WideEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <WideItem>...</WideItem>
</WideEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ccd01-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ccd01-107">Attributes and Elements</span></span>

<span data-ttu-id="ccd01-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `WideEntry` элемента.</span><span class="sxs-lookup"><span data-stu-id="ccd01-108">The following sections describe the attributes, child elements, and the parent element of the `WideEntry` element.</span></span> <span data-ttu-id="ccd01-109">Необходимо указать один `WideItem` дочерний элемент.</span><span class="sxs-lookup"><span data-stu-id="ccd01-109">You must specify a single `WideItem` child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ccd01-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ccd01-110">Attributes</span></span>

<span data-ttu-id="ccd01-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ccd01-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ccd01-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ccd01-112">Child Elements</span></span>

|<span data-ttu-id="ccd01-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="ccd01-113">Element</span></span>|<span data-ttu-id="ccd01-114">Описание</span><span class="sxs-lookup"><span data-stu-id="ccd01-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ccd01-115">Элемент EntrySelectedBy для элемента WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="ccd01-115">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)|<span data-ttu-id="ccd01-116">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="ccd01-116">Optional element.</span></span><br /><br /> <span data-ttu-id="ccd01-117">Определяет типы .NET, которые используют определение расширенной записи или условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="ccd01-117">Defines the .NET types that use this wide entry definition or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="ccd01-118">Элемент Видеитем (Format)</span><span class="sxs-lookup"><span data-stu-id="ccd01-118">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="ccd01-119">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="ccd01-119">Required element.</span></span><br /><br /> <span data-ttu-id="ccd01-120">Определяет свойство или скрипт, значение которого отображается.</span><span class="sxs-lookup"><span data-stu-id="ccd01-120">Defines the property or script whose value is displayed.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="ccd01-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ccd01-121">Parent Elements</span></span>

|<span data-ttu-id="ccd01-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="ccd01-122">Element</span></span>|<span data-ttu-id="ccd01-123">Описание</span><span class="sxs-lookup"><span data-stu-id="ccd01-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ccd01-124">Элемент Видинтриес (Format)</span><span class="sxs-lookup"><span data-stu-id="ccd01-124">WideEntries Element (Format)</span></span>](./wideentries-element-for-widecontrol-format.md)|<span data-ttu-id="ccd01-125">Предоставляет определения расширенного представления.</span><span class="sxs-lookup"><span data-stu-id="ccd01-125">Provides the definitions of the wide view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ccd01-126">Комментарии</span><span class="sxs-lookup"><span data-stu-id="ccd01-126">Remarks</span></span>

<span data-ttu-id="ccd01-127">Расширенное представление — это формат списка, который отображает одно значение свойства или значение скрипта для каждого объекта.</span><span class="sxs-lookup"><span data-stu-id="ccd01-127">A wide view is a list format that displays a single property value or script value for each object.</span></span> <span data-ttu-id="ccd01-128">В отличие от других типов представлений, для каждого определения представления можно указать только один элемент Item.</span><span class="sxs-lookup"><span data-stu-id="ccd01-128">Unlike other types of views, you can specify only one item element for each view definition.</span></span> <span data-ttu-id="ccd01-129">Дополнительные сведения о других компонентах расширенного представления см. в разделе [Создание расширенного представления](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="ccd01-129">For more information about the other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="ccd01-130">Пример</span><span class="sxs-lookup"><span data-stu-id="ccd01-130">Example</span></span>

<span data-ttu-id="ccd01-131">В следующем примере показан `WideEntry` элемент, определяющий один `WideItem` элемент.</span><span class="sxs-lookup"><span data-stu-id="ccd01-131">The following example shows a `WideEntry` element that defines a single `WideItem` element.</span></span> <span data-ttu-id="ccd01-132">`WideItem`Элемент определяет свойство, значение которого отображается в представлении.</span><span class="sxs-lookup"><span data-stu-id="ccd01-132">The `WideItem` element defines the property whose value is displayed in the view.</span></span>

```xml
<WideEntries>
  <WideEntry>
    <WideItem>
      <PropertyName>ProcessName</PropertyName>
    </WideItem>
  </WideEntry>
</WideEntries>

```

<span data-ttu-id="ccd01-133">Полный пример расширенного представления см. в разделе [широкие представления (базовый)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="ccd01-133">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ccd01-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="ccd01-134">See Also</span></span>

[<span data-ttu-id="ccd01-135">Создание широкого представления</span><span class="sxs-lookup"><span data-stu-id="ccd01-135">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="ccd01-136">Элемент Селектионкондитион для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="ccd01-136">SelectionCondition Element for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="ccd01-137">Элемент Селектионсетнаме для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="ccd01-137">SelectionSetName Element for WideEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="ccd01-138">Элемент TypeName для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="ccd01-138">TypeName Element for WideEntry (Format)</span></span>](./typename-element-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="ccd01-139">Элемент Видинтриес (Format)</span><span class="sxs-lookup"><span data-stu-id="ccd01-139">WideEntries Element (Format)</span></span>](./wideentries-element-for-widecontrol-format.md)

[<span data-ttu-id="ccd01-140">Элемент Видеитем (Format)</span><span class="sxs-lookup"><span data-stu-id="ccd01-140">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="ccd01-141">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="ccd01-141">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
