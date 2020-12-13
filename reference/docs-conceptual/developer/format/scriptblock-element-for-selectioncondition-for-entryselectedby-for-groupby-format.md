---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент ScriptBlock для элемента SelectionCondition для элемента EntrySelectedBy для элемента GroupBy (формат)
description: Элемент ScriptBlock для элемента SelectionCondition для элемента EntrySelectedBy для элемента GroupBy (формат)
ms.openlocfilehash: cc92aa642b42fa3e4c4f974e954d5eac73179de3
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664880"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-groupby-format"></a><span data-ttu-id="f252b-103">Элемент ScriptBlock для элемента SelectionCondition для элемента EntrySelectedBy для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="f252b-103">ScriptBlock Element for SelectionCondition for EntrySelectedBy for GroupBy (Format)</span></span>

<span data-ttu-id="f252b-104">Указывает скрипт, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="f252b-104">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="f252b-105">При вычислении этого скрипта `true` выполняется условие, и используется определение.</span><span class="sxs-lookup"><span data-stu-id="f252b-105">When this script is evaluated to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="f252b-106">Этот элемент используется при определении того, как отображается новая группа объектов.</span><span class="sxs-lookup"><span data-stu-id="f252b-106">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="f252b-107">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент GroupBy для элемента Ошибка customcontrol представления (Format) для элемента Кустоментриес для GroupBy (Format) кустоментри для ошибка customcontrol для ошибка customcontrol for GroupBy (Format) ентриселектедби для кустоментри for GroupBy (формат). элемент селектионкондитион для для EntrySelectedBy для SelectionCondition for GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="f252b-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format) ScriptBlock Element for SelectionCondition for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f252b-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f252b-108">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f252b-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f252b-109">Attributes and Elements</span></span>

<span data-ttu-id="f252b-110">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ScriptBlock` элемента.</span><span class="sxs-lookup"><span data-stu-id="f252b-110">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f252b-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f252b-111">Attributes</span></span>

<span data-ttu-id="f252b-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f252b-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f252b-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f252b-113">Child Elements</span></span>

<span data-ttu-id="f252b-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f252b-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f252b-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f252b-115">Parent Elements</span></span>

|<span data-ttu-id="f252b-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="f252b-116">Element</span></span>|<span data-ttu-id="f252b-117">Описание</span><span class="sxs-lookup"><span data-stu-id="f252b-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f252b-118">Элемент SelectionCondition для элемента EntrySelectedBy для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="f252b-118">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="f252b-119">Определяет условие, которое должно существовать для использования определения элемента управления.</span><span class="sxs-lookup"><span data-stu-id="f252b-119">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f252b-120">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="f252b-120">Text Value</span></span>

<span data-ttu-id="f252b-121">Укажите оцениваемый скрипт.</span><span class="sxs-lookup"><span data-stu-id="f252b-121">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="f252b-122">Комментарии</span><span class="sxs-lookup"><span data-stu-id="f252b-122">Remarks</span></span>

<span data-ttu-id="f252b-123">Условие выбора должно указывать по крайней мере один имя скрипта или свойства для вычисления, но не может одновременно указывать оба значения.</span><span class="sxs-lookup"><span data-stu-id="f252b-123">The selection condition must specify a least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="f252b-124">Дополнительные сведения о том, как можно использовать условия выбора, см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="f252b-124">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f252b-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="f252b-125">See Also</span></span>

[<span data-ttu-id="f252b-126">Элемент SelectionCondition для элемента EntrySelectedBy для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="f252b-126">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="f252b-127">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="f252b-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
