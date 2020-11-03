---
description: Описание использования классов для создания собственных пользовательских типов.
keywords: powershell,командлет
Locale: en-US
ms.date: 09/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_classes?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Classes
ms.openlocfilehash: e4e3379c18b8e63e5c494b71485d6dab5c7689f2
ms.sourcegitcommit: 16d62a98449e3ddaf8d7c65bc1848ede1fd8a3e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2020
ms.locfileid: "93230650"
---
# <a name="about-classes"></a><span data-ttu-id="27993-104">О классах</span><span class="sxs-lookup"><span data-stu-id="27993-104">About Classes</span></span>

## <a name="short-description"></a><span data-ttu-id="27993-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="27993-105">Short description</span></span>
<span data-ttu-id="27993-106">Описание использования классов для создания собственных пользовательских типов.</span><span class="sxs-lookup"><span data-stu-id="27993-106">Describes how you can use classes to create your own custom types.</span></span>

## <a name="long-description"></a><span data-ttu-id="27993-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="27993-107">Long description</span></span>

<span data-ttu-id="27993-108">PowerShell 5,0 добавляет формальный синтаксис для определения классов и других определяемых пользователем типов.</span><span class="sxs-lookup"><span data-stu-id="27993-108">PowerShell 5.0 adds a formal syntax to define classes and other user-defined types.</span></span> <span data-ttu-id="27993-109">Добавление классов позволяет разработчикам и ИТ-специалистам использовать PowerShell для более широкого спектра вариантов использования.</span><span class="sxs-lookup"><span data-stu-id="27993-109">The addition of classes enables developers and IT professionals to embrace PowerShell for a wider range of use cases.</span></span> <span data-ttu-id="27993-110">Она упрощает разработку артефактов PowerShell и ускоряет покрытие областей управления.</span><span class="sxs-lookup"><span data-stu-id="27993-110">It simplifies development of PowerShell artifacts and accelerates coverage of management surfaces.</span></span>

<span data-ttu-id="27993-111">Объявление класса — это схема, используемая для создания экземпляров объектов во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="27993-111">A class declaration is a blueprint used to create instances of objects at run time.</span></span> <span data-ttu-id="27993-112">При определении класса имя класса является именем типа.</span><span class="sxs-lookup"><span data-stu-id="27993-112">When you define a class, the class name is the name of the type.</span></span> <span data-ttu-id="27993-113">Например, если объявить класс с именем **Device** и инициализировать переменную `$dev` для нового экземпляра **устройства** , `$dev` то объект или экземпляр типа **Device** .</span><span class="sxs-lookup"><span data-stu-id="27993-113">For example, if you declare a class named **Device** and initialize a variable `$dev` to a new instance of **Device** , `$dev` is an object or instance of type **Device** .</span></span> <span data-ttu-id="27993-114">Каждый экземпляр **устройства** может иметь разные значения в своих свойствах.</span><span class="sxs-lookup"><span data-stu-id="27993-114">Each instance of **Device** can have different values in its properties.</span></span>

## <a name="supported-scenarios"></a><span data-ttu-id="27993-115">Поддерживаемые сценарии</span><span class="sxs-lookup"><span data-stu-id="27993-115">Supported scenarios</span></span>

- <span data-ttu-id="27993-116">Определение пользовательских типов в PowerShell с помощью знакомой семантики объектно-ориентированного программирования, такой как классы, свойства, методы, наследование и т. д.</span><span class="sxs-lookup"><span data-stu-id="27993-116">Define custom types in PowerShell using familiar object-oriented programming semantics like classes, properties, methods, inheritance, etc.</span></span>
- <span data-ttu-id="27993-117">Типы отладки с использованием языка PowerShell.</span><span class="sxs-lookup"><span data-stu-id="27993-117">Debug types using the PowerShell language.</span></span>
- <span data-ttu-id="27993-118">Создание и обработку исключений с помощью формальных механизмов.</span><span class="sxs-lookup"><span data-stu-id="27993-118">Generate and handle exceptions using formal mechanisms.</span></span>
- <span data-ttu-id="27993-119">Определите ресурсы DSC и связанные с ними типы с помощью языка PowerShell.</span><span class="sxs-lookup"><span data-stu-id="27993-119">Define DSC resources and their associated types by using the PowerShell language.</span></span>

## <a name="syntax"></a><span data-ttu-id="27993-120">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="27993-120">Syntax</span></span>

