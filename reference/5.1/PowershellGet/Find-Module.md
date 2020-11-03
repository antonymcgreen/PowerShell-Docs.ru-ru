---
external help file: PSModule-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PowerShellGet
ms.date: 03/11/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/find-module?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-Module
ms.openlocfilehash: 8b17019932df5b2cad68a9ea382387451d1b22e1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227269"
---
# Find-Module

## Краткий обзор
Находит модули в репозитории, соответствующие указанным критериям.

## SYNTAX

### Все

```
Find-Module [[-Name] <string[]>] [-MinimumVersion <string>] [-MaximumVersion <string>]
 [-RequiredVersion <string>] [-AllVersions] [-IncludeDependencies] [-Filter <string>]
 [-Tag <string[]>] [-Includes <string[]>] [-DscResource <string[]>] [-RoleCapability <string[]>]
 [-Command <string[]>] [-Proxy <uri>] [-ProxyCredential <pscredential>] [-Repository <string[]>]
 [-Credential <pscredential>] [-AllowPrerelease] [<CommonParameters>]
```

## DESCRIPTION

`Find-Module`Командлет находит модули в репозитории, соответствующие указанным критериям.
`Find-Module` Возвращает объект **PSRepositoryItemInfo** для каждого найденного модуля. Объекты можно отсылать по конвейеру в командлеты, такие как `Install-Module` .

В первый раз `Find-Module` при попытке использовать репозиторий может быть предложено установить обновления.
Если источник репозитория не зарегистрирован с помощью `Register-PSRepository` командлета, возвращается ошибка.

`Find-Module` Возвращает последнюю версию модуля, если не используются параметры, ограничивающие версию. Чтобы получить список версий модуля для репозитория, используйте параметр **AllVersions**.

Если указан параметр **MinimumVersion** , `Find-Module` возвращает версию модуля, которая больше или равна минимальному значению. Если в репозитории доступна более новая версия, возвращается более новая версия.

Если указан параметр **MaximumVersion** , `Find-Module` возвращает последнюю версию модуля, которая не превышает указанную версию.

Если указан параметр **RequiredVersion** , то `Find-Module` возвращает только версию модуля, точно совпадающую с указанной версией. `Find-Module` выполняет поиск во всех доступных модулях, так как может происходить конфликт имен между источниками.

