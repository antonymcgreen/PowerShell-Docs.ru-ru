---
description: Описывает переменные, в которых хранятся сведения о состоянии для PowerShell. Эти переменные создаются и обслуживаются с помощью PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 08/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_automatic_variables?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Automatic_Variables
ms.openlocfilehash: 5ce9e61113da2c781f5774866e827663a7c7ced4
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232745"
---
# <a name="about-automatic-variables"></a><span data-ttu-id="6ff4a-105">Сведения об автоматических переменных</span><span class="sxs-lookup"><span data-stu-id="6ff4a-105">About Automatic Variables</span></span>

## <a name="short-description"></a><span data-ttu-id="6ff4a-106">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="6ff4a-106">Short description</span></span>

<span data-ttu-id="6ff4a-107">Описывает переменные, в которых хранятся сведения о состоянии для PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-107">Describes variables that store state information for PowerShell.</span></span> <span data-ttu-id="6ff4a-108">Эти переменные создаются и обслуживаются с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-108">These variables are created and maintained by PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="6ff4a-109">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="6ff4a-109">Long description</span></span>

<span data-ttu-id="6ff4a-110">По сути, эти переменные считаются доступны только для чтения.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-110">Conceptually, these variables are considered to be read-only.</span></span> <span data-ttu-id="6ff4a-111">Несмотря на то, что они **могут** быть записаны в, для обратной совместимости их **не следует** записывать в.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-111">Even though they **can** be written to, for backward compatibility they **should not** be written to.</span></span>

<span data-ttu-id="6ff4a-112">Ниже приведен список автоматических переменных в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-112">Here is a list of the automatic variables in PowerShell:</span></span>

### <a name=""></a>$$

<span data-ttu-id="6ff4a-113">Содержит последний токен в последней строке, полученной сеансом.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-113">Contains the last token in the last line received by the session.</span></span>

### <a name=""></a><span data-ttu-id="6ff4a-114">$?</span><span class="sxs-lookup"><span data-stu-id="6ff4a-114">$?</span></span>

<span data-ttu-id="6ff4a-115">Содержит состояние выполнения последней команды.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-115">Contains the execution status of the last command.</span></span> <span data-ttu-id="6ff4a-116">Он содержит **значение true** , если последняя команда выполнена успешно, и **значение false** в случае сбоя.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-116">It contains **True** if the last command succeeded and **False** if it failed.</span></span>

<span data-ttu-id="6ff4a-117">Для командлетов и расширенных функций, выполняемых на нескольких этапах конвейера, например в обоих `process` `end` блоках и, вызов `this.WriteError()` или `$PSCmdlet.WriteError()` соответственно в любой точке будет иметь значение `$?` **false** , как `this.ThrowTerminatingError()` и `$PSCmdlet.ThrowTerminatingError()` .</span><span class="sxs-lookup"><span data-stu-id="6ff4a-117">For cmdlets and advanced functions that are run at multiple stages in a pipeline, for example in both `process` and `end` blocks, calling `this.WriteError()` or `$PSCmdlet.WriteError()` respectively at any point will set `$?` to **False** , as will `this.ThrowTerminatingError()` and `$PSCmdlet.ThrowTerminatingError()`.</span></span>

<span data-ttu-id="6ff4a-118">`Write-Error`Командлет всегда задает `$?` **значение false** сразу после выполнения, но не имеет значения `$?` **false** для вызывающей ее функции:</span><span class="sxs-lookup"><span data-stu-id="6ff4a-118">The `Write-Error` cmdlet always sets `$?` to **False** immediately after it is executed, but will not set `$?` to **False** for a function calling it:</span></span>

```powershell
function Test-WriteError
{
    Write-Error "Bad"
    $? # $false
}

Test-WriteError
$? # $true
```

<span data-ttu-id="6ff4a-119">Для последней цели `$PSCmdlet.WriteError()` следует использовать вместо него.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-119">For the latter purpose, `$PSCmdlet.WriteError()` should be used instead.</span></span>

<span data-ttu-id="6ff4a-120">Для собственных команд (исполняемых файлов) `$?` имеет значение **true** , если `$LASTEXITCODE` равно 0, и значение **false** , если `$LASTEXITCODE` — любое другое значение.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-120">For native commands (executables), `$?` is set to **True** when `$LASTEXITCODE` is 0, and set to **False** when `$LASTEXITCODE` is any other value.</span></span>

> [!NOTE]
> <span data-ttu-id="6ff4a-121">До тех пор пока PowerShell 7, содержащий оператор в круглых скобках `(...)` , синтаксисе части выражения `$(...)` или выражении массива `@(...)` , всегда сбрасывается `$?` в **значение true** , чтобы `(Write-Error)` Показать `$?` **значение true**.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-121">Until PowerShell 7, containing a statement within parentheses `(...)`, subexpression syntax `$(...)` or array expression `@(...)` always reset `$?` to **True** , so that `(Write-Error)` shows `$?` as **True**.</span></span>
> <span data-ttu-id="6ff4a-122">Это было изменено в PowerShell 7, поэтому `$?` всегда будет отражать фактическое успешное выполнение последней команды в этих выражениях.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-122">This has been changed in PowerShell 7, so that `$?` will always reflect the actual success of the last command run in these expressions.</span></span>

### <a name=""></a>$^

<span data-ttu-id="6ff4a-123">Содержит первый маркер в последней строке, полученной сеансом.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-123">Contains the first token in the last line received by the session.</span></span>

### <a name="_"></a><span data-ttu-id="6ff4a-124">$_</span><span class="sxs-lookup"><span data-stu-id="6ff4a-124">$_</span></span>

<span data-ttu-id="6ff4a-125">Эквивалентно `$PSItem`.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-125">Same as `$PSItem`.</span></span> <span data-ttu-id="6ff4a-126">Содержит текущий объект в объекте конвейера.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-126">Contains the current object in the pipeline object.</span></span> <span data-ttu-id="6ff4a-127">Эту переменную можно использовать в командах, выполняющих действия с каждым объектом или на выбранных объектах в конвейере.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-127">You can use this variable in commands that perform an action on every object or on selected objects in a pipeline.</span></span>

### <a name="args"></a><span data-ttu-id="6ff4a-128">$args</span><span class="sxs-lookup"><span data-stu-id="6ff4a-128">$args</span></span>

<span data-ttu-id="6ff4a-129">Содержит массив значений для необъявленных параметров, которые передаются в функцию, скрипт или блок скрипта.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-129">Contains an array of values for undeclared parameters that are passed to a function, script, or script block.</span></span> <span data-ttu-id="6ff4a-130">При создании функции можно объявить параметры с помощью `param` ключевого слова или путем добавления разделенного запятыми списка параметров в круглые скобки после имени функции.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-130">When you create a function, you can declare the parameters by using the `param` keyword or by adding a comma-separated list of parameters in parentheses after the function name.</span></span>

<span data-ttu-id="6ff4a-131">В действии события `$Args` переменная содержит объекты, представляющие аргументы события обрабатываемого события.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-131">In an event action, the `$Args` variable contains objects that represent the event arguments of the event that is being processed.</span></span> <span data-ttu-id="6ff4a-132">Эта переменная заполняется только в `Action` блоке команды регистрации события.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-132">This variable is populated only within the `Action` block of an event registration command.</span></span>
<span data-ttu-id="6ff4a-133">Значение этой переменной также можно найти в свойстве **саурцеаргс** объекта **PSEventArgs** , который `Get-Event` возвращает.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-133">The value of this variable can also be found in the **SourceArgs** property of the **PSEventArgs** object that `Get-Event` returns.</span></span>

### <a name="consolefilename"></a><span data-ttu-id="6ff4a-134">$ConsoleFileName</span><span class="sxs-lookup"><span data-stu-id="6ff4a-134">$ConsoleFileName</span></span>

<span data-ttu-id="6ff4a-135">Содержит путь к файлу консоли ( `.psc1` ), который использовался в последнее время в сеансе.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-135">Contains the path of the console file (`.psc1`) that was most recently used in the session.</span></span> <span data-ttu-id="6ff4a-136">Эта переменная заполняется при запуске PowerShell с параметром **PSConsoleFile** или при использовании `Export-Console` командлета для экспорта имен оснасток в файл консоли.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-136">This variable is populated when you start PowerShell with the **PSConsoleFile** parameter or when you use the `Export-Console` cmdlet to export snap-in names to a console file.</span></span>

<span data-ttu-id="6ff4a-137">При использовании `Export-Console` командлета без параметров он автоматически обновляет файл консоли, который использовался в последнее время в сеансе.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-137">When you use the `Export-Console` cmdlet without parameters, it automatically updates the console file that was most recently used in the session.</span></span> <span data-ttu-id="6ff4a-138">Эту автоматическую переменную можно использовать для определения того, какой файл будет обновлен.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-138">You can use this automatic variable to determine which file will be updated.</span></span>

### <a name="error"></a><span data-ttu-id="6ff4a-139">$Error</span><span class="sxs-lookup"><span data-stu-id="6ff4a-139">$Error</span></span>

<span data-ttu-id="6ff4a-140">Содержит массив объектов Error, которые представляют последние ошибки.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-140">Contains an array of error objects that represent the most recent errors.</span></span>
<span data-ttu-id="6ff4a-141">Самая последняя ошибка — первый объект Error в массиве `$Error[0]` .</span><span class="sxs-lookup"><span data-stu-id="6ff4a-141">The most recent error is the first error object in the array `$Error[0]`.</span></span>

<span data-ttu-id="6ff4a-142">Чтобы предотвратить добавление ошибки в `$Error` массив, используйте общий параметр **ErrorAction** со значением **Ignore**.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-142">To prevent an error from being added to the `$Error` array, use the **ErrorAction** common parameter with a value of **Ignore**.</span></span> <span data-ttu-id="6ff4a-143">См. сведения в разделе [about_CommonParameters](about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="6ff4a-143">For more information, see [about_CommonParameters](about_CommonParameters.md).</span></span>

