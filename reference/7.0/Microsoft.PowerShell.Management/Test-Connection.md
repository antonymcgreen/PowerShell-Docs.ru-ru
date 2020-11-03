---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/test-connection?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-Connection
ms.openlocfilehash: 04e9e47055610ef8120b44f2418a0843e5901062
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93225958"
---
# Test-Connection

## Краткий обзор
Отправляет пакеты запроса проверки связи ICMP или проверки связи на один или несколько компьютеров.

## SYNTAX

### Дефаултпинг (по умолчанию)

```
Test-Connection [-TargetName] <string[]> [-Ping] [-IPv4] [-IPv6] [-ResolveDestination]
 [-Source <string>] [-MaxHops <int>] [-Count <int>] [-Delay <int>] [-BufferSize <int>]
 [-DontFragment] [-TimeoutSeconds <int>] [-Quiet] [<CommonParameters>]
```

### репеатпинг

```
Test-Connection [-TargetName] <string[]> -Repeat [-Ping] [-IPv4] [-IPv6] [-ResolveDestination]
 [-Source <string>] [-MaxHops <int>] [-Delay <int>] [-BufferSize <int>] [-DontFragment]
 [-TimeoutSeconds <int>] [-Quiet] [<CommonParameters>]
```

### мтусизедетект

```
Test-Connection [-TargetName] <string[]> -MtuSize [-IPv4] [-IPv6] [-ResolveDestination]
 [-TimeoutSeconds <int>] [-Quiet] [<CommonParameters>]
```

### TraceRoute

```
Test-Connection [-TargetName] <string[]> -Traceroute [-IPv4] [-IPv6] [-ResolveDestination]
 [-Source <string>] [-MaxHops <int>] [-TimeoutSeconds <int>] [-Quiet] [<CommonParameters>]
```

### TcpPort

```
Test-Connection [-TargetName] <string[]> -TcpPort <int> [-IPv4] [-IPv6] [-ResolveDestination]
 [-Source <string>] [-TimeoutSeconds <int>] [-Quiet] [<CommonParameters>]
```

## DESCRIPTION

`Test-Connection`Командлет отправляет пакеты эхо-запросов протокола ICMP (ping) на один или несколько удаленных компьютеров и возвращает ответ на эхо-ответы. С помощью этого командлета можно определить, можно ли связаться с определенным компьютером по IP-сети.

С помощью параметров можно `Test-Connection` указать как отправляющее, так и принимающее компьютеры, чтобы выполнить команду в качестве фонового задания, установить время ожидания и количество проверок связи, а также настроить подключение и проверку подлинности.

В отличие от знакомой команды **ping** , `Test-Connection` возвращает объект **тестконнектионкомманд + пингстатус** , который можно исследовать в PowerShell. Параметр **quiet** возвращает **логическое** значение в объекте **System. Boolean** для каждого проверенного подключения. Если тестируется несколько подключений, возвращается массив **логических** значений.

## Примеры

### Пример 1. Отправка эхо-запросов на удаленный компьютер

Этот пример отправляет пакеты эхо-запросов с локального компьютера на компьютер Server01.

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

`Test-Connection` использует параметр **TargetName** для указания компьютера Server01. Параметр **IPv4** указывает протокол для теста.

Ряд объектов **тестконнектионкомманд + пингстатус** отправляется в поток вывода, по одному объекту на ответ проверки связи от целевого компьютера.

### Пример 2. Отправка эхо-запросов на несколько компьютеров

Этот пример отправляет команды ping с локального компьютера на несколько удаленных компьютеров.

```powershell
Test-Connection -TargetName Server01, Server02, Server12
```

### Пример 3. Использование параметров для настройки команды теста

В этом примере `Test-Connection` для настройки команды используются параметры. Локальный компьютер отправляет тест проверки связи на удаленный компьютер.

```powershell
Test-Connection -TargetName Server01 -Count 3 -Delay 2 -MaxHops 255 -BufferSize 256
```

`Test-Connection` использует параметр **TargetName** для указания Server01. Параметр **Count** указывает три сообщения проверки связи, отправляемые на компьютер Server01 с **задержкой** в 2 секунды.

Эти параметры можно использовать, если ожидается, что ответ на запрос проверки связи займет больше времени, чем обычно, из-за расширенного числа прыжков или состояния сети с высоким трафиком.

### Пример 4. Запуск теста в качестве фонового задания

В этом примере показано, как выполнить `Test-Connection` команду в качестве фонового задания PowerShell.

```powershell
$job = Start-Job -ScriptBlock { Test-Connection -TargetName (Get-Content -Path "Servers.txt") }
$Results = Receive-Job $job -Wait
```

`Start-Job`Команда использует `Test-Connection` командлет для проверки связи между многими компьютерами предприятия.
Значение параметра **TargetName** — это `Get-Content` команда, которая считывает список имен компьютеров из `Servers.txt` файла. Команда использует `Start-Job` командлет для выполнения команды в качестве фонового задания и сохраняет задание в `$job` переменной.

