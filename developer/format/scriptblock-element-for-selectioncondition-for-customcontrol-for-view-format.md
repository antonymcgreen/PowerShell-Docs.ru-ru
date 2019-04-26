---
title: Элемент ScriptBlock для SelectionCondition для пользовательский элемент управления для представления (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7031fa8b-3e2b-4ea8-89cb-95171f467b5a
caps.latest.revision: 6
ms.openlocfilehash: e55d1c5aa533005b258ecbbbf3ed9d55f852eab6
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064566"
---
# <a name="scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format"></a><span data-ttu-id="f8044-102">Элемент ScriptBlock для элемента SelectionCondition для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="f8044-102">ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>

<span data-ttu-id="f8044-103">Указывает сценарий, который активирует условие.</span><span class="sxs-lookup"><span data-stu-id="f8044-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="f8044-104">При вычислении этого сценария для `true`условие выполняется, и используется определение.</span><span class="sxs-lookup"><span data-stu-id="f8044-104">When this script is evaluated to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="f8044-105">Этот элемент используется при определении представления пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="f8044-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="f8044-106">Конфигурации элемента (формат) элемент ViewDefinitions (формат) элемент (формат) пользовательский элемент управления элемента представления для элемента представления (формат) CustomEntries для пользовательский элемент управления для элемента представления (формат) CustomEntry для CustomEntries для пользовательский элемент управления (представление Элемент CustomItem Format) для CustomEntry для пользовательский элемент управления для элемента представления (формат) SelectionCondition для EntrySelectedBy для пользовательский элемент управления для элемента представления (формат) ScriptBlock для SelectionCondition для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="f8044-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for CustomControl for View (Format) CustomItem Element for CustomEntry for CustomControl for View (Format) SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format) ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f8044-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f8044-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f8044-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f8044-108">Attributes and Elements</span></span>

<span data-ttu-id="f8044-109">Ниже описаны атрибуты, дочерние элементы и родительский элемент `ScriptBlock` элемент.</span><span class="sxs-lookup"><span data-stu-id="f8044-109">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f8044-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f8044-110">Attributes</span></span>

<span data-ttu-id="f8044-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="f8044-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f8044-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f8044-112">Child Elements</span></span>

<span data-ttu-id="f8044-113">Нет.</span><span class="sxs-lookup"><span data-stu-id="f8044-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f8044-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f8044-114">Parent Elements</span></span>

|<span data-ttu-id="f8044-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="f8044-115">Element</span></span>|<span data-ttu-id="f8044-116">Описание</span><span class="sxs-lookup"><span data-stu-id="f8044-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f8044-117">Элемент SelectionCondition для EntrySelectedBy для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="f8044-117">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|<span data-ttu-id="f8044-118">Определяет условие, которое должен существовать для определение элемента управления для использования.</span><span class="sxs-lookup"><span data-stu-id="f8044-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f8044-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="f8044-119">Text Value</span></span>

<span data-ttu-id="f8044-120">Укажите сценарий, который вычисляется.</span><span class="sxs-lookup"><span data-stu-id="f8044-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="f8044-121">Замечания</span><span class="sxs-lookup"><span data-stu-id="f8044-121">Remarks</span></span>

<span data-ttu-id="f8044-122">Условию выбора необходимо указать как минимум одно имя сценария или свойство для оценки, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="f8044-122">The selection condition must specify a least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="f8044-123">Дополнительные сведения об использовании условий выборки см. в разделе [определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="f8044-123">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f8044-124">См. также</span><span class="sxs-lookup"><span data-stu-id="f8044-124">See Also</span></span>

[<span data-ttu-id="f8044-125">Элемент SelectionCondition для EntrySelectedBy для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="f8044-125">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[<span data-ttu-id="f8044-126">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="f8044-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
