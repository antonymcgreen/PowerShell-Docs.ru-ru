---
title: Элемент ItemSelectionCondition для ExpressionBinding для GroupBy (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6af3be7d-921e-4cf7-bd5a-d87aa0b4efbd
caps.latest.revision: 7
ms.openlocfilehash: b2b0a0d1996392614807e08b820a72978e38a0cb
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065467"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-groupby-format"></a><span data-ttu-id="ddf40-102">Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="ddf40-102">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>

<span data-ttu-id="ddf40-103">Определяет условие, которое должен существовать для данного элемента управления для использования.</span><span class="sxs-lookup"><span data-stu-id="ddf40-103">Defines the condition that must exist for this control to be used.</span></span> <span data-ttu-id="ddf40-104">Нет ограничений на число условий выборки, которые можно задать для элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ddf40-104">There is no limit to the number of selection conditions that can be specified for a control item.</span></span> <span data-ttu-id="ddf40-105">Этот элемент используется при определении того, как отображается группу объектов.</span><span class="sxs-lookup"><span data-stu-id="ddf40-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="ddf40-106">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) GroupBy элемента конфигурации для элемента представления (формат) пользовательский элемент управления для элемента CustomEntries GroupBy (формат) пользовательский элемент управления для элемента CustomEntry GroupBy (формат) Пользовательский элемент управления для элемента CustomItem GroupBy (формат) для CustomEntry элемента ExpressionBinding GroupBy (формат) для CustomItem элемента ItemSelectionCondition GroupBy (формат) для ExpressionBinding для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="ddf40-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format) ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ddf40-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ddf40-107">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ddf40-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ddf40-108">Attributes and Elements</span></span>

<span data-ttu-id="ddf40-109">Ниже описаны атрибуты, дочерние элементы и родительский элемент `ItemSelectionCondition` элемент.</span><span class="sxs-lookup"><span data-stu-id="ddf40-109">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ddf40-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ddf40-110">Attributes</span></span>

<span data-ttu-id="ddf40-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="ddf40-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ddf40-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ddf40-112">Child Elements</span></span>

|<span data-ttu-id="ddf40-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="ddf40-113">Element</span></span>|<span data-ttu-id="ddf40-114">Описание</span><span class="sxs-lookup"><span data-stu-id="ddf40-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ddf40-115">Элемент PropertyName для ItemSelectionCondition для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="ddf40-115">PropertyName Element for ItemSelectionCondition for GroupBy (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-groupby-format.md)|<span data-ttu-id="ddf40-116">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="ddf40-116">Optional element.</span></span><br /><br /> <span data-ttu-id="ddf40-117">Задает свойство .NET, которое активирует условие.</span><span class="sxs-lookup"><span data-stu-id="ddf40-117">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="ddf40-118">Элемент ScriptBlock для ItemSelectionCondition для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="ddf40-118">ScriptBlock Element for ItemSelectionCondition for GroupBy (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md)|<span data-ttu-id="ddf40-119">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="ddf40-119">Optional element.</span></span><br /><br /> <span data-ttu-id="ddf40-120">Указывает сценарий, который активирует условие.</span><span class="sxs-lookup"><span data-stu-id="ddf40-120">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="ddf40-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ddf40-121">Parent Elements</span></span>

|<span data-ttu-id="ddf40-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="ddf40-122">Element</span></span>|<span data-ttu-id="ddf40-123">Описание</span><span class="sxs-lookup"><span data-stu-id="ddf40-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ddf40-124">Элемент ExpressionBinding для CustomItem для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="ddf40-124">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="ddf40-125">Определяет данные, отображаемые элементом управления.</span><span class="sxs-lookup"><span data-stu-id="ddf40-125">Defines the data that is displayed by the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ddf40-126">Замечания</span><span class="sxs-lookup"><span data-stu-id="ddf40-126">Remarks</span></span>

<span data-ttu-id="ddf40-127">Можно указать одно имя свойства или сценарий для данного условия, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="ddf40-127">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="ddf40-128">См. также</span><span class="sxs-lookup"><span data-stu-id="ddf40-128">See Also</span></span>

[<span data-ttu-id="ddf40-129">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="ddf40-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)

[<span data-ttu-id="ddf40-130">Элемент ExpressionBinding для CustomItem для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="ddf40-130">ExpressionBinding Element for CustomItem for GroupBy (Format)</span></span>](./expressionbinding-element-for-customitem-for-groupby-format.md)
