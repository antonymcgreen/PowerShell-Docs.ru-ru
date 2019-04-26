---
title: Элемент ListControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 37beeb0b-7a81-4747-becb-e309e17278fb
caps.latest.revision: 12
ms.openlocfilehash: 7a117c25b0d117dc846ba8e060e31e838b5edd52
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065263"
---
# <a name="listcontrol-element-format"></a><span data-ttu-id="f893b-102">Элемент ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="f893b-102">ListControl Element (Format)</span></span>

<span data-ttu-id="f893b-103">Определяет формат для представления списка.</span><span class="sxs-lookup"><span data-stu-id="f893b-103">Defines a list format for the view.</span></span>

<span data-ttu-id="f893b-104">Элемент элемента (формат) ListControl для элемента (формат) элемент ViewDefinitions (формат) конфигурации представления (формат)</span><span class="sxs-lookup"><span data-stu-id="f893b-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f893b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f893b-105">Syntax</span></span>

```xml
<ListControl>
  <ListEntries>...</ListEntries>
</ListControl>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="f893b-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f893b-106">Attributes and Elements</span></span>

<span data-ttu-id="f893b-107">В следующих разделах атрибуты, дочерние элементы и родительский элемент `ListControl` элемент.</span><span class="sxs-lookup"><span data-stu-id="f893b-107">The following sections describe the attributes, child elements, and the parent element of the `ListControl` element.</span></span> <span data-ttu-id="f893b-108">Этот элемент должен содержать только один дочерний элемент.</span><span class="sxs-lookup"><span data-stu-id="f893b-108">This element must contain only a single child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f893b-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f893b-109">Attributes</span></span>

<span data-ttu-id="f893b-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="f893b-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f893b-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f893b-111">Child Elements</span></span>

|<span data-ttu-id="f893b-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="f893b-112">Element</span></span>|<span data-ttu-id="f893b-113">Описание</span><span class="sxs-lookup"><span data-stu-id="f893b-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f893b-114">Элемент ListEntries (формат)</span><span class="sxs-lookup"><span data-stu-id="f893b-114">ListEntries Element (Format)</span></span>](./listentries-element-for-listcontrol-format.md)|<span data-ttu-id="f893b-115">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="f893b-115">Required element.</span></span><br /><br /> <span data-ttu-id="f893b-116">Предоставляет определения представления "list".</span><span class="sxs-lookup"><span data-stu-id="f893b-116">Provides the definitions of the list view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="f893b-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f893b-117">Parent Elements</span></span>

|<span data-ttu-id="f893b-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="f893b-118">Element</span></span>|<span data-ttu-id="f893b-119">Описание</span><span class="sxs-lookup"><span data-stu-id="f893b-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f893b-120">Элемент представления (формат)</span><span class="sxs-lookup"><span data-stu-id="f893b-120">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="f893b-121">Определяет представление, которое используется для отображения элементов из одного или нескольких объектов.</span><span class="sxs-lookup"><span data-stu-id="f893b-121">Defines a view that is used to display the members of one or more objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f893b-122">Замечания</span><span class="sxs-lookup"><span data-stu-id="f893b-122">Remarks</span></span>

<span data-ttu-id="f893b-123">Дополнительные сведения о создании представления списка, см. в разделе [Создание представления списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="f893b-123">For more information about creating a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="f893b-124">Пример</span><span class="sxs-lookup"><span data-stu-id="f893b-124">Example</span></span>

<span data-ttu-id="f893b-125">В этом примере показано представление списка для [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) объекта.</span><span class="sxs-lookup"><span data-stu-id="f893b-125">This example shows a list view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="f893b-126">См. также</span><span class="sxs-lookup"><span data-stu-id="f893b-126">See Also</span></span>

[<span data-ttu-id="f893b-127">Элемент представления (формат)</span><span class="sxs-lookup"><span data-stu-id="f893b-127">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="f893b-128">Элемент ListEntries (формат)</span><span class="sxs-lookup"><span data-stu-id="f893b-128">ListEntries Element (Format)</span></span>](./listentries-element-for-listcontrol-format.md)

[<span data-ttu-id="f893b-129">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="f893b-129">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="f893b-130">Написание форматирования Windows PowerShell и типы файлов</span><span class="sxs-lookup"><span data-stu-id="f893b-130">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
