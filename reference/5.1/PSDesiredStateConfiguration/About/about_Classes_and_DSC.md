---
description: Описывает, как можно использовать классы для разработки в PowerShell с помощью настройки требуемого состояния (DSC).
keywords: powershell,командлет
Locale: en-US
ms.date: 1/11/2019
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/about/about_classes_and_dsc?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Classes_and_DSC
ms.openlocfilehash: 21a013bb817367dd2a11cc0826263d0f3203796b
ms.sourcegitcommit: cc72c40315fd2981d3009b335accbfa52d57640c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/30/2020
ms.locfileid: "96349835"
---
# <a name="about-classes-and-desired-state-configuration"></a>Сведения о классах и настройке требуемого состояния

## <a name="short-description"></a>Краткое описание

Описывает, как можно использовать классы для разработки в PowerShell с помощью настройки требуемого состояния (DSC).

## <a name="long-description"></a>Подробное описание

Начиная с Windows PowerShell 5,0, язык был добавлен для определения классов и других определяемых пользователем типов с помощью формального синтаксиса и семантики, аналогичные другим объектно-ориентированным языкам программирования. Целью является предоставление разработчикам и ИТ-специалистам возможности использовать Windows PowerShell для более широкого спектра вариантов использования, упростить разработку артефактов PowerShell, таких как ресурсы DSC, и ускорить работу областей управления.

## <a name="supported-scenarios"></a>Поддерживаемые сценарии

Поддерживаются следующие сценарии:

- Определите ресурсы DSC и связанные с ними типы с помощью языка PowerShell.
- Определение пользовательских типов в PowerShell с помощью знакомых конструкций объектно-ориентированного программирования, таких как классы, свойства, методы и наследование.
- Типы отладки с помощью языка PowerShell.
- Создавайте и обрабатывайте исключения с помощью формальных механизмов и на нужном уровне.

## <a name="define-dsc-resources-with-classes"></a>Определение ресурсов DSC с помощью классов

Помимо изменений в синтаксисе основные различия между определенным классом ресурсом DSC и поставщиком ресурса DSC командлета являются следующими элементами:

- Файл формата управляющих объектов (MOF) не требуется.
- Вложенная папка DSCResource в папке модуля не требуется.
- Файл модуля PowerShell может содержать несколько классов ресурсов DSC.

## <a name="create-a-class-defined-dsc-resource-provider"></a>Создание поставщика ресурсов DSC, определяемого классом

В следующем примере показан поставщик ресурсов DSC, определяемый классом, который сохраняется как модуль MyDSCResource. PSM1. Необходимо всегда включать ключевое свойство в определяемый классом поставщик ресурсов DSC.

