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
# Test-Connection

## Краткий обзор
Отправляет пакеты запроса проверки связи ICMP или проверки связи на один или несколько компьютеров.

## SYNTAX

### Пингкаунт (по умолчанию)

```
Test-Connection [-Ping] [-IPv4] [-IPv6] [-ResolveDestination] [-Source <String>] [-MaxHops <Int32>]
 [-Count <Int32>] [-Delay <Int32>] [-BufferSize <Int32>] [-DontFragment] [-TimeoutSeconds <Int32>]
 [-TargetName] <String[]> [-Quiet] [<CommonParameters>]
```

### пингконтинуес

```
Test-Connection [-Ping] [-IPv4] [-IPv6] [-ResolveDestination] [-Source <String>] [-MaxHops <Int32>]
 [-Delay <Int32>] [-BufferSize <Int32>] [-DontFragment] [-Continues] [-TimeoutSeconds <Int32>]
 [-TargetName] <String[]> [-Quiet] [<CommonParameters>]
```

### детектионофмтусизе

```
Test-Connection [-IPv4] [-IPv6] [-ResolveDestination] [-TimeoutSeconds <Int32>]
 [-TargetName] <String[]> -MTUSizeDetect [-Quiet] [<CommonParameters>]
```

### TraceRoute

```
Test-Connection [-IPv4] [-IPv6] [-ResolveDestination] [-Source <String>] [-MaxHops <Int32>]
 [-TimeoutSeconds <Int32>] [-TargetName] <String[]> -Traceroute [-Quiet] [<CommonParameters>]
```

### коннектионбиткппорт

```
Test-Connection [-IPv4] [-IPv6] [-ResolveDestination] [-Source <String>] [-TimeoutSeconds <Int32>]
 [-TargetName] <String[]> -TCPPort <Int32> [-Quiet] [<CommonParameters>]
```

## DESCRIPTION

`Test-Connection`Командлет отправляет пакеты эхо-запросов протокола ICMP (ping) на один или несколько удаленных компьютеров и возвращает ответ на эхо-ответы. С помощью этого командлета можно определить, можно ли связаться с определенным компьютером по IP-сети.

С помощью параметров можно `Test-Connection` указать как отправляющее, так и принимающее компьютеры, чтобы выполнить команду в качестве фонового задания, установить время ожидания и количество проверок связи, а также настроить подключение и проверку подлинности.

В отличие от знакомой команды **ping** , `Test-Connection` возвращает объект **тестконнектионкомманд + пингрепорт** , который можно исследовать в PowerShell. Параметр **quiet** возвращает **логическое** значение в объекте **System. Boolean** для каждого проверенного подключения. Если тестируется несколько подключений, возвращается массив **логических** значений.

## Примеры

### Пример 1. Отправка эхо-запросов на удаленный компьютер

Этот пример отправляет пакеты эхо-запросов с локального компьютера на компьютер Server01.

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

`Test-Connection` использует параметр **TargetName** для указания компьютера Server01. Параметр **IPv4** указывает протокол для теста.

Выходные данные ping отправляются в **информационный** поток, пока объект **тестконнектионкомманд + пингрепорт** отправляется в поток **успешного выполнения** . Дополнительные сведения о выходных потоках см. в разделе [about_Redirection](../microsoft.powershell.core/about/about_redirection.md).

### Пример 2. Отправка эхо-запросов на несколько компьютеров

Этот пример отправляет команды ping с локального компьютера на несколько удаленных компьютеров.

```powershell
Test-Connection -TargetName Server01, Server02, Server12
```

### Пример 3. Отправка эхо-запросов с нескольких компьютеров на компьютер

В этом примере команды ping отправляются с разных исходных компьютеров на один удаленный компьютер Server01.

```powershell
Test-Connection -Source Server02, Server12, localhost -TargetName Server01
```

Этот формат команды можно использовать для тестирования задержки подключения из нескольких точек.

### Пример 4. Использование параметров для настройки команды теста

В этом примере `Test-Connection` для настройки команды используются параметры. Локальный компьютер отправляет тест проверки связи на удаленный компьютер.

```powershell
Test-Connection -TargetName Server01 -Count 3 -Delay 2 -MaxHops 255 -BufferSize 256
```

`Test-Connection` использует параметр **TargetName** для указания Server01. Параметр **Count** указывает три сообщения проверки связи, отправляемые на компьютер Server01 с **задержкой** в 2 секунды.

Эти параметры можно использовать, если ожидается, что ответ на запрос проверки связи займет больше времени, чем обычно, из-за расширенного числа прыжков или состояния сети с высоким трафиком.

### Пример 5. выполнение теста в качестве фонового задания

В этом примере показано, как выполнить `Test-Connection` команду в качестве фонового задания PowerShell.

```powershell
$job = Start-Job -ScriptBlock { Test-Connection -TargetName (Get-Content "Servers.txt") }
if ($job.JobStateInfo.State -ne "Running") { $Results = Receive-Job $job }
```

`Start-Job`Команда использует `Test-Connection` командлет для проверки связи между многими компьютерами предприятия.
Значение параметра **TargetName** — это `Get-Content` команда, которая считывает список имен компьютеров из `Servers.txt` файла. Команда использует `Start-Job` командлет для выполнения команды в качестве фонового задания и сохраняет задание в `$job` переменной.

`if`Команда проверяет, что задание еще не выполняется. Если задание не выполняется, `Receive-Job` получает результаты и сохраняет их в `$Results` переменной.

