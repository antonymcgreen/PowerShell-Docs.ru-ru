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
# Test-Connection

## Краткий обзор
Отправляет пакеты запроса проверки связи ICMP или проверки связи на один или несколько компьютеров.

## SYNTAX

### Default (по умолчанию)

```
Test-Connection [-AsJob] [-DcomAuthentication <AuthenticationLevel>] [-WsmanAuthentication <String>]
 [-Protocol <String>] [-BufferSize <Int32>] [-ComputerName] <String[]> [-Count <Int32>]
 [-Impersonation <ImpersonationLevel>] [-ThrottleLimit <Int32>] [-TimeToLive <Int32>]
 [-Delay <Int32>] [<CommonParameters>]
```

### Источник

```
Test-Connection [-AsJob] [-DcomAuthentication <AuthenticationLevel>] [-WsmanAuthentication <String>]
 [-Protocol <String>] [-BufferSize <Int32>] [-ComputerName] <String[]> [-Count <Int32>]
 [-Credential <PSCredential>] [-Source] <String[]> [-Impersonation <ImpersonationLevel>]
 [-ThrottleLimit <Int32>] [-TimeToLive <Int32>] [-Delay <Int32>] [<CommonParameters>]
```

### Тихий NaN

```
Test-Connection [-DcomAuthentication <AuthenticationLevel>] [-WsmanAuthentication <String>]
 [-Protocol <String>] [-BufferSize <Int32>] [-ComputerName] <String[]> [-Count <Int32>]
 [-Impersonation <ImpersonationLevel>] [-TimeToLive <Int32>] [-Delay <Int32>] [-Quiet]
 [<CommonParameters>]
```

## DESCRIPTION

`Test-Connection`Командлет отправляет пакеты эхо-запросов протокола ICMP (ping) на один или несколько удаленных компьютеров и возвращает ответ на эхо-ответы. С помощью этого командлета можно определить, можно ли связаться с определенным компьютером по IP-сети.

С помощью параметров можно `Test-Connection` указать как отправляющее, так и принимающее компьютеры, чтобы выполнить команду в качестве фонового задания, установить время ожидания и количество проверок связи, а также настроить подключение и проверку подлинности.

В отличие от знакомой команды **ping** , `Test-Connection` возвращает объект **Win32_PingStatus** , который можно исследовать в PowerShell. Параметр **quiet** возвращает **логическое** значение в объекте **System. Boolean** для каждого проверенного подключения. Если тестируется несколько подключений, возвращается массив **логических** значений.

## Примеры

### Пример 1. Отправка эхо-запросов на удаленный компьютер

Этот пример отправляет пакеты эхо-запросов с локального компьютера на компьютер Server01.

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

`Test-Connection` использует параметр **ComputerName** для указания компьютера Server01.

### Пример 2. Отправка эхо-запросов на несколько компьютеров

Этот пример отправляет команды ping с локального компьютера на несколько удаленных компьютеров.

```powershell
Test-Connection -ComputerName Server01, Server02, Server12
```

### Пример 3. Отправка эхо-запросов с нескольких компьютеров на компьютер

В этом примере команды ping отправляются с разных исходных компьютеров на один удаленный компьютер Server01.

```powershell
Test-Connection -Source Server02, Server12, localhost -ComputerName Server01 -Credential Domain01\Admin01
```

`Test-Connection` использует параметр **Credential** для указания учетных данных пользователя, имеющего разрешение на отправку запроса проверки связи с исходных компьютеров. Этот формат команды можно использовать для тестирования задержки подключения из нескольких точек.

### Пример 4. Использование параметров для настройки команды теста

В этом примере `Test-Connection` для настройки команды используются параметры. Локальный компьютер отправляет тест проверки связи на удаленный компьютер.

```powershell
Test-Connection -ComputerName Server01 -Count 3 -Delay 2 -TTL 255 -BufferSize 256 -ThrottleLimit 32
```

`Test-Connection` использует параметр **ComputerName** для указания Server01. Параметр **Count** указывает три сообщения проверки связи, отправляемые на компьютер Server01 с **задержкой** в 2 секунды.

Эти параметры можно использовать, если ожидается, что ответ на запрос проверки связи займет больше времени, чем обычно, из-за расширенного числа прыжков или состояния сети с высоким трафиком.

### Пример 5. выполнение теста в качестве фонового задания

В этом примере показано, как выполнить `Test-Connection` команду в качестве фонового задания PowerShell.

