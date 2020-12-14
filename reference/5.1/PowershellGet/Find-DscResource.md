---
external help file: PSModule-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/04/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/find-dscresource?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-DscResource
ms.openlocfilehash: 39896c4f48d6cd8809d4a680e776d36deb65b0d8
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "94889867"
---
# Find-DscResource

## Краткий обзор
Находит ресурсы настройки требуемого состояния (DSC).

## SYNTAX

### Все

```
Find-DscResource [[-Name] <String[]>] [-ModuleName <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-RequiredVersion <String>] [-AllVersions] [-AllowPrerelease]
 [-Tag <String[]>] [-Filter <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-Repository <String[]>] [<CommonParameters>]
```

## DESCRIPTION

`Find-DscResource`Командлет ищет зарегистрированные репозитории для поиска ресурсов DSC, содержащихся в модулях. По умолчанию `Find-DscResource` Поиск выполняется по всем зарегистрированным репозиториям.

Для каждого модуля, найденного `Find-DscResource` , возвращается объект **псжетдскресаурцеинфо** .
Объекты **псжетдскресаурцеинфо** можно отсылать по конвейеру в `Install-Module` командлет.
`Install-Module` устанавливает модуль.

## Примеры

### Пример 1. Поиск всех ресурсов DSC

`Find-DscResource` Возвращает ресурсы DSC из зарегистрированных репозиториев. Для поиска в определенном репозитории используйте параметр **репозитория** .

```powershell
Find-DscResource
```

```Output
Name                           Version    ModuleName                     Repository
----                           -------    ----------                     ----------
Carbon_Privilege               2.8.1      Carbon                         PSGallery
Carbon_ScheduledTask           2.8.1      Carbon                         PSGallery
Carbon_Service                 2.8.1      Carbon                         PSGallery
PackageManagement              1.4        PackageManagement              PSGallery
PackageManagementSource        1.4        PackageManagement              PSGallery
PSModule                       2.1.4      PowerShellGet                  PSGallery
PSRepository                   2.1.4      PowerShellGet                  PSGallery
xArchive                       8.7.0.0    xPSDesiredStateConfiguration   PSGallery
xDSCWebService                 8.7.0.0    xPSDesiredStateConfiguration   PSGallery
xEnvironment                   8.7.0.0    xPSDesiredStateConfiguration   PSGallery
```

### Пример 2. поиск ресурса DSC по имени

`Find-DscResource` находит ресурсы DSC по имени. Используйте запятые для разделения массива имен ресурсов.

```powershell
Find-DscResource -Name xWebsite, xWebApplication, xWebSiteDefaults
```

```Output
Name               Version    ModuleName            Repository
----               -------    ----------            ----------
xWebApplication    2.6.0.0    xWebAdministration    PSGallery
xWebsite           2.6.0.0    xWebAdministration    PSGallery
xWebSiteDefaults   2.6.0.0    xWebAdministration    PSGallery
```

`Find-DscResource` использует параметр **Name** для поиска указанного массива ресурсов DSC.

### Пример 3. поиск ресурса DSC и его установка

`Find-DscResource` находит ресурс DSC и отправляет объект по конвейеру, который необходимо установить.
После установки используйте `Get-InstalledModule` для просмотра результатов.

Несколько ресурсов из одного модуля можно отсылать по конвейеру в `Install-Module` .
`Install-Module` пытается установить модуль только один раз.

```powershell
Find-DscResource -Name xWebsite | Install-Module
```

`Find-DscResource` использует параметр **Name** для поиска ресурса с именем **ксвебсите**. Объект отправляется по конвейеру в `Install-Module` командлет. `Install-Module` устанавливает модуль **xWebAdministration** для ресурса.

### Пример 4. Поиск всех ресурсов DSC в модуле

`Find-DscResource` находит все ресурсы DSC, содержащиеся в указанном модуле. По умолчанию отображается текущая версия. Чтобы отобразить другие версии, используйте параметры **AllVersions** или **рекуиредверсионс** .

```powershell
Find-DscResource -ModuleName xWebAdministration
```

