---
description: '`Format.ps1xml`Файлы в PowerShell определяют отображение объектов по умолчанию в консоли PowerShell. Можно создать собственные файлы, `Format.ps1xml` чтобы изменить отображение объектов или определить отображение по умолчанию для новых типов объектов, создаваемых в PowerShell.'
keywords: powershell,командлет
Locale: en-US
ms.date: 11/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_format.ps1xml?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Format.ps1xml
ms.openlocfilehash: be88007d23ab98b9c2f707b77f9c43578ba9887b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232045"
---
# <a name="about-formatps1xml"></a><span data-ttu-id="65b91-105">Сведения о Format.ps1XML</span><span class="sxs-lookup"><span data-stu-id="65b91-105">About Format.ps1xml</span></span>

## <a name="short-description"></a><span data-ttu-id="65b91-106">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="65b91-106">Short description</span></span>

<span data-ttu-id="65b91-107">`Format.ps1xml`Файлы в PowerShell определяют отображение объектов по умолчанию в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="65b91-107">The `Format.ps1xml` files in PowerShell define the default display of objects in the PowerShell console.</span></span> <span data-ttu-id="65b91-108">Можно создать собственные файлы, `Format.ps1xml` чтобы изменить отображение объектов или определить отображение по умолчанию для новых типов объектов, создаваемых в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="65b91-108">You can create your own `Format.ps1xml` files to change the display of objects or to define default displays for new object types that you create in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="65b91-109">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="65b91-109">Long description</span></span>

<span data-ttu-id="65b91-110">`Format.ps1xml`Файлы в PowerShell определяют отображение объектов по умолчанию в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="65b91-110">The `Format.ps1xml` files in PowerShell define the default display of objects in PowerShell.</span></span> <span data-ttu-id="65b91-111">Можно создать собственные файлы, `Format.ps1xml` чтобы изменить отображение объектов или определить отображение по умолчанию для новых типов объектов, создаваемых в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="65b91-111">You can create your own `Format.ps1xml` files to change the display of objects or to define default displays for new object types that you create in PowerShell.</span></span>

<span data-ttu-id="65b91-112">Когда в PowerShell отображается объект, он использует данные в структурированных файлах форматирования для определения отображения объекта по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="65b91-112">When PowerShell displays an object, it uses the data in structured formatting files to determine the default display of the object.</span></span> <span data-ttu-id="65b91-113">Данные в файлах форматирования определяют, отображается ли объект в таблице или в списке, и определяет, какие свойства отображаются по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="65b91-113">The data in the formatting files determines whether the object is rendered in a table or in a list, and it determines which properties are displayed by default.</span></span>

<span data-ttu-id="65b91-114">Форматирование влияет только на отображение.</span><span class="sxs-lookup"><span data-stu-id="65b91-114">The formatting affects the display only.</span></span> <span data-ttu-id="65b91-115">Он не влияет на то, какие свойства объекта передаются по конвейеру или каким способом они передаются.</span><span class="sxs-lookup"><span data-stu-id="65b91-115">It doesn't affect which object properties are passed down the pipeline or how they're passed.</span></span> <span data-ttu-id="65b91-116">`Format.ps1xml` файлы нельзя использовать для настройки формата выходных данных для хэш-таблиц.</span><span class="sxs-lookup"><span data-stu-id="65b91-116">`Format.ps1xml` files can't be used to customize the output format for hash tables.</span></span>

<span data-ttu-id="65b91-117">PowerShell включает семь файлов форматирования.</span><span class="sxs-lookup"><span data-stu-id="65b91-117">PowerShell includes seven formatting files.</span></span> <span data-ttu-id="65b91-118">Эти файлы находятся в каталоге установки ( `$PSHOME` ).</span><span class="sxs-lookup"><span data-stu-id="65b91-118">These files are located in the installation directory (`$PSHOME`).</span></span> <span data-ttu-id="65b91-119">Каждый файл определяет отображение группы объектов Microsoft .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="65b91-119">Each file defines the display of a group of Microsoft .NET Framework objects:</span></span>

1. `Certificate.Format.ps1xml`

   <span data-ttu-id="65b91-120">Объекты в хранилище сертификатов, такие как сертификаты X. 509 и хранилища сертификатов.</span><span class="sxs-lookup"><span data-stu-id="65b91-120">Objects in the Certificate store, such as X.509 certificates and certificate stores.</span></span>

1. `DotNetTypes.Format.ps1xml`

   <span data-ttu-id="65b91-121">Другие типы .NET Framework, например объекты CultureInfo, FileVersionInfo и EventLogEntry.</span><span class="sxs-lookup"><span data-stu-id="65b91-121">Other .NET Framework types, such as CultureInfo, FileVersionInfo, and EventLogEntry objects.</span></span>

1. `FileSystem.Format.ps1xml`

   <span data-ttu-id="65b91-122">Объекты файловой системы, такие как файлы и каталоги.</span><span class="sxs-lookup"><span data-stu-id="65b91-122">File system objects, such as files and directories.</span></span>

1. `Help.Format.ps1xml`

   <span data-ttu-id="65b91-123">Представления справки, такие как подробные и полные представления, параметры и примеры.</span><span class="sxs-lookup"><span data-stu-id="65b91-123">Help views, such as detailed and full views, parameters, and examples.</span></span>

1. `PowerShellCore.Format.ps1xml`

   <span data-ttu-id="65b91-124">Объекты, создаваемые командлетами PowerShell Core, например `Get-Member` и `Get-History` .</span><span class="sxs-lookup"><span data-stu-id="65b91-124">Objects generated by PowerShell core cmdlets, such as `Get-Member` and `Get-History`.</span></span>