```powershell
$job = Test-Connection -ComputerName (Get-Content Servers.txt) -AsJob
if ($job.JobStateInfo.State -ne "Running") {$Results = Receive-Job $job}
```

`Test-Connection`Команда проверяет связь между многими компьютерами в Организации. Значение параметра **ComputerName** — это `Get-Content` команда, которая считывает список имен компьютеров из `Servers.txt file` . Команда использует параметр **AsJob** для выполнения команды в качестве фонового задания и сохраняет задание в `$job` переменной.

`if`Команда проверяет, что задание еще не выполняется. Если задание не выполняется, `Receive-Job` получает результаты и сохраняет их в `$Results` переменной.

### Пример 6. Проверка связи с удаленным компьютером с учетными данными

Эта команда использует `Test-Connection` командлет для проверки связи с удаленным компьютером.

```powershell
Test-Connection Server55 -Credential Domain55\User01 -Impersonation Identify
```

Команда использует параметр **Credential** , чтобы указать учетную запись пользователя, имеющего разрешение на проверку связи с удаленным компьютером, и параметр **олицетворения** , чтобы изменить уровень олицетворения для **определения** .

### Пример 7. Создание сеанса только в случае успешности проверки соединения

Этот пример создает сеанс на компьютере Server01, только если по крайней мере один из пакетов проверки связи успешно отправлен на компьютер.

```powershell
if (Test-Connection -ComputerName Server01 -Quiet) {New-PSSession Server01}
```

`if`Команда использует `Test-Connection` командлет для проверки связи с компьютером Server01. Команда использует параметр **quiet** , который возвращает **логическое** значение вместо объекта **Win32_PingStatus** . Значение равно, `$True` Если любая из четырех проверок связи успешно выполнена, и в противном случае — `$False` .

Если `Test-Connection` команда возвращает значение `$True` , команда использует `New-PSSession` командлет для создания **сеанса PSSession** .

## PARAMETERS

### -AsJob

Указывает, что этот командлет выполняется как фоновое задание.

Чтобы использовать этот параметр, на локальном и удаленном компьютерах необходимо настроить удаленное взаимодействие, а в Windows Vista и более поздних версиях операционной системы Windows необходимо открыть PowerShell с помощью команды **Запуск от имени администратора** . Дополнительные сведения см. в разделе [about_Remote_Requirements](../microsoft.powershell.core/about/about_remote_requirements.md).

При указании параметра **AsJob** команда немедленно возвращает объект, представляющий фоновое задание. Можно продолжить работу в рамках данного сеанса, пока задание завершается. Задание создается на локальном компьютере, а результаты с удаленных компьютеров автоматически возвращаются на локальный компьютер. Чтобы получить результаты задания, используйте `Receive-Job` командлет.

Дополнительные сведения о фоновых заданиях PowerShell см. в разделе [about_Jobs](../Microsoft.PowerShell.Core/About/about_jobs.md) и [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_remote_jobs.md).

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

### — BufferSize

Указывает размер (в байтах) буфера, отправленного с помощью этой команды. Значение по умолчанию: 32.

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

### -ComputerName

Указывает компьютеры для проверки связи. Введите имена компьютеров или IP-адреса в формате IPv4 или IPv6. Подстановочные знаки не допускаются. Этот параметр обязателен.

Этот параметр не зависит от удаленного взаимодействия PowerShell. Параметр **ComputerName** можно использовать, даже если компьютер не настроен для выполнения удаленных команд.

> [!NOTE]
> Параметр **ComputerName** переименовывается в **TargetName** в PowerShell 6,0 и более поздних версиях.

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

### — Количество

Указывает число отправляемых запросов проверки связи. Значение по умолчанию — 4.

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

### -Credential

Указывает учетную запись, имеющую разрешение на отправку запроса проверки связи с исходного компьютера. Введите имя пользователя, например User01 или Domain01\User01, либо введите объект **PSCredential** , например один из `Get-Credential` командлетов.

Параметр **Credential** допустим, только если в команде используется параметр **Source** . Учетные данные не влияют на конечный компьютер.

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

### -Дкомаусентикатион

Указывает уровень проверки подлинности, используемый этим командлетом с WMI.
`Test-Connection` использует WMI.
Допустимые значения для этого параметра:

- **Default** . Проверка подлинности Windows
- **Нет** . Без проверки подлинности COM
- **Подключитесь** . Проверка подлинности COM на уровне подключения
- **Вызов метода** . Проверка подлинности COM на уровне вызова
- **Пакет** . Проверка подлинности COM на уровне пакета
- **Паккетинтегрити** . Проверка подлинности COM на уровне целостности пакета
- **Паккетприваци** . Проверка подлинности COM уровня конфиденциальности пакета
- **Без изменений** . То же, что и в предыдущей команде

