---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 12/20/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-pssession?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSSession
ms.openlocfilehash: 90bd1d539bb6bc071df6bfcf326adc57e24fff8f
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "93229882"
---
# New-PSSession

## Краткий обзор
Создает постоянное подключение к локальному или удаленному компьютеру.

## SYNTAX

### ComputerName (по умолчанию)

```
New-PSSession [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-Name <String[]>]
 [-EnableNetworkAccess] [-ConfigurationName <String>] [-Port <Int32>] [-UseSSL]
 [-ApplicationName <String>] [-ThrottleLimit <Int32>] [-SessionOption <PSSessionOption>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

### VMId

```
New-PSSession -Credential <PSCredential> [-Name <String[]>] [-ConfigurationName <String>]
 [-VMId] <Guid[]> [-ThrottleLimit <Int32>] [<CommonParameters>]
```

### URI

```
New-PSSession [-Credential <PSCredential>] [-Name <String[]>] [-EnableNetworkAccess]
 [-ConfigurationName <String>] [-ThrottleLimit <Int32>] [-ConnectionUri] <Uri[]> [-AllowRedirection]
 [-SessionOption <PSSessionOption>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [<CommonParameters>]
```

### VMName

```
New-PSSession -Credential <PSCredential> [-Name <String[]>] [-ConfigurationName <String>]
 -VMName <String[]> [-ThrottleLimit <Int32>] [<CommonParameters>]
```

### Сеанс

```
New-PSSession [[-Session] <PSSession[]>] [-Name <String[]>] [-EnableNetworkAccess]
 [-ThrottleLimit <Int32>] [<CommonParameters>]
```

### ContainerId

```
New-PSSession [-Name <String[]>] [-ConfigurationName <String>] -ContainerId <String[]>
 [-RunAsAdministrator] [-ThrottleLimit <Int32>] [<CommonParameters>]
```

### сшхост

```
New-PSSession [-Name <String[]>] [-Port <Int32>] [-HostName] <String[]> [-UserName <String>]
 [-KeyFilePath <String>] [-SSHTransport] [-Subsystem <String>] [<CommonParameters>]
```

### сшхоссашпарам

```
New-PSSession [-Name <String[]>] -SSHConnection <Hashtable[]> [<CommonParameters>]
```

## DESCRIPTION

`New-PSSession`Командлет создает сеанс PowerShell ( **PSSession** ) на локальном или удаленном компьютере. При создании **сеанса PSSession** PowerShell устанавливает постоянное подключение к удаленному компьютеру.

Используйте **PSSession** для выполнения нескольких команд, совместно использующих данные, таких как функция или значение переменной. Для выполнения команд в **PSSession** используйте `Invoke-Command` командлет. Чтобы использовать **PSSession** для взаимодействия непосредственно с удаленным компьютером, используйте `Enter-PSSession` командлет. Дополнительные сведения см. в разделе [about_PSSessions](about/about_PSSessions.md).

Команды можно выполнять на удаленном компьютере без создания **сеанса PSSession** с помощью параметров **ComputerName** параметра `Enter-PSSession` или `Invoke-Command` . При использовании параметра **ComputerName** PowerShell создает временное подключение, которое используется для команды и затем закрывается.

Начиная с PowerShell 6,0 можно использовать Secure Shell (SSH) для установления подключения к и создания сеанса на удаленном компьютере, если SSH доступен на локальном компьютере, а удаленный компьютер настроен с помощью конечной точки SSH PowerShell. Преимуществом удаленного сеанса PowerShell на основе SSH является то, что он может работать на нескольких платформах (Windows, Linux, macOS). Для сеансов на основе SSH используется параметр **HostName** или **сшконнектион** , заданный для указания удаленного компьютера и соответствующих сведений о соединении. Дополнительные сведения о настройке удаленного взаимодействия PowerShell с использованием SSH см. в статье [удаленное взаимодействие PowerShell через SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).

> [!NOTE]
> При использовании удаленного взаимодействия WSMan из клиента Linux или macOS с конечной точкой HTTPS, в которой сертификат сервера не является доверенным (например, самозаверяющий сертификат). `PSSessionOption` `-SkipCACheck` Для успешного установления соединения необходимо указать, который включает и `-SkipCNCheck` . Сделайте это, только если вы в среде, где можно указать сертификат сервера и сетевое подключение к целевой системе.

## Примеры

### Пример 1. Создание сеанса на локальном компьютере

```powershell
$s = New-PSSession
```

Эта команда создает новый **сеанс PSSession** на локальном компьютере и сохраняет **сеанс PSSession** в `$s` переменной.

Теперь этот **сеанс PSSession** можно использовать для выполнения команд на локальном компьютере.

### Пример 2. Создание сеанса на удаленном компьютере

```powershell
$Server01 = New-PSSession -ComputerName Server01
```

Эта команда создает новый **сеанс PSSession** на компьютере Server01 и сохраняет его в `$Server01` переменной.

При создании нескольких объектов **PSSession** назначьте их переменным с полезными именами. Это позволит управлять объектами **PSSession** в последующих командах.

### Пример 3. Создание сеансов на нескольких компьютерах

```powershell
$s1, $s2, $s3 = New-PSSession -ComputerName Server01,Server02,Server03
```

Эта команда создает три объекта **PSSession** — по одному на каждом из компьютеров, указанных параметром **ComputerName** .

Команда использует оператор присваивания (=) для назначения новых объектов **PSSession** переменным: `$s1` , `$s2` , `$s3` . Он назначает Server01 **PSSession** `$s1` , Server02 **PSSession** `$s2` —, а Server03 **PSSession** — `$s3` .

При назначении нескольких объектов ряду переменных PowerShell каждый объект назначается переменной в ряде, соответственно. Если объектов больше, чем переменных, все оставшиеся объекты назначаются последней переменной. Если переменных больше, чем объектов, оставшиеся переменные остаются пустыми (null).

### Пример 4. Создание сеанса с указанным портом

```powershell
New-PSSession -ComputerName Server01 -Port 8081 -UseSSL -ConfigurationName E12
```

Эта команда создает новый **сеанс PSSession** на компьютере Server01, который подключается к порту сервера 8081 и использует протокол SSL. Новый сеанс **PSSession** использует альтернативную конфигурацию сеанса с именем E12.

Прежде чем задать порт, необходимо настроить прослушиватель службы удаленного управления Windows для прослушивания порта 8081 на удаленном компьютере. Дополнительные сведения см. в описании параметра **Port**.

### Пример 5. Создание сеанса на основе существующего сеанса

```powershell
New-PSSession -Session $s -Credential Domain01\User01
```

Эта команда создает **сеанс PSSession** с теми же свойствами, что и у существующего **сеанса PSSession**. Этот формат команды можно использовать, когда ресурсы существующего **сеанса PSSession** исчерпаны, а для разгрузки какого-либо запроса требуется новый **сеанс PSSession** .

Команда использует параметр **Session** объекта, `New-PSSession` чтобы указать **сеанс PSSession** , сохраненный в `$s` переменной. Она использует для выполнения команды учетные данные пользователя Domain1\Admin01.

### Пример 6. Создание сеанса с глобальной областью в другом домене

```powershell
$global:s = New-PSSession -ComputerName Server1.Domain44.Corpnet.Fabrikam.com -Credential Domain01\Admin01
```

В этом примере показано, как создать **сеанс PSSession** с глобальной областью на компьютере в другом домене.

По умолчанию объекты **PSSession** , созданные в командной строке, создаются с помощью локальной области, а объекты **PSSession** , созданные в скрипте, имеют область скриптов.

Чтобы создать **сеанс PSSession** с глобальной областью, создайте новый **сеанс PSSession** , а затем сохраните **PSSession** в переменной, приведенной к глобальной области. В этом случае `$s` переменная приводится к глобальной области видимости.

Команда использует параметр **ComputerName** , чтобы указать удаленный компьютер. Так как компьютер находится в домене, отличном от домена с учетной записью пользователя, полное имя компьютера указывается вместе с учетными данными пользователя.

### Пример 7. Создание сеансов для многих компьютеров

```powershell
$rs = Get-Content C:\Test\Servers.txt | New-PSSession -ThrottleLimit 50
```

Эта команда создает **сеанс PSSession** на каждом из 200 компьютеров, перечисленных в файле Servers.txt и сохраняет полученный **сеанс PSSession** в `$rs` переменной. Объекты **PSSession** имеют ограничение регулирования в 50.

Этот формат команды можно использовать, если имена компьютеров хранятся в базе данных, электронной таблице, текстовом файле или другом формате, преобразуемом в текст.

### Пример 8. Создание сеанса с помощью URI

```powershell
$s = New-PSSession -URI http://Server01:91/NewSession -Credential Domain01\User01
```

Эта команда создает **сеанс PSSession** на компьютере Server01 и сохраняет его в `$s` переменной. Он использует параметр **URI** , чтобы указать транспортный протокол, удаленный компьютер, порт и конфигурацию дополнительного сеанса. Он также использует параметр **Credential** , чтобы указать учетную запись пользователя, имеющую разрешение на создание сеанса на удаленном компьютере.

### Пример 9. Запуск фонового задания в наборе сеансов

```powershell
$s = New-PSSession -ComputerName (Get-Content Servers.txt) -Credential Domain01\Admin01 -ThrottleLimit 16
Invoke-Command -Session $s -ScriptBlock {Get-Process PowerShell} -AsJob
```

Эти команды создают набор объектов **PSSession** , а затем запускают фоновое задание в каждом из объектов **PSSession** .

Первая команда создает новый **сеанс PSSession** на каждом из компьютеров, перечисленных в файле Servers.txt. Он использует `New-PSSession` командлет для создания **сеанса PSSession**. Значение параметра **ComputerName** — это команда, использующая `Get-Content` командлет для получения списка имен компьютеров с Servers.txtным файлом.

Команда использует параметр **Credential** для создания объектов **PSSession** , имеющих разрешение администратора домена, и использует параметр **ThrottleLimit** , чтобы ограничить команду 16 одновременными подключениями. Команда сохраняет объекты **PSSession** в `$s` переменной.

Вторая команда использует параметр **AsJob** `Invoke-Command` командлета для запуска фонового задания, которое выполняет `Get-Process PowerShell` команду в каждом из объектов **PSSession** в `$s` .

Дополнительные сведения о фоновых заданиях PowerShell см. в разделе [about_Jobs](About/about_Jobs.md) и [about_Remote_Jobs](About/about_Remote_Jobs.md).

### Пример 10. Создание сеанса для компьютера с помощью универсального кода ресурса (URI)

```powershell
New-PSSession -ConnectionURI https://management.exchangelabs.com/Management
```

Эта команда создает объекты **PSSession** , которые подключаются к компьютеру, указанному с помощью универсального кода ресурса (URI), а не имени компьютера.

### Пример 11. Создание параметра сеанса

```powershell
$so = New-PSSessionOption -SkipCACheck
New-PSSession -ConnectionUri https://management.exchangelabs.com/Management -SessionOption $so -Credential Server01\Admin01
```

В этом примере показано, как создать объект параметров сеанса и использовать параметр **SessionOption** .

Первая команда использует `New-PSSessionOption` командлет для создания параметра сеанса. Он сохраняет полученный объект **SessionOption** в `$so` переменной.

Вторая команда использует параметр в новом сеансе. Команда использует `New-PSSession` командлет для создания нового сеанса. Значением параметра SessionOption является объект **SessionOption** в `$so` переменной.

### Пример 12. Создание сеанса с помощью SSH

```powershell
New-PSSession -HostName UserA@LinuxServer01
```

В этом примере показано, как создать новый **сеанс PSSession** с помощью Secure Shell (SSH). Если на удаленном компьютере настроен протокол SSH для запроса паролей, вы получите запрос на ввод пароля. В противном случае необходимо будет использовать проверку подлинности пользователя на основе ключа SSH.

### Пример 13. Создание сеанса с помощью SSH и указание ключа проверки подлинности порта и пользователя

```powershell
New-PSSession -HostName UserA@LinuxServer01:22 -KeyFilePath c:\<path>\userAKey_rsa
```

В этом примере показано, как создать **сеанс PSSession** с помощью Secure Shell (SSH). Он использует параметр **Port** для указания используемого порта и параметр **KeyFilePath** для указания ключа RSA, используемого для идентификации пользователя на удаленном компьютере и проверки его подлинности.

### Пример 14. Создание нескольких сеансов с помощью SSH

```powershell
$sshConnections = @{ HostName="WinServer1"; UserName="domain\userA"; KeyFilePath="c:\users\UserA\id_rsa" }, @{ HostName="UserB@LinuxServer5"; KeyFilePath="c:\UserB\<path>\id_rsa" }
New-PSSession -SSHConnection $sshConnections
```

В этом примере показано, как создать несколько сеансов с помощью Secure Shell (SSH) и набора параметров **сшконнектион** . Параметр **сшконнектион** принимает массив хэш-таблиц, содержащих сведения о соединении для каждого сеанса. Обратите внимание, что этот пример требует, чтобы на целевых удаленных компьютерах был настроен SSH для поддержки проверки подлинности пользователей на основе ключей.

## PARAMETERS

### -AllowRedirection

Указывает, что этот командлет разрешает перенаправление этого соединения в альтернативный универсальный код ресурса (URI).

При использовании параметра **ConnectionURI** удаленный компьютер может вернуть инструкцию для перенаправления на другой URI. По умолчанию PowerShell не перенаправляет соединения, но этот параметр можно использовать, чтобы разрешить ему перенаправить подключение.

Можно также ограничить количество перенаправлений соединение, изменив значение параметра сеанса **MaximumConnectionRedirectionCount**. Используйте параметр **максимумредиректион** `New-PSSessionOption` командлета или задайте свойство **MaximumConnectionRedirectionCount** переменной предпочтений **$PSSessionOption** . Значение по умолчанию — 5.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Uri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationName

Определяет сегмент имени приложения в URI соединения. Используйте этот параметр, чтобы указать имя приложения, если в команде не используется параметр **ConnectionURI**.

Значение по умолчанию — это значение `$PSSessionApplicationName` привилегированной переменной на локальном компьютере. Если привилегированная переменная не определена, значение по умолчанию — WSMAN. Это значение подходит для большинства случаев Дополнительные сведения см. в разделе [about_Preference_Variables](About/about_Preference_Variables.md).

Служба удаленного управления Windows (WinRM) использует имя приложения для выбора прослушивателя для обслуживания запроса на подключение.
Значение этого параметра должно совпадать со значением свойства **URLPrefix** прослушивателя на удаленном компьютере.

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Authentication

Задает механизм, используемый при проверке подлинности учетных данных пользователя.
Допустимые значения для этого параметра:

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
Parameter Sets: ComputerName, Uri
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CertificateThumbprint

Задает цифровой сертификат с открытым ключом (X509) учетной записи пользователя, который располагает разрешением для выполнения этого действия. Введите отпечаток сертификата.

Сертификаты используются при проверке подлинности на основе сертификата клиента. Они могут сопоставляться только с учетными записями локальных пользователей и не работают с учетными записями доменов.

Чтобы получить сертификат, используйте `Get-Item` `Get-ChildItem` команду или на диске PowerShell CERT:.

```yaml
Type: System.String
Parameter Sets: ComputerName, Uri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Указывает массив имен компьютеров. Этот командлет создает постоянное подключение ( **PSSession** ) к указанному компьютеру. Если ввести несколько имен компьютеров, `New-PSSession` создает несколько объектов **PSSession** , по одному для каждого компьютера. По умолчанию это локальный компьютер.

Введите имя NetBIOS, IP-адрес или полное доменное имя одного или нескольких удаленных компьютеров. Чтобы указать локальный компьютер, введите имя компьютера, localhost или точку (.). Если компьютер находится в другом домене, отличном от домена пользователя, полное доменное имя является обязательным. Также можно передать имя компьютера в кавычках в `New-PSSession` .

Чтобы использовать IP-адрес в значении параметра **ComputerName** , команда должна включать параметр **Credential** . Кроме того, компьютер должен быть настроен для транспорта HTTPS или IP-адрес удаленного компьютера должен быть включен в список TrustedHosts службы WinRM на локальном компьютере. Инструкции по добавлению имени компьютера в список TrustedHosts см. в разделе "Добавление компьютера в список надежных узлов" в [about_Remote_Troubleshooting](about/about_Remote_Troubleshooting.md).

Чтобы включить локальный компьютер в значение параметра **ComputerName** , запустите Windows PowerShell с помощью команды Запуск от имени администратора.

```yaml
Type: System.String[]
Parameter Sets: ComputerName
Aliases: Cn

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -ConfigurationName

Указывает конфигурацию сеанса, используемую для нового **PSSession**.

Введите имя конфигурации или полное имя ресурса (URI) для конфигурации сеанса. Если указано только имя конфигурации, в начале добавляется следующий URI схемы: `http://schemas.microsoft.com/PowerShell` .

Конфигурация сеанса для сеанса размещается на удаленном компьютере. Если указанной конфигурации сеанса нет на удаленном компьютере, команда завершается ошибкой.

Значение по умолчанию — это значение `$PSSessionConfigurationName` привилегированной переменной на локальном компьютере. Если эта привилегированная переменная не определена, значением по умолчанию является Microsoft.PowerShell. Дополнительные сведения см. в разделе [about_Preference_Variables](About/about_Preference_Variables.md).

```yaml
Type: System.String
Parameter Sets: ComputerName, Uri, VMId, VMName, ContainerId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConnectionUri

Задает универсальный код ресурса (URI), определяющий конечную точку подключения для сеанса. Значение URI должно быть указано полностью. Строка имеет следующий формат:

`<Transport>://<ComputerName>:<Port>/<ApplicationName>`

Значение по умолчанию определяется следующим образом.

`http://localhost:5985/WSMAN`

Если не указывать **ConnectionURI** , можно использовать параметры **UseSSL** , **ComputerName** , **Port** и **ApplicationName** для задания значений **ConnectionURI**.

Допустимые значения для сегмента транспорта URI — HTTP и HTTPS. Если указать URI подключения с сегментом Transport, но не указать порт, сеанс будет создан со стандартными портами: 80 для HTTP и 443 для HTTPS. Чтобы использовать порты по умолчанию для удаленного взаимодействия PowerShell, укажите порт 5985 для HTTP или 5986 для HTTPS.

Если конечный компьютер перенаправляет подключение к другому универсальному коду ресурса (URI), PowerShell предотвращает перенаправление, если в команде не используется параметр **AllowRedirection** .

```yaml
Type: System.Uri[]
Parameter Sets: Uri
Aliases: URI, CU

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ContainerId

Указывает массив идентификаторов контейнеров. Этот командлет запускает интерактивный сеанс с каждым из указанных контейнеров. Используйте `docker ps` команду, чтобы получить список идентификаторов контейнеров. Дополнительные сведения см. в справке по команде [DOCKER PS](https://docs.docker.com/engine/reference/commandline/ps/) .

```yaml
Type: System.String[]
Parameter Sets: ContainerId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Credential

Указывает учетную запись пользователя, имеющую разрешение на это действие. По умолчанию используется текущий пользователь.

Введите имя пользователя, например **User01** или **Domain01\User01** , либо введите объект **PSCredential** , созданный `Get-Credential` командлетом. Если ввести имя пользователя, будет предложено ввести пароль.

Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).