<span data-ttu-id="27993-121">Классы объявляются с помощью следующего синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="27993-121">Classes are declared using the following syntax:</span></span>

```syntax
class <class-name> [: [<base-class>][,<interface-list]] {
    [[<attribute>] [hidden] [static] <property-definition> ...]
    [<class-name>([<constructor-argument-list>])
      {<constructor-statement-list>} ...]
    [[<attribute>] [hidden] [static] <method-definition> ...]
}
```

<span data-ttu-id="27993-122">Экземпляры классов создаются с помощью любого из следующих синтаксисов:</span><span class="sxs-lookup"><span data-stu-id="27993-122">Classes are instantiated using either of the following syntaxes:</span></span>

```syntax
[$<variable-name> =] New-Object -TypeName <class-name> [
  [-ArgumentList] <constructor-argument-list>]
```

```syntax
[$<variable-name> =] [<class-name>]::new([<constructor-argument-list>])
```

> [!NOTE]
> <span data-ttu-id="27993-123">При использовании `[<class-name>]::new()` синтаксиса скобки вокруг имени класса являются обязательными.</span><span class="sxs-lookup"><span data-stu-id="27993-123">When using the `[<class-name>]::new()` syntax, brackets around the class name are mandatory.</span></span> <span data-ttu-id="27993-124">Скобки обозначают определение типа для PowerShell.</span><span class="sxs-lookup"><span data-stu-id="27993-124">The brackets signal a type definition for PowerShell.</span></span>

### <a name="example-syntax-and-usage"></a><span data-ttu-id="27993-125">Пример синтаксиса и использования</span><span class="sxs-lookup"><span data-stu-id="27993-125">Example syntax and usage</span></span>

<span data-ttu-id="27993-126">В этом примере показан минимальный синтаксис, необходимый для создания используемого класса.</span><span class="sxs-lookup"><span data-stu-id="27993-126">This example shows the minimum syntax needed to create a usable class.</span></span>

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

## <a name="class-properties"></a><span data-ttu-id="27993-127">Свойства класса</span><span class="sxs-lookup"><span data-stu-id="27993-127">Class properties</span></span>

<span data-ttu-id="27993-128">Свойства являются переменными, объявленными в области видимости класса.</span><span class="sxs-lookup"><span data-stu-id="27993-128">Properties are variables declared at class scope.</span></span> <span data-ttu-id="27993-129">Свойство может иметь любой встроенный тип или экземпляр другого класса.</span><span class="sxs-lookup"><span data-stu-id="27993-129">A property may be of any built-in type or an instance of another class.</span></span> <span data-ttu-id="27993-130">Классы не имеют ограничений на количество свойств, которые у них есть.</span><span class="sxs-lookup"><span data-stu-id="27993-130">Classes have no restriction in the number of properties they have.</span></span>

### <a name="example-class-with-simple-properties"></a><span data-ttu-id="27993-131">Пример класса с простыми свойствами</span><span class="sxs-lookup"><span data-stu-id="27993-131">Example class with simple properties</span></span>

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

### <a name="example-complex-types-in-class-properties"></a><span data-ttu-id="27993-132">Примеры сложных типов в свойствах класса</span><span class="sxs-lookup"><span data-stu-id="27993-132">Example complex types in class properties</span></span>

<span data-ttu-id="27993-133">В этом примере определяется пустой класс **стойки** с помощью класса **Device** .</span><span class="sxs-lookup"><span data-stu-id="27993-133">This example defines an empty **Rack** class using the **Device** class.</span></span> <span data-ttu-id="27993-134">В примерах, приведенных ниже, показано, как добавить устройства в стойку и как начать с предварительно загруженной стойки.</span><span class="sxs-lookup"><span data-stu-id="27993-134">The examples, following this one, show how to add devices to the rack and how to start with a pre-loaded rack.</span></span>

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

## <a name="class-methods"></a><span data-ttu-id="27993-135">Методы класса</span><span class="sxs-lookup"><span data-stu-id="27993-135">Class methods</span></span>

<span data-ttu-id="27993-136">Методы определяют действия, которые может выполнить класс.</span><span class="sxs-lookup"><span data-stu-id="27993-136">Methods define the actions that a class can perform.</span></span> <span data-ttu-id="27993-137">Методы могут принимать параметры, предоставляющие входные данные.</span><span class="sxs-lookup"><span data-stu-id="27993-137">Methods may take parameters that provide input data.</span></span> <span data-ttu-id="27993-138">Методы могут возвращать выходные данные.</span><span class="sxs-lookup"><span data-stu-id="27993-138">Methods can return output.</span></span> <span data-ttu-id="27993-139">Данными, возвращаемыми методом, может быть любой определенный тип данных.</span><span class="sxs-lookup"><span data-stu-id="27993-139">Data returned by a method can be any defined data type.</span></span>

