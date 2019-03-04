---
title: Элемент ViewSelectedBy (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: acdeef4d-3554-4f39-a7e6-a684e3848fd7
caps.latest.revision: 19
ms.openlocfilehash: efc1c5d1338889ecd0be7150b7733842ce78979e
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56863190"
---
# <a name="viewselectedby-element-format"></a><span data-ttu-id="b2b6d-102">Элемент ViewSelectedBy (формат)</span><span class="sxs-lookup"><span data-stu-id="b2b6d-102">ViewSelectedBy Element (Format)</span></span>

<span data-ttu-id="b2b6d-103">Определяет объекты .NET, которые отображаются в представлении.</span><span class="sxs-lookup"><span data-stu-id="b2b6d-103">Defines the .NET objects that are displayed by the view.</span></span> <span data-ttu-id="b2b6d-104">Каждое представление необходимо указать хотя бы один объект .NET.</span><span class="sxs-lookup"><span data-stu-id="b2b6d-104">Each view must specify at least one .NET object.</span></span>

<span data-ttu-id="b2b6d-105">Элемент ViewDefinitions (формат) представления (формат) ViewSelectedBy элемента (формат)</span><span class="sxs-lookup"><span data-stu-id="b2b6d-105">ViewDefinitions Element (Format) View Element (Format) ViewSelectedBy Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b2b6d-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b2b6d-106">Syntax</span></span>

```xml
<ViewSelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>SelectionSet</SelectionSetName>
</ViewSelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b2b6d-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b2b6d-107">Attributes and Elements</span></span>

<span data-ttu-id="b2b6d-108">В следующих разделах атрибуты, дочерние элементы и родительский элемент `ViewSelectedBy` элемент.</span><span class="sxs-lookup"><span data-stu-id="b2b6d-108">The following sections describe the attributes, child elements, and parent element of the `ViewSelectedBy` element.</span></span> <span data-ttu-id="b2b6d-109">Этот элемент должен содержать по крайней мере один `TypeName` или `SelectionSetName` дочерний элемент.</span><span class="sxs-lookup"><span data-stu-id="b2b6d-109">This element must contain at least one `TypeName` or `SelectionSetName` child element.</span></span> <span data-ttu-id="b2b6d-110">Нет ограничений на количество дочерних элементов, которые могут быть указаны и не важен их порядок.</span><span class="sxs-lookup"><span data-stu-id="b2b6d-110">There is no limit to the number of child elements that can be specified nor is their order significant.</span></span>

### <a name="attributes"></a><span data-ttu-id="b2b6d-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b2b6d-111">Attributes</span></span>

<span data-ttu-id="b2b6d-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="b2b6d-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b2b6d-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b2b6d-113">Child Elements</span></span>

|<span data-ttu-id="b2b6d-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="b2b6d-114">Element</span></span>|<span data-ttu-id="b2b6d-115">Описание</span><span class="sxs-lookup"><span data-stu-id="b2b6d-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b2b6d-116">TypeName-элемент для ViewSelectedBy (формат)</span><span class="sxs-lookup"><span data-stu-id="b2b6d-116">TypeName Element for ViewSelectedBy (Format)</span></span>](./typename-element-for-viewselectedby-format.md)|<span data-ttu-id="b2b6d-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="b2b6d-117">Optional element.</span></span><br /><br /> <span data-ttu-id="b2b6d-118">Указывает объект .NET, который отображается в представлении.</span><span class="sxs-lookup"><span data-stu-id="b2b6d-118">Specifies a .NET object that is displayed by the view.</span></span>|
|[<span data-ttu-id="b2b6d-119">Элемент SelectionSetName для ViewSelectedBy (формат)</span><span class="sxs-lookup"><span data-stu-id="b2b6d-119">SelectionSetName Element for ViewSelectedBy (Format)</span></span>](./selectionsetname-element-for-viewselectedby-format.md)|<span data-ttu-id="b2b6d-120">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="b2b6d-120">Optional element.</span></span><br /><br /> <span data-ttu-id="b2b6d-121">Задает набор объектов .NET, которые отображаются в представлении.</span><span class="sxs-lookup"><span data-stu-id="b2b6d-121">Specifies a set of .NET objects that are displayed by the view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="b2b6d-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b2b6d-122">Parent Elements</span></span>

|<span data-ttu-id="b2b6d-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="b2b6d-123">Element</span></span>|<span data-ttu-id="b2b6d-124">Описание</span><span class="sxs-lookup"><span data-stu-id="b2b6d-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b2b6d-125">Элемент представления (формат)</span><span class="sxs-lookup"><span data-stu-id="b2b6d-125">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="b2b6d-126">Определяет представление, которое отображает один или несколько объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="b2b6d-126">Defines a view that displays one or more .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b2b6d-127">Замечания</span><span class="sxs-lookup"><span data-stu-id="b2b6d-127">Remarks</span></span>

<span data-ttu-id="b2b6d-128">Дополнительные сведения о том, как этот элемент используется в различных представлениях см. в разделе [компоненты представлений таблицы](./creating-a-table-view.md), [компоненты представлений списка](./creating-a-list-view.md), [расширенные компоненты представлений](./creating-a-wide-view.md)и [Компоненты пользовательского элемента управления](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="b2b6d-128">For more information about how this element is used in different views, see [Table View Components](./creating-a-table-view.md), [List View Components](./creating-a-list-view.md), [Wide View Components](./creating-a-wide-view.md), and [Custom Control Components](./creating-custom-controls.md).</span></span>

<span data-ttu-id="b2b6d-129">`SelectionSetName` Элемент используется в том случае, если файл форматирования определяет набор объектов, которые отображаются по несколько представлений.</span><span class="sxs-lookup"><span data-stu-id="b2b6d-129">The `SelectionSetName` element is used when the formatting file defines a set of objects that are displayed by multiple views.</span></span> <span data-ttu-id="b2b6d-130">Дополнительные сведения о как определенные или используемые наборы выделения, см. в разделе [определение задает объектов](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="b2b6d-130">For more information about how selection sets are defined and referenced, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="b2b6d-131">Пример</span><span class="sxs-lookup"><span data-stu-id="b2b6d-131">Example</span></span>

<span data-ttu-id="b2b6d-132">В следующем примере показано, как указать [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) объект для представления списка.</span><span class="sxs-lookup"><span data-stu-id="b2b6d-132">The following example shows how to specify the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object for a list view.</span></span> <span data-ttu-id="b2b6d-133">Ту же схему используется для таблицы, расширенных и настраиваемых представлений.</span><span class="sxs-lookup"><span data-stu-id="b2b6d-133">The same schema is used for table, wide, and custom views.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a><span data-ttu-id="b2b6d-134">См. также</span><span class="sxs-lookup"><span data-stu-id="b2b6d-134">See Also</span></span>

[<span data-ttu-id="b2b6d-135">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="b2b6d-135">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="b2b6d-136">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="b2b6d-136">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="b2b6d-137">Создание широкое представление</span><span class="sxs-lookup"><span data-stu-id="b2b6d-137">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="b2b6d-138">Создание пользовательских элементов управления</span><span class="sxs-lookup"><span data-stu-id="b2b6d-138">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="b2b6d-139">Определение наборов Выбор</span><span class="sxs-lookup"><span data-stu-id="b2b6d-139">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="b2b6d-140">Элемент SelectionSetName для ViewSelectedBy (формат)</span><span class="sxs-lookup"><span data-stu-id="b2b6d-140">SelectionSetName Element for ViewSelectedBy (Format)</span></span>](./selectionsetname-element-for-viewselectedby-format.md)

[<span data-ttu-id="b2b6d-141">Имя типа элемента (формат)</span><span class="sxs-lookup"><span data-stu-id="b2b6d-141">TypeName Element (Format)</span></span>](./typename-element-for-viewselectedby-format.md)

[<span data-ttu-id="b2b6d-142">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="b2b6d-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
