---
ms.date: 06/12/2017
keywords: wmf,powershell,установка
title: Создание настраиваемых типов с помощью классов PowerShell
ms.openlocfilehash: c2c50fb65ce4931fcf6ae529b4146df391c831c4
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "71147844"
---
# <a name="creating-custom-types-using-powershell-classes"></a><span data-ttu-id="71a81-103">Создание настраиваемых типов с помощью классов PowerShell</span><span class="sxs-lookup"><span data-stu-id="71a81-103">Creating Custom Types using PowerShell Classes</span></span>

<span data-ttu-id="71a81-104">В PowerShell 5.0 появилась возможность определения классов и других определяемых пользователем типов с использованием формального синтаксиса и семантики, как и в других объектно-ориентированных языках программирования.</span><span class="sxs-lookup"><span data-stu-id="71a81-104">PowerShell 5.0 added the ability to define classes and other user-defined types using formal syntax and semantics like other object-oriented programming languages.</span></span> <span data-ttu-id="71a81-105">Целью этого шага является расширение вариантов использования PowerShell, доступных разработчикам и ИТ-специалистам, упрощение разработки артефактов PowerShell (например, ресурсов DSC) и ускорение освоения поверхностей управления.</span><span class="sxs-lookup"><span data-stu-id="71a81-105">The goal is to enable developers and IT professionals to embrace PowerShell for a wider range of use cases, simplify development of PowerShell artifacts (such as DSC resources), and accelerate coverage of management surfaces.</span></span>

## <a name="supported-scenarios-in-this-release"></a><span data-ttu-id="71a81-106">Поддерживаемые сценарии в этом выпуске</span><span class="sxs-lookup"><span data-stu-id="71a81-106">Supported scenarios in this release</span></span>

- <span data-ttu-id="71a81-107">Определение ресурсов DSC и связанных с ними типов с помощью языка PowerShell</span><span class="sxs-lookup"><span data-stu-id="71a81-107">Define DSC resources and their associated types by using the PowerShell language</span></span>
- <span data-ttu-id="71a81-108">Определение настраиваемых типов в PowerShell с помощью знакомых конструкций объектно-ориентированного программирования, таких как классы, свойства, методы и т. п.</span><span class="sxs-lookup"><span data-stu-id="71a81-108">Define custom types in PowerShell by using familiar object-oriented programming constructs, such as classes, properties, methods, etc.</span></span>
- <span data-ttu-id="71a81-109">Поддержка наследования с помощью класса в PowerShell и базового ресурса DSC класса</span><span class="sxs-lookup"><span data-stu-id="71a81-109">Inheritance support with class in PowerShell and class base DSC resource</span></span>
- <span data-ttu-id="71a81-110">Отладка типов с помощью языка PowerShell</span><span class="sxs-lookup"><span data-stu-id="71a81-110">Debug types by using the PowerShell language</span></span>
- <span data-ttu-id="71a81-111">Создание и обработка исключений с помощью формальных механизмов и на нужном уровне</span><span class="sxs-lookup"><span data-stu-id="71a81-111">Generate and handle exceptions by using formal mechanisms, and at the right level</span></span>

## <a name="declare-base-class"></a><span data-ttu-id="71a81-112">Объявление базового класса</span><span class="sxs-lookup"><span data-stu-id="71a81-112">Declare Base Class</span></span>

<span data-ttu-id="71a81-113">Класс PowerShell можно объявить в качестве базового типа для другого класса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="71a81-113">You can declare a PowerShell class as a base type for another PowerShell class.</span></span>

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

<span data-ttu-id="71a81-114">Кроме того, можно использовать существующие типы .NET Framework в качестве базовых классов:</span><span class="sxs-lookup"><span data-stu-id="71a81-114">You can also use existing .NET Framework types as base classes:</span></span>

```powershell
class MyIntList : system.collections.generic.list[int]
{

}

$list = [MyIntList]::new()

$list.Add(100)

$list[0] # return 100
```

