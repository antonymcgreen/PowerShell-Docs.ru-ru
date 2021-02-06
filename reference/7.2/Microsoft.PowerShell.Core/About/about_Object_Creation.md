---
description: Объясняется, как создавать объекты в PowerShell.
Locale: en-US
ms.date: 09/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_object_creation?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Object_Creation
ms.openlocfilehash: 72c0d763fe7f3838c8b2ca68930521e24d0e6139
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604367"
---
# <a name="about-object-creation"></a><span data-ttu-id="47f61-103">О создании объектов</span><span class="sxs-lookup"><span data-stu-id="47f61-103">About Object Creation</span></span>

## <a name="short-description"></a><span data-ttu-id="47f61-104">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="47f61-104">Short description</span></span>

<span data-ttu-id="47f61-105">Объясняется, как создавать объекты в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="47f61-105">Explains how to create objects in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="47f61-106">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="47f61-106">Long description</span></span>

<span data-ttu-id="47f61-107">Вы можете создавать объекты в PowerShell и использовать объекты, созданные в командах и скриптах.</span><span class="sxs-lookup"><span data-stu-id="47f61-107">You can create objects in PowerShell and use the objects that you create in commands and scripts.</span></span>

<span data-ttu-id="47f61-108">Существует множество способов создания объектов. Этот список не является самым непредсказуемым.</span><span class="sxs-lookup"><span data-stu-id="47f61-108">There are many ways to create objects, this list is not definitive:</span></span>

- <span data-ttu-id="47f61-109">[New-Object](xref:Microsoft.PowerShell.Utility.New-Object): создает экземпляр объекта платформа .NET Framework или COM-объекта.</span><span class="sxs-lookup"><span data-stu-id="47f61-109">[New-Object](xref:Microsoft.PowerShell.Utility.New-Object): Creates an instance of a .NET Framework object or COM object.</span></span>
- <span data-ttu-id="47f61-110">[Import-CSV](xref:Microsoft.PowerShell.Utility.Import-Csv) /
   [ConvertFrom-CSV](xref:Microsoft.PowerShell.Utility.ConvertFrom-Csv): создает пользовательские объекты (**PSCustomObject**) из элементов, определенных как значения с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="47f61-110">[Import-Csv](xref:Microsoft.PowerShell.Utility.Import-Csv)/
  [ConvertFrom-CSV](xref:Microsoft.PowerShell.Utility.ConvertFrom-Csv): Creates custom objects (**PSCustomObject**) from the items defined as comma separated values.</span></span>
- <span data-ttu-id="47f61-111">[ConvertFrom-JSON](xref:Microsoft.PowerShell.Utility.ConvertFrom-Json): создает пользовательские объекты, определенные в НОТАЦИЯ объектов JavaScript (JSON).</span><span class="sxs-lookup"><span data-stu-id="47f61-111">[ConvertFrom-Json](xref:Microsoft.PowerShell.Utility.ConvertFrom-Json): Creates custom objects defined in JavaScript Object Notation (JSON).</span></span>
- <span data-ttu-id="47f61-112">[ConvertFrom-StringData](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData): создает пользовательские объекты, определенные как пары "ключ — значение".</span><span class="sxs-lookup"><span data-stu-id="47f61-112">[ConvertFrom-StringData](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData): Creates custom objects defined as key value pairs.</span></span>
- <span data-ttu-id="47f61-113">[Add-Type (добавить тип)](xref:Microsoft.PowerShell.Utility.Add-Type). позволяет определить класс в сеансе PowerShell, с которым можно создать экземпляр `New-Object` .</span><span class="sxs-lookup"><span data-stu-id="47f61-113">[Add-Type](xref:Microsoft.PowerShell.Utility.Add-Type): Allows you to define a class in your PowerShell session that you can instantiate with `New-Object`.</span></span>
- <span data-ttu-id="47f61-114">[New-Module](xref:Microsoft.PowerShell.Core.New-Module): параметр **AsCustomObject** создает пользовательский объект, определяемый с помощью блока сценария.</span><span class="sxs-lookup"><span data-stu-id="47f61-114">[New-Module](xref:Microsoft.PowerShell.Core.New-Module): The **AsCustomObject** parameter creates a custom object you define using script block.</span></span>
- <span data-ttu-id="47f61-115">[Добавить-член](xref:Microsoft.PowerShell.Utility.Add-Member): добавляет свойства в существующие объекты.</span><span class="sxs-lookup"><span data-stu-id="47f61-115">[Add-Member](xref:Microsoft.PowerShell.Utility.Add-Member): Adds properties to existing objects.</span></span> <span data-ttu-id="47f61-116">Можно использовать `Add-Member` для создания пользовательского объекта из простого типа, например `[System.Int32]` .</span><span class="sxs-lookup"><span data-stu-id="47f61-116">You can use `Add-Member` to create a custom object out of a simple type, like `[System.Int32]`.</span></span>
- <span data-ttu-id="47f61-117">[Select-Object](xref:Microsoft.PowerShell.Utility.Select-Object): выбирает свойства объекта.</span><span class="sxs-lookup"><span data-stu-id="47f61-117">[Select-Object](xref:Microsoft.PowerShell.Utility.Select-Object): Selects properties on an object.</span></span> <span data-ttu-id="47f61-118">Можно использовать `Select-Object` для создания настраиваемых и вычисляемых свойств для уже созданного объекта.</span><span class="sxs-lookup"><span data-stu-id="47f61-118">You can use `Select-Object` to create custom and calculated properties on an already instantiated object.</span></span>

