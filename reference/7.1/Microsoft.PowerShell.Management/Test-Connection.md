---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/test-connection?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-Connection
ms.openlocfilehash: 6a03d5a644e3d4be515a93a702d0ef0aff23a8d7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226758"
---
# <span data-ttu-id="e423b-103">Test-Connection</span><span class="sxs-lookup"><span data-stu-id="e423b-103">Test-Connection</span></span>

## <span data-ttu-id="e423b-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="e423b-104">SYNOPSIS</span></span>
<span data-ttu-id="e423b-105">Отправляет пакеты запроса проверки связи ICMP или проверки связи на один или несколько компьютеров.</span><span class="sxs-lookup"><span data-stu-id="e423b-105">Sends ICMP echo request packets, or pings, to one or more computers.</span></span>

## <span data-ttu-id="e423b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e423b-106">SYNTAX</span></span>

### <span data-ttu-id="e423b-107">Дефаултпинг (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="e423b-107">DefaultPing (Default)</span></span>

```
Test-Connection [-TargetName] <string[]> [-Ping] [-IPv4] [-IPv6] [-ResolveDestination]
 [-Source <string>] [-MaxHops <int>] [-Count <int>] [-Delay <int>] [-BufferSize <int>]
 [-DontFragment] [-TimeoutSeconds <int>] [-Quiet] [<CommonParameters>]
```

### <span data-ttu-id="e423b-108">репеатпинг</span><span class="sxs-lookup"><span data-stu-id="e423b-108">RepeatPing</span></span>

```
Test-Connection [-TargetName] <string[]> -Repeat [-Ping] [-IPv4] [-IPv6] [-ResolveDestination]
 [-Source <string>] [-MaxHops <int>] [-Delay <int>] [-BufferSize <int>] [-DontFragment]
 [-TimeoutSeconds <int>] [-Quiet] [<CommonParameters>]
```

### <span data-ttu-id="e423b-109">мтусизедетект</span><span class="sxs-lookup"><span data-stu-id="e423b-109">MtuSizeDetect</span></span>

```
Test-Connection [-TargetName] <string[]> -MtuSize [-IPv4] [-IPv6] [-ResolveDestination]
 [-TimeoutSeconds <int>] [-Quiet] [<CommonParameters>]
```

### <span data-ttu-id="e423b-110">TraceRoute</span><span class="sxs-lookup"><span data-stu-id="e423b-110">TraceRoute</span></span>

```
Test-Connection [-TargetName] <string[]> -Traceroute [-IPv4] [-IPv6] [-ResolveDestination]
 [-Source <string>] [-MaxHops <int>] [-TimeoutSeconds <int>] [-Quiet] [<CommonParameters>]
```

### <span data-ttu-id="e423b-111">TcpPort</span><span class="sxs-lookup"><span data-stu-id="e423b-111">TcpPort</span></span>

```
Test-Connection [-TargetName] <string[]> -TcpPort <int> [-IPv4] [-IPv6] [-ResolveDestination]
 [-Source <string>] [-TimeoutSeconds <int>] [-Quiet] [<CommonParameters>]
```

## <span data-ttu-id="e423b-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e423b-112">DESCRIPTION</span></span>

<span data-ttu-id="e423b-113">`Test-Connection`Командлет отправляет пакеты эхо-запросов протокола ICMP (ping) на один или несколько удаленных компьютеров и возвращает ответ на эхо-ответы.</span><span class="sxs-lookup"><span data-stu-id="e423b-113">The `Test-Connection` cmdlet sends Internet Control Message Protocol (ICMP) echo request packets, or pings, to one or more remote computers and returns the echo response replies.</span></span> <span data-ttu-id="e423b-114">С помощью этого командлета можно определить, можно ли связаться с определенным компьютером по IP-сети.</span><span class="sxs-lookup"><span data-stu-id="e423b-114">You can use this cmdlet to determine whether a particular computer can be contacted across an IP network.</span></span>

<span data-ttu-id="e423b-115">С помощью параметров можно `Test-Connection` указать как отправляющее, так и принимающее компьютеры, чтобы выполнить команду в качестве фонового задания, установить время ожидания и количество проверок связи, а также настроить подключение и проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="e423b-115">You can use the parameters of `Test-Connection` to specify both the sending and receiving computers, to run the command as a background job, to set a time-out and number of pings, and to configure the connection and authentication.</span></span>

