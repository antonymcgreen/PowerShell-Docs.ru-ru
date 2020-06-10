---
title: Все, что вы хотели знать о ShouldProcess
description: ShouldProcess — важный компонент, который часто упускают из виду. Параметры WhatIf и Confirm упрощают добавление в функции.
ms.date: 05/23/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: 1d9110302a191b90bd11bdf742f77704a8c9d6f0
ms.sourcegitcommit: ed4a895d672334c7b02fb7ef6e950dbc2ba4a197
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/28/2020
ms.locfileid: "84149487"
---
# <a name="everything-you-wanted-to-know-about-shouldprocess"></a><span data-ttu-id="f8075-104">Все, что вы хотели знать о ShouldProcess</span><span class="sxs-lookup"><span data-stu-id="f8075-104">Everything you wanted to know about ShouldProcess</span></span>

<span data-ttu-id="f8075-105">Некоторые возможности функций PowerShell значительно улучшают способ взаимодействия с ними пользователей.</span><span class="sxs-lookup"><span data-stu-id="f8075-105">PowerShell functions have several features that greatly improve the way users interact with them.</span></span>
<span data-ttu-id="f8075-106">Одна из таких важных возможностей, которую часто упускают из виду, — это поддержка параметров `-WhatIf` и `-Confirm`, которые можно легко добавить в функции.</span><span class="sxs-lookup"><span data-stu-id="f8075-106">One important feature that is often overlooked is `-WhatIf` and `-Confirm` support and it's easy to add to your functions.</span></span> <span data-ttu-id="f8075-107">В этой статье мы подробно рассмотрим, как реализовать эту возможность.</span><span class="sxs-lookup"><span data-stu-id="f8075-107">In this article, we dive deep into how to implement this feature.</span></span>

> [!NOTE]
> <span data-ttu-id="f8075-108">[Оригинал][] этой статьи впервые был опубликован в блоге автора [@KevinMarquette][].</span><span class="sxs-lookup"><span data-stu-id="f8075-108">The [original version][] of this article appeared on the blog written by [@KevinMarquette][].</span></span> <span data-ttu-id="f8075-109">Команда разработчиков PowerShell благодарит Кевина за то, что он поделился с нами этим материалом.</span><span class="sxs-lookup"><span data-stu-id="f8075-109">The PowerShell team thanks Kevin for sharing this content with us.</span></span> <span data-ttu-id="f8075-110">Читайте его блог — [PowerShellExplained.com][].</span><span class="sxs-lookup"><span data-stu-id="f8075-110">Please check out his blog at [PowerShellExplained.com][].</span></span>

<span data-ttu-id="f8075-111">Это простая возможность, которую можно включить в функциях, чтобы подстраховать пользователей, если им это необходимо.</span><span class="sxs-lookup"><span data-stu-id="f8075-111">This is a simple feature you can enable in your functions to provide a safety net for the users that need it.</span></span> <span data-ttu-id="f8075-112">Нет ничего страшнее, чем в первый раз использовать потенциально опасную команду.</span><span class="sxs-lookup"><span data-stu-id="f8075-112">There's nothing scarier than running a command that you know can be dangerous for the first time.</span></span> <span data-ttu-id="f8075-113">Совсем другое дело, если она запущена с параметром `-WhatIf`.</span><span class="sxs-lookup"><span data-stu-id="f8075-113">The option to run it with `-WhatIf` can make a big difference.</span></span>

## <a name="commonparameters"></a><span data-ttu-id="f8075-114">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="f8075-114">CommonParameters</span></span>

<span data-ttu-id="f8075-115">Прежде чем мы рассмотрим реализацию этих [общих параметров][], я хочу вкратце рассказать о том, как они используются.</span><span class="sxs-lookup"><span data-stu-id="f8075-115">Before we look at implementing these [common parameters][], I want to take a quick look at how they're used.</span></span>

## <a name="using--whatif"></a><span data-ttu-id="f8075-116">Использование параметра -WhatIf</span><span class="sxs-lookup"><span data-stu-id="f8075-116">Using -WhatIf</span></span>

<span data-ttu-id="f8075-117">Если команда поддерживает параметр `-WhatIf`, вы можете увидеть, что делает эта команда, не внося фактические изменения.</span><span class="sxs-lookup"><span data-stu-id="f8075-117">When a command supports the `-WhatIf` parameter, it allows you to see what the command would have done instead of making changes.</span></span> <span data-ttu-id="f8075-118">Это хороший способ протестировать влияние команды, особенно перед выполнением каких-либо необратимых действий.</span><span class="sxs-lookup"><span data-stu-id="f8075-118">it's a good way to test out the impact of a command, especially before you do something destructive.</span></span>

```powershell
PS C:\temp> Remove-Item -Path .\myfile1.txt -WhatIf
What if: Performing the operation "Remove File" on target "C:\Temp\myfile1.txt".
```

<span data-ttu-id="f8075-119">Если команда правильно реализует `ShouldProcess`, она должна отобразить все изменения, которые были бы внесены.</span><span class="sxs-lookup"><span data-stu-id="f8075-119">If the command correctly implements `ShouldProcess`, it should show you all the changes that it would have made.</span></span> <span data-ttu-id="f8075-120">Ниже приведен пример использования подстановочного знака для удаления нескольких файлов.</span><span class="sxs-lookup"><span data-stu-id="f8075-120">Here is an example using a wildcard to delete multiple files.</span></span>

```powershell
PS C:\temp> Remove-Item -Path * -WhatIf
What if: Performing the operation "Remove File" on target "C:\Temp\myfile1.txt".
What if: Performing the operation "Remove File" on target "C:\Temp\myfile2.txt".
What if: Performing the operation "Remove File" on target "C:\Temp\importantfile.txt".
```

## <a name="using--confirm"></a><span data-ttu-id="f8075-121">Использование параметра -Confirm</span><span class="sxs-lookup"><span data-stu-id="f8075-121">Using -Confirm</span></span>

<span data-ttu-id="f8075-122">Команды, поддерживающие `-WhatIf`, также поддерживают `-Confirm`.</span><span class="sxs-lookup"><span data-stu-id="f8075-122">Commands that support `-WhatIf` also support `-Confirm`.</span></span> <span data-ttu-id="f8075-123">Это дает возможность подтвердить действие перед его выполнением.</span><span class="sxs-lookup"><span data-stu-id="f8075-123">This gives you a chance confirm an action before performing it.</span></span>

```powershell
PS C:\temp> Remove-Item .\myfile1.txt -Confirm

Confirm
Are you sure you want to perform this action?
Performing the operation "Remove File" on target "C:\Temp\myfile1.txt".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="f8075-124">В этом случае у вас есть несколько вариантов: продолжить выполнение, пропустить изменение или остановить выполнение скрипта.</span><span class="sxs-lookup"><span data-stu-id="f8075-124">In this case, you have multiple options that allow you to continue, skip a change, or stop the script.</span></span> <span data-ttu-id="f8075-125">Эти параметры описаны в справке, которая вызывается при запросе из командной строки.</span><span class="sxs-lookup"><span data-stu-id="f8075-125">The help prompt describes each of those options like this.</span></span>

```Output
Y - Continue with only the next step of the operation.
A - Continue with all the steps of the operation.
N - Skip this operation and proceed with the next operation.
L - Skip this operation and all subsequent operations.
S - Pause the current pipeline and return to the command prompt. Type "exit" to resume the pipeline.
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

### <a name="localization"></a><span data-ttu-id="f8075-126">Локализация</span><span class="sxs-lookup"><span data-stu-id="f8075-126">Localization</span></span>

