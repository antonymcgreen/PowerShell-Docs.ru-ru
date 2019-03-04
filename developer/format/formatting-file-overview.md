---
title: Общие сведения о файлах форматирования | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fe888fee-1fe9-459f-9d62-35732c19a7f8
caps.latest.revision: 13
ms.openlocfilehash: d418cff70c1197aa3c331eed909f49198da139e9
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56863300"
---
# <a name="formatting-file-overview"></a><span data-ttu-id="724f6-102">Общие сведения о файлах форматирования</span><span class="sxs-lookup"><span data-stu-id="724f6-102">Formatting File Overview</span></span>

<span data-ttu-id="724f6-103">Формат отображения для объектов, возвращаемых функцией команды (командлеты, функции и сценарии) определяются с помощью форматирования (файлы format.ps1xml).</span><span class="sxs-lookup"><span data-stu-id="724f6-103">The display format for the objects that are returned by commands (cmdlets, functions, and scripts) are defined by using formatting files (format.ps1xml files).</span></span> <span data-ttu-id="724f6-104">Некоторые из этих файлов предоставляются PowerShell, чтобы определить формат отображения этих объектов, возвращенных предоставляемых системой PowerShell команд, таких как [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) объект, возвращаемый `Get-Process` командлета.</span><span class="sxs-lookup"><span data-stu-id="724f6-104">Several of these files are provided by PowerShell to define the display format for those objects returned by PowerShell-provided commands, such as the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object returned by the `Get-Process` cmdlet.</span></span> <span data-ttu-id="724f6-105">Тем не менее можно также создать собственные пользовательские файлы форматирования для перезаписи форматы отображения по умолчанию, или можно написать пользовательский файл форматирования для определения отображения объектов, возвращенных собственные команды.</span><span class="sxs-lookup"><span data-stu-id="724f6-105">However, you can also create your own custom formatting files to overwrite the default display formats or you can write a custom formatting file to define the display of objects returned by your own commands.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="724f6-106">Файлы форматирования, не определяют элементы объекта, которые возвращаются в конвейер.</span><span class="sxs-lookup"><span data-stu-id="724f6-106">Formatting files do not determine the elements of an object that are returned to the pipeline.</span></span> <span data-ttu-id="724f6-107">Когда объект возвращается в конвейер, все члены этого объекта доступны, даже если некоторые не отображаются.</span><span class="sxs-lookup"><span data-stu-id="724f6-107">When an object is returned to the pipeline, all members of that object are available even if some are not displayed.</span></span>

<span data-ttu-id="724f6-108">PowerShell использует данные в эти файлы форматирования, чтобы определить, что отображается и форматирование отображаемых данных.</span><span class="sxs-lookup"><span data-stu-id="724f6-108">PowerShell uses the data in these formatting files to determine what is displayed and how the displayed data is formatted.</span></span> <span data-ttu-id="724f6-109">Отображаемые данные могут включать, свойства объекта или значение скрипта.</span><span class="sxs-lookup"><span data-stu-id="724f6-109">The displayed data can include the properties of an object or the value of a script.</span></span> <span data-ttu-id="724f6-110">Сценарии используются в том случае, если вы хотите отобразить некое значение, не доступны непосредственно из окна свойств объекта, таких как добавление значения двух свойств объекта, а затем Отображение суммы в виде фрагмента данных.</span><span class="sxs-lookup"><span data-stu-id="724f6-110">Scripts are used if you want to display some value that is not available directly from the properties of an object, such as adding the value of two properties of an object and then displaying the sum as a piece of data.</span></span> <span data-ttu-id="724f6-111">Форматирование отображаемых данных выполняется с помощью определения представления для объектов, которые вы хотите отобразить.</span><span class="sxs-lookup"><span data-stu-id="724f6-111">Formatting of the displayed data is done by defining views for the objects that you want to display.</span></span> <span data-ttu-id="724f6-112">Можно определить одно представление для каждого объекта, можно определить одно представление для нескольких объектов или вы можете определить несколько представлений для одного объекта.</span><span class="sxs-lookup"><span data-stu-id="724f6-112">You can define a single view for each object, you can define a single view for multiple objects, or you can define multiple views for the same object.</span></span> <span data-ttu-id="724f6-113">Нет ограничений на количество представлений, которые можно определить.</span><span class="sxs-lookup"><span data-stu-id="724f6-113">There is no limit to the number of views that you can define.</span></span>

## <a name="common-features-of-formatting-files"></a><span data-ttu-id="724f6-114">Общие возможности методов файлы форматирования</span><span class="sxs-lookup"><span data-stu-id="724f6-114">Common Features of Formatting Files</span></span>

