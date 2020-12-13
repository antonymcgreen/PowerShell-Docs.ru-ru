---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент ViewDefinitions (формат)
description: Элемент ViewDefinitions (формат)
ms.openlocfilehash: fceef0e5ec91e8c59a7b2b90fd31ca422ff0c94d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664581"
---
# <a name="viewdefinitions-element-format"></a><span data-ttu-id="aa60b-103">Элемент ViewDefinitions (формат)</span><span class="sxs-lookup"><span data-stu-id="aa60b-103">ViewDefinitions Element (Format)</span></span>

<span data-ttu-id="aa60b-104">Определяет представления, используемые для отображения объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="aa60b-104">Defines the views used to display .NET objects.</span></span> <span data-ttu-id="aa60b-105">Эти представления могут отображать свойства и значения скриптов объекта в формате таблицы, формате списка, расширенном формате и пользовательском формате элемента управления.</span><span class="sxs-lookup"><span data-stu-id="aa60b-105">These views can display the properties and script values of an object  in a table format, list format, wide format, and custom control format.</span></span>

<span data-ttu-id="aa60b-106">Элемент конфигурации (Format) Виевдефинитионс (формат XML)</span><span class="sxs-lookup"><span data-stu-id="aa60b-106">Configuration Element (Format) ViewDefinitions (Format XML) Element</span></span>

## <a name="syntax"></a><span data-ttu-id="aa60b-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aa60b-107">Syntax</span></span>

```xml

<ViewDefinitions>
  <View>...</View>
</ViewDefinitions>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="aa60b-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="aa60b-108">Attributes and Elements</span></span>

<span data-ttu-id="aa60b-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ViewDefinitions` элемента.</span><span class="sxs-lookup"><span data-stu-id="aa60b-109">The following sections describe the attributes, child elements, and parent element of the `ViewDefinitions` element.</span></span> <span data-ttu-id="aa60b-110">Количество представлений, которые могут быть определены в файле форматирования, не ограничено, и их можно добавлять в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="aa60b-110">There is no limit to the number of views that can be defined in a formatting file, and they can be added in any order.</span></span>

### <a name="attributes"></a><span data-ttu-id="aa60b-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="aa60b-111">Attributes</span></span>

<span data-ttu-id="aa60b-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="aa60b-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="aa60b-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="aa60b-113">Child Elements</span></span>

|<span data-ttu-id="aa60b-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="aa60b-114">Element</span></span>|<span data-ttu-id="aa60b-115">Описание</span><span class="sxs-lookup"><span data-stu-id="aa60b-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="aa60b-116">Элемент View (формат)</span><span class="sxs-lookup"><span data-stu-id="aa60b-116">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="aa60b-117">Определяет представление, используемое для отображения одного или нескольких объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="aa60b-117">Defines a view that is used to display one or more .NET objects.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="aa60b-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="aa60b-118">Parent Elements</span></span>

|<span data-ttu-id="aa60b-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="aa60b-119">Element</span></span>|<span data-ttu-id="aa60b-120">Описание</span><span class="sxs-lookup"><span data-stu-id="aa60b-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="aa60b-121">Элемент Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="aa60b-121">Configuration Element (Format)</span></span>](./configuration-element-format.md)|<span data-ttu-id="aa60b-122">Представляет элемент верхнего уровня файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="aa60b-122">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="aa60b-123">Комментарии</span><span class="sxs-lookup"><span data-stu-id="aa60b-123">Remarks</span></span>

<span data-ttu-id="aa60b-124">Дополнительные сведения о компонентах различных типов представлений см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="aa60b-124">For more information about the components of the different types of views, see the following topics:</span></span>

- [<span data-ttu-id="aa60b-125">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="aa60b-125">Creating a Table View</span></span>](./creating-a-table-view.md)

- [<span data-ttu-id="aa60b-126">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="aa60b-126">Creating a List View</span></span>](./creating-a-list-view.md)

- [<span data-ttu-id="aa60b-127">Создание широкого представления</span><span class="sxs-lookup"><span data-stu-id="aa60b-127">Creating a Wide View</span></span>](./creating-a-wide-view.md)

- [<span data-ttu-id="aa60b-128">Пользовательские элементы управления</span><span class="sxs-lookup"><span data-stu-id="aa60b-128">Custom Controls</span></span>](./creating-custom-controls.md)

## <a name="example"></a><span data-ttu-id="aa60b-129">Пример</span><span class="sxs-lookup"><span data-stu-id="aa60b-129">Example</span></span>

<span data-ttu-id="aa60b-130">В этом примере показан `ViewDefinitions` элемент, содержащий родительские элементы для табличного представления и представления списка.</span><span class="sxs-lookup"><span data-stu-id="aa60b-130">This example shows a `ViewDefinitions` element that contains the parent elements for a table view and a list view.</span></span>

```xml
<Configuration>
  <ViewDefinitions>
    <View>
      <TableControl>...</TableControl>
    </View>
    <View>
      <ListControl>...</ListControl>
    </View>
  </ViewDefinitions>
</Configuration>
```

## <a name="see-also"></a><span data-ttu-id="aa60b-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="aa60b-131">See Also</span></span>

[<span data-ttu-id="aa60b-132">Элемент Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="aa60b-132">Configuration Element (Format)</span></span>](./configuration-element-format.md)

[<span data-ttu-id="aa60b-133">Элемент View (формат)</span><span class="sxs-lookup"><span data-stu-id="aa60b-133">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="aa60b-134">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="aa60b-134">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="aa60b-135">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="aa60b-135">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="aa60b-136">Создание широкого представления</span><span class="sxs-lookup"><span data-stu-id="aa60b-136">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="aa60b-137">Пользовательские элементы управления</span><span class="sxs-lookup"><span data-stu-id="aa60b-137">Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="aa60b-138">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="aa60b-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
