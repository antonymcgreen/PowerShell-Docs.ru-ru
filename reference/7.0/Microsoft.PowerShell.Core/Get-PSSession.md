---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 5/15/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-pssession?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSSession
ms.openlocfilehash: 2f233dad23a8dead5e6fe0d072d71f0e2528551d
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "93230010"
---
# Get-PSSession

## Краткий обзор
Получает сеансы PowerShell на локальных и удаленных компьютерах.

## SYNTAX

### Имя (по умолчанию)

```
Get-PSSession [-Name <String[]>] [<CommonParameters>]
```

### ИмяКомпьютера

```
Get-PSSession [-ComputerName] <String[]> [-ApplicationName <String>] [-ConfigurationName <String>]
 [-Name <String[]>] [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [-Port <Int32>] [-UseSSL] [-ThrottleLimit <Int32>]
 [-State <SessionFilterState>] [-SessionOption <PSSessionOption>] [<CommonParameters>]
```

### компутеринстанцеид

```
Get-PSSession [-ComputerName] <String[]> [-ApplicationName <String>] [-ConfigurationName <String>]
 -InstanceId <Guid[]> [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [-Port <Int32>] [-UseSSL] [-ThrottleLimit <Int32>]
 [-State <SessionFilterState>] [-SessionOption <PSSessionOption>] [<CommonParameters>]
```

### ConnectionUri

```
Get-PSSession [-ConnectionUri] <Uri[]> [-ConfigurationName <String>] [-AllowRedirection] [-Name <String[]>]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [-ThrottleLimit <Int32>] [-State <SessionFilterState>] [-SessionOption <PSSessionOption>] [<CommonParameters>]
```

### коннектионуриинстанцеид

```
Get-PSSession [-ConnectionUri] <Uri[]> [-ConfigurationName <String>] [-AllowRedirection] -InstanceId <Guid[]>
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [-ThrottleLimit <Int32>] [-State <SessionFilterState>] [-SessionOption <PSSessionOption>] [<CommonParameters>]
```

### вмнамеинстанцеид

```
Get-PSSession [-ConfigurationName <String>] -InstanceId <Guid[]> [-State <SessionFilterState>]
 -VMName <String[]> [<CommonParameters>]
```

### ContainerId

```
Get-PSSession [-ConfigurationName <String>] [-Name <String[]>] [-State <SessionFilterState>]
 -ContainerId <String[]> [<CommonParameters>]
```

### контаинеридинстанцеид

```
Get-PSSession [-ConfigurationName <String>] -InstanceId <Guid[]> [-State <SessionFilterState>]
 -ContainerId <String[]> [<CommonParameters>]
```

### VMId

```
Get-PSSession [-ConfigurationName <String>] [-Name <String[]>] [-State <SessionFilterState>] -VMId <Guid[]>
 [<CommonParameters>]
```

### вмидинстанцеид

```
Get-PSSession [-ConfigurationName <String>] -InstanceId <Guid[]> [-State <SessionFilterState>] -VMId <Guid[]>
 [<CommonParameters>]
```

### VMName

```
Get-PSSession [-ConfigurationName <String>] [-Name <String[]>] [-State <SessionFilterState>] -VMName <String[]>
 [<CommonParameters>]
```

### InstanceId

```
Get-PSSession [-InstanceId <Guid[]>] [<CommonParameters>]
```

### Идентификатор

```
Get-PSSession [-Id] <Int32[]> [<CommonParameters>]
```

## DESCRIPTION

`Get-PSSession`Командлет получает управляемые пользователем сеансы PowerShell ( **PSSession** ) на локальных и удаленных компьютерах.

Начиная с Windows PowerShell 3,0, сеансы хранятся на компьютерах на удаленной стороне каждого подключения. Параметры **ComputerName** или **ConnectionURI** можно использовать `Get-PSSession` для получения сеансов, подключающихся к локальному компьютеру или удаленным компьютерам, даже если они не были созданы в текущем сеансе.

Без параметров `Get-PSSession` возвращает все сеансы, которые были созданы в текущем сеансе.

Используйте параметры фильтрации, в том числе **Name** , **ID** , **InstanceId** , **State** , **applicationName** и **configurationName** , чтобы выбрать из сеансов, которые `Get-PSSession` возвращает.

Используйте оставшиеся параметры для настройки временного подключения, в котором `Get-PSSession` выполняется команда при использовании параметров **ComputerName** или **ConnectionURI** .

