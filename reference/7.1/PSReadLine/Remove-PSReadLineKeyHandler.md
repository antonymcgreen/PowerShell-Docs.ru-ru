---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSReadLine
ms.date: 12/07/2018
online version: https://docs.microsoft.com/powershell/module/psreadline/remove-psreadlinekeyhandler?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSReadLineKeyHandler
ms.openlocfilehash: a13677035581a081df51917bc6b82efec0ff2156
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "93233177"
---
# Remove-PSReadLineKeyHandler

## Краткий обзор
Удаляет привязку клавиш.

## SYNTAX

```
Remove-PSReadLineKeyHandler [-Chord] <String[]> [-ViMode <ViMode>] [<CommonParameters>]
```

## DESCRIPTION

`Remove-PSReadLineKeyHandler`Командлет удаляет указанную привязку ключа.

## Примеры

### Пример 1. Удаление привязки

```powershell
Remove-PSReadLineKeyHandler -Chord Ctrl+B
```

Эта команда удаляет привязку из сочетания клавиш или аккорд `Ctrl+B` . `Ctrl+B`Аккорд создается в этой `Set-PSReadLineKeyHandler` статье.

## PARAMETERS

### -Chord

Указывает массив ключей или последовательностей удаляемых ключей. Одну привязку можно задать в одной строке. Если привязка представляет собой сочетание клавиш, разделите сочетания запятой, как показано в следующем примере:

`Ctrl+x,Ctrl+l`

Этот параметр принимает массив строк. Каждая строка — это отдельная привязка, а не сочетание клавиш для одной привязки.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Key

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Вимоде

Укажите режим VI, к которому применяется привязка. Возможные значения: INSERT, Command.

```yaml
Type: Microsoft.PowerShell.ViMode
Parameter Sets: (All)
Aliases:
Accepted values: Insert, Command

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет

Нельзя передать объекты в этот командлет с помощью конвейера.

## Выходные данные

### Нет

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Get-PSReadLineKeyHandler](Get-PSReadLineKeyHandler.md)

[Get-PSReadLineOption](Get-PSReadLineOption.md)

[Set-PSReadLineOption](Set-PSReadLineOption.md)

[Set-PSReadLineKeyHandler](Set-PSReadLineKeyHandler.md)

