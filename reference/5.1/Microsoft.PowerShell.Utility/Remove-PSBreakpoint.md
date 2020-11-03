---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-psbreakpoint?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSBreakpoint
ms.openlocfilehash: b12913cd10c2c505322c1f922a05ecc98987e830
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227542"
---
# <span data-ttu-id="ef502-103">Remove-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="ef502-103">Remove-PSBreakpoint</span></span>

## <span data-ttu-id="ef502-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="ef502-104">SYNOPSIS</span></span>
<span data-ttu-id="ef502-105">Удаляет из текущей консоли точки останова.</span><span class="sxs-lookup"><span data-stu-id="ef502-105">Deletes breakpoints from the current console.</span></span>

## <span data-ttu-id="ef502-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ef502-106">SYNTAX</span></span>

### <span data-ttu-id="ef502-107">Точка останова (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="ef502-107">Breakpoint (Default)</span></span>

```
Remove-PSBreakpoint [-Breakpoint] <Breakpoint[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="ef502-108">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="ef502-108">Id</span></span>

```
Remove-PSBreakpoint [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="ef502-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ef502-109">DESCRIPTION</span></span>
<span data-ttu-id="ef502-110">Командлет **Remove-PSBreakpoint** удаляет точку останова.</span><span class="sxs-lookup"><span data-stu-id="ef502-110">The **Remove-PSBreakpoint** cmdlet deletes a breakpoint.</span></span>
<span data-ttu-id="ef502-111">Введите объект или идентификатор точки останова.</span><span class="sxs-lookup"><span data-stu-id="ef502-111">Enter a breakpoint object or a breakpoint ID.</span></span>

<span data-ttu-id="ef502-112">При удалении точки останова объект точки останова становится недоступным и перестает функционировать.</span><span class="sxs-lookup"><span data-stu-id="ef502-112">When you remove a breakpoint, the breakpoint object is no longer available or functional.</span></span>
<span data-ttu-id="ef502-113">Если объект точки останова сохранен в переменную, ссылка остается, но точка останова не работает.</span><span class="sxs-lookup"><span data-stu-id="ef502-113">If you have saved a breakpoint object in a variable, the reference still exists, but the breakpoint does not function.</span></span>

<span data-ttu-id="ef502-114">**Remove-PSBreakpoint** — это один из нескольких командлетов, предназначенных для отладки сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ef502-114">**Remove-PSBreakpoint** is one of several cmdlets designed for debugging Windows PowerShell scripts.</span></span>
<span data-ttu-id="ef502-115">Дополнительные сведения об отладчике Windows PowerShell см. в разделе about_Debuggers.</span><span class="sxs-lookup"><span data-stu-id="ef502-115">For more information about the Windows PowerShell debugger, see about_Debuggers.</span></span>

## <span data-ttu-id="ef502-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="ef502-116">EXAMPLES</span></span>

### <span data-ttu-id="ef502-117">Пример 1. Удаление всех точек останова</span><span class="sxs-lookup"><span data-stu-id="ef502-117">Example 1: Remove all breakpoints</span></span>

```
PS C:\> Get-PSBreakpoint | Remove-PSBreakpoint
```

<span data-ttu-id="ef502-118">Эта команда удаляет все точки останова в текущей консоли.</span><span class="sxs-lookup"><span data-stu-id="ef502-118">This command deletes all of the breakpoints in the current console.</span></span>

### <span data-ttu-id="ef502-119">Пример 2. Удаление указанной точки останова</span><span class="sxs-lookup"><span data-stu-id="ef502-119">Example 2: Remove a specified breakpoint</span></span>

```
PS C:\> $B = Set-PSBreakpoint -Script "sample.ps1" -Variable "Name"
PS C:\> $B | Remove-PSBreakpoint
```

<span data-ttu-id="ef502-120">Эта команда удаляет точку останова.</span><span class="sxs-lookup"><span data-stu-id="ef502-120">This command deletes a breakpoint.</span></span>

<span data-ttu-id="ef502-121">Первая команда использует командлет Set-PSBreakpoint для создания точки останова на переменной Name в скрипте Sample.ps1.</span><span class="sxs-lookup"><span data-stu-id="ef502-121">The first command uses the Set-PSBreakpoint cmdlet to create a breakpoint on the Name variable in the Sample.ps1 script.</span></span>
<span data-ttu-id="ef502-122">Затем она сохраняет объект точки останова в переменной $b.</span><span class="sxs-lookup"><span data-stu-id="ef502-122">Then, it saves the breakpoint object in the $B variable.</span></span>

<span data-ttu-id="ef502-123">Вторая команда использует командлет **Remove-PSBreakpoint** для удаления новой точки останова.</span><span class="sxs-lookup"><span data-stu-id="ef502-123">The second command uses the **Remove-PSBreakpoint** cmdlet to delete the new breakpoint.</span></span>
<span data-ttu-id="ef502-124">Он использует оператор конвейера (|) для отправки объекта точки останова в переменную $B в командлет **Remove-PSBreakpoint** .</span><span class="sxs-lookup"><span data-stu-id="ef502-124">It uses a pipeline operator (|) to send the breakpoint object in the $B variable to the **Remove-PSBreakpoint** cmdlet.</span></span>

<span data-ttu-id="ef502-125">В результате выполнения этой команды запущенный скрипт выполняется до завершения без остановки.</span><span class="sxs-lookup"><span data-stu-id="ef502-125">As a result of this command, if you run the script, it runs to completion without stopping.</span></span>
<span data-ttu-id="ef502-126">Кроме того, командлет **Get-PSBreakpoint** не возвращает эту точку останова.</span><span class="sxs-lookup"><span data-stu-id="ef502-126">Also, the **Get-PSBreakpoint** cmdlet does not return this breakpoint.</span></span>

### <span data-ttu-id="ef502-127">Пример 3. Удаление точки останова по ИДЕНТИФИКАТОРу</span><span class="sxs-lookup"><span data-stu-id="ef502-127">Example 3: Remove a breakpoint by ID</span></span>

```
PS C:\> Remove-PSBreakpoint -Id 2
```

<span data-ttu-id="ef502-128">Эта команда удаляет точку останова с идентификатором 2.</span><span class="sxs-lookup"><span data-stu-id="ef502-128">This command deletes the breakpoint with breakpoint ID 2.</span></span>

### <span data-ttu-id="ef502-129">Пример 4. Удаление всех точек останова с помощью функции</span><span class="sxs-lookup"><span data-stu-id="ef502-129">Example 4: Use a function to remove all breakpoints</span></span>

```
PS C:\> function del-psb { get-psbreakpoint | remove-psbreakpoint }
```

<span data-ttu-id="ef502-130">Эта простая функция удаляет все точки останова в текущей консоли.</span><span class="sxs-lookup"><span data-stu-id="ef502-130">This simple function deletes all of the breakpoints in the current console.</span></span>
<span data-ttu-id="ef502-131">С помощью командлета Get-PSBreakpoint она получает точки останова.</span><span class="sxs-lookup"><span data-stu-id="ef502-131">It uses the Get-PSBreakpoint cmdlet to get the breakpoints.</span></span>
<span data-ttu-id="ef502-132">Затем он использует оператор конвейера (|) для отправки точек останова в командлет **Remove-PSBreakpoint** , который удаляет их.</span><span class="sxs-lookup"><span data-stu-id="ef502-132">Then, it uses a pipeline operator (|) to send the breakpoints to the **Remove-PSBreakpoint** cmdlet, which deletes them.</span></span>

<span data-ttu-id="ef502-133">В результате `del-psb` вместо более длинной команды можно ввести.</span><span class="sxs-lookup"><span data-stu-id="ef502-133">As a result, you can type `del-psb` instead of the longer command.</span></span>

<span data-ttu-id="ef502-134">Чтобы сохранить функцию, добавьте ее в свой профиль Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ef502-134">To save the function, add it to your Windows PowerShell profile.</span></span>

## <span data-ttu-id="ef502-135">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ef502-135">PARAMETERS</span></span>

### <span data-ttu-id="ef502-136">-Breakpoint</span><span class="sxs-lookup"><span data-stu-id="ef502-136">-Breakpoint</span></span>
<span data-ttu-id="ef502-137">Определяет точки останова для удаления.</span><span class="sxs-lookup"><span data-stu-id="ef502-137">Specifies the breakpoints to delete.</span></span>
<span data-ttu-id="ef502-138">Введите переменную, которая содержит объекты точки останова, или команду, которая получает объекты точки останова, такие как команда **Get-PSBreakpoint** .</span><span class="sxs-lookup"><span data-stu-id="ef502-138">Enter a variable that contains breakpoint objects or a command that gets breakpoint objects, such as a **Get-PSBreakpoint** command.</span></span>
<span data-ttu-id="ef502-139">Кроме того, можно передать объекты точки останова в командлет **Remove-PSBreakpoint**.</span><span class="sxs-lookup"><span data-stu-id="ef502-139">You can also pipe breakpoint objects to **Remove-PSBreakpoint**.</span></span>

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

### <span data-ttu-id="ef502-140">-Id</span><span class="sxs-lookup"><span data-stu-id="ef502-140">-Id</span></span>
<span data-ttu-id="ef502-141">Указывает идентификаторы точек останова, для которых этот командлет удаляет точки останова.</span><span class="sxs-lookup"><span data-stu-id="ef502-141">Specifies breakpoint IDs for which this cmdlet deletes breakpoints.</span></span>

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

### <span data-ttu-id="ef502-142">-Confirm</span><span class="sxs-lookup"><span data-stu-id="ef502-142">-Confirm</span></span>
<span data-ttu-id="ef502-143">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="ef502-143">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="ef502-144">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="ef502-144">-WhatIf</span></span>
<span data-ttu-id="ef502-145">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="ef502-145">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="ef502-146">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="ef502-146">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="ef502-147">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="ef502-147">CommonParameters</span></span>
<span data-ttu-id="ef502-148">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ef502-148">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ef502-149">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ef502-149">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ef502-150">Входные данные</span><span class="sxs-lookup"><span data-stu-id="ef502-150">INPUTS</span></span>

### <span data-ttu-id="ef502-151">System.Management.Automation.Breakpoint</span><span class="sxs-lookup"><span data-stu-id="ef502-151">System.Management.Automation.Breakpoint</span></span>
<span data-ttu-id="ef502-152">Объекты точки останова можно передать в командлет **Remove-PSBreakpoint** по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="ef502-152">You can pipe breakpoint objects to **Remove-PSBreakpoint**.</span></span>

## <span data-ttu-id="ef502-153">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="ef502-153">OUTPUTS</span></span>

### <span data-ttu-id="ef502-154">Нет</span><span class="sxs-lookup"><span data-stu-id="ef502-154">None</span></span>
<span data-ttu-id="ef502-155">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="ef502-155">The cmdlet does not generate any output.</span></span>

## <span data-ttu-id="ef502-156">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="ef502-156">NOTES</span></span>

## <span data-ttu-id="ef502-157">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="ef502-157">RELATED LINKS</span></span>

[<span data-ttu-id="ef502-158">Disable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="ef502-158">Disable-PSBreakpoint</span></span>](Disable-PSBreakpoint.md)

[<span data-ttu-id="ef502-159">Enable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="ef502-159">Enable-PSBreakpoint</span></span>](Enable-PSBreakpoint.md)

[<span data-ttu-id="ef502-160">Get-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="ef502-160">Get-PSBreakpoint</span></span>](Get-PSBreakpoint.md)

[<span data-ttu-id="ef502-161">Get-PSCallStack</span><span class="sxs-lookup"><span data-stu-id="ef502-161">Get-PSCallStack</span></span>](Get-PSCallStack.md)

[<span data-ttu-id="ef502-162">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="ef502-162">Set-PSBreakpoint</span></span>](Set-PSBreakpoint.md)
