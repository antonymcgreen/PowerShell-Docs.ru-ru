---
title: Элемент PropertyName для SelectionCondition для GroupBy (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d1707317-6c26-4866-bcc1-8924103c9014
caps.latest.revision: 6
ms.openlocfilehash: 7241ea0ea364befa7ad4ab0af4c4209be72214a7
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064821"
---
# <a name="propertyname-element-for-selectioncondition-for-groupby-format"></a><span data-ttu-id="09191-102">Элемент PropertyName для элемента SelectionCondition для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="09191-102">PropertyName Element for SelectionCondition for GroupBy (Format)</span></span>

<span data-ttu-id="09191-103">Задает свойство .NET, которое активирует условие.</span><span class="sxs-lookup"><span data-stu-id="09191-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="09191-104">Если этому свойству присвоено присутствует или когда оно оценивается как `true`условие выполняется, и используется определение.</span><span class="sxs-lookup"><span data-stu-id="09191-104">When this property is present or when it evaluates to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="09191-105">Этот элемент используется при определении того, как отображается группу объектов.</span><span class="sxs-lookup"><span data-stu-id="09191-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="09191-106">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) GroupBy элемента конфигурации для элемента представления (формат) пользовательский элемент управления для элемента CustomEntries GroupBy (формат) пользовательский элемент управления для элемента CustomEntry GroupBy (формат) Пользовательский элемент управления для элемента EntrySelectedBy GroupBy (формат) для CustomEntry элемента SelectionCondition GroupBy (формат) для EntrySelectedBy элемента PropertyName GroupBy (формат) для SelectionCondition для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="09191-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format) PropertyName Element for SelectionCondition for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="09191-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="09191-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="09191-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="09191-108">Attributes and Elements</span></span>

<span data-ttu-id="09191-109">Ниже описаны атрибуты, дочерние элементы и родительский элемент `PropertyName` элемент.</span><span class="sxs-lookup"><span data-stu-id="09191-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="09191-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="09191-110">Attributes</span></span>

<span data-ttu-id="09191-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="09191-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="09191-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="09191-112">Child Elements</span></span>

<span data-ttu-id="09191-113">Нет.</span><span class="sxs-lookup"><span data-stu-id="09191-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="09191-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="09191-114">Parent Elements</span></span>

|<span data-ttu-id="09191-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="09191-115">Element</span></span>|<span data-ttu-id="09191-116">Описание</span><span class="sxs-lookup"><span data-stu-id="09191-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="09191-117">Элемент SelectionCondition для EntrySelectedBy для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="09191-117">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="09191-118">Определяет условие, которое должен существовать для определение элемента управления для использования.</span><span class="sxs-lookup"><span data-stu-id="09191-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="09191-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="09191-119">Text Value</span></span>

<span data-ttu-id="09191-120">Укажите имя свойства .NET.</span><span class="sxs-lookup"><span data-stu-id="09191-120">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="09191-121">Замечания</span><span class="sxs-lookup"><span data-stu-id="09191-121">Remarks</span></span>

<span data-ttu-id="09191-122">Условию выбора необходимо указать имя как минимум одно свойство или сценария, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="09191-122">The selection condition must specify a least one property name or a script, but cannot specify both.</span></span> <span data-ttu-id="09191-123">Дополнительные сведения об использовании условий выборки см. в разделе [определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="09191-123">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="09191-124">См. также</span><span class="sxs-lookup"><span data-stu-id="09191-124">See Also</span></span>

[<span data-ttu-id="09191-125">Элемент SelectionCondition для EntrySelectedBy для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="09191-125">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="09191-126">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="09191-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
