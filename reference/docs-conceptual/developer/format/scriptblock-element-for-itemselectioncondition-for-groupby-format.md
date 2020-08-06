---
title: Элемент ScriptBlock для Итемселектионкондитион для GroupBy (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 7738b180f328c7360275058cdb9dea01df6ea285
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787654"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-groupby-format"></a><span data-ttu-id="ff493-102">Элемент ScriptBlock для элемента ItemSelectionCondition для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="ff493-102">ScriptBlock Element for ItemSelectionCondition for GroupBy (Format)</span></span>

<span data-ttu-id="ff493-103">Указывает скрипт, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="ff493-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="ff493-104">При вычислении этого скрипта `true` выполняется условие, и используется элемент управления.</span><span class="sxs-lookup"><span data-stu-id="ff493-104">When this script is evaluated to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="ff493-105">Этот элемент используется при определении того, как отображается новая группа объектов.</span><span class="sxs-lookup"><span data-stu-id="ff493-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="ff493-106">Элемент конфигурации (Format) Виевдефинитионс элемент (Format) представление элемента GroupBy для элемента Ошибка customcontrol представления (Format) элемент Кустоментриес для ошибка customcontrol для элемента GroupBy (Format) Кустоментри для ошибка customcontrol для элемента GroupBy (Format) Кустомитем для элемента Кустоментри для GroupBy (Format) ExpressionBinding для Кустомитем для элемента итемселектионкондитион в ExpressionBinding для GroupBy (Format) элемент ScriptBlock для ItemSelectionCondition для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="ff493-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) ExpressionBinding Element for CustomItem for GroupBy (Format) ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format) ScriptBlock Element for ItemSelectionCondition for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ff493-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ff493-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ff493-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ff493-108">Attributes and Elements</span></span>

<span data-ttu-id="ff493-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ScriptBlock` элемента.</span><span class="sxs-lookup"><span data-stu-id="ff493-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ff493-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ff493-110">Attributes</span></span>

<span data-ttu-id="ff493-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ff493-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ff493-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ff493-112">Child Elements</span></span>

<span data-ttu-id="ff493-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ff493-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ff493-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ff493-114">Parent Elements</span></span>

|<span data-ttu-id="ff493-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="ff493-115">Element</span></span>|<span data-ttu-id="ff493-116">Описание</span><span class="sxs-lookup"><span data-stu-id="ff493-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ff493-117">Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="ff493-117">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)|<span data-ttu-id="ff493-118">Определяет условие, которое должно существовать для использования этого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ff493-118">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="ff493-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="ff493-119">Text Value</span></span>

<span data-ttu-id="ff493-120">Укажите оцениваемый скрипт.</span><span class="sxs-lookup"><span data-stu-id="ff493-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="ff493-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="ff493-121">Remarks</span></span>

<span data-ttu-id="ff493-122">Если используется этот элемент, нельзя указать элемент [PropertyName](./propertyname-element-for-itemselectioncondition-for-groupby-format.md) при определении условия выбора.</span><span class="sxs-lookup"><span data-stu-id="ff493-122">If this element is used, you cannot specify the [PropertyName](./propertyname-element-for-itemselectioncondition-for-groupby-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="ff493-123">См. также</span><span class="sxs-lookup"><span data-stu-id="ff493-123">See Also</span></span>

[<span data-ttu-id="ff493-124">Элемент ItemSelectionCondition для элемента ExpressionBinding для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="ff493-124">ItemSelectionCondition Element for ExpressionBinding for GroupBy (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="ff493-125">Элемент PropertyName для элемента ItemSelectionCondition для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="ff493-125">PropertyName Element for ItemSelectionCondition for GroupBy (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-groupby-format.md)

[<span data-ttu-id="ff493-126">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="ff493-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