```powershell
enum Ensure
{
    Absent
    Present
}

<#
    This resource manages the file in a specific path.
    [DscResource()] indicates the class is a DSC resource
#>

[DscResource()]
class FileResource
{
    <#
        This property is the fully qualified path to the file that is
        expected to be present or absent.

        The [DscProperty(Key)] attribute indicates the property is a
        key and its value uniquely identifies a resource instance.
        Defining this attribute also means the property is required
        and DSC will ensure a value is set before calling the resource.

        A DSC resource must define at least one key property.
    #>
    [DscProperty(Key)]
    [string]$Path

    <#
        This property indicates if the settings should be present or absent
        on the system. For present, the resource ensures the file pointed
        to by $Path exists. For absent, it ensures the file point to by
        $Path does not exist.

        The [DscProperty(Mandatory)] attribute indicates the property is
        required and DSC will guarantee it is set.

        If Mandatory is not specified or if it is defined as
        Mandatory=$false, the value is not guaranteed to be set when DSC
        calls the resource.  This is appropriate for optional properties.
    #>
    [DscProperty(Mandatory)]
    [Ensure] $Ensure

    <#
        This property defines the fully qualified path to a file that will
        be placed on the system if $Ensure = Present and $Path does not
        exist.

        NOTE: This property is required because [DscProperty(Mandatory)] is
        set.
    #>
    [DscProperty(Mandatory)]
    [string] $SourcePath

    <#
        This property reports the file's create timestamp.

        [DscProperty(NotConfigurable)] attribute indicates the property is
        not configurable in DSC configuration.  Properties marked this way
        are populated by the Get() method to report additional details
        about the resource when it is present.

    #>
    [DscProperty(NotConfigurable)]
    [Nullable[datetime]] $CreationTime

    <#
        This method is equivalent of the Set-TargetResource script function.
        It sets the resource to the desired state.
    #>
    [void] Set()
    {
        $fileExists = $this.TestFilePath($this.Path)
        if($this.ensure -eq [Ensure]::Present)
        {
            if(-not $fileExists)
            {
                $this.CopyFile()
            }
        }
        else
        {
            if($fileExists)
            {
                Write-Verbose -Message "Deleting the file $($this.Path)"
                Remove-Item -LiteralPath $this.Path -Force
            }
        }
    }

    <#

        This method is equivalent of the Test-TargetResource script
        function. It should return True or False, showing whether the
        resource is in a desired state.
    #>
    [bool] Test()
    {
        $present = $this.TestFilePath($this.Path)

        if($this.Ensure -eq [Ensure]::Present)
        {
            return $present
        }
        else
{
            return -not $present
        }
    }

    <#
        This method is equivalent of the Get-TargetResource script function.
        The implementation should use the keys to find appropriate
        resources. This method returns an instance of this class with the
        updated key properties.
    #>
    [FileResource] Get()
    {
        $present = $this.TestFilePath($this.Path)

        if ($present)
        {
            $file = Get-ChildItem -LiteralPath $this.Path
            $this.CreationTime = $file.CreationTime
            $this.Ensure = [Ensure]::Present
        }
        else
        {
            $this.CreationTime = $null
            $this.Ensure = [Ensure]::Absent
        }
        return $this
    }

    <#
        Helper method to check if the file exists and it is correct file
    #>
    [bool] TestFilePath([string] $location)
    {
        $present = $true

        $item = Get-ChildItem -LiteralPath $location -ea Ignore
        if ($null -eq $item)
        {
            $present = $false
        }
        elseif( $item.PSProvider.Name -ne "FileSystem")
        {
            throw "Path $($location) is not a file path."
        }
        elseif($item.PSIsContainer)
        {
            throw "Path $($location) is a directory path."
        }
        return $present
    }

    <#
        Helper method to copy file from source to path
    #>
    [void] CopyFile()
    {
        if(-not $this.TestFilePath($this.SourcePath))
        {
            throw "SourcePath $($this.SourcePath) is not found."
        }

        [System.IO.FileInfo]
        $destFileInfo = new-object System.IO.FileInfo($this.Path)

        if (-not $destFileInfo.Directory.Exists)
        {
            $FullName = $destFileInfo.Directory.FullName
            $Message = "Creating directory $FullName"

            Write-Verbose -Message $Message

            #use CreateDirectory instead of New-Item to avoid code
            # to handle the non-terminating error
            [System.IO.Directory]::CreateDirectory($FullName)
        }

        if(Test-Path -LiteralPath $this.Path -PathType Container)
        {
            throw "Path $($this.Path) is a directory path"
        }

        Write-Verbose -Message "Copying $this.SourcePath to $this.Path"

        #DSC engine catches and reports any error that occurs
        Copy-Item -Path $this.SourcePath -Destination $this.Path -Force
    }
}
```

## <a name="create-a-module-manifest"></a>Создание манифеста модуля

После создания поставщика определенных классом ресурсов DSC и его сохранения в виде модуля создайте манифест для модуля. Чтобы сделать ресурс на основе класса доступным для модуля DSC, необходимо добавить в файл манифеста оператор `DscResourcesToExport`, который указывает модулю, что нужно экспортировать этот ресурс. В этом примере приведенный ниже манифест модуля сохраняется как MyDscResource.psd1.

```powershell
@{

# Script module or binary module file associated with this manifest.
RootModule = 'MyDscResource.psm1'

DscResourcesToExport = 'FileResource'

# Version number of this module.
ModuleVersion = '1.0'

# ID used to uniquely identify this module
GUID = '81624038-5e71-40f8-8905-b1a87afe22d7'

# Author of this module
Author = 'Microsoft Corporation'

# Company or vendor of this module
CompanyName = 'Microsoft Corporation'

# Copyright statement for this module
Copyright = '(c) 2014 Microsoft. All rights reserved.'

# Description of the functionality provided by this module
# Description = ''

# Minimum version of the PowerShell engine required by this module
PowerShellVersion = '5.0'

# Name of the PowerShell host required by this module
# PowerShellHostName = ''

}
```

