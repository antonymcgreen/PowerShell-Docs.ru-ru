---
title: View, элемент (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d837d5d4-ed2e-4d84-a306-0b5d2ad2d0bf
caps.latest.revision: 24
ms.openlocfilehash: 2361c1117757569bef0815018c75764430a9e7a8
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361463"
---
# <a name="view-element-format"></a><span data-ttu-id="86afe-102">Элемент View (формат)</span><span class="sxs-lookup"><span data-stu-id="86afe-102">View Element (Format)</span></span>

<span data-ttu-id="86afe-103">Определяет представление, в котором отображается один или несколько объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="86afe-103">Defines a view that displays one or more .NET objects.</span></span> <span data-ttu-id="86afe-104">Количество представлений, которые могут быть определены в файле форматирования, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="86afe-104">There is no limit to the number of views that can be defined in a formatting file.</span></span>

<span data-ttu-id="86afe-105">Элемент конфигурации (Format) Виевдефинитионс элемента представления (Format) (формат)</span><span class="sxs-lookup"><span data-stu-id="86afe-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="86afe-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="86afe-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="86afe-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="86afe-107">Attributes and Elements</span></span>

<span data-ttu-id="86afe-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `View`.</span><span class="sxs-lookup"><span data-stu-id="86afe-108">The following sections describe the attributes, child elements, and the parent element of the `View` element.</span></span> <span data-ttu-id="86afe-109">Необходимо указать один и только один из дочерних элементов элемента управления, а также указать имя представления и объекты, использующие это представление.</span><span class="sxs-lookup"><span data-stu-id="86afe-109">You must specify one and only one of the control child elements, and you must specify the name of the view and the objects that use the view.</span></span> <span data-ttu-id="86afe-110">Определение пользовательских элементов управления, Группировка объектов и указание, являются ли представление внешними, являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="86afe-110">Defining custom controls, how to group objects, and specifying if the view is out-of-band are optional.</span></span>

### <a name="attributes"></a><span data-ttu-id="86afe-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="86afe-111">Attributes</span></span>

<span data-ttu-id="86afe-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="86afe-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="86afe-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="86afe-113">Child Elements</span></span>

|<span data-ttu-id="86afe-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="86afe-114">Element</span></span>|<span data-ttu-id="86afe-115">Описание</span><span class="sxs-lookup"><span data-stu-id="86afe-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="86afe-116">Элемент Controls для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="86afe-116">Controls Element for View (Format)</span></span>](./controls-element-for-view-format.md)|<span data-ttu-id="86afe-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="86afe-117">Optional element.</span></span><br /><br /> <span data-ttu-id="86afe-118">Определяет набор элементов управления, на которые в представлении можно ссылаться по именам.</span><span class="sxs-lookup"><span data-stu-id="86afe-118">Defines a set of controls that can be referenced by their name from within the view.</span></span>|
|[<span data-ttu-id="86afe-119">Элемент ошибка customcontrol (Format)</span><span class="sxs-lookup"><span data-stu-id="86afe-119">CustomControl Element (Format)</span></span>](./customcontrol-element-for-groupby-format.md)|<span data-ttu-id="86afe-120">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="86afe-120">Optional element.</span></span><br /><br /> <span data-ttu-id="86afe-121">Определяет формат пользовательского элемента управления для представления.</span><span class="sxs-lookup"><span data-stu-id="86afe-121">Defines a custom control format for the view.</span></span>|
|[<span data-ttu-id="86afe-122">Элемент GroupBy для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="86afe-122">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="86afe-123">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="86afe-123">Optional element.</span></span><br /><br /> <span data-ttu-id="86afe-124">Определяет, как группируются элементы объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="86afe-124">Defines how the members of the .NET objects are grouped.</span></span>|
|[<span data-ttu-id="86afe-125">Элемент ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="86afe-125">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)|<span data-ttu-id="86afe-126">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="86afe-126">Optional element.</span></span><br /><br /> <span data-ttu-id="86afe-127">Определяет формат списка для представления.</span><span class="sxs-lookup"><span data-stu-id="86afe-127">Defines a list format for the view.</span></span>|
|[<span data-ttu-id="86afe-128">Элемент Name для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="86afe-128">Name Element for View (Format)</span></span>](./name-element-for-view-format.md)|<span data-ttu-id="86afe-129">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="86afe-129">Required element.</span></span><br /><br /> <span data-ttu-id="86afe-130">Задает имя, используемое для ссылки на представление.</span><span class="sxs-lookup"><span data-stu-id="86afe-130">Specifies the name used to reference the view.</span></span>|
|[<span data-ttu-id="86afe-131">Элемент Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="86afe-131">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)|<span data-ttu-id="86afe-132">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="86afe-132">Optional element.</span></span><br /><br /> <span data-ttu-id="86afe-133">Определяет формат таблицы для представления.</span><span class="sxs-lookup"><span data-stu-id="86afe-133">Defines a table format for the view.</span></span>|
|[<span data-ttu-id="86afe-134">Элемент Виевселектедби для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="86afe-134">ViewSelectedBy Element for View (Format)</span></span>](./viewselectedby-element-format.md)|<span data-ttu-id="86afe-135">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="86afe-135">Required element.</span></span><br /><br /> <span data-ttu-id="86afe-136">Определяет объекты .NET, отображаемые в этом представлении.</span><span class="sxs-lookup"><span data-stu-id="86afe-136">Defines the .NET objects that this view displays.</span></span>|
|[<span data-ttu-id="86afe-137">Элемент Видеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="86afe-137">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)|<span data-ttu-id="86afe-138">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="86afe-138">Optional element.</span></span><br /><br /> <span data-ttu-id="86afe-139">Определяет для представления широкий формат списка (одно значение).</span><span class="sxs-lookup"><span data-stu-id="86afe-139">Defines a wide (single value) list format for the view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="86afe-140">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="86afe-140">Parent Elements</span></span>

|<span data-ttu-id="86afe-141">Элемент</span><span class="sxs-lookup"><span data-stu-id="86afe-141">Element</span></span>|<span data-ttu-id="86afe-142">Описание</span><span class="sxs-lookup"><span data-stu-id="86afe-142">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="86afe-143">Элемент Виевдефинитионс (Format)</span><span class="sxs-lookup"><span data-stu-id="86afe-143">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)|<span data-ttu-id="86afe-144">Определяет представления, используемые для отображения объектов.</span><span class="sxs-lookup"><span data-stu-id="86afe-144">Defines the views used to display objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="86afe-145">Замечания</span><span class="sxs-lookup"><span data-stu-id="86afe-145">Remarks</span></span>

