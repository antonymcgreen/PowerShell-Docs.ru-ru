---
ms.date: 09/13/2016
ms.topic: reference
title: Создание представления таблицы
description: Создание представления таблицы
ms.openlocfilehash: 035d42f7968a9e8babec692a7a5873e24b36cd97
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660290"
---
# <a name="creating-a-table-view"></a><span data-ttu-id="43774-103">Создание представления таблицы</span><span class="sxs-lookup"><span data-stu-id="43774-103">Creating a Table View</span></span>

<span data-ttu-id="43774-104">Табличное представление отображает данные в одном или нескольких столбцах.</span><span class="sxs-lookup"><span data-stu-id="43774-104">A table view displays data in one or more columns.</span></span> <span data-ttu-id="43774-105">Каждая строка в таблице представляет объект .NET, а каждый столбец таблицы представляет свойство объекта или значение скрипта.</span><span class="sxs-lookup"><span data-stu-id="43774-105">Each row in the table represents a .NET object, and each column of the table represents a property of the object or a script value.</span></span> <span data-ttu-id="43774-106">Можно определить табличное представление, в котором отображаются все свойства объекта или подмножество свойств объекта.</span><span class="sxs-lookup"><span data-stu-id="43774-106">You can define a table view that displays all the properties of an object or a subset of the properties of an object.</span></span>

## <a name="a-table-view-display"></a><span data-ttu-id="43774-107">Отображение табличного представления</span><span class="sxs-lookup"><span data-stu-id="43774-107">A Table View Display</span></span>

<span data-ttu-id="43774-108">В следующем примере показано, как Windows PowerShell отображает объект [System. ServiceProcess. ServiceController](/dotnet/api/System.ServiceProcess.ServiceController) , возвращаемый командлетом [Get-Service](/powershell/module/microsoft.powershell.management/get-service) .</span><span class="sxs-lookup"><span data-stu-id="43774-108">The following example shows how Windows PowerShell displays the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object that is returned by the [Get-Service](/powershell/module/microsoft.powershell.management/get-service) cmdlet.</span></span> <span data-ttu-id="43774-109">Для этого объекта в Windows PowerShell определено табличное представление, в котором отображается `Status` свойство, `Name` свойство (это свойство является свойством псевдонима для `ServiceName` Свойства) и `DisplayName` свойство.</span><span class="sxs-lookup"><span data-stu-id="43774-109">For this object, Windows PowerShell has defined a table view that displays the `Status` property, the `Name` property (this property is an alias property for the `ServiceName` property), and the `DisplayName` property.</span></span> <span data-ttu-id="43774-110">Каждая строка в таблице представляет объект, возвращаемый командлетом.</span><span class="sxs-lookup"><span data-stu-id="43774-110">Each row in the table represents an object returned by the cmdlet.</span></span>

```output
Status   Name               DisplayName
------   ----               -----------
Stopped  AJRouter           AllJoyn Router Service
Stopped  ALG                Application Layer Gateway Service
Stopped  AppIDSvc           Application Identity
Running  Appinfo            Application Information
```

## <a name="defining-the-table-view"></a><span data-ttu-id="43774-111">Определение табличного представления</span><span class="sxs-lookup"><span data-stu-id="43774-111">Defining the Table View</span></span>

