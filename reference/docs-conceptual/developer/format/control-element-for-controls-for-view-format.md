---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент Control для элемента Controls для элемента View (формат)
description: Элемент Control для элемента Controls для элемента View (формат)
ms.openlocfilehash: c48b8b7ecaebfde5e6ed2123b837d92561551766
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668088"
---
# <a name="control-element-for-controls-for-view--format"></a><span data-ttu-id="5867b-103">Элемент Control для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="5867b-103">Control Element for Controls for View  (Format)</span></span>

<span data-ttu-id="5867b-104">Определяет элемент управления, который может использоваться представлением, и имя, используемое для ссылки на элемент управления.</span><span class="sxs-lookup"><span data-stu-id="5867b-104">Defines a control that can be used by the view and the name that is used to reference the control.</span></span>

<span data-ttu-id="5867b-105">Элемент Configuration (Format) Виевдефинитионс элемент (формат) элемент представления (Format) управляет элементом управления "элемент (Format)" элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="5867b-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="5867b-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5867b-106">Syntax</span></span>

```xml
<Control>
  <Name>NameOfControl</Name>
  <CustomControl>...</CustomControl>
</Control>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5867b-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5867b-107">Attributes and Elements</span></span>

<span data-ttu-id="5867b-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `Control` элемента.</span><span class="sxs-lookup"><span data-stu-id="5867b-108">The following sections describe the attributes, child elements, and the parent element of the `Control` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="5867b-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5867b-109">Attributes</span></span>

<span data-ttu-id="5867b-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5867b-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="5867b-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5867b-111">Child Elements</span></span>

|<span data-ttu-id="5867b-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="5867b-112">Element</span></span>|<span data-ttu-id="5867b-113">Описание</span><span class="sxs-lookup"><span data-stu-id="5867b-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5867b-114">Элемент Name элемента управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="5867b-114">Name Element for Control for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)|<span data-ttu-id="5867b-115">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="5867b-115">Required element.</span></span><br /><br /> <span data-ttu-id="5867b-116">Задает имя элемента управления.</span><span class="sxs-lookup"><span data-stu-id="5867b-116">Specifies the name of the control.</span></span>|
|[<span data-ttu-id="5867b-117">Элемент CustomControl для элемента Control для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="5867b-117">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)|<span data-ttu-id="5867b-118">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="5867b-118">Required element.</span></span><br /><br /> <span data-ttu-id="5867b-119">Определяет элемент управления, используемый этим представлением.</span><span class="sxs-lookup"><span data-stu-id="5867b-119">Defines the control used by this view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="5867b-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5867b-120">Parent Elements</span></span>

|<span data-ttu-id="5867b-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="5867b-121">Element</span></span>|<span data-ttu-id="5867b-122">Описание</span><span class="sxs-lookup"><span data-stu-id="5867b-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5867b-123">Элемент Controls (Format)</span><span class="sxs-lookup"><span data-stu-id="5867b-123">Controls Element (Format)</span></span>](./controls-element-for-view-format.md)|<span data-ttu-id="5867b-124">Определяет элементы управления представления, которые могут использоваться в определенном представлении.</span><span class="sxs-lookup"><span data-stu-id="5867b-124">Defines the view controls that can be used by a specific view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="5867b-125">Комментарии</span><span class="sxs-lookup"><span data-stu-id="5867b-125">Remarks</span></span>

<span data-ttu-id="5867b-126">Этот элемент управления может быть задан следующими элементами:</span><span class="sxs-lookup"><span data-stu-id="5867b-126">This control can be specified by the following elements:</span></span>

- [<span data-ttu-id="5867b-127">Элемент CustomControlName для элемента ExpressionBinding для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="5867b-127">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

- [<span data-ttu-id="5867b-128">Элемент CustomControlName для элемента ExpressionBinding для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="5867b-128">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

- [<span data-ttu-id="5867b-129">Элемент CustomControlName для элемента ExpressionBinding для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="5867b-129">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

- [<span data-ttu-id="5867b-130">Элемент CustomControlName для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="5867b-130">CustomControlName Element for GroupBy (Format)</span></span>](./customcontrolname-element-for-groupby-format.md)

## <a name="see-also"></a><span data-ttu-id="5867b-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="5867b-131">See Also</span></span>

[<span data-ttu-id="5867b-132">Элемент CustomControl для элемента Control для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="5867b-132">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="5867b-133">Элемент CustomControlName для элемента ExpressionBinding для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="5867b-133">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="5867b-134">Элемент CustomControlName для элемента ExpressionBinding для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="5867b-134">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="5867b-135">Элемент CustomControlName для элемента ExpressionBinding для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="5867b-135">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="5867b-136">Элемент CustomControlName для элемента ExpressionBinding для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="5867b-136">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="5867b-137">Элемент Controls (Format)</span><span class="sxs-lookup"><span data-stu-id="5867b-137">Controls Element (Format)</span></span>](./controls-element-for-view-format.md)

[<span data-ttu-id="5867b-138">Элемент Name для элемента Control для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="5867b-138">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="5867b-139">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="5867b-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
