---
description: Описание использования классов для создания собственных пользовательских типов.
keywords: powershell,командлет
Locale: en-US
ms.date: 09/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_classes?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Classes
ms.openlocfilehash: 3b4222752492d13d07aba14b2b4f157edc319353
ms.sourcegitcommit: 16d62a98449e3ddaf8d7c65bc1848ede1fd8a3e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2020
ms.locfileid: "93230649"
---
# <a name="about-classes"></a>О классах

## <a name="short-description"></a>Краткое описание
Описание использования классов для создания собственных пользовательских типов.

## <a name="long-description"></a>Подробное описание

PowerShell 5,0 добавляет формальный синтаксис для определения классов и других определяемых пользователем типов. Добавление классов позволяет разработчикам и ИТ-специалистам использовать PowerShell для более широкого спектра вариантов использования. Она упрощает разработку артефактов PowerShell и ускоряет покрытие областей управления.

Объявление класса — это схема, используемая для создания экземпляров объектов во время выполнения. При определении класса имя класса является именем типа. Например, если объявить класс с именем **Device** и инициализировать переменную `$dev` для нового экземпляра **устройства** , `$dev` то объект или экземпляр типа **Device** . Каждый экземпляр **устройства** может иметь разные значения в своих свойствах.

## <a name="supported-scenarios"></a>Поддерживаемые сценарии

- Определение пользовательских типов в PowerShell с помощью знакомой семантики объектно-ориентированного программирования, такой как классы, свойства, методы, наследование и т. д.
- Типы отладки с использованием языка PowerShell.
- Создание и обработку исключений с помощью формальных механизмов.
- Определите ресурсы DSC и связанные с ними типы с помощью языка PowerShell.

## <a name="syntax"></a>Синтаксис

Классы объявляются с помощью следующего синтаксиса:

```syntax
class <class-name> [: [<base-class>][,<interface-list]] {
    [[<attribute>] [hidden] [static] <property-definition> ...]
    [<class-name>([<constructor-argument-list>])
      {<constructor-statement-list>} ...]
    [[<attribute>] [hidden] [static] <method-definition> ...]
}
```

Экземпляры классов создаются с помощью любого из следующих синтаксисов:

```syntax
[$<variable-name> =] New-Object -TypeName <class-name> [
  [-ArgumentList] <constructor-argument-list>]
```

```syntax
[$<variable-name> =] [<class-name>]::new([<constructor-argument-list>])
```

> [!NOTE]
> При использовании `[<class-name>]::new()` синтаксиса скобки вокруг имени класса являются обязательными. Скобки обозначают определение типа для PowerShell.

### <a name="example-syntax-and-usage"></a>Пример синтаксиса и использования

В этом примере показан минимальный синтаксис, необходимый для создания используемого класса.

```powershell
class Device {
    [string]$Brand
}

$dev = [Device]::new()
$dev.Brand = "Microsoft"
$dev
```

```Output
Brand
-----
Microsoft
```

## <a name="class-properties"></a>Свойства класса

Свойства являются переменными, объявленными в области видимости класса. Свойство может иметь любой встроенный тип или экземпляр другого класса. Классы не имеют ограничений на количество свойств, которые у них есть.

### <a name="example-class-with-simple-properties"></a>Пример класса с простыми свойствами

```powershell
class Device {
    [string]$Brand
    [string]$Model
    [string]$VendorSku
}

$device = [Device]::new()
$device.Brand = "Microsoft"
$device.Model = "Surface Pro 4"
$device.VendorSku = "5072641000"

$device
```

```Output
Brand     Model         VendorSku
-----     -----         ---------
Microsoft Surface Pro 4 5072641000
```

### <a name="example-complex-types-in-class-properties"></a>Примеры сложных типов в свойствах класса

В этом примере определяется пустой класс **стойки** с помощью класса **Device** . В примерах, приведенных ниже, показано, как добавить устройства в стойку и как начать с предварительно загруженной стойки.

