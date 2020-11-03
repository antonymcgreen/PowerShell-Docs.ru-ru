---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/add-type?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-Type
ms.openlocfilehash: af7cd937ccfc7c5f05fd0213764ed51a3ba9f2bb
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227745"
---
# <span data-ttu-id="76a10-103">Add-Type</span><span class="sxs-lookup"><span data-stu-id="76a10-103">Add-Type</span></span>

## <span data-ttu-id="76a10-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="76a10-104">SYNOPSIS</span></span>
<span data-ttu-id="76a10-105">Добавляет класс Microsoft .NET Framework в сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="76a10-105">Adds a Microsoft .NET Framework class to a PowerShell session.</span></span>

## <span data-ttu-id="76a10-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="76a10-106">SYNTAX</span></span>

### <span data-ttu-id="76a10-107">Фромсаурце (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="76a10-107">FromSource (Default)</span></span>

```
Add-Type [-CodeDomProvider <CodeDomProvider>] [-CompilerParameters <CompilerParameters>]
 [-TypeDefinition] <String> [-Language <Language>] [-ReferencedAssemblies <String[]>]
 [-OutputAssembly <String>] [-OutputType <OutputAssemblyType>] [-PassThru] [-IgnoreWarnings]
 [<CommonParameters>]
```

### <span data-ttu-id="76a10-108">фроммембер</span><span class="sxs-lookup"><span data-stu-id="76a10-108">FromMember</span></span>

```
Add-Type [-CodeDomProvider <CodeDomProvider>] [-CompilerParameters <CompilerParameters>]
 [-Name] <String> [-MemberDefinition] <String[]> [-Namespace <String>] [-UsingNamespace <String[]>]
 [-Language <Language>] [-ReferencedAssemblies <String[]>] [-OutputAssembly <String>]
 [-OutputType <OutputAssemblyType>] [-PassThru] [-IgnoreWarnings] [<CommonParameters>]
```

### <span data-ttu-id="76a10-109">фромпас</span><span class="sxs-lookup"><span data-stu-id="76a10-109">FromPath</span></span>

```
Add-Type [-CompilerParameters <CompilerParameters>] [-Path] <String[]>
 [-ReferencedAssemblies <String[]>] [-OutputAssembly <String>] [-OutputType <OutputAssemblyType>]
 [-PassThru] [-IgnoreWarnings] [<CommonParameters>]
```

### <span data-ttu-id="76a10-110">фромлитералпас</span><span class="sxs-lookup"><span data-stu-id="76a10-110">FromLiteralPath</span></span>

```
Add-Type [-CompilerParameters <CompilerParameters>] -LiteralPath <String[]>
 [-ReferencedAssemblies <String[]>] [-OutputAssembly <String>] [-OutputType <OutputAssemblyType>]
 [-PassThru] [-IgnoreWarnings] [<CommonParameters>]
```

### <span data-ttu-id="76a10-111">фромассемблинаме</span><span class="sxs-lookup"><span data-stu-id="76a10-111">FromAssemblyName</span></span>

```
Add-Type -AssemblyName <String[]> [-PassThru] [-IgnoreWarnings] [<CommonParameters>]
```

## <span data-ttu-id="76a10-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="76a10-112">DESCRIPTION</span></span>

<span data-ttu-id="76a10-113">`Add-Type`Командлет позволяет определить класс Microsoft .NET Framework в сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="76a10-113">The `Add-Type` cmdlet lets you define a Microsoft .NET Framework class in your PowerShell session.</span></span>
<span data-ttu-id="76a10-114">Затем можно создать экземпляры объектов с помощью `New-Object` командлета и использовать объекты так же, как любой объект .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="76a10-114">You can then instantiate objects, by using the `New-Object` cmdlet, and use the objects just as you would use any .NET Framework object.</span></span> <span data-ttu-id="76a10-115">При добавлении `Add-Type` команды в профиль PowerShell класс доступен во всех сеансах PowerShell.</span><span class="sxs-lookup"><span data-stu-id="76a10-115">If you add an `Add-Type` command to your PowerShell profile, the class is available in all PowerShell sessions.</span></span>

<span data-ttu-id="76a10-116">Тип можно указать, указав существующую сборку или файлы исходного кода. Кроме того, можно указать встроенный или сохраненный в переменной исходный код.</span><span class="sxs-lookup"><span data-stu-id="76a10-116">You can specify the type by specifying an existing assembly or source code files, or you can specify the source code inline or saved in a variable.</span></span> <span data-ttu-id="76a10-117">Можно даже указать только метод и `Add-Type` определить и создать класс.</span><span class="sxs-lookup"><span data-stu-id="76a10-117">You can even specify only a method and `Add-Type` will define and generate the class.</span></span> <span data-ttu-id="76a10-118">В Windows эту функцию можно использовать для вызова неуправляемых функций (P/Invoke) в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="76a10-118">On Windows, you can use this feature to make Platform Invoke (P/Invoke) calls to unmanaged functions in PowerShell.</span></span> <span data-ttu-id="76a10-119">Если указан исходный код, `Add-Type` компилирует указанный исходный код и создает сборку в памяти, содержащую новые типы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="76a10-119">If you specify source code, `Add-Type` compiles the specified source code and generates an in-memory assembly that contains the new .NET Framework types.</span></span>

<span data-ttu-id="76a10-120">`Add-Type`Для указания альтернативного языка и компилятора можно использовать параметры, C# — это по умолчанию, параметры компилятора, зависимости сборок, пространство имен класса, имена типа и результирующая сборка.</span><span class="sxs-lookup"><span data-stu-id="76a10-120">You can use the parameters of `Add-Type` to specify an alternate language and compiler, C# is the default, compiler options, assembly dependencies, the class namespace, the names of the type, and the resulting assembly.</span></span>

## <span data-ttu-id="76a10-121">Примеры</span><span class="sxs-lookup"><span data-stu-id="76a10-121">EXAMPLES</span></span>

### <span data-ttu-id="76a10-122">Пример 1. Добавление типа .NET в сеанс</span><span class="sxs-lookup"><span data-stu-id="76a10-122">Example 1: Add a .NET type to a session</span></span>

<span data-ttu-id="76a10-123">В этом примере класс **BasicTest** добавляется в сеанс путем указания исходного кода, хранящегося в переменной.</span><span class="sxs-lookup"><span data-stu-id="76a10-123">This example adds the **BasicTest** class to the session by specifying source code that is stored in a variable.</span></span> <span data-ttu-id="76a10-124">Класс **BasicTest** используется для добавления целых чисел, создания объекта и умножения целых чисел.</span><span class="sxs-lookup"><span data-stu-id="76a10-124">The **BasicTest** class is used to add integers, create an object, and multiply integers.</span></span>

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

