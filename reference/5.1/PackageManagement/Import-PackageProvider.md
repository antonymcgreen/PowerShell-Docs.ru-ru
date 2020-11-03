---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PackageManagement
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/packagemanagement/import-packageprovider?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-PackageProvider
ms.openlocfilehash: 1ff00ea134c442e2bdb926d12ebbfa02098d6104
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227306"
---
# Import-PackageProvider

## Краткий обзор
Добавляет поставщики пакетов Управление пакетами в текущий сеанс.

## SYNTAX

```
Import-PackageProvider [-Name] <String[]> [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-Force] [-ForceBootstrap] [<CommonParameters>]
```

## DESCRIPTION

`Import-PackageProvider`Командлет добавляет один или несколько поставщиков пакетов в текущий сеанс.
Импортируемый поставщик должен быть установлен на локальном компьютере.

Чтобы получить список доступных поставщиков, выполните команду `Get-PackageProvider -ListAvailable` .
Обратите внимание, что имя поставщика пакета может отличаться от имени модуля.

Из соображений безопасности **PackageManagement** требует, чтобы поставщики на основе C# содержали `provider.manifest` . Дополнительные сведения о создании поставщика с `provider.manifest` внедренным см. в разделе `.csproj` файлы проекта в [https://github.com/oneget/oneget](https://github.com/oneget/oneget) .

## Примеры

### Пример 1. Импорт поставщика пакетов с локального компьютера

```powershell
PS C:\> Import-PackageProvider -Name "Nuget"
```

Эта команда импортирует поставщик NuGet после установки на локальном компьютере.

### Пример 2. импорт определенной версии поставщика пакетов

```powershell
PS C:\> Find-PackageProvider -Name "Nuget" -AllVersions
Install-PackageProvider -Name "Nuget" -RequiredVersion "2.8.5.201" -Force
Get-PackageProvider -ListAvailable
Import-PackageProvider -Name "Nuget" -RequiredVersion "2.8.5.201" -Verbose
```

Эта команда находит, устанавливает и импортирует определенную версию поставщика пакетов NuGet.

## PARAMETERS

### -Force

Принудительное выполнение команды без запроса на подтверждение пользователем.
Повторно импортирует поставщик пакетов.

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

Указывает, что этот командлет заставляет систему управления пакетами автоматически установить поставщик пакетов.

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

### -MaximumVersion

Указывает максимально допустимую версию поставщика пакета, который требуется импортировать. Если этот параметр не добавлен, `Import-PackageProvider` импортирует самую новую доступную версию поставщика.

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

### -MinimumVersion

Указывает минимально допустимую версию поставщика пакета, который требуется импортировать. Если этот параметр не добавлен, `Import-PackageProvider` импортирует самую новую доступную версию пакета, которая также соответствует любой максимальной версии, указанной с помощью параметра *MaximumVersion* .

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

Указывает одно или несколько имен поставщиков пакетов. Использовать подстановочные знаки запрещено.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RequiredVersion

Указывает точную версию поставщика пакета, который требуется импортировать. Если этот параметр не добавлен, `Import-PackageProvider` импортирует самую новую доступную версию поставщика, которая также соответствует максимальной версии, указанной в параметре **MaximumVersion** .

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

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Microsoft. PackageManagement. Реализация. PackageProvider

Объект **PackageProvider** , возвращаемый, можно передать `Get-PackageProvider` в `Import-PackageProvider` .

## Выходные данные

## ПРИМЕЧАНИЯ

## Связанные ссылки

[about_PackageManagement](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[Unregister-PackageSource](Unregister-PackageSource.md)

[Get-PackageSource](Get-PackageSource.md)

[Register-PackageSource](Register-PackageSource.md)

[Get-PackageProvider](Get-PackageProvider.md)
