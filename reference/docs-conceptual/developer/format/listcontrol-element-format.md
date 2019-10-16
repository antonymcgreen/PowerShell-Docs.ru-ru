---
title: Элемент ListControl (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 37beeb0b-7a81-4747-becb-e309e17278fb
caps.latest.revision: 12
ms.openlocfilehash: 7a117c25b0d117dc846ba8e060e31e838b5edd52
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362783"
---
# <a name="listcontrol-element-format"></a><span data-ttu-id="02144-102">Элемент ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="02144-102">ListControl Element (Format)</span></span>

<span data-ttu-id="02144-103">Определяет формат списка для представления.</span><span class="sxs-lookup"><span data-stu-id="02144-103">Defines a list format for the view.</span></span>

<span data-ttu-id="02144-104">Элемент конфигурации (Format) Виевдефинитионс элемента представления (Format) элемент (формат) ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="02144-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="02144-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="02144-105">Syntax</span></span>

```xml
<ListControl>
  <ListEntries>...</ListEntries>
</ListControl>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="02144-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="02144-106">Attributes and Elements</span></span>

<span data-ttu-id="02144-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `ListControl`.</span><span class="sxs-lookup"><span data-stu-id="02144-107">The following sections describe the attributes, child elements, and the parent element of the `ListControl` element.</span></span> <span data-ttu-id="02144-108">Этот элемент должен содержать только один дочерний элемент.</span><span class="sxs-lookup"><span data-stu-id="02144-108">This element must contain only a single child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="02144-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="02144-109">Attributes</span></span>

<span data-ttu-id="02144-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="02144-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="02144-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="02144-111">Child Elements</span></span>

|<span data-ttu-id="02144-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="02144-112">Element</span></span>|<span data-ttu-id="02144-113">Описание</span><span class="sxs-lookup"><span data-stu-id="02144-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="02144-114">Элемент Листентриес (Format)</span><span class="sxs-lookup"><span data-stu-id="02144-114">ListEntries Element (Format)</span></span>](./listentries-element-for-listcontrol-format.md)|<span data-ttu-id="02144-115">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="02144-115">Required element.</span></span><br /><br /> <span data-ttu-id="02144-116">Предоставляет определения представления списка.</span><span class="sxs-lookup"><span data-stu-id="02144-116">Provides the definitions of the list view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="02144-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="02144-117">Parent Elements</span></span>

|<span data-ttu-id="02144-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="02144-118">Element</span></span>|<span data-ttu-id="02144-119">Описание</span><span class="sxs-lookup"><span data-stu-id="02144-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="02144-120">View, элемент (Format)</span><span class="sxs-lookup"><span data-stu-id="02144-120">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="02144-121">Определяет представление, используемое для отображения элементов одного или нескольких объектов.</span><span class="sxs-lookup"><span data-stu-id="02144-121">Defines a view that is used to display the members of one or more objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="02144-122">Замечания</span><span class="sxs-lookup"><span data-stu-id="02144-122">Remarks</span></span>

<span data-ttu-id="02144-123">Дополнительные сведения о создании представления списка см. в разделе [Создание представления списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="02144-123">For more information about creating a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="02144-124">Пример</span><span class="sxs-lookup"><span data-stu-id="02144-124">Example</span></span>

<span data-ttu-id="02144-125">В этом примере показано представление списка для объекта [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) .</span><span class="sxs-lookup"><span data-stu-id="02144-125">This example shows a list view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="02144-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="02144-126">See Also</span></span>

[<span data-ttu-id="02144-127">View, элемент (Format)</span><span class="sxs-lookup"><span data-stu-id="02144-127">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="02144-128">Элемент Листентриес (Format)</span><span class="sxs-lookup"><span data-stu-id="02144-128">ListEntries Element (Format)</span></span>](./listentries-element-for-listcontrol-format.md)

[<span data-ttu-id="02144-129">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="02144-129">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="02144-130">Создание файла форматирования и типов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="02144-130">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
