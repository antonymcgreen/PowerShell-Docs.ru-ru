---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/connect-wsman?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Connect-WSMan
ms.openlocfilehash: e22aeef7dbc7ef799127def2606a15fdccbfffe3
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93226178"
---
# Connect-WSMan

## Краткий обзор
Подключается к службе удаленного управления Windows на удаленном компьютере.

## SYNTAX

### ComputerName (по умолчанию)

```
Connect-WSMan [-ApplicationName <String>] [[-ComputerName] <String>] [-OptionSet <Hashtable>] [-Port <Int32>]
 [-SessionOption <SessionOption>] [-UseSSL] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

### URI

```
Connect-WSMan [-ConnectionURI <Uri>] [-OptionSet <Hashtable>] [-Port <Int32>] [-SessionOption <SessionOption>]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

## DESCRIPTION
Командлет **Connect-WSMan** подключается к службе WinRM на удаленном компьютере и устанавливает постоянное подключение к удаленному компьютеру.
Этот командлет можно использовать в контексте поставщика WSMan для подключения к службе WinRM на удаленном компьютере.
Однако его также можно использовать для подключения к службе удаленного управления Windows на удаленном компьютере перед изменением поставщика WSMan.
Удаленный компьютер появится в корневом каталоге поставщика WSMan.

Если клиентский и серверный компьютеры находятся в разных доменах или рабочих группах, необходимы явные учетные данные.

Сведения о том, как отключиться от службы WinRM на удаленном компьютере, см. в описании командлета Disconnect-WSMan.

## Примеры

### Пример 1. подключение к удаленному компьютеру

```
PS C:\> Connect-WSMan -ComputerName "server01"
PS C:\> cd wsman:
PS WSMan:\>
PS WSMan:\> dir
WSManConfig: Microsoft.WSMan.Management\WSMan::WSMan

ComputerName                                  Type
------------                                  ----
localhost                                     Container
server01                                      Container
```

Эта команда создает подключение к удаленному компьютеру server01.

Командлет **Connect-WSMan** обычно используется в контексте поставщика WSMan для подключения к удаленному компьютеру (в данном случае это компьютер Server01).
Однако этот командлет можно использовать для установки соединения с удаленными компьютерами перед изменением поставщика WSMan.
Эти подключения отображаются в списке **ComputerName** .

### Пример 2. подключение к удаленному компьютеру с помощью учетных данных администратора

```
PS C:\> $cred = Get-Credential Administrator
PS C:\> Connect-WSMan -ComputerName "server01" -Credential $cred
PS C:\> cd wsman:
PS WSMan:\>
PS WSMan:\> dir
WSManConfig: Microsoft.WSMan.Management\WSMan::WSMan

ComputerName                                  Type
------------                                  ----
localhost                                     Container
server01                                      Container
```

Эта команда создает подключение к удаленной системе server01 с использованием учетных данных учетной записи администратора.

Первая команда использует командлет Get-Credential, чтобы получить учетные данные администратора, и сохраняет их в переменной $cred.
**Get-Credential** запрашивает пароль пользователя и пароль в диалоговом окне или в командной строке в зависимости от параметров системного реестра.

Вторая команда использует параметр *Credential* для передачи учетных данных, хранящихся в $CRED, в **Connect-WSMan**.
**Connect-WSMan** подключается к удаленной системе Server01 с помощью учетных данных администратора.

### Пример 3. подключение к удаленному компьютеру через указанный порт

```
PS C:\> Connect-WSMan -ComputerName "server01" -Port 80
PS C:\> cd wsman:
PS WSMan:\>
PS WSMan:\> dir
WSManConfig: Microsoft.WSMan.Management\WSMan::WSMan
ComputerName                                  Type
------------                                  ----
localhost                                     Container
server01                                      Container
```

Эта команда создает подключение к удаленному компьютеру server01 через порт 80.

### Пример 4. подключение к удаленному компьютеру с помощью параметров подключения

```
PS C:\> $a = New-WSManSessionOption -OperationTimeout 30000
PS C:\> Connect-WSMan -ComputerName "server01" -SessionOption $a
PS C:\> cd wsman:
PS WSMan:\>
PS WSMan:\> dir
WSManConfig: Microsoft.WSMan.Management\WSMan::WSMan
ComputerName                                  Type
------------                                  ----
localhost                                     Container
server01                                      Container
```

В этом примере создается подключение к удаленному компьютеру Server01 с помощью параметров соединения, определенных в команде **New-WSManSessionOption** .

Первая команда использует **New-WSManSessionOption** для хранения набора параметров подключения в переменной $a.
В этом случае для параметров сеанса задано время ожидания подключения в размере 30 секунд (30 000 миллисекунд).

Вторая команда использует параметр *SessionOption* для передачи учетных данных, хранящихся в переменной $a, в **Connect-WSMan**.
Затем **Connect-WSMan** подключается к удаленному компьютеру Server01, используя указанные параметры сеанса.

## PARAMETERS

### -ApplicationName
Указывает имя приложения в соединении.
Значением параметра *applicationName* по умолчанию является WSMan.
Полный идентификатор для удаленной конечной точки имеет следующий формат:

\<transport\>://\<server\>:\<port\>/\<ApplicationName\>

Пример: `http://server01:8080/WSMAN`

Службы IIS, где размещен сеанс, перенаправляют запросы с этой конечной точки в заданное приложение.
Значение по умолчанию (WSMAN) подходит для большинства задач.
Этот параметр предназначен для использования, если многие компьютеры устанавливают удаленные подключения к одному компьютеру, на котором работает PowerShell.
В данном случае для повышения эффективности в службах IIS размещены веб-службы для управления (WS-Management).

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Authentication
Задает способ проверки подлинности, используемый на сервере.
Допустимые значения для этого параметра:

