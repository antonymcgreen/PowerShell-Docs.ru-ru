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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065076"
---
# <a name="name-element-for-view-format"></a><span data-ttu-id="4790e-102">Элемент Name для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="4790e-102">Name Element for View (Format)</span></span>

<span data-ttu-id="4790e-103">Указывает имя, которое используется для идентификации представления.</span><span class="sxs-lookup"><span data-stu-id="4790e-103">Specifies the name that is used to identify the view.</span></span>

<span data-ttu-id="4790e-104">Имя элемента (формат) элемента (формат) для конфигурации элемента (формат) элемент ViewDefinitions (формат) представления</span><span class="sxs-lookup"><span data-stu-id="4790e-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Name Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4790e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4790e-105">Syntax</span></span>

```xml
<Name>ViewName</Name>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4790e-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4790e-106">Attributes and Elements</span></span>

<span data-ttu-id="4790e-107">Ниже описаны атрибуты, дочерние элементы и родительский элемент `Name` элемент.</span><span class="sxs-lookup"><span data-stu-id="4790e-107">The following sections describe attributes, child elements, and the parent element of the `Name` element.</span></span> <span data-ttu-id="4790e-108">Только один `Name` элемент допускается для каждого представления.</span><span class="sxs-lookup"><span data-stu-id="4790e-108">Only one `Name` element is allowed for each view.</span></span>

### <a name="attributes"></a><span data-ttu-id="4790e-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4790e-109">Attributes</span></span>

<span data-ttu-id="4790e-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="4790e-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4790e-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4790e-111">Child Elements</span></span>

<span data-ttu-id="4790e-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="4790e-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="4790e-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4790e-113">Parent Elements</span></span>

|<span data-ttu-id="4790e-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="4790e-114">Element</span></span>|<span data-ttu-id="4790e-115">Описание</span><span class="sxs-lookup"><span data-stu-id="4790e-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4790e-116">Элемент представления (формат)</span><span class="sxs-lookup"><span data-stu-id="4790e-116">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="4790e-117">Определяет представление, которое используется для отображения элементов из одного или нескольких объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="4790e-117">Defines a view that is used to display the members of one or more .NET objects.</span></span>|

## <a name="text-value"></a><span data-ttu-id="4790e-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="4790e-118">Text Value</span></span>

<span data-ttu-id="4790e-119">Укажите уникальное понятное имя для представления.</span><span class="sxs-lookup"><span data-stu-id="4790e-119">Specify a unique friendly name for the view.</span></span> <span data-ttu-id="4790e-120">Это имя может содержать ссылку на тип представления (например, таблица или представление списка), объект или набор объектов, который следует использовать представление, какая команда возвращает объекты или их сочетание.</span><span class="sxs-lookup"><span data-stu-id="4790e-120">This name can include a reference to the type of the view (such as a table view or list view), which object or set of objects use the view, what command returns the objects, or a combination of these.</span></span>

## <a name="remarks"></a><span data-ttu-id="4790e-121">Замечания</span><span class="sxs-lookup"><span data-stu-id="4790e-121">Remarks</span></span>

<span data-ttu-id="4790e-122">Дополнительные сведения о различных типах представлений см. в разделах: [Табличное представление](./creating-a-table-view.md), [представление списка](./creating-a-list-view.md), [широкое представление](./creating-a-wide-view.md), и [пользовательское представление](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="4790e-122">For more information about the different types of views, see the following topics: [Table View](./creating-a-table-view.md), [List View](./creating-a-list-view.md), [Wide View](./creating-a-wide-view.md), and [Custom View](./creating-custom-controls.md).</span></span>

## <a name="example"></a><span data-ttu-id="4790e-123">Пример</span><span class="sxs-lookup"><span data-stu-id="4790e-123">Example</span></span>

<span data-ttu-id="4790e-124">В следующем примере показан `View` элемент, который определяет представление таблицы для [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) объекта.</span><span class="sxs-lookup"><span data-stu-id="4790e-124">The following example shows a `View` element that defines a table view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span> <span data-ttu-id="4790e-125">Представление называется «служба».</span><span class="sxs-lookup"><span data-stu-id="4790e-125">The name of the view is "service".</span></span>

```xml
<View>
  <Name>service</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <TableControl>...</TableControl>
</View>

```

## <a name="see-also"></a><span data-ttu-id="4790e-126">См. также</span><span class="sxs-lookup"><span data-stu-id="4790e-126">See Also</span></span>

[<span data-ttu-id="4790e-127">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="4790e-127">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="4790e-128">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="4790e-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="4790e-129">Создание широкое представление</span><span class="sxs-lookup"><span data-stu-id="4790e-129">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="4790e-130">Создание пользовательских элементов управления</span><span class="sxs-lookup"><span data-stu-id="4790e-130">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="4790e-131">Элемент представления (формат)</span><span class="sxs-lookup"><span data-stu-id="4790e-131">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="4790e-132">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="4790e-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
