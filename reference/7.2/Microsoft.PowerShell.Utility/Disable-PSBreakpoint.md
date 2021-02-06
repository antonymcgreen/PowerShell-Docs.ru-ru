---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/disable-psbreakpoint?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSBreakpoint
ms.openlocfilehash: 2bd1a48d2075950cdb337063a100bf31534ac6fe
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602866"
---
# <span data-ttu-id="c0cde-102">Disable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="c0cde-102">Disable-PSBreakpoint</span></span>

## <span data-ttu-id="c0cde-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="c0cde-103">SYNOPSIS</span></span>
<span data-ttu-id="c0cde-104">Отключает точки останова в текущей консоли.</span><span class="sxs-lookup"><span data-stu-id="c0cde-104">Disables the breakpoints in the current console.</span></span>

## <span data-ttu-id="c0cde-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c0cde-105">SYNTAX</span></span>

### <span data-ttu-id="c0cde-106">Точка останова (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="c0cde-106">Breakpoint (Default)</span></span>

```
Disable-PSBreakpoint [-PassThru] [-Breakpoint] <Breakpoint[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c0cde-107">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="c0cde-107">Id</span></span>

```
Disable-PSBreakpoint [-PassThru] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="c0cde-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c0cde-108">DESCRIPTION</span></span>

<span data-ttu-id="c0cde-109">Командлет **Disable-PSBreakpoint** отключает точки останова, что гарантирует, что они не будут достигнуты при выполнении скрипта.</span><span class="sxs-lookup"><span data-stu-id="c0cde-109">The **Disable-PSBreakpoint** cmdlet disables breakpoints, which assures that they are not hit when the script runs.</span></span>
<span data-ttu-id="c0cde-110">С помощью этого командлета можно отключить все точки останова или указать конкретные точки, задав соответствующие объекты или их идентификаторы.</span><span class="sxs-lookup"><span data-stu-id="c0cde-110">You can use it to disable all breakpoints, or you can specify breakpoints by submitting breakpoint objects or breakpoint IDs.</span></span>

<span data-ttu-id="c0cde-111">Технически этот командлет изменяет значение свойства Enabled объекта точки останова на значение False.</span><span class="sxs-lookup"><span data-stu-id="c0cde-111">Technically, this cmdlet changes the value of the Enabled property of a breakpoint object to False.</span></span>
<span data-ttu-id="c0cde-112">Для повторного включения точки останова используется командлет Enable-PSBreakpoint.</span><span class="sxs-lookup"><span data-stu-id="c0cde-112">To re-enable a breakpoint, use the Enable-PSBreakpoint cmdlet.</span></span>
<span data-ttu-id="c0cde-113">Точки останова по умолчанию включаются при их создании с помощью командлета Set-PSBreakpoint.</span><span class="sxs-lookup"><span data-stu-id="c0cde-113">Breakpoints are enabled by default when you create them by using the Set-PSBreakpoint cmdlet.</span></span>

<span data-ttu-id="c0cde-114">Точка останова — это точка в скрипте, на которой выполнение временно останавливается, чтобы можно было проверить инструкции скрипта.</span><span class="sxs-lookup"><span data-stu-id="c0cde-114">A breakpoint is a point in a script where execution stops temporarily so that you can examine the instructions in the script.</span></span>
<span data-ttu-id="c0cde-115">**Disable-PSBreakpoint** — это один из нескольких командлетов, предназначенных для отладки скриптов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c0cde-115">**Disable-PSBreakpoint** is one of several cmdlets designed for debugging PowerShell scripts.</span></span>
<span data-ttu-id="c0cde-116">Дополнительные сведения о отладчике PowerShell см. в разделе about_Debuggers.</span><span class="sxs-lookup"><span data-stu-id="c0cde-116">For more information about the PowerShell debugger, see about_Debuggers.</span></span>

## <span data-ttu-id="c0cde-117">Примеры</span><span class="sxs-lookup"><span data-stu-id="c0cde-117">EXAMPLES</span></span>

### <span data-ttu-id="c0cde-118">Пример 1. Установка точки останова и ее отключение</span><span class="sxs-lookup"><span data-stu-id="c0cde-118">Example 1: Set a breakpoint and disable it</span></span>

```
PS C:\> $B = Set-PSBreakpoint -Script "sample.ps1" -Variable "name"
PS C:\> $B | Disable-PSBreakpoint
```

<span data-ttu-id="c0cde-119">Эти команды отключают только что созданную точку останова.</span><span class="sxs-lookup"><span data-stu-id="c0cde-119">These commands disable a newly-created breakpoint.</span></span>

<span data-ttu-id="c0cde-120">Первая команда использует командлет Set-PSBreakpoint для создания точки останова на переменной *Name* в скрипте Sample.ps1.</span><span class="sxs-lookup"><span data-stu-id="c0cde-120">The first command uses the Set-PSBreakpoint cmdlet to create a breakpoint on the *Name* variable in the Sample.ps1 script.</span></span>
<span data-ttu-id="c0cde-121">Затем она сохраняет объект точки останова в переменной $b.</span><span class="sxs-lookup"><span data-stu-id="c0cde-121">Then, it saves the breakpoint object in the $B variable.</span></span>