> [!NOTE]
> Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerName, Uri, VMId, VMName
Aliases:

Required: True (VMId, VMName), False (ComputerName, Uri)
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableNetworkAccess

Указывает, что этот командлет добавляет интерактивный маркер безопасности в сеансы замыкания на себя. Интерактивный маркер позволяет выполнять в петлевом сеансе команды, которые получают данные с других компьютеров. Например, можно выполнить команду в сеансе, который копирует XML-файлы с удаленного компьютера на локальный.

Сеанс замыкания на себя — это **PSSession** , который создается и завершается на том же компьютере. Чтобы создать сеанс замыкания на себя, опустите параметр **ComputerName** или задайте для него значение Dot (.), localhost или имя локального компьютера.

По умолчанию этот командлет создает сеансы замыкания на себя с помощью токена сети, который может не предоставить достаточных разрешений для проверки подлинности на удаленных компьютерах.

Параметр **EnableNetworkAccess** действует только в петлевых сеансах. Если при создании сеанса на удаленном компьютере используется **EnableNetworkAccess** , команда будет выполнена, но параметр игнорируется.

Кроме того, можно включить удаленный доступ в сеансе замыкания на себя, используя значение CredSSP параметра **authentication** , которое делегирует учетные данные сеанса другим компьютерам.

