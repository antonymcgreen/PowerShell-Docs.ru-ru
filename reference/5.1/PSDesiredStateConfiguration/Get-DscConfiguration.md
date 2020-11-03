---
external help file: Get-DSCConfiguration.cdxml-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/get-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DscConfiguration
ms.openlocfilehash: 42b24e72de4c4bcc9326d52861c08a05853b18e0
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228342"
---
# Get-DscConfiguration

## Краткий обзор
Возвращает текущую конфигурацию узлов.

## SYNTAX

```
Get-DscConfiguration [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
Командлет **Get-DscConfiguration** возвращает текущую конфигурацию узлов, если такая конфигурация существует.
Укажите компьютеры, используя сеансы модели CIM.
Если целевой компьютер не указан, командлет возвращает конфигурацию с локального компьютера.

## Примеры

### Пример 1. получение конфигурации для локального компьютера

```
PS C:\> Get-DscConfiguration
```

Эта команда возвращает текущее состояние для локального компьютера.

### Пример 2. получение конфигурации для указанного компьютера

```
PS C:\> $Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
PS C:\> Get-DscConfiguration -CimSession $Session
```

Этот пример получает текущее состояние с компьютера, указанного в сеансе CIM.
Пример создает сеанс CIM для компьютера с именем Server01, чтобы использовать с командлетом.
Кроме того, можно создать массив сеансов CIM для применения командлета к нескольким указанным компьютерам.

Первая команда создает сеанс CIM, используя командлет **New-CimSession** , а затем сохраняет объект **CimSession** в переменной **$Session** .
Команда запрашивает пароль.
Для получения дополнительных сведений введите `Get-Help New-CimSession`.

Вторая команда возвращает текущую конфигурацию для компьютеров, определенных объектами **CimSession** , сохраненными в переменной **$Session** , в данном случае — для компьютера с именем Server01.

## PARAMETERS

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

[Get-DscConfigurationStatus](Get-DscConfigurationStatus.md)

[Restore-DscConfiguration](Restore-DscConfiguration.md)

[Start-DscConfiguration](Start-DscConfiguration.md)

[Test-DscConfiguration](Test-DscConfiguration.md)
