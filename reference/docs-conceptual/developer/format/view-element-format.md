---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент View (формат)
description: Элемент View (формат)
ms.openlocfilehash: 6fed1304d94339cc90b6ae53e06483c08d937c12
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649748"
---
# <a name="view-element-format"></a><span data-ttu-id="4b6fc-103">Элемент View (формат)</span><span class="sxs-lookup"><span data-stu-id="4b6fc-103">View Element (Format)</span></span>

<span data-ttu-id="4b6fc-104">Определяет представление, в котором отображается один или несколько объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="4b6fc-104">Defines a view that displays one or more .NET objects.</span></span> <span data-ttu-id="4b6fc-105">Количество представлений, которые могут быть определены в файле форматирования, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="4b6fc-105">There is no limit to the number of views that can be defined in a formatting file.</span></span>

<span data-ttu-id="4b6fc-106">Элемент конфигурации (Format) Виевдефинитионс элемента представления (Format) (формат)</span><span class="sxs-lookup"><span data-stu-id="4b6fc-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4b6fc-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4b6fc-107">Syntax</span></span>

```xml
<View>
  <Name>Friendly name of view.</Name>
  <ViewSelectedBy>...</ViewSelectedBy>
  <Controls>...</Controls>
  <GroupBy>...</GroupBy>
  <TableControl>...</TableControl>
  <ListControl>...</ListControl>
  <WideControl>...</WideControl>
  <CustomControl>...</CustomControl>
</View>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4b6fc-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4b6fc-108">Attributes and Elements</span></span>

<span data-ttu-id="4b6fc-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `View` элемента.</span><span class="sxs-lookup"><span data-stu-id="4b6fc-109">The following sections describe the attributes, child elements, and the parent element of the `View` element.</span></span> <span data-ttu-id="4b6fc-110">Необходимо указать один и только один из дочерних элементов элемента управления, а также указать имя представления и объекты, использующие это представление.</span><span class="sxs-lookup"><span data-stu-id="4b6fc-110">You must specify one and only one of the control child elements, and you must specify the name of the view and the objects that use the view.</span></span> <span data-ttu-id="4b6fc-111">Определение пользовательских элементов управления, Группировка объектов и указание, являются ли представление внешними, являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="4b6fc-111">Defining custom controls, how to group objects, and specifying if the view is out-of-band are optional.</span></span>

### <a name="attributes"></a><span data-ttu-id="4b6fc-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4b6fc-112">Attributes</span></span>

<span data-ttu-id="4b6fc-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="4b6fc-113">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4b6fc-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4b6fc-114">Child Elements</span></span>

|<span data-ttu-id="4b6fc-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="4b6fc-115">Element</span></span>|<span data-ttu-id="4b6fc-116">Описание</span><span class="sxs-lookup"><span data-stu-id="4b6fc-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4b6fc-117">Элемент Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="4b6fc-117">Controls Element for View (Format)</span></span>](./controls-element-for-view-format.md)|<span data-ttu-id="4b6fc-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="4b6fc-118">Optional element.</span></span><br /><br /> <span data-ttu-id="4b6fc-119">Определяет набор элементов управления, на которые в представлении можно ссылаться по именам.</span><span class="sxs-lookup"><span data-stu-id="4b6fc-119">Defines a set of controls that can be referenced by their name from within the view.</span></span>|
|[<span data-ttu-id="4b6fc-120">Элемент ошибка customcontrol (Format)</span><span class="sxs-lookup"><span data-stu-id="4b6fc-120">CustomControl Element (Format)</span></span>](./customcontrol-element-for-groupby-format.md)|<span data-ttu-id="4b6fc-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="4b6fc-121">Optional element.</span></span><br /><br /> <span data-ttu-id="4b6fc-122">Определяет формат пользовательского элемента управления для представления.</span><span class="sxs-lookup"><span data-stu-id="4b6fc-122">Defines a custom control format for the view.</span></span>|
|[<span data-ttu-id="4b6fc-123">Элемент GroupBy для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="4b6fc-123">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="4b6fc-124">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="4b6fc-124">Optional element.</span></span><br /><br /> <span data-ttu-id="4b6fc-125">Определяет, как группируются элементы объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="4b6fc-125">Defines how the members of the .NET objects are grouped.</span></span>|
|[<span data-ttu-id="4b6fc-126">Элемент ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="4b6fc-126">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)|<span data-ttu-id="4b6fc-127">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="4b6fc-127">Optional element.</span></span><br /><br /> <span data-ttu-id="4b6fc-128">Определяет формат списка для представления.</span><span class="sxs-lookup"><span data-stu-id="4b6fc-128">Defines a list format for the view.</span></span>|
|[<span data-ttu-id="4b6fc-129">Элемент Name для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="4b6fc-129">Name Element for View (Format)</span></span>](./name-element-for-view-format.md)|<span data-ttu-id="4b6fc-130">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="4b6fc-130">Required element.</span></span><br /><br /> <span data-ttu-id="4b6fc-131">Задает имя, используемое для ссылки на представление.</span><span class="sxs-lookup"><span data-stu-id="4b6fc-131">Specifies the name used to reference the view.</span></span>|
|[<span data-ttu-id="4b6fc-132">Элемент TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="4b6fc-132">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)|<span data-ttu-id="4b6fc-133">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="4b6fc-133">Optional element.</span></span><br /><br /> <span data-ttu-id="4b6fc-134">Определяет формат таблицы для представления.</span><span class="sxs-lookup"><span data-stu-id="4b6fc-134">Defines a table format for the view.</span></span>|
|[<span data-ttu-id="4b6fc-135">Элемент Виевселектедби для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="4b6fc-135">ViewSelectedBy Element for View (Format)</span></span>](./viewselectedby-element-format.md)|<span data-ttu-id="4b6fc-136">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="4b6fc-136">Required element.</span></span><br /><br /> <span data-ttu-id="4b6fc-137">Определяет объекты .NET, отображаемые в этом представлении.</span><span class="sxs-lookup"><span data-stu-id="4b6fc-137">Defines the .NET objects that this view displays.</span></span>|
|[<span data-ttu-id="4b6fc-138">Элемент WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="4b6fc-138">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)|<span data-ttu-id="4b6fc-139">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="4b6fc-139">Optional element.</span></span><br /><br /> <span data-ttu-id="4b6fc-140">Определяет для представления широкий формат списка (одно значение).</span><span class="sxs-lookup"><span data-stu-id="4b6fc-140">Defines a wide (single value) list format for the view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="4b6fc-141">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4b6fc-141">Parent Elements</span></span>

|<span data-ttu-id="4b6fc-142">Элемент</span><span class="sxs-lookup"><span data-stu-id="4b6fc-142">Element</span></span>|<span data-ttu-id="4b6fc-143">Описание</span><span class="sxs-lookup"><span data-stu-id="4b6fc-143">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4b6fc-144">Элемент ViewDefinitions (формат)</span><span class="sxs-lookup"><span data-stu-id="4b6fc-144">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)|<span data-ttu-id="4b6fc-145">Определяет представления, используемые для отображения объектов.</span><span class="sxs-lookup"><span data-stu-id="4b6fc-145">Defines the views used to display objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="4b6fc-146">Комментарии</span><span class="sxs-lookup"><span data-stu-id="4b6fc-146">Remarks</span></span>

<span data-ttu-id="4b6fc-147">Дополнительные сведения о компонентах различных представлений и пользовательских элементов управления см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="4b6fc-147">For more information about the components of different views and custom controls, see the following topics:</span></span>

- [<span data-ttu-id="4b6fc-148">Компоненты табличного представления</span><span class="sxs-lookup"><span data-stu-id="4b6fc-148">Table View Components</span></span>](./creating-a-table-view.md)

- [<span data-ttu-id="4b6fc-149">Компоненты представления списка</span><span class="sxs-lookup"><span data-stu-id="4b6fc-149">List View Components</span></span>](./creating-a-list-view.md)

- [<span data-ttu-id="4b6fc-150">Компоненты расширенного представления</span><span class="sxs-lookup"><span data-stu-id="4b6fc-150">Wide View Components</span></span>](./creating-a-wide-view.md)

- [<span data-ttu-id="4b6fc-151">Пользовательские элементы управления</span><span class="sxs-lookup"><span data-stu-id="4b6fc-151">Custom Controls</span></span>](./creating-custom-controls.md)

## <a name="example"></a><span data-ttu-id="4b6fc-152">Пример</span><span class="sxs-lookup"><span data-stu-id="4b6fc-152">Example</span></span>

<span data-ttu-id="4b6fc-153">В этом примере показан `View` элемент, определяющий представление таблицы для объекта [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) .</span><span class="sxs-lookup"><span data-stu-id="4b6fc-153">This example shows a `View` element that defines a table view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

```xml
<ViewDefinitions>
  <View>
    <Name>service</Name>
    <ViewSelectedBy>
      <TypeName>System.ServiceProcess.ServiceController</TypeName>
    </ViewSelectedBy>
    <TableControl>...</TableControl>
  </View>
