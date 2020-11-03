---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/start-transaction?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Transaction
ms.openlocfilehash: 53be131f45f15e5d2053b183040dc7b3dca4a14c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227861"
---
# Start-Transaction

## Краткий обзор
Запускает транзакцию.

## SYNTAX

```
Start-Transaction [-Timeout <Int32>] [-Independent] [-RollbackPreference <RollbackSeverity>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Командлет **Start-Transaction** запускает транзакцию, которая представляет собой последовательность команд, управляемых как единое целое.
Транзакция может быть выполнена или зафиксирована.
Кроме того, его можно полностью отменить или откатить, чтобы любые данные, измененные транзакцией, восстанавливались в исходное состояние.
Так как команды транзакции управляются как единое целое, фиксируются или откатываются все команды.

По умолчанию, если любая команда в транзакции создает ошибку, автоматически выполняется откат транзакций.
Для изменения этого поведения можно использовать параметр *RollbackPreference* .

Командлеты, используемые в транзакции, должны поддерживать такую возможность.
Командлеты, которые поддерживают транзакции, имеют параметр *UseTransaction* .
Для выполнения транзакций в поставщике поставщик должен поддерживать транзакции.
Поставщик реестра Windows PowerShell в Windows Vista и более поздних версиях операционной системы Windows поддерживает транзакции.
Можно также использовать класс **Microsoft. PowerShell. Commands. Management. TransactedString** для включения выражений в транзакции в любой версии системы Windows, которая поддерживает Windows PowerShell.
Другие поставщики Windows PowerShell также могут поддерживать транзакции.

Одновременно может быть активна только одна транзакция.
При запуске новой, независимой транзакции во время выполнения транзакции новая транзакция становится активной транзакцией, и перед внесением изменений в исходную транзакцию необходимо зафиксировать или откатить новую транзакцию.

Командлет **Start-Transaction** — это один из набора командлетов, поддерживающих функцию Transactions в Windows PowerShell.
Дополнительные сведения см. в разделе about_Transactions.

## Примеры

### Пример 1. Запуск и откат транзакции

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item "ContosoCompany" -UseTransaction
PS HKCU:\software> New-ItemProperty "ContosoCompany" -Name "MyKey" -Value 123 -UseTransaction
PS HKCU:\software> Undo-Transaction
```

Эти команды запускают, а затем откатывают транзакцию.
Так как транзакция откатывается, изменения в реестр не вносятся.

### Пример 2. Запуск и завершение транзакции

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item "ContosoCompany" -UseTransaction
PS HKCU:\software> New-ItemProperty "ContosoCompany" -Name "MyKey" -Value 123 -UseTransaction
PS HKCU:\software> Complete-Transaction
```

Эти команды запускают, а затем завершают транзакцию.
В реестр не вносятся изменения, пока не будет использована команда **Complete-Transaction** .

### Пример 3. Использование различных настроек отката

```
PS C:\> cd HKCU:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item -Path "NoPath" -Name "ContosoCompany" -UseTransaction
PS HKCU:\software> New-Item -Path . -Name "ContosoCompany" -UseTransaction
PS HKCU:\software> Start-Transaction -RollbackPreference never
PS HKCU:\software> New-Item -Path "NoPath" -Name "ContosoCompany" -UseTransaction
PS HKCU:\software> New-Item -Path . -Name "ContosoCompany" -UseTransaction

# Start-Transaction (-rollbackpreference error)

PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item -Path "NoPath" -Name "ContosoCompany" -UseTransaction
New-Item : The registry key at the specified path does not exist.
At line:1 char:9
+ new-item <<<<  -Path NoPath -Name ContosoCompany -UseTransaction

PS HKCU:\software> New-Item -Path . -Name "Contoso" -UseTransaction

New-Item : Cannot use transaction. The transaction has been rolled back or has timed out.
At line:1 char:9
+ new-item <<<<  -Path . -Name ContosoCompany -UseTransaction

# Start-Transaction (-rollbackpreference never)

PS HKCU:\software> Start-Transaction -RollbackPreference never
PS HKCU:\software> New-Item -Path "NoPath" -Name "ContosoCompany" -UseTransaction

New-Item : The registry key at the specified path does not exist.
At line:1 char:9
+ new-item <<<<  -Path NoPath -Name "ContosoCompany" -UseTransaction
PS HKCU:\software> New-Item -Path . -Name "ContosoCompany" -UseTransaction

Hive: HKEY_CURRENT_USER\Software
SKC  VC Name                           Property
---  -- ----                           --------
0   0 ContosoCompany                 {}
PS HKCU:\Software> Complete-Transaction

