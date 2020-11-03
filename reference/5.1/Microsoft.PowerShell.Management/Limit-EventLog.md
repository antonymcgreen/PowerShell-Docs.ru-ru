---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/limit-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Limit-EventLog
ms.openlocfilehash: 3ec3214103dc6151e148f7482b0be8b821871e3c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227997"
---
# <span data-ttu-id="ef489-103">Limit-EventLog</span><span class="sxs-lookup"><span data-stu-id="ef489-103">Limit-EventLog</span></span>

## <span data-ttu-id="ef489-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="ef489-104">SYNOPSIS</span></span>
<span data-ttu-id="ef489-105">Задает свойства журнала событий, которые ограничивают его размер и возраст записей.</span><span class="sxs-lookup"><span data-stu-id="ef489-105">Sets the event log properties that limit the size of the event log and the age of its entries.</span></span>

## <span data-ttu-id="ef489-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ef489-106">SYNTAX</span></span>

```
Limit-EventLog [-LogName] <String[]> [-ComputerName <String[]>] [-RetentionDays <Int32>]
 [-OverflowAction <OverflowAction>] [-MaximumSize <Int64>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="ef489-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ef489-107">DESCRIPTION</span></span>
<span data-ttu-id="ef489-108">Командлет **Limit-EventLog** задает максимальный размер классического журнала событий, время хранения каждого события и то, что происходит при достижении максимального размера журнала.</span><span class="sxs-lookup"><span data-stu-id="ef489-108">The **Limit-EventLog** cmdlet sets the maximum size of a classic event log, how long each event must be retained, and what happens when the log reaches its maximum size.</span></span>
<span data-ttu-id="ef489-109">Его можно использовать для настройки ограничений журналов событий на локальном и удаленном компьютерах.</span><span class="sxs-lookup"><span data-stu-id="ef489-109">You can use it to limit the event logs on local or remote computers.</span></span>

<span data-ttu-id="ef489-110">Командлеты, которые содержат существительное EventLog, работают только с классическими журналами событий.</span><span class="sxs-lookup"><span data-stu-id="ef489-110">The cmdlets that contain the EventLog noun (the EventLog cmdlets) work only on classic event logs.</span></span>
<span data-ttu-id="ef489-111">Чтобы получить события из журналов, использующих технологию журнала событий Windows, в Windows Vista и более поздних версиях Windows, используйте Get-WinEvent.</span><span class="sxs-lookup"><span data-stu-id="ef489-111">To get events from logs that use the Windows Event Log technology in Windows Vista and later versions of Windows, use Get-WinEvent.</span></span>

## <span data-ttu-id="ef489-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="ef489-112">EXAMPLES</span></span>

### <span data-ttu-id="ef489-113">Пример 1. увеличение размера журнала событий</span><span class="sxs-lookup"><span data-stu-id="ef489-113">Example 1: Increase the size of an event log</span></span>

```
PS C:\> Limit-EventLog -LogName "Windows PowerShell" -MaximumSize 20KB
```

<span data-ttu-id="ef489-114">Эта команда увеличивает максимальный размер журнала событий Windows PowerShell на локальном компьютере до 20 480 байт (20 КБ).</span><span class="sxs-lookup"><span data-stu-id="ef489-114">This command increases the maximum size of the Windows PowerShell event log on the local computer to 20480 bytes (20 KB).</span></span>

### <span data-ttu-id="ef489-115">Пример 2. хранить журнал событий в течение указанного времени</span><span class="sxs-lookup"><span data-stu-id="ef489-115">Example 2: Retain an event log for a specified duration</span></span>

```
PS C:\> Limit-EventLog -LogName Security -ComputerName "Server01", "Server02" -RetentionDays 7
```

<span data-ttu-id="ef489-116">Эта команда обеспечивает хранение событий в журнале Security на компьютерах Server01 и Server02 не менее 7 дней.</span><span class="sxs-lookup"><span data-stu-id="ef489-116">This command ensures that events in the Security log on the Server01 and Server02 computers are retained for at least 7 days.</span></span>

### <span data-ttu-id="ef489-117">Пример 3. изменение действия переполнения для всех журналов событий</span><span class="sxs-lookup"><span data-stu-id="ef489-117">Example 3: Change the overflow action of all event logs</span></span>

```
PS C:\> $Logs = Get-EventLog -List | ForEach {$_.log}
PS C:\> Limit-EventLog -OverflowAction OverwriteOlder -LogName $Logs
PS C:\> Get-EventLog -List

