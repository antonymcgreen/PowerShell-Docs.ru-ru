---
ms.date: 09/13/2016
ms.topic: reference
title: Элемент TypeName для элемента SelectionCondition для элемента EntrySelectedBy для элемента ListControl (формат)
description: Элемент TypeName для элемента SelectionCondition для элемента EntrySelectedBy для элемента ListControl (формат)
ms.openlocfilehash: 2e8246e3ef2cba38824d8f8004acfffc3236df13
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645558"
---
# <a name="typename-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="d29ab-103">Элемент TypeName для элемента SelectionCondition для элемента EntrySelectedBy для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="d29ab-103">TypeName Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="d29ab-104">Указывает тип .NET, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="d29ab-104">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="d29ab-105">При наличии этого типа используется запись списка.</span><span class="sxs-lookup"><span data-stu-id="d29ab-105">When this type is present, the list entry is used.</span></span>

<span data-ttu-id="d29ab-106">Элемент конфигурации (Format) Виевдефинитионс элемент (Format) элемент представления (формат) ListControl элемент (Format) Листентриес для ListControl (Format) Листентри элемент для листентриес для ListControl (Format) ентриселектедби для листентри for ListControl (формат) селектионкондитион элемента for EntrySelectedBy for ListControl для SelectionCondition (Format).</span><span class="sxs-lookup"><span data-stu-id="d29ab-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) EntrySelectedBy Element for ListEntry for ListControl (Format) SelectionCondition Element for EntrySelectedBy for ListControl (Format) TypeName Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d29ab-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d29ab-107">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d29ab-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d29ab-108">Attributes and Elements</span></span>

<span data-ttu-id="d29ab-109">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `TypeName` элемента.</span><span class="sxs-lookup"><span data-stu-id="d29ab-109">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d29ab-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d29ab-110">Attributes</span></span>

<span data-ttu-id="d29ab-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d29ab-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d29ab-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d29ab-112">Child Elements</span></span>

<span data-ttu-id="d29ab-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d29ab-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d29ab-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d29ab-114">Parent Elements</span></span>

|<span data-ttu-id="d29ab-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="d29ab-115">Element</span></span>|<span data-ttu-id="d29ab-116">Описание</span><span class="sxs-lookup"><span data-stu-id="d29ab-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d29ab-117">Элемент SelectionCondition для элемента EntrySelectedBy для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="d29ab-117">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="d29ab-118">Определяет условие, которое должно существовать для использования этой записи списка.</span><span class="sxs-lookup"><span data-stu-id="d29ab-118">Defines the condition that must exist for this list entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="d29ab-119">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="d29ab-119">Text Value</span></span>

<span data-ttu-id="d29ab-120">Укажите полное имя типа .NET, например `System.IO.DirectoryInfo` .</span><span class="sxs-lookup"><span data-stu-id="d29ab-120">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="d29ab-121">Комментарии</span><span class="sxs-lookup"><span data-stu-id="d29ab-121">Remarks</span></span>

<span data-ttu-id="d29ab-122">Условие выбора может указывать любое количество типов .NET или наборов выбора, но не может одновременно указывать оба типа.</span><span class="sxs-lookup"><span data-stu-id="d29ab-122">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span> <span data-ttu-id="d29ab-123">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="d29ab-123">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="d29ab-124">Дополнительные сведения о других компонентах представления списка см. [в разделе Создание представления списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="d29ab-124">For more information about other the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d29ab-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="d29ab-125">See Also</span></span>

[<span data-ttu-id="d29ab-126">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="d29ab-126">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="d29ab-127">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="d29ab-127">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="d29ab-128">Элемент SelectionCondition для элемента EntrySelectedBy для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="d29ab-128">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="d29ab-129">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="d29ab-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
