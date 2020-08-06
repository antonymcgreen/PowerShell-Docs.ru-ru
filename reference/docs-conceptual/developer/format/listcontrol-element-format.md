---
title: Элемент ListControl (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 0173b9797bffcca74f1a32903686f771366ebb1b
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785733"
---
# <a name="listcontrol-element-format"></a><span data-ttu-id="c76a8-102">Элемент ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="c76a8-102">ListControl Element (Format)</span></span>

<span data-ttu-id="c76a8-103">Определяет формат списка для представления.</span><span class="sxs-lookup"><span data-stu-id="c76a8-103">Defines a list format for the view.</span></span>

<span data-ttu-id="c76a8-104">Элемент конфигурации (Format) Виевдефинитионс элемента представления (Format) элемент (формат) ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="c76a8-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c76a8-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c76a8-105">Syntax</span></span>

```xml
<ListControl>
  <ListEntries>...</ListEntries>
</ListControl>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="c76a8-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c76a8-106">Attributes and Elements</span></span>

<span data-ttu-id="c76a8-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ListControl` элемента.</span><span class="sxs-lookup"><span data-stu-id="c76a8-107">The following sections describe the attributes, child elements, and the parent element of the `ListControl` element.</span></span> <span data-ttu-id="c76a8-108">Этот элемент должен содержать только один дочерний элемент.</span><span class="sxs-lookup"><span data-stu-id="c76a8-108">This element must contain only a single child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="c76a8-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c76a8-109">Attributes</span></span>

<span data-ttu-id="c76a8-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="c76a8-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c76a8-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c76a8-111">Child Elements</span></span>

|<span data-ttu-id="c76a8-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="c76a8-112">Element</span></span>|<span data-ttu-id="c76a8-113">Описание</span><span class="sxs-lookup"><span data-stu-id="c76a8-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c76a8-114">Элемент Листентриес (Format)</span><span class="sxs-lookup"><span data-stu-id="c76a8-114">ListEntries Element (Format)</span></span>](./listentries-element-for-listcontrol-format.md)|<span data-ttu-id="c76a8-115">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="c76a8-115">Required element.</span></span><br /><br /> <span data-ttu-id="c76a8-116">Предоставляет определения представления списка.</span><span class="sxs-lookup"><span data-stu-id="c76a8-116">Provides the definitions of the list view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="c76a8-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c76a8-117">Parent Elements</span></span>

|<span data-ttu-id="c76a8-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="c76a8-118">Element</span></span>|<span data-ttu-id="c76a8-119">Описание</span><span class="sxs-lookup"><span data-stu-id="c76a8-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c76a8-120">Элемент View (формат)</span><span class="sxs-lookup"><span data-stu-id="c76a8-120">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="c76a8-121">Определяет представление, используемое для отображения элементов одного или нескольких объектов.</span><span class="sxs-lookup"><span data-stu-id="c76a8-121">Defines a view that is used to display the members of one or more objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="c76a8-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="c76a8-122">Remarks</span></span>

<span data-ttu-id="c76a8-123">Дополнительные сведения о создании представления списка см. в разделе [Создание представления списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="c76a8-123">For more information about creating a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="c76a8-124">Пример</span><span class="sxs-lookup"><span data-stu-id="c76a8-124">Example</span></span>

<span data-ttu-id="c76a8-125">В этом примере показано представление списка для объекта [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) .</span><span class="sxs-lookup"><span data-stu-id="c76a8-125">This example shows a list view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="c76a8-126">См. также</span><span class="sxs-lookup"><span data-stu-id="c76a8-126">See Also</span></span>

[<span data-ttu-id="c76a8-127">Элемент View (формат)</span><span class="sxs-lookup"><span data-stu-id="c76a8-127">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="c76a8-128">Элемент Листентриес (Format)</span><span class="sxs-lookup"><span data-stu-id="c76a8-128">ListEntries Element (Format)</span></span>](./listentries-element-for-listcontrol-format.md)

[<span data-ttu-id="c76a8-129">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="c76a8-129">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="c76a8-130">Создание файла форматирования и типов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c76a8-130">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