Примечание. в Windows PowerShell 2,0 без параметров `Get-PSSession` получает все сеансы, которые были созданы в текущем сеансе. Параметр **ComputerName** получает сеансы, которые были созданы в текущем сеансе и подключаются к указанному компьютеру.

Дополнительные сведения о сеансах PowerShell см. в разделе [about_PSSessions](about/about_PSSessions.md).

## Примеры

### Пример 1. получение сеансов, созданных в текущем сеансе

```powershell
Get-PSSession
```

Эта команда возвращает все **PSSession** , созданные в текущем сеансе. Он не получает **PSSession** , которые были созданы в других сеансах или на других компьютерах, даже если они подключаются к этому компьютеру.

### Пример 2. получение сеансов, подключенных к локальному компьютеру

```powershell
Get-PSSession -ComputerName "localhost"
```

Эта команда возвращает **PSSession** , подключенные к локальному компьютеру. Чтобы указать локальный компьютер, введите имя компьютера, localhost или точку (.)

Эта команда возвращает все сеансы на локальном компьютере, даже если они были созданы в других сеансах или на других компьютерах.

### Пример 3. получение сеансов, подключенных к компьютеру

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

Эта команда возвращает **PSSession** , подключенные к компьютеру Server02.

Эта команда возвращает все сеансы на компьютере Server02, даже если они были созданы в других сеансах или на других компьютерах.

Выходные данные показывают, что два сеансы находятся в отключенном состоянии с доступностью "Занято". Они были созданы в различных сеансах и в настоящее время используются. Сеанс ScheduledJobs, который открыт и доступен, был создан в текущем сеансе.

### Пример 4. Сохранение результатов выполнения этой команды

```powershell
New-PSSession -ComputerName Server01, Server02, Server03
$s1, $s2, $s3 = Get-PSSession
```

В этом примере показано, как сохранить результаты `Get-PSSession` команды в нескольких переменных.

Первая команда использует `New-PSSession` командлет для создания **PSSession** на трех удаленных компьютерах.

Вторая команда использует `Get-PSSession` командлет для получения трех **PSSession** . Затем он сохраняет каждую из **PSSession** в отдельной переменной.

Когда PowerShell назначает массив объектов массиву переменных, он присваивает первому объекту первую переменную, второй объект второй переменной и т. д. Если объектов больше, чем переменных, все оставшиеся объекты назначаются последней переменной в массиве. Если переменных больше, чем объектов, дополнительные переменные не используются.

### Пример 5. Удаление сеанса с помощью идентификатора экземпляра

```powershell
Get-PSSession | Format-Table -Property ComputerName, InstanceID
$s = Get-PSSession -InstanceID a786be29-a6bb-40da-80fb-782c67f7db0f
Remove-PSSession -Session $s
```

В этом примере показано, как получить **PSSession** с помощью идентификатора экземпляра, а затем удалить **PSSession** .

Первая команда получает все **PSSession** , созданные в текущем сеансе. Он отправляет **PSSession** командлету Format-Table, который отображает свойства **ComputerName** и **InstanceId** каждого **сеанса PSSession** .

Вторая команда использует командлет, `Get-PSSession` чтобы получить определенный **сеанс PSSession** и сохранить его в `$s` переменной. Команда использует параметр **InstanceId** для задания **сеанса PSSession** .

Третья команда использует командлет Remove-PSSession для удаления **сеанса PSSession** в `$s` переменной.

### Пример 6. Получение сеанса с определенным именем

Команды в этом примере находят сеанс, имя которого имеет определенный формат, использует конфигурацию сеанса и затем подключается к сеансу. С помощью подобной команды можно найти сеанс, в котором коллега запустил задачу, и подключиться к нему для завершения задачи.

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

Первая команда получает сеансы на удаленных компьютерах Server02 и Server12, имена которых начинаются с Баккупжоб и используют конфигурацию сеанса ITTasks. Команда использует параметр **Name** для указания шаблона имени, а параметр **configurationName** — для указания конфигурации сеанса. Значение параметра **SessionOption** — это хэш-таблица, которая устанавливает для параметра **OperationTimeout** значение 240 000 мс (4 минуты). Этот параметр дает команде больше времени на завершение. Параметры **configurationName** и **SessionOption** используются для настройки временных сеансов, в которых `Get-PSSession` командлет выполняется на каждом компьютере. Выходные данные показывают, что команда возвращает сеанс BackupJob04. Сеанс отключен, а уровень **доступности** равен None, что означает, что он не используется.

