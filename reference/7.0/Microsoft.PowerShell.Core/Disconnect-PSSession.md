---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/disconnect-pssession?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disconnect-PSSession
ms.openlocfilehash: e4036924c45a5fd1b031fa33c8b9226aa5a66c30
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2020
ms.locfileid: "94347403"
---
# <span data-ttu-id="a2f75-103">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="a2f75-103">Disconnect-PSSession</span></span>

## <span data-ttu-id="a2f75-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="a2f75-104">SYNOPSIS</span></span>
<span data-ttu-id="a2f75-105">Отключает от сеанса.</span><span class="sxs-lookup"><span data-stu-id="a2f75-105">Disconnects from a session.</span></span>

## <span data-ttu-id="a2f75-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a2f75-106">SYNTAX</span></span>

### <span data-ttu-id="a2f75-107">Сеанс (значение по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="a2f75-107">Session (Default)</span></span>

```
Disconnect-PSSession [-Session] <PSSession[]> [-IdleTimeoutSec <Int32>]
 [-OutputBufferingMode <OutputBufferingMode>] [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="a2f75-108">Имя</span><span class="sxs-lookup"><span data-stu-id="a2f75-108">Name</span></span>

```
Disconnect-PSSession [-IdleTimeoutSec <Int32>] [-OutputBufferingMode <OutputBufferingMode>]
 [-ThrottleLimit <Int32>] -Name <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="a2f75-109">InstanceId</span><span class="sxs-lookup"><span data-stu-id="a2f75-109">InstanceId</span></span>

```
Disconnect-PSSession [-IdleTimeoutSec <Int32>] [-OutputBufferingMode <OutputBufferingMode>]
 [-ThrottleLimit <Int32>] -InstanceId <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="a2f75-110">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="a2f75-110">Id</span></span>

```
Disconnect-PSSession [-IdleTimeoutSec <Int32>] [-OutputBufferingMode <OutputBufferingMode>]
 [-ThrottleLimit <Int32>] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="a2f75-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a2f75-111">DESCRIPTION</span></span>

<span data-ttu-id="a2f75-112">`Disconnect-PSSession`Командлет отключает сеанс PowerShell (PSSession), например, запущенный с помощью `New-PSSession` командлета, из текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="a2f75-112">The `Disconnect-PSSession` cmdlet disconnects a PowerShell session ("PSSession"), such as one started by using the `New-PSSession` cmdlet, from the current session.</span></span> <span data-ttu-id="a2f75-113">В результате PSSession переходит в отключенное состояние.</span><span class="sxs-lookup"><span data-stu-id="a2f75-113">As a result, the PSSession is in a disconnected state.</span></span> <span data-ttu-id="a2f75-114">К отключенному сеансу PSSession можно подключиться из текущего или другого сеанса на локальном или другом компьютере.</span><span class="sxs-lookup"><span data-stu-id="a2f75-114">You can connect to the disconnected PSSession from the current session or from another session on the local computer or a different computer.</span></span>

<span data-ttu-id="a2f75-115">`Disconnect-PSSession`Командлет отключает только открытые PSSession, подключенные к текущему сеансу.</span><span class="sxs-lookup"><span data-stu-id="a2f75-115">The `Disconnect-PSSession` cmdlet disconnects only open PSSessions that are connected to the current session.</span></span> <span data-ttu-id="a2f75-116">`Disconnect-PSSession` не удается отключить разорванные или закрытые PSSession или интерактивный PSSession, запущенный с помощью `Enter-PSSession` командлета, и он не может отключить PSSession, подключенные к другим сеансам.</span><span class="sxs-lookup"><span data-stu-id="a2f75-116">`Disconnect-PSSession` cannot disconnect broken or closed PSSessions, or interactive PSSessions started by using the `Enter-PSSession` cmdlet, and it cannot disconnect PSSessions that are connected to other sessions.</span></span>

<span data-ttu-id="a2f75-117">Чтобы повторно подключиться к отключенному сеансу PSSession, `Connect-PSSession` Используйте `Receive-PSSession` командлеты или.</span><span class="sxs-lookup"><span data-stu-id="a2f75-117">To reconnect to a disconnected PSSession, use the `Connect-PSSession` or `Receive-PSSession` cmdlets.</span></span>

<span data-ttu-id="a2f75-118">При отключении PSSession, запущенные в этом сеансе команды выполняются до завершения или до окончания времени ожидания сеанса PSSession либо блокируются полным выходным буфером.</span><span class="sxs-lookup"><span data-stu-id="a2f75-118">When a PSSession is disconnected, the commands in the PSSession continue to run until they complete, unless the PSSession times out or the commands in the PSSession are blocked by a full output buffer.</span></span> <span data-ttu-id="a2f75-119">Чтобы изменить время ожидания простоя, используйте параметр **IdleTimeoutSec**.</span><span class="sxs-lookup"><span data-stu-id="a2f75-119">To change the idle timeout, use the **IdleTimeoutSec** parameter.</span></span> <span data-ttu-id="a2f75-120">Чтобы изменить режим буферизации вывода, используйте параметр **аутпутбуфферингмоде** . также можно использовать параметр **InDisconnectedSession** `Invoke-Command` командлета для выполнения команды в отключенном сеансе.</span><span class="sxs-lookup"><span data-stu-id="a2f75-120">To change the output buffering mode, use the **OutputBufferingMode** parameter You can also use the **InDisconnectedSession** parameter of the `Invoke-Command` cmdlet to run a command in a disconnected session.</span></span>

<span data-ttu-id="a2f75-121">Дополнительные сведения о функции отключенных сеансов см. в разделе [about_Remote_Disconnected_Sessions](./About/about_Remote_Disconnected_Sessions.md).</span><span class="sxs-lookup"><span data-stu-id="a2f75-121">For more information about the Disconnected Sessions feature, see [about_Remote_Disconnected_Sessions](./About/about_Remote_Disconnected_Sessions.md).</span></span>

<span data-ttu-id="a2f75-122">Этот командлет впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="a2f75-122">This cmdlet is introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="a2f75-123">Примеры</span><span class="sxs-lookup"><span data-stu-id="a2f75-123">EXAMPLES</span></span>

### <span data-ttu-id="a2f75-124">Пример 1. Отключение сеанса по имени</span><span class="sxs-lookup"><span data-stu-id="a2f75-124">Example 1 - Disconnect a session by name</span></span>

