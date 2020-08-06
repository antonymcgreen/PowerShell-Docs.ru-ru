---
title: Элемент Виевдефинитионс (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: a108c4f8b03e3dec3905181b390aee2c82ab0028
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772490"
---
# <a name="viewdefinitions-element-format"></a><span data-ttu-id="2145f-102">Элемент ViewDefinitions (формат)</span><span class="sxs-lookup"><span data-stu-id="2145f-102">ViewDefinitions Element (Format)</span></span>

<span data-ttu-id="2145f-103">Определяет представления, используемые для отображения объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="2145f-103">Defines the views used to display .NET objects.</span></span> <span data-ttu-id="2145f-104">Эти представления могут отображать свойства и значения скриптов объекта в формате таблицы, формате списка, расширенном формате и пользовательском формате элемента управления.</span><span class="sxs-lookup"><span data-stu-id="2145f-104">These views can display the properties and script values of an object  in a table format, list format, wide format, and custom control format.</span></span>

<span data-ttu-id="2145f-105">Элемент конфигурации (Format) Виевдефинитионс (формат XML)</span><span class="sxs-lookup"><span data-stu-id="2145f-105">Configuration Element (Format) ViewDefinitions (Format XML) Element</span></span>

## <a name="syntax"></a><span data-ttu-id="2145f-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2145f-106">Syntax</span></span>

```xml

<ViewDefinitions>
  <View>...</View>
</ViewDefinitions>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2145f-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2145f-107">Attributes and Elements</span></span>

<span data-ttu-id="2145f-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ViewDefinitions` элемента.</span><span class="sxs-lookup"><span data-stu-id="2145f-108">The following sections describe the attributes, child elements, and parent element of the `ViewDefinitions` element.</span></span> <span data-ttu-id="2145f-109">Количество представлений, которые могут быть определены в файле форматирования, не ограничено, и их можно добавлять в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="2145f-109">There is no limit to the number of views that can be defined in a formatting file, and they can be added in any order.</span></span>

### <a name="attributes"></a><span data-ttu-id="2145f-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2145f-110">Attributes</span></span>

<span data-ttu-id="2145f-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="2145f-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2145f-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2145f-112">Child Elements</span></span>

|<span data-ttu-id="2145f-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="2145f-113">Element</span></span>|<span data-ttu-id="2145f-114">Описание</span><span class="sxs-lookup"><span data-stu-id="2145f-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2145f-115">Элемент View (формат)</span><span class="sxs-lookup"><span data-stu-id="2145f-115">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="2145f-116">Определяет представление, используемое для отображения одного или нескольких объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="2145f-116">Defines a view that is used to display one or more .NET objects.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="2145f-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2145f-117">Parent Elements</span></span>

|<span data-ttu-id="2145f-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="2145f-118">Element</span></span>|<span data-ttu-id="2145f-119">Описание</span><span class="sxs-lookup"><span data-stu-id="2145f-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2145f-120">Элемент Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="2145f-120">Configuration Element (Format)</span></span>](./configuration-element-format.md)|<span data-ttu-id="2145f-121">Представляет элемент верхнего уровня файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="2145f-121">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="2145f-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="2145f-122">Remarks</span></span>

<span data-ttu-id="2145f-123">Дополнительные сведения о компонентах различных типов представлений см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="2145f-123">For more information about the components of the different types of views, see the following topics:</span></span>

- [<span data-ttu-id="2145f-124">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="2145f-124">Creating a Table View</span></span>](./creating-a-table-view.md)

- [<span data-ttu-id="2145f-125">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="2145f-125">Creating a List View</span></span>](./creating-a-list-view.md)

- [<span data-ttu-id="2145f-126">Создание широкого представления</span><span class="sxs-lookup"><span data-stu-id="2145f-126">Creating a Wide View</span></span>](./creating-a-wide-view.md)

- [<span data-ttu-id="2145f-127">Пользовательские элементы управления</span><span class="sxs-lookup"><span data-stu-id="2145f-127">Custom Controls</span></span>](./creating-custom-controls.md)

## <a name="example"></a><span data-ttu-id="2145f-128">Пример</span><span class="sxs-lookup"><span data-stu-id="2145f-128">Example</span></span>

<span data-ttu-id="2145f-129">В этом примере показан `ViewDefinitions` элемент, содержащий родительские элементы для табличного представления и представления списка.</span><span class="sxs-lookup"><span data-stu-id="2145f-129">This example shows a `ViewDefinitions` element that contains the parent elements for a table view and a list view.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="2145f-130">См. также</span><span class="sxs-lookup"><span data-stu-id="2145f-130">See Also</span></span>

[<span data-ttu-id="2145f-131">Элемент Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="2145f-131">Configuration Element (Format)</span></span>](./configuration-element-format.md)

[<span data-ttu-id="2145f-132">Элемент View (формат)</span><span class="sxs-lookup"><span data-stu-id="2145f-132">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="2145f-133">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="2145f-133">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="2145f-134">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="2145f-134">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="2145f-135">Создание широкого представления</span><span class="sxs-lookup"><span data-stu-id="2145f-135">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="2145f-136">Пользовательские элементы управления</span><span class="sxs-lookup"><span data-stu-id="2145f-136">Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="2145f-137">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="2145f-137">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
