---
title: Элемент Виевдефинитионс (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 29840c10-2b30-4bb1-a8a0-ddf84d19c2d0
caps.latest.revision: 18
ms.openlocfilehash: c5ec80350c7707ccd41112ab5e1952e5dc198cca
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361423"
---
# <a name="viewdefinitions-element-format"></a><span data-ttu-id="5a734-102">Элемент ViewDefinitions (формат)</span><span class="sxs-lookup"><span data-stu-id="5a734-102">ViewDefinitions Element (Format)</span></span>

<span data-ttu-id="5a734-103">Определяет представления, используемые для отображения объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="5a734-103">Defines the views used to display .NET objects.</span></span> <span data-ttu-id="5a734-104">Эти представления могут отображать свойства и значения скриптов объекта в формате таблицы, формате списка, расширенном формате и пользовательском формате элемента управления.</span><span class="sxs-lookup"><span data-stu-id="5a734-104">These views can display the properties and script values of an object  in a table format, list format, wide format, and custom control format.</span></span>

<span data-ttu-id="5a734-105">Элемент конфигурации (Format) Виевдефинитионс (формат XML)</span><span class="sxs-lookup"><span data-stu-id="5a734-105">Configuration Element (Format) ViewDefinitions (Format XML) Element</span></span>

## <a name="syntax"></a><span data-ttu-id="5a734-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5a734-106">Syntax</span></span>

```xml

<ViewDefinitions>
  <View>...</View>
</ViewDefinitions>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5a734-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5a734-107">Attributes and Elements</span></span>

<span data-ttu-id="5a734-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `ViewDefinitions`.</span><span class="sxs-lookup"><span data-stu-id="5a734-108">The following sections describe the attributes, child elements, and parent element of the `ViewDefinitions` element.</span></span> <span data-ttu-id="5a734-109">Количество представлений, которые могут быть определены в файле форматирования, не ограничено, и их можно добавлять в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="5a734-109">There is no limit to the number of views that can be defined in a formatting file, and they can be added in any order.</span></span>

### <a name="attributes"></a><span data-ttu-id="5a734-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5a734-110">Attributes</span></span>

<span data-ttu-id="5a734-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="5a734-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5a734-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5a734-112">Child Elements</span></span>

|<span data-ttu-id="5a734-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="5a734-113">Element</span></span>|<span data-ttu-id="5a734-114">Описание</span><span class="sxs-lookup"><span data-stu-id="5a734-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5a734-115">View, элемент (Format)</span><span class="sxs-lookup"><span data-stu-id="5a734-115">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="5a734-116">Определяет представление, используемое для отображения одного или нескольких объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="5a734-116">Defines a view that is used to display one or more .NET objects.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="5a734-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5a734-117">Parent Elements</span></span>

|<span data-ttu-id="5a734-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="5a734-118">Element</span></span>|<span data-ttu-id="5a734-119">Описание</span><span class="sxs-lookup"><span data-stu-id="5a734-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5a734-120">Элемент Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="5a734-120">Configuration Element (Format)</span></span>](./configuration-element-format.md)|<span data-ttu-id="5a734-121">Представляет элемент верхнего уровня файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="5a734-121">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="5a734-122">Замечания</span><span class="sxs-lookup"><span data-stu-id="5a734-122">Remarks</span></span>

<span data-ttu-id="5a734-123">Дополнительные сведения о компонентах различных типов представлений см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="5a734-123">For more information about the components of the different types of views, see the following topics:</span></span>

- [<span data-ttu-id="5a734-124">Создание табличного представления</span><span class="sxs-lookup"><span data-stu-id="5a734-124">Creating a Table View</span></span>](./creating-a-table-view.md)

- [<span data-ttu-id="5a734-125">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="5a734-125">Creating a List View</span></span>](./creating-a-list-view.md)

- [<span data-ttu-id="5a734-126">Создание расширенного представления</span><span class="sxs-lookup"><span data-stu-id="5a734-126">Creating a Wide View</span></span>](./creating-a-wide-view.md)

- [<span data-ttu-id="5a734-127">Пользовательские элементы управления</span><span class="sxs-lookup"><span data-stu-id="5a734-127">Custom Controls</span></span>](./creating-custom-controls.md)

## <a name="example"></a><span data-ttu-id="5a734-128">Пример</span><span class="sxs-lookup"><span data-stu-id="5a734-128">Example</span></span>

<span data-ttu-id="5a734-129">В этом примере показан элемент `ViewDefinitions`, содержащий родительские элементы для табличного представления и представления списка.</span><span class="sxs-lookup"><span data-stu-id="5a734-129">This example shows a `ViewDefinitions` element that contains the parent elements for a table view and a list view.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="5a734-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="5a734-130">See Also</span></span>

[<span data-ttu-id="5a734-131">Элемент Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="5a734-131">Configuration Element (Format)</span></span>](./configuration-element-format.md)

[<span data-ttu-id="5a734-132">View, элемент (Format)</span><span class="sxs-lookup"><span data-stu-id="5a734-132">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="5a734-133">Создание табличного представления</span><span class="sxs-lookup"><span data-stu-id="5a734-133">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="5a734-134">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="5a734-134">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="5a734-135">Создание расширенного представления</span><span class="sxs-lookup"><span data-stu-id="5a734-135">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="5a734-136">Пользовательские элементы управления</span><span class="sxs-lookup"><span data-stu-id="5a734-136">Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="5a734-137">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="5a734-137">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
