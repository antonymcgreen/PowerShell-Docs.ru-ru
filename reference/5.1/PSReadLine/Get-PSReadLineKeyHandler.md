---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSReadLine
ms.date: 12/07/2018
online version: https://docs.microsoft.com/powershell/module/psreadline/get-psreadlinekeyhandler?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSReadLineKeyHandler
ms.openlocfilehash: 7cebb2a601714992759a310b6012deee5157e322
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "93233033"
---
# Get-PSReadLineKeyHandler

## Краткий обзор
Возвращает ключевые привязки для модуля PSReadLine.

## SYNTAX

```
Get-PSReadLineKeyHandler [-Bound] [-Unbound] [<CommonParameters>]
```

## DESCRIPTION

Командлет **Get-PSReadLineKeyHandler** Возвращает привязки ключей, привязанные к текущему объекту.

## Примеры

### Пример 1. получение всех сопоставлений ключей

Эта команда возвращает все сопоставления ключей, связанные и несвязанные.

```powershell
Get-PSReadLineKeyHandler -Bound -Unbound
```

```Output
Key                   Function                Description
---                   --------                -----------
Enter                 AcceptLine              Accept the input or move to the next line if input is missing a closing token.
Shift+Enter           AddLine                 Move the cursor to the next line without attempting to execute the input
Escape                RevertLine              Equivalent to undo all edits (clears the line except lines imported from history)
LeftArrow             BackwardChar            Move the cursor back one character
RightArrow            ForwardChar             Move the cursor forward one character
Ctrl+LeftArrow        BackwardWord            Move the cursor to the beginning of the current or previous word
Ctrl+RightArrow       NextWord                Move the cursor forward to the start of the next word
Shift+LeftArrow       SelectBackwardChar      Adjust the current selection to include the previous character
Shift+RightArrow      SelectForwardChar       Adjust the current selection to include the next character
Ctrl+Shift+LeftArrow  SelectBackwardWord      Adjust the current selection to include the previous word
Ctrl+Shift+RightArrow SelectNextWord          Adjust the current selection to include the next word
UpArrow               PreviousHistory         Replace the input with the previous item in the history
DownArrow             NextHistory             Replace the input with the next item in the history
Home                  BeginningOfLine         Move the cursor to the beginning of the line
End                   EndOfLine               Move the cursor to the end of the line
Shift+Home            SelectBackwardsLine     Adjust the current selection to include from the cursor to the end of the line
Shift+End             SelectLine              Adjust the current selection to include from the cursor to the start of the line
Delete                DeleteChar              Delete the character under the cursor
Backspace             BackwardDeleteChar      Delete the character before the cursor
Ctrl+Spacebar         MenuComplete            Complete the input if there is a single completion, otherwise complete the input by selecting from a menu o...
Tab                   TabCompleteNext         Complete the input using the next completion
Shift+Tab             TabCompletePrevious     Complete the input using the previous completion
Ctrl+a                SelectAll               Select the entire line. Moves the cursor to the end of the line
Ctrl+c                CopyOrCancelLine        Either copy selected text to the clipboard, or if no text is selected, cancel editing the line with Cancel...
Ctrl+C                Copy                    Copy selected region to the system clipboard.  If no region is selected, copy the whole line
Ctrl+l                ClearScreen             Clear the screen and redraw the current line at the top of the screen
Ctrl+r                ReverseSearchHistory    Search history backwards interactively
...
```

### Пример 2. получение привязанных ключей

Эта команда возвращает только связанные ключи и сочетания клавиш.

```powershell
Get-PSReadLineKeyHandler
```

```Output
Key                   Function                Description
---                   --------                -----------
Enter                 AcceptLine              Accept the input or move to the next line if input is missing a closing token.
Shift+Enter           AddLine                 Move the cursor to the next line without attempting to execute the input
Escape                RevertLine              Equivalent to undo all edits (clears the line except lines imported from history)
LeftArrow             BackwardChar            Move the cursor back one character
RightArrow            ForwardChar             Move the cursor forward one character
Ctrl+LeftArrow        BackwardWord            Move the cursor to the beginning of the current or previous word
Ctrl+RightArrow       NextWord                Move the cursor forward to the start of the next word
Shift+LeftArrow       SelectBackwardChar      Adjust the current selection to include the previous character
Shift+RightArrow      SelectForwardChar       Adjust the current selection to include the next character
Ctrl+Shift+LeftArrow  SelectBackwardWord      Adjust the current selection to include the previous word
Ctrl+Shift+RightArrow SelectNextWord          Adjust the current selection to include the next word
UpArrow               PreviousHistory         Replace the input with the previous item in the history
DownArrow             NextHistory             Replace the input with the next item in the history
Home                  BeginningOfLine         Move the cursor to the beginning of the line
End                   EndOfLine               Move the cursor to the end of the line
Shift+Home            SelectBackwardsLine     Adjust the current selection to include from the cursor to the end of the line
Shift+End             SelectLine              Adjust the current selection to include from the cursor to the start of the line
Delete                DeleteChar              Delete the character under the cursor
Backspace             BackwardDeleteChar      Delete the character before the cursor
Ctrl+Spacebar         MenuComplete            Complete the input if there is a single completion, otherwise complete the input by selecting from a menu o...
Tab                   TabCompleteNext         Complete the input using the next completion
...
```

## PARAMETERS

### С привязкой

Указывает, что этот командлет возвращает функции, которые связаны.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### — Без привязки

Указывает, что этот командлет возвращает функции, которые не привязаны.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет

Нельзя передать объекты в этот командлет с помощью конвейера.

## Выходные данные

### Microsoft. PowerShell. Кэйхандлер

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Remove-PSReadLineKeyHandler](Remove-PSReadLineKeyHandler.md)

[Get-PSReadLineOption](Get-PSReadLineOption.md)

[Set-PSReadLineOption](Set-PSReadLineOption.md)

[Set-PSReadLineKeyHandler](Set-PSReadLineKeyHandler.md)
