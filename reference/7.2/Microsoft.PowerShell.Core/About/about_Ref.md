---
description: Описывает создание и использование переменной ссылочного типа. Можно использовать переменные ссылочного типа, чтобы позволить функции изменять значение передаваемой ей переменной.
Locale: en-US
ms.date: 08/24/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_ref?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Ref
ms.openlocfilehash: 5b966816c8ac1ef91e03c78378f57fa20b5697de
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600182"
---
# <a name="about-ref"></a><span data-ttu-id="a3c3e-104">О ссылке</span><span class="sxs-lookup"><span data-stu-id="a3c3e-104">About Ref</span></span>

## <a name="short-description"></a><span data-ttu-id="a3c3e-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="a3c3e-105">Short description</span></span>
<span data-ttu-id="a3c3e-106">Описывает создание и использование переменной ссылочного типа.</span><span class="sxs-lookup"><span data-stu-id="a3c3e-106">Describes how to create and use a reference type variable.</span></span> <span data-ttu-id="a3c3e-107">Можно использовать переменные ссылочного типа, чтобы позволить функции изменять значение передаваемой ей переменной.</span><span class="sxs-lookup"><span data-stu-id="a3c3e-107">You can use reference type variables to permit a function to change the value of a variable that is passed to it.</span></span>

## <a name="long-description"></a><span data-ttu-id="a3c3e-108">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="a3c3e-108">Long description</span></span>

<span data-ttu-id="a3c3e-109">Переменные можно передавать в функции *по ссылке* или *по значению*.</span><span class="sxs-lookup"><span data-stu-id="a3c3e-109">You can pass variables to functions *by reference* or *by value*.</span></span>

<span data-ttu-id="a3c3e-110">При передаче переменной *по значению* передается копия данных.</span><span class="sxs-lookup"><span data-stu-id="a3c3e-110">When you pass a variable *by value*, you are passing a copy of the data.</span></span>

<span data-ttu-id="a3c3e-111">В следующем примере функция изменяет значение переданной переменной.</span><span class="sxs-lookup"><span data-stu-id="a3c3e-111">In the following example, the function changes the value of the variable passed to it.</span></span> <span data-ttu-id="a3c3e-112">В PowerShell целочисленные типы являются типами значений, поэтому они передаются по значению.</span><span class="sxs-lookup"><span data-stu-id="a3c3e-112">In PowerShell, integers are value types so they are passed by value.</span></span>
<span data-ttu-id="a3c3e-113">Таким образом, значение `$var` не изменяется вне области действия функции.</span><span class="sxs-lookup"><span data-stu-id="a3c3e-113">Therefore, the value of `$var` is unchanged outside the scope of the function.</span></span>

```powershell
Function Test($data)
{
    $data = 3
}

$var = 10
Test -data $var
$var
```

```output
10
```

<span data-ttu-id="a3c3e-114">В следующем примере переменная, содержащая, `Hashtable` передается в функцию.</span><span class="sxs-lookup"><span data-stu-id="a3c3e-114">In the following example, a variable containing a `Hashtable` is passed to a function.</span></span> <span data-ttu-id="a3c3e-115">`Hashtable` объект является типом объекта, поэтому по умолчанию он передается в функцию *по ссылке*.</span><span class="sxs-lookup"><span data-stu-id="a3c3e-115">`Hashtable` is an object type so by default it is passed to the function *by reference*.</span></span>

<span data-ttu-id="a3c3e-116">При передаче переменной *по ссылке* функция может изменить данные, и это изменение сохраняется после выполнения функции.</span><span class="sxs-lookup"><span data-stu-id="a3c3e-116">When passing a variable *by reference*, the function can change the data and that change persists after the function executes.</span></span>

```powershell
Function Test($data)
{
    $data.Test = "New Text"
}

$var = @{}
Test -data $var
$var
```

```output
Name                           Value
----                           -----
Test                           New Text
```

<span data-ttu-id="a3c3e-117">Функция добавляет новую пару "ключ-значение", которая сохраняется вне области действия функции.</span><span class="sxs-lookup"><span data-stu-id="a3c3e-117">The function adds a new key-value pair that persists outside of the function's scope.</span></span>

### <a name="writing-functions-to-accept-reference-parameters"></a><span data-ttu-id="a3c3e-118">Написание функций для принятия ссылочных параметров</span><span class="sxs-lookup"><span data-stu-id="a3c3e-118">Writing functions to accept reference parameters</span></span>

<span data-ttu-id="a3c3e-119">Можно создать код для функций, чтобы использовать в качестве ссылки параметр, независимо от типа передаваемых данных.</span><span class="sxs-lookup"><span data-stu-id="a3c3e-119">You can code your functions to take a parameter as a reference, regardless of the type of data passed.</span></span> <span data-ttu-id="a3c3e-120">Для этого необходимо указать тип параметров в виде `System.Management.Automation.PSReference` или `[ref]` .</span><span class="sxs-lookup"><span data-stu-id="a3c3e-120">This requires that you specify the parameters type as `System.Management.Automation.PSReference`, or `[ref]`.</span></span>