```powershell
class Device {
    [string]$Brand
    [string]$Model
    [string]$VendorSku
}

class Rack {
    [string]$Brand
    [string]$Model
    [string]$VendorSku
    [string]$AssetId
    [Device[]]$Devices = [Device[]]::new(8)

}

$rack = [Rack]::new()

$rack
```

```Output

Brand     :
Model     :
VendorSku :
AssetId   :
Devices   : {$null, $null, $null, $null...}


```

## <a name="class-methods"></a>Методы класса

Методы определяют действия, которые может выполнить класс. Методы могут принимать параметры, предоставляющие входные данные. Методы могут возвращать выходные данные. Данными, возвращаемыми методом, может быть любой определенный тип данных.

При определении метода для класса вы ссылаетесь на текущий объект класса с помощью `$this` автоматической переменной. Это позволяет получить доступ к свойствам и другим методам, определенным в текущем классе.

### <a name="example-simple-class-with-properties-and-methods"></a>Пример простого класса со свойствами и методами

Расширение класса **Rack** для добавления и удаления устройств или из него.

```powershell
class Device {
    [string]$Brand
    [string]$Model
    [string]$VendorSku

    [string]ToString(){
        return ("{0}|{1}|{2}" -f $this.Brand, $this.Model, $this.VendorSku)
    }
}

class Rack {
    [int]$Slots = 8
    [string]$Brand
    [string]$Model
    [string]$VendorSku
    [string]$AssetId
    [Device[]]$Devices = [Device[]]::new($this.Slots)

    [void] AddDevice([Device]$dev, [int]$slot){
        ## Add argument validation logic here
        $this.Devices[$slot] = $dev
    }

    [void]RemoveDevice([int]$slot){
        ## Add argument validation logic here
        $this.Devices[$slot] = $null
    }

    [int[]] GetAvailableSlots(){
        [int]$i = 0
        return @($this.Devices.foreach{ if($_ -eq $null){$i}; $i++})
    }
}

$rack = [Rack]::new()

$surface = [Device]::new()
$surface.Brand = "Microsoft"
$surface.Model = "Surface Pro 4"
$surface.VendorSku = "5072641000"

$rack.AddDevice($surface, 2)

$rack
$rack.GetAvailableSlots()
```

```Output

Slots     : 8
Brand     :
Model     :
VendorSku :
AssetId   :
Devices   : {$null, $null, Microsoft|Surface Pro 4|5072641000, $null...}

0
1
3
4
5
6
7

```

## <a name="output-in-class-methods"></a>Выходные данные в методах класса

Методы должны иметь определенный тип возвращаемого значения. Если метод не возвращает выходные данные, то тип выходных данных должен быть `[void]` .

В методах класса ни один из объектов не отправляется в конвейер, за исключением тех, которые упоминаются в `return` инструкции. Нет случайных выходных данных конвейера из кода.

> [!NOTE]
> Это существенно отличается от того, как функции PowerShell обработают выходные данные, где все происходит в конвейере.

Неустранимые ошибки, записанные в поток ошибок из метода класса, не передаются через. `throw`Для завершения завершающей ошибки необходимо использовать.
С помощью `Write-*` командлетов вы по-прежнему можете записывать в выходные потоки PowerShell из метода класса. Однако следует избегать этого, чтобы метод выдавал объекты, используя только `return` инструкцию.

### <a name="method-output"></a>Выходные данные метода

В этом примере нет случайных выходных данных конвейера из методов класса, за исключением `return` оператора.

```powershell
class FunWithIntegers
{
    [int[]]$Integers = 0..10

    [int[]]GetOddIntegers(){
        return $this.Integers.Where({ ($_ % 2) })
    }

    [void] GetEvenIntegers(){
        # this following line doesn't go to the pipeline
        $this.Integers.Where({ ($_ % 2) -eq 0})
    }

    [string]SayHello(){
        # this following line doesn't go to the pipeline
        "Good Morning"

        # this line goes to the pipeline
        return "Hello World"
    }
}

$ints = [FunWithIntegers]::new()
$ints.GetOddIntegers()
$ints.GetEvenIntegers()
$ints.SayHello()
```

