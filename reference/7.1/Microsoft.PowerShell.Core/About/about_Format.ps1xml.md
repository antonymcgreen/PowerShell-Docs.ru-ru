---
description: Начиная с PowerShell 6, представления по умолчанию для объектов определяются в исходном коде PowerShell.  Можно создать собственные файлы, `Format.ps1xml` чтобы изменить отображение объектов или определить отображение по умолчанию для новых типов объектов, создаваемых в PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 11/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_format.ps1xml?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Format.ps1xml
ms.openlocfilehash: c638001c8442284224c0cb554513ef988ba59f3d
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232466"
---
# <a name="about-formatps1xml"></a><span data-ttu-id="ac406-105">Сведения о Format.ps1XML</span><span class="sxs-lookup"><span data-stu-id="ac406-105">About Format.ps1xml</span></span>

## <a name="short-description"></a><span data-ttu-id="ac406-106">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="ac406-106">Short description</span></span>

<span data-ttu-id="ac406-107">Начиная с PowerShell 6, представления по умолчанию для объектов определяются в исходном коде PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac406-107">Beginning in PowerShell 6, the default views for objects are defined in PowerShell source code.</span></span>

<span data-ttu-id="ac406-108">Можно создать собственные файлы, `Format.ps1xml` чтобы изменить отображение объектов или определить отображение по умолчанию для новых типов объектов, создаваемых в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac406-108">You can create your own `Format.ps1xml` files to change the display of objects or to define default displays for new object types that you create in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="ac406-109">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="ac406-109">Long description</span></span>

<span data-ttu-id="ac406-110">Начиная с PowerShell 6, представления по умолчанию определяются в исходном коде PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac406-110">Beginning in PowerShell 6, the default views are defined in PowerShell source code.</span></span> <span data-ttu-id="ac406-111">`Format.ps1xml`Файлы из powershell 5,1 и более ранних версий не существуют в PowerShell 6 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="ac406-111">The `Format.ps1xml` files from PowerShell 5.1 and earlier versions don't exist in PowerShell 6 and later versions.</span></span>

<span data-ttu-id="ac406-112">Исходный код PowerShell определяет отображение объектов по умолчанию в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac406-112">The PowerShell source code defines the default display of objects in the PowerShell console.</span></span> <span data-ttu-id="ac406-113">Можно создать собственные файлы, `Format.ps1xml` чтобы изменить отображение объектов или определить отображение по умолчанию для новых типов объектов, создаваемых в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac406-113">You can create your own `Format.ps1xml` files to change the display of objects or to define default displays for new object types that you create in PowerShell.</span></span>

<span data-ttu-id="ac406-114">Когда в PowerShell отображается объект, он использует данные в структурированных файлах форматирования для определения отображения объекта по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ac406-114">When PowerShell displays an object, it uses the data in structured formatting files to determine the default display of the object.</span></span> <span data-ttu-id="ac406-115">Данные в файлах форматирования определяют, отображается ли объект в таблице или в списке, и определяет, какие свойства отображаются по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ac406-115">The data in the formatting files determines whether the object is rendered in a table or in a list, and it determines which properties are displayed by default.</span></span>

<span data-ttu-id="ac406-116">Форматирование влияет только на отображение.</span><span class="sxs-lookup"><span data-stu-id="ac406-116">The formatting affects the display only.</span></span> <span data-ttu-id="ac406-117">Он не влияет на то, какие свойства объекта передаются по конвейеру или каким способом они передаются.</span><span class="sxs-lookup"><span data-stu-id="ac406-117">It doesn't affect which object properties are passed down the pipeline or how they're passed.</span></span> <span data-ttu-id="ac406-118">`Format.ps1xml` файлы нельзя использовать для настройки формата выходных данных для хэш-таблиц.</span><span class="sxs-lookup"><span data-stu-id="ac406-118">`Format.ps1xml` files can't be used to customize the output format for hash tables.</span></span>

<span data-ttu-id="ac406-119">`.ps1xml`Файл форматирования может определять четыре различных представления каждого объекта:</span><span class="sxs-lookup"><span data-stu-id="ac406-119">A `.ps1xml` formatting file can define four different views of each object:</span></span>

- <span data-ttu-id="ac406-120">Таблица</span><span class="sxs-lookup"><span data-stu-id="ac406-120">Table</span></span>
- <span data-ttu-id="ac406-121">Список</span><span class="sxs-lookup"><span data-stu-id="ac406-121">List</span></span>
- <span data-ttu-id="ac406-122">Широкий</span><span class="sxs-lookup"><span data-stu-id="ac406-122">Wide</span></span>
- <span data-ttu-id="ac406-123">Другой</span><span class="sxs-lookup"><span data-stu-id="ac406-123">Custom</span></span>

<span data-ttu-id="ac406-124">Например, когда выходные данные `Get-ChildItem` команды передаются в `Format-List` команду, `Format-List` использует представление списка, определенное в исходном коде, для определения способа отображения объектов файлов и папок в виде списка.</span><span class="sxs-lookup"><span data-stu-id="ac406-124">For example, when the output of a `Get-ChildItem` command is piped to a `Format-List` command, `Format-List` uses the list view defined in the source code to determine how to display the file and folder objects as a list.</span></span>