1. `PowerShellTrace.Format.ps1xml`

   <span data-ttu-id="65b91-125">Объекты трассировки, такие как созданные `Trace-Command` командлетом.</span><span class="sxs-lookup"><span data-stu-id="65b91-125">Trace objects, such as those generated by the `Trace-Command` cmdlet.</span></span>

1. `Registry.Format.ps1xml`

   <span data-ttu-id="65b91-126">Объекты реестра, такие как ключи и записи.</span><span class="sxs-lookup"><span data-stu-id="65b91-126">Registry objects, such as keys and entries.</span></span>

<span data-ttu-id="65b91-127">Файл форматирования может определять четыре различных представления каждого объекта:</span><span class="sxs-lookup"><span data-stu-id="65b91-127">A formatting file can define four different views of each object:</span></span>

- <span data-ttu-id="65b91-128">Таблица</span><span class="sxs-lookup"><span data-stu-id="65b91-128">Table</span></span>
- <span data-ttu-id="65b91-129">Список</span><span class="sxs-lookup"><span data-stu-id="65b91-129">List</span></span>
- <span data-ttu-id="65b91-130">Широкий</span><span class="sxs-lookup"><span data-stu-id="65b91-130">Wide</span></span>
- <span data-ttu-id="65b91-131">Другой</span><span class="sxs-lookup"><span data-stu-id="65b91-131">Custom</span></span>

<span data-ttu-id="65b91-132">Например, когда выходные данные `Get-ChildItem` команды передаются в `Format-List` команду, `Format-List` использует представление в `FileSystem.Format.ps1xml` файле для определения способа отображения объектов файла и папки в виде списка.</span><span class="sxs-lookup"><span data-stu-id="65b91-132">For example, when the output of a `Get-ChildItem` command is piped to a `Format-List` command, `Format-List` uses the view in the `FileSystem.Format.ps1xml` file to determine how to display the file and folder objects as a list.</span></span>

<span data-ttu-id="65b91-133">Если файл форматирования содержит более одного представления объекта, PowerShell применяет первое найденное представление.</span><span class="sxs-lookup"><span data-stu-id="65b91-133">When a formatting file includes more than one view of an object, PowerShell applies the first view that it finds.</span></span>

<span data-ttu-id="65b91-134">В `Format.ps1xml` файле представление определяется набором XML-тегов, описывающих имя представления, тип объекта, к которому он может быть применен, заголовки столбцов и свойства, отображаемые в тексте представления.</span><span class="sxs-lookup"><span data-stu-id="65b91-134">In a `Format.ps1xml` file, a view is defined by a set of XML tags that describe the name of the view, the type of object to which it can be applied, the column headers, and the properties that are displayed in the body of the view.</span></span> <span data-ttu-id="65b91-135">Формат в `Format.ps1xml` файлах применяется непосредственно перед тем, как данные представлены пользователю.</span><span class="sxs-lookup"><span data-stu-id="65b91-135">The format in `Format.ps1xml` files is applied just before the data is presented to the user.</span></span>

## <a name="creating-new-formatps1xml-files"></a><span data-ttu-id="65b91-136">Создание новых Format.ps1XML-файлов</span><span class="sxs-lookup"><span data-stu-id="65b91-136">Creating new Format.ps1xml files</span></span>

<span data-ttu-id="65b91-137">`.ps1xml`Файлы, устанавливаемые с помощью PowerShell, имеют цифровую подпись, чтобы предотвратить незаконное изменение, так как форматирование может включать блоки сценариев.</span><span class="sxs-lookup"><span data-stu-id="65b91-137">The `.ps1xml` files that are installed with PowerShell are digitally signed to prevent tampering because the formatting can include script blocks.</span></span> <span data-ttu-id="65b91-138">Чтобы изменить формат отображения существующего представления объектов или добавить представления для новых объектов, создайте собственные `Format.ps1xml` файлы, а затем добавьте их в сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="65b91-138">To change the display format of an existing object view, or to add views for new objects, create your own `Format.ps1xml` files, and then add them to your PowerShell session.</span></span>

<span data-ttu-id="65b91-139">Чтобы создать новый файл, скопируйте существующий `Format.ps1xml` файл.</span><span class="sxs-lookup"><span data-stu-id="65b91-139">To create a new file, copy an existing `Format.ps1xml` file.</span></span> <span data-ttu-id="65b91-140">Новый файл может иметь любое имя, но он должен иметь `.ps1xml` расширение имени файла.</span><span class="sxs-lookup"><span data-stu-id="65b91-140">The new file can have any name, but it must have a `.ps1xml` file name extension.</span></span> <span data-ttu-id="65b91-141">Новый файл можно поместить в любой каталог, доступный для PowerShell, но при этом полезно поместить файлы в каталог установки PowerShell ( `$PSHOME` ) или в подкаталог каталога установки.</span><span class="sxs-lookup"><span data-stu-id="65b91-141">You can place the new file in any directory that is accessible to PowerShell, but it's useful to place the files in the PowerShell installation directory (`$PSHOME`) or in a subdirectory of the installation directory.</span></span>

<span data-ttu-id="65b91-142">Чтобы изменить форматирование текущего представления, найдите представление в файле форматирования, а затем используйте теги для изменения представления.</span><span class="sxs-lookup"><span data-stu-id="65b91-142">To change the formatting of a current view, locate the view in the formatting file, and then use the tags to change the view.</span></span> <span data-ttu-id="65b91-143">Чтобы создать представление для нового типа объекта, создайте новое представление или используйте существующее представление в качестве модели.</span><span class="sxs-lookup"><span data-stu-id="65b91-143">To create a view for a new object type, create a new view, or use an existing view as a model.</span></span> <span data-ttu-id="65b91-144">Теги описаны в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="65b91-144">The tags are described in the next section.</span></span> <span data-ttu-id="65b91-145">Затем можно удалить все остальные представления в файле, чтобы изменения были очевидны для любого, который просматривает файл.</span><span class="sxs-lookup"><span data-stu-id="65b91-145">You can then delete all the other views in the file so that the changes are obvious to anyone examining the file.</span></span>

