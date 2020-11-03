---
description: Содержит описание атрибута, который сообщает о типе объекта, возвращаемого функцией.
keywords: powershell,командлет
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_functions_outputtypeattribute?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Functions_OutputTypeAttribute
ms.openlocfilehash: 94e6ab9926f8d31e6b7602792f836fa5eadd3b50
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231462"
---
# <a name="about-functions-outputtypeattribute"></a><span data-ttu-id="5ddc0-104">О функциях Аутпуттипеаттрибуте</span><span class="sxs-lookup"><span data-stu-id="5ddc0-104">About Functions OutputTypeAttribute</span></span>

## <a name="short-description"></a><span data-ttu-id="5ddc0-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="5ddc0-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="5ddc0-106">Содержит описание атрибута, который сообщает о типе объекта, возвращаемого функцией.</span><span class="sxs-lookup"><span data-stu-id="5ddc0-106">Describes an attribute that reports the type of object that the function returns.</span></span>

## <a name="long-description"></a><span data-ttu-id="5ddc0-107">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="5ddc0-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="5ddc0-108">Атрибут OutputType перечисляет типы .NET объектов, возвращаемых функциями.</span><span class="sxs-lookup"><span data-stu-id="5ddc0-108">The OutputType attribute lists the .NET types of objects that the functions returns.</span></span> <span data-ttu-id="5ddc0-109">Можно использовать его необязательный параметр Параметерсетнаме для вывода списка различных типов выходных данных для каждого набора параметров.</span><span class="sxs-lookup"><span data-stu-id="5ddc0-109">You can use its optional ParameterSetName parameter to list different output types for each parameter set.</span></span>

<span data-ttu-id="5ddc0-110">Атрибут OutputType поддерживается в простых и расширенных функциях.</span><span class="sxs-lookup"><span data-stu-id="5ddc0-110">The OutputType attribute is supported on simple and advanced functions.</span></span> <span data-ttu-id="5ddc0-111">Он не зависит от атрибута CmdletBinding.</span><span class="sxs-lookup"><span data-stu-id="5ddc0-111">It is independent of the CmdletBinding attribute.</span></span>

<span data-ttu-id="5ddc0-112">Атрибут OutputType предоставляет значение свойства OutputType объекта **System. Management. Automation. FunctionInfo** , `Get-Command` возвращаемого командлетом.</span><span class="sxs-lookup"><span data-stu-id="5ddc0-112">The OutputType attribute provides the value of the OutputType property of the **System.Management.Automation.FunctionInfo** object that the `Get-Command` cmdlet returns.</span></span>

<span data-ttu-id="5ddc0-113">Значение атрибута OutputType предназначено только для документации.</span><span class="sxs-lookup"><span data-stu-id="5ddc0-113">The OutputType attribute value is only a documentation note.</span></span> <span data-ttu-id="5ddc0-114">Он не является производным от кода функции или не сравнивается с фактическим выходом функции.</span><span class="sxs-lookup"><span data-stu-id="5ddc0-114">It is not derived from the function code or compared to the actual function output.</span></span> <span data-ttu-id="5ddc0-115">Таким образом, значение может быть неточным.</span><span class="sxs-lookup"><span data-stu-id="5ddc0-115">As such, the value might be inaccurate.</span></span>

## <a name="syntax"></a><span data-ttu-id="5ddc0-116">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5ddc0-116">SYNTAX</span></span>

<span data-ttu-id="5ddc0-117">Атрибут OutputType функций имеет следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="5ddc0-117">The OutputType attribute of functions has the following syntax:</span></span>

```
[OutputType([<TypeLiteral>], ParameterSetName="<Name>")]
[OutputType("<TypeNameString>", ParameterSetName="<Name>")]
```

<span data-ttu-id="5ddc0-118">Параметр **параметерсетнаме** является необязательным.</span><span class="sxs-lookup"><span data-stu-id="5ddc0-118">The **ParameterSetName** parameter is optional.</span></span>

<span data-ttu-id="5ddc0-119">В атрибут OutputType можно перечислить несколько типов.</span><span class="sxs-lookup"><span data-stu-id="5ddc0-119">You can list multiple types in the OutputType attribute.</span></span>

```
[OutputType([<Type1>],[<Type2>],[<Type3>])]
```

