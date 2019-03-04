---
title: Создание представления таблицы | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1f405afb-70b5-4fe0-9986-bc07401d93fd
caps.latest.revision: 23
ms.openlocfilehash: 832527ea4b042812c39934cd7e124201c6dc2ea4
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861500"
---
# <a name="creating-a-table-view"></a><span data-ttu-id="f7bcc-102">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="f7bcc-102">Creating a Table View</span></span>

<span data-ttu-id="f7bcc-103">В табличное представление отображает данные в один или несколько столбцов.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-103">A table view displays data in one or more columns.</span></span> <span data-ttu-id="f7bcc-104">Каждая строка таблицы представляет объект .NET, и каждый столбец таблицы представляет свойства объекта или значение скрипта.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-104">Each row in the table represents a .NET object, and each column of the table represents a property of the object or a script value.</span></span> <span data-ttu-id="f7bcc-105">Можно определить представление таблицы, которое отображает все свойства объекта или подмножество свойств объекта.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-105">You can define a table view that displays all the properties of an object or a subset of the properties of an object.</span></span>

## <a name="a-table-view-display"></a><span data-ttu-id="f7bcc-106">Отображение представления таблиц</span><span class="sxs-lookup"><span data-stu-id="f7bcc-106">A Table View Display</span></span>

<span data-ttu-id="f7bcc-107">В следующем примере показано, как Windows PowerShell отображает [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) объект, возвращаемый [Get-Service](/powershell/module/microsoft.powershell.management/get-service) командлета.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-107">The following example shows how Windows PowerShell displays the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object that is returned by the [Get-Service](/powershell/module/microsoft.powershell.management/get-service) cmdlet.</span></span> <span data-ttu-id="f7bcc-108">Для этого объекта, Windows PowerShell определенные отображаются: представление таблицы `Status` свойство, `Name` свойство (это свойство является псевдонимом свойства для `ServiceName` свойства) и `DisplayName` свойство.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-108">For this object, Windows PowerShell has defined a table view that displays the `Status` property, the `Name` property (this property is an alias property for the `ServiceName` property), and the `DisplayName` property.</span></span> <span data-ttu-id="f7bcc-109">Каждая строка таблицы представляет объект, возвращаемый командлетом.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-109">Each row in the table represents an object returned by the cmdlet.</span></span>

```output
Status   Name               DisplayName
------   ----               -----------
Stopped  AJRouter           AllJoyn Router Service
Stopped  ALG                Application Layer Gateway Service
Stopped  AppIDSvc           Application Identity
Running  Appinfo            Application Information
```

## <a name="defining-the-table-view"></a><span data-ttu-id="f7bcc-110">Определение представления таблицы</span><span class="sxs-lookup"><span data-stu-id="f7bcc-110">Defining the Table View</span></span>

<span data-ttu-id="f7bcc-111">Следующий код XML показывает схему представления таблицы для отображения [System.Serviceprocess.Servicecontroller? Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController) объекта.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-111">The following XML shows the table view schema for displaying the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span> <span data-ttu-id="f7bcc-112">Укажите каждое свойство, которое будет отображаться в табличном представлении.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-112">You must specify each property that you want displayed in the table view.</span></span>

```xml
<View>
  <Name>service</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <TableControl>
    <TableHeaders>
      <TableColumnHeader>
        <Width>8</Width>
      </TableColumnHeader>
      <TableColumnHeader>
        <Width>18</Width>
      </TableColumnHeader>
      <TableColumnHeader>
        <Width>38</Width>
      </TableColumnHeader>
    </TableHeaders>
    <TableRowEntries>
      <TableRowEntry>
        <TableColumnItems>
          <TableColumnItem>
           <PropertyName>Status</PropertyName>
          </TableColumnItem>
          <TableColumnItem>
            <PropertyName>Name</PropertyName>
          </TableColumnItem>
          <TableColumnItem>
            <PropertyName>DisplayName</PropertyName>
          </TableColumnItem>
        </TableColumnItems>
      </TableRowEntry>
    </TableRowEntries>
  </TableControl>
</View>
```

