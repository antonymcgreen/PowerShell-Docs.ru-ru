---
title: Элемент WideControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 715ea055-037b-46ad-b70f-87b3f5134403
caps.latest.revision: 14
ms.openlocfilehash: 2742be0389a1bf04af100a490a59c0d938165811
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859830"
---
# <a name="widecontrol-element-format"></a><span data-ttu-id="9ad95-102">Элемент WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="9ad95-102">WideControl Element (Format)</span></span>

<span data-ttu-id="9ad95-103">Большое (значение одно значение) определяет формат списка для представления.</span><span class="sxs-lookup"><span data-stu-id="9ad95-103">Defines a wide (single value) list format for the view.</span></span> <span data-ttu-id="9ad95-104">Это представление отображает значение одного свойства или значение скрипта для каждого объекта.</span><span class="sxs-lookup"><span data-stu-id="9ad95-104">This view displays a single property value or script value for each object.</span></span>

<span data-ttu-id="9ad95-105">Элемент элемента (формат) WideControl для элемента (формат) элемент ViewDefinitions (формат) конфигурации представления (формат)</span><span class="sxs-lookup"><span data-stu-id="9ad95-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9ad95-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9ad95-106">Syntax</span></span>

```xml
<WideControl>
  <AutoSize/>
  <ColumnNumber>PositiveInteger</ColumnNumber>
  <WideEntries>...</WideEntries>
</WideControl>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9ad95-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9ad95-107">Attributes and Elements</span></span>

<span data-ttu-id="9ad95-108">В следующих разделах атрибуты, дочерние элементы и родительский элемент `WideControl` элемент.</span><span class="sxs-lookup"><span data-stu-id="9ad95-108">The following sections describe the attributes, child elements, and parent element of the `WideControl` element.</span></span> <span data-ttu-id="9ad95-109">Нельзя указать `AutoSize` и `ColumnNumber` элементы, в то же время.</span><span class="sxs-lookup"><span data-stu-id="9ad95-109">You cannot specify the `AutoSize` and `ColumnNumber` elements at the same time.</span></span>

### <a name="attributes"></a><span data-ttu-id="9ad95-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9ad95-110">Attributes</span></span>

<span data-ttu-id="9ad95-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="9ad95-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9ad95-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9ad95-112">Child Elements</span></span>

|<span data-ttu-id="9ad95-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="9ad95-113">Element</span></span>|<span data-ttu-id="9ad95-114">Описание</span><span class="sxs-lookup"><span data-stu-id="9ad95-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9ad95-115">AutoSize-элемент для WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="9ad95-115">AutoSize Element for WideControl (Format)</span></span>](./autosize-element-for-widecontrol-format.md)|<span data-ttu-id="9ad95-116">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="9ad95-116">Optional element.</span></span><br /><br /> <span data-ttu-id="9ad95-117">Указывает ли размер столбца и количество столбцов изменить в зависимости от объема данных.</span><span class="sxs-lookup"><span data-stu-id="9ad95-117">Specifies whether the column size and the number of columns are adjusted based on the size of the data.</span></span>|
|[<span data-ttu-id="9ad95-118">ColumnNumber-элемент для WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="9ad95-118">ColumnNumber Element for WideControl (Format)</span></span>](./columnnumber-element-for-widecontrol-format.md)|<span data-ttu-id="9ad95-119">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="9ad95-119">Optional element.</span></span><br /><br /> <span data-ttu-id="9ad95-120">Указывает количество столбцов, отображаемых в широком представлении.</span><span class="sxs-lookup"><span data-stu-id="9ad95-120">Specifies the number of columns displayed in the wide view.</span></span>|
|[<span data-ttu-id="9ad95-121">Элемент WideEntries (формат)</span><span class="sxs-lookup"><span data-stu-id="9ad95-121">WideEntries Element (Format)</span></span>](./wideentries-element-for-widecontrol-format.md)|<span data-ttu-id="9ad95-122">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="9ad95-122">Required element.</span></span><br /><br /> <span data-ttu-id="9ad95-123">Предоставляет определения широкое представление.</span><span class="sxs-lookup"><span data-stu-id="9ad95-123">Provides the definitions of the wide view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="9ad95-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9ad95-124">Parent Elements</span></span>

|<span data-ttu-id="9ad95-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="9ad95-125">Element</span></span>|<span data-ttu-id="9ad95-126">Описание</span><span class="sxs-lookup"><span data-stu-id="9ad95-126">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9ad95-127">Элемент представления (формат)</span><span class="sxs-lookup"><span data-stu-id="9ad95-127">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="9ad95-128">Определяет представление, которое используется для отображения один или несколько объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="9ad95-128">Defines a view that is used to display one or more .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="9ad95-129">Замечания</span><span class="sxs-lookup"><span data-stu-id="9ad95-129">Remarks</span></span>

<span data-ttu-id="9ad95-130">При определении широкое представление, можно добавить `AutoSize` элемент или `ColumnNumber` , но нельзя добавить одновременно.</span><span class="sxs-lookup"><span data-stu-id="9ad95-130">When defining a wide view, you can add the `AutoSize` element or the `ColumnNumber` but you cannot add both.</span></span>

<span data-ttu-id="9ad95-131">В большинстве случаев только одно определение является обязательным для каждого широкое представление, но можно иметь несколько определений, если вы хотите использовать одинаковое представление для отображения различных объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="9ad95-131">In most cases, only one definition is required for each wide view, but it is possible to have multiple definitions if you want to use the same view to display different .NET objects.</span></span> <span data-ttu-id="9ad95-132">В таком случае можно задать отдельный определение для каждого объекта или набора объектов.</span><span class="sxs-lookup"><span data-stu-id="9ad95-132">In those cases, you can provide a separate definition for each object or set of objects.</span></span>

<span data-ttu-id="9ad95-133">Дополнительные сведения о компонентах широкое представление, см. в разделе [расширенные компоненты представлений](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="9ad95-133">For more information about the components of a wide view, see [Wide View Components](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="9ad95-134">Пример</span><span class="sxs-lookup"><span data-stu-id="9ad95-134">Example</span></span>

<span data-ttu-id="9ad95-135">В следующем примере показан `WideControl` элемент, который используется для отображения свойства [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) объекта.</span><span class="sxs-lookup"><span data-stu-id="9ad95-135">The following example shows a `WideControl` element that is used to display a property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<View>
  <Name>process</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <WideControl>
    <WideEntries>...</WideEntries>
  </WideControl>
</View>
```

