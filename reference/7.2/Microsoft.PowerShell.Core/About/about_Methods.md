---
description: Описывает, как использовать методы для выполнения действий с объектами в PowerShell.
Locale: en-US
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_methods?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Methods
ms.openlocfilehash: 35eaafcec5d645be6fe88f506bc0971344406273
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600190"
---
# <a name="about-methods"></a><span data-ttu-id="4e688-103">О методах</span><span class="sxs-lookup"><span data-stu-id="4e688-103">About methods</span></span>

## <a name="short-description"></a><span data-ttu-id="4e688-104">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="4e688-104">Short description</span></span>
<span data-ttu-id="4e688-105">Описывает, как использовать методы для выполнения действий с объектами в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4e688-105">Describes how to use methods to perform actions on objects in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="4e688-106">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="4e688-106">Long description</span></span>

<span data-ttu-id="4e688-107">PowerShell использует объекты для представления элементов в хранилищах данных или состояния компьютера.</span><span class="sxs-lookup"><span data-stu-id="4e688-107">PowerShell uses objects to represent the items in data stores or the state of the computer.</span></span> <span data-ttu-id="4e688-108">Например, объекты FileInfo представляют файлы на дисках файловой системы, а объекты Процессинфо представляют процессы на компьютере.</span><span class="sxs-lookup"><span data-stu-id="4e688-108">For example, FileInfo objects represent the files in file system drives and ProcessInfo objects represent the processes on the computer.</span></span>

<span data-ttu-id="4e688-109">Объекты имеют свойства, которые хранят данные об объекте и методы, позволяющие изменить объект.</span><span class="sxs-lookup"><span data-stu-id="4e688-109">Objects have properties, which store data about the object, and methods that let you change the object.</span></span>

<span data-ttu-id="4e688-110">"Метод" — это набор инструкций, указывающих действие, которое можно выполнить над объектом.</span><span class="sxs-lookup"><span data-stu-id="4e688-110">A "method" is a set of instructions that specify an action you can perform on the object.</span></span> <span data-ttu-id="4e688-111">Например, `FileInfo` объект включает `CopyTo` метод, который копирует файл, который `FileInfo` представляет объект.</span><span class="sxs-lookup"><span data-stu-id="4e688-111">For example, the `FileInfo` object includes the `CopyTo` method that copies the file that the `FileInfo` object represents.</span></span>

<span data-ttu-id="4e688-112">Чтобы получить методы любого объекта, используйте `Get-Member` командлет.</span><span class="sxs-lookup"><span data-stu-id="4e688-112">To get the methods of any object, use the `Get-Member` cmdlet.</span></span> <span data-ttu-id="4e688-113">Используйте свойство **MemberType** со значением "Method".</span><span class="sxs-lookup"><span data-stu-id="4e688-113">Use its **MemberType** property with a value of "Method".</span></span> <span data-ttu-id="4e688-114">Следующая команда получает методы объектов Process.</span><span class="sxs-lookup"><span data-stu-id="4e688-114">The following command gets the methods of process objects.</span></span>

```powershell
Get-Process | Get-Member -MemberType Method
```

```Output
TypeName: System.Diagnostics.Process

Name                      MemberType Definition
----                      ---------- ----------
BeginErrorReadLine        Method     System.Void BeginErrorReadLine()
BeginOutputReadLine       Method     System.Void BeginOutputReadLine()
...
Kill                      Method     System.Void Kill()
Refresh                   Method     System.Void Refresh()
Start                     Method     bool Start()
ToString                  Method     string ToString()
WaitForExit               Method     bool WaitForExit(int milliseconds), ...
WaitForInputIdle          Method     bool WaitForInputIdle(int millisecon...
```

<span data-ttu-id="4e688-115">Чтобы выполнить или "вызвать" метод объекта, введите точку (.), имя метода и набор круглых скобок "()".</span><span class="sxs-lookup"><span data-stu-id="4e688-115">To perform or "invoke" a method of an object, type a dot (.), the method name, and a set of parentheses "()".</span></span> <span data-ttu-id="4e688-116">Если у метода есть аргументы, заключите значения аргументов в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="4e688-116">If the method has arguments, place the argument values inside the parentheses.</span></span> <span data-ttu-id="4e688-117">Круглые скобки требуются для каждого вызова метода, даже если отсутствуют аргументы.</span><span class="sxs-lookup"><span data-stu-id="4e688-117">The parentheses are required for every method call, even when there are no arguments.</span></span> <span data-ttu-id="4e688-118">Если метод принимает несколько аргументов, они должны быть разделены запятыми.</span><span class="sxs-lookup"><span data-stu-id="4e688-118">If the method takes multiple arguments, they should be separated by commas.</span></span>

