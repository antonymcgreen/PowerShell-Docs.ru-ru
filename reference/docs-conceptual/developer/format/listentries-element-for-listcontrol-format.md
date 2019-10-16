---
title: Элемент Листентриес для ListControl (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b62e81cc-4175-40fa-829f-634245b09f86
caps.latest.revision: 12
ms.openlocfilehash: aaf16702e485135b5299ccb43a2b62db2d9f5762
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362763"
---
# <a name="listentries-element-for-listcontrol-format"></a><span data-ttu-id="4f4c7-102">Элемент ListEntries для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="4f4c7-102">ListEntries Element for ListControl (Format)</span></span>

<span data-ttu-id="4f4c7-103">Предоставляет определения представления списка.</span><span class="sxs-lookup"><span data-stu-id="4f4c7-103">Provides the definitions of the list view.</span></span> <span data-ttu-id="4f4c7-104">В представлении списка должно быть указано одно или несколько определений.</span><span class="sxs-lookup"><span data-stu-id="4f4c7-104">The list view must specify one or more definitions.</span></span>

<span data-ttu-id="4f4c7-105">Элемент конфигурации (Format) Виевдефинитионс элемента представления (Format) элемент (формат) ListControl элемент (Format) Листентриес (формат)</span><span class="sxs-lookup"><span data-stu-id="4f4c7-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4f4c7-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4f4c7-106">Syntax</span></span>

```xml
<ListEntries>
  <ListEntry>...</ListEntry>
</ListEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4f4c7-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4f4c7-107">Attributes and Elements</span></span>

<span data-ttu-id="4f4c7-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `ListEntries`.</span><span class="sxs-lookup"><span data-stu-id="4f4c7-108">The following sections describe the attributes, child elements, and the parent element of the `ListEntries` element.</span></span> <span data-ttu-id="4f4c7-109">Необходимо указать по крайней мере один дочерний элемент.</span><span class="sxs-lookup"><span data-stu-id="4f4c7-109">At least one child element must be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="4f4c7-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4f4c7-110">Attributes</span></span>

<span data-ttu-id="4f4c7-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="4f4c7-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4f4c7-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4f4c7-112">Child Elements</span></span>

|<span data-ttu-id="4f4c7-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="4f4c7-113">Element</span></span>|<span data-ttu-id="4f4c7-114">Описание</span><span class="sxs-lookup"><span data-stu-id="4f4c7-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4f4c7-115">Элемент Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="4f4c7-115">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)|<span data-ttu-id="4f4c7-116">Предоставляет определение представления списка.</span><span class="sxs-lookup"><span data-stu-id="4f4c7-116">Provides a definition of the list view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="4f4c7-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4f4c7-117">Parent Elements</span></span>

|<span data-ttu-id="4f4c7-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="4f4c7-118">Element</span></span>|<span data-ttu-id="4f4c7-119">Описание</span><span class="sxs-lookup"><span data-stu-id="4f4c7-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4f4c7-120">Элемент ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="4f4c7-120">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)|<span data-ttu-id="4f4c7-121">Определяет формат списка для представления.</span><span class="sxs-lookup"><span data-stu-id="4f4c7-121">Defines a list format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="4f4c7-122">Замечания</span><span class="sxs-lookup"><span data-stu-id="4f4c7-122">Remarks</span></span>

<span data-ttu-id="4f4c7-123">Дополнительные сведения о представлениях списков см. в разделе [представление списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="4f4c7-123">For more information about list views, see [List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="4f4c7-124">Пример</span><span class="sxs-lookup"><span data-stu-id="4f4c7-124">Example</span></span>

<span data-ttu-id="4f4c7-125">В этом примере показаны XML-элементы, определяющие представление списка для объекта [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) .</span><span class="sxs-lookup"><span data-stu-id="4f4c7-125">This example shows the XML elements that define the list view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="4f4c7-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="4f4c7-126">See Also</span></span>

[<span data-ttu-id="4f4c7-127">Элемент ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="4f4c7-127">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)

[<span data-ttu-id="4f4c7-128">Элемент Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="4f4c7-128">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="4f4c7-129">Представление списка</span><span class="sxs-lookup"><span data-stu-id="4f4c7-129">List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="4f4c7-130">Создание файла форматирования и типов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4f4c7-130">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
