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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361423"
---
# <a name="viewdefinitions-element-format"></a><span data-ttu-id="f1602-102">Элемент ViewDefinitions (формат)</span><span class="sxs-lookup"><span data-stu-id="f1602-102">ViewDefinitions Element (Format)</span></span>

<span data-ttu-id="f1602-103">Определяет представления, используемые для отображения объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="f1602-103">Defines the views used to display .NET objects.</span></span> <span data-ttu-id="f1602-104">Эти представления могут отображать свойства и значения скриптов объекта в формате таблицы, формате списка, расширенном формате и пользовательском формате элемента управления.</span><span class="sxs-lookup"><span data-stu-id="f1602-104">These views can display the properties and script values of an object  in a table format, list format, wide format, and custom control format.</span></span>

<span data-ttu-id="f1602-105">Элемент конфигурации (Format) Виевдефинитионс (формат XML)</span><span class="sxs-lookup"><span data-stu-id="f1602-105">Configuration Element (Format) ViewDefinitions (Format XML) Element</span></span>

## <a name="syntax"></a><span data-ttu-id="f1602-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f1602-106">Syntax</span></span>

```xml

<ViewDefinitions>
  <View>...</View>
</ViewDefinitions>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f1602-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f1602-107">Attributes and Elements</span></span>

<span data-ttu-id="f1602-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `ViewDefinitions`.</span><span class="sxs-lookup"><span data-stu-id="f1602-108">The following sections describe the attributes, child elements, and parent element of the `ViewDefinitions` element.</span></span> <span data-ttu-id="f1602-109">Количество представлений, которые могут быть определены в файле форматирования, не ограничено, и их можно добавлять в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="f1602-109">There is no limit to the number of views that can be defined in a formatting file, and they can be added in any order.</span></span>

### <a name="attributes"></a><span data-ttu-id="f1602-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f1602-110">Attributes</span></span>

<span data-ttu-id="f1602-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="f1602-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f1602-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f1602-112">Child Elements</span></span>

|<span data-ttu-id="f1602-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="f1602-113">Element</span></span>|<span data-ttu-id="f1602-114">Описание</span><span class="sxs-lookup"><span data-stu-id="f1602-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f1602-115">View, элемент (Format)</span><span class="sxs-lookup"><span data-stu-id="f1602-115">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="f1602-116">Определяет представление, используемое для отображения одного или нескольких объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="f1602-116">Defines a view that is used to display one or more .NET objects.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="f1602-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f1602-117">Parent Elements</span></span>

|<span data-ttu-id="f1602-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="f1602-118">Element</span></span>|<span data-ttu-id="f1602-119">Описание</span><span class="sxs-lookup"><span data-stu-id="f1602-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f1602-120">Элемент Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="f1602-120">Configuration Element (Format)</span></span>](./configuration-element-format.md)|<span data-ttu-id="f1602-121">Представляет элемент верхнего уровня файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="f1602-121">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f1602-122">Замечания</span><span class="sxs-lookup"><span data-stu-id="f1602-122">Remarks</span></span>

<span data-ttu-id="f1602-123">Дополнительные сведения о компонентах различных типов представлений см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="f1602-123">For more information about the components of the different types of views, see the following topics:</span></span>

- [<span data-ttu-id="f1602-124">Создание табличного представления</span><span class="sxs-lookup"><span data-stu-id="f1602-124">Creating a Table View</span></span>](./creating-a-table-view.md)

- [<span data-ttu-id="f1602-125">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="f1602-125">Creating a List View</span></span>](./creating-a-list-view.md)

- [<span data-ttu-id="f1602-126">Создание расширенного представления</span><span class="sxs-lookup"><span data-stu-id="f1602-126">Creating a Wide View</span></span>](./creating-a-wide-view.md)

- [<span data-ttu-id="f1602-127">Пользовательские элементы управления</span><span class="sxs-lookup"><span data-stu-id="f1602-127">Custom Controls</span></span>](./creating-custom-controls.md)

## <a name="example"></a><span data-ttu-id="f1602-128">Пример</span><span class="sxs-lookup"><span data-stu-id="f1602-128">Example</span></span>

<span data-ttu-id="f1602-129">В этом примере показан элемент `ViewDefinitions`, содержащий родительские элементы для табличного представления и представления списка.</span><span class="sxs-lookup"><span data-stu-id="f1602-129">This example shows a `ViewDefinitions` element that contains the parent elements for a table view and a list view.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="f1602-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="f1602-130">See Also</span></span>

[<span data-ttu-id="f1602-131">Элемент Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="f1602-131">Configuration Element (Format)</span></span>](./configuration-element-format.md)

[<span data-ttu-id="f1602-132">View, элемент (Format)</span><span class="sxs-lookup"><span data-stu-id="f1602-132">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="f1602-133">Создание табличного представления</span><span class="sxs-lookup"><span data-stu-id="f1602-133">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="f1602-134">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="f1602-134">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="f1602-135">Создание расширенного представления</span><span class="sxs-lookup"><span data-stu-id="f1602-135">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="f1602-136">Пользовательские элементы управления</span><span class="sxs-lookup"><span data-stu-id="f1602-136">Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="f1602-137">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="f1602-137">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