Чтобы защитить компьютер от вредоносного доступа, отключенные сеансы замыкания на себя с интерактивными маркерами, которые созданы с помощью параметра **EnableNetworkAccess** , могут быть повторно подключены только с компьютера, на котором был создан сеанс. Отключенные сеансы, использующие проверку подлинности CredSSP, можно повторно подключить с других компьютеров. Для получения дополнительной информации см. `Disconnect-PSSession`.

Этот параметр появился в PowerShell 3,0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName, Uri, Session
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HostName

Указывает массив имен компьютеров для подключения на основе Secure Shell (SSH). Это похоже на параметр ComputerName, за исключением того, что подключение к удаленному компьютеру выполняется с помощью SSH, а не Windows WinRM.

Этот параметр появился в PowerShell 6,0.

```yaml
Type: System.String[]
Parameter Sets: SSHHost
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyFilePath

Указывает путь к файлу ключа, используемый Secure Shell (SSH) для проверки подлинности пользователя на удаленном компьютере.

SSH позволяет выполнять проверку подлинности пользователя с помощью закрытых и открытых ключей в качестве альтернативы обычной проверке пароля. Если на удаленном компьютере настроена проверка подлинности с помощью ключа, этот параметр можно использовать для предоставления ключа, определяющего пользователя.

Этот параметр появился в PowerShell 6,0.

```yaml
Type: System.String
Parameter Sets: SSHHost
Aliases: IdentityFilePath

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Указывает понятное имя для **PSSession**.

