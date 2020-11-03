---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/disable-psbreakpoint?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSBreakpoint
ms.openlocfilehash: 66ef0cec2bfdb1aa70b97001830811f68c68b911
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229050"
---
# <span data-ttu-id="64aeb-103">Disable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="64aeb-103">Disable-PSBreakpoint</span></span>

## <span data-ttu-id="64aeb-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="64aeb-104">SYNOPSIS</span></span>
<span data-ttu-id="64aeb-105">Отключает точки останова в текущей консоли.</span><span class="sxs-lookup"><span data-stu-id="64aeb-105">Disables the breakpoints in the current console.</span></span>

## <span data-ttu-id="64aeb-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="64aeb-106">SYNTAX</span></span>

### <span data-ttu-id="64aeb-107">Точка останова (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="64aeb-107">Breakpoint (Default)</span></span>

```
Disable-PSBreakpoint [-PassThru] [-Breakpoint] <Breakpoint[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="64aeb-108">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="64aeb-108">Id</span></span>

```
Disable-PSBreakpoint [-PassThru] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="64aeb-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="64aeb-109">DESCRIPTION</span></span>

<span data-ttu-id="64aeb-110">Командлет **Disable-PSBreakpoint** отключает точки останова, что гарантирует, что они не будут достигнуты при выполнении скрипта.</span><span class="sxs-lookup"><span data-stu-id="64aeb-110">The **Disable-PSBreakpoint** cmdlet disables breakpoints, which assures that they are not hit when the script runs.</span></span>
<span data-ttu-id="64aeb-111">С помощью этого командлета можно отключить все точки останова или указать конкретные точки, задав соответствующие объекты или их идентификаторы.</span><span class="sxs-lookup"><span data-stu-id="64aeb-111">You can use it to disable all breakpoints, or you can specify breakpoints by submitting breakpoint objects or breakpoint IDs.</span></span>

<span data-ttu-id="64aeb-112">Технически этот командлет изменяет значение свойства Enabled объекта точки останова на значение False.</span><span class="sxs-lookup"><span data-stu-id="64aeb-112">Technically, this cmdlet changes the value of the Enabled property of a breakpoint object to False.</span></span>
<span data-ttu-id="64aeb-113">Для повторного включения точки останова используется командлет Enable-PSBreakpoint.</span><span class="sxs-lookup"><span data-stu-id="64aeb-113">To re-enable a breakpoint, use the Enable-PSBreakpoint cmdlet.</span></span>
<span data-ttu-id="64aeb-114">Точки останова по умолчанию включаются при их создании с помощью командлета Set-PSBreakpoint.</span><span class="sxs-lookup"><span data-stu-id="64aeb-114">Breakpoints are enabled by default when you create them by using the Set-PSBreakpoint cmdlet.</span></span>

<span data-ttu-id="64aeb-115">Точка останова — это точка в скрипте, на которой выполнение временно останавливается, чтобы можно было проверить инструкции скрипта.</span><span class="sxs-lookup"><span data-stu-id="64aeb-115">A breakpoint is a point in a script where execution stops temporarily so that you can examine the instructions in the script.</span></span>
<span data-ttu-id="64aeb-116">**Disable-PSBreakpoint** — это один из нескольких командлетов, предназначенных для отладки скриптов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="64aeb-116">**Disable-PSBreakpoint** is one of several cmdlets designed for debugging PowerShell scripts.</span></span>
<span data-ttu-id="64aeb-117">Дополнительные сведения о отладчике PowerShell см. в разделе about_Debuggers.</span><span class="sxs-lookup"><span data-stu-id="64aeb-117">For more information about the PowerShell debugger, see about_Debuggers.</span></span>

## <span data-ttu-id="64aeb-118">Примеры</span><span class="sxs-lookup"><span data-stu-id="64aeb-118">EXAMPLES</span></span>

### <span data-ttu-id="64aeb-119">Пример 1. Установка точки останова и ее отключение</span><span class="sxs-lookup"><span data-stu-id="64aeb-119">Example 1: Set a breakpoint and disable it</span></span>

```
PS C:\> $B = Set-PSBreakpoint -Script "sample.ps1" -Variable "name"
PS C:\> $B | Disable-PSBreakpoint
```

<span data-ttu-id="64aeb-120">Эти команды отключают только что созданную точку останова.</span><span class="sxs-lookup"><span data-stu-id="64aeb-120">These commands disable a newly-created breakpoint.</span></span>

<span data-ttu-id="64aeb-121">Первая команда использует командлет Set-PSBreakpoint для создания точки останова на переменной *Name* в скрипте Sample.ps1.</span><span class="sxs-lookup"><span data-stu-id="64aeb-121">The first command uses the Set-PSBreakpoint cmdlet to create a breakpoint on the *Name* variable in the Sample.ps1 script.</span></span>
<span data-ttu-id="64aeb-122">Затем она сохраняет объект точки останова в переменной $b.</span><span class="sxs-lookup"><span data-stu-id="64aeb-122">Then, it saves the breakpoint object in the $B variable.</span></span>