<span data-ttu-id="a2f75-125">Эта команда отключает сеанс UpdateSession на компьютере Server01 от текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="a2f75-125">This command disconnects the UpdateSession PSSession on the Server01 computer from the current session.</span></span> <span data-ttu-id="a2f75-126">Для идентификации сеанса PSSession в команде используется параметр **Name**.</span><span class="sxs-lookup"><span data-stu-id="a2f75-126">The command uses the **Name** parameter to identify the PSSession.</span></span>

```
PS> Disconnect-PSSession -Name UpdateSession
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
1  UpdateSession   Server01        Disconnected  Microsoft.PowerShell          None
```

<span data-ttu-id="a2f75-127">Выходные данные показывают, что попытка отключения оказалась успешной.</span><span class="sxs-lookup"><span data-stu-id="a2f75-127">The output shows that the attempt to disconnect was successful.</span></span> <span data-ttu-id="a2f75-128">Сеанс перешел в состояние Disconnected, а свойство Availability получило значение None — это значит, что сеанс не занят и к нему можно подключиться повторно.</span><span class="sxs-lookup"><span data-stu-id="a2f75-128">The session state is Disconnected and the Availability is None, which indicates that the session is not busy and can be reconnected.</span></span>

### <span data-ttu-id="a2f75-129">Пример 2. Отключение сеанса от определенного компьютера</span><span class="sxs-lookup"><span data-stu-id="a2f75-129">Example 2 - Disconnect a session from a specific computer</span></span>

<span data-ttu-id="a2f75-130">Эта команда отключает сеанс ITTask на компьютере Server12 от текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="a2f75-130">This command disconnects the ITTask PSSession on the Server12 computer from the current session.</span></span>
<span data-ttu-id="a2f75-131">Сеанс ITTask был создан в текущем сеансе и подключен к компьютеру Server12.</span><span class="sxs-lookup"><span data-stu-id="a2f75-131">The ITTask session was created in the current session and connects to the Server12 computer.</span></span> <span data-ttu-id="a2f75-132">Команда использует `Get-PSSession` командлет для получения сеанса и `Disconnect-PSSession` командлет для его отключения.</span><span class="sxs-lookup"><span data-stu-id="a2f75-132">The command uses the `Get-PSSession` cmdlet to get the session and the `Disconnect-PSSession` cmdlet to disconnect it.</span></span>

```
PS> Get-PSSession -ComputerName Server12 -Name ITTask |
  Disconnect-PSSession -OutputBufferingMode Drop -IdleTimeoutSec 86400
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
1  ITTask          Server12        Disconnected  ITTasks               None
```

<span data-ttu-id="a2f75-133">`Disconnect-PSSession`Команда использует параметр **аутпутбуфферингмоде** , чтобы установить режим вывода для **удаления**.</span><span class="sxs-lookup"><span data-stu-id="a2f75-133">The `Disconnect-PSSession` command uses the **OutputBufferingMode** parameter to set the output mode to **Drop**.</span></span> <span data-ttu-id="a2f75-134">Это гарантирует, что выполнения скрипта, запущенного в данном сеансе, будет продолжено, даже если выходной буфер сеанса заполнен.</span><span class="sxs-lookup"><span data-stu-id="a2f75-134">This setting ensures that the script that is running in the session can continue to run even if the session output buffer is full.</span></span> <span data-ttu-id="a2f75-135">Поскольку скрипт записывает выходные данные в отчет, находящийся в общей папке, другие выходные данные могут быть потеряны без последствий.</span><span class="sxs-lookup"><span data-stu-id="a2f75-135">Because the script writes its output to a report on a file share, other output can be lost without consequence.</span></span>

<span data-ttu-id="a2f75-136">Кроме того, команда включает параметр **IdleTimeoutSec** , увеличивающий время ожидания простоя сеанса до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="a2f75-136">The command also uses the **IdleTimeoutSec** parameter to extend the idle timeout of the session to 24 hours.</span></span> <span data-ttu-id="a2f75-137">Это позволит данному или другим администраторам восстановить подключение к сеансу, убедиться, что скрипт был выполнен, и устранить неполадки, если потребуется.</span><span class="sxs-lookup"><span data-stu-id="a2f75-137">This setting allows time for this administrator or other administrators to reconnect to the session to verify that the script ran and troubleshoot if needed.</span></span>

### <span data-ttu-id="a2f75-138">Пример 3. Использование нескольких PSSession на нескольких компьютерах</span><span class="sxs-lookup"><span data-stu-id="a2f75-138">Example 3 - Using multiple PSSessions on multiple computers</span></span>

<span data-ttu-id="a2f75-139">Эта серия команд показывает, как `Disconnect-PSSession` можно использовать командлет в корпоративном сценарии.</span><span class="sxs-lookup"><span data-stu-id="a2f75-139">This series of commands shows how the `Disconnect-PSSession` cmdlet might be used in an enterprise scenario.</span></span> <span data-ttu-id="a2f75-140">В данном случае новый специалист запускает скрипт в сеансе на удаленном компьютере и сталкивается с проблемой.</span><span class="sxs-lookup"><span data-stu-id="a2f75-140">In this case, a new technician starts a script in a session on a remote computer and runs into a problem.</span></span> <span data-ttu-id="a2f75-141">Специалист отключается от сеанса, чтобы более опытный менеджер смогу подключиться к сеансу и устранить проблему.</span><span class="sxs-lookup"><span data-stu-id="a2f75-141">The technician disconnects from the session so that a more experienced manager can connect to the session and resolve the problem.</span></span>

```
PS> $s = New-PSSession -ComputerName Srv1, Srv2, Srv30 -Name ITTask
PS> Invoke-Command $s -FilePath \\Server01\Scripts\Get-PatchStatus.ps1
PS> Get-PSSession -Name ITTask -ComputerName Srv1 | Disconnect-PSSession
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
1 ITTask           Srv1            Disconnected  Microsoft.PowerShell          None

PS> Get-PSSession -ComputerName Srv1, Srv2, Srv30 -Name ITTask
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Srv1            Disconnected  Microsoft.PowerShell          None
 2 ITTask          Srv2            Opened        Microsoft.PowerShell     Available
 3 ITTask          Srv30           Opened        Microsoft.PowerShell     Available

PS> Get-PSSession -ComputerName Srv1 -Name ITTask -Credential Domain01\User01
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Srv1            Disconnected  Microsoft.PowerShell          None

PS> $s = Connect-PSSession -ComputerName Srv1 -Name ITTask -Credential Domain01\User01
PS> Invoke-Command -Session $s {dir $home\Scripts\PatchStatusOutput.ps1}
PS> Invoke-Command -Session $s {mkdir $home\Scripts\PatchStatusOutput}
PS> Invoke-Command -Session $s -FilePath \\Server01\Scripts\Get-PatchStatus.ps1
PS> Disconnect-PSSession -Session $s
```

