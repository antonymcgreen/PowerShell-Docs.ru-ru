---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/debug-process?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Debug-Process
ms.openlocfilehash: 1cc0b0f51d84f3471bc3f54a91daba10f3528a8a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228433"
---
# <span data-ttu-id="3b9ff-103">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="3b9ff-103">Debug-Process</span></span>

## <span data-ttu-id="3b9ff-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="3b9ff-104">SYNOPSIS</span></span>
<span data-ttu-id="3b9ff-105">Выполняет отладку одного или нескольких процессов, запущенных на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3b9ff-105">Debugs one or more processes running on the local computer.</span></span>

## <span data-ttu-id="3b9ff-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3b9ff-106">SYNTAX</span></span>

### <span data-ttu-id="3b9ff-107">Имя (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="3b9ff-107">Name (Default)</span></span>

```
Debug-Process [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="3b9ff-108">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="3b9ff-108">Id</span></span>

```
Debug-Process [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="3b9ff-109">InputObject</span><span class="sxs-lookup"><span data-stu-id="3b9ff-109">InputObject</span></span>

```
Debug-Process -InputObject <Process[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="3b9ff-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3b9ff-110">DESCRIPTION</span></span>
<span data-ttu-id="3b9ff-111">Командлет **Debug-Process** присоединяет отладчик к одному или нескольким запущенным процессам на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3b9ff-111">The **Debug-Process** cmdlet attaches a debugger to one or more running processes on a local computer.</span></span>
<span data-ttu-id="3b9ff-112">Процессы можно указать по имени процесса или ИДЕНТИФИКАТОРу процесса (PID), или же можно передать объекты Process в этот командлет.</span><span class="sxs-lookup"><span data-stu-id="3b9ff-112">You can specify the processes by their process name or process ID (PID), or you can pipe process objects to this cmdlet.</span></span>

<span data-ttu-id="3b9ff-113">Этот командлет присоединяет отладчик, который в настоящее время зарегистрирован для процесса.</span><span class="sxs-lookup"><span data-stu-id="3b9ff-113">This cmdlet attaches the debugger that is currently registered for the process.</span></span>
<span data-ttu-id="3b9ff-114">Перед использованием этого командлета убедитесь, что отладчик загружен и правильно настроен.</span><span class="sxs-lookup"><span data-stu-id="3b9ff-114">Before using this cmdlet, verify that a debugger is downloaded and correctly configured.</span></span>

## <span data-ttu-id="3b9ff-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="3b9ff-115">EXAMPLES</span></span>

### <span data-ttu-id="3b9ff-116">Пример 1. подключение отладчика к процессу на компьютере</span><span class="sxs-lookup"><span data-stu-id="3b9ff-116">Example 1: Attach a debugger to a process on the computer</span></span>

```
PS C:\> Debug-Process -Name "Windows Powershell"
```

<span data-ttu-id="3b9ff-117">Эта команда присоединяет отладчик к процессу Windows PowerShell на компьютере.</span><span class="sxs-lookup"><span data-stu-id="3b9ff-117">This command attaches a debugger to the Windows PowerShell process on the computer.</span></span>

### <span data-ttu-id="3b9ff-118">Пример 2. подключение отладчика ко всем процессам, начинающимся с указанной строки</span><span class="sxs-lookup"><span data-stu-id="3b9ff-118">Example 2: Attach a debugger to all processes that begin with the specified string</span></span>

```
PS C:\> Debug-Process -Name "SQL*"
```

<span data-ttu-id="3b9ff-119">Эта команда присоединяет отладчик ко всем процессам, имена которых начинаются с SQL.</span><span class="sxs-lookup"><span data-stu-id="3b9ff-119">This command attaches a debugger to all processes that have names that begin with SQL.</span></span>

### <span data-ttu-id="3b9ff-120">Пример 3. подключение отладчика к нескольким процессам</span><span class="sxs-lookup"><span data-stu-id="3b9ff-120">Example 3: Attach a debugger to multiple processes</span></span>

```
PS C:\> Debug-Process "Winlogon", "Explorer", "Outlook"
```

<span data-ttu-id="3b9ff-121">Эта команда присоединяет отладчик к процессам Winlogon, Explorer и Outlook.</span><span class="sxs-lookup"><span data-stu-id="3b9ff-121">This command attaches a debugger to the Winlogon, Explorer, and Outlook processes.</span></span>

### <span data-ttu-id="3b9ff-122">Пример 4. подключение отладчика к нескольким идентификаторам процессов</span><span class="sxs-lookup"><span data-stu-id="3b9ff-122">Example 4: Attach a debugger to multiple process IDs</span></span>

```
PS C:\> Debug-Process -Id 1132, 2028
```

<span data-ttu-id="3b9ff-123">Эта команда присоединяет отладчик к процессам с идентификатором 1132 и 2028.</span><span class="sxs-lookup"><span data-stu-id="3b9ff-123">This command attaches a debugger to the processes that have process IDs 1132 and 2028.</span></span>

### <span data-ttu-id="3b9ff-124">Пример 5. Использование Get-Process для получения процесса с последующим подключением к нему отладчика</span><span class="sxs-lookup"><span data-stu-id="3b9ff-124">Example 5: Use Get-Process to get a process then attach a debugger to it</span></span>

```
PS C:\> Get-Process "Windows PowerShell" | Debug-Process
```

<span data-ttu-id="3b9ff-125">Эта команда присоединяет отладчик к процессам Windows PowerShell на компьютере.</span><span class="sxs-lookup"><span data-stu-id="3b9ff-125">This command attaches a debugger to the Windows PowerShell processes on the computer.</span></span>
<span data-ttu-id="3b9ff-126">Он использует командлет **Get-Process** для получения процессов Windows PowerShell на компьютере и использует оператор конвейера (|) для отправки процессов в командлет **Debug-Process** .</span><span class="sxs-lookup"><span data-stu-id="3b9ff-126">It uses the **Get-Process** cmdlet to get the Windows PowerShell processes on the computer, and it uses a pipeline operator (|) to send the processes to the **Debug-Process** cmdlet.</span></span>

<span data-ttu-id="3b9ff-127">Чтобы указать конкретный процесс PowerShell, используйте параметр ID командлета **Get-Process** .</span><span class="sxs-lookup"><span data-stu-id="3b9ff-127">To specify a particular PowerShell process, use the ID parameter of **Get-Process** .</span></span>

### <span data-ttu-id="3b9ff-128">Пример 6. подключение отладчика к текущему процессу на локальном компьютере</span><span class="sxs-lookup"><span data-stu-id="3b9ff-128">Example 6: Attach a debugger to a current process on the local computer</span></span>

```
PS C:\> $PID | Debug-Process
```

<span data-ttu-id="3b9ff-129">Эта команда присоединяет отладчик к текущим процессам Windows PowerShell на компьютере.</span><span class="sxs-lookup"><span data-stu-id="3b9ff-129">This command attaches a debugger to the current Windows PowerShell processes on the computer.</span></span>

<span data-ttu-id="3b9ff-130">Команда использует автоматическую переменную $PID, которая содержит идентификатор процесса текущего процесса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3b9ff-130">The command uses the $PID automatic variable, which contains the process ID of the current Windows PowerShell process.</span></span>
<span data-ttu-id="3b9ff-131">Затем он использует оператор конвейера (|) для отправки идентификатора процесса в командлет **Debug-Process** .</span><span class="sxs-lookup"><span data-stu-id="3b9ff-131">Then, it uses a pipeline operator (|) to send the process ID to the **Debug-Process** cmdlet.</span></span>

<span data-ttu-id="3b9ff-132">Дополнительные сведения об автоматической переменной $PID см. в разделе about_Automatic_Variables.</span><span class="sxs-lookup"><span data-stu-id="3b9ff-132">For more information about the $PID automatic variable, see about_Automatic_Variables.</span></span>

### <span data-ttu-id="3b9ff-133">Пример 7. подключение отладчика к указанному процессу на нескольких компьютерах</span><span class="sxs-lookup"><span data-stu-id="3b9ff-133">Example 7: Attach a debugger to the specified process on multiple computers</span></span>

```
PS C:\> Get-Process -ComputerName "Server01", "Server02" -Name "MyApp" | Debug-Process
```

<span data-ttu-id="3b9ff-134">Эта команда присоединяет отладчик к процессам MyApp на компьютерах Server01 и Server02.</span><span class="sxs-lookup"><span data-stu-id="3b9ff-134">This command attaches a debugger to the MyApp processes on the Server01 and Server02 computers.</span></span>

<span data-ttu-id="3b9ff-135">Команда использует командлет **Get-Process** для получения процессов MyApp на компьютерах Server01 и Server02.</span><span class="sxs-lookup"><span data-stu-id="3b9ff-135">The command uses the **Get-Process** cmdlet to get the MyApp processes on the Server01 and Server02 computers.</span></span>
<span data-ttu-id="3b9ff-136">Оператор конвейера (|) применяется для отправки процессов командлету Debug-Process, который присоединяет отладчики.</span><span class="sxs-lookup"><span data-stu-id="3b9ff-136">It uses a pipeline operator to send the processes to the Debug-Process cmdlet, which attaches the debuggers.</span></span>

### <span data-ttu-id="3b9ff-137">Пример 8. подключение отладчика к процессу, использующему параметр InputObject</span><span class="sxs-lookup"><span data-stu-id="3b9ff-137">Example 8: Attach a debugger to a process that uses the InputObject parameter</span></span>

```
PS C:\> $P = Get-Process "Windows PowerShell"
PS C:\> Debug-Process -InputObject $P
```

<span data-ttu-id="3b9ff-138">Эта команда присоединяет отладчик к процессам Windows PowerShell на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3b9ff-138">This command attaches a debugger to the Windows PowerShell processes on the local computer.</span></span>

<span data-ttu-id="3b9ff-139">Первая команда использует командлет **Get-Process** для получения процессов Windows PowerShell на компьютере.</span><span class="sxs-lookup"><span data-stu-id="3b9ff-139">The first command uses the **Get-Process** cmdlet to get the Windows PowerShell processes on the computer.</span></span>
<span data-ttu-id="3b9ff-140">Он сохраняет полученный объект процесса в переменной с именем $P.</span><span class="sxs-lookup"><span data-stu-id="3b9ff-140">It saves the resulting process object in the variable named $P.</span></span>

<span data-ttu-id="3b9ff-141">Вторая команда использует параметр *InputObject* командлета **Debug-Process** для отправки объекта процесса в переменную $P.</span><span class="sxs-lookup"><span data-stu-id="3b9ff-141">The second command uses the *InputObject* parameter of the **Debug-Process** cmdlet to submit the process object in the $P variable.</span></span>

## <span data-ttu-id="3b9ff-142">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3b9ff-142">PARAMETERS</span></span>

### <span data-ttu-id="3b9ff-143">-Id</span><span class="sxs-lookup"><span data-stu-id="3b9ff-143">-Id</span></span>
<span data-ttu-id="3b9ff-144">Указывает идентификаторы процессов, которые необходимо отладить.</span><span class="sxs-lookup"><span data-stu-id="3b9ff-144">Specifies the process IDs of the processes to be debugged.</span></span>
<span data-ttu-id="3b9ff-145">Имя параметра *идентификатора* является необязательным.</span><span class="sxs-lookup"><span data-stu-id="3b9ff-145">The *Id* parameter name is optional.</span></span>

<span data-ttu-id="3b9ff-146">Чтобы найти идентификатор процесса, введите `Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="3b9ff-146">To find the process ID of a process, type `Get-Process`.</span></span>

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

### <span data-ttu-id="3b9ff-147">-InputObject</span><span class="sxs-lookup"><span data-stu-id="3b9ff-147">-InputObject</span></span>
<span data-ttu-id="3b9ff-148">Указывает объекты процессов, которые необходимо отладить.</span><span class="sxs-lookup"><span data-stu-id="3b9ff-148">Specifies the process objects that represent processes to be debugged.</span></span>
<span data-ttu-id="3b9ff-149">Введите переменную, которая содержит объекты процесса, или команду, которая получает объекты процесса, например командлет Get-Process.</span><span class="sxs-lookup"><span data-stu-id="3b9ff-149">Enter a variable that contains the process objects or a command that gets the process objects, such as the Get-Process cmdlet.</span></span>
<span data-ttu-id="3b9ff-150">Вы также можете передать объекты Process в этот командлет.</span><span class="sxs-lookup"><span data-stu-id="3b9ff-150">You can also pipe process objects to this cmdlet.</span></span>

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

### <span data-ttu-id="3b9ff-151">-Name</span><span class="sxs-lookup"><span data-stu-id="3b9ff-151">-Name</span></span>
<span data-ttu-id="3b9ff-152">Указывает имена процессов, которые необходимо отладить.</span><span class="sxs-lookup"><span data-stu-id="3b9ff-152">Specifies the names of the processes to be debugged.</span></span>
<span data-ttu-id="3b9ff-153">Если существует несколько процессов с одним и тем же именем, этот командлет присоединяет отладчик ко всем процессам с таким именем.</span><span class="sxs-lookup"><span data-stu-id="3b9ff-153">If there is more than one process with the same name, this cmdlet attaches a debugger to all processes with that name.</span></span>
<span data-ttu-id="3b9ff-154">Параметр *Name* является необязательным.</span><span class="sxs-lookup"><span data-stu-id="3b9ff-154">The *Name* parameter is optional.</span></span>

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

### <span data-ttu-id="3b9ff-155">-Confirm</span><span class="sxs-lookup"><span data-stu-id="3b9ff-155">-Confirm</span></span>
<span data-ttu-id="3b9ff-156">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="3b9ff-156">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="3b9ff-157">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="3b9ff-157">-WhatIf</span></span>
<span data-ttu-id="3b9ff-158">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="3b9ff-158">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="3b9ff-159">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="3b9ff-159">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="3b9ff-160">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="3b9ff-160">CommonParameters</span></span>
<span data-ttu-id="3b9ff-161">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3b9ff-161">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3b9ff-162">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3b9ff-162">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3b9ff-163">Входные данные</span><span class="sxs-lookup"><span data-stu-id="3b9ff-163">INPUTS</span></span>

### <span data-ttu-id="3b9ff-164">System. Int32, System. Diagnostics. Process, System. String</span><span class="sxs-lookup"><span data-stu-id="3b9ff-164">System.Int32, System.Diagnostics.Process, System.String</span></span>
<span data-ttu-id="3b9ff-165">В этот командлет можно передать по конвейеру идентификатор процесса (Int32), объект процесса (System. Diagnostics. Process) или имя процесса (строка).</span><span class="sxs-lookup"><span data-stu-id="3b9ff-165">You can pipe a process ID (Int32), a process object (System.Diagnostics.Process), or a process name (String) to this cmdlet.</span></span>

## <span data-ttu-id="3b9ff-166">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="3b9ff-166">OUTPUTS</span></span>

### <span data-ttu-id="3b9ff-167">Нет</span><span class="sxs-lookup"><span data-stu-id="3b9ff-167">None</span></span>
<span data-ttu-id="3b9ff-168">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="3b9ff-168">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="3b9ff-169">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="3b9ff-169">NOTES</span></span>

* <span data-ttu-id="3b9ff-170">Этот командлет использует метод AttachDebugger класса Win32_Process инструментария управления Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="3b9ff-170">This cmdlet uses the AttachDebugger method of the Windows Management Instrumentation (WMI) Win32_Process class.</span></span> <span data-ttu-id="3b9ff-171">Дополнительные сведения об этом методе см. в разделе [метод аттачдебугжер](https://go.microsoft.com/fwlink/?LinkId=143640) в библиотеке MSDN.</span><span class="sxs-lookup"><span data-stu-id="3b9ff-171">For more information about this method, see [AttachDebugger method](https://go.microsoft.com/fwlink/?LinkId=143640) in the MSDN library.</span></span>

## <span data-ttu-id="3b9ff-172">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="3b9ff-172">RELATED LINKS</span></span>

[<span data-ttu-id="3b9ff-173">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="3b9ff-173">Debug-Process</span></span>](Debug-Process.md)

[<span data-ttu-id="3b9ff-174">Get-Process</span><span class="sxs-lookup"><span data-stu-id="3b9ff-174">Get-Process</span></span>](Get-Process.md)

[<span data-ttu-id="3b9ff-175">Start-Process</span><span class="sxs-lookup"><span data-stu-id="3b9ff-175">Start-Process</span></span>](Start-Process.md)

[<span data-ttu-id="3b9ff-176">Stop-Process</span><span class="sxs-lookup"><span data-stu-id="3b9ff-176">Stop-Process</span></span>](Stop-Process.md)

[<span data-ttu-id="3b9ff-177">Wait-Process</span><span class="sxs-lookup"><span data-stu-id="3b9ff-177">Wait-Process</span></span>](Wait-Process.md)
