---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PackageManagement
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/packagemanagement/install-packageprovider?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Install-PackageProvider
ms.openlocfilehash: 8ab8a0fd505bca7cda5cef17a09baa9f7e571dd4
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "94892803"
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

`Install-PackageProvider`Командлет устанавливает соответствующие поставщики Управление пакетами, доступные в источниках пакетов, зарегистрированных с помощью **PowerShellGet**. По умолчанию сюда входят модули, доступные в коллекция PowerShell Windows с тегом **PackageManagement** . Поставщик Управление пакетами **PowerShellGet** используется для поиска поставщиков в этих репозиториях.

Этот командлет также устанавливает соответствующие поставщики Управление пакетами, доступные с помощью приложения начальной загрузки Управление пакетами.

Этот командлет также устанавливает соответствующие поставщики Управление пакетами, доступные в хранилище больших двоичных объектов Azure Управление пакетами. Используйте поставщик загрузчика, чтобы найти и установить их.

Для первого выполнения PackageManagement требуется подключение к Интернету для загрузки поставщика пакетов NuGet. Однако если компьютер не подключен к Интернету и необходимо использовать поставщик NuGet или PowerShellGet, его можно загрузить на другой компьютер и скопировать на целевой компьютер. Для этого сделайте следующее.

1. Выполните команду `Install-PackageProvider -Name NuGet -RequiredVersion 2.8.5.201 -Force` , чтобы установить поставщик с компьютера с подключением к Интернету.
1. После установки можно найти поставщика, установленного в `$env:ProgramFiles\PackageManagement\ReferenceAssemblies\<ProviderName>\<ProviderVersion>` или `$env:LOCALAPPDATA\PackageManagement\ProviderAssemblies\<ProviderName>\<ProviderVersion>` .
1. Поместите `<ProviderName>` папку, которая в данном случае является папкой NuGet, в соответствующее расположение на целевом компьютере. Если целевой компьютер является Nano Server, необходимо запустить `Install-PackageProvider` с Nano Server, чтобы скачать правильные двоичные файлы NuGet.
1. Перезапустите PowerShell для автоматической загрузки поставщика пакетов. Кроме того, можно выполнить команду, `Get-PackageProvider -ListAvailable` чтобы вывести список всех поставщиков пакетов, доступных на компьютере.
   Затем используйте `Import-PackageProvider -Name NuGet -RequiredVersion 2.8.5.201` для импорта поставщика в текущий сеанс Windows PowerShell.

## Примеры

### Пример 1. Установка поставщика пакетов из коллекция PowerShell

Эта команда устанавливает поставщик пакетов GistProvider из коллекция PowerShell.

```powershell
Install-PackageProvider -Name "GistProvider" -Verbose
```

### Пример 2. Установка указанной версии поставщика пакетов

В этом примере устанавливается указанная версия поставщика пакетов NuGet.

Первая команда находит все версии поставщика пакетов с именем NuGet.
Вторая команда устанавливает указанную версию поставщика пакетов NuGet.

```powershell
Find-PackageProvider -Name "NuGet" -AllVersions
Install-PackageProvider -Name "NuGet" -RequiredVersion "2.8.5.216" -Force
```

### Пример 3. Поиск поставщика и его установка

В этом примере используется `Find-PackageProvider` и конвейер для поиска поставщика и его установки.

```powershell
Find-PackageProvider -Name "GistProvider" | Install-PackageProvider -Verbose
```

### Пример 4. Установка поставщика в папку модуля текущего пользователя

Эта команда устанавливает поставщик пакетов, чтобы `$env:LOCALAPPDATA\PackageManagement\ProviderAssemblies` только текущий пользователь мог его использовать.

```powershell
Install-PackageProvider -Name GistProvider -Verbose -Scope CurrentUser
```

## PARAMETERS

### -AllVersions

Указывает, что этот командлет устанавливает все доступные версии поставщика пакетов. По умолчанию `Install-PackageProvider` возвращает только самую новую доступную версию.

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

Указывает, что этот командлет принудительно выполняет все действия с этим командлетом, который можно принудительно применить. Сейчас это означает, что параметр **Force** действует так же, как параметр **форцебутстрап** .

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

Указывает объект **софтвареидентити** . Используйте `Find-PackageProvider` командлет, чтобы получить объект **софтвареидентити** для передачи в `Install-PackageProvider` .

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

Указывает максимально допустимую версию поставщика пакета, который требуется установить. Если этот параметр не добавлен, `Install-PackageProvider` устанавливает самую новую доступную версию поставщика.

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

Указывает минимально допустимую версию поставщика пакета, который требуется установить. Если этот параметр не добавлен, `Install-PackageProvider` устанавливает самую новую версию пакета, которая также удовлетворяет всем требованиям, указанным в параметре *MaximumVersion* .

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

Указывает одно или несколько имен модулей поставщика пакетов. Несколько имен пакетов следует разделять запятыми.
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

Указывает точную разрешенную версию поставщика пакета, который требуется установить. Если этот параметр не добавлен, `Install-PackageProvider` устанавливает самую новую доступную версию поставщика, которая также соответствует максимальной версии, заданной параметром **MaximumVersion** .

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

Указывает область установки поставщика. Допустимые значения для этого параметра:

- **ALLUSERS** — устанавливает поставщиков в расположение, доступное всем пользователям компьютера.
  По умолчанию это **$env:P рограмфилес\паккажеманажемент\провидерассемблиес.**

- **CurrentUser** — устанавливает поставщики в расположении, где они доступны только текущему пользователю. По умолчанию это **$env: локалаппдата\паккажеманажемент\провидерассемблиес.**

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

Указывает один или несколько источников пакетов. Используйте `Get-PackageSource` командлет, чтобы получить список доступных источников пакетов.

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

Показывает, что произойдет при запуске командлета. Командлет не выполняется.

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

Объект **софтвареидентити** можно передать в этот командлет по конвейеру. Используйте `Find-PackageProvider` для получения объекта **софтвареидентити** , в который можно направить `Install-PackageProvider` .

## Выходные данные

## ПРИМЕЧАНИЯ

> [!IMPORTANT]
> По состоянию на апрель 2020 коллекция PowerShell больше не поддерживает TLS-версии 1,0 и 1,1. Если вы не используете TLS 1,2 или более поздней версии, при попытке доступа к коллекция PowerShell возникает ошибка. Используйте следующую команду, чтобы убедиться, что используется TLS 1,2:
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> Дополнительные сведения см. в [объявлении](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) в блоге PowerShell.

## Связанные ссылки

[Find-PackageProvider](Find-PackageProvider.md)

[Get-PackageProvider](Get-PackageProvider.md)

[Import-PackageProvider](Import-PackageProvider.md)
