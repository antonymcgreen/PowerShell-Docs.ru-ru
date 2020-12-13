---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент Expand (формат)
description: Элемент Expand (формат)
ms.openlocfilehash: 518e132e3e74b921d4e51966fc60088a22ef63f1
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667952"
---
# <a name="expand-element-format"></a><span data-ttu-id="0e50c-103">Элемент Expand (формат)</span><span class="sxs-lookup"><span data-stu-id="0e50c-103">Expand Element (Format)</span></span>

<span data-ttu-id="0e50c-104">Указывает, как разворачивается объект коллекции для этого определения.</span><span class="sxs-lookup"><span data-stu-id="0e50c-104">Specifies how the collection object is expanded for this definition.</span></span>

<span data-ttu-id="0e50c-105">Элемент конфигурации (Format) Дефаултсеттингс элемент (Format) Енумерабликспансионс элемент (Format) Енумерабликспансион элемент (Format) развернуть элемент (Format)</span><span class="sxs-lookup"><span data-stu-id="0e50c-105">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) Expand Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="0e50c-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0e50c-106">Syntax</span></span>

```xml
<Expand>EnumOnly, CoreOnly, Both</Expand>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0e50c-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0e50c-107">Attributes and Elements</span></span>

<span data-ttu-id="0e50c-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `Expand` элемента.</span><span class="sxs-lookup"><span data-stu-id="0e50c-108">The following sections describe attributes, child elements, and the parent element of the `Expand` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="0e50c-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0e50c-109">Attributes</span></span>

<span data-ttu-id="0e50c-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0e50c-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="0e50c-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0e50c-111">Child Elements</span></span>

<span data-ttu-id="0e50c-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0e50c-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="0e50c-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0e50c-113">Parent Elements</span></span>

|<span data-ttu-id="0e50c-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="0e50c-114">Element</span></span>|<span data-ttu-id="0e50c-115">Описание</span><span class="sxs-lookup"><span data-stu-id="0e50c-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0e50c-116">Элемент EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="0e50c-116">EnumerableExpansion Element (Format)</span></span>](./enumerableexpansion-element-format.md)|<span data-ttu-id="0e50c-117">Определяет, каким способом развертываются определенные объекты коллекции .NET, когда они отображаются в представлении.</span><span class="sxs-lookup"><span data-stu-id="0e50c-117">Defines how specific .NET collection objects are expanded when they are displayed in a view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="0e50c-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="0e50c-118">Text Value</span></span>

<span data-ttu-id="0e50c-119">Укажите одно из следующих значений.</span><span class="sxs-lookup"><span data-stu-id="0e50c-119">Specify one of the following values:</span></span>

- <span data-ttu-id="0e50c-120">Енумонли: отображает только свойства объектов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="0e50c-120">EnumOnly: Displays only the properties of the objects in the collection.</span></span>

- <span data-ttu-id="0e50c-121">Кореонли: отображает только свойства объекта коллекции.</span><span class="sxs-lookup"><span data-stu-id="0e50c-121">CoreOnly: Displays only the properties of the collection object.</span></span>

- <span data-ttu-id="0e50c-122">Оба: отображает свойства объектов в коллекции и свойства объекта коллекции.</span><span class="sxs-lookup"><span data-stu-id="0e50c-122">Both: Displays the properties of the objects in the collection and the properties of the collection object.</span></span>

## <a name="remarks"></a><span data-ttu-id="0e50c-123">Комментарии</span><span class="sxs-lookup"><span data-stu-id="0e50c-123">Remarks</span></span>

<span data-ttu-id="0e50c-124">Этот элемент используется для определения способа отображения объектов коллекции и объектов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="0e50c-124">This element is used to define how collection objects and the objects in the collection are displayed.</span></span> <span data-ttu-id="0e50c-125">В этом случае объект коллекции ссылается на любой объект, поддерживающий интерфейс  **System. Collections. ICollection** .</span><span class="sxs-lookup"><span data-stu-id="0e50c-125">In this case, a collection object refers to any object that supports the  **System.Collections.ICollection** interface.</span></span>

<span data-ttu-id="0e50c-126">Поведение по умолчанию — отображение только свойств объектов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="0e50c-126">The default behavior is to display only the properties of the objects in the collection.</span></span>

## <a name="see-also"></a><span data-ttu-id="0e50c-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="0e50c-127">See Also</span></span>

[<span data-ttu-id="0e50c-128">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="0e50c-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