<span data-ttu-id="ac406-125">Если файл форматирования содержит более одного представления объекта, PowerShell применяет первое найденное представление.</span><span class="sxs-lookup"><span data-stu-id="ac406-125">When a formatting file includes more than one view of an object, PowerShell applies the first view that it finds.</span></span>

<span data-ttu-id="ac406-126">В пользовательском `Format.ps1xml` файле представление определяется набором XML-тегов, описывающих имя представления, тип объекта, к которому он может быть применен, заголовки столбцов и свойства, отображаемые в тексте представления.</span><span class="sxs-lookup"><span data-stu-id="ac406-126">In a custom `Format.ps1xml` file, a view is defined by a set of XML tags that describe the name of the view, the type of object to which it can be applied, the column headers, and the properties that are displayed in the body of the view.</span></span> <span data-ttu-id="ac406-127">Формат в `Format.ps1xml` файлах применяется непосредственно перед тем, как данные представлены пользователю.</span><span class="sxs-lookup"><span data-stu-id="ac406-127">The format in `Format.ps1xml` files is applied just before the data is presented to the user.</span></span>

## <a name="creating-new-formatps1xml-files"></a><span data-ttu-id="ac406-128">Создание новых Format.ps1XML-файлов</span><span class="sxs-lookup"><span data-stu-id="ac406-128">Creating new Format.ps1xml files</span></span>

<span data-ttu-id="ac406-129">Чтобы изменить формат отображения существующего представления объектов или добавить представления для новых объектов, создайте собственные `Format.ps1xml` файлы, а затем добавьте их в сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac406-129">To change the display format of an existing object view, or to add views for new objects, create your own `Format.ps1xml` files, and then add them to your PowerShell session.</span></span>

<span data-ttu-id="ac406-130">Чтобы создать `Format.ps1xml` файл для определения пользовательского представления, используйте командлеты [Get-FormatData](xref:Microsoft.PowerShell.Utility.Get-FormatData) и [Export-FormatData](xref:Microsoft.PowerShell.Utility.Export-FormatData) .</span><span class="sxs-lookup"><span data-stu-id="ac406-130">To create a `Format.ps1xml` file to define a custom view, use the [Get-FormatData](xref:Microsoft.PowerShell.Utility.Get-FormatData) and [Export-FormatData](xref:Microsoft.PowerShell.Utility.Export-FormatData) cmdlets.</span></span> <span data-ttu-id="ac406-131">Для редактирования файла используйте текстовый редактор.</span><span class="sxs-lookup"><span data-stu-id="ac406-131">Use a text editor to edit the file.</span></span> <span data-ttu-id="ac406-132">Файл можно сохранить в любой каталог, к которому может получить доступ PowerShell, например в подкаталог `$HOME` .</span><span class="sxs-lookup"><span data-stu-id="ac406-132">The file can be saved to any directory that PowerShell can access, such as a subdirectory of `$HOME`.</span></span>

<span data-ttu-id="ac406-133">Чтобы изменить форматирование текущего представления, найдите представление в файле форматирования, а затем используйте теги для изменения представления.</span><span class="sxs-lookup"><span data-stu-id="ac406-133">To change the formatting of a current view, locate the view in the formatting file, and then use the tags to change the view.</span></span> <span data-ttu-id="ac406-134">Чтобы создать представление для нового типа объекта, создайте новое представление или используйте существующее представление в качестве модели.</span><span class="sxs-lookup"><span data-stu-id="ac406-134">To create a view for a new object type, create a new view, or use an existing view as a model.</span></span> <span data-ttu-id="ac406-135">Теги описаны в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="ac406-135">The tags are described in the next section.</span></span> <span data-ttu-id="ac406-136">Затем можно удалить все остальные представления в файле, чтобы изменения были очевидны для любого, который просматривает файл.</span><span class="sxs-lookup"><span data-stu-id="ac406-136">You can then delete all the other views in the file so that the changes are obvious to anyone examining the file.</span></span>

<span data-ttu-id="ac406-137">После сохранения изменений используйте [Update-FormatData](xref:Microsoft.PowerShell.Utility.Update-FormatData) , чтобы добавить новый файл в сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac406-137">After you save the changes, use the [Update-FormatData](xref:Microsoft.PowerShell.Utility.Update-FormatData) to add the new file to your PowerShell session.</span></span> <span data-ttu-id="ac406-138">Если необходимо, чтобы представление было иметь приоритет над представлением, определенным во встроенных файлах, используйте параметр **препендпас** .</span><span class="sxs-lookup"><span data-stu-id="ac406-138">If you want your view to take precedence over a view defined in the built-in files, use the **PrependPath** parameter.</span></span> <span data-ttu-id="ac406-139">`Update-FormatData` влияет только на текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="ac406-139">`Update-FormatData` affects only the current session.</span></span> <span data-ttu-id="ac406-140">Чтобы внести изменения во все будущие сеансы, добавьте `Update-FormatData` команду в профиль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac406-140">To make the change to all future sessions, add the `Update-FormatData` command to your PowerShell profile.</span></span>