### <a name="call-base-class-constructor"></a><span data-ttu-id="71a81-115">Вызов конструктора базовых классов</span><span class="sxs-lookup"><span data-stu-id="71a81-115">Call Base Class Constructor</span></span>

<span data-ttu-id="71a81-116">Чтобы вызвать конструктор базовых классов из подкласса, используйте ключевое слово **base**:</span><span class="sxs-lookup"><span data-stu-id="71a81-116">To call a base class constructor from a subclass, use the keyword **base**:</span></span>

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

<span data-ttu-id="71a81-117">Если базовый класс имеет конструктор по умолчанию (без параметров), явный вызов конструктора можно опустить:</span><span class="sxs-lookup"><span data-stu-id="71a81-117">If a base class has a default (no parameter) constructor, you can omit an explicit constructor call:</span></span>

```powershell
class C : B
{
    C([int]$c) {}
}
```

### <a name="call-base-class-method"></a><span data-ttu-id="71a81-118">Вызов метода базового класса</span><span class="sxs-lookup"><span data-stu-id="71a81-118">Call Base Class Method</span></span>

<span data-ttu-id="71a81-119">Можно переопределить существующие методы в подклассах.</span><span class="sxs-lookup"><span data-stu-id="71a81-119">You can override existing methods in subclasses.</span></span> <span data-ttu-id="71a81-120">Для этого объявите методы, используя те же имя и сигнатуру:</span><span class="sxs-lookup"><span data-stu-id="71a81-120">To do this, declare methods by using the same name and signature:</span></span>

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

<span data-ttu-id="71a81-121">Для вызова методов базового класса из переопределенных реализаций выполните приведение к базовому классу (`[baseClass]$this`) при вызове:</span><span class="sxs-lookup"><span data-stu-id="71a81-121">To call base class methods from overridden implementations, cast to the base class (`[baseClass]$this`) on invocation:</span></span>

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

<span data-ttu-id="71a81-122">Все методы PowerShell являются виртуальными.</span><span class="sxs-lookup"><span data-stu-id="71a81-122">All PowerShell methods are virtual.</span></span> <span data-ttu-id="71a81-123">Вы можете скрыть невиртуальные методы .NET в подклассе, используя тот же синтаксис, что и для переопределения: просто объявите методы, используя те же имя и сигнатуру.</span><span class="sxs-lookup"><span data-stu-id="71a81-123">You can hide non-virtual .NET methods in a subclass by using the same syntax as you do for an override, by declaring methods with same name and signature.</span></span>

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

### <a name="declare-implemented-interface"></a><span data-ttu-id="71a81-124">Объявление реализованного интерфейса</span><span class="sxs-lookup"><span data-stu-id="71a81-124">Declare Implemented Interface</span></span>

<span data-ttu-id="71a81-125">Реализованные интерфейсы можно объявить после базовых типов или сразу после двоеточия (:), если базовый тип не указан.</span><span class="sxs-lookup"><span data-stu-id="71a81-125">You can declare implemented interfaces after base types, or immediately after a colon (:), if there is no base type specified.</span></span> <span data-ttu-id="71a81-126">Все имена типов следует разделять запятыми.</span><span class="sxs-lookup"><span data-stu-id="71a81-126">Separate all type names by using commas.</span></span> <span data-ttu-id="71a81-127">Это похоже на синтаксис C#.</span><span class="sxs-lookup"><span data-stu-id="71a81-127">It's similar to C# syntax.</span></span>

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

## <a name="new-language-features-in-powershell-50"></a><span data-ttu-id="71a81-128">Новые возможности языка в PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="71a81-128">New language features in PowerShell 5.0</span></span>

<span data-ttu-id="71a81-129">В PowerShell 5.0 появились следующие новые элементы языка для PowerShell:</span><span class="sxs-lookup"><span data-stu-id="71a81-129">PowerShell 5.0 introduces the following new language elements in PowerShell:</span></span>

