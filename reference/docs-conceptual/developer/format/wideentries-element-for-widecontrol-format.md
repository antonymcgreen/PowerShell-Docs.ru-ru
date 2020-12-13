---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент WideEntries для WideControl (формат)
description: Элемент WideEntries для WideControl (формат)
ms.openlocfilehash: 567b8acdd0d2e8d5daaef2c31b4fe4ce38c23a47
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651243"
---
# <a name="wideentries-element-for-widecontrol-format"></a><span data-ttu-id="72a57-103">Элемент WideEntries для WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="72a57-103">WideEntries Element for WideControl (Format)</span></span>

<span data-ttu-id="72a57-104">Предоставляет определения расширенного представления.</span><span class="sxs-lookup"><span data-stu-id="72a57-104">Provides the definitions of the wide view.</span></span> <span data-ttu-id="72a57-105">В расширенном представлении должно быть указано одно или несколько определений.</span><span class="sxs-lookup"><span data-stu-id="72a57-105">The wide view must specify one or more definitions.</span></span>

<span data-ttu-id="72a57-106">Элемент конфигурации (Format) Виевдефинитионс элемента представления (Format) элемент (формат) Видеконтрол элемент (Format) Видинтриес (формат)</span><span class="sxs-lookup"><span data-stu-id="72a57-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="72a57-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="72a57-107">Syntax</span></span>

```xml
<WideEntries>
  <WideEntry>...</WideEntry>
</WideEntries>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="72a57-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="72a57-108">Attributes and Elements</span></span>

<span data-ttu-id="72a57-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `WideEntries` элемента.</span><span class="sxs-lookup"><span data-stu-id="72a57-109">The following sections describe the attributes, child elements, and parent element of the `WideEntries` element.</span></span> <span data-ttu-id="72a57-110">Необходимо указать по крайней мере один дочерний элемент.</span><span class="sxs-lookup"><span data-stu-id="72a57-110">At least one child element must be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="72a57-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="72a57-111">Attributes</span></span>

<span data-ttu-id="72a57-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="72a57-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="72a57-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="72a57-113">Child Elements</span></span>

|<span data-ttu-id="72a57-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="72a57-114">Element</span></span>|<span data-ttu-id="72a57-115">Описание</span><span class="sxs-lookup"><span data-stu-id="72a57-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="72a57-116">Элемент Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="72a57-116">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)|<span data-ttu-id="72a57-117">Предоставляет определение расширенного представления.</span><span class="sxs-lookup"><span data-stu-id="72a57-117">Provides a definition of the wide view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="72a57-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="72a57-118">Parent Elements</span></span>

|<span data-ttu-id="72a57-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="72a57-119">Element</span></span>|<span data-ttu-id="72a57-120">Описание</span><span class="sxs-lookup"><span data-stu-id="72a57-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="72a57-121">Элемент WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="72a57-121">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)|<span data-ttu-id="72a57-122">Определяет для представления широкий формат списка (одно значение).</span><span class="sxs-lookup"><span data-stu-id="72a57-122">Defines a wide (single value) list format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="72a57-123">Комментарии</span><span class="sxs-lookup"><span data-stu-id="72a57-123">Remarks</span></span>

<span data-ttu-id="72a57-124">Расширенное представление — это формат списка, который отображает одно значение свойства или значение скрипта для каждого объекта.</span><span class="sxs-lookup"><span data-stu-id="72a57-124">A wide view is a list format that displays a single property value or script value for each object.</span></span> <span data-ttu-id="72a57-125">Дополнительные сведения о компонентах широкого представления см. в разделе [широкие компоненты представления](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="72a57-125">For more information about the components of a wide view, see [Wide View Components](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="72a57-126">Пример</span><span class="sxs-lookup"><span data-stu-id="72a57-126">Example</span></span>

<span data-ttu-id="72a57-127">В следующем примере показан `WideEntries` элемент, определяющий один `WideEntry` элемент.</span><span class="sxs-lookup"><span data-stu-id="72a57-127">The following example shows a `WideEntries` element that defines a single `WideEntry` element.</span></span> <span data-ttu-id="72a57-128">`WideEntry`Элемент содержит единственный `WideItem` элемент, который определяет, какое свойство или значение скрипта отображается в представлении.</span><span class="sxs-lookup"><span data-stu-id="72a57-128">The `WideEntry` element contains a single `WideItem` element that defines what property or script value is displayed in the view.</span></span>

```xml
<WideControl>
  <WideEntries>
    <WideEntry>
      <WideItem>...</WideItem>
    <WideEntry>
  </WideEntries>
</WideControl>
```

<span data-ttu-id="72a57-129">Полный пример расширенного представления см. в разделе [широкие представления (базовый)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="72a57-129">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="72a57-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="72a57-130">See Also</span></span>

[<span data-ttu-id="72a57-131">Создание широкого представления</span><span class="sxs-lookup"><span data-stu-id="72a57-131">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="72a57-132">Элемент WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="72a57-132">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)

[<span data-ttu-id="72a57-133">Элемент Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="72a57-133">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)

[<span data-ttu-id="72a57-134">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="72a57-134">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
