---
title: TypeName-элемент для SelectionCondition для EntrySelectedBy для TableControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e97d56fb-4e35-447a-9282-26f10d0a4609
caps.latest.revision: 11
ms.openlocfilehash: fe65ac95cead7df0069ffdae666fb34b7309fbb6
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083847"
---
# <a name="typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="f37d2-102">Элемент TypeName для элемента SelectionCondition для элемента EntrySelectedBy для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="f37d2-102">TypeName Element for SelectionCondition for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="f37d2-103">Указывает тип .NET, который активирует условие.</span><span class="sxs-lookup"><span data-stu-id="f37d2-103">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="f37d2-104">При наличии этого типа условие выполняется, и используется строке таблицы.</span><span class="sxs-lookup"><span data-stu-id="f37d2-104">When this type is present, the condition is met, and the table row is used.</span></span>

<span data-ttu-id="f37d2-105">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) TableControl-элемент (формат) элемент TableRowEntries (формат) элемент TableRowEntry (формат) EntrySelectedBy элемент конфигурации для TableRowEntry (формат) Элемент SelectionCondition для EntrySelectedBy элемента TypeName TableRowEntry (формат) для SelectionCondition для EntrySelectedBy для TableRowEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="f37d2-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format) TypeName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f37d2-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f37d2-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f37d2-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f37d2-107">Attributes and Elements</span></span>

<span data-ttu-id="f37d2-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `TypeName` элемент.</span><span class="sxs-lookup"><span data-stu-id="f37d2-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f37d2-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f37d2-109">Attributes</span></span>

<span data-ttu-id="f37d2-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="f37d2-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f37d2-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f37d2-111">Child Elements</span></span>

<span data-ttu-id="f37d2-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="f37d2-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f37d2-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f37d2-113">Parent Elements</span></span>

|<span data-ttu-id="f37d2-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="f37d2-114">Element</span></span>|<span data-ttu-id="f37d2-115">Описание</span><span class="sxs-lookup"><span data-stu-id="f37d2-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f37d2-116">Элемент SelectionCondition для EntrySelectedBy для TableRowEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="f37d2-116">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="f37d2-117">Определяет условие, которое должен существовать для строки таблицы для использования.</span><span class="sxs-lookup"><span data-stu-id="f37d2-117">Defines the condition that must exist for this table row to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f37d2-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="f37d2-118">Text Value</span></span>

<span data-ttu-id="f37d2-119">Укажите полное имя типа .NET, например `System.IO.DirectoryInfo`.</span><span class="sxs-lookup"><span data-stu-id="f37d2-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="f37d2-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="f37d2-120">Remarks</span></span>

<span data-ttu-id="f37d2-121">Условию выбора можно указать любое число типов .NET или выбора задает, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="f37d2-121">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span> <span data-ttu-id="f37d2-122">Дополнительные сведения об использовании условий выборки см. в разделе [определение условий для, когда операция отчета или элемента используется](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="f37d2-122">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="f37d2-123">Дополнительные сведения о компонентах в табличное представление, см. в разделе [Создание представления таблицы](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="f37d2-123">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f37d2-124">См. также</span><span class="sxs-lookup"><span data-stu-id="f37d2-124">See Also</span></span>

[<span data-ttu-id="f37d2-125">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="f37d2-125">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="f37d2-126">Определение условия при отображении данных</span><span class="sxs-lookup"><span data-stu-id="f37d2-126">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="f37d2-127">Элемент SelectionCondition для EntrySelectedBy для TableRowEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="f37d2-127">SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="f37d2-128">Элемент SelectionSetName для SelectionCondition для EntrySelectedBy для TableRowEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="f37d2-128">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="f37d2-129">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="f37d2-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
