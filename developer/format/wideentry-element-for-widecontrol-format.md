---
title: Элемент WideEntry для WideControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 014763cb-7716-4931-899c-8375b5d7a3dd
caps.latest.revision: 15
ms.openlocfilehash: d1d13b5c3436871053353814293d9163ea13c7fb
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083677"
---
# <a name="wideentry-element-for-widecontrol-format"></a><span data-ttu-id="74b04-102">Элемент WideEntry для WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="74b04-102">WideEntry Element for WideControl (Format)</span></span>

<span data-ttu-id="74b04-103">Предоставляет определение широкое представление.</span><span class="sxs-lookup"><span data-stu-id="74b04-103">Provides a definition of the wide view.</span></span>

<span data-ttu-id="74b04-104">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) элемент WideControl (формат) элемент WideEntries (формат) WideEntry элемент конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="74b04-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="74b04-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="74b04-105">Syntax</span></span>

```xml
<WideEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <WideItem>...</WideItem>
</WideEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="74b04-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="74b04-106">Attributes and Elements</span></span>

<span data-ttu-id="74b04-107">В следующих разделах атрибуты, дочерние элементы и родительский элемент `WideEntry` элемент.</span><span class="sxs-lookup"><span data-stu-id="74b04-107">The following sections describe the attributes, child elements, and the parent element of the `WideEntry` element.</span></span> <span data-ttu-id="74b04-108">Необходимо указать один `WideItem` дочерний элемент.</span><span class="sxs-lookup"><span data-stu-id="74b04-108">You must specify a single `WideItem` child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="74b04-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="74b04-109">Attributes</span></span>

<span data-ttu-id="74b04-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="74b04-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="74b04-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="74b04-111">Child Elements</span></span>

|<span data-ttu-id="74b04-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="74b04-112">Element</span></span>|<span data-ttu-id="74b04-113">Описание</span><span class="sxs-lookup"><span data-stu-id="74b04-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="74b04-114">Элемент EntrySelectedBy для WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="74b04-114">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)|<span data-ttu-id="74b04-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="74b04-115">Optional element.</span></span><br /><br /> <span data-ttu-id="74b04-116">Определяет типы .NET, которые используют это определение расширенных запись или условие, которое должен существовать для данного определения для использования.</span><span class="sxs-lookup"><span data-stu-id="74b04-116">Defines the .NET types that use this wide entry definition or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="74b04-117">Элемент WideItem (формат)</span><span class="sxs-lookup"><span data-stu-id="74b04-117">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="74b04-118">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="74b04-118">Required element.</span></span><br /><br /> <span data-ttu-id="74b04-119">Определяет свойство или скрипта, значение которого отображается.</span><span class="sxs-lookup"><span data-stu-id="74b04-119">Defines the property or script whose value is displayed.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="74b04-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="74b04-120">Parent Elements</span></span>

|<span data-ttu-id="74b04-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="74b04-121">Element</span></span>|<span data-ttu-id="74b04-122">Описание</span><span class="sxs-lookup"><span data-stu-id="74b04-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="74b04-123">Элемент WideEntries (формат)</span><span class="sxs-lookup"><span data-stu-id="74b04-123">WideEntries Element (Format)</span></span>](./wideentries-element-for-widecontrol-format.md)|<span data-ttu-id="74b04-124">Предоставляет определения широкое представление.</span><span class="sxs-lookup"><span data-stu-id="74b04-124">Provides the definitions of the wide view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="74b04-125">Замечания</span><span class="sxs-lookup"><span data-stu-id="74b04-125">Remarks</span></span>

<span data-ttu-id="74b04-126">Широкое представление — это формат списка, который отображает значение одного свойства или значение скрипта для каждого объекта.</span><span class="sxs-lookup"><span data-stu-id="74b04-126">A wide view is a list format that displays a single property value or script value for each object.</span></span> <span data-ttu-id="74b04-127">В отличие от других типов представлений можно указать только один элемент для каждого определения представления.</span><span class="sxs-lookup"><span data-stu-id="74b04-127">Unlike other types of views, you can specify only one item element for each view definition.</span></span> <span data-ttu-id="74b04-128">Дополнительные сведения о других компонентах широкое представление, см. в разделе [Создание широкое представление](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="74b04-128">For more information about the other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="74b04-129">Пример</span><span class="sxs-lookup"><span data-stu-id="74b04-129">Example</span></span>

<span data-ttu-id="74b04-130">В следующем примере показан `WideEntry` элемент, который определяет одно `WideItem` элемент.</span><span class="sxs-lookup"><span data-stu-id="74b04-130">The following example shows a `WideEntry` element that defines a single `WideItem` element.</span></span> <span data-ttu-id="74b04-131">`WideItem` Элемент определяет свойство, значение которого отображается в представлении.</span><span class="sxs-lookup"><span data-stu-id="74b04-131">The `WideItem` element defines the property whose value is displayed in the view.</span></span>

```xml
<WideEntries>
  <WideEntry>
    <WideItem>
      <PropertyName>ProcessName</PropertyName>
    </WideItem>
  </WideEntry>
</WideEntries>

```

<span data-ttu-id="74b04-132">Полный пример широкое представление, см. в разделе [широкое представление (Basic)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="74b04-132">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="74b04-133">См. также</span><span class="sxs-lookup"><span data-stu-id="74b04-133">See Also</span></span>

[<span data-ttu-id="74b04-134">Создание широкое представление</span><span class="sxs-lookup"><span data-stu-id="74b04-134">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="74b04-135">Элемент SelectionCondition для WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="74b04-135">SelectionCondition Element for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="74b04-136">Элемент SelectionSetName для WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="74b04-136">SelectionSetName Element for WideEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="74b04-137">TypeName-элемент для WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="74b04-137">TypeName Element for WideEntry (Format)</span></span>](./typename-element-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="74b04-138">Элемент WideEntries (формат)</span><span class="sxs-lookup"><span data-stu-id="74b04-138">WideEntries Element (Format)</span></span>](./wideentries-element-for-widecontrol-format.md)

[<span data-ttu-id="74b04-139">Элемент WideItem (формат)</span><span class="sxs-lookup"><span data-stu-id="74b04-139">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="74b04-140">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="74b04-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
