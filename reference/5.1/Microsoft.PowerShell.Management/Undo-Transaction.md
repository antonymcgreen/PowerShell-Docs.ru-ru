---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/undo-transaction?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Undo-Transaction
ms.openlocfilehash: 1acb06ea7b05a2127b04a22c4c51b92cd68056f2
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227834"
---
# Undo-Transaction

## Краткий обзор
Откатывает активную транзакцию.

## SYNTAX

```
Undo-Transaction [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Командлет **Undo-Transaction** выполняет откат активной транзакции.
При откате транзакции изменения, внесенные командами в транзакции, отбрасываются, а данные восстанавливаются в исходную форму.

Если транзакция включает несколько подписчиков, команда **Undo-Transaction** выполняет откат всей транзакции для всех подписчиков.

По умолчанию откат транзакций выполняется автоматически в случае создания ошибки любой из команд в транзакции.
Однако транзакции могут быть запущены с другим приоритетом отката, и этот командлет можно использовать для отката активной транзакции в любое время.

Командлет **Undo-Transaction** является одним из набора командлетов, поддерживающих функцию Transactions в Windows PowerShell.
Дополнительные сведения см. в разделе about_Transactions.

## Примеры

### Пример 1. откат текущей транзакции

```
PS C:\> Undo-Transaction
```

Эта команда выполняет откат текущей активной транзакции.

### Пример 2. Запуск и откат транзакции

```
PS C:\> cd hkcu:\software
PS HKCU:\Software> Start-Transaction
PS HKCU:\Software> New-Item -Path "ContosoCompany" -UseTransaction
PS HKCU:\Software> Undo-Transaction
```

В этом примере запускается транзакция, а затем выполняется ее откат.
В результате изменения не вносятся в реестр.

### Пример 3. откат транзакции для всех подписчиков

```
PS C:\> cd hkcu:\software
PS HKCU:\Software> Start-Transaction
PS HKCU:\Software> New-Item -Path "ContosoCompany" -UseTransaction
PS HKCU:\Software> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   -----
Error                1                 Active

PS HKCU:\Software> Start-Transaction
PS HKCU:\Software> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   -----
Error                2                 Active

PS HKCU:\Software> Undo-Transaction
PS HKCU:\Software> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   -----
Error                0                 RolledBack
```

В этом примере показано, что когда любой подписчик откатывает транзакцию, выполняется откат всей транзакции для всех подписчиков.

Первая команда изменяет расположение на раздел реестра HKCU:\Software.

Вторая команда запускает транзакцию.

Третья команда использует командлет New-Item для создания нового раздела реестра.
Команда использует параметр *UseTransaction* для включения изменения в транзакцию.

Четвертая команда использует командлет Get-Transaction для получения активной транзакции.
Обратите внимание, что состояние — Active, а число подписчиков — 1.

Пятая команда использует команду Start-Transaction еще раз.
Как правило, запуск транзакции во время выполнения другой транзакции происходит, когда скрипт, используемый основной транзакцией, содержит собственную полную транзакцию.
Этот пример выполняется в интерактивном режиме, чтобы его можно было изучить поэтапно.
При выполнении команды **Start-Transaction** во время выполнения другой транзакции команды присоединяются к существующей транзакции в качестве нового подписчика, а число подписчиков увеличивается.

Шестая команда использует командлет **Get-Transaction** для получения активной транзакции.
Обратите внимание, что число подписчиков теперь 2.

Седьмая команда использует для отката транзакции операцию **отмены-Transaction** .
Этот командлет не возвращает никакие объекты.

Последняя команда — это команда **Get-Transaction** , которая получает активный объект или, в данном случае, последнюю активную транзакцию.
Результаты показывают, что откат транзакции выполнен и число подписчиков равно 0, то есть, откат транзакции был выполнен для всех подписчиков.

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
В этот командлет нельзя передать входные данные.

## Выходные данные

### Нет
Этот командлет не возвращает никакие выходные данные.

## ПРИМЕЧАНИЯ

* Нельзя выполнить откат транзакции, которая была зафиксирована.

  Нельзя выполнить откат транзакции, которая не является активной.
Для отката другой, независимой транзакции необходимо сначала выполнить фиксацию или откат активной транзакции.

  Откат транзакции завершает транзакцию.
Чтобы использовать транзакцию снова, необходимо запустить новую транзакцию.

## Связанные ссылки

[Complete-Transaction](Complete-Transaction.md)

[Get-Transaction](Get-Transaction.md)

[Start-Transaction](Start-Transaction.md)

[Use-Transaction](Use-Transaction.md)