Вторая команда использует `Get-PSSession` командлет для перехода к сеансу BackupJob04 и командлету Connect-PSSession для подключения к сеансу. Сеанс сохраняется в переменную $s.

Третья команда получает сеанс в переменной $s. Выходные данные показывают, что `Connect-PSSession` команда выполнена успешно. Сеанс находится в состоянии **Opened** и доступен для использования.

### Пример 7. Получение сеанса с помощью его идентификатора

```powershell
Get-PSSession -Id 2
```

Эта команда получает **сеанс PSSession** с идентификатором 2. Так как значение свойства **ID** уникально только в текущем сеансе, параметр **ID** допустим только для локальных команд.

## PARAMETERS

### -AllowRedirection

Указывает, что этот командлет разрешает перенаправление этого соединения в альтернативный универсальный код ресурса (URI). По умолчанию PowerShell не перенаправляет соединения.

Этот параметр настраивает временное подключение, созданное для выполнения `Get-PSSession` команды с параметром **ConnectionURI** .

Этот параметр впервые появился в Windows PowerShell 3.0.

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

### -ApplicationName

Указывает имя приложения. Этот командлет подключается только к сеансам, использующим указанное приложение.

Введите сегмент имени приложения URI подключения. Например, в следующем URI соединения имя приложения — WSMan: `http://localhost:5985/WSMAN` . Имя приложения сеанса хранится в свойстве сеанса **Runspace.ConnectionInfo.AppName** .

Значение этого параметра используется для выбора и фильтрации сеансов. Оно не изменяет приложение, которое использует сеанс.

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

### -Authentication

Указывает механизм, используемый для проверки подлинности учетных данных для сеанса, в котором `Get-PSSession` выполняется команда.

Этот параметр настраивает временное подключение, созданное для выполнения `Get-PSSession` команды с параметром **ComputerName** или **ConnectionURI** .

Допустимые значения для этого параметра:

- По умолчанию
- Базовый
- CredSSP
- Digest (дайджест)
- Kerberos
- Согласование
- NegotiateWithImplicitCredential.

Значение по умолчанию — Default.