## <a name="deploy-a-dsc-resource-provider"></a>Развертывание поставщика ресурсов DSC

Разверните новый поставщик ресурсов DSC, создав папку MyDscResource в `$pshome\Modules` или `$env:SystemDrive\ProgramFiles\WindowsPowerShell\Modules` .

Создавать вложенную папку DSCResource не нужно. Скопируйте файлы модуля и его манифеста (MyDscResource.psm1 и MyDscResource.psd1) в папку MyDscResource.

С этого момента вы можете создавать и выполнять сценарий конфигурации, как и любой другой ресурс DSC.

## <a name="create-a-dsc-configuration-script"></a>Создание сценария конфигурации DSC

Сохранив файлы класса и манифеста в структуру папок, как описано выше, вы можете создать конфигурацию, использующую новый ресурс. Следующая конфигурация ссылается на модуль MyDSCResource. Сохраните конфигурацию в виде скрипта MyResource.ps1.

Сведения о запуске конфигурации DSC см. в разделе [Общие сведения о настройке требуемого состояния Windows PowerShell](/powershell/scripting/dsc/overview/dscforengineers).

Перед запуском конфигурации создайте `C:\test.txt` . Конфигурация проверяет, существует ли файл в `c:\test\test.txt` . Если файл не существует, конфигурация копирует файл из `C:\test.txt` .

```powershell
Configuration Test
{
    Import-DSCResource -module MyDscResource
    FileResource file
    {
        Path = "C:\test\test.txt"
        SourcePath = "C:\test.txt"
        Ensure = "Present"
    }
}
Test
Start-DscConfiguration -Wait -Force Test
```

Запустите этот скрипт так же, как любой сценарий настройки DSC. Чтобы запустить конфигурацию, в консоли PowerShell с повышенными привилегиями выполните следующую команду:

`PS C:\test> .\MyResource.ps1`

## <a name="inheritance-in-powershell-classes"></a>Наследование в классах PowerShell

### <a name="declare-base-classes-for-powershell-classes"></a>Объявление базовых классов для классов PowerShell

Класс PowerShell можно объявить как базовый тип для другого класса PowerShell, как показано в следующем примере, в котором **фруктов** является базовым типом для **Apple**.

```powershell
class fruit
{
    [int]sold() {return 100500}
}

class apple : fruit {}
    [apple]::new().sold() # return 100500
```

### <a name="declare-implemented-interfaces-for-powershell-classes"></a>Объявление реализованных интерфейсов для классов PowerShell

Можно объявить реализованные интерфейсы после базовых типов или сразу после двоеточия ( `:` ), если не указан базовый тип. Все имена типов следует разделять запятыми. Это похоже на синтаксис C#.

```powershell
class MyComparable : system.IComparable
{
    [int] CompareTo([object] $obj)
    {
        return 0;
    }
}

class MyComparableTest : test, system.IComparable
{
    [int] CompareTo([object] $obj)
    {
        return 0;
    }
}
```

### <a name="call-base-class-constructors"></a>Вызов конструкторов базового класса

Чтобы вызвать конструктор базового класса из подкласса, добавьте `base` ключевое слово, как показано в следующем примере:

```powershell
class A {
    [int]$a
    A([int]$a)
    {
        $this.a = $a
    }
}

class B : A
{
    B() : base(103) {}
}

    [B]::new().a # return 103
```

Если базовый класс имеет конструктор по умолчанию (без параметров), можно опустить вызов явного конструктора, как показано ниже.

```powershell
class C : B
{
    C([int]$c) {}
}
```

### <a name="call-base-class-methods"></a>Вызов методов базового класса

Можно переопределить существующие методы в подклассах. Чтобы выполнить переопределение, объявите методы с использованием того же имени и сигнатуры.

