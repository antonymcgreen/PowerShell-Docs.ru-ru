---
title: Элемент ItemSelectionCondition для ExpressionBinding для пользовательский элемент управления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f4bea9d8-27ad-410e-ad48-287f807d3e4e
caps.latest.revision: 7
ms.openlocfilehash: 18b0113c9b7b0895a1093cb0b56cd2d02c74a6c1
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858190"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-customcontrol-format"></a><span data-ttu-id="043c8-102">Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента CustomControl (формат)</span><span class="sxs-lookup"><span data-stu-id="043c8-102">ItemSelectionCondition Element for ExpressionBinding for CustomControl (Format)</span></span>

<span data-ttu-id="043c8-103">Определяет условие, которое должен существовать для данного элемента управления для использования.</span><span class="sxs-lookup"><span data-stu-id="043c8-103">Defines the condition that must exist for this control to be used.</span></span> <span data-ttu-id="043c8-104">Нет ограничений на число условий выборки, которые можно задать для элемента управления.</span><span class="sxs-lookup"><span data-stu-id="043c8-104">There is no limit to the number of selection conditions that can be specified for a control item.</span></span> <span data-ttu-id="043c8-105">Этот элемент используется при определении представления пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="043c8-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="043c8-106">Элемент (формат) элемент ViewDefinitions (формат) представление элемент (формат) элемент пользовательский элемент управления (формат) CustomEntries элемент конфигурации для пользовательский элемент управления для элемента представления (формат) CustomEntry для CustomEntries для элемента CustomItem представление (формат) CustomEntry для элемента представления (формат) ExpressionBinding для CustomItem для пользовательский элемент управления для элемента ItemSelectionCondition представления (формат) для привязки выражения для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="043c8-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for View (Format) ExpressionBinding Element for CustomItem for CustomControl for View (Format) ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="043c8-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="043c8-107">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="043c8-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="043c8-108">Attributes and Elements</span></span>

<span data-ttu-id="043c8-109">Ниже описаны атрибуты, дочерние элементы и родительский элемент `ItemSelectionCondition` элемент.</span><span class="sxs-lookup"><span data-stu-id="043c8-109">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="043c8-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="043c8-110">Attributes</span></span>

<span data-ttu-id="043c8-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="043c8-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="043c8-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="043c8-112">Child Elements</span></span>

|<span data-ttu-id="043c8-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="043c8-113">Element</span></span>|<span data-ttu-id="043c8-114">Описание</span><span class="sxs-lookup"><span data-stu-id="043c8-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="043c8-115">Элемент PropertyName для ItemSelectionCondition для пользовательский элемент управления для представления (в формате</span><span class="sxs-lookup"><span data-stu-id="043c8-115">PropertyName Element for ItemSelectionCondition for CustomControl for View (Format</span></span>](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="043c8-116">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="043c8-116">Optional element.</span></span><br /><br /> <span data-ttu-id="043c8-117">Задает свойство .NET, которое активирует условие.</span><span class="sxs-lookup"><span data-stu-id="043c8-117">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="043c8-118">Элемент ScriptBlock для ItemSelectionCondition для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="043c8-118">ScriptBlock Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="043c8-119">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="043c8-119">Optional element.</span></span><br /><br /> <span data-ttu-id="043c8-120">Указывает сценарий, который активирует условие.</span><span class="sxs-lookup"><span data-stu-id="043c8-120">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="043c8-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="043c8-121">Parent Elements</span></span>

|<span data-ttu-id="043c8-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="043c8-122">Element</span></span>|<span data-ttu-id="043c8-123">Описание</span><span class="sxs-lookup"><span data-stu-id="043c8-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="043c8-124">Элемент ExpressionBinding для CustomItem для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="043c8-124">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)|<span data-ttu-id="043c8-125">Определяет данные, отображаемые элементом управления.</span><span class="sxs-lookup"><span data-stu-id="043c8-125">Defines the data that is displayed by the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="043c8-126">Замечания</span><span class="sxs-lookup"><span data-stu-id="043c8-126">Remarks</span></span>

<span data-ttu-id="043c8-127">Можно указать одно имя свойства или сценарий для данного условия, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="043c8-127">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="043c8-128">См. также</span><span class="sxs-lookup"><span data-stu-id="043c8-128">See Also</span></span>

[<span data-ttu-id="043c8-129">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="043c8-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)

[<span data-ttu-id="043c8-130">Элемент ExpressionBinding для CustomItem для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="043c8-130">ExpressionBinding Element for CustomItem for CustomControl for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-customcontrol-for-view-format.md)
