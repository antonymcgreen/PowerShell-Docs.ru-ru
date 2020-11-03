---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 07/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enter-pssession?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enter-PSSession
ms.openlocfilehash: a1b87830e1a9f330b10fb3e283fa990ccff66d36
ms.sourcegitcommit: 9dddf1d2e91ebcd347fcfb7bf6ef670d49a12ab7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "93230146"
---
# Enter-PSSession

## Краткий обзор
Запускает интерактивный сеанс с удаленным компьютером.

## SYNTAX

### ComputerName (по умолчанию)

```
Enter-PSSession [-ComputerName] <String> [-EnableNetworkAccess] [[-Credential] <PSCredential>]
 [-ConfigurationName <String>] [-Port <Int32>] [-UseSSL] [-ApplicationName <String>]
 [-SessionOption <PSSessionOption>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [<CommonParameters>]
```

### сшхост

```
Enter-PSSession [-HostName] <String> [-Port <Int32>] [-UserName <String>] [-KeyFilePath <String>]
 [-SSHTransport] [<CommonParameters>]
```

### Сеанс

```
Enter-PSSession [[-Session] <PSSession>] [<CommonParameters>]
```

### URI

```
Enter-PSSession [[-ConnectionUri] <Uri>] [-EnableNetworkAccess] [[-Credential] <PSCredential>]
 [-ConfigurationName <String>] [-AllowRedirection] [-SessionOption <PSSessionOption>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

### InstanceId

```
Enter-PSSession [-InstanceId <Guid>] [<CommonParameters>]
```

### Идентификатор

```
Enter-PSSession [[-Id] <Int32>] [<CommonParameters>]
```

### Имя

```
Enter-PSSession [-Name <String>] [<CommonParameters>]
```

### VMId

```
Enter-PSSession [-VMId] <Guid> [-Credential] <PSCredential> [-ConfigurationName <String>] [<CommonParameters>]
```

### VMName

```
Enter-PSSession [-VMName] <String> [-Credential] <PSCredential> [-ConfigurationName <String>]
 [<CommonParameters>]
```

### ContainerId

```
Enter-PSSession [-ContainerId] <String> [-ConfigurationName <String>] [-RunAsAdministrator]
 [<CommonParameters>]