<span data-ttu-id="f8075-127">Этот запрос локализован в PowerShell, поэтому язык изменяется в зависимости от языка операционной системы.</span><span class="sxs-lookup"><span data-stu-id="f8075-127">This prompt is localized in PowerShell so the language changes based on the language of your operating system.</span></span> <span data-ttu-id="f8075-128">Это одна из автоматических возможностей PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f8075-128">This is one more thing that PowerShell manages for you.</span></span>

### <a name="switch-parameters"></a><span data-ttu-id="f8075-129">Параметры-переключатели</span><span class="sxs-lookup"><span data-stu-id="f8075-129">Switch parameters</span></span>

<span data-ttu-id="f8075-130">Давайте вкратце рассмотрим способы передачи значения в параметр-переключатель.</span><span class="sxs-lookup"><span data-stu-id="f8075-130">Let's take quick moment to look at ways to pass a value to a switch parameter.</span></span> <span data-ttu-id="f8075-131">Основная причина, по которой я использую их для вызова, заключается в том, что зачастую вызываемые функции требуется передавать в значения параметров.</span><span class="sxs-lookup"><span data-stu-id="f8075-131">The main reason I call this out is that you often want to pass parameter values to functions you call.</span></span>

<span data-ttu-id="f8075-132">Первый подход — это использовать определенный синтаксис параметров, который применим для любых параметров, но в основном используется для параметров-переключателей.</span><span class="sxs-lookup"><span data-stu-id="f8075-132">The first approach is a specific parameter syntax that can be used for all parameters but you mostly see it used for switch parameters.</span></span> <span data-ttu-id="f8075-133">Чтобы присоединить значение к параметру, необходимо поставить двоеточие.</span><span class="sxs-lookup"><span data-stu-id="f8075-133">You specify a colon to attach a value to the parameter.</span></span>

```powershell
Remove-Item -Path:* -WhatIf:$true
```

<span data-ttu-id="f8075-134">То же самое можно сделать и с переменной.</span><span class="sxs-lookup"><span data-stu-id="f8075-134">You can do the same with a variable.</span></span>

```powershell
$DoWhatIf = $true
Remove-Item -Path * -WhatIf:$DoWhatIf
```

<span data-ttu-id="f8075-135">Второй подход заключается в использовании хэш-таблицы для сплаттинга значения.</span><span class="sxs-lookup"><span data-stu-id="f8075-135">The second approach is to use a hashtable to splat the value.</span></span>

```powershell
$RemoveSplat = @{
    Path = '*'
    WhatIf = $true
}
Remove-Item @RemoveSplat
```

<span data-ttu-id="f8075-136">Если вы не знакомы с использованием хэш-таблиц или сплаттинга, то у меня есть другая статья на эту тему, в которой есть [все, что вы хотели узнать о хэш-таблицах][].</span><span class="sxs-lookup"><span data-stu-id="f8075-136">If you're new to hashtables or splatting, I have another article on that covers [everything you wanted to know about hashtables][].</span></span>

## <a name="supportsshouldprocess"></a><span data-ttu-id="f8075-137">SupportsShouldProcess</span><span class="sxs-lookup"><span data-stu-id="f8075-137">SupportsShouldProcess</span></span>

<span data-ttu-id="f8075-138">Чтобы включить поддержку `-WhatIf` и `-Confirm`, для начала необходимо указать `SupportsShouldProcess` в `CmdletBinding` функции.</span><span class="sxs-lookup"><span data-stu-id="f8075-138">The first step to enable `-WhatIf` and `-Confirm` support is to specify `SupportsShouldProcess` in the `CmdletBinding` of your function.</span></span>

```powershell
function Test-ShouldProcess {
    [CmdletBinding(SupportsShouldProcess)]
    param()
    Remove-Item .\myfile1.txt
}
```

<span data-ttu-id="f8075-139">Указав `SupportsShouldProcess` таким образом, можно вызвать функцию с параметром `-WhatIf` (или `-Confirm`).</span><span class="sxs-lookup"><span data-stu-id="f8075-139">By specifying `SupportsShouldProcess` in this way, we can now call our function with `-WhatIf` (or `-Confirm`).</span></span>

```powershell
PS> Test-ShouldProcess -WhatIf
What if: Performing the operation "Remove File" on target "C:\Temp\myfile1.txt".
```

<span data-ttu-id="f8075-140">Обратите внимание, что я не создаю параметр с именем `-WhatIf`.</span><span class="sxs-lookup"><span data-stu-id="f8075-140">Notice that I did not create a parameter called `-WhatIf`.</span></span> <span data-ttu-id="f8075-141">Он создается автоматически, если задать свойство `SupportsShouldProcess`.</span><span class="sxs-lookup"><span data-stu-id="f8075-141">Specifying `SupportsShouldProcess` automatically creates it for us.</span></span> <span data-ttu-id="f8075-142">Если задать параметр `-WhatIf` для `Test-ShouldProcess`, некоторые из вызываемых объектов также выполняют обработку `-WhatIf`.</span><span class="sxs-lookup"><span data-stu-id="f8075-142">When we specify the `-WhatIf` parameter on `Test-ShouldProcess`, some things we call also perform `-WhatIf` processing.</span></span>

### <a name="trust-but-verify"></a><span data-ttu-id="f8075-143">Доверяйте, но проверяйте</span><span class="sxs-lookup"><span data-stu-id="f8075-143">Trust but verify</span></span>

<span data-ttu-id="f8075-144">Полагаться на то, что все вызовы наследуют значение `-WhatIf`, довольно опасно.</span><span class="sxs-lookup"><span data-stu-id="f8075-144">There's some danger here trusting that everything you call inherits `-WhatIf` values.</span></span> <span data-ttu-id="f8075-145">В остальных примерах я предполагаю, что это не так, и при вызове других команд буду задавать все параметры явно.</span><span class="sxs-lookup"><span data-stu-id="f8075-145">For the rest of the examples, I'm going to assume that it doesn't work and be very explicit when making calls to other commands.</span></span> <span data-ttu-id="f8075-146">Рекомендую и вам придерживаться того же подхода.</span><span class="sxs-lookup"><span data-stu-id="f8075-146">I recommend that you do the same.</span></span>

```powershell
function Test-ShouldProcess {
    [CmdletBinding(SupportsShouldProcess)]
    param()
    Remove-Item .\myfile1.txt -WhatIf:$WhatIf
}
```

<span data-ttu-id="f8075-147">Позже, когда вы получите более полное представление об этих возможностях, я вернусь к этому вопросу и расскажу о различных тонкостях.</span><span class="sxs-lookup"><span data-stu-id="f8075-147">I will revisit the nuances much later once you have a better understanding of all the pieces in play.</span></span>

## <a name="pscmdletshouldprocess"></a><span data-ttu-id="f8075-148">$PSCmdlet.ShouldProcess</span><span class="sxs-lookup"><span data-stu-id="f8075-148">$PSCmdlet.ShouldProcess</span></span>

<span data-ttu-id="f8075-149">Метод, который позволяет реализовать свойство `SupportsShouldProcess`, называется `$PSCmdlet.ShouldProcess`.</span><span class="sxs-lookup"><span data-stu-id="f8075-149">The method that allows you to implement `SupportsShouldProcess` is `$PSCmdlet.ShouldProcess`.</span></span> <span data-ttu-id="f8075-150">Вы вызываете `$PSCmdlet.ShouldProcess(...)`, чтобы узнать, нужно ли обработать ту или иную логику, а остальное PowerShell выполняет автоматически.</span><span class="sxs-lookup"><span data-stu-id="f8075-150">You call `$PSCmdlet.ShouldProcess(...)` to see if you should process some logic and PowerShell takes care of the rest.</span></span> <span data-ttu-id="f8075-151">Давайте начнем с примера.</span><span class="sxs-lookup"><span data-stu-id="f8075-151">Let's start with an example:</span></span>

