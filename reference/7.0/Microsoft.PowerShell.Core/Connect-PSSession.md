---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 5/15/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/connect-pssession?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Connect-PSSession
ms.openlocfilehash: 61f1d13628763710f01cf0c2ec413f446e4bdd39
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "93229922"
---
# Connect-PSSession

## Краткий обзор
Выполняет повторное подключение к отключенным сеансам.

## SYNTAX

### Имя (по умолчанию)

```
Connect-PSSession -Name <String[]> [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Сеанс

```
Connect-PSSession [-Session] <PSSession[]> [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### компутернамегуид

```
Connect-PSSession -ComputerName <String[]> [-ApplicationName <String>] [-ConfigurationName <String>]
 -InstanceId <Guid[]> [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [-Port <Int32>] [-UseSSL] [-SessionOption <PSSessionOption>]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ИмяКомпьютера

```
Connect-PSSession -ComputerName <String[]> [-ApplicationName <String>] [-ConfigurationName <String>]
 [-Name <String[]>] [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [-Port <Int32>] [-UseSSL] [-SessionOption <PSSessionOption>]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### коннектионуригуид

```
Connect-PSSession [-ConfigurationName <String>] [-ConnectionUri] <Uri[]> [-AllowRedirection]
 -InstanceId <Guid[]> [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [-SessionOption <PSSessionOption>] [-ThrottleLimit <Int32>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ConnectionUri

```
Connect-PSSession [-ConfigurationName <String>] [-ConnectionUri] <Uri[]> [-AllowRedirection] [-Name <String[]>]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [-SessionOption <PSSessionOption>] [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InstanceId

```
Connect-PSSession -InstanceId <Guid[]> [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Идентификатор

```
Connect-PSSession [-ThrottleLimit <Int32>] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Командлет **Connect-PSSession** повторно подключается к управляемым пользователем сеансам PowerShell ( **PSSession** ), которые были отключены.
Он работает в сеансах, которые не были намеренно отключены, например с помощью командлета Disconnect-PSSession или параметра *InDisconnectedSession* командлета Invoke-Command, и тех, которые были отключены непреднамеренно, например с помощью временного сбоя сети.

**Connect-PSSession** может подключаться к любому отключенному сеансу, запущенному этим же пользователем.
К ним относятся те, которые были запущены или отключены от других сеансов на других компьютерах.

Однако **Connect-PSSession** не может подключиться к разорванным или закрытым сеансам или интерактивным сеансам, запущенным с помощью командлета Enter-PSSession.
Кроме того, вы не сможете подключиться к сеансам, запущенным другими пользователями, если не указать учетные данные пользователя, создавшего сеанс.

Дополнительные сведения о функции отключенных сеансов см. в разделе about_Remote_Disconnected_Sessions.

Этот командлет впервые появился в Windows PowerShell 3.0.

## Примеры

### Пример 1. Повторное подключение к сеансу

```
PS C:\> Connect-PSSession -ComputerName Server01 -Name ITTask
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 4 ITTask          Server01        Opened        ITTasks                  Available
```

Эта команда восстанавливает соединение с сеансом ITTask на компьютере Server01.

Выходные данные показывают, что команда выполнена успешно.
**Состояние** сеанса открывается, а **доступность** доступна, что означает, что можно выполнять команды в сеансе.

### Пример 2. последствия отключения и повторного подключения

```
PS C:\> Get-PSSession

Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 Backups         Localhost       Opened        Microsoft.PowerShell     Available


PS C:\> Get-PSSession | Disconnect-PSSession

Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 Backups         Localhost       Disconnected  Microsoft.PowerShell          None


PS C:\> Get-PSSession | Connect-PSSession

Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 Backups         Localhost       Opened        Microsoft.PowerShell     Available
```

В этом примере показан результат отключения и повторного подключения сеанса.

Первая команда использует командлет Get-PSSession.
Без параметра *ComputerName* команда возвращает только сеансы, которые были созданы в текущем сеансе.

Выходные данные показывают, что команда возвращает сеанс Backups на локальном компьютере.
**Состояние** сеанса открыто, и доступна **доступность** .

Вторая команда использует командлет **Get-PSSession** для получения объектов **PSSession** , созданных в текущем сеансе, и командлет **Disconnect-PSSession** для отключения сеансов.
Выходные данные показывают, что сеанс Backups отключен.
**Состояние** сеанса отключено, а уровень **доступности** — None.

Третья команда использует командлет **Get-PSSession** для получения объектов **PSSession** , которые были созданы в текущем сеансе, и командлет **Connect-PSSession** для повторного подключения сеансов.
Выходные данные показывают, что сеанс Backups был повторно подключен.
**Состояние** сеанса открыто, и доступна **доступность** .

При использовании командлета **Connect-PSSession** в сеансе, который не был отключен, команда не влияет на сеанс и не создает ошибок.

### Пример 3. ряд команд в корпоративном сценарии

```
The administrator starts by creating a sessions on a remote computer and running a script in the session.The first command uses the **New-PSSession** cmdlet to create the ITTask session on the Server01 remote computer. The command uses the *ConfigurationName* parameter to specify the ITTasks session configuration. The command saves the sessions in the $s variable.
PS C:\> $s = New-PSSession -ComputerName Server01 -Name ITTask -ConfigurationName ITTasks

 The second command **Invoke-Command** cmdlet to start a background job in the session in the $s variable. It uses the *FilePath* parameter to run the script in the background job.
PS C:\> Invoke-Command -Session $s {Start-Job -FilePath \\Server30\Scripts\Backup-SQLDatabase.ps1}
Id     Name            State         HasMoreData     Location             Command
--     ----            -----         -----------     --------             -------
2      Job2            Running       True            Server01             \\Server30\Scripts\Backup...

The third command uses the Disconnect-PSSession cmdlet to disconnect from the session in the $s variable. The command uses the *OutputBufferingMode* parameter with a value of Drop to prevent the script from being blocked by having to deliver output to the session. It uses the *IdleTimeoutSec* parameter to extend the session time-out to 15 hours.When the command is completed, the administrator locks her computer and goes home for the evening.
PS C:\> Disconnect-PSSession -Session $s -OutputBufferingMode Drop -IdleTimeoutSec 60*60*15
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Server01        Disconnected  ITTasks               None

Later that evening, the administrator starts her home computer, logs on to the corporate network, and starts PowerShell. The fourth command uses the Get-PSSession cmdlet to get the sessions on the Server01 computer. The command finds the ITTask session.The fifth command uses the **Connect-PSSession** cmdlet to connect to the ITTask session. The command saves the session in the $s variable.
PS C:\> Get-PSSession -ComputerName Server01 -Name ITTask

Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Server01        Disconnected  ITTasks               None


PS C:\> $s = Connect-PSSession -ComputerName Server01 -Name ITTask


Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Server01        Opened        ITTasks               Available

The sixth command uses the **Invoke-Command** cmdlet to run a Get-Job command in the session in the $s variable. The output shows that the job finished successfully.The seventh command uses the **Invoke-Command** cmdlet to run a Receive-Job command in the session in the $s variable in the session. The command saves the results in the $BackupSpecs variable.The eighth command uses the **Invoke-Command** cmdlet to runs another script in the session. The command uses the value of the $BackupSpecs variable in the session as input to the script.


PS C:\> Invoke-Command -Session $s {Get-Job}

Id     Name            State         HasMoreData     Location             Command
--     ----            -----         -----------     --------             -------
2      Job2            Completed     True            Server01             \\Server30\Scripts\Backup...

PS C:\> Invoke-Command -Session $s {$BackupSpecs = Receive-Job -JobName Job2}

PS C:\> Invoke-Command -Session $s {\\Server30\Scripts\New-SQLDatabase.ps1 -InitData $BackupSpecs.Initialization}

The ninth command disconnects from the session in the $s variable.The administrator closes PowerShell and closes the computer. She can reconnect to the session on the next day and check the script status from her work computer.
PS C:\> Disconnect-PSSession -Session $s -OutputBufferingMode Drop -IdleTimeoutSec 60*60*15
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Server01        Disconnected  ITTasks               None
```

В этой серии команд показано, как командлет **Connect-PSSession** можно использовать на предприятии.
В этом случае системный администратор запускает длительное задание в сеансе на удаленном компьютере.
После запуска задания администратор отключается от сеанса и отправляется домой.
Позднее, вечером, администратор выполняет вход на свой домашний компьютер и проверяет, выполнялось ли задание до его завершения.

## PARAMETERS

### -AllowRedirection

Указывает, что этот командлет разрешает перенаправление этого соединения на альтернативный URI.

При использовании параметра *ConnectionURI* удаленный компьютер может вернуть инструкцию для перенаправления на другой URI.
По умолчанию PowerShell не перенаправляет соединения, но можно использовать этот параметр, чтобы разрешить перенаправление подключения.

Можно также ограничить количество перенаправлений соединение, изменив значение параметра сеанса **MaximumConnectionRedirectionCount**.
Используйте параметр *максимумредиректион* командлета New-PSSessionOption или задайте свойство **MaximumConnectionRedirectionCount** для переменной настройки **$PSSessionOption** .
Значение по умолчанию — 5.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ConnectionUri, ConnectionUriGuid
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationName

Указывает имя приложения.
Этот командлет подключается только к сеансам, использующим указанное приложение.

Введите сегмент имени приложения URI подключения.
Например, в следующем URI соединения имя приложения — WSMan: `http://localhost:5985/WSMAN` .
Имя приложения сеанса хранится в свойстве сеанса **Runspace.ConnectionInfo.AppName**.

Значение этого параметра используется для выбора и фильтрации сеансов.
Оно не изменяет приложение, которое использует сеанс.

```yaml
Type: System.String
Parameter Sets: ComputerNameGuid, ComputerName
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

Дополнительные сведения о значениях этого параметра см. в разделе [перечисление AuthenticationMechanism](https://msdn.microsoft.com/library/system.management.automation.runspaces.authenticationmechanism) в библиотеке MSDN.

Внимание! Аутентификация CredSSP, в рамках которой учетные данные пользователя передаются на удаленный компьютер для проверки, предназначена для команд, требующих аутентификацию нескольких ресурсов, например для доступа к удаленной сетевой папке.
Этот механизм повышает риск безопасности удаленной операции.
Если удаленный компьютер скомпрометирован, учетные данные, передаваемые ему, могут использоваться для управления сетевым сеансом.

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ComputerNameGuid, ComputerName, ConnectionUri, ConnectionUriGuid
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CertificateThumbprint

Задает цифровой сертификат с открытым ключом (X509) учетной записи пользователя, который располагает разрешением для подключения к отсоединенному сеансу. Введите отпечаток сертификата.

Сертификаты используются при проверке подлинности на основе сертификата клиента.
Они могут быть сопоставлены только с локальными учетными записями пользователей.
Они не работают с учетными записями домена.

Чтобы получить отпечаток сертификата, используйте команду Get-Item или Get-ChildItem на диске с сертификатом PowerShell:.

```yaml
Type: System.String
Parameter Sets: ComputerNameGuid, ComputerName, ConnectionUri, ConnectionUriGuid
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Указывает компьютеры, на которых хранятся отключенные сеансы.
Сеансы хранятся на компьютере, который находится на стороне сервера или получает окончание соединения.
По умолчанию это локальный компьютер.

Введите имя NetBIOS, IP-адрес или полное доменное имя компьютера.
Подстановочные знаки не допускаются.
Чтобы указать локальный компьютер, введите имя компьютера, localhost или точку (.)

```yaml
Type: System.String[]
Parameter Sets: ComputerNameGuid, ComputerName
Aliases: Cn

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConfigurationName

Подключается только к сеансам, использующим указанную конфигурацию сеанса.

Введите имя конфигурации или полное имя ресурса (URI) для конфигурации сеанса.
Если указано только имя конфигурации, в начале добавляется следующий URI схемы: `http://schemas.microsoft.com/powershell` .
Имя конфигурации сеанса хранится в свойстве сеанса **ConfigurationName**.

Значение этого параметра используется для выбора и фильтрации сеансов.
Оно не изменяет конфигурацию, которую использует сеанс.

Дополнительные сведения о конфигурациях сеансов см. в разделе [about_Session_Configurations](About/about_Session_Configurations.md).

```yaml
Type: System.String
Parameter Sets: ComputerNameGuid, ComputerName, ConnectionUri, ConnectionUriGuid
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConnectionUri

Указывает URI конечных точек подключения для отключенных сеансов.

Значение URI должно быть указано полностью.
Строка имеет следующий формат:

`\<Transport\>://\<ComputerName\>:\<Port\>/\<ApplicationName\>`

Значение по умолчанию определяется следующим образом.

`http://localhost:5985/WSMAN`

Если не указать URI соединения, можно использовать параметры *UseSSL* и *Port* , чтобы указать значения универсального кода ресурса (URI) соединения.

Допустимые значения для сегмента **Transport** идентификатора URI: HTTP и HTTPS.
Если указать URI подключения с сегментом Transport, но не указать порт, сеанс будет создан со стандартными портами: 80 для HTTP и 443 для HTTPS.
Чтобы использовать порты по умолчанию для удаленного взаимодействия PowerShell, укажите порт 5985 для HTTP или 5986 для HTTPS.

Если конечный компьютер перенаправляет подключение к другому универсальному коду ресурса (URI), PowerShell предотвращает перенаправление, если в команде не используется параметр *AllowRedirection* .

```yaml
Type: System.Uri[]
Parameter Sets: ConnectionUri, ConnectionUriGuid
Aliases: URI, CU

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Credential

Указывает учетную запись пользователя с разрешением на подключение к отсоединенному сеансу.
По умолчанию используется текущий пользователь.

Введите имя пользователя, например **User01** или **Domain01\User01** , либо введите объект **PSCredential** , созданный `Get-Credential` командлетом. Если ввести имя пользователя, будет предложено ввести пароль.

Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).

> [!NOTE]
> Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerNameGuid, ComputerName, ConnectionUri, ConnectionUriGuid
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id

Указывает идентификаторы отключенных сеансов.
Параметр *ID* работает только в том случае, если отключенный сеанс ранее был подключен к текущему сеансу.

Этот параметр допустим, но не имеет силы, если сеанс хранится на локальном компьютере, но не был подключен к текущему сеансу.

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InstanceId

Указывает идентификаторы экземпляров отключенных сеансов.

Идентификатор экземпляра — это идентификатор GUID, который однозначно определяет **сеанс PSSession** на локальном или удаленном компьютере.

Идентификатор экземпляра хранится в свойстве **InstanceId** **сеанса PSSession**.

```yaml
Type: System.Guid[]
Parameter Sets: ComputerNameGuid, ConnectionUriGuid, InstanceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Указывает понятные имена отключенных сеансов.

```yaml
Type: System.String[]
Parameter Sets: Name, ComputerName, ConnectionUri
Aliases:

Required: True (Name), False (ComputerName, ConnectionUri)
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Port

Указывает сетевой порт на удаленном компьютере, который используется для повторного подключения к сеансу.
Для подключения к удаленному компьютеру требуется, чтобы он прослушивал порт, используемый соединением.
Порты по умолчанию — 5985, то есть порт WinRM для HTTP, а 5986 — порт WinRM для HTTPS.

Прежде чем использовать альтернативный порт, необходимо настроить прослушиватель WinRM на удаленном компьютере для прослушивания по этому порту.
Чтобы настроить прослушиватель, введите следующие две команды в командной строке PowerShell:

`Remove-Item -Path WSMan:\Localhost\listener\listener* -Recurse`

`New-Item -Path WSMan:\Localhost\listener -Transport http -Address * -Port \<port-number\>`

Не используйте параметр *Port* , если этого можно избежать.
Порт, который задается в команде, применяется ко всем компьютерам или сеансам, в которых выполняется команда.
Альтернативный порт может помешать выполнению команды на всех компьютерах.

```yaml
Type: System.Int32
Parameter Sets: ComputerNameGuid, ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Session

Указывает отключенные сеансы.
Введите переменную, содержащую объекты **PSSession** , или команду, которая создает или получает объекты **PSSession** , такие как команда Get-PSSession.

```yaml
Type: System.Management.Automation.Runspaces.PSSession[]
Parameter Sets: Session
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -SessionOption

Задает дополнительные параметры для сеанса.
Введите объект **SessionOption** , например объект, созданный с помощью командлета New-PSSessionOption, или хэш-таблицу, где ключи — это имена параметров сеанса, а значения — это значения параметров сеанса.

Значения по умолчанию для параметров определяются значением привилегированной переменной $PSSessionOption, если оно задано.
В противном случае значения по умолчанию задаются параметрами, указанными в конфигурации сеанса.

Значения параметров сеанса имеют приоритет над значениями по умолчанию, заданными в переменной $PSSessionOption и конфигурации сеанса.
Однако они не имеют приоритет над максимальными значениями, квотами и ограничениями, заданными в конфигурации сеанса.

Описание параметров сеанса, включающих значения по умолчанию, см. в разделе New-PSSessionOption.
Дополнительные сведения о переменной настройки **$PSSessionOption** см. в разделе [about_Preference_Variables](About/about_Preference_Variables.md).
Дополнительные сведения о конфигурациях сеансов см. в разделе [about_Session_Configurations](About/about_Session_Configurations.md).

```yaml
Type: System.Management.Automation.Remoting.PSSessionOption
Parameter Sets: ComputerNameGuid, ComputerName, ConnectionUri, ConnectionUriGuid
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

Указывает максимальное число одновременных подключений, которые можно установить для запуска этой команды.
Если этот параметр не указан или имеет значение 0, используется значение по умолчанию — 32.

Предел регулирования применяется только к текущему командлету, а не к сеансу или компьютеру.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseSSL

Указывает, что этот командлет использует протокол SSL (SSL) для подключения к отключенному сеансу. По умолчанию SSL не используется.

WS-Management шифрует все содержимое PowerShell, передаваемое по сети.
Параметр *UseSSL* — это дополнительная защита, которая отправляет данные по HTTPS-соединению, а не по HTTP.

Если вы используете этот параметр, но протокол SSL недоступен для порта, используемого для команды, команда завершается ошибкой.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerNameGuid, ComputerName
Aliases:

Required: False
Position: Named
Default value: None
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

Показывает, что произойдет при запуске командлета.
Командлет не выполняется.

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

Сеанс ( **PSSession** ) можно передать в этот командлет по конвейеру.

## Выходные данные

### System.Management.Automation.Runspaces.PSSession

Этот командлет возвращает объект, представляющий сеанс, к которому он был подключен повторно.

## ПРИМЕЧАНИЯ

* **Connect-PSSession** повторно подключается только к сеансам, которые отключены, т. е. сеансы со значением disconnected (отключено) для свойства **State** . Только сеансы, подключенные к или конечным компьютерам под управлением Windows PowerShell 3,0 или более поздней версии, могут быть отключены и повторно подключены.
* При использовании **Connect-PSSession** для сеанса, который не был отключен, команда не влияет на сеанс и не создает ошибок.
* Отключенные сеансы замыкания на себя с интерактивными маркерами, которые создаются с помощью параметра *EnableNetworkAccess* , могут быть повторно подключены только с компьютера, на котором был создан сеанс. Это ограничение защищает компьютер от вредоносного доступа.
* Значение свойства **State** для **PSSession** задается относительно текущего сеанса.
Таким образом, значение **disconnected** означает, что **сеанс PSSession** не подключен к текущему сеансу. Однако это не означает, что **сеанс PSSession** отключен от всех сеансов. Он может быть подключен к другому сеансу. Определить возможность подключения или повторного подключения к сеансу позволяет свойство **Availability**.

  Если свойство **Availability** имеет значение None, подключиться к сеансу можно.
Значение занято указывает, что невозможно подключиться к сеансу **PSSession** , так как он подключен к другому сеансу.

  Дополнительные сведения о значениях свойства **State** в сеансах см. в разделе [перечисление РУНСПАЦЕСТАТЕ](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspacestate) в библиотеке MSDN.

  Дополнительные сведения о значениях свойства **доступность** сеансов см. в разделе [перечисление РУНСПАЦЕАВАИЛАБИЛИТИ](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspaceavailability) в библиотеке MSDN.

* Нельзя изменить значение времени ожидания простоя **сеанса PSSession** при подключении к **сеансу PSSession**. Параметр *SessionOption* командлета **Connect-PSSession** принимает объект **SessionOption** со значением **IdleTimeout** . Однако значение **IdleTimeout** объекта **SessionOption** и значение **IdleTimeout** переменной $PSSessionOption не учитываются при соединении с **PSSession**.

  Можно задать и изменить время ожидания простоя **сеанса PSSession** при создании **сеанса PSSession** с помощью командлетов **New-PSSession** или **Invoke-Command** , а также при отключении от **сеанса PSSession**.

  Свойство **IdleTimeout** для сеанса **PSSession** очень важно для отключенных сеансов, так как оно определяет, как долго отключенный сеанс сохраняется на удаленном компьютере.
Отключенные сеансы считаются находящимися в режиме простоя с момента их отключения, даже если в них выполняются команды.

## Связанные ссылки

[Disconnect-PSSession](Disconnect-PSSession.md)

[Enter-PSSession](Enter-PSSession.md)

[Exit-PSSession;](Exit-PSSession.md)

[Get-PSSession](Get-PSSession.md)

[Get-PSSessionConfiguration](Get-PSSessionConfiguration.md)

[New-PSSession](New-PSSession.md)

[New-PSSessionOption](New-PSSessionOption.md)

[New-PSTransportOption](New-PSTransportOption.md)

[Receive-PSSession](Receive-PSSession.md)

[Register-PSSessionConfiguration](Register-PSSessionConfiguration.md)

[Remove-PSSession](Remove-PSSession.md)