<span data-ttu-id="e423b-116">В отличие от знакомой команды **ping** , `Test-Connection` возвращает объект **тестконнектионкомманд + пингстатус** , который можно исследовать в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e423b-116">Unlike the familiar **ping** command, `Test-Connection` returns a **TestConnectionCommand+PingStatus** object that you can investigate in PowerShell.</span></span> <span data-ttu-id="e423b-117">Параметр **quiet** возвращает **логическое** значение в объекте **System. Boolean** для каждого проверенного подключения.</span><span class="sxs-lookup"><span data-stu-id="e423b-117">The **Quiet** parameter returns a **Boolean** value in a **System.Boolean** object for each tested connection.</span></span> <span data-ttu-id="e423b-118">Если тестируется несколько подключений, возвращается массив **логических** значений.</span><span class="sxs-lookup"><span data-stu-id="e423b-118">If multiple connections are tested, an array of **Boolean** values is returned.</span></span>

## <span data-ttu-id="e423b-119">Примеры</span><span class="sxs-lookup"><span data-stu-id="e423b-119">EXAMPLES</span></span>

### <span data-ttu-id="e423b-120">Пример 1. Отправка эхо-запросов на удаленный компьютер</span><span class="sxs-lookup"><span data-stu-id="e423b-120">Example 1: Send echo requests to a remote computer</span></span>

<span data-ttu-id="e423b-121">Этот пример отправляет пакеты эхо-запросов с локального компьютера на компьютер Server01.</span><span class="sxs-lookup"><span data-stu-id="e423b-121">This example sends echo request packets from the local computer to the Server01 computer.</span></span>

```powershell
Test-Connection -TargetName Server01 -IPv4
```

```Output
   Destination: Server01

Ping Source           Address                   Latency BufferSize Status
                                                   (ms)        (B)
---- ------           -------                   ------- ---------- ------
   1 ADMIN1           10.59.137.44                   24         32 Success
   2 ADMIN1           10.59.137.44                   39         32 Success
   3 ADMIN1           *                               *          * TimedOut
   4 ADMIN1           10.59.137.44                   28         32 Success
```

<span data-ttu-id="e423b-122">`Test-Connection` использует параметр **TargetName** для указания компьютера Server01.</span><span class="sxs-lookup"><span data-stu-id="e423b-122">`Test-Connection` uses the **TargetName** parameter to specify the Server01 computer.</span></span> <span data-ttu-id="e423b-123">Параметр **IPv4** указывает протокол для теста.</span><span class="sxs-lookup"><span data-stu-id="e423b-123">The **IPv4** parameter specifies the protocol for the test.</span></span>

<span data-ttu-id="e423b-124">Ряд объектов **тестконнектионкомманд + пингстатус** отправляется в поток вывода, по одному объекту на ответ проверки связи от целевого компьютера.</span><span class="sxs-lookup"><span data-stu-id="e423b-124">A series of **TestConnectionCommand+PingStatus** objects are sent to the output stream, one object per ping reply from the target machine.</span></span>

### <span data-ttu-id="e423b-125">Пример 2. Отправка эхо-запросов на несколько компьютеров</span><span class="sxs-lookup"><span data-stu-id="e423b-125">Example 2: Send echo requests to several computers</span></span>

<span data-ttu-id="e423b-126">Этот пример отправляет команды ping с локального компьютера на несколько удаленных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="e423b-126">This example sends pings from the local computer to several remote computers.</span></span>

```powershell
Test-Connection -TargetName Server01, Server02, Server12
```

### <span data-ttu-id="e423b-127">Пример 3. Использование параметров для настройки команды теста</span><span class="sxs-lookup"><span data-stu-id="e423b-127">Example 3: Use parameters to customize the test command</span></span>

<span data-ttu-id="e423b-128">В этом примере `Test-Connection` для настройки команды используются параметры.</span><span class="sxs-lookup"><span data-stu-id="e423b-128">This example uses the parameters of `Test-Connection` to customize the command.</span></span> <span data-ttu-id="e423b-129">Локальный компьютер отправляет тест проверки связи на удаленный компьютер.</span><span class="sxs-lookup"><span data-stu-id="e423b-129">The local computer sends a ping test to a remote computer.</span></span>

```powershell
Test-Connection -TargetName Server01 -Count 3 -Delay 2 -MaxHops 255 -BufferSize 256
```

