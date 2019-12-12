---
title: Определение наборов выбора | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 00dbb5ee-93d4-4914-a082-ef4d8b236b5c
caps.latest.revision: 16
ms.openlocfilehash: 596212f2e64401a751cf3dca0ee7d60b80912c00
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72368853"
---
# <a name="defining-selection-sets"></a><span data-ttu-id="2e44a-102">Определение наборов выделенных фрагментов</span><span class="sxs-lookup"><span data-stu-id="2e44a-102">Defining Selection Sets</span></span>

<span data-ttu-id="2e44a-103">При создании нескольких представлений и элементов управления можно определить наборы объектов, которые называются наборами выбора.</span><span class="sxs-lookup"><span data-stu-id="2e44a-103">When creating multiple views and controls, you can define sets of objects that are referred to as selection sets.</span></span> <span data-ttu-id="2e44a-104">Набор выбора позволяет определять объекты один раз без необходимости их многократного определения для каждого представления или элемента управления.</span><span class="sxs-lookup"><span data-stu-id="2e44a-104">A selection set enables you to define the objects one time, without having to define them repeatedly for each view or control.</span></span> <span data-ttu-id="2e44a-105">Обычно наборы выбора используются при наличии набора связанных объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="2e44a-105">Typically, selection sets are used when you have a set of related .NET objects.</span></span> <span data-ttu-id="2e44a-106">Например, файл форматирования `FileSystem` (FileSystem. Format. ps1xml) определяет набор типов файловой системы, используемых несколькими представлениями.</span><span class="sxs-lookup"><span data-stu-id="2e44a-106">For example, The `FileSystem` formatting file (FileSystem.format.ps1xml) defines a selection set of the file system types that several views use.</span></span>

## <a name="where-selection-sets-are-defined-and-referenced"></a><span data-ttu-id="2e44a-107">Где определяются и указываются наборы выбора</span><span class="sxs-lookup"><span data-stu-id="2e44a-107">Where Selection Sets are Defined and Referenced</span></span>

<span data-ttu-id="2e44a-108">Наборы выбора определяются как часть общих данных, которые могут использоваться всеми представлениями и элементами управления, определенными в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="2e44a-108">You define selection sets as part of the common data that can be used by all the views and controls defined in the formatting file.</span></span> <span data-ttu-id="2e44a-109">В следующем примере показано, как определить три набора выбора.</span><span class="sxs-lookup"><span data-stu-id="2e44a-109">The following example shows how to define three selection sets.</span></span>

```xml
<Configuration>
  <SelectionSets>
    <SelectionSet>...</SelectionSet>
    <SelectionSet>...</SelectionSet>
    <SelectionSet>...</SelectionSet>
  </SelectionSets>
</Configuration>
```

<span data-ttu-id="2e44a-110">Ссылаться на наборы выбора можно следующими способами.</span><span class="sxs-lookup"><span data-stu-id="2e44a-110">You can reference a selection sets in the following ways:</span></span>

- <span data-ttu-id="2e44a-111">Каждое представление содержит элемент `ViewSelectedBy`, который определяет, какие объекты отображаются с помощью представления.</span><span class="sxs-lookup"><span data-stu-id="2e44a-111">Each view has a `ViewSelectedBy` element that defines which objects are displayed by using the view.</span></span> <span data-ttu-id="2e44a-112">Элемент `ViewSelectedBy` имеет `SelectionSetName` дочерний элемент, указывающий набор выбора, который используется всеми определениями представления.</span><span class="sxs-lookup"><span data-stu-id="2e44a-112">The `ViewSelectedBy` element has a `SelectionSetName` child element that specifies the selection set that all the definitions of the view use.</span></span> <span data-ttu-id="2e44a-113">На количество наборов выбора, на которые можно ссылаться из представления, нет ограничений.</span><span class="sxs-lookup"><span data-stu-id="2e44a-113">There is no restriction on the number of selection sets that you can reference from a view.</span></span>