<span data-ttu-id="76a10-125">`$Source`Переменная хранит исходный код для класса.</span><span class="sxs-lookup"><span data-stu-id="76a10-125">The `$Source` variable stores the source code for the class.</span></span> <span data-ttu-id="76a10-126">Тип имеет вызванный статический метод `Add` и метод, не являющийся статическим `Multiply` .</span><span class="sxs-lookup"><span data-stu-id="76a10-126">The type has a static method called `Add` and a non-static method called `Multiply`.</span></span>

<span data-ttu-id="76a10-127">`Add-Type`Командлет добавляет класс в сеанс.</span><span class="sxs-lookup"><span data-stu-id="76a10-127">The `Add-Type` cmdlet adds the class to the session.</span></span> <span data-ttu-id="76a10-128">Так как он использует встроенный исходный код, команда использует параметр **типедефинитион** для указания кода в `$Source` переменной.</span><span class="sxs-lookup"><span data-stu-id="76a10-128">Because it's using inline source code, the command uses the **TypeDefinition** parameter to specify the code in the `$Source` variable.</span></span>

<span data-ttu-id="76a10-129">`Add`Статический метод класса **BasicTest** использует символы двойного двоеточия ( `::` ) для указания статического члена класса.</span><span class="sxs-lookup"><span data-stu-id="76a10-129">The `Add` static method of the **BasicTest** class uses the double-colon characters (`::`) to specify a static member of the class.</span></span> <span data-ttu-id="76a10-130">Добавляются целые числа и отображается сумма.</span><span class="sxs-lookup"><span data-stu-id="76a10-130">The integers are added and the sum is displayed.</span></span>

<span data-ttu-id="76a10-131">`New-Object`Командлет создает экземпляр класса **BasicTest** .</span><span class="sxs-lookup"><span data-stu-id="76a10-131">The `New-Object` cmdlet instantiates an instance of the **BasicTest** class.</span></span> <span data-ttu-id="76a10-132">Он сохраняет новый объект в `$BasicTestObject` переменной.</span><span class="sxs-lookup"><span data-stu-id="76a10-132">It saves the new object in the `$BasicTestObject` variable.</span></span>

<span data-ttu-id="76a10-133">`$BasicTestObject` использует `Multiply` метод.</span><span class="sxs-lookup"><span data-stu-id="76a10-133">`$BasicTestObject` uses the `Multiply` method.</span></span> <span data-ttu-id="76a10-134">Целые числа умножаются, а продукт отображается.</span><span class="sxs-lookup"><span data-stu-id="76a10-134">The integers are multiplied and the product is displayed.</span></span>

### <span data-ttu-id="76a10-135">Пример 2. Проверка добавленного типа</span><span class="sxs-lookup"><span data-stu-id="76a10-135">Example 2: Examine an added type</span></span>

<span data-ttu-id="76a10-136">В этом примере `Get-Member` командлет используется для проверки объектов, `Add-Type` `New-Object` созданных командлетами и, в **примере 1** .</span><span class="sxs-lookup"><span data-stu-id="76a10-136">This example uses the `Get-Member` cmdlet to examine the objects that the `Add-Type` and `New-Object` cmdlets created in **Example 1** .</span></span>

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

<span data-ttu-id="76a10-137">`Get-Member`Командлет возвращает тип и члены класса **BasicTest** , `Add-Type` добавленные в сеанс.</span><span class="sxs-lookup"><span data-stu-id="76a10-137">The `Get-Member` cmdlet gets the type and members of the **BasicTest** class that `Add-Type` added to the session.</span></span> <span data-ttu-id="76a10-138">`Get-Member`Команда обнаруживает, что это объект **System. RuntimeType** , производный от класса **System. Object** .</span><span class="sxs-lookup"><span data-stu-id="76a10-138">The `Get-Member` command reveals that it's a **System.RuntimeType** object, which is derived from the **System.Object** class.</span></span>

<span data-ttu-id="76a10-139">`Get-Member` **Статический** параметр получает статические свойства и методы класса **BasicTest** .</span><span class="sxs-lookup"><span data-stu-id="76a10-139">The `Get-Member` **Static** parameter gets the static properties and methods of the **BasicTest** class.</span></span> <span data-ttu-id="76a10-140">Выходные данные показывают, что `Add` метод включен.</span><span class="sxs-lookup"><span data-stu-id="76a10-140">The output shows that the `Add` method is included.</span></span>

<span data-ttu-id="76a10-141">`Get-Member`Командлет возвращает элементы объекта, хранящегося в `$BasicTestObject` переменной.</span><span class="sxs-lookup"><span data-stu-id="76a10-141">The `Get-Member` cmdlet gets the members of the object stored in the `$BasicTestObject` variable.</span></span>
<span data-ttu-id="76a10-142">`$BasicTestObject` был создан с помощью `New-Object` командлета с классом **BasicTest** .</span><span class="sxs-lookup"><span data-stu-id="76a10-142">`$BasicTestObject` was created by using the `New-Object` cmdlet with the **BasicTest** class.</span></span> <span data-ttu-id="76a10-143">Результат показывает, что значение `$BasicTestObject` переменной является экземпляром класса **BasicTest** и включает член с именем `Multiply` .</span><span class="sxs-lookup"><span data-stu-id="76a10-143">The output reveals that the value of the `$BasicTestObject` variable is an instance of the **BasicTest** class and that it includes a member called `Multiply`.</span></span>

### <span data-ttu-id="76a10-144">Пример 3. Добавление типов из сборки</span><span class="sxs-lookup"><span data-stu-id="76a10-144">Example 3: Add types from an assembly</span></span>

<span data-ttu-id="76a10-145">В этом примере классы из сборки добавляются `Accessibility.dll` в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="76a10-145">This example adds the classes from the `Accessibility.dll` assembly to the current session.</span></span>

```powershell
$AccType = Add-Type -AssemblyName "accessib*" -PassThru
```

<span data-ttu-id="76a10-146">`$AccType`Переменная хранит объект, созданный с помощью `Add-Type` командлета.</span><span class="sxs-lookup"><span data-stu-id="76a10-146">The `$AccType` variable stores an object created with the `Add-Type` cmdlet.</span></span> <span data-ttu-id="76a10-147">`Add-Type` использует параметр **AssemblyName** для указания имени сборки.</span><span class="sxs-lookup"><span data-stu-id="76a10-147">`Add-Type` uses the **AssemblyName** parameter to specify the name of the assembly.</span></span> <span data-ttu-id="76a10-148">`*`Подстановочный знак звездочки () позволяет получить правильную сборку, даже если вы не уверены в ее имени или ее написании.</span><span class="sxs-lookup"><span data-stu-id="76a10-148">The asterisk (`*`) wildcard character allows you to get the correct assembly even when you aren't sure of the name or its spelling.</span></span> <span data-ttu-id="76a10-149">Параметр **PassThru** создает объекты, представляющие классы, которые добавляются в сеанс.</span><span class="sxs-lookup"><span data-stu-id="76a10-149">The **PassThru** parameter generates objects that represent the classes that are added to the session.</span></span>

