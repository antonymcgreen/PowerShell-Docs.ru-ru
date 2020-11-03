---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/disable-computerrestore?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-ComputerRestore
ms.openlocfilehash: 941829c3caa0f6bb2f5712dda9eb7d8c36908062
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228413"
---
# Disable-ComputerRestore

## Краткий обзор
Отключает функцию восстановления системы на указанном диске файловой системы.

## SYNTAX

```
Disable-ComputerRestore [-Drive] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Командлет **Disable-ComputerRestore** отключает функцию восстановления системы на одном или нескольких дисках файловой системы.
В результате попытки восстановить компьютер не затрагивают указанный диск.

Чтобы отключить функцию восстановления системы на любом диске, ее необходимо отключить на системном диске либо предварительно, либо одновременно.

Чтобы повторно включить восстановление системы, используйте командлет Enable-ComputerRestore.
Чтобы определить состояние функции восстановления системы для каждого диска, используйте программу Rstrui.exe.

Точки восстановления системы и командлеты ComputerRestore поддерживаются только в клиентских операционных системах. таких как Windows 7, Windows Vista и Windows XP.

## Примеры

### Пример 1. Отключение восстановления системы на указанном диске

```
PS C:\> Disable-ComputerRestore -Drive "C:\"
```

Эта команда отключает восстановление системы на диске C:.

### Пример 2. Отключение восстановления системы на нескольких дисках

```
PS C:\> Disable-ComputerRestore "C:\", "D:\"
```

Эта команда отключает восстановление системы на дисках C: и D:.
В команде используется параметр *Drive* , но имя параметра диска опускается.

## PARAMETERS

### -Диск
Определяет диски файловой системы.
Введите одну или несколько букв диска файловой системы, а затем двоеточие и обратную косую черту, а также заключите их в кавычки, например C:\. или Д:\.
Этот параметр обязателен.

С помощью командлета нельзя отключить восстановление системы на удаленном сетевом диске, даже если он сопоставлен с локальным компьютером, и на дисках, на которых использование восстановления системы невозможно, например на внешних дисках.

Чтобы отключить функцию восстановления системы на любом диске, ее необходимо отключить на системном диске либо предварительно, либо одновременно.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

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

* Чтобы запустить этот командлет в Windows Vista и более поздних версиях Windows, откройте Windows PowerShell с параметром Запуск от имени администратора.

  Чтобы найти диски файловой системы, подходящие для восстановления системы, в разделе "система" панели управления перейдите на вкладку "Защита системы". Чтобы открыть эту вкладку в Windows PowerShell, введите `SystemPropertiesProtection` .

  Этот командлет использует класс инструментарий управления Windows (WMI) (WMI) **SystemRestore** .

*

## Связанные ссылки

[Checkpoint-Computer](Checkpoint-Computer.md)

[Enable-ComputerRestore](Enable-ComputerRestore.md)

[Get-ComputerRestorePoint](Get-ComputerRestorePoint.md)

[Restart-Computer](Restart-Computer.md)

[Restore-Computer](Restore-Computer.md)
