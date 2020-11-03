---
description: Описывает выход из текущей области действия, которая может быть функцией, скриптом или блоком скриптов.
keywords: powershell,командлет
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_return?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Return
ms.openlocfilehash: c0c5b60163870e9352f0c3aa750d5603f29a81b1
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232621"
---
# <a name="about-return"></a><span data-ttu-id="c0e95-104">О возврате</span><span class="sxs-lookup"><span data-stu-id="c0e95-104">About Return</span></span>

## <a name="short-description"></a><span data-ttu-id="c0e95-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="c0e95-105">Short description</span></span>

<span data-ttu-id="c0e95-106">Описывает выход из текущей области действия, которая может быть функцией, скриптом или блоком скриптов.</span><span class="sxs-lookup"><span data-stu-id="c0e95-106">Exits the current scope, which can be a function, script, or script block.</span></span>

## <a name="long-description"></a><span data-ttu-id="c0e95-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="c0e95-107">Long description</span></span>

<span data-ttu-id="c0e95-108">`return`Ключевое слово выполняет выход из функции, скрипта или блока скрипта.</span><span class="sxs-lookup"><span data-stu-id="c0e95-108">The `return` keyword exits a function, script, or script block.</span></span> <span data-ttu-id="c0e95-109">Он может использоваться для выхода из области в определенной точке, для возвращения значения или для указания на достижение конца области.</span><span class="sxs-lookup"><span data-stu-id="c0e95-109">It can be used to exit a scope at a specific point, to return a value, or to indicate that the end of the scope has been reached.</span></span>

<span data-ttu-id="c0e95-110">Пользователи, знакомые с языками, например C или C, \# могут использовать `return` ключевое слово, чтобы логика не выглядела явно.</span><span class="sxs-lookup"><span data-stu-id="c0e95-110">Users who are familiar with languages like C or C\# might want to use the `return` keyword to make the logic of leaving a scope explicit.</span></span>

<span data-ttu-id="c0e95-111">В PowerShell результаты каждой инструкции возвращаются в виде выходных данных даже без оператора, содержащего ключевое слово return.</span><span class="sxs-lookup"><span data-stu-id="c0e95-111">In PowerShell, the results of each statement are returned as output, even without a statement that contains the Return keyword.</span></span> <span data-ttu-id="c0e95-112">Такие языки, как C или C \# , возвращают только значения или значения, заданные `return` ключевым словом.</span><span class="sxs-lookup"><span data-stu-id="c0e95-112">Languages like C or C\# return only the value or values that are specified by the `return` keyword.</span></span>

> [!NOTE]
> <span data-ttu-id="c0e95-113">Начиная с PowerShell 5,0, в PowerShell добавлен язык для определения классов с помощью формального синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="c0e95-113">Beginning in PowerShell 5.0, PowerShell added language for defining classes, by using formal syntax.</span></span>  <span data-ttu-id="c0e95-114">В контексте класса PowerShell ничего не выводится из метода, за исключением того, что указывается с помощью `return` инструкции.</span><span class="sxs-lookup"><span data-stu-id="c0e95-114">In the context of a PowerShell class, nothing is output from a method except what you specify using a `return` statement.</span></span> <span data-ttu-id="c0e95-115">Дополнительные сведения о классах PowerShell можно узнать в [about_Classes](about_Classes.md).</span><span class="sxs-lookup"><span data-stu-id="c0e95-115">You can read more about PowerShell classes in [about_Classes](about_Classes.md).</span></span>

### <a name="syntax"></a><span data-ttu-id="c0e95-116">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c0e95-116">Syntax</span></span>

<span data-ttu-id="c0e95-117">Синтаксис `return` ключевого слова выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c0e95-117">The syntax for the `return` keyword is as follows:</span></span>

```
return [<expression>]
```

<span data-ttu-id="c0e95-118">`return`Ключевое слово может располагаться отдельно, а за ним может следовать значение или выражение следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c0e95-118">The `return` keyword can appear alone, or it can be followed by a value or expression, as follows:</span></span>

```powershell
return
return $a
return (2 + $a)
```

### <a name="examples"></a><span data-ttu-id="c0e95-119">Примеры</span><span class="sxs-lookup"><span data-stu-id="c0e95-119">Examples</span></span>

<span data-ttu-id="c0e95-120">В следующем примере `return` ключевое слово используется для выхода из функции в определенной точке, если выполняется условное выполнение.</span><span class="sxs-lookup"><span data-stu-id="c0e95-120">The following example uses the `return` keyword to exit a function at a specific point if a conditional is met.</span></span> <span data-ttu-id="c0e95-121">Нечетные числа не умножаются, поскольку оператор return завершается до выполнения этой инструкции.</span><span class="sxs-lookup"><span data-stu-id="c0e95-121">Odd numbers are not multiplied because the return statement exits before that statement can execute.</span></span>