### <a name="event"></a><span data-ttu-id="6ff4a-144">$Event</span><span class="sxs-lookup"><span data-stu-id="6ff4a-144">$Event</span></span>

<span data-ttu-id="6ff4a-145">Содержит объект **PSEventArgs** , представляющий обрабатываемое событие.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-145">Contains a **PSEventArgs** object that represents the event that is being processed.</span></span> <span data-ttu-id="6ff4a-146">Эта переменная заполняется только в `Action` блоке команды регистрации событий, например `Register-ObjectEvent` .</span><span class="sxs-lookup"><span data-stu-id="6ff4a-146">This variable is populated only within the `Action` block of an event registration command, such as `Register-ObjectEvent`.</span></span> <span data-ttu-id="6ff4a-147">Значением этой переменной является тот же объект, который `Get-Event` возвращает командлет.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-147">The value of this variable is the same object that the `Get-Event` cmdlet returns.</span></span> <span data-ttu-id="6ff4a-148">Таким образом, можно использовать свойства `Event` переменной, например `$Event.TimeGenerated` , в `Action` блоке скрипта.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-148">Therefore, you can use the properties of the `Event` variable, such as `$Event.TimeGenerated`, in an `Action` script block.</span></span>

### <a name="eventargs"></a><span data-ttu-id="6ff4a-149">$EventArgs</span><span class="sxs-lookup"><span data-stu-id="6ff4a-149">$EventArgs</span></span>

<span data-ttu-id="6ff4a-150">Содержит объект, представляющий первый аргумент события, производный от **EventArgs** обрабатываемого события.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-150">Contains an object that represents the first event argument that derives from **EventArgs** of the event that is being processed.</span></span> <span data-ttu-id="6ff4a-151">Эта переменная заполняется только в `Action` блоке команды регистрации события.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-151">This variable is populated only within the `Action` block of an event registration command.</span></span>
<span data-ttu-id="6ff4a-152">Значение этой переменной также можно найти в свойстве **саурцеевентаргс** объекта **PSEventArgs** , который `Get-Event` возвращает.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-152">The value of this variable can also be found in the **SourceEventArgs** property of the **PSEventArgs** object that `Get-Event` returns.</span></span>

### <a name="eventsubscriber"></a><span data-ttu-id="6ff4a-153">$EventSubscriber</span><span class="sxs-lookup"><span data-stu-id="6ff4a-153">$EventSubscriber</span></span>

<span data-ttu-id="6ff4a-154">Содержит объект **псевентсубскрибер** , представляющий подписчика на событие обрабатываемого события.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-154">Contains a **PSEventSubscriber** object that represents the event subscriber of the event that is being processed.</span></span> <span data-ttu-id="6ff4a-155">Эта переменная заполняется только в `Action` блоке команды регистрации события.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-155">This variable is populated only within the `Action` block of an event registration command.</span></span> <span data-ttu-id="6ff4a-156">Значением этой переменной является тот же объект, который `Get-EventSubscriber` возвращает командлет.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-156">The value of this variable is the same object that the `Get-EventSubscriber` cmdlet returns.</span></span>

### <a name="executioncontext"></a><span data-ttu-id="6ff4a-157">$ExecutionContext</span><span class="sxs-lookup"><span data-stu-id="6ff4a-157">$ExecutionContext</span></span>

<span data-ttu-id="6ff4a-158">Содержит объект **енгинеинтринсикс** , представляющий контекст выполнения узла PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-158">Contains an **EngineIntrinsics** object that represents the execution context of the PowerShell host.</span></span> <span data-ttu-id="6ff4a-159">Эту переменную можно использовать для поиска объектов выполнения, доступных для командлетов.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-159">You can use this variable to find the execution objects that are available to cmdlets.</span></span>

### <a name="false"></a><span data-ttu-id="6ff4a-160">$false</span><span class="sxs-lookup"><span data-stu-id="6ff4a-160">$false</span></span>

<span data-ttu-id="6ff4a-161">Содержит **значение false**.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-161">Contains **False**.</span></span> <span data-ttu-id="6ff4a-162">Эту переменную можно использовать для представления значения **false** в командах и скриптах вместо использования строки false.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-162">You can use this variable to represent **False** in commands and scripts instead of using the string "false".</span></span> <span data-ttu-id="6ff4a-163">Строка может интерпретироваться как **истинная** , если она преобразуется в непустую строку или не имеет нулевого целого числа.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-163">The string can be interpreted as **True** if it's converted to a non-empty string or to a non-zero integer.</span></span>

### <a name="foreach"></a><span data-ttu-id="6ff4a-164">$foreach</span><span class="sxs-lookup"><span data-stu-id="6ff4a-164">$foreach</span></span>

<span data-ttu-id="6ff4a-165">Содержит перечислитель (а не результирующие значения) цикла [foreach](about_ForEach.md) .</span><span class="sxs-lookup"><span data-stu-id="6ff4a-165">Contains the enumerator (not the resulting values) of a [ForEach](about_ForEach.md) loop.</span></span> <span data-ttu-id="6ff4a-166">`$ForEach`Переменная существует только во время `ForEach` выполнения цикла; она удаляется после завершения цикла.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-166">The `$ForEach` variable exists only while the `ForEach` loop is running; it's deleted after the loop is completed.</span></span>

<span data-ttu-id="6ff4a-167">Перечислители содержат свойства и методы, которые можно использовать для получения значений циклов и изменения текущей итерации цикла.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-167">Enumerators contain properties and methods you can use to retrieve loop values and change the current loop iteration.</span></span> <span data-ttu-id="6ff4a-168">Дополнительные сведения см. [в разделе Использование перечислителей](#using-enumerators).</span><span class="sxs-lookup"><span data-stu-id="6ff4a-168">For more information, see [Using Enumerators](#using-enumerators).</span></span>

### <a name="home"></a><span data-ttu-id="6ff4a-169">$HOME</span><span class="sxs-lookup"><span data-stu-id="6ff4a-169">$HOME</span></span>

<span data-ttu-id="6ff4a-170">Содержит полный путь к домашнему каталогу пользователя.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-170">Contains the full path of the user's home directory.</span></span> <span data-ttu-id="6ff4a-171">Эта переменная эквивалентна `"$env:homedrive$env:homepath"` переменным среды Windows, обычно `C:\Users\<UserName>` .</span><span class="sxs-lookup"><span data-stu-id="6ff4a-171">This variable is the equivalent of the `"$env:homedrive$env:homepath"` Windows environment variables, typically `C:\Users\<UserName>`.</span></span>

### <a name="host"></a><span data-ttu-id="6ff4a-172">$Host</span><span class="sxs-lookup"><span data-stu-id="6ff4a-172">$Host</span></span>

<span data-ttu-id="6ff4a-173">Содержит объект, представляющий текущее ведущее приложение для PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-173">Contains an object that represents the current host application for PowerShell.</span></span> <span data-ttu-id="6ff4a-174">Эту переменную можно использовать для представления текущего узла в командах или для отображения или изменения свойств узла, например `$Host.version` или `$Host.CurrentCulture` `$host.ui.rawui.setbackgroundcolor("Red")` .</span><span class="sxs-lookup"><span data-stu-id="6ff4a-174">You can use this variable to represent the current host in commands or to display or change the properties of the host, such as `$Host.version` or `$Host.CurrentCulture`, or `$host.ui.rawui.setbackgroundcolor("Red")`.</span></span>

### <a name="input"></a><span data-ttu-id="6ff4a-175">$input</span><span class="sxs-lookup"><span data-stu-id="6ff4a-175">$input</span></span>

<span data-ttu-id="6ff4a-176">Содержит перечислитель, перечисляющий все входные данные, передаваемые в функцию.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-176">Contains an enumerator that enumerates all input that is passed to a function.</span></span> <span data-ttu-id="6ff4a-177">`$input`Переменная доступна только для функций и блоков скриптов (которые являются неименованными функциями).</span><span class="sxs-lookup"><span data-stu-id="6ff4a-177">The `$input` variable is available only to functions and script blocks (which are unnamed functions).</span></span>

- <span data-ttu-id="6ff4a-178">В функции без `Begin` `Process` блока, или `End` `$input` переменная перечисляет коллекцию всех входных данных для функции.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-178">In a function without a `Begin`, `Process`, or `End` block, the `$input` variable enumerates the collection of all input to the function.</span></span>

- <span data-ttu-id="6ff4a-179">В `Begin` блоке `$input` переменная не содержит данных.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-179">In the `Begin` block, the `$input` variable contains no data.</span></span>

- <span data-ttu-id="6ff4a-180">В `Process` блоке `$input` переменная содержит объект, который в настоящее время находится в конвейере.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-180">In the `Process` block, the `$input` variable contains the object that is currently in the pipeline.</span></span>

- <span data-ttu-id="6ff4a-181">В `End` блоке `$input` переменная перечисляет коллекцию всех входных данных для функции.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-181">In the `End` block, the `$input` variable enumerates the collection of all input to the function.</span></span>

  > [!NOTE]
  > <span data-ttu-id="6ff4a-182">Нельзя использовать `$input` переменную внутри блока Process и End блока в одной и той же функции или блоке скрипта.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-182">You cannot use the `$input` variable inside both the Process block and the End block in the same function or script block.</span></span>

<span data-ttu-id="6ff4a-183">Поскольку `$input` является перечислителем, доступ к любому из его свойств приводит к тому, что он `$input` больше не будет доступен.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-183">Since `$input` is an enumerator, accessing any of it's properties causes `$input` to no longer be available.</span></span> <span data-ttu-id="6ff4a-184">`$input`Для повторного использования свойств можно сохранить в другой переменной `$input` .</span><span class="sxs-lookup"><span data-stu-id="6ff4a-184">You can store `$input` in another variable to reuse the `$input` properties.</span></span>