```powershell
function Test-ShouldProcess {
    [CmdletBinding(SupportsShouldProcess)]
    param()

    $file = Get-ChildItem './myfile1.txt'
    if($PSCmdlet.ShouldProcess($file.Name)){
        $file.Delete()
    }
}
```

<span data-ttu-id="f8075-152">Вызов `$PSCmdlet.ShouldProcess($file.name)` проверяет наличие параметра `-WhatIf` (и `-Confirm`) и обрабатывает его соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="f8075-152">The call to `$PSCmdlet.ShouldProcess($file.name)` checks for the `-WhatIf` (and `-Confirm` parameter) then handles it accordingly.</span></span> <span data-ttu-id="f8075-153">`-WhatIf` приводит к тому, что `ShouldProcess` выводит описание изменения и возвращает `$false`.</span><span class="sxs-lookup"><span data-stu-id="f8075-153">The `-WhatIf` causes `ShouldProcess` to output a description of the change and return `$false`:</span></span>

```powershell
PS> Test-ShouldProcess -WhatIf
What if: Performing the operation "Test-ShouldProcess" on target "myfile1.txt".
```

<span data-ttu-id="f8075-154">Вызов с `-Confirm` приводит к приостановке выполнения скрипта и отображению для пользователя вариантов продолжения.</span><span class="sxs-lookup"><span data-stu-id="f8075-154">A call using `-Confirm` pauses the script and prompts the user with the option to continue.</span></span> <span data-ttu-id="f8075-155">Он возвращает `$true`, если пользователь выбрал `Y`.</span><span class="sxs-lookup"><span data-stu-id="f8075-155">It returns `$true` if the user selected `Y`.</span></span>

```powershell
PS> Test-ShouldProcess -Confirm
Confirm
Are you sure you want to perform this action?
Performing the operation "Test-ShouldProcess" on target "myfile1.txt".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="f8075-156">Замечательной особенностью метода `$PSCmdlet.ShouldProcess` является то, что он дублируется в подробных выходных данных.</span><span class="sxs-lookup"><span data-stu-id="f8075-156">An awesome feature of `$PSCmdlet.ShouldProcess` is that it doubles as verbose output.</span></span> <span data-ttu-id="f8075-157">Я часто использую это при реализации `ShouldProcess`.</span><span class="sxs-lookup"><span data-stu-id="f8075-157">I depend on this often when implementing `ShouldProcess`.</span></span>

```powershell
PS> Test-ShouldProcess -Verbose
VERBOSE: Performing the operation "Test-ShouldProcess" on target "myfile1.txt".
```

### <a name="overloads"></a><span data-ttu-id="f8075-158">Перегрузки</span><span class="sxs-lookup"><span data-stu-id="f8075-158">Overloads</span></span>

<span data-ttu-id="f8075-159">Для `$PSCmdlet.ShouldProcess` предусмотрено несколько различных перегрузок с разными параметрами для настройки вывода сообщений.</span><span class="sxs-lookup"><span data-stu-id="f8075-159">There are a few different overloads for `$PSCmdlet.ShouldProcess` with different parameters for customizing the messaging.</span></span> <span data-ttu-id="f8075-160">Первая из них уже использовалась в приведенном выше примере.</span><span class="sxs-lookup"><span data-stu-id="f8075-160">We already saw the first one in the example above.</span></span> <span data-ttu-id="f8075-161">Давайте подробнее рассмотрим каждую из них.</span><span class="sxs-lookup"><span data-stu-id="f8075-161">Let's take a closer look at it.</span></span>

```powershell
function Test-ShouldProcess {
    [CmdletBinding(SupportsShouldProcess)]
    param()

    if($PSCmdlet.ShouldProcess('TARGET')){
        # ...
    }
}
```

<span data-ttu-id="f8075-162">Эта выводит результат, включающий имя функции и целевой объект (значение параметра).</span><span class="sxs-lookup"><span data-stu-id="f8075-162">This produces output that includes both the function name and the target (value of the parameter).</span></span>

```powershell
What if: Performing the operation "Test-ShouldProcess" on target "TARGET".
```

<span data-ttu-id="f8075-163">Если указать второй параметр в качестве операции, вместо имени функции в сообщении будет использоваться значение операции.</span><span class="sxs-lookup"><span data-stu-id="f8075-163">Specifying a second parameter as the operation uses the operation value instead of the function name in the message.</span></span>

```powershell
## $PSCmdlet.ShouldProcess('TARGET','OPERATION')
What if: Performing the operation "OPERATION" on target "TARGET".
```

<span data-ttu-id="f8075-164">Следующий вариант — указать три параметра для полной настройки сообщения.</span><span class="sxs-lookup"><span data-stu-id="f8075-164">The next option is to specify three parameters to fully customize the message.</span></span> <span data-ttu-id="f8075-165">Если используются три параметра, первый из них является сообщением в целом.</span><span class="sxs-lookup"><span data-stu-id="f8075-165">When three parameters are used, the first one is the entire message.</span></span> <span data-ttu-id="f8075-166">Два других параметра по-прежнему используются в выходных данных сообщения `-Confirm`.</span><span class="sxs-lookup"><span data-stu-id="f8075-166">The second two parameters are still used in the `-Confirm` message output.</span></span>

```powershell
## $PSCmdlet.ShouldProcess('MESSAGE','TARGET','OPERATION')
What if: MESSAGE
```

### <a name="quick-parameter-reference"></a><span data-ttu-id="f8075-167">Ссылка на параметр</span><span class="sxs-lookup"><span data-stu-id="f8075-167">Quick parameter reference</span></span>

<span data-ttu-id="f8075-168">Если вы читаете эту статью, только чтобы выяснить, какие параметры следует использовать, ниже приведен краткий справочник со сведениями о том, как параметры изменяют сообщение в различных сценариях `-WhatIf`.</span><span class="sxs-lookup"><span data-stu-id="f8075-168">Just in case you came here only to figure out what parameters you should use, here is a quick reference showing how the parameters change the message in the different `-WhatIf` scenarios.</span></span>

```powershell
## $PSCmdlet.ShouldProcess('TARGET')
What if: Performing the operation "FUNCTION_NAME" on target "TARGET".

## $PSCmdlet.ShouldProcess('TARGET','OPERATION')
What if: Performing the operation "OPERATION" on target "TARGET".

