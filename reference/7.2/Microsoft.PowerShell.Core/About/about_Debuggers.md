---
description: Описывает отладчик PowerShell.
Locale: en-US
ms.date: 08/06/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_debuggers?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Debuggers
ms.openlocfilehash: 46914937cebdf8cf3559371f354bf14cd6706115
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604495"
---
# <a name="about-debuggers"></a><span data-ttu-id="45441-103">О отладчиках</span><span class="sxs-lookup"><span data-stu-id="45441-103">About Debuggers</span></span>

## <a name="short-description"></a><span data-ttu-id="45441-104">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="45441-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="45441-105">Описывает отладчик PowerShell.</span><span class="sxs-lookup"><span data-stu-id="45441-105">Describes the PowerShell debugger.</span></span>

## <a name="long-description"></a><span data-ttu-id="45441-106">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="45441-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="45441-107">Отладка — это процесс проверки сценария во время его выполнения для обнаружения и исправления ошибок в инструкциях сценария.</span><span class="sxs-lookup"><span data-stu-id="45441-107">Debugging is the process of examining a script while it is running to identify and correct errors in the script instructions.</span></span> <span data-ttu-id="45441-108">Отладчик PowerShell помогает исследовать и выявление ошибок и неэффективности в скриптах, функциях, командах, конфигурациях и выражениях настройки требуемого состояния (DSC) PowerShell.</span><span class="sxs-lookup"><span data-stu-id="45441-108">The PowerShell debugger can help you examine and identify errors and inefficiencies in your scripts, functions, commands, PowerShell Desired State Configuration (DSC) configurations, or expressions.</span></span>

<span data-ttu-id="45441-109">Начиная с PowerShell 5,0, отладчик PowerShell был обновлен для отладки скриптов, функций, команд, конфигураций или выражений, которые выполняются в консоли или в интегрированной среде сценариев Windows PowerShell на удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="45441-109">Starting in PowerShell 5.0, the PowerShell debugger has been updated to debug scripts, functions, commands, configurations, or expressions that are running in either the console or Windows PowerShell ISE on remote computers.</span></span> <span data-ttu-id="45441-110">Вы можете запустить `Enter-PSSession` Интерактивный удаленный сеанс PowerShell, в котором можно задать точки останова и выполнять отладку файлов сценариев и команд на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="45441-110">You can run `Enter-PSSession` to start an interactive remote PowerShell session in which you can set breakpoints and debug script files and commands on the remote computer.</span></span> <span data-ttu-id="45441-111">`Enter-PSSession` Обновлены функциональные возможности, которые позволяют повторно подключиться к и ввести отключенный сеанс, выполняющий сценарий или команду на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="45441-111">`Enter-PSSession` functionality has been updated to let you reconnect to and enter a disconnected session that is running a script or command on a remote computer.</span></span> <span data-ttu-id="45441-112">Если выполняемый скрипт достигает точки останова, ваш сеанс клиента автоматически запускает отладчик.</span><span class="sxs-lookup"><span data-stu-id="45441-112">If the running script hits a breakpoint, your client session automatically starts the debugger.</span></span> <span data-ttu-id="45441-113">Если отключенный сеанс, в котором выполняется скрипт, уже вызвал точку останова и остановлен в точке останова, `Enter-PSSession` автоматически запускает отладчик командной строки после повторного подключения к сеансу.</span><span class="sxs-lookup"><span data-stu-id="45441-113">If the disconnected session that is running a script has already hit a breakpoint, and is stopped at the breakpoint, `Enter-PSSession` automatically starts the command-line debugger, after you reconnect to the session.</span></span>

<span data-ttu-id="45441-114">Функции отладчика PowerShell можно использовать для проверки сценария, функции, команды или выражения PowerShell во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="45441-114">You can use the features of the PowerShell debugger to examine a PowerShell script, function, command, or expression while it is running.</span></span> <span data-ttu-id="45441-115">Отладчик PowerShell включает набор командлетов, позволяющих задавать точки останова, управлять точками останова и просматривать стек вызовов.</span><span class="sxs-lookup"><span data-stu-id="45441-115">The PowerShell debugger includes a set of cmdlets that let you set breakpoints, manage breakpoints, and view the call stack.</span></span>

## <a name="debugger-cmdlets"></a><span data-ttu-id="45441-116">Командлеты отладчика</span><span class="sxs-lookup"><span data-stu-id="45441-116">Debugger Cmdlets</span></span>

<span data-ttu-id="45441-117">Отладчик PowerShell включает следующий набор командлетов:</span><span class="sxs-lookup"><span data-stu-id="45441-117">The PowerShell debugger includes the following set of cmdlets:</span></span>

- <span data-ttu-id="45441-118">`Set-PSBreakpoint`: Задает точки останова в строках, переменных и командах.</span><span class="sxs-lookup"><span data-stu-id="45441-118">`Set-PSBreakpoint`: Sets breakpoints on lines, variables, and commands.</span></span>
- <span data-ttu-id="45441-119">`Get-PSBreakpoint`: Возвращает точки останова в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="45441-119">`Get-PSBreakpoint`: Gets breakpoints in the current session.</span></span>
- <span data-ttu-id="45441-120">`Disable-PSBreakpoint`: Отключает точки останова в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="45441-120">`Disable-PSBreakpoint`: Turns off breakpoints in the current session.</span></span>
- <span data-ttu-id="45441-121">`Enable-PSBreakpoint`: Повторное включение точек останова в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="45441-121">`Enable-PSBreakpoint`: Re-enables breakpoints in the current session.</span></span>
- <span data-ttu-id="45441-122">`Remove-PSBreakpoint`: Удаляет точки останова из текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="45441-122">`Remove-PSBreakpoint`: Deletes breakpoints from the current session.</span></span>
- <span data-ttu-id="45441-123">`Get-PSCallStack`: Отображает текущий стек вызовов.</span><span class="sxs-lookup"><span data-stu-id="45441-123">`Get-PSCallStack`: Displays the current call stack.</span></span>

## <a name="starting-and-stopping-the-debugger"></a><span data-ttu-id="45441-124">Запуск и остановка отладчика</span><span class="sxs-lookup"><span data-stu-id="45441-124">Starting and Stopping the Debugger</span></span>

<span data-ttu-id="45441-125">Чтобы запустить отладчик, задайте одну или несколько точек останова.</span><span class="sxs-lookup"><span data-stu-id="45441-125">To start the debugger, set one or more breakpoints.</span></span> <span data-ttu-id="45441-126">Затем запустите скрипт, команду или функцию, которые требуется отладить.</span><span class="sxs-lookup"><span data-stu-id="45441-126">Then, run the script, command, or function that you want to debug.</span></span>

<span data-ttu-id="45441-127">При достижении точки останова выполнение останавливается и управление передается отладчику.</span><span class="sxs-lookup"><span data-stu-id="45441-127">When you reach a breakpoint, execution stops, and control is turned over to the debugger.</span></span>

