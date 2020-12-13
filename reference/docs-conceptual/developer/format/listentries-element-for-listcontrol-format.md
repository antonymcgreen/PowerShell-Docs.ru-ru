---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент ListEntries для элемента ListControl (формат)
description: Элемент ListEntries для элемента ListControl (формат)
ms.openlocfilehash: d4d6625bb92ea27863fc30d5bf5625f9275e4f69
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666609"
---
# <a name="listentries-element-for-listcontrol-format"></a><span data-ttu-id="65fbb-103">Элемент ListEntries для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="65fbb-103">ListEntries Element for ListControl (Format)</span></span>

<span data-ttu-id="65fbb-104">Предоставляет определения представления списка.</span><span class="sxs-lookup"><span data-stu-id="65fbb-104">Provides the definitions of the list view.</span></span> <span data-ttu-id="65fbb-105">В представлении списка должно быть указано одно или несколько определений.</span><span class="sxs-lookup"><span data-stu-id="65fbb-105">The list view must specify one or more definitions.</span></span>

<span data-ttu-id="65fbb-106">Элемент конфигурации (Format) Виевдефинитионс элемента представления (Format) элемент (формат) ListControl элемент (Format) Листентриес (формат)</span><span class="sxs-lookup"><span data-stu-id="65fbb-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="65fbb-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="65fbb-107">Syntax</span></span>

```xml
<ListEntries>
  <ListEntry>...</ListEntry>
</ListEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="65fbb-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="65fbb-108">Attributes and Elements</span></span>

<span data-ttu-id="65fbb-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ListEntries` элемента.</span><span class="sxs-lookup"><span data-stu-id="65fbb-109">The following sections describe the attributes, child elements, and the parent element of the `ListEntries` element.</span></span> <span data-ttu-id="65fbb-110">Необходимо указать по крайней мере один дочерний элемент.</span><span class="sxs-lookup"><span data-stu-id="65fbb-110">At least one child element must be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="65fbb-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="65fbb-111">Attributes</span></span>

<span data-ttu-id="65fbb-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="65fbb-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="65fbb-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="65fbb-113">Child Elements</span></span>

|<span data-ttu-id="65fbb-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="65fbb-114">Element</span></span>|<span data-ttu-id="65fbb-115">Описание</span><span class="sxs-lookup"><span data-stu-id="65fbb-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="65fbb-116">Элемент Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="65fbb-116">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)|<span data-ttu-id="65fbb-117">Предоставляет определение представления списка.</span><span class="sxs-lookup"><span data-stu-id="65fbb-117">Provides a definition of the list view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="65fbb-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="65fbb-118">Parent Elements</span></span>

|<span data-ttu-id="65fbb-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="65fbb-119">Element</span></span>|<span data-ttu-id="65fbb-120">Описание</span><span class="sxs-lookup"><span data-stu-id="65fbb-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="65fbb-121">Элемент ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="65fbb-121">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)|<span data-ttu-id="65fbb-122">Определяет формат списка для представления.</span><span class="sxs-lookup"><span data-stu-id="65fbb-122">Defines a list format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="65fbb-123">Комментарии</span><span class="sxs-lookup"><span data-stu-id="65fbb-123">Remarks</span></span>

<span data-ttu-id="65fbb-124">Дополнительные сведения о представлениях списков см. в разделе [представление списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="65fbb-124">For more information about list views, see [List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="65fbb-125">Пример</span><span class="sxs-lookup"><span data-stu-id="65fbb-125">Example</span></span>

<span data-ttu-id="65fbb-126">В этом примере показаны XML-элементы, определяющие представление списка для объекта [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) .</span><span class="sxs-lookup"><span data-stu-id="65fbb-126">This example shows the XML elements that define the list view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>
    <ListEntries>
      <ListEntry>
        <ListItems>...</ListItems>
      </ListEntry>
    </ListEntries>
  </ListControl>
</View>
```

## <a name="see-also"></a><span data-ttu-id="65fbb-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="65fbb-127">See Also</span></span>

[<span data-ttu-id="65fbb-128">Элемент ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="65fbb-128">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)

[<span data-ttu-id="65fbb-129">Элемент Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="65fbb-129">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="65fbb-130">Представление списка</span><span class="sxs-lookup"><span data-stu-id="65fbb-130">List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="65fbb-131">Создание файла форматирования и типов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="65fbb-131">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