<span data-ttu-id="65b91-146">После сохранения изменений используйте `Update-FormatData` командлет, чтобы добавить новый файл в сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="65b91-146">After you save the changes, use the `Update-FormatData` cmdlet to add the new file to your PowerShell session.</span></span> <span data-ttu-id="65b91-147">Если необходимо, чтобы представление было иметь приоритет над представлением, определенным во встроенных файлах, используйте параметр **препендпас** .</span><span class="sxs-lookup"><span data-stu-id="65b91-147">If you want your view to take precedence over a view defined in the built-in files, use the **PrependPath** parameter.</span></span>
<span data-ttu-id="65b91-148">`Update-FormatData` влияет только на текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="65b91-148">`Update-FormatData` affects only the current session.</span></span> <span data-ttu-id="65b91-149">Чтобы внести изменения во все будущие сеансы, добавьте `Update-FormatData` команду в профиль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="65b91-149">To make the change to all future sessions, add the `Update-FormatData` command to your PowerShell profile.</span></span>

### <a name="example-adding-calendar-data-to-culture-objects"></a><span data-ttu-id="65b91-150">Пример. Добавление данных календаря в объекты языка и региональных параметров</span><span class="sxs-lookup"><span data-stu-id="65b91-150">Example: Adding calendar data to culture objects</span></span>

<span data-ttu-id="65b91-151">В этом примере показано, как изменить форматирование объектов языка и региональных параметров **System. Globalization. CultureInfo** , созданных `Get-Culture` командлетом в текущем сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="65b91-151">This example shows how to change the formatting of the culture objects **System.Globalization.CultureInfo** generated by the `Get-Culture` cmdlet in the current PowerShell session.</span></span> <span data-ttu-id="65b91-152">Команды в примере добавляют свойство **Calendar** в представление таблицы по умолчанию, отображающее объекты языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="65b91-152">The commands in the example add the **Calendar** property to the default table view display of culture objects.</span></span>

<span data-ttu-id="65b91-153">Первым шагом является поиск `Format.ps1xml` файла, содержащего текущее представление объектов языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="65b91-153">The first step is to find the `Format.ps1xml` file that contains the current view of the culture objects.</span></span> <span data-ttu-id="65b91-154">Следующая `Select-String` команда находит файл:</span><span class="sxs-lookup"><span data-stu-id="65b91-154">The following `Select-String` command finds the file:</span></span>

```powershell
$Parms = @{
  Path = "$PSHOME\*Format.ps1xml"
  Pattern = "System.Globalization.CultureInfo"
}

Select-String @Parms
```

```Output
C:\Windows\System32\WindowsPowerShell\v1.0\DotNetTypes.format.ps1xml:113:
     <Name>System.Globalization.CultureInfo</Name>
C:\Windows\System32\WindowsPowerShell\v1.0\DotNetTypes.format.ps1xml:115:
<TypeName>System.Globalization.CultureInfo</TypeName>
```

<span data-ttu-id="65b91-155">Эта команда показывает, что определение находится в `DotNetTypes.Format.ps1xml` файле.</span><span class="sxs-lookup"><span data-stu-id="65b91-155">This command reveals that the definition is in the `DotNetTypes.Format.ps1xml` file.</span></span>

<span data-ttu-id="65b91-156">Следующая команда копирует содержимое файла в новый файл, `MyDotNetTypes.Format.ps1xml` .</span><span class="sxs-lookup"><span data-stu-id="65b91-156">The next command copies the file contents to a new file, `MyDotNetTypes.Format.ps1xml`.</span></span>

```powershell
Copy-Item $PSHome\DotNetTypes.format.ps1xml MyDotNetTypes.Format.ps1xml
```

<span data-ttu-id="65b91-157">Откройте `MyDotNetTypes.Format.ps1xml` файл в любом XML-или текстовом редакторе, например Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="65b91-157">Open the `MyDotNetTypes.Format.ps1xml` file in any XML or text editor, such as Visual Studio Code.</span></span> <span data-ttu-id="65b91-158">Найдите раздел объект **System. Globalization. CultureInfo** .</span><span class="sxs-lookup"><span data-stu-id="65b91-158">Find the **System.Globalization.CultureInfo** object section.</span></span> <span data-ttu-id="65b91-159">Следующий XML-код определяет представления объекта **CultureInfo** .</span><span class="sxs-lookup"><span data-stu-id="65b91-159">The following XML defines the views of the **CultureInfo** object.</span></span> <span data-ttu-id="65b91-160">Объект имеет только представление **таблеконтрол** .</span><span class="sxs-lookup"><span data-stu-id="65b91-160">The object has only a **TableControl** view.</span></span>

```xml
<View>
  <Name>System.Globalization.CultureInfo</Name>
  <ViewSelectedBy>
    <TypeName>Deserialized.System.Globalization.CultureInfo</TypeName>
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
```

<span data-ttu-id="65b91-161">Удалите оставшуюся часть файла, за исключением открывающих `<?xml>` тегов, и, а `<Configuration>` `<ViewDefinitions>` также закрывающих `<ViewDefinitions>` `<Configuration>` тегов и.</span><span class="sxs-lookup"><span data-stu-id="65b91-161">Delete the remainder of the file, except for the opening `<?xml>`, `<Configuration>`, and `<ViewDefinitions>` tags and the closing `<ViewDefinitions>` and `<Configuration>` tags.</span></span> <span data-ttu-id="65b91-162">Если имеется цифровая подпись, удалите ее из пользовательского `Format.ps1xml` файла.</span><span class="sxs-lookup"><span data-stu-id="65b91-162">If there is a digital signature, delete it from your custom `Format.ps1xml`file.</span></span>

