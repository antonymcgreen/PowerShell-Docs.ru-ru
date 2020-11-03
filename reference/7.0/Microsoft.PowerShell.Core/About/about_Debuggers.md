---
description: Описывает отладчик PowerShell.
keywords: powershell,командлет
Locale: en-US
ms.date: 08/06/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_debuggers?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Debuggers
ms.openlocfilehash: c53229752a26428ff4bc47fd5cecf039bdef7275
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93232610"
---
# <a name="about-debuggers"></a><span data-ttu-id="7035b-104">О отладчиках</span><span class="sxs-lookup"><span data-stu-id="7035b-104">About Debuggers</span></span>

## <a name="short-description"></a><span data-ttu-id="7035b-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="7035b-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="7035b-106">Описывает отладчик PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7035b-106">Describes the PowerShell debugger.</span></span>

## <a name="long-description"></a><span data-ttu-id="7035b-107">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="7035b-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="7035b-108">Отладка — это процесс проверки сценария во время его выполнения для обнаружения и исправления ошибок в инструкциях сценария.</span><span class="sxs-lookup"><span data-stu-id="7035b-108">Debugging is the process of examining a script while it is running to identify and correct errors in the script instructions.</span></span> <span data-ttu-id="7035b-109">Отладчик PowerShell помогает исследовать и выявление ошибок и неэффективности в скриптах, функциях, командах, конфигурациях и выражениях настройки требуемого состояния (DSC) PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7035b-109">The PowerShell debugger can help you examine and identify errors and inefficiencies in your scripts, functions, commands, PowerShell Desired State Configuration (DSC) configurations, or expressions.</span></span>

<span data-ttu-id="7035b-110">Начиная с PowerShell 5,0, отладчик PowerShell был обновлен для отладки скриптов, функций, команд, конфигураций или выражений, которые выполняются в консоли или в интегрированной среде сценариев Windows PowerShell на удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="7035b-110">Starting in PowerShell 5.0, the PowerShell debugger has been updated to debug scripts, functions, commands, configurations, or expressions that are running in either the console or Windows PowerShell ISE on remote computers.</span></span> <span data-ttu-id="7035b-111">Вы можете запустить `Enter-PSSession` Интерактивный удаленный сеанс PowerShell, в котором можно задать точки останова и выполнять отладку файлов сценариев и команд на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="7035b-111">You can run `Enter-PSSession` to start an interactive remote PowerShell session in which you can set breakpoints and debug script files and commands on the remote computer.</span></span> <span data-ttu-id="7035b-112">`Enter-PSSession` Обновлены функциональные возможности, которые позволяют повторно подключиться к и ввести отключенный сеанс, выполняющий сценарий или команду на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="7035b-112">`Enter-PSSession` functionality has been updated to let you reconnect to and enter a disconnected session that is running a script or command on a remote computer.</span></span> <span data-ttu-id="7035b-113">Если выполняемый скрипт достигает точки останова, ваш сеанс клиента автоматически запускает отладчик.</span><span class="sxs-lookup"><span data-stu-id="7035b-113">If the running script hits a breakpoint, your client session automatically starts the debugger.</span></span> <span data-ttu-id="7035b-114">Если отключенный сеанс, в котором выполняется скрипт, уже вызвал точку останова и остановлен в точке останова, `Enter-PSSession` автоматически запускает отладчик командной строки после повторного подключения к сеансу.</span><span class="sxs-lookup"><span data-stu-id="7035b-114">If the disconnected session that is running a script has already hit a breakpoint, and is stopped at the breakpoint, `Enter-PSSession` automatically starts the command-line debugger, after you reconnect to the session.</span></span>

<span data-ttu-id="7035b-115">Функции отладчика PowerShell можно использовать для проверки сценария, функции, команды или выражения PowerShell во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="7035b-115">You can use the features of the PowerShell debugger to examine a PowerShell script, function, command, or expression while it is running.</span></span> <span data-ttu-id="7035b-116">Отладчик PowerShell включает набор командлетов, позволяющих задавать точки останова, управлять точками останова и просматривать стек вызовов.</span><span class="sxs-lookup"><span data-stu-id="7035b-116">The PowerShell debugger includes a set of cmdlets that let you set breakpoints, manage breakpoints, and view the call stack.</span></span>

## <a name="debugger-cmdlets"></a><span data-ttu-id="7035b-117">Командлеты отладчика</span><span class="sxs-lookup"><span data-stu-id="7035b-117">Debugger Cmdlets</span></span>

<span data-ttu-id="7035b-118">Отладчик PowerShell включает следующий набор командлетов:</span><span class="sxs-lookup"><span data-stu-id="7035b-118">The PowerShell debugger includes the following set of cmdlets:</span></span>

- <span data-ttu-id="7035b-119">`Set-PSBreakpoint`: Задает точки останова в строках, переменных и командах.</span><span class="sxs-lookup"><span data-stu-id="7035b-119">`Set-PSBreakpoint`: Sets breakpoints on lines, variables, and commands.</span></span>
- <span data-ttu-id="7035b-120">`Get-PSBreakpoint`: Возвращает точки останова в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="7035b-120">`Get-PSBreakpoint`: Gets breakpoints in the current session.</span></span>
- <span data-ttu-id="7035b-121">`Disable-PSBreakpoint`: Отключает точки останова в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="7035b-121">`Disable-PSBreakpoint`: Turns off breakpoints in the current session.</span></span>
- <span data-ttu-id="7035b-122">`Enable-PSBreakpoint`: Повторное включение точек останова в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="7035b-122">`Enable-PSBreakpoint`: Re-enables breakpoints in the current session.</span></span>
- <span data-ttu-id="7035b-123">`Remove-PSBreakpoint`: Удаляет точки останова из текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="7035b-123">`Remove-PSBreakpoint`: Deletes breakpoints from the current session.</span></span>
- <span data-ttu-id="7035b-124">`Get-PSCallStack`: Отображает текущий стек вызовов.</span><span class="sxs-lookup"><span data-stu-id="7035b-124">`Get-PSCallStack`: Displays the current call stack.</span></span>

## <a name="starting-and-stopping-the-debugger"></a><span data-ttu-id="7035b-125">Запуск и остановка отладчика</span><span class="sxs-lookup"><span data-stu-id="7035b-125">Starting and Stopping the Debugger</span></span>

<span data-ttu-id="7035b-126">Чтобы запустить отладчик, задайте одну или несколько точек останова.</span><span class="sxs-lookup"><span data-stu-id="7035b-126">To start the debugger, set one or more breakpoints.</span></span> <span data-ttu-id="7035b-127">Затем запустите скрипт, команду или функцию, которые требуется отладить.</span><span class="sxs-lookup"><span data-stu-id="7035b-127">Then, run the script, command, or function that you want to debug.</span></span>

<span data-ttu-id="7035b-128">При достижении точки останова выполнение останавливается и управление передается отладчику.</span><span class="sxs-lookup"><span data-stu-id="7035b-128">When you reach a breakpoint, execution stops, and control is turned over to the debugger.</span></span>

<span data-ttu-id="7035b-129">Чтобы завершить работу отладчика, выполните сценарий, команду или функцию, пока она не будет завершена.</span><span class="sxs-lookup"><span data-stu-id="7035b-129">To stop the debugger, run the script, command, or function until it is complete.</span></span> <span data-ttu-id="7035b-130">Или введите `stop` или `t` .</span><span class="sxs-lookup"><span data-stu-id="7035b-130">Or, type `stop` or `t`.</span></span>