<span data-ttu-id="724f6-115">Каждый файл форматирования можно определить следующие компоненты, которые могут совместно использоваться все представления, определенные в файле:</span><span class="sxs-lookup"><span data-stu-id="724f6-115">Each formatting file can define the following components that can be shared across all the views defined by the file:</span></span>

- <span data-ttu-id="724f6-116">Параметр конфигурации, такие как ли данные, отображаемые в строках таблицы будет отображаться на следующей строке, если длина превышает ширину столбца данных по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="724f6-116">Default configuration setting, such as whether the data displayed in the rows of tables will be displayed on the next line if the data is longer than the width of the column.</span></span> <span data-ttu-id="724f6-117">Дополнительные сведения об этих параметрах см. в разделе [определение Общие параметры конфигурации](./defining-common-configuration-features.md).</span><span class="sxs-lookup"><span data-stu-id="724f6-117">For more information about these settings, see [Defining Common Configuration Settings](./defining-common-configuration-features.md).</span></span>

- <span data-ttu-id="724f6-118">Наборы объектов, которые могут отображаться по любому из представлений форматирования файла.</span><span class="sxs-lookup"><span data-stu-id="724f6-118">Sets of objects that can be displayed by any of the views of the formatting file.</span></span> <span data-ttu-id="724f6-119">Дополнительные сведения об этих наборах (называется *наборы выделения*), см. в разделе [определение задает объектов](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="724f6-119">For more information about these sets (referred to as *selection sets*), see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

- <span data-ttu-id="724f6-120">Стандартные элементы управления, которые могут использоваться все представления файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="724f6-120">Common controls that can be used by all the views of the formatting file.</span></span> <span data-ttu-id="724f6-121">Элементы управления предоставляют возможности более точного управления на отображение данных.</span><span class="sxs-lookup"><span data-stu-id="724f6-121">Controls give you finer control on how data is displayed.</span></span> <span data-ttu-id="724f6-122">Дополнительные сведения об элементах управления см. в разделе [определение пользовательских элементов управления](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="724f6-122">For more information about controls, see [Defining Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="formatting-views"></a><span data-ttu-id="724f6-123">Форматирование представления</span><span class="sxs-lookup"><span data-stu-id="724f6-123">Formatting Views</span></span>

<span data-ttu-id="724f6-124">Форматирования представлений можно отображать объекты в табличном формате, формате списка, колонок и настраиваемого формата.</span><span class="sxs-lookup"><span data-stu-id="724f6-124">Formatting views can display objects in a table format, list format, wide format, and custom format.</span></span> <span data-ttu-id="724f6-125">В большинстве случаев каждое определение форматирования описывается набор XML-теги, которые описывают представления.</span><span class="sxs-lookup"><span data-stu-id="724f6-125">For the most part, each formatting definition is described by a set of XML tags that describe the view.</span></span> <span data-ttu-id="724f6-126">Каждое представление содержит имя представления, объекты, используемые представления и элементы представления, такие как данные столбцов и строк для таблицы представления.</span><span class="sxs-lookup"><span data-stu-id="724f6-126">Each view contains the name of the view, the objects that use the view, and the elements of the view, such as the column and row information for a table view.</span></span>

<span data-ttu-id="724f6-127">Просмотр списков свойств объекта или значение блока скрипта в одном или нескольких столбцах таблицы.</span><span class="sxs-lookup"><span data-stu-id="724f6-127">Table View Lists the properties of an object or a script block value in one or more columns.</span></span> <span data-ttu-id="724f6-128">Каждый столбец представляет одно свойство объекта или значение скрипта.</span><span class="sxs-lookup"><span data-stu-id="724f6-128">Each column represents a single property of the object or a script value.</span></span> <span data-ttu-id="724f6-129">Можно определить представление таблицы, которое отображает все свойства объекта, подмножество свойств объекта или комбинации свойств и значений в скрипт.</span><span class="sxs-lookup"><span data-stu-id="724f6-129">You can define a table view that displays all the properties of an object, a subset of the properties of an object, or a combination of properties and script values.</span></span> <span data-ttu-id="724f6-130">Каждая строка таблицы представляет возвращаемый объект.</span><span class="sxs-lookup"><span data-stu-id="724f6-130">Each row of the table represents a returned object.</span></span> <span data-ttu-id="724f6-131">Создание представления таблицы очень похожа на при передаче объекта в `Format-Table` командлета.</span><span class="sxs-lookup"><span data-stu-id="724f6-131">Creating a table view is very similar to when you pipe an object to the `Format-Table` cmdlet.</span></span> <span data-ttu-id="724f6-132">Дополнительные сведения об этом представлении см. в разделе [табличное представление](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="724f6-132">For more information about this view, see [Table View](./creating-a-table-view.md).</span></span>

<span data-ttu-id="724f6-133">Перечислите представлении перечислены свойства объекта или значение скрипта в одном столбце.</span><span class="sxs-lookup"><span data-stu-id="724f6-133">List View Lists the properties of an object or a script value in a single column.</span></span> <span data-ttu-id="724f6-134">Каждая строка списка отображает необязательную метку или имя свойства, за которым следует значение свойства или скрипт.</span><span class="sxs-lookup"><span data-stu-id="724f6-134">Each row of the list displays an optional label or the property name followed by the value of the property or script.</span></span> <span data-ttu-id="724f6-135">Создание представления списка очень похожа на передачи объекта в `Format-List` командлета.</span><span class="sxs-lookup"><span data-stu-id="724f6-135">Creating a list view is very similar to piping an object to the `Format-List` cmdlet.</span></span> <span data-ttu-id="724f6-136">Дополнительные сведения об этом представлении см. в разделе [представление списка](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="724f6-136">For more information about this view, see [List View](./creating-a-list-view.md).</span></span>

<span data-ttu-id="724f6-137">Широкое представление перечислены одиночному свойству объекта или значение скрипт в один или несколько столбцов.</span><span class="sxs-lookup"><span data-stu-id="724f6-137">Wide View Lists a single property of an object or a script value in one or more columns.</span></span> <span data-ttu-id="724f6-138">Нет, метка или заголовок для этого представления.</span><span class="sxs-lookup"><span data-stu-id="724f6-138">There is no label or header for this view.</span></span> <span data-ttu-id="724f6-139">Создание широкое представление очень похоже, для передачи объекта в `Format-Wide` командлета.</span><span class="sxs-lookup"><span data-stu-id="724f6-139">Creating a wide view is very similar to piping an object to the `Format-Wide` cmdlet.</span></span> <span data-ttu-id="724f6-140">Дополнительные сведения об этом представлении см. в разделе [широкое представление](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="724f6-140">For more information about this view, see [Wide View](./creating-a-wide-view.md).</span></span>

<span data-ttu-id="724f6-141">Настраиваемое представление содержит настраиваемое представление свойств объекта или значения скриптов, не соответствует структуре жесткой представления таблицы, списки или широкие представления.</span><span class="sxs-lookup"><span data-stu-id="724f6-141">Custom View Displays a customizable view of object properties or script values that does not adhere to the rigid structure of table views, list views, or wide views.</span></span> <span data-ttu-id="724f6-142">Можно определить автономного представления, или можно определить пользовательское представление, которое используется другое представление, например представление таблицы или представления списка.</span><span class="sxs-lookup"><span data-stu-id="724f6-142">You can define a stand-alone custom view, or you can define a custom view that is used by another view, such as a table view or list view.</span></span> <span data-ttu-id="724f6-143">Создание настраиваемого представления очень похожа на передачи объекта в `Format-Custom` командлета.</span><span class="sxs-lookup"><span data-stu-id="724f6-143">Creating a custom view is very similar to piping an object to the `Format-Custom` cmdlet.</span></span> <span data-ttu-id="724f6-144">Дополнительные сведения об этом представлении см. в разделе [пользовательское представление](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="724f6-144">For more information about this view, see [Custom View](./creating-custom-controls.md).</span></span>

## <a name="components-of-a-view"></a><span data-ttu-id="724f6-145">Компоненты представлений</span><span class="sxs-lookup"><span data-stu-id="724f6-145">Components of a View</span></span>

<span data-ttu-id="724f6-146">В следующих примерах XML основные компоненты представления XML.</span><span class="sxs-lookup"><span data-stu-id="724f6-146">The following XML examples show the basic XML components of a view.</span></span> <span data-ttu-id="724f6-147">Отдельные XML-элементов различаются в зависимости от того, какое представление, вы хотите создать, но основные компоненты представления являются одинаковыми.</span><span class="sxs-lookup"><span data-stu-id="724f6-147">The individual XML elements vary depending on which view you want to create, but the basic components of the views are all the same.</span></span>

<span data-ttu-id="724f6-148">Для начала работы, каждое представление имеет `Name` элемент, который задает понятное имя, которое используется для ссылки на представление.</span><span class="sxs-lookup"><span data-stu-id="724f6-148">To start with, each view has a `Name` element that specifies a user friendly name that is used to reference the view.</span></span> <span data-ttu-id="724f6-149">`ViewSelectedBy` элемент, который определяет, какие объекты .NET, отображаются в представлении и *управления* элемент, который определяет представление.</span><span class="sxs-lookup"><span data-stu-id="724f6-149">a `ViewSelectedBy` element that defines which .NET objects are displayed by the view, and a *control* element that defines the view.</span></span>

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

<span data-ttu-id="724f6-150">В элементе управления, можно определить один или несколько *запись* элементов.</span><span class="sxs-lookup"><span data-stu-id="724f6-150">Within the control element, you can define one or more *entry* elements.</span></span> <span data-ttu-id="724f6-151">Если вы используете несколько определений, необходимо указать, какие объекты .NET использовать каждое определение.</span><span class="sxs-lookup"><span data-stu-id="724f6-151">If you use multiple definitions, you must specify which .NET objects use each definition.</span></span> <span data-ttu-id="724f6-152">Обычно для каждого элемента управления требуется только одна запись, с помощью только одно определение.</span><span class="sxs-lookup"><span data-stu-id="724f6-152">Typically only one entry, with only one definition, is needed for each control.</span></span>

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

<span data-ttu-id="724f6-153">В каждый элемент представления, вы задаете *элемент* элементы, определяющие свойства .NET или скрипты, которые отображаются в представлении.</span><span class="sxs-lookup"><span data-stu-id="724f6-153">Within each entry element of a view, you specify the *item* elements that define the .NET properties or scripts that are displayed by that view.</span></span>

```xml

<ListItems>
  <ListItem>...</ListItem>
  <ListItem>...</ListItem>
  <ListItem>...</ListItem>
</ListItems>

```

<span data-ttu-id="724f6-154">Как показано в предыдущих примерах, файл форматирования может содержать несколько представлений, представление может содержать несколько определений, и каждое определение может содержать несколько элементов.</span><span class="sxs-lookup"><span data-stu-id="724f6-154">As shown in the preceding examples, the formatting file can contain multiple views, a view can contain multiple definitions, and each definition can contain multiple items.</span></span>

## <a name="example-of-a-table-view"></a><span data-ttu-id="724f6-155">Пример представления "таблицы"</span><span class="sxs-lookup"><span data-stu-id="724f6-155">Example of a Table View</span></span>

<span data-ttu-id="724f6-156">В следующем примере показано XML-теги, используемые для определения представления таблицы, содержащий два столбца.</span><span class="sxs-lookup"><span data-stu-id="724f6-156">The following example shows the XML tags used to define a table view that contains two columns.</span></span> <span data-ttu-id="724f6-157">[ViewDefinitions](./viewdefinitions-element-format.md) элементом является элемент-контейнер для всех представлений, определенных в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="724f6-157">The [ViewDefinitions](./viewdefinitions-element-format.md) element is the container element for all the views defined in the formatting file.</span></span> <span data-ttu-id="724f6-158">[Представление](./view-element-format.md) элемент определяет конкретную таблицу, список, ширину, или в пользовательские представления.</span><span class="sxs-lookup"><span data-stu-id="724f6-158">The [View](./view-element-format.md) element defines the specific table, list, wide, or custom view.</span></span> <span data-ttu-id="724f6-159">В каждом [представление](./view-element-format.md) элемент, [имя](./name-element-for-view-format.md) элемент задает имя представления, [ViewSelectedBy](./viewselectedby-element-format.md) элемент определяет объекты, использующие представление и различных элементы управления (такие как `TableControl` элемент, показанный в следующем примере) определения типа представления.</span><span class="sxs-lookup"><span data-stu-id="724f6-159">Within each [View](./view-element-format.md) element, the [Name](./name-element-for-view-format.md) element specifies the name of the view, the [ViewSelectedBy](./viewselectedby-element-format.md) element defines the objects that use the view, and the different control elements (such as the `TableControl` element shown in the following example) define the type of the view.</span></span>

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
    </TableControl)
  </View>
</ViewDefinitions>

```

## <a name="see-also"></a><span data-ttu-id="724f6-160">См. также</span><span class="sxs-lookup"><span data-stu-id="724f6-160">See Also</span></span>

[<span data-ttu-id="724f6-161">Создание представления списка</span><span class="sxs-lookup"><span data-stu-id="724f6-161">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="724f6-162">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="724f6-162">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="724f6-163">Создание широкое представление</span><span class="sxs-lookup"><span data-stu-id="724f6-163">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="724f6-164">Создание пользовательских элементов управления</span><span class="sxs-lookup"><span data-stu-id="724f6-164">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="724f6-165">Написание форматирование PowerShell и типы файлов</span><span class="sxs-lookup"><span data-stu-id="724f6-165">Writing a PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