## $PSCmdlet.ShouldProcess('MESSAGE','TARGET','OPERATION')
What if: MESSAGE
```

<span data-ttu-id="f8075-169">Я обычно использую метод с двумя параметрами.</span><span class="sxs-lookup"><span data-stu-id="f8075-169">I tend to use the one with two parameters.</span></span>

### <a name="shouldprocessreason"></a><span data-ttu-id="f8075-170">ShouldProcessReason</span><span class="sxs-lookup"><span data-stu-id="f8075-170">ShouldProcessReason</span></span>

<span data-ttu-id="f8075-171">Существует также четвертая перегрузка. Она сложнее, чем друге,</span><span class="sxs-lookup"><span data-stu-id="f8075-171">We have a fourth overload that's more advanced than the others.</span></span> <span data-ttu-id="f8075-172">и позволяет получить причину выполнения `ShouldProcess`.</span><span class="sxs-lookup"><span data-stu-id="f8075-172">It allows you to get the reason `ShouldProcess` was executed.</span></span> <span data-ttu-id="f8075-173">Я добавляю ее здесь для полноты картины, так как вместо этого можно просто проверить, действительно ли значение `$WhatIf` равно `$true`.</span><span class="sxs-lookup"><span data-stu-id="f8075-173">I'm only adding this here for completeness because we can just check if `$WhatIf` is `$true` instead.</span></span>

```powershell
$reason = ''
if($PSCmdlet.ShouldProcess('MESSAGE','TARGET','OPERATION',[ref]$reason)){
    Write-Output "Some Action"
}
$reason
```

<span data-ttu-id="f8075-174">Переменную `$reason` необходимо передать в четвертый параметр в виде ссылочной переменной с `[ref]`.</span><span class="sxs-lookup"><span data-stu-id="f8075-174">We have to pass the `$reason` variable into the fourth parameter as a reference variable with `[ref]`.</span></span> <span data-ttu-id="f8075-175">`ShouldProcess` заполняет `$reason` значением `None` или `WhatIf`.</span><span class="sxs-lookup"><span data-stu-id="f8075-175">`ShouldProcess` populates `$reason` with the value `None` or `WhatIf`.</span></span> <span data-ttu-id="f8075-176">Я бы не назвал это полезной возможностью, так что у меня нет причин ее использовать.</span><span class="sxs-lookup"><span data-stu-id="f8075-176">I didn't say this was useful and I have had no reason to ever use it.</span></span>

### <a name="where-to-place-it"></a><span data-ttu-id="f8075-177">Место размещения</span><span class="sxs-lookup"><span data-stu-id="f8075-177">Where to place it</span></span>

<span data-ttu-id="f8075-178">Метод `ShouldProcess` используется, чтобы сделать скрипты безопаснее.</span><span class="sxs-lookup"><span data-stu-id="f8075-178">You use `ShouldProcess` to make your scripts safer.</span></span> <span data-ttu-id="f8075-179">Поэтому его можно использовать при внесении изменений в скрипты.</span><span class="sxs-lookup"><span data-stu-id="f8075-179">So you use it when your scripts are making changes.</span></span> <span data-ttu-id="f8075-180">Я предпочитаю размещать вызов `$PSCmdlet.ShouldProcess` как можно ближе к изменению.</span><span class="sxs-lookup"><span data-stu-id="f8075-180">I like to place the `$PSCmdlet.ShouldProcess` call as close to the change as possible.</span></span>

```powershell
## general logic and variable work
if ($PSCmdlet.ShouldProcess('TARGET','OPERATION')){
    # Change goes here
}
```

<span data-ttu-id="f8075-181">Если я обрабатываю коллекцию элементов, я вызываю этот метод для каждого элемента.</span><span class="sxs-lookup"><span data-stu-id="f8075-181">If I'm processing a collection of items, I call it for each item.</span></span> <span data-ttu-id="f8075-182">Поэтому вызов помещается внутри цикла foreach.</span><span class="sxs-lookup"><span data-stu-id="f8075-182">So the call gets placed inside the foreach loop.</span></span>

```powershell
foreach ($node in $collection){
    # general logic and variable work
    if ($PSCmdlet.ShouldProcess($node,'OPERATION')){
        # Change goes here
    }
}
```

<span data-ttu-id="f8075-183">Причина, по которой я располагаю `ShouldProcess` в непосредственной близости от этого изменения, заключается в том, что мне нужно обеспечить выполнение как можно большей части кода при заданном параметре `-WhatIf`.</span><span class="sxs-lookup"><span data-stu-id="f8075-183">The reason why I place `ShouldProcess` tightly around the change, is that I want as much code to execute as possible when `-WhatIf` is specified.</span></span> <span data-ttu-id="f8075-184">Я хочу, чтобы по возможности выполнялась установка и проверка. Тогда пользователь увидит эти ошибки.</span><span class="sxs-lookup"><span data-stu-id="f8075-184">I want the setup and validation to run if possible so the user gets to see those errors.</span></span>

<span data-ttu-id="f8075-185">Я также хотел бы использовать этот код в тестах Pester, которые проверяют мои проекты.</span><span class="sxs-lookup"><span data-stu-id="f8075-185">I also like to use this in my Pester tests that validate my projects.</span></span> <span data-ttu-id="f8075-186">Если у меня есть фрагмент логики, который трудно макетировать в Pester, я зачастую помещаю его в метод `ShouldProcess` и вызываю его в своих тестах с параметром `-WhatIf`.</span><span class="sxs-lookup"><span data-stu-id="f8075-186">If I have a piece of logic that is hard to mock in pester, I can often wrap it in `ShouldProcess` and call it with `-WhatIf` in my tests.</span></span> <span data-ttu-id="f8075-187">Лучше протестировать часть кода, чем не тестировать его вообще.</span><span class="sxs-lookup"><span data-stu-id="f8075-187">It's better to test some of your code than none of it.</span></span>

### <a name="whatifpreference"></a><span data-ttu-id="f8075-188">$WhatIfPreference</span><span class="sxs-lookup"><span data-stu-id="f8075-188">$WhatIfPreference</span></span>

<span data-ttu-id="f8075-189">Первая привилегированная переменная — `$WhatIfPreference`.</span><span class="sxs-lookup"><span data-stu-id="f8075-189">The first preference variable we have is `$WhatIfPreference`.</span></span> <span data-ttu-id="f8075-190">По умолчанию ее значение `$false`.</span><span class="sxs-lookup"><span data-stu-id="f8075-190">This is `$false` by default.</span></span> <span data-ttu-id="f8075-191">Если задать для нее значение `$true`, функция выполняется так, как если бы вы указали `-WhatIf`.</span><span class="sxs-lookup"><span data-stu-id="f8075-191">If you set it to `$true` then your function executes as if you specified `-WhatIf`.</span></span> <span data-ttu-id="f8075-192">Если задать это в сеансе, все команды будут выполняться с параметром `-WhatIf`.</span><span class="sxs-lookup"><span data-stu-id="f8075-192">If you set this in your session, all commands perform `-WhatIf` execution.</span></span>

<span data-ttu-id="f8075-193">При вызове функции с параметром `-WhatIf` значение `$WhatIfPreference` становится равным `$true` в области действия функции.</span><span class="sxs-lookup"><span data-stu-id="f8075-193">When you call a function with `-WhatIf`, the value of `$WhatIfPreference` gets set to `$true` inside the scope of your function.</span></span>

## <a name="confirmimpact"></a><span data-ttu-id="f8075-194">ConfirmImpact</span><span class="sxs-lookup"><span data-stu-id="f8075-194">ConfirmImpact</span></span>

<span data-ttu-id="f8075-195">Большинство моих примеров касаются `-WhatIf`, но все это также работает и при использовании `-Confirm` для отправки запроса пользователю.</span><span class="sxs-lookup"><span data-stu-id="f8075-195">Most of my examples are for `-WhatIf` but everything so far also works with `-Confirm` to prompt the user.</span></span> <span data-ttu-id="f8075-196">Для аргумента `ConfirmImpact` функции можно задать значение high, и тогда она будет выводить запрос пользователю, как если бы была вызвана с параметром `-Confirm`.</span><span class="sxs-lookup"><span data-stu-id="f8075-196">You can set the `ConfirmImpact` of the function to high and it prompts the user as if it was called with `-Confirm`.</span></span>

```powershell
function Test-ShouldProcess {
    [CmdletBinding(
        SupportsShouldProcess,
        ConfirmImpact = 'High'
    )]
    param()

    if ($PSCmdlet.ShouldProcess('TARGET')){
        Write-Output "Some Action"
    }
}
```

<span data-ttu-id="f8075-197">Этот вызов `Test-ShouldProcess` выполняет действие `-Confirm` из-за значения `High`.</span><span class="sxs-lookup"><span data-stu-id="f8075-197">This call to `Test-ShouldProcess` is performing the `-Confirm` action because of the `High` impact.</span></span>

```powershell
PS> Test-ShouldProcess

