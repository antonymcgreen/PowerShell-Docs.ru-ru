---
title: Элемент Видинтри для Видеконтрол (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 13dd1f6ad7ac1e9d8d0524f0a0f18fe80ffaf8e2
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780021"
---
# <a name="wideentry-element-for-widecontrol-format"></a><span data-ttu-id="89818-102">Элемент WideEntry для WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="89818-102">WideEntry Element for WideControl (Format)</span></span>

<span data-ttu-id="89818-103">Предоставляет определение расширенного представления.</span><span class="sxs-lookup"><span data-stu-id="89818-103">Provides a definition of the wide view.</span></span>

<span data-ttu-id="89818-104">Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) Видеконтрол элемент (Format) Видинтриес элемент (Format) Видинтри элемент (Format)</span><span class="sxs-lookup"><span data-stu-id="89818-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="89818-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="89818-105">Syntax</span></span>

```xml
<WideEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <WideItem>...</WideItem>
</WideEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="89818-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="89818-106">Attributes and Elements</span></span>

<span data-ttu-id="89818-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `WideEntry` элемента.</span><span class="sxs-lookup"><span data-stu-id="89818-107">The following sections describe the attributes, child elements, and the parent element of the `WideEntry` element.</span></span> <span data-ttu-id="89818-108">Необходимо указать один `WideItem` дочерний элемент.</span><span class="sxs-lookup"><span data-stu-id="89818-108">You must specify a single `WideItem` child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="89818-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="89818-109">Attributes</span></span>

<span data-ttu-id="89818-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="89818-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="89818-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="89818-111">Child Elements</span></span>

|<span data-ttu-id="89818-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="89818-112">Element</span></span>|<span data-ttu-id="89818-113">Описание</span><span class="sxs-lookup"><span data-stu-id="89818-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="89818-114">Элемент EntrySelectedBy для элемента WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="89818-114">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)|<span data-ttu-id="89818-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="89818-115">Optional element.</span></span><br /><br /> <span data-ttu-id="89818-116">Определяет типы .NET, которые используют определение расширенной записи или условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="89818-116">Defines the .NET types that use this wide entry definition or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="89818-117">Элемент Видеитем (Format)</span><span class="sxs-lookup"><span data-stu-id="89818-117">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="89818-118">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="89818-118">Required element.</span></span><br /><br /> <span data-ttu-id="89818-119">Определяет свойство или скрипт, значение которого отображается.</span><span class="sxs-lookup"><span data-stu-id="89818-119">Defines the property or script whose value is displayed.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="89818-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="89818-120">Parent Elements</span></span>

|<span data-ttu-id="89818-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="89818-121">Element</span></span>|<span data-ttu-id="89818-122">Описание</span><span class="sxs-lookup"><span data-stu-id="89818-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="89818-123">Элемент Видинтриес (Format)</span><span class="sxs-lookup"><span data-stu-id="89818-123">WideEntries Element (Format)</span></span>](./wideentries-element-for-widecontrol-format.md)|<span data-ttu-id="89818-124">Предоставляет определения расширенного представления.</span><span class="sxs-lookup"><span data-stu-id="89818-124">Provides the definitions of the wide view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="89818-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="89818-125">Remarks</span></span>

<span data-ttu-id="89818-126">Расширенное представление — это формат списка, который отображает одно значение свойства или значение скрипта для каждого объекта.</span><span class="sxs-lookup"><span data-stu-id="89818-126">A wide view is a list format that displays a single property value or script value for each object.</span></span> <span data-ttu-id="89818-127">В отличие от других типов представлений, для каждого определения представления можно указать только один элемент Item.</span><span class="sxs-lookup"><span data-stu-id="89818-127">Unlike other types of views, you can specify only one item element for each view definition.</span></span> <span data-ttu-id="89818-128">Дополнительные сведения о других компонентах расширенного представления см. в разделе [Создание расширенного представления](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="89818-128">For more information about the other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="89818-129">Пример</span><span class="sxs-lookup"><span data-stu-id="89818-129">Example</span></span>

<span data-ttu-id="89818-130">В следующем примере показан `WideEntry` элемент, определяющий один `WideItem` элемент.</span><span class="sxs-lookup"><span data-stu-id="89818-130">The following example shows a `WideEntry` element that defines a single `WideItem` element.</span></span> <span data-ttu-id="89818-131">`WideItem`Элемент определяет свойство, значение которого отображается в представлении.</span><span class="sxs-lookup"><span data-stu-id="89818-131">The `WideItem` element defines the property whose value is displayed in the view.</span></span>

```xml
<WideEntries>
  <WideEntry>
    <WideItem>
      <PropertyName>ProcessName</PropertyName>
    </WideItem>
  </WideEntry>
</WideEntries>

```

<span data-ttu-id="89818-132">Полный пример расширенного представления см. в разделе [широкие представления (базовый)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="89818-132">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="89818-133">См. также</span><span class="sxs-lookup"><span data-stu-id="89818-133">See Also</span></span>

[<span data-ttu-id="89818-134">Создание широкого представления</span><span class="sxs-lookup"><span data-stu-id="89818-134">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="89818-135">Элемент Селектионкондитион для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="89818-135">SelectionCondition Element for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="89818-136">Элемент Селектионсетнаме для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="89818-136">SelectionSetName Element for WideEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="89818-137">Элемент TypeName для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="89818-137">TypeName Element for WideEntry (Format)</span></span>](./typename-element-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="89818-138">Элемент Видинтриес (Format)</span><span class="sxs-lookup"><span data-stu-id="89818-138">WideEntries Element (Format)</span></span>](./wideentries-element-for-widecontrol-format.md)

[<span data-ttu-id="89818-139">Элемент Видеитем (Format)</span><span class="sxs-lookup"><span data-stu-id="89818-139">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="89818-140">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="89818-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
