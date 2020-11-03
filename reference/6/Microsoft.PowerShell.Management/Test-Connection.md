---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 11/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/test-connection?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-Connection
ms.openlocfilehash: 54ba1d7db60db7b4bb64f3161bba9c1fba124219
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226762"
---
# <span data-ttu-id="31aa6-103">Test-Connection</span><span class="sxs-lookup"><span data-stu-id="31aa6-103">Test-Connection</span></span>

## <span data-ttu-id="31aa6-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="31aa6-104">SYNOPSIS</span></span>
<span data-ttu-id="31aa6-105">Отправляет пакеты запроса проверки связи ICMP или проверки связи на один или несколько компьютеров.</span><span class="sxs-lookup"><span data-stu-id="31aa6-105">Sends ICMP echo request packets, or pings, to one or more computers.</span></span>

## <span data-ttu-id="31aa6-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="31aa6-106">SYNTAX</span></span>

### <span data-ttu-id="31aa6-107">Пингкаунт (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="31aa6-107">PingCount (Default)</span></span>

```
Test-Connection [-Ping] [-IPv4] [-IPv6] [-ResolveDestination] [-Source <String>] [-MaxHops <Int32>]
 [-Count <Int32>] [-Delay <Int32>] [-BufferSize <Int32>] [-DontFragment] [-TimeoutSeconds <Int32>]
 [-TargetName] <String[]> [-Quiet] [<CommonParameters>]
```

### <span data-ttu-id="31aa6-108">пингконтинуес</span><span class="sxs-lookup"><span data-stu-id="31aa6-108">PingContinues</span></span>

```
Test-Connection [-Ping] [-IPv4] [-IPv6] [-ResolveDestination] [-Source <String>] [-MaxHops <Int32>]
 [-Delay <Int32>] [-BufferSize <Int32>] [-DontFragment] [-Continues] [-TimeoutSeconds <Int32>]
 [-TargetName] <String[]> [-Quiet] [<CommonParameters>]
```

### <span data-ttu-id="31aa6-109">детектионофмтусизе</span><span class="sxs-lookup"><span data-stu-id="31aa6-109">DetectionOfMTUSize</span></span>

```
Test-Connection [-IPv4] [-IPv6] [-ResolveDestination] [-TimeoutSeconds <Int32>]
 [-TargetName] <String[]> -MTUSizeDetect [-Quiet] [<CommonParameters>]
```

### <span data-ttu-id="31aa6-110">TraceRoute</span><span class="sxs-lookup"><span data-stu-id="31aa6-110">TraceRoute</span></span>

```
Test-Connection [-IPv4] [-IPv6] [-ResolveDestination] [-Source <String>] [-MaxHops <Int32>]
 [-TimeoutSeconds <Int32>] [-TargetName] <String[]> -Traceroute [-Quiet] [<CommonParameters>]
```

### <span data-ttu-id="31aa6-111">коннектионбиткппорт</span><span class="sxs-lookup"><span data-stu-id="31aa6-111">ConnectionByTCPPort</span></span>

```
Test-Connection [-IPv4] [-IPv6] [-ResolveDestination] [-Source <String>] [-TimeoutSeconds <Int32>]
 [-TargetName] <String[]> -TCPPort <Int32> [-Quiet] [<CommonParameters>]
```

## <span data-ttu-id="31aa6-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="31aa6-112">DESCRIPTION</span></span>

<span data-ttu-id="31aa6-113">`Test-Connection`Командлет отправляет пакеты эхо-запросов протокола ICMP (ping) на один или несколько удаленных компьютеров и возвращает ответ на эхо-ответы.</span><span class="sxs-lookup"><span data-stu-id="31aa6-113">The `Test-Connection` cmdlet sends Internet Control Message Protocol (ICMP) echo request packets, or pings, to one or more remote computers and returns the echo response replies.</span></span> <span data-ttu-id="31aa6-114">С помощью этого командлета можно определить, можно ли связаться с определенным компьютером по IP-сети.</span><span class="sxs-lookup"><span data-stu-id="31aa6-114">You can use this cmdlet to determine whether a particular computer can be contacted across an IP network.</span></span>

<span data-ttu-id="31aa6-115">С помощью параметров можно `Test-Connection` указать как отправляющее, так и принимающее компьютеры, чтобы выполнить команду в качестве фонового задания, установить время ожидания и количество проверок связи, а также настроить подключение и проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="31aa6-115">You can use the parameters of `Test-Connection` to specify both the sending and receiving computers, to run the command as a background job, to set a time-out and number of pings, and to configure the connection and authentication.</span></span>