### <span data-ttu-id="76a10-150">Пример 4. вызов собственных интерфейсов API Windows</span><span class="sxs-lookup"><span data-stu-id="76a10-150">Example 4: Call native Windows APIs</span></span>

<span data-ttu-id="76a10-151">В этом примере показано, как вызывать собственные API Windows в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="76a10-151">This example demonstrates how to call native Windows APIs in PowerShell.</span></span> <span data-ttu-id="76a10-152">`Add-Type` использует механизм вызова неуправляемого кода (P/Invoke) для вызова функции `User32.dll` из PowerShell.</span><span class="sxs-lookup"><span data-stu-id="76a10-152">`Add-Type` uses the Platform Invoke (P/Invoke) mechanism to call a function in `User32.dll` from PowerShell.</span></span> <span data-ttu-id="76a10-153">Этот пример работает только на компьютерах под управлением операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="76a10-153">This example only works on computers running the Windows operating system.</span></span>

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

<span data-ttu-id="76a10-154">`$Signature`Переменная хранит сигнатуру C# `ShowWindowAsync` функции.</span><span class="sxs-lookup"><span data-stu-id="76a10-154">The `$Signature` variable stores the C# signature of the `ShowWindowAsync` function.</span></span> <span data-ttu-id="76a10-155">Чтобы убедиться, что полученный метод будет виден в сеансе PowerShell, `public` ключевое слово было добавлено к стандартной сигнатуре.</span><span class="sxs-lookup"><span data-stu-id="76a10-155">To ensure that the resulting method will be visible in a PowerShell session, the `public` keyword was added to the standard signature.</span></span> <span data-ttu-id="76a10-156">Дополнительные сведения см. в разделе [функция showWindowAsync](/windows/win32/api/winuser/nf-winuser-showwindowasync).</span><span class="sxs-lookup"><span data-stu-id="76a10-156">For more information, see [ShowWindowAsync function](/windows/win32/api/winuser/nf-winuser-showwindowasync).</span></span>

<span data-ttu-id="76a10-157">`$ShowWindowAsync`Переменная хранит объект, созданный `Add-Type` параметром **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="76a10-157">The `$ShowWindowAsync` variable stores the object created by the `Add-Type` **PassThru** parameter.</span></span>
<span data-ttu-id="76a10-158">`Add-Type`Командлет добавляет `ShowWindowAsync` функцию в сеанс PowerShell как статический метод.</span><span class="sxs-lookup"><span data-stu-id="76a10-158">The `Add-Type` cmdlet adds the `ShowWindowAsync` function to the PowerShell session as a static method.</span></span> <span data-ttu-id="76a10-159">Команда использует параметр **MemberDefinition** для указания определения метода, сохраненного в `$Signature` переменной.</span><span class="sxs-lookup"><span data-stu-id="76a10-159">The command uses the **MemberDefinition** parameter to specify the method definition saved in the `$Signature` variable.</span></span> <span data-ttu-id="76a10-160">Команда использует параметры **Name** и **Namespace** , чтобы указать имя и пространство имен для класса.</span><span class="sxs-lookup"><span data-stu-id="76a10-160">The command uses the **Name** and **Namespace** parameters to specify a name and namespace for the class.</span></span> <span data-ttu-id="76a10-161">Параметр **PassThru** создает объект, представляющий типы.</span><span class="sxs-lookup"><span data-stu-id="76a10-161">The **PassThru** parameter generates an object that represents the types.</span></span>

<span data-ttu-id="76a10-162">Новый `ShowWindowAsync` статический метод используется в командах для сворачивания и восстановления консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="76a10-162">The new `ShowWindowAsync` static method is used in the commands to minimize and restore the PowerShell console.</span></span> <span data-ttu-id="76a10-163">Метод принимает два параметра: маркер окна и целое число, которое указывает, как отображается окно.</span><span class="sxs-lookup"><span data-stu-id="76a10-163">The method takes two parameters: the window handle, and an integer that specifies how the window is displayed.</span></span>

<span data-ttu-id="76a10-164">Для сворачивания консоли PowerShell `ShowWindowAsync` использует `Get-Process` командлет с `$PID` автоматической переменной для получения процесса, в котором размещается текущий сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="76a10-164">To minimize the PowerShell console, `ShowWindowAsync` uses the `Get-Process` cmdlet with the `$PID` automatic variable to get the process that is hosting the current PowerShell session.</span></span> <span data-ttu-id="76a10-165">Затем используется свойство **маинвиндовхандле** текущего процесса и значение `2` , представляющее `SW_MINIMIZE` значение.</span><span class="sxs-lookup"><span data-stu-id="76a10-165">Then it uses the **MainWindowHandle** property of the current process and a value of `2`, which represents the `SW_MINIMIZE` value.</span></span>

<span data-ttu-id="76a10-166">Для восстановления окна `ShowWindowAsync` использует значение `4` для расположения окна, которое представляет `SW_RESTORE` значение.</span><span class="sxs-lookup"><span data-stu-id="76a10-166">To restore the window, `ShowWindowAsync` uses a value of `4` for the window position, which represents the `SW_RESTORE` value.</span></span>

<span data-ttu-id="76a10-167">Чтобы развернуть окно, используйте значение `3` , представляющее `SW_MAXIMIZE` .</span><span class="sxs-lookup"><span data-stu-id="76a10-167">To maximize the window, use the value of `3` that represents `SW_MAXIMIZE`.</span></span>

### <span data-ttu-id="76a10-168">Пример 5. Добавление типа из файла Visual Basic</span><span class="sxs-lookup"><span data-stu-id="76a10-168">Example 5: Add a type from a Visual Basic file</span></span>

<span data-ttu-id="76a10-169">В этом примере `Add-Type` командлет используется для добавления класса **вбфромфиле** , который определен в файле, в `Hello.vb` текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="76a10-169">This example uses the `Add-Type` cmdlet to add the **VBFromFile** class that's defined in the `Hello.vb` file to the current session.</span></span> <span data-ttu-id="76a10-170">Текст `Hello.vb` файла отображается в выходных данных команды.</span><span class="sxs-lookup"><span data-stu-id="76a10-170">The text of the `Hello.vb` file is shown in the command output.</span></span>