Confirm
Are you sure you want to perform this action?
Performing the operation "Test-ShouldProcess" on target "TARGET".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): y
Some Action
```

<span data-ttu-id="f8075-198">Очевидная проблема заключается в том, что теперь ее сложнее использовать в других скриптах без запроса пользователя.</span><span class="sxs-lookup"><span data-stu-id="f8075-198">The obvious issue is that now it's harder to use in other scripts without prompting the user.</span></span> <span data-ttu-id="f8075-199">В этом случае можно передать `$false` в `-Confirm`, чтобы подавить запрос.</span><span class="sxs-lookup"><span data-stu-id="f8075-199">In this case, we can pass a `$false` to `-Confirm` to suppress the prompt.</span></span>

```powershell
PS> Test-ShouldProcess -Confirm:$false
Some Action
```

<span data-ttu-id="f8075-200">Я расскажу, как добавить поддержку `-Force` в одном из следующих разделов.</span><span class="sxs-lookup"><span data-stu-id="f8075-200">I'll cover how to add `-Force` support in a later section.</span></span>

### <a name="confirmpreference"></a><span data-ttu-id="f8075-201">$ConfirmPreference</span><span class="sxs-lookup"><span data-stu-id="f8075-201">$ConfirmPreference</span></span>

<span data-ttu-id="f8075-202">`$ConfirmPreference` — это автоматическая переменная, определяющая, когда `ConfirmImpact` запрашивает подтверждение выполнения.</span><span class="sxs-lookup"><span data-stu-id="f8075-202">`$ConfirmPreference` is an automatic variable that controls when `ConfirmImpact` asks you to confirm execution.</span></span> <span data-ttu-id="f8075-203">Ниже приведены возможные значения для `$ConfirmPreference` и `ConfirmImpact`.</span><span class="sxs-lookup"><span data-stu-id="f8075-203">Here are the possible values for both `$ConfirmPreference` and `ConfirmImpact`.</span></span>

- `High`
- `Medium`
- `Low`
- `None`

<span data-ttu-id="f8075-204">С помощью этих значений можно указать различные уровни влияния для каждой функции.</span><span class="sxs-lookup"><span data-stu-id="f8075-204">With these values, you can specify different levels of impact for each function.</span></span> <span data-ttu-id="f8075-205">Если заданное для `$ConfirmPreference` значение выше, чем значение `ConfirmImpact`, запрос на подтверждение выполнения не выводится.</span><span class="sxs-lookup"><span data-stu-id="f8075-205">If you have `$ConfirmPreference` set to a value higher than `ConfirmImpact`, then you aren't prompted to confirm execution.</span></span>

<span data-ttu-id="f8075-206">По умолчанию для `$ConfirmPreference` задано значение `High`, а для `ConfirmImpact` — значение `Medium`.</span><span class="sxs-lookup"><span data-stu-id="f8075-206">By default, `$ConfirmPreference` is set to `High` and `ConfirmImpact` is `Medium`.</span></span> <span data-ttu-id="f8075-207">Если вы хотите, чтобы функция автоматически запрашивала подтверждение пользователя, задайте для аргумента `ConfirmImpact` значение `High`.</span><span class="sxs-lookup"><span data-stu-id="f8075-207">If you want your function to automatically prompt the user, set your `ConfirmImpact` to `High`.</span></span> <span data-ttu-id="f8075-208">В противном случае задайте для него значение `Medium`, если команда выполняет необратимое действие, и `Low`, если она всегда безопасна для выполнения в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="f8075-208">Otherwise set it to `Medium` if its destructive and use `Low` if the command is always safe run in production.</span></span> <span data-ttu-id="f8075-209">Если задать для него значение `none`, запрос на подтверждение не выводится, даже если задан параметр `-Confirm` (но поддержка `-WhatIf` по-прежнему предоставляется).</span><span class="sxs-lookup"><span data-stu-id="f8075-209">If you set it to `none`, it doesn't prompt even if `-Confirm` was specified (but it still gives you `-WhatIf` support).</span></span>

<span data-ttu-id="f8075-210">В случае вызова функции с параметром `-Confirm` значение `$ConfirmPreference` становится равным `Low` в области действия функции.</span><span class="sxs-lookup"><span data-stu-id="f8075-210">When calling a function with `-Confirm`, the value of `$ConfirmPreference` gets set to `Low` inside the scope of your function.</span></span>

### <a name="suppressing-nested-confirm-prompts"></a><span data-ttu-id="f8075-211">Подавление вложенных запросов на подтверждение</span><span class="sxs-lookup"><span data-stu-id="f8075-211">Suppressing nested confirm prompts</span></span>

<span data-ttu-id="f8075-212">Вызываемые функции могут получать значение `$ConfirmPreference`.</span><span class="sxs-lookup"><span data-stu-id="f8075-212">The `$ConfirmPreference` can get picked up by functions that you call.</span></span> <span data-ttu-id="f8075-213">Это может привести к ситуации, когда вы добавляете запрос на подтверждение, но при этом вызываемая функция также запрашивает его у пользователя.</span><span class="sxs-lookup"><span data-stu-id="f8075-213">This can create scenarios where you add a confirm prompt and the function you call also prompts the user.</span></span>

<span data-ttu-id="f8075-214">Я обычно предпочитаю использовать `-Confirm:$false` для вызываемых команд после того, как запрос уже обработан.</span><span class="sxs-lookup"><span data-stu-id="f8075-214">What I tend to do is specify `-Confirm:$false` on the commands that I call when I have already handled the prompting.</span></span>

```powershell
function Test-ShouldProcess {
    [CmdletBinding(SupportsShouldProcess)]
    param()

    $file = Get-ChildItem './myfile1.txt'
    if($PSCmdlet.ShouldProcess($file.Name)){
        Remove-Item -Path $file.FullName -Confirm:$false
    }
}
```

<span data-ttu-id="f8075-215">Таким образом, мы снова возвращаемся к предыдущему предупреждению. Есть ряд особенностей, от которых зависит, в каких ситуациях `-WhatIf` не передается в функцию и в каких ситуациях `-Confirm` передается в функцию.</span><span class="sxs-lookup"><span data-stu-id="f8075-215">This brings us back to an earlier warning: There are nuances as to when `-WhatIf` is not passed to a function and when `-Confirm` passes to a function.</span></span> <span data-ttu-id="f8075-216">Обещаю вернуться к этому вопросу позже.</span><span class="sxs-lookup"><span data-stu-id="f8075-216">I promise I'll get back to this later.</span></span>

## <a name="pscmdletshouldcontinue"></a><span data-ttu-id="f8075-217">$PSCmdlet.ShouldContinue</span><span class="sxs-lookup"><span data-stu-id="f8075-217">$PSCmdlet.ShouldContinue</span></span>

<span data-ttu-id="f8075-218">Если вам требуется более жесткий контроль, чем обеспечивает `ShouldProcess`, можно запустить запрос непосредственно с помощью `ShouldContinue`.</span><span class="sxs-lookup"><span data-stu-id="f8075-218">If you need more control than `ShouldProcess` provides, you can trigger the prompt directly with `ShouldContinue`.</span></span> <span data-ttu-id="f8075-219">`ShouldContinue` пропускает `$ConfirmPreference`, `ConfirmImpact`, `-Confirm`, `$WhatIfPreference` и `-WhatIf`, так как запрос выводится при каждом выполнении.</span><span class="sxs-lookup"><span data-stu-id="f8075-219">`ShouldContinue` ignores `$ConfirmPreference`, `ConfirmImpact`, `-Confirm`, `$WhatIfPreference`, and `-WhatIf` because it prompts every time it's executed.</span></span>

<span data-ttu-id="f8075-220">`ShouldProcess` и `ShouldContinue` можно легко перепутать.</span><span class="sxs-lookup"><span data-stu-id="f8075-220">At a quick glance, it's easy to confuse `ShouldProcess` and `ShouldContinue`.</span></span> <span data-ttu-id="f8075-221">Я обычно помню, что нужно использовать `ShouldProcess`, поскольку параметр в `CmdletBinding` называется `SupportsShouldProcess`.</span><span class="sxs-lookup"><span data-stu-id="f8075-221">I tend to remember to use `ShouldProcess` because the parameter is called `SupportsShouldProcess` in the `CmdletBinding`.</span></span>
<span data-ttu-id="f8075-222">Практически во всех сценариях следует использовать `ShouldProcess`.</span><span class="sxs-lookup"><span data-stu-id="f8075-222">You should use `ShouldProcess` in almost every scenario.</span></span> <span data-ttu-id="f8075-223">Именно поэтому я сначала рассматривал именно этот метод.</span><span class="sxs-lookup"><span data-stu-id="f8075-223">That is why I covered that method first.</span></span>

<span data-ttu-id="f8075-224">Давайте посмотрим на метод `ShouldContinue` в действии.</span><span class="sxs-lookup"><span data-stu-id="f8075-224">Let's take a look at `ShouldContinue` in action.</span></span>

```powershell
function Test-ShouldContinue {
    [CmdletBinding()]
    param()

    if($PSCmdlet.ShouldContinue('TARGET','OPERATION')){
        Write-Output "Some Action"
    }
}
```

<span data-ttu-id="f8075-225">В данном случае мы получаем простой запрос с несколькими вариантами.</span><span class="sxs-lookup"><span data-stu-id="f8075-225">This provides us a simpler prompt with fewer options.</span></span>

```powershell
Test-ShouldContinue

