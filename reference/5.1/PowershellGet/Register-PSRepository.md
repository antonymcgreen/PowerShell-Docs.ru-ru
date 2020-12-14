---
external help file: PSModule-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/register-psrepository?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-PSRepository
ms.openlocfilehash: 07f70f4fad6057ad689befaafd1d41f819a4538c
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "94892769"
---
# <span data-ttu-id="237ed-103">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="237ed-103">Register-PSRepository</span></span>

## <span data-ttu-id="237ed-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="237ed-104">SYNOPSIS</span></span>
<span data-ttu-id="237ed-105">Регистрирует репозиторий PowerShell.</span><span class="sxs-lookup"><span data-stu-id="237ed-105">Registers a PowerShell repository.</span></span>

## <span data-ttu-id="237ed-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="237ed-106">SYNTAX</span></span>

### <span data-ttu-id="237ed-107">NameParameterSet (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="237ed-107">NameParameterSet (Default)</span></span>

```
Register-PSRepository [-Name] <String> [-SourceLocation] <Uri> [-PublishLocation <Uri>]
 [-ScriptSourceLocation <Uri>] [-ScriptPublishLocation <Uri>] [-Credential <PSCredential>]
 [-InstallationPolicy <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-PackageManagementProvider <String>] [<CommonParameters>]
```

### <span data-ttu-id="237ed-108">псгаллерипараметерсет</span><span class="sxs-lookup"><span data-stu-id="237ed-108">PSGalleryParameterSet</span></span>

```
Register-PSRepository [-Default] [-InstallationPolicy <String>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [<CommonParameters>]
```

## <span data-ttu-id="237ed-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="237ed-109">DESCRIPTION</span></span>

<span data-ttu-id="237ed-110">`Register-PSRepository`Командлет регистрирует репозиторий по умолчанию для модулей PowerShell.</span><span class="sxs-lookup"><span data-stu-id="237ed-110">The `Register-PSRepository` cmdlet registers the default repository for PowerShell modules.</span></span> <span data-ttu-id="237ed-111">После регистрации репозитория можно ссылаться на него из `Find-Module` `Install-Module` `Publish-Module` командлетов, и.</span><span class="sxs-lookup"><span data-stu-id="237ed-111">After a repository is registered, you can reference it from the `Find-Module`, `Install-Module`, and `Publish-Module` cmdlets.</span></span> <span data-ttu-id="237ed-112">Зарегистрированный репозиторий станет репозиторием по умолчанию в `Find-Module` и `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="237ed-112">The registered repository becomes the default repository in `Find-Module` and `Install-Module`.</span></span>

<span data-ttu-id="237ed-113">Информация о зарегистрированных репозиториях привязана к конкретному пользователю.</span><span class="sxs-lookup"><span data-stu-id="237ed-113">Registered repositories are user-specific.</span></span> <span data-ttu-id="237ed-114">Они не регистрируются в контексте всей системы.</span><span class="sxs-lookup"><span data-stu-id="237ed-114">They are not registered in a system-wide context.</span></span>

<span data-ttu-id="237ed-115">Каждый зарегистрированный репозиторий связан с поставщиком пакетов OneGet, который указан с помощью параметра **паккажеманажементпровидер** .</span><span class="sxs-lookup"><span data-stu-id="237ed-115">Each registered repository is associated with a OneGet package provider, which is specified with the **PackageManagementProvider** parameter.</span></span> <span data-ttu-id="237ed-116">Каждый поставщик OneGet предназначен для взаимодействия с конкретным типом репозитория.</span><span class="sxs-lookup"><span data-stu-id="237ed-116">Each OneGet provider is designed to interact with a specific type of repository.</span></span> <span data-ttu-id="237ed-117">Например, поставщик NuGet предназначен для взаимодействия с репозиториями на основе NuGet.</span><span class="sxs-lookup"><span data-stu-id="237ed-117">For example, the NuGet provider is designed to interact with NuGet-based repositories.</span></span> <span data-ttu-id="237ed-118">Если поставщик OneGet не указан во время регистрации, PowerShellGet пытается найти поставщик OneGet, который может работать с указанным исходным расположением.</span><span class="sxs-lookup"><span data-stu-id="237ed-118">If a OneGet provider is not specified during registration, PowerShellGet attempts to find a OneGet provider that can handle the specified source location.</span></span>

## <span data-ttu-id="237ed-119">Примеры</span><span class="sxs-lookup"><span data-stu-id="237ed-119">EXAMPLES</span></span>

### <span data-ttu-id="237ed-120">Пример 1. Регистрация репозитория</span><span class="sxs-lookup"><span data-stu-id="237ed-120">Example 1: Register a repository</span></span>

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

<span data-ttu-id="237ed-121">Первая команда регистрируется в `https://www.myget.org/F/powershellgetdemo/` качестве репозитория для текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="237ed-121">The first command registers `https://www.myget.org/F/powershellgetdemo/` as a repository for the current user.</span></span> <span data-ttu-id="237ed-122">После регистрации Минужетсаурце можно явно ссылаться на него при поиске, установке и публикации модулей.</span><span class="sxs-lookup"><span data-stu-id="237ed-122">After myNuGetSource is registered, you can explicitly reference it when searching for, installing, and publishing modules.</span></span> <span data-ttu-id="237ed-123">Так как параметр **паккажеманажементпровидер** не указан, репозиторий не связан явно с поставщиком пакетов OneGet, поэтому PowerShellGet опрашивает доступные поставщики пакетов и связывает их с поставщиком NuGet.</span><span class="sxs-lookup"><span data-stu-id="237ed-123">Because the **PackageManagementProvider** parameter isn't specified, the repository is not explicitly associated with a OneGet package provider, so PowerShellGet polls available package providers and associates it with the NuGet provider.</span></span>

