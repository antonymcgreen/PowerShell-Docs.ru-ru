---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 05/15/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-psbreakpoint?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSBreakpoint
ms.openlocfilehash: 78691b806fe68aaa8d9e502d28e6f3967867f95b
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604557"
---
# <span data-ttu-id="8ced6-102">Get-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="8ced6-102">Get-PSBreakpoint</span></span>

## <span data-ttu-id="8ced6-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="8ced6-103">SYNOPSIS</span></span>
<span data-ttu-id="8ced6-104">Возвращает точки останова, установленные в рамках текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="8ced6-104">Gets the breakpoints that are set in the current session.</span></span>

## <span data-ttu-id="8ced6-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8ced6-105">SYNTAX</span></span>

### <span data-ttu-id="8ced6-106">Скрипт (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="8ced6-106">Script (Default)</span></span>

```
Get-PSBreakpoint [-Script <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="8ced6-107">Переменная</span><span class="sxs-lookup"><span data-stu-id="8ced6-107">Variable</span></span>

```
Get-PSBreakpoint [-Script <String[]>] -Variable <String[]> [<CommonParameters>]
```

### <span data-ttu-id="8ced6-108">Get-Help</span><span class="sxs-lookup"><span data-stu-id="8ced6-108">Command</span></span>

```
Get-PSBreakpoint [-Script <String[]>] -Command <String[]> [<CommonParameters>]
```

### <span data-ttu-id="8ced6-109">Тип</span><span class="sxs-lookup"><span data-stu-id="8ced6-109">Type</span></span>

```
Get-PSBreakpoint [-Script <String[]>] [-Type] <BreakpointType[]> [<CommonParameters>]
```

### <span data-ttu-id="8ced6-110">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="8ced6-110">Id</span></span>

```
Get-PSBreakpoint [-Id] <Int32[]> [<CommonParameters>]
```

## <span data-ttu-id="8ced6-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8ced6-111">DESCRIPTION</span></span>

<span data-ttu-id="8ced6-112">Командлет **Get-PSBreakpoint** возвращает точки останова, установленные в рамках текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="8ced6-112">The **Get-PSBreakPoint** cmdlet gets the breakpoints that are set in the current session.</span></span>
<span data-ttu-id="8ced6-113">С помощью параметров командлета можно получить определенные точки останова.</span><span class="sxs-lookup"><span data-stu-id="8ced6-113">You can use the cmdlet parameters to get particular breakpoints.</span></span>

<span data-ttu-id="8ced6-114">Точка останова — это место в команде или сценарии, в котором выполнение временно приостанавливается, чтобы вы могли изучить инструкции.</span><span class="sxs-lookup"><span data-stu-id="8ced6-114">A breakpoint is a point in a command or script where execution stops temporarily so that you can examine the instructions.</span></span>
<span data-ttu-id="8ced6-115">**Get-PSBreakpoint** — это один из нескольких командлетов, предназначенных для отладки сценариев и команд PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8ced6-115">**Get-PSBreakpoint** is one of several cmdlets designed for debugging PowerShell scripts and commands.</span></span> <span data-ttu-id="8ced6-116">Дополнительные сведения о отладчике PowerShell см. в разделе about_Debuggers.</span><span class="sxs-lookup"><span data-stu-id="8ced6-116">For more information about the PowerShell debugger, see about_Debuggers.</span></span>

## <span data-ttu-id="8ced6-117">Примеры</span><span class="sxs-lookup"><span data-stu-id="8ced6-117">EXAMPLES</span></span>

### <span data-ttu-id="8ced6-118">Пример 1. Получение всех точек останова для всех скриптов и функций</span><span class="sxs-lookup"><span data-stu-id="8ced6-118">Example 1: Get all breakpoints for all scripts and functions</span></span>

```
PS C:\> Get-PSBreakpoint
```

<span data-ttu-id="8ced6-119">Эта команда возвращает все точки останова, установленные во всех сценариях и функциях текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="8ced6-119">This command gets all breakpoints set on all scripts and functions in the current session.</span></span>

### <span data-ttu-id="8ced6-120">Пример 2. Получение точек останова по идентификатору</span><span class="sxs-lookup"><span data-stu-id="8ced6-120">Example 2: Get breakpoints by ID</span></span>

```
PS C:\> Get-PSBreakpoint -Id 2
Function   :
IncrementAction     :
Enabled    :
TrueHitCount   : 0
Id         : 2
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1
```

<span data-ttu-id="8ced6-121">Эта команда возвращает точку останова с идентификатором 2.</span><span class="sxs-lookup"><span data-stu-id="8ced6-121">This command gets the breakpoint with breakpoint ID 2.</span></span>

### <span data-ttu-id="8ced6-122">Пример 3. Передача идентификатора в командлет Get-PSBreakpoint по конвейеру</span><span class="sxs-lookup"><span data-stu-id="8ced6-122">Example 3: Pipe an ID to Get-PSBreakpoint</span></span>

```
PS C:\> $B = Set-PSBreakpoint -Script "sample.ps1" -Command "Increment"
PS C:\> $B.Id | Get-PSBreakpoint
```

<span data-ttu-id="8ced6-123">Эти команды показывают, как получить точку останова путем передачи ее идентификатора по конвейеру в командлет **Get-PSBreakpoint**.</span><span class="sxs-lookup"><span data-stu-id="8ced6-123">These commands show how to get a breakpoint by piping a breakpoint ID to **Get-PSBreakpoint**.</span></span>

<span data-ttu-id="8ced6-124">В первой команде используется командлет Set-PSBreakpoint для создания точки останова в функции Increment в сценарии Sample.ps1.</span><span class="sxs-lookup"><span data-stu-id="8ced6-124">The first command uses the Set-PSBreakpoint cmdlet to create a breakpoint on the Increment function in the Sample.ps1 script.</span></span> <span data-ttu-id="8ced6-125">Объект точки останова сохраняется в переменной $B.</span><span class="sxs-lookup"><span data-stu-id="8ced6-125">It saves the breakpoint object in the $B variable.</span></span>

<span data-ttu-id="8ced6-126">Во второй команде используется оператор-точка (.) для получения свойства Id объекта точки останова в переменной $B.</span><span class="sxs-lookup"><span data-stu-id="8ced6-126">The second command uses the dot operator (.) to get the Id property of the breakpoint object in the $B variable.</span></span> <span data-ttu-id="8ced6-127">С помощью конвейерного оператора (|) идентификатор передается в командлет **Get-PSBreakpoint**.</span><span class="sxs-lookup"><span data-stu-id="8ced6-127">It uses a pipeline operator (|) to send the ID to the **Get-PSBreakpoint** cmdlet.</span></span>

<span data-ttu-id="8ced6-128">В результате командлет **Get-PSBreakpoint** возвращает точку останова с указанным идентификатором.</span><span class="sxs-lookup"><span data-stu-id="8ced6-128">As a result, **Get-PSBreakpoint** gets the breakpoint with the specified ID.</span></span>

### <span data-ttu-id="8ced6-129">Пример 4. Возвращение точек останова в указанных файлах скриптов</span><span class="sxs-lookup"><span data-stu-id="8ced6-129">Example 4: Get breakpoints in specified script files</span></span>

```
PS C:\> Get-PSBreakpoint -Script "Sample.ps1, SupportScript.ps1"
```

<span data-ttu-id="8ced6-130">Эта команда возвращает все точки останова в файлах Sample.ps1 и SupportScript.ps1.</span><span class="sxs-lookup"><span data-stu-id="8ced6-130">This command gets all of the breakpoints in the Sample.ps1 and SupportScript.ps1 files.</span></span>

<span data-ttu-id="8ced6-131">Она не возвращает точки останова, которые могут быть установлены в других скриптах или функциях в рамках сеанса.</span><span class="sxs-lookup"><span data-stu-id="8ced6-131">This command does not get other breakpoints that might be set in other scripts or on functions in the session.</span></span>

### <span data-ttu-id="8ced6-132">Пример 5. Возвращение точек останова в указанных командлетах</span><span class="sxs-lookup"><span data-stu-id="8ced6-132">Example 5: Get breakpoints in specified cmdlets</span></span>

```
PS C:\> Get-PSBreakpoint -Command "Read-Host, Write-Host" -Script "Sample.ps1"
```

<span data-ttu-id="8ced6-133">Эта команда возвращает все точки останова, установленные в командах Read-Host или Write-Host в файле Sample.ps1.</span><span class="sxs-lookup"><span data-stu-id="8ced6-133">This command gets all Command breakpoints that are set on Read-Host or Write-Host commands in the Sample.ps1 file.</span></span>

### <span data-ttu-id="8ced6-134">Пример 6. Возвращение точек останова команды в указанном файле</span><span class="sxs-lookup"><span data-stu-id="8ced6-134">Example 6: Get Command breakpoints in a specified file</span></span>

```
PS C:\> Get-PSBreakpoint -Type Command -Script "Sample.ps1"
```

<span data-ttu-id="8ced6-135">Эта команда возвращает все точки останова команд в файле Sample.ps1.</span><span class="sxs-lookup"><span data-stu-id="8ced6-135">This command gets all Command breakpoints in the Sample.ps1 file.</span></span>

### <span data-ttu-id="8ced6-136">Пример 7. Получение точек останова по переменной</span><span class="sxs-lookup"><span data-stu-id="8ced6-136">Example 7: Get breakpoints by variable</span></span>

```
PS C:\> Get-PSBreakpoint -Variable "Index, Swap"
```

<span data-ttu-id="8ced6-137">Эта команда возвращает точки останова, установленные для переменных $Index и $Swap в рамках текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="8ced6-137">This command gets breakpoints that are set on the $Index and $Swap variables in the current session.</span></span>

### <span data-ttu-id="8ced6-138">Пример 8. Возвращение всех точек останова строк и переменных в файле</span><span class="sxs-lookup"><span data-stu-id="8ced6-138">Example 8: Get all Line and Variable breakpoints in a file</span></span>

```
PS C:\> Get-PSBreakpoint -Type Line, Variable -Script "Sample.ps1"
```

<span data-ttu-id="8ced6-139">Эта команда возвращает все точки останова строк и переменных в сценарии Sample.ps1.</span><span class="sxs-lookup"><span data-stu-id="8ced6-139">This command gets all line and variable breakpoints in the Sample.ps1 script.</span></span>

## <span data-ttu-id="8ced6-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8ced6-140">PARAMETERS</span></span>

### <span data-ttu-id="8ced6-141">-Command</span><span class="sxs-lookup"><span data-stu-id="8ced6-141">-Command</span></span>

<span data-ttu-id="8ced6-142">Указывает массив точек останова, заданных для команд с указанными именами.</span><span class="sxs-lookup"><span data-stu-id="8ced6-142">Specifies an array of command breakpoints that are set on the specified command names.</span></span>
<span data-ttu-id="8ced6-143">Введите имена команд, например имя командлета или функции.</span><span class="sxs-lookup"><span data-stu-id="8ced6-143">Enter the command names, such as the name of a cmdlet or function.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Command
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8ced6-144">-Id</span><span class="sxs-lookup"><span data-stu-id="8ced6-144">-Id</span></span>

<span data-ttu-id="8ced6-145">Указывает идентификаторы точки останова, которую возвращает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="8ced6-145">Specifies the breakpoint IDs that this cmdlet gets.</span></span>
<span data-ttu-id="8ced6-146">Введите идентификаторы в виде разделенного запятыми списка.</span><span class="sxs-lookup"><span data-stu-id="8ced6-146">Enter the IDs in a comma-separated list.</span></span>
<span data-ttu-id="8ced6-147">Идентификаторы точек останова можно также передать в командлет **Get-PSBreakpoint** по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="8ced6-147">You can also pipe breakpoint IDs to **Get-PSBreakpoint**.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="8ced6-148">-Script</span><span class="sxs-lookup"><span data-stu-id="8ced6-148">-Script</span></span>

<span data-ttu-id="8ced6-149">Указывает массив скриптов, содержащих точки останова.</span><span class="sxs-lookup"><span data-stu-id="8ced6-149">Specifies an array of scripts that contain the breakpoints.</span></span>
<span data-ttu-id="8ced6-150">Введите путь (необязательно) и имена одного или нескольких файлов скриптов.</span><span class="sxs-lookup"><span data-stu-id="8ced6-150">Enter the path (optional) and names of one or more script files.</span></span>
<span data-ttu-id="8ced6-151">Если путь не указан, расположением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="8ced6-151">If you omit the path, the default location is the current directory.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Script, Variable, Command, Type
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="8ced6-152">-Type</span><span class="sxs-lookup"><span data-stu-id="8ced6-152">-Type</span></span>

<span data-ttu-id="8ced6-153">Указывает массив типов точек останова, которые возвращает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="8ced6-153">Specifies an array of breakpoint types that this cmdlet gets.</span></span>
<span data-ttu-id="8ced6-154">Введите один или несколько типов.</span><span class="sxs-lookup"><span data-stu-id="8ced6-154">Enter one or more types.</span></span>
<span data-ttu-id="8ced6-155">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="8ced6-155">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="8ced6-156">Линия</span><span class="sxs-lookup"><span data-stu-id="8ced6-156">Line</span></span>
- <span data-ttu-id="8ced6-157">Get-Help</span><span class="sxs-lookup"><span data-stu-id="8ced6-157">Command</span></span>
- <span data-ttu-id="8ced6-158">Переменная</span><span class="sxs-lookup"><span data-stu-id="8ced6-158">Variable</span></span>

<span data-ttu-id="8ced6-159">Типы точек останова можно также передать в командлет **Get-PSBreakpoint** по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="8ced6-159">You can also pipe breakpoint types to **Get-PSBreakPoint**.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.BreakpointType[]
Parameter Sets: Type
Aliases:
Accepted values: Line, Variable, Command

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="8ced6-160">-Variable</span><span class="sxs-lookup"><span data-stu-id="8ced6-160">-Variable</span></span>

<span data-ttu-id="8ced6-161">Указывает массив точек останова, заданных для переменных с указанными именами.</span><span class="sxs-lookup"><span data-stu-id="8ced6-161">Specifies an array of variable breakpoints that are set on the specified variable names.</span></span>
<span data-ttu-id="8ced6-162">Введите имена переменных без знака доллара.</span><span class="sxs-lookup"><span data-stu-id="8ced6-162">Enter the variable names without dollar signs.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Variable
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8ced6-163">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="8ced6-163">CommonParameters</span></span>

<span data-ttu-id="8ced6-164">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="8ced6-164">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8ced6-165">Дополнительные сведения см. в разделе about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="8ced6-165">For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8ced6-166">Входные данные</span><span class="sxs-lookup"><span data-stu-id="8ced6-166">INPUTS</span></span>

### <span data-ttu-id="8ced6-167">System.Int32, Microsoft.PowerShell.Commands.BreakpointType</span><span class="sxs-lookup"><span data-stu-id="8ced6-167">System.Int32, Microsoft.PowerShell.Commands.BreakpointType</span></span>

<span data-ttu-id="8ced6-168">Идентификаторы и типы точек останова можно передавать в командлет **Get-PSBreakpoint** по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="8ced6-168">You can pipe breakpoint IDs and breakpoint types to **Get-PSBreakPoint**.</span></span>

## <span data-ttu-id="8ced6-169">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="8ced6-169">OUTPUTS</span></span>

### <span data-ttu-id="8ced6-170">System.Management.Automation.Breakpoint</span><span class="sxs-lookup"><span data-stu-id="8ced6-170">System.Management.Automation.Breakpoint</span></span>

<span data-ttu-id="8ced6-171">Командлет **Get-PSBreakpoint** возвращает объекты, которые представляют точки останова в рамках сеанса.</span><span class="sxs-lookup"><span data-stu-id="8ced6-171">**Get-PSBreakPoint** returns objects that represent the breakpoints in the session.</span></span>

## <span data-ttu-id="8ced6-172">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="8ced6-172">NOTES</span></span>

* <span data-ttu-id="8ced6-173">Можно использовать **Get-PSBreakpoint** или его псевдоним "GBP".</span><span class="sxs-lookup"><span data-stu-id="8ced6-173">You can use **Get-PSBreakpoint** or its alias, "gbp".</span></span>

## <span data-ttu-id="8ced6-174">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="8ced6-174">RELATED LINKS</span></span>

[<span data-ttu-id="8ced6-175">Disable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="8ced6-175">Disable-PSBreakpoint</span></span>](Disable-PSBreakpoint.md)

[<span data-ttu-id="8ced6-176">Enable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="8ced6-176">Enable-PSBreakpoint</span></span>](Enable-PSBreakpoint.md)

[<span data-ttu-id="8ced6-177">Get-PSCallStack</span><span class="sxs-lookup"><span data-stu-id="8ced6-177">Get-PSCallStack</span></span>](Get-PSCallStack.md)

[<span data-ttu-id="8ced6-178">Remove-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="8ced6-178">Remove-PSBreakpoint</span></span>](Remove-PSBreakpoint.md)

[<span data-ttu-id="8ced6-179">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="8ced6-179">Set-PSBreakpoint</span></span>](Set-PSBreakpoint.md)