<span data-ttu-id="e423b-130">`Test-Connection` использует параметр **TargetName** для указания Server01.</span><span class="sxs-lookup"><span data-stu-id="e423b-130">`Test-Connection` uses the **TargetName** parameter to specify Server01.</span></span> <span data-ttu-id="e423b-131">Параметр **Count** указывает три сообщения проверки связи, отправляемые на компьютер Server01 с **задержкой** в 2 секунды.</span><span class="sxs-lookup"><span data-stu-id="e423b-131">The **Count** parameter specifies three pings are sent to the Server01 computer with a **Delay** of 2-second intervals.</span></span>

<span data-ttu-id="e423b-132">Эти параметры можно использовать, если ожидается, что ответ на запрос проверки связи займет больше времени, чем обычно, из-за расширенного числа прыжков или состояния сети с высоким трафиком.</span><span class="sxs-lookup"><span data-stu-id="e423b-132">You might use these options when the ping response is expected to take longer than usual, either because of an extended number of hops or a high-traffic network condition.</span></span>

### <span data-ttu-id="e423b-133">Пример 4. Запуск теста в качестве фонового задания</span><span class="sxs-lookup"><span data-stu-id="e423b-133">Example 4: Run a test as a background job</span></span>

<span data-ttu-id="e423b-134">В этом примере показано, как выполнить `Test-Connection` команду в качестве фонового задания PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e423b-134">This example shows how to run a `Test-Connection` command as a PowerShell background job.</span></span>

```powershell
$job = Start-Job -ScriptBlock { Test-Connection -TargetName (Get-Content -Path "Servers.txt") }
$Results = Receive-Job $job -Wait
```

<span data-ttu-id="e423b-135">`Start-Job`Команда использует `Test-Connection` командлет для проверки связи между многими компьютерами предприятия.</span><span class="sxs-lookup"><span data-stu-id="e423b-135">The `Start-Job` command uses the `Test-Connection` cmdlet to ping many computers in an enterprise.</span></span>
<span data-ttu-id="e423b-136">Значение параметра **TargetName** — это `Get-Content` команда, которая считывает список имен компьютеров из `Servers.txt` файла.</span><span class="sxs-lookup"><span data-stu-id="e423b-136">The value of the **TargetName** parameter is a `Get-Content` command that reads a list of computer names from the `Servers.txt` file.</span></span> <span data-ttu-id="e423b-137">Команда использует `Start-Job` командлет для выполнения команды в качестве фонового задания и сохраняет задание в `$job` переменной.</span><span class="sxs-lookup"><span data-stu-id="e423b-137">The command uses the `Start-Job` cmdlet to run the command as a background job and it saves the job in the `$job` variable.</span></span>

<span data-ttu-id="e423b-138">`Receive-Job`Команда будет давать инструкции `-Wait` до тех пор, пока задание не будет завершено, а затем не получит результаты и сохранит их в `$Results` переменной.</span><span class="sxs-lookup"><span data-stu-id="e423b-138">The `Receive-Job` command is instructed to `-Wait` until the job is completed, and then gets the results and stores them in the `$Results` variable.</span></span>

### <span data-ttu-id="e423b-139">Пример 5. Создание сеанса только в случае успешности проверки соединения</span><span class="sxs-lookup"><span data-stu-id="e423b-139">Example 5: Create a session only if a connection test succeeds</span></span>

<span data-ttu-id="e423b-140">Этот пример создает сеанс на компьютере Server01, только если по крайней мере один из пакетов проверки связи успешно отправлен на компьютер.</span><span class="sxs-lookup"><span data-stu-id="e423b-140">This example creates a session on the Server01 computer only if at least one of the pings sent to the computer succeeds.</span></span>

```powershell
if (Test-Connection -TargetName Server01 -Quiet) { New-PSSession -ComputerName Server01 }
```

<span data-ttu-id="e423b-141">`Test-Connection`Командлет проверяет связь `Server01` с компьютером с указанным параметром **quiet** .</span><span class="sxs-lookup"><span data-stu-id="e423b-141">The `Test-Connection` cmdlet pings the `Server01` computer, with the **Quiet** parameter provided.</span></span>
<span data-ttu-id="e423b-142">Полученное значение — `$True` при успешном выполнении любой из четырех проверок связи.</span><span class="sxs-lookup"><span data-stu-id="e423b-142">The resulting value is `$True` if any of the four pings succeed.</span></span> <span data-ttu-id="e423b-143">Если ни одна из проверок связи не выполнена успешно, значение равно `$False` .</span><span class="sxs-lookup"><span data-stu-id="e423b-143">If none of the pings succeed, the value is `$False`.</span></span>