```

## DESCRIPTION

`Enter-PSSession`Командлет запускает интерактивный сеанс с одним удаленным компьютером.
Во время сеанса вводимые команды выполняются на удаленном компьютере, точно так же, как при вводе непосредственно на удаленном компьютере. В любой момент времени может использоваться только один интерактивный сеанс.

Как правило имя удаленного компьютера указывается с помощью параметра **ComputerName** .
Однако можно также использовать сеанс, созданный с помощью `New-PSSession` командлета для интерактивного сеанса. Однако нельзя использовать `Disconnect-PSSession` `Connect-PSSession` `Receive-PSSession` командлеты, или для отключения или повторного подключения к интерактивному сеансу.

Начиная с PowerShell 6,0 можно использовать Secure Shell (SSH) для установления подключения к удаленному компьютеру, если SSH доступен на локальном компьютере, а удаленный компьютер настроен с помощью конечной точки SSH PowerShell. Преимуществом удаленного сеанса PowerShell на основе SSH является то, что он работает на нескольких платформах (Windows, Linux, macOS). При удаленном взаимодействии на основе SSH используется параметр **HostName** , заданный для указания удаленного компьютера и соответствующих сведений о соединении. Дополнительные сведения о настройке удаленного взаимодействия PowerShell с использованием SSH см. в статье [удаленное взаимодействие PowerShell через SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).

Чтобы завершить интерактивный сеанс и отключиться от удаленного компьютера, используйте `Exit-PSSession` командлет или введите `exit` .

## Примеры

### Пример 1. Запуск интерактивного сеанса

```
PS> Enter-PSSession
[localhost]: PS>
```

Эта команда запускает интерактивный сеанс на локальном компьютере. Командная строка изменяется, показывая, что команды выполняются в рамках другого сеанса.

Вводимые команды выполняются в рамках нового сеанса, а результаты возвращаются в сеанс по умолчанию в виде текста.

### Пример 2. Работа с интерактивным сеансом

Первая команда использует `Enter-PSSession` командлет для запуска интерактивного сеанса с Server01, удаленным компьютером. При запуске сеанса в командную строку включается имя компьютера.

Вторая команда получает процесс PowerShell и перенаправляет выходные данные в файл Process.txt. Команда передается на удаленный компьютер, и файл сохраняется на удаленном компьютере.

Третья команда использует ключевое слово **Exit** для завершения интерактивного сеанса и закрытия соединения.
Четвертая команда позволяет убедиться в том, что файл Process.txt сохранен на удаленном компьютере. `Get-ChildItem`Команда ("Dir") на локальном компьютере не может найти файл.

```powershell
PS C:\> Enter-PSSession -ComputerName Server01
[Server01]: PS>
[Server01]: PS C:\> Get-Process PowerShell > C:\ps-test\Process.txt
[Server01]: PS C:\> exit
PS C:\>
PS C:\> dir C:\ps-test\process.txt
Get-ChildItem : Cannot find path 'C:\ps-test\process.txt' because it does not exist.
At line:1 char:4
+ dir <<<<  c:\ps-test\process.txt
```

Эта команда демонстрирует работу в интерактивном сеансе с удаленным компьютером.

### Пример 3. Использование параметра Session

```powershell
PS> $s = New-PSSession -ComputerName Server01
PS> Enter-PSSession -Session $s
[Server01]: PS>
```

Эти команды используют параметр **сеанса** `Enter-PSSession` для запуска интерактивного сеанса в существующем сеансе PowerShell ( **PSSession** ).

### Пример 4. Запуск интерактивного сеанса и указание параметров порта и учетных данных

```powershell
PS> Enter-PSSession -ComputerName Server01 -Port 90 -Credential Domain01\User01
[Server01]: PS>
```

Эта команда запускает интерактивный сеанс на компьютере Server01. Он использует параметр **Port** , чтобы указать порт, а параметр **Credential** — учетную запись пользователя, имеющего разрешение на подключение к удаленному компьютеру.

### Пример 5. Завершение интерактивного сеанса

```powershell
PS> Enter-PSSession -ComputerName Server01
[Server01]: PS> Exit-PSSession
PS>
```

В этом примере показано, как запускать и останавливать интерактивный сеанс. Первая команда использует `Enter-PSSession` командлет для запуска интерактивного сеанса с компьютером Server01.

Вторая команда использует `Exit-PSSession` командлет для завершения сеанса. Можно также использовать ключевое слово **Exit** для завершения интерактивного сеанса. `Exit-PSSession` и **Exit** имеют одинаковый результат.

### Пример 6. Запуск интерактивного сеанса с помощью SSH

```powershell
PS> Enter-PSSession -HostName UserA@LinuxServer01
```

В этом примере показано, как запустить интерактивный сеанс с помощью Secure Shell (SSH). Если на удаленном компьютере настроен протокол SSH для запроса паролей, вы получите запрос на ввод пароля.
В противном случае необходимо будет использовать проверку подлинности пользователя на основе ключа SSH.

### Пример 7. Запуск интерактивного сеанса с помощью SSH и указание ключа проверки подлинности порта и пользователя

```powershell
PS> Enter-PSSession -HostName UserA@LinuxServer02:22 -KeyFilePath c:\<path>\userAKey_rsa
```

В этом примере показано, как запустить интерактивный сеанс с помощью SSH. В нем используется параметр **Port** для указания используемого порта и параметр **KeyFilePath** для указания ключа RSA, используемого для проверки подлинности пользователя на удаленном компьютере.

## PARAMETERS

### -AllowRedirection

Разрешает перенаправление данного соединения на альтернативный URI. По умолчанию перенаправление не допускается.

При использовании параметра **ConnectionURI** удаленный компьютер может вернуть инструкцию для перенаправления на другой URI. По умолчанию PowerShell не перенаправляет соединения, но можно использовать этот параметр, чтобы разрешить перенаправление подключения.

Можно также ограничить количество перенаправлений соединение, изменив значение параметра сеанса **MaximumConnectionRedirectionCount** . Используйте параметр **максимумредиректион** `New-PSSessionOption` командлета или задайте свойство **MaximumConnectionRedirectionCount** `$PSSessionOption` переменной предпочтений. Значение по умолчанию — 5.

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

Определяет сегмент имени приложения в URI соединения. Используйте этот параметр, чтобы указать имя приложения, если в команде не используется параметр **ConnectionURI** .

Значение по умолчанию — это значение `$PSSessionApplicationName` привилегированной переменной на локальном компьютере. Если привилегированная переменная не определена, значение по умолчанию — WSMAN. Это значение подходит для большинства случаев Дополнительные сведения см. в разделе [about_Preference_Variables](About/about_Preference_Variables.md).

Служба **WinRM** использует имя приложения для выбора прослушивателя, который будет обслуживать запрос на подключение. Значение этого параметра должно совпадать со значением свойства **URLPrefix** прослушивателя на удаленном компьютере.

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

Задает механизм, используемый при проверке подлинности учетных данных пользователя. Допустимые значения для этого параметра:

- По умолчанию
- Базовый
- CredSSP
- Digest (дайджест)
- Kerberos
- Согласование
- NegotiateWithImplicitCredential

Значение по умолчанию — Default.

Проверка подлинности CredSSP доступна только в Windows Vista, Windows Server 2008 и более поздних версиях операционной системы Windows.

Дополнительные сведения о значениях этого параметра см. в разделе [AuthenticationMechanism enum](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).

Внимание! Аутентификация CredSSP, в рамках которой учетные данные пользователя передаются на удаленный компьютер для проверки, предназначена для команд, требующих аутентификацию нескольких ресурсов, например для доступа к удаленной сетевой папке. Этот механизм повышает риск безопасности удаленной операции. Если удаленный компьютер скомпрометирован, учетные данные, передаваемые ему, могут использоваться для управления сетевым сеансом.

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

Указывает имя компьютера. Этот командлет запускает интерактивный сеанс с указанным удаленным компьютером. Введите имя одного компьютера. По умолчанию это локальный компьютер.

Введите имя NetBIOS, IP-адрес или полное доменное имя компьютера. Можно также передать имя компьютера в `Enter-PSSession` .

Чтобы использовать IP-адрес в значении параметра **ComputerName** , команда должна включать параметр **Credential** . Кроме того, компьютер должен быть настроен для транспорта HTTPS или IP-адрес удаленного компьютера должен быть включен в список TrustedHosts службы WinRM на локальном компьютере. Инструкции по добавлению имени компьютера в список TrustedHosts см. в разделе "Добавление компьютера в список надежных узлов" в [about_Remote_Troubleshooting](About/about_Remote_Troubleshooting.md).

Примечание. в Windows Vista и более поздних версиях операционной системы Windows для включения локального компьютера в значение параметра **ComputerName** необходимо запустить PowerShell с параметром "Запуск от имени администратора".

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases: Cn

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -ConfigurationName

Задает конфигурацию сеанса, используемого для интерактивного сеанса.

Введите имя конфигурации или полное имя ресурса (URI) для конфигурации сеанса. Если указано только имя конфигурации, в начале добавляется следующий URI схемы: `http://schemas.microsoft.com/powershell` .