<span data-ttu-id="a2f75-142">Для начала специалист создает сеансы на нескольких удаленных компьютерах и запускает скрипт в каждом из этих сеансов.</span><span class="sxs-lookup"><span data-stu-id="a2f75-142">The technician begins by creating sessions on several remote computers and running a script in each session.</span></span> <span data-ttu-id="a2f75-143">Первая команда использует `New-PSSession` командлет для создания сеанса иттаск на трех удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="a2f75-143">The first command uses the `New-PSSession` cmdlet to create the ITTask session on three remote computers.</span></span> <span data-ttu-id="a2f75-144">Сеансы сохраняются в переменную $s.</span><span class="sxs-lookup"><span data-stu-id="a2f75-144">The command saves the sessions in the $s variable.</span></span> <span data-ttu-id="a2f75-145">Вторая команда использует параметр **FilePath** `Invoke-Command` командлета для выполнения скрипта в сеансах в переменной $s.</span><span class="sxs-lookup"><span data-stu-id="a2f75-145">The second command uses the **FilePath** parameter of the `Invoke-Command` cmdlet to run a script in the sessions in the $s variable.</span></span>

<span data-ttu-id="a2f75-146">Скрипт, запущенный на компьютере Srv1, вызывает непредвиденные ошибки.</span><span class="sxs-lookup"><span data-stu-id="a2f75-146">The script running on the Srv1 computer generates unexpected errors.</span></span> <span data-ttu-id="a2f75-147">Специалист обращается за помощью к менеджеру.</span><span class="sxs-lookup"><span data-stu-id="a2f75-147">The technician contacts his manager and asks for assistance.</span></span> <span data-ttu-id="a2f75-148">Руководитель направляет специалисту отключиться от сеанса, чтобы он мог исследовать его. Вторая команда использует `Get-PSSession` командлет для получения сеанса иттаск на компьютере Srv1 и `Disconnect-PSSession` командлет для его отключения.</span><span class="sxs-lookup"><span data-stu-id="a2f75-148">The manager directs the technician to disconnect from the session so he can investigate.The second command uses the `Get-PSSession` cmdlet to get the ITTask session on the Srv1 computer and the `Disconnect-PSSession` cmdlet to disconnect it.</span></span> <span data-ttu-id="a2f75-149">Эта команда не влияет на сеансы Иттаск на других компьютерах.</span><span class="sxs-lookup"><span data-stu-id="a2f75-149">This command does not affect the ITTask sessions on the other computers.</span></span>

<span data-ttu-id="a2f75-150">Третья команда использует `Get-PSSession` командлет для получения сеансов иттаск.</span><span class="sxs-lookup"><span data-stu-id="a2f75-150">The third command uses the `Get-PSSession` cmdlet to get the ITTask sessions.</span></span> <span data-ttu-id="a2f75-151">Выходные данные показывают, что команда отключения не повлияла на сеансы ITTask, созданные на компьютерах Srv2 и Srv30.</span><span class="sxs-lookup"><span data-stu-id="a2f75-151">The output shows that the ITTask sessions on the Srv2 and Srv30 computers were not affected by the command to disconnect.</span></span>

<span data-ttu-id="a2f75-152">Диспетчер выполняет вход на свой домашний компьютер, подключается к корпоративной сети, запускает PowerShell и использует `Get-PSSession` командлет для получения сеанса иттаск на компьютере Srv1.</span><span class="sxs-lookup"><span data-stu-id="a2f75-152">The manager logs on to his home computer, connects to his corporate network, starts PowerShell, and uses the `Get-PSSession` cmdlet to get the ITTask session on the Srv1 computer.</span></span> <span data-ttu-id="a2f75-153">Для доступа к сеансу он использует учетные данные специалиста.</span><span class="sxs-lookup"><span data-stu-id="a2f75-153">He uses the credentials of the technician to access the session.</span></span>

<span data-ttu-id="a2f75-154">Затем диспетчер использует `Connect-PSSession` командлет для подключения к сеансу иттаск на компьютере Srv1.</span><span class="sxs-lookup"><span data-stu-id="a2f75-154">Next, the manager uses the `Connect-PSSession` cmdlet to connect to the ITTask session on the Srv1 computer.</span></span> <span data-ttu-id="a2f75-155">Сеанс сохраняется в переменную $s.</span><span class="sxs-lookup"><span data-stu-id="a2f75-155">The command saves the session in the $s variable.</span></span>

<span data-ttu-id="a2f75-156">Диспетчер использует `Invoke-Command` командлет для выполнения некоторых диагностических команд в сеансе в `$s` переменной.</span><span class="sxs-lookup"><span data-stu-id="a2f75-156">The manager uses the `Invoke-Command` cmdlet to run some diagnostic commands in the session in the `$s` variable.</span></span> <span data-ttu-id="a2f75-157">Он понимает, что скрипт не выполняется, так как не может найти необходимый каталог.</span><span class="sxs-lookup"><span data-stu-id="a2f75-157">He recognizes that the script failed because it did not find a required directory.</span></span>
<span data-ttu-id="a2f75-158">Диспетчер использует `MkDir` функцию для создания каталога, а затем перезапускает `Get-PatchStatus.ps1` сценарий и отключает его от сеанса. Руководитель сообщает о своих возможностях, предлагая, что он повторно подключится к сеансу для выполнения задач, и попросит добавить в `Get-PatchStatus.ps1` сценарий команду, которая создает требуемый каталог, если он не существует.</span><span class="sxs-lookup"><span data-stu-id="a2f75-158">The manager uses the `MkDir` function to create the directory, and then he restarts the `Get-PatchStatus.ps1` script and disconnects from the session.The manager reports his findings to the technician, suggests that he reconnect to the session to complete the tasks, and asks him to add a command to the `Get-PatchStatus.ps1` script that creates the required directory if it does not exist.</span></span>

### <span data-ttu-id="a2f75-159">Пример 4. изменение значения времени ожидания для PSSession</span><span class="sxs-lookup"><span data-stu-id="a2f75-159">Example 4 - Change the timeout value for a PSSession</span></span>

<span data-ttu-id="a2f75-160">В этом примере показано, как скорректировать значение свойства **IdleTimeout** сеанса таким образом, чтобы сеанс можно было отключить.</span><span class="sxs-lookup"><span data-stu-id="a2f75-160">This example shows how to correct the value of the **IdleTimeout** property of a session so that it can be disconnected.</span></span>

