---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/set-wsmaninstance?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WSManInstance
ms.openlocfilehash: 3f4ee9edf6e8dfce21a51ff9c055fe56a0cbef3c
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "93229938"
---
# Set-WSManInstance

## Краткий обзор
Изменяет данные управления, связанные с ресурсом.

## SYNTAX

### ComputerName (по умолчанию)

```
Set-WSManInstance [-ApplicationName <String>] [-ComputerName <String>] [-Dialect <Uri>] [-FilePath <String>]
 [-Fragment <String>] [-OptionSet <Hashtable>] [-Port <Int32>] [-ResourceURI] <Uri>
 [[-SelectorSet] <Hashtable>] [-SessionOption <SessionOption>] [-UseSSL] [-ValueSet <Hashtable>]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

### URI

```
Set-WSManInstance [-ConnectionURI <Uri>] [-Dialect <Uri>] [-FilePath <String>] [-Fragment <String>]
 [-OptionSet <Hashtable>] [-ResourceURI] <Uri> [[-SelectorSet] <Hashtable>] [-SessionOption <SessionOption>]
 [-ValueSet <Hashtable>] [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [<CommonParameters>]
```

## DESCRIPTION

Командлет Set-WSManInstance изменяет данные управления, связанные с ресурсом.

Для изменения информации он использует соединение/транспортный уровень службы удаленного управления Windows.

## Примеры

### Пример 1. Отключение прослушивателя на локальном компьютере

```powershell
Set-WSManInstance -ResourceURI winrm/config/listener -SelectorSet @{address="*";transport="https"} -ValueSet @{Enabled="false"}
```

```Output
cfg                   : http://schemas.microsoft.com/wbem/wsman/1/config/listener
xsi                   : http://www.w3.org/2001/XMLSchema-instance
lang                  : en-US
Address               : *
Transport             : HTTPS
Port                  : 443
Hostname              :
Enabled               : false
URLPrefix             : wsman
CertificateThumbprint :
ListeningOn           : {127.0.0.1, 172.30.168.171, ::1, 2001:4898:0:fff:0:5efe:172.30.168.171...}
```

Эта команда отключает прослушиватель HTTPS на локальном компьютере.

Важно! в *параметре* Parameter учитывается регистр, если он совпадает с указанными свойствами.

Например, в этой команде

Этот сбой: `-ValueSet @{enabled="False"}`

Это будет выполнен следующим образом: `-ValueSet @{Enabled="False"}`

### Пример 2. Установка максимального размера конверта на локальном компьютере

```powershell
Set-WSManInstance -ResourceURI winrm/config -ValueSet @{MaxEnvelopeSizekb = "200"}
```

```Output
cfg                 : http://schemas.microsoft.com/wbem/wsman/1/config
lang                : en-US
MaxEnvelopeSizekb   : 200
MaxTimeoutms        : 60000
MaxBatchItems       : 32000
MaxProviderRequests : 4294967295
Client              : Client
Service             : Service
Winrs               : Winrs
```

Эта команда задает для MaxEnvelopeSizekb значение 200 на локальном компьютере.

Важно! в параметре Parameter учитывается регистр, если он совпадает с указанными свойствами.

Например, воспользуемся указанной выше командой.

Этот сбой:-value @ {Максенвелопесизекб = "200"}

Это будет выполнен следующим образом:-value @ {Максенвелопесизекб = "200"}

### Пример 3. Отключение прослушивателя на удаленном компьютере

```powershell
Set-WSManInstance -ResourceURI winrm/config/listener -ComputerName SERVER02 -SelectorSet @{address="*";transport="https"} -ValueSet @{Enabled="false"}
```

```Output
cfg                   : http://schemas.microsoft.com/wbem/wsman/1/config/listener
xsi                   : http://www.w3.org/2001/XMLSchema-instance
lang                  : en-US
Address               : *
Transport             : HTTPS
Port                  : 443
Hostname              :
Enabled               : false
URLPrefix             : wsman
CertificateThumbprint :
ListeningOn           : {127.0.0.1, 172.30.168.172, ::1, 2001:4898:0:fff:0:5efe:172.30.168.172...}
```

Эта команда отключает прослушиватель HTTPS на удаленном компьютере SERVER02.

Важно! в параметре Parameter учитывается регистр, если он совпадает с указанными свойствами.

Например, воспользуемся указанной выше командой.

Этот сбой: параметр-value @ {Enabled = "false"}

Это происходит следующим образом:-valued @ {Enabled = "false"}

## PARAMETERS

### -ApplicationName

Указывает имя приложения в соединении.
Значение по умолчанию для параметра ApplicationName — WSMAN.
Полный идентификатор для удаленной конечной точки имеет следующий формат:

\<transport\>://\<server\>:\<port\>/\<ApplicationName\>

Пример:

`http://server01:8080/WSMAN`

Службы IIS, где размещен сеанс, перенаправляют запросы с этой конечной точки в заданное приложение.
Этот параметр по умолчанию WSMAN подходит для большинства задач.
Он предназначен для использования в ситуации, когда много компьютеров устанавливают удаленное подключение к одному компьютеру, на котором выполняется Windows PowerShell.
В данном случае для повышения эффективности в службах IIS размещены веб-службы для управления (WS-Management).

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

Задает способ проверки подлинности, используемый на сервере.
Возможны следующие значения:

- Basic — схема, в которой имя пользователя и пароль отправляются на сервер или прокси-сервер в виде открытого текста.
- Default — использование метода аутентификации, реализованного протоколом WS-Management. Это значение по умолчанию.
- Digest — это схема запроса и ответа, использующая указанную сервером строку данных в качестве запроса.
- Kerberos — клиентский компьютер и сервер выполняют взаимную аутентификацию с использованием сертификатов Kerberos.
- Negotiate — это схема запроса и ответа, которая согласовывает с сервером или прокси-сервером ту схему, которую нужно использовать для аутентификации. Например, значение этого параметра позволяет согласованию определить, используется ли протокол Kerberos или NTLM.
- CredSSP — использование аутентификации CredSSP, которая позволяет пользователю делегировать учетные данные. Этот параметр предназначен для команд, которые выполняются на одном удаленном компьютере, но собирают данные или выполняют дополнительные команды на других удаленных компьютерах.

Внимание! CredSSP делегирует учетные данные пользователя с локального компьютера на удаленный компьютер.
Это повышает угрозу безопасности при работе в удаленном режиме.
Если удаленный компьютер скомпрометирован, то передаваемые на него учетные данные могут быть использованы для управления сетевым сеансом.

```yaml
Type: Microsoft.WSMan.Management.AuthenticationMechanism
Parameter Sets: (All)
Aliases: auth, am

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
Position: Named
Default value: Localhost
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConnectionURI

Указывает конечную точку соединения.
Строки имеют следующий формат:

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
Введите имя пользователя, например "User01", "Domain01\User01" или " User@Domain.com ".
либо введите объект PSCredential, например такой, который возвращает командлет Get-Credential.
При вводе имени пользователя появится приглашение ввести пароль.

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

### -Dialect

Определяет диалект, используемый в предикате фильтра.
Это может быть любой диалект, поддерживаемый удаленной службой.
Для URI диалекта можно использовать следующие псевдонимы:

- ВОДИТ `http://schemas.microsoft.com/wbem/wsman/1/WQL`
- Выбора `http://schemas.microsoft.com/wbem/wsman/1/wsman/SelectorFilter`
- Связке `http://schemas.dmtf.org/wbem/wsman/1/cimbinding/associationFilter`

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: http://schemas.microsoft.com/wbem/wsman/1/WQL
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilePath

Указывает путь к файлу, который используется для обновления ресурса управления.
Для указания ресурса управления используется параметр ResourceURI и параметр SelectorSet.
Например, следующая команда использует параметр FilePath:

`Invoke-WSManAction -action StopService -resourceuri wmicimv2/Win32_Service -SelectorSet @{Name="spooler"} -FilePath:c:\input.xml -authentication default`

Эта команда вызывает метод StopService для службы очереди печати с использованием входных данных из файла.
Файл Input.xml содержит следующее:

`<p:StopService_INPUT xmlns:p="http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service" />`

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Path

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Fragment

Задает раздел внутри экземпляра, который должен быть обновлен или возвращен для указанной операции.
Например, чтобы получить состояние службы очереди печати, укажите "-Fragment Status".

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

### -OptionSet

Передает набор параметров в службу, чтобы изменить или уточнить характер запроса.
Это похоже на ключи, используемые в оболочках командной строки, поскольку они зависят от конкретной службы.
Можно указать любое количество параметров.

В следующем примере демонстрируется синтаксис, который передает значения 1, 2 и 3 для параметров a, b и c:

-OptionSet @{a=1;b=2;c=3}

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
При использовании HTTPS в качестве транспорта значение параметра ComputerName должно соответствовать общему имени (CN) сертификата сервера.
Однако если параметр SkipCNCheck указан в составе параметра SessionOption, то общее имя сертификата сервера может отличаться от имени узла сервера.
Параметр SkipCNCheck следует использовать только для доверенных компьютеров.

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

Содержит универсальный код ресурса (URI) для класса или экземпляра ресурса.
URI используется для идентификации определенного типа ресурсов, например дисков и процессов на компьютере.

URI состоит из префикса и пути к ресурсу.
Пример:

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

Задает набор пар значений, используемых для выбора определенных экземпляров ресурсов управления.
Параметр SelectorSet используется в том случае, если существует более одного экземпляра ресурса.
Значение параметра SelectorSet должно быть хэш-таблицей.
В следующем примере показано, как ввести значение для этого параметра:

-SelectorSet @{Name="WinRM";ID="yyy"}

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -SessionOption

Определяет набор расширенных параметров для сеанса WS-Management.
Введите объект SessionOption, созданный с помощью командлета New-WSManSessionOption.
Дополнительные сведения о доступных параметрах см. в описании New-WSManSessionOption.

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

Указывает, что для подключения к удаленному компьютеру следует использовать протокол SSL.
По умолчанию SSL не используется.

WS-Management шифрует все содержимое Windows PowerShell, передаваемое по сети.
Параметр UseSSL позволяет задать дополнительную защиту HTTPS вместо HTTP.
Если протокол SSL недоступен в порту, используемом для установки соединения, и вы указываете этот параметр, команда завершается с ошибкой.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName
Aliases: ssl

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Value

Указывает хэш-таблицу, помогающую изменить ресурс управления.
Для указания ресурса управления используется параметр ResourceURI и параметр SelectorSet.
Значение параметра ValueSet должно быть хэш-таблицей.

```yaml
Type: System.Collections.Hashtable
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

Этот командлет не принимает никаких входных данных.

## Выходные данные

### Нет

Этот командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Connect-WSMan](Connect-WSMan.md)

[Disable-WSManCredSSP](Disable-WSManCredSSP.md)

[Disconnect-WSMan](Disconnect-WSMan.md)

[Enable-WSManCredSSP](Enable-WSManCredSSP.md)

[Get-WSManCredSSP](Get-WSManCredSSP.md)

[Get-WSManInstance](Get-WSManInstance.md)

[Invoke-WSManAction](Invoke-WSManAction.md)

[New-WSManInstance](New-WSManInstance.md)

[New-WSManSessionOption](New-WSManSessionOption.md)

[Remove-WSManInstance](Remove-WSManInstance.md)

[Set-WSManQuickConfig](Set-WSManQuickConfig.md)

[Test-WSMan](Test-WSMan.md)
