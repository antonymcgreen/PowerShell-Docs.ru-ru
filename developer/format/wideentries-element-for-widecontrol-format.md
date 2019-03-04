---
title: Элемент WideEntries для WideControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0c4bff45-0960-4b3a-95e7-47f2cee03ac5
caps.latest.revision: 12
ms.openlocfilehash: 083f3c8df8136858e32778ed231943ef983e47aa
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853280"
---
# <a name="wideentries-element-for-widecontrol-format"></a><span data-ttu-id="e148b-102">Элемент WideEntries для WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="e148b-102">WideEntries Element for WideControl (Format)</span></span>

<span data-ttu-id="e148b-103">Предоставляет определения широкое представление.</span><span class="sxs-lookup"><span data-stu-id="e148b-103">Provides the definitions of the wide view.</span></span> <span data-ttu-id="e148b-104">Широкое представление необходимо указать одно или несколько определений.</span><span class="sxs-lookup"><span data-stu-id="e148b-104">The wide view must specify one or more definitions.</span></span>

<span data-ttu-id="e148b-105">Элемент WideControl элемент (формат) WideEntries ViewDefinitions элемент (формат) представление конфигурации элемента (формат) элемент (формат) (формат)</span><span class="sxs-lookup"><span data-stu-id="e148b-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e148b-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e148b-106">Syntax</span></span>

```xml
<WideEntries>
  <WideEntry>...</WideEntry>
</WideEntries>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="e148b-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e148b-107">Attributes and Elements</span></span>

<span data-ttu-id="e148b-108">В следующих разделах атрибуты, дочерние элементы и родительский элемент `WideEntries` элемент.</span><span class="sxs-lookup"><span data-stu-id="e148b-108">The following sections describe the attributes, child elements, and parent element of the `WideEntries` element.</span></span> <span data-ttu-id="e148b-109">Необходимо указать хотя бы один дочерний элемент.</span><span class="sxs-lookup"><span data-stu-id="e148b-109">At least one child element must be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="e148b-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e148b-110">Attributes</span></span>

<span data-ttu-id="e148b-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="e148b-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e148b-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e148b-112">Child Elements</span></span>

|<span data-ttu-id="e148b-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="e148b-113">Element</span></span>|<span data-ttu-id="e148b-114">Описание</span><span class="sxs-lookup"><span data-stu-id="e148b-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e148b-115">Элемент WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="e148b-115">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)|<span data-ttu-id="e148b-116">Предоставляет определение широкое представление.</span><span class="sxs-lookup"><span data-stu-id="e148b-116">Provides a definition of the wide view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e148b-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e148b-117">Parent Elements</span></span>

|<span data-ttu-id="e148b-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="e148b-118">Element</span></span>|<span data-ttu-id="e148b-119">Описание</span><span class="sxs-lookup"><span data-stu-id="e148b-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e148b-120">Элемент WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="e148b-120">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)|<span data-ttu-id="e148b-121">Большое (значение одно значение) определяет формат списка для представления.</span><span class="sxs-lookup"><span data-stu-id="e148b-121">Defines a wide (single value) list format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e148b-122">Замечания</span><span class="sxs-lookup"><span data-stu-id="e148b-122">Remarks</span></span>

<span data-ttu-id="e148b-123">Широкое представление — это формат списка, который отображает значение одного свойства или значение скрипта для каждого объекта.</span><span class="sxs-lookup"><span data-stu-id="e148b-123">A wide view is a list format that displays a single property value or script value for each object.</span></span> <span data-ttu-id="e148b-124">Дополнительные сведения о компонентах широкое представление, см. в разделе [расширенные компоненты представлений](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="e148b-124">For more information about the components of a wide view, see [Wide View Components](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="e148b-125">Пример</span><span class="sxs-lookup"><span data-stu-id="e148b-125">Example</span></span>

<span data-ttu-id="e148b-126">В следующем примере показан `WideEntries` элемент, который определяет одно `WideEntry` элемент.</span><span class="sxs-lookup"><span data-stu-id="e148b-126">The following example shows a `WideEntries` element that defines a single `WideEntry` element.</span></span> <span data-ttu-id="e148b-127">`WideEntry` Элемент содержит один `WideItem` элемент, который определяет, какое значение свойства или скрипт отображается в представлении.</span><span class="sxs-lookup"><span data-stu-id="e148b-127">The `WideEntry` element contains a single `WideItem` element that defines what property or script value is displayed in the view.</span></span>

```xml
<WideControl>
  <WideEntries>
    <WideEntry>
      <WideItem>...</WideItem>
    <WideEntry>
  </WideEntries>
</WideControl>
```

<span data-ttu-id="e148b-128">Полный пример широкое представление, см. в разделе [широкое представление (Basic)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="e148b-128">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e148b-129">См. также</span><span class="sxs-lookup"><span data-stu-id="e148b-129">See Also</span></span>

[<span data-ttu-id="e148b-130">Создание широкое представление</span><span class="sxs-lookup"><span data-stu-id="e148b-130">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="e148b-131">Элемент WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="e148b-131">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)

[<span data-ttu-id="e148b-132">Элемент WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="e148b-132">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)

[<span data-ttu-id="e148b-133">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="e148b-133">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
