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
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856790"
---
# <a name="listentries-element-for-listcontrol-format"></a><span data-ttu-id="fe633-102">Элемент ListEntries для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="fe633-102">ListEntries Element for ListControl (Format)</span></span>

<span data-ttu-id="fe633-103">Предоставляет определения представления "list".</span><span class="sxs-lookup"><span data-stu-id="fe633-103">Provides the definitions of the list view.</span></span> <span data-ttu-id="fe633-104">В представлении списка необходимо указать одно или несколько определений.</span><span class="sxs-lookup"><span data-stu-id="fe633-104">The list view must specify one or more definitions.</span></span>

<span data-ttu-id="fe633-105">Элемент элемента ListControl (формат) ListEntries ViewDefinitions элемент (формат) представление конфигурации элемента (формат) элемент (формат) (формат)</span><span class="sxs-lookup"><span data-stu-id="fe633-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="fe633-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fe633-106">Syntax</span></span>

```xml
<ListEntries>
  <ListEntry>...</ListEntry>
</ListEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="fe633-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="fe633-107">Attributes and Elements</span></span>

<span data-ttu-id="fe633-108">В следующих разделах атрибуты, дочерние элементы и родительский элемент `ListEntries` элемент.</span><span class="sxs-lookup"><span data-stu-id="fe633-108">The following sections describe the attributes, child elements, and the parent element of the `ListEntries` element.</span></span> <span data-ttu-id="fe633-109">Необходимо указать хотя бы один дочерний элемент.</span><span class="sxs-lookup"><span data-stu-id="fe633-109">At least one child element must be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="fe633-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="fe633-110">Attributes</span></span>

<span data-ttu-id="fe633-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="fe633-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="fe633-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="fe633-112">Child Elements</span></span>

|<span data-ttu-id="fe633-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="fe633-113">Element</span></span>|<span data-ttu-id="fe633-114">Описание</span><span class="sxs-lookup"><span data-stu-id="fe633-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="fe633-115">Элемент ListEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="fe633-115">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)|<span data-ttu-id="fe633-116">Предоставляет определение представления "list".</span><span class="sxs-lookup"><span data-stu-id="fe633-116">Provides a definition of the list view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="fe633-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="fe633-117">Parent Elements</span></span>

|<span data-ttu-id="fe633-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="fe633-118">Element</span></span>|<span data-ttu-id="fe633-119">Описание</span><span class="sxs-lookup"><span data-stu-id="fe633-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="fe633-120">Элемент ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="fe633-120">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)|<span data-ttu-id="fe633-121">Определяет формат для представления списка.</span><span class="sxs-lookup"><span data-stu-id="fe633-121">Defines a list format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="fe633-122">Замечания</span><span class="sxs-lookup"><span data-stu-id="fe633-122">Remarks</span></span>

<span data-ttu-id="fe633-123">Дополнительные сведения о списках см. в разделе [представление списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="fe633-123">For more information about list views, see [List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="fe633-124">Пример</span><span class="sxs-lookup"><span data-stu-id="fe633-124">Example</span></span>

<span data-ttu-id="fe633-125">В этом примере показаны элементы XML, которые определяют представление списка для [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) объекта.</span><span class="sxs-lookup"><span data-stu-id="fe633-125">This example shows the XML elements that define the list view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="fe633-126">См. также</span><span class="sxs-lookup"><span data-stu-id="fe633-126">See Also</span></span>

[<span data-ttu-id="fe633-127">Элемент ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="fe633-127">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)

[<span data-ttu-id="fe633-128">Элемент ListEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="fe633-128">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="fe633-129">Представление списка</span><span class="sxs-lookup"><span data-stu-id="fe633-129">List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="fe633-130">Написание форматирования Windows PowerShell и типы файлов</span><span class="sxs-lookup"><span data-stu-id="fe633-130">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