### Пример 6. Создание сеанса только в случае успешности проверки соединения

Этот пример создает сеанс на компьютере Server01, только если по крайней мере один из пакетов проверки связи успешно отправлен на компьютер.

```powershell
if (Test-Connection -TargetName Server01 -Quiet) {New-PSSession Server01}
```

`if`Команда использует `Test-Connection` командлет для проверки связи с компьютером Server01. Команда использует параметр **quiet** , который возвращает **логическое** значение вместо объекта **тестконнектионкомманд + пингрепорт** .

Значение равно, `$True` Если любая из четырех проверок связи успешно выполнена. Если ни одна из проверок связи не выполнена успешно, значение равно `$False` .

Если `Test-Connection` команда возвращает значение `$True` , команда использует `New-PSSession` командлет для создания **сеанса PSSession**.

### Пример 7. Использование параметра Traceroute

Начиная с PowerShell 6,0, параметр **Traceroute** сопоставляет маршрут между локальным компьютером и удаленным назначением, указанным с помощью параметра **TargetName** .

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

`Test-Connection`Команда использует параметр **Traceroute** . Результаты, являющиеся `[Microsoft.PowerShell.Commands.TestConnectionCommand+TraceRouteResult]` объектами, передаются в `ForEach-Object` командлет. `ForEach-Object` создает структурированные выходные данные вложенных `[Microsoft.PowerShell.Commands.TestConnectionCommand+TraceRouteReply]` объектов и последующих `[System.Net.NetworkInformation.PingReply]` объектов.

## PARAMETERS

### — BufferSize

Указывает размер (в байтах) буфера, отправленного с помощью этой команды. Значение по умолчанию: 32.

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

### — Количество

Указывает число отправляемых запросов проверки связи. Значение по умолчанию — 4.

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

### -Delay

Задает интервал между проверками связи в секундах.

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

### -Донтфрагмент

Этот параметр задает флаг « **не фрагментировать** » в заголовке IP-адреса. Этот параметр можно использовать с параметром **bufferSize** для проверки размера MTU пути. Дополнительные сведения о пути MTU см. в статье о [поиске пути MTU](https://wikipedia.org/wiki/Path_MTU_Discovery) в Википедии.

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

### — IPv4

Заставляет командлет использовать протокол IPv4 для теста.

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

### — IPv6

Заставляет командлет использовать протокол IPv6 для теста.

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

### -Максхопс

Задает максимальное число прыжков, на которое может быть отправлено сообщение с запросом ICMP. Значение по умолчанию управляется операционной системой. Значение по умолчанию для Windows 10 — 128 прыжков.

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

### — Проверка связи

Вызывает выполнение командлетом проверки связи, что является действием по умолчанию.

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

### -Quiet

Параметр **quiet** возвращает **логическое** значение в объекте **System. Boolean** . Использование этого параметра подавляет все ошибки.

Каждое проверенное соединение возвращает **логическое** значение. Если параметр **TargetName** задает несколько компьютеров, возвращается массив **логических** значений.

Если **Проверка** связи выполнена успешно, `$True` возвращается значение.

Если **все** проверки связи завершаются ошибкой, `$False` возвращается значение.

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

### -Ресолведестинатион

Вызывает попытку командлета разрешить DNS-имя целевого объекта.

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

### -Source

Указывает имена компьютеров, на которых создается проверка связи. Введите разделенный запятыми список имен компьютеров. По умолчанию это локальный компьютер.

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

### -TargetName

Указывает компьютеры для проверки. Введите имена компьютеров или IP-адреса в формате IPv4 или IPv6. Подстановочные знаки не допускаются. Этот параметр обязателен. **ComputerName** — это псевдоним для этого параметра.

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

### -TCPPort

Указывает номер порта TCP на целевом объекте, который будет использоваться при проверке подключения TCP. Командлет попытается установить TCP-подключение к указанному порту на целевом объекте.

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

### -TimeoutSeconds

Задает значение времени ожидания для теста. Тест завершается ошибкой, если не получен ответ до истечения времени ожидания. Значение по умолчанию — пять секунд.

Этот параметр появился в PowerShell 6,0.

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

### -Traceroute

Вызывает выполнение командлетом Traceroute теста. При использовании этого параметра командлет возвращает `TestConnectionCommand+TraceRouteResult` объект.

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

### — Продолжение

Указывает, что командлет будет постоянно отсылать запросы проверки связи. Этот параметр нельзя использовать с параметром **Count** .

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

### -Мтусизедетект

Этот параметр используется для определения размера MTU пути. Командлет возвращает объект **пингрепли # мтусизе** , который содержит размер MTU для пути к целевому объекту. Дополнительные сведения о пути MTU см. в статье о [поиске пути MTU](https://wikipedia.org/wiki/Path_MTU_Discovery) в Википедии.

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

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет

Вы не можете передать входные данные в этот командлет.

## Выходные данные

### Тестконнектионкомманд + Пингрепорт, Тестконнектионкомманд + Трацераутересулт, Boolean, Пингрепли # MTUSize

При указании параметра **quiet** возвращается **логическое** значение. Если тестируется несколько подключений, возвращается массив **логических** значений. В противном случае `Test-Connection` возвращает объект **Тестконнектионкомманд + пингрепорт** для каждой проверки связи.

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Restart-Computer](Restart-Computer.md)

[Stop-Computer](Stop-Computer.md)
