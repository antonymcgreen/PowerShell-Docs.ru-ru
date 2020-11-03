---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 01/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-EventLog
ms.openlocfilehash: 61fafc0670a24fd6ca057e4cf0c7179d90446b07
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227974"
---
# New-EventLog

## Краткий обзор
Создает новый журнал событий и новый источник событий на локальном или удаленном компьютере.

## SYNTAX

```
New-EventLog [-LogName] <string> [-Source] <string[]> [[-ComputerName] <string[]>]
  [-CategoryResourceFile <string>] [-MessageResourceFile <string>] [-ParameterResourceFile <string>]
  [<CommonParameters>]
```

## DESCRIPTION

Этот командлет создает классический журнал событий на локальном или удаленном компьютере. С его помощью можно также зарегистрировать источник событий, записывающий данные в новый или существующий журнал.

Командлеты с существительным EventLog (командлеты журнала событий) работают только с классическими журналами событий.
Для получения событий из журналов, использующих технологию журнала событий Windows в Windows Vista и более поздних версиях Windows, используйте `Get-WinEvent` .

## Примеры

### Пример 1. Создание нового журнала событий

Эта команда создает журнал событий TestLog на локальном компьютере и регистрирует для него новый источник.

```powershell
New-EventLog -source TestApp -LogName TestLog -MessageResourceFile C:\Test\TestApp.dll
```

### Пример 2. Добавление нового источника событий в существующий журнал

Эта команда добавляет новый источник событий NewTestApp в журнал приложений на удаленном компьютере Server01.

```powershell
$file = "C:\Program Files\TestApps\NewTestApp.dll"
New-EventLog -ComputerName Server01 -Source NewTestApp -LogName Application -MessageResourceFile $file -CategoryResourceFile $file
```

Команда требует, чтобы файл NewTestApp.dll находился на компьютере Server01.

## PARAMETERS

### -Категориресаурцефиле

Указывает путь к файлу, содержащему строки категорий для исходных событий. Этот файл также известен как файл сообщений о категориях.

Он должен находиться на компьютере, на котором создается журнал событий. Этот параметр не создает и не перемещает файлы.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: CRF

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Создает журналы событий на указанных компьютерах. По умолчанию это локальный компьютер.

Имя NetBIOS, IP-адрес или полное доменное имя удаленного компьютера.
Чтобы указать локальный компьютер, введите имя компьютера, "localhost" или точку (.).

Этот параметр не зависит от удаленного взаимодействия PowerShell. Параметр **ComputerName** можно использовать, `Get-EventLog` даже если компьютер не настроен для выполнения удаленных команд.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN

Required: False
Position: 3
Default value: Local computer
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogName

Указывает имя журнала событий.

Если журнал не существует, `New-EventLog` создает журнал и использует это значение для свойств **log** и **LogDisplayName** нового журнала событий. Если журнал существует, `New-EventLog` регистрирует новый источник для журнала событий.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: LN

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Мессажересаурцефиле

Указывает путь к файлу, содержащему строки форматирования сообщений для исходных событий.
Этот файл также известен как файл сообщений о событиях.

Он должен находиться на компьютере, на котором создается журнал событий.
Этот параметр не создает и не перемещает файлы.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: MRF

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Параметерресаурцефиле

Указывает путь к файлу, который содержит строки, используемые для подстановки параметров в описаниях событий. Этот файл также известен как файл сообщений о параметрах.

Он должен находиться на компьютере, на котором создается журнал событий.
Этот параметр не создает и не перемещает файлы.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PRF

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Source

Указывает имена источников журнала событий, например программ, записывающих данные в журнал событий. Этот параметр обязателен.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: SRC

Required: True
Position: 2
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

## ПРИМЕЧАНИЯ

Для использования `New-EventLog` в Windows Vista и более поздних версиях Windows откройте PowerShell с параметром "Запуск от имени администратора".

Для создания источника событий в Windows Vista, Windows XP Professional или Windows Server 2003 необходимо быть членом группы "Администраторы" на компьютере.

При создании журнала событий и источника событий система регистрирует источник для нового журнала, но журнал не создается, пока в него не будет внесена первая запись.

Журналы событий сохраняются операционной системой как файлы.

При создании нового журнала событий связанный файл сохраняется в `$env:SystemRoot\System32\Config` каталоге на указанном компьютере.

Имя файла — первые восемь символов свойства **log** с расширением evt.

## Связанные ссылки

[Clear-EventLog](Clear-EventLog.md)

[Get-EventLog](Get-EventLog.md)

[Get-WinEvent](../Microsoft.PowerShell.Diagnostics/Get-WinEvent.md)

[Limit-EventLog](Limit-EventLog.md)

[New-EventLog](New-EventLog.md)

[Remove-EventLog](Remove-EventLog.md)

[Show-EventLog](Show-EventLog.md)

[Write-EventLog](Write-EventLog.md)