Max(K) Retain OverflowAction     Entries  Log
------ ------ --------------     -------  ---
15,168      0 OverwriteOlder       3,412  Application
512         0 OverwriteOlder           0  DFS Replication
512         0 OverwriteOlder          17  DxStudio
10,240      7 OverwriteOlder           0  HardwareEvents
512         0 OverwriteOlder           0  Internet Explorer
512         0 OverwriteOlder           0  Key Management Service
16,384      0 OverwriteOlder           4  ODiag
16,384      0 OverwriteOlder         389  OSession Security
15,168      0 OverwriteOlder      19,360  System
15,360      0 OverwriteOlder      15,828  Windows PowerShell
```

<span data-ttu-id="ef489-118">В этом примере изменяется действие переполнения всех журналов событий на локальном компьютере до Овервритеолдер.</span><span class="sxs-lookup"><span data-stu-id="ef489-118">This example changes the overflow action of all event logs on the local computer to OverwriteOlder.</span></span>

<span data-ttu-id="ef489-119">Первая команда возвращает имена всех журналов на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ef489-119">The first command gets the log names of all of the logs on the local computer.</span></span>
<span data-ttu-id="ef489-120">Вторая команда задает действие, выполняемое при переполнении.</span><span class="sxs-lookup"><span data-stu-id="ef489-120">The second command sets the overflow action.</span></span>
<span data-ttu-id="ef489-121">Третья команда отображает результаты.</span><span class="sxs-lookup"><span data-stu-id="ef489-121">The third command displays the results.</span></span>

## <span data-ttu-id="ef489-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ef489-122">PARAMETERS</span></span>

### <span data-ttu-id="ef489-123">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="ef489-123">-ComputerName</span></span>
<span data-ttu-id="ef489-124">Указывает удаленные компьютеры.</span><span class="sxs-lookup"><span data-stu-id="ef489-124">Specifies remote computers.</span></span>
<span data-ttu-id="ef489-125">По умолчанию это локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="ef489-125">The default is the local computer.</span></span>

<span data-ttu-id="ef489-126">Введите имя NetBIOS, IP-адрес или полное доменное имя (FQDN) удаленного компьютера.</span><span class="sxs-lookup"><span data-stu-id="ef489-126">Type the NetBIOS name, an Internet Protocol (IP) address, or a fully qualified domain name (FQDN) of a remote computer.</span></span>
<span data-ttu-id="ef489-127">Чтобы указать локальный компьютер, введите имя компьютера, localhost или точку (.).</span><span class="sxs-lookup"><span data-stu-id="ef489-127">To specify the local computer, type the computer name, a dot (.), or localhost.</span></span>

<span data-ttu-id="ef489-128">Этот параметр не зависит от удаленного взаимодействия Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ef489-128">This parameter does not rely on Windows PowerShell remoting.</span></span>
<span data-ttu-id="ef489-129">Параметр *ComputerName* параметра **Limit-EventLog** можно использовать, даже если компьютер не настроен для выполнения удаленных команд.</span><span class="sxs-lookup"><span data-stu-id="ef489-129">You can use the *ComputerName* parameter of **Limit-EventLog** even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ef489-130">-LogName</span><span class="sxs-lookup"><span data-stu-id="ef489-130">-LogName</span></span>
<span data-ttu-id="ef489-131">Определяет журналы событий.</span><span class="sxs-lookup"><span data-stu-id="ef489-131">Specifies the event logs.</span></span>
<span data-ttu-id="ef489-132">Введите имена (значение свойства Log, а не LogDisplayName) одного или нескольких журналов событий, разделенные запятыми.</span><span class="sxs-lookup"><span data-stu-id="ef489-132">Enter the log name (the value of the Log property; not the LogDisplayName) of one or more event logs, separated by commas.</span></span>
<span data-ttu-id="ef489-133">Подстановочные знаки не допускаются.</span><span class="sxs-lookup"><span data-stu-id="ef489-133">Wildcard characters are not permitted.</span></span>
<span data-ttu-id="ef489-134">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="ef489-134">This parameter is required.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: LN

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ef489-135">-MaximumSize</span><span class="sxs-lookup"><span data-stu-id="ef489-135">-MaximumSize</span></span>
<span data-ttu-id="ef489-136">Задает максимальный размер журналов событий в байтах.</span><span class="sxs-lookup"><span data-stu-id="ef489-136">Specifies the maximum size of the event logs in bytes.</span></span>
<span data-ttu-id="ef489-137">Введите значение от 64 килобайт (КБ) до 4 гигабайт (ГБ).</span><span class="sxs-lookup"><span data-stu-id="ef489-137">Enter a value between 64 kilobytes (KB) and 4 gigabytes (GB).</span></span>
<span data-ttu-id="ef489-138">Значение должно быть кратным 64 КБ (65 536).</span><span class="sxs-lookup"><span data-stu-id="ef489-138">The value must be divisible by 64 KB (65536).</span></span>

<span data-ttu-id="ef489-139">Этот параметр задает значение свойства **максимумкилобитес** объекта **System. Diagnostics. EventLog** , представляющего классическую запись журнала событий.</span><span class="sxs-lookup"><span data-stu-id="ef489-139">This parameter specifies the value of the **MaximumKilobytes** property of the **System.Diagnostics.EventLog** object that represents a classic event log.</span></span>

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ef489-140">-Оверфловактион</span><span class="sxs-lookup"><span data-stu-id="ef489-140">-OverflowAction</span></span>
<span data-ttu-id="ef489-141">Задает действие, выполняемое при достижении максимального размера журнала событий.</span><span class="sxs-lookup"><span data-stu-id="ef489-141">Specifies what happens when the event log reaches its maximum size.</span></span>

<span data-ttu-id="ef489-142">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="ef489-142">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="ef489-143">Донотоверврите: существующие записи сохраняются, а новые записи отбрасываются.</span><span class="sxs-lookup"><span data-stu-id="ef489-143">DoNotOverwrite:  Existing entries are retained and new entries are discarded.</span></span>
- <span data-ttu-id="ef489-144">Овервритеаснидед: каждая новая запись перезаписывает самую старую запись.</span><span class="sxs-lookup"><span data-stu-id="ef489-144">OverwriteAsNeeded:  Each new entry overwrites the oldest entry.</span></span>
- <span data-ttu-id="ef489-145">Овервритеолдер: новые события перезаписывают события старше значения, заданного свойством **MinimumRetentionDays** .</span><span class="sxs-lookup"><span data-stu-id="ef489-145">OverwriteOlder:  New events overwrite events older than the value specified by the **MinimumRetentionDays** property.</span></span> <span data-ttu-id="ef489-146">Если события старше, чем указано значением свойства **MinimumRetentionDays** , новые события отбрасываются.</span><span class="sxs-lookup"><span data-stu-id="ef489-146">If there are no events older than specified by the **MinimumRetentionDays** property value, new events are discarded.</span></span>

<span data-ttu-id="ef489-147">Этот параметр задает значение свойства **оверфловактион** объекта **System. Diagnostics. EventLog** , представляющего классическую запись журнала событий.</span><span class="sxs-lookup"><span data-stu-id="ef489-147">This parameter specifies the value of the **OverflowAction** property of the **System.Diagnostics.EventLog** object that represents a classic event log.</span></span>

```yaml
Type: System.Diagnostics.OverflowAction
Parameter Sets: (All)
Aliases: OFA
Accepted values: OverwriteOlder, OverwriteAsNeeded, DoNotOverwrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ef489-148">-Ретентиондайс</span><span class="sxs-lookup"><span data-stu-id="ef489-148">-RetentionDays</span></span>
<span data-ttu-id="ef489-149">Задает минимальный срок хранения события в журнале событий (в днях).</span><span class="sxs-lookup"><span data-stu-id="ef489-149">Specifies the minimum number of days that an event must remain in the event log.</span></span>

