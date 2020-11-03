---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-EventLog
ms.openlocfilehash: 4cf29146727c9a54715459a2d56e47a27c5bacc0
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227942"
---
# Remove-EventLog

## Краткий обзор
Удаляет журнал событий или отменяет регистрацию источника событий.

## SYNTAX

### Default (по умолчанию)

```
Remove-EventLog [[-ComputerName] <String[]>] [-LogName] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Источник

```
Remove-EventLog [[-ComputerName] <String[]>] [-Source <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Командлет **Remove-EventLog** удаляет файл журнала событий с локального или удаленного компьютера и отменяет регистрацию всех источников событий для журнала.
Кроме того, этот командлет можно использовать для отмены регистрации источников событий без удаления каких-либо журналов событий.

Командлеты, содержащие существительное в **EventLog** , командлеты **EventLog** , работают только с классическими журналами событий.
Для получения событий из журналов, использующих технологию журнала событий Windows в Windows Vista и более поздних версиях операционной системы Windows, используйте Get-WinEvent.

ВНИМАНИЕ! этот командлет может удалять журналы событий операционной системы, что может привести к сбоям приложения и непредвиденному поведению системы.

## Примеры

### Пример 1. Удаление журнала событий с локального компьютера

```
PS C:\> Remove-EventLog -LogName "MyLog"
```

Эта команда удаляет журнал событий MyLog с локального компьютера и отменяет регистрацию источников событий для этого журнала.

### Пример 2. Удаление журнала событий с нескольких компьютеров

```
PS C:\> Remove-EventLog -LogName "MyLog", "TestLog" -ComputerName "Server01", "Server02", "localhost"
```

Эта команда удаляет журналы событий Милог и TestLog с локального компьютера, а также с удаленных компьютеров Server01 и Server02.
и отменяет регистрацию источников событий для этих журналов.

### Пример 3. Удаление источника события

```
PS C:\> Remove-EventLog -Source "MyApp"
```

Эта команда удаляет источник событий MyApp из журналов на локальном компьютере.
По завершении выполнения команды программа MyApp не сможет выполнить запись в какие бы то ни было журналы событий.

### Пример 4. Удаление журнала событий и подтверждение действия

```
The first command lists the event logs on the local computer.
PS C:\> Get-EventLog -List
Max(K) Retain OverflowAction        Entries Log
------ ------ --------------        ------- ---
15,168      0 OverwriteAsNeeded      22,923 Application
15,168      0 OverwriteAsNeeded          53 DFS Replication
15,168      7 OverwriteOlder              0 Hardware Events
512      7 OverwriteOlder              0 Internet Explorer
20,480      0 OverwriteAsNeeded           0 Key Management Service
30,016      0 OverwriteAsNeeded      50,060 Security
15,168      0 OverwriteAsNeeded      27,592 System
15,360      0 OverwriteAsNeeded      18,355 Windows PowerShell
15,168      7 OverwriteAsNeeded          12 ZapLog

The second command deletes the ZapLog event log.
PS C:\> Remove-EventLog -LogName "ZapLog"

The third command lists the event logs again. The ZapLog event log no longer appears in the list.
PS C:\> Get-EventLog -List
Max(K) Retain OverflowAction        Entries Log
------ ------ --------------        ------- ---
15,168      0 OverwriteAsNeeded      22,923 Application
15,168      0 OverwriteAsNeeded          53 DFS Replication
15,168      7 OverwriteOlder              0 Hardware Events
512      7 OverwriteOlder              0 Internet Explorer
20,480      0 OverwriteAsNeeded           0 Key Management Service
30,016      0 OverwriteAsNeeded      50,060 Security
15,168      0 OverwriteAsNeeded      27,592 System
15,360      0 OverwriteAsNeeded      18,355 Windows PowerShell
```

Эти команды показывают, как получить список журналов событий на компьютере и убедиться, что команда **Remove-EventLog** выполнена успешно.

### Пример 5. Удаление источника события и подтверждение действия

```
PS C:\> Get-WmiObject win32_nteventlogfile -Filter "logfilename='TestLog'" | foreach {$_.sources}
MyApp
TestApp
PS C:\> Remove-Eventlog -Source "MyApp"
PS C:\> Get-WmiObject win32_nteventlogfile -Filter "logfilename='TestLog'"} | foreach {$_.sources}
TestApp
```

С помощью командлета Get-WmiObject эти команды выводят список источников событий на локальном компьютере.
Эти команды можно использовать для проверки выполнения команды или удаления источника событий.

Первая команда выдает источники событий TestLog журнала событий на локальном компьютере.
Одним из источников является MyApp.

Вторая команда использует параметр *Source* командлета **Remove-EventLog** для удаления источника событий MyApp.

Третья команда идентична первой.
Она показывает, что источник событий MyApp удален.

## PARAMETERS

### -ComputerName
Указывает удаленный компьютер.
По умолчанию это локальный компьютер.

Введите имя NetBIOS, IP-адрес или полное доменное имя удаленного компьютера.
Чтобы указать локальный компьютер, введите имя компьютера, localhost или точку (.).

Этот параметр не зависит от удаленного взаимодействия Windows PowerShell.
Параметр *ComputerName* командлета **Remove-EventLog** можно использовать, даже если компьютер не настроен для выполнения удаленных команд.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogName
Определяет журналы событий.
Введите имя журнала одного или нескольких журналов событий, разделенных запятыми.
Имя журнала — это значение свойства **log** , а не *LogDisplayName* , а подстановочные знаки не допускаются.
Этот параметр обязателен.

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases: LN

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Source
Указывает источники событий, для которых этот командлет отменяет регистрацию.
Введите имена источников, а не имя исполняемого файла, разделенные запятыми.

```yaml
Type: System.String[]
Parameter Sets: Source
Aliases: SRC

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
Этот командлет не возвращает никакие выходные данные.

## ПРИМЕЧАНИЯ

* Чтобы использовать **Remove-EventLog** в Windows Vista и более поздних версиях операционной системы Windows, запустите Windows PowerShell с помощью команды Запуск от имени администратора.

  Если удалить журнал событий, а затем создать его заново, регистрация источников событий, которые использовались с прежним журналом, будет невозможна.
Приложения, которые использовали источники событий для внесения записей в исходный журнал, не будут записывать данные в новый журнал.

* После отмены регистрации источника событий для одного журнала этому источнику может быть запрещена запись данных в другие журналы.

## Связанные ссылки

[Clear-EventLog](Clear-EventLog.md)

[Get-EventLog](Get-EventLog.md)

[Limit-EventLog](Limit-EventLog.md)

[New-EventLog](New-EventLog.md)

[Remove-EventLog](Remove-EventLog.md)

[Show-EventLog](Show-EventLog.md)

[Write-EventLog](Write-EventLog.md)
