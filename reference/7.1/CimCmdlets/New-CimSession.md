---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/new-cimsession?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-CimSession
ms.openlocfilehash: eaf64fd0cbd8d0bcac5e77a72a51b2d2657a3c12
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229574"
---
# New-CimSession

## Краткий обзор

Создает сеанс CIM.

## SYNTAX

### Кредентиалпараметерсет (по умолчанию)

```
New-CimSession [-Authentication <PasswordAuthenticationMechanism>] [[-Credential] <PSCredential>]
 [[-ComputerName] <String[]>] [-Name <String>] [-OperationTimeoutSec <UInt32>] [-SkipTestConnection]
 [-Port <UInt32>] [-SessionOption <CimSessionOptions>] [<CommonParameters>]
```

### цертификатепараметерсет

```
New-CimSession [-CertificateThumbprint <String>] [[-ComputerName] <String[]>] [-Name <String>]
 [-OperationTimeoutSec <UInt32>] [-SkipTestConnection] [-Port <UInt32>]
 [-SessionOption <CimSessionOptions>] [<CommonParameters>]
```

## DESCRIPTION

`New-CimSession`Командлет создает сеанс CIM. Сеанс CIM — это клиентский объект, представляющий подключение к локальному компьютеру или удаленному компьютеру. Сеанс CIM содержит сведения о соединении, например **ComputerName** , используемый протокол или различные идентификаторы.

Этот командлет возвращает объект сеанса CIM, который может использоваться всеми другими командлетами CIM.

## Примеры

### Пример 1. Создание сеанса CIM с параметрами по умолчанию

В этом примере создается локальный сеанс CIM с параметрами по умолчанию. Если параметр **ComputerName** не указан, `New-CimSession` создает сеанс DCOM на локальном компьютере.

```powershell
New-CimSession
```

### Пример 2. Создание сеанса CIM для определенного компьютера

В этом примере создается сеанс CIM для компьютера, указанного параметром **ComputerName** .
По умолчанию `New-CimSession` создает сеанс WSMan при указании **ComputerName** .

```powershell
New-CimSession -ComputerName Server01
```

### Пример 3. Создание сеанса CIM для нескольких компьютеров

В этом примере создается сеанс CIM для каждого компьютера, указанного параметром **ComputerName** , в списке с разделителями-запятыми.

```powershell
New-CimSession -ComputerName Server01,Server02,Server03
```

### Пример 4. Создание сеанса CIM с понятным именем

В этом примере создается удаленный сеанс CIM для каждого из компьютеров, указанных параметром **ComputerName** , в списке с разделителями-запятыми и назначается понятное имя новым сеансам путем указания **имени** .

```powershell
New-CimSession -ComputerName Server01,Server02 -Name FileServers
Get-CimSession -Name File*
```

Понятное имя сеанса CIM можно использовать для ссылки на сеанс в других командлетах CIM, например [Get-CimSession](Get-CimSession.md).

### Пример 5. Создание сеанса CIM для компьютера с помощью объекта PSCredential

В этом примере создается сеанс CIM с компьютером, указанным в параметре **ComputerName** , с использованием объекта **PSCredential** , указанного в параметре **Credential** , и типа проверки подлинности, заданного **проверкой подлинности** .

```powershell
New-CimSession -ComputerName Server01 -Credential $cred -Authentication Negotiate
```

Объект **PSCredential** можно создать с помощью [`Get-Credential`](../Microsoft.PowerShell.Security/Get-Credential.md) командлета.

### Пример 6. Создание сеанса CIM для компьютера с помощью определенного порта

В этом примере создается сеанс CIM для компьютера, указанного параметром **ComputerName** , с использованием TCP-порта, заданного **портом** .

```powershell
New-CimSession -ComputerName Server01 -Port 1234
```

### Пример 7. Создание сеанса CIM с помощью DCOM

В этом примере создается сеанс CIM с использованием протокола DCOM, а не WSMan.

```powershell
$SessionOption = New-CimSessionOption -Protocol DCOM
New-CimSession -ComputerName Server1 -SessionOption $SessionOption
```

## PARAMETERS

### -Authentication

Указывает тип проверки подлинности, используемый для учетных данных пользователя. Допустимые значения для этого параметра:

- По умолчанию
- Digest (дайджест)
- Согласование
- Базовый
- Kerberos
- нтлмдомаин
- CredSsp

Тип проверки подлинности **нтлмдомаин** нельзя использовать для подключения к локальному компьютеру. Проверка подлинности **CredSSP** доступна только в Windows Vista, windows Server 2008 и более поздних версиях Windows.

> [!CAUTION]
> Проверка подлинности поставщика службы безопасности учетных данных (CredSSP) предназначена для команд, требующих проверки подлинности в нескольких ресурсах, например для доступа к удаленной сетевой папке. Этот механизм повышает риск безопасности удаленной операции. Если удаленный компьютер скомпрометирован, учетные данные, передаваемые ему, могут использоваться для управления сетевым сеансом.