При использовании с SSH указывает подсистему для использования в целевом объекте, как определено в sshd_config. Значение по умолчанию для SSH — `powershell` подсистема.

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

Если не указывать **ConnectionURI** , можно использовать параметры **UseSSL** , **ComputerName** , **Port** и **ApplicationName** для задания значений **ConnectionURI** .

Допустимые значения для сегмента транспорта URI — HTTP и HTTPS. Если указать универсальный код ресурса (URI) соединения с сегментом транспорта, но не указывать порт, то сеанс создается с использованием стандартных портов: 80 для HTTP и 443 для HTTPS. Чтобы использовать порты по умолчанию для удаленного взаимодействия PowerShell, укажите порт 5985 для HTTP или 5986 для HTTPS.

Если конечный компьютер перенаправляет подключение к другому универсальному коду ресурса (URI), PowerShell предотвращает перенаправление, если в команде не используется параметр **AllowRedirection** .

```yaml
Type: System.Uri
Parameter Sets: Uri
Aliases: URI, CU

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ContainerId

Указывает идентификатор контейнера.

```yaml
Type: System.String
Parameter Sets: ContainerId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Credential

Указывает учетную запись пользователя с разрешением на выполнение этого действия. По умолчанию используется текущий пользователь.

Введите имя пользователя, например **User01** или **Domain01\User01** , либо введите объект **PSCredential** , созданный `Get-Credential` командлетом. Если ввести имя пользователя, будет предложено ввести пароль.

Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).

