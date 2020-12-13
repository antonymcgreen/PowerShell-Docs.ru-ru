---
ms.date: 09/13/2016
ms.topic: reference
title: Определение наборов выделенных фрагментов
description: Определение наборов выделенных фрагментов
ms.openlocfilehash: d709a368a45623d56fdbf4e98a11a5e5f8a193fa
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648265"
---
# <a name="defining-selection-sets"></a><span data-ttu-id="5d1ff-103">Определение наборов выделенных фрагментов</span><span class="sxs-lookup"><span data-stu-id="5d1ff-103">Defining Selection Sets</span></span>

<span data-ttu-id="5d1ff-104">При создании нескольких представлений и элементов управления можно определить наборы объектов, которые называются наборами выбора.</span><span class="sxs-lookup"><span data-stu-id="5d1ff-104">When creating multiple views and controls, you can define sets of objects that are referred to as selection sets.</span></span> <span data-ttu-id="5d1ff-105">Набор выбора позволяет определять объекты один раз без необходимости их многократного определения для каждого представления или элемента управления.</span><span class="sxs-lookup"><span data-stu-id="5d1ff-105">A selection set enables you to define the objects one time, without having to define them repeatedly for each view or control.</span></span> <span data-ttu-id="5d1ff-106">Обычно наборы выбора используются при наличии набора связанных объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="5d1ff-106">Typically, selection sets are used when you have a set of related .NET objects.</span></span> <span data-ttu-id="5d1ff-107">Например, `FileSystem` файл форматирования (FileSystem.format.ps1XML) определяет набор типов файловой системы, используемых несколькими представлениями.</span><span class="sxs-lookup"><span data-stu-id="5d1ff-107">For example, The `FileSystem` formatting file (FileSystem.format.ps1xml) defines a selection set of the file system types that several views use.</span></span>

## <a name="where-selection-sets-are-defined-and-referenced"></a><span data-ttu-id="5d1ff-108">Где определяются и указываются наборы выбора</span><span class="sxs-lookup"><span data-stu-id="5d1ff-108">Where Selection Sets are Defined and Referenced</span></span>

<span data-ttu-id="5d1ff-109">Наборы выбора определяются как часть общих данных, которые могут использоваться всеми представлениями и элементами управления, определенными в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="5d1ff-109">You define selection sets as part of the common data that can be used by all the views and controls defined in the formatting file.</span></span> <span data-ttu-id="5d1ff-110">В следующем примере показано, как определить три набора выбора.</span><span class="sxs-lookup"><span data-stu-id="5d1ff-110">The following example shows how to define three selection sets.</span></span>

```xml
<Configuration>
  <SelectionSets>
    <SelectionSet>...</SelectionSet>
    <SelectionSet>...</SelectionSet>
    <SelectionSet>...</SelectionSet>
  </SelectionSets>
</Configuration>
```

<span data-ttu-id="5d1ff-111">Ссылаться на наборы выбора можно следующими способами.</span><span class="sxs-lookup"><span data-stu-id="5d1ff-111">You can reference a selection sets in the following ways:</span></span>

- <span data-ttu-id="5d1ff-112">Каждое представление содержит `ViewSelectedBy` элемент, который определяет, какие объекты отображаются с помощью представления.</span><span class="sxs-lookup"><span data-stu-id="5d1ff-112">Each view has a `ViewSelectedBy` element that defines which objects are displayed by using the view.</span></span> <span data-ttu-id="5d1ff-113">`ViewSelectedBy`Элемент имеет `SelectionSetName` дочерний элемент, указывающий набор выбора, который используется всеми определениями представления.</span><span class="sxs-lookup"><span data-stu-id="5d1ff-113">The `ViewSelectedBy` element has a `SelectionSetName` child element that specifies the selection set that all the definitions of the view use.</span></span> <span data-ttu-id="5d1ff-114">На количество наборов выбора, на которые можно ссылаться из представления, нет ограничений.</span><span class="sxs-lookup"><span data-stu-id="5d1ff-114">There is no restriction on the number of selection sets that you can reference from a view.</span></span>