```Output
Name                                Version    ModuleName              Repository
----                                -------    ----------              ----------
WebApplicationHandler               2.6.0.0    xWebAdministration      PSGallery
xIisFeatureDelegation               2.6.0.0    xWebAdministration      PSGallery
xIisHandler                         2.6.0.0    xWebAdministration      PSGallery
xIisLogging                         2.6.0.0    xWebAdministration      PSGallery
```

`Find-DscResource` использует параметр **ModuleName** для указания **xWebAdministration** и поиска ресурсов DSC, содержащихся в модуле. Отобразится текущая версия каждого ресурса.

### Пример 5. поиск ресурса DSC по тегу и требуемой версии

Ресурсы DSC можно найти с помощью **тега** параметров и **RequiredVersion**. **Тег** отображает текущую версию каждого ресурса, содержащего указанный тег в репозитории.
**RequiredVersion** требуется параметр **ModuleName** , а параметр **Name** — необязательный. Параметры **Name** и **ModuleName** ограничивают выходные данные. Используйте параметр **AllVersions** для вывода доступных версий ресурса DSC.

```powershell
Find-DscResource -ModuleName xWebAdministration -Tag DSC -RequiredVersion 1.20
```

```output
Name                    Version    ModuleName             Repository
----                    -------    ----------             ----------
xIisFeatureDelegation   1.20.0.0   xWebAdministration     PSGallery
xIisHandler             1.20.0.0   xWebAdministration     PSGallery
xIisLogging             1.20.0.0   xWebAdministration     PSGallery
xIisMimeTypeMapping     1.20.0.0   xWebAdministration     PSGallery
```

### Пример 6. поиск ресурса с помощью фильтра

`Find-DscResource` находит все ресурсы и использует параметр **Filter** для указания результатов по **домену**. Параметр **Filter** находит значение фильтра в описании объекта или имени модуля. Используйте `Select-Object` командлет для просмотра свойств объекта.

```powershell
Find-DscResource -Filter Domain
```

```output
Name                    Version    ModuleName                 Repository
----                    -------    ----------                 ---------
xComputer               4.1.0.0    xComputerManagement        PSGallery
Computer                6.4.0.0    ComputerManagementDsc      PSGallery
xDSCDomainjoin          1.1        xDSCDomainjoin             PSGallery
xDisk                   1.0        xDisk                      PSGallery
xDSCFirewall            1.6.21     xDSCFirewall               PSGallery
dmAwsTagInstance        1.0.1      domainAwsDSCResources      PSGallery
```

## PARAMETERS

### -AllowPrerelease

Включает ресурсы, помеченные как предварительные версии в результатах.

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

### -AllVersions

Параметр **AllVersions** отображает все доступные версии ресурса DSC. Параметр **AllVersions** нельзя использовать с параметрами **MinimumVersion**, **MaximumVersion** или **RequiredVersion** .

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

Находит ресурсы на основе синтаксиса поиска поставщика **PackageManagement** . Например, укажите слова для поиска в свойствах **ModuleName** и **Description** .

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

Указывает максимальную версию ресурса, включаемую в результаты. Параметры **MaximumVersion** и **RequiredVersion** нельзя использовать в одной команде.

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

Указывает минимальную версию ресурса для включения в результаты. Параметры **MinimumVersion** и **RequiredVersion** нельзя использовать в одной команде.

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

Указывает модуль, содержащий ресурс DSC.

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

Указывает имя ресурса. По умолчанию все ресурсы. Используйте запятые для разделения массива имен ресурсов.

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

Указывает учетную запись пользователя с разрешением на использование прокси-сервера, указанного в параметре **прокси** .

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

Указывает репозиторий для поиска ресурсов. Используйте запятые для разделения массива имен репозитория.

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

Указывает точный номер версии модуля для включения в результаты. Параметры **RequiredVersion** и **MinimumVersion** нельзя использовать в одной команде.

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

### псжетдскресаурцеинфо

`Find-DscResource` Возвращает объект **псжетдскресаурцеинфо** .

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

[Register-PSRepository](Register-PSRepository.md)

[Select-Object](../Microsoft.PowerShell.Utility/Select-Object.md)

[Uninstall — Module](Uninstall-Module.md)
