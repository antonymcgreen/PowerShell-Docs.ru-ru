---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSReadLine
ms.date: 12/07/2018
online version: https://docs.microsoft.com/powershell/module/psreadline/set-psreadlinekeyhandler?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSReadLineKeyHandler
ms.openlocfilehash: 97d342d9f5d7227fb831794055c2cfa75b8cf765
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "93233166"
---
# Set-PSReadLineKeyHandler

## Краткий обзор
Привязывает ключи к функциям, определяемым пользователем или PSReadLine Key.

## SYNTAX

### ScriptBlock

```
Set-PSReadLineKeyHandler [-ScriptBlock] <ScriptBlock> [-BriefDescription <String>]
 [-Description <String>] [-Chord] <String[]> [-ViMode <ViMode>] [<CommonParameters>]
```

### Компонент

```
Set-PSReadLineKeyHandler [-Chord] <String[]> [-ViMode <ViMode>] [-Function] <String>
 [<CommonParameters>]
```

## DESCRIPTION

`Set-PSReadLineKeyHandler`Командлет настраивает результат при нажатии клавиши или последовательности клавиш. С помощью пользовательских привязок клавиш можно практически все, что можно сделать в сценарии PowerShell.

## Примеры

### Пример 1. Привязка клавиши со стрелкой к функции

Эта команда привязывает клавишу Стрелка вверх к функции **хисторисеарчбакквард** . Эта функция выполняет поиск в журнале команд командных строк, начинающихся с текущего содержимого командной строки.

```powershell
Set-PSReadLineKeyHandler -Chord UpArrow -Function HistorySearchBackward
```

### Пример 2. Привязка ключа к блоку сценария

В этом примере показано, как можно использовать один ключ для выполнения команды. Команда привязывает ключ `Ctrl+B` к блоку скрипта, который очищает строку, вставляет слово «Build», а затем принимает строку.

```powershell
Set-PSReadLineKeyHandler -Chord Ctrl+B -ScriptBlock {
    [Microsoft.PowerShell.PSConsoleReadLine]::RevertLine()
    [Microsoft.PowerShell.PSConsoleReadLine]::Insert('build')
    [Microsoft.PowerShell.PSConsoleReadLine]::AcceptLine()
}
```

## PARAMETERS

### -Бриефдескриптион

Краткое описание сочетания клавиш. Это описание отображается `Get-PSReadLineKeyHandler` командлетом.

```yaml
Type: System.String
Parameter Sets: ScriptBlock
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Chord

Ключ или последовательность ключей, которые должны быть привязаны к блоку функции или скрипта. Используйте одну строку для указания одной привязки. Если привязка представляет собой сочетание клавиш, разделите сочетания запятой, как показано в следующем примере:

`Ctrl+X,Ctrl+L`

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

### -Description

Задает более подробное описание привязки ключа, которое отображается в выходных данных `Get-PSReadLineKeyHandler` командлета.

```yaml
Type: System.String
Parameter Sets: ScriptBlock
Aliases: LongDescription

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Function

Указывает имя существующего обработчика ключей, предоставляемого PSReadLine. Этот параметр позволяет повторно привязывать существующие привязки к ключам или привязывать обработчик, который в настоящее время не привязан.

```yaml
Type: System.String
Parameter Sets: Function
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScriptBlock

Задает значение блока скрипта для запуска при входе в аккорд. PSReadLine передает один или два параметра в этот блок сценария. Первый параметр — это объект **консолекэйинфо** , представляющий нажатую клавишу. Вторым аргументом может быть любой объект в зависимости от контекста.

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlock
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Вимоде

Укажите режим VI, к которому применяется привязка.

Допустимые значения:

- Вставить
- Get-Help

```yaml
Type: Microsoft.PowerShell.ViMode
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет

Нельзя передать объекты в этот командлет с помощью конвейера.

## Выходные данные

### Нет

Этот командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Get-PSReadLineKeyHandler](Get-PSReadLineKeyHandler.md)

[Remove-PSReadLineKeyHandler](Remove-PSReadLineKeyHandler.md)

[Get-PSReadLineOption](Get-PSReadLineOption.md)

[Set-PSReadLineOption](Set-PSReadLineOption.md)

