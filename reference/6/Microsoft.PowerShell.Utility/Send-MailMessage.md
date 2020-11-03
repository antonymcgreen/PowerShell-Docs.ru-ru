---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 05/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/send-mailmessage?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Send-MailMessage
ms.openlocfilehash: 367cd4c193d9cee2375d9ef119bbf7731364351e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228806"
---
# Send-MailMessage

## Краткий обзор
Отправляет сообщение электронной почты.

## SYNTAX

### Все

```
Send-MailMessage [-Attachments <String[]>] [-Bcc <String[]>] [[-Body] <String>] [-BodyAsHtml]
 [-Encoding <Encoding>] [-Cc <String[]>] [-DeliveryNotificationOption <DeliveryNotificationOptions>]
 -From <String> [[-SmtpServer] <String>] [-Priority <MailPriority>] [-ReplyTo <String[]>]
 [-Subject] <String> [-To] <String[]> [-Credential <PSCredential>] [-UseSsl] [-Port <Int32>]
 [<CommonParameters>]
```

## DESCRIPTION

`Send-MailMessage`Командлет отправляет сообщение электронной почты в PowerShell.

Необходимо указать SMTP-сервер или `Send-MailMessage` выполнить команду с ошибкой. Используйте параметр **SMTP** или задайте `$PSEmailServer` для переменной допустимый SMTP-сервер.
Значение, присваиваемое, `$PSEmailServer` является параметром SMTP по умолчанию для PowerShell. Дополнительные сведения см. в разделе [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).

