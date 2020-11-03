---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
ms.date: 09/07/2018
Module Name: Microsoft.PowerShell.Core
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/functions/get-verb?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Verb
ms.openlocfilehash: 4474bb50c2bf3be10e72d2554190208e956f9040
ms.sourcegitcommit: 7d052985c20761fdf4c6d7ce4e04df4c551c36a3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/11/2020
ms.locfileid: "93230413"
---
# Get-Verb

## Краткий обзор
Получает утвержденные команды PowerShell.

## SYNTAX

```
Get-Verb [[-verb] <String[]>] [<CommonParameters>]
```

## DESCRIPTION

`Get-Verb`Функция возвращает команды, которые утверждены для использования в командах PowerShell.

PowerShell рекомендует имена командлетов и функций в формате Verb-Noun и включают утвержденную команду. Такой подход делает имена команд более единообразными, прогнозируемыми и простыми в использовании.

Команды, использующие неутвержденные команды, выполняются в PowerShell. Однако при импорте модуля, который содержит команду с неодобренным глаголом, в имени `Import-Module` команды отображается предупреждающее сообщение.

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
Verb                 Group
----                 -----
Undo                 Common
Unlock               Common
Unpublish            Data
Uninstall            Lifecycle
Unregister           Lifecycle
Unblock              Security
Unprotect            Security
```

### Пример 3. получение всех утвержденных команд в группе безопасности

```powershell
Get-Verb | Where-Object Group -EQ Security
```

```Output
Verb      Group
----      -----
Block     Security
Grant     Security
Protect   Security
Revoke    Security
Unblock   Security
Unprotect Security
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

### -verb

Возвращает только указанные глаголы.
Введите имя глагола или шаблон имени.
Знаки подстановки разрешены.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: All verbs
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

## Входные данные

### Нет

## Выходные данные

### Selected.Microsoft.PowerShell.Commands.MemberDefinition

## ПРИМЕЧАНИЯ

`Get-Verb` Возвращает измененную версию объекта Microsoft. PowerShell. Commands. MemberDefinition.
Объект не имеет стандартных свойств объекта MemberDefinition. У него есть свойства Verb и Group. Свойство Verb содержит строку с наименованием глагола. Свойство Group содержит строку с группой глаголов.

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

[Import-Module](import-module.md)