<span data-ttu-id="a2f75-161">Свойство времени ожидания простоя имеет важное значение для отключенных сеансов, поскольку определяет, как долго отключенный сеанс будет храниться до удаления.</span><span class="sxs-lookup"><span data-stu-id="a2f75-161">The idle timeout property of a session is critical to disconnected sessions, because it determines how long a disconnected session is maintained before it is deleted.</span></span> <span data-ttu-id="a2f75-162">Время ожидания простоя можно настроить при создании сеанса, а также при отключении.</span><span class="sxs-lookup"><span data-stu-id="a2f75-162">You can set the idle timeout option when you create a session and when you disconnect it.</span></span> <span data-ttu-id="a2f75-163">Значения по умолчанию для времени ожидания простоя сеанса задаются в `$PSSessionOption` переменной предпочтений на локальном компьютере и в конфигурации сеанса на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a2f75-163">The default values for the idle timeout of a session are set in the `$PSSessionOption` preference variable on the local computer and in the session configuration on the remote computer.</span></span> <span data-ttu-id="a2f75-164">Значения, установленные для сеанса, превалируют над значениями, установленными в конфигурации сеанса, но не могут превышать квоты, предусмотренные конфигурацией сеанса, например, значением **MaxIdleTimeoutMs**.</span><span class="sxs-lookup"><span data-stu-id="a2f75-164">Values set for the session take precedence over values set in the session configuration, but session values cannot exceed quotas set in the session configuration, such as the **MaxIdleTimeoutMs** value.</span></span>

```
PS> $Timeout = New-PSSessionOption -IdleTimeout 172800000
PS> $s = New-PSSession -Computer Server01 -Name ITTask -SessionOption $Timeout
PS> Disconnect-PSSession -Session $s
Disconnect-PSSession : The session ITTask cannot be disconnected because the specified
idle timeout value 172800(seconds) is either greater than the server maximum allowed
43200 (seconds) or less that the minimum allowed60(seconds).  Choose an idle time out
value that is within the allowed range and try again.

PS> Invoke-Command -ComputerName Server01 {Get-PSSessionConfiguration Microsoft.PowerShell} |
 Format-List -Property *

Architecture                  : 64
Filename                      : %windir%\system32\pwrshplugin.dll
ResourceUri                   : http://schemas.microsoft.com/powershell/microsoft.powershell
MaxConcurrentCommandsPerShell : 1000
UseSharedProcess              : false
ProcessIdleTimeoutSec         : 0
xmlns                         : http://schemas.microsoft.com/wbem/wsman/1/config/PluginConfiguration
MaxConcurrentUsers            : 5
lang                          : en-US
SupportsOptions               : true
ExactMatch                    : true
RunAsUser                     :
IdleTimeoutms                 : 7200000
PSVersion                     : 3.0
OutputBufferingMode           : Block
AutoRestart                   : false
SecurityDescriptorSddl        : O:NSG:BAD:P(A;;GA;;;BA)S:P(AU;FA;GA;;;WD)(AU;SA;GXGW;;;WD)
MaxMemoryPerShellMB           : 1024
MaxIdleTimeoutms              : 2147483647
Uri                           : http://schemas.microsoft.com/powershell/microsoft.powershell
SDKVersion                    : 2
Name                          : microsoft.powershell
XmlRenderingType              : text
Capability                    : {Shell}
RunAsPassword                 :
MaxProcessesPerShell          : 15
ParentResourceUri             : http://schemas.microsoft.com/powershell/microsoft.powershell
Enabled                       : true
MaxShells                     : 25
MaxShellsPerUser              : 25
Permission                    : BUILTIN\Administrators AccessAllowed
PSComputerName                : localhost
RunspaceId                    : aea84310-6dbf-4c21-90ac-13980039925a
PSShowComputerName            : True


PS> $s.Runspace.ConnectionInfo
ConnectionUri                     : http://Server01/wsman
ComputerName                      : Server01
Scheme                            : http
Port                              : 80
AppName                           : /wsman
Credential                        :
ShellUri                          : http://schemas.microsoft.com/powershell/Microsoft.PowerShell
AuthenticationMechanism           : Default
CertificateThumbprint             :
MaximumConnectionRedirectionCount : 5
MaximumReceivedDataSizePerCommand :
MaximumReceivedObjectSize         : 209715200
UseCompression                    : True
NoMachineProfile                  : False
ProxyAccessType                   : None
ProxyAuthentication               : Negotiate
ProxyCredential                   :
SkipCACheck                       : False
SkipCNCheck                       : False
SkipRevocationCheck               : False
NoEncryption                      : False
UseUTF16                          : False
OutputBufferingMode               : Drop
IncludePortInSPN                  : False
Culture                           : en-US
UICulture                         : en-US
OpenTimeout                       : 180000
CancelTimeout                     : 60000
OperationTimeout                  : 180000
IdleTimeout                       : 172800000

PS> Disconnect-PSSession $s -IdleTimeoutSec 43200
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 4 ITTask          Server01        Disconnected  Microsoft.PowerShell          None

PS> $s.Runspace.ConnectionInfo.IdleTimeout
43200000
```

<span data-ttu-id="a2f75-165">Первая команда использует `New-PSSessionOption` командлет для создания объекта параметра сеанса.</span><span class="sxs-lookup"><span data-stu-id="a2f75-165">The first command uses the `New-PSSessionOption` cmdlet to create a session option object.</span></span> <span data-ttu-id="a2f75-166">Она включает параметр **IdleTimeout** , определяющий время ожидания простоя, равное 48 часам (172 800 000 миллисекундам).</span><span class="sxs-lookup"><span data-stu-id="a2f75-166">It uses the **IdleTimeout** parameter to set an idle timeout of 48 hours (172800000 milliseconds).</span></span> <span data-ttu-id="a2f75-167">Объект параметров сеанса сохраняется в переменную $Timeout .</span><span class="sxs-lookup"><span data-stu-id="a2f75-167">The command saves the session option object in the $Timeout variable.</span></span>

<span data-ttu-id="a2f75-168">Вторая команда использует `New-PSSession` командлет для создания сеанса иттаск на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="a2f75-168">The second command uses the `New-PSSession` cmdlet to create the ITTask session on the Server01 computer.</span></span> <span data-ttu-id="a2f75-169">Сеанс сохраняется в переменную $s.</span><span class="sxs-lookup"><span data-stu-id="a2f75-169">The command save the session in the $s variable.</span></span> <span data-ttu-id="a2f75-170">Параметр **SessionOption** получает значение 48 часов в соответствии со временем ожидания простоя, указанным в переменной $Timeout.</span><span class="sxs-lookup"><span data-stu-id="a2f75-170">The value of the **SessionOption** parameter is the 48-hour idle timeout in the $Timeout variable.</span></span>