> [!WARNING]
> `Send-MailMessage`Командлет устарел. Этот командлет не гарантирует безопасное подключение к SMTP-серверам. Хотя в PowerShell нет доступной немедленной замены, мы рекомендуем не использовать `Send-MailMessage` . Дополнительные сведения см. в разделе [Примечание о совместимости платформ DE0005](https://aka.ms/SendMailMessage).

## Примеры

### Пример 1. Отправка сообщения электронной почты от одного пользователя другому человеку

В этом примере посылается сообщение электронной почты от одного лица другому человеку.

Параметры **from** , **to** и **subject** обязательны для `Send-MailMessage` . В этом примере используется переменная по умолчанию `$PSEmailServer` для SMTP-сервера, поэтому параметр **SMTP** не требуется.

```powershell
Send-MailMessage -From 'User01 <user01@fabrikam.com>' -To 'User02 <user02@fabrikam.com>' -Subject 'Test mail'
```

`Send-MailMessage`Командлет использует параметр **from** для указания отправителя сообщения. Параметр **to** указывает получателя сообщения. Параметр **subject** использует **тестовую почту** Text String в качестве сообщения, так как необязательный параметр **Body** не включен.

### Пример 2. Отправка вложения

В этом примере отправляется сообщение электронной почты с вложением.

```powershell
Send-MailMessage -From 'User01 <user01@fabrikam.com>' -To 'User02 <user02@fabrikam.com>', 'User03 <user03@fabrikam.com>' -Subject 'Sending the Attachment' -Body "Forgot to send the attachment. Sending now." -Attachments .\data.csv -Priority High -DeliveryNotificationOption OnSuccess, OnFailure -SmtpServer 'smtp.fabrikam.com'
```

`Send-MailMessage`Командлет использует параметр **from** для указания отправителя сообщения. Параметр **to** указывает получателей сообщения. Параметр **subject** описывает содержимое сообщения. Параметр **Body** — это содержимое сообщения.

Параметр **вложения** указывает файл в текущем каталоге, присоединенном к сообщению электронной почты. Параметр **Priority** задает для сообщения **высокий** приоритет. Параметр **-деливеринотификатионоптион** задает два значения: **onsuccesss** и **onSuccess** . Отправитель получит уведомления по электронной почте для подтверждения успешной или неуспешной доставки сообщения.
Параметр **SMTP** задает для SMTP-сервера значение **SMTP.fabrikam.com** .

### Пример 3. Отправка сообщения электронной почты в список рассылки

В этом примере сообщение электронной почты отправляется в список рассылки.

```powershell
Send-MailMessage -From 'User01 <user01@fabrikam.com>' -To 'ITGroup <itdept@fabrikam.com>' -Cc 'User02 <user02@fabrikam.com>' -Bcc 'ITMgr <itmgr@fabrikam.com>' -Subject "Don't forget today's meeting!" -Credential domain01\admin01 -UseSsl
```

`Send-MailMessage`Командлет использует параметр **from** для указания отправителя сообщения. Параметр **to** указывает получателей сообщения. Параметр **CC** отправляет копию сообщения указанному получателю. Параметр **BCC** отправляет скрытую копию сообщения. Скрытая копия — это адрес электронной почты, который скрыт от других получателей. Параметр **subject** является сообщением, так как необязательный параметр **тела** не включен.

Параметр **Credential** указывает учетные данные администратора домена, используемые для отправки сообщения. Параметр **UseSsl** указывает, что протокол SSL создает безопасное соединение.

## PARAMETERS

### — Вложения

Указывает путь и имена файлов, которые будут присоединены к сообщению электронной почты. Можно использовать этот параметр или передать пути и имена файлов в `Send-MailMessage` .

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PsPath

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -СК

Указывает адреса электронной почты, получающие копию почты, но не указанные в качестве получателей сообщения. Введите имена (необязательно) и адрес электронной почты, например `Name <someone@fabrikam.com>` .

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Body

Указывает содержимое сообщения электронной почты.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Бодяштмл

Указывает, что значение параметра **Body** содержит HTML.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: BAH

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Копия

Указывает адреса электронной почты, на которые отправляется копия (CC) сообщения электронной почты. Введите имена (необязательно) и адрес электронной почты, например `Name <someone@fabrikam.com>` .

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Credential

Указывает учетную запись пользователя с разрешением на выполнение этого действия. По умолчанию используется текущий пользователь.

Введите имя пользователя, например **User01** или **Domain01\User01** . Или введите объект **PSCredential** , например один из `Get-Credential` командлетов.

Учетные данные хранятся в объекте [PSCredential](/dotnet/api/system.management.automation.pscredential) , а пароль хранится в качестве [SecureString](/dotnet/api/system.security.securestring).

> [!NOTE]
> Дополнительные сведения о защите данных **SecureString** см. в разделе [насколько безопасным является SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Деливеринотификатионоптион

Указывает параметры уведомлений о доставке для сообщения электронной почты. Можно указать несколько значений.
Значение по умолчанию — None. Псевдоним для этого параметра — **дно** .

Уведомления о доставке отправляются на адрес в параметре **from** .

Для этого параметра допустимы следующие значения:

- `None`: Нет уведомления.
- `OnSuccess`: Уведомлять, если доставка выполнена успешно.
- `OnFailure`: Уведомлять, если доставка не выполнена.
- `Delay`: Уведомлять при задержке доставки.
- `Never`: Никогда не уведомлять.

```yaml
Type: System.Net.Mail.DeliveryNotificationOptions
Parameter Sets: (All)
Aliases: DNO
Accepted values: None, OnSuccess, OnFailure, Delay, Never

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Encoding

Указывает тип кодировки для целевого файла. Значение по умолчанию — `utf8NoBOM`.

Для этого параметра допустимы следующие значения:

- `ascii`: Использует кодировку для набора символов ASCII (7-разрядных).
- `bigendianunicode`: Кодируется в формате UTF-16 с обратным порядком байтов.
- `oem`: Использует кодировку по умолчанию для программ MS-DOS и консолей.
- `unicode`: Кодируется в формате UTF-16 с прямым порядком байтов.
- `utf7`: Кодируется в формате UTF-7.
- `utf8`: Кодируется в формате UTF-8.
- `utf8BOM`: Кодирует в формате UTF-8 с меткой порядка байтов (BOM)
- `utf8NoBOM`: Кодирует в формате UTF-8 без метки порядка байтов (BOM)
- `utf32`: Кодируется в формате UTF-32.

Начиная с PowerShell 6,2, параметр **кодировки** также разрешает числовые идентификаторы зарегистрированных кодовых страниц (например `-Encoding 1251` ,) или строковых имен зарегистрированных кодовых страниц (например `-Encoding "windows-1251"` ,). Дополнительные сведения см. в документации .NET по [кодированию. codepage](/dotnet/api/system.text.encoding.codepage?view=netcore-2.2).

```yaml
Type: System.Text.Encoding
Parameter Sets: (All)
Aliases: BE
Accepted values: ASCII, BigEndianUnicode, OEM, Unicode, UTF7, UTF8, UTF8BOM, UTF8NoBOM, UTF32

Required: False
Position: Named
Default value: UTF8NoBOM
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### — От

Параметр **from** является обязательным. Этот параметр указывает адрес электронной почты отправителя. Введите имя (необязательно) и адрес электронной почты, например `Name <someone@fabrikam.com>` .

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Port

Указывает дополнительный порт на сервере SMTP. Значение по умолчанию — 25 (значение по умолчанию для порта SMTP).

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 25
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Priority

Указывает приоритет сообщения электронной почты. Значение по умолчанию: Normal. Допустимые значения для этого параметра: обычная, высокая и низкая.

```yaml
Type: System.Net.Mail.MailPriority
Parameter Sets: (All)
Aliases:
Accepted values: Normal, High, Low

Required: False
Position: Named
Default value: Normal
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReplyTo

Указывает дополнительные адреса электронной почты (отличные от адреса отклика), которые следует использовать для ответа на это сообщение.
Введите имена (необязательно) и адрес электронной почты, например `Name <someone@fabrikam.com>` .

Этот параметр появился в PowerShell 6,2.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SMTP

Указывает имя SMTP-сервера, который отправляет сообщение электронной почты.

Значением по умолчанию является значение `$PSEmailServer` привилегированной переменной. Если переменная предпочтений не задана и этот параметр не используется, `Send-MailMessage` команда завершается ошибкой.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ComputerName

Required: False
Position: 3
Default value: $PSEmailServer
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Subject

Параметр **subject** является обязательным. Этот параметр указывает тему сообщения электронной почты.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: sub

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### — Для

Параметр **to** является обязательным. Этот параметр указывает адрес электронной почты получателя. При наличии нескольких получателей разделите их адреса запятой ( `,` ). Введите имена (необязательно) и адрес электронной почты, например `Name <someone@fabrikam.com>` .

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UseSsl

Протокол SSL (SSL) используется для установления безопасного подключения к удаленному компьютеру для отправки почты. По умолчанию SSL не используется.

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

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.String

Путь и имена файлов вложений можно передать в `Send-MailMessage` .

## Выходные данные

### Нет

Этот командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

## Связанные ссылки

[about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md)

[Get-Credential](../Microsoft.PowerShell.Security/Get-Credential.md)
