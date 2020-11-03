---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/limit-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Limit-EventLog
ms.openlocfilehash: 3ec3214103dc6151e148f7482b0be8b821871e3c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227997"
---
# Limit-EventLog

## Краткий обзор
Задает свойства журнала событий, которые ограничивают его размер и возраст записей.

## SYNTAX

```
Limit-EventLog [-LogName] <String[]> [-ComputerName <String[]>] [-RetentionDays <Int32>]
 [-OverflowAction <OverflowAction>] [-MaximumSize <Int64>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Командлет **Limit-EventLog** задает максимальный размер классического журнала событий, время хранения каждого события и то, что происходит при достижении максимального размера журнала.
Его можно использовать для настройки ограничений журналов событий на локальном и удаленном компьютерах.

Командлеты, которые содержат существительное EventLog, работают только с классическими журналами событий.
Чтобы получить события из журналов, использующих технологию журнала событий Windows, в Windows Vista и более поздних версиях Windows, используйте Get-WinEvent.

## Примеры

### Пример 1. увеличение размера журнала событий

```
PS C:\> Limit-EventLog -LogName "Windows PowerShell" -MaximumSize 20KB
```

Эта команда увеличивает максимальный размер журнала событий Windows PowerShell на локальном компьютере до 20 480 байт (20 КБ).

### Пример 2. хранить журнал событий в течение указанного времени

```
PS C:\> Limit-EventLog -LogName Security -ComputerName "Server01", "Server02" -RetentionDays 7
```

Эта команда обеспечивает хранение событий в журнале Security на компьютерах Server01 и Server02 не менее 7 дней.

### Пример 3. изменение действия переполнения для всех журналов событий

```
PS C:\> $Logs = Get-EventLog -List | ForEach {$_.log}
PS C:\> Limit-EventLog -OverflowAction OverwriteOlder -LogName $Logs
PS C:\> Get-EventLog -List

Max(K) Retain OverflowAction     Entries  Log
------ ------ --------------     -------  ---
15,168      0 OverwriteOlder       3,412  Application
512         0 OverwriteOlder           0  DFS Replication
512         0 OverwriteOlder          17  DxStudio
10,240      7 OverwriteOlder           0  HardwareEvents
512         0 OverwriteOlder           0  Internet Explorer
512         0 OverwriteOlder           0  Key Management Service
16,384      0 OverwriteOlder           4  ODiag
16,384      0 OverwriteOlder         389  OSession Security
15,168      0 OverwriteOlder      19,360  System
15,360      0 OverwriteOlder      15,828  Windows PowerShell
```

В этом примере изменяется действие переполнения всех журналов событий на локальном компьютере до Овервритеолдер.

Первая команда возвращает имена всех журналов на локальном компьютере.
Вторая команда задает действие, выполняемое при переполнении.
Третья команда отображает результаты.

## PARAMETERS

### -ComputerName
Указывает удаленные компьютеры.
По умолчанию это локальный компьютер.

Введите имя NetBIOS, IP-адрес или полное доменное имя (FQDN) удаленного компьютера.
Чтобы указать локальный компьютер, введите имя компьютера, localhost или точку (.).

Этот параметр не зависит от удаленного взаимодействия Windows PowerShell.
Параметр *ComputerName* параметра **Limit-EventLog** можно использовать, даже если компьютер не настроен для выполнения удаленных команд.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumSize
Задает максимальный размер журналов событий в байтах.
Введите значение от 64 килобайт (КБ) до 4 гигабайт (ГБ).
Значение должно быть кратным 64 КБ (65 536).

Этот параметр задает значение свойства **максимумкилобитес** объекта **System. Diagnostics. EventLog** , представляющего классическую запись журнала событий.

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Оверфловактион
Задает действие, выполняемое при достижении максимального размера журнала событий.

Допустимые значения для этого параметра:

- Донотоверврите: существующие записи сохраняются, а новые записи отбрасываются.
- Овервритеаснидед: каждая новая запись перезаписывает самую старую запись.
- Овервритеолдер: новые события перезаписывают события старше значения, заданного свойством **MinimumRetentionDays** . Если события старше, чем указано значением свойства **MinimumRetentionDays** , новые события отбрасываются.

Этот параметр задает значение свойства **оверфловактион** объекта **System. Diagnostics. EventLog** , представляющего классическую запись журнала событий.

```yaml
Type: System.Diagnostics.OverflowAction
Parameter Sets: (All)
Aliases: OFA
Accepted values: OverwriteOlder, OverwriteAsNeeded, DoNotOverwrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Ретентиондайс
Задает минимальный срок хранения события в журнале событий (в днях).

Этот параметр задает значение свойства **MinimumRetentionDays** объекта **System. Diagnostics. EventLog** , представляющего классическую запись журнала событий.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: MRD

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

* Чтобы использовать этот командлет в Windows Vista и более поздних версиях Windows, откройте Windows PowerShell с параметром Запуск от имени администратора.

  Этот командлет изменяет свойства объекта **System. Diagnostics. EventLog** , который представляет Классический журнал событий.
Чтобы просмотреть текущие параметры свойств журнала событий, введите `Get-EventLog -List` .

*

## Связанные ссылки

[Clear-EventLog](Clear-EventLog.md)

[Get-EventLog](Get-EventLog.md)

[Limit-EventLog](Limit-EventLog.md)

[New-EventLog](New-EventLog.md)

[Remove-EventLog](Remove-EventLog.md)

[Show-EventLog](Show-EventLog.md)

[Write-EventLog](Write-EventLog.md)