<span data-ttu-id="47f61-119">В этой статье рассматриваются следующие дополнительные методы.</span><span class="sxs-lookup"><span data-stu-id="47f61-119">The following additional methods are covered in this article:</span></span>

- <span data-ttu-id="47f61-120">Путем вызова конструктора типа с помощью статического `new()` метода</span><span class="sxs-lookup"><span data-stu-id="47f61-120">By calling a type's constructor using a static `new()` method</span></span>
- <span data-ttu-id="47f61-121">Путем приведения хэш-таблиц имен свойств и значений свойств</span><span class="sxs-lookup"><span data-stu-id="47f61-121">By typecasting hash tables of property names and property values</span></span>

## <a name="static-new-method"></a><span data-ttu-id="47f61-122">Статический метод New ()</span><span class="sxs-lookup"><span data-stu-id="47f61-122">Static new() method</span></span>

<span data-ttu-id="47f61-123">Все типы .NET имеют `new()` метод, позволяющий более легко создавать экземпляры.</span><span class="sxs-lookup"><span data-stu-id="47f61-123">All .NET types have a `new()` method that allows you to construct instances more easily.</span></span> <span data-ttu-id="47f61-124">Можно также просмотреть все доступные конструкторы для данного типа.</span><span class="sxs-lookup"><span data-stu-id="47f61-124">You can also see all the available constructors for a given type.</span></span>

<span data-ttu-id="47f61-125">Чтобы просмотреть конструкторы для типа, укажите `new` имя метода после имени типа и нажмите клавишу `<ENTER>` .</span><span class="sxs-lookup"><span data-stu-id="47f61-125">To see the constructors for a type, specify the `new` method name after the type name and press `<ENTER>`.</span></span>

```powershell
[System.Uri]::new
```

```Output
OverloadDefinitions
-------------------
uri new(string uriString)
uri new(string uriString, bool dontEscape)
uri new(uri baseUri, string relativeUri, bool dontEscape)
uri new(string uriString, System.UriKind uriKind)
uri new(uri baseUri, string relativeUri)
uri new(uri baseUri, uri relativeUri)
```

<span data-ttu-id="47f61-126">Теперь можно создать **System. URI** , указав соответствующий конструктор.</span><span class="sxs-lookup"><span data-stu-id="47f61-126">Now, you can create a **System.Uri** by specifying the appropriate constructor.</span></span>

```powershell
[System.Uri]::new("https://www.bing.com")
```

```Output
AbsolutePath   : /
AbsoluteUri    : https://www.bing.com/
LocalPath      : /
Authority      : www.bing.com
...
```

<span data-ttu-id="47f61-127">Чтобы определить, какие типы .NET в данный момент загружены для создания экземпляра, можно использовать следующий пример.</span><span class="sxs-lookup"><span data-stu-id="47f61-127">You can use the following sample to determine what .NET types are currently loaded for you to instantiate.</span></span>

```powershell
[AppDomain]::CurrentDomain.GetAssemblies() |
  ForEach-Object {
    $_.GetExportedTypes() |
      ForEach-Object { $_.FullName }
  }
```

<span data-ttu-id="47f61-128">Объекты, созданные с помощью `new()` метода, не могут иметь те же свойства, что и объекты того же типа, которые создаются командлетами PowerShell.</span><span class="sxs-lookup"><span data-stu-id="47f61-128">Objects created using the `new()` method may not have the same properties as objects of the same type that are created by PowerShell cmdlets.</span></span> <span data-ttu-id="47f61-129">Командлеты PowerShell, поставщики и система расширенного типа могут добавлять дополнительные свойства в экземпляр.</span><span class="sxs-lookup"><span data-stu-id="47f61-129">PowerShell cmdlets, providers, and Extended Type System can add extra properties to the instance.</span></span>