<span data-ttu-id="64aeb-123">Вторая команда использует командлет **Disable-PSBreakpoint** для отключения новой точки останова.</span><span class="sxs-lookup"><span data-stu-id="64aeb-123">The second command uses the **Disable-PSBreakpoint** cmdlet to disable the new breakpoint.</span></span>
<span data-ttu-id="64aeb-124">Для отправки объекта точки останова в $B в командлет **Disable-PSBreakpoint** используется оператор конвейера (|).</span><span class="sxs-lookup"><span data-stu-id="64aeb-124">It uses a pipeline operator (|) to send the breakpoint object in $B to the **Disable-PSBreakpoint** cmdlet.</span></span>

<span data-ttu-id="64aeb-125">В результате выполнения этой команды значение свойства Enabled объекта точки останова в $B равно false.</span><span class="sxs-lookup"><span data-stu-id="64aeb-125">As a result of this command, the value of the Enabled property of the breakpoint object in $B is False.</span></span>

### <span data-ttu-id="64aeb-126">Пример 2. Отключение точки останова</span><span class="sxs-lookup"><span data-stu-id="64aeb-126">Example 2: Disable a breakpoint</span></span>

```
PS C:\> Disable-PSBreakpoint -Id 0
```

<span data-ttu-id="64aeb-127">Эта команда отключает точку останова с идентификатором 0.</span><span class="sxs-lookup"><span data-stu-id="64aeb-127">This command disables the breakpoint with breakpoint ID 0.</span></span>

### <span data-ttu-id="64aeb-128">Пример 3. Создание отключенной точки останова</span><span class="sxs-lookup"><span data-stu-id="64aeb-128">Example 3: Create a disabled breakpoint</span></span>

```
PS C:\> Disable-PSBreakpoint -Breakpoint ($B = Set-PSBreakpoint -Script "sample.ps1" -Line 5)
PS C:\> $B
```

<span data-ttu-id="64aeb-129">Эта команда создает новую точку останова, которая остается отключенной, пока пользователь ее не включит.</span><span class="sxs-lookup"><span data-stu-id="64aeb-129">This command creates a new breakpoint that is disabled until you enable it.</span></span>

<span data-ttu-id="64aeb-130">Для отключения точки останова используется командлет **Disable-PSBreakpoint** .</span><span class="sxs-lookup"><span data-stu-id="64aeb-130">It uses the **Disable-PSBreakpoint** cmdlet to disable the breakpoint.</span></span>
<span data-ttu-id="64aeb-131">Значение параметра *точки останова* — это Set-PSBreakpoint команда, которая задает новую точку останова, создает объект точки останова и сохраняет объект в переменной $B.</span><span class="sxs-lookup"><span data-stu-id="64aeb-131">The value of the *Breakpoint* parameter is a Set-PSBreakpoint command that sets a new breakpoint, generates a breakpoint object, and saves the object in the $B variable.</span></span>

<span data-ttu-id="64aeb-132">Параметры командлета, принимающие в качестве значений объекты, могут принять переменную, которая содержит объект, или команду, которая получает или создает объект.</span><span class="sxs-lookup"><span data-stu-id="64aeb-132">Cmdlet parameters that take objects as their values can accept a variable that contains the object or a command that gets or generates the object.</span></span>
<span data-ttu-id="64aeb-133">В этом случае, поскольку командлет **Set-PSBreakpoint** создает объект точки останова, его можно использовать в качестве значения параметра *точки останова* .</span><span class="sxs-lookup"><span data-stu-id="64aeb-133">In this case, because **Set-PSBreakpoint** generates a breakpoint object, it can be used as the value of the *Breakpoint* parameter.</span></span>

<span data-ttu-id="64aeb-134">Вторая команда отображает объект точки останова в значении переменной $B.</span><span class="sxs-lookup"><span data-stu-id="64aeb-134">The second command displays the breakpoint object in the value of the $B variable.</span></span>

### <span data-ttu-id="64aeb-135">Пример 4. Отключение всех точек останова в текущей консоли</span><span class="sxs-lookup"><span data-stu-id="64aeb-135">Example 4: Disable all breakpoints in the current console</span></span>

```
PS C:\> Get-PSBreakpoint | Disable-PSBreakpoint
```

<span data-ttu-id="64aeb-136">Эта команда отключает все точки останова в текущей консоли.</span><span class="sxs-lookup"><span data-stu-id="64aeb-136">This command disables all breakpoints in the current console.</span></span>
<span data-ttu-id="64aeb-137">Эту команду можно сократить следующим образом: "GBP | DBP».</span><span class="sxs-lookup"><span data-stu-id="64aeb-137">You can abbreviate this command as: "gbp | dbp".</span></span>

## <span data-ttu-id="64aeb-138">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="64aeb-138">PARAMETERS</span></span>

### <span data-ttu-id="64aeb-139">-Breakpoint</span><span class="sxs-lookup"><span data-stu-id="64aeb-139">-Breakpoint</span></span>

