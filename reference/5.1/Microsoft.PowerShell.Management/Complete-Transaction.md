---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/complete-transaction?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Complete-Transaction
ms.openlocfilehash: 20fbdd86aab07dda065492eff2da4f358fb2ffca
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228442"
---
# Complete-Transaction

## Краткий обзор
Фиксирует активную транзакцию.

## SYNTAX

```
Complete-Transaction [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Командлет **Complete-Transaction** фиксирует активную транзакцию.
При фиксации активной транзакции ее команды завершаются, а данные, которые затрагиваются ими, изменяются.

Если транзакция содержит несколько подписчиков, для фиксации транзакции необходимо ввести одну команду **завершения транзакции** для каждой команды Start-Transaction.

Командлет **Complete-Transaction** является одним из набора командлетов, поддерживающих функцию Transactions в Windows PowerShell.
Дополнительные сведения см. в разделе about_Transactions.

## Примеры

### Пример 1. Фиксация транзакции

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item MyCompany -UseTransaction
PS HKCU:\software> dir m*
Hive: HKEY_CURRENT_USER\software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}

PS HKCU:\software> Complete-Transaction
PS HKCU:\software> dir m*
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}
0   0 MyCompany                      {}
```

В этом примере показано, что происходит при использовании командлета **Complete-Transaction** для фиксации транзакции.

Команда **Start-Transaction** запускает транзакцию.
Команда New-Item использует параметр *UseTransaction* для включения команды в транзакцию.

Первая команда dir (Get-ChildItem) показывает, что новый элемент еще не добавлен в реестр.

Команда **Complete-Transaction** фиксирует транзакцию, что делает изменение в реестре эффективным.
В результате вторая команда dir показывает, что реестр изменился.

### Пример 2. Фиксация транзакции, имеющей более одного подписчика

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item MyCompany -UseTransaction
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
0   0 MyCompany                      {}

PS HKCU:\software> Start-Transaction
PS HKCU:\Software> Get-Transaction

RollbackPreference   SubscriberCount  Status
------------------   ---------------  ------
Error                2                Active

PS HKCU:\software> New-ItemProperty -Path MyCompany -Name MyKey -Value -UseTransaction

MyKey
-----
123

PS HKCU:\software> Complete-Transaction
PS HKCU:\software> Get-Transaction

RollbackPreference   SubscriberCount  Status
------------------   ---------------  ------
Error                1                Active

PS HKCU:\software> dir m*
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}

PS HKCU:\software> Complete-Transaction
PS HKCU:\software> dir m*
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}
0   1 MyCompany                      {MyKey}
```

В этом примере показано, как использовать **полную транзакцию** для фиксации транзакции, имеющей более одного подписчика.

Чтобы зафиксировать транзакцию с несколькими подписчиками, необходимо ввести одну команду **завершения транзакции** для каждой команды **Start-Transaction** .
Данные изменяются только после отправки последней команды **завершения транзакции** .

Для демонстрации в этом примере показана последовательность команд, введенных в командной строке.
На практике транзакции чаще выполняются в рамках сценариев, причем дополнительная транзакция выполняется функцией или вспомогательным сценарием, вызываемым основным сценарием.

В этом примере команда **Start-Transaction** запускает транзакцию.
Команда **New-Item** с параметром *UseTransaction* добавляет ключ MyCompany в ключ программного обеспечения.
Хотя командлет **New-Item** возвращает ключевой объект, данные в реестре еще не изменялись.

Вторая команда **Start-Transaction** добавляет второй подписчик в существующую транзакцию.
Командлет **Get-Transaction** подтверждает, что число подписчиков равно 2.
Команда New-ItemProperty с параметром *UseTransaction* добавляет запись реестра в новый ключ MyCompany.
И в этом случае команда возвращает значение, но реестр не изменен.

Первая команда **Complete-Transaction** сокращает число подписчиков на 1.
Это подтверждается командой **Get-Transaction** .
Однако данные не изменяются, как свидетельствует команда dir m * ( **Get-ChildItem** ).

Вторая команда **Complete-Transaction** фиксирует всю транзакцию и изменяет данные в реестре.
Это подтверждается второй командой dir m *, которая показывает изменения.

### Пример 3. выполнение транзакции, которая не изменяет данные

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item MyCompany -UseTransaction
PS HKCU:\software> dir m*
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}

PS HKCU:\software> dir m* -UseTransaction
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}
0   0 MyCompany                      {}

PS HKCU:\software> Complete-Transaction
```

В этом примере показано значение с помощью Get- \* Commands и других команд, которые не изменяют данные в транзакции.
Если \* в транзакции используется команда Get-Command, она получает объекты, которые являются частью транзакции.
Это позволяет предварительно просматривать изменения в транзакции перед их фиксацией.

В этом примере запускается транзакция.
Команда New-Item с параметром *UseTransaction* добавляет новый раздел в реестр как часть транзакции.

Поскольку новый раздел реестра не добавляется в реестр до тех пор, пока не будет запущена команда **Complete-Transaction** , в простой команде dir ( **Get-ChildItem** ) будет показан реестр без нового ключа.

Однако при добавлении параметра *UseTransaction* в команду dir команда становится частью транзакции и получает элементы в транзакции, даже если они еще не добавлены в данные.

## PARAMETERS

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

### Нет
Этот командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

* Зафиксированную транзакцию нельзя откатить, а транзакцию, для которой выполнен откат, — зафиксировать.

  Нельзя выполнить откат транзакции, которая не является активной.
Чтобы откатить другую транзакцию, сначала нужно зафиксировать или откатить активную транзакцию.

  По умолчанию, если какая-либо часть транзакции не может быть зафиксирована, например, если команда транзакции завершается ошибкой, откатывается вся транзакция.

*

## Связанные ссылки

[Get-Transaction](Get-Transaction.md)

[Start-Transaction](Start-Transaction.md)

[Undo-Transaction](Undo-Transaction.md)

[Use-Transaction](Use-Transaction.md)

[Get-ChildItem](Get-ChildItem.md)

[New-Item](New-Item.md)

[New-ItemProperty](New-ItemProperty.md)
