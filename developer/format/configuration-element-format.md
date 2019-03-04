---
title: Элемент конфигурации (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d46df0cb-50b7-4b81-82ba-37186a7b7a7f
caps.latest.revision: 28
ms.openlocfilehash: 296c63d0c774a0bf56e90dbaa32f2c221d4c3dbd
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856330"
---
# <a name="configuration-element-format"></a><span data-ttu-id="be86d-102">Элемент Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="be86d-102">Configuration Element (Format)</span></span>

<span data-ttu-id="be86d-103">Представляет элемент верхнего уровня файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="be86d-103">Represents the top-level element of a formatting file.</span></span>

<span data-ttu-id="be86d-104">Элемент конфигурации</span><span class="sxs-lookup"><span data-stu-id="be86d-104">Configuration Element</span></span>

## <a name="syntax"></a><span data-ttu-id="be86d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="be86d-105">Syntax</span></span>

```xml
<Configuration>
  <DefaultSettings>...</DefaultSettings>
  <SelectionSets>...</SelectionSets>
  <Controls>...</Controls>
  <ViewDefinitions>...</ViewDefinitions>
</Configuration>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="be86d-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="be86d-106">Attributes and Elements</span></span>

<span data-ttu-id="be86d-107">В следующих разделах атрибуты, дочерние элементы и родительский элемент `Configuration` элемент.</span><span class="sxs-lookup"><span data-stu-id="be86d-107">The following sections describe the attributes, child elements, and the parent element of the `Configuration` element.</span></span> <span data-ttu-id="be86d-108">Этот элемент должен быть корневой элемент для каждого файла форматирования, и этот элемент должен содержать по крайней мере один дочерний элемент.</span><span class="sxs-lookup"><span data-stu-id="be86d-108">This element must be the root element for each formatting file, and this element must contain at least one child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="be86d-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="be86d-109">Attributes</span></span>

<span data-ttu-id="be86d-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="be86d-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="be86d-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="be86d-111">Child Elements</span></span>

|<span data-ttu-id="be86d-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="be86d-112">Element</span></span>|<span data-ttu-id="be86d-113">Описание</span><span class="sxs-lookup"><span data-stu-id="be86d-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="be86d-114">Элементы управления элемент конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="be86d-114">Controls Element for Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)|<span data-ttu-id="be86d-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="be86d-115">Optional element.</span></span><br /><br /> <span data-ttu-id="be86d-116">Определяет общие элементы управления, которые могут использоваться все представления файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="be86d-116">Defines the common controls that can be used by all views of the formatting file.</span></span>|
|[<span data-ttu-id="be86d-117">Элемент DefaultSettings (формат)</span><span class="sxs-lookup"><span data-stu-id="be86d-117">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)|<span data-ttu-id="be86d-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="be86d-118">Optional element.</span></span><br /><br /> <span data-ttu-id="be86d-119">Определяет общие параметры, которые применяются ко всем представлениям форматирования файла.</span><span class="sxs-lookup"><span data-stu-id="be86d-119">Defines common settings that apply to all the views of the formatting file.</span></span>|
|[<span data-ttu-id="be86d-120">Формат SelectionSets элемент</span><span class="sxs-lookup"><span data-stu-id="be86d-120">SelectionSets Element Format</span></span>](./selectionsets-element-format.md)|<span data-ttu-id="be86d-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="be86d-121">Optional element.</span></span><br /><br /> <span data-ttu-id="be86d-122">Определяет общие наборы объектов .NET, которые могут использоваться все представления файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="be86d-122">Defines the common sets of .NET objects that can be used by all views of the formatting file.</span></span>|
|[<span data-ttu-id="be86d-123">Элемент ViewDefinitions (формат)</span><span class="sxs-lookup"><span data-stu-id="be86d-123">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)|<span data-ttu-id="be86d-124">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="be86d-124">Optional element.</span></span><br /><br /> <span data-ttu-id="be86d-125">Определяет представления для отображения объектов.</span><span class="sxs-lookup"><span data-stu-id="be86d-125">Defines the views used to display objects.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="be86d-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="be86d-126">Parent Elements</span></span>

<span data-ttu-id="be86d-127">Нет.</span><span class="sxs-lookup"><span data-stu-id="be86d-127">None.</span></span>

## <a name="remarks"></a><span data-ttu-id="be86d-128">Замечания</span><span class="sxs-lookup"><span data-stu-id="be86d-128">Remarks</span></span>

<span data-ttu-id="be86d-129">Файлы форматирования определяют способ отображения объектов.</span><span class="sxs-lookup"><span data-stu-id="be86d-129">Formatting files define how objects are displayed.</span></span> <span data-ttu-id="be86d-130">В большинстве случаев это корневой элемент содержит [ViewDefinitions](./viewdefinitions-element-format.md) элемент, который определяет таблицы, список и широкие представления файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="be86d-130">In most cases, this root element contains a [ViewDefinitions](./viewdefinitions-element-format.md) element that defines the table, list, and wide views of the formatting file.</span></span> <span data-ttu-id="be86d-131">Помимо определения представлений файл форматирования можно определить общие наборы выделения, параметры и элементы управления, которые могут использовать эти представления.</span><span class="sxs-lookup"><span data-stu-id="be86d-131">In addition to the view definitions, the formatting file can define common selection sets, settings, and controls that those views can use.</span></span>

## <a name="see-also"></a><span data-ttu-id="be86d-132">См. также</span><span class="sxs-lookup"><span data-stu-id="be86d-132">See Also</span></span>

[<span data-ttu-id="be86d-133">Элементы управления элемент конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="be86d-133">Controls Element for Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)

[<span data-ttu-id="be86d-134">Элемент DefaultSettings (формат)</span><span class="sxs-lookup"><span data-stu-id="be86d-134">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)

[<span data-ttu-id="be86d-135">Элемент SelectionSets (формат)</span><span class="sxs-lookup"><span data-stu-id="be86d-135">SelectionSets Element (Format)</span></span>](./selectionsets-element-format.md)

[<span data-ttu-id="be86d-136">Элемент ViewDefinitions (формат)</span><span class="sxs-lookup"><span data-stu-id="be86d-136">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)

[<span data-ttu-id="be86d-137">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="be86d-137">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
