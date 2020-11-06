---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 5/15/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-pssession?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSSession
ms.openlocfilehash: 08ca0ec9a45542e86ea197fc24df65430f2d0649
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "93230057"
---
# <span data-ttu-id="d3db4-103">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="d3db4-103">Get-PSSession</span></span>

## <span data-ttu-id="d3db4-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="d3db4-104">SYNOPSIS</span></span>
<span data-ttu-id="d3db4-105">Получает сеансы PowerShell на локальных и удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="d3db4-105">Gets the PowerShell sessions on local and remote computers.</span></span>

## <span data-ttu-id="d3db4-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d3db4-106">SYNTAX</span></span>

### <span data-ttu-id="d3db4-107">Имя (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="d3db4-107">Name (Default)</span></span>

```
Get-PSSession [-Name <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="d3db4-108">ИмяКомпьютера</span><span class="sxs-lookup"><span data-stu-id="d3db4-108">ComputerName</span></span>

```
Get-PSSession [-ComputerName] <String[]> [-ApplicationName <String>] [-ConfigurationName <String>]
 [-Name <String[]>] [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [-Port <Int32>] [-UseSSL] [-ThrottleLimit <Int32>]
 [-State <SessionFilterState>] [-SessionOption <PSSessionOption>] [<CommonParameters>]
```

### <span data-ttu-id="d3db4-109">компутеринстанцеид</span><span class="sxs-lookup"><span data-stu-id="d3db4-109">ComputerInstanceId</span></span>

```
Get-PSSession [-ComputerName] <String[]> [-ApplicationName <String>] [-ConfigurationName <String>]
 -InstanceId <Guid[]> [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [-Port <Int32>] [-UseSSL] [-ThrottleLimit <Int32>]
 [-State <SessionFilterState>] [-SessionOption <PSSessionOption>] [<CommonParameters>]
```

### <span data-ttu-id="d3db4-110">ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="d3db4-110">ConnectionUri</span></span>

```
Get-PSSession [-ConnectionUri] <Uri[]> [-ConfigurationName <String>] [-AllowRedirection] [-Name <String[]>]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [-ThrottleLimit <Int32>] [-State <SessionFilterState>] [-SessionOption <PSSessionOption>] [<CommonParameters>]
```

### <span data-ttu-id="d3db4-111">коннектионуриинстанцеид</span><span class="sxs-lookup"><span data-stu-id="d3db4-111">ConnectionUriInstanceId</span></span>

```
Get-PSSession [-ConnectionUri] <Uri[]> [-ConfigurationName <String>] [-AllowRedirection] -InstanceId <Guid[]>
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [-ThrottleLimit <Int32>] [-State <SessionFilterState>] [-SessionOption <PSSessionOption>] [<CommonParameters>]
```

### <span data-ttu-id="d3db4-112">вмнамеинстанцеид</span><span class="sxs-lookup"><span data-stu-id="d3db4-112">VMNameInstanceId</span></span>

```
Get-PSSession [-ConfigurationName <String>] -InstanceId <Guid[]> [-State <SessionFilterState>]
 -VMName <String[]> [<CommonParameters>]
```

### <span data-ttu-id="d3db4-113">ContainerId</span><span class="sxs-lookup"><span data-stu-id="d3db4-113">ContainerId</span></span>

```
Get-PSSession [-ConfigurationName <String>] [-Name <String[]>] [-State <SessionFilterState>]
 -ContainerId <String[]> [<CommonParameters>]
```

### <span data-ttu-id="d3db4-114">контаинеридинстанцеид</span><span class="sxs-lookup"><span data-stu-id="d3db4-114">ContainerIdInstanceId</span></span>

```
Get-PSSession [-ConfigurationName <String>] -InstanceId <Guid[]> [-State <SessionFilterState>]
 -ContainerId <String[]> [<CommonParameters>]
```

### <span data-ttu-id="d3db4-115">VMId</span><span class="sxs-lookup"><span data-stu-id="d3db4-115">VMId</span></span>

```
Get-PSSession [-ConfigurationName <String>] [-Name <String[]>] [-State <SessionFilterState>] -VMId <Guid[]>
 [<CommonParameters>]
```

### <span data-ttu-id="d3db4-116">вмидинстанцеид</span><span class="sxs-lookup"><span data-stu-id="d3db4-116">VMIdInstanceId</span></span>

```
Get-PSSession [-ConfigurationName <String>] -InstanceId <Guid[]> [-State <SessionFilterState>] -VMId <Guid[]>
 [<CommonParameters>]
```

### <span data-ttu-id="d3db4-117">VMName</span><span class="sxs-lookup"><span data-stu-id="d3db4-117">VMName</span></span>

```
Get-PSSession [-ConfigurationName <String>] [-Name <String[]>] [-State <SessionFilterState>] -VMName <String[]>
 [<CommonParameters>]
```

### <span data-ttu-id="d3db4-118">InstanceId</span><span class="sxs-lookup"><span data-stu-id="d3db4-118">InstanceId</span></span>

```
Get-PSSession [-InstanceId <Guid[]>] [<CommonParameters>]
```

### <span data-ttu-id="d3db4-119">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="d3db4-119">Id</span></span>

```
Get-PSSession [-Id] <Int32[]> [<CommonParameters>]
```

## <span data-ttu-id="d3db4-120">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d3db4-120">DESCRIPTION</span></span>

<span data-ttu-id="d3db4-121">`Get-PSSession`Командлет получает управляемые пользователем сеансы PowerShell ( **PSSession** ) на локальных и удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="d3db4-121">The `Get-PSSession` cmdlet gets the user-managed PowerShell sessions ( **PSSessions** ) on local and remote computers.</span></span>

<span data-ttu-id="d3db4-122">Начиная с Windows PowerShell 3,0, сеансы хранятся на компьютерах на удаленной стороне каждого подключения.</span><span class="sxs-lookup"><span data-stu-id="d3db4-122">Starting in Windows PowerShell 3.0, sessions are stored on the computers at the remote end of each connection.</span></span> <span data-ttu-id="d3db4-123">Параметры **ComputerName** или **ConnectionURI** можно использовать `Get-PSSession` для получения сеансов, подключающихся к локальному компьютеру или удаленным компьютерам, даже если они не были созданы в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="d3db4-123">You can use the **ComputerName** or **ConnectionUri** parameters of `Get-PSSession` to get the sessions that connect to the local computer or remote computers, even if they were not created in the current session.</span></span>

<span data-ttu-id="d3db4-124">Без параметров `Get-PSSession` возвращает все сеансы, которые были созданы в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="d3db4-124">Without parameters, `Get-PSSession` gets all sessions that were created in the current session.</span></span>

<span data-ttu-id="d3db4-125">Используйте параметры фильтрации, в том числе **Name** , **ID** , **InstanceId** , **State** , **applicationName** и **configurationName** , чтобы выбрать из сеансов, которые `Get-PSSession` возвращает.</span><span class="sxs-lookup"><span data-stu-id="d3db4-125">Use the filtering parameters, including **Name** , **ID** , **InstanceID** , **State** , **ApplicationName** , and **ConfigurationName** to select from among the sessions that `Get-PSSession` returns.</span></span>

<span data-ttu-id="d3db4-126">Используйте оставшиеся параметры для настройки временного подключения, в котором `Get-PSSession` выполняется команда при использовании параметров **ComputerName** или **ConnectionURI** .</span><span class="sxs-lookup"><span data-stu-id="d3db4-126">Use the remaining parameters to configure the temporary connection in which the `Get-PSSession` command runs when you use the **ComputerName** or **ConnectionUri** parameters.</span></span>

<span data-ttu-id="d3db4-127">Примечание. в Windows PowerShell 2,0 без параметров `Get-PSSession` получает все сеансы, которые были созданы в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="d3db4-127">NOTE: In Windows PowerShell 2.0, without parameters, `Get-PSSession` gets all sessions that were created in the current session.</span></span> <span data-ttu-id="d3db4-128">Параметр **ComputerName** получает сеансы, которые были созданы в текущем сеансе и подключаются к указанному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="d3db4-128">The **ComputerName** parameter gets sessions that were created in the current session and connect to the specified computer.</span></span>

<span data-ttu-id="d3db4-129">Дополнительные сведения о сеансах PowerShell см. в разделе [about_PSSessions](about/about_PSSessions.md).</span><span class="sxs-lookup"><span data-stu-id="d3db4-129">For more information about PowerShell sessions, see [about_PSSessions](about/about_PSSessions.md).</span></span>

## <span data-ttu-id="d3db4-130">Примеры</span><span class="sxs-lookup"><span data-stu-id="d3db4-130">EXAMPLES</span></span>

### <span data-ttu-id="d3db4-131">Пример 1. получение сеансов, созданных в текущем сеансе</span><span class="sxs-lookup"><span data-stu-id="d3db4-131">Example 1: Get sessions created in the current session</span></span>

```powershell
Get-PSSession
```

<span data-ttu-id="d3db4-132">Эта команда возвращает все **PSSession** , созданные в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="d3db4-132">This command gets all of the **PSSessions** that were created in the current session.</span></span> <span data-ttu-id="d3db4-133">Он не получает **PSSession** , которые были созданы в других сеансах или на других компьютерах, даже если они подключаются к этому компьютеру.</span><span class="sxs-lookup"><span data-stu-id="d3db4-133">It does not get **PSSessions** that were created in other sessions or on other computers, even if they connect to this computer.</span></span>

### <span data-ttu-id="d3db4-134">Пример 2. получение сеансов, подключенных к локальному компьютеру</span><span class="sxs-lookup"><span data-stu-id="d3db4-134">Example 2: Get sessions connected to the local computer</span></span>

```powershell
Get-PSSession -ComputerName "localhost"
```

<span data-ttu-id="d3db4-135">Эта команда возвращает **PSSession** , подключенные к локальному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="d3db4-135">This command gets the **PSSessions** that are connected to the local computer.</span></span> <span data-ttu-id="d3db4-136">Чтобы указать локальный компьютер, введите имя компьютера, localhost или точку (.)</span><span class="sxs-lookup"><span data-stu-id="d3db4-136">To indicate the local computer, type the computer name, localhost, or a dot (.)</span></span>

<span data-ttu-id="d3db4-137">Эта команда возвращает все сеансы на локальном компьютере, даже если они были созданы в других сеансах или на других компьютерах.</span><span class="sxs-lookup"><span data-stu-id="d3db4-137">The command returns all of the sessions on the local computer, even if they were created in different sessions or on different computers.</span></span>

### <span data-ttu-id="d3db4-138">Пример 3. получение сеансов, подключенных к компьютеру</span><span class="sxs-lookup"><span data-stu-id="d3db4-138">Example 3: Get sessions connected to a computer</span></span>

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

<span data-ttu-id="d3db4-139">Эта команда возвращает **PSSession** , подключенные к компьютеру Server02.</span><span class="sxs-lookup"><span data-stu-id="d3db4-139">This command gets the **PSSessions** that are connected to the Server02 computer.</span></span>

<span data-ttu-id="d3db4-140">Эта команда возвращает все сеансы на компьютере Server02, даже если они были созданы в других сеансах или на других компьютерах.</span><span class="sxs-lookup"><span data-stu-id="d3db4-140">The command returns all of the sessions on Server02, even if they were created in different sessions or on different computers.</span></span>

<span data-ttu-id="d3db4-141">Выходные данные показывают, что два сеансы находятся в отключенном состоянии с доступностью "Занято".</span><span class="sxs-lookup"><span data-stu-id="d3db4-141">The output shows that two of the sessions have a Disconnected state and a Busy availability.</span></span> <span data-ttu-id="d3db4-142">Они были созданы в различных сеансах и в настоящее время используются.</span><span class="sxs-lookup"><span data-stu-id="d3db4-142">They were created in different sessions and are currently in use.</span></span> <span data-ttu-id="d3db4-143">Сеанс ScheduledJobs, который открыт и доступен, был создан в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="d3db4-143">The ScheduledJobs session, which is Opened and Available, was created in the current session.</span></span>

### <span data-ttu-id="d3db4-144">Пример 4. Сохранение результатов выполнения этой команды</span><span class="sxs-lookup"><span data-stu-id="d3db4-144">Example 4: Save results of this command</span></span>

```powershell
New-PSSession -ComputerName Server01, Server02, Server03
$s1, $s2, $s3 = Get-PSSession
```

<span data-ttu-id="d3db4-145">В этом примере показано, как сохранить результаты `Get-PSSession` команды в нескольких переменных.</span><span class="sxs-lookup"><span data-stu-id="d3db4-145">This example shows how to save the results of a `Get-PSSession` command in multiple variables.</span></span>

<span data-ttu-id="d3db4-146">Первая команда использует `New-PSSession` командлет для создания **PSSession** на трех удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="d3db4-146">The first command uses the `New-PSSession` cmdlet to create **PSSessions** on three remote computers.</span></span>

<span data-ttu-id="d3db4-147">Вторая команда использует `Get-PSSession` командлет для получения трех **PSSession** .</span><span class="sxs-lookup"><span data-stu-id="d3db4-147">The second command uses a `Get-PSSession` cmdlet to get the three **PSSessions** .</span></span> <span data-ttu-id="d3db4-148">Затем он сохраняет каждую из **PSSession** в отдельной переменной.</span><span class="sxs-lookup"><span data-stu-id="d3db4-148">It then saves each of the **PSSessions** in a separate variable.</span></span>

<span data-ttu-id="d3db4-149">Когда PowerShell назначает массив объектов массиву переменных, он присваивает первому объекту первую переменную, второй объект второй переменной и т. д.</span><span class="sxs-lookup"><span data-stu-id="d3db4-149">When PowerShell assigns an array of objects to an array of variables, it assigns the first object to the first variable, the second object to the second variable, and so on.</span></span> <span data-ttu-id="d3db4-150">Если объектов больше, чем переменных, все оставшиеся объекты назначаются последней переменной в массиве.</span><span class="sxs-lookup"><span data-stu-id="d3db4-150">If there are more objects than variables, it assigns all remaining objects to the last variable in the array.</span></span> <span data-ttu-id="d3db4-151">Если переменных больше, чем объектов, дополнительные переменные не используются.</span><span class="sxs-lookup"><span data-stu-id="d3db4-151">If there are more variables than objects, the extra variables are not used.</span></span>

### <span data-ttu-id="d3db4-152">Пример 5. Удаление сеанса с помощью идентификатора экземпляра</span><span class="sxs-lookup"><span data-stu-id="d3db4-152">Example 5: Delete a session by using an instance ID</span></span>

```powershell
Get-PSSession | Format-Table -Property ComputerName, InstanceID
$s = Get-PSSession -InstanceID a786be29-a6bb-40da-80fb-782c67f7db0f
Remove-PSSession -Session $s
```

<span data-ttu-id="d3db4-153">В этом примере показано, как получить **PSSession** с помощью идентификатора экземпляра, а затем удалить **PSSession** .</span><span class="sxs-lookup"><span data-stu-id="d3db4-153">This example shows how to get a **PSSession** by using its instance ID, and then to delete the **PSSession** .</span></span>

<span data-ttu-id="d3db4-154">Первая команда получает все **PSSession** , созданные в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="d3db4-154">The first command gets all of the **PSSessions** that were created in the current session.</span></span> <span data-ttu-id="d3db4-155">Он отправляет **PSSession** командлету Format-Table, который отображает свойства **ComputerName** и **InstanceId** каждого **сеанса PSSession** .</span><span class="sxs-lookup"><span data-stu-id="d3db4-155">It sends the **PSSessions** to the Format-Table cmdlet, which displays the **ComputerName** and **InstanceID** properties of each **PSSession** .</span></span>

<span data-ttu-id="d3db4-156">Вторая команда использует командлет, `Get-PSSession` чтобы получить определенный **сеанс PSSession** и сохранить его в `$s` переменной.</span><span class="sxs-lookup"><span data-stu-id="d3db4-156">The second command uses the `Get-PSSession` cmdlet to get a particular **PSSession** and to save it in the `$s` variable.</span></span> <span data-ttu-id="d3db4-157">Команда использует параметр **InstanceId** для задания **сеанса PSSession** .</span><span class="sxs-lookup"><span data-stu-id="d3db4-157">The command uses the **InstanceID** parameter to identify the **PSSession** .</span></span>

<span data-ttu-id="d3db4-158">Третья команда использует командлет Remove-PSSession для удаления **сеанса PSSession** в `$s` переменной.</span><span class="sxs-lookup"><span data-stu-id="d3db4-158">The third command uses the Remove-PSSession cmdlet to delete the **PSSession** in the `$s` variable.</span></span>

### <span data-ttu-id="d3db4-159">Пример 6. Получение сеанса с определенным именем</span><span class="sxs-lookup"><span data-stu-id="d3db4-159">Example 6: Get a session that has a particular name</span></span>

<span data-ttu-id="d3db4-160">Команды в этом примере находят сеанс, имя которого имеет определенный формат, использует конфигурацию сеанса и затем подключается к сеансу.</span><span class="sxs-lookup"><span data-stu-id="d3db4-160">The commands in this example find a session that has a particular name format and uses a particular session configuration and then connect to the session.</span></span> <span data-ttu-id="d3db4-161">С помощью подобной команды можно найти сеанс, в котором коллега запустил задачу, и подключиться к нему для завершения задачи.</span><span class="sxs-lookup"><span data-stu-id="d3db4-161">You can use a command like this one to find a session in which a colleague started a task and connect to finish the task.</span></span>

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

<span data-ttu-id="d3db4-162">Первая команда получает сеансы на удаленных компьютерах Server02 и Server12, имена которых начинаются с Баккупжоб и используют конфигурацию сеанса ITTasks. Команда использует параметр **Name** для указания шаблона имени, а параметр **configurationName** — для указания конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="d3db4-162">The first command gets sessions on the Server02 and Server12 remote computers that have names that begin with BackupJob and use the ITTasks session configuration.The command uses the **Name** parameter to specify the name pattern and the **ConfigurationName** parameter to specify the session configuration.</span></span> <span data-ttu-id="d3db4-163">Значение параметра **SessionOption** — это хэш-таблица, которая устанавливает для параметра **OperationTimeout** значение 240 000 мс (4 минуты).</span><span class="sxs-lookup"><span data-stu-id="d3db4-163">The value of the **SessionOption** parameter is a hash table that sets the value of the **OperationTimeout** to 240000 milliseconds (4 minutes).</span></span> <span data-ttu-id="d3db4-164">Этот параметр дает команде больше времени на завершение. Параметры **configurationName** и **SessionOption** используются для настройки временных сеансов, в которых `Get-PSSession` командлет выполняется на каждом компьютере. Выходные данные показывают, что команда возвращает сеанс BackupJob04.</span><span class="sxs-lookup"><span data-stu-id="d3db4-164">This setting gives the command more time to complete.The **ConfigurationName** and **SessionOption** parameters are used to configure the temporary sessions in which the `Get-PSSession` cmdlet runs on each computer.The output shows that the command returns the BackupJob04 session.</span></span> <span data-ttu-id="d3db4-165">Сеанс отключен, а уровень **доступности** равен None, что означает, что он не используется.</span><span class="sxs-lookup"><span data-stu-id="d3db4-165">The session is disconnected and the **Availability** is None, which indicates that it is not in use.</span></span>

<span data-ttu-id="d3db4-166">Вторая команда использует `Get-PSSession` командлет для перехода к сеансу BackupJob04 и командлету Connect-PSSession для подключения к сеансу.</span><span class="sxs-lookup"><span data-stu-id="d3db4-166">The second command uses the `Get-PSSession` cmdlet to get to the BackupJob04 session and the Connect-PSSession cmdlet to connect to the session.</span></span> <span data-ttu-id="d3db4-167">Сеанс сохраняется в переменную $s.</span><span class="sxs-lookup"><span data-stu-id="d3db4-167">The command saves the session in the $s variable.</span></span>

<span data-ttu-id="d3db4-168">Третья команда получает сеанс в переменной $s.</span><span class="sxs-lookup"><span data-stu-id="d3db4-168">The third command gets the session in the $s variable.</span></span> <span data-ttu-id="d3db4-169">Выходные данные показывают, что `Connect-PSSession` команда выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="d3db4-169">The output shows that the `Connect-PSSession` command was successful.</span></span> <span data-ttu-id="d3db4-170">Сеанс находится в состоянии **Opened** и доступен для использования.</span><span class="sxs-lookup"><span data-stu-id="d3db4-170">The session is in the **Opened** state and is available for use.</span></span>

### <span data-ttu-id="d3db4-171">Пример 7. Получение сеанса с помощью его идентификатора</span><span class="sxs-lookup"><span data-stu-id="d3db4-171">Example 7: Get a session by using its ID</span></span>

```powershell
Get-PSSession -Id 2
```

<span data-ttu-id="d3db4-172">Эта команда получает **сеанс PSSession** с идентификатором 2.</span><span class="sxs-lookup"><span data-stu-id="d3db4-172">This command gets the **PSSession** with ID 2.</span></span> <span data-ttu-id="d3db4-173">Так как значение свойства **ID** уникально только в текущем сеансе, параметр **ID** допустим только для локальных команд.</span><span class="sxs-lookup"><span data-stu-id="d3db4-173">Because the value of the **ID** property is unique only in the current session, the **Id** parameter is valid only for local commands.</span></span>

## <span data-ttu-id="d3db4-174">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d3db4-174">PARAMETERS</span></span>

### <span data-ttu-id="d3db4-175">-AllowRedirection</span><span class="sxs-lookup"><span data-stu-id="d3db4-175">-AllowRedirection</span></span>

<span data-ttu-id="d3db4-176">Указывает, что этот командлет разрешает перенаправление этого соединения в альтернативный универсальный код ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="d3db4-176">Indicates that this cmdlet allows redirection of this connection to an alternate Uniform Resource Identifier (URI).</span></span> <span data-ttu-id="d3db4-177">По умолчанию PowerShell не перенаправляет соединения.</span><span class="sxs-lookup"><span data-stu-id="d3db4-177">By default, PowerShell does not redirect connections.</span></span>

<span data-ttu-id="d3db4-178">Этот параметр настраивает временное подключение, созданное для выполнения `Get-PSSession` команды с параметром **ConnectionURI** .</span><span class="sxs-lookup"><span data-stu-id="d3db4-178">This parameter configures the temporary connection that is created to run a `Get-PSSession` command with the **ConnectionUri** parameter.</span></span>

<span data-ttu-id="d3db4-179">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="d3db4-179">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="d3db4-180">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="d3db4-180">-ApplicationName</span></span>

<span data-ttu-id="d3db4-181">Указывает имя приложения.</span><span class="sxs-lookup"><span data-stu-id="d3db4-181">Specifies the name of an application.</span></span> <span data-ttu-id="d3db4-182">Этот командлет подключается только к сеансам, использующим указанное приложение.</span><span class="sxs-lookup"><span data-stu-id="d3db4-182">This cmdlet connects only to sessions that use the specified application.</span></span>

<span data-ttu-id="d3db4-183">Введите сегмент имени приложения URI подключения.</span><span class="sxs-lookup"><span data-stu-id="d3db4-183">Enter the application name segment of the connection URI.</span></span> <span data-ttu-id="d3db4-184">Например, в следующем URI соединения имя приложения — WSMan: `http://localhost:5985/WSMAN` .</span><span class="sxs-lookup"><span data-stu-id="d3db4-184">For example, in the following connection URI, the application name is WSMan: `http://localhost:5985/WSMAN`.</span></span> <span data-ttu-id="d3db4-185">Имя приложения сеанса хранится в свойстве сеанса **Runspace.ConnectionInfo.AppName** .</span><span class="sxs-lookup"><span data-stu-id="d3db4-185">The application name of a session is stored in the **Runspace.ConnectionInfo.AppName** property of the session.</span></span>

<span data-ttu-id="d3db4-186">Значение этого параметра используется для выбора и фильтрации сеансов.</span><span class="sxs-lookup"><span data-stu-id="d3db4-186">The value of this parameter is used to select and filter sessions.</span></span> <span data-ttu-id="d3db4-187">Оно не изменяет приложение, которое использует сеанс.</span><span class="sxs-lookup"><span data-stu-id="d3db4-187">It does not change the application that the session uses.</span></span>

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

### <span data-ttu-id="d3db4-188">-Authentication</span><span class="sxs-lookup"><span data-stu-id="d3db4-188">-Authentication</span></span>

<span data-ttu-id="d3db4-189">Указывает механизм, используемый для проверки подлинности учетных данных для сеанса, в котором `Get-PSSession` выполняется команда.</span><span class="sxs-lookup"><span data-stu-id="d3db4-189">Specifies the mechanism that is used to authenticate credentials for the session in which the `Get-PSSession` command runs.</span></span>

<span data-ttu-id="d3db4-190">Этот параметр настраивает временное подключение, созданное для выполнения `Get-PSSession` команды с параметром **ComputerName** или **ConnectionURI** .</span><span class="sxs-lookup"><span data-stu-id="d3db4-190">This parameter configures the temporary connection that is created to run a `Get-PSSession` command with the **ComputerName** or **ConnectionUri** parameter.</span></span>

<span data-ttu-id="d3db4-191">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="d3db4-191">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="d3db4-192">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="d3db4-192">Default</span></span>
- <span data-ttu-id="d3db4-193">Базовый</span><span class="sxs-lookup"><span data-stu-id="d3db4-193">Basic</span></span>
- <span data-ttu-id="d3db4-194">CredSSP</span><span class="sxs-lookup"><span data-stu-id="d3db4-194">Credssp</span></span>
- <span data-ttu-id="d3db4-195">Digest (дайджест)</span><span class="sxs-lookup"><span data-stu-id="d3db4-195">Digest</span></span>
- <span data-ttu-id="d3db4-196">Kerberos</span><span class="sxs-lookup"><span data-stu-id="d3db4-196">Kerberos</span></span>
- <span data-ttu-id="d3db4-197">Согласование</span><span class="sxs-lookup"><span data-stu-id="d3db4-197">Negotiate</span></span>
- <span data-ttu-id="d3db4-198">NegotiateWithImplicitCredential.</span><span class="sxs-lookup"><span data-stu-id="d3db4-198">NegotiateWithImplicitCredential.</span></span>

<span data-ttu-id="d3db4-199">Значение по умолчанию — Default.</span><span class="sxs-lookup"><span data-stu-id="d3db4-199">The default value is Default.</span></span>

<span data-ttu-id="d3db4-200">Дополнительные сведения о значениях этого параметра см. в разделе [перечисление AuthenticationMechanism](https://msdn.microsoft.com/library/system.management.automation.runspaces.authenticationmechanism) в библиотеке MSDN.</span><span class="sxs-lookup"><span data-stu-id="d3db4-200">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](https://msdn.microsoft.com/library/system.management.automation.runspaces.authenticationmechanism) in the MSDN library.</span></span>

<span data-ttu-id="d3db4-201">ВНИМАНИЕ! проверка подлинности поставщика поддержки безопасности учетных данных (CredSSP), в которой учетные данные пользователя передаются на удаленный компьютер для проверки подлинности, предназначена для команд, требующих проверки подлинности в нескольких ресурсах, таких как доступ к удаленной сетевой папке.</span><span class="sxs-lookup"><span data-stu-id="d3db4-201">CAUTION: Credential Security Support Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="d3db4-202">Этот механизм повышает риск безопасности удаленной операции.</span><span class="sxs-lookup"><span data-stu-id="d3db4-202">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="d3db4-203">Если удаленный компьютер скомпрометирован, учетные данные, передаваемые ему, могут использоваться для управления сетевым сеансом.</span><span class="sxs-lookup"><span data-stu-id="d3db4-203">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

<span data-ttu-id="d3db4-204">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="d3db4-204">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="d3db4-205">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="d3db4-205">-CertificateThumbprint</span></span>

<span data-ttu-id="d3db4-206">Указывает сертификат цифрового открытого ключа (X509) учетной записи пользователя, имеющей разрешение на создание сеанса, в котором `Get-PSSession` выполняется команда.</span><span class="sxs-lookup"><span data-stu-id="d3db4-206">Specifies the digital public key certificate (X509) of a user account that has permission to create the session in which the `Get-PSSession` command runs.</span></span> <span data-ttu-id="d3db4-207">Введите отпечаток сертификата.</span><span class="sxs-lookup"><span data-stu-id="d3db4-207">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="d3db4-208">Этот параметр настраивает временное подключение, созданное для выполнения `Get-PSSession` команды с параметром **ComputerName** или **ConnectionURI** .</span><span class="sxs-lookup"><span data-stu-id="d3db4-208">This parameter configures the temporary connection that is created to run a `Get-PSSession` command with the **ComputerName** or **ConnectionUri** parameter.</span></span>

<span data-ttu-id="d3db4-209">Сертификаты используются при проверке подлинности на основе сертификата клиента.</span><span class="sxs-lookup"><span data-stu-id="d3db4-209">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="d3db4-210">Они могут сопоставляться только с учетными записями локальных пользователей и не работают с учетными записями доменов.</span><span class="sxs-lookup"><span data-stu-id="d3db4-210">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="d3db4-211">Чтобы получить отпечаток сертификата, используйте команду Get-Item или Get-ChildItem на диске с сертификатом PowerShell:.</span><span class="sxs-lookup"><span data-stu-id="d3db4-211">To get a certificate thumbprint, use a Get-Item or Get-ChildItem command in the PowerShell Cert: drive.</span></span>

<span data-ttu-id="d3db4-212">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="d3db4-212">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="d3db4-213">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="d3db4-213">-ComputerName</span></span>

<span data-ttu-id="d3db4-214">Указывает массив имен компьютеров.</span><span class="sxs-lookup"><span data-stu-id="d3db4-214">Specifies an array of names of computers.</span></span> <span data-ttu-id="d3db4-215">Возвращает сеансов, которые подключаются к указанным компьютерам.</span><span class="sxs-lookup"><span data-stu-id="d3db4-215">Gets the sessions that connect to the specified computers.</span></span>
<span data-ttu-id="d3db4-216">Подстановочные знаки не допускаются.</span><span class="sxs-lookup"><span data-stu-id="d3db4-216">Wildcard characters are not permitted.</span></span> <span data-ttu-id="d3db4-217">Значение по умолчанию отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d3db4-217">There is no default value.</span></span>

<span data-ttu-id="d3db4-218">Начиная с Windows PowerShell 3,0, объекты **PSSession** хранятся на компьютерах на удаленной стороне каждого подключения.</span><span class="sxs-lookup"><span data-stu-id="d3db4-218">Beginning in Windows PowerShell 3.0, **PSSession** objects are stored on the computers at the remote end of each connection.</span></span> <span data-ttu-id="d3db4-219">Чтобы получить сеансы на указанных компьютерах, PowerShell создает временное подключение к каждому компьютеру и выполняет `Get-PSSession` команду.</span><span class="sxs-lookup"><span data-stu-id="d3db4-219">To get the sessions on the specified computers, PowerShell creates a temporary connection to each computer and runs a `Get-PSSession` command.</span></span>

<span data-ttu-id="d3db4-220">Введите имя NetBIOS, IP-адрес или полное доменное имя одного или нескольких компьютеров.</span><span class="sxs-lookup"><span data-stu-id="d3db4-220">Type the NetBIOS name, an IP address, or a fully-qualified domain name of one or more computers.</span></span> <span data-ttu-id="d3db4-221">Чтобы указать локальный компьютер, введите имя компьютера, localhost или точку (.).</span><span class="sxs-lookup"><span data-stu-id="d3db4-221">To specify the local computer, type the computer name, localhost, or a dot (.).</span></span>

<span data-ttu-id="d3db4-222">Примечание. Этот параметр получает сеансы только с компьютеров, на которых выполняется Windows PowerShell 3,0 или более поздних версий PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d3db4-222">Note: This parameter gets sessions only from computers that run Windows PowerShell 3.0 or later versions of PowerShell.</span></span> <span data-ttu-id="d3db4-223">Предыдущие версии не хранят сеансы.</span><span class="sxs-lookup"><span data-stu-id="d3db4-223">Earlier versions do not store sessions.</span></span>

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

### <span data-ttu-id="d3db4-224">-ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="d3db4-224">-ConfigurationName</span></span>

<span data-ttu-id="d3db4-225">Указывает имя конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d3db4-225">Specifies the name of a configuration.</span></span> <span data-ttu-id="d3db4-226">Этот командлет получает только сеансы, в которых используется указанная конфигурация сеанса.</span><span class="sxs-lookup"><span data-stu-id="d3db4-226">This cmdlet gets only to sessions that use the specified session configuration.</span></span>

<span data-ttu-id="d3db4-227">Введите имя конфигурации или полное имя ресурса (URI) для конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="d3db4-227">Enter a configuration name or the fully qualified resource URI for a session configuration.</span></span> <span data-ttu-id="d3db4-228">Если указано только имя конфигурации, в начале добавляется следующий URI схемы: `http://schemas.microsoft.com/powershell` .</span><span class="sxs-lookup"><span data-stu-id="d3db4-228">If you specify only the configuration name, the following schema URI is prepended: `http://schemas.microsoft.com/powershell`.</span></span> <span data-ttu-id="d3db4-229">Имя конфигурации сеанса хранится в свойстве сеанса **ConfigurationName** .</span><span class="sxs-lookup"><span data-stu-id="d3db4-229">The configuration name of a session is stored in the **ConfigurationName** property of the session.</span></span>

<span data-ttu-id="d3db4-230">Значение этого параметра используется для выбора и фильтрации сеансов.</span><span class="sxs-lookup"><span data-stu-id="d3db4-230">The value of this parameter is used to select and filter sessions.</span></span> <span data-ttu-id="d3db4-231">Оно не изменяет конфигурацию, которую использует сеанс.</span><span class="sxs-lookup"><span data-stu-id="d3db4-231">It does not change the session configuration that the session uses.</span></span>

<span data-ttu-id="d3db4-232">Дополнительные сведения о конфигурациях сеансов см. в разделе [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="d3db4-232">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

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

### <span data-ttu-id="d3db4-233">-ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="d3db4-233">-ConnectionUri</span></span>

<span data-ttu-id="d3db4-234">Задает универсальный код ресурса (URI), определяющий конечную точку подключения для временного сеанса, в котором `Get-PSSession` выполняется команда.</span><span class="sxs-lookup"><span data-stu-id="d3db4-234">Specifies a URI that defines the connection endpoint for the temporary session in which the `Get-PSSession` command runs.</span></span> <span data-ttu-id="d3db4-235">Значение URI должно быть указано полностью.</span><span class="sxs-lookup"><span data-stu-id="d3db4-235">The URI must be fully qualified.</span></span>

<span data-ttu-id="d3db4-236">Этот параметр настраивает временное подключение, созданное для выполнения `Get-PSSession` команды с параметром **ConnectionURI** .</span><span class="sxs-lookup"><span data-stu-id="d3db4-236">This parameter configures the temporary connection that is created to run a `Get-PSSession` command with the **ConnectionUri** parameter.</span></span>

<span data-ttu-id="d3db4-237">Строки имеют следующий формат:</span><span class="sxs-lookup"><span data-stu-id="d3db4-237">The format of this string is:</span></span>

`<Transport>://<ComputerName>:<Port\>/<ApplicationName>`

<span data-ttu-id="d3db4-238">Значение по умолчанию: `http://localhost:5985/WSMAN` .</span><span class="sxs-lookup"><span data-stu-id="d3db4-238">The default value is: `http://localhost:5985/WSMAN`.</span></span>

<span data-ttu-id="d3db4-239">Если не указать **ConnectionURI** , можно использовать параметры **UseSSL** , **ComputerName** , **Port** и **applicationName** , чтобы указать значения **ConnectionURI** .</span><span class="sxs-lookup"><span data-stu-id="d3db4-239">If you do not specify a **ConnectionUri** , you can use the **UseSSL** , **ComputerName** , **Port** , and **ApplicationName** parameters to specify the **ConnectionURI** values.</span></span> <span data-ttu-id="d3db4-240">Допустимые значения для сегмента транспорта URI — HTTP и HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d3db4-240">Valid values for the Transport segment of the URI are HTTP and HTTPS.</span></span> <span data-ttu-id="d3db4-241">Если указать URI подключения с сегментом Transport, но не указать порт, сеанс будет создан со стандартными портами: 80 для HTTP и 443 для HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d3db4-241">If you specify a connection URI with a Transport segment, but do not specify a port, the session is created with standards ports: 80 for HTTP and 443 for HTTPS.</span></span> <span data-ttu-id="d3db4-242">Чтобы использовать порты по умолчанию для удаленного взаимодействия PowerShell, укажите порт 5985 для HTTP или 5986 для HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d3db4-242">To use the default ports for PowerShell remoting, specify port 5985 for HTTP or 5986 for HTTPS.</span></span>

<span data-ttu-id="d3db4-243">Если конечный компьютер перенаправляет подключение к другому универсальному коду ресурса (URI), PowerShell предотвращает перенаправление, если в команде не используется параметр **AllowRedirection** .</span><span class="sxs-lookup"><span data-stu-id="d3db4-243">If the destination computer redirects the connection to a different URI, PowerShell prevents the redirection unless you use the **AllowRedirection** parameter in the command.</span></span>

<span data-ttu-id="d3db4-244">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="d3db4-244">This parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="d3db4-245">Этот параметр получает сеансы только с компьютеров, на которых выполняется Windows PowerShell 3,0 или более поздней версии Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d3db4-245">This parameter gets sessions only from computers that run Windows PowerShell 3.0 or later versions of Windows PowerShell.</span></span> <span data-ttu-id="d3db4-246">Предыдущие версии не хранят сеансы.</span><span class="sxs-lookup"><span data-stu-id="d3db4-246">Earlier versions do not store sessions.</span></span>

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

### <span data-ttu-id="d3db4-247">-ContainerId</span><span class="sxs-lookup"><span data-stu-id="d3db4-247">-ContainerId</span></span>

<span data-ttu-id="d3db4-248">Указывает массив идентификаторов контейнеров.</span><span class="sxs-lookup"><span data-stu-id="d3db4-248">Specifies an array of IDs of containers.</span></span> <span data-ttu-id="d3db4-249">Этот командлет запускает интерактивный сеанс с каждым из указанных контейнеров.</span><span class="sxs-lookup"><span data-stu-id="d3db4-249">This cmdlet starts an interactive session with each of the specified containers.</span></span> <span data-ttu-id="d3db4-250">Используйте `docker ps` команду, чтобы получить список идентификаторов контейнеров.</span><span class="sxs-lookup"><span data-stu-id="d3db4-250">Use the `docker ps` command to get a list of container IDs.</span></span> <span data-ttu-id="d3db4-251">Дополнительные сведения см. в справке по команде [DOCKER PS](https://docs.docker.com/engine/reference/commandline/ps/) .</span><span class="sxs-lookup"><span data-stu-id="d3db4-251">For more information, see the help for the [docker ps](https://docs.docker.com/engine/reference/commandline/ps/) command.</span></span>

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

### <span data-ttu-id="d3db4-252">-Credential</span><span class="sxs-lookup"><span data-stu-id="d3db4-252">-Credential</span></span>

<span data-ttu-id="d3db4-253">Указывает учетные данные пользователя.</span><span class="sxs-lookup"><span data-stu-id="d3db4-253">Specifies a user credential.</span></span> <span data-ttu-id="d3db4-254">Этот командлет выполняет команду с разрешениями указанного пользователя.</span><span class="sxs-lookup"><span data-stu-id="d3db4-254">This cmdlet runs the command with the permissions of the specified user.</span></span> <span data-ttu-id="d3db4-255">Укажите учетную запись пользователя, имеющую разрешение на подключение к удаленному компьютеру, и выполните `Get-PSSession` команду.</span><span class="sxs-lookup"><span data-stu-id="d3db4-255">Specify a user account that has permission to connect to the remote computer and run a `Get-PSSession` command.</span></span> <span data-ttu-id="d3db4-256">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="d3db4-256">The default is the current user.</span></span>

<span data-ttu-id="d3db4-257">Введите имя пользователя, например **User01** или **Domain01\User01** , либо введите объект **PSCredential** , созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="d3db4-257">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="d3db4-258">Если ввести имя пользователя, будет предложено ввести пароль.</span><span class="sxs-lookup"><span data-stu-id="d3db4-258">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="d3db4-259">Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).</span><span class="sxs-lookup"><span data-stu-id="d3db4-259">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="d3db4-260">Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="d3db4-260">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

<span data-ttu-id="d3db4-261">Этот параметр задает временное подключение, созданное для выполнения `Get-PSSession` команды с параметром **ComputerName** или **ConnectionURI** .</span><span class="sxs-lookup"><span data-stu-id="d3db4-261">This parameter configures to the temporary connection that is created to run a `Get-PSSession` command with the **ComputerName** or **ConnectionUri** parameter.</span></span>

<span data-ttu-id="d3db4-262">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="d3db4-262">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="d3db4-263">-Id</span><span class="sxs-lookup"><span data-stu-id="d3db4-263">-Id</span></span>

<span data-ttu-id="d3db4-264">Указывает массив идентификаторов сеансов.</span><span class="sxs-lookup"><span data-stu-id="d3db4-264">Specifies an array of session IDs.</span></span> <span data-ttu-id="d3db4-265">Этот командлет возвращает только сеансы с указанными идентификаторами.</span><span class="sxs-lookup"><span data-stu-id="d3db4-265">This cmdlet gets only the sessions with the specified IDs.</span></span> <span data-ttu-id="d3db4-266">Введите один или несколько идентификаторов, разделенных запятыми, или используйте оператор Range (..), чтобы указать диапазон идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="d3db4-266">Type one or more IDs, separated by commas, or use the range operator (..) to specify a range of IDs.</span></span> <span data-ttu-id="d3db4-267">Параметр ID нельзя использовать вместе с параметром **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="d3db4-267">You cannot use the ID parameter together with the **ComputerName** parameter.</span></span>

<span data-ttu-id="d3db4-268">Идентификатор — это целое число, которое однозначно определяет управляемые пользователем сеансы в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="d3db4-268">An ID is an integer that uniquely identifies the user-managed sessions in the current session.</span></span> <span data-ttu-id="d3db4-269">Проще запомнить и ввести, чем **InstanceId** , но он уникален только в пределах текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="d3db4-269">It is easier to remember and type than the **InstanceId** , but it is unique only within the current session.</span></span> <span data-ttu-id="d3db4-270">Идентификатор сеанса хранится в свойстве ID сеанса.</span><span class="sxs-lookup"><span data-stu-id="d3db4-270">The ID of a session is stored in the ID property of the session.</span></span>

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

### <span data-ttu-id="d3db4-271">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="d3db4-271">-InstanceId</span></span>

<span data-ttu-id="d3db4-272">Указывает массив идентификаторов экземпляров сеансов.</span><span class="sxs-lookup"><span data-stu-id="d3db4-272">Specifies an array of instance IDs of sessions.</span></span> <span data-ttu-id="d3db4-273">Этот командлет возвращает только сеансы с указанными идентификаторами экземпляра.</span><span class="sxs-lookup"><span data-stu-id="d3db4-273">This cmdlet gets only the sessions with the specified instance IDs.</span></span>

<span data-ttu-id="d3db4-274">Идентификатор экземпляра — это GUID, однозначно определяющий сеанс на локальном или удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="d3db4-274">The instance ID is a GUID that uniquely identifies a session on a local or remote computer.</span></span> <span data-ttu-id="d3db4-275">Идентификатор **InstanceId** уникален, даже если в PowerShell работает несколько сеансов.</span><span class="sxs-lookup"><span data-stu-id="d3db4-275">The **InstanceID** is unique, even when you have multiple sessions running in PowerShell.</span></span>

<span data-ttu-id="d3db4-276">Идентификатор экземпляра сеанса хранится в свойстве сеанса **InstanceID** .</span><span class="sxs-lookup"><span data-stu-id="d3db4-276">The instance ID of a session is stored in the **InstanceID** property of the session.</span></span>

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

### <span data-ttu-id="d3db4-277">-Name</span><span class="sxs-lookup"><span data-stu-id="d3db4-277">-Name</span></span>

<span data-ttu-id="d3db4-278">Указывает массив имен сеансов.</span><span class="sxs-lookup"><span data-stu-id="d3db4-278">Specifies an array of session names.</span></span> <span data-ttu-id="d3db4-279">Этот командлет возвращает только сеансы с указанными понятными именами.</span><span class="sxs-lookup"><span data-stu-id="d3db4-279">This cmdlet gets only the sessions that have the specified friendly names.</span></span> <span data-ttu-id="d3db4-280">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="d3db4-280">Wildcard characters are permitted.</span></span>

<span data-ttu-id="d3db4-281">Понятное имя сеанса хранится в свойстве **Name** .</span><span class="sxs-lookup"><span data-stu-id="d3db4-281">The friendly name of a session is stored in the **Name** property of the session.</span></span>

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

### <span data-ttu-id="d3db4-282">-Port</span><span class="sxs-lookup"><span data-stu-id="d3db4-282">-Port</span></span>

<span data-ttu-id="d3db4-283">Указывает указанный сетевой порт, используемый для временного подключения, в котором `Get-PSSession` выполняется команда.</span><span class="sxs-lookup"><span data-stu-id="d3db4-283">Specifies the specified network port that is used for the temporary connection in which the `Get-PSSession` command runs.</span></span> <span data-ttu-id="d3db4-284">Для подключения к удаленному компьютеру требуется, чтобы он прослушивал порт, используемый соединением.</span><span class="sxs-lookup"><span data-stu-id="d3db4-284">To connect to a remote computer, the remote computer must be listening on the port that the connection uses.</span></span> <span data-ttu-id="d3db4-285">Порты по умолчанию — 5985, то есть порт WinRM для HTTP, а 5986 — порт WinRM для HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d3db4-285">The default ports are 5985, which is the WinRM port for HTTP, and 5986, which is the WinRM port for HTTPS.</span></span>

<span data-ttu-id="d3db4-286">Прежде чем использовать альтернативный порт, необходимо настроить прослушиватель WinRM на удаленном компьютере для прослушивания по этому порту.</span><span class="sxs-lookup"><span data-stu-id="d3db4-286">Before using an alternate port, you must configure the WinRM listener on the remote computer to listen at that port.</span></span> <span data-ttu-id="d3db4-287">Чтобы настроить прослушиватель, введите следующие две команды в командной строке PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d3db4-287">To configure the listener, type the following two commands at the PowerShell prompt:</span></span>

`Remove-Item -Path WSMan:\Localhost\listener\listener* -Recurse`

`New-Item -Path WSMan:\Localhost\listener -Transport http -Address * -Port \<port-number\>`

<span data-ttu-id="d3db4-288">Этот параметр задает временное подключение, созданное для выполнения `Get-PSSession` команды с параметром **ComputerName** или **ConnectionURI** .</span><span class="sxs-lookup"><span data-stu-id="d3db4-288">This parameter configures to the temporary connection that is created to run a `Get-PSSession` command with the **ComputerName** or **ConnectionUri** parameter.</span></span>

<span data-ttu-id="d3db4-289">Не используйте параметр **Port** , если этого можно избежать.</span><span class="sxs-lookup"><span data-stu-id="d3db4-289">Do not use the **Port** parameter unless you must.</span></span> <span data-ttu-id="d3db4-290">**Порт** , заданный в команде, применяется ко всем компьютерам или сеансам, на которых выполняется команда.</span><span class="sxs-lookup"><span data-stu-id="d3db4-290">The **Port** set in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="d3db4-291">Альтернативный порт может помешать выполнению команды на всех компьютерах.</span><span class="sxs-lookup"><span data-stu-id="d3db4-291">An alternate port setting might prevent the command from running on all computers.</span></span>

<span data-ttu-id="d3db4-292">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="d3db4-292">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="d3db4-293">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="d3db4-293">-SessionOption</span></span>

<span data-ttu-id="d3db4-294">Задает дополнительные параметры для сеанса.</span><span class="sxs-lookup"><span data-stu-id="d3db4-294">Specifies advanced options for the session.</span></span> <span data-ttu-id="d3db4-295">Введите объект **SessionOption** , например объект, созданный с помощью командлета New-PSSessionOption, или хэш-таблицу, где ключи — это имена параметров сеанса, а значения — это значения параметров сеанса.</span><span class="sxs-lookup"><span data-stu-id="d3db4-295">Enter a **SessionOption** object, such as one that you create by using the New-PSSessionOption cmdlet, or a hash table in which the keys are session option names and the values are session option values.</span></span>

<span data-ttu-id="d3db4-296">Значения по умолчанию для параметров определяются значением привилегированной переменной $PSSessionOption, если оно задано.</span><span class="sxs-lookup"><span data-stu-id="d3db4-296">The default values for the options are determined by the value of the $PSSessionOption preference variable, if it is set.</span></span> <span data-ttu-id="d3db4-297">В противном случае значения по умолчанию задаются параметрами, указанными в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="d3db4-297">Otherwise, the default values are established by options set in the session configuration.</span></span>

<span data-ttu-id="d3db4-298">Значения параметров сеанса имеют приоритет над значениями по умолчанию, заданными в переменной $PSSessionOption и конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="d3db4-298">The session option values take precedence over default values for sessions set in the $PSSessionOption preference variable and in the session configuration.</span></span> <span data-ttu-id="d3db4-299">Однако они не имеют приоритет над максимальными значениями, квотами и ограничениями, заданными в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="d3db4-299">However, they do not take precedence over maximum values, quotas or limits set in the session configuration.</span></span>

<span data-ttu-id="d3db4-300">Описание параметров сеанса, включая значения по умолчанию, см. в разделе `New-PSSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="d3db4-300">For a description of the session options, including the default values, see `New-PSSessionOption`.</span></span>
<span data-ttu-id="d3db4-301">Дополнительные сведения о `$PSSessionOption` переменной предпочтений см. в разделе [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="d3db4-301">For information about the `$PSSessionOption` preference variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span> <span data-ttu-id="d3db4-302">Дополнительные сведения о конфигурациях сеансов см. в разделе [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="d3db4-302">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

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

### <span data-ttu-id="d3db4-303">-State</span><span class="sxs-lookup"><span data-stu-id="d3db4-303">-State</span></span>

<span data-ttu-id="d3db4-304">Указывает состояние сеанса.</span><span class="sxs-lookup"><span data-stu-id="d3db4-304">Specifies a session state.</span></span> <span data-ttu-id="d3db4-305">Этот командлет возвращает только сеансы в указанном состоянии.</span><span class="sxs-lookup"><span data-stu-id="d3db4-305">This cmdlet gets only sessions in the specified state.</span></span> <span data-ttu-id="d3db4-306">Допустимые значения для этого параметра: "все", "открыто", "отключено", "закрыто" и "нарушено".</span><span class="sxs-lookup"><span data-stu-id="d3db4-306">The acceptable values for this parameter are: All, Opened, Disconnected, Closed, and Broken.</span></span> <span data-ttu-id="d3db4-307">Значение по умолчанию — All.</span><span class="sxs-lookup"><span data-stu-id="d3db4-307">The default value is All.</span></span>

<span data-ttu-id="d3db4-308">Значение состояния сеанса задается относительно текущих сеансов.</span><span class="sxs-lookup"><span data-stu-id="d3db4-308">The session state value is relative to the current sessions.</span></span> <span data-ttu-id="d3db4-309">Сеансы, которые не были созданы в текущих сеансах и не подключены к текущему сеансу, находятся в состоянии Disconnected, даже если подключены к другому сеансу.</span><span class="sxs-lookup"><span data-stu-id="d3db4-309">Sessions that were not created in the current sessions and are not connected to the current session have a state of Disconnected even when they are connected to a different session.</span></span>

<span data-ttu-id="d3db4-310">Состояние сеанса хранится в свойстве **State** .</span><span class="sxs-lookup"><span data-stu-id="d3db4-310">The state of a session is stored in the **State** property of the session.</span></span>

<span data-ttu-id="d3db4-311">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="d3db4-311">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="d3db4-312">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="d3db4-312">-ThrottleLimit</span></span>

<span data-ttu-id="d3db4-313">Указывает максимальное количество одновременных подключений, которое может быть установлено для выполнения `Get-PSSession` команды.</span><span class="sxs-lookup"><span data-stu-id="d3db4-313">Specifies the maximum number of concurrent connections that can be established to run the `Get-PSSession` command.</span></span> <span data-ttu-id="d3db4-314">Если этот параметр не указан или введено значение 0 (ноль), используется значение по умолчанию — 32.</span><span class="sxs-lookup"><span data-stu-id="d3db4-314">If you omit this parameter or enter a value of 0 (zero), the default value, 32, is used.</span></span> <span data-ttu-id="d3db4-315">Предел регулирования применяется только к текущему командлету, а не к сеансу или компьютеру.</span><span class="sxs-lookup"><span data-stu-id="d3db4-315">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

<span data-ttu-id="d3db4-316">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="d3db4-316">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="d3db4-317">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="d3db4-317">-UseSSL</span></span>

<span data-ttu-id="d3db4-318">Указывает, что этот командлет использует протокол SSL (SSL) для установления соединения, в котором `Get-PSSession` выполняется команда.</span><span class="sxs-lookup"><span data-stu-id="d3db4-318">Indicates that this cmdlet uses the Secure Sockets Layer (SSL) protocol to establish the connection in which the `Get-PSSession` command runs.</span></span> <span data-ttu-id="d3db4-319">По умолчанию SSL не используется.</span><span class="sxs-lookup"><span data-stu-id="d3db4-319">By default, SSL is not used.</span></span> <span data-ttu-id="d3db4-320">Если вы используете этот параметр, но SSL недоступен для порт, указанному в команде, она завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="d3db4-320">If you use this parameter, but SSL is not available on the port used for the command, the command fails.</span></span>

<span data-ttu-id="d3db4-321">Этот параметр настраивает временное подключение, созданное для выполнения `Get-PSSession` команды с параметром **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="d3db4-321">This parameter configures the temporary connection that is created to run a `Get-PSSession` command with the **ComputerName** parameter.</span></span>

<span data-ttu-id="d3db4-322">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="d3db4-322">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="d3db4-323">— VMId</span><span class="sxs-lookup"><span data-stu-id="d3db4-323">-VMId</span></span>

<span data-ttu-id="d3db4-324">Указывает массив ИДЕНТИФИКАТОРов виртуальных машин.</span><span class="sxs-lookup"><span data-stu-id="d3db4-324">Specifies an array of ID of virtual machines.</span></span> <span data-ttu-id="d3db4-325">Этот командлет запускает интерактивный сеанс с каждой из указанных виртуальных машин.</span><span class="sxs-lookup"><span data-stu-id="d3db4-325">This cmdlet starts an interactive session with each of the specified virtual machines.</span></span> <span data-ttu-id="d3db4-326">Чтобы просмотреть доступные виртуальные машины, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d3db4-326">To see the virtual machines that are available to you, use the following command:</span></span>

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

### <span data-ttu-id="d3db4-327">-VMName</span><span class="sxs-lookup"><span data-stu-id="d3db4-327">-VMName</span></span>

<span data-ttu-id="d3db4-328">Указывает массив имен виртуальных машин.</span><span class="sxs-lookup"><span data-stu-id="d3db4-328">Specifies an array of names of virtual machines.</span></span> <span data-ttu-id="d3db4-329">Этот командлет запускает интерактивный сеанс с каждой из указанных виртуальных машин.</span><span class="sxs-lookup"><span data-stu-id="d3db4-329">This cmdlet starts an interactive session with each of the specified virtual machines.</span></span> <span data-ttu-id="d3db4-330">Чтобы просмотреть доступные виртуальные машины, используйте `Get-VM` командлет.</span><span class="sxs-lookup"><span data-stu-id="d3db4-330">To see the virtual machines that are available to you, use the `Get-VM` cmdlet.</span></span>

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

### <span data-ttu-id="d3db4-331">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="d3db4-331">CommonParameters</span></span>

<span data-ttu-id="d3db4-332">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d3db4-332">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d3db4-333">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d3db4-333">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d3db4-334">Входные данные</span><span class="sxs-lookup"><span data-stu-id="d3db4-334">INPUTS</span></span>

### <span data-ttu-id="d3db4-335">Нет</span><span class="sxs-lookup"><span data-stu-id="d3db4-335">None</span></span>

<span data-ttu-id="d3db4-336">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="d3db4-336">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="d3db4-337">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="d3db4-337">OUTPUTS</span></span>

### <span data-ttu-id="d3db4-338">System.Management.Automation.Runspaces.PSSession</span><span class="sxs-lookup"><span data-stu-id="d3db4-338">System.Management.Automation.Runspaces.PSSession</span></span>

## <span data-ttu-id="d3db4-339">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="d3db4-339">NOTES</span></span>

- <span data-ttu-id="d3db4-340">Этот командлет получает управляемые пользователем сеансы **PSSession** (например, созданные с помощью командлетов New-PSSession, `Enter-PSSession` и Invoke-Command).</span><span class="sxs-lookup"><span data-stu-id="d3db4-340">This cmdlet gets user-managed sessions **PSSession** objects" such as those that are created by using the New-PSSession, `Enter-PSSession`, and Invoke-Command cmdlets.</span></span> <span data-ttu-id="d3db4-341">Он не получает управляемый системой сеанс, который создается при запуске PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d3db4-341">It does not get the system-managed session that is created when you start PowerShell.</span></span>
- <span data-ttu-id="d3db4-342">Начиная с Windows PowerShell 3,0, объекты **PSSession** хранятся на компьютере, который находится на стороне сервера или получает окончание соединения.</span><span class="sxs-lookup"><span data-stu-id="d3db4-342">Starting in Windows PowerShell 3.0, **PSSession** objects are stored on the computer that is at the server-side or receiving end of a connection.</span></span> <span data-ttu-id="d3db4-343">Чтобы получить сеансы, хранящиеся на локальном или удаленном компьютере, PowerShell устанавливает временный сеанс на указанном компьютере и выполняет команды запросов в сеансе.</span><span class="sxs-lookup"><span data-stu-id="d3db4-343">To get the sessions that are stored on the local computer or a remote computer, PowerShell establishes a temporary session to the specified computer and runs query commands in the session.</span></span>
- <span data-ttu-id="d3db4-344">Чтобы получить сеансы, которые подключены к удаленному компьютеру, укажите удаленный компьютер в параметре **ComputerName** или **ConnectionUri** .</span><span class="sxs-lookup"><span data-stu-id="d3db4-344">To get sessions that connect to a remote computer, use the **ComputerName** or **ConnectionUri** parameters to specify the remote computer.</span></span> <span data-ttu-id="d3db4-345">Чтобы отфильтровать сеансы, которые `Get-PSSession` получают, используйте параметры **Name** , **ID** , **InstanceId** и **State** .</span><span class="sxs-lookup"><span data-stu-id="d3db4-345">To filter the sessions that `Get-PSSession` gets, use the **Name** , **ID** , **InstanceID** , and **State** parameters.</span></span> <span data-ttu-id="d3db4-346">Используйте остальные параметры, чтобы настроить временный сеанс, в котором `Get-PSSession` используется.</span><span class="sxs-lookup"><span data-stu-id="d3db4-346">Use the remaining parameters to configure the temporary session that `Get-PSSession` uses.</span></span>
- <span data-ttu-id="d3db4-347">При использовании параметров **ComputerName** или **ConnectionURI** `Get-PSSession` получает только сеансы с компьютеров, на которых выполняется Windows PowerShell 3,0 и более поздних версий PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d3db4-347">When you use the **ComputerName** or **ConnectionUri** parameters, `Get-PSSession` gets only sessions from computers running Windows PowerShell 3.0 and later versions of PowerShell.</span></span>
- <span data-ttu-id="d3db4-348">Значение свойства **State** для **PSSession** задается относительно текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="d3db4-348">The value of the **State** property of a **PSSession** is relative to the current session.</span></span>
  <span data-ttu-id="d3db4-349">Таким образом, значение **disconnected** означает, что **сеанс PSSession** не подключен к текущему сеансу.</span><span class="sxs-lookup"><span data-stu-id="d3db4-349">Therefore, a value of **Disconnected** means that the **PSSession** is not connected to the current session.</span></span> <span data-ttu-id="d3db4-350">Однако это не означает, что **сеанс PSSession** отключен от всех сеансов.</span><span class="sxs-lookup"><span data-stu-id="d3db4-350">However, it does not mean that the **PSSession** is disconnected from all sessions.</span></span> <span data-ttu-id="d3db4-351">Он может быть подключен к другому сеансу.</span><span class="sxs-lookup"><span data-stu-id="d3db4-351">It might be connected to a different session.</span></span> <span data-ttu-id="d3db4-352">Чтобы определить, можно ли подключиться к сеансу **PSSession** или повторно подключиться к нему из текущего сеанса, используйте свойство **Availability** .</span><span class="sxs-lookup"><span data-stu-id="d3db4-352">To determine whether you can connect or reconnect to the **PSSession** from the current session, use the **Availability** property.</span></span>

<span data-ttu-id="d3db4-353">Если свойство **Availability** имеет значение **None** , подключиться к сеансу можно.</span><span class="sxs-lookup"><span data-stu-id="d3db4-353">An **Availability** value of **None** indicates that you can connect to the session.</span></span> <span data-ttu-id="d3db4-354">Значение **занято** указывает, что невозможно подключиться к сеансу **PSSession** , так как он подключен к другому сеансу.</span><span class="sxs-lookup"><span data-stu-id="d3db4-354">A value of **Busy** indicates that you cannot connect to the **PSSession** because it is connected to another session.</span></span>

<span data-ttu-id="d3db4-355">Дополнительные сведения о значениях свойства **State** в сеансах см. в разделе [рунспацестате enumeration](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspacestate).</span><span class="sxs-lookup"><span data-stu-id="d3db4-355">For more information about the values of the **State** property of sessions, see [RunspaceState Enumeration](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspacestate).</span></span>

<span data-ttu-id="d3db4-356">Дополнительные сведения о значениях свойства **Availability** сеансов см. в разделе [рунспацеаваилабилити enumeration](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspaceavailability).</span><span class="sxs-lookup"><span data-stu-id="d3db4-356">For more information about the values of the **Availability** property of sessions, see [RunspaceAvailability Enumeration](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspaceavailability).</span></span>

## <span data-ttu-id="d3db4-357">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="d3db4-357">RELATED LINKS</span></span>

[<span data-ttu-id="d3db4-358">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="d3db4-358">Connect-PSSession</span></span>](Connect-PSSession.md)

[<span data-ttu-id="d3db4-359">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="d3db4-359">Disconnect-PSSession</span></span>](Disconnect-PSSession.md)

[<span data-ttu-id="d3db4-360">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="d3db4-360">Receive-PSSession</span></span>](Receive-PSSession.md)

[<span data-ttu-id="d3db4-361">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="d3db4-361">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="d3db4-362">Exit-PSSession;</span><span class="sxs-lookup"><span data-stu-id="d3db4-362">Exit-PSSession</span></span>](Exit-PSSession.md)

[<span data-ttu-id="d3db4-363">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="d3db4-363">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="d3db4-364">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="d3db4-364">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="d3db4-365">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="d3db4-365">Remove-PSSession</span></span>](Remove-PSSession.md)

[<span data-ttu-id="d3db4-366">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="d3db4-366">about_PSSessions</span></span>](About/about_PSSessions.md)

[<span data-ttu-id="d3db4-367">about_Remote</span><span class="sxs-lookup"><span data-stu-id="d3db4-367">about_Remote</span></span>](About/about_Remote.md)
