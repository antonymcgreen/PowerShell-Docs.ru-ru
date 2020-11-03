---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/clear-variable?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-Variable
ms.openlocfilehash: c696fb0f9d95548d80e772809c6f83e86f1581f6
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227742"
---
# Clear-Variable

## Краткий обзор
Удаляет значение переменной.

## SYNTAX

```
Clear-Variable [-Name] <String[]> [-Include <String[]>] [-Exclude <String[]>] [-Force] [-PassThru]
 [-Scope <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Командлет **clear-variable** удаляет данные, хранящиеся в переменной, но не удаляет переменную.
В результате переменная получает значение NULL (пустое).
Если переменная имеет указанный тип данных или объект, этот командлет сохраняет тип объекта, хранящегося в переменной.

## Примеры

### Пример 1. Удаление значений глобальных переменных, начинающихся со строки поиска

```
PS C:\> Clear-Variable my* -Scope Global
```

Эта команда удаляет значения глобальных переменных, имена которых начинаются с My.

### Пример 2. Очистка переменной в дочерней области, но не родительской области

```
PS C:\> $a=3
PS C:\> &{ Clear-Variable a }
PS C:\> $a
3
```

Эти команды показывают, что при очистке переменной в дочерней области значение в родительской области не удаляется.
Первая команда задает значение переменной $A равным 3.
Вторая команда использует оператор Invoke (&) для выполнения команды **clear-variable** в новой области.
В результате в дочерней области переменная очищается (хотя она и не существовала), а в локальной — нет.
Третья команда, которая получает значение $A, показывает, что значение 3 не затрагивается.

### Пример 3. Удаление значения указанной переменной

```
PS C:\> Clear-Variable -Name "Processes"
```

Эта команда удаляет значение переменной с именем Processes.
После того как командлет завершит операцию, переменная с именем Processes по-прежнему существует, но имеет значение null.

## PARAMETERS

### -Exclude

Указывает массив элементов, пропущенных этим командлетом в операции.
Значение этого параметра определяет параметр *Name* .
Введите часть имени или шаблон, например "s*".
Разрешено использовать подстановочные знаки.

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

Позволяет командлету очистить переменную, даже если она доступна только для чтения.
Даже при использовании параметра Force командлет не может очистить константу.

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

Задает массив элементов, включаемых этим командлетом в операцию.
Значение этого параметра определяет параметр *Name* .
Введите часть имени или шаблон, например "s*".
Разрешено использовать подстановочные знаки.

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

Указывает имя переменной, которую нужно очистить.
Разрешено использовать подстановочные знаки.
Этот параметр обязателен, но его имя (Name) можно не указывать.

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

Задает область действия псевдонима.

Допустимые значения для этого параметра:

- Глобальный
- Локальная
- Сценарий

Можно также использовать число относительно текущей области (от 0 до количества областей, где 0 — текущая область, а 1 — ее родителя).
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

### Нет

Нельзя передать объекты в этот командлет с помощью конвейера.

## Выходные данные

### None или System. Management. Automation. PSVariable

При использовании параметра *PassThru* этот командлет создает объект **System. Management. Automation. PSVariable** , представляющий переменную, которая была сброшена.
В противном случае командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

* Чтобы удалить переменную вместе со значением, используйте командлеты Remove-Variable или Remove-Item.

  Этот командлет не удаляет значения переменных, которые установлены как константы или принадлежат системе, даже если используется параметр *Force* .

  Если очищаемой переменной не существует, этот командлет не выполняет никаких действий.
Он не создает переменную со значением NULL.

  Можно также ссылаться на **clear-variable** по встроенному псевдониму CLV.
Подробнее см. в разделе "about_Aliases".

*

## Связанные ссылки

[Get-Variable](Get-Variable.md)

[New-Variable](New-Variable.md)

[Remove-Variable](Remove-Variable.md)

[Set-Variable](Set-Variable.md)
