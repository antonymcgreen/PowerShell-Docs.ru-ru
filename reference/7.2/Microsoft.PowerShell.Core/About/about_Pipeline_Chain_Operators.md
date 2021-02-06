---
description: Описывает цепочки конвейеров с помощью `&&` `||` операторов и в PowerShell.
Locale: en-US
ms.date: 09/30/2019
schema: 2.0.0
title: about_Pipeline_Chain_Operators
ms.openlocfilehash: ece84ec061126401e53bf58112cd79a07a816e8d
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605303"
---
# <a name="about-pipeline-chain-operators"></a><span data-ttu-id="f6dc9-103">Сведения об операторах цепочки конвейеров</span><span class="sxs-lookup"><span data-stu-id="f6dc9-103">About Pipeline Chain Operators</span></span>

## <a name="short-description"></a><span data-ttu-id="f6dc9-104">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="f6dc9-104">Short description</span></span>

<span data-ttu-id="f6dc9-105">Описывает цепочки конвейеров с помощью `&&` `||` операторов и в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f6dc9-105">Describes chaining pipelines with the `&&` and `||` operators in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="f6dc9-106">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="f6dc9-106">Long description</span></span>

<span data-ttu-id="f6dc9-107">Начиная с PowerShell 7, PowerShell реализует `&&` операторы и `||` для условного сцепления конвейеров.</span><span class="sxs-lookup"><span data-stu-id="f6dc9-107">Beginning in PowerShell 7, PowerShell implements the `&&` and `||` operators to conditionally chain pipelines.</span></span> <span data-ttu-id="f6dc9-108">Эти операторы известны в PowerShell как *Операторы цепочки конвейеров* и похожи на [списки и или](https://pubs.opengroup.org/onlinepubs/009695399/utilities/xcu_chap02.html#tag_02_09_03) в оболочках POSIX, таких как bash, ЗШ и SH, а также на [символы условной обработки](/previous-versions/windows/it-pro/windows-xp/bb490954(v=technet.10)#using-multiple-commands-and-conditional-processing-symbols) в командной оболочке Windows (cmd.exe).</span><span class="sxs-lookup"><span data-stu-id="f6dc9-108">These operators are known in PowerShell as *pipeline chain operators*, and are similar to [AND-OR lists](https://pubs.opengroup.org/onlinepubs/009695399/utilities/xcu_chap02.html#tag_02_09_03) in POSIX shells like bash, zsh and sh, as well as [conditional processing symbols](/previous-versions/windows/it-pro/windows-xp/bb490954(v=technet.10)#using-multiple-commands-and-conditional-processing-symbols) in the Windows Command Shell (cmd.exe).</span></span>

<span data-ttu-id="f6dc9-109">Оператор `&&` выполняет конвейер в правой части, если конвейер в левой части был выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="f6dc9-109">The `&&` operator executes the right-hand pipeline, if the left-hand pipeline succeeded.</span></span> <span data-ttu-id="f6dc9-110">И наоборот, оператор `||` выполняет конвейер в правой части, если конвейер в левой части не удалось выполнить.</span><span class="sxs-lookup"><span data-stu-id="f6dc9-110">Conversely, the `||` operator executes the right-hand pipeline if the left-hand pipeline failed.</span></span>

<span data-ttu-id="f6dc9-111">Для определения того, был ли выполнен конвейер, эти операторы используют переменные `$?` и `$LASTEXITCODE`.</span><span class="sxs-lookup"><span data-stu-id="f6dc9-111">These operators use the `$?` and `$LASTEXITCODE` variables to determine if a pipeline failed.</span></span> <span data-ttu-id="f6dc9-112">Это позволяет использовать их с собственными командами, а не только с командлетами или функциями.</span><span class="sxs-lookup"><span data-stu-id="f6dc9-112">This allows you to use them with native commands and not just with cmdlets or functions.</span></span> <span data-ttu-id="f6dc9-113">Пример:</span><span class="sxs-lookup"><span data-stu-id="f6dc9-113">For example:</span></span>

```powershell
# Create an SSH key pair - if successful copy the public key to clipboard
ssh-keygen -t rsa -b 2048 && Get-Content -Raw ~\.ssh\id_rsa.pub | clip
```

### <a name="examples"></a><span data-ttu-id="f6dc9-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="f6dc9-114">Examples</span></span>

#### <a name="two-successful-commands"></a><span data-ttu-id="f6dc9-115">Две успешные команды</span><span class="sxs-lookup"><span data-stu-id="f6dc9-115">Two successful commands</span></span>

```powershell
Write-Output 'First' && Write-Output 'Second'
```

```Output
First
Second
```

#### <a name="first-command-fails-causing-second-not-to-be-executed"></a><span data-ttu-id="f6dc9-116">Первая команда завершается неудачно, что привело к невыполнению второго</span><span class="sxs-lookup"><span data-stu-id="f6dc9-116">First command fails, causing second not to be executed</span></span>

```powershell
Write-Error 'Bad' && Write-Output 'Second'
```

```Output
Write-Error: Bad
```

#### <a name="first-command-succeeds-so-the-second-command-is-not-executed"></a><span data-ttu-id="f6dc9-117">Первая команда выполняется, поэтому вторая команда не выполняется</span><span class="sxs-lookup"><span data-stu-id="f6dc9-117">First command succeeds, so the second command is not executed</span></span>

```powershell
Write-Output 'First' || Write-Output 'Second'
```

```Output
First
```

#### <a name="first-command-fails-so-the-second-command-is-executed"></a><span data-ttu-id="f6dc9-118">Первая команда завершается ошибкой, поэтому выполняется Вторая команда.</span><span class="sxs-lookup"><span data-stu-id="f6dc9-118">First command fails, so the second command is executed</span></span>

```powershell
Write-Error 'Bad' || Write-Output 'Second'
```

```Output
Write-Error: Bad
Second
```

<span data-ttu-id="f6dc9-119">Успешное завершение конвейера определяется значением `$?` переменной, которое PowerShell автоматически задает после выполнения конвейера в зависимости от состояния выполнения.</span><span class="sxs-lookup"><span data-stu-id="f6dc9-119">Pipeline success is defined by the value of the `$?` variable, which PowerShell automatically sets after executing a pipeline based on its execution status.</span></span>
<span data-ttu-id="f6dc9-120">Это означает, что операторы цепочки конвейера имеют следующие эквиваленты:</span><span class="sxs-lookup"><span data-stu-id="f6dc9-120">This means that pipeline chain operators have the following equivalence:</span></span>

```powershell
Test-Command '1' && Test-Command '2'
```

<span data-ttu-id="f6dc9-121">работает так же, как</span><span class="sxs-lookup"><span data-stu-id="f6dc9-121">works the same as</span></span>

```powershell
Test-Command '1'; if ($?) { Test-Command '2' }
```

<span data-ttu-id="f6dc9-122">и</span><span class="sxs-lookup"><span data-stu-id="f6dc9-122">and</span></span>

```powershell
Test-Command '1' || Test-Command '2'
```

<span data-ttu-id="f6dc9-123">работает так же, как</span><span class="sxs-lookup"><span data-stu-id="f6dc9-123">works the same as</span></span>

```powershell
Test-Command '1'; if (-not $?) { Test-Command '2' }
```

### <a name="assignment-from-pipeline-chains"></a><span data-ttu-id="f6dc9-124">Назначение из цепочек конвейера</span><span class="sxs-lookup"><span data-stu-id="f6dc9-124">Assignment from pipeline chains</span></span>

<span data-ttu-id="f6dc9-125">Назначение переменной из цепочки конвейера выполняется путем объединения всех конвейеров в цепочке:</span><span class="sxs-lookup"><span data-stu-id="f6dc9-125">Assigning a variable from a pipeline chain takes the concatenation of all the pipelines in the chain:</span></span>

```powershell
$result = Write-Output '1' && Write-Output '2'
$result
```

```Output
1
2
```

<span data-ttu-id="f6dc9-126">Если во время назначения из цепочки конвейера возникает ошибка, связанная со сценарием, то назначение не выполняется.</span><span class="sxs-lookup"><span data-stu-id="f6dc9-126">If a script-terminating error occurs during assignment from a pipeline chain, the assignment does not succeed:</span></span>

```powershell
try
{
    $result = Write-Output 'Value' && $(throw 'Bad')
}
catch
{
    # Do nothing, just squash the error
}

"Result: $result"
```

```Output
Result:
```

### <a name="operator-syntax-and-precedence"></a><span data-ttu-id="f6dc9-127">Синтаксис операторов и их приоритет</span><span class="sxs-lookup"><span data-stu-id="f6dc9-127">Operator syntax and precedence</span></span>

<span data-ttu-id="f6dc9-128">В отличие от других операторов `&&` и для обработки `||` конвейеров, а не для таких выражений, как `+` или `-and` , например.</span><span class="sxs-lookup"><span data-stu-id="f6dc9-128">Unlike other operators, `&&` and `||` operate on pipelines, rather than on expressions like `+` or `-and`, for example.</span></span>

<span data-ttu-id="f6dc9-129">`&&` и `||` имеют более низкий приоритет, чем конвейер ( `|` ) или перенаправление ( `>` ), но более высокий приоритет по сравнению с операторами задания ( `&` ), присваиванием ( `=` ) или точкой с запятой ( `;` ).</span><span class="sxs-lookup"><span data-stu-id="f6dc9-129">`&&` and `||` have a lower precedence than piping (`|`) or redirection (`>`), but a higher precedence than job operators (`&`), assignment (`=`) or semicolons (`;`).</span></span> <span data-ttu-id="f6dc9-130">Это означает, что конвейеры в цепочке конвейера могут быть перенаправлены по отдельности, а все цепочки конвейеров могут быть фоновыми, назначены переменным или разделены инструкциями.</span><span class="sxs-lookup"><span data-stu-id="f6dc9-130">This means that pipelines within a pipeline chain can be individually redirected, and that entire pipeline chains can be backgrounded, assigned to variables, or separated as statements.</span></span>

<span data-ttu-id="f6dc9-131">Чтобы использовать синтаксис более низкого приоритета в цепочке конвейера, рассмотрите возможность использования круглых скобок `(...)` .</span><span class="sxs-lookup"><span data-stu-id="f6dc9-131">To use lower precedence syntax within a pipeline chain, consider the use of parentheses `(...)`.</span></span>
<span data-ttu-id="f6dc9-132">Аналогично, чтобы внедрить инструкцию в цепочку конвейера, `$(...)` можно использовать часть выражения.</span><span class="sxs-lookup"><span data-stu-id="f6dc9-132">Similarly, to embed a statement within a pipeline chain, a subexpression `$(...)` can be used.</span></span>
<span data-ttu-id="f6dc9-133">Это может быть полезно для объединения машинных команд с потоком управления:</span><span class="sxs-lookup"><span data-stu-id="f6dc9-133">This can be useful for combining native commands with control flow:</span></span>

```powershell
foreach ($file in 'file1','file2','file3')
{
    # When find succeeds, the loop breaks
    find $file && Write-Output "Found $file" && $(break)
}
```

```Output
find: file1: No such file or directory
file2
Found file2
```

<span data-ttu-id="f6dc9-134">Начиная с PowerShell 7, поведение этих синтаксисов было изменено так, чтобы `$?` оно было задано как ожидается при успешном или неудачном выполнении команды в круглых скобках или части выражения.</span><span class="sxs-lookup"><span data-stu-id="f6dc9-134">As of PowerShell 7, the behaviour of these syntaxes has been changed so that `$?` is set as expected when a command succeeds or fails within parentheses or a subexpression.</span></span>

<span data-ttu-id="f6dc9-135">Как и большинство других операторов в PowerShell, они `&&` `||` также имеют *левую ассоциативность*, то есть группируются слева.</span><span class="sxs-lookup"><span data-stu-id="f6dc9-135">Like most other operators in PowerShell, `&&` and `||` are also *left-associative*, meaning they group from the left.</span></span> <span data-ttu-id="f6dc9-136">Пример:</span><span class="sxs-lookup"><span data-stu-id="f6dc9-136">For example:</span></span>

```powershell
Get-ChildItem -Path ./file.txt || Write-Error "file.txt does not exist" && Get-Content -Raw ./file.txt
```

<span data-ttu-id="f6dc9-137">будет группироваться как:</span><span class="sxs-lookup"><span data-stu-id="f6dc9-137">will group as:</span></span>

```
[Get-ChildItem -Path ./file.txt || Write-Error "file.txt does not exist"] && Get-Content -Raw ./file.txt
```

<span data-ttu-id="f6dc9-138">эквивалентно:</span><span class="sxs-lookup"><span data-stu-id="f6dc9-138">being equivalent to:</span></span>

```powershell
Get-ChildItem -Path ./file.txt

if (-not $?) { Write-Error "file.txt does not exist" }

if ($?) { Get-Content -Raw ./file.txt }
```

### <a name="error-interaction"></a><span data-ttu-id="f6dc9-139">Взаимодействие с ошибкой</span><span class="sxs-lookup"><span data-stu-id="f6dc9-139">Error interaction</span></span>

<span data-ttu-id="f6dc9-140">Операторы цепочки конвейеров не применяют к ошибкам.</span><span class="sxs-lookup"><span data-stu-id="f6dc9-140">Pipeline chain operators do not absorb errors.</span></span> <span data-ttu-id="f6dc9-141">Если инструкция в цепочке конвейера вызывает ошибку, завершающуюся сценарием, то цепь конвейера завершается.</span><span class="sxs-lookup"><span data-stu-id="f6dc9-141">When a statement in a pipeline chain throws a script-terminating error, the pipeline chain is terminated.</span></span>

<span data-ttu-id="f6dc9-142">Пример:</span><span class="sxs-lookup"><span data-stu-id="f6dc9-142">For example:</span></span>

```powershell
$(throw 'Bad') || Write-Output '2'
```

```Output
Exception: Bad
```

<span data-ttu-id="f6dc9-143">Даже если ошибка перехвачена, цепь конвейера по-прежнему завершается:</span><span class="sxs-lookup"><span data-stu-id="f6dc9-143">Even when the error is caught, the pipeline chain is still terminated:</span></span>

```powershell
try
{
    $(throw 'Bad') || Write-Output '2'
}
catch
{
    Write-Output "Caught: $_"
}
Write-Output 'Done'
```

```Output
Caught: Bad
Done
```

<span data-ttu-id="f6dc9-144">Если ошибка не завершается или завершается только конвейер, то цепь конвейера будет продолжаться, в соответствии со значением `$?` :</span><span class="sxs-lookup"><span data-stu-id="f6dc9-144">If an error is non-terminating, or only terminates a pipeline, the pipeline chain continues, respecting the value of `$?`:</span></span>

```powershell
function Test-NonTerminatingError
{
    [CmdletBinding()]
    param()

    $exception = [System.Exception]::new('BAD')
    $errorId = 'BAD'
    $errorCategory = 'NotSpecified'

    $errorRecord = [System.Management.Automation.ErrorRecord]::new($exception, $errorId, $errorCategory, $null)

    $PSCmdlet.WriteError($errorRecord)
}

Test-NonTerminatingError || Write-Output 'Second'
```

```Output
Test-NonTerminatingError: BAD
Second
```

### <a name="chaining-pipelines-rather-than-commands"></a><span data-ttu-id="f6dc9-145">Сцепление конвейеров, а не команд</span><span class="sxs-lookup"><span data-stu-id="f6dc9-145">Chaining pipelines rather than commands</span></span>

<span data-ttu-id="f6dc9-146">Операторы цепочки конвейеров по имени можно использовать для сцепления конвейеров, а не просто команд.</span><span class="sxs-lookup"><span data-stu-id="f6dc9-146">Pipeline chain operators, by their name, can be used to chain pipelines, rather than just commands.</span></span> <span data-ttu-id="f6dc9-147">Это соответствует поведению других оболочек, но может усложнить *успешно* определить:</span><span class="sxs-lookup"><span data-stu-id="f6dc9-147">This matches the behavior of other shells, but can make *success* harder to determine:</span></span>

```powershell
function Test-NotTwo
{
    [CmdletBinding()]
    param(
      [Parameter(ValueFromPipeline)]
      $Input
    )

    process
    {
        if ($Input -ne 2)
        {
            return $Input
        }

        $exception = [System.Exception]::new('Input is 2')
        $errorId = 'InputTwo'
        $errorCategory = 'InvalidData'

        $errorRecord = [System.Management.Automation.ErrorRecord]::new($exception, $errorId, $errorCategory, $null)

        $PSCmdlet.WriteError($errorRecord)
    }
}

1,2,3 | Test-NotTwo && Write-Output 'All done!'
```

```Output
1
Test-NotTwo : Input is 2
3
```

<span data-ttu-id="f6dc9-148">Обратите внимание, что `Write-Output 'All done!'` не выполняется, поскольку считается `Test-NotTwo` неудачным после создания неустранимой ошибки.</span><span class="sxs-lookup"><span data-stu-id="f6dc9-148">Note that `Write-Output 'All done!'` is not executed, since `Test-NotTwo` is deemed to have failed after generating the non-terminating error.</span></span>

## <a name="see-also"></a><span data-ttu-id="f6dc9-149">См. также</span><span class="sxs-lookup"><span data-stu-id="f6dc9-149">See also</span></span>

- [<span data-ttu-id="f6dc9-150">about_Operators</span><span class="sxs-lookup"><span data-stu-id="f6dc9-150">about_Operators</span></span>](about_Operators.md)
- [<span data-ttu-id="f6dc9-151">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="f6dc9-151">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)
- [<span data-ttu-id="f6dc9-152">about_pipelines</span><span class="sxs-lookup"><span data-stu-id="f6dc9-152">about_pipelines</span></span>](about_pipelines.md)

