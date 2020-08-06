---
title: Элемент Видинтриес для Видеконтрол (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 74383b288c945008c1d7b5119363a166c04802ae
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785053"
---
# <a name="wideentries-element-for-widecontrol-format"></a><span data-ttu-id="300d6-102">Элемент WideEntries для WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="300d6-102">WideEntries Element for WideControl (Format)</span></span>

<span data-ttu-id="300d6-103">Предоставляет определения расширенного представления.</span><span class="sxs-lookup"><span data-stu-id="300d6-103">Provides the definitions of the wide view.</span></span> <span data-ttu-id="300d6-104">В расширенном представлении должно быть указано одно или несколько определений.</span><span class="sxs-lookup"><span data-stu-id="300d6-104">The wide view must specify one or more definitions.</span></span>

<span data-ttu-id="300d6-105">Элемент конфигурации (Format) Виевдефинитионс элемента представления (Format) элемент (формат) Видеконтрол элемент (Format) Видинтриес (формат)</span><span class="sxs-lookup"><span data-stu-id="300d6-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="300d6-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="300d6-106">Syntax</span></span>

```xml
<WideEntries>
  <WideEntry>...</WideEntry>
</WideEntries>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="300d6-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="300d6-107">Attributes and Elements</span></span>

<span data-ttu-id="300d6-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `WideEntries` элемента.</span><span class="sxs-lookup"><span data-stu-id="300d6-108">The following sections describe the attributes, child elements, and parent element of the `WideEntries` element.</span></span> <span data-ttu-id="300d6-109">Необходимо указать по крайней мере один дочерний элемент.</span><span class="sxs-lookup"><span data-stu-id="300d6-109">At least one child element must be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="300d6-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="300d6-110">Attributes</span></span>

<span data-ttu-id="300d6-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="300d6-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="300d6-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="300d6-112">Child Elements</span></span>

|<span data-ttu-id="300d6-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="300d6-113">Element</span></span>|<span data-ttu-id="300d6-114">Описание</span><span class="sxs-lookup"><span data-stu-id="300d6-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="300d6-115">Элемент Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="300d6-115">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)|<span data-ttu-id="300d6-116">Предоставляет определение расширенного представления.</span><span class="sxs-lookup"><span data-stu-id="300d6-116">Provides a definition of the wide view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="300d6-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="300d6-117">Parent Elements</span></span>

|<span data-ttu-id="300d6-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="300d6-118">Element</span></span>|<span data-ttu-id="300d6-119">Описание</span><span class="sxs-lookup"><span data-stu-id="300d6-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="300d6-120">Элемент WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="300d6-120">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)|<span data-ttu-id="300d6-121">Определяет для представления широкий формат списка (одно значение).</span><span class="sxs-lookup"><span data-stu-id="300d6-121">Defines a wide (single value) list format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="300d6-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="300d6-122">Remarks</span></span>

<span data-ttu-id="300d6-123">Расширенное представление — это формат списка, который отображает одно значение свойства или значение скрипта для каждого объекта.</span><span class="sxs-lookup"><span data-stu-id="300d6-123">A wide view is a list format that displays a single property value or script value for each object.</span></span> <span data-ttu-id="300d6-124">Дополнительные сведения о компонентах широкого представления см. в разделе [широкие компоненты представления](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="300d6-124">For more information about the components of a wide view, see [Wide View Components](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="300d6-125">Пример</span><span class="sxs-lookup"><span data-stu-id="300d6-125">Example</span></span>

<span data-ttu-id="300d6-126">В следующем примере показан `WideEntries` элемент, определяющий один `WideEntry` элемент.</span><span class="sxs-lookup"><span data-stu-id="300d6-126">The following example shows a `WideEntries` element that defines a single `WideEntry` element.</span></span> <span data-ttu-id="300d6-127">`WideEntry`Элемент содержит единственный `WideItem` элемент, который определяет, какое свойство или значение скрипта отображается в представлении.</span><span class="sxs-lookup"><span data-stu-id="300d6-127">The `WideEntry` element contains a single `WideItem` element that defines what property or script value is displayed in the view.</span></span>

```xml
<WideControl>
  <WideEntries>
    <WideEntry>
      <WideItem>...</WideItem>
    <WideEntry>
  </WideEntries>
</WideControl>
```

<span data-ttu-id="300d6-128">Полный пример расширенного представления см. в разделе [широкие представления (базовый)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="300d6-128">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="300d6-129">См. также</span><span class="sxs-lookup"><span data-stu-id="300d6-129">See Also</span></span>

[<span data-ttu-id="300d6-130">Создание широкого представления</span><span class="sxs-lookup"><span data-stu-id="300d6-130">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="300d6-131">Элемент WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="300d6-131">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)

[<span data-ttu-id="300d6-132">Элемент Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="300d6-132">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)

[<span data-ttu-id="300d6-133">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="300d6-133">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
