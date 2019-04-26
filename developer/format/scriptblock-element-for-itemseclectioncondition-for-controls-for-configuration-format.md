---
title: Элемент ScriptBlock для ItemSeclectionCondition для элементов управления для конфигурации (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 51f7aec9-7b01-4370-84f4-1e58508a851f
caps.latest.revision: 6
ms.openlocfilehash: e92b2dfff07358132c480c47c34279e5365fe400
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064447"
---
# <a name="scriptblock-element-for-itemseclectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="adfb3-102">Элемент ScriptBlock для элемента ItemSeclectionCondition для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="adfb3-102">ScriptBlock Element for ItemSeclectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="adfb3-103">Указывает сценарий, который активирует условие.</span><span class="sxs-lookup"><span data-stu-id="adfb3-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="adfb3-104">При вычислении этого сценария для `true`условие выполняется, и используется элемент управления.</span><span class="sxs-lookup"><span data-stu-id="adfb3-104">When this script is evaluated to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="adfb3-105">Этот элемент используется при определении общего элемента управления, который может использоваться все представления в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="adfb3-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="adfb3-106">Конфигурации (формат) элементы управления элемента конфигурации (формат) элемента управления для элементов управления для элемента конфигурации (формат) пользовательский элемент управления для элемента управления для элемента конфигурации (формат) CustomEntries пользовательский элемент управления для конфигурации ( Элемент CustomEntry Format) для пользовательский элемент управления для элементов управления для элемента конфигурации (формат) CustomItem для CustomEntry для элементов управления для элемента конфигурации ExpressionBinding для CustomItem для элементов управления для конфигурации (формат) Элемент ItemSelectionCondition для ExpressionBinding для элементов управления для элемента конфигурации (формат) ScriptBlock для ItemSelectionCondition для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="adfb3-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format) ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format) ScriptBlock Element for ItemSelectionCondition for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="adfb3-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="adfb3-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="adfb3-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="adfb3-108">Attributes and Elements</span></span>

<span data-ttu-id="adfb3-109">Ниже описаны атрибуты, дочерние элементы и родительский элемент `ScriptBlock` элемент.</span><span class="sxs-lookup"><span data-stu-id="adfb3-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="adfb3-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="adfb3-110">Attributes</span></span>

<span data-ttu-id="adfb3-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="adfb3-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="adfb3-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="adfb3-112">Child Elements</span></span>

<span data-ttu-id="adfb3-113">Нет.</span><span class="sxs-lookup"><span data-stu-id="adfb3-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="adfb3-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="adfb3-114">Parent Elements</span></span>

|<span data-ttu-id="adfb3-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="adfb3-115">Element</span></span>|<span data-ttu-id="adfb3-116">Описание</span><span class="sxs-lookup"><span data-stu-id="adfb3-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="adfb3-117">Элемент ItemSelectionCondition для ExpressionBinding для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="adfb3-117">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="adfb3-118">Определяет условие, которое должен существовать для данного элемента управления для использования.</span><span class="sxs-lookup"><span data-stu-id="adfb3-118">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="adfb3-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="adfb3-119">Text Value</span></span>

<span data-ttu-id="adfb3-120">Укажите сценарий, который вычисляется.</span><span class="sxs-lookup"><span data-stu-id="adfb3-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="adfb3-121">Замечания</span><span class="sxs-lookup"><span data-stu-id="adfb3-121">Remarks</span></span>

<span data-ttu-id="adfb3-122">Если этот элемент используется, нельзя указать [PropertyName](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md) элемент при определении условию выбора.</span><span class="sxs-lookup"><span data-stu-id="adfb3-122">If this element is used, you cannot specify the [PropertyName](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="adfb3-123">См. также</span><span class="sxs-lookup"><span data-stu-id="adfb3-123">See Also</span></span>

[<span data-ttu-id="adfb3-124">Элемент PropertyName для ItemSeclectionCondition для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="adfb3-124">PropertyName Element for ItemSeclectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-itemseclectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="adfb3-125">Элемент ItemSelectionCondition для ExpressionBinding для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="adfb3-125">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)

[<span data-ttu-id="adfb3-126">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="adfb3-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
