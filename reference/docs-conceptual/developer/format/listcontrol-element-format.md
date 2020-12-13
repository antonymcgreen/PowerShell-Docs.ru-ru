---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент ListControl (формат)
description: Элемент ListControl (формат)
ms.openlocfilehash: cd5687ac8e94e2245d1ae2de8b2206185e5b8ca4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666592"
---
# <a name="listcontrol-element-format"></a><span data-ttu-id="68f68-103">Элемент ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="68f68-103">ListControl Element (Format)</span></span>

<span data-ttu-id="68f68-104">Определяет формат списка для представления.</span><span class="sxs-lookup"><span data-stu-id="68f68-104">Defines a list format for the view.</span></span>

<span data-ttu-id="68f68-105">Элемент конфигурации (Format) Виевдефинитионс элемента представления (Format) элемент (формат) ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="68f68-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="68f68-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="68f68-106">Syntax</span></span>

```xml
<ListControl>
  <ListEntries>...</ListEntries>
</ListControl>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="68f68-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="68f68-107">Attributes and Elements</span></span>

<span data-ttu-id="68f68-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ListControl` элемента.</span><span class="sxs-lookup"><span data-stu-id="68f68-108">The following sections describe the attributes, child elements, and the parent element of the `ListControl` element.</span></span> <span data-ttu-id="68f68-109">Этот элемент должен содержать только один дочерний элемент.</span><span class="sxs-lookup"><span data-stu-id="68f68-109">This element must contain only a single child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="68f68-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="68f68-110">Attributes</span></span>

<span data-ttu-id="68f68-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="68f68-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="68f68-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="68f68-112">Child Elements</span></span>

|<span data-ttu-id="68f68-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="68f68-113">Element</span></span>|<span data-ttu-id="68f68-114">Описание</span><span class="sxs-lookup"><span data-stu-id="68f68-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="68f68-115">Элемент Листентриес (Format)</span><span class="sxs-lookup"><span data-stu-id="68f68-115">ListEntries Element (Format)</span></span>](./listentries-element-for-listcontrol-format.md)|<span data-ttu-id="68f68-116">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="68f68-116">Required element.</span></span><br /><br /> <span data-ttu-id="68f68-117">Предоставляет определения представления списка.</span><span class="sxs-lookup"><span data-stu-id="68f68-117">Provides the definitions of the list view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="68f68-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="68f68-118">Parent Elements</span></span>

|<span data-ttu-id="68f68-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="68f68-119">Element</span></span>|<span data-ttu-id="68f68-120">Описание</span><span class="sxs-lookup"><span data-stu-id="68f68-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="68f68-121">Элемент View (формат)</span><span class="sxs-lookup"><span data-stu-id="68f68-121">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="68f68-122">Определяет представление, используемое для отображения элементов одного или нескольких объектов.</span><span class="sxs-lookup"><span data-stu-id="68f68-122">Defines a view that is used to display the members of one or more objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="68f68-123">Комментарии</span><span class="sxs-lookup"><span data-stu-id="68f68-123">Remarks</span></span>

<span data-ttu-id="68f68-124">Дополнительные сведения о создании представления списка см. в разделе [Создание представления списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="68f68-124">For more information about creating a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="68f68-125">Пример</span><span class="sxs-lookup"><span data-stu-id="68f68-125">Example</span></span>

<span data-ttu-id="68f68-126">В этом примере показано представление списка для объекта [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) .</span><span class="sxs-lookup"><span data-stu-id="68f68-126">This example shows a list view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

```
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>
    <ListEntries>
      <ListEntry>...</ListEntry>
    </ListEntries>
  </ListControl>
</View>
```

## <a name="see-also"></a><span data-ttu-id="68f68-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="68f68-127">See Also</span></span>

[<span data-ttu-id="68f68-128">Элемент View (формат)</span><span class="sxs-lookup"><span data-stu-id="68f68-128">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="68f68-129">Элемент Листентриес (Format)</span><span class="sxs-lookup"><span data-stu-id="68f68-129">ListEntries Element (Format)</span></span>](./listentries-element-for-listcontrol-format.md)

[<span data-ttu-id="68f68-130">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="68f68-130">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="68f68-131">Создание файла форматирования и типов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="68f68-131">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