### <a name="class-keyword"></a><span data-ttu-id="71a81-130">Ключевое слово Class</span><span class="sxs-lookup"><span data-stu-id="71a81-130">Class keyword</span></span>

<span data-ttu-id="71a81-131">Ключевое слово `class` определяет новый класс.</span><span class="sxs-lookup"><span data-stu-id="71a81-131">The `class` keyword defines a new class.</span></span> <span data-ttu-id="71a81-132">Это подлинный тип .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="71a81-132">This is a true .NET Framework type.</span></span> <span data-ttu-id="71a81-133">Члены класса являются открытыми, но только в рамках области модуля.</span><span class="sxs-lookup"><span data-stu-id="71a81-133">Class members are public, but only public within the module scope.</span></span> <span data-ttu-id="71a81-134">Вы не можете ссылаться на имя типа в виде строки (например, `New-Object` не работает), а также использовать литерал типа (например, `[MyClass]`) за пределами файла скрипта или модуля, где определен этот класс.</span><span class="sxs-lookup"><span data-stu-id="71a81-134">You can't refer to the type name as a string (for example, `New-Object` doesn't work), and in this release, you can't use a type literal (for example, `[MyClass]`) outside the script or module file in which the class is defined.</span></span>

```powershell
class MyClass
{
    ...
}
```

### <a name="enum-keyword-and-enumerations"></a><span data-ttu-id="71a81-135">Ключевое слово Enum и перечисления</span><span class="sxs-lookup"><span data-stu-id="71a81-135">Enum keyword and enumerations</span></span>

<span data-ttu-id="71a81-136">Добавлена поддержка ключевого слова `enum`, где символ новой строки используется в качестве разделителя.</span><span class="sxs-lookup"><span data-stu-id="71a81-136">Support for the `enum` keyword has been added, which uses newline as the delimiter.</span></span> <span data-ttu-id="71a81-137">Сейчас нельзя определить перечислитель относительно самого себя.</span><span class="sxs-lookup"><span data-stu-id="71a81-137">Currently, you cannot define an enumerator in terms of itself.</span></span> <span data-ttu-id="71a81-138">Тем не менее перечисление можно инициализировать относительно другого перечисления, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="71a81-138">However, you can initialize an enum in terms of another enum, as shown in the following example.</span></span> <span data-ttu-id="71a81-139">Кроме того, нельзя задать базовый тип (всегда `[int]`).</span><span class="sxs-lookup"><span data-stu-id="71a81-139">Also, the base type cannot be specified; it is always `[int]`.</span></span>

```powershell
enum Color2
{
    Yellow = [Color]::Blue
}
```

<span data-ttu-id="71a81-140">Значение перечислителя должно быть константой времени анализа.</span><span class="sxs-lookup"><span data-stu-id="71a81-140">An enumerator value must be a parse time constant.</span></span> <span data-ttu-id="71a81-141">Его нельзя задать как результат вызванной команды.</span><span class="sxs-lookup"><span data-stu-id="71a81-141">You cannot set it to the result of an invoked command.</span></span>

```powershell
enum MyEnum
{
    Enum1
    Enum2
    Enum3 = 42
    Enum4 = [int]::MaxValue
}
```

<span data-ttu-id="71a81-142">Перечисления поддерживают арифметические операции, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="71a81-142">Enums support arithmetic operations, as shown in the following example.</span></span>

```powershell
enum SomeEnum { Max = 42 }
enum OtherEnum { Max = [SomeEnum]::Max + 1 }
```

### <a name="import-dscresource"></a><span data-ttu-id="71a81-143">Import-DscResource</span><span class="sxs-lookup"><span data-stu-id="71a81-143">Import-DscResource</span></span>

<span data-ttu-id="71a81-144">Теперь `Import-DscResource` — это динамическое ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="71a81-144">`Import-DscResource` is now a true dynamic keyword.</span></span> <span data-ttu-id="71a81-145">PowerShell анализирует корневой модуль указанного модуля, выполняя поиск классов, которые содержат атрибут **DscResource**.</span><span class="sxs-lookup"><span data-stu-id="71a81-145">PowerShell parses the specified module's root module, searching for classes that contain the **DscResource** attribute.</span></span>

