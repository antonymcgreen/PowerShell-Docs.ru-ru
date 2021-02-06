---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 04/22/2020
online version: https://docs.microsoft.com/powershell/module/powershellget/set-psrepository?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSRepository
ms.openlocfilehash: d6f3901ba389ff910dcc808d2e4296032617052c
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "99600472"
---
# Set-PSRepository

## Краткий обзор
Задает значения для зарегистрированного репозитория.

## SYNTAX

```
Set-PSRepository [-Name] <String> [[-SourceLocation] <Uri>] [-PublishLocation <Uri>]
 [-ScriptSourceLocation <Uri>] [-ScriptPublishLocation <Uri>] [-Credential <PSCredential>]
 [-InstallationPolicy <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-PackageManagementProvider <String>] [<CommonParameters>]
```

## DESCRIPTION

`Set-PSRepository`Командлет задает значения для зарегистрированного репозитория модуля. Параметры постоянны для текущего пользователя и применяются ко всем версиям PowerShell, установленным для этого пользователя.

## Примеры

### Пример 1. Задание политики установки для репозитория

```powershell
Set-PSRepository -Name "myInternalSource" -InstallationPolicy Trusted
```

Эта команда задает **доверенную** политику установки для репозитория **минтерналсаурце** , чтобы не выводить запрос перед установкой модулей из этого источника.

### Пример 2. Задание расположений источника и публикации для репозитория

```powershell
Set-PSRepository -Name "myInternalSource" -SourceLocation 'https://someNuGetUrl.com/api/v2' -PublishLocation 'https://someNuGetUrl.com/api/v2/packages'
```

Эта команда задает исходное расположение и расположение публикации для **минтерналсаурце** указанным URI.

## PARAMETERS

### -Credential

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

### -InstallationPolicy

Указывает политику установки. Допустимые значения: **доверие**, **без доверия**.

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

Указывает имя репозитория.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PackageManagementProvider

Указывает поставщика управления пакетами.

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
Parameter Sets: (All)
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
Parameter Sets: (All)
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
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceLocation

Указывает URI для обнаружения и установки модулей из этого репозитория. Например, для репозиториев на основе NuGet исходное расположение аналогично `https://someNuGetUrl.com/api/v2` .

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.String

### System.Management.Automation.PSCredential

### System.Uri

## Выходные данные

### System.Object

## ПРИМЕЧАНИЯ

> [!IMPORTANT]
> Начиная с апреля 2020 года коллекция PowerShell не поддерживает протокол TLS (Transport Layer Security) версий 1.0 и 1.1. Если вы не используете TLS 1.2 или более поздней версии, при попытке доступа к коллекции PowerShell возникнет ошибка. Чтобы проверить, используется ли TLS 1.2, выполните следующую команду:
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> Дополнительные сведения см. в [объявлении](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) в блоге, посвященном PowerShell.

## Связанные ссылки

[Get-PSRepository](Get-PSRepository.md)

[Register-PSRepository](Register-PSRepository.md)

[Unregister-PSRepository](Unregister-PSRepository.md)