```powershell
Add-Type -Path "C:\PS-Test\Hello.vb"
[VBFromFile]::SayHello(", World")

# From Hello.vb

Public Class VBFromFile
  Public Shared Function SayHello(sourceName As String) As String
    Dim myValue As String = "Hello"
    return myValue + sourceName
  End Function
End Class
```

```Output
Hello, World
```

<span data-ttu-id="76a10-171">`Add-Type` использует параметр **path** для указания исходного файла `Hello.vb` и добавляет тип, определенный в файле.</span><span class="sxs-lookup"><span data-stu-id="76a10-171">`Add-Type` uses the **Path** parameter to specify the source file, `Hello.vb`, and adds the type defined in the file.</span></span> <span data-ttu-id="76a10-172">`SayHello`Функция вызывается как статический метод класса **вбфромфиле** .</span><span class="sxs-lookup"><span data-stu-id="76a10-172">The `SayHello` function is called as a static method of the **VBFromFile** class.</span></span>

### <span data-ttu-id="76a10-173">Пример 6. Добавление класса с помощью JScript.NET</span><span class="sxs-lookup"><span data-stu-id="76a10-173">Example 6: Add a class with JScript.NET</span></span>

<span data-ttu-id="76a10-174">В этом примере используется JScript.NET для создания нового класса **фректангле** в сеансе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="76a10-174">This example uses JScript.NET to create a new class, **FRectangle** , in your PowerShell session.</span></span>

```powershell
Add-Type @'
 class FRectangle {
   var Length : double;
   var Height : double;
   function Perimeter() : double {
       return (Length + Height) * 2; }
   function Area() : double {
       return Length * Height;  } }
'@ -Language JScript

$rect = [FRectangle]::new()
$rect
```

```Output
Length Height
------ ------
     0      0
```

### <span data-ttu-id="76a10-175">Пример 7. Добавление компилятора F #</span><span class="sxs-lookup"><span data-stu-id="76a10-175">Example 7: Add an F# compiler</span></span>

<span data-ttu-id="76a10-176">В этом примере показано, как с помощью `Add-Type` командлета добавить компилятор кода F # в сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="76a10-176">This example shows how to use the `Add-Type` cmdlet to add an F# code compiler to your PowerShell session.</span></span> <span data-ttu-id="76a10-177">Чтобы выполнить этот пример в PowerShell, необходимо `FSharp.Compiler.CodeDom.dll` установить компонент, установленный с языком F #.</span><span class="sxs-lookup"><span data-stu-id="76a10-177">To run this example in PowerShell, you must have the `FSharp.Compiler.CodeDom.dll` that is installed with the F# language.</span></span>

```powershell
Add-Type -Path "FSharp.Compiler.CodeDom.dll"
$Provider = New-Object Microsoft.FSharp.Compiler.CodeDom.FSharpCodeProvider
$FSharpCode = @"
let rec loop n =if n <= 0 then () else beginprint_endline (string_of_int n);loop (n-1)end
"@
$FSharpType = Add-Type -TypeDefinition $FSharpCode -CodeDomProvider $Provider -PassThru |
   Where-Object { $_.IsPublic }
$FSharpType::loop(4)
```

```Output
4
3
2
1
```

<span data-ttu-id="76a10-178">`Add-Type` использует параметр **path** для указания сборки и возвращает типы в сборке.</span><span class="sxs-lookup"><span data-stu-id="76a10-178">`Add-Type` uses the **Path** parameter to specify an assembly and gets the types in the assembly.</span></span>
<span data-ttu-id="76a10-179">`New-Object` создает экземпляр поставщика кода F # и сохраняет результат в `$Provider` переменной.</span><span class="sxs-lookup"><span data-stu-id="76a10-179">`New-Object` creates an instance of the F# code provider and saves the result in the `$Provider` variable.</span></span> <span data-ttu-id="76a10-180">`$FSharpCode`Переменная сохраняет код F #, определяющий метод **Loop** .</span><span class="sxs-lookup"><span data-stu-id="76a10-180">The `$FSharpCode` variable saves the F# code that defines the **Loop** method.</span></span>

<span data-ttu-id="76a10-181">`$FSharpType`Переменная хранит результаты `Add-Type` командлета, сохраняющего открытые типы, определенные в `$FSharpCode` .</span><span class="sxs-lookup"><span data-stu-id="76a10-181">The the `$FSharpType` variable stores the results of the `Add-Type` cmdlet that saves the public types defined in `$FSharpCode`.</span></span> <span data-ttu-id="76a10-182">Параметр **TypeDefinition** указывает исходный код, который определяет типы.</span><span class="sxs-lookup"><span data-stu-id="76a10-182">The **TypeDefinition** parameter specifies the source code that defines the types.</span></span> <span data-ttu-id="76a10-183">Параметр **CodeDomProvider** указывает компилятор исходного кода.</span><span class="sxs-lookup"><span data-stu-id="76a10-183">The **CodeDomProvider** parameter specifies the source code compiler.</span></span> <span data-ttu-id="76a10-184">Параметр **PassThru** направляет `Add-Type` Возврат объекта **среды выполнения** , представляющего типы.</span><span class="sxs-lookup"><span data-stu-id="76a10-184">The **PassThru** parameter directs `Add-Type` to return a **Runtime** object that represents the types.</span></span>
<span data-ttu-id="76a10-185">Объекты отправляются по конвейеру в `Where-Object` командлет, который возвращает только открытые типы.</span><span class="sxs-lookup"><span data-stu-id="76a10-185">The objects are sent down the pipeline to the `Where-Object` cmdlet, which returns only the public types.</span></span> <span data-ttu-id="76a10-186">Используется командлет **Where-Object** , поскольку поставщик F # создает типы, не являющиеся открытыми, для поддержки полученного открытого типа.</span><span class="sxs-lookup"><span data-stu-id="76a10-186">The **Where-Object** cmdlet is used because the F# provider generates non-public types to support the resulting public type.</span></span>

<span data-ttu-id="76a10-187">Метод Loop вызывается как статический метод типа, хранящегося в `$FSharpType` переменной.</span><span class="sxs-lookup"><span data-stu-id="76a10-187">The Loop method is called as a static method of the type stored in the `$FSharpType` variable.</span></span>

## <span data-ttu-id="76a10-188">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="76a10-188">PARAMETERS</span></span>

### <span data-ttu-id="76a10-189">-AssemblyName</span><span class="sxs-lookup"><span data-stu-id="76a10-189">-AssemblyName</span></span>

