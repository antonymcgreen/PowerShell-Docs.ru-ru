---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 05/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/invoke-history?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-History
ms.openlocfilehash: 7fb4341a84706f7d31d463bb527a1a31f387c2ae
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604483"
---
# Invoke-History

## Краткий обзор
Выполняет команды из журнала сеанса.

## SYNTAX

```
Invoke-History [[-Id] <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Invoke-History`Командлет запускает команды из журнала сеанса. Можно передать объекты, представляющие команды, из Get-History в `Invoke-History` или же можно указать команды в текущем журнале, используя их **идентификационный** номер. Чтобы найти идентификационный номер команды, используйте `Get-History` командлет.

Журнал сеанса управляется отдельно от журнала, поддерживаемого модулем **PSReadLine** .
Оба журнала доступны в сеансах, где загружен **PSReadLine** . Этот командлет работает только с журналом сеанса. Дополнительные сведения см. в разделе [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).

## Примеры

### Пример 1. запуск последней команды в журнале

В этом примере выполняется последняя или самая последняя команда в журнале сеанса. Можно сократить эту команду, например `r` , псевдоним для `Invoke-History` .

```powershell
Invoke-History
```

### Пример 2. выполнение команды с указанным ИДЕНТИФИКАТОРом

В этом примере выполняется команда в журнале сеанса с **идентификатором** 132. Поскольку имя параметра **ID** является необязательным, можно сократить эту команду следующим образом: `Invoke-History 132` , `ihy 132` или `r 132` .

```powershell
Invoke-History -Id 132
```

### Пример 3. запуск последней команды с помощью текста команды

В этом примере выполняется последняя `Get-Process` команда в журнале сеанса. При вводе символов для параметра **ID** `Invoke-History` выполняет первую найденную команду, совпадающую с шаблоном, начиная с самых последних команд.

```powershell
Invoke-History -Id get-pr
```

> [!NOTE]
> Сопоставление шаблонов не учитывает регистр, но шаблон соответствует началу строки.

### Пример 4. выполнение последовательности команд из журнала

В этом примере выполняются команды от 16 до 24. Так как вы можете вывести только одно значение **идентификатора** , команда использует `ForEach-Object` командлет для выполнения `Invoke-History` команды один раз для каждого значения **идентификатора** .

```powershell
16..24 | ForEach {Invoke-History -Id $_ }
```

### Пример 5

В этом примере выполняются семь команд в журнале, которые заканчиваются командой 255 (от 249 до 255). Он использует `Get-History` командлет для получения команд. Так как можно вывести только одно значение **идентификатора** , команда использует `ForEach-Object` командлет для `Invoke-History` однократного выполнения команды для каждого значения **идентификатора** .

```powershell
Get-History -Id 255 -Count 7 | ForEach {Invoke-History -Id $_.Id}
```

## PARAMETERS

### -Id

Указывает **идентификатор** команды в журнале. Можно ввести **идентификационный** номер команды или несколько первых символов команды.

Если ввести символы, `Invoke-History` сначала будет соответствовать последним командам. Если этот параметр не указан, `Invoke-History` выполняет последнюю или последнюю команду. Чтобы найти **идентификационный** номер команды, используйте `Get-History` командлет.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.String

**Идентификатор** журнала можно передать в этот командлет по конвейеру.

## Выходные данные

### None

Этот командлет не создает никаких выходных данных, но выходные данные могут создаваться командами, `Invoke-History` запускающими.

## ПРИМЕЧАНИЯ

Журнал сеанса — это список команд, введенных за время сеанса. В журнале сеанса представлен порядок выполнения, состояние, время начала и завершения выполнения команды. По мере ввода каждой команды PowerShell добавляет его в журнал, чтобы его можно было использовать повторно. Дополнительные сведения о журнале сеанса см. в разделе [about_History](About/about_History.md).

Также можно ссылаться `Invoke-History` по встроенным псевдонимам `r` и `ihy` . Дополнительные сведения см. в разделе [about_Aliases](About/about_Aliases.md).

## Связанные ссылки

[Add-History](Add-History.md)

[Clear-History](Clear-History.md)

[Get-History](Get-History.md)

