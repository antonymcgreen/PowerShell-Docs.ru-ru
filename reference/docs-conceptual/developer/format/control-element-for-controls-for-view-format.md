---
title: Элемент Control для элементов управления для представления (формат) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 13ea2f09aec7fea8e5460197f133b5f5219cd369
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783812"
---
# <a name="control-element-for-controls-for-view--format"></a><span data-ttu-id="465a1-102">Элемент Control для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="465a1-102">Control Element for Controls for View  (Format)</span></span>

<span data-ttu-id="465a1-103">Определяет элемент управления, который может использоваться представлением, и имя, используемое для ссылки на элемент управления.</span><span class="sxs-lookup"><span data-stu-id="465a1-103">Defines a control that can be used by the view and the name that is used to reference the control.</span></span>

<span data-ttu-id="465a1-104">Элемент Configuration (Format) Виевдефинитионс элемент (формат) элемент представления (Format) управляет элементом управления "элемент (Format)" элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="465a1-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="465a1-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="465a1-105">Syntax</span></span>

```xml
<Control>
  <Name>NameOfControl</Name>
  <CustomControl>...</CustomControl>
</Control>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="465a1-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="465a1-106">Attributes and Elements</span></span>

<span data-ttu-id="465a1-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `Control` элемента.</span><span class="sxs-lookup"><span data-stu-id="465a1-107">The following sections describe the attributes, child elements, and the parent element of the `Control` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="465a1-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="465a1-108">Attributes</span></span>

<span data-ttu-id="465a1-109">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="465a1-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="465a1-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="465a1-110">Child Elements</span></span>

|<span data-ttu-id="465a1-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="465a1-111">Element</span></span>|<span data-ttu-id="465a1-112">Описание</span><span class="sxs-lookup"><span data-stu-id="465a1-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="465a1-113">Элемент Name элемента управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="465a1-113">Name Element for Control for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)|<span data-ttu-id="465a1-114">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="465a1-114">Required element.</span></span><br /><br /> <span data-ttu-id="465a1-115">Задает имя элемента управления.</span><span class="sxs-lookup"><span data-stu-id="465a1-115">Specifies the name of the control.</span></span>|
|[<span data-ttu-id="465a1-116">Элемент CustomControl для элемента Control для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="465a1-116">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)|<span data-ttu-id="465a1-117">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="465a1-117">Required element.</span></span><br /><br /> <span data-ttu-id="465a1-118">Определяет элемент управления, используемый этим представлением.</span><span class="sxs-lookup"><span data-stu-id="465a1-118">Defines the control used by this view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="465a1-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="465a1-119">Parent Elements</span></span>

|<span data-ttu-id="465a1-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="465a1-120">Element</span></span>|<span data-ttu-id="465a1-121">Описание</span><span class="sxs-lookup"><span data-stu-id="465a1-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="465a1-122">Элемент Controls (Format)</span><span class="sxs-lookup"><span data-stu-id="465a1-122">Controls Element (Format)</span></span>](./controls-element-for-view-format.md)|<span data-ttu-id="465a1-123">Определяет элементы управления представления, которые могут использоваться в определенном представлении.</span><span class="sxs-lookup"><span data-stu-id="465a1-123">Defines the view controls that can be used by a specific view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="465a1-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="465a1-124">Remarks</span></span>

<span data-ttu-id="465a1-125">Этот элемент управления может быть задан следующими элементами:</span><span class="sxs-lookup"><span data-stu-id="465a1-125">This control can be specified by the following elements:</span></span>

- [<span data-ttu-id="465a1-126">Элемент CustomControlName для элемента ExpressionBinding для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="465a1-126">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

- [<span data-ttu-id="465a1-127">Элемент CustomControlName для элемента ExpressionBinding для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="465a1-127">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

- [<span data-ttu-id="465a1-128">Элемент CustomControlName для элемента ExpressionBinding для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="465a1-128">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

- [<span data-ttu-id="465a1-129">Элемент CustomControlName для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="465a1-129">CustomControlName Element for GroupBy (Format)</span></span>](./customcontrolname-element-for-groupby-format.md)

## <a name="see-also"></a><span data-ttu-id="465a1-130">См. также</span><span class="sxs-lookup"><span data-stu-id="465a1-130">See Also</span></span>

[<span data-ttu-id="465a1-131">Элемент CustomControl для элемента Control для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="465a1-131">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="465a1-132">Элемент CustomControlName для элемента ExpressionBinding для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="465a1-132">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="465a1-133">Элемент CustomControlName для элемента ExpressionBinding для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="465a1-133">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="465a1-134">Элемент CustomControlName для элемента ExpressionBinding для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="465a1-134">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="465a1-135">Элемент CustomControlName для элемента ExpressionBinding для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="465a1-135">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="465a1-136">Элемент Controls (Format)</span><span class="sxs-lookup"><span data-stu-id="465a1-136">Controls Element (Format)</span></span>](./controls-element-for-view-format.md)

[<span data-ttu-id="465a1-137">Элемент Name для элемента Control для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="465a1-137">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="465a1-138">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="465a1-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
