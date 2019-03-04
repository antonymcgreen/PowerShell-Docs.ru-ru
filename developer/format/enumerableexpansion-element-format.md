---
title: Элемент EnumerableExpansion (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93d27173-9ae4-46e5-bb78-90525915cd70
caps.latest.revision: 9
ms.openlocfilehash: bc1e58c00ca8419f9204076f0a46050281e704db
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856840"
---
# <a name="enumerableexpansion-element-format"></a><span data-ttu-id="1e85d-102">Элемент EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="1e85d-102">EnumerableExpansion Element (Format)</span></span>

<span data-ttu-id="1e85d-103">Определяет, как определенные коллекции .NET, объекты развертываются в том случае, когда они отображаются в представлении.</span><span class="sxs-lookup"><span data-stu-id="1e85d-103">Defines how specific .NET collection objects are expanded when they are displayed in a view.</span></span>

<span data-ttu-id="1e85d-104">Элемент конфигурации элемент (формат) элемент DefaultSettings (формат) элемент EnumerableExpansions (формат) EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="1e85d-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="1e85d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1e85d-105">Syntax</span></span>

```xml
<EnumerableExpansion>
  <EntrySelectedBy>...</EntrySelectedBy>
  <Expand>EnumOnly, CoreOnly, Both</Expand>
</EnumerableExpansion>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1e85d-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1e85d-106">Attributes and Elements</span></span>

<span data-ttu-id="1e85d-107">Ниже описаны атрибуты, дочерние элементы и родительский элемент `EnumerableExpansion` элемент.</span><span class="sxs-lookup"><span data-stu-id="1e85d-107">The following sections describe attributes, child elements, and the parent element of the `EnumerableExpansion` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="1e85d-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1e85d-108">Attributes</span></span>

<span data-ttu-id="1e85d-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="1e85d-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1e85d-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1e85d-110">Child Elements</span></span>

|<span data-ttu-id="1e85d-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="1e85d-111">Element</span></span>|<span data-ttu-id="1e85d-112">Описание</span><span class="sxs-lookup"><span data-stu-id="1e85d-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1e85d-113">Элемент EntrySelectedBy для EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="1e85d-113">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)|<span data-ttu-id="1e85d-114">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="1e85d-114">Optional element.</span></span><br /><br /> <span data-ttu-id="1e85d-115">Определяет, какие объекты коллекции .NET расширяются согласно этому определению.</span><span class="sxs-lookup"><span data-stu-id="1e85d-115">Defines which .NET collection objects are expanded by this definition.</span></span>|
|[<span data-ttu-id="1e85d-116">Разверните элемент (формат)</span><span class="sxs-lookup"><span data-stu-id="1e85d-116">Expand Element (Format)</span></span>](./expand-element-format.md)|<span data-ttu-id="1e85d-117">Указывает, каким образом объект коллекции расширяется для данного определения.</span><span class="sxs-lookup"><span data-stu-id="1e85d-117">Specifies how the collection object is expanded for this definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="1e85d-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1e85d-118">Parent Elements</span></span>

|<span data-ttu-id="1e85d-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="1e85d-119">Element</span></span>|<span data-ttu-id="1e85d-120">Описание</span><span class="sxs-lookup"><span data-stu-id="1e85d-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1e85d-121">Элемент EnumerableExpansions (формат)</span><span class="sxs-lookup"><span data-stu-id="1e85d-121">EnumerableExpansions Element (Format)</span></span>](./enumerableexpansions-element-format.md)|<span data-ttu-id="1e85d-122">Определяет различные способы, коллекции .NET, в которой объекты развертываются в том случае, когда они отображаются в представлении.</span><span class="sxs-lookup"><span data-stu-id="1e85d-122">Defines the different ways that .NET collection objects are expanded when they are displayed in a view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="1e85d-123">Замечания</span><span class="sxs-lookup"><span data-stu-id="1e85d-123">Remarks</span></span>

<span data-ttu-id="1e85d-124">Этот элемент используется для определения того, как отображаются объекты и коллекции объектов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="1e85d-124">This element is used to define how collection objects and the objects in the collection are displayed.</span></span> <span data-ttu-id="1e85d-125">В этом случае объект коллекции ссылается на любой объект, который поддерживает **System.Collections.ICollection** интерфейс.</span><span class="sxs-lookup"><span data-stu-id="1e85d-125">In this case, a collection object refers to any object that supports the  **System.Collections.ICollection** interface.</span></span>

<span data-ttu-id="1e85d-126">По умолчанию задается для отображения только свойств объектов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="1e85d-126">The default behavior is to display only the properties of the objects in the collection.</span></span>

## <a name="see-also"></a><span data-ttu-id="1e85d-127">См. также</span><span class="sxs-lookup"><span data-stu-id="1e85d-127">See Also</span></span>

[<span data-ttu-id="1e85d-128">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e85d-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