<span data-ttu-id="ef489-150">Этот параметр задает значение свойства **MinimumRetentionDays** объекта **System. Diagnostics. EventLog** , представляющего классическую запись журнала событий.</span><span class="sxs-lookup"><span data-stu-id="ef489-150">This parameter specifies the value of the **MinimumRetentionDays** property of the **System.Diagnostics.EventLog** object that represents a classic event log.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: MRD

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ef489-151">-Confirm</span><span class="sxs-lookup"><span data-stu-id="ef489-151">-Confirm</span></span>
<span data-ttu-id="ef489-152">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="ef489-152">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="ef489-153">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="ef489-153">-WhatIf</span></span>
<span data-ttu-id="ef489-154">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="ef489-154">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="ef489-155">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="ef489-155">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="ef489-156">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="ef489-156">CommonParameters</span></span>
<span data-ttu-id="ef489-157">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ef489-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ef489-158">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ef489-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ef489-159">Входные данные</span><span class="sxs-lookup"><span data-stu-id="ef489-159">INPUTS</span></span>

### <span data-ttu-id="ef489-160">Нет</span><span class="sxs-lookup"><span data-stu-id="ef489-160">None</span></span>
<span data-ttu-id="ef489-161">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="ef489-161">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="ef489-162">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="ef489-162">OUTPUTS</span></span>

