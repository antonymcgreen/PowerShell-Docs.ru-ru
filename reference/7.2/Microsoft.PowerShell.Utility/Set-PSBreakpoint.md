---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/24/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-psbreakpoint?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSBreakpoint
ms.openlocfilehash: 5e2bdf435bf7cb9da3f31712c346beff29a11baf
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603972"
---
# <span data-ttu-id="939a5-102">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="939a5-102">Set-PSBreakpoint</span></span>

## <span data-ttu-id="939a5-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="939a5-103">SYNOPSIS</span></span>
<span data-ttu-id="939a5-104">Устанавливает точку останова на строке, команде или переменной.</span><span class="sxs-lookup"><span data-stu-id="939a5-104">Sets a breakpoint on a line, command, or variable.</span></span>

## <span data-ttu-id="939a5-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="939a5-105">SYNTAX</span></span>

### <span data-ttu-id="939a5-106">Строка (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="939a5-106">Line (Default)</span></span>

```
Set-PSBreakpoint [-Action <ScriptBlock>] [[-Column] <Int32>] [-Line] <Int32[]> [-Script] <String[]>
 [<CommonParameters>]
```

### <span data-ttu-id="939a5-107">Get-Help</span><span class="sxs-lookup"><span data-stu-id="939a5-107">Command</span></span>

```
Set-PSBreakpoint [-Action <ScriptBlock>] -Command <String[]> [[-Script] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="939a5-108">Переменная</span><span class="sxs-lookup"><span data-stu-id="939a5-108">Variable</span></span>

```
Set-PSBreakpoint [-Action <ScriptBlock>] [[-Script] <String[]>] -Variable <String[]>
 [-Mode <VariableAccessMode>] [<CommonParameters>]
