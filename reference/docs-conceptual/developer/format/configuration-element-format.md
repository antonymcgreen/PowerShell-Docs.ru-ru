---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент Configuration (формат)
description: Элемент Configuration (формат)
ms.openlocfilehash: 0524736d40dd7a7acb0b6fb61d1438b75672c240
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655694"
---
# <a name="configuration-element-format"></a><span data-ttu-id="30788-103">Элемент Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="30788-103">Configuration Element (Format)</span></span>

<span data-ttu-id="30788-104">Представляет элемент верхнего уровня файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="30788-104">Represents the top-level element of a formatting file.</span></span>

<span data-ttu-id="30788-105">Элемент настройки</span><span class="sxs-lookup"><span data-stu-id="30788-105">Configuration Element</span></span>

## <a name="syntax"></a><span data-ttu-id="30788-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="30788-106">Syntax</span></span>

```xml
<Configuration>
  <DefaultSettings>...</DefaultSettings>
  <SelectionSets>...</SelectionSets>
  <Controls>...</Controls>
  <ViewDefinitions>...</ViewDefinitions>
</Configuration>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="30788-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="30788-107">Attributes and Elements</span></span>

<span data-ttu-id="30788-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `Configuration` элемента.</span><span class="sxs-lookup"><span data-stu-id="30788-108">The following sections describe the attributes, child elements, and the parent element of the `Configuration` element.</span></span> <span data-ttu-id="30788-109">Этот элемент должен быть корневым элементом для каждого файла форматирования, и этот элемент должен содержать по крайней мере один дочерний элемент.</span><span class="sxs-lookup"><span data-stu-id="30788-109">This element must be the root element for each formatting file, and this element must contain at least one child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="30788-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="30788-110">Attributes</span></span>

<span data-ttu-id="30788-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="30788-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="30788-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="30788-112">Child Elements</span></span>

|<span data-ttu-id="30788-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="30788-113">Element</span></span>|<span data-ttu-id="30788-114">Описание</span><span class="sxs-lookup"><span data-stu-id="30788-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="30788-115">Элемент Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="30788-115">Controls Element for Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)|<span data-ttu-id="30788-116">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="30788-116">Optional element.</span></span><br /><br /> <span data-ttu-id="30788-117">Определяет общие элементы управления, которые могут использоваться всеми представлениями файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="30788-117">Defines the common controls that can be used by all views of the formatting file.</span></span>|
|[<span data-ttu-id="30788-118">Элемент DefaultSettings (формат)</span><span class="sxs-lookup"><span data-stu-id="30788-118">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)|<span data-ttu-id="30788-119">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="30788-119">Optional element.</span></span><br /><br /> <span data-ttu-id="30788-120">Определяет общие параметры, которые применяются ко всем представлениям файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="30788-120">Defines common settings that apply to all the views of the formatting file.</span></span>|
|[<span data-ttu-id="30788-121">Формат элемента Селектионсетс</span><span class="sxs-lookup"><span data-stu-id="30788-121">SelectionSets Element Format</span></span>](./selectionsets-element-format.md)|<span data-ttu-id="30788-122">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="30788-122">Optional element.</span></span><br /><br /> <span data-ttu-id="30788-123">Определяет общие наборы объектов .NET, которые могут использоваться всеми представлениями файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="30788-123">Defines the common sets of .NET objects that can be used by all views of the formatting file.</span></span>|
|[<span data-ttu-id="30788-124">Элемент ViewDefinitions (формат)</span><span class="sxs-lookup"><span data-stu-id="30788-124">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)|<span data-ttu-id="30788-125">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="30788-125">Optional element.</span></span><br /><br /> <span data-ttu-id="30788-126">Определяет представления, используемые для отображения объектов.</span><span class="sxs-lookup"><span data-stu-id="30788-126">Defines the views used to display objects.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="30788-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="30788-127">Parent Elements</span></span>

<span data-ttu-id="30788-128">Нет.</span><span class="sxs-lookup"><span data-stu-id="30788-128">None.</span></span>

## <a name="remarks"></a><span data-ttu-id="30788-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="30788-129">Remarks</span></span>

<span data-ttu-id="30788-130">Файлы форматирования определяют, как отображаются объекты.</span><span class="sxs-lookup"><span data-stu-id="30788-130">Formatting files define how objects are displayed.</span></span> <span data-ttu-id="30788-131">В большинстве случаев этот корневой элемент содержит элемент [виевдефинитионс](./viewdefinitions-element-format.md) , определяющий таблицу, список и широкие представления файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="30788-131">In most cases, this root element contains a [ViewDefinitions](./viewdefinitions-element-format.md) element that defines the table, list, and wide views of the formatting file.</span></span> <span data-ttu-id="30788-132">В дополнение к определениям представлений файл форматирования может определять стандартные наборы, параметры и элементы управления, которые могут использоваться этими представлениями.</span><span class="sxs-lookup"><span data-stu-id="30788-132">In addition to the view definitions, the formatting file can define common selection sets, settings, and controls that those views can use.</span></span>

## <a name="see-also"></a><span data-ttu-id="30788-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="30788-133">See Also</span></span>

[<span data-ttu-id="30788-134">Элемент Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="30788-134">Controls Element for Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)

[<span data-ttu-id="30788-135">Элемент DefaultSettings (формат)</span><span class="sxs-lookup"><span data-stu-id="30788-135">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)

[<span data-ttu-id="30788-136">Элемент SelectionSets (формат)</span><span class="sxs-lookup"><span data-stu-id="30788-136">SelectionSets Element (Format)</span></span>](./selectionsets-element-format.md)

[<span data-ttu-id="30788-137">Элемент ViewDefinitions (формат)</span><span class="sxs-lookup"><span data-stu-id="30788-137">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)

[<span data-ttu-id="30788-138">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="30788-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
