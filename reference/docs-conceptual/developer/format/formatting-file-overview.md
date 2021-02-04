---
ms.date: 09/13/2016
ms.topic: reference
title: Общие сведения о файлах форматирования
description: Общие сведения о файлах форматирования
ms.openlocfilehash: 769a86d274ef3b35a322d76e2f03cb551d9204a1
ms.sourcegitcommit: 04faa7dc1122bce839295d4891bd8b2f0ecb06ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/05/2021
ms.locfileid: "97879142"
---
# <a name="formatting-file-overview"></a><span data-ttu-id="835ac-103">Общие сведения о файлах форматирования</span><span class="sxs-lookup"><span data-stu-id="835ac-103">Formatting File Overview</span></span>

<span data-ttu-id="835ac-104">Формат вывода объектов, возвращаемых командами (командлетами, функциями и скриптами), определяется с помощью файлов форматирования (format.ps1XML-файлов).</span><span class="sxs-lookup"><span data-stu-id="835ac-104">The display format for the objects that are returned by commands (cmdlets, functions, and scripts) are defined by using formatting files (format.ps1xml files).</span></span> <span data-ttu-id="835ac-105">Некоторые из этих файлов предоставляются PowerShell, чтобы определить формат представления для объектов, возвращаемых командами, предоставляемыми PowerShell, например объект [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) , возвращаемый `Get-Process` командлетом.</span><span class="sxs-lookup"><span data-stu-id="835ac-105">Several of these files are provided by PowerShell to define the display format for those objects returned by PowerShell-provided commands, such as the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object returned by the `Get-Process` cmdlet.</span></span> <span data-ttu-id="835ac-106">Однако можно также создать собственные файлы форматирования, чтобы перезаписать форматы вывода по умолчанию, или создать файл пользовательского форматирования, чтобы определить отображение объектов, возвращаемых собственными командами.</span><span class="sxs-lookup"><span data-stu-id="835ac-106">However, you can also create your own custom formatting files to overwrite the default display formats or you can write a custom formatting file to define the display of objects returned by your own commands.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="835ac-107">Файлы форматирования не определяют элементы объекта, возвращаемого в конвейер.</span><span class="sxs-lookup"><span data-stu-id="835ac-107">Formatting files do not determine the elements of an object that are returned to the pipeline.</span></span> <span data-ttu-id="835ac-108">Когда объект возвращается в конвейер, все члены этого объекта доступны, даже если некоторые из них не отображаются.</span><span class="sxs-lookup"><span data-stu-id="835ac-108">When an object is returned to the pipeline, all members of that object are available even if some are not displayed.</span></span>

<span data-ttu-id="835ac-109">PowerShell использует данные в этих файлах форматирования для определения того, что отображается и как форматируются отображаемые данные.</span><span class="sxs-lookup"><span data-stu-id="835ac-109">PowerShell uses the data in these formatting files to determine what is displayed and how the displayed data is formatted.</span></span> <span data-ttu-id="835ac-110">Отображаемые данные могут включать свойства объекта или значение скрипта.</span><span class="sxs-lookup"><span data-stu-id="835ac-110">The displayed data can include the properties of an object or the value of a script.</span></span> <span data-ttu-id="835ac-111">Скрипты используются, если требуется отобразить какое-либо значение, недоступное непосредственно из свойств объекта, например добавление значения двух свойств объекта и последующее отображение суммы в виде фрагмента данных.</span><span class="sxs-lookup"><span data-stu-id="835ac-111">Scripts are used if you want to display some value that is not available directly from the properties of an object, such as adding the value of two properties of an object and then displaying the sum as a piece of data.</span></span> <span data-ttu-id="835ac-112">Форматирование отображаемых данных выполняется путем определения представлений для объектов, которые необходимо отобразить.</span><span class="sxs-lookup"><span data-stu-id="835ac-112">Formatting of the displayed data is done by defining views for the objects that you want to display.</span></span> <span data-ttu-id="835ac-113">Можно определить одно представление для каждого объекта, можно определить одно представление для нескольких объектов или определить несколько представлений для одного и того же объекта.</span><span class="sxs-lookup"><span data-stu-id="835ac-113">You can define a single view for each object, you can define a single view for multiple objects, or you can define multiple views for the same object.</span></span> <span data-ttu-id="835ac-114">Количество представлений, которые можно определить, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="835ac-114">There is no limit to the number of views that you can define.</span></span>

