---
title: Элемент ScriptBlock для SelectionCondition для EntrySelectedBy для TableControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2b11fbcf-3426-48ae-9319-2c847969f723
caps.latest.revision: 10
ms.openlocfilehash: 7afc834e68ef332bee1e23da782fb5c5527fcf54
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855580"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="3f520-102">Элемент ScriptBlock для элемента SelectionCondition для элемента EntrySelectedBy для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="3f520-102">ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="3f520-103">Указывает блок скрипта, который активирует условие.</span><span class="sxs-lookup"><span data-stu-id="3f520-103">Specifies the script block that triggers the condition.</span></span> <span data-ttu-id="3f520-104">При вычислении этого сценария для `true`условие выполняется, и записи в таблице используется.</span><span class="sxs-lookup"><span data-stu-id="3f520-104">When this script is evaluated to `true`, the condition is met, and the table entry is used.</span></span>

<span data-ttu-id="3f520-105">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) TableControl-элемент (формат) элемент TableRowEntries (формат) элемент TableRowEntry (формат) EntrySelectedBy элемент конфигурации для TableRowEntry (формат) Элемент SelectionCondition для EntrySelectedBy TableRowEntry (формат) элемента ScriptBlock для SelectionCondition для EntrySelectedBy для TableRowEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="3f520-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="3f520-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3f520-106">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3f520-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3f520-107">Attributes and Elements</span></span>

<span data-ttu-id="3f520-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `ScriptBlock` элемент.</span><span class="sxs-lookup"><span data-stu-id="3f520-108">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="3f520-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3f520-109">Attributes</span></span>

<span data-ttu-id="3f520-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="3f520-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="3f520-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3f520-111">Child Elements</span></span>

<span data-ttu-id="3f520-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="3f520-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="3f520-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3f520-113">Parent Elements</span></span>

|<span data-ttu-id="3f520-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="3f520-114">Element</span></span>|<span data-ttu-id="3f520-115">Описание</span><span class="sxs-lookup"><span data-stu-id="3f520-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3f520-116">Элемент SelectionCondition для EntrySelectedBy для TableRowEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="3f520-116">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="3f520-117">Определяет условие, которое должен существовать для этой записи таблицы для использования.</span><span class="sxs-lookup"><span data-stu-id="3f520-117">Defines the condition that must exist for this table entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="3f520-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="3f520-118">Text Value</span></span>

<span data-ttu-id="3f520-119">Укажите сценарий, который вычисляется.</span><span class="sxs-lookup"><span data-stu-id="3f520-119">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="3f520-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="3f520-120">Remarks</span></span>

<span data-ttu-id="3f520-121">Условию выбора необходимо указать по крайней мере один скрипт блока или имя свойства, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="3f520-121">The selection condition must specify at least one script block or property name, but cannot specify both.</span></span> <span data-ttu-id="3f520-122">Дополнительные сведения об использовании условий выборки см. в разделе [определение условий для, когда операция отчета или элемента используется](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="3f520-122">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="3f520-123">Дополнительные сведения о компонентах в табличное представление, см. в разделе [Создание представления таблицы](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="3f520-123">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3f520-124">См. также</span><span class="sxs-lookup"><span data-stu-id="3f520-124">See Also</span></span>

[<span data-ttu-id="3f520-125">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="3f520-125">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="3f520-126">Определение условия при отображении данных</span><span class="sxs-lookup"><span data-stu-id="3f520-126">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="3f520-127">Элемент PropertyName для SelectionCondition для EntrySelectedBy для TableRowEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="3f520-127">PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)

[<span data-ttu-id="3f520-128">Элемент SelectionCondition для EntrySelectedBy для TableRowEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="3f520-128">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="3f520-129">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="3f520-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
