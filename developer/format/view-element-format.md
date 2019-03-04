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
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856150"
---
# <a name="view-element-format"></a><span data-ttu-id="993c3-102">Элемент View (формат)</span><span class="sxs-lookup"><span data-stu-id="993c3-102">View Element (Format)</span></span>

<span data-ttu-id="993c3-103">Определяет представление, которое отображает один или несколько объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="993c3-103">Defines a view that displays one or more .NET objects.</span></span> <span data-ttu-id="993c3-104">Нет ограничений на количество представлений, которые могут быть определены в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="993c3-104">There is no limit to the number of views that can be defined in a formatting file.</span></span>

<span data-ttu-id="993c3-105">Элемент представления ViewDefinitions элемент (формат) конфигурации элемент (формат) (формат)</span><span class="sxs-lookup"><span data-stu-id="993c3-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="993c3-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="993c3-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="993c3-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="993c3-107">Attributes and Elements</span></span>

<span data-ttu-id="993c3-108">В следующих разделах атрибуты, дочерние элементы и родительский элемент `View` элемент.</span><span class="sxs-lookup"><span data-stu-id="993c3-108">The following sections describe the attributes, child elements, and the parent element of the `View` element.</span></span> <span data-ttu-id="993c3-109">Необходимо указать один и только один из дочерних элементов управления, и необходимо указать имя представления и объекты, используемые представления.</span><span class="sxs-lookup"><span data-stu-id="993c3-109">You must specify one and only one of the control child elements, and you must specify the name of the view and the objects that use the view.</span></span> <span data-ttu-id="993c3-110">Определение пользовательских элементов управления, как группировать объекты и указание, если это представление является out of band являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="993c3-110">Defining custom controls, how to group objects, and specifying if the view is out-of-band are optional.</span></span>

### <a name="attributes"></a><span data-ttu-id="993c3-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="993c3-111">Attributes</span></span>

<span data-ttu-id="993c3-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="993c3-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="993c3-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="993c3-113">Child Elements</span></span>

|<span data-ttu-id="993c3-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="993c3-114">Element</span></span>|<span data-ttu-id="993c3-115">Описание</span><span class="sxs-lookup"><span data-stu-id="993c3-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="993c3-116">Элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="993c3-116">Controls Element for View (Format)</span></span>](./controls-element-for-view-format.md)|<span data-ttu-id="993c3-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="993c3-117">Optional element.</span></span><br /><br /> <span data-ttu-id="993c3-118">Определяет набор элементов управления, которые можно ссылаться по имени в представлении.</span><span class="sxs-lookup"><span data-stu-id="993c3-118">Defines a set of controls that can be referenced by their name from within the view.</span></span>|
|[<span data-ttu-id="993c3-119">Пользовательский элемент управления элемент (формат)</span><span class="sxs-lookup"><span data-stu-id="993c3-119">CustomControl Element (Format)</span></span>](./customcontrol-element-for-groupby-format.md)|<span data-ttu-id="993c3-120">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="993c3-120">Optional element.</span></span><br /><br /> <span data-ttu-id="993c3-121">Определяет формат для представления пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="993c3-121">Defines a custom control format for the view.</span></span>|
|[<span data-ttu-id="993c3-122">GroupBy-элемент для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="993c3-122">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="993c3-123">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="993c3-123">Optional element.</span></span><br /><br /> <span data-ttu-id="993c3-124">Определяет, каким образом группируются члены объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="993c3-124">Defines how the members of the .NET objects are grouped.</span></span>|
|[<span data-ttu-id="993c3-125">Элемент ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="993c3-125">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)|<span data-ttu-id="993c3-126">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="993c3-126">Optional element.</span></span><br /><br /> <span data-ttu-id="993c3-127">Определяет формат для представления списка.</span><span class="sxs-lookup"><span data-stu-id="993c3-127">Defines a list format for the view.</span></span>|
|[<span data-ttu-id="993c3-128">Элемент Name описания представления (формат)</span><span class="sxs-lookup"><span data-stu-id="993c3-128">Name Element for View (Format)</span></span>](./name-element-for-view-format.md)|<span data-ttu-id="993c3-129">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="993c3-129">Required element.</span></span><br /><br /> <span data-ttu-id="993c3-130">Указывает имя, используемое для ссылки на представление.</span><span class="sxs-lookup"><span data-stu-id="993c3-130">Specifies the name used to reference the view.</span></span>|
|[<span data-ttu-id="993c3-131">TableControl-элемент (формат)</span><span class="sxs-lookup"><span data-stu-id="993c3-131">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)|<span data-ttu-id="993c3-132">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="993c3-132">Optional element.</span></span><br /><br /> <span data-ttu-id="993c3-133">Определяет формат таблицы для представления.</span><span class="sxs-lookup"><span data-stu-id="993c3-133">Defines a table format for the view.</span></span>|
|[<span data-ttu-id="993c3-134">Элемент ViewSelectedBy для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="993c3-134">ViewSelectedBy Element for View (Format)</span></span>](./viewselectedby-element-format.md)|<span data-ttu-id="993c3-135">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="993c3-135">Required element.</span></span><br /><br /> <span data-ttu-id="993c3-136">Определяет, в этом представлении отображаются объекты .NET.</span><span class="sxs-lookup"><span data-stu-id="993c3-136">Defines the .NET objects that this view displays.</span></span>|
|[<span data-ttu-id="993c3-137">Элемент WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="993c3-137">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)|<span data-ttu-id="993c3-138">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="993c3-138">Optional element.</span></span><br /><br /> <span data-ttu-id="993c3-139">Большое (значение одно значение) определяет формат списка для представления.</span><span class="sxs-lookup"><span data-stu-id="993c3-139">Defines a wide (single value) list format for the view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="993c3-140">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="993c3-140">Parent Elements</span></span>

|<span data-ttu-id="993c3-141">Элемент</span><span class="sxs-lookup"><span data-stu-id="993c3-141">Element</span></span>|<span data-ttu-id="993c3-142">Описание</span><span class="sxs-lookup"><span data-stu-id="993c3-142">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="993c3-143">Элемент ViewDefinitions (формат)</span><span class="sxs-lookup"><span data-stu-id="993c3-143">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)|<span data-ttu-id="993c3-144">Определяет представления для отображения объектов.</span><span class="sxs-lookup"><span data-stu-id="993c3-144">Defines the views used to display objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="993c3-145">Замечания</span><span class="sxs-lookup"><span data-stu-id="993c3-145">Remarks</span></span>

