---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/debug-process?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Debug-Process
ms.openlocfilehash: 98bd72901339d040748fc0d99b14bc1404ea1465
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388320"
---
# <span data-ttu-id="148fa-103">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="148fa-103">Debug-Process</span></span>

## <span data-ttu-id="148fa-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="148fa-104">SYNOPSIS</span></span>
<span data-ttu-id="148fa-105">Выполняет отладку одного или нескольких процессов, запущенных на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="148fa-105">Debugs one or more processes running on the local computer.</span></span>

## <span data-ttu-id="148fa-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="148fa-106">SYNTAX</span></span>

### <span data-ttu-id="148fa-107">Имя (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="148fa-107">Name (Default)</span></span>

```
Debug-Process [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="148fa-108">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="148fa-108">Id</span></span>

```
Debug-Process [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="148fa-109">InputObject</span><span class="sxs-lookup"><span data-stu-id="148fa-109">InputObject</span></span>

```
Debug-Process -InputObject <Process[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="148fa-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="148fa-110">DESCRIPTION</span></span>

<span data-ttu-id="148fa-111">`Debug-Process`Командлет присоединяет отладчик к одному или нескольким запущенным процессам на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="148fa-111">The `Debug-Process` cmdlet attaches a debugger to one or more running processes on a local computer.</span></span>
<span data-ttu-id="148fa-112">Процессы можно указать по имени процесса или ИДЕНТИФИКАТОРу процесса (PID), или же можно передать объекты Process в этот командлет.</span><span class="sxs-lookup"><span data-stu-id="148fa-112">You can specify the processes by their process name or process ID (PID), or you can pipe process objects to this cmdlet.</span></span>

<span data-ttu-id="148fa-113">Этот командлет присоединяет отладчик, который в настоящее время зарегистрирован для процесса.</span><span class="sxs-lookup"><span data-stu-id="148fa-113">This cmdlet attaches the debugger that is currently registered for the process.</span></span> <span data-ttu-id="148fa-114">Перед использованием этого командлета убедитесь, что отладчик загружен и правильно настроен.</span><span class="sxs-lookup"><span data-stu-id="148fa-114">Before using this cmdlet, verify that a debugger is downloaded and correctly configured.</span></span>

## <span data-ttu-id="148fa-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="148fa-115">EXAMPLES</span></span>

### <span data-ttu-id="148fa-116">Пример 1. подключение отладчика к процессу на компьютере</span><span class="sxs-lookup"><span data-stu-id="148fa-116">Example 1: Attach a debugger to a process on the computer</span></span>

```
PS C:\> Debug-Process -Name "Windows Powershell"
```

<span data-ttu-id="148fa-117">Эта команда присоединяет отладчик к процессу PowerShell на компьютере.</span><span class="sxs-lookup"><span data-stu-id="148fa-117">This command attaches a debugger to the PowerShell process on the computer.</span></span>

### <span data-ttu-id="148fa-118">Пример 2. подключение отладчика ко всем процессам, начинающимся с указанной строки</span><span class="sxs-lookup"><span data-stu-id="148fa-118">Example 2: Attach a debugger to all processes that begin with the specified string</span></span>

```
PS C:\> Debug-Process -Name "SQL*"
```

<span data-ttu-id="148fa-119">Эта команда присоединяет отладчик ко всем процессам, имена которых начинаются с SQL.</span><span class="sxs-lookup"><span data-stu-id="148fa-119">This command attaches a debugger to all processes that have names that begin with SQL.</span></span>

### <span data-ttu-id="148fa-120">Пример 3. подключение отладчика к нескольким процессам</span><span class="sxs-lookup"><span data-stu-id="148fa-120">Example 3: Attach a debugger to multiple processes</span></span>

```
PS C:\> Debug-Process "Winlogon", "Explorer", "Outlook"
```

<span data-ttu-id="148fa-121">Эта команда присоединяет отладчик к процессам Winlogon, Explorer и Outlook.</span><span class="sxs-lookup"><span data-stu-id="148fa-121">This command attaches a debugger to the Winlogon, Explorer, and Outlook processes.</span></span>

### <span data-ttu-id="148fa-122">Пример 4. подключение отладчика к нескольким идентификаторам процессов</span><span class="sxs-lookup"><span data-stu-id="148fa-122">Example 4: Attach a debugger to multiple process IDs</span></span>

```
PS C:\> Debug-Process -Id 1132, 2028
```

<span data-ttu-id="148fa-123">Эта команда присоединяет отладчик к процессам с идентификатором 1132 и 2028.</span><span class="sxs-lookup"><span data-stu-id="148fa-123">This command attaches a debugger to the processes that have process IDs 1132 and 2028.</span></span>

### <span data-ttu-id="148fa-124">Пример 5. Использование Get-Process для получения процесса с последующим подключением к нему отладчика</span><span class="sxs-lookup"><span data-stu-id="148fa-124">Example 5: Use Get-Process to get a process then attach a debugger to it</span></span>

```
PS C:\> Get-Process "Windows PowerShell" | Debug-Process
```

<span data-ttu-id="148fa-125">Эта команда присоединяет отладчик к процессам PowerShell на компьютере.</span><span class="sxs-lookup"><span data-stu-id="148fa-125">This command attaches a debugger to the PowerShell processes on the computer.</span></span> <span data-ttu-id="148fa-126">Он использует `Get-Process` командлет для получения процессов PowerShell на компьютере и использует оператор конвейера ( `|` ) для отправки процессов в `Debug-Process` командлет.</span><span class="sxs-lookup"><span data-stu-id="148fa-126">It uses the `Get-Process` cmdlet to get the PowerShell processes on the computer, and it uses a pipeline operator (`|`) to send the processes to the `Debug-Process` cmdlet.</span></span>

<span data-ttu-id="148fa-127">Чтобы указать конкретный процесс PowerShell, используйте параметр ID параметра `Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="148fa-127">To specify a particular PowerShell process, use the ID parameter of `Get-Process`.</span></span>

### <span data-ttu-id="148fa-128">Пример 6. подключение отладчика к текущему процессу на локальном компьютере</span><span class="sxs-lookup"><span data-stu-id="148fa-128">Example 6: Attach a debugger to a current process on the local computer</span></span>

```
PS C:\> $PID | Debug-Process
```

<span data-ttu-id="148fa-129">Эта команда присоединяет отладчик к текущим процессам PowerShell на компьютере.</span><span class="sxs-lookup"><span data-stu-id="148fa-129">This command attaches a debugger to the current PowerShell processes on the computer.</span></span>

<span data-ttu-id="148fa-130">Команда использует `$PID` автоматическую переменную, которая содержит идентификатор процесса текущего процесса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="148fa-130">The command uses the `$PID` automatic variable, which contains the process ID of the current PowerShell process.</span></span> <span data-ttu-id="148fa-131">Затем он использует оператор конвейера ( `|` ) для отправки идентификатора процесса в `Debug-Process` командлет.</span><span class="sxs-lookup"><span data-stu-id="148fa-131">Then, it uses a pipeline operator (`|`) to send the process ID to the `Debug-Process` cmdlet.</span></span>

<span data-ttu-id="148fa-132">Дополнительные сведения об `$PID` автоматической переменной см. в разделе about_Automatic_Variables.</span><span class="sxs-lookup"><span data-stu-id="148fa-132">For more information about the `$PID` automatic variable, see about_Automatic_Variables.</span></span>

### <span data-ttu-id="148fa-133">Пример 7. подключение отладчика к указанному процессу на нескольких компьютерах</span><span class="sxs-lookup"><span data-stu-id="148fa-133">Example 7: Attach a debugger to the specified process on multiple computers</span></span>

```
PS C:\> Get-Process -ComputerName "Server01", "Server02" -Name "MyApp" | Debug-Process
```

<span data-ttu-id="148fa-134">Эта команда присоединяет отладчик к процессам MyApp на компьютерах Server01 и Server02.</span><span class="sxs-lookup"><span data-stu-id="148fa-134">This command attaches a debugger to the MyApp processes on the Server01 and Server02 computers.</span></span>

<span data-ttu-id="148fa-135">Команда использует `Get-Process` командлет для получения процессов MyApp на компьютерах Server01 и Server02.</span><span class="sxs-lookup"><span data-stu-id="148fa-135">The command uses the `Get-Process` cmdlet to get the MyApp processes on the Server01 and Server02 computers.</span></span> <span data-ttu-id="148fa-136">Он использует оператор конвейера для отправки процессов в `Debug-Process` командлет, который прикрепляет отладчики.</span><span class="sxs-lookup"><span data-stu-id="148fa-136">It uses a pipeline operator to send the processes to the `Debug-Process` cmdlet, which attaches the debuggers.</span></span>

### <span data-ttu-id="148fa-137">Пример 8. подключение отладчика к процессу, использующему параметр InputObject</span><span class="sxs-lookup"><span data-stu-id="148fa-137">Example 8: Attach a debugger to a process that uses the InputObject parameter</span></span>

```
PS C:\> $P = Get-Process "Windows PowerShell"
PS C:\> Debug-Process -InputObject $P
```

<span data-ttu-id="148fa-138">Эта команда присоединяет отладчик к процессам PowerShell на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="148fa-138">This command attaches a debugger to the PowerShell processes on the local computer.</span></span>

<span data-ttu-id="148fa-139">Первая команда использует `Get-Process` командлет для получения процессов PowerShell на компьютере.</span><span class="sxs-lookup"><span data-stu-id="148fa-139">The first command uses the `Get-Process` cmdlet to get the PowerShell processes on the computer.</span></span> <span data-ttu-id="148fa-140">Он сохраняет полученный объект процесса в переменной с именем `$P` .</span><span class="sxs-lookup"><span data-stu-id="148fa-140">It saves the resulting process object in the variable named `$P`.</span></span>

<span data-ttu-id="148fa-141">Вторая команда использует параметр **InputObject** `Debug-Process` командлета для отправки объекта процесса в `$P` переменную.</span><span class="sxs-lookup"><span data-stu-id="148fa-141">The second command uses the **InputObject** parameter of the `Debug-Process` cmdlet to submit the process object in the `$P` variable.</span></span>

## <span data-ttu-id="148fa-142">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="148fa-142">PARAMETERS</span></span>

### <span data-ttu-id="148fa-143">-Id</span><span class="sxs-lookup"><span data-stu-id="148fa-143">-Id</span></span>

<span data-ttu-id="148fa-144">Указывает идентификаторы процессов, которые необходимо отладить.</span><span class="sxs-lookup"><span data-stu-id="148fa-144">Specifies the process IDs of the processes to be debugged.</span></span> <span data-ttu-id="148fa-145">Имя параметра **идентификатора** является необязательным.</span><span class="sxs-lookup"><span data-stu-id="148fa-145">The **Id** parameter name is optional.</span></span>

<span data-ttu-id="148fa-146">Чтобы найти идентификатор процесса, введите `Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="148fa-146">To find the process ID of a process, type `Get-Process`.</span></span>

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

### <span data-ttu-id="148fa-147">-InputObject</span><span class="sxs-lookup"><span data-stu-id="148fa-147">-InputObject</span></span>

<span data-ttu-id="148fa-148">Указывает объекты процессов, которые необходимо отладить.</span><span class="sxs-lookup"><span data-stu-id="148fa-148">Specifies the process objects that represent processes to be debugged.</span></span> <span data-ttu-id="148fa-149">Введите переменную, которая содержит объекты процесса, или команду, которая получает объекты процесса, такие как `Get-Process` командлет.</span><span class="sxs-lookup"><span data-stu-id="148fa-149">Enter a variable that contains the process objects or a command that gets the process objects, such as the `Get-Process` cmdlet.</span></span> <span data-ttu-id="148fa-150">Вы также можете передать объекты Process в этот командлет.</span><span class="sxs-lookup"><span data-stu-id="148fa-150">You can also pipe process objects to this cmdlet.</span></span>

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

### <span data-ttu-id="148fa-151">-Name</span><span class="sxs-lookup"><span data-stu-id="148fa-151">-Name</span></span>

<span data-ttu-id="148fa-152">Указывает имена процессов, которые необходимо отладить.</span><span class="sxs-lookup"><span data-stu-id="148fa-152">Specifies the names of the processes to be debugged.</span></span> <span data-ttu-id="148fa-153">Если существует несколько процессов с одним и тем же именем, этот командлет присоединяет отладчик ко всем процессам с таким именем.</span><span class="sxs-lookup"><span data-stu-id="148fa-153">If there is more than one process with the same name, this cmdlet attaches a debugger to all processes with that name.</span></span> <span data-ttu-id="148fa-154">Параметр **Name** является необязательным.</span><span class="sxs-lookup"><span data-stu-id="148fa-154">The **Name** parameter is optional.</span></span>

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

### <span data-ttu-id="148fa-155">-Confirm</span><span class="sxs-lookup"><span data-stu-id="148fa-155">-Confirm</span></span>

<span data-ttu-id="148fa-156">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="148fa-156">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="148fa-157">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="148fa-157">-WhatIf</span></span>

<span data-ttu-id="148fa-158">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="148fa-158">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="148fa-159">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="148fa-159">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="148fa-160">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="148fa-160">CommonParameters</span></span>

<span data-ttu-id="148fa-161">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="148fa-161">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="148fa-162">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="148fa-162">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="148fa-163">Входные данные</span><span class="sxs-lookup"><span data-stu-id="148fa-163">INPUTS</span></span>

### <span data-ttu-id="148fa-164">System. Int32, System. Diagnostics. Process, System. String</span><span class="sxs-lookup"><span data-stu-id="148fa-164">System.Int32, System.Diagnostics.Process, System.String</span></span>

<span data-ttu-id="148fa-165">В этот командлет можно передать по конвейеру идентификатор процесса (Int32), объект процесса (System. Diagnostics. Process) или имя процесса (строка).</span><span class="sxs-lookup"><span data-stu-id="148fa-165">You can pipe a process ID (Int32), a process object (System.Diagnostics.Process), or a process name (String) to this cmdlet.</span></span>

## <span data-ttu-id="148fa-166">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="148fa-166">OUTPUTS</span></span>

### <span data-ttu-id="148fa-167">Нет</span><span class="sxs-lookup"><span data-stu-id="148fa-167">None</span></span>

<span data-ttu-id="148fa-168">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="148fa-168">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="148fa-169">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="148fa-169">NOTES</span></span>

<span data-ttu-id="148fa-170">Этот командлет использует метод AttachDebugger класса Win32_Process инструментария управления Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="148fa-170">This cmdlet uses the AttachDebugger method of the Windows Management Instrumentation (WMI) Win32_Process class.</span></span> <span data-ttu-id="148fa-171">Дополнительные сведения об этом методе см. в разделе [метод аттачдебугжер](https://go.microsoft.com/fwlink/?LinkId=143640) в библиотеке MSDN.</span><span class="sxs-lookup"><span data-stu-id="148fa-171">For more information about this method, see [AttachDebugger method](https://go.microsoft.com/fwlink/?LinkId=143640) in the MSDN library.</span></span>

## <span data-ttu-id="148fa-172">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="148fa-172">RELATED LINKS</span></span>

[<span data-ttu-id="148fa-173">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="148fa-173">Debug-Process</span></span>](Debug-Process.md)

[<span data-ttu-id="148fa-174">Get-Process</span><span class="sxs-lookup"><span data-stu-id="148fa-174">Get-Process</span></span>](Get-Process.md)

[<span data-ttu-id="148fa-175">Start-Process</span><span class="sxs-lookup"><span data-stu-id="148fa-175">Start-Process</span></span>](Start-Process.md)

[<span data-ttu-id="148fa-176">Stop-Process</span><span class="sxs-lookup"><span data-stu-id="148fa-176">Stop-Process</span></span>](Stop-Process.md)

[<span data-ttu-id="148fa-177">Wait-Process</span><span class="sxs-lookup"><span data-stu-id="148fa-177">Wait-Process</span></span>](Wait-Process.md)
