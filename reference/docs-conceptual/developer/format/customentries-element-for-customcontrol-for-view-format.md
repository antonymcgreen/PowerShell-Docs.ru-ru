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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364083"
---
# <a name="customentries-element-for-customcontrol-for-view-format"></a><span data-ttu-id="c57de-102">Элемент CustomEntries для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="c57de-102">CustomEntries Element for CustomControl for View (Format)</span></span>

<span data-ttu-id="c57de-103">Предоставляет определения представления пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="c57de-103">Provides the definitions of the custom control view.</span></span> <span data-ttu-id="c57de-104">В представлении пользовательского элемента управления должно быть указано одно или несколько определений.</span><span class="sxs-lookup"><span data-stu-id="c57de-104">The custom control view must specify one or more definitions.</span></span>

<span data-ttu-id="c57de-105">Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) ошибка customcontrol элемент (Format) Кустоментриес для ошибка customcontrol для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="c57de-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c57de-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c57de-106">Syntax</span></span>

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c57de-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c57de-107">Attributes and Elements</span></span>

<span data-ttu-id="c57de-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `CustomControlEntries`.</span><span class="sxs-lookup"><span data-stu-id="c57de-108">The following sections describe attributes, child elements, and the parent element of the `CustomControlEntries` element.</span></span> <span data-ttu-id="c57de-109">Необходимо указать один или несколько дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="c57de-109">You must specify one or more child elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="c57de-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c57de-110">Attributes</span></span>

<span data-ttu-id="c57de-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="c57de-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c57de-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c57de-112">Child Elements</span></span>

|<span data-ttu-id="c57de-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="c57de-113">Element</span></span>|<span data-ttu-id="c57de-114">Описание</span><span class="sxs-lookup"><span data-stu-id="c57de-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c57de-115">Элемент Кустоментри для Кустоментриес для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="c57de-115">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|<span data-ttu-id="c57de-116">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="c57de-116">Required element.</span></span><br /><br /> <span data-ttu-id="c57de-117">Предоставляет определение представления пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="c57de-117">Provides a definition of the custom control view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="c57de-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c57de-118">Parent Elements</span></span>

|<span data-ttu-id="c57de-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="c57de-119">Element</span></span>|<span data-ttu-id="c57de-120">Описание</span><span class="sxs-lookup"><span data-stu-id="c57de-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c57de-121">Элемент ошибка customcontrol для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="c57de-121">CustomControl Element for View (Format)</span></span>](./customcontrol-element-for-view-format.md)|<span data-ttu-id="c57de-122">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="c57de-122">Required element.</span></span><br /><br /> <span data-ttu-id="c57de-123">Определяет формат пользовательского элемента управления для представления.</span><span class="sxs-lookup"><span data-stu-id="c57de-123">Defines a custom control format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="c57de-124">Замечания</span><span class="sxs-lookup"><span data-stu-id="c57de-124">Remarks</span></span>

<span data-ttu-id="c57de-125">В большинстве случаев элемент управления имеет только одно определение, которое определено в одном элементе `CustomEntry`.</span><span class="sxs-lookup"><span data-stu-id="c57de-125">In most cases, a control has only one definition, which is defined in a single `CustomEntry` element.</span></span> <span data-ttu-id="c57de-126">Однако существует несколько определений, если вы хотите использовать один и тот же элемент управления для вывода различных объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="c57de-126">However it is possible to have multiple definitions if you want to use the same control to display different .NET objects.</span></span> <span data-ttu-id="c57de-127">В таких случаях можно определить элемент `CustomEntry` для каждого объекта или набора объектов.</span><span class="sxs-lookup"><span data-stu-id="c57de-127">In those cases, you can define a `CustomEntry` element for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="c57de-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="c57de-128">See Also</span></span>

[<span data-ttu-id="c57de-129">Элемент ошибка customcontrol для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="c57de-129">CustomControl Element for View (Format)</span></span>](./customcontrol-element-for-view-format.md)

[<span data-ttu-id="c57de-130">Элемент Кустоментри для Кустоментриес для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="c57de-130">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[<span data-ttu-id="c57de-131">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="c57de-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
