---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PackageManagement
ms.date: 05/24/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/uninstall-package?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Uninstall-Package
ms.openlocfilehash: 4be80765181e045f24b1f90243de21f38533bfba
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228069"
---
# Uninstall-Package

## Краткий обзор
Удаляет один или несколько пакетов программного обеспечения.

## SYNTAX

### паккажебинпутобжект

```
Uninstall-Package [-InputObject] <SoftwareIdentity[]> [-AllVersions] [-Force] [-ForceBootstrap]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### паккажебисеарч

```
Uninstall-Package [-Name] <String[]> [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-ProviderName <String[]>] [<CommonParameters>]
```

### NuGet: Паккажебинпутобжект

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-Destination <String>] [-ExcludeVersion] [-Scope <String>] [-SkipDependencies]
 [<CommonParameters>]
```

### NuGet: Паккажебисеарч

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-Destination <String>] [-ExcludeVersion] [-Scope <String>] [-SkipDependencies]
 [<CommonParameters>]
```

### PowerShellGet: Паккажебинпутобжект

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-Scope <String>]
 [-PackageManagementProvider <String>] [-Type <String>] [-AllowClobber] [-SkipPublisherCheck]
 [-InstallUpdate] [-NoPathUpdate] [-AllowPrereleaseVersions] [<CommonParameters>]
```

### PowerShellGet: Паккажебисеарч

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-Scope <String>]
 [-PackageManagementProvider <String>] [-Type <String>] [-AllowClobber] [-SkipPublisherCheck]
 [-InstallUpdate] [-NoPathUpdate] [-AllowPrereleaseVersions] [<CommonParameters>]
```

## DESCRIPTION

`Uninstall-Package`Командлет удаляет один или несколько пакетов программного обеспечения с локального компьютера. Чтобы найти установленные пакеты, используйте `Get-Package` командлет.

## Примеры

### Пример 1. Удаление пакета

`Uninstall-Package`Командлет удаляет пакеты. Параметр **Name** указывает пакет для удаления. При установке нескольких версий пакета удаляется последняя версия.

```
PS> Uninstall-Package -Name NuGet.Core
```

### Пример 2. Использование конвейера для удаления пакета

`Get-Package` находит конкретный пакет и отправляет объект **софтвареидентити** по конвейеру в `Uninsall-Package` командлет.

```
PS> Get-Package -Name NuGet.Core -RequiredVersion 2.14.0 | Uninstall-Package
```

`Get-Package`Для указания пакета командлет использует параметры **Name** и **RequiredVersion** .
Объект **софтвареидентити** отправляется вниз по конвейеру. `Uninstall-Package`Командлет получает объект в качестве **InputObject** и удаляет пакет.

В качестве альтернативы `Uninstall-Package` командлет может указать значение для параметра **InputObject** :

`Uninstall-Package -InputObject ( Get-Package -Name NuGet.Core -RequiredVersion 2.14.0 )`

## PARAMETERS

### -AllowClobber

Переопределяет предупреждающие сообщения о конфликтах с существующими командами. Перезаписывает существующие команды, имена которых совпадают с именами устанавливаемых команд.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Алловпререлеасеверсионс

Позволяет удалять пакеты, помеченные как предварительные.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllVersions

Указывает, что этот командлет удаляет все версии пакета.

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

### -Destination

Задает строку пути к входному объекту.

```yaml
Type: System.String
Parameter Sets: NuGet:PackageByInputObject, NuGet:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Ексклудеверсион

Переключитесь, чтобы исключить номер версии из пути к папке.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet:PackageByInputObject, NuGet:PackageBySearch
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

### -ForceBootstrap

Заставляет службу **PackageManagement** автоматически устанавливать поставщик пакетов для указанного пакета.

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

Принимает входные данные конвейера, указывающие объект пакета **софтвареидентити** из `Get-Package` командлета. **InputObject** принимает объект **софтвареидентити** как `Get-Package` значение или переменную, содержащую объект.

