---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент PropertyName для элемента SelectionCondition для элемента GroupBy (формат)
description: Элемент PropertyName для элемента SelectionCondition для элемента GroupBy (формат)
ms.openlocfilehash: b89fead6185c88ca03956dc265135833696b91d7
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665674"
---
# <a name="propertyname-element-for-selectioncondition-for-groupby-format"></a><span data-ttu-id="56dd4-103">Элемент PropertyName для элемента SelectionCondition для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="56dd4-103">PropertyName Element for SelectionCondition for GroupBy (Format)</span></span>

<span data-ttu-id="56dd4-104">Указывает свойство .NET, которое запускает условие.</span><span class="sxs-lookup"><span data-stu-id="56dd4-104">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="56dd4-105">При наличии этого свойства или при его вычислении `true` условие выполняется, и используется определение.</span><span class="sxs-lookup"><span data-stu-id="56dd4-105">When this property is present or when it evaluates to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="56dd4-106">Этот элемент используется при определении того, как отображается новая группа объектов.</span><span class="sxs-lookup"><span data-stu-id="56dd4-106">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="56dd4-107">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент GroupBy для элемента Ошибка customcontrol представления (Format) для элемента Кустоментриес для GroupBy (Format) кустоментри для ошибка customcontrol для ошибка customcontrol for GroupBy (формат) ентриселектедби для кустоментри for GroupBy для селектионкондитион для EntrySelectedBy for GroupBy (формат), для SelectionCondition в качестве элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="56dd4-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format) PropertyName Element for SelectionCondition for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="56dd4-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="56dd4-108">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="56dd4-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="56dd4-109">Attributes and Elements</span></span>

<span data-ttu-id="56dd4-110">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `PropertyName` элемента.</span><span class="sxs-lookup"><span data-stu-id="56dd4-110">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="56dd4-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="56dd4-111">Attributes</span></span>

<span data-ttu-id="56dd4-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="56dd4-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="56dd4-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="56dd4-113">Child Elements</span></span>

<span data-ttu-id="56dd4-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="56dd4-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="56dd4-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="56dd4-115">Parent Elements</span></span>

|<span data-ttu-id="56dd4-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="56dd4-116">Element</span></span>|<span data-ttu-id="56dd4-117">Описание</span><span class="sxs-lookup"><span data-stu-id="56dd4-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="56dd4-118">Элемент SelectionCondition для элемента EntrySelectedBy для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="56dd4-118">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="56dd4-119">Определяет условие, которое должно существовать для использования определения элемента управления.</span><span class="sxs-lookup"><span data-stu-id="56dd4-119">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="56dd4-120">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="56dd4-120">Text Value</span></span>

<span data-ttu-id="56dd4-121">Укажите имя свойства .NET.</span><span class="sxs-lookup"><span data-stu-id="56dd4-121">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="56dd4-122">Комментарии</span><span class="sxs-lookup"><span data-stu-id="56dd4-122">Remarks</span></span>

<span data-ttu-id="56dd4-123">Условие выбора должно указывать по крайней мере одно имя свойства или скрипт, но не может указывать и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="56dd4-123">The selection condition must specify a least one property name or a script, but cannot specify both.</span></span> <span data-ttu-id="56dd4-124">Дополнительные сведения о том, как можно использовать условия выбора, см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="56dd4-124">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="56dd4-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="56dd4-125">See Also</span></span>

[<span data-ttu-id="56dd4-126">Элемент SelectionCondition для элемента EntrySelectedBy для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="56dd4-126">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="56dd4-127">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="56dd4-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
