---
title: View, элемент (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: c0c6fa373cfca3a55a62f201e1eabc6a1e308ef7
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785036"
---
# <a name="view-element-format"></a><span data-ttu-id="59e65-102">Элемент View (формат)</span><span class="sxs-lookup"><span data-stu-id="59e65-102">View Element (Format)</span></span>

<span data-ttu-id="59e65-103">Определяет представление, в котором отображается один или несколько объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="59e65-103">Defines a view that displays one or more .NET objects.</span></span> <span data-ttu-id="59e65-104">Количество представлений, которые могут быть определены в файле форматирования, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="59e65-104">There is no limit to the number of views that can be defined in a formatting file.</span></span>

<span data-ttu-id="59e65-105">Элемент конфигурации (Format) Виевдефинитионс элемента представления (Format) (формат)</span><span class="sxs-lookup"><span data-stu-id="59e65-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="59e65-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="59e65-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="59e65-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="59e65-107">Attributes and Elements</span></span>

<span data-ttu-id="59e65-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `View` элемента.</span><span class="sxs-lookup"><span data-stu-id="59e65-108">The following sections describe the attributes, child elements, and the parent element of the `View` element.</span></span> <span data-ttu-id="59e65-109">Необходимо указать один и только один из дочерних элементов элемента управления, а также указать имя представления и объекты, использующие это представление.</span><span class="sxs-lookup"><span data-stu-id="59e65-109">You must specify one and only one of the control child elements, and you must specify the name of the view and the objects that use the view.</span></span> <span data-ttu-id="59e65-110">Определение пользовательских элементов управления, Группировка объектов и указание, являются ли представление внешними, являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="59e65-110">Defining custom controls, how to group objects, and specifying if the view is out-of-band are optional.</span></span>

### <a name="attributes"></a><span data-ttu-id="59e65-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="59e65-111">Attributes</span></span>

<span data-ttu-id="59e65-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="59e65-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="59e65-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="59e65-113">Child Elements</span></span>

|<span data-ttu-id="59e65-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="59e65-114">Element</span></span>|<span data-ttu-id="59e65-115">Описание</span><span class="sxs-lookup"><span data-stu-id="59e65-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="59e65-116">Элемент Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="59e65-116">Controls Element for View (Format)</span></span>](./controls-element-for-view-format.md)|<span data-ttu-id="59e65-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="59e65-117">Optional element.</span></span><br /><br /> <span data-ttu-id="59e65-118">Определяет набор элементов управления, на которые в представлении можно ссылаться по именам.</span><span class="sxs-lookup"><span data-stu-id="59e65-118">Defines a set of controls that can be referenced by their name from within the view.</span></span>|
|[<span data-ttu-id="59e65-119">Элемент ошибка customcontrol (Format)</span><span class="sxs-lookup"><span data-stu-id="59e65-119">CustomControl Element (Format)</span></span>](./customcontrol-element-for-groupby-format.md)|<span data-ttu-id="59e65-120">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="59e65-120">Optional element.</span></span><br /><br /> <span data-ttu-id="59e65-121">Определяет формат пользовательского элемента управления для представления.</span><span class="sxs-lookup"><span data-stu-id="59e65-121">Defines a custom control format for the view.</span></span>|
|[<span data-ttu-id="59e65-122">Элемент GroupBy для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="59e65-122">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="59e65-123">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="59e65-123">Optional element.</span></span><br /><br /> <span data-ttu-id="59e65-124">Определяет, как группируются элементы объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="59e65-124">Defines how the members of the .NET objects are grouped.</span></span>|
|[<span data-ttu-id="59e65-125">Элемент ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="59e65-125">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)|<span data-ttu-id="59e65-126">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="59e65-126">Optional element.</span></span><br /><br /> <span data-ttu-id="59e65-127">Определяет формат списка для представления.</span><span class="sxs-lookup"><span data-stu-id="59e65-127">Defines a list format for the view.</span></span>|
|[<span data-ttu-id="59e65-128">Элемент Name для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="59e65-128">Name Element for View (Format)</span></span>](./name-element-for-view-format.md)|<span data-ttu-id="59e65-129">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="59e65-129">Required element.</span></span><br /><br /> <span data-ttu-id="59e65-130">Задает имя, используемое для ссылки на представление.</span><span class="sxs-lookup"><span data-stu-id="59e65-130">Specifies the name used to reference the view.</span></span>|
|[<span data-ttu-id="59e65-131">Элемент TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="59e65-131">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)|<span data-ttu-id="59e65-132">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="59e65-132">Optional element.</span></span><br /><br /> <span data-ttu-id="59e65-133">Определяет формат таблицы для представления.</span><span class="sxs-lookup"><span data-stu-id="59e65-133">Defines a table format for the view.</span></span>|
|[<span data-ttu-id="59e65-134">Элемент Виевселектедби для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="59e65-134">ViewSelectedBy Element for View (Format)</span></span>](./viewselectedby-element-format.md)|<span data-ttu-id="59e65-135">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="59e65-135">Required element.</span></span><br /><br /> <span data-ttu-id="59e65-136">Определяет объекты .NET, отображаемые в этом представлении.</span><span class="sxs-lookup"><span data-stu-id="59e65-136">Defines the .NET objects that this view displays.</span></span>|
|[<span data-ttu-id="59e65-137">Элемент WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="59e65-137">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)|<span data-ttu-id="59e65-138">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="59e65-138">Optional element.</span></span><br /><br /> <span data-ttu-id="59e65-139">Определяет для представления широкий формат списка (одно значение).</span><span class="sxs-lookup"><span data-stu-id="59e65-139">Defines a wide (single value) list format for the view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="59e65-140">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="59e65-140">Parent Elements</span></span>

|<span data-ttu-id="59e65-141">Элемент</span><span class="sxs-lookup"><span data-stu-id="59e65-141">Element</span></span>|<span data-ttu-id="59e65-142">Описание</span><span class="sxs-lookup"><span data-stu-id="59e65-142">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="59e65-143">Элемент ViewDefinitions (формат)</span><span class="sxs-lookup"><span data-stu-id="59e65-143">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)|<span data-ttu-id="59e65-144">Определяет представления, используемые для отображения объектов.</span><span class="sxs-lookup"><span data-stu-id="59e65-144">Defines the views used to display objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="59e65-145">Примечания</span><span class="sxs-lookup"><span data-stu-id="59e65-145">Remarks</span></span>