Имя можно использовать для ссылки на **PSSession** при использовании других командлетов, таких как `Get-PSSession` и `Enter-PSSession` . Имя не обязательно должно быть уникальным для компьютера или текущего сеанса.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Port

Задает сетевой порт на удаленном компьютере, используемый для данного соединения. Для подключения к удаленному компьютеру требуется, чтобы он прослушивал порт, используемый соединением. Порты по умолчанию — 5985, то есть порт WinRM для HTTP, а 5986 — порт WinRM для HTTPS.

Прежде чем использовать другой порт, необходимо настроить прослушиватель WinRM на удаленном компьютере для прослушивания этого порта. Для настройки прослушивателя используйте следующие команды:

1. `winrm delete winrm/config/listener?Address=*+Transport=HTTP`
2. `winrm create winrm/config/listener?Address=*+Transport=HTTP @{Port="\<port-number\>"}`

Не используйте параметр **Port** , если этого можно избежать. Настройка порта в команде применяется ко всем компьютерам или сеансам, на которых выполняется команда. Альтернативный порт может помешать выполнению команды на всех компьютерах.

```yaml
Type: System.Int32
Parameter Sets: ComputerName, SSHHost
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Рунасадминистратор

Указывает, что **сеанс PSSession** запускается от имени администратора.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ContainerId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Session

Указывает массив объектов **PSSession** , который используется этим командлетом в качестве модели для нового **сеанса PSSession**. Этот параметр создает новые объекты **PSSession** , имеющие те же свойства, что и указанные объекты **PSSession** .

Введите переменную, содержащую объекты **PSSession** , или команду, которая создает или получает объекты **PSSession** , такие как `New-PSSession` `Get-PSSession` команда или.

Итоговые объекты **PSSession** имеют те же имя компьютера, имя приложения, URI подключения, порт, имя конфигурации, предел регулирования и SSL (SSL) в качестве исходных значений, но имеют разные отображаемые имя, идентификатор и идентификатор экземпляра (GUID).

```yaml
Type: System.Management.Automation.Runspaces.PSSession[]
Parameter Sets: Session
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -SessionOption

