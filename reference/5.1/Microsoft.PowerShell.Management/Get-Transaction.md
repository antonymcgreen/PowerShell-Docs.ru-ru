---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-transaction?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Transaction
ms.openlocfilehash: bb8e9e1f204c67207f31613181f856d3bcaf8dc3
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "93209025"
---
# Get-Transaction

## Краткий обзор
Получает текущую (активную) транзакцию.

## SYNTAX

```
Get-Transaction [<CommonParameters>]
```

## DESCRIPTION
Командлет **Get-Transaction** возвращает объект, представляющий текущую транзакцию в сеансе.

Он никогда не возвращает более одного объекта, так как одновременно активна только одна транзакция.
При запуске одной или нескольких независимых транзакций (с помощью независимого параметра Start-Transaction) активная транзакция становится активной и это транзакция, возвращаемая командлетом **Get-Transaction** .

При откате или фиксации всех активных транзакций этот командлет показывает транзакцию, которая была недавно активна в сеансе.

Этот командлет является одним из набора командлетов, поддерживающих функцию Transactions в Windows PowerShell.
Дополнительные сведения см. в разделе about_Transactions.

## Примеры

### Пример 1. Получение текущей транзакции

```
PS C:\> Start-Transaction
PS C:\> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

Командлет Get-Transaction применяется для получения текущей транзакции.

### Пример 2. Отображение свойств и методов объекта Transaction

```
PS C:\> Get-Transaction | Get-Member

Name               MemberType Definition
----               ---------- ----------
Dispose            Method     System.Void Dispose(), System.Void Dispose(Boolean disposing)
Equals             Method     System.Boolean Equals(Object obj)
GetHashCode        Method     System.Int32 GetHashCode()
GetType            Method     System.Type GetType()
ToString           Method     System.String ToString()
IsCommitted        Property   System.Boolean IsCommitted {get;}
IsRolledBack       Property   System.Boolean IsRolledBack {get;}
RollbackPreference Property   System.Management.Automation.RollbackSeverity RollbackPreference {get;}
SubscriberCount    Property   System.Int32 SubscriberCount {get;set;}
```

Эта команда использует командлет Get-Member для отображения свойств и методов объекта транзакции.

### Пример 3. Отображение значений свойств для выполненной отката транзакции

```
PS C:\> cd hklm:\software
HKLM:\SOFTWARE> Start-Transaction
HKLM:\SOFTWARE> New-Item MyCompany -UseTransaction
HKLM:\SOFTWARE> Undo-Transaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ----------
Error                0                 RolledBack
```

Эта команда показывает значения свойств объекта транзакции, для которой был выполнен откат.

### Пример 4. Отображение значений свойств зафиксированной транзакции

```
PS C:\> cd hklm:\software
HKLM:\SOFTWARE> Start-Transaction
HKLM:\SOFTWARE> New-Item MyCompany -UseTransaction
HKLM:\SOFTWARE> Complete-Transaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ---------
Error                1                 Committed
```

Эта команда показывает значения свойств объекта транзакции, которая была зафиксирована.

### Пример 5. запуск транзакции во время выполнения другого

```
PS C:\> cd hklm:\software
HKLM:\SOFTWARE> Start-Transaction
HKLM:\SOFTWARE> New-Item MyCompany -UseTransaction
HKLM:\SOFTWARE> Start-Transaction
HKLM:\SOFTWARE> New-Item MyCompany2 -UseTransaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                2                 Active

HKLM:\SOFTWARE> Complete-Transaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active

HKLM:\SOFTWARE> Complete-Transaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ---------
Error                1                 Committed
```

В этом примере показано, как запуск транзакции влияет на объект транзакции во время выполнения другой транзакции.
Как правило, это происходит, когда скрипт, выполняющий транзакцию, включает в себя функцию или вызывает скрипт, который содержит другую транзакцию.

Если вторая команда **Start-Transaction** не содержит *независимый* параметр, командлет **Start-Transaction** не создает новую транзакцию.
Вместо этого командлет добавляет второго подписчика к исходной транзакции.

Первая команда **Start-Transaction** запускает транзакцию.
Команда New-Item с параметром *UseTransaction* является частью транзакции.

Вторая команда **Start-Transaction** добавляет подписчика в транзакцию.
Следующая команда New-Item также является частью транзакции.

Первая команда **Get-Transaction** показывает транзакцию с несколькими подписчиками.
Обратите внимание, что число подписчиков — 2.

Первая команда Complete-Transaction не фиксируют транзакцию, но оно уменьшает число подписчиков до 1.

Вторая команда **Complete-Transaction** фиксирует транзакцию.

### Пример 6. Запуск независимой транзакции во время выполнения другого

```
PS C:\>
HKLM:\SOFTWARE> Start-Transaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   IsRolledBack   IsCommitted
------------------   ---------------   ------------   -----------
Error                1                 False          False

HKLM:\SOFTWARE> Start-Transaction -Independent
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   IsRolledBack   IsCommitted
------------------   ---------------   ------------   -----------
Error                1                 False          False

HKLM:\SOFTWARE> Complete-Transaction
HKLM:\SOFTWARE> Get-Transaction
HKLM:\SOFTWARE> Complete-Transaction
HKLM:\SOFTWARE> Get-Transaction
```

В этом примере показано, как запуск независимой транзакции влияет на объект транзакции во время выполнения другой транзакции.

Первая команда **Start-Transaction** запускает транзакцию.
Команда **нового элемента** с параметром *UseTransaction* является частью транзакции.

Вторая команда **Start-Transaction** добавляет подписчика в транзакцию.
Следующая команда **New-Item** также является частью транзакции.

Первая команда **Get-Transaction** показывает транзакцию с несколькими подписчиками.
Обратите внимание, что число подписчиков — 2.

Команда **Complete-Transaction** сокращает число подписчиков до 1, но не фиксирует транзакцию.

Вторая команда **Complete-Transaction** фиксирует транзакцию.

## PARAMETERS

### Общие параметры
Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет
Нельзя передать объекты в этот командлет с помощью конвейера.

## Выходные данные

### System. Management. Automation. Пстрансактион
Этот командлет возвращает объект, представляющий текущую транзакцию.

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Complete-Transaction](Complete-Transaction.md)

[Start-Transaction](Start-Transaction.md)

[Undo-Transaction](Undo-Transaction.md)

[Use-Transaction](Use-Transaction.md)

[New-Item](New-Item.md)