`Receive-Job`Команда будет давать инструкции `-Wait` до тех пор, пока задание не будет завершено, а затем не получит результаты и сохранит их в `$Results` переменной.

### Пример 5. Создание сеанса только в случае успешности проверки соединения

Этот пример создает сеанс на компьютере Server01, только если по крайней мере один из пакетов проверки связи успешно отправлен на компьютер.

```powershell
if (Test-Connection -TargetName Server01 -Quiet) { New-PSSession -ComputerName Server01 }
```

`Test-Connection`Командлет проверяет связь `Server01` с компьютером с указанным параметром **quiet** .
Полученное значение — `$True` при успешном выполнении любой из четырех проверок связи. Если ни одна из проверок связи не выполнена успешно, значение равно `$False` .

Если `Test-Connection` команда возвращает значение `$True` , команда использует `New-PSSession` командлет для создания **сеанса PSSession**.

### Пример 6. Использование параметра Traceroute

Параметр **Traceroute** , введенный в PowerShell 6,0, сопоставляет маршрут между локальным компьютером и удаленным назначением, указанным с помощью параметра **TargetName** .

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

`Test-Connection`Команда вызывается с параметром **Traceroute** . Результаты, являющиеся объектами, выводятся в `[Microsoft.PowerShell.Commands.TestConnectionCommand+TraceStatus]` поток выходных данных **успешного** выполнения.

## PARAMETERS

### — BufferSize

Указывает размер (в байтах) буфера, отправленного с помощью этой команды. Значение по умолчанию: 32.

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

### Повтор

Указывает, что командлет будет постоянно отсылать запросы проверки связи. Этот параметр нельзя использовать с параметром **Count** .

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

### — Количество

Указывает число отправляемых запросов проверки связи. Значение по умолчанию — 4.

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

### -Delay

Задает интервал между проверками связи в секундах.

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

### -Донтфрагмент

Этот параметр задает флаг « **не фрагментировать** » в заголовке IP-адреса. Этот параметр можно использовать с параметром **bufferSize** для проверки размера MTU пути. Дополнительные сведения о пути MTU см. в статье о [поиске пути MTU](https://wikipedia.org/wiki/Path_MTU_Discovery) в Википедии.

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
Parameter Sets: DefaultPing, RepeatPing, TraceRoute
Aliases: Ttl, TimeToLive, Hops

Required: False
Position: Named
Default value: 128 hops in Windows 10
Accept pipeline input: False
Accept wildcard characters: False
```

### — Проверка связи

Вызывает выполнение командлетом проверки связи. Это режим по умолчанию для `Test-Connection` командлета.

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

### -Quiet

Параметр **quiet** возвращает **логическое** значение. Использование этого параметра подавляет все ошибки.

Каждое проверенное соединение возвращает **логическое** значение. Если параметр **TargetName** задает несколько компьютеров, возвращается массив **логических** значений.

Если **Проверка** связи с указанным целевым объектом будет выполнена успешно, `$True` возвращается значение.

Если **все** команды ping для данного целевого объекта завершаются ошибкой, `$False` возвращается значение.

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

Вызывает попытку командлета разрешить DNS-имя целевого объекта. При использовании в сочетании с параметром **Traceroute** имена DNS всех промежуточных узлов также будут извлекаться, если это возможно.

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

**Примечание.** Этот параметр не работает в PowerShell версии 6 и выше.
Предоставление этого параметра не будет влиять на выполнение команды.

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

### -TargetName

Указывает компьютеры для проверки. Введите имена компьютеров или IP-адреса в формате IPv4 или IPv6.

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

Вызывает выполнение командлетом Traceroute теста. При использовании этого параметра командлет возвращает `TestConnectionCommand+TraceStatus` объект.

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

### -Мтусизе

Этот параметр используется для определения размера MTU пути. Командлет возвращает объект **пингрепли # мтусизе** , который содержит размер MTU для пути к целевому объекту. Дополнительные сведения о пути MTU см. в статье о [поиске пути MTU](https://wikipedia.org/wiki/Path_MTU_Discovery) в Википедии.

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

### -TcpPort

Указывает номер порта TCP на целевом объекте, который будет использоваться при проверке подключения TCP. Командлет попытается установить TCP-подключение к указанному порту на целевом объекте.

Если соединение может быть установлено, `$True` будет возвращено.

Если соединение не может быть установлено, `$False` будет возвращено значение.

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

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет

Вы не можете передать входные данные в этот командлет.

## Выходные данные

### Тестконнектионкомманд + Пингстатус, Тестконнектионкомманд + TraceStatus, Boolean, Тестконнектионкомманд + Пингмтустатус

По умолчанию `Test-Connection` возвращает объект **Тестконнектионкомманд + пингстатус** для каждого ответа проверки связи.

Если указать параметр **Traceroute** , командлет вернет объект **тестконнектионкомманд + TraceStatus** для каждого ответа на маршрут.

Если заданы параметры **quiet** или **TcpPort** , то возвращается **логическое** значение. Если тестируется несколько подключений, возвращается массив **логических** значений.

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Restart-Computer](Restart-Computer.md)

[Stop-Computer](Stop-Computer.md)
