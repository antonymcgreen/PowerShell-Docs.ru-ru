---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/debug-process?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Debug-Process
ms.openlocfilehash: 660d2b4845df8091ff8b69b28c4e7695af557122
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603948"
---
# <span data-ttu-id="e3faf-102">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="e3faf-102">Debug-Process</span></span>

## <span data-ttu-id="e3faf-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="e3faf-103">SYNOPSIS</span></span>
<span data-ttu-id="e3faf-104">Выполняет отладку одного или нескольких процессов, запущенных на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="e3faf-104">Debugs one or more processes running on the local computer.</span></span>

## <span data-ttu-id="e3faf-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e3faf-105">SYNTAX</span></span>

### <span data-ttu-id="e3faf-106">Имя (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="e3faf-106">Name (Default)</span></span>

```
Debug-Process [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="e3faf-107">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="e3faf-107">Id</span></span>

```
Debug-Process [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="e3faf-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="e3faf-108">InputObject</span></span>

```
Debug-Process -InputObject <Process[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="e3faf-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e3faf-109">DESCRIPTION</span></span>

<span data-ttu-id="e3faf-110">`Debug-Process`Командлет присоединяет отладчик к одному или нескольким запущенным процессам на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="e3faf-110">The `Debug-Process` cmdlet attaches a debugger to one or more running processes on a local computer.</span></span>
<span data-ttu-id="e3faf-111">Процессы можно указать по имени процесса или ИДЕНТИФИКАТОРу процесса (PID), или же можно передать объекты Process в этот командлет.</span><span class="sxs-lookup"><span data-stu-id="e3faf-111">You can specify the processes by their process name or process ID (PID), or you can pipe process objects to this cmdlet.</span></span>

<span data-ttu-id="e3faf-112">Этот командлет присоединяет отладчик, который в настоящее время зарегистрирован для процесса.</span><span class="sxs-lookup"><span data-stu-id="e3faf-112">This cmdlet attaches the debugger that is currently registered for the process.</span></span> <span data-ttu-id="e3faf-113">Перед использованием этого командлета убедитесь, что отладчик загружен и правильно настроен.</span><span class="sxs-lookup"><span data-stu-id="e3faf-113">Before using this cmdlet, verify that a debugger is downloaded and correctly configured.</span></span>

## <span data-ttu-id="e3faf-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="e3faf-114">EXAMPLES</span></span>

### <span data-ttu-id="e3faf-115">Пример 1. подключение отладчика к процессу на компьютере</span><span class="sxs-lookup"><span data-stu-id="e3faf-115">Example 1: Attach a debugger to a process on the computer</span></span>

```
PS C:\> Debug-Process -Name "Windows Powershell"
```

<span data-ttu-id="e3faf-116">Эта команда присоединяет отладчик к процессу PowerShell на компьютере.</span><span class="sxs-lookup"><span data-stu-id="e3faf-116">This command attaches a debugger to the PowerShell process on the computer.</span></span>

### <span data-ttu-id="e3faf-117">Пример 2. подключение отладчика ко всем процессам, начинающимся с указанной строки</span><span class="sxs-lookup"><span data-stu-id="e3faf-117">Example 2: Attach a debugger to all processes that begin with the specified string</span></span>

```
PS C:\> Debug-Process -Name "SQL*"
```

<span data-ttu-id="e3faf-118">Эта команда присоединяет отладчик ко всем процессам, имена которых начинаются с SQL.</span><span class="sxs-lookup"><span data-stu-id="e3faf-118">This command attaches a debugger to all processes that have names that begin with SQL.</span></span>

### <span data-ttu-id="e3faf-119">Пример 3. подключение отладчика к нескольким процессам</span><span class="sxs-lookup"><span data-stu-id="e3faf-119">Example 3: Attach a debugger to multiple processes</span></span>

```
PS C:\> Debug-Process "Winlogon", "Explorer", "Outlook"
```

<span data-ttu-id="e3faf-120">Эта команда присоединяет отладчик к процессам Winlogon, Explorer и Outlook.</span><span class="sxs-lookup"><span data-stu-id="e3faf-120">This command attaches a debugger to the Winlogon, Explorer, and Outlook processes.</span></span>

### <span data-ttu-id="e3faf-121">Пример 4. подключение отладчика к нескольким идентификаторам процессов</span><span class="sxs-lookup"><span data-stu-id="e3faf-121">Example 4: Attach a debugger to multiple process IDs</span></span>

```
PS C:\> Debug-Process -Id 1132, 2028
```

<span data-ttu-id="e3faf-122">Эта команда присоединяет отладчик к процессам с идентификатором 1132 и 2028.</span><span class="sxs-lookup"><span data-stu-id="e3faf-122">This command attaches a debugger to the processes that have process IDs 1132 and 2028.</span></span>

### <span data-ttu-id="e3faf-123">Пример 5. Использование Get-Process для получения процесса с последующим подключением к нему отладчика</span><span class="sxs-lookup"><span data-stu-id="e3faf-123">Example 5: Use Get-Process to get a process then attach a debugger to it</span></span>

```
PS C:\> Get-Process "Windows PowerShell" | Debug-Process
```

<span data-ttu-id="e3faf-124">Эта команда присоединяет отладчик к процессам PowerShell на компьютере.</span><span class="sxs-lookup"><span data-stu-id="e3faf-124">This command attaches a debugger to the PowerShell processes on the computer.</span></span> <span data-ttu-id="e3faf-125">Он использует `Get-Process` командлет для получения процессов PowerShell на компьютере и использует оператор конвейера ( `|` ) для отправки процессов в `Debug-Process` командлет.</span><span class="sxs-lookup"><span data-stu-id="e3faf-125">It uses the `Get-Process` cmdlet to get the PowerShell processes on the computer, and it uses a pipeline operator (`|`) to send the processes to the `Debug-Process` cmdlet.</span></span>

<span data-ttu-id="e3faf-126">Чтобы указать конкретный процесс PowerShell, используйте параметр ID параметра `Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="e3faf-126">To specify a particular PowerShell process, use the ID parameter of `Get-Process`.</span></span>

### <span data-ttu-id="e3faf-127">Пример 6. подключение отладчика к текущему процессу на локальном компьютере</span><span class="sxs-lookup"><span data-stu-id="e3faf-127">Example 6: Attach a debugger to a current process on the local computer</span></span>

```
PS C:\> $PID | Debug-Process
```

<span data-ttu-id="e3faf-128">Эта команда присоединяет отладчик к текущим процессам PowerShell на компьютере.</span><span class="sxs-lookup"><span data-stu-id="e3faf-128">This command attaches a debugger to the current PowerShell processes on the computer.</span></span>

<span data-ttu-id="e3faf-129">Команда использует `$PID` автоматическую переменную, которая содержит идентификатор процесса текущего процесса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e3faf-129">The command uses the `$PID` automatic variable, which contains the process ID of the current PowerShell process.</span></span> <span data-ttu-id="e3faf-130">Затем он использует оператор конвейера ( `|` ) для отправки идентификатора процесса в `Debug-Process` командлет.</span><span class="sxs-lookup"><span data-stu-id="e3faf-130">Then, it uses a pipeline operator (`|`) to send the process ID to the `Debug-Process` cmdlet.</span></span>

<span data-ttu-id="e3faf-131">Дополнительные сведения об `$PID` автоматической переменной см. в разделе about_Automatic_Variables.</span><span class="sxs-lookup"><span data-stu-id="e3faf-131">For more information about the `$PID` automatic variable, see about_Automatic_Variables.</span></span>

### <span data-ttu-id="e3faf-132">Пример 7. подключение отладчика к процессу, использующему параметр InputObject</span><span class="sxs-lookup"><span data-stu-id="e3faf-132">Example 7: Attach a debugger to a process that uses the InputObject parameter</span></span>

```
PS C:\> $P = Get-Process "Windows PowerShell"
PS C:\> Debug-Process -InputObject $P
```

<span data-ttu-id="e3faf-133">Эта команда присоединяет отладчик к процессам PowerShell на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="e3faf-133">This command attaches a debugger to the PowerShell processes on the local computer.</span></span>

<span data-ttu-id="e3faf-134">Первая команда использует `Get-Process` командлет для получения процессов PowerShell на компьютере.</span><span class="sxs-lookup"><span data-stu-id="e3faf-134">The first command uses the `Get-Process` cmdlet to get the PowerShell processes on the computer.</span></span> <span data-ttu-id="e3faf-135">Он сохраняет полученный объект процесса в переменной с именем `$P` .</span><span class="sxs-lookup"><span data-stu-id="e3faf-135">It saves the resulting process object in the variable named `$P`.</span></span>

<span data-ttu-id="e3faf-136">Вторая команда использует параметр **InputObject** `Debug-Process` командлета для отправки объекта процесса в `$P` переменную.</span><span class="sxs-lookup"><span data-stu-id="e3faf-136">The second command uses the **InputObject** parameter of the `Debug-Process` cmdlet to submit the process object in the `$P` variable.</span></span>

## <span data-ttu-id="e3faf-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e3faf-137">PARAMETERS</span></span>

### <span data-ttu-id="e3faf-138">-Id</span><span class="sxs-lookup"><span data-stu-id="e3faf-138">-Id</span></span>

<span data-ttu-id="e3faf-139">Указывает идентификаторы процессов, которые необходимо отладить.</span><span class="sxs-lookup"><span data-stu-id="e3faf-139">Specifies the process IDs of the processes to be debugged.</span></span> <span data-ttu-id="e3faf-140">Имя параметра **идентификатора** является необязательным.</span><span class="sxs-lookup"><span data-stu-id="e3faf-140">The **Id** parameter name is optional.</span></span>

<span data-ttu-id="e3faf-141">Чтобы найти идентификатор процесса, введите `Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="e3faf-141">To find the process ID of a process, type `Get-Process`.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases: PID, ProcessId

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="e3faf-142">-InputObject</span><span class="sxs-lookup"><span data-stu-id="e3faf-142">-InputObject</span></span>

<span data-ttu-id="e3faf-143">Указывает объекты процессов, которые необходимо отладить.</span><span class="sxs-lookup"><span data-stu-id="e3faf-143">Specifies the process objects that represent processes to be debugged.</span></span> <span data-ttu-id="e3faf-144">Введите переменную, которая содержит объекты процесса, или команду, которая получает объекты процесса, такие как `Get-Process` командлет.</span><span class="sxs-lookup"><span data-stu-id="e3faf-144">Enter a variable that contains the process objects or a command that gets the process objects, such as the `Get-Process` cmdlet.</span></span> <span data-ttu-id="e3faf-145">Вы также можете передать объекты Process в этот командлет.</span><span class="sxs-lookup"><span data-stu-id="e3faf-145">You can also pipe process objects to this cmdlet.</span></span>

```yaml
Type: System.Diagnostics.Process[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="e3faf-146">-Name</span><span class="sxs-lookup"><span data-stu-id="e3faf-146">-Name</span></span>

<span data-ttu-id="e3faf-147">Указывает имена процессов, которые необходимо отладить.</span><span class="sxs-lookup"><span data-stu-id="e3faf-147">Specifies the names of the processes to be debugged.</span></span> <span data-ttu-id="e3faf-148">Если существует несколько процессов с одним и тем же именем, этот командлет присоединяет отладчик ко всем процессам с таким именем.</span><span class="sxs-lookup"><span data-stu-id="e3faf-148">If there is more than one process with the same name, this cmdlet attaches a debugger to all processes with that name.</span></span> <span data-ttu-id="e3faf-149">Параметр **Name** является необязательным.</span><span class="sxs-lookup"><span data-stu-id="e3faf-149">The **Name** parameter is optional.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases: ProcessName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="e3faf-150">-Confirm</span><span class="sxs-lookup"><span data-stu-id="e3faf-150">-Confirm</span></span>

<span data-ttu-id="e3faf-151">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="e3faf-151">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="e3faf-152">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="e3faf-152">-WhatIf</span></span>

<span data-ttu-id="e3faf-153">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="e3faf-153">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="e3faf-154">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="e3faf-154">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="e3faf-155">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="e3faf-155">CommonParameters</span></span>

<span data-ttu-id="e3faf-156">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e3faf-156">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e3faf-157">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e3faf-157">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e3faf-158">Входные данные</span><span class="sxs-lookup"><span data-stu-id="e3faf-158">INPUTS</span></span>

### <span data-ttu-id="e3faf-159">System. Int32, System. Diagnostics. Process, System. String</span><span class="sxs-lookup"><span data-stu-id="e3faf-159">System.Int32, System.Diagnostics.Process, System.String</span></span>

<span data-ttu-id="e3faf-160">В этот командлет можно передать по конвейеру идентификатор процесса (Int32), объект процесса (System. Diagnostics. Process) или имя процесса (строка).</span><span class="sxs-lookup"><span data-stu-id="e3faf-160">You can pipe a process ID (Int32), a process object (System.Diagnostics.Process), or a process name (String) to this cmdlet.</span></span>

## <span data-ttu-id="e3faf-161">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="e3faf-161">OUTPUTS</span></span>

### <span data-ttu-id="e3faf-162">None</span><span class="sxs-lookup"><span data-stu-id="e3faf-162">None</span></span>

<span data-ttu-id="e3faf-163">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="e3faf-163">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="e3faf-164">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="e3faf-164">NOTES</span></span>

<span data-ttu-id="e3faf-165">Этот командлет использует метод AttachDebugger класса Win32_Process инструментария управления Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="e3faf-165">This cmdlet uses the AttachDebugger method of the Windows Management Instrumentation (WMI) Win32_Process class.</span></span> <span data-ttu-id="e3faf-166">Дополнительные сведения об этом методе см. в разделе [метод аттачдебугжер](https://go.microsoft.com/fwlink/?LinkId=143640) в библиотеке MSDN.</span><span class="sxs-lookup"><span data-stu-id="e3faf-166">For more information about this method, see [AttachDebugger method](https://go.microsoft.com/fwlink/?LinkId=143640) in the MSDN library.</span></span>

## <span data-ttu-id="e3faf-167">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="e3faf-167">RELATED LINKS</span></span>

[<span data-ttu-id="e3faf-168">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="e3faf-168">Debug-Process</span></span>](Debug-Process.md)

[<span data-ttu-id="e3faf-169">Get-Process</span><span class="sxs-lookup"><span data-stu-id="e3faf-169">Get-Process</span></span>](Get-Process.md)

[<span data-ttu-id="e3faf-170">Start-Process</span><span class="sxs-lookup"><span data-stu-id="e3faf-170">Start-Process</span></span>](Start-Process.md)

[<span data-ttu-id="e3faf-171">Stop-Process</span><span class="sxs-lookup"><span data-stu-id="e3faf-171">Stop-Process</span></span>](Stop-Process.md)

[<span data-ttu-id="e3faf-172">Wait-Process</span><span class="sxs-lookup"><span data-stu-id="e3faf-172">Wait-Process</span></span>](Wait-Process.md)
