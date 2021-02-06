---
external help file: PSDesiredStateConfiguration-help.xml
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/new-dscchecksum?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-DscChecksum
ms.openlocfilehash: 8b8d0c545cdb36b6184a0670a52a5a30aa33a465
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605049"
---
# New-DscChecksum

## Краткий обзор
Создает файлы контрольных сумм для документов DSC и ресурсов DSC.

## SYNTAX

```
New-DscChecksum [-Path] <String[]> [[-OutPath] <String>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Командлет **New-DSCCheckSum** создает файлы контрольных сумм для документов DSC и сжатых ресурсов DSC PowerShell.
Этот командлет создает файл контрольной суммы для каждой конфигурации и ресурса, которые будут использоваться в режиме опроса.
Служба DSC использует контрольные суммы, чтобы убедиться, что на целевом узле существуют правильная конфигурация и ресурсы.
Разместите контрольные суммы вместе со связанными документами DSC и сжатыми ресурсами DSC в хранилище служб DSC.

## Примеры

### Пример 1. Создание файлов контрольной суммы для всех конфигураций по указанному пути

```
PS C:\> New-DscCheckSum -Path "C:\DSC\Configurations\"
```

Эта команда создает файлы контрольных сумм для всех конфигураций по пути C:\DSC\Configurations.
Все уже существующие файлы контрольных сумм пропускаются.

### Пример 2. Создание файлов контрольной суммы для всех конфигураций по указанному пути и перезапись существующих файлов контрольной суммы

```
PS C:\> New-DscCheckSum -Path "C:\DSC\Configurations\" -Force
```

Эта команда создает новые файлы контрольных сумм для всех конфигураций по пути C:\DSC\Configurations.
Указание параметра *Force* приводит к тому, что команда перезаписывает все уже существующие файлы контрольной суммы.

## PARAMETERS

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

### -Force

Указывает, что командлет перезаписывает выбранный выходной файл, если он уже существует.

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

### -Путь

Указывает путь и имя выходного файла контрольной суммы.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

Задает путь к входному файлу.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: ConfigurationPath

Required: True
Position: 0
Default value: None
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

### None

## Выходные данные

### System.Object

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Обзор Windows PowerShell Desired State Configuration](/powershell/scripting/dsc/overview/dscforengineers)

