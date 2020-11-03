---
description: Описывает создание и использование переменной ссылочного типа. Можно использовать переменные ссылочного типа, чтобы позволить функции изменять значение передаваемой ей переменной.
keywords: powershell,командлет
Locale: en-US
ms.date: 08/24/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_ref?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Ref
ms.openlocfilehash: fefc0f002db0b9591b2d23e148db381f7413871f
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231326"
---
# <a name="about-ref"></a><span data-ttu-id="1f6d7-105">О ссылке</span><span class="sxs-lookup"><span data-stu-id="1f6d7-105">About Ref</span></span>

## <a name="short-description"></a><span data-ttu-id="1f6d7-106">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="1f6d7-106">Short description</span></span>
<span data-ttu-id="1f6d7-107">Описывает создание и использование переменной ссылочного типа.</span><span class="sxs-lookup"><span data-stu-id="1f6d7-107">Describes how to create and use a reference type variable.</span></span> <span data-ttu-id="1f6d7-108">Можно использовать переменные ссылочного типа, чтобы позволить функции изменять значение передаваемой ей переменной.</span><span class="sxs-lookup"><span data-stu-id="1f6d7-108">You can use reference type variables to permit a function to change the value of a variable that is passed to it.</span></span>

## <a name="long-description"></a><span data-ttu-id="1f6d7-109">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="1f6d7-109">Long description</span></span>

<span data-ttu-id="1f6d7-110">Переменные можно передавать в функции *по ссылке* или *по значению* .</span><span class="sxs-lookup"><span data-stu-id="1f6d7-110">You can pass variables to functions *by reference* or *by value* .</span></span>

<span data-ttu-id="1f6d7-111">При передаче переменной *по значению* передается копия данных.</span><span class="sxs-lookup"><span data-stu-id="1f6d7-111">When you pass a variable *by value* , you are passing a copy of the data.</span></span>

<span data-ttu-id="1f6d7-112">В следующем примере функция изменяет значение переданной переменной.</span><span class="sxs-lookup"><span data-stu-id="1f6d7-112">In the following example, the function changes the value of the variable passed to it.</span></span> <span data-ttu-id="1f6d7-113">В PowerShell целочисленные типы являются типами значений, поэтому они передаются по значению.</span><span class="sxs-lookup"><span data-stu-id="1f6d7-113">In PowerShell, integers are value types so they are passed by value.</span></span>
<span data-ttu-id="1f6d7-114">Таким образом, значение `$var` не изменяется вне области действия функции.</span><span class="sxs-lookup"><span data-stu-id="1f6d7-114">Therefore, the value of `$var` is unchanged outside the scope of the function.</span></span>

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

<span data-ttu-id="1f6d7-115">В следующем примере переменная, содержащая, `Hashtable` передается в функцию.</span><span class="sxs-lookup"><span data-stu-id="1f6d7-115">In the following example, a variable containing a `Hashtable` is passed to a function.</span></span> <span data-ttu-id="1f6d7-116">`Hashtable` объект является типом объекта, поэтому по умолчанию он передается в функцию *по ссылке* .</span><span class="sxs-lookup"><span data-stu-id="1f6d7-116">`Hashtable` is an object type so by default it is passed to the function *by reference* .</span></span>

<span data-ttu-id="1f6d7-117">При передаче переменной *по ссылке* функция может изменить данные, и это изменение сохраняется после выполнения функции.</span><span class="sxs-lookup"><span data-stu-id="1f6d7-117">When passing a variable *by reference* , the function can change the data and that change persists after the function executes.</span></span>

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

<span data-ttu-id="1f6d7-118">Функция добавляет новую пару "ключ-значение", которая сохраняется вне области действия функции.</span><span class="sxs-lookup"><span data-stu-id="1f6d7-118">The function adds a new key-value pair that persists outside of the function's scope.</span></span>

### <a name="writing-functions-to-accept-reference-parameters"></a><span data-ttu-id="1f6d7-119">Написание функций для принятия ссылочных параметров</span><span class="sxs-lookup"><span data-stu-id="1f6d7-119">Writing functions to accept reference parameters</span></span>

<span data-ttu-id="1f6d7-120">Можно создать код для функций, чтобы использовать в качестве ссылки параметр, независимо от типа передаваемых данных.</span><span class="sxs-lookup"><span data-stu-id="1f6d7-120">You can code your functions to take a parameter as a reference, regardless of the type of data passed.</span></span> <span data-ttu-id="1f6d7-121">Для этого необходимо указать тип параметров в виде `System.Management.Automation.PSReference` или `[ref]` .</span><span class="sxs-lookup"><span data-stu-id="1f6d7-121">This requires that you specify the parameters type as `System.Management.Automation.PSReference`, or `[ref]`.</span></span>

