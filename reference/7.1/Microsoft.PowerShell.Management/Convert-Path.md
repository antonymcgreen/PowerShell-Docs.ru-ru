---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/12/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/convert-path?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Convert-Path
ms.openlocfilehash: 498620ee79285f0c0fe2a001b99fe5dc179ea0ac
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229462"
---
# Convert-Path

## Краткий обзор
Преобразует путь из пути PowerShell в путь поставщика PowerShell.

## SYNTAX

### Путь (по умолчанию)

```
Convert-Path [-Path] <String[]> [<CommonParameters>]
```

### LiteralPath

```
Convert-Path -LiteralPath <String[]> [<CommonParameters>]
```

## DESCRIPTION

`Convert-Path`Командлет преобразует путь из пути PowerShell в путь поставщика PowerShell.

## Примеры

### Пример 1. преобразование рабочего каталога в стандартный путь файловой системы

В этом примере текущий рабочий каталог, представленный точкой (), преобразуется `.` в стандартный путь файловой системы.

```
PS C:\> Convert-Path .
C:\
```

### Пример 2. преобразование пути поставщика в стандартный путь реестра

В этом примере путь к поставщику PowerShell преобразуется в стандартный путь реестра.

```powershell
PS C:\> Convert-Path HKLM:\Software\Microsoft
HKEY_LOCAL_MACHINE\Software\Microsoft
```

### Пример 3. преобразование пути в строку

В этом примере путь преобразуется в корневой каталог текущего поставщика, который является поставщиком FileSystem, в строку.

```powershell
PS C:\> Convert-Path ~
C:\Users\User01
```

## PARAMETERS

### -LiteralPath

Указывает преобразуемый путь в виде массива строк. Значение параметра **LiteralPath** используется точно так же, как оно введено. Никакие символы не интерпретируются как знаки подстановки. Если путь содержит escape-символы, заключите его в одинарные кавычки. Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path

Указывает путь PowerShell для преобразования.

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.String

В этот командлет можно передать по конвейеру путь, но не литеральный путь.

## Выходные данные

### System.String

Этот командлет возвращает строку, содержащую преобразованный путь.

## ПРИМЕЧАНИЯ

Командлеты, которые содержат существительное пути, управляют именами путей и возвращают имена в кратком формате, который могут интерпретировать все поставщики PowerShell. Они предназначены для использования в программах и скриптах, где имя пути или его часть должны отображаться в определенном формате. Используйте их, например **dirname** , **нормпас** , **реалпас** , **Join** или другие манипуляторы пути.

Командлеты для работы с путями можно использовать с различными поставщиками, включая FileSystem, Registry и Certificate.

Этот командлет предназначен для работы с данными, предоставляемыми любым поставщиком. Чтобы вывести список поставщиков, доступных в данном сеансе, введите командлет `Get-PSProvider`. Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).

`Convert-Path` преобразует только существующие пути. Его нельзя использовать для преобразования расположения, которое еще не существует.

## Связанные ссылки

[Join-Path](Join-Path.md)

[Resolve-Path](Resolve-Path.md)

[Split-Path](Split-Path.md)

[Test-Path](Test-Path.md)

[Get-PSProvider](Get-PSProvider.md)

