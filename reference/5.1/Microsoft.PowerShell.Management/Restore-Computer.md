---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restore-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Restore-Computer
ms.openlocfilehash: 824e9a24693c7a7de01358a048a0df55be333263
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227902"
---
# Restore-Computer

## Краткий обзор
Запускает восстановление системы на локальном компьютере.

## SYNTAX

```
Restore-Computer [-RestorePoint] <Int32> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Командлет **Restore-Computer** восстанавливает локальный компьютер до указанной точки восстановления системы.

**Restart-Computer** перезагружает компьютер.
Восстановление завершается при выполнении перезагрузки.

Точки восстановления системы и **Восстановление компьютера** поддерживаются только в клиентских операционных системах, таких как Windows 7, Windows Vista и Windows XP.

## Примеры

### Пример 1. Восстановление локального компьютера

```
PS C:\> Restore-Computer -RestorePoint 253
```

Эта команда восстанавливает локальный компьютер в точке восстановления с порядковым номером 253.

### Пример 2. Восстановление локального компьютера с подтверждением

```
PS C:\> Restore-Computer -RestorePoint 255 -Confirm
Confirm
Are you sure you want to perform this action?
Performing operation "Restore-Computer" .
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

Эта команда восстанавливает локальный компьютер в точке восстановления с порядковым номером 255.
Он использует параметр *Confirm* для запроса пользователя перед фактическим выполнением операции.

### Пример 3. Восстановление компьютера и проверка состояния

```
PS C:\> Get-ComputerRestorePoint
PS C:\> Restore-Computer -RestorePoint 255
PS C:\> Get-ComputerRestorePoint -LastStatus
```

Эти команды выполняют восстановление системы и затем проверяют его результат.

Первая команда использует **Get-ComputerRestorePoint** для получения точек восстановления на локальном компьютере.

Вторая команда восстанавливает компьютер до точки восстановления с порядковым номером 255.

Третья команда использует параметр *LastStatus* командлета *Get-ComputerRestorePoint* для проверки состояния операции восстановления.
Так как **Restart-Computer** принудительно перезапускается, эта команда будет выполнена после перезагрузки компьютера.

## PARAMETERS

### -Ресторепоинт
Задает порядковый номер точки восстановления.
Чтобы найти порядковый номер, используйте командлет Get-ComputerRestorePoint.
Этот параметр обязателен.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: SequenceNumber, SN, RP

Required: True
Position: 0
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

* Чтобы выполнить команду Restore-Computer в Windows Vista и более поздних версиях операционной системы Windows, откройте Windows PowerShell с помощью команды Запуск от имени администратора.
* Этот командлет использует класс инструментарий управления Windows (WMI) (WMI) **SystemRestore** .

## Связанные ссылки

[Checkpoint-Computer](Checkpoint-Computer.md)

[Disable-ComputerRestore](Disable-ComputerRestore.md)

[Enable-ComputerRestore](Enable-ComputerRestore.md)

[Get-ComputerRestorePoint](Get-ComputerRestorePoint.md)

[Restart-Computer](Restart-Computer.md)