### <a name="example-add-calendar-data-to-culture-objects"></a><span data-ttu-id="ac406-141">Пример. Добавление данных календаря в объекты языка и региональных параметров</span><span class="sxs-lookup"><span data-stu-id="ac406-141">Example: Add calendar data to culture objects</span></span>

<span data-ttu-id="ac406-142">В этом примере показано, как изменить форматирование объектов языка и региональных параметров **System. Globalization. CultureInfo** , созданных `Get-Culture` командлетом в текущем сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac406-142">This example shows how to change the formatting of the culture objects **System.Globalization.CultureInfo** generated by the `Get-Culture` cmdlet in the current PowerShell session.</span></span> <span data-ttu-id="ac406-143">Команды в примере добавляют свойство **Calendar** в представление таблицы по умолчанию, отображающее объекты языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="ac406-143">The commands in the example add the **Calendar** property to the default table view display of culture objects.</span></span>

<span data-ttu-id="ac406-144">Чтобы начать, получите данные форматирования из файла исходного кода и создайте `Format.ps1xml` файл, содержащий текущее представление объектов языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="ac406-144">To begin, get the format data from the source code file and create a `Format.ps1xml` file that contains the current view of the culture objects.</span></span>

```powershell
Get-FormatData -TypeName System.Globalization.CultureInfo |
  Export-FormatData -Path $HOME\Format\CultureInfo.Format.ps1xml
```

<span data-ttu-id="ac406-145">Откройте `CultureInfo.Format.ps1xml` файл в любом XML-или текстовом редакторе, например Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="ac406-145">Open the `CultureInfo.Format.ps1xml` file in any XML or text editor, such as Visual Studio Code.</span></span> <span data-ttu-id="ac406-146">Следующий XML-код определяет представления объекта **CultureInfo** .</span><span class="sxs-lookup"><span data-stu-id="ac406-146">The following XML defines the views of the **CultureInfo** object.</span></span>

<span data-ttu-id="ac406-147">`CultureInfo.Format.ps1xml`Файл должен выглядеть, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="ac406-147">The `CultureInfo.Format.ps1xml` file should look like the following sample:</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<Configuration>
  <ViewDefinitions>
    <View>
      <Name>System.Globalization.CultureInfo</Name>
      <ViewSelectedBy>
        <TypeName>System.Globalization.CultureInfo</TypeName>
      </ViewSelectedBy>
      <TableControl>
        <TableHeaders>
          <TableColumnHeader>
            <Width>16</Width>
          </TableColumnHeader>
          <TableColumnHeader>
            <Width>16</Width>
          </TableColumnHeader>
          <TableColumnHeader />
        </TableHeaders>
        <TableRowEntries>
          <TableRowEntry>
            <TableColumnItems>
              <TableColumnItem>
                <PropertyName>LCID</PropertyName>
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
  </ViewDefinitions>
</Configuration>
```

<span data-ttu-id="ac406-148">Создайте новый столбец для свойства **Calendar** , добавив новый набор `<TableColumnHeader>` тегов.</span><span class="sxs-lookup"><span data-stu-id="ac406-148">Create a new column for the **Calendar** property by adding a new set of `<TableColumnHeader>` tags.</span></span> <span data-ttu-id="ac406-149">Значение свойства **Calendar** может быть длинным, поэтому укажите в качестве значения 45 символов `<Width>` .</span><span class="sxs-lookup"><span data-stu-id="ac406-149">The value of the **Calendar** property can be long, so specify a value of 45 characters as the `<Width>`.</span></span>

```xml
<TableHeaders>
  <TableColumnHeader>
    <Width>16</Width>
  </TableColumnHeader>
  <TableColumnHeader>
    <Width>16</Width>
  </TableColumnHeader>
  <TableColumnHeader>
    <Width>45</Width>
  </TableColumnHeader>
  <TableColumnHeader/>
</TableHeaders>
```

<span data-ttu-id="ac406-150">Добавьте новый элемент столбца для **Calendar** в строки таблицы с помощью `<TableColumnItem>` `<PropertyName` тегов и.</span><span class="sxs-lookup"><span data-stu-id="ac406-150">Add a new column item for **Calendar** in the table rows using the `<TableColumnItem>` and `<PropertyName` tags:</span></span>

```xml
<TableRowEntries>
  <TableRowEntry>
    <TableColumnItems>
      <TableColumnItem>
        <PropertyName>LCID</PropertyName>
      </TableColumnItem>
      <TableColumnItem>
        <PropertyName>Name</PropertyName>
      </TableColumnItem>
      <TableColumnItem>
        <PropertyName>Calendar</PropertyName>
      </TableColumnItem>
      <TableColumnItem>
        <PropertyName>DisplayName</PropertyName>
      </TableColumnItem>
    </TableColumnItems>
  </TableRowEntry>