Задает дополнительные параметры для сеанса. Введите объект **SessionOption** , например, созданный с помощью `New-PSSessionOption` командлета, или хэш-таблицу, в которой ключи являются именами параметров сеанса, а значения — значениями параметров сеанса.

Значения по умолчанию для параметров определяются значением `$PSSessionOption` привилегированной переменной, если оно задано. В противном случае значения по умолчанию задаются параметрами, указанными в конфигурации сеанса.

Значения параметров сеанса имеют приоритет над значениями по умолчанию для сеансов, заданных в `$PSSessionOption` переменной предпочтений и в конфигурации сеанса. Однако они не имеют приоритет над максимальными значениями, квотами и ограничениями, заданными в конфигурации сеанса.

Описание параметров сеанса, содержащих значения по умолчанию, см. в разделе `New-PSSessionOption` . Дополнительные сведения о `$PSSessionOption` переменной предпочтений см. в разделе [about_Preference_Variables](About/about_Preference_Variables.md). Дополнительные сведения о конфигурациях сеансов см. в разделе [about_Session_Configurations](About/about_Session_Configurations.md).

```yaml
Type: System.Management.Automation.Remoting.PSSessionOption
Parameter Sets: ComputerName, Uri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Сшконнектион

Этот параметр принимает массив хэш-таблиц, где каждая таблица Hashtable содержит один или несколько параметров соединения, необходимых для установления подключения Secure Shell (имя узла, порт, имя пользователя, KeyFilePath).

Параметры соединения Hashtable аналогичны параметрам, заданным для набора параметров **HostName** .

Параметр **сшконнектион** полезен для создания нескольких сеансов, в которых каждому сеансу требуются разные сведения о соединении.

Этот параметр появился в PowerShell 6,0.

```yaml
Type: System.Collections.Hashtable[]
Parameter Sets: SSHHostHashParam
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Сштранспорт

