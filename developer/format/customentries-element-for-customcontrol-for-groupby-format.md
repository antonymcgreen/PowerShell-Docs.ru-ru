---
title: Элемент CustomEntries для пользовательский элемент управления для GroupBy (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: af83c0f6-7fdd-4aa0-af12-efc62f632974
caps.latest.revision: 7
ms.openlocfilehash: f073142bf836ae892f161cf8c36ed16c35e311f5
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853680"
---
# <a name="customentries-element-for-customcontrol-for-groupby-format"></a><span data-ttu-id="5751c-102">Элемент CustomEntries для элемента CustomControl для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="5751c-102">CustomEntries Element for CustomControl for GroupBy (Format)</span></span>

<span data-ttu-id="5751c-103">Предоставляет определения для элемента управления.</span><span class="sxs-lookup"><span data-stu-id="5751c-103">Provides the definitions for the control.</span></span> <span data-ttu-id="5751c-104">Этот элемент используется при определении того, как отображается группу объектов.</span><span class="sxs-lookup"><span data-stu-id="5751c-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="5751c-105">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) GroupBy элемента конфигурации для элемента представления (формат) пользовательский элемент управления для элемента CustomEntries GroupBy (формат) пользовательский элемент управления для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="5751c-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="5751c-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5751c-106">Syntax</span></span>

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5751c-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5751c-107">Attributes and Elements</span></span>

<span data-ttu-id="5751c-108">В следующих разделах атрибуты, дочерние и родительские элементы из `CustomEntries` элемент.</span><span class="sxs-lookup"><span data-stu-id="5751c-108">The following sections describe attributes, child elements, and parent elements of the `CustomEntries` element.</span></span> <span data-ttu-id="5751c-109">Не ограничено максимальное число дочерних элементов, которые могут быть указаны.</span><span class="sxs-lookup"><span data-stu-id="5751c-109">There is no maximum limit to the number of child elements that can be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="5751c-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5751c-110">Attributes</span></span>

<span data-ttu-id="5751c-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="5751c-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5751c-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5751c-112">Child Elements</span></span>

|<span data-ttu-id="5751c-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="5751c-113">Element</span></span>|<span data-ttu-id="5751c-114">Описание</span><span class="sxs-lookup"><span data-stu-id="5751c-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5751c-115">Элемент CustomEntry для пользовательский элемент управления для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="5751c-115">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>](./customentry-element-for-customcontrol-for-groupby-format.md)|<span data-ttu-id="5751c-116">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="5751c-116">Required element.</span></span><br /><br /> <span data-ttu-id="5751c-117">Предоставляет определение элемента управления.</span><span class="sxs-lookup"><span data-stu-id="5751c-117">Provides a definition of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="5751c-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5751c-118">Parent Elements</span></span>

|<span data-ttu-id="5751c-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="5751c-119">Element</span></span>|<span data-ttu-id="5751c-120">Описание</span><span class="sxs-lookup"><span data-stu-id="5751c-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5751c-121">Пользовательский элемент управления-элемент для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="5751c-121">CustomControl Element for GroupBy (Format)</span></span>](./customcontrol-element-for-groupby-format.md)|<span data-ttu-id="5751c-122">Определяет пользовательский элемент управления, отображающий новой группы.</span><span class="sxs-lookup"><span data-stu-id="5751c-122">Defines the custom control that displays the new group.</span></span>|

## <a name="remarks"></a><span data-ttu-id="5751c-123">Замечания</span><span class="sxs-lookup"><span data-stu-id="5751c-123">Remarks</span></span>

<span data-ttu-id="5751c-124">В большинстве случаев элемент управления имеет только одно определение, которое указано в одном `CustomEntry` элемент.</span><span class="sxs-lookup"><span data-stu-id="5751c-124">In most cases, a control has only one definition, which is specified in a single `CustomEntry` element.</span></span> <span data-ttu-id="5751c-125">Тем не менее можно указать несколько определений, если вы хотите использовать тот же элемент управления для отображения различных групп.</span><span class="sxs-lookup"><span data-stu-id="5751c-125">However, it is possible to provide multiple definitions if you want to use the same control to display different groups.</span></span> <span data-ttu-id="5751c-126">В таких случаях можно определить `CustomEntry` элемента для группы.</span><span class="sxs-lookup"><span data-stu-id="5751c-126">In those cases, you can define a `CustomEntry` element for a group.</span></span>

## <a name="see-also"></a><span data-ttu-id="5751c-127">См. также</span><span class="sxs-lookup"><span data-stu-id="5751c-127">See Also</span></span>

[<span data-ttu-id="5751c-128">Элемент CustomEntry для CustomEntries для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="5751c-128">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)

[<span data-ttu-id="5751c-129">Пользовательский элемент управления-элемент для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="5751c-129">CustomControl Element for GroupBy (Format)</span></span>](./customcontrol-element-for-groupby-format.md)

[<span data-ttu-id="5751c-130">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="5751c-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
