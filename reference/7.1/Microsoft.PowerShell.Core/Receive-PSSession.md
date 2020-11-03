---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 12/11/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/receive-pssession?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Receive-PSSession
ms.openlocfilehash: 71a17d71cf7bfdbc6ef14d0eb6949a366cb8c233
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "93230054"
---
# <span data-ttu-id="70552-103">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="70552-103">Receive-PSSession</span></span>

## <span data-ttu-id="70552-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="70552-104">SYNOPSIS</span></span>

<span data-ttu-id="70552-105">Возвращает результаты выполнения команд в отключенных сеансах</span><span class="sxs-lookup"><span data-stu-id="70552-105">Gets results of commands in disconnected sessions</span></span>

## <span data-ttu-id="70552-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="70552-106">SYNTAX</span></span>

### <span data-ttu-id="70552-107">Сеанс (значение по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="70552-107">Session (Default)</span></span>

```
Receive-PSSession [-Session] <PSSession> [-OutTarget <OutTarget>] [-JobName <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="70552-108">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="70552-108">Id</span></span>

```
Receive-PSSession [-Id] <Int32> [-OutTarget <OutTarget>] [-JobName <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="70552-109">компутерсессионнаме</span><span class="sxs-lookup"><span data-stu-id="70552-109">ComputerSessionName</span></span>

```
Receive-PSSession [-ComputerName] <String> [-ApplicationName <String>] [-ConfigurationName <String>]
 -Name <String> [-OutTarget <OutTarget>] [-JobName <String>] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [-Port <Int32>]
 [-UseSSL] [-SessionOption <PSSessionOption>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="70552-110">компутеринстанцеид</span><span class="sxs-lookup"><span data-stu-id="70552-110">ComputerInstanceId</span></span>

```
Receive-PSSession [-ComputerName] <String> [-ApplicationName <String>] [-ConfigurationName <String>]
 -InstanceId <Guid> [-OutTarget <OutTarget>] [-JobName <String>] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [-Port <Int32>]
 [-UseSSL] [-SessionOption <PSSessionOption>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="70552-111">коннектионурисессионнаме</span><span class="sxs-lookup"><span data-stu-id="70552-111">ConnectionUriSessionName</span></span>

```
Receive-PSSession [-ConfigurationName <String>] [-ConnectionUri] <Uri> [-AllowRedirection]
 -Name <String> [-OutTarget <OutTarget>] [-JobName <String>] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [-SessionOption <PSSessionOption>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="70552-112">коннектионуриинстанцеид</span><span class="sxs-lookup"><span data-stu-id="70552-112">ConnectionUriInstanceId</span></span>

```
Receive-PSSession [-ConfigurationName <String>] [-ConnectionUri] <Uri> [-AllowRedirection]
 -InstanceId <Guid> [-OutTarget <OutTarget>] [-JobName <String>] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [-SessionOption <PSSessionOption>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="70552-113">InstanceId</span><span class="sxs-lookup"><span data-stu-id="70552-113">InstanceId</span></span>

```
Receive-PSSession -InstanceId <Guid> [-OutTarget <OutTarget>] [-JobName <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="70552-114">SessionName</span><span class="sxs-lookup"><span data-stu-id="70552-114">SessionName</span></span>

```
Receive-PSSession -Name <String> [-OutTarget <OutTarget>] [-JobName <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="70552-115">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="70552-115">DESCRIPTION</span></span>

<span data-ttu-id="70552-116">`Receive-PSSession`Командлет возвращает результаты выполнения команд в сеансах PowerShell ( **PSSession** ), которые были отключены.</span><span class="sxs-lookup"><span data-stu-id="70552-116">The `Receive-PSSession` cmdlet gets the results of commands running in PowerShell sessions ( **PSSession** ) that were disconnected.</span></span> <span data-ttu-id="70552-117">Если сеанс подключен, `Receive-PSSession` получает результаты команд, которые выполнялись в момент отключения сеанса.</span><span class="sxs-lookup"><span data-stu-id="70552-117">If the session is currently connected, `Receive-PSSession` gets the results of commands that were running when the session was disconnected.</span></span> <span data-ttu-id="70552-118">Если сеанс по-прежнему отключен, `Receive-PSSession` подключается к сеансу, возобновляет все команды, которые были приостановлены, и возвращает результаты команд, выполняемых в сеансе.</span><span class="sxs-lookup"><span data-stu-id="70552-118">If the session is still disconnected, `Receive-PSSession` connects to the session, resumes any commands that were suspended, and gets the results of commands running in the session.</span></span>

<span data-ttu-id="70552-119">Этот командлет появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="70552-119">This cmdlet was introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="70552-120">`Receive-PSSession`В дополнение к команде или вместо нее можно использовать `Connect-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="70552-120">You can use a `Receive-PSSession` in addition to or instead of a `Connect-PSSession` command.</span></span>
<span data-ttu-id="70552-121">`Receive-PSSession` может подключаться к любому отключенному или повторно подключенному сеансу, который был запущен в других сеансах или на других компьютерах.</span><span class="sxs-lookup"><span data-stu-id="70552-121">`Receive-PSSession` can connect to any disconnected or reconnected session that was started in other sessions or on other computers.</span></span>

<span data-ttu-id="70552-122">`Receive-PSSession` работает с **PSSession** , который был намеренно отключен с помощью `Disconnect-PSSession` командлета или `Invoke-Command` параметра **InDisconnectedSession** .</span><span class="sxs-lookup"><span data-stu-id="70552-122">`Receive-PSSession` works on **PSSessions** that were disconnected intentionally using the `Disconnect-PSSession` cmdlet or the `Invoke-Command` **InDisconnectedSession** parameter.</span></span> <span data-ttu-id="70552-123">Или непреднамеренное отключение сетевого прерывания.</span><span class="sxs-lookup"><span data-stu-id="70552-123">Or disconnected unintentionally by a network interruption.</span></span>

<span data-ttu-id="70552-124">При использовании `Receive-PSSession` командлета для подключения к сеансу, в котором никакие команды не выполняются или приостановлены, `Receive-PSSession` подключается к сеансу, но не возвращает выходные данные и ошибки.</span><span class="sxs-lookup"><span data-stu-id="70552-124">If you use the `Receive-PSSession` cmdlet to connect to a session in which no commands are running or suspended, `Receive-PSSession` connects to the session, but returns no output or errors.</span></span>

<span data-ttu-id="70552-125">Дополнительные сведения о функции отключенных сеансов см. в разделе [about_Remote_Disconnected_Sessions](./About/about_Remote_Disconnected_Sessions.md).</span><span class="sxs-lookup"><span data-stu-id="70552-125">For more information about the Disconnected Sessions feature, see [about_Remote_Disconnected_Sessions](./About/about_Remote_Disconnected_Sessions.md).</span></span>

<span data-ttu-id="70552-126">В некоторых примерах используется Сплаттинг для уменьшения длины строки и улучшения удобочитаемости.</span><span class="sxs-lookup"><span data-stu-id="70552-126">Some examples use splatting to reduce the line length and improve readability.</span></span> <span data-ttu-id="70552-127">Дополнительные сведения см. в разделе [about_Splatting](./About/about_Splatting.md).</span><span class="sxs-lookup"><span data-stu-id="70552-127">For more information, see [about_Splatting](./About/about_Splatting.md).</span></span>

## <span data-ttu-id="70552-128">Примеры</span><span class="sxs-lookup"><span data-stu-id="70552-128">EXAMPLES</span></span>

### <span data-ttu-id="70552-129">Пример 1. подключение к PSSession</span><span class="sxs-lookup"><span data-stu-id="70552-129">Example 1: Connect to a PSSession</span></span>

<span data-ttu-id="70552-130">Этот пример подключается к сеансу на удаленном компьютере и получает результаты выполнения команд в сеансе.</span><span class="sxs-lookup"><span data-stu-id="70552-130">This example connects to a session on a remote computer and gets the results of commands that are running in a session.</span></span>

```powershell
Receive-PSSession -ComputerName Server01 -Name ITTask
```

<span data-ttu-id="70552-131">`Receive-PSSession`Указывает удаленный компьютер с параметром **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="70552-131">The `Receive-PSSession` specifies the remote computer with the **ComputerName** parameter.</span></span> <span data-ttu-id="70552-132">Параметр **Name** определяет сеанс иттаск на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="70552-132">The **Name** parameter identifies the ITTask session on the Server01 computer.</span></span> <span data-ttu-id="70552-133">В этом примере получаются результаты команд, которые были запущены в сеансе Иттаск.</span><span class="sxs-lookup"><span data-stu-id="70552-133">The example gets the results of commands that were running in the ITTask session.</span></span>

<span data-ttu-id="70552-134">Так как команда не использует параметр **Target** , результаты отображаются в командной строке.</span><span class="sxs-lookup"><span data-stu-id="70552-134">Because the command doesn't use the **OutTarget** parameter, the results appear on the command line.</span></span>

### <span data-ttu-id="70552-135">Пример 2. получение результатов всех команд в отключенных сеансах</span><span class="sxs-lookup"><span data-stu-id="70552-135">Example 2: Get results of all commands on disconnected sessions</span></span>

<span data-ttu-id="70552-136">Этот пример возвращает результаты всех команд, выполняющихся во всех отключенных сеансах на двух удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="70552-136">This example gets the results of all commands running in all disconnected sessions on two remote computers.</span></span>

<span data-ttu-id="70552-137">Если какой либо сеанс не был отключен или не выполнял команды, `Receive-PSSession` не подключается к сеансу и не возвращает никаких выходных данных или ошибок.</span><span class="sxs-lookup"><span data-stu-id="70552-137">If any session wasn't disconnected or isn't running commands, `Receive-PSSession` doesn't connect to the session and doesn't return any output or errors.</span></span>

```powershell
Get-PSSession -ComputerName Server01, Server02 | Receive-PSSession
```

<span data-ttu-id="70552-138">`Get-PSSession` задает удаленные компьютеры с помощью параметра **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="70552-138">`Get-PSSession` uses the **ComputerName** parameter to specify the remote computers.</span></span> <span data-ttu-id="70552-139">Объекты отправляются по конвейеру в `Receive-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="70552-139">The objects are sent down the pipeline to `Receive-PSSession`.</span></span>

### <span data-ttu-id="70552-140">Пример 3. получение результатов сценария, выполняемого в сеансе</span><span class="sxs-lookup"><span data-stu-id="70552-140">Example 3: Get the results of a script running in a session</span></span>

<span data-ttu-id="70552-141">В этом примере используется `Receive-PSSession` командлет для получения результатов сценария, который был запущен в сеансе удаленного компьютера.</span><span class="sxs-lookup"><span data-stu-id="70552-141">This example uses the `Receive-PSSession` cmdlet to get the results of a script that was running in a remote computer's session.</span></span>

```powershell
$parms = @{
  ComputerName = "Server01"
  Name = "ITTask"
  OutTarget = "Job"
  JobName = "ITTaskJob01"
  Credential = "Domain01\Admin01"
}
Receive-PSSession @parms
```

```Output
Id     Name            State         HasMoreData     Location
--     ----            -----         -----------     --------
16     ITTaskJob01     Running       True            Server01
```

<span data-ttu-id="70552-142">Команда использует параметры **ComputerName** и **Name** для идентификации отключенного сеанса.</span><span class="sxs-lookup"><span data-stu-id="70552-142">The command uses the **ComputerName** and **Name** parameters to identify the disconnected session.</span></span>
<span data-ttu-id="70552-143">Он использует параметр **Target** со значением задания для направления `Receive-PSSession` возврата результатов в виде задания.</span><span class="sxs-lookup"><span data-stu-id="70552-143">It uses the **OutTarget** parameter with a value of Job to direct `Receive-PSSession` to return the results as a job.</span></span> <span data-ttu-id="70552-144">Параметр **JobName** указывает имя задания в повторно подключенном сеансе.</span><span class="sxs-lookup"><span data-stu-id="70552-144">The **JobName** parameter specifies a name for the job in the reconnected session.</span></span>
<span data-ttu-id="70552-145">Параметр **Credential** выполняет команду, `Receive-PSSession` используя разрешения администратора домена.</span><span class="sxs-lookup"><span data-stu-id="70552-145">The **Credential** parameter runs the `Receive-PSSession` command using the permissions of a domain administrator.</span></span>

<span data-ttu-id="70552-146">Выходные данные показывают, что `Receive-PSSession` результаты возвращались в виде задания в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="70552-146">The output shows that `Receive-PSSession` returned the results as a job in the current session.</span></span> <span data-ttu-id="70552-147">Чтобы получить результаты задания, используйте команду. `Receive-Job`</span><span class="sxs-lookup"><span data-stu-id="70552-147">To get the job results, use a `Receive-Job` command</span></span>

### <span data-ttu-id="70552-148">Пример 4. получение результатов после сбоя сети</span><span class="sxs-lookup"><span data-stu-id="70552-148">Example 4: Get results after a network outage</span></span>

<span data-ttu-id="70552-149">В этом примере используется `Receive-PSSession` командлет для получения результатов задания после того, как сетевой сбой прерывает соединение с сеансом.</span><span class="sxs-lookup"><span data-stu-id="70552-149">This example uses the `Receive-PSSession` cmdlet to get the results of a job after a network outage disrupts a session connection.</span></span> <span data-ttu-id="70552-150">PowerShell автоматически пытается повторно подключиться к сеансу раз в секунду в течение следующих четырех минут и отменяет усилия только в случае сбоя всех попыток в течение четырех минут.</span><span class="sxs-lookup"><span data-stu-id="70552-150">PowerShell automatically attempts to reconnect the session once per second for the next four minutes and abandons the effort only if all attempts in the four-minute interval fail.</span></span>

```
PS> $s = New-PSSession -ComputerName Server01 -Name AD -ConfigurationName ADEndpoint
PS> $s

Id  Name   ComputerName    State        ConfigurationName     Availability
--  ----   ------------    -----        -----------------     ------------
8   AD      Server01       Opened       ADEndpoint               Available


PS> Invoke-Command -Session $s -FilePath \\Server12\Scripts\SharedScripts\New-ADResolve.ps1

Running "New-ADResolve.ps1"

# Network outage
# Restart local computer
# Network access is not re-established within 4 minutes


PS> Get-PSSession -ComputerName Server01

Id  Name   ComputerName    State          ConfigurationName      Availability
--  ----   ------------    -----          -----------------      ------------
1  Backup  Server01        Disconnected   Microsoft.PowerShell           None
8  AD      Server01        Disconnected   ADEndpoint                     None


PS> Receive-PSSession -ComputerName Server01 -Name AD -OutTarget Job -JobName AD

Job Id   Name      State         HasMoreData     Location
--       ----      -----         -----------     --------
16       ADJob     Running       True            Server01


PS> Get-PSSession -ComputerName Server01

Id  Name    ComputerName    State         ConfigurationName     Availability
--  ----    ------------    -----         -----------------     ------------
1  Backup   Server01        Disconnected  Microsoft.PowerShell          Busy
8  AD       Server01        Opened        ADEndpoint               Available
```

<span data-ttu-id="70552-151">`New-PSSession`Командлет создает сеанс на компьютере Server01 и сохраняет сеанс в `$s` переменной.</span><span class="sxs-lookup"><span data-stu-id="70552-151">The `New-PSSession` cmdlet creates a session on the Server01 computer and saves the session in the `$s` variable.</span></span> <span data-ttu-id="70552-152">`$s`Переменная показывает, что **состояние** открыто и доступна **доступность** .</span><span class="sxs-lookup"><span data-stu-id="70552-152">The `$s` variable displays that the **State** is Opened and the **Availability** is Available.</span></span> <span data-ttu-id="70552-153">Эти значения указывают, что вы подключены к сеансу и можете выполнять команды в сеансе.</span><span class="sxs-lookup"><span data-stu-id="70552-153">These values indicate that you're connected to the session and can run commands in the session.</span></span>

<span data-ttu-id="70552-154">`Invoke-Command`Командлет запускает скрипт в сеансе в `$s` переменной.</span><span class="sxs-lookup"><span data-stu-id="70552-154">The `Invoke-Command` cmdlet runs a script in the session in the `$s` variable.</span></span> <span data-ttu-id="70552-155">Скрипт начинает выполняться и возвращает данные, но из-за сбоя сети сеанс прерывается.</span><span class="sxs-lookup"><span data-stu-id="70552-155">The script begins to run and return data, but a network outage occurs that interrupts the session.</span></span> <span data-ttu-id="70552-156">Пользователю необходимо завершить сеанс и перезагрузить локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="70552-156">The user has to exit the session and restart the local computer.</span></span>

<span data-ttu-id="70552-157">При перезапуске компьютера пользователь запускает PowerShell и выполняет `Get-PSSession` команду для получения сеансов на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="70552-157">When the computer restarts, the user starts PowerShell and runs a `Get-PSSession` command to get sessions on the Server01 computer.</span></span> <span data-ttu-id="70552-158">В выходных данных показано, что сеанс **AD** по-прежнему существует на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="70552-158">The output shows that the **AD** session still exists on the Server01 computer.</span></span> <span data-ttu-id="70552-159">**Состояние** указывает на то, что сеанс **AD** отключен.</span><span class="sxs-lookup"><span data-stu-id="70552-159">The **State** indicates that the **AD** session is disconnected.</span></span> <span data-ttu-id="70552-160">Значение **доступности** None указывает, что сеанс не подключен ни к одному из клиентских сеансов.</span><span class="sxs-lookup"><span data-stu-id="70552-160">The **Availability** value of None, indicates that the session isn't connected to any client sessions.</span></span>

<span data-ttu-id="70552-161">`Receive-PSSession`Командлет повторно подключится к сеансу **AD** и получит результаты сценария, который выполнялся в сеансе.</span><span class="sxs-lookup"><span data-stu-id="70552-161">The `Receive-PSSession` cmdlet reconnects to the **AD** session and gets the results of the script that ran in the session.</span></span> <span data-ttu-id="70552-162">Команда использует параметр **Target** для запроса результатов в задании с именем **аджоб** .</span><span class="sxs-lookup"><span data-stu-id="70552-162">The command uses the **OutTarget** parameter to request the results in a job named **ADJob** .</span></span> <span data-ttu-id="70552-163">Команда возвращает объект задания, и выходные данные указывают на то, что сценарий все еще выполняется.</span><span class="sxs-lookup"><span data-stu-id="70552-163">The command returns a job object and the output indicates that the script is still running.</span></span>

<span data-ttu-id="70552-164">`Get-PSSession`Командлет используется для проверки состояния задания.</span><span class="sxs-lookup"><span data-stu-id="70552-164">The `Get-PSSession` cmdlet is used to check the job state.</span></span> <span data-ttu-id="70552-165">Выходные данные подтверждают, что `Receive-PSSession` командлет повторно подключен к сеансу **AD** , который теперь открыт и доступен для команд.</span><span class="sxs-lookup"><span data-stu-id="70552-165">The output confirms that the `Receive-PSSession` cmdlet reconnected to the **AD** session, which is now open and available for commands.</span></span> <span data-ttu-id="70552-166">Скрипт возобновил выполнение и получает результаты скрипта.</span><span class="sxs-lookup"><span data-stu-id="70552-166">And, the script resumed execution and is getting the script results.</span></span>

### <span data-ttu-id="70552-167">Пример 5. Повторное подключение к отключенным сеансам</span><span class="sxs-lookup"><span data-stu-id="70552-167">Example 5: Reconnect to disconnected sessions</span></span>

<span data-ttu-id="70552-168">В этом примере `Receive-PSSession` командлет используется для повторного подключения к сеансам, которые были намеренно отключены, и получения результатов заданий, которые были запущены в сеансах.</span><span class="sxs-lookup"><span data-stu-id="70552-168">This example uses the `Receive-PSSession` cmdlet to reconnect to sessions that were intentionally disconnected and get the results of jobs that were running in the sessions.</span></span>

```
PS> $parms = @{
      InDisconnectedSession = $True
      ComputerName = "Server01", "Server02", "Server30"
      FilePath = "\\Server12\Scripts\SharedScripts\Get-BugStatus.ps1"
      Name = "BugStatus"
      SessionOption = @{IdleTimeout = 86400000}
      ConfigurationName = "ITTasks"
    }
PS> Invoke-Command @parms
PS> Exit


PS> $s = Get-PSSession -ComputerName Server01, Server02, Server30 -Name BugStatus
PS> $s

Id  Name   ComputerName    State         ConfigurationName     Availability
--  ----   ------------    -----         -----------------     ------------
1  ITTask  Server01        Disconnected  ITTasks                       None
8  ITTask  Server02        Disconnected  ITTasks                       None
2  ITTask  Server30        Disconnected  ITTasks                       None


PS> $Results = Receive-PSSession -Session $s
PS> $s

Id  Name   ComputerName    State         ConfigurationName     Availability
--  ----   ------------    -----         -----------------     ------------
1  ITTask  Server01        Opened        ITTasks                  Available
8  ITTask  Server02        Opened        ITTasks                  Available
2  ITTask  Server30        Opened        ITTasks                  Available


PS> $Results

Bug Report - Domain 01
----------------------
ComputerName          BugCount          LastUpdated
--------------        ---------         ------------
Server01              121               Friday, December 30, 2011 5:03:34 PM
```

<span data-ttu-id="70552-169">`Invoke-Command`Командлет запускает сценарий на трех удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="70552-169">The `Invoke-Command` cmdlet runs a script on three remote computers.</span></span> <span data-ttu-id="70552-170">Поскольку сценарий собирает и суммирует данные из нескольких баз данных, они часто занимают длительное время для завершения сценария.</span><span class="sxs-lookup"><span data-stu-id="70552-170">Because the script gathers and summarizes data from multiple databases, it often takes the script an extended time to finish.</span></span> <span data-ttu-id="70552-171">Команда использует параметр **InDisconnectedSession** , который запускает скрипты, а затем сразу же отключает сеансы.</span><span class="sxs-lookup"><span data-stu-id="70552-171">The command uses the **InDisconnectedSession** parameter that starts the scripts and then immediately disconnects the sessions.</span></span> <span data-ttu-id="70552-172">Параметр **SessionOption** расширяет значение **IdleTimeout** в отключенном сеансе.</span><span class="sxs-lookup"><span data-stu-id="70552-172">The **SessionOption** parameter extends the **IdleTimeout** value of the disconnected session.</span></span> <span data-ttu-id="70552-173">Отключенные сеансы считаются неактивными с момента отключения.</span><span class="sxs-lookup"><span data-stu-id="70552-173">Disconnected sessions are considered idle from the moment they're disconnected.</span></span> <span data-ttu-id="70552-174">Важно установить тайм-аут простоя для достаточного времени, чтобы команды могли быть выполнены и можно было заново подключиться к сеансу.</span><span class="sxs-lookup"><span data-stu-id="70552-174">It's important to set the idle time-out for long enough so that the commands can complete and you can reconnect to the session.</span></span> <span data-ttu-id="70552-175">Параметр **IdleTimeout** можно задать только при создании **сеанса PSSession** и изменить его только при отключении от него.</span><span class="sxs-lookup"><span data-stu-id="70552-175">You can set the **IdleTimeout** only when you create the **PSSession** and change it only when you disconnect from it.</span></span> <span data-ttu-id="70552-176">Нельзя изменить значение **IdleTimeout** при подключении к **сеансу PSSession** или получении его результатов.</span><span class="sxs-lookup"><span data-stu-id="70552-176">You can't change the **IdleTimeout** value when you connect to a **PSSession** or receiving its results.</span></span> <span data-ttu-id="70552-177">После выполнения команды пользователь выходит из PowerShell и закрывает компьютер.</span><span class="sxs-lookup"><span data-stu-id="70552-177">After running the command, the user exits PowerShell and closes the computer.</span></span>

<span data-ttu-id="70552-178">На следующий день пользователь возобновляет работу с Windows, запускает PowerShell и использует `Get-PSSession` для получения сеансов, в которых выполнялись сценарии.</span><span class="sxs-lookup"><span data-stu-id="70552-178">The next day, the user resumes Windows, starts PowerShell, and uses `Get-PSSession` to get the sessions in which the scripts were running.</span></span> <span data-ttu-id="70552-179">Команда определяет сеансы по имени компьютера, имени сеанса, имени конфигурации сеанса и сохраняет сеансы в `$s` переменной.</span><span class="sxs-lookup"><span data-stu-id="70552-179">The command identifies the sessions by the computer name, session name, and the name of the session configuration and saves the sessions in the `$s` variable.</span></span> <span data-ttu-id="70552-180">Значение `$s` переменной отображается и показывает, что сеансы отключены, но не заняты.</span><span class="sxs-lookup"><span data-stu-id="70552-180">The value of the `$s` variable is displayed and shows that the sessions are disconnected, but aren't busy.</span></span>

<span data-ttu-id="70552-181">`Receive-PSSession`Командлет подключается к сеансам в `$s` переменной и получает их результаты.</span><span class="sxs-lookup"><span data-stu-id="70552-181">The `Receive-PSSession` cmdlet connects to the sessions in the `$s` variable and gets their results.</span></span>
<span data-ttu-id="70552-182">Команда сохраняет результаты в `$Results` переменной.</span><span class="sxs-lookup"><span data-stu-id="70552-182">The command saves the results in the `$Results` variable.</span></span> <span data-ttu-id="70552-183">`$s`Переменная отображается и показывает, что сеансы подключены и доступны для команд.</span><span class="sxs-lookup"><span data-stu-id="70552-183">The `$s` variable is displayed and shows that the sessions are connected and available for commands.</span></span>

<span data-ttu-id="70552-184">Результат выполнения скрипта в этой `$Results` переменной отображается в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="70552-184">The script results in the `$Results` variable are displayed in the PowerShell console.</span></span> <span data-ttu-id="70552-185">В случае непредвиденных результатов пользователь может выполнять команды в сеансах, чтобы исследовать основную причину.</span><span class="sxs-lookup"><span data-stu-id="70552-185">If any of the results are unexpected, the user can run commands in the sessions to investigate the root cause.</span></span>

### <span data-ttu-id="70552-186">Пример 6. выполнение задания в отключенном сеансе</span><span class="sxs-lookup"><span data-stu-id="70552-186">Example 6: Running a job in a disconnected session</span></span>

<span data-ttu-id="70552-187">В этом примере показано, что происходит с заданием, которое выполняется в отключенном сеансе.</span><span class="sxs-lookup"><span data-stu-id="70552-187">This example shows what happens to a job that's running in a disconnected session.</span></span>

```
PS> $s = New-PSSession -ComputerName Server01 -Name Test
PS> $j = Invoke-Command -Session $s { 1..1500 | Foreach-Object {"Return $_"; sleep 30}} -AsJob
PS> $j

Id     Name           State         HasMoreData     Location
--     ----           -----         -----------     --------
16     Job1           Running       True            Server01


PS> $s | Disconnect-PSSession

Id Name   ComputerName    State         ConfigurationName     Availability
-- ----   ------------    -----         -----------------     ------------
1  Test   Server01        Disconnected  Microsoft.PowerShell          None


PS> $j

Id     Name           State         HasMoreData     Location
--     ----           -----         -----------     --------
16     Job1           Disconnected  True            Server01


PS> Receive-Job $j -Keep

Return 1
Return 2


PS> $s2 = Connect-PSSession -ComputerName Server01 -Name Test
PS> $j2 = Receive-PSSession -ComputerName Server01 -Name Test
PS> Receive-Job $j

Return 3
Return 4
```

<span data-ttu-id="70552-188">`New-PSSession`Командлет создает сеанс тестирования на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="70552-188">The `New-PSSession` cmdlet creates the Test session on the Server01 computer.</span></span> <span data-ttu-id="70552-189">Сеанс сохраняется в переменную `$s`.</span><span class="sxs-lookup"><span data-stu-id="70552-189">The command saves the session in the `$s` variable.</span></span>

<span data-ttu-id="70552-190">`Invoke-Command`Командлет выполняет команду в сеансе в `$s` переменной.</span><span class="sxs-lookup"><span data-stu-id="70552-190">The `Invoke-Command` cmdlet runs a command in the session in the `$s` variable.</span></span> <span data-ttu-id="70552-191">Команда использует параметр **AsJob** для выполнения команды в качестве задания и создает объект задания в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="70552-191">The command uses the **AsJob** parameter to run the command as a job and creates the job object in the current session.</span></span>
<span data-ttu-id="70552-192">Команда возвращает объект задания, сохраненный в `$j` переменной.</span><span class="sxs-lookup"><span data-stu-id="70552-192">The command returns a job object that's saved in the `$j` variable.</span></span> <span data-ttu-id="70552-193">`$j`Переменная отображает объект задания.</span><span class="sxs-lookup"><span data-stu-id="70552-193">The `$j` variable displays the job object.</span></span>

<span data-ttu-id="70552-194">Объект сеанса в `$s` переменной отправляется по конвейеру в `Disconnect-PSSession` , а сеанс отключается.</span><span class="sxs-lookup"><span data-stu-id="70552-194">The session object in the `$s` variable is sent down the pipeline to `Disconnect-PSSession` and the session is disconnected.</span></span>

<span data-ttu-id="70552-195">`$j`Переменная отображается и показывает результат отключения объекта задания в `$j` переменной.</span><span class="sxs-lookup"><span data-stu-id="70552-195">The `$j` variable is displayed and shows the effect of disconnecting the job object in the `$j` variable.</span></span> <span data-ttu-id="70552-196">Состояние задания меняется на "Отключено".</span><span class="sxs-lookup"><span data-stu-id="70552-196">The job state is now Disconnected.</span></span>

<span data-ttu-id="70552-197">`Receive-Job`Выполняется в задании в `$j` переменной.</span><span class="sxs-lookup"><span data-stu-id="70552-197">The `Receive-Job` is run on the job in the `$j` variable.</span></span> <span data-ttu-id="70552-198">Выходные данные показывают, что задание приступило к возврату выходных данных до отключения сеанса и задания.</span><span class="sxs-lookup"><span data-stu-id="70552-198">The output shows that the job began to return output before the session and the job were disconnected.</span></span>

<span data-ttu-id="70552-199">`Connect-PSSession`Командлет выполняется в том же сеансе клиента.</span><span class="sxs-lookup"><span data-stu-id="70552-199">The `Connect-PSSession` cmdlet is run in the same client session.</span></span> <span data-ttu-id="70552-200">Команда повторно подключится к сеансу тестирования на компьютере Server01 и сохранит сеанс в `$s2` переменной.</span><span class="sxs-lookup"><span data-stu-id="70552-200">The command reconnects to the Test session on the Server01 computer and saves the session in the `$s2` variable.</span></span>

<span data-ttu-id="70552-201">`Receive-PSSession`Командлет возвращает результаты задания, которое было запущено в сеансе.</span><span class="sxs-lookup"><span data-stu-id="70552-201">The `Receive-PSSession` cmdlet gets the results of the job that was running in the session.</span></span> <span data-ttu-id="70552-202">Поскольку команда выполняется в том же сеансе, `Receive-PSSession` по умолчанию возвращает результаты в виде задания и повторно использует тот же объект задания.</span><span class="sxs-lookup"><span data-stu-id="70552-202">Because the command is run in the same session, `Receive-PSSession` returns the results as a job by default and reuses the same job object.</span></span> <span data-ttu-id="70552-203">Команда сохраняет задание в `$j2` переменной.</span><span class="sxs-lookup"><span data-stu-id="70552-203">The command saves the job in the `$j2` variable.</span></span> <span data-ttu-id="70552-204">`Receive-Job`Командлет возвращает результаты задания в `$j` переменной.</span><span class="sxs-lookup"><span data-stu-id="70552-204">The `Receive-Job` cmdlet gets the results of the job in the `$j` variable.</span></span>

## <span data-ttu-id="70552-205">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="70552-205">PARAMETERS</span></span>

### <span data-ttu-id="70552-206">-AllowRedirection</span><span class="sxs-lookup"><span data-stu-id="70552-206">-AllowRedirection</span></span>

<span data-ttu-id="70552-207">Указывает, что этот командлет разрешает перенаправление этого соединения в альтернативный универсальный код ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="70552-207">Indicates that this cmdlet allows redirection of this connection to an alternate Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="70552-208">При использовании параметра **ConnectionURI** удаленный компьютер может вернуть инструкцию для перенаправления на другой URI.</span><span class="sxs-lookup"><span data-stu-id="70552-208">When you use the **ConnectionURI** parameter, the remote destination can return an instruction to redirect to a different URI.</span></span> <span data-ttu-id="70552-209">По умолчанию PowerShell не перенаправляет соединения, но можно использовать этот параметр, чтобы разрешить ему перенаправить подключение.</span><span class="sxs-lookup"><span data-stu-id="70552-209">By default, PowerShell doesn't redirect connections, but you can use this parameter to enable it to redirect the connection.</span></span>

<span data-ttu-id="70552-210">Можно также ограничить количество перенаправлений соединение, изменив значение параметра сеанса **MaximumConnectionRedirectionCount** .</span><span class="sxs-lookup"><span data-stu-id="70552-210">You can also limit the number of times the connection is redirected by changing the **MaximumConnectionRedirectionCount** session option value.</span></span> <span data-ttu-id="70552-211">Используйте параметр **максимумредиректион** `New-PSSessionOption` командлета или задайте свойство **MaximumConnectionRedirectionCount** `$PSSessionOption` переменной предпочтений.</span><span class="sxs-lookup"><span data-stu-id="70552-211">Use the **MaximumRedirection** parameter of the `New-PSSessionOption` cmdlet or set the **MaximumConnectionRedirectionCount** property of the `$PSSessionOption` preference variable.</span></span> <span data-ttu-id="70552-212">Значение по умолчанию — 5.</span><span class="sxs-lookup"><span data-stu-id="70552-212">The default value is 5.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ConnectionUriSessionName, ConnectionUriInstanceId
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="70552-213">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="70552-213">-ApplicationName</span></span>

<span data-ttu-id="70552-214">Указывает приложение.</span><span class="sxs-lookup"><span data-stu-id="70552-214">Specifies an application.</span></span> <span data-ttu-id="70552-215">Этот командлет подключается только к сеансам, использующим указанное приложение.</span><span class="sxs-lookup"><span data-stu-id="70552-215">This cmdlet connects only to sessions that use the specified application.</span></span>

<span data-ttu-id="70552-216">Введите сегмент имени приложения URI подключения.</span><span class="sxs-lookup"><span data-stu-id="70552-216">Enter the application name segment of the connection URI.</span></span> <span data-ttu-id="70552-217">Например, в следующем URI соединения WSMan — это имя приложения: `http://localhost:5985/WSMAN` .</span><span class="sxs-lookup"><span data-stu-id="70552-217">For example, in the following connection URI, WSMan is the application name: `http://localhost:5985/WSMAN`.</span></span>

<span data-ttu-id="70552-218">Имя приложения сеанса хранится в свойстве сеанса **Runspace.ConnectionInfo.AppName** .</span><span class="sxs-lookup"><span data-stu-id="70552-218">The application name of a session is stored in the **Runspace.ConnectionInfo.AppName** property of the session.</span></span>

<span data-ttu-id="70552-219">Значение параметра используется для выбора и фильтрации сеансов.</span><span class="sxs-lookup"><span data-stu-id="70552-219">The parameter's value is used to select and filter sessions.</span></span> <span data-ttu-id="70552-220">Оно не изменяет приложение, которое использует сеанс.</span><span class="sxs-lookup"><span data-stu-id="70552-220">It doesn't change the application that the session uses.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerInstanceId, ComputerSessionName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="70552-221">-Authentication</span><span class="sxs-lookup"><span data-stu-id="70552-221">-Authentication</span></span>

<span data-ttu-id="70552-222">Указывает механизм, используемый для проверки подлинности учетных данных пользователя в команде для повторного подключения к отключенному сеансу.</span><span class="sxs-lookup"><span data-stu-id="70552-222">Specifies the mechanism that's used to authenticate the user credentials in the command to reconnect to a disconnected session.</span></span> <span data-ttu-id="70552-223">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="70552-223">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="70552-224">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="70552-224">Default</span></span>
- <span data-ttu-id="70552-225">Базовый</span><span class="sxs-lookup"><span data-stu-id="70552-225">Basic</span></span>
- <span data-ttu-id="70552-226">CredSSP</span><span class="sxs-lookup"><span data-stu-id="70552-226">Credssp</span></span>
- <span data-ttu-id="70552-227">Digest (дайджест)</span><span class="sxs-lookup"><span data-stu-id="70552-227">Digest</span></span>
- <span data-ttu-id="70552-228">Kerberos</span><span class="sxs-lookup"><span data-stu-id="70552-228">Kerberos</span></span>
- <span data-ttu-id="70552-229">Согласование</span><span class="sxs-lookup"><span data-stu-id="70552-229">Negotiate</span></span>
- <span data-ttu-id="70552-230">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="70552-230">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="70552-231">Значение по умолчанию — Default.</span><span class="sxs-lookup"><span data-stu-id="70552-231">The default value is Default.</span></span>

<span data-ttu-id="70552-232">Дополнительные сведения о значениях этого параметра см. в разделе [AuthenticationMechanism enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="70552-232">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!CAUTION]
> <span data-ttu-id="70552-233">Проверка подлинности с помощью поставщика поддержки безопасности учетных данных (CredSSP), в которой учетные данные пользователя передаются на удаленный компьютер для проверки подлинности, предназначена для команд, требующих проверки подлинности в нескольких ресурсах, таких как доступ к удаленной сетевой папке.</span><span class="sxs-lookup"><span data-stu-id="70552-233">Credential Security Support Provider (CredSSP) authentication, in which the user credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="70552-234">Этот механизм повышает риск безопасности удаленной операции.</span><span class="sxs-lookup"><span data-stu-id="70552-234">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="70552-235">Если удаленный компьютер скомпрометирован, учетные данные, передаваемые ему, могут использоваться для управления сетевым сеансом.</span><span class="sxs-lookup"><span data-stu-id="70552-235">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ComputerInstanceId, ComputerSessionName, ConnectionUriSessionName, ConnectionUriInstanceId
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="70552-236">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="70552-236">-CertificateThumbprint</span></span>

<span data-ttu-id="70552-237">Задает цифровой сертификат с открытым ключом (X509) учетной записи пользователя, который располагает разрешением для подключения к отсоединенному сеансу.</span><span class="sxs-lookup"><span data-stu-id="70552-237">Specifies the digital public key certificate (X509) of a user account that has permission to connect to the disconnected session.</span></span> <span data-ttu-id="70552-238">Введите отпечаток сертификата.</span><span class="sxs-lookup"><span data-stu-id="70552-238">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="70552-239">Сертификаты используются при проверке подлинности на основе сертификата клиента.</span><span class="sxs-lookup"><span data-stu-id="70552-239">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="70552-240">Сертификаты могут сопоставляться только с локальными учетными записями пользователей и не работать с учетными записями домена.</span><span class="sxs-lookup"><span data-stu-id="70552-240">Certificates can be mapped only to local user accounts, and don't work with domain accounts.</span></span>

<span data-ttu-id="70552-241">Чтобы получить отпечаток сертификата, используйте `Get-Item` `Get-ChildItem` команду или на диске PowerShell `Cert:` .</span><span class="sxs-lookup"><span data-stu-id="70552-241">To get a certificate thumbprint, use a `Get-Item` or `Get-ChildItem` command in the PowerShell `Cert:` drive.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerInstanceId, ComputerSessionName, ConnectionUriSessionName, ConnectionUriInstanceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="70552-242">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="70552-242">-ComputerName</span></span>

<span data-ttu-id="70552-243">Указывает компьютер, на котором хранится отключенный сеанс.</span><span class="sxs-lookup"><span data-stu-id="70552-243">Specifies the computer on which the disconnected session is stored.</span></span> <span data-ttu-id="70552-244">Сеансы хранятся на компьютере, который находится на стороне сервера или получает окончание соединения.</span><span class="sxs-lookup"><span data-stu-id="70552-244">Sessions are stored on the computer that's at the server-side, or receiving end of a connection.</span></span> <span data-ttu-id="70552-245">По умолчанию это локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="70552-245">The default is the local computer.</span></span>

<span data-ttu-id="70552-246">Введите имя NetBIOS, IP-адрес или полное доменное имя (FQDN) одного компьютера.</span><span class="sxs-lookup"><span data-stu-id="70552-246">Type the NetBIOS name, an IP address, or a fully qualified domain name (FQDN) of one computer.</span></span>
<span data-ttu-id="70552-247">Подстановочные знаки не допускаются.</span><span class="sxs-lookup"><span data-stu-id="70552-247">Wildcard characters aren't permitted.</span></span> <span data-ttu-id="70552-248">Чтобы указать локальный компьютер, введите имя компьютера, точку ( `.` ), `$env:COMPUTERNAME` или localhost.</span><span class="sxs-lookup"><span data-stu-id="70552-248">To specify the local computer, type the computer name, a dot (`.`), `$env:COMPUTERNAME`, or localhost.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerInstanceId, ComputerSessionName
Aliases: Cn

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="70552-249">-ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="70552-249">-ConfigurationName</span></span>

<span data-ttu-id="70552-250">Указывает имя конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="70552-250">Specifies the name of a session configuration.</span></span> <span data-ttu-id="70552-251">Этот командлет подключается только к сеансам, использующим указанную конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="70552-251">This cmdlet connects only to sessions that use the specified session configuration.</span></span>

<span data-ttu-id="70552-252">Введите имя конфигурации или полное имя ресурса (URI) для конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="70552-252">Enter a configuration name or the fully qualified resource URI for a session configuration.</span></span> <span data-ttu-id="70552-253">Если указать только имя конфигурации, добавляется следующая схема URI:</span><span class="sxs-lookup"><span data-stu-id="70552-253">If you specify only the configuration name, the following schema URI is prepended:</span></span>

<span data-ttu-id="70552-254">`http://schemas.microsoft.com/powershell`.</span><span class="sxs-lookup"><span data-stu-id="70552-254">`http://schemas.microsoft.com/powershell`.</span></span>

<span data-ttu-id="70552-255">Имя конфигурации сеанса хранится в свойстве сеанса **ConfigurationName** .</span><span class="sxs-lookup"><span data-stu-id="70552-255">The configuration name of a session is stored in the **ConfigurationName** property of the session.</span></span>

<span data-ttu-id="70552-256">Значение параметра используется для выбора и фильтрации сеансов.</span><span class="sxs-lookup"><span data-stu-id="70552-256">The parameter's value is used to select and filter sessions.</span></span> <span data-ttu-id="70552-257">Он не изменяет конфигурацию сеанса, используемую сеансом.</span><span class="sxs-lookup"><span data-stu-id="70552-257">It doesn't change the session configuration that the session uses.</span></span>

<span data-ttu-id="70552-258">Дополнительные сведения о конфигурациях сеансов см. в разделе [about_Session_Configurations](./About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="70552-258">For more information about session configurations, see [about_Session_Configurations](./About/about_Session_Configurations.md).</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerInstanceId, ComputerSessionName, ConnectionUriSessionName, ConnectionUriInstanceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="70552-259">-ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="70552-259">-ConnectionUri</span></span>

<span data-ttu-id="70552-260">Указывает универсальный код ресурса (URI), определяющий конечную точку подключения, используемую для повторного подключения к отключенному сеансу.</span><span class="sxs-lookup"><span data-stu-id="70552-260">Specifies a URI that defines the connection endpoint that is used to reconnect to the disconnected session.</span></span>

<span data-ttu-id="70552-261">Значение URI должно быть указано полностью.</span><span class="sxs-lookup"><span data-stu-id="70552-261">The URI must be fully qualified.</span></span> <span data-ttu-id="70552-262">Формат строки выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="70552-262">The string's format is as follows:</span></span>

`<Transport>://<ComputerName>:<Port>/<ApplicationName>`

<span data-ttu-id="70552-263">Значение по умолчанию определяется следующим образом.</span><span class="sxs-lookup"><span data-stu-id="70552-263">The default value is as follows:</span></span>

`http://localhost:5985/WSMAN`

<span data-ttu-id="70552-264">Если не указать URI соединения, можно использовать параметры **UseSSL** , **ComputerName** , **Port** и **applicationName** , чтобы указать значения универсального кода ресурса (URI) соединения.</span><span class="sxs-lookup"><span data-stu-id="70552-264">If you don't specify a connection URI, you can use the **UseSSL** , **ComputerName** , **Port** , and **ApplicationName** parameters to specify the connection URI values.</span></span>

<span data-ttu-id="70552-265">Допустимые значения для сегмента **Transport** идентификатора URI: HTTP и HTTPS.</span><span class="sxs-lookup"><span data-stu-id="70552-265">Valid values for the **Transport** segment of the URI are HTTP and HTTPS.</span></span> <span data-ttu-id="70552-266">Если указать универсальный код ресурса (URI) соединения с сегментом транспорта, но не указывать порт, то сеанс будет создан с использованием стандартных портов: 80 для HTTP и 443 для HTTPS.</span><span class="sxs-lookup"><span data-stu-id="70552-266">If you specify a connection URI with a Transport segment, but don't specify a port, the session is created with standard ports: 80 for HTTP and 443 for HTTPS.</span></span> <span data-ttu-id="70552-267">Чтобы использовать порты по умолчанию для удаленного взаимодействия PowerShell, укажите порт 5985 для HTTP или 5986 для HTTPS.</span><span class="sxs-lookup"><span data-stu-id="70552-267">To use the default ports for PowerShell remoting, specify port 5985 for HTTP or 5986 for HTTPS.</span></span>

<span data-ttu-id="70552-268">Если конечный компьютер перенаправляет подключение к другому универсальному коду ресурса (URI), PowerShell предотвращает перенаправление, если в команде не используется параметр **AllowRedirection** .</span><span class="sxs-lookup"><span data-stu-id="70552-268">If the destination computer redirects the connection to a different URI, PowerShell prevents the redirection unless you use the **AllowRedirection** parameter in the command.</span></span>

```yaml
Type: System.Uri
Parameter Sets: ConnectionUriSessionName, ConnectionUriInstanceId
Aliases: URI, CU

Required: True
Position: 0
Default value: http://localhost:5985/WSMAN
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="70552-269">-Credential</span><span class="sxs-lookup"><span data-stu-id="70552-269">-Credential</span></span>

<span data-ttu-id="70552-270">Указывает учетную запись пользователя с разрешением на подключение к отсоединенному сеансу.</span><span class="sxs-lookup"><span data-stu-id="70552-270">Specifies a user account that has permission to connect to the disconnected session.</span></span> <span data-ttu-id="70552-271">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="70552-271">The default is the current user.</span></span>

<span data-ttu-id="70552-272">Введите имя пользователя, например **User01** или **Domain01\User01** , либо введите объект **PSCredential** , созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="70552-272">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="70552-273">Если ввести имя пользователя, будет предложено ввести пароль.</span><span class="sxs-lookup"><span data-stu-id="70552-273">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="70552-274">Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="70552-274">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="70552-275">Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="70552-275">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerInstanceId, ComputerSessionName, ConnectionUriSessionName, ConnectionUriInstanceId
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="70552-276">-Id</span><span class="sxs-lookup"><span data-stu-id="70552-276">-Id</span></span>

<span data-ttu-id="70552-277">Указывает идентификатор отключенного сеанса.</span><span class="sxs-lookup"><span data-stu-id="70552-277">Specifies the ID of a disconnected session.</span></span> <span data-ttu-id="70552-278">Параметр **ID** работает только в том случае, если отключенный сеанс ранее был подключен к текущему сеансу.</span><span class="sxs-lookup"><span data-stu-id="70552-278">The **Id** parameter works only when the disconnected session was previously connected to the current session.</span></span>

<span data-ttu-id="70552-279">Этот параметр является допустимым, но неэффективным, если сеанс хранится на локальном компьютере, но не был подключен к текущему сеансу.</span><span class="sxs-lookup"><span data-stu-id="70552-279">This parameter is valid, but not effective, when the session is stored on the local computer, but wasn't connected to the current session.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="70552-280">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="70552-280">-InstanceId</span></span>

<span data-ttu-id="70552-281">Указывает идентификатор экземпляра отключенного сеанса.</span><span class="sxs-lookup"><span data-stu-id="70552-281">Specifies the instance ID of the disconnected session.</span></span> <span data-ttu-id="70552-282">Идентификатор экземпляра — это идентификатор GUID, который однозначно определяет **сеанс PSSession** на локальном или удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="70552-282">The instance ID is a GUID that uniquely identifies a **PSSession** on a local or remote computer.</span></span> <span data-ttu-id="70552-283">Идентификатор экземпляра хранится в свойстве **InstanceId** **сеанса PSSession** .</span><span class="sxs-lookup"><span data-stu-id="70552-283">The instance ID is stored in the **InstanceID** property of the **PSSession** .</span></span>

```yaml
Type: System.Guid
Parameter Sets: ComputerInstanceId, ConnectionUriInstanceId, InstanceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="70552-284">-JobName</span><span class="sxs-lookup"><span data-stu-id="70552-284">-JobName</span></span>

<span data-ttu-id="70552-285">Указывает понятное имя для задания, которое `Receive-PSSession` возвращает.</span><span class="sxs-lookup"><span data-stu-id="70552-285">Specifies a friendly name for the job that `Receive-PSSession` returns.</span></span>

<span data-ttu-id="70552-286">`Receive-PSSession` Возвращает задание, если в текущем сеансе было запущено значение параметра **Target** или задание, запущенное в отключенном сеансе.</span><span class="sxs-lookup"><span data-stu-id="70552-286">`Receive-PSSession` returns a job when the value of the **OutTarget** parameter is Job or the job that's running in the disconnected session was started in the current session.</span></span>

<span data-ttu-id="70552-287">Если задание, запущенное в отключенном сеансе, было запущено в текущем сеансе, PowerShell повторно использует исходный объект задания в сеансе и игнорирует значение параметра **JobName** .</span><span class="sxs-lookup"><span data-stu-id="70552-287">If the job that's running in the disconnected session was started in the current session, PowerShell reuses the original job object in the session and ignores the value of the **JobName** parameter.</span></span>

<span data-ttu-id="70552-288">Если задание, запущенное в отключенном сеансе, было запущено в другом сеансе, PowerShell создает новый объект задания.</span><span class="sxs-lookup"><span data-stu-id="70552-288">If the job that's running in the disconnected session was started in a different session, PowerShell creates a new job object.</span></span> <span data-ttu-id="70552-289">При этом используется имя по умолчанию, но его можно изменить с помощью этого параметра.</span><span class="sxs-lookup"><span data-stu-id="70552-289">It uses a default name, but you can use this parameter to change the name.</span></span>

<span data-ttu-id="70552-290">Если значение по умолчанию или явное значение параметра **Target** не задано, команда будет выполнена успешно, но параметр **JobName** не будет действовать.</span><span class="sxs-lookup"><span data-stu-id="70552-290">If the default value or explicit value of the **OutTarget** parameter isn't Job, the command succeeds, but the **JobName** parameter has no effect.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="70552-291">-Name</span><span class="sxs-lookup"><span data-stu-id="70552-291">-Name</span></span>

<span data-ttu-id="70552-292">Указывает понятное имя отключенного сеанса.</span><span class="sxs-lookup"><span data-stu-id="70552-292">Specifies the friendly name of the disconnected session.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerSessionName, ConnectionUriSessionName, SessionName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="70552-293">-Назначение</span><span class="sxs-lookup"><span data-stu-id="70552-293">-OutTarget</span></span>

<span data-ttu-id="70552-294">Определяет, как возвращаются результаты сеанса.</span><span class="sxs-lookup"><span data-stu-id="70552-294">Determines how the session results are returned.</span></span> <span data-ttu-id="70552-295">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="70552-295">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="70552-296">**Задание** .</span><span class="sxs-lookup"><span data-stu-id="70552-296">**Job** .</span></span> <span data-ttu-id="70552-297">асинхронно возвращает результаты в объекте задания.</span><span class="sxs-lookup"><span data-stu-id="70552-297">Returns the results asynchronously in a job object.</span></span> <span data-ttu-id="70552-298">С помощью параметра **JobName** можно указать имя задания (имя по умолчанию или новое).</span><span class="sxs-lookup"><span data-stu-id="70552-298">You can use the **JobName** parameter to specify a name or new name for the job.</span></span>
- <span data-ttu-id="70552-299">**Узел** .</span><span class="sxs-lookup"><span data-stu-id="70552-299">**Host** .</span></span> <span data-ttu-id="70552-300">возвращает результаты из командной строки (синхронно).</span><span class="sxs-lookup"><span data-stu-id="70552-300">Returns the results to the command line (synchronously).</span></span> <span data-ttu-id="70552-301">Если команда возобновляется или результаты состоят из большого числа объектов, ответ может быть отложен.</span><span class="sxs-lookup"><span data-stu-id="70552-301">If the command is being resumed or the results consist of a large number of objects, the response might be delayed.</span></span>

<span data-ttu-id="70552-302">Значение **параметра по** умолчанию — Host.</span><span class="sxs-lookup"><span data-stu-id="70552-302">The default value of the **OutTarget** parameter is Host.</span></span> <span data-ttu-id="70552-303">Если команда, полученная в отключенном сеансе, была запущена в текущем сеансе, **значением параметра по** умолчанию является форма, в которой была запущена команда.</span><span class="sxs-lookup"><span data-stu-id="70552-303">If the command that's being received in a disconnected session was started in the current session, the default value of the **OutTarget** parameter is the form in which the command was started.</span></span> <span data-ttu-id="70552-304">Если команда была запущена как задание, по умолчанию она возвращается в виде задания.</span><span class="sxs-lookup"><span data-stu-id="70552-304">If the command was started as a job, by default, it's returned as a job.</span></span> <span data-ttu-id="70552-305">В противном случае по умолчанию возвращается в ведущее приложение.</span><span class="sxs-lookup"><span data-stu-id="70552-305">Otherwise, it's returned to the host program by default.</span></span>

<span data-ttu-id="70552-306">Как правило, основная программа отображает возвращаемые объекты в командной строке без задержки, но это не всегда так.</span><span class="sxs-lookup"><span data-stu-id="70552-306">Typically, the host program displays returned objects at the command line without delay, but this behavior can vary.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.OutTarget
Parameter Sets: (All)
Aliases:
Accepted values: Default, Host, Job

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="70552-307">-Port</span><span class="sxs-lookup"><span data-stu-id="70552-307">-Port</span></span>

<span data-ttu-id="70552-308">Указывает сетевой порт удаленного компьютера, используемый для повторного подключения к сеансу.</span><span class="sxs-lookup"><span data-stu-id="70552-308">Specifies the remote computer's network port that's used to reconnect to the session.</span></span> <span data-ttu-id="70552-309">Для подключения к удаленному компьютеру он должен прослушивать порт, используемый подключением.</span><span class="sxs-lookup"><span data-stu-id="70552-309">To connect to a remote computer, it must be listening on the port that the connection uses.</span></span> <span data-ttu-id="70552-310">Порты по умолчанию — 5985, то есть порт WinRM для HTTP, а 5986 — порт WinRM для HTTPS.</span><span class="sxs-lookup"><span data-stu-id="70552-310">The default ports are 5985, which is the WinRM port for HTTP, and 5986, which is the WinRM port for HTTPS.</span></span>

<span data-ttu-id="70552-311">Перед использованием альтернативного порта необходимо настроить прослушиватель WinRM на удаленном компьютере для прослушивания этого порта.</span><span class="sxs-lookup"><span data-stu-id="70552-311">Before using an alternate port, you must configure the WinRM listener on the remote computer to listen on that port.</span></span> <span data-ttu-id="70552-312">Чтобы настроить прослушиватель, введите следующие две команды в командной строке PowerShell:</span><span class="sxs-lookup"><span data-stu-id="70552-312">To configure the listener, type the following two commands at the PowerShell prompt:</span></span>

`Remove-Item -Path WSMan:\Localhost\listener\listener* -Recurse`

`New-Item -Path WSMan:\Localhost\listener -Transport http -Address * -Port \<port-number\>`

<span data-ttu-id="70552-313">Не используйте параметр **Port** , если он не требуется.</span><span class="sxs-lookup"><span data-stu-id="70552-313">Don't use the **Port** parameter unless it's necessary.</span></span> <span data-ttu-id="70552-314">Порт, заданный в команде, применяется ко всем компьютерам или сеансам, на которых выполняется команда.</span><span class="sxs-lookup"><span data-stu-id="70552-314">The port that's set in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="70552-315">Альтернативный порт может помешать выполнению команды на всех компьютерах.</span><span class="sxs-lookup"><span data-stu-id="70552-315">An alternate port setting might prevent the command from running on all computers.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ComputerInstanceId, ComputerSessionName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="70552-316">-Session</span><span class="sxs-lookup"><span data-stu-id="70552-316">-Session</span></span>

<span data-ttu-id="70552-317">Указывает отключенный сеанс.</span><span class="sxs-lookup"><span data-stu-id="70552-317">Specifies the disconnected session.</span></span> <span data-ttu-id="70552-318">Введите переменную, содержащую **PSSession** или команду, которая создает или получает **сеанс PSSession** , например `Get-PSSession` команду.</span><span class="sxs-lookup"><span data-stu-id="70552-318">Enter a variable that contains the **PSSession** or a command that creates or gets the **PSSession** , such as a `Get-PSSession` command.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: Session
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="70552-319">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="70552-319">-SessionOption</span></span>

<span data-ttu-id="70552-320">Задает дополнительные параметры для сеанса.</span><span class="sxs-lookup"><span data-stu-id="70552-320">Specifies advanced options for the session.</span></span> <span data-ttu-id="70552-321">Введите объект **SessionOption** , например, созданный с помощью `New-PSSessionOption` командлета, или хэш-таблицу, в которой ключи являются именами параметров сеанса, а значения — значениями параметров сеанса.</span><span class="sxs-lookup"><span data-stu-id="70552-321">Enter a **SessionOption** object, such as one that you create by using the `New-PSSessionOption` cmdlet, or a hash table in which the keys are session option names and the values are session option values.</span></span>

<span data-ttu-id="70552-322">Значения по умолчанию для параметров определяются значением `$PSSessionOption` привилегированной переменной, если оно задано.</span><span class="sxs-lookup"><span data-stu-id="70552-322">The default values for the options are determined by the value of the `$PSSessionOption` preference variable, if it's set.</span></span> <span data-ttu-id="70552-323">В противном случае значения по умолчанию задаются параметрами, указанными в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="70552-323">Otherwise, the default values are established by options set in the session configuration.</span></span>

<span data-ttu-id="70552-324">Значения параметров сеанса имеют приоритет над значениями по умолчанию для сеансов, заданных в `$PSSessionOption` переменной предпочтений и в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="70552-324">The session option values take precedence over default values for sessions set in the `$PSSessionOption` preference variable and in the session configuration.</span></span> <span data-ttu-id="70552-325">Однако они не имеют приоритета над максимальными значениями, квотами или ограничениями, установленными в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="70552-325">However, they don't take precedence over maximum values, quotas, or limits set in the session configuration.</span></span>

<span data-ttu-id="70552-326">Описание параметров сеанса, содержащих значения по умолчанию, см. в разделе `New-PSSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="70552-326">For a description of the session options that includes the default values, see `New-PSSessionOption`.</span></span> <span data-ttu-id="70552-327">Дополнительные сведения о переменной настройки **$PSSessionOption** см. в разделе [about_Preference_Variables](./About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="70552-327">For information about the **$PSSessionOption** preference variable, see [about_Preference_Variables](./About/about_Preference_Variables.md).</span></span> <span data-ttu-id="70552-328">Дополнительные сведения о конфигурациях сеансов см. в разделе [about_Session_Configurations](./About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="70552-328">For more information about session configurations, see [about_Session_Configurations](./About/about_Session_Configurations.md).</span></span>

```yaml
Type: System.Management.Automation.Remoting.PSSessionOption
Parameter Sets: ComputerInstanceId, ComputerSessionName, ConnectionUriSessionName, ConnectionUriInstanceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="70552-329">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="70552-329">-UseSSL</span></span>

<span data-ttu-id="70552-330">Указывает, что этот командлет использует протокол SSL (SSL) для подключения к отключенному сеансу.</span><span class="sxs-lookup"><span data-stu-id="70552-330">Indicates that this cmdlet uses the Secure Sockets Layer (SSL) protocol to connect to the disconnected session.</span></span> <span data-ttu-id="70552-331">По умолчанию протокол SSL не используется.</span><span class="sxs-lookup"><span data-stu-id="70552-331">By default, SSL isn't used.</span></span>

<span data-ttu-id="70552-332">WS-Management шифрует все содержимое PowerShell, передаваемое по сети.</span><span class="sxs-lookup"><span data-stu-id="70552-332">WS-Management encrypts all PowerShell content transmitted over the network.</span></span> <span data-ttu-id="70552-333">**UseSSL** обеспечивает дополнительную защиту за счет передачи данных по защищенному HTTPS-подключению вместо HTTP-подключения.</span><span class="sxs-lookup"><span data-stu-id="70552-333">**UseSSL** is an additional protection that sends the data across an HTTPS connection instead of an HTTP connection.</span></span>

<span data-ttu-id="70552-334">Если вы используете этот параметр и протокол SSL недоступен в порте, используемом для команды, команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="70552-334">If you use this parameter and SSL isn't available on the port that's used for the command, the command fails.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerInstanceId, ComputerSessionName
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="70552-335">-Confirm</span><span class="sxs-lookup"><span data-stu-id="70552-335">-Confirm</span></span>

<span data-ttu-id="70552-336">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="70552-336">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="70552-337">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="70552-337">-WhatIf</span></span>

<span data-ttu-id="70552-338">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="70552-338">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="70552-339">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="70552-339">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="70552-340">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="70552-340">CommonParameters</span></span>

<span data-ttu-id="70552-341">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="70552-341">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="70552-342">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="70552-342">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="70552-343">Входные данные</span><span class="sxs-lookup"><span data-stu-id="70552-343">INPUTS</span></span>

### <span data-ttu-id="70552-344">System.Management.Automation.Runspaces.PSSession</span><span class="sxs-lookup"><span data-stu-id="70552-344">System.Management.Automation.Runspaces.PSSession</span></span>

<span data-ttu-id="70552-345">К этому командлету можно передать объекты сеанса, например объекты, возвращаемые `Get-PSSession` командлетом.</span><span class="sxs-lookup"><span data-stu-id="70552-345">You can pipe session objects to this cmdlet, such as objects returned by the `Get-PSSession` cmdlet.</span></span>

### <span data-ttu-id="70552-346">System.Int32</span><span class="sxs-lookup"><span data-stu-id="70552-346">System.Int32</span></span>

<span data-ttu-id="70552-347">В этот командлет можно передать идентификаторы сеансов.</span><span class="sxs-lookup"><span data-stu-id="70552-347">You can pipe session Ids to this cmdlet.</span></span>

### <span data-ttu-id="70552-348">System.Guid</span><span class="sxs-lookup"><span data-stu-id="70552-348">System.Guid</span></span>

<span data-ttu-id="70552-349">Идентификаторы экземпляров сеансов этого командлета можно передать по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="70552-349">You can pipe the instance Ids of sessions this cmdlet.</span></span>

### <span data-ttu-id="70552-350">System.String</span><span class="sxs-lookup"><span data-stu-id="70552-350">System.String</span></span>

<span data-ttu-id="70552-351">К этому командлету можно передать имена сеансов.</span><span class="sxs-lookup"><span data-stu-id="70552-351">You can pipe session names to this cmdlet.</span></span>

## <span data-ttu-id="70552-352">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="70552-352">OUTPUTS</span></span>

### <span data-ttu-id="70552-353">System. Management. Automation. job или PSObject</span><span class="sxs-lookup"><span data-stu-id="70552-353">System.Management.Automation.Job or PSObject</span></span>

<span data-ttu-id="70552-354">Этот командлет возвращает результаты команд, которые выполнялись в отключенном сеансе, если таковые имеются.</span><span class="sxs-lookup"><span data-stu-id="70552-354">This cmdlet returns the results of commands that ran in the disconnected session, if any.</span></span> <span data-ttu-id="70552-355">Если значение или значение по умолчанию параметра для **целевого объекта** задано как Job, `Receive-PSSession` возвращает объект задания.</span><span class="sxs-lookup"><span data-stu-id="70552-355">If the value or default value of the **OutTarget** parameter is Job, `Receive-PSSession` returns a job object.</span></span> <span data-ttu-id="70552-356">В противном случае возвращаются объекты, представляющие результаты выполнения этой команды.</span><span class="sxs-lookup"><span data-stu-id="70552-356">Otherwise, it returns objects that represent that command results.</span></span>

## <span data-ttu-id="70552-357">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="70552-357">NOTES</span></span>

<span data-ttu-id="70552-358">`Receive-PSSession` Возвращает результаты только из сеансов, которые были отключены.</span><span class="sxs-lookup"><span data-stu-id="70552-358">`Receive-PSSession` gets results only from sessions that were disconnected.</span></span> <span data-ttu-id="70552-359">Только сеансы, подключенные к или завершенные на компьютерах, на которых выполняется PowerShell 3,0 или более поздней версии, могут быть отключены и повторно подключены.</span><span class="sxs-lookup"><span data-stu-id="70552-359">Only sessions that are connected to, or terminate at, computers that run PowerShell 3.0 or later versions can be disconnected and reconnected.</span></span>

<span data-ttu-id="70552-360">Если команды, которые выполнялись в отключенном сеансе, не создавали результатов или если результаты уже были возвращены другому сеансу, `Receive-PSSession` не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="70552-360">If the commands that were running in the disconnected session didn't generate results or if the results were already returned to another session, `Receive-PSSession` doesn't generate any output.</span></span>

<span data-ttu-id="70552-361">Режим буферизации вывода сеанса определяет, как команды в сеансе управляют выходными данными при отключении сеанса.</span><span class="sxs-lookup"><span data-stu-id="70552-361">A session's output buffering mode determines how commands in the session manage output when the session is disconnected.</span></span> <span data-ttu-id="70552-362">Если параметр **аутпутбуфферингмоде** сеанса имеет значение Drop и выходной буфер заполнен, команда начинает удалять выходные данные.</span><span class="sxs-lookup"><span data-stu-id="70552-362">When the value of the **OutputBufferingMode** option of the session is Drop and the output buffer is full, the command starts to delete output.</span></span> <span data-ttu-id="70552-363">`Receive-PSSession` не удается восстановить эти выходные данные.</span><span class="sxs-lookup"><span data-stu-id="70552-363">`Receive-PSSession` can't recover this output.</span></span> <span data-ttu-id="70552-364">Дополнительные сведения о параметре режим буферизации вывода см. в статьях справки для командлетов [New-PSSessionOption](New-PSSessionOption.md) и [New-пстранспортоптион](New-PSTransportOption.md) .</span><span class="sxs-lookup"><span data-stu-id="70552-364">For more information about the output buffering mode option, see the help articles for the [New-PSSessionOption](New-PSSessionOption.md) and [New-PSTransportOption](New-PSTransportOption.md) cmdlets.</span></span>

<span data-ttu-id="70552-365">Нельзя изменить значение времени ожидания простоя **сеанса PSSession** при подключении к **сеансу PSSession** или получению результатов.</span><span class="sxs-lookup"><span data-stu-id="70552-365">You can't change the idle time-out value of a **PSSession** when you connect to the **PSSession** or receive results.</span></span> <span data-ttu-id="70552-366">Параметр **SessionOption** `Receive-PSSession` принимает объект **SessionOption** , имеющий значение **IdleTimeout** .</span><span class="sxs-lookup"><span data-stu-id="70552-366">The **SessionOption** parameter of `Receive-PSSession` takes a **SessionOption** object that has an **IdleTimeout** value.</span></span> <span data-ttu-id="70552-367">Однако значение **IdleTimeout** объекта **SessionOption** и значение **IdleTimeout** `$PSSessionOption` переменной не учитывается при подключении к **PSSession** или получению результатов.</span><span class="sxs-lookup"><span data-stu-id="70552-367">However, the **IdleTimeout** value of the **SessionOption** object and the **IdleTimeout** value of the `$PSSessionOption` variable are ignored when it connects to a **PSSession** or receiving results.</span></span>

- <span data-ttu-id="70552-368">Можно задать и изменить время ожидания простоя **сеанса PSSession** при создании **сеанса PSSession** с помощью `New-PSSession` `Invoke-Command` командлетов или, а также при отключении от **сеанса PSSession** .</span><span class="sxs-lookup"><span data-stu-id="70552-368">You can set and change the idle time-out of a **PSSession** when you create the **PSSession** , by using the `New-PSSession` or `Invoke-Command` cmdlets, and when you disconnect from the **PSSession** .</span></span>
- <span data-ttu-id="70552-369">Свойство **IdleTimeout** в **PSSession** очень важно для отключенных сеансов, так как оно определяет, как долго отключенный сеанс сохраняется на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="70552-369">The **IdleTimeout** property of a **PSSession** is critical to disconnected sessions because it determines how long a disconnected session is maintained on the remote computer.</span></span> <span data-ttu-id="70552-370">Отключенные сеансы считаются находящимися в режиме простоя с момента их отключения, даже если в них выполняются команды.</span><span class="sxs-lookup"><span data-stu-id="70552-370">Disconnected sessions are considered to be idle from the moment that they are disconnected, even if commands are running in the disconnected session.</span></span>

<span data-ttu-id="70552-371">Если запустить задание запуска в удаленном сеансе с помощью параметра **AsJob** `Invoke-Command` командлета, то объект задания создается в текущем сеансе, даже если задание выполняется в удаленном сеансе.</span><span class="sxs-lookup"><span data-stu-id="70552-371">If you start a start a job in a remote session by using the **AsJob** parameter of the `Invoke-Command` cmdlet, the job object is created in the current session, even though the job runs in the remote session.</span></span> <span data-ttu-id="70552-372">При отключении удаленного сеанса объект задания в текущем сеансе отключается от задания.</span><span class="sxs-lookup"><span data-stu-id="70552-372">If you disconnect the remote session, the job object in the current session is disconnected from the job.</span></span> <span data-ttu-id="70552-373">Объект задания содержит возвращенные результаты, но не получает новые результаты из задания в отключенном сеансе.</span><span class="sxs-lookup"><span data-stu-id="70552-373">The job object contains any results that were returned to it, but doesn't receive new results from the job in the disconnected session.</span></span>

<span data-ttu-id="70552-374">Если другой клиент подключается к сеансу, содержащему выполняемое задание, то результаты, которые были переданы исходному объекту задания в исходном сеансе, не будут доступны во вновь подключенном сеансе.</span><span class="sxs-lookup"><span data-stu-id="70552-374">If a different client connects to the session that contains the running job, the results that were delivered to the original job object in the original session aren't available in the newly connected session.</span></span> <span data-ttu-id="70552-375">После повторного подключения сеанса доступны только те результаты, которые не были доставлены в исходный объект задания.</span><span class="sxs-lookup"><span data-stu-id="70552-375">Only results that were not delivered to the original job object are available in the reconnected session.</span></span>

<span data-ttu-id="70552-376">Аналогично, если запустить сценарий в сеансе, а затем отключиться от него, все результаты, которые сценарий доставляет в сеанс до отключения, не будут доступны другому клиенту, который подключается к сеансу.</span><span class="sxs-lookup"><span data-stu-id="70552-376">Similarly, if you start a script in a session and then disconnect from the session, any results that the script delivers to the session before disconnecting aren't available to another client that connects to the session.</span></span>

<span data-ttu-id="70552-377">Чтобы предотвратить потери данных в сеансах, которые планируется отключить, используйте параметр **InDisconnectedSession** `Invoke-Command` командлета.</span><span class="sxs-lookup"><span data-stu-id="70552-377">To prevent data loss in sessions that you intend to disconnect, use the **InDisconnectedSession** parameter of the `Invoke-Command` cmdlet.</span></span> <span data-ttu-id="70552-378">Поскольку этот параметр запрещает возвращать результаты текущему сеансу, после повторного подключения сеанса доступны все результаты.</span><span class="sxs-lookup"><span data-stu-id="70552-378">Because this parameter prevents results from being returned to the current session, all results are available when the session is reconnected.</span></span>

<span data-ttu-id="70552-379">Можно также предотвратить потери данных с помощью `Invoke-Command` командлета для выполнения `Start-Job` команды в удаленном сеансе.</span><span class="sxs-lookup"><span data-stu-id="70552-379">You can also prevent data loss by using the `Invoke-Command` cmdlet to run a `Start-Job` command in the remote session.</span></span> <span data-ttu-id="70552-380">В этом случае объект задания создается в удаленном сеансе.</span><span class="sxs-lookup"><span data-stu-id="70552-380">In this case, the job object is created in the remote session.</span></span> <span data-ttu-id="70552-381">`Receive-PSSession`Для получения результатов задания нельзя использовать командлет.</span><span class="sxs-lookup"><span data-stu-id="70552-381">You can't use the `Receive-PSSession` cmdlet to get the job results.</span></span> <span data-ttu-id="70552-382">Вместо этого используйте `Connect-PSSession` командлет для подключения к сеансу, а затем используйте `Invoke-Command` командлет для выполнения `Receive-Job` команды в сеансе.</span><span class="sxs-lookup"><span data-stu-id="70552-382">Instead, use the `Connect-PSSession` cmdlet to connect to the session and then use the `Invoke-Command` cmdlet to run a `Receive-Job` command in the session.</span></span>

<span data-ttu-id="70552-383">Если сеанс, содержащий выполняющееся задание, отключен, а затем повторно подключен, исходный объект задания используется повторно только в том случае, если задание отключено и повторно подключено к тому же сеансу, а команда для повторного подключения не указывает новое имя задания.</span><span class="sxs-lookup"><span data-stu-id="70552-383">When a session that contains a running job is disconnected and then reconnected, the original job object is reused only if the job is disconnected and reconnected to the same session, and the command to reconnect doesn't specify a new job name.</span></span> <span data-ttu-id="70552-384">Если сеанс повторно подключается к другому клиентскому сеансу или указано новое имя задания, PowerShell создает новый объект задания для нового сеанса.</span><span class="sxs-lookup"><span data-stu-id="70552-384">If the session is reconnected to a different client session or a new job name is specified, PowerShell creates a new job object for the new session.</span></span>

<span data-ttu-id="70552-385">При отключении **PSSession** состояние сеанса отключается, а уровень доступности — нет.</span><span class="sxs-lookup"><span data-stu-id="70552-385">When you disconnect a **PSSession** , the session state is Disconnected and the availability is None.</span></span>

- <span data-ttu-id="70552-386">Значение свойства **State** определяется текущим сеансом.</span><span class="sxs-lookup"><span data-stu-id="70552-386">The value of the **State** property is relative to the current session.</span></span> <span data-ttu-id="70552-387">Значение disconnected означает, что **сеанс PSSession** не подключен к текущему сеансу.</span><span class="sxs-lookup"><span data-stu-id="70552-387">A value of Disconnected means that the **PSSession** isn't connected to the current session.</span></span> <span data-ttu-id="70552-388">Однако это не означает, что **сеанс PSSession** отключен от всех сеансов.</span><span class="sxs-lookup"><span data-stu-id="70552-388">However, it doesn't mean that the **PSSession** is disconnected from all sessions.</span></span> <span data-ttu-id="70552-389">Он может быть подключен к другому сеансу.</span><span class="sxs-lookup"><span data-stu-id="70552-389">It might be connected to a different session.</span></span>
  <span data-ttu-id="70552-390">Определить возможность подключения или повторного подключения к сеансу позволяет свойство **Availability** .</span><span class="sxs-lookup"><span data-stu-id="70552-390">To determine whether you can connect or reconnect to the session, use the **Availability** property.</span></span>
- <span data-ttu-id="70552-391">Если свойство **Availability** имеет значение None, подключиться к сеансу можно.</span><span class="sxs-lookup"><span data-stu-id="70552-391">An **Availability** value of None indicates that you can connect to the session.</span></span> <span data-ttu-id="70552-392">Значение занято указывает, что невозможно подключиться к сеансу **PSSession** , так как он подключен к другому сеансу.</span><span class="sxs-lookup"><span data-stu-id="70552-392">A value of Busy indicates that you can't connect to the **PSSession** because it's connected to another session.</span></span>
- <span data-ttu-id="70552-393">Дополнительные сведения о значениях свойства **State** в сеансах см. в разделе [РУНСПАЦЕСТАТЕ](/dotnet/api/system.management.automation.runspaces.runspacestate) в библиотеке MSDN.</span><span class="sxs-lookup"><span data-stu-id="70552-393">For more information about the values of the **State** property of sessions, see [RunspaceState](/dotnet/api/system.management.automation.runspaces.runspacestate) in the MSDN library.</span></span>
- <span data-ttu-id="70552-394">Дополнительные сведения о значениях свойства **Availability** сеансов см. в разделе [рунспацеаваилабилити](/dotnet/api/system.management.automation.runspaces.runspaceavailability).</span><span class="sxs-lookup"><span data-stu-id="70552-394">For more information about the values of the **Availability** property of sessions, see [RunspaceAvailability](/dotnet/api/system.management.automation.runspaces.runspaceavailability).</span></span>

## <span data-ttu-id="70552-395">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="70552-395">RELATED LINKS</span></span>

[<span data-ttu-id="70552-396">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="70552-396">about_PSSessions</span></span>](./About/about_PSSessions.md)

[<span data-ttu-id="70552-397">about_Remote</span><span class="sxs-lookup"><span data-stu-id="70552-397">about_Remote</span></span>](./About/about_Remote.md)

[<span data-ttu-id="70552-398">about_Remote_Disconnected_Sessions</span><span class="sxs-lookup"><span data-stu-id="70552-398">about_Remote_Disconnected_Sessions</span></span>](./About/about_Remote_Disconnected_Sessions.md)

[<span data-ttu-id="70552-399">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="70552-399">about_Session_Configurations</span></span>](./About/about_Session_Configurations.md)

[<span data-ttu-id="70552-400">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="70552-400">Connect-PSSession</span></span>](Connect-PSSession.md)

[<span data-ttu-id="70552-401">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="70552-401">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="70552-402">Exit-PSSession;</span><span class="sxs-lookup"><span data-stu-id="70552-402">Exit-PSSession</span></span>](Exit-PSSession.md)

[<span data-ttu-id="70552-403">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="70552-403">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="70552-404">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="70552-404">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="70552-405">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="70552-405">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="70552-406">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="70552-406">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="70552-407">New-PSTransportOption</span><span class="sxs-lookup"><span data-stu-id="70552-407">New-PSTransportOption</span></span>](New-PSTransportOption.md)

[<span data-ttu-id="70552-408">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="70552-408">Remove-PSSession</span></span>](Remove-PSSession.md)