<span data-ttu-id="e423b-144">Если `Test-Connection` команда возвращает значение `$True` , команда использует `New-PSSession` командлет для создания **сеанса PSSession**.</span><span class="sxs-lookup"><span data-stu-id="e423b-144">If the `Test-Connection` command returns a value of `$True`, the command uses the `New-PSSession` cmdlet to create the **PSSession**.</span></span>

### <span data-ttu-id="e423b-145">Пример 6. Использование параметра Traceroute</span><span class="sxs-lookup"><span data-stu-id="e423b-145">Example 6: Use the Traceroute parameter</span></span>

<span data-ttu-id="e423b-146">Параметр **Traceroute** , введенный в PowerShell 6,0, сопоставляет маршрут между локальным компьютером и удаленным назначением, указанным с помощью параметра **TargetName** .</span><span class="sxs-lookup"><span data-stu-id="e423b-146">Introduced in PowerShell 6.0, the **Traceroute** parameter maps a route between the local computer and the remote destination you specify with the **TargetName** parameter.</span></span>

```powershell
Test-Connection -TargetName www.google.com -Traceroute
```

```Output
   Target: google.com

Hop Hostname                  Ping Latency Status           Source       TargetAddress
                                      (ms)
--- --------                  ---- ------- ------           ------       -------------
  1 172.20.0.1                   1       4 Success          Lira         172.217.9.174
  1 172.20.0.1                   2       3 Success          Lira         172.217.9.174
  1 172.20.0.1                   3       2 Success          Lira         172.217.9.174
  2 12.108.153.193               1       3 Success          Lira         172.217.9.174
  2 12.108.153.193               2       3 Success          Lira         172.217.9.174
  2 12.108.153.193               3       2 Success          Lira         172.217.9.174
  3 12.244.85.177                1      11 Success          Lira         172.217.9.174
  3 12.244.85.177                2      12 Success          Lira         172.217.9.174
  3 12.244.85.177                3      12 Success          Lira         172.217.9.174
  4 *                            1      14 DestinationNetw… Lira         172.217.9.174
  4 *                            2       * TimedOut         Lira         172.217.9.174
  4 *                            3      20 DestinationNetw… Lira         172.217.9.174
  5 *                            1       * TimedOut         Lira         172.217.9.174
  5 *                            2      15 DestinationNetw… Lira         172.217.9.174
  5 *                            3       * TimedOut         Lira         172.217.9.174
  6 *                            1      18 DestinationNetw… Lira         172.217.9.174
  6 *                            2       * TimedOut         Lira         172.217.9.174
  6 *                            3      16 DestinationNetw… Lira         172.217.9.174
  7 *                            1       * TimedOut         Lira         172.217.9.174
  7 *                            2       * TimedOut         Lira         172.217.9.174
  7 *                            3       * TimedOut         Lira         172.217.9.174
  8 *                            1       * TimedOut         Lira         172.217.9.174
  8 *                            2       * TimedOut         Lira         172.217.9.174
  8 *                            3       * TimedOut         Lira         172.217.9.174
  9 *                            1       * TimedOut         Lira         172.217.9.174
  9 *                            2       * TimedOut         Lira         172.217.9.174
  9 *                            3       * TimedOut         Lira         172.217.9.174
 10 *                            1       * TimedOut         Lira         172.217.9.174
 10 *                            2       * TimedOut         Lira         172.217.9.174
 10 *                            3       * TimedOut         Lira         172.217.9.174
 11 172.217.9.174                1      23 Success          Lira         172.217.9.174
 11 172.217.9.174                2      21 Success          Lira         172.217.9.174
 11 172.217.9.174                3      22 Success          Lira         172.217.9.174
```

<span data-ttu-id="e423b-147">`Test-Connection`Команда вызывается с параметром **Traceroute** .</span><span class="sxs-lookup"><span data-stu-id="e423b-147">The `Test-Connection` command is called with the **Traceroute** parameter.</span></span> <span data-ttu-id="e423b-148">Результаты, являющиеся объектами, выводятся в `[Microsoft.PowerShell.Commands.TestConnectionCommand+TraceStatus]` поток выходных данных **успешного** выполнения.</span><span class="sxs-lookup"><span data-stu-id="e423b-148">The results, which are `[Microsoft.PowerShell.Commands.TestConnectionCommand+TraceStatus]` objects, are output to the **Success** output stream.</span></span>