Second
TARGET
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="f8075-226">Основная проблема использования `ShouldContinue` заключается в том, что пользователь в таком случае должен работать в интерактивном режиме, потому что для него всегда отображется запрос.</span><span class="sxs-lookup"><span data-stu-id="f8075-226">The biggest issue with `ShouldContinue` is that it requires the user to run it interactively because it always prompts the user.</span></span> <span data-ttu-id="f8075-227">Вам всегда следует создавать такие средства, которые могут использоваться другими скриптами.</span><span class="sxs-lookup"><span data-stu-id="f8075-227">You should always be building tools that can be used by other scripts.</span></span> <span data-ttu-id="f8075-228">Для этого используется реализация `-Force`.</span><span class="sxs-lookup"><span data-stu-id="f8075-228">The way you do this is by implementing `-Force`.</span></span> <span data-ttu-id="f8075-229">Я вернусь к этой идее позже.</span><span class="sxs-lookup"><span data-stu-id="f8075-229">I'll revisit this idea later.</span></span>

### <a name="yes-to-all"></a><span data-ttu-id="f8075-230">Да для всех</span><span class="sxs-lookup"><span data-stu-id="f8075-230">Yes to all</span></span>

<span data-ttu-id="f8075-231">Для `ShouldProcess` этот вариант обрабатывается автоматически, но для `ShouldContinue` необходимо выполнить еще несколько действий.</span><span class="sxs-lookup"><span data-stu-id="f8075-231">This is automatically handled with `ShouldProcess` but we have to do a little more work for `ShouldContinue`.</span></span> <span data-ttu-id="f8075-232">Существует вторая перегрузка метода, в которую необходимо передать несколько значений по ссылке для управления логикой.</span><span class="sxs-lookup"><span data-stu-id="f8075-232">There's a second method overload where we have to pass in a few values by reference to control the logic.</span></span>

```powershell
function Test-ShouldContinue {
    [CmdletBinding()]
    param()

    $collection = 1..5
    $yesToAll = $false
    $noToAll = $false

    foreach($target in $collection) {

        $continue = $PSCmdlet.ShouldContinue(
                "TARGET_$target",
                'OPERATION',
                [ref]$yesToAll,
                [ref]$noToAll
            )

        if ($continue){
            Write-Output "Some Action [$target]"
        }
    }
}
```

<span data-ttu-id="f8075-233">Я добавил цикл `foreach` и коллекцию, чтобы показать их в действии.</span><span class="sxs-lookup"><span data-stu-id="f8075-233">I added a `foreach` loop and a collection to show it in action.</span></span> <span data-ttu-id="f8075-234">Я извлек вызов `ShouldContinue` из инструкции `if`, чтобы упростить чтение.</span><span class="sxs-lookup"><span data-stu-id="f8075-234">I pulled the `ShouldContinue` call out of the `if` statement to make it easier to read.</span></span> <span data-ttu-id="f8075-235">Вызов метода с четырьмя параметрами — далеко не самый лучший подход, но я постарался сделать его как можно более понятным.</span><span class="sxs-lookup"><span data-stu-id="f8075-235">Calling a method with four parameters starts to get a little ugly, but I tried to make it look as clean as I could.</span></span>

## <a name="implementing--force"></a><span data-ttu-id="f8075-236">Реализация -Force</span><span class="sxs-lookup"><span data-stu-id="f8075-236">Implementing -Force</span></span>

<span data-ttu-id="f8075-237">`ShouldProcess` и `ShouldContinue` должны реализовывать `-Force` различными способами.</span><span class="sxs-lookup"><span data-stu-id="f8075-237">`ShouldProcess` and `ShouldContinue` need to implement `-Force` in different ways.</span></span> <span data-ttu-id="f8075-238">Хитрость таких реализаций заключается в том, что метод `ShouldProcess` всегда должен выполняться, а `ShouldContinue` не должен выполняться, если указано `-Force`.</span><span class="sxs-lookup"><span data-stu-id="f8075-238">The trick to these implementations is that `ShouldProcess` should always get executed, but `ShouldContinue` should not get executed if `-Force` is specified.</span></span>

### <a name="shouldprocess--force"></a><span data-ttu-id="f8075-239">Параметр -Force метода ShouldProcess</span><span class="sxs-lookup"><span data-stu-id="f8075-239">ShouldProcess -Force</span></span>

<span data-ttu-id="f8075-240">Если задать для `ConfirmImpact` значение `high`, первое, что попытаются сделать пользователи, — это подавить его запрос с помощью `-Force`.</span><span class="sxs-lookup"><span data-stu-id="f8075-240">If you set your `ConfirmImpact` to `high`, the first thing your users are going to try is to suppress it with `-Force`.</span></span> <span data-ttu-id="f8075-241">Во всяком случае, это первое, что делаю я.</span><span class="sxs-lookup"><span data-stu-id="f8075-241">That's the first thing I do anyway.</span></span>