```powershell
class baseClass
{
    [int]days() {return 100500}
}
class childClass1 : baseClass
{
    [int]days () {return 200600}
}

    [childClass1]::new().days() # return 200600
```

Чтобы вызвать методы базового класса из переопределенных реализаций, приведите к базовому классу `([baseclass]$this)` при вызове.

```powershell
class childClass2 : baseClass
{
    [int]days()
    {
        return 3 * ([baseClass]$this).days()
    }
}

    [childClass2]::new().days() # return 301500
```

Все методы PowerShell являются виртуальными. Вы можете скрыть невиртуальные методы .NET в подклассе, используя тот же синтаксис, что и для переопределения: Declare Methods с тем же именем и сигнатурой.

```powershell
class MyIntList : system.collections.generic.list[int]
{
    # Add is final in system.collections.generic.list
    [void] Add([int]$arg)
    {
        ([system.collections.generic.list[int]]$this).Add($arg * 2)
    }
}

$list = [MyIntList]::new()
$list.Add(100)
$list[0] # return 200
```

### <a name="current-limitations-with-class-inheritance"></a>Текущие ограничения с наследованием классов

Ограничение с наследованием класса заключается в отсутствии синтаксиса объявления интерфейсов в PowerShell.

## <a name="defining-custom-types-in-powershell"></a>Определение пользовательских типов в PowerShell

В Windows PowerShell 5,0 появился ряд языковых элементов.

### <a name="class-keyword"></a>Ключевое слово Class

Определяет новый класс.
`class`Ключевое слово является истинным .NET Framework типом.
Члены класса являются открытыми.

```powershell
class MyClass
{
}
```

### <a name="enum-keyword-and-enumerations"></a>Ключевое слово Enum и перечисления

`enum`Добавлена поддержка ключевого слова, что является критическим изменением. `enum`Разделитель в настоящее время является новой строкой. Обходной путь для тех, кто уже использует, `enum` — Вставить амперсанд ( `&` ) перед словом. Текущие ограничения. невозможно определить перечислитель с точки зрения самого себя, но можно инициализировать `enum` в терминах другого `enum` , как показано в следующем примере:

В настоящее время невозможно указать базовый тип. Базовый тип всегда имеет значение [int].

```powershell
enum Color2
{
    Yellow = [Color]::Blue
}
```

Значение перечислителя должно быть константой времени анализа. Значение перечислителя не может быть результатом вызванной команды.

```powershell
enum MyEnum
{
    Enum1
    Enum2
    Enum3 = 42
    Enum4 = [int]::MaxValue
}
```

`Enum` поддерживает арифметические операции, как показано в следующем примере:

```powershell
enum SomeEnum { Max = 42 }
enum OtherEnum { Max = [SomeEnum]::Max + 1 }
```

### <a name="hidden-keyword"></a>Ключевое слово Hidden

`hidden`Ключевое слово, представленное в Windows PowerShell 5,0, скрывает члены класса от результатов по умолчанию `Get-Member` . Укажите свойство Hidden, как показано в следующей строке:

```powershell
hidden [type] $classmember = <value>
```

Скрытые члены не отображаются при нажатии клавиши TAB или IntelliSense, если завершение не происходит в классе, который определяет скрытый элемент.

Добавлен новый атрибут **System. Management. Automation. хидденаттрибуте**, поэтому код C# может иметь ту же семантику в PowerShell.

Дополнительные сведения см. в разделе [about_Hidden](../../Microsoft.PowerShell.Core/About/about_hidden.md).

### <a name="import-dscresource"></a>Import-DscResource

Теперь `Import-DscResource` — это динамическое ключевое слово. PowerShell анализирует корневой модуль указанного модуля, выполняя поиск классов, которые содержат атрибут DscResource.

### <a name="properties"></a>Свойства

Новое поле, `ImplementingAssembly` Добавлено в `ModuleInfo` . Если скрипт определяет классы или в загруженной сборке для двоичных модулей `ImplementingAssembly` задана динамическая сборка, созданная для модуля скрипта. Оно не задано, когда ModuleType = Manifest.

Отражение в `ImplementingAssembly` поле обнаруживает ресурсы в модуле. Это означает, что можно обнаруживать ресурсы, созданные в PowerShell или в любых других управляемых языках.

