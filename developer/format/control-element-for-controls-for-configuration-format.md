---
title: Элемент Control для элементов управления для конфигурации (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bddf7ffa-04d3-4354-90b9-5e714e096260
caps.latest.revision: 13
ms.openlocfilehash: 26fe417c9ca60dda22bdc23d9d339d40135a0c9b
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858890"
---
# <a name="control-element-for-controls-for-configuration-format"></a><span data-ttu-id="7ce4b-102">Элемент Control для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="7ce4b-102">Control Element for Controls for Configuration (Format)</span></span>

<span data-ttu-id="7ce4b-103">Определяет общий элемент управления, который может использоваться все представления файла форматирования и имя, которое используется для ссылки на элемент управления.</span><span class="sxs-lookup"><span data-stu-id="7ce4b-103">Defines a common control that can be used by all the views of the formatting file and the name that is used to reference the control.</span></span>

<span data-ttu-id="7ce4b-104">Конфигурации (формат) элементы управления элемента конфигурации (формат) элемента управления для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="7ce4b-104">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7ce4b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7ce4b-105">Syntax</span></span>

```xml
<Control>
  <Name>NameOfControl</Name>
  <CustomControl>...</CustomControl>
</Control>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7ce4b-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7ce4b-106">Attributes and Elements</span></span>

<span data-ttu-id="7ce4b-107">В следующих разделах атрибуты, дочерние элементы и родительский элемент для `Control` элемент.</span><span class="sxs-lookup"><span data-stu-id="7ce4b-107">The following sections describe the attributes, child elements, and the parent element for the `Control` element.</span></span> <span data-ttu-id="7ce4b-108">Необходимо указать только один из каждого дочернего элемента.</span><span class="sxs-lookup"><span data-stu-id="7ce4b-108">You must specify only one of each child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="7ce4b-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7ce4b-109">Attributes</span></span>

<span data-ttu-id="7ce4b-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="7ce4b-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7ce4b-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7ce4b-111">Child Elements</span></span>

|<span data-ttu-id="7ce4b-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="7ce4b-112">Element</span></span>|<span data-ttu-id="7ce4b-113">Описание</span><span class="sxs-lookup"><span data-stu-id="7ce4b-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7ce4b-114">Пользовательский элемент управления элемент для элемента управления для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="7ce4b-114">CustomControl Element for Control for Controls for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)|<span data-ttu-id="7ce4b-115">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="7ce4b-115">Required element.</span></span><br /><br /> <span data-ttu-id="7ce4b-116">Определяет элемент управления.</span><span class="sxs-lookup"><span data-stu-id="7ce4b-116">Defines the control.</span></span>|
|[<span data-ttu-id="7ce4b-117">Элемент Name описания для элемента управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="7ce4b-117">Name Element for Control for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)|<span data-ttu-id="7ce4b-118">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="7ce4b-118">Required element.</span></span><br /><br /> <span data-ttu-id="7ce4b-119">Указывает имя, используемое для ссылки на элемент управления.</span><span class="sxs-lookup"><span data-stu-id="7ce4b-119">Specifies the name used to reference the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="7ce4b-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7ce4b-120">Parent Elements</span></span>

|<span data-ttu-id="7ce4b-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="7ce4b-121">Element</span></span>|<span data-ttu-id="7ce4b-122">Описание</span><span class="sxs-lookup"><span data-stu-id="7ce4b-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7ce4b-123">Элементы управления элемента конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="7ce4b-123">Controls Element of Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)|<span data-ttu-id="7ce4b-124">Определяет общие элементы управления, которые могут использоваться все представления файла форматирования или других элементов управления.</span><span class="sxs-lookup"><span data-stu-id="7ce4b-124">Defines the common controls that can be used by all views of the formatting file or by other controls.</span></span>|

## <a name="remarks"></a><span data-ttu-id="7ce4b-125">Замечания</span><span class="sxs-lookup"><span data-stu-id="7ce4b-125">Remarks</span></span>

<span data-ttu-id="7ce4b-126">Имя, присвоенное этот элемент управления можно ссылаться в следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="7ce4b-126">The name given to this control can be referenced in the following elements:</span></span>

- [<span data-ttu-id="7ce4b-127">Элемент ExpressionBinding для CustomItem (формат)</span><span class="sxs-lookup"><span data-stu-id="7ce4b-127">ExpressionBinding Element for CustomItem (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

- [<span data-ttu-id="7ce4b-128">GroupBy-элемент для View(Format)</span><span class="sxs-lookup"><span data-stu-id="7ce4b-128">GroupBy Element for View(Format)</span></span>](./groupby-element-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="7ce4b-129">См. также</span><span class="sxs-lookup"><span data-stu-id="7ce4b-129">See Also</span></span>

[<span data-ttu-id="7ce4b-130">Элементы управления элемента конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="7ce4b-130">Controls Element of Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)

[<span data-ttu-id="7ce4b-131">Пользовательский элемент управления элемент для элемента управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="7ce4b-131">CustomControl element for Control for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="7ce4b-132">Элемент ExpressionBinding для CustomItem (формат)</span><span class="sxs-lookup"><span data-stu-id="7ce4b-132">ExpressionBinding Element for CustomItem (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="7ce4b-133">GroupBy-элемент для View(Format)</span><span class="sxs-lookup"><span data-stu-id="7ce4b-133">GroupBy Element for View(Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="7ce4b-134">Элемент Name описания для элемента управления для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="7ce4b-134">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="7ce4b-135">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="7ce4b-135">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