<span data-ttu-id="76a10-190">Задает имя сборки, включающей типы.</span><span class="sxs-lookup"><span data-stu-id="76a10-190">Specifies the name of an assembly that includes the types.</span></span> <span data-ttu-id="76a10-191">`Add-Type` принимает типы из указанной сборки.</span><span class="sxs-lookup"><span data-stu-id="76a10-191">`Add-Type` takes the types from the specified assembly.</span></span> <span data-ttu-id="76a10-192">Этот параметр является обязательным при создании типов на основе имени сборки.</span><span class="sxs-lookup"><span data-stu-id="76a10-192">This parameter is required when you're creating types based on an assembly name.</span></span>

<span data-ttu-id="76a10-193">Введите полное или простое имя сборки, также называемое частичным именем.</span><span class="sxs-lookup"><span data-stu-id="76a10-193">Enter the full or simple name, also known as the partial name, of an assembly.</span></span> <span data-ttu-id="76a10-194">В именах сборок можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="76a10-194">Wildcard characters are permitted in the assembly name.</span></span> <span data-ttu-id="76a10-195">Если вы вводите простое или частичное имя, `Add-Type` разрешаете его в полное имя, а затем использует полное имя для загрузки сборки.</span><span class="sxs-lookup"><span data-stu-id="76a10-195">If you enter a simple or partial name, `Add-Type` resolves it to the full name, and then uses the full name to load the assembly.</span></span>

<span data-ttu-id="76a10-196">Этот параметр не принимает путь или имя файла.</span><span class="sxs-lookup"><span data-stu-id="76a10-196">This parameter doesn't accept a path or a file name.</span></span> <span data-ttu-id="76a10-197">Чтобы ввести путь к файлу библиотеки динамической компоновки (DLL) сборки, используйте параметр **path** .</span><span class="sxs-lookup"><span data-stu-id="76a10-197">To enter the path to the assembly dynamic-link library (DLL) file, use the **Path** parameter.</span></span>

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

### <span data-ttu-id="76a10-198">-CodeDomProvider</span><span class="sxs-lookup"><span data-stu-id="76a10-198">-CodeDomProvider</span></span>

<span data-ttu-id="76a10-199">Указывает генератор кода или компилятор.</span><span class="sxs-lookup"><span data-stu-id="76a10-199">Specifies a code generator or compiler.</span></span> <span data-ttu-id="76a10-200">`Add-Type` использует указанный компилятор для компиляции исходного кода.</span><span class="sxs-lookup"><span data-stu-id="76a10-200">`Add-Type` uses the specified compiler to compile the source code.</span></span> <span data-ttu-id="76a10-201">По умолчанию используется компилятор C#.</span><span class="sxs-lookup"><span data-stu-id="76a10-201">The default is the C# compiler.</span></span> <span data-ttu-id="76a10-202">Используйте этот параметр, если вы используете язык, который нельзя указать с помощью параметра **Language** .</span><span class="sxs-lookup"><span data-stu-id="76a10-202">Use this parameter if you're using a language that can't be specified by using the **Language** parameter.</span></span> <span data-ttu-id="76a10-203">Указанный **CodeDomProvider** должен иметь возможность создавать сборки из исходного кода.</span><span class="sxs-lookup"><span data-stu-id="76a10-203">The **CodeDomProvider** that you specify must be able to generate assemblies from source code.</span></span>

```yaml
Type: System.CodeDom.Compiler.CodeDomProvider
Parameter Sets: FromSource, FromMember
Aliases: Provider

Required: False
Position: Named
Default value: C# compiler
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="76a10-204">-CompilerParameters</span><span class="sxs-lookup"><span data-stu-id="76a10-204">-CompilerParameters</span></span>

<span data-ttu-id="76a10-205">Указывает параметры для компилятора исходного кода.</span><span class="sxs-lookup"><span data-stu-id="76a10-205">Specifies the options for the source code compiler.</span></span> <span data-ttu-id="76a10-206">Эти параметры отправляются в компилятор без проверки.</span><span class="sxs-lookup"><span data-stu-id="76a10-206">These options are sent to the compiler without revision.</span></span>

<span data-ttu-id="76a10-207">Этот параметр позволяет указать компилятору создать исполняемый файл, внедрить ресурсы или задать параметры командной строки, например `/unsafe` параметр.</span><span class="sxs-lookup"><span data-stu-id="76a10-207">This parameter allows you to direct the compiler to generate an executable file, embed resources, or set command-line options, such as the `/unsafe` option.</span></span> <span data-ttu-id="76a10-208">Этот параметр реализует класс **CompilerParameters** , **System. CodeDom. Compiler. CompilerParameters** .</span><span class="sxs-lookup"><span data-stu-id="76a10-208">This parameter implements the **CompilerParameters** class, **System.CodeDom.Compiler.CompilerParameters** .</span></span>

<span data-ttu-id="76a10-209">В одной команде нельзя использовать параметры **CompilerParameters** и **референцедассемблиес** .</span><span class="sxs-lookup"><span data-stu-id="76a10-209">You can't use the **CompilerParameters** and **ReferencedAssemblies** parameters in the same command.</span></span>

```yaml
Type: System.CodeDom.Compiler.CompilerParameters
Parameter Sets: FromSource, FromMember, FromPath, FromLiteralPath
Aliases: CP

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="76a10-210">-Игнореварнингс</span><span class="sxs-lookup"><span data-stu-id="76a10-210">-IgnoreWarnings</span></span>

<span data-ttu-id="76a10-211">Игнорирует предупреждения компилятора.</span><span class="sxs-lookup"><span data-stu-id="76a10-211">Ignores compiler warnings.</span></span> <span data-ttu-id="76a10-212">Используйте этот параметр, чтобы предотвратить `Add-Type` обработку предупреждений компилятора как ошибок.</span><span class="sxs-lookup"><span data-stu-id="76a10-212">Use this parameter to prevent `Add-Type` from handling compiler warnings as errors.</span></span>

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

### <span data-ttu-id="76a10-213">— Язык</span><span class="sxs-lookup"><span data-stu-id="76a10-213">-Language</span></span>