<span data-ttu-id="43774-112">В следующем коде XML показана схема табличного представления для отображения [System. ServiceProcess. ServiceController? DisplayProperty = FullName](/dotnet/api/System.ServiceProcess.ServiceController) , объект.</span><span class="sxs-lookup"><span data-stu-id="43774-112">The following XML shows the table view schema for displaying the [System.Serviceprocess.Servicecontroller?Displayproperty=Fullname](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span> <span data-ttu-id="43774-113">Необходимо указать каждое свойство, которое должно отображаться в представлении таблицы.</span><span class="sxs-lookup"><span data-stu-id="43774-113">You must specify each property that you want displayed in the table view.</span></span>

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

<span data-ttu-id="43774-114">Для определения представления списка используются следующие XML-элементы:</span><span class="sxs-lookup"><span data-stu-id="43774-114">The following XML elements are used to define a list view:</span></span>

- <span data-ttu-id="43774-115">Элемент [View](./view-element-format.md) является родительским элементом табличного представления.</span><span class="sxs-lookup"><span data-stu-id="43774-115">The [View](./view-element-format.md) element is the parent element of the table view.</span></span> <span data-ttu-id="43774-116">(Это тот же родительский элемент для представлений list, Wide и Custom Control.)</span><span class="sxs-lookup"><span data-stu-id="43774-116">(This is the same parent element for the list, wide, and custom control views.)</span></span>

- <span data-ttu-id="43774-117">Элемент [Name](./name-element-for-view-format.md) указывает имя представления.</span><span class="sxs-lookup"><span data-stu-id="43774-117">The [Name](./name-element-for-view-format.md) element specifies the name of the view.</span></span> <span data-ttu-id="43774-118">Этот элемент является обязательным для всех представлений.</span><span class="sxs-lookup"><span data-stu-id="43774-118">This element is required for all views.</span></span>

- <span data-ttu-id="43774-119">Элемент [виевселектедби](./viewselectedby-element-format.md) определяет объекты, которые используют представление.</span><span class="sxs-lookup"><span data-stu-id="43774-119">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines the objects that use the view.</span></span> <span data-ttu-id="43774-120">Этот элемент является обязательным.</span><span class="sxs-lookup"><span data-stu-id="43774-120">This element is required.</span></span>

- <span data-ttu-id="43774-121">Элемент [GroupBy](./groupby-element-for-view-format.md) (не показан в этом примере) определяет, когда отображается новая группа объектов.</span><span class="sxs-lookup"><span data-stu-id="43774-121">The [GroupBy](./groupby-element-for-view-format.md) element (not shown in this example) defines when a new group of objects is displayed.</span></span> <span data-ttu-id="43774-122">Новая группа запускается каждый раз при изменении значения определенного свойства или сценария.</span><span class="sxs-lookup"><span data-stu-id="43774-122">A new group is started whenever the value of a specific property or script changes.</span></span> <span data-ttu-id="43774-123">Этот элемент является необязательным.</span><span class="sxs-lookup"><span data-stu-id="43774-123">This element is optional.</span></span>

- <span data-ttu-id="43774-124">Элемент [Controls](./controls-element-for-view-format.md) (не показан в этом примере) определяет пользовательские элементы управления, определенные табличным представлением.</span><span class="sxs-lookup"><span data-stu-id="43774-124">The [Controls](./controls-element-for-view-format.md) element (not shown in this example) defines the custom controls that are defined by the table view.</span></span> <span data-ttu-id="43774-125">Элементы управления позволяют дополнительно указать способ отображения данных.</span><span class="sxs-lookup"><span data-stu-id="43774-125">Controls give you a way to further specify how the data is displayed.</span></span> <span data-ttu-id="43774-126">Этот элемент является необязательным.</span><span class="sxs-lookup"><span data-stu-id="43774-126">This element is optional.</span></span> <span data-ttu-id="43774-127">Представление может определять собственные пользовательские элементы управления или использовать стандартные элементы управления, которые могут использоваться любыми представлениями в файле форматирования.</span><span class="sxs-lookup"><span data-stu-id="43774-127">A view can define its own custom controls, or it can use common controls that can be used by any view in the formatting file.</span></span> <span data-ttu-id="43774-128">Дополнительные сведения о пользовательских элементах управления см. в разделе [Создание пользовательских элементов управления](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="43774-128">For more information about custom controls, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

- <span data-ttu-id="43774-129">Элемент [хидетаблехеадерс](./hidetableheaders-element-format.md) (не показан в этом примере) указывает, что в таблице не будут отображаться метки в верхней части таблицы.</span><span class="sxs-lookup"><span data-stu-id="43774-129">The [HideTableHeaders](./hidetableheaders-element-format.md) element (not show in this example) specifies that the table will not show any labels at the top of the table.</span></span> <span data-ttu-id="43774-130">Этот элемент является необязательным.</span><span class="sxs-lookup"><span data-stu-id="43774-130">This element is optional.</span></span>

- <span data-ttu-id="43774-131">Элемент [таблеконтрол](./tablecontrol-element-format.md) , определяющий заголовок и сведения о строках таблицы.</span><span class="sxs-lookup"><span data-stu-id="43774-131">The [TableControl](./tablecontrol-element-format.md) element that defines the header and row information of the table.</span></span> <span data-ttu-id="43774-132">Как и в других представлениях, табличное представление может отображать значения свойств объектов или значений, создаваемых скриптами.</span><span class="sxs-lookup"><span data-stu-id="43774-132">Similar to all other views, a table view can display the values of object properties or values generated by scripts.</span></span>

## <a name="defining-column-headers"></a><span data-ttu-id="43774-133">Определение заголовков столбцов</span><span class="sxs-lookup"><span data-stu-id="43774-133">Defining Column Headers</span></span>

1. <span data-ttu-id="43774-134">Элемент [таблехеадерс](./tableheaders-element-format.md) и его дочерние элементы определяют, что отображается в верхней части таблицы.</span><span class="sxs-lookup"><span data-stu-id="43774-134">The [TableHeaders](./tableheaders-element-format.md) element and its child elements define what is displayed at the top of the table.</span></span>

2. <span data-ttu-id="43774-135">Элемент [таблеколумнхеадер](./tablecolumnheader-element-format.md) определяет, что отображается в верхней части столбца таблицы.</span><span class="sxs-lookup"><span data-stu-id="43774-135">The [TableColumnHeader](./tablecolumnheader-element-format.md) element defines what is displayed at the top of a column of the table.</span></span> <span data-ttu-id="43774-136">Укажите эти элементы в том порядке, в котором должны отображаться заголовки.</span><span class="sxs-lookup"><span data-stu-id="43774-136">Specify these elements in the order that you want the headers displayed.</span></span>

   <span data-ttu-id="43774-137">Число элементов в представлении таблицы, которое можно использовать, не ограничено, но число [таблеколумнхеадер](./tablecolumnheader-element-format.md) в таблице должно равняться числу используемых элементов [таблеровентри](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md) .</span><span class="sxs-lookup"><span data-stu-id="43774-137">There is no limit to the number of these element that you can use, but the number of [TableColumnHeader](./tablecolumnheader-element-format.md) elements in your table view must equal the number of [TableRowEntry](./tablerowentry-element-for-tablerowentries-for-tablecontrol-format.md) elements that you use.</span></span>

3. <span data-ttu-id="43774-138">Элемент [Label](./label-element-for-tablecolumnheader-for-tablecontrol-format.md) указывает отображаемый текст.</span><span class="sxs-lookup"><span data-stu-id="43774-138">The [Label](./label-element-for-tablecolumnheader-for-tablecontrol-format.md) element specifies the text that is displayed.</span></span> <span data-ttu-id="43774-139">Этот элемент является необязательным.</span><span class="sxs-lookup"><span data-stu-id="43774-139">This element is optional.</span></span>

4. <span data-ttu-id="43774-140">Элемент [Width](./width-element-for-tablecolumnheader-for-tablecontrol-format.md) задает ширину столбца (в символах).</span><span class="sxs-lookup"><span data-stu-id="43774-140">The [Width](./width-element-for-tablecolumnheader-for-tablecontrol-format.md) element specifies the width (in characters) of the column.</span></span> <span data-ttu-id="43774-141">Этот элемент является необязательным.</span><span class="sxs-lookup"><span data-stu-id="43774-141">This element is optional.</span></span>

5. <span data-ttu-id="43774-142">Элемент [alignment](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md) определяет способ отображения метки.</span><span class="sxs-lookup"><span data-stu-id="43774-142">The [Alignment](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md) element specifies how the label is displayed.</span></span> <span data-ttu-id="43774-143">Метка может быть выровнена слева, справа или по центру.</span><span class="sxs-lookup"><span data-stu-id="43774-143">The label can be aligned to the left, to the right, or centered.</span></span> <span data-ttu-id="43774-144">Этот элемент является необязательным.</span><span class="sxs-lookup"><span data-stu-id="43774-144">This element is optional.</span></span>

## <a name="defining-the-table-rows"></a><span data-ttu-id="43774-145">Определение строк таблицы</span><span class="sxs-lookup"><span data-stu-id="43774-145">Defining the Table Rows</span></span>

<span data-ttu-id="43774-146">Табличные представления могут содержать одно или несколько определений, которые определяют, какие данные отображаются в строках таблицы с помощью дочерних элементов элемента [таблеровентриес](./tablerowentries-element-for-tablecontrol-format.md) .</span><span class="sxs-lookup"><span data-stu-id="43774-146">Table views can provide one or more definitions that specify what data is displayed in the rows of the table by using the child elements of the [TableRowEntries](./tablerowentries-element-for-tablecontrol-format.md) element.</span></span> <span data-ttu-id="43774-147">Обратите внимание, что можно указать несколько определений для строк таблицы, но заголовки строк остаются неизменными независимо от того, какое определение строки используется.</span><span class="sxs-lookup"><span data-stu-id="43774-147">Notice that you can specify multiple definitions for the rows of the table, but the headers for the rows remains the same, regardless of what row definition is used.</span></span> <span data-ttu-id="43774-148">Как правило, таблица будет иметь только одно определение.</span><span class="sxs-lookup"><span data-stu-id="43774-148">Typically, a table will have only one definition.</span></span>

<span data-ttu-id="43774-149">В следующем примере представление предоставляет одно определение, в котором отображаются значения нескольких свойств [System. Diagnostics. Process? DisplayProperty = FullName](/dotnet/api/System.Diagnostics.Process) , объект.</span><span class="sxs-lookup"><span data-stu-id="43774-149">In the following example, the view provides a single definition that displays the values of several properties of the [System.Diagnostics.Process?Displayproperty=Fullname](/dotnet/api/System.Diagnostics.Process) object.</span></span> <span data-ttu-id="43774-150">Табличное представление может отображать значение свойства или значение скрипта (не показано в примере) в его строках.</span><span class="sxs-lookup"><span data-stu-id="43774-150">A table view can display the value of a property or the value of a script (not shown in the example) in its rows.</span></span>

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

<span data-ttu-id="43774-151">Для определения строки можно использовать следующие XML-элементы:</span><span class="sxs-lookup"><span data-stu-id="43774-151">The following XML elements can be used to provide definitions for a row:</span></span>

- <span data-ttu-id="43774-152">Элемент [таблеровентриес](./tablerowentries-element-for-tablecontrol-format.md) и его дочерние элементы определяют, что отображается в строках таблицы.</span><span class="sxs-lookup"><span data-stu-id="43774-152">The [TableRowEntries](./tablerowentries-element-for-tablecontrol-format.md) element and its child elements define what is displayed in the rows of the table.</span></span>

- <span data-ttu-id="43774-153">Элемент [таблеровентри](./listentry-element-for-listcontrol-format.md) предоставляет определение строки.</span><span class="sxs-lookup"><span data-stu-id="43774-153">The [TableRowEntry](./listentry-element-for-listcontrol-format.md) element provides a definition of the row.</span></span> <span data-ttu-id="43774-154">Требуется по крайней мере один [таблеровентри](./listentry-element-for-listcontrol-format.md) ; Однако максимальное количество элементов, которые можно добавить, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="43774-154">At least one [TableRowEntry](./listentry-element-for-listcontrol-format.md) is required; however, there is no maximum limit to the number of elements that you can add.</span></span> <span data-ttu-id="43774-155">В большинстве случаев представление будет иметь только одно определение.</span><span class="sxs-lookup"><span data-stu-id="43774-155">In most cases, a view will have only one definition.</span></span>

- <span data-ttu-id="43774-156">Элемент [ентриселектедби](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md) указывает объекты, отображаемые конкретным определением.</span><span class="sxs-lookup"><span data-stu-id="43774-156">The [EntrySelectedBy](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md) element specifies the objects that are displayed by a specific definition.</span></span> <span data-ttu-id="43774-157">Этот элемент является необязательным и необходим только при определении нескольких элементов [таблеровентри](./listentry-element-for-listcontrol-format.md) , отображающих разные объекты.</span><span class="sxs-lookup"><span data-stu-id="43774-157">This element is optional and is needed only when you define multiple [TableRowEntry](./listentry-element-for-listcontrol-format.md) elements that display different objects.</span></span>

- <span data-ttu-id="43774-158">Элемент [Wrap](./wrap-element-for-tablerowentry-for-tablecontrol-format.md) указывает, что текст, превышающий ширину столбца, отображается на следующей строке.</span><span class="sxs-lookup"><span data-stu-id="43774-158">The [Wrap](./wrap-element-for-tablerowentry-for-tablecontrol-format.md) element specifies that text that exceeds the column width is displayed on the next line.</span></span> <span data-ttu-id="43774-159">По умолчанию текст, не уместившийся по ширине столбца, усекается.</span><span class="sxs-lookup"><span data-stu-id="43774-159">By default, text that exceeds the column width is truncated.</span></span>

- <span data-ttu-id="43774-160">Элемент [таблеколумнитемс](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md) определяет свойства или скрипты, значения которых отображаются в строке.</span><span class="sxs-lookup"><span data-stu-id="43774-160">The [TableColumnItems](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md) element defines the properties or scripts whose values are displayed in the row.</span></span>

- <span data-ttu-id="43774-161">Элемент [таблеколумнитем](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) определяет свойство или скрипт, значение которого отображается в столбце строки.</span><span class="sxs-lookup"><span data-stu-id="43774-161">The [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) element defines the property or script whose value is displayed in the column of the row.</span></span> <span data-ttu-id="43774-162">Для каждого столбца строки требуется элемент [таблеколумнитем](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) .</span><span class="sxs-lookup"><span data-stu-id="43774-162">A [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) element is required for each column of the row.</span></span> <span data-ttu-id="43774-163">Первая запись отображается в первом столбце, второй элемент во втором столбце и т. д.</span><span class="sxs-lookup"><span data-stu-id="43774-163">The first entry is displayed in first column, the second entry in the second column, and so on.</span></span>

- <span data-ttu-id="43774-164">Элемент [PropertyName](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md) указывает свойство, значение которого отображается в строке.</span><span class="sxs-lookup"><span data-stu-id="43774-164">The [PropertyName](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md) element specifies the property whose value is displayed in the row.</span></span> <span data-ttu-id="43774-165">Необходимо указать либо свойство, либо скрипт, но нельзя указать и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="43774-165">You must specify either a property or a script, but you cannot specify both.</span></span>

- <span data-ttu-id="43774-166">Элемент [ScriptBlock](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md) указывает скрипт, значение которого отображается в строке.</span><span class="sxs-lookup"><span data-stu-id="43774-166">The [ScriptBlock](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md) element specifies the script whose value is displayed in the row.</span></span> <span data-ttu-id="43774-167">Необходимо указать либо скрипт, либо свойство, но нельзя указать и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="43774-167">You must specify either a script or a property, but you cannot specify both.</span></span>

- <span data-ttu-id="43774-168">Элемент [FormatString](./label-element-for-listitem-for-listcontrol-format.md) задает шаблон формата, определяющий способ отображения значения свойства или скрипта.</span><span class="sxs-lookup"><span data-stu-id="43774-168">The [FormatString](./label-element-for-listitem-for-listcontrol-format.md) element specifies a format pattern that defines how the property or script value is displayed.</span></span> <span data-ttu-id="43774-169">Этот элемент является необязательным.</span><span class="sxs-lookup"><span data-stu-id="43774-169">This element is optional.</span></span>

- <span data-ttu-id="43774-170">Элемент [alignment](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md) определяет, как отображается значение свойства или скрипта.</span><span class="sxs-lookup"><span data-stu-id="43774-170">The [Alignment](./alignment-element-for-tablecolumnitem-for-tablecontrol-format.md) element specifies how the value of the property or script is displayed.</span></span> <span data-ttu-id="43774-171">Значение может быть выровнено слева, справа или по центру.</span><span class="sxs-lookup"><span data-stu-id="43774-171">The value can be aligned to the left, to the right, or centered.</span></span> <span data-ttu-id="43774-172">Этот элемент является необязательным.</span><span class="sxs-lookup"><span data-stu-id="43774-172">This element is optional.</span></span>

## <a name="defining-the-objects-that-use-the-table-view"></a><span data-ttu-id="43774-173">Определение объектов, использующих табличное представление</span><span class="sxs-lookup"><span data-stu-id="43774-173">Defining the Objects That Use the Table View</span></span>

<span data-ttu-id="43774-174">Существует два способа определения объектов .NET, использующих табличное представление.</span><span class="sxs-lookup"><span data-stu-id="43774-174">There are two ways to define which .NET objects use the table view.</span></span> <span data-ttu-id="43774-175">Элемент [виевселектедби](./viewselectedby-element-format.md) можно использовать для определения объектов, которые могут отображаться всеми определениями представления, или можно использовать элемент [ентриселектедби](./entryselectedby-element-for-listentry-for-listcontrol-format.md) для определения объектов, отображаемых определенным определением представления.</span><span class="sxs-lookup"><span data-stu-id="43774-175">You can use the [ViewSelectedBy](./viewselectedby-element-format.md) element to define the objects that can be displayed by all the definitions of the view, or you can use the [EntrySelectedBy](./entryselectedby-element-for-listentry-for-listcontrol-format.md) element to define which objects are displayed by a specific definition of the view.</span></span> <span data-ttu-id="43774-176">В большинстве случаев представление имеет только одно определение, поэтому объекты обычно определяются элементом [виевселектедби](./viewselectedby-element-format.md) .</span><span class="sxs-lookup"><span data-stu-id="43774-176">In most cases, a view has only one definition, so objects are typically defined by the [ViewSelectedBy](./viewselectedby-element-format.md) element.</span></span>

<span data-ttu-id="43774-177">В следующем примере показано, как определить объекты, отображаемые табличным представлением с помощью элементов [виевселектедби](./viewselectedby-element-format.md) и [TypeName](./typename-element-for-viewselectedby-format.md) .</span><span class="sxs-lookup"><span data-stu-id="43774-177">The following example shows how to define the objects that are displayed by the table view using the [ViewSelectedBy](./viewselectedby-element-format.md) and [TypeName](./typename-element-for-viewselectedby-format.md) elements.</span></span> <span data-ttu-id="43774-178">Количество элементов [TypeName](./typename-element-for-viewselectedby-format.md) , которые можно указать, не ограничено, и их порядок не важен.</span><span class="sxs-lookup"><span data-stu-id="43774-178">There is no limit to the number of [TypeName](./typename-element-for-viewselectedby-format.md) elements that you can specify, and their order is not significant.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <TableControl>...</TableControl>
</View>
```

<span data-ttu-id="43774-179">Для указания объектов, используемых табличным представлением, можно использовать следующие XML-элементы:</span><span class="sxs-lookup"><span data-stu-id="43774-179">The following XML elements can be used to specify the objects that are used by the table view:</span></span>

- <span data-ttu-id="43774-180">Элемент [виевселектедби](./viewselectedby-element-format.md) определяет, какие объекты отображаются в представлении списка.</span><span class="sxs-lookup"><span data-stu-id="43774-180">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines which objects are displayed by the list view.</span></span>

- <span data-ttu-id="43774-181">Элемент [TypeName](./typename-element-for-viewselectedby-format.md) задает объект .NET, отображаемый представлением.</span><span class="sxs-lookup"><span data-stu-id="43774-181">The [TypeName](./typename-element-for-viewselectedby-format.md) element specifies the .NET object that is displayed by the view.</span></span> <span data-ttu-id="43774-182">Требуется полное имя типа .NET.</span><span class="sxs-lookup"><span data-stu-id="43774-182">The fully qualified .NET type name is required.</span></span> <span data-ttu-id="43774-183">Необходимо указать по крайней мере один тип или набор элементов для представления, но максимальное количество заданных объектов не предусмотрено.</span><span class="sxs-lookup"><span data-stu-id="43774-183">You must specify at least one type or selection set for the view, but there is no maximum number of elements that can be specified.</span></span>

<span data-ttu-id="43774-184">В следующем примере используются элементы [виевселектедби](./viewselectedby-element-format.md) и [селектионсетнаме](./selectionsetname-element-for-viewselectedby-format.md) .</span><span class="sxs-lookup"><span data-stu-id="43774-184">The following example uses the [ViewSelectedBy](./viewselectedby-element-format.md) and [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) elements.</span></span> <span data-ttu-id="43774-185">Используйте наборы выбора, в которых имеется связанный набор объектов, отображаемых с помощью нескольких представлений, например при определении представления списка и табличного представления для тех же объектов.</span><span class="sxs-lookup"><span data-stu-id="43774-185">Use selection sets where you have a related set of objects that are displayed using multiple views, such as when you define a list view and a table view for the same objects.</span></span> <span data-ttu-id="43774-186">Дополнительные сведения о создании набора выбора см. в разделе [Определение наборов выбора](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="43774-186">For more information about how to create a selection set, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <SelectionSetName>.NET Type Set</SelectionSetName>
  </ViewSelectedBy>
  <TableControl>...</TableControl>
</View>
```

<span data-ttu-id="43774-187">Для указания объектов, используемых представлением списка, можно использовать следующие XML-элементы:</span><span class="sxs-lookup"><span data-stu-id="43774-187">The following XML elements can be used to specify the objects that are used by the list view:</span></span>

- <span data-ttu-id="43774-188">Элемент [виевселектедби](./viewselectedby-element-format.md) определяет, какие объекты отображаются в представлении списка.</span><span class="sxs-lookup"><span data-stu-id="43774-188">The [ViewSelectedBy](./viewselectedby-element-format.md) element defines which objects are displayed by the list view.</span></span>

- <span data-ttu-id="43774-189">Элемент [селектионсетнаме](./selectionsetname-element-for-viewselectedby-format.md) указывает набор объектов, которые могут быть отображены представлением.</span><span class="sxs-lookup"><span data-stu-id="43774-189">The [SelectionSetName](./selectionsetname-element-for-viewselectedby-format.md) element specifies a set of objects that can be displayed by the view.</span></span> <span data-ttu-id="43774-190">Необходимо указать хотя бы один набор выбора или тип для представления, но максимальное количество элементов, которое можно указать, не существует.</span><span class="sxs-lookup"><span data-stu-id="43774-190">You must specify at least one selection set or type for the view, but there is no maximum number of elements that can be specified.</span></span>

<span data-ttu-id="43774-191">В следующем примере показано, как определить объекты, отображаемые определенным определением табличного представления с помощью элемента [ентриселектедби](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md) .</span><span class="sxs-lookup"><span data-stu-id="43774-191">The following example shows how to define the objects displayed by a specific definition of the table view using the [EntrySelectedBy](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md) element.</span></span> <span data-ttu-id="43774-192">С помощью этого элемента можно указать имя типа .NET объекта, набор элементов выбора объектов или условие выбора, которое указывает, когда используется определение.</span><span class="sxs-lookup"><span data-stu-id="43774-192">Using this element, you can specify the .NET type name of the object, a selection set of objects, or a selection condition that specifies when the definition is used.</span></span> <span data-ttu-id="43774-193">Дополнительные сведения о создании условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="43774-193">For more information about how to create a selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

> [!NOTE]
> <span data-ttu-id="43774-194">При создании нескольких определений табличного представления нельзя указывать разные заголовки столбцов.</span><span class="sxs-lookup"><span data-stu-id="43774-194">When creating multiple definitions of the table view you cannot specify different column headers.</span></span> <span data-ttu-id="43774-195">Можно указать только то, что отображается в строках таблицы, например, какие объекты отображаются.</span><span class="sxs-lookup"><span data-stu-id="43774-195">You can specify only what is displayed in the rows of the table, such as what objects are displayed.</span></span>

```xml
<TableRowEntry>
  <EntrySelectedBy>
    <TypeName>.NET Type</TypeName>
  </EntrySelectedBy>
</TableRowEntry>
```

<span data-ttu-id="43774-196">Следующие XML-элементы можно использовать для указания объектов, которые используются в определенном определении представления списка:</span><span class="sxs-lookup"><span data-stu-id="43774-196">The following XML elements can be used to specify the objects that are used by a specific definition of the list view:</span></span>

- <span data-ttu-id="43774-197">Элемент [ентриселектедби](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md) определяет, какие объекты отображаются в определении.</span><span class="sxs-lookup"><span data-stu-id="43774-197">The [EntrySelectedBy](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md) element defines which objects are displayed by the definition.</span></span>

- <span data-ttu-id="43774-198">Элемент [TypeName](./typename-element-for-entryselectedby-for-listcontrol-format.md) указывает объект .NET, который отображается в определении.</span><span class="sxs-lookup"><span data-stu-id="43774-198">The [TypeName](./typename-element-for-entryselectedby-for-listcontrol-format.md) element specifies the .NET object that is displayed by the definition.</span></span> <span data-ttu-id="43774-199">При использовании этого элемента требуется полное имя типа .NET.</span><span class="sxs-lookup"><span data-stu-id="43774-199">When using this element, the fully qualified .NET type name is required.</span></span> <span data-ttu-id="43774-200">Необходимо указать по крайней мере один тип, набор выбора или условие выбора для определения, но максимальное число элементов, которое можно указать, не предусмотрено.</span><span class="sxs-lookup"><span data-stu-id="43774-200">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span>

- <span data-ttu-id="43774-201">Элемент [селектионсетнаме](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md) (не показан) задает набор объектов, которые могут отображаться в этом определении.</span><span class="sxs-lookup"><span data-stu-id="43774-201">The [SelectionSetName](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md) element (not shown) specifies a set of objects that can be displayed by this definition.</span></span> <span data-ttu-id="43774-202">Необходимо указать по крайней мере один тип, набор выбора или условие выбора для определения, но максимальное число элементов, которое можно указать, не предусмотрено.</span><span class="sxs-lookup"><span data-stu-id="43774-202">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span>

- <span data-ttu-id="43774-203">Элемент [селектионкондитион](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md) (не показано) указывает условие, которое должно существовать, чтобы использовать это определение.</span><span class="sxs-lookup"><span data-stu-id="43774-203">The [SelectionCondition](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md) element (not shown) specifies a condition that must exist for this definition to be used.</span></span> <span data-ttu-id="43774-204">Необходимо указать по крайней мере один тип, набор выбора или условие выбора для определения, но максимальное число элементов, которое можно указать, не предусмотрено.</span><span class="sxs-lookup"><span data-stu-id="43774-204">You must specify at least one type, selection set, or selection condition for the definition, but there is no maximum number of elements that can be specified.</span></span> <span data-ttu-id="43774-205">Дополнительные сведения об определении условий выбора см. в разделе [Определение условий для отображения данных](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="43774-205">For more information about defining selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="using-format-strings"></a><span data-ttu-id="43774-206">Использование строк формата</span><span class="sxs-lookup"><span data-stu-id="43774-206">Using Format Strings</span></span>

<span data-ttu-id="43774-207">Строки форматирования можно добавить в представление, чтобы дополнительно определить способ отображения данных.</span><span class="sxs-lookup"><span data-stu-id="43774-207">Formatting strings can be added to a view to further define how the data is displayed.</span></span> <span data-ttu-id="43774-208">В следующем примере показано, как определить строку форматирования для значения `StartTime` Свойства.</span><span class="sxs-lookup"><span data-stu-id="43774-208">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<TableColumnItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</TableColumnItem>
```

<span data-ttu-id="43774-209">Для указания шаблона формата можно использовать следующие XML-элементы:</span><span class="sxs-lookup"><span data-stu-id="43774-209">The following XML elements can be used to specify a format pattern:</span></span>

- <span data-ttu-id="43774-210">Элемент [таблеколумнитем](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) определяет свойство или скрипт, значение которого отображается в столбце строки.</span><span class="sxs-lookup"><span data-stu-id="43774-210">The [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) element defines the property or script whose value is displayed in the column of the row.</span></span> <span data-ttu-id="43774-211">Для каждого столбца строки требуется элемент [таблеколумнитем](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) .</span><span class="sxs-lookup"><span data-stu-id="43774-211">A [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) element is required for each column of the row.</span></span> <span data-ttu-id="43774-212">Первая запись отображается в первом столбце, второй элемент во втором столбце и т. д.</span><span class="sxs-lookup"><span data-stu-id="43774-212">The first entry is displayed in first column, the second entry in the second column, and so on.</span></span>

- <span data-ttu-id="43774-213">Элемент [PropertyName](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md) указывает свойство, значение которого отображается в строке.</span><span class="sxs-lookup"><span data-stu-id="43774-213">The [PropertyName](./propertyname-element-for-tablecolumnitem-for-tablecontrol-format.md) element specifies the property whose value is displayed in the row.</span></span> <span data-ttu-id="43774-214">Необходимо указать либо свойство, либо скрипт, но нельзя указать и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="43774-214">You must specify either a property or a script, but you cannot specify both.</span></span>

- <span data-ttu-id="43774-215">Элемент [FormatString](./label-element-for-listitem-for-listcontrol-format.md) задает шаблон формата, определяющий способ отображения значения свойства или скрипта.</span><span class="sxs-lookup"><span data-stu-id="43774-215">The [FormatString](./label-element-for-listitem-for-listcontrol-format.md) element specifies a format pattern that defines how the property or script value is displayed.</span></span>

<span data-ttu-id="43774-216">В следующем примере `ToString` метод вызывается для форматирования значения скрипта.</span><span class="sxs-lookup"><span data-stu-id="43774-216">In the following example, the `ToString` method is called to format the value of the script.</span></span> <span data-ttu-id="43774-217">Скрипты могут вызывать любой метод объекта.</span><span class="sxs-lookup"><span data-stu-id="43774-217">Scripts can call any method of an object.</span></span> <span data-ttu-id="43774-218">Таким образом, если у объекта есть метод, такой как `ToString` , имеющий параметры форматирования, скрипт может вызвать этот метод для форматирования выходного значения скрипта.</span><span class="sxs-lookup"><span data-stu-id="43774-218">Therefore, if an object has a method, such as `ToString`, that has formatting parameters, the script can call that method to format the output value of the script.</span></span>

```xml
<ListItem>
  <ScriptBlock>
    [String]::Format("(0,10) (1,8)", .LastWriteTime.ToString("d"),
    $_.LastWriteTime.Totring("t"))
  </ScriptBlock>
</ListItem>
```

<span data-ttu-id="43774-219">Для вызова метода можно использовать следующий XML-элемент `ToString` :</span><span class="sxs-lookup"><span data-stu-id="43774-219">The following XML element can be used to calling the `ToString` method:</span></span>

- <span data-ttu-id="43774-220">Элемент [таблеколумнитем](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) определяет свойство или скрипт, значение которого отображается в столбце строки.</span><span class="sxs-lookup"><span data-stu-id="43774-220">The [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) element defines the property or script whose value is displayed in the column of the row.</span></span> <span data-ttu-id="43774-221">Для каждого столбца строки требуется элемент [таблеколумнитем](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) .</span><span class="sxs-lookup"><span data-stu-id="43774-221">A [TableColumnItem](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md) element is required for each column of the row.</span></span> <span data-ttu-id="43774-222">Первая запись отображается в первом столбце, второй элемент во втором столбце и т. д.</span><span class="sxs-lookup"><span data-stu-id="43774-222">The first entry is displayed in first column, the second entry in the second column, and so on.</span></span>

- <span data-ttu-id="43774-223">Элемент [ScriptBlock](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md) указывает скрипт, значение которого отображается в строке.</span><span class="sxs-lookup"><span data-stu-id="43774-223">The [ScriptBlock](./scriptblock-element-for-tablecolumnitem-for-tablecontrol-format.md) element specifies the script whose value is displayed in the row.</span></span> <span data-ttu-id="43774-224">Необходимо указать либо скрипт, либо свойство, но нельзя указать и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="43774-224">You must specify either a script or a property, but you cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="43774-225">См. также:</span><span class="sxs-lookup"><span data-stu-id="43774-225">See Also</span></span>

[<span data-ttu-id="43774-226">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="43774-226">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