<span data-ttu-id="31aa6-116">В отличие от знакомой команды **ping** , `Test-Connection` возвращает объект **тестконнектионкомманд + пингрепорт** , который можно исследовать в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="31aa6-116">Unlike the familiar **ping** command, `Test-Connection` returns a **TestConnectionCommand+PingReport** object that you can investigate in PowerShell.</span></span> <span data-ttu-id="31aa6-117">Параметр **quiet** возвращает **логическое** значение в объекте **System. Boolean** для каждого проверенного подключения.</span><span class="sxs-lookup"><span data-stu-id="31aa6-117">The **Quiet** parameter returns a **Boolean** value in a **System.Boolean** object for each tested connection.</span></span> <span data-ttu-id="31aa6-118">Если тестируется несколько подключений, возвращается массив **логических** значений.</span><span class="sxs-lookup"><span data-stu-id="31aa6-118">If multiple connections are tested, an array of **Boolean** values is returned.</span></span>

## <span data-ttu-id="31aa6-119">Примеры</span><span class="sxs-lookup"><span data-stu-id="31aa6-119">EXAMPLES</span></span>

### <span data-ttu-id="31aa6-120">Пример 1. Отправка эхо-запросов на удаленный компьютер</span><span class="sxs-lookup"><span data-stu-id="31aa6-120">Example 1: Send echo requests to a remote computer</span></span>

<span data-ttu-id="31aa6-121">Этот пример отправляет пакеты эхо-запросов с локального компьютера на компьютер Server01.</span><span class="sxs-lookup"><span data-stu-id="31aa6-121">This example sends echo request packets from the local computer to the Server01 computer.</span></span>

```powershell
Test-Connection -TargetName Server01 -IPv4
```

```Output
Pinging Server01 [10.59.137.44] with 32 bytes of data:
Reply from 10.59.137.44: bytes=32 time=0ms TTL=128
Reply from 10.59.137.44: bytes=32 time=0ms TTL=128
Reply from 10.59.137.44: bytes=32 time=0ms TTL=128
Reply from 10.59.137.44: bytes=32 time=0ms TTL=128
Ping complete.

Source     Destination Replies
------     ----------- -------
Server01   Server01    {System.Net.NetworkInformation.PingReply, System.Net.NetworkInformation ...
```

<span data-ttu-id="31aa6-122">`Test-Connection` использует параметр **TargetName** для указания компьютера Server01.</span><span class="sxs-lookup"><span data-stu-id="31aa6-122">`Test-Connection` uses the **TargetName** parameter to specify the Server01 computer.</span></span> <span data-ttu-id="31aa6-123">Параметр **IPv4** указывает протокол для теста.</span><span class="sxs-lookup"><span data-stu-id="31aa6-123">The **IPv4** parameter specifies the protocol for the test.</span></span>

<span data-ttu-id="31aa6-124">Выходные данные ping отправляются в **информационный** поток, пока объект **тестконнектионкомманд + пингрепорт** отправляется в поток **успешного выполнения** .</span><span class="sxs-lookup"><span data-stu-id="31aa6-124">The ping output is sent to the **Information** stream while the **TestConnectionCommand+PingReport** object sent to the **Success** stream.</span></span> <span data-ttu-id="31aa6-125">Дополнительные сведения о выходных потоках см. в разделе [about_Redirection](../microsoft.powershell.core/about/about_redirection.md).</span><span class="sxs-lookup"><span data-stu-id="31aa6-125">For more information about the output streams, see [about_Redirection](../microsoft.powershell.core/about/about_redirection.md).</span></span>

### <span data-ttu-id="31aa6-126">Пример 2. Отправка эхо-запросов на несколько компьютеров</span><span class="sxs-lookup"><span data-stu-id="31aa6-126">Example 2: Send echo requests to several computers</span></span>

<span data-ttu-id="31aa6-127">Этот пример отправляет команды ping с локального компьютера на несколько удаленных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="31aa6-127">This example sends pings from the local computer to several remote computers.</span></span>

```powershell
Test-Connection -TargetName Server01, Server02, Server12
```

### <span data-ttu-id="31aa6-128">Пример 3. Отправка эхо-запросов с нескольких компьютеров на компьютер</span><span class="sxs-lookup"><span data-stu-id="31aa6-128">Example 3: Send echo requests from several computers to a computer</span></span>