<span data-ttu-id="5ddc0-120">Можно использовать параметр **параметерсетнаме** , чтобы указать, что различные наборы параметров возвращают разные типы.</span><span class="sxs-lookup"><span data-stu-id="5ddc0-120">You can use the **ParameterSetName** parameter to indicate that different parameter sets return different types.</span></span>

```
[OutputType([<Type1>], ParameterSetName=("<Set1>","<Set2>"))]
[OutputType([<Type2>], ParameterSetName="<Set3>")]
```

<span data-ttu-id="5ddc0-121">Поместите операторы атрибута OutputType в список Attributes, предшествующий `Param` оператору.</span><span class="sxs-lookup"><span data-stu-id="5ddc0-121">Place the OutputType attribute statements in the attributes list that precedes the `Param` statement.</span></span>

<span data-ttu-id="5ddc0-122">В следующем примере показано размещение атрибута OutputType в простой функции.</span><span class="sxs-lookup"><span data-stu-id="5ddc0-122">The following example shows the placement of the OutputType attribute in a simple function.</span></span>

```powershell
function SimpleFunction2
{
  [OutputType([<Type>])]
  Param ($Parameter1)

  <function body>
}
```

<span data-ttu-id="5ddc0-123">В следующем примере показано размещение атрибута OutputType в расширенных функциях.</span><span class="sxs-lookup"><span data-stu-id="5ddc0-123">The following example shows the placement of the OutputType attribute in advanced functions.</span></span>

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

## <a name="examples"></a><span data-ttu-id="5ddc0-124">Примеры</span><span class="sxs-lookup"><span data-stu-id="5ddc0-124">EXAMPLES</span></span>

### <a name="example-1-create-a-function-that-has-the-outputtype-of-string"></a><span data-ttu-id="5ddc0-125">Пример 1. Создание функции, имеющей значение OutputType строки</span><span class="sxs-lookup"><span data-stu-id="5ddc0-125">Example 1: Create a function that has the OutputType of String</span></span>

```powershell
function Send-Greeting
{
  [OutputType([String])]
  Param ($Name)

  "Hello, $Name"
}
```

<span data-ttu-id="5ddc0-126">Чтобы просмотреть результирующее свойство типа выходных данных, используйте `Get-Command` командлет.</span><span class="sxs-lookup"><span data-stu-id="5ddc0-126">To see the resulting output type property, use the `Get-Command` cmdlet.</span></span>

```powershell
(Get-Command Send-Greeting).OutputType
```

```Output
Name                                               Type
----                                               ----
System.String                                      System.String
```

### <a name="example-2-use-the-output-attribute-to-indicate-dynamic-output-types"></a><span data-ttu-id="5ddc0-127">Пример 2. Использование выходного атрибута для указания динамических типов выходных данных</span><span class="sxs-lookup"><span data-stu-id="5ddc0-127">Example 2: Use the Output attribute to indicate dynamic output types</span></span>

<span data-ttu-id="5ddc0-128">Следующая Расширенная функция использует атрибут OutputType, чтобы указать, что функция возвращает различные типы в зависимости от набора параметров, используемого в команде функции.</span><span class="sxs-lookup"><span data-stu-id="5ddc0-128">The following advanced function uses the OutputType attribute to indicate that the function returns different types depending on the parameter set used in the function command.</span></span>

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

### <a name="example-3-shows-when-an-actual-output-differs-from-the-outputtype"></a><span data-ttu-id="5ddc0-129">Пример 3. показывает, что фактические выходные данные отличаются от значения OutputType</span><span class="sxs-lookup"><span data-stu-id="5ddc0-129">Example 3: Shows when an actual output differs from the OutputType</span></span>

<span data-ttu-id="5ddc0-130">В следующем примере показано, что значение свойства Тип выходных данных отображает значение атрибута OutputType, даже если оно неточно.</span><span class="sxs-lookup"><span data-stu-id="5ddc0-130">The following example demonstrates that the output type property value displays the value of the OutputType attribute, even when it is inaccurate.</span></span>

<span data-ttu-id="5ddc0-131">`Get-Time`Функция возвращает строку, содержащую краткую форму времени в любом объекте DateTime.</span><span class="sxs-lookup"><span data-stu-id="5ddc0-131">The `Get-Time` function returns a string that contains the short form of the time in any DateTime object.</span></span> <span data-ttu-id="5ddc0-132">Однако атрибут OutputType сообщает, что он возвращает объект **System. DateTime** .</span><span class="sxs-lookup"><span data-stu-id="5ddc0-132">However, the OutputType attribute reports that it returns a **System.DateTime** object.</span></span>

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

