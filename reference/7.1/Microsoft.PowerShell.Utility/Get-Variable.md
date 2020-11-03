---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 5/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-variable?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Variable
ms.openlocfilehash: f544a33a4d2aa2cabd330ce7cc30c5270eeff897
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227169"
---
# Get-Variable

## Краткий обзор
Получает переменные в текущей консоли.

## SYNTAX

```
Get-Variable [[-Name] <String[]>] [-ValueOnly] [-Include <String[]>] [-Exclude <String[]>] [-Scope <String>]
 [<CommonParameters>]
```

## DESCRIPTION

`Get-Variable`Командлет получает переменные PowerShell в текущей консоли.
Вы можете получить только значения переменных, указав параметр **ValueOnly** , и отфильтровать полученные переменные по имени.

## Примеры

### Пример 1. получение переменных по буквам

Эта команда получает переменные с именами, начинающимися с буквы m.
Она также возвращает значения переменных.

```powershell
Get-Variable m*
```

### Пример 2. Получение значений переменных по буквам

Эта команда возвращает только значения переменных, имена которых начинаются с m.

```powershell
Get-Variable m* -ValueOnly
```

### Пример 3. получение переменных по двум буквам

Эта команда возвращает сведения о переменных, которые начинаются с буквы M или буквы P.

```powershell
Get-Variable -Include M*,P*
```

### Пример 4. получение переменных по области

Первая команда возвращает только те переменные, которые определены в локальной области.
Оно эквивалентно `Get-Variable -Scope Local` и может быть сокращено до `gv -s 0` .

Вторая команда использует `Compare-Object` командлет для поиска переменных, определенных в родительской области (область 1), но видимых только в локальной области (область 0).

```powershell
Get-Variable -Scope 0
Compare-Object (Get-Variable -Scope 0) (Get-Variable -Scope 1)
```

## PARAMETERS

### -Exclude

Указывает массив элементов, которые этот командлет исключает из операции.
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

### -Include

Указывает массив элементов, на основании которых будет действовать командлет, исключая все остальные.
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

Указывает имя переменной.
Разрешено использовать подстановочные знаки.
Можно также передать имя переменной по конвейеру в `Get-Variable` .

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -Scope

Задает переменные в области. Допустимые значения для этого параметра:

- **Глобальный**
- **Локальное**
- **Сценарий**
- Номер относительно текущей области (от 0 до количества областей, где 0 — это текущая область, а 1 — ее родительская область).

По умолчанию используется **Local** .
Дополнительные сведения см. в разделе [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).

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

### -Валуеонли

Указывает, что этот командлет возвращает только значение переменной.

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

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## Входные данные

### System.String

Строку, содержащую имя переменной, можно передать в `Get-Variable` .

## Выходные данные

### System. Management. Automation. PSVariable

Этот командлет возвращает объект **System. Management. аутоматионпсвариабле** для каждой переменной, которую она получает. Тип объекта зависит от переменной.

### System. Object []

При указании параметра **валуеонли** , если значение указанной переменной является коллекцией, `Get-Variable` возвращает `[System.Object[]]` . Это поведение предотвращает обработку значений переменных в обычной операции конвейера по одной за раз. Обходной путь для принудительного перечисления коллекций заключается в заключении `Get-Variable` команды в круглые скобки.

## ПРИМЕЧАНИЯ

- Этот командлет не управляет переменными среды. Для управления этими переменными можно использовать поставщика переменных среды.

## Связанные ссылки

[Clear-Variable](Clear-Variable.md)

[New-Variable](New-Variable.md)

[Remove-Variable](Remove-Variable.md)

[Set-Variable](Set-Variable.md)

