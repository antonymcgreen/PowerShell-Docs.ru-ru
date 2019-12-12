---
title: Элемент ScriptBlock для Селектионкондитион для Ентриселектедби для Видеконтрол (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5ec68309-7826-4643-a521-e29c996663fb
caps.latest.revision: 11
ms.openlocfilehash: 649a978e21e9421a3f3e953261e1d309e23c3f9c
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368563"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format"></a><span data-ttu-id="110e7-102">Элемент ScriptBlock для элемента SelectionCondition для элемента EntrySelectedBy для элемента WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="110e7-102">ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideControl (Format)</span></span>

<span data-ttu-id="110e7-103">Указывает скрипт, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="110e7-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="110e7-104">При вычислении этого скрипта на `true`условие выполняется, и используется расширенное определение записи.</span><span class="sxs-lookup"><span data-stu-id="110e7-104">When this script is evaluated to `true`, the condition is met, and the wide entry definition is used.</span></span>

<span data-ttu-id="110e7-105">Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) Видеконтрол элемент (Format) Видинтриес элемент (Format) Видинтри элемент (Format) Ентриселектедби для Видинтри (Format) Селектионкондитион элемент для Ентриселектедби для Видинтри (Format) элемент ScriptBlock для Селектионкондитион для Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="110e7-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="110e7-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="110e7-106">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="110e7-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="110e7-107">Attributes and Elements</span></span>

<span data-ttu-id="110e7-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `ScriptBlock`.</span><span class="sxs-lookup"><span data-stu-id="110e7-108">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="110e7-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="110e7-109">Attributes</span></span>

<span data-ttu-id="110e7-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="110e7-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="110e7-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="110e7-111">Child Elements</span></span>

<span data-ttu-id="110e7-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="110e7-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="110e7-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="110e7-113">Parent Elements</span></span>

|<span data-ttu-id="110e7-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="110e7-114">Element</span></span>|<span data-ttu-id="110e7-115">Описание</span><span class="sxs-lookup"><span data-stu-id="110e7-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="110e7-116">Элемент Селектионкондитион для Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="110e7-116">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="110e7-117">Определяет условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="110e7-117">Defines the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="110e7-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="110e7-118">Text Value</span></span>

<span data-ttu-id="110e7-119">Укажите оцениваемый скрипт.</span><span class="sxs-lookup"><span data-stu-id="110e7-119">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="110e7-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="110e7-120">Remarks</span></span>

<span data-ttu-id="110e7-121">Условие выбора должно указывать по крайней мере одно имя скрипта или свойства для вычисления, но не может одновременно указывать оба значения.</span><span class="sxs-lookup"><span data-stu-id="110e7-121">The selection condition must specify at least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="110e7-122">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="110e7-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="110e7-123">Дополнительные сведения о других компонентах расширенного представления см. в разделе [широкие представления](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="110e7-123">For more information about other components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="110e7-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="110e7-124">See Also</span></span>

[<span data-ttu-id="110e7-125">Создание расширенного представления</span><span class="sxs-lookup"><span data-stu-id="110e7-125">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="110e7-126">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="110e7-126">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="110e7-127">Элемент PropertyName для Селектионкондитион для Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="110e7-127">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="110e7-128">Элемент Селектионкондитион для Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="110e7-128">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="110e7-129">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="110e7-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
