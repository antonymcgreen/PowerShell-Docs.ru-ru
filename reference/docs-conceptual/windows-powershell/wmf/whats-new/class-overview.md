---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
title: Создание настраиваемых типов с помощью классов PowerShell
ms.openlocfilehash: c2c50fb65ce4931fcf6ae529b4146df391c831c4
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2020
ms.locfileid: "83809010"
---
# <a name="creating-custom-types-using-powershell-classes"></a>Создание настраиваемых типов с помощью классов PowerShell

В PowerShell 5.0 появилась возможность определения классов и других определяемых пользователем типов с использованием формального синтаксиса и семантики, как и в других объектно-ориентированных языках программирования. Целью этого шага является расширение вариантов использования PowerShell, доступных разработчикам и ИТ-специалистам, упрощение разработки артефактов PowerShell (например, ресурсов DSC) и ускорение освоения поверхностей управления.

## <a name="supported-scenarios-in-this-release"></a>Поддерживаемые сценарии в этом выпуске

- Определение ресурсов DSC и связанных с ними типов с помощью языка PowerShell
- Определение настраиваемых типов в PowerShell с помощью знакомых конструкций объектно-ориентированного программирования, таких как классы, свойства, методы и т. п.
- Поддержка наследования с помощью класса в PowerShell и базового ресурса DSC класса
- Отладка типов с помощью языка PowerShell
- Создание и обработка исключений с помощью формальных механизмов и на нужном уровне

## <a name="declare-base-class"></a>Объявление базового класса

Класс PowerShell можно объявить в качестве базового типа для другого класса PowerShell.

```powershell
class bar
{
   [int]foo()
       {
           return 100500
       }
}

class baz : bar {}

[baz]::new().foo() # return 100500
```

Кроме того, можно использовать существующие типы .NET Framework в качестве базовых классов:

```powershell
class MyIntList : system.collections.generic.list[int]
{

}

$list = [MyIntList]::new()

$list.Add(100)

$list[0] # return 100
```

### <a name="call-base-class-constructor"></a>Вызов конструктора базовых классов

Чтобы вызвать конструктор базовых классов из подкласса, используйте ключевое слово **base**:

```powershell
class A
{
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

Если базовый класс имеет конструктор по умолчанию (без параметров), явный вызов конструктора можно опустить:

```powershell
class C : B
{
    C([int]$c) {}
}
```

### <a name="call-base-class-method"></a>Вызов метода базового класса

Можно переопределить существующие методы в подклассах. Для этого объявите методы, используя те же имя и сигнатуру:

```powershell
class baseClass
{
    [int]foo() {return 100500}
}

class childClass1 : baseClass
{
    [int]foo() {return 200600}
}

[childClass1]::new().foo() # return 200600
```

Для вызова методов базового класса из переопределенных реализаций выполните приведение к базовому классу (`[baseClass]$this`) при вызове:

```powershell
class childClass2 : baseClass
{
    [int]foo()
    {
        return 3 * ([baseClass]$this).foo()
    }
}

[childClass2]::new().foo() # return 301500
```

Все методы PowerShell являются виртуальными. Вы можете скрыть невиртуальные методы .NET в подклассе, используя тот же синтаксис, что и для переопределения: просто объявите методы, используя те же имя и сигнатуру.

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

### <a name="declare-implemented-interface"></a>Объявление реализованного интерфейса

Реализованные интерфейсы можно объявить после базовых типов или сразу после двоеточия (:), если базовый тип не указан. Все имена типов следует разделять запятыми. Это похоже на синтаксис C#.

```powershell
class MyComparable : system.IComparable
{
    [int] CompareTo([object] $obj)
    {
        return 0;
    }
}