<span data-ttu-id="27993-140">При определении метода для класса вы ссылаетесь на текущий объект класса с помощью `$this` автоматической переменной.</span><span class="sxs-lookup"><span data-stu-id="27993-140">When defining a method for a class, you reference the current class object by using the `$this` automatic variable.</span></span> <span data-ttu-id="27993-141">Это позволяет получить доступ к свойствам и другим методам, определенным в текущем классе.</span><span class="sxs-lookup"><span data-stu-id="27993-141">This allows you to access properties and other methods defined in the current class.</span></span>

### <a name="example-simple-class-with-properties-and-methods"></a><span data-ttu-id="27993-142">Пример простого класса со свойствами и методами</span><span class="sxs-lookup"><span data-stu-id="27993-142">Example simple class with properties and methods</span></span>

<span data-ttu-id="27993-143">Расширение класса **Rack** для добавления и удаления устройств или из него.</span><span class="sxs-lookup"><span data-stu-id="27993-143">Extending the **Rack** class to add and remove devices to or from it.</span></span>

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

## <a name="output-in-class-methods"></a><span data-ttu-id="27993-144">Выходные данные в методах класса</span><span class="sxs-lookup"><span data-stu-id="27993-144">Output in class methods</span></span>

<span data-ttu-id="27993-145">Методы должны иметь определенный тип возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="27993-145">Methods should have a return type defined.</span></span> <span data-ttu-id="27993-146">Если метод не возвращает выходные данные, то тип выходных данных должен быть `[void]` .</span><span class="sxs-lookup"><span data-stu-id="27993-146">If a method doesn't return output, then the output type should be `[void]`.</span></span>

<span data-ttu-id="27993-147">В методах класса ни один из объектов не отправляется в конвейер, за исключением тех, которые упоминаются в `return` инструкции.</span><span class="sxs-lookup"><span data-stu-id="27993-147">In class methods, no objects get sent to the pipeline except those mentioned in the `return` statement.</span></span> <span data-ttu-id="27993-148">Нет случайных выходных данных конвейера из кода.</span><span class="sxs-lookup"><span data-stu-id="27993-148">There's no accidental output to the pipeline from the code.</span></span>

> [!NOTE]
> <span data-ttu-id="27993-149">Это существенно отличается от того, как функции PowerShell обработают выходные данные, где все происходит в конвейере.</span><span class="sxs-lookup"><span data-stu-id="27993-149">This is fundamentally different from how PowerShell functions handle output, where everything goes to the pipeline.</span></span>

<span data-ttu-id="27993-150">Неустранимые ошибки, записанные в поток ошибок из метода класса, не передаются через.</span><span class="sxs-lookup"><span data-stu-id="27993-150">Non-terminating errors written to the error stream from inside a class method are not passed through.</span></span> <span data-ttu-id="27993-151">`throw`Для завершения завершающей ошибки необходимо использовать.</span><span class="sxs-lookup"><span data-stu-id="27993-151">You must use `throw` to surface a terminating error.</span></span>
<span data-ttu-id="27993-152">С помощью `Write-*` командлетов вы по-прежнему можете записывать в выходные потоки PowerShell из метода класса.</span><span class="sxs-lookup"><span data-stu-id="27993-152">Using the `Write-*` cmdlets, you can still write to PowerShell's output streams from within a class method.</span></span> <span data-ttu-id="27993-153">Однако следует избегать этого, чтобы метод выдавал объекты, используя только `return` инструкцию.</span><span class="sxs-lookup"><span data-stu-id="27993-153">However, this should be avoided so that the method emits objects using only the `return` statement.</span></span>

### <a name="method-output"></a><span data-ttu-id="27993-154">Выходные данные метода</span><span class="sxs-lookup"><span data-stu-id="27993-154">Method output</span></span>

<span data-ttu-id="27993-155">В этом примере нет случайных выходных данных конвейера из методов класса, за исключением `return` оператора.</span><span class="sxs-lookup"><span data-stu-id="27993-155">This example demonstrates no accidental output to the pipeline from class methods, except on the `return` statement.</span></span>

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

