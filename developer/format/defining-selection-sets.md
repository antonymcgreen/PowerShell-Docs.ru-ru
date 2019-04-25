---
title: Определение наборов Выбор | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 00dbb5ee-93d4-4914-a082-ef4d8b236b5c
caps.latest.revision: 16
ms.openlocfilehash: 596212f2e64401a751cf3dca0ee7d60b80912c00
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066317"
---
# <a name="defining-selection-sets"></a><span data-ttu-id="b4a36-102">Определение наборов выделенных фрагментов</span><span class="sxs-lookup"><span data-stu-id="b4a36-102">Defining Selection Sets</span></span>

<span data-ttu-id="b4a36-103">При создании нескольких представлений и элементов управления, можно определить наборы объектов, которые указаны как наборы выделения.</span><span class="sxs-lookup"><span data-stu-id="b4a36-103">When creating multiple views and controls, you can define sets of objects that are referred to as selection sets.</span></span> <span data-ttu-id="b4a36-104">Выбора позволяет определить один раз объекты без необходимости определять их несколько раз для каждого представления или элемента управления.</span><span class="sxs-lookup"><span data-stu-id="b4a36-104">A selection set enables you to define the objects one time, without having to define them repeatedly for each view or control.</span></span> <span data-ttu-id="b4a36-105">Как правило выбор наборов используются при наличии набора связанных объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="b4a36-105">Typically, selection sets are used when you have a set of related .NET objects.</span></span> <span data-ttu-id="b4a36-106">Например `FileSystem` файл форматирования (FileSystem.format.ps1xml) определяет набор выбора типов файлов системы, использующие несколько представлений.</span><span class="sxs-lookup"><span data-stu-id="b4a36-106">For example, The `FileSystem` formatting file (FileSystem.format.ps1xml) defines a selection set of the file system types that several views use.</span></span>

## <a name="where-selection-sets-are-defined-and-referenced"></a><span data-ttu-id="b4a36-107">Где находятся наборы выделения, определенные и указывает на</span><span class="sxs-lookup"><span data-stu-id="b4a36-107">Where Selection Sets are Defined and Referenced</span></span>

<span data-ttu-id="b4a36-108">Выбор наборов определить как часть общих данных, который может использоваться для всех представлений и элементов управления, определенных в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="b4a36-108">You define selection sets as part of the common data that can be used by all the views and controls defined in the formatting file.</span></span> <span data-ttu-id="b4a36-109">В следующем примере показано, как определяются три набора выбора.</span><span class="sxs-lookup"><span data-stu-id="b4a36-109">The following example shows how to define three selection sets.</span></span>

```xml
<Configuration>
  <SelectionSets>
    <SelectionSet>...</SelectionSet>
    <SelectionSet>...</SelectionSet>
    <SelectionSet>...</SelectionSet>
  </SelectionSets>
</Configuration>
```

<span data-ttu-id="b4a36-110">Вы можете ссылаться на выбор задает одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="b4a36-110">You can reference a selection sets in the following ways:</span></span>

- <span data-ttu-id="b4a36-111">Каждое представление имеет `ViewSelectedBy` элемент, который определяет, какие объекты отображаются с помощью представления.</span><span class="sxs-lookup"><span data-stu-id="b4a36-111">Each view has a `ViewSelectedBy` element that defines which objects are displayed by using the view.</span></span> <span data-ttu-id="b4a36-112">`ViewSelectedBy` Элемент имеет `SelectionSetName` дочерний элемент, который указывает выбранный набор, все определения использования представления.</span><span class="sxs-lookup"><span data-stu-id="b4a36-112">The `ViewSelectedBy` element has a `SelectionSetName` child element that specifies the selection set that all the definitions of the view use.</span></span> <span data-ttu-id="b4a36-113">Нет никаких ограничений на число наборов выбора, которые можно создать ссылку из представления.</span><span class="sxs-lookup"><span data-stu-id="b4a36-113">There is no restriction on the number of selection sets that you can reference from a view.</span></span>

