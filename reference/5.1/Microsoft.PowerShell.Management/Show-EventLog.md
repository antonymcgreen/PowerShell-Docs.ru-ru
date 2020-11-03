---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/show-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Show-EventLog
ms.openlocfilehash: e8dbcf1aa4280c0481714a8a9fb24f2e5ef79ffe
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227869"
---
# Show-EventLog

## Краткий обзор
Отображает журналы событий локального или удаленного компьютера в просмотре событий.

## SYNTAX

```
Show-EventLog [[-ComputerName] <String>] [<CommonParameters>]
```

## DESCRIPTION
Командлет Display **-EventLog** откроется Просмотр событий на локальном компьютере и отобразит в нем все классические журналы событий на локальном или удаленном компьютере.

Чтобы открыть Просмотр событий в Windows Vista и более поздних версиях операционной системы Windows, текущий пользователь должен быть членом группы администраторов на локальном компьютере.

Командлеты, содержащие существительное в **EventLog** (командлеты **EventLog** ), работают только в классических журналах событий.
Для получения событий из журналов, использующих технологию журнала событий Windows в Windows Vista и более поздних версиях операционной системы Windows, используйте командлет Get-WinEvent.

## Примеры

### Пример 1. Отображение журналов событий для локального компьютера

```
PS C:\> Show-EventLog
```

Эта команда открывает просмотр событий и отображает в нем классические журналы событий на локальном компьютере.

### Пример 2. Отображение журналов событий для удаленного компьютера

```
PS C:\> Show-EventLog -ComputerName "Server01"
```

Эта команда открывает просмотр событий и отображает в нем классические журналы событий на компьютере Server01.

## PARAMETERS

### -ComputerName
Указывает удаленный компьютер.
**Показать-EventLog** отображает журналы событий с указанного компьютера в Просмотр событий на локальном компьютере.
По умолчанию это локальный компьютер.

Введите имя NetBIOS, IP-адрес или полное доменное имя удаленного компьютера.

Этот параметр не зависит от удаленного взаимодействия Windows PowerShell.
Параметр *ComputerName* можно использовать, даже если компьютер не настроен для выполнения удаленных команд.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: CN

Required: False
Position: 0
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

### Нет
Этот командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

* Командная строка Windows PowerShell возвращается сразу после открытия просмотра событий. При открытом окне просмотра событий можно работать в текущем сеансе.

  Поскольку этот командлет требует наличия пользовательского интерфейса, он недоступен в варианте установки основных серверных компонентов операционной системы Windows Server.

*

## Связанные ссылки

[Clear-EventLog](Clear-EventLog.md)

[Get-EventLog](Get-EventLog.md)

[Limit-EventLog](Limit-EventLog.md)

[New-EventLog](New-EventLog.md)

[Remove-EventLog](Remove-EventLog.md)

[Write-EventLog](Write-EventLog.md)