<span data-ttu-id="45441-128">Чтобы завершить работу отладчика, выполните сценарий, команду или функцию, пока она не будет завершена.</span><span class="sxs-lookup"><span data-stu-id="45441-128">To stop the debugger, run the script, command, or function until it is complete.</span></span> <span data-ttu-id="45441-129">Или введите `stop` или `t` .</span><span class="sxs-lookup"><span data-stu-id="45441-129">Or, type `stop` or `t`.</span></span>

### <a name="debugger-commands"></a><span data-ttu-id="45441-130">Команды отладчика</span><span class="sxs-lookup"><span data-stu-id="45441-130">Debugger Commands</span></span>

<span data-ttu-id="45441-131">При использовании отладчика в консоли PowerShell используйте следующие команды для управления выполнением.</span><span class="sxs-lookup"><span data-stu-id="45441-131">When you use the debugger in the PowerShell console, use the following commands to control the execution.</span></span> <span data-ttu-id="45441-132">В интегрированной среде сценариев Windows PowerShell используйте команды в меню Отладка.</span><span class="sxs-lookup"><span data-stu-id="45441-132">In Windows PowerShell ISE, use commands on the Debug menu.</span></span>

<span data-ttu-id="45441-133">Примечание. сведения об использовании отладчика в других ведущих приложениях см. в документации по ведущему приложению.</span><span class="sxs-lookup"><span data-stu-id="45441-133">Note: For information about how to use the debugger in other host applications, see the host application documentation.</span></span>

- <span data-ttu-id="45441-134">`s`, `StepInto` : Выполняет следующий оператор, а затем останавливается.</span><span class="sxs-lookup"><span data-stu-id="45441-134">`s`, `StepInto`: Executes the next statement and then stops.</span></span>

- <span data-ttu-id="45441-135">`v`, `StepOver` : Выполняет следующий оператор, но пропускает функции и вызовы.</span><span class="sxs-lookup"><span data-stu-id="45441-135">`v`, `StepOver`: Executes the next statement, but skips functions and invocations.</span></span> <span data-ttu-id="45441-136">Пропущенные операторы выполняются, но в них отладчик не останавливается.</span><span class="sxs-lookup"><span data-stu-id="45441-136">The skipped statements are executed, but not stepped through.</span></span>

- <span data-ttu-id="45441-137">`Ctrl+Break`(Разбейте все в ISE) на выполнение сценария в консоли PowerShell или ИНТЕГРИРОВАНной среде сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="45441-137">`Ctrl+Break`: (Break All in ISE) Breaks into a running script within either the PowerShell console, or Windows PowerShell ISE.</span></span> <span data-ttu-id="45441-138">Обратите <kbd></kbd>внимание, что + <kbd>разрыв</kbd> CTRL в Windows PowerShell 2,0, 3,0 и 4,0 закрывает программу.</span><span class="sxs-lookup"><span data-stu-id="45441-138">Note that <kbd>Ctrl</kbd>+<kbd>Break</kbd> in Windows PowerShell 2.0, 3.0, and 4.0 closes the program.</span></span> <span data-ttu-id="45441-139">Прерывать все работает как с локальными, так и с удаленными интерактивными сценариями.</span><span class="sxs-lookup"><span data-stu-id="45441-139">Break All works on both local and remote interactively-running scripts.</span></span>

- <span data-ttu-id="45441-140">`o`, `StepOut` : Действия из текущей функции; на один уровень вверх при вложении.</span><span class="sxs-lookup"><span data-stu-id="45441-140">`o`, `StepOut`: Steps out of the current function; up one level if nested.</span></span> <span data-ttu-id="45441-141">Если в основном тексте, он переходит к концу или следующей точке останова.</span><span class="sxs-lookup"><span data-stu-id="45441-141">If in the main body, it continues to the end or the next breakpoint.</span></span> <span data-ttu-id="45441-142">Пропущенные операторы выполняются, но в них отладчик не останавливается.</span><span class="sxs-lookup"><span data-stu-id="45441-142">The skipped statements are executed, but not stepped through.</span></span>

- <span data-ttu-id="45441-143">`c`, `Continue` : Продолжит работу до завершения скрипта или до достижения следующей точки останова.</span><span class="sxs-lookup"><span data-stu-id="45441-143">`c`, `Continue`: Continues to run until the script is complete or until the next breakpoint is reached.</span></span> <span data-ttu-id="45441-144">Пропущенные операторы выполняются, но в них отладчик не останавливается.</span><span class="sxs-lookup"><span data-stu-id="45441-144">The skipped statements are executed, but not stepped through.</span></span>

- <span data-ttu-id="45441-145">`l`, `List` : Отображает часть скрипта, который исполняется.</span><span class="sxs-lookup"><span data-stu-id="45441-145">`l`, `List`: Displays the part of the script that is executing.</span></span> <span data-ttu-id="45441-146">По умолчанию отображается текущая строка, пять предыдущих строк и 10 последующих строк.</span><span class="sxs-lookup"><span data-stu-id="45441-146">By default, it displays the current line, five previous lines, and 10 subsequent lines.</span></span>
  <span data-ttu-id="45441-147">Чтобы продолжить составление списка сценариев, нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="45441-147">To continue listing the script, press ENTER.</span></span>

- <span data-ttu-id="45441-148">`l <m>`, `List` : Отображает 16 строк сценария, начиная с номера строки, заданного параметром `<m>` .</span><span class="sxs-lookup"><span data-stu-id="45441-148">`l <m>`, `List`: Displays 16 lines of the script beginning with the line number specified by `<m>`.</span></span>

- <span data-ttu-id="45441-149">`l <m> <n>`, `List` : Отображает `<n>` строки скрипта, начиная с номера строки, заданного параметром `<m>` .</span><span class="sxs-lookup"><span data-stu-id="45441-149">`l <m> <n>`, `List`: Displays `<n>` lines of the script, beginning with the line number specified by `<m>`.</span></span>

- <span data-ttu-id="45441-150">`q`, `Stop` , `Exit` : Останавливает выполнение скрипта и завершает работу отладчика.</span><span class="sxs-lookup"><span data-stu-id="45441-150">`q`, `Stop`, `Exit`: Stops executing the script, and exits the debugger.</span></span> <span data-ttu-id="45441-151">Если выполняется отладка задания с помощью `Debug-Job` командлета, `Exit` команда отсоединяет отладчик и позволяет продолжить выполнение задания.</span><span class="sxs-lookup"><span data-stu-id="45441-151">If you are debugging a job by running the `Debug-Job` cmdlet, the `Exit` command detaches the debugger, and allows the job to continue running.</span></span>

- <span data-ttu-id="45441-152">`k`, `Get-PsCallStack` : Отображает текущий стек вызовов.</span><span class="sxs-lookup"><span data-stu-id="45441-152">`k`, `Get-PsCallStack`: Displays the current call stack.</span></span>

- <span data-ttu-id="45441-153">`<Enter>`: Повторяет последнюю команду, если она была на шаге (-ов), Степовер (v) или List (l).</span><span class="sxs-lookup"><span data-stu-id="45441-153">`<Enter>`: Repeats the last command if it was Step (s), StepOver (v), or List (l).</span></span> <span data-ttu-id="45441-154">В противном случае представляет действие отправки.</span><span class="sxs-lookup"><span data-stu-id="45441-154">Otherwise, represents a submit action.</span></span>

