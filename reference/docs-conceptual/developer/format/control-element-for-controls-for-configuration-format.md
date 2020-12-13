---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент Control для элемента Controls для элемента Configuration (формат)
description: Элемент Control для элемента Controls для элемента Configuration (формат)
ms.openlocfilehash: 43424de025cb89d81533e973abd7c39c09533747
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655662"
---
# <a name="control-element-for-controls-for-configuration-format"></a><span data-ttu-id="5c366-103">Элемент Control для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="5c366-103">Control Element for Controls for Configuration (Format)</span></span>

<span data-ttu-id="5c366-104">Определяет общий элемент управления, который может использоваться всеми представлениями файла форматирования и именем, используемым для ссылки на элемент управления.</span><span class="sxs-lookup"><span data-stu-id="5c366-104">Defines a common control that can be used by all the views of the formatting file and the name that is used to reference the control.</span></span>

<span data-ttu-id="5c366-105">Элемент Configuration (Format) управляет элементом контрольного элемента конфигурации (Format) для элементов управления конфигурации (Format).</span><span class="sxs-lookup"><span data-stu-id="5c366-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="5c366-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5c366-106">Syntax</span></span>

```xml
<Control>
  <Name>NameOfControl</Name>
  <CustomControl>...</CustomControl>
</Control>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5c366-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5c366-107">Attributes and Elements</span></span>

<span data-ttu-id="5c366-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент для `Control` элемента.</span><span class="sxs-lookup"><span data-stu-id="5c366-108">The following sections describe the attributes, child elements, and the parent element for the `Control` element.</span></span> <span data-ttu-id="5c366-109">Необходимо указать только один дочерний элемент.</span><span class="sxs-lookup"><span data-stu-id="5c366-109">You must specify only one of each child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="5c366-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5c366-110">Attributes</span></span>

<span data-ttu-id="5c366-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5c366-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5c366-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5c366-112">Child Elements</span></span>

|<span data-ttu-id="5c366-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="5c366-113">Element</span></span>|<span data-ttu-id="5c366-114">Описание</span><span class="sxs-lookup"><span data-stu-id="5c366-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5c366-115">Элемент CustomControl для элемента Control для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="5c366-115">CustomControl Element for Control for Controls for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)|<span data-ttu-id="5c366-116">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="5c366-116">Required element.</span></span><br /><br /> <span data-ttu-id="5c366-117">Определяет элемент управления.</span><span class="sxs-lookup"><span data-stu-id="5c366-117">Defines the control.</span></span>|
|[<span data-ttu-id="5c366-118">Элемент Name для элемента управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="5c366-118">Name Element for Control for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)|<span data-ttu-id="5c366-119">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="5c366-119">Required element.</span></span><br /><br /> <span data-ttu-id="5c366-120">Задает имя, используемое для ссылки на элемент управления.</span><span class="sxs-lookup"><span data-stu-id="5c366-120">Specifies the name used to reference the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="5c366-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5c366-121">Parent Elements</span></span>

|<span data-ttu-id="5c366-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="5c366-122">Element</span></span>|<span data-ttu-id="5c366-123">Описание</span><span class="sxs-lookup"><span data-stu-id="5c366-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5c366-124">Элемент управления в конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="5c366-124">Controls Element of Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)|<span data-ttu-id="5c366-125">Определяет общие элементы управления, которые могут использоваться всеми представлениями файла форматирования или другими элементами управления.</span><span class="sxs-lookup"><span data-stu-id="5c366-125">Defines the common controls that can be used by all views of the formatting file or by other controls.</span></span>|

## <a name="remarks"></a><span data-ttu-id="5c366-126">Комментарии</span><span class="sxs-lookup"><span data-stu-id="5c366-126">Remarks</span></span>

<span data-ttu-id="5c366-127">На имя, присвоенное этому элементу управления, можно ссылаться в следующих элементах:</span><span class="sxs-lookup"><span data-stu-id="5c366-127">The name given to this control can be referenced in the following elements:</span></span>

- [<span data-ttu-id="5c366-128">Элемент ExpressionBinding для Кустомитем (Format)</span><span class="sxs-lookup"><span data-stu-id="5c366-128">ExpressionBinding Element for CustomItem (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

- [<span data-ttu-id="5c366-129">Элемент GroupBy для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="5c366-129">GroupBy Element for View(Format)</span></span>](./groupby-element-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="5c366-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="5c366-130">See Also</span></span>

[<span data-ttu-id="5c366-131">Элемент управления в конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="5c366-131">Controls Element of Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)

[<span data-ttu-id="5c366-132">Элемент ошибка customcontrol для элемента управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="5c366-132">CustomControl element for Control for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="5c366-133">Элемент ExpressionBinding для Кустомитем (Format)</span><span class="sxs-lookup"><span data-stu-id="5c366-133">ExpressionBinding Element for CustomItem (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="5c366-134">Элемент GroupBy для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="5c366-134">GroupBy Element for View(Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="5c366-135">Элемент Name для элемента Control для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="5c366-135">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="5c366-136">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="5c366-136">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