## <span data-ttu-id="e423b-149">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e423b-149">PARAMETERS</span></span>

### <span data-ttu-id="e423b-150">— BufferSize</span><span class="sxs-lookup"><span data-stu-id="e423b-150">-BufferSize</span></span>

<span data-ttu-id="e423b-151">Указывает размер (в байтах) буфера, отправленного с помощью этой команды.</span><span class="sxs-lookup"><span data-stu-id="e423b-151">Specifies the size, in bytes, of the buffer sent with this command.</span></span> <span data-ttu-id="e423b-152">Значение по умолчанию: 32.</span><span class="sxs-lookup"><span data-stu-id="e423b-152">The default value is 32.</span></span>

```yaml
Type: System.Int32
Parameter Sets: DefaultPing, RepeatPing
Aliases: Size, Bytes, BS

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e423b-153">Повтор</span><span class="sxs-lookup"><span data-stu-id="e423b-153">-Repeat</span></span>

<span data-ttu-id="e423b-154">Указывает, что командлет будет постоянно отсылать запросы проверки связи.</span><span class="sxs-lookup"><span data-stu-id="e423b-154">Causes the cmdlet to send ping requests continuously.</span></span> <span data-ttu-id="e423b-155">Этот параметр нельзя использовать с параметром **Count** .</span><span class="sxs-lookup"><span data-stu-id="e423b-155">This parameter can't be used with the **Count** parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: RepeatPing
Aliases: Continuous

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e423b-156">— Количество</span><span class="sxs-lookup"><span data-stu-id="e423b-156">-Count</span></span>

<span data-ttu-id="e423b-157">Указывает число отправляемых запросов проверки связи.</span><span class="sxs-lookup"><span data-stu-id="e423b-157">Specifies the number of echo requests to send.</span></span> <span data-ttu-id="e423b-158">Значение по умолчанию — 4.</span><span class="sxs-lookup"><span data-stu-id="e423b-158">The default value is 4.</span></span>

```yaml
Type: System.Int32
Parameter Sets: DefaultPing
Aliases:

Required: False
Position: Named
Default value: 4
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e423b-159">-Delay</span><span class="sxs-lookup"><span data-stu-id="e423b-159">-Delay</span></span>

<span data-ttu-id="e423b-160">Задает интервал между проверками связи в секундах.</span><span class="sxs-lookup"><span data-stu-id="e423b-160">Specifies the interval between pings, in seconds.</span></span>

```yaml
Type: System.Int32
Parameter Sets: DefaultPing, RepeatPing
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e423b-161">-Донтфрагмент</span><span class="sxs-lookup"><span data-stu-id="e423b-161">-DontFragment</span></span>

<span data-ttu-id="e423b-162">Этот параметр задает флаг « **не фрагментировать** » в заголовке IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="e423b-162">This parameter sets the **Don't Fragment** flag in the IP header.</span></span> <span data-ttu-id="e423b-163">Этот параметр можно использовать с параметром **bufferSize** для проверки размера MTU пути.</span><span class="sxs-lookup"><span data-stu-id="e423b-163">You can use this parameter with the **BufferSize** parameter to test the Path MTU size.</span></span> <span data-ttu-id="e423b-164">Дополнительные сведения о пути MTU см. в статье о [поиске пути MTU](https://wikipedia.org/wiki/Path_MTU_Discovery) в Википедии.</span><span class="sxs-lookup"><span data-stu-id="e423b-164">For more information about Path MTU, see the [Path MTU Discovery](https://wikipedia.org/wiki/Path_MTU_Discovery) article in wikipedia.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DefaultPing, RepeatPing
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e423b-165">— IPv4</span><span class="sxs-lookup"><span data-stu-id="e423b-165">-IPv4</span></span>

<span data-ttu-id="e423b-166">Заставляет командлет использовать протокол IPv4 для теста.</span><span class="sxs-lookup"><span data-stu-id="e423b-166">Forces the cmdlet to use the IPv4 protocol for the test.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e423b-167">— IPv6</span><span class="sxs-lookup"><span data-stu-id="e423b-167">-IPv6</span></span>

<span data-ttu-id="e423b-168">Заставляет командлет использовать протокол IPv6 для теста.</span><span class="sxs-lookup"><span data-stu-id="e423b-168">Forces the cmdlet to use the IPv6 protocol for the test.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e423b-169">-Максхопс</span><span class="sxs-lookup"><span data-stu-id="e423b-169">-MaxHops</span></span>

<span data-ttu-id="e423b-170">Задает максимальное число прыжков, на которое может быть отправлено сообщение с запросом ICMP.</span><span class="sxs-lookup"><span data-stu-id="e423b-170">Sets the maximum number of hops that an ICMP request message can be sent.</span></span> <span data-ttu-id="e423b-171">Значение по умолчанию управляется операционной системой.</span><span class="sxs-lookup"><span data-stu-id="e423b-171">The default value is controlled by the operating system.</span></span> <span data-ttu-id="e423b-172">Значение по умолчанию для Windows 10 — 128 прыжков.</span><span class="sxs-lookup"><span data-stu-id="e423b-172">The default value for Windows 10 is 128 hops.</span></span>

```yaml
Type: System.Int32
Parameter Sets: DefaultPing, RepeatPing, TraceRoute
Aliases: Ttl, TimeToLive, Hops

