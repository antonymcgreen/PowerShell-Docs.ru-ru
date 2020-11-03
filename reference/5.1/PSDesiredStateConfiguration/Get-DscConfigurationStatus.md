---
external help file: Get-DscConfigurationStatus.cdxml-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/get-dscconfigurationstatus?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DscConfigurationStatus
ms.openlocfilehash: 0d59ce58a70eab68441ea1fe6097bbdf7792a54f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228346"
---
# Get-DscConfigurationStatus

## Краткий обзор
Извлекает данные о завершенных запусках конфигурации.

## SYNTAX

```
Get-DscConfigurationStatus [-All] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
Командлет **Get-DscConfigurationStatus** извлекает подробные сведения о завершенных запусках конфигурации в системе.
По умолчанию он возвращает сведения о последнем запуске конфигурации.
Этот командлет полезен для поиска исторических сведений о выполнении конфигурации, например при выполнении конфигураций, состоянии выполнения, количестве ресурсов в конфигурациях, а также об успешном или неудачном завершении ресурсов.

## Примеры

### Пример 1. Получение сведений о последнем запуске конфигурации

```
PS C:\> Get-DscConfigurationStatus
```

Эта команда возвращает сведения о последнем запуске конфигурации.

### Пример 2. Получение сведений обо всех конфигурациях

```
PS C:\> Get-DscConfigurationStatus -All
```

Эта команда возвращает сведения обо всех конфигурациях, которые были запущены в системе, включая проверку согласованности Desired State Configuration (DSC) Windows PowerShell.

### Пример 3. Получение сведений о настройке, выполняемой на удаленном компьютере

```
PS C:\> Get-DscConfigurationStatus -CimSession "Server01"
```

Эта команда возвращает сведения о выполнении конфигурации удаленного компьютера с именем Server01.
При этом используется транспорт WSMan для подключения к удаленному компьютеру и требуется, чтобы подключающийся пользователь был администратором на удаленном компьютере.

## PARAMETERS

### -All
Указывает, что этот командлет извлекает сведения обо всех запусках конфигурации на компьютере, включая приложение конфигурации и проверку согласованности.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsJob
Указывает, что этот командлет выполняет команду как фоновое задание.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession
Запуск командлета в удаленном сеансе или на удаленном компьютере.
Введите имя компьютера или объект сеанса, например выходные данные командлета [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) или [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) .
Сеанс по умолчанию — текущий сеанс на локальном компьютере.

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
Указание максимального количества одновременных операций, которые можно выполнять для запуска командлета.
Если этот параметр пропущен или указано значение `0` , Windows PowerShell вычисляет оптимальное ограничение регулирования для командлета на основе числа командлетов CIM, выполняемых на компьютере.
Предел регулирования применим только к текущему командлету, а не к сеансу или компьютеру.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры
Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

## Выходные данные

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Обзор Windows PowerShell Desired State Configuration](/powershell/scripting/dsc/overview/dscforengineers)

[Get-DscConfiguration](Get-DscConfiguration.md)

[Get-DscLocalConfigurationManager](Get-DscLocalConfigurationManager.md)

[Restore-DscConfiguration](Restore-DscConfiguration.md)

[Start-DscConfiguration](Start-DscConfiguration.md)

[Test-DscConfiguration](Test-DscConfiguration.md)