<span data-ttu-id="4e688-119">Например, следующая команда вызывает метод Kill для процессов, чтобы завершить процесс «блокнота» на компьютере.</span><span class="sxs-lookup"><span data-stu-id="4e688-119">For example, the following command invokes the Kill method of processes to end the Notepad process on the computer.</span></span>

```powershell
$notepad = Get-Process notepad
$notepad.Kill()
```

<span data-ttu-id="4e688-120">Этот пример можно сократить, объединив приведенные выше операторы.</span><span class="sxs-lookup"><span data-stu-id="4e688-120">This example can be shortened by combining the above statements.</span></span>

```powershell
(Get-Process Notepad).Kill()
```

<span data-ttu-id="4e688-121">`Get-Process`Команда заключается в круглые скобки, чтобы убедиться, что она выполняется перед вызовом метода Kill.</span><span class="sxs-lookup"><span data-stu-id="4e688-121">The `Get-Process` command is enclosed in parentheses to ensure that it runs before the Kill method is invoked.</span></span> <span data-ttu-id="4e688-122">`Kill`Затем метод вызывается для возвращенного `Process` объекта.</span><span class="sxs-lookup"><span data-stu-id="4e688-122">The `Kill` method is then invoked on the returned `Process` object.</span></span>

<span data-ttu-id="4e688-123">Еще один очень полезный метод — это `Replace` метод строк.</span><span class="sxs-lookup"><span data-stu-id="4e688-123">Another very useful method is the `Replace` method of strings.</span></span> <span data-ttu-id="4e688-124">`Replace`Метод заменяет текст в строке.</span><span class="sxs-lookup"><span data-stu-id="4e688-124">The `Replace` method, replaces text within a string.</span></span> <span data-ttu-id="4e688-125">В приведенном ниже примере точка (.) может быть помещена сразу после закрывающей кавычки строки.</span><span class="sxs-lookup"><span data-stu-id="4e688-125">In the example below, the dot (.) can be placed immediately after the end quote of the string.</span></span>

```powershell
'this is rocket science'.Replace('rocket', 'rock')
```

```Output
this is rock science
```

<span data-ttu-id="4e688-126">Как показано в предыдущих примерах, можно вызвать метод для объекта, полученного с помощью команды, объекта в переменной или любого объекта, который приводит к объекту (например, строке в кавычках).</span><span class="sxs-lookup"><span data-stu-id="4e688-126">As shown in the previous examples, you can invoke a method on an object that you get by using a command, an object in a variable, or anything that results in an object (like a string in quotes).</span></span>

<span data-ttu-id="4e688-127">Начиная с PowerShell 4,0 поддерживается вызов методов с использованием имен динамических методов.</span><span class="sxs-lookup"><span data-stu-id="4e688-127">Starting in PowerShell 4.0, method invocation by using dynamic method names is supported.</span></span>

### <a name="learning-about-methods"></a><span data-ttu-id="4e688-128">Изучение методов</span><span class="sxs-lookup"><span data-stu-id="4e688-128">Learning about methods</span></span>

