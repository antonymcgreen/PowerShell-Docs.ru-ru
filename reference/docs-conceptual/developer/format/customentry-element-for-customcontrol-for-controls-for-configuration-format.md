---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент CustomEntry для элемента CustomControl для элемента Controls для элемента Configuration (формат)
description: Элемент CustomEntry для элемента CustomControl для элемента Controls для элемента Configuration (формат)
ms.openlocfilehash: 3967be86a1d6c12c7215ef19d50bac9fafd5ad6d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648276"
---
# <a name="customentry-element-for-customcontrol-for-controls-for-configuration-format"></a><span data-ttu-id="42827-103">Элемент CustomEntry для элемента CustomControl для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="42827-103">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>

<span data-ttu-id="42827-104">Предоставляет определение общего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="42827-104">Provides a definition of the common control.</span></span> <span data-ttu-id="42827-105">Этот элемент используется при определении общего элемента управления, который может использоваться всеми представлениями в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="42827-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="42827-106">Элемент Configuration (Format) управляет элементом контрольного элемента конфигурации (Format) элементов управления для элемента управления конфигурации (Format) ошибка customcontrol для элемента Control (формат) Кустоментриес для ошибка customcontrol для элемента Configuration (формат) Кустоментри для ошибка customcontrol для элементов управления конфигурации (Format).</span><span class="sxs-lookup"><span data-stu-id="42827-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="42827-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="42827-107">Syntax</span></span>

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="42827-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="42827-108">Attributes and Elements</span></span>

<span data-ttu-id="42827-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `CustomEntry` элемента.</span><span class="sxs-lookup"><span data-stu-id="42827-109">The following sections describe attributes, child elements, and the parent element of the `CustomEntry` element.</span></span> <span data-ttu-id="42827-110">Необходимо указать элементы, отображаемые в определении.</span><span class="sxs-lookup"><span data-stu-id="42827-110">You must specify the items displayed by the definition.</span></span>

### <a name="attributes"></a><span data-ttu-id="42827-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="42827-111">Attributes</span></span>

<span data-ttu-id="42827-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="42827-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="42827-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="42827-113">Child Elements</span></span>

|<span data-ttu-id="42827-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="42827-114">Element</span></span>|<span data-ttu-id="42827-115">Описание</span><span class="sxs-lookup"><span data-stu-id="42827-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="42827-116">Элемент EntrySelectedBy для элемента CustomEntry для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="42827-116">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="42827-117">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="42827-117">Optional element.</span></span><br /><br /> <span data-ttu-id="42827-118">Определяет типы .NET, использующие определение общего элемента управления или условие, которое должно существовать для использования этого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="42827-118">Defines the .NET types that use the definition of the common control or the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="42827-119">Элемент Кустомитем для Кустоментри элементов управления для конфигурации</span><span class="sxs-lookup"><span data-stu-id="42827-119">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="42827-120">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="42827-120">Required element.</span></span><br /><br /> <span data-ttu-id="42827-121">Определяет, какие данные отображаются элементом управления и как они отображаются.</span><span class="sxs-lookup"><span data-stu-id="42827-121">Defines what data is displayed by the control and how it is displayed.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="42827-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="42827-122">Parent Elements</span></span>

|<span data-ttu-id="42827-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="42827-123">Element</span></span>|<span data-ttu-id="42827-124">Описание</span><span class="sxs-lookup"><span data-stu-id="42827-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="42827-125">Элемент Кустоментриес для ошибка customcontrol конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="42827-125">CustomEntries Element for CustomControl for Configuration (Format)</span></span>](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="42827-126">Предоставляет определения общего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="42827-126">Provides the definitions of the common control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="42827-127">Комментарии</span><span class="sxs-lookup"><span data-stu-id="42827-127">Remarks</span></span>

<span data-ttu-id="42827-128">В большинстве случаев для каждого общего пользовательского элемента управления требуется только одно определение, но существует несколько определений, если вы хотите использовать один и тот же элемент управления для вывода различных объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="42827-128">In most cases, only one definition is required for each common custom control, but it is possible to have multiple definitions if you want to use the same control to display different .NET objects.</span></span> <span data-ttu-id="42827-129">В таких случаях можно указать отдельное определение для каждого объекта или набора объектов.</span><span class="sxs-lookup"><span data-stu-id="42827-129">In those cases, you can provide a separate definition for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="42827-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="42827-130">See Also</span></span>

[<span data-ttu-id="42827-131">Элемент Кустоментриес для ошибка customcontrol конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="42827-131">CustomEntries Element for CustomControl for Configuration (Format)</span></span>](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)

[<span data-ttu-id="42827-132">Элемент Кустомитем для Кустоментри элементов управления для конфигурации</span><span class="sxs-lookup"><span data-stu-id="42827-132">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="42827-133">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="42827-133">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
