---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/09/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/enable-psbreakpoint?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSBreakpoint
ms.openlocfilehash: 547739d6482e86bc558245bc5c5f04eddcfe9614
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228589"
---
# <span data-ttu-id="203ee-103">Enable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="203ee-103">Enable-PSBreakpoint</span></span>

## <span data-ttu-id="203ee-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="203ee-104">SYNOPSIS</span></span>
<span data-ttu-id="203ee-105">Включает точки останова в текущей консоли.</span><span class="sxs-lookup"><span data-stu-id="203ee-105">Enables the breakpoints in the current console.</span></span>

## <span data-ttu-id="203ee-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="203ee-106">SYNTAX</span></span>

### <span data-ttu-id="203ee-107">Id (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="203ee-107">Id (Default)</span></span>

```
Enable-PSBreakpoint [-PassThru] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="203ee-108">Точка останова</span><span class="sxs-lookup"><span data-stu-id="203ee-108">Breakpoint</span></span>

```
Enable-PSBreakpoint [-PassThru] [-Breakpoint] <Breakpoint[]> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="203ee-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="203ee-109">DESCRIPTION</span></span>

<span data-ttu-id="203ee-110">`Enable-PSBreakpoint`Командлет повторно включает отключенные точки останова.</span><span class="sxs-lookup"><span data-stu-id="203ee-110">The `Enable-PSBreakpoint` cmdlet re-enables disabled breakpoints.</span></span> <span data-ttu-id="203ee-111">Его можно использовать для включения всех точек останова или конкретных точек останова, предоставляя объекты или идентификаторы точек останова.</span><span class="sxs-lookup"><span data-stu-id="203ee-111">You can use it to enable all breakpoints, or specific breakpoints by providing breakpoint objects or IDs.</span></span>

<span data-ttu-id="203ee-112">Точка останова — это точка в скрипте, в которой выполнение останавливается временно, чтобы можно было проверить состояние скрипта.</span><span class="sxs-lookup"><span data-stu-id="203ee-112">A breakpoint is a point in a script where execution stops temporarily so that you can examine the state of the script.</span></span> <span data-ttu-id="203ee-113">Вновь созданные точки останова включаются автоматически, но могут быть отключены с помощью `Disable-PSBreakpoint` .</span><span class="sxs-lookup"><span data-stu-id="203ee-113">Newly created breakpoints are automatically enabled, but can be disabled using `Disable-PSBreakpoint`.</span></span>

<span data-ttu-id="203ee-114">Технически этот командлет изменяет значение свойства **Enabled** объекта точки останова на **true** .</span><span class="sxs-lookup"><span data-stu-id="203ee-114">Technically, this cmdlet changes the value of the **Enabled** property of a breakpoint object to **True** .</span></span>

<span data-ttu-id="203ee-115">`Enable-PSBreakpoint` является одним из нескольких командлетов, предназначенных для отладки скриптов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="203ee-115">`Enable-PSBreakpoint` is one of several cmdlets designed for debugging PowerShell scripts.</span></span> <span data-ttu-id="203ee-116">Дополнительные сведения о отладчике PowerShell см. в разделе [about_Debuggers](../Microsoft.PowerShell.Core/About/about_Debuggers.md).</span><span class="sxs-lookup"><span data-stu-id="203ee-116">For more information about the PowerShell debugger, see [about_Debuggers](../Microsoft.PowerShell.Core/About/about_Debuggers.md).</span></span>

## <span data-ttu-id="203ee-117">Примеры</span><span class="sxs-lookup"><span data-stu-id="203ee-117">EXAMPLES</span></span>

### <span data-ttu-id="203ee-118">Пример 1. Включение всех точек останова</span><span class="sxs-lookup"><span data-stu-id="203ee-118">Example 1: Enable all breakpoints</span></span>

<span data-ttu-id="203ee-119">В этом примере включаются все точки останова в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="203ee-119">This example enables all breakpoints in the current session.</span></span>

