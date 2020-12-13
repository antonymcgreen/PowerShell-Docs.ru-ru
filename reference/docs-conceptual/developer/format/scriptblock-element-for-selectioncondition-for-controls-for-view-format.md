---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент ScriptBlock для элемента SelectionCondition для элемента Controls для элемента View (формат)
description: Элемент ScriptBlock для элемента SelectionCondition для элемента Controls для элемента View (формат)
ms.openlocfilehash: 7eed3b8a06bc45396026b8e2a7454447b3090d74
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664945"
---
# <a name="scriptblock-element-for-selectioncondition-for-controls-for-view-format"></a><span data-ttu-id="07f57-103">Элемент ScriptBlock для элемента SelectionCondition для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="07f57-103">ScriptBlock Element for SelectionCondition for Controls for View (Format)</span></span>

<span data-ttu-id="07f57-104">Указывает скрипт, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="07f57-104">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="07f57-105">При вычислении этого скрипта `true` выполняется условие, и используется определение.</span><span class="sxs-lookup"><span data-stu-id="07f57-105">When this script is evaluated to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="07f57-106">Этот элемент используется при определении элементов управления, которые могут использоваться представлением.</span><span class="sxs-lookup"><span data-stu-id="07f57-106">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="07f57-107">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) управляет элементом управления "элемент (Format)" для элементов управления для элемента "View" (Format) ошибка customcontrol для элемента управления, для которого элемент Control элемента (Format) Кустоментри элемент для Кустоментриес для элементов управления элемента Ентриселектедби представления (Format) для Кустоментри для элементов управления для элемента "View" (формат) SelectionCondition для EntrySelectedBy для элементов управления представления (Format) элемент ScriptBlock для SelectionCondition для элементов управления View (формат)</span><span class="sxs-lookup"><span data-stu-id="07f57-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format) SelectionCondition Element for EntrySelectedBy for Controls for View (Format) ScriptBlock Element for SelectionCondition for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="07f57-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="07f57-108">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="07f57-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="07f57-109">Attributes and Elements</span></span>

<span data-ttu-id="07f57-110">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ScriptBlock` элемента.</span><span class="sxs-lookup"><span data-stu-id="07f57-110">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="07f57-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="07f57-111">Attributes</span></span>

<span data-ttu-id="07f57-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="07f57-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="07f57-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="07f57-113">Child Elements</span></span>

<span data-ttu-id="07f57-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="07f57-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="07f57-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="07f57-115">Parent Elements</span></span>

|<span data-ttu-id="07f57-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="07f57-116">Element</span></span>|<span data-ttu-id="07f57-117">Описание</span><span class="sxs-lookup"><span data-stu-id="07f57-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="07f57-118">Элемент SelectionCondition для элемента EntrySelectedBy для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="07f57-118">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="07f57-119">Определяет условие, которое должно существовать для использования определения элемента управления.</span><span class="sxs-lookup"><span data-stu-id="07f57-119">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="07f57-120">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="07f57-120">Text Value</span></span>

<span data-ttu-id="07f57-121">Укажите оцениваемый скрипт.</span><span class="sxs-lookup"><span data-stu-id="07f57-121">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="07f57-122">Комментарии</span><span class="sxs-lookup"><span data-stu-id="07f57-122">Remarks</span></span>

<span data-ttu-id="07f57-123">Условие выбора должно указывать по крайней мере один имя скрипта или свойства для вычисления, но не может одновременно указывать оба значения.</span><span class="sxs-lookup"><span data-stu-id="07f57-123">The selection condition must specify a least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="07f57-124">Дополнительные сведения о том, как можно использовать условия выбора, см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="07f57-124">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="07f57-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="07f57-125">See Also</span></span>

[<span data-ttu-id="07f57-126">Элемент SelectionCondition для элемента EntrySelectedBy для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="07f57-126">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)

[<span data-ttu-id="07f57-127">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="07f57-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
