---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент CustomEntries для элемента CustomControl для элемента Controls для элемента Configuration (формат)
description: Элемент CustomEntries для элемента CustomControl для элемента Controls для элемента Configuration (формат)
ms.openlocfilehash: 86c2b517d0d7075a355a3190a14e25d9dd4fe374
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655404"
---
# <a name="customentries-element-for-customcontrol-for-controls-for-configuration-format"></a><span data-ttu-id="793e1-103">Элемент CustomEntries для элемента CustomControl для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="793e1-103">CustomEntries Element for CustomControl for Controls for Configuration (Format)</span></span>

<span data-ttu-id="793e1-104">Предоставляет определения общего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="793e1-104">Provides the definitions of a common control.</span></span> <span data-ttu-id="793e1-105">Этот элемент используется при определении общего элемента управления, который может использоваться всеми представлениями в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="793e1-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="793e1-106">Элемент Configuration (Format) управляет элементом контрольного элемента конфигурации (Format) элементов управления для элемента управления конфигурации (Format) ошибка customcontrol для элемента Control в конфигурации (Format) Кустоментриес для ошибка customcontrol для конфигурации (Format).</span><span class="sxs-lookup"><span data-stu-id="793e1-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="793e1-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="793e1-107">Syntax</span></span>

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="793e1-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="793e1-108">Attributes and Elements</span></span>

<span data-ttu-id="793e1-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `CustomEntries` элемента.</span><span class="sxs-lookup"><span data-stu-id="793e1-109">The following sections describe attributes, child elements, and the parent element of the `CustomEntries` element.</span></span> <span data-ttu-id="793e1-110">Необходимо указать один или несколько дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="793e1-110">You must specify one or more child elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="793e1-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="793e1-111">Attributes</span></span>

<span data-ttu-id="793e1-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="793e1-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="793e1-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="793e1-113">Child Elements</span></span>

|<span data-ttu-id="793e1-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="793e1-114">Element</span></span>|<span data-ttu-id="793e1-115">Описание</span><span class="sxs-lookup"><span data-stu-id="793e1-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="793e1-116">Элемент CustomEntry для элемента CustomControl для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="793e1-116">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="793e1-117">Предоставляет определение общего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="793e1-117">Provides a definition of the common control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="793e1-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="793e1-118">Parent Elements</span></span>

|<span data-ttu-id="793e1-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="793e1-119">Element</span></span>|<span data-ttu-id="793e1-120">Описание</span><span class="sxs-lookup"><span data-stu-id="793e1-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="793e1-121">Элемент ошибка customcontrol для элемента управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="793e1-121">CustomControl Element for Control for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)|<span data-ttu-id="793e1-122">Определяет общий элемент управления.</span><span class="sxs-lookup"><span data-stu-id="793e1-122">Defines a common control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="793e1-123">Комментарии</span><span class="sxs-lookup"><span data-stu-id="793e1-123">Remarks</span></span>

<span data-ttu-id="793e1-124">В большинстве случаев элемент управления имеет только одно определение, которое определено в одном `CustomEntry` элементе.</span><span class="sxs-lookup"><span data-stu-id="793e1-124">In most cases, a control has only one definition, which is defined in a single `CustomEntry` element.</span></span> <span data-ttu-id="793e1-125">Однако существует несколько определений, если вы хотите использовать один и тот же элемент управления для вывода различных объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="793e1-125">However it is possible to have multiple definitions if you want to use the same control to display different .NET objects.</span></span> <span data-ttu-id="793e1-126">В таких случаях можно определить `CustomEntry` элемент для каждого объекта или набора объектов.</span><span class="sxs-lookup"><span data-stu-id="793e1-126">In those cases, you can define a `CustomEntry` element for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="793e1-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="793e1-127">See Also</span></span>

[<span data-ttu-id="793e1-128">Элемент ошибка customcontrol для элемента управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="793e1-128">CustomControl Element for Control for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="793e1-129">Элемент CustomEntry для элемента CustomControl для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="793e1-129">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)

[<span data-ttu-id="793e1-130">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="793e1-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
