---
title: Элемент Кустоментриес для ошибка customcontrol для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cb412831-94f7-4054-b19e-32c1b14c66dd
caps.latest.revision: 11
ms.openlocfilehash: 827baacd22ef258dd9b0c8a383a23fce7d975f7f
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364083"
---
# <a name="customentries-element-for-customcontrol-for-view-format"></a><span data-ttu-id="51097-102">Элемент CustomEntries для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="51097-102">CustomEntries Element for CustomControl for View (Format)</span></span>

<span data-ttu-id="51097-103">Предоставляет определения представления пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="51097-103">Provides the definitions of the custom control view.</span></span> <span data-ttu-id="51097-104">В представлении пользовательского элемента управления должно быть указано одно или несколько определений.</span><span class="sxs-lookup"><span data-stu-id="51097-104">The custom control view must specify one or more definitions.</span></span>

<span data-ttu-id="51097-105">Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) ошибка customcontrol элемент (Format) Кустоментриес для ошибка customcontrol для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="51097-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="51097-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="51097-106">Syntax</span></span>

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="51097-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="51097-107">Attributes and Elements</span></span>

<span data-ttu-id="51097-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `CustomControlEntries`.</span><span class="sxs-lookup"><span data-stu-id="51097-108">The following sections describe attributes, child elements, and the parent element of the `CustomControlEntries` element.</span></span> <span data-ttu-id="51097-109">Необходимо указать один или несколько дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="51097-109">You must specify one or more child elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="51097-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="51097-110">Attributes</span></span>

<span data-ttu-id="51097-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="51097-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="51097-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="51097-112">Child Elements</span></span>

|<span data-ttu-id="51097-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="51097-113">Element</span></span>|<span data-ttu-id="51097-114">Описание</span><span class="sxs-lookup"><span data-stu-id="51097-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="51097-115">Элемент Кустоментри для Кустоментриес для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="51097-115">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|<span data-ttu-id="51097-116">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="51097-116">Required element.</span></span><br /><br /> <span data-ttu-id="51097-117">Предоставляет определение представления пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="51097-117">Provides a definition of the custom control view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="51097-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="51097-118">Parent Elements</span></span>

|<span data-ttu-id="51097-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="51097-119">Element</span></span>|<span data-ttu-id="51097-120">Описание</span><span class="sxs-lookup"><span data-stu-id="51097-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="51097-121">Элемент ошибка customcontrol для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="51097-121">CustomControl Element for View (Format)</span></span>](./customcontrol-element-for-view-format.md)|<span data-ttu-id="51097-122">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="51097-122">Required element.</span></span><br /><br /> <span data-ttu-id="51097-123">Определяет формат пользовательского элемента управления для представления.</span><span class="sxs-lookup"><span data-stu-id="51097-123">Defines a custom control format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="51097-124">Замечания</span><span class="sxs-lookup"><span data-stu-id="51097-124">Remarks</span></span>

<span data-ttu-id="51097-125">В большинстве случаев элемент управления имеет только одно определение, которое определено в одном элементе `CustomEntry`.</span><span class="sxs-lookup"><span data-stu-id="51097-125">In most cases, a control has only one definition, which is defined in a single `CustomEntry` element.</span></span> <span data-ttu-id="51097-126">Однако существует несколько определений, если вы хотите использовать один и тот же элемент управления для вывода различных объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="51097-126">However it is possible to have multiple definitions if you want to use the same control to display different .NET objects.</span></span> <span data-ttu-id="51097-127">В таких случаях можно определить элемент `CustomEntry` для каждого объекта или набора объектов.</span><span class="sxs-lookup"><span data-stu-id="51097-127">In those cases, you can define a `CustomEntry` element for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="51097-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="51097-128">See Also</span></span>

[<span data-ttu-id="51097-129">Элемент ошибка customcontrol для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="51097-129">CustomControl Element for View (Format)</span></span>](./customcontrol-element-for-view-format.md)

[<span data-ttu-id="51097-130">Элемент Кустоментри для Кустоментриес для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="51097-130">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[<span data-ttu-id="51097-131">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="51097-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
