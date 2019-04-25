---
title: TypeName-элемент для SelectionCondition для EntrySelectedBy для ListControl (формат) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bd025a3a-3780-40db-a068-873e7df38015
caps.latest.revision: 9
ms.openlocfilehash: 2b76b040b39088cc9c3b9d6890c38df3c533b39f
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083864"
---
# <a name="typename-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="b593b-102">Элемент TypeName для элемента SelectionCondition для элемента EntrySelectedBy для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="b593b-102">TypeName Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="b593b-103">Указывает тип .NET, который активирует условие.</span><span class="sxs-lookup"><span data-stu-id="b593b-103">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="b593b-104">При наличии этого типа используется элемент списка.</span><span class="sxs-lookup"><span data-stu-id="b593b-104">When this type is present, the list entry is used.</span></span>

<span data-ttu-id="b593b-105">Элемент (формат) элемент ViewDefinitions (формат) представление элемента (формат) элемента ListControl (формат) ListEntries элемента конфигурации для элемента ListControl (формат) ListEntry ListEntries для EntrySelectedBy элемента ListControl (формат) ListEntry для элемента ListControl (формат) SelectionCondition EntrySelectedBy для элемента ListControl (формат) TypeName SelectionCondition для EntrySelectedBy для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="b593b-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) EntrySelectedBy Element for ListEntry for ListControl (Format) SelectionCondition Element for EntrySelectedBy for ListControl (Format) TypeName Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b593b-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b593b-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b593b-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b593b-107">Attributes and Elements</span></span>

<span data-ttu-id="b593b-108">Ниже описаны атрибуты, дочерние элементы и родительский элемент `TypeName` элемент.</span><span class="sxs-lookup"><span data-stu-id="b593b-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b593b-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b593b-109">Attributes</span></span>

<span data-ttu-id="b593b-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="b593b-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b593b-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b593b-111">Child Elements</span></span>

<span data-ttu-id="b593b-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="b593b-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b593b-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b593b-113">Parent Elements</span></span>

|<span data-ttu-id="b593b-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="b593b-114">Element</span></span>|<span data-ttu-id="b593b-115">Описание</span><span class="sxs-lookup"><span data-stu-id="b593b-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b593b-116">Элемент SelectionCondition для EntrySelectedBy для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="b593b-116">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="b593b-117">Определяет условие, которое должен существовать для записи в этом списке для использования.</span><span class="sxs-lookup"><span data-stu-id="b593b-117">Defines the condition that must exist for this list entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="b593b-118">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="b593b-118">Text Value</span></span>

<span data-ttu-id="b593b-119">Укажите полное имя типа .NET, например `System.IO.DirectoryInfo`.</span><span class="sxs-lookup"><span data-stu-id="b593b-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="b593b-120">Замечания</span><span class="sxs-lookup"><span data-stu-id="b593b-120">Remarks</span></span>

<span data-ttu-id="b593b-121">Условию выбора можно указать любое число типов .NET или выбора задает, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="b593b-121">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span> <span data-ttu-id="b593b-122">Дополнительные сведения об использовании условий выборки см. в разделе [определение условий при отображении данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="b593b-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="b593b-123">Дополнительные сведения о других компонентов представления списка, см. в разделе [Создание представления списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="b593b-123">For more information about other the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b593b-124">См. также</span><span class="sxs-lookup"><span data-stu-id="b593b-124">See Also</span></span>

[<span data-ttu-id="b593b-125">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="b593b-125">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="b593b-126">Определение условия при отображении данных</span><span class="sxs-lookup"><span data-stu-id="b593b-126">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="b593b-127">Элемент SelectionCondition для EntrySelectedBy для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="b593b-127">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="b593b-128">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="b593b-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