В следующих примерах используется [коллекция PowerShell](https://www.powershellgallery.com/) в качестве единственного зарегистрированного репозитория. `Get-PSRepository` отображает зарегистрированные репозитории. Если у вас есть несколько зарегистрированных репозиториев, используйте `-Repository` параметр, чтобы указать имя репозитория.

## Примеры

### Пример 1. Поиск модуля по имени

В этом примере выполняется поиск модуля в репозитории по умолчанию.

```powershell
Find-Module -Name PowerShellGet
```

```Output
Version   Name              Repository           Description
-------   ----              ----------           -----------
2.1.0     PowerShellGet     PSGallery            PowerShell module with commands for discovering...
```

`Find-Module`Командлет использует параметр **Name** для указания модуля **PowerShellGet** .

### Пример 2. Поиск модулей с одинаковыми именами

В этом примере используется `*` подстановочный знак звездочки () для поиска модулей с похожими именами.

```powershell
Find-Module -Name PowerShell*
```

```Output
Version   Name                            Repository    Description
-------   ----                            ----------    -----------
0.4.0     powershell-yaml                 PSGallery     Powershell module for serializing and...
2.1.0     PowerShellGet                   PSGallery     PowerShell module with commands for...
1.9       Powershell.Helper.Extension     PSGallery     # Powershell.Helper.Extension...
3.1       PowerShellHumanizer             PSGallery     PowerShell Humanizer wraps Humanizer...
4.0       PowerShellISEModule             PSGallery     a module that adds capability to the ISE
```

`Find-Module` **Name** `*` Для поиска всех модулей, содержащих **PowerShell** , командлет использует параметр Name с подстановочным знаком звездочки ().

### Пример 3. Поиск модуля по минимальной версии

В этом примере выполняется поиск минимальной версии модуля. Если репозиторий содержит более новую версию модуля, возвращается более новая версия.

```powershell
Find-Module -Name PowerShellGet -MinimumVersion 1.6.5
```

```Output
Version   Name             Repository     Description
-------   ----             ----------     -----------
2.1.0     PowerShellGet    PSGallery      PowerShell module with commands for discovering...
```

`Find-Module`Командлет использует параметр **Name** для указания модуля **PowerShellGet** . Параметр **MinimumVersion** указывает версию **1.6.5**. `Find-Module` Возвращает PowerShellGet версии **2.1.0** , так как она превышает минимальную версию и является самой последней версией.

### Пример 4. Поиск модуля по определенной версии

В этом примере возвращается объект, представляющий конкретную версию модуля. Если указанная версия не найдена, возвращается ошибка.

```powershell
Find-Module -Name PowerShellGet -RequiredVersion 1.6.5
```

```Output
Version   Name             Repository     Description
-------   ----             ----------     -----------
1.6.5     PowerShellGet    PSGallery      PowerShell module with commands for discovering...
```

`Find-Module`Командлет использует параметр **Name** для указания модуля **PowerShellGet** . Параметр **RequiredVersion** указывает версию **1.6.5**.

### Пример 5. Поиск модуля в определенном репозитории

В этом примере используется параметр **репозитория** для поиска модуля в определенном репозитории.

```powershell
Find-Module -Name PowerShellGet -Repository PSGallery
```

```Output
Version   Name             Repository     Description
-------   ----             ----------     -----------
2.1.0     PowerShellGet    PSGallery      PowerShell module with commands for discovering...
```

`Find-Module`Командлет использует параметр **Name** для указания модуля **PowerShellGet** . Параметр **репозитория** задает поиск в репозитории **PSGallery** .

### Пример 6. Поиск модуля в нескольких репозиториях

В этом примере используется `Register-PSRepository` для указания репозитория. `Find-Module` использует репозиторий для поиска модуля.

```powershell
Register-PSRepository -Name MySource -SourceLocation https://www.myget.org/F/powershellgetdemo/
Find-Module -Name Contoso* -Repository PSGallery, MySource
```

```Output
Repository    Version   Name             Description
----------    -------   ----             -----------
PSGallery     2.0.0.0   ContosoServer    Cmdlets and DSC resources for managing Contoso Server...
MySource      1.2.0.0   ContosoClient    Cmdlets and DSC resources for managing Contoso Client...
```

`Register-PSRepository`Командлет регистрирует новый репозиторий. Параметр **Name** назначает имя **mysource**. Параметр **SourceLocation** указывает адрес репозитория.

`Find-Module`Командлет использует параметр **Name** с подстановочным знаком звездочки ( `*` ) для указания модуля **contoso** . Параметр **репозитория** определяет Поиск двух репозиториев, **PSGallery** и **mysource**.

### Пример 7. Поиск модуля, содержащего ресурс DSC

Эта команда возвращает модули, которые содержат ресурсы DSC. Параметр **включает** четыре стандартные функции, которые используются для поиска в репозитории. Используйте клавишу TAB для вывода четырех функций, поддерживаемых параметром **включает** .

```powershell
Find-Module -Repository PSGallery -Includes DscResource
```

```Output
Version     Name                            Repository    Description
-------     ----                            ----------    -----------
2.7.0       Carbon                          PSGallery     Carbon is a PowerShell module...
8.5.0.0     xPSDesiredStateConfiguration    PSGallery     The xPSDesiredStateConfiguration module...
1.3.1       PackageManagement               PSGallery     PackageManagement (a.k.a. OneGet) is...
2.7.0.0     xWindowsUpdate                  PSGallery     Module with DSC Resources...
3.2.0.0     xCertificate                    PSGallery     This module includes DSC resources...
3.1.0.0     xPowerShellExecutionPolicy      PSGallery     This DSC resource can change the user...
```

`Find-Module`Командлет использует параметр **репозитория** для поиска в репозитории, **PSGallery**.
Параметр **содержит** указывает **DscResource** , которая является функцией, которую параметр может искать в репозитории.

### Пример 8. Поиск модуля с фильтром

В этом примере, чтобы найти модули, используется фильтр для поиска в репозитории.

Для репозитория на основе NuGet параметр **Filter** выполняет поиск по имени, описанию и тегам для аргумента.

```powershell
Find-Module -Filter AppDomain
```

```Output
Version    Name              Repository           Description
-------    ----              ----------           -----------
1.0.0.0  AppDomainConfig     PSGallery            Manipulate AppDomain configuration...
1.1.0    ClassExplorer       PSGallery            Quickly search the AppDomain for classes...
```

`Find-Module`Командлет использует параметр **Filter** для поиска в репозитории для **AppDomain**.

## PARAMETERS

### -AllowPrerelease

Включает в модули результатов, помеченные как предварительные версии.

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

Указывает, что в результаты включаются все версии модуля. Параметр **AllVersions** нельзя использовать с параметрами **MinimumVersion** , **MaximumVersion** или **RequiredVersion** .

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

### -Command

Указывает массив команд для поиска в модулях. Команда может быть функцией или рабочим процессом.

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

### -Credential

Указывает учетную запись пользователя, имеющую права на установку модуля для указанного поставщика пакетов или источника.

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

### -DscResource

Задает имя или часть имени модулей, содержащих ресурсы DSC. Для каждого соглашения PowerShell выполняет поиск **или** , если вы предоставляете несколько аргументов.

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

### -Filter

Задает фильтр на основе синтаксиса поиска, зависящего от поставщика **PackageManagement** . Для модулей NuGet этот параметр эквивалентен поиску с помощью панели поиска на веб-сайте [коллекция PowerShell](https://www.powershellgallery.com/) .

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

### -IncludeDependencies

Указывает, что эта операция включает все модули, зависящие от модуля, указанного в параметре **Name** .

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

### — Включает

Возвращает только те модули, которые включают в себя определенные виды функций PowerShell. Например, может потребоваться найти только модули, включающие **DSCResource**. Для этого параметра допустимы следующие значения:

- Командлет
- DscResource
- Компонент
- RoleCapability

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:
Accepted values: DscResource, Cmdlet, Function, RoleCapability

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumVersion

Указывает максимальную или последнюю версию модуля для включения в результаты поиска.
В одной команде нельзя использовать **MaximumVersion** и **RequiredVersion** .

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MinimumVersion

Указывает минимальную версию модуля для включения в результаты. В одной команде нельзя использовать **MinimumVersion** и **RequiredVersion** .

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Указывает имена модулей для поиска в репозитории. Принимается список имен модулей с разделителями-запятыми. Подстановочные знаки принимаются.

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

Используйте параметр **репозитория** , чтобы указать репозиторий для поиска модуля. Используется при регистрации нескольких репозиториев. Принимает разделенный запятыми список репозиториев. Чтобы зарегистрировать репозиторий, используйте `Register-PSRepository` . Чтобы отобразить зарегистрированные репозитории, используйте `Get-PSRepository` .

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

Указывает точный номер версии модуля, который должен быть включен в результаты. Параметр **RequiredVersion** нельзя использовать в той же команде, что и **MinimumVersion** или **MaximumVersion**.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RoleCapability

Указывает массив возможностей роли.

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

### -Tag

Задает массив тегов. Примеры тегов: **десиредстатеконфигуратион** , **DSC** , **дскресаурцекит** или **PSModule**.

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

### PSRepositoryItemInfo

`Find-Module` создает объекты **PSRepositoryItemInfo** , которые можно отсылать по конвейеру в командлеты, такие как `Install-Module` .

## ПРИМЕЧАНИЯ

Этот командлет выполняется в PowerShell 5,0 или более поздних версиях Windows PowerShell, Windows 7 или Windows 2008 R2 и более поздних версиях Windows.

## Связанные ссылки

[Get-PSRepository](Get-PSRepository.md)

[Install-Module](Install-Module.md)

[Publish-Module](Publish-Module.md)

[Save-Module](Save-Module.md)

[Uninstall-Module](Uninstall-Module.md)

[Update-Module](Update-Module.md)

[Register-PSRepository](Register-PSRepository.md)