- <span data-ttu-id="45441-155">`?`, `h` : Отображает справку по командам отладчика.</span><span class="sxs-lookup"><span data-stu-id="45441-155">`?`, `h`: Displays the debugger command Help.</span></span>

<span data-ttu-id="45441-156">Чтобы выйти из отладчика, можно использовать команду «прекратить» (q).</span><span class="sxs-lookup"><span data-stu-id="45441-156">To exit the debugger, you can use Stop (q).</span></span>

<span data-ttu-id="45441-157">Начиная с PowerShell 5,0 можно выполнить команду Exit, чтобы выйти из вложенного сеанса отладки, запущенного с помощью команды `Debug-Job` или `Debug-Runspace` .</span><span class="sxs-lookup"><span data-stu-id="45441-157">Starting in PowerShell 5.0, you can run the Exit command to exit a nested debugging session that you started by running either `Debug-Job` or `Debug-Runspace`.</span></span>

<span data-ttu-id="45441-158">С помощью этих команд отладчика можно выполнять сценарий, останавливаться на определенном этапе, проверять значения переменных и состояния системы и продолжать выполнение сценария до тех пор, пока не будет выявлена проблема.</span><span class="sxs-lookup"><span data-stu-id="45441-158">By using these debugger commands, you can run a script, stop on a point of concern, examine the values of variables and the state of the system, and continue running the script until you have identified a problem.</span></span>

<span data-ttu-id="45441-159">Примечание. при переходе к оператору с оператором перенаправления, например ">", отладчик PowerShell выполняет шаг над всеми остальными инструкциями в скрипте.</span><span class="sxs-lookup"><span data-stu-id="45441-159">NOTE: If you step into a statement with a redirection operator, such as ">", the PowerShell debugger steps over all remaining statements in the script.</span></span>

<span data-ttu-id="45441-160">Отображение значений переменных скрипта</span><span class="sxs-lookup"><span data-stu-id="45441-160">Displaying the Values of script Variables</span></span>

<span data-ttu-id="45441-161">В отладчике можно также вводить команды, отображать значения переменных, использовать командлеты и выполнять сценарии в командной строке.</span><span class="sxs-lookup"><span data-stu-id="45441-161">While you are in the debugger, you can also enter commands, display the value of variables, use cmdlets, and run scripts at the command line.</span></span>

<span data-ttu-id="45441-162">Можно отобразить текущее значение всех переменных в отлаживаемом скрипте, за исключением следующих автоматических переменных:</span><span class="sxs-lookup"><span data-stu-id="45441-162">You can display the current value of all variables in the script that is being debugged, except for the following automatic variables:</span></span>

```powershell
$_
$Args
$Input
$MyInvocation
$PSBoundParameters
```

<span data-ttu-id="45441-163">При попытке отобразить значение любой из этих переменных отображается значение переменной из внутреннего конвейера отладчика, а не переменной в сценарии.</span><span class="sxs-lookup"><span data-stu-id="45441-163">If you try to display the value of any of these variables, you get the value of that variable for in an internal pipeline the debugger uses, not the value of the variable in the script.</span></span>

<span data-ttu-id="45441-164">Чтобы отобразить значения этих переменных для отлаживаемого скрипта, в скрипте присвойте значение автоматически изменяемой переменной новой переменной.</span><span class="sxs-lookup"><span data-stu-id="45441-164">To display the value these variables for the script that is being debugged, in the script, assign the value of the automatic variable to a new variable.</span></span> <span data-ttu-id="45441-165">Затем можно отобразить значение новой переменной.</span><span class="sxs-lookup"><span data-stu-id="45441-165">Then you can display the value of the new variable.</span></span>

<span data-ttu-id="45441-166">Например,</span><span class="sxs-lookup"><span data-stu-id="45441-166">For example,</span></span>

```powershell
$scriptArgs = $Args
$scriptArgs
```

<span data-ttu-id="45441-167">В примере в этом разделе значение `$MyInvocation` переменной переназначается следующим образом:</span><span class="sxs-lookup"><span data-stu-id="45441-167">In the example in this topic, the value of the `$MyInvocation` variable is reassigned as follows:</span></span>

```powershell
$scriptname = $MyInvocation.MyCommand.Path
```

## <a name="the-debugger-environment"></a><span data-ttu-id="45441-168">Среда отладчика</span><span class="sxs-lookup"><span data-stu-id="45441-168">The Debugger Environment</span></span>

<span data-ttu-id="45441-169">При достижении точки останова вы вводите среду отладчика.</span><span class="sxs-lookup"><span data-stu-id="45441-169">When you reach a breakpoint, you enter the debugger environment.</span></span> <span data-ttu-id="45441-170">Командная строка изменится так, чтобы она начиналась с "[DBG]:".</span><span class="sxs-lookup"><span data-stu-id="45441-170">The command prompt changes so that it begins with "[DBG]:".</span></span>

<span data-ttu-id="45441-171">Дополнительные сведения о настройке командной строки см. в разделе [about_Prompts](about_prompts.md).</span><span class="sxs-lookup"><span data-stu-id="45441-171">For more information about customizing the prompt, see [about_Prompts](about_prompts.md).</span></span>

<span data-ttu-id="45441-172">Кроме того, в некоторых ведущих приложениях, таких как консоль PowerShell (но не в интегрированной среде сценариев Windows PowerShell [ISE]), для отладки открывается вложенный запрос.</span><span class="sxs-lookup"><span data-stu-id="45441-172">Also, in some host applications, such as the PowerShell console, (but not in Windows PowerShell Integrated Scripting Environment [ISE]), a nested prompt opens for debugging.</span></span> <span data-ttu-id="45441-173">Вложенные запросы можно обнаружить по повторяющимся символам "больше чем" (ASCII 62), которые отображаются в командной строке.</span><span class="sxs-lookup"><span data-stu-id="45441-173">You can detect the nested prompt by the repeating greater-than characters (ASCII 62) that appear at the command prompt.</span></span>

<span data-ttu-id="45441-174">Например, в консоли PowerShell по умолчанию используется следующая строка отладки:</span><span class="sxs-lookup"><span data-stu-id="45441-174">For example, the following is the default debugging prompt in the PowerShell console:</span></span>

```
[DBG]: PS (get-location)>>>
```

<span data-ttu-id="45441-175">Уровень вложенности можно найти с помощью `$NestedPromptLevel` автоматической переменной.</span><span class="sxs-lookup"><span data-stu-id="45441-175">You can find the nesting level by using the `$NestedPromptLevel` automatic variable.</span></span>

<span data-ttu-id="45441-176">Кроме того, `$PSDebugContext` в локальной области определена автоматическая переменная,.</span><span class="sxs-lookup"><span data-stu-id="45441-176">Additionally, an automatic variable, `$PSDebugContext`, is defined in the local scope.</span></span> <span data-ttu-id="45441-177">Наличие переменной можно использовать `$PsDebugContext` для определения того, находится ли вы в отладчике.</span><span class="sxs-lookup"><span data-stu-id="45441-177">You can use the presence of the `$PsDebugContext` variable to determine whether you are in the debugger.</span></span>