Поля с инициализаторами.

`[int] $i = 5`

Поддерживается static и работает как атрибут, аналогично ограничениям типа, поэтому его можно указать в любом порядке.

`static [int] $count = 0`

Тип не является обязательным.

`$s = "hello"`

Все члены являются открытыми. Для свойств требуется точка с запятой или новая строка. Если тип объекта не указан, свойство имеет тип **Object**.

### <a name="constructors-and-instantiation"></a>Конструкторы и создание экземпляров

Классы PowerShell могут иметь конструкторы, имена которых совпадают с именами их классов. Конструкторы могут быть перегружены. Поддерживаются статические конструкторы.
Свойства с выражениями инициализации инициализируются перед выполнением любого кода в конструкторе. Статические свойства инициализируются до основной части статического конструктора, а свойства экземпляра инициализируются до основной части нестатического конструктора. В настоящее время нет синтаксиса для вызова конструктора из другого конструктора, например синтаксиса C#: `": this()")` . Обходной путь заключается в определении общего метода Init.

Ниже приведены способы создания экземпляров классов.

- Создание экземпляров с помощью конструктора по умолчанию. Обратите внимание, что `New-Object` в этом выпуске не поддерживается.

  `$a = [MyClass]::new()`

- Вызов конструктора с параметром.

  `$b = [MyClass]::new(42)`

- Передача массива в конструктор с несколькими параметрами:

  `$c = [MyClass]::new(@(42,43,44), "Hello")`

В этом выпуске имя типа видимо только лексически, то есть оно не видимо за пределами модуля или скрипта, определяющего класс. Функции могут возвращать экземпляры класса, определенного в PowerShell, а экземпляры отлично работают за пределами модуля или скрипта.

`Get-Member` **Статический** параметр перечисляет конструкторы, поэтому можно просматривать перегрузки, как и любые другие методы. Производительность этого синтаксиса также значительно выше по сравнению с `New-Object`.

Псевдостатический метод с именем **new** работает с типами .NET, как показано в следующем примере: `[hashtable]::new()`

Теперь можно просмотреть перегрузки конструктора с помощью `Get-Member` или так, как показано в этом примере:

```powershell
[hashtable]::new
OverloadDefinitions
-------------------
hashtable new()
hashtable new(int capacity)
hashtable new(int capacity, float loadFactor)
```

### <a name="methods"></a>Методы

Метод класса PowerShell реализуется как **ScriptBlock**, имеющий только конечный блок. Все методы являются открытыми. Ниже приведен пример определения метода с именем **DoSomething**.

```powershell
class MyClass
{
    DoSomething($x)
    {
        $this._doSomething($x)       # method syntax
    }
    private _doSomething($a) {}
}
```

### <a name="method-invocation"></a>Вызов метода

Поддерживаются перегруженные методы. Перегруженные методы именуются аналогично существующему методу, но различаются по указанным значениям.

```powershell
$b = [MyClass]::new()
$b.DoSomething(42)
```

### <a name="invocation"></a>Вызов

См. раздел [вызов метода](#method-invocation).

### <a name="attributes"></a>Атрибуты

Добавлены три новых атрибута: `DscResource` , `DscResourceKey` и `DscResourceMandatory` .

### <a name="return-types"></a>Типы возвращаемых данных

Тип возвращаемого значения является контрактом. Возвращаемое значение преобразуется к ожидаемому типу.
Если тип возвращаемого значения не указан, ему присваивается значение void. Потоковая передача объектов и объектов не может быть записана в конвейер намеренно или случайно.

### <a name="lexical-scoping-of-variables"></a>Лексическая область переменных

Ниже приведен пример того, как работает лексическая область в этом выпуске.

```powershell
$d = 42  # Script scope

function bar
{
    $d = 0  # Function scope
    [MyClass]::DoSomething()
}

class MyClass
{
    static [object] DoSomething()
    {
        return $d  # error, not found dynamically
        return $script:d # no error

        $d = $script:d
        return $d # no error, found lexically
    }
}

$v = bar
$v -eq $d # true
```

## <a name="example-create-custom-classes"></a>Пример. Создание пользовательских классов

В следующем примере создается несколько новых пользовательских классов для реализации языка динамических стилей HTML (DSL). В примере добавляются вспомогательные функции для создания конкретных типов элементов как часть класса element, например стили и таблицы заголовков, поскольку типы не могут использоваться вне области действия модуля.

```powershell
# Classes that define the structure of the document
#
class Html
{
    [string] $docType
    [HtmlHead] $Head
    [Element[]] $Body

    [string] Render()
    {
        $text = "<html>`n<head>`n"
        $text += $Head
        $text += "`n</head>`n<body>`n"
        $text += $Body -join "`n" # Render all of the body elements
        $text += "</body>`n</html>"
        return $text
    }
    [string] ToString() { return $this.Render() }
}

