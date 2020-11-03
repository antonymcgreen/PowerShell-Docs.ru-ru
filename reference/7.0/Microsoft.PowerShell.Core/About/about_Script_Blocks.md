---
description: Определяет, что такое блок скрипта, и объясняет, как использовать блоки сценариев на языке программирования PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_script_blocks?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Script_Blocks
ms.openlocfilehash: 1793deded63669399246d18132bbc5b6d6c4810b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93230970"
---
# <a name="about-script-blocks"></a><span data-ttu-id="a5022-104">О блоках скриптов</span><span class="sxs-lookup"><span data-stu-id="a5022-104">About Script Blocks</span></span>

## <a name="short-description"></a><span data-ttu-id="a5022-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="a5022-105">Short description</span></span>

<span data-ttu-id="a5022-106">Определяет, что такое блок скрипта, и объясняет, как использовать блоки сценариев на языке программирования PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a5022-106">Defines what a script block is and explains how to use script blocks in the PowerShell programming language.</span></span>

## <a name="long-description"></a><span data-ttu-id="a5022-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="a5022-107">Long description</span></span>

<span data-ttu-id="a5022-108">В языке программирования PowerShell блок скрипта представляет собой коллекцию инструкций или выражений, которые можно использовать как единый блок.</span><span class="sxs-lookup"><span data-stu-id="a5022-108">In the PowerShell programming language, a script block is a collection of statements or expressions that can be used as a single unit.</span></span>
<span data-ttu-id="a5022-109">Блок сценария может принимать аргументы и возвращать значения.</span><span class="sxs-lookup"><span data-stu-id="a5022-109">A script block can accept arguments and return values.</span></span>

<span data-ttu-id="a5022-110">Синтаксический блок скрипта — это список операторов в фигурных скобках, как показано в следующем синтаксисе:</span><span class="sxs-lookup"><span data-stu-id="a5022-110">Syntactically, a script block is a statement list in braces, as shown in the following syntax:</span></span>

```
{<statement list>}
```

<span data-ttu-id="a5022-111">Блок скрипта возвращает выходные данные всех команд в блоке скрипта либо как один объект, либо как массив.</span><span class="sxs-lookup"><span data-stu-id="a5022-111">A script block returns the output of all the commands in the script block, either as a single object or as an array.</span></span>

<span data-ttu-id="a5022-112">Также можно указать возвращаемое значение с помощью `return` ключевого слова.</span><span class="sxs-lookup"><span data-stu-id="a5022-112">You can also specify a return value using the `return` keyword.</span></span> <span data-ttu-id="a5022-113">`return`Ключевое слово не влияет на другие выходные данные, возвращаемые блоком скрипта, и не подавляет их.</span><span class="sxs-lookup"><span data-stu-id="a5022-113">The `return` keyword does not affect or suppress other output returned from your script block.</span></span> <span data-ttu-id="a5022-114">Однако `return` ключевое слово завершает блок сценария в этой строке.</span><span class="sxs-lookup"><span data-stu-id="a5022-114">However, the `return` keyword exits the script block at that line.</span></span> <span data-ttu-id="a5022-115">Дополнительные сведения см. в разделе [about_Return](about_Return.md).</span><span class="sxs-lookup"><span data-stu-id="a5022-115">For more information, see [about_Return](about_Return.md).</span></span>

<span data-ttu-id="a5022-116">Как и функции, блок скрипта может включать параметры.</span><span class="sxs-lookup"><span data-stu-id="a5022-116">Like functions, a script block can include parameters.</span></span> <span data-ttu-id="a5022-117">Используйте ключевое слово Param для присвоения именованных параметров, как показано в следующем синтаксисе:</span><span class="sxs-lookup"><span data-stu-id="a5022-117">Use the Param keyword to assign named parameters, as shown in the following syntax:</span></span>

```
{
Param([type]$Parameter1 [,[type]$Parameter2])
<statement list>
}
```

> [!NOTE]
> <span data-ttu-id="a5022-118">В блоке сценария, в отличие от функции, нельзя указывать параметры за пределами фигурных скобок.</span><span class="sxs-lookup"><span data-stu-id="a5022-118">In a script block, unlike a function, you cannot specify parameters outside the braces.</span></span>

<span data-ttu-id="a5022-119">Как и функции, блоки скриптов могут содержать `DynamicParam` `Begin` `Process` Ключевые слова,, и `End` .</span><span class="sxs-lookup"><span data-stu-id="a5022-119">Like functions, script blocks can include the `DynamicParam`, `Begin`, `Process`, and `End` keywords.</span></span> <span data-ttu-id="a5022-120">Дополнительные сведения см. в разделе [about_Functions](about_Functions.md) и [about_Functions_Advanced](about_Functions_Advanced.md).</span><span class="sxs-lookup"><span data-stu-id="a5022-120">For more information, see [about_Functions](about_Functions.md) and [about_Functions_Advanced](about_Functions_Advanced.md).</span></span>

