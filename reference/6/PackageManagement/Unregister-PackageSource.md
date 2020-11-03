---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PackageManagement
ms.date: 05/24/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/unregister-packagesource?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-PackageSource
ms.openlocfilehash: 21735007c50f208c4150c02628ab1475f18fd6e3
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228049"
---
# Unregister-PackageSource

## Краткий обзор
Удаляет зарегистрированный источник пакета.

## SYNTAX

### саурцебисеарч

```
Unregister-PackageSource [[-Source] <String>] [-Location <String>] [-Credential <PSCredential>]
 [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-ProviderName <String>] [<CommonParameters>]
```

### саурцебинпутобжект

```
Unregister-PackageSource -InputObject <PackageSource[]> [-Credential <PSCredential>] [-Force]
 [-ForceBootstrap] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### NuGet: Саурцебинпутобжект

```
Unregister-PackageSource [-Credential <PSCredential>] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### NuGet: Саурцебисеарч

```
Unregister-PackageSource [-Credential <PSCredential>] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### PowerShellGet: Саурцебинпутобжект

```
Unregister-PackageSource [-Credential <PSCredential>] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

### PowerShellGet: Саурцебисеарч

```
Unregister-PackageSource [-Credential <PSCredential>] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

## DESCRIPTION

`Unregister-PackageSource`Командлет удаляет зарегистрированный источник пакета. Источники пакетов всегда управляются поставщиком пакетов. Чтобы найти источники пакетов, используйте `Get-PackageSource` командлет.

## Примеры

### Пример 1. Отмена регистрации источника пакета для поставщика NuGet

`Unregister-PackageSource`Командлет отменяет регистрацию источника пакета на локальном компьютере. Параметры **расположения** и **поставщика** можно использовать, чтобы дополнительно указать источник для удаления.

```
PS> Unregister-PackageSource -Source MyNuGet
```

`Unregister-PackageSource`Командлет использует параметр **Source** , чтобы указать источник для удаления.

### Пример 2. Отмена регистрации пакета с помощью объекта PackageSource

В этом примере `Get-PackageSource` `Unregister-PackageSource` для отмены регистрации источника пакета используются и. Объект **PackageSource** хранится в переменной.

```
PS> $pkgsource = Get-PackageSource -Name MyNuGet
PS> Unregister-PackageSource -InputObject $pkgsource
```

`$pkgsource`Переменная хранит **PackageSource** , созданные `Get-PackageSource` командлетом.
`Unregister-PackageSource` использует в `$pkgsource` качестве входных данных для параметра **InputObject** .

В качестве альтернативы `Unregister-PackageSource` командлет может указать значение для параметра **InputObject** :

`Unregister-PackageSource -InputObject ( Get-PackageSource -Name MyNuGet )`

## PARAMETERS

### -ConfigFile

Указывает файл конфигурации.

```yaml
Type: System.String
Parameter Sets: NuGet:SourceByInputObject, NuGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Указывает учетную запись пользователя, имеющую разрешение на доступ к компьютеру и выполнение команд. Введите имя пользователя, например **User01** , **Domain01\User01** , или введите объект **PSCredential** , созданный `Get-Credential` командлетом. Если ввести имя пользователя, будет предложено ввести пароль.

Если параметр **Credential** не указан, используется текущая учетная запись пользователя.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Принудительное выполнение команды без запроса на подтверждение пользователем. Переопределяет ограничения, которые препятствуют `Unregister-PackageSource` выполнению, за исключением безопасности.

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

Указывает, что `Unregister-PackageSource` заставляет **PackageManagement** автоматически удалить поставщик пакетов для указанного источника пакета.

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

Принимает входные данные конвейера, указывающие объект **PackageSource** из `Get-PackageSource` командлета. **InputObject** принимает объект **PackageSource** как `Get-PackageSource` значение или переменную, содержащую объект.

```yaml
Type: Microsoft.PackageManagement.Packaging.PackageSource[]
Parameter Sets: SourceByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### — Расположение

Задает расположение, на которое указывает источник пакета. Значением этого параметра может быть URI, путь к файлу или любой другой формат назначения, поддерживаемый поставщиком пакетов.

```yaml
Type: System.String
Parameter Sets: SourceBySearch
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
Parameter Sets: PowerShellGet:SourceByInputObject, PowerShellGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProviderName

Указывает имя поставщика.

```yaml
Type: System.String
Parameter Sets: SourceBySearch
Aliases: Provider
Accepted values: Bootstrap, NuGet, PowerShellGet

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PublishLocation

Указывает расположение публикации.

```yaml
Type: System.String
Parameter Sets: PowerShellGet:SourceByInputObject, PowerShellGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScriptPublishLocation

Указывает расположение публикации скрипта.

```yaml
Type: System.String
Parameter Sets: PowerShellGet:SourceByInputObject, PowerShellGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScriptSourceLocation

Указывает расположение источника скрипта.

```yaml
Type: System.String
Parameter Sets: PowerShellGet:SourceByInputObject, PowerShellGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Скипвалидате

Параметр, который пропускает проверку учетных данных источника пакета.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet:SourceByInputObject, NuGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Source

Указывает понятное имя источника пакета.

```yaml
Type: System.String
Parameter Sets: SourceBySearch
Aliases: Name

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

Запрашивает подтверждение перед `Unregister-PackageSource` запуском.

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

Показывает, что произойдет при `Unregister-PackageSource` запуске командлета. Командлет не выполняется.

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

### `Unregister-PackageSource` принимает объекты **PackageSource** из конвейера в качестве входных данных.

## Выходные данные

### `Unregister-PackageSource` не создает никаких выходных данных.

## ПРИМЕЧАНИЯ

Включение поставщика пакетов в команду может сделать динамические параметры доступными для командлета. Динамические параметры относятся к поставщику пакетов. `Get-Help`Командлет перечисляет наборы параметров командлета и включает набор параметров поставщика.

## Связанные ссылки

[about_PackageManagement](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[Get-Credential](../Microsoft.PowerShell.Security/Get-Credential.md)

[Get-PackageSource](Get-PackageSource.md)

[Register-PackageSource](Register-PackageSource.md)

[Set-PackageSource](Set-PackageSource.md)