<span data-ttu-id="c0cde-122">Вторая команда использует командлет **Disable-PSBreakpoint** для отключения новой точки останова.</span><span class="sxs-lookup"><span data-stu-id="c0cde-122">The second command uses the **Disable-PSBreakpoint** cmdlet to disable the new breakpoint.</span></span>
<span data-ttu-id="c0cde-123">Для отправки объекта точки останова в $B в командлет **Disable-PSBreakpoint** используется оператор конвейера (|).</span><span class="sxs-lookup"><span data-stu-id="c0cde-123">It uses a pipeline operator (|) to send the breakpoint object in $B to the **Disable-PSBreakpoint** cmdlet.</span></span>

<span data-ttu-id="c0cde-124">В результате выполнения этой команды значение свойства Enabled объекта точки останова в $B равно false.</span><span class="sxs-lookup"><span data-stu-id="c0cde-124">As a result of this command, the value of the Enabled property of the breakpoint object in $B is False.</span></span>

### <span data-ttu-id="c0cde-125">Пример 2. Отключение точки останова</span><span class="sxs-lookup"><span data-stu-id="c0cde-125">Example 2: Disable a breakpoint</span></span>

```
PS C:\> Disable-PSBreakpoint -Id 0
```

<span data-ttu-id="c0cde-126">Эта команда отключает точку останова с идентификатором 0.</span><span class="sxs-lookup"><span data-stu-id="c0cde-126">This command disables the breakpoint with breakpoint ID 0.</span></span>

### <span data-ttu-id="c0cde-127">Пример 3. Создание отключенной точки останова</span><span class="sxs-lookup"><span data-stu-id="c0cde-127">Example 3: Create a disabled breakpoint</span></span>

```
PS C:\> Disable-PSBreakpoint -Breakpoint ($B = Set-PSBreakpoint -Script "sample.ps1" -Line 5)
PS C:\> $B
```

<span data-ttu-id="c0cde-128">Эта команда создает новую точку останова, которая остается отключенной, пока пользователь ее не включит.</span><span class="sxs-lookup"><span data-stu-id="c0cde-128">This command creates a new breakpoint that is disabled until you enable it.</span></span>

<span data-ttu-id="c0cde-129">Для отключения точки останова используется командлет **Disable-PSBreakpoint** .</span><span class="sxs-lookup"><span data-stu-id="c0cde-129">It uses the **Disable-PSBreakpoint** cmdlet to disable the breakpoint.</span></span>
<span data-ttu-id="c0cde-130">Значение параметра *точки останова* — это Set-PSBreakpoint команда, которая задает новую точку останова, создает объект точки останова и сохраняет объект в переменной $B.</span><span class="sxs-lookup"><span data-stu-id="c0cde-130">The value of the *Breakpoint* parameter is a Set-PSBreakpoint command that sets a new breakpoint, generates a breakpoint object, and saves the object in the $B variable.</span></span>

<span data-ttu-id="c0cde-131">Параметры командлета, принимающие в качестве значений объекты, могут принять переменную, которая содержит объект, или команду, которая получает или создает объект.</span><span class="sxs-lookup"><span data-stu-id="c0cde-131">Cmdlet parameters that take objects as their values can accept a variable that contains the object or a command that gets or generates the object.</span></span>
<span data-ttu-id="c0cde-132">В этом случае, поскольку командлет **Set-PSBreakpoint** создает объект точки останова, его можно использовать в качестве значения параметра *точки останова* .</span><span class="sxs-lookup"><span data-stu-id="c0cde-132">In this case, because **Set-PSBreakpoint** generates a breakpoint object, it can be used as the value of the *Breakpoint* parameter.</span></span>

<span data-ttu-id="c0cde-133">Вторая команда отображает объект точки останова в значении переменной $B.</span><span class="sxs-lookup"><span data-stu-id="c0cde-133">The second command displays the breakpoint object in the value of the $B variable.</span></span>

### <span data-ttu-id="c0cde-134">Пример 4. Отключение всех точек останова в текущей консоли</span><span class="sxs-lookup"><span data-stu-id="c0cde-134">Example 4: Disable all breakpoints in the current console</span></span>

```
PS C:\> Get-PSBreakpoint | Disable-PSBreakpoint
```

<span data-ttu-id="c0cde-135">Эта команда отключает все точки останова в текущей консоли.</span><span class="sxs-lookup"><span data-stu-id="c0cde-135">This command disables all breakpoints in the current console.</span></span>
<span data-ttu-id="c0cde-136">Эту команду можно сократить следующим образом: "GBP | DBP».</span><span class="sxs-lookup"><span data-stu-id="c0cde-136">You can abbreviate this command as: "gbp | dbp".</span></span>

## <span data-ttu-id="c0cde-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c0cde-137">PARAMETERS</span></span>

### <span data-ttu-id="c0cde-138">-Breakpoint</span><span class="sxs-lookup"><span data-stu-id="c0cde-138">-Breakpoint</span></span>