<span data-ttu-id="65b91-163">`MyDotNetTypes.Format.ps1xml`Теперь файл должен выглядеть, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="65b91-163">The `MyDotNetTypes.Format.ps1xml` file should now look like the following sample:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<Configuration>
<ViewDefinitions>
<View>
  <Name>System.Globalization.CultureInfo</Name>
  <ViewSelectedBy>
    <TypeName>Deserialized.System.Globalization.CultureInfo</TypeName>
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
      <TableColumnHeader/>
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

<span data-ttu-id="65b91-164">Создайте новый столбец для свойства **Calendar** , добавив новый набор `<TableColumnHeader>` тегов.</span><span class="sxs-lookup"><span data-stu-id="65b91-164">Create a new column for the **Calendar** property by adding a new set of `<TableColumnHeader>` tags.</span></span> <span data-ttu-id="65b91-165">Значение свойства **Calendar** может быть длинным, поэтому укажите в качестве значения 45 символов `<Width>` .</span><span class="sxs-lookup"><span data-stu-id="65b91-165">The value of the **Calendar** property can be long, so specify a value of 45 characters as the `<Width>`.</span></span>

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

<span data-ttu-id="65b91-166">Добавьте новый элемент столбца для **Calendar** в строки таблицы с помощью `<TableColumnItem>` `<PropertyName` тегов и.</span><span class="sxs-lookup"><span data-stu-id="65b91-166">Add a new column item for **Calendar** in the table rows using the `<TableColumnItem>` and `<PropertyName` tags:</span></span>

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

<span data-ttu-id="65b91-167">Сохраните файл и закройте его.</span><span class="sxs-lookup"><span data-stu-id="65b91-167">Save and close the file.</span></span> <span data-ttu-id="65b91-168">Используйте `Update-FormatData` , чтобы добавить новый файл форматирования в текущий сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="65b91-168">Use `Update-FormatData` to add the new format file to the current PowerShell session.</span></span>

<span data-ttu-id="65b91-169">В этом примере используется параметр **препендпас** для размещения нового файла в порядке приоритета, отличном от исходного файла.</span><span class="sxs-lookup"><span data-stu-id="65b91-169">This example uses the **PrependPath** parameter to place the new file in a higher precedence order than the original file.</span></span> <span data-ttu-id="65b91-170">Дополнительные сведения см. в разделе [Update-FormatData](xref:Microsoft.PowerShell.Utility.Update-FormatData).</span><span class="sxs-lookup"><span data-stu-id="65b91-170">For more information, see [Update-FormatData](xref:Microsoft.PowerShell.Utility.Update-FormatData).</span></span>

```powershell
Update-FormatData -PrependPath $PSHOME\MyDotNetTypes.Format.ps1xml
```

<span data-ttu-id="65b91-171">Чтобы проверить изменение, введите `Get-Culture` и проверьте выходные данные, включающие в себя свойство **Calendar** .</span><span class="sxs-lookup"><span data-stu-id="65b91-171">To test the change, type `Get-Culture` and review the output that includes the **Calendar** property.</span></span>

```powershell
Get-Culture
```

```Output
LCID Name  Calendar                               DisplayName
---- ----  --------                               -----------
1033 en-US System.Globalization.GregorianCalendar English (United States)
```

## <a name="the-xml-in-formatps1xml-files"></a><span data-ttu-id="65b91-172">XML-файлы в Format.ps1XML-файлах</span><span class="sxs-lookup"><span data-stu-id="65b91-172">The XML in Format.ps1xml files</span></span>