<span data-ttu-id="76a10-214">Задает язык, который используется в исходном коде.</span><span class="sxs-lookup"><span data-stu-id="76a10-214">Specifies the language that is used in the source code.</span></span> <span data-ttu-id="76a10-215">`Add-Type`Командлет использует значение этого параметра для выбора соответствующего **CodeDomProvider** .</span><span class="sxs-lookup"><span data-stu-id="76a10-215">The `Add-Type` cmdlet uses the value of this parameter to select the appropriate **CodeDomProvider** .</span></span> <span data-ttu-id="76a10-216">Значение по умолчанию — CSharp.</span><span class="sxs-lookup"><span data-stu-id="76a10-216">CSharp is the default value.</span></span> <span data-ttu-id="76a10-217">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="76a10-217">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="76a10-218">CSharp</span><span class="sxs-lookup"><span data-stu-id="76a10-218">CSharp</span></span>
- <span data-ttu-id="76a10-219">CSharpVersion2</span><span class="sxs-lookup"><span data-stu-id="76a10-219">CSharpVersion2</span></span>
- <span data-ttu-id="76a10-220">CSharpVersion3</span><span class="sxs-lookup"><span data-stu-id="76a10-220">CSharpVersion3</span></span>
- <span data-ttu-id="76a10-221">Язык JScript</span><span class="sxs-lookup"><span data-stu-id="76a10-221">JScript</span></span>
- <span data-ttu-id="76a10-222">VisualBasic</span><span class="sxs-lookup"><span data-stu-id="76a10-222">VisualBasic</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.Language
Parameter Sets: FromSource, FromMember
Aliases:
Accepted values: CSharp, CSharpVersion2, CSharpVersion3, JScript, VisualBasic

Required: False
Position: Named
Default value: CSharp
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="76a10-223">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="76a10-223">-LiteralPath</span></span>

<span data-ttu-id="76a10-224">Задает путь к файлу исходного кода или DLL-файлам сборки, содержащей типы.</span><span class="sxs-lookup"><span data-stu-id="76a10-224">Specifies the path to source code files or assembly DLL files that contain the types.</span></span> <span data-ttu-id="76a10-225">В отличие от **path** , значение параметра **LiteralPath** используется точно так же, как типизировано.</span><span class="sxs-lookup"><span data-stu-id="76a10-225">Unlike **Path** , the value of the **LiteralPath** parameter is used exactly as it's typed.</span></span> <span data-ttu-id="76a10-226">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="76a10-226">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="76a10-227">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="76a10-227">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="76a10-228">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="76a10-228">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FromLiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="76a10-229">-MemberDefinition</span><span class="sxs-lookup"><span data-stu-id="76a10-229">-MemberDefinition</span></span>

<span data-ttu-id="76a10-230">Указывает новые свойства или методы для класса.</span><span class="sxs-lookup"><span data-stu-id="76a10-230">Specifies new properties or methods for the class.</span></span> <span data-ttu-id="76a10-231">`Add-Type` создает код шаблона, необходимый для поддержки свойств или методов.</span><span class="sxs-lookup"><span data-stu-id="76a10-231">`Add-Type` generates the template code that is required to support the properties or methods.</span></span>

<span data-ttu-id="76a10-232">В Windows эту функцию можно использовать для вызова неуправляемых функций (P/Invoke) в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="76a10-232">On Windows, you can use this feature to make Platform Invoke (P/Invoke) calls to unmanaged functions in PowerShell.</span></span>

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

### <span data-ttu-id="76a10-233">-Name</span><span class="sxs-lookup"><span data-stu-id="76a10-233">-Name</span></span>

<span data-ttu-id="76a10-234">Задает имя создаваемого класса.</span><span class="sxs-lookup"><span data-stu-id="76a10-234">Specifies the name of the class to create.</span></span> <span data-ttu-id="76a10-235">Этот параметр является обязательным при создании типа из определения члена.</span><span class="sxs-lookup"><span data-stu-id="76a10-235">This parameter is required when generating a type from a member definition.</span></span>

<span data-ttu-id="76a10-236">Имя типа и пространство имен должны быть уникальными в пределах сеанса.</span><span class="sxs-lookup"><span data-stu-id="76a10-236">The type name and namespace must be unique within a session.</span></span> <span data-ttu-id="76a10-237">Невозможно выгрузить тип или изменить его.</span><span class="sxs-lookup"><span data-stu-id="76a10-237">You can't unload a type or change it.</span></span>
<span data-ttu-id="76a10-238">Чтобы изменить код для типа, необходимо изменить имя или запустить новый сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="76a10-238">To change the code for a type, you must change the name or start a new PowerShell session.</span></span>
<span data-ttu-id="76a10-239">В противном случае произойдет сбой команды.</span><span class="sxs-lookup"><span data-stu-id="76a10-239">Otherwise, the command fails.</span></span>

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

### <span data-ttu-id="76a10-240">-Namespace</span><span class="sxs-lookup"><span data-stu-id="76a10-240">-Namespace</span></span>

<span data-ttu-id="76a10-241">Задает пространство имен для типа.</span><span class="sxs-lookup"><span data-stu-id="76a10-241">Specifies a namespace for the type.</span></span>

<span data-ttu-id="76a10-242">Если этот параметр не включен в команду, тип создается в пространстве имен **Microsoft. PowerShell. Commands. аддтипе. аутоженератедтипес** .</span><span class="sxs-lookup"><span data-stu-id="76a10-242">If this parameter isn't included in the command, the type is created in the **Microsoft.PowerShell.Commands.AddType.AutoGeneratedTypes** namespace.</span></span> <span data-ttu-id="76a10-243">Если параметр включен в команду с пустым строковым значением или значением `$Null` , то тип создается в глобальном пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="76a10-243">If the parameter is included in the command with an empty string value or a value of `$Null`, the type is generated in the global namespace.</span></span>

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

### <span data-ttu-id="76a10-244">-Аутпутассембли</span><span class="sxs-lookup"><span data-stu-id="76a10-244">-OutputAssembly</span></span>

<span data-ttu-id="76a10-245">Создает DLL-файл для сборки с заданным именем в расположении.</span><span class="sxs-lookup"><span data-stu-id="76a10-245">Generates a DLL file for the assembly with the specified name in the location.</span></span> <span data-ttu-id="76a10-246">Введите необязательный путь и имя файла.</span><span class="sxs-lookup"><span data-stu-id="76a10-246">Enter an optional path and file name.</span></span> <span data-ttu-id="76a10-247">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="76a10-247">Wildcard characters are permitted.</span></span> <span data-ttu-id="76a10-248">По умолчанию `Add-Type` создает сборку только в памяти.</span><span class="sxs-lookup"><span data-stu-id="76a10-248">By default, `Add-Type` generates the assembly only in memory.</span></span>

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

### <span data-ttu-id="76a10-249">-OutputType</span><span class="sxs-lookup"><span data-stu-id="76a10-249">-OutputType</span></span>

