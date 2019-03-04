---
title: Элемент ScriptBlock для SelectionCondition для EntrySelectedBy для GroupBy (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e01344bd-ad69-4789-8e9f-2e79880c3a33
caps.latest.revision: 6
ms.openlocfilehash: cb79fb942111cee89c6b2abba75de4c494082b7e
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853080"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-groupby-format"></a><span data-ttu-id="073db-102">Элемент ScriptBlock для элемента SelectionCondition для элемента EntrySelectedBy для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="073db-102">ScriptBlock Element for SelectionCondition for EntrySelectedBy for GroupBy (Format)</span></span>

<span data-ttu-id="073db-103">Указывает сценарий, который активирует условие.</span><span class="sxs-lookup"><span data-stu-id="073db-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="073db-104">При вычислении этого сценария для `true`условие выполняется, и используется определение.</span><span class="sxs-lookup"><span data-stu-id="073db-104">When this script is evaluated to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="073db-105">Этот элемент используется при определении того, как отображается группу объектов.</span><span class="sxs-lookup"><span data-stu-id="073db-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="073db-106">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) GroupBy элемента конфигурации для элемента представления (формат) пользовательский элемент управления для элемента CustomEntries GroupBy (формат) пользовательский элемент управления для элемента CustomEntry GroupBy (формат) Пользовательский элемент управления для элемента EntrySelectedBy GroupBy (формат) для CustomEntry элемента SelectionCondition GroupBy (формат) для EntrySelectedBy GroupBy (формат) элемента ScriptBlock для SelectionCondition для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="073db-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format) ScriptBlock Element for SelectionCondition for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="073db-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="073db-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="073db-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="073db-108">Attributes and Elements</span></span>

<span data-ttu-id="073db-109">Ниже описаны атрибуты, дочерние элементы и родительский элемент `ScriptBlock` элемент.</span><span class="sxs-lookup"><span data-stu-id="073db-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="073db-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="073db-110">Attributes</span></span>

<span data-ttu-id="073db-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="073db-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="073db-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="073db-112">Child Elements</span></span>

<span data-ttu-id="073db-113">Нет.</span><span class="sxs-lookup"><span data-stu-id="073db-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="073db-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="073db-114">Parent Elements</span></span>

|<span data-ttu-id="073db-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="073db-115">Element</span></span>|<span data-ttu-id="073db-116">Описание</span><span class="sxs-lookup"><span data-stu-id="073db-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="073db-117">Элемент SelectionCondition для EntrySelectedBy для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="073db-117">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="073db-118">Определяет условие, которое должен существовать для определение элемента управления для использования.</span><span class="sxs-lookup"><span data-stu-id="073db-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="073db-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="073db-119">Text Value</span></span>

<span data-ttu-id="073db-120">Укажите сценарий, который вычисляется.</span><span class="sxs-lookup"><span data-stu-id="073db-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="073db-121">Замечания</span><span class="sxs-lookup"><span data-stu-id="073db-121">Remarks</span></span>

<span data-ttu-id="073db-122">Условию выбора необходимо указать как минимум одно имя сценария или свойство для оценки, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="073db-122">The selection condition must specify a least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="073db-123">Дополнительные сведения об использовании условий выборки см. в разделе [определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="073db-123">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="073db-124">См. также</span><span class="sxs-lookup"><span data-stu-id="073db-124">See Also</span></span>

[<span data-ttu-id="073db-125">Элемент SelectionCondition для EntrySelectedBy для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="073db-125">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="073db-126">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="073db-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