## <a name="using-script-blocks"></a><span data-ttu-id="a5022-121">Использование блоков сценариев</span><span class="sxs-lookup"><span data-stu-id="a5022-121">Using Script Blocks</span></span>

<span data-ttu-id="a5022-122">Блок скрипта — это экземпляр Microsoft .NET типа платформы `System.Management.Automation.ScriptBlock` .</span><span class="sxs-lookup"><span data-stu-id="a5022-122">A script block is an instance of a Microsoft .NET Framework type `System.Management.Automation.ScriptBlock`.</span></span> <span data-ttu-id="a5022-123">Команды могут иметь значения параметров блока сценария.</span><span class="sxs-lookup"><span data-stu-id="a5022-123">Commands can have script block parameter values.</span></span> <span data-ttu-id="a5022-124">Например, `Invoke-Command` командлет имеет `ScriptBlock` параметр, который принимает значение блока сценария, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="a5022-124">For example, the `Invoke-Command` cmdlet has a `ScriptBlock` parameter that takes a script block value, as shown in this example:</span></span>

```powershell
Invoke-Command -ScriptBlock { Get-Process }
```

```Output
Handles  NPM(K)    PM(K)     WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----     ----- -----   ------     -- -----------
999          28    39100     45020   262    15.88   1844 communicator
721          28    32696     36536   222    20.84   4028 explorer
...
```

<span data-ttu-id="a5022-125">`Invoke-Command` также может выполнять блоки скриптов с блоками параметров.</span><span class="sxs-lookup"><span data-stu-id="a5022-125">`Invoke-Command` can also execute script blocks that have parameter blocks.</span></span>
<span data-ttu-id="a5022-126">Параметры присваиваются по положению с помощью параметра **ArgumentList** .</span><span class="sxs-lookup"><span data-stu-id="a5022-126">Parameters are assigned by position using the **ArgumentList** parameter.</span></span>

```powershell
Invoke-Command -ScriptBlock { param($p1, $p2)
"p1: $p1"
"p2: $p2"
} -ArgumentList "First", "Second"
```

```Output
p1: First
p2: Second
```

<span data-ttu-id="a5022-127">Блок скрипта в предыдущем примере использует `param` ключевое слово для создания параметров `$p1` и `$p2` .</span><span class="sxs-lookup"><span data-stu-id="a5022-127">The script block in the preceding example uses the `param` keyword to create a parameters `$p1` and `$p2`.</span></span> <span data-ttu-id="a5022-128">Строка "First" привязывается к первому параметру ( `$p1` ), а "Second" — к ( `$p2` ).</span><span class="sxs-lookup"><span data-stu-id="a5022-128">The string "First" is bound to the first parameter (`$p1`) and "Second" is bound to (`$p2`).</span></span>