### <span data-ttu-id="ef489-163">Нет</span><span class="sxs-lookup"><span data-stu-id="ef489-163">None</span></span>
<span data-ttu-id="ef489-164">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="ef489-164">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="ef489-165">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="ef489-165">NOTES</span></span>

* <span data-ttu-id="ef489-166">Чтобы использовать этот командлет в Windows Vista и более поздних версиях Windows, откройте Windows PowerShell с параметром Запуск от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="ef489-166">To use this cmdlet on Windows Vista and later versions of Windows, open Windows PowerShell with the Run as administrator option.</span></span>

  <span data-ttu-id="ef489-167">Этот командлет изменяет свойства объекта **System. Diagnostics. EventLog** , который представляет Классический журнал событий.</span><span class="sxs-lookup"><span data-stu-id="ef489-167">This cmdlet changes the properties of the **System.Diagnostics.EventLog** object that represents a classic event log.</span></span>
<span data-ttu-id="ef489-168">Чтобы просмотреть текущие параметры свойств журнала событий, введите `Get-EventLog -List` .</span><span class="sxs-lookup"><span data-stu-id="ef489-168">To see the current settings of the event log properties, type `Get-EventLog -List`.</span></span>

*

## <span data-ttu-id="ef489-169">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="ef489-169">RELATED LINKS</span></span>

[<span data-ttu-id="ef489-170">Clear-EventLog</span><span class="sxs-lookup"><span data-stu-id="ef489-170">Clear-EventLog</span></span>](Clear-EventLog.md)

[<span data-ttu-id="ef489-171">Get-EventLog</span><span class="sxs-lookup"><span data-stu-id="ef489-171">Get-EventLog</span></span>](Get-EventLog.md)

[<span data-ttu-id="ef489-172">Limit-EventLog</span><span class="sxs-lookup"><span data-stu-id="ef489-172">Limit-EventLog</span></span>](Limit-EventLog.md)

[<span data-ttu-id="ef489-173">New-EventLog</span><span class="sxs-lookup"><span data-stu-id="ef489-173">New-EventLog</span></span>](New-EventLog.md)

[<span data-ttu-id="ef489-174">Remove-EventLog</span><span class="sxs-lookup"><span data-stu-id="ef489-174">Remove-EventLog</span></span>](Remove-EventLog.md)

[<span data-ttu-id="ef489-175">Show-EventLog</span><span class="sxs-lookup"><span data-stu-id="ef489-175">Show-EventLog</span></span>](Show-EventLog.md)

[<span data-ttu-id="ef489-176">Write-EventLog</span><span class="sxs-lookup"><span data-stu-id="ef489-176">Write-EventLog</span></span>](Write-EventLog.md)