- <span data-ttu-id="5d1ff-115">В каждом определении представления или элемента управления `EntrySelectedBy` элемент определяет, какие объекты отображаются с помощью этого определения.</span><span class="sxs-lookup"><span data-stu-id="5d1ff-115">In each definition of a view or control, the `EntrySelectedBy` element defines which objects are displayed by using that definition.</span></span> <span data-ttu-id="5d1ff-116">Как правило, представление или элемент управления имеет только одно определение, поэтому объекты определяются `ViewSelectedBy` элементом.</span><span class="sxs-lookup"><span data-stu-id="5d1ff-116">Typically a view or control has only one definition so the objects are defined by the `ViewSelectedBy` element.</span></span> <span data-ttu-id="5d1ff-117">`EntrySelectedBy`Элемент определения содержит `SelectionSetName` дочерний элемент, указывающий набор выбора.</span><span class="sxs-lookup"><span data-stu-id="5d1ff-117">The `EntrySelectedBy` element of the definition has a `SelectionSetName` child element that specifies the selection set.</span></span> <span data-ttu-id="5d1ff-118">При указании набора, выбранного для определения, нельзя указать какие-либо другие дочерние элементы `EntrySelectedBy` элемента.</span><span class="sxs-lookup"><span data-stu-id="5d1ff-118">If you specify the selection set for a definition, you cannot specify any of the other child elements of the `EntrySelectedBy` element.</span></span>

- <span data-ttu-id="5d1ff-119">В каждом определении представления или элемента управления `SelectionCondition` элемент можно использовать для указания условия использования определения.</span><span class="sxs-lookup"><span data-stu-id="5d1ff-119">In each definition of a view or control, the `SelectionCondition` element can be used to specify a condition for when the definition is used.</span></span> <span data-ttu-id="5d1ff-120">`SelectionCondition`Элемент имеет `SelectionSetName` дочерний элемент, указывающий набор выбора, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="5d1ff-120">The `SelectionCondition` element has a `SelectionSetName` child element that specifies the selection set that triggers the condition.</span></span> <span data-ttu-id="5d1ff-121">Условие активируется при отображении любого из объектов, определенных в наборе выбора.</span><span class="sxs-lookup"><span data-stu-id="5d1ff-121">The condition is triggered when any of the objects defined in the selection set are displayed.</span></span> <span data-ttu-id="5d1ff-122">Дополнительные сведения о настройке этих условий см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="5d1ff-122">For more information about how to set these conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="selection-set-example"></a><span data-ttu-id="5d1ff-123">Пример набора выбора</span><span class="sxs-lookup"><span data-stu-id="5d1ff-123">Selection Set Example</span></span>

<span data-ttu-id="5d1ff-124">В следующем примере показан набор выбора, который берется непосредственно из `FileSystem` файла форматирования, предоставляемого Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5d1ff-124">The following example shows a selection set that is taken directly from the `FileSystem` formatting file provided by Windows PowerShell.</span></span> <span data-ttu-id="5d1ff-125">Дополнительные сведения о других файлах форматирования Windows PowerShell см. в разделе [файлы форматирования Windows PowerShell](./powershell-formatting-files.md).</span><span class="sxs-lookup"><span data-stu-id="5d1ff-125">For more information about other Windows PowerShell formatting files, see [Windows PowerShell Formatting Files](./powershell-formatting-files.md).</span></span>

```xml
<SelectionSets>
  <SelectionSet>
    <Name>FileSystemTypes</Name>
    <Types>
     <TypeName>System.IO.DirectoryInfo</TypeName>
     <TypeName>System.IO.FileInfo</TypeName>
     <TypeName>Deserialized.System.IO.DirectoryInfo</TypeName>
     <TypeName>Deserialized.System.IO.FileInfo</TypeName>
    </Types>
  </SelectionSet>
</SelectionSets>
```

<span data-ttu-id="5d1ff-126">В элементе табличного представления имеется ссылка на предыдущий набор элементов `ViewSelectedBy` .</span><span class="sxs-lookup"><span data-stu-id="5d1ff-126">The previous selection set is referenced in the `ViewSelectedBy` element of a table view.</span></span>

```xml
<ViewDefinitions>
  <View>
    <Name>Files</Name>
    <ViewSelectedBy>
      <SelectionSetName>FileSystemTypes</SelectionSetName>
    </ViewSelectedBy>
    <TableControl>...</TableControl>
  </View>
</ViewDefinitions>

```

