---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/register-psrepository?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-PSRepository
ms.openlocfilehash: 179e672a099cfb92275795a0dc6129581a0e0299
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "99600686"
---
# <span data-ttu-id="b4668-102">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="b4668-102">Register-PSRepository</span></span>

## <span data-ttu-id="b4668-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="b4668-103">SYNOPSIS</span></span>
<span data-ttu-id="b4668-104">Регистрирует репозиторий PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b4668-104">Registers a PowerShell repository.</span></span>

## <span data-ttu-id="b4668-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b4668-105">SYNTAX</span></span>

### <span data-ttu-id="b4668-106">NameParameterSet (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="b4668-106">NameParameterSet (Default)</span></span>

```
Register-PSRepository [-Name] <String> [-SourceLocation] <Uri> [-PublishLocation <Uri>]
 [-ScriptSourceLocation <Uri>] [-ScriptPublishLocation <Uri>] [-Credential <PSCredential>]
 [-InstallationPolicy <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-PackageManagementProvider <String>] [<CommonParameters>]
```

### <span data-ttu-id="b4668-107">псгаллерипараметерсет</span><span class="sxs-lookup"><span data-stu-id="b4668-107">PSGalleryParameterSet</span></span>

```
Register-PSRepository [-Default] [-InstallationPolicy <String>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [<CommonParameters>]
```

## <span data-ttu-id="b4668-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b4668-108">DESCRIPTION</span></span>

<span data-ttu-id="b4668-109">`Register-PSRepository`Командлет регистрирует репозиторий по умолчанию для модулей PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b4668-109">The `Register-PSRepository` cmdlet registers the default repository for PowerShell modules.</span></span> <span data-ttu-id="b4668-110">После регистрации репозитория можно ссылаться на него из `Find-Module` `Install-Module` `Publish-Module` командлетов, и.</span><span class="sxs-lookup"><span data-stu-id="b4668-110">After a repository is registered, you can reference it from the `Find-Module`, `Install-Module`, and `Publish-Module` cmdlets.</span></span> <span data-ttu-id="b4668-111">Зарегистрированный репозиторий станет репозиторием по умолчанию в `Find-Module` и `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="b4668-111">The registered repository becomes the default repository in `Find-Module` and `Install-Module`.</span></span>

<span data-ttu-id="b4668-112">Информация о зарегистрированных репозиториях привязана к конкретному пользователю.</span><span class="sxs-lookup"><span data-stu-id="b4668-112">Registered repositories are user-specific.</span></span> <span data-ttu-id="b4668-113">Они не регистрируются в контексте всей системы.</span><span class="sxs-lookup"><span data-stu-id="b4668-113">They are not registered in a system-wide context.</span></span>

<span data-ttu-id="b4668-114">Каждый зарегистрированный репозиторий связан с поставщиком пакетов OneGet, который указан с помощью параметра **паккажеманажементпровидер** .</span><span class="sxs-lookup"><span data-stu-id="b4668-114">Each registered repository is associated with a OneGet package provider, which is specified with the **PackageManagementProvider** parameter.</span></span> <span data-ttu-id="b4668-115">Каждый поставщик OneGet предназначен для взаимодействия с конкретным типом репозитория.</span><span class="sxs-lookup"><span data-stu-id="b4668-115">Each OneGet provider is designed to interact with a specific type of repository.</span></span> <span data-ttu-id="b4668-116">Например, поставщик NuGet предназначен для взаимодействия с репозиториями на основе NuGet.</span><span class="sxs-lookup"><span data-stu-id="b4668-116">For example, the NuGet provider is designed to interact with NuGet-based repositories.</span></span> <span data-ttu-id="b4668-117">Если поставщик OneGet не указан во время регистрации, PowerShellGet пытается найти поставщик OneGet, который может работать с указанным исходным расположением.</span><span class="sxs-lookup"><span data-stu-id="b4668-117">If a OneGet provider is not specified during registration, PowerShellGet attempts to find a OneGet provider that can handle the specified source location.</span></span>

## <span data-ttu-id="b4668-118">Примеры</span><span class="sxs-lookup"><span data-stu-id="b4668-118">EXAMPLES</span></span>

### <span data-ttu-id="b4668-119">Пример 1. Регистрация репозитория</span><span class="sxs-lookup"><span data-stu-id="b4668-119">Example 1: Register a repository</span></span>

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

