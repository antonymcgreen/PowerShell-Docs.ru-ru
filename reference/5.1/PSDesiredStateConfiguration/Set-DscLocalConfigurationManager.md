---
external help file: Microsoft.Windows.DSC.CoreConfProviders.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 04/29/2020
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/set-dsclocalconfigurationmanager?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DscLocalConfigurationManager
ms.openlocfilehash: 0d35aa56a52f0e6c17abd0e7b2707869e780324c
ms.sourcegitcommit: 0d4d3e47f6979876550591f62061096e7a568f7e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2020
ms.locfileid: "93229673"
---
# Set-DscLocalConfigurationManager

## Краткий обзор

Применяет локальные параметры Configuration Manager (LCM) к узлам.

## SYNTAX

### Компутернамесет (по умолчанию)

```
Set-DscLocalConfigurationManager [-Path] <String> [-Force] [[-ComputerName] <String[]>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Цимсессионсет

```
Set-DscLocalConfigurationManager [-Path] <String> [-Force] [-ThrottleLimit <Int32>] -CimSession <CimSession[]>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Set-DscLocalConfigurationManager`Командлет применяет параметры LCM или мета-конфигурацию к узлам. Укажите компьютеры, выбрав имена компьютеров или используя сеансы модели CIM. Если целевой компьютер не указан, командлет применяет параметры к локальному компьютеру.

## Примеры

### Пример 1. применение параметров LCM

```
Set-DscLocalConfigurationManager -Path "C:\DSC\Configurations\"
```

Эта команда применяет параметры LCM `C:\DSC\Configurations\` к целевым узлам. После получения параметров LCM обрабатывает их.

> [!WARNING]
> Если для одного и того же компьютера, хранящегося в указанной папке, существует несколько мета-MOF, будет применен только первый объект meta MOF.

### Пример 2. применение параметров LCM с помощью сеанса CIM

```
$Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
Set-DscLocalConfigurationManager -Path "C:\DSC\Configurations\" -CimSession $Session
```

Этот пример применяет параметры LCM к компьютеру и применяет параметры. Пример создает сеанс CIM для компьютера с именем Server01, чтобы использовать с командлетом. Кроме того, можно создать массив сеансов CIM для применения командлета к нескольким указанным компьютерам.

Первая команда создает сеанс CIM с помощью `New-CimSession` командлета, а затем сохраняет объект **CimSession** в `$Session` переменной. Команда запрашивает пароль. Для получения дополнительных сведений введите `Get-Help New-CimSession`.

Вторая команда применяет параметры LCM к целевому узлу с `C:\DSC\Configurations\` компьютера, определяемого объектами **CimSession** , хранящимися в `$Session` переменной. В этом примере `$Session` переменная содержит сеанс CIM только для компьютера с именем Server01. Команда применяет параметры. После получения параметров LCM обрабатывает их.

## PARAMETERS

### -CimSession

Запуск командлета в удаленном сеансе или на удаленном компьютере. Введите имя компьютера или объект сеанса, например выходные данные командлета [New-CimSession](/powershell/module/CimCmdlets/New-CimSession) или [Get-CimSession](/powershell/module/CimCmdlets/Get-CimSession) .
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

Указывает массив имен компьютеров. Этот параметр позволяет задать для компьютеров с документами мета-конфигурации в параметре **path** значения, указанные в массиве.

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

Указывает имя пользователя и пароль как объект **PSCredential** для целевого компьютера. Чтобы получить объект **PSCredential** , используйте командлет Get-Credential. Для получения дополнительных сведений введите `Get-Help Get-Credential`.

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

### -Force

Принудительное выполнение команды без запроса на подтверждение пользователем.

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

### -Path

Указывает путь к файлу папки, которая содержит файлы параметров конфигурации. Командлет публикует и применяет эти параметры LCM к компьютерам, имеющим файлы параметров по указанному пути. Каждый целевой узел должен иметь файл параметров следующего формата: `NetBIOS Name.meta.mof` .

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

Указание максимального количества одновременных операций, которые можно выполнять для запуска командлета. Если этот параметр пропущен или указано значение `0` , Windows PowerShell вычисляет оптимальное ограничение регулирования для командлета на основе числа командлетов CIM, выполняемых на компьютере. Предел регулирования применим только к текущему командлету, а не к сеансу или компьютеру.

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

[Обзор Windows PowerShell Desired State Configuration](/powershell/scripting/dsc/overview/overview)

[Get-DscLocalConfigurationManager](Get-DscLocalConfigurationManager.md)
