---
external help file: PSModule-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/03/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/find-command?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-Command
ms.openlocfilehash: 824e5b0012f8cf8394252704d0e16e49b3f7fa39
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "94892694"
---
# Find-Command

## Краткий обзор
Ищет команды PowerShell в модулях.

## SYNTAX

### Все

```
Find-Command [[-Name] <String[]>] [-ModuleName <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-RequiredVersion <String>] [-AllVersions] [-AllowPrerelease]
 [-Tag <String[]>] [-Filter <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-Repository <String[]>] [<CommonParameters>]
```

## DESCRIPTION

`Find-Command`Командлет находит команды PowerShell, такие как командлеты, псевдонимы, функции и рабочие процессы. `Find-Command` Поиск модулей в зарегистрированных репозиториях.

Для каждой команды, найденной в `Find-Command` , возвращается объект **PSGetCommandInfo** . Объект **PSGetCommandInfo** может быть отправлен в командлет по конвейеру `Install-Module` .
`Install-Module` устанавливает модуль, содержащий команду.

## Примеры

### Пример 1. Поиск всех команд в указанном репозитории

`Find-Command`Командлет выполняет поиск модулей в зарегистрированном репозитории.

```powershell
Find-Command -Repository PSGallery | Select-Object -First 10
```

```output
Name                                Version    ModuleName          Repository
----                                -------    ----------          ----------
Disable-AzureRmDataCollection       5.8.3      AzureRM.profile     PSGallery
Disable-AzureRmContextAutosave      5.8.3      AzureRM.profile     PSGallery
Enable-AzureRmDataCollection        5.8.3      AzureRM.profile     PSGallery
Enable-AzureRmContextAutosave       5.8.3      AzureRM.profile     PSGallery
Remove-AzureRmEnvironment           5.8.3      AzureRM.profile     PSGallery
Get-AzureRmEnvironment              5.8.3      AzureRM.profile     PSGallery
Set-AzureRmEnvironment              5.8.3      AzureRM.profile     PSGallery
Add-AzureRmEnvironment              5.8.3      AzureRM.profile     PSGallery
Get-AzureRmSubscription             5.8.3      AzureRM.profile     PSGallery
Connect-AzureRmAccount              5.8.3      AzureRM.profile     PSGallery
```

`Find-Command` использует параметр **репозитория** для указания имени зарегистрированного репозитория. Объекты отправляются по конвейеру. `Select-Object` Получает объекты и использует **первый** параметр для вывода первых 10 результатов.

### Пример 2. Поиск команды по имени

`Find-Command` может использовать имя команды для нахождение модуля в репозитории. Возможно, имя команды существует в нескольких **модуленамес**.

```powershell
Find-Command -Repository PSGallery -Name Get-TargetResource
```

```Output
Name                  Version    ModuleName                      Repository
----                  -------    ----------                      ----------
Get-TargetResource    3.1.0.0    xPowerShellExecutionPolicy      PSGallery
Get-TargetResource    1.0.0      xInternetExplorerHomePage       PSGallery
Get-TargetResource    1.2.0.0    SystemLocaleDsc                 PSGallery
```

`Find-Command` использует параметр **репозитория** для поиска в **PSGallery**. Параметр **Name** указывает команду **Get-TargetResource**.

### Пример 3. Поиск команд по имени и установка модуля

`Find-Command` может разместить команду и модуль, а затем отправить объект в `Install-Module` . Если команда включена в несколько модулей, используйте `Find-Command` параметр **module-name модуля** командлетов.
В противном случае могут быть установлены модули, которые не нужно устанавливать.

```powershell
PS> Find-Command -Name Get-TargetResource -Repository PSGallery -ModuleName SystemLocaleDsc |
    Install-Module

PS> Get-InstalledModule

Version   Name               Repository   Description
-------   ----               ----------   -----------
1.2.0.0   SystemLocaleDsc    PSGallery    This DSC Resource allows configuration of the Windows...
```

`Find-Command` использует параметр **Name** для указания команды **Get-TargetResource**. Параметр **репозитория** выполняет поиск в **PSGallery**. Параметр **ModuleName** указывает модуль, который необходимо установить, **системлокаледск**. Объект отправляется по конвейеру в `Install-Module` и устанавливается модуль. После завершения установки можно использовать `Get-InstalledModule` для вывода результатов.

### Пример 4. Поиск команды и сохранение ее модуля

```
PS> Find-Command -Name Invoke-ScriptAnalyzer -Repository PSGallery | Save-Module -Path C:\Test\Modules -Verbose

VERBOSE: Downloading 'https://www.powershellgallery.com/api/v2/package/PSScriptAnalyzer/1.18.0'.
VERBOSE: Completed downloading 'https://www.powershellgallery.com/api/v2/package/PSScriptAnalyzer/1.18.0'.
VERBOSE: Completed downloading 'PSScriptAnalyzer'.
VERBOSE: Module 'PSScriptAnalyzer' was saved successfully to path 'C:\Test\Modules\PSScriptAnalyzer\1.18.0'.
```

`Find-Command` использует параметры **имени** и **репозитория** для поиска команды **Invoke-ScriptAnalyzer** в репозитории **PSGallery** . Объект отправляется по конвейеру в `Save-Module` . Параметр **path** определяет расположение для сохранения модуля. **Verbose** является необязательным параметром, но отображает выходные данные состояния в консоли PowerShell. Подробные выходные данные полезны для устранения неполадок.

## PARAMETERS

### -AllowPrerelease

Включает модули, помеченные как предварительные версии в результатах.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllVersions

Указывает, что этот командлет получает все версии модуля.

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

### -Filter

Находит модули на основе синтаксиса поиска поставщика **PackageManagement** . Например, укажите слова для поиска в свойствах **ModuleName** и **Description** .

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

### -MaximumVersion

Указывает максимальную версию модуля для включения в результаты. Параметры **MaximumVersion** и **RequiredVersion** нельзя использовать в одной команде.

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

Указывает минимальную версию модуля для включения в результаты. Параметры **MinimumVersion** и **RequiredVersion** нельзя использовать в одной команде.

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

### -ModuleName

Указывает имя модуля для поиска команд. По умолчанию все модули.

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

Указывает имя команды для поиска в репозитории. Используйте запятые для разделения массива имен команд.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Прокси-сервер

Указывает прокси-сервер для запроса, а не прямое подключение к Интернету.

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### — Репозиторий;

Указывает репозиторий для поиска команд. Используйте запятые для разделения массива имен репозитория. Значение по умолчанию — все репозитории.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequiredVersion

Указывает версию модуля для включения в результаты.

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

### -Tag

Указывает теги, которые классифицируют модули в репозитории. Используйте запятые для разделения массива тегов.

```yaml
Type: System.String[]
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

## Выходные данные

### PSGetCommandInfo

`Find-Command` выводит объект **PSGetCommandInfo** .

## ПРИМЕЧАНИЯ

> [!IMPORTANT]
> По состоянию на апрель 2020 коллекция PowerShell больше не поддерживает TLS-версии 1,0 и 1,1. Если вы не используете TLS 1,2 или более поздней версии, при попытке доступа к коллекция PowerShell возникает ошибка. Используйте следующую команду, чтобы убедиться, что используется TLS 1,2:
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> Дополнительные сведения см. в [объявлении](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) в блоге PowerShell.

## Связанные ссылки

[Get-InstalledModule](Get-InstalledModule.md)

[Install-Module](Install-Module.md)

[Save-Module](Save-Module.md)

[Select-Object](../Microsoft.PowerShell.Utility/Select-Object.md)

[Uninstall — Module](Uninstall-Module.md)
