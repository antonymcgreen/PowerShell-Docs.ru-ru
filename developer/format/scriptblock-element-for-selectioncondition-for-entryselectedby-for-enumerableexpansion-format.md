---
title: Элемент ScriptBlock для SelectionCondition для EntrySelectedBy для EnumerableExpansion (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4126b799-c43d-4175-8513-6d761c65437e
caps.latest.revision: 9
ms.openlocfilehash: a51d8d22fa8b0c7f303a5e8f37edcc5e57724063
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854800"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="1ce1d-102">Элемент ScriptBlock для элемента SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="1ce1d-102">ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="1ce1d-103">Указывает сценарий, который активирует условие.</span><span class="sxs-lookup"><span data-stu-id="1ce1d-103">Specifies the script that triggers the condition.</span></span>

<span data-ttu-id="1ce1d-104">Элемент (формат) элемент DefaultSettings (формат) элемент EnumerableExpansions (формат) элемент EnumerableExpansion (формат) EntrySelectedBy элемента конфигурации для элемента SelectionCondition EnumerableExpansion (формат) EntrySelectedBy для Элемент ScriptBlock EnumerableExpansion (формат) для SelectionCondition для EntrySelectedBy для EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="1ce1d-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="1ce1d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1ce1d-105">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1ce1d-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1ce1d-106">Attributes and Elements</span></span>

<span data-ttu-id="1ce1d-107">Ниже описаны атрибуты, дочерние элементы и родительский элемент `ScriptBlock` элемент.</span><span class="sxs-lookup"><span data-stu-id="1ce1d-107">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="1ce1d-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1ce1d-108">Attributes</span></span>

<span data-ttu-id="1ce1d-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="1ce1d-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1ce1d-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1ce1d-110">Child Elements</span></span>

<span data-ttu-id="1ce1d-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="1ce1d-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="1ce1d-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1ce1d-112">Parent Elements</span></span>

|<span data-ttu-id="1ce1d-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="1ce1d-113">Element</span></span>|<span data-ttu-id="1ce1d-114">Описание</span><span class="sxs-lookup"><span data-stu-id="1ce1d-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1ce1d-115">Элемент SelectionCondition для EntrySelectedBy для EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="1ce1d-115">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="1ce1d-116">Определяет условие, которое должно существовать разверните коллекцию объектов данного определения.</span><span class="sxs-lookup"><span data-stu-id="1ce1d-116">Defines the condition that must exist to expand the collection objects of this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="1ce1d-117">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="1ce1d-117">Text Value</span></span>

<span data-ttu-id="1ce1d-118">Укажите сценарий, который вычисляется.</span><span class="sxs-lookup"><span data-stu-id="1ce1d-118">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="1ce1d-119">Замечания</span><span class="sxs-lookup"><span data-stu-id="1ce1d-119">Remarks</span></span>

<span data-ttu-id="1ce1d-120">Условию выбора необходимо указать хотя бы одно имя сценария или свойство, чтобы оценить, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="1ce1d-120">The selection condition must specify at least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="1ce1d-121">Дополнительные сведения об использовании условий выборки см. в разделе [определение условий при отображении данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="1ce1d-121">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1ce1d-122">См. также</span><span class="sxs-lookup"><span data-stu-id="1ce1d-122">See Also</span></span>

[<span data-ttu-id="1ce1d-123">Определение условия при отображении данных</span><span class="sxs-lookup"><span data-stu-id="1ce1d-123">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="1ce1d-124">Элемент PropertyName для SelectionCondition для EntrySelectedBy для EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="1ce1d-124">PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="1ce1d-125">Элемент SelectionCondition для EntrySelectedBy для EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="1ce1d-125">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="1ce1d-126">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="1ce1d-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