- <span data-ttu-id="2e44a-114">В каждом определении представления или элемента управления элемент `EntrySelectedBy` определяет, какие объекты отображаются с помощью этого определения.</span><span class="sxs-lookup"><span data-stu-id="2e44a-114">In each definition of a view or control, the `EntrySelectedBy` element defines which objects are displayed by using that definition.</span></span> <span data-ttu-id="2e44a-115">Как правило, представление или элемент управления имеет только одно определение, поэтому объекты определяются элементом `ViewSelectedBy`.</span><span class="sxs-lookup"><span data-stu-id="2e44a-115">Typically a view or control has only one definition so the objects are defined by the `ViewSelectedBy` element.</span></span> <span data-ttu-id="2e44a-116">Элемент `EntrySelectedBy` определения содержит дочерний элемент `SelectionSetName`, указывающий набор выбора.</span><span class="sxs-lookup"><span data-stu-id="2e44a-116">The `EntrySelectedBy` element of the definition has a `SelectionSetName` child element that specifies the selection set.</span></span> <span data-ttu-id="2e44a-117">При указании набора, выбранного для определения, нельзя указать какие-либо другие дочерние элементы элемента `EntrySelectedBy`.</span><span class="sxs-lookup"><span data-stu-id="2e44a-117">If you specify the selection set for a definition, you cannot specify any of the other child elements of the `EntrySelectedBy` element.</span></span>

- <span data-ttu-id="2e44a-118">В каждом определении представления или элемента управления элемент `SelectionCondition` можно использовать для указания условия использования определения.</span><span class="sxs-lookup"><span data-stu-id="2e44a-118">In each definition of a view or control, the `SelectionCondition` element can be used to specify a condition for when the definition is used.</span></span> <span data-ttu-id="2e44a-119">Элемент `SelectionCondition` имеет `SelectionSetName` дочерний элемент, указывающий набор выбора, который запускает условие.</span><span class="sxs-lookup"><span data-stu-id="2e44a-119">The `SelectionCondition` element has a `SelectionSetName` child element that specifies the selection set that triggers the condition.</span></span> <span data-ttu-id="2e44a-120">Условие активируется при отображении любого из объектов, определенных в наборе выбора.</span><span class="sxs-lookup"><span data-stu-id="2e44a-120">The condition is triggered when any of the objects defined in the selection set are displayed.</span></span> <span data-ttu-id="2e44a-121">Дополнительные сведения о настройке этих условий см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="2e44a-121">For more information about how to set these conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="selection-set-example"></a><span data-ttu-id="2e44a-122">Пример набора выбора</span><span class="sxs-lookup"><span data-stu-id="2e44a-122">Selection Set Example</span></span>

<span data-ttu-id="2e44a-123">В следующем примере показан набор выбора, который берется непосредственно из файла форматирования `FileSystem`, предоставляемого Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2e44a-123">The following example shows a selection set that is taken directly from the `FileSystem` formatting file provided by Windows PowerShell.</span></span> <span data-ttu-id="2e44a-124">Дополнительные сведения о других файлах форматирования Windows PowerShell см. в разделе [файлы форматирования Windows PowerShell](./powershell-formatting-files.md).</span><span class="sxs-lookup"><span data-stu-id="2e44a-124">For more information about other Windows PowerShell formatting files, see [Windows PowerShell Formatting Files](./powershell-formatting-files.md).</span></span>

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

<span data-ttu-id="2e44a-125">В элементе `ViewSelectedBy` представления таблицы содержится ссылка на предыдущий набор элементов.</span><span class="sxs-lookup"><span data-stu-id="2e44a-125">The previous selection set is referenced in the `ViewSelectedBy` element of a table view.</span></span>

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

## <a name="xml-elements"></a><span data-ttu-id="2e44a-126">Элементы XML</span><span class="sxs-lookup"><span data-stu-id="2e44a-126">XML Elements</span></span>

 <span data-ttu-id="2e44a-127">Количество наборов выбора, которые можно определить, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="2e44a-127">There is no limit to the number of selection sets that you can define.</span></span> <span data-ttu-id="2e44a-128">Для создания набора выбора используются следующие XML-элементы.</span><span class="sxs-lookup"><span data-stu-id="2e44a-128">The following XML elements are used to create a selection set.</span></span>