- <span data-ttu-id="b4a36-114">В каждое определение представления или элемента управления `EntrySelectedBy` элемент определяет, какие объекты отображаются с помощью этого определения.</span><span class="sxs-lookup"><span data-stu-id="b4a36-114">In each definition of a view or control, the `EntrySelectedBy` element defines which objects are displayed by using that definition.</span></span> <span data-ttu-id="b4a36-115">Обычно в представлении или элемент управления имеет только одно определение, определяются объекты `ViewSelectedBy` элемент.</span><span class="sxs-lookup"><span data-stu-id="b4a36-115">Typically a view or control has only one definition so the objects are defined by the `ViewSelectedBy` element.</span></span> <span data-ttu-id="b4a36-116">`EntrySelectedBy` Элемент определения имеет `SelectionSetName` дочерний элемент, указывающий набор выделения.</span><span class="sxs-lookup"><span data-stu-id="b4a36-116">The `EntrySelectedBy` element of the definition has a `SelectionSetName` child element that specifies the selection set.</span></span> <span data-ttu-id="b4a36-117">Если указать значение для определения выделения, нельзя задавать любые другие дочерние элементы `EntrySelectedBy` элемент.</span><span class="sxs-lookup"><span data-stu-id="b4a36-117">If you specify the selection set for a definition, you cannot specify any of the other child elements of the `EntrySelectedBy` element.</span></span>