<span data-ttu-id="76a10-250">Указывает тип вывода выходной сборки.</span><span class="sxs-lookup"><span data-stu-id="76a10-250">Specifies the output type of the output assembly.</span></span> <span data-ttu-id="76a10-251">По умолчанию тип вывода не указывается.</span><span class="sxs-lookup"><span data-stu-id="76a10-251">By default, no output type is specified.</span></span> <span data-ttu-id="76a10-252">Этот параметр допустим только в том случае, если в команде указана выходная сборка.</span><span class="sxs-lookup"><span data-stu-id="76a10-252">This parameter is valid only when an output assembly is specified in the command.</span></span> <span data-ttu-id="76a10-253">Дополнительные сведения о значениях см. в разделе [Аутпутассемблитипе enumeration](/dotnet/api/microsoft.powershell.commands.outputassemblytype).</span><span class="sxs-lookup"><span data-stu-id="76a10-253">For more information about the values, see [OutputAssemblyType Enumeration](/dotnet/api/microsoft.powershell.commands.outputassemblytype).</span></span>

<span data-ttu-id="76a10-254">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="76a10-254">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="76a10-255">консолеаппликатион</span><span class="sxs-lookup"><span data-stu-id="76a10-255">ConsoleApplication</span></span>
- <span data-ttu-id="76a10-256">Библиотека</span><span class="sxs-lookup"><span data-stu-id="76a10-256">Library</span></span>
- <span data-ttu-id="76a10-257">виндовсаппликатион</span><span class="sxs-lookup"><span data-stu-id="76a10-257">WindowsApplication</span></span>

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

### <span data-ttu-id="76a10-258">-PassThru</span><span class="sxs-lookup"><span data-stu-id="76a10-258">-PassThru</span></span>

<span data-ttu-id="76a10-259">Возвращает объект **System.Runtime** , представляющий добавленные типы.</span><span class="sxs-lookup"><span data-stu-id="76a10-259">Returns a **System.Runtime** object that represents the types that were added.</span></span> <span data-ttu-id="76a10-260">По умолчанию этот командлет не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="76a10-260">By default, this cmdlet doesn't generate any output.</span></span>

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

### <span data-ttu-id="76a10-261">-Path</span><span class="sxs-lookup"><span data-stu-id="76a10-261">-Path</span></span>

<span data-ttu-id="76a10-262">Задает путь к файлу исходного кода или DLL-файлам сборки, содержащей типы.</span><span class="sxs-lookup"><span data-stu-id="76a10-262">Specifies the path to source code files or assembly DLL files that contain the types.</span></span>

<span data-ttu-id="76a10-263">При отправке файлов исходного кода `Add-Type` компилирует код в файлы и создает сборку типов в памяти.</span><span class="sxs-lookup"><span data-stu-id="76a10-263">If you submit source code files, `Add-Type` compiles the code in the files and creates an in-memory assembly of the types.</span></span> <span data-ttu-id="76a10-264">Расширение имени файла, указанное в параметре **path** , определяет компилятор, который `Add-Type` использует.</span><span class="sxs-lookup"><span data-stu-id="76a10-264">The file name extension specified in the value of **Path** determines the compiler that `Add-Type` uses.</span></span>

<span data-ttu-id="76a10-265">При отправке файла сборки `Add-Type` принимает типы из сборки.</span><span class="sxs-lookup"><span data-stu-id="76a10-265">If you submit an assembly file, `Add-Type` takes the types from the assembly.</span></span> <span data-ttu-id="76a10-266">Чтобы указать сборку в памяти или глобальный кэш сборок, используйте параметр **AssemblyName** .</span><span class="sxs-lookup"><span data-stu-id="76a10-266">To specify an in-memory assembly or the global assembly cache, use the **AssemblyName** parameter.</span></span>

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

### <span data-ttu-id="76a10-267">-Референцедассемблиес</span><span class="sxs-lookup"><span data-stu-id="76a10-267">-ReferencedAssemblies</span></span>

<span data-ttu-id="76a10-268">Указывает сборки, от которых зависит тип.</span><span class="sxs-lookup"><span data-stu-id="76a10-268">Specifies the assemblies upon which the type depends.</span></span> <span data-ttu-id="76a10-269">По умолчанию `Add-Type` ссылки `System.dll` и `System.Management.Automation.dll` .</span><span class="sxs-lookup"><span data-stu-id="76a10-269">By default, `Add-Type` references `System.dll` and `System.Management.Automation.dll`.</span></span> <span data-ttu-id="76a10-270">Ссылки на сборки, указываемые этим параметром, создаются в дополнение к сборкам по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="76a10-270">The assemblies that you specify by using this parameter are referenced in addition to the default assemblies.</span></span>

<span data-ttu-id="76a10-271">В одной команде нельзя использовать параметры **CompilerParameters** и **референцедассемблиес** .</span><span class="sxs-lookup"><span data-stu-id="76a10-271">You can't use the **CompilerParameters** and **ReferencedAssemblies** parameters in the same command.</span></span>

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

### <span data-ttu-id="76a10-272">-Типедефинитион</span><span class="sxs-lookup"><span data-stu-id="76a10-272">-TypeDefinition</span></span>

