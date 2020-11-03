---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 02/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/unprotect-cmsmessage?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unprotect-CmsMessage
ms.openlocfilehash: eaabf4e45a9441a479059513a428f2d87430dd2a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229325"
---
# Unprotect-CmsMessage

## Краткий обзор
Расшифровывает содержимое, зашифрованное с помощью формата синтаксиса криптографического сообщения.

## SYNTAX

### Бивиневент (по умолчанию)

```
Unprotect-CmsMessage [-EventLogRecord] <PSObject> [-IncludeContext] [[-To] <CmsMessageRecipient[]>]
 [<CommonParameters>]
```

### биконтент

```
Unprotect-CmsMessage [-Content] <String> [-IncludeContext] [[-To] <CmsMessageRecipient[]>] [<CommonParameters>]
```

### бипас

```
Unprotect-CmsMessage [-Path] <String> [-IncludeContext] [[-To] <CmsMessageRecipient[]>] [<CommonParameters>]
```

### ByLiteralPath

```
Unprotect-CmsMessage [-LiteralPath] <String> [-IncludeContext] [[-To] <CmsMessageRecipient[]>]
 [<CommonParameters>]
```

## DESCRIPTION

`Unprotect-CmsMessage`Командлет расшифровывает содержимое, зашифрованное с помощью формата синтаксиса криптографического сообщения (CMS).

Командлеты CMS поддерживают шифрование и расшифровку содержимого, используя стандартный формат IETF для криптографической защиты сообщений, как описано в [RFC5652](https://tools.ietf.org/html/rfc5652).

Стандарт шифрования CMS использует шифрование с открытым ключом, где ключи, используемые для шифрования содержимого (открытый ключ) и ключи, используемые для расшифровки содержимого (закрытый ключ), являются отдельными. Открытый ключ можно свободно распространять, так как он не относится к конфиденциальным сведениям. Если какое-либо содержимое зашифровано с помощью данного открытого ключа, расшифровать его позволяет только имеющийся у вас закрытый ключ. Дополнительные сведения см. на странице о [шифровании с открытым ключом](https://en.wikipedia.org/wiki/Public-key_cryptography).

`Unprotect-CmsMessage` расшифровывает содержимое, зашифрованное в формате CMS. Этот командлет можно использовать для расшифровки зашифрованного содержимого, выполнив `Protect-CmsMessage` командлет. Можно указать содержимое, которое нужно расшифровать как строку, с помощью идентификатора записи журнала событий шифрования или путем к зашифрованному содержимому. `Unprotect-CmsMessage`Командлет возвращает расшифрованное содержимое.

В PowerShell 7,1 добавлена поддержка Linux и macOS.

## Примеры

### Пример 1. Расшифровка сообщения

В следующем примере выполняется расшифровка содержимого, расположенного по литеральному пути `C:\Users\Test\Documents\PowerShell` . В этом примере для значения параметра Required **to** используется отпечаток сертификата, который использовался для шифрования. Расшифрованное сообщение "попробовать новую команду" прервать все "— результат.

```powershell
$parameters = @{
  LiteralPath = "C:\Users\Test\Documents\PowerShell\Future_Plans.txt"
  To = '0f 8j b1 ab e0 ce 35 1d 67 d2 f2 6f a2 d2 00 cl 22 z9 m9 85'
}
Unprotect-CmsMessage -LiteralPath @parameters
```

```Output
Try the new Break All command
```

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
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -EventLogRecord

Указывает идентификатор записи в журнале событий, представляющий операцию шифрования CMS.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: ByWinEvent
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Инклудеконтекст

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LiteralPath

Указывает путь к зашифрованному содержимому, которое необходимо расшифровать. В отличие от параметра **Path** , значение параметра **LiteralPath** используется строго в том виде, в котором оно указано. Никакие символы не распознаются как подстановочные знаки. Если путь содержит escape-символы, заключите его в одинарные кавычки. Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases:

Required: True
Position: 0
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
Position: 0
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

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System. Diagnostics. Eventing. Reader. EventLogRecord или System. String

Объект, содержащий зашифрованное содержимое, можно передать в `Unprotect-CmsMessage` .

## Выходные данные

### System.String

Незашифрованное сообщение.

## ПРИМЕЧАНИЯ

## Связанные ссылки

[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)

[Get-CmsMessage](Get-CmsMessage.md)

[Protect-CmsMessage](Protect-CmsMessage.md)

