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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066776"
---
# <a name="control-element-for-controls-for-view--format"></a><span data-ttu-id="70f25-102">Элемент Control для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="70f25-102">Control Element for Controls for View  (Format)</span></span>

<span data-ttu-id="70f25-103">Определяет элемент управления, который может использоваться представление и имя, которое используется для ссылки на элемент управления.</span><span class="sxs-lookup"><span data-stu-id="70f25-103">Defines a control that can be used by the view and the name that is used to reference the control.</span></span>

<span data-ttu-id="70f25-104">Элемент представления ViewDefinitions элемент (формат) конфигурации элемент (формат) (формат) управляет элемент управления элемента (формат) для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="70f25-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="70f25-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="70f25-105">Syntax</span></span>

```xml
<Control>
  <Name>NameOfControl</Name>
  <CustomControl>...</CustomControl>
</Control>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="70f25-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="70f25-106">Attributes and Elements</span></span>

<span data-ttu-id="70f25-107">В следующих разделах атрибуты, дочерние элементы и родительский элемент `Control` элемент.</span><span class="sxs-lookup"><span data-stu-id="70f25-107">The following sections describe the attributes, child elements, and the parent element of the `Control` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="70f25-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="70f25-108">Attributes</span></span>

<span data-ttu-id="70f25-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="70f25-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="70f25-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="70f25-110">Child Elements</span></span>

|<span data-ttu-id="70f25-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="70f25-111">Element</span></span>|<span data-ttu-id="70f25-112">Описание</span><span class="sxs-lookup"><span data-stu-id="70f25-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="70f25-113">Элемент Name описания для элемента управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="70f25-113">Name Element for Control for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)|<span data-ttu-id="70f25-114">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="70f25-114">Required element.</span></span><br /><br /> <span data-ttu-id="70f25-115">Задает имя элемента управления.</span><span class="sxs-lookup"><span data-stu-id="70f25-115">Specifies the name of the control.</span></span>|
|[<span data-ttu-id="70f25-116">Пользовательский элемент управления элемент для элемента управления для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="70f25-116">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)|<span data-ttu-id="70f25-117">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="70f25-117">Required element.</span></span><br /><br /> <span data-ttu-id="70f25-118">Определяет элемент управления, используемый в данном представлении.</span><span class="sxs-lookup"><span data-stu-id="70f25-118">Defines the control used by this view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="70f25-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="70f25-119">Parent Elements</span></span>

|<span data-ttu-id="70f25-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="70f25-120">Element</span></span>|<span data-ttu-id="70f25-121">Описание</span><span class="sxs-lookup"><span data-stu-id="70f25-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="70f25-122">Controls-элемент (формат)</span><span class="sxs-lookup"><span data-stu-id="70f25-122">Controls Element (Format)</span></span>](./controls-element-for-view-format.md)|<span data-ttu-id="70f25-123">Определяет элементы управления представления, которые могут использоваться по определенному представлению.</span><span class="sxs-lookup"><span data-stu-id="70f25-123">Defines the view controls that can be used by a specific view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="70f25-124">Замечания</span><span class="sxs-lookup"><span data-stu-id="70f25-124">Remarks</span></span>

<span data-ttu-id="70f25-125">Этот элемент управления можно указать, следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="70f25-125">This control can be specified by the following elements:</span></span>

- [<span data-ttu-id="70f25-126">Элемент CustomControlName для ExpressionBinding для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="70f25-126">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

- [<span data-ttu-id="70f25-127">Элемент CustomControlName для ExpressionBinding для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="70f25-127">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

- [<span data-ttu-id="70f25-128">Элемент CustomControlName для ExpressionBinding для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="70f25-128">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

- [<span data-ttu-id="70f25-129">Элемент CustomControlName для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="70f25-129">CustomControlName Element for GroupBy (Format)</span></span>](./customcontrolname-element-for-groupby-format.md)

## <a name="see-also"></a><span data-ttu-id="70f25-130">См. также</span><span class="sxs-lookup"><span data-stu-id="70f25-130">See Also</span></span>

[<span data-ttu-id="70f25-131">Пользовательский элемент управления элемент для элемента управления для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="70f25-131">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="70f25-132">Элемент CustomControlName для ExpressionBinding для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="70f25-132">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="70f25-133">Элемент CustomControlName для ExpressionBinding для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="70f25-133">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="70f25-134">Элемент CustomControlName для ExpressionBinding для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="70f25-134">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="70f25-135">Элемент CustomControlName для ExpressionBinding для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="70f25-135">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="70f25-136">Controls-элемент (формат)</span><span class="sxs-lookup"><span data-stu-id="70f25-136">Controls Element (Format)</span></span>](./controls-element-for-view-format.md)

[<span data-ttu-id="70f25-137">Элемент Name описания для элемента управления для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="70f25-137">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="70f25-138">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="70f25-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