## <a name="common-features-of-formatting-files"></a><span data-ttu-id="835ac-115">Общие возможности файлов форматирования</span><span class="sxs-lookup"><span data-stu-id="835ac-115">Common Features of Formatting Files</span></span>

<span data-ttu-id="835ac-116">Каждый файл форматирования может определять следующие компоненты, которые можно совместно использовать во всех представлениях, определенных в файле:</span><span class="sxs-lookup"><span data-stu-id="835ac-116">Each formatting file can define the following components that can be shared across all the views defined by the file:</span></span>

- <span data-ttu-id="835ac-117">Параметр конфигурации по умолчанию, например, будут ли данные, отображаемые в строках таблиц, отображаться на следующей строке, если данные длиннее, чем ширина столбца.</span><span class="sxs-lookup"><span data-stu-id="835ac-117">Default configuration setting, such as whether the data displayed in the rows of tables will be displayed on the next line if the data is longer than the width of the column.</span></span> <span data-ttu-id="835ac-118">Дополнительные сведения об этих параметрах см. в разделе [Определение общих параметров конфигурации](./defining-common-configuration-features.md).</span><span class="sxs-lookup"><span data-stu-id="835ac-118">For more information about these settings, see [Defining Common Configuration Settings](./defining-common-configuration-features.md).</span></span>

