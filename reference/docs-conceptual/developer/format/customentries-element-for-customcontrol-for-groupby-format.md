---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент CustomEntries для элемента CustomControl для элемента GroupBy (формат)
description: Элемент CustomEntries для элемента CustomControl для элемента GroupBy (формат)
ms.openlocfilehash: cde59d38b83930cb64a3a0040891783e4ab96723
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666796"
---
# <a name="customentries-element-for-customcontrol-for-groupby-format"></a><span data-ttu-id="5448b-103">Элемент CustomEntries для элемента CustomControl для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="5448b-103">CustomEntries Element for CustomControl for GroupBy (Format)</span></span>

<span data-ttu-id="5448b-104">Предоставляет определения для элемента управления.</span><span class="sxs-lookup"><span data-stu-id="5448b-104">Provides the definitions for the control.</span></span> <span data-ttu-id="5448b-105">Этот элемент используется при определении того, как отображается новая группа объектов.</span><span class="sxs-lookup"><span data-stu-id="5448b-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="5448b-106">Элемент Configuration (Format) Виевдефинитионс элемент представления (Format) элемент GroupBy для элемента представления (Format) ошибка customcontrol для элемента GroupBy (Format) Кустоментриес для ошибка customcontrol для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="5448b-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="5448b-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5448b-107">Syntax</span></span>

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5448b-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5448b-108">Attributes and Elements</span></span>

<span data-ttu-id="5448b-109">В следующих разделах описываются атрибуты, дочерние элементы и родительские элементы `CustomEntries` элемента.</span><span class="sxs-lookup"><span data-stu-id="5448b-109">The following sections describe attributes, child elements, and parent elements of the `CustomEntries` element.</span></span> <span data-ttu-id="5448b-110">Максимальное количество дочерних элементов, которое можно указать, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="5448b-110">There is no maximum limit to the number of child elements that can be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="5448b-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5448b-111">Attributes</span></span>

<span data-ttu-id="5448b-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5448b-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5448b-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5448b-113">Child Elements</span></span>

|<span data-ttu-id="5448b-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="5448b-114">Element</span></span>|<span data-ttu-id="5448b-115">Описание</span><span class="sxs-lookup"><span data-stu-id="5448b-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5448b-116">Элемент CustomEntry для элемента CustomControl для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="5448b-116">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>](./customentry-element-for-customcontrol-for-groupby-format.md)|<span data-ttu-id="5448b-117">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="5448b-117">Required element.</span></span><br /><br /> <span data-ttu-id="5448b-118">Предоставляет определение элемента управления.</span><span class="sxs-lookup"><span data-stu-id="5448b-118">Provides a definition of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="5448b-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5448b-119">Parent Elements</span></span>

|<span data-ttu-id="5448b-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="5448b-120">Element</span></span>|<span data-ttu-id="5448b-121">Описание</span><span class="sxs-lookup"><span data-stu-id="5448b-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5448b-122">Элемент CustomControl для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="5448b-122">CustomControl Element for GroupBy (Format)</span></span>](./customcontrol-element-for-groupby-format.md)|<span data-ttu-id="5448b-123">Определяет пользовательский элемент управления, отображающий новую группу.</span><span class="sxs-lookup"><span data-stu-id="5448b-123">Defines the custom control that displays the new group.</span></span>|

## <a name="remarks"></a><span data-ttu-id="5448b-124">Комментарии</span><span class="sxs-lookup"><span data-stu-id="5448b-124">Remarks</span></span>

<span data-ttu-id="5448b-125">В большинстве случаев элемент управления имеет только одно определение, которое указывается в одном `CustomEntry` элементе.</span><span class="sxs-lookup"><span data-stu-id="5448b-125">In most cases, a control has only one definition, which is specified in a single `CustomEntry` element.</span></span> <span data-ttu-id="5448b-126">Однако можно предоставить несколько определений, если вы хотите использовать один и тот же элемент управления для вывода различных групп.</span><span class="sxs-lookup"><span data-stu-id="5448b-126">However, it is possible to provide multiple definitions if you want to use the same control to display different groups.</span></span> <span data-ttu-id="5448b-127">В таких случаях можно определить `CustomEntry` элемент для группы.</span><span class="sxs-lookup"><span data-stu-id="5448b-127">In those cases, you can define a `CustomEntry` element for a group.</span></span>

## <a name="see-also"></a><span data-ttu-id="5448b-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="5448b-128">See Also</span></span>

[<span data-ttu-id="5448b-129">Элемент CustomEntry для элемента CustomEntries для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="5448b-129">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)

[<span data-ttu-id="5448b-130">Элемент CustomControl для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="5448b-130">CustomControl Element for GroupBy (Format)</span></span>](./customcontrol-element-for-groupby-format.md)

[<span data-ttu-id="5448b-131">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="5448b-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