### <a name="debugger-commands"></a><span data-ttu-id="7035b-131">Команды отладчика</span><span class="sxs-lookup"><span data-stu-id="7035b-131">Debugger Commands</span></span>

<span data-ttu-id="7035b-132">При использовании отладчика в консоли PowerShell используйте следующие команды для управления выполнением.</span><span class="sxs-lookup"><span data-stu-id="7035b-132">When you use the debugger in the PowerShell console, use the following commands to control the execution.</span></span> <span data-ttu-id="7035b-133">В интегрированной среде сценариев Windows PowerShell используйте команды в меню Отладка.</span><span class="sxs-lookup"><span data-stu-id="7035b-133">In Windows PowerShell ISE, use commands on the Debug menu.</span></span>

<span data-ttu-id="7035b-134">Примечание. сведения об использовании отладчика в других ведущих приложениях см. в документации по ведущему приложению.</span><span class="sxs-lookup"><span data-stu-id="7035b-134">Note: For information about how to use the debugger in other host applications, see the host application documentation.</span></span>

- <span data-ttu-id="7035b-135">`s`, `StepInto` : Выполняет следующий оператор, а затем останавливается.</span><span class="sxs-lookup"><span data-stu-id="7035b-135">`s`, `StepInto`: Executes the next statement and then stops.</span></span>

- <span data-ttu-id="7035b-136">`v`, `StepOver` : Выполняет следующий оператор, но пропускает функции и вызовы.</span><span class="sxs-lookup"><span data-stu-id="7035b-136">`v`, `StepOver`: Executes the next statement, but skips functions and invocations.</span></span> <span data-ttu-id="7035b-137">Пропущенные операторы выполняются, но в них отладчик не останавливается.</span><span class="sxs-lookup"><span data-stu-id="7035b-137">The skipped statements are executed, but not stepped through.</span></span>

- <span data-ttu-id="7035b-138">`Ctrl+Break`(Разбейте все в ISE) на выполнение сценария в консоли PowerShell или ИНТЕГРИРОВАНной среде сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7035b-138">`Ctrl+Break`: (Break All in ISE) Breaks into a running script within either the PowerShell console, or Windows PowerShell ISE.</span></span> <span data-ttu-id="7035b-139">Обратите <kbd>Ctrl</kbd>внимание, что + <kbd>разрыв</kbd> CTRL в Windows PowerShell 2,0, 3,0 и 4,0 закрывает программу.</span><span class="sxs-lookup"><span data-stu-id="7035b-139">Note that <kbd>Ctrl</kbd>+<kbd>Break</kbd> in Windows PowerShell 2.0, 3.0, and 4.0 closes the program.</span></span> <span data-ttu-id="7035b-140">Прерывать все работает как с локальными, так и с удаленными интерактивными сценариями.</span><span class="sxs-lookup"><span data-stu-id="7035b-140">Break All works on both local and remote interactively-running scripts.</span></span>

- <span data-ttu-id="7035b-141">`o`, `StepOut` : Действия из текущей функции; на один уровень вверх при вложении.</span><span class="sxs-lookup"><span data-stu-id="7035b-141">`o`, `StepOut`: Steps out of the current function; up one level if nested.</span></span> <span data-ttu-id="7035b-142">Если в основном тексте, он переходит к концу или следующей точке останова.</span><span class="sxs-lookup"><span data-stu-id="7035b-142">If in the main body, it continues to the end or the next breakpoint.</span></span> <span data-ttu-id="7035b-143">Пропущенные операторы выполняются, но в них отладчик не останавливается.</span><span class="sxs-lookup"><span data-stu-id="7035b-143">The skipped statements are executed, but not stepped through.</span></span>

- <span data-ttu-id="7035b-144">`c`, `Continue` : Продолжит работу до завершения скрипта или до достижения следующей точки останова.</span><span class="sxs-lookup"><span data-stu-id="7035b-144">`c`, `Continue`: Continues to run until the script is complete or until the next breakpoint is reached.</span></span> <span data-ttu-id="7035b-145">Пропущенные операторы выполняются, но в них отладчик не останавливается.</span><span class="sxs-lookup"><span data-stu-id="7035b-145">The skipped statements are executed, but not stepped through.</span></span>

- <span data-ttu-id="7035b-146">`l`, `List` : Отображает часть скрипта, который исполняется.</span><span class="sxs-lookup"><span data-stu-id="7035b-146">`l`, `List`: Displays the part of the script that is executing.</span></span> <span data-ttu-id="7035b-147">По умолчанию отображается текущая строка, пять предыдущих строк и 10 последующих строк.</span><span class="sxs-lookup"><span data-stu-id="7035b-147">By default, it displays the current line, five previous lines, and 10 subsequent lines.</span></span>
  <span data-ttu-id="7035b-148">Чтобы продолжить составление списка сценариев, нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="7035b-148">To continue listing the script, press ENTER.</span></span>

- <span data-ttu-id="7035b-149">`l <m>`, `List` : Отображает 16 строк сценария, начиная с номера строки, заданного параметром `<m>` .</span><span class="sxs-lookup"><span data-stu-id="7035b-149">`l <m>`, `List`: Displays 16 lines of the script beginning with the line number specified by `<m>`.</span></span>

- <span data-ttu-id="7035b-150">`l <m> <n>`, `List` : Отображает `<n>` строки скрипта, начиная с номера строки, заданного параметром `<m>` .</span><span class="sxs-lookup"><span data-stu-id="7035b-150">`l <m> <n>`, `List`: Displays `<n>` lines of the script, beginning with the line number specified by `<m>`.</span></span>

- <span data-ttu-id="7035b-151">`q`, `Stop` , `Exit` : Останавливает выполнение скрипта и завершает работу отладчика.</span><span class="sxs-lookup"><span data-stu-id="7035b-151">`q`, `Stop`, `Exit`: Stops executing the script, and exits the debugger.</span></span> <span data-ttu-id="7035b-152">Если выполняется отладка задания с помощью `Debug-Job` командлета, `Exit` команда отсоединяет отладчик и позволяет продолжить выполнение задания.</span><span class="sxs-lookup"><span data-stu-id="7035b-152">If you are debugging a job by running the `Debug-Job` cmdlet, the `Exit` command detaches the debugger, and allows the job to continue running.</span></span>

- <span data-ttu-id="7035b-153">`k`, `Get-PsCallStack` : Отображает текущий стек вызовов.</span><span class="sxs-lookup"><span data-stu-id="7035b-153">`k`, `Get-PsCallStack`: Displays the current call stack.</span></span>

- <span data-ttu-id="7035b-154">`<Enter>`: Повторяет последнюю команду, если она была на шаге (-ов), Степовер (v) или List (l).</span><span class="sxs-lookup"><span data-stu-id="7035b-154">`<Enter>`: Repeats the last command if it was Step (s), StepOver (v), or List (l).</span></span> <span data-ttu-id="7035b-155">В противном случае представляет действие отправки.</span><span class="sxs-lookup"><span data-stu-id="7035b-155">Otherwise, represents a submit action.</span></span>

- <span data-ttu-id="7035b-156">`?`, `h` : Отображает справку по командам отладчика.</span><span class="sxs-lookup"><span data-stu-id="7035b-156">`?`, `h`: Displays the debugger command Help.</span></span>

<span data-ttu-id="7035b-157">Чтобы выйти из отладчика, можно использовать команду «прекратить» (q).</span><span class="sxs-lookup"><span data-stu-id="7035b-157">To exit the debugger, you can use Stop (q).</span></span>

