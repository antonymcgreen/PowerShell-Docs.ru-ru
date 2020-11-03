---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 02/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/protect-cmsmessage?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Protect-CmsMessage
ms.openlocfilehash: bca0f75ac371fe18d5a35f5c57572f415922d890
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93225750"
---
# Protect-CmsMessage

## Краткий обзор
Шифрует содержимое с помощью формата синтаксиса криптографического сообщения.

## SYNTAX

### Биконтент (по умолчанию)

```
Protect-CmsMessage [-To] <CmsMessageRecipient[]> [-Content] <PSObject> [[-OutFile] <String>]
 [<CommonParameters>]
```

### бипас

```
Protect-CmsMessage [-To] <CmsMessageRecipient[]> [-Path] <String> [[-OutFile] <String>] [<CommonParameters>]
```

### ByLiteralPath

```
Protect-CmsMessage [-To] <CmsMessageRecipient[]> [-LiteralPath] <String> [[-OutFile] <String>]
 [<CommonParameters>]
```

## DESCRIPTION

`Protect-CmsMessage`Командлет шифрует содержимое с помощью формата синтаксиса криптографического сообщения (CMS).

Командлеты CMS поддерживают шифрование и расшифровку содержимого с помощью формата IETF, как описано в [RFC5652](https://tools.ietf.org/html/rfc5652.html).

Стандарт шифрования CMS использует шифрование с открытым ключом, где ключи, используемые для шифрования содержимого (открытый ключ) и ключи, используемые для расшифровки содержимого (закрытый ключ), являются отдельными. Открытый ключ можно свободно распространять, так как он не относится к конфиденциальным сведениям. Если какое-либо содержимое зашифровано с помощью данного открытого ключа, расшифровать его позволяет только имеющийся у вас закрытый ключ. Дополнительные сведения см. на странице о [шифровании с открытым ключом](https://en.wikipedia.org/wiki/Public-key_cryptography).

Перед запуском `Protect-CmsMessage` командлета необходимо настроить сертификат шифрования.
Для распознавания в PowerShell сертификатам шифрования требуется уникальный идентификатор расширенного использования ключа ([EKU](/windows/desktop/SecCrypto/eku)), чтобы идентифицировать их в качестве сертификатов шифрования данных (например, идентификаторы для подписывания кода и зашифрованной почты). Пример сертификата, который будет работать при шифровании документов, см. в примере 1 в этом разделе.

> [!NOTE]
> Этот командлет доступен только в Windows.

## Примеры

### Пример 1. Создание сертификата для шифрования содержимого

Перед запуском `Protect-CmsMessage` командлета необходимо создать сертификат шифрования. Используя следующий текст, измените имя в строке темы на имя, адрес электронной почты или другой идентификатор и сохраните сертификат в файле (например `DocumentEncryption.inf` , как показано в этом примере).

```powershell
# Create .INF file for certreq
{[Version]
Signature = "$Windows NT$"

[Strings]
szOID_ENHANCED_KEY_USAGE = "2.5.29.37"
szOID_DOCUMENT_ENCRYPTION = "1.3.6.1.4.1.311.80.1"

[NewRequest]
Subject = "cn=youralias@emailaddress.com"
MachineKeySet = false
KeyLength = 2048
KeySpec = AT_KEYEXCHANGE
HashAlgorithm = Sha1
Exportable = true
RequestType = Cert
KeyUsage = "CERT_KEY_ENCIPHERMENT_KEY_USAGE | CERT_DATA_ENCIPHERMENT_KEY_USAGE"
ValidityPeriod = "Years"
ValidityPeriodUnits = "1000"

[Extensions]
%szOID_ENHANCED_KEY_USAGE% = "{text}%szOID_DOCUMENT_ENCRYPTION%"
} | Out-File -FilePath DocumentEncryption.inf

# After you have created your certificate file, run the following command to add
# the certificate file to the certificate store. Now you are ready to encrypt and
# decrypt content with the next two examples.
certreq.exe -new DocumentEncryption.inf DocumentEncryption.cer
```

### Пример 2. шифрование сообщения, отправленного по электронной почте

```powershell
$Protected = "Hello World" | Protect-CmsMessage -To "*youralias@emailaddress.com*"
```

В следующем примере выполняется шифрование сообщения "Hello World" путем передачи его в `Protect-CmsMessage` командлет, а затем сохраняется зашифрованное сообщение в переменной. Параметр **to** использует значение строки темы в сертификате.

### Пример 3. Просмотр сертификатов шифрования документов

```
PS C:\> cd Cert:\CurrentUser\My
PS Cert:\CurrentUser\My> Get-ChildItem -DocumentEncryptionCert
```

Чтобы просмотреть сертификаты шифрования документов в поставщике сертификатов, можно добавить динамический параметр **документенкриптионцерт** командлета [Get-ChildItem](../Microsoft.PowerShell.Management/Get-ChildItem.md), доступный только при загрузке поставщика сертификатов.

## PARAMETERS

### — Содержимое

Задает **PSObject** , содержащий содержимое, которое необходимо зашифровать. Например, можно зашифровать содержимое сообщения о событии, а затем использовать переменную, содержащую сообщение ( `$Event` в данном примере), в качестве значения параметра **Content** : `$event = Get-WinEvent -ProviderName "PowerShell" -MaxEvents 1` . Можно также использовать командлет, `Get-Content` чтобы получить содержимое файла, например документ Microsoft Word, и сохранить содержимое в переменной, используемой в качестве значения параметра **Content** .

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: ByContent
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LiteralPath

Указывает путь к содержимому, которое необходимо зашифровать. В отличие от параметра **Path** , значение параметра **LiteralPath** используется строго в том виде, в котором оно указано. Никакие символы не интерпретируются как знаки подстановки. Если путь содержит escape-символы, заключите его в одинарные кавычки. Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Файл

Указывает путь и имя файла, в который будет отправлено зашифрованное содержимое.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Указывает путь к содержимому, которое необходимо зашифровать.

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### — Для

Указывает одного или нескольких получателей сообщений CMS, определенных в любом из следующих форматов:

- Фактический сертификат (полученный от поставщика сертификата).
- Путь к файлу, содержащему сертификат.
- Путь к каталогу, содержащему сертификат.
- Отпечаток сертификата (используется для поиска в хранилище сертификатов).
- Имя субъекта сертификата (используется для поиска в хранилище сертификатов).

```yaml
Type: System.Management.Automation.CmsMessageRecipient[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` и `-WarningVariable` . См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## Входные данные

## Выходные данные

## ПРИМЕЧАНИЯ

## Связанные ссылки

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)

[Get-CmsMessage](Get-CmsMessage.md)

[Unprotect-CmsMessage](Unprotect-CmsMessage.md)
