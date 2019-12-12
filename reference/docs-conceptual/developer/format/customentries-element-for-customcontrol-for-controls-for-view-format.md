---
title: Элемент Кустоментриес для ошибка customcontrol элементов управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3485958a-ba87-4932-907c-a8f140c4abdb
caps.latest.revision: 8
ms.openlocfilehash: 4856aee930285781a101868bd6cb67824585bce1
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368813"
---
# <a name="customentries-element-for-customcontrol-for-controls-for-view-format"></a><span data-ttu-id="dc307-102">Элемент CustomEntries для элемента CustomControl для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="dc307-102">CustomEntries Element for CustomControl for Controls for View (Format)</span></span>

<span data-ttu-id="dc307-103">Предоставляет определения для элемента управления.</span><span class="sxs-lookup"><span data-stu-id="dc307-103">Provides the definitions for the control.</span></span> <span data-ttu-id="dc307-104">Этот элемент используется при определении элементов управления, которые могут использоваться представлением.</span><span class="sxs-lookup"><span data-stu-id="dc307-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="dc307-105">Элемент Configuration (Format) Виевдефинитионс элемент (формат) элемент представления (Format) управляет управляющий элемент (Format) элемент управления для элементов управления представления (Format) ошибка customcontrol для элементов управления элемента Кустоментриес представления (Format) для Ошибка customcontrol для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="dc307-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="dc307-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dc307-106">Syntax</span></span>

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="dc307-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="dc307-107">Attributes and Elements</span></span>

<span data-ttu-id="dc307-108">В следующих разделах описываются атрибуты, дочерние элементы и родительские элементы элемента `CustomEntries`.</span><span class="sxs-lookup"><span data-stu-id="dc307-108">The following sections describe attributes, child elements, and parent elements of the `CustomEntries` element.</span></span> <span data-ttu-id="dc307-109">Максимальное количество дочерних элементов, которое можно указать, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="dc307-109">There is no maximum limit to the number of child elements that can be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="dc307-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="dc307-110">Attributes</span></span>

<span data-ttu-id="dc307-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="dc307-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="dc307-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="dc307-112">Child Elements</span></span>

|<span data-ttu-id="dc307-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="dc307-113">Element</span></span>|<span data-ttu-id="dc307-114">Описание</span><span class="sxs-lookup"><span data-stu-id="dc307-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="dc307-115">Элемент Кустоментри для Кустоментриес элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="dc307-115">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)|<span data-ttu-id="dc307-116">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="dc307-116">Required element.</span></span><br /><br /> <span data-ttu-id="dc307-117">Предоставляет определение элемента управления.</span><span class="sxs-lookup"><span data-stu-id="dc307-117">Provides a definition of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="dc307-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="dc307-118">Parent Elements</span></span>

|<span data-ttu-id="dc307-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="dc307-119">Element</span></span>|<span data-ttu-id="dc307-120">Описание</span><span class="sxs-lookup"><span data-stu-id="dc307-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="dc307-121">Элемент ошибка customcontrol для элемента управления для элементов управления в представлении (формат)</span><span class="sxs-lookup"><span data-stu-id="dc307-121">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)|<span data-ttu-id="dc307-122">Определяет элемент управления, используемый представлением.</span><span class="sxs-lookup"><span data-stu-id="dc307-122">Defines the control used by the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="dc307-123">Замечания</span><span class="sxs-lookup"><span data-stu-id="dc307-123">Remarks</span></span>

<span data-ttu-id="dc307-124">В большинстве случаев элемент управления имеет только одно определение, которое указывается в одном элементе `CustomEntry`.</span><span class="sxs-lookup"><span data-stu-id="dc307-124">In most cases, a control has only one definition, which is specified in a single `CustomEntry` element.</span></span> <span data-ttu-id="dc307-125">Однако можно предоставить несколько определений, если вы хотите использовать один и тот же элемент управления для вывода различных объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="dc307-125">However, it is possible to provide multiple definitions if you want to use the same control to display different .NET objects.</span></span> <span data-ttu-id="dc307-126">В таких случаях можно определить элемент `CustomEntry` для каждого объекта или набора объектов.</span><span class="sxs-lookup"><span data-stu-id="dc307-126">In those cases, you can define a `CustomEntry` element for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="dc307-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="dc307-127">See Also</span></span>

[<span data-ttu-id="dc307-128">Элемент Кустоментри для Кустоментриес элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="dc307-128">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)

[<span data-ttu-id="dc307-129">Элемент ошибка customcontrol для элемента управления для элементов управления в представлении (формат)</span><span class="sxs-lookup"><span data-stu-id="dc307-129">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="dc307-130">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="dc307-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
