---
title: Элемент ScriptBlock для SelectionCondition для EntrySelectedBy для ListControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4a1adad7-e864-4892-9d26-a6476a9698d2
caps.latest.revision: 7
ms.openlocfilehash: b65d953169f6daf15fb617ce4d0303cf4cb584ee
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58057779"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="34e0e-102">Элемент ScriptBlock для элемента SelectionCondition для элемента EntrySelectedBy для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="34e0e-102">ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="34e0e-103">Указывает сценарий, который активирует условие.</span><span class="sxs-lookup"><span data-stu-id="34e0e-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="34e0e-104">При вычислении этого сценария для `true`условие выполняется, и используется элемент списка.</span><span class="sxs-lookup"><span data-stu-id="34e0e-104">When this script is evaluated to `true`, the condition is met, and the list entry is used.</span></span>

<span data-ttu-id="34e0e-105">Элемент (формат) элемент ViewDefinitions (формат) представление элемент (формат) элемента ListControl (формат) элемент ListEntries (формат) элемент ListEntry (формат) EntrySelectedBy элемент конфигурации для элемента SelectionCondition ListEntry (формат) для EntrySelectedBy ListEntry (формат) элемента ScriptBlock для SelectionCondition для EntrySelectedBy для ListEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="34e0e-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="34e0e-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="34e0e-106">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="34e0e-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="34e0e-107">Attributes and Elements</span></span>

<span data-ttu-id="34e0e-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `ScriptBlock` элемент.</span><span class="sxs-lookup"><span data-stu-id="34e0e-108">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="34e0e-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="34e0e-109">Attributes</span></span>

<span data-ttu-id="34e0e-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="34e0e-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="34e0e-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="34e0e-111">Child Elements</span></span>

<span data-ttu-id="34e0e-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="34e0e-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="34e0e-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="34e0e-113">Parent Elements</span></span>

|<span data-ttu-id="34e0e-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="34e0e-114">Element</span></span>|<span data-ttu-id="34e0e-115">Описание</span><span class="sxs-lookup"><span data-stu-id="34e0e-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="34e0e-116">Элемент SelectionCondition для EntrySelectedBy для ListEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="34e0e-116">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="34e0e-117">Определяет условие, которое должен существовать для записи в этом списке для использования.</span><span class="sxs-lookup"><span data-stu-id="34e0e-117">Defines the condition that must exist for this list entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="34e0e-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="34e0e-118">Text Value</span></span>

<span data-ttu-id="34e0e-119">Укажите сценарий, который вычисляется.</span><span class="sxs-lookup"><span data-stu-id="34e0e-119">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="34e0e-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="34e0e-120">Remarks</span></span>

<span data-ttu-id="34e0e-121">Условию выбора необходимо указать как минимум одно имя сценария или свойство для оценки, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="34e0e-121">The selection condition must specify a least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="34e0e-122">(Дополнительные сведения об использовании условий выборки см. в разделе [определение условий для, когда операция отчета или элемента используется](./defining-conditions-for-displaying-data.md).)</span><span class="sxs-lookup"><span data-stu-id="34e0e-122">(For more information about how selection conditions can be used, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).)</span></span>

<span data-ttu-id="34e0e-123">Дополнительные сведения о других компонентов представления списка, см. в разделе [представление списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="34e0e-123">For more information about the other components of a list view, see [List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="34e0e-124">См. также</span><span class="sxs-lookup"><span data-stu-id="34e0e-124">See Also</span></span>

[<span data-ttu-id="34e0e-125">Элемент ListEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="34e0e-125">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="34e0e-126">Элемент PropertyName для SelectionCondition для EntrySelectedBy для ListEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="34e0e-126">PropertyName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="34e0e-127">Элемент SelectionCondition для EntrySelectedBy для ListEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="34e0e-127">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="34e0e-128">Представление списка</span><span class="sxs-lookup"><span data-stu-id="34e0e-128">List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="34e0e-129">Определение условия, при использовании операции отчета или элемента</span><span class="sxs-lookup"><span data-stu-id="34e0e-129">Defining Conditions for when a View Entry or Item is Used</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="34e0e-130">Написание форматирования Windows PowerShell и типы файлов</span><span class="sxs-lookup"><span data-stu-id="34e0e-130">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
