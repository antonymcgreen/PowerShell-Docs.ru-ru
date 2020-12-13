---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент ScriptBlock для элемента ItemSelectionCondition для элемента GroupBy (формат)
description: Элемент ScriptBlock для элемента ItemSelectionCondition для элемента GroupBy (формат)
ms.openlocfilehash: fe366fa31b93e8d69409cc49c3fe2c350d4d06d9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665091"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-groupby-format"></a><span data-ttu-id="6cff6-103">Элемент ScriptBlock для элемента ItemSelectionCondition для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="6cff6-103">ScriptBlock Element for ItemSelectionCondition for GroupBy (Format)</span></span>

<span data-ttu-id="6cff6-104">Указывает скрипт, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="6cff6-104">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="6cff6-105">При вычислении этого скрипта `true` выполняется условие, и используется элемент управления.</span><span class="sxs-lookup"><span data-stu-id="6cff6-105">When this script is evaluated to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="6cff6-106">Этот элемент используется при определении того, как отображается новая группа объектов.</span><span class="sxs-lookup"><span data-stu-id="6cff6-106">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="6cff6-107">Элемент конфигурации (Format) Виевдефинитионс элемент (Format) представление элемента GroupBy для элемента Ошибка customcontrol представления (Format) элемент Кустоментриес для ошибка customcontrol для элемента GroupBy (Format) Кустоментри для ошибка customcontrol для элемента GroupBy (Format) Кустомитем для элемента Кустоментри для GroupBy (Format) ExpressionBinding для Кустомитем для элемента итемселектионкондитион в ExpressionBinding для GroupBy (Format) элемент ScriptBlock для ItemSelectionCondition для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="6cff6-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format) ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format) ScriptBlock Element for ItemSelectionCondition for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="6cff6-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6cff6-108">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6cff6-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6cff6-109">Attributes and Elements</span></span>

<span data-ttu-id="6cff6-110">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ScriptBlock` элемента.</span><span class="sxs-lookup"><span data-stu-id="6cff6-110">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="6cff6-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6cff6-111">Attributes</span></span>

<span data-ttu-id="6cff6-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="6cff6-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="6cff6-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6cff6-113">Child Elements</span></span>

<span data-ttu-id="6cff6-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="6cff6-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="6cff6-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6cff6-115">Parent Elements</span></span>

|<span data-ttu-id="6cff6-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="6cff6-116">Element</span></span>|<span data-ttu-id="6cff6-117">Описание</span><span class="sxs-lookup"><span data-stu-id="6cff6-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6cff6-118">Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="6cff6-118">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="6cff6-119">Определяет условие, которое должно существовать для использования этого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="6cff6-119">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="6cff6-120">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="6cff6-120">Text Value</span></span>

<span data-ttu-id="6cff6-121">Укажите оцениваемый скрипт.</span><span class="sxs-lookup"><span data-stu-id="6cff6-121">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="6cff6-122">Комментарии</span><span class="sxs-lookup"><span data-stu-id="6cff6-122">Remarks</span></span>

<span data-ttu-id="6cff6-123">Если используется этот элемент, нельзя указать элемент [PropertyName](./propertyname-element-for-itemselectioncondition-for-groupby-format.md) при определении условия выбора.</span><span class="sxs-lookup"><span data-stu-id="6cff6-123">If this element is used, you cannot specify the [PropertyName](./propertyname-element-for-itemselectioncondition-for-groupby-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="6cff6-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="6cff6-124">See Also</span></span>

[<span data-ttu-id="6cff6-125">Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="6cff6-125">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="6cff6-126">Элемент PropertyName для элемента ItemSelectionCondition для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="6cff6-126">PropertyName Element for ItemSelectionCondition for GroupBy (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-groupby-format.md)

[<span data-ttu-id="6cff6-127">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="6cff6-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