<span data-ttu-id="7035b-158">Начиная с PowerShell 5,0 можно выполнить команду Exit, чтобы выйти из вложенного сеанса отладки, запущенного с помощью команды `Debug-Job` или `Debug-Runspace` .</span><span class="sxs-lookup"><span data-stu-id="7035b-158">Starting in PowerShell 5.0, you can run the Exit command to exit a nested debugging session that you started by running either `Debug-Job` or `Debug-Runspace`.</span></span>

<span data-ttu-id="7035b-159">С помощью этих команд отладчика можно выполнять сценарий, останавливаться на определенном этапе, проверять значения переменных и состояния системы и продолжать выполнение сценария до тех пор, пока не будет выявлена проблема.</span><span class="sxs-lookup"><span data-stu-id="7035b-159">By using these debugger commands, you can run a script, stop on a point of concern, examine the values of variables and the state of the system, and continue running the script until you have identified a problem.</span></span>

<span data-ttu-id="7035b-160">Примечание. при переходе к оператору с оператором перенаправления, например ">", отладчик PowerShell выполняет шаг над всеми остальными инструкциями в скрипте.</span><span class="sxs-lookup"><span data-stu-id="7035b-160">NOTE: If you step into a statement with a redirection operator, such as ">", the PowerShell debugger steps over all remaining statements in the script.</span></span>

<span data-ttu-id="7035b-161">Отображение значений переменных скрипта</span><span class="sxs-lookup"><span data-stu-id="7035b-161">Displaying the Values of script Variables</span></span>

<span data-ttu-id="7035b-162">В отладчике можно также вводить команды, отображать значения переменных, использовать командлеты и выполнять сценарии в командной строке.</span><span class="sxs-lookup"><span data-stu-id="7035b-162">While you are in the debugger, you can also enter commands, display the value of variables, use cmdlets, and run scripts at the command line.</span></span>

<span data-ttu-id="7035b-163">Можно отобразить текущее значение всех переменных в отлаживаемом скрипте, за исключением следующих автоматических переменных:</span><span class="sxs-lookup"><span data-stu-id="7035b-163">You can display the current value of all variables in the script that is being debugged, except for the following automatic variables:</span></span>

```powershell
$_
$Args
$Input
$MyInvocation
$PSBoundParameters
```

<span data-ttu-id="7035b-164">При попытке отобразить значение любой из этих переменных отображается значение переменной из внутреннего конвейера отладчика, а не переменной в сценарии.</span><span class="sxs-lookup"><span data-stu-id="7035b-164">If you try to display the value of any of these variables, you get the value of that variable for in an internal pipeline the debugger uses, not the value of the variable in the script.</span></span>

<span data-ttu-id="7035b-165">Чтобы отобразить значения этих переменных для отлаживаемого скрипта, в скрипте присвойте значение автоматически изменяемой переменной новой переменной.</span><span class="sxs-lookup"><span data-stu-id="7035b-165">To display the value these variables for the script that is being debugged, in the script, assign the value of the automatic variable to a new variable.</span></span> <span data-ttu-id="7035b-166">Затем можно отобразить значение новой переменной.</span><span class="sxs-lookup"><span data-stu-id="7035b-166">Then you can display the value of the new variable.</span></span>

<span data-ttu-id="7035b-167">Например, примененная к объекту директива</span><span class="sxs-lookup"><span data-stu-id="7035b-167">For example,</span></span>

```powershell
$scriptArgs = $Args
$scriptArgs
```

<span data-ttu-id="7035b-168">В примере в этом разделе значение `$MyInvocation` переменной переназначается следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7035b-168">In the example in this topic, the value of the `$MyInvocation` variable is reassigned as follows:</span></span>

```powershell
$scriptname = $MyInvocation.MyCommand.Path
```

## <a name="the-debugger-environment"></a><span data-ttu-id="7035b-169">Среда отладчика</span><span class="sxs-lookup"><span data-stu-id="7035b-169">The Debugger Environment</span></span>

<span data-ttu-id="7035b-170">При достижении точки останова вы вводите среду отладчика.</span><span class="sxs-lookup"><span data-stu-id="7035b-170">When you reach a breakpoint, you enter the debugger environment.</span></span> <span data-ttu-id="7035b-171">Командная строка изменится так, чтобы она начиналась с "[DBG]:".</span><span class="sxs-lookup"><span data-stu-id="7035b-171">The command prompt changes so that it begins with "[DBG]:".</span></span>

<span data-ttu-id="7035b-172">Дополнительные сведения о настройке командной строки см. в разделе [about_Prompts](about_prompts.md).</span><span class="sxs-lookup"><span data-stu-id="7035b-172">For more information about customizing the prompt, see [about_Prompts](about_prompts.md).</span></span>

<span data-ttu-id="7035b-173">Кроме того, в некоторых ведущих приложениях, таких как консоль PowerShell (но не в интегрированной среде сценариев Windows PowerShell [ISE]), для отладки открывается вложенный запрос.</span><span class="sxs-lookup"><span data-stu-id="7035b-173">Also, in some host applications, such as the PowerShell console, (but not in Windows PowerShell Integrated Scripting Environment [ISE]), a nested prompt opens for debugging.</span></span> <span data-ttu-id="7035b-174">Вложенные запросы можно обнаружить по повторяющимся символам "больше чем" (ASCII 62), которые отображаются в командной строке.</span><span class="sxs-lookup"><span data-stu-id="7035b-174">You can detect the nested prompt by the repeating greater-than characters (ASCII 62) that appear at the command prompt.</span></span>

<span data-ttu-id="7035b-175">Например, в консоли PowerShell по умолчанию используется следующая строка отладки:</span><span class="sxs-lookup"><span data-stu-id="7035b-175">For example, the following is the default debugging prompt in the PowerShell console:</span></span>

```
[DBG]: PS (get-location)>>>
```

<span data-ttu-id="7035b-176">Уровень вложенности можно найти с помощью `$NestedPromptLevel` автоматической переменной.</span><span class="sxs-lookup"><span data-stu-id="7035b-176">You can find the nesting level by using the `$NestedPromptLevel` automatic variable.</span></span>

<span data-ttu-id="7035b-177">Кроме того, `$PSDebugContext` в локальной области определена автоматическая переменная,.</span><span class="sxs-lookup"><span data-stu-id="7035b-177">Additionally, an automatic variable, `$PSDebugContext`, is defined in the local scope.</span></span> <span data-ttu-id="7035b-178">Наличие переменной можно использовать `$PsDebugContext` для определения того, находится ли вы в отладчике.</span><span class="sxs-lookup"><span data-stu-id="7035b-178">You can use the presence of the `$PsDebugContext` variable to determine whether you are in the debugger.</span></span>

<span data-ttu-id="7035b-179">Пример:</span><span class="sxs-lookup"><span data-stu-id="7035b-179">For example:</span></span>

```powershell
if ($PSDebugContext) {"Debugging"} else {"Not Debugging"}
```

<span data-ttu-id="7035b-180">Значение переменной можно использовать `$PSDebugContext` в отладке.</span><span class="sxs-lookup"><span data-stu-id="7035b-180">You can use the value of the `$PSDebugContext` variable in your debugging.</span></span>

```
[DBG]: PS>>> $PSDebugContext.InvocationInfo

Name   CommandLineParameters  UnboundArguments  Location
----   ---------------------  ----------------  --------
=      {}                     {}                C:\ps-test\vote.ps1 (1)
```

## <a name="debugging-and-scope"></a><span data-ttu-id="7035b-181">Отладка и область</span><span class="sxs-lookup"><span data-stu-id="7035b-181">Debugging and Scope</span></span>