<span data-ttu-id="b4668-120">Первая команда регистрируется в `https://www.myget.org/F/powershellgetdemo/` качестве репозитория для текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="b4668-120">The first command registers `https://www.myget.org/F/powershellgetdemo/` as a repository for the current user.</span></span> <span data-ttu-id="b4668-121">После регистрации Минужетсаурце можно явно ссылаться на него при поиске, установке и публикации модулей.</span><span class="sxs-lookup"><span data-stu-id="b4668-121">After myNuGetSource is registered, you can explicitly reference it when searching for, installing, and publishing modules.</span></span> <span data-ttu-id="b4668-122">Так как параметр **паккажеманажементпровидер** не указан, репозиторий не связан явно с поставщиком пакетов OneGet, поэтому PowerShellGet опрашивает доступные поставщики пакетов и связывает их с поставщиком NuGet.</span><span class="sxs-lookup"><span data-stu-id="b4668-122">Because the **PackageManagementProvider** parameter isn't specified, the repository is not explicitly associated with a OneGet package provider, so PowerShellGet polls available package providers and associates it with the NuGet provider.</span></span>

<span data-ttu-id="b4668-123">Вторая команда получает зарегистрированные репозитории и отображает результаты.</span><span class="sxs-lookup"><span data-stu-id="b4668-123">The second command gets registered repositories and displays the results.</span></span>

## <span data-ttu-id="b4668-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b4668-124">PARAMETERS</span></span>

### <span data-ttu-id="b4668-125">-Credential</span><span class="sxs-lookup"><span data-stu-id="b4668-125">-Credential</span></span>

<span data-ttu-id="b4668-126">Указывает учетные данные учетной записи, имеющей права на регистрацию репозитория.</span><span class="sxs-lookup"><span data-stu-id="b4668-126">Specifies credentials of an account that has rights to register a repository.</span></span>

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

### <span data-ttu-id="b4668-127">-Default</span><span class="sxs-lookup"><span data-stu-id="b4668-127">-Default</span></span>

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

### <span data-ttu-id="b4668-128">-InstallationPolicy</span><span class="sxs-lookup"><span data-stu-id="b4668-128">-InstallationPolicy</span></span>

<span data-ttu-id="b4668-129">Указывает политику установки.</span><span class="sxs-lookup"><span data-stu-id="b4668-129">Specifies the installation policy.</span></span> <span data-ttu-id="b4668-130">Допустимые значения: Trusted, UnTrusted.</span><span class="sxs-lookup"><span data-stu-id="b4668-130">Valid values are: Trusted, UnTrusted.</span></span> <span data-ttu-id="b4668-131">Значение по умолчанию не является доверенным.</span><span class="sxs-lookup"><span data-stu-id="b4668-131">The default value is UnTrusted.</span></span>

<span data-ttu-id="b4668-132">Политика установки репозитория задает поведение PowerShell при установке из этого репозитория.</span><span class="sxs-lookup"><span data-stu-id="b4668-132">A repository's installation policy specifies PowerShell behavior when installing from that repository.</span></span> <span data-ttu-id="b4668-133">При установке модулей из ненадежного репозитория пользователю предлагается подтверждение.</span><span class="sxs-lookup"><span data-stu-id="b4668-133">When installing modules from an UnTrusted repository, the user is prompted for confirmation.</span></span>

<span data-ttu-id="b4668-134">**Инсталлатионполици** можно задать с помощью `Set-PSRepository` командлета.</span><span class="sxs-lookup"><span data-stu-id="b4668-134">You can set the **InstallationPolicy** with the `Set-PSRepository` cmdlet.</span></span>

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

### <span data-ttu-id="b4668-135">-Name</span><span class="sxs-lookup"><span data-stu-id="b4668-135">-Name</span></span>

<span data-ttu-id="b4668-136">Указывает имя регистрируемого репозитория.</span><span class="sxs-lookup"><span data-stu-id="b4668-136">Specifies the name of the repository to register.</span></span> <span data-ttu-id="b4668-137">Это имя можно использовать для указания репозитория в командлетах, таких как `Find-Module` и `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="b4668-137">You can use this name to specify the repository in cmdlets such as `Find-Module` and `Install-Module`.</span></span>

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

### <span data-ttu-id="b4668-138">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="b4668-138">-PackageManagementProvider</span></span>

<span data-ttu-id="b4668-139">Указывает поставщика пакетов OneGet.</span><span class="sxs-lookup"><span data-stu-id="b4668-139">Specifies a OneGet package provider.</span></span> <span data-ttu-id="b4668-140">Если не указать значение для этого параметра, PowerShellGet опрашивает доступные поставщики пакетов и связывает этот репозиторий с первым поставщиком пакетов, указывающим, что он может работать с репозиторием.</span><span class="sxs-lookup"><span data-stu-id="b4668-140">If you don't specify a value for this parameter, PowerShellGet polls available package providers and associates this repository with the first package provider that indicates it can handle the repository.</span></span>

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

### <span data-ttu-id="b4668-141">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="b4668-141">-Proxy</span></span>

<span data-ttu-id="b4668-142">Указывает прокси-сервер для запроса, а не напрямуюе подключение к Интернет-ресурсу.</span><span class="sxs-lookup"><span data-stu-id="b4668-142">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

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

### <span data-ttu-id="b4668-143">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="b4668-143">-ProxyCredential</span></span>

<span data-ttu-id="b4668-144">Указывает учетную запись пользователя, имеющую разрешение на использование прокси-сервера, который задается параметром **Proxy**.</span><span class="sxs-lookup"><span data-stu-id="b4668-144">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="b4668-145">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="b4668-145">-PublishLocation</span></span>

<span data-ttu-id="b4668-146">Указывает URI расположения публикации.</span><span class="sxs-lookup"><span data-stu-id="b4668-146">Specifies the URI of the publish location.</span></span> <span data-ttu-id="b4668-147">Например, для репозиториев на основе NuGet расположение публикации аналогично `https://someNuGetUrl.com/api/v2/Packages` .</span><span class="sxs-lookup"><span data-stu-id="b4668-147">For example, for NuGet-based repositories, the publish location is similar to `https://someNuGetUrl.com/api/v2/Packages`.</span></span>

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

