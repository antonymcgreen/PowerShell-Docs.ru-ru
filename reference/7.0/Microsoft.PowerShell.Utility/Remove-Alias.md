---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/24/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-alias?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Alias
ms.openlocfilehash: 6f98a910e43b87793ac4f2af8ffb069d3e5d47ba
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93225809"
---
# Remove-Alias

## Краткий обзор
Удаление псевдонима из текущего сеанса.

## SYNTAX

### Default (по умолчанию)

```
Remove-Alias [-Name] <String[]> [-Scope <String>] [-Force] [<CommonParameters>]
```

## DESCRIPTION

`Remove-Alias`Командлет удаляет псевдоним из текущего сеанса PowerShell. Чтобы удалить псевдоним с свойством **Option** , имеющим значение **ReadOnly** , используйте параметр **Force** .

`Remove-Alias`Командлет был представлен в PowerShell 6,0.

## Примеры

### Пример 1. Удаление псевдонима

В этом примере удаляется псевдоним с именем `del` , который представляет `Remove-Item` командлет.

```powershell
Remove-Alias -Name del
```

### Пример 2. Удаление всех псевдонимов, не являющихся константами

В этом примере удаляются все псевдонимы из текущего сеанса PowerShell, за исключением псевдонимов со свойством **Options** , для которых установлено значение **Constant** . После выполнения команды псевдонимы будут доступны в других сеансах PowerShell или в новых сеансах PowerShell.

```powershell
Get-Alias | Where-Object { $_.Options -NE "Constant" } | Remove-Alias -Force
```

`Get-Alias` Получает все псевдонимы в сеансе PowerShell и отправляет объекты по конвейеру.
`Where-Object` использует блок скрипта, а свойство Variables ( `$_` ) и **Options** представляет текущий объект конвейера. Параметр **Ne** (не равно) выбирает объекты, для которых **не задано значение "** **константа** ". `Remove-Alias` использует параметр **Force** для удаления псевдонимов, в том числе псевдонимов только для чтения, из сеанса PowerShell.

## PARAMETERS

### -Force

Указывает, что командлет удаляет псевдоним, включая псевдонимы со свойством **Option** , имеющим значение **ReadOnly** . Параметр **Force** не может удалить псевдоним с свойством **параметра** , имеющим значение **Constant** .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Указывает имя удаляемого псевдонима.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Scope

Затрагивает только псевдонимы в указанной области. Область по умолчанию — **Local** . Дополнительные сведения см. в разделе [about_Scopes](../microsoft.powershell.core/about/about_scopes.md).

Допустимые значения для этого параметра:

- Глобальный
- Локальная
- Сценарий
- Номер относительно текущей области (от 0 до количества областей, где 0 — это текущая область, а 1 — ее родительская область).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Local
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.String[]

Объект псевдонима можно передать в командлет **Remove-Alias** .

## Выходные данные

### Нет

Этот командлет не возвращает никаких выходных данных.

## ПРИМЕЧАНИЯ

Изменения влияют только на текущую область. Чтобы удалить псевдоним из всех сеансов, добавьте команду **Remove-Alias** в профиль PowerShell.

Дополнительные сведения см. в разделе [about_Aliases](../microsoft.powershell.core/about/about_aliases.md).

## Связанные ссылки

[about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

[Export-Alias](Export-Alias.md)

[Get-Alias](Get-Alias.md)

[Import-Alias](Import-Alias.md)

[New-Alias](New-Alias.md)

[Set-Alias](Set-Alias.md)

[Where-Object](../Microsoft.PowerShell.Core/Where-Object.md)