## <a name="constructor"></a><span data-ttu-id="27993-156">Конструктор</span><span class="sxs-lookup"><span data-stu-id="27993-156">Constructor</span></span>

<span data-ttu-id="27993-157">Конструкторы позволяют задавать значения по умолчанию и проверять логику объектов в момент создания экземпляра класса.</span><span class="sxs-lookup"><span data-stu-id="27993-157">Constructors enable you to set default values and validate object logic at the moment of creating the instance of the class.</span></span> <span data-ttu-id="27993-158">Конструкторы имеют то же имя, что и класс.</span><span class="sxs-lookup"><span data-stu-id="27993-158">Constructors have the same name as the class.</span></span> <span data-ttu-id="27993-159">Конструкторы могут иметь аргументы, чтобы инициализировать элементы данных нового объекта.</span><span class="sxs-lookup"><span data-stu-id="27993-159">Constructors might have arguments, to initialize the data members of the new object.</span></span>

<span data-ttu-id="27993-160">В классе может быть определено не менее одного конструктора.</span><span class="sxs-lookup"><span data-stu-id="27993-160">The class can have zero or more constructors defined.</span></span> <span data-ttu-id="27993-161">Если конструктор не определен, классу предоставляется конструктор без параметров по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="27993-161">If no constructor is defined, the class is given a default parameterless constructor.</span></span> <span data-ttu-id="27993-162">Этот конструктор инициализирует все элементы значениями по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="27993-162">This constructor initializes all members to their default values.</span></span> <span data-ttu-id="27993-163">Типам объектов и строкам присваиваются значения NULL.</span><span class="sxs-lookup"><span data-stu-id="27993-163">Object types and strings are given null values.</span></span> <span data-ttu-id="27993-164">При определении конструктора конструктор без параметров по умолчанию не создается.</span><span class="sxs-lookup"><span data-stu-id="27993-164">When you define constructor, no default parameterless constructor is created.</span></span> <span data-ttu-id="27993-165">Создайте конструктор без параметров, если он необходим.</span><span class="sxs-lookup"><span data-stu-id="27993-165">Create a parameterless constructor if one is needed.</span></span>

### <a name="constructor-basic-syntax"></a><span data-ttu-id="27993-166">Базовый синтаксис конструктора</span><span class="sxs-lookup"><span data-stu-id="27993-166">Constructor basic syntax</span></span>

<span data-ttu-id="27993-167">В этом примере класс Device определен со свойствами и конструктором.</span><span class="sxs-lookup"><span data-stu-id="27993-167">In this example, the Device class is defined with properties and a constructor.</span></span>
<span data-ttu-id="27993-168">Чтобы использовать этот класс, пользователю необходимо предоставить значения для параметров, перечисленных в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="27993-168">To use this class, the user is required to provide values for the parameters listed in the constructor.</span></span>

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

### <a name="example-with-multiple-constructors"></a><span data-ttu-id="27993-169">Пример с несколькими конструкторами</span><span class="sxs-lookup"><span data-stu-id="27993-169">Example with multiple constructors</span></span>

<span data-ttu-id="27993-170">В этом примере класс **Device** определен со свойствами, конструктором по умолчанию и конструктором для инициализации экземпляра.</span><span class="sxs-lookup"><span data-stu-id="27993-170">In this example, the **Device** class is defined with properties, a default constructor, and a constructor to initialize the instance.</span></span>

<span data-ttu-id="27993-171">Конструктор по умолчанию задает для **торговой марки** значение **undefine** , а **model** и **Vendor-SKU —** со значениями NULL.</span><span class="sxs-lookup"><span data-stu-id="27993-171">The default constructor sets the **brand** to **Undefined** , and leaves **model** and **vendor-sku** with null values.</span></span>

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

## <a name="hidden-attribute"></a><span data-ttu-id="27993-172">Скрытый атрибут</span><span class="sxs-lookup"><span data-stu-id="27993-172">Hidden attribute</span></span>

