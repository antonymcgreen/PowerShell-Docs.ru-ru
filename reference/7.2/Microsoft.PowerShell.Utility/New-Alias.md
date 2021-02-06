---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-alias?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Alias
ms.openlocfilehash: 7f226af3cb221543cdae88930f661e2343d954b9
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604101"
---
# New-Alias

## Краткий обзор
Создает новый псевдоним.

## SYNTAX

```
New-Alias [-Name] <String> [-Value] <String> [-Description <String>] [-Option <ScopedItemOptions>] [-PassThru]
 [-Scope <String>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Командлет **New-Alias** создает новый псевдоним в текущем сеансе PowerShell.
Псевдонимы, созданные с помощью **New-Alias** , не сохраняются после выхода из сеанса или закрытия PowerShell.
Командлет Export-Alias можно использовать для сохранения сведений о псевдонимах в файл.
Позже можно будет использовать **Import-Alias** для получения сохраненных сведений о псевдониме.

## Примеры

### Пример 1. Создание псевдонима для командлета

```
PS C:\> New-Alias -Name "List" Get-ChildItem
```

Эта команда создает псевдоним с именем List для представления командлета Get-ChildItem.

### Пример 2. Создание псевдонима, доступного только для чтения, для командлета

```
PS C:\> New-Alias -Name "W" -Value Get-WmiObject -Description "quick wmi alias" -Option ReadOnly
PS C:\> Get-Alias -Name "W" | Format-List *
```

Эта команда создает псевдоним W для представления командлета Get-WmiObject.
Он создает описание, быстрый псевдоним WMI для псевдонима и делает его доступным только для чтения.
В последней строке командлет Get-Alias возвращает новый псевдоним и передает его в командлет Format-List по конвейеру для отображения всех данных о псевдониме.

## PARAMETERS

### -Description

Указывает описание псевдонима.
Можно ввести любую строку.
Если описание содержит пробелы, заключите его в кавычки.

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

### -Force

Указывает, что командлет действует как Set-Alias, если псевдоним с именем уже существует.

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

### -Name

Указывает новый псевдоним.
В псевдониме можно использовать любые буквы или цифры, но первым знаком не может быть цифра.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### Параметр-Option

Задает значение свойства **Options** псевдонима.
Допустимые значения:

- Нет: псевдоним не имеет ограничений (значение по умолчанию).
- ReadOnly: псевдоним можно удалить, но нельзя изменить, только используя параметр **Force**
- Константа: невозможно удалить или изменить псевдоним
- Частный: псевдоним доступен только в текущей области видимости
- AllScope: Псевдоним копируется во все новые создаваемые области
- Не указано: параметр не указан

Чтобы просмотреть свойство **Options** всех псевдонимов в сеансе, введите `Get-Alias | Format-Table -Property Name, Options -AutoSize` .

```yaml
Type: System.Management.Automation.ScopedItemOptions
Parameter Sets: (All)
Aliases:
Accepted values: None, ReadOnly, Constant, Private, AllScope, Unspecified

Required: False
Position: Named
Default value: [System.Management.Automation.ScopedItemOptions]::None
Accept pipeline input: False
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

### -Scope

Указывает область действия нового псевдонима.
Допустимые значения для этого параметра:

- Глобальный
- Локальная
- Скрипт
- Число относительно текущей области (от 0 до количества областей, где 0 — текущая область, а 1 — ее родитель).

По умолчанию используется значение Local.
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

### -Value

Указывает имя командлета или элемента команды, для которого создается псевдоним.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
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

### None

В этот командлет нельзя передать входные данные.

## Выходные данные

### None или System. Management. Automation. AliasInfo

При использовании параметра *PassThru* командлет **New-Alias** создает объект **System. Management. Automation. AliasInfo** , представляющий новый псевдоним.
В противном случае командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

* Чтобы создать новый псевдоним, используйте `Set-Alias` или `New-Alias` . Чтобы изменить псевдоним, используйте `Set-Alias` . Чтобы удалить псевдоним, используйте `Remove-Item` .

## Связанные ссылки

[Export-Alias](Export-Alias.md)

[Get-Alias](Get-Alias.md)

[Import-Alias](Import-Alias.md)

[Set-Alias](Set-Alias.md)