<span data-ttu-id="31aa6-129">В этом примере команды ping отправляются с разных исходных компьютеров на один удаленный компьютер Server01.</span><span class="sxs-lookup"><span data-stu-id="31aa6-129">This example sends pings from different source computers to a single remote computer, Server01.</span></span>

```powershell
Test-Connection -Source Server02, Server12, localhost -TargetName Server01
```

<span data-ttu-id="31aa6-130">Этот формат команды можно использовать для тестирования задержки подключения из нескольких точек.</span><span class="sxs-lookup"><span data-stu-id="31aa6-130">Use this command format to test the latency of connections from multiple points.</span></span>

### <span data-ttu-id="31aa6-131">Пример 4. Использование параметров для настройки команды теста</span><span class="sxs-lookup"><span data-stu-id="31aa6-131">Example 4: Use parameters to customize the test command</span></span>

<span data-ttu-id="31aa6-132">В этом примере `Test-Connection` для настройки команды используются параметры.</span><span class="sxs-lookup"><span data-stu-id="31aa6-132">This example uses the parameters of `Test-Connection` to customize the command.</span></span> <span data-ttu-id="31aa6-133">Локальный компьютер отправляет тест проверки связи на удаленный компьютер.</span><span class="sxs-lookup"><span data-stu-id="31aa6-133">The local computer sends a ping test to a remote computer.</span></span>

```powershell
Test-Connection -TargetName Server01 -Count 3 -Delay 2 -MaxHops 255 -BufferSize 256
```

<span data-ttu-id="31aa6-134">`Test-Connection` использует параметр **TargetName** для указания Server01.</span><span class="sxs-lookup"><span data-stu-id="31aa6-134">`Test-Connection` uses the **TargetName** parameter to specify Server01.</span></span> <span data-ttu-id="31aa6-135">Параметр **Count** указывает три сообщения проверки связи, отправляемые на компьютер Server01 с **задержкой** в 2 секунды.</span><span class="sxs-lookup"><span data-stu-id="31aa6-135">The **Count** parameter specifies three pings are sent to the Server01 computer with a **Delay** of 2-second intervals.</span></span>

<span data-ttu-id="31aa6-136">Эти параметры можно использовать, если ожидается, что ответ на запрос проверки связи займет больше времени, чем обычно, из-за расширенного числа прыжков или состояния сети с высоким трафиком.</span><span class="sxs-lookup"><span data-stu-id="31aa6-136">You might use these options when the ping response is expected to take longer than usual, either because of an extended number of hops or a high-traffic network condition.</span></span>

### <span data-ttu-id="31aa6-137">Пример 5. выполнение теста в качестве фонового задания</span><span class="sxs-lookup"><span data-stu-id="31aa6-137">Example 5: Run a test as a background job</span></span>

<span data-ttu-id="31aa6-138">В этом примере показано, как выполнить `Test-Connection` команду в качестве фонового задания PowerShell.</span><span class="sxs-lookup"><span data-stu-id="31aa6-138">This example shows how to run a `Test-Connection` command as a PowerShell background job.</span></span>

```powershell
$job = Start-Job -ScriptBlock { Test-Connection -TargetName (Get-Content "Servers.txt") }
if ($job.JobStateInfo.State -ne "Running") { $Results = Receive-Job $job }
```

<span data-ttu-id="31aa6-139">`Start-Job`Команда использует `Test-Connection` командлет для проверки связи между многими компьютерами предприятия.</span><span class="sxs-lookup"><span data-stu-id="31aa6-139">The `Start-Job` command uses the `Test-Connection` cmdlet to ping many computers in an enterprise.</span></span>
<span data-ttu-id="31aa6-140">Значение параметра **TargetName** — это `Get-Content` команда, которая считывает список имен компьютеров из `Servers.txt` файла.</span><span class="sxs-lookup"><span data-stu-id="31aa6-140">The value of the **TargetName** parameter is a `Get-Content` command that reads a list of computer names from the `Servers.txt` file.</span></span> <span data-ttu-id="31aa6-141">Команда использует `Start-Job` командлет для выполнения команды в качестве фонового задания и сохраняет задание в `$job` переменной.</span><span class="sxs-lookup"><span data-stu-id="31aa6-141">The command uses the `Start-Job` cmdlet to run the command as a background job and it saves the job in the `$job` variable.</span></span>

<span data-ttu-id="31aa6-142">`if`Команда проверяет, что задание еще не выполняется.</span><span class="sxs-lookup"><span data-stu-id="31aa6-142">The `if` command checks to see that the job isn't still running.</span></span> <span data-ttu-id="31aa6-143">Если задание не выполняется, `Receive-Job` получает результаты и сохраняет их в `$Results` переменной.</span><span class="sxs-lookup"><span data-stu-id="31aa6-143">If the job isn't running, `Receive-Job` gets the results and stores them in the `$Results` variable.</span></span>