<span data-ttu-id="45441-178">Пример:</span><span class="sxs-lookup"><span data-stu-id="45441-178">For example:</span></span>

```powershell
if ($PSDebugContext) {"Debugging"} else {"Not Debugging"}
```

<span data-ttu-id="45441-179">Значение переменной можно использовать `$PSDebugContext` в отладке.</span><span class="sxs-lookup"><span data-stu-id="45441-179">You can use the value of the `$PSDebugContext` variable in your debugging.</span></span>

```
[DBG]: PS>>> $PSDebugContext.InvocationInfo

Name   CommandLineParameters  UnboundArguments  Location
----   ---------------------  ----------------  --------
=      {}                     {}                C:\ps-test\vote.ps1 (1)
```

## <a name="debugging-and-scope"></a><span data-ttu-id="45441-180">Отладка и область</span><span class="sxs-lookup"><span data-stu-id="45441-180">Debugging and Scope</span></span>

<span data-ttu-id="45441-181">Переход в отладчик не влияет на область, в которой работает, но при достижении точки останова в скрипте вы переходите в область скрипта.</span><span class="sxs-lookup"><span data-stu-id="45441-181">Breaking into the debugger does not change the scope in which you are operating, but when you reach a breakpoint in a script, you move into the script scope.</span></span> <span data-ttu-id="45441-182">Область скрипта является дочерней для области, в которой запущен отладчик.</span><span class="sxs-lookup"><span data-stu-id="45441-182">The script scope is a child of the scope in which you ran the debugger.</span></span>

<span data-ttu-id="45441-183">Чтобы найти переменные и псевдонимы, определенные в области скрипта, используйте параметр scope `Get-Alias` `Get-Variable` командлета или.</span><span class="sxs-lookup"><span data-stu-id="45441-183">To find the variables and aliases that are defined in the script scope, use the Scope parameter of the `Get-Alias` or `Get-Variable` cmdlets.</span></span>

<span data-ttu-id="45441-184">Например, следующая команда получает переменные в локальной области (скрипт):</span><span class="sxs-lookup"><span data-stu-id="45441-184">For example, the following command gets the variables in the local (script) scope:</span></span>

```powershell
Get-Variable -scope 0
```

<span data-ttu-id="45441-185">Вы можете сократить команду следующим образом:</span><span class="sxs-lookup"><span data-stu-id="45441-185">You can abbreviate the command as:</span></span>

```powershell
gv -s 0
```

<span data-ttu-id="45441-186">Это удобный способ просмотра только переменных, определенных в скрипте и определенных во время отладки.</span><span class="sxs-lookup"><span data-stu-id="45441-186">This is a useful way to see only the variables that you defined in the script and that you defined while debugging.</span></span>

<span data-ttu-id="45441-187">Отладка в командной строке</span><span class="sxs-lookup"><span data-stu-id="45441-187">Debugging at the Command Line</span></span>

<span data-ttu-id="45441-188">При установке точки останова переменной или точки останова команды можно задать точку останова только в файле скрипта.</span><span class="sxs-lookup"><span data-stu-id="45441-188">When you set a variable breakpoint or a command breakpoint, you can set the breakpoint only in a script file.</span></span> <span data-ttu-id="45441-189">Однако по умолчанию точка останова устанавливается для любого, который выполняется в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="45441-189">However, by default, the breakpoint is set on anything that runs in the current session.</span></span>

<span data-ttu-id="45441-190">Например, если задать точку останова в `$name` переменной, отладчик остановится на любой `$name` переменной в любом скрипте, команде, функции, командлете или выражении, которое выполняется до отключения или удаления точки останова.</span><span class="sxs-lookup"><span data-stu-id="45441-190">For example, if you set a breakpoint on the `$name` variable, the debugger breaks on any `$name` variable in any script, command, function, script cmdlet or expression that you run until you disable or remove the breakpoint.</span></span>

<span data-ttu-id="45441-191">Это позволяет выполнять отладку скриптов в более реалистичном контексте, в котором они могут зависеть от функций, переменных и других сценариев в сеансе и в профиле пользователя.</span><span class="sxs-lookup"><span data-stu-id="45441-191">This allows you to debug your scripts in a more realistic context in which they might be affected by functions, variables, and other scripts in the session and in the user's profile.</span></span>

<span data-ttu-id="45441-192">Точки останова строки зависят от файлов скриптов, поэтому они задаются только в файлах скриптов.</span><span class="sxs-lookup"><span data-stu-id="45441-192">Line breakpoints are specific to script files, so they are set only in script files.</span></span>

## <a name="debugging-functions"></a><span data-ttu-id="45441-193">Функции отладки</span><span class="sxs-lookup"><span data-stu-id="45441-193">Debugging Functions</span></span>

<span data-ttu-id="45441-194">При установке точки останова в функции, которая содержит `Begin` `Process` разделы, и `End` , отладчик прерывает выполнение в первой строке каждого раздела.</span><span class="sxs-lookup"><span data-stu-id="45441-194">When you set a breakpoint on a function that has `Begin`, `Process`, and `End` sections, the debugger breaks at the first line of each section.</span></span>

<span data-ttu-id="45441-195">Пример:</span><span class="sxs-lookup"><span data-stu-id="45441-195">For example:</span></span>

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

## <a name="debugging-remote-scripts"></a><span data-ttu-id="45441-196">Отладка удаленных скриптов</span><span class="sxs-lookup"><span data-stu-id="45441-196">Debugging Remote Scripts</span></span>

<span data-ttu-id="45441-197">Начиная с PowerShell 5,0 можно запустить отладчик PowerShell в удаленном сеансе, в консоли или в интегрированной среде сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="45441-197">Starting in PowerShell 5.0, you can run the PowerShell debugger in a remote session, in either the console, or Windows PowerShell ISE.</span></span>
<span data-ttu-id="45441-198">`Enter-PSSession` были обновлены функциональные возможности для повторного подключения к и входа в отключенный сеанс, запущенный на удаленном компьютере, и в данный момент выполняется сценарий.</span><span class="sxs-lookup"><span data-stu-id="45441-198">`Enter-PSSession` functionality has been updated to let you reconnect to and enter a disconnected session that is running on a remote computer, and currently running a script.</span></span> <span data-ttu-id="45441-199">Если выполняемый скрипт достигает точки останова, ваш сеанс клиента автоматически запускает отладчик.</span><span class="sxs-lookup"><span data-stu-id="45441-199">If the running script hits a breakpoint, your client session automatically starts the debugger.</span></span>

<span data-ttu-id="45441-200">Ниже приведен пример, в котором показано, как это работает, с точками останова, заданными в скрипте в строках 6, 11, 22 и 25.</span><span class="sxs-lookup"><span data-stu-id="45441-200">The following is an example that shows how this works, with breakpoints set in a script at lines 6, 11, 22, and 25.</span></span> <span data-ttu-id="45441-201">Обратите внимание, что в примере при запуске отладчика есть два идентифицирующих приглашения: имя компьютера, на котором выполняется сеанс, и запрос DBG, который позволяет убедиться в том, что вы работаете в режиме отладки.</span><span class="sxs-lookup"><span data-stu-id="45441-201">Note that in the example, when the debugger starts, there are two identifying prompts: the name of the computer on which the session is running, and the DBG prompt that lets you know you are in debugging mode.</span></span>

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