<span data-ttu-id="6ff4a-185">Перечислители содержат свойства и методы, которые можно использовать для получения значений циклов и изменения текущей итерации цикла.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-185">Enumerators contain properties and methods you can use to retrieve loop values and change the current loop iteration.</span></span> <span data-ttu-id="6ff4a-186">Дополнительные сведения см. [в разделе Использование перечислителей](#using-enumerators).</span><span class="sxs-lookup"><span data-stu-id="6ff4a-186">For more information, see [Using Enumerators](#using-enumerators).</span></span>

### <a name="iscoreclr"></a><span data-ttu-id="6ff4a-187">$IsCoreCLR</span><span class="sxs-lookup"><span data-stu-id="6ff4a-187">$IsCoreCLR</span></span>

<span data-ttu-id="6ff4a-188">Содержит значение `$True` , если текущий сеанс работает в среде выполнения .NET Core (CoreCLR).</span><span class="sxs-lookup"><span data-stu-id="6ff4a-188">Contains `$True` if the current session is running on the .NET Core Runtime (CoreCLR).</span></span> <span data-ttu-id="6ff4a-189">В противном случае содержит `$False` .</span><span class="sxs-lookup"><span data-stu-id="6ff4a-189">Otherwise contains `$False`.</span></span>

### <a name="islinux"></a><span data-ttu-id="6ff4a-190">$IsLinux</span><span class="sxs-lookup"><span data-stu-id="6ff4a-190">$IsLinux</span></span>

<span data-ttu-id="6ff4a-191">Содержит `$True` , если текущий сеанс работает в операционной системе Linux.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-191">Contains `$True` if the current session is running on a Linux operating system.</span></span>
<span data-ttu-id="6ff4a-192">В противном случае содержит `$False` .</span><span class="sxs-lookup"><span data-stu-id="6ff4a-192">Otherwise contains `$False`.</span></span>

### <a name="ismacos"></a><span data-ttu-id="6ff4a-193">$IsMacOS</span><span class="sxs-lookup"><span data-stu-id="6ff4a-193">$IsMacOS</span></span>

<span data-ttu-id="6ff4a-194">Содержит, `$True` Если текущий сеанс работает в операционной системе MacOS.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-194">Contains `$True` if the current session is running on a MacOS operating system.</span></span>
<span data-ttu-id="6ff4a-195">В противном случае содержит `$False` .</span><span class="sxs-lookup"><span data-stu-id="6ff4a-195">Otherwise contains `$False`.</span></span>

### <a name="iswindows"></a><span data-ttu-id="6ff4a-196">$IsWindows</span><span class="sxs-lookup"><span data-stu-id="6ff4a-196">$IsWindows</span></span>

<span data-ttu-id="6ff4a-197">Содержит `$TRUE` , если текущий сеанс работает в операционной системе Windows.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-197">Contains `$TRUE` if the current session is running on a Windows operating system.</span></span> <span data-ttu-id="6ff4a-198">В противном случае содержит `$FALSE` .</span><span class="sxs-lookup"><span data-stu-id="6ff4a-198">Otherwise contains `$FALSE`.</span></span>

### <a name="lastexitcode"></a><span data-ttu-id="6ff4a-199">$LastExitCode</span><span class="sxs-lookup"><span data-stu-id="6ff4a-199">$LastExitCode</span></span>

<span data-ttu-id="6ff4a-200">Содержит код выхода последней запущенной программы Windows.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-200">Contains the exit code of the last Windows-based program that was run.</span></span>

### <a name="matches"></a><span data-ttu-id="6ff4a-201">$Matches</span><span class="sxs-lookup"><span data-stu-id="6ff4a-201">$Matches</span></span>

<span data-ttu-id="6ff4a-202">`Matches`Переменная работает с `-match` `-notmatch` операторами и.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-202">The `Matches` variable works with the `-match` and `-notmatch` operators.</span></span>
<span data-ttu-id="6ff4a-203">Когда вы отправляете скалярные входные данные в `-match` `-notmatch` оператор OR и один из них обнаруживает совпадение, он возвращает логическое значение и заполняет `$Matches` автоматическую переменную хэш-таблицей всех совпадающих строковых значений.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-203">When you submit scalar input to the `-match` or `-notmatch` operator, and either one detects a match, they return a Boolean value and populate the `$Matches` automatic variable with a hash table of any string values that were matched.</span></span> <span data-ttu-id="6ff4a-204">`$Matches`Кроме того, хэш-таблица может быть заполнена с помощью захватов при использовании регулярных выражений с `-match` оператором.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-204">The `$Matches` hash table can also be populated with captures when you use regular expressions with the `-match` operator.</span></span>

<span data-ttu-id="6ff4a-205">Дополнительные сведения об `-match` операторе см. в разделе [about_Comparison_Operators](about_comparison_operators.md).</span><span class="sxs-lookup"><span data-stu-id="6ff4a-205">For more information about the `-match` operator, see [about_Comparison_Operators](about_comparison_operators.md).</span></span> <span data-ttu-id="6ff4a-206">Дополнительные сведения о регулярных выражениях см. в разделе [about_Regular_Expressions](about_Regular_Expressions.md).</span><span class="sxs-lookup"><span data-stu-id="6ff4a-206">For more information on regular expressions, see [about_Regular_Expressions](about_Regular_Expressions.md).</span></span>

### <a name="myinvocation"></a><span data-ttu-id="6ff4a-207">$MyInvocation</span><span class="sxs-lookup"><span data-stu-id="6ff4a-207">$MyInvocation</span></span>

<span data-ttu-id="6ff4a-208">Содержит сведения о текущей команде, такие как имя, параметры, значения параметров и сведения о том, как команда была запущена, вызвана или вызвана, например имя скрипта, вызвавшего текущую команду.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-208">Contains information about the current command, such as the name, parameters, parameter values, and information about how the command was started, called, or invoked, such as the name of the script that called the current command.</span></span>

<span data-ttu-id="6ff4a-209">`$MyInvocation` заполняется только для скриптов, функций и блоков скриптов.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-209">`$MyInvocation` is populated only for scripts, function, and script blocks.</span></span> <span data-ttu-id="6ff4a-210">Можно использовать сведения в объекте **System. Management. Automation. инвокатионинфо** , которые `$MyInvocation` возвращают в текущем скрипте, например путь и имя файла скрипта ( `$MyInvocation.MyCommand.Path` ) или имя функции ( `$MyInvocation.MyCommand.Name` ) для определения текущей команды.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-210">You can use the information in the **System.Management.Automation.InvocationInfo** object that `$MyInvocation` returns in the current script, such as the path and file name of the script (`$MyInvocation.MyCommand.Path`) or the name of a function (`$MyInvocation.MyCommand.Name`) to identify the current command.</span></span> <span data-ttu-id="6ff4a-211">Это особенно полезно для поиска имени текущего скрипта.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-211">This is particularly useful for finding the name of the current script.</span></span>

<span data-ttu-id="6ff4a-212">Начиная с PowerShell 3,0, `MyInvocation` содержит следующие новые свойства.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-212">Beginning in PowerShell 3.0, `MyInvocation` has the following new properties.</span></span>

| <span data-ttu-id="6ff4a-213">Свойство</span><span class="sxs-lookup"><span data-stu-id="6ff4a-213">Property</span></span>      | <span data-ttu-id="6ff4a-214">Описание</span><span class="sxs-lookup"><span data-stu-id="6ff4a-214">Description</span></span>                                         |
| ------------- | --------------------------------------------------- |
| <span data-ttu-id="6ff4a-215">**PSScriptRoot**</span><span class="sxs-lookup"><span data-stu-id="6ff4a-215">**PSScriptRoot**</span></span>  | <span data-ttu-id="6ff4a-216">Содержит полный путь к скрипту, который вызывается</span><span class="sxs-lookup"><span data-stu-id="6ff4a-216">Contains the full path to the script that invoked</span></span>   |
|               | <span data-ttu-id="6ff4a-217">Текущая команда.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-217">the current command.</span></span> <span data-ttu-id="6ff4a-218">Значение этого свойства равно</span><span class="sxs-lookup"><span data-stu-id="6ff4a-218">The value of this property is</span></span>  |
|               | <span data-ttu-id="6ff4a-219">заполняется только в том случае, если вызывающий объект является сценарием.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-219">populated only when the caller is a script.</span></span>         |
| <span data-ttu-id="6ff4a-220">**пскоммандпас**</span><span class="sxs-lookup"><span data-stu-id="6ff4a-220">**PSCommandPath**</span></span> | <span data-ttu-id="6ff4a-221">Содержит полный путь и имя файла скрипта</span><span class="sxs-lookup"><span data-stu-id="6ff4a-221">Contains the full path and file name of the script</span></span>  |
|               | <span data-ttu-id="6ff4a-222">, вызвавший текущую команду.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-222">that invoked the current command.</span></span> <span data-ttu-id="6ff4a-223">Значение этого</span><span class="sxs-lookup"><span data-stu-id="6ff4a-223">The value of this</span></span> |
|               | <span data-ttu-id="6ff4a-224">заполняется только в том случае, если вызывающий объект является</span><span class="sxs-lookup"><span data-stu-id="6ff4a-224">property is populated only when the caller is a</span></span>     |
|               | <span data-ttu-id="6ff4a-225">.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-225">script.</span></span>                                             |

<span data-ttu-id="6ff4a-226">В отличие от `$PSScriptRoot` `$PSCommandPath` автоматических переменных, свойства **PSScriptRoot** и **пскоммандпас** `$MyInvocation` автоматических переменных содержат сведения о вызывающем элементе или вызове скрипта, а не текущем скрипте.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-226">Unlike the `$PSScriptRoot` and `$PSCommandPath` automatic variables, the **PSScriptRoot** and **PSCommandPath** properties of the `$MyInvocation` automatic variable contain information about the invoker or calling script, not the current script.</span></span>

