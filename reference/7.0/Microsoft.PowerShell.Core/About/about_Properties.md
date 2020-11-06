---
description: Описывает использование свойств объекта в PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_properties?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Properties
ms.openlocfilehash: a9ba35ea0a999b116f818bffa5fba3a1366687b1
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231005"
---
# <a name="about-properties"></a><span data-ttu-id="5e57a-104">Сведения о свойствах</span><span class="sxs-lookup"><span data-stu-id="5e57a-104">About Properties</span></span>

## <a name="short-description"></a><span data-ttu-id="5e57a-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="5e57a-105">Short description</span></span>
<span data-ttu-id="5e57a-106">Описывает использование свойств объекта в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5e57a-106">Describes how to use object properties in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="5e57a-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="5e57a-107">Long description</span></span>

<span data-ttu-id="5e57a-108">PowerShell использует структурированные коллекции сведений, называемых объектами, для представления элементов в хранилищах данных или состояния компьютера.</span><span class="sxs-lookup"><span data-stu-id="5e57a-108">PowerShell uses structured collections of information called objects to represent the items in data stores or the state of the computer.</span></span> <span data-ttu-id="5e57a-109">Как правило, работа осуществляется с объектом, который является частью Microsoft .NET Framework, но можно также создавать пользовательские объекты в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5e57a-109">Typically, you work with object that are part of the Microsoft .NET Framework, but you can also create custom objects in PowerShell.</span></span>

<span data-ttu-id="5e57a-110">Элемент и его объект тесно связаны между собой.</span><span class="sxs-lookup"><span data-stu-id="5e57a-110">The association between an item and its object is very close.</span></span> <span data-ttu-id="5e57a-111">При изменении объекта обычно изменяется и элемент, который он представляет.</span><span class="sxs-lookup"><span data-stu-id="5e57a-111">When you change an object, you usually change the item that it represents.</span></span> <span data-ttu-id="5e57a-112">Например, при получении файла в PowerShell фактический файл не получается.</span><span class="sxs-lookup"><span data-stu-id="5e57a-112">For example, when you get a file in PowerShell, you do not get the actual file.</span></span> <span data-ttu-id="5e57a-113">Вместо этого вы получите объект FileInfo, представляющий файл.</span><span class="sxs-lookup"><span data-stu-id="5e57a-113">Instead, you get a FileInfo object that represents the file.</span></span> <span data-ttu-id="5e57a-114">При изменении объекта FileInfo файл также изменяется.</span><span class="sxs-lookup"><span data-stu-id="5e57a-114">When you change the FileInfo object, the file changes too.</span></span>

<span data-ttu-id="5e57a-115">Большинство объектов имеют свойства.</span><span class="sxs-lookup"><span data-stu-id="5e57a-115">Most objects have properties.</span></span> <span data-ttu-id="5e57a-116">Свойства —это данные, связанные с объектом.</span><span class="sxs-lookup"><span data-stu-id="5e57a-116">Properties are the data that is associated with an object.</span></span> <span data-ttu-id="5e57a-117">Различные типы объектов имеют разные свойства.</span><span class="sxs-lookup"><span data-stu-id="5e57a-117">Different types of object have different properties.</span></span> <span data-ttu-id="5e57a-118">Например, объект FileInfo, представляющий файл, имеет свойство **IsReadOnly** , которое содержит $true, если файл имеет атрибут только для чтения и $false в противном случае.</span><span class="sxs-lookup"><span data-stu-id="5e57a-118">For example, a FileInfo object, which represents a file, has an **IsReadOnly** property that contains $True if the file the read-only attribute and $False if it does not.</span></span>
<span data-ttu-id="5e57a-119">Объект DirectoryInfo, представляющий каталог файловой системы, имеет свойство Parent, которое содержит путь к родительскому каталогу.</span><span class="sxs-lookup"><span data-stu-id="5e57a-119">A DirectoryInfo object, which represents a file system directory, has a Parent property that contains the path to the parent directory.</span></span>

### <a name="object-properties"></a><span data-ttu-id="5e57a-120">Свойства объекта</span><span class="sxs-lookup"><span data-stu-id="5e57a-120">Object properties</span></span>