## <a name="examples"></a><span data-ttu-id="45441-202">Примеры</span><span class="sxs-lookup"><span data-stu-id="45441-202">Examples</span></span>

<span data-ttu-id="45441-203">Этот сценарий тестирования обнаруживает версию операционной системы и отображает сообщение, соответствующее системе.</span><span class="sxs-lookup"><span data-stu-id="45441-203">This test script detects the version of the operating system and displays a system-appropriate message.</span></span> <span data-ttu-id="45441-204">Он включает функцию, вызов функции и переменную.</span><span class="sxs-lookup"><span data-stu-id="45441-204">It includes a function, a function call, and a variable.</span></span>

<span data-ttu-id="45441-205">Следующая команда отображает содержимое файла скрипта теста:</span><span class="sxs-lookup"><span data-stu-id="45441-205">The following command displays the contents of the test script file:</span></span>

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

<span data-ttu-id="45441-206">Для начала установите точку останова в определенном месте скрипта, например в строке, команде, переменной или функции.</span><span class="sxs-lookup"><span data-stu-id="45441-206">To start, set a breakpoint at a point of interest in the script, such as a line, command, variable, or function.</span></span>

<span data-ttu-id="45441-207">Начните с создания точки останова строки в первой строке скрипта Test.ps1 в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="45441-207">Start by creating a line breakpoint on the first line of the Test.ps1 script in the current directory.</span></span>

```powershell
PS C:\ps-test> Set-PSBreakpoint -line 1 -script test.ps1
```

<span data-ttu-id="45441-208">Данную команду можно сократить следующим образом:</span><span class="sxs-lookup"><span data-stu-id="45441-208">You can abbreviate this command as:</span></span>

```powershell
PS C:\ps-test> spb 1 -s test.ps1
```

<span data-ttu-id="45441-209">Команда возвращает объект точки останова строки (**System. Management. Automation. линебреакпоинт**).</span><span class="sxs-lookup"><span data-stu-id="45441-209">The command returns a line-breakpoint object (**System.Management.Automation.LineBreakpoint**).</span></span>

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

<span data-ttu-id="45441-210">Теперь запустите сценарий.</span><span class="sxs-lookup"><span data-stu-id="45441-210">Now, start the script.</span></span>

```powershell
PS C:\ps-test> .\test.ps1
```

<span data-ttu-id="45441-211">Когда скрипт достигает первой точки останова, сообщение точки останова указывает на то, что отладчик активен.</span><span class="sxs-lookup"><span data-stu-id="45441-211">When the script reaches the first breakpoint, the breakpoint message indicates that the debugger is active.</span></span> <span data-ttu-id="45441-212">Он описывает точку останова и предварительный просмотр первой строки скрипта, которая является объявлением функции.</span><span class="sxs-lookup"><span data-stu-id="45441-212">It describes the breakpoint and previews the first line of the script, which is a function declaration.</span></span> <span data-ttu-id="45441-213">Командная строка также изменится, указывая, что отладчик имеет элемент управления.</span><span class="sxs-lookup"><span data-stu-id="45441-213">The command prompt also changes to indicate that the debugger has control.</span></span>

<span data-ttu-id="45441-214">В строке предварительного просмотра содержится имя скрипта и номер строки предварительно просматриваемой команды.</span><span class="sxs-lookup"><span data-stu-id="45441-214">The preview line includes the script name and the line number of the previewed command.</span></span>

```powershell
Entering debug mode. Use h or ? for help.

Hit Line breakpoint on 'C:\ps-test\test.ps1:1'

test.ps1:1   function psversion {
# DBG>
```

<span data-ttu-id="45441-215">Используйте команды step, чтобы выполнить первый оператор в скрипте и просмотреть следующий оператор.</span><span class="sxs-lookup"><span data-stu-id="45441-215">Use the Step command (s) to execute the first statement in the script and to preview the next statement.</span></span> <span data-ttu-id="45441-216">Следующая инструкция использует `$MyInvocation` автоматическую переменную, чтобы установить значение `$scriptName` переменной в качестве пути и имени файла скрипта.</span><span class="sxs-lookup"><span data-stu-id="45441-216">The next statement uses the `$MyInvocation` automatic variable to set the value of the `$scriptName` variable to the path and file name of the script file.</span></span>

```powershell
DBG> s
test.ps1:11  $scriptName = $MyInvocation.MyCommand.Path
```

<span data-ttu-id="45441-217">На этом этапе `$scriptName` переменная не заполняется, но можно проверить значение переменной, отображая ее значение.</span><span class="sxs-lookup"><span data-stu-id="45441-217">At this point, the `$scriptName` variable is not populated, but you can verify the value of the variable by displaying its value.</span></span> <span data-ttu-id="45441-218">В этом случае используется значение `$null`.</span><span class="sxs-lookup"><span data-stu-id="45441-218">In this case, the value is `$null`.</span></span>

```powershell
DBG> $scriptname
# DBG>
```

<span data-ttu-id="45441-219">Используйте другие команды шага для выполнения текущей инструкции и предварительного просмотра следующей инструкции в скрипте.</span><span class="sxs-lookup"><span data-stu-id="45441-219">Use another Step command (s) to execute the current statement and to preview the next statement in the script.</span></span> <span data-ttu-id="45441-220">Следующий оператор вызывает функцию PsVersion.</span><span class="sxs-lookup"><span data-stu-id="45441-220">The next statement calls the PsVersion function.</span></span>

```powershell
DBG> s
test.ps1:12  psversion
```

<span data-ttu-id="45441-221">На этом этапе `$scriptName` переменная заполняется, но значение переменной проверяется путем отображения ее значения.</span><span class="sxs-lookup"><span data-stu-id="45441-221">At this point, the `$scriptName` variable is populated, but you verify the value of the variable by displaying its value.</span></span> <span data-ttu-id="45441-222">В этом случае в качестве значения задается путь к скрипту.</span><span class="sxs-lookup"><span data-stu-id="45441-222">In this case, the value is set to the script path.</span></span>

```powershell
DBG> $scriptName
C:\ps-test\test.ps1
```

<span data-ttu-id="45441-223">Используйте другую команду Step для выполнения вызова функции.</span><span class="sxs-lookup"><span data-stu-id="45441-223">Use another Step command to execute the function call.</span></span> <span data-ttu-id="45441-224">Нажмите клавишу ВВОД или введите "s" для шага.</span><span class="sxs-lookup"><span data-stu-id="45441-224">Press ENTER, or type "s" for Step.</span></span>

```powershell
DBG> s
test.ps1:2       "PowerShell " + $PSVersionTable.PSVersion
```

