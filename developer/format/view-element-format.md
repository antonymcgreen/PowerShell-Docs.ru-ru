---
title: Просмотреть элемент (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d837d5d4-ed2e-4d84-a306-0b5d2ad2d0bf
caps.latest.revision: 24
ms.openlocfilehash: 2361c1117757569bef0815018c75764430a9e7a8
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083728"
---
# <a name="view-element-format"></a><span data-ttu-id="480f7-102">Элемент View (формат)</span><span class="sxs-lookup"><span data-stu-id="480f7-102">View Element (Format)</span></span>

<span data-ttu-id="480f7-103">Определяет представление, которое отображает один или несколько объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="480f7-103">Defines a view that displays one or more .NET objects.</span></span> <span data-ttu-id="480f7-104">Нет ограничений на количество представлений, которые могут быть определены в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="480f7-104">There is no limit to the number of views that can be defined in a formatting file.</span></span>

<span data-ttu-id="480f7-105">Элемент представления ViewDefinitions элемент (формат) конфигурации элемент (формат) (формат)</span><span class="sxs-lookup"><span data-stu-id="480f7-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="480f7-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="480f7-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="480f7-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="480f7-107">Attributes and Elements</span></span>

<span data-ttu-id="480f7-108">В следующих разделах атрибуты, дочерние элементы и родительский элемент `View` элемент.</span><span class="sxs-lookup"><span data-stu-id="480f7-108">The following sections describe the attributes, child elements, and the parent element of the `View` element.</span></span> <span data-ttu-id="480f7-109">Необходимо указать один и только один из дочерних элементов управления, и необходимо указать имя представления и объекты, используемые представления.</span><span class="sxs-lookup"><span data-stu-id="480f7-109">You must specify one and only one of the control child elements, and you must specify the name of the view and the objects that use the view.</span></span> <span data-ttu-id="480f7-110">Определение пользовательских элементов управления, как группировать объекты и указание, если это представление является out of band являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="480f7-110">Defining custom controls, how to group objects, and specifying if the view is out-of-band are optional.</span></span>

### <a name="attributes"></a><span data-ttu-id="480f7-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="480f7-111">Attributes</span></span>

<span data-ttu-id="480f7-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="480f7-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="480f7-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="480f7-113">Child Elements</span></span>

|<span data-ttu-id="480f7-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="480f7-114">Element</span></span>|<span data-ttu-id="480f7-115">Описание</span><span class="sxs-lookup"><span data-stu-id="480f7-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="480f7-116">Элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="480f7-116">Controls Element for View (Format)</span></span>](./controls-element-for-view-format.md)|<span data-ttu-id="480f7-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="480f7-117">Optional element.</span></span><br /><br /> <span data-ttu-id="480f7-118">Определяет набор элементов управления, которые можно ссылаться по имени в представлении.</span><span class="sxs-lookup"><span data-stu-id="480f7-118">Defines a set of controls that can be referenced by their name from within the view.</span></span>|
|[<span data-ttu-id="480f7-119">Пользовательский элемент управления элемент (формат)</span><span class="sxs-lookup"><span data-stu-id="480f7-119">CustomControl Element (Format)</span></span>](./customcontrol-element-for-groupby-format.md)|<span data-ttu-id="480f7-120">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="480f7-120">Optional element.</span></span><br /><br /> <span data-ttu-id="480f7-121">Определяет формат для представления пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="480f7-121">Defines a custom control format for the view.</span></span>|
|[<span data-ttu-id="480f7-122">GroupBy-элемент для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="480f7-122">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="480f7-123">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="480f7-123">Optional element.</span></span><br /><br /> <span data-ttu-id="480f7-124">Определяет, каким образом группируются члены объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="480f7-124">Defines how the members of the .NET objects are grouped.</span></span>|
|[<span data-ttu-id="480f7-125">Элемент ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="480f7-125">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)|<span data-ttu-id="480f7-126">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="480f7-126">Optional element.</span></span><br /><br /> <span data-ttu-id="480f7-127">Определяет формат для представления списка.</span><span class="sxs-lookup"><span data-stu-id="480f7-127">Defines a list format for the view.</span></span>|
|[<span data-ttu-id="480f7-128">Элемент Name описания представления (формат)</span><span class="sxs-lookup"><span data-stu-id="480f7-128">Name Element for View (Format)</span></span>](./name-element-for-view-format.md)|<span data-ttu-id="480f7-129">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="480f7-129">Required element.</span></span><br /><br /> <span data-ttu-id="480f7-130">Указывает имя, используемое для ссылки на представление.</span><span class="sxs-lookup"><span data-stu-id="480f7-130">Specifies the name used to reference the view.</span></span>|
|[<span data-ttu-id="480f7-131">TableControl-элемент (формат)</span><span class="sxs-lookup"><span data-stu-id="480f7-131">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)|<span data-ttu-id="480f7-132">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="480f7-132">Optional element.</span></span><br /><br /> <span data-ttu-id="480f7-133">Определяет формат таблицы для представления.</span><span class="sxs-lookup"><span data-stu-id="480f7-133">Defines a table format for the view.</span></span>|
|[<span data-ttu-id="480f7-134">Элемент ViewSelectedBy для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="480f7-134">ViewSelectedBy Element for View (Format)</span></span>](./viewselectedby-element-format.md)|<span data-ttu-id="480f7-135">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="480f7-135">Required element.</span></span><br /><br /> <span data-ttu-id="480f7-136">Определяет, в этом представлении отображаются объекты .NET.</span><span class="sxs-lookup"><span data-stu-id="480f7-136">Defines the .NET objects that this view displays.</span></span>|
|[<span data-ttu-id="480f7-137">Элемент WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="480f7-137">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)|<span data-ttu-id="480f7-138">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="480f7-138">Optional element.</span></span><br /><br /> <span data-ttu-id="480f7-139">Большое (значение одно значение) определяет формат списка для представления.</span><span class="sxs-lookup"><span data-stu-id="480f7-139">Defines a wide (single value) list format for the view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="480f7-140">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="480f7-140">Parent Elements</span></span>

|<span data-ttu-id="480f7-141">Элемент</span><span class="sxs-lookup"><span data-stu-id="480f7-141">Element</span></span>|<span data-ttu-id="480f7-142">Описание</span><span class="sxs-lookup"><span data-stu-id="480f7-142">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="480f7-143">Элемент ViewDefinitions (формат)</span><span class="sxs-lookup"><span data-stu-id="480f7-143">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)|<span data-ttu-id="480f7-144">Определяет представления для отображения объектов.</span><span class="sxs-lookup"><span data-stu-id="480f7-144">Defines the views used to display objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="480f7-145">Замечания</span><span class="sxs-lookup"><span data-stu-id="480f7-145">Remarks</span></span>

