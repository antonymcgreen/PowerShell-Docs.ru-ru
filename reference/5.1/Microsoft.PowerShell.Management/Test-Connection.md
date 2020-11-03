---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/09/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/test-connection?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-Connection
ms.openlocfilehash: a8d3923db69a20cfada58391944b592cf999e6ef
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227833"
---
# <span data-ttu-id="7a832-103">Test-Connection</span><span class="sxs-lookup"><span data-stu-id="7a832-103">Test-Connection</span></span>

## <span data-ttu-id="7a832-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="7a832-104">SYNOPSIS</span></span>
<span data-ttu-id="7a832-105">Отправляет пакеты запроса проверки связи ICMP или проверки связи на один или несколько компьютеров.</span><span class="sxs-lookup"><span data-stu-id="7a832-105">Sends ICMP echo request packets, or pings, to one or more computers.</span></span>

## <span data-ttu-id="7a832-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7a832-106">SYNTAX</span></span>

### <span data-ttu-id="7a832-107">Default (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="7a832-107">Default (Default)</span></span>

```
Test-Connection [-AsJob] [-DcomAuthentication <AuthenticationLevel>] [-WsmanAuthentication <String>]
 [-Protocol <String>] [-BufferSize <Int32>] [-ComputerName] <String[]> [-Count <Int32>]
 [-Impersonation <ImpersonationLevel>] [-ThrottleLimit <Int32>] [-TimeToLive <Int32>]
 [-Delay <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="7a832-108">Источник</span><span class="sxs-lookup"><span data-stu-id="7a832-108">Source</span></span>

```
Test-Connection [-AsJob] [-DcomAuthentication <AuthenticationLevel>] [-WsmanAuthentication <String>]
 [-Protocol <String>] [-BufferSize <Int32>] [-ComputerName] <String[]> [-Count <Int32>]
 [-Credential <PSCredential>] [-Source] <String[]> [-Impersonation <ImpersonationLevel>]
 [-ThrottleLimit <Int32>] [-TimeToLive <Int32>] [-Delay <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="7a832-109">Тихий NaN</span><span class="sxs-lookup"><span data-stu-id="7a832-109">Quiet</span></span>

```
Test-Connection [-DcomAuthentication <AuthenticationLevel>] [-WsmanAuthentication <String>]
 [-Protocol <String>] [-BufferSize <Int32>] [-ComputerName] <String[]> [-Count <Int32>]
 [-Impersonation <ImpersonationLevel>] [-TimeToLive <Int32>] [-Delay <Int32>] [-Quiet]
 [<CommonParameters>]
```

## <span data-ttu-id="7a832-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7a832-110">DESCRIPTION</span></span>

<span data-ttu-id="7a832-111">`Test-Connection`Командлет отправляет пакеты эхо-запросов протокола ICMP (ping) на один или несколько удаленных компьютеров и возвращает ответ на эхо-ответы.</span><span class="sxs-lookup"><span data-stu-id="7a832-111">The `Test-Connection` cmdlet sends Internet Control Message Protocol (ICMP) echo request packets, or pings, to one or more remote computers and returns the echo response replies.</span></span> <span data-ttu-id="7a832-112">С помощью этого командлета можно определить, можно ли связаться с определенным компьютером по IP-сети.</span><span class="sxs-lookup"><span data-stu-id="7a832-112">You can use this cmdlet to determine whether a particular computer can be contacted across an IP network.</span></span>

<span data-ttu-id="7a832-113">С помощью параметров можно `Test-Connection` указать как отправляющее, так и принимающее компьютеры, чтобы выполнить команду в качестве фонового задания, установить время ожидания и количество проверок связи, а также настроить подключение и проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="7a832-113">You can use the parameters of `Test-Connection` to specify both the sending and receiving computers, to run the command as a background job, to set a time-out and number of pings, and to configure the connection and authentication.</span></span>

<span data-ttu-id="7a832-114">В отличие от знакомой команды **ping** , `Test-Connection` возвращает объект **Win32_PingStatus** , который можно исследовать в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7a832-114">Unlike the familiar **ping** command, `Test-Connection` returns a **Win32_PingStatus** object that you can investigate in PowerShell.</span></span> <span data-ttu-id="7a832-115">Параметр **quiet** возвращает **логическое** значение в объекте **System. Boolean** для каждого проверенного подключения.</span><span class="sxs-lookup"><span data-stu-id="7a832-115">The **Quiet** parameter returns a **Boolean** value in a **System.Boolean** object for each tested connection.</span></span> <span data-ttu-id="7a832-116">Если тестируется несколько подключений, возвращается массив **логических** значений.</span><span class="sxs-lookup"><span data-stu-id="7a832-116">If multiple connections are tested, an array of **Boolean** values is returned.</span></span>

## <span data-ttu-id="7a832-117">Примеры</span><span class="sxs-lookup"><span data-stu-id="7a832-117">EXAMPLES</span></span>

### <span data-ttu-id="7a832-118">Пример 1. Отправка эхо-запросов на удаленный компьютер</span><span class="sxs-lookup"><span data-stu-id="7a832-118">Example 1: Send echo requests to a remote computer</span></span>

<span data-ttu-id="7a832-119">Этот пример отправляет пакеты эхо-запросов с локального компьютера на компьютер Server01.</span><span class="sxs-lookup"><span data-stu-id="7a832-119">This example sends echo request packets from the local computer to the Server01 computer.</span></span>

```powershell
Test-Connection -ComputerName Server01
```

```Output
Source        Destination     IPV4Address     IPV6Address  Bytes    Time(ms)
------        -----------     -----------     -----------  -----    --------
ADMIN1        Server01         10.59.137.44                32       0
ADMIN1        Server01         10.59.137.44                32       0
ADMIN1        Server01         10.59.137.44                32       0
ADMIN1        Server01         10.59.137.44                32       1
```

<span data-ttu-id="7a832-120">`Test-Connection` использует параметр **ComputerName** для указания компьютера Server01.</span><span class="sxs-lookup"><span data-stu-id="7a832-120">`Test-Connection` uses the **ComputerName** parameter to specify the Server01 computer.</span></span>

### <span data-ttu-id="7a832-121">Пример 2. Отправка эхо-запросов на несколько компьютеров</span><span class="sxs-lookup"><span data-stu-id="7a832-121">Example 2: Send echo requests to several computers</span></span>

<span data-ttu-id="7a832-122">Этот пример отправляет команды ping с локального компьютера на несколько удаленных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="7a832-122">This example sends pings from the local computer to several remote computers.</span></span>

```powershell
Test-Connection -ComputerName Server01, Server02, Server12
```

### <span data-ttu-id="7a832-123">Пример 3. Отправка эхо-запросов с нескольких компьютеров на компьютер</span><span class="sxs-lookup"><span data-stu-id="7a832-123">Example 3: Send echo requests from several computers to a computer</span></span>

<span data-ttu-id="7a832-124">В этом примере команды ping отправляются с разных исходных компьютеров на один удаленный компьютер Server01.</span><span class="sxs-lookup"><span data-stu-id="7a832-124">This example sends pings from different source computers to a single remote computer, Server01.</span></span>

```powershell
Test-Connection -Source Server02, Server12, localhost -ComputerName Server01 -Credential Domain01\Admin01
```

<span data-ttu-id="7a832-125">`Test-Connection` использует параметр **Credential** для указания учетных данных пользователя, имеющего разрешение на отправку запроса проверки связи с исходных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="7a832-125">`Test-Connection` uses the **Credential** parameter to specify the credentials of a user who has permission to send a ping request from the source computers.</span></span> <span data-ttu-id="7a832-126">Этот формат команды можно использовать для тестирования задержки подключения из нескольких точек.</span><span class="sxs-lookup"><span data-stu-id="7a832-126">Use this command format to test the latency of connections from multiple points.</span></span>

### <span data-ttu-id="7a832-127">Пример 4. Использование параметров для настройки команды теста</span><span class="sxs-lookup"><span data-stu-id="7a832-127">Example 4: Use parameters to customize the test command</span></span>

<span data-ttu-id="7a832-128">В этом примере `Test-Connection` для настройки команды используются параметры.</span><span class="sxs-lookup"><span data-stu-id="7a832-128">This example uses the parameters of `Test-Connection` to customize the command.</span></span> <span data-ttu-id="7a832-129">Локальный компьютер отправляет тест проверки связи на удаленный компьютер.</span><span class="sxs-lookup"><span data-stu-id="7a832-129">The local computer sends a ping test to a remote computer.</span></span>

```powershell
Test-Connection -ComputerName Server01 -Count 3 -Delay 2 -TTL 255 -BufferSize 256 -ThrottleLimit 32
```

<span data-ttu-id="7a832-130">`Test-Connection` использует параметр **ComputerName** для указания Server01.</span><span class="sxs-lookup"><span data-stu-id="7a832-130">`Test-Connection` uses the **ComputerName** parameter to specify Server01.</span></span> <span data-ttu-id="7a832-131">Параметр **Count** указывает три сообщения проверки связи, отправляемые на компьютер Server01 с **задержкой** в 2 секунды.</span><span class="sxs-lookup"><span data-stu-id="7a832-131">The **Count** parameter specifies three pings are sent to the Server01 computer with a **Delay** of 2-second intervals.</span></span>

<span data-ttu-id="7a832-132">Эти параметры можно использовать, если ожидается, что ответ на запрос проверки связи займет больше времени, чем обычно, из-за расширенного числа прыжков или состояния сети с высоким трафиком.</span><span class="sxs-lookup"><span data-stu-id="7a832-132">You might use these options when the ping response is expected to take longer than usual, either because of an extended number of hops or a high-traffic network condition.</span></span>

### <span data-ttu-id="7a832-133">Пример 5. выполнение теста в качестве фонового задания</span><span class="sxs-lookup"><span data-stu-id="7a832-133">Example 5: Run a test as a background job</span></span>

<span data-ttu-id="7a832-134">В этом примере показано, как выполнить `Test-Connection` команду в качестве фонового задания PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7a832-134">This example shows how to run a `Test-Connection` command as a PowerShell background job.</span></span>

```powershell
$job = Test-Connection -ComputerName (Get-Content Servers.txt) -AsJob
if ($job.JobStateInfo.State -ne "Running") {$Results = Receive-Job $job}
```

<span data-ttu-id="7a832-135">`Test-Connection`Команда проверяет связь между многими компьютерами в Организации.</span><span class="sxs-lookup"><span data-stu-id="7a832-135">The `Test-Connection` command pings many computers in an enterprise.</span></span> <span data-ttu-id="7a832-136">Значение параметра **ComputerName** — это `Get-Content` команда, которая считывает список имен компьютеров из `Servers.txt file` .</span><span class="sxs-lookup"><span data-stu-id="7a832-136">The value of the **ComputerName** parameter is a `Get-Content` command that reads a list of computer names from the `Servers.txt file`.</span></span> <span data-ttu-id="7a832-137">Команда использует параметр **AsJob** для выполнения команды в качестве фонового задания и сохраняет задание в `$job` переменной.</span><span class="sxs-lookup"><span data-stu-id="7a832-137">The command uses the **AsJob** parameter to run the command as a background job and it saves the job in the `$job` variable.</span></span>

<span data-ttu-id="7a832-138">`if`Команда проверяет, что задание еще не выполняется.</span><span class="sxs-lookup"><span data-stu-id="7a832-138">The `if` command checks to see that the job isn't still running.</span></span> <span data-ttu-id="7a832-139">Если задание не выполняется, `Receive-Job` получает результаты и сохраняет их в `$Results` переменной.</span><span class="sxs-lookup"><span data-stu-id="7a832-139">If the job isn't running, `Receive-Job` gets the results and stores them in the `$Results` variable.</span></span>

### <span data-ttu-id="7a832-140">Пример 6. Проверка связи с удаленным компьютером с учетными данными</span><span class="sxs-lookup"><span data-stu-id="7a832-140">Example 6: Ping a remote computer with credentials</span></span>

<span data-ttu-id="7a832-141">Эта команда использует `Test-Connection` командлет для проверки связи с удаленным компьютером.</span><span class="sxs-lookup"><span data-stu-id="7a832-141">This command uses the `Test-Connection` cmdlet to ping a remote computer.</span></span>

```powershell
Test-Connection Server55 -Credential Domain55\User01 -Impersonation Identify
```

<span data-ttu-id="7a832-142">Команда использует параметр **Credential** , чтобы указать учетную запись пользователя, имеющего разрешение на проверку связи с удаленным компьютером, и параметр **олицетворения** , чтобы изменить уровень олицетворения для **определения** .</span><span class="sxs-lookup"><span data-stu-id="7a832-142">The command uses the **Credential** parameter to specify a user account that has permission to ping the remote computer and the **Impersonation** parameter to change the impersonation level to **Identify** .</span></span>

### <span data-ttu-id="7a832-143">Пример 7. Создание сеанса только в случае успешности проверки соединения</span><span class="sxs-lookup"><span data-stu-id="7a832-143">Example 7: Create a session only if a connection test succeeds</span></span>

<span data-ttu-id="7a832-144">Этот пример создает сеанс на компьютере Server01, только если по крайней мере один из пакетов проверки связи успешно отправлен на компьютер.</span><span class="sxs-lookup"><span data-stu-id="7a832-144">This example creates a session on the Server01 computer only if at least one of the pings sent to the computer succeeds.</span></span>

```powershell
if (Test-Connection -ComputerName Server01 -Quiet) {New-PSSession Server01}
```

<span data-ttu-id="7a832-145">`if`Команда использует `Test-Connection` командлет для проверки связи с компьютером Server01.</span><span class="sxs-lookup"><span data-stu-id="7a832-145">The `if` command uses the `Test-Connection` cmdlet to ping the Server01 computer.</span></span> <span data-ttu-id="7a832-146">Команда использует параметр **quiet** , который возвращает **логическое** значение вместо объекта **Win32_PingStatus** .</span><span class="sxs-lookup"><span data-stu-id="7a832-146">The command uses the **Quiet** parameter, which returns a **Boolean** value, instead of a **Win32_PingStatus** object.</span></span> <span data-ttu-id="7a832-147">Значение равно, `$True` Если любая из четырех проверок связи успешно выполнена, и в противном случае — `$False` .</span><span class="sxs-lookup"><span data-stu-id="7a832-147">The value is `$True` if any of the four pings succeed and is, otherwise, `$False`.</span></span>

<span data-ttu-id="7a832-148">Если `Test-Connection` команда возвращает значение `$True` , команда использует `New-PSSession` командлет для создания **сеанса PSSession** .</span><span class="sxs-lookup"><span data-stu-id="7a832-148">If the `Test-Connection` command returns a value of `$True`, the command uses the `New-PSSession` cmdlet to create the **PSSession** .</span></span>

## <span data-ttu-id="7a832-149">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7a832-149">PARAMETERS</span></span>

### <span data-ttu-id="7a832-150">-AsJob</span><span class="sxs-lookup"><span data-stu-id="7a832-150">-AsJob</span></span>

<span data-ttu-id="7a832-151">Указывает, что этот командлет выполняется как фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="7a832-151">Indicates that this cmdlet runs as a background job.</span></span>

<span data-ttu-id="7a832-152">Чтобы использовать этот параметр, на локальном и удаленном компьютерах необходимо настроить удаленное взаимодействие, а в Windows Vista и более поздних версиях операционной системы Windows необходимо открыть PowerShell с помощью команды **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="7a832-152">To use this parameter, the local and remote computers must be configured for remoting and, on Windows Vista and later versions of the Windows operating system, you must open PowerShell by using the **Run as administrator** option.</span></span> <span data-ttu-id="7a832-153">Дополнительные сведения см. в разделе [about_Remote_Requirements](../microsoft.powershell.core/about/about_remote_requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a832-153">For more information, see [about_Remote_Requirements](../microsoft.powershell.core/about/about_remote_requirements.md).</span></span>

<span data-ttu-id="7a832-154">При указании параметра **AsJob** команда немедленно возвращает объект, представляющий фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="7a832-154">When you specify the **AsJob** parameter, the command immediately returns an object that represents the background job.</span></span> <span data-ttu-id="7a832-155">Можно продолжить работу в рамках данного сеанса, пока задание завершается.</span><span class="sxs-lookup"><span data-stu-id="7a832-155">You can continue to work in the session while the job finishes.</span></span> <span data-ttu-id="7a832-156">Задание создается на локальном компьютере, а результаты с удаленных компьютеров автоматически возвращаются на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="7a832-156">The job is created on the local computer and the results from remote computers are automatically returned to the local computer.</span></span> <span data-ttu-id="7a832-157">Чтобы получить результаты задания, используйте `Receive-Job` командлет.</span><span class="sxs-lookup"><span data-stu-id="7a832-157">To get the job results, use the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="7a832-158">Дополнительные сведения о фоновых заданиях PowerShell см. в разделе [about_Jobs](../Microsoft.PowerShell.Core/About/about_jobs.md) и [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_remote_jobs.md).</span><span class="sxs-lookup"><span data-stu-id="7a832-158">For more information about PowerShell background jobs, see [about_Jobs](../Microsoft.PowerShell.Core/About/about_jobs.md) and [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_remote_jobs.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Default, Source
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7a832-159">— BufferSize</span><span class="sxs-lookup"><span data-stu-id="7a832-159">-BufferSize</span></span>

<span data-ttu-id="7a832-160">Указывает размер (в байтах) буфера, отправленного с помощью этой команды.</span><span class="sxs-lookup"><span data-stu-id="7a832-160">Specifies the size, in bytes, of the buffer sent with this command.</span></span> <span data-ttu-id="7a832-161">Значение по умолчанию: 32.</span><span class="sxs-lookup"><span data-stu-id="7a832-161">The default value is 32.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: Size, Bytes, BS

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7a832-162">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="7a832-162">-ComputerName</span></span>

<span data-ttu-id="7a832-163">Указывает компьютеры для проверки связи.</span><span class="sxs-lookup"><span data-stu-id="7a832-163">Specifies the computers to ping.</span></span> <span data-ttu-id="7a832-164">Введите имена компьютеров или IP-адреса в формате IPv4 или IPv6.</span><span class="sxs-lookup"><span data-stu-id="7a832-164">Type the computer names or type IP addresses in IPv4 or IPv6 format.</span></span> <span data-ttu-id="7a832-165">Подстановочные знаки не допускаются.</span><span class="sxs-lookup"><span data-stu-id="7a832-165">Wildcard characters are not permitted.</span></span> <span data-ttu-id="7a832-166">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="7a832-166">This parameter is required.</span></span>

<span data-ttu-id="7a832-167">Этот параметр не зависит от удаленного взаимодействия PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7a832-167">This parameter doesn't rely on PowerShell remoting.</span></span> <span data-ttu-id="7a832-168">Параметр **ComputerName** можно использовать, даже если компьютер не настроен для выполнения удаленных команд.</span><span class="sxs-lookup"><span data-stu-id="7a832-168">You can use the **ComputerName** parameter even if your computer isn't configured to run remote commands.</span></span>

> [!NOTE]
> <span data-ttu-id="7a832-169">Параметр **ComputerName** переименовывается в **TargetName** в PowerShell 6,0 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="7a832-169">The **ComputerName** parameter is renamed to **TargetName** in PowerShell 6.0 and above.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN, IPAddress, __SERVER, Server, Destination

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="7a832-170">— Количество</span><span class="sxs-lookup"><span data-stu-id="7a832-170">-Count</span></span>

<span data-ttu-id="7a832-171">Указывает число отправляемых запросов проверки связи.</span><span class="sxs-lookup"><span data-stu-id="7a832-171">Specifies the number of echo requests to send.</span></span> <span data-ttu-id="7a832-172">Значение по умолчанию — 4.</span><span class="sxs-lookup"><span data-stu-id="7a832-172">The default value is 4.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 4
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7a832-173">-Credential</span><span class="sxs-lookup"><span data-stu-id="7a832-173">-Credential</span></span>

<span data-ttu-id="7a832-174">Указывает учетную запись, имеющую разрешение на отправку запроса проверки связи с исходного компьютера.</span><span class="sxs-lookup"><span data-stu-id="7a832-174">Specifies a user account that has permission to send a ping request from the source computer.</span></span> <span data-ttu-id="7a832-175">Введите имя пользователя, например User01 или Domain01\User01, либо введите объект **PSCredential** , например один из `Get-Credential` командлетов.</span><span class="sxs-lookup"><span data-stu-id="7a832-175">Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one from the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="7a832-176">Параметр **Credential** допустим, только если в команде используется параметр **Source** .</span><span class="sxs-lookup"><span data-stu-id="7a832-176">The **Credential** parameter is valid only when the **Source** parameter is used in the command.</span></span> <span data-ttu-id="7a832-177">Учетные данные не влияют на конечный компьютер.</span><span class="sxs-lookup"><span data-stu-id="7a832-177">The credentials don't affect the destination computer.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Source
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7a832-178">-Дкомаусентикатион</span><span class="sxs-lookup"><span data-stu-id="7a832-178">-DcomAuthentication</span></span>

<span data-ttu-id="7a832-179">Указывает уровень проверки подлинности, используемый этим командлетом с WMI.</span><span class="sxs-lookup"><span data-stu-id="7a832-179">Specifies the authentication level that this cmdlet uses with WMI.</span></span>
<span data-ttu-id="7a832-180">`Test-Connection` использует WMI.</span><span class="sxs-lookup"><span data-stu-id="7a832-180">`Test-Connection` uses WMI.</span></span>
<span data-ttu-id="7a832-181">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="7a832-181">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="7a832-182">**Default** .</span><span class="sxs-lookup"><span data-stu-id="7a832-182">**Default** .</span></span> <span data-ttu-id="7a832-183">Проверка подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="7a832-183">Windows Authentication</span></span>
- <span data-ttu-id="7a832-184">**Нет** .</span><span class="sxs-lookup"><span data-stu-id="7a832-184">**None** .</span></span> <span data-ttu-id="7a832-185">Без проверки подлинности COM</span><span class="sxs-lookup"><span data-stu-id="7a832-185">No COM authentication</span></span>
- <span data-ttu-id="7a832-186">**Подключитесь** .</span><span class="sxs-lookup"><span data-stu-id="7a832-186">**Connect** .</span></span> <span data-ttu-id="7a832-187">Проверка подлинности COM на уровне подключения</span><span class="sxs-lookup"><span data-stu-id="7a832-187">Connect-level COM authentication</span></span>
- <span data-ttu-id="7a832-188">**Вызов метода** .</span><span class="sxs-lookup"><span data-stu-id="7a832-188">**Call** .</span></span> <span data-ttu-id="7a832-189">Проверка подлинности COM на уровне вызова</span><span class="sxs-lookup"><span data-stu-id="7a832-189">Call-level COM authentication</span></span>
- <span data-ttu-id="7a832-190">**Пакет** .</span><span class="sxs-lookup"><span data-stu-id="7a832-190">**Packet** .</span></span> <span data-ttu-id="7a832-191">Проверка подлинности COM на уровне пакета</span><span class="sxs-lookup"><span data-stu-id="7a832-191">Packet-level COM authentication</span></span>
- <span data-ttu-id="7a832-192">**Паккетинтегрити** .</span><span class="sxs-lookup"><span data-stu-id="7a832-192">**PacketIntegrity** .</span></span> <span data-ttu-id="7a832-193">Проверка подлинности COM на уровне целостности пакета</span><span class="sxs-lookup"><span data-stu-id="7a832-193">Packet Integrity-level COM authentication</span></span>
- <span data-ttu-id="7a832-194">**Паккетприваци** .</span><span class="sxs-lookup"><span data-stu-id="7a832-194">**PacketPrivacy** .</span></span> <span data-ttu-id="7a832-195">Проверка подлинности COM уровня конфиденциальности пакета</span><span class="sxs-lookup"><span data-stu-id="7a832-195">Packet Privacy-level COM authentication</span></span>
- <span data-ttu-id="7a832-196">**Без изменений** .</span><span class="sxs-lookup"><span data-stu-id="7a832-196">**Unchanged** .</span></span> <span data-ttu-id="7a832-197">То же, что и в предыдущей команде</span><span class="sxs-lookup"><span data-stu-id="7a832-197">Same as the previous command</span></span>

<span data-ttu-id="7a832-198">Значение по умолчанию — **Packet** с перечислимым значением **4** .</span><span class="sxs-lookup"><span data-stu-id="7a832-198">The default value is **Packet** that has an enumerated value of **4** .</span></span> <span data-ttu-id="7a832-199">Дополнительные сведения о значениях этого параметра см. в разделе [аусентикатионлевел](/dotnet/api/system.management.authenticationlevel) Enumeration.</span><span class="sxs-lookup"><span data-stu-id="7a832-199">For more information about the values of this parameter, see [AuthenticationLevel](/dotnet/api/system.management.authenticationlevel) enumeration.</span></span>

```yaml
Type: System.Management.AuthenticationLevel
Parameter Sets: (All)
Aliases: Authentication
Accepted values: Default, None, Connect, Call, Packet, PacketIntegrity, PacketPrivacy, Unchanged

Required: False
Position: Named
Default value: Packet (enumerated value of 4)
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7a832-200">-Delay</span><span class="sxs-lookup"><span data-stu-id="7a832-200">-Delay</span></span>

<span data-ttu-id="7a832-201">Задает интервал между проверками связи в секундах.</span><span class="sxs-lookup"><span data-stu-id="7a832-201">Specifies the interval between pings, in seconds.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 1 (second)
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7a832-202">— Олицетворение</span><span class="sxs-lookup"><span data-stu-id="7a832-202">-Impersonation</span></span>

<span data-ttu-id="7a832-203">Задает уровень олицетворения, используемый при вызове WMI этим командлетом.</span><span class="sxs-lookup"><span data-stu-id="7a832-203">Specifies the impersonation level to use when this cmdlet calls WMI.</span></span> <span data-ttu-id="7a832-204">`Test-Connection` использует WMI.</span><span class="sxs-lookup"><span data-stu-id="7a832-204">`Test-Connection` uses WMI.</span></span>

<span data-ttu-id="7a832-205">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="7a832-205">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="7a832-206">**Default** .</span><span class="sxs-lookup"><span data-stu-id="7a832-206">**Default** .</span></span> <span data-ttu-id="7a832-207">Олицетворение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7a832-207">Default impersonation.</span></span>
- <span data-ttu-id="7a832-208">**Анонимно** .</span><span class="sxs-lookup"><span data-stu-id="7a832-208">**Anonymous** .</span></span> <span data-ttu-id="7a832-209">скрывает удостоверение вызывающей стороны.</span><span class="sxs-lookup"><span data-stu-id="7a832-209">Hides the identity of the caller.</span></span>
- <span data-ttu-id="7a832-210">**Выявление** .</span><span class="sxs-lookup"><span data-stu-id="7a832-210">**Identify** .</span></span> <span data-ttu-id="7a832-211">позволяет объектам запрашивать учетные данные вызывающей стороны.</span><span class="sxs-lookup"><span data-stu-id="7a832-211">Allows objects to query the credentials of the caller.</span></span>
- <span data-ttu-id="7a832-212">**Олицетворять** .</span><span class="sxs-lookup"><span data-stu-id="7a832-212">**Impersonate** .</span></span> <span data-ttu-id="7a832-213">позволяет объектам использовать учетные данные вызывающей стороны.</span><span class="sxs-lookup"><span data-stu-id="7a832-213">Allows objects to use the credentials of the caller.</span></span>

<span data-ttu-id="7a832-214">Значение по умолчанию — **impersonate** .</span><span class="sxs-lookup"><span data-stu-id="7a832-214">The default value is **Impersonate** .</span></span>

```yaml
Type: System.Management.ImpersonationLevel
Parameter Sets: (All)
Aliases:
Accepted values: Default, Anonymous, Identify, Impersonate, Delegate

Required: False
Position: Named
Default value: Impersonate
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7a832-215">-Protocol</span><span class="sxs-lookup"><span data-stu-id="7a832-215">-Protocol</span></span>

<span data-ttu-id="7a832-216">Указывает протокол.</span><span class="sxs-lookup"><span data-stu-id="7a832-216">Specifies a protocol.</span></span> <span data-ttu-id="7a832-217">Допустимые значения для этого параметра: DCOM и WSMan.</span><span class="sxs-lookup"><span data-stu-id="7a832-217">The acceptable values for this parameter are DCOM and WSMan.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: DCOM, WSMan

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7a832-218">-Quiet</span><span class="sxs-lookup"><span data-stu-id="7a832-218">-Quiet</span></span>

<span data-ttu-id="7a832-219">Параметр **quiet** возвращает **логическое** значение в объекте **System. Boolean** .</span><span class="sxs-lookup"><span data-stu-id="7a832-219">The **Quiet** parameter returns a **Boolean** value in a **System.Boolean** object.</span></span> <span data-ttu-id="7a832-220">Использование этого параметра подавляет все ошибки.</span><span class="sxs-lookup"><span data-stu-id="7a832-220">Using this parameter suppresses all errors.</span></span>

<span data-ttu-id="7a832-221">Каждое проверенное соединение возвращает **логическое** значение.</span><span class="sxs-lookup"><span data-stu-id="7a832-221">Each connection that's tested returns a **Boolean** value.</span></span> <span data-ttu-id="7a832-222">Если параметр **ComputerName** задает несколько компьютеров, возвращается массив **логических** значений.</span><span class="sxs-lookup"><span data-stu-id="7a832-222">If the **ComputerName** parameter specifies multiple computers, an array of **Boolean** values is returned.</span></span>

<span data-ttu-id="7a832-223">Если **Проверка** связи выполнена успешно, `$True` возвращается значение.</span><span class="sxs-lookup"><span data-stu-id="7a832-223">If **any** ping succeeds, `$True` is returned.</span></span>

<span data-ttu-id="7a832-224">Если **все** проверки связи завершаются ошибкой, `$False` возвращается значение.</span><span class="sxs-lookup"><span data-stu-id="7a832-224">If **all** pings fail, `$False` is returned.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Quiet
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7a832-225">-Source</span><span class="sxs-lookup"><span data-stu-id="7a832-225">-Source</span></span>

<span data-ttu-id="7a832-226">Указывает имена компьютеров, на которых создается проверка связи.</span><span class="sxs-lookup"><span data-stu-id="7a832-226">Specifies the names of the computers where the ping originates.</span></span> <span data-ttu-id="7a832-227">Введите разделенный запятыми список имен компьютеров.</span><span class="sxs-lookup"><span data-stu-id="7a832-227">Enter a comma-separated list of computer names.</span></span> <span data-ttu-id="7a832-228">По умолчанию это локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="7a832-228">The default is the local computer.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Source
Aliases: FCN, SRC

Required: True
Position: 1
Default value: Local computer
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7a832-229">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="7a832-229">-ThrottleLimit</span></span>

<span data-ttu-id="7a832-230">Указывает максимальное число одновременных подключений, которые можно установить для запуска этой команды.</span><span class="sxs-lookup"><span data-stu-id="7a832-230">Specifies the maximum number of concurrent connections that can be established to run this command.</span></span>
<span data-ttu-id="7a832-231">Если этот параметр не указан или имеет значение 0, используется значение по умолчанию — 32.</span><span class="sxs-lookup"><span data-stu-id="7a832-231">If you omit this parameter or enter a value of 0, the default value, 32, is used.</span></span>

<span data-ttu-id="7a832-232">Предел регулирования применяется только к текущему командлету, а не к сеансу или компьютеру.</span><span class="sxs-lookup"><span data-stu-id="7a832-232">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Default, Source
Aliases:

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7a832-233">-TimeToLive</span><span class="sxs-lookup"><span data-stu-id="7a832-233">-TimeToLive</span></span>

<span data-ttu-id="7a832-234">Указывает максимальное время, в течение которого пакет может быть перенаправлен.</span><span class="sxs-lookup"><span data-stu-id="7a832-234">Specifies the maximum times a packet can be forwarded.</span></span> <span data-ttu-id="7a832-235">Для каждого прыжка в шлюзах, маршрутизаторов и т. д. значение **TimeToLive** уменьшается на единицу.</span><span class="sxs-lookup"><span data-stu-id="7a832-235">For every hop in gateways, routers etc. the **TimeToLive** value is decreased by one.</span></span> <span data-ttu-id="7a832-236">При нулевом пакете пакет отбрасывается и возвращается ошибка.</span><span class="sxs-lookup"><span data-stu-id="7a832-236">At zero the packet is discarded and an error is returned.</span></span>
<span data-ttu-id="7a832-237">В **Windows** значение по умолчанию — **128** .</span><span class="sxs-lookup"><span data-stu-id="7a832-237">In **Windows** , The default value is **128** .</span></span> <span data-ttu-id="7a832-238">Псевдоним параметра **TimeToLive** — **TTL** .</span><span class="sxs-lookup"><span data-stu-id="7a832-238">The alias of the **TimeToLive** parameter is **TTL** .</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: TTL

Required: False
Position: Named
Default value: 128 in Windows
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7a832-239">-Всманаусентикатион</span><span class="sxs-lookup"><span data-stu-id="7a832-239">-WsmanAuthentication</span></span>

<span data-ttu-id="7a832-240">Указывает механизм, используемый для проверки подлинности учетных данных пользователя, когда этот командлет использует протокол WSMan.</span><span class="sxs-lookup"><span data-stu-id="7a832-240">Specifies the mechanism that is used to authenticate the user credentials when this cmdlet uses the WSMan protocol.</span></span>
<span data-ttu-id="7a832-241">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="7a832-241">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="7a832-242">Базовый</span><span class="sxs-lookup"><span data-stu-id="7a832-242">Basic</span></span>
- <span data-ttu-id="7a832-243">CredSSP</span><span class="sxs-lookup"><span data-stu-id="7a832-243">CredSSP</span></span>
- <span data-ttu-id="7a832-244">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="7a832-244">Default</span></span>
- <span data-ttu-id="7a832-245">Digest (дайджест)</span><span class="sxs-lookup"><span data-stu-id="7a832-245">Digest</span></span>
- <span data-ttu-id="7a832-246">Kerberos</span><span class="sxs-lookup"><span data-stu-id="7a832-246">Kerberos</span></span>
- <span data-ttu-id="7a832-247">Negotiate —</span><span class="sxs-lookup"><span data-stu-id="7a832-247">Negotiate.</span></span>

<span data-ttu-id="7a832-248">Значение по умолчанию — Default.</span><span class="sxs-lookup"><span data-stu-id="7a832-248">The default value is Default.</span></span>

<span data-ttu-id="7a832-249">Дополнительные сведения о значениях этого параметра см. в разделе [AuthenticationMechanism enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism?view=powershellsdk-1.1.0).</span><span class="sxs-lookup"><span data-stu-id="7a832-249">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism?view=powershellsdk-1.1.0).</span></span>

<span data-ttu-id="7a832-250">Внимание! проверка подлинности с помощью поставщика службы безопасности учетных данных (CredSSP), в которой учетные данные пользователя передаются на удаленный компьютер для проверки подлинности, предназначена для команд, требующих проверки подлинности в нескольких ресурсах, например для доступа к удаленной сетевой папке.</span><span class="sxs-lookup"><span data-stu-id="7a832-250">Caution: Credential Security Service Provider (CredSSP) authentication, in which the user credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span>
<span data-ttu-id="7a832-251">Этот механизм повышает риск безопасности удаленной операции.</span><span class="sxs-lookup"><span data-stu-id="7a832-251">This mechanism increases the security risk of the remote operation.</span></span>
<span data-ttu-id="7a832-252">Если удаленный компьютер скомпрометирован, учетные данные, передаваемые ему, могут использоваться для управления сетевым сеансом.</span><span class="sxs-lookup"><span data-stu-id="7a832-252">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

<span data-ttu-id="7a832-253">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="7a832-253">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Default, Basic, Negotiate, CredSSP, Digest, Kerberos

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7a832-254">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="7a832-254">CommonParameters</span></span>

<span data-ttu-id="7a832-255">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7a832-255">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7a832-256">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="7a832-256">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7a832-257">Входные данные</span><span class="sxs-lookup"><span data-stu-id="7a832-257">INPUTS</span></span>

### <span data-ttu-id="7a832-258">Нет</span><span class="sxs-lookup"><span data-stu-id="7a832-258">None</span></span>

<span data-ttu-id="7a832-259">Вы не можете передать входные данные в этот командлет.</span><span class="sxs-lookup"><span data-stu-id="7a832-259">You can't pipe input to this cmdlet.</span></span>

## <span data-ttu-id="7a832-260">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="7a832-260">OUTPUTS</span></span>

### <span data-ttu-id="7a832-261">System. Management. ManagementObject # root\cimv2\ Win32_PingStatus, System. Management. Automation. Ремотингжоб, System. Boolean</span><span class="sxs-lookup"><span data-stu-id="7a832-261">System.Management.ManagementObject#root\cimv2\Win32_PingStatus, System.Management.Automation.RemotingJob, System.Boolean</span></span>

<span data-ttu-id="7a832-262">Этот командлет возвращает объект задания, если указан параметр **AsJob** .</span><span class="sxs-lookup"><span data-stu-id="7a832-262">This cmdlet returns a job object, if you specify the **AsJob** parameter.</span></span>

<span data-ttu-id="7a832-263">При указании параметра **quiet** возвращается **логическое** значение.</span><span class="sxs-lookup"><span data-stu-id="7a832-263">If you specify the **Quiet** parameter, it returns a **Boolean** value.</span></span> <span data-ttu-id="7a832-264">Если тестируется несколько подключений, возвращается массив **логических** значений.</span><span class="sxs-lookup"><span data-stu-id="7a832-264">If multiple connections are tested, an array of **Boolean** values is returned.</span></span> <span data-ttu-id="7a832-265">В противном случае `Test-Connection` возвращает объект **Win32_PingStatus** для каждой проверки связи.</span><span class="sxs-lookup"><span data-stu-id="7a832-265">Otherwise, `Test-Connection` returns a **Win32_PingStatus** object for each ping.</span></span>

## <span data-ttu-id="7a832-266">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="7a832-266">NOTES</span></span>

<span data-ttu-id="7a832-267">Этот командлет использует класс **Win32_PingStatus** .</span><span class="sxs-lookup"><span data-stu-id="7a832-267">This cmdlet uses the **Win32_PingStatus** class.</span></span> <span data-ttu-id="7a832-268">`Get-WMIObject Win32_PingStatus`Команда эквивалентна `Test-Connection` команде.</span><span class="sxs-lookup"><span data-stu-id="7a832-268">A `Get-WMIObject Win32_PingStatus` command is equivalent to a `Test-Connection` command.</span></span>

<span data-ttu-id="7a832-269">Набор **исходных** параметров был представлен в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="7a832-269">The **Source** parameter set was introduced in PowerShell 3.0.</span></span>

## <span data-ttu-id="7a832-270">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="7a832-270">RELATED LINKS</span></span>

[<span data-ttu-id="7a832-271">Add-Computer</span><span class="sxs-lookup"><span data-stu-id="7a832-271">Add-Computer</span></span>](Add-Computer.md)

[<span data-ttu-id="7a832-272">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="7a832-272">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="7a832-273">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="7a832-273">Stop-Computer</span></span>](Stop-Computer.md)