<span data-ttu-id="45441-225">Сообщение отладки содержит предварительную версию инструкции в функции.</span><span class="sxs-lookup"><span data-stu-id="45441-225">The debug message includes a preview of the statement in the function.</span></span> <span data-ttu-id="45441-226">Чтобы выполнить эту инструкцию и предварительно просмотреть следующий оператор в функции, можно использовать `Step` команду.</span><span class="sxs-lookup"><span data-stu-id="45441-226">To execute this statement and to preview the next statement in the function, you can use a `Step` command.</span></span> <span data-ttu-id="45441-227">Но в этом случае используйте команду шага (o).</span><span class="sxs-lookup"><span data-stu-id="45441-227">But, in this case, use a StepOut command (o).</span></span> <span data-ttu-id="45441-228">Она завершает выполнение функции (если она не достигает точки останова) и переходит к следующему оператору в скрипте.</span><span class="sxs-lookup"><span data-stu-id="45441-228">It completes the execution of the function (unless it reaches a breakpoint) and steps to the next statement in the script.</span></span>

```powershell
DBG> o
Windows PowerShell 2.0
Have you run a background job today (start-job)?
test.ps1:13  "Done $scriptName"
```

<span data-ttu-id="45441-229">Так как мы работаем с последней инструкцией в сценарии, команды шаг, шаг с заходом и продолжить имеют одинаковый результат.</span><span class="sxs-lookup"><span data-stu-id="45441-229">Because we are on the last statement in the script, the Step, StepOut, and Continue commands have the same effect.</span></span> <span data-ttu-id="45441-230">В этом случае используйте шаг (o).</span><span class="sxs-lookup"><span data-stu-id="45441-230">In this case, use StepOut (o).</span></span>

```powershell
Done C:\ps-test\test.ps1
PS C:\ps-test>
```

<span data-ttu-id="45441-231">Команда Step by выполняет последнюю команду.</span><span class="sxs-lookup"><span data-stu-id="45441-231">The StepOut command executes the last command.</span></span> <span data-ttu-id="45441-232">Стандартная командная строка указывает, что отладчик завершил работу и вернул управление обработчику команд.</span><span class="sxs-lookup"><span data-stu-id="45441-232">The standard command prompt indicates that the debugger has exited and returned control to the command processor.</span></span>

<span data-ttu-id="45441-233">Теперь снова запустите отладчик.</span><span class="sxs-lookup"><span data-stu-id="45441-233">Now, run the debugger again.</span></span> <span data-ttu-id="45441-234">Прежде всего, чтобы удалить текущую точку останова, `Get-PsBreakpoint` Используйте `Remove-PsBreakpoint` командлеты и.</span><span class="sxs-lookup"><span data-stu-id="45441-234">First, to delete the current breakpoint, use the `Get-PsBreakpoint` and `Remove-PsBreakpoint` cmdlets.</span></span> <span data-ttu-id="45441-235">(Если вы считаете, что вы можете повторно использовать точку останова, используйте `Disable-PsBreakpoint` командлет вместо `Remove-PsBreakpoint` .)</span><span class="sxs-lookup"><span data-stu-id="45441-235">(If you think you might reuse the breakpoint, use the `Disable-PsBreakpoint` cmdlet instead of `Remove-PsBreakpoint`.)</span></span>

```powershell
PS C:\ps-test> Get-PSBreakpoint| Remove-PSBreakpoint
```

<span data-ttu-id="45441-236">Данную команду можно сократить следующим образом:</span><span class="sxs-lookup"><span data-stu-id="45441-236">You can abbreviate this command as:</span></span>

```powershell
PS C:\ps-test> gbp | rbp
```

<span data-ttu-id="45441-237">Или выполните команду, написав функцию, например следующую:</span><span class="sxs-lookup"><span data-stu-id="45441-237">Or, run the command by writing a function, such as the following function:</span></span>

```powershell
function delbr { gbp | rbp }
```

<span data-ttu-id="45441-238">Теперь создайте точку останова для `$scriptname` переменной.</span><span class="sxs-lookup"><span data-stu-id="45441-238">Now, create a breakpoint on the `$scriptname` variable.</span></span>

```powershell
PS C:\ps-test> Set-PSBreakpoint -variable scriptname -script test.ps1
```

<span data-ttu-id="45441-239">Вы можете сократить команду следующим образом:</span><span class="sxs-lookup"><span data-stu-id="45441-239">You can abbreviate the command as:</span></span>

```powershell
PS C:\ps-test> sbp -v scriptname -s test.ps1
```

<span data-ttu-id="45441-240">Теперь запустите сценарий.</span><span class="sxs-lookup"><span data-stu-id="45441-240">Now, start the script.</span></span> <span data-ttu-id="45441-241">Скрипт достигает точки останова переменной.</span><span class="sxs-lookup"><span data-stu-id="45441-241">The script reaches the variable breakpoint.</span></span> <span data-ttu-id="45441-242">Режимом по умолчанию является Write, поэтому выполнение останавливается непосредственно перед инструкцией, которая изменяет значение переменной.</span><span class="sxs-lookup"><span data-stu-id="45441-242">The default mode is Write, so execution stops just before the statement that changes the value of the variable.</span></span>

```powershell
PS C:\ps-test> .\test.ps1
Hit Variable breakpoint on 'C:\ps-test\test.ps1:$scriptName'
(Write access)

test.ps1:11  $scriptName = $MyInvocation.MyCommand.Path
# DBG>
```

<span data-ttu-id="45441-243">Отображает текущее значение `$scriptName` переменной, то есть `$null` .</span><span class="sxs-lookup"><span data-stu-id="45441-243">Display the current value of the `$scriptName` variable, which is `$null`.</span></span>

```powershell
DBG> $scriptName
# DBG>
```

<span data-ttu-id="45441-244">Используйте команды шага для выполнения инструкции, заполняющей переменную.</span><span class="sxs-lookup"><span data-stu-id="45441-244">Use a Step command (s) to execute the statement that populates the variable.</span></span>
<span data-ttu-id="45441-245">Затем отобразится новое значение `$scriptName` переменной.</span><span class="sxs-lookup"><span data-stu-id="45441-245">Then, display the new value of the `$scriptName` variable.</span></span>

```powershell
DBG> $scriptName
C:\ps-test\test.ps1
```powershell

Use a Step command (s) to preview the next statement in the script.

```powershell
DBG> s
test.ps1:12  psversion
```

<span data-ttu-id="45441-246">Следующий оператор является вызовом функции PsVersion.</span><span class="sxs-lookup"><span data-stu-id="45441-246">The next statement is a call to the PsVersion function.</span></span> <span data-ttu-id="45441-247">Чтобы пропустить функцию, но по-прежнему выполнить ее, используйте команду Степовер (v).</span><span class="sxs-lookup"><span data-stu-id="45441-247">To skip the function but still execute it, use a StepOver command (v).</span></span> <span data-ttu-id="45441-248">Если вы уже используете функцию Степовер, она не действует.</span><span class="sxs-lookup"><span data-stu-id="45441-248">If you are already in the function when you use StepOver, it is not effective.</span></span> <span data-ttu-id="45441-249">Вызов функции отображается, но не выполняется.</span><span class="sxs-lookup"><span data-stu-id="45441-249">The function call is displayed, but it is not executed.</span></span>

