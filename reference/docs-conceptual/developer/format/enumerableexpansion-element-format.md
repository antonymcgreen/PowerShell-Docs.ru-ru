---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент EnumerableExpansion (формат)
description: Элемент EnumerableExpansion (формат)
ms.openlocfilehash: 207ad99d5335e99701660159ab77279b55b0b6b5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668020"
---
# <a name="enumerableexpansion-element-format"></a><span data-ttu-id="ef5d9-103">Элемент EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="ef5d9-103">EnumerableExpansion Element (Format)</span></span>

<span data-ttu-id="ef5d9-104">Определяет, каким способом развертываются определенные объекты коллекции .NET, когда они отображаются в представлении.</span><span class="sxs-lookup"><span data-stu-id="ef5d9-104">Defines how specific .NET collection objects are expanded when they are displayed in a view.</span></span>

<span data-ttu-id="ef5d9-105">Элемент конфигурации (Format) Дефаултсеттингс элемент (Format) Енумерабликспансионс элемент (Format) Енумерабликспансион (формат)</span><span class="sxs-lookup"><span data-stu-id="ef5d9-105">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ef5d9-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ef5d9-106">Syntax</span></span>

```xml
<EnumerableExpansion>
  <EntrySelectedBy>...</EntrySelectedBy>
  <Expand>EnumOnly, CoreOnly, Both</Expand>
</EnumerableExpansion>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ef5d9-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ef5d9-107">Attributes and Elements</span></span>

<span data-ttu-id="ef5d9-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `EnumerableExpansion` элемента.</span><span class="sxs-lookup"><span data-stu-id="ef5d9-108">The following sections describe attributes, child elements, and the parent element of the `EnumerableExpansion` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ef5d9-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ef5d9-109">Attributes</span></span>

<span data-ttu-id="ef5d9-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ef5d9-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ef5d9-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ef5d9-111">Child Elements</span></span>

|<span data-ttu-id="ef5d9-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="ef5d9-112">Element</span></span>|<span data-ttu-id="ef5d9-113">Описание</span><span class="sxs-lookup"><span data-stu-id="ef5d9-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ef5d9-114">Элемент EntrySelectedBy для элемента EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="ef5d9-114">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)|<span data-ttu-id="ef5d9-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="ef5d9-115">Optional element.</span></span><br /><br /> <span data-ttu-id="ef5d9-116">Определяет, какие объекты коллекции .NET разворачиваются этим определением.</span><span class="sxs-lookup"><span data-stu-id="ef5d9-116">Defines which .NET collection objects are expanded by this definition.</span></span>|
|[<span data-ttu-id="ef5d9-117">Элемент Expand (формат)</span><span class="sxs-lookup"><span data-stu-id="ef5d9-117">Expand Element (Format)</span></span>](./expand-element-format.md)|<span data-ttu-id="ef5d9-118">Указывает, как разворачивается объект коллекции для этого определения.</span><span class="sxs-lookup"><span data-stu-id="ef5d9-118">Specifies how the collection object is expanded for this definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="ef5d9-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ef5d9-119">Parent Elements</span></span>

|<span data-ttu-id="ef5d9-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="ef5d9-120">Element</span></span>|<span data-ttu-id="ef5d9-121">Описание</span><span class="sxs-lookup"><span data-stu-id="ef5d9-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ef5d9-122">Элемент EnumerableExpansions (формат)</span><span class="sxs-lookup"><span data-stu-id="ef5d9-122">EnumerableExpansions Element (Format)</span></span>](./enumerableexpansions-element-format.md)|<span data-ttu-id="ef5d9-123">Определяет различные способы развертывания объектов коллекции .NET при их отображении в представлении.</span><span class="sxs-lookup"><span data-stu-id="ef5d9-123">Defines the different ways that .NET collection objects are expanded when they are displayed in a view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ef5d9-124">Комментарии</span><span class="sxs-lookup"><span data-stu-id="ef5d9-124">Remarks</span></span>

<span data-ttu-id="ef5d9-125">Этот элемент используется для определения способа отображения объектов коллекции и объектов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="ef5d9-125">This element is used to define how collection objects and the objects in the collection are displayed.</span></span> <span data-ttu-id="ef5d9-126">В этом случае объект коллекции ссылается на любой объект, поддерживающий интерфейс  **System. Collections. ICollection** .</span><span class="sxs-lookup"><span data-stu-id="ef5d9-126">In this case, a collection object refers to any object that supports the  **System.Collections.ICollection** interface.</span></span>

<span data-ttu-id="ef5d9-127">Поведение по умолчанию — отображение только свойств объектов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="ef5d9-127">The default behavior is to display only the properties of the objects in the collection.</span></span>

## <a name="see-also"></a><span data-ttu-id="ef5d9-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="ef5d9-128">See Also</span></span>

[<span data-ttu-id="ef5d9-129">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="ef5d9-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