### <a name="nestedpromptlevel"></a><span data-ttu-id="6ff4a-227">$NestedPromptLevel</span><span class="sxs-lookup"><span data-stu-id="6ff4a-227">$NestedPromptLevel</span></span>

<span data-ttu-id="6ff4a-228">Содержит текущий уровень запросов.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-228">Contains the current prompt level.</span></span> <span data-ttu-id="6ff4a-229">Значение 0 указывает на исходный уровень запроса.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-229">A value of 0 indicates the original prompt level.</span></span> <span data-ttu-id="6ff4a-230">Значение увеличивается при вводе вложенного уровня и уменьшается при его выходе.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-230">The value is incremented when you enter a nested level and decremented when you exit it.</span></span>

<span data-ttu-id="6ff4a-231">Например, при использовании метода PowerShell представляет собой вложенную командную строку `$Host.EnterNestedPrompt` .</span><span class="sxs-lookup"><span data-stu-id="6ff4a-231">For example, PowerShell presents a nested command prompt when you use the `$Host.EnterNestedPrompt` method.</span></span> <span data-ttu-id="6ff4a-232">PowerShell также предоставляет вложенную командную строку при достижении точки останова в отладчике PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-232">PowerShell also presents a nested command prompt when you reach a breakpoint in the PowerShell debugger.</span></span>

<span data-ttu-id="6ff4a-233">При вводе вложенного запроса PowerShell приостанавливает текущую команду, сохраняет контекст выполнения и увеличивает значение `$NestedPromptLevel` переменной.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-233">When you enter a nested prompt, PowerShell pauses the current command, saves the execution context, and increments the value of the `$NestedPromptLevel` variable.</span></span> <span data-ttu-id="6ff4a-234">Чтобы создать дополнительные вложенные командные подсказки (до 128) или вернуться к исходной командной строке, выполните команду или введите `exit` .</span><span class="sxs-lookup"><span data-stu-id="6ff4a-234">To create additional nested command prompts (up to 128 levels) or to return to the original command prompt, complete the command, or type `exit`.</span></span>

<span data-ttu-id="6ff4a-235">`$NestedPromptLevel`Переменная помогает контролировать уровень запросов.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-235">The `$NestedPromptLevel` variable helps you track the prompt level.</span></span> <span data-ttu-id="6ff4a-236">Можно создать альтернативную командную строку PowerShell, которая включает это значение, чтобы она всегда была видимой.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-236">You can create an alternative PowerShell command prompt that includes this value so that it's always visible.</span></span>

### <a name="null"></a><span data-ttu-id="6ff4a-237">$null</span><span class="sxs-lookup"><span data-stu-id="6ff4a-237">$null</span></span>

<span data-ttu-id="6ff4a-238">`$null` — Это автоматическая переменная, которая содержит значение **null** или пустую переменную.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-238">`$null` is an automatic variable that contains a **null** or empty value.</span></span> <span data-ttu-id="6ff4a-239">Эту переменную можно использовать для представления отсутствующего или неопределенного значения в командах и скриптах.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-239">You can use this variable to represent an absent or undefined value in commands and scripts.</span></span>

<span data-ttu-id="6ff4a-240">PowerShell обрабатывает `$null` как объект со значением, то есть как явный заполнитель, поэтому можно использовать `$null` для представления пустого значения в ряде значений.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-240">PowerShell treats `$null` as an object with a value, that is, as an explicit placeholder, so you can use `$null` to represent an empty value in a series of values.</span></span>

<span data-ttu-id="6ff4a-241">Например, если `$null` включен в коллекцию, то он считается одним из объектов.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-241">For example, when `$null` is included in a collection, it's counted as one of the objects.</span></span>

```powershell
$a = "one", $null, "three"
$a.count
```

```Output
3
```

<span data-ttu-id="6ff4a-242">При `$null` передаче переменной в `ForEach-Object` командлет создается значение для `$null` , точно так же, как и для других объектов.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-242">If you pipe the `$null` variable to the `ForEach-Object` cmdlet, it generates a value for `$null`, just as it does for the other objects</span></span>

```powershell
"one", $null, "three" | ForEach-Object { "Hello " + $_}
```

```Output
Hello one
Hello
Hello three
```

<span data-ttu-id="6ff4a-243">В результате нельзя использовать, `$null` чтобы **не указывать значение параметра**.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-243">As a result, you can't use `$null` to mean **no parameter value**.</span></span> <span data-ttu-id="6ff4a-244">Значение параметра `$null` переопределяет значение параметра по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-244">A parameter value of `$null` overrides the default parameter value.</span></span>

<span data-ttu-id="6ff4a-245">Однако, поскольку PowerShell обрабатывает `$null` переменную как заполнитель, ее можно использовать в сценариях, подобных следующим, что не будет работать, если `$null` они были пропущены.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-245">However, because PowerShell treats the `$null` variable as a placeholder, you can use it in scripts like the following one, which wouldn't work if `$null` were ignored.</span></span>

```powershell
$calendar = @($null, $null, "Meeting", $null, $null, "Team Lunch", $null)
$days = "Sunday","Monday","Tuesday","Wednesday","Thursday",
        "Friday","Saturday"
$currentDay = 0
foreach($day in $calendar)
{
    if($day -ne $null)
    {
        "Appointment on $($days[$currentDay]): $day"
    }

    $currentDay++
}
```

```Output
Appointment on Tuesday: Meeting
Appointment on Friday: Team lunch
```

### <a name="pid"></a><span data-ttu-id="6ff4a-246">$PID</span><span class="sxs-lookup"><span data-stu-id="6ff4a-246">$PID</span></span>

<span data-ttu-id="6ff4a-247">Содержит идентификатор процесса (PID) процесса, в котором размещается текущий сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-247">Contains the process identifier (PID) of the process that is hosting the current PowerShell session.</span></span>

### <a name="profile"></a><span data-ttu-id="6ff4a-248">$PROFILE</span><span class="sxs-lookup"><span data-stu-id="6ff4a-248">$PROFILE</span></span>

<span data-ttu-id="6ff4a-249">Содержит полный путь к профилю PowerShell для текущего пользователя и текущего ведущего приложения.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-249">Contains the full path of the PowerShell profile for the current user and the current host application.</span></span> <span data-ttu-id="6ff4a-250">Эту переменную можно использовать для представления профиля в командах.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-250">You can use this variable to represent the profile in commands.</span></span> <span data-ttu-id="6ff4a-251">Например, вы можете использовать его в команде, чтобы определить, был ли создан профиль:</span><span class="sxs-lookup"><span data-stu-id="6ff4a-251">For example, you can use it in a command to determine whether a profile has been created:</span></span>

```powershell
Test-Path $PROFILE
```

<span data-ttu-id="6ff4a-252">Вы также можете использовать его в команде для создания профиля:</span><span class="sxs-lookup"><span data-stu-id="6ff4a-252">Or, you can use it in a command to create a profile:</span></span>

```powershell
New-Item -ItemType file -Path $PROFILE -Force
```

<span data-ttu-id="6ff4a-253">Его можно использовать в команде, чтобы открыть профиль в **notepad.exe** :</span><span class="sxs-lookup"><span data-stu-id="6ff4a-253">You can use it in a command to open the profile in **notepad.exe** :</span></span>

```powershell
notepad.exe $PROFILE
```

### <a name="psboundparameters"></a><span data-ttu-id="6ff4a-254">$PSBoundParameters</span><span class="sxs-lookup"><span data-stu-id="6ff4a-254">$PSBoundParameters</span></span>

<span data-ttu-id="6ff4a-255">Содержит словарь параметров, которые передаются в скрипт или функцию, а также их текущие значения.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-255">Contains a dictionary of the parameters that are passed to a script or function and their current values.</span></span> <span data-ttu-id="6ff4a-256">Эта переменная имеет значение только в области, где объявляются параметры, например скрипт или функция.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-256">This variable has a value only in a scope where parameters are declared, such as a script or function.</span></span> <span data-ttu-id="6ff4a-257">Его можно использовать для вывода или изменения текущих значений параметров, а также для передачи значений параметров другому сценарию или функции.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-257">You can use it to display or change the current values of parameters or to pass parameter values to another script or function.</span></span>

<span data-ttu-id="6ff4a-258">В этом примере функция **Test2** передает в `$PSBoundParameters` функцию **test1** .</span><span class="sxs-lookup"><span data-stu-id="6ff4a-258">In this example, the **Test2** function passes the `$PSBoundParameters` to the **Test1** function.</span></span> <span data-ttu-id="6ff4a-259">`$PSBoundParameters`Отображаются в формате **ключа** и **значения**.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-259">The `$PSBoundParameters` are displayed in the format of **Key** and **Value**.</span></span>

```powershell
function Test1 {
   param($a, $b)

   # Display the parameters in dictionary format.
   $PSBoundParameters
}

function Test2 {
   param($a, $b)

   # Run the Test1 function with $a and $b.
   Test1 @PSBoundParameters
}
```

```powershell
Test2 -a Power -b Shell
```

```Output
Key   Value
---   -----
a     Power
b     Shell
```

### <a name="pscmdlet"></a><span data-ttu-id="6ff4a-260">$PSCmdlet</span><span class="sxs-lookup"><span data-stu-id="6ff4a-260">$PSCmdlet</span></span>

<span data-ttu-id="6ff4a-261">Содержит объект, представляющий выполняемый командлет или расширенную функцию.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-261">Contains an object that represents the cmdlet or advanced function that's being run.</span></span>

