---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 5/15/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-psbreakpoint?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSBreakpoint
ms.openlocfilehash: 6afabaf46907d317ec864519a658c500466d4c38
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227185"
---
# <span data-ttu-id="91308-103">Get-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="91308-103">Get-PSBreakpoint</span></span>

## <span data-ttu-id="91308-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="91308-104">SYNOPSIS</span></span>
<span data-ttu-id="91308-105">Возвращает точки останова, установленные в рамках текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="91308-105">Gets the breakpoints that are set in the current session.</span></span>

## <span data-ttu-id="91308-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="91308-106">SYNTAX</span></span>

### <span data-ttu-id="91308-107">Скрипт (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="91308-107">Script (Default)</span></span>

```
Get-PSBreakpoint [-Script <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="91308-108">Переменная</span><span class="sxs-lookup"><span data-stu-id="91308-108">Variable</span></span>

```
Get-PSBreakpoint [-Script <String[]>] -Variable <String[]> [<CommonParameters>]
```

### <span data-ttu-id="91308-109">Get-Help</span><span class="sxs-lookup"><span data-stu-id="91308-109">Command</span></span>

```
Get-PSBreakpoint [-Script <String[]>] -Command <String[]> [<CommonParameters>]
```

### <span data-ttu-id="91308-110">Тип</span><span class="sxs-lookup"><span data-stu-id="91308-110">Type</span></span>

```
Get-PSBreakpoint [-Script <String[]>] [-Type] <BreakpointType[]> [<CommonParameters>]
```

### <span data-ttu-id="91308-111">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="91308-111">Id</span></span>

```
Get-PSBreakpoint [-Id] <Int32[]> [<CommonParameters>]
```

## <span data-ttu-id="91308-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="91308-112">DESCRIPTION</span></span>

<span data-ttu-id="91308-113">Командлет **Get-PSBreakpoint** возвращает точки останова, установленные в рамках текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="91308-113">The **Get-PSBreakPoint** cmdlet gets the breakpoints that are set in the current session.</span></span>
<span data-ttu-id="91308-114">С помощью параметров командлета можно получить определенные точки останова.</span><span class="sxs-lookup"><span data-stu-id="91308-114">You can use the cmdlet parameters to get particular breakpoints.</span></span>

<span data-ttu-id="91308-115">Точка останова — это место в команде или сценарии, в котором выполнение временно приостанавливается, чтобы вы могли изучить инструкции.</span><span class="sxs-lookup"><span data-stu-id="91308-115">A breakpoint is a point in a command or script where execution stops temporarily so that you can examine the instructions.</span></span>
<span data-ttu-id="91308-116">**Get-PSBreakpoint** — это один из нескольких командлетов, предназначенных для отладки сценариев и команд PowerShell.</span><span class="sxs-lookup"><span data-stu-id="91308-116">**Get-PSBreakpoint** is one of several cmdlets designed for debugging PowerShell scripts and commands.</span></span> <span data-ttu-id="91308-117">Дополнительные сведения о отладчике PowerShell см. в разделе about_Debuggers.</span><span class="sxs-lookup"><span data-stu-id="91308-117">For more information about the PowerShell debugger, see about_Debuggers.</span></span>

## <span data-ttu-id="91308-118">Примеры</span><span class="sxs-lookup"><span data-stu-id="91308-118">EXAMPLES</span></span>

### <span data-ttu-id="91308-119">Пример 1. Получение всех точек останова для всех скриптов и функций</span><span class="sxs-lookup"><span data-stu-id="91308-119">Example 1: Get all breakpoints for all scripts and functions</span></span>

```
PS C:\> Get-PSBreakpoint
```

<span data-ttu-id="91308-120">Эта команда возвращает все точки останова, установленные во всех сценариях и функциях текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="91308-120">This command gets all breakpoints set on all scripts and functions in the current session.</span></span>

### <span data-ttu-id="91308-121">Пример 2. Получение точек останова по идентификатору</span><span class="sxs-lookup"><span data-stu-id="91308-121">Example 2: Get breakpoints by ID</span></span>

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

<span data-ttu-id="91308-122">Эта команда возвращает точку останова с идентификатором 2.</span><span class="sxs-lookup"><span data-stu-id="91308-122">This command gets the breakpoint with breakpoint ID 2.</span></span>

### <span data-ttu-id="91308-123">Пример 3. Передача идентификатора в командлет Get-PSBreakpoint по конвейеру</span><span class="sxs-lookup"><span data-stu-id="91308-123">Example 3: Pipe an ID to Get-PSBreakpoint</span></span>

```
PS C:\> $B = Set-PSBreakpoint -Script "sample.ps1" -Command "Increment"
PS C:\> $B.Id | Get-PSBreakpoint
```

<span data-ttu-id="91308-124">Эти команды показывают, как получить точку останова путем передачи ее идентификатора по конвейеру в командлет **Get-PSBreakpoint**.</span><span class="sxs-lookup"><span data-stu-id="91308-124">These commands show how to get a breakpoint by piping a breakpoint ID to **Get-PSBreakpoint**.</span></span>

<span data-ttu-id="91308-125">В первой команде используется командлет Set-PSBreakpoint для создания точки останова в функции Increment в сценарии Sample.ps1.</span><span class="sxs-lookup"><span data-stu-id="91308-125">The first command uses the Set-PSBreakpoint cmdlet to create a breakpoint on the Increment function in the Sample.ps1 script.</span></span> <span data-ttu-id="91308-126">Объект точки останова сохраняется в переменной $B.</span><span class="sxs-lookup"><span data-stu-id="91308-126">It saves the breakpoint object in the $B variable.</span></span>

<span data-ttu-id="91308-127">Во второй команде используется оператор-точка (.) для получения свойства Id объекта точки останова в переменной $B.</span><span class="sxs-lookup"><span data-stu-id="91308-127">The second command uses the dot operator (.) to get the Id property of the breakpoint object in the $B variable.</span></span> <span data-ttu-id="91308-128">С помощью конвейерного оператора (|) идентификатор передается в командлет **Get-PSBreakpoint**.</span><span class="sxs-lookup"><span data-stu-id="91308-128">It uses a pipeline operator (|) to send the ID to the **Get-PSBreakpoint** cmdlet.</span></span>

<span data-ttu-id="91308-129">В результате командлет **Get-PSBreakpoint** возвращает точку останова с указанным идентификатором.</span><span class="sxs-lookup"><span data-stu-id="91308-129">As a result, **Get-PSBreakpoint** gets the breakpoint with the specified ID.</span></span>

### <span data-ttu-id="91308-130">Пример 4. Возвращение точек останова в указанных файлах скриптов</span><span class="sxs-lookup"><span data-stu-id="91308-130">Example 4: Get breakpoints in specified script files</span></span>

```
PS C:\> Get-PSBreakpoint -Script "Sample.ps1, SupportScript.ps1"
```

<span data-ttu-id="91308-131">Эта команда возвращает все точки останова в файлах Sample.ps1 и SupportScript.ps1.</span><span class="sxs-lookup"><span data-stu-id="91308-131">This command gets all of the breakpoints in the Sample.ps1 and SupportScript.ps1 files.</span></span>

<span data-ttu-id="91308-132">Она не возвращает точки останова, которые могут быть установлены в других скриптах или функциях в рамках сеанса.</span><span class="sxs-lookup"><span data-stu-id="91308-132">This command does not get other breakpoints that might be set in other scripts or on functions in the session.</span></span>

### <span data-ttu-id="91308-133">Пример 5. Возвращение точек останова в указанных командлетах</span><span class="sxs-lookup"><span data-stu-id="91308-133">Example 5: Get breakpoints in specified cmdlets</span></span>

```
PS C:\> Get-PSBreakpoint -Command "Read-Host, Write-Host" -Script "Sample.ps1"
```

<span data-ttu-id="91308-134">Эта команда возвращает все точки останова, установленные в командах Read-Host или Write-Host в файле Sample.ps1.</span><span class="sxs-lookup"><span data-stu-id="91308-134">This command gets all Command breakpoints that are set on Read-Host or Write-Host commands in the Sample.ps1 file.</span></span>

### <span data-ttu-id="91308-135">Пример 6. Возвращение точек останова команды в указанном файле</span><span class="sxs-lookup"><span data-stu-id="91308-135">Example 6: Get Command breakpoints in a specified file</span></span>

```
PS C:\> Get-PSBreakpoint -Type Command -Script "Sample.ps1"
```

<span data-ttu-id="91308-136">Эта команда возвращает все точки останова команд в файле Sample.ps1.</span><span class="sxs-lookup"><span data-stu-id="91308-136">This command gets all Command breakpoints in the Sample.ps1 file.</span></span>

### <span data-ttu-id="91308-137">Пример 7. Получение точек останова по переменной</span><span class="sxs-lookup"><span data-stu-id="91308-137">Example 7: Get breakpoints by variable</span></span>

```
PS C:\> Get-PSBreakpoint -Variable "Index, Swap"
```

<span data-ttu-id="91308-138">Эта команда возвращает точки останова, установленные для переменных $Index и $Swap в рамках текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="91308-138">This command gets breakpoints that are set on the $Index and $Swap variables in the current session.</span></span>

### <span data-ttu-id="91308-139">Пример 8. Возвращение всех точек останова строк и переменных в файле</span><span class="sxs-lookup"><span data-stu-id="91308-139">Example 8: Get all Line and Variable breakpoints in a file</span></span>

```
PS C:\> Get-PSBreakpoint -Type Line, Variable -Script "Sample.ps1"
```

<span data-ttu-id="91308-140">Эта команда возвращает все точки останова строк и переменных в сценарии Sample.ps1.</span><span class="sxs-lookup"><span data-stu-id="91308-140">This command gets all line and variable breakpoints in the Sample.ps1 script.</span></span>

## <span data-ttu-id="91308-141">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="91308-141">PARAMETERS</span></span>

### <span data-ttu-id="91308-142">-Command</span><span class="sxs-lookup"><span data-stu-id="91308-142">-Command</span></span>

<span data-ttu-id="91308-143">Указывает массив точек останова, заданных для команд с указанными именами.</span><span class="sxs-lookup"><span data-stu-id="91308-143">Specifies an array of command breakpoints that are set on the specified command names.</span></span>
<span data-ttu-id="91308-144">Введите имена команд, например имя командлета или функции.</span><span class="sxs-lookup"><span data-stu-id="91308-144">Enter the command names, such as the name of a cmdlet or function.</span></span>

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

### <span data-ttu-id="91308-145">-Id</span><span class="sxs-lookup"><span data-stu-id="91308-145">-Id</span></span>

<span data-ttu-id="91308-146">Указывает идентификаторы точки останова, которую возвращает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="91308-146">Specifies the breakpoint IDs that this cmdlet gets.</span></span>
<span data-ttu-id="91308-147">Введите идентификаторы в виде разделенного запятыми списка.</span><span class="sxs-lookup"><span data-stu-id="91308-147">Enter the IDs in a comma-separated list.</span></span>
<span data-ttu-id="91308-148">Идентификаторы точек останова можно также передать в командлет **Get-PSBreakpoint** по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="91308-148">You can also pipe breakpoint IDs to **Get-PSBreakpoint**.</span></span>

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

### <span data-ttu-id="91308-149">-Script</span><span class="sxs-lookup"><span data-stu-id="91308-149">-Script</span></span>

<span data-ttu-id="91308-150">Указывает массив скриптов, содержащих точки останова.</span><span class="sxs-lookup"><span data-stu-id="91308-150">Specifies an array of scripts that contain the breakpoints.</span></span>
<span data-ttu-id="91308-151">Введите путь (необязательно) и имена одного или нескольких файлов скриптов.</span><span class="sxs-lookup"><span data-stu-id="91308-151">Enter the path (optional) and names of one or more script files.</span></span>
<span data-ttu-id="91308-152">Если путь не указан, расположением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="91308-152">If you omit the path, the default location is the current directory.</span></span>

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

### <span data-ttu-id="91308-153">-Type</span><span class="sxs-lookup"><span data-stu-id="91308-153">-Type</span></span>

<span data-ttu-id="91308-154">Указывает массив типов точек останова, которые возвращает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="91308-154">Specifies an array of breakpoint types that this cmdlet gets.</span></span>
<span data-ttu-id="91308-155">Введите один или несколько типов.</span><span class="sxs-lookup"><span data-stu-id="91308-155">Enter one or more types.</span></span>
<span data-ttu-id="91308-156">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="91308-156">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="91308-157">Линия</span><span class="sxs-lookup"><span data-stu-id="91308-157">Line</span></span>
- <span data-ttu-id="91308-158">Get-Help</span><span class="sxs-lookup"><span data-stu-id="91308-158">Command</span></span>
- <span data-ttu-id="91308-159">Переменная</span><span class="sxs-lookup"><span data-stu-id="91308-159">Variable</span></span>

<span data-ttu-id="91308-160">Типы точек останова можно также передать в командлет **Get-PSBreakpoint** по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="91308-160">You can also pipe breakpoint types to **Get-PSBreakPoint**.</span></span>

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

### <span data-ttu-id="91308-161">-Variable</span><span class="sxs-lookup"><span data-stu-id="91308-161">-Variable</span></span>

<span data-ttu-id="91308-162">Указывает массив точек останова, заданных для переменных с указанными именами.</span><span class="sxs-lookup"><span data-stu-id="91308-162">Specifies an array of variable breakpoints that are set on the specified variable names.</span></span>
<span data-ttu-id="91308-163">Введите имена переменных без знака доллара.</span><span class="sxs-lookup"><span data-stu-id="91308-163">Enter the variable names without dollar signs.</span></span>

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

### <span data-ttu-id="91308-164">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="91308-164">CommonParameters</span></span>

<span data-ttu-id="91308-165">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="91308-165">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="91308-166">Дополнительные сведения см. в разделе about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="91308-166">For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="91308-167">Входные данные</span><span class="sxs-lookup"><span data-stu-id="91308-167">INPUTS</span></span>

### <span data-ttu-id="91308-168">System.Int32, Microsoft.PowerShell.Commands.BreakpointType</span><span class="sxs-lookup"><span data-stu-id="91308-168">System.Int32, Microsoft.PowerShell.Commands.BreakpointType</span></span>

<span data-ttu-id="91308-169">Идентификаторы и типы точек останова можно передавать в командлет **Get-PSBreakpoint** по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="91308-169">You can pipe breakpoint IDs and breakpoint types to **Get-PSBreakPoint**.</span></span>

## <span data-ttu-id="91308-170">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="91308-170">OUTPUTS</span></span>

### <span data-ttu-id="91308-171">System.Management.Automation.Breakpoint</span><span class="sxs-lookup"><span data-stu-id="91308-171">System.Management.Automation.Breakpoint</span></span>

<span data-ttu-id="91308-172">Командлет **Get-PSBreakpoint** возвращает объекты, которые представляют точки останова в рамках сеанса.</span><span class="sxs-lookup"><span data-stu-id="91308-172">**Get-PSBreakPoint** returns objects that represent the breakpoints in the session.</span></span>

## <span data-ttu-id="91308-173">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="91308-173">NOTES</span></span>

* <span data-ttu-id="91308-174">Можно использовать **Get-PSBreakpoint** или его псевдоним "GBP".</span><span class="sxs-lookup"><span data-stu-id="91308-174">You can use **Get-PSBreakpoint** or its alias, "gbp".</span></span>

## <span data-ttu-id="91308-175">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="91308-175">RELATED LINKS</span></span>

[<span data-ttu-id="91308-176">Disable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="91308-176">Disable-PSBreakpoint</span></span>](Disable-PSBreakpoint.md)

[<span data-ttu-id="91308-177">Enable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="91308-177">Enable-PSBreakpoint</span></span>](Enable-PSBreakpoint.md)

[<span data-ttu-id="91308-178">Get-PSCallStack</span><span class="sxs-lookup"><span data-stu-id="91308-178">Get-PSCallStack</span></span>](Get-PSCallStack.md)

[<span data-ttu-id="91308-179">Remove-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="91308-179">Remove-PSBreakpoint</span></span>](Remove-PSBreakpoint.md)

[<span data-ttu-id="91308-180">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="91308-180">Set-PSBreakpoint</span></span>](Set-PSBreakpoint.md)