<span data-ttu-id="a2f75-171">Третья команда отключает сеанс ITTask из переменной $s.</span><span class="sxs-lookup"><span data-stu-id="a2f75-171">The third command disconnects the ITTask session in the $s variable.</span></span> <span data-ttu-id="a2f75-172">Команда завершается ошибкой, так как превышает квоту **MaxIdleTimeoutMs** для времени ожидания простоя, указанную в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="a2f75-172">The command fails because the idle timeout value of the session exceeds the **MaxIdleTimeoutMs** quota in the session configuration.</span></span> <span data-ttu-id="a2f75-173">Поскольку значение времени ожидания простоя не используется, пока сеанс не будет отключен, это нарушение может оставаться незамеченными, пока сеанс еще используется.</span><span class="sxs-lookup"><span data-stu-id="a2f75-173">Because the idle timeout is not used until the session is disconnected, this violation can go undetected while the session is in use.</span></span>

<span data-ttu-id="a2f75-174">Четвертая команда использует `Invoke-Command` командлет для выполнения `Get-PSSessionConfiguration` команды для конфигурации сеанса Microsoft. PowerShell на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="a2f75-174">The fourth command uses the `Invoke-Command` cmdlet to run a `Get-PSSessionConfiguration` command for the Microsoft.PowerShell session configuration on the Server01 computer.</span></span> <span data-ttu-id="a2f75-175">Команда использует `Format-List` командлет для вывода всех свойств конфигурации сеанса в списке. Выходные данные показывают, что свойство **максидлетимеаутмс** , устанавливающее максимально допустимое значение **IdleTimeout** для сеансов, использующих конфигурацию сеанса, составляет 43200000 миллисекунд (12 часов).</span><span class="sxs-lookup"><span data-stu-id="a2f75-175">The command uses the `Format-List` cmdlet to display all properties of the session configuration in a list.The output shows that the **MaxIdleTimeoutMS** property, which establishes the maximum permitted **IdleTimeout** value for sessions that use the session configuration, is 43200000 milliseconds (12 hours).</span></span>

<span data-ttu-id="a2f75-176">Пятая команда возвращает значения параметров для сеанса, сохраненного в переменную $s.</span><span class="sxs-lookup"><span data-stu-id="a2f75-176">The fifth command gets the session option values of the session in the $s variable.</span></span> <span data-ttu-id="a2f75-177">Значения многих параметров сеанса являются свойствами свойства **ConnectionInfo** свойства **пространства выполнения** сеанса. Выходные данные показывают, что значение свойства **IdleTimeout** сеанса составляет 172800000 миллисекунд (48 часа), что нарушает квоту **максидлетимеаутмс** в 12 часов в конфигурации сеанса. Чтобы устранить этот конфликт, можно использовать параметр **configurationName** , чтобы выбрать другую конфигурацию сеанса или использовать параметр **IdleTimeout** для сокращения времени ожидания простоя сеанса.</span><span class="sxs-lookup"><span data-stu-id="a2f75-177">The values of many session options are properties of the **ConnectionInfo** property of the **Runspace** property of the session.The output shows that the value of the **IdleTimeout** property of the session is 172800000 milliseconds (48 hours), which violates the **MaxIdleTimeoutMs** quota of 12 hours in the session configuration.To resolve this conflict, you can use the **ConfigurationName** parameter to select a different session configuration or use the **IdleTimeout** parameter to reduce the idle timeout of the session.</span></span>

<span data-ttu-id="a2f75-178">Шестая команда отключает сеанс.</span><span class="sxs-lookup"><span data-stu-id="a2f75-178">The sixth command disconnects the session.</span></span> <span data-ttu-id="a2f75-179">С помощью параметра **IdleTimeoutSec** она устанавливает время ожидания простоя, равное 12 часовому максимуму.</span><span class="sxs-lookup"><span data-stu-id="a2f75-179">It uses the **IdleTimeoutSec** parameter to set the idle timeout to the 12-hour maximum.</span></span>

<span data-ttu-id="a2f75-180">Седьмая команда получает значение свойства **IdleTimeout** отключенного сеанса, которое измеряется в миллисекундах.</span><span class="sxs-lookup"><span data-stu-id="a2f75-180">The seventh command gets the value of the **IdleTimeout** property of the disconnected session, which is measured in milliseconds.</span></span> <span data-ttu-id="a2f75-181">Выходные данные подтверждают, что команда выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="a2f75-181">The output confirms that the command was successful.</span></span>

## <span data-ttu-id="a2f75-182">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a2f75-182">PARAMETERS</span></span>

### <span data-ttu-id="a2f75-183">-Id</span><span class="sxs-lookup"><span data-stu-id="a2f75-183">-Id</span></span>

<span data-ttu-id="a2f75-184">Отключается от сеансов с указанным идентификатором сеанса.</span><span class="sxs-lookup"><span data-stu-id="a2f75-184">Disconnects from sessions with the specified session ID.</span></span> <span data-ttu-id="a2f75-185">Введите один или несколько идентификаторов (разделенные запятыми) или укажите диапазон идентификаторов, используя соответствующий оператор (.).</span><span class="sxs-lookup"><span data-stu-id="a2f75-185">Type one or more IDs (separated by commas), or use the range operator (..) to specify a range of IDs.</span></span>

<span data-ttu-id="a2f75-186">Чтобы получить идентификатор сеанса, используйте `Get-PSSession` командлет.</span><span class="sxs-lookup"><span data-stu-id="a2f75-186">To get the ID of a session, use the `Get-PSSession` cmdlet.</span></span> <span data-ttu-id="a2f75-187">Идентификатор экземпляра хранится в свойстве **ID** сеанса.</span><span class="sxs-lookup"><span data-stu-id="a2f75-187">The instance ID is stored in the **ID** property of the session.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a2f75-188">-Идлетимеаутсек</span><span class="sxs-lookup"><span data-stu-id="a2f75-188">-IdleTimeoutSec</span></span>

<span data-ttu-id="a2f75-189">Изменяет значение времени ожидания простоя для отключенного сеанса PSSession.</span><span class="sxs-lookup"><span data-stu-id="a2f75-189">Changes the idle timeout value of the disconnected PSSession.</span></span> <span data-ttu-id="a2f75-190">Введите значение в секундах.</span><span class="sxs-lookup"><span data-stu-id="a2f75-190">Enter a value in seconds.</span></span> <span data-ttu-id="a2f75-191">Минимальное значение — 60 секунд (1 минута).</span><span class="sxs-lookup"><span data-stu-id="a2f75-191">The minimum value is 60 (1 minute).</span></span>