```powershell
Test-ShouldProcess -Force
Error: Test-ShouldProcess: A parameter cannot be found that matches parameter name 'force'.
```

<span data-ttu-id="f8075-242">Если вы припомните раздел `ConfirmImpact`, то поймете, что им на самом деле нужно вызвать его следующим образом.</span><span class="sxs-lookup"><span data-stu-id="f8075-242">If you recall from the `ConfirmImpact` section, they actually need to call it like this:</span></span>

```powershell
Test-ShouldProcess -Confirm:$false
```

<span data-ttu-id="f8075-243">Не все понимают, что это действительно необходимо сделать и что `-Confirm:$false` не подавляет `ShouldContinue`.</span><span class="sxs-lookup"><span data-stu-id="f8075-243">Not everyone realizes they need to do that and `-Confirm:$false` doesn't suppress `ShouldContinue`.</span></span>
<span data-ttu-id="f8075-244">Поэтому для нормальной работы пользователей мы должны реализовать `-Force`.</span><span class="sxs-lookup"><span data-stu-id="f8075-244">So we should implement `-Force` for the sanity of our users.</span></span> <span data-ttu-id="f8075-245">Взгляните на этот полный пример.</span><span class="sxs-lookup"><span data-stu-id="f8075-245">Take a look at this full example here:</span></span>

```powershell
function Test-ShouldProcess {
    [CmdletBinding(
        SupportsShouldProcess,
        ConfirmImpact = 'High'
    )]
    param(
        [Switch]$Force
    )

    if ($Force -and -not $Confirm){
        $ConfirmPreference = 'None'
    }

    if ($PSCmdlet.ShouldProcess('TARGET')){
        Write-Output "Some Action"
    }
}
```

<span data-ttu-id="f8075-246">Мы добавим собственный ключ `-Force` в качестве параметра и используем автоматический параметр `$Confirm`, доступный при добавлении `SupportsShouldProcess` в `CmdletBinding`.</span><span class="sxs-lookup"><span data-stu-id="f8075-246">We add our own `-Force` switch as a parameter and use the `$Confirm` automatic parameter that is available when adding `SupportsShouldProcess` in the `CmdletBinding`.</span></span>

```powershell
[CmdletBinding(
    SupportsShouldProcess,
    ConfirmImpact = 'High'
)]
param(
    [Switch]$Force
)
```

<span data-ttu-id="f8075-247">Здесь основное внимание следует уделить логике `-Force`.</span><span class="sxs-lookup"><span data-stu-id="f8075-247">Focusing in on the `-Force` logic here:</span></span>

```powershell
if ($Force -and -not $Confirm){
    $ConfirmPreference = 'None'
}
```

<span data-ttu-id="f8075-248">Если пользователь задает `-Force`, необходимо отключить запрос на подтверждение, если не указан параметр `-Confirm`.</span><span class="sxs-lookup"><span data-stu-id="f8075-248">If the user specifies `-Force`, we want to suppress the confirm prompt unless they also specify `-Confirm`.</span></span> <span data-ttu-id="f8075-249">Это позволит пользователю принудительно вносить изменения, но ему по-прежнему придется их подтверждать.</span><span class="sxs-lookup"><span data-stu-id="f8075-249">This allows a user to force a change but still confirm the change.</span></span> <span data-ttu-id="f8075-250">Затем мы зададим переменную `$ConfirmPreference` в локальной области, где наш вызов `ShouldProcess` ее обнаружит.</span><span class="sxs-lookup"><span data-stu-id="f8075-250">Then we set `$ConfirmPreference` in the local scope where our call to `ShouldProcess` discoverers it.</span></span>

```powershell
if ($PSCmdlet.ShouldProcess('TARGET')){
        Write-Output "Some Action"
    }
```

<span data-ttu-id="f8075-251">Если указать как `-Force`, так и `-WhatIf`, приоритет будет у `-WhatIf`.</span><span class="sxs-lookup"><span data-stu-id="f8075-251">If someone specifies both `-Force` and `-WhatIf`, then `-WhatIf` needs to take priority.</span></span> <span data-ttu-id="f8075-252">При таком подходе обработка `-WhatIf` сохраняется, так как `ShouldProcess` выполняется всегда.</span><span class="sxs-lookup"><span data-stu-id="f8075-252">This approach preserves `-WhatIf` processing because `ShouldProcess` always gets executed.</span></span>

<span data-ttu-id="f8075-253">Не добавляйте проверку для значения `$Force` в инструкцию IF с методом `ShouldProcess`.</span><span class="sxs-lookup"><span data-stu-id="f8075-253">Do not add a check for the `$Force` value inside the if statement with the `ShouldProcess`.</span></span> <span data-ttu-id="f8075-254">Это неподходящий вариант для данного конкретного сценария, несмотря на то, что я продемонстрирую его в следующем разделе, посвященном `ShouldContinue`.</span><span class="sxs-lookup"><span data-stu-id="f8075-254">That is an anti-pattern for this specific scenario even though that's what I show you in the next section for `ShouldContinue`.</span></span>

### <a name="shouldcontinue--force"></a><span data-ttu-id="f8075-255">Параметр -Force метода ShouldContinue</span><span class="sxs-lookup"><span data-stu-id="f8075-255">ShouldContinue -Force</span></span>

<span data-ttu-id="f8075-256">Это правильный способ реализации `-Force` с `ShouldContinue`.</span><span class="sxs-lookup"><span data-stu-id="f8075-256">This is the correct way to implement `-Force` with `ShouldContinue`.</span></span>

```powershell
function Test-ShouldContinue {
    [CmdletBinding()]
    param(
        [Switch]$Force
    )

    if($Force -or $PSCmdlet.ShouldContinue('TARGET','OPERATION')){
        Write-Output "Some Action"
    }
}
```

<span data-ttu-id="f8075-257">Если поместить переменную `$Force` слева от оператора `-or`, она вычисляется первой.</span><span class="sxs-lookup"><span data-stu-id="f8075-257">By placing the `$Force` to the left of the `-or` operator, it gets evaluated first.</span></span> <span data-ttu-id="f8075-258">При такой записи выполнение инструкции `if` упрощается.</span><span class="sxs-lookup"><span data-stu-id="f8075-258">Writing it this way short circuits the execution of the `if` statement.</span></span> <span data-ttu-id="f8075-259">Если значение `$force` равно `$true`, `ShouldContinue` не выполняется.</span><span class="sxs-lookup"><span data-stu-id="f8075-259">If `$force` is `$true`, then the `ShouldContinue` is not executed.</span></span>

```powershell
PS> Test-ShouldContinue -Force
Some Action
```

<span data-ttu-id="f8075-260">В этом сценарии не нужно беспокоиться о параметрах `-Confirm` и `-WhatIf`, так как они не поддерживаются `ShouldContinue`.</span><span class="sxs-lookup"><span data-stu-id="f8075-260">We don't have to worry about `-Confirm` or `-WhatIf` in this scenario because they're not supported by `ShouldContinue`.</span></span> <span data-ttu-id="f8075-261">Именно поэтому с данным методом следует работать иначе, чем с `ShouldProcess`.</span><span class="sxs-lookup"><span data-stu-id="f8075-261">This is why it needs to be handled differently than `ShouldProcess`.</span></span>

## <a name="scope-issues"></a><span data-ttu-id="f8075-262">Проблемы с областью действия</span><span class="sxs-lookup"><span data-stu-id="f8075-262">Scope issues</span></span>