```powershell
Get-PSBreakpoint | Enable-PSBreakpoint
```

<span data-ttu-id="203ee-120">С помощью псевдонимов этот пример можно сократить на `gbp | ebp` .</span><span class="sxs-lookup"><span data-stu-id="203ee-120">Using aliases, this example can be abbreviated as `gbp | ebp`.</span></span>

### <span data-ttu-id="203ee-121">Пример 2. Включение точек останова по идентификатору</span><span class="sxs-lookup"><span data-stu-id="203ee-121">Example 2: Enable breakpoints by ID</span></span>

<span data-ttu-id="203ee-122">Этот пример включает несколько точек останова, использующих их идентификаторы точек останова.</span><span class="sxs-lookup"><span data-stu-id="203ee-122">This example enables multiple breakpoints using their breakpoint IDs.</span></span>

```powershell
Enable-PSBreakpoint -Id 0, 1, 5
```

### <span data-ttu-id="203ee-123">Пример 3. Включение отключенной точки останова</span><span class="sxs-lookup"><span data-stu-id="203ee-123">Example 3: Enable a disabled breakpoint</span></span>

<span data-ttu-id="203ee-124">В этом примере повторно включается Отключенная точка останова.</span><span class="sxs-lookup"><span data-stu-id="203ee-124">This example re-enables a breakpoint that has been disabled.</span></span>

```powershell
$B = Set-PSBreakpoint -Script "sample.ps1" -Variable Name -PassThru
$B | Enable-PSBreakpoint -PassThru
```

```Output
AccessMode : Write
Variable   : Name
Action     :
Enabled    : False
HitCount   : 0
Id         : 0
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1

AccessMode : Write
Variable   : Name
Action     :
Enabled    : True
HitCount   : 0
Id         : 0
Script     : C:\ps-test\sample.ps1
ScriptName : C:\ps-test\sample.ps1
```

<span data-ttu-id="203ee-125">`Set-PSBreakpoint` Создает точку останова в переменной **Name** в `Sample.ps1` скрипте, сохранив объект точки останова в `$B` переменной.</span><span class="sxs-lookup"><span data-stu-id="203ee-125">`Set-PSBreakpoint` creates a breakpoint on the **Name** variable in the `Sample.ps1` script saving the breakpoint object in the `$B` variable.</span></span> <span data-ttu-id="203ee-126">Параметр **PassThru** отображает значение свойства **Enabled** точки останова равно **false** .</span><span class="sxs-lookup"><span data-stu-id="203ee-126">The **PassThru** parameter displays the value of the **Enabled** property of the breakpoint is **False** .</span></span>

<span data-ttu-id="203ee-127">`Enable-PSBreakpoint` повторно включает точку останова.</span><span class="sxs-lookup"><span data-stu-id="203ee-127">`Enable-PSBreakpoint` re-enables the breakpoint.</span></span> <span data-ttu-id="203ee-128">Опять же, с помощью параметра **PassThru** мы видим, что значение свойства **Enabled** равно **true** .</span><span class="sxs-lookup"><span data-stu-id="203ee-128">Again, using the **PassThru** parameter we see that the value of the **Enabled** property is **True** .</span></span>

### <span data-ttu-id="203ee-129">Пример 4. Включение точек останова с помощью переменной</span><span class="sxs-lookup"><span data-stu-id="203ee-129">Example 4: Enable breakpoints using a variable</span></span>

<span data-ttu-id="203ee-130">Этот пример включает набор точек останова с помощью объектов точки останова.</span><span class="sxs-lookup"><span data-stu-id="203ee-130">This example enables a set of breakpoints using the breakpoint objects.</span></span>

```powershell
$B = Get-PSBreakpoint -Id 3, 5
Enable-PSBreakpoint -Breakpoint $B
```