<span data-ttu-id="65b91-173">Полное определение схемы можно найти в файле [format. xsd](https://github.com/PowerShell/PowerShell/blob/master/src/Schemas/Format.xsd) в репозитории исходного кода PowerShell на сайте GitHub.</span><span class="sxs-lookup"><span data-stu-id="65b91-173">The full schema definition can be found in [Format.xsd](https://github.com/PowerShell/PowerShell/blob/master/src/Schemas/Format.xsd) in the PowerShell source code repository on GitHub.</span></span>

<span data-ttu-id="65b91-174">Раздел **виевдефинитионс** каждого `Format.ps1xml` файла содержит `<View>` теги, определяющие каждое представление.</span><span class="sxs-lookup"><span data-stu-id="65b91-174">The **ViewDefinitions** section of each `Format.ps1xml` file contains the `<View>` tags that define each view.</span></span> <span data-ttu-id="65b91-175">Типичный `<View>` тег содержит следующие Теги:</span><span class="sxs-lookup"><span data-stu-id="65b91-175">A typical `<View>` tag includes the following tags:</span></span>

- <span data-ttu-id="65b91-176">`<Name>` Определяет имя представления.</span><span class="sxs-lookup"><span data-stu-id="65b91-176">`<Name>` identifies the name of the view.</span></span>
- <span data-ttu-id="65b91-177">`<ViewSelectedBy>` Указывает тип или типы объектов, к которым применяется представление.</span><span class="sxs-lookup"><span data-stu-id="65b91-177">`<ViewSelectedBy>` specifies the object type or types to which the view applies.</span></span>
- <span data-ttu-id="65b91-178">`<GroupBy>` Указывает, как элементы представления будут объединены в группы.</span><span class="sxs-lookup"><span data-stu-id="65b91-178">`<GroupBy>` specifies how items in the view will be combined in groups.</span></span>
- <span data-ttu-id="65b91-179">`<TableControl>`, `<ListControl>` , `<WideControl>` и `<CustomControl>` содержат теги, которые определяют, как будет отображаться каждый элемент.</span><span class="sxs-lookup"><span data-stu-id="65b91-179">`<TableControl>`, `<ListControl>`, `<WideControl>`, and `<CustomControl>` contain the tags that specify how each item will be displayed.</span></span>

### <a name="viewselectedby-tag"></a><span data-ttu-id="65b91-180">Тег Виевселектедби</span><span class="sxs-lookup"><span data-stu-id="65b91-180">ViewSelectedBy tag</span></span>

<span data-ttu-id="65b91-181">`<ViewSelectedBy>`Тег может содержать `<TypeName>` тег для каждого типа объектов, к которому применяется представление.</span><span class="sxs-lookup"><span data-stu-id="65b91-181">The `<ViewSelectedBy>` tag can contain a `<TypeName>` tag for each object type to which the view applies.</span></span> <span data-ttu-id="65b91-182">Или может содержать `<SelectionSetName>` тег, который ссылается на набор выбора, определенный в других местах с помощью `<SelectionSet>` тега.</span><span class="sxs-lookup"><span data-stu-id="65b91-182">Or, it can contain a `<SelectionSetName>` tag that references a selection set that is defined elsewhere by using a `<SelectionSet>` tag.</span></span>

### <a name="groupby-tag"></a><span data-ttu-id="65b91-183">Тег GroupBy</span><span class="sxs-lookup"><span data-stu-id="65b91-183">GroupBy tag</span></span>

<span data-ttu-id="65b91-184">`<GroupBy>`Тег содержит `<PropertyName>` тег, указывающий свойство объекта, по которому группируются элементы.</span><span class="sxs-lookup"><span data-stu-id="65b91-184">The `<GroupBy>` tag contains a `<PropertyName>` tag that specifies the object property by which items are to be grouped.</span></span> <span data-ttu-id="65b91-185">Он также содержит `<Label>` тег, указывающий строку, которая будет использоваться в качестве метки для каждой группы `<CustomControlName>` , или тег, который ссылается на пользовательский элемент управления, определенный в любом расположении с помощью `<Control>` тега.</span><span class="sxs-lookup"><span data-stu-id="65b91-185">It also contains either a `<Label>` tag that specifies a string to be used as a label for each group or a `<CustomControlName>` tag that references a custom control defined elsewhere using a `<Control>` tag.</span></span> <span data-ttu-id="65b91-186">`<Control>`Тег содержит `<Name>` тег и `<CustomControl>` тег.</span><span class="sxs-lookup"><span data-stu-id="65b91-186">The `<Control>` tag contains a `<Name>` tag and a `<CustomControl>` tag.</span></span>

### <a name="tablecontroltag"></a><span data-ttu-id="65b91-187">таблеконтролтаг</span><span class="sxs-lookup"><span data-stu-id="65b91-187">TableControlTag</span></span>

<span data-ttu-id="65b91-188">`<TableControl>`Тег обычно содержит `<TableHeaders>` теги и `<TableRowEntries>` , определяющие форматирование головок и строк таблицы.</span><span class="sxs-lookup"><span data-stu-id="65b91-188">The `<TableControl>` tag typically contains `<TableHeaders>` and `<TableRowEntries>` tags that define the formatting for the table's heads and rows.</span></span> <span data-ttu-id="65b91-189">`<TableHeaders>`Тег обычно содержит `<TableColumnHeader>` теги, которые содержат `<Label>` теги, `<Width>` и `<Alignment>` .</span><span class="sxs-lookup"><span data-stu-id="65b91-189">The `<TableHeaders>` tag typically contains `<TableColumnHeader>` tags that contain `<Label>`, `<Width>`, and `<Alignment>` tags.</span></span> <span data-ttu-id="65b91-190">`<TableRowEntries>`Тег содержит `<TableRowEntry>` теги для каждой строки в таблице.</span><span class="sxs-lookup"><span data-stu-id="65b91-190">The `<TableRowEntries>` tag contains `<TableRowEntry>` tags for each row in the table.</span></span> <span data-ttu-id="65b91-191">`<TableRowEntry>`Тег содержит `<TableColumnItems>` тег, который содержит `<TableColumnItem>` тег для каждого столбца в строке.</span><span class="sxs-lookup"><span data-stu-id="65b91-191">The `<TableRowEntry>` tag contains a `<TableColumnItems>` tag that contains a `<TableColumnItem>` tag for each column in the row.</span></span> <span data-ttu-id="65b91-192">Как правило, `<TableColumnItem>` тег содержит либо `<PropertyName>` тег, определяющий свойство объекта, которое должно отображаться в определенном расположении, либо `<ScriptBlock>` тег, содержащий код скрипта, который вычисляет результат, отображаемый в расположении.</span><span class="sxs-lookup"><span data-stu-id="65b91-192">Typically, the `<TableColumnItem>` tag contains either a `<PropertyName>` tag that identifies the object property to be displayed in the defined location, or a `<ScriptBlock>` tag that contains script code that calculates a result that is to be displayed in the location.</span></span>

> [!NOTE]
> <span data-ttu-id="65b91-193">Блоки сценариев также можно использовать в других местах, где вычисленные результаты могут быть полезными.</span><span class="sxs-lookup"><span data-stu-id="65b91-193">Script blocks can also be used elsewhere in locations where calculated results can be useful.</span></span>

<span data-ttu-id="65b91-194">`<TableColumnItem>`Тег также может содержать `<FormatString>` тег, указывающий, как будут отображаться свойство или вычисляемые результаты.</span><span class="sxs-lookup"><span data-stu-id="65b91-194">The `<TableColumnItem>` tag can also contain a `<FormatString>` tag that specifies how the property or the calculated results will be displayed.</span></span>

### <a name="listcontrol-tag"></a><span data-ttu-id="65b91-195">Тег ListControl</span><span class="sxs-lookup"><span data-stu-id="65b91-195">ListControl tag</span></span>

<span data-ttu-id="65b91-196">`<ListControl>`Тег обычно содержит `<ListEntries>` тег.</span><span class="sxs-lookup"><span data-stu-id="65b91-196">The `<ListControl>` tag typically contains a `<ListEntries>` tag.</span></span> <span data-ttu-id="65b91-197">`<ListEntries>`Тег содержит `<ListEntry>` тег.</span><span class="sxs-lookup"><span data-stu-id="65b91-197">The `<ListEntries>` tag contains a `<ListEntry>` tag.</span></span> <span data-ttu-id="65b91-198">`<ListEntry>`Тег содержит `<ListItems>` тег.</span><span class="sxs-lookup"><span data-stu-id="65b91-198">The `<ListEntry>` tag contains a `<ListItems>` tag.</span></span> <span data-ttu-id="65b91-199">`<ListItems>`Тег содержит `<ListItem>` теги, которые содержат `<PropertyName>` теги.</span><span class="sxs-lookup"><span data-stu-id="65b91-199">The `<ListItems>` tag contains `<ListItem>` tags, which contain `<PropertyName>` tags.</span></span> <span data-ttu-id="65b91-200">`<PropertyName>`Теги указывают свойство объекта, которое должно отображаться в указанном месте списка.</span><span class="sxs-lookup"><span data-stu-id="65b91-200">The `<PropertyName>` tags specify the object property to be displayed at the specified location in the list.</span></span> <span data-ttu-id="65b91-201">Если выбор представления определен с помощью набора элементов, `<ListControl>` `<ListEntry>` теги и также могут содержать `<EntrySelectedBy>` тег, содержащий один или несколько `<TypeName>` тегов.</span><span class="sxs-lookup"><span data-stu-id="65b91-201">If the view selection is defined using a selection set, the `<ListControl>` and `<ListEntry>` tags can also contain an `<EntrySelectedBy>` tag that contains one or more `<TypeName>` tags.</span></span> <span data-ttu-id="65b91-202">Эти `<TypeName>` теги указывают тип объекта, который должен `<ListControl>` отображаться в теге.</span><span class="sxs-lookup"><span data-stu-id="65b91-202">These `<TypeName>` tags specify the object type that the `<ListControl>` tag is intended to display.</span></span>

### <a name="widecontrol-tag"></a><span data-ttu-id="65b91-203">Тег Видеконтрол</span><span class="sxs-lookup"><span data-stu-id="65b91-203">WideControl tag</span></span>

<span data-ttu-id="65b91-204">`<WideControl>`Тег обычно содержит `<WideEntries>` тег.</span><span class="sxs-lookup"><span data-stu-id="65b91-204">The `<WideControl>` tag typically contains a `<WideEntries>` tag.</span></span> <span data-ttu-id="65b91-205">`<WideEntries>`Тег содержит один или несколько `<WideEntry>` тегов.</span><span class="sxs-lookup"><span data-stu-id="65b91-205">The `<WideEntries>` tag contains one or more `<WideEntry>` tags.</span></span> <span data-ttu-id="65b91-206">`<WideEntry>`Тег обычно содержит `<PropertyName>` тег, указывающий свойство, которое должно отображаться в указанном месте представления.</span><span class="sxs-lookup"><span data-stu-id="65b91-206">A `<WideEntry>` tag typically contains a `<PropertyName>` tag that specifies the property to be displayed at the specified location in the view.</span></span> <span data-ttu-id="65b91-207">`<PropertyName>`Тег может содержать `<FormatString>` тег, указывающий, как должно отображаться свойство.</span><span class="sxs-lookup"><span data-stu-id="65b91-207">The `<PropertyName>` tag can contain a `<FormatString>` tag that specifies how the property is to be displayed.</span></span>

### <a name="customcontrol-tag"></a><span data-ttu-id="65b91-208">Тег ошибка customcontrol</span><span class="sxs-lookup"><span data-stu-id="65b91-208">CustomControl tag</span></span>

<span data-ttu-id="65b91-209">`<CustomControl>`Тег позволяет использовать блок скрипта для определения формата.</span><span class="sxs-lookup"><span data-stu-id="65b91-209">The `<CustomControl>` tag lets you use a script block to define a format.</span></span> <span data-ttu-id="65b91-210">`<CustomControl>`Тег обычно содержит `<CustomEntries>` тег, который содержит несколько `<CustomEntry>` тегов.</span><span class="sxs-lookup"><span data-stu-id="65b91-210">A `<CustomControl>` tag typically contains a `<CustomEntries>` tag that contains multiple `<CustomEntry>` tags.</span></span> <span data-ttu-id="65b91-211">Каждый `<CustomEntry>` тег содержит `<CustomItem>` тег, который может содержать различные теги, которые задают содержимое и форматирование указанного расположения в представлении, включая `<Text>` `<Indentation>` теги,, `<ExpressionBinding>` и `<NewLine>` .</span><span class="sxs-lookup"><span data-stu-id="65b91-211">Each `<CustomEntry>` tag contains a `<CustomItem>` tag that can contain a variety of tags that specify contents and formatting of the specified location in the view, including `<Text>`, `<Indentation>`, `<ExpressionBinding>`, and `<NewLine>` tags.</span></span>

## <a name="default-displays-in-typesps1xml"></a><span data-ttu-id="65b91-212">Отображение по умолчанию в Types.ps1XML</span><span class="sxs-lookup"><span data-stu-id="65b91-212">Default displays in Types.ps1xml</span></span>

<span data-ttu-id="65b91-213">По умолчанию отображаются некоторые базовые типы объектов, определенные в `Types.ps1xml` файле в `$PSHOME` каталоге.</span><span class="sxs-lookup"><span data-stu-id="65b91-213">The default displays of some basic object types are defined in the `Types.ps1xml` file in the `$PSHOME` directory.</span></span> <span data-ttu-id="65b91-214">Узлы имеют имя **псстандардмемберс** , а подузлы используют один из следующих тегов:</span><span class="sxs-lookup"><span data-stu-id="65b91-214">The nodes are named **PsStandardMembers** , and the subnodes use one of the following tags:</span></span>

- `<DefaultDisplayProperty>`
- `<DefaultDisplayPropertySet>`
- `<DefaultKeyPropertySet>`

<span data-ttu-id="65b91-215">Дополнительные сведения см. в разделе [about_Types.ps1XML](about_Types.ps1xml.md).</span><span class="sxs-lookup"><span data-stu-id="65b91-215">For more information, see [about_Types.ps1xml](about_Types.ps1xml.md).</span></span>

## <a name="tracing-formatps1xml-file-use"></a><span data-ttu-id="65b91-216">Использование трассировки Format.ps1XML-файла</span><span class="sxs-lookup"><span data-stu-id="65b91-216">Tracing Format.ps1xml file use</span></span>

<span data-ttu-id="65b91-217">Чтобы обнаружить ошибки при загрузке или применении `Format.ps1xml` файлов, используйте `Trace-Command` командлет с любым из следующих компонентов формата в качестве значения параметра **Name** :</span><span class="sxs-lookup"><span data-stu-id="65b91-217">To detect errors in the loading or application of `Format.ps1xml` files, use the `Trace-Command` cmdlet with any of the following format components as the value of the **Name** parameter:</span></span>

- <span data-ttu-id="65b91-218">форматфилелоадинг</span><span class="sxs-lookup"><span data-stu-id="65b91-218">FormatFileLoading</span></span>
- <span data-ttu-id="65b91-219">форматвиевбиндинг</span><span class="sxs-lookup"><span data-stu-id="65b91-219">FormatViewBinding</span></span>

<span data-ttu-id="65b91-220">Дополнительные сведения см. в разделе [Trace-Command](xref:Microsoft.PowerShell.Utility.Trace-Command) и [Get-TraceSource](xref:Microsoft.PowerShell.Utility.Get-TraceSource).</span><span class="sxs-lookup"><span data-stu-id="65b91-220">For more information, see [Trace-Command](xref:Microsoft.PowerShell.Utility.Trace-Command) and [Get-TraceSource](xref:Microsoft.PowerShell.Utility.Get-TraceSource).</span></span>

## <a name="signing-a-formatps1xml-file"></a><span data-ttu-id="65b91-221">Подписывание Format.ps1XML-файла</span><span class="sxs-lookup"><span data-stu-id="65b91-221">Signing a Format.ps1xml file</span></span>

<span data-ttu-id="65b91-222">Для защиты пользователей `Format.ps1xml` файла подпишите его с помощью цифровой подписи.</span><span class="sxs-lookup"><span data-stu-id="65b91-222">To protect the users of your `Format.ps1xml` file, sign the file using a digital signature.</span></span> <span data-ttu-id="65b91-223">Дополнительные сведения см. в разделе [about_Signing](about_Signing.md).</span><span class="sxs-lookup"><span data-stu-id="65b91-223">For more information, see [about_Signing](about_Signing.md).</span></span>

## <a name="sample-xml-for-a-format-table-custom-view"></a><span data-ttu-id="65b91-224">Образец XML-кода для Format-Table пользовательского представления</span><span class="sxs-lookup"><span data-stu-id="65b91-224">Sample XML for a Format-Table custom view</span></span>

<span data-ttu-id="65b91-225">В следующем примере создается `Format-Table` пользовательское представление для объектов **System. IO. DirectoryInfo** и **System. IO. FileInfo** , созданных `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="65b91-225">The following sample creates a `Format-Table` custom view for the **System.IO.DirectoryInfo** and **System.IO.FileInfo** objects created by `Get-ChildItem`.</span></span> <span data-ttu-id="65b91-226">Пользовательское представление называется **мигЦивиев** и добавляет столбец **CreationTime** в таблицу.</span><span class="sxs-lookup"><span data-stu-id="65b91-226">The custom view is named **mygciview** and adds the **CreationTime** column to the table.</span></span>

<span data-ttu-id="65b91-227">Пользовательское представление создается из измененной версии `FileSystem.Format.ps1xml` файла, хранящегося в в `$PSHOME` PowerShell 5,1.</span><span class="sxs-lookup"><span data-stu-id="65b91-227">The custom view is created from an edited version of the `FileSystem.Format.ps1xml` file that's stored in `$PSHOME` on PowerShell 5.1.</span></span>

<span data-ttu-id="65b91-228">После сохранения пользовательского `.ps1xml` файла используйте `Update-FormatData` для включения представления в сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="65b91-228">After your custom `.ps1xml` file is saved, use `Update-FormatData` to include the view in a PowerShell session.</span></span> <span data-ttu-id="65b91-229">В этом примере пользовательское представление должно использовать формат таблицы, в противном случае — `Format-Table` сбой.</span><span class="sxs-lookup"><span data-stu-id="65b91-229">For this example, the custom view must use the table format, otherwise, `Format-Table` fails.</span></span>

<span data-ttu-id="65b91-230">Используйте `Format-Table` с параметром **View** , чтобы указать имя пользовательского представления и отформатировать выходные данные таблицы.</span><span class="sxs-lookup"><span data-stu-id="65b91-230">Use `Format-Table` with the **View** parameter to specify the custom view's name and format the table's output.</span></span> <span data-ttu-id="65b91-231">Пример выполнения команды см. в разделе [Format-Table](xref:Microsoft.PowerShell.Utility.Format-Table).</span><span class="sxs-lookup"><span data-stu-id="65b91-231">For an example of how the command is run, see [Format-Table](xref:Microsoft.PowerShell.Utility.Format-Table).</span></span>

```powershell
$Parms = @{
  Path = "$PSHOME\*Format.ps1xml"
  Pattern = "System.IO.DirectoryInfo"
}
Select-String @Parms
Copy-Item $PSHome\FileSystem.format.ps1xml .\MyFileSystem.Format.ps1xml
Update-FormatData -PrependPath $PSHOME\Format\MyFileSystem.Format.ps1xml
```

> [!NOTE]
> <span data-ttu-id="65b91-232">Чтобы вписать образец XML в ограничения по ширине строк, необходимо сжать некоторые отступы и использовать разрывы строк в коде.</span><span class="sxs-lookup"><span data-stu-id="65b91-232">To fit the XML sample within line width limitations, it was necessary to compress some indentation and use line breaks within the code.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<Configuration>
    <SelectionSets>
        <SelectionSet>
            <Name>FileSystemTypes</Name>
            <Types>
                <TypeName>System.IO.DirectoryInfo</TypeName>
                <TypeName>System.IO.FileInfo</TypeName>
            </Types>
        </SelectionSet>
    </SelectionSets>
<Controls>
<Control>
<Name>FileSystemTypes-GroupingFormat</Name>
<CustomControl>
 <CustomEntries>
  <CustomEntry>
    <CustomItem>
    <Frame>
    <LeftIndent>4</LeftIndent>
    <CustomItem>
    <Text AssemblyName="System.Management.Automation"
    BaseName="FileSystemProviderStrings"
    ResourceId="DirectoryDisplayGrouping"/>
    <ExpressionBinding>
     <ScriptBlock>
      $_.PSParentPath.Replace("Microsoft.PowerShell.Core\FileSystem::", "")
     </ScriptBlock>
    </ExpressionBinding>
    <NewLine/>
    </CustomItem>
    </Frame>
    </CustomItem>
    </CustomEntry>
 </CustomEntries>
</CustomControl>
</Control>
</Controls>
<ViewDefinitions>
    <View>
    <Name>mygciview</Name>
    <ViewSelectedBy>
        <SelectionSetName>FileSystemTypes</SelectionSetName>
    </ViewSelectedBy>
    <GroupBy>
      <PropertyName>PSParentPath</PropertyName>
      <CustomControlName>FileSystemTypes-GroupingFormat</CustomControlName>
    </GroupBy>
        <TableControl>
            <TableHeaders>
                <TableColumnHeader>
                    <Label>Mode</Label>
                    <Width>7</Width>
                    <Alignment>left</Alignment>
                </TableColumnHeader>
                <TableColumnHeader>
                    <Label>LastWriteTime</Label>
                    <Width>25</Width>
                    <Alignment>right</Alignment>
                </TableColumnHeader>
                <TableColumnHeader>
                    <Label>CreationTime</Label>
                    <Width>25</Width>
                    <Alignment>right</Alignment>
                </TableColumnHeader>
                <TableColumnHeader>
                    <Label>Length</Label>
                    <Width>14</Width>
                    <Alignment>right</Alignment>
                </TableColumnHeader>
                <TableColumnHeader/>
            </TableHeaders>
            <TableRowEntries>
                <TableRowEntry>
                    <Wrap/>
                    <TableColumnItems>
                        <TableColumnItem>
                            <PropertyName>Mode</PropertyName>
                        </TableColumnItem>
                        <TableColumnItem>
                            <ScriptBlock>
                                [String]::Format("{0,10}  {1,8}",
                                    $_.LastWriteTime.ToString("d"),
                                    $_.LastWriteTime.ToString("t"))
                            </ScriptBlock>
                        </TableColumnItem>
                        <TableColumnItem>
                            <ScriptBlock>
                                [String]::Format("{0,10}  {1,8}",
                                    $_.CreationTime.ToString("d"),
                                    $_.LastWriteTime.ToString("t"))
                            </ScriptBlock>
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

## <a name="see-also"></a><span data-ttu-id="65b91-233">См. также статью</span><span class="sxs-lookup"><span data-stu-id="65b91-233">See also</span></span>

[<span data-ttu-id="65b91-234">Export-FormatData</span><span class="sxs-lookup"><span data-stu-id="65b91-234">Export-FormatData</span></span>](xref:Microsoft.PowerShell.Utility.Export-FormatData)

[<span data-ttu-id="65b91-235">Get-FormatData;</span><span class="sxs-lookup"><span data-stu-id="65b91-235">Get-FormatData</span></span>](xref:Microsoft.PowerShell.Utility.Get-FormatData)

[<span data-ttu-id="65b91-236">Get-TraceSource</span><span class="sxs-lookup"><span data-stu-id="65b91-236">Get-TraceSource</span></span>](xref:Microsoft.PowerShell.Utility.Get-TraceSource)

[<span data-ttu-id="65b91-237">Ссылка на схему формата XML</span><span class="sxs-lookup"><span data-stu-id="65b91-237">Format Schema XML Reference</span></span>](/powershell/scripting/developer/format/format-schema-xml-reference)

[<span data-ttu-id="65b91-238">Trace-Command</span><span class="sxs-lookup"><span data-stu-id="65b91-238">Trace-Command</span></span>](xref:Microsoft.PowerShell.Utility.Trace-Command)

[<span data-ttu-id="65b91-239">Update-FormatData</span><span class="sxs-lookup"><span data-stu-id="65b91-239">Update-FormatData</span></span>](xref:Microsoft.PowerShell.Utility.Update-FormatData)

[<span data-ttu-id="65b91-240">Написание файла форматирования PowerShell</span><span class="sxs-lookup"><span data-stu-id="65b91-240">Writing a PowerShell Formatting File</span></span>](/powershell/scripting/developer/format/writing-a-powershell-formatting-file)
