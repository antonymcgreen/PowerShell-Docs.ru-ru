---
title: Элемент ScriptBlock для Итемселектионкондитион элементов управления для представления (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 74b3e23005f595c4c550320849cac5b196e9d479
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787671"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-controls-for-view-format"></a><span data-ttu-id="ec8be-102">Элемент ScriptBlock для элемента ItemSelectionCondition для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="ec8be-102">ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>

<span data-ttu-id="ec8be-103">Указывает скрипт, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="ec8be-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="ec8be-104">При вычислении этого скрипта `true` выполняется условие, и используется элемент управления.</span><span class="sxs-lookup"><span data-stu-id="ec8be-104">When this script is evaluated to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="ec8be-105">Этот элемент используется при определении элементов управления, которые могут использоваться представлением.</span><span class="sxs-lookup"><span data-stu-id="ec8be-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="ec8be-106">Элемент Configuration (Format) Виевдефинитионс элемент (формат) элемент представления (Format) управляет элементом управления "элемент (Format)" для элементов управления для элемента "View" (Format) ошибка customcontrol для элементов управления для элемента Control (формат). для элементов управления для элемента "View" (Format) Кустомитем для Кустоментри для элементов управления для элемента ExpressionBinding представления (Format) ItemSelectionCondition для Кустомитем элементов управления для элемента "View" (формат) элемент ExpressionBinding для элементов управления представления (Format).</span><span class="sxs-lookup"><span data-stu-id="ec8be-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format) ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format) ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ec8be-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ec8be-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ec8be-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ec8be-108">Attributes and Elements</span></span>

<span data-ttu-id="ec8be-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ScriptBlock` элемента.</span><span class="sxs-lookup"><span data-stu-id="ec8be-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ec8be-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ec8be-110">Attributes</span></span>

<span data-ttu-id="ec8be-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ec8be-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ec8be-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ec8be-112">Child Elements</span></span>

<span data-ttu-id="ec8be-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ec8be-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ec8be-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ec8be-114">Parent Elements</span></span>

|<span data-ttu-id="ec8be-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="ec8be-115">Element</span></span>|<span data-ttu-id="ec8be-116">Описание</span><span class="sxs-lookup"><span data-stu-id="ec8be-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ec8be-117">Элемент Итемселектионкондитион элемента ExpressionBinding для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="ec8be-117">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)|<span data-ttu-id="ec8be-118">Определяет условие, которое должно существовать для использования этого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ec8be-118">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="ec8be-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="ec8be-119">Text Value</span></span>

<span data-ttu-id="ec8be-120">Укажите оцениваемый скрипт.</span><span class="sxs-lookup"><span data-stu-id="ec8be-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="ec8be-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="ec8be-121">Remarks</span></span>

<span data-ttu-id="ec8be-122">Если используется этот элемент, нельзя указать элемент [PropertyName](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md) при определении условия выбора.</span><span class="sxs-lookup"><span data-stu-id="ec8be-122">If this element is used, you cannot specify the [PropertyName](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="ec8be-123">См. также</span><span class="sxs-lookup"><span data-stu-id="ec8be-123">See Also</span></span>

[<span data-ttu-id="ec8be-124">Элемент PropertyName для элемента ItemSelectionCondition для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="ec8be-124">PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="ec8be-125">Элемент Итемселектионкондитион элемента ExpressionBinding для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="ec8be-125">ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="ec8be-126">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="ec8be-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