<span data-ttu-id="86afe-146">Дополнительные сведения о компонентах различных представлений и пользовательских элементов управления см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="86afe-146">For more information about the components of different views and custom controls, see the following topics:</span></span>

- [<span data-ttu-id="86afe-147">Компоненты табличного представления</span><span class="sxs-lookup"><span data-stu-id="86afe-147">Table View Components</span></span>](./creating-a-table-view.md)

- [<span data-ttu-id="86afe-148">Компоненты представления списка</span><span class="sxs-lookup"><span data-stu-id="86afe-148">List View Components</span></span>](./creating-a-list-view.md)

- [<span data-ttu-id="86afe-149">Компоненты расширенного представления</span><span class="sxs-lookup"><span data-stu-id="86afe-149">Wide View Components</span></span>](./creating-a-wide-view.md)

- [<span data-ttu-id="86afe-150">Пользовательские элементы управления</span><span class="sxs-lookup"><span data-stu-id="86afe-150">Custom Controls</span></span>](./creating-custom-controls.md)

## <a name="example"></a><span data-ttu-id="86afe-151">Пример</span><span class="sxs-lookup"><span data-stu-id="86afe-151">Example</span></span>

<span data-ttu-id="86afe-152">В этом примере показан элемент `View`, определяющий представление таблицы для объекта [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) .</span><span class="sxs-lookup"><span data-stu-id="86afe-152">This example shows a `View` element that defines a table view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="86afe-153">См. также:</span><span class="sxs-lookup"><span data-stu-id="86afe-153">See Also</span></span>

[<span data-ttu-id="86afe-154">Элемент Виевдефинитионс (Format)</span><span class="sxs-lookup"><span data-stu-id="86afe-154">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)

[<span data-ttu-id="86afe-155">Элемент Name для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="86afe-155">Name Element for View (Format)</span></span>](./name-element-for-view-format.md)

[<span data-ttu-id="86afe-156">Элемент Виевселектедби (Format)</span><span class="sxs-lookup"><span data-stu-id="86afe-156">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)

[<span data-ttu-id="86afe-157">Элемент Controls для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="86afe-157">Controls Element for View (Format)</span></span>](./controls-element-for-view-format.md)

[<span data-ttu-id="86afe-158">Элемент GroupBy для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="86afe-158">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="86afe-159">Элемент Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="86afe-159">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)

[<span data-ttu-id="86afe-160">Элемент ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="86afe-160">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)

[<span data-ttu-id="86afe-161">Элемент Видеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="86afe-161">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)

[<span data-ttu-id="86afe-162">Элемент ошибка customcontrol (Format)</span><span class="sxs-lookup"><span data-stu-id="86afe-162">CustomControl Element (Format)</span></span>](./customcontrol-element-for-groupby-format.md)

[<span data-ttu-id="86afe-163">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="86afe-163">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