class HtmlHead
{
    $Title
    $Base
    $Link
    $Style
    $Meta
    $Script
    [string] Render() { return "<title>$Title</title>" }
    [string] ToString() { return $this.Render() }
}

class Element
{
    [string] $Tag
    [string] $Text
    [hashtable] $Attributes
    [string] Render() {
        $attributesText= ""
        if ($Attributes)
        {
            foreach ($attr in $Attributes.Keys)
            {
                $attributesText = " $attr=`"$($Attributes[$attr])`""
            }
        }

        return "<${tag}${attributesText}>$text</$tag>`n"
    }
    [string] ToString() { return $this.Render() }
}

#
# Helper functions for creating specific element types on top of the classes.
# These are required because types aren't visible outside of the module.
#
function H1 {[Element] @{Tag = "H1"; Text = $args.foreach{$_} -join " "}}
function H2 {[Element] @{Tag = "H2"; Text = $args.foreach{$_} -join " "}}
function H3 {[Element] @{Tag = "H3"; Text = $args.foreach{$_} -join " "}}
function P  {[Element] @{Tag = "P" ; Text = $args.foreach{$_} -join " "}}
function B  {[Element] @{Tag = "B" ; Text = $args.foreach{$_} -join " "}}
function I  {[Element] @{Tag = "I" ; Text = $args.foreach{$_} -join " "}}
function HREF
{
    param (
        $Name,
        $Link
    )

    return [Element] @{
        Tag = "A"
        Attributes = @{ HREF = $link }
        Text = $name
    }
}
function Table
{
    param (
        [Parameter(Mandatory)]
        [object[]]
            $Data,
        [Parameter()]
        [string[]]
            $Properties = "*",
        [Parameter()]
        [hashtable]
            $Attributes = @{ border=2; cellpadding=2; cellspacing=2 }
    )

    $bodyText = ""
    # Add the header tags
    $bodyText +=  $Properties.foreach{TH $_}
    # Add the rows
    $bodyText += foreach ($row in $Data)
                {
                            TR (-join $Properties.Foreach{ TD ($row.$_) } )
                }

    $table = [Element] @{
                Tag = "Table"
                Attributes = $Attributes
                Text = $bodyText
            }
    $table
}
function TH  {([Element] @{Tag="TH"; Text=$args.foreach{$_} -join " "})}
function TR  {([Element] @{Tag="TR"; Text=$args.foreach{$_} -join " "})}
function TD  {([Element] @{Tag="TD"; Text=$args.foreach{$_} -join " "})}

function Style
{
    return  [Element]  @{
        Tag = "style"
        Text = "$args"
    }
}

# Takes a hash table, casts it to and HTML document
# and then returns the resulting type.
#
function Html ([HTML] $doc) { return $doc }
```

## <a name="see-also"></a>См. также раздел

[about_DesiredStateConfiguration](../../Microsoft.PowerShell.Core/About/about_desiredstateconfiguration.md)

[about_Enum](../../Microsoft.PowerShell.Core/About/about_Enum.md)

[about_Hidden](../../Microsoft.PowerShell.Core/About/about_hidden.md)

[about_Language_Keywords](../../Microsoft.PowerShell.Core/About/about_Language_Keywords.md)

[about_Methods](../../Microsoft.PowerShell.Core/About/about_Methods.md)

[Создание пользовательских ресурсов DSC Windows PowerShell](/powershell/scripting/dsc/resources/authoringResource)