Значение по умолчанию — **Packet** с перечислимым значением **4** . Дополнительные сведения о значениях этого параметра см. в разделе [аусентикатионлевел](/dotnet/api/system.management.authenticationlevel) Enumeration.

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

### -Delay

Задает интервал между проверками связи в секундах.

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

### — Олицетворение

Задает уровень олицетворения, используемый при вызове WMI этим командлетом. `Test-Connection` использует WMI.

Для этого параметра допустимы следующие значения:

- **Default** . Олицетворение по умолчанию.
- **Анонимно** . скрывает удостоверение вызывающей стороны.
- **Выявление** . позволяет объектам запрашивать учетные данные вызывающей стороны.
- **Олицетворять** . позволяет объектам использовать учетные данные вызывающей стороны.

Значение по умолчанию — **impersonate** .

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

### -Protocol

Указывает протокол. Допустимые значения для этого параметра: DCOM и WSMan.

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

### -Quiet

Параметр **quiet** возвращает **логическое** значение в объекте **System. Boolean** . Использование этого параметра подавляет все ошибки.

Каждое проверенное соединение возвращает **логическое** значение. Если параметр **ComputerName** задает несколько компьютеров, возвращается массив **логических** значений.

Если **Проверка** связи выполнена успешно, `$True` возвращается значение.

Если **все** проверки связи завершаются ошибкой, `$False` возвращается значение.

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

### -Source

Указывает имена компьютеров, на которых создается проверка связи. Введите разделенный запятыми список имен компьютеров. По умолчанию это локальный компьютер.

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

### -ThrottleLimit

Указывает максимальное число одновременных подключений, которые можно установить для запуска этой команды.
Если этот параметр не указан или имеет значение 0, используется значение по умолчанию — 32.

Предел регулирования применяется только к текущему командлету, а не к сеансу или компьютеру.

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

### -TimeToLive

Указывает максимальное время, в течение которого пакет может быть перенаправлен. Для каждого прыжка в шлюзах, маршрутизаторов и т. д. значение **TimeToLive** уменьшается на единицу. При нулевом пакете пакет отбрасывается и возвращается ошибка.
В **Windows** значение по умолчанию — **128** . Псевдоним параметра **TimeToLive** — **TTL** .

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

### -Всманаусентикатион

Указывает механизм, используемый для проверки подлинности учетных данных пользователя, когда этот командлет использует протокол WSMan.
Допустимые значения для этого параметра:

- Базовый
- CredSSP
- По умолчанию
- Digest (дайджест)
- Kerberos
- Negotiate —

Значение по умолчанию — Default.

Дополнительные сведения о значениях этого параметра см. в разделе [AuthenticationMechanism enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism?view=powershellsdk-1.1.0).

Внимание! проверка подлинности с помощью поставщика службы безопасности учетных данных (CredSSP), в которой учетные данные пользователя передаются на удаленный компьютер для проверки подлинности, предназначена для команд, требующих проверки подлинности в нескольких ресурсах, например для доступа к удаленной сетевой папке.
Этот механизм повышает риск безопасности удаленной операции.
Если удаленный компьютер скомпрометирован, учетные данные, передаваемые ему, могут использоваться для управления сетевым сеансом.

Этот параметр впервые появился в Windows PowerShell 3.0.

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

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет

Вы не можете передать входные данные в этот командлет.

## Выходные данные

### System. Management. ManagementObject # root\cimv2\ Win32_PingStatus, System. Management. Automation. Ремотингжоб, System. Boolean

Этот командлет возвращает объект задания, если указан параметр **AsJob** .

При указании параметра **quiet** возвращается **логическое** значение. Если тестируется несколько подключений, возвращается массив **логических** значений. В противном случае `Test-Connection` возвращает объект **Win32_PingStatus** для каждой проверки связи.

## ПРИМЕЧАНИЯ

Этот командлет использует класс **Win32_PingStatus** . `Get-WMIObject Win32_PingStatus`Команда эквивалентна `Test-Connection` команде.

Набор **исходных** параметров был представлен в PowerShell 3,0.

## Связанные ссылки

[Add-Computer](Add-Computer.md)

[Restart-Computer](Restart-Computer.md)

[Stop-Computer](Stop-Computer.md)