Required: False
Position: Named
Default value: 128 hops in Windows 10
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e423b-173">— Проверка связи</span><span class="sxs-lookup"><span data-stu-id="e423b-173">-Ping</span></span>

<span data-ttu-id="e423b-174">Вызывает выполнение командлетом проверки связи.</span><span class="sxs-lookup"><span data-stu-id="e423b-174">Causes the cmdlet to do a ping test.</span></span> <span data-ttu-id="e423b-175">Это режим по умолчанию для `Test-Connection` командлета.</span><span class="sxs-lookup"><span data-stu-id="e423b-175">This is the default mode for the `Test-Connection` cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DefaultPing, RepeatPing
Aliases:

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e423b-176">-Quiet</span><span class="sxs-lookup"><span data-stu-id="e423b-176">-Quiet</span></span>

<span data-ttu-id="e423b-177">Параметр **quiet** возвращает **логическое** значение.</span><span class="sxs-lookup"><span data-stu-id="e423b-177">The **Quiet** parameter returns a **Boolean** value.</span></span> <span data-ttu-id="e423b-178">Использование этого параметра подавляет все ошибки.</span><span class="sxs-lookup"><span data-stu-id="e423b-178">Using this parameter suppresses all errors.</span></span>

<span data-ttu-id="e423b-179">Каждое проверенное соединение возвращает **логическое** значение.</span><span class="sxs-lookup"><span data-stu-id="e423b-179">Each connection that's tested returns a **Boolean** value.</span></span> <span data-ttu-id="e423b-180">Если параметр **TargetName** задает несколько компьютеров, возвращается массив **логических** значений.</span><span class="sxs-lookup"><span data-stu-id="e423b-180">If the **TargetName** parameter specifies multiple computers, an array of **Boolean** values is returned.</span></span>

<span data-ttu-id="e423b-181">Если **Проверка** связи с указанным целевым объектом будет выполнена успешно, `$True` возвращается значение.</span><span class="sxs-lookup"><span data-stu-id="e423b-181">If **any** ping to a given target succeeds, `$True` is returned.</span></span>

<span data-ttu-id="e423b-182">Если **все** команды ping для данного целевого объекта завершаются ошибкой, `$False` возвращается значение.</span><span class="sxs-lookup"><span data-stu-id="e423b-182">If **all** pings to a given target fail, `$False` is returned.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e423b-183">-Ресолведестинатион</span><span class="sxs-lookup"><span data-stu-id="e423b-183">-ResolveDestination</span></span>

<span data-ttu-id="e423b-184">Вызывает попытку командлета разрешить DNS-имя целевого объекта.</span><span class="sxs-lookup"><span data-stu-id="e423b-184">Causes the cmdlet to attempt to resolve the DNS name of the target.</span></span> <span data-ttu-id="e423b-185">При использовании в сочетании с параметром **Traceroute** имена DNS всех промежуточных узлов также будут извлекаться, если это возможно.</span><span class="sxs-lookup"><span data-stu-id="e423b-185">When used in conjunction with the **Traceroute** parameter, the DNS names of all intermediate hosts will also be retrieved, if possible.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e423b-186">-Source</span><span class="sxs-lookup"><span data-stu-id="e423b-186">-Source</span></span>