- <span data-ttu-id="2e44a-129">Элемент [селектионсетс](./selectionsets-element-format.md) определяет наборы объектов .NET, на которые ссылаются представления и элементы управления файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="2e44a-129">The [SelectionSets](./selectionsets-element-format.md) element defines the sets of .NET objects that are referenced by the views and controls of the formatting file.</span></span>

- <span data-ttu-id="2e44a-130">Элемент [Selection](./selectionset-element-format.md) определяет один набор объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="2e44a-130">The [SelectionSet](./selectionset-element-format.md) element defines a single set of .NET objects.</span></span>

- <span data-ttu-id="2e44a-131">Элемент [Name](./name-element-for-selectionset-format.md) указывает имя, используемое для ссылки на набор выбора.</span><span class="sxs-lookup"><span data-stu-id="2e44a-131">The [Name](./name-element-for-selectionset-format.md) element specifies the name that is used to reference the selection set.</span></span>

- <span data-ttu-id="2e44a-132">Элемент [types](./types-element-for-selectionset-format.md) указывает типы .NET объектов набора выбора.</span><span class="sxs-lookup"><span data-stu-id="2e44a-132">The [Types](./types-element-for-selectionset-format.md) element specifies the .NET types of the objects of the selection set.</span></span> <span data-ttu-id="2e44a-133">(В файлах форматирования объекты задаются типом .NET.)</span><span class="sxs-lookup"><span data-stu-id="2e44a-133">(Within formatting files, objects are specified by their .NET type.)</span></span>

 <span data-ttu-id="2e44a-134">Для указания набора выбора используются следующие XML-элементы.</span><span class="sxs-lookup"><span data-stu-id="2e44a-134">The following XML elements are used to specify a selection set.</span></span>

- <span data-ttu-id="2e44a-135">Следующий элемент задает набор выбора, который будет использоваться во всех определениях представления:</span><span class="sxs-lookup"><span data-stu-id="2e44a-135">The following element specifies the selection set to use in all the definitions of the view:</span></span>

    - [<span data-ttu-id="2e44a-136">Элемент Селектионсетнаме для Виевселектедби (Format)</span><span class="sxs-lookup"><span data-stu-id="2e44a-136">SelectionSetName Element for ViewSelectedBy (Format)</span></span>](./selectionsetname-element-for-viewselectedby-format.md)

    - [<span data-ttu-id="2e44a-137">Элемент Селектионсетнаме для Ентриселектедби для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="2e44a-137">SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)

