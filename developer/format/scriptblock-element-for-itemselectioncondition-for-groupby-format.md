---
title: Элемент ScriptBlock для ItemSelectionCondition для GroupBy (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 58d25835-4636-4c58-9f6c-0332b9318051
caps.latest.revision: 6
ms.openlocfilehash: 4045196e306e766cd805b3e7ae31bfcb3de184ee
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860950"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-groupby-format"></a><span data-ttu-id="93a8d-102">Элемент ScriptBlock для элемента ItemSelectionCondition для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="93a8d-102">ScriptBlock Element for ItemSelectionCondition for GroupBy (Format)</span></span>

<span data-ttu-id="93a8d-103">Указывает сценарий, который активирует условие.</span><span class="sxs-lookup"><span data-stu-id="93a8d-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="93a8d-104">При вычислении этого сценария для `true`условие выполняется, и используется элемент управления.</span><span class="sxs-lookup"><span data-stu-id="93a8d-104">When this script is evaluated to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="93a8d-105">Этот элемент используется при определении того, как отображается группу объектов.</span><span class="sxs-lookup"><span data-stu-id="93a8d-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="93a8d-106">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) GroupBy элемента конфигурации для элемента представления (формат) пользовательский элемент управления для элемента CustomEntries GroupBy (формат) пользовательский элемент управления для элемента CustomEntry GroupBy (формат) Пользовательский элемент управления для элемента CustomItem GroupBy (формат) для CustomEntry элемента ExpressionBinding GroupBy (формат) для CustomItem элемента ItemSelectionCondition GroupBy (формат) для ExpressionBinding для элемента ScriptBlock GroupBy (формат) ItemSelectionCondition для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="93a8d-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format) ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format) ScriptBlock Element for ItemSelectionCondition for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="93a8d-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="93a8d-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="93a8d-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="93a8d-108">Attributes and Elements</span></span>

<span data-ttu-id="93a8d-109">Ниже описаны атрибуты, дочерние элементы и родительский элемент `ScriptBlock` элемент.</span><span class="sxs-lookup"><span data-stu-id="93a8d-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="93a8d-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="93a8d-110">Attributes</span></span>

<span data-ttu-id="93a8d-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="93a8d-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="93a8d-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="93a8d-112">Child Elements</span></span>

<span data-ttu-id="93a8d-113">Нет.</span><span class="sxs-lookup"><span data-stu-id="93a8d-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="93a8d-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="93a8d-114">Parent Elements</span></span>

|<span data-ttu-id="93a8d-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="93a8d-115">Element</span></span>|<span data-ttu-id="93a8d-116">Описание</span><span class="sxs-lookup"><span data-stu-id="93a8d-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="93a8d-117">Элемент ItemSelectionCondition для ExpressionBinding для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="93a8d-117">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="93a8d-118">Определяет условие, которое должен существовать для данного элемента управления для использования.</span><span class="sxs-lookup"><span data-stu-id="93a8d-118">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="93a8d-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="93a8d-119">Text Value</span></span>

<span data-ttu-id="93a8d-120">Укажите сценарий, который вычисляется.</span><span class="sxs-lookup"><span data-stu-id="93a8d-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="93a8d-121">Замечания</span><span class="sxs-lookup"><span data-stu-id="93a8d-121">Remarks</span></span>

<span data-ttu-id="93a8d-122">Если этот элемент используется, нельзя указать [PropertyName](./propertyname-element-for-itemselectioncondition-for-groupby-format.md) элемент при определении условию выбора.</span><span class="sxs-lookup"><span data-stu-id="93a8d-122">If this element is used, you cannot specify the [PropertyName](./propertyname-element-for-itemselectioncondition-for-groupby-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="93a8d-123">См. также</span><span class="sxs-lookup"><span data-stu-id="93a8d-123">See Also</span></span>

[<span data-ttu-id="93a8d-124">Элемент ItemSelectionCondition для ExpressionBinding для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="93a8d-124">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="93a8d-125">Элемент PropertyName для ItemSelectionCondition для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="93a8d-125">PropertyName Element for ItemSelectionCondition for GroupBy (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-groupby-format.md)

[<span data-ttu-id="93a8d-126">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="93a8d-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
