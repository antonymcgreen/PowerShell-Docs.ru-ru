---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-psbreakpoint?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSBreakpoint
ms.openlocfilehash: a56b9041c0ae70def7df619f2a4d265cb631fe7b
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599368"
---
# <span data-ttu-id="9cd48-102">Remove-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="9cd48-102">Remove-PSBreakpoint</span></span>

## <span data-ttu-id="9cd48-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="9cd48-103">SYNOPSIS</span></span>
<span data-ttu-id="9cd48-104">Удаляет из текущей консоли точки останова.</span><span class="sxs-lookup"><span data-stu-id="9cd48-104">Deletes breakpoints from the current console.</span></span>

## <span data-ttu-id="9cd48-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9cd48-105">SYNTAX</span></span>

### <span data-ttu-id="9cd48-106">Точка останова (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="9cd48-106">Breakpoint (Default)</span></span>

```
Remove-PSBreakpoint [-Breakpoint] <Breakpoint[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9cd48-107">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="9cd48-107">Id</span></span>

```
Remove-PSBreakpoint [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="9cd48-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9cd48-108">DESCRIPTION</span></span>
<span data-ttu-id="9cd48-109">Командлет **Remove-PSBreakpoint** удаляет точку останова.</span><span class="sxs-lookup"><span data-stu-id="9cd48-109">The **Remove-PSBreakpoint** cmdlet deletes a breakpoint.</span></span>
<span data-ttu-id="9cd48-110">Введите объект или идентификатор точки останова.</span><span class="sxs-lookup"><span data-stu-id="9cd48-110">Enter a breakpoint object or a breakpoint ID.</span></span>

<span data-ttu-id="9cd48-111">При удалении точки останова объект точки останова становится недоступным и перестает функционировать.</span><span class="sxs-lookup"><span data-stu-id="9cd48-111">When you remove a breakpoint, the breakpoint object is no longer available or functional.</span></span>
<span data-ttu-id="9cd48-112">Если объект точки останова сохранен в переменную, ссылка остается, но точка останова не работает.</span><span class="sxs-lookup"><span data-stu-id="9cd48-112">If you have saved a breakpoint object in a variable, the reference still exists, but the breakpoint does not function.</span></span>

<span data-ttu-id="9cd48-113">**Remove-PSBreakpoint** — это один из нескольких командлетов, предназначенных для отладки скриптов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9cd48-113">**Remove-PSBreakpoint** is one of several cmdlets designed for debugging PowerShell scripts.</span></span>
<span data-ttu-id="9cd48-114">Дополнительные сведения о отладчике PowerShell см. в разделе about_Debuggers.</span><span class="sxs-lookup"><span data-stu-id="9cd48-114">For more information about the PowerShell debugger, see about_Debuggers.</span></span>

## <span data-ttu-id="9cd48-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="9cd48-115">EXAMPLES</span></span>

### <span data-ttu-id="9cd48-116">Пример 1. Удаление всех точек останова</span><span class="sxs-lookup"><span data-stu-id="9cd48-116">Example 1: Remove all breakpoints</span></span>

```
PS C:\> Get-PSBreakpoint | Remove-PSBreakpoint
```

<span data-ttu-id="9cd48-117">Эта команда удаляет все точки останова в текущей консоли.</span><span class="sxs-lookup"><span data-stu-id="9cd48-117">This command deletes all of the breakpoints in the current console.</span></span>

### <span data-ttu-id="9cd48-118">Пример 2. Удаление указанной точки останова</span><span class="sxs-lookup"><span data-stu-id="9cd48-118">Example 2: Remove a specified breakpoint</span></span>

```
PS C:\> $B = Set-PSBreakpoint -Script "sample.ps1" -Variable "Name"
PS C:\> $B | Remove-PSBreakpoint
```

<span data-ttu-id="9cd48-119">Эта команда удаляет точку останова.</span><span class="sxs-lookup"><span data-stu-id="9cd48-119">This command deletes a breakpoint.</span></span>

<span data-ttu-id="9cd48-120">Первая команда использует командлет Set-PSBreakpoint для создания точки останова на переменной Name в скрипте Sample.ps1.</span><span class="sxs-lookup"><span data-stu-id="9cd48-120">The first command uses the Set-PSBreakpoint cmdlet to create a breakpoint on the Name variable in the Sample.ps1 script.</span></span>
<span data-ttu-id="9cd48-121">Затем она сохраняет объект точки останова в переменной $b.</span><span class="sxs-lookup"><span data-stu-id="9cd48-121">Then, it saves the breakpoint object in the $B variable.</span></span>

<span data-ttu-id="9cd48-122">Вторая команда использует командлет **Remove-PSBreakpoint** для удаления новой точки останова.</span><span class="sxs-lookup"><span data-stu-id="9cd48-122">The second command uses the **Remove-PSBreakpoint** cmdlet to delete the new breakpoint.</span></span>
<span data-ttu-id="9cd48-123">Он использует оператор конвейера (|) для отправки объекта точки останова в переменную $B в командлет **Remove-PSBreakpoint** .</span><span class="sxs-lookup"><span data-stu-id="9cd48-123">It uses a pipeline operator (|) to send the breakpoint object in the $B variable to the **Remove-PSBreakpoint** cmdlet.</span></span>

<span data-ttu-id="9cd48-124">В результате выполнения этой команды запущенный скрипт выполняется до завершения без остановки.</span><span class="sxs-lookup"><span data-stu-id="9cd48-124">As a result of this command, if you run the script, it runs to completion without stopping.</span></span>
<span data-ttu-id="9cd48-125">Кроме того, командлет **Get-PSBreakpoint** не возвращает эту точку останова.</span><span class="sxs-lookup"><span data-stu-id="9cd48-125">Also, the **Get-PSBreakpoint** cmdlet does not return this breakpoint.</span></span>

### <span data-ttu-id="9cd48-126">Пример 3. Удаление точки останова по ИДЕНТИФИКАТОРу</span><span class="sxs-lookup"><span data-stu-id="9cd48-126">Example 3: Remove a breakpoint by ID</span></span>

```
PS C:\> Remove-PSBreakpoint -Id 2
```

<span data-ttu-id="9cd48-127">Эта команда удаляет точку останова с идентификатором 2.</span><span class="sxs-lookup"><span data-stu-id="9cd48-127">This command deletes the breakpoint with breakpoint ID 2.</span></span>

### <span data-ttu-id="9cd48-128">Пример 4. Удаление всех точек останова с помощью функции</span><span class="sxs-lookup"><span data-stu-id="9cd48-128">Example 4: Use a function to remove all breakpoints</span></span>

```
PS C:\> function del-psb { get-psbreakpoint | remove-psbreakpoint }
```

<span data-ttu-id="9cd48-129">Эта простая функция удаляет все точки останова в текущей консоли.</span><span class="sxs-lookup"><span data-stu-id="9cd48-129">This simple function deletes all of the breakpoints in the current console.</span></span>
<span data-ttu-id="9cd48-130">С помощью командлета Get-PSBreakpoint она получает точки останова.</span><span class="sxs-lookup"><span data-stu-id="9cd48-130">It uses the Get-PSBreakpoint cmdlet to get the breakpoints.</span></span>
<span data-ttu-id="9cd48-131">Затем он использует оператор конвейера (|) для отправки точек останова в командлет **Remove-PSBreakpoint** , который удаляет их.</span><span class="sxs-lookup"><span data-stu-id="9cd48-131">Then, it uses a pipeline operator (|) to send the breakpoints to the **Remove-PSBreakpoint** cmdlet, which deletes them.</span></span>

<span data-ttu-id="9cd48-132">В результате `del-psb` вместо более длинной команды можно ввести.</span><span class="sxs-lookup"><span data-stu-id="9cd48-132">As a result, you can type `del-psb` instead of the longer command.</span></span>

<span data-ttu-id="9cd48-133">Чтобы сохранить функцию, добавьте ее в профиль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9cd48-133">To save the function, add it to your PowerShell profile.</span></span>

## <span data-ttu-id="9cd48-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9cd48-134">PARAMETERS</span></span>

### <span data-ttu-id="9cd48-135">-Breakpoint</span><span class="sxs-lookup"><span data-stu-id="9cd48-135">-Breakpoint</span></span>
<span data-ttu-id="9cd48-136">Определяет точки останова для удаления.</span><span class="sxs-lookup"><span data-stu-id="9cd48-136">Specifies the breakpoints to delete.</span></span>
<span data-ttu-id="9cd48-137">Введите переменную, которая содержит объекты точки останова, или команду, которая получает объекты точки останова, такие как команда **Get-PSBreakpoint** .</span><span class="sxs-lookup"><span data-stu-id="9cd48-137">Enter a variable that contains breakpoint objects or a command that gets breakpoint objects, such as a **Get-PSBreakpoint** command.</span></span>
<span data-ttu-id="9cd48-138">Кроме того, можно передать объекты точки останова в командлет **Remove-PSBreakpoint**.</span><span class="sxs-lookup"><span data-stu-id="9cd48-138">You can also pipe breakpoint objects to **Remove-PSBreakpoint**.</span></span>

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

### <span data-ttu-id="9cd48-139">-Id</span><span class="sxs-lookup"><span data-stu-id="9cd48-139">-Id</span></span>
<span data-ttu-id="9cd48-140">Указывает идентификаторы точек останова, для которых этот командлет удаляет точки останова.</span><span class="sxs-lookup"><span data-stu-id="9cd48-140">Specifies breakpoint IDs for which this cmdlet deletes breakpoints.</span></span>

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

### <span data-ttu-id="9cd48-141">-Confirm</span><span class="sxs-lookup"><span data-stu-id="9cd48-141">-Confirm</span></span>
<span data-ttu-id="9cd48-142">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="9cd48-142">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="9cd48-143">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="9cd48-143">-WhatIf</span></span>
<span data-ttu-id="9cd48-144">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="9cd48-144">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="9cd48-145">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="9cd48-145">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="9cd48-146">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="9cd48-146">CommonParameters</span></span>
<span data-ttu-id="9cd48-147">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9cd48-147">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9cd48-148">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9cd48-148">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9cd48-149">Входные данные</span><span class="sxs-lookup"><span data-stu-id="9cd48-149">INPUTS</span></span>

### <span data-ttu-id="9cd48-150">System.Management.Automation.Breakpoint</span><span class="sxs-lookup"><span data-stu-id="9cd48-150">System.Management.Automation.Breakpoint</span></span>
<span data-ttu-id="9cd48-151">Объекты точки останова можно передать в командлет **Remove-PSBreakpoint** по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="9cd48-151">You can pipe breakpoint objects to **Remove-PSBreakpoint**.</span></span>

## <span data-ttu-id="9cd48-152">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="9cd48-152">OUTPUTS</span></span>

### <span data-ttu-id="9cd48-153">None</span><span class="sxs-lookup"><span data-stu-id="9cd48-153">None</span></span>
<span data-ttu-id="9cd48-154">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="9cd48-154">The cmdlet does not generate any output.</span></span>

## <span data-ttu-id="9cd48-155">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="9cd48-155">NOTES</span></span>

## <span data-ttu-id="9cd48-156">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="9cd48-156">RELATED LINKS</span></span>

[<span data-ttu-id="9cd48-157">Disable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="9cd48-157">Disable-PSBreakpoint</span></span>](Disable-PSBreakpoint.md)

[<span data-ttu-id="9cd48-158">Enable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="9cd48-158">Enable-PSBreakpoint</span></span>](Enable-PSBreakpoint.md)

[<span data-ttu-id="9cd48-159">Get-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="9cd48-159">Get-PSBreakpoint</span></span>](Get-PSBreakpoint.md)

[<span data-ttu-id="9cd48-160">Get-PSCallStack</span><span class="sxs-lookup"><span data-stu-id="9cd48-160">Get-PSCallStack</span></span>](Get-PSCallStack.md)

[<span data-ttu-id="9cd48-161">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="9cd48-161">Set-PSBreakpoint</span></span>](Set-PSBreakpoint.md)

