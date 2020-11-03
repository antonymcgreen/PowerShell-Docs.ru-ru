---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 02/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-cmsmessage?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CmsMessage
ms.openlocfilehash: 9a24cfc0e2312a5bb985084ffb9eb753f49cb8ea
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229421"
---
# Get-CmsMessage

## Краткий обзор
Возвращает содержимое, зашифрованное с помощью формата синтаксиса криптографического сообщения.

## SYNTAX

### биконтент

```
Get-CmsMessage [-Content] <String> [<CommonParameters>]
```

### бипас

```
Get-CmsMessage [-Path] <String> [<CommonParameters>]
```

### ByLiteralPath

```
Get-CmsMessage [-LiteralPath] <String> [<CommonParameters>]
```

## DESCRIPTION

`Get-CmsMessage`Командлет получает содержимое, зашифрованное с помощью формата синтаксиса криптографического сообщения (CMS).

Командлеты CMS поддерживают шифрование и расшифровку содержимого, используя формат IETF для криптографической защиты сообщений, как описано в [RFC5652](https://tools.ietf.org/html/rfc5652).

Стандарт шифрования CMS использует шифрование с открытым ключом, где ключи, используемые для шифрования содержимого (открытый ключ) и ключи, используемые для расшифровки содержимого (закрытый ключ), являются отдельными. Открытый ключ можно свободно распространять, так как он не относится к конфиденциальным сведениям. Если какое-либо содержимое зашифровано с помощью данного открытого ключа, расшифровать его позволяет только имеющийся у вас закрытый ключ. Дополнительные сведения см. на странице о [шифровании с открытым ключом](https://en.wikipedia.org/wiki/Public-key_cryptography).

`Get-CmsMessage` Возвращает содержимое, зашифрованное в формате CMS. Он не расшифровывает и не снимает защиту с содержимого. Этот командлет можно использовать для получения зашифрованного содержимого, выполнив `Protect-CmsMessage` командлет. Можно указать содержимое, которое нужно расшифровать как строку, или путем к зашифрованному содержимому. Вы можете передать результаты в для `Get-CmsMessage` `Unprotect-CmsMessage` расшифровки содержимого при условии, что у вас есть сведения о сертификате шифрования документов, который использовался для шифрования содержимого.

В PowerShell 7,1 добавлена поддержка Linux и macOS.

## Примеры

### Пример 1. Получение зашифрованного содержимого

```powershell
$Msg = Get-CmsMessage -Path "C:\Users\Test\Documents\PowerShell\Future_Plans.txt"
$Msg.Content
```

```Output
-----BEGIN CMS-----
MIIBqAYJKoZIhvcNAQcDoIIBmTCCAZUCAQAxggFQMIIBTAIBADA0MCAxHjAcBgNVBAMBFWxlZWhv
bG1AbGljcm9zb2Z0LmNvbQIQQYHsbcXnjIJCtH+OhGmc1DANBgkqhkiG9w0BAQcwAASCAQAnkFHM
proJnFy4geFGfyNmxH3yeoPvwEYzdnsoVqqDPAd8D3wao77z7OhJEXwz9GeFLnxD6djKV/tF4PxR
E27aduKSLbnxfpf/sepZ4fUkuGibnwWFrxGE3B1G26MCenHWjYQiqv+Nq32Gc97qEAERrhLv6S4R
G+2dJEnesW8A+z9QPo+DwYP5FzD0Td0ExrkswVckpLNR6j17Yaags3ltNXmbdEXekhi6Psf2MLMP
TSO79lv2L0KeXFGuPOrdzPRwCkV0vNEqTEBeDnZGrjv/5766bM3GW34FXApod9u+VSFpBnqVOCBA
DVDraA6k+xwBt66cV84AHLkh0kT02SIHMDwGCSqGSIb3DQEHATAdBglghkgBZQMEASoEEJbJaiRl
KMnBoD1dkb/FzSWAEBaL8xkFwCu0e1AtDj7nSJc=
-----END CMS-----
```

Эта команда получает зашифрованное содержимое, расположенное по адресу C:\Users\Test\Documents\PowerShell\Future_Plans.txt.

### Пример 2. переканалировать зашифрованное содержимое в Unprotect-CmsMessage

```powershell
$Msg = Get-CmsMessage -Path "C:\Users\Test\Documents\PowerShell\Future_Plans.txt"
$Msg | Unprotect-CmsMessage -To "cn=youralias@emailaddress.com"
```

```Output
Try the new Break All command
```

Эта команда передает результаты `Get-CmsMessage` командлета из примера 1 в `Unprotect-CmsMessage` , чтобы расшифровать сообщение и прочитать его в виде обычного текста. В этом случае значением параметра **to** является значение строки темы сертификата шифрования. Расшифрованное сообщение "попробовать новую команду" прервать все "— результат.

## PARAMETERS

### — Содержимое

Задает зашифрованную строку или переменную, содержащую зашифрованную строку.

```yaml
Type: System.String
Parameter Sets: ByContent
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LiteralPath

Указывает путь к зашифрованному содержимому, которое требуется получить. В отличие от параметра **Path** , значение параметра **LiteralPath** используется строго в том виде, в котором оно указано. Никакие символы не распознаются как подстановочные знаки. Если путь содержит escape-символы, заключите его в одинарные кавычки.
Одинарные кавычки указывают, что PowerShell не интерпретирует символы, заключенные в escape-символы.

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

### -Path

Указывает путь к зашифрованному содержимому, которое необходимо расшифровать.

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

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

## Выходные данные

## ПРИМЕЧАНИЯ

## Связанные ссылки

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)

[Protect-CmsMessage](Protect-CmsMessage.md)

[Unprotect-CmsMessage](Unprotect-CmsMessage.md)