<span data-ttu-id="27993-173">`hidden`Атрибут скрывает свойство или метод.</span><span class="sxs-lookup"><span data-stu-id="27993-173">The `hidden` attribute hides a property or method.</span></span> <span data-ttu-id="27993-174">Свойство или метод по-прежнему доступны для пользователя и доступны во всех областях, в которых объект доступен.</span><span class="sxs-lookup"><span data-stu-id="27993-174">The property or method is still accessible to the user and is available in all scopes in which the object is available.</span></span> <span data-ttu-id="27993-175">Скрытые члены скрыты от `Get-Member` командлета и не могут быть отображены с помощью заполнения нажатием клавиши TAB или IntelliSense вне определения класса.</span><span class="sxs-lookup"><span data-stu-id="27993-175">Hidden members are hidden from the `Get-Member` cmdlet and can't be displayed using tab completion or IntelliSense outside the class definition.</span></span>

<span data-ttu-id="27993-176">Дополнительные сведения см. в разделе [About_hidden](About_hidden.md).</span><span class="sxs-lookup"><span data-stu-id="27993-176">For more information, see [About_hidden](About_hidden.md).</span></span>

### <a name="example-using-hidden-attributes"></a><span data-ttu-id="27993-177">Пример с использованием скрытых атрибутов</span><span class="sxs-lookup"><span data-stu-id="27993-177">Example using hidden attributes</span></span>

<span data-ttu-id="27993-178">При создании объекта **стойки** число слотов для устройств является фиксированным значением, которое не должно изменяться в любое время.</span><span class="sxs-lookup"><span data-stu-id="27993-178">When a **Rack** object is created, the number of slots for devices is a fixed value that shouldn't be changed at any time.</span></span> <span data-ttu-id="27993-179">Это значение известно во время создания.</span><span class="sxs-lookup"><span data-stu-id="27993-179">This value is known at creation time.</span></span>

<span data-ttu-id="27993-180">Использование атрибута Hidden позволяет разработчику сократить число слотов и предотвратить непреднамеренное изменение размера стойки.</span><span class="sxs-lookup"><span data-stu-id="27993-180">Using the hidden attribute allows the developer to keep the number of slots hidden and prevents unintentional changes the size of the rack.</span></span>

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

<span data-ttu-id="27993-181">Свойство **слотов** уведомлений не отображается в `$r1` выходных данных.</span><span class="sxs-lookup"><span data-stu-id="27993-181">Notice **Slots** property isn't shown in `$r1` output.</span></span> <span data-ttu-id="27993-182">Однако этот размер был изменен конструктором.</span><span class="sxs-lookup"><span data-stu-id="27993-182">However, the size was changed by the constructor.</span></span>

## <a name="static-attribute"></a><span data-ttu-id="27993-183">Статический атрибут</span><span class="sxs-lookup"><span data-stu-id="27993-183">Static attribute</span></span>

<span data-ttu-id="27993-184">`static`Атрибут определяет свойство или метод, который существует в классе и не требует экземпляра.</span><span class="sxs-lookup"><span data-stu-id="27993-184">The `static` attribute defines a property or a method that exists in the class and needs no instance.</span></span>

<span data-ttu-id="27993-185">Статическое свойство всегда доступно, независимо от создания экземпляра класса.</span><span class="sxs-lookup"><span data-stu-id="27993-185">A static property is always available, independent of class instantiation.</span></span> <span data-ttu-id="27993-186">Статическое свойство является общим для всех экземпляров класса.</span><span class="sxs-lookup"><span data-stu-id="27993-186">A static property is shared across all instances of the class.</span></span> <span data-ttu-id="27993-187">Статический метод всегда доступен.</span><span class="sxs-lookup"><span data-stu-id="27993-187">A static method is available always.</span></span> <span data-ttu-id="27993-188">Все статические свойства в динамическом режиме для всего диапазона сеанса.</span><span class="sxs-lookup"><span data-stu-id="27993-188">All static properties live for the entire session span.</span></span>

### <a name="example-using-static-attributes-and-methods"></a><span data-ttu-id="27993-189">Пример использования статических атрибутов и методов</span><span class="sxs-lookup"><span data-stu-id="27993-189">Example using static attributes and methods</span></span>

<span data-ttu-id="27993-190">Предположим, что в центре обработки данных существуют экземпляры стоек.</span><span class="sxs-lookup"><span data-stu-id="27993-190">Assume the racks instantiated here exist in your data center.</span></span> <span data-ttu-id="27993-191">Итак, вы хотите следить за стойками в коде.</span><span class="sxs-lookup"><span data-stu-id="27993-191">So, you would like to keep track of the racks in your code.</span></span>

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

### <a name="testing-static-property-and-method-exist"></a><span data-ttu-id="27993-192">Тестирование статического свойства и метода существует</span><span class="sxs-lookup"><span data-stu-id="27993-192">Testing static property and method exist</span></span>

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