<span data-ttu-id="f7bcc-113">Следующие элементы XML используются для определения представления списка:</span><span class="sxs-lookup"><span data-stu-id="f7bcc-113">The following XML elements are used to define a list view:</span></span>

- <span data-ttu-id="f7bcc-114">[Представление](./view-element-format.md) элемент является родительским для элемента представления таблицы.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-114">The [View](./view-element-format.md) element is the parent element of the table view.</span></span> <span data-ttu-id="f7bcc-115">(Это же родительского элемента для списка, ширину и пользовательский элемент управления представления).</span><span class="sxs-lookup"><span data-stu-id="f7bcc-115">(This is the same parent element for the list, wide, and custom control views.)</span></span>

- <span data-ttu-id="f7bcc-116">[Имя](./name-element-for-view-format.md) элемент задает имя представления.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-116">The [Name](./name-element-for-view-format.md) element specifies the name of the view.</span></span> <span data-ttu-id="f7bcc-117">Этот элемент является обязательным для всех представлений.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-117">This element is required for all views.</span></span>

- <span data-ttu-id="f7bcc-118">[ViewSelectedBy](./viewselectedby-element-format.md) элемент определяет объекты, используемые представления.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-118">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines the objects that use the view.</span></span> <span data-ttu-id="f7bcc-119">Этот элемент является обязательным.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-119">This element is required.</span></span>

- <span data-ttu-id="f7bcc-120">[GroupBy](./groupby-element-for-view-format.md) (не показано в следующем примере) определяет при отображении группу объектов.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-120">The [GroupBy](./groupby-element-for-view-format.md) element (not shown in this example) defines when a new group of objects is displayed.</span></span> <span data-ttu-id="f7bcc-121">Новая группа запускается при каждом изменении значения определенных свойств или скрипта.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-121">A new group is started whenever the value of a specific property or script changes.</span></span> <span data-ttu-id="f7bcc-122">Этот элемент является необязательным.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-122">This element is optional.</span></span>

