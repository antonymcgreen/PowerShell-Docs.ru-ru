---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 03/31/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/new-wsmaninstance?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-WSManInstance
ms.openlocfilehash: cab18c513be5427f06165ae0558ad87653d23e35
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "93229953"
---
# New-WSManInstance

## Краткий обзор
Создает новый экземпляр ресурса управления.

## SYNTAX

### ComputerName (по умолчанию)

```
New-WSManInstance [-ApplicationName <String>] [-ComputerName <String>] [-FilePath <String>]
 [-OptionSet <Hashtable>] [-Port <Int32>] [-ResourceURI] <Uri> [-SelectorSet] <Hashtable>
 [-SessionOption <SessionOption>] [-UseSSL] [-ValueSet <Hashtable>] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

### URI

```
New-WSManInstance [-ConnectionURI <Uri>] [-FilePath <String>] [-OptionSet <Hashtable>] [-ResourceURI] <Uri>
 [-SelectorSet] <Hashtable> [-SessionOption <SessionOption>] [-ValueSet <Hashtable>]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

## DESCRIPTION

`New-WSManInstance`Командлет создает новый экземпляр ресурса управления. Для создания нового экземпляра ресурса управления он использует URI ресурса и заданное значение или входной файл.

Для создания экземпляра ресурса управления этот командлет использует соединение/транспортный уровень службы удаленного управления Windows.

## Примеры

### Пример 1. Создание прослушивателя HTTPS

Эта команда создает экземпляр прослушивателя HTTPS WS-Management для всех IP-адресов.

```powershell
New-WSManInstance winrm/config/Listener -SelectorSet @{Transport='HTTPS'; Address='*'} -ValueSet @{Hostname="HOST";CertificateThumbprint="XXXXXXXXXX"}
```

## PARAMETERS

### -ApplicationName

Указывает имя приложения в соединении. Значением параметра **applicationName** по умолчанию является **WSMan** . Полный идентификатор для удаленной конечной точки имеет следующий формат:

`<transport>://<server>:<port>/<ApplicationName>`

Пример:

`http://server01:8080/WSMAN`

Службы IIS, где размещен сеанс, перенаправляют запросы с этой конечной точки в заданное приложение. Этот параметр по умолчанию **WSMan** подходит для большинства применений. Он предназначен для использования в ситуации, когда много компьютеров устанавливают удаленное подключение к одному компьютеру, на котором выполняется Windows PowerShell. В данном случае для повышения эффективности в службах IIS размещены веб-службы для управления (WS-Management).

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases:

Required: False
Position: Named
Default value: Wsman
Accept pipeline input: False
Accept wildcard characters: False
```

### -Authentication

Задает способ проверки подлинности, используемый на сервере. Возможны следующие значения:

- Базовый: базовый — это схема, в которой имя пользователя и пароль отправляются открытым текстом на сервер или на прокси.
- По умолчанию: используйте метод проверки подлинности, реализованный протоколом WS-Management. Это значение по умолчанию.
- Digest — это схема запроса и ответа, использующая указанную сервером строку данных в качестве запроса.
- Kerberos: клиентский компьютер и сервер выполняют взаимную проверку подлинности с помощью сертификатов Kerberos.
- Negotiate — это схема запроса и ответа, которая согласовывает с сервером или прокси-сервером ту схему, которую нужно использовать для аутентификации. Например, значение этого параметра позволяет согласованию определить, используется ли протокол Kerberos или NTLM.
- CredSSP — использование аутентификации CredSSP, которая позволяет пользователю делегировать учетные данные. Этот параметр предназначен для команд, которые выполняются на одном удаленном компьютере, но собирают данные или выполняют дополнительные команды на других удаленных компьютерах.

> [!CAUTION]
> CredSSP делегирует учетные данные пользователя с локального компьютера на удаленный компьютер. Это повышает угрозу безопасности при работе в удаленном режиме. Если удаленный компьютер скомпрометирован, то передаваемые на него учетные данные могут быть использованы для управления сетевым сеансом.

```yaml
Type: Microsoft.WSMan.Management.AuthenticationMechanism
Parameter Sets: (All)
Aliases: auth, am
Accepted values: None, Default, Digest, Negotiate, Basic, Kerberos, ClientCertificate, Credssp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CertificateThumbprint

Задает цифровой сертификат с открытым ключом (X509) учетной записи пользователя, который располагает разрешением для выполнения этого действия. Введите отпечаток сертификата.

Сертификаты используются при проверке подлинности на основе сертификата клиента. Они могут сопоставляться только с учетными записями локальных пользователей и не работают с учетными записями доменов.

Чтобы получить отпечаток сертификата, используйте `Get-Item` `Get-ChildItem` команду или на диске PowerShell CERT:.

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

### -ComputerName

Задает имя компьютера, для которого требуется выполнить операцию управления. Значение может быть полным доменным именем, NetBIOS-именем или IP-адресом. Используйте имя локального компьютера, localhost или точку ( `.` ), чтобы указать локальный компьютер. Локальный компьютер используется по умолчанию. Если удаленный компьютер находится в другом домене по отношению к пользователю, необходимо использовать полное имя домена. Можно передать значение этого параметра в командлет.

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases: cn

Required: False
Position: Named
Default value: Localhost
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConnectionURI

Указывает конечную точку соединения.
Строки имеют следующий формат:

`<Transport>://<Server>:<Port>/<ApplicationName>`

Следующая строка представляет собой правильно отформатированное значение для этого параметра:

`http://Server01:8080/WSMAN`

Значение URI должно быть указано полностью.

```yaml
Type: System.Uri
Parameter Sets: URI
Aliases: CURI, CU

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Указывает учетную запись пользователя с разрешением на выполнение этого действия. По умолчанию используется текущий пользователь. Введите имя пользователя, например "User01", "Domain01\User01" или " User@Domain.com ". Или введите объект PSCredential, например, возвращаемый `Get-Credential` командлетом. При вводе имени пользователя появится приглашение ввести пароль.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases: cred, c

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FilePath

Указывает путь к файлу, который используется для создания ресурса управления. Ресурс управления указывается с помощью параметра **resourceUri** и параметра **selector** . Например, следующая команда использует параметр **File** :

`Invoke-WSManAction -Action stopservice -ResourceUri wmi/cimv2/Win32_Service -SelectorSet @{Name="spooler"} -File c:\input.xml -Authentication Default`

Эта команда вызывает метод **«не используется» в** службе диспетчера очереди, используя входные данные из файла. Файл `Input.xml` содержит следующее содержимое:

`<p:StopService_INPUT xmlns:p="http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service" />`

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Path

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OptionSet

Передает набор параметров в службу, чтобы изменить или уточнить характер запроса. Это похоже на ключи, используемые в оболочках командной строки, поскольку они зависят от конкретной службы. Можно указать любое количество параметров.

В следующем примере демонстрируется синтаксис, который передает значения 1, 2 и 3 для параметров a, b и c:

`-OptionSet @{a=1;b=2;c=3}`

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases: os

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Port

Указывает порт, используемый при подключении клиента к службе удаленного управления Windows. Если транспортом является HTTP, порт по умолчанию равен 80. Если транспортом является HTTPS, порт по умолчанию равен 443.

При использовании протокола HTTPS в качестве транспорта значение параметра **ComputerName** должно совпадать с общим именем сертификата сервера (CN). Но если параметр **SkipCNCheck** указан в составе параметра **SessionOption** , то общее имя сертификата сервера может отличаться от имени узла сервера. Параметр **SkipCNCheck** следует использовать только для доверенных компьютеров.

```yaml
Type: System.Int32
Parameter Sets: ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceURI

Содержит универсальный код ресурса (URI) для класса или экземпляра ресурса. URI используется для идентификации определенного типа ресурсов, например дисков и процессов на компьютере.

URI состоит из префикса и пути к ресурсу. Пример:

`http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_LogicalDisk`

`http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/CIM_NumericSensor`

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases: ruri

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SelectorSet

Задает набор пар значений, используемых для выбора определенных экземпляров ресурсов управления. Параметр **selector** используется, если существует более одного экземпляра ресурса. Значение параметра набора **selector** должно быть хэш-таблицей.

В следующем примере показано, как ввести значение для этого параметра:

`-SelectorSet @{Name="WinRM";ID="yyy"}`

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SessionOption

Определяет набор расширенных параметров для сеанса WS-Management. Введите объект **SessionOption** , созданный с помощью `New-WSManSessionOption` командлета. Дополнительные сведения о доступных параметрах см. в разделе `New-WSManSessionOption` .

```yaml
Type: Microsoft.WSMan.Management.SessionOption
Parameter Sets: (All)
Aliases: so

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseSSL

Указывает, что для подключения к удаленному компьютеру следует использовать протокол SSL. По умолчанию SSL не используется.

WS-Management шифрует все содержимое Windows PowerShell, передаваемое по сети. Параметр **UseSSL** позволяет указать дополнительную защиту протокола HTTPS вместо HTTP. Если протокол SSL недоступен в порту, используемом для установки соединения, и вы указываете этот параметр, команда завершается с ошибкой.

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

### -Value

Указывает хэш-таблицу, помогающую изменить ресурс управления. Ресурс управления указывается с помощью параметра **resourceUri** и параметра **selector** . Значение параметра набора **значений** должно быть хэш-таблицей.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## Входные данные

### Нет

Этот командлет не принимает никаких входных данных.

## Выходные данные

### Нет

Этот командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

Командлет `Set-WmiInstance` , командлет инструментарий управления Windows (WMI) (WMI), аналогичен.
`Set-WmiInstance` использует DCOM-соединение/транспортный уровень для создания или обновления экземпляров WMI.

## Связанные ссылки

[Connect-WSMan](Connect-WSMan.md)

[Disable-WSManCredSSP](Disable-WSManCredSSP.md)

[Disconnect-WSMan](Disconnect-WSMan.md)

[Enable-WSManCredSSP](Enable-WSManCredSSP.md)

[Get-WSManCredSSP](Get-WSManCredSSP.md)

[Get-WSManInstance](Get-WSManInstance.md)

[Invoke-WSManAction](Invoke-WSManAction.md)

[New-WSManSessionOption](New-WSManSessionOption.md)

[Remove-WSManInstance](Remove-WSManInstance.md)

[Set-WSManInstance](Set-WSManInstance.md)

[Set-WSManQuickConfig](Set-WSManQuickConfig.md)

[Test-WSMan](Test-WSMan.md)