<span data-ttu-id="a2f75-192">Время ожидания простоя определяет, как долго отключенный сеанс PSSession будет храниться на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a2f75-192">The idle timeout determines how long the disconnected PSSession is maintained on the remote computer.</span></span> <span data-ttu-id="a2f75-193">По истечении времени ожидания сеанс PSSession будет удален.</span><span class="sxs-lookup"><span data-stu-id="a2f75-193">When the timeout expires, the PSSession is deleted.</span></span>

<span data-ttu-id="a2f75-194">Время простоя отключенных сеансов PSSession отсчитывается с момента их отключения, даже если в отключенном сеансе выполняются команды.</span><span class="sxs-lookup"><span data-stu-id="a2f75-194">Disconnected PSSessions are considered to be idle from the moment that they are disconnected, even if commands are running in the disconnected session.</span></span>

<span data-ttu-id="a2f75-195">Время ожидания простоя сеанса по умолчанию определяется значением свойства **IdleTimeoutMs** конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="a2f75-195">The default value for the idle timeout of a session is set by the value of the **IdleTimeoutMs** property of the session configuration.</span></span> <span data-ttu-id="a2f75-196">Значение по умолчанию составляет 7200000 миллисекунд (2 часа).</span><span class="sxs-lookup"><span data-stu-id="a2f75-196">The default value is 7200000 milliseconds (2 hours).</span></span>

<span data-ttu-id="a2f75-197">Значение этого параметра превалирует над значением свойства **IdleTimeout** привилегированной переменной $PSSessionOption и значением времени ожидания простоя по умолчанию, предусмотренным конфигурацией сеанса.</span><span class="sxs-lookup"><span data-stu-id="a2f75-197">The value of this parameter takes precedence over the value of the **IdleTimeout** property of the $PSSessionOption preference variable and the default idle timeout value in the session configuration.</span></span> <span data-ttu-id="a2f75-198">Тем не менее, это значение не может превышать значение свойства **MaxIdleTimeoutMs** конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="a2f75-198">However, this value cannot exceed the value of the **MaxIdleTimeoutMs** property of the session configuration.</span></span> <span data-ttu-id="a2f75-199">Значение свойства **MaxIdleTimeoutMs** по умолчанию составляет 12 часов (43200000 миллисекунд).</span><span class="sxs-lookup"><span data-stu-id="a2f75-199">The default value of **MaxIdleTimeoutMs** is 12 hours (43200000 milliseconds).</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 60
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a2f75-200">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="a2f75-200">-InstanceId</span></span>

<span data-ttu-id="a2f75-201">Отключается от сеансов с указанными идентификаторами экземпляров.</span><span class="sxs-lookup"><span data-stu-id="a2f75-201">Disconnects from sessions with the specified instance IDs.</span></span>

<span data-ttu-id="a2f75-202">Идентификатор экземпляра — это GUID, однозначно определяющий сеанс на локальном или удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a2f75-202">The instance ID is a GUID that uniquely identifies a session on a local or remote computer.</span></span> <span data-ttu-id="a2f75-203">Идентификатор экземпляра уникален даже для нескольких сеансов на различных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="a2f75-203">The instance ID is unique, even across multiple sessions on multiple computers.</span></span>

<span data-ttu-id="a2f75-204">Чтобы получить идентификатор экземпляра сеанса, используйте `Get-PSSession` командлет.</span><span class="sxs-lookup"><span data-stu-id="a2f75-204">To get the instance ID of a session, use the `Get-PSSession` cmdlet.</span></span> <span data-ttu-id="a2f75-205">Идентификатор экземпляра хранится в свойстве **InstanceId** сеанса.</span><span class="sxs-lookup"><span data-stu-id="a2f75-205">The instance ID is stored in the **InstanceID** property of the session.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: InstanceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a2f75-206">-Name</span><span class="sxs-lookup"><span data-stu-id="a2f75-206">-Name</span></span>

<span data-ttu-id="a2f75-207">Отключается от сеансов с указанными понятными именами.</span><span class="sxs-lookup"><span data-stu-id="a2f75-207">Disconnects from sessions with the specified friendly names.</span></span> <span data-ttu-id="a2f75-208">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="a2f75-208">Wildcards are permitted.</span></span>

<span data-ttu-id="a2f75-209">Чтобы получить понятное имя сеанса, используйте `Get-PSSession` командлет.</span><span class="sxs-lookup"><span data-stu-id="a2f75-209">To get the friendly name of a session, use the `Get-PSSession` cmdlet.</span></span> <span data-ttu-id="a2f75-210">Понятное имя хранится в свойстве **Name** сеанса.</span><span class="sxs-lookup"><span data-stu-id="a2f75-210">The friendly name is stored in the **Name** property of the session.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="a2f75-211">-Session</span><span class="sxs-lookup"><span data-stu-id="a2f75-211">-Session</span></span>