- <span data-ttu-id="f7bcc-123">[Элементов управления](./controls-element-for-view-format.md) (не показано в следующем примере) определяет пользовательские элементы управления, которые определены в представлении таблицы.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-123">The [Controls](./controls-element-for-view-format.md) element (not shown in this example) defines the custom controls that are defined by the table view.</span></span> <span data-ttu-id="f7bcc-124">Элементы управления позволяют для указания способа отображения данных.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-124">Controls give you a way to further specify how the data is displayed.</span></span> <span data-ttu-id="f7bcc-125">Этот элемент является необязательным.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-125">This element is optional.</span></span> <span data-ttu-id="f7bcc-126">Представления можно определить свои собственные пользовательские элементы управления, или он может использовать стандартные элементы управления, которые могут использоваться с любого представления в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-126">A view can define its own custom controls, or it can use common controls that can be used by any view in the formatting file.</span></span> <span data-ttu-id="f7bcc-127">Дополнительные сведения о пользовательских элементах управления см. в разделе [Создание пользовательских элементов управления](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="f7bcc-127">For more information about custom controls, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

- <span data-ttu-id="f7bcc-128">[HideTableHeaders](./hidetableheaders-element-format.md) элемент (не показано в этом примере) указывает, что в таблице не отображается все названия в верхней части таблицы.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-128">The [HideTableHeaders](./hidetableheaders-element-format.md) element (not show in this example) specifies that the table will not show any labels at the top of the table.</span></span> <span data-ttu-id="f7bcc-129">Этот элемент является необязательным.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-129">This element is optional.</span></span>

- <span data-ttu-id="f7bcc-130">[TableControl](./tablecontrol-element-format.md) элемент, который определяет сведения о заголовке и строки таблицы.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-130">The [TableControl](./tablecontrol-element-format.md) element that defines the header and row information of the table.</span></span> <span data-ttu-id="f7bcc-131">Как и с другими представлениями, табличном представлении можно отобразить значения свойств объекта или значения, создаваемые скрипты.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-131">Similar to all other views, a table view can display the values of object properties or values generated by scripts.</span></span>

## <a name="defining-column-headers"></a><span data-ttu-id="f7bcc-132">Определение заголовков столбцов</span><span class="sxs-lookup"><span data-stu-id="f7bcc-132">Defining Column Headers</span></span>

1. <span data-ttu-id="f7bcc-133">[TableHeaders](./tableheaders-element-format.md) элемент и его дочерние элементы определяют, отображаемые в верхней части таблицы.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-133">The [TableHeaders](./tableheaders-element-format.md) element and its child elements define what is displayed at the top of the table.</span></span>

2. <span data-ttu-id="f7bcc-134">[TableColumnHeader](./tablecolumnheader-element-format.md) элемент определяет, что отображается в верхней части столбца таблицы.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-134">The [TableColumnHeader](./tablecolumnheader-element-format.md) element defines what is displayed at the top of a column of the table.</span></span> <span data-ttu-id="f7bcc-135">Эти элементы указываются в том порядке, что отображаются заголовки.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-135">Specify these elements in the order that you want the headers displayed.</span></span>

   <span data-ttu-id="f7bcc-136">Неограниченное количество этих элементом, который можно использовать, но число [TableColumnHeader](./tablecolumnheader-element-format.md) элементов в представлении таблицы должно быть равно количество [TableRowEntry](./tablerowentry-element-for-tablerowentroes-for-tablecontrol-format.md) элементы, которые можно использовать.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-136">There is no limit to the number of these element that you can use, but the number of [TableColumnHeader](./tablecolumnheader-element-format.md) elements in your table view must equal the number of [TableRowEntry](./tablerowentry-element-for-tablerowentroes-for-tablecontrol-format.md) elements that you use.</span></span>

3. <span data-ttu-id="f7bcc-137">[Метка](./label-element-for-tablecolumnheader-for-tablecontrol-format.md) элемент указывает текст, который будет отображаться.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-137">The [Label](./label-element-for-tablecolumnheader-for-tablecontrol-format.md) element specifies the text that is displayed.</span></span> <span data-ttu-id="f7bcc-138">Этот элемент является необязательным.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-138">This element is optional.</span></span>

4. <span data-ttu-id="f7bcc-139">[Ширины](./width-element-for-tablecolumnheader-for-tablecontrol-format.md) элемент задает ширину (в символах) столбца.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-139">The [Width](./width-element-for-tablecolumnheader-for-tablecontrol-format.md) element specifies the width (in characters) of the column.</span></span> <span data-ttu-id="f7bcc-140">Этот элемент является необязательным.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-140">This element is optional.</span></span>

5. <span data-ttu-id="f7bcc-141">[Выравнивание](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md) элемент указывает способ отображения метки.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-141">The [Alignment](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md) element specifies how the label is displayed.</span></span> <span data-ttu-id="f7bcc-142">Метка может быть выровнены по левому краю, по правому краю; или по центру.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-142">The label can be aligned to the left, to the right, or centered.</span></span> <span data-ttu-id="f7bcc-143">Этот элемент является необязательным.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-143">This element is optional.</span></span>

## <a name="defining-the-table-rows"></a><span data-ttu-id="f7bcc-144">Определение строк таблицы</span><span class="sxs-lookup"><span data-stu-id="f7bcc-144">Defining the Table Rows</span></span>

<span data-ttu-id="f7bcc-145">Представления таблиц можно указать одно или несколько определений, которые указывают, какие данные отображаются в строках таблицы с помощью дочерних элементов элемента [TableRowEntries](./tablerowentries-element-for-tablecontrol-format.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-145">Table views can provide one or more definitions that specify what data is displayed in the rows of the table by using the child elements of the [TableRowEntries](./tablerowentries-element-for-tablecontrol-format.md) element.</span></span> <span data-ttu-id="f7bcc-146">Обратите внимание, что можно указать несколько определений для строки таблицы, что заголовки строк остается тем же, независимо от того, какие определения строки используется.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-146">Notice that you can specify multiple definitions for the rows of the table, but the headers for the rows remains the same, regardless of what row definition is used.</span></span> <span data-ttu-id="f7bcc-147">Как правило таблица будет содержать только одно определение.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-147">Typically, a table will have only one definition.</span></span>

<span data-ttu-id="f7bcc-148">В следующем примере, представление будет содержать одно определение, которое отображает значения нескольких свойств [System.Diagnostics.Process? Displayproperty = Fullname](/dotnet/api/System.Diagnostics.Process) объекта.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-148">In the following example, the view provides a single definition that displays the values of several properties of the [System.Diagnostics.Process?Displayproperty=Fullname](/dotnet/api/System.Diagnostics.Process) object.</span></span> <span data-ttu-id="f7bcc-149">Представление таблицы можно отобразить значение свойства или значение сценария (не показано в примере) в строках.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-149">A table view can display the value of a property or the value of a script (not shown in the example) in its rows.</span></span>

```xml
<TableRowEntries>
      <TableRowEntry>
        <TableColumnItems>
          <TableColumnItem>
           <PropertyName>Status</PropertyName>
          </TableColumnItem>
          <TableColumnItem>
            <PropertyName>Name</PropertyName>
          </TableColumnItem>
          <TableColumnItem>
            <PropertyName>DisplayName</PropertyName>
          </TableColumnItem>
        </TableColumnItems>
      </TableRowEntry>
    </TableRowEntries>

```

<span data-ttu-id="f7bcc-150">Следующие элементы XML может использоваться для предоставления определения для строки:</span><span class="sxs-lookup"><span data-stu-id="f7bcc-150">The following XML elements can be used to provide definitions for a row:</span></span>

- <span data-ttu-id="f7bcc-151">[TableRowEntries](./tablerowentries-element-for-tablecontrol-format.md) элемент и его дочерние элементы определяют, отображаемые в строках таблицы.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-151">The [TableRowEntries](./tablerowentries-element-for-tablecontrol-format.md) element and its child elements define what is displayed in the rows of the table.</span></span>

- <span data-ttu-id="f7bcc-152">[TableRowEntry](./listentry-element-for-listcontrol-format.md) элемент предоставляет определение строки.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-152">The [TableRowEntry](./listentry-element-for-listcontrol-format.md) element provides a definition of the row.</span></span> <span data-ttu-id="f7bcc-153">По крайней мере один [TableRowEntry](./listentry-element-for-listcontrol-format.md) требуется; тем не менее, не ограничено максимальное количество элементов, которые могут быть добавлены.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-153">At least one [TableRowEntry](./listentry-element-for-listcontrol-format.md) is required; however, there is no maximum limit to the number of elements that you can add.</span></span> <span data-ttu-id="f7bcc-154">В большинстве случаев представление будет иметь только одно определение.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-154">In most cases, a view will have only one definition.</span></span>

- <span data-ttu-id="f7bcc-155">[EntrySelectedBy](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md) элемент определяет объекты, которые отображаются по специфическим определением.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-155">The [EntrySelectedBy](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md) element specifies the objects that are displayed by a specific definition.</span></span> <span data-ttu-id="f7bcc-156">Этот элемент является необязательным и требуется только в том случае, при определении нескольких [TableRowEntry](./listentry-element-for-listcontrol-format.md) элементы, отображающие разные объекты.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-156">This element is optional and is needed only when you define multiple [TableRowEntry](./listentry-element-for-listcontrol-format.md) elements that display different objects.</span></span>

- <span data-ttu-id="f7bcc-157">[Wrap](./wrap-element-for-tablerowentry-for-tablecontrl-format.md) элемент указывает, что текст, который превышает ширину столбца отображается на следующей строке.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-157">The [Wrap](./wrap-element-for-tablerowentry-for-tablecontrl-format.md) element specifies that text that exceeds the column width is displayed on the next line.</span></span> <span data-ttu-id="f7bcc-158">По умолчанию текст, не уместившийся по ширине столбца, усекается.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-158">By default, text that exceeds the column width is truncated.</span></span>

- <span data-ttu-id="f7bcc-159">[TableColumnItems](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md) элемент определяет свойства или скрипты, значения которых отображаются в строке.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-159">The [TableColumnItems](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md) element defines the properties or scripts whose values are displayed in the row.</span></span>

- <span data-ttu-id="f7bcc-160">[TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) элемент определяет свойства или скрипта, значение которого отображается в столбце строки.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-160">The [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) element defines the property or script whose value is displayed in the column of the row.</span></span> <span data-ttu-id="f7bcc-161">Объект [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) элемент является обязательным для каждого столбца, строки.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-161">A [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) element is required for each column of the row.</span></span> <span data-ttu-id="f7bcc-162">Первая запись отображается в первом столбце, вторая запись второго столбца и т. д.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-162">The first entry is displayed in first column, the second entry in the second column, and so on.</span></span>

- <span data-ttu-id="f7bcc-163">[PropertyName](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md) определяет свойство, значение которого отображается в строке.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-163">The [PropertyName](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md) element specifies the property whose value is displayed in the row.</span></span> <span data-ttu-id="f7bcc-164">Необходимо указать свойство или сценария, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-164">You must specify either a property or a script, but you cannot specify both.</span></span>

- <span data-ttu-id="f7bcc-165">[ScriptBlock](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md) элемент указывает сценарий, значение которого отображается в строке.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-165">The [ScriptBlock](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md) element specifies the script whose value is displayed in the row.</span></span> <span data-ttu-id="f7bcc-166">Необходимо указать сценарий или свойство, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-166">You must specify either a script or a property, but you cannot specify both.</span></span>

- <span data-ttu-id="f7bcc-167">[FormatString](./label-element-for-listitem-for-listcontrol-format.md) элемент задает шаблон формата, который определяет способ отображения значения свойства или скрипт.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-167">The [FormatString](./label-element-for-listitem-for-listcontrol-format.md) element specifies a format pattern that defines how the property or script value is displayed.</span></span> <span data-ttu-id="f7bcc-168">Этот элемент является необязательным.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-168">This element is optional.</span></span>

- <span data-ttu-id="f7bcc-169">[Выравнивание](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md) элемент указывает, как отображается значение свойства или скрипт.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-169">The [Alignment](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md) element specifies how the value of the property or script is displayed.</span></span> <span data-ttu-id="f7bcc-170">Значение может быть выровнены по левому краю, по правому краю; или по центру.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-170">The value can be aligned to the left, to the right, or centered.</span></span> <span data-ttu-id="f7bcc-171">Этот элемент является необязательным.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-171">This element is optional.</span></span>

## <a name="defining-the-objects-that-use-the-table-view"></a><span data-ttu-id="f7bcc-172">Определение объектов, используйте представление таблицы</span><span class="sxs-lookup"><span data-stu-id="f7bcc-172">Defining the Objects That Use the Table View</span></span>

<span data-ttu-id="f7bcc-173">Существует два способа определить, какие объекты .NET используйте представление таблицы.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-173">There are two ways to define which .NET objects use the table view.</span></span> <span data-ttu-id="f7bcc-174">Можно использовать [ViewSelectedBy](./viewselectedby-element-format.md) можно использовать для определения объектов, которые могут отображаться все определения представления, или [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) элемент, чтобы определить, какие объекты будут отображаться по Определение конкретного представления.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-174">You can use the [ViewSelectedBy](./viewselectedby-element-format.md) element to define the objects that can be displayed by all the definitions of the view, or you can use the [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) element to define which objects are displayed by a specific definition of the view.</span></span> <span data-ttu-id="f7bcc-175">В большинстве случаев представление имеет только одно определение, поэтому обычно определяются объекты [ViewSelectedBy](./viewselectedby-element-format.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-175">In most cases, a view has only one definition, so objects are typically defined by the [ViewSelectedBy](./viewselectedby-element-format.md) element.</span></span>

<span data-ttu-id="f7bcc-176">В следующем примере показано, как для определения объектов для отображения в представлении таблицы с помощью [ViewSelectedBy](./viewselectedby-element-format.md) и [TypeName](./typename-element-for-viewselectedby-format.md) элементов.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-176">The following example shows how to define the objects that are displayed by the table view using the [ViewSelectedBy](./viewselectedby-element-format.md) and [TypeName](./typename-element-for-viewselectedby-format.md) elements.</span></span> <span data-ttu-id="f7bcc-177">Нет ограничений на число [TypeName](./typename-element-for-viewselectedby-format.md) элементов можно указать, что их порядок не имеет значения.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-177">There is no limit to the number of [TypeName](./typename-element-for-viewselectedby-format.md) elements that you can specify, and their order is not significant.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <TableControl>...</TableControl>
</View>
```

<span data-ttu-id="f7bcc-178">Чтобы указать объекты, которые используются в представлении таблицы можно использовать следующие элементы XML:</span><span class="sxs-lookup"><span data-stu-id="f7bcc-178">The following XML elements can be used to specify the objects that are used by the table view:</span></span>

- <span data-ttu-id="f7bcc-179">[ViewSelectedBy](./viewselectedby-element-format.md) элемент определяет объекты, отображаемые в представлении списка.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-179">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines which objects are displayed by the list view.</span></span>

- <span data-ttu-id="f7bcc-180">[TypeName](./typename-element-for-viewselectedby-format.md) элемент указывает объект .NET, которое отображается в представлении.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-180">The [TypeName](./typename-element-for-viewselectedby-format.md) element specifies the .NET object that is displayed by the view.</span></span> <span data-ttu-id="f7bcc-181">Полное имя типа .NET является обязательным.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-181">The fully qualified .NET type name is required.</span></span> <span data-ttu-id="f7bcc-182">Необходимо указать по крайней мере один тип или выбора для представления, но есть не максимального количества элементов, которые могут быть указаны.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-182">You must specify at least one type or selection set for the view, but there is no maximum number of elements that can be specified.</span></span>

<span data-ttu-id="f7bcc-183">В следующем примере используется [ViewSelectedBy](./viewselectedby-element-format.md) и [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) элементов.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-183">The following example uses the [ViewSelectedBy](./viewselectedby-element-format.md) and [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) elements.</span></span> <span data-ttu-id="f7bcc-184">Используйте наборы выделения, где, что у вас есть набор связанных объектов, которые отображаются в нескольких представлениях, например при определении представления списка и представление таблицы для те же объекты.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-184">Use selection sets where you have a related set of objects that are displayed using multiple views, such as when you define a list view and a table view for the same objects.</span></span> <span data-ttu-id="f7bcc-185">Дополнительные сведения о том, как создать набор выбора см. в разделе [определение наборы выделения](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="f7bcc-185">For more information about how to create a selection set, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <SelectionSetName>.NET Type Set</SelectionSetName>
  </ViewSelectedBy>
  <TableControl>...</TableControl>
</View>
```

<span data-ttu-id="f7bcc-186">Чтобы указать объекты, которые используются в представлении списка можно использовать следующие элементы XML:</span><span class="sxs-lookup"><span data-stu-id="f7bcc-186">The following XML elements can be used to specify the objects that are used by the list view:</span></span>

- <span data-ttu-id="f7bcc-187">[ViewSelectedBy](./viewselectedby-element-format.md) элемент определяет объекты, отображаемые в представлении списка.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-187">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines which objects are displayed by the list view.</span></span>

- <span data-ttu-id="f7bcc-188">[SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) элемент указывает набор объектов, которые могут отображаться в представлении.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-188">The [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) element specifies a set of objects that can be displayed by the view.</span></span> <span data-ttu-id="f7bcc-189">Необходимо указать по крайней мере одного набора или тип для представления, но есть не максимального количества элементов, которые могут быть указаны.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-189">You must specify at least one selection set or type for the view, but there is no maximum number of elements that can be specified.</span></span>

<span data-ttu-id="f7bcc-190">В следующем примере показано, как для определения объектов, отображаемых командлетом точное определение таблицы представления, используя [EntrySelectedBy](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-190">The following example shows how to define the objects displayed by a specific definition of the table view using the [EntrySelectedBy](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md) element.</span></span> <span data-ttu-id="f7bcc-191">С помощью этого элемента, можно указать имя типа .NET объект набора выбора объектов и выбора условие, которое указывает, когда используется определение.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-191">Using this element, you can specify the .NET type name of the object, a selection set of objects, or a selection condition that specifies when the definition is used.</span></span> <span data-ttu-id="f7bcc-192">Дополнительные сведения о том, как для создания выделения условий см. в разделе [определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="f7bcc-192">For more information about how to create a selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f7bcc-193">При создании нескольких определений представления таблицы нельзя указать другой столбец заголовков.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-193">When creating multiple definitions of the table view you cannot specify different column headers.</span></span> <span data-ttu-id="f7bcc-194">Можно указать только сведения, отображаемые в строках таблицы, например, какие объекты отображаются.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-194">You can specify only what is displayed in the rows of the table, such as what objects are displayed.</span></span>

```xml
<TableRowEntry>
  <EntrySelectedBy>
    <TypeName>.NET Type</TypeName>
  </EntrySelectedBy>
</TableRowEntry>
```

<span data-ttu-id="f7bcc-195">Чтобы указать объекты, которые используются с конкретным определением в представлении списка можно использовать следующие элементы XML:</span><span class="sxs-lookup"><span data-stu-id="f7bcc-195">The following XML elements can be used to specify the objects that are used by a specific definition of the list view:</span></span>

- <span data-ttu-id="f7bcc-196">[EntrySelectedBy](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md) элемент определяет, какие объекты отображаются с помощью определения.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-196">The [EntrySelectedBy](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md) element defines which objects are displayed by the definition.</span></span>

- <span data-ttu-id="f7bcc-197">[TypeName](./typename-element-for-entryselectedby-for-listcontrol-format.md) элемент указывает объект .NET, которое отображается с помощью определения.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-197">The [TypeName](./typename-element-for-entryselectedby-for-listcontrol-format.md) element specifies the .NET object that is displayed by the definition.</span></span> <span data-ttu-id="f7bcc-198">При использовании этого элемента, требуется полное имя типа .NET.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-198">When using this element, the fully qualified .NET type name is required.</span></span> <span data-ttu-id="f7bcc-199">Необходимо указать по крайней мере один тип, выбора или условию выбора для определения, но есть не максимального количества элементов, которые могут быть указаны.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-199">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span>

- <span data-ttu-id="f7bcc-200">[SelectionSetName](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md) (не показано) указывает набор объектов, которые могут отображаться в соответствии с этим определением.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-200">The [SelectionSetName](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md) element (not shown) specifies a set of objects that can be displayed by this definition.</span></span> <span data-ttu-id="f7bcc-201">Необходимо указать по крайней мере один тип, выбора или условию выбора для определения, но есть не максимального количества элементов, которые могут быть указаны.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-201">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span>

- <span data-ttu-id="f7bcc-202">[SelectionCondition](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md) элемент (не показано) определяет условие, которое должен существовать для данного определения для использования.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-202">The [SelectionCondition](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md) element (not shown) specifies a condition that must exist for this definition to be used.</span></span> <span data-ttu-id="f7bcc-203">Необходимо указать по крайней мере один тип, выбора или условию выбора для определения, но есть не максимального количества элементов, которые могут быть указаны.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-203">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span> <span data-ttu-id="f7bcc-204">Дополнительные сведения об определении условий выборки см. в разделе [определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="f7bcc-204">For more information about defining selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="using-format-strings"></a><span data-ttu-id="f7bcc-205">С помощью строки формата</span><span class="sxs-lookup"><span data-stu-id="f7bcc-205">Using Format Strings</span></span>

<span data-ttu-id="f7bcc-206">Строки форматирования можно добавить в представление, чтобы более детально определить способ отображения данных.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-206">Formatting strings can be added to a view to further define how the data is displayed.</span></span> <span data-ttu-id="f7bcc-207">Приведенный ниже показано, как определить строку форматирования для значения `StartTime` свойство.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-207">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<TableColumnItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</TableColumnItem>
```

<span data-ttu-id="f7bcc-208">Следующие элементы XML может использоваться для указания шаблона формата:</span><span class="sxs-lookup"><span data-stu-id="f7bcc-208">The following XML elements can be used to specify a format pattern:</span></span>

- <span data-ttu-id="f7bcc-209">[TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) элемент определяет свойства или скрипта, значение которого отображается в столбце строки.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-209">The [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) element defines the property or script whose value is displayed in the column of the row.</span></span> <span data-ttu-id="f7bcc-210">Объект [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) элемент является обязательным для каждого столбца, строки.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-210">A [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) element is required for each column of the row.</span></span> <span data-ttu-id="f7bcc-211">Первая запись отображается в первом столбце, вторая запись второго столбца и т. д.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-211">The first entry is displayed in first column, the second entry in the second column, and so on.</span></span>

- <span data-ttu-id="f7bcc-212">[PropertyName](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md) определяет свойство, значение которого отображается в строке.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-212">The [PropertyName](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md) element specifies the property whose value is displayed in the row.</span></span> <span data-ttu-id="f7bcc-213">Необходимо указать свойство или сценария, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-213">You must specify either a property or a script, but you cannot specify both.</span></span>

- <span data-ttu-id="f7bcc-214">[FormatString](./label-element-for-listitem-for-listcontrol-format.md) элемент задает шаблон формата, который определяет способ отображения значения свойства или скрипт.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-214">The [FormatString](./label-element-for-listitem-for-listcontrol-format.md) element specifies a format pattern that defines how the property or script value is displayed.</span></span>

<span data-ttu-id="f7bcc-215">В следующем примере `ToString` метод вызывается для форматирования значения переменной скрипта.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-215">In the following example, the `ToString` method is called to format the value of the script.</span></span> <span data-ttu-id="f7bcc-216">Скрипты можно вызвать любой метод объекта.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-216">Scripts can call any method of an object.</span></span> <span data-ttu-id="f7bcc-217">Таким образом Если объект имеет метод, такой как `ToString`, с параметрами форматирования, скрипт можно вызвать этот метод для форматирования значения выходных данных сценария.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-217">Therefore, if an object has a method, such as `ToString`, that has formatting parameters, the script can call that method to format the output value of the script.</span></span>

```xml
<ListItem>
  <ScriptBlock>
    [String]::Format("(0,10) (1,8)", .LastWriteTime.ToString("d"),
    $_.LastWriteTime.Totring("t"))
  </ScriptBlock>
</ListItem>
```

<span data-ttu-id="f7bcc-218">Следующий XML-элемент может использоваться для вызова метода `ToString` метод:</span><span class="sxs-lookup"><span data-stu-id="f7bcc-218">The following XML element can be used to calling the `ToString` method:</span></span>

- <span data-ttu-id="f7bcc-219">[TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) элемент определяет свойства или скрипта, значение которого отображается в столбце строки.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-219">The [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) element defines the property or script whose value is displayed in the column of the row.</span></span> <span data-ttu-id="f7bcc-220">Объект [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) элемент является обязательным для каждого столбца, строки.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-220">A [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) element is required for each column of the row.</span></span> <span data-ttu-id="f7bcc-221">Первая запись отображается в первом столбце, вторая запись второго столбца и т. д.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-221">The first entry is displayed in first column, the second entry in the second column, and so on.</span></span>

- <span data-ttu-id="f7bcc-222">[ScriptBlock](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md) элемент указывает сценарий, значение которого отображается в строке.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-222">The [ScriptBlock](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md) element specifies the script whose value is displayed in the row.</span></span> <span data-ttu-id="f7bcc-223">Необходимо указать сценарий или свойство, но нельзя указать одновременно.</span><span class="sxs-lookup"><span data-stu-id="f7bcc-223">You must specify either a script or a property, but you cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="f7bcc-224">См. также</span><span class="sxs-lookup"><span data-stu-id="f7bcc-224">See Also</span></span>

[<span data-ttu-id="f7bcc-225">Запись файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="f7bcc-225">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
