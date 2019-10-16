---
title: Элемент Виевселектедби (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: acdeef4d-3554-4f39-a7e6-a684e3848fd7
caps.latest.revision: 19
ms.openlocfilehash: efc1c5d1338889ecd0be7150b7733842ce78979e
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72367973"
---
# <a name="viewselectedby-element-format"></a><span data-ttu-id="b4b84-102">Элемент ViewSelectedBy (формат)</span><span class="sxs-lookup"><span data-stu-id="b4b84-102">ViewSelectedBy Element (Format)</span></span>

<span data-ttu-id="b4b84-103">Определяет объекты .NET, отображаемые представлением.</span><span class="sxs-lookup"><span data-stu-id="b4b84-103">Defines the .NET objects that are displayed by the view.</span></span> <span data-ttu-id="b4b84-104">Каждое представление должно содержать по крайней мере один объект .NET.</span><span class="sxs-lookup"><span data-stu-id="b4b84-104">Each view must specify at least one .NET object.</span></span>

<span data-ttu-id="b4b84-105">Элемент Виевдефинитионс (Format) View элемент (Format) Виевселектедби (формат)</span><span class="sxs-lookup"><span data-stu-id="b4b84-105">ViewDefinitions Element (Format) View Element (Format) ViewSelectedBy Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b4b84-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b4b84-106">Syntax</span></span>

```xml
<ViewSelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>SelectionSet</SelectionSetName>
</ViewSelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b4b84-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b4b84-107">Attributes and Elements</span></span>

<span data-ttu-id="b4b84-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `ViewSelectedBy`.</span><span class="sxs-lookup"><span data-stu-id="b4b84-108">The following sections describe the attributes, child elements, and parent element of the `ViewSelectedBy` element.</span></span> <span data-ttu-id="b4b84-109">Этот элемент должен содержать по крайней мере один дочерний элемент `TypeName` или `SelectionSetName`.</span><span class="sxs-lookup"><span data-stu-id="b4b84-109">This element must contain at least one `TypeName` or `SelectionSetName` child element.</span></span> <span data-ttu-id="b4b84-110">Количество дочерних элементов, которые можно указать, не ограничено, а их порядок не является значимым.</span><span class="sxs-lookup"><span data-stu-id="b4b84-110">There is no limit to the number of child elements that can be specified nor is their order significant.</span></span>

### <a name="attributes"></a><span data-ttu-id="b4b84-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b4b84-111">Attributes</span></span>

<span data-ttu-id="b4b84-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="b4b84-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b4b84-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b4b84-113">Child Elements</span></span>

|<span data-ttu-id="b4b84-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="b4b84-114">Element</span></span>|<span data-ttu-id="b4b84-115">Описание</span><span class="sxs-lookup"><span data-stu-id="b4b84-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b4b84-116">Элемент TypeName для Виевселектедби (Format)</span><span class="sxs-lookup"><span data-stu-id="b4b84-116">TypeName Element for ViewSelectedBy (Format)</span></span>](./typename-element-for-viewselectedby-format.md)|<span data-ttu-id="b4b84-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="b4b84-117">Optional element.</span></span><br /><br /> <span data-ttu-id="b4b84-118">Задает объект .NET, отображаемый представлением.</span><span class="sxs-lookup"><span data-stu-id="b4b84-118">Specifies a .NET object that is displayed by the view.</span></span>|
|[<span data-ttu-id="b4b84-119">Элемент Селектионсетнаме для Виевселектедби (Format)</span><span class="sxs-lookup"><span data-stu-id="b4b84-119">SelectionSetName Element for ViewSelectedBy (Format)</span></span>](./selectionsetname-element-for-viewselectedby-format.md)|<span data-ttu-id="b4b84-120">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="b4b84-120">Optional element.</span></span><br /><br /> <span data-ttu-id="b4b84-121">Задает набор объектов .NET, отображаемых представлением.</span><span class="sxs-lookup"><span data-stu-id="b4b84-121">Specifies a set of .NET objects that are displayed by the view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="b4b84-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b4b84-122">Parent Elements</span></span>

|<span data-ttu-id="b4b84-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="b4b84-123">Element</span></span>|<span data-ttu-id="b4b84-124">Описание</span><span class="sxs-lookup"><span data-stu-id="b4b84-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b4b84-125">View, элемент (Format)</span><span class="sxs-lookup"><span data-stu-id="b4b84-125">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="b4b84-126">Определяет представление, в котором отображается один или несколько объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="b4b84-126">Defines a view that displays one or more .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b4b84-127">Замечания</span><span class="sxs-lookup"><span data-stu-id="b4b84-127">Remarks</span></span>

<span data-ttu-id="b4b84-128">Дополнительные сведения об использовании этого элемента в различных представлениях см. в разделе [компоненты табличного](./creating-a-table-view.md)представления, [Компоненты представления списка](./creating-a-list-view.md), [компоненты расширенного представления](./creating-a-wide-view.md)и [компоненты пользовательского элемента управления](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="b4b84-128">For more information about how this element is used in different views, see [Table View Components](./creating-a-table-view.md), [List View Components](./creating-a-list-view.md), [Wide View Components](./creating-a-wide-view.md), and [Custom Control Components](./creating-custom-controls.md).</span></span>

<span data-ttu-id="b4b84-129">Элемент `SelectionSetName` используется, когда файл форматирования определяет набор объектов, отображаемых несколькими представлениями.</span><span class="sxs-lookup"><span data-stu-id="b4b84-129">The `SelectionSetName` element is used when the formatting file defines a set of objects that are displayed by multiple views.</span></span> <span data-ttu-id="b4b84-130">Дополнительные сведения о том, как определяются и указываются наборы выбора, см. в разделе [Определение наборов объектов](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="b4b84-130">For more information about how selection sets are defined and referenced, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="b4b84-131">Пример</span><span class="sxs-lookup"><span data-stu-id="b4b84-131">Example</span></span>

<span data-ttu-id="b4b84-132">В следующем примере показано, как указать объект [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) для представления списка.</span><span class="sxs-lookup"><span data-stu-id="b4b84-132">The following example shows how to specify the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object for a list view.</span></span> <span data-ttu-id="b4b84-133">Одна и та же схема используется для таблиц, расширенных и пользовательских представлений.</span><span class="sxs-lookup"><span data-stu-id="b4b84-133">The same schema is used for table, wide, and custom views.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a><span data-ttu-id="b4b84-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="b4b84-134">See Also</span></span>

[<span data-ttu-id="b4b84-135">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="b4b84-135">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="b4b84-136">Создание табличного представления</span><span class="sxs-lookup"><span data-stu-id="b4b84-136">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="b4b84-137">Создание расширенного представления</span><span class="sxs-lookup"><span data-stu-id="b4b84-137">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="b4b84-138">Создание пользовательских элементов управления</span><span class="sxs-lookup"><span data-stu-id="b4b84-138">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="b4b84-139">Определение наборов выбора</span><span class="sxs-lookup"><span data-stu-id="b4b84-139">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="b4b84-140">Элемент Селектионсетнаме для Виевселектедби (Format)</span><span class="sxs-lookup"><span data-stu-id="b4b84-140">SelectionSetName Element for ViewSelectedBy (Format)</span></span>](./selectionsetname-element-for-viewselectedby-format.md)

[<span data-ttu-id="b4b84-141">Элемент TypeName (Format)</span><span class="sxs-lookup"><span data-stu-id="b4b84-141">TypeName Element (Format)</span></span>](./typename-element-for-viewselectedby-format.md)

[<span data-ttu-id="b4b84-142">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="b4b84-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
