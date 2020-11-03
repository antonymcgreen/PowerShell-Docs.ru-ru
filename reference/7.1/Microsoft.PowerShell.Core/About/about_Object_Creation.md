---
description: Объясняется, как создавать объекты в PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 09/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_object_creation?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Object_Creation
ms.openlocfilehash: 57cc45640879aa80142c27c27a7810dcc5f31a9c
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232717"
---
# <a name="about-object-creation"></a>О создании объектов

## <a name="short-description"></a>Краткое описание

Объясняется, как создавать объекты в PowerShell.

## <a name="long-description"></a>Подробное описание

Вы можете создавать объекты в PowerShell и использовать объекты, созданные в командах и скриптах.

Существует множество способов создания объектов. Этот список не является самым непредсказуемым.

- [New-Object](xref:Microsoft.PowerShell.Utility.New-Object): создает экземпляр объекта .NET Framework или COM-объекта.
- [Import-CSV](xref:Microsoft.PowerShell.Utility.Import-Csv) /
   [ConvertFrom-CSV](xref:Microsoft.PowerShell.Utility.ConvertFrom-Csv): создает пользовательские объекты ( **PSCustomObject** ) из элементов, определенных как значения с разделителями-запятыми.
- [ConvertFrom-JSON](xref:Microsoft.PowerShell.Utility.ConvertFrom-Json): создает пользовательские объекты, определенные в НОТАЦИЯ объектов JavaScript (JSON).
- [ConvertFrom-StringData](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData): создает пользовательские объекты, определенные как пары "ключ — значение".
- [Add-Type (добавить тип)](xref:Microsoft.PowerShell.Utility.Add-Type). позволяет определить класс в сеансе PowerShell, с которым можно создать экземпляр `New-Object` .
- [New-Module](xref:Microsoft.PowerShell.Core.New-Module): параметр **AsCustomObject** создает пользовательский объект, определяемый с помощью блока сценария.
- [Добавить-член](xref:Microsoft.PowerShell.Utility.Add-Member): добавляет свойства в существующие объекты. Можно использовать `Add-Member` для создания пользовательского объекта из простого типа, например `[System.Int32]` .
- [Select-Object](xref:Microsoft.PowerShell.Utility.Select-Object): выбирает свойства объекта. Можно использовать `Select-Object` для создания настраиваемых и вычисляемых свойств для уже созданного объекта.

В этой статье рассматриваются следующие дополнительные методы.

- Путем вызова конструктора типа с помощью статического `new()` метода
- Путем приведения хэш-таблиц имен свойств и значений свойств

## <a name="static-new-method"></a>Статический метод New ()

Все типы .NET имеют `new()` метод, позволяющий более легко создавать экземпляры. Можно также просмотреть все доступные конструкторы для данного типа.

Чтобы просмотреть конструкторы для типа, укажите `new` имя метода после имени типа и нажмите клавишу `<ENTER>` .

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

Теперь можно создать **System. URI** , указав соответствующий конструктор.

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

Чтобы определить, какие типы .NET в данный момент загружены для создания экземпляра, можно использовать следующий пример.

```powershell
[AppDomain]::CurrentDomain.GetAssemblies() |
  ForEach-Object {
    $_.GetExportedTypes() |
      ForEach-Object { $_.FullName }
  }
```

Объекты, созданные с помощью `new()` метода, не могут иметь те же свойства, что и объекты того же типа, которые создаются командлетами PowerShell. Командлеты PowerShell, поставщики и система расширенного типа могут добавлять дополнительные свойства в экземпляр.

Например, Поставщик FileSystem в PowerShell добавляет шесть значений **NoteProperty** в объект **DirectoryInfo** , возвращаемый методом `Get-Item` .

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

При непосредственном создании объекта **DirectoryInfo** он не имеет шести значений **NoteProperty** .

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

Дополнительные сведения о системе расширенных типов см. в разделе [about_Types.ps1XML](about_Types.ps1xml.md).

Эта функция была добавлена в PowerShell 5,0

## <a name="create-objects-from-hash-tables"></a>Создание объектов из хэш-таблиц

Вы можете создать объект из хэш-таблицы свойств и значений свойств.

Синтаксис выглядит следующим образом:

```
[<class-name>]@{
  <property-name>=<property-value>
  <property-name>=<property-value>
}
```

Этот метод работает только для классов, у которых есть конструктор без параметров. Свойства объекта должны быть общедоступными и настраиваемыми.

Эта функция была добавлена в PowerShell версии 3,0

## <a name="create-custom-objects-from-hash-tables"></a>Создание пользовательских объектов из хэш-таблиц

Пользовательские объекты очень полезны и легко создаются с помощью метода хэш-таблицы. Класс **PSCustomObject** разработан специально для этой цели.

Пользовательские объекты — это отличный способ возврата настраиваемых выходных данных из функции или скрипта. Это более полезно, чем возврат форматированных выходных данных, которые не могут быть переформатированы или переданы другим командам.

Команды в `Test-Object function` задают некоторые значения переменных, а затем используют эти значения для создания пользовательского объекта. Этот объект можно увидеть в разделе "пример" `Update-Help` раздела справки по командлетам.

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

Выходные данные этой функции представляют собой коллекцию пользовательских объектов, отформатированных по умолчанию в виде таблицы.

```Output
ModuleName        UICulture      Version
---------         ---------      -------
PSScheduledJob    en-us          3.1.0.0
PSWorkflow        en-us          3.0.0.0
```

Пользователи могут управлять свойствами пользовательских объектов так же, как и со стандартными объектами.

```powershell
(Test-Object).ModuleName
```

```Output
 PSScheduledJob
 PSWorkflow
```

## <a name="create-non-custom-objects-from-hash-tables"></a>Создание ненастраиваемых объектов из хэш-таблиц

Хэш-таблицы также можно использовать для создания объектов для непользовательских классов. При создании объекта для непользовательского класса требуется имя типа с указанием пространства имен, хотя вы можете опустить любой начальный компонент **системного** пространства имен.

Например, следующая команда создает объект параметра сеанса.

```powershell
[System.Management.Automation.Remoting.PSSessionOption]@{
  IdleTimeout=43200000
  SkipCnCheck=$True
}
```

Требования к функции хэш-таблицы, особенно требования к конструктору без параметров, устраняют многие существующие классы. Однако большинство классов _параметров_ PowerShell предназначены для работы с этой функцией, а также с другими очень полезными классами, такими как класс **ProcessStartInfo** .

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

Можно также использовать функцию хэш-таблицы при задании значений параметров. Например, значение параметра **SessionOption** объекта `New-PSSession` .
Командлет может быть хэш-таблицей.

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

## <a name="generic-objects"></a>Универсальные объекты

В PowerShell можно также создавать универсальные объекты. Универсальными шаблонами являются классы, структуры, интерфейсы и методы, которые имеют прототипы (параметры типов) для одного или нескольких типов, которые они хранят или используют.

В следующем примере создается объект **Dictionary** .

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

Дополнительные сведения об универсальных шаблонах см. [в разделе Универсальные шаблоны в .NET](/dotnet/standard/generics).

## <a name="see-also"></a>См. также статью

[about_Objects](about_Objects.md)

[about_Methods](about_Methods.md)

[about_Properties](about_Properties.md)

[about_Pipelines](about_Pipelines.md)

[about_Types.ps1xml](about_Types.ps1xml.md)
