---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/new-cimsessionoption?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-CimSessionOption
ms.openlocfilehash: 54a2ca8a28d54bfe1d9676acdaace4592f62620f
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599983"
---
# New-CimSessionOption

## Краткий обзор
Задает дополнительные параметры для командлета New-CimSession.

## SYNTAX

### Протоколтипесет (по умолчанию)

```
New-CimSessionOption [-Protocol] <ProtocolType> [-UICulture <CultureInfo>] [-Culture <CultureInfo>]
 [<CommonParameters>]
```

### всманпараметерсет

```
New-CimSessionOption [-NoEncryption] [-SkipCACheck] [-SkipCNCheck] [-SkipRevocationCheck]
 [-EncodePortInServicePrincipalName] [-Encoding <PacketEncoding>] [-HttpPrefix <Uri>]
 [-MaxEnvelopeSizeKB <UInt32>] [-ProxyAuthentication <PasswordAuthenticationMechanism>]
 [-ProxyCertificateThumbprint <String>] [-ProxyCredential <PSCredential>] [-ProxyType <ProxyType>]
 [-UseSsl] [-UICulture <CultureInfo>] [-Culture <CultureInfo>] [<CommonParameters>]
```

### дкомпараметерсет

```
New-CimSessionOption [-Impersonation <ImpersonationType>] [-PacketIntegrity] [-PacketPrivacy]
 [-UICulture <CultureInfo>] [-Culture <CultureInfo>] [<CommonParameters>]
```

## DESCRIPTION

`New-CimSessionOption`Командлет создает экземпляр объекта параметров сеанса CIM. Используйте объект параметров сеанса CIM в качестве входных данных для `New-CimSession` командлета, чтобы указать параметры для сеанса CIM.

Этот командлет имеет два набора параметров: один для параметров WsMan и один для параметров распределенной модели объектов компонента (DCOM). В зависимости от используемых параметров командлет возвращает либо экземпляр параметров сеанса DCOM, либо метод, который возвращает параметры сеанса WsMan.

## Примеры

### Пример 1. Создание объекта параметров сеанса CIM для DCOM

В этом примере создается объект параметров сеанса CIM для протокола DCOM и сохраняется в переменной с именем `$so` . После этого содержимое переменной передается в `New-CimSession` командлет.
`New-CimSession` затем создает новый сеанс CIM с удаленным сервером с именем Server01, используя параметры, определенные в переменной.

```powershell
$so = New-CimSessionOption -Protocol DCOM
New-CimSession -ComputerName Server01 -SessionOption $so
```

### Пример 2. Создание объекта параметров сеанса CIM для WsMan

В этом примере создается объект параметров сеанса CIM для протокола WsMan. Объект содержит конфигурацию режима проверки подлинности **Kerberos** , заданного параметром **проксяусентикатион** , учетные данные, указанные параметром **ProxyCredential** , и указывает, что команда должна пропустить проверку ЦС, пропустить проверку CN и использовать SSL.

```powershell
New-CimSessionOption -ProxyAuthentication Kerberos -ProxyCredential $cred -SkipCACheck -SkipCNCheck -UseSsl
```

### Пример 3. Создание объекта параметров сеанса CIM с заданной культурой

```powershell
New-CimSessionOption -Culture Fr-Fr -Protocol Wsman
```

В этом примере указывается язык и региональные параметры, используемые для сеанса CIM. По умолчанию при выполнении операций используется язык и региональные параметры клиента. Однако язык и региональные параметры по умолчанию можно переопределить с помощью параметра **culture** .

## PARAMETERS

### -Culture

Указывает язык и региональные параметры пользовательского интерфейса, используемые для сеанса CIM. Укажите значение этого параметра в одном из следующих форматов:

- Имя языка и региональных параметров в `<languagecode2>-<country/regioncode2>` формате, например "en-US".
- Переменная, содержащая объект **CultureInfo** .
- Команда, которая получает объект **CultureInfo** , например [Get-Culture](../Microsoft.PowerShell.Utility/Get-Culture.md)

```yaml
Type: System.Globalization.CultureInfo
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ЕнкодепортинсервицепринЦипалнаме

Указывает, что соединение Kerberos подключается к службе, имя участника-службы (SPN) которого содержит номер порта службы. Этот тип соединения не является распространенным.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Encoding

Указывает кодировку, используемую для протокола WsMan. Допустимые значения для этого параметра: **Default**, **Utf8** или **Utf16**.

```yaml
Type: Microsoft.Management.Infrastructure.Options.PacketEncoding
Parameter Sets: WSManParameterSet
Aliases:
Accepted values: Default, Utf8, Utf16

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Хттппрефикс

Указывает часть URL-адреса HTTP после имени компьютера и номера порта. Изменение этого не является распространенным. По умолчанию значение этого параметра равно **/всман**.

```yaml
Type: System.Uri
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### — Олицетворение

Создает сеанс DCOM для инструментарий управления Windows (WMI) (WMI) с использованием олицетворения.

Допустимые значения для этого параметра:

- По умолчанию. DCOM может выбрать уровень олицетворения с помощью обычного алгоритма согласования безопасности.
- Нет: клиент является анонимным для сервера. Серверный процесс может олицетворять клиента, но маркер олицетворения не содержит никаких сведений и не может использоваться.
- Identify: позволяет объектам запрашивать учетные данные вызывающей стороны.
- Impersonate: позволяет объектам использовать учетные данные вызывающей стороны.
- Delegate: позволяет объектам разрешить другим объектам использовать учетные данные вызывающей стороны.

Если **олицетворение** не указано, `New-CimSession` командлет использует значение **impersonate**.

```yaml
Type: Microsoft.Management.Infrastructure.Options.ImpersonationType
Parameter Sets: DcomParameterSet
Aliases:
Accepted values: Default, None, Identify, Impersonate, Delegate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Максенвелопесизекб