### <a name="implementingassembly"></a><span data-ttu-id="71a81-146">ImplementingAssembly</span><span class="sxs-lookup"><span data-stu-id="71a81-146">ImplementingAssembly</span></span>

<span data-ttu-id="71a81-147">В **ModuleInfo** добавлено новое поле **ImplementingAssembly**.</span><span class="sxs-lookup"><span data-stu-id="71a81-147">A new field, **ImplementingAssembly**, has been added to **ModuleInfo**.</span></span> <span data-ttu-id="71a81-148">Ему присваивается динамическая сборка, созданная для модуля сценариев, если скрипт определяет классы, или загруженная сборка для двоичных модулей.</span><span class="sxs-lookup"><span data-stu-id="71a81-148">It is set to the dynamic assembly created for a script module if the script defines classes, or the loaded assembly for binary modules.</span></span> <span data-ttu-id="71a81-149">Оно не задано, когда **ModuleType** имеет значение **Manifest**.</span><span class="sxs-lookup"><span data-stu-id="71a81-149">It is not set when **ModuleType** is **Manifest**.</span></span>

<span data-ttu-id="71a81-150">Отражение поля **ImplementingAssembly** обнаруживает ресурсы в модуле.</span><span class="sxs-lookup"><span data-stu-id="71a81-150">Reflection on the **ImplementingAssembly** field discovers resources in a module.</span></span> <span data-ttu-id="71a81-151">Это означает, что можно обнаруживать ресурсы, созданные в PowerShell или в любых других управляемых языках.</span><span class="sxs-lookup"><span data-stu-id="71a81-151">This means you can discover resources written in either PowerShell or other managed languages.</span></span>

<span data-ttu-id="71a81-152">Поля с инициализаторами:</span><span class="sxs-lookup"><span data-stu-id="71a81-152">Fields with initializers:</span></span>

```powershell
[int] $i = 5
```

<span data-ttu-id="71a81-153">`Static` поддерживается.</span><span class="sxs-lookup"><span data-stu-id="71a81-153">`Static` is supported.</span></span> <span data-ttu-id="71a81-154">Он действует как атрибут, также как и ограничения типов.</span><span class="sxs-lookup"><span data-stu-id="71a81-154">It works like an attribute, as do the type constraints.</span></span> <span data-ttu-id="71a81-155">Его можно указать в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="71a81-155">It can be specified in any order.</span></span>

```powershell
static [int] $count = 0
```

<span data-ttu-id="71a81-156">Тип не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="71a81-156">A type is optional.</span></span>

```powershell
$s = "hello"
```

<span data-ttu-id="71a81-157">Все члены являются открытыми.</span><span class="sxs-lookup"><span data-stu-id="71a81-157">All members are public.</span></span>

### <a name="constructors-and-instantiation"></a><span data-ttu-id="71a81-158">Конструкторы и создание экземпляров</span><span class="sxs-lookup"><span data-stu-id="71a81-158">Constructors and instantiation</span></span>