<span data-ttu-id="27993-193">Обратите внимание, что число стоек увеличивается при каждом запуске этого примера.</span><span class="sxs-lookup"><span data-stu-id="27993-193">Notice that the number of racks increases each time you run this example.</span></span>

## <a name="property-validation-attributes"></a><span data-ttu-id="27993-194">Атрибуты проверки свойства</span><span class="sxs-lookup"><span data-stu-id="27993-194">Property validation attributes</span></span>

<span data-ttu-id="27993-195">Атрибуты проверки позволяют проверить, что значения, присвоенные свойствам, соответствуют определенным требованиям.</span><span class="sxs-lookup"><span data-stu-id="27993-195">Validation attributes allow you to test that values given to properties meet defined requirements.</span></span> <span data-ttu-id="27993-196">Проверка активируется в момент назначения значения.</span><span class="sxs-lookup"><span data-stu-id="27993-196">Validation is triggered the moment that the value is assigned.</span></span> <span data-ttu-id="27993-197">См. [about_functions_advanced_parameters](about_functions_advanced_parameters.md).</span><span class="sxs-lookup"><span data-stu-id="27993-197">See [about_functions_advanced_parameters](about_functions_advanced_parameters.md).</span></span>

### <a name="example-using-validation-attributes"></a><span data-ttu-id="27993-198">Пример с использованием атрибутов проверки</span><span class="sxs-lookup"><span data-stu-id="27993-198">Example using validation attributes</span></span>

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

## <a name="inheritance-in-powershell-classes"></a><span data-ttu-id="27993-199">Наследование в классах PowerShell</span><span class="sxs-lookup"><span data-stu-id="27993-199">Inheritance in PowerShell classes</span></span>

<span data-ttu-id="27993-200">Класс можно расширить путем создания нового класса, производного от существующего класса.</span><span class="sxs-lookup"><span data-stu-id="27993-200">You can extend a class by creating a new class that derives from an existing class.</span></span> <span data-ttu-id="27993-201">Производный класс наследует свойства базового класса.</span><span class="sxs-lookup"><span data-stu-id="27993-201">The derived class inherits the properties of the base class.</span></span> <span data-ttu-id="27993-202">При необходимости можно добавлять или переопределять методы и свойства.</span><span class="sxs-lookup"><span data-stu-id="27993-202">You can add or override methods and properties as required.</span></span>

<span data-ttu-id="27993-203">PowerShell не поддерживает множественное наследование.</span><span class="sxs-lookup"><span data-stu-id="27993-203">PowerShell does not support multiple inheritance.</span></span> <span data-ttu-id="27993-204">Классы не могут наследовать более чем от одного класса.</span><span class="sxs-lookup"><span data-stu-id="27993-204">Classes cannot inherit from more than one class.</span></span> <span data-ttu-id="27993-205">Однако для этой цели можно использовать интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="27993-205">However, you can use interfaces for that purpose.</span></span>

<span data-ttu-id="27993-206">Реализация наследования определяется `:` оператором; это означает расширение этого класса или реализация этих интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="27993-206">Inheritance implementation is defined by the `:` operator; which means to extend this class or implements these interfaces.</span></span> <span data-ttu-id="27993-207">Производный класс всегда должен быть крайним левым в объявлении класса.</span><span class="sxs-lookup"><span data-stu-id="27993-207">The derived class should always be leftmost in the class declaration.</span></span>

### <a name="example-using-simple-inheritance-syntax"></a><span data-ttu-id="27993-208">Пример использования простого синтаксиса наследования</span><span class="sxs-lookup"><span data-stu-id="27993-208">Example using simple inheritance syntax</span></span>

<span data-ttu-id="27993-209">В этом примере показан простой синтаксис наследования класса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="27993-209">This example shows the simple PowerShell class inheritance syntax.</span></span>

```powershell
Class Derived : Base {...}
```

<span data-ttu-id="27993-210">В этом примере показано наследование с помощью объявления интерфейса, поступающего после базового класса.</span><span class="sxs-lookup"><span data-stu-id="27993-210">This example shows inheritance with an interface declaration coming after the base class.</span></span>

```powershell
Class Derived : Base, Interface {...}
```

### <a name="example-of-simple-inheritance-in-powershell-classes"></a><span data-ttu-id="27993-211">Пример простого наследования в классах PowerShell</span><span class="sxs-lookup"><span data-stu-id="27993-211">Example of simple inheritance in PowerShell classes</span></span>