<span data-ttu-id="47f61-130">Например, Поставщик FileSystem в PowerShell добавляет шесть значений **NoteProperty** в объект **DirectoryInfo** , возвращаемый методом `Get-Item` .</span><span class="sxs-lookup"><span data-stu-id="47f61-130">For example, the FileSystem provider in PowerShell adds six **NoteProperty** values to the **DirectoryInfo** object returned by `Get-Item`.</span></span>

```powershell
$PSDirInfo = Get-Item /
$PSDirInfo | Get-Member | Group-Object MemberType | Select-Object Count, Name
```

```Output
Count Name
----- ----
    4 CodeProperty
   13 Property
    6 NoteProperty
    1 ScriptProperty
   18 Method
```

<span data-ttu-id="47f61-131">При непосредственном создании объекта **DirectoryInfo** он не имеет шести значений **NoteProperty** .</span><span class="sxs-lookup"><span data-stu-id="47f61-131">When you create a **DirectoryInfo** object directly, it does not have those six **NoteProperty** values.</span></span>

```powershell
$NewDirInfo = [System.IO.DirectoryInfo]::new('/')
$NewDirInfo | Get-Member | Group-Object MemberType | Select-Object Count, Name
```

```Output
Count Name
----- ----
    4 CodeProperty
   13 Property
    1 ScriptProperty
   18 Method
```

<span data-ttu-id="47f61-132">Дополнительные сведения о системе расширенных типов см. в разделе [about_Types.ps1XML](about_Types.ps1xml.md).</span><span class="sxs-lookup"><span data-stu-id="47f61-132">For more information about the Extended Type System, see [about_Types.ps1xml](about_Types.ps1xml.md).</span></span>

<span data-ttu-id="47f61-133">Эта функция была добавлена в PowerShell 5,0</span><span class="sxs-lookup"><span data-stu-id="47f61-133">This feature was added in PowerShell 5.0</span></span>

## <a name="create-objects-from-hash-tables"></a><span data-ttu-id="47f61-134">Создание объектов из хэш-таблиц</span><span class="sxs-lookup"><span data-stu-id="47f61-134">Create objects from hash tables</span></span>

<span data-ttu-id="47f61-135">Вы можете создать объект из хэш-таблицы свойств и значений свойств.</span><span class="sxs-lookup"><span data-stu-id="47f61-135">You can create an object from a hash table of properties and property values.</span></span>

<span data-ttu-id="47f61-136">Синтаксис выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="47f61-136">The syntax is as follows:</span></span>

```
[<class-name>]@{
  <property-name>=<property-value>
  <property-name>=<property-value>
}
```

<span data-ttu-id="47f61-137">Этот метод работает только для классов, у которых есть конструктор без параметров.</span><span class="sxs-lookup"><span data-stu-id="47f61-137">This method works only for classes that have a parameterless constructor.</span></span> <span data-ttu-id="47f61-138">Свойства объекта должны быть общедоступными и настраиваемыми.</span><span class="sxs-lookup"><span data-stu-id="47f61-138">The object properties must be public and settable.</span></span>

<span data-ttu-id="47f61-139">Эта функция была добавлена в PowerShell версии 3,0</span><span class="sxs-lookup"><span data-stu-id="47f61-139">This feature was added in PowerShell version 3.0</span></span>

## <a name="create-custom-objects-from-hash-tables"></a><span data-ttu-id="47f61-140">Создание пользовательских объектов из хэш-таблиц</span><span class="sxs-lookup"><span data-stu-id="47f61-140">Create custom objects from hash tables</span></span>

<span data-ttu-id="47f61-141">Пользовательские объекты очень полезны и легко создаются с помощью метода хэш-таблицы.</span><span class="sxs-lookup"><span data-stu-id="47f61-141">Custom objects are very useful and are easy to create using the hash table method.</span></span> <span data-ttu-id="47f61-142">Класс **PSCustomObject** разработан специально для этой цели.</span><span class="sxs-lookup"><span data-stu-id="47f61-142">The **PSCustomObject** class is designed specifically for this purpose.</span></span>