```Output
1
3
5
7
9
Hello World

```

## <a name="constructor"></a>Конструктор

Конструкторы позволяют задавать значения по умолчанию и проверять логику объектов в момент создания экземпляра класса. Конструкторы имеют то же имя, что и класс. Конструкторы могут иметь аргументы, чтобы инициализировать элементы данных нового объекта.

В классе может быть определено не менее одного конструктора. Если конструктор не определен, классу предоставляется конструктор без параметров по умолчанию. Этот конструктор инициализирует все элементы значениями по умолчанию. Типам объектов и строкам присваиваются значения NULL. При определении конструктора конструктор без параметров по умолчанию не создается. Создайте конструктор без параметров, если он необходим.

### <a name="constructor-basic-syntax"></a>Базовый синтаксис конструктора

В этом примере класс Device определен со свойствами и конструктором.
Чтобы использовать этот класс, пользователю необходимо предоставить значения для параметров, перечисленных в конструкторе.

```powershell
class Device {
    [string]$Brand
    [string]$Model
    [string]$VendorSku

    Device(
        [string]$b,
        [string]$m,
        [string]$vsk
    ){
        $this.Brand = $b
        $this.Model = $m
        $this.VendorSku = $vsk
    }
}

[Device]$surface = [Device]::new("Microsoft", "Surface Pro 4", "5072641000")

$surface
```

```Output
Brand     Model         VendorSku
-----     -----         ---------
Microsoft Surface Pro 4 5072641000
```

### <a name="example-with-multiple-constructors"></a>Пример с несколькими конструкторами

В этом примере класс **Device** определен со свойствами, конструктором по умолчанию и конструктором для инициализации экземпляра.

Конструктор по умолчанию задает для **торговой марки** значение **undefine** , а **model** и **Vendor-SKU —** со значениями NULL.

```powershell
class Device {
    [string]$Brand
    [string]$Model
    [string]$VendorSku

    Device(){
        $this.Brand = 'Undefined'
    }

    Device(
        [string]$b,
        [string]$m,
        [string]$vsk
    ){
        $this.Brand = $b
        $this.Model = $m
        $this.VendorSku = $vsk
    }
}

[Device]$somedevice = [Device]::new()
[Device]$surface = [Device]::new("Microsoft", "Surface Pro 4", "5072641000")

$somedevice
$surface
```

```Output
Brand       Model           VendorSku
-----       -----           ---------
Undefined
Microsoft   Surface Pro 4   5072641000
```

## <a name="hidden-attribute"></a>Скрытый атрибут

`hidden`Атрибут скрывает свойство или метод. Свойство или метод по-прежнему доступны для пользователя и доступны во всех областях, в которых объект доступен. Скрытые члены скрыты от `Get-Member` командлета и не могут быть отображены с помощью заполнения нажатием клавиши TAB или IntelliSense вне определения класса.

Дополнительные сведения см. в разделе [About_hidden](About_hidden.md).

### <a name="example-using-hidden-attributes"></a>Пример с использованием скрытых атрибутов

При создании объекта **стойки** число слотов для устройств является фиксированным значением, которое не должно изменяться в любое время. Это значение известно во время создания.

Использование атрибута Hidden позволяет разработчику сократить число слотов и предотвратить непреднамеренное изменение размера стойки.

```powershell
class Device {
    [string]$Brand
    [string]$Model
}

class Rack {
    [int] hidden $Slots = 8
    [string]$Brand
    [string]$Model
    [Device[]]$Devices = [Device[]]::new($this.Slots)

    Rack ([string]$b, [string]$m, [int]$capacity){
        ## argument validation here

        $this.Brand = $b
        $this.Model = $m
        $this.Slots = $capacity

        ## reset rack size to new capacity
        $this.Devices = [Device[]]::new($this.Slots)
    }
}

[Rack]$r1 = [Rack]::new("Microsoft", "Surface Pro 4", 16)

$r1
$r1.Devices.Length
$r1.Slots
```