<span data-ttu-id="27993-212">В этом примере классы **стоек** и **устройств** , используемые в предыдущих примерах, лучше всего определяются с помощью: избежать повторов свойств, лучше выровняйте общие свойства и повторно использовать общую бизнес-логику.</span><span class="sxs-lookup"><span data-stu-id="27993-212">In this example the **Rack** and **Device** classes used in the previous examples are better defined to: avoid property repetitions, better align common properties, and reuse common business logic.</span></span>

<span data-ttu-id="27993-213">Большинство объектов в центре обработки данных являются ресурсами компании, что имеет смысл начать их отслеживание как ресурсов.</span><span class="sxs-lookup"><span data-stu-id="27993-213">Most objects in the data center are company assets, which makes sense to start tracking them as assets.</span></span> <span data-ttu-id="27993-214">Типы устройств определяются `DeviceType` перечислением. Дополнительные сведения о перечислениях см. в [about_Enum](about_Enum.md) .</span><span class="sxs-lookup"><span data-stu-id="27993-214">Device types are defined by the `DeviceType` enumeration, see [about_Enum](about_Enum.md) for details on enumerations.</span></span>

<span data-ttu-id="27993-215">В нашем примере мы только определим и. `Rack` `ComputeServer` оба расширения `Device` класса.</span><span class="sxs-lookup"><span data-stu-id="27993-215">In our example, we're only defining `Rack` and `ComputeServer`; both extensions to the `Device` class.</span></span>

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

### <a name="calling-base-class-constructors"></a><span data-ttu-id="27993-216">Вызов конструкторов базового класса</span><span class="sxs-lookup"><span data-stu-id="27993-216">Calling base class constructors</span></span>

<span data-ttu-id="27993-217">Чтобы вызвать конструктор базового класса из подкласса, добавьте `base` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="27993-217">To invoke a base class constructor from a subclass, add the `base` keyword.</span></span>

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

### <a name="invoke-base-class-methods"></a><span data-ttu-id="27993-218">Вызов методов базового класса</span><span class="sxs-lookup"><span data-stu-id="27993-218">Invoke base class methods</span></span>

<span data-ttu-id="27993-219">Чтобы переопределить существующие методы в подклассах, объявите методы с использованием того же имени и сигнатуры.</span><span class="sxs-lookup"><span data-stu-id="27993-219">To override existing methods in subclasses, declare methods using the same name and signature.</span></span>

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

<span data-ttu-id="27993-220">Чтобы вызвать методы базового класса из переопределенных реализаций, приведите к базовому классу ([BaseClass] $this) при вызове.</span><span class="sxs-lookup"><span data-stu-id="27993-220">To call base class methods from overridden implementations, cast to the base class ([baseclass]$this) on invocation.</span></span>

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

### <a name="inheriting-from-interfaces"></a><span data-ttu-id="27993-221">Наследование от интерфейсов</span><span class="sxs-lookup"><span data-stu-id="27993-221">Inheriting from interfaces</span></span>

<span data-ttu-id="27993-222">Классы PowerShell могут реализовывать интерфейс, используя тот же синтаксис наследования, который используется для расширения базовых классов.</span><span class="sxs-lookup"><span data-stu-id="27993-222">PowerShell classes can implement an interface using the same inheritance syntax used to extend base classes.</span></span> <span data-ttu-id="27993-223">Поскольку интерфейсы допускают множественное наследование, класс PowerShell, реализующий интерфейс, может наследовать от нескольких типов, разделяя имена типов после двоеточия ( `:` ) с запятыми ( `,` ).</span><span class="sxs-lookup"><span data-stu-id="27993-223">Because interfaces allow multiple inheritance, a PowerShell class implementing an interface may inherit from multiple types, by separating the type names after the colon (`:`) with commas (`,`).</span></span> <span data-ttu-id="27993-224">Класс PowerShell, реализующий интерфейс, должен реализовать все члены этого интерфейса.</span><span class="sxs-lookup"><span data-stu-id="27993-224">A PowerShell class that implements an interface must implement all the members of that interface.</span></span> <span data-ttu-id="27993-225">Пропуск членов интерфейса реализации вызывает ошибку времени синтаксического анализа в скрипте.</span><span class="sxs-lookup"><span data-stu-id="27993-225">Omitting the implemention interface members causes a parse-time error in the script.</span></span>

