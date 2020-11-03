---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PackageManagement
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/packagemanagement/install-packageprovider?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Install-PackageProvider
ms.openlocfilehash: 9bb2bf79aa17b139bd89281ac0967f7241414d89
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93225881"
---
# Install-PackageProvider

## Краткий обзор
Устанавливает один или несколько поставщиков пакетов Управление пакетами.

## SYNTAX

### Паккажебисеарч (по умолчанию)

```
Install-PackageProvider [-Name] <String[]> [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-Credential <PSCredential>] [-Scope <String>] [-Source <String[]>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### паккажебинпутобжект

```
Install-PackageProvider [-Scope <String>] [-InputObject] <SoftwareIdentity[]> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION

Командлет **Install-PackageProvider** устанавливает соответствующие поставщики Управление пакетами, доступные в источниках пакетов, зарегистрированных с помощью **PowerShellGet**.
По умолчанию сюда входят модули, доступные в коллекция PowerShell с тегом **PackageManagement** .
Поставщик Управление пакетами **PowerShellGet** используется для поиска поставщиков в этих репозиториях.

Этот командлет также устанавливает соответствующие поставщики Управление пакетами, доступные с помощью приложения начальной загрузки Управление пакетами.

Этот командлет также устанавливает соответствующие поставщики Управление пакетами, доступные в хранилище больших двоичных объектов Azure Управление пакетами.
Используйте поставщик загрузчика, чтобы найти и установить их.

Для первого выполнения PackageManagement требуется подключение к Интернету для загрузки поставщика пакетов NuGet.
Однако если компьютер не подключен к Интернету и необходимо использовать поставщик NuGet или PowerShellGet, его можно загрузить на другой компьютер и скопировать на целевой компьютер.
Для этого сделайте следующее.

1.
Выполните команду `Install-PackageProvider -Name NuGet -RequiredVersion 2.8.5.201 -Force` , чтобы установить поставщик с компьютера с подключением к Интернету.

2.
После установки можно найти поставщика, установленного в `$env:ProgramFiles\PackageManagement\ReferenceAssemblies\\\<ProviderName\>\\\<ProviderVersion\>` или `$env:LOCALAPPDATA\PackageManagement\ProviderAssemblies\\\<ProviderName\>\\\<ProviderVersion\>` .

3.
Поместите \<ProviderName\> папку, которая в данном случае является папкой NuGet, в соответствующее расположение на целевом компьютере.
Если целевой компьютер является Nano Server, необходимо выполнить команду **Install-PackageProvider** с Nano Server, чтобы скачать правильные двоичные файлы NuGet.

4.
Перезапустите PowerShell для автоматической загрузки поставщика пакетов.
Кроме того, можно выполнить команду, `Get-PackageProvider -ListAvailable` чтобы вывести список всех поставщиков пакетов, доступных на компьютере.
Затем используйте `Import-PackageProvider -Name NuGet -RequiredVersion 2.8.5.201` для импорта поставщика в текущий сеанс PowerShell.

## Примеры

### Пример 1. Установка поставщика пакетов из коллекция PowerShell

```
PS C:\> Install-PackageProvider -Name "Gistprovider" -Verbose
```

Эта команда устанавливает Gistprovider из коллекция PowerShell.

### Пример 2. Установка указанной версии поставщика пакетов

```
PS C:\> Find-PackageProvider -Name "Nuget" -AllVersions
PS C:\> Install-PackageProvider -Name "Nuget" -RequiredVersion "2.8.5.216" -Force
```

В этом примере устанавливается указанная версия поставщика пакетов NuGet.

Первая команда находит все версии поставщика пакетов с именем NuGet.
Вторая команда устанавливает указанную версию поставщика пакетов NuGet.

### Пример 3. Поиск поставщика и его установка

```
PS C:\> Find-PackageProvider -Name "Gistprovider" | Install-PackageProvider -Verbose
```

Эта команда использует **Find-PackageProvider** и конвейер для поиска и установки поставщика реестра.

### Пример 4. Установка поставщика в папку модуля текущего пользователя

```
PS C:\> Install-PackageProvider -Name Gistprovider -Verbose -Scope CurrentUser
```

Эта команда устанавливает поставщик пакетов в $env: LOCALAPPDATA\PackageManagement\ProviderAssemblies, чтобы только текущий пользователь мог его использовать.

## PARAMETERS

### -AllVersions

Указывает, что этот командлет устанавливает все доступные версии поставщика пакетов.
По умолчанию командлет **Install-PackageProvider** Возвращает максимальную доступную версию.

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

Указывает учетную запись пользователя, имеющую разрешение на установку поставщиков пакетов.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Указывает, что этот командлет принудительно выполняет все действия с этим командлетом, который можно принудительно применить.
Сейчас это означает, что параметр *Force* действует так же, как параметр *форцебутстрап* .

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

Указывает, что этот командлет автоматически устанавливает поставщик пакетов.

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

Указывает объект **софтвареидентити** .
Используйте командлет **Find-PackageProvider** , чтобы получить объект **софтвареидентити** для передачи в **Install-PackageProvider**.

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

### -MaximumVersion

Указывает максимально допустимую версию поставщика пакета, который требуется установить.
Если этот параметр не добавлен, командлет **Install-PackageProvider** устанавливает самую новую доступную версию поставщика.

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

Указывает минимально допустимую версию поставщика пакета, который требуется установить.
Если этот параметр не указан, командлет **Install-PackageProvider** устанавливает самую новую доступную версию пакета, которая также удовлетворяет всем требованиям, указанным в параметре *MaximumVersion* .

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

Указывает одно или несколько имен модулей поставщика пакетов.
Несколько имен пакетов следует разделять запятыми.
Подстановочные знаки не поддерживаются.

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

### Прокси-сервер

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

Указывает точную разрешенную версию поставщика пакета, который требуется установить.
Если этот параметр не указан, командлет **Install-PackageProvider** устанавливает самую новую доступную версию поставщика, которая также соответствует максимальной версии, указанной в параметре *MaximumVersion* .

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

Указывает область установки поставщика.
Допустимые значения для этого параметра: **ALLUSERS** и **CurrentUser**.

Область **ALLUSERS** устанавливает поставщиков в расположение, доступное всем пользователям компьютера.
По умолчанию это **$env:P рограмфилес\паккажеманажемент\провидерассемблиес.**

В области **CurrentUser** устанавливаются поставщики в расположении, где они доступны только текущему пользователю.
По умолчанию это **$env: локалаппдата\паккажеманажемент\провидерассемблиес.**

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: CurrentUser, AllUsers

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Source

Указывает один или несколько источников пакетов.
Используйте командлет Get-PackageSource, чтобы получить список доступных источников пакетов.

```yaml
Type: System.String[]
Parameter Sets: PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### Microsoft. PackageManagement. Packaging. Софтвареидентити

Объект **софтвареидентити** можно передать в этот командлет по конвейеру.
Используйте Find-PackageProvider, чтобы получить объект **софтвареидентити** , который можно направить в **Install-PackageProvider**.

## Выходные данные

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Find-PackageProvider](Find-PackageProvider.md)

[Get-PackageProvider](Get-PackageProvider.md)

[Import-PackageProvider](Import-PackageProvider.md)