<span data-ttu-id="64aeb-140">Определяет точки останова, которые нужно отключить.</span><span class="sxs-lookup"><span data-stu-id="64aeb-140">Specifies the breakpoints to disable.</span></span>
<span data-ttu-id="64aeb-141">Введите переменную, которая содержит объекты точек останова, или команду, которая их получает (например, Get-PSBreakpoint).</span><span class="sxs-lookup"><span data-stu-id="64aeb-141">Enter a variable that contains breakpoint objects or a command that gets breakpoint objects, such as a Get-PSBreakpoint command.</span></span>
<span data-ttu-id="64aeb-142">Объекты точки останова также можно передать в командлет **Disable-PSBreakpoint** .</span><span class="sxs-lookup"><span data-stu-id="64aeb-142">You can also pipe breakpoint objects to the **Disable-PSBreakpoint** cmdlet.</span></span>

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

### <span data-ttu-id="64aeb-143">-Id</span><span class="sxs-lookup"><span data-stu-id="64aeb-143">-Id</span></span>

<span data-ttu-id="64aeb-144">Отключает точки останова с указанными идентификаторами.</span><span class="sxs-lookup"><span data-stu-id="64aeb-144">Disables the breakpoints with the specified breakpoint IDs.</span></span>
<span data-ttu-id="64aeb-145">Введите идентификаторы или переменную, которая их содержит.</span><span class="sxs-lookup"><span data-stu-id="64aeb-145">Enter the IDs or a variable that contains the IDs.</span></span>
<span data-ttu-id="64aeb-146">Невозможно передать идентификаторы в командлет **Disable-PSBreakpoint** .</span><span class="sxs-lookup"><span data-stu-id="64aeb-146">You cannot pipe IDs to **Disable-PSBreakpoint** .</span></span>

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

### <span data-ttu-id="64aeb-147">-PassThru</span><span class="sxs-lookup"><span data-stu-id="64aeb-147">-PassThru</span></span>

<span data-ttu-id="64aeb-148">Возвращает объект, представляющий включенные точки останова.</span><span class="sxs-lookup"><span data-stu-id="64aeb-148">Returns an object representing the enabled breakpoints.</span></span>
<span data-ttu-id="64aeb-149">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="64aeb-149">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="64aeb-150">-Confirm</span><span class="sxs-lookup"><span data-stu-id="64aeb-150">-Confirm</span></span>

<span data-ttu-id="64aeb-151">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="64aeb-151">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="64aeb-152">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="64aeb-152">-WhatIf</span></span>

<span data-ttu-id="64aeb-153">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="64aeb-153">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="64aeb-154">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="64aeb-154">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="64aeb-155">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="64aeb-155">CommonParameters</span></span>

<span data-ttu-id="64aeb-156">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="64aeb-156">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="64aeb-157">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="64aeb-157">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="64aeb-158">Входные данные</span><span class="sxs-lookup"><span data-stu-id="64aeb-158">INPUTS</span></span>

### <span data-ttu-id="64aeb-159">System.Management.Automation.Breakpoint</span><span class="sxs-lookup"><span data-stu-id="64aeb-159">System.Management.Automation.Breakpoint</span></span>

<span data-ttu-id="64aeb-160">Объект точки останова можно передать в командлет **Disable-PSBreakpoint** по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="64aeb-160">You can pipe a breakpoint object to **Disable-PSBreakpoint** .</span></span>

## <span data-ttu-id="64aeb-161">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="64aeb-161">OUTPUTS</span></span>

### <span data-ttu-id="64aeb-162">Нет или System.Management.Automation.Breakpoint</span><span class="sxs-lookup"><span data-stu-id="64aeb-162">None or System.Management.Automation.Breakpoint</span></span>

<span data-ttu-id="64aeb-163">При использовании параметра *PassThru* командлет **Disable-PSBreakpoint** возвращает объект, представляющий отключенную точку останова.</span><span class="sxs-lookup"><span data-stu-id="64aeb-163">When you use the *PassThru* parameter, **Disable-PSBreakpoint** returns an object that represents the disabled breakpoint.</span></span>
<span data-ttu-id="64aeb-164">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="64aeb-164">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="64aeb-165">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="64aeb-165">NOTES</span></span>

## <span data-ttu-id="64aeb-166">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="64aeb-166">RELATED LINKS</span></span>

[<span data-ttu-id="64aeb-167">Enable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="64aeb-167">Enable-PSBreakpoint</span></span>](Enable-PSBreakpoint.md)

[<span data-ttu-id="64aeb-168">Get-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="64aeb-168">Get-PSBreakpoint</span></span>](Get-PSBreakpoint.md)

[<span data-ttu-id="64aeb-169">Get-PSCallStack</span><span class="sxs-lookup"><span data-stu-id="64aeb-169">Get-PSCallStack</span></span>](Get-PSCallStack.md)

[<span data-ttu-id="64aeb-170">Remove-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="64aeb-170">Remove-PSBreakpoint</span></span>](Remove-PSBreakpoint.md)

[<span data-ttu-id="64aeb-171">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="64aeb-171">Set-PSBreakpoint</span></span>](Set-PSBreakpoint.md)