```

## <span data-ttu-id="939a5-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="939a5-109">DESCRIPTION</span></span>

<span data-ttu-id="939a5-110">`Set-PSBreakpoint`Командлет задает точку останова в скрипте или в любой команде, выполняемой в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="939a5-110">The `Set-PSBreakpoint` cmdlet sets a breakpoint in a script or in any command run in the current session.</span></span> <span data-ttu-id="939a5-111">Можно использовать `Set-PSBreakpoint` для установки точки останова перед выполнением сценария или выполнением команды или во время отладки, если остановлена в другой точке останова.</span><span class="sxs-lookup"><span data-stu-id="939a5-111">You can use `Set-PSBreakpoint` to set a breakpoint before executing a script or running a command, or during debugging, when stopped at another breakpoint.</span></span>

<span data-ttu-id="939a5-112">`Set-PSBreakpoint` невозможно установить точку останова на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="939a5-112">`Set-PSBreakpoint` cannot set a breakpoint on a remote computer.</span></span> <span data-ttu-id="939a5-113">Для отладки сценария на удаленном компьютере скопируйте сценарий на локальный компьютер, а затем выполните отладку локально.</span><span class="sxs-lookup"><span data-stu-id="939a5-113">To debug a script on a remote computer, copy the script to the local computer and then debug it locally.</span></span>

<span data-ttu-id="939a5-114">Каждая `Set-PSBreakpoint` команда создает один из следующих трех типов точек останова:</span><span class="sxs-lookup"><span data-stu-id="939a5-114">Each `Set-PSBreakpoint` command creates one of the following three types of breakpoints:</span></span>

- <span data-ttu-id="939a5-115">Точка останова в строке — задает точки останова в определенных координатах строки и столбца.</span><span class="sxs-lookup"><span data-stu-id="939a5-115">Line breakpoint - Sets breakpoints at particular line and column coordinates.</span></span>
- <span data-ttu-id="939a5-116">Точка останова команды — задает точки останова для команд и функций.</span><span class="sxs-lookup"><span data-stu-id="939a5-116">Command breakpoint - Sets breakpoints on commands and functions.</span></span>
- <span data-ttu-id="939a5-117">Точка останова — задает точки останова для переменных.</span><span class="sxs-lookup"><span data-stu-id="939a5-117">Variable breakpoint - Sets breakpoints on variables.</span></span>

<span data-ttu-id="939a5-118">Точку останова можно задать в нескольких строках, командах или переменных в одной `Set-PSBreakpoint` команде, но каждая `Set-PSBreakpoint` команда устанавливает только один тип точки останова.</span><span class="sxs-lookup"><span data-stu-id="939a5-118">You can set a breakpoint on multiple lines, commands, or variables in a single `Set-PSBreakpoint` command, but each `Set-PSBreakpoint` command sets only one type of breakpoint.</span></span>

<span data-ttu-id="939a5-119">В точке останова PowerShell временно останавливает выполнение и передает управление отладчику.</span><span class="sxs-lookup"><span data-stu-id="939a5-119">At a breakpoint, PowerShell temporarily stops executing and gives control to the debugger.</span></span> <span data-ttu-id="939a5-120">Командная строка изменится на `DBG\>` , а набор команд отладчика станет доступным для использования.</span><span class="sxs-lookup"><span data-stu-id="939a5-120">The command prompt changes to `DBG\>`, and a set of debugger commands become available for use.</span></span> <span data-ttu-id="939a5-121">Однако можно использовать параметр **Action** , чтобы указать альтернативный ответ, например условия для точки останова или инструкции для выполнения дополнительных задач, таких как ведение журнала или диагностика.</span><span class="sxs-lookup"><span data-stu-id="939a5-121">However, you can use the **Action** parameter to specify an alternate response, such as conditions for the breakpoint or instructions to perform additional tasks such as logging or diagnostics.</span></span>

<span data-ttu-id="939a5-122">`Set-PSBreakpoint`Командлет — это один из нескольких командлетов, предназначенных для отладки скриптов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="939a5-122">The `Set-PSBreakpoint` cmdlet is one of several cmdlets designed for debugging PowerShell scripts.</span></span>
<span data-ttu-id="939a5-123">Дополнительные сведения о отладчике PowerShell см. в разделе [about_Debuggers](../Microsoft.PowerShell.Core/About/about_Debuggers.md).</span><span class="sxs-lookup"><span data-stu-id="939a5-123">For more information about the PowerShell debugger, see [about_Debuggers](../Microsoft.PowerShell.Core/About/about_Debuggers.md).</span></span>

## <span data-ttu-id="939a5-124">Примеры</span><span class="sxs-lookup"><span data-stu-id="939a5-124">EXAMPLES</span></span>

### <span data-ttu-id="939a5-125">Пример 1. Задание точки останова в строке</span><span class="sxs-lookup"><span data-stu-id="939a5-125">Example 1: Set a breakpoint on a line</span></span>

<span data-ttu-id="939a5-126">В этом примере задается точка останова в строке 5 в скрипте Sample.ps1.</span><span class="sxs-lookup"><span data-stu-id="939a5-126">This example sets a breakpoint at line 5 in the Sample.ps1 script.</span></span> <span data-ttu-id="939a5-127">При выполнении скрипта выполнение останавливается непосредственно перед выполнением строки 5.</span><span class="sxs-lookup"><span data-stu-id="939a5-127">When the script runs, execution stops immediately before line 5 would execute.</span></span>

```powershell
Set-PSBreakpoint -Script "sample.ps1" -Line 5
```

```output
Column     : 0
Line       : 5
Action     :
Enabled    : True
HitCount   : 0
Id         : 0
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1
```

<span data-ttu-id="939a5-128">При установке новой точки останова по номеру строки `Set-PSBreakpoint` командлет создает объект точки останова строки (**System. Management. Automation. линебреакпоинт**), включающий идентификатор точки останова и число попаданий.</span><span class="sxs-lookup"><span data-stu-id="939a5-128">When you set a new breakpoint by line number, the `Set-PSBreakpoint` cmdlet generates a line breakpoint object (**System.Management.Automation.LineBreakpoint**) that includes the breakpoint ID and hit count.</span></span>

### <span data-ttu-id="939a5-129">Пример 2. Установка точки останова в функции</span><span class="sxs-lookup"><span data-stu-id="939a5-129">Example 2: Set a breakpoint on a function</span></span>

<span data-ttu-id="939a5-130">В этом примере создается точка останова команды для `Increment` функции в командлете Sample.ps1.</span><span class="sxs-lookup"><span data-stu-id="939a5-130">This example creates a command breakpoint on the `Increment` function in the Sample.ps1 cmdlet.</span></span> <span data-ttu-id="939a5-131">Сценарий останавливает выполнение непосредственно перед каждым вызовом указанной функции.</span><span class="sxs-lookup"><span data-stu-id="939a5-131">The script stops executing immediately before each call to the specified function.</span></span>

```powershell
Set-PSBreakpoint -Command "Increment" -Script "sample.ps1"
```

```Output
Command    : Increment
Action     :
Enabled    : True
HitCount   : 0
Id         : 1
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1
```

<span data-ttu-id="939a5-132">Результатом является объект точки останова команды.</span><span class="sxs-lookup"><span data-stu-id="939a5-132">The result is a command breakpoint object.</span></span> <span data-ttu-id="939a5-133">Перед выполнением скрипта значение свойства **хиткаунт** равно 0.</span><span class="sxs-lookup"><span data-stu-id="939a5-133">Before the script runs, the value of the **HitCount** property is 0.</span></span>

### <span data-ttu-id="939a5-134">Пример 3. Установка точки останова в переменной</span><span class="sxs-lookup"><span data-stu-id="939a5-134">Example 3: Set a breakpoint on a variable</span></span>

<span data-ttu-id="939a5-135">В этом примере задается точка останова на **серверной** переменной в скрипте Sample.ps1.</span><span class="sxs-lookup"><span data-stu-id="939a5-135">This example sets a breakpoint on the **Server** variable in the Sample.ps1 script.</span></span> <span data-ttu-id="939a5-136">Он использует параметр **mode** со значением **ReadWrite** , чтобы прерывать выполнение при считывании значения переменной и непосредственно перед изменением значения.</span><span class="sxs-lookup"><span data-stu-id="939a5-136">It uses the **Mode** parameter with a value of **ReadWrite** to stop execution when the value of the variable is read and just before the value changes.</span></span>

```powershell
Set-PSBreakpoint -Script "sample.ps1" -Variable "Server" -Mode ReadWrite
```

### <span data-ttu-id="939a5-137">Пример 4. Установка точки останова для каждой команды, которая начинается с указанного текста</span><span class="sxs-lookup"><span data-stu-id="939a5-137">Example 4: Set a breakpoint on every command that begins with specified text</span></span>

<span data-ttu-id="939a5-138">В этом примере задается точка останова для каждой команды в Sample.ps1 скрипте, которая начинается с "Write", например `Write-Host` .</span><span class="sxs-lookup"><span data-stu-id="939a5-138">This example sets a breakpoint on every command in the Sample.ps1 script that begins with "write", such as `Write-Host`.</span></span>

```powershell
Set-PSBreakpoint -Script Sample.ps1 -Command "write*"
```

### <span data-ttu-id="939a5-139">Пример 5. Задание точки останова в зависимости от значения переменной</span><span class="sxs-lookup"><span data-stu-id="939a5-139">Example 5: Set a breakpoint depending on the value of a variable</span></span>

<span data-ttu-id="939a5-140">В этом примере выполнение `DiskTest` функции в скрипте Test.ps1 прекращается, только если значение `$Disk` переменной больше 2.</span><span class="sxs-lookup"><span data-stu-id="939a5-140">This example stops execution at the `DiskTest` function in the Test.ps1 script only when the value of the `$Disk` variable is greater than 2.</span></span>

```powershell
Set-PSBreakpoint -Script "test.ps1" -Command "DiskTest" -Action { if ($Disk -gt 2) { break } }
```

<span data-ttu-id="939a5-141">Значением **действия** является блок скрипта, который проверяет значение `$Disk` переменной в функции.</span><span class="sxs-lookup"><span data-stu-id="939a5-141">The value of the **Action** is a script block that tests the value of the `$Disk` variable in the function.</span></span>

<span data-ttu-id="939a5-142">Действие использует `break` ключевое слово для отмены выполнения при соблюдении условия.</span><span class="sxs-lookup"><span data-stu-id="939a5-142">The action uses the `break` keyword to stop execution if the condition is met.</span></span> <span data-ttu-id="939a5-143">Альтернативный вариант (и значение по умолчанию) будет **продолжен**.</span><span class="sxs-lookup"><span data-stu-id="939a5-143">The alternative (and the default) is **Continue**.</span></span>

### <span data-ttu-id="939a5-144">Пример 6. Установка точки останова в функции</span><span class="sxs-lookup"><span data-stu-id="939a5-144">Example 6: Set a breakpoint on a function</span></span>

<span data-ttu-id="939a5-145">В этом примере задается точка останова для `CheckLog` функции.</span><span class="sxs-lookup"><span data-stu-id="939a5-145">This example sets a breakpoint on the `CheckLog` function.</span></span> <span data-ttu-id="939a5-146">Поскольку команда не указывает сценарий, точка останова устанавливается для любого объекта, который выполняется в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="939a5-146">Because the command does not specify a script, the breakpoint is set on anything that runs in the current session.</span></span> <span data-ttu-id="939a5-147">Отладчик останавливается при вызове функции, а не при ее объявлении.</span><span class="sxs-lookup"><span data-stu-id="939a5-147">The debugger breaks when the function is called, not when it is declared.</span></span>

```
PS> Set-PSBreakpoint -Command "checklog"
Id       : 0
Command  : checklog
Enabled  : True
HitCount : 0
Action   :