<span data-ttu-id="7035b-182">Переход в отладчик не влияет на область, в которой работает, но при достижении точки останова в скрипте вы переходите в область скрипта.</span><span class="sxs-lookup"><span data-stu-id="7035b-182">Breaking into the debugger does not change the scope in which you are operating, but when you reach a breakpoint in a script, you move into the script scope.</span></span> <span data-ttu-id="7035b-183">Область скрипта является дочерней для области, в которой запущен отладчик.</span><span class="sxs-lookup"><span data-stu-id="7035b-183">The script scope is a child of the scope in which you ran the debugger.</span></span>

<span data-ttu-id="7035b-184">Чтобы найти переменные и псевдонимы, определенные в области скрипта, используйте параметр scope `Get-Alias` `Get-Variable` командлета или.</span><span class="sxs-lookup"><span data-stu-id="7035b-184">To find the variables and aliases that are defined in the script scope, use the Scope parameter of the `Get-Alias` or `Get-Variable` cmdlets.</span></span>

<span data-ttu-id="7035b-185">Например, следующая команда получает переменные в локальной области (скрипт):</span><span class="sxs-lookup"><span data-stu-id="7035b-185">For example, the following command gets the variables in the local (script) scope:</span></span>

```powershell
Get-Variable -scope 0
```

<span data-ttu-id="7035b-186">Вы можете сократить команду следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7035b-186">You can abbreviate the command as:</span></span>

```powershell
gv -s 0
```

<span data-ttu-id="7035b-187">Это удобный способ просмотра только переменных, определенных в скрипте и определенных во время отладки.</span><span class="sxs-lookup"><span data-stu-id="7035b-187">This is a useful way to see only the variables that you defined in the script and that you defined while debugging.</span></span>

<span data-ttu-id="7035b-188">Отладка в командной строке</span><span class="sxs-lookup"><span data-stu-id="7035b-188">Debugging at the Command Line</span></span>

<span data-ttu-id="7035b-189">При установке точки останова переменной или точки останова команды можно задать точку останова только в файле скрипта.</span><span class="sxs-lookup"><span data-stu-id="7035b-189">When you set a variable breakpoint or a command breakpoint, you can set the breakpoint only in a script file.</span></span> <span data-ttu-id="7035b-190">Однако по умолчанию точка останова устанавливается для любого, который выполняется в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="7035b-190">However, by default, the breakpoint is set on anything that runs in the current session.</span></span>

<span data-ttu-id="7035b-191">Например, если задать точку останова в `$name` переменной, отладчик остановится на любой `$name` переменной в любом скрипте, команде, функции, командлете или выражении, которое выполняется до отключения или удаления точки останова.</span><span class="sxs-lookup"><span data-stu-id="7035b-191">For example, if you set a breakpoint on the `$name` variable, the debugger breaks on any `$name` variable in any script, command, function, script cmdlet or expression that you run until you disable or remove the breakpoint.</span></span>

<span data-ttu-id="7035b-192">Это позволяет выполнять отладку скриптов в более реалистичном контексте, в котором они могут зависеть от функций, переменных и других сценариев в сеансе и в профиле пользователя.</span><span class="sxs-lookup"><span data-stu-id="7035b-192">This allows you to debug your scripts in a more realistic context in which they might be affected by functions, variables, and other scripts in the session and in the user's profile.</span></span>

<span data-ttu-id="7035b-193">Точки останова строки зависят от файлов скриптов, поэтому они задаются только в файлах скриптов.</span><span class="sxs-lookup"><span data-stu-id="7035b-193">Line breakpoints are specific to script files, so they are set only in script files.</span></span>

## <a name="debugging-functions"></a><span data-ttu-id="7035b-194">Функции отладки</span><span class="sxs-lookup"><span data-stu-id="7035b-194">Debugging Functions</span></span>

<span data-ttu-id="7035b-195">При установке точки останова в функции, которая содержит `Begin` `Process` разделы, и `End` , отладчик прерывает выполнение в первой строке каждого раздела.</span><span class="sxs-lookup"><span data-stu-id="7035b-195">When you set a breakpoint on a function that has `Begin`, `Process`, and `End` sections, the debugger breaks at the first line of each section.</span></span>

<span data-ttu-id="7035b-196">Пример:</span><span class="sxs-lookup"><span data-stu-id="7035b-196">For example:</span></span>

```powershell
function test-cmdlet {
    begin {
        write-output "Begin"
    }
    process {
        write-output "Process"
    }
    end {
        write-output "End"
    }
}

C:\PS> Set-PSBreakpoint -command test-cmdlet

C:\PS> test-cmdlet

Begin
Entering debug mode. Use h or ? for help.

Hit Command breakpoint on 'prompt:test-cmdlet'

test-cmdlet

[DBG]: C:\PS> c
Process
Entering debug mode. Use h or ? for help.

Hit Command breakpoint on 'prompt:test-cmdlet'

test-cmdlet

[DBG]: C:\PS> c
End
Entering debug mode. Use h or ? for help.

Hit Command breakpoint on 'prompt:test-cmdlet'

test-cmdlet

# [DBG]: C:\PS>
```

## <a name="debugging-remote-scripts"></a><span data-ttu-id="7035b-197">Отладка удаленных скриптов</span><span class="sxs-lookup"><span data-stu-id="7035b-197">Debugging Remote Scripts</span></span>

<span data-ttu-id="7035b-198">Начиная с PowerShell 5,0 можно запустить отладчик PowerShell в удаленном сеансе, в консоли или в интегрированной среде сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7035b-198">Starting in PowerShell 5.0, you can run the PowerShell debugger in a remote session, in either the console, or Windows PowerShell ISE.</span></span>
<span data-ttu-id="7035b-199">`Enter-PSSession` были обновлены функциональные возможности для повторного подключения к и входа в отключенный сеанс, запущенный на удаленном компьютере, и в данный момент выполняется сценарий.</span><span class="sxs-lookup"><span data-stu-id="7035b-199">`Enter-PSSession` functionality has been updated to let you reconnect to and enter a disconnected session that is running on a remote computer, and currently running a script.</span></span> <span data-ttu-id="7035b-200">Если выполняемый скрипт достигает точки останова, ваш сеанс клиента автоматически запускает отладчик.</span><span class="sxs-lookup"><span data-stu-id="7035b-200">If the running script hits a breakpoint, your client session automatically starts the debugger.</span></span>

<span data-ttu-id="7035b-201">Ниже приведен пример, в котором показано, как это работает, с точками останова, заданными в скрипте в строках 6, 11, 22 и 25.</span><span class="sxs-lookup"><span data-stu-id="7035b-201">The following is an example that shows how this works, with breakpoints set in a script at lines 6, 11, 22, and 25.</span></span> <span data-ttu-id="7035b-202">Обратите внимание, что в примере при запуске отладчика есть два идентифицирующих приглашения: имя компьютера, на котором выполняется сеанс, и запрос DBG, который позволяет убедиться в том, что вы работаете в режиме отладки.</span><span class="sxs-lookup"><span data-stu-id="7035b-202">Note that in the example, when the debugger starts, there are two identifying prompts: the name of the computer on which the session is running, and the DBG prompt that lets you know you are in debugging mode.</span></span>