```powershell
DBG> v
Windows PowerShell 2.0
Have you run a background job today (start-job)?
test.ps1:13  "Done $scriptName"
```

<span data-ttu-id="45441-250">Команда Степовер выполняет функцию и просматривает следующий оператор в скрипте, который выводит последнюю строку.</span><span class="sxs-lookup"><span data-stu-id="45441-250">The StepOver command executes the function, and it previews the next statement in the script, which prints the final line.</span></span>

<span data-ttu-id="45441-251">Чтобы выйти из отладчика, используйте команду "прекратить" (t).</span><span class="sxs-lookup"><span data-stu-id="45441-251">Use a Stop command (t) to exit the debugger.</span></span> <span data-ttu-id="45441-252">Командная строка вернется в стандартную командную строку.</span><span class="sxs-lookup"><span data-stu-id="45441-252">The command prompt reverts to the standard command prompt.</span></span>

```powershell
C:\ps-test>
```

<span data-ttu-id="45441-253">Чтобы удалить точки останова, используйте `Get-PsBreakpoint` `Remove-PsBreakpoint` командлеты и.</span><span class="sxs-lookup"><span data-stu-id="45441-253">To delete the breakpoints, use the `Get-PsBreakpoint` and `Remove-PsBreakpoint` cmdlets.</span></span>

```powershell
PS C:\ps-test> Get-PSBreakpoint| Remove-PSBreakpoint
```

<span data-ttu-id="45441-254">Создайте новую точку останова команды в функции PsVersion.</span><span class="sxs-lookup"><span data-stu-id="45441-254">Create a new command breakpoint on the PsVersion function.</span></span>

```powershell
PS C:\ps-test> Set-PSBreakpoint -command psversion -script test.ps1
```

<span data-ttu-id="45441-255">Эту команду можно сократить, чтобы:</span><span class="sxs-lookup"><span data-stu-id="45441-255">You can abbreviate this command to:</span></span>

```powershell
PS C:\ps-test> sbp -c psversion -s test.ps1
```

<span data-ttu-id="45441-256">Теперь запустите сценарий.</span><span class="sxs-lookup"><span data-stu-id="45441-256">Now, run the script.</span></span>

```powershell
PS C:\ps-test> .\test.ps1
Hit Command breakpoint on 'C:\ps-test\test.ps1:psversion'

test.ps1:12  psversion
# DBG>
```

<span data-ttu-id="45441-257">Скрипт достигает точки останова при вызове функции.</span><span class="sxs-lookup"><span data-stu-id="45441-257">The script reaches the breakpoint at the function call.</span></span> <span data-ttu-id="45441-258">На этом этапе функция еще не вызывалась.</span><span class="sxs-lookup"><span data-stu-id="45441-258">At this point, the function has not yet been called.</span></span> <span data-ttu-id="45441-259">Это дает возможность использовать параметр Action в, `Set-PSBreakpoint` чтобы задать условия для выполнения точки останова или выполнить подготовительные или диагностические задачи, такие как запуск журнала или вызов диагностического скрипта или сценария безопасности.</span><span class="sxs-lookup"><span data-stu-id="45441-259">This gives you the opportunity to use the Action parameter of `Set-PSBreakpoint` to set conditions for the execution of the breakpoint or to perform preparatory or diagnostic tasks, such as starting a log or invoking a diagnostic or security script.</span></span>

<span data-ttu-id="45441-260">Чтобы задать действие, используйте команду Continue (c), чтобы выйти из скрипта, и `Remove-PsBreakpoint` команду, чтобы удалить текущую точку останова.</span><span class="sxs-lookup"><span data-stu-id="45441-260">To set an action, use a Continue command (c) to exit the script, and a `Remove-PsBreakpoint` command to delete the current breakpoint.</span></span> <span data-ttu-id="45441-261">(Точки останова доступны только для чтения, поэтому нельзя добавить действие в текущую точку останова.)</span><span class="sxs-lookup"><span data-stu-id="45441-261">(Breakpoints are read-only, so you cannot add an action to the current breakpoint.)</span></span>

```powershell
DBG> c
Windows PowerShell 2.0
Have you run a background job today (start-job)?
Done C:\ps-test\test.ps1

PS C:\ps-test> Get-PSBreakpoint| Remove-PSBreakpoint
PS C:\ps-test>
```

