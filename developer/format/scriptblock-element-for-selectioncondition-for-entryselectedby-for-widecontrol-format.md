---
title: Элемент ScriptBlock для SelectionCondition для EntrySelectedBy для WideControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5ec68309-7826-4643-a521-e29c996663fb
caps.latest.revision: 11
ms.openlocfilehash: 649a978e21e9421a3f3e953261e1d309e23c3f9c
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862950"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format"></a><span data-ttu-id="74209-102">Элемент ScriptBlock для элемента SelectionCondition для элемента EntrySelectedBy для элемента WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="74209-102">ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideControl (Format)</span></span>

<span data-ttu-id="74209-103">Указывает сценарий, который активирует условие.</span><span class="sxs-lookup"><span data-stu-id="74209-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="74209-104">При вычислении этого сценария для `true`условие выполняется, и используется определение расширенных запись.</span><span class="sxs-lookup"><span data-stu-id="74209-104">When this script is evaluated to `true`, the condition is met, and the wide entry definition is used.</span></span>

<span data-ttu-id="74209-105">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) элемент WideControl (формат) элемент WideEntries (формат) элемент WideEntry (формат) EntrySelectedBy элемент конфигурации для элемент SelectionCondition WideEntry (формат) для EntrySelectedBy WideEntry (формат) элемента ScriptBlock для SelectionCondition для EntrySelectedBy для WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="74209-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="74209-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="74209-106">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="74209-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="74209-107">Attributes and Elements</span></span>

<span data-ttu-id="74209-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `ScriptBlock` элемент.</span><span class="sxs-lookup"><span data-stu-id="74209-108">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="74209-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="74209-109">Attributes</span></span>

<span data-ttu-id="74209-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="74209-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="74209-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="74209-111">Child Elements</span></span>

<span data-ttu-id="74209-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="74209-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="74209-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="74209-113">Parent Elements</span></span>

|<span data-ttu-id="74209-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="74209-114">Element</span></span>|<span data-ttu-id="74209-115">Описание</span><span class="sxs-lookup"><span data-stu-id="74209-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="74209-116">Элемент SelectionCondition для EntrySelectedBy для WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="74209-116">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="74209-117">Определяет условие, которое должен существовать для данного определения для использования.</span><span class="sxs-lookup"><span data-stu-id="74209-117">Defines the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="74209-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="74209-118">Text Value</span></span>

<span data-ttu-id="74209-119">Укажите сценарий, который вычисляется.</span><span class="sxs-lookup"><span data-stu-id="74209-119">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="74209-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="74209-120">Remarks</span></span>

<span data-ttu-id="74209-121">Условию выбора необходимо указать хотя бы одно имя сценария или свойство, чтобы оценить, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="74209-121">The selection condition must specify at least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="74209-122">Дополнительные сведения об использовании условий выборки см. в разделе [определение условий при отображении данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="74209-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="74209-123">Дополнительные сведения о других компонентах широкое представление, см. в разделе [широкое представление](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="74209-123">For more information about other components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="74209-124">См. также</span><span class="sxs-lookup"><span data-stu-id="74209-124">See Also</span></span>

[<span data-ttu-id="74209-125">Создание широкое представление</span><span class="sxs-lookup"><span data-stu-id="74209-125">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="74209-126">Определение условия при отображении данных</span><span class="sxs-lookup"><span data-stu-id="74209-126">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="74209-127">Элемент PropertyName для SelectionCondition для EntrySelectedBy для WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="74209-127">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="74209-128">Элемент SelectionCondition для EntrySelectedBy для WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="74209-128">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="74209-129">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="74209-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