```powershell
Enter-Pssession -Cn localhost
[localhost]: PS C:\psscripts> Set-PSBreakpoint .\ttest19.ps1 6,11,22,25

ID Script          Line     Command          Variable          Action
-- ------          ----     -------          --------          ------
0 ttest19.ps1          6
1 ttest19.ps1          11
2 ttest19.ps1          22
3 ttest19.ps1          25

[localhost]: PS C:\psscripts> .\ttest19.ps1
Hit Line breakpoint on 'C:\psscripts\ttest19.ps1:11'

At C:\psscripts\ttest19.ps1:11 char:1
+ $winRMName = "WinRM"
# + ~

[localhost]: [DBG]: PS C:\psscripts>> list

6:      1..5 | foreach { sleep 1; Write-Output "hello2day $_" }
7:  }
# 8:

9:  $count = 10
10:  $psName = "PowerShell"
11:* $winRMName = "WinRM"
12:  $myVar = 102
# 13:

14:  for ($i=0; $i -lt $count; $i++)
15:  {
16:      sleep 1
17:      Write-Output "Loop iteration is: $i"
18:      Write-Output "MyVar is $myVar"
# 19:

20:      hello2day
# 21:


[localhost]: [DBG]: PS C:\psscripts>> stepover
At C:\psscripts\ttest19.ps1:12 char:1
+ $myVar = 102
# + ~

[localhost]: [DBG]: PS C:\psscripts>> quit
[localhost]: PS C:\psscripts> Exit-PSSession
PS C:\psscripts>
```

## <a name="examples"></a><span data-ttu-id="7035b-203">Примеры</span><span class="sxs-lookup"><span data-stu-id="7035b-203">Examples</span></span>

<span data-ttu-id="7035b-204">Этот сценарий тестирования обнаруживает версию операционной системы и отображает сообщение, соответствующее системе.</span><span class="sxs-lookup"><span data-stu-id="7035b-204">This test script detects the version of the operating system and displays a system-appropriate message.</span></span> <span data-ttu-id="7035b-205">Он включает функцию, вызов функции и переменную.</span><span class="sxs-lookup"><span data-stu-id="7035b-205">It includes a function, a function call, and a variable.</span></span>

<span data-ttu-id="7035b-206">Следующая команда отображает содержимое файла скрипта теста:</span><span class="sxs-lookup"><span data-stu-id="7035b-206">The following command displays the contents of the test script file:</span></span>

```powershell
PS C:\PS-test>  Get-Content test.ps1

function psversion {
  "PowerShell " + $PSVersionTable.PSVersion
  if ($PSVersionTable.PSVersion.Major -lt 6) {
    "Upgrade to PowerShell 6.0!"
  }
  else {
    "Have you run a background job today (start-job)?"
  }
}

$scriptName = $MyInvocation.MyCommand.Path
psversion
"Done $scriptName."
```

<span data-ttu-id="7035b-207">Для начала установите точку останова в определенном месте скрипта, например в строке, команде, переменной или функции.</span><span class="sxs-lookup"><span data-stu-id="7035b-207">To start, set a breakpoint at a point of interest in the script, such as a line, command, variable, or function.</span></span>

<span data-ttu-id="7035b-208">Начните с создания точки останова строки в первой строке скрипта Test.ps1 в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="7035b-208">Start by creating a line breakpoint on the first line of the Test.ps1 script in the current directory.</span></span>

```powershell
PS C:\ps-test> Set-PSBreakpoint -line 1 -script test.ps1
```

<span data-ttu-id="7035b-209">Данную команду можно сократить следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7035b-209">You can abbreviate this command as:</span></span>

```powershell
PS C:\ps-test> spb 1 -s test.ps1
```

<span data-ttu-id="7035b-210">Команда возвращает объект точки останова строки ( **System. Management. Automation. линебреакпоинт** ).</span><span class="sxs-lookup"><span data-stu-id="7035b-210">The command returns a line-breakpoint object ( **System.Management.Automation.LineBreakpoint** ).</span></span>

```
Column     : 0
Line       : 1
Action     :
Enabled    : True
HitCount   : 0
Id         : 0
Script     : C:\ps-test\test.ps1
ScriptName : C:\ps-test\test.ps1
```

<span data-ttu-id="7035b-211">Теперь запустите сценарий.</span><span class="sxs-lookup"><span data-stu-id="7035b-211">Now, start the script.</span></span>

```powershell
PS C:\ps-test> .\test.ps1
```

<span data-ttu-id="7035b-212">Когда скрипт достигает первой точки останова, сообщение точки останова указывает на то, что отладчик активен.</span><span class="sxs-lookup"><span data-stu-id="7035b-212">When the script reaches the first breakpoint, the breakpoint message indicates that the debugger is active.</span></span> <span data-ttu-id="7035b-213">Он описывает точку останова и предварительный просмотр первой строки скрипта, которая является объявлением функции.</span><span class="sxs-lookup"><span data-stu-id="7035b-213">It describes the breakpoint and previews the first line of the script, which is a function declaration.</span></span> <span data-ttu-id="7035b-214">Командная строка также изменится, указывая, что отладчик имеет элемент управления.</span><span class="sxs-lookup"><span data-stu-id="7035b-214">The command prompt also changes to indicate that the debugger has control.</span></span>

<span data-ttu-id="7035b-215">В строке предварительного просмотра содержится имя скрипта и номер строки предварительно просматриваемой команды.</span><span class="sxs-lookup"><span data-stu-id="7035b-215">The preview line includes the script name and the line number of the previewed command.</span></span>

```powershell
Entering debug mode. Use h or ? for help.

Hit Line breakpoint on 'C:\ps-test\test.ps1:1'

test.ps1:1   function psversion {
# DBG>
```

<span data-ttu-id="7035b-216">Используйте команды step, чтобы выполнить первый оператор в скрипте и просмотреть следующий оператор.</span><span class="sxs-lookup"><span data-stu-id="7035b-216">Use the Step command (s) to execute the first statement in the script and to preview the next statement.</span></span> <span data-ttu-id="7035b-217">Следующая инструкция использует `$MyInvocation` автоматическую переменную, чтобы установить значение `$scriptName` переменной в качестве пути и имени файла скрипта.</span><span class="sxs-lookup"><span data-stu-id="7035b-217">The next statement uses the `$MyInvocation` automatic variable to set the value of the `$scriptName` variable to the path and file name of the script file.</span></span>

```powershell
DBG> s
test.ps1:11  $scriptName = $MyInvocation.MyCommand.Path
```

<span data-ttu-id="7035b-218">На этом этапе `$scriptName` переменная не заполняется, но можно проверить значение переменной, отображая ее значение.</span><span class="sxs-lookup"><span data-stu-id="7035b-218">At this point, the `$scriptName` variable is not populated, but you can verify the value of the variable by displaying its value.</span></span> <span data-ttu-id="7035b-219">В этом случае используется значение `$null`.</span><span class="sxs-lookup"><span data-stu-id="7035b-219">In this case, the value is `$null`.</span></span>

```powershell
DBG> $scriptname
# DBG>
```

<span data-ttu-id="7035b-220">Используйте другие команды шага для выполнения текущей инструкции и предварительного просмотра следующей инструкции в скрипте.</span><span class="sxs-lookup"><span data-stu-id="7035b-220">Use another Step command (s) to execute the current statement and to preview the next statement in the script.</span></span> <span data-ttu-id="7035b-221">Следующий оператор вызывает функцию PsVersion.</span><span class="sxs-lookup"><span data-stu-id="7035b-221">The next statement calls the PsVersion function.</span></span>

```powershell
DBG> s
test.ps1:12  psversion
```