```yaml
Type: Microsoft.PackageManagement.Packaging.SoftwareIdentity[]
Parameter Sets: PackageByInputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Инсталлупдате

Указывает, что `Uninstall-Package` удаляет обновления.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumVersion

Указывает максимально допустимую версию пакета, которую требуется удалить. Если этот параметр не указан, `Uninstall-Package` удаляется последняя версия пакета.

```yaml
Type: System.String
Parameter Sets: PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinimumVersion

Указывает минимальную допустимую версию пакета, которую необходимо удалить. Если вы не добавите этот параметр, `Uninstall-Package` удаляет последнюю версию пакета, соответствующую любой версии, указанной параметром **MaximumVersion** .

```yaml
Type: System.String
Parameter Sets: PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Указывает одно или несколько имен пакетов. Несколько имен пакетов должны быть разделены запятыми.

```yaml
Type: System.String[]
Parameter Sets: PackageBySearch
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoPathUpdate

**NoPathUpdate** применяется только к `Install-Script` командлету. **NoPathUpdate** — это динамический параметр, добавленный поставщиком и не поддерживаемый `Uninstall-Package` .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PackageManagementProvider

Указывает поставщика **PackageManagement** .

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProviderName

Указывает одно или несколько имен поставщиков пакетов для поиска пакетов. Чтобы получить имена поставщиков пакетов, выполните командлет `Get-PackageProvider`.

```yaml
Type: System.String[]
Parameter Sets: PackageBySearch
Aliases: Provider
Accepted values: Bootstrap, NuGet, PowerShellGet

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RequiredVersion

Указывает точную допустимую версию пакета, который требуется удалить. Если вы не добавите этот параметр, `Uninstall-Package` удаляет последнюю версию пакета, соответствующую любой версии, указанной параметром **MaximumVersion** .

```yaml
Type: System.String
Parameter Sets: PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scope

Указывает область, для которой необходимо удалить пакет. Для этого параметра допустимы следующие значения:

- CurrentUser
- AllUsers

```yaml
Type: System.String
Parameter Sets: NuGet:PackageByInputObject, NuGet:PackageBySearch, PowerShellGet:PackageByInputObject, PowerShellGet:PackageBySearch
Aliases:
Accepted values: CurrentUser, AllUsers

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -СкипдепенденЦиес

Пропускает удаление зависимостей программного обеспечения.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet:PackageByInputObject, NuGet:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Скиппублишерчекк

Позволяет получить версию пакета, более новую по сравнению с установленной версией. Например, установленный пакет с цифровой подписью доверенного издателя, но новая версия не подписана цифровой подписью.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Type

Указывает, следует ли выполнять поиск пакетов с помощью модуля, скрипта или и того, и другого. Для этого параметра допустимы следующие значения:

- Модуль
- Скрипт
- Все

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet:PackageBySearch
Aliases:
Accepted values: Module, Script, All

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

Показывает, что произойдет при `Uninstall-Package` запуске командлета. Командлет не выполняется.

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

### `Uninstall-Package` принимает объекты **софтвареидентити** из конвейера в качестве входных данных.

## Выходные данные

### `Uninstall-Package` не создает никаких выходных данных.

## ПРИМЕЧАНИЯ

Включение поставщика пакетов в команду может сделать динамические параметры доступными для командлета. Динамические параметры относятся к поставщику пакетов. `Get-Help`Командлет перечисляет наборы параметров командлета и включает набор параметров поставщика. Например, `Uninstall-Package` имеет набор параметров **PowerShellGet** , включающий `-NoPathUpdate` , `AllowClobber` и `SkipPublisherCheck` .

## Связанные ссылки

[about_PackageManagement](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[Find-Package](Find-Package.md)

[Get-Package](Get-Package.md)

[Install-Package](Install-Package.md)

[Save-Package](Save-Package.md)