### <span data-ttu-id="31aa6-144">Пример 6. Создание сеанса только в случае успешности проверки соединения</span><span class="sxs-lookup"><span data-stu-id="31aa6-144">Example 6: Create a session only if a connection test succeeds</span></span>

<span data-ttu-id="31aa6-145">Этот пример создает сеанс на компьютере Server01, только если по крайней мере один из пакетов проверки связи успешно отправлен на компьютер.</span><span class="sxs-lookup"><span data-stu-id="31aa6-145">This example creates a session on the Server01 computer only if at least one of the pings sent to the computer succeeds.</span></span>

```powershell
if (Test-Connection -TargetName Server01 -Quiet) {New-PSSession Server01}
```

<span data-ttu-id="31aa6-146">`if`Команда использует `Test-Connection` командлет для проверки связи с компьютером Server01.</span><span class="sxs-lookup"><span data-stu-id="31aa6-146">The `if` command uses the `Test-Connection` cmdlet to ping the Server01 computer.</span></span> <span data-ttu-id="31aa6-147">Команда использует параметр **quiet** , который возвращает **логическое** значение вместо объекта **тестконнектионкомманд + пингрепорт** .</span><span class="sxs-lookup"><span data-stu-id="31aa6-147">The command uses the **Quiet** parameter, which returns a **Boolean** value, instead of a **TestConnectionCommand+PingReport** object.</span></span>

<span data-ttu-id="31aa6-148">Значение равно, `$True` Если любая из четырех проверок связи успешно выполнена.</span><span class="sxs-lookup"><span data-stu-id="31aa6-148">The value is `$True` if any of the four pings succeed.</span></span> <span data-ttu-id="31aa6-149">Если ни одна из проверок связи не выполнена успешно, значение равно `$False` .</span><span class="sxs-lookup"><span data-stu-id="31aa6-149">If none of the pings succeed, the value is `$False`.</span></span>

<span data-ttu-id="31aa6-150">Если `Test-Connection` команда возвращает значение `$True` , команда использует `New-PSSession` командлет для создания **сеанса PSSession**.</span><span class="sxs-lookup"><span data-stu-id="31aa6-150">If the `Test-Connection` command returns a value of `$True`, the command uses the `New-PSSession` cmdlet to create the **PSSession**.</span></span>

### <span data-ttu-id="31aa6-151">Пример 7. Использование параметра Traceroute</span><span class="sxs-lookup"><span data-stu-id="31aa6-151">Example 7: Use the Traceroute parameter</span></span>

<span data-ttu-id="31aa6-152">Начиная с PowerShell 6,0, параметр **Traceroute** сопоставляет маршрут между локальным компьютером и удаленным назначением, указанным с помощью параметра **TargetName** .</span><span class="sxs-lookup"><span data-stu-id="31aa6-152">Beginning in PowerShell 6.0, the **Traceroute** parameter maps a route between the local computer and the remote destination you specify with the **TargetName** parameter.</span></span>

```powershell
Test-Connection -TargetName www.microsoft.com -Traceroute | ForEach-Object {
  $_ | Format-Table Source, DestinationAddress, DestinationHost
  $_.Replies | ForEach-Object {
      $_ | Format-Table Hop, ReplyRouterAddress
      $_.PingReplies | Format-Table
  }
}
```

```Output
Tracing route to www.microsoft.com [96.6.27.90] over a maximum of 128 hops:
  1   0 ms   0 ms   0 ms   192.168.0.3 [192.168.0.3]
  2   0 ms   0 ms   0 ms   192.168.1.1 [192.168.1.1]
  3   3 ms   29 ms   4 ms   96.6.27.90 [96.6.27.90]
Trace complete.

Source      DestinationAddress DestinationHost   Replies
------      ------------------ ---------------   -------
SERVER01    96.6.27.90         www.microsoft.com {, , }

Hop ReplyRouterAddress
--- ------------------
  1 192.168.0.3

    Status Address      RoundtripTime Options Buffer
    ------ -------      ------------- ------- ------
TtlExpired 192.168.86.1             0         {}
TtlExpired 192.168.86.1             0         {}
TtlExpired 192.168.86.1             0         {}

Hop ReplyRouterAddress
--- ------------------
  2 192.168.1.1

    Status Address     RoundtripTime Options Buffer
    ------ -------     ------------- ------- ------
TtlExpired 192.168.1.1             0         {}
TtlExpired 192.168.1.1             0         {}
TtlExpired 192.168.1.1             0         {}

Hop ReplyRouterAddress
--- ------------------
  3 96.6.27.90

 Status Address    RoundtripTime Options                                   Buffer
 ------ -------    ------------- -------                                   ------
Success 96.6.27.90             3 System.Net.NetworkInformation.PingOptions {97, 98, 99, 100…}
Success 96.6.27.90             2 System.Net.NetworkInformation.PingOptions {97, 98, 99, 100…}
Success 96.6.27.90             4 System.Net.NetworkInformation.PingOptions {97, 98, 99, 100…}
```

