---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент ViewSelectedBy (формат)
description: Элемент ViewSelectedBy (формат)
ms.openlocfilehash: ac3c7de299b3009a067a476a024c6a6fcb5dce02
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667714"
---
# <a name="viewselectedby-element-format"></a><span data-ttu-id="836ff-103">Элемент ViewSelectedBy (формат)</span><span class="sxs-lookup"><span data-stu-id="836ff-103">ViewSelectedBy Element (Format)</span></span>

<span data-ttu-id="836ff-104">Определяет объекты .NET, отображаемые представлением.</span><span class="sxs-lookup"><span data-stu-id="836ff-104">Defines the .NET objects that are displayed by the view.</span></span> <span data-ttu-id="836ff-105">Каждое представление должно содержать по крайней мере один объект .NET.</span><span class="sxs-lookup"><span data-stu-id="836ff-105">Each view must specify at least one .NET object.</span></span>

<span data-ttu-id="836ff-106">Элемент Виевдефинитионс (Format) View элемент (Format) Виевселектедби (формат)</span><span class="sxs-lookup"><span data-stu-id="836ff-106">ViewDefinitions Element (Format) View Element (Format) ViewSelectedBy Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="836ff-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="836ff-107">Syntax</span></span>

```xml
<ViewSelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>SelectionSet</SelectionSetName>
</ViewSelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="836ff-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="836ff-108">Attributes and Elements</span></span>

<span data-ttu-id="836ff-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ViewSelectedBy` элемента.</span><span class="sxs-lookup"><span data-stu-id="836ff-109">The following sections describe the attributes, child elements, and parent element of the `ViewSelectedBy` element.</span></span> <span data-ttu-id="836ff-110">Этот элемент должен содержать по крайней мере один `TypeName` или `SelectionSetName` дочерний элемент.</span><span class="sxs-lookup"><span data-stu-id="836ff-110">This element must contain at least one `TypeName` or `SelectionSetName` child element.</span></span> <span data-ttu-id="836ff-111">Количество дочерних элементов, которые можно указать, не ограничено, а их порядок не является значимым.</span><span class="sxs-lookup"><span data-stu-id="836ff-111">There is no limit to the number of child elements that can be specified nor is their order significant.</span></span>

### <a name="attributes"></a><span data-ttu-id="836ff-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="836ff-112">Attributes</span></span>

<span data-ttu-id="836ff-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="836ff-113">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="836ff-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="836ff-114">Child Elements</span></span>

|<span data-ttu-id="836ff-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="836ff-115">Element</span></span>|<span data-ttu-id="836ff-116">Описание</span><span class="sxs-lookup"><span data-stu-id="836ff-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="836ff-117">Элемент TypeName для элемента ViewSelectedBy (формат)</span><span class="sxs-lookup"><span data-stu-id="836ff-117">TypeName Element for ViewSelectedBy (Format)</span></span>](./typename-element-for-viewselectedby-format.md)|<span data-ttu-id="836ff-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="836ff-118">Optional element.</span></span><br /><br /> <span data-ttu-id="836ff-119">Задает объект .NET, отображаемый представлением.</span><span class="sxs-lookup"><span data-stu-id="836ff-119">Specifies a .NET object that is displayed by the view.</span></span>|
|[<span data-ttu-id="836ff-120">Элемент SelectionSetName для элемента ViewSelectedBy (формат)</span><span class="sxs-lookup"><span data-stu-id="836ff-120">SelectionSetName Element for ViewSelectedBy (Format)</span></span>](./selectionsetname-element-for-viewselectedby-format.md)|<span data-ttu-id="836ff-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="836ff-121">Optional element.</span></span><br /><br /> <span data-ttu-id="836ff-122">Задает набор объектов .NET, отображаемых представлением.</span><span class="sxs-lookup"><span data-stu-id="836ff-122">Specifies a set of .NET objects that are displayed by the view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="836ff-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="836ff-123">Parent Elements</span></span>

|<span data-ttu-id="836ff-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="836ff-124">Element</span></span>|<span data-ttu-id="836ff-125">Описание</span><span class="sxs-lookup"><span data-stu-id="836ff-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="836ff-126">Элемент View (формат)</span><span class="sxs-lookup"><span data-stu-id="836ff-126">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="836ff-127">Определяет представление, в котором отображается один или несколько объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="836ff-127">Defines a view that displays one or more .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="836ff-128">Комментарии</span><span class="sxs-lookup"><span data-stu-id="836ff-128">Remarks</span></span>

<span data-ttu-id="836ff-129">Дополнительные сведения об использовании этого элемента в различных представлениях см. в разделе [компоненты табличного](./creating-a-table-view.md)представления, [Компоненты представления списка](./creating-a-list-view.md), [компоненты расширенного представления](./creating-a-wide-view.md)и [компоненты пользовательского элемента управления](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="836ff-129">For more information about how this element is used in different views, see [Table View Components](./creating-a-table-view.md), [List View Components](./creating-a-list-view.md), [Wide View Components](./creating-a-wide-view.md), and [Custom Control Components](./creating-custom-controls.md).</span></span>

<span data-ttu-id="836ff-130">`SelectionSetName`Элемент используется, когда файл форматирования определяет набор объектов, отображаемых несколькими представлениями.</span><span class="sxs-lookup"><span data-stu-id="836ff-130">The `SelectionSetName` element is used when the formatting file defines a set of objects that are displayed by multiple views.</span></span> <span data-ttu-id="836ff-131">Дополнительные сведения о том, как определяются и указываются наборы выбора, см. в разделе [Определение наборов объектов](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="836ff-131">For more information about how selection sets are defined and referenced, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="836ff-132">Пример</span><span class="sxs-lookup"><span data-stu-id="836ff-132">Example</span></span>

<span data-ttu-id="836ff-133">В следующем примере показано, как указать объект [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) для представления списка.</span><span class="sxs-lookup"><span data-stu-id="836ff-133">The following example shows how to specify the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object for a list view.</span></span> <span data-ttu-id="836ff-134">Одна и та же схема используется для таблиц, расширенных и пользовательских представлений.</span><span class="sxs-lookup"><span data-stu-id="836ff-134">The same schema is used for table, wide, and custom views.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a><span data-ttu-id="836ff-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="836ff-135">See Also</span></span>

[<span data-ttu-id="836ff-136">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="836ff-136">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="836ff-137">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="836ff-137">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="836ff-138">Создание широкого представления</span><span class="sxs-lookup"><span data-stu-id="836ff-138">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="836ff-139">Создание пользовательских элементов управления</span><span class="sxs-lookup"><span data-stu-id="836ff-139">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="836ff-140">Определение наборов выделенных фрагментов</span><span class="sxs-lookup"><span data-stu-id="836ff-140">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="836ff-141">Элемент SelectionSetName для элемента ViewSelectedBy (формат)</span><span class="sxs-lookup"><span data-stu-id="836ff-141">SelectionSetName Element for ViewSelectedBy (Format)</span></span>](./selectionsetname-element-for-viewselectedby-format.md)

[<span data-ttu-id="836ff-142">Элемент TypeName (Format)</span><span class="sxs-lookup"><span data-stu-id="836ff-142">TypeName Element (Format)</span></span>](./typename-element-for-viewselectedby-format.md)

[<span data-ttu-id="836ff-143">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="836ff-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
