---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/enable-computerrestore?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-ComputerRestore
ms.openlocfilehash: f9616a7f9af4dd2fa45e150bb64eef65427b4947
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228410"
---
# Enable-ComputerRestore

## Краткий обзор
Включает функцию восстановления на указанном диске файловой системы.

## SYNTAX

```
Enable-ComputerRestore [-Drive] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Командлет **Enable-ComputerRestore** включает функцию восстановления системы на одном или нескольких дисках файловой системы.
В результате такие средства как командлет Restore-Computer можно использовать для восстановления компьютера в предыдущее состояние.

По умолчанию функция восстановления системы включена на всех соответствующих дисках, но ее можно отключить, например, с помощью командлета Disable-ComputerRestore.
Чтобы включить (или повторно включить) функцию восстановления системы на каком-либо диске, ее необходимо включить на системном диске (предварительно или одновременно).
Чтобы определить состояние функции восстановления системы для каждого диска, используйте программу Rstrui.exe.

Точки восстановления системы и командлеты ComputerRestore поддерживаются только в клиентских операционных системах. таких как Windows 7, Windows Vista и Windows XP.

## Примеры

### Пример 1. Включение восстановления системы на указанном диске

```
PS C:\> Enable-ComputerRestore -Drive "C:\"
```

Эта команда включает восстановление системы на диске C: локального компьютера.

### Пример 2. Включение восстановления системы на нескольких дисках

```
PS C:\> Enable-ComputerRestore -Drive "C:\", "D:\"
```

Эта команда включает восстановление системы на дисках C: и D: локального компьютера.

## PARAMETERS

### -Диск
Определяет диски файловой системы.
Введите одну или несколько букв диска файловой системы, а затем двоеточие и обратную косую черту, а также заключите их в кавычки, например C:\. или Д:\.
Этот параметр обязателен.

С помощью этого командлета нельзя включить функцию восстановления системы на удаленном сетевом диске, даже если он подключен к локальному компьютеру, а также на дисках, не подходящих для ее использования, например, на внешних дисках.

Чтобы включить функцию восстановления системы на каком-либо диске, ее необходимо включить на системном диске (предварительно или одновременно).

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
Нельзя передать объекты в этот командлет с помощью конвейера.

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

[Disable-ComputerRestore](Disable-ComputerRestore.md)

[Get-ComputerRestorePoint](Get-ComputerRestorePoint.md)

[Restart-Computer](Restart-Computer.md)

[Restore-Computer](Restore-Computer.md)
