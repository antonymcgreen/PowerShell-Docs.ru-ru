---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/add-type?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-Type
ms.openlocfilehash: d55925b0580542459e62e60108f855508232f232
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601890"
---
# <span data-ttu-id="99f63-102">Add-Type</span><span class="sxs-lookup"><span data-stu-id="99f63-102">Add-Type</span></span>

## <span data-ttu-id="99f63-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="99f63-103">SYNOPSIS</span></span>
<span data-ttu-id="99f63-104">Добавляет класс Microsoft .NET Core в сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99f63-104">Adds a Microsoft .NET Core class to a PowerShell session.</span></span>

## <span data-ttu-id="99f63-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="99f63-105">SYNTAX</span></span>

### <span data-ttu-id="99f63-106">Фромсаурце (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="99f63-106">FromSource (Default)</span></span>

```
Add-Type [-TypeDefinition] <String> [-Language <Language>] [-ReferencedAssemblies <String[]>]
 [-OutputAssembly <String>] [-OutputType <OutputAssemblyType>] [-PassThru] [-IgnoreWarnings]
 [-CompilerOptions <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="99f63-107">фроммембер</span><span class="sxs-lookup"><span data-stu-id="99f63-107">FromMember</span></span>

```
Add-Type [-Name] <String> [-MemberDefinition] <String[]> [-Namespace <String>]
 [-UsingNamespace <String[]>] [-Language <Language>] [-ReferencedAssemblies <String[]>]
 [-OutputAssembly <String>] [-OutputType <OutputAssemblyType>] [-PassThru] [-IgnoreWarnings]
 [-CompilerOptions <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="99f63-108">фромпас</span><span class="sxs-lookup"><span data-stu-id="99f63-108">FromPath</span></span>

```
Add-Type [-Path] <String[]> [-ReferencedAssemblies <String[]>] [-OutputAssembly <String>]
 [-OutputType <OutputAssemblyType>] [-PassThru] [-IgnoreWarnings] [-CompilerOptions <String[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="99f63-109">фромлитералпас</span><span class="sxs-lookup"><span data-stu-id="99f63-109">FromLiteralPath</span></span>

```
Add-Type -LiteralPath <String[]> [-ReferencedAssemblies <String[]>] [-OutputAssembly <String>]
 [-OutputType <OutputAssemblyType>] [-PassThru] [-IgnoreWarnings] [-CompilerOptions <String[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="99f63-110">фромассемблинаме</span><span class="sxs-lookup"><span data-stu-id="99f63-110">FromAssemblyName</span></span>

```
Add-Type -AssemblyName <String[]> [-PassThru] [<CommonParameters>]
```

## <span data-ttu-id="99f63-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="99f63-111">DESCRIPTION</span></span>

<span data-ttu-id="99f63-112">`Add-Type`Командлет позволяет определить класс Microsoft .NET Core в сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99f63-112">The `Add-Type` cmdlet lets you define a Microsoft .NET Core class in your PowerShell session.</span></span> <span data-ttu-id="99f63-113">Затем можно создать экземпляры объектов с помощью `New-Object` командлета и использовать объекты так же, как и любой объект .NET Core.</span><span class="sxs-lookup"><span data-stu-id="99f63-113">You can then instantiate objects, by using the `New-Object` cmdlet, and use the objects just as you would use any .NET Core object.</span></span> <span data-ttu-id="99f63-114">При добавлении `Add-Type` команды в профиль PowerShell класс доступен во всех сеансах PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99f63-114">If you add an `Add-Type` command to your PowerShell profile, the class is available in all PowerShell sessions.</span></span>

<span data-ttu-id="99f63-115">Тип можно указать, указав существующую сборку или файлы исходного кода. Кроме того, можно указать встроенный или сохраненный в переменной исходный код.</span><span class="sxs-lookup"><span data-stu-id="99f63-115">You can specify the type by specifying an existing assembly or source code files, or you can specify the source code inline or saved in a variable.</span></span> <span data-ttu-id="99f63-116">Можно даже указать только метод, а также `Add-Type` Определение и создание класса.</span><span class="sxs-lookup"><span data-stu-id="99f63-116">You can even specify only a method and `Add-Type` defines and generates the class.</span></span> <span data-ttu-id="99f63-117">В Windows эту функцию можно использовать для вызова неуправляемых функций (P/Invoke) в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99f63-117">On Windows, you can use this feature to make Platform Invoke (P/Invoke) calls to unmanaged functions in PowerShell.</span></span> <span data-ttu-id="99f63-118">Если указан исходный код, `Add-Type` компилирует указанный исходный код и создает сборку в памяти, содержащую новые типы .NET Core.</span><span class="sxs-lookup"><span data-stu-id="99f63-118">If you specify source code, `Add-Type` compiles the specified source code and generates an in-memory assembly that contains the new .NET Core types.</span></span>

<span data-ttu-id="99f63-119">`Add-Type`Для указания альтернативного языка и компилятора можно использовать параметры, C# — это по умолчанию, параметры компилятора, зависимости сборок, пространство имен класса, имена типа и результирующая сборка.</span><span class="sxs-lookup"><span data-stu-id="99f63-119">You can use the parameters of `Add-Type` to specify an alternate language and compiler, C# is the default, compiler options, assembly dependencies, the class namespace, the names of the type, and the resulting assembly.</span></span>

<span data-ttu-id="99f63-120">Начиная с PowerShell 7, не `Add-Type` компилирует тип, если тип с таким именем уже существует.</span><span class="sxs-lookup"><span data-stu-id="99f63-120">Beginning in PowerShell 7, `Add-Type` does not compile a type if a type with the same name already exists.</span></span> <span data-ttu-id="99f63-121">Кроме того, `Add-Type` ищет сборки в `ref` папке, содержащей `pwsh.dll` .</span><span class="sxs-lookup"><span data-stu-id="99f63-121">Also, `Add-Type` looks for assemblies in a `ref` folder under the folder that contains `pwsh.dll`.</span></span>

## <span data-ttu-id="99f63-122">Примеры</span><span class="sxs-lookup"><span data-stu-id="99f63-122">EXAMPLES</span></span>

### <span data-ttu-id="99f63-123">Пример 1. Добавление типа .NET в сеанс</span><span class="sxs-lookup"><span data-stu-id="99f63-123">Example 1: Add a .NET type to a session</span></span>

<span data-ttu-id="99f63-124">В этом примере класс **BasicTest** добавляется в сеанс путем указания исходного кода, хранящегося в переменной.</span><span class="sxs-lookup"><span data-stu-id="99f63-124">This example adds the **BasicTest** class to the session by specifying source code that is stored in a variable.</span></span> <span data-ttu-id="99f63-125">Класс **BasicTest** используется для добавления целых чисел, создания объекта и умножения целых чисел.</span><span class="sxs-lookup"><span data-stu-id="99f63-125">The **BasicTest** class is used to add integers, create an object, and multiply integers.</span></span>

```powershell
$Source = @"
public class BasicTest
{
  public static int Add(int a, int b)
    {
        return (a + b);
    }
  public int Multiply(int a, int b)
    {
    return (a * b);
    }
}
"@

Add-Type -TypeDefinition $Source
[BasicTest]::Add(4, 3)
$BasicTestObject = New-Object BasicTest
$BasicTestObject.Multiply(5, 2)
```

<span data-ttu-id="99f63-126">`$Source`Переменная хранит исходный код для класса.</span><span class="sxs-lookup"><span data-stu-id="99f63-126">The `$Source` variable stores the source code for the class.</span></span> <span data-ttu-id="99f63-127">Тип имеет вызванный статический метод `Add` и метод, не являющийся статическим `Multiply` .</span><span class="sxs-lookup"><span data-stu-id="99f63-127">The type has a static method called `Add` and a non-static method called `Multiply`.</span></span>

<span data-ttu-id="99f63-128">`Add-Type`Командлет добавляет класс в сеанс.</span><span class="sxs-lookup"><span data-stu-id="99f63-128">The `Add-Type` cmdlet adds the class to the session.</span></span> <span data-ttu-id="99f63-129">Так как он использует встроенный исходный код, команда использует параметр **типедефинитион** для указания кода в `$Source` переменной.</span><span class="sxs-lookup"><span data-stu-id="99f63-129">Because it's using inline source code, the command uses the **TypeDefinition** parameter to specify the code in the `$Source` variable.</span></span>

<span data-ttu-id="99f63-130">`Add`Статический метод класса **BasicTest** использует символы двойного двоеточия ( `::` ) для указания статического члена класса.</span><span class="sxs-lookup"><span data-stu-id="99f63-130">The `Add` static method of the **BasicTest** class uses the double-colon characters (`::`) to specify a static member of the class.</span></span> <span data-ttu-id="99f63-131">Добавляются целые числа и отображается сумма.</span><span class="sxs-lookup"><span data-stu-id="99f63-131">The integers are added and the sum is displayed.</span></span>

<span data-ttu-id="99f63-132">`New-Object`Командлет создает экземпляр класса **BasicTest** .</span><span class="sxs-lookup"><span data-stu-id="99f63-132">The `New-Object` cmdlet instantiates an instance of the **BasicTest** class.</span></span> <span data-ttu-id="99f63-133">Он сохраняет новый объект в `$BasicTestObject` переменной.</span><span class="sxs-lookup"><span data-stu-id="99f63-133">It saves the new object in the `$BasicTestObject` variable.</span></span>

<span data-ttu-id="99f63-134">`$BasicTestObject` использует `Multiply` метод.</span><span class="sxs-lookup"><span data-stu-id="99f63-134">`$BasicTestObject` uses the `Multiply` method.</span></span> <span data-ttu-id="99f63-135">Целые числа умножаются, а продукт отображается.</span><span class="sxs-lookup"><span data-stu-id="99f63-135">The integers are multiplied and the product is displayed.</span></span>

### <span data-ttu-id="99f63-136">Пример 2. Проверка добавленного типа</span><span class="sxs-lookup"><span data-stu-id="99f63-136">Example 2: Examine an added type</span></span>

<span data-ttu-id="99f63-137">В этом примере `Get-Member` командлет используется для проверки объектов, `Add-Type` `New-Object` созданных командлетами и, в **примере 1**.</span><span class="sxs-lookup"><span data-stu-id="99f63-137">This example uses the `Get-Member` cmdlet to examine the objects that the `Add-Type` and `New-Object` cmdlets created in **Example 1**.</span></span>

```powershell
[BasicTest] | Get-Member
```

```Output
   TypeName: System.RuntimeType

Name                 MemberType Definition
----                 ---------- ----------
AsType               Method     type AsType()
Clone                Method     System.Object Clone(), System.Object ICloneable.Clone()
Equals               Method     bool Equals(System.Object obj), bool Equals(type o)
FindInterfaces       Method     type[] FindInterfaces(System.Reflection.TypeFilter filter...
...
```

```powershell
[BasicTest] | Get-Member -Static
```

```Output
  TypeName: BasicTest

Name            MemberType Definition
----            ---------- ----------
Add             Method     static int Add(int a, int b)
Equals          Method     static bool Equals(System.Object objA, System.Object objB)
new             Method     BasicTest new()
ReferenceEquals Method     static bool ReferenceEquals(System.Object objA, System.Object objB)
```

```powershell
$BasicTestObject | Get-Member
```

```Output
   TypeName: BasicTest

Name        MemberType Definition
----        ---------- ----------
Equals      Method     bool Equals(System.Object obj)
GetHashCode Method     int GetHashCode()
GetType     Method     type GetType()
Multiply    Method     int Multiply(int a, int b)
ToString    Method     string ToString()
```

<span data-ttu-id="99f63-138">`Get-Member`Командлет возвращает тип и члены класса **BasicTest** , `Add-Type` добавленные в сеанс.</span><span class="sxs-lookup"><span data-stu-id="99f63-138">The `Get-Member` cmdlet gets the type and members of the **BasicTest** class that `Add-Type` added to the session.</span></span> <span data-ttu-id="99f63-139">`Get-Member`Команда обнаруживает, что это объект **System. RuntimeType** , производный от класса **System. Object** .</span><span class="sxs-lookup"><span data-stu-id="99f63-139">The `Get-Member` command reveals that it's a **System.RuntimeType** object, which is derived from the **System.Object** class.</span></span>

<span data-ttu-id="99f63-140">`Get-Member` **Статический** параметр получает статические свойства и методы класса **BasicTest** .</span><span class="sxs-lookup"><span data-stu-id="99f63-140">The `Get-Member` **Static** parameter gets the static properties and methods of the **BasicTest** class.</span></span> <span data-ttu-id="99f63-141">Выходные данные показывают, что `Add` метод включен.</span><span class="sxs-lookup"><span data-stu-id="99f63-141">The output shows that the `Add` method is included.</span></span>

<span data-ttu-id="99f63-142">`Get-Member`Командлет возвращает элементы объекта, хранящегося в `$BasicTestObject` переменной.</span><span class="sxs-lookup"><span data-stu-id="99f63-142">The `Get-Member` cmdlet gets the members of the object stored in the `$BasicTestObject` variable.</span></span>
<span data-ttu-id="99f63-143">`$BasicTestObject` был создан с помощью `New-Object` командлета с классом **BasicTest** .</span><span class="sxs-lookup"><span data-stu-id="99f63-143">`$BasicTestObject` was created by using the `New-Object` cmdlet with the **BasicTest** class.</span></span> <span data-ttu-id="99f63-144">Результат показывает, что значение `$BasicTestObject` переменной является экземпляром класса **BasicTest** и включает член с именем `Multiply` .</span><span class="sxs-lookup"><span data-stu-id="99f63-144">The output reveals that the value of the `$BasicTestObject` variable is an instance of the **BasicTest** class and that it includes a member called `Multiply`.</span></span>

### <span data-ttu-id="99f63-145">Пример 3. Добавление типов из сборки</span><span class="sxs-lookup"><span data-stu-id="99f63-145">Example 3: Add types from an assembly</span></span>

<span data-ttu-id="99f63-146">В этом примере классы из сборки добавляются `NJsonSchema.dll` в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="99f63-146">This example adds the classes from the `NJsonSchema.dll` assembly to the current session.</span></span>

```powershell
Set-Location -Path $PSHOME
$AccType = Add-Type -AssemblyName *jsonschema* -PassThru
```

<span data-ttu-id="99f63-147">`Set-Location` использует параметр **path** для указания `$PSHOME` переменной.</span><span class="sxs-lookup"><span data-stu-id="99f63-147">`Set-Location` uses the **Path** parameter to specify the `$PSHOME` variable.</span></span> <span data-ttu-id="99f63-148">Переменная ссылается на каталог установки PowerShell, в котором находится DLL-файл.</span><span class="sxs-lookup"><span data-stu-id="99f63-148">The variable references the PowerShell installation directory where the DLL file is located.</span></span>

<span data-ttu-id="99f63-149">`$AccType`Переменная хранит объект, созданный с помощью `Add-Type` командлета.</span><span class="sxs-lookup"><span data-stu-id="99f63-149">The `$AccType` variable stores an object created with the `Add-Type` cmdlet.</span></span> <span data-ttu-id="99f63-150">`Add-Type` использует параметр **AssemblyName** для указания имени сборки.</span><span class="sxs-lookup"><span data-stu-id="99f63-150">`Add-Type` uses the **AssemblyName** parameter to specify the name of the assembly.</span></span> <span data-ttu-id="99f63-151">`*`Подстановочный знак звездочки () позволяет получить правильную сборку, даже если вы не уверены в ее имени или ее написании.</span><span class="sxs-lookup"><span data-stu-id="99f63-151">The asterisk (`*`) wildcard character allows you to get the correct assembly even when you aren't sure of the name or its spelling.</span></span> <span data-ttu-id="99f63-152">Параметр **PassThru** создает объекты, представляющие классы, которые добавляются в сеанс.</span><span class="sxs-lookup"><span data-stu-id="99f63-152">The **PassThru** parameter generates objects that represent the classes that are added to the session.</span></span>

### <span data-ttu-id="99f63-153">Пример 4. вызов собственных интерфейсов API Windows</span><span class="sxs-lookup"><span data-stu-id="99f63-153">Example 4: Call native Windows APIs</span></span>

<span data-ttu-id="99f63-154">В этом примере показано, как вызывать собственные API Windows в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99f63-154">This example demonstrates how to call native Windows APIs in PowerShell.</span></span> <span data-ttu-id="99f63-155">`Add-Type` использует механизм вызова неуправляемого кода (P/Invoke) для вызова функции `User32.dll` из PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99f63-155">`Add-Type` uses the Platform Invoke (P/Invoke) mechanism to call a function in `User32.dll` from PowerShell.</span></span> <span data-ttu-id="99f63-156">Этот пример работает только на компьютерах под управлением операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="99f63-156">This example only works on computers running the Windows operating system.</span></span>

```powershell
$Signature = @"
[DllImport("user32.dll")]public static extern bool ShowWindowAsync(IntPtr hWnd, int nCmdShow);
"@

$ShowWindowAsync = Add-Type -MemberDefinition $Signature -Name "Win32ShowWindowAsync" -Namespace Win32Functions -PassThru

# Minimize the PowerShell console

$ShowWindowAsync::ShowWindowAsync((Get-Process -Id $pid).MainWindowHandle, 2)

# Restore the PowerShell console

$ShowWindowAsync::ShowWindowAsync((Get-Process -Id $Pid).MainWindowHandle, 4)
```

<span data-ttu-id="99f63-157">`$Signature`Переменная хранит сигнатуру C# `ShowWindowAsync` функции.</span><span class="sxs-lookup"><span data-stu-id="99f63-157">The `$Signature` variable stores the C# signature of the `ShowWindowAsync` function.</span></span> <span data-ttu-id="99f63-158">Чтобы обеспечить видимость полученного метода в сеансе PowerShell, `public` ключевое слово было добавлено к стандартной сигнатуре.</span><span class="sxs-lookup"><span data-stu-id="99f63-158">To ensure that the resulting method is visible in a PowerShell session, the `public` keyword was added to the standard signature.</span></span> <span data-ttu-id="99f63-159">Дополнительные сведения см. в разделе [функция showWindowAsync](/windows/win32/api/winuser/nf-winuser-showwindowasync).</span><span class="sxs-lookup"><span data-stu-id="99f63-159">For more information, see [ShowWindowAsync function](/windows/win32/api/winuser/nf-winuser-showwindowasync).</span></span>

<span data-ttu-id="99f63-160">`$ShowWindowAsync`Переменная хранит объект, созданный `Add-Type` параметром **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="99f63-160">The `$ShowWindowAsync` variable stores the object created by the `Add-Type` **PassThru** parameter.</span></span>
<span data-ttu-id="99f63-161">`Add-Type`Командлет добавляет `ShowWindowAsync` функцию в сеанс PowerShell как статический метод.</span><span class="sxs-lookup"><span data-stu-id="99f63-161">The `Add-Type` cmdlet adds the `ShowWindowAsync` function to the PowerShell session as a static method.</span></span> <span data-ttu-id="99f63-162">Команда использует параметр **MemberDefinition** для указания определения метода, сохраненного в `$Signature` переменной.</span><span class="sxs-lookup"><span data-stu-id="99f63-162">The command uses the **MemberDefinition** parameter to specify the method definition saved in the `$Signature` variable.</span></span> <span data-ttu-id="99f63-163">Команда использует параметры **Name** и **Namespace**, чтобы указать имя и пространство имен для класса.</span><span class="sxs-lookup"><span data-stu-id="99f63-163">The command uses the **Name** and **Namespace** parameters to specify a name and namespace for the class.</span></span> <span data-ttu-id="99f63-164">Параметр **PassThru** создает объект, представляющий типы.</span><span class="sxs-lookup"><span data-stu-id="99f63-164">The **PassThru** parameter generates an object that represents the types.</span></span>

<span data-ttu-id="99f63-165">Новый `ShowWindowAsync` статический метод используется в командах для сворачивания и восстановления консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99f63-165">The new `ShowWindowAsync` static method is used in the commands to minimize and restore the PowerShell console.</span></span> <span data-ttu-id="99f63-166">Метод принимает два параметра: маркер окна и целое число, которое указывает, как отображается окно.</span><span class="sxs-lookup"><span data-stu-id="99f63-166">The method takes two parameters: the window handle, and an integer that specifies how the window is displayed.</span></span>

<span data-ttu-id="99f63-167">Для сворачивания консоли PowerShell `ShowWindowAsync` использует `Get-Process` командлет с `$PID` автоматической переменной для получения процесса, в котором размещается текущий сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99f63-167">To minimize the PowerShell console, `ShowWindowAsync` uses the `Get-Process` cmdlet with the `$PID` automatic variable to get the process that is hosting the current PowerShell session.</span></span> <span data-ttu-id="99f63-168">Затем используется свойство **маинвиндовхандле** текущего процесса и значение `2` , представляющее `SW_MINIMIZE` значение.</span><span class="sxs-lookup"><span data-stu-id="99f63-168">Then it uses the **MainWindowHandle** property of the current process and a value of `2`, which represents the `SW_MINIMIZE` value.</span></span>

<span data-ttu-id="99f63-169">Для восстановления окна `ShowWindowAsync` использует значение `4` для расположения окна, которое представляет `SW_RESTORE` значение.</span><span class="sxs-lookup"><span data-stu-id="99f63-169">To restore the window, `ShowWindowAsync` uses a value of `4` for the window position, which represents the `SW_RESTORE` value.</span></span>

<span data-ttu-id="99f63-170">Чтобы развернуть окно, используйте значение `3` , представляющее `SW_MAXIMIZE` .</span><span class="sxs-lookup"><span data-stu-id="99f63-170">To maximize the window, use the value of `3` that represents `SW_MAXIMIZE`.</span></span>

## <span data-ttu-id="99f63-171">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="99f63-171">PARAMETERS</span></span>

### <span data-ttu-id="99f63-172">-AssemblyName</span><span class="sxs-lookup"><span data-stu-id="99f63-172">-AssemblyName</span></span>

<span data-ttu-id="99f63-173">Задает имя сборки, включающей типы.</span><span class="sxs-lookup"><span data-stu-id="99f63-173">Specifies the name of an assembly that includes the types.</span></span> <span data-ttu-id="99f63-174">`Add-Type` принимает типы из указанной сборки.</span><span class="sxs-lookup"><span data-stu-id="99f63-174">`Add-Type` takes the types from the specified assembly.</span></span> <span data-ttu-id="99f63-175">Этот параметр является обязательным при создании типов на основе имени сборки.</span><span class="sxs-lookup"><span data-stu-id="99f63-175">This parameter is required when you're creating types based on an assembly name.</span></span>

<span data-ttu-id="99f63-176">Введите полное или простое имя сборки, также называемое частичным именем.</span><span class="sxs-lookup"><span data-stu-id="99f63-176">Enter the full or simple name, also known as the partial name, of an assembly.</span></span> <span data-ttu-id="99f63-177">В именах сборок можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="99f63-177">Wildcard characters are permitted in the assembly name.</span></span> <span data-ttu-id="99f63-178">Если вы вводите простое или частичное имя, `Add-Type` разрешаете его в полное имя, а затем использует полное имя для загрузки сборки.</span><span class="sxs-lookup"><span data-stu-id="99f63-178">If you enter a simple or partial name, `Add-Type` resolves it to the full name, and then uses the full name to load the assembly.</span></span>

<span data-ttu-id="99f63-179">Этот параметр не принимает путь или имя файла.</span><span class="sxs-lookup"><span data-stu-id="99f63-179">This parameter doesn't accept a path or a filename.</span></span> <span data-ttu-id="99f63-180">Чтобы ввести путь к файлу библиотеки динамической компоновки (DLL) сборки, используйте параметр **path** .</span><span class="sxs-lookup"><span data-stu-id="99f63-180">To enter the path to the assembly dynamic-link library (DLL) file, use the **Path** parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FromAssemblyName
Aliases: AN

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="99f63-181">-Компилероптионс</span><span class="sxs-lookup"><span data-stu-id="99f63-181">-CompilerOptions</span></span>

<span data-ttu-id="99f63-182">Указывает параметры для компилятора исходного кода.</span><span class="sxs-lookup"><span data-stu-id="99f63-182">Specifies the options for the source code compiler.</span></span> <span data-ttu-id="99f63-183">Эти параметры отправляются в компилятор без проверки.</span><span class="sxs-lookup"><span data-stu-id="99f63-183">These options are sent to the compiler without revision.</span></span>

<span data-ttu-id="99f63-184">Этот параметр позволяет указать компилятору создать исполняемый файл, внедрить ресурсы или задать параметры командной строки, например `/unsafe` параметр.</span><span class="sxs-lookup"><span data-stu-id="99f63-184">This parameter allows you to direct the compiler to generate an executable file, embed resources, or set command-line options, such as the `/unsafe` option.</span></span>

<span data-ttu-id="99f63-185">В одной команде нельзя использовать параметры **компилероптионс** и **референцедассемблиес** .</span><span class="sxs-lookup"><span data-stu-id="99f63-185">You can't use the **CompilerOptions** and **ReferencedAssemblies** parameters in the same command.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FromSource, FromMember, FromPath, FromLiteralPath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="99f63-186">-Игнореварнингс</span><span class="sxs-lookup"><span data-stu-id="99f63-186">-IgnoreWarnings</span></span>

<span data-ttu-id="99f63-187">Игнорирует предупреждения компилятора.</span><span class="sxs-lookup"><span data-stu-id="99f63-187">Ignores compiler warnings.</span></span> <span data-ttu-id="99f63-188">Используйте этот параметр, чтобы предотвратить `Add-Type` обработку предупреждений компилятора как ошибок.</span><span class="sxs-lookup"><span data-stu-id="99f63-188">Use this parameter to prevent `Add-Type` from handling compiler warnings as errors.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FromSource, FromMember, FromPath, FromLiteralPath
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="99f63-189">— Язык</span><span class="sxs-lookup"><span data-stu-id="99f63-189">-Language</span></span>

<span data-ttu-id="99f63-190">Задает язык, который используется в исходном коде.</span><span class="sxs-lookup"><span data-stu-id="99f63-190">Specifies the language that is used in the source code.</span></span> <span data-ttu-id="99f63-191">Допустимое значение для этого параметра — **CSharp**.</span><span class="sxs-lookup"><span data-stu-id="99f63-191">The acceptable value for this parameter is **CSharp**.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.Language
Parameter Sets: FromSource, FromMember
Aliases:
Accepted values: CSharp

Required: False
Position: Named
Default value: CSharp
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="99f63-192">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="99f63-192">-LiteralPath</span></span>

<span data-ttu-id="99f63-193">Задает путь к файлу исходного кода или DLL-файлам сборки, содержащей типы.</span><span class="sxs-lookup"><span data-stu-id="99f63-193">Specifies the path to source code files or assembly DLL files that contain the types.</span></span> <span data-ttu-id="99f63-194">В отличие от **path**, значение параметра **LiteralPath** используется точно так же, как типизировано.</span><span class="sxs-lookup"><span data-stu-id="99f63-194">Unlike **Path**, the value of the **LiteralPath** parameter is used exactly as it's typed.</span></span> <span data-ttu-id="99f63-195">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="99f63-195">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="99f63-196">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="99f63-196">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="99f63-197">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="99f63-197">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FromLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="99f63-198">-MemberDefinition</span><span class="sxs-lookup"><span data-stu-id="99f63-198">-MemberDefinition</span></span>

<span data-ttu-id="99f63-199">Указывает новые свойства или методы для класса.</span><span class="sxs-lookup"><span data-stu-id="99f63-199">Specifies new properties or methods for the class.</span></span> <span data-ttu-id="99f63-200">`Add-Type` создает код шаблона, необходимый для поддержки свойств или методов.</span><span class="sxs-lookup"><span data-stu-id="99f63-200">`Add-Type` generates the template code that is required to support the properties or methods.</span></span>

<span data-ttu-id="99f63-201">В Windows эту функцию можно использовать для вызова неуправляемых функций (P/Invoke) в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99f63-201">On Windows, you can use this feature to make Platform Invoke (P/Invoke) calls to unmanaged functions in PowerShell.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FromMember
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="99f63-202">-Name</span><span class="sxs-lookup"><span data-stu-id="99f63-202">-Name</span></span>

<span data-ttu-id="99f63-203">Задает имя создаваемого класса.</span><span class="sxs-lookup"><span data-stu-id="99f63-203">Specifies the name of the class to create.</span></span> <span data-ttu-id="99f63-204">Этот параметр является обязательным при создании типа из определения члена.</span><span class="sxs-lookup"><span data-stu-id="99f63-204">This parameter is required when generating a type from a member definition.</span></span>

<span data-ttu-id="99f63-205">Имя типа и пространство имен должны быть уникальными в пределах сеанса.</span><span class="sxs-lookup"><span data-stu-id="99f63-205">The type name and namespace must be unique within a session.</span></span> <span data-ttu-id="99f63-206">Невозможно выгрузить тип или изменить его.</span><span class="sxs-lookup"><span data-stu-id="99f63-206">You can't unload a type or change it.</span></span>
<span data-ttu-id="99f63-207">Чтобы изменить код для типа, необходимо изменить имя или запустить новый сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99f63-207">To change the code for a type, you must change the name or start a new PowerShell session.</span></span>
<span data-ttu-id="99f63-208">В противном случае произойдет сбой команды.</span><span class="sxs-lookup"><span data-stu-id="99f63-208">Otherwise, the command fails.</span></span>

```yaml
Type: System.String
Parameter Sets: FromMember
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="99f63-209">-Namespace</span><span class="sxs-lookup"><span data-stu-id="99f63-209">-Namespace</span></span>

<span data-ttu-id="99f63-210">Задает пространство имен для типа.</span><span class="sxs-lookup"><span data-stu-id="99f63-210">Specifies a namespace for the type.</span></span>

<span data-ttu-id="99f63-211">Если этот параметр не включен в команду, тип создается в пространстве имен **Microsoft. PowerShell. Commands. аддтипе. аутоженератедтипес** .</span><span class="sxs-lookup"><span data-stu-id="99f63-211">If this parameter isn't included in the command, the type is created in the **Microsoft.PowerShell.Commands.AddType.AutoGeneratedTypes** namespace.</span></span> <span data-ttu-id="99f63-212">Если параметр включен в команду с пустым строковым значением или значением `$Null` , то тип создается в глобальном пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="99f63-212">If the parameter is included in the command with an empty string value or a value of `$Null`, the type is generated in the global namespace.</span></span>

```yaml
Type: System.String
Parameter Sets: FromMember
Aliases: NS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="99f63-213">-Аутпутассембли</span><span class="sxs-lookup"><span data-stu-id="99f63-213">-OutputAssembly</span></span>

<span data-ttu-id="99f63-214">Создает DLL-файл для сборки с заданным именем в расположении.</span><span class="sxs-lookup"><span data-stu-id="99f63-214">Generates a DLL file for the assembly with the specified name in the location.</span></span> <span data-ttu-id="99f63-215">Введите необязательный путь и имя файла.</span><span class="sxs-lookup"><span data-stu-id="99f63-215">Enter an optional path and filename.</span></span> <span data-ttu-id="99f63-216">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="99f63-216">Wildcard characters are permitted.</span></span> <span data-ttu-id="99f63-217">По умолчанию `Add-Type` создает сборку только в памяти.</span><span class="sxs-lookup"><span data-stu-id="99f63-217">By default, `Add-Type` generates the assembly only in memory.</span></span>

```yaml
Type: System.String
Parameter Sets: FromSource, FromMember, FromPath, FromLiteralPath
Aliases: OA

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="99f63-218">-OutputType</span><span class="sxs-lookup"><span data-stu-id="99f63-218">-OutputType</span></span>

<span data-ttu-id="99f63-219">Указывает тип вывода выходной сборки.</span><span class="sxs-lookup"><span data-stu-id="99f63-219">Specifies the output type of the output assembly.</span></span> <span data-ttu-id="99f63-220">По умолчанию тип вывода не указывается.</span><span class="sxs-lookup"><span data-stu-id="99f63-220">By default, no output type is specified.</span></span> <span data-ttu-id="99f63-221">Этот параметр допустим только в том случае, если в команде указана выходная сборка.</span><span class="sxs-lookup"><span data-stu-id="99f63-221">This parameter is valid only when an output assembly is specified in the command.</span></span> <span data-ttu-id="99f63-222">Дополнительные сведения о значениях см. в разделе [Аутпутассемблитипе enumeration](/dotnet/api/microsoft.powershell.commands.outputassemblytype).</span><span class="sxs-lookup"><span data-stu-id="99f63-222">For more information about the values, see [OutputAssemblyType Enumeration](/dotnet/api/microsoft.powershell.commands.outputassemblytype).</span></span>

<span data-ttu-id="99f63-223">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="99f63-223">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="99f63-224">консолеаппликатион</span><span class="sxs-lookup"><span data-stu-id="99f63-224">ConsoleApplication</span></span>
- <span data-ttu-id="99f63-225">Библиотека</span><span class="sxs-lookup"><span data-stu-id="99f63-225">Library</span></span>
- <span data-ttu-id="99f63-226">виндовсаппликатион</span><span class="sxs-lookup"><span data-stu-id="99f63-226">WindowsApplication</span></span>

> [!IMPORTANT]
> <span data-ttu-id="99f63-227">Начиная с версии PowerShell 7,1 `ConsoleApplication` и `WindowsApplication` не поддерживаются, и PowerShell вызывает завершающую ошибку, если в качестве значений параметра **OutputType** задано значение.</span><span class="sxs-lookup"><span data-stu-id="99f63-227">As of PowerShell 7.1, `ConsoleApplication` and `WindowsApplication` are not supported and PowerShell throws a terminating error if either are specified as values for the **OutputType** parameter.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.OutputAssemblyType
Parameter Sets: FromSource, FromMember, FromPath, FromLiteralPath
Aliases: OT
Accepted values: ConsoleApplication, Library, WindowsApplication

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="99f63-228">-PassThru</span><span class="sxs-lookup"><span data-stu-id="99f63-228">-PassThru</span></span>

<span data-ttu-id="99f63-229">Возвращает объект **System.Runtime**, представляющий добавленные типы.</span><span class="sxs-lookup"><span data-stu-id="99f63-229">Returns a **System.Runtime** object that represents the types that were added.</span></span> <span data-ttu-id="99f63-230">По умолчанию этот командлет не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="99f63-230">By default, this cmdlet doesn't generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="99f63-231">-Path</span><span class="sxs-lookup"><span data-stu-id="99f63-231">-Path</span></span>

<span data-ttu-id="99f63-232">Задает путь к файлу исходного кода или DLL-файлам сборки, содержащей типы.</span><span class="sxs-lookup"><span data-stu-id="99f63-232">Specifies the path to source code files or assembly DLL files that contain the types.</span></span>

<span data-ttu-id="99f63-233">При отправке файлов исходного кода `Add-Type` компилирует код в файлы и создает сборку типов в памяти.</span><span class="sxs-lookup"><span data-stu-id="99f63-233">If you submit source code files, `Add-Type` compiles the code in the files and creates an in-memory assembly of the types.</span></span> <span data-ttu-id="99f63-234">Расширение файла, указанное в значении **path** , определяет компилятор, который `Add-Type` использует.</span><span class="sxs-lookup"><span data-stu-id="99f63-234">The file extension specified in the value of **Path** determines the compiler that `Add-Type` uses.</span></span>

<span data-ttu-id="99f63-235">При отправке файла сборки `Add-Type` принимает типы из сборки.</span><span class="sxs-lookup"><span data-stu-id="99f63-235">If you submit an assembly file, `Add-Type` takes the types from the assembly.</span></span> <span data-ttu-id="99f63-236">Чтобы указать сборку в памяти или глобальный кэш сборок, используйте параметр **AssemblyName**.</span><span class="sxs-lookup"><span data-stu-id="99f63-236">To specify an in-memory assembly or the global assembly cache, use the **AssemblyName** parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FromPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="99f63-237">-Референцедассемблиес</span><span class="sxs-lookup"><span data-stu-id="99f63-237">-ReferencedAssemblies</span></span>

<span data-ttu-id="99f63-238">Указывает сборки, от которых зависит тип.</span><span class="sxs-lookup"><span data-stu-id="99f63-238">Specifies the assemblies upon which the type depends.</span></span> <span data-ttu-id="99f63-239">По умолчанию `Add-Type` ссылки `System.dll` и `System.Management.Automation.dll` .</span><span class="sxs-lookup"><span data-stu-id="99f63-239">By default, `Add-Type` references `System.dll` and `System.Management.Automation.dll`.</span></span> <span data-ttu-id="99f63-240">Ссылки на сборки, указываемые этим параметром, создаются в дополнение к сборкам по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="99f63-240">The assemblies that you specify by using this parameter are referenced in addition to the default assemblies.</span></span>

<span data-ttu-id="99f63-241">Начиная с PowerShell 6, **референцедассемблиес** не включает сборки .NET по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="99f63-241">Beginning in PowerShell 6, **ReferencedAssemblies** doesn't include the default .NET assemblies.</span></span> <span data-ttu-id="99f63-242">В значение, передаваемое этому параметру, необходимо включить определенную ссылку на них.</span><span class="sxs-lookup"><span data-stu-id="99f63-242">You must include a specific reference to them in the value passed to this parameter.</span></span>

<span data-ttu-id="99f63-243">В одной команде нельзя использовать параметры **компилероптионс** и **референцедассемблиес** .</span><span class="sxs-lookup"><span data-stu-id="99f63-243">You can't use the **CompilerOptions** and **ReferencedAssemblies** parameters in the same command.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FromSource, FromMember, FromPath, FromLiteralPath
Aliases: RA

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="99f63-244">-Типедефинитион</span><span class="sxs-lookup"><span data-stu-id="99f63-244">-TypeDefinition</span></span>

<span data-ttu-id="99f63-245">Указывает исходный код, содержащий определения типов.</span><span class="sxs-lookup"><span data-stu-id="99f63-245">Specifies the source code that contains the type definitions.</span></span> <span data-ttu-id="99f63-246">Введите исходный код в строку или автономную строку либо введите переменную, которая содержит исходный код.</span><span class="sxs-lookup"><span data-stu-id="99f63-246">Enter the source code in a string or here-string, or enter a variable that contains the source code.</span></span> <span data-ttu-id="99f63-247">Дополнительные сведения о строках см. в разделе [about_Quoting_Rules](../Microsoft.PowerShell.Core/about/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="99f63-247">For more information about here-strings, see [about_Quoting_Rules](../Microsoft.PowerShell.Core/about/about_Quoting_Rules.md).</span></span>

<span data-ttu-id="99f63-248">Включите объявление пространства имен в определение типа.</span><span class="sxs-lookup"><span data-stu-id="99f63-248">Include a namespace declaration in your type definition.</span></span> <span data-ttu-id="99f63-249">Если опустить объявление пространства имен, имя типа может совпасть с именем или ярлыком другого типа, вызывая непреднамеренную перезапись.</span><span class="sxs-lookup"><span data-stu-id="99f63-249">If you omit the namespace declaration, your type might have the same name as another type or the shortcut for another type, causing an unintentional overwrite.</span></span> <span data-ttu-id="99f63-250">Например, если определить тип с именем **Exception**, скрипты, использующие **исключение** в качестве ярлыка для **System. Exception** , завершатся ошибкой.</span><span class="sxs-lookup"><span data-stu-id="99f63-250">For example, if you define a type called **Exception**, scripts that use **Exception** as the shortcut for **System.Exception** will fail.</span></span>

```yaml
Type: System.String
Parameter Sets: FromSource
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="99f63-251">-Усингнамеспаце</span><span class="sxs-lookup"><span data-stu-id="99f63-251">-UsingNamespace</span></span>

<span data-ttu-id="99f63-252">Задает другие пространства имен, которые требуются для класса.</span><span class="sxs-lookup"><span data-stu-id="99f63-252">Specifies other namespaces that are required for the class.</span></span> <span data-ttu-id="99f63-253">Это очень похоже на ключевое слово C# `Using` .</span><span class="sxs-lookup"><span data-stu-id="99f63-253">This is much like the C# keyword, `Using`.</span></span>

<span data-ttu-id="99f63-254">По умолчанию `Add-Type` ссылается на пространство имен **System** .</span><span class="sxs-lookup"><span data-stu-id="99f63-254">By default, `Add-Type` references the **System** namespace.</span></span> <span data-ttu-id="99f63-255">При использовании параметра **MemberDefinition** `Add-Type` также ссылается на пространство имен **System. Runtime. InteropServices** по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="99f63-255">When the **MemberDefinition** parameter is used, `Add-Type` also references the **System.Runtime.InteropServices** namespace by default.</span></span> <span data-ttu-id="99f63-256">Ссылки на пространства имен, добавляемые с помощью **UsingNamespace**, создаются в дополнение к пространствами имен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="99f63-256">The namespaces that you add by using the **UsingNamespace** parameter are referenced in addition to the default namespaces.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FromMember
Aliases: Using

Required: False
Position: Named
Default value: System namespace
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="99f63-257">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="99f63-257">CommonParameters</span></span>

<span data-ttu-id="99f63-258">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="99f63-258">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="99f63-259">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="99f63-259">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="99f63-260">Входные данные</span><span class="sxs-lookup"><span data-stu-id="99f63-260">INPUTS</span></span>

### <span data-ttu-id="99f63-261">None</span><span class="sxs-lookup"><span data-stu-id="99f63-261">None</span></span>

<span data-ttu-id="99f63-262">Вы не можете отправить объекты по конвейеру в `Add-Type` .</span><span class="sxs-lookup"><span data-stu-id="99f63-262">You can't send objects down the pipeline to `Add-Type`.</span></span>

## <span data-ttu-id="99f63-263">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="99f63-263">OUTPUTS</span></span>

### <span data-ttu-id="99f63-264">None или System. Type</span><span class="sxs-lookup"><span data-stu-id="99f63-264">None or System.Type</span></span>

<span data-ttu-id="99f63-265">При использовании параметра **PassThru** `Add-Type` возвращает объект **System. Type** , представляющий новый тип.</span><span class="sxs-lookup"><span data-stu-id="99f63-265">When you use the **PassThru** parameter, `Add-Type` returns a **System.Type** object that represents the new type.</span></span> <span data-ttu-id="99f63-266">В противном случае этот командлет не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="99f63-266">Otherwise, this cmdlet doesn't generate any output.</span></span>

## <span data-ttu-id="99f63-267">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="99f63-267">NOTES</span></span>

<span data-ttu-id="99f63-268">Добавляемые типы существуют только в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="99f63-268">The types that you add exist only in the current session.</span></span> <span data-ttu-id="99f63-269">Чтобы использовать типы во всех сеансах, добавьте их в профиль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99f63-269">To use the types in all sessions, add them to your PowerShell profile.</span></span> <span data-ttu-id="99f63-270">Дополнительные сведения о профиле см. в разделе [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="99f63-270">For more information about the profile, see [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

<span data-ttu-id="99f63-271">Имена типов и пространства имен должны быть уникальными в пределах сеанса.</span><span class="sxs-lookup"><span data-stu-id="99f63-271">Type names and namespaces must be unique within a session.</span></span> <span data-ttu-id="99f63-272">Невозможно выгрузить тип или изменить его.</span><span class="sxs-lookup"><span data-stu-id="99f63-272">You can't unload a type or change it.</span></span> <span data-ttu-id="99f63-273">Если необходимо изменить код для типа, необходимо изменить имя или запустить новый сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99f63-273">If you need to change the code for a type, you must change the name or start a new PowerShell session.</span></span>
<span data-ttu-id="99f63-274">В противном случае произойдет сбой команды.</span><span class="sxs-lookup"><span data-stu-id="99f63-274">Otherwise, the command fails.</span></span>

<span data-ttu-id="99f63-275">В Windows PowerShell (версия 5,1 и более ранние версии) необходимо использовать `Add-Type` для всех компонентов, которые еще не загружены.</span><span class="sxs-lookup"><span data-stu-id="99f63-275">In Windows PowerShell (version 5.1 and below), you need to use `Add-Type` for anything that isn't already loaded.</span></span> <span data-ttu-id="99f63-276">Чаще всего это относится к сборкам, находящихся в глобальном кэше сборок (GAC).</span><span class="sxs-lookup"><span data-stu-id="99f63-276">Most commonly, this applies to assemblies found in the Global Assembly Cache (GAC).</span></span>
<span data-ttu-id="99f63-277">В PowerShell 6 и более поздних версий отсутствует глобальный кэш сборок, поэтому PowerShell устанавливает собственные сборки в `$PSHome` .</span><span class="sxs-lookup"><span data-stu-id="99f63-277">In PowerShell 6 and higher, there is no GAC, so PowerShell installs its own assemblies in `$PSHome`.</span></span>
<span data-ttu-id="99f63-278">Эти сборки автоматически загружаются по запросу, поэтому их не нужно использовать `Add-Type` для их загрузки.</span><span class="sxs-lookup"><span data-stu-id="99f63-278">These assemblies are automatically loaded on request, so there's no need to use `Add-Type` to load them.</span></span> <span data-ttu-id="99f63-279">Тем не менее, использование имеет разрешение на `Add-Type` разрешение неявной совместимости скриптов с любой версией PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99f63-279">However, using `Add-Type` is still permitted to allow scripts to be implicitly compatible with any version of PowerShell.</span></span>

<span data-ttu-id="99f63-280">Сборки в глобальном кэше сборок могут загружаться по имени типа, а не по пути.</span><span class="sxs-lookup"><span data-stu-id="99f63-280">Assemblies in the GAC can be loaded by type name, rather than by path.</span></span> <span data-ttu-id="99f63-281">Для загрузки сборок из произвольного пути требуется `Add-Type` , так как эти сборки не могут быть загружены автоматически.</span><span class="sxs-lookup"><span data-stu-id="99f63-281">Loading assemblies from an arbitrary path requires `Add-Type`, since those assemblies cannot not be loaded automatically.</span></span>

## <span data-ttu-id="99f63-282">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="99f63-282">RELATED LINKS</span></span>

[<span data-ttu-id="99f63-283">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="99f63-283">about_Profiles</span></span>](../Microsoft.PowerShell.Core/About/about_profiles.md)

[<span data-ttu-id="99f63-284">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="99f63-284">about_Quoting_Rules</span></span>](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="99f63-285">Add-Member</span><span class="sxs-lookup"><span data-stu-id="99f63-285">Add-Member</span></span>](Add-Member.md)

[<span data-ttu-id="99f63-286">New-Object</span><span class="sxs-lookup"><span data-stu-id="99f63-286">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="99f63-287">аутпутассемблитипе</span><span class="sxs-lookup"><span data-stu-id="99f63-287">OutputAssemblyType</span></span>](/dotnet/api/microsoft.powershell.commands.outputassemblytype)

[<span data-ttu-id="99f63-288">Вызов неуправляемого кода (P/Invoke)</span><span class="sxs-lookup"><span data-stu-id="99f63-288">Platform Invoke (P/Invoke)</span></span>](/dotnet/standard/native-interop/pinvoke)

[<span data-ttu-id="99f63-289">Where-Object</span><span class="sxs-lookup"><span data-stu-id="99f63-289">Where-Object</span></span>](../Microsoft.PowerShell.Core/Where-Object.md)
