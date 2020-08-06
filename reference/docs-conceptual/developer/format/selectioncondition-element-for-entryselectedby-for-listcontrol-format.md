---
title: Элемент Селектионкондитион для Ентриселектедби для ListControl (Format) | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 29626b181f21d168e1ebf973e01afeb411d9ef54
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772779"
---
# <a name="selectioncondition-element-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="4e1ea-102">Элемент SelectionCondition для элемента EntrySelectedBy для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="4e1ea-102">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="4e1ea-103">Определяет условие, которое должно существовать для использования этого определения представления списка.</span><span class="sxs-lookup"><span data-stu-id="4e1ea-103">Defines the condition that must exist to use this definition of the list view.</span></span> <span data-ttu-id="4e1ea-104">Количество условий выбора, которое можно указать для определения списка, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="4e1ea-104">There is no limit to the number of selection conditions that can be specified for a list definition.</span></span>

<span data-ttu-id="4e1ea-105">Элемент конфигурации (Format) Виевдефинитионс элемент (формат) элемент представления (Format) ListControl элемент (Format) Листентриес элемент (Format) Листентри элемент (Format) Ентриселектедби для листентри (Format) Селектионкондитион для EntrySelectedBy в ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="4e1ea-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4e1ea-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4e1ea-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4e1ea-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4e1ea-107">Attributes and Elements</span></span>

<span data-ttu-id="4e1ea-108">В следующих разделах описываются атрибуты, дочерние элементы и родительский элемент `SelectionCondition` элемента.</span><span class="sxs-lookup"><span data-stu-id="4e1ea-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="4e1ea-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4e1ea-109">Attributes</span></span>

<span data-ttu-id="4e1ea-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="4e1ea-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4e1ea-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4e1ea-111">Child Elements</span></span>

|<span data-ttu-id="4e1ea-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="4e1ea-112">Element</span></span>|<span data-ttu-id="4e1ea-113">Описание</span><span class="sxs-lookup"><span data-stu-id="4e1ea-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4e1ea-114">Элемент PropertyName для Селектионкондитион для Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="4e1ea-114">PropertyName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="4e1ea-115">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="4e1ea-115">Optional element.</span></span><br /><br /> <span data-ttu-id="4e1ea-116">Указывает свойство .NET, которое запускает условие.</span><span class="sxs-lookup"><span data-stu-id="4e1ea-116">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="4e1ea-117">Элемент ScriptBlock для Селектионкондитион для Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="4e1ea-117">ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="4e1ea-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="4e1ea-118">Optional element.</span></span><br /><br /> <span data-ttu-id="4e1ea-119">Указывает скрипт, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="4e1ea-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="4e1ea-120">Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента ListEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="4e1ea-120">SelectionSetName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-listentry-format.md)|<span data-ttu-id="4e1ea-121">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="4e1ea-121">Optional element.</span></span><br /><br /> <span data-ttu-id="4e1ea-122">Указывает набор типов .NET, которые активируют условие.</span><span class="sxs-lookup"><span data-stu-id="4e1ea-122">Specifies the set of .NET types that trigger the condition.</span></span>|
|[<span data-ttu-id="4e1ea-123">Элемент TypeName для Селектионкондитион для Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="4e1ea-123">TypeName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="4e1ea-124">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="4e1ea-124">Optional element.</span></span><br /><br /> <span data-ttu-id="4e1ea-125">Указывает тип .NET, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="4e1ea-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="4e1ea-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4e1ea-126">Parent Elements</span></span>

|<span data-ttu-id="4e1ea-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="4e1ea-127">Element</span></span>|<span data-ttu-id="4e1ea-128">Описание</span><span class="sxs-lookup"><span data-stu-id="4e1ea-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4e1ea-129">Элемент Ентриселектедби для Таблеровентри (Format)</span><span class="sxs-lookup"><span data-stu-id="4e1ea-129">EntrySelectedBy Element for TableRowEntry (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="4e1ea-130">Определяет типы .NET, которые используют эту запись таблицы, или условие, которое должно существовать для использования этой записи.</span><span class="sxs-lookup"><span data-stu-id="4e1ea-130">Defines the .NET types that use this table entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="4e1ea-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="4e1ea-131">Remarks</span></span>

<span data-ttu-id="4e1ea-132">Лвхен вы определяете условие выбора, применяются следующие требования.</span><span class="sxs-lookup"><span data-stu-id="4e1ea-132">lWhen you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="4e1ea-133">Условие выбора должно указывать по крайней мере одно имя свойства или блок скрипта, но не может указывать и то и другое.</span><span class="sxs-lookup"><span data-stu-id="4e1ea-133">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="4e1ea-134">Условие выбора может указывать любое количество типов .NET или наборов выбора, но не может одновременно указывать оба типа.</span><span class="sxs-lookup"><span data-stu-id="4e1ea-134">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="4e1ea-135">Дополнительные сведения об использовании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="4e1ea-135">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="4e1ea-136">Дополнительные сведения о других компонентах представления списка см. в разделе [Создание представления списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="4e1ea-136">For more information about other components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4e1ea-137">См. также</span><span class="sxs-lookup"><span data-stu-id="4e1ea-137">See Also</span></span>

[<span data-ttu-id="4e1ea-138">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="4e1ea-138">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="4e1ea-139">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="4e1ea-139">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="4e1ea-140">Элемент Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="4e1ea-140">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="4e1ea-141">Элемент Селектионсетнаме для Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="4e1ea-141">SelectionSetName Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="4e1ea-142">Элемент TypeName для Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="4e1ea-142">TypeName Element for EntrySelectedBy for ListEntry (Format)</span></span>](/powershell/scripting/developer/format/typename-element-for-entryselectedby-for-listcontrol-format)

[<span data-ttu-id="4e1ea-143">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="4e1ea-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