function CheckLog {
>> get-eventlog -log Application |
>> where {($_.source -like "TestApp") -and ($_.Message -like "*failed*")}
>>}
>>
PS> Checklog
DEBUG: Hit breakpoint(s)
DEBUG:  Function breakpoint on 'prompt:Checklog'
```

### <span data-ttu-id="939a5-148">Пример 7. Установка точек останова в нескольких строках</span><span class="sxs-lookup"><span data-stu-id="939a5-148">Example 7: Set breakpoints on multiple lines</span></span>

<span data-ttu-id="939a5-149">В этом примере задаются три точки останова по строке в скрипте Sample.ps1.</span><span class="sxs-lookup"><span data-stu-id="939a5-149">This example sets three line breakpoints in the Sample.ps1 script.</span></span> <span data-ttu-id="939a5-150">Она задает одну точку останова в столбце 2 каждой из строк, указанных в сценарии.</span><span class="sxs-lookup"><span data-stu-id="939a5-150">It sets one breakpoint at column 2 on each of the lines specified in the script.</span></span> <span data-ttu-id="939a5-151">Действие, указанное в параметре **Action** , применяется ко всем точкам останова.</span><span class="sxs-lookup"><span data-stu-id="939a5-151">The action specified in the **Action** parameter applies to all breakpoints.</span></span>

```powershell
PS C:\> Set-PSBreakpoint -Script "sample.ps1" -Line 1, 14, 19 -Column 2 -Action {&(log.ps1)}
```

```Output
Column     : 2
Line       : 1
Action     :
Enabled    : True
HitCount   : 0
Id         : 6
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1


