---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-alias?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Alias
ms.openlocfilehash: e0a08a4ee6f00702f765bc359a20bf9e30b9b1c5
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227218"
---
# Get-Alias

## Краткий обзор
Получает псевдонимы, действительные в ходе текущего сеанса.

## SYNTAX

### Default (по умолчанию)

```
Get-Alias [[-Name] <String[]>] [-Exclude <String[]>] [-Scope <String>] [<CommonParameters>]
```

### Определение

```
Get-Alias [-Exclude <String[]>] [-Scope <String>] [-Definition <String[]>] [<CommonParameters>]
```

## DESCRIPTION

Командлет **Get-Alias** получает псевдонимы в текущем сеансе.
Сюда входят встроенные псевдонимы, псевдонимы, которые вы установили или импортировали, и псевдонимы, добавленные в профиль PowerShell.

По умолчанию командлет **Get-Alias** принимает псевдоним и возвращает имя команды.
При использовании параметра *определения* командлет **Get-Alias** принимает имя команды и возвращает его псевдонимы.

Начиная с Windows PowerShell 3,0, **Get-Alias** отображает имена псевдонимов без дефисов в `<alias> -> <definition>` формате, чтобы упростить поиск нужных сведений.

## Примеры

### Пример 1. Получение всех псевдонимов в текущем сеансе

```
PS C:\> Get-Alias

CommandType     Name
-----------     ----
Alias           % -> ForEach-Object
Alias           ? -> Where-Object
Alias           ac -> Add-Content
Alias           asnp -> Add-PSSnapin
Alias           cat -> Get-Content
Alias           cd -> Set-Location
Alias           chdir -> Set-Location
Alias           clc -> Clear-Content
Alias           clear -> Clear-Host
Alias           clhy -> Clear-History
...
```

Эта команда получает все псевдонимы в текущем сеансе.

В выходных данных показан `<alias> -> <definition>` Формат, представленный в Windows PowerShell 3,0.
Этот формат используется только для псевдонимов, не содержащих дефисы, поскольку вместо названий командлетов и функций предпочтительнее использовать псевдонимы с дефисами.

### Пример 2. Получение псевдонимов по имени

```powershell
Get-Alias -Name gp*, sp* -Exclude *ps
```

Эта команда возвращает все псевдонимы, которые начинаются с GP или SP, за исключением псевдонимов, которые заканчиваются на PS.

### Пример 3. Получение псевдонимов для командлета

```powershell
Get-Alias -Definition Get-ChildItem
```

Эта команда получает псевдонимы для командлета Get-ChildItem.

По умолчанию командлет **Get-Alias** получает имя элемента, если известно его псевдоним.
Параметр *определения* получает псевдоним, если известно имя элемента.

### Пример 4. Получение псевдонимов по свойству

```powershell
Get-Alias | Where-Object {$_.Options -Match "ReadOnly"}
```

Эта команда получает все псевдонимы, в которых свойство Options имеет значение ReadOnly.
Эта команда позволяет быстро найти псевдонимы, встроенные в PowerShell, так как они имеют параметр ReadOnly.

Параметры — это только одно свойство объектов AliasInfo, которое получает **Get-Alias** .
Чтобы найти все свойства и методы объектов AliasInfo, введите команду `Get-Alias | get-member`.

### Пример 5. Получение псевдонимов по имени и фильтрование по первой букве

```powershell
Get-Alias -Definition "*-PSSession" -Exclude e* -Scope Global
```

Этот пример получает псевдонимы команд, имена которых заканчиваются на "-PSSession", кроме команд, начинающихся на букву "e".

Команда использует параметр *Scope* для применения команды в глобальной области.
Эта функция пригодится в скриптах, где необходимо получить псевдонимы, действительные в сеансе.

## PARAMETERS

### -Definition

Получает псевдонимы для заданного элемента.
Введите имя командлета, функции, скрипта, файла или исполняемого файла.

Этот параметр называется *определением* , так как он ищет имя элемента в свойстве Definition объекта псевдонима.

```yaml
Type: System.String[]
Parameter Sets: Definition
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Exclude

Исключает указанные элементы.
Значение этого параметра определяет значение параметров Name и Definition.
Введите имя, определение или шаблон, например, "s *".
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

Задает получаемые этим командлетом псевдонимы.
Разрешено использовать подстановочные знаки.
По умолчанию `Get-Alias` получает все псевдонимы, определенные для текущего сеанса.
**Имя параметра является** необязательным.
Имена псевдонимов можно также передавать в `Get-Alias` .

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases:

Required: False
Position: 0
Default value: All aliases
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -Scope

Задает область, псевдонимы для которой получает этот командлет.
Допустимые значения для этого параметра:

- Глобальный
- Локальная
- Сценарий
- Номер относительно текущей области (от 0 до количества областей, где 0 — это текущая область, а 1 — ее родительская область).

По умолчанию используется значение Local.
Дополнительные сведения см. в разделе about_Scopes.

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

### System.String

Имена псевдонимов можно передавать в командлет **Get-Alias**.

## Выходные данные

### System.Management.Automation.AliasInfo

Командлет **Get-Alias** возвращает объект, представляющий каждый псевдоним.
Командлет **Get-Alias** возвращает один и тот же объект для каждого псевдонима, но PowerShell использует формат на основе стрелок для вывода имен псевдонимов, отличных от дефисов.

## ПРИМЕЧАНИЯ

- Для создания нового псевдонима используйте командлет Set-Alias или New-Alias. Для удаления псевдонима используйте командлет Remove-Item.
- Формат имени псевдонима со стрелками не используется для псевдонимов, содержащих дефис. Для замены названий командлетов и функций такие псевдонимы более предпочтительны, чем обычные псевдонимы и сокращения.

## Связанные ссылки

[Export-Alias](Export-Alias.md)

[Import-Alias](Import-Alias.md)

[New-Alias](New-Alias.md)

[Set-Alias](Set-Alias.md)

[Alias Provider](../Microsoft.PowerShell.Core/About/about_Alias_Provider.md)

[about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)