> [!NOTE]
> Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerName, Uri, VMId, VMName
Aliases:

Required: True (VMId, VMName), False (ComputerName, Uri)
Position: 1
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EnableNetworkAccess

Указывает, что этот командлет добавляет интерактивный маркер безопасности в сеансы замыкания на себя. Интерактивный маркер позволяет выполнять в петлевом сеансе команды, которые получают данные с других компьютеров. Например, можно выполнить команду в сеансе, который копирует XML-файлы с удаленного компьютера на локальный.

Сеанс замыкания на себя — это **PSSession** , который создается и завершается на том же компьютере. Чтобы создать сеанс замыкания на себя, опустите параметр **ComputerName** или задайте для него значение. (точка), localhost или имя локального компьютера.

По умолчанию сеансы замыкания на себя создаются с помощью токена сети, который может не предоставить достаточных разрешений для проверки подлинности на удаленных компьютерах.

Параметр **EnableNetworkAccess** действует только в петлевых сеансах. Если при создании сеанса на удаленном компьютере используется **EnableNetworkAccess** , команда будет выполнена, но параметр игнорируется.

Удаленный доступ в петлевом сеансе также можно разрешить с помощью значения **CredSSP** параметра **Authentication** , который делегирует учетные данные сеанса на другие компьютеры.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName, Uri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HostName

Указывает имя компьютера для подключения на основе Secure Shell (SSH). Это похоже на параметр **ComputerName** , за исключением того, что подключение к удаленному компьютеру выполняется с помощью SSH, а не Windows WinRM. Этот параметр поддерживает указание имени пользователя и/или порта в качестве части значения параметра имени узла с помощью формы `user@hostname:port` . Имя пользователя и (или) порт, указанный как часть имени узла, имеет приоритет над `-UserName` параметрами и `-Port` , если они заданы. Это позволяет передавать этому параметру несколько имен компьютеров, где некоторые имеют определенные имена пользователей и (или) порты, а другие используют имя пользователя и (или) порт `-UserName` из `-Port` параметров и.

Этот параметр появился в PowerShell 6,0.

```yaml
Type: System.String
Parameter Sets: SSHHost
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Id

Указывает идентификатор существующего сеанса. `Enter-PSSession` использует указанный сеанс для интерактивного сеанса.

Чтобы найти идентификатор сеанса, используйте `Get-PSSession` командлет.

```yaml
Type: System.Int32
Parameter Sets: Id
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InstanceId

Указывает идентификатор экземпляра существующего сеанса. `Enter-PSSession` использует указанный сеанс для интерактивного сеанса.

Значение идентификатора экземпляра представляет собой GUID. Чтобы найти идентификатор экземпляра сеанса, используйте `Get-PSSession` командлет. Можно также использовать параметры **Session** , **Name** или **ID** , чтобы указать существующий сеанс. Можно также использовать параметр **ComputerName** для запуска временного сеанса.

```yaml
Type: System.Guid
Parameter Sets: InstanceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

Указывает понятное имя существующего сеанса. `Enter-PSSession` использует указанный сеанс для интерактивного сеанса.

Если указанное имя соответствует сразу нескольким сеансам, команда завершается ошибкой. Можно также использовать параметры **Session** , **InstanceId** или **ID** , чтобы указать существующий сеанс. Можно также использовать параметр **ComputerName** для запуска временного сеанса.

Чтобы установить понятное имя для сеанса, используйте параметр **Name** `New-PSSession` командлета.

```yaml
Type: System.String
Parameter Sets: Name
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Port

