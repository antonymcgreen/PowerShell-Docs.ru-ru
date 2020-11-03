---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PackageManagement
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/packagemanagement/find-packageprovider?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-PackageProvider
ms.openlocfilehash: 96e8829b6939c40c85fb924ae65d73f48d2e475b
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93225902"
---
# Find-PackageProvider

## Краткий обзор
Возвращает список поставщиков пакетов Управление пакетами, доступных для установки.

## SYNTAX

```
Find-PackageProvider [[-Name] <String[]>] [-AllVersions] [-Source <String[]>] [-IncludeDependencies]
 [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-RequiredVersion <String>]
 [-MinimumVersion <String>] [-MaximumVersion <String>] [-Force] [-ForceBootstrap] [<CommonParameters>]
```

## DESCRIPTION

Командлет **Find-PackageProvider** находит соответствующие поставщики PackageManagement, доступные в источниках пакетов, зарегистрированных с помощью PowerShellGet.
Эти поставщики пакетов можно установить с помощью командлета Install-PackageProvider.
По умолчанию сюда входят модули, доступные в коллекция PowerShell с тегами **PackageManagement** и **provider** .

**Find-PackageProvider** также находит соответствующие поставщики Управление пакетами, доступные в хранилище больших двоичных объектов Azure Управление пакетами.
Используйте поставщик загрузчика, чтобы найти и установить их.

## Примеры

### Пример 1. Поиск всех доступных поставщиков пакетов

```
PS C:\> Find-PackageProvider
```

Эта команда возвращает список всех поставщиков пакетов, доступных в репозиториях, поддерживаемых Управление пакетами.
По умолчанию эти поставщики пакетов доступны на коллекция PowerShell и с помощью приложения начальной загрузки Управление пакетами.

### Пример 2. Поиск всех версий поставщика

```
PS C:\> Find-PackageProvider -Name "Nuget" -AllVersions
```

Эта команда находит все версии поставщика пакетов с именем NuGet.

### Пример 3. Поиск поставщика из указанного источника

```
PS C:\> Find-PackageProvider -Name "Gistprovider" -Source "PSGallery"
```

Эта команда находит поставщик пакетов, доступный с помощью указанного источника пакета.

## PARAMETERS

### -AllVersions

Указывает, что этот командлет возвращает все доступные версии поставщика пакетов.
По умолчанию командлет **Find-PackageProvider** возвращает только последнюю доступную версию.

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

### -Credential

Указывает учетную запись пользователя, имеющую разрешение на поиск поставщиков пакетов.

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

Принудительное выполнение команды без запроса на подтверждение пользователем.
В настоящее время это эквивалентно параметру *форцебутстрап* .

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

### -IncludeDependencies

Указывает, что этот командлет включает зависимости.

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

Указывает максимально допустимую версию поставщика пакетов, которую необходимо найти.
Если этот параметр не добавлен, командлет **Find-PackageProvider** находит самую новую доступную версию поставщика.

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

Указывает минимально допустимую версию поставщика пакетов, которую необходимо найти.
Если этот параметр не указан, командлет **Find-PackageProvider** находит самую новую доступную версию пакета, которая также соответствует максимальной заданной версии, заданной параметром *MaximumVersion* .

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

Указывает одно или несколько имен модулей поставщика пакетов или имена поставщиков с подстановочными знаками.
Несколько имен пакетов следует разделять запятыми.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### Прокси-сервер

Указывает прокси-сервер для запроса, а не напрямуюе подключение к Интернет-ресурсу.

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProxyCredential

Указывает учетную запись пользователя, имеющую разрешение на использование прокси-сервера, который задается параметром **Proxy**.

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

### -RequiredVersion

Указывает точную разрешенную версию поставщика пакета, который требуется найти.
Если этот параметр не указан, командлет **Find-PackageProvider** находит самую новую доступную версию поставщика, которая также соответствует максимальной версии, указанной в параметре *MaximumVersion* .

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

### -Source

Указывает один или несколько источников пакетов.
Список доступных источников пакетов можно получить с помощью командлета Get-PackageSource.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

## Выходные данные

### Microsoft. PackageManagement. Packaging. Софтвареидентити

Этот командлет возвращает объект **софтвареидентити** .
Объект **софтвареидентити** можно передать в командлет **Install-PackageProvider** , чтобы установить результаты командлета **Find-PackageProvider**.

## ПРИМЕЧАНИЯ

## Связанные ссылки

[about_PackageManagement](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[Unregister-PackageSource](Unregister-PackageSource.md)

[Get-PackageSource](Get-PackageSource.md)

[Register-PackageSource](Register-PackageSource.md)

[Install-PackageProvider](Install-PackageProvider.md)
