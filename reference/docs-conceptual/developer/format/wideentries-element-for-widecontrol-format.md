---
title: Элемент Видинтриес для Видеконтрол (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0c4bff45-0960-4b3a-95e7-47f2cee03ac5
caps.latest.revision: 12
ms.openlocfilehash: 083f3c8df8136858e32778ed231943ef983e47aa
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361433"
---
# <a name="wideentries-element-for-widecontrol-format"></a><span data-ttu-id="91a3c-102">Элемент WideEntries для WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="91a3c-102">WideEntries Element for WideControl (Format)</span></span>

<span data-ttu-id="91a3c-103">Предоставляет определения расширенного представления.</span><span class="sxs-lookup"><span data-stu-id="91a3c-103">Provides the definitions of the wide view.</span></span> <span data-ttu-id="91a3c-104">В расширенном представлении должно быть указано одно или несколько определений.</span><span class="sxs-lookup"><span data-stu-id="91a3c-104">The wide view must specify one or more definitions.</span></span>

<span data-ttu-id="91a3c-105">Элемент конфигурации (Format) Виевдефинитионс элемента представления (Format) элемент (формат) Видеконтрол элемент (Format) Видинтриес (формат)</span><span class="sxs-lookup"><span data-stu-id="91a3c-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="91a3c-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="91a3c-106">Syntax</span></span>

```xml
<WideEntries>
  <WideEntry>...</WideEntry>
</WideEntries>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="91a3c-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="91a3c-107">Attributes and Elements</span></span>

<span data-ttu-id="91a3c-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `WideEntries`.</span><span class="sxs-lookup"><span data-stu-id="91a3c-108">The following sections describe the attributes, child elements, and parent element of the `WideEntries` element.</span></span> <span data-ttu-id="91a3c-109">Необходимо указать по крайней мере один дочерний элемент.</span><span class="sxs-lookup"><span data-stu-id="91a3c-109">At least one child element must be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="91a3c-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="91a3c-110">Attributes</span></span>

<span data-ttu-id="91a3c-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="91a3c-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="91a3c-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="91a3c-112">Child Elements</span></span>

|<span data-ttu-id="91a3c-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="91a3c-113">Element</span></span>|<span data-ttu-id="91a3c-114">Описание</span><span class="sxs-lookup"><span data-stu-id="91a3c-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="91a3c-115">Элемент Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="91a3c-115">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)|<span data-ttu-id="91a3c-116">Предоставляет определение расширенного представления.</span><span class="sxs-lookup"><span data-stu-id="91a3c-116">Provides a definition of the wide view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="91a3c-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="91a3c-117">Parent Elements</span></span>

|<span data-ttu-id="91a3c-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="91a3c-118">Element</span></span>|<span data-ttu-id="91a3c-119">Описание</span><span class="sxs-lookup"><span data-stu-id="91a3c-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="91a3c-120">Элемент Видеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="91a3c-120">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)|<span data-ttu-id="91a3c-121">Определяет для представления широкий формат списка (одно значение).</span><span class="sxs-lookup"><span data-stu-id="91a3c-121">Defines a wide (single value) list format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="91a3c-122">Замечания</span><span class="sxs-lookup"><span data-stu-id="91a3c-122">Remarks</span></span>

<span data-ttu-id="91a3c-123">Расширенное представление — это формат списка, который отображает одно значение свойства или значение скрипта для каждого объекта.</span><span class="sxs-lookup"><span data-stu-id="91a3c-123">A wide view is a list format that displays a single property value or script value for each object.</span></span> <span data-ttu-id="91a3c-124">Дополнительные сведения о компонентах широкого представления см. в разделе [широкие компоненты представления](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="91a3c-124">For more information about the components of a wide view, see [Wide View Components](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="91a3c-125">Пример</span><span class="sxs-lookup"><span data-stu-id="91a3c-125">Example</span></span>

<span data-ttu-id="91a3c-126">В следующем примере показан элемент `WideEntries`, определяющий один элемент `WideEntry`.</span><span class="sxs-lookup"><span data-stu-id="91a3c-126">The following example shows a `WideEntries` element that defines a single `WideEntry` element.</span></span> <span data-ttu-id="91a3c-127">Элемент `WideEntry` содержит один элемент `WideItem`, который определяет, какое свойство или значение скрипта отображается в представлении.</span><span class="sxs-lookup"><span data-stu-id="91a3c-127">The `WideEntry` element contains a single `WideItem` element that defines what property or script value is displayed in the view.</span></span>

```xml
<WideControl>
  <WideEntries>
    <WideEntry>
      <WideItem>...</WideItem>
    <WideEntry>
  </WideEntries>
</WideControl>
```

<span data-ttu-id="91a3c-128">Полный пример расширенного представления см. в разделе [широкие представления (базовый)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="91a3c-128">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="91a3c-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="91a3c-129">See Also</span></span>

[<span data-ttu-id="91a3c-130">Создание расширенного представления</span><span class="sxs-lookup"><span data-stu-id="91a3c-130">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="91a3c-131">Элемент Видеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="91a3c-131">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)

[<span data-ttu-id="91a3c-132">Элемент Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="91a3c-132">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)

[<span data-ttu-id="91a3c-133">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="91a3c-133">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
