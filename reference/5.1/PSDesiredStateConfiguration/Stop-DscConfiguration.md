---
external help file: Stop-DscConfiguration.cdxml-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 08/19/2019
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/stop-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-DscConfiguration
ms.openlocfilehash: 93c8585ae948dfa360a2ae8e2563670de8fd6e93
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227465"
---
# Stop-DscConfiguration

## Краткий обзор
Останавливает выполняемое задание настройки.

## SYNTAX

### Все

```
Stop-DscConfiguration [-Force] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Stop-DscConfiguration`Командлет останавливает выполняемое задание настройки. Укажите компьютеры, к которым применяется этот командлет, с помощью сеансов модель CIM (CIM). Если задание конфигурации не запускается, этот командлет возвращает предупреждающее сообщение.

`Stop-DscConfiguration` доступно только в составе [накопительного пакета обновления за ноябрь 2014 для Windows RT 8,1, Windows 8.1 и Windows Server 2012 R2](https://support.microsoft.com/kb/3000850) из библиотеки служба поддержки Майкрософт. Перед использованием этого командлета ознакомьтесь со сведениями в подразделах [что нового в Windows PowerShell 5,0](/powershell/scripting/whats-new/What-s-New-in-Windows-PowerShell-50)

## Примеры

### Пример 1. завершение задания конфигурации

В этом примере создается сеанс CIM с помощью `New-CimSession` командлета. Объект **CimSession** используется для завершения выполняющегося задания конфигурации.

```powershell
$Session = New-CimSession -ComputerName Server01 -Credential ACCOUNTS\User01
Stop-DscConfiguration -CimSession $Session
```

`New-CimSession` использует параметр **ComputerName** для указания компьютера Server01. Параметр **Credential** указывает учетную запись пользователя. Объект **CimSession** хранится в `$Session` переменной. При выполнении команды вам будет предложено ввести пароль учетной записи пользователя.

`Stop-DscConfiguration` использует параметр **CimSession** и объект, хранящийся в `$Session` , для завершения задания настройки.

## PARAMETERS

### -AsJob

Указывает, что этот командлет выполняет команду как фоновое задание. Дополнительные сведения о фоновых заданиях PowerShell см. в разделе [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) и [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md).

Для использования параметра **AsJob** локальный и удаленный компьютеры должны быть настроены для удаленного взаимодействия. В Windows Vista и более поздних версиях операционной системы Windows необходимо открыть PowerShell с параметром **Запуск от имени администратора** . Дополнительные сведения см. в разделе [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession

Запуск командлета в удаленном сеансе или на удаленном компьютере. Введите имя компьютера или объект сеанса, например выходные данные из `New-CimSession` или `Get-CimSession` .

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

### -Confirm

`Stop-DscConfiguration` не поддерживает параметр **Confirm** . Если используется параметр **Confirm** , выводится сообщение об ошибке.

Для командлетов PowerShell, поддерживающих **Confirm** , с помощью параметра запрашиваются подтверждение перед выполнением команды.

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

### -Force

Принудительное выполнение команды без запроса на подтверждение пользователем.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

Указание максимального количества одновременных операций, которые можно выполнять для запуска командлета.

Если этот параметр пропущен или указано значение `0` , PowerShell вычисляет оптимальное ограничение регулирования на основе числа командлетов CIM, выполняемых на компьютере. Предел регулирования применим только к текущему командлету, а не к сеансу или компьютеру.

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

### -WhatIf

Показывает, что произойдет при запуске командлета. Командлет не выполняется.

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

## Выходные данные

### Нет

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Get-CimSession](../CimCmdlets/Get-CimSession.md)

[Get-DscConfiguration](Get-DscConfiguration.md)

[Get-DscConfigurationStatus](Get-DscConfigurationStatus.md)

[New-CimSession](../CimCmdlets/New-CimSession.md)

[Restore-DscConfiguration](Restore-DscConfiguration.md)

[Start-DscConfiguration](Start-DscConfiguration.md)

[Test-DscConfiguration](Test-DscConfiguration.md)

[Update-DscConfiguration](Update-DscConfiguration.md)

[Обзор Windows PowerShell Desired State Configuration](/powershell/scripting/dsc/overview/overview)
