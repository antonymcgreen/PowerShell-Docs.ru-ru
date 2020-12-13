---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент WideControl (формат)
description: Элемент WideControl (формат)
ms.openlocfilehash: f88e1ce18f87e5e47de473298b3ecf070b71c192
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651277"
---
# <a name="widecontrol-element-format"></a><span data-ttu-id="dd672-103">Элемент WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="dd672-103">WideControl Element (Format)</span></span>

<span data-ttu-id="dd672-104">Определяет для представления широкий формат списка (одно значение).</span><span class="sxs-lookup"><span data-stu-id="dd672-104">Defines a wide (single value) list format for the view.</span></span> <span data-ttu-id="dd672-105">В этом представлении отображается одно значение свойства или значение скрипта для каждого объекта.</span><span class="sxs-lookup"><span data-stu-id="dd672-105">This view displays a single property value or script value for each object.</span></span>

<span data-ttu-id="dd672-106">Элемент конфигурации (Format) Виевдефинитионс элемента представления (Format) элемент (формат) Видеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="dd672-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="dd672-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dd672-107">Syntax</span></span>

```xml
<WideControl>
  <AutoSize/>
  <ColumnNumber>PositiveInteger</ColumnNumber>
  <WideEntries>...</WideEntries>
</WideControl>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="dd672-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="dd672-108">Attributes and Elements</span></span>

<span data-ttu-id="dd672-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `WideControl` элемента.</span><span class="sxs-lookup"><span data-stu-id="dd672-109">The following sections describe the attributes, child elements, and parent element of the `WideControl` element.</span></span> <span data-ttu-id="dd672-110">Нельзя `AutoSize` одновременно указать элементы и `ColumnNumber` .</span><span class="sxs-lookup"><span data-stu-id="dd672-110">You cannot specify the `AutoSize` and `ColumnNumber` elements at the same time.</span></span>

### <a name="attributes"></a><span data-ttu-id="dd672-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="dd672-111">Attributes</span></span>

<span data-ttu-id="dd672-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="dd672-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="dd672-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="dd672-113">Child Elements</span></span>

|<span data-ttu-id="dd672-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="dd672-114">Element</span></span>|<span data-ttu-id="dd672-115">Описание</span><span class="sxs-lookup"><span data-stu-id="dd672-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="dd672-116">Элемент AutoSize для WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="dd672-116">AutoSize Element for WideControl (Format)</span></span>](./autosize-element-for-widecontrol-format.md)|<span data-ttu-id="dd672-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="dd672-117">Optional element.</span></span><br /><br /> <span data-ttu-id="dd672-118">Указывает, изменяется ли размер столбца и число столбцов в зависимости от размера данных.</span><span class="sxs-lookup"><span data-stu-id="dd672-118">Specifies whether the column size and the number of columns are adjusted based on the size of the data.</span></span>|
|[<span data-ttu-id="dd672-119">Элемент ColumnNumber для WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="dd672-119">ColumnNumber Element for WideControl (Format)</span></span>](./columnnumber-element-for-widecontrol-format.md)|<span data-ttu-id="dd672-120">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="dd672-120">Optional element.</span></span><br /><br /> <span data-ttu-id="dd672-121">Указывает число столбцов, отображаемых в расширенном представлении.</span><span class="sxs-lookup"><span data-stu-id="dd672-121">Specifies the number of columns displayed in the wide view.</span></span>|
|[<span data-ttu-id="dd672-122">Элемент Видинтриес (Format)</span><span class="sxs-lookup"><span data-stu-id="dd672-122">WideEntries Element (Format)</span></span>](./wideentries-element-for-widecontrol-format.md)|<span data-ttu-id="dd672-123">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="dd672-123">Required element.</span></span><br /><br /> <span data-ttu-id="dd672-124">Предоставляет определения расширенного представления.</span><span class="sxs-lookup"><span data-stu-id="dd672-124">Provides the definitions of the wide view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="dd672-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="dd672-125">Parent Elements</span></span>

|<span data-ttu-id="dd672-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="dd672-126">Element</span></span>|<span data-ttu-id="dd672-127">Описание</span><span class="sxs-lookup"><span data-stu-id="dd672-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="dd672-128">Элемент View (формат)</span><span class="sxs-lookup"><span data-stu-id="dd672-128">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="dd672-129">Определяет представление, используемое для отображения одного или нескольких объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="dd672-129">Defines a view that is used to display one or more .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="dd672-130">Комментарии</span><span class="sxs-lookup"><span data-stu-id="dd672-130">Remarks</span></span>

<span data-ttu-id="dd672-131">При определении расширенного представления можно добавить `AutoSize` элемент или, `ColumnNumber` но нельзя добавить оба.</span><span class="sxs-lookup"><span data-stu-id="dd672-131">When defining a wide view, you can add the `AutoSize` element or the `ColumnNumber` but you cannot add both.</span></span>

<span data-ttu-id="dd672-132">В большинстве случаев для каждого расширенного представления требуется только одно определение, но существует несколько определений, если вы хотите использовать одно и то же представление для отображения различных объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="dd672-132">In most cases, only one definition is required for each wide view, but it is possible to have multiple definitions if you want to use the same view to display different .NET objects.</span></span> <span data-ttu-id="dd672-133">В таких случаях можно указать отдельное определение для каждого объекта или набора объектов.</span><span class="sxs-lookup"><span data-stu-id="dd672-133">In those cases, you can provide a separate definition for each object or set of objects.</span></span>

<span data-ttu-id="dd672-134">Дополнительные сведения о компонентах широкого представления см. в разделе [широкие компоненты представления](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="dd672-134">For more information about the components of a wide view, see [Wide View Components](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="dd672-135">Пример</span><span class="sxs-lookup"><span data-stu-id="dd672-135">Example</span></span>

<span data-ttu-id="dd672-136">В следующем примере показан `WideControl` элемент, используемый для отображения свойства объекта [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .</span><span class="sxs-lookup"><span data-stu-id="dd672-136">The following example shows a `WideControl` element that is used to display a property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

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

<span data-ttu-id="dd672-137">Полный пример расширенного представления см. в разделе [широкие представления (базовый)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="dd672-137">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dd672-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="dd672-138">See Also</span></span>

[<span data-ttu-id="dd672-139">Элемент AutoSize для Видеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="dd672-139">Autosize Element for WideControl (Format)</span></span>](./autosize-element-for-widecontrol-format.md)

[<span data-ttu-id="dd672-140">Элемент ColumnNumber для WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="dd672-140">ColumnNumber Element for WideControl (Format)</span></span>](./columnnumber-element-for-widecontrol-format.md)

[<span data-ttu-id="dd672-141">Элемент View (формат)</span><span class="sxs-lookup"><span data-stu-id="dd672-141">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="dd672-142">Элемент Видинтриес (Format)</span><span class="sxs-lookup"><span data-stu-id="dd672-142">WideEntries Element (Format)</span></span>](./wideentries-element-for-widecontrol-format.md)

[<span data-ttu-id="dd672-143">Широкое представление (базовое)</span><span class="sxs-lookup"><span data-stu-id="dd672-143">Wide View (Basic)</span></span>](./wide-view-basic.md)

[<span data-ttu-id="dd672-144">Создание широкого представления</span><span class="sxs-lookup"><span data-stu-id="dd672-144">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="dd672-145">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="dd672-145">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
