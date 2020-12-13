---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент ListEntry для элемента ListControl (формат)
description: Элемент ListEntry для элемента ListControl (формат)
ms.openlocfilehash: 96ae5fcdd837d2491d6c7ff6a375fef1d83ae3e9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666575"
---
# <a name="listentry-element-for-listcontrol-format"></a><span data-ttu-id="979bf-103">Элемент ListEntry для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="979bf-103">ListEntry Element for ListControl (Format)</span></span>

<span data-ttu-id="979bf-104">Предоставляет определение представления списка.</span><span class="sxs-lookup"><span data-stu-id="979bf-104">Provides a definition of the list view.</span></span>

<span data-ttu-id="979bf-105">Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) ListControl элемент (Format) Листентриес элемент (Format) Листентри элемент (Format)</span><span class="sxs-lookup"><span data-stu-id="979bf-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="979bf-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="979bf-106">Syntax</span></span>

```xml
<ListEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <ListItems>...</ListItems>
</ListEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="979bf-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="979bf-107">Attributes and Elements</span></span>

<span data-ttu-id="979bf-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ListEntry` элемента.</span><span class="sxs-lookup"><span data-stu-id="979bf-108">The following sections describe the attributes, child elements, and the parent element of the `ListEntry` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="979bf-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="979bf-109">Attributes</span></span>

<span data-ttu-id="979bf-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="979bf-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="979bf-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="979bf-111">Child Elements</span></span>

|<span data-ttu-id="979bf-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="979bf-112">Element</span></span>|<span data-ttu-id="979bf-113">Описание</span><span class="sxs-lookup"><span data-stu-id="979bf-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="979bf-114">Элемент Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="979bf-114">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="979bf-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="979bf-115">Optional element.</span></span><br /><br /> <span data-ttu-id="979bf-116">Определяет объекты .NET, использующие это определение представления списка, или условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="979bf-116">Defines the .NET objects that use this list view definition or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="979bf-117">Элемент ListItems (формат)</span><span class="sxs-lookup"><span data-stu-id="979bf-117">ListItems Element (Format)</span></span>](./listitems-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="979bf-118">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="979bf-118">Required element.</span></span><br /><br /> <span data-ttu-id="979bf-119">Определяет свойства и скрипты, значения которых отображаются в представлении списка.</span><span class="sxs-lookup"><span data-stu-id="979bf-119">Defines the properties and scripts whose values are displayed by the list view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="979bf-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="979bf-120">Parent Elements</span></span>

|<span data-ttu-id="979bf-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="979bf-121">Element</span></span>|<span data-ttu-id="979bf-122">Описание</span><span class="sxs-lookup"><span data-stu-id="979bf-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="979bf-123">Элемент Листентриес (Format)</span><span class="sxs-lookup"><span data-stu-id="979bf-123">ListEntries Element (Format)</span></span>](./listentries-element-for-listcontrol-format.md)|<span data-ttu-id="979bf-124">Предоставляет определения представления списка.</span><span class="sxs-lookup"><span data-stu-id="979bf-124">Provides the definitions of the list view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="979bf-125">Комментарии</span><span class="sxs-lookup"><span data-stu-id="979bf-125">Remarks</span></span>

<span data-ttu-id="979bf-126">Представление списка — это формат списка, который отображает значения свойств или значения скриптов для каждого объекта.</span><span class="sxs-lookup"><span data-stu-id="979bf-126">A list view is a list format that displays property values or script values for each object.</span></span> <span data-ttu-id="979bf-127">Дополнительные сведения о представлениях списков см. [в разделе Создание представления списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="979bf-127">For more information about list views, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="979bf-128">Пример</span><span class="sxs-lookup"><span data-stu-id="979bf-128">Example</span></span>

<span data-ttu-id="979bf-129">В этом примере показаны XML-элементы, определяющие представление списка для объекта [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) .</span><span class="sxs-lookup"><span data-stu-id="979bf-129">This example shows the XML elements that define the list view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="979bf-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="979bf-130">See Also</span></span>

[<span data-ttu-id="979bf-131">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="979bf-131">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="979bf-132">Элемент Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="979bf-132">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="979bf-133">Элемент Листентриес (Format)</span><span class="sxs-lookup"><span data-stu-id="979bf-133">ListEntries Element (Format)</span></span>](./listentries-element-for-listcontrol-format.md)

[<span data-ttu-id="979bf-134">Элемент ListItems (формат)</span><span class="sxs-lookup"><span data-stu-id="979bf-134">ListItems Element (Format)</span></span>](./listitems-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="979bf-135">Создание файла форматирования и типов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="979bf-135">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
