---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/clear-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-EventLog
ms.openlocfilehash: 695a13d4fbbf60caadeed994c1aa9c36432be917
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228446"
---
# Clear-EventLog

## Краткий обзор
Удаляет все записи из указанных журналов событий на локальном или удаленном компьютере.

## SYNTAX

```
Clear-EventLog [-LogName] <String[]> [[-ComputerName] <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Clear-EventLog`Командлет удаляет все записи из указанных журналов событий на локальном компьютере или на удаленных компьютерах.
Для использования необходимо `Clear-EventLog` быть членом группы "Администраторы" на затронутом компьютере.

Командлеты, содержащие существительное в **EventLog** (командлеты EventLog), работают только в классических журналах событий.
Для получения событий из журналов, использующих технологию журнала событий Windows в Windows Vista и более поздних версиях Windows, используйте командлет Get-WinEvent.

## Примеры

### Пример 1. Удаление конкретных типов журналов событий с локального компьютера

```powershell
Clear-EventLog "Windows PowerShell"
```

Эта команда удаляет записи из журнала событий Windows PowerShell на локальном компьютере.

### Пример 2. Удаление конкретных нескольких типов журналов с локального и удаленных компьютеров

```powershell
Clear-EventLog -LogName ODiag, OSession -ComputerName localhost, Server02
```

Эта команда удаляет все записи журналов Microsoft Office Diagnostics (Одиаг) и Microsoft Office Sessions (Осессион) на локальном компьютере и Server02 удаленном компьютере.

### Пример 3. Очистка всех журналов на указанных компьютерах, а затем отображение списка журналов событий

```powershell
Clear-EventLog -LogName application, system -confirm
```

Эта команда запрашивает подтверждение перед удалением записей из указанных журналов событий.

### Пример 4. Очистка всех журналов на указанных компьютерах, а затем отображение списка журналов событий

```powershell
function clear-all-event-logs ($computerName="localhost")
{
   $logs = Get-EventLog -ComputerName $computername -List | ForEach-Object {$_.Log}
   $logs | ForEach-Object {Clear-EventLog -ComputerName $computername -LogName $_ }
   Get-EventLog -ComputerName $computername -list
}

clear-all-event-logs -ComputerName Server01
```

```Output
Max(K) Retain OverflowAction        Entries Log
------ ------ --------------        ------- ---
15,168      0 OverwriteAsNeeded           0 Application
15,168      0 OverwriteAsNeeded           0 DFS Replication
512         7 OverwriteOlder              0 DxStudio
20,480      0 OverwriteAsNeeded           0 Hardware Events
512         7 OverwriteOlder              0 Internet Explorer
20,480      0 OverwriteAsNeeded           0 Key Management Service
16,384      0 OverwriteAsNeeded           0 Microsoft Office Diagnostics
16,384      0 OverwriteAsNeeded           0 Microsoft Office Sessions
30,016      0 OverwriteAsNeeded           1 Security
15,168      0 OverwriteAsNeeded           2 System
15,360      0 OverwriteAsNeeded           0 Windows PowerShell
```

Эта функция очищает все журналы событий на указанных компьютерах и отображает полученный список журналов событий.

Обратите внимание, что после выполнения этой команды, но перед их выводом на экран в журналы системы и безопасности добавляются несколько записей.

## PARAMETERS

### -ComputerName

Указывает удаленный компьютер.
По умолчанию это локальный компьютер.

Введите имя NetBIOS, IP-адрес или полное доменное имя удаленного компьютера.
Чтобы указать локальный компьютер, введите имя компьютера, "localhost" или точку (.).

Этот параметр не зависит от удаленного взаимодействия Windows PowerShell.
Параметр **ComputerName** можно использовать, `Get-EventLog` даже если компьютер не настроен для выполнения удаленных команд.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: 1
Default value: Local computer
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LogName

Определяет журналы событий.
Введите имена (значение свойства Log, а не LogDisplayName) одного или нескольких журналов событий, разделенные запятыми.
Подстановочные знаки не допускаются.
Этот параметр обязателен.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: LN

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## Входные данные

### Нет

Вы не можете передать объекты в `Clear-EventLog` .

## Выходные данные

### Нет

Этот командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

- Для использования `Clear-EventLog` в Windows Vista и более поздних версиях Windows запустите Windows PowerShell с параметром "Запуск от имени администратора".

## Связанные ссылки

[Get-EventLog](Get-EventLog.md)

[Limit-EventLog](Limit-EventLog.md)

[New-EventLog](New-EventLog.md)

[Remove-EventLog](Remove-EventLog.md)

[Show-EventLog](Show-EventLog.md)

[Write-EventLog](Write-EventLog.md)