<span data-ttu-id="31aa6-153">`Test-Connection`Команда использует параметр **Traceroute** .</span><span class="sxs-lookup"><span data-stu-id="31aa6-153">The `Test-Connection` command uses the **Traceroute** parameter.</span></span> <span data-ttu-id="31aa6-154">Результаты, являющиеся `[Microsoft.PowerShell.Commands.TestConnectionCommand+TraceRouteResult]` объектами, передаются в `ForEach-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="31aa6-154">The results, which are `[Microsoft.PowerShell.Commands.TestConnectionCommand+TraceRouteResult]` objects, are piped to the `ForEach-Object` cmdlet.</span></span> <span data-ttu-id="31aa6-155">`ForEach-Object` создает структурированные выходные данные вложенных `[Microsoft.PowerShell.Commands.TestConnectionCommand+TraceRouteReply]` объектов и последующих `[System.Net.NetworkInformation.PingReply]` объектов.</span><span class="sxs-lookup"><span data-stu-id="31aa6-155">`ForEach-Object` creates a structured output of the contained `[Microsoft.PowerShell.Commands.TestConnectionCommand+TraceRouteReply]` objects and subsequent `[System.Net.NetworkInformation.PingReply]` objects.</span></span>

## <span data-ttu-id="31aa6-156">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="31aa6-156">PARAMETERS</span></span>

### <span data-ttu-id="31aa6-157">— BufferSize</span><span class="sxs-lookup"><span data-stu-id="31aa6-157">-BufferSize</span></span>

<span data-ttu-id="31aa6-158">Указывает размер (в байтах) буфера, отправленного с помощью этой команды.</span><span class="sxs-lookup"><span data-stu-id="31aa6-158">Specifies the size, in bytes, of the buffer sent with this command.</span></span> <span data-ttu-id="31aa6-159">Значение по умолчанию: 32.</span><span class="sxs-lookup"><span data-stu-id="31aa6-159">The default value is 32.</span></span>

```yaml
Type: System.Int32
Parameter Sets: PingCount, PingContinues
Aliases: Size, Bytes, BS

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="31aa6-160">— Количество</span><span class="sxs-lookup"><span data-stu-id="31aa6-160">-Count</span></span>

<span data-ttu-id="31aa6-161">Указывает число отправляемых запросов проверки связи.</span><span class="sxs-lookup"><span data-stu-id="31aa6-161">Specifies the number of echo requests to send.</span></span> <span data-ttu-id="31aa6-162">Значение по умолчанию — 4.</span><span class="sxs-lookup"><span data-stu-id="31aa6-162">The default value is 4.</span></span>

```yaml
Type: System.Int32
Parameter Sets: PingCount
Aliases:

Required: False
Position: Named
Default value: 4
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="31aa6-163">-Delay</span><span class="sxs-lookup"><span data-stu-id="31aa6-163">-Delay</span></span>

<span data-ttu-id="31aa6-164">Задает интервал между проверками связи в секундах.</span><span class="sxs-lookup"><span data-stu-id="31aa6-164">Specifies the interval between pings, in seconds.</span></span>

```yaml
Type: System.Int32
Parameter Sets: PingCount, PingContinues
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="31aa6-165">-Донтфрагмент</span><span class="sxs-lookup"><span data-stu-id="31aa6-165">-DontFragment</span></span>