```Output
Brand     Model         Devices
-----     -----         -------
Microsoft Surface Pro 4 {$null, $null, $null, $null...}
16
16
```

Свойство **слотов** уведомлений не отображается в `$r1` выходных данных. Однако этот размер был изменен конструктором.

## <a name="static-attribute"></a>Статический атрибут

`static`Атрибут определяет свойство или метод, который существует в классе и не требует экземпляра.

Статическое свойство всегда доступно, независимо от создания экземпляра класса. Статическое свойство является общим для всех экземпляров класса. Статический метод всегда доступен. Все статические свойства в динамическом режиме для всего диапазона сеанса.

### <a name="example-using-static-attributes-and-methods"></a>Пример использования статических атрибутов и методов

Предположим, что в центре обработки данных существуют экземпляры стоек. Итак, вы хотите следить за стойками в коде.

```powershell
class Device {
    [string]$Brand
    [string]$Model
}

class Rack {
    hidden [int] $Slots = 8
    static [Rack[]]$InstalledRacks = @()
    [string]$Brand
    [string]$Model
    [string]$AssetId
    [Device[]]$Devices = [Device[]]::new($this.Slots)

    Rack ([string]$b, [string]$m, [string]$id, [int]$capacity){
        ## argument validation here

        $this.Brand = $b
        $this.Model = $m
        $this.AssetId = $id
        $this.Slots = $capacity

        ## reset rack size to new capacity
        $this.Devices = [Device[]]::new($this.Slots)

        ## add rack to installed racks
        [Rack]::InstalledRacks += $this
    }

    static [void]PowerOffRacks(){
        foreach ($rack in [Rack]::InstalledRacks) {
            Write-Warning ("Turning off rack: " + ($rack.AssetId))
        }
    }
}
```

### <a name="testing-static-property-and-method-exist"></a>Тестирование статического свойства и метода существует

```
PS> [Rack]::InstalledRacks.Length
0

PS> [Rack]::PowerOffRacks()

PS> (1..10) | ForEach-Object {
>>   [Rack]::new("Adatum Corporation", "Standard-16",
>>     $_.ToString("Std0000"), 16)
>> } > $null

PS> [Rack]::InstalledRacks.Length
10

PS> [Rack]::InstalledRacks[3]
Brand              Model       AssetId Devices
-----              -----       ------- -------
Adatum Corporation Standard-16 Std0004 {$null, $null, $null, $null...}

PS> [Rack]::PowerOffRacks()
WARNING: Turning off rack: Std0001
WARNING: Turning off rack: Std0002
WARNING: Turning off rack: Std0003
WARNING: Turning off rack: Std0004
WARNING: Turning off rack: Std0005
WARNING: Turning off rack: Std0006
WARNING: Turning off rack: Std0007
WARNING: Turning off rack: Std0008
WARNING: Turning off rack: Std0009
WARNING: Turning off rack: Std0010
```

Обратите внимание, что число стоек увеличивается при каждом запуске этого примера.

## <a name="property-validation-attributes"></a>Атрибуты проверки свойства

Атрибуты проверки позволяют проверить, что значения, присвоенные свойствам, соответствуют определенным требованиям. Проверка активируется в момент назначения значения. См. [about_functions_advanced_parameters](about_functions_advanced_parameters.md).

### <a name="example-using-validation-attributes"></a>Пример с использованием атрибутов проверки

```powershell
class Device {
    [ValidateNotNullOrEmpty()][string]$Brand
    [ValidateNotNullOrEmpty()][string]$Model
}

[Device]$dev = [Device]::new()

Write-Output "Testing dev"
$dev

$dev.Brand = ""
```

```Output
Testing dev

Brand Model
----- -----

Exception setting "Brand": "The argument is null or empty. Provide an
argument that is not null or empty, and then try the command again."
At C:\tmp\Untitled-5.ps1:11 char:1
+ $dev.Brand = ""
+ ~~~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [], SetValueInvocationException
    + FullyQualifiedErrorId : ExceptionWhenSetting
```

## <a name="inheritance-in-powershell-classes"></a>Наследование в классах PowerShell

