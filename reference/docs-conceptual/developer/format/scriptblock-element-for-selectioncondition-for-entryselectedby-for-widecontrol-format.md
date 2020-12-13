---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент ScriptBlock для элемента SelectionCondition для элемента EntrySelectedBy для элемента WideControl (формат)
description: Элемент ScriptBlock для элемента SelectionCondition для элемента EntrySelectedBy для элемента WideControl (формат)
ms.openlocfilehash: 53d3eba9d453dbcc96afbe8f81a16b61573f2874
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651962"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format"></a><span data-ttu-id="36d6e-103">Элемент ScriptBlock для элемента SelectionCondition для элемента EntrySelectedBy для элемента WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="36d6e-103">ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideControl (Format)</span></span>

<span data-ttu-id="36d6e-104">Указывает скрипт, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="36d6e-104">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="36d6e-105">При вычислении этого скрипта `true` выполняется условие, и используется расширенное определение записи.</span><span class="sxs-lookup"><span data-stu-id="36d6e-105">When this script is evaluated to `true`, the condition is met, and the wide entry definition is used.</span></span>

<span data-ttu-id="36d6e-106">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Видеконтрол элемент (Format) Видинтриес элемент (Format) Видинтри элемент (Format) Ентриселектедби для Видинтри (Format) Селектионкондитион для EntrySelectedBy в WideEntry для SelectionCondition в EntrySelectedBy (Format)</span><span class="sxs-lookup"><span data-stu-id="36d6e-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="36d6e-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="36d6e-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="36d6e-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="36d6e-108">Attributes and Elements</span></span>

<span data-ttu-id="36d6e-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `ScriptBlock` элемента.</span><span class="sxs-lookup"><span data-stu-id="36d6e-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="36d6e-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="36d6e-110">Attributes</span></span>

<span data-ttu-id="36d6e-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="36d6e-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="36d6e-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="36d6e-112">Child Elements</span></span>

<span data-ttu-id="36d6e-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="36d6e-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="36d6e-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="36d6e-114">Parent Elements</span></span>

|<span data-ttu-id="36d6e-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="36d6e-115">Element</span></span>|<span data-ttu-id="36d6e-116">Описание</span><span class="sxs-lookup"><span data-stu-id="36d6e-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="36d6e-117">Элемент Селектионкондитион для Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="36d6e-117">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="36d6e-118">Определяет условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="36d6e-118">Defines the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="36d6e-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="36d6e-119">Text Value</span></span>

<span data-ttu-id="36d6e-120">Укажите оцениваемый скрипт.</span><span class="sxs-lookup"><span data-stu-id="36d6e-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="36d6e-121">Комментарии</span><span class="sxs-lookup"><span data-stu-id="36d6e-121">Remarks</span></span>

<span data-ttu-id="36d6e-122">Условие выбора должно указывать по крайней мере одно имя скрипта или свойства для вычисления, но не может одновременно указывать оба значения.</span><span class="sxs-lookup"><span data-stu-id="36d6e-122">The selection condition must specify at least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="36d6e-123">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="36d6e-123">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="36d6e-124">Дополнительные сведения о других компонентах расширенного представления см. в разделе [широкие представления](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="36d6e-124">For more information about other components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="36d6e-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="36d6e-125">See Also</span></span>

[<span data-ttu-id="36d6e-126">Создание широкого представления</span><span class="sxs-lookup"><span data-stu-id="36d6e-126">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="36d6e-127">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="36d6e-127">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="36d6e-128">Элемент PropertyName для элемента SelectionCondition для элемента EntrySelectedBy для элемента WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="36d6e-128">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="36d6e-129">Элемент Селектионкондитион для Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="36d6e-129">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="36d6e-130">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="36d6e-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