class MyComparableBar : bar, system.IComparable
{
    [int] CompareTo([object] $obj)
    {
        return 0;
    }
}
```

## <a name="new-language-features-in-powershell-50"></a>Новые возможности языка в PowerShell 5.0

В PowerShell 5.0 появились следующие новые элементы языка для PowerShell:

### <a name="class-keyword"></a>Ключевое слово Class

Ключевое слово `class` определяет новый класс. Это подлинный тип .NET Framework. Члены класса являются открытыми, но только в рамках области модуля. Вы не можете ссылаться на имя типа в виде строки (например, `New-Object` не работает), а также использовать литерал типа (например, `[MyClass]`) за пределами файла скрипта или модуля, где определен этот класс.

```powershell
class MyClass
{
    ...
}
```

### <a name="enum-keyword-and-enumerations"></a>Ключевое слово Enum и перечисления

Добавлена поддержка ключевого слова `enum`, где символ новой строки используется в качестве разделителя. Сейчас нельзя определить перечислитель относительно самого себя. Тем не менее перечисление можно инициализировать относительно другого перечисления, как показано в следующем примере. Кроме того, нельзя задать базовый тип (всегда `[int]`).

```powershell
enum Color2
{
    Yellow = [Color]::Blue
}
```

Значение перечислителя должно быть константой времени анализа. Его нельзя задать как результат вызванной команды.

```powershell
enum MyEnum
{
    Enum1
    Enum2
    Enum3 = 42
    Enum4 = [int]::MaxValue
}
```

Перечисления поддерживают арифметические операции, как показано в следующем примере:

```powershell
enum SomeEnum { Max = 42 }
enum OtherEnum { Max = [SomeEnum]::Max + 1 }
```

### <a name="import-dscresource"></a>Import-DscResource

Теперь `Import-DscResource` — это динамическое ключевое слово. PowerShell анализирует корневой модуль указанного модуля, выполняя поиск классов, которые содержат атрибут **DscResource**.

### <a name="implementingassembly"></a>ImplementingAssembly

В **ModuleInfo** добавлено новое поле **ImplementingAssembly**. Ему присваивается динамическая сборка, созданная для модуля сценариев, если скрипт определяет классы, или загруженная сборка для двоичных модулей. Оно не задано, когда **ModuleType** имеет значение **Manifest**.

Отражение поля **ImplementingAssembly** обнаруживает ресурсы в модуле. Это означает, что можно обнаруживать ресурсы, созданные в PowerShell или в любых других управляемых языках.

Поля с инициализаторами:

```powershell
[int] $i = 5
```

`Static` поддерживается. Он действует как атрибут, также как и ограничения типов. Его можно указать в любом порядке.

```powershell
static [int] $count = 0
```

Тип не является обязательным.

```powershell
$s = "hello"
```

Все члены являются открытыми.

### <a name="constructors-and-instantiation"></a>Конструкторы и создание экземпляров

У классов PowerShell могут быть конструкторы. Имя конструктора совпадает с именем класса. Конструкторы могут быть перегружены. Поддерживаются статические конструкторы. Свойства с выражениями инициализации инициализируются перед выполнением любого кода в конструкторе. Статические свойства инициализируются до основной части статического конструктора, а свойства экземпляра инициализируются до основной части нестатического конструктора. В настоящее время не существует синтаксис для вызова конструктора из другого конструктора (такой как синтаксис C\# ": this()"). Обходной путь заключается в определении общего метода `Init()`.

#### <a name="creating-instances"></a>Создание экземпляров

> [!NOTE]
> В PowerShell 5.0 `New-Object` не работает с классами, определенными в PowerShell. Кроме того, имя типа отображается только лексически, то есть оно не отображается за пределами модуля или скрипта, определяющего класс. Функции могут возвращать экземпляры класса, определенного в PowerShell. Эти экземпляры работают за пределами модуля или скрипта.

1. Создание экземпляров с помощью конструктора по умолчанию.

   ```powershell
   $a = [MyClass]::new()
   ```

1. Вызов конструктора с параметром:

   ```powershell
   $b = [MyClass]::new(42)
   ```

1. Передача массива в конструктор с несколькими параметрами.

   ```powershell
   $c = [MyClass]::new(@(42,43,44), "Hello")
   ```

Псевдостатический метод `new()` работает с типами .NET, как показано в следующем примере.

```powershell
[hashtable]::new()
```

#### <a name="discovering-constructors"></a>Обнаружение конструкторов

Теперь можно просмотреть перегрузки конструктора с помощью `Get-Member` или так, как показано в этом примере:

```powershell
PS> [hashtable]::new
OverloadDefinitions
-------------------
hashtable new()
hashtable new(int capacity)
hashtable new(int capacity, float loadFactor)
```

`Get-Member -Static` выводит список конструкторов, чтобы перегрузки можно было просматривать как и любой другой метод. Производительность этого синтаксиса также значительно выше по сравнению с `New-Object`.

### <a name="methods"></a>Методы

Метод класса PowerShell реализуется как **ScriptBlock**, имеющий только конечный блок. Все методы являются открытыми. Ниже приведен пример определения метода с именем **DoSomething**.

```powershell
class MyClass
{
    DoSomething($x)
    {
        $this._doSomething($x) # method syntax
    }
    private _doSomething($a) {}
}
```

Вызов метода:

```powershell
$b = [MyClass]::new()
$b.DoSomething(42)
```

Кроме того, поддерживаются перегруженные методы.

### <a name="properties"></a>Свойства

Все свойства являются открытыми. Для свойств требуется точка с запятой или новая строка. Если тип объекта не указан, тип свойства является объектом.

Свойства, использующие атрибуты проверки или преобразования аргументов (например, `[ValidateSet("aaa")]`) работают должным образом.

### <a name="hidden"></a>Скрытый

Добавлено новое ключевое слово `Hidden`. `Hidden` может применяться к свойствам и методам (включая конструкторы).

Члены Hidden являются открытыми, но отображаются в выходных данных `Get-Member` только при использовании параметра `-Force`. Элементы Hidden не учитываются при заполнении нажатием клавиши TAB или использовании Intellisense, если только такая операция не выполняется в классе, определяющем элемент Hidden.

Добавлен новый атрибут **System.Management.Automation.HiddenAttribute**, чтобы код C\# мог иметь ту же семантику в PowerShell.

### <a name="return-types"></a>Типы возвращаемых данных

Тип возвращаемого значения является контрактом. Возвращаемое значение преобразуется к ожидаемому типу. Если тип возвращаемого значения не указан, ему присваивается значение **void**. Потоковая передача объектов отсутствует. Записать объекты в конвейер специально или случайно невозможно.

### <a name="attributes"></a>Атрибуты

Добавлены два новых атрибута — **DscResource** и **DscProperty**.

### <a name="lexical-scoping-of-variables"></a>Лексическая область переменных

Ниже приведен пример того, как работает лексическая область в этом выпуске.

```powershell
$d = 42 # Script scope

