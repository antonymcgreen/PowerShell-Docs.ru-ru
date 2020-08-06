---
title: Элемент Configuration (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 90be02f8e27c0bd391e01da1a08ecd8eeb29b84c
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783846"
---
# <a name="configuration-element-format"></a><span data-ttu-id="d4f9f-102">Элемент Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="d4f9f-102">Configuration Element (Format)</span></span>

<span data-ttu-id="d4f9f-103">Представляет элемент верхнего уровня файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="d4f9f-103">Represents the top-level element of a formatting file.</span></span>

<span data-ttu-id="d4f9f-104">Элемент настройки</span><span class="sxs-lookup"><span data-stu-id="d4f9f-104">Configuration Element</span></span>

## <a name="syntax"></a><span data-ttu-id="d4f9f-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d4f9f-105">Syntax</span></span>

```xml
<Configuration>
  <DefaultSettings>...</DefaultSettings>
  <SelectionSets>...</SelectionSets>
  <Controls>...</Controls>
  <ViewDefinitions>...</ViewDefinitions>
</Configuration>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="d4f9f-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d4f9f-106">Attributes and Elements</span></span>

<span data-ttu-id="d4f9f-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `Configuration` элемента.</span><span class="sxs-lookup"><span data-stu-id="d4f9f-107">The following sections describe the attributes, child elements, and the parent element of the `Configuration` element.</span></span> <span data-ttu-id="d4f9f-108">Этот элемент должен быть корневым элементом для каждого файла форматирования, и этот элемент должен содержать по крайней мере один дочерний элемент.</span><span class="sxs-lookup"><span data-stu-id="d4f9f-108">This element must be the root element for each formatting file, and this element must contain at least one child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d4f9f-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d4f9f-109">Attributes</span></span>

<span data-ttu-id="d4f9f-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d4f9f-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d4f9f-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d4f9f-111">Child Elements</span></span>

|<span data-ttu-id="d4f9f-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="d4f9f-112">Element</span></span>|<span data-ttu-id="d4f9f-113">Description</span><span class="sxs-lookup"><span data-stu-id="d4f9f-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d4f9f-114">Элемент Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="d4f9f-114">Controls Element for Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)|<span data-ttu-id="d4f9f-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d4f9f-115">Optional element.</span></span><br /><br /> <span data-ttu-id="d4f9f-116">Определяет общие элементы управления, которые могут использоваться всеми представлениями файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="d4f9f-116">Defines the common controls that can be used by all views of the formatting file.</span></span>|
|[<span data-ttu-id="d4f9f-117">Элемент DefaultSettings (формат)</span><span class="sxs-lookup"><span data-stu-id="d4f9f-117">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)|<span data-ttu-id="d4f9f-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d4f9f-118">Optional element.</span></span><br /><br /> <span data-ttu-id="d4f9f-119">Определяет общие параметры, которые применяются ко всем представлениям файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="d4f9f-119">Defines common settings that apply to all the views of the formatting file.</span></span>|
|[<span data-ttu-id="d4f9f-120">Формат элемента Селектионсетс</span><span class="sxs-lookup"><span data-stu-id="d4f9f-120">SelectionSets Element Format</span></span>](./selectionsets-element-format.md)|<span data-ttu-id="d4f9f-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d4f9f-121">Optional element.</span></span><br /><br /> <span data-ttu-id="d4f9f-122">Определяет общие наборы объектов .NET, которые могут использоваться всеми представлениями файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="d4f9f-122">Defines the common sets of .NET objects that can be used by all views of the formatting file.</span></span>|
|[<span data-ttu-id="d4f9f-123">Элемент ViewDefinitions (формат)</span><span class="sxs-lookup"><span data-stu-id="d4f9f-123">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)|<span data-ttu-id="d4f9f-124">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d4f9f-124">Optional element.</span></span><br /><br /> <span data-ttu-id="d4f9f-125">Определяет представления, используемые для отображения объектов.</span><span class="sxs-lookup"><span data-stu-id="d4f9f-125">Defines the views used to display objects.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="d4f9f-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d4f9f-126">Parent Elements</span></span>

<span data-ttu-id="d4f9f-127">Нет.</span><span class="sxs-lookup"><span data-stu-id="d4f9f-127">None.</span></span>

## <a name="remarks"></a><span data-ttu-id="d4f9f-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="d4f9f-128">Remarks</span></span>

<span data-ttu-id="d4f9f-129">Файлы форматирования определяют, как отображаются объекты.</span><span class="sxs-lookup"><span data-stu-id="d4f9f-129">Formatting files define how objects are displayed.</span></span> <span data-ttu-id="d4f9f-130">В большинстве случаев этот корневой элемент содержит элемент [виевдефинитионс](./viewdefinitions-element-format.md) , определяющий таблицу, список и широкие представления файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="d4f9f-130">In most cases, this root element contains a [ViewDefinitions](./viewdefinitions-element-format.md) element that defines the table, list, and wide views of the formatting file.</span></span> <span data-ttu-id="d4f9f-131">В дополнение к определениям представлений файл форматирования может определять стандартные наборы, параметры и элементы управления, которые могут использоваться этими представлениями.</span><span class="sxs-lookup"><span data-stu-id="d4f9f-131">In addition to the view definitions, the formatting file can define common selection sets, settings, and controls that those views can use.</span></span>

## <a name="see-also"></a><span data-ttu-id="d4f9f-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="d4f9f-132">See Also</span></span>

[<span data-ttu-id="d4f9f-133">Элемент Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="d4f9f-133">Controls Element for Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)

[<span data-ttu-id="d4f9f-134">Элемент DefaultSettings (формат)</span><span class="sxs-lookup"><span data-stu-id="d4f9f-134">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)

[<span data-ttu-id="d4f9f-135">Элемент SelectionSets (формат)</span><span class="sxs-lookup"><span data-stu-id="d4f9f-135">SelectionSets Element (Format)</span></span>](./selectionsets-element-format.md)

[<span data-ttu-id="d4f9f-136">Элемент ViewDefinitions (формат)</span><span class="sxs-lookup"><span data-stu-id="d4f9f-136">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)

[<span data-ttu-id="d4f9f-137">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="d4f9f-137">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
