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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066799"
---
# <a name="control-element-for-controls-for-configuration-format"></a><span data-ttu-id="05166-102">Элемент Control для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="05166-102">Control Element for Controls for Configuration (Format)</span></span>

<span data-ttu-id="05166-103">Определяет общий элемент управления, который может использоваться все представления файла форматирования и имя, которое используется для ссылки на элемент управления.</span><span class="sxs-lookup"><span data-stu-id="05166-103">Defines a common control that can be used by all the views of the formatting file and the name that is used to reference the control.</span></span>

<span data-ttu-id="05166-104">Конфигурации (формат) элементы управления элемента конфигурации (формат) элемента управления для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="05166-104">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="05166-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="05166-105">Syntax</span></span>

```xml
<Control>
  <Name>NameOfControl</Name>
  <CustomControl>...</CustomControl>
</Control>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="05166-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="05166-106">Attributes and Elements</span></span>

<span data-ttu-id="05166-107">В следующих разделах атрибуты, дочерние элементы и родительский элемент для `Control` элемент.</span><span class="sxs-lookup"><span data-stu-id="05166-107">The following sections describe the attributes, child elements, and the parent element for the `Control` element.</span></span> <span data-ttu-id="05166-108">Необходимо указать только один из каждого дочернего элемента.</span><span class="sxs-lookup"><span data-stu-id="05166-108">You must specify only one of each child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="05166-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="05166-109">Attributes</span></span>

<span data-ttu-id="05166-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="05166-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="05166-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="05166-111">Child Elements</span></span>

|<span data-ttu-id="05166-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="05166-112">Element</span></span>|<span data-ttu-id="05166-113">Описание</span><span class="sxs-lookup"><span data-stu-id="05166-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="05166-114">Пользовательский элемент управления элемент для элемента управления для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="05166-114">CustomControl Element for Control for Controls for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)|<span data-ttu-id="05166-115">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="05166-115">Required element.</span></span><br /><br /> <span data-ttu-id="05166-116">Определяет элемент управления.</span><span class="sxs-lookup"><span data-stu-id="05166-116">Defines the control.</span></span>|
|[<span data-ttu-id="05166-117">Элемент Name описания для элемента управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="05166-117">Name Element for Control for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)|<span data-ttu-id="05166-118">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="05166-118">Required element.</span></span><br /><br /> <span data-ttu-id="05166-119">Указывает имя, используемое для ссылки на элемент управления.</span><span class="sxs-lookup"><span data-stu-id="05166-119">Specifies the name used to reference the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="05166-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="05166-120">Parent Elements</span></span>

|<span data-ttu-id="05166-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="05166-121">Element</span></span>|<span data-ttu-id="05166-122">Описание</span><span class="sxs-lookup"><span data-stu-id="05166-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="05166-123">Элементы управления элемента конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="05166-123">Controls Element of Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)|<span data-ttu-id="05166-124">Определяет общие элементы управления, которые могут использоваться все представления файла форматирования или других элементов управления.</span><span class="sxs-lookup"><span data-stu-id="05166-124">Defines the common controls that can be used by all views of the formatting file or by other controls.</span></span>|

## <a name="remarks"></a><span data-ttu-id="05166-125">Замечания</span><span class="sxs-lookup"><span data-stu-id="05166-125">Remarks</span></span>

<span data-ttu-id="05166-126">Имя, присвоенное этот элемент управления можно ссылаться в следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="05166-126">The name given to this control can be referenced in the following elements:</span></span>

- [<span data-ttu-id="05166-127">Элемент ExpressionBinding для CustomItem (формат)</span><span class="sxs-lookup"><span data-stu-id="05166-127">ExpressionBinding Element for CustomItem (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

- [<span data-ttu-id="05166-128">GroupBy-элемент для View(Format)</span><span class="sxs-lookup"><span data-stu-id="05166-128">GroupBy Element for View(Format)</span></span>](./groupby-element-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="05166-129">См. также</span><span class="sxs-lookup"><span data-stu-id="05166-129">See Also</span></span>

[<span data-ttu-id="05166-130">Элементы управления элемента конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="05166-130">Controls Element of Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)

[<span data-ttu-id="05166-131">Пользовательский элемент управления элемент для элемента управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="05166-131">CustomControl element for Control for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="05166-132">Элемент ExpressionBinding для CustomItem (формат)</span><span class="sxs-lookup"><span data-stu-id="05166-132">ExpressionBinding Element for CustomItem (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="05166-133">GroupBy-элемент для View(Format)</span><span class="sxs-lookup"><span data-stu-id="05166-133">GroupBy Element for View(Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="05166-134">Элемент Name описания для элемента управления для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="05166-134">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="05166-135">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="05166-135">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
