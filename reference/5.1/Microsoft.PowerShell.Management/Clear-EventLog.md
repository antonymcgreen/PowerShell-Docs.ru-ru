---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/clear-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-EventLog
ms.openlocfilehash: 695a13d4fbbf60caadeed994c1aa9c36432be917
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228446"
---
# <span data-ttu-id="cdffb-103">Clear-EventLog</span><span class="sxs-lookup"><span data-stu-id="cdffb-103">Clear-EventLog</span></span>

## <span data-ttu-id="cdffb-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="cdffb-104">SYNOPSIS</span></span>
<span data-ttu-id="cdffb-105">Удаляет все записи из указанных журналов событий на локальном или удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="cdffb-105">Clears all entries from specified event logs on the local or remote computers.</span></span>

## <span data-ttu-id="cdffb-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="cdffb-106">SYNTAX</span></span>

```
Clear-EventLog [-LogName] <String[]> [[-ComputerName] <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="cdffb-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="cdffb-107">DESCRIPTION</span></span>

<span data-ttu-id="cdffb-108">`Clear-EventLog`Командлет удаляет все записи из указанных журналов событий на локальном компьютере или на удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="cdffb-108">The `Clear-EventLog` cmdlet deletes all of the entries from the specified event logs on the local computer or on remote computers.</span></span>
<span data-ttu-id="cdffb-109">Для использования необходимо `Clear-EventLog` быть членом группы "Администраторы" на затронутом компьютере.</span><span class="sxs-lookup"><span data-stu-id="cdffb-109">To use `Clear-EventLog`, you must be a member of the Administrators group on the affected computer.</span></span>

<span data-ttu-id="cdffb-110">Командлеты, содержащие существительное в **EventLog** (командлеты EventLog), работают только в классических журналах событий.</span><span class="sxs-lookup"><span data-stu-id="cdffb-110">The cmdlets that contain the **EventLog** noun (the EventLog cmdlets) work only on classic event logs.</span></span>
<span data-ttu-id="cdffb-111">Для получения событий из журналов, использующих технологию журнала событий Windows в Windows Vista и более поздних версиях Windows, используйте командлет Get-WinEvent.</span><span class="sxs-lookup"><span data-stu-id="cdffb-111">To get events from logs that use the Windows Event Log technology in Windows Vista and later versions of Windows, use the Get-WinEvent cmdlet.</span></span>

## <span data-ttu-id="cdffb-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="cdffb-112">EXAMPLES</span></span>

### <span data-ttu-id="cdffb-113">Пример 1. Удаление конкретных типов журналов событий с локального компьютера</span><span class="sxs-lookup"><span data-stu-id="cdffb-113">Example 1: Clear specific event log types from the local computer</span></span>

```powershell
Clear-EventLog "Windows PowerShell"
```

<span data-ttu-id="cdffb-114">Эта команда удаляет записи из журнала событий Windows PowerShell на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="cdffb-114">This command clears the entries from the Windows PowerShell event log on the local computer.</span></span>

### <span data-ttu-id="cdffb-115">Пример 2. Удаление конкретных нескольких типов журналов с локального и удаленных компьютеров</span><span class="sxs-lookup"><span data-stu-id="cdffb-115">Example 2: Clear specific multiple log types from the local and remote computers</span></span>

```powershell
Clear-EventLog -LogName ODiag, OSession -ComputerName localhost, Server02
```

<span data-ttu-id="cdffb-116">Эта команда удаляет все записи журналов Microsoft Office Diagnostics (Одиаг) и Microsoft Office Sessions (Осессион) на локальном компьютере и Server02 удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="cdffb-116">This command clears all of the entries in the Microsoft Office Diagnostics (ODiag) and Microsoft Office Sessions (OSession) logs on the local computer and the Server02 remote computer.</span></span>

### <span data-ttu-id="cdffb-117">Пример 3. Очистка всех журналов на указанных компьютерах, а затем отображение списка журналов событий</span><span class="sxs-lookup"><span data-stu-id="cdffb-117">Example 3: Clear all logs on the specified computers then display the event log list</span></span>

```powershell
Clear-EventLog -LogName application, system -confirm
```

<span data-ttu-id="cdffb-118">Эта команда запрашивает подтверждение перед удалением записей из указанных журналов событий.</span><span class="sxs-lookup"><span data-stu-id="cdffb-118">This command prompts you for confirmation before deleting the entries in the specified event logs.</span></span>

### <span data-ttu-id="cdffb-119">Пример 4. Очистка всех журналов на указанных компьютерах, а затем отображение списка журналов событий</span><span class="sxs-lookup"><span data-stu-id="cdffb-119">Example 4: Clear all logs on the specified computers then display the event log list</span></span>

```powershell
function clear-all-event-logs ($computerName="localhost")
{
   $logs = Get-EventLog -ComputerName $computername -List | ForEach-Object {$_.Log}
   $logs | ForEach-Object {Clear-EventLog -ComputerName $computername -LogName $_ }
   Get-EventLog -ComputerName $computername -list
}