<span data-ttu-id="7035b-222">На этом этапе `$scriptName` переменная заполняется, но значение переменной проверяется путем отображения ее значения.</span><span class="sxs-lookup"><span data-stu-id="7035b-222">At this point, the `$scriptName` variable is populated, but you verify the value of the variable by displaying its value.</span></span> <span data-ttu-id="7035b-223">В этом случае в качестве значения задается путь к скрипту.</span><span class="sxs-lookup"><span data-stu-id="7035b-223">In this case, the value is set to the script path.</span></span>

```powershell
DBG> $scriptName
C:\ps-test\test.ps1
```

<span data-ttu-id="7035b-224">Используйте другую команду Step для выполнения вызова функции.</span><span class="sxs-lookup"><span data-stu-id="7035b-224">Use another Step command to execute the function call.</span></span> <span data-ttu-id="7035b-225">Нажмите клавишу ВВОД или введите "s" для шага.</span><span class="sxs-lookup"><span data-stu-id="7035b-225">Press ENTER, or type "s" for Step.</span></span>

```powershell
DBG> s
test.ps1:2       "PowerShell " + $PSVersionTable.PSVersion
```

<span data-ttu-id="7035b-226">Сообщение отладки содержит предварительную версию инструкции в функции.</span><span class="sxs-lookup"><span data-stu-id="7035b-226">The debug message includes a preview of the statement in the function.</span></span> <span data-ttu-id="7035b-227">Чтобы выполнить эту инструкцию и предварительно просмотреть следующий оператор в функции, можно использовать `Step` команду.</span><span class="sxs-lookup"><span data-stu-id="7035b-227">To execute this statement and to preview the next statement in the function, you can use a `Step` command.</span></span> <span data-ttu-id="7035b-228">Но в этом случае используйте команду шага (o).</span><span class="sxs-lookup"><span data-stu-id="7035b-228">But, in this case, use a StepOut command (o).</span></span> <span data-ttu-id="7035b-229">Она завершает выполнение функции (если она не достигает точки останова) и переходит к следующему оператору в скрипте.</span><span class="sxs-lookup"><span data-stu-id="7035b-229">It completes the execution of the function (unless it reaches a breakpoint) and steps to the next statement in the script.</span></span>

```powershell
DBG> o
Windows PowerShell 2.0
Have you run a background job today (start-job)?
test.ps1:13  "Done $scriptName"
```

<span data-ttu-id="7035b-230">Так как мы работаем с последней инструкцией в сценарии, команды шаг, шаг с заходом и продолжить имеют одинаковый результат.</span><span class="sxs-lookup"><span data-stu-id="7035b-230">Because we are on the last statement in the script, the Step, StepOut, and Continue commands have the same effect.</span></span> <span data-ttu-id="7035b-231">В этом случае используйте шаг (o).</span><span class="sxs-lookup"><span data-stu-id="7035b-231">In this case, use StepOut (o).</span></span>

```powershell
Done C:\ps-test\test.ps1
PS C:\ps-test>
```

<span data-ttu-id="7035b-232">Команда Step by выполняет последнюю команду.</span><span class="sxs-lookup"><span data-stu-id="7035b-232">The StepOut command executes the last command.</span></span> <span data-ttu-id="7035b-233">Стандартная командная строка указывает, что отладчик завершил работу и вернул управление обработчику команд.</span><span class="sxs-lookup"><span data-stu-id="7035b-233">The standard command prompt indicates that the debugger has exited and returned control to the command processor.</span></span>

<span data-ttu-id="7035b-234">Теперь снова запустите отладчик.</span><span class="sxs-lookup"><span data-stu-id="7035b-234">Now, run the debugger again.</span></span> <span data-ttu-id="7035b-235">Прежде всего, чтобы удалить текущую точку останова, `Get-PsBreakpoint` Используйте `Remove-PsBreakpoint` командлеты и.</span><span class="sxs-lookup"><span data-stu-id="7035b-235">First, to delete the current breakpoint, use the `Get-PsBreakpoint` and `Remove-PsBreakpoint` cmdlets.</span></span> <span data-ttu-id="7035b-236">(Если вы считаете, что вы можете повторно использовать точку останова, используйте `Disable-PsBreakpoint` командлет вместо `Remove-PsBreakpoint` .)</span><span class="sxs-lookup"><span data-stu-id="7035b-236">(If you think you might reuse the breakpoint, use the `Disable-PsBreakpoint` cmdlet instead of `Remove-PsBreakpoint`.)</span></span>

```powershell
PS C:\ps-test> Get-PSBreakpoint| Remove-PSBreakpoint
```

<span data-ttu-id="7035b-237">Данную команду можно сократить следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7035b-237">You can abbreviate this command as:</span></span>

```powershell
PS C:\ps-test> gbp | rbp
```

<span data-ttu-id="7035b-238">Или выполните команду, написав функцию, например следующую:</span><span class="sxs-lookup"><span data-stu-id="7035b-238">Or, run the command by writing a function, such as the following function:</span></span>

```powershell
function delbr { gbp | rbp }
```

<span data-ttu-id="7035b-239">Теперь создайте точку останова для `$scriptname` переменной.</span><span class="sxs-lookup"><span data-stu-id="7035b-239">Now, create a breakpoint on the `$scriptname` variable.</span></span>

```powershell
PS C:\ps-test> Set-PSBreakpoint -variable scriptname -script test.ps1
```

<span data-ttu-id="7035b-240">Вы можете сократить команду следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7035b-240">You can abbreviate the command as:</span></span>

```powershell
PS C:\ps-test> sbp -v scriptname -s test.ps1
```

<span data-ttu-id="7035b-241">Теперь запустите сценарий.</span><span class="sxs-lookup"><span data-stu-id="7035b-241">Now, start the script.</span></span> <span data-ttu-id="7035b-242">Скрипт достигает точки останова переменной.</span><span class="sxs-lookup"><span data-stu-id="7035b-242">The script reaches the variable breakpoint.</span></span> <span data-ttu-id="7035b-243">Режимом по умолчанию является Write, поэтому выполнение останавливается непосредственно перед инструкцией, которая изменяет значение переменной.</span><span class="sxs-lookup"><span data-stu-id="7035b-243">The default mode is Write, so execution stops just before the statement that changes the value of the variable.</span></span>

```powershell
PS C:\ps-test> .\test.ps1
Hit Variable breakpoint on 'C:\ps-test\test.ps1:$scriptName'
(Write access)

test.ps1:11  $scriptName = $MyInvocation.MyCommand.Path
# DBG>
```

<span data-ttu-id="7035b-244">Отображает текущее значение `$scriptName` переменной, то есть `$null` .</span><span class="sxs-lookup"><span data-stu-id="7035b-244">Display the current value of the `$scriptName` variable, which is `$null`.</span></span>

```powershell
DBG> $scriptName
# DBG>
```

<span data-ttu-id="7035b-245">Используйте команды шага для выполнения инструкции, заполняющей переменную.</span><span class="sxs-lookup"><span data-stu-id="7035b-245">Use a Step command (s) to execute the statement that populates the variable.</span></span>
<span data-ttu-id="7035b-246">Затем отобразится новое значение `$scriptName` переменной.</span><span class="sxs-lookup"><span data-stu-id="7035b-246">Then, display the new value of the `$scriptName` variable.</span></span>

```powershell
DBG> $scriptName
C:\ps-test\test.ps1
```powershell

Use a Step command (s) to preview the next statement in the script.

```powershell
DBG> s
test.ps1:12  psversion
```