## <a name="xml-elements"></a><span data-ttu-id="5d1ff-127">Элементы XML</span><span class="sxs-lookup"><span data-stu-id="5d1ff-127">XML Elements</span></span>

 <span data-ttu-id="5d1ff-128">Количество наборов выбора, которые можно определить, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="5d1ff-128">There is no limit to the number of selection sets that you can define.</span></span> <span data-ttu-id="5d1ff-129">Для создания набора выбора используются следующие XML-элементы.</span><span class="sxs-lookup"><span data-stu-id="5d1ff-129">The following XML elements are used to create a selection set.</span></span>

- <span data-ttu-id="5d1ff-130">Элемент [селектионсетс](./selectionsets-element-format.md) определяет наборы объектов .NET, на которые ссылаются представления и элементы управления файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="5d1ff-130">The [SelectionSets](./selectionsets-element-format.md) element defines the sets of .NET objects that are referenced by the views and controls of the formatting file.</span></span>

- <span data-ttu-id="5d1ff-131">Элемент [Selection](./selectionset-element-format.md) определяет один набор объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="5d1ff-131">The [SelectionSet](./selectionset-element-format.md) element defines a single set of .NET objects.</span></span>

- <span data-ttu-id="5d1ff-132">Элемент [Name](./name-element-for-selectionset-format.md) указывает имя, используемое для ссылки на набор выбора.</span><span class="sxs-lookup"><span data-stu-id="5d1ff-132">The [Name](./name-element-for-selectionset-format.md) element specifies the name that is used to reference the selection set.</span></span>

- <span data-ttu-id="5d1ff-133">Элемент [types](./types-element-for-selectionset-format.md) указывает типы .NET объектов набора выбора.</span><span class="sxs-lookup"><span data-stu-id="5d1ff-133">The [Types](./types-element-for-selectionset-format.md) element specifies the .NET types of the objects of the selection set.</span></span> <span data-ttu-id="5d1ff-134">(В файлах форматирования объекты задаются типом .NET.)</span><span class="sxs-lookup"><span data-stu-id="5d1ff-134">(Within formatting files, objects are specified by their .NET type.)</span></span>

 <span data-ttu-id="5d1ff-135">Для указания набора выбора используются следующие XML-элементы.</span><span class="sxs-lookup"><span data-stu-id="5d1ff-135">The following XML elements are used to specify a selection set.</span></span>

- <span data-ttu-id="5d1ff-136">Следующий элемент задает набор выбора, который будет использоваться во всех определениях представления:</span><span class="sxs-lookup"><span data-stu-id="5d1ff-136">The following element specifies the selection set to use in all the definitions of the view:</span></span>

  - [<span data-ttu-id="5d1ff-137">Элемент SelectionSetName для элемента ViewSelectedBy (формат)</span><span class="sxs-lookup"><span data-stu-id="5d1ff-137">SelectionSetName Element for ViewSelectedBy (Format)</span></span>](./selectionsetname-element-for-viewselectedby-format.md)

  - [<span data-ttu-id="5d1ff-138">Элемент SelectionSetName для элемента EntrySelectedBy для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="5d1ff-138">SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)