```powershell
function MultiplyEven
{
    param($number)

    if ($number % 2) { return "$number is not even" }
    $number * 2
}

1..10 | ForEach-Object {MultiplyEven -Number $_}
```

```output
1 is not even
4
3 is not even
8
5 is not even
12
7 is not even
16
9 is not even
20
```

<span data-ttu-id="c0e95-122">В PowerShell значения могут возвращаться, даже если `return` ключевое слово не используется.</span><span class="sxs-lookup"><span data-stu-id="c0e95-122">In PowerShell, values can be returned even if the `return` keyword is not used.</span></span>
<span data-ttu-id="c0e95-123">Возвращаются результаты каждой инструкции.</span><span class="sxs-lookup"><span data-stu-id="c0e95-123">The results of each statement are returned.</span></span> <span data-ttu-id="c0e95-124">Например, следующие инструкции возвращают значение `$a` переменной:</span><span class="sxs-lookup"><span data-stu-id="c0e95-124">For example, the following statements return the value of the `$a` variable:</span></span>

```powershell
$a
return
```

<span data-ttu-id="c0e95-125">Следующая инструкция также возвращает значение `$a` :</span><span class="sxs-lookup"><span data-stu-id="c0e95-125">The following statement also returns the value of `$a`:</span></span>

```powershell
return $a
```

<span data-ttu-id="c0e95-126">Следующий пример включает оператор, позволяющий пользователю понять, что функция выполняет вычисление:</span><span class="sxs-lookup"><span data-stu-id="c0e95-126">The following example includes a statement intended to let the user know that the function is performing a calculation:</span></span>

```powershell
function calculation {
    param ($value)

    "Please wait. Working on calculation..."
    $value += 73
    return $value
}

$a = calculation 14
```

<span data-ttu-id="c0e95-127">"Подождите.</span><span class="sxs-lookup"><span data-stu-id="c0e95-127">The "Please wait.</span></span> <span data-ttu-id="c0e95-128">Работа с вычислениями... " строка не отображается.</span><span class="sxs-lookup"><span data-stu-id="c0e95-128">Working on calculation..." string is not displayed.</span></span> <span data-ttu-id="c0e95-129">Вместо этого он присваивается `$a` переменной, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="c0e95-129">Instead, it is assigned to the `$a` variable, as in the following example:</span></span>

```
PS> $a
Please wait. Working on calculation...
87
```

<span data-ttu-id="c0e95-130">И информационная строка, и результат вычисления возвращаются функцией и присваиваются `$a` переменной.</span><span class="sxs-lookup"><span data-stu-id="c0e95-130">Both the informational string and the result of the calculation are returned by the function and assigned to the `$a` variable.</span></span>

<span data-ttu-id="c0e95-131">Если вы хотите отобразить сообщение в функции, начиная с PowerShell 5,0, можно использовать `Information` поток.</span><span class="sxs-lookup"><span data-stu-id="c0e95-131">If you would like to display a message within your function, beginning in PowerShell 5.0, you can use the `Information` stream.</span></span> <span data-ttu-id="c0e95-132">Приведенный ниже код исправляет приведенный выше пример с помощью `Write-Information` командлета с `InformationAction` **продолжением**.</span><span class="sxs-lookup"><span data-stu-id="c0e95-132">The code below corrects the above example using the `Write-Information` cmdlet with a `InformationAction` of **Continue**.</span></span>

```powershell
function calculation {
    param ($value)

    Write-Information "Please wait. Working on calculation..." -InformationAction Continue
    $value += 73
    return $value
}

$a = calculation 14
```

```output
Please wait. Working on calculation...
C:\PS> $a
87
```

### <a name="return-values-and-the-pipeline"></a><span data-ttu-id="c0e95-133">Возвращаемые значения и конвейер</span><span class="sxs-lookup"><span data-stu-id="c0e95-133">Return values and the Pipeline</span></span>

