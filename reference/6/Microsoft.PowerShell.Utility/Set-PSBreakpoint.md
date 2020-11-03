---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/24/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/set-psbreakpoint?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSBreakpoint
ms.openlocfilehash: 3f6720ee2235438a3f71c4efd6fb4083360bd520
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228781"
---
# <span data-ttu-id="6f4b7-103">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="6f4b7-103">Set-PSBreakpoint</span></span>

## <span data-ttu-id="6f4b7-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="6f4b7-104">SYNOPSIS</span></span>
<span data-ttu-id="6f4b7-105">Устанавливает точку останова на строке, команде или переменной.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-105">Sets a breakpoint on a line, command, or variable.</span></span>

## <span data-ttu-id="6f4b7-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6f4b7-106">SYNTAX</span></span>

### <span data-ttu-id="6f4b7-107">Строка (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="6f4b7-107">Line (Default)</span></span>

```
Set-PSBreakpoint [-Action <ScriptBlock>] [[-Column] <Int32>] [-Line] <Int32[]> [-Script] <String[]>
 [<CommonParameters>]
```

### <span data-ttu-id="6f4b7-108">Get-Help</span><span class="sxs-lookup"><span data-stu-id="6f4b7-108">Command</span></span>

```
Set-PSBreakpoint [-Action <ScriptBlock>] -Command <String[]> [[-Script] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="6f4b7-109">Переменная</span><span class="sxs-lookup"><span data-stu-id="6f4b7-109">Variable</span></span>

```
Set-PSBreakpoint [-Action <ScriptBlock>] [[-Script] <String[]>] -Variable <String[]>
 [-Mode <VariableAccessMode>] [<CommonParameters>]