Класс можно расширить путем создания нового класса, производного от существующего класса. Производный класс наследует свойства базового класса. При необходимости можно добавлять или переопределять методы и свойства.

PowerShell не поддерживает множественное наследование. Классы не могут наследовать более чем от одного класса. Однако для этой цели можно использовать интерфейсы.

Реализация наследования определяется `:` оператором; это означает расширение этого класса или реализация этих интерфейсов. Производный класс всегда должен быть крайним левым в объявлении класса.

### <a name="example-using-simple-inheritance-syntax"></a>Пример использования простого синтаксиса наследования

В этом примере показан простой синтаксис наследования класса PowerShell.

```powershell
Class Derived : Base {...}
```

В этом примере показано наследование с помощью объявления интерфейса, поступающего после базового класса.

```powershell
Class Derived : Base, Interface {...}
```

### <a name="example-of-simple-inheritance-in-powershell-classes"></a>Пример простого наследования в классах PowerShell

В этом примере классы **стоек** и **устройств** , используемые в предыдущих примерах, лучше всего определяются с помощью: избежать повторов свойств, лучше выровняйте общие свойства и повторно использовать общую бизнес-логику.

Большинство объектов в центре обработки данных являются ресурсами компании, что имеет смысл начать их отслеживание как ресурсов. Типы устройств определяются `DeviceType` перечислением. Дополнительные сведения о перечислениях см. в [about_Enum](about_Enum.md) .

В нашем примере мы только определим и. `Rack` `ComputeServer` оба расширения `Device` класса.

```powershell
enum DeviceType {
    Undefined = 0
    Compute = 1
    Storage = 2
    Networking = 4
    Communications = 8
    Power = 16
    Rack = 32
}

class Asset {
    [string]$Brand
    [string]$Model
}

class Device : Asset {
    hidden [DeviceType]$devtype = [DeviceType]::Undefined
    [string]$Status

    [DeviceType] GetDeviceType(){
        return $this.devtype
    }
}

class ComputeServer : Device {
    hidden [DeviceType]$devtype = [DeviceType]::Compute
    [string]$ProcessorIdentifier
    [string]$Hostname
}

class Rack : Device {
    hidden [DeviceType]$devtype = [DeviceType]::Rack
    hidden [int]$Slots = 8

    [string]$Datacenter
    [string]$Location
    [Device[]]$Devices = [Device[]]::new($this.Slots)

    Rack (){
        ## Just create the default rack with 8 slots
    }

    Rack ([int]$s){
        ## Add argument validation logic here
        $this.Devices = [Device[]]::new($s)
    }

    [void] AddDevice([Device]$dev, [int]$slot){
        ## Add argument validation logic here
        $this.Devices[$slot] = $dev
    }

    [void] RemoveDevice([int]$slot){
        ## Add argument validation logic here
        $this.Devices[$slot] = $null
    }
}

$FirstRack = [Rack]::new(16)
$FirstRack.Status = "Operational"
$FirstRack.Datacenter = "PNW"
$FirstRack.Location = "F03R02.J10"

(0..15).ForEach({
    $ComputeServer = [ComputeServer]::new()
    $ComputeServer.Brand = "Fabrikam, Inc."       ## Inherited from Asset
    $ComputeServer.Model = "Fbk5040"              ## Inherited from Asset
    $ComputeServer.Status = "Installed"           ## Inherited from Device
    $ComputeServer.ProcessorIdentifier = "x64"    ## ComputeServer
    $ComputeServer.Hostname = ("r1s" + $_.ToString("000")) ## ComputeServer
    $FirstRack.AddDevice($ComputeServer, $_)
  })

$FirstRack
$FirstRack.Devices
```

```Output
Datacenter : PNW
Location   : F03R02.J10
Devices    : {r1s000, r1s001, r1s002, r1s003...}
Status     : Operational
Brand      :
Model      :

ProcessorIdentifier : x64
Hostname            : r1s000
Status              : Installed
Brand               : Fabrikam, Inc.
Model               : Fbk5040

ProcessorIdentifier : x64
Hostname            : r1s001
Status              : Installed
Brand               : Fabrikam, Inc.
Model               : Fbk5040

<... content truncated here for brevity ...>

ProcessorIdentifier : x64
Hostname            : r1s015
Status              : Installed
Brand               : Fabrikam, Inc.
Model               : Fbk5040
```

