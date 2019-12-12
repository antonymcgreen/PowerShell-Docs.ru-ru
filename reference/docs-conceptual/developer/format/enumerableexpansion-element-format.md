---
title: Элемент Енумерабликспансион (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93d27173-9ae4-46e5-bb78-90525915cd70
caps.latest.revision: 9
ms.openlocfilehash: bc1e58c00ca8419f9204076f0a46050281e704db
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368753"
---
# <a name="enumerableexpansion-element-format"></a><span data-ttu-id="465f3-102">Элемент EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="465f3-102">EnumerableExpansion Element (Format)</span></span>

<span data-ttu-id="465f3-103">Определяет, каким способом развертываются определенные объекты коллекции .NET, когда они отображаются в представлении.</span><span class="sxs-lookup"><span data-stu-id="465f3-103">Defines how specific .NET collection objects are expanded when they are displayed in a view.</span></span>

<span data-ttu-id="465f3-104">Элемент конфигурации (Format) Дефаултсеттингс элемент (Format) Енумерабликспансионс элемент (Format) Енумерабликспансион (формат)</span><span class="sxs-lookup"><span data-stu-id="465f3-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="465f3-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="465f3-105">Syntax</span></span>

```xml
<EnumerableExpansion>
  <EntrySelectedBy>...</EntrySelectedBy>
  <Expand>EnumOnly, CoreOnly, Both</Expand>
</EnumerableExpansion>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="465f3-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="465f3-106">Attributes and Elements</span></span>

<span data-ttu-id="465f3-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `EnumerableExpansion`.</span><span class="sxs-lookup"><span data-stu-id="465f3-107">The following sections describe attributes, child elements, and the parent element of the `EnumerableExpansion` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="465f3-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="465f3-108">Attributes</span></span>

<span data-ttu-id="465f3-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="465f3-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="465f3-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="465f3-110">Child Elements</span></span>

|<span data-ttu-id="465f3-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="465f3-111">Element</span></span>|<span data-ttu-id="465f3-112">Описание</span><span class="sxs-lookup"><span data-stu-id="465f3-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="465f3-113">Элемент Ентриселектедби для Енумерабликспансион (Format)</span><span class="sxs-lookup"><span data-stu-id="465f3-113">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)|<span data-ttu-id="465f3-114">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="465f3-114">Optional element.</span></span><br /><br /> <span data-ttu-id="465f3-115">Определяет, какие объекты коллекции .NET разворачиваются этим определением.</span><span class="sxs-lookup"><span data-stu-id="465f3-115">Defines which .NET collection objects are expanded by this definition.</span></span>|
|[<span data-ttu-id="465f3-116">Элемент Expand (Format)</span><span class="sxs-lookup"><span data-stu-id="465f3-116">Expand Element (Format)</span></span>](./expand-element-format.md)|<span data-ttu-id="465f3-117">Указывает, как разворачивается объект коллекции для этого определения.</span><span class="sxs-lookup"><span data-stu-id="465f3-117">Specifies how the collection object is expanded for this definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="465f3-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="465f3-118">Parent Elements</span></span>

|<span data-ttu-id="465f3-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="465f3-119">Element</span></span>|<span data-ttu-id="465f3-120">Описание</span><span class="sxs-lookup"><span data-stu-id="465f3-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="465f3-121">Элемент Енумерабликспансионс (Format)</span><span class="sxs-lookup"><span data-stu-id="465f3-121">EnumerableExpansions Element (Format)</span></span>](./enumerableexpansions-element-format.md)|<span data-ttu-id="465f3-122">Определяет различные способы развертывания объектов коллекции .NET при их отображении в представлении.</span><span class="sxs-lookup"><span data-stu-id="465f3-122">Defines the different ways that .NET collection objects are expanded when they are displayed in a view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="465f3-123">Замечания</span><span class="sxs-lookup"><span data-stu-id="465f3-123">Remarks</span></span>

<span data-ttu-id="465f3-124">Этот элемент используется для определения способа отображения объектов коллекции и объектов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="465f3-124">This element is used to define how collection objects and the objects in the collection are displayed.</span></span> <span data-ttu-id="465f3-125">В этом случае объект коллекции ссылается на любой объект, поддерживающий интерфейс **System. Collections. ICollection** .</span><span class="sxs-lookup"><span data-stu-id="465f3-125">In this case, a collection object refers to any object that supports the  **System.Collections.ICollection** interface.</span></span>

<span data-ttu-id="465f3-126">Поведение по умолчанию — отображение только свойств объектов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="465f3-126">The default behavior is to display only the properties of the objects in the collection.</span></span>

## <a name="see-also"></a><span data-ttu-id="465f3-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="465f3-127">See Also</span></span>

[<span data-ttu-id="465f3-128">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="465f3-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
