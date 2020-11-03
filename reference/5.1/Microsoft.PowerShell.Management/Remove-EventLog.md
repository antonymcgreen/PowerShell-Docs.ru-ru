---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-EventLog
ms.openlocfilehash: 4cf29146727c9a54715459a2d56e47a27c5bacc0
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227942"
---
# <span data-ttu-id="12270-103">Remove-EventLog</span><span class="sxs-lookup"><span data-stu-id="12270-103">Remove-EventLog</span></span>

## <span data-ttu-id="12270-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="12270-104">SYNOPSIS</span></span>
<span data-ttu-id="12270-105">Удаляет журнал событий или отменяет регистрацию источника событий.</span><span class="sxs-lookup"><span data-stu-id="12270-105">Deletes an event log or unregisters an event source.</span></span>

## <span data-ttu-id="12270-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="12270-106">SYNTAX</span></span>

### <span data-ttu-id="12270-107">Default (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="12270-107">Default (Default)</span></span>

```
Remove-EventLog [[-ComputerName] <String[]>] [-LogName] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="12270-108">Источник</span><span class="sxs-lookup"><span data-stu-id="12270-108">Source</span></span>

```
Remove-EventLog [[-ComputerName] <String[]>] [-Source <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="12270-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="12270-109">DESCRIPTION</span></span>
<span data-ttu-id="12270-110">Командлет **Remove-EventLog** удаляет файл журнала событий с локального или удаленного компьютера и отменяет регистрацию всех источников событий для журнала.</span><span class="sxs-lookup"><span data-stu-id="12270-110">The **Remove-EventLog** cmdlet deletes an event log file from a local or remote computer and unregisters all its event sources for the log.</span></span>
<span data-ttu-id="12270-111">Кроме того, этот командлет можно использовать для отмены регистрации источников событий без удаления каких-либо журналов событий.</span><span class="sxs-lookup"><span data-stu-id="12270-111">You can also use this cmdlet to unregister event sources without deleting any event logs.</span></span>

<span data-ttu-id="12270-112">Командлеты, содержащие существительное в **EventLog** , командлеты **EventLog** , работают только с классическими журналами событий.</span><span class="sxs-lookup"><span data-stu-id="12270-112">The cmdlets that contain the **EventLog** noun, the **EventLog** cmdlets, work only on classic event logs.</span></span>
<span data-ttu-id="12270-113">Для получения событий из журналов, использующих технологию журнала событий Windows в Windows Vista и более поздних версиях операционной системы Windows, используйте Get-WinEvent.</span><span class="sxs-lookup"><span data-stu-id="12270-113">To get events from logs that use the Windows Event Log technology in Windows Vista and later versions of the Windows operating system, use Get-WinEvent.</span></span>

<span data-ttu-id="12270-114">ВНИМАНИЕ! этот командлет может удалять журналы событий операционной системы, что может привести к сбоям приложения и непредвиденному поведению системы.</span><span class="sxs-lookup"><span data-stu-id="12270-114">CAUTION: This cmdlet can delete operating system event logs, which might cause application failures and unexpected system behavior.</span></span>

## <span data-ttu-id="12270-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="12270-115">EXAMPLES</span></span>

### <span data-ttu-id="12270-116">Пример 1. Удаление журнала событий с локального компьютера</span><span class="sxs-lookup"><span data-stu-id="12270-116">Example 1: Remove an event log from the local computer</span></span>

```
PS C:\> Remove-EventLog -LogName "MyLog"
```

<span data-ttu-id="12270-117">Эта команда удаляет журнал событий MyLog с локального компьютера и отменяет регистрацию источников событий для этого журнала.</span><span class="sxs-lookup"><span data-stu-id="12270-117">This command deletes the MyLog event log from the local computer and unregisters its event sources.</span></span>

### <span data-ttu-id="12270-118">Пример 2. Удаление журнала событий с нескольких компьютеров</span><span class="sxs-lookup"><span data-stu-id="12270-118">Example 2: Remove an event log from several computers</span></span>

```
PS C:\> Remove-EventLog -LogName "MyLog", "TestLog" -ComputerName "Server01", "Server02", "localhost"
```

<span data-ttu-id="12270-119">Эта команда удаляет журналы событий Милог и TestLog с локального компьютера, а также с удаленных компьютеров Server01 и Server02.</span><span class="sxs-lookup"><span data-stu-id="12270-119">This command deletes the MyLog and TestLog event logs from the local computer and the Server01 and Server02 remote computers.</span></span>
<span data-ttu-id="12270-120">и отменяет регистрацию источников событий для этих журналов.</span><span class="sxs-lookup"><span data-stu-id="12270-120">The command also unregisters the event sources for these logs.</span></span>

### <span data-ttu-id="12270-121">Пример 3. Удаление источника события</span><span class="sxs-lookup"><span data-stu-id="12270-121">Example 3: Delete an event source</span></span>

```
PS C:\> Remove-EventLog -Source "MyApp"
```

<span data-ttu-id="12270-122">Эта команда удаляет источник событий MyApp из журналов на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="12270-122">This command deletes the MyApp event source from the logs on the local computer.</span></span>
<span data-ttu-id="12270-123">По завершении выполнения команды программа MyApp не сможет выполнить запись в какие бы то ни было журналы событий.</span><span class="sxs-lookup"><span data-stu-id="12270-123">When the command finishes, the MyApp program cannot write to any event logs.</span></span>

### <span data-ttu-id="12270-124">Пример 4. Удаление журнала событий и подтверждение действия</span><span class="sxs-lookup"><span data-stu-id="12270-124">Example 4: Remove an event log and confirm the action</span></span>

```
The first command lists the event logs on the local computer.
PS C:\> Get-EventLog -List
Max(K) Retain OverflowAction        Entries Log
------ ------ --------------        ------- ---
15,168      0 OverwriteAsNeeded      22,923 Application
15,168      0 OverwriteAsNeeded          53 DFS Replication
15,168      7 OverwriteOlder              0 Hardware Events
512      7 OverwriteOlder              0 Internet Explorer
20,480      0 OverwriteAsNeeded           0 Key Management Service
30,016      0 OverwriteAsNeeded      50,060 Security
15,168      0 OverwriteAsNeeded      27,592 System
15,360      0 OverwriteAsNeeded      18,355 Windows PowerShell
15,168      7 OverwriteAsNeeded          12 ZapLog

The second command deletes the ZapLog event log.
PS C:\> Remove-EventLog -LogName "ZapLog"

The third command lists the event logs again. The ZapLog event log no longer appears in the list.
PS C:\> Get-EventLog -List
Max(K) Retain OverflowAction        Entries Log
------ ------ --------------        ------- ---
15,168      0 OverwriteAsNeeded      22,923 Application
15,168      0 OverwriteAsNeeded          53 DFS Replication
15,168      7 OverwriteOlder              0 Hardware Events
512      7 OverwriteOlder              0 Internet Explorer
20,480      0 OverwriteAsNeeded           0 Key Management Service
30,016      0 OverwriteAsNeeded      50,060 Security
15,168      0 OverwriteAsNeeded      27,592 System
15,360      0 OverwriteAsNeeded      18,355 Windows PowerShell
```

<span data-ttu-id="12270-125">Эти команды показывают, как получить список журналов событий на компьютере и убедиться, что команда **Remove-EventLog** выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="12270-125">These commands show how to list the event logs on a computer and verify that a **Remove-EventLog** command was successful.</span></span>

### <span data-ttu-id="12270-126">Пример 5. Удаление источника события и подтверждение действия</span><span class="sxs-lookup"><span data-stu-id="12270-126">Example 5: Remove an event source and confirm the action</span></span>

```
PS C:\> Get-WmiObject win32_nteventlogfile -Filter "logfilename='TestLog'" | foreach {$_.sources}
MyApp
TestApp
PS C:\> Remove-Eventlog -Source "MyApp"
PS C:\> Get-WmiObject win32_nteventlogfile -Filter "logfilename='TestLog'"} | foreach {$_.sources}
TestApp
```

<span data-ttu-id="12270-127">С помощью командлета Get-WmiObject эти команды выводят список источников событий на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="12270-127">These commands use the Get-WmiObject cmdlet to list the event sources on the local computer.</span></span>
<span data-ttu-id="12270-128">Эти команды можно использовать для проверки выполнения команды или удаления источника событий.</span><span class="sxs-lookup"><span data-stu-id="12270-128">You can these commands to verify the success of a command or to delete an event source.</span></span>

<span data-ttu-id="12270-129">Первая команда выдает источники событий TestLog журнала событий на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="12270-129">The first command gets the event sources of the TestLog event log on the local computer.</span></span>
<span data-ttu-id="12270-130">Одним из источников является MyApp.</span><span class="sxs-lookup"><span data-stu-id="12270-130">MyApp is one of the sources.</span></span>

<span data-ttu-id="12270-131">Вторая команда использует параметр *Source* командлета **Remove-EventLog** для удаления источника событий MyApp.</span><span class="sxs-lookup"><span data-stu-id="12270-131">The second command uses the *Source* parameter of **Remove-EventLog** to delete the MyApp event source.</span></span>

<span data-ttu-id="12270-132">Третья команда идентична первой.</span><span class="sxs-lookup"><span data-stu-id="12270-132">The third command is identical to the first.</span></span>
<span data-ttu-id="12270-133">Она показывает, что источник событий MyApp удален.</span><span class="sxs-lookup"><span data-stu-id="12270-133">It shows that the MyApp event source was deleted.</span></span>

## <span data-ttu-id="12270-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="12270-134">PARAMETERS</span></span>

### <span data-ttu-id="12270-135">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="12270-135">-ComputerName</span></span>
<span data-ttu-id="12270-136">Указывает удаленный компьютер.</span><span class="sxs-lookup"><span data-stu-id="12270-136">Specifies a remote computer.</span></span>
<span data-ttu-id="12270-137">По умолчанию это локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="12270-137">The default is the local computer.</span></span>

<span data-ttu-id="12270-138">Введите имя NetBIOS, IP-адрес или полное доменное имя удаленного компьютера.</span><span class="sxs-lookup"><span data-stu-id="12270-138">Type the NetBIOS name, an IP address, or a fully qualified domain name of a remote computer.</span></span>
<span data-ttu-id="12270-139">Чтобы указать локальный компьютер, введите имя компьютера, localhost или точку (.).</span><span class="sxs-lookup"><span data-stu-id="12270-139">To specify the local computer, type the computer name, a dot (.), or localhost.</span></span>

<span data-ttu-id="12270-140">Этот параметр не зависит от удаленного взаимодействия Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="12270-140">This parameter does not rely on Windows PowerShell remoting.</span></span>
<span data-ttu-id="12270-141">Параметр *ComputerName* командлета **Remove-EventLog** можно использовать, даже если компьютер не настроен для выполнения удаленных команд.</span><span class="sxs-lookup"><span data-stu-id="12270-141">You can use the *ComputerName* parameter of **Remove-EventLog** even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="12270-142">-LogName</span><span class="sxs-lookup"><span data-stu-id="12270-142">-LogName</span></span>
<span data-ttu-id="12270-143">Определяет журналы событий.</span><span class="sxs-lookup"><span data-stu-id="12270-143">Specifies the event logs.</span></span>
<span data-ttu-id="12270-144">Введите имя журнала одного или нескольких журналов событий, разделенных запятыми.</span><span class="sxs-lookup"><span data-stu-id="12270-144">Enter the log name of one or more event logs, separated by commas.</span></span>
<span data-ttu-id="12270-145">Имя журнала — это значение свойства **log** , а не *LogDisplayName* , а подстановочные знаки не допускаются.</span><span class="sxs-lookup"><span data-stu-id="12270-145">The log name is the value of the **Log** property, not the *LogDisplayName* , Wildcard characters are not permitted.</span></span>
<span data-ttu-id="12270-146">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="12270-146">This parameter is required.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases: LN

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="12270-147">-Source</span><span class="sxs-lookup"><span data-stu-id="12270-147">-Source</span></span>
<span data-ttu-id="12270-148">Указывает источники событий, для которых этот командлет отменяет регистрацию.</span><span class="sxs-lookup"><span data-stu-id="12270-148">Specifies the event sources that this cmdlet unregisters.</span></span>
<span data-ttu-id="12270-149">Введите имена источников, а не имя исполняемого файла, разделенные запятыми.</span><span class="sxs-lookup"><span data-stu-id="12270-149">Enter the source names, not the executable name, separated by commas.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Source
Aliases: SRC

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="12270-150">-Confirm</span><span class="sxs-lookup"><span data-stu-id="12270-150">-Confirm</span></span>
<span data-ttu-id="12270-151">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="12270-151">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="12270-152">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="12270-152">-WhatIf</span></span>
<span data-ttu-id="12270-153">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="12270-153">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="12270-154">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="12270-154">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="12270-155">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="12270-155">CommonParameters</span></span>
<span data-ttu-id="12270-156">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="12270-156">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="12270-157">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="12270-157">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="12270-158">Входные данные</span><span class="sxs-lookup"><span data-stu-id="12270-158">INPUTS</span></span>

### <span data-ttu-id="12270-159">Нет</span><span class="sxs-lookup"><span data-stu-id="12270-159">None</span></span>
<span data-ttu-id="12270-160">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="12270-160">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="12270-161">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="12270-161">OUTPUTS</span></span>

### <span data-ttu-id="12270-162">Нет</span><span class="sxs-lookup"><span data-stu-id="12270-162">None</span></span>
<span data-ttu-id="12270-163">Этот командлет не возвращает никакие выходные данные.</span><span class="sxs-lookup"><span data-stu-id="12270-163">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="12270-164">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="12270-164">NOTES</span></span>

* <span data-ttu-id="12270-165">Чтобы использовать **Remove-EventLog** в Windows Vista и более поздних версиях операционной системы Windows, запустите Windows PowerShell с помощью команды Запуск от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="12270-165">To use **Remove-EventLog** on Windows Vista and later versions of the Windows operating system, start Windows PowerShell by using the Run as administrator option.</span></span>

  <span data-ttu-id="12270-166">Если удалить журнал событий, а затем создать его заново, регистрация источников событий, которые использовались с прежним журналом, будет невозможна.</span><span class="sxs-lookup"><span data-stu-id="12270-166">If you remove an event log and then re-create the log, you will not be able to register the same event sources.</span></span>
<span data-ttu-id="12270-167">Приложения, которые использовали источники событий для внесения записей в исходный журнал, не будут записывать данные в новый журнал.</span><span class="sxs-lookup"><span data-stu-id="12270-167">Applications that used the events sources to write entries to the original log will not be able to write to the new log.</span></span>

* <span data-ttu-id="12270-168">После отмены регистрации источника событий для одного журнала этому источнику может быть запрещена запись данных в другие журналы.</span><span class="sxs-lookup"><span data-stu-id="12270-168">When you unregister an event source for a particular log, the event source might be prevented from writing entries in other event logs.</span></span>

## <span data-ttu-id="12270-169">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="12270-169">RELATED LINKS</span></span>

[<span data-ttu-id="12270-170">Clear-EventLog</span><span class="sxs-lookup"><span data-stu-id="12270-170">Clear-EventLog</span></span>](Clear-EventLog.md)

[<span data-ttu-id="12270-171">Get-EventLog</span><span class="sxs-lookup"><span data-stu-id="12270-171">Get-EventLog</span></span>](Get-EventLog.md)

[<span data-ttu-id="12270-172">Limit-EventLog</span><span class="sxs-lookup"><span data-stu-id="12270-172">Limit-EventLog</span></span>](Limit-EventLog.md)

[<span data-ttu-id="12270-173">New-EventLog</span><span class="sxs-lookup"><span data-stu-id="12270-173">New-EventLog</span></span>](New-EventLog.md)

[<span data-ttu-id="12270-174">Remove-EventLog</span><span class="sxs-lookup"><span data-stu-id="12270-174">Remove-EventLog</span></span>](Remove-EventLog.md)

[<span data-ttu-id="12270-175">Show-EventLog</span><span class="sxs-lookup"><span data-stu-id="12270-175">Show-EventLog</span></span>](Show-EventLog.md)

[<span data-ttu-id="12270-176">Write-EventLog</span><span class="sxs-lookup"><span data-stu-id="12270-176">Write-EventLog</span></span>](Write-EventLog.md)
