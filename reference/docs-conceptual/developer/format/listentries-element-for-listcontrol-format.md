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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72362763"
---
# <a name="listentries-element-for-listcontrol-format"></a><span data-ttu-id="15766-102">Элемент ListEntries для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="15766-102">ListEntries Element for ListControl (Format)</span></span>

<span data-ttu-id="15766-103">Предоставляет определения представления списка.</span><span class="sxs-lookup"><span data-stu-id="15766-103">Provides the definitions of the list view.</span></span> <span data-ttu-id="15766-104">В представлении списка должно быть указано одно или несколько определений.</span><span class="sxs-lookup"><span data-stu-id="15766-104">The list view must specify one or more definitions.</span></span>

<span data-ttu-id="15766-105">Элемент конфигурации (Format) Виевдефинитионс элемента представления (Format) элемент (формат) ListControl элемент (Format) Листентриес (формат)</span><span class="sxs-lookup"><span data-stu-id="15766-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="15766-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="15766-106">Syntax</span></span>

```xml
<ListEntries>
  <ListEntry>...</ListEntry>
</ListEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="15766-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="15766-107">Attributes and Elements</span></span>

<span data-ttu-id="15766-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `ListEntries`.</span><span class="sxs-lookup"><span data-stu-id="15766-108">The following sections describe the attributes, child elements, and the parent element of the `ListEntries` element.</span></span> <span data-ttu-id="15766-109">Необходимо указать по крайней мере один дочерний элемент.</span><span class="sxs-lookup"><span data-stu-id="15766-109">At least one child element must be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="15766-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="15766-110">Attributes</span></span>

<span data-ttu-id="15766-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="15766-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="15766-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="15766-112">Child Elements</span></span>

|<span data-ttu-id="15766-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="15766-113">Element</span></span>|<span data-ttu-id="15766-114">Описание</span><span class="sxs-lookup"><span data-stu-id="15766-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="15766-115">Элемент Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="15766-115">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)|<span data-ttu-id="15766-116">Предоставляет определение представления списка.</span><span class="sxs-lookup"><span data-stu-id="15766-116">Provides a definition of the list view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="15766-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="15766-117">Parent Elements</span></span>

|<span data-ttu-id="15766-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="15766-118">Element</span></span>|<span data-ttu-id="15766-119">Описание</span><span class="sxs-lookup"><span data-stu-id="15766-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="15766-120">Элемент ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="15766-120">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)|<span data-ttu-id="15766-121">Определяет формат списка для представления.</span><span class="sxs-lookup"><span data-stu-id="15766-121">Defines a list format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="15766-122">Замечания</span><span class="sxs-lookup"><span data-stu-id="15766-122">Remarks</span></span>

<span data-ttu-id="15766-123">Дополнительные сведения о представлениях списков см. в разделе [представление списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="15766-123">For more information about list views, see [List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="15766-124">Пример</span><span class="sxs-lookup"><span data-stu-id="15766-124">Example</span></span>

<span data-ttu-id="15766-125">В этом примере показаны XML-элементы, определяющие представление списка для объекта [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) .</span><span class="sxs-lookup"><span data-stu-id="15766-125">This example shows the XML elements that define the list view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="15766-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="15766-126">See Also</span></span>

[<span data-ttu-id="15766-127">Элемент ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="15766-127">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)

[<span data-ttu-id="15766-128">Элемент Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="15766-128">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="15766-129">Представление списка</span><span class="sxs-lookup"><span data-stu-id="15766-129">List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="15766-130">Создание файла форматирования и типов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="15766-130">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
