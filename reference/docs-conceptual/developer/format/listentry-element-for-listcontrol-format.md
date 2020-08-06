---
title: Элемент Листентри для ListControl (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: d98f0b5215eea7668f866d2733214ade79d748f1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785699"
---
# <a name="listentry-element-for-listcontrol-format"></a><span data-ttu-id="c200a-102">Элемент ListEntry для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="c200a-102">ListEntry Element for ListControl (Format)</span></span>

<span data-ttu-id="c200a-103">Предоставляет определение представления списка.</span><span class="sxs-lookup"><span data-stu-id="c200a-103">Provides a definition of the list view.</span></span>

<span data-ttu-id="c200a-104">Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) ListControl элемент (Format) Листентриес элемент (Format) Листентри элемент (Format)</span><span class="sxs-lookup"><span data-stu-id="c200a-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c200a-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c200a-105">Syntax</span></span>

```xml
<ListEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <ListItems>...</ListItems>
</ListEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c200a-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c200a-106">Attributes and Elements</span></span>

<span data-ttu-id="c200a-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ListEntry` элемента.</span><span class="sxs-lookup"><span data-stu-id="c200a-107">The following sections describe the attributes, child elements, and the parent element of the `ListEntry` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="c200a-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c200a-108">Attributes</span></span>

<span data-ttu-id="c200a-109">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="c200a-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c200a-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c200a-110">Child Elements</span></span>

|<span data-ttu-id="c200a-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="c200a-111">Element</span></span>|<span data-ttu-id="c200a-112">Описание</span><span class="sxs-lookup"><span data-stu-id="c200a-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c200a-113">Элемент Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="c200a-113">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="c200a-114">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="c200a-114">Optional element.</span></span><br /><br /> <span data-ttu-id="c200a-115">Определяет объекты .NET, использующие это определение представления списка, или условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="c200a-115">Defines the .NET objects that use this list view definition or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="c200a-116">Элемент ListItems (формат)</span><span class="sxs-lookup"><span data-stu-id="c200a-116">ListItems Element (Format)</span></span>](./listitems-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="c200a-117">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="c200a-117">Required element.</span></span><br /><br /> <span data-ttu-id="c200a-118">Определяет свойства и скрипты, значения которых отображаются в представлении списка.</span><span class="sxs-lookup"><span data-stu-id="c200a-118">Defines the properties and scripts whose values are displayed by the list view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="c200a-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c200a-119">Parent Elements</span></span>

|<span data-ttu-id="c200a-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="c200a-120">Element</span></span>|<span data-ttu-id="c200a-121">Описание</span><span class="sxs-lookup"><span data-stu-id="c200a-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c200a-122">Элемент Листентриес (Format)</span><span class="sxs-lookup"><span data-stu-id="c200a-122">ListEntries Element (Format)</span></span>](./listentries-element-for-listcontrol-format.md)|<span data-ttu-id="c200a-123">Предоставляет определения представления списка.</span><span class="sxs-lookup"><span data-stu-id="c200a-123">Provides the definitions of the list view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="c200a-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="c200a-124">Remarks</span></span>

<span data-ttu-id="c200a-125">Представление списка — это формат списка, который отображает значения свойств или значения скриптов для каждого объекта.</span><span class="sxs-lookup"><span data-stu-id="c200a-125">A list view is a list format that displays property values or script values for each object.</span></span> <span data-ttu-id="c200a-126">Дополнительные сведения о представлениях списков см. [в разделе Создание представления списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="c200a-126">For more information about list views, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="c200a-127">Пример</span><span class="sxs-lookup"><span data-stu-id="c200a-127">Example</span></span>

<span data-ttu-id="c200a-128">В этом примере показаны XML-элементы, определяющие представление списка для объекта [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) .</span><span class="sxs-lookup"><span data-stu-id="c200a-128">This example shows the XML elements that define the list view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="c200a-129">См. также</span><span class="sxs-lookup"><span data-stu-id="c200a-129">See Also</span></span>

[<span data-ttu-id="c200a-130">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="c200a-130">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="c200a-131">Элемент Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="c200a-131">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="c200a-132">Элемент Листентриес (Format)</span><span class="sxs-lookup"><span data-stu-id="c200a-132">ListEntries Element (Format)</span></span>](./listentries-element-for-listcontrol-format.md)

[<span data-ttu-id="c200a-133">Элемент ListItems (формат)</span><span class="sxs-lookup"><span data-stu-id="c200a-133">ListItems Element (Format)</span></span>](./listitems-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="c200a-134">Создание файла форматирования и типов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c200a-134">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
