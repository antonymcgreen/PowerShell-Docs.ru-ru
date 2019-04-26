---
title: Элемент ListEntries для ListControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b62e81cc-4175-40fa-829f-634245b09f86
caps.latest.revision: 12
ms.openlocfilehash: aaf16702e485135b5299ccb43a2b62db2d9f5762
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065399"
---
# <a name="listentries-element-for-listcontrol-format"></a><span data-ttu-id="9fc45-102">Элемент ListEntries для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="9fc45-102">ListEntries Element for ListControl (Format)</span></span>

<span data-ttu-id="9fc45-103">Предоставляет определения представления "list".</span><span class="sxs-lookup"><span data-stu-id="9fc45-103">Provides the definitions of the list view.</span></span> <span data-ttu-id="9fc45-104">В представлении списка необходимо указать одно или несколько определений.</span><span class="sxs-lookup"><span data-stu-id="9fc45-104">The list view must specify one or more definitions.</span></span>

<span data-ttu-id="9fc45-105">Элемент элемента ListControl (формат) ListEntries ViewDefinitions элемент (формат) представление конфигурации элемента (формат) элемент (формат) (формат)</span><span class="sxs-lookup"><span data-stu-id="9fc45-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9fc45-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9fc45-106">Syntax</span></span>

```xml
<ListEntries>
  <ListEntry>...</ListEntry>
</ListEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9fc45-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9fc45-107">Attributes and Elements</span></span>

<span data-ttu-id="9fc45-108">В следующих разделах атрибуты, дочерние элементы и родительский элемент `ListEntries` элемент.</span><span class="sxs-lookup"><span data-stu-id="9fc45-108">The following sections describe the attributes, child elements, and the parent element of the `ListEntries` element.</span></span> <span data-ttu-id="9fc45-109">Необходимо указать хотя бы один дочерний элемент.</span><span class="sxs-lookup"><span data-stu-id="9fc45-109">At least one child element must be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="9fc45-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9fc45-110">Attributes</span></span>

<span data-ttu-id="9fc45-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="9fc45-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9fc45-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9fc45-112">Child Elements</span></span>

|<span data-ttu-id="9fc45-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="9fc45-113">Element</span></span>|<span data-ttu-id="9fc45-114">Описание</span><span class="sxs-lookup"><span data-stu-id="9fc45-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9fc45-115">Элемент ListEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="9fc45-115">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)|<span data-ttu-id="9fc45-116">Предоставляет определение представления "list".</span><span class="sxs-lookup"><span data-stu-id="9fc45-116">Provides a definition of the list view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="9fc45-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9fc45-117">Parent Elements</span></span>

|<span data-ttu-id="9fc45-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="9fc45-118">Element</span></span>|<span data-ttu-id="9fc45-119">Описание</span><span class="sxs-lookup"><span data-stu-id="9fc45-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9fc45-120">Элемент ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="9fc45-120">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)|<span data-ttu-id="9fc45-121">Определяет формат для представления списка.</span><span class="sxs-lookup"><span data-stu-id="9fc45-121">Defines a list format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="9fc45-122">Замечания</span><span class="sxs-lookup"><span data-stu-id="9fc45-122">Remarks</span></span>

<span data-ttu-id="9fc45-123">Дополнительные сведения о списках см. в разделе [представление списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="9fc45-123">For more information about list views, see [List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="9fc45-124">Пример</span><span class="sxs-lookup"><span data-stu-id="9fc45-124">Example</span></span>

<span data-ttu-id="9fc45-125">В этом примере показаны элементы XML, которые определяют представление списка для [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) объекта.</span><span class="sxs-lookup"><span data-stu-id="9fc45-125">This example shows the XML elements that define the list view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="9fc45-126">См. также</span><span class="sxs-lookup"><span data-stu-id="9fc45-126">See Also</span></span>

[<span data-ttu-id="9fc45-127">Элемент ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="9fc45-127">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)

[<span data-ttu-id="9fc45-128">Элемент ListEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="9fc45-128">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="9fc45-129">Представление списка</span><span class="sxs-lookup"><span data-stu-id="9fc45-129">List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="9fc45-130">Написание форматирования Windows PowerShell и типы файлов</span><span class="sxs-lookup"><span data-stu-id="9fc45-130">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
