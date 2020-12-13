---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент CustomEntries для элемента CustomControl для элемента View (формат)
description: Элемент CustomEntries для элемента CustomControl для элемента View (формат)
ms.openlocfilehash: 6e757bccdface2503667f8786462a2b43134a07d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649984"
---
# <a name="customentries-element-for-customcontrol-for-view-format"></a><span data-ttu-id="1a668-103">Элемент CustomEntries для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="1a668-103">CustomEntries Element for CustomControl for View (Format)</span></span>

<span data-ttu-id="1a668-104">Предоставляет определения представления пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="1a668-104">Provides the definitions of the custom control view.</span></span> <span data-ttu-id="1a668-105">В представлении пользовательского элемента управления должно быть указано одно или несколько определений.</span><span class="sxs-lookup"><span data-stu-id="1a668-105">The custom control view must specify one or more definitions.</span></span>

<span data-ttu-id="1a668-106">Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) ошибка customcontrol элемент (Format) Кустоментриес для ошибка customcontrol для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="1a668-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="1a668-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1a668-107">Syntax</span></span>

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1a668-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1a668-108">Attributes and Elements</span></span>

<span data-ttu-id="1a668-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `CustomControlEntries` элемента.</span><span class="sxs-lookup"><span data-stu-id="1a668-109">The following sections describe attributes, child elements, and the parent element of the `CustomControlEntries` element.</span></span> <span data-ttu-id="1a668-110">Необходимо указать один или несколько дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="1a668-110">You must specify one or more child elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="1a668-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1a668-111">Attributes</span></span>

<span data-ttu-id="1a668-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="1a668-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1a668-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1a668-113">Child Elements</span></span>

|<span data-ttu-id="1a668-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="1a668-114">Element</span></span>|<span data-ttu-id="1a668-115">Описание</span><span class="sxs-lookup"><span data-stu-id="1a668-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1a668-116">Элемент Кустоментри для Кустоментриес для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="1a668-116">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|<span data-ttu-id="1a668-117">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="1a668-117">Required element.</span></span><br /><br /> <span data-ttu-id="1a668-118">Предоставляет определение представления пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="1a668-118">Provides a definition of the custom control view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="1a668-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1a668-119">Parent Elements</span></span>

|<span data-ttu-id="1a668-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="1a668-120">Element</span></span>|<span data-ttu-id="1a668-121">Описание</span><span class="sxs-lookup"><span data-stu-id="1a668-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1a668-122">Элемент CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="1a668-122">CustomControl Element for View (Format)</span></span>](./customcontrol-element-for-view-format.md)|<span data-ttu-id="1a668-123">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="1a668-123">Required element.</span></span><br /><br /> <span data-ttu-id="1a668-124">Определяет формат пользовательского элемента управления для представления.</span><span class="sxs-lookup"><span data-stu-id="1a668-124">Defines a custom control format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="1a668-125">Комментарии</span><span class="sxs-lookup"><span data-stu-id="1a668-125">Remarks</span></span>

<span data-ttu-id="1a668-126">В большинстве случаев элемент управления имеет только одно определение, которое определено в одном `CustomEntry` элементе.</span><span class="sxs-lookup"><span data-stu-id="1a668-126">In most cases, a control has only one definition, which is defined in a single `CustomEntry` element.</span></span> <span data-ttu-id="1a668-127">Однако существует несколько определений, если вы хотите использовать один и тот же элемент управления для вывода различных объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="1a668-127">However it is possible to have multiple definitions if you want to use the same control to display different .NET objects.</span></span> <span data-ttu-id="1a668-128">В таких случаях можно определить `CustomEntry` элемент для каждого объекта или набора объектов.</span><span class="sxs-lookup"><span data-stu-id="1a668-128">In those cases, you can define a `CustomEntry` element for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="1a668-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="1a668-129">See Also</span></span>

[<span data-ttu-id="1a668-130">Элемент CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="1a668-130">CustomControl Element for View (Format)</span></span>](./customcontrol-element-for-view-format.md)

[<span data-ttu-id="1a668-131">Элемент Кустоментри для Кустоментриес для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="1a668-131">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[<span data-ttu-id="1a668-132">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="1a668-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