<span data-ttu-id="993c3-146">Дополнительные сведения о компонентах различные представления и пользовательские элементы управления см. в разделах:</span><span class="sxs-lookup"><span data-stu-id="993c3-146">For more information about the components of different views and custom controls, see the following topics:</span></span>

- [<span data-ttu-id="993c3-147">Компоненты представлений таблицы</span><span class="sxs-lookup"><span data-stu-id="993c3-147">Table View Components</span></span>](./creating-a-table-view.md)

- [<span data-ttu-id="993c3-148">Компоненты представлений списка</span><span class="sxs-lookup"><span data-stu-id="993c3-148">List View Components</span></span>](./creating-a-list-view.md)

- [<span data-ttu-id="993c3-149">Широкое представление компонентов</span><span class="sxs-lookup"><span data-stu-id="993c3-149">Wide View Components</span></span>](./creating-a-wide-view.md)

- [<span data-ttu-id="993c3-150">Пользовательские элементы управления</span><span class="sxs-lookup"><span data-stu-id="993c3-150">Custom Controls</span></span>](./creating-custom-controls.md)

## <a name="example"></a><span data-ttu-id="993c3-151">Пример</span><span class="sxs-lookup"><span data-stu-id="993c3-151">Example</span></span>

<span data-ttu-id="993c3-152">В этом примере показано `View` элемент, который определяет представление таблицы для [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) объекта.</span><span class="sxs-lookup"><span data-stu-id="993c3-152">This example shows a `View` element that defines a table view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="993c3-153">См. также</span><span class="sxs-lookup"><span data-stu-id="993c3-153">See Also</span></span>

[<span data-ttu-id="993c3-154">Элемент ViewDefinitions (формат)</span><span class="sxs-lookup"><span data-stu-id="993c3-154">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)

[<span data-ttu-id="993c3-155">Элемент Name описания представления (формат)</span><span class="sxs-lookup"><span data-stu-id="993c3-155">Name Element for View (Format)</span></span>](./name-element-for-view-format.md)

[<span data-ttu-id="993c3-156">Элемент ViewSelectedBy (формат)</span><span class="sxs-lookup"><span data-stu-id="993c3-156">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)

[<span data-ttu-id="993c3-157">Элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="993c3-157">Controls Element for View (Format)</span></span>](./controls-element-for-view-format.md)

[<span data-ttu-id="993c3-158">GroupBy-элемент для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="993c3-158">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="993c3-159">TableControl-элемент (формат)</span><span class="sxs-lookup"><span data-stu-id="993c3-159">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)

[<span data-ttu-id="993c3-160">Элемент ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="993c3-160">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)

[<span data-ttu-id="993c3-161">Элемент WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="993c3-161">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)

[<span data-ttu-id="993c3-162">Пользовательский элемент управления элемент (формат)</span><span class="sxs-lookup"><span data-stu-id="993c3-162">CustomControl Element (Format)</span></span>](./customcontrol-element-for-groupby-format.md)

[<span data-ttu-id="993c3-163">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="993c3-163">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