<span data-ttu-id="a5022-129">Дополнительные сведения о поведении **ArgumentList** см. в разделе [about_Splatting](about_Splatting.md#splatting-with-arrays).</span><span class="sxs-lookup"><span data-stu-id="a5022-129">For more information about the behavior of **ArgumentList** , see [about_Splatting](about_Splatting.md#splatting-with-arrays).</span></span>

<span data-ttu-id="a5022-130">Переменные можно использовать для хранения и выполнения блоков сценариев.</span><span class="sxs-lookup"><span data-stu-id="a5022-130">You can use variables to store and execute script blocks.</span></span> <span data-ttu-id="a5022-131">В приведенном ниже примере блок скрипта сохраняется в переменной и передается в `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="a5022-131">The example below stores a script block in a variable and passes it to `Invoke-Command`.</span></span>

```powershell
$a = { Get-Service BITS }
Invoke-Command -ScriptBlock $a
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  BITS               Background Intelligent Transfer Ser...
```

<span data-ttu-id="a5022-132">Оператор Call — это еще один способ выполнения блоков сценариев, хранящихся в переменной.</span><span class="sxs-lookup"><span data-stu-id="a5022-132">The call operator is another way to execute script blocks stored in a variable.</span></span>
<span data-ttu-id="a5022-133">Как и `Invoke-Command` оператор Call, выполняет блок скрипта в дочерней области.</span><span class="sxs-lookup"><span data-stu-id="a5022-133">Like `Invoke-Command`, the call operator executes the script block in a child scope.</span></span> <span data-ttu-id="a5022-134">Оператор Call может упростить использование параметров с блоками скриптов.</span><span class="sxs-lookup"><span data-stu-id="a5022-134">The call operator can make it easier for you to use parameters with your script blocks.</span></span>

```powershell
$a ={ param($p1, $p2)
"p1: $p1"
"p2: $p2"
}
&$a -p2 "First" -p1 "Second"
```

```Output
p1: Second
p2: First
```

<span data-ttu-id="a5022-135">Выходные данные из блоков скрипта можно сохранить в переменной с помощью присваивания.</span><span class="sxs-lookup"><span data-stu-id="a5022-135">You can store the output from your script blocks in a variable using assignment.</span></span>

```
PS>  $a = { 1 + 1}
PS>  $b = &$a
PS>  $b
2
```

```
PS>  $a = { 1 + 1}
PS>  $b = Invoke-Command $a
PS>  $b
2
```

<span data-ttu-id="a5022-136">Дополнительные сведения о операторе Call см. в разделе [about_Operators](about_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="a5022-136">For more information about the call operator, see [about_Operators](about_Operators.md).</span></span>

## <a name="using-delay-bind-script-blocks-with-parameters"></a><span data-ttu-id="a5022-137">Использование блоков скриптов с отложенной привязкой с параметрами</span><span class="sxs-lookup"><span data-stu-id="a5022-137">Using delay-bind script blocks with parameters</span></span>

<span data-ttu-id="a5022-138">Типизированный параметр, который принимает входные данные конвейера ( `by Value` ) или ( `by PropertyName` ), позволяет использовать блоки скриптов с **отложенной привязкой** для параметра.</span><span class="sxs-lookup"><span data-stu-id="a5022-138">A typed parameter that accepts pipeline input (`by Value`) or (`by PropertyName`) enables use of **delay-bind** script blocks on the parameter.</span></span>
<span data-ttu-id="a5022-139">В блоке скрипта **с отложенной привязкой** можно ссылаться на перенаправленный объект, используя переменную конвейера `$_` .</span><span class="sxs-lookup"><span data-stu-id="a5022-139">Within the **delay-bind** script block, you can reference the piped in object using the pipeline variable `$_`.</span></span>

```powershell
# Renames config.log to old_config.log
dir config.log | Rename-Item -NewName {"old_" + $_.Name}
```

<span data-ttu-id="a5022-140">В более сложных командлетах блоки скриптов с отложенной привязкой позволяют повторно использовать один из переданных объектов для заполнения других параметров.</span><span class="sxs-lookup"><span data-stu-id="a5022-140">In more complex cmdlets, delay-bind script blocks allow the reuse of one piped in object to populate other parameters.</span></span>

<span data-ttu-id="a5022-141">Примечания к блокам скриптов **отложенной привязки** в качестве параметров:</span><span class="sxs-lookup"><span data-stu-id="a5022-141">Notes on **delay-bind** script blocks as parameters:</span></span>

- <span data-ttu-id="a5022-142">Необходимо явно указать все имена параметров, используемые с блоками скриптов **отложенной привязки** .</span><span class="sxs-lookup"><span data-stu-id="a5022-142">You must explicitly specify any parameter names you use with **delay-bind** script blocks.</span></span>
- <span data-ttu-id="a5022-143">Параметр не должен быть нетипизированным, а тип параметра не может быть `[scriptblock]` или `[object]` .</span><span class="sxs-lookup"><span data-stu-id="a5022-143">The parameter must not be untyped, and the parameter's type cannot be `[scriptblock]` or `[object]`.</span></span>
- <span data-ttu-id="a5022-144">Если используется блок скрипта **отложенной привязки** без предоставления входных данных конвейера, возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="a5022-144">You receive an error if you use a **delay-bind** script block without providing pipeline input.</span></span>

  ```powershell
  Rename-Item -NewName {$_.Name + ".old"}
  ```

  ```Output
  Rename-Item : Cannot evaluate parameter 'NewName' because its argument is
  specified as a script block and there is no input. A script block cannot
  be evaluated without input.
  At line:1 char:23
  +  Rename-Item -NewName {$_.Name + ".old"}
  +                       ~~~~~~~~~~~~~~~~~~
      + CategoryInfo          : MetadataError: (:) [Rename-Item],
        ParameterBindingException
      + FullyQualifiedErrorId : ScriptBlockArgumentNoInput,
        Microsoft.PowerShell.Commands.RenameItemCommand
  ```

## <a name="see-also"></a><span data-ttu-id="a5022-145">См. также:</span><span class="sxs-lookup"><span data-stu-id="a5022-145">See Also</span></span>

[<span data-ttu-id="a5022-146">about_Functions</span><span class="sxs-lookup"><span data-stu-id="a5022-146">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="a5022-147">about_Functions_Advanced</span><span class="sxs-lookup"><span data-stu-id="a5022-147">about_Functions_Advanced</span></span>](about_Functions_Advanced.md)

[<span data-ttu-id="a5022-148">about_Operators</span><span class="sxs-lookup"><span data-stu-id="a5022-148">about_Operators</span></span>](about_Operators.md)
