---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент CustomControl для элемента View (формат)
description: Элемент CustomControl для элемента View (формат)
ms.openlocfilehash: 41352be55f0c03b2eaca0dbe2d7345e7cf804a7c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655462"
---
# <a name="customcontrol-element-for-view-format"></a><span data-ttu-id="6d69d-103">Элемент CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="6d69d-103">CustomControl Element for View (Format)</span></span>

<span data-ttu-id="6d69d-104">Определяет формат пользовательского элемента управления для представления.</span><span class="sxs-lookup"><span data-stu-id="6d69d-104">Defines a custom control format for the view.</span></span>

<span data-ttu-id="6d69d-105">Элемент конфигурации (Format) Виевдефинитионс элемента представления (Format) элемент (формат) ошибка customcontrol (Format)</span><span class="sxs-lookup"><span data-stu-id="6d69d-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="6d69d-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6d69d-106">Syntax</span></span>

```xml
<CustomControl>
  <CustomEntries>...</CustomEntries>
</CustomControl>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6d69d-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6d69d-107">Attributes and Elements</span></span>

<span data-ttu-id="6d69d-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `CustomControl` элемента.</span><span class="sxs-lookup"><span data-stu-id="6d69d-108">The following sections describe attributes, child elements, and the parent element of the `CustomControl` element.</span></span> <span data-ttu-id="6d69d-109">Необходимо указать один дочерний элемент.</span><span class="sxs-lookup"><span data-stu-id="6d69d-109">You must specify one child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="6d69d-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6d69d-110">Attributes</span></span>

<span data-ttu-id="6d69d-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="6d69d-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="6d69d-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6d69d-112">Child Elements</span></span>

|<span data-ttu-id="6d69d-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="6d69d-113">Element</span></span>|<span data-ttu-id="6d69d-114">Описание</span><span class="sxs-lookup"><span data-stu-id="6d69d-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6d69d-115">Элемент CustomEntries для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="6d69d-115">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)|<span data-ttu-id="6d69d-116">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="6d69d-116">Required element.</span></span><br /><br /> <span data-ttu-id="6d69d-117">Предоставляет определения представления пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="6d69d-117">Provides the definitions of the custom control view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="6d69d-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6d69d-118">Parent Elements</span></span>

|<span data-ttu-id="6d69d-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="6d69d-119">Element</span></span>|<span data-ttu-id="6d69d-120">Описание</span><span class="sxs-lookup"><span data-stu-id="6d69d-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6d69d-121">Элемент View (формат)</span><span class="sxs-lookup"><span data-stu-id="6d69d-121">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="6d69d-122">Определяет представление, используемое для отображения одного или нескольких объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="6d69d-122">Defines a view that is used to display one or more .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="6d69d-123">Комментарии</span><span class="sxs-lookup"><span data-stu-id="6d69d-123">Remarks</span></span>

<span data-ttu-id="6d69d-124">В большинстве случаев для каждого представления элемента управления требуется только одно определение, но можно предоставить несколько определений, если вы хотите использовать одно и то же представление для отображения различных объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="6d69d-124">In most cases, only one definition is required for each control view, but it is possible to provide multiple definitions if you want to use the same view to display different .NET objects.</span></span> <span data-ttu-id="6d69d-125">В таких случаях можно указать отдельное определение для каждого объекта или набора объектов.</span><span class="sxs-lookup"><span data-stu-id="6d69d-125">In those cases, you can provide a separate definition for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="6d69d-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="6d69d-126">See Also</span></span>

[<span data-ttu-id="6d69d-127">Элемент CustomEntries для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="6d69d-127">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)

[<span data-ttu-id="6d69d-128">Элемент View (формат)</span><span class="sxs-lookup"><span data-stu-id="6d69d-128">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="6d69d-129">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="6d69d-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