function bar
{
    $d = 0 # Function scope
    [MyClass]::DoSomething()
}

class MyClass
{
    static [object] DoSomething()
    {
        return $d # error, not found dynamically
        return $script:d # no error
        $d = $script:d
        return $d # no error, found lexically
    }
}

$v = bar
$v -eq $d # true
```

## <a name="end-to-end-example"></a>Комплексный пример

Следующий пример создает несколько новых пользовательских классов для реализации языка динамических таблиц стилей (DSL) HTML. Затем пример добавляет вспомогательные функции для создания определенных типов элементов в рамках класса элементов, таких как стили заголовков и таблицы, так как типы нельзя использовать за пределами области действия модуля.

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
        $text += $this.Head
        $text += "`n</head>`n<body>`n"
        $text += $this.Body -join "`n" # Render all of the body elements
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
    [string] Render() { return "<title>$($this.Title)</title>" }
    [string] ToString() { return $this.Render() }
}

class Element
{
    [string] $Tag
    [string] $Text
    [hashtable] $Attributes
    [string] Render() {
        $attributesText= ""
        if ($this.Attributes)
        {
            foreach ($attr in $this.Attributes.Keys)
            {
                #BUGBUG - need to validate keys against attribute
                $attributesText += " $attr=`"$($this.Attributes[$attr])\`""
            }
        }
        return "<$($this.tag)${attributesText}>$($this.text)</$($this.tag)>`n"
    }
[string] ToString() { return $this.Render() }
}

#
# Helper functions for creating specific element types on top of the classes.
# These are required because types aren't visible outside of the module.
#

function H1 { [Element] @{ Tag = "H1" ; Text = $args.foreach{$_} -join " " }}
function H2 { [Element] @{ Tag = "H2" ; Text = $args.foreach{$_} -join " " }}
function H3 { [Element] @{ Tag = "H3" ; Text = $args.foreach{$_} -join " " }}
function P { [Element] @{ Tag = "P" ; Text = $args.foreach{$_} -join " " }}
function B { [Element] @{ Tag = "B" ; Text = $args.foreach{$_} -join " " }}
function I { [Element] @{ Tag = "I" ; Text = $args.foreach{$_} -join " " }}
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
$bodyText += $Properties.foreach{TH $_}
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
function TH { ([Element] @{ Tag = "TH" ; Text = $args.foreach{$_} -join " " }) }
function TR { ([Element] @{ Tag = "TR" ; Text = $args.foreach{$_} -join " " }) }
function TD { ([Element] @{ Tag = "TD" ; Text = $args.foreach{$_} -join " " }) }
function Style

{
    return [Element] @{
        Tag = "style"
        Text = "$args"
    }
}

# Takes a hash table, casts it to and HTML document
# and then returns the resulting type.
#
function Html ([HTML] $doc) { return $doc }
```