<span data-ttu-id="a2f75-212">Отключается от указанных сеансов PSSession.</span><span class="sxs-lookup"><span data-stu-id="a2f75-212">Disconnects from the specified PSSessions.</span></span> <span data-ttu-id="a2f75-213">Введите объекты PSSession, например те, которые `New-PSSession` возвращает командлет.</span><span class="sxs-lookup"><span data-stu-id="a2f75-213">Enter PSSession objects, such as those that the `New-PSSession` cmdlet returns.</span></span> <span data-ttu-id="a2f75-214">Объект PSSession также можно передать в `Disconnect-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="a2f75-214">You can also pipe a PSSession object to `Disconnect-PSSession`.</span></span>

<span data-ttu-id="a2f75-215">`Get-PSSession`Командлет может получить все PSSession, которые завершаются на удаленном компьютере, включая PSSession, которые отключены и PSSession, подключенные к другим сеансам на других компьютерах.</span><span class="sxs-lookup"><span data-stu-id="a2f75-215">The `Get-PSSession` cmdlet can get all PSSessions that terminate at a remote computer, including PSSessions that are disconnected and PSSessions that are connected to other sessions on other computers.</span></span> <span data-ttu-id="a2f75-216">`Disconnect-PSSession` отключает только сеанс PSSession, подключенный к текущему сеансу.</span><span class="sxs-lookup"><span data-stu-id="a2f75-216">`Disconnect-PSSession` disconnects only PSSession that are connected to the current session.</span></span> <span data-ttu-id="a2f75-217">Если передать другие PSSession в `Disconnect-PSSession` , `Disconnect-PSSession` команда завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="a2f75-217">If you pipe other PSSessions to `Disconnect-PSSession`, the `Disconnect-PSSession` command fails.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession[]
Parameter Sets: Session
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="a2f75-218">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="a2f75-218">-ThrottleLimit</span></span>

<span data-ttu-id="a2f75-219">Задает ограничение регулирования для `Disconnect-PSSession` команды.</span><span class="sxs-lookup"><span data-stu-id="a2f75-219">Sets the throttle limit for the `Disconnect-PSSession` command.</span></span>

<span data-ttu-id="a2f75-220">Предел регулирования — это максимальное количество одновременных подключений, которые могут быть установлены для выполнения этой команды.</span><span class="sxs-lookup"><span data-stu-id="a2f75-220">The throttle limit is the maximum number of concurrent connections that can be established to run this command.</span></span> <span data-ttu-id="a2f75-221">Если этот параметр не указан или имеет значение 0, используется значение по умолчанию — 32.</span><span class="sxs-lookup"><span data-stu-id="a2f75-221">If you omit this parameter or enter a value of 0, the default value, 32, is used.</span></span>

<span data-ttu-id="a2f75-222">Предел регулирования применяется только к текущему командлету, а не к сеансу или компьютеру.</span><span class="sxs-lookup"><span data-stu-id="a2f75-222">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a2f75-223">-Аутпутбуфферингмоде</span><span class="sxs-lookup"><span data-stu-id="a2f75-223">-OutputBufferingMode</span></span>

<span data-ttu-id="a2f75-224">Определяет порядок управления выходным потоком команды в отключенном сеансе при заполнении .</span><span class="sxs-lookup"><span data-stu-id="a2f75-224">Determines how command output is managed in the disconnected session when the output buffer is full.</span></span> <span data-ttu-id="a2f75-225">Значение по умолчанию — **Block**.</span><span class="sxs-lookup"><span data-stu-id="a2f75-225">The default value is **Block**.</span></span>

<span data-ttu-id="a2f75-226">Если команда в отключенном сеансе возвращает данные и заполняет выходной буфер, значение этого параметра определяет, продолжится ли выполнение этой команды в отключенном сеансе.</span><span class="sxs-lookup"><span data-stu-id="a2f75-226">If the command in the disconnected session is returning output and the output buffer fills, the value of this parameter effectively determines whether the command continues to run while the session is disconnected.</span></span> <span data-ttu-id="a2f75-227">Значение **Block** приостанавливает команду до повторного подключения к сеансу.</span><span class="sxs-lookup"><span data-stu-id="a2f75-227">A value of **Block** suspends the command until the session is reconnected.</span></span> <span data-ttu-id="a2f75-228">Значение **Drop** позволяет завершить выполнение команды, несмотря на возможную потерю данных.</span><span class="sxs-lookup"><span data-stu-id="a2f75-228">A value of **Drop** allows the command to complete, although data might be lost.</span></span> <span data-ttu-id="a2f75-229">При использовании значения **Drop** выходные данные команды необходимо перенаправить в какой-либо файл на диске.</span><span class="sxs-lookup"><span data-stu-id="a2f75-229">When using the **Drop** value, redirect the command output to a file on disk.</span></span>

<span data-ttu-id="a2f75-230">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="a2f75-230">Valid values are:</span></span>

- <span data-ttu-id="a2f75-231">**Блокировать** : когда выходной буфер полон, выполнение приостанавливается до тех пор, пока буфер не будет очищен.</span><span class="sxs-lookup"><span data-stu-id="a2f75-231">**Block** : When the output buffer is full, execution is suspended until the buffer is clear.</span></span>
- <span data-ttu-id="a2f75-232">**Drop** : когда выходной буфер полон, выполнение продолжится.</span><span class="sxs-lookup"><span data-stu-id="a2f75-232">**Drop** : When the output buffer is full, execution continues.</span></span> <span data-ttu-id="a2f75-233">Новые выходные данные сохраняются вместо наиболее старых.</span><span class="sxs-lookup"><span data-stu-id="a2f75-233">As new output is saved, the oldest output is discarded.</span></span>
- <span data-ttu-id="a2f75-234">**Нет** : режим буферизации вывода не указан.</span><span class="sxs-lookup"><span data-stu-id="a2f75-234">**None** : No output buffering mode is specified.</span></span> <span data-ttu-id="a2f75-235">Значение свойства **OutputBufferingMode** конфигурации сеанса используется для отключенного сеанса.</span><span class="sxs-lookup"><span data-stu-id="a2f75-235">The value of the **OutputBufferingMode** property of the session configuration is used for the disconnected session.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.OutputBufferingMode
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Block
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a2f75-236">-Confirm</span><span class="sxs-lookup"><span data-stu-id="a2f75-236">-Confirm</span></span>

<span data-ttu-id="a2f75-237">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="a2f75-237">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="a2f75-238">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="a2f75-238">-WhatIf</span></span>

<span data-ttu-id="a2f75-239">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="a2f75-239">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="a2f75-240">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="a2f75-240">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="a2f75-241">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="a2f75-241">CommonParameters</span></span>

<span data-ttu-id="a2f75-242">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a2f75-242">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a2f75-243">См. сведения в разделе [about_CommonParameters](./About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="a2f75-243">For more information, see [about_CommonParameters](./About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="a2f75-244">Входные данные</span><span class="sxs-lookup"><span data-stu-id="a2f75-244">INPUTS</span></span>

### <span data-ttu-id="a2f75-245">System.Management.Automation.Runspaces.PSSession</span><span class="sxs-lookup"><span data-stu-id="a2f75-245">System.Management.Automation.Runspaces.PSSession</span></span>

<span data-ttu-id="a2f75-246">Можно передать сеанс в `Disconnect-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="a2f75-246">You can pipe a session to `Disconnect-PSSession`.</span></span>

## <span data-ttu-id="a2f75-247">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="a2f75-247">OUTPUTS</span></span>

### <span data-ttu-id="a2f75-248">System.Management.Automation.Runspaces.PSSession</span><span class="sxs-lookup"><span data-stu-id="a2f75-248">System.Management.Automation.Runspaces.PSSession</span></span>

<span data-ttu-id="a2f75-249">`Disconnect-PSSession` Возвращает объект, представляющий сеанс, который он отключил.</span><span class="sxs-lookup"><span data-stu-id="a2f75-249">`Disconnect-PSSession` returns an object that represents the session that it disconnected.</span></span>

