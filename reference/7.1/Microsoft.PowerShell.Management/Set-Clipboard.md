---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-clipboard?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Clipboard
ms.openlocfilehash: 1ee55dfaf4ecd3e46bedd8f356b1f677180c9c62
ms.sourcegitcommit: 7b376314e7640c39a53aac9f0db8bb935514a960
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2020
ms.locfileid: "96564560"
---
# Set-Clipboard

## Краткий обзор
Задает содержимое буфера обмена.

## SYNTAX

```
Set-Clipboard -Value <String[]> [-Append] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Set-Clipboard`Командлет задает содержимое буфера обмена.

> [!NOTE]
> В Linux для этого командлета требуется, `xclip` чтобы программа была в пути.

## Примеры

### Пример 1. копирование текста в буфер обмена

```powershell
Set-Clipboard -Value "This is a test string"
```

### Пример 2. копирование содержимого файла в буфер обмена

В этом примере содержимое файла переводится в буфер обмена. В этом примере мы получаем открытый ключ SSH, чтобы его можно было вставлять в другое приложение, например GitHub.

```powershell
Get-Content C:\Users\user1\.ssh\id_ed25519.pub | Set-Clipboard
```

## PARAMETERS

### — Добавление

Указывает, что командлет не очищает буфер обмена и добавляет к нему содержимое.

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

### -Confirm

Запрос подтверждения перед выполнением командлета.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Показывает, что произойдет при запуске командлета. Командлет не выполняется.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Value

Строковые значения, которые необходимо добавить в буфер обмена.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.String[]

## Выходные данные

## ПРИМЕЧАНИЯ

В редких случаях при `Set-Clipboard` быстром выполнении с большим количеством значений, например в цикле, вы можете регулярно получать пустое значение из буфера обмена. Это можно исправить с помощью `Start-Sleep -Milliseconds 1` в цикле.

## Связанные ссылки

[Get-Clipboard](Get-Clipboard.md)