</TableRowEntries>
```

<span data-ttu-id="ac406-151">Сохраните файл и закройте его.</span><span class="sxs-lookup"><span data-stu-id="ac406-151">Save and close the file.</span></span> <span data-ttu-id="ac406-152">Используйте `Update-FormatData` , чтобы добавить новый файл форматирования в текущий сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac406-152">Use `Update-FormatData` to add the new format file to the current PowerShell session.</span></span>

<span data-ttu-id="ac406-153">В этом примере используется параметр **препендпас** для размещения нового файла в порядке приоритета, отличном от исходного файла.</span><span class="sxs-lookup"><span data-stu-id="ac406-153">This example uses the **PrependPath** parameter to place the new file in a higher precedence order than the original file.</span></span> <span data-ttu-id="ac406-154">Дополнительные сведения см. в разделе [Update-FormatData](xref:Microsoft.PowerShell.Utility.Update-FormatData).</span><span class="sxs-lookup"><span data-stu-id="ac406-154">For more information, see [Update-FormatData](xref:Microsoft.PowerShell.Utility.Update-FormatData).</span></span>

```powershell
Update-FormatData -PrependPath $HOME\Format\CultureInfo.Format.ps1xml
```

<span data-ttu-id="ac406-155">Чтобы проверить изменение, введите `Get-Culture` и проверьте выходные данные, включающие в себя свойство **Calendar** .</span><span class="sxs-lookup"><span data-stu-id="ac406-155">To test the change, type `Get-Culture` and review the output that includes the **Calendar** property.</span></span>

```powershell
Get-Culture
```

```Output
LCID  Name   Calendar                                DisplayName
----  ----   --------                                -----------
1033  en-US  System.Globalization.GregorianCalendar  English (United States)
```

## <a name="the-xml-in-formatps1xml-files"></a><span data-ttu-id="ac406-156">XML-файлы в Format.ps1XML-файлах</span><span class="sxs-lookup"><span data-stu-id="ac406-156">The XML in Format.ps1xml files</span></span>

<span data-ttu-id="ac406-157">Полное определение схемы можно найти в файле [format. xsd](https://github.com/PowerShell/PowerShell/blob/master/src/Schemas/Format.xsd) в репозитории исходного кода PowerShell на сайте GitHub.</span><span class="sxs-lookup"><span data-stu-id="ac406-157">The full schema definition can be found in [Format.xsd](https://github.com/PowerShell/PowerShell/blob/master/src/Schemas/Format.xsd) in the PowerShell source code repository on GitHub.</span></span>

<span data-ttu-id="ac406-158">Раздел **виевдефинитионс** каждого `Format.ps1xml` файла содержит `<View>` теги, определяющие каждое представление.</span><span class="sxs-lookup"><span data-stu-id="ac406-158">The **ViewDefinitions** section of each `Format.ps1xml` file contains the `<View>` tags that define each view.</span></span> <span data-ttu-id="ac406-159">Типичный `<View>` тег содержит следующие Теги:</span><span class="sxs-lookup"><span data-stu-id="ac406-159">A typical `<View>` tag includes the following tags:</span></span>

- <span data-ttu-id="ac406-160">`<Name>` Определяет имя представления.</span><span class="sxs-lookup"><span data-stu-id="ac406-160">`<Name>` identifies the name of the view.</span></span>
- <span data-ttu-id="ac406-161">`<ViewSelectedBy>` Указывает тип или типы объектов, к которым применяется представление.</span><span class="sxs-lookup"><span data-stu-id="ac406-161">`<ViewSelectedBy>` specifies the object type or types to which the view applies.</span></span>
- <span data-ttu-id="ac406-162">`<GroupBy>` Указывает, как элементы представления будут объединены в группы.</span><span class="sxs-lookup"><span data-stu-id="ac406-162">`<GroupBy>` specifies how items in the view will be combined in groups.</span></span>
- <span data-ttu-id="ac406-163">`<TableControl>`, `<ListControl>` , `<WideControl>` и `<CustomControl>` содержат теги, которые определяют, как будет отображаться каждый элемент.</span><span class="sxs-lookup"><span data-stu-id="ac406-163">`<TableControl>`, `<ListControl>`, `<WideControl>`, and `<CustomControl>` contain the tags that specify how each item will be displayed.</span></span>

### <a name="viewselectedby-tag"></a><span data-ttu-id="ac406-164">Тег Виевселектедби</span><span class="sxs-lookup"><span data-stu-id="ac406-164">ViewSelectedBy tag</span></span>

<span data-ttu-id="ac406-165">`<ViewSelectedBy>`Тег может содержать `<TypeName>` тег для каждого типа объектов, к которому применяется представление.</span><span class="sxs-lookup"><span data-stu-id="ac406-165">The `<ViewSelectedBy>` tag can contain a `<TypeName>` tag for each object type to which the view applies.</span></span> <span data-ttu-id="ac406-166">Или может содержать `<SelectionSetName>` тег, который ссылается на набор выбора, определенный в других местах с помощью `<SelectionSet>` тега.</span><span class="sxs-lookup"><span data-stu-id="ac406-166">Or, it can contain a `<SelectionSetName>` tag that references a selection set that is defined elsewhere by using a `<SelectionSet>` tag.</span></span>

### <a name="groupby-tag"></a><span data-ttu-id="ac406-167">Тег GroupBy</span><span class="sxs-lookup"><span data-stu-id="ac406-167">GroupBy tag</span></span>

<span data-ttu-id="ac406-168">`<GroupBy>`Тег содержит `<PropertyName>` тег, указывающий свойство объекта, по которому группируются элементы.</span><span class="sxs-lookup"><span data-stu-id="ac406-168">The `<GroupBy>` tag contains a `<PropertyName>` tag that specifies the object property by which items are to be grouped.</span></span> <span data-ttu-id="ac406-169">Он также содержит `<Label>` тег, указывающий строку, которая будет использоваться в качестве метки для каждой группы `<CustomControlName>` , или тег, который ссылается на пользовательский элемент управления, определенный в любом расположении с помощью `<Control>` тега.</span><span class="sxs-lookup"><span data-stu-id="ac406-169">It also contains either a `<Label>` tag that specifies a string to be used as a label for each group or a `<CustomControlName>` tag that references a custom control defined elsewhere using a `<Control>` tag.</span></span> <span data-ttu-id="ac406-170">`<Control>`Тег содержит `<Name>` тег и `<CustomControl>` тег.</span><span class="sxs-lookup"><span data-stu-id="ac406-170">The `<Control>` tag contains a `<Name>` tag and a `<CustomControl>` tag.</span></span>

### <a name="tablecontroltag"></a><span data-ttu-id="ac406-171">таблеконтролтаг</span><span class="sxs-lookup"><span data-stu-id="ac406-171">TableControlTag</span></span>

<span data-ttu-id="ac406-172">`<TableControl>`Тег обычно содержит `<TableHeaders>` теги и `<TableRowEntries>` , определяющие форматирование головок и строк таблицы.</span><span class="sxs-lookup"><span data-stu-id="ac406-172">The `<TableControl>` tag typically contains `<TableHeaders>` and `<TableRowEntries>` tags that define the formatting for the table's heads and rows.</span></span> <span data-ttu-id="ac406-173">`<TableHeaders>`Тег обычно содержит `<TableColumnHeader>` теги, которые содержат `<Label>` теги, `<Width>` и `<Alignment>` .</span><span class="sxs-lookup"><span data-stu-id="ac406-173">The `<TableHeaders>` tag typically contains `<TableColumnHeader>` tags that contain `<Label>`, `<Width>`, and `<Alignment>` tags.</span></span> <span data-ttu-id="ac406-174">`<TableRowEntries>`Тег содержит `<TableRowEntry>` теги для каждой строки в таблице.</span><span class="sxs-lookup"><span data-stu-id="ac406-174">The `<TableRowEntries>` tag contains `<TableRowEntry>` tags for each row in the table.</span></span> <span data-ttu-id="ac406-175">`<TableRowEntry>`Тег содержит `<TableColumnItems>` тег, который содержит `<TableColumnItem>` тег для каждого столбца в строке.</span><span class="sxs-lookup"><span data-stu-id="ac406-175">The `<TableRowEntry>` tag contains a `<TableColumnItems>` tag that contains a `<TableColumnItem>` tag for each column in the row.</span></span> <span data-ttu-id="ac406-176">Как правило, `<TableColumnItem>` тег содержит либо `<PropertyName>` тег, определяющий свойство объекта, которое должно отображаться в определенном расположении, либо `<ScriptBlock>` тег, содержащий код скрипта, который вычисляет результат, отображаемый в расположении.</span><span class="sxs-lookup"><span data-stu-id="ac406-176">Typically, the `<TableColumnItem>` tag contains either a `<PropertyName>` tag that identifies the object property to be displayed in the defined location, or a `<ScriptBlock>` tag that contains script code that calculates a result that is to be displayed in the location.</span></span>

> [!NOTE]
> <span data-ttu-id="ac406-177">Блоки сценариев также можно использовать в других местах, где вычисленные результаты могут быть полезными.</span><span class="sxs-lookup"><span data-stu-id="ac406-177">Script blocks can also be used elsewhere in locations where calculated results can be useful.</span></span>

<span data-ttu-id="ac406-178">`<TableColumnItem>`Тег также может содержать `<FormatString>` тег, указывающий, как будут отображаться свойство или вычисляемые результаты.</span><span class="sxs-lookup"><span data-stu-id="ac406-178">The `<TableColumnItem>` tag can also contain a `<FormatString>` tag that specifies how the property or the calculated results will be displayed.</span></span>

### <a name="listcontrol-tag"></a><span data-ttu-id="ac406-179">Тег ListControl</span><span class="sxs-lookup"><span data-stu-id="ac406-179">ListControl tag</span></span>

<span data-ttu-id="ac406-180">`<ListControl>`Тег обычно содержит `<ListEntries>` тег.</span><span class="sxs-lookup"><span data-stu-id="ac406-180">The `<ListControl>` tag typically contains a `<ListEntries>` tag.</span></span> <span data-ttu-id="ac406-181">`<ListEntries>`Тег содержит `<ListEntry>` тег.</span><span class="sxs-lookup"><span data-stu-id="ac406-181">The `<ListEntries>` tag contains a `<ListEntry>` tag.</span></span> <span data-ttu-id="ac406-182">`<ListEntry>`Тег содержит `<ListItems>` тег.</span><span class="sxs-lookup"><span data-stu-id="ac406-182">The `<ListEntry>` tag contains a `<ListItems>` tag.</span></span> <span data-ttu-id="ac406-183">`<ListItems>`Тег содержит `<ListItem>` теги, которые содержат `<PropertyName>` теги.</span><span class="sxs-lookup"><span data-stu-id="ac406-183">The `<ListItems>` tag contains `<ListItem>` tags, which contain `<PropertyName>` tags.</span></span> <span data-ttu-id="ac406-184">`<PropertyName>`Теги указывают свойство объекта, которое должно отображаться в указанном месте списка.</span><span class="sxs-lookup"><span data-stu-id="ac406-184">The `<PropertyName>` tags specify the object property to be displayed at the specified location in the list.</span></span> <span data-ttu-id="ac406-185">Если выбор представления определен с помощью набора элементов, `<ListControl>` `<ListEntry>` теги и также могут содержать `<EntrySelectedBy>` тег, содержащий один или несколько `<TypeName>` тегов.</span><span class="sxs-lookup"><span data-stu-id="ac406-185">If the view selection is defined using a selection set, the `<ListControl>` and `<ListEntry>` tags can also contain an `<EntrySelectedBy>` tag that contains one or more `<TypeName>` tags.</span></span> <span data-ttu-id="ac406-186">Эти `<TypeName>` теги указывают тип объекта, который должен `<ListControl>` отображаться в теге.</span><span class="sxs-lookup"><span data-stu-id="ac406-186">These `<TypeName>` tags specify the object type that the `<ListControl>` tag is intended to display.</span></span>

### <a name="widecontrol-tag"></a><span data-ttu-id="ac406-187">Тег Видеконтрол</span><span class="sxs-lookup"><span data-stu-id="ac406-187">WideControl tag</span></span>

<span data-ttu-id="ac406-188">`<WideControl>`Тег обычно содержит `<WideEntries>` тег.</span><span class="sxs-lookup"><span data-stu-id="ac406-188">The `<WideControl>` tag typically contains a `<WideEntries>` tag.</span></span> <span data-ttu-id="ac406-189">`<WideEntries>`Тег содержит один или несколько `<WideEntry>` тегов.</span><span class="sxs-lookup"><span data-stu-id="ac406-189">The `<WideEntries>` tag contains one or more `<WideEntry>` tags.</span></span> <span data-ttu-id="ac406-190">`<WideEntry>`Тег обычно содержит `<PropertyName>` тег, указывающий свойство, которое должно отображаться в указанном месте представления.</span><span class="sxs-lookup"><span data-stu-id="ac406-190">A `<WideEntry>` tag typically contains a `<PropertyName>` tag that specifies the property to be displayed at the specified location in the view.</span></span> <span data-ttu-id="ac406-191">`<PropertyName>`Тег может содержать `<FormatString>` тег, указывающий, как должно отображаться свойство.</span><span class="sxs-lookup"><span data-stu-id="ac406-191">The `<PropertyName>` tag can contain a `<FormatString>` tag that specifies how the property is to be displayed.</span></span>

### <a name="customcontrol-tag"></a><span data-ttu-id="ac406-192">Тег ошибка customcontrol</span><span class="sxs-lookup"><span data-stu-id="ac406-192">CustomControl tag</span></span>

<span data-ttu-id="ac406-193">`<CustomControl>`Тег позволяет использовать блок скрипта для определения формата.</span><span class="sxs-lookup"><span data-stu-id="ac406-193">The `<CustomControl>` tag lets you use a script block to define a format.</span></span> <span data-ttu-id="ac406-194">`<CustomControl>`Тег обычно содержит `<CustomEntries>` тег, который содержит несколько `<CustomEntry>` тегов.</span><span class="sxs-lookup"><span data-stu-id="ac406-194">A `<CustomControl>` tag typically contains a `<CustomEntries>` tag that contains multiple `<CustomEntry>` tags.</span></span> <span data-ttu-id="ac406-195">Каждый `<CustomEntry>` тег содержит `<CustomItem>` тег, который может содержать различные теги, которые задают содержимое и форматирование указанного расположения в представлении, включая `<Text>` `<Indentation>` теги,, `<ExpressionBinding>` и `<NewLine>` .</span><span class="sxs-lookup"><span data-stu-id="ac406-195">Each `<CustomEntry>` tag contains a `<CustomItem>` tag that can contain a variety of tags that specify contents and formatting of the specified location in the view, including `<Text>`, `<Indentation>`, `<ExpressionBinding>`, and `<NewLine>` tags.</span></span>

## <a name="tracing-formatps1xml-file-use"></a><span data-ttu-id="ac406-196">Использование трассировки Format.ps1XML-файла</span><span class="sxs-lookup"><span data-stu-id="ac406-196">Tracing Format.ps1xml file use</span></span>

<span data-ttu-id="ac406-197">Чтобы обнаружить ошибки при загрузке или применении `Format.ps1xml` файлов, используйте `Trace-Command` командлет с любым из следующих компонентов формата в качестве значения параметра **Name** :</span><span class="sxs-lookup"><span data-stu-id="ac406-197">To detect errors in the loading or application of `Format.ps1xml` files, use the `Trace-Command` cmdlet with any of the following format components as the value of the **Name** parameter:</span></span>

- <span data-ttu-id="ac406-198">форматфилелоадинг</span><span class="sxs-lookup"><span data-stu-id="ac406-198">FormatFileLoading</span></span>
- <span data-ttu-id="ac406-199">форматвиевбиндинг</span><span class="sxs-lookup"><span data-stu-id="ac406-199">FormatViewBinding</span></span>

<span data-ttu-id="ac406-200">Дополнительные сведения см. в разделе [Trace-Command](xref:Microsoft.PowerShell.Utility.Trace-Command) и [Get-TraceSource](xref:Microsoft.PowerShell.Utility.Get-TraceSource).</span><span class="sxs-lookup"><span data-stu-id="ac406-200">For more information, see [Trace-Command](xref:Microsoft.PowerShell.Utility.Trace-Command) and [Get-TraceSource](xref:Microsoft.PowerShell.Utility.Get-TraceSource).</span></span>

## <a name="signing-a-formatps1xml-file"></a><span data-ttu-id="ac406-201">Подписывание Format.ps1XML-файла</span><span class="sxs-lookup"><span data-stu-id="ac406-201">Signing a Format.ps1xml file</span></span>

<span data-ttu-id="ac406-202">Для защиты пользователей `Format.ps1xml` файла подпишите его с помощью цифровой подписи.</span><span class="sxs-lookup"><span data-stu-id="ac406-202">To protect the users of your `Format.ps1xml` file, sign the file using a digital signature.</span></span> <span data-ttu-id="ac406-203">Дополнительные сведения см. в разделе [about_Signing](about_Signing.md).</span><span class="sxs-lookup"><span data-stu-id="ac406-203">For more information, see [about_Signing](about_Signing.md).</span></span>

## <a name="sample-xml-for-a-format-table-custom-view"></a><span data-ttu-id="ac406-204">Образец XML-кода для Format-Table пользовательского представления</span><span class="sxs-lookup"><span data-stu-id="ac406-204">Sample XML for a Format-Table custom view</span></span>

<span data-ttu-id="ac406-205">Следующий образец XML-кода создает `Format-Table` пользовательское представление для объектов **System. IO. DirectoryInfo** и **System. IO. FileInfo** , созданных `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="ac406-205">The following XML sample creates a `Format-Table` custom view for the **System.IO.DirectoryInfo** and **System.IO.FileInfo** objects created by `Get-ChildItem`.</span></span> <span data-ttu-id="ac406-206">Пользовательское представление называется **мигЦивиев** и добавляет столбец **CreationTime** в таблицу.</span><span class="sxs-lookup"><span data-stu-id="ac406-206">The custom view is named **mygciview** and adds the **CreationTime** column to the table.</span></span>