<span data-ttu-id="9ad95-136">Полный пример широкое представление, см. в разделе [широкое представление (Basic)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="9ad95-136">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9ad95-137">См. также</span><span class="sxs-lookup"><span data-stu-id="9ad95-137">See Also</span></span>

[<span data-ttu-id="9ad95-138">AutoSize-элемент для WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="9ad95-138">Autosize Element for WideControl (Format)</span></span>](./autosize-element-for-widecontrol-format.md)

[<span data-ttu-id="9ad95-139">ColumnNumber-элемент для WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="9ad95-139">ColumnNumber Element for WideControl (Format)</span></span>](./columnnumber-element-for-widecontrol-format.md)

[<span data-ttu-id="9ad95-140">Элемент представления (формат)</span><span class="sxs-lookup"><span data-stu-id="9ad95-140">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="9ad95-141">Элемент WideEntries (формат)</span><span class="sxs-lookup"><span data-stu-id="9ad95-141">WideEntries Element (Format)</span></span>](./wideentries-element-for-widecontrol-format.md)

[<span data-ttu-id="9ad95-142">Широкое представление (Basic)</span><span class="sxs-lookup"><span data-stu-id="9ad95-142">Wide View (Basic)</span></span>](./wide-view-basic.md)

[<span data-ttu-id="9ad95-143">Создание широкое представление</span><span class="sxs-lookup"><span data-stu-id="9ad95-143">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="9ad95-144">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="9ad95-144">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