<span data-ttu-id="237ed-124">Вторая команда получает зарегистрированные репозитории и отображает результаты.</span><span class="sxs-lookup"><span data-stu-id="237ed-124">The second command gets registered repositories and displays the results.</span></span>

## <span data-ttu-id="237ed-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="237ed-125">PARAMETERS</span></span>

### <span data-ttu-id="237ed-126">-Credential</span><span class="sxs-lookup"><span data-stu-id="237ed-126">-Credential</span></span>

<span data-ttu-id="237ed-127">Указывает учетные данные учетной записи, имеющей права на регистрацию репозитория.</span><span class="sxs-lookup"><span data-stu-id="237ed-127">Specifies credentials of an account that has rights to register a repository.</span></span>

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

### <span data-ttu-id="237ed-128">-Default</span><span class="sxs-lookup"><span data-stu-id="237ed-128">-Default</span></span>

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

### <span data-ttu-id="237ed-129">-InstallationPolicy</span><span class="sxs-lookup"><span data-stu-id="237ed-129">-InstallationPolicy</span></span>

<span data-ttu-id="237ed-130">Указывает политику установки.</span><span class="sxs-lookup"><span data-stu-id="237ed-130">Specifies the installation policy.</span></span> <span data-ttu-id="237ed-131">Допустимые значения: Trusted, UnTrusted.</span><span class="sxs-lookup"><span data-stu-id="237ed-131">Valid values are: Trusted, UnTrusted.</span></span> <span data-ttu-id="237ed-132">Значение по умолчанию не является доверенным.</span><span class="sxs-lookup"><span data-stu-id="237ed-132">The default value is UnTrusted.</span></span>

<span data-ttu-id="237ed-133">Политика установки репозитория задает поведение PowerShell при установке из этого репозитория.</span><span class="sxs-lookup"><span data-stu-id="237ed-133">A repository's installation policy specifies PowerShell behavior when installing from that repository.</span></span> <span data-ttu-id="237ed-134">При установке модулей из ненадежного репозитория пользователю предлагается подтверждение.</span><span class="sxs-lookup"><span data-stu-id="237ed-134">When installing modules from an UnTrusted repository, the user is prompted for confirmation.</span></span>

<span data-ttu-id="237ed-135">**Инсталлатионполици** можно задать с помощью `Set-PSRepository` командлета.</span><span class="sxs-lookup"><span data-stu-id="237ed-135">You can set the **InstallationPolicy** with the `Set-PSRepository` cmdlet.</span></span>

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

### <span data-ttu-id="237ed-136">-Name</span><span class="sxs-lookup"><span data-stu-id="237ed-136">-Name</span></span>

<span data-ttu-id="237ed-137">Указывает имя регистрируемого репозитория.</span><span class="sxs-lookup"><span data-stu-id="237ed-137">Specifies the name of the repository to register.</span></span> <span data-ttu-id="237ed-138">Это имя можно использовать для указания репозитория в командлетах, таких как `Find-Module` и `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="237ed-138">You can use this name to specify the repository in cmdlets such as `Find-Module` and `Install-Module`.</span></span>

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

### <span data-ttu-id="237ed-139">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="237ed-139">-PackageManagementProvider</span></span>

<span data-ttu-id="237ed-140">Указывает поставщика пакетов OneGet.</span><span class="sxs-lookup"><span data-stu-id="237ed-140">Specifies a OneGet package provider.</span></span> <span data-ttu-id="237ed-141">Если не указать значение для этого параметра, PowerShellGet опрашивает доступные поставщики пакетов и связывает этот репозиторий с первым поставщиком пакетов, указывающим, что он может работать с репозиторием.</span><span class="sxs-lookup"><span data-stu-id="237ed-141">If you don't specify a value for this parameter, PowerShellGet polls available package providers and associates this repository with the first package provider that indicates it can handle the repository.</span></span>

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

### <span data-ttu-id="237ed-142">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="237ed-142">-Proxy</span></span>

<span data-ttu-id="237ed-143">Указывает прокси-сервер для запроса, а не напрямуюе подключение к Интернет-ресурсу.</span><span class="sxs-lookup"><span data-stu-id="237ed-143">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

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

### <span data-ttu-id="237ed-144">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="237ed-144">-ProxyCredential</span></span>

<span data-ttu-id="237ed-145">Указывает учетную запись пользователя, имеющую разрешение на использование прокси-сервера, который задается параметром **Proxy**.</span><span class="sxs-lookup"><span data-stu-id="237ed-145">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="237ed-146">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="237ed-146">-PublishLocation</span></span>

<span data-ttu-id="237ed-147">Указывает URI расположения публикации.</span><span class="sxs-lookup"><span data-stu-id="237ed-147">Specifies the URI of the publish location.</span></span> <span data-ttu-id="237ed-148">Например, для репозиториев на основе NuGet расположение публикации аналогично `https://someNuGetUrl.com/api/v2/Packages` .</span><span class="sxs-lookup"><span data-stu-id="237ed-148">For example, for NuGet-based repositories, the publish location is similar to `https://someNuGetUrl.com/api/v2/Packages`.</span></span>

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

