---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент PropertyName для элемента ItemSelectionCondition для элемента CustomControl для элемента View (формат)
description: Элемент PropertyName для элемента ItemSelectionCondition для элемента CustomControl для элемента View (формат)
ms.openlocfilehash: 5687bb781ce2db27b875f829147ee8b436f04adc
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666133"
---
# <a name="propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format"></a><span data-ttu-id="f4520-103">Элемент PropertyName для элемента ItemSelectionCondition для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="f4520-103">PropertyName Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>

<span data-ttu-id="f4520-104">Указывает свойство .NET, которое запускает условие.</span><span class="sxs-lookup"><span data-stu-id="f4520-104">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="f4520-105">При наличии этого свойства или при его вычислении `true` условие выполняется, и используется элемент управления.</span><span class="sxs-lookup"><span data-stu-id="f4520-105">When this property is present or when it evaluates to `true`, the condition is met, and the control is used.</span></span> <span data-ttu-id="f4520-106">Этот элемент используется при определении пользовательского представления элемента управления.</span><span class="sxs-lookup"><span data-stu-id="f4520-106">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="f4520-107">Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент ошибка customcontrol (Format) элемент Кустоментриес для ошибка customcontrol для элемента View (формат) Кустоментри для Кустоментриес для представления (Format) Кустомитем для Кустоментри для элемента ExpressionBinding представления (Format) для Кустомитем для ошибка customcontrol для элемента представления (Format) ItemSelectionCondition для привязки выражения ошибка customcontrol для представления (Format) PropertyName для ItemSelectionCondition для ошибка customcontrol для представления (Format</span><span class="sxs-lookup"><span data-stu-id="f4520-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for View (Format) ExpressionBinding Element for CustomItem for CustomControl for View (Format) ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format) PropertyName Element for ItemSelectionCondition for CustomControl for View (Format</span></span>

## <a name="syntax"></a><span data-ttu-id="f4520-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f4520-108">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f4520-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f4520-109">Attributes and Elements</span></span>

<span data-ttu-id="f4520-110">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `PropertyName` элемента.</span><span class="sxs-lookup"><span data-stu-id="f4520-110">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f4520-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f4520-111">Attributes</span></span>

<span data-ttu-id="f4520-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f4520-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f4520-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f4520-113">Child Elements</span></span>

<span data-ttu-id="f4520-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f4520-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f4520-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f4520-115">Parent Elements</span></span>

|<span data-ttu-id="f4520-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="f4520-116">Element</span></span>|<span data-ttu-id="f4520-117">Описание</span><span class="sxs-lookup"><span data-stu-id="f4520-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f4520-118">Элемент Итемселектионкондитион для привязки выражения ошибка customcontrol для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="f4520-118">ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)|<span data-ttu-id="f4520-119">Определяет условие, которое должно существовать для использования этого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="f4520-119">Defines the condition that must exist for this control to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f4520-120">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="f4520-120">Text Value</span></span>

<span data-ttu-id="f4520-121">Укажите имя свойства .NET, которое запускает условие.</span><span class="sxs-lookup"><span data-stu-id="f4520-121">Specify the name of the .NET property that triggers the condition.</span></span>

## <a name="remarks"></a><span data-ttu-id="f4520-122">Комментарии</span><span class="sxs-lookup"><span data-stu-id="f4520-122">Remarks</span></span>

<span data-ttu-id="f4520-123">Если этот элемент используется, нельзя указать элемент [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md) при определении условия выбора.</span><span class="sxs-lookup"><span data-stu-id="f4520-123">If this element is used, you cannot specify the [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="f4520-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="f4520-124">See Also</span></span>

[<span data-ttu-id="f4520-125">Элемент ScriptBlock для элемента ItemSelectionCondition для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="f4520-125">ScriptBlock Element for ItemSelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="f4520-126">Элемент Итемселектионкондитион для привязки выражения ошибка customcontrol для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="f4520-126">ItemSelectionCondition Element for Expression Binding for CustomControl for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

[<span data-ttu-id="f4520-127">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="f4520-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