- <span data-ttu-id="2e44a-138">Следующие элементы определяют набор выбора, используемый одним определением представления:</span><span class="sxs-lookup"><span data-stu-id="2e44a-138">The following elements specify the selection set used by a single view definition:</span></span>

    - [<span data-ttu-id="2e44a-139">Элемент Селектионсетнаме для Ентриселектедби для ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="2e44a-139">SelectionSetName Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

    - [<span data-ttu-id="2e44a-140">Элемент Селектионсетнаме для Ентриселектедби для Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="2e44a-140">SelectionSetName Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)

    - [<span data-ttu-id="2e44a-141">Элемент Селектионсетнаме для Ентриселектедби для Видеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="2e44a-141">SelectionSetName Element for EntrySelectedBy for WideControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

    - [<span data-ttu-id="2e44a-142">Элемент Селектионсетнаме для Ентриселектедби для ошибка customcontrol для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="2e44a-142">SelectionSetName Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)

- <span data-ttu-id="2e44a-143">Следующие элементы задают набор элементов, используемый в определениях типов Common и View Control:</span><span class="sxs-lookup"><span data-stu-id="2e44a-143">The following elements specify the selection set used by common and view control definitions:</span></span>

    - [<span data-ttu-id="2e44a-144">Элемент Селектионсетнаме для Ентриселектедби элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="2e44a-144">SelectionSetName Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-controls-for-view-format.md)

    - [<span data-ttu-id="2e44a-145">Элемент Селектионсетнаме для Ентриселектедби для элементов управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="2e44a-145">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-controls-for-configuration-format.md)

- <span data-ttu-id="2e44a-146">Следующие элементы определяют набор выбора, используемый при определении, какой объект следует развернуть:</span><span class="sxs-lookup"><span data-stu-id="2e44a-146">The following elements specify the selection set used when you define which object to expand:</span></span>

    - [<span data-ttu-id="2e44a-147">Элемент Селектионсетнаме для Ентриселектедби для Енумерабликспансион (Format)</span><span class="sxs-lookup"><span data-stu-id="2e44a-147">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)

- <span data-ttu-id="2e44a-148">Следующие элементы определяют набор элементов, используемый условиями выбора.</span><span class="sxs-lookup"><span data-stu-id="2e44a-148">The following elements specify the selection set used by selection conditions.</span></span>

    - [<span data-ttu-id="2e44a-149">Элемент Селектионсетнаме для Селектионкондитион для элементов управления конфигурации (Format)</span><span class="sxs-lookup"><span data-stu-id="2e44a-149">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

    - [<span data-ttu-id="2e44a-150">Элемент Селектионсетнаме для Селектионкондитион элементов управления для представления (формат)</span><span class="sxs-lookup"><span data-stu-id="2e44a-150">SelectionSetName Element for SelectionCondition for Controls for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)

    - [<span data-ttu-id="2e44a-151">Элемент Селектионсетнаме для Селектионкондитион для ошибка customcontrol для представления (Format)</span><span class="sxs-lookup"><span data-stu-id="2e44a-151">SelectionSetName Element for SelectionCondition for CustomControl for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

    - [<span data-ttu-id="2e44a-152">Элемент Селектионсетнаме для Селектионкондитион для Ентриселектедби для Енумерабликспансион (Format)</span><span class="sxs-lookup"><span data-stu-id="2e44a-152">SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)

    - [<span data-ttu-id="2e44a-153">Элемент Селектионсетнаме для Селектионкондитион для Ентриселектедби для Листентри (Format)</span><span class="sxs-lookup"><span data-stu-id="2e44a-153">SelectionSetName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-listentry-format.md)

    - [<span data-ttu-id="2e44a-154">Элемент Селектионсетнаме для Селектионкондитион для Ентриселектедби для Таблеконтрол (Format)</span><span class="sxs-lookup"><span data-stu-id="2e44a-154">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableControl (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

    - [<span data-ttu-id="2e44a-155">Элемент Селектионсетнаме для Селектионкондитион для Ентриселектедби для Видинтри (Format)</span><span class="sxs-lookup"><span data-stu-id="2e44a-155">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

    - [<span data-ttu-id="2e44a-156">Элемент Селектионсетнаме для Селектионкондитион для GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="2e44a-156">SelectionSetName Element for SelectionCondition for GroupBy (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-groupby-format.md)

## <a name="see-also"></a><span data-ttu-id="2e44a-157">См. также:</span><span class="sxs-lookup"><span data-stu-id="2e44a-157">See Also</span></span>

[<span data-ttu-id="2e44a-158">селектионсетс</span><span class="sxs-lookup"><span data-stu-id="2e44a-158">SelectionSets</span></span>](./selectionsets-element-format.md)

[<span data-ttu-id="2e44a-159">Набор выбора</span><span class="sxs-lookup"><span data-stu-id="2e44a-159">SelectionSet</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="2e44a-160">Name</span><span class="sxs-lookup"><span data-stu-id="2e44a-160">Name</span></span>](./name-element-for-selectionset-format.md)

[<span data-ttu-id="2e44a-161">Типы</span><span class="sxs-lookup"><span data-stu-id="2e44a-161">Types</span></span>](./types-element-for-selectionset-format.md)

[<span data-ttu-id="2e44a-162">Файлы форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="2e44a-162">PowerShell Formatting Files</span></span>](./powershell-formatting-files.md)

[<span data-ttu-id="2e44a-163">Определение условий для отображения данных</span><span class="sxs-lookup"><span data-stu-id="2e44a-163">Defining Conditions for when Data is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="2e44a-164">Создание файла форматирования и типов PowerShell</span><span class="sxs-lookup"><span data-stu-id="2e44a-164">Writing a PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