<span data-ttu-id="6ff4a-262">Можно использовать свойства и методы объекта в командлете или коде функции для реагирования на условия использования.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-262">You can use the properties and methods of the object in your cmdlet or function code to respond to the conditions of use.</span></span> <span data-ttu-id="6ff4a-263">Например, свойство **параметерсетнаме** содержит имя используемого набора параметров, а метод **ShouldProcess** динамически добавляет параметры **WhatIf** и **Confirm** в командлет.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-263">For example, the **ParameterSetName** property contains the name of the parameter set that's being used, and the **ShouldProcess** method adds the **WhatIf** and **Confirm** parameters to the cmdlet dynamically.</span></span>

<span data-ttu-id="6ff4a-264">Дополнительные сведения об `$PSCmdlet` автоматической переменной см. в разделе [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md) и [about_Functions_Advanced](about_Functions_Advanced.md).</span><span class="sxs-lookup"><span data-stu-id="6ff4a-264">For more information about the `$PSCmdlet` automatic variable, see [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md) and [about_Functions_Advanced](about_Functions_Advanced.md).</span></span>

### <a name="pscommandpath"></a><span data-ttu-id="6ff4a-265">$PSCommandPath</span><span class="sxs-lookup"><span data-stu-id="6ff4a-265">$PSCommandPath</span></span>

<span data-ttu-id="6ff4a-266">Содержит полный путь и имя файла скрипта, который выполняется.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-266">Contains the full path and file name of the script that's being run.</span></span> <span data-ttu-id="6ff4a-267">Эта переменная допустима во всех скриптах.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-267">This variable is valid in all scripts.</span></span>

### <a name="psculture"></a><span data-ttu-id="6ff4a-268">$PSCulture</span><span class="sxs-lookup"><span data-stu-id="6ff4a-268">$PSCulture</span></span>

<span data-ttu-id="6ff4a-269">Начиная с PowerShell 7, `$PSCulture` отражает язык и региональные параметры текущего пространства выполнения PowerShell (сеанса).</span><span class="sxs-lookup"><span data-stu-id="6ff4a-269">Beginning in PowerShell 7, `$PSCulture` reflects the culture of the current PowerShell runspace (session).</span></span> <span data-ttu-id="6ff4a-270">Если язык и региональные параметры изменены в пространстве выполнения PowerShell, `$PSCulture` значение этого пространства выполнения обновляется.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-270">If the culture is changed in a PowerShell runspace, the `$PSCulture` value for that runspace is updated.</span></span>

<span data-ttu-id="6ff4a-271">Язык и региональные параметры определяют формат отображаемых элементов, таких как числа, денежные единицы и даты, и хранятся в объекте **System. Globalization. CultureInfo** .</span><span class="sxs-lookup"><span data-stu-id="6ff4a-271">The culture determines the display format of items such as numbers, currency, and dates, and is stored in a **System.Globalization.CultureInfo** object.</span></span> <span data-ttu-id="6ff4a-272">Используется `Get-Culture` для вывода языка и региональных параметров компьютера.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-272">Use `Get-Culture` to display the computer's culture.</span></span> <span data-ttu-id="6ff4a-273">`$PSCulture` содержит значение свойства **Name** .</span><span class="sxs-lookup"><span data-stu-id="6ff4a-273">`$PSCulture` contains the **Name** property's value.</span></span>

### <a name="psdebugcontext"></a><span data-ttu-id="6ff4a-274">$PSDebugContext</span><span class="sxs-lookup"><span data-stu-id="6ff4a-274">$PSDebugContext</span></span>

<span data-ttu-id="6ff4a-275">Во время отладки эта переменная содержит сведения о среде отладки.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-275">While debugging, this variable contains information about the debugging environment.</span></span> <span data-ttu-id="6ff4a-276">В противном случае он содержит значение **null** .</span><span class="sxs-lookup"><span data-stu-id="6ff4a-276">Otherwise, it contains a **null** value.</span></span> <span data-ttu-id="6ff4a-277">В результате его можно использовать, чтобы указать, имеет ли отладчик элемент управления.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-277">As a result, you can use it to indicate whether the debugger has control.</span></span> <span data-ttu-id="6ff4a-278">При заполнении он содержит объект **псдебугконтекст** с **точками останова** и свойствами **инвокатионинфо** .</span><span class="sxs-lookup"><span data-stu-id="6ff4a-278">When populated, it contains a **PsDebugContext** object that has **Breakpoints** and **InvocationInfo** properties.</span></span> <span data-ttu-id="6ff4a-279">Свойство **инвокатионинфо** имеет несколько полезных свойств, включая свойство **Location** .</span><span class="sxs-lookup"><span data-stu-id="6ff4a-279">The **InvocationInfo** property has several useful properties, including the **Location** property.</span></span> <span data-ttu-id="6ff4a-280">Свойство **Location** указывает путь отлаживаемого скрипта.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-280">The **Location** property indicates the path of the script that is being debugged.</span></span>

### <a name="pshome"></a><span data-ttu-id="6ff4a-281">$PSHOME</span><span class="sxs-lookup"><span data-stu-id="6ff4a-281">$PSHOME</span></span>

<span data-ttu-id="6ff4a-282">Содержит полный путь к каталогу установки PowerShell (обычно `$env:windir\System32\PowerShell\v1.0` в системах Windows).</span><span class="sxs-lookup"><span data-stu-id="6ff4a-282">Contains the full path of the installation directory for PowerShell, typically, `$env:windir\System32\PowerShell\v1.0` in Windows systems.</span></span> <span data-ttu-id="6ff4a-283">Эту переменную можно использовать в путях файлов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-283">You can use this variable in the paths of PowerShell files.</span></span> <span data-ttu-id="6ff4a-284">Например, следующая команда выполняет поиск в основных разделах справки по **переменной** Word:</span><span class="sxs-lookup"><span data-stu-id="6ff4a-284">For example, the following command searches the conceptual Help topics for the word **variable** :</span></span>

```powershell
Select-String -Pattern Variable -Path $pshome\*.txt
```

### <a name="psitem"></a><span data-ttu-id="6ff4a-285">$PSItem</span><span class="sxs-lookup"><span data-stu-id="6ff4a-285">$PSItem</span></span>

<span data-ttu-id="6ff4a-286">Эквивалентно `$_`.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-286">Same as `$_`.</span></span> <span data-ttu-id="6ff4a-287">Содержит текущий объект в объекте конвейера.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-287">Contains the current object in the pipeline object.</span></span> <span data-ttu-id="6ff4a-288">Эту переменную можно использовать в командах, выполняющих действия с каждым объектом или на выбранных объектах в конвейере.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-288">You can use this variable in commands that perform an action on every object or on selected objects in a pipeline.</span></span>

### <a name="psscriptroot"></a><span data-ttu-id="6ff4a-289">$PSScriptRoot</span><span class="sxs-lookup"><span data-stu-id="6ff4a-289">$PSScriptRoot</span></span>

<span data-ttu-id="6ff4a-290">Содержит каталог, из которого выполняется скрипт.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-290">Contains the directory from which a script is being run.</span></span>

<span data-ttu-id="6ff4a-291">В PowerShell 2,0 эта переменная допустима только в модулях скриптов ( `.psm1` ).</span><span class="sxs-lookup"><span data-stu-id="6ff4a-291">In PowerShell 2.0, this variable is valid only in script modules (`.psm1`).</span></span>
<span data-ttu-id="6ff4a-292">Начиная с PowerShell 3,0, он действителен во всех скриптах.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-292">Beginning in PowerShell 3.0, it's valid in all scripts.</span></span>

### <a name="pssenderinfo"></a><span data-ttu-id="6ff4a-293">$PSSenderInfo</span><span class="sxs-lookup"><span data-stu-id="6ff4a-293">$PSSenderInfo</span></span>

<span data-ttu-id="6ff4a-294">Содержит сведения о пользователе, запустившего PSSession, включая удостоверение пользователя и часовой пояс исходного компьютера.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-294">Contains information about the user who started the PSSession, including the user identity and the time zone of the originating computer.</span></span> <span data-ttu-id="6ff4a-295">Эта переменная доступна только в PSSession.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-295">This variable is available only in PSSessions.</span></span>

<span data-ttu-id="6ff4a-296">`$PSSenderInfo`Переменная включает настраиваемое пользователем свойство **аппликатионаргументс** , которое по умолчанию содержит только `$PSVersionTable` из исходного сеанса.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-296">The `$PSSenderInfo` variable includes a user-configurable property, **ApplicationArguments** , that by default, contains only the `$PSVersionTable` from the originating session.</span></span> <span data-ttu-id="6ff4a-297">Чтобы добавить данные в свойство **аппликатионаргументс** , используйте параметр **аппликатионаргументс** `New-PSSessionOption` командлета.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-297">To add data to the **ApplicationArguments** property, use the **ApplicationArguments** parameter of the `New-PSSessionOption` cmdlet.</span></span>

### <a name="psuiculture"></a><span data-ttu-id="6ff4a-298">$PSUICulture</span><span class="sxs-lookup"><span data-stu-id="6ff4a-298">$PSUICulture</span></span>

<span data-ttu-id="6ff4a-299">Содержит имя языка и региональных параметров пользовательского интерфейса, используемого в данный момент в операционной системе.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-299">Contains the name of the user interface (UI) culture that's currently in use in the operating system.</span></span> <span data-ttu-id="6ff4a-300">Язык и региональные параметры пользовательского интерфейса определяют, какие строки текста используются для элементов пользовательского интерфейса, например меню и сообщений.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-300">The UI culture determines which text strings are used for user interface elements, such as menus and messages.</span></span> <span data-ttu-id="6ff4a-301">Это значение свойства **System.Globalization.CultureInfo.CurrentUICulture.Name** системы.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-301">This is the value of the **System.Globalization.CultureInfo.CurrentUICulture.Name** property of the system.</span></span> <span data-ttu-id="6ff4a-302">Чтобы получить объект **System. Globalization. CultureInfo** для системы, используйте `Get-UICulture` командлет.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-302">To get the **System.Globalization.CultureInfo** object for the system, use the `Get-UICulture` cmdlet.</span></span>