- <span data-ttu-id="835ac-119">Наборы объектов, которые могут отображаться любыми представлениями файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="835ac-119">Sets of objects that can be displayed by any of the views of the formatting file.</span></span> <span data-ttu-id="835ac-120">Дополнительные сведения об этих наборах (называемых *наборами выбора*) см. в разделе [Определение наборов объектов](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="835ac-120">For more information about these sets (referred to as *selection sets*), see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

- <span data-ttu-id="835ac-121">Стандартные элементы управления, которые могут использоваться всеми представлениями файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="835ac-121">Common controls that can be used by all the views of the formatting file.</span></span> <span data-ttu-id="835ac-122">Элементы управления обеспечивают более точный контроль над отображением данных.</span><span class="sxs-lookup"><span data-stu-id="835ac-122">Controls give you finer control on how data is displayed.</span></span> <span data-ttu-id="835ac-123">Дополнительные сведения об элементах управления см. в разделе [Определение пользовательских элементов управления](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="835ac-123">For more information about controls, see [Defining Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="formatting-views"></a><span data-ttu-id="835ac-124">Представления форматирования</span><span class="sxs-lookup"><span data-stu-id="835ac-124">Formatting Views</span></span>

<span data-ttu-id="835ac-125">Представления форматирования могут отображать объекты в табличном формате, формате списка, в расширенном формате и пользовательском формате.</span><span class="sxs-lookup"><span data-stu-id="835ac-125">Formatting views can display objects in a table format, list format, wide format, and custom format.</span></span> <span data-ttu-id="835ac-126">В большей части каждое определение форматирования описывается набором XML-тегов, описывающих представление.</span><span class="sxs-lookup"><span data-stu-id="835ac-126">For the most part, each formatting definition is described by a set of XML tags that describe the view.</span></span> <span data-ttu-id="835ac-127">Каждое представление содержит имя представления, объекты, использующие представление, и элементы представления, такие как сведения о столбцах и строках для табличного представления.</span><span class="sxs-lookup"><span data-stu-id="835ac-127">Each view contains the name of the view, the objects that use the view, and the elements of the view, such as the column and row information for a table view.</span></span>

<span data-ttu-id="835ac-128">Табличное представление содержит список свойств объекта или значения блока скрипта в одном или нескольких столбцах.</span><span class="sxs-lookup"><span data-stu-id="835ac-128">Table View Lists the properties of an object or a script block value in one or more columns.</span></span> <span data-ttu-id="835ac-129">Каждый столбец представляет отдельное свойство объекта или значение скрипта.</span><span class="sxs-lookup"><span data-stu-id="835ac-129">Each column represents a single property of the object or a script value.</span></span> <span data-ttu-id="835ac-130">Можно определить табличное представление, отображающее все свойства объекта, подмножество свойств объекта или сочетание свойств и значений скриптов.</span><span class="sxs-lookup"><span data-stu-id="835ac-130">You can define a table view that displays all the properties of an object, a subset of the properties of an object, or a combination of properties and script values.</span></span> <span data-ttu-id="835ac-131">Каждая строка таблицы представляет возвращаемый объект.</span><span class="sxs-lookup"><span data-stu-id="835ac-131">Each row of the table represents a returned object.</span></span> <span data-ttu-id="835ac-132">Создание табличного представления очень похоже на то, что при передаче объекта в `Format-Table` командлет.</span><span class="sxs-lookup"><span data-stu-id="835ac-132">Creating a table view is very similar to when you pipe an object to the `Format-Table` cmdlet.</span></span> <span data-ttu-id="835ac-133">Дополнительные сведения об этом представлении см. в разделе [табличное представление](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="835ac-133">For more information about this view, see [Table View](./creating-a-table-view.md).</span></span>

<span data-ttu-id="835ac-134">Представление списка содержит свойства объекта или значения скрипта в одном столбце.</span><span class="sxs-lookup"><span data-stu-id="835ac-134">List View Lists the properties of an object or a script value in a single column.</span></span> <span data-ttu-id="835ac-135">В каждой строке списка отображается необязательная метка или имя свойства, за которым следует значение свойства или скрипта.</span><span class="sxs-lookup"><span data-stu-id="835ac-135">Each row of the list displays an optional label or the property name followed by the value of the property or script.</span></span> <span data-ttu-id="835ac-136">Создание представления списка очень похоже на передача объекта в командлет по конвейеру `Format-List` .</span><span class="sxs-lookup"><span data-stu-id="835ac-136">Creating a list view is very similar to piping an object to the `Format-List` cmdlet.</span></span> <span data-ttu-id="835ac-137">Дополнительные сведения об этом представлении см. в разделе [представление списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="835ac-137">For more information about this view, see [List View](./creating-a-list-view.md).</span></span>

<span data-ttu-id="835ac-138">Расширенное представление содержит одно свойство объекта или значение скрипта в одном или нескольких столбцах.</span><span class="sxs-lookup"><span data-stu-id="835ac-138">Wide View Lists a single property of an object or a script value in one or more columns.</span></span> <span data-ttu-id="835ac-139">Для этого представления отсутствует метка или заголовок.</span><span class="sxs-lookup"><span data-stu-id="835ac-139">There is no label or header for this view.</span></span> <span data-ttu-id="835ac-140">Создание широкого представления очень похоже на передача объекта в командлет по конвейеру `Format-Wide` .</span><span class="sxs-lookup"><span data-stu-id="835ac-140">Creating a wide view is very similar to piping an object to the `Format-Wide` cmdlet.</span></span> <span data-ttu-id="835ac-141">Дополнительные сведения об этом представлении см. в разделе [широкие представления](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="835ac-141">For more information about this view, see [Wide View](./creating-a-wide-view.md).</span></span>

<span data-ttu-id="835ac-142">Настраиваемое представление отображает настраиваемое представление свойств объекта или значений скриптов, не соответствующих жестким структурам табличных представлений, представлений списков или расширенных представлений.</span><span class="sxs-lookup"><span data-stu-id="835ac-142">Custom View Displays a customizable view of object properties or script values that does not adhere to the rigid structure of table views, list views, or wide views.</span></span> <span data-ttu-id="835ac-143">Можно определить автономное пользовательское представление или определить пользовательское представление, используемое другим представлением, например табличное представление или представление списка.</span><span class="sxs-lookup"><span data-stu-id="835ac-143">You can define a stand-alone custom view, or you can define a custom view that is used by another view, such as a table view or list view.</span></span> <span data-ttu-id="835ac-144">Создание пользовательского представления очень похоже на передача объекта в командлет по конвейеру `Format-Custom` .</span><span class="sxs-lookup"><span data-stu-id="835ac-144">Creating a custom view is very similar to piping an object to the `Format-Custom` cmdlet.</span></span> <span data-ttu-id="835ac-145">Дополнительные сведения об этом представлении см. в разделе [пользовательское представление](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="835ac-145">For more information about this view, see [Custom View](./creating-custom-controls.md).</span></span>

## <a name="components-of-a-view"></a><span data-ttu-id="835ac-146">Компоненты представления</span><span class="sxs-lookup"><span data-stu-id="835ac-146">Components of a View</span></span>

<span data-ttu-id="835ac-147">В следующих примерах кода XML показаны базовые XML-компоненты представления.</span><span class="sxs-lookup"><span data-stu-id="835ac-147">The following XML examples show the basic XML components of a view.</span></span> <span data-ttu-id="835ac-148">Отдельные XML-элементы зависят от того, какое представление вы хотите создать, но основные компоненты представлений одинаковы.</span><span class="sxs-lookup"><span data-stu-id="835ac-148">The individual XML elements vary depending on which view you want to create, but the basic components of the views are all the same.</span></span>

<span data-ttu-id="835ac-149">Для начала каждое представление содержит `Name` элемент, указывающий понятное имя, используемое для ссылки на представление.</span><span class="sxs-lookup"><span data-stu-id="835ac-149">To start with, each view has a `Name` element that specifies a user friendly name that is used to reference the view.</span></span> <span data-ttu-id="835ac-150">`ViewSelectedBy`элемент, который определяет, какие объекты .NET отображаются в представлении, и элемент *управления* , определяющий представление.</span><span class="sxs-lookup"><span data-stu-id="835ac-150">a `ViewSelectedBy` element that defines which .NET objects are displayed by the view, and a *control* element that defines the view.</span></span>

```xml
<ViewDefinitions>
  <View>
    <Name>NameOfView</Name>
    <ViewSelectedBy>...</ViewSelectedBy>
    <TableControl>...</TableControl>
  </View>
  <View>
    <Name>NameOfView</Name>
    <ViewSelectedBy>...</ViewSelectedBy>
    <ListControl>...</ListControl>
  <View>
  <View>
    <Name>NameOfView</Name>
    <ViewSelectedBy>...</ViewSelectedBy>
    <WideControl>...</WideControl>
  <View>
  <View>
    <Name>NameOfView</Name>
    <ViewSelectedBy>...</ViewSelectedBy>
    <CustomControl>...</CustomControl>
  </View>
</ViewDefinitions>

```

<span data-ttu-id="835ac-151">Внутри элемента управления можно определить один или несколько элементов *записи* .</span><span class="sxs-lookup"><span data-stu-id="835ac-151">Within the control element, you can define one or more *entry* elements.</span></span> <span data-ttu-id="835ac-152">При использовании нескольких определений необходимо указать, какие объекты .NET будут использовать каждое определение.</span><span class="sxs-lookup"><span data-stu-id="835ac-152">If you use multiple definitions, you must specify which .NET objects use each definition.</span></span> <span data-ttu-id="835ac-153">Как правило, для каждого элемента управления требуется только одна запись с одним определением.</span><span class="sxs-lookup"><span data-stu-id="835ac-153">Typically only one entry, with only one definition, is needed for each control.</span></span>

```xml
<ListControl>
  <ListEntries>
    <ListEntry>
      <EntrySelectedBy>...</EntrySelectedBy>
      <ListItems>...</ListItems>
    <ListEntry>
    <ListEntry>
        <EntrySelectedBy>...</EntrySelectedBy>
      <ListItems>...</ListItems>
    <ListEntry>
    <ListEntry>
        <EntrySelectedBy>...</EntrySelectedBy>
      <ListItems>...</ListItems>
    <ListEntry>
  </ListEntries>
</ListControl>

```

<span data-ttu-id="835ac-154">В каждом элементе Entry представления указываются *элементы,* определяющие свойства или скрипты .NET, отображаемые этим представлением.</span><span class="sxs-lookup"><span data-stu-id="835ac-154">Within each entry element of a view, you specify the *item* elements that define the .NET properties or scripts that are displayed by that view.</span></span>

```xml

<ListItems>
  <ListItem>...</ListItem>
  <ListItem>...</ListItem>
  <ListItem>...</ListItem>
</ListItems>

```

<span data-ttu-id="835ac-155">Как показано в предыдущих примерах, файл форматирования может содержать несколько представлений, представление может содержать несколько определений, и каждое определение может содержать несколько элементов.</span><span class="sxs-lookup"><span data-stu-id="835ac-155">As shown in the preceding examples, the formatting file can contain multiple views, a view can contain multiple definitions, and each definition can contain multiple items.</span></span>

## <a name="example-of-a-table-view"></a><span data-ttu-id="835ac-156">Пример табличного представления</span><span class="sxs-lookup"><span data-stu-id="835ac-156">Example of a Table View</span></span>

<span data-ttu-id="835ac-157">В следующем примере показаны XML-теги, используемые для определения табличного представления, содержащего два столбца.</span><span class="sxs-lookup"><span data-stu-id="835ac-157">The following example shows the XML tags used to define a table view that contains two columns.</span></span> <span data-ttu-id="835ac-158">Элемент [виевдефинитионс](./viewdefinitions-element-format.md) является элементом-контейнером для всех представлений, определенных в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="835ac-158">The [ViewDefinitions](./viewdefinitions-element-format.md) element is the container element for all the views defined in the formatting file.</span></span> <span data-ttu-id="835ac-159">Элемент [View](./view-element-format.md) определяет определенную таблицу, список, широкий или настраиваемое представление.</span><span class="sxs-lookup"><span data-stu-id="835ac-159">The [View](./view-element-format.md) element defines the specific table, list, wide, or custom view.</span></span> <span data-ttu-id="835ac-160">В каждом элементе [View](./view-element-format.md) элемент [Name](./name-element-for-view-format.md) задает имя представления, элемент [виевселектедби](./viewselectedby-element-format.md) определяет объекты, использующие представление, а различные управляющие элементы (такие как `TableControl` элемент, показанный в следующем примере) определяют тип представления.</span><span class="sxs-lookup"><span data-stu-id="835ac-160">Within each [View](./view-element-format.md) element, the [Name](./name-element-for-view-format.md) element specifies the name of the view, the [ViewSelectedBy](./viewselectedby-element-format.md) element defines the objects that use the view, and the different control elements (such as the `TableControl` element shown in the following example) define the type of the view.</span></span>

```xml
<ViewDefinitions>
  <View>
    <Name>Name of View</Name>
    <ViewSelectedBy>
      <TypeName>Object to display using this view</TypeName>
      <TypeName>Object to display using this view</TypeName>
    </ViewSelectedBy>
    <TableControl>
      <TableHeaders>
        <TableColumnHeader>
          <Width></Width>
        </TableColumnHeader>
        <TableColumnHeader>
          <Width></Width>
        </TableColumnHeader>
      </TableHeaders>
      <TableRowEntries>
        <TableRowEntry>
          <TableColumnItems>
            <TableColumnItem>
              <PropertyName>Header for column 1</PropertyName>
            </TableColumnItem>
            <TableColumnItem>
              <PropertyName>Header for column 2</PropertyName>
            </TableColumnItem>
          </TableColumnItems>
        </TableRowEntry>
      </TableRowEntries>
    </TableControl>
  </View>
</ViewDefinitions>

```

## <a name="see-also"></a><span data-ttu-id="835ac-161">См. также:</span><span class="sxs-lookup"><span data-stu-id="835ac-161">See Also</span></span>

[<span data-ttu-id="835ac-162">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="835ac-162">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="835ac-163">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="835ac-163">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="835ac-164">Создание широкого представления</span><span class="sxs-lookup"><span data-stu-id="835ac-164">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="835ac-165">Создание пользовательских элементов управления</span><span class="sxs-lookup"><span data-stu-id="835ac-165">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="835ac-166">Создание файла форматирования и типов PowerShell</span><span class="sxs-lookup"><span data-stu-id="835ac-166">Writing a PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