<span data-ttu-id="a3c3e-121">При использовании ссылок необходимо использовать `Value` свойство `System.Management.Automation.PSReference` типа для доступа к данным.</span><span class="sxs-lookup"><span data-stu-id="a3c3e-121">When using references, you must use the `Value` property of the `System.Management.Automation.PSReference` type to access your data.</span></span>

```powershell
Function Test([ref]$data)
{
    $data.Value = 3
}
```

<span data-ttu-id="a3c3e-122">Чтобы передать переменную в параметр, для которого требуется ссылка, необходимо ввести в качестве ссылки приведение переменной.</span><span class="sxs-lookup"><span data-stu-id="a3c3e-122">To pass a variable to a parameter that expects a reference, you must type cast your variable as a reference.</span></span>

> [!NOTE]
> <span data-ttu-id="a3c3e-123">Требуются квадратные скобки и скобки.</span><span class="sxs-lookup"><span data-stu-id="a3c3e-123">The brackets and parenthesis are BOTH required.</span></span>

```powershell
$var = 10
Test -data ([ref]$var)
$var
```

```output
3
```

### <a name="passing-references-to-net-methods"></a><span data-ttu-id="a3c3e-124">Передача ссылок в методы .NET</span><span class="sxs-lookup"><span data-stu-id="a3c3e-124">Passing references to .NET methods</span></span>

<span data-ttu-id="a3c3e-125">Некоторые методы .NET могут потребовать передачи переменной в качестве ссылки.</span><span class="sxs-lookup"><span data-stu-id="a3c3e-125">Some .NET methods may require you to pass a variable as a reference.</span></span> <span data-ttu-id="a3c3e-126">Если в определении метода используются ключевые слова `in` , `out` или `ref` для параметра, он принимает ссылку.</span><span class="sxs-lookup"><span data-stu-id="a3c3e-126">When the method's definition uses the keywords `in`, `out`, or `ref` on a parameter, it expects a reference.</span></span>

```powershell
[int] | Get-Member -Static -Name TryParse
```

```output
Name     MemberType Definition
----     ---------- ----------
TryParse Method     static bool TryParse(string s, [ref] int result)
```

<span data-ttu-id="a3c3e-127">`TryParse`Метод пытается выполнить синтаксический анализ строки в виде целого числа.</span><span class="sxs-lookup"><span data-stu-id="a3c3e-127">The `TryParse` method attempts to parse a string as an integer.</span></span> <span data-ttu-id="a3c3e-128">Если метод завершается успешно, возвращается значение `$true` , а результат сохраняется в переменной, передаваемой **по ссылке**.</span><span class="sxs-lookup"><span data-stu-id="a3c3e-128">If the method succeeds, it returns `$true`, and the result is stored in the variable you passed **by reference**.</span></span>

```
PS> $number = 0
PS> [int]::TryParse("15", ([ref]$number))
True
PS> $number
15
```

### <a name="references-and-scopes"></a><span data-ttu-id="a3c3e-129">Ссылки и области</span><span class="sxs-lookup"><span data-stu-id="a3c3e-129">References and scopes</span></span>

<span data-ttu-id="a3c3e-130">Ссылки позволяют изменять значение переменной в родительской области внутри дочерней области.</span><span class="sxs-lookup"><span data-stu-id="a3c3e-130">References allow the value of a variable in the parent scope to be changed within a child scope.</span></span>

```powershell
# Create a value type variable.
$i = 0
# Create a reference type variable.
$iRef = [ref]0
# Invoke a scriptblock to attempt to change both values.
&{$i++;$iRef.Value++}
# Output the results.
"`$i = $i;`$iRef = $($iRef.Value)"
```

```output
$i = 0;$iRef = 1
```

<span data-ttu-id="a3c3e-131">Была изменена только переменная ссылочного типа.</span><span class="sxs-lookup"><span data-stu-id="a3c3e-131">Only the reference type's variable was changed.</span></span>

## <a name="see-also"></a><span data-ttu-id="a3c3e-132">См. также</span><span class="sxs-lookup"><span data-stu-id="a3c3e-132">See also</span></span>

[<span data-ttu-id="a3c3e-133">about_Variables</span><span class="sxs-lookup"><span data-stu-id="a3c3e-133">about_Variables</span></span>](about_Variables.md)

[<span data-ttu-id="a3c3e-134">about_Environment_Variables</span><span class="sxs-lookup"><span data-stu-id="a3c3e-134">about_Environment_Variables</span></span>](about_Environment_Variables.md)

[<span data-ttu-id="a3c3e-135">about_Functions</span><span class="sxs-lookup"><span data-stu-id="a3c3e-135">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="a3c3e-136">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="a3c3e-136">about_Script_Blocks</span></span>](about_Script_Blocks.md)

[<span data-ttu-id="a3c3e-137">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="a3c3e-137">about_Scopes</span></span>](about_scopes.md)

