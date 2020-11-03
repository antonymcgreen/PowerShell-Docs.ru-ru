---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 12/11/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/receive-pssession?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Receive-PSSession
ms.openlocfilehash: 266c12224ee579add22715f47a9047d400fab255
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "93229874"
---
# Receive-PSSession

## Краткий обзор

Возвращает результаты выполнения команд в отключенных сеансах

## SYNTAX

### Сеанс (значение по умолчанию)

```
Receive-PSSession [-Session] <PSSession> [-OutTarget <OutTarget>] [-JobName <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### Идентификатор

```
Receive-PSSession [-Id] <Int32> [-OutTarget <OutTarget>] [-JobName <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### компутерсессионнаме

```
Receive-PSSession [-ComputerName] <String> [-ApplicationName <String>] [-ConfigurationName <String>]
 -Name <String> [-OutTarget <OutTarget>] [-JobName <String>] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [-Port <Int32>]
 [-UseSSL] [-SessionOption <PSSessionOption>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### компутеринстанцеид

```
Receive-PSSession [-ComputerName] <String> [-ApplicationName <String>] [-ConfigurationName <String>]
 -InstanceId <Guid> [-OutTarget <OutTarget>] [-JobName <String>] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [-Port <Int32>]
 [-UseSSL] [-SessionOption <PSSessionOption>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### коннектионурисессионнаме

```
Receive-PSSession [-ConfigurationName <String>] [-ConnectionUri] <Uri> [-AllowRedirection]
 -Name <String> [-OutTarget <OutTarget>] [-JobName <String>] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [-SessionOption <PSSessionOption>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### коннектионуриинстанцеид

```
Receive-PSSession [-ConfigurationName <String>] [-ConnectionUri] <Uri> [-AllowRedirection]
 -InstanceId <Guid> [-OutTarget <OutTarget>] [-JobName <String>] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [-SessionOption <PSSessionOption>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InstanceId

```
Receive-PSSession [-InstanceId] <Guid> [-OutTarget <OutTarget>] [-JobName <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### SessionName

```
Receive-PSSession [-Name] <String> [-OutTarget <OutTarget>] [-JobName <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

`Receive-PSSession`Командлет возвращает результаты выполнения команд в сеансах PowerShell ( **PSSession** ), которые были отключены. Если сеанс подключен, `Receive-PSSession` получает результаты команд, которые выполнялись в момент отключения сеанса. Если сеанс по-прежнему отключен, `Receive-PSSession` подключается к сеансу, возобновляет все команды, которые были приостановлены, и возвращает результаты команд, выполняемых в сеансе.

Этот командлет появился в PowerShell 3,0.

`Receive-PSSession`В дополнение к команде или вместо нее можно использовать `Connect-PSSession` .
`Receive-PSSession` может подключаться к любому отключенному или повторно подключенному сеансу, который был запущен в других сеансах или на других компьютерах.

`Receive-PSSession` работает с **PSSession** , который был намеренно отключен с помощью `Disconnect-PSSession` командлета или `Invoke-Command` параметра **InDisconnectedSession** . Или непреднамеренное отключение сетевого прерывания.

При использовании `Receive-PSSession` командлета для подключения к сеансу, в котором никакие команды не выполняются или приостановлены, `Receive-PSSession` подключается к сеансу, но не возвращает выходные данные и ошибки.

Дополнительные сведения о функции отключенных сеансов см. в разделе [about_Remote_Disconnected_Sessions](./About/about_Remote_Disconnected_Sessions.md).

В некоторых примерах используется Сплаттинг для уменьшения длины строки и улучшения удобочитаемости. Дополнительные сведения см. в разделе [about_Splatting](./About/about_Splatting.md).

## Примеры

### Пример 1. подключение к PSSession

Этот пример подключается к сеансу на удаленном компьютере и получает результаты выполнения команд в сеансе.

```powershell
Receive-PSSession -ComputerName Server01 -Name ITTask
```

`Receive-PSSession`Указывает удаленный компьютер с параметром **ComputerName** . Параметр **Name** определяет сеанс иттаск на компьютере Server01. В этом примере получаются результаты команд, которые были запущены в сеансе Иттаск.

Так как команда не использует параметр **Target** , результаты отображаются в командной строке.

### Пример 2. получение результатов всех команд в отключенных сеансах

Этот пример возвращает результаты всех команд, выполняющихся во всех отключенных сеансах на двух удаленных компьютерах.

Если какой либо сеанс не был отключен или не выполнял команды, `Receive-PSSession` не подключается к сеансу и не возвращает никаких выходных данных или ошибок.

```powershell
Get-PSSession -ComputerName Server01, Server02 | Receive-PSSession
```

`Get-PSSession` задает удаленные компьютеры с помощью параметра **ComputerName** . Объекты отправляются по конвейеру в `Receive-PSSession` .

### Пример 3. получение результатов сценария, выполняемого в сеансе

В этом примере используется `Receive-PSSession` командлет для получения результатов сценария, который был запущен в сеансе удаленного компьютера.

```powershell
$parms = @{
  ComputerName = "Server01"
  Name = "ITTask"
  OutTarget = "Job"
  JobName = "ITTaskJob01"
  Credential = "Domain01\Admin01"
}
Receive-PSSession @parms
```

```Output
Id     Name            State         HasMoreData     Location
--     ----            -----         -----------     --------
16     ITTaskJob01     Running       True            Server01
```

Команда использует параметры **ComputerName** и **Name** для идентификации отключенного сеанса.
Он использует параметр **Target** со значением задания для направления `Receive-PSSession` возврата результатов в виде задания. Параметр **JobName** указывает имя задания в повторно подключенном сеансе.
Параметр **Credential** выполняет команду, `Receive-PSSession` используя разрешения администратора домена.

Выходные данные показывают, что `Receive-PSSession` результаты возвращались в виде задания в текущем сеансе. Чтобы получить результаты задания, используйте команду. `Receive-Job`

### Пример 4. получение результатов после сбоя сети

В этом примере используется `Receive-PSSession` командлет для получения результатов задания после того, как сетевой сбой прерывает соединение с сеансом. PowerShell автоматически пытается повторно подключиться к сеансу раз в секунду в течение следующих четырех минут и отменяет усилия только в случае сбоя всех попыток в течение четырех минут.

```
PS> $s = New-PSSession -ComputerName Server01 -Name AD -ConfigurationName ADEndpoint
PS> $s

Id  Name   ComputerName    State        ConfigurationName     Availability
--  ----   ------------    -----        -----------------     ------------
8   AD      Server01       Opened       ADEndpoint               Available


PS> Invoke-Command -Session $s -FilePath \\Server12\Scripts\SharedScripts\New-ADResolve.ps1

Running "New-ADResolve.ps1"

# Network outage
# Restart local computer
# Network access is not re-established within 4 minutes


PS> Get-PSSession -ComputerName Server01

Id  Name   ComputerName    State          ConfigurationName      Availability
--  ----   ------------    -----          -----------------      ------------
1  Backup  Server01        Disconnected   Microsoft.PowerShell           None
8  AD      Server01        Disconnected   ADEndpoint                     None


PS> Receive-PSSession -ComputerName Server01 -Name AD -OutTarget Job -JobName AD

Job Id   Name      State         HasMoreData     Location
--       ----      -----         -----------     --------
16       ADJob     Running       True            Server01


PS> Get-PSSession -ComputerName Server01

Id  Name    ComputerName    State         ConfigurationName     Availability
--  ----    ------------    -----         -----------------     ------------
1  Backup   Server01        Disconnected  Microsoft.PowerShell          Busy
8  AD       Server01        Opened        ADEndpoint               Available
```

`New-PSSession`Командлет создает сеанс на компьютере Server01 и сохраняет сеанс в `$s` переменной. `$s`Переменная показывает, что **состояние** открыто и доступна **доступность** . Эти значения указывают, что вы подключены к сеансу и можете выполнять команды в сеансе.

`Invoke-Command`Командлет запускает скрипт в сеансе в `$s` переменной. Скрипт начинает выполняться и возвращает данные, но из-за сбоя сети сеанс прерывается. Пользователю необходимо завершить сеанс и перезагрузить локальный компьютер.

При перезапуске компьютера пользователь запускает PowerShell и выполняет `Get-PSSession` команду для получения сеансов на компьютере Server01. В выходных данных показано, что сеанс **AD** по-прежнему существует на компьютере Server01. **Состояние** указывает на то, что сеанс **AD** отключен. Значение **доступности** None указывает, что сеанс не подключен ни к одному из клиентских сеансов.

`Receive-PSSession`Командлет повторно подключится к сеансу **AD** и получит результаты сценария, который выполнялся в сеансе. Команда использует параметр **Target** для запроса результатов в задании с именем **аджоб**. Команда возвращает объект задания, и выходные данные указывают на то, что сценарий все еще выполняется.

`Get-PSSession`Командлет используется для проверки состояния задания. Выходные данные подтверждают, что `Receive-PSSession` командлет повторно подключен к сеансу **AD** , который теперь открыт и доступен для команд. Скрипт возобновил выполнение и получает результаты скрипта.

### Пример 5. Повторное подключение к отключенным сеансам

В этом примере `Receive-PSSession` командлет используется для повторного подключения к сеансам, которые были намеренно отключены, и получения результатов заданий, которые были запущены в сеансах.

```
PS> $parms = @{
      InDisconnectedSession = $True
      ComputerName = "Server01", "Server02", "Server30"
      FilePath = "\\Server12\Scripts\SharedScripts\Get-BugStatus.ps1"
      Name = "BugStatus"
      SessionOption = @{IdleTimeout = 86400000}
      ConfigurationName = "ITTasks"
    }
PS> Invoke-Command @parms
PS> Exit


PS> $s = Get-PSSession -ComputerName Server01, Server02, Server30 -Name BugStatus
PS> $s

Id  Name   ComputerName    State         ConfigurationName     Availability
--  ----   ------------    -----         -----------------     ------------
1  ITTask  Server01        Disconnected  ITTasks                       None
8  ITTask  Server02        Disconnected  ITTasks                       None
2  ITTask  Server30        Disconnected  ITTasks                       None


PS> $Results = Receive-PSSession -Session $s
PS> $s

Id  Name   ComputerName    State         ConfigurationName     Availability
--  ----   ------------    -----         -----------------     ------------
1  ITTask  Server01        Opened        ITTasks                  Available
8  ITTask  Server02        Opened        ITTasks                  Available
2  ITTask  Server30        Opened        ITTasks                  Available


PS> $Results

Bug Report - Domain 01
----------------------
ComputerName          BugCount          LastUpdated
--------------        ---------         ------------
Server01              121               Friday, December 30, 2011 5:03:34 PM
```

`Invoke-Command`Командлет запускает сценарий на трех удаленных компьютерах. Поскольку сценарий собирает и суммирует данные из нескольких баз данных, они часто занимают длительное время для завершения сценария. Команда использует параметр **InDisconnectedSession** , который запускает скрипты, а затем сразу же отключает сеансы. Параметр **SessionOption** расширяет значение **IdleTimeout** в отключенном сеансе. Отключенные сеансы считаются неактивными с момента отключения. Важно установить тайм-аут простоя для достаточного времени, чтобы команды могли быть выполнены и можно было заново подключиться к сеансу. Параметр **IdleTimeout** можно задать только при создании **сеанса PSSession** и изменить его только при отключении от него. Нельзя изменить значение **IdleTimeout** при подключении к **сеансу PSSession** или получении его результатов. После выполнения команды пользователь выходит из PowerShell и закрывает компьютер.

На следующий день пользователь возобновляет работу с Windows, запускает PowerShell и использует `Get-PSSession` для получения сеансов, в которых выполнялись сценарии. Команда определяет сеансы по имени компьютера, имени сеанса, имени конфигурации сеанса и сохраняет сеансы в `$s` переменной. Значение `$s` переменной отображается и показывает, что сеансы отключены, но не заняты.

`Receive-PSSession`Командлет подключается к сеансам в `$s` переменной и получает их результаты.
Команда сохраняет результаты в `$Results` переменной. `$s`Переменная отображается и показывает, что сеансы подключены и доступны для команд.

Результат выполнения скрипта в этой `$Results` переменной отображается в консоли PowerShell. В случае непредвиденных результатов пользователь может выполнять команды в сеансах, чтобы исследовать основную причину.

### Пример 6. выполнение задания в отключенном сеансе

В этом примере показано, что происходит с заданием, которое выполняется в отключенном сеансе.

```
PS> $s = New-PSSession -ComputerName Server01 -Name Test
PS> $j = Invoke-Command -Session $s { 1..1500 | Foreach-Object {"Return $_"; sleep 30}} -AsJob
PS> $j

Id     Name           State         HasMoreData     Location
--     ----           -----         -----------     --------
16     Job1           Running       True            Server01


PS> $s | Disconnect-PSSession

Id Name   ComputerName    State         ConfigurationName     Availability
-- ----   ------------    -----         -----------------     ------------
1  Test   Server01        Disconnected  Microsoft.PowerShell          None


PS> $j

Id     Name           State         HasMoreData     Location
--     ----           -----         -----------     --------
16     Job1           Disconnected  True            Server01


PS> Receive-Job $j -Keep

Return 1
Return 2


PS> $s2 = Connect-PSSession -ComputerName Server01 -Name Test
PS> $j2 = Receive-PSSession -ComputerName Server01 -Name Test
PS> Receive-Job $j

Return 3
Return 4
```

`New-PSSession`Командлет создает сеанс тестирования на компьютере Server01. Сеанс сохраняется в переменную `$s`.

`Invoke-Command`Командлет выполняет команду в сеансе в `$s` переменной. Команда использует параметр **AsJob** для выполнения команды в качестве задания и создает объект задания в текущем сеансе.
Команда возвращает объект задания, сохраненный в `$j` переменной. `$j`Переменная отображает объект задания.

Объект сеанса в `$s` переменной отправляется по конвейеру в `Disconnect-PSSession` , а сеанс отключается.

`$j`Переменная отображается и показывает результат отключения объекта задания в `$j` переменной. Состояние задания меняется на "Отключено".

`Receive-Job`Выполняется в задании в `$j` переменной. Выходные данные показывают, что задание приступило к возврату выходных данных до отключения сеанса и задания.

`Connect-PSSession`Командлет выполняется в том же сеансе клиента. Команда повторно подключится к сеансу тестирования на компьютере Server01 и сохранит сеанс в `$s2` переменной.

`Receive-PSSession`Командлет возвращает результаты задания, которое было запущено в сеансе. Поскольку команда выполняется в том же сеансе, `Receive-PSSession` по умолчанию возвращает результаты в виде задания и повторно использует тот же объект задания. Команда сохраняет задание в `$j2` переменной. `Receive-Job`Командлет возвращает результаты задания в `$j` переменной.

## PARAMETERS

### -AllowRedirection

Указывает, что этот командлет разрешает перенаправление этого соединения в альтернативный универсальный код ресурса (URI).

При использовании параметра **ConnectionURI** удаленный компьютер может вернуть инструкцию для перенаправления на другой URI. По умолчанию PowerShell не перенаправляет соединения, но можно использовать этот параметр, чтобы разрешить ему перенаправить подключение.

Можно также ограничить количество перенаправлений соединение, изменив значение параметра сеанса **MaximumConnectionRedirectionCount**. Используйте параметр **максимумредиректион** `New-PSSessionOption` командлета или задайте свойство **MaximumConnectionRedirectionCount** `$PSSessionOption` переменной предпочтений. Значение по умолчанию — 5.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ConnectionUriSessionName, ConnectionUriInstanceId
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationName

Указывает приложение. Этот командлет подключается только к сеансам, использующим указанное приложение.

Введите сегмент имени приложения URI подключения. Например, в следующем URI соединения WSMan — это имя приложения: `http://localhost:5985/WSMAN` .

Имя приложения сеанса хранится в свойстве сеанса **Runspace.ConnectionInfo.AppName**.

Значение параметра используется для выбора и фильтрации сеансов. Оно не изменяет приложение, которое использует сеанс.

```yaml
Type: System.String
Parameter Sets: ComputerSessionName, ComputerInstanceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Authentication

Указывает механизм, используемый для проверки подлинности учетных данных пользователя в команде для повторного подключения к отключенному сеансу. Допустимые значения для этого параметра:

- По умолчанию
- Базовый
- CredSSP
- Digest (дайджест)
- Kerberos
- Согласование
- NegotiateWithImplicitCredential

Значение по умолчанию — Default.

Дополнительные сведения о значениях этого параметра см. в разделе [AuthenticationMechanism enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).

> [!CAUTION]
> Проверка подлинности с помощью поставщика поддержки безопасности учетных данных (CredSSP), в которой учетные данные пользователя передаются на удаленный компьютер для проверки подлинности, предназначена для команд, требующих проверки подлинности в нескольких ресурсах, таких как доступ к удаленной сетевой папке. Этот механизм повышает риск безопасности удаленной операции. Если удаленный компьютер скомпрометирован, учетные данные, передаваемые ему, могут использоваться для управления сетевым сеансом.

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ComputerSessionName, ComputerInstanceId, ConnectionUriSessionName, ConnectionUriInstanceId
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### -CertificateThumbprint

Задает цифровой сертификат с открытым ключом (X509) учетной записи пользователя, который располагает разрешением для подключения к отсоединенному сеансу. Введите отпечаток сертификата.

Сертификаты используются при проверке подлинности на основе сертификата клиента. Сертификаты могут сопоставляться только с локальными учетными записями пользователей и не работать с учетными записями домена.

Чтобы получить отпечаток сертификата, используйте `Get-Item` `Get-ChildItem` команду или на диске PowerShell `Cert:` .

```yaml
Type: System.String
Parameter Sets: ComputerSessionName, ComputerInstanceId, ConnectionUriSessionName, ConnectionUriInstanceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Указывает компьютер, на котором хранится отключенный сеанс. Сеансы хранятся на компьютере, который находится на стороне сервера или получает окончание соединения. По умолчанию это локальный компьютер.

Введите имя NetBIOS, IP-адрес или полное доменное имя (FQDN) одного компьютера.
Подстановочные знаки не допускаются. Чтобы указать локальный компьютер, введите имя компьютера, точку ( `.` ), `$env:COMPUTERNAME` или localhost.

```yaml
Type: System.String
Parameter Sets: ComputerSessionName, ComputerInstanceId
Aliases: Cn

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConfigurationName

Указывает имя конфигурации сеанса. Этот командлет подключается только к сеансам, использующим указанную конфигурацию сеанса.

Введите имя конфигурации или полное имя ресурса (URI) для конфигурации сеанса. Если указать только имя конфигурации, добавляется следующая схема URI:

`http://schemas.microsoft.com/powershell`.

Имя конфигурации сеанса хранится в свойстве сеанса **ConfigurationName**.

Значение параметра используется для выбора и фильтрации сеансов. Он не изменяет конфигурацию сеанса, используемую сеансом.

Дополнительные сведения о конфигурациях сеансов см. в разделе [about_Session_Configurations](./About/about_Session_Configurations.md).

```yaml
Type: System.String
Parameter Sets: ComputerSessionName, ComputerInstanceId, ConnectionUriSessionName, ConnectionUriInstanceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConnectionUri

Указывает универсальный код ресурса (URI), определяющий конечную точку подключения, используемую для повторного подключения к отключенному сеансу.

Значение URI должно быть указано полностью. Формат строки выглядит следующим образом:

`<Transport>://<ComputerName>:<Port>/<ApplicationName>`

Значение по умолчанию определяется следующим образом.

`http://localhost:5985/WSMAN`

Если не указать URI соединения, можно использовать параметры **UseSSL** , **ComputerName** , **Port** и **applicationName** , чтобы указать значения универсального кода ресурса (URI) соединения.

Допустимые значения для сегмента **Transport** идентификатора URI: HTTP и HTTPS. Если указать универсальный код ресурса (URI) соединения с сегментом транспорта, но не указывать порт, то сеанс будет создан с использованием стандартных портов: 80 для HTTP и 443 для HTTPS. Чтобы использовать порты по умолчанию для удаленного взаимодействия PowerShell, укажите порт 5985 для HTTP или 5986 для HTTPS.

Если конечный компьютер перенаправляет подключение к другому универсальному коду ресурса (URI), PowerShell предотвращает перенаправление, если в команде не используется параметр **AllowRedirection** .

```yaml
Type: System.Uri
Parameter Sets: ConnectionUriSessionName, ConnectionUriInstanceId
Aliases: URI, CU

Required: True
Position: 0
Default value: http://localhost:5985/WSMAN
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Credential

Указывает учетную запись пользователя с разрешением на подключение к отсоединенному сеансу. По умолчанию используется текущий пользователь.

Введите имя пользователя, например **User01** или **Domain01\User01** , либо введите объект **PSCredential** , созданный `Get-Credential` командлетом. Если ввести имя пользователя, будет предложено ввести пароль.

Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).

> [!NOTE]
> Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerSessionName, ComputerInstanceId, ConnectionUriSessionName, ConnectionUriInstanceId
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id

Указывает идентификатор отключенного сеанса. Параметр **ID** работает только в том случае, если отключенный сеанс ранее был подключен к текущему сеансу.

Этот параметр является допустимым, но неэффективным, если сеанс хранится на локальном компьютере, но не был подключен к текущему сеансу.

```yaml
Type: System.Int32
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -InstanceId

Указывает идентификатор экземпляра отключенного сеанса. Идентификатор экземпляра — это идентификатор GUID, который однозначно определяет **сеанс PSSession** на локальном или удаленном компьютере. Идентификатор экземпляра хранится в свойстве **InstanceId** **сеанса PSSession**.

```yaml
Type: System.Guid
Parameter Sets: ComputerInstanceId, ConnectionUriInstanceId, InstanceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobName

Указывает понятное имя для задания, которое `Receive-PSSession` возвращает.

`Receive-PSSession` Возвращает задание, если в текущем сеансе было запущено значение параметра **Target** или задание, запущенное в отключенном сеансе.

Если задание, запущенное в отключенном сеансе, было запущено в текущем сеансе, PowerShell повторно использует исходный объект задания в сеансе и игнорирует значение параметра **JobName** .

Если задание, запущенное в отключенном сеансе, было запущено в другом сеансе, PowerShell создает новый объект задания. При этом используется имя по умолчанию, но его можно изменить с помощью этого параметра.

Если значение по умолчанию или явное значение параметра **Target** не задано, команда будет выполнена успешно, но параметр **JobName** не будет действовать.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Указывает понятное имя отключенного сеанса.

```yaml
Type: System.String
Parameter Sets: ComputerSessionName, ConnectionUriSessionName, SessionName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Назначение

Определяет, как возвращаются результаты сеанса. Допустимые значения для этого параметра:

- **Задание**. асинхронно возвращает результаты в объекте задания. С помощью параметра **JobName** можно указать имя задания (имя по умолчанию или новое).
- **Узел**. возвращает результаты из командной строки (синхронно). Если команда возобновляется или результаты состоят из большого числа объектов, ответ может быть отложен.

Значение **параметра по** умолчанию — Host. Если команда, полученная в отключенном сеансе, была запущена в текущем сеансе, **значением параметра по** умолчанию является форма, в которой была запущена команда. Если команда была запущена как задание, по умолчанию она возвращается в виде задания. В противном случае по умолчанию возвращается в ведущее приложение.

Как правило, основная программа отображает возвращаемые объекты в командной строке без задержки, но это не всегда так.

```yaml
Type: Microsoft.PowerShell.Commands.OutTarget
Parameter Sets: (All)
Aliases:
Accepted values: Default, Host, Job

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Port

Указывает сетевой порт удаленного компьютера, используемый для повторного подключения к сеансу. Для подключения к удаленному компьютеру он должен прослушивать порт, используемый подключением. Порты по умолчанию — 5985, то есть порт WinRM для HTTP, а 5986 — порт WinRM для HTTPS.

Перед использованием альтернативного порта необходимо настроить прослушиватель WinRM на удаленном компьютере для прослушивания этого порта. Чтобы настроить прослушиватель, введите следующие две команды в командной строке PowerShell:

`Remove-Item -Path WSMan:\Localhost\listener\listener* -Recurse`

`New-Item -Path WSMan:\Localhost\listener -Transport http -Address * -Port \<port-number\>`

Не используйте параметр **Port** , если он не требуется. Порт, заданный в команде, применяется ко всем компьютерам или сеансам, на которых выполняется команда. Альтернативный порт может помешать выполнению команды на всех компьютерах.

```yaml
Type: System.Int32
Parameter Sets: ComputerSessionName, ComputerInstanceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Session

Указывает отключенный сеанс. Введите переменную, содержащую **PSSession** или команду, которая создает или получает **сеанс PSSession** , например `Get-PSSession` команду.

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: Session
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -SessionOption

Задает дополнительные параметры для сеанса. Введите объект **SessionOption** , например, созданный с помощью `New-PSSessionOption` командлета, или хэш-таблицу, в которой ключи являются именами параметров сеанса, а значения — значениями параметров сеанса.

Значения по умолчанию для параметров определяются значением `$PSSessionOption` привилегированной переменной, если оно задано. В противном случае значения по умолчанию задаются параметрами, указанными в конфигурации сеанса.

Значения параметров сеанса имеют приоритет над значениями по умолчанию для сеансов, заданных в `$PSSessionOption` переменной предпочтений и в конфигурации сеанса. Однако они не имеют приоритета над максимальными значениями, квотами или ограничениями, установленными в конфигурации сеанса.

Описание параметров сеанса, содержащих значения по умолчанию, см. в разделе `New-PSSessionOption` . Дополнительные сведения о переменной настройки **$PSSessionOption** см. в разделе [about_Preference_Variables](./About/about_Preference_Variables.md). Дополнительные сведения о конфигурациях сеансов см. в разделе [about_Session_Configurations](./About/about_Session_Configurations.md).

```yaml
Type: System.Management.Automation.Remoting.PSSessionOption
Parameter Sets: ComputerSessionName, ComputerInstanceId, ConnectionUriSessionName, ConnectionUriInstanceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseSSL

Указывает, что этот командлет использует протокол SSL (SSL) для подключения к отключенному сеансу. По умолчанию протокол SSL не используется.

WS-Management шифрует все содержимое PowerShell, передаваемое по сети. **UseSSL** обеспечивает дополнительную защиту за счет передачи данных по защищенному HTTPS-подключению вместо HTTP-подключения.

Если вы используете этот параметр и протокол SSL недоступен в порте, используемом для команды, команда завершается ошибкой.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerSessionName, ComputerInstanceId
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

Запрос подтверждения перед выполнением командлета.

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

### -WhatIf

Показывает, что произойдет при запуске командлета. Командлет не выполняется.

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

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.Management.Automation.Runspaces.PSSession

К этому командлету можно передать объекты сеанса, например объекты, возвращаемые `Get-PSSession` командлетом.

### System.Int32

В этот командлет можно передать идентификаторы сеансов.

### System.Guid

Идентификаторы экземпляров сеансов этого командлета можно передать по конвейеру.

### System.String

К этому командлету можно передать имена сеансов.

## Выходные данные

### System. Management. Automation. job или PSObject

Этот командлет возвращает результаты команд, которые выполнялись в отключенном сеансе, если таковые имеются. Если значение или значение по умолчанию параметра для **целевого объекта** задано как Job, `Receive-PSSession` возвращает объект задания. В противном случае возвращаются объекты, представляющие результаты выполнения этой команды.

## ПРИМЕЧАНИЯ

`Receive-PSSession` Возвращает результаты только из сеансов, которые были отключены. Только сеансы, подключенные к или завершенные на компьютерах, на которых выполняется PowerShell 3,0 или более поздней версии, могут быть отключены и повторно подключены.

Если команды, которые выполнялись в отключенном сеансе, не создавали результатов или если результаты уже были возвращены другому сеансу, `Receive-PSSession` не создает никаких выходных данных.

Режим буферизации вывода сеанса определяет, как команды в сеансе управляют выходными данными при отключении сеанса. Если параметр **аутпутбуфферингмоде** сеанса имеет значение Drop и выходной буфер заполнен, команда начинает удалять выходные данные. `Receive-PSSession` не удается восстановить эти выходные данные. Дополнительные сведения о параметре режим буферизации вывода см. в статьях справки для командлетов [New-PSSessionOption](New-PSSessionOption.md) и [New-пстранспортоптион](New-PSTransportOption.md) .

Нельзя изменить значение времени ожидания простоя **сеанса PSSession** при подключении к **сеансу PSSession** или получению результатов. Параметр **SessionOption** `Receive-PSSession` принимает объект **SessionOption** , имеющий значение **IdleTimeout** . Однако значение **IdleTimeout** объекта **SessionOption** и значение **IdleTimeout** `$PSSessionOption` переменной не учитывается при подключении к **PSSession** или получению результатов.

- Можно задать и изменить время ожидания простоя **сеанса PSSession** при создании **сеанса PSSession** с помощью `New-PSSession` `Invoke-Command` командлетов или, а также при отключении от **сеанса PSSession**.
- Свойство **IdleTimeout** в **PSSession** очень важно для отключенных сеансов, так как оно определяет, как долго отключенный сеанс сохраняется на удаленном компьютере. Отключенные сеансы считаются находящимися в режиме простоя с момента их отключения, даже если в них выполняются команды.

Если запустить задание запуска в удаленном сеансе с помощью параметра **AsJob** `Invoke-Command` командлета, то объект задания создается в текущем сеансе, даже если задание выполняется в удаленном сеансе. При отключении удаленного сеанса объект задания в текущем сеансе отключается от задания. Объект задания содержит возвращенные результаты, но не получает новые результаты из задания в отключенном сеансе.

Если другой клиент подключается к сеансу, содержащему выполняемое задание, то результаты, которые были переданы исходному объекту задания в исходном сеансе, не будут доступны во вновь подключенном сеансе. После повторного подключения сеанса доступны только те результаты, которые не были доставлены в исходный объект задания.

Аналогично, если запустить сценарий в сеансе, а затем отключиться от него, все результаты, которые сценарий доставляет в сеанс до отключения, не будут доступны другому клиенту, который подключается к сеансу.

Чтобы предотвратить потери данных в сеансах, которые планируется отключить, используйте параметр **InDisconnectedSession** `Invoke-Command` командлета. Поскольку этот параметр запрещает возвращать результаты текущему сеансу, после повторного подключения сеанса доступны все результаты.

Можно также предотвратить потери данных с помощью `Invoke-Command` командлета для выполнения `Start-Job` команды в удаленном сеансе. В этом случае объект задания создается в удаленном сеансе. `Receive-PSSession`Для получения результатов задания нельзя использовать командлет. Вместо этого используйте `Connect-PSSession` командлет для подключения к сеансу, а затем используйте `Invoke-Command` командлет для выполнения `Receive-Job` команды в сеансе.

Если сеанс, содержащий выполняющееся задание, отключен, а затем повторно подключен, исходный объект задания используется повторно только в том случае, если задание отключено и повторно подключено к тому же сеансу, а команда для повторного подключения не указывает новое имя задания. Если сеанс повторно подключается к другому клиентскому сеансу или указано новое имя задания, PowerShell создает новый объект задания для нового сеанса.

При отключении **PSSession** состояние сеанса отключается, а уровень доступности — нет.

- Значение свойства **State** определяется текущим сеансом. Значение disconnected означает, что **сеанс PSSession** не подключен к текущему сеансу. Однако это не означает, что **сеанс PSSession** отключен от всех сеансов. Он может быть подключен к другому сеансу.
  Определить возможность подключения или повторного подключения к сеансу позволяет свойство **Availability**.
- Если свойство **Availability** имеет значение None, подключиться к сеансу можно. Значение занято указывает, что невозможно подключиться к сеансу **PSSession** , так как он подключен к другому сеансу.
- Дополнительные сведения о значениях свойства **State** в сеансах см. в разделе [РУНСПАЦЕСТАТЕ](/dotnet/api/system.management.automation.runspaces.runspacestate) в библиотеке MSDN.
- Дополнительные сведения о значениях свойства **Availability** сеансов см. в разделе [рунспацеаваилабилити](/dotnet/api/system.management.automation.runspaces.runspaceavailability).

## Связанные ссылки

[about_PSSessions](./About/about_PSSessions.md)

[about_Remote](./About/about_Remote.md)

[about_Remote_Disconnected_Sessions](./About/about_Remote_Disconnected_Sessions.md)

[about_Session_Configurations](./About/about_Session_Configurations.md)

[Connect-PSSession](Connect-PSSession.md)

[Enter-PSSession](Enter-PSSession.md)

[Exit-PSSession;](Exit-PSSession.md)

[Get-PSSession](Get-PSSession.md)

[Invoke-Command](Invoke-Command.md)

[New-PSSession](New-PSSession.md)

[New-PSSessionOption](New-PSSessionOption.md)

[New-PSTransportOption](New-PSTransportOption.md)

[Remove-PSSession](Remove-PSSession.md)