<span data-ttu-id="203ee-131">`Get-PSBreakpoint` Возвращает точки останова и сохраняет их в `$B` переменной.</span><span class="sxs-lookup"><span data-stu-id="203ee-131">`Get-PSBreakpoint` gets the breakpoints and saves them in the `$B` variable.</span></span> <span data-ttu-id="203ee-132">Использование параметра **точки останова** `Enable-PSBreakpoint` включает точки останова.</span><span class="sxs-lookup"><span data-stu-id="203ee-132">Using the **Breakpoint** parameter, `Enable-PSBreakpoint` enables the breakpoints.</span></span>

<span data-ttu-id="203ee-133">Этот пример эквивалентен запуску `Enable-PSBreakpoint -Id 3, 5` .</span><span class="sxs-lookup"><span data-stu-id="203ee-133">This example is equivalent to running `Enable-PSBreakpoint -Id 3, 5`.</span></span>

## <span data-ttu-id="203ee-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="203ee-134">PARAMETERS</span></span>

### <span data-ttu-id="203ee-135">-Breakpoint</span><span class="sxs-lookup"><span data-stu-id="203ee-135">-Breakpoint</span></span>

<span data-ttu-id="203ee-136">Задает точки останова для включения.</span><span class="sxs-lookup"><span data-stu-id="203ee-136">Specifies the breakpoints to enable.</span></span> <span data-ttu-id="203ee-137">Укажите переменную, содержащую точки останова, или команду, которая получает объекты точек останова, такие как `Get-PSBreakpoint` .</span><span class="sxs-lookup"><span data-stu-id="203ee-137">Provide a variable containing breakpoints or a command that gets breakpoint objects, such as `Get-PSBreakpoint`.</span></span> <span data-ttu-id="203ee-138">Также можно передать объекты точки останова по конвейеру в `Enable-PSBreakpoint` .</span><span class="sxs-lookup"><span data-stu-id="203ee-138">You can also pipe breakpoint objects to `Enable-PSBreakpoint`.</span></span>

