---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/tee-object?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Tee-Object
ms.openlocfilehash: 47c1eb6b31f762e3950c07f9edec81a081ce616e
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93226377"
---
# Tee-Object

## Краткий обзор
Сохраняет выходные данные команды в файле или переменной, а также отправляет их в конвейер.

## SYNTAX

### Файл (по умолчанию)

```
Tee-Object [-InputObject <PSObject>] [-FilePath] <String> [-Append] [<CommonParameters>]
```

### литералфиле

```
Tee-Object [-InputObject <PSObject>] -LiteralPath <String> [<CommonParameters>]
```

### Переменная

```
Tee-Object [-InputObject <PSObject>] -Variable <String> [<CommonParameters>]
```

## DESCRIPTION

`Tee-Object`Командлет перенаправляет выходные данные, то есть отправляет выходные данные команды в двух направлениях (например, букве T). Она сохраняет выходные данные команды в файле или переменной, а также отправляет их в конвейер. Если `Tee-Object` — Последняя команда в конвейере, выходные данные команды отображаются в командной строке.

## Примеры

### Пример 1. вывод процессов в файл и в консоль

В этом примере возвращается список процессов, запущенных на компьютере, и результат отправляется в файл.
Так как второй путь не указан, процессы также отображаются в консоли.

```powershell
Get-Process | Tee-Object -FilePath "C:\Test1\testfile2.txt"
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)    Id ProcessName
-------  ------    -----      ----- -----   ------    -- -----------
83       4     2300       4520    39     0.30    4032 00THotkey
272      6     1400       3944    34     0.06    3088 alg
81       3      804       3284    21     2.45     148 ApntEx
81       4     2008       5808    38     0.75    3684 Apoint
...
```

### Пример 2. вывод процессов в переменную и `Select-Object`

Этот пример возвращает список процессов, запущенных на компьютере, сохраняет их в `$proc` переменную и передает их в `Select-Object` .

```powershell
Get-Process notepad | Tee-Object -Variable proc | Select-Object processname,handles
```

```Output
ProcessName                              Handles
-----------                              -------
notepad                                  43
notepad                                  37
notepad                                  38
notepad                                  38
```

`Select-Object`Командлет выбирает **processName** и **обрабатывает** свойства. Обратите внимание, что `$proc` Переменная включает сведения по умолчанию, возвращаемые `Get-Process` .

### Пример 3. вывод системных файлов в два файла журнала

В этом примере список системных файлов сохраняется в двух файлах журнала, в совокупном файле и в текущем файле.

```powershell
Get-ChildItem -Path D: -File -System -Recurse |
  Tee-Object -FilePath "c:\test\AllSystemFiles.txt" -Append |
    Out-File c:\test\NewSystemFiles.txt
```

Команда использует `Get-ChildItem` командлет для рекурсивного поиска системных файлов на диске D:. Оператор конвейера (|) отправляет список в `Tee-Object` , который добавляет список в файл AllSystemFiles.txt и передает список по конвейеру в `Out-File` командлет, который сохраняет список в файле NewSystemFiles.txt.

## PARAMETERS

### — Добавление

Указывает, что командлет добавляет выходные данные в указанный файл. Без этого параметра новое содержимое заменяет все существующее содержимое файла без предупреждения.

Этот параметр впервые появился в Windows PowerShell 3.0.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: File
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilePath

Указывает файл, который этот командлет сохраняет в подстановочных знаках, но должен разрешаться в один файл.

```yaml
Type: System.String
Parameter Sets: File
Aliases: Path

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -InputObject

Указывает объект, который необходимо показать и сохранить. Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты. Также можно передать объект в `Tee-Object` .

При использовании параметра **InputObject** с параметром `Tee-Object` , а не с результатами команды трубопроводов в `Tee-Object` значение **InputObject** рассматривается как один объект, даже если значение является коллекцией.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LiteralPath

Указывает файл, в который этот командлет сохраняет объект. В отличие от **FilePath** значение параметра **LiteralPath** используется именно в том виде, в котором оно вводится. Никакие символы не интерпретируются как знаки подстановки. Если путь содержит escape-символы, заключите его в одинарные кавычки. Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.

```yaml
Type: System.String
Parameter Sets: LiteralFile
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Variable

Указывает переменную, в которую командлет сохраняет объект. Введите имя переменной без предшествующего знака доллара ( `$` ).

```yaml
Type: System.String
Parameter Sets: Variable
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.Management.Automation.PSObject

Вы можете передать объекты в `Tee-Object` .

## Выходные данные

### System.Management.Automation.PSObject

`Tee-Object` Возвращает перенаправляемый объект.

## ПРИМЕЧАНИЯ

Можно также использовать `Out-File` командлет или оператор перенаправления, оба из которых сохраняют выходные данные в файле, но не отправляют их по конвейеру.

Начиная с PowerShell 6, `Tee-Object` при записи в файлы использует кодировку UTF-8 без спецификации. Если требуется другая кодировка, используйте `Out-File` командлет с параметром **Encoding** .

## Связанные ссылки

[Compare-Object](Compare-Object.md)

[ForEach-Object](../Microsoft.PowerShell.Core/ForEach-Object.md)

[Group-Object](Group-Object.md)

[Measure-Object;](Measure-Object.md)

[New-Object](New-Object.md)

[Select-Object](Select-Object.md)

[Sort-Object](Sort-Object.md)

[Where-Object](../Microsoft.PowerShell.Core/Where-Object.md)

[about_Redirection](../Microsoft.PowerShell.Core/About/about_Redirection.md)
