---
title: Элемент Виевселектедби (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: c8704c1504c6e24c9cac6bc8bc25e92a0d9110cc
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785019"
---
# <a name="viewselectedby-element-format"></a><span data-ttu-id="057b7-102">Элемент ViewSelectedBy (формат)</span><span class="sxs-lookup"><span data-stu-id="057b7-102">ViewSelectedBy Element (Format)</span></span>

<span data-ttu-id="057b7-103">Определяет объекты .NET, отображаемые представлением.</span><span class="sxs-lookup"><span data-stu-id="057b7-103">Defines the .NET objects that are displayed by the view.</span></span> <span data-ttu-id="057b7-104">Каждое представление должно содержать по крайней мере один объект .NET.</span><span class="sxs-lookup"><span data-stu-id="057b7-104">Each view must specify at least one .NET object.</span></span>

<span data-ttu-id="057b7-105">Элемент Виевдефинитионс (Format) View элемент (Format) Виевселектедби (формат)</span><span class="sxs-lookup"><span data-stu-id="057b7-105">ViewDefinitions Element (Format) View Element (Format) ViewSelectedBy Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="057b7-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="057b7-106">Syntax</span></span>

```xml
<ViewSelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>SelectionSet</SelectionSetName>
</ViewSelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="057b7-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="057b7-107">Attributes and Elements</span></span>

<span data-ttu-id="057b7-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ViewSelectedBy` элемента.</span><span class="sxs-lookup"><span data-stu-id="057b7-108">The following sections describe the attributes, child elements, and parent element of the `ViewSelectedBy` element.</span></span> <span data-ttu-id="057b7-109">Этот элемент должен содержать по крайней мере один `TypeName` или `SelectionSetName` дочерний элемент.</span><span class="sxs-lookup"><span data-stu-id="057b7-109">This element must contain at least one `TypeName` or `SelectionSetName` child element.</span></span> <span data-ttu-id="057b7-110">Количество дочерних элементов, которые можно указать, не ограничено, а их порядок не является значимым.</span><span class="sxs-lookup"><span data-stu-id="057b7-110">There is no limit to the number of child elements that can be specified nor is their order significant.</span></span>

### <a name="attributes"></a><span data-ttu-id="057b7-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="057b7-111">Attributes</span></span>

<span data-ttu-id="057b7-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="057b7-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="057b7-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="057b7-113">Child Elements</span></span>

|<span data-ttu-id="057b7-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="057b7-114">Element</span></span>|<span data-ttu-id="057b7-115">Описание</span><span class="sxs-lookup"><span data-stu-id="057b7-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="057b7-116">Элемент TypeName для элемента ViewSelectedBy (формат)</span><span class="sxs-lookup"><span data-stu-id="057b7-116">TypeName Element for ViewSelectedBy (Format)</span></span>](./typename-element-for-viewselectedby-format.md)|<span data-ttu-id="057b7-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="057b7-117">Optional element.</span></span><br /><br /> <span data-ttu-id="057b7-118">Задает объект .NET, отображаемый представлением.</span><span class="sxs-lookup"><span data-stu-id="057b7-118">Specifies a .NET object that is displayed by the view.</span></span>|
|[<span data-ttu-id="057b7-119">Элемент SelectionSetName для элемента ViewSelectedBy (формат)</span><span class="sxs-lookup"><span data-stu-id="057b7-119">SelectionSetName Element for ViewSelectedBy (Format)</span></span>](./selectionsetname-element-for-viewselectedby-format.md)|<span data-ttu-id="057b7-120">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="057b7-120">Optional element.</span></span><br /><br /> <span data-ttu-id="057b7-121">Задает набор объектов .NET, отображаемых представлением.</span><span class="sxs-lookup"><span data-stu-id="057b7-121">Specifies a set of .NET objects that are displayed by the view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="057b7-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="057b7-122">Parent Elements</span></span>

|<span data-ttu-id="057b7-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="057b7-123">Element</span></span>|<span data-ttu-id="057b7-124">Описание</span><span class="sxs-lookup"><span data-stu-id="057b7-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="057b7-125">Элемент View (формат)</span><span class="sxs-lookup"><span data-stu-id="057b7-125">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="057b7-126">Определяет представление, в котором отображается один или несколько объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="057b7-126">Defines a view that displays one or more .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="057b7-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="057b7-127">Remarks</span></span>

<span data-ttu-id="057b7-128">Дополнительные сведения об использовании этого элемента в различных представлениях см. в разделе [компоненты табличного](./creating-a-table-view.md)представления, [Компоненты представления списка](./creating-a-list-view.md), [компоненты расширенного представления](./creating-a-wide-view.md)и [компоненты пользовательского элемента управления](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="057b7-128">For more information about how this element is used in different views, see [Table View Components](./creating-a-table-view.md), [List View Components](./creating-a-list-view.md), [Wide View Components](./creating-a-wide-view.md), and [Custom Control Components](./creating-custom-controls.md).</span></span>

<span data-ttu-id="057b7-129">`SelectionSetName`Элемент используется, когда файл форматирования определяет набор объектов, отображаемых несколькими представлениями.</span><span class="sxs-lookup"><span data-stu-id="057b7-129">The `SelectionSetName` element is used when the formatting file defines a set of objects that are displayed by multiple views.</span></span> <span data-ttu-id="057b7-130">Дополнительные сведения о том, как определяются и указываются наборы выбора, см. в разделе [Определение наборов объектов](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="057b7-130">For more information about how selection sets are defined and referenced, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="057b7-131">Пример</span><span class="sxs-lookup"><span data-stu-id="057b7-131">Example</span></span>

<span data-ttu-id="057b7-132">В следующем примере показано, как указать объект [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) для представления списка.</span><span class="sxs-lookup"><span data-stu-id="057b7-132">The following example shows how to specify the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object for a list view.</span></span> <span data-ttu-id="057b7-133">Одна и та же схема используется для таблиц, расширенных и пользовательских представлений.</span><span class="sxs-lookup"><span data-stu-id="057b7-133">The same schema is used for table, wide, and custom views.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a><span data-ttu-id="057b7-134">См. также</span><span class="sxs-lookup"><span data-stu-id="057b7-134">See Also</span></span>

[<span data-ttu-id="057b7-135">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="057b7-135">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="057b7-136">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="057b7-136">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="057b7-137">Создание широкого представления</span><span class="sxs-lookup"><span data-stu-id="057b7-137">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="057b7-138">Создание пользовательских элементов управления</span><span class="sxs-lookup"><span data-stu-id="057b7-138">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="057b7-139">Определение наборов выделенных фрагментов</span><span class="sxs-lookup"><span data-stu-id="057b7-139">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="057b7-140">Элемент SelectionSetName для элемента ViewSelectedBy (формат)</span><span class="sxs-lookup"><span data-stu-id="057b7-140">SelectionSetName Element for ViewSelectedBy (Format)</span></span>](./selectionsetname-element-for-viewselectedby-format.md)

[<span data-ttu-id="057b7-141">Элемент TypeName (Format)</span><span class="sxs-lookup"><span data-stu-id="057b7-141">TypeName Element (Format)</span></span>](./typename-element-for-viewselectedby-format.md)

[<span data-ttu-id="057b7-142">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="057b7-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