<span data-ttu-id="4e688-129">Чтобы найти определения методов объекта, перейдите в раздел справки для типа объекта и найдите страницу его методов.</span><span class="sxs-lookup"><span data-stu-id="4e688-129">To find definitions of the methods of an object, go to help topic for the object type and look for its methods page.</span></span> <span data-ttu-id="4e688-130">Например, на следующей странице описываются методы обработки объектов [System. Diagnostics. Process](/dotnet/api/system.diagnostics.process#methods).</span><span class="sxs-lookup"><span data-stu-id="4e688-130">For example, the following page describes the methods of process objects [System.Diagnostics.Process](/dotnet/api/system.diagnostics.process#methods).</span></span>

<span data-ttu-id="4e688-131">Чтобы определить аргументы метода, проверьте определение метода, похожее на схему синтаксиса командлета PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4e688-131">To determine the arguments of a method, review the method definition, which is like the syntax diagram of a PowerShell cmdlet.</span></span>

<span data-ttu-id="4e688-132">Определение метода может иметь одну или несколько подписей методов, которые подобны наборам параметров командлетов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4e688-132">A method definition might have one or more method signatures, which are like the parameter sets of PowerShell cmdlets.</span></span> <span data-ttu-id="4e688-133">Сигнатуры показывают все допустимые форматы команд для вызова метода.</span><span class="sxs-lookup"><span data-stu-id="4e688-133">The signatures show all of the valid formats of commands to invoke the method.</span></span>

<span data-ttu-id="4e688-134">Например, `CopyTo` метод `FileInfo` класса содержит следующие две сигнатуры метода:</span><span class="sxs-lookup"><span data-stu-id="4e688-134">For example, the `CopyTo` method of the `FileInfo` class contains the following two method signatures:</span></span>

```
    CopyTo(String destFileName)
    CopyTo(String destFileName, Boolean overwrite)
```

<span data-ttu-id="4e688-135">Первая сигнатура метода принимает имя целевого файла (и путь).</span><span class="sxs-lookup"><span data-stu-id="4e688-135">The first method signature takes the destination file name (and a path).</span></span> <span data-ttu-id="4e688-136">В следующем примере первый метод используется `CopyTo` для копирования `Final.txt` файла в `C:\Bin` каталог.</span><span class="sxs-lookup"><span data-stu-id="4e688-136">The following example uses the first `CopyTo` method to copy the `Final.txt` file to the `C:\Bin` directory.</span></span>

```powershell
(Get-ChildItem c:\final.txt).CopyTo("c:\bin\final.txt")
```

> [!NOTE]
> <span data-ttu-id="4e688-137">В отличие от режима _аргументов_ PowerShell, методы объекта выполняются в режиме _выражения_ , который является транзитным для платформы .NET Framework, на которой построена оболочка PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4e688-137">Unlike PowerShell's _argument_ mode, object methods execute in _expression_ mode, which is a pass-through to the .NET framework that PowerShell is built on.</span></span> <span data-ttu-id="4e688-138">В  режиме выражения **бареворд** аргументы (строки без кавычек) не допускаются.</span><span class="sxs-lookup"><span data-stu-id="4e688-138">In _expression_ mode **bareword** arguments (unquoted strings) are not allowed.</span></span> <span data-ttu-id="4e688-139">Это различие можно увидеть при использовании пути в качестве параметра, а не пути в качестве аргумента.</span><span class="sxs-lookup"><span data-stu-id="4e688-139">You can see this difference when using a the path as a parameter, versus the path as an argument.</span></span> <span data-ttu-id="4e688-140">Дополнительные сведения о режимах анализа можно узнать в [about_Parsing](about_Parsing.md)</span><span class="sxs-lookup"><span data-stu-id="4e688-140">You can read more about parsing modes in [about_Parsing](about_Parsing.md)</span></span>

<span data-ttu-id="4e688-141">Вторая сигнатура метода принимает имя целевого файла и логическое значение, определяющее, следует ли перезаписывать файл назначения, если он уже существует.</span><span class="sxs-lookup"><span data-stu-id="4e688-141">The second method signature takes a destination file name and a Boolean value that determines whether the destination file should be overwritten, if it already exists.</span></span>

<span data-ttu-id="4e688-142">В следующем примере второй метод используется `CopyTo` для копирования `Final.txt` файла в `C:\Bin` каталог и для перезаписи существующих файлов.</span><span class="sxs-lookup"><span data-stu-id="4e688-142">The following example uses the second `CopyTo` method to copy the `Final.txt` file to the `C:\Bin` directory, and to overwrite existing files.</span></span>

```powershell
(Get-ChildItem c:\final.txt).CopyTo("c:\bin\final.txt", $true)
```

### <a name="methods-of-scalar-objects-and-collections"></a><span data-ttu-id="4e688-143">Методы скалярных объектов и коллекций</span><span class="sxs-lookup"><span data-stu-id="4e688-143">Methods of Scalar objects and Collections</span></span>

<span data-ttu-id="4e688-144">Методы одного («скалярного») объекта определенного типа часто отличаются от методов коллекции объектов того же типа.</span><span class="sxs-lookup"><span data-stu-id="4e688-144">The methods of one ("scalar") object of a particular type are often different from the methods of a collection of objects of the same type.</span></span>

<span data-ttu-id="4e688-145">Например, каждый процесс имеет `Kill` метод, но коллекция процессов не имеет метода Kill.</span><span class="sxs-lookup"><span data-stu-id="4e688-145">For example, every process has a `Kill` method, but a collection of processes does not have a Kill method.</span></span>

<span data-ttu-id="4e688-146">Начиная с PowerShell 3,0, PowerShell пытается предотвратить ошибки скрипта, которые возникают из разных методов скалярных объектов и коллекций.</span><span class="sxs-lookup"><span data-stu-id="4e688-146">Beginning in PowerShell 3.0, PowerShell tries to prevent scripting errors that result from the differing methods of scalar objects and collections.</span></span>

<span data-ttu-id="4e688-147">Если вы отправляете коллекцию, но запрашиваете метод, который существует только для отдельных ("скалярных") объектов, PowerShell вызывает метод для каждого объекта в коллекции.</span><span class="sxs-lookup"><span data-stu-id="4e688-147">If you submit a collection, but request a method that exists only on single ("scalar") objects, PowerShell invokes the method on every object in the collection.</span></span>

<span data-ttu-id="4e688-148">Если метод существует для отдельных объектов и коллекции, вызывается только метод коллекции.</span><span class="sxs-lookup"><span data-stu-id="4e688-148">If the method exists on the individual objects and on the collection, only the collection's method is invoked.</span></span>

<span data-ttu-id="4e688-149">Эта функция также работает с свойствами скалярных объектов и коллекций.</span><span class="sxs-lookup"><span data-stu-id="4e688-149">This feature also works on properties of scalar objects and collections.</span></span> <span data-ttu-id="4e688-150">Дополнительные сведения см. в разделе [about_Properties](about_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="4e688-150">For more information, see [about_Properties](about_Properties.md).</span></span>

### <a name="examples"></a><span data-ttu-id="4e688-151">Примеры</span><span class="sxs-lookup"><span data-stu-id="4e688-151">Examples</span></span>

<span data-ttu-id="4e688-152">В следующем примере выполняется метод **Kill** отдельных объектов Process в коллекции объектов.</span><span class="sxs-lookup"><span data-stu-id="4e688-152">The following example runs the **Kill** method of individual process objects in a collection of objects.</span></span>

<span data-ttu-id="4e688-153">Первая команда запускает три экземпляра процесса Блокнота.</span><span class="sxs-lookup"><span data-stu-id="4e688-153">The first command starts three instances of the Notepad process.</span></span> <span data-ttu-id="4e688-154">`Get-Process` Возвращает все три экземпляра процесса блокнота и сохраняет их в `$p` переменной.</span><span class="sxs-lookup"><span data-stu-id="4e688-154">`Get-Process` gets all three instance of the Notepad process and saves them in the `$p` variable.</span></span>

```powershell
Notepad; Notepad; Notepad
$p = Get-Process Notepad
$p.Count
```

```Output
3
```

<span data-ttu-id="4e688-155">Следующая команда выполняет метод **Kill** для всех трех процессов в `$p` переменной.</span><span class="sxs-lookup"><span data-stu-id="4e688-155">The next command runs the **Kill** method on all three processes in the `$p` variable.</span></span> <span data-ttu-id="4e688-156">Эта команда работает, даже если в коллекции процессов отсутствует `Kill` метод.</span><span class="sxs-lookup"><span data-stu-id="4e688-156">This command works even though a collection of processes does not have a `Kill` method.</span></span>

```powershell
$p.Kill()
Get-Process Notepad
```

<span data-ttu-id="4e688-157">`Get-Process`Команда подтверждает, что `Kill` метод сработал.</span><span class="sxs-lookup"><span data-stu-id="4e688-157">The `Get-Process` command confirms that the `Kill` method worked.</span></span>

```Output
Get-Process : Cannot find a process with the name "notepad". Verify the proc
ess name and call the cmdlet again.
At line:1 char:12
+ Get-Process <<<<  notepad
    + CategoryInfo          : ObjectNotFound: (notepad:String) [Get-Process]
, ProcessCommandException
    + FullyQualifiedErrorId : NoProcessFoundForGivenName,Microsoft.PowerShel
l.Commands.GetProcessCommand
```

<span data-ttu-id="4e688-158">Этот пример функционально эквивалентен использованию `Foreach-Object` командлета для выполнения метода для каждого объекта в коллекции.</span><span class="sxs-lookup"><span data-stu-id="4e688-158">This example is functionally equivalent to using the `Foreach-Object` cmdlet to run the method on each object in the collection.</span></span>

```powershell
$p | ForEach-Object {$_.Kill()}
```

### <a name="foreach-and-where-methods"></a><span data-ttu-id="4e688-159">Методы ForEach и WHERE</span><span class="sxs-lookup"><span data-stu-id="4e688-159">ForEach and Where methods</span></span>

<span data-ttu-id="4e688-160">Начиная с PowerShell 4,0, поддерживается фильтрация коллекций с помощью синтаксиса методов.</span><span class="sxs-lookup"><span data-stu-id="4e688-160">Beginning in PowerShell 4.0, collection filtering by using a method syntax is supported.</span></span> <span data-ttu-id="4e688-161">Это позволяет использовать два новых метода при работе с коллекциями `ForEach` и `Where` .</span><span class="sxs-lookup"><span data-stu-id="4e688-161">This allows use of two new methods when dealing with collections `ForEach` and `Where`.</span></span>

<span data-ttu-id="4e688-162">Дополнительные сведения об этих методах в см. в разделе [about_arrays](about_arrays.md).</span><span class="sxs-lookup"><span data-stu-id="4e688-162">You can read more about these methods in [about_arrays](about_arrays.md)</span></span>

### <a name="calling-a-specific-method-when-multiple-overloads-exist"></a><span data-ttu-id="4e688-163">Вызов определенного метода при наличии нескольких перегрузок</span><span class="sxs-lookup"><span data-stu-id="4e688-163">Calling a specific method when multiple overloads exist</span></span>

<span data-ttu-id="4e688-164">При вызове методов .NET учитывайте следующий сценарий.</span><span class="sxs-lookup"><span data-stu-id="4e688-164">Consider the following scenario when calling .NET methods.</span></span> <span data-ttu-id="4e688-165">Если метод принимает объект, но имеет перегрузку через интерфейс, принимающий более конкретный тип, то PowerShell выбирает метод, который принимает объект, пока он не будет явно приведен к этому интерфейсу.</span><span class="sxs-lookup"><span data-stu-id="4e688-165">If a method takes an object but has an overload via an interface taking a more specific type, PowerShell chooses the method that accepts the object unless you explicitly cast it to that interface.</span></span>

```powershell
Add-Type -TypeDefinition @'

   // Interface
   public interface IFoo {
     string Bar(int p);
   }

   // Type that implements the interface
   public class Foo : IFoo {

   // Direct member method named 'Bar'
   public string Bar(object p) { return $"object: {p}"; }

   // *Explicit* implementation of IFoo's 'Bar' method().
   string IFoo.Bar(int p) {
       return $"int: {p}";
   }

}
'@
```

<span data-ttu-id="4e688-166">В этом примере `object` был выбран менее определенный перегруженный метод **линейчатого** метода.</span><span class="sxs-lookup"><span data-stu-id="4e688-166">In this example the less specific `object` overload of the **Bar** method was chosen.</span></span>

```powershell
[Foo]::new().Bar(1)
```

```Output
object: 1
```

<span data-ttu-id="4e688-167">В этом примере мы приведен метод к интерфейсу **Ифу** , чтобы выбрать более конкретную перегрузку метода **Bar** .</span><span class="sxs-lookup"><span data-stu-id="4e688-167">In this example we cast the method to the interface **IFoo** to select the more specific overload of the **Bar** method.</span></span>

```powershell
([IFoo] [Foo]::new()).Bar(1)
```

```Output
int: 1
```

## <a name="see-also"></a><span data-ttu-id="4e688-168">См. также:</span><span class="sxs-lookup"><span data-stu-id="4e688-168">See Also</span></span>

[<span data-ttu-id="4e688-169">about_Objects</span><span class="sxs-lookup"><span data-stu-id="4e688-169">about_Objects</span></span>](about_Objects.md)

[<span data-ttu-id="4e688-170">about_Properties</span><span class="sxs-lookup"><span data-stu-id="4e688-170">about_Properties</span></span>](about_Properties.md)

[<span data-ttu-id="4e688-171">Get-Member</span><span class="sxs-lookup"><span data-stu-id="4e688-171">Get-Member</span></span>](xref:Microsoft.PowerShell.Utility.Get-Member)