### <a name="psversiontable"></a><span data-ttu-id="6ff4a-303">$PSVersionTable</span><span class="sxs-lookup"><span data-stu-id="6ff4a-303">$PSVersionTable</span></span>

<span data-ttu-id="6ff4a-304">Содержит хэш-таблицу только для чтения, в которой отображаются сведения о версии PowerShell, которая выполняется в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-304">Contains a read-only hash table that displays details about the version of PowerShell that is running in the current session.</span></span> <span data-ttu-id="6ff4a-305">Таблица содержит следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="6ff4a-305">The table includes the following items:</span></span>

| <span data-ttu-id="6ff4a-306">Свойство</span><span class="sxs-lookup"><span data-stu-id="6ff4a-306">Property</span></span>                  | <span data-ttu-id="6ff4a-307">Описание</span><span class="sxs-lookup"><span data-stu-id="6ff4a-307">Description</span></span>                                   |
| ------------------------- | --------------------------------------------- |
| <span data-ttu-id="6ff4a-308">**PSVersion**</span><span class="sxs-lookup"><span data-stu-id="6ff4a-308">**PSVersion**</span></span>             | <span data-ttu-id="6ff4a-309">Номер версии PowerShell</span><span class="sxs-lookup"><span data-stu-id="6ff4a-309">The PowerShell version number</span></span>                 |
| <span data-ttu-id="6ff4a-310">**PSEdition**</span><span class="sxs-lookup"><span data-stu-id="6ff4a-310">**PSEdition**</span></span>             | <span data-ttu-id="6ff4a-311">Это свойство имеет значение "Desktop" для</span><span class="sxs-lookup"><span data-stu-id="6ff4a-311">This property has the value of 'Desktop' for</span></span>  |
|                           | <span data-ttu-id="6ff4a-312">PowerShell 4 и ниже, а также PowerShell</span><span class="sxs-lookup"><span data-stu-id="6ff4a-312">PowerShell 4 and below as well as PowerShell</span></span>  |
|                           | <span data-ttu-id="6ff4a-313">5,1 в полнофункциональных выпусках Windows.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-313">5.1 on full-featured Windows editions.</span></span>        |
|                           | <span data-ttu-id="6ff4a-314">Это свойство имеет значение "Core" для</span><span class="sxs-lookup"><span data-stu-id="6ff4a-314">This property has the value of 'Core' for</span></span>     |
|                           | <span data-ttu-id="6ff4a-315">PowerShell 6 и более поздней версии, а также PowerShell</span><span class="sxs-lookup"><span data-stu-id="6ff4a-315">PowerShell 6 and above as well as PowerShell</span></span>  |
|                           | <span data-ttu-id="6ff4a-316">PowerShell 5,1 в выпусках с ограниченным объемом памяти</span><span class="sxs-lookup"><span data-stu-id="6ff4a-316">PowerShell 5.1 on reduced-footprint editions</span></span>  |
|                           | <span data-ttu-id="6ff4a-317">как и в Windows Nano Server или Windows IoT.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-317">like Windows Nano Server or Windows IoT.</span></span>      |
| <span data-ttu-id="6ff4a-318">**гиткоммитид**</span><span class="sxs-lookup"><span data-stu-id="6ff4a-318">**GitCommitId**</span></span>           | <span data-ttu-id="6ff4a-319">Идентификаторы фиксации исходных файлов, в GitHub</span><span class="sxs-lookup"><span data-stu-id="6ff4a-319">The commit Id of the source files, in GitHub,</span></span> |
| <span data-ttu-id="6ff4a-320">**ОС**</span><span class="sxs-lookup"><span data-stu-id="6ff4a-320">**OS**</span></span>                    | <span data-ttu-id="6ff4a-321">Описание операционной системы,</span><span class="sxs-lookup"><span data-stu-id="6ff4a-321">Description of the operating system that</span></span>      |
|                           | <span data-ttu-id="6ff4a-322">PowerShell работает в.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-322">PowerShell is running on.</span></span>                     |
| <span data-ttu-id="6ff4a-323">**Платформа**</span><span class="sxs-lookup"><span data-stu-id="6ff4a-323">**Platform**</span></span>              | <span data-ttu-id="6ff4a-324">Платформа, под которой работает операционная система</span><span class="sxs-lookup"><span data-stu-id="6ff4a-324">Platform that the operating system is running</span></span> |
|                           | <span data-ttu-id="6ff4a-325">в.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-325">on.</span></span> <span data-ttu-id="6ff4a-326">Значение в Linux и macOS — **UNIX**.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-326">The value on Linux and macOS is **Unix**.</span></span> |
|                           | <span data-ttu-id="6ff4a-327">См. разделы `$IsMacOs` и `$IsLinux`.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-327">See `$IsMacOs` and `$IsLinux`.</span></span>                |
| <span data-ttu-id="6ff4a-328">**пскомпатиблеверсионс**</span><span class="sxs-lookup"><span data-stu-id="6ff4a-328">**PSCompatibleVersions**</span></span>  | <span data-ttu-id="6ff4a-329">Совместимые версии PowerShell</span><span class="sxs-lookup"><span data-stu-id="6ff4a-329">Versions of PowerShell that are compatible</span></span>    |
|                           | <span data-ttu-id="6ff4a-330">с текущей версией</span><span class="sxs-lookup"><span data-stu-id="6ff4a-330">with the current version</span></span>                      |
| <span data-ttu-id="6ff4a-331">**псремотингпротоколверсион**</span><span class="sxs-lookup"><span data-stu-id="6ff4a-331">**PSRemotingProtocolVersion**</span></span> | <span data-ttu-id="6ff4a-332">Версия удаленного экземпляра PowerShell</span><span class="sxs-lookup"><span data-stu-id="6ff4a-332">The version of the PowerShell remote</span></span>      |
|                           | <span data-ttu-id="6ff4a-333">Протокол управления.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-333">management protocol.</span></span>                          |
| <span data-ttu-id="6ff4a-334">**сериализатионверсион**</span><span class="sxs-lookup"><span data-stu-id="6ff4a-334">**SerializationVersion**</span></span>  | <span data-ttu-id="6ff4a-335">Версия метода сериализации</span><span class="sxs-lookup"><span data-stu-id="6ff4a-335">The version of the serialization method</span></span>       |
| <span data-ttu-id="6ff4a-336">**всманстаккверсион**</span><span class="sxs-lookup"><span data-stu-id="6ff4a-336">**WSManStackVersion**</span></span>     | <span data-ttu-id="6ff4a-337">Номер версии стека WS-Management</span><span class="sxs-lookup"><span data-stu-id="6ff4a-337">The version number of the WS-Management stack</span></span> |

### <a name="pwd"></a><span data-ttu-id="6ff4a-338">$PWD</span><span class="sxs-lookup"><span data-stu-id="6ff4a-338">$PWD</span></span>

<span data-ttu-id="6ff4a-339">Содержит объект Path, представляющий полный путь к текущему каталогу.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-339">Contains a path object that represents the full path of the current directory.</span></span>

### <a name="sender"></a><span data-ttu-id="6ff4a-340">$Sender</span><span class="sxs-lookup"><span data-stu-id="6ff4a-340">$Sender</span></span>

<span data-ttu-id="6ff4a-341">Содержит объект, создавший это событие.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-341">Contains the object that generated this event.</span></span> <span data-ttu-id="6ff4a-342">Эта переменная заполняется только в блоке действия для команды регистрации события.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-342">This variable is populated only within the Action block of an event registration command.</span></span> <span data-ttu-id="6ff4a-343">Значение этой переменной также можно найти в свойстве sender объекта **PSEventArgs** , который `Get-Event` возвращает.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-343">The value of this variable can also be found in the Sender property of the **PSEventArgs** object that `Get-Event` returns.</span></span>

### <a name="shellid"></a><span data-ttu-id="6ff4a-344">$ShellId</span><span class="sxs-lookup"><span data-stu-id="6ff4a-344">$ShellId</span></span>

<span data-ttu-id="6ff4a-345">Содержит идентификатор текущей оболочки.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-345">Contains the identifier of the current shell.</span></span>

### <a name="stacktrace"></a><span data-ttu-id="6ff4a-346">$StackTrace</span><span class="sxs-lookup"><span data-stu-id="6ff4a-346">$StackTrace</span></span>

<span data-ttu-id="6ff4a-347">Содержит трассировку стека для последней ошибки.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-347">Contains a stack trace for the most recent error.</span></span>

### <a name="switch"></a><span data-ttu-id="6ff4a-348">$switch</span><span class="sxs-lookup"><span data-stu-id="6ff4a-348">$switch</span></span>

<span data-ttu-id="6ff4a-349">Содержит перечислитель, а не результирующие значения `Switch` инструкции.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-349">Contains the enumerator not the resulting values of a `Switch` statement.</span></span> <span data-ttu-id="6ff4a-350">`$switch`Переменная существует только во время выполнения `Switch` инструкции. она удаляется, когда `switch` выполнение инструкции завершается.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-350">The `$switch` variable exists only while the `Switch` statement is running; it's deleted when the `switch` statement completes execution.</span></span> <span data-ttu-id="6ff4a-351">Дополнительные сведения см. в разделе [about_Switch](about_Switch.md).</span><span class="sxs-lookup"><span data-stu-id="6ff4a-351">For more information, see [about_Switch](about_Switch.md).</span></span>

<span data-ttu-id="6ff4a-352">Перечислители содержат свойства и методы, которые можно использовать для получения значений циклов и изменения текущей итерации цикла.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-352">Enumerators contain properties and methods you can use to retrieve loop values and change the current loop iteration.</span></span> <span data-ttu-id="6ff4a-353">Дополнительные сведения см. [в разделе Использование перечислителей](#using-enumerators).</span><span class="sxs-lookup"><span data-stu-id="6ff4a-353">For more information, see [Using Enumerators](#using-enumerators).</span></span>