<span data-ttu-id="e423b-187">Указывает имена компьютеров, на которых создается проверка связи.</span><span class="sxs-lookup"><span data-stu-id="e423b-187">Specifies the names of the computers where the ping originates.</span></span> <span data-ttu-id="e423b-188">Введите разделенный запятыми список имен компьютеров.</span><span class="sxs-lookup"><span data-stu-id="e423b-188">Enter a comma-separated list of computer names.</span></span> <span data-ttu-id="e423b-189">По умолчанию это локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="e423b-189">The default is the local computer.</span></span>

<span data-ttu-id="e423b-190">**Примечание.** Этот параметр не работает в PowerShell версии 6 и выше.</span><span class="sxs-lookup"><span data-stu-id="e423b-190">**NOTE:** This parameter is not functional in PowerShell versions 6 and up.</span></span>
<span data-ttu-id="e423b-191">Предоставление этого параметра не будет влиять на выполнение команды.</span><span class="sxs-lookup"><span data-stu-id="e423b-191">Supplying this parameter will have no effect on the command.</span></span>

```yaml
Type: System.String
Parameter Sets: DefaultPing, RepeatPing, TraceRoute, TcpPort
Aliases:

Required: False
Position: Named
Default value: Local computer
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e423b-192">-TargetName</span><span class="sxs-lookup"><span data-stu-id="e423b-192">-TargetName</span></span>

<span data-ttu-id="e423b-193">Указывает компьютеры для проверки.</span><span class="sxs-lookup"><span data-stu-id="e423b-193">Specifies the computer(s) to test.</span></span> <span data-ttu-id="e423b-194">Введите имена компьютеров или IP-адреса в формате IPv4 или IPv6.</span><span class="sxs-lookup"><span data-stu-id="e423b-194">Type the computer names or type IP addresses in IPv4 or IPv6 format.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: ComputerName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="e423b-195">-TimeoutSeconds</span><span class="sxs-lookup"><span data-stu-id="e423b-195">-TimeoutSeconds</span></span>

<span data-ttu-id="e423b-196">Задает значение времени ожидания для теста.</span><span class="sxs-lookup"><span data-stu-id="e423b-196">Sets the timeout value for the test.</span></span> <span data-ttu-id="e423b-197">Тест завершается ошибкой, если не получен ответ до истечения времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="e423b-197">The test fails if a response isn't received before the timeout expires.</span></span> <span data-ttu-id="e423b-198">Значение по умолчанию — пять секунд.</span><span class="sxs-lookup"><span data-stu-id="e423b-198">The default is five seconds.</span></span>

<span data-ttu-id="e423b-199">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="e423b-199">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 5 seconds
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e423b-200">-Traceroute</span><span class="sxs-lookup"><span data-stu-id="e423b-200">-Traceroute</span></span>

<span data-ttu-id="e423b-201">Вызывает выполнение командлетом Traceroute теста.</span><span class="sxs-lookup"><span data-stu-id="e423b-201">Causes the cmdlet to do a traceroute test.</span></span> <span data-ttu-id="e423b-202">При использовании этого параметра командлет возвращает `TestConnectionCommand+TraceStatus` объект.</span><span class="sxs-lookup"><span data-stu-id="e423b-202">When this parameter is used, the cmdlet returns a `TestConnectionCommand+TraceStatus` object.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TraceRoute
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e423b-203">-Мтусизе</span><span class="sxs-lookup"><span data-stu-id="e423b-203">-MtuSize</span></span>

<span data-ttu-id="e423b-204">Этот параметр используется для определения размера MTU пути.</span><span class="sxs-lookup"><span data-stu-id="e423b-204">This parameter is used to discover the Path MTU size.</span></span> <span data-ttu-id="e423b-205">Командлет возвращает объект **пингрепли # мтусизе** , который содержит размер MTU для пути к целевому объекту.</span><span class="sxs-lookup"><span data-stu-id="e423b-205">The cmdlet returns a **PingReply#MTUSize** object that contains the Path MTU size to the target.</span></span> <span data-ttu-id="e423b-206">Дополнительные сведения о пути MTU см. в статье о [поиске пути MTU](https://wikipedia.org/wiki/Path_MTU_Discovery) в Википедии.</span><span class="sxs-lookup"><span data-stu-id="e423b-206">For more information about Path MTU, see the [Path MTU Discovery](https://wikipedia.org/wiki/Path_MTU_Discovery) article in wikipedia.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: MtuSizeDetect
Aliases: MtuSizeDetect

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e423b-207">-TcpPort</span><span class="sxs-lookup"><span data-stu-id="e423b-207">-TcpPort</span></span>

<span data-ttu-id="e423b-208">Указывает номер порта TCP на целевом объекте, который будет использоваться при проверке подключения TCP.</span><span class="sxs-lookup"><span data-stu-id="e423b-208">Specifies the TCP port number on the target to be used in the TCP connection test.</span></span> <span data-ttu-id="e423b-209">Командлет попытается установить TCP-подключение к указанному порту на целевом объекте.</span><span class="sxs-lookup"><span data-stu-id="e423b-209">The cmdlet will attempt to make a TCP connection to the specified port on the target.</span></span>

<span data-ttu-id="e423b-210">Если соединение может быть установлено, `$True` будет возвращено.</span><span class="sxs-lookup"><span data-stu-id="e423b-210">If a connection can be made, `$True` will be returned.</span></span>

<span data-ttu-id="e423b-211">Если соединение не может быть установлено, `$False` будет возвращено значение.</span><span class="sxs-lookup"><span data-stu-id="e423b-211">If a connection cannot be made, `$False` will be returned.</span></span>

```yaml
Type: System.Int32
Parameter Sets: TcpPort
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e423b-212">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="e423b-212">CommonParameters</span></span>