Column     : 2
Line       : 14
Action     :
Enabled    : True
HitCount   : 0
Id         : 7
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1


Column     : 2
Line       : 19
Action     :
Enabled    : True
HitCount   : 0
Id         : 8
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1
```

## <span data-ttu-id="939a5-152">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="939a5-152">PARAMETERS</span></span>

### <span data-ttu-id="939a5-153">-Action</span><span class="sxs-lookup"><span data-stu-id="939a5-153">-Action</span></span>

<span data-ttu-id="939a5-154">Задает команды, которые выполняются в каждой точке останова вместо останова.</span><span class="sxs-lookup"><span data-stu-id="939a5-154">Specifies commands that run at each breakpoint instead of breaking.</span></span> <span data-ttu-id="939a5-155">Введите блок сценария, содержащий команды.</span><span class="sxs-lookup"><span data-stu-id="939a5-155">Enter a script block that contains the commands.</span></span> <span data-ttu-id="939a5-156">Этот параметр можно использовать для задания условных точек останова или выполнения других задач, таких как тестирование или ведение журнала.</span><span class="sxs-lookup"><span data-stu-id="939a5-156">You can use this parameter to set conditional breakpoints or to perform other tasks, such as testing or logging.</span></span>

<span data-ttu-id="939a5-157">Если этот параметр пропущен или не указаны никакие действия, выполнение останавливается в точке останова и запускается отладчик.</span><span class="sxs-lookup"><span data-stu-id="939a5-157">If this parameter is omitted, or no action is specified, execution stops at the breakpoint, and the debugger starts.</span></span>

<span data-ttu-id="939a5-158">При использовании параметра **Action** блок сценария действия выполняется в каждой точке останова.</span><span class="sxs-lookup"><span data-stu-id="939a5-158">When the **Action** parameter is used, the Action script block runs at each breakpoint.</span></span> <span data-ttu-id="939a5-159">Выполнение не останавливается, если блок сценария не включает ключевое слово Break.</span><span class="sxs-lookup"><span data-stu-id="939a5-159">Execution does not stop unless the script block includes the Break keyword.</span></span> <span data-ttu-id="939a5-160">При использовании ключевого слова Continue в блоке сценария выполнение возобновляется до следующей точки останова.</span><span class="sxs-lookup"><span data-stu-id="939a5-160">If you use the Continue keyword in the script block, execution resumes until the next breakpoint.</span></span>

<span data-ttu-id="939a5-161">Дополнительные сведения см. в разделе [about_Script_Blocks](../Microsoft.PowerShell.Core/About/about_Script_Blocks.md), [about_Break](../Microsoft.PowerShell.Core/About/about_Break.md)и [about_Continue](../Microsoft.PowerShell.Core/About/about_Continue.md).</span><span class="sxs-lookup"><span data-stu-id="939a5-161">For more information, see [about_Script_Blocks](../Microsoft.PowerShell.Core/About/about_Script_Blocks.md), [about_Break](../Microsoft.PowerShell.Core/About/about_Break.md), and [about_Continue](../Microsoft.PowerShell.Core/About/about_Continue.md).</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="939a5-162">-Column</span><span class="sxs-lookup"><span data-stu-id="939a5-162">-Column</span></span>

<span data-ttu-id="939a5-163">Указывает номер столбца в файле сценария, в котором выполнение останавливается.</span><span class="sxs-lookup"><span data-stu-id="939a5-163">Specifies the column number of the column in the script file on which execution stops.</span></span> <span data-ttu-id="939a5-164">Введите только один номер столбца.</span><span class="sxs-lookup"><span data-stu-id="939a5-164">Enter only one column number.</span></span> <span data-ttu-id="939a5-165">Значение по умолчанию: столбец 1.</span><span class="sxs-lookup"><span data-stu-id="939a5-165">The default is column 1.</span></span>

<span data-ttu-id="939a5-166">Значение столбца используется со значением параметра **line** для указания точки останова.</span><span class="sxs-lookup"><span data-stu-id="939a5-166">The Column value is used with the value of the **Line** parameter to specify the breakpoint.</span></span> <span data-ttu-id="939a5-167">Если параметр **line** задает несколько строк, параметр **Column** задает точку останова в указанном столбце для каждой из указанных строк.</span><span class="sxs-lookup"><span data-stu-id="939a5-167">If the **Line** parameter specifies multiple lines, the **Column** parameter sets a breakpoint at the specified column on each of the specified lines.</span></span> <span data-ttu-id="939a5-168">PowerShell прекращает выполнение до инструкции или выражения, включающего символ в указанной строке и позиции столбца.</span><span class="sxs-lookup"><span data-stu-id="939a5-168">PowerShell stops executing before the statement or expression that includes the character at the specified line and column position.</span></span>

<span data-ttu-id="939a5-169">Столбцы отсчитываются от верхней левой границы, начиная с номера столбца 1 (не 0).</span><span class="sxs-lookup"><span data-stu-id="939a5-169">Columns are counted from the top left margin beginning with column number 1 (not 0).</span></span> <span data-ttu-id="939a5-170">Если указать столбец, который не существует в сценарии, ошибка не объявляется, однако точка останова не выполняется.</span><span class="sxs-lookup"><span data-stu-id="939a5-170">If you specify a column that does not exist in the script, an error is not declared, but the breakpoint is never executed.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Line
Aliases:

Required: False
Position: 2
Default value: 1
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="939a5-171">-Command</span><span class="sxs-lookup"><span data-stu-id="939a5-171">-Command</span></span>

<span data-ttu-id="939a5-172">Задает точку останова команды.</span><span class="sxs-lookup"><span data-stu-id="939a5-172">Sets a command breakpoint.</span></span> <span data-ttu-id="939a5-173">Введите имена командлетов, например `Get-Process` , или имена функций.</span><span class="sxs-lookup"><span data-stu-id="939a5-173">Enter cmdlet names, such as `Get-Process`, or function names.</span></span> <span data-ttu-id="939a5-174">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="939a5-174">Wildcards are permitted.</span></span>

<span data-ttu-id="939a5-175">Выполнение останавливается непосредственно перед выполнением каждого экземпляра каждой команды.</span><span class="sxs-lookup"><span data-stu-id="939a5-175">Execution stops just before each instance of each command is executed.</span></span> <span data-ttu-id="939a5-176">Если команда является функцией, выполнение останавливается при каждом вызове функции и в каждом разделе BEGIN, PROCESS и END.</span><span class="sxs-lookup"><span data-stu-id="939a5-176">If the command is a function, execution stops each time the function is called and at each BEGIN, PROCESS, and END section.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Command
Aliases: C

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="939a5-177">-Line</span><span class="sxs-lookup"><span data-stu-id="939a5-177">-Line</span></span>

<span data-ttu-id="939a5-178">Задает точку останова строки в сценарии.</span><span class="sxs-lookup"><span data-stu-id="939a5-178">Sets a line breakpoint in a script.</span></span> <span data-ttu-id="939a5-179">Введите один или несколько номеров строк, разделенных запятыми.</span><span class="sxs-lookup"><span data-stu-id="939a5-179">Enter one or more line numbers, separated by commas.</span></span> <span data-ttu-id="939a5-180">PowerShell останавливается сразу перед выполнением инструкции, которая начинается на каждой из указанных строк.</span><span class="sxs-lookup"><span data-stu-id="939a5-180">PowerShell stops immediately before executing the statement that begins on each of the specified lines.</span></span>

<span data-ttu-id="939a5-181">Строки отсчитываются от верхней левой границы файла сценария, начиная с номера строки 1 (не 0).</span><span class="sxs-lookup"><span data-stu-id="939a5-181">Lines are counted from the top left margin of the script file beginning with line number 1 (not 0).</span></span>
<span data-ttu-id="939a5-182">Если указать пустую строку, выполнение останавливается перед следующей непустой строкой.</span><span class="sxs-lookup"><span data-stu-id="939a5-182">If you specify a blank line, execution stops before the next non-blank line.</span></span> <span data-ttu-id="939a5-183">Если строка выходит за пределы диапазона, останов не выполняется.</span><span class="sxs-lookup"><span data-stu-id="939a5-183">If the line is out of range, the breakpoint is never hit.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: Line
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="939a5-184">-Mode</span><span class="sxs-lookup"><span data-stu-id="939a5-184">-Mode</span></span>

<span data-ttu-id="939a5-185">Задает режим доступа, который активирует переменные точки останова.</span><span class="sxs-lookup"><span data-stu-id="939a5-185">Specifies the mode of access that triggers variable breakpoints.</span></span> <span data-ttu-id="939a5-186">Значение по умолчанию — **Write**.</span><span class="sxs-lookup"><span data-stu-id="939a5-186">The default is **Write**.</span></span>

<span data-ttu-id="939a5-187">Этот параметр допустим только в том случае, если в команде используется параметр **variable** .</span><span class="sxs-lookup"><span data-stu-id="939a5-187">This parameter is valid only when the **Variable** parameter is used in the command.</span></span> <span data-ttu-id="939a5-188">Режим применяется ко всем точкам останова, заданным в команде.</span><span class="sxs-lookup"><span data-stu-id="939a5-188">The mode applies to all breakpoints set in the command.</span></span> <span data-ttu-id="939a5-189">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="939a5-189">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="939a5-190">**Запись** — останавливает выполнение непосредственно перед записью нового значения в переменную.</span><span class="sxs-lookup"><span data-stu-id="939a5-190">**Write** - Stops execution immediately before a new value is written to the variable.</span></span>
- <span data-ttu-id="939a5-191">**Чтение** — остановка выполнения при считывании переменной, то есть при доступе к ее значению, назначению, отображению или использования.</span><span class="sxs-lookup"><span data-stu-id="939a5-191">**Read** - Stops execution when the variable is read, that is, when its value is accessed, either to be assigned, displayed, or used.</span></span> <span data-ttu-id="939a5-192">В режиме чтения выполнение не прекращается при изменении значения переменной.</span><span class="sxs-lookup"><span data-stu-id="939a5-192">In read mode, execution does not stop when the value of the variable changes.</span></span>
- <span data-ttu-id="939a5-193">**ReadWrite** — останавливает выполнение, когда переменная считывается или записывается.</span><span class="sxs-lookup"><span data-stu-id="939a5-193">**ReadWrite** - Stops execution when the variable is read or written.</span></span>

```yaml
Type: System.Management.Automation.VariableAccessMode
Parameter Sets: Variable
Aliases:
Accepted values: Read, Write, ReadWrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="939a5-194">-Script</span><span class="sxs-lookup"><span data-stu-id="939a5-194">-Script</span></span>