<span data-ttu-id="ac406-207">Чтобы создать пользовательское представление, используйте `Get-FormatData` `Export-FormatData` командлеты и для создания `.ps1xml` файла.</span><span class="sxs-lookup"><span data-stu-id="ac406-207">To create the custom view, use the `Get-FormatData` and `Export-FormatData` cmdlets to generate a `.ps1xml` file.</span></span> <span data-ttu-id="ac406-208">Затем измените файл, `.ps1xml` чтобы создать код для пользовательского представления.</span><span class="sxs-lookup"><span data-stu-id="ac406-208">Then, edit your `.ps1xml` file to create the code for your custom view.</span></span> <span data-ttu-id="ac406-209">`.ps1xml`Файл может храниться в любом каталоге, к которому может получить доступ PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac406-209">The `.ps1xml` file can be stored in any directory that PowerShell can access.</span></span> <span data-ttu-id="ac406-210">Например, подкаталог `$HOME` .</span><span class="sxs-lookup"><span data-stu-id="ac406-210">For example, a subdirectory of `$HOME`.</span></span>

<span data-ttu-id="ac406-211">После `.ps1xml` создания файла используйте `Update-FormatData` командлет, чтобы включить представление в текущий сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac406-211">After the `.ps1xml` file is created, use the `Update-FormatData` cmdlet to include the view in the current PowerShell session.</span></span> <span data-ttu-id="ac406-212">Также можно добавить команду Update в профиль PowerShell, если требуется представление, доступное во всех сеансах PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac406-212">Or, add the update command to your PowerShell profile if you need the view available in all PowerShell sessions.</span></span>