<span data-ttu-id="1f6d7-122">При использовании ссылок необходимо использовать `Value` свойство `System.Management.Automation.PSReference` типа для доступа к данным.</span><span class="sxs-lookup"><span data-stu-id="1f6d7-122">When using references, you must use the `Value` property of the `System.Management.Automation.PSReference` type to access your data.</span></span>

```powershell
Function Test([ref]$data)
{
    $data.Value = 3
}
```

<span data-ttu-id="1f6d7-123">Чтобы передать переменную в параметр, для которого требуется ссылка, необходимо ввести в качестве ссылки приведение переменной.</span><span class="sxs-lookup"><span data-stu-id="1f6d7-123">To pass a variable to a parameter that expects a reference, you must type cast your variable as a reference.</span></span>

> [!NOTE]
> <span data-ttu-id="1f6d7-124">Требуются квадратные скобки и скобки.</span><span class="sxs-lookup"><span data-stu-id="1f6d7-124">The brackets and parenthesis are BOTH required.</span></span>

```powershell
$var = 10
Test -data ([ref]$var)
$var
```

```output
3
```

### <a name="passing-references-to-net-methods"></a><span data-ttu-id="1f6d7-125">Передача ссылок в методы .NET</span><span class="sxs-lookup"><span data-stu-id="1f6d7-125">Passing references to .NET methods</span></span>

<span data-ttu-id="1f6d7-126">Некоторые методы .NET могут потребовать передачи переменной в качестве ссылки.</span><span class="sxs-lookup"><span data-stu-id="1f6d7-126">Some .NET methods may require you to pass a variable as a reference.</span></span> <span data-ttu-id="1f6d7-127">Если в определении метода используются ключевые слова `in` , `out` или `ref` для параметра, он принимает ссылку.</span><span class="sxs-lookup"><span data-stu-id="1f6d7-127">When the method's definition uses the keywords `in`, `out`, or `ref` on a parameter, it expects a reference.</span></span>

```powershell
[int] | Get-Member -Static -Name TryParse
```

```output
Name     MemberType Definition
----     ---------- ----------
TryParse Method     static bool TryParse(string s, [ref] int result)
```

<span data-ttu-id="1f6d7-128">`TryParse`Метод пытается выполнить синтаксический анализ строки в виде целого числа.</span><span class="sxs-lookup"><span data-stu-id="1f6d7-128">The `TryParse` method attempts to parse a string as an integer.</span></span> <span data-ttu-id="1f6d7-129">Если метод завершается успешно, возвращается значение `$true` , а результат сохраняется в переменной, передаваемой **по ссылке** .</span><span class="sxs-lookup"><span data-stu-id="1f6d7-129">If the method succeeds, it returns `$true`, and the result is stored in the variable you passed **by reference** .</span></span>

```
PS> $number = 0
PS> [int]::TryParse("15", ([ref]$number))
True
PS> $number
15
```

### <a name="references-and-scopes"></a><span data-ttu-id="1f6d7-130">Ссылки и области</span><span class="sxs-lookup"><span data-stu-id="1f6d7-130">References and scopes</span></span>

<span data-ttu-id="1f6d7-131">Ссылки позволяют изменять значение переменной в родительской области внутри дочерней области.</span><span class="sxs-lookup"><span data-stu-id="1f6d7-131">References allow the value of a variable in the parent scope to be changed within a child scope.</span></span>

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

<span data-ttu-id="1f6d7-132">Была изменена только переменная ссылочного типа.</span><span class="sxs-lookup"><span data-stu-id="1f6d7-132">Only the reference type's variable was changed.</span></span>

## <a name="see-also"></a><span data-ttu-id="1f6d7-133">См. также статью</span><span class="sxs-lookup"><span data-stu-id="1f6d7-133">See also</span></span>

[<span data-ttu-id="1f6d7-134">about_Variables</span><span class="sxs-lookup"><span data-stu-id="1f6d7-134">about_Variables</span></span>](about_Variables.md)

[<span data-ttu-id="1f6d7-135">about_Environment_Variables</span><span class="sxs-lookup"><span data-stu-id="1f6d7-135">about_Environment_Variables</span></span>](about_Environment_Variables.md)

[<span data-ttu-id="1f6d7-136">about_Functions</span><span class="sxs-lookup"><span data-stu-id="1f6d7-136">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="1f6d7-137">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="1f6d7-137">about_Script_Blocks</span></span>](about_Script_Blocks.md)

[<span data-ttu-id="1f6d7-138">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="1f6d7-138">about_Scopes</span></span>](about_scopes.md)
