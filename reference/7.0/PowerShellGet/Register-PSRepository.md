---
external help file: PSModule-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/register-psrepository?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-PSRepository
ms.openlocfilehash: be7ffa38a0409fa7ef0d01649b863a32732e34de
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93226206"
---
# Register-PSRepository

## Краткий обзор
Регистрирует репозиторий PowerShell.

## SYNTAX

### NameParameterSet (по умолчанию)

```
Register-PSRepository [-Name] <String> [-SourceLocation] <Uri> [-PublishLocation <Uri>]
 [-ScriptSourceLocation <Uri>] [-ScriptPublishLocation <Uri>] [-Credential <PSCredential>]
 [-InstallationPolicy <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-PackageManagementProvider <String>] [<CommonParameters>]
```

### псгаллерипараметерсет

```
Register-PSRepository [-Default] [-InstallationPolicy <String>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION

`Register-PSRepository`Командлет регистрирует репозиторий по умолчанию для модулей PowerShell. После регистрации репозитория можно ссылаться на него из `Find-Module` `Install-Module` `Publish-Module` командлетов, и. Зарегистрированный репозиторий станет репозиторием по умолчанию в `Find-Module` и `Install-Module` .

Информация о зарегистрированных репозиториях привязана к конкретному пользователю. Они не регистрируются в контексте всей системы.

Каждый зарегистрированный репозиторий связан с поставщиком пакетов OneGet, который указан с помощью параметра **паккажеманажементпровидер** . Каждый поставщик OneGet предназначен для взаимодействия с конкретным типом репозитория. Например, поставщик NuGet предназначен для взаимодействия с репозиториями на основе NuGet. Если поставщик OneGet не указан во время регистрации, PowerShellGet пытается найти поставщик OneGet, который может работать с указанным исходным расположением.

## Примеры

### Пример 1. Регистрация репозитория

```powershell
$parameters = @{
  Name = "myNuGetSource"
  SourceLocation = "https://www.myget.org/F/powershellgetdemo/api/v2"
  PublishLocation = "https://www.myget.org/F/powershellgetdemo/api/v2/Packages"
  InstallationPolicy = 'Trusted'
}
Register-PSRepository @parameters
Get-PSRepository
```

```Output
Name                SourceLocation          OneGetProvider       InstallationPolicy
----                --------------          --------------       ------------------
PSGallery           http://go.micro...      NuGet                Untrusted
myNuGetSource       https://myget.c...      NuGet                Trusted
```

Первая команда регистрируется в `https://www.myget.org/F/powershellgetdemo/` качестве репозитория для текущего пользователя. После регистрации Минужетсаурце можно явно ссылаться на него при поиске, установке и публикации модулей. Так как параметр **паккажеманажементпровидер** не указан, репозиторий не связан явно с поставщиком пакетов OneGet, поэтому PowerShellGet опрашивает доступные поставщики пакетов и связывает их с поставщиком NuGet.

Вторая команда получает зарегистрированные репозитории и отображает результаты.

## PARAMETERS

### -Credential

Указывает учетные данные учетной записи, имеющей права на регистрацию репозитория.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Default

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PSGalleryParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstallationPolicy

Указывает политику установки. Допустимые значения: Trusted, UnTrusted. Значение по умолчанию не является доверенным.

Политика установки репозитория задает поведение PowerShell при установке из этого репозитория. При установке модулей из ненадежного репозитория пользователю предлагается подтверждение.

**Инсталлатионполици** можно задать с помощью `Set-PSRepository` командлета.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Trusted, Untrusted

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Указывает имя регистрируемого репозитория. Это имя можно использовать для указания репозитория в командлетах, таких как `Find-Module` и `Install-Module` .

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PackageManagementProvider

Указывает поставщика пакетов OneGet. Если не указать значение для этого параметра, PowerShellGet опрашивает доступные поставщики пакетов и связывает этот репозиторий с первым поставщиком пакетов, указывающим, что он может работать с репозиторием.

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
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

### -PublishLocation

Указывает URI расположения публикации. Например, для репозиториев на основе NuGet расположение публикации аналогично `https://someNuGetUrl.com/api/v2/Packages` .

```yaml
Type: System.Uri
Parameter Sets: NameParameterSet
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
Type: System.Uri
Parameter Sets: NameParameterSet
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
Type: System.Uri
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceLocation

Указывает URI для обнаружения и установки модулей из этого репозитория. URI может быть веб-каналом сервера NuGet (наиболее распространенной ситуацией), HTTP, HTTPS, FTP или расположением файла.

Например, для репозиториев на основе NuGet исходное расположение аналогично `https://someNuGetUrl.com/api/v2` .

```yaml
Type: System.Uri
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.Management.Automation.PSCredential

### System.Uri

## Выходные данные

### System.Object

## ПРИМЕЧАНИЯ

## Связанные ссылки

[Get-PSRepository](Get-PSRepository.md)

[Set-PSRepository](Set-PSRepository.md)

[Unregister-PSRepository](Unregister-PSRepository.md)
