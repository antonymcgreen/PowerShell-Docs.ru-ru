---
title: Элемент Configuration (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d46df0cb-50b7-4b81-82ba-37186a7b7a7f
caps.latest.revision: 28
ms.openlocfilehash: 296c63d0c774a0bf56e90dbaa32f2c221d4c3dbd
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363503"
---
# <a name="configuration-element-format"></a><span data-ttu-id="6c835-102">Элемент Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="6c835-102">Configuration Element (Format)</span></span>

<span data-ttu-id="6c835-103">Представляет элемент верхнего уровня файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="6c835-103">Represents the top-level element of a formatting file.</span></span>

<span data-ttu-id="6c835-104">Элемент Configuration</span><span class="sxs-lookup"><span data-stu-id="6c835-104">Configuration Element</span></span>

## <a name="syntax"></a><span data-ttu-id="6c835-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6c835-105">Syntax</span></span>

```xml
<Configuration>
  <DefaultSettings>...</DefaultSettings>
  <SelectionSets>...</SelectionSets>
  <Controls>...</Controls>
  <ViewDefinitions>...</ViewDefinitions>
</Configuration>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="6c835-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6c835-106">Attributes and Elements</span></span>

<span data-ttu-id="6c835-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `Configuration`.</span><span class="sxs-lookup"><span data-stu-id="6c835-107">The following sections describe the attributes, child elements, and the parent element of the `Configuration` element.</span></span> <span data-ttu-id="6c835-108">Этот элемент должен быть корневым элементом для каждого файла форматирования, и этот элемент должен содержать по крайней мере один дочерний элемент.</span><span class="sxs-lookup"><span data-stu-id="6c835-108">This element must be the root element for each formatting file, and this element must contain at least one child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="6c835-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6c835-109">Attributes</span></span>

<span data-ttu-id="6c835-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="6c835-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="6c835-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6c835-111">Child Elements</span></span>

|<span data-ttu-id="6c835-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="6c835-112">Element</span></span>|<span data-ttu-id="6c835-113">Описание</span><span class="sxs-lookup"><span data-stu-id="6c835-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6c835-114">Элемент Controls для конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="6c835-114">Controls Element for Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)|<span data-ttu-id="6c835-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="6c835-115">Optional element.</span></span><br /><br /> <span data-ttu-id="6c835-116">Определяет общие элементы управления, которые могут использоваться всеми представлениями файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="6c835-116">Defines the common controls that can be used by all views of the formatting file.</span></span>|
|[<span data-ttu-id="6c835-117">Элемент Дефаултсеттингс (Format)</span><span class="sxs-lookup"><span data-stu-id="6c835-117">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)|<span data-ttu-id="6c835-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="6c835-118">Optional element.</span></span><br /><br /> <span data-ttu-id="6c835-119">Определяет общие параметры, которые применяются ко всем представлениям файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="6c835-119">Defines common settings that apply to all the views of the formatting file.</span></span>|
|[<span data-ttu-id="6c835-120">Формат элемента Селектионсетс</span><span class="sxs-lookup"><span data-stu-id="6c835-120">SelectionSets Element Format</span></span>](./selectionsets-element-format.md)|<span data-ttu-id="6c835-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="6c835-121">Optional element.</span></span><br /><br /> <span data-ttu-id="6c835-122">Определяет общие наборы объектов .NET, которые могут использоваться всеми представлениями файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="6c835-122">Defines the common sets of .NET objects that can be used by all views of the formatting file.</span></span>|
|[<span data-ttu-id="6c835-123">Элемент Виевдефинитионс (Format)</span><span class="sxs-lookup"><span data-stu-id="6c835-123">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)|<span data-ttu-id="6c835-124">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="6c835-124">Optional element.</span></span><br /><br /> <span data-ttu-id="6c835-125">Определяет представления, используемые для отображения объектов.</span><span class="sxs-lookup"><span data-stu-id="6c835-125">Defines the views used to display objects.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="6c835-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6c835-126">Parent Elements</span></span>

<span data-ttu-id="6c835-127">Нет.</span><span class="sxs-lookup"><span data-stu-id="6c835-127">None.</span></span>

## <a name="remarks"></a><span data-ttu-id="6c835-128">Замечания</span><span class="sxs-lookup"><span data-stu-id="6c835-128">Remarks</span></span>

<span data-ttu-id="6c835-129">Файлы форматирования определяют, как отображаются объекты.</span><span class="sxs-lookup"><span data-stu-id="6c835-129">Formatting files define how objects are displayed.</span></span> <span data-ttu-id="6c835-130">В большинстве случаев этот корневой элемент содержит элемент [виевдефинитионс](./viewdefinitions-element-format.md) , определяющий таблицу, список и широкие представления файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="6c835-130">In most cases, this root element contains a [ViewDefinitions](./viewdefinitions-element-format.md) element that defines the table, list, and wide views of the formatting file.</span></span> <span data-ttu-id="6c835-131">В дополнение к определениям представлений файл форматирования может определять стандартные наборы, параметры и элементы управления, которые могут использоваться этими представлениями.</span><span class="sxs-lookup"><span data-stu-id="6c835-131">In addition to the view definitions, the formatting file can define common selection sets, settings, and controls that those views can use.</span></span>

## <a name="see-also"></a><span data-ttu-id="6c835-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="6c835-132">See Also</span></span>

[<span data-ttu-id="6c835-133">Элемент Controls для конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="6c835-133">Controls Element for Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)

[<span data-ttu-id="6c835-134">Элемент Дефаултсеттингс (Format)</span><span class="sxs-lookup"><span data-stu-id="6c835-134">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)

[<span data-ttu-id="6c835-135">Элемент Селектионсетс (Format)</span><span class="sxs-lookup"><span data-stu-id="6c835-135">SelectionSets Element (Format)</span></span>](./selectionsets-element-format.md)

[<span data-ttu-id="6c835-136">Элемент Виевдефинитионс (Format)</span><span class="sxs-lookup"><span data-stu-id="6c835-136">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)

[<span data-ttu-id="6c835-137">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="6c835-137">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
