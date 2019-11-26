---
title: Элемент Селектионкондитион для Ентриселектедби для ListControl (Format) | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7649d5d0-2b56-49b5-a670-dde46caca343
caps.latest.revision: 11
ms.openlocfilehash: 7150b29ad84dfb587215ee3e64c356adbd5a6305
ms.sourcegitcommit: d43f66071f1f33b350d34fa1f46f3a35910c5d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74417537"
---
# <a name="selectioncondition-element-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="8d46f-102">Элемент SelectionCondition для элемента EntrySelectedBy для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="8d46f-102">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="8d46f-103">Определяет условие, которое должно существовать для использования этого определения представления списка.</span><span class="sxs-lookup"><span data-stu-id="8d46f-103">Defines the condition that must exist to use this definition of the list view.</span></span> <span data-ttu-id="8d46f-104">Количество условий выбора, которое можно указать для определения списка, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="8d46f-104">There is no limit to the number of selection conditions that can be specified for a list definition.</span></span>

<span data-ttu-id="8d46f-105">Элемент конфигурации (Format) Виевдефинитионс элемент представления (Format) элемент (формат) ListControl элемент (Format) Листентриес элемент (Format) Листентри элемент (Format) Ентриселектедби для Листентри (Format) Селектионкондитион элемент для Ентриселектедби для Листентри (формат)</span><span class="sxs-lookup"><span data-stu-id="8d46f-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="8d46f-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8d46f-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8d46f-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8d46f-107">Attributes and Elements</span></span>

<span data-ttu-id="8d46f-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент элемента `SelectionCondition`.</span><span class="sxs-lookup"><span data-stu-id="8d46f-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="8d46f-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8d46f-109">Attributes</span></span>

<span data-ttu-id="8d46f-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="8d46f-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8d46f-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8d46f-111">Child Elements</span></span>

|<span data-ttu-id="8d46f-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="8d46f-112">Element</span></span>|<span data-ttu-id="8d46f-113">Описание</span><span class="sxs-lookup"><span data-stu-id="8d46f-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8d46f-114">Элемент PropertyName для Селектионкондитион для Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="8d46f-114">PropertyName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="8d46f-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="8d46f-115">Optional element.</span></span><br /><br /> <span data-ttu-id="8d46f-116">Указывает свойство .NET, которое запускает условие.</span><span class="sxs-lookup"><span data-stu-id="8d46f-116">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="8d46f-117">Элемент ScriptBlock для Селектионкондитион для Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="8d46f-117">ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="8d46f-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="8d46f-118">Optional element.</span></span><br /><br /> <span data-ttu-id="8d46f-119">Указывает скрипт, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="8d46f-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="8d46f-120">Элемент Селектионсетнаме для Селектионкондитион для Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="8d46f-120">SelectionSetName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-listentry-format.md)|<span data-ttu-id="8d46f-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="8d46f-121">Optional element.</span></span><br /><br /> <span data-ttu-id="8d46f-122">Указывает набор типов .NET, которые активируют условие.</span><span class="sxs-lookup"><span data-stu-id="8d46f-122">Specifies the set of .NET types that trigger the condition.</span></span>|
|[<span data-ttu-id="8d46f-123">Элемент TypeName для Селектионкондитион для Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="8d46f-123">TypeName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="8d46f-124">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="8d46f-124">Optional element.</span></span><br /><br /> <span data-ttu-id="8d46f-125">Указывает тип .NET, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="8d46f-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="8d46f-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8d46f-126">Parent Elements</span></span>

|<span data-ttu-id="8d46f-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="8d46f-127">Element</span></span>|<span data-ttu-id="8d46f-128">Описание</span><span class="sxs-lookup"><span data-stu-id="8d46f-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8d46f-129">Элемент Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="8d46f-129">EntrySelectedBy Element for TableRowEntry (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="8d46f-130">Определяет типы .NET, которые используют эту запись таблицы, или условие, которое должно существовать для использования этой записи.</span><span class="sxs-lookup"><span data-stu-id="8d46f-130">Defines the .NET types that use this table entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="8d46f-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="8d46f-131">Remarks</span></span>

<span data-ttu-id="8d46f-132">Лвхен вы определяете условие выбора, применяются следующие требования.</span><span class="sxs-lookup"><span data-stu-id="8d46f-132">lWhen you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="8d46f-133">Условие выбора должно указывать по крайней мере одно имя свойства или блок скрипта, но не может указывать и то и другое.</span><span class="sxs-lookup"><span data-stu-id="8d46f-133">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="8d46f-134">Условие выбора может указывать любое количество типов .NET или наборов выбора, но не может одновременно указывать оба типа.</span><span class="sxs-lookup"><span data-stu-id="8d46f-134">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="8d46f-135">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="8d46f-135">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="8d46f-136">Дополнительные сведения о других компонентах представления списка см. в разделе [Создание представления списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="8d46f-136">For more information about other components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8d46f-137">См. также</span><span class="sxs-lookup"><span data-stu-id="8d46f-137">See Also</span></span>

[<span data-ttu-id="8d46f-138">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="8d46f-138">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="8d46f-139">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="8d46f-139">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="8d46f-140">Элемент Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="8d46f-140">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="8d46f-141">Элемент Селектионсетнаме для Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="8d46f-141">SelectionSetName Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="8d46f-142">Элемент TypeName для Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="8d46f-142">TypeName Element for EntrySelectedBy for ListEntry (Format)</span></span>](/powershell/scripting/developer/format/typename-element-for-entryselectedby-for-listcontrol-format)

[<span data-ttu-id="8d46f-143">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="8d46f-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
