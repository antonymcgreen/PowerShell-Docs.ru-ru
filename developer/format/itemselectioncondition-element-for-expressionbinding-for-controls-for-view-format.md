---
title: Элемент ItemSelectionCondition для ExpressionBinding для элементов управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 82c15014-2440-410d-b02d-b7f1a49240a0
caps.latest.revision: 7
ms.openlocfilehash: 80f375c53c205c793600655fa6031d114871618e
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065484"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format"></a><span data-ttu-id="2547c-102">Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="2547c-102">ItemSelectionCondition Element for ExpressionBinding for Controls for View (Format)</span></span>

<span data-ttu-id="2547c-103">Определяет условие, которое должен существовать для данного элемента управления для использования.</span><span class="sxs-lookup"><span data-stu-id="2547c-103">Defines the condition that must exist for this control to be used.</span></span> <span data-ttu-id="2547c-104">Этот элемент используется при определении элементов управления, которые могут использоваться представлением.</span><span class="sxs-lookup"><span data-stu-id="2547c-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="2547c-105">Конфигурации элемента (формат) элемент ViewDefinitions (формат) представление элемента (формат) элементы управления элемента (формат) элемент управления для элементов управления для элемента представления (формат) пользовательский элемент управления для элемента управления для элементов управления для элемента CustomEntries представления (формат) для Пользовательский элемент управления для элемента представления (формат) CustomEntry для CustomEntries для элементов управления для элемента представления (формат) CustomItem для CustomEntry для элементов управления для элемента представления (формат) ExpressionBinding для CustomItem для элементов управления для представления (формат) Элемент ItemSelectionCondition ExpressionBinding для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="2547c-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format) ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2547c-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2547c-106">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2547c-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2547c-107">Attributes and Elements</span></span>

<span data-ttu-id="2547c-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `ItemSelectionCondition` элемент.</span><span class="sxs-lookup"><span data-stu-id="2547c-108">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="2547c-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2547c-109">Attributes</span></span>

<span data-ttu-id="2547c-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="2547c-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2547c-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2547c-111">Child Elements</span></span>

|<span data-ttu-id="2547c-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="2547c-112">Element</span></span>|<span data-ttu-id="2547c-113">Описание</span><span class="sxs-lookup"><span data-stu-id="2547c-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2547c-114">Элемент PropertyName для ItemSelectionCondition для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="2547c-114">PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="2547c-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="2547c-115">Optional element.</span></span><br /><br /> <span data-ttu-id="2547c-116">Задает свойство .NET, которое активирует условие.</span><span class="sxs-lookup"><span data-stu-id="2547c-116">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="2547c-117">Элемент ScriptBlock для ItemSelectionCondition для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="2547c-117">ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="2547c-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="2547c-118">Optional element.</span></span><br /><br /> <span data-ttu-id="2547c-119">Указывает сценарий, который активирует условие.</span><span class="sxs-lookup"><span data-stu-id="2547c-119">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="2547c-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2547c-120">Parent Elements</span></span>

|<span data-ttu-id="2547c-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="2547c-121">Element</span></span>|<span data-ttu-id="2547c-122">Описание</span><span class="sxs-lookup"><span data-stu-id="2547c-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2547c-123">Элемент ExpressionBinding для CustomItem для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="2547c-123">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="2547c-124">Определяет данные, отображаемые элементом управления.</span><span class="sxs-lookup"><span data-stu-id="2547c-124">Defines the data that is displayed by the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="2547c-125">Замечания</span><span class="sxs-lookup"><span data-stu-id="2547c-125">Remarks</span></span>

<span data-ttu-id="2547c-126">Можно указать одно имя свойства или сценарий для данного условия, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="2547c-126">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="2547c-127">См. также</span><span class="sxs-lookup"><span data-stu-id="2547c-127">See Also</span></span>

[<span data-ttu-id="2547c-128">Элемент PropertyName для ItemSelectionCondition для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="2547c-128">PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="2547c-129">Элемент ScriptBlock для ItemSelectionCondition для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="2547c-129">ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="2547c-130">Элемент ExpressionBinding для CustomItem для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="2547c-130">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="2547c-131">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="2547c-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
