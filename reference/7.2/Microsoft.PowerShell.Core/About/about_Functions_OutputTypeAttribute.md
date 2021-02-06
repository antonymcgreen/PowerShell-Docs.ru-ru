---
description: Содержит описание атрибута, который сообщает о типе объекта, возвращаемого функцией.
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_functions_outputtypeattribute?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Functions_OutputTypeAttribute
ms.openlocfilehash: 82f1615c4a2fe2a24f104d8e5637103dea6e5a0a
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599815"
---
# <a name="about-functions-outputtypeattribute"></a><span data-ttu-id="2acf1-103">О функциях Аутпуттипеаттрибуте</span><span class="sxs-lookup"><span data-stu-id="2acf1-103">About Functions OutputTypeAttribute</span></span>

## <a name="short-description"></a><span data-ttu-id="2acf1-104">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="2acf1-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="2acf1-105">Содержит описание атрибута, который сообщает о типе объекта, возвращаемого функцией.</span><span class="sxs-lookup"><span data-stu-id="2acf1-105">Describes an attribute that reports the type of object that the function returns.</span></span>

## <a name="long-description"></a><span data-ttu-id="2acf1-106">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="2acf1-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="2acf1-107">Атрибут OutputType перечисляет типы .NET объектов, возвращаемых функциями.</span><span class="sxs-lookup"><span data-stu-id="2acf1-107">The OutputType attribute lists the .NET types of objects that the functions returns.</span></span> <span data-ttu-id="2acf1-108">Можно использовать его необязательный параметр Параметерсетнаме для вывода списка различных типов выходных данных для каждого набора параметров.</span><span class="sxs-lookup"><span data-stu-id="2acf1-108">You can use its optional ParameterSetName parameter to list different output types for each parameter set.</span></span>

<span data-ttu-id="2acf1-109">Атрибут OutputType поддерживается в простых и расширенных функциях.</span><span class="sxs-lookup"><span data-stu-id="2acf1-109">The OutputType attribute is supported on simple and advanced functions.</span></span> <span data-ttu-id="2acf1-110">Он не зависит от атрибута CmdletBinding.</span><span class="sxs-lookup"><span data-stu-id="2acf1-110">It is independent of the CmdletBinding attribute.</span></span>

<span data-ttu-id="2acf1-111">Атрибут OutputType предоставляет значение свойства OutputType объекта **System. Management. Automation. FunctionInfo** , `Get-Command` возвращаемого командлетом.</span><span class="sxs-lookup"><span data-stu-id="2acf1-111">The OutputType attribute provides the value of the OutputType property of the **System.Management.Automation.FunctionInfo** object that the `Get-Command` cmdlet returns.</span></span>

<span data-ttu-id="2acf1-112">Значение атрибута OutputType предназначено только для документации.</span><span class="sxs-lookup"><span data-stu-id="2acf1-112">The OutputType attribute value is only a documentation note.</span></span> <span data-ttu-id="2acf1-113">Он не является производным от кода функции или не сравнивается с фактическим выходом функции.</span><span class="sxs-lookup"><span data-stu-id="2acf1-113">It is not derived from the function code or compared to the actual function output.</span></span> <span data-ttu-id="2acf1-114">Таким образом, значение может быть неточным.</span><span class="sxs-lookup"><span data-stu-id="2acf1-114">As such, the value might be inaccurate.</span></span>

## <a name="syntax"></a><span data-ttu-id="2acf1-115">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2acf1-115">SYNTAX</span></span>

<span data-ttu-id="2acf1-116">Атрибут OutputType функций имеет следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="2acf1-116">The OutputType attribute of functions has the following syntax:</span></span>

```
[OutputType([<TypeLiteral>], ParameterSetName="<Name>")]
[OutputType("<TypeNameString>", ParameterSetName="<Name>")]
```

<span data-ttu-id="2acf1-117">Параметр **параметерсетнаме** является необязательным.</span><span class="sxs-lookup"><span data-stu-id="2acf1-117">The **ParameterSetName** parameter is optional.</span></span>

<span data-ttu-id="2acf1-118">В атрибут OutputType можно перечислить несколько типов.</span><span class="sxs-lookup"><span data-stu-id="2acf1-118">You can list multiple types in the OutputType attribute.</span></span>

```
[OutputType([<Type1>],[<Type2>],[<Type3>])]
```

<span data-ttu-id="2acf1-119">Можно использовать параметр **параметерсетнаме** , чтобы указать, что различные наборы параметров возвращают разные типы.</span><span class="sxs-lookup"><span data-stu-id="2acf1-119">You can use the **ParameterSetName** parameter to indicate that different parameter sets return different types.</span></span>