- <span data-ttu-id="b4a36-118">В каждое определение представления или элемента управления `SelectionCondition` элемент может использоваться для указания условия для использования определение.</span><span class="sxs-lookup"><span data-stu-id="b4a36-118">In each definition of a view or control, the `SelectionCondition` element can be used to specify a condition for when the definition is used.</span></span> <span data-ttu-id="b4a36-119">`SelectionCondition` Элемент имеет `SelectionSetName` дочерний элемент, который указывает выбранный набор, который активирует условие.</span><span class="sxs-lookup"><span data-stu-id="b4a36-119">The `SelectionCondition` element has a `SelectionSetName` child element that specifies the selection set that triggers the condition.</span></span> <span data-ttu-id="b4a36-120">Условие активируется в том случае, когда отображается ни одно из объектов, определенных в наборе выбора.</span><span class="sxs-lookup"><span data-stu-id="b4a36-120">The condition is triggered when any of the objects defined in the selection set are displayed.</span></span> <span data-ttu-id="b4a36-121">Дополнительные сведения о настройке этих условий см. в разделе [определение условий при отображении данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="b4a36-121">For more information about how to set these conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="selection-set-example"></a><span data-ttu-id="b4a36-122">Пример выбора набора</span><span class="sxs-lookup"><span data-stu-id="b4a36-122">Selection Set Example</span></span>

<span data-ttu-id="b4a36-123">В следующем примере показано набор выделения берется непосредственно из `FileSystem` форматирования файлов, предоставляемые Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b4a36-123">The following example shows a selection set that is taken directly from the `FileSystem` formatting file provided by Windows PowerShell.</span></span> <span data-ttu-id="b4a36-124">Дополнительные сведения о других Windows PowerShell, в файлов форматирования см. в разделе [файлы форматирования Windows PowerShell](./powershell-formatting-files.md).</span><span class="sxs-lookup"><span data-stu-id="b4a36-124">For more information about other Windows PowerShell formatting files, see [Windows PowerShell Formatting Files](./powershell-formatting-files.md).</span></span>

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

<span data-ttu-id="b4a36-125">Предыдущий набор выбора указывается в `ViewSelectedBy` элемент представления таблицы.</span><span class="sxs-lookup"><span data-stu-id="b4a36-125">The previous selection set is referenced in the `ViewSelectedBy` element of a table view.</span></span>

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

## <a name="xml-elements"></a><span data-ttu-id="b4a36-126">XML-элементов</span><span class="sxs-lookup"><span data-stu-id="b4a36-126">XML Elements</span></span>

 <span data-ttu-id="b4a36-127">Нет ограничений на число наборов выбора, которые можно определить.</span><span class="sxs-lookup"><span data-stu-id="b4a36-127">There is no limit to the number of selection sets that you can define.</span></span> <span data-ttu-id="b4a36-128">Следующие элементы XML используются для создания набора выбора.</span><span class="sxs-lookup"><span data-stu-id="b4a36-128">The following XML elements are used to create a selection set.</span></span>

- <span data-ttu-id="b4a36-129">[SelectionSets](./selectionsets-element-format.md) элемент определяет набор объектов .NET, на которые ссылается представления и элементы управления форматирования файла.</span><span class="sxs-lookup"><span data-stu-id="b4a36-129">The [SelectionSets](./selectionsets-element-format.md) element defines the sets of .NET objects that are referenced by the views and controls of the formatting file.</span></span>

- <span data-ttu-id="b4a36-130">[SelectionSet](./selectionset-element-format.md) элемент определяет один набор объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="b4a36-130">The [SelectionSet](./selectionset-element-format.md) element defines a single set of .NET objects.</span></span>

- <span data-ttu-id="b4a36-131">[Имя](./name-element-for-selectionset-format.md) элемент указывает имя, которое используется для ссылки на наборе выбора.</span><span class="sxs-lookup"><span data-stu-id="b4a36-131">The [Name](./name-element-for-selectionset-format.md) element specifies the name that is used to reference the selection set.</span></span>

- <span data-ttu-id="b4a36-132">[Типы](./types-element-for-selectionset-format.md) элемент задает типы .NET объектов набора выбора.</span><span class="sxs-lookup"><span data-stu-id="b4a36-132">The [Types](./types-element-for-selectionset-format.md) element specifies the .NET types of the objects of the selection set.</span></span> <span data-ttu-id="b4a36-133">(Внутри файлов форматирования, объекты указываются по типу .NET.)</span><span class="sxs-lookup"><span data-stu-id="b4a36-133">(Within formatting files, objects are specified by their .NET type.)</span></span>

 <span data-ttu-id="b4a36-134">Следующие элементы XML используются для указания выбора.</span><span class="sxs-lookup"><span data-stu-id="b4a36-134">The following XML elements are used to specify a selection set.</span></span>

- <span data-ttu-id="b4a36-135">Следующий элемент указывает выбора, настроенный для использования в все определения представления:</span><span class="sxs-lookup"><span data-stu-id="b4a36-135">The following element specifies the selection set to use in all the definitions of the view:</span></span>

    - [<span data-ttu-id="b4a36-136">Элемент SelectionSetName для ViewSelectedBy (формат)</span><span class="sxs-lookup"><span data-stu-id="b4a36-136">SelectionSetName Element for ViewSelectedBy (Format)</span></span>](./selectionsetname-element-for-viewselectedby-format.md)

    - [<span data-ttu-id="b4a36-137">Элемент SelectionSetName для EntrySelectedBy для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="b4a36-137">SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)

- <span data-ttu-id="b4a36-138">Следующие элементы указать набор выделения, используемый по определению одно представление:</span><span class="sxs-lookup"><span data-stu-id="b4a36-138">The following elements specify the selection set used by a single view definition:</span></span>

    - [<span data-ttu-id="b4a36-139">Элемент SelectionSetName для EntrySelectedBy для ListControl (формат)</span><span class="sxs-lookup"><span data-stu-id="b4a36-139">SelectionSetName Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

    - [<span data-ttu-id="b4a36-140">Элемент SelectionSetName для EntrySelectedBy для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="b4a36-140">SelectionSetName Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)

    - [<span data-ttu-id="b4a36-141">Элемент SelectionSetName для EntrySelectedBy для WideControl (формат)</span><span class="sxs-lookup"><span data-stu-id="b4a36-141">SelectionSetName Element for EntrySelectedBy for WideControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

    - [<span data-ttu-id="b4a36-142">Элемент SelectionSetName для EntrySelectedBy для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="b4a36-142">SelectionSetName Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)

- <span data-ttu-id="b4a36-143">Следующие элементы указать набор выделения, используемый общего определения элемента управления:</span><span class="sxs-lookup"><span data-stu-id="b4a36-143">The following elements specify the selection set used by common and view control definitions:</span></span>

    - [<span data-ttu-id="b4a36-144">Элемент SelectionSetName для EntrySelectedBy для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="b4a36-144">SelectionSetName Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-controls-for-view-format.md)

    - [<span data-ttu-id="b4a36-145">Элемент SelectionSetName для EntrySelectedBy для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="b4a36-145">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-controls-for-configuration-format.md)

- <span data-ttu-id="b4a36-146">Следующие элементы укажите набора, используемые при определении какого объекта, чтобы развернуть:</span><span class="sxs-lookup"><span data-stu-id="b4a36-146">The following elements specify the selection set used when you define which object to expand:</span></span>

    - [<span data-ttu-id="b4a36-147">Элемент SelectionSetName для EntrySelectedBy для EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="b4a36-147">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)

- <span data-ttu-id="b4a36-148">Следующие элементы укажите набор выбора используемых условий выборки.</span><span class="sxs-lookup"><span data-stu-id="b4a36-148">The following elements specify the selection set used by selection conditions.</span></span>

    - [<span data-ttu-id="b4a36-149">Элемент SelectionSetName для SelectionCondition для элементов управления для конфигурации (формат)</span><span class="sxs-lookup"><span data-stu-id="b4a36-149">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

    - [<span data-ttu-id="b4a36-150">Элемент SelectionSetName для SelectionCondition для элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="b4a36-150">SelectionSetName Element for SelectionCondition for Controls for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)

    - [<span data-ttu-id="b4a36-151">Элемент SelectionSetName для SelectionCondition для пользовательский элемент управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="b4a36-151">SelectionSetName Element for SelectionCondition for CustomControl for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

    - [<span data-ttu-id="b4a36-152">Элемент SelectionSetName для SelectionCondition для EntrySelectedBy для EnumerableExpansion (формат)</span><span class="sxs-lookup"><span data-stu-id="b4a36-152">SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)

    - [<span data-ttu-id="b4a36-153">Элемент SelectionSetName для SelectionCondition для EntrySelectedBy для ListEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="b4a36-153">SelectionSetName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-listentry-format.md)

    - [<span data-ttu-id="b4a36-154">Элемент SelectionSetName для SelectionCondition для EntrySelectedBy для TableControl (формат)</span><span class="sxs-lookup"><span data-stu-id="b4a36-154">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableControl (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

    - [<span data-ttu-id="b4a36-155">Элемент SelectionSetName для SelectionCondition для EntrySelectedBy для WideEntry (формат)</span><span class="sxs-lookup"><span data-stu-id="b4a36-155">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

    - [<span data-ttu-id="b4a36-156">Элемент SelectionSetName для SelectionCondition для GroupBy (формат)</span><span class="sxs-lookup"><span data-stu-id="b4a36-156">SelectionSetName Element for SelectionCondition for GroupBy (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-groupby-format.md)

## <a name="see-also"></a><span data-ttu-id="b4a36-157">См. также</span><span class="sxs-lookup"><span data-stu-id="b4a36-157">See Also</span></span>

[<span data-ttu-id="b4a36-158">SelectionSets</span><span class="sxs-lookup"><span data-stu-id="b4a36-158">SelectionSets</span></span>](./selectionsets-element-format.md)

[<span data-ttu-id="b4a36-159">SelectionSet</span><span class="sxs-lookup"><span data-stu-id="b4a36-159">SelectionSet</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="b4a36-160">Name</span><span class="sxs-lookup"><span data-stu-id="b4a36-160">Name</span></span>](./name-element-for-selectionset-format.md)

[<span data-ttu-id="b4a36-161">Типы</span><span class="sxs-lookup"><span data-stu-id="b4a36-161">Types</span></span>](./types-element-for-selectionset-format.md)

[<span data-ttu-id="b4a36-162">Файлы форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="b4a36-162">PowerShell Formatting Files</span></span>](./powershell-formatting-files.md)

[<span data-ttu-id="b4a36-163">Определение условия при отображении данных</span><span class="sxs-lookup"><span data-stu-id="b4a36-163">Defining Conditions for when Data is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="b4a36-164">Написание форматирование PowerShell и типы файлов</span><span class="sxs-lookup"><span data-stu-id="b4a36-164">Writing a PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
