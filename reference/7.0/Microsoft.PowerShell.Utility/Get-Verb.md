---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/07/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-verb?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Verb
ms.openlocfilehash: a1459c276d8d6b2d031bc4b4f7ab521f7582a4cb
ms.sourcegitcommit: 7d052985c20761fdf4c6d7ce4e04df4c551c36a3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/11/2020
ms.locfileid: "93230417"
---
# Get-Verb

## Краткий обзор
Получает утвержденные команды PowerShell.

## SYNTAX

```
Get-Verb [[-Verb] <String[]>] [[-Group] <String[]>] [<CommonParameters>]
```

## DESCRIPTION

`Get-Verb`Функция возвращает команды, которые утверждены для использования в командах PowerShell.

Рекомендуется, чтобы имена командлетов и функций PowerShell были в `Verb-Noun` формате и включали утвержденную команду. Такой подход делает имена команд более единообразными, прогнозируемыми и простыми в использовании.

Команды, использующие неутвержденные команды, по-прежнему выполняются в PowerShell. Однако при импорте модуля, который содержит команду с неодобренным глаголом, в имени `Import-Module` команды отображается предупреждающее сообщение.

> [!NOTE]
> Возвращаемый список команд `Get-Verb` может быть неполным. Обновленный список утвержденных команд PowerShell с описаниями см. в разделе [утвержденные команды](../../docs-conceptual/developer/cmdlet/approved-verbs-for-windows-powershell-commands.md) в документация Майкрософт.

## Примеры

### Пример 1. Получение списка всех команд

```powershell
Get-Verb
```

### Пример 2. Получение списка утвержденных команд, начинающихся с "UN"

```powershell
Get-Verb un*
```

```Output
Verb       AliasPrefix Group     Description
----       ----------- -----     -----------
Undo       un          Common    Sets a resource to its previous state
Unlock     uk          Common    Releases a resource that was locked
Unpublish  ub          Data      Makes a resource unavailable to others
Uninstall  us          Lifecycle Removes a resource from an indicated location
Unregister ur          Lifecycle Removes the entry for a resource from a repository
Unblock    ul          Security  Removes restrictions to a resource
Unprotect  up          Security  Removes safeguards from a resource that were added to prevent it from attack or loss
```

### Пример 3. получение всех утвержденных команд в группе безопасности

```powershell
Get-Verb -Group Security
```

```Output
Verb      AliasPrefix Group    Description
----      ----------- -----    -----------
Block     bl          Security Restricts access to a resource
Grant     gr          Security Allows access to a resource
Protect   pt          Security Safeguards a resource from attack or loss
Revoke    rk          Security Specifies an action that does not allow access to a resource
Unblock   ul          Security Removes restrictions to a resource
Unprotect up          Security Removes safeguards from a resource that were added to prevent it from attack or loss
```

### Пример 4. Поиск всех команд в модуле с неутвержденными командами

```powershell
Get-Command -Module Microsoft.PowerShell.Utility | Where-Object Verb -NotIn (Get-Verb).Verb
```

```Output
CommandType     Name            Version    Source
-----------     ----            -------    ------
Cmdlet          Sort-Object     3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Tee-Object      3.1.0.0    Microsoft.PowerShell.Utility
```

## PARAMETERS

### -Verb

Возвращает только указанные глаголы. Введите имя глагола или шаблон имени. Знаки подстановки разрешены.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:
Accepted values: Common, Communications, Data, Diagnostic, Lifecycle, Other, Security

Required: False
Position: 1
Default value: All groups
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -Group

Возвращает только указанные группы. Введите имя группы. Подстановочные знаки не допускаются.

Этот параметр появился в PowerShell 6,0.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: All verbs
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет

## Выходные данные

### System. Management. Automation. Вербинфо

## ПРИМЕЧАНИЯ

Команды PowerShell назначаются группе в соответствии с их наиболее распространенным использованием. Группы предназначены для поиска и сравнения глаголов, а не для ограничения их использования. Утвержденный глагол можно использовать в команде любого типа.

Каждая команда PowerShell назначается одной из следующих групп.

- Общие: Определите общие действия, которые могут применяться практически к любому командлету, например Add.
- Обмен данными: определение действий, которые применяются к обмену данными, например Connect.
- Данные: определяют действия, которые применяются к обработке данных, например резервное копирование.
- Диагностика. определяет действия, которые применяются к диагностике, например Отладка.
- Жизненный цикл. Определите действия, которые применяются к жизненному циклу командлета, например Complete.
- Безопасность: Определите действия, которые применяются к безопасности, например отозвать.
- Другое: определение других типов действий.

Некоторые командлеты, устанавливаемые с помощью PowerShell, такие как `Tee-Object` и `Where-Object` , используют неутвержденные команды. Эти командлеты являются историческими исключениями, а их глаголы классифицируются как **зарезервированные** .

## Связанные ссылки

[Import-Module](../microsoft.powershell.core/import-module.md)