Указывает сетевой порт на удаленном компьютере, используемый для этой команды.

В PowerShell 6,0 этот параметр был включено в наборе параметров **HostName** , который поддерживает подключения Secure Shell (SSH).

**WinRM (набор параметров ComputerName)**

Для подключения к удаленному компьютеру требуется, чтобы он прослушивал порт, используемый соединением. Порты по умолчанию — 5985, то есть порт WinRM для HTTP, а 5986 — порт WinRM для HTTPS.

Прежде чем использовать альтернативный порт, необходимо настроить прослушиватель WinRM на удаленном компьютере для прослушивания по этому порту. Для настройки прослушивателя используйте следующие команды:

1. `winrm delete winrm/config/listener?Address=*+Transport=HTTP`
2. `winrm create winrm/config/listener?Address=*+Transport=HTTP @{Port="\<port-number\>"}`

Не используйте параметр **Port** , если этого можно избежать. Настройка порта в команде применяется ко всем компьютерам или сеансам, на которых выполняется команда. Альтернативный порт может помешать выполнению команды на всех компьютерах.

**SSH (набор параметров HostName)**

Для подключения к удаленному компьютеру на удаленном компьютере должна быть настроена служба SSH (SSHD) и он должен прослушивать порт, используемый подключением. По умолчанию для SSH используется порт 22.

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

Указывает сеанс PowerShell ( **PSSession** ), используемый для интерактивного сеанса. Этот параметр принимает объект сеанса. Для указания **PSSession** можно также использовать параметры **Name** , **InstanceId** или **ID** .

Введите переменную, содержащую объект сеанса, или команду, которая создает или получает объект сеанса, например `New-PSSession` `Get-PSSession` команду или. Можно также передать объект сеанса в `Enter-PSSession` . С помощью этого параметра можно отправить только один **сеанс PSSession** . Если ввести переменную, содержащую более одного **сеанса PSSession** , команда завершится ошибкой.

При использовании `Exit-PSSession` или ключевого слова **Exit** интерактивный сеанс завершается, но созданный **сеанс PSSession** остается открытым и доступным для использования.

```yaml
Type: System.Management.Automation.Runspaces.PSSession
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

Описание параметров сеанса, включая значения по умолчанию, см. в разделе `New-PSSessionOption` .
Дополнительные сведения о `$PSSessionOption` переменной предпочтений см. в разделе [about_Preference_Variables](About/about_Preference_Variables.md). Дополнительные сведения о конфигурациях сеансов см. в разделе [about_Session_Configurations](About/about_Session_Configurations.md).

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

### -Подсистема

Указывает подсистему SSH, используемую для нового **сеанса PSSession** .

Указывает подсистему для использования в целевом объекте, как определено в sshd_config. Подсистема запускает определенную версию PowerShell с предопределенными параметрами. Если указанная подсистема не существует на удаленном компьютере, команда завершается ошибкой.

Если этот параметр не используется, по умолчанию используется подсистема PowerShell.

```yaml
Type: System.String
Parameter Sets: SSHHost
Aliases:

Required: False
Position: Named
Default value: powershell
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UserName

Указывает имя пользователя для учетной записи, используемой для создания сеанса на удаленном компьютере. Метод проверки подлинности пользователя зависит от того, как Secure Shell (SSH) настроен на удаленном компьютере.

Если для протокола SSH настроена обычная проверка подлинности по паролю, вам будет предложено ввести пароль пользователя.

Если протокол SSH настроен для проверки подлинности пользователя на основе ключей, то путь к файлу ключа можно указать с помощью параметра **KeyFilePath** . при этом запрос на ввод пароля не будет выполняться. Обратите внимание, что если файл ключа пользователя клиента находится в известном расположении SSH, параметр **KeyFilePath** не требуется для проверки подлинности на основе ключей, а проверка подлинности пользователя выполняется автоматически на основе имени пользователя. Дополнительные сведения см. в документации по протоколу SSH для проверки подлинности пользователя на основе ключа.

Этот параметр не является обязательным. Если параметр **username** не указан, то для соединения используется текущее имя пользователя для входа.

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