<span data-ttu-id="5ddc0-133">`GetType()`Метод подтверждает, что функция возвращает строку.</span><span class="sxs-lookup"><span data-stu-id="5ddc0-133">The `GetType()` method confirms that the function returns a string.</span></span>

```powershell
(Get-Time -DateTime (Get-Date)).GetType().FullName
```

```Output
System.String
```

<span data-ttu-id="5ddc0-134">Однако свойство OutputType, получающее его значение из атрибута OutputType, сообщает о том, что функция возвращает объект **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="5ddc0-134">However, the OutputType property, which gets its value from the OutputType attribute, reports that the function returns a **DateTime** object.</span></span>

```powershell
(Get-Command Get-Time).OutputType
```

```Output
Name                                      Type
----                                      ----
System.DateTime                           System.DateTime
```

### <a name="example-4-a-function--that-shouldnt-have-output"></a><span data-ttu-id="5ddc0-135">Пример 4. функция, которая не должна иметь выходных данных</span><span class="sxs-lookup"><span data-stu-id="5ddc0-135">Example 4: A function  that shouldn't have output</span></span>

<span data-ttu-id="5ddc0-136">В следующем примере показана пользовательская функция, которая должна выполнять действия и не возвращать никаких результатов.</span><span class="sxs-lookup"><span data-stu-id="5ddc0-136">The following example shows a custom function that should perform and action but not return anything.</span></span>

```powershell
function Invoke-Notepad
{
  [OutputType([System.Void])]
  Param ()
  & notepad.exe | Out-Null
}
```

## <a name="notes"></a><span data-ttu-id="5ddc0-137">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="5ddc0-137">NOTES</span></span>

<span data-ttu-id="5ddc0-138">Значением свойства OutputType объекта **FunctionInfo** является массив объектов **System. Management. Automation. пстипенаме** , каждый из которых имеет свойства Name и Type.</span><span class="sxs-lookup"><span data-stu-id="5ddc0-138">The value of the OutputType property of a **FunctionInfo** object is an array of **System.Management.Automation.PSTypeName** objects, each of which have Name and Type properties.</span></span>

<span data-ttu-id="5ddc0-139">Чтобы получить только имя каждого выходного типа, используйте команду в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="5ddc0-139">To get only the name of each output type, use a command with the following format.</span></span>

```powershell
(Get-Command Get-Time).OutputType | ForEach {$_.Name}
```

<span data-ttu-id="5ddc0-140">Значение свойства OutputType может быть равно null.</span><span class="sxs-lookup"><span data-stu-id="5ddc0-140">The value of the OutputType property can be null.</span></span> <span data-ttu-id="5ddc0-141">Используйте значение null, если выходные данные не являются типом .NET, например **WMI** -объектом или форматированным представлением объекта.</span><span class="sxs-lookup"><span data-stu-id="5ddc0-141">Use a null value when the output is a not a .NET type, such as a **WMI** object or a formatted view of an object.</span></span>

## <a name="see-also"></a><span data-ttu-id="5ddc0-142">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="5ddc0-142">SEE ALSO</span></span>

[<span data-ttu-id="5ddc0-143">about_Functions</span><span class="sxs-lookup"><span data-stu-id="5ddc0-143">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="5ddc0-144">about_Functions_Advanced</span><span class="sxs-lookup"><span data-stu-id="5ddc0-144">about_Functions_Advanced</span></span>](about_Functions_Advanced.md)

[<span data-ttu-id="5ddc0-145">about_Functions_Advanced_Methods</span><span class="sxs-lookup"><span data-stu-id="5ddc0-145">about_Functions_Advanced_Methods</span></span>](about_Functions_Advanced_Methods.md)

[<span data-ttu-id="5ddc0-146">about_Functions_Advanced_Parameters</span><span class="sxs-lookup"><span data-stu-id="5ddc0-146">about_Functions_Advanced_Parameters</span></span>](about_Functions_Advanced_Parameters.md)

[<span data-ttu-id="5ddc0-147">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="5ddc0-147">about_Functions_CmdletBindingAttribute</span></span>](about_Functions_CmdletBindingAttribute.md)
