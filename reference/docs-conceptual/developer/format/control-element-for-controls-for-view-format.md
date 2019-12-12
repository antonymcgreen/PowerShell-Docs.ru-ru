---
title: Элемент Control для элементов управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1fd53f55-698d-4df5-bb9a-fe28dc3193e1
caps.latest.revision: 11
ms.openlocfilehash: df568ccb36a2646b983622cdf95718dd5cac62c3
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72363473"
---
# <a name="control-element-for-controls-for-view--format"></a><span data-ttu-id="d740c-102">Элемент Control для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="d740c-102">Control Element for Controls for View  (Format)</span></span>

<span data-ttu-id="d740c-103">Определяет элемент управления, который может использоваться представлением, и имя, используемое для ссылки на элемент управления.</span><span class="sxs-lookup"><span data-stu-id="d740c-103">Defines a control that can be used by the view and the name that is used to reference the control.</span></span>

<span data-ttu-id="d740c-104">Элемент Configuration (Format) Виевдефинитионс элемент (формат) элемент представления (Format) управляет элементом управления "элемент (Format)" элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="d740c-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d740c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d740c-105">Syntax</span></span>

```xml
<Control>
  <Name>NameOfControl</Name>
  <CustomControl>...</CustomControl>
</Control>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d740c-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d740c-106">Attributes and Elements</span></span>

<span data-ttu-id="d740c-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `Control`.</span><span class="sxs-lookup"><span data-stu-id="d740c-107">The following sections describe the attributes, child elements, and the parent element of the `Control` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d740c-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d740c-108">Attributes</span></span>

<span data-ttu-id="d740c-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="d740c-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d740c-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d740c-110">Child Elements</span></span>

|<span data-ttu-id="d740c-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="d740c-111">Element</span></span>|<span data-ttu-id="d740c-112">Описание</span><span class="sxs-lookup"><span data-stu-id="d740c-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d740c-113">Элемент Name элемента управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="d740c-113">Name Element for Control for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)|<span data-ttu-id="d740c-114">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d740c-114">Required element.</span></span><br /><br /> <span data-ttu-id="d740c-115">Задает имя элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d740c-115">Specifies the name of the control.</span></span>|
|[<span data-ttu-id="d740c-116">Элемент ошибка customcontrol для элемента управления для элементов управления в представлении (формат)</span><span class="sxs-lookup"><span data-stu-id="d740c-116">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)|<span data-ttu-id="d740c-117">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d740c-117">Required element.</span></span><br /><br /> <span data-ttu-id="d740c-118">Определяет элемент управления, используемый этим представлением.</span><span class="sxs-lookup"><span data-stu-id="d740c-118">Defines the control used by this view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="d740c-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d740c-119">Parent Elements</span></span>

|<span data-ttu-id="d740c-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="d740c-120">Element</span></span>|<span data-ttu-id="d740c-121">Описание</span><span class="sxs-lookup"><span data-stu-id="d740c-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d740c-122">Элемент Controls (Format)</span><span class="sxs-lookup"><span data-stu-id="d740c-122">Controls Element (Format)</span></span>](./controls-element-for-view-format.md)|<span data-ttu-id="d740c-123">Определяет элементы управления представления, которые могут использоваться в определенном представлении.</span><span class="sxs-lookup"><span data-stu-id="d740c-123">Defines the view controls that can be used by a specific view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d740c-124">Замечания</span><span class="sxs-lookup"><span data-stu-id="d740c-124">Remarks</span></span>

<span data-ttu-id="d740c-125">Этот элемент управления может быть задан следующими элементами:</span><span class="sxs-lookup"><span data-stu-id="d740c-125">This control can be specified by the following elements:</span></span>

- [<span data-ttu-id="d740c-126">Элемент Кустомконтролнаме для ExpressionBinding элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="d740c-126">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

- [<span data-ttu-id="d740c-127">Элемент Кустомконтролнаме для ExpressionBinding для ошибка customcontrol для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="d740c-127">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

- [<span data-ttu-id="d740c-128">Элемент Кустомконтролнаме для ExpressionBinding для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="d740c-128">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

- [<span data-ttu-id="d740c-129">Элемент Кустомконтролнаме для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="d740c-129">CustomControlName Element for GroupBy (Format)</span></span>](./customcontrolname-element-for-groupby-format.md)

## <a name="see-also"></a><span data-ttu-id="d740c-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="d740c-130">See Also</span></span>

[<span data-ttu-id="d740c-131">Элемент ошибка customcontrol для элемента управления для элементов управления в представлении (формат)</span><span class="sxs-lookup"><span data-stu-id="d740c-131">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="d740c-132">Элемент Кустомконтролнаме для ExpressionBinding элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="d740c-132">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="d740c-133">Элемент Кустомконтролнаме для ExpressionBinding для ошибка customcontrol для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="d740c-133">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="d740c-134">Элемент Кустомконтролнаме для ExpressionBinding для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="d740c-134">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="d740c-135">Элемент Кустомконтролнаме для ExpressionBinding для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="d740c-135">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="d740c-136">Элемент Controls (Format)</span><span class="sxs-lookup"><span data-stu-id="d740c-136">Controls Element (Format)</span></span>](./controls-element-for-view-format.md)

[<span data-ttu-id="d740c-137">Элемент Name для элемента управления для элементов управления в представлении (формат)</span><span class="sxs-lookup"><span data-stu-id="d740c-137">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="d740c-138">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="d740c-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
