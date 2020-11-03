---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 07/21/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-variable?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Variable
ms.openlocfilehash: 2e0e9388c592cb83dd7609fed663ae220e380750
ms.sourcegitcommit: 84fcc90bd018ab76ac4e964d53e7c9c2b5a7b6c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2020
ms.locfileid: "93230110"
---
# Remove-Variable

## Краткий обзор
Удаляет переменную и ее значение.

## SYNTAX

```
Remove-Variable [-Name] <String[]> [-Include <String[]>] [-Exclude <String[]>] [-Force] [-Scope <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Remove-Variable`Командлет удаляет переменную и ее значение из области, в которой она определена, например в текущем сеансе. Этот командлет невозможно использовать для удаления переменных, задающихся как константы или принадлежащих системе.

## Примеры

### Пример 1. Удаление переменной

```powershell
Remove-Variable Smp
```

Эта команда удаляет `$Smp` переменную.

## PARAMETERS

### -Exclude

Указывает массив элементов, который не пропускается этим командлетом из операции. Значение этого параметра определяет параметр **Name** . Введите часть имени или шаблон, например "s*". Разрешено использовать подстановочные знаки.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Force

Указывает, что командлет удаляет переменную, даже если она доступна только для чтения. Даже при использовании параметра **Force** командлет не может удалить константу.

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

### -Include

Указывает массив элементов, которые этот командлет удаляет в операции. Значение этого параметра определяет параметр **Name** . Введите часть имени или шаблон, например "s*". Разрешено использовать подстановочные знаки.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Name

Указывает имя удаляемой переменной. Имя параметра ( **Name** ) является необязательным.
Разрешены подстановочные знаки

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Scope

Возвращает только те переменные, которые относятся к указанной области. Допустимые значения для этого параметра:

- Глобальный
- Локальная
- Сценарий
- Номер относительно текущей области (от 0 до количества областей, где 0 — это текущая область, а 1 — ее родительская область).

По умолчанию используется значение Local. Дополнительные сведения см. в разделе [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).

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

### System. Management. Automation. PSVariable

Объект переменной можно передать в `Remove-Variable` .

## Выходные данные

### Нет

Этот командлет не возвращает никакие выходные данные.

## ПРИМЕЧАНИЯ

- Изменения затрагивают только текущую область, например сеанс. Чтобы удалить переменную из всех сеансов, добавьте `Remove-Variable` команду в профиль PowerShell.

- Также можно ссылаться `Remove-Variable` по встроенному псевдониму `rv` . Дополнительные сведения см. в разделе [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).

## Связанные ссылки

[Clear-Variable](Clear-Variable.md)

[Get-Variable](Get-Variable.md)

[New-Variable](New-Variable.md)

[Set-Variable](Set-Variable.md)
