---
title: Элемент Control для элементов управления Configuration (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bddf7ffa-04d3-4354-90b9-5e714e096260
caps.latest.revision: 13
ms.openlocfilehash: 26fe417c9ca60dda22bdc23d9d339d40135a0c9b
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369013"
---
# <a name="control-element-for-controls-for-configuration-format"></a><span data-ttu-id="1d96c-102">Элемент Control для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="1d96c-102">Control Element for Controls for Configuration (Format)</span></span>

<span data-ttu-id="1d96c-103">Определяет общий элемент управления, который может использоваться всеми представлениями файла форматирования и именем, используемым для ссылки на элемент управления.</span><span class="sxs-lookup"><span data-stu-id="1d96c-103">Defines a common control that can be used by all the views of the formatting file and the name that is used to reference the control.</span></span>

<span data-ttu-id="1d96c-104">Элемент Configuration (Format) управляет элементом контрольного элемента конфигурации (Format) для элементов управления конфигурации (Format).</span><span class="sxs-lookup"><span data-stu-id="1d96c-104">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="1d96c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1d96c-105">Syntax</span></span>

```xml
<Control>
  <Name>NameOfControl</Name>
  <CustomControl>...</CustomControl>
</Control>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1d96c-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1d96c-106">Attributes and Elements</span></span>

<span data-ttu-id="1d96c-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент для элемента `Control`.</span><span class="sxs-lookup"><span data-stu-id="1d96c-107">The following sections describe the attributes, child elements, and the parent element for the `Control` element.</span></span> <span data-ttu-id="1d96c-108">Необходимо указать только один дочерний элемент.</span><span class="sxs-lookup"><span data-stu-id="1d96c-108">You must specify only one of each child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="1d96c-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1d96c-109">Attributes</span></span>

<span data-ttu-id="1d96c-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="1d96c-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1d96c-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1d96c-111">Child Elements</span></span>

|<span data-ttu-id="1d96c-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="1d96c-112">Element</span></span>|<span data-ttu-id="1d96c-113">Описание</span><span class="sxs-lookup"><span data-stu-id="1d96c-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1d96c-114">Элемент ошибка customcontrol для элемента управления для элементов управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="1d96c-114">CustomControl Element for Control for Controls for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)|<span data-ttu-id="1d96c-115">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="1d96c-115">Required element.</span></span><br /><br /> <span data-ttu-id="1d96c-116">Определяет элемент управления.</span><span class="sxs-lookup"><span data-stu-id="1d96c-116">Defines the control.</span></span>|
|[<span data-ttu-id="1d96c-117">Элемент Name для элемента управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="1d96c-117">Name Element for Control for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)|<span data-ttu-id="1d96c-118">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="1d96c-118">Required element.</span></span><br /><br /> <span data-ttu-id="1d96c-119">Задает имя, используемое для ссылки на элемент управления.</span><span class="sxs-lookup"><span data-stu-id="1d96c-119">Specifies the name used to reference the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="1d96c-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1d96c-120">Parent Elements</span></span>

|<span data-ttu-id="1d96c-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="1d96c-121">Element</span></span>|<span data-ttu-id="1d96c-122">Описание</span><span class="sxs-lookup"><span data-stu-id="1d96c-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1d96c-123">Элемент управления в конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="1d96c-123">Controls Element of Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)|<span data-ttu-id="1d96c-124">Определяет общие элементы управления, которые могут использоваться всеми представлениями файла форматирования или другими элементами управления.</span><span class="sxs-lookup"><span data-stu-id="1d96c-124">Defines the common controls that can be used by all views of the formatting file or by other controls.</span></span>|

## <a name="remarks"></a><span data-ttu-id="1d96c-125">Замечания</span><span class="sxs-lookup"><span data-stu-id="1d96c-125">Remarks</span></span>

<span data-ttu-id="1d96c-126">На имя, присвоенное этому элементу управления, можно ссылаться в следующих элементах:</span><span class="sxs-lookup"><span data-stu-id="1d96c-126">The name given to this control can be referenced in the following elements:</span></span>

- [<span data-ttu-id="1d96c-127">Элемент ExpressionBinding для Кустомитем (Format)</span><span class="sxs-lookup"><span data-stu-id="1d96c-127">ExpressionBinding Element for CustomItem (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

- [<span data-ttu-id="1d96c-128">Элемент GroupBy для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="1d96c-128">GroupBy Element for View(Format)</span></span>](./groupby-element-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="1d96c-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="1d96c-129">See Also</span></span>

[<span data-ttu-id="1d96c-130">Элемент управления в конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="1d96c-130">Controls Element of Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)

[<span data-ttu-id="1d96c-131">Элемент ошибка customcontrol для элемента управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="1d96c-131">CustomControl element for Control for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="1d96c-132">Элемент ExpressionBinding для Кустомитем (Format)</span><span class="sxs-lookup"><span data-stu-id="1d96c-132">ExpressionBinding Element for CustomItem (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="1d96c-133">Элемент GroupBy для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="1d96c-133">GroupBy Element for View(Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="1d96c-134">Элемент Name для элемента управления для элементов управления Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="1d96c-134">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="1d96c-135">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="1d96c-135">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