```yaml
Type: Microsoft.Management.Infrastructure.Options.PasswordAuthenticationMechanism
Parameter Sets: CredentialParameterSet
Aliases:
Accepted values: Default, Digest, Negotiate, Basic, Kerberos, NtlmDomain, CredSsp

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CertificateThumbprint

Указывает сертификат цифрового открытого ключа (X. 509) учетной записи пользователя, имеющей разрешение на выполнение этого действия. Введите отпечаток сертификата.

Сертификаты используются при проверке подлинности на основе сертификата клиента. Они могут сопоставляться только с учетными записями локальных пользователей и не работают с учетными записями доменов.

Чтобы получить отпечаток сертификата, используйте [`Get-Item`](../Microsoft.Powershell.Management/Get-Item.md) [`Get-ChildItem`](../Microsoft.Powershell.Management/Get-ChildItem.md) командлеты или в поставщике сертификатов PowerShell.

Дополнительные сведения см. в разделе [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md).

```yaml
Type: System.String
Parameter Sets: CertificateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ComputerName

Указывает имя компьютера, на котором создается сеанс CIM. Укажите одно имя компьютера или несколько имен компьютеров, разделенные запятыми.

Если параметр **ComputerName** не указан, создается сеанс CIM для локального компьютера. Можно указать значение имени компьютера в одном из следующих форматов:

- Одно или несколько имен NetBIOS
- Один или несколько IP-адресов
- Одно или несколько полных доменных имен.

Если компьютер находится в домене, отличном от домена пользователя, необходимо указать полное доменное имя.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN, ServerName

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Credential

Указывает учетную запись пользователя с разрешением на выполнение этого действия. Если **учетные данные** не указаны, используется текущая учетная запись пользователя.

Укажите значение **учетных данных** в одном из следующих форматов:

- Имя пользователя: "User01"
- Имя домена и имя пользователя: "Domain01\User01"
- Имя участника-пользователя: " User@Domain.com "
- Объект PSCredential, например, возвращаемый [`Get-Credential`](../Microsoft.PowerShell.Security/Get-Credential.md) командлетом.

При вводе имени пользователя запрашивается пароль.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: CredentialParameterSet
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Указывает понятное имя для сеанса CIM.

Имя можно использовать для ссылки на сеанс CIM при использовании других командлетов, например командлета [Get-CimSession](Get-CimSession.md) .
Имя не обязательно должно быть уникальным для компьютера или текущего сеанса.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Оператионтимеаутсек

Длительность, в течение которого командлет ожидает ответа от сервера.

По умолчанию значение этого параметра равно 0, что означает, что командлет использует значение времени ожидания по умолчанию для сервера.

Если для параметра **оператионтимеаутсек** задано значение меньше, чем значение времени ожидания повторного подключения, равное 3 минутам, сбои в работе сети, которые больше значения параметра **оператионтимеаутсек** , не могут быть восстановлены, так как время ожидания операции на сервере истекло до того, как клиент сможет повторно подключиться.

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases: OT

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Port

Задает сетевой порт на удаленном компьютере, используемый для данного соединения. Для подключения к удаленному компьютеру требуется, чтобы он прослушивал порт, используемый соединением. Порты по умолчанию: 5985 (порт службы удаленного управления Windows для HTTP) и 5986 (порт службы удаленного управления Windows для HTTPS).

Прежде чем использовать альтернативный порт, необходимо настроить прослушиватель WinRM на удаленном компьютере для прослушивания по этому порту. Для настройки прослушивателя используйте следующие команды:

`winrm delete winrm/config/listener?Address=*+Transport=HTTP`

`winrm create winrm/config/listener?Address=*+Transport=HTTP @{Port="\<port-number>"}`

Не используйте параметр **Port** , если этого можно избежать. Настройка порта в команде применяется ко всем компьютерам или сеансам, на которых выполняется команда. Альтернативный порт может помешать выполнению команды на всех компьютерах.

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SessionOption

Задает дополнительные параметры для нового сеанса CIM. Введите имя объекта **Цимсессионоптион** , созданного с помощью [`New-CimSessionOption`](New-CimSessionOption.md) командлета.

```yaml
Type: Microsoft.Management.Infrastructure.Options.CimSessionOptions
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Скиптестконнектион

По умолчанию `New-CimSession` командлет устанавливает подключение к удаленной конечной точке WS-Management по двум причинам: чтобы убедиться, что удаленный сервер прослушивает номер порта, указанный с помощью параметра **Port** , и проверить указанные учетные данные учетной записи. Проверка выполняется с помощью стандартной операции WS-Identity. Можно добавить параметр **скиптестконнектион** , если конечная точка удаленного WS-Management не может использовать WS-Identify или сократить время передачи данных.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## Входные данные

### Нет

Этот командлет не принимает входные данные.

## Выходные данные

### Microsoft.Management.Infrastructure.CimSession

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Get-ChildItem](../Microsoft.Powershell.Management/Get-ChildItem.md)

[Get-Credential](../Microsoft.PowerShell.Security/Get-Credential.md)

[Get-Item](../Microsoft.Powershell.Management/Get-Item.md)

[Get-CimSession](Get-CimSession.md)

[Remove-CimSession](Remove-CimSession.md)

[New-CimSessionOption](New-CimSessionOption.md)

[about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md)

