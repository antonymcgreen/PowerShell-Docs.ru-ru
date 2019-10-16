---
title: Элемент Name для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3a31010d-1db9-44ae-a7f3-6ed32cb641cb
caps.latest.revision: 16
ms.openlocfilehash: 097d20cb6a04635124d1f96823248df6095ca1af
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362643"
---
# <a name="name-element-for-view-format"></a><span data-ttu-id="9d3c3-102">Элемент Name для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="9d3c3-102">Name Element for View (Format)</span></span>

<span data-ttu-id="9d3c3-103">Задает имя, используемое для указания представления.</span><span class="sxs-lookup"><span data-stu-id="9d3c3-103">Specifies the name that is used to identify the view.</span></span>

<span data-ttu-id="9d3c3-104">Элемент Configuration (Format) Виевдефинитионс элемент (Format) View элемент (Format) имя элемента (Format)</span><span class="sxs-lookup"><span data-stu-id="9d3c3-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Name Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9d3c3-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9d3c3-105">Syntax</span></span>

```xml
<Name>ViewName</Name>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9d3c3-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9d3c3-106">Attributes and Elements</span></span>

<span data-ttu-id="9d3c3-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `Name`.</span><span class="sxs-lookup"><span data-stu-id="9d3c3-107">The following sections describe attributes, child elements, and the parent element of the `Name` element.</span></span> <span data-ttu-id="9d3c3-108">Для каждого представления допускается только один элемент `Name`.</span><span class="sxs-lookup"><span data-stu-id="9d3c3-108">Only one `Name` element is allowed for each view.</span></span>

### <a name="attributes"></a><span data-ttu-id="9d3c3-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9d3c3-109">Attributes</span></span>

<span data-ttu-id="9d3c3-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="9d3c3-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9d3c3-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9d3c3-111">Child Elements</span></span>

<span data-ttu-id="9d3c3-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="9d3c3-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="9d3c3-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9d3c3-113">Parent Elements</span></span>

|<span data-ttu-id="9d3c3-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="9d3c3-114">Element</span></span>|<span data-ttu-id="9d3c3-115">Описание</span><span class="sxs-lookup"><span data-stu-id="9d3c3-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9d3c3-116">View, элемент (Format)</span><span class="sxs-lookup"><span data-stu-id="9d3c3-116">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="9d3c3-117">Определяет представление, используемое для отображения элементов одного или нескольких объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="9d3c3-117">Defines a view that is used to display the members of one or more .NET objects.</span></span>|

## <a name="text-value"></a><span data-ttu-id="9d3c3-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="9d3c3-118">Text Value</span></span>

<span data-ttu-id="9d3c3-119">Укажите уникальное понятное имя для представления.</span><span class="sxs-lookup"><span data-stu-id="9d3c3-119">Specify a unique friendly name for the view.</span></span> <span data-ttu-id="9d3c3-120">Это имя может включать ссылку на тип представления (например, представление таблицы или представление списка), какой объект или набор объектов использует представление, какая команда возвращает объекты или их сочетание.</span><span class="sxs-lookup"><span data-stu-id="9d3c3-120">This name can include a reference to the type of the view (such as a table view or list view), which object or set of objects use the view, what command returns the objects, or a combination of these.</span></span>

## <a name="remarks"></a><span data-ttu-id="9d3c3-121">Замечания</span><span class="sxs-lookup"><span data-stu-id="9d3c3-121">Remarks</span></span>

<span data-ttu-id="9d3c3-122">Дополнительные сведения о различных типах представлений см. в следующих разделах: [представление таблицы](./creating-a-table-view.md), [представление списка](./creating-a-list-view.md), [Расширенное представление](./creating-a-wide-view.md)и [пользовательское представление](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="9d3c3-122">For more information about the different types of views, see the following topics: [Table View](./creating-a-table-view.md), [List View](./creating-a-list-view.md), [Wide View](./creating-a-wide-view.md), and [Custom View](./creating-custom-controls.md).</span></span>

## <a name="example"></a><span data-ttu-id="9d3c3-123">Пример</span><span class="sxs-lookup"><span data-stu-id="9d3c3-123">Example</span></span>

<span data-ttu-id="9d3c3-124">В следующем примере показан элемент `View`, определяющий представление таблицы для объекта [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) .</span><span class="sxs-lookup"><span data-stu-id="9d3c3-124">The following example shows a `View` element that defines a table view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span> <span data-ttu-id="9d3c3-125">Имя представления — "служба".</span><span class="sxs-lookup"><span data-stu-id="9d3c3-125">The name of the view is "service".</span></span>

```xml
<View>
  <Name>service</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <TableControl>...</TableControl>
</View>

```

## <a name="see-also"></a><span data-ttu-id="9d3c3-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="9d3c3-126">See Also</span></span>

[<span data-ttu-id="9d3c3-127">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="9d3c3-127">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="9d3c3-128">Создание табличного представления</span><span class="sxs-lookup"><span data-stu-id="9d3c3-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="9d3c3-129">Создание расширенного представления</span><span class="sxs-lookup"><span data-stu-id="9d3c3-129">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="9d3c3-130">Создание пользовательских элементов управления</span><span class="sxs-lookup"><span data-stu-id="9d3c3-130">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="9d3c3-131">View, элемент (Format)</span><span class="sxs-lookup"><span data-stu-id="9d3c3-131">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="9d3c3-132">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="9d3c3-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
