---
description: Описывает использование свойств объекта в PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_properties?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Properties
ms.openlocfilehash: d4d3cd93e6b177e80d85315f125c647219fc4a45
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232682"
---
# <a name="about-properties"></a>Сведения о свойствах

## <a name="short-description"></a>Краткое описание
Описывает использование свойств объекта в PowerShell.

## <a name="long-description"></a>Подробное описание

PowerShell использует структурированные коллекции сведений, называемых объектами, для представления элементов в хранилищах данных или состояния компьютера. Как правило, работа осуществляется с объектом, который является частью Microsoft .NET Framework, но можно также создавать пользовательские объекты в PowerShell.

Элемент и его объект тесно связаны между собой. При изменении объекта обычно изменяется и элемент, который он представляет. Например, при получении файла в PowerShell фактический файл не получается. Вместо этого вы получите объект FileInfo, представляющий файл. При изменении объекта FileInfo файл также изменяется.

Большинство объектов имеют свойства. Свойства —это данные, связанные с объектом. Различные типы объектов имеют разные свойства. Например, объект FileInfo, представляющий файл, имеет свойство **IsReadOnly** , которое содержит $true, если файл имеет атрибут только для чтения и $false в противном случае.
Объект DirectoryInfo, представляющий каталог файловой системы, имеет свойство Parent, которое содержит путь к родительскому каталогу.

### <a name="object-properties"></a>Свойства объекта

Чтобы получить свойства объекта, используйте `Get-Member` командлет. Например, чтобы получить свойства объекта **FileInfo** , используйте `Get-ChildItem` командлет, чтобы получить объект FileInfo, представляющий файл. Затем используйте оператор конвейера (&#124;), чтобы отправить объект **FileInfo** в `Get-Member` . Следующая команда возвращает файл PowerShell.exe и отправляет его в `Get-Member` .
\$Автоматическая переменная pshome содержит путь к каталогу установки PowerShell.

```powershell
Get-ChildItem $pshome\PowerShell.exe | Get-Member
```

Выходные данные команды выводят список элементов объекта **FileInfo** .
К элементам относятся свойства и методы. При работе в PowerShell у вас есть доступ ко всем членам этих объектов.

Чтобы получить только свойства объекта, а не методы, используйте параметр MemberType `Get-Member` командлета со значением Property, как показано в следующем примере.

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

После нахождения свойств их можно использовать в командах PowerShell.

## <a name="property-values"></a>Значения свойств

Несмотря на то, что все объекты определенного типа имеют одинаковые свойства, значения этих свойств описывают конкретный объект. Например, каждый объект FileInfo имеет свойство CreationTime, но значение этого свойства разное для каждого файла.

Как правило, для получения значений свойств объекта используется точка. Введите ссылку на объект, например переменную, содержащую этот объект, либо команду, которая его возвращает. Затем введите точку (.) и имя свойства.

Например, следующая команда отображает значение свойства CreationTime файла PowerShell.exe. `Get-ChildItem`Команда возвращает объект FileInfo, представляющий файл PowerShell.exe. Команду следует заключить в скобки, чтобы она выполнялась перед тем, как к свойствам получат доступ. `Get-ChildItem`За командой следует точка и имя свойства CreationTime, как показано ниже:

```powershell
(Get-ChildItem $pshome\PowerShell.exe).creationtime
```

```output
Tuesday, March 18, 2008 12:07:52 AM
```

Вы также можете сохранить объект в переменной и получить его свойства, используя точку, как показано в следующем примере:

```powershell
$a = Get-ChildItem $pshome\PowerShell.exe
$a.CreationTime
```

```output
Tuesday, March 18, 2008 12:07:52 AM
```

Также можно использовать `Select-Object` `Format-List` командлеты и для вывода значений свойств объекта. `Select-Object``Format-List`каждый из них имеет параметр **Property** . С помощью параметра **Property** можно указать одно или несколько свойств и их значений. Или можно использовать подстановочный знак (\*) для представления всех свойств.

Например, следующая команда отображает значения всех свойств файла PowerShell.exe.

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

### <a name="static-properties"></a>Статические свойства

В PowerShell можно использовать статические свойства классов .NET. Статические свойства являются свойствами класса, в отличие от стандартных свойств, которые являются свойствами объекта.

Чтобы получить статические свойства класса, используйте параметр Static командлета Get-Member.

Например, следующая команда возвращает статические свойства `System.DateTime` класса.

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

Чтобы получить значение статического свойства, используйте следующий синтаксис.

```
[<ClassName>]::<Property>
```

Например, следующая команда возвращает значение статического свойства UtcNow `System.DateTime` класса.

```powershell
[System.DateTime]::UtcNow
```

### <a name="properties-of-scalar-objects-and-collections"></a>Свойства скалярных объектов и коллекций

Свойства одного объекта (скаляр) определенного типа часто отличаются от свойств коллекции объектов одного типа.
Например, у каждой службы есть свойство **DisplayName** , но коллекция служб не имеет свойства **DisplayName** .

Следующая команда возвращает значение свойства **DisplayName** службы "аудиосрв".

```powershell
(Get-Service Audiosrv).DisplayName
```

```output
Windows Audio
```

Начиная с PowerShell 3,0, PowerShell пытается предотвратить ошибки скрипта, возникающие в результате различных свойств скалярных объектов и коллекций. Та же команда возвращает значение свойства **DisplayName** каждой службы, которая `Get-Service` возвращает.

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

При отправке коллекции, но при запросе свойства, которое существует только для отдельных ("скалярных") объектов, PowerShell возвращает значение этого свойства для каждого объекта в коллекции.

Все коллекции имеют свойство **Count** , которое возвращает количество объектов в коллекции.

```powershell
(Get-Service).Count
```

```output
176
```

Начиная с PowerShell 3,0, при запросе свойства Count или length нулевых объектов или одного объекта PowerShell возвращает правильное значение.

```powershell
(Get-Service Audiosrv).Count
```

```output
1
```

Если свойство существует для отдельных объектов и коллекции, то возвращается только свойство коллекции.

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

Эта возможность также действует для методов скалярных объектов и коллекций. Дополнительные сведения см. в разделе [about_Methods](about_methods.md).

## <a name="see-also"></a>См. также статью

[about_Methods](about_Methods.md)

[about_Objects](about_Objects.md)

[Get-Member](xref:Microsoft.PowerShell.Utility.Get-Member)

[Select-Object](xref:Microsoft.PowerShell.Utility.Select-Object)

[Format-List](xref:Microsoft.PowerShell.Utility.Format-List)