<span data-ttu-id="c0cde-139">Определяет точки останова, которые нужно отключить.</span><span class="sxs-lookup"><span data-stu-id="c0cde-139">Specifies the breakpoints to disable.</span></span>
<span data-ttu-id="c0cde-140">Введите переменную, которая содержит объекты точек останова, или команду, которая их получает (например, Get-PSBreakpoint).</span><span class="sxs-lookup"><span data-stu-id="c0cde-140">Enter a variable that contains breakpoint objects or a command that gets breakpoint objects, such as a Get-PSBreakpoint command.</span></span>
<span data-ttu-id="c0cde-141">Объекты точки останова также можно передать в командлет **Disable-PSBreakpoint** .</span><span class="sxs-lookup"><span data-stu-id="c0cde-141">You can also pipe breakpoint objects to the **Disable-PSBreakpoint** cmdlet.</span></span>

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

### <span data-ttu-id="c0cde-142">-Id</span><span class="sxs-lookup"><span data-stu-id="c0cde-142">-Id</span></span>

<span data-ttu-id="c0cde-143">Отключает точки останова с указанными идентификаторами.</span><span class="sxs-lookup"><span data-stu-id="c0cde-143">Disables the breakpoints with the specified breakpoint IDs.</span></span>
<span data-ttu-id="c0cde-144">Введите идентификаторы или переменную, которая их содержит.</span><span class="sxs-lookup"><span data-stu-id="c0cde-144">Enter the IDs or a variable that contains the IDs.</span></span>
<span data-ttu-id="c0cde-145">Невозможно передать идентификаторы в командлет **Disable-PSBreakpoint**.</span><span class="sxs-lookup"><span data-stu-id="c0cde-145">You cannot pipe IDs to **Disable-PSBreakpoint**.</span></span>

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

### <span data-ttu-id="c0cde-146">-PassThru</span><span class="sxs-lookup"><span data-stu-id="c0cde-146">-PassThru</span></span>

<span data-ttu-id="c0cde-147">Возвращает объект, представляющий включенные точки останова.</span><span class="sxs-lookup"><span data-stu-id="c0cde-147">Returns an object representing the enabled breakpoints.</span></span>
<span data-ttu-id="c0cde-148">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="c0cde-148">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="c0cde-149">-Confirm</span><span class="sxs-lookup"><span data-stu-id="c0cde-149">-Confirm</span></span>

<span data-ttu-id="c0cde-150">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="c0cde-150">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="c0cde-151">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="c0cde-151">-WhatIf</span></span>

<span data-ttu-id="c0cde-152">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="c0cde-152">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="c0cde-153">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="c0cde-153">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="c0cde-154">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="c0cde-154">CommonParameters</span></span>

<span data-ttu-id="c0cde-155">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c0cde-155">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c0cde-156">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c0cde-156">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c0cde-157">Входные данные</span><span class="sxs-lookup"><span data-stu-id="c0cde-157">INPUTS</span></span>

### <span data-ttu-id="c0cde-158">System.Management.Automation.Breakpoint</span><span class="sxs-lookup"><span data-stu-id="c0cde-158">System.Management.Automation.Breakpoint</span></span>

<span data-ttu-id="c0cde-159">Объект точки останова можно передать в командлет **Disable-PSBreakpoint** по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="c0cde-159">You can pipe a breakpoint object to **Disable-PSBreakpoint**.</span></span>

## <span data-ttu-id="c0cde-160">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="c0cde-160">OUTPUTS</span></span>

### <span data-ttu-id="c0cde-161">Нет или System.Management.Automation.Breakpoint</span><span class="sxs-lookup"><span data-stu-id="c0cde-161">None or System.Management.Automation.Breakpoint</span></span>

<span data-ttu-id="c0cde-162">При использовании параметра *PassThru* командлет **Disable-PSBreakpoint** возвращает объект, представляющий отключенную точку останова.</span><span class="sxs-lookup"><span data-stu-id="c0cde-162">When you use the *PassThru* parameter, **Disable-PSBreakpoint** returns an object that represents the disabled breakpoint.</span></span>
<span data-ttu-id="c0cde-163">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="c0cde-163">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="c0cde-164">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="c0cde-164">NOTES</span></span>

## <span data-ttu-id="c0cde-165">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="c0cde-165">RELATED LINKS</span></span>

[<span data-ttu-id="c0cde-166">Enable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="c0cde-166">Enable-PSBreakpoint</span></span>](Enable-PSBreakpoint.md)

[<span data-ttu-id="c0cde-167">Get-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="c0cde-167">Get-PSBreakpoint</span></span>](Get-PSBreakpoint.md)

[<span data-ttu-id="c0cde-168">Get-PSCallStack</span><span class="sxs-lookup"><span data-stu-id="c0cde-168">Get-PSCallStack</span></span>](Get-PSCallStack.md)

[<span data-ttu-id="c0cde-169">Remove-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="c0cde-169">Remove-PSBreakpoint</span></span>](Remove-PSBreakpoint.md)

[<span data-ttu-id="c0cde-170">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="c0cde-170">Set-PSBreakpoint</span></span>](Set-PSBreakpoint.md)