```

## <span data-ttu-id="6f4b7-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6f4b7-110">DESCRIPTION</span></span>

<span data-ttu-id="6f4b7-111">`Set-PSBreakpoint`Командлет задает точку останова в скрипте или в любой команде, выполняемой в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-111">The `Set-PSBreakpoint` cmdlet sets a breakpoint in a script or in any command run in the current session.</span></span> <span data-ttu-id="6f4b7-112">Можно использовать `Set-PSBreakpoint` для установки точки останова перед выполнением сценария или выполнением команды или во время отладки, если остановлена в другой точке останова.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-112">You can use `Set-PSBreakpoint` to set a breakpoint before executing a script or running a command, or during debugging, when stopped at another breakpoint.</span></span>

<span data-ttu-id="6f4b7-113">`Set-PSBreakpoint` невозможно установить точку останова на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-113">`Set-PSBreakpoint` cannot set a breakpoint on a remote computer.</span></span> <span data-ttu-id="6f4b7-114">Для отладки сценария на удаленном компьютере скопируйте сценарий на локальный компьютер, а затем выполните отладку локально.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-114">To debug a script on a remote computer, copy the script to the local computer and then debug it locally.</span></span>

<span data-ttu-id="6f4b7-115">Каждая `Set-PSBreakpoint` команда создает один из следующих трех типов точек останова:</span><span class="sxs-lookup"><span data-stu-id="6f4b7-115">Each `Set-PSBreakpoint` command creates one of the following three types of breakpoints:</span></span>

- <span data-ttu-id="6f4b7-116">Точка останова в строке — задает точки останова в определенных координатах строки и столбца.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-116">Line breakpoint - Sets breakpoints at particular line and column coordinates.</span></span>
- <span data-ttu-id="6f4b7-117">Точка останова команды — задает точки останова для команд и функций.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-117">Command breakpoint - Sets breakpoints on commands and functions.</span></span>
- <span data-ttu-id="6f4b7-118">Точка останова — задает точки останова для переменных.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-118">Variable breakpoint - Sets breakpoints on variables.</span></span>

<span data-ttu-id="6f4b7-119">Точку останова можно задать в нескольких строках, командах или переменных в одной `Set-PSBreakpoint` команде, но каждая `Set-PSBreakpoint` команда устанавливает только один тип точки останова.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-119">You can set a breakpoint on multiple lines, commands, or variables in a single `Set-PSBreakpoint` command, but each `Set-PSBreakpoint` command sets only one type of breakpoint.</span></span>

<span data-ttu-id="6f4b7-120">В точке останова PowerShell временно останавливает выполнение и передает управление отладчику.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-120">At a breakpoint, PowerShell temporarily stops executing and gives control to the debugger.</span></span> <span data-ttu-id="6f4b7-121">Командная строка изменится на `DBG\>` , а набор команд отладчика станет доступным для использования.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-121">The command prompt changes to `DBG\>`, and a set of debugger commands become available for use.</span></span> <span data-ttu-id="6f4b7-122">Однако можно использовать параметр **Action** , чтобы указать альтернативный ответ, например условия для точки останова или инструкции для выполнения дополнительных задач, таких как ведение журнала или диагностика.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-122">However, you can use the **Action** parameter to specify an alternate response, such as conditions for the breakpoint or instructions to perform additional tasks such as logging or diagnostics.</span></span>

<span data-ttu-id="6f4b7-123">`Set-PSBreakpoint`Командлет — это один из нескольких командлетов, предназначенных для отладки скриптов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-123">The `Set-PSBreakpoint` cmdlet is one of several cmdlets designed for debugging PowerShell scripts.</span></span>
<span data-ttu-id="6f4b7-124">Дополнительные сведения о отладчике PowerShell см. в разделе [about_Debuggers](../Microsoft.PowerShell.Core/About/about_Debuggers.md).</span><span class="sxs-lookup"><span data-stu-id="6f4b7-124">For more information about the PowerShell debugger, see [about_Debuggers](../Microsoft.PowerShell.Core/About/about_Debuggers.md).</span></span>

## <span data-ttu-id="6f4b7-125">Примеры</span><span class="sxs-lookup"><span data-stu-id="6f4b7-125">EXAMPLES</span></span>

### <span data-ttu-id="6f4b7-126">Пример 1. Задание точки останова в строке</span><span class="sxs-lookup"><span data-stu-id="6f4b7-126">Example 1: Set a breakpoint on a line</span></span>

<span data-ttu-id="6f4b7-127">В этом примере задается точка останова в строке 5 в скрипте Sample.ps1.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-127">This example sets a breakpoint at line 5 in the Sample.ps1 script.</span></span> <span data-ttu-id="6f4b7-128">При выполнении скрипта выполнение останавливается непосредственно перед выполнением строки 5.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-128">When the script runs, execution stops immediately before line 5 would execute.</span></span>

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

<span data-ttu-id="6f4b7-129">При установке новой точки останова по номеру строки `Set-PSBreakpoint` командлет создает объект точки останова строки ( **System. Management. Automation. линебреакпоинт** ), включающий идентификатор точки останова и число попаданий.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-129">When you set a new breakpoint by line number, the `Set-PSBreakpoint` cmdlet generates a line breakpoint object ( **System.Management.Automation.LineBreakpoint** ) that includes the breakpoint ID and hit count.</span></span>

### <span data-ttu-id="6f4b7-130">Пример 2. Установка точки останова в функции</span><span class="sxs-lookup"><span data-stu-id="6f4b7-130">Example 2: Set a breakpoint on a function</span></span>

<span data-ttu-id="6f4b7-131">В этом примере создается точка останова команды для `Increment` функции в командлете Sample.ps1.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-131">This example creates a command breakpoint on the `Increment` function in the Sample.ps1 cmdlet.</span></span> <span data-ttu-id="6f4b7-132">Сценарий останавливает выполнение непосредственно перед каждым вызовом указанной функции.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-132">The script stops executing immediately before each call to the specified function.</span></span>

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

<span data-ttu-id="6f4b7-133">Результатом является объект точки останова команды.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-133">The result is a command breakpoint object.</span></span> <span data-ttu-id="6f4b7-134">Перед выполнением скрипта значение свойства **хиткаунт** равно 0.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-134">Before the script runs, the value of the **HitCount** property is 0.</span></span>

### <span data-ttu-id="6f4b7-135">Пример 3. Установка точки останова в переменной</span><span class="sxs-lookup"><span data-stu-id="6f4b7-135">Example 3: Set a breakpoint on a variable</span></span>

<span data-ttu-id="6f4b7-136">В этом примере задается точка останова на **серверной** переменной в скрипте Sample.ps1.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-136">This example sets a breakpoint on the **Server** variable in the Sample.ps1 script.</span></span> <span data-ttu-id="6f4b7-137">Он использует параметр **mode** со значением **ReadWrite** , чтобы прерывать выполнение при считывании значения переменной и непосредственно перед изменением значения.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-137">It uses the **Mode** parameter with a value of **ReadWrite** to stop execution when the value of the variable is read and just before the value changes.</span></span>

```powershell
Set-PSBreakpoint -Script "sample.ps1" -Variable "Server" -Mode ReadWrite
```

### <span data-ttu-id="6f4b7-138">Пример 4. Установка точки останова для каждой команды, которая начинается с указанного текста</span><span class="sxs-lookup"><span data-stu-id="6f4b7-138">Example 4: Set a breakpoint on every command that begins with specified text</span></span>

<span data-ttu-id="6f4b7-139">В этом примере задается точка останова для каждой команды в Sample.ps1 скрипте, которая начинается с "Write", например `Write-Host` .</span><span class="sxs-lookup"><span data-stu-id="6f4b7-139">This example sets a breakpoint on every command in the Sample.ps1 script that begins with "write", such as `Write-Host`.</span></span>

```powershell
Set-PSBreakpoint -Script Sample.ps1 -Command "write*"
```

### <span data-ttu-id="6f4b7-140">Пример 5. Задание точки останова в зависимости от значения переменной</span><span class="sxs-lookup"><span data-stu-id="6f4b7-140">Example 5: Set a breakpoint depending on the value of a variable</span></span>

<span data-ttu-id="6f4b7-141">В этом примере выполнение `DiskTest` функции в скрипте Test.ps1 прекращается, только если значение `$Disk` переменной больше 2.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-141">This example stops execution at the `DiskTest` function in the Test.ps1 script only when the value of the `$Disk` variable is greater than 2.</span></span>

```powershell
Set-PSBreakpoint -Script "test.ps1" -Command "DiskTest" -Action { if ($Disk -gt 2) { break } }
```

<span data-ttu-id="6f4b7-142">Значением **действия** является блок скрипта, который проверяет значение `$Disk` переменной в функции.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-142">The value of the **Action** is a script block that tests the value of the `$Disk` variable in the function.</span></span>

<span data-ttu-id="6f4b7-143">Действие использует `break` ключевое слово для отмены выполнения при соблюдении условия.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-143">The action uses the `break` keyword to stop execution if the condition is met.</span></span> <span data-ttu-id="6f4b7-144">Альтернативный вариант (и значение по умолчанию) будет **продолжен** .</span><span class="sxs-lookup"><span data-stu-id="6f4b7-144">The alternative (and the default) is **Continue** .</span></span>

### <span data-ttu-id="6f4b7-145">Пример 6. Установка точки останова в функции</span><span class="sxs-lookup"><span data-stu-id="6f4b7-145">Example 6: Set a breakpoint on a function</span></span>

<span data-ttu-id="6f4b7-146">В этом примере задается точка останова для `CheckLog` функции.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-146">This example sets a breakpoint on the `CheckLog` function.</span></span> <span data-ttu-id="6f4b7-147">Поскольку команда не указывает сценарий, точка останова устанавливается для любого объекта, который выполняется в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-147">Because the command does not specify a script, the breakpoint is set on anything that runs in the current session.</span></span> <span data-ttu-id="6f4b7-148">Отладчик останавливается при вызове функции, а не при ее объявлении.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-148">The debugger breaks when the function is called, not when it is declared.</span></span>

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

### <span data-ttu-id="6f4b7-149">Пример 7. Установка точек останова в нескольких строках</span><span class="sxs-lookup"><span data-stu-id="6f4b7-149">Example 7: Set breakpoints on multiple lines</span></span>

<span data-ttu-id="6f4b7-150">В этом примере задаются три точки останова по строке в скрипте Sample.ps1.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-150">This example sets three line breakpoints in the Sample.ps1 script.</span></span> <span data-ttu-id="6f4b7-151">Она задает одну точку останова в столбце 2 каждой из строк, указанных в сценарии.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-151">It sets one breakpoint at column 2 on each of the lines specified in the script.</span></span> <span data-ttu-id="6f4b7-152">Действие, указанное в параметре **Action** , применяется ко всем точкам останова.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-152">The action specified in the **Action** parameter applies to all breakpoints.</span></span>

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

## <span data-ttu-id="6f4b7-153">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6f4b7-153">PARAMETERS</span></span>

### <span data-ttu-id="6f4b7-154">-Action</span><span class="sxs-lookup"><span data-stu-id="6f4b7-154">-Action</span></span>

<span data-ttu-id="6f4b7-155">Задает команды, которые выполняются в каждой точке останова вместо останова.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-155">Specifies commands that run at each breakpoint instead of breaking.</span></span> <span data-ttu-id="6f4b7-156">Введите блок сценария, содержащий команды.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-156">Enter a script block that contains the commands.</span></span> <span data-ttu-id="6f4b7-157">Этот параметр можно использовать для задания условных точек останова или выполнения других задач, таких как тестирование или ведение журнала.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-157">You can use this parameter to set conditional breakpoints or to perform other tasks, such as testing or logging.</span></span>

<span data-ttu-id="6f4b7-158">Если этот параметр пропущен или не указаны никакие действия, выполнение останавливается в точке останова и запускается отладчик.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-158">If this parameter is omitted, or no action is specified, execution stops at the breakpoint, and the debugger starts.</span></span>

<span data-ttu-id="6f4b7-159">При использовании параметра **Action** блок сценария действия выполняется в каждой точке останова.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-159">When the **Action** parameter is used, the Action script block runs at each breakpoint.</span></span> <span data-ttu-id="6f4b7-160">Выполнение не останавливается, если блок сценария не включает ключевое слово Break.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-160">Execution does not stop unless the script block includes the Break keyword.</span></span> <span data-ttu-id="6f4b7-161">При использовании ключевого слова Continue в блоке сценария выполнение возобновляется до следующей точки останова.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-161">If you use the Continue keyword in the script block, execution resumes until the next breakpoint.</span></span>

<span data-ttu-id="6f4b7-162">Дополнительные сведения см. в разделе [about_Script_Blocks](../Microsoft.PowerShell.Core/About/about_Script_Blocks.md), [about_Break](../Microsoft.PowerShell.Core/About/about_Break.md)и [about_Continue](../Microsoft.PowerShell.Core/About/about_Continue.md).</span><span class="sxs-lookup"><span data-stu-id="6f4b7-162">For more information, see [about_Script_Blocks](../Microsoft.PowerShell.Core/About/about_Script_Blocks.md), [about_Break](../Microsoft.PowerShell.Core/About/about_Break.md), and [about_Continue](../Microsoft.PowerShell.Core/About/about_Continue.md).</span></span>

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

### <span data-ttu-id="6f4b7-163">-Column</span><span class="sxs-lookup"><span data-stu-id="6f4b7-163">-Column</span></span>

<span data-ttu-id="6f4b7-164">Указывает номер столбца в файле сценария, в котором выполнение останавливается.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-164">Specifies the column number of the column in the script file on which execution stops.</span></span> <span data-ttu-id="6f4b7-165">Введите только один номер столбца.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-165">Enter only one column number.</span></span> <span data-ttu-id="6f4b7-166">Значение по умолчанию: столбец 1.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-166">The default is column 1.</span></span>

<span data-ttu-id="6f4b7-167">Значение столбца используется со значением параметра **line** для указания точки останова.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-167">The Column value is used with the value of the **Line** parameter to specify the breakpoint.</span></span> <span data-ttu-id="6f4b7-168">Если параметр **line** задает несколько строк, параметр **Column** задает точку останова в указанном столбце для каждой из указанных строк.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-168">If the **Line** parameter specifies multiple lines, the **Column** parameter sets a breakpoint at the specified column on each of the specified lines.</span></span> <span data-ttu-id="6f4b7-169">PowerShell прекращает выполнение до инструкции или выражения, включающего символ в указанной строке и позиции столбца.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-169">PowerShell stops executing before the statement or expression that includes the character at the specified line and column position.</span></span>

<span data-ttu-id="6f4b7-170">Столбцы отсчитываются от верхней левой границы, начиная с номера столбца 1 (не 0).</span><span class="sxs-lookup"><span data-stu-id="6f4b7-170">Columns are counted from the top left margin beginning with column number 1 (not 0).</span></span> <span data-ttu-id="6f4b7-171">Если указать столбец, который не существует в сценарии, ошибка не объявляется, однако точка останова не выполняется.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-171">If you specify a column that does not exist in the script, an error is not declared, but the breakpoint is never executed.</span></span>

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

### <span data-ttu-id="6f4b7-172">-Command</span><span class="sxs-lookup"><span data-stu-id="6f4b7-172">-Command</span></span>

<span data-ttu-id="6f4b7-173">Задает точку останова команды.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-173">Sets a command breakpoint.</span></span> <span data-ttu-id="6f4b7-174">Введите имена командлетов, например `Get-Process` , или имена функций.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-174">Enter cmdlet names, such as `Get-Process`, or function names.</span></span> <span data-ttu-id="6f4b7-175">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-175">Wildcards are permitted.</span></span>

<span data-ttu-id="6f4b7-176">Выполнение останавливается непосредственно перед выполнением каждого экземпляра каждой команды.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-176">Execution stops just before each instance of each command is executed.</span></span> <span data-ttu-id="6f4b7-177">Если команда является функцией, выполнение останавливается при каждом вызове функции и в каждом разделе BEGIN, PROCESS и END.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-177">If the command is a function, execution stops each time the function is called and at each BEGIN, PROCESS, and END section.</span></span>

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

### <span data-ttu-id="6f4b7-178">-Line</span><span class="sxs-lookup"><span data-stu-id="6f4b7-178">-Line</span></span>

<span data-ttu-id="6f4b7-179">Задает точку останова строки в сценарии.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-179">Sets a line breakpoint in a script.</span></span> <span data-ttu-id="6f4b7-180">Введите один или несколько номеров строк, разделенных запятыми.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-180">Enter one or more line numbers, separated by commas.</span></span> <span data-ttu-id="6f4b7-181">PowerShell останавливается сразу перед выполнением инструкции, которая начинается на каждой из указанных строк.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-181">PowerShell stops immediately before executing the statement that begins on each of the specified lines.</span></span>

<span data-ttu-id="6f4b7-182">Строки отсчитываются от верхней левой границы файла сценария, начиная с номера строки 1 (не 0).</span><span class="sxs-lookup"><span data-stu-id="6f4b7-182">Lines are counted from the top left margin of the script file beginning with line number 1 (not 0).</span></span>
<span data-ttu-id="6f4b7-183">Если указать пустую строку, выполнение останавливается перед следующей непустой строкой.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-183">If you specify a blank line, execution stops before the next non-blank line.</span></span> <span data-ttu-id="6f4b7-184">Если строка выходит за пределы диапазона, останов не выполняется.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-184">If the line is out of range, the breakpoint is never hit.</span></span>

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

### <span data-ttu-id="6f4b7-185">-Mode</span><span class="sxs-lookup"><span data-stu-id="6f4b7-185">-Mode</span></span>

<span data-ttu-id="6f4b7-186">Задает режим доступа, который активирует переменные точки останова.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-186">Specifies the mode of access that triggers variable breakpoints.</span></span> <span data-ttu-id="6f4b7-187">Значение по умолчанию — **Write** .</span><span class="sxs-lookup"><span data-stu-id="6f4b7-187">The default is **Write** .</span></span>

<span data-ttu-id="6f4b7-188">Этот параметр допустим только в том случае, если в команде используется параметр **variable** .</span><span class="sxs-lookup"><span data-stu-id="6f4b7-188">This parameter is valid only when the **Variable** parameter is used in the command.</span></span> <span data-ttu-id="6f4b7-189">Режим применяется ко всем точкам останова, заданным в команде.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-189">The mode applies to all breakpoints set in the command.</span></span> <span data-ttu-id="6f4b7-190">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="6f4b7-190">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="6f4b7-191">**Запись** — останавливает выполнение непосредственно перед записью нового значения в переменную.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-191">**Write** - Stops execution immediately before a new value is written to the variable.</span></span>
- <span data-ttu-id="6f4b7-192">**Чтение** — остановка выполнения при считывании переменной, то есть при доступе к ее значению, назначению, отображению или использования.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-192">**Read** - Stops execution when the variable is read, that is, when its value is accessed, either to be assigned, displayed, or used.</span></span> <span data-ttu-id="6f4b7-193">В режиме чтения выполнение не прекращается при изменении значения переменной.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-193">In read mode, execution does not stop when the value of the variable changes.</span></span>
- <span data-ttu-id="6f4b7-194">**ReadWrite** — останавливает выполнение, когда переменная считывается или записывается.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-194">**ReadWrite** - Stops execution when the variable is read or written.</span></span>

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

### <span data-ttu-id="6f4b7-195">-Script</span><span class="sxs-lookup"><span data-stu-id="6f4b7-195">-Script</span></span>

<span data-ttu-id="6f4b7-196">Указывает массив файлов скрипта, в котором этот командлет задает точку останова.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-196">Specifies an array of script files that this cmdlet sets a breakpoint in.</span></span> <span data-ttu-id="6f4b7-197">Введите пути и имена одного или нескольких файлов сценариев.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-197">Enter the paths and file names of one or more script files.</span></span> <span data-ttu-id="6f4b7-198">Если файлы находятся в текущем каталоге, путь можно опустить.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-198">If the files are in the current directory, you can omit the path.</span></span>
<span data-ttu-id="6f4b7-199">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-199">Wildcards are permitted.</span></span>

<span data-ttu-id="6f4b7-200">По умолчанию точки останова переменной и точки останова команды задаются в любых командах, которые выполняются в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-200">By default, variable breakpoints and command breakpoints are set on any command that runs in the current session.</span></span> <span data-ttu-id="6f4b7-201">Этот параметр является обязательным, только если задается точка останова строки.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-201">This parameter is required only when setting a line breakpoint.</span></span>

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

### <span data-ttu-id="6f4b7-202">-Variable</span><span class="sxs-lookup"><span data-stu-id="6f4b7-202">-Variable</span></span>

<span data-ttu-id="6f4b7-203">Задает массив переменных, на которых этот командлет задает точки останова.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-203">Specifies an array of variables that this cmdlet sets breakpoints on.</span></span> <span data-ttu-id="6f4b7-204">Введите разделенный запятыми список переменных без знака доллара ( `$` ).</span><span class="sxs-lookup"><span data-stu-id="6f4b7-204">Enter a comma-separated list of variables without dollar signs (`$`).</span></span>

<span data-ttu-id="6f4b7-205">Используйте параметр **mode** для определения режима доступа, запускающего точки останова.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-205">Use the **Mode** parameter to determine the mode of access that triggers the breakpoints.</span></span> <span data-ttu-id="6f4b7-206">Режим по умолчанию, Write, останавливает выполнение непосредственно перед записью нового значения в переменную.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-206">The default mode, Write, stops execution just before a new value is written to the variable.</span></span>

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

### <span data-ttu-id="6f4b7-207">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="6f4b7-207">CommonParameters</span></span>

<span data-ttu-id="6f4b7-208">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-208">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6f4b7-209">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="6f4b7-209">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6f4b7-210">Входные данные</span><span class="sxs-lookup"><span data-stu-id="6f4b7-210">INPUTS</span></span>

### <span data-ttu-id="6f4b7-211">Нет</span><span class="sxs-lookup"><span data-stu-id="6f4b7-211">None</span></span>
<span data-ttu-id="6f4b7-212">Вы не можете передать входные данные в `Set-PSBreakpoint` .</span><span class="sxs-lookup"><span data-stu-id="6f4b7-212">You cannot pipe input to `Set-PSBreakpoint`.</span></span>

## <span data-ttu-id="6f4b7-213">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="6f4b7-213">OUTPUTS</span></span>

### <span data-ttu-id="6f4b7-214">Объект точки останова (System. Management. Automation. Линебреакпоинт, System. Management. Automation. Вариаблебреакпоинт, System. Management. Automation. Коммандбреакпоинт)</span><span class="sxs-lookup"><span data-stu-id="6f4b7-214">Breakpoint object (System.Management.Automation.LineBreakpoint, System.Management.Automation.VariableBreakpoint, System.Management.Automation.CommandBreakpoint)</span></span>

<span data-ttu-id="6f4b7-215">`Set-PSBreakpoint` Возвращает объект, представляющий каждую точку останова, которую он задает.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-215">`Set-PSBreakpoint` returns an object that represents each breakpoint that it sets.</span></span>

## <span data-ttu-id="6f4b7-216">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="6f4b7-216">NOTES</span></span>

- <span data-ttu-id="6f4b7-217">`Set-PSBreakpoint` невозможно установить точку останова на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-217">`Set-PSBreakpoint` cannot set a breakpoint on a remote computer.</span></span> <span data-ttu-id="6f4b7-218">Для отладки сценария на удаленном компьютере скопируйте сценарий на локальный компьютер, а затем выполните отладку локально.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-218">To debug a script on a remote computer, copy the script to the local computer and then debug it locally.</span></span>
- <span data-ttu-id="6f4b7-219">При установке точки останова более чем в одной строке, команде или переменной `Set-PSBreakpoint` создает объект точки останова для каждой записи.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-219">When you set a breakpoint on more than one line, command, or variable, `Set-PSBreakpoint` generates a breakpoint object for each entry.</span></span>
- <span data-ttu-id="6f4b7-220">При задании точки останова в функции или переменной в командной строке можно задать точку останова до или после создания функции или переменной.</span><span class="sxs-lookup"><span data-stu-id="6f4b7-220">When setting a breakpoint on a function or variable at the command prompt, you can set the breakpoint before or after you create the function or variable.</span></span>

## <span data-ttu-id="6f4b7-221">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="6f4b7-221">RELATED LINKS</span></span>

[<span data-ttu-id="6f4b7-222">Disable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="6f4b7-222">Disable-PSBreakpoint</span></span>](Disable-PSBreakpoint.md)

[<span data-ttu-id="6f4b7-223">Enable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="6f4b7-223">Enable-PSBreakpoint</span></span>](Enable-PSBreakpoint.md)

[<span data-ttu-id="6f4b7-224">Get-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="6f4b7-224">Get-PSBreakpoint</span></span>](Get-PSBreakpoint.md)

[<span data-ttu-id="6f4b7-225">Get-PSCallStack</span><span class="sxs-lookup"><span data-stu-id="6f4b7-225">Get-PSCallStack</span></span>](Get-PSCallStack.md)

[<span data-ttu-id="6f4b7-226">Remove-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="6f4b7-226">Remove-PSBreakpoint</span></span>](Remove-PSBreakpoint.md)