<span data-ttu-id="7035b-247">Следующий оператор является вызовом функции PsVersion.</span><span class="sxs-lookup"><span data-stu-id="7035b-247">The next statement is a call to the PsVersion function.</span></span> <span data-ttu-id="7035b-248">Чтобы пропустить функцию, но по-прежнему выполнить ее, используйте команду Степовер (v).</span><span class="sxs-lookup"><span data-stu-id="7035b-248">To skip the function but still execute it, use a StepOver command (v).</span></span> <span data-ttu-id="7035b-249">Если вы уже используете функцию Степовер, она не действует.</span><span class="sxs-lookup"><span data-stu-id="7035b-249">If you are already in the function when you use StepOver, it is not effective.</span></span> <span data-ttu-id="7035b-250">Вызов функции отображается, но не выполняется.</span><span class="sxs-lookup"><span data-stu-id="7035b-250">The function call is displayed, but it is not executed.</span></span>

```powershell
DBG> v
Windows PowerShell 2.0
Have you run a background job today (start-job)?
test.ps1:13  "Done $scriptName"
```

<span data-ttu-id="7035b-251">Команда Степовер выполняет функцию и просматривает следующий оператор в скрипте, который выводит последнюю строку.</span><span class="sxs-lookup"><span data-stu-id="7035b-251">The StepOver command executes the function, and it previews the next statement in the script, which prints the final line.</span></span>

<span data-ttu-id="7035b-252">Чтобы выйти из отладчика, используйте команду "прекратить" (t).</span><span class="sxs-lookup"><span data-stu-id="7035b-252">Use a Stop command (t) to exit the debugger.</span></span> <span data-ttu-id="7035b-253">Командная строка вернется в стандартную командную строку.</span><span class="sxs-lookup"><span data-stu-id="7035b-253">The command prompt reverts to the standard command prompt.</span></span>

```powershell
C:\ps-test>
```

<span data-ttu-id="7035b-254">Чтобы удалить точки останова, используйте `Get-PsBreakpoint` `Remove-PsBreakpoint` командлеты и.</span><span class="sxs-lookup"><span data-stu-id="7035b-254">To delete the breakpoints, use the `Get-PsBreakpoint` and `Remove-PsBreakpoint` cmdlets.</span></span>

```powershell
PS C:\ps-test> Get-PSBreakpoint| Remove-PSBreakpoint
```

<span data-ttu-id="7035b-255">Создайте новую точку останова команды в функции PsVersion.</span><span class="sxs-lookup"><span data-stu-id="7035b-255">Create a new command breakpoint on the PsVersion function.</span></span>

```powershell
PS C:\ps-test> Set-PSBreakpoint -command psversion -script test.ps1
```

<span data-ttu-id="7035b-256">Эту команду можно сократить, чтобы:</span><span class="sxs-lookup"><span data-stu-id="7035b-256">You can abbreviate this command to:</span></span>

```powershell
PS C:\ps-test> sbp -c psversion -s test.ps1
```

<span data-ttu-id="7035b-257">Теперь запустите сценарий.</span><span class="sxs-lookup"><span data-stu-id="7035b-257">Now, run the script.</span></span>

```powershell
PS C:\ps-test> .\test.ps1
Hit Command breakpoint on 'C:\ps-test\test.ps1:psversion'

test.ps1:12  psversion
# DBG>
```

<span data-ttu-id="7035b-258">Скрипт достигает точки останова при вызове функции.</span><span class="sxs-lookup"><span data-stu-id="7035b-258">The script reaches the breakpoint at the function call.</span></span> <span data-ttu-id="7035b-259">На этом этапе функция еще не вызывалась.</span><span class="sxs-lookup"><span data-stu-id="7035b-259">At this point, the function has not yet been called.</span></span> <span data-ttu-id="7035b-260">Это дает возможность использовать параметр Action в, `Set-PSBreakpoint` чтобы задать условия для выполнения точки останова или выполнить подготовительные или диагностические задачи, такие как запуск журнала или вызов диагностического скрипта или сценария безопасности.</span><span class="sxs-lookup"><span data-stu-id="7035b-260">This gives you the opportunity to use the Action parameter of `Set-PSBreakpoint` to set conditions for the execution of the breakpoint or to perform preparatory or diagnostic tasks, such as starting a log or invoking a diagnostic or security script.</span></span>

<span data-ttu-id="7035b-261">Чтобы задать действие, используйте команду Continue (c), чтобы выйти из скрипта, и `Remove-PsBreakpoint` команду, чтобы удалить текущую точку останова.</span><span class="sxs-lookup"><span data-stu-id="7035b-261">To set an action, use a Continue command (c) to exit the script, and a `Remove-PsBreakpoint` command to delete the current breakpoint.</span></span> <span data-ttu-id="7035b-262">(Точки останова доступны только для чтения, поэтому нельзя добавить действие в текущую точку останова.)</span><span class="sxs-lookup"><span data-stu-id="7035b-262">(Breakpoints are read-only, so you cannot add an action to the current breakpoint.)</span></span>

```powershell
DBG> c
Windows PowerShell 2.0
Have you run a background job today (start-job)?
Done C:\ps-test\test.ps1

PS C:\ps-test> Get-PSBreakpoint| Remove-PSBreakpoint
PS C:\ps-test>
```

