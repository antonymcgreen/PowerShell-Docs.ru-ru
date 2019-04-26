---
title: Элемент PropertyName для SelectionCondition для EntrySelectedBy для TableRowEntry (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ba3b4d9b-2b8c-4a3a-8887-6c606eb9d490
caps.latest.revision: 10
ms.openlocfilehash: 48011950ed64e78a84292762f2c7779003dc59fd
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62064668"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format"></a><span data-ttu-id="2191d-102">Элемент PropertyName для элемента SelectionCondition для элемента EntrySelectedBy для элемента TableRowEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="2191d-102">PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>

<span data-ttu-id="2191d-103">Задает свойство .NET, которое активирует условие.</span><span class="sxs-lookup"><span data-stu-id="2191d-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="2191d-104">Если этому свойству присвоено присутствует или когда оно оценивается как `true`условие выполняется, и записи в таблице используется.</span><span class="sxs-lookup"><span data-stu-id="2191d-104">When this property is present or when it evaluates to `true`, the condition is met, and the table entry is used.</span></span>

<span data-ttu-id="2191d-105">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) TableControl-элемент (формат) элемент TableRowEntries (формат) элемент TableRowEntry (формат) EntrySelectedBy элемент конфигурации для TableRowEntry (формат) Элемент SelectionCondition для EntrySelectedBy элемента PropertyName TableRowEntry (формат) для SelectionCondition для EntrySelectedBy для TableRowEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="2191d-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2191d-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2191d-106">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2191d-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2191d-107">Attributes and Elements</span></span>

<span data-ttu-id="2191d-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `PropertyName` элемент.</span><span class="sxs-lookup"><span data-stu-id="2191d-108">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="2191d-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2191d-109">Attributes</span></span>

<span data-ttu-id="2191d-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="2191d-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2191d-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2191d-111">Child Elements</span></span>

<span data-ttu-id="2191d-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="2191d-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2191d-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2191d-113">Parent Elements</span></span>

|<span data-ttu-id="2191d-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="2191d-114">Element</span></span>|<span data-ttu-id="2191d-115">Описание</span><span class="sxs-lookup"><span data-stu-id="2191d-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2191d-116">Элемент SelectionCondition для EntrySelectedBy для TableRowEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="2191d-116">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="2191d-117">Определяет условие, которое должен существовать для этой записи таблицы для использования.</span><span class="sxs-lookup"><span data-stu-id="2191d-117">Defines the condition that must exist for this table entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="2191d-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="2191d-118">Text Value</span></span>

<span data-ttu-id="2191d-119">Укажите имя свойства .NET.</span><span class="sxs-lookup"><span data-stu-id="2191d-119">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="2191d-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="2191d-120">Remarks</span></span>

<span data-ttu-id="2191d-121">Условию выбора необходимо указать по крайней мере для одного имени свойства или блок скрипта, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="2191d-121">The selection condition must specify at least one property name or a script block, but cannot specify both.</span></span> <span data-ttu-id="2191d-122">Дополнительные сведения об использовании условий выборки см. в разделе [определение условий для, когда операция отчета или элемента используется](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="2191d-122">For more information about how selection conditions can be used, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="2191d-123">Дополнительные сведения о компонентах в табличное представление, см. в разделе [Создание представления таблицы](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="2191d-123">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2191d-124">См. также</span><span class="sxs-lookup"><span data-stu-id="2191d-124">See Also</span></span>

[<span data-ttu-id="2191d-125">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="2191d-125">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="2191d-126">Определение условия при отображении данных</span><span class="sxs-lookup"><span data-stu-id="2191d-126">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="2191d-127">Элемент ScriptBlock для SelectionCondition для EntrySelectedBy для TableRowEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="2191d-127">ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="2191d-128">Элемент SelectionCondition для EntrySelectedBy для TableRowEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="2191d-128">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="2191d-129">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="2191d-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
