---
title: Элемент PropertyName для Селектионкондитион для Ентриселектедби для Видинтри (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 340abb12-6df1-42f4-bdae-b0509c90952c
caps.latest.revision: 11
ms.openlocfilehash: 196877b97db9ed0592e357486c1318dc1e7efd31
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72362243"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format"></a><span data-ttu-id="eb525-102">Элемент PropertyName для элемента SelectionCondition для элемента EntrySelectedBy для элемента WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="eb525-102">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

<span data-ttu-id="eb525-103">Указывает свойство .NET, которое запускает условие.</span><span class="sxs-lookup"><span data-stu-id="eb525-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="eb525-104">Если это свойство имеется или если оно имеет значение `true`, условие выполняется, и используется определение.</span><span class="sxs-lookup"><span data-stu-id="eb525-104">When this property is present or when it evaluates to `true`, the condition is met, and the definition is used.</span></span>

<span data-ttu-id="eb525-105">Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) Видеконтрол элемент (Format) Видинтриес элемент (Format) Видинтри элемент (Format) Ентриселектедби для Видинтри (Format) Селектионкондитион элемент для Ентриселектедби для Видинтри (Format) PropertyName элемент для Селектионкондитион для Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="eb525-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="eb525-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eb525-106">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

```csharp

```

## <a name="attributes-and-elements"></a><span data-ttu-id="eb525-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="eb525-107">Attributes and Elements</span></span>

<span data-ttu-id="eb525-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `PropertyName`.</span><span class="sxs-lookup"><span data-stu-id="eb525-108">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="eb525-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="eb525-109">Attributes</span></span>

<span data-ttu-id="eb525-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="eb525-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="eb525-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="eb525-111">Child Elements</span></span>

<span data-ttu-id="eb525-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="eb525-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="eb525-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="eb525-113">Parent Elements</span></span>

|<span data-ttu-id="eb525-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="eb525-114">Element</span></span>|<span data-ttu-id="eb525-115">Описание</span><span class="sxs-lookup"><span data-stu-id="eb525-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="eb525-116">Элемент Селектионкондитион для Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="eb525-116">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="eb525-117">Определяет условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="eb525-117">Defines the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="eb525-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="eb525-118">Text Value</span></span>

<span data-ttu-id="eb525-119">Укажите имя свойства .NET.</span><span class="sxs-lookup"><span data-stu-id="eb525-119">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="eb525-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="eb525-120">Remarks</span></span>

<span data-ttu-id="eb525-121">Условие выбора должно указывать по крайней мере одно имя свойства или скрипт для вычисления, но не может одновременно указывать оба значения.</span><span class="sxs-lookup"><span data-stu-id="eb525-121">The selection condition must specify at least one property name or a script to evaluate, but cannot specify both.</span></span> <span data-ttu-id="eb525-122">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="eb525-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="eb525-123">Дополнительные сведения о других компонентах расширенного представления см. в разделе [широкие представления](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="eb525-123">For more information about other components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="eb525-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="eb525-124">See Also</span></span>

[<span data-ttu-id="eb525-125">Создание расширенного представления</span><span class="sxs-lookup"><span data-stu-id="eb525-125">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="eb525-126">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="eb525-126">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="eb525-127">Элемент ScriptBlock для Селектионкондитион для Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="eb525-127">ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="eb525-128">Элемент Селектионкондитион для Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="eb525-128">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="eb525-129">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="eb525-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