# Succeeds
```

В этом примере демонстрируется результат изменения значения параметра *RollbackPreference* .

В первом наборе команд **Start-Transaction** не использует *RollbackPreference* .
В результате используется значение по умолчанию (Error).
При возникновении ошибки в команде транзакции, то есть указанный путь не существует, транзакция автоматически откатывается.

Во втором наборе команд **Start-Transaction** использует *RollbackPreference* со значением Never.
Поэтому, когда в команде транзакции происходит ошибка, транзакция остается активной и ее можно успешно завершить.

Так как большинство транзакций должно выполняться без ошибок, обычно рекомендуется использовать значение по умолчанию *RollbackPreference* .

### Пример 4. Использование этого командлета во время выполнения транзакции

```
PS C:\> cd HKCU:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item "ContosoCompany" -UseTransaction
PS HKCU:\software> Start-Transaction
PS HKCU:\software> Get-Transaction
PS HKCU:\software> New-Item "ContosoCompany2" -UseTransaction
PS HKCU:\software> Complete-Transaction
PS HKCU:\software> Complete-Transaction
PS HKCU:\Software> Get-Transaction
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                2                 Active
```

В этом примере показан результат использования команды **Start-Transaction** во время выполнения транзакции.
Он во многом похож на присоединение к выполняющейся транзакции.

Хотя это упрощенная команда, этот сценарий часто возникает, когда транзакция включает в себя выполнение скрипта, включающего полную транзакцию.

Первая команда **Start-Transaction** запускает транзакцию.
Первая команда **New-Item** является частью транзакции.

Вторая команда **Start-Transaction** добавляет нового подписчика в транзакцию.
Команда **Get-Transaction** теперь возвращает транзакцию с числом подписчиков, равным 2.
Вторая команда **New-Item** является частью той же транзакции.

В реестр не вносятся изменения, пока не завершится вся транзакция.
Чтобы завершить транзакцию, необходимо ввести две команды **полных транзакций** — по одной для каждого подписчика.
Если вы намерены откатить транзакцию в любой момент, для обоих подписчиков будет выполнен откат всей транзакции.

### Пример 5. Запуск независимой транзакции во время ее выполнения

```
PS C:\> cd HKCU:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item "ContosoCompany" -UseTransaction
PS HKCU:\software> Start-Transaction -Independent
PS HKCU:\software> Get-Transaction
PS HKCU:\software> Undo-Transaction
PS HKCU:\software> New-ItemProperty -Path "ContosoCompany" -Name "MyKey" -Value 123 -UseTransaction
PS HKCU:\software> Complete-Transaction
PS HKCU:\software> dir contoso*
PS HKCU:\Software> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
PS HKCU:\software> Undo-Transaction
PS HKCU:\software> New-ItemProperty -Path "ContosoCompany" -Name "MyKey" -Value 123 -UseTransaction
MyKey
-----
123
PS HKCU:\software> Complete-Transaction
PS HKCU:\software> dir contoso*
Hive: HKEY_CURRENT_USER\Software
SKC  VC Name                           Property
---  -- ----                           --------
0   1 MyCompany                      {MyKey}
```

В этом примере показан результат использования *независимого* параметра командлета **Start-Transaction** для запуска транзакции во время выполнения другой транзакции.
В этом случае новая транзакция откатывается, не затрагивая исходной транзакции.

Хотя транзакции логически не зависят друг от друга, одновременно может быть активна только одна транзакция, поэтому более позднюю транзакцию нужно откатить или зафиксировать, прежде чем возобновлять работу с исходной.

Первый набор команд запускает транзакцию.
Команда **New-Item** является частью первой транзакции.

Во втором наборе команд Команда **Start-Transaction** использует *независимый* параметр.
Приведенная ниже команда **Get-Transaction** показывает объект транзакции для активной транзакции, которая является самой новой.
Число подписчиков равно 1, что указывает, что транзакции не связаны.

При откате активной транзакции с помощью команды **отмены транзакции** исходная транзакция снова становится активной.

Команда **New-ItemProperty** , которая является частью исходной транзакции, завершается без ошибок, а исходная транзакция может быть выполнена с помощью команды **Complete-Transaction** .
В результате реестр изменяется.

### Пример 6. выполнение команд, не входящих в транзакцию

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item "ContosoCompany1" -UseTransaction
PS HKCU:\software> New-Item "ContosoCompany2"
PS HKCU:\software> New-Item "ContosoCompany3" -UseTransaction
PS HKCU:\software> dir contoso*
PS HKCU:\software> Complete-Transaction
PS HKCU:\software> dir contoso*
PS HKCU:\Software> dir contoso*

Hive: HKEY_CURRENT_USER\Software
SKC  VC Name                           Property
---  -- ----                           --------
0   0 ContosoCompany2                {}

PS HKCU:\Software> Complete-Transaction
PS HKCU:\Software> dir contoso*

Hive: HKEY_CURRENT_USER\Software
SKC  VC Name                           Property
---  -- ----                           --------
0   0 ContosoCompany1                     {}
0   0 ContosoCompany2                     {}
0   0 ContosoCompany3                     {}
```