<span data-ttu-id="480f7-146">Дополнительные сведения о компонентах различные представления и пользовательские элементы управления см. в разделах:</span><span class="sxs-lookup"><span data-stu-id="480f7-146">For more information about the components of different views and custom controls, see the following topics:</span></span>

- [<span data-ttu-id="480f7-147">Компоненты представлений таблицы</span><span class="sxs-lookup"><span data-stu-id="480f7-147">Table View Components</span></span>](./creating-a-table-view.md)

- [<span data-ttu-id="480f7-148">Компоненты представлений списка</span><span class="sxs-lookup"><span data-stu-id="480f7-148">List View Components</span></span>](./creating-a-list-view.md)

- [<span data-ttu-id="480f7-149">Широкое представление компонентов</span><span class="sxs-lookup"><span data-stu-id="480f7-149">Wide View Components</span></span>](./creating-a-wide-view.md)

- [<span data-ttu-id="480f7-150">Пользовательские элементы управления</span><span class="sxs-lookup"><span data-stu-id="480f7-150">Custom Controls</span></span>](./creating-custom-controls.md)

## <a name="example"></a><span data-ttu-id="480f7-151">Пример</span><span class="sxs-lookup"><span data-stu-id="480f7-151">Example</span></span>

<span data-ttu-id="480f7-152">В этом примере показано `View` элемент, который определяет представление таблицы для [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) объекта.</span><span class="sxs-lookup"><span data-stu-id="480f7-152">This example shows a `View` element that defines a table view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="480f7-153">См. также</span><span class="sxs-lookup"><span data-stu-id="480f7-153">See Also</span></span>

[<span data-ttu-id="480f7-154">Элемент ViewDefinitions (формат)</span><span class="sxs-lookup"><span data-stu-id="480f7-154">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)

[<span data-ttu-id="480f7-155">Элемент Name описания представления (формат)</span><span class="sxs-lookup"><span data-stu-id="480f7-155">Name Element for View (Format)</span></span>](./name-element-for-view-format.md)

[<span data-ttu-id="480f7-156">Элемент ViewSelectedBy (формат)</span><span class="sxs-lookup"><span data-stu-id="480f7-156">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)

[<span data-ttu-id="480f7-157">Элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="480f7-157">Controls Element for View (Format)</span></span>](./controls-element-for-view-format.md)

[<span data-ttu-id="480f7-158">GroupBy-элемент для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="480f7-158">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="480f7-159">TableControl-элемент (формат)</span><span class="sxs-lookup"><span data-stu-id="480f7-159">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)

[<span data-ttu-id="480f7-160">Элемент ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="480f7-160">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)

[<span data-ttu-id="480f7-161">Элемент WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="480f7-161">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)

[<span data-ttu-id="480f7-162">Пользовательский элемент управления элемент (формат)</span><span class="sxs-lookup"><span data-stu-id="480f7-162">CustomControl Element (Format)</span></span>](./customcontrol-element-for-groupby-format.md)

[<span data-ttu-id="480f7-163">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="480f7-163">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