> [!NOTE]
> <span data-ttu-id="27993-226">В настоящее время PowerShell не поддерживает объявление новых интерфейсов в скрипте PowerShell.</span><span class="sxs-lookup"><span data-stu-id="27993-226">PowerShell does not currently support declaring new interfaces in PowerShell script.</span></span>

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

## <a name="importing-classes-from-a-powershell-module"></a><span data-ttu-id="27993-227">Импорт классов из модуля PowerShell</span><span class="sxs-lookup"><span data-stu-id="27993-227">Importing classes from a PowerShell module</span></span>

<span data-ttu-id="27993-228">`Import-Module` и `#requires` инструкция импортирует только функции, псевдонимы и переменные модуля, как определено модулем.</span><span class="sxs-lookup"><span data-stu-id="27993-228">`Import-Module` and the `#requires` statement only import the module functions, aliases, and variables, as defined by the module.</span></span> <span data-ttu-id="27993-229">Классы не импортируются.</span><span class="sxs-lookup"><span data-stu-id="27993-229">Classes are not imported.</span></span> <span data-ttu-id="27993-230">`using module`Оператор импортирует классы, определенные в модуле.</span><span class="sxs-lookup"><span data-stu-id="27993-230">The `using module` statement imports the classes defined in the module.</span></span> <span data-ttu-id="27993-231">Если модуль не загружен в текущем сеансе, выполнение `using` инструкции завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="27993-231">If the module isn't loaded in the current session, the `using` statement fails.</span></span> <span data-ttu-id="27993-232">Дополнительные сведения об `using` инструкции см. в разделе [about_Using](about_Using.md).</span><span class="sxs-lookup"><span data-stu-id="27993-232">For more information about the `using` statement, see [about_Using](about_Using.md).</span></span>

## <a name="the-psreference-type-is-not-supported-with-class-members"></a><span data-ttu-id="27993-233">Тип Псреференце не поддерживается для членов класса</span><span class="sxs-lookup"><span data-stu-id="27993-233">The PSReference type is not supported with class members</span></span>

<span data-ttu-id="27993-234">`[ref]`Не удается автоматически использовать приведение типа к члену класса.</span><span class="sxs-lookup"><span data-stu-id="27993-234">Using the `[ref]` type-cast with a class member silently fails.</span></span> <span data-ttu-id="27993-235">API-интерфейсы, использующие `[ref]` Параметры, нельзя использовать с членами класса.</span><span class="sxs-lookup"><span data-stu-id="27993-235">APIs that use `[ref]` parameters cannot be used with class members.</span></span> <span data-ttu-id="27993-236">**Псреференце** был разработан для поддержки COM-объектов.</span><span class="sxs-lookup"><span data-stu-id="27993-236">The **PSReference** was designed to support COM objects.</span></span> <span data-ttu-id="27993-237">Объекты COM содержат случаи, когда необходимо передать значение в по ссылке.</span><span class="sxs-lookup"><span data-stu-id="27993-237">COM objects have cases where you need to pass a value in by reference.</span></span>

<span data-ttu-id="27993-238">Дополнительные сведения о типе см `[ref]` . в разделе [класс псреференце](/dotnet/api/system.management.automation.psreference).</span><span class="sxs-lookup"><span data-stu-id="27993-238">For more information about the `[ref]` type, see [PSReference Class](/dotnet/api/system.management.automation.psreference).</span></span>

## <a name="see-also"></a><span data-ttu-id="27993-239">См. также статью</span><span class="sxs-lookup"><span data-stu-id="27993-239">See also</span></span>

- [<span data-ttu-id="27993-240">About_hidden</span><span class="sxs-lookup"><span data-stu-id="27993-240">About_hidden</span></span>](About_hidden.md)
- [<span data-ttu-id="27993-241">about_Enum</span><span class="sxs-lookup"><span data-stu-id="27993-241">about_Enum</span></span>](about_Enum.md)
- [<span data-ttu-id="27993-242">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="27993-242">about_Language_Keywords</span></span>](about_language_keywords.md)
- [<span data-ttu-id="27993-243">about_Methods</span><span class="sxs-lookup"><span data-stu-id="27993-243">about_Methods</span></span>](about_methods.md)
- [<span data-ttu-id="27993-244">about_Using</span><span class="sxs-lookup"><span data-stu-id="27993-244">about_Using</span></span>](about_using.md)