Указывает, что удаленное подключение устанавливается с помощью Secure Shell (SSH).

По умолчанию PowerShell использует Windows WinRM для подключения к удаленному компьютеру. Этот параметр заставляет PowerShell использовать набор параметров HostName для установления удаленного подключения на основе SSH.

Этот параметр появился в PowerShell 6,0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SSHHost
Aliases:
Accepted values: true

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

Указывает максимальное число одновременных подключений, которые можно установить для запуска этой команды.
Если этот параметр не указан или введено значение 0 (ноль), используется значение по умолчанию — 32.

Предел регулирования применяется только к текущему командлету, а не к сеансу или компьютеру.

```yaml
Type: System.Int32
Parameter Sets: ComputerName, Uri, VMId, VMName, Session, ContainerId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserName

Указывает имя пользователя для учетной записи, используемой для создания сеанса на удаленном компьютере. Метод проверки подлинности пользователя зависит от того, как Secure Shell (SSH) настроен на удаленном компьютере.

Если для протокола SSH настроена обычная проверка подлинности по паролю, вам будет предложено ввести пароль пользователя.

Если протокол SSH настроен для проверки подлинности пользователя на основе ключей, то путь к файлу ключа можно указать с помощью параметра KeyFilePath. при этом запрос на ввод пароля не будет выполняться. Обратите внимание, что если файл ключа пользователя клиента находится в известном расположении SSH, параметр KeyFilePath не требуется для проверки подлинности на основе ключей, а проверка подлинности пользователя выполняется автоматически на основе имени пользователя. Дополнительные сведения см. в документации по протоколу SSH для проверки подлинности пользователя на основе ключа.

Этот параметр не является обязательным. Если параметр UserName не указан, то для соединения используется текущее имя пользователя для входа.

Этот параметр появился в PowerShell 6,0.

```yaml
Type: System.String
Parameter Sets: SSHHost
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseSSL

Указывает, что этот командлет использует протокол SSL для установления соединения с удаленным компьютером.
По умолчанию SSL не используется.

WS-Management шифрует все содержимое PowerShell, передаваемое по сети. Параметр **UseSSL** обеспечивает дополнительную защиту, которая отправляет данные по HTTPS-соединению, а не по HTTP.

Если вы используете этот параметр, но протокол SSL недоступен для порта, используемого для команды, команда завершается ошибкой.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### — VMId

Указывает массив ИДЕНТИФИКАТОРов виртуальных машин. Этот командлет запускает интерактивный сеанс с каждой из указанных виртуальных машин. Чтобы просмотреть доступные виртуальные машины, используйте следующую команду:

`Get-VM | Select-Object -Property Name, ID`

```yaml
Type: System.Guid[]
Parameter Sets: VMId
Aliases: VMGuid

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VMName

Указывает массив имен виртуальных машин. Этот командлет запускает интерактивный сеанс с каждой из указанных виртуальных машин. Чтобы просмотреть доступные виртуальные машины, используйте `Get-VM` командлет.

```yaml
Type: System.String[]
Parameter Sets: VMName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -HostName

Указывает массив имен компьютеров для подключения на основе Secure Shell (SSH). Это похоже на параметр ComputerName, за исключением того, что подключение к удаленному компьютеру выполняется с помощью SSH, а не Windows WinRM.
Этот параметр поддерживает указание имени пользователя и/или порта в качестве части значения параметра имени узла с помощью формы `user@hostname:port` .
Имя пользователя и (или) порт, указанный как часть имени узла, имеет приоритет над `-UserName` параметрами и `-Port` , если они заданы.
Это позволяет передавать этому параметру несколько имен компьютеров, где некоторые имеют определенные имена пользователей и (или) порты, а другие используют имя пользователя и (или) порт `-UserName` из `-Port` параметров и.

Этот параметр появился в PowerShell 6,0.

```yaml
Type: System.String[]
Parameter Sets: HostName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyFilePath

Указывает путь к файлу ключа, используемый Secure Shell (SSH) для проверки подлинности пользователя на удаленном компьютере.

SSH позволяет выполнять проверку подлинности пользователя с помощью закрытых и открытых ключей в качестве альтернативы обычной проверке пароля. Если на удаленном компьютере настроена проверка подлинности с помощью ключа, этот параметр можно использовать для предоставления ключа, определяющего пользователя.

Этот параметр появился в PowerShell 6,0.

```yaml
Type: System.String
Parameter Sets: HostName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Сштранспорт

Указывает, что удаленное подключение устанавливается с помощью Secure Shell (SSH).

По умолчанию PowerShell использует Windows WinRM для подключения к удаленному компьютеру. Этот параметр заставляет PowerShell использовать набор параметров HostName для установления удаленного подключения на основе SSH.

Этот параметр появился в PowerShell 6,0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: HostName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserName

Указывает имя пользователя для учетной записи, используемой для создания сеанса на удаленном компьютере. Метод проверки подлинности пользователя зависит от того, как Secure Shell (SSH) настроен на удаленном компьютере.

Если для протокола SSH настроена обычная проверка подлинности по паролю, вам будет предложено ввести пароль пользователя.

