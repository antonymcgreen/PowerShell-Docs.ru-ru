---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PackageManagement
ms.date: 03/29/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/get-packagesource?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PackageSource
ms.openlocfilehash: 77e5ba9954b70c053541648b5d8d2bd8e7237f75
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227313"
---
# Get-PackageSource

## Краткий обзор
Возвращает список источников пакетов, зарегистрированных для поставщика пакетов.

## SYNTAX

### NuGet

```
Get-PackageSource [[-Name] <String>] [-Location <String>] [-Force] [-ForceBootstrap]
 [-ProviderName <String[]>] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### PowerShellGet

```
Get-PackageSource [[-Name] <String>] [-Location <String>] [-Force] [-ForceBootstrap]
 [-ProviderName <String[]>] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

## DESCRIPTION

`Get-PackageSource`Командлет возвращает список источников пакетов, зарегистрированных с помощью **PackageManagement** , на локальном компьютере. При указании поставщика пакетов `Get-PackageSource` получает только те источники, которые связаны с указанным поставщиком. В противном случае команда возвращает все источники пакетов, зарегистрированные с помощью **PackageManagement**.

## Примеры

### Пример 1. получение всех источников пакетов

`Get-PackageSource`Командлет возвращает все источники пакетов, зарегистрированные с помощью **PackageManagement** , на локальном компьютере.

```powershell
Get-PackageSource
```

```Output
Name                 ProviderName     IsTrusted  Location
----                 ------------     ---------  --------
LocalPackages        NuGet            False      C:\LocalPkg\
MyNuget              NuGet            False      https://www.nuget.org/api/v2
PSGallery            PowerShellGet    False      https://www.powershellgallery.com/api/v2
```

### Пример 2. получение всех источников пакетов для конкретного поставщика

Эта команда получает источники пакетов, которые зарегистрированы для конкретного поставщика.

```powershell
Get-PackageSource -ProviderName NuGet
```

```Output
Name                 ProviderName     IsTrusted  Location
----                 ------------     ---------  --------
LocalPackages        NuGet            False      C:\LocalPkg\
MyNuget              NuGet            False      https://www.nuget.org/api/v2
```

`Get-PackageSource` использует параметр **providerName** для получения источников пакетов, зарегистрированных для поставщика **NuGet** .

### Пример 3. получение источников из поставщика пакетов

Эта команда использует поставщик пакетов для получения источников пакетов.

```powershell
Get-PackageProvider -Name NuGet | Get-PackageSource
```

```Output
Name                 ProviderName     IsTrusted  Location
----                 ------------     ---------  --------
LocalPackages        NuGet            False      C:\LocalPkg\
MyNuget              NuGet            False      https://www.nuget.org/api/v2
```

`Get-PackageProvider` использует параметр **Name** , чтобы указать имя поставщика, **NuGet**. Объект отправляется по конвейеру в `Get-PackageSource` .

## PARAMETERS

### -ConfigFile

Указывает файл конфигурации.

```yaml
Type: System.String
Parameter Sets: NuGet
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

Указывает, что этот командлет заставляет службу **PackageManagement** автоматически установить поставщик пакетов.

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

### — Расположение

Указывает расположение источника или репозитория управления пакетами.

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

### -Name

Указывает имя источника управления пакетами.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PackageManagementProvider

Указывает поставщика управления пакетами.

```yaml
Type: System.String
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProviderName

Указывает одно или несколько имен поставщиков пакетов. Несколько имен поставщиков пакетов следует разделять запятыми.
Используйте `Get-PackageProvider` для получения списка доступных поставщиков пакетов.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Provider
Accepted values: Bootstrap, NuGet, PowerShellGet

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PublishLocation

Указывает расположение публикации для источника пакета.

```yaml
Type: System.String
Parameter Sets: PowerShellGet
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
Parameter Sets: PowerShellGet
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
Parameter Sets: PowerShellGet
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
Parameter Sets: NuGet
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

### PackageSource []

Указывает один или несколько источников пакетов.

## ПРИМЕЧАНИЯ

## Связанные ссылки

[about_PackageManagement](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[Find-Package](Find-Package.md)

[Get-Package](Get-Package.md)

[Get-PackageProvider](Get-PackageProvider.md)

[Register-PackageSource](Register-PackageSource.md)

[Set-PackageSource](Set-PackageSource.md)

[Unregister-PackageSource](Unregister-PackageSource.md)
