---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 5/15/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/connect-pssession?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Connect-PSSession
ms.openlocfilehash: 65f6544835562e4006319b5bd8d9fc9404f75e1a
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "93230062"
---
# <span data-ttu-id="638a0-103">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="638a0-103">Connect-PSSession</span></span>

## <span data-ttu-id="638a0-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="638a0-104">SYNOPSIS</span></span>
<span data-ttu-id="638a0-105">Выполняет повторное подключение к отключенным сеансам.</span><span class="sxs-lookup"><span data-stu-id="638a0-105">Reconnects to disconnected sessions.</span></span>

## <span data-ttu-id="638a0-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="638a0-106">SYNTAX</span></span>

### <span data-ttu-id="638a0-107">Имя (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="638a0-107">Name (Default)</span></span>

```
Connect-PSSession -Name <String[]> [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="638a0-108">Сеанс</span><span class="sxs-lookup"><span data-stu-id="638a0-108">Session</span></span>

```
Connect-PSSession [-Session] <PSSession[]> [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="638a0-109">компутернамегуид</span><span class="sxs-lookup"><span data-stu-id="638a0-109">ComputerNameGuid</span></span>

```
Connect-PSSession -ComputerName <String[]> [-ApplicationName <String>] [-ConfigurationName <String>]
 -InstanceId <Guid[]> [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [-Port <Int32>] [-UseSSL] [-SessionOption <PSSessionOption>]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="638a0-110">ИмяКомпьютера</span><span class="sxs-lookup"><span data-stu-id="638a0-110">ComputerName</span></span>

```
Connect-PSSession -ComputerName <String[]> [-ApplicationName <String>] [-ConfigurationName <String>]
 [-Name <String[]>] [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [-Port <Int32>] [-UseSSL] [-SessionOption <PSSessionOption>]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="638a0-111">коннектионуригуид</span><span class="sxs-lookup"><span data-stu-id="638a0-111">ConnectionUriGuid</span></span>

```
Connect-PSSession [-ConfigurationName <String>] [-ConnectionUri] <Uri[]> [-AllowRedirection]
 -InstanceId <Guid[]> [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [-SessionOption <PSSessionOption>] [-ThrottleLimit <Int32>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="638a0-112">ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="638a0-112">ConnectionUri</span></span>

```
Connect-PSSession [-ConfigurationName <String>] [-ConnectionUri] <Uri[]> [-AllowRedirection] [-Name <String[]>]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [-SessionOption <PSSessionOption>] [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="638a0-113">InstanceId</span><span class="sxs-lookup"><span data-stu-id="638a0-113">InstanceId</span></span>

```
Connect-PSSession -InstanceId <Guid[]> [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="638a0-114">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="638a0-114">Id</span></span>

```
Connect-PSSession [-ThrottleLimit <Int32>] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="638a0-115">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="638a0-115">DESCRIPTION</span></span>

<span data-ttu-id="638a0-116">Командлет **Connect-PSSession** повторно подключается к управляемым пользователем сеансам PowerShell ( **PSSession** ), которые были отключены.</span><span class="sxs-lookup"><span data-stu-id="638a0-116">The **Connect-PSSession** cmdlet reconnects to user-managed PowerShell sessions ( **PSSessions** ) that were disconnected.</span></span>
<span data-ttu-id="638a0-117">Он работает в сеансах, которые не были намеренно отключены, например с помощью командлета Disconnect-PSSession или параметра *InDisconnectedSession* командлета Invoke-Command, и тех, которые были отключены непреднамеренно, например с помощью временного сбоя сети.</span><span class="sxs-lookup"><span data-stu-id="638a0-117">It works on sessions that are disconnected intentionally, such as by using the Disconnect-PSSession cmdlet or the *InDisconnectedSession* parameter of the Invoke-Command cmdlet, and those that were disconnected unintentionally, such as by a temporary network outage.</span></span>

<span data-ttu-id="638a0-118">**Connect-PSSession** может подключаться к любому отключенному сеансу, запущенному этим же пользователем.</span><span class="sxs-lookup"><span data-stu-id="638a0-118">**Connect-PSSession** can connect to any disconnected session that was started by the same user.</span></span>
<span data-ttu-id="638a0-119">К ним относятся те, которые были запущены или отключены от других сеансов на других компьютерах.</span><span class="sxs-lookup"><span data-stu-id="638a0-119">These include those that were started by or disconnected from other sessions on other computers.</span></span>

<span data-ttu-id="638a0-120">Однако **Connect-PSSession** не может подключиться к разорванным или закрытым сеансам или интерактивным сеансам, запущенным с помощью командлета Enter-PSSession.</span><span class="sxs-lookup"><span data-stu-id="638a0-120">However, **Connect-PSSession** cannot connect to broken or closed sessions, or interactive sessions started by using the Enter-PSSession cmdlet.</span></span>
<span data-ttu-id="638a0-121">Кроме того, вы не сможете подключиться к сеансам, запущенным другими пользователями, если не указать учетные данные пользователя, создавшего сеанс.</span><span class="sxs-lookup"><span data-stu-id="638a0-121">Also you cannot connect sessions to sessions started by other users, unless you can provide the credentials of the user who created the session.</span></span>

<span data-ttu-id="638a0-122">Дополнительные сведения о функции отключенных сеансов см. в разделе about_Remote_Disconnected_Sessions.</span><span class="sxs-lookup"><span data-stu-id="638a0-122">For more information about the Disconnected Sessions feature, see about_Remote_Disconnected_Sessions.</span></span>

<span data-ttu-id="638a0-123">Этот командлет впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="638a0-123">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="638a0-124">Примеры</span><span class="sxs-lookup"><span data-stu-id="638a0-124">EXAMPLES</span></span>

### <span data-ttu-id="638a0-125">Пример 1. Повторное подключение к сеансу</span><span class="sxs-lookup"><span data-stu-id="638a0-125">Example 1: Reconnect to a session</span></span>

```
PS C:\> Connect-PSSession -ComputerName Server01 -Name ITTask
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 4 ITTask          Server01        Opened        ITTasks                  Available
```

<span data-ttu-id="638a0-126">Эта команда восстанавливает соединение с сеансом ITTask на компьютере Server01.</span><span class="sxs-lookup"><span data-stu-id="638a0-126">This command reconnects to the ITTask session on the Server01 computer.</span></span>

<span data-ttu-id="638a0-127">Выходные данные показывают, что команда выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="638a0-127">The output shows that the command was successful.</span></span>
<span data-ttu-id="638a0-128">**Состояние** сеанса открывается, а **доступность** доступна, что означает, что можно выполнять команды в сеансе.</span><span class="sxs-lookup"><span data-stu-id="638a0-128">The **State** of the session is Opened and the **Availability** is Available, which indicates that you can run commands in the session.</span></span>

### <span data-ttu-id="638a0-129">Пример 2. последствия отключения и повторного подключения</span><span class="sxs-lookup"><span data-stu-id="638a0-129">Example 2: Effect of disconnecting and reconnecting</span></span>

```
PS C:\> Get-PSSession

Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 Backups         Localhost       Opened        Microsoft.PowerShell     Available


PS C:\> Get-PSSession | Disconnect-PSSession

Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 Backups         Localhost       Disconnected  Microsoft.PowerShell          None


PS C:\> Get-PSSession | Connect-PSSession

Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 Backups         Localhost       Opened        Microsoft.PowerShell     Available
```

<span data-ttu-id="638a0-130">В этом примере показан результат отключения и повторного подключения сеанса.</span><span class="sxs-lookup"><span data-stu-id="638a0-130">This example shows the effect of disconnecting and then reconnecting to a session.</span></span>

<span data-ttu-id="638a0-131">Первая команда использует командлет Get-PSSession.</span><span class="sxs-lookup"><span data-stu-id="638a0-131">The first command uses the Get-PSSession cmdlet.</span></span>
<span data-ttu-id="638a0-132">Без параметра *ComputerName* команда возвращает только сеансы, которые были созданы в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="638a0-132">Without the *ComputerName* parameter, the command gets only sessions that were created in the current session.</span></span>

<span data-ttu-id="638a0-133">Выходные данные показывают, что команда возвращает сеанс Backups на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="638a0-133">The output shows that the command gets the Backups session on the local computer.</span></span>
<span data-ttu-id="638a0-134">**Состояние** сеанса открыто, и доступна **доступность** .</span><span class="sxs-lookup"><span data-stu-id="638a0-134">The **State** of the session is Opened and the **Availability** is Available.</span></span>

<span data-ttu-id="638a0-135">Вторая команда использует командлет **Get-PSSession** для получения объектов **PSSession** , созданных в текущем сеансе, и командлет **Disconnect-PSSession** для отключения сеансов.</span><span class="sxs-lookup"><span data-stu-id="638a0-135">The second command uses the **Get-PSSession** cmdlet to get the **PSSession** objects that were created in the current session and the **Disconnect-PSSession** cmdlet to disconnect the sessions.</span></span>
<span data-ttu-id="638a0-136">Выходные данные показывают, что сеанс Backups отключен.</span><span class="sxs-lookup"><span data-stu-id="638a0-136">The output shows that the Backups session was disconnected.</span></span>
<span data-ttu-id="638a0-137">**Состояние** сеанса отключено, а уровень **доступности** — None.</span><span class="sxs-lookup"><span data-stu-id="638a0-137">The **State** of the session is Disconnected and the **Availability** is None.</span></span>

<span data-ttu-id="638a0-138">Третья команда использует командлет **Get-PSSession** для получения объектов **PSSession** , которые были созданы в текущем сеансе, и командлет **Connect-PSSession** для повторного подключения сеансов.</span><span class="sxs-lookup"><span data-stu-id="638a0-138">The third command uses the **Get-PSSession** cmdlet to get the **PSSession** objects that were created in the current session and the **Connect-PSSession** cmdlet to reconnect the sessions.</span></span>
<span data-ttu-id="638a0-139">Выходные данные показывают, что сеанс Backups был повторно подключен.</span><span class="sxs-lookup"><span data-stu-id="638a0-139">The output shows that the Backups session was reconnected.</span></span>
<span data-ttu-id="638a0-140">**Состояние** сеанса открыто, и доступна **доступность** .</span><span class="sxs-lookup"><span data-stu-id="638a0-140">The **State** of the session is Opened and the **Availability** is Available.</span></span>

<span data-ttu-id="638a0-141">При использовании командлета **Connect-PSSession** в сеансе, который не был отключен, команда не влияет на сеанс и не создает ошибок.</span><span class="sxs-lookup"><span data-stu-id="638a0-141">If you use the **Connect-PSSession** cmdlet on a session that is not disconnected, the command does not affect the session and it does not generate any errors.</span></span>

### <span data-ttu-id="638a0-142">Пример 3. ряд команд в корпоративном сценарии</span><span class="sxs-lookup"><span data-stu-id="638a0-142">Example 3: Series of commands in an enterprise scenario</span></span>

```
The administrator starts by creating a sessions on a remote computer and running a script in the session.The first command uses the **New-PSSession** cmdlet to create the ITTask session on the Server01 remote computer. The command uses the *ConfigurationName* parameter to specify the ITTasks session configuration. The command saves the sessions in the $s variable.
PS C:\> $s = New-PSSession -ComputerName Server01 -Name ITTask -ConfigurationName ITTasks

 The second command **Invoke-Command** cmdlet to start a background job in the session in the $s variable. It uses the *FilePath* parameter to run the script in the background job.
PS C:\> Invoke-Command -Session $s {Start-Job -FilePath \\Server30\Scripts\Backup-SQLDatabase.ps1}
Id     Name            State         HasMoreData     Location             Command
--     ----            -----         -----------     --------             -------
2      Job2            Running       True            Server01             \\Server30\Scripts\Backup...

The third command uses the Disconnect-PSSession cmdlet to disconnect from the session in the $s variable. The command uses the *OutputBufferingMode* parameter with a value of Drop to prevent the script from being blocked by having to deliver output to the session. It uses the *IdleTimeoutSec* parameter to extend the session time-out to 15 hours.When the command is completed, the administrator locks her computer and goes home for the evening.
PS C:\> Disconnect-PSSession -Session $s -OutputBufferingMode Drop -IdleTimeoutSec 60*60*15
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Server01        Disconnected  ITTasks               None

Later that evening, the administrator starts her home computer, logs on to the corporate network, and starts PowerShell. The fourth command uses the Get-PSSession cmdlet to get the sessions on the Server01 computer. The command finds the ITTask session.The fifth command uses the **Connect-PSSession** cmdlet to connect to the ITTask session. The command saves the session in the $s variable.
PS C:\> Get-PSSession -ComputerName Server01 -Name ITTask

Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Server01        Disconnected  ITTasks               None


PS C:\> $s = Connect-PSSession -ComputerName Server01 -Name ITTask


Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Server01        Opened        ITTasks               Available

The sixth command uses the **Invoke-Command** cmdlet to run a Get-Job command in the session in the $s variable. The output shows that the job finished successfully.The seventh command uses the **Invoke-Command** cmdlet to run a Receive-Job command in the session in the $s variable in the session. The command saves the results in the $BackupSpecs variable.The eighth command uses the **Invoke-Command** cmdlet to runs another script in the session. The command uses the value of the $BackupSpecs variable in the session as input to the script.


PS C:\> Invoke-Command -Session $s {Get-Job}

Id     Name            State         HasMoreData     Location             Command
--     ----            -----         -----------     --------             -------
2      Job2            Completed     True            Server01             \\Server30\Scripts\Backup...

PS C:\> Invoke-Command -Session $s {$BackupSpecs = Receive-Job -JobName Job2}

PS C:\> Invoke-Command -Session $s {\\Server30\Scripts\New-SQLDatabase.ps1 -InitData $BackupSpecs.Initialization}

The ninth command disconnects from the session in the $s variable.The administrator closes PowerShell and closes the computer. She can reconnect to the session on the next day and check the script status from her work computer.
PS C:\> Disconnect-PSSession -Session $s -OutputBufferingMode Drop -IdleTimeoutSec 60*60*15
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Server01        Disconnected  ITTasks               None
```

<span data-ttu-id="638a0-143">В этой серии команд показано, как командлет **Connect-PSSession** можно использовать на предприятии.</span><span class="sxs-lookup"><span data-stu-id="638a0-143">This series of commands shows how the **Connect-PSSession** cmdlet might be used in an enterprise scenario.</span></span>
<span data-ttu-id="638a0-144">В этом случае системный администратор запускает длительное задание в сеансе на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="638a0-144">In this case, a system administrator starts a long-running job in a session on a remote computer.</span></span>
<span data-ttu-id="638a0-145">После запуска задания администратор отключается от сеанса и отправляется домой.</span><span class="sxs-lookup"><span data-stu-id="638a0-145">After starting the job, the administrator disconnects from the session and goes home.</span></span>
<span data-ttu-id="638a0-146">Позднее, вечером, администратор выполняет вход на свой домашний компьютер и проверяет, выполнялось ли задание до его завершения.</span><span class="sxs-lookup"><span data-stu-id="638a0-146">Later that evening, the administrator logs on to her home computer and verifies that the job ran until it is completed.</span></span>

## <span data-ttu-id="638a0-147">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="638a0-147">PARAMETERS</span></span>

### <span data-ttu-id="638a0-148">-AllowRedirection</span><span class="sxs-lookup"><span data-stu-id="638a0-148">-AllowRedirection</span></span>

<span data-ttu-id="638a0-149">Указывает, что этот командлет разрешает перенаправление этого соединения на альтернативный URI.</span><span class="sxs-lookup"><span data-stu-id="638a0-149">Indicates that this cmdlet allows redirection of this connection to an alternate URI.</span></span>

<span data-ttu-id="638a0-150">При использовании параметра *ConnectionURI* удаленный компьютер может вернуть инструкцию для перенаправления на другой URI.</span><span class="sxs-lookup"><span data-stu-id="638a0-150">When you use the *ConnectionURI* parameter, the remote destination can return an instruction to redirect to a different URI.</span></span>
<span data-ttu-id="638a0-151">По умолчанию PowerShell не перенаправляет соединения, но можно использовать этот параметр, чтобы разрешить перенаправление подключения.</span><span class="sxs-lookup"><span data-stu-id="638a0-151">By default, PowerShell does not redirect connections, but you can use this parameter to allow it to redirect the connection.</span></span>

<span data-ttu-id="638a0-152">Можно также ограничить количество перенаправлений соединение, изменив значение параметра сеанса **MaximumConnectionRedirectionCount** .</span><span class="sxs-lookup"><span data-stu-id="638a0-152">You can also limit the number of times the connection is redirected by changing the **MaximumConnectionRedirectionCount** session option value.</span></span>
<span data-ttu-id="638a0-153">Используйте параметр *максимумредиректион* командлета New-PSSessionOption или задайте свойство **MaximumConnectionRedirectionCount** для переменной настройки **$PSSessionOption** .</span><span class="sxs-lookup"><span data-stu-id="638a0-153">Use the *MaximumRedirection* parameter of the New-PSSessionOption cmdlet or set the **MaximumConnectionRedirectionCount** property of the **$PSSessionOption** preference variable.</span></span>
<span data-ttu-id="638a0-154">Значение по умолчанию — 5.</span><span class="sxs-lookup"><span data-stu-id="638a0-154">The default value is 5.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ConnectionUriGuid, ConnectionUri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="638a0-155">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="638a0-155">-ApplicationName</span></span>

<span data-ttu-id="638a0-156">Указывает имя приложения.</span><span class="sxs-lookup"><span data-stu-id="638a0-156">Specifies the name of an application.</span></span>
<span data-ttu-id="638a0-157">Этот командлет подключается только к сеансам, использующим указанное приложение.</span><span class="sxs-lookup"><span data-stu-id="638a0-157">This cmdlet connects only to sessions that use the specified application.</span></span>

<span data-ttu-id="638a0-158">Введите сегмент имени приложения URI подключения.</span><span class="sxs-lookup"><span data-stu-id="638a0-158">Enter the application name segment of the connection URI.</span></span>
<span data-ttu-id="638a0-159">Например, в следующем URI соединения имя приложения — WSMan: `http://localhost:5985/WSMAN` .</span><span class="sxs-lookup"><span data-stu-id="638a0-159">For example, in the following connection URI, the application name is WSMan: `http://localhost:5985/WSMAN`.</span></span>
<span data-ttu-id="638a0-160">Имя приложения сеанса хранится в свойстве сеанса **Runspace.ConnectionInfo.AppName** .</span><span class="sxs-lookup"><span data-stu-id="638a0-160">The application name of a session is stored in the **Runspace.ConnectionInfo.AppName** property of the session.</span></span>

<span data-ttu-id="638a0-161">Значение этого параметра используется для выбора и фильтрации сеансов.</span><span class="sxs-lookup"><span data-stu-id="638a0-161">The value of this parameter is used to select and filter sessions.</span></span>
<span data-ttu-id="638a0-162">Оно не изменяет приложение, которое использует сеанс.</span><span class="sxs-lookup"><span data-stu-id="638a0-162">It does not change the application that the session uses.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerNameGuid, ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="638a0-163">-Authentication</span><span class="sxs-lookup"><span data-stu-id="638a0-163">-Authentication</span></span>

<span data-ttu-id="638a0-164">Указывает механизм, используемый для проверки подлинности учетных данных пользователя в команде для повторного подключения к отключенному сеансу.</span><span class="sxs-lookup"><span data-stu-id="638a0-164">Specifies the mechanism that is used to authenticate user credentials in the command to reconnect to the disconnected session.</span></span> <span data-ttu-id="638a0-165">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="638a0-165">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="638a0-166">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="638a0-166">Default</span></span>
- <span data-ttu-id="638a0-167">Базовый</span><span class="sxs-lookup"><span data-stu-id="638a0-167">Basic</span></span>
- <span data-ttu-id="638a0-168">CredSSP</span><span class="sxs-lookup"><span data-stu-id="638a0-168">Credssp</span></span>
- <span data-ttu-id="638a0-169">Digest (дайджест)</span><span class="sxs-lookup"><span data-stu-id="638a0-169">Digest</span></span>
- <span data-ttu-id="638a0-170">Kerberos</span><span class="sxs-lookup"><span data-stu-id="638a0-170">Kerberos</span></span>
- <span data-ttu-id="638a0-171">Согласование</span><span class="sxs-lookup"><span data-stu-id="638a0-171">Negotiate</span></span>
- <span data-ttu-id="638a0-172">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="638a0-172">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="638a0-173">Значение по умолчанию — Default.</span><span class="sxs-lookup"><span data-stu-id="638a0-173">The default value is Default.</span></span>

<span data-ttu-id="638a0-174">Дополнительные сведения о значениях этого параметра см. в разделе [перечисление AuthenticationMechanism](https://msdn.microsoft.com/library/system.management.automation.runspaces.authenticationmechanism) в библиотеке MSDN.</span><span class="sxs-lookup"><span data-stu-id="638a0-174">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](https://msdn.microsoft.com/library/system.management.automation.runspaces.authenticationmechanism) in the MSDN library.</span></span>

<span data-ttu-id="638a0-175">Внимание! Аутентификация CredSSP, в рамках которой учетные данные пользователя передаются на удаленный компьютер для проверки, предназначена для команд, требующих аутентификацию нескольких ресурсов, например для доступа к удаленной сетевой папке.</span><span class="sxs-lookup"><span data-stu-id="638a0-175">Caution: Credential Security Support Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span>
<span data-ttu-id="638a0-176">Этот механизм повышает риск безопасности удаленной операции.</span><span class="sxs-lookup"><span data-stu-id="638a0-176">This mechanism increases the security risk of the remote operation.</span></span>
<span data-ttu-id="638a0-177">Если удаленный компьютер скомпрометирован, учетные данные, передаваемые ему, могут использоваться для управления сетевым сеансом.</span><span class="sxs-lookup"><span data-stu-id="638a0-177">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ComputerNameGuid, ComputerName, ConnectionUriGuid, ConnectionUri
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="638a0-178">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="638a0-178">-CertificateThumbprint</span></span>

<span data-ttu-id="638a0-179">Задает цифровой сертификат с открытым ключом (X509) учетной записи пользователя, который располагает разрешением для подключения к отсоединенному сеансу.</span><span class="sxs-lookup"><span data-stu-id="638a0-179">Specifies the digital public key certificate (X509) of a user account that has permission to connect to the disconnected session.</span></span> <span data-ttu-id="638a0-180">Введите отпечаток сертификата.</span><span class="sxs-lookup"><span data-stu-id="638a0-180">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="638a0-181">Сертификаты используются при проверке подлинности на основе сертификата клиента.</span><span class="sxs-lookup"><span data-stu-id="638a0-181">Certificates are used in client certificate-based authentication.</span></span>
<span data-ttu-id="638a0-182">Они могут быть сопоставлены только с локальными учетными записями пользователей.</span><span class="sxs-lookup"><span data-stu-id="638a0-182">They can be mapped only to local user accounts.</span></span>
<span data-ttu-id="638a0-183">Они не работают с учетными записями домена.</span><span class="sxs-lookup"><span data-stu-id="638a0-183">They do not work with domain accounts.</span></span>

<span data-ttu-id="638a0-184">Чтобы получить отпечаток сертификата, используйте команду Get-Item или Get-ChildItem на диске с сертификатом PowerShell:.</span><span class="sxs-lookup"><span data-stu-id="638a0-184">To get a certificate thumbprint, use a Get-Item or Get-ChildItem command in the PowerShell Cert: drive.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerNameGuid, ComputerName, ConnectionUriGuid, ConnectionUri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="638a0-185">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="638a0-185">-ComputerName</span></span>

<span data-ttu-id="638a0-186">Указывает компьютеры, на которых хранятся отключенные сеансы.</span><span class="sxs-lookup"><span data-stu-id="638a0-186">Specifies the computers on which the disconnected sessions are stored.</span></span>
<span data-ttu-id="638a0-187">Сеансы хранятся на компьютере, который находится на стороне сервера или получает окончание соединения.</span><span class="sxs-lookup"><span data-stu-id="638a0-187">Sessions are stored on the computer that is at the server-side or receiving end of a connection.</span></span>
<span data-ttu-id="638a0-188">По умолчанию это локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="638a0-188">The default is the local computer.</span></span>

<span data-ttu-id="638a0-189">Введите имя NetBIOS, IP-адрес или полное доменное имя компьютера.</span><span class="sxs-lookup"><span data-stu-id="638a0-189">Type the NetBIOS name, an IP address, or a fully qualified domain name of one computer.</span></span>
<span data-ttu-id="638a0-190">Подстановочные знаки не допускаются.</span><span class="sxs-lookup"><span data-stu-id="638a0-190">Wildcard characters are not permitted.</span></span>
<span data-ttu-id="638a0-191">Чтобы указать локальный компьютер, введите имя компьютера, localhost или точку (.)</span><span class="sxs-lookup"><span data-stu-id="638a0-191">To specify the local computer, type the computer name, localhost, or a dot (.)</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerNameGuid, ComputerName
Aliases: Cn

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="638a0-192">-ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="638a0-192">-ConfigurationName</span></span>

<span data-ttu-id="638a0-193">Подключается только к сеансам, использующим указанную конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="638a0-193">Connects only to sessions that use the specified session configuration.</span></span>

<span data-ttu-id="638a0-194">Введите имя конфигурации или полное имя ресурса (URI) для конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="638a0-194">Enter a configuration name or the fully qualified resource URI for a session configuration.</span></span>
<span data-ttu-id="638a0-195">Если указано только имя конфигурации, в начале добавляется следующий URI схемы: `http://schemas.microsoft.com/powershell` .</span><span class="sxs-lookup"><span data-stu-id="638a0-195">If you specify only the configuration name, the following schema URI is prepended: `http://schemas.microsoft.com/powershell`.</span></span>
<span data-ttu-id="638a0-196">Имя конфигурации сеанса хранится в свойстве сеанса **ConfigurationName** .</span><span class="sxs-lookup"><span data-stu-id="638a0-196">The configuration name of a session is stored in the **ConfigurationName** property of the session.</span></span>

<span data-ttu-id="638a0-197">Значение этого параметра используется для выбора и фильтрации сеансов.</span><span class="sxs-lookup"><span data-stu-id="638a0-197">The value of this parameter is used to select and filter sessions.</span></span>
<span data-ttu-id="638a0-198">Оно не изменяет конфигурацию, которую использует сеанс.</span><span class="sxs-lookup"><span data-stu-id="638a0-198">It does not change the session configuration that the session uses.</span></span>

<span data-ttu-id="638a0-199">Дополнительные сведения о конфигурациях сеансов см. в разделе [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="638a0-199">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerNameGuid, ComputerName, ConnectionUriGuid, ConnectionUri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="638a0-200">-ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="638a0-200">-ConnectionUri</span></span>

<span data-ttu-id="638a0-201">Указывает URI конечных точек подключения для отключенных сеансов.</span><span class="sxs-lookup"><span data-stu-id="638a0-201">Specifies the URIs of the connection endpoints for the disconnected sessions.</span></span>

<span data-ttu-id="638a0-202">Значение URI должно быть указано полностью.</span><span class="sxs-lookup"><span data-stu-id="638a0-202">The URI must be fully qualified.</span></span>
<span data-ttu-id="638a0-203">Строка имеет следующий формат:</span><span class="sxs-lookup"><span data-stu-id="638a0-203">The format of this string is as follows:</span></span>

`\<Transport\>://\<ComputerName\>:\<Port\>/\<ApplicationName\>`

<span data-ttu-id="638a0-204">Значение по умолчанию определяется следующим образом.</span><span class="sxs-lookup"><span data-stu-id="638a0-204">The default value is as follows:</span></span>

`http://localhost:5985/WSMAN`

<span data-ttu-id="638a0-205">Если не указать URI соединения, можно использовать параметры *UseSSL* и *Port* , чтобы указать значения универсального кода ресурса (URI) соединения.</span><span class="sxs-lookup"><span data-stu-id="638a0-205">If you do not specify a connection URI, you can use the *UseSSL* and *Port* parameters to specify the connection URI values.</span></span>

<span data-ttu-id="638a0-206">Допустимые значения для сегмента **Transport** идентификатора URI: HTTP и HTTPS.</span><span class="sxs-lookup"><span data-stu-id="638a0-206">Valid values for the **Transport** segment of the URI are HTTP and HTTPS.</span></span>
<span data-ttu-id="638a0-207">Если указать URI подключения с сегментом Transport, но не указать порт, сеанс будет создан со стандартными портами: 80 для HTTP и 443 для HTTPS.</span><span class="sxs-lookup"><span data-stu-id="638a0-207">If you specify a connection URI with a Transport segment, but do not specify a port, the session is created with standards ports: 80 for HTTP and 443 for HTTPS.</span></span>
<span data-ttu-id="638a0-208">Чтобы использовать порты по умолчанию для удаленного взаимодействия PowerShell, укажите порт 5985 для HTTP или 5986 для HTTPS.</span><span class="sxs-lookup"><span data-stu-id="638a0-208">To use the default ports for PowerShell remoting, specify port 5985 for HTTP or 5986 for HTTPS.</span></span>

<span data-ttu-id="638a0-209">Если конечный компьютер перенаправляет подключение к другому универсальному коду ресурса (URI), PowerShell предотвращает перенаправление, если в команде не используется параметр *AllowRedirection* .</span><span class="sxs-lookup"><span data-stu-id="638a0-209">If the destination computer redirects the connection to a different URI, PowerShell prevents the redirection unless you use the *AllowRedirection* parameter in the command.</span></span>

```yaml
Type: System.Uri[]
Parameter Sets: ConnectionUriGuid, ConnectionUri
Aliases: URI, CU

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="638a0-210">-Credential</span><span class="sxs-lookup"><span data-stu-id="638a0-210">-Credential</span></span>

<span data-ttu-id="638a0-211">Указывает учетную запись пользователя с разрешением на подключение к отсоединенному сеансу.</span><span class="sxs-lookup"><span data-stu-id="638a0-211">Specifies a user account that has permission to connect to the disconnected session.</span></span>
<span data-ttu-id="638a0-212">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="638a0-212">The default is the current user.</span></span>

<span data-ttu-id="638a0-213">Введите имя пользователя, например **User01** или **Domain01\User01** , либо введите объект **PSCredential** , созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="638a0-213">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="638a0-214">Если ввести имя пользователя, будет предложено ввести пароль.</span><span class="sxs-lookup"><span data-stu-id="638a0-214">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="638a0-215">Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="638a0-215">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="638a0-216">Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="638a0-216">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerNameGuid, ComputerName, ConnectionUriGuid, ConnectionUri
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="638a0-217">-Id</span><span class="sxs-lookup"><span data-stu-id="638a0-217">-Id</span></span>

<span data-ttu-id="638a0-218">Указывает идентификаторы отключенных сеансов.</span><span class="sxs-lookup"><span data-stu-id="638a0-218">Specifies the IDs of the disconnected sessions.</span></span>
<span data-ttu-id="638a0-219">Параметр *ID* работает только в том случае, если отключенный сеанс ранее был подключен к текущему сеансу.</span><span class="sxs-lookup"><span data-stu-id="638a0-219">The *Id* parameter works only when the disconnected session was previously connected to the current session.</span></span>

<span data-ttu-id="638a0-220">Этот параметр допустим, но не имеет силы, если сеанс хранится на локальном компьютере, но не был подключен к текущему сеансу.</span><span class="sxs-lookup"><span data-stu-id="638a0-220">This parameter is valid, but not effective, when the session is stored on the local computer, but was not connected to the current session.</span></span>

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

### <span data-ttu-id="638a0-221">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="638a0-221">-InstanceId</span></span>

<span data-ttu-id="638a0-222">Указывает идентификаторы экземпляров отключенных сеансов.</span><span class="sxs-lookup"><span data-stu-id="638a0-222">Specifies the instance IDs of the disconnected sessions.</span></span>

<span data-ttu-id="638a0-223">Идентификатор экземпляра — это идентификатор GUID, который однозначно определяет **сеанс PSSession** на локальном или удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="638a0-223">The instance ID is a GUID that uniquely identifies a **PSSession** on a local or remote computer.</span></span>

<span data-ttu-id="638a0-224">Идентификатор экземпляра хранится в свойстве **InstanceId** **сеанса PSSession** .</span><span class="sxs-lookup"><span data-stu-id="638a0-224">The instance ID is stored in the **InstanceID** property of the **PSSession** .</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: ComputerNameGuid, ConnectionUriGuid, InstanceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="638a0-225">-Name</span><span class="sxs-lookup"><span data-stu-id="638a0-225">-Name</span></span>

<span data-ttu-id="638a0-226">Указывает понятные имена отключенных сеансов.</span><span class="sxs-lookup"><span data-stu-id="638a0-226">Specifies the friendly names of the disconnected sessions.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name, ComputerName, ConnectionUri
Aliases:

Required: True (Name), False (ComputerName, ConnectionUri)
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="638a0-227">-Port</span><span class="sxs-lookup"><span data-stu-id="638a0-227">-Port</span></span>

<span data-ttu-id="638a0-228">Указывает сетевой порт на удаленном компьютере, который используется для повторного подключения к сеансу.</span><span class="sxs-lookup"><span data-stu-id="638a0-228">Specifies the network port on the remote computer that is used to reconnect to the session.</span></span>
<span data-ttu-id="638a0-229">Для подключения к удаленному компьютеру требуется, чтобы он прослушивал порт, используемый соединением.</span><span class="sxs-lookup"><span data-stu-id="638a0-229">To connect to a remote computer, the remote computer must be listening on the port that the connection uses.</span></span>
<span data-ttu-id="638a0-230">Порты по умолчанию — 5985, то есть порт WinRM для HTTP, а 5986 — порт WinRM для HTTPS.</span><span class="sxs-lookup"><span data-stu-id="638a0-230">The default ports are 5985, which is the WinRM port for HTTP, and 5986, which is the WinRM port for HTTPS.</span></span>

<span data-ttu-id="638a0-231">Прежде чем использовать альтернативный порт, необходимо настроить прослушиватель WinRM на удаленном компьютере для прослушивания по этому порту.</span><span class="sxs-lookup"><span data-stu-id="638a0-231">Before using an alternate port, you must configure the WinRM listener on the remote computer to listen at that port.</span></span>
<span data-ttu-id="638a0-232">Чтобы настроить прослушиватель, введите следующие две команды в командной строке PowerShell:</span><span class="sxs-lookup"><span data-stu-id="638a0-232">To configure the listener, type the following two commands at the PowerShell prompt:</span></span>

`Remove-Item -Path WSMan:\Localhost\listener\listener* -Recurse`

`New-Item -Path WSMan:\Localhost\listener -Transport http -Address * -Port \<port-number\>`

<span data-ttu-id="638a0-233">Не используйте параметр *Port* , если этого можно избежать.</span><span class="sxs-lookup"><span data-stu-id="638a0-233">Do not use the *Port* parameter unless you must.</span></span>
<span data-ttu-id="638a0-234">Порт, который задается в команде, применяется ко всем компьютерам или сеансам, в которых выполняется команда.</span><span class="sxs-lookup"><span data-stu-id="638a0-234">The port that is set in the command applies to all computers or sessions on which the command runs.</span></span>
<span data-ttu-id="638a0-235">Альтернативный порт может помешать выполнению команды на всех компьютерах.</span><span class="sxs-lookup"><span data-stu-id="638a0-235">An alternate port setting might prevent the command from running on all computers.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ComputerNameGuid, ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="638a0-236">-Session</span><span class="sxs-lookup"><span data-stu-id="638a0-236">-Session</span></span>

<span data-ttu-id="638a0-237">Указывает отключенные сеансы.</span><span class="sxs-lookup"><span data-stu-id="638a0-237">Specifies the disconnected sessions.</span></span>
<span data-ttu-id="638a0-238">Введите переменную, содержащую объекты **PSSession** , или команду, которая создает или получает объекты **PSSession** , такие как команда Get-PSSession.</span><span class="sxs-lookup"><span data-stu-id="638a0-238">Enter a variable that contains the **PSSession** objects or a command that creates or gets the **PSSession** objects, such as a Get-PSSession command.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession[]
Parameter Sets: Session
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="638a0-239">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="638a0-239">-SessionOption</span></span>

<span data-ttu-id="638a0-240">Задает дополнительные параметры для сеанса.</span><span class="sxs-lookup"><span data-stu-id="638a0-240">Specifies advanced options for the session.</span></span>
<span data-ttu-id="638a0-241">Введите объект **SessionOption** , например объект, созданный с помощью командлета New-PSSessionOption, или хэш-таблицу, где ключи — это имена параметров сеанса, а значения — это значения параметров сеанса.</span><span class="sxs-lookup"><span data-stu-id="638a0-241">Enter a **SessionOption** object, such as one that you create by using the New-PSSessionOption cmdlet, or a hash table in which the keys are session option names and the values are session option values.</span></span>

<span data-ttu-id="638a0-242">Значения по умолчанию для параметров определяются значением привилегированной переменной $PSSessionOption, если оно задано.</span><span class="sxs-lookup"><span data-stu-id="638a0-242">The default values for the options are determined by the value of the $PSSessionOption preference variable, if it is set.</span></span>
<span data-ttu-id="638a0-243">В противном случае значения по умолчанию задаются параметрами, указанными в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="638a0-243">Otherwise, the default values are established by options set in the session configuration.</span></span>

<span data-ttu-id="638a0-244">Значения параметров сеанса имеют приоритет над значениями по умолчанию, заданными в переменной $PSSessionOption и конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="638a0-244">The session option values take precedence over default values for sessions set in the $PSSessionOption preference variable and in the session configuration.</span></span>
<span data-ttu-id="638a0-245">Однако они не имеют приоритет над максимальными значениями, квотами и ограничениями, заданными в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="638a0-245">However, they do not take precedence over maximum values, quotas or limits set in the session configuration.</span></span>

<span data-ttu-id="638a0-246">Описание параметров сеанса, включающих значения по умолчанию, см. в разделе New-PSSessionOption.</span><span class="sxs-lookup"><span data-stu-id="638a0-246">For a description of the session options that includes the default values, see New-PSSessionOption.</span></span>
<span data-ttu-id="638a0-247">Дополнительные сведения о переменной настройки **$PSSessionOption** см. в разделе [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="638a0-247">For information about the **$PSSessionOption** preference variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>
<span data-ttu-id="638a0-248">Дополнительные сведения о конфигурациях сеансов см. в разделе [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="638a0-248">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

```yaml
Type: System.Management.Automation.Remoting.PSSessionOption
Parameter Sets: ComputerNameGuid, ComputerName, ConnectionUriGuid, ConnectionUri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="638a0-249">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="638a0-249">-ThrottleLimit</span></span>

<span data-ttu-id="638a0-250">Указывает максимальное число одновременных подключений, которые можно установить для запуска этой команды.</span><span class="sxs-lookup"><span data-stu-id="638a0-250">Specifies the maximum number of concurrent connections that can be established to run this command.</span></span>
<span data-ttu-id="638a0-251">Если этот параметр не указан или имеет значение 0, используется значение по умолчанию — 32.</span><span class="sxs-lookup"><span data-stu-id="638a0-251">If you omit this parameter or enter a value of 0, the default value, 32, is used.</span></span>

<span data-ttu-id="638a0-252">Предел регулирования применяется только к текущему командлету, а не к сеансу или компьютеру.</span><span class="sxs-lookup"><span data-stu-id="638a0-252">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="638a0-253">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="638a0-253">-UseSSL</span></span>

<span data-ttu-id="638a0-254">Указывает, что этот командлет использует протокол SSL (SSL) для подключения к отключенному сеансу.</span><span class="sxs-lookup"><span data-stu-id="638a0-254">Indicates that this cmdlet uses the Secure Sockets Layer (SSL) protocol to connect to the disconnected session.</span></span> <span data-ttu-id="638a0-255">По умолчанию SSL не используется.</span><span class="sxs-lookup"><span data-stu-id="638a0-255">By default, SSL is not used.</span></span>

<span data-ttu-id="638a0-256">WS-Management шифрует все содержимое PowerShell, передаваемое по сети.</span><span class="sxs-lookup"><span data-stu-id="638a0-256">WS-Management encrypts all PowerShell content transmitted over the network.</span></span>
<span data-ttu-id="638a0-257">Параметр *UseSSL* — это дополнительная защита, которая отправляет данные по HTTPS-соединению, а не по HTTP.</span><span class="sxs-lookup"><span data-stu-id="638a0-257">The *UseSSL* parameter is an additional protection that sends the data across an HTTPS connection instead of an HTTP connection.</span></span>

<span data-ttu-id="638a0-258">Если вы используете этот параметр, но протокол SSL недоступен для порта, используемого для команды, команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="638a0-258">If you use this parameter, but SSL is not available on the port that is used for the command, the command fails.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerNameGuid, ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="638a0-259">-Confirm</span><span class="sxs-lookup"><span data-stu-id="638a0-259">-Confirm</span></span>

<span data-ttu-id="638a0-260">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="638a0-260">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="638a0-261">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="638a0-261">-WhatIf</span></span>

<span data-ttu-id="638a0-262">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="638a0-262">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="638a0-263">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="638a0-263">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="638a0-264">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="638a0-264">CommonParameters</span></span>

<span data-ttu-id="638a0-265">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="638a0-265">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="638a0-266">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="638a0-266">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="638a0-267">Входные данные</span><span class="sxs-lookup"><span data-stu-id="638a0-267">INPUTS</span></span>

### <span data-ttu-id="638a0-268">System.Management.Automation.Runspaces.PSSession</span><span class="sxs-lookup"><span data-stu-id="638a0-268">System.Management.Automation.Runspaces.PSSession</span></span>

<span data-ttu-id="638a0-269">Сеанс ( **PSSession** ) можно передать в этот командлет по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="638a0-269">You can pipe a session ( **PSSession** ) to this cmdlet.</span></span>

## <span data-ttu-id="638a0-270">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="638a0-270">OUTPUTS</span></span>

### <span data-ttu-id="638a0-271">System.Management.Automation.Runspaces.PSSession</span><span class="sxs-lookup"><span data-stu-id="638a0-271">System.Management.Automation.Runspaces.PSSession</span></span>

<span data-ttu-id="638a0-272">Этот командлет возвращает объект, представляющий сеанс, к которому он был подключен повторно.</span><span class="sxs-lookup"><span data-stu-id="638a0-272">This cmdlet returns an object that represents the session to which it reconnected.</span></span>

## <span data-ttu-id="638a0-273">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="638a0-273">NOTES</span></span>

* <span data-ttu-id="638a0-274">**Connect-PSSession** повторно подключается только к сеансам, которые отключены, т. е. сеансы со значением disconnected (отключено) для свойства **State** .</span><span class="sxs-lookup"><span data-stu-id="638a0-274">**Connect-PSSession** reconnects only to sessions that are disconnected, that is, sessions that have a value of Disconnected for the **State** property.</span></span> <span data-ttu-id="638a0-275">Только сеансы, подключенные к или конечным компьютерам под управлением Windows PowerShell 3,0 или более поздней версии, могут быть отключены и повторно подключены.</span><span class="sxs-lookup"><span data-stu-id="638a0-275">Only sessions that are connected to, or end at, computers that run Windows PowerShell 3.0 or later versions can be disconnected and reconnected.</span></span>
* <span data-ttu-id="638a0-276">При использовании **Connect-PSSession** для сеанса, который не был отключен, команда не влияет на сеанс и не создает ошибок.</span><span class="sxs-lookup"><span data-stu-id="638a0-276">If you use **Connect-PSSession** on a session that is not disconnected, the command does not affect the session and it does not generate errors.</span></span>
* <span data-ttu-id="638a0-277">Отключенные сеансы замыкания на себя с интерактивными маркерами, которые создаются с помощью параметра *EnableNetworkAccess* , могут быть повторно подключены только с компьютера, на котором был создан сеанс.</span><span class="sxs-lookup"><span data-stu-id="638a0-277">Disconnected loopback sessions with interactive tokens, which are created by using the *EnableNetworkAccess* parameter, can be reconnected only from the computer on which the session was created.</span></span> <span data-ttu-id="638a0-278">Это ограничение защищает компьютер от вредоносного доступа.</span><span class="sxs-lookup"><span data-stu-id="638a0-278">This restriction protects the computer from malicious access.</span></span>
* <span data-ttu-id="638a0-279">Значение свойства **State** для **PSSession** задается относительно текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="638a0-279">The value of the **State** property of a **PSSession** is relative to the current session.</span></span>
<span data-ttu-id="638a0-280">Таким образом, значение **disconnected** означает, что **сеанс PSSession** не подключен к текущему сеансу.</span><span class="sxs-lookup"><span data-stu-id="638a0-280">Therefore, a value of **Disconnected** means that the **PSSession** is not connected to the current session.</span></span> <span data-ttu-id="638a0-281">Однако это не означает, что **сеанс PSSession** отключен от всех сеансов.</span><span class="sxs-lookup"><span data-stu-id="638a0-281">However, it does not mean that the **PSSession** is disconnected from all sessions.</span></span> <span data-ttu-id="638a0-282">Он может быть подключен к другому сеансу.</span><span class="sxs-lookup"><span data-stu-id="638a0-282">It might be connected to a different session.</span></span> <span data-ttu-id="638a0-283">Определить возможность подключения или повторного подключения к сеансу позволяет свойство **Availability** .</span><span class="sxs-lookup"><span data-stu-id="638a0-283">To determine whether you can connect or reconnect to the session, use the **Availability** property.</span></span>

  <span data-ttu-id="638a0-284">Если свойство **Availability** имеет значение None, подключиться к сеансу можно.</span><span class="sxs-lookup"><span data-stu-id="638a0-284">An **Availability** value of None indicates that you can connect to the session.</span></span>
<span data-ttu-id="638a0-285">Значение занято указывает, что невозможно подключиться к сеансу **PSSession** , так как он подключен к другому сеансу.</span><span class="sxs-lookup"><span data-stu-id="638a0-285">A value of Busy indicates that you cannot connect to the **PSSession** because it is connected to another session.</span></span>

  <span data-ttu-id="638a0-286">Дополнительные сведения о значениях свойства **State** в сеансах см. в разделе [перечисление РУНСПАЦЕСТАТЕ](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspacestate) в библиотеке MSDN.</span><span class="sxs-lookup"><span data-stu-id="638a0-286">For more information about the values of the **State** property of sessions, see [RunspaceState Enumeration](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspacestate) in the MSDN library.</span></span>

  <span data-ttu-id="638a0-287">Дополнительные сведения о значениях свойства **доступность** сеансов см. в разделе [перечисление РУНСПАЦЕАВАИЛАБИЛИТИ](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspaceavailability) в библиотеке MSDN.</span><span class="sxs-lookup"><span data-stu-id="638a0-287">For more information about the values of the **Availability** property of sessions, see [RunspaceAvailability Enumeration](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspaceavailability) in the MSDN library.</span></span>

* <span data-ttu-id="638a0-288">Нельзя изменить значение времени ожидания простоя **сеанса PSSession** при подключении к **сеансу PSSession** .</span><span class="sxs-lookup"><span data-stu-id="638a0-288">You cannot change the idle time-out value of a **PSSession** when you connect to the **PSSession** .</span></span> <span data-ttu-id="638a0-289">Параметр *SessionOption* командлета **Connect-PSSession** принимает объект **SessionOption** со значением **IdleTimeout** .</span><span class="sxs-lookup"><span data-stu-id="638a0-289">The *SessionOption* parameter of **Connect-PSSession** takes a **SessionOption** object that has an **IdleTimeout** value.</span></span> <span data-ttu-id="638a0-290">Однако значение **IdleTimeout** объекта **SessionOption** и значение **IdleTimeout** переменной $PSSessionOption не учитываются при соединении с **PSSession** .</span><span class="sxs-lookup"><span data-stu-id="638a0-290">However, the **IdleTimeout** value of the **SessionOption** object and the **IdleTimeout** value of the $PSSessionOption variable are ignored when connecting to a **PSSession** .</span></span>

  <span data-ttu-id="638a0-291">Можно задать и изменить время ожидания простоя **сеанса PSSession** при создании **сеанса PSSession** с помощью командлетов **New-PSSession** или **Invoke-Command** , а также при отключении от **сеанса PSSession** .</span><span class="sxs-lookup"><span data-stu-id="638a0-291">You can set and change the idle time-out of a **PSSession** when you create the **PSSession** , by using the **New-PSSession** or **Invoke-Command** cmdlets, and when you disconnect from the **PSSession** .</span></span>

  <span data-ttu-id="638a0-292">Свойство **IdleTimeout** для сеанса **PSSession** очень важно для отключенных сеансов, так как оно определяет, как долго отключенный сеанс сохраняется на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="638a0-292">The **IdleTimeout** property of a **PSSession** is critical to disconnected sessions, because it determines how long a disconnected session is maintained on the remote computer.</span></span>
<span data-ttu-id="638a0-293">Отключенные сеансы считаются находящимися в режиме простоя с момента их отключения, даже если в них выполняются команды.</span><span class="sxs-lookup"><span data-stu-id="638a0-293">Disconnected sessions are considered to be idle from the moment that they are disconnected, even if commands are running in the disconnected session.</span></span>

## <span data-ttu-id="638a0-294">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="638a0-294">RELATED LINKS</span></span>

[<span data-ttu-id="638a0-295">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="638a0-295">Disconnect-PSSession</span></span>](Disconnect-PSSession.md)

[<span data-ttu-id="638a0-296">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="638a0-296">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="638a0-297">Exit-PSSession;</span><span class="sxs-lookup"><span data-stu-id="638a0-297">Exit-PSSession</span></span>](Exit-PSSession.md)

[<span data-ttu-id="638a0-298">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="638a0-298">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="638a0-299">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="638a0-299">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="638a0-300">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="638a0-300">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="638a0-301">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="638a0-301">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="638a0-302">New-PSTransportOption</span><span class="sxs-lookup"><span data-stu-id="638a0-302">New-PSTransportOption</span></span>](New-PSTransportOption.md)

[<span data-ttu-id="638a0-303">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="638a0-303">Receive-PSSession</span></span>](Receive-PSSession.md)

[<span data-ttu-id="638a0-304">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="638a0-304">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="638a0-305">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="638a0-305">Remove-PSSession</span></span>](Remove-PSSession.md)