<span data-ttu-id="31aa6-166">Этот параметр задает флаг « **не фрагментировать** » в заголовке IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="31aa6-166">This parameter sets the **Don't Fragment** flag in the IP header.</span></span> <span data-ttu-id="31aa6-167">Этот параметр можно использовать с параметром **bufferSize** для проверки размера MTU пути.</span><span class="sxs-lookup"><span data-stu-id="31aa6-167">You can use this parameter with the **BufferSize** parameter to test the Path MTU size.</span></span> <span data-ttu-id="31aa6-168">Дополнительные сведения о пути MTU см. в статье о [поиске пути MTU](https://wikipedia.org/wiki/Path_MTU_Discovery) в Википедии.</span><span class="sxs-lookup"><span data-stu-id="31aa6-168">For more information about Path MTU, see the [Path MTU Discovery](https://wikipedia.org/wiki/Path_MTU_Discovery) article in wikipedia.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PingCount, PingContinues
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="31aa6-169">— IPv4</span><span class="sxs-lookup"><span data-stu-id="31aa6-169">-IPv4</span></span>

<span data-ttu-id="31aa6-170">Заставляет командлет использовать протокол IPv4 для теста.</span><span class="sxs-lookup"><span data-stu-id="31aa6-170">Forces the cmdlet to use the IPv4 protocol for the test.</span></span>

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

### <span data-ttu-id="31aa6-171">— IPv6</span><span class="sxs-lookup"><span data-stu-id="31aa6-171">-IPv6</span></span>

<span data-ttu-id="31aa6-172">Заставляет командлет использовать протокол IPv6 для теста.</span><span class="sxs-lookup"><span data-stu-id="31aa6-172">Forces the cmdlet to use the IPv6 protocol for the test.</span></span>

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

### <span data-ttu-id="31aa6-173">-Максхопс</span><span class="sxs-lookup"><span data-stu-id="31aa6-173">-MaxHops</span></span>

<span data-ttu-id="31aa6-174">Задает максимальное число прыжков, на которое может быть отправлено сообщение с запросом ICMP.</span><span class="sxs-lookup"><span data-stu-id="31aa6-174">Sets the maximum number of hops that an ICMP request message can be sent.</span></span> <span data-ttu-id="31aa6-175">Значение по умолчанию управляется операционной системой.</span><span class="sxs-lookup"><span data-stu-id="31aa6-175">The default value is controlled by the operating system.</span></span> <span data-ttu-id="31aa6-176">Значение по умолчанию для Windows 10 — 128 прыжков.</span><span class="sxs-lookup"><span data-stu-id="31aa6-176">The default value for Windows 10 is 128 hops.</span></span>

```yaml
Type: System.Int32
Parameter Sets: PingCount, PingContinues, TraceRoute
Aliases: Ttl, TimeToLive, Hops

Required: False
Position: Named
Default value: 128 hops in Windows 10
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="31aa6-177">— Проверка связи</span><span class="sxs-lookup"><span data-stu-id="31aa6-177">-Ping</span></span>

<span data-ttu-id="31aa6-178">Вызывает выполнение командлетом проверки связи, что является действием по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="31aa6-178">Causes the cmdlet to do a ping test, which is the default action.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PingCount, PingContinues
Aliases:

Required: False
Position: Named
Default value: Ping test
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="31aa6-179">-Quiet</span><span class="sxs-lookup"><span data-stu-id="31aa6-179">-Quiet</span></span>

<span data-ttu-id="31aa6-180">Параметр **quiet** возвращает **логическое** значение в объекте **System. Boolean** .</span><span class="sxs-lookup"><span data-stu-id="31aa6-180">The **Quiet** parameter returns a **Boolean** value in a **System.Boolean** object.</span></span> <span data-ttu-id="31aa6-181">Использование этого параметра подавляет все ошибки.</span><span class="sxs-lookup"><span data-stu-id="31aa6-181">Using this parameter suppresses all errors.</span></span>

<span data-ttu-id="31aa6-182">Каждое проверенное соединение возвращает **логическое** значение.</span><span class="sxs-lookup"><span data-stu-id="31aa6-182">Each connection that's tested returns a **Boolean** value.</span></span> <span data-ttu-id="31aa6-183">Если параметр **TargetName** задает несколько компьютеров, возвращается массив **логических** значений.</span><span class="sxs-lookup"><span data-stu-id="31aa6-183">If the **TargetName** parameter specifies multiple computers, an array of **Boolean** values is returned.</span></span>

<span data-ttu-id="31aa6-184">Если **Проверка** связи выполнена успешно, `$True` возвращается значение.</span><span class="sxs-lookup"><span data-stu-id="31aa6-184">If **any** ping succeeds, `$True` is returned.</span></span>

<span data-ttu-id="31aa6-185">Если **все** проверки связи завершаются ошибкой, `$False` возвращается значение.</span><span class="sxs-lookup"><span data-stu-id="31aa6-185">If **all** pings fail, `$False` is returned.</span></span>

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

### <span data-ttu-id="31aa6-186">-Ресолведестинатион</span><span class="sxs-lookup"><span data-stu-id="31aa6-186">-ResolveDestination</span></span>

<span data-ttu-id="31aa6-187">Вызывает попытку командлета разрешить DNS-имя целевого объекта.</span><span class="sxs-lookup"><span data-stu-id="31aa6-187">Causes the cmdlet to attempt to resolve the DNS name of the target.</span></span>

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

### <span data-ttu-id="31aa6-188">-Source</span><span class="sxs-lookup"><span data-stu-id="31aa6-188">-Source</span></span>

<span data-ttu-id="31aa6-189">Указывает имена компьютеров, на которых создается проверка связи.</span><span class="sxs-lookup"><span data-stu-id="31aa6-189">Specifies the names of the computers where the ping originates.</span></span> <span data-ttu-id="31aa6-190">Введите разделенный запятыми список имен компьютеров.</span><span class="sxs-lookup"><span data-stu-id="31aa6-190">Enter a comma-separated list of computer names.</span></span> <span data-ttu-id="31aa6-191">По умолчанию это локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="31aa6-191">The default is the local computer.</span></span>

```yaml
Type: System.String
Parameter Sets: PingCount, PingContinues, TraceRoute, ConnectionByTCPPort
Aliases:

Required: False
Position: Named
Default value: Local computer
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="31aa6-192">-TargetName</span><span class="sxs-lookup"><span data-stu-id="31aa6-192">-TargetName</span></span>

<span data-ttu-id="31aa6-193">Указывает компьютеры для проверки.</span><span class="sxs-lookup"><span data-stu-id="31aa6-193">Specifies the computers to test.</span></span> <span data-ttu-id="31aa6-194">Введите имена компьютеров или IP-адреса в формате IPv4 или IPv6.</span><span class="sxs-lookup"><span data-stu-id="31aa6-194">Type the computer names or type IP addresses in IPv4 or IPv6 format.</span></span> <span data-ttu-id="31aa6-195">Подстановочные знаки не допускаются.</span><span class="sxs-lookup"><span data-stu-id="31aa6-195">Wildcard characters aren't permitted.</span></span> <span data-ttu-id="31aa6-196">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="31aa6-196">This parameter is required.</span></span> <span data-ttu-id="31aa6-197">**ComputerName** — это псевдоним для этого параметра.</span><span class="sxs-lookup"><span data-stu-id="31aa6-197">**ComputerName** is an alias for this parameter.</span></span>

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

### <span data-ttu-id="31aa6-198">-TCPPort</span><span class="sxs-lookup"><span data-stu-id="31aa6-198">-TCPPort</span></span>

<span data-ttu-id="31aa6-199">Указывает номер порта TCP на целевом объекте, который будет использоваться при проверке подключения TCP.</span><span class="sxs-lookup"><span data-stu-id="31aa6-199">Specifies the TCP port number on the target to be used in the TCP connection test.</span></span> <span data-ttu-id="31aa6-200">Командлет попытается установить TCP-подключение к указанному порту на целевом объекте.</span><span class="sxs-lookup"><span data-stu-id="31aa6-200">The cmdlet will attempt to make a TCP connection to the specified port on the target.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ConnectionByTCPPort
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="31aa6-201">-TimeoutSeconds</span><span class="sxs-lookup"><span data-stu-id="31aa6-201">-TimeoutSeconds</span></span>

<span data-ttu-id="31aa6-202">Задает значение времени ожидания для теста.</span><span class="sxs-lookup"><span data-stu-id="31aa6-202">Sets the timeout value for the test.</span></span> <span data-ttu-id="31aa6-203">Тест завершается ошибкой, если не получен ответ до истечения времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="31aa6-203">The test fails if a response isn't received before the timeout expires.</span></span> <span data-ttu-id="31aa6-204">Значение по умолчанию — пять секунд.</span><span class="sxs-lookup"><span data-stu-id="31aa6-204">The default is five seconds.</span></span>

<span data-ttu-id="31aa6-205">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="31aa6-205">This parameter was introduced in PowerShell 6.0.</span></span>

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

### <span data-ttu-id="31aa6-206">-Traceroute</span><span class="sxs-lookup"><span data-stu-id="31aa6-206">-Traceroute</span></span>

