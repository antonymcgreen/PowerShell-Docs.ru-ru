---
title: Элемент Видинтри для Видеконтрол (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 014763cb-7716-4931-899c-8375b5d7a3dd
caps.latest.revision: 15
ms.openlocfilehash: d1d13b5c3436871053353814293d9163ea13c7fb
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72367903"
---
# <a name="wideentry-element-for-widecontrol-format"></a><span data-ttu-id="878ed-102">Элемент WideEntry для WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="878ed-102">WideEntry Element for WideControl (Format)</span></span>

<span data-ttu-id="878ed-103">Предоставляет определение расширенного представления.</span><span class="sxs-lookup"><span data-stu-id="878ed-103">Provides a definition of the wide view.</span></span>

<span data-ttu-id="878ed-104">Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) Видеконтрол элемент (Format) Видинтриес элемент (Format) Видинтри элемент (Format)</span><span class="sxs-lookup"><span data-stu-id="878ed-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="878ed-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="878ed-105">Syntax</span></span>

```xml
<WideEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <WideItem>...</WideItem>
</WideEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="878ed-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="878ed-106">Attributes and Elements</span></span>

<span data-ttu-id="878ed-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `WideEntry`.</span><span class="sxs-lookup"><span data-stu-id="878ed-107">The following sections describe the attributes, child elements, and the parent element of the `WideEntry` element.</span></span> <span data-ttu-id="878ed-108">Необходимо указать один дочерний элемент `WideItem`.</span><span class="sxs-lookup"><span data-stu-id="878ed-108">You must specify a single `WideItem` child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="878ed-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="878ed-109">Attributes</span></span>

<span data-ttu-id="878ed-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="878ed-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="878ed-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="878ed-111">Child Elements</span></span>

|<span data-ttu-id="878ed-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="878ed-112">Element</span></span>|<span data-ttu-id="878ed-113">Описание</span><span class="sxs-lookup"><span data-stu-id="878ed-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="878ed-114">Элемент Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="878ed-114">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)|<span data-ttu-id="878ed-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="878ed-115">Optional element.</span></span><br /><br /> <span data-ttu-id="878ed-116">Определяет типы .NET, которые используют определение расширенной записи или условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="878ed-116">Defines the .NET types that use this wide entry definition or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="878ed-117">Элемент Видеитем (Format)</span><span class="sxs-lookup"><span data-stu-id="878ed-117">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="878ed-118">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="878ed-118">Required element.</span></span><br /><br /> <span data-ttu-id="878ed-119">Определяет свойство или скрипт, значение которого отображается.</span><span class="sxs-lookup"><span data-stu-id="878ed-119">Defines the property or script whose value is displayed.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="878ed-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="878ed-120">Parent Elements</span></span>

|<span data-ttu-id="878ed-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="878ed-121">Element</span></span>|<span data-ttu-id="878ed-122">Описание</span><span class="sxs-lookup"><span data-stu-id="878ed-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="878ed-123">Элемент Видинтриес (Format)</span><span class="sxs-lookup"><span data-stu-id="878ed-123">WideEntries Element (Format)</span></span>](./wideentries-element-for-widecontrol-format.md)|<span data-ttu-id="878ed-124">Предоставляет определения расширенного представления.</span><span class="sxs-lookup"><span data-stu-id="878ed-124">Provides the definitions of the wide view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="878ed-125">Замечания</span><span class="sxs-lookup"><span data-stu-id="878ed-125">Remarks</span></span>

<span data-ttu-id="878ed-126">Расширенное представление — это формат списка, который отображает одно значение свойства или значение скрипта для каждого объекта.</span><span class="sxs-lookup"><span data-stu-id="878ed-126">A wide view is a list format that displays a single property value or script value for each object.</span></span> <span data-ttu-id="878ed-127">В отличие от других типов представлений, для каждого определения представления можно указать только один элемент Item.</span><span class="sxs-lookup"><span data-stu-id="878ed-127">Unlike other types of views, you can specify only one item element for each view definition.</span></span> <span data-ttu-id="878ed-128">Дополнительные сведения о других компонентах расширенного представления см. в разделе [Создание расширенного представления](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="878ed-128">For more information about the other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="878ed-129">Пример</span><span class="sxs-lookup"><span data-stu-id="878ed-129">Example</span></span>

<span data-ttu-id="878ed-130">В следующем примере показан элемент `WideEntry`, определяющий один элемент `WideItem`.</span><span class="sxs-lookup"><span data-stu-id="878ed-130">The following example shows a `WideEntry` element that defines a single `WideItem` element.</span></span> <span data-ttu-id="878ed-131">Элемент `WideItem` определяет свойство, значение которого отображается в представлении.</span><span class="sxs-lookup"><span data-stu-id="878ed-131">The `WideItem` element defines the property whose value is displayed in the view.</span></span>

```xml
<WideEntries>
  <WideEntry>
    <WideItem>
      <PropertyName>ProcessName</PropertyName>
    </WideItem>
  </WideEntry>
</WideEntries>

```

<span data-ttu-id="878ed-132">Полный пример расширенного представления см. в разделе [широкие представления (базовый)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="878ed-132">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="878ed-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="878ed-133">See Also</span></span>

[<span data-ttu-id="878ed-134">Создание расширенного представления</span><span class="sxs-lookup"><span data-stu-id="878ed-134">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="878ed-135">Элемент Селектионкондитион для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="878ed-135">SelectionCondition Element for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="878ed-136">Элемент Селектионсетнаме для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="878ed-136">SelectionSetName Element for WideEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="878ed-137">Элемент TypeName для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="878ed-137">TypeName Element for WideEntry (Format)</span></span>](./typename-element-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="878ed-138">Элемент Видинтриес (Format)</span><span class="sxs-lookup"><span data-stu-id="878ed-138">WideEntries Element (Format)</span></span>](./wideentries-element-for-widecontrol-format.md)

[<span data-ttu-id="878ed-139">Элемент Видеитем (Format)</span><span class="sxs-lookup"><span data-stu-id="878ed-139">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="878ed-140">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="878ed-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