<span data-ttu-id="ac406-213">В этом примере пользовательское представление должно использовать формат таблицы, в противном случае — `Format-Table` сбой.</span><span class="sxs-lookup"><span data-stu-id="ac406-213">For this example, the custom view must use the table format, otherwise, `Format-Table` fails.</span></span>

<span data-ttu-id="ac406-214">Используйте `Format-Table` с параметром **View** , чтобы указать имя пользовательского представления, **мигЦивиев** и отформатировать выходные данные таблицы с помощью столбца **CreationTime** .</span><span class="sxs-lookup"><span data-stu-id="ac406-214">Use `Format-Table` with the **View** parameter to specify the custom view's name, **mygciview** , and format the table's output with the **CreationTime** column.</span></span> <span data-ttu-id="ac406-215">Пример выполнения команды см. в разделе [Format-Table](xref:Microsoft.PowerShell.Utility.Format-Table).</span><span class="sxs-lookup"><span data-stu-id="ac406-215">For an example of how the command is run, see [Format-Table](xref:Microsoft.PowerShell.Utility.Format-Table).</span></span>

> [!NOTE]
> <span data-ttu-id="ac406-216">Хотя можно получить XML-код форматирования из исходного кода для создания пользовательского представления, для получения желаемого результата может потребоваться дополнительная разработка.</span><span class="sxs-lookup"><span data-stu-id="ac406-216">Although you can get the formatting XML from the source code to create a custom view, more development might be needed to get the desired result.</span></span>