<span data-ttu-id="5e57a-121">Чтобы получить свойства объекта, используйте `Get-Member` командлет.</span><span class="sxs-lookup"><span data-stu-id="5e57a-121">To get the properties of an object, use the `Get-Member` cmdlet.</span></span> <span data-ttu-id="5e57a-122">Например, чтобы получить свойства объекта **FileInfo** , используйте `Get-ChildItem` командлет, чтобы получить объект FileInfo, представляющий файл.</span><span class="sxs-lookup"><span data-stu-id="5e57a-122">For example, to get the properties of a **FileInfo** object, use the `Get-ChildItem` cmdlet to get the FileInfo object that represents a file.</span></span> <span data-ttu-id="5e57a-123">Затем используйте оператор конвейера (&#124;), чтобы отправить объект **FileInfo** в `Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="5e57a-123">Then, use a pipeline operator (&#124;) to send the **FileInfo** object to `Get-Member`.</span></span> <span data-ttu-id="5e57a-124">Следующая команда возвращает файл PowerShell.exe и отправляет его в `Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="5e57a-124">The following command gets the PowerShell.exe file and sends it to `Get-Member`.</span></span>
<span data-ttu-id="5e57a-125">\$Автоматическая переменная pshome содержит путь к каталогу установки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5e57a-125">The \$Pshome automatic variable contains the path of the PowerShell installation directory.</span></span>

```powershell
Get-ChildItem $pshome\PowerShell.exe | Get-Member
```

<span data-ttu-id="5e57a-126">Выходные данные команды выводят список элементов объекта **FileInfo** .</span><span class="sxs-lookup"><span data-stu-id="5e57a-126">The output of the command lists the members of the **FileInfo** object.</span></span>
<span data-ttu-id="5e57a-127">К элементам относятся свойства и методы.</span><span class="sxs-lookup"><span data-stu-id="5e57a-127">Members include both properties and methods.</span></span> <span data-ttu-id="5e57a-128">При работе в PowerShell у вас есть доступ ко всем членам этих объектов.</span><span class="sxs-lookup"><span data-stu-id="5e57a-128">When you work in PowerShell, you have access to all the members of the objects.</span></span>

<span data-ttu-id="5e57a-129">Чтобы получить только свойства объекта, а не методы, используйте параметр MemberType `Get-Member` командлета со значением Property, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="5e57a-129">To get only the properties of an object and not the methods, use the MemberType parameter of the `Get-Member` cmdlet with a value of "property", as shown in the following example.</span></span>

```powershell
Get-ChildItem $pshome\PowerShell.exe | Get-Member -MemberType property
```

```Output
TypeName: System.IO.FileInfo

Name              MemberType Definition
----              ---------- ----------
Attributes        Property   System.IO.FileAttributes Attributes {get;set;}
CreationTime      Property   System.DateTime CreationTime {get;set;}
CreationTimeUtc   Property   System.DateTime CreationTimeUtc {get;set;}
Directory         Property   System.IO.DirectoryInfo Directory {get;}
DirectoryName     Property   System.String DirectoryName {get;}
Exists            Property   System.Boolean Exists {get;}
Extension         Property   System.String Extension {get;}
FullName          Property   System.String FullName {get;}
IsReadOnly        Property   System.Boolean IsReadOnly {get;set;}
LastAccessTime    Property   System.DateTime LastAccessTime {get;set;}
LastAccessTimeUtc Property   System.DateTime LastAccessTimeUtc {get;set;}
LastWriteTime     Property   System.DateTime LastWriteTime {get;set;}
LastWriteTimeUtc  Property   System.DateTime LastWriteTimeUtc {get;set;}
Length            Property   System.Int64 Length {get;}
Name              Property   System.String Name {get;}
```

<span data-ttu-id="5e57a-130">После нахождения свойств их можно использовать в командах PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5e57a-130">After you find the properties, you can use them in your PowerShell commands.</span></span>

## <a name="property-values"></a><span data-ttu-id="5e57a-131">Значения свойств</span><span class="sxs-lookup"><span data-stu-id="5e57a-131">Property values</span></span>

<span data-ttu-id="5e57a-132">Несмотря на то, что все объекты определенного типа имеют одинаковые свойства, значения этих свойств описывают конкретный объект.</span><span class="sxs-lookup"><span data-stu-id="5e57a-132">Although every object of a specific type has the same properties, the values of those properties describe the particular object.</span></span> <span data-ttu-id="5e57a-133">Например, каждый объект FileInfo имеет свойство CreationTime, но значение этого свойства разное для каждого файла.</span><span class="sxs-lookup"><span data-stu-id="5e57a-133">For example, every FileInfo object has a CreationTime property, but the value of that property differs for each file.</span></span>

<span data-ttu-id="5e57a-134">Как правило, для получения значений свойств объекта используется точка.</span><span class="sxs-lookup"><span data-stu-id="5e57a-134">The most common way to get the values of the properties of an object is to use the dot method.</span></span> <span data-ttu-id="5e57a-135">Введите ссылку на объект, например переменную, содержащую этот объект, либо команду, которая его возвращает.</span><span class="sxs-lookup"><span data-stu-id="5e57a-135">Type a reference to the object, such as a variable that contains the object, or a command that gets the object.</span></span> <span data-ttu-id="5e57a-136">Затем введите точку (.) и имя свойства.</span><span class="sxs-lookup"><span data-stu-id="5e57a-136">Then, type a dot (.) followed by the property name.</span></span>

<span data-ttu-id="5e57a-137">Например, следующая команда отображает значение свойства CreationTime файла PowerShell.exe.</span><span class="sxs-lookup"><span data-stu-id="5e57a-137">For example, the following command displays the value of the CreationTime property of the PowerShell.exe file.</span></span> <span data-ttu-id="5e57a-138">`Get-ChildItem`Команда возвращает объект FileInfo, представляющий файл PowerShell.exe.</span><span class="sxs-lookup"><span data-stu-id="5e57a-138">The `Get-ChildItem` command returns a FileInfo object that represents the PowerShell.exe file.</span></span> <span data-ttu-id="5e57a-139">Команду следует заключить в скобки, чтобы она выполнялась перед тем, как к свойствам получат доступ.</span><span class="sxs-lookup"><span data-stu-id="5e57a-139">The command is enclosed in parentheses to make sure that it is executed before any properties are accessed.</span></span> <span data-ttu-id="5e57a-140">`Get-ChildItem`За командой следует точка и имя свойства CreationTime, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="5e57a-140">The `Get-ChildItem` command is followed by a dot and the name of the CreationTime property, as follows:</span></span>

```powershell
(Get-ChildItem $pshome\PowerShell.exe).creationtime
```

```output
Tuesday, March 18, 2008 12:07:52 AM
```

<span data-ttu-id="5e57a-141">Вы также можете сохранить объект в переменной и получить его свойства, используя точку, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="5e57a-141">You can also save an object in a variable and then get its properties by using the dot method, as shown in the following example:</span></span>

```powershell
$a = Get-ChildItem $pshome\PowerShell.exe
$a.CreationTime
```

```output
Tuesday, March 18, 2008 12:07:52 AM
```

<span data-ttu-id="5e57a-142">Также можно использовать `Select-Object` `Format-List` командлеты и для вывода значений свойств объекта.</span><span class="sxs-lookup"><span data-stu-id="5e57a-142">You can also use the `Select-Object` and `Format-List` cmdlets to display the property values of an object.</span></span> <span data-ttu-id="5e57a-143">`Select-Object``Format-List`каждый из них имеет параметр **Property** .</span><span class="sxs-lookup"><span data-stu-id="5e57a-143">`Select-Object` and `Format-List` each have a **Property** parameter.</span></span> <span data-ttu-id="5e57a-144">С помощью параметра **Property** можно указать одно или несколько свойств и их значений.</span><span class="sxs-lookup"><span data-stu-id="5e57a-144">You can use the **Property** parameter to specify one or more properties and their values.</span></span> <span data-ttu-id="5e57a-145">Или можно использовать подстановочный знак (\*) для представления всех свойств.</span><span class="sxs-lookup"><span data-stu-id="5e57a-145">Or, you can use the wildcard character (\*) to represent all the properties.</span></span>

<span data-ttu-id="5e57a-146">Например, следующая команда отображает значения всех свойств файла PowerShell.exe.</span><span class="sxs-lookup"><span data-stu-id="5e57a-146">For example, the following command displays the values of all the properties of the PowerShell.exe file.</span></span>

```powershell
Get-ChildItem $pshome\PowerShell.exe | Format-List -Property *
```

```output
PSPath            : Microsoft.PowerShell.Core\FileSystem::C:\Windows\System3
                    2\WindowsPowerShell\v1.0\PowerShell.exe
PSParentPath      : Microsoft.PowerShell.Core\FileSystem::C:\Windows\System3
                    2\WindowsPowerShell\v1.0
PSChildName       : PowerShell.exe
PSDrive           : C
PSProvider        : Microsoft.PowerShell.Core\FileSystem
PSIsContainer     : False
Mode              : -a----
VersionInfo       : File:             C:\Windows\System32\WindowsPowerShell\
                    v1.0\PowerShell.exe
                    InternalName:     POWERSHELL
                    OriginalFilename: PowerShell.EXE.MUI
                    FileVersion:      10.0.16299.15 (WinBuild.160101.0800)
                    FileDescription:  Windows PowerShell
                    Product:          Microsoft Windows Operating System
                    ProductVersion:   10.0.16299.15
                    Debug:            False
                    Patched:          False
                    PreRelease:       False
                    PrivateBuild:     False
                    SpecialBuild:     False
                    Language:         English (United States)

BaseName          : PowerShell
Target            : {C:\Windows\WinSxS\amd64_microsoft-windows-powershell-ex
                    e_31bf3856ad364e35_10.0.16299.15_none_8c022aa6735716ae\p
                    owershell.exe}
LinkType          : HardLink
Name              : PowerShell.exe
Length            : 449024
DirectoryName     : C:\Windows\System32\WindowsPowerShell\v1.0
Directory         : C:\Windows\System32\WindowsPowerShell\v1.0
IsReadOnly        : False
Exists            : True
FullName          : C:\Windows\System32\WindowsPowerShell\v1.0\PowerShell.ex
Extension         : .exe
CreationTime      : 9/29/2017 6:43:19 AM
CreationTimeUtc   : 9/29/2017 1:43:19 PM
LastAccessTime    : 9/29/2017 6:43:19 AM
LastAccessTimeUtc : 9/29/2017 1:43:19 PM
LastWriteTime     : 9/29/2017 6:43:19 AM
LastWriteTimeUtc  : 9/29/2017 1:43:19 PM
Attributes        : Archive
```

### <a name="static-properties"></a><span data-ttu-id="5e57a-147">Статические свойства</span><span class="sxs-lookup"><span data-stu-id="5e57a-147">Static properties</span></span>

<span data-ttu-id="5e57a-148">В PowerShell можно использовать статические свойства классов .NET.</span><span class="sxs-lookup"><span data-stu-id="5e57a-148">You can use the static properties of .NET classes in PowerShell.</span></span> <span data-ttu-id="5e57a-149">Статические свойства являются свойствами класса, в отличие от стандартных свойств, которые являются свойствами объекта.</span><span class="sxs-lookup"><span data-stu-id="5e57a-149">Static properties are properties of class, unlike standard properties, which are properties of an object.</span></span>

<span data-ttu-id="5e57a-150">Чтобы получить статические свойства класса, используйте параметр Static командлета Get-Member.</span><span class="sxs-lookup"><span data-stu-id="5e57a-150">To get the static properties of an class, use the Static parameter of the Get-Member cmdlet.</span></span>

<span data-ttu-id="5e57a-151">Например, следующая команда возвращает статические свойства `System.DateTime` класса.</span><span class="sxs-lookup"><span data-stu-id="5e57a-151">For example, the following command gets the static properties of the `System.DateTime` class.</span></span>

```powershell
Get-Date | Get-Member -MemberType Property -Static
```

```Output
TypeName: System.DateTime

Name     MemberType Definition
----     ---------- ----------
MaxValue Property   static datetime MaxValue {get;}
MinValue Property   static datetime MinValue {get;}
Now      Property   datetime Now {get;}
Today    Property   datetime Today {get;}
UtcNow   Property   datetime UtcNow {get;}
```

<span data-ttu-id="5e57a-152">Чтобы получить значение статического свойства, используйте следующий синтаксис.</span><span class="sxs-lookup"><span data-stu-id="5e57a-152">To get the value of a static property, use the following syntax.</span></span>

```
[<ClassName>]::<Property>
```

<span data-ttu-id="5e57a-153">Например, следующая команда возвращает значение статического свойства UtcNow `System.DateTime` класса.</span><span class="sxs-lookup"><span data-stu-id="5e57a-153">For example, the following command gets the value of the UtcNow static property of the `System.DateTime` class.</span></span>

```powershell
[System.DateTime]::UtcNow
```

### <a name="properties-of-scalar-objects-and-collections"></a><span data-ttu-id="5e57a-154">Свойства скалярных объектов и коллекций</span><span class="sxs-lookup"><span data-stu-id="5e57a-154">Properties of scalar objects and collections</span></span>

<span data-ttu-id="5e57a-155">Свойства одного объекта (скаляр) определенного типа часто отличаются от свойств коллекции объектов одного типа.</span><span class="sxs-lookup"><span data-stu-id="5e57a-155">The properties of one ("scalar") object of a particular type are often different from the properties of a collection of objects of the same type.</span></span>
<span data-ttu-id="5e57a-156">Например, у каждой службы есть свойство **DisplayName** , но коллекция служб не имеет свойства **DisplayName** .</span><span class="sxs-lookup"><span data-stu-id="5e57a-156">For example, every service has as **DisplayName** property, but a collection of services does not have a **DisplayName** property.</span></span>

<span data-ttu-id="5e57a-157">Следующая команда возвращает значение свойства **DisplayName** службы "аудиосрв".</span><span class="sxs-lookup"><span data-stu-id="5e57a-157">The following command gets the value of the **DisplayName** property of the 'Audiosrv' service.</span></span>

```powershell
(Get-Service Audiosrv).DisplayName
```

```output
Windows Audio
```

<span data-ttu-id="5e57a-158">Начиная с PowerShell 3,0, PowerShell пытается предотвратить ошибки скрипта, возникающие в результате различных свойств скалярных объектов и коллекций.</span><span class="sxs-lookup"><span data-stu-id="5e57a-158">Beginning in PowerShell 3.0, PowerShell tries to prevent scripting errors that result from the differing properties of scalar objects and collections.</span></span> <span data-ttu-id="5e57a-159">Та же команда возвращает значение свойства **DisplayName** каждой службы, которая `Get-Service` возвращает.</span><span class="sxs-lookup"><span data-stu-id="5e57a-159">The same command returns the value of the **DisplayName** property of every service that `Get-Service` returns.</span></span>

```powershell
(Get-Service).DisplayName
```

```output
Application Experience
Application Layer Gateway Service
Windows All-User Install Agent
Application Identity
Application Information
...
```

<span data-ttu-id="5e57a-160">При отправке коллекции, но при запросе свойства, которое существует только для отдельных ("скалярных") объектов, PowerShell возвращает значение этого свойства для каждого объекта в коллекции.</span><span class="sxs-lookup"><span data-stu-id="5e57a-160">When you submit a collection, but request a property that exists only on single ("scalar") objects, PowerShell returns the value of that property for every object in the collection.</span></span>

<span data-ttu-id="5e57a-161">Все коллекции имеют свойство **Count** , которое возвращает количество объектов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="5e57a-161">All collections have a **Count** property that returns how many objects are in the collection.</span></span>

```powershell
(Get-Service).Count
```

```output
176
```

<span data-ttu-id="5e57a-162">Начиная с PowerShell 3,0, при запросе свойства Count или length нулевых объектов или одного объекта PowerShell возвращает правильное значение.</span><span class="sxs-lookup"><span data-stu-id="5e57a-162">Beginning in PowerShell 3.0, if you request the Count or Length property of zero objects or one object, PowerShell returns the correct value.</span></span>

```powershell
(Get-Service Audiosrv).Count
```

```output
1
```

<span data-ttu-id="5e57a-163">Если свойство существует для отдельных объектов и коллекции, то возвращается только свойство коллекции.</span><span class="sxs-lookup"><span data-stu-id="5e57a-163">If a property exists on the individual objects and on the collection, only the collection's property is returned.</span></span>

 ```powershell
 $collection = @(
 [pscustomobject]@{length = "foo"}
 [pscustomobject]@{length = "bar"}
 )
 # PowerShell returns the collection's Length.
 $collection.length
 ```

 ```output
 2
 ```

<span data-ttu-id="5e57a-164">Эта возможность также действует для методов скалярных объектов и коллекций.</span><span class="sxs-lookup"><span data-stu-id="5e57a-164">This feature also works on methods of scalar objects and collections.</span></span> <span data-ttu-id="5e57a-165">Дополнительные сведения см. в разделе [about_Methods](about_methods.md).</span><span class="sxs-lookup"><span data-stu-id="5e57a-165">For more information, see [about_Methods](about_methods.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5e57a-166">См. также статью</span><span class="sxs-lookup"><span data-stu-id="5e57a-166">See also</span></span>

[<span data-ttu-id="5e57a-167">about_Methods</span><span class="sxs-lookup"><span data-stu-id="5e57a-167">about_Methods</span></span>](about_Methods.md)

[<span data-ttu-id="5e57a-168">about_Objects</span><span class="sxs-lookup"><span data-stu-id="5e57a-168">about_Objects</span></span>](about_Objects.md)

[<span data-ttu-id="5e57a-169">Get-Member</span><span class="sxs-lookup"><span data-stu-id="5e57a-169">Get-Member</span></span>](xref:Microsoft.PowerShell.Utility.Get-Member)

[<span data-ttu-id="5e57a-170">Select-Object</span><span class="sxs-lookup"><span data-stu-id="5e57a-170">Select-Object</span></span>](xref:Microsoft.PowerShell.Utility.Select-Object)

[<span data-ttu-id="5e57a-171">Format-List</span><span class="sxs-lookup"><span data-stu-id="5e57a-171">Format-List</span></span>](xref:Microsoft.PowerShell.Utility.Format-List)