### <span data-ttu-id="b4668-148">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="b4668-148">-ScriptPublishLocation</span></span>

<span data-ttu-id="b4668-149">Указывает расположение публикации скрипта.</span><span class="sxs-lookup"><span data-stu-id="b4668-149">Specifies the script publish location.</span></span>

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

### <span data-ttu-id="b4668-150">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="b4668-150">-ScriptSourceLocation</span></span>

<span data-ttu-id="b4668-151">Указывает расположение источника скрипта.</span><span class="sxs-lookup"><span data-stu-id="b4668-151">Specifies the script source location.</span></span>

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

### <span data-ttu-id="b4668-152">-SourceLocation</span><span class="sxs-lookup"><span data-stu-id="b4668-152">-SourceLocation</span></span>

<span data-ttu-id="b4668-153">Указывает URI для обнаружения и установки модулей из этого репозитория.</span><span class="sxs-lookup"><span data-stu-id="b4668-153">Specifies the URI for discovering and installing modules from this repository.</span></span> <span data-ttu-id="b4668-154">URI может быть веб-каналом сервера NuGet (наиболее распространенной ситуацией), HTTP, HTTPS, FTP или расположением файла.</span><span class="sxs-lookup"><span data-stu-id="b4668-154">A URI can be a NuGet server feed (most common situation), HTTP, HTTPS, FTP or file location.</span></span>

<span data-ttu-id="b4668-155">Например, для репозиториев на основе NuGet исходное расположение аналогично `https://someNuGetUrl.com/api/v2` .</span><span class="sxs-lookup"><span data-stu-id="b4668-155">For example, for NuGet-based repositories, the source location is similar to `https://someNuGetUrl.com/api/v2`.</span></span>

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

### <span data-ttu-id="b4668-156">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="b4668-156">CommonParameters</span></span>

<span data-ttu-id="b4668-157">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b4668-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b4668-158">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b4668-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b4668-159">Входные данные</span><span class="sxs-lookup"><span data-stu-id="b4668-159">INPUTS</span></span>

### <span data-ttu-id="b4668-160">System.Management.Automation.PSCredential</span><span class="sxs-lookup"><span data-stu-id="b4668-160">System.Management.Automation.PSCredential</span></span>

### <span data-ttu-id="b4668-161">System.Uri</span><span class="sxs-lookup"><span data-stu-id="b4668-161">System.Uri</span></span>

## <span data-ttu-id="b4668-162">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="b4668-162">OUTPUTS</span></span>

### <span data-ttu-id="b4668-163">System.Object</span><span class="sxs-lookup"><span data-stu-id="b4668-163">System.Object</span></span>

## <span data-ttu-id="b4668-164">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="b4668-164">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b4668-165">Начиная с апреля 2020 года коллекция PowerShell не поддерживает протокол TLS (Transport Layer Security) версий 1.0 и 1.1.</span><span class="sxs-lookup"><span data-stu-id="b4668-165">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="b4668-166">Если вы не используете TLS 1.2 или более поздней версии, при попытке доступа к коллекции PowerShell возникнет ошибка.</span><span class="sxs-lookup"><span data-stu-id="b4668-166">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="b4668-167">Чтобы проверить, используется ли TLS 1.2, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b4668-167">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="b4668-168">Дополнительные сведения см. в [объявлении](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) в блоге, посвященном PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b4668-168">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="b4668-169">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="b4668-169">RELATED LINKS</span></span>

[<span data-ttu-id="b4668-170">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="b4668-170">Get-PSRepository</span></span>](Get-PSRepository.md)

[<span data-ttu-id="b4668-171">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="b4668-171">Set-PSRepository</span></span>](Set-PSRepository.md)

[<span data-ttu-id="b4668-172">Unregister-PSRepository</span><span class="sxs-lookup"><span data-stu-id="b4668-172">Unregister-PSRepository</span></span>](Unregister-PSRepository.md)