### <a name="calling-base-class-constructors"></a>Вызов конструкторов базового класса

Чтобы вызвать конструктор базового класса из подкласса, добавьте `base` ключевое слово.

```powershell
class Person {
    [int]$Age

    Person([int]$a)
    {
        $this.Age = $a
    }
}

class Child : Person
{
    [string]$School

    Child([int]$a, [string]$s ) : base($a) {
        $this.School = $s
    }
}

[Child]$littleone = [Child]::new(10, "Silver Fir Elementary School")

$littleone.Age
```

```Output

10
```

### <a name="invoke-base-class-methods"></a>Вызов методов базового класса

Чтобы переопределить существующие методы в подклассах, объявите методы с использованием того же имени и сигнатуры.

```powershell
class BaseClass
{
    [int]days() {return 1}
}
class ChildClass1 : BaseClass
{
    [int]days () {return 2}
}

[ChildClass1]::new().days()
```

```Output

2
```

Чтобы вызвать методы базового класса из переопределенных реализаций, приведите к базовому классу ([BaseClass] $this) при вызове.

```powershell
class BaseClass
{
    [int]days() {return 1}
}
class ChildClass1 : BaseClass
{
    [int]days () {return 2}
    [int]basedays() {return ([BaseClass]$this).days()}
}

[ChildClass1]::new().days()
[ChildClass1]::new().basedays()
```

```Output

2
1
```

### <a name="inheriting-from-interfaces"></a>Наследование от интерфейсов

Классы PowerShell могут реализовывать интерфейс, используя тот же синтаксис наследования, который используется для расширения базовых классов. Поскольку интерфейсы допускают множественное наследование, класс PowerShell, реализующий интерфейс, может наследовать от нескольких типов, разделяя имена типов после двоеточия ( `:` ) с запятыми ( `,` ). Класс PowerShell, реализующий интерфейс, должен реализовать все члены этого интерфейса. Пропуск членов интерфейса реализации вызывает ошибку времени синтаксического анализа в скрипте.

> [!NOTE]
> В настоящее время PowerShell не поддерживает объявление новых интерфейсов в скрипте PowerShell.

```powershell
class MyComparable : System.IComparable
{
    [int] CompareTo([object] $obj)
    {
        return 0;
    }
}

class MyComparableBar : bar, System.IComparable
{
    [int] CompareTo([object] $obj)
    {
        return 0;
    }
}
```

## <a name="importing-classes-from-a-powershell-module"></a>Импорт классов из модуля PowerShell

`Import-Module` и `#requires` инструкция импортирует только функции, псевдонимы и переменные модуля, как определено модулем. Классы не импортируются. `using module`Оператор импортирует классы, определенные в модуле. Если модуль не загружен в текущем сеансе, выполнение `using` инструкции завершается ошибкой. Дополнительные сведения об `using` инструкции см. в разделе [about_Using](about_Using.md).

## <a name="the-psreference-type-is-not-supported-with-class-members"></a>Тип Псреференце не поддерживается для членов класса

`[ref]`Не удается автоматически использовать приведение типа к члену класса. API-интерфейсы, использующие `[ref]` Параметры, нельзя использовать с членами класса. **Псреференце** был разработан для поддержки COM-объектов. Объекты COM содержат случаи, когда необходимо передать значение в по ссылке.

Дополнительные сведения о типе см `[ref]` . в разделе [класс псреференце](/dotnet/api/system.management.automation.psreference).

## <a name="see-also"></a>См. также статью

- [About_hidden](About_hidden.md)
- [about_Enum](about_Enum.md)
- [about_Language_Keywords](about_language_keywords.md)
- [about_Methods](about_methods.md)
- [about_Using](about_using.md)
