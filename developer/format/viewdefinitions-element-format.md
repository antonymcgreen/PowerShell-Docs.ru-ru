---
title: Элемент ViewDefinitions (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 29840c10-2b30-4bb1-a8a0-ddf84d19c2d0
caps.latest.revision: 18
ms.openlocfilehash: c5ec80350c7707ccd41112ab5e1952e5dc198cca
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083711"
---
# <a name="viewdefinitions-element-format"></a><span data-ttu-id="78bee-102">Элемент ViewDefinitions (формат)</span><span class="sxs-lookup"><span data-stu-id="78bee-102">ViewDefinitions Element (Format)</span></span>

<span data-ttu-id="78bee-103">Определяет представления для отображения объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="78bee-103">Defines the views used to display .NET objects.</span></span> <span data-ttu-id="78bee-104">Эти представления могут отображать свойства и значения объекта скрипта в табличном формате, формате списка, расширенном формате и формате пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="78bee-104">These views can display the properties and script values of an object  in a table format, list format, wide format, and custom control format.</span></span>

<span data-ttu-id="78bee-105">Элемент ViewDefinitions (в формате XML) (формат) элемента конфигурации</span><span class="sxs-lookup"><span data-stu-id="78bee-105">Configuration Element (Format) ViewDefinitions (Format XML) Element</span></span>

## <a name="syntax"></a><span data-ttu-id="78bee-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="78bee-106">Syntax</span></span>

```xml

<ViewDefinitions>
  <View>...</View>
</ViewDefinitions>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="78bee-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="78bee-107">Attributes and Elements</span></span>

<span data-ttu-id="78bee-108">В следующих разделах атрибуты, дочерние элементы и родительский элемент `ViewDefinitions` элемент.</span><span class="sxs-lookup"><span data-stu-id="78bee-108">The following sections describe the attributes, child elements, and parent element of the `ViewDefinitions` element.</span></span> <span data-ttu-id="78bee-109">Нет ограничений на количество представлений, которые могут быть определены в файле форматирования, и могут быть добавлены в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="78bee-109">There is no limit to the number of views that can be defined in a formatting file, and they can be added in any order.</span></span>

### <a name="attributes"></a><span data-ttu-id="78bee-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="78bee-110">Attributes</span></span>

<span data-ttu-id="78bee-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="78bee-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="78bee-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="78bee-112">Child Elements</span></span>

|<span data-ttu-id="78bee-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="78bee-113">Element</span></span>|<span data-ttu-id="78bee-114">Описание</span><span class="sxs-lookup"><span data-stu-id="78bee-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="78bee-115">Элемент представления (формат)</span><span class="sxs-lookup"><span data-stu-id="78bee-115">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="78bee-116">Определяет представление, которое используется для отображения один или несколько объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="78bee-116">Defines a view that is used to display one or more .NET objects.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="78bee-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="78bee-117">Parent Elements</span></span>

|<span data-ttu-id="78bee-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="78bee-118">Element</span></span>|<span data-ttu-id="78bee-119">Описание</span><span class="sxs-lookup"><span data-stu-id="78bee-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="78bee-120">Элемент конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="78bee-120">Configuration Element (Format)</span></span>](./configuration-element-format.md)|<span data-ttu-id="78bee-121">Представляет элемент верхнего уровня файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="78bee-121">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="78bee-122">Замечания</span><span class="sxs-lookup"><span data-stu-id="78bee-122">Remarks</span></span>

<span data-ttu-id="78bee-123">Дополнительные сведения о компонентах различных типов представлений см. в разделах:</span><span class="sxs-lookup"><span data-stu-id="78bee-123">For more information about the components of the different types of views, see the following topics:</span></span>

- [<span data-ttu-id="78bee-124">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="78bee-124">Creating a Table View</span></span>](./creating-a-table-view.md)

- [<span data-ttu-id="78bee-125">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="78bee-125">Creating a List View</span></span>](./creating-a-list-view.md)

- [<span data-ttu-id="78bee-126">Создание широкое представление</span><span class="sxs-lookup"><span data-stu-id="78bee-126">Creating a Wide View</span></span>](./creating-a-wide-view.md)

- [<span data-ttu-id="78bee-127">Пользовательские элементы управления</span><span class="sxs-lookup"><span data-stu-id="78bee-127">Custom Controls</span></span>](./creating-custom-controls.md)

## <a name="example"></a><span data-ttu-id="78bee-128">Пример</span><span class="sxs-lookup"><span data-stu-id="78bee-128">Example</span></span>

<span data-ttu-id="78bee-129">В этом примере показано `ViewDefinitions` элемент, содержащий родительские элементы для представления таблицы и представления списка.</span><span class="sxs-lookup"><span data-stu-id="78bee-129">This example shows a `ViewDefinitions` element that contains the parent elements for a table view and a list view.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="78bee-130">См. также</span><span class="sxs-lookup"><span data-stu-id="78bee-130">See Also</span></span>

[<span data-ttu-id="78bee-131">Элемент конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="78bee-131">Configuration Element (Format)</span></span>](./configuration-element-format.md)

[<span data-ttu-id="78bee-132">Элемент представления (формат)</span><span class="sxs-lookup"><span data-stu-id="78bee-132">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="78bee-133">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="78bee-133">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="78bee-134">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="78bee-134">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="78bee-135">Создание широкое представление</span><span class="sxs-lookup"><span data-stu-id="78bee-135">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="78bee-136">Пользовательские элементы управления</span><span class="sxs-lookup"><span data-stu-id="78bee-136">Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="78bee-137">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="78bee-137">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