### <a name="this"></a><span data-ttu-id="6ff4a-354">$this</span><span class="sxs-lookup"><span data-stu-id="6ff4a-354">$this</span></span>

<span data-ttu-id="6ff4a-355">В блоке скрипта, который определяет свойство скрипта или метод скрипта, `$this` переменная ссылается на объект, который расширяется.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-355">In a script block that defines a script property or script method, the `$this` variable refers to the object that is being extended.</span></span>

<span data-ttu-id="6ff4a-356">В пользовательском классе `$this` переменная ссылается на сам объект класса, который обеспечивает доступ к свойствам и методам, определенным в классе.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-356">In a custom class, the `$this` variable refers to the class object itself allowing access to properties and methods defined in the class.</span></span>

### <a name="true"></a><span data-ttu-id="6ff4a-357">$true</span><span class="sxs-lookup"><span data-stu-id="6ff4a-357">$true</span></span>

<span data-ttu-id="6ff4a-358">Содержит **значение true**.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-358">Contains **True**.</span></span> <span data-ttu-id="6ff4a-359">С помощью этой переменной можно представить **значение true** в командах и скриптах.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-359">You can use this variable to represent **True** in commands and scripts.</span></span>

## <a name="using-enumerators"></a><span data-ttu-id="6ff4a-360">Использование перечислителей</span><span class="sxs-lookup"><span data-stu-id="6ff4a-360">Using Enumerators</span></span>

<span data-ttu-id="6ff4a-361">`$input`Переменные, `$foreach` и `$switch` — это все перечислители, используемые для прохода по значениям, обрабатываемым содержащим его блоком кода.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-361">The `$input`, `$foreach`, and `$switch` variables are all enumerators used to iterate through the values processed by their containing code block.</span></span>

<span data-ttu-id="6ff4a-362">Перечислитель содержит свойства и методы, которые можно использовать для перебора или сброса итерации, а также для получения значений итерации.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-362">An enumerator contains properties and methods you can use to advance or reset iteration, or retrieve iteration values.</span></span> <span data-ttu-id="6ff4a-363">Непосредственное управление перечислителями не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-363">Directly manipulating enumerators isn't considered best practice.</span></span>

- <span data-ttu-id="6ff4a-364">В циклах управление потоком ключевые слова [break](about_Break.md) и [Continue](about_Continue.md) должны быть предпочтительными.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-364">Within loops, flow control keywords [break](about_Break.md) and [continue](about_Continue.md) should be preferred.</span></span>
- <span data-ttu-id="6ff4a-365">В функциях, принимающих входные данные конвейера, рекомендуется использовать параметры с атрибутами **валуефромпипелине** или **валуефромпипелинебипропертинаме** .</span><span class="sxs-lookup"><span data-stu-id="6ff4a-365">Within functions that accept pipeline input, it's best practice to use Parameters with the **ValueFromPipeline** or **ValueFromPipelineByPropertyName** attributes.</span></span>

  <span data-ttu-id="6ff4a-366">Дополнительные сведения см. в разделе [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span><span class="sxs-lookup"><span data-stu-id="6ff4a-366">For more information, see [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span></span>

### <a name="movenext"></a><span data-ttu-id="6ff4a-367">MoveNext</span><span class="sxs-lookup"><span data-stu-id="6ff4a-367">MoveNext</span></span>

<span data-ttu-id="6ff4a-368">Метод [MoveNext](/dotnet/api/system.collections.ienumerator.movenext) перемещает перечислитель к следующему элементу коллекции.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-368">The [MoveNext](/dotnet/api/system.collections.ienumerator.movenext) method advances the enumerator to the next element of the collection.</span></span> <span data-ttu-id="6ff4a-369">**MoveNext** возвращает **значение true** , если перечислитель был успешно расширен, и **false** , если перечислитель прошел конец коллекции.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-369">**MoveNext** returns **True** if the enumerator was successfully advanced, **False** if the enumerator has passed the end of the collection.</span></span>

> [!NOTE]
> <span data-ttu-id="6ff4a-370">**Логическое** значение, возвращенное моим методом **MoveNext** , отправляется в поток вывода.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-370">The **Boolean** value returned my **MoveNext** is sent to the output stream.</span></span>
> <span data-ttu-id="6ff4a-371">Вы можете подавить вывод, применив его к `[void]` или передав его в [out-NULL](xref:Microsoft.PowerShell.Core.Out-Null).</span><span class="sxs-lookup"><span data-stu-id="6ff4a-371">You can suppress the output by typecasting it to `[void]` or piping it to [Out-Null](xref:Microsoft.PowerShell.Core.Out-Null).</span></span>
>
> ```powershell
> $input.MoveNext() | Out-Null
> ```
>
> ```powershell
> [void]$input.MoveNext()
> ```

### <a name="reset"></a><span data-ttu-id="6ff4a-372">Reset</span><span class="sxs-lookup"><span data-stu-id="6ff4a-372">Reset</span></span>

<span data-ttu-id="6ff4a-373">Метод [Reset](/dotnet/api/system.collections.ienumerator.reset) устанавливает перечислитель в исходное расположение, которое **предшествует** первому элементу в коллекции.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-373">The [Reset](/dotnet/api/system.collections.ienumerator.reset) method sets the enumerator to its initial position, which is **before** the first element in the collection.</span></span>

### <a name="current"></a><span data-ttu-id="6ff4a-374">Текущий</span><span class="sxs-lookup"><span data-stu-id="6ff4a-374">Current</span></span>

<span data-ttu-id="6ff4a-375">[Текущее](/dotnet/api/system.collections.ienumerator.current) свойство получает элемент в коллекции или конвейере в текущей позиции перечислителя.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-375">The [Current](/dotnet/api/system.collections.ienumerator.current) property gets the element in the collection, or pipeline, at the current position of the enumerator.</span></span>

<span data-ttu-id="6ff4a-376">**Текущее** свойство будет возвращать то же самое свойство, пока не будет вызван метод **MoveNext** .</span><span class="sxs-lookup"><span data-stu-id="6ff4a-376">The **Current** property continues to return the same property until **MoveNext** is called.</span></span>

## <a name="examples"></a><span data-ttu-id="6ff4a-377">Примеры</span><span class="sxs-lookup"><span data-stu-id="6ff4a-377">Examples</span></span>

### <a name="example-1-using-the-input-variable"></a><span data-ttu-id="6ff4a-378">Пример 1. Использование переменной $input</span><span class="sxs-lookup"><span data-stu-id="6ff4a-378">Example 1: Using the $input variable</span></span>

<span data-ttu-id="6ff4a-379">В следующем примере доступ к `$input` переменной очищает переменную до следующего выполнения блока Process.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-379">In the following example, accessing the `$input` variable clears the variable until the next time the process block executes.</span></span> <span data-ttu-id="6ff4a-380">При использовании метода **Reset** переменная сбрасывается в `$input` Текущее значение конвейера.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-380">Using the **Reset** method resets the `$input` variable to the current pipeline value.</span></span>

```powershell
function Test
{
    begin
    {
        $i = 0
    }

    process
    {
        "Iteration: $i"
        $i++
        "`tInput: $input"
        "`tAccess Again: $input"
        $input.Reset()
        "`tAfter Reset: $input"
    }
}

"one","two" | Test
```

```Output
Iteration: 0
    Input: one
    Access Again:
    After Reset: one
Iteration: 1
    Input: two
    Access Again:
    After Reset: two
```

<span data-ttu-id="6ff4a-381">Блок Process автоматически перемещает `$input` переменную, даже если вы не обращаетесь к ней.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-381">The process block automatically advances the `$input` variable even if you don't access it.</span></span>

```powershell
$skip = $true
function Skip
{
    begin
    {
        $i = 0
    }

    process
    {
        "Iteration: $i"
        $i++
        if ($skip)
        {
            "`tSkipping"
            $skip = $false
        }
        else
        {
            "`tInput: $input"
        }
    }
}

"one","two" | Skip
```

```Output
Iteration: 0
    Skipping
Iteration: 1
    Input: two
```

### <a name="example-2-using-input-outside-the-process-block"></a><span data-ttu-id="6ff4a-382">Пример 2. Использование $input за пределами блока Process</span><span class="sxs-lookup"><span data-stu-id="6ff4a-382">Example 2: Using $input outside the process block</span></span>

<span data-ttu-id="6ff4a-383">За пределами блока Process `$input` переменная представляет все значения, переданные функции.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-383">Outside of the process block the `$input` variable represents all the values piped into the function.</span></span>

- <span data-ttu-id="6ff4a-384">При доступе к `$input` переменной очищаются все значения.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-384">Accessing the `$input` variable clears all values.</span></span>
- <span data-ttu-id="6ff4a-385">Метод **Reset** сбрасывает всю коллекцию.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-385">The **Reset** method resets the entire collection.</span></span>
- <span data-ttu-id="6ff4a-386">**Текущее** свойство никогда не заполняется.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-386">The **Current** property is never populated.</span></span>
- <span data-ttu-id="6ff4a-387">Метод **MoveNext** возвращает значение false, так как коллекция не может быть расширена.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-387">The **MoveNext** method returns false because the collection can't be advanced.</span></span>
  - <span data-ttu-id="6ff4a-388">При вызове **MoveNext** очищается `$input` переменная.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-388">Calling **MoveNext** clears out the `$input` variable.</span></span>

```powershell
Function All
{
    "All Values: $input"
    "Access Again: $input"
    $input.Reset()
    "After Reset: $input"
    $input.MoveNext() | Out-Null
    "After MoveNext: $input"
}