Указывает, что этот командлет использует протокол SSL (SSL) для установления соединения с удаленным компьютером. По умолчанию SSL не используется.

WS-Management шифрует все содержимое PowerShell, передаваемое по сети. Параметр **UseSSL** — это дополнительная защита, которая отправляет данные по HTTPS-соединению, а не по HTTP.

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

Указывает идентификатор виртуальной машины.

```yaml
Type: System.Guid
Parameter Sets: VMId
Aliases: VMGuid

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -VMName

Указывает имя виртуальной машины.

```yaml
Type: System.String
Parameter Sets: VMName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System. String, System. Management. Automation. пространства выполнения PSSession

В этот командлет можно передать по конвейеру имя компьютера в виде строки или объекта сеанса.

## Выходные данные

### Нет

Этот командлет не создает никаких выходных данных.

## ПРИМЕЧАНИЯ

Чтобы подключиться к удаленному компьютеру, необходимо быть членом группы администраторов на удаленном компьютере. Чтобы запустить интерактивный сеанс на локальном компьютере, необходимо запустить PowerShell с параметром **Запуск от имени администратора** .

При использовании `Enter-PSSession` для интерактивного сеанса используется профиль пользователя на удаленном компьютере. Команды в профиле удаленного пользователя, включая команды для добавления модулей PowerShell и изменения командной строки, выполняются перед отображением удаленного запроса.

`Enter-PSSession` использует параметр языка и региональных параметров пользовательского интерфейса на локальном компьютере для интерактивного сеанса. Чтобы найти язык и региональные параметры локального пользовательского интерфейса, используйте `$UICulture` автоматическую переменную.

`Enter-PSSession` требуются `Get-Command` `Out-Default` командлеты, и `Exit-PSSession` . Если эти командлеты не включены в конфигурацию сеанса на удаленном компьютере, команды не будут `Enter-PSSession` работать.

В отличие от `Invoke-Command` , который анализирует и интерпретирует команды перед их отправкой на удаленный компьютер, `Enter-PSSession` отправляет команды непосредственно на удаленный компьютер без интерпретации.

Если сеанс, который вы хотите ввести, занят обработкой команды, может возникнуть задержка, прежде чем PowerShell ответит на `Enter-PSSession` команду. Вы подключены сразу после того, как сеанс будет доступен. Чтобы отменить `Enter-PSSession` команду, нажмите клавиши <kbd>CTRL</kbd> + <kbd>C</kbd>.

Набор параметров **HostName** был добавлен начиная с PowerShell 6,0. Он был добавлен для обеспечения удаленного взаимодействия PowerShell на основе Secure Shell (SSH). SSH и PowerShell поддерживаются на нескольких платформах (Windows, Linux, macOS) и удаленное взаимодействие PowerShell будет работать на этих платформах, где установлены и настроены PowerShell и SSH. Это отдельно от предыдущего удаленного взаимодействия только в Windows, основанного на WinRM, и многие функции и ограничения WinRM не применяются. Например, квоты на основе WinRM, параметры сеанса, конфигурация пользовательской конечной точки и функции отключения и повторного подключения сейчас не поддерживаются. Дополнительные сведения о настройке удаленного взаимодействия PowerShell с использованием SSH см. в статье [удаленное взаимодействие PowerShell через SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).

До PowerShell 7.1 удаленное взаимодействие по SSH не поддерживало удаленные сеансы со вторым прыжком. Эта возможность была ограничена сеансами через WinRM. PowerShell 7.1 позволяет `Enter-PSSession` и `Enter-PSHostProcess` работать в любом интерактивном удаленном сеансе.

## Связанные ссылки

[Exit-PSSession;](Exit-PSSession.md)

[Get-PSSession](Get-PSSession.md)

[Invoke-Command](Invoke-Command.md)

[New-PSSession](New-PSSession.md)

[Remove-PSSession](Remove-PSSession.md)

[Connect-PSSession](Connect-PSSession.md)

[Disconnect-PSSession](Disconnect-PSSession.md)

[Receive-PSSession](Receive-PSSession.md)

[about_PSSessions](About/about_PSSessions.md)

[about_Remote](About/about_Remote.md)