<span data-ttu-id="59e65-146">Дополнительные сведения о компонентах различных представлений и пользовательских элементов управления см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="59e65-146">For more information about the components of different views and custom controls, see the following topics:</span></span>

- [<span data-ttu-id="59e65-147">Компоненты табличного представления</span><span class="sxs-lookup"><span data-stu-id="59e65-147">Table View Components</span></span>](./creating-a-table-view.md)

- [<span data-ttu-id="59e65-148">Компоненты представления списка</span><span class="sxs-lookup"><span data-stu-id="59e65-148">List View Components</span></span>](./creating-a-list-view.md)

- [<span data-ttu-id="59e65-149">Компоненты расширенного представления</span><span class="sxs-lookup"><span data-stu-id="59e65-149">Wide View Components</span></span>](./creating-a-wide-view.md)

- [<span data-ttu-id="59e65-150">Пользовательские элементы управления</span><span class="sxs-lookup"><span data-stu-id="59e65-150">Custom Controls</span></span>](./creating-custom-controls.md)

## <a name="example"></a><span data-ttu-id="59e65-151">Пример</span><span class="sxs-lookup"><span data-stu-id="59e65-151">Example</span></span>

<span data-ttu-id="59e65-152">В этом примере показан `View` элемент, определяющий представление таблицы для объекта [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) .</span><span class="sxs-lookup"><span data-stu-id="59e65-152">This example shows a `View` element that defines a table view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="59e65-153">См. также</span><span class="sxs-lookup"><span data-stu-id="59e65-153">See Also</span></span>

[<span data-ttu-id="59e65-154">Элемент ViewDefinitions (формат)</span><span class="sxs-lookup"><span data-stu-id="59e65-154">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)

[<span data-ttu-id="59e65-155">Элемент Name для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="59e65-155">Name Element for View (Format)</span></span>](./name-element-for-view-format.md)

[<span data-ttu-id="59e65-156">Элемент ViewSelectedBy (формат)</span><span class="sxs-lookup"><span data-stu-id="59e65-156">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)

[<span data-ttu-id="59e65-157">Элемент Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="59e65-157">Controls Element for View (Format)</span></span>](./controls-element-for-view-format.md)

[<span data-ttu-id="59e65-158">Элемент GroupBy для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="59e65-158">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="59e65-159">Элемент TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="59e65-159">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)

[<span data-ttu-id="59e65-160">Элемент ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="59e65-160">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)

[<span data-ttu-id="59e65-161">Элемент WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="59e65-161">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)

[<span data-ttu-id="59e65-162">Элемент ошибка customcontrol (Format)</span><span class="sxs-lookup"><span data-stu-id="59e65-162">CustomControl Element (Format)</span></span>](./customcontrol-element-for-groupby-format.md)

[<span data-ttu-id="59e65-163">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="59e65-163">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