<span data-ttu-id="45441-262">Теперь создайте новую точку останова команды с действием.</span><span class="sxs-lookup"><span data-stu-id="45441-262">Now, create a new command breakpoint with an action.</span></span> <span data-ttu-id="45441-263">Следующая команда задает точку останова команды с действием, которое регистрирует значение `$scriptName` переменной при вызове функции.</span><span class="sxs-lookup"><span data-stu-id="45441-263">The following command sets a command breakpoint with an action that logs the value of the `$scriptName` variable when the function is called.</span></span> <span data-ttu-id="45441-264">Поскольку ключевое слово Break не используется в действии, выполнение не останавливается.</span><span class="sxs-lookup"><span data-stu-id="45441-264">Because the Break keyword is not used in the action, execution does not stop.</span></span> <span data-ttu-id="45441-265">(Обратная кавычка (') — это символ продолжения строки.)</span><span class="sxs-lookup"><span data-stu-id="45441-265">(The backtick (\`) is the line-continuation character.)</span></span>

```powershell
PS C:\ps-test> Set-PSBreakpoint -command psversion -script test.ps1  `
-action { add-content "The value of `$scriptName is $scriptName." `
-path action.log}
```

<span data-ttu-id="45441-266">Можно также добавить действия, задаваемые в качестве условий для точки останова.</span><span class="sxs-lookup"><span data-stu-id="45441-266">You can also add actions that set conditions for the breakpoint.</span></span> <span data-ttu-id="45441-267">В следующей команде точка останова команды выполняется только в том случае, если для политики выполнения задано значение RemoteSigned, наиболее ограниченная политика, которая по-прежнему позволяет выполнять сценарии.</span><span class="sxs-lookup"><span data-stu-id="45441-267">In the following command, the command breakpoint is executed only if the execution policy is set to RemoteSigned, the most restrictive policy that still permits you to run scripts.</span></span> <span data-ttu-id="45441-268">(Обратная кавычка (') — это символ продолжения.)</span><span class="sxs-lookup"><span data-stu-id="45441-268">(The backtick (\`) is the continuation character.)</span></span>

```powershell
PS C:\ps-test> Set-PSBreakpoint -script test.ps1 -command psversion `
-action { if ((Get-ExecutionPolicy) -eq "RemoteSigned") { break }}
```

<span data-ttu-id="45441-269">Ключевое слово Break в действии направляет отладчик для выполнения точки останова.</span><span class="sxs-lookup"><span data-stu-id="45441-269">The Break keyword in the action directs the debugger to execute the breakpoint.</span></span>
<span data-ttu-id="45441-270">Можно также использовать ключевое слово Continue, чтобы направить отладчик для выполнения без нарушения.</span><span class="sxs-lookup"><span data-stu-id="45441-270">You can also use the Continue keyword to direct the debugger to execute without breaking.</span></span> <span data-ttu-id="45441-271">Так как ключевое слово default продолжает выполняться, необходимо указать Break, чтобы остановить выполнение.</span><span class="sxs-lookup"><span data-stu-id="45441-271">Because the default keyword is Continue, you must specify Break to stop execution.</span></span>

<span data-ttu-id="45441-272">Теперь запустите сценарий.</span><span class="sxs-lookup"><span data-stu-id="45441-272">Now, run the script.</span></span>

```powershell
PS C:\ps-test> .\test.ps1
Hit Command breakpoint on 'C:\ps-test\test.ps1:psversion'

test.ps1:12  psversion
```

<span data-ttu-id="45441-273">Так как для политики выполнения задано значение **RemoteSigned**, выполнение останавливается при вызове функции.</span><span class="sxs-lookup"><span data-stu-id="45441-273">Because the execution policy is set to **RemoteSigned**, execution stops at the function call.</span></span>

<span data-ttu-id="45441-274">На этом этапе может потребоваться проверить стек вызовов.</span><span class="sxs-lookup"><span data-stu-id="45441-274">At this point, you might want to check the call stack.</span></span> <span data-ttu-id="45441-275">Используйте `Get-PsCallStack` командлет или `Get-PsCallStack` команду отладчика (k).</span><span class="sxs-lookup"><span data-stu-id="45441-275">Use the `Get-PsCallStack` cmdlet or the `Get-PsCallStack` debugger command (k).</span></span> <span data-ttu-id="45441-276">Следующая команда возвращает текущий стек вызовов.</span><span class="sxs-lookup"><span data-stu-id="45441-276">The following command gets the current call stack.</span></span>

```powershell
DBG> k
2: prompt
1: .\test.ps1: $args=[]
0: prompt: $args=[]
```

<span data-ttu-id="45441-277">В этом примере демонстрируется лишь несколько способов использования отладчика PowerShell.</span><span class="sxs-lookup"><span data-stu-id="45441-277">This example demonstrates just a few of the many ways to use the PowerShell debugger.</span></span>

<span data-ttu-id="45441-278">Чтобы получить дополнительные сведения о командлетах отладчика, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="45441-278">For more information about the debugger cmdlets, type the following command:</span></span>

```powershell
help <cmdlet-name> -full
```

<span data-ttu-id="45441-279">Например, введите:</span><span class="sxs-lookup"><span data-stu-id="45441-279">For example, type:</span></span>

```powershell
help Set-PSBreakpoint -full
```

## <a name="other-debugging-features-in-powershell"></a><span data-ttu-id="45441-280">Другие функции отладки в PowerShell</span><span class="sxs-lookup"><span data-stu-id="45441-280">Other Debugging Features in PowerShell</span></span>

<span data-ttu-id="45441-281">Помимо отладчика PowerShell, в PowerShell есть несколько других функций, которые можно использовать для отладки скриптов и функций.</span><span class="sxs-lookup"><span data-stu-id="45441-281">In addition to the PowerShell debugger, PowerShell includes several other features that you can use to debug scripts and functions.</span></span>

- <span data-ttu-id="45441-282">Интегрированная среда сценариев Windows PowerShell включает в себя интерактивный графический отладчик.</span><span class="sxs-lookup"><span data-stu-id="45441-282">Windows PowerShell ISE includes an interactive graphical debugger.</span></span> <span data-ttu-id="45441-283">Для получения дополнительных сведений запустите интегрированную среду сценариев Windows PowerShell и нажмите клавишу F1.</span><span class="sxs-lookup"><span data-stu-id="45441-283">For more information, start Windows PowerShell ISE and press F1.</span></span>

- <span data-ttu-id="45441-284">`Set-PSDebug`Командлет предлагает самые базовые функции отладки скриптов, включая пошаговое выполнение и трассировку.</span><span class="sxs-lookup"><span data-stu-id="45441-284">The `Set-PSDebug` cmdlet offers very basic script debugging features, including stepping and tracing.</span></span>

- <span data-ttu-id="45441-285">Используйте `Set-StrictMode` командлет, чтобы обнаружить ссылки на неинициализированные переменные, ссылки на несуществующие свойства объекта и на недопустимый синтаксис функции.</span><span class="sxs-lookup"><span data-stu-id="45441-285">Use the `Set-StrictMode` cmdlet to detect references to uninitialized variables, to references to non-existent properties of an object, and to function syntax that is not valid.</span></span>

- <span data-ttu-id="45441-286">Добавьте в скрипт диагностические инструкции, например инструкции, отображающие значения переменных, инструкции, считывающие входные данные из командной строки, или инструкции, сообщающие о текущей инструкции.</span><span class="sxs-lookup"><span data-stu-id="45441-286">Add diagnostic statements to a script, such as statements that display the value of variables, statements that read input from the command line, or statements that report the current instruction.</span></span> <span data-ttu-id="45441-287">Используйте командлеты, которые содержат команду записи для этой задачи, например `Write-Host` ,, `Write-Debug` `Write-Warning` и `Write-Verbose` .</span><span class="sxs-lookup"><span data-stu-id="45441-287">Use the cmdlets that contain the Write verb for this task, such as `Write-Host`, `Write-Debug`, `Write-Warning`, and `Write-Verbose`.</span></span>

## <a name="see-also"></a><span data-ttu-id="45441-288">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="45441-288">SEE ALSO</span></span>

- [<span data-ttu-id="45441-289">Disable-PsBreakpoint</span><span class="sxs-lookup"><span data-stu-id="45441-289">Disable-PsBreakpoint</span></span>](xref:Microsoft.PowerShell.Utility.Disable-PSBreakpoint)
- [<span data-ttu-id="45441-290">Enable-PsBreakpoint</span><span class="sxs-lookup"><span data-stu-id="45441-290">Enable-PsBreakpoint</span></span>](xref:Microsoft.PowerShell.Utility.Enable-PSBreakpoint)
- [<span data-ttu-id="45441-291">Get-PsBreakpoint</span><span class="sxs-lookup"><span data-stu-id="45441-291">Get-PsBreakpoint</span></span>](xref:Microsoft.PowerShell.Utility.Get-PSBreakpoint)
- [<span data-ttu-id="45441-292">Get-PsCallStack</span><span class="sxs-lookup"><span data-stu-id="45441-292">Get-PsCallStack</span></span>](xref:Microsoft.PowerShell.Utility.Get-PSCallStack)
- [<span data-ttu-id="45441-293">Remove-PsBreakpoint</span><span class="sxs-lookup"><span data-stu-id="45441-293">Remove-PsBreakpoint</span></span>](xref:Microsoft.PowerShell.Utility.Remove-PSBreakpoint)
- [<span data-ttu-id="45441-294">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="45441-294">Set-PSBreakpoint</span></span>](xref:Microsoft.PowerShell.Utility.Set-PSBreakpoint)
- [<span data-ttu-id="45441-295">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="45441-295">Write-Debug</span></span>](xref:Microsoft.PowerShell.Utility.Write-Debug)
- [<span data-ttu-id="45441-296">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="45441-296">Write-Verbose</span></span>](xref:Microsoft.PowerShell.Utility.Write-Verbose)