clear-all-event-logs -ComputerName Server01
```

```Output
Max(K) Retain OverflowAction        Entries Log
------ ------ --------------        ------- ---
15,168      0 OverwriteAsNeeded           0 Application
15,168      0 OverwriteAsNeeded           0 DFS Replication
512         7 OverwriteOlder              0 DxStudio
20,480      0 OverwriteAsNeeded           0 Hardware Events
512         7 OverwriteOlder              0 Internet Explorer
20,480      0 OverwriteAsNeeded           0 Key Management Service
16,384      0 OverwriteAsNeeded           0 Microsoft Office Diagnostics
16,384      0 OverwriteAsNeeded           0 Microsoft Office Sessions
30,016      0 OverwriteAsNeeded           1 Security
15,168      0 OverwriteAsNeeded           2 System
15,360      0 OverwriteAsNeeded           0 Windows PowerShell
```

<span data-ttu-id="cdffb-120">Эта функция очищает все журналы событий на указанных компьютерах и отображает полученный список журналов событий.</span><span class="sxs-lookup"><span data-stu-id="cdffb-120">This function clears all event logs on the specified computers and then displays the resulting event log list.</span></span>

<span data-ttu-id="cdffb-121">Обратите внимание, что после выполнения этой команды, но перед их выводом на экран в журналы системы и безопасности добавляются несколько записей.</span><span class="sxs-lookup"><span data-stu-id="cdffb-121">Notice that a few entries were added to the System and Security logs after the logs were cleared but before they were displayed.</span></span>

## <span data-ttu-id="cdffb-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="cdffb-122">PARAMETERS</span></span>

### <span data-ttu-id="cdffb-123">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="cdffb-123">-ComputerName</span></span>

<span data-ttu-id="cdffb-124">Указывает удаленный компьютер.</span><span class="sxs-lookup"><span data-stu-id="cdffb-124">Specifies a remote computer.</span></span>
<span data-ttu-id="cdffb-125">По умолчанию это локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="cdffb-125">The default is the local computer.</span></span>

<span data-ttu-id="cdffb-126">Введите имя NetBIOS, IP-адрес или полное доменное имя удаленного компьютера.</span><span class="sxs-lookup"><span data-stu-id="cdffb-126">Type the NetBIOS name, an Internet Protocol (IP) address, or a fully qualified domain name of a remote computer.</span></span>
<span data-ttu-id="cdffb-127">Чтобы указать локальный компьютер, введите имя компьютера, "localhost" или точку (.).</span><span class="sxs-lookup"><span data-stu-id="cdffb-127">To specify the local computer, type the computer name, a dot (.), or "localhost".</span></span>

<span data-ttu-id="cdffb-128">Этот параметр не зависит от удаленного взаимодействия Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cdffb-128">This parameter does not rely on Windows PowerShell remoting.</span></span>
<span data-ttu-id="cdffb-129">Параметр **ComputerName** можно использовать, `Get-EventLog` даже если компьютер не настроен для выполнения удаленных команд.</span><span class="sxs-lookup"><span data-stu-id="cdffb-129">You can use the **ComputerName** parameter of `Get-EventLog` even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: 1
Default value: Local computer
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="cdffb-130">-LogName</span><span class="sxs-lookup"><span data-stu-id="cdffb-130">-LogName</span></span>

<span data-ttu-id="cdffb-131">Определяет журналы событий.</span><span class="sxs-lookup"><span data-stu-id="cdffb-131">Specifies the event logs.</span></span>
<span data-ttu-id="cdffb-132">Введите имена (значение свойства Log, а не LogDisplayName) одного или нескольких журналов событий, разделенные запятыми.</span><span class="sxs-lookup"><span data-stu-id="cdffb-132">Enter the log name (the value of the Log property; not the LogDisplayName) of one or more event logs, separated by commas.</span></span>
<span data-ttu-id="cdffb-133">Подстановочные знаки не допускаются.</span><span class="sxs-lookup"><span data-stu-id="cdffb-133">Wildcard characters are not permitted.</span></span>
<span data-ttu-id="cdffb-134">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="cdffb-134">This parameter is required.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: LN

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="cdffb-135">-Confirm</span><span class="sxs-lookup"><span data-stu-id="cdffb-135">-Confirm</span></span>

<span data-ttu-id="cdffb-136">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="cdffb-136">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="cdffb-137">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="cdffb-137">-WhatIf</span></span>

<span data-ttu-id="cdffb-138">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="cdffb-138">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="cdffb-139">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="cdffb-139">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="cdffb-140">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="cdffb-140">CommonParameters</span></span>

<span data-ttu-id="cdffb-141">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="cdffb-141">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="cdffb-142">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="cdffb-142">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="cdffb-143">Входные данные</span><span class="sxs-lookup"><span data-stu-id="cdffb-143">INPUTS</span></span>

### <span data-ttu-id="cdffb-144">Нет</span><span class="sxs-lookup"><span data-stu-id="cdffb-144">None</span></span>

<span data-ttu-id="cdffb-145">Вы не можете передать объекты в `Clear-EventLog` .</span><span class="sxs-lookup"><span data-stu-id="cdffb-145">You cannot pipe objects to `Clear-EventLog`.</span></span>

## <span data-ttu-id="cdffb-146">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="cdffb-146">OUTPUTS</span></span>

### <span data-ttu-id="cdffb-147">Нет</span><span class="sxs-lookup"><span data-stu-id="cdffb-147">None</span></span>

<span data-ttu-id="cdffb-148">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="cdffb-148">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="cdffb-149">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="cdffb-149">NOTES</span></span>

- <span data-ttu-id="cdffb-150">Для использования `Clear-EventLog` в Windows Vista и более поздних версиях Windows запустите Windows PowerShell с параметром "Запуск от имени администратора".</span><span class="sxs-lookup"><span data-stu-id="cdffb-150">To use `Clear-EventLog` on Windows Vista and later versions of Windows, start Windows PowerShell with the "Run as administrator" option.</span></span>

## <span data-ttu-id="cdffb-151">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="cdffb-151">RELATED LINKS</span></span>

[<span data-ttu-id="cdffb-152">Get-EventLog</span><span class="sxs-lookup"><span data-stu-id="cdffb-152">Get-EventLog</span></span>](Get-EventLog.md)

[<span data-ttu-id="cdffb-153">Limit-EventLog</span><span class="sxs-lookup"><span data-stu-id="cdffb-153">Limit-EventLog</span></span>](Limit-EventLog.md)

[<span data-ttu-id="cdffb-154">New-EventLog</span><span class="sxs-lookup"><span data-stu-id="cdffb-154">New-EventLog</span></span>](New-EventLog.md)

[<span data-ttu-id="cdffb-155">Remove-EventLog</span><span class="sxs-lookup"><span data-stu-id="cdffb-155">Remove-EventLog</span></span>](Remove-EventLog.md)

[<span data-ttu-id="cdffb-156">Show-EventLog</span><span class="sxs-lookup"><span data-stu-id="cdffb-156">Show-EventLog</span></span>](Show-EventLog.md)

[<span data-ttu-id="cdffb-157">Write-EventLog</span><span class="sxs-lookup"><span data-stu-id="cdffb-157">Write-EventLog</span></span>](Write-EventLog.md)