<span data-ttu-id="939a5-195">Указывает массив файлов скрипта, в котором этот командлет задает точку останова.</span><span class="sxs-lookup"><span data-stu-id="939a5-195">Specifies an array of script files that this cmdlet sets a breakpoint in.</span></span> <span data-ttu-id="939a5-196">Введите пути и имена одного или нескольких файлов сценариев.</span><span class="sxs-lookup"><span data-stu-id="939a5-196">Enter the paths and file names of one or more script files.</span></span> <span data-ttu-id="939a5-197">Если файлы находятся в текущем каталоге, путь можно опустить.</span><span class="sxs-lookup"><span data-stu-id="939a5-197">If the files are in the current directory, you can omit the path.</span></span>
<span data-ttu-id="939a5-198">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="939a5-198">Wildcards are permitted.</span></span>

<span data-ttu-id="939a5-199">По умолчанию точки останова переменной и точки останова команды задаются в любых командах, которые выполняются в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="939a5-199">By default, variable breakpoints and command breakpoints are set on any command that runs in the current session.</span></span> <span data-ttu-id="939a5-200">Этот параметр является обязательным, только если задается точка останова строки.</span><span class="sxs-lookup"><span data-stu-id="939a5-200">This parameter is required only when setting a line breakpoint.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Line, Command, Variable
Aliases:

Required: True (Line), False (Command, Variable)
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="939a5-201">-Variable</span><span class="sxs-lookup"><span data-stu-id="939a5-201">-Variable</span></span>

<span data-ttu-id="939a5-202">Задает массив переменных, на которых этот командлет задает точки останова.</span><span class="sxs-lookup"><span data-stu-id="939a5-202">Specifies an array of variables that this cmdlet sets breakpoints on.</span></span> <span data-ttu-id="939a5-203">Введите разделенный запятыми список переменных без знака доллара ( `$` ).</span><span class="sxs-lookup"><span data-stu-id="939a5-203">Enter a comma-separated list of variables without dollar signs (`$`).</span></span>

<span data-ttu-id="939a5-204">Используйте параметр **mode** для определения режима доступа, запускающего точки останова.</span><span class="sxs-lookup"><span data-stu-id="939a5-204">Use the **Mode** parameter to determine the mode of access that triggers the breakpoints.</span></span> <span data-ttu-id="939a5-205">Режим по умолчанию, Write, останавливает выполнение непосредственно перед записью нового значения в переменную.</span><span class="sxs-lookup"><span data-stu-id="939a5-205">The default mode, Write, stops execution just before a new value is written to the variable.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Variable
Aliases: V

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="939a5-206">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="939a5-206">CommonParameters</span></span>

