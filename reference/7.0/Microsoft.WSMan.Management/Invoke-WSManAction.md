---
external help file: Microsoft.WSMan.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.WSMan.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/invoke-wsmanaction?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-WSManAction
ms.openlocfilehash: 18ca64912df0e6b672bd05358aa806f639a590e7
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "93229850"
---
# Invoke-WSManAction

## Краткий обзор
Вызывает действие для объекта, указанного в URI ресурса и селекторах.

## SYNTAX

### URI (по умолчанию)

```
Invoke-WSManAction [-Action] <String> [-ConnectionURI <Uri>] [-FilePath <String>] [-OptionSet <Hashtable>]
 [[-SelectorSet] <Hashtable>] [-SessionOption <SessionOption>] [-ValueSet <Hashtable>] [-ResourceURI] <Uri>
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [<CommonParameters>]
```

### ИмяКомпьютера

```
Invoke-WSManAction [-Action] <String> [-ApplicationName <String>] [-ComputerName <String>] [-FilePath <String>]
 [-OptionSet <Hashtable>] [-Port <Int32>] [[-SelectorSet] <Hashtable>] [-SessionOption <SessionOption>]
 [-UseSSL] [-ValueSet <Hashtable>] [-ResourceURI] <Uri> [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

## DESCRIPTION
**Командлет Invoke-WSManAction** выполняет действие с объектом, указанным в RESOURCE_URI, где параметры задаются парами "ключ-значение".

Для выполнения действия этот командлет использует соединение/транспортный уровень WS-Management.

## Примеры

### Пример 1. вызов метода

```powershell
Invoke-WSManAction -Action startservice -ResourceURI wmicimv2/win32_service  -SelectorSet @{name="spooler"} -Authentication default
```

```Output
xsi         : http://www.w3.org/2001/XMLSchema-instance
p           : http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service
cim         : http://schemas.dmtf.org/wbem/wscim/1/common
lang        : en-US
ReturnValue : 0
```

Эта команда вызывает метод **StartService** экземпляра класса WMI Win32_Service, который соответствует службе диспетчера очереди печати.

Возвращаемое значение указывает, было ли действие успешным.
В данном случае возвращаемое значение 0 указывает на успешное выполнение.
Возвращаемое значение 5 указывает на то, что служба уже запущена.

### Пример 2. вызов метода

```powershell
Invoke-WSManAction -Action stopservice -ResourceURI wmicimv2/Win32_Service -SelectorSet @{Name="spooler"} -FilePath:input.xml -Authentication default
```

```Output
xsi         : http://www.w3.org/2001/XMLSchema-instance
p           : http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service
cim         : http://schemas.dmtf.org/wbem/wscim/1/common
lang        : en-US
ReturnValue : 0
```

Эта команда вызывает метод **«не используется» в** службе диспетчера очереди, используя входные данные из файла.
Файл Input.xml содержит следующее:

`<p:StopService_INPUT xmlns:p="http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service" />`

### Пример 3. вызов метода с указанными значениями параметров

```powershell
Invoke-WSManAction -Action create -ResourceURI wmicimv2/win32_process -ValueSet @{commandline="notepad.exe";currentdirectory="C:\"}
```

```Output
xsi         : http://www.w3.org/2001/XMLSchema-instance
p           : http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Process
cim         : http://schemas.dmtf.org/wbem/wscim/1/common
lang        : en-US
ProcessId   : 6356
ReturnValue : 0
```

Эта команда вызывает метод **CREATE** класса Win32_Process.
Он передает методу два значения параметров: Notepad.exe и C:\..
В результате создается новый процесс для запуска Блокнота, а текущим каталогом нового процесса присваивается значение C:\.

### Пример 4. вызов метода на удаленном компьютере

```powershell
Invoke-WSManAction -Action startservice -ResourceURI wmicimv2/win32_service  -SelectorSet @{name="spooler"} -ComputerName server01 -Authentication default
```

```Output
xsi         : http://www.w3.org/2001/XMLSchema-instance
p           : http://schemas.microsoft.com/wbem/wsman/1/wmi/root/cimv2/Win32_Service
cim         : http://schemas.dmtf.org/wbem/wscim/1/common
lang        : en-US
ReturnValue : 0
```

Эта команда вызывает метод **StartService** экземпляра класса WMI Win32_Service, который соответствует службе диспетчера очереди печати.
Так как указан параметр *ComputerName* , команда выполняется на удаленном компьютере Server01.

## PARAMETERS

### -Action
Задает метод для выполнения в объекте управления, указанном ResourceURI и селекторами.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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
Position: Named
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
Aliases: CURI, CU

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

### -FilePath
Указывает путь к файлу, который используется для обновления ресурса управления.
Ресурс управления указывается с помощью параметра *resourceUri* и параметра *selector* .
Например, следующая команда использует параметр *FilePath* :

`Invoke-WSManAction -Action stopservice -ResourceUri wmicimv2/Win32_Service -SelectorSet @{Name="spooler"} -FilePath c:\input.xml -Authentication default`

Эта команда вызывает метод **«не используется» в** службе **диспетчера очереди** , используя входные данные из файла.
Файл Input.xml содержит следующее:

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
Accept pipeline input: True (ByPropertyName, ByValue)
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
Parameter Sets: ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceURI
Указывает URI класса или экземпляра ресурса.
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
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -SelectorSet
Задает набор пар значений, используемых для выбора определенных экземпляров ресурсов управления.
Набор *selector* используется, если существует более одного экземпляра ресурса.
Значение *selector* должно быть хэш-таблицей.

В следующем примере показано, как ввести значение для этого параметра:

`-SelectorSet @{Name="WinRM";ID="yyy"}`

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

### -Value
Указывает хэш-таблицу, помогающую изменить ресурс управления.
Ресурс управления указывается с помощью *resourceUri* и *selector*.
Значение параметра набора *значений* должно быть хэш-таблицей.

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
Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

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

[New-WSManInstance](New-WSManInstance.md)

[New-WSManSessionOption](New-WSManSessionOption.md)

[Remove-WSManInstance](Remove-WSManInstance.md)

[Set-WSManInstance](Set-WSManInstance.md)

[Set-WSManQuickConfig](Set-WSManQuickConfig.md)

[Test-WSMan](Test-WSMan.md)