<span data-ttu-id="7035b-263">Теперь создайте новую точку останова команды с действием.</span><span class="sxs-lookup"><span data-stu-id="7035b-263">Now, create a new command breakpoint with an action.</span></span> <span data-ttu-id="7035b-264">Следующая команда задает точку останова команды с действием, которое регистрирует значение `$scriptName` переменной при вызове функции.</span><span class="sxs-lookup"><span data-stu-id="7035b-264">The following command sets a command breakpoint with an action that logs the value of the `$scriptName` variable when the function is called.</span></span> <span data-ttu-id="7035b-265">Поскольку ключевое слово Break не используется в действии, выполнение не останавливается.</span><span class="sxs-lookup"><span data-stu-id="7035b-265">Because the Break keyword is not used in the action, execution does not stop.</span></span> <span data-ttu-id="7035b-266">(Обратная кавычка (') — это символ продолжения строки.)</span><span class="sxs-lookup"><span data-stu-id="7035b-266">(The backtick (\`) is the line-continuation character.)</span></span>

```powershell
PS C:\ps-test> Set-PSBreakpoint -command psversion -script test.ps1  `
-action { add-content "The value of `$scriptName is $scriptName." `
-path action.log}
```

<span data-ttu-id="7035b-267">Можно также добавить действия, задаваемые в качестве условий для точки останова.</span><span class="sxs-lookup"><span data-stu-id="7035b-267">You can also add actions that set conditions for the breakpoint.</span></span> <span data-ttu-id="7035b-268">В следующей команде точка останова команды выполняется только в том случае, если для политики выполнения задано значение RemoteSigned, наиболее ограниченная политика, которая по-прежнему позволяет выполнять сценарии.</span><span class="sxs-lookup"><span data-stu-id="7035b-268">In the following command, the command breakpoint is executed only if the execution policy is set to RemoteSigned, the most restrictive policy that still permits you to run scripts.</span></span> <span data-ttu-id="7035b-269">(Обратная кавычка (') — это символ продолжения.)</span><span class="sxs-lookup"><span data-stu-id="7035b-269">(The backtick (\`) is the continuation character.)</span></span>

```powershell
PS C:\ps-test> Set-PSBreakpoint -script test.ps1 -command psversion `
-action { if ((Get-ExecutionPolicy) -eq "RemoteSigned") { break }}
```

<span data-ttu-id="7035b-270">Ключевое слово Break в действии направляет отладчик для выполнения точки останова.</span><span class="sxs-lookup"><span data-stu-id="7035b-270">The Break keyword in the action directs the debugger to execute the breakpoint.</span></span>
<span data-ttu-id="7035b-271">Можно также использовать ключевое слово Continue, чтобы направить отладчик для выполнения без нарушения.</span><span class="sxs-lookup"><span data-stu-id="7035b-271">You can also use the Continue keyword to direct the debugger to execute without breaking.</span></span> <span data-ttu-id="7035b-272">Так как ключевое слово default продолжает выполняться, необходимо указать Break, чтобы остановить выполнение.</span><span class="sxs-lookup"><span data-stu-id="7035b-272">Because the default keyword is Continue, you must specify Break to stop execution.</span></span>

<span data-ttu-id="7035b-273">Теперь запустите сценарий.</span><span class="sxs-lookup"><span data-stu-id="7035b-273">Now, run the script.</span></span>

```powershell
PS C:\ps-test> .\test.ps1
Hit Command breakpoint on 'C:\ps-test\test.ps1:psversion'

test.ps1:12  psversion
```

<span data-ttu-id="7035b-274">Так как для политики выполнения задано значение **RemoteSigned** , выполнение останавливается при вызове функции.</span><span class="sxs-lookup"><span data-stu-id="7035b-274">Because the execution policy is set to **RemoteSigned** , execution stops at the function call.</span></span>

<span data-ttu-id="7035b-275">На этом этапе может потребоваться проверить стек вызовов.</span><span class="sxs-lookup"><span data-stu-id="7035b-275">At this point, you might want to check the call stack.</span></span> <span data-ttu-id="7035b-276">Используйте `Get-PsCallStack` командлет или `Get-PsCallStack` команду отладчика (k).</span><span class="sxs-lookup"><span data-stu-id="7035b-276">Use the `Get-PsCallStack` cmdlet or the `Get-PsCallStack` debugger command (k).</span></span> <span data-ttu-id="7035b-277">Следующая команда возвращает текущий стек вызовов.</span><span class="sxs-lookup"><span data-stu-id="7035b-277">The following command gets the current call stack.</span></span>

```powershell
DBG> k
2: prompt
1: .\test.ps1: $args=[]
0: prompt: $args=[]
```

<span data-ttu-id="7035b-278">В этом примере демонстрируется лишь несколько способов использования отладчика PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7035b-278">This example demonstrates just a few of the many ways to use the PowerShell debugger.</span></span>

<span data-ttu-id="7035b-279">Чтобы получить дополнительные сведения о командлетах отладчика, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="7035b-279">For more information about the debugger cmdlets, type the following command:</span></span>

```powershell
help <cmdlet-name> -full
```

<span data-ttu-id="7035b-280">Например, введите:</span><span class="sxs-lookup"><span data-stu-id="7035b-280">For example, type:</span></span>

```powershell
help Set-PSBreakpoint -full
```

## <a name="other-debugging-features-in-powershell"></a><span data-ttu-id="7035b-281">Другие функции отладки в PowerShell</span><span class="sxs-lookup"><span data-stu-id="7035b-281">Other Debugging Features in PowerShell</span></span>

<span data-ttu-id="7035b-282">Помимо отладчика PowerShell, в PowerShell есть несколько других функций, которые можно использовать для отладки скриптов и функций.</span><span class="sxs-lookup"><span data-stu-id="7035b-282">In addition to the PowerShell debugger, PowerShell includes several other features that you can use to debug scripts and functions.</span></span>

- <span data-ttu-id="7035b-283">Интегрированная среда сценариев Windows PowerShell включает в себя интерактивный графический отладчик.</span><span class="sxs-lookup"><span data-stu-id="7035b-283">Windows PowerShell ISE includes an interactive graphical debugger.</span></span> <span data-ttu-id="7035b-284">Для получения дополнительных сведений запустите интегрированную среду сценариев Windows PowerShell и нажмите клавишу F1.</span><span class="sxs-lookup"><span data-stu-id="7035b-284">For more information, start Windows PowerShell ISE and press F1.</span></span>

- <span data-ttu-id="7035b-285">`Set-PSDebug`Командлет предлагает самые базовые функции отладки скриптов, включая пошаговое выполнение и трассировку.</span><span class="sxs-lookup"><span data-stu-id="7035b-285">The `Set-PSDebug` cmdlet offers very basic script debugging features, including stepping and tracing.</span></span>

- <span data-ttu-id="7035b-286">Используйте `Set-StrictMode` командлет, чтобы обнаружить ссылки на неинициализированные переменные, ссылки на несуществующие свойства объекта и на недопустимый синтаксис функции.</span><span class="sxs-lookup"><span data-stu-id="7035b-286">Use the `Set-StrictMode` cmdlet to detect references to uninitialized variables, to references to non-existent properties of an object, and to function syntax that is not valid.</span></span>

- <span data-ttu-id="7035b-287">Добавьте в скрипт диагностические инструкции, например инструкции, отображающие значения переменных, инструкции, считывающие входные данные из командной строки, или инструкции, сообщающие о текущей инструкции.</span><span class="sxs-lookup"><span data-stu-id="7035b-287">Add diagnostic statements to a script, such as statements that display the value of variables, statements that read input from the command line, or statements that report the current instruction.</span></span> <span data-ttu-id="7035b-288">Используйте командлеты, которые содержат команду записи для этой задачи, например `Write-Host` ,, `Write-Debug` `Write-Warning` и `Write-Verbose` .</span><span class="sxs-lookup"><span data-stu-id="7035b-288">Use the cmdlets that contain the Write verb for this task, such as `Write-Host`, `Write-Debug`, `Write-Warning`, and `Write-Verbose`.</span></span>

## <a name="see-also"></a><span data-ttu-id="7035b-289">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="7035b-289">SEE ALSO</span></span>

- [<span data-ttu-id="7035b-290">Disable-PsBreakpoint</span><span class="sxs-lookup"><span data-stu-id="7035b-290">Disable-PsBreakpoint</span></span>](xref:Microsoft.PowerShell.Utility.Disable-PSBreakpoint)
- [<span data-ttu-id="7035b-291">Enable-PsBreakpoint</span><span class="sxs-lookup"><span data-stu-id="7035b-291">Enable-PsBreakpoint</span></span>](xref:Microsoft.PowerShell.Utility.Enable-PSBreakpoint)
- [<span data-ttu-id="7035b-292">Get-PsBreakpoint</span><span class="sxs-lookup"><span data-stu-id="7035b-292">Get-PsBreakpoint</span></span>](xref:Microsoft.PowerShell.Utility.Get-PSBreakpoint)
- [<span data-ttu-id="7035b-293">Get-PsCallStack</span><span class="sxs-lookup"><span data-stu-id="7035b-293">Get-PsCallStack</span></span>](xref:Microsoft.PowerShell.Utility.Get-PSCallStack)
- [<span data-ttu-id="7035b-294">Remove-PsBreakpoint</span><span class="sxs-lookup"><span data-stu-id="7035b-294">Remove-PsBreakpoint</span></span>](xref:Microsoft.PowerShell.Utility.Remove-PSBreakpoint)
- [<span data-ttu-id="7035b-295">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="7035b-295">Set-PSBreakpoint</span></span>](xref:Microsoft.PowerShell.Utility.Set-PSBreakpoint)
- [<span data-ttu-id="7035b-296">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="7035b-296">Write-Debug</span></span>](xref:Microsoft.PowerShell.Utility.Write-Debug)
- [<span data-ttu-id="7035b-297">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="7035b-297">Write-Verbose</span></span>](xref:Microsoft.PowerShell.Utility.Write-Verbose)