Этот пример демонстрирует, что команды, переданные во время выполнения транзакции, могут включаться в транзакцию или не включаться.
Только команды, использующие параметр *UseTransaction* , являются частью транзакции.

В первой и третьей командах **нового элемента** используется параметр *UseTransaction* .
Эти команды входят в транзакцию.
Так как Вторая команда **New-Item** не использует параметр *UseTransaction* , она не является частью транзакции.

Первая команда dir отображает результат.
Вторая команда **New-Item** выполняется немедленно, но первая и третья команды **нового элемента** не вступают в силу до тех пор, пока не будет выполнена фиксация транзакции.

Команда **Complete-Transaction** фиксирует транзакцию.
В результате вторая команда dir показывает, что все новые элементы добавляются в реестр.

### Пример 7. откат транзакции, которая не завершается в указанное время

```
PS C:\> Start-Transaction -Timeout 2

# Wait two minutes...

PS C:\> Get-Transaction
PS C:\> New-Item HKCU:\Software\ContosoCompany -UseTransaction
PS C:\> Start-Transaction -Timeout 2

# Wait two minutes...

PS C:\> > Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   -----------
Error                1                 RolledBack

PS C:\> New-Item HKCU:\Software\ContosoCompany -UseTransaction

New-Item : Cannot use transaction. The transaction has been rolled back or has timed out.
At line:1 char:9
+ new-item <<<<  MyCompany -UseTransaction
```

Эта команда использует параметр *timeout* командлета **Start-Transaction** для запуска транзакции, которая должна быть выполнена в течение двух минут.
Если транзакция не завершена по истечении времени ожидания, она автоматически откатывается.

По истечении времени ожидания вы не получаете уведомления, но свойство **Status** объекта Transaction имеет значение откат и команды, использующие параметр *UseTransaction* , завершаются ошибкой.

## PARAMETERS

### Не зависит от
Указывает, что этот командлет запускает транзакцию, которая не зависит от выполняемых транзакций.
По умолчанию, если используется **Start-Transaction** во время выполнения другой транзакции, в выполняемую транзакцию добавляется новый подписчик.
Этот параметр действует только в том случае, если в рамках сеанса уже выполняется транзакция.

По умолчанию, если при выполнении транзакции используется **Start-Transaction** , существующий объект транзакции повторно используется и число подписчиков увеличивается.
Результат во многом похож на присоединение к исходной транзакции.
Команда Undo-Transaction выполняет откат всей транзакции.
Чтобы завершить транзакцию, необходимо выполнить команду Complete-Transaction для каждого подписчика.
Так как обычно одновременно выполняющиеся транзакции связаны, значения по умолчанию в большинстве случаев достаточно.

Если указан *независимый* параметр, этот командлет создает новую транзакцию, которая может быть завершена или отменена без влияния на исходную транзакцию.
Однако, поскольку одновременно может быть активна только одна транзакция, новую транзакцию необходимо завершить или откатить, прежде чем возобновлять работу с исходной транзакцией.

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

### -RollbackPreference
Указывает условия, при которых транзакция автоматически откатывается.
Допустимые значения для этого параметра:

- Ошибка.
транзакция откатывается автоматически, если происходит устранимая или неустранимая ошибка.
- Терминатинжеррор.
транзакция откатывается автоматически, если происходит неустранимая ошибка.
- Никогда.
транзакция никогда не откатывается автоматически.

Значение по умолчанию — Error.

```yaml
Type: System.Management.Automation.RollbackSeverity
Parameter Sets: (All)
Aliases:
Accepted values: Error, TerminatingError, Never

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Timeout
Указывает максимальный период времени в минутах, в течение которого транзакция может быть активна.
По истечении времени ожидания транзакция откатывается автоматически.

По умолчанию для транзакций, запускаемых из командной строки, время ожидания не устанавливается.
Если транзакции запускаются с помощью сценария, время ожидания по умолчанию — 30 минут.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: TimeoutMins

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
В этот командлет нельзя передать входные данные.

## Выходные данные

### Нет
Этот командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Complete-Transaction](Complete-Transaction.md)

[Get-Transaction](Get-Transaction.md)

[Undo-Transaction](Undo-Transaction.md)

[Use-Transaction](Use-Transaction.md)