<span data-ttu-id="ac406-217">В следующей `Get-FormatData` команде есть альтернатива параметру **PowerShellVersion** , чтобы гарантировать возврат всех сведений о локальном форматировании.</span><span class="sxs-lookup"><span data-stu-id="ac406-217">In the following `Get-FormatData` command, there's an alternative for the **PowerShellVersion** parameter to ensure that all local formatting information is returned.</span></span> <span data-ttu-id="ac406-218">Используйте `-PowerShellVersion $PSVersionTable.PSVersion` вместо конкретной версии PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac406-218">Use `-PowerShellVersion $PSVersionTable.PSVersion` rather than a specific PowerShell version.</span></span>

```powershell
Get-FormatData -PowerShellVersion 5.1 -TypeName System.IO.DirectoryInfo |
   Export-FormatData -Path ./Mygciview.Format.ps1xml
Update-FormatData -AppendPath ./Mygciview.Format.ps1xml
```

```xml
<?xml version="1.0" encoding="utf-8"?>
<Configuration>
  <ViewDefinitions>
    <View>
      <Name>mygciview</Name>
      <ViewSelectedBy>
        <TypeName>System.IO.DirectoryInfo</TypeName>
        <TypeName>System.IO.FileInfo</TypeName>
      </ViewSelectedBy>
      <GroupBy>
        <PropertyName>PSParentPath</PropertyName>
      </GroupBy>
      <TableControl>
        <TableHeaders>
          <TableColumnHeader>
            <Label>Mode</Label>
            <Width>7</Width>
            <Alignment>Left</Alignment>
          </TableColumnHeader>
          <TableColumnHeader>
            <Label>LastWriteTime</Label>
            <Width>26</Width>
            <Alignment>Right</Alignment>
          </TableColumnHeader>
          <TableColumnHeader>
            <Label>CreationTime</Label>
            <Width>26</Width>
            <Alignment>Right</Alignment>
          </TableColumnHeader>
          <TableColumnHeader>
            <Label>Length</Label>
            <Width>14</Width>
            <Alignment>Right</Alignment>
          </TableColumnHeader>
          <TableColumnHeader>
            <Label>Name</Label>
            <Alignment>Left</Alignment>
          </TableColumnHeader>
        </TableHeaders>
        <TableRowEntries>
          <TableRowEntry>
            <Wrap />
            <TableColumnItems>
              <TableColumnItem>
                <PropertyName>ModeWithoutHardLink</PropertyName>
              </TableColumnItem>
              <TableColumnItem>
                <PropertyName>LastWriteTime</PropertyName>
              </TableColumnItem>
              <TableColumnItem>
                <PropertyName>CreationTime</PropertyName>
              </TableColumnItem>
              <TableColumnItem>
                <PropertyName>Length</PropertyName>
              </TableColumnItem>
              <TableColumnItem>
                <PropertyName>Name</PropertyName>
              </TableColumnItem>
            </TableColumnItems>
          </TableRowEntry>
        </TableRowEntries>
      </TableControl>
    </View>
  </ViewDefinitions>
</Configuration>
```