<span data-ttu-id="47f61-143">Пользовательские объекты — это отличный способ возврата настраиваемых выходных данных из функции или скрипта.</span><span class="sxs-lookup"><span data-stu-id="47f61-143">Custom objects are an excellent way to return customized output from a function or script.</span></span> <span data-ttu-id="47f61-144">Это более полезно, чем возврат форматированных выходных данных, которые не могут быть переформатированы или переданы другим командам.</span><span class="sxs-lookup"><span data-stu-id="47f61-144">This is more useful than returning formatted output that cannot be reformatted or piped to other commands.</span></span>

<span data-ttu-id="47f61-145">Команды в `Test-Object function` задают некоторые значения переменных, а затем используют эти значения для создания пользовательского объекта.</span><span class="sxs-lookup"><span data-stu-id="47f61-145">The commands in the `Test-Object function` set some variable values and then use those values to create a custom object.</span></span> <span data-ttu-id="47f61-146">Этот объект можно увидеть в разделе "пример" `Update-Help` раздела справки по командлетам.</span><span class="sxs-lookup"><span data-stu-id="47f61-146">You can see this object in use in the example section of the `Update-Help` cmdlet help topic.</span></span>

```powershell
function Test-Object {
  $ModuleName = "PSScheduledJob"
  $HelpCulture = "en-us"
  $HelpVersion = "3.1.0.0"
  [PSCustomObject]@{
    "ModuleName"=$ModuleName
    "UICulture"=$HelpCulture
    "Version"=$HelpVersion
  }
  $ModuleName = "PSWorkflow"
  $HelpCulture = "en-us"
  $HelpVersion = "3.0.0.0"
  [PSCustomObject]@{
    "ModuleName"=$ModuleName
    "UICulture"=$HelpCulture
    "Version"=$HelpVersion
  }
}
Test-Object
```

<span data-ttu-id="47f61-147">Выходные данные этой функции представляют собой коллекцию пользовательских объектов, отформатированных по умолчанию в виде таблицы.</span><span class="sxs-lookup"><span data-stu-id="47f61-147">The output of this function is a collection of custom objects formatted as a table by default.</span></span>

```Output
ModuleName        UICulture      Version
---------         ---------      -------
PSScheduledJob    en-us          3.1.0.0
PSWorkflow        en-us          3.0.0.0
```

<span data-ttu-id="47f61-148">Пользователи могут управлять свойствами пользовательских объектов так же, как и со стандартными объектами.</span><span class="sxs-lookup"><span data-stu-id="47f61-148">Users can manage the properties of the custom objects just as they do with standard objects.</span></span>

```powershell
(Test-Object).ModuleName
```

```Output
 PSScheduledJob
 PSWorkflow
```

## <a name="create-non-custom-objects-from-hash-tables"></a><span data-ttu-id="47f61-149">Создание ненастраиваемых объектов из хэш-таблиц</span><span class="sxs-lookup"><span data-stu-id="47f61-149">Create non-custom objects from hash tables</span></span>

<span data-ttu-id="47f61-150">Хэш-таблицы также можно использовать для создания объектов для непользовательских классов.</span><span class="sxs-lookup"><span data-stu-id="47f61-150">You can also use hash tables to create objects for non-custom classes.</span></span> <span data-ttu-id="47f61-151">При создании объекта для непользовательского класса требуется имя типа с указанием пространства имен, хотя вы можете опустить любой начальный компонент **системного** пространства имен.</span><span class="sxs-lookup"><span data-stu-id="47f61-151">When you create an object for a non-custom class, the namespace-qualified type name is required, although you may omit any initial **System** namespace component.</span></span>

<span data-ttu-id="47f61-152">Например, следующая команда создает объект параметра сеанса.</span><span class="sxs-lookup"><span data-stu-id="47f61-152">For example, the following command creates a session option object.</span></span>

```powershell
[System.Management.Automation.Remoting.PSSessionOption]@{
  IdleTimeout=43200000
  SkipCnCheck=$True
}
```

<span data-ttu-id="47f61-153">Требования к функции хэш-таблицы, особенно требования к конструктору без параметров, устраняют многие существующие классы.</span><span class="sxs-lookup"><span data-stu-id="47f61-153">The requirements of the hash table feature, especially the parameterless constructor requirement, eliminate many existing classes.</span></span> <span data-ttu-id="47f61-154">Однако большинство классов _параметров_ PowerShell предназначены для работы с этой функцией, а также с другими очень полезными классами, такими как класс **ProcessStartInfo** .</span><span class="sxs-lookup"><span data-stu-id="47f61-154">However, most PowerShell _option_ classes are designed to work with this feature, as well as other very useful classes, such as the **ProcessStartInfo** class.</span></span>

