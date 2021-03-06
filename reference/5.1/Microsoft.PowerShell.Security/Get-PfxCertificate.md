---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-pfxcertificate?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PfxCertificate
ms.openlocfilehash: 1be3034b1fb44b1dce1a592ea5a2c1622b54d28f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227777"
---
# Get-PfxCertificate

## Краткий обзор
Возвращает сведения о файлах сертификатов PFX на компьютере.

## SYNTAX

### ByPath (по умолчанию)

```
Get-PfxCertificate [-FilePath] <String[]> [<CommonParameters>]
```

### ByLiteralPath

```
Get-PfxCertificate -LiteralPath <String[]> [<CommonParameters>]
```

## DESCRIPTION

`Get-PfxCertificate`Командлет возвращает объект, представляющий каждый указанный PFX-файл сертификата.
PFX-файл включает сертификат и закрытый ключ.

## Примеры

### Пример 1. получение сертификата PFX

```powershell
Get-PfxCertificate -FilePath "C:\windows\system32\Test.pfx"
```

```output
Password: ******
Signer Certificate:      David Chew (Self Certificate)
Time Certificate:
Time Stamp:
Path:                    C:\windows\system32\zap.pfx
```

Эта команда возвращает сведения о файле сертификата Test. pfx в системе.

### Пример 2. получение сертификата PFX с удаленного компьютера

```powershell
Invoke-Command -ComputerName "Server01" -ScriptBlock {Get-PfxCertificate -FilePath "C:\Text\TestNoPassword.pfx"} -Authentication CredSSP
```

Эта команда получает PFX-файл сертификата с удаленного компьютера Server01. Он использует `Invoke-Command` для удаленного выполнения `Get-PfxCertificate` команды.

Если файл сертификата PFX не защищен паролем, параметр **проверки подлинности** `Invoke-Command` должен иметь значение CredSSP.

## PARAMETERS

### -FilePath

Указывает полный путь к PFX-файлу защищенного файла. Если указать значение для этого параметра, то вводить `-FilePath` в командной строке не нужно.

```yaml
Type: System.String[]
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -LiteralPath

Полный путь к PFX-файлу защищенного файла. В отличие от **FilePath** значение параметра **LiteralPath** используется именно в том виде, в котором оно вводится. Никакие символы не интерпретируются как знаки подстановки. Если путь содержит escape-символы, заключите его в одинарные кавычки. Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.

```yaml
Type: System.String[]
Parameter Sets: ByLiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.String

Строку, содержащую путь к файлу, можно передать по конвейеру `Get-PfxCertificate` .

## Выходные данные

### System.Security.Cryptography.X509Certificates.X509Certificate2

`Get-PfxCertificate` Возвращает объект для каждого сертификата, который он получает.

## ПРИМЕЧАНИЯ

При использовании `Invoke-Command` командлета для удаленного выполнения `Get-PfxCertificate` команды, если файл сертификата pfx не защищен паролем, параметр **проверки подлинности** `Invoke-Command` должен иметь значение CredSSP.

## Связанные ссылки

[Get-AuthenticodeSignature](Get-AuthenticodeSignature.md)

[Set-AuthenticodeSignature](Set-AuthenticodeSignature.md)