Задает предельный размер сообщений WsMan XML для любого направления.

```yaml
Type: System.UInt32
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NoEncryption

Указывает, что шифрование данных отключено.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Паккетинтегрити

Указывает, что сеанс DCOM, созданный для WMI, использует функциональные возможности _Паккетинтегрити_ модели COM. По умолчанию все сеансы CIM, созданные с помощью DCOM, имеют для параметра **паккетинтегрити** значение **true**.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DcomParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Паккетприваци

Создает сеанс DCOM для WMI с помощью _ПАККЕТПРИВАЦИ_ com. По умолчанию все сеансы CIM, созданные с помощью DCOM, имеют для параметра **паккетприваци** значение **true**.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DcomParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Protocol

Указывает протокол, который необходимо использовать. Допустимые значения для этого параметра: **DCOM**, **Default** или **WSMan**.

```yaml
Type: Microsoft.Management.Infrastructure.CimCmdlets.ProtocolType
Parameter Sets: ProtocolTypeSet
Aliases:
Accepted values: Dcom, Default, Wsman

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Проксяусентикатион

Указывает метод проверки подлинности, используемый для разрешения прокси-сервера. Допустимые значения для этого параметра: **Default**, **дайджест**, **Negotiate**, **Basic**, **Kerberos**, **нтлмдомаин** или **CredSsp**.

```yaml
Type: Microsoft.Management.Infrastructure.Options.PasswordAuthenticationMechanism
Parameter Sets: WSManParameterSet
Aliases:
Accepted values: Default, Digest, Negotiate, Basic, Kerberos, NtlmDomain, CredSsp

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Проксицертификатесумбпринт

Указывает сертификат цифрового открытого ключа (x. 509) учетной записи пользователя для проверки подлинности прокси-сервера.
Введите отпечаток сертификата. Сертификаты используются при проверке подлинности на основе сертификата клиента. Они могут быть сопоставлены только с локальными учетными записями пользователей и не работают с учетными записями домена.

Чтобы получить отпечаток сертификата, используйте `Get-Item` `Get-ChildItem` командлеты или на диске PowerShell CERT:.

```yaml
Type: System.String
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProxyCredential

Задает учетные данные, используемые для аутентификации прокси-сервера. Введите одно из следующих значений.

- Переменная, содержащая объект PSCredential.
- Команда, которая получает объект PSCredential, например `Get-Credential`

Если этот параметр не задан, то нельзя указать учетные данные.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Прокситипе

Указывает используемый механизм разрешения имен узлов. Допустимые значения для этого параметра: **None**, **WinHTTP**, **Auto** или **InternetExplorer**.

Значение этого параметра по умолчанию — **InternetExplorer**.

```yaml
Type: Microsoft.Management.Infrastructure.Options.ProxyType
Parameter Sets: WSManParameterSet
Aliases:
Accepted values: None, WinHttp, Auto, InternetExplorer

Required: False
Position: Named
Default value: InternetExplorer
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Скипкачекк

Указывает, что при подключении по протоколу HTTPS клиент не проверяет, подписан ли сертификат сервера доверенным центром сертификации (ЦС).

Используйте этот параметр только в том случае, если удаленный компьютер является доверенным с помощью другого механизма, например, когда удаленный компьютер входит в сеть, которая физически защищена и изолирована, или если удаленный компьютер указан как доверенный узел в конфигурации WinRM.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SkipCNCheck

Указывает, что общее имя сертификата (CN) сервера не обязательно должно совпадать с именем узла сервера. Используйте этот параметр для удаленных операций только с доверенными компьютерами, использующими протокол HTTPS.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Скипревокатиончекк

Указывает, что проверка отзыва сертификатов сервера пропускается. Используйте этот параметр только для доверенных компьютеров.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UICulture

Указывает язык и региональные параметры пользовательского интерфейса, используемые для сеанса CIM. Укажите значение этого параметра в одном из следующих форматов:

- Имя языка и региональных параметров в `<languagecode2>-<country/regioncode2>` формате, например "en-US".
- Переменная, содержащая объект CultureInfo.
- Команда, которая получает объект CultureInfo, например `Get-Culture` .

```yaml
Type: System.Globalization.CultureInfo
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UseSsl

Указывает, что для установления соединения с удаленным компьютером следует использовать протокол SSL. По умолчанию SSL не используется. WsMan шифрует все содержимое, передаваемое по сети, даже при использовании протокола HTTP.

Этот параметр позволяет указать дополнительную защиту протокола HTTPS вместо HTTP. Если протокол SSL недоступен для порта, используемого для соединения, и указан этот параметр, команда завершается ошибкой.

Рекомендуется использовать этот параметр только в том случае, если не указан параметр **паккетприваци** .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: WSManParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### None

Этот командлет не принимает входные объекты.

## Выходные данные

### Цимсессионоптион

Этот командлет возвращает объект, содержащий сведения о параметрах сеанса CIM.

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Get-ChildItem](../microsoft.powershell.management/get-childitem.md)

[Get-Credential](../microsoft.powershell.security/get-credential.md)

[Get-Culture](../microsoft.powershell.utility/get-culture.md)

[Get-Item](../microsoft.powershell.management/get-item.md)

[New-CimSession](New-CimSession.md)