<span data-ttu-id="939a5-207">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="939a5-207">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="939a5-208">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="939a5-208">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="939a5-209">Входные данные</span><span class="sxs-lookup"><span data-stu-id="939a5-209">INPUTS</span></span>

### <span data-ttu-id="939a5-210">None</span><span class="sxs-lookup"><span data-stu-id="939a5-210">None</span></span>
<span data-ttu-id="939a5-211">Вы не можете передать входные данные в `Set-PSBreakpoint` .</span><span class="sxs-lookup"><span data-stu-id="939a5-211">You cannot pipe input to `Set-PSBreakpoint`.</span></span>

## <span data-ttu-id="939a5-212">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="939a5-212">OUTPUTS</span></span>

### <span data-ttu-id="939a5-213">Объект точки останова (System. Management. Automation. Линебреакпоинт, System. Management. Automation. Вариаблебреакпоинт, System. Management. Automation. Коммандбреакпоинт)</span><span class="sxs-lookup"><span data-stu-id="939a5-213">Breakpoint object (System.Management.Automation.LineBreakpoint, System.Management.Automation.VariableBreakpoint, System.Management.Automation.CommandBreakpoint)</span></span>

<span data-ttu-id="939a5-214">`Set-PSBreakpoint` Возвращает объект, представляющий каждую точку останова, которую он задает.</span><span class="sxs-lookup"><span data-stu-id="939a5-214">`Set-PSBreakpoint` returns an object that represents each breakpoint that it sets.</span></span>

