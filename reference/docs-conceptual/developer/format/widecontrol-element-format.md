---
title: Элемент Видеконтрол (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: b6f19cf94dcb440eeaf53547db407287e5462520
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784985"
---
# <a name="widecontrol-element-format"></a><span data-ttu-id="75a8f-102">Элемент WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="75a8f-102">WideControl Element (Format)</span></span>

<span data-ttu-id="75a8f-103">Определяет для представления широкий формат списка (одно значение).</span><span class="sxs-lookup"><span data-stu-id="75a8f-103">Defines a wide (single value) list format for the view.</span></span> <span data-ttu-id="75a8f-104">В этом представлении отображается одно значение свойства или значение скрипта для каждого объекта.</span><span class="sxs-lookup"><span data-stu-id="75a8f-104">This view displays a single property value or script value for each object.</span></span>

<span data-ttu-id="75a8f-105">Элемент конфигурации (Format) Виевдефинитионс элемента представления (Format) элемент (формат) Видеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="75a8f-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="75a8f-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="75a8f-106">Syntax</span></span>

```xml
<WideControl>
  <AutoSize/>
  <ColumnNumber>PositiveInteger</ColumnNumber>
  <WideEntries>...</WideEntries>
</WideControl>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="75a8f-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="75a8f-107">Attributes and Elements</span></span>

<span data-ttu-id="75a8f-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `WideControl` элемента.</span><span class="sxs-lookup"><span data-stu-id="75a8f-108">The following sections describe the attributes, child elements, and parent element of the `WideControl` element.</span></span> <span data-ttu-id="75a8f-109">Нельзя `AutoSize` одновременно указать элементы и `ColumnNumber` .</span><span class="sxs-lookup"><span data-stu-id="75a8f-109">You cannot specify the `AutoSize` and `ColumnNumber` elements at the same time.</span></span>

### <a name="attributes"></a><span data-ttu-id="75a8f-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="75a8f-110">Attributes</span></span>

<span data-ttu-id="75a8f-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="75a8f-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="75a8f-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="75a8f-112">Child Elements</span></span>

|<span data-ttu-id="75a8f-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="75a8f-113">Element</span></span>|<span data-ttu-id="75a8f-114">Описание</span><span class="sxs-lookup"><span data-stu-id="75a8f-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="75a8f-115">Элемент AutoSize для WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="75a8f-115">AutoSize Element for WideControl (Format)</span></span>](./autosize-element-for-widecontrol-format.md)|<span data-ttu-id="75a8f-116">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="75a8f-116">Optional element.</span></span><br /><br /> <span data-ttu-id="75a8f-117">Указывает, изменяется ли размер столбца и число столбцов в зависимости от размера данных.</span><span class="sxs-lookup"><span data-stu-id="75a8f-117">Specifies whether the column size and the number of columns are adjusted based on the size of the data.</span></span>|
|[<span data-ttu-id="75a8f-118">Элемент ColumnNumber для WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="75a8f-118">ColumnNumber Element for WideControl (Format)</span></span>](./columnnumber-element-for-widecontrol-format.md)|<span data-ttu-id="75a8f-119">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="75a8f-119">Optional element.</span></span><br /><br /> <span data-ttu-id="75a8f-120">Указывает число столбцов, отображаемых в расширенном представлении.</span><span class="sxs-lookup"><span data-stu-id="75a8f-120">Specifies the number of columns displayed in the wide view.</span></span>|
|[<span data-ttu-id="75a8f-121">Элемент Видинтриес (Format)</span><span class="sxs-lookup"><span data-stu-id="75a8f-121">WideEntries Element (Format)</span></span>](./wideentries-element-for-widecontrol-format.md)|<span data-ttu-id="75a8f-122">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="75a8f-122">Required element.</span></span><br /><br /> <span data-ttu-id="75a8f-123">Предоставляет определения расширенного представления.</span><span class="sxs-lookup"><span data-stu-id="75a8f-123">Provides the definitions of the wide view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="75a8f-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="75a8f-124">Parent Elements</span></span>

|<span data-ttu-id="75a8f-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="75a8f-125">Element</span></span>|<span data-ttu-id="75a8f-126">Описание</span><span class="sxs-lookup"><span data-stu-id="75a8f-126">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="75a8f-127">Элемент View (формат)</span><span class="sxs-lookup"><span data-stu-id="75a8f-127">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="75a8f-128">Определяет представление, используемое для отображения одного или нескольких объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="75a8f-128">Defines a view that is used to display one or more .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="75a8f-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="75a8f-129">Remarks</span></span>

<span data-ttu-id="75a8f-130">При определении расширенного представления можно добавить `AutoSize` элемент или, `ColumnNumber` но нельзя добавить оба.</span><span class="sxs-lookup"><span data-stu-id="75a8f-130">When defining a wide view, you can add the `AutoSize` element or the `ColumnNumber` but you cannot add both.</span></span>

<span data-ttu-id="75a8f-131">В большинстве случаев для каждого расширенного представления требуется только одно определение, но существует несколько определений, если вы хотите использовать одно и то же представление для отображения различных объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="75a8f-131">In most cases, only one definition is required for each wide view, but it is possible to have multiple definitions if you want to use the same view to display different .NET objects.</span></span> <span data-ttu-id="75a8f-132">В таких случаях можно указать отдельное определение для каждого объекта или набора объектов.</span><span class="sxs-lookup"><span data-stu-id="75a8f-132">In those cases, you can provide a separate definition for each object or set of objects.</span></span>

<span data-ttu-id="75a8f-133">Дополнительные сведения о компонентах широкого представления см. в разделе [широкие компоненты представления](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="75a8f-133">For more information about the components of a wide view, see [Wide View Components](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="75a8f-134">Пример</span><span class="sxs-lookup"><span data-stu-id="75a8f-134">Example</span></span>

<span data-ttu-id="75a8f-135">В следующем примере показан `WideControl` элемент, используемый для отображения свойства объекта [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) .</span><span class="sxs-lookup"><span data-stu-id="75a8f-135">The following example shows a `WideControl` element that is used to display a property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

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

<span data-ttu-id="75a8f-136">Полный пример расширенного представления см. в разделе [широкие представления (базовый)](./wide-view-basic.md).</span><span class="sxs-lookup"><span data-stu-id="75a8f-136">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="75a8f-137">См. также</span><span class="sxs-lookup"><span data-stu-id="75a8f-137">See Also</span></span>

[<span data-ttu-id="75a8f-138">Элемент AutoSize для Видеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="75a8f-138">Autosize Element for WideControl (Format)</span></span>](./autosize-element-for-widecontrol-format.md)

[<span data-ttu-id="75a8f-139">Элемент ColumnNumber для WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="75a8f-139">ColumnNumber Element for WideControl (Format)</span></span>](./columnnumber-element-for-widecontrol-format.md)

[<span data-ttu-id="75a8f-140">Элемент View (формат)</span><span class="sxs-lookup"><span data-stu-id="75a8f-140">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="75a8f-141">Элемент Видинтриес (Format)</span><span class="sxs-lookup"><span data-stu-id="75a8f-141">WideEntries Element (Format)</span></span>](./wideentries-element-for-widecontrol-format.md)

[<span data-ttu-id="75a8f-142">Широкое представление (базовое)</span><span class="sxs-lookup"><span data-stu-id="75a8f-142">Wide View (Basic)</span></span>](./wide-view-basic.md)

[<span data-ttu-id="75a8f-143">Создание широкого представления</span><span class="sxs-lookup"><span data-stu-id="75a8f-143">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="75a8f-144">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="75a8f-144">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