<span data-ttu-id="e423b-213">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e423b-213">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e423b-214">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e423b-214">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e423b-215">Входные данные</span><span class="sxs-lookup"><span data-stu-id="e423b-215">INPUTS</span></span>

### <span data-ttu-id="e423b-216">Нет</span><span class="sxs-lookup"><span data-stu-id="e423b-216">None</span></span>

<span data-ttu-id="e423b-217">Вы не можете передать входные данные в этот командлет.</span><span class="sxs-lookup"><span data-stu-id="e423b-217">You can't pipe input to this cmdlet.</span></span>

## <span data-ttu-id="e423b-218">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="e423b-218">OUTPUTS</span></span>

### <span data-ttu-id="e423b-219">Тестконнектионкомманд + Пингстатус, Тестконнектионкомманд + TraceStatus, Boolean, Тестконнектионкомманд + Пингмтустатус</span><span class="sxs-lookup"><span data-stu-id="e423b-219">TestConnectionCommand+PingStatus, TestConnectionCommand+TraceStatus, Boolean, TestConnectionCommand+PingMtuStatus</span></span>

<span data-ttu-id="e423b-220">По умолчанию `Test-Connection` возвращает объект **Тестконнектионкомманд + пингстатус** для каждого ответа проверки связи.</span><span class="sxs-lookup"><span data-stu-id="e423b-220">By default, `Test-Connection` returns a **TestConnectionCommand+PingStatus** object for each ping reply.</span></span>

<span data-ttu-id="e423b-221">Если указать параметр **Traceroute** , командлет вернет объект **тестконнектионкомманд + TraceStatus** для каждого ответа на маршрут.</span><span class="sxs-lookup"><span data-stu-id="e423b-221">If you specify the **Traceroute** parameter, the cmdlet will return a **TestConnectionCommand+TraceStatus** object for each ping reply along the route.</span></span>

<span data-ttu-id="e423b-222">Если заданы параметры **quiet** или **TcpPort** , то возвращается **логическое** значение.</span><span class="sxs-lookup"><span data-stu-id="e423b-222">If you specify the **Quiet** or **TcpPort** parameters, it returns a **Boolean** value.</span></span> <span data-ttu-id="e423b-223">Если тестируется несколько подключений, возвращается массив **логических** значений.</span><span class="sxs-lookup"><span data-stu-id="e423b-223">If multiple connections are tested, an array of **Boolean** values is returned.</span></span>

## <span data-ttu-id="e423b-224">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="e423b-224">NOTES</span></span>

## <span data-ttu-id="e423b-225">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="e423b-225">RELATED LINKS</span></span>

[<span data-ttu-id="e423b-226">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="e423b-226">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="e423b-227">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="e423b-227">Stop-Computer</span></span>](Stop-Computer.md)