"one","two","three" | All
```

```Output
All Values: one two three
Access Again:
After Reset: one two three
After MoveNext:
```

### <a name="example-3-using-the-inputcurrent-property"></a><span data-ttu-id="6ff4a-389">Пример 3. Использование $input. Текущее свойство</span><span class="sxs-lookup"><span data-stu-id="6ff4a-389">Example 3: Using the $input.Current property</span></span>

<span data-ttu-id="6ff4a-390">С помощью **текущего** свойства текущее значение конвейера можно получить несколько раз без использования метода **Reset** .</span><span class="sxs-lookup"><span data-stu-id="6ff4a-390">By using the **Current** property, the current pipeline value can be accessed multiple times without using the **Reset** method.</span></span> <span data-ttu-id="6ff4a-391">Блок Process не вызывает метод **MoveNext** автоматически.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-391">The process block doesn't automatically call the **MoveNext** method.</span></span>

<span data-ttu-id="6ff4a-392">**Текущее** свойство никогда не будет заполнено, если явно не вызвать **MoveNext**.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-392">The **Current** property will never be populated unless you explicitly call **MoveNext**.</span></span> <span data-ttu-id="6ff4a-393">Доступ к **текущему** свойству можно осуществлять несколько раз в блоке Process без очистки его значения.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-393">The **Current** property can be accessed multiple times inside the process block without clearing its value.</span></span>

```powershell
function Current
{
    begin
    {
        $i = 0
    }

    process
    {
        "Iteration: $i"
        $i++
        "`tBefore MoveNext: $($input.Current)"
        $input.MoveNext() | Out-Null
        "`tAfter MoveNext: $($input.Current)"
        "`tAccess Again: $($input.Current)"
    }
}

"one","two" | Current
```

```Output
Iteration: 0
    Before MoveNext:
    After MoveNext: one
    Access Again: one
Iteration: 1
    Before MoveNext:
    After MoveNext: two
    Access Again: two
```

### <a name="example-4-using-the-foreach-variable"></a><span data-ttu-id="6ff4a-394">Пример 4. Использование переменной $foreach</span><span class="sxs-lookup"><span data-stu-id="6ff4a-394">Example 4: Using the $foreach variable</span></span>

<span data-ttu-id="6ff4a-395">В отличие от `$input` переменной переменная `$foreach` всегда представляет все элементы коллекции при обращении к ним напрямую.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-395">Unlike the `$input` variable, the `$foreach` variable always represents all items in the collection when accessed directly.</span></span> <span data-ttu-id="6ff4a-396">Используйте свойство **Current** для доступа к текущему элементу коллекции, а методы **Reset** и **MoveNext** — для изменения его значения.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-396">Use the **Current** property to access the current collection element, and the **Reset** and **MoveNext** methods to change its value.</span></span>

> [!NOTE]
> <span data-ttu-id="6ff4a-397">Каждая итерация `foreach` цикла будет автоматически вызывать метод **MoveNext** .</span><span class="sxs-lookup"><span data-stu-id="6ff4a-397">Each iteration of the `foreach` loop will automatically call the **MoveNext** method.</span></span>

<span data-ttu-id="6ff4a-398">Следующий цикл выполняется только дважды.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-398">The following loop only executes twice.</span></span> <span data-ttu-id="6ff4a-399">Во второй итерации коллекция перемещается в третий элемент до завершения итерации.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-399">In the second iteration, the collection is moved to the third element before the iteration is complete.</span></span> <span data-ttu-id="6ff4a-400">После второй итерации теперь больше нет значений для итерации, и цикл завершается.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-400">After the second iteration, there are now no more values to iterate, and the loop terminates.</span></span>

<span data-ttu-id="6ff4a-401">Свойство **MoveNext** не влияет на переменную, выбранную для итерации по коллекции ( `$Num` ).</span><span class="sxs-lookup"><span data-stu-id="6ff4a-401">The **MoveNext** property doesn't affect the variable chosen to iterate through the collection (`$Num`).</span></span>

```powershell
$i = 0
foreach ($num in ("one","two","three"))
{
    "Iteration: $i"
    $i++
    "`tNum: $num"
    "`tCurrent: $($foreach.Current)"

    if ($foreach.Current -eq "two")
    {
        "Before MoveNext (Current): $($foreach.Current)"
        $foreach.MoveNext() | Out-Null
        "After MoveNext (Current): $($foreach.Current)"
        "Num has not changed: $num"
    }
}
```

```Output
Iteration: 0
        Num: one
        Current: one
Iteration: 1
        Num: two
        Current: two
Before MoveNext (Current): two
After MoveNext (Current): three
Num has not changed: two
```

<span data-ttu-id="6ff4a-402">При использовании метода **Reset** текущий элемент в коллекции сбрасывается.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-402">Using the **Reset** method resets the current element in the collection.</span></span> <span data-ttu-id="6ff4a-403">В следующем **примере два первых элемента циклически** перебирается, так как вызывается метод **Reset** .</span><span class="sxs-lookup"><span data-stu-id="6ff4a-403">The following example loops through the first two elements **twice** because the **Reset** method is called.</span></span> <span data-ttu-id="6ff4a-404">После первых двух циклов `if` инструкция завершается ошибкой, и цикл выполняет итерацию по всем трем элементам обычно.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-404">After the first two loops, the `if` statement fails and the loop iterates through all three elements normally.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6ff4a-405">Это может привести к бесконечному циклу.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-405">This could result in an infinite loop.</span></span>

```powershell
$stopLoop = 0
foreach ($num in ("one","two", "three"))
{
    ("`t" * $stopLoop) + "Current: $($foreach.Current)"

    if ($num -eq "two" -and $stopLoop -lt 2)
    {
        $foreach.Reset() | Out-Null
        ("`t" * $stopLoop) + "Reset Loop: $stopLoop"
        $stopLoop++
    }
}
```

```Output
Current: one
Current: two
Reset Loop: 0
        Current: one
        Current: two
        Reset Loop: 1
                Current: one
                Current: two
                Current: three
```

### <a name="example-5-using-the-switch-variable"></a><span data-ttu-id="6ff4a-406">Пример 5. Использование переменной $switch</span><span class="sxs-lookup"><span data-stu-id="6ff4a-406">Example 5: Using the $switch variable</span></span>

<span data-ttu-id="6ff4a-407">`$switch`Переменная имеет те же правила, что и `$foreach` переменная.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-407">The `$switch` variable has the exact same rules as the `$foreach` variable.</span></span>
<span data-ttu-id="6ff4a-408">В следующем примере показаны все основные понятия перечислителя.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-408">The following example demonstrates all the enumerator concepts.</span></span>

> [!NOTE]
> <span data-ttu-id="6ff4a-409">Обратите внимание, что **нотевалуатед** Case никогда не выполняется, несмотря на то, что `break` после метода **MoveNext** отсутствует оператор.</span><span class="sxs-lookup"><span data-stu-id="6ff4a-409">Note how the **NotEvaluated** case is never executed, even though there's no `break` statement after the **MoveNext** method.</span></span>

```powershell
$values = "Start", "MoveNext", "NotEvaluated", "Reset", "End"
$stopInfinite = $false
switch ($values)
{
    "MoveNext" {
        "`tMoveNext"
        $switch.MoveNext() | Out-Null
        "`tAfter MoveNext: $($switch.Current)"
    }
    # This case is never evaluated.
    "NotEvaluated" {
        "`tAfterMoveNext: $($switch.Current)"
    }

    "Reset" {
        if (!$stopInfinite)
        {
            "`tReset"
            $switch.Reset()
            $stopInfinite = $true
        }
    }

    default {
        "Default (Current): $($switch.Current)"
    }
}
```

```Output
Default (Current): Start
    MoveNext
    After MoveNext: NotEvaluated
    Reset
Default (Current): Start
    MoveNext
    After MoveNext: NotEvaluated
Default (Current): End
```

## <a name="see-also"></a><span data-ttu-id="6ff4a-410">См. также статью</span><span class="sxs-lookup"><span data-stu-id="6ff4a-410">See also</span></span>

[<span data-ttu-id="6ff4a-411">about_Functions</span><span class="sxs-lookup"><span data-stu-id="6ff4a-411">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="6ff4a-412">about_Functions_Advanced</span><span class="sxs-lookup"><span data-stu-id="6ff4a-412">about_Functions_Advanced</span></span>](about_Functions_Advanced.md)

[<span data-ttu-id="6ff4a-413">about_Functions_Advanced_Methods</span><span class="sxs-lookup"><span data-stu-id="6ff4a-413">about_Functions_Advanced_Methods</span></span>](about_Functions_Advanced_Methods.md)

[<span data-ttu-id="6ff4a-414">about_Functions_Advanced_Parameters</span><span class="sxs-lookup"><span data-stu-id="6ff4a-414">about_Functions_Advanced_Parameters</span></span>](about_Functions_Advanced_Parameters.md)

[<span data-ttu-id="6ff4a-415">about_Functions_OutputTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="6ff4a-415">about_Functions_OutputTypeAttribute</span></span>](about_Functions_OutputTypeAttribute.md)

[<span data-ttu-id="6ff4a-416">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="6ff4a-416">about_Functions_CmdletBindingAttribute</span></span>](about_Functions_CmdletBindingAttribute.md)

[<span data-ttu-id="6ff4a-417">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="6ff4a-417">about_Hash_Tables</span></span>](about_Hash_Tables.md)

[<span data-ttu-id="6ff4a-418">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="6ff4a-418">about_Preference_Variables</span></span>](about_Preference_Variables.md)

[<span data-ttu-id="6ff4a-419">about_Splatting</span><span class="sxs-lookup"><span data-stu-id="6ff4a-419">about_Splatting</span></span>](about_Splatting.md)

[<span data-ttu-id="6ff4a-420">about_Variables</span><span class="sxs-lookup"><span data-stu-id="6ff4a-420">about_Variables</span></span>](about_Variables.md)
