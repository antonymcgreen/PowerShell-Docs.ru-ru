---
title: Элемент Name для представления (формат) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 670b089f850fa4b39b7b100ca1e1ce45b05ea72d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773238"
---
# <a name="name-element-for-view-format"></a><span data-ttu-id="4e83c-102">Элемент Name для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="4e83c-102">Name Element for View (Format)</span></span>

<span data-ttu-id="4e83c-103">Задает имя, используемое для указания представления.</span><span class="sxs-lookup"><span data-stu-id="4e83c-103">Specifies the name that is used to identify the view.</span></span>

<span data-ttu-id="4e83c-104">Элемент Configuration (Format) Виевдефинитионс элемент (Format) View элемент (Format) имя элемента (Format)</span><span class="sxs-lookup"><span data-stu-id="4e83c-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Name Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4e83c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4e83c-105">Syntax</span></span>

```xml
<Name>ViewName</Name>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4e83c-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4e83c-106">Attributes and Elements</span></span>

<span data-ttu-id="4e83c-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `Name` элемента.</span><span class="sxs-lookup"><span data-stu-id="4e83c-107">The following sections describe attributes, child elements, and the parent element of the `Name` element.</span></span> <span data-ttu-id="4e83c-108">`Name`Для каждого представления допускается только один элемент.</span><span class="sxs-lookup"><span data-stu-id="4e83c-108">Only one `Name` element is allowed for each view.</span></span>

### <a name="attributes"></a><span data-ttu-id="4e83c-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4e83c-109">Attributes</span></span>

<span data-ttu-id="4e83c-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="4e83c-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4e83c-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4e83c-111">Child Elements</span></span>

<span data-ttu-id="4e83c-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="4e83c-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="4e83c-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4e83c-113">Parent Elements</span></span>

|<span data-ttu-id="4e83c-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="4e83c-114">Element</span></span>|<span data-ttu-id="4e83c-115">Описание</span><span class="sxs-lookup"><span data-stu-id="4e83c-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4e83c-116">Элемент View (формат)</span><span class="sxs-lookup"><span data-stu-id="4e83c-116">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="4e83c-117">Определяет представление, используемое для отображения элементов одного или нескольких объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="4e83c-117">Defines a view that is used to display the members of one or more .NET objects.</span></span>|

## <a name="text-value"></a><span data-ttu-id="4e83c-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="4e83c-118">Text Value</span></span>

<span data-ttu-id="4e83c-119">Укажите уникальное понятное имя для представления.</span><span class="sxs-lookup"><span data-stu-id="4e83c-119">Specify a unique friendly name for the view.</span></span> <span data-ttu-id="4e83c-120">Это имя может включать ссылку на тип представления (например, представление таблицы или представление списка), какой объект или набор объектов использует представление, какая команда возвращает объекты или их сочетание.</span><span class="sxs-lookup"><span data-stu-id="4e83c-120">This name can include a reference to the type of the view (such as a table view or list view), which object or set of objects use the view, what command returns the objects, or a combination of these.</span></span>

## <a name="remarks"></a><span data-ttu-id="4e83c-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="4e83c-121">Remarks</span></span>

<span data-ttu-id="4e83c-122">Дополнительные сведения о различных типах представлений см. в следующих разделах: [представление таблицы](./creating-a-table-view.md), [представление списка](./creating-a-list-view.md), [Расширенное представление](./creating-a-wide-view.md)и [пользовательское представление](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="4e83c-122">For more information about the different types of views, see the following topics: [Table View](./creating-a-table-view.md), [List View](./creating-a-list-view.md), [Wide View](./creating-a-wide-view.md), and [Custom View](./creating-custom-controls.md).</span></span>

## <a name="example"></a><span data-ttu-id="4e83c-123">Пример</span><span class="sxs-lookup"><span data-stu-id="4e83c-123">Example</span></span>

<span data-ttu-id="4e83c-124">В следующем примере показан `View` элемент, определяющий представление таблицы для объекта [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) .</span><span class="sxs-lookup"><span data-stu-id="4e83c-124">The following example shows a `View` element that defines a table view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span> <span data-ttu-id="4e83c-125">Имя представления — "служба".</span><span class="sxs-lookup"><span data-stu-id="4e83c-125">The name of the view is "service".</span></span>

```xml
<View>
  <Name>service</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <TableControl>...</TableControl>
</View>

```

## <a name="see-also"></a><span data-ttu-id="4e83c-126">См. также</span><span class="sxs-lookup"><span data-stu-id="4e83c-126">See Also</span></span>

[<span data-ttu-id="4e83c-127">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="4e83c-127">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="4e83c-128">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="4e83c-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="4e83c-129">Создание широкого представления</span><span class="sxs-lookup"><span data-stu-id="4e83c-129">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="4e83c-130">Создание пользовательских элементов управления</span><span class="sxs-lookup"><span data-stu-id="4e83c-130">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="4e83c-131">Элемент View (формат)</span><span class="sxs-lookup"><span data-stu-id="4e83c-131">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="4e83c-132">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="4e83c-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