## <span data-ttu-id="939a5-215">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="939a5-215">NOTES</span></span>

- <span data-ttu-id="939a5-216">`Set-PSBreakpoint` невозможно установить точку останова на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="939a5-216">`Set-PSBreakpoint` cannot set a breakpoint on a remote computer.</span></span> <span data-ttu-id="939a5-217">Для отладки сценария на удаленном компьютере скопируйте сценарий на локальный компьютер, а затем выполните отладку локально.</span><span class="sxs-lookup"><span data-stu-id="939a5-217">To debug a script on a remote computer, copy the script to the local computer and then debug it locally.</span></span>
- <span data-ttu-id="939a5-218">При установке точки останова более чем в одной строке, команде или переменной `Set-PSBreakpoint` создает объект точки останова для каждой записи.</span><span class="sxs-lookup"><span data-stu-id="939a5-218">When you set a breakpoint on more than one line, command, or variable, `Set-PSBreakpoint` generates a breakpoint object for each entry.</span></span>
- <span data-ttu-id="939a5-219">При задании точки останова в функции или переменной в командной строке можно задать точку останова до или после создания функции или переменной.</span><span class="sxs-lookup"><span data-stu-id="939a5-219">When setting a breakpoint on a function or variable at the command prompt, you can set the breakpoint before or after you create the function or variable.</span></span>

## <span data-ttu-id="939a5-220">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="939a5-220">RELATED LINKS</span></span>

[<span data-ttu-id="939a5-221">Disable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="939a5-221">Disable-PSBreakpoint</span></span>](Disable-PSBreakpoint.md)

[<span data-ttu-id="939a5-222">Enable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="939a5-222">Enable-PSBreakpoint</span></span>](Enable-PSBreakpoint.md)

[<span data-ttu-id="939a5-223">Get-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="939a5-223">Get-PSBreakpoint</span></span>](Get-PSBreakpoint.md)

[<span data-ttu-id="939a5-224">Get-PSCallStack</span><span class="sxs-lookup"><span data-stu-id="939a5-224">Get-PSCallStack</span></span>](Get-PSCallStack.md)

[<span data-ttu-id="939a5-225">Remove-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="939a5-225">Remove-PSBreakpoint</span></span>](Remove-PSBreakpoint.md)