```powershell
[System.Diagnostics.ProcessStartInfo]@{
  CreateNoWindow="$true"
  Verb="run as"
}
```

```Output
Arguments               :
ArgumentList            : {}
CreateNoWindow          : True
EnvironmentVariables    : {OneDriveConsumer, PROCESSOR_ARCHITECTURE,
                           CommonProgramFiles(x86), APPDATA...}
Environment             : {[OneDriveConsumer, C:\Users\user1\OneDrive],
                           [PROCESSOR_ARCHITECTURE, AMD64],
                           [CommonProgramFiles(x86),
                           C:\Program Files (x86)\Common Files],
                           [APPDATA, C:\Users\user1\AppData\Roaming]...}
RedirectStandardInput   : False
RedirectStandardOutput  : False
RedirectStandardError   : False
...
```

<span data-ttu-id="47f61-155">Можно также использовать функцию хэш-таблицы при задании значений параметров.</span><span class="sxs-lookup"><span data-stu-id="47f61-155">You can also use the hash table feature when setting parameter values.</span></span> <span data-ttu-id="47f61-156">Например, значение параметра **SessionOption** объекта `New-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="47f61-156">For example, the value of the **SessionOption** parameter of the `New-PSSession`.</span></span>
<span data-ttu-id="47f61-157">Командлет может быть хэш-таблицей.</span><span class="sxs-lookup"><span data-stu-id="47f61-157">cmdlet can be a hash table.</span></span>

```powershell
New-PSSession -ComputerName Server01 -SessionOption @{
  IdleTimeout=43200000
  SkipCnCheck=$True
}
Register-ScheduledJob Name Test -FilePath .\Get-Inventory.ps1 -Trigger @{
  Frequency="Daily"
  At="15:00"
}
```

## <a name="generic-objects"></a><span data-ttu-id="47f61-158">Универсальные объекты</span><span class="sxs-lookup"><span data-stu-id="47f61-158">Generic objects</span></span>

<span data-ttu-id="47f61-159">В PowerShell можно также создавать универсальные объекты.</span><span class="sxs-lookup"><span data-stu-id="47f61-159">You can also create generic objects in PowerShell.</span></span> <span data-ttu-id="47f61-160">Универсальными шаблонами являются классы, структуры, интерфейсы и методы, которые имеют прототипы (параметры типов) для одного или нескольких типов, которые они хранят или используют.</span><span class="sxs-lookup"><span data-stu-id="47f61-160">Generics are classes, structures, interfaces, and methods that have placeholders (type parameters) for one or more of the types that they store or use.</span></span>

<span data-ttu-id="47f61-161">В следующем примере создается объект **Dictionary** .</span><span class="sxs-lookup"><span data-stu-id="47f61-161">The following example creates a **Dictionary** object.</span></span>

```powershell
$dict = New-Object 'System.Collections.Generic.Dictionary[String,Int]'
$dict.Add("One", 1)
$dict
```

```Output
Key Value
--- -----
One     1
```

<span data-ttu-id="47f61-162">Дополнительные сведения об универсальных шаблонах см. [в разделе Универсальные шаблоны в .NET](/dotnet/standard/generics).</span><span class="sxs-lookup"><span data-stu-id="47f61-162">For more information on Generics, see [Generics in .NET](/dotnet/standard/generics).</span></span>

## <a name="see-also"></a><span data-ttu-id="47f61-163">См. также</span><span class="sxs-lookup"><span data-stu-id="47f61-163">See also</span></span>

[<span data-ttu-id="47f61-164">about_Objects</span><span class="sxs-lookup"><span data-stu-id="47f61-164">about_Objects</span></span>](about_Objects.md)

[<span data-ttu-id="47f61-165">about_Methods</span><span class="sxs-lookup"><span data-stu-id="47f61-165">about_Methods</span></span>](about_Methods.md)

[<span data-ttu-id="47f61-166">about_Properties</span><span class="sxs-lookup"><span data-stu-id="47f61-166">about_Properties</span></span>](about_Properties.md)

[<span data-ttu-id="47f61-167">about_Pipelines</span><span class="sxs-lookup"><span data-stu-id="47f61-167">about_Pipelines</span></span>](about_Pipelines.md)

[<span data-ttu-id="47f61-168">about_Types.ps1xml</span><span class="sxs-lookup"><span data-stu-id="47f61-168">about_Types.ps1xml</span></span>](about_Types.ps1xml.md)