```
[OutputType([<Type1>], ParameterSetName=("<Set1>","<Set2>"))]
[OutputType([<Type2>], ParameterSetName="<Set3>")]
```

<span data-ttu-id="2acf1-120">Поместите операторы атрибута OutputType в список Attributes, предшествующий `Param` оператору.</span><span class="sxs-lookup"><span data-stu-id="2acf1-120">Place the OutputType attribute statements in the attributes list that precedes the `Param` statement.</span></span>

<span data-ttu-id="2acf1-121">В следующем примере показано размещение атрибута OutputType в простой функции.</span><span class="sxs-lookup"><span data-stu-id="2acf1-121">The following example shows the placement of the OutputType attribute in a simple function.</span></span>

```powershell
function SimpleFunction2
{
  [OutputType([<Type>])]
  Param ($Parameter1)

  <function body>
}
```

<span data-ttu-id="2acf1-122">В следующем примере показано размещение атрибута OutputType в расширенных функциях.</span><span class="sxs-lookup"><span data-stu-id="2acf1-122">The following example shows the placement of the OutputType attribute in advanced functions.</span></span>

```powershell
function AdvancedFunction1
{
  [OutputType([<Type>])]
  Param (
    [parameter(Mandatory=$true)]
    [String[]]
    $Parameter1
  )

  <function body>
}

function AdvancedFunction2
{
  [CmdletBinding(SupportsShouldProcess=<Boolean>)]
  [OutputType([<Type>])]
  Param (
    [parameter(Mandatory=$true)]
    [String[]]
    $Parameter1
  )

  <function body>
}
```

## <a name="examples"></a><span data-ttu-id="2acf1-123">Примеры</span><span class="sxs-lookup"><span data-stu-id="2acf1-123">EXAMPLES</span></span>

### <a name="example-1-create-a-function-that-has-the-outputtype-of-string"></a><span data-ttu-id="2acf1-124">Пример 1. Создание функции, имеющей значение OutputType строки</span><span class="sxs-lookup"><span data-stu-id="2acf1-124">Example 1: Create a function that has the OutputType of String</span></span>

```powershell
function Send-Greeting
{
  [OutputType([String])]
  Param ($Name)

  "Hello, $Name"
}
```

<span data-ttu-id="2acf1-125">Чтобы просмотреть результирующее свойство типа выходных данных, используйте `Get-Command` командлет.</span><span class="sxs-lookup"><span data-stu-id="2acf1-125">To see the resulting output type property, use the `Get-Command` cmdlet.</span></span>

```powershell
(Get-Command Send-Greeting).OutputType
```

```Output
Name                                               Type
----                                               ----
System.String                                      System.String
```

### <a name="example-2-use-the-output-attribute-to-indicate-dynamic-output-types"></a><span data-ttu-id="2acf1-126">Пример 2. Использование выходного атрибута для указания динамических типов выходных данных</span><span class="sxs-lookup"><span data-stu-id="2acf1-126">Example 2: Use the Output attribute to indicate dynamic output types</span></span>

<span data-ttu-id="2acf1-127">Следующая Расширенная функция использует атрибут OutputType, чтобы указать, что функция возвращает различные типы в зависимости от набора параметров, используемого в команде функции.</span><span class="sxs-lookup"><span data-stu-id="2acf1-127">The following advanced function uses the OutputType attribute to indicate that the function returns different types depending on the parameter set used in the function command.</span></span>

```powershell
function Get-User
{
  [CmdletBinding(DefaultParameterSetName="ID")]

  [OutputType("System.Int32", ParameterSetName="ID")]
  [OutputType([String], ParameterSetName="Name")]

  Param (
    [parameter(Mandatory=$true, ParameterSetName="ID")]
    [Int[]]
    $UserID,

    [parameter(Mandatory=$true, ParameterSetName="Name")]
    [String[]]
    $UserName
  )

  <function body>
}
```

### <a name="example-3-shows-when-an-actual-output-differs-from-the-outputtype"></a><span data-ttu-id="2acf1-128">Пример 3. показывает, что фактические выходные данные отличаются от значения OutputType</span><span class="sxs-lookup"><span data-stu-id="2acf1-128">Example 3: Shows when an actual output differs from the OutputType</span></span>

<span data-ttu-id="2acf1-129">В следующем примере показано, что значение свойства Тип выходных данных отображает значение атрибута OutputType, даже если оно неточно.</span><span class="sxs-lookup"><span data-stu-id="2acf1-129">The following example demonstrates that the output type property value displays the value of the OutputType attribute, even when it is inaccurate.</span></span>