```yaml
Type: System.Management.Automation.Breakpoint[]
Parameter Sets: Breakpoint
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="203ee-139">-Id</span><span class="sxs-lookup"><span data-stu-id="203ee-139">-Id</span></span>

<span data-ttu-id="203ee-140">Указывает номера **идентификаторов** точек останова, которые необходимо включить.</span><span class="sxs-lookup"><span data-stu-id="203ee-140">Specifies the **Id** numbers of the breakpoints to enable.</span></span> <span data-ttu-id="203ee-141">Значение по умолчанию — все точки останова.</span><span class="sxs-lookup"><span data-stu-id="203ee-141">The default value is all breakpoints.</span></span>
<span data-ttu-id="203ee-142">Укажите **ID** по номеру или в переменной.</span><span class="sxs-lookup"><span data-stu-id="203ee-142">Provide the **Id** by number or in a variable.</span></span> <span data-ttu-id="203ee-143">Вы не можете передавать номера **идентификаторов** в `Enable-PSBreakpoint` .</span><span class="sxs-lookup"><span data-stu-id="203ee-143">You can't pipe **Id** numbers to `Enable-PSBreakpoint`.</span></span> <span data-ttu-id="203ee-144">Чтобы найти **идентификатор** точки останова, используйте `Get-PSBreakpoint` командлет.</span><span class="sxs-lookup"><span data-stu-id="203ee-144">To find the **Id** of a breakpoint, use the `Get-PSBreakpoint` cmdlet.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="203ee-145">-PassThru</span><span class="sxs-lookup"><span data-stu-id="203ee-145">-PassThru</span></span>

<span data-ttu-id="203ee-146">Возвращает объект, представляющий включенную точку останова.</span><span class="sxs-lookup"><span data-stu-id="203ee-146">Returns an object representing the breakpoint being enabled.</span></span> <span data-ttu-id="203ee-147">По умолчанию этот командлет не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="203ee-147">By default, this cmdlet doesn't generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="203ee-148">-Confirm</span><span class="sxs-lookup"><span data-stu-id="203ee-148">-Confirm</span></span>

<span data-ttu-id="203ee-149">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="203ee-149">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="203ee-150">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="203ee-150">-WhatIf</span></span>

<span data-ttu-id="203ee-151">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="203ee-151">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="203ee-152">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="203ee-152">The cmdlet isn't run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="203ee-153">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="203ee-153">CommonParameters</span></span>

<span data-ttu-id="203ee-154">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="203ee-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="203ee-155">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="203ee-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="203ee-156">Входные данные</span><span class="sxs-lookup"><span data-stu-id="203ee-156">INPUTS</span></span>

### <span data-ttu-id="203ee-157">System.Management.Automation.Breakpoint</span><span class="sxs-lookup"><span data-stu-id="203ee-157">System.Management.Automation.Breakpoint</span></span>

<span data-ttu-id="203ee-158">Объект точки останова можно передать в `Enable-PSBreakpoint` .</span><span class="sxs-lookup"><span data-stu-id="203ee-158">You can pipe a breakpoint object to `Enable-PSBreakpoint`.</span></span>

## <span data-ttu-id="203ee-159">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="203ee-159">OUTPUTS</span></span>

### <span data-ttu-id="203ee-160">Нет или System.Management.Automation.Breakpoint</span><span class="sxs-lookup"><span data-stu-id="203ee-160">None or System.Management.Automation.Breakpoint</span></span>

<span data-ttu-id="203ee-161">При использовании параметра **PassThru** `Enable-PSBreakpoint` возвращает объект точки останова, представляющий включенную точку останова.</span><span class="sxs-lookup"><span data-stu-id="203ee-161">When you use the **PassThru** parameter, `Enable-PSBreakpoint` returns a breakpoint object that represents that breakpoint that was enabled.</span></span> <span data-ttu-id="203ee-162">В противном случае этот командлет не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="203ee-162">Otherwise, this cmdlet doesn't generate any output.</span></span>

## <span data-ttu-id="203ee-163">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="203ee-163">NOTES</span></span>

- <span data-ttu-id="203ee-164">`Enable-PSBreakpoint`Если вы попытаетесь включить уже включенную точку останова, командлет не выдаст ошибку.</span><span class="sxs-lookup"><span data-stu-id="203ee-164">The `Enable-PSBreakpoint` cmdlet doesn't generate an error if you try to enable a breakpoint that is already enabled.</span></span> <span data-ttu-id="203ee-165">Таким образом, можно включить все точки останова, не опасаясь ошибок, даже если только некоторые из них отключены.</span><span class="sxs-lookup"><span data-stu-id="203ee-165">As such, you can enable all breakpoints without error, even when only a few are disabled.</span></span>

- <span data-ttu-id="203ee-166">Точки останова включаются при их создании с помощью `Set-PSBreakpoint` командлета.</span><span class="sxs-lookup"><span data-stu-id="203ee-166">Breakpoints are enabled when you create them by using the `Set-PSBreakpoint` cmdlet.</span></span> <span data-ttu-id="203ee-167">Не нужно включать вновь созданные точки останова.</span><span class="sxs-lookup"><span data-stu-id="203ee-167">You don't need to enable newly created breakpoints.</span></span>

## <span data-ttu-id="203ee-168">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="203ee-168">RELATED LINKS</span></span>

[<span data-ttu-id="203ee-169">Disable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="203ee-169">Disable-PSBreakpoint</span></span>](Disable-PSBreakpoint.md)

[<span data-ttu-id="203ee-170">Get-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="203ee-170">Get-PSBreakpoint</span></span>](Get-PSBreakpoint.md)

[<span data-ttu-id="203ee-171">Get-PSCallStack</span><span class="sxs-lookup"><span data-stu-id="203ee-171">Get-PSCallStack</span></span>](Get-PSCallStack.md)

[<span data-ttu-id="203ee-172">Remove-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="203ee-172">Remove-PSBreakpoint</span></span>](Remove-PSBreakpoint.md)

[<span data-ttu-id="203ee-173">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="203ee-173">Set-PSBreakpoint</span></span>](Set-PSBreakpoint.md)