<span data-ttu-id="f8075-263">Предполагается, что при использовании параметров `-WhatIf` и `-Confirm` они применяются ко всем элементам внутри функции и всему, что она вызывает.</span><span class="sxs-lookup"><span data-stu-id="f8075-263">Using `-WhatIf` and `-Confirm` are supposed to apply to everything inside your functions and everything they call.</span></span> <span data-ttu-id="f8075-264">Для этого они задают значение `$true` для параметра `$WhatIfPreference` или значение `Low` для параметра `$ConfirmPreference` в локальной области функции.</span><span class="sxs-lookup"><span data-stu-id="f8075-264">They do this by setting `$WhatIfPreference` to `$true` or setting `$ConfirmPreference` to `Low` in the local scope of the function.</span></span> <span data-ttu-id="f8075-265">При вызове другой функции эти значения используются для вызова метода `ShouldProcess`.</span><span class="sxs-lookup"><span data-stu-id="f8075-265">When you call another function, calls to `ShouldProcess` use those values.</span></span>

<span data-ttu-id="f8075-266">Фактически в большинстве случаев такой подход работает надлежащим образом.</span><span class="sxs-lookup"><span data-stu-id="f8075-266">This actually works correctly most of the time.</span></span> <span data-ttu-id="f8075-267">Каждый раз, когда вы вызываете встроенный командлет или функцию в той же области, все работает так, как нужно.</span><span class="sxs-lookup"><span data-stu-id="f8075-267">Anytime you call built-in cmdlet or a function in your same scope, it works.</span></span> <span data-ttu-id="f8075-268">Этот подход также работает при вызове скрипта или функции в модуле скрипта из консоли.</span><span class="sxs-lookup"><span data-stu-id="f8075-268">It also works when you call a script or a function in a script module from the console.</span></span>

<span data-ttu-id="f8075-269">Однако есть одна особая ситуация, когда он не срабатывает. Возникает она, когда скрипт или модуль скрипта вызывает функцию в другом модуле скрипта.</span><span class="sxs-lookup"><span data-stu-id="f8075-269">The one specific place where it doesn't work is when a script or a script module calls a function in another script module.</span></span> <span data-ttu-id="f8075-270">Может показаться, что это не такая уж проблема, однако следует отметить, что большинство модулей, создаваемых в коллекции PSGallery или извлекаемых из нее, являются модулями скриптов.</span><span class="sxs-lookup"><span data-stu-id="f8075-270">This may not sound like a big problem, but most of the modules you create or pull from the PSGallery are script modules.</span></span>

<span data-ttu-id="f8075-271">Основная проблема заключается в том, что модули скриптов не наследуют значения `$WhatIfPreference` или `$ConfirmPreference` (и некоторых других) при вызове из функций в других модулях скриптов.</span><span class="sxs-lookup"><span data-stu-id="f8075-271">The core issue is that script modules do not inherit the values for `$WhatIfPreference` or `$ConfirmPreference` (and several others) when called from functions in other script modules.</span></span>

<span data-ttu-id="f8075-272">Чтобы подвести итоги, сформулируем общее правило: данный подход работает правильно для двоичных модулей, но при работе и с модулями скриптов полагаться на него не следует.</span><span class="sxs-lookup"><span data-stu-id="f8075-272">The best way to summarize this as a general rule is that this works correctly for binary modules and never trust it to work for script modules.</span></span> <span data-ttu-id="f8075-273">Если вы не уверены, проверьте его работу или просто считайте, что он работает неправильно.</span><span class="sxs-lookup"><span data-stu-id="f8075-273">If you aren't sure, either test it or just assume it doesn't work correctly.</span></span>

<span data-ttu-id="f8075-274">Лично мне кажется, что это очень опасно, так как создает ситуацию, когда вы добавляете поддержку `-WhatIf` в несколько модулей, которые работают верно по отдельности, но при вызове друг из друга начинают функционировать неправильно.</span><span class="sxs-lookup"><span data-stu-id="f8075-274">I personally feel this is very dangerous because it creates scenarios where you add `-WhatIf` support to multiple modules that work correctly in isolation, but fail to work correctly when they call each other.</span></span>

<span data-ttu-id="f8075-275">Сейчас ведутся работы по устранению этой проблемы согласно RFC на GitHub.</span><span class="sxs-lookup"><span data-stu-id="f8075-275">We do have a GitHub RFC working to get this issue fixed.</span></span> <span data-ttu-id="f8075-276">Дополнительные сведения см. в обсуждении [распространения настроек выполнения за пределы области действия модуля скрипта][RFC].</span><span class="sxs-lookup"><span data-stu-id="f8075-276">See [Propagate execution preferences beyond script module scope][RFC] for more details.</span></span>

## <a name="in-closing"></a><span data-ttu-id="f8075-277">Заключение</span><span class="sxs-lookup"><span data-stu-id="f8075-277">In closing</span></span>

<span data-ttu-id="f8075-278">Мне нужно узнать, как использовать `ShouldProcess` всякий раз, когда это необходимо.</span><span class="sxs-lookup"><span data-stu-id="f8075-278">I have to look up how to use `ShouldProcess` every time I need to use it.</span></span> <span data-ttu-id="f8075-279">Мне пришлось потратить много времени, чтобы научиться отличать `ShouldProcess` от `ShouldContinue`.</span><span class="sxs-lookup"><span data-stu-id="f8075-279">It took me a long time to distinguish `ShouldProcess` from `ShouldContinue`.</span></span> <span data-ttu-id="f8075-280">Мне почти всегда нужно искать данные о том, какие параметры следует использовать.</span><span class="sxs-lookup"><span data-stu-id="f8075-280">I almost always need to look up what parameters to use.</span></span> <span data-ttu-id="f8075-281">Поэтому не беспокойтесь, если вы все еще путаете их время от времени.</span><span class="sxs-lookup"><span data-stu-id="f8075-281">So don't worry if you still get confused from time to time.</span></span> <span data-ttu-id="f8075-282">Эта статья будет всегда у вас под рукой.</span><span class="sxs-lookup"><span data-stu-id="f8075-282">This article will be here when you need it.</span></span> <span data-ttu-id="f8075-283">Уверен, что я сам буду часто к ней обращаться.</span><span class="sxs-lookup"><span data-stu-id="f8075-283">I'm sure I will reference it often myself.</span></span>

<span data-ttu-id="f8075-284">Если вам понравилась эта публикация, поделитесь со мной своими идеями в Twitter по приведенной ниже ссылке.</span><span class="sxs-lookup"><span data-stu-id="f8075-284">If you liked this post, please share your thoughts with me on Twitter using the link below.</span></span> <span data-ttu-id="f8075-285">Мне всегда приятно общаться с людьми, которым были полезны мои материалы.</span><span class="sxs-lookup"><span data-stu-id="f8075-285">I always like hearing from people that get value from my content.</span></span>

<!-- link references -->
[Оригинал]: https://powershellexplained.com/2020-03-15-Powershell-shouldprocess-whatif-confirm-shouldcontinue-everything/
[original version]: https://powershellexplained.com/2020-03-15-Powershell-shouldprocess-whatif-confirm-shouldcontinue-everything/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[общих параметров]: /powershell/module/microsoft.powershell.core/about/about_commonparameters
[common parameters]: /powershell/module/microsoft.powershell.core/about/about_commonparameters
[все, что вы хотели узнать о хэш-таблицах]: everything-about-hashtable.md
[everything you wanted to know about hashtables]: everything-about-hashtable.md
[RFC]: https://github.com/PowerShell/PowerShell-RFC/pull/221#issuecomment-592954839