Дополнительные сведения о значениях этого параметра см. в разделе [перечисление AuthenticationMechanism](https://msdn.microsoft.com/library/system.management.automation.runspaces.authenticationmechanism) в библиотеке MSDN.

ВНИМАНИЕ! проверка подлинности поставщика поддержки безопасности учетных данных (CredSSP), в которой учетные данные пользователя передаются на удаленный компьютер для проверки подлинности, предназначена для команд, требующих проверки подлинности в нескольких ресурсах, таких как доступ к удаленной сетевой папке. Этот механизм повышает риск безопасности удаленной операции. Если удаленный компьютер скомпрометирован, учетные данные, передаваемые ему, могут использоваться для управления сетевым сеансом.

Этот параметр впервые появился в Windows PowerShell 3.0.

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

### -CertificateThumbprint

Указывает сертификат цифрового открытого ключа (X509) учетной записи пользователя, имеющей разрешение на создание сеанса, в котором `Get-PSSession` выполняется команда. Введите отпечаток сертификата.

Этот параметр настраивает временное подключение, созданное для выполнения `Get-PSSession` команды с параметром **ComputerName** или **ConnectionURI** .

Сертификаты используются при проверке подлинности на основе сертификата клиента. Они могут сопоставляться только с учетными записями локальных пользователей и не работают с учетными записями доменов.

Чтобы получить отпечаток сертификата, используйте команду Get-Item или Get-ChildItem на диске с сертификатом PowerShell:.

Этот параметр впервые появился в Windows PowerShell 3.0.

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

### -ComputerName

Указывает массив имен компьютеров. Возвращает сеансов, которые подключаются к указанным компьютерам.
Подстановочные знаки не допускаются. Значение по умолчанию отсутствует.

Начиная с Windows PowerShell 3,0, объекты **PSSession** хранятся на компьютерах на удаленной стороне каждого подключения. Чтобы получить сеансы на указанных компьютерах, PowerShell создает временное подключение к каждому компьютеру и выполняет `Get-PSSession` команду.

Введите имя NetBIOS, IP-адрес или полное доменное имя одного или нескольких компьютеров. Чтобы указать локальный компьютер, введите имя компьютера, localhost или точку (.).

Примечание. Этот параметр получает сеансы только с компьютеров, на которых выполняется Windows PowerShell 3,0 или более поздних версий PowerShell. Предыдущие версии не хранят сеансы.

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

### -ConfigurationName

Указывает имя конфигурации. Этот командлет получает только сеансы, в которых используется указанная конфигурация сеанса.

Введите имя конфигурации или полное имя ресурса (URI) для конфигурации сеанса. Если указано только имя конфигурации, в начале добавляется следующий URI схемы: `http://schemas.microsoft.com/powershell` . Имя конфигурации сеанса хранится в свойстве сеанса **ConfigurationName** .

Значение этого параметра используется для выбора и фильтрации сеансов. Оно не изменяет конфигурацию, которую использует сеанс.

Дополнительные сведения о конфигурациях сеансов см. в разделе [about_Session_Configurations](About/about_Session_Configurations.md).

```yaml
Type: System.String
Parameter Sets: ComputerInstanceId, ComputerName, ConnectionUriInstanceId, ConnectionUri, VMNameInstanceId, ContainerId, ContainerIdInstanceId, VMId, VMIdInstanceId, VMName
Aliases:

Required: False
Position: Named
Default value: All sessions
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConnectionUri

Задает универсальный код ресурса (URI), определяющий конечную точку подключения для временного сеанса, в котором `Get-PSSession` выполняется команда. Значение URI должно быть указано полностью.

Этот параметр настраивает временное подключение, созданное для выполнения `Get-PSSession` команды с параметром **ConnectionURI** .

Строки имеют следующий формат:

`<Transport>://<ComputerName>:<Port\>/<ApplicationName>`

Значение по умолчанию: `http://localhost:5985/WSMAN` .

Если не указать **ConnectionURI** , можно использовать параметры **UseSSL** , **ComputerName** , **Port** и **applicationName** , чтобы указать значения **ConnectionURI** . Допустимые значения для сегмента транспорта URI — HTTP и HTTPS. Если указать URI подключения с сегментом Transport, но не указать порт, сеанс будет создан со стандартными портами: 80 для HTTP и 443 для HTTPS. Чтобы использовать порты по умолчанию для удаленного взаимодействия PowerShell, укажите порт 5985 для HTTP или 5986 для HTTPS.

Если конечный компьютер перенаправляет подключение к другому универсальному коду ресурса (URI), PowerShell предотвращает перенаправление, если в команде не используется параметр **AllowRedirection** .

Этот параметр впервые появился в Windows PowerShell 3.0.

Этот параметр получает сеансы только с компьютеров, на которых выполняется Windows PowerShell 3,0 или более поздней версии Windows PowerShell. Предыдущие версии не хранят сеансы.

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

### -ContainerId

Указывает массив идентификаторов контейнеров. Этот командлет запускает интерактивный сеанс с каждым из указанных контейнеров. Используйте `docker ps` команду, чтобы получить список идентификаторов контейнеров. Дополнительные сведения см. в справке по команде [DOCKER PS](https://docs.docker.com/engine/reference/commandline/ps/) .

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

### -Credential

Указывает учетные данные пользователя. Этот командлет выполняет команду с разрешениями указанного пользователя. Укажите учетную запись пользователя, имеющую разрешение на подключение к удаленному компьютеру, и выполните `Get-PSSession` команду. По умолчанию используется текущий пользователь.

Введите имя пользователя, например **User01** или **Domain01\User01** , либо введите объект **PSCredential** , созданный `Get-Credential` командлетом. Если ввести имя пользователя, будет предложено ввести пароль.

Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).

> [!NOTE]
> Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

Этот параметр задает временное подключение, созданное для выполнения `Get-PSSession` команды с параметром **ComputerName** или **ConnectionURI** .

Этот параметр впервые появился в Windows PowerShell 3.0.

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

### -Id

Указывает массив идентификаторов сеансов. Этот командлет возвращает только сеансы с указанными идентификаторами. Введите один или несколько идентификаторов, разделенных запятыми, или используйте оператор Range (..), чтобы указать диапазон идентификаторов. Параметр ID нельзя использовать вместе с параметром **ComputerName** .

Идентификатор — это целое число, которое однозначно определяет управляемые пользователем сеансы в текущем сеансе. Проще запомнить и ввести, чем **InstanceId** , но он уникален только в пределах текущего сеанса. Идентификатор сеанса хранится в свойстве ID сеанса.

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

### -InstanceId

Указывает массив идентификаторов экземпляров сеансов. Этот командлет возвращает только сеансы с указанными идентификаторами экземпляра.

Идентификатор экземпляра — это GUID, однозначно определяющий сеанс на локальном или удаленном компьютере. Идентификатор **InstanceId** уникален, даже если в PowerShell работает несколько сеансов.

Идентификатор экземпляра сеанса хранится в свойстве сеанса **InstanceID** .

```yaml
Type: System.Guid[]
Parameter Sets: ComputerInstanceId, ConnectionUriInstanceId, VMNameInstanceId, ContainerIdInstanceId, VMIdInstanceId
Aliases:

Required: True (ComputerInstanceId, ConnectionUriInstanceId, ContainerIdInstanceId, VMIdInstanceId, VMNameInstanceId), False (InstanceId)
Position: Named
Default value: All sessions
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Указывает массив имен сеансов. Этот командлет возвращает только сеансы с указанными понятными именами. Можно использовать подстановочные знаки.

Понятное имя сеанса хранится в свойстве **Name** .

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

### -Port

Указывает указанный сетевой порт, используемый для временного подключения, в котором `Get-PSSession` выполняется команда. Для подключения к удаленному компьютеру требуется, чтобы он прослушивал порт, используемый соединением. Порты по умолчанию — 5985, то есть порт WinRM для HTTP, а 5986 — порт WinRM для HTTPS.

Прежде чем использовать альтернативный порт, необходимо настроить прослушиватель WinRM на удаленном компьютере для прослушивания по этому порту. Чтобы настроить прослушиватель, введите следующие две команды в командной строке PowerShell:

`Remove-Item -Path WSMan:\Localhost\listener\listener* -Recurse`

`New-Item -Path WSMan:\Localhost\listener -Transport http -Address * -Port \<port-number\>`

Этот параметр задает временное подключение, созданное для выполнения `Get-PSSession` команды с параметром **ComputerName** или **ConnectionURI** .

Не используйте параметр **Port** , если этого можно избежать. **Порт** , заданный в команде, применяется ко всем компьютерам или сеансам, на которых выполняется команда. Альтернативный порт может помешать выполнению команды на всех компьютерах.

Этот параметр впервые появился в Windows PowerShell 3.0.

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

### -SessionOption

Задает дополнительные параметры для сеанса. Введите объект **SessionOption** , например объект, созданный с помощью командлета New-PSSessionOption, или хэш-таблицу, где ключи — это имена параметров сеанса, а значения — это значения параметров сеанса.

Значения по умолчанию для параметров определяются значением привилегированной переменной $PSSessionOption, если оно задано. В противном случае значения по умолчанию задаются параметрами, указанными в конфигурации сеанса.

Значения параметров сеанса имеют приоритет над значениями по умолчанию, заданными в переменной $PSSessionOption и конфигурации сеанса. Однако они не имеют приоритет над максимальными значениями, квотами и ограничениями, заданными в конфигурации сеанса.

Описание параметров сеанса, включая значения по умолчанию, см. в разделе `New-PSSessionOption` .
Дополнительные сведения о `$PSSessionOption` переменной предпочтений см. в разделе [about_Preference_Variables](About/about_Preference_Variables.md). Дополнительные сведения о конфигурациях сеансов см. в разделе [about_Session_Configurations](About/about_Session_Configurations.md).

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

### -State

Указывает состояние сеанса. Этот командлет возвращает только сеансы в указанном состоянии. Допустимые значения для этого параметра: "все", "открыто", "отключено", "закрыто" и "нарушено". Значение по умолчанию — All.

Значение состояния сеанса задается относительно текущих сеансов. Сеансы, которые не были созданы в текущих сеансах и не подключены к текущему сеансу, находятся в состоянии Disconnected, даже если подключены к другому сеансу.

Состояние сеанса хранится в свойстве **State** .

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: Microsoft.PowerShell.Commands.SessionFilterState
Parameter Sets: ComputerInstanceId, ComputerName, ConnectionUriInstanceId, ConnectionUri, VMNameInstanceId, ContainerId, ContainerIdInstanceId, VMId, VMIdInstanceId, VMName
Aliases:
Accepted values: All, Opened, Disconnected, Closed, Broken

Required: False
Position: Named
Default value: All
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

Указывает максимальное количество одновременных подключений, которое может быть установлено для выполнения `Get-PSSession` команды. Если этот параметр не указан или введено значение 0 (ноль), используется значение по умолчанию — 32. Предел регулирования применяется только к текущему командлету, а не к сеансу или компьютеру.

Этот параметр впервые появился в Windows PowerShell 3.0.

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

### -UseSSL

Указывает, что этот командлет использует протокол SSL (SSL) для установления соединения, в котором `Get-PSSession` выполняется команда. По умолчанию SSL не используется. Если вы используете этот параметр, но SSL недоступен для порт, указанному в команде, она завершается ошибкой.

Этот параметр настраивает временное подключение, созданное для выполнения `Get-PSSession` команды с параметром **ComputerName** .

Этот параметр впервые появился в Windows PowerShell 3.0.

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

### — VMId

Указывает массив ИДЕНТИФИКАТОРов виртуальных машин. Этот командлет запускает интерактивный сеанс с каждой из указанных виртуальных машин. Чтобы просмотреть доступные виртуальные машины, используйте следующую команду:

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

### -VMName

Указывает массив имен виртуальных машин. Этот командлет запускает интерактивный сеанс с каждой из указанных виртуальных машин. Чтобы просмотреть доступные виртуальные машины, используйте `Get-VM` командлет.

```yaml
Type: System.String[]
Parameter Sets: VMNameInstanceId, VMName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет

В этот командлет нельзя передать входные данные.

## Выходные данные

### System.Management.Automation.Runspaces.PSSession

## ПРИМЕЧАНИЯ

- Этот командлет получает управляемые пользователем сеансы **PSSession** (например, созданные с помощью командлетов New-PSSession, `Enter-PSSession` и Invoke-Command). Он не получает управляемый системой сеанс, который создается при запуске PowerShell.
- Начиная с Windows PowerShell 3,0, объекты **PSSession** хранятся на компьютере, который находится на стороне сервера или получает окончание соединения. Чтобы получить сеансы, хранящиеся на локальном или удаленном компьютере, PowerShell устанавливает временный сеанс на указанном компьютере и выполняет команды запросов в сеансе.
- Чтобы получить сеансы, которые подключены к удаленному компьютеру, укажите удаленный компьютер в параметре **ComputerName** или **ConnectionUri** . Чтобы отфильтровать сеансы, которые `Get-PSSession` получают, используйте параметры **Name** , **ID** , **InstanceId** и **State** . Используйте остальные параметры, чтобы настроить временный сеанс, в котором `Get-PSSession` используется.
- При использовании параметров **ComputerName** или **ConnectionURI** `Get-PSSession` получает только сеансы с компьютеров, на которых выполняется Windows PowerShell 3,0 и более поздних версий PowerShell.
- Значение свойства **State** для **PSSession** задается относительно текущего сеанса.
  Таким образом, значение **disconnected** означает, что **сеанс PSSession** не подключен к текущему сеансу. Однако это не означает, что **сеанс PSSession** отключен от всех сеансов. Он может быть подключен к другому сеансу. Чтобы определить, можно ли подключиться к сеансу **PSSession** или повторно подключиться к нему из текущего сеанса, используйте свойство **Availability** .

Если свойство **Availability** имеет значение **None** , подключиться к сеансу можно. Значение **занято** указывает, что невозможно подключиться к сеансу **PSSession** , так как он подключен к другому сеансу.

Дополнительные сведения о значениях свойства **State** в сеансах см. в разделе [рунспацестате enumeration](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspacestate).

Дополнительные сведения о значениях свойства **Availability** сеансов см. в разделе [рунспацеаваилабилити enumeration](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspaceavailability).

## Связанные ссылки

[Connect-PSSession](Connect-PSSession.md)

[Disconnect-PSSession](Disconnect-PSSession.md)

[Receive-PSSession](Receive-PSSession.md)

[Enter-PSSession](Enter-PSSession.md)

[Exit-PSSession;](Exit-PSSession.md)

[Invoke-Command](Invoke-Command.md)

[New-PSSession](New-PSSession.md)

[Remove-PSSession](Remove-PSSession.md)

[about_PSSessions](About/about_PSSessions.md)

[about_Remote](About/about_Remote.md)