Если протокол SSH настроен для проверки подлинности пользователя на основе ключей, то путь к файлу ключа можно указать с помощью параметра KeyFilePath. при этом запрос на ввод пароля не будет выполняться. Обратите внимание, что если файл ключа пользователя клиента находится в известном расположении SSH, параметр KeyFilePath не требуется для проверки подлинности на основе ключей, а проверка подлинности пользователя выполняется автоматически на основе имени пользователя. Дополнительные сведения см. в документации по протоколу SSH для проверки подлинности пользователя на основе ключа.

Этот параметр не является обязательным. Если параметр UserName не указан, то для соединения используется текущее имя пользователя для входа.

Этот параметр появился в PowerShell 6,0.

```yaml
Type: System.String
Parameter Sets: HostName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Сшконнектион

Этот параметр принимает массив хэш-таблиц, где каждая таблица Hashtable содержит один или несколько параметров соединения, необходимых для установления подключения Secure Shell (имя узла, порт, имя пользователя, KeyFilePath, подсистема).

Параметры соединения Hashtable аналогичны параметрам, заданным для набора параметров **HostName** .
Обратите внимание, что порядок ключей в хэш-таблице приводит к тому, что имя пользователя и порт используются для соединения, в котором используется последнее указанное значение.  Например, если используется `@{UserName="first";HostName="second@host"}` , `second` будет использоваться имя пользователя.  Однако если используется `@{HostName="second@host:22";Port=23}` , будет использоваться порт 23.

Этот параметр появился в PowerShell 6,0.

Параметр **сшконнектион** полезен для создания нескольких сеансов, в которых каждому сеансу требуются разные сведения о соединении.

```yaml
Type: hashtable
Parameter Sets: SSHConnection
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Подсистема

Указывает подсистему SSH, используемую для нового **сеанса PSSession**.

Указывает подсистему для использования в целевом объекте, как определено в sshd_config.
Подсистема запускает определенную версию PowerShell с предопределенными параметрами.
Если указанная подсистема не существует на удаленном компьютере, команда завершается ошибкой.

Если этот параметр не используется, по умолчанию используется подсистема PowerShell.

```yaml
Type: System.String
Parameter Sets: HostName
Aliases:

Required: False
Position: Named
Default value: powershell
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. Дополнительные сведения см. в разделе about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.String, System.URI, System.Management.Automation.Runspaces.PSSession

В этот командлет можно передать строку, URI или объект сеанса.

## Выходные данные

### System.Management.Automation.Runspaces.PSSession

## ПРИМЕЧАНИЯ

- Этот командлет использует инфраструктуру удаленного взаимодействия PowerShell. Для использования этого командлета локальный компьютер и все удаленные компьютеры должны быть настроены для удаленного взаимодействия PowerShell. Дополнительные сведения см. в разделе [about_Remote_Requirements](About/about_Remote_Requirements.md).
- Чтобы создать **сеанс PSSession** на локальном компьютере, запустите PowerShell с параметром Запуск от имени администратора.
- По завершении работы с **PSSession** используйте `Remove-PSSession` командлет, чтобы удалить **сеанс PSSession** и освободить его ресурсы.
- Наборы параметров **HostName** и **сшконнектион** были добавлены начиная с PowerShell 6,0.
  Они были добавлены для обеспечения удаленного взаимодействия PowerShell на основе Secure Shell (SSH). SSH и PowerShell поддерживаются на нескольких платформах (Windows, Linux, macOS) и удаленное взаимодействие PowerShell будет работать на этих платформах, где установлены и настроены PowerShell и SSH. Это отдельно от предыдущего удаленного взаимодействия только в Windows, основанного на WinRM, и многие функции и ограничения WinRM не применяются. Например, квоты на основе WinRM, параметры сеанса, конфигурация пользовательской конечной точки и функции отключения и повторного подключения сейчас не поддерживаются. Дополнительные сведения о настройке удаленного взаимодействия PowerShell с использованием SSH см. в статье [удаленное взаимодействие PowerShell через SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).

## Связанные ссылки

[Connect-PSSession](Connect-PSSession.md)

[Disconnect-PSSession](Disconnect-PSSession.md)

[Enter-PSSession](Enter-PSSession.md)

[Exit-PSSession;](Exit-PSSession.md)

[Get-PSSession](Get-PSSession.md)

[Invoke-Command](Invoke-Command.md)

[Receive-PSSession](Receive-PSSession.md)

[Remove-PSSession](Remove-PSSession.md)
