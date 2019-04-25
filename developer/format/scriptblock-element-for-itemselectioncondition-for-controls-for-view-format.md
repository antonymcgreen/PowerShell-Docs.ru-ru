---
title: Элемент ScriptBlock для ItemSelectionCondition для элементов управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b4191157-bf01-4831-b221-6f8cc581cd53
caps.latest.revision: 6
ms.openlocfilehash: 0cbefbb48427b56d4ae2a5ae27c7726dcfad7b84
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064719"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-controls-for-view-format"></a><span data-ttu-id="e85c7-102">Элемент ScriptBlock для элемента ItemSelectionCondition для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="e85c7-102">ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>

<span data-ttu-id="e85c7-103">Указывает сценарий, который активирует условие.</span><span class="sxs-lookup"><span data-stu-id="e85c7-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="e85c7-104">При вычислении этого сценария для `true`условие выполняется, и используется элемент управления.</span><span class="sxs-lookup"><span data-stu-id="e85c7-104">When this script is evaluated to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="e85c7-105">Этот элемент используется при определении элементов управления, которые могут использоваться представлением.</span><span class="sxs-lookup"><span data-stu-id="e85c7-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="e85c7-106">Конфигурации элемента (формат) элемент ViewDefinitions (формат) представление элемента (формат) элементы управления элемента (формат) элемент управления для элементов управления для элемента представления (формат) пользовательский элемент управления для элемента управления для элементов управления для элемента CustomEntries представления (формат) для Пользовательский элемент управления для элемента представления (формат) CustomEntry для CustomEntries для элементов управления для элемента представления (формат) CustomItem для CustomEntry для элементов управления для элемента представления (формат) ExpressionBinding для CustomItem для элементов управления для представления (формат) Элемент ItemSelectionCondition ExpressionBinding для элементов управления для элемента представления (формат) ScriptBlock для ItemSelectionCondition для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="e85c7-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format) ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format) ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e85c7-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e85c7-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e85c7-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e85c7-108">Attributes and Elements</span></span>

<span data-ttu-id="e85c7-109">Ниже описаны атрибуты, дочерние элементы и родительский элемент `ScriptBlock` элемент.</span><span class="sxs-lookup"><span data-stu-id="e85c7-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e85c7-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e85c7-110">Attributes</span></span>

<span data-ttu-id="e85c7-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="e85c7-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e85c7-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e85c7-112">Child Elements</span></span>

<span data-ttu-id="e85c7-113">Нет.</span><span class="sxs-lookup"><span data-stu-id="e85c7-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e85c7-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e85c7-114">Parent Elements</span></span>

|<span data-ttu-id="e85c7-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="e85c7-115">Element</span></span>|<span data-ttu-id="e85c7-116">Описание</span><span class="sxs-lookup"><span data-stu-id="e85c7-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e85c7-117">Элемент ItemSelectionCondition ExpressionBinding для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="e85c7-117">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="e85c7-118">Определяет условие, которое должен существовать для данного элемента управления для использования.</span><span class="sxs-lookup"><span data-stu-id="e85c7-118">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="e85c7-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="e85c7-119">Text Value</span></span>

<span data-ttu-id="e85c7-120">Укажите сценарий, который вычисляется.</span><span class="sxs-lookup"><span data-stu-id="e85c7-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="e85c7-121">Замечания</span><span class="sxs-lookup"><span data-stu-id="e85c7-121">Remarks</span></span>

<span data-ttu-id="e85c7-122">Если этот элемент используется, нельзя указать [PropertyName](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md) элемент при определении условию выбора.</span><span class="sxs-lookup"><span data-stu-id="e85c7-122">If this element is used, you cannot specify the [PropertyName](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="e85c7-123">См. также</span><span class="sxs-lookup"><span data-stu-id="e85c7-123">See Also</span></span>

[<span data-ttu-id="e85c7-124">Элемент PropertyName для ItemSelectionCondition для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="e85c7-124">PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="e85c7-125">Элемент ItemSelectionCondition ExpressionBinding для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="e85c7-125">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="e85c7-126">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="e85c7-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
