---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-temporaryfile?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-TemporaryFile
ms.openlocfilehash: c4bfe6b4ed04ae638421c18f5095403057dc03c9
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93225837"
---
# New-TemporaryFile

## Краткий обзор
Создает временный файл.

## SYNTAX

```
New-TemporaryFile [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Этот командлет создает временные файлы, которые можно использовать в скриптах.

`New-TemporaryFile`Командлет создает пустой файл с `.tmp` расширением имени файла.
Этот командлет называет файл `tmp<NNNN>.tmp` , где `<NNNN>` — случайное шестнадцатеричное число.
Командлет создает файл во **временной** папке.

Этот командлет использует метод [path. жеттемппас ()](/dotnet/api/system.io.path.gettemppath) для поиска **временной** папки. Этот метод проверяет наличие переменных среды в следующем порядке и использует первый найденный путь:

- На платформах Windows:

  1. Путь, заданный переменной среды TMP.
  1. Путь, заданный переменной среды TEMP.
  1. Путь, заданный переменной среды USERPROFILE.
  1. Каталог Windows.

- На платформах, отличных от Windows: использует путь, заданный переменной среды TMPDIR.

## Примеры

### Пример 1. Создание временного файла

```powershell
$TempFile = New-TemporaryFile
```

Эта команда создает `.tmp` файл во временной папке, а затем сохраняет ссылку на файл в `$TempFile` переменной. Этот файл можно использовать позже в скрипте.

## PARAMETERS

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

Показывает, что произойдет при запуске командлета.
Командлет не выполняется.

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

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## Входные данные

## Выходные данные

### System. IO. FileInfo

Этот командлет возвращает объект **FileInfo** , представляющий временный файл.

## ПРИМЕЧАНИЯ

## Связанные ссылки
