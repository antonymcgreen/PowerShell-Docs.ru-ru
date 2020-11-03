---
external help file: Microsoft.Windows.DSC.CoreConfProviders.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/update-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-DscConfiguration
ms.openlocfilehash: 13365902ab317a3daa41b9a951d5e2fa6e4f1b37
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227450"
---
# Update-DscConfiguration

## Краткий обзор
Проверяет наличие обновленной конфигурации опрашивающего сервера и применяет его.

## SYNTAX

### Компутернамесет (по умолчанию)

```
Update-DscConfiguration [-Wait] [-JobName <String>] [[-ComputerName] <String[]>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Цимсессионсет

```
Update-DscConfiguration [-Wait] [-JobName <String>] [-ThrottleLimit <Int32>] -CimSession <CimSession[]>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
`Update-DscConfiguration`Командлет подключается к опрашивающем серверу, загружает конфигурацию, если она отличается от текущей на узле, а затем применяет конфигурацию к компьютеру.

Этот командлет доступен только в составе [накопительного пакета обновления за ноябрь 2014 для Windows RT 8,1, Windows 8.1 и Windows Server 2012 R2](https://support.microsoft.com/kb/3000850) из библиотеки служба поддержки Майкрософт.

## Примеры

### Пример 1. Обновление конфигурации

```
PS C:\> Update-DscConfiguration -Wait -Verbose
```

После выполнения этой команды сервер будет подключаться к зарегистрированной опрашивающей службе, загрузить последнюю назначенную конфигурацию и применить ее.
Параметры-Wait и-verbose являются необязательными.
При работе в интерактивном режиме эти параметры позволяют оставить отзыв о ходе выполнения и успехе или сбое при применении конфигурации.

### Пример 2. Обновление конфигурации путем подключения через сеанс CIM

```
PS C:\> $Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
PS C:\> Update-DscConfiguration -CimSession $Session -Wait
```

Первая команда создает сеанс CIM, используя командлет **New-CimSession** , а затем сохраняет объект **CimSession** в переменной $Session.
Команда запрашивает пароль.
Для получения дополнительных сведений введите `Get-Help New-CimSession`.

Вторая команда обновляет компьютер, указанный в параметре **CimSession** , который хранится в $Session.
Команда задает параметр *Wait* .
Консоль не принимает дополнительные команды до тех пор, пока текущая команда не будет завершена.

## PARAMETERS

### -CimSession
Запуск командлета в удаленном сеансе или на удаленном компьютере.
Введите имя компьютера или объект сеанса, например выходные данные командлета [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) или [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) .
Сеанс по умолчанию — текущий сеанс на локальном компьютере.

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: CimSessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ComputerName
Указывает массив имен компьютеров.
Командлет применяет параметры конфигурации к компьютерам, указанному этим параметром.

```yaml
Type: System.String[]
Parameter Sets: ComputerNameSet
Aliases: CN, ServerName

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Credential
Указывает имя пользователя и пароль как объект **PSCredential** для целевого компьютера.
Чтобы получить объект **PSCredential** , используйте командлет Get-Credential.
Для получения дополнительных сведений введите `Get-Help Get-Credential`.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerNameSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobName
Задает понятное имя для задания.
Если указать этот параметр, командлет выполняется как задание и возвращает объект **Job** .

По умолчанию Windows PowerShell назначает имя Жобн, где N — целое число.

Если параметр *Wait* указан, не указывайте этот параметр.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

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

### -Wait
Указывает, что командлет блокирует консоль до тех пор, пока не завершит все задачи настройки.

Если этот параметр указан, не указывайте параметр *JobName* .

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

## Выходные данные

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Обзор Windows PowerShell Desired State Configuration](/powershell/scripting/dsc/overview/dscforengineers)

[Get-DscConfiguration](Get-DscConfiguration.md)

[Get-DscConfigurationStatus](Get-DscConfigurationStatus.md)

[Restore-DscConfiguration](Restore-DscConfiguration.md)

[Start-DscConfiguration](Start-DscConfiguration.md)

[Stop-DscConfiguration](Stop-DscConfiguration.md)

[Test-DscConfiguration](Test-DscConfiguration.md)