<span data-ttu-id="76a10-273">Указывает исходный код, содержащий определения типов.</span><span class="sxs-lookup"><span data-stu-id="76a10-273">Specifies the source code that contains the type definitions.</span></span> <span data-ttu-id="76a10-274">Введите исходный код в строку или автономную строку либо введите переменную, которая содержит исходный код.</span><span class="sxs-lookup"><span data-stu-id="76a10-274">Enter the source code in a string or here-string, or enter a variable that contains the source code.</span></span> <span data-ttu-id="76a10-275">Дополнительные сведения о строках см. в разделе [about_Quoting_Rules](../Microsoft.PowerShell.Core/about/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="76a10-275">For more information about here-strings, see [about_Quoting_Rules](../Microsoft.PowerShell.Core/about/about_Quoting_Rules.md).</span></span>

<span data-ttu-id="76a10-276">Включите объявление пространства имен в определение типа.</span><span class="sxs-lookup"><span data-stu-id="76a10-276">Include a namespace declaration in your type definition.</span></span> <span data-ttu-id="76a10-277">Если опустить объявление пространства имен, имя типа может совпасть с именем или ярлыком другого типа, вызывая непреднамеренную перезапись.</span><span class="sxs-lookup"><span data-stu-id="76a10-277">If you omit the namespace declaration, your type might have the same name as another type or the shortcut for another type, causing an unintentional overwrite.</span></span> <span data-ttu-id="76a10-278">Например, если определить тип с именем **Exception** , скрипты, использующие **исключение** в качестве ярлыка для **System. Exception** , завершатся ошибкой.</span><span class="sxs-lookup"><span data-stu-id="76a10-278">For example, if you define a type called **Exception** , scripts that use **Exception** as the shortcut for **System.Exception** will fail.</span></span>

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

### <span data-ttu-id="76a10-279">-Усингнамеспаце</span><span class="sxs-lookup"><span data-stu-id="76a10-279">-UsingNamespace</span></span>

<span data-ttu-id="76a10-280">Задает другие пространства имен, которые требуются для класса.</span><span class="sxs-lookup"><span data-stu-id="76a10-280">Specifies other namespaces that are required for the class.</span></span> <span data-ttu-id="76a10-281">Это очень похоже на ключевое слово C# `Using` .</span><span class="sxs-lookup"><span data-stu-id="76a10-281">This is much like the C# keyword, `Using`.</span></span>

<span data-ttu-id="76a10-282">По умолчанию `Add-Type` ссылается на пространство имен **System** .</span><span class="sxs-lookup"><span data-stu-id="76a10-282">By default, `Add-Type` references the **System** namespace.</span></span> <span data-ttu-id="76a10-283">При использовании параметра **MemberDefinition** `Add-Type` также ссылается на пространство имен **System. Runtime. InteropServices** по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="76a10-283">When the **MemberDefinition** parameter is used, `Add-Type` also references the **System.Runtime.InteropServices** namespace by default.</span></span> <span data-ttu-id="76a10-284">Ссылки на пространства имен, добавляемые с помощью **UsingNamespace** , создаются в дополнение к пространствами имен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="76a10-284">The namespaces that you add by using the **UsingNamespace** parameter are referenced in addition to the default namespaces.</span></span>

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

### <span data-ttu-id="76a10-285">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="76a10-285">CommonParameters</span></span>

<span data-ttu-id="76a10-286">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="76a10-286">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="76a10-287">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="76a10-287">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="76a10-288">Входные данные</span><span class="sxs-lookup"><span data-stu-id="76a10-288">INPUTS</span></span>

### <span data-ttu-id="76a10-289">Нет</span><span class="sxs-lookup"><span data-stu-id="76a10-289">None</span></span>

<span data-ttu-id="76a10-290">Вы не можете отправить объекты по конвейеру в `Add-Type` .</span><span class="sxs-lookup"><span data-stu-id="76a10-290">You can't send objects down the pipeline to `Add-Type`.</span></span>

## <span data-ttu-id="76a10-291">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="76a10-291">OUTPUTS</span></span>

### <span data-ttu-id="76a10-292">None или System. Type</span><span class="sxs-lookup"><span data-stu-id="76a10-292">None or System.Type</span></span>

<span data-ttu-id="76a10-293">При использовании параметра **PassThru** `Add-Type` возвращает объект **System. Type** , представляющий новый тип.</span><span class="sxs-lookup"><span data-stu-id="76a10-293">When you use the **PassThru** parameter, `Add-Type` returns a **System.Type** object that represents the new type.</span></span> <span data-ttu-id="76a10-294">В противном случае этот командлет не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="76a10-294">Otherwise, this cmdlet doesn't generate any output.</span></span>

## <span data-ttu-id="76a10-295">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="76a10-295">NOTES</span></span>

<span data-ttu-id="76a10-296">Добавляемые типы существуют только в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="76a10-296">The types that you add exist only in the current session.</span></span> <span data-ttu-id="76a10-297">Чтобы использовать типы во всех сеансах, добавьте их в профиль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="76a10-297">To use the types in all sessions, add them to your PowerShell profile.</span></span> <span data-ttu-id="76a10-298">Дополнительные сведения о профиле см. в разделе [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="76a10-298">For more information about the profile, see [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

<span data-ttu-id="76a10-299">Имена типов и пространства имен должны быть уникальными в пределах сеанса.</span><span class="sxs-lookup"><span data-stu-id="76a10-299">Type names and namespaces must be unique within a session.</span></span> <span data-ttu-id="76a10-300">Невозможно выгрузить тип или изменить его.</span><span class="sxs-lookup"><span data-stu-id="76a10-300">You can't unload a type or change it.</span></span> <span data-ttu-id="76a10-301">Если необходимо изменить код для типа, необходимо изменить имя или запустить новый сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="76a10-301">If you need to change the code for a type, you must change the name or start a new PowerShell session.</span></span>
<span data-ttu-id="76a10-302">В противном случае произойдет сбой команды.</span><span class="sxs-lookup"><span data-stu-id="76a10-302">Otherwise, the command fails.</span></span>

<span data-ttu-id="76a10-303">Класс **CodeDomProvider** для некоторых языков, таких как IronPython и J#, не создает выходных данных.</span><span class="sxs-lookup"><span data-stu-id="76a10-303">The **CodeDomProvider** class for some languages, such as IronPython and J#, doesn't generate output.</span></span> <span data-ttu-id="76a10-304">В результате типы, написанные на этих языках, нельзя использовать с `Add-Type` .</span><span class="sxs-lookup"><span data-stu-id="76a10-304">As a result, types written in these languages can't be used with `Add-Type`.</span></span>

<span data-ttu-id="76a10-305">Этот командлет основан на классе Microsoft .NET Framework [CodeDomProvider](/dotnet/api/system.codedom.compiler.codedomprovider).</span><span class="sxs-lookup"><span data-stu-id="76a10-305">This cmdlet is based on the Microsoft .NET Framework [CodeDomProvider Class](/dotnet/api/system.codedom.compiler.codedomprovider).</span></span>

## <span data-ttu-id="76a10-306">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="76a10-306">RELATED LINKS</span></span>

[<span data-ttu-id="76a10-307">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="76a10-307">about_Profiles</span></span>](../Microsoft.PowerShell.Core/About/about_profiles.md)

[<span data-ttu-id="76a10-308">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="76a10-308">about_Quoting_Rules</span></span>](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="76a10-309">Add-Member</span><span class="sxs-lookup"><span data-stu-id="76a10-309">Add-Member</span></span>](Add-Member.md)

[<span data-ttu-id="76a10-310">New-Object</span><span class="sxs-lookup"><span data-stu-id="76a10-310">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="76a10-311">аутпутассемблитипе</span><span class="sxs-lookup"><span data-stu-id="76a10-311">OutputAssemblyType</span></span>](/dotnet/api/microsoft.powershell.commands.outputassemblytype)

[<span data-ttu-id="76a10-312">Вызов неуправляемого кода (P/Invoke)</span><span class="sxs-lookup"><span data-stu-id="76a10-312">Platform Invoke (P/Invoke)</span></span>](/dotnet/standard/native-interop/pinvoke)

[<span data-ttu-id="76a10-313">Where-Object</span><span class="sxs-lookup"><span data-stu-id="76a10-313">Where-Object</span></span>](../Microsoft.PowerShell.Core/Where-Object.md)