## <span data-ttu-id="a2f75-250">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="a2f75-250">NOTES</span></span>

<span data-ttu-id="a2f75-251">Этот командлет доступен только на платформах Windows.</span><span class="sxs-lookup"><span data-stu-id="a2f75-251">This cmdlet is only available on Windows platforms.</span></span>

- <span data-ttu-id="a2f75-252">`Disconnect-PSSession`Командлет работает, только если на локальном и удаленном компьютерах работает PowerShell 3,0 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="a2f75-252">The `Disconnect-PSSession` cmdlet works only when the local and remote computers are running PowerShell 3.0 or later.</span></span>
- <span data-ttu-id="a2f75-253">При использовании `Disconnect-PSSession` командлета в отключенном сеансе команда не оказывает влияния на сеанс и не создает ошибок.</span><span class="sxs-lookup"><span data-stu-id="a2f75-253">If you use the `Disconnect-PSSession` cmdlet on a disconnected session, the command has no effect on the session and it does not generate errors.</span></span>
- <span data-ttu-id="a2f75-254">Повторно подключиться к отключенному сеансу замыкания на себя с интерактивным маркером безопасности, созданным с помощью параметра **EnableNetworkAccess** , можно только с компьютера, на котором этот сеанс был создан.</span><span class="sxs-lookup"><span data-stu-id="a2f75-254">Disconnected loopback sessions with interactive security tokens (those created with the **EnableNetworkAccess** parameter) can be reconnected only from the computer on which the session was created.</span></span> <span data-ttu-id="a2f75-255">Это ограничение защищает компьютер от вредоносного доступа.</span><span class="sxs-lookup"><span data-stu-id="a2f75-255">This restriction protects the computer from malicious access.</span></span>
- <span data-ttu-id="a2f75-256">Отключенный сеанс PSSession переходит в состояние **Disconnected** и получает доступность **None**.</span><span class="sxs-lookup"><span data-stu-id="a2f75-256">When you disconnect a PSSession, the session state is **Disconnected** and the availability is **None**.</span></span>

  <span data-ttu-id="a2f75-257">Значение свойства **State** определяется текущим сеансом.</span><span class="sxs-lookup"><span data-stu-id="a2f75-257">The value of the **State** property is relative to the current session.</span></span> <span data-ttu-id="a2f75-258">Таким образом, значение **Disconnected** показывает, что сеанс PSSession не подключен к текущему сеансу.</span><span class="sxs-lookup"><span data-stu-id="a2f75-258">Therefore, a value of **Disconnected** means that the PSSession is not connected to the current session.</span></span> <span data-ttu-id="a2f75-259">При этом оно не означает, что сеанс PSSession отключен от всех сеансов.</span><span class="sxs-lookup"><span data-stu-id="a2f75-259">However, it does not mean that the PSSession is disconnected from all sessions.</span></span> <span data-ttu-id="a2f75-260">Он может быть подключен к другому сеансу.</span><span class="sxs-lookup"><span data-stu-id="a2f75-260">It might be connected to a different session.</span></span> <span data-ttu-id="a2f75-261">Определить возможность подключения или повторного подключения к сеансу позволяет свойство **Availability**.</span><span class="sxs-lookup"><span data-stu-id="a2f75-261">To determine whether you can connect or reconnect to the session, use the **Availability** property.</span></span>

  <span data-ttu-id="a2f75-262">Если свойство **Availability** имеет значение **None** , подключиться к сеансу можно.</span><span class="sxs-lookup"><span data-stu-id="a2f75-262">An **Availability** value of **None** indicates that you can connect to the session.</span></span> <span data-ttu-id="a2f75-263">Значение **Busy** показывает, что подключиться сеансу к PSSession нельзя, так как он подключен к другому сеансу.</span><span class="sxs-lookup"><span data-stu-id="a2f75-263">A value of **Busy** indicates that you cannot connect to the PSSession because it is connected to another session.</span></span>

  <span data-ttu-id="a2f75-264">Дополнительные сведения о значениях свойства **State** в сеансах см. в разделе [рунспацестате enumeration](/dotnet/api/system.management.automation.runspaces.runspacestate).</span><span class="sxs-lookup"><span data-stu-id="a2f75-264">For more information about the values of the **State** property of sessions, see [RunspaceState Enumeration](/dotnet/api/system.management.automation.runspaces.runspacestate).</span></span>

  <span data-ttu-id="a2f75-265">Дополнительные сведения о значениях свойства **Availability** сеансов см. в разделе [рунспацеаваилабилити enumeration](/dotnet/api/system.management.automation.runspaces.runspaceavailability).</span><span class="sxs-lookup"><span data-stu-id="a2f75-265">For more information about the values of the **Availability** property of sessions, see [RunspaceAvailability Enumeration](/dotnet/api/system.management.automation.runspaces.runspaceavailability).</span></span>

## <span data-ttu-id="a2f75-266">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="a2f75-266">RELATED LINKS</span></span>

[<span data-ttu-id="a2f75-267">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="a2f75-267">Connect-PSSession</span></span>](Connect-PSSession.md)

[<span data-ttu-id="a2f75-268">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="a2f75-268">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="a2f75-269">Exit-PSSession;</span><span class="sxs-lookup"><span data-stu-id="a2f75-269">Exit-PSSession</span></span>](Exit-PSSession.md)

[<span data-ttu-id="a2f75-270">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="a2f75-270">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="a2f75-271">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="a2f75-271">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="a2f75-272">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="a2f75-272">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="a2f75-273">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="a2f75-273">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="a2f75-274">New-PSTransportOption</span><span class="sxs-lookup"><span data-stu-id="a2f75-274">New-PSTransportOption</span></span>](New-PSTransportOption.md)

[<span data-ttu-id="a2f75-275">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="a2f75-275">Receive-PSSession</span></span>](Receive-PSSession.md)

[<span data-ttu-id="a2f75-276">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="a2f75-276">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="a2f75-277">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="a2f75-277">Remove-PSSession</span></span>](Remove-PSSession.md)

[<span data-ttu-id="a2f75-278">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="a2f75-278">about_PSSessions</span></span>](About/about_PSSessions.md)

[<span data-ttu-id="a2f75-279">about_Remote</span><span class="sxs-lookup"><span data-stu-id="a2f75-279">about_Remote</span></span>](About/about_Remote.md)

[<span data-ttu-id="a2f75-280">about_Remote_Disconnected_Sessions</span><span class="sxs-lookup"><span data-stu-id="a2f75-280">about_Remote_Disconnected_Sessions</span></span>](About/about_Remote_Disconnected_Sessions.md)
