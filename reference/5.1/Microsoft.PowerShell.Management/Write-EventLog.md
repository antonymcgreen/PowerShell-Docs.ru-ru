---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/write-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-EventLog
ms.openlocfilehash: cae34c4cf942d9aa4abb9a2d716ef9854f70de2e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227813"
---
# Write-EventLog

## Краткий обзор
Записывает событие в журнал событий.

## SYNTAX

```
Write-EventLog [-LogName] <String> [-Source] <String> [[-EntryType] <EventLogEntryType>] [-Category <Int16>]
 [-EventId] <Int32> [-Message] <String> [-RawData <Byte[]>] [-ComputerName <String>] [<CommonParameters>]
```

## DESCRIPTION
Командлет **Write-EventLog** записывает событие в журнал событий.

Чтобы событие было записано в журнал событий, он должен существовать на компьютере и иметь зарегистрированный источник.

Командлеты, содержащие существительное в **EventLog** (командлеты **EventLog** ), работают только в классических журналах событий.
Для получения событий из журналов, использующих технологию журнала событий Windows в Windows Vista и более поздних версиях операционной системы Windows, используйте командлет Get-WinEvent.

## Примеры

### Пример 1. запись события в журнал событий приложений

```
PS C:\> Write-EventLog -LogName "Application" -Source "MyApp" -EventID 3001 -EntryType Information -Message "MyApp added a user-requested feature to the display." -Category 1 -RawData 10,20
```

Эта команда записывает событие из источника MyApp в журнал событий Application.

### Пример 2. запись события в журнал событий приложений на удаленном компьютере

```
PS C:\> Write-EventLog -ComputerName "Server01" -LogName Application -Source "MyApp" -EventID 3001 -Message "MyApp added a user-requested feature to the display."
```

Эта команда записывает событие из источника MyApp в журнал событий Application на удаленном компьютере Server01.

## PARAMETERS

### -Category
Указывает категорию задач для события.
Введите целочисленное значение, связанное со строками в файле сообщений категорий для журнала событий.

```yaml
Type: System.Int16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Указывает удаленный компьютер.
По умолчанию это локальный компьютер.

Введите имя NetBIOS, IP-адрес или полное доменное имя удаленного компьютера.

Этот параметр не зависит от удаленного взаимодействия Windows PowerShell.
Параметр *ComputerName* командлета Get-EventLog можно использовать, даже если компьютер не настроен для выполнения удаленных команд.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: CN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EntryType
Указывает тип записи события.
Допустимые значения для этого параметра: Error, Warning, Information, SuccessAudit и FailureAudit.
По умолчанию используется значение Information.

Описание значений см. в разделе [перечисление евентложентритипе](https://go.microsoft.com/fwlink/?LinkId=143599) в библиотеке MSDN.

```yaml
Type: System.Diagnostics.EventLogEntryType
Parameter Sets: (All)
Aliases: ET
Accepted values: Error, Information, FailureAudit, SuccessAudit, Warning

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EventId
Указывает идентификатор события.
Этот параметр обязателен.
Максимальное значение для параметра *EventID* — 65535.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: ID, EID

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogName
Указывает имя журнала, в который записывается событие.
Введите имя журнала.
Имя журнала — это значение свойства **log** , а не **LogDisplayName** .
Подстановочные знаки не допускаются.
Этот параметр обязателен.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: LN

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Message
Определяет сообщение о событии.
Этот параметр обязателен.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: MSG

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RawData
Указывает двоичные данные, связанные с событием, в байтах.

```yaml
Type: System.Byte[]
Parameter Sets: (All)
Aliases: RD

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Source
Указывает источник события (обычно имя приложения, которое записывает события в журнал).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: SRC

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры
Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет
В этот командлет нельзя передать входные данные.

## Выходные данные

### System. Diagnostics. EventLogEntry
Этот командлет возвращает объекты, представляющие события в журналах.

## ПРИМЕЧАНИЯ

* Чтобы использовать **Write-EventLog** , запустите Windows PowerShell с помощью команды Запуск от имени администратора.

*

## Связанные ссылки

[Clear-EventLog](Clear-EventLog.md)

[Get-EventLog](Get-EventLog.md)

[Limit-EventLog](Limit-EventLog.md)

[New-EventLog](New-EventLog.md)

[Remove-EventLog](Remove-EventLog.md)

[Show-EventLog](Show-EventLog.md)

[Write-EventLog](Write-EventLog.md)