### <span data-ttu-id="237ed-149">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="237ed-149">-ScriptPublishLocation</span></span>

<span data-ttu-id="237ed-150">Указывает расположение публикации скрипта.</span><span class="sxs-lookup"><span data-stu-id="237ed-150">Specifies the script publish location.</span></span>

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

### <span data-ttu-id="237ed-151">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="237ed-151">-ScriptSourceLocation</span></span>

<span data-ttu-id="237ed-152">Указывает расположение источника скрипта.</span><span class="sxs-lookup"><span data-stu-id="237ed-152">Specifies the script source location.</span></span>

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

### <span data-ttu-id="237ed-153">-SourceLocation</span><span class="sxs-lookup"><span data-stu-id="237ed-153">-SourceLocation</span></span>

<span data-ttu-id="237ed-154">Указывает URI для обнаружения и установки модулей из этого репозитория.</span><span class="sxs-lookup"><span data-stu-id="237ed-154">Specifies the URI for discovering and installing modules from this repository.</span></span> <span data-ttu-id="237ed-155">URI может быть веб-каналом сервера NuGet (наиболее распространенной ситуацией), HTTP, HTTPS, FTP или расположением файла.</span><span class="sxs-lookup"><span data-stu-id="237ed-155">A URI can be a NuGet server feed (most common situation), HTTP, HTTPS, FTP or file location.</span></span>

<span data-ttu-id="237ed-156">Например, для репозиториев на основе NuGet исходное расположение аналогично `https://someNuGetUrl.com/api/v2` .</span><span class="sxs-lookup"><span data-stu-id="237ed-156">For example, for NuGet-based repositories, the source location is similar to `https://someNuGetUrl.com/api/v2`.</span></span>

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

### <span data-ttu-id="237ed-157">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="237ed-157">CommonParameters</span></span>

<span data-ttu-id="237ed-158">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="237ed-158">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="237ed-159">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="237ed-159">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="237ed-160">Входные данные</span><span class="sxs-lookup"><span data-stu-id="237ed-160">INPUTS</span></span>

### <span data-ttu-id="237ed-161">System.Management.Automation.PSCredential</span><span class="sxs-lookup"><span data-stu-id="237ed-161">System.Management.Automation.PSCredential</span></span>

### <span data-ttu-id="237ed-162">System.Uri</span><span class="sxs-lookup"><span data-stu-id="237ed-162">System.Uri</span></span>

## <span data-ttu-id="237ed-163">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="237ed-163">OUTPUTS</span></span>

### <span data-ttu-id="237ed-164">System.Object</span><span class="sxs-lookup"><span data-stu-id="237ed-164">System.Object</span></span>

## <span data-ttu-id="237ed-165">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="237ed-165">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="237ed-166">По состоянию на апрель 2020 коллекция PowerShell больше не поддерживает TLS-версии 1,0 и 1,1.</span><span class="sxs-lookup"><span data-stu-id="237ed-166">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="237ed-167">Если вы не используете TLS 1,2 или более поздней версии, при попытке доступа к коллекция PowerShell возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="237ed-167">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="237ed-168">Используйте следующую команду, чтобы убедиться, что используется TLS 1,2:</span><span class="sxs-lookup"><span data-stu-id="237ed-168">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="237ed-169">Дополнительные сведения см. в [объявлении](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) в блоге PowerShell.</span><span class="sxs-lookup"><span data-stu-id="237ed-169">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="237ed-170">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="237ed-170">RELATED LINKS</span></span>

[<span data-ttu-id="237ed-171">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="237ed-171">Get-PSRepository</span></span>](Get-PSRepository.md)

[<span data-ttu-id="237ed-172">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="237ed-172">Set-PSRepository</span></span>](Set-PSRepository.md)

[<span data-ttu-id="237ed-173">Unregister-PSRepository</span><span class="sxs-lookup"><span data-stu-id="237ed-173">Unregister-PSRepository</span></span>](Unregister-PSRepository.md)