</ViewDefinitions>

```

## <a name="see-also"></a><span data-ttu-id="4b6fc-154">См. также:</span><span class="sxs-lookup"><span data-stu-id="4b6fc-154">See Also</span></span>

[<span data-ttu-id="4b6fc-155">Элемент ViewDefinitions (формат)</span><span class="sxs-lookup"><span data-stu-id="4b6fc-155">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)

[<span data-ttu-id="4b6fc-156">Элемент Name для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="4b6fc-156">Name Element for View (Format)</span></span>](./name-element-for-view-format.md)

[<span data-ttu-id="4b6fc-157">Элемент ViewSelectedBy (формат)</span><span class="sxs-lookup"><span data-stu-id="4b6fc-157">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)

[<span data-ttu-id="4b6fc-158">Элемент Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="4b6fc-158">Controls Element for View (Format)</span></span>](./controls-element-for-view-format.md)

[<span data-ttu-id="4b6fc-159">Элемент GroupBy для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="4b6fc-159">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="4b6fc-160">Элемент TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="4b6fc-160">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)

[<span data-ttu-id="4b6fc-161">Элемент ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="4b6fc-161">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)

[<span data-ttu-id="4b6fc-162">Элемент WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="4b6fc-162">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)

[<span data-ttu-id="4b6fc-163">Элемент ошибка customcontrol (Format)</span><span class="sxs-lookup"><span data-stu-id="4b6fc-163">CustomControl Element (Format)</span></span>](./customcontrol-element-for-groupby-format.md)

[<span data-ttu-id="4b6fc-164">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="4b6fc-164">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