- Обычные.
схема, в которой имя пользователя и пароль отправляются на сервер или прокси-сервер в виде открытого текста.
- По умолчанию.
использование метода аутентификации, реализованного протоколом WS-Management.
Это значение по умолчанию.
- Дайджест.
это схема запроса и ответа, использующая указанную сервером строку данных в качестве запроса.
- Kerberos —
клиентский компьютер и сервер выполняют взаимную аутентификацию с использованием сертификатов Kerberos.
- Negotiate —
это схема запроса и ответа, которая согласовывает с сервером или прокси-сервером ту схему, которую нужно использовать для аутентификации.
Например, значение этого параметра позволяет согласованию определить, используется ли протокол Kerberos или NTLM.
- CredSSP —
использование проверки подлинности CredSSP, которая позволяет пользователю делегировать учетные данные.
Этот параметр предназначен для команд, которые выполняются на одном удаленном компьютере, но собирают данные или выполняют дополнительные команды на других удаленных компьютерах.

Внимание! CredSSP делегирует учетные данные пользователя с локального на удаленный компьютер.
Это повышает угрозу безопасности при работе в удаленном режиме.
Если удаленный компьютер скомпрометирован, то передаваемые на него учетные данные могут быть использованы для управления сетевым сеансом.

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
Задает цифровой сертификат с открытым ключом (X509) учетной записи пользователя, который располагает разрешением для выполнения этого действия.
Введите отпечаток сертификата.

Сертификаты используются при проверке подлинности на основе сертификата клиента.
Они могут сопоставляться только с учетными записями локальных пользователей и не работают с учетными записями доменов.

Чтобы получить отпечаток сертификата, используйте команду Get-Item или Get-ChildItem на диске с сертификатом PowerShell:.

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
Задает имя компьютера, для которого требуется выполнить операцию управления.
Значение может быть полным доменным именем, NetBIOS-именем или IP-адресом.
Для указания локального компьютера используйте его имя, localhost или точку (.).
Локальный компьютер используется по умолчанию.
Если удаленный компьютер находится в другом домене по отношению к пользователю, необходимо использовать полное имя домена.
Можно передать значение этого параметра в командлет.

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases: cn

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConnectionURI
Указывает конечную точку соединения.
Строка имеет следующий формат:

\<Transport\>://\<Server\>:\<Port\>/\<ApplicationName\>

Следующая строка представляет собой правильно отформатированное значение для этого параметра:

`http://Server01:8080/WSMAN`

Значение URI должно быть указано полностью.

```yaml
Type: System.Uri
Parameter Sets: URI
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Указывает учетную запись пользователя с разрешением на выполнение этого действия.
По умолчанию используется текущий пользователь.
Введите имя пользователя, например User01, Domain01\User01 или User@Domain.com .
Или введите объект **PSCredential** , например, возвращаемый командлетом Get-Credential.
При вводе имени пользователя этот командлет запрашивает пароль.

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

### -OptionSet
Указывает набор параметров в службе, чтобы изменить или уточнить характер запроса.
Это похоже на ключи, используемые в оболочках командной строки, так как они зависят от конкретной службы.
Можно указать любое количество параметров.

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
Указывает порт, используемый при подключении клиента к службе удаленного управления Windows.
Если транспортом является HTTP, порт по умолчанию равен 80.
Если транспортом является HTTPS, порт по умолчанию равен 443.

При использовании протокола HTTPS в качестве транспорта значение параметра *ComputerName* должно совпадать с общим именем сертификата сервера (CN).
Но если параметр *SkipCNCheck* указан в составе параметра *SessionOption* , то общее имя сертификата сервера может отличаться от имени узла сервера.
Параметр *SkipCNCheck* следует использовать только для доверенных компьютеров.

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

### -SessionOption
Определяет расширенные параметры для сеанса WS-Management.
Введите объект **SessionOption** , созданный с помощью командлета New-WSManSessionOption.
Чтобы получить дополнительные сведения о доступных параметрах, введите `Get-Help New-WSManSessionOption`.

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
Указывает, что для подключения к удаленному компьютеру используется протокол SSL.
По умолчанию SSL не используется.

WS-Management шифрует все содержимое PowerShell, передаваемое по сети.
Параметр *UseSSL* позволяет указать дополнительную защиту протокола HTTPS вместо HTTP.
Если протокол SSL недоступен в порту, используемом для установки соединения, и вы указываете этот параметр, команда завершается с ошибкой.

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

### Общие параметры
Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет
Этот командлет не принимает никаких входных данных.

## Выходные данные

### Нет
Этот командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

* Вы можете выполнять команды управления или запрашивать данные управления на удаленном компьютере без создания сеанса WS-Management. Это можно сделать с помощью параметров *ComputerName* в Invoke-WSManAction и Get-WSManInstance. При использовании параметра *ComputerName* PowerShell создает временное подключение, используемое для одной команды. После выполнения команды соединение закрывается.

*

## Связанные ссылки

[Disable-WSManCredSSP](Disable-WSManCredSSP.md)

[Disconnect-WSMan](Disconnect-WSMan.md)

[Enable-WSManCredSSP](Enable-WSManCredSSP.md)

[Get-WSManCredSSP](Get-WSManCredSSP.md)

[Get-WSManInstance](Get-WSManInstance.md)

[Invoke-WSManAction](Invoke-WSManAction.md)

[New-WSManInstance](New-WSManInstance.md)

[New-WSManSessionOption](New-WSManSessionOption.md)

[Remove-WSManInstance](Remove-WSManInstance.md)

[Set-WSManInstance](Set-WSManInstance.md)

[Set-WSManQuickConfig](Set-WSManQuickConfig.md)

[Test-WSMan](Test-WSMan.md)
