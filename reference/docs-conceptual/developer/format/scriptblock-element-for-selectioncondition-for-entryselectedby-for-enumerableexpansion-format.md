---
title: Элемент ScriptBlock для Селектионкондитион для Ентриселектедби для Енумерабликспансион (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4126b799-c43d-4175-8513-6d761c65437e
caps.latest.revision: 9
ms.openlocfilehash: a51d8d22fa8b0c7f303a5e8f37edcc5e57724063
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368613"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="36468-102">Элемент ScriptBlock для элемента SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="36468-102">ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="36468-103">Указывает скрипт, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="36468-103">Specifies the script that triggers the condition.</span></span>

<span data-ttu-id="36468-104">Элемент конфигурации (Format) Дефаултсеттингс элемент (Format) Енумерабликспансионс элемент (Format) Енумерабликспансион элемент (Format) Ентриселектедби элемент для енумерабликспансион (Format) SelectionCondition для EntrySelectedBy Енумерабликспансион (Format) элемент ScriptBlock для Селектионкондитион для Ентриселектедби для Енумерабликспансион (Format)</span><span class="sxs-lookup"><span data-stu-id="36468-104">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="36468-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="36468-105">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="36468-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="36468-106">Attributes and Elements</span></span>

<span data-ttu-id="36468-107">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `ScriptBlock`.</span><span class="sxs-lookup"><span data-stu-id="36468-107">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="36468-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="36468-108">Attributes</span></span>

<span data-ttu-id="36468-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="36468-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="36468-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="36468-110">Child Elements</span></span>

<span data-ttu-id="36468-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="36468-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="36468-112">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="36468-112">Parent Elements</span></span>

|<span data-ttu-id="36468-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="36468-113">Element</span></span>|<span data-ttu-id="36468-114">Описание</span><span class="sxs-lookup"><span data-stu-id="36468-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="36468-115">Элемент Селектионкондитион для Ентриселектедби для Енумерабликспансион (Format)</span><span class="sxs-lookup"><span data-stu-id="36468-115">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="36468-116">Определяет условие, которое должно существовать для расширения объектов коллекции этого определения.</span><span class="sxs-lookup"><span data-stu-id="36468-116">Defines the condition that must exist to expand the collection objects of this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="36468-117">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="36468-117">Text Value</span></span>

<span data-ttu-id="36468-118">Укажите оцениваемый скрипт.</span><span class="sxs-lookup"><span data-stu-id="36468-118">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="36468-119">Замечания</span><span class="sxs-lookup"><span data-stu-id="36468-119">Remarks</span></span>

<span data-ttu-id="36468-120">Условие выбора должно указывать по крайней мере одно имя скрипта или свойства для вычисления, но не может одновременно указывать оба значения.</span><span class="sxs-lookup"><span data-stu-id="36468-120">The selection condition must specify at least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="36468-121">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="36468-121">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="36468-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="36468-122">See Also</span></span>

[<span data-ttu-id="36468-123">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="36468-123">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="36468-124">Элемент PropertyName для Селектионкондитион для Ентриселектедби для Енумерабликспансион (Format)</span><span class="sxs-lookup"><span data-stu-id="36468-124">PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="36468-125">Элемент Селектионкондитион для Ентриселектедби для Енумерабликспансион (Format)</span><span class="sxs-lookup"><span data-stu-id="36468-125">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="36468-126">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="36468-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