<span data-ttu-id="c0e95-134">При возврате коллекции из блока скрипта или функции PowerShell автоматически выполняет откат элементов и передает их по одному за раз через конвейер.</span><span class="sxs-lookup"><span data-stu-id="c0e95-134">When you return a collection from your script block or function, PowerShell automatically unrolls the members and passes them one at a time through the pipeline.</span></span> <span data-ttu-id="c0e95-135">Это происходит из-за обработки PowerShell по одному времени.</span><span class="sxs-lookup"><span data-stu-id="c0e95-135">This is due to PowerShell's one-at-a-time processing.</span></span> <span data-ttu-id="c0e95-136">Дополнительные сведения см. в разделе [about_pipelines](about_pipelines.md).</span><span class="sxs-lookup"><span data-stu-id="c0e95-136">For more information, see [about_pipelines](about_pipelines.md).</span></span>

<span data-ttu-id="c0e95-137">Эта концепция показана в следующем примере функции, возвращающей массив чисел.</span><span class="sxs-lookup"><span data-stu-id="c0e95-137">This concept is illustrated by the following sample function that returns an array of numbers.</span></span> <span data-ttu-id="c0e95-138">Выходные данные функции передаются в командлет, `Measure-Object` который подсчитывает количество объектов в конвейере.</span><span class="sxs-lookup"><span data-stu-id="c0e95-138">The output from the function is piped to the `Measure-Object` cmdlet which counts the number of objects in the pipeline.</span></span>

```powershell
function Test-Return
{
    $array = 1,2,3
    return $array
}
Test-Return | Measure-Object
```

```Output
Count    : 3
Average  :
Sum      :
Maximum  :
Minimum  :
Property :
```

<span data-ttu-id="c0e95-139">Чтобы принудительно вернуть коллекцию в качестве одного объекта в конвейер, используйте один из следующих двух методов:</span><span class="sxs-lookup"><span data-stu-id="c0e95-139">To force a script block or function to return collection as a single object to the pipeline, use one of the following two methods:</span></span>

- <span data-ttu-id="c0e95-140">Выражение унарного массива</span><span class="sxs-lookup"><span data-stu-id="c0e95-140">Unary array expression</span></span>

  <span data-ttu-id="c0e95-141">Используя унарное выражение, можно отправить возвращаемое значение вниз по конвейеру в виде одного объекта, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="c0e95-141">Utilizing a unary expression you can send your return value down the pipeline as a single object as illustrated by the following example.</span></span>

  ```powershell
  function Test-Return
  {
      $array = 1,2,3
      return (, $array)
  }
  Test-Return | Measure-Object
  ```

  ```Output
  Count    : 1
  Average  :
  Sum      :
  Maximum  :
  Minimum  :
  Property :
  ```

- <span data-ttu-id="c0e95-142">`Write-Output` параметр WITH **GetEnumerator** .</span><span class="sxs-lookup"><span data-stu-id="c0e95-142">`Write-Output` with **NoEnumerate** parameter.</span></span>

  <span data-ttu-id="c0e95-143">Можно также использовать `Write-Output` командлет с параметром **GetEnumerator** .</span><span class="sxs-lookup"><span data-stu-id="c0e95-143">You can also use the `Write-Output` cmdlet with the **NoEnumerate** parameter.</span></span> <span data-ttu-id="c0e95-144">В приведенном ниже примере `Measure-Object` командлет используется для подсчета объектов, отправленных в конвейер из примера функции с помощью `return` ключевого слова.</span><span class="sxs-lookup"><span data-stu-id="c0e95-144">The example below uses the `Measure-Object` cmdlet to count the objects sent to the pipeline from the sample function by the `return` keyword.</span></span>

  ```powershell
  function Test-Return
  {
      $array = 1, 2, 3
      return Write-Output -NoEnumerate $array
  }

  Test-Return | Measure-Object
  ```

  ```Output
  Count    : 1
  Average  :
  Sum      :
  Maximum  :
  Minimum  :
  Property :
  ```

## <a name="see-also"></a><span data-ttu-id="c0e95-145">См. также статью</span><span class="sxs-lookup"><span data-stu-id="c0e95-145">See also</span></span>

[<span data-ttu-id="c0e95-146">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="c0e95-146">about_Language_Keywords</span></span>](about_Language_Keywords.md)

[<span data-ttu-id="c0e95-147">about_Functions</span><span class="sxs-lookup"><span data-stu-id="c0e95-147">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="c0e95-148">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="c0e95-148">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="c0e95-149">about_Classes</span><span class="sxs-lookup"><span data-stu-id="c0e95-149">about_Classes</span></span>](about_Classes.md)

[<span data-ttu-id="c0e95-150">Write-Information</span><span class="sxs-lookup"><span data-stu-id="c0e95-150">Write-Information</span></span>](xref:Microsoft.PowerShell.Utility.Write-Information)

[<span data-ttu-id="c0e95-151">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="c0e95-151">about_Script_Blocks</span></span>](about_Script_Blocks.md)

