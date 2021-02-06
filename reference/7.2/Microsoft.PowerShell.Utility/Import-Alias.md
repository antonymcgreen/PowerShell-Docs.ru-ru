---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-alias?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-Alias
ms.openlocfilehash: 20bc5d141b68cab19374afbe44b3472c72bf69bc
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600674"
---
# Import-Alias

## Краткий обзор
Импортирует список псевдонимов из файла.

## SYNTAX

### ByPath (по умолчанию)

```
Import-Alias [-Path] <String> [-Scope <String>] [-PassThru] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByLiteralPath

```
Import-Alias -LiteralPath <String> [-Scope <String>] [-PassThru] [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

`Import-Alias`Командлет импортирует список псевдонимов из файла.

Начиная с Windows PowerShell 3,0, в качестве функции безопасности не `Import-Alias` перезаписывает существующие псевдонимы по умолчанию.
Для перезаписи существующего псевдонима используйте параметр **Force** (предварительно убедившись в безопасности содержимого файла этого псевдонима).

## Примеры

### Пример 1. импорт псевдонимов из файла

```powershell
Import-Alias test.txt
```

Эта команда импортирует сведения о псевдонимах из файла Test.txt.

## PARAMETERS

### -Force

Позволяет командлету импортировать псевдоним, который уже определен и доступен только для чтения.
Для отображения сведений об определенных на текущий момент псевдонимах можно использовать следующую команду:

`Get-Alias | Select-Object Name, Options`

Если соответствующий псевдоним доступен только для чтения, это будет указано в значении свойства **Options**.

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

Задает путь к файлу, содержащему экспортированные сведения о псевдонимах.
В отличие от параметра **Path** значение параметра **LiteralPath** используется в точности так, как вводится.
Никакие символы не интерпретируются как знаки подстановки.
Если путь содержит escape-символы, заключите его в одинарные кавычки.
Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.

```yaml
Type: System.String
Parameter Sets: ByLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -PassThru

Возвращает объект, представляющий элемент, с которым вы работаете.
По умолчанию этот командлет не создает выходные данные.

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

### -Path

Задает путь к файлу, содержащему экспортированные сведения о псевдонимах.
Использовать подстановочные знаки можно, но они должны указывать только на одно имя.

```yaml
Type: System.String
Parameter Sets: ByPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -Scope

Задает область, в которую будут импортироваться псевдонимы.
Допустимые значения для этого параметра:

- Глобальный
- Локальная
- Скрипт
- Номер относительно текущей области (от 0 до количества областей, где 0 — это текущая область, а 1 — ее родительская область).

Значение по умолчанию — Local.
Дополнительные сведения см. в разделе about_Scopes.

```yaml
Type: System.String
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

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.String

Можно передать строку, содержащую путь, в `Import-Alias` .

## Выходные данные

### None или System. Management. Automation. AliasInfo

При использовании параметра **PassThru** `Import-Alias` возвращает объект **System. Management. Automation. AliasInfo** , представляющий псевдоним.
В противном случае командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Export-Alias](Export-Alias.md)

[Get-Alias](Get-Alias.md)

[New-Alias](New-Alias.md)

[Set-Alias](Set-Alias.md)