## <a name="see-also"></a><span data-ttu-id="ac406-219">См. также статью</span><span class="sxs-lookup"><span data-stu-id="ac406-219">See also</span></span>

[<span data-ttu-id="ac406-220">Export-FormatData</span><span class="sxs-lookup"><span data-stu-id="ac406-220">Export-FormatData</span></span>](xref:Microsoft.PowerShell.Utility.Export-FormatData)

[<span data-ttu-id="ac406-221">Get-FormatData;</span><span class="sxs-lookup"><span data-stu-id="ac406-221">Get-FormatData</span></span>](xref:Microsoft.PowerShell.Utility.Get-FormatData)

[<span data-ttu-id="ac406-222">Get-TraceSource</span><span class="sxs-lookup"><span data-stu-id="ac406-222">Get-TraceSource</span></span>](xref:Microsoft.PowerShell.Utility.Get-TraceSource)

[<span data-ttu-id="ac406-223">Ссылка на схему формата XML</span><span class="sxs-lookup"><span data-stu-id="ac406-223">Format Schema XML Reference</span></span>](/powershell/scripting/developer/format/format-schema-xml-reference)

[<span data-ttu-id="ac406-224">Trace-Command</span><span class="sxs-lookup"><span data-stu-id="ac406-224">Trace-Command</span></span>](xref:Microsoft.PowerShell.Utility.Trace-Command)

[<span data-ttu-id="ac406-225">Update-FormatData</span><span class="sxs-lookup"><span data-stu-id="ac406-225">Update-FormatData</span></span>](xref:Microsoft.PowerShell.Utility.Update-FormatData)

[<span data-ttu-id="ac406-226">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="ac406-226">Writing a PowerShell Formatting File</span></span>](/powershell/scripting/developer/format/writing-a-powershell-formatting-file)
