---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент PropertyName для элемента ItemSelectionCondition для элемента GroupBy (формат)
description: Элемент PropertyName для элемента ItemSelectionCondition для элемента GroupBy (формат)
ms.openlocfilehash: 9667a389ded33d0744f0f7f8d739635a8b21d98b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666116"
---
# <a name="propertyname-element-for-itemselectioncondition-for-groupby-format"></a><span data-ttu-id="93341-103">Элемент PropertyName для элемента ItemSelectionCondition для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="93341-103">PropertyName Element for ItemSelectionCondition for GroupBy (Format)</span></span>

<span data-ttu-id="93341-104">Указывает свойство .NET, которое запускает условие.</span><span class="sxs-lookup"><span data-stu-id="93341-104">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="93341-105">При наличии этого свойства или при его вычислении `true` условие выполняется, и используется элемент управления.</span><span class="sxs-lookup"><span data-stu-id="93341-105">When this property is present or when it evaluates to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="93341-106">Этот элемент используется при определении того, как отображается новая группа объектов.</span><span class="sxs-lookup"><span data-stu-id="93341-106">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="93341-107">Элемент конфигурации (Format) Виевдефинитионс элемент (Format) представление элемента GroupBy для элемента Ошибка customcontrol представления (Format) элемент Кустоментриес для ошибка customcontrol для элемента GroupBy (Format) Кустоментри для ошибка customcontrol для элемента GroupBy (Format) Кустомитем для элемента Кустоментри для GroupBy (Format) ExpressionBinding для Кустомитем for GroupBy (формат) Итемселектионкондитион для ExpressionBinding для GroupBy (Format) элемент PropertyName для ItemSelectionCondition для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="93341-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format) ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format) PropertyName Element for ItemSelectionCondition for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="93341-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="93341-108">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="93341-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="93341-109">Attributes and Elements</span></span>

<span data-ttu-id="93341-110">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `PropertyName` элемента.</span><span class="sxs-lookup"><span data-stu-id="93341-110">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="93341-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="93341-111">Attributes</span></span>

<span data-ttu-id="93341-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="93341-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="93341-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="93341-113">Child Elements</span></span>

<span data-ttu-id="93341-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="93341-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="93341-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="93341-115">Parent Elements</span></span>

|<span data-ttu-id="93341-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="93341-116">Element</span></span>|<span data-ttu-id="93341-117">Описание</span><span class="sxs-lookup"><span data-stu-id="93341-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="93341-118">Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="93341-118">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="93341-119">Определяет условие, которое должно существовать для использования этого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="93341-119">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="93341-120">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="93341-120">Text Value</span></span>

<span data-ttu-id="93341-121">Укажите имя свойства .NET, которое запускает условие.</span><span class="sxs-lookup"><span data-stu-id="93341-121">Specify the name of the .NET property that triggers the condition.</span></span>

## <a name="remarks"></a><span data-ttu-id="93341-122">Комментарии</span><span class="sxs-lookup"><span data-stu-id="93341-122">Remarks</span></span>

<span data-ttu-id="93341-123">Если этот элемент используется, нельзя указать элемент [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md) при определении условия выбора.</span><span class="sxs-lookup"><span data-stu-id="93341-123">If this element is used, you cannot specify the [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="93341-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="93341-124">See Also</span></span>

[<span data-ttu-id="93341-125">Элемент ScriptBlock для элемента ItemSelectionCondition для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="93341-125">ScriptBlock Element for ItemSelectionCondition for GroupBy (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-groupby-format.md)

[<span data-ttu-id="93341-126">Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="93341-126">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="93341-127">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="93341-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
