---
external help file: PSModule-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/03/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/uninstall-script?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Uninstall-Script
ms.openlocfilehash: e285391bdfd68211883827babbc7075e4727f06d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228250"
---
# Uninstall-Script

## Краткий обзор
Удаляет скрипт.

## SYNTAX

### NameParameterSet (по умолчанию)

```
Uninstall-Script [-Name] <String[]> [-MinimumVersion <String>] [-RequiredVersion <String>]
 [-MaximumVersion <String>] [-Force] [-AllowPrerelease] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject

```
Uninstall-Script [-InputObject] <PSObject[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Uninstall-Script`Командлет удаляет указанный скрипт с локального компьютера.

## Примеры

### Пример 1. Удаление скрипта

В этом примере удаляется скрипт.

```powershell
Uninstall-Script -Name UpdateManagement-Template
```

`Uninstall-Script` использует параметр **Name** , чтобы указать скрипт для удаления с локального компьютера.

### Пример 2. Использование конвейера для удаления сценария

В этом примере конвейер используется для удаления скрипта.

```powershell
Get-InstalledScript -Name UpdateManagement-Template | Uninstall-Script
```

`Get-InstalledScript` использует параметр **Name** для указания скрипта. Объект отправляется по конвейеру в `Uninstall-Script` и удаляется скрипт.

## PARAMETERS

### -AllowPrerelease

Позволяет удалить скрипт, помеченный как предварительная версия.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

Запрашивает подтверждение перед запуском `Uninstall-Script` .

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

Принудительное `Uninstall-Script` выполнение без запроса подтверждения пользователя.

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

### -InputObject

Принимает объект **PSRepositoryItemInfo** . Например, выходные данные переводятся `Get-InstalledScript` в переменную и используют эту переменную в качестве аргумента **InputObject** .

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -MaximumVersion

Указывает максимальную или самую новую версию скрипта для удаления. Параметры **MaximumVersion** и **RequiredVersion** нельзя использовать в одной команде.

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MinimumVersion

Указывает минимальную версию скрипта для удаления. Параметры **MinimumVersion** и **RequiredVersion** нельзя использовать в одной команде.

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Указывает массив имен скриптов для удаления.

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RequiredVersion

Указывает точный номер версии скрипта для удаления.

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WhatIf

Показывает, что произойдет при `Uninstall-Script` запуске. Командлет не выполняется.

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

### System.String[]

### System. Management. Automation. PSObject []

`Uninstall-Script` принимает объекты **PSRepositoryItemInfo** из конвейера.

### System.String

## Выходные данные

### System.Object

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Find-Script](Find-Script.md)

[Install-Script](Install-Script.md)

[Publish-Script](Publish-Script.md)

[Save-Script](Save-Script.md)

[Update-Script](Update-Script.md)