<span data-ttu-id="2acf1-130">`Get-Time`Функция возвращает строку, содержащую краткую форму времени в любом объекте DateTime.</span><span class="sxs-lookup"><span data-stu-id="2acf1-130">The `Get-Time` function returns a string that contains the short form of the time in any DateTime object.</span></span> <span data-ttu-id="2acf1-131">Однако атрибут OutputType сообщает, что он возвращает объект **System. DateTime** .</span><span class="sxs-lookup"><span data-stu-id="2acf1-131">However, the OutputType attribute reports that it returns a **System.DateTime** object.</span></span>

```powershell
function Get-Time
{
  [OutputType([DateTime])]
  Param (
    [parameter(Mandatory=$true)]
    [Datetime]$DateTime
  )

  $DateTime.ToShortTimeString()
}
```

<span data-ttu-id="2acf1-132">`GetType()`Метод подтверждает, что функция возвращает строку.</span><span class="sxs-lookup"><span data-stu-id="2acf1-132">The `GetType()` method confirms that the function returns a string.</span></span>

```powershell
(Get-Time -DateTime (Get-Date)).GetType().FullName
```

```Output
System.String
```

<span data-ttu-id="2acf1-133">Однако свойство OutputType, получающее его значение из атрибута OutputType, сообщает о том, что функция возвращает объект **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="2acf1-133">However, the OutputType property, which gets its value from the OutputType attribute, reports that the function returns a **DateTime** object.</span></span>

```powershell
(Get-Command Get-Time).OutputType
```

```Output
Name                                      Type
----                                      ----
System.DateTime                           System.DateTime
```

### <a name="example-4-a-function--that-shouldnt-have-output"></a><span data-ttu-id="2acf1-134">Пример 4. функция, которая не должна иметь выходных данных</span><span class="sxs-lookup"><span data-stu-id="2acf1-134">Example 4: A function  that shouldn't have output</span></span>

<span data-ttu-id="2acf1-135">В следующем примере показана пользовательская функция, которая должна выполнять действия и не возвращать никаких результатов.</span><span class="sxs-lookup"><span data-stu-id="2acf1-135">The following example shows a custom function that should perform and action but not return anything.</span></span>

```powershell
function Invoke-Notepad
{
  [OutputType([System.Void])]
  Param ()
  & notepad.exe | Out-Null
}
```

## <a name="notes"></a><span data-ttu-id="2acf1-136">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="2acf1-136">NOTES</span></span>

<span data-ttu-id="2acf1-137">Значением свойства OutputType объекта **FunctionInfo** является массив объектов **System. Management. Automation. пстипенаме** , каждый из которых имеет свойства Name и Type.</span><span class="sxs-lookup"><span data-stu-id="2acf1-137">The value of the OutputType property of a **FunctionInfo** object is an array of **System.Management.Automation.PSTypeName** objects, each of which have Name and Type properties.</span></span>

<span data-ttu-id="2acf1-138">Чтобы получить только имя каждого выходного типа, используйте команду в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="2acf1-138">To get only the name of each output type, use a command with the following format.</span></span>

```powershell
(Get-Command Get-Time).OutputType | ForEach {$_.Name}
```

<span data-ttu-id="2acf1-139">Значение свойства OutputType может быть равно null.</span><span class="sxs-lookup"><span data-stu-id="2acf1-139">The value of the OutputType property can be null.</span></span> <span data-ttu-id="2acf1-140">Используйте значение null, если выходные данные не являются типом .NET, например **WMI** -объектом или форматированным представлением объекта.</span><span class="sxs-lookup"><span data-stu-id="2acf1-140">Use a null value when the output is a not a .NET type, such as a **WMI** object or a formatted view of an object.</span></span>

## <a name="see-also"></a><span data-ttu-id="2acf1-141">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="2acf1-141">SEE ALSO</span></span>

[<span data-ttu-id="2acf1-142">about_Functions</span><span class="sxs-lookup"><span data-stu-id="2acf1-142">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="2acf1-143">about_Functions_Advanced</span><span class="sxs-lookup"><span data-stu-id="2acf1-143">about_Functions_Advanced</span></span>](about_Functions_Advanced.md)

[<span data-ttu-id="2acf1-144">about_Functions_Advanced_Methods</span><span class="sxs-lookup"><span data-stu-id="2acf1-144">about_Functions_Advanced_Methods</span></span>](about_Functions_Advanced_Methods.md)

[<span data-ttu-id="2acf1-145">about_Functions_Advanced_Parameters</span><span class="sxs-lookup"><span data-stu-id="2acf1-145">about_Functions_Advanced_Parameters</span></span>](about_Functions_Advanced_Parameters.md)

[<span data-ttu-id="2acf1-146">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="2acf1-146">about_Functions_CmdletBindingAttribute</span></span>](about_Functions_CmdletBindingAttribute.md)

