---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 05/15/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-pssession?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSSession
ms.openlocfilehash: e06eaaa3b6042a2105462adfc2ba8f0a4867f045
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600675"
---
# <span data-ttu-id="35184-102">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="35184-102">Get-PSSession</span></span>

## <span data-ttu-id="35184-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="35184-103">SYNOPSIS</span></span>
<span data-ttu-id="35184-104">Получает сеансы PowerShell на локальных и удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="35184-104">Gets the PowerShell sessions on local and remote computers.</span></span>

## <span data-ttu-id="35184-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="35184-105">SYNTAX</span></span>

### <span data-ttu-id="35184-106">Имя (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="35184-106">Name (Default)</span></span>

```
Get-PSSession [-Name <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="35184-107">ИмяКомпьютера</span><span class="sxs-lookup"><span data-stu-id="35184-107">ComputerName</span></span>

```
Get-PSSession [-ComputerName] <String[]> [-ApplicationName <String>] [-ConfigurationName <String>]
 [-Name <String[]>] [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [-Port <Int32>] [-UseSSL] [-ThrottleLimit <Int32>]
 [-State <SessionFilterState>] [-SessionOption <PSSessionOption>] [<CommonParameters>]
```

### <span data-ttu-id="35184-108">компутеринстанцеид</span><span class="sxs-lookup"><span data-stu-id="35184-108">ComputerInstanceId</span></span>

```
Get-PSSession [-ComputerName] <String[]> [-ApplicationName <String>] [-ConfigurationName <String>]
 -InstanceId <Guid[]> [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [-Port <Int32>] [-UseSSL] [-ThrottleLimit <Int32>]
 [-State <SessionFilterState>] [-SessionOption <PSSessionOption>] [<CommonParameters>]
```

### <span data-ttu-id="35184-109">ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="35184-109">ConnectionUri</span></span>

```
Get-PSSession [-ConnectionUri] <Uri[]> [-ConfigurationName <String>] [-AllowRedirection] [-Name <String[]>]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [-ThrottleLimit <Int32>] [-State <SessionFilterState>] [-SessionOption <PSSessionOption>] [<CommonParameters>]
```

### <span data-ttu-id="35184-110">коннектионуриинстанцеид</span><span class="sxs-lookup"><span data-stu-id="35184-110">ConnectionUriInstanceId</span></span>

```
Get-PSSession [-ConnectionUri] <Uri[]> [-ConfigurationName <String>] [-AllowRedirection] -InstanceId <Guid[]>
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [-ThrottleLimit <Int32>] [-State <SessionFilterState>] [-SessionOption <PSSessionOption>] [<CommonParameters>]
```

### <span data-ttu-id="35184-111">вмнамеинстанцеид</span><span class="sxs-lookup"><span data-stu-id="35184-111">VMNameInstanceId</span></span>

```
Get-PSSession [-ConfigurationName <String>] -InstanceId <Guid[]> [-State <SessionFilterState>]
 -VMName <String[]> [<CommonParameters>]
```

### <span data-ttu-id="35184-112">ContainerId</span><span class="sxs-lookup"><span data-stu-id="35184-112">ContainerId</span></span>

```
Get-PSSession [-ConfigurationName <String>] [-Name <String[]>] [-State <SessionFilterState>]
 -ContainerId <String[]> [<CommonParameters>]
```

### <span data-ttu-id="35184-113">контаинеридинстанцеид</span><span class="sxs-lookup"><span data-stu-id="35184-113">ContainerIdInstanceId</span></span>

```
Get-PSSession [-ConfigurationName <String>] -InstanceId <Guid[]> [-State <SessionFilterState>]
 -ContainerId <String[]> [<CommonParameters>]
```

### <span data-ttu-id="35184-114">VMId</span><span class="sxs-lookup"><span data-stu-id="35184-114">VMId</span></span>

```
Get-PSSession [-ConfigurationName <String>] [-Name <String[]>] [-State <SessionFilterState>] -VMId <Guid[]>
 [<CommonParameters>]
```

### <span data-ttu-id="35184-115">вмидинстанцеид</span><span class="sxs-lookup"><span data-stu-id="35184-115">VMIdInstanceId</span></span>

```
Get-PSSession [-ConfigurationName <String>] -InstanceId <Guid[]> [-State <SessionFilterState>] -VMId <Guid[]>
 [<CommonParameters>]
```

### <span data-ttu-id="35184-116">VMName</span><span class="sxs-lookup"><span data-stu-id="35184-116">VMName</span></span>

```
Get-PSSession [-ConfigurationName <String>] [-Name <String[]>] [-State <SessionFilterState>] -VMName <String[]>
 [<CommonParameters>]
```

### <span data-ttu-id="35184-117">InstanceId</span><span class="sxs-lookup"><span data-stu-id="35184-117">InstanceId</span></span>

```
Get-PSSession [-InstanceId <Guid[]>] [<CommonParameters>]
```

### <span data-ttu-id="35184-118">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="35184-118">Id</span></span>

```
Get-PSSession [-Id] <Int32[]> [<CommonParameters>]
```

## <span data-ttu-id="35184-119">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="35184-119">DESCRIPTION</span></span>

<span data-ttu-id="35184-120">`Get-PSSession`Командлет получает управляемые пользователем сеансы PowerShell (**PSSession**) на локальных и удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="35184-120">The `Get-PSSession` cmdlet gets the user-managed PowerShell sessions (**PSSessions**) on local and remote computers.</span></span>

<span data-ttu-id="35184-121">Начиная с Windows PowerShell 3,0, сеансы хранятся на компьютерах на удаленной стороне каждого подключения.</span><span class="sxs-lookup"><span data-stu-id="35184-121">Starting in Windows PowerShell 3.0, sessions are stored on the computers at the remote end of each connection.</span></span> <span data-ttu-id="35184-122">Параметры **ComputerName** или **ConnectionURI** можно использовать `Get-PSSession` для получения сеансов, подключающихся к локальному компьютеру или удаленным компьютерам, даже если они не были созданы в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="35184-122">You can use the **ComputerName** or **ConnectionUri** parameters of `Get-PSSession` to get the sessions that connect to the local computer or remote computers, even if they were not created in the current session.</span></span>

<span data-ttu-id="35184-123">Без параметров `Get-PSSession` возвращает все сеансы, которые были созданы в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="35184-123">Without parameters, `Get-PSSession` gets all sessions that were created in the current session.</span></span>

<span data-ttu-id="35184-124">Используйте параметры фильтрации, в том числе **Name**, **ID**, **InstanceId**, **State**, **applicationName** и **configurationName** , чтобы выбрать из сеансов, которые `Get-PSSession` возвращает.</span><span class="sxs-lookup"><span data-stu-id="35184-124">Use the filtering parameters, including **Name**, **ID**, **InstanceID**, **State**, **ApplicationName**, and **ConfigurationName** to select from among the sessions that `Get-PSSession` returns.</span></span>

<span data-ttu-id="35184-125">Используйте оставшиеся параметры для настройки временного подключения, в котором `Get-PSSession` выполняется команда при использовании параметров **ComputerName** или **ConnectionURI** .</span><span class="sxs-lookup"><span data-stu-id="35184-125">Use the remaining parameters to configure the temporary connection in which the `Get-PSSession` command runs when you use the **ComputerName** or **ConnectionUri** parameters.</span></span>

<span data-ttu-id="35184-126">Примечание. в Windows PowerShell 2,0 без параметров `Get-PSSession` получает все сеансы, которые были созданы в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="35184-126">NOTE: In Windows PowerShell 2.0, without parameters, `Get-PSSession` gets all sessions that were created in the current session.</span></span> <span data-ttu-id="35184-127">Параметр **ComputerName** получает сеансы, которые были созданы в текущем сеансе и подключаются к указанному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="35184-127">The **ComputerName** parameter gets sessions that were created in the current session and connect to the specified computer.</span></span>

<span data-ttu-id="35184-128">Дополнительные сведения о сеансах PowerShell см. в разделе [about_PSSessions](about/about_PSSessions.md).</span><span class="sxs-lookup"><span data-stu-id="35184-128">For more information about PowerShell sessions, see [about_PSSessions](about/about_PSSessions.md).</span></span>

## <span data-ttu-id="35184-129">Примеры</span><span class="sxs-lookup"><span data-stu-id="35184-129">EXAMPLES</span></span>

### <span data-ttu-id="35184-130">Пример 1. получение сеансов, созданных в текущем сеансе</span><span class="sxs-lookup"><span data-stu-id="35184-130">Example 1: Get sessions created in the current session</span></span>

```powershell
Get-PSSession
```

<span data-ttu-id="35184-131">Эта команда возвращает все **PSSession** , созданные в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="35184-131">This command gets all of the **PSSessions** that were created in the current session.</span></span> <span data-ttu-id="35184-132">Он не получает **PSSession** , которые были созданы в других сеансах или на других компьютерах, даже если они подключаются к этому компьютеру.</span><span class="sxs-lookup"><span data-stu-id="35184-132">It does not get **PSSessions** that were created in other sessions or on other computers, even if they connect to this computer.</span></span>

### <span data-ttu-id="35184-133">Пример 2. получение сеансов, подключенных к локальному компьютеру</span><span class="sxs-lookup"><span data-stu-id="35184-133">Example 2: Get sessions connected to the local computer</span></span>

```powershell
Get-PSSession -ComputerName "localhost"
```

<span data-ttu-id="35184-134">Эта команда возвращает **PSSession** , подключенные к локальному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="35184-134">This command gets the **PSSessions** that are connected to the local computer.</span></span> <span data-ttu-id="35184-135">Чтобы указать локальный компьютер, введите имя компьютера, localhost или точку (.)</span><span class="sxs-lookup"><span data-stu-id="35184-135">To indicate the local computer, type the computer name, localhost, or a dot (.)</span></span>

<span data-ttu-id="35184-136">Эта команда возвращает все сеансы на локальном компьютере, даже если они были созданы в других сеансах или на других компьютерах.</span><span class="sxs-lookup"><span data-stu-id="35184-136">The command returns all of the sessions on the local computer, even if they were created in different sessions or on different computers.</span></span>

### <span data-ttu-id="35184-137">Пример 3. получение сеансов, подключенных к компьютеру</span><span class="sxs-lookup"><span data-stu-id="35184-137">Example 3: Get sessions connected to a computer</span></span>

```powershell
Get-PSSession -ComputerName "Server02"
```

```Output
 Id Name            ComputerName    State         ConfigurationName     Availability
 -- ----            ------------    -----         -----------------     ------------
  2 Session3        Server02       Disconnected  ITTasks                       Busy
  1 ScheduledJobs   Server02       Opened        Microsoft.PowerShell     Available
  3 Test            Server02       Disconnected  Microsoft.PowerShell          Busy
```

<span data-ttu-id="35184-138">Эта команда возвращает **PSSession** , подключенные к компьютеру Server02.</span><span class="sxs-lookup"><span data-stu-id="35184-138">This command gets the **PSSessions** that are connected to the Server02 computer.</span></span>

<span data-ttu-id="35184-139">Эта команда возвращает все сеансы на компьютере Server02, даже если они были созданы в других сеансах или на других компьютерах.</span><span class="sxs-lookup"><span data-stu-id="35184-139">The command returns all of the sessions on Server02, even if they were created in different sessions or on different computers.</span></span>

<span data-ttu-id="35184-140">Выходные данные показывают, что два сеансы находятся в отключенном состоянии с доступностью "Занято".</span><span class="sxs-lookup"><span data-stu-id="35184-140">The output shows that two of the sessions have a Disconnected state and a Busy availability.</span></span> <span data-ttu-id="35184-141">Они были созданы в различных сеансах и в настоящее время используются.</span><span class="sxs-lookup"><span data-stu-id="35184-141">They were created in different sessions and are currently in use.</span></span> <span data-ttu-id="35184-142">Сеанс ScheduledJobs, который открыт и доступен, был создан в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="35184-142">The ScheduledJobs session, which is Opened and Available, was created in the current session.</span></span>

### <span data-ttu-id="35184-143">Пример 4. Сохранение результатов выполнения этой команды</span><span class="sxs-lookup"><span data-stu-id="35184-143">Example 4: Save results of this command</span></span>

```powershell
New-PSSession -ComputerName Server01, Server02, Server03
$s1, $s2, $s3 = Get-PSSession
```

<span data-ttu-id="35184-144">В этом примере показано, как сохранить результаты `Get-PSSession` команды в нескольких переменных.</span><span class="sxs-lookup"><span data-stu-id="35184-144">This example shows how to save the results of a `Get-PSSession` command in multiple variables.</span></span>

<span data-ttu-id="35184-145">Первая команда использует `New-PSSession` командлет для создания **PSSession** на трех удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="35184-145">The first command uses the `New-PSSession` cmdlet to create **PSSessions** on three remote computers.</span></span>

<span data-ttu-id="35184-146">Вторая команда использует `Get-PSSession` командлет для получения трех **PSSession**.</span><span class="sxs-lookup"><span data-stu-id="35184-146">The second command uses a `Get-PSSession` cmdlet to get the three **PSSessions**.</span></span> <span data-ttu-id="35184-147">Затем он сохраняет каждую из **PSSession** в отдельной переменной.</span><span class="sxs-lookup"><span data-stu-id="35184-147">It then saves each of the **PSSessions** in a separate variable.</span></span>

<span data-ttu-id="35184-148">Когда PowerShell назначает массив объектов массиву переменных, он присваивает первому объекту первую переменную, второй объект второй переменной и т. д.</span><span class="sxs-lookup"><span data-stu-id="35184-148">When PowerShell assigns an array of objects to an array of variables, it assigns the first object to the first variable, the second object to the second variable, and so on.</span></span> <span data-ttu-id="35184-149">Если объектов больше, чем переменных, все оставшиеся объекты назначаются последней переменной в массиве.</span><span class="sxs-lookup"><span data-stu-id="35184-149">If there are more objects than variables, it assigns all remaining objects to the last variable in the array.</span></span> <span data-ttu-id="35184-150">Если переменных больше, чем объектов, дополнительные переменные не используются.</span><span class="sxs-lookup"><span data-stu-id="35184-150">If there are more variables than objects, the extra variables are not used.</span></span>

### <span data-ttu-id="35184-151">Пример 5. Удаление сеанса с помощью идентификатора экземпляра</span><span class="sxs-lookup"><span data-stu-id="35184-151">Example 5: Delete a session by using an instance ID</span></span>

```powershell
Get-PSSession | Format-Table -Property ComputerName, InstanceID
$s = Get-PSSession -InstanceID a786be29-a6bb-40da-80fb-782c67f7db0f
Remove-PSSession -Session $s
```

<span data-ttu-id="35184-152">В этом примере показано, как получить **PSSession** с помощью идентификатора экземпляра, а затем удалить **PSSession**.</span><span class="sxs-lookup"><span data-stu-id="35184-152">This example shows how to get a **PSSession** by using its instance ID, and then to delete the **PSSession**.</span></span>

<span data-ttu-id="35184-153">Первая команда получает все **PSSession** , созданные в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="35184-153">The first command gets all of the **PSSessions** that were created in the current session.</span></span> <span data-ttu-id="35184-154">Он отправляет **PSSession** командлету Format-Table, который отображает свойства **ComputerName** и **InstanceId** каждого **сеанса PSSession**.</span><span class="sxs-lookup"><span data-stu-id="35184-154">It sends the **PSSessions** to the Format-Table cmdlet, which displays the **ComputerName** and **InstanceID** properties of each **PSSession**.</span></span>

<span data-ttu-id="35184-155">Вторая команда использует командлет, `Get-PSSession` чтобы получить определенный **сеанс PSSession** и сохранить его в `$s` переменной.</span><span class="sxs-lookup"><span data-stu-id="35184-155">The second command uses the `Get-PSSession` cmdlet to get a particular **PSSession** and to save it in the `$s` variable.</span></span> <span data-ttu-id="35184-156">Команда использует параметр **InstanceId** для задания **сеанса PSSession**.</span><span class="sxs-lookup"><span data-stu-id="35184-156">The command uses the **InstanceID** parameter to identify the **PSSession**.</span></span>

<span data-ttu-id="35184-157">Третья команда использует командлет Remove-PSSession для удаления **сеанса PSSession** в `$s` переменной.</span><span class="sxs-lookup"><span data-stu-id="35184-157">The third command uses the Remove-PSSession cmdlet to delete the **PSSession** in the `$s` variable.</span></span>

### <span data-ttu-id="35184-158">Пример 6. Получение сеанса с определенным именем</span><span class="sxs-lookup"><span data-stu-id="35184-158">Example 6: Get a session that has a particular name</span></span>

<span data-ttu-id="35184-159">Команды в этом примере находят сеанс, имя которого имеет определенный формат, использует конфигурацию сеанса и затем подключается к сеансу.</span><span class="sxs-lookup"><span data-stu-id="35184-159">The commands in this example find a session that has a particular name format and uses a particular session configuration and then connect to the session.</span></span> <span data-ttu-id="35184-160">С помощью подобной команды можно найти сеанс, в котором коллега запустил задачу, и подключиться к нему для завершения задачи.</span><span class="sxs-lookup"><span data-stu-id="35184-160">You can use a command like this one to find a session in which a colleague started a task and connect to finish the task.</span></span>

```powershell
Get-PSSession -ComputerName Server02, Server12 -Name BackupJob* -ConfigurationName ITTasks -SessionOption @{OperationTimeout=240000}
```

```Output
 Id Name            ComputerName    State         ConfigurationName     Availability
 -- ----            ------------    -----         -----------------     ------------
  3 BackupJob04     Server02        Disconnected        ITTasks                  None
```

```powershell
$s = Get-PSSession -ComputerName Server02 -Name BackupJob04 -ConfigurationName ITTasks | Connect-PSSession
$s
```

```Output
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 5 BackupJob04     Server02        Opened        ITTasks                  Available
```

<span data-ttu-id="35184-161">Первая команда получает сеансы на удаленных компьютерах Server02 и Server12, имена которых начинаются с Баккупжоб и используют конфигурацию сеанса ITTasks. Команда использует параметр **Name** для указания шаблона имени, а параметр **configurationName** — для указания конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="35184-161">The first command gets sessions on the Server02 and Server12 remote computers that have names that begin with BackupJob and use the ITTasks session configuration.The command uses the **Name** parameter to specify the name pattern and the **ConfigurationName** parameter to specify the session configuration.</span></span> <span data-ttu-id="35184-162">Значение параметра **SessionOption** — это хэш-таблица, которая устанавливает для параметра **OperationTimeout** значение 240 000 мс (4 минуты).</span><span class="sxs-lookup"><span data-stu-id="35184-162">The value of the **SessionOption** parameter is a hash table that sets the value of the **OperationTimeout** to 240000 milliseconds (4 minutes).</span></span> <span data-ttu-id="35184-163">Этот параметр дает команде больше времени на завершение. Параметры **configurationName** и **SessionOption** используются для настройки временных сеансов, в которых `Get-PSSession` командлет выполняется на каждом компьютере. Выходные данные показывают, что команда возвращает сеанс BackupJob04.</span><span class="sxs-lookup"><span data-stu-id="35184-163">This setting gives the command more time to complete.The **ConfigurationName** and **SessionOption** parameters are used to configure the temporary sessions in which the `Get-PSSession` cmdlet runs on each computer.The output shows that the command returns the BackupJob04 session.</span></span> <span data-ttu-id="35184-164">Сеанс отключен, а уровень **доступности** равен None, что означает, что он не используется.</span><span class="sxs-lookup"><span data-stu-id="35184-164">The session is disconnected and the **Availability** is None, which indicates that it is not in use.</span></span>

<span data-ttu-id="35184-165">Вторая команда использует `Get-PSSession` командлет для перехода к сеансу BackupJob04 и командлету Connect-PSSession для подключения к сеансу.</span><span class="sxs-lookup"><span data-stu-id="35184-165">The second command uses the `Get-PSSession` cmdlet to get to the BackupJob04 session and the Connect-PSSession cmdlet to connect to the session.</span></span> <span data-ttu-id="35184-166">Сеанс сохраняется в переменную $s.</span><span class="sxs-lookup"><span data-stu-id="35184-166">The command saves the session in the $s variable.</span></span>

<span data-ttu-id="35184-167">Третья команда получает сеанс в переменной $s.</span><span class="sxs-lookup"><span data-stu-id="35184-167">The third command gets the session in the $s variable.</span></span> <span data-ttu-id="35184-168">Выходные данные показывают, что `Connect-PSSession` команда выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="35184-168">The output shows that the `Connect-PSSession` command was successful.</span></span> <span data-ttu-id="35184-169">Сеанс находится в состоянии **Opened** и доступен для использования.</span><span class="sxs-lookup"><span data-stu-id="35184-169">The session is in the **Opened** state and is available for use.</span></span>

### <span data-ttu-id="35184-170">Пример 7. Получение сеанса с помощью его идентификатора</span><span class="sxs-lookup"><span data-stu-id="35184-170">Example 7: Get a session by using its ID</span></span>

```powershell
Get-PSSession -Id 2
```

<span data-ttu-id="35184-171">Эта команда получает **сеанс PSSession** с идентификатором 2.</span><span class="sxs-lookup"><span data-stu-id="35184-171">This command gets the **PSSession** with ID 2.</span></span> <span data-ttu-id="35184-172">Так как значение свойства **ID** уникально только в текущем сеансе, параметр **ID** допустим только для локальных команд.</span><span class="sxs-lookup"><span data-stu-id="35184-172">Because the value of the **ID** property is unique only in the current session, the **Id** parameter is valid only for local commands.</span></span>

## <span data-ttu-id="35184-173">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="35184-173">PARAMETERS</span></span>

### <span data-ttu-id="35184-174">-AllowRedirection</span><span class="sxs-lookup"><span data-stu-id="35184-174">-AllowRedirection</span></span>

<span data-ttu-id="35184-175">Указывает, что этот командлет разрешает перенаправление этого соединения в альтернативный универсальный код ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="35184-175">Indicates that this cmdlet allows redirection of this connection to an alternate Uniform Resource Identifier (URI).</span></span> <span data-ttu-id="35184-176">По умолчанию PowerShell не перенаправляет соединения.</span><span class="sxs-lookup"><span data-stu-id="35184-176">By default, PowerShell does not redirect connections.</span></span>

<span data-ttu-id="35184-177">Этот параметр настраивает временное подключение, созданное для выполнения `Get-PSSession` команды с параметром **ConnectionURI** .</span><span class="sxs-lookup"><span data-stu-id="35184-177">This parameter configures the temporary connection that is created to run a `Get-PSSession` command with the **ConnectionUri** parameter.</span></span>

<span data-ttu-id="35184-178">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="35184-178">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ConnectionUriInstanceId, ConnectionUri
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="35184-179">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="35184-179">-ApplicationName</span></span>

<span data-ttu-id="35184-180">Указывает имя приложения.</span><span class="sxs-lookup"><span data-stu-id="35184-180">Specifies the name of an application.</span></span> <span data-ttu-id="35184-181">Этот командлет подключается только к сеансам, использующим указанное приложение.</span><span class="sxs-lookup"><span data-stu-id="35184-181">This cmdlet connects only to sessions that use the specified application.</span></span>

<span data-ttu-id="35184-182">Введите сегмент имени приложения URI подключения.</span><span class="sxs-lookup"><span data-stu-id="35184-182">Enter the application name segment of the connection URI.</span></span> <span data-ttu-id="35184-183">Например, в следующем URI соединения имя приложения — WSMan: `http://localhost:5985/WSMAN` .</span><span class="sxs-lookup"><span data-stu-id="35184-183">For example, in the following connection URI, the application name is WSMan: `http://localhost:5985/WSMAN`.</span></span> <span data-ttu-id="35184-184">Имя приложения сеанса хранится в свойстве сеанса **Runspace.ConnectionInfo.AppName**.</span><span class="sxs-lookup"><span data-stu-id="35184-184">The application name of a session is stored in the **Runspace.ConnectionInfo.AppName** property of the session.</span></span>

<span data-ttu-id="35184-185">Значение этого параметра используется для выбора и фильтрации сеансов.</span><span class="sxs-lookup"><span data-stu-id="35184-185">The value of this parameter is used to select and filter sessions.</span></span> <span data-ttu-id="35184-186">Оно не изменяет приложение, которое использует сеанс.</span><span class="sxs-lookup"><span data-stu-id="35184-186">It does not change the application that the session uses.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerInstanceId, ComputerName
Aliases:

Required: False
Position: Named
Default value: All sessions
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="35184-187">-Authentication</span><span class="sxs-lookup"><span data-stu-id="35184-187">-Authentication</span></span>

<span data-ttu-id="35184-188">Указывает механизм, используемый для проверки подлинности учетных данных для сеанса, в котором `Get-PSSession` выполняется команда.</span><span class="sxs-lookup"><span data-stu-id="35184-188">Specifies the mechanism that is used to authenticate credentials for the session in which the `Get-PSSession` command runs.</span></span>

<span data-ttu-id="35184-189">Этот параметр настраивает временное подключение, созданное для выполнения `Get-PSSession` команды с параметром **ComputerName** или **ConnectionURI** .</span><span class="sxs-lookup"><span data-stu-id="35184-189">This parameter configures the temporary connection that is created to run a `Get-PSSession` command with the **ComputerName** or **ConnectionUri** parameter.</span></span>

<span data-ttu-id="35184-190">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="35184-190">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="35184-191">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="35184-191">Default</span></span>
- <span data-ttu-id="35184-192">Basic</span><span class="sxs-lookup"><span data-stu-id="35184-192">Basic</span></span>
- <span data-ttu-id="35184-193">CredSSP</span><span class="sxs-lookup"><span data-stu-id="35184-193">Credssp</span></span>
- <span data-ttu-id="35184-194">Digest (дайджест)</span><span class="sxs-lookup"><span data-stu-id="35184-194">Digest</span></span>
- <span data-ttu-id="35184-195">Kerberos</span><span class="sxs-lookup"><span data-stu-id="35184-195">Kerberos</span></span>
- <span data-ttu-id="35184-196">Согласование</span><span class="sxs-lookup"><span data-stu-id="35184-196">Negotiate</span></span>
- <span data-ttu-id="35184-197">NegotiateWithImplicitCredential.</span><span class="sxs-lookup"><span data-stu-id="35184-197">NegotiateWithImplicitCredential.</span></span>

<span data-ttu-id="35184-198">Значение по умолчанию — Default.</span><span class="sxs-lookup"><span data-stu-id="35184-198">The default value is Default.</span></span>

<span data-ttu-id="35184-199">Дополнительные сведения о значениях этого параметра см. в разделе [AuthenticationMechanism enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span><span class="sxs-lookup"><span data-stu-id="35184-199">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

<span data-ttu-id="35184-200">ВНИМАНИЕ! проверка подлинности поставщика поддержки безопасности учетных данных (CredSSP), в которой учетные данные пользователя передаются на удаленный компьютер для проверки подлинности, предназначена для команд, требующих проверки подлинности в нескольких ресурсах, таких как доступ к удаленной сетевой папке.</span><span class="sxs-lookup"><span data-stu-id="35184-200">CAUTION: Credential Security Support Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="35184-201">Этот механизм повышает риск безопасности удаленной операции.</span><span class="sxs-lookup"><span data-stu-id="35184-201">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="35184-202">Если удаленный компьютер скомпрометирован, учетные данные, передаваемые ему, могут использоваться для управления сетевым сеансом.</span><span class="sxs-lookup"><span data-stu-id="35184-202">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

<span data-ttu-id="35184-203">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="35184-203">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ComputerInstanceId, ComputerName, ConnectionUriInstanceId, ConnectionUri
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="35184-204">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="35184-204">-CertificateThumbprint</span></span>

<span data-ttu-id="35184-205">Указывает сертификат цифрового открытого ключа (X509) учетной записи пользователя, имеющей разрешение на создание сеанса, в котором `Get-PSSession` выполняется команда.</span><span class="sxs-lookup"><span data-stu-id="35184-205">Specifies the digital public key certificate (X509) of a user account that has permission to create the session in which the `Get-PSSession` command runs.</span></span> <span data-ttu-id="35184-206">Введите отпечаток сертификата.</span><span class="sxs-lookup"><span data-stu-id="35184-206">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="35184-207">Этот параметр настраивает временное подключение, созданное для выполнения `Get-PSSession` команды с параметром **ComputerName** или **ConnectionURI** .</span><span class="sxs-lookup"><span data-stu-id="35184-207">This parameter configures the temporary connection that is created to run a `Get-PSSession` command with the **ComputerName** or **ConnectionUri** parameter.</span></span>

<span data-ttu-id="35184-208">Сертификаты используются при проверке подлинности на основе сертификата клиента.</span><span class="sxs-lookup"><span data-stu-id="35184-208">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="35184-209">Они могут сопоставляться только с учетными записями локальных пользователей и не работают с учетными записями доменов.</span><span class="sxs-lookup"><span data-stu-id="35184-209">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="35184-210">Чтобы получить отпечаток сертификата, используйте команду Get-Item или Get-ChildItem на диске с сертификатом PowerShell:.</span><span class="sxs-lookup"><span data-stu-id="35184-210">To get a certificate thumbprint, use a Get-Item or Get-ChildItem command in the PowerShell Cert: drive.</span></span>

<span data-ttu-id="35184-211">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="35184-211">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerInstanceId, ComputerName, ConnectionUriInstanceId, ConnectionUri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="35184-212">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="35184-212">-ComputerName</span></span>

<span data-ttu-id="35184-213">Указывает массив имен компьютеров.</span><span class="sxs-lookup"><span data-stu-id="35184-213">Specifies an array of names of computers.</span></span> <span data-ttu-id="35184-214">Возвращает сеансов, которые подключаются к указанным компьютерам.</span><span class="sxs-lookup"><span data-stu-id="35184-214">Gets the sessions that connect to the specified computers.</span></span>
<span data-ttu-id="35184-215">Подстановочные знаки не допускаются.</span><span class="sxs-lookup"><span data-stu-id="35184-215">Wildcard characters are not permitted.</span></span> <span data-ttu-id="35184-216">Значение по умолчанию отсутствует.</span><span class="sxs-lookup"><span data-stu-id="35184-216">There is no default value.</span></span>

<span data-ttu-id="35184-217">Начиная с Windows PowerShell 3,0, объекты **PSSession** хранятся на компьютерах на удаленной стороне каждого подключения.</span><span class="sxs-lookup"><span data-stu-id="35184-217">Beginning in Windows PowerShell 3.0, **PSSession** objects are stored on the computers at the remote end of each connection.</span></span> <span data-ttu-id="35184-218">Чтобы получить сеансы на указанных компьютерах, PowerShell создает временное подключение к каждому компьютеру и выполняет `Get-PSSession` команду.</span><span class="sxs-lookup"><span data-stu-id="35184-218">To get the sessions on the specified computers, PowerShell creates a temporary connection to each computer and runs a `Get-PSSession` command.</span></span>

<span data-ttu-id="35184-219">Введите имя NetBIOS, IP-адрес или полное доменное имя одного или нескольких компьютеров.</span><span class="sxs-lookup"><span data-stu-id="35184-219">Type the NetBIOS name, an IP address, or a fully-qualified domain name of one or more computers.</span></span> <span data-ttu-id="35184-220">Чтобы указать локальный компьютер, введите имя компьютера, localhost или точку (.).</span><span class="sxs-lookup"><span data-stu-id="35184-220">To specify the local computer, type the computer name, localhost, or a dot (.).</span></span>

<span data-ttu-id="35184-221">Примечание. Этот параметр получает сеансы только с компьютеров, на которых выполняется Windows PowerShell 3,0 или более поздних версий PowerShell.</span><span class="sxs-lookup"><span data-stu-id="35184-221">Note: This parameter gets sessions only from computers that run Windows PowerShell 3.0 or later versions of PowerShell.</span></span> <span data-ttu-id="35184-222">Предыдущие версии не хранят сеансы.</span><span class="sxs-lookup"><span data-stu-id="35184-222">Earlier versions do not store sessions.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerInstanceId, ComputerName
Aliases: Cn

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="35184-223">-ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="35184-223">-ConfigurationName</span></span>

<span data-ttu-id="35184-224">Указывает имя конфигурации.</span><span class="sxs-lookup"><span data-stu-id="35184-224">Specifies the name of a configuration.</span></span> <span data-ttu-id="35184-225">Этот командлет получает только сеансы, в которых используется указанная конфигурация сеанса.</span><span class="sxs-lookup"><span data-stu-id="35184-225">This cmdlet gets only to sessions that use the specified session configuration.</span></span>

<span data-ttu-id="35184-226">Введите имя конфигурации или полное имя ресурса (URI) для конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="35184-226">Enter a configuration name or the fully qualified resource URI for a session configuration.</span></span> <span data-ttu-id="35184-227">Если указано только имя конфигурации, в начале добавляется следующий URI схемы: `http://schemas.microsoft.com/powershell` .</span><span class="sxs-lookup"><span data-stu-id="35184-227">If you specify only the configuration name, the following schema URI is prepended: `http://schemas.microsoft.com/powershell`.</span></span> <span data-ttu-id="35184-228">Имя конфигурации сеанса хранится в свойстве сеанса **ConfigurationName**.</span><span class="sxs-lookup"><span data-stu-id="35184-228">The configuration name of a session is stored in the **ConfigurationName** property of the session.</span></span>

<span data-ttu-id="35184-229">Значение этого параметра используется для выбора и фильтрации сеансов.</span><span class="sxs-lookup"><span data-stu-id="35184-229">The value of this parameter is used to select and filter sessions.</span></span> <span data-ttu-id="35184-230">Оно не изменяет конфигурацию, которую использует сеанс.</span><span class="sxs-lookup"><span data-stu-id="35184-230">It does not change the session configuration that the session uses.</span></span>

<span data-ttu-id="35184-231">Дополнительные сведения о конфигурациях сеансов см. в разделе [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="35184-231">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerInstanceId, ComputerName, ConnectionUriInstanceId, ConnectionUri, ContainerId, ContainerIdInstanceId, VMId, VMIdInstanceId, VMName, VMNameInstanceId
Aliases:

Required: False
Position: Named
Default value: All sessions
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="35184-232">-ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="35184-232">-ConnectionUri</span></span>

<span data-ttu-id="35184-233">Задает универсальный код ресурса (URI), определяющий конечную точку подключения для временного сеанса, в котором `Get-PSSession` выполняется команда.</span><span class="sxs-lookup"><span data-stu-id="35184-233">Specifies a URI that defines the connection endpoint for the temporary session in which the `Get-PSSession` command runs.</span></span> <span data-ttu-id="35184-234">Значение URI должно быть указано полностью.</span><span class="sxs-lookup"><span data-stu-id="35184-234">The URI must be fully qualified.</span></span>

<span data-ttu-id="35184-235">Этот параметр настраивает временное подключение, созданное для выполнения `Get-PSSession` команды с параметром **ConnectionURI** .</span><span class="sxs-lookup"><span data-stu-id="35184-235">This parameter configures the temporary connection that is created to run a `Get-PSSession` command with the **ConnectionUri** parameter.</span></span>

<span data-ttu-id="35184-236">Строки имеют следующий формат:</span><span class="sxs-lookup"><span data-stu-id="35184-236">The format of this string is:</span></span>

`<Transport>://<ComputerName>:<Port\>/<ApplicationName>`

<span data-ttu-id="35184-237">Значение по умолчанию: `http://localhost:5985/WSMAN` .</span><span class="sxs-lookup"><span data-stu-id="35184-237">The default value is: `http://localhost:5985/WSMAN`.</span></span>

<span data-ttu-id="35184-238">Если не указать **ConnectionURI**, можно использовать параметры **UseSSL**, **ComputerName**, **Port** и **applicationName** , чтобы указать значения **ConnectionURI** .</span><span class="sxs-lookup"><span data-stu-id="35184-238">If you do not specify a **ConnectionUri**, you can use the **UseSSL**, **ComputerName**, **Port**, and **ApplicationName** parameters to specify the **ConnectionURI** values.</span></span> <span data-ttu-id="35184-239">Допустимые значения для сегмента транспорта URI — HTTP и HTTPS.</span><span class="sxs-lookup"><span data-stu-id="35184-239">Valid values for the Transport segment of the URI are HTTP and HTTPS.</span></span> <span data-ttu-id="35184-240">Если указать URI подключения с сегментом Transport, но не указать порт, сеанс будет создан со стандартными портами: 80 для HTTP и 443 для HTTPS.</span><span class="sxs-lookup"><span data-stu-id="35184-240">If you specify a connection URI with a Transport segment, but do not specify a port, the session is created with standards ports: 80 for HTTP and 443 for HTTPS.</span></span> <span data-ttu-id="35184-241">Чтобы использовать порты по умолчанию для удаленного взаимодействия PowerShell, укажите порт 5985 для HTTP или 5986 для HTTPS.</span><span class="sxs-lookup"><span data-stu-id="35184-241">To use the default ports for PowerShell remoting, specify port 5985 for HTTP or 5986 for HTTPS.</span></span>

<span data-ttu-id="35184-242">Если конечный компьютер перенаправляет подключение к другому универсальному коду ресурса (URI), PowerShell предотвращает перенаправление, если в команде не используется параметр **AllowRedirection** .</span><span class="sxs-lookup"><span data-stu-id="35184-242">If the destination computer redirects the connection to a different URI, PowerShell prevents the redirection unless you use the **AllowRedirection** parameter in the command.</span></span>

<span data-ttu-id="35184-243">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="35184-243">This parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="35184-244">Этот параметр получает сеансы только с компьютеров, на которых выполняется Windows PowerShell 3,0 или более поздней версии Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="35184-244">This parameter gets sessions only from computers that run Windows PowerShell 3.0 or later versions of Windows PowerShell.</span></span> <span data-ttu-id="35184-245">Предыдущие версии не хранят сеансы.</span><span class="sxs-lookup"><span data-stu-id="35184-245">Earlier versions do not store sessions.</span></span>

```yaml
Type: System.Uri[]
Parameter Sets: ConnectionUriInstanceId, ConnectionUri
Aliases: URI, CU

Required: True
Position: 0
Default value: Http://localhost:5985/WSMAN
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="35184-246">-ContainerId</span><span class="sxs-lookup"><span data-stu-id="35184-246">-ContainerId</span></span>

<span data-ttu-id="35184-247">Указывает массив идентификаторов контейнеров.</span><span class="sxs-lookup"><span data-stu-id="35184-247">Specifies an array of IDs of containers.</span></span> <span data-ttu-id="35184-248">Этот командлет запускает интерактивный сеанс с каждым из указанных контейнеров.</span><span class="sxs-lookup"><span data-stu-id="35184-248">This cmdlet starts an interactive session with each of the specified containers.</span></span> <span data-ttu-id="35184-249">Используйте `docker ps` команду, чтобы получить список идентификаторов контейнеров.</span><span class="sxs-lookup"><span data-stu-id="35184-249">Use the `docker ps` command to get a list of container IDs.</span></span> <span data-ttu-id="35184-250">Дополнительные сведения см. в справке по команде [DOCKER PS](https://docs.docker.com/engine/reference/commandline/ps/) .</span><span class="sxs-lookup"><span data-stu-id="35184-250">For more information, see the help for the [docker ps](https://docs.docker.com/engine/reference/commandline/ps/) command.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ContainerId, ContainerIdInstanceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="35184-251">-Credential</span><span class="sxs-lookup"><span data-stu-id="35184-251">-Credential</span></span>

<span data-ttu-id="35184-252">Указывает учетные данные пользователя.</span><span class="sxs-lookup"><span data-stu-id="35184-252">Specifies a user credential.</span></span> <span data-ttu-id="35184-253">Этот командлет выполняет команду с разрешениями указанного пользователя.</span><span class="sxs-lookup"><span data-stu-id="35184-253">This cmdlet runs the command with the permissions of the specified user.</span></span> <span data-ttu-id="35184-254">Укажите учетную запись пользователя, имеющую разрешение на подключение к удаленному компьютеру, и выполните `Get-PSSession` команду.</span><span class="sxs-lookup"><span data-stu-id="35184-254">Specify a user account that has permission to connect to the remote computer and run a `Get-PSSession` command.</span></span> <span data-ttu-id="35184-255">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="35184-255">The default is the current user.</span></span>

<span data-ttu-id="35184-256">Введите имя пользователя, например **User01** или **Domain01\User01**, либо введите объект **PSCredential** , созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="35184-256">Type a user name, such as **User01** or **Domain01\User01**, or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="35184-257">Если ввести имя пользователя, будет предложено ввести пароль.</span><span class="sxs-lookup"><span data-stu-id="35184-257">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="35184-258">Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="35184-258">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="35184-259">Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="35184-259">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

<span data-ttu-id="35184-260">Этот параметр задает временное подключение, созданное для выполнения `Get-PSSession` команды с параметром **ComputerName** или **ConnectionURI** .</span><span class="sxs-lookup"><span data-stu-id="35184-260">This parameter configures to the temporary connection that is created to run a `Get-PSSession` command with the **ComputerName** or **ConnectionUri** parameter.</span></span>

<span data-ttu-id="35184-261">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="35184-261">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerInstanceId, ComputerName, ConnectionUriInstanceId, ConnectionUri
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="35184-262">-Id</span><span class="sxs-lookup"><span data-stu-id="35184-262">-Id</span></span>

<span data-ttu-id="35184-263">Указывает массив идентификаторов сеансов.</span><span class="sxs-lookup"><span data-stu-id="35184-263">Specifies an array of session IDs.</span></span> <span data-ttu-id="35184-264">Этот командлет возвращает только сеансы с указанными идентификаторами.</span><span class="sxs-lookup"><span data-stu-id="35184-264">This cmdlet gets only the sessions with the specified IDs.</span></span> <span data-ttu-id="35184-265">Введите один или несколько идентификаторов, разделенных запятыми, или используйте оператор Range (..), чтобы указать диапазон идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="35184-265">Type one or more IDs, separated by commas, or use the range operator (..) to specify a range of IDs.</span></span> <span data-ttu-id="35184-266">Параметр ID нельзя использовать вместе с параметром **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="35184-266">You cannot use the ID parameter together with the **ComputerName** parameter.</span></span>

<span data-ttu-id="35184-267">Идентификатор — это целое число, которое однозначно определяет управляемые пользователем сеансы в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="35184-267">An ID is an integer that uniquely identifies the user-managed sessions in the current session.</span></span> <span data-ttu-id="35184-268">Проще запомнить и ввести, чем **InstanceId**, но он уникален только в пределах текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="35184-268">It is easier to remember and type than the **InstanceId**, but it is unique only within the current session.</span></span> <span data-ttu-id="35184-269">Идентификатор сеанса хранится в свойстве ID сеанса.</span><span class="sxs-lookup"><span data-stu-id="35184-269">The ID of a session is stored in the ID property of the session.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: All sessions
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="35184-270">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="35184-270">-InstanceId</span></span>

<span data-ttu-id="35184-271">Указывает массив идентификаторов экземпляров сеансов.</span><span class="sxs-lookup"><span data-stu-id="35184-271">Specifies an array of instance IDs of sessions.</span></span> <span data-ttu-id="35184-272">Этот командлет возвращает только сеансы с указанными идентификаторами экземпляра.</span><span class="sxs-lookup"><span data-stu-id="35184-272">This cmdlet gets only the sessions with the specified instance IDs.</span></span>

<span data-ttu-id="35184-273">Идентификатор экземпляра — это GUID, однозначно определяющий сеанс на локальном или удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="35184-273">The instance ID is a GUID that uniquely identifies a session on a local or remote computer.</span></span> <span data-ttu-id="35184-274">Идентификатор **InstanceId** уникален, даже если в PowerShell работает несколько сеансов.</span><span class="sxs-lookup"><span data-stu-id="35184-274">The **InstanceID** is unique, even when you have multiple sessions running in PowerShell.</span></span>

<span data-ttu-id="35184-275">Идентификатор экземпляра сеанса хранится в свойстве сеанса **InstanceID**.</span><span class="sxs-lookup"><span data-stu-id="35184-275">The instance ID of a session is stored in the **InstanceID** property of the session.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: ComputerInstanceId, ConnectionUriInstanceId, ContainerIdInstanceId, VMIdInstanceId, VMNameInstanceId, InstanceId
Aliases:

Required: True (ComputerInstanceId, ConnectionUriInstanceId, ContainerIdInstanceId, VMIdInstanceId, VMNameInstanceId), False (InstanceId)
Position: Named
Default value: All sessions
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="35184-276">-Name</span><span class="sxs-lookup"><span data-stu-id="35184-276">-Name</span></span>

<span data-ttu-id="35184-277">Указывает массив имен сеансов.</span><span class="sxs-lookup"><span data-stu-id="35184-277">Specifies an array of session names.</span></span> <span data-ttu-id="35184-278">Этот командлет возвращает только сеансы с указанными понятными именами.</span><span class="sxs-lookup"><span data-stu-id="35184-278">This cmdlet gets only the sessions that have the specified friendly names.</span></span> <span data-ttu-id="35184-279">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="35184-279">Wildcard characters are permitted.</span></span>

<span data-ttu-id="35184-280">Понятное имя сеанса хранится в свойстве **Name**.</span><span class="sxs-lookup"><span data-stu-id="35184-280">The friendly name of a session is stored in the **Name** property of the session.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name, ComputerName, ConnectionUri, ContainerId, VMId, VMName
Aliases:

Required: False
Position: Named
Default value: All sessions
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="35184-281">-Port</span><span class="sxs-lookup"><span data-stu-id="35184-281">-Port</span></span>

<span data-ttu-id="35184-282">Указывает указанный сетевой порт, используемый для временного подключения, в котором `Get-PSSession` выполняется команда.</span><span class="sxs-lookup"><span data-stu-id="35184-282">Specifies the specified network port that is used for the temporary connection in which the `Get-PSSession` command runs.</span></span> <span data-ttu-id="35184-283">Для подключения к удаленному компьютеру требуется, чтобы он прослушивал порт, используемый соединением.</span><span class="sxs-lookup"><span data-stu-id="35184-283">To connect to a remote computer, the remote computer must be listening on the port that the connection uses.</span></span> <span data-ttu-id="35184-284">Порты по умолчанию — 5985, то есть порт WinRM для HTTP, а 5986 — порт WinRM для HTTPS.</span><span class="sxs-lookup"><span data-stu-id="35184-284">The default ports are 5985, which is the WinRM port for HTTP, and 5986, which is the WinRM port for HTTPS.</span></span>

<span data-ttu-id="35184-285">Прежде чем использовать альтернативный порт, необходимо настроить прослушиватель WinRM на удаленном компьютере для прослушивания по этому порту.</span><span class="sxs-lookup"><span data-stu-id="35184-285">Before using an alternate port, you must configure the WinRM listener on the remote computer to listen at that port.</span></span> <span data-ttu-id="35184-286">Чтобы настроить прослушиватель, введите следующие две команды в командной строке PowerShell:</span><span class="sxs-lookup"><span data-stu-id="35184-286">To configure the listener, type the following two commands at the PowerShell prompt:</span></span>

`Remove-Item -Path WSMan:\Localhost\listener\listener* -Recurse`

`New-Item -Path WSMan:\Localhost\listener -Transport http -Address * -Port \<port-number\>`

<span data-ttu-id="35184-287">Этот параметр задает временное подключение, созданное для выполнения `Get-PSSession` команды с параметром **ComputerName** или **ConnectionURI** .</span><span class="sxs-lookup"><span data-stu-id="35184-287">This parameter configures to the temporary connection that is created to run a `Get-PSSession` command with the **ComputerName** or **ConnectionUri** parameter.</span></span>

<span data-ttu-id="35184-288">Не используйте параметр **Port**, если этого можно избежать.</span><span class="sxs-lookup"><span data-stu-id="35184-288">Do not use the **Port** parameter unless you must.</span></span> <span data-ttu-id="35184-289">**Порт** , заданный в команде, применяется ко всем компьютерам или сеансам, на которых выполняется команда.</span><span class="sxs-lookup"><span data-stu-id="35184-289">The **Port** set in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="35184-290">Альтернативный порт может помешать выполнению команды на всех компьютерах.</span><span class="sxs-lookup"><span data-stu-id="35184-290">An alternate port setting might prevent the command from running on all computers.</span></span>

<span data-ttu-id="35184-291">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="35184-291">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ComputerInstanceId, ComputerName
Aliases:

Required: False
Position: Named
Default value: 5985, 5986
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="35184-292">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="35184-292">-SessionOption</span></span>

<span data-ttu-id="35184-293">Задает дополнительные параметры для сеанса.</span><span class="sxs-lookup"><span data-stu-id="35184-293">Specifies advanced options for the session.</span></span> <span data-ttu-id="35184-294">Введите объект **SessionOption**, например объект, созданный с помощью командлета New-PSSessionOption, или хэш-таблицу, где ключи — это имена параметров сеанса, а значения — это значения параметров сеанса.</span><span class="sxs-lookup"><span data-stu-id="35184-294">Enter a **SessionOption** object, such as one that you create by using the New-PSSessionOption cmdlet, or a hash table in which the keys are session option names and the values are session option values.</span></span>

<span data-ttu-id="35184-295">Значения по умолчанию для параметров определяются значением привилегированной переменной $PSSessionOption, если оно задано.</span><span class="sxs-lookup"><span data-stu-id="35184-295">The default values for the options are determined by the value of the $PSSessionOption preference variable, if it is set.</span></span> <span data-ttu-id="35184-296">В противном случае значения по умолчанию задаются параметрами, указанными в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="35184-296">Otherwise, the default values are established by options set in the session configuration.</span></span>

<span data-ttu-id="35184-297">Значения параметров сеанса имеют приоритет над значениями по умолчанию, заданными в переменной $PSSessionOption и конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="35184-297">The session option values take precedence over default values for sessions set in the $PSSessionOption preference variable and in the session configuration.</span></span> <span data-ttu-id="35184-298">Однако они не имеют приоритет над максимальными значениями, квотами и ограничениями, заданными в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="35184-298">However, they do not take precedence over maximum values, quotas or limits set in the session configuration.</span></span>

<span data-ttu-id="35184-299">Описание параметров сеанса, включая значения по умолчанию, см. в разделе `New-PSSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="35184-299">For a description of the session options, including the default values, see `New-PSSessionOption`.</span></span>
<span data-ttu-id="35184-300">Дополнительные сведения о `$PSSessionOption` переменной предпочтений см. в разделе [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="35184-300">For information about the `$PSSessionOption` preference variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span> <span data-ttu-id="35184-301">Дополнительные сведения о конфигурациях сеансов см. в разделе [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="35184-301">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

```yaml
Type: System.Management.Automation.Remoting.PSSessionOption
Parameter Sets: ComputerInstanceId, ComputerName, ConnectionUriInstanceId, ConnectionUri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="35184-302">-State</span><span class="sxs-lookup"><span data-stu-id="35184-302">-State</span></span>

<span data-ttu-id="35184-303">Указывает состояние сеанса.</span><span class="sxs-lookup"><span data-stu-id="35184-303">Specifies a session state.</span></span> <span data-ttu-id="35184-304">Этот командлет возвращает только сеансы в указанном состоянии.</span><span class="sxs-lookup"><span data-stu-id="35184-304">This cmdlet gets only sessions in the specified state.</span></span> <span data-ttu-id="35184-305">Допустимые значения для этого параметра: "все", "открыто", "отключено", "закрыто" и "нарушено".</span><span class="sxs-lookup"><span data-stu-id="35184-305">The acceptable values for this parameter are: All, Opened, Disconnected, Closed, and Broken.</span></span> <span data-ttu-id="35184-306">Значение по умолчанию — All.</span><span class="sxs-lookup"><span data-stu-id="35184-306">The default value is All.</span></span>

<span data-ttu-id="35184-307">Значение состояния сеанса задается относительно текущих сеансов.</span><span class="sxs-lookup"><span data-stu-id="35184-307">The session state value is relative to the current sessions.</span></span> <span data-ttu-id="35184-308">Сеансы, которые не были созданы в текущих сеансах и не подключены к текущему сеансу, находятся в состоянии Disconnected, даже если подключены к другому сеансу.</span><span class="sxs-lookup"><span data-stu-id="35184-308">Sessions that were not created in the current sessions and are not connected to the current session have a state of Disconnected even when they are connected to a different session.</span></span>

<span data-ttu-id="35184-309">Состояние сеанса хранится в свойстве **State**.</span><span class="sxs-lookup"><span data-stu-id="35184-309">The state of a session is stored in the **State** property of the session.</span></span>

<span data-ttu-id="35184-310">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="35184-310">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.SessionFilterState
Parameter Sets: ComputerInstanceId, ComputerName, ConnectionUriInstanceId, ConnectionUri, ContainerId, ContainerIdInstanceId, VMId, VMIdInstanceId, VMName, VMNameInstanceId
Aliases:
Accepted values: All, Opened, Disconnected, Closed, Broken

Required: False
Position: Named
Default value: All
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="35184-311">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="35184-311">-ThrottleLimit</span></span>

<span data-ttu-id="35184-312">Указывает максимальное количество одновременных подключений, которое может быть установлено для выполнения `Get-PSSession` команды.</span><span class="sxs-lookup"><span data-stu-id="35184-312">Specifies the maximum number of concurrent connections that can be established to run the `Get-PSSession` command.</span></span> <span data-ttu-id="35184-313">Если этот параметр не указан или введено значение 0 (ноль), используется значение по умолчанию — 32.</span><span class="sxs-lookup"><span data-stu-id="35184-313">If you omit this parameter or enter a value of 0 (zero), the default value, 32, is used.</span></span> <span data-ttu-id="35184-314">Предел регулирования применяется только к текущему командлету, а не к сеансу или компьютеру.</span><span class="sxs-lookup"><span data-stu-id="35184-314">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

<span data-ttu-id="35184-315">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="35184-315">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ComputerInstanceId, ComputerName, ConnectionUriInstanceId, ConnectionUri
Aliases:

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="35184-316">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="35184-316">-UseSSL</span></span>

<span data-ttu-id="35184-317">Указывает, что этот командлет использует протокол SSL (SSL) для установления соединения, в котором `Get-PSSession` выполняется команда.</span><span class="sxs-lookup"><span data-stu-id="35184-317">Indicates that this cmdlet uses the Secure Sockets Layer (SSL) protocol to establish the connection in which the `Get-PSSession` command runs.</span></span> <span data-ttu-id="35184-318">По умолчанию SSL не используется.</span><span class="sxs-lookup"><span data-stu-id="35184-318">By default, SSL is not used.</span></span> <span data-ttu-id="35184-319">Если вы используете этот параметр, но SSL недоступен для порт, указанному в команде, она завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="35184-319">If you use this parameter, but SSL is not available on the port used for the command, the command fails.</span></span>

<span data-ttu-id="35184-320">Этот параметр настраивает временное подключение, созданное для выполнения `Get-PSSession` команды с параметром **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="35184-320">This parameter configures the temporary connection that is created to run a `Get-PSSession` command with the **ComputerName** parameter.</span></span>

<span data-ttu-id="35184-321">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="35184-321">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerInstanceId, ComputerName
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="35184-322">— VMId</span><span class="sxs-lookup"><span data-stu-id="35184-322">-VMId</span></span>

<span data-ttu-id="35184-323">Указывает массив ИДЕНТИФИКАТОРов виртуальных машин.</span><span class="sxs-lookup"><span data-stu-id="35184-323">Specifies an array of ID of virtual machines.</span></span> <span data-ttu-id="35184-324">Этот командлет запускает интерактивный сеанс с каждой из указанных виртуальных машин.</span><span class="sxs-lookup"><span data-stu-id="35184-324">This cmdlet starts an interactive session with each of the specified virtual machines.</span></span> <span data-ttu-id="35184-325">Чтобы просмотреть доступные виртуальные машины, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="35184-325">To see the virtual machines that are available to you, use the following command:</span></span>

`Get-VM | Select-Object -Property Name, ID`

```yaml
Type: System.Guid[]
Parameter Sets: VMId, VMIdInstanceId
Aliases: VMGuid

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="35184-326">-VMName</span><span class="sxs-lookup"><span data-stu-id="35184-326">-VMName</span></span>

<span data-ttu-id="35184-327">Указывает массив имен виртуальных машин.</span><span class="sxs-lookup"><span data-stu-id="35184-327">Specifies an array of names of virtual machines.</span></span> <span data-ttu-id="35184-328">Этот командлет запускает интерактивный сеанс с каждой из указанных виртуальных машин.</span><span class="sxs-lookup"><span data-stu-id="35184-328">This cmdlet starts an interactive session with each of the specified virtual machines.</span></span> <span data-ttu-id="35184-329">Чтобы просмотреть доступные виртуальные машины, используйте `Get-VM` командлет.</span><span class="sxs-lookup"><span data-stu-id="35184-329">To see the virtual machines that are available to you, use the `Get-VM` cmdlet.</span></span>

```yaml
Type: System.String[]
Parameter Sets: VMName, VMNameInstanceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="35184-330">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="35184-330">CommonParameters</span></span>

<span data-ttu-id="35184-331">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="35184-331">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="35184-332">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="35184-332">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="35184-333">Входные данные</span><span class="sxs-lookup"><span data-stu-id="35184-333">INPUTS</span></span>

### <span data-ttu-id="35184-334">None</span><span class="sxs-lookup"><span data-stu-id="35184-334">None</span></span>

<span data-ttu-id="35184-335">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="35184-335">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="35184-336">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="35184-336">OUTPUTS</span></span>

### <span data-ttu-id="35184-337">System.Management.Automation.Runspaces.PSSession</span><span class="sxs-lookup"><span data-stu-id="35184-337">System.Management.Automation.Runspaces.PSSession</span></span>

## <span data-ttu-id="35184-338">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="35184-338">NOTES</span></span>

- <span data-ttu-id="35184-339">Этот командлет получает управляемые пользователем сеансы **PSSession** (например, созданные с помощью командлетов New-PSSession, `Enter-PSSession` и Invoke-Command).</span><span class="sxs-lookup"><span data-stu-id="35184-339">This cmdlet gets user-managed sessions **PSSession** objects" such as those that are created by using the New-PSSession, `Enter-PSSession`, and Invoke-Command cmdlets.</span></span> <span data-ttu-id="35184-340">Он не получает управляемый системой сеанс, который создается при запуске PowerShell.</span><span class="sxs-lookup"><span data-stu-id="35184-340">It does not get the system-managed session that is created when you start PowerShell.</span></span>
- <span data-ttu-id="35184-341">Начиная с Windows PowerShell 3,0, объекты **PSSession** хранятся на компьютере, который находится на стороне сервера или получает окончание соединения.</span><span class="sxs-lookup"><span data-stu-id="35184-341">Starting in Windows PowerShell 3.0, **PSSession** objects are stored on the computer that is at the server-side or receiving end of a connection.</span></span> <span data-ttu-id="35184-342">Чтобы получить сеансы, хранящиеся на локальном или удаленном компьютере, PowerShell устанавливает временный сеанс на указанном компьютере и выполняет команды запросов в сеансе.</span><span class="sxs-lookup"><span data-stu-id="35184-342">To get the sessions that are stored on the local computer or a remote computer, PowerShell establishes a temporary session to the specified computer and runs query commands in the session.</span></span>
- <span data-ttu-id="35184-343">Чтобы получить сеансы, которые подключены к удаленному компьютеру, укажите удаленный компьютер в параметре **ComputerName** или **ConnectionUri**.</span><span class="sxs-lookup"><span data-stu-id="35184-343">To get sessions that connect to a remote computer, use the **ComputerName** or **ConnectionUri** parameters to specify the remote computer.</span></span> <span data-ttu-id="35184-344">Чтобы отфильтровать сеансы, которые `Get-PSSession` получают, используйте параметры **Name**, **ID**, **InstanceId** и **State** .</span><span class="sxs-lookup"><span data-stu-id="35184-344">To filter the sessions that `Get-PSSession` gets, use the **Name**, **ID**, **InstanceID**, and **State** parameters.</span></span> <span data-ttu-id="35184-345">Используйте остальные параметры, чтобы настроить временный сеанс, в котором `Get-PSSession` используется.</span><span class="sxs-lookup"><span data-stu-id="35184-345">Use the remaining parameters to configure the temporary session that `Get-PSSession` uses.</span></span>
- <span data-ttu-id="35184-346">При использовании параметров **ComputerName** или **ConnectionURI** `Get-PSSession` получает только сеансы с компьютеров, на которых выполняется Windows PowerShell 3,0 и более поздних версий PowerShell.</span><span class="sxs-lookup"><span data-stu-id="35184-346">When you use the **ComputerName** or **ConnectionUri** parameters, `Get-PSSession` gets only sessions from computers running Windows PowerShell 3.0 and later versions of PowerShell.</span></span>
- <span data-ttu-id="35184-347">Значение свойства **State** для **PSSession** задается относительно текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="35184-347">The value of the **State** property of a **PSSession** is relative to the current session.</span></span>
  <span data-ttu-id="35184-348">Таким образом, значение **disconnected** означает, что **сеанс PSSession** не подключен к текущему сеансу.</span><span class="sxs-lookup"><span data-stu-id="35184-348">Therefore, a value of **Disconnected** means that the **PSSession** is not connected to the current session.</span></span> <span data-ttu-id="35184-349">Однако это не означает, что **сеанс PSSession** отключен от всех сеансов.</span><span class="sxs-lookup"><span data-stu-id="35184-349">However, it does not mean that the **PSSession** is disconnected from all sessions.</span></span> <span data-ttu-id="35184-350">Он может быть подключен к другому сеансу.</span><span class="sxs-lookup"><span data-stu-id="35184-350">It might be connected to a different session.</span></span> <span data-ttu-id="35184-351">Чтобы определить, можно ли подключиться к сеансу **PSSession** или повторно подключиться к нему из текущего сеанса, используйте свойство **Availability** .</span><span class="sxs-lookup"><span data-stu-id="35184-351">To determine whether you can connect or reconnect to the **PSSession** from the current session, use the **Availability** property.</span></span>

<span data-ttu-id="35184-352">Если свойство **Availability** имеет значение **None**, подключиться к сеансу можно.</span><span class="sxs-lookup"><span data-stu-id="35184-352">An **Availability** value of **None** indicates that you can connect to the session.</span></span> <span data-ttu-id="35184-353">Значение **занято** указывает, что невозможно подключиться к сеансу **PSSession** , так как он подключен к другому сеансу.</span><span class="sxs-lookup"><span data-stu-id="35184-353">A value of **Busy** indicates that you cannot connect to the **PSSession** because it is connected to another session.</span></span>

<span data-ttu-id="35184-354">Дополнительные сведения о значениях свойства **State** в сеансах см. в разделе [рунспацестате enumeration](/dotnet/api/system.management.automation.runspaces.runspacestate).</span><span class="sxs-lookup"><span data-stu-id="35184-354">For more information about the values of the **State** property of sessions, see [RunspaceState Enumeration](/dotnet/api/system.management.automation.runspaces.runspacestate).</span></span>

<span data-ttu-id="35184-355">Дополнительные сведения о значениях свойства **Availability** сеансов см. в разделе [рунспацеаваилабилити enumeration](/dotnet/api/system.management.automation.runspaces.runspaceavailability).</span><span class="sxs-lookup"><span data-stu-id="35184-355">For more information about the values of the **Availability** property of sessions, see [RunspaceAvailability Enumeration](/dotnet/api/system.management.automation.runspaces.runspaceavailability).</span></span>

## <span data-ttu-id="35184-356">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="35184-356">RELATED LINKS</span></span>

[<span data-ttu-id="35184-357">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="35184-357">Connect-PSSession</span></span>](Connect-PSSession.md)

[<span data-ttu-id="35184-358">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="35184-358">Disconnect-PSSession</span></span>](Disconnect-PSSession.md)

[<span data-ttu-id="35184-359">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="35184-359">Receive-PSSession</span></span>](Receive-PSSession.md)

[<span data-ttu-id="35184-360">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="35184-360">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="35184-361">Exit-PSSession;</span><span class="sxs-lookup"><span data-stu-id="35184-361">Exit-PSSession</span></span>](Exit-PSSession.md)

[<span data-ttu-id="35184-362">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="35184-362">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="35184-363">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="35184-363">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="35184-364">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="35184-364">Remove-PSSession</span></span>](Remove-PSSession.md)

[<span data-ttu-id="35184-365">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="35184-365">about_PSSessions</span></span>](About/about_PSSessions.md)

[<span data-ttu-id="35184-366">about_Remote</span><span class="sxs-lookup"><span data-stu-id="35184-366">about_Remote</span></span>](About/about_Remote.md)

