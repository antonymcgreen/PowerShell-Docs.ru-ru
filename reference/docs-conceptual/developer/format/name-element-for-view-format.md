---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент Name для элемента View (формат)
description: Элемент Name для элемента View (формат)
ms.openlocfilehash: 5781bcdf7a0e1eb5e9c7e97bb6acc0a383dc0262
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666469"
---
# <a name="name-element-for-view-format"></a><span data-ttu-id="279ec-103">Элемент Name для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="279ec-103">Name Element for View (Format)</span></span>

<span data-ttu-id="279ec-104">Задает имя, используемое для указания представления.</span><span class="sxs-lookup"><span data-stu-id="279ec-104">Specifies the name that is used to identify the view.</span></span>

<span data-ttu-id="279ec-105">Элемент Configuration (Format) Виевдефинитионс элемент (Format) View элемент (Format) имя элемента (Format)</span><span class="sxs-lookup"><span data-stu-id="279ec-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Name Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="279ec-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="279ec-106">Syntax</span></span>

```xml
<Name>ViewName</Name>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="279ec-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="279ec-107">Attributes and Elements</span></span>

<span data-ttu-id="279ec-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `Name` элемента.</span><span class="sxs-lookup"><span data-stu-id="279ec-108">The following sections describe attributes, child elements, and the parent element of the `Name` element.</span></span> <span data-ttu-id="279ec-109">`Name`Для каждого представления допускается только один элемент.</span><span class="sxs-lookup"><span data-stu-id="279ec-109">Only one `Name` element is allowed for each view.</span></span>

### <a name="attributes"></a><span data-ttu-id="279ec-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="279ec-110">Attributes</span></span>

<span data-ttu-id="279ec-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="279ec-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="279ec-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="279ec-112">Child Elements</span></span>

<span data-ttu-id="279ec-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="279ec-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="279ec-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="279ec-114">Parent Elements</span></span>

|<span data-ttu-id="279ec-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="279ec-115">Element</span></span>|<span data-ttu-id="279ec-116">Описание</span><span class="sxs-lookup"><span data-stu-id="279ec-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="279ec-117">Элемент View (формат)</span><span class="sxs-lookup"><span data-stu-id="279ec-117">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="279ec-118">Определяет представление, используемое для отображения элементов одного или нескольких объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="279ec-118">Defines a view that is used to display the members of one or more .NET objects.</span></span>|

## <a name="text-value"></a><span data-ttu-id="279ec-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="279ec-119">Text Value</span></span>

<span data-ttu-id="279ec-120">Укажите уникальное понятное имя для представления.</span><span class="sxs-lookup"><span data-stu-id="279ec-120">Specify a unique friendly name for the view.</span></span> <span data-ttu-id="279ec-121">Это имя может включать ссылку на тип представления (например, представление таблицы или представление списка), какой объект или набор объектов использует представление, какая команда возвращает объекты или их сочетание.</span><span class="sxs-lookup"><span data-stu-id="279ec-121">This name can include a reference to the type of the view (such as a table view or list view), which object or set of objects use the view, what command returns the objects, or a combination of these.</span></span>

## <a name="remarks"></a><span data-ttu-id="279ec-122">Комментарии</span><span class="sxs-lookup"><span data-stu-id="279ec-122">Remarks</span></span>

<span data-ttu-id="279ec-123">Дополнительные сведения о различных типах представлений см. в следующих разделах: [представление таблицы](./creating-a-table-view.md), [представление списка](./creating-a-list-view.md), [Расширенное представление](./creating-a-wide-view.md)и [пользовательское представление](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="279ec-123">For more information about the different types of views, see the following topics: [Table View](./creating-a-table-view.md), [List View](./creating-a-list-view.md), [Wide View](./creating-a-wide-view.md), and [Custom View](./creating-custom-controls.md).</span></span>

## <a name="example"></a><span data-ttu-id="279ec-124">Пример</span><span class="sxs-lookup"><span data-stu-id="279ec-124">Example</span></span>

<span data-ttu-id="279ec-125">В следующем примере показан `View` элемент, определяющий представление таблицы для объекта [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) .</span><span class="sxs-lookup"><span data-stu-id="279ec-125">The following example shows a `View` element that defines a table view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span> <span data-ttu-id="279ec-126">Имя представления — "служба".</span><span class="sxs-lookup"><span data-stu-id="279ec-126">The name of the view is "service".</span></span>

```xml
<View>
  <Name>service</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <TableControl>...</TableControl>
</View>

```

## <a name="see-also"></a><span data-ttu-id="279ec-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="279ec-127">See Also</span></span>

[<span data-ttu-id="279ec-128">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="279ec-128">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="279ec-129">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="279ec-129">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="279ec-130">Создание широкого представления</span><span class="sxs-lookup"><span data-stu-id="279ec-130">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="279ec-131">Создание пользовательских элементов управления</span><span class="sxs-lookup"><span data-stu-id="279ec-131">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="279ec-132">Элемент View (формат)</span><span class="sxs-lookup"><span data-stu-id="279ec-132">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="279ec-133">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="279ec-133">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