- <span data-ttu-id="5d1ff-139">Следующие элементы определяют набор выбора, используемый одним определением представления:</span><span class="sxs-lookup"><span data-stu-id="5d1ff-139">The following elements specify the selection set used by a single view definition:</span></span>

  - [<span data-ttu-id="5d1ff-140">Элемент SelectionSetName для элемента EntrySelectedBy для элемента ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="5d1ff-140">SelectionSetName Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

  - [<span data-ttu-id="5d1ff-141">Элемент SelectionSetName для элемента EntrySelectedBy для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="5d1ff-141">SelectionSetName Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)

  - [<span data-ttu-id="5d1ff-142">Элемент SelectionSetName для элемента EntrySelectedBy для элемента WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="5d1ff-142">SelectionSetName Element for EntrySelectedBy for WideControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

  - [<span data-ttu-id="5d1ff-143">Элемент SelectionSetName для элемента EntrySelectedBy для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="5d1ff-143">SelectionSetName Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)

- <span data-ttu-id="5d1ff-144">Следующие элементы задают набор элементов, используемый в определениях типов Common и View Control:</span><span class="sxs-lookup"><span data-stu-id="5d1ff-144">The following elements specify the selection set used by common and view control definitions:</span></span>

  - [<span data-ttu-id="5d1ff-145">Элемент SelectionSetName для элемента EntrySelectedBy для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="5d1ff-145">SelectionSetName Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-controls-for-view-format.md)

  - [<span data-ttu-id="5d1ff-146">Элемент SelectionSetName для элемента EntrySelectedBy для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="5d1ff-146">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-controls-for-configuration-format.md)

- <span data-ttu-id="5d1ff-147">Следующие элементы определяют набор выбора, используемый при определении, какой объект следует развернуть:</span><span class="sxs-lookup"><span data-stu-id="5d1ff-147">The following elements specify the selection set used when you define which object to expand:</span></span>

  - [<span data-ttu-id="5d1ff-148">Элемент SelectionSetName для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="5d1ff-148">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)

- <span data-ttu-id="5d1ff-149">Следующие элементы определяют набор элементов, используемый условиями выбора.</span><span class="sxs-lookup"><span data-stu-id="5d1ff-149">The following elements specify the selection set used by selection conditions.</span></span>

  - [<span data-ttu-id="5d1ff-150">Элемент SelectionSetName для элемента SelectionCondition для элемента Controls для элемента Configuration (формат)</span><span class="sxs-lookup"><span data-stu-id="5d1ff-150">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

  - [<span data-ttu-id="5d1ff-151">Элемент SelectionSetName для элемента SelectionCondition для элемента Controls для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="5d1ff-151">SelectionSetName Element for SelectionCondition for Controls for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)

  - [<span data-ttu-id="5d1ff-152">Элемент SelectionSetName для элемента SelectionCondition для элемента CustomControl для элемента View (формат)</span><span class="sxs-lookup"><span data-stu-id="5d1ff-152">SelectionSetName Element for SelectionCondition for CustomControl for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

  - [<span data-ttu-id="5d1ff-153">Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="5d1ff-153">SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)

  - [<span data-ttu-id="5d1ff-154">Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента ListEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="5d1ff-154">SelectionSetName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-listentry-format.md)

  - [<span data-ttu-id="5d1ff-155">Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="5d1ff-155">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableControl (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

  - [<span data-ttu-id="5d1ff-156">Элемент SelectionSetName для элемента SelectionCondition для элемента EntrySelectedBy для элемента WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="5d1ff-156">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

  - [<span data-ttu-id="5d1ff-157">Элемент SelectionSetName для элемента SelectionCondition для элемента GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="5d1ff-157">SelectionSetName Element for SelectionCondition for GroupBy (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-groupby-format.md)

## <a name="see-also"></a><span data-ttu-id="5d1ff-158">См. также:</span><span class="sxs-lookup"><span data-stu-id="5d1ff-158">See Also</span></span>

[<span data-ttu-id="5d1ff-159">селектионсетс</span><span class="sxs-lookup"><span data-stu-id="5d1ff-159">SelectionSets</span></span>](./selectionsets-element-format.md)

[<span data-ttu-id="5d1ff-160">Набор выбора</span><span class="sxs-lookup"><span data-stu-id="5d1ff-160">SelectionSet</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="5d1ff-161">Имя</span><span class="sxs-lookup"><span data-stu-id="5d1ff-161">Name</span></span>](./name-element-for-selectionset-format.md)

[<span data-ttu-id="5d1ff-162">Типы</span><span class="sxs-lookup"><span data-stu-id="5d1ff-162">Types</span></span>](./types-element-for-selectionset-format.md)

[<span data-ttu-id="5d1ff-163">Файлы форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="5d1ff-163">PowerShell Formatting Files</span></span>](./powershell-formatting-files.md)

[<span data-ttu-id="5d1ff-164">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="5d1ff-164">Defining Conditions for when Data is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="5d1ff-165">Создание файла форматирования и типов PowerShell</span><span class="sxs-lookup"><span data-stu-id="5d1ff-165">Writing a PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