<span data-ttu-id="31aa6-207">Вызывает выполнение командлетом Traceroute теста.</span><span class="sxs-lookup"><span data-stu-id="31aa6-207">Causes the cmdlet to do a traceroute test.</span></span> <span data-ttu-id="31aa6-208">При использовании этого параметра командлет возвращает `TestConnectionCommand+TraceRouteResult` объект.</span><span class="sxs-lookup"><span data-stu-id="31aa6-208">When this parameter is used, the cmdlet returns a `TestConnectionCommand+TraceRouteResult` object.</span></span>

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

### <span data-ttu-id="31aa6-209">— Продолжение</span><span class="sxs-lookup"><span data-stu-id="31aa6-209">-Continues</span></span>

<span data-ttu-id="31aa6-210">Указывает, что командлет будет постоянно отсылать запросы проверки связи.</span><span class="sxs-lookup"><span data-stu-id="31aa6-210">Causes the cmdlet to send ping requests continuously.</span></span> <span data-ttu-id="31aa6-211">Этот параметр нельзя использовать с параметром **Count** .</span><span class="sxs-lookup"><span data-stu-id="31aa6-211">This parameter can't be used with the **Count** parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PingContinues
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="31aa6-212">-Мтусизедетект</span><span class="sxs-lookup"><span data-stu-id="31aa6-212">-MTUSizeDetect</span></span>

<span data-ttu-id="31aa6-213">Этот параметр используется для определения размера MTU пути.</span><span class="sxs-lookup"><span data-stu-id="31aa6-213">This parameter is used to discover the Path MTU size.</span></span> <span data-ttu-id="31aa6-214">Командлет возвращает объект **пингрепли # мтусизе** , который содержит размер MTU для пути к целевому объекту.</span><span class="sxs-lookup"><span data-stu-id="31aa6-214">The cmdlet returns a **PingReply#MTUSize** object that contains the Path MTU size to the target.</span></span> <span data-ttu-id="31aa6-215">Дополнительные сведения о пути MTU см. в статье о [поиске пути MTU](https://wikipedia.org/wiki/Path_MTU_Discovery) в Википедии.</span><span class="sxs-lookup"><span data-stu-id="31aa6-215">For more information about Path MTU, see the [Path MTU Discovery](https://wikipedia.org/wiki/Path_MTU_Discovery) article in wikipedia.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DetectionOfMTUSize
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="31aa6-216">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="31aa6-216">CommonParameters</span></span>

<span data-ttu-id="31aa6-217">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="31aa6-217">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="31aa6-218">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="31aa6-218">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="31aa6-219">Входные данные</span><span class="sxs-lookup"><span data-stu-id="31aa6-219">INPUTS</span></span>

### <span data-ttu-id="31aa6-220">Нет</span><span class="sxs-lookup"><span data-stu-id="31aa6-220">None</span></span>

<span data-ttu-id="31aa6-221">Вы не можете передать входные данные в этот командлет.</span><span class="sxs-lookup"><span data-stu-id="31aa6-221">You can't pipe input to this cmdlet.</span></span>

## <span data-ttu-id="31aa6-222">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="31aa6-222">OUTPUTS</span></span>

### <span data-ttu-id="31aa6-223">Тестконнектионкомманд + Пингрепорт, Тестконнектионкомманд + Трацераутересулт, Boolean, Пингрепли # MTUSize</span><span class="sxs-lookup"><span data-stu-id="31aa6-223">TestConnectionCommand+PingReport, TestConnectionCommand+TraceRouteResult, Boolean, PingReply#MTUSize</span></span>

<span data-ttu-id="31aa6-224">При указании параметра **quiet** возвращается **логическое** значение.</span><span class="sxs-lookup"><span data-stu-id="31aa6-224">If you specify the **Quiet** parameter, it returns a **Boolean** value.</span></span> <span data-ttu-id="31aa6-225">Если тестируется несколько подключений, возвращается массив **логических** значений.</span><span class="sxs-lookup"><span data-stu-id="31aa6-225">If multiple connections are tested, an array of **Boolean** values is returned.</span></span> <span data-ttu-id="31aa6-226">В противном случае `Test-Connection` возвращает объект **Тестконнектионкомманд + пингрепорт** для каждой проверки связи.</span><span class="sxs-lookup"><span data-stu-id="31aa6-226">Otherwise, `Test-Connection` returns a **TestConnectionCommand+PingReport** object for each ping.</span></span>

## <span data-ttu-id="31aa6-227">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="31aa6-227">NOTES</span></span>

## <span data-ttu-id="31aa6-228">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="31aa6-228">RELATED LINKS</span></span>

[<span data-ttu-id="31aa6-229">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="31aa6-229">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="31aa6-230">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="31aa6-230">Stop-Computer</span></span>](Stop-Computer.md)