<span data-ttu-id="71a81-159">У классов PowerShell могут быть конструкторы.</span><span class="sxs-lookup"><span data-stu-id="71a81-159">PowerShell classes can have constructors.</span></span> <span data-ttu-id="71a81-160">Имя конструктора совпадает с именем класса.</span><span class="sxs-lookup"><span data-stu-id="71a81-160">They have the same name as their class.</span></span> <span data-ttu-id="71a81-161">Конструкторы могут быть перегружены.</span><span class="sxs-lookup"><span data-stu-id="71a81-161">Constructors can be overloaded.</span></span> <span data-ttu-id="71a81-162">Поддерживаются статические конструкторы.</span><span class="sxs-lookup"><span data-stu-id="71a81-162">Static constructors are supported.</span></span> <span data-ttu-id="71a81-163">Свойства с выражениями инициализации инициализируются перед выполнением любого кода в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="71a81-163">Properties with initialization expressions are initialized before running any code in a constructor.</span></span> <span data-ttu-id="71a81-164">Статические свойства инициализируются до основной части статического конструктора, а свойства экземпляра инициализируются до основной части нестатического конструктора.</span><span class="sxs-lookup"><span data-stu-id="71a81-164">Static properties are initialized before the body of a static constructor, and instance properties are initialized before the body of the non-static constructor.</span></span> <span data-ttu-id="71a81-165">В настоящее время не существует синтаксис для вызова конструктора из другого конструктора (такой как синтаксис C\# ": this()").</span><span class="sxs-lookup"><span data-stu-id="71a81-165">Currently, there is no syntax for calling a constructor from another constructor (like the C\# syntax ": this()").</span></span> <span data-ttu-id="71a81-166">Обходной путь заключается в определении общего метода `Init()`.</span><span class="sxs-lookup"><span data-stu-id="71a81-166">The workaround is to define a common `Init()` method.</span></span>

#### <a name="creating-instances"></a><span data-ttu-id="71a81-167">Создание экземпляров</span><span class="sxs-lookup"><span data-stu-id="71a81-167">Creating instances</span></span>

> [!NOTE]
> <span data-ttu-id="71a81-168">В PowerShell 5.0 `New-Object` не работает с классами, определенными в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="71a81-168">In PowerShell 5.0, `New-Object` does not work with classes defined in PowerShell.</span></span> <span data-ttu-id="71a81-169">Кроме того, имя типа отображается только лексически, то есть оно не отображается за пределами модуля или скрипта, определяющего класс.</span><span class="sxs-lookup"><span data-stu-id="71a81-169">Also, the type name is only visible lexically, meaning it is not visible outside of the module or script that defines the class.</span></span> <span data-ttu-id="71a81-170">Функции могут возвращать экземпляры класса, определенного в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="71a81-170">Functions can return instances of a class defined in PowerShell.</span></span> <span data-ttu-id="71a81-171">Эти экземпляры работают за пределами модуля или скрипта.</span><span class="sxs-lookup"><span data-stu-id="71a81-171">Those instances work outside of the module or script.</span></span>

1. <span data-ttu-id="71a81-172">Создание экземпляров с помощью конструктора по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="71a81-172">Instantiating by using the default constructor.</span></span>

   ```powershell
   $a = [MyClass]::new()
   ```

1. <span data-ttu-id="71a81-173">Вызов конструктора с параметром:</span><span class="sxs-lookup"><span data-stu-id="71a81-173">Calling a constructor with a parameter</span></span>

   ```powershell
   $b = [MyClass]::new(42)
   ```

1. <span data-ttu-id="71a81-174">Передача массива в конструктор с несколькими параметрами.</span><span class="sxs-lookup"><span data-stu-id="71a81-174">Passing an array to a constructor with multiple parameters.</span></span>

   ```powershell
   $c = [MyClass]::new(@(42,43,44), "Hello")
   ```

<span data-ttu-id="71a81-175">Псевдостатический метод `new()` работает с типами .NET, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="71a81-175">The pseudo-static method `new()` works with .NET types, as shown in the following example.</span></span>

```powershell
[hashtable]::new()
```

#### <a name="discovering-constructors"></a><span data-ttu-id="71a81-176">Обнаружение конструкторов</span><span class="sxs-lookup"><span data-stu-id="71a81-176">Discovering constructors</span></span>

<span data-ttu-id="71a81-177">Теперь можно просмотреть перегрузки конструктора с помощью `Get-Member` или так, как показано в этом примере:</span><span class="sxs-lookup"><span data-stu-id="71a81-177">You can now see constructor overloads with `Get-Member`, or as shown in this example:</span></span>

```powershell
PS> [hashtable]::new
OverloadDefinitions
-------------------
hashtable new()
hashtable new(int capacity)
hashtable new(int capacity, float loadFactor)
```

<span data-ttu-id="71a81-178">`Get-Member -Static` выводит список конструкторов, чтобы перегрузки можно было просматривать как и любой другой метод.</span><span class="sxs-lookup"><span data-stu-id="71a81-178">`Get-Member -Static` lists constructors, so you can view overloads like any other method.</span></span> <span data-ttu-id="71a81-179">Производительность этого синтаксиса также значительно выше по сравнению с `New-Object`.</span><span class="sxs-lookup"><span data-stu-id="71a81-179">The performance of this syntax is also considerably faster than `New-Object`.</span></span>

### <a name="methods"></a><span data-ttu-id="71a81-180">Методы</span><span class="sxs-lookup"><span data-stu-id="71a81-180">Methods</span></span>

<span data-ttu-id="71a81-181">Метод класса PowerShell реализуется как **ScriptBlock**, имеющий только конечный блок.</span><span class="sxs-lookup"><span data-stu-id="71a81-181">A PowerShell class method is implemented as a **ScriptBlock** that has only an end block.</span></span> <span data-ttu-id="71a81-182">Все методы являются открытыми.</span><span class="sxs-lookup"><span data-stu-id="71a81-182">All methods are public.</span></span> <span data-ttu-id="71a81-183">Ниже приведен пример определения метода с именем **DoSomething**.</span><span class="sxs-lookup"><span data-stu-id="71a81-183">The following shows an example of defining a method named **DoSomething**.</span></span>

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

<span data-ttu-id="71a81-184">Вызов метода:</span><span class="sxs-lookup"><span data-stu-id="71a81-184">Method invocation:</span></span>

```powershell
$b = [MyClass]::new()
$b.DoSomething(42)
```

<span data-ttu-id="71a81-185">Кроме того, поддерживаются перегруженные методы.</span><span class="sxs-lookup"><span data-stu-id="71a81-185">Overloaded methods are also supported.</span></span>

### <a name="properties"></a><span data-ttu-id="71a81-186">Свойства</span><span class="sxs-lookup"><span data-stu-id="71a81-186">Properties</span></span>

<span data-ttu-id="71a81-187">Все свойства являются открытыми.</span><span class="sxs-lookup"><span data-stu-id="71a81-187">All properties are public.</span></span> <span data-ttu-id="71a81-188">Для свойств требуется точка с запятой или новая строка.</span><span class="sxs-lookup"><span data-stu-id="71a81-188">Properties require either a newline or semicolon.</span></span> <span data-ttu-id="71a81-189">Если тип объекта не указан, тип свойства является объектом.</span><span class="sxs-lookup"><span data-stu-id="71a81-189">If no object type is specified, the property type is object.</span></span>

<span data-ttu-id="71a81-190">Свойства, использующие атрибуты проверки или преобразования аргументов (например, `[ValidateSet("aaa")]`) работают должным образом.</span><span class="sxs-lookup"><span data-stu-id="71a81-190">Properties that use validation or argument transformation attributes (like `[ValidateSet("aaa")]`) work as expected.</span></span>

### <a name="hidden"></a><span data-ttu-id="71a81-191">Hidden</span><span class="sxs-lookup"><span data-stu-id="71a81-191">Hidden</span></span>

<span data-ttu-id="71a81-192">Добавлено новое ключевое слово `Hidden`.</span><span class="sxs-lookup"><span data-stu-id="71a81-192">A new keyword, `Hidden`, has been added.</span></span> <span data-ttu-id="71a81-193">`Hidden` может применяться к свойствам и методам (включая конструкторы).</span><span class="sxs-lookup"><span data-stu-id="71a81-193">`Hidden` can be applied to properties and methods (including constructors).</span></span>

<span data-ttu-id="71a81-194">Члены Hidden являются открытыми, но отображаются в выходных данных `Get-Member` только при использовании параметра `-Force`.</span><span class="sxs-lookup"><span data-stu-id="71a81-194">Hidden members are public, but do not appear in the output of `Get-Member` unless the `-Force` parameter is added.</span></span> <span data-ttu-id="71a81-195">Элементы Hidden не учитываются при заполнении нажатием клавиши TAB или использовании Intellisense, если только такая операция не выполняется в классе, определяющем элемент Hidden.</span><span class="sxs-lookup"><span data-stu-id="71a81-195">Hidden members are not included when tab completing or using Intellisense unless the completion occurs in the class defining the hidden member.</span></span>

<span data-ttu-id="71a81-196">Добавлен новый атрибут **System.Management.Automation.HiddenAttribute**, чтобы код C\# мог иметь ту же семантику в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="71a81-196">A new attribute, **System.Management.Automation.HiddenAttribute** has been added so that C\# code can have the same semantics within PowerShell.</span></span>

### <a name="return-types"></a><span data-ttu-id="71a81-197">Типы возвращаемых значений</span><span class="sxs-lookup"><span data-stu-id="71a81-197">Return types</span></span>

<span data-ttu-id="71a81-198">Тип возвращаемого значения является контрактом.</span><span class="sxs-lookup"><span data-stu-id="71a81-198">Return type is a contract.</span></span> <span data-ttu-id="71a81-199">Возвращаемое значение преобразуется к ожидаемому типу.</span><span class="sxs-lookup"><span data-stu-id="71a81-199">The return value is converted to the expected type.</span></span> <span data-ttu-id="71a81-200">Если тип возвращаемого значения не указан, ему присваивается значение **void**.</span><span class="sxs-lookup"><span data-stu-id="71a81-200">If no return type is specified, the return type is **void**.</span></span> <span data-ttu-id="71a81-201">Потоковая передача объектов отсутствует.</span><span class="sxs-lookup"><span data-stu-id="71a81-201">There is no streaming of objects.</span></span> <span data-ttu-id="71a81-202">Записать объекты в конвейер специально или случайно невозможно.</span><span class="sxs-lookup"><span data-stu-id="71a81-202">Objects cannot be written to the pipeline either intentionally or by accident.</span></span>

### <a name="attributes"></a><span data-ttu-id="71a81-203">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="71a81-203">Attributes</span></span>

<span data-ttu-id="71a81-204">Добавлены два новых атрибута — **DscResource** и **DscProperty**.</span><span class="sxs-lookup"><span data-stu-id="71a81-204">Two new attributes, **DscResource** and **DscProperty** have been added.</span></span>

### <a name="lexical-scoping-of-variables"></a><span data-ttu-id="71a81-205">Лексическая область переменных</span><span class="sxs-lookup"><span data-stu-id="71a81-205">Lexical scoping of variables</span></span>

<span data-ttu-id="71a81-206">Ниже приведен пример того, как работает лексическая область в этом выпуске.</span><span class="sxs-lookup"><span data-stu-id="71a81-206">The following shows an example of how lexical scoping works in this release.</span></span>

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

## <a name="end-to-end-example"></a><span data-ttu-id="71a81-207">Комплексный пример</span><span class="sxs-lookup"><span data-stu-id="71a81-207">End-to-End Example</span></span>

<span data-ttu-id="71a81-208">Следующий пример создает несколько новых пользовательских классов для реализации языка динамических таблиц стилей (DSL) HTML.</span><span class="sxs-lookup"><span data-stu-id="71a81-208">The following example creates some custom classes to implement an HTML dynamic style sheet language (DSL).</span></span> <span data-ttu-id="71a81-209">Затем пример добавляет вспомогательные функции для создания определенных типов элементов в рамках класса элементов, таких как стили заголовков и таблицы, так как типы нельзя использовать за пределами области действия модуля.</span><span class="sxs-lookup"><span data-stu-id="71a81-209">Then, the example adds helper functions to create specific element types as part of the element class, such as heading styles and tables, because types cannot be used outside the scope of a module.</span></span>

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
