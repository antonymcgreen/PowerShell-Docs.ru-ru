---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент PropertyName для элемента SelectionCondition для элемента EntrySelectedBy для элемента WideEntry (формат)
description: Элемент PropertyName для элемента SelectionCondition для элемента EntrySelectedBy для элемента WideEntry (формат)
ms.openlocfilehash: bda34b0c1e97fb85536132bedcec3986072801b7
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665708"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format"></a><span data-ttu-id="497c4-103">Элемент PropertyName для элемента SelectionCondition для элемента EntrySelectedBy для элемента WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="497c4-103">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

<span data-ttu-id="497c4-104">Указывает свойство .NET, которое запускает условие.</span><span class="sxs-lookup"><span data-stu-id="497c4-104">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="497c4-105">При наличии этого свойства или при его вычислении `true` условие выполняется, и используется определение.</span><span class="sxs-lookup"><span data-stu-id="497c4-105">When this property is present or when it evaluates to `true`, the condition is met, and the definition is used.</span></span>

<span data-ttu-id="497c4-106">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) Видеконтрол элемент (Format) Видинтриес элемент (Format) Видинтри элемент (Format) Ентриселектедби для видинтри (Format) Селектионкондитион для EntrySelectedBy в WideEntry для SelectionCondition в EntrySelectedBy (Format)</span><span class="sxs-lookup"><span data-stu-id="497c4-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="497c4-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="497c4-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

```csharp

```

## <a name="attributes-and-elements"></a><span data-ttu-id="497c4-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="497c4-108">Attributes and Elements</span></span>

<span data-ttu-id="497c4-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `PropertyName` элемента.</span><span class="sxs-lookup"><span data-stu-id="497c4-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="497c4-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="497c4-110">Attributes</span></span>

<span data-ttu-id="497c4-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="497c4-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="497c4-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="497c4-112">Child Elements</span></span>

<span data-ttu-id="497c4-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="497c4-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="497c4-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="497c4-114">Parent Elements</span></span>

|<span data-ttu-id="497c4-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="497c4-115">Element</span></span>|<span data-ttu-id="497c4-116">Описание</span><span class="sxs-lookup"><span data-stu-id="497c4-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="497c4-117">Элемент Селектионкондитион для Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="497c4-117">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="497c4-118">Определяет условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="497c4-118">Defines the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="497c4-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="497c4-119">Text Value</span></span>

<span data-ttu-id="497c4-120">Укажите имя свойства .NET.</span><span class="sxs-lookup"><span data-stu-id="497c4-120">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="497c4-121">Комментарии</span><span class="sxs-lookup"><span data-stu-id="497c4-121">Remarks</span></span>

<span data-ttu-id="497c4-122">Условие выбора должно указывать по крайней мере одно имя свойства или скрипт для вычисления, но не может одновременно указывать оба значения.</span><span class="sxs-lookup"><span data-stu-id="497c4-122">The selection condition must specify at least one property name or a script to evaluate, but cannot specify both.</span></span> <span data-ttu-id="497c4-123">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="497c4-123">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="497c4-124">Дополнительные сведения о других компонентах расширенного представления см. в разделе [широкие представления](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="497c4-124">For more information about other components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="497c4-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="497c4-125">See Also</span></span>

[<span data-ttu-id="497c4-126">Создание широкого представления</span><span class="sxs-lookup"><span data-stu-id="497c4-126">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="497c4-127">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="497c4-127">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="497c4-128">Элемент ScriptBlock для Селектионкондитион для Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="497c4-128">ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="497c4-129">Элемент Селектионкондитион для Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="497c4-129">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="497c4-130">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="497c4-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
