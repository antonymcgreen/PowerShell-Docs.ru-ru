---
title: Элемент ItemSelectionCondition для ExpressionBinding для элементов управления для конфигурации (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd3ddc33-b21c-4464-b3f2-a78dbe0062a8
caps.latest.revision: 8
ms.openlocfilehash: 4865d716ebe0460b662253a3019e93e82428b882
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065518"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format"></a><span data-ttu-id="46585-102">Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="46585-102">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>

<span data-ttu-id="46585-103">Определяет условие, которое должен существовать для данного элемента управления для использования.</span><span class="sxs-lookup"><span data-stu-id="46585-103">Defines the condition that must exist for this control to be used.</span></span> <span data-ttu-id="46585-104">Этот элемент используется при определении общего элемента управления, который может использоваться все представления в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="46585-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="46585-105">Конфигурации (формат) элементы управления элемента конфигурации (формат) элемента управления для элементов управления для элемента конфигурации (формат) пользовательский элемент управления для элемента управления для элемента конфигурации (формат) CustomEntries пользовательский элемент управления для конфигурации ( Элемент CustomEntry Format) для пользовательский элемент управления для элементов управления для элемента конфигурации (формат) CustomItem для CustomEntry для элементов управления для элемента конфигурации ExpressionBinding для CustomItem для элементов управления для конфигурации (формат) Элемент ItemSelectionCondition для ExpressionBinding для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="46585-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format) ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="46585-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="46585-106">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="46585-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="46585-107">Attributes and Elements</span></span>

<span data-ttu-id="46585-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `ItemSelectionCondition` элемент.</span><span class="sxs-lookup"><span data-stu-id="46585-108">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="46585-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="46585-109">Attributes</span></span>

<span data-ttu-id="46585-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="46585-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="46585-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="46585-111">Child Elements</span></span>

|<span data-ttu-id="46585-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="46585-112">Element</span></span>|<span data-ttu-id="46585-113">Описание</span><span class="sxs-lookup"><span data-stu-id="46585-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="46585-114">Элемент PropertyName для ItemSelectionCondition для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="46585-114">PropertyName Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="46585-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="46585-115">Optional element.</span></span><br /><br /> <span data-ttu-id="46585-116">Задает свойство .NET, которое активирует условие.</span><span class="sxs-lookup"><span data-stu-id="46585-116">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="46585-117">Элемент ScriptBlock для ItemSelectionCondition для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="46585-117">ScriptBlock Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="46585-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="46585-118">Optional element.</span></span><br /><br /> <span data-ttu-id="46585-119">Указывает сценарий, который активирует условие.</span><span class="sxs-lookup"><span data-stu-id="46585-119">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="46585-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="46585-120">Parent Elements</span></span>

|<span data-ttu-id="46585-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="46585-121">Element</span></span>|<span data-ttu-id="46585-122">Описание</span><span class="sxs-lookup"><span data-stu-id="46585-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="46585-123">Элемент ExpressionBinding для CustomItem для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="46585-123">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="46585-124">Определяет данные, отображаемые элементом управления.</span><span class="sxs-lookup"><span data-stu-id="46585-124">Defines the data that is displayed by the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="46585-125">Замечания</span><span class="sxs-lookup"><span data-stu-id="46585-125">Remarks</span></span>

<span data-ttu-id="46585-126">Можно указать одно имя свойства или сценарий для данного условия, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="46585-126">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="46585-127">См. также</span><span class="sxs-lookup"><span data-stu-id="46585-127">See Also</span></span>

[<span data-ttu-id="46585-128">Элемент PropertyName для ItemSelectionCondition для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="46585-128">PropertyName Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="46585-129">Элемент ScriptBlock для ItemSelectionCondition для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="46585-129">ScriptBlock Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="46585-130">Элемент ExpressionBinding для CustomItem для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="46585-130">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="46585-131">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="46585-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
