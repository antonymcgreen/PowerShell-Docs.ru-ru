---
title: Элемент Кустоментриес для ошибка customcontrol для GroupBy (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 2221d1bb94159697ff10466e4606d6d54e117e30
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785954"
---
# <a name="customentries-element-for-customcontrol-for-groupby-format"></a><span data-ttu-id="f8da6-102">Элемент CustomEntries для элемента CustomControl для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="f8da6-102">CustomEntries Element for CustomControl for GroupBy (Format)</span></span>

<span data-ttu-id="f8da6-103">Предоставляет определения для элемента управления.</span><span class="sxs-lookup"><span data-stu-id="f8da6-103">Provides the definitions for the control.</span></span> <span data-ttu-id="f8da6-104">Этот элемент используется при определении того, как отображается новая группа объектов.</span><span class="sxs-lookup"><span data-stu-id="f8da6-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="f8da6-105">Элемент Configuration (Format) Виевдефинитионс элемент представления (Format) элемент GroupBy для элемента представления (Format) ошибка customcontrol для элемента GroupBy (Format) Кустоментриес для ошибка customcontrol для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="f8da6-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f8da6-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f8da6-106">Syntax</span></span>

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f8da6-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f8da6-107">Attributes and Elements</span></span>

<span data-ttu-id="f8da6-108">В следующих разделах описываются атрибуты, дочерние элементы и родительские элементы `CustomEntries` элемента.</span><span class="sxs-lookup"><span data-stu-id="f8da6-108">The following sections describe attributes, child elements, and parent elements of the `CustomEntries` element.</span></span> <span data-ttu-id="f8da6-109">Максимальное количество дочерних элементов, которое можно указать, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="f8da6-109">There is no maximum limit to the number of child elements that can be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="f8da6-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f8da6-110">Attributes</span></span>

<span data-ttu-id="f8da6-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f8da6-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f8da6-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f8da6-112">Child Elements</span></span>

|<span data-ttu-id="f8da6-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="f8da6-113">Element</span></span>|<span data-ttu-id="f8da6-114">Описание</span><span class="sxs-lookup"><span data-stu-id="f8da6-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f8da6-115">Элемент CustomEntry для элемента CustomControl для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="f8da6-115">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>](./customentry-element-for-customcontrol-for-groupby-format.md)|<span data-ttu-id="f8da6-116">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="f8da6-116">Required element.</span></span><br /><br /> <span data-ttu-id="f8da6-117">Предоставляет определение элемента управления.</span><span class="sxs-lookup"><span data-stu-id="f8da6-117">Provides a definition of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="f8da6-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f8da6-118">Parent Elements</span></span>

|<span data-ttu-id="f8da6-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="f8da6-119">Element</span></span>|<span data-ttu-id="f8da6-120">Описание</span><span class="sxs-lookup"><span data-stu-id="f8da6-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f8da6-121">Элемент CustomControl для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="f8da6-121">CustomControl Element for GroupBy (Format)</span></span>](./customcontrol-element-for-groupby-format.md)|<span data-ttu-id="f8da6-122">Определяет пользовательский элемент управления, отображающий новую группу.</span><span class="sxs-lookup"><span data-stu-id="f8da6-122">Defines the custom control that displays the new group.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f8da6-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="f8da6-123">Remarks</span></span>

<span data-ttu-id="f8da6-124">В большинстве случаев элемент управления имеет только одно определение, которое указывается в одном `CustomEntry` элементе.</span><span class="sxs-lookup"><span data-stu-id="f8da6-124">In most cases, a control has only one definition, which is specified in a single `CustomEntry` element.</span></span> <span data-ttu-id="f8da6-125">Однако можно предоставить несколько определений, если вы хотите использовать один и тот же элемент управления для вывода различных групп.</span><span class="sxs-lookup"><span data-stu-id="f8da6-125">However, it is possible to provide multiple definitions if you want to use the same control to display different groups.</span></span> <span data-ttu-id="f8da6-126">В таких случаях можно определить `CustomEntry` элемент для группы.</span><span class="sxs-lookup"><span data-stu-id="f8da6-126">In those cases, you can define a `CustomEntry` element for a group.</span></span>

## <a name="see-also"></a><span data-ttu-id="f8da6-127">См. также</span><span class="sxs-lookup"><span data-stu-id="f8da6-127">See Also</span></span>

[<span data-ttu-id="f8da6-128">Элемент CustomEntry для элемента CustomEntries для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="f8da6-128">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)

[<span data-ttu-id="f8da6-129">Элемент CustomControl для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="f8da6-129">CustomControl Element for GroupBy (Format)</span></span>](./customcontrol-element-for-groupby-format.md)

[<span data-ttu-id="f8da6-130">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="f8da6-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
