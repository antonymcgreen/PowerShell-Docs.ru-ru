---
external help file: PSModule-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/register-psrepository?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-PSRepository
ms.openlocfilehash: c42d13707e850990a8dcacfdaacec2b382c224a1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228629"
---
# <span data-ttu-id="e6607-103">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="e6607-103">Register-PSRepository</span></span>

## <span data-ttu-id="e6607-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="e6607-104">SYNOPSIS</span></span>
<span data-ttu-id="e6607-105">Регистрирует репозиторий PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e6607-105">Registers a PowerShell repository.</span></span>

## <span data-ttu-id="e6607-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e6607-106">SYNTAX</span></span>

### <span data-ttu-id="e6607-107">NameParameterSet (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="e6607-107">NameParameterSet (Default)</span></span>

```
Register-PSRepository [-Name] <String> [-SourceLocation] <Uri> [-PublishLocation <Uri>]
 [-ScriptSourceLocation <Uri>] [-ScriptPublishLocation <Uri>] [-Credential <PSCredential>]
 [-InstallationPolicy <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-PackageManagementProvider <String>] [<CommonParameters>]
```

### <span data-ttu-id="e6607-108">псгаллерипараметерсет</span><span class="sxs-lookup"><span data-stu-id="e6607-108">PSGalleryParameterSet</span></span>

```
Register-PSRepository [-Default] [-InstallationPolicy <String>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [<CommonParameters>]
```

## <span data-ttu-id="e6607-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e6607-109">DESCRIPTION</span></span>

<span data-ttu-id="e6607-110">`Register-PSRepository`Командлет регистрирует репозиторий по умолчанию для модулей PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e6607-110">The `Register-PSRepository` cmdlet registers the default repository for PowerShell modules.</span></span> <span data-ttu-id="e6607-111">После регистрации репозитория можно ссылаться на него из `Find-Module` `Install-Module` `Publish-Module` командлетов, и.</span><span class="sxs-lookup"><span data-stu-id="e6607-111">After a repository is registered, you can reference it from the `Find-Module`, `Install-Module`, and `Publish-Module` cmdlets.</span></span> <span data-ttu-id="e6607-112">Зарегистрированный репозиторий станет репозиторием по умолчанию в `Find-Module` и `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="e6607-112">The registered repository becomes the default repository in `Find-Module` and `Install-Module`.</span></span>

<span data-ttu-id="e6607-113">Информация о зарегистрированных репозиториях привязана к конкретному пользователю.</span><span class="sxs-lookup"><span data-stu-id="e6607-113">Registered repositories are user-specific.</span></span> <span data-ttu-id="e6607-114">Они не регистрируются в контексте всей системы.</span><span class="sxs-lookup"><span data-stu-id="e6607-114">They are not registered in a system-wide context.</span></span>

<span data-ttu-id="e6607-115">Каждый зарегистрированный репозиторий связан с поставщиком пакетов OneGet, который указан с помощью параметра **паккажеманажементпровидер** .</span><span class="sxs-lookup"><span data-stu-id="e6607-115">Each registered repository is associated with a OneGet package provider, which is specified with the **PackageManagementProvider** parameter.</span></span> <span data-ttu-id="e6607-116">Каждый поставщик OneGet предназначен для взаимодействия с конкретным типом репозитория.</span><span class="sxs-lookup"><span data-stu-id="e6607-116">Each OneGet provider is designed to interact with a specific type of repository.</span></span> <span data-ttu-id="e6607-117">Например, поставщик NuGet предназначен для взаимодействия с репозиториями на основе NuGet.</span><span class="sxs-lookup"><span data-stu-id="e6607-117">For example, the NuGet provider is designed to interact with NuGet-based repositories.</span></span> <span data-ttu-id="e6607-118">Если поставщик OneGet не указан во время регистрации, PowerShellGet пытается найти поставщик OneGet, который может работать с указанным исходным расположением.</span><span class="sxs-lookup"><span data-stu-id="e6607-118">If a OneGet provider is not specified during registration, PowerShellGet attempts to find a OneGet provider that can handle the specified source location.</span></span>

## <span data-ttu-id="e6607-119">Примеры</span><span class="sxs-lookup"><span data-stu-id="e6607-119">EXAMPLES</span></span>

### <span data-ttu-id="e6607-120">Пример 1. Регистрация репозитория</span><span class="sxs-lookup"><span data-stu-id="e6607-120">Example 1: Register a repository</span></span>

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

<span data-ttu-id="e6607-121">Первая команда регистрируется в `https://www.myget.org/F/powershellgetdemo/` качестве репозитория для текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="e6607-121">The first command registers `https://www.myget.org/F/powershellgetdemo/` as a repository for the current user.</span></span> <span data-ttu-id="e6607-122">После регистрации Минужетсаурце можно явно ссылаться на него при поиске, установке и публикации модулей.</span><span class="sxs-lookup"><span data-stu-id="e6607-122">After myNuGetSource is registered, you can explicitly reference it when searching for, installing, and publishing modules.</span></span> <span data-ttu-id="e6607-123">Так как параметр **паккажеманажементпровидер** не указан, репозиторий не связан явно с поставщиком пакетов OneGet, поэтому PowerShellGet опрашивает доступные поставщики пакетов и связывает их с поставщиком NuGet.</span><span class="sxs-lookup"><span data-stu-id="e6607-123">Because the **PackageManagementProvider** parameter isn't specified, the repository is not explicitly associated with a OneGet package provider, so PowerShellGet polls available package providers and associates it with the NuGet provider.</span></span>

<span data-ttu-id="e6607-124">Вторая команда получает зарегистрированные репозитории и отображает результаты.</span><span class="sxs-lookup"><span data-stu-id="e6607-124">The second command gets registered repositories and displays the results.</span></span>

## <span data-ttu-id="e6607-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e6607-125">PARAMETERS</span></span>

### <span data-ttu-id="e6607-126">-Credential</span><span class="sxs-lookup"><span data-stu-id="e6607-126">-Credential</span></span>

<span data-ttu-id="e6607-127">Указывает учетные данные учетной записи, имеющей права на регистрацию репозитория.</span><span class="sxs-lookup"><span data-stu-id="e6607-127">Specifies credentials of an account that has rights to register a repository.</span></span>

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

### <span data-ttu-id="e6607-128">-Default</span><span class="sxs-lookup"><span data-stu-id="e6607-128">-Default</span></span>

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

### <span data-ttu-id="e6607-129">-InstallationPolicy</span><span class="sxs-lookup"><span data-stu-id="e6607-129">-InstallationPolicy</span></span>

<span data-ttu-id="e6607-130">Указывает политику установки.</span><span class="sxs-lookup"><span data-stu-id="e6607-130">Specifies the installation policy.</span></span> <span data-ttu-id="e6607-131">Допустимые значения: Trusted, UnTrusted.</span><span class="sxs-lookup"><span data-stu-id="e6607-131">Valid values are: Trusted, UnTrusted.</span></span> <span data-ttu-id="e6607-132">Значение по умолчанию не является доверенным.</span><span class="sxs-lookup"><span data-stu-id="e6607-132">The default value is UnTrusted.</span></span>

<span data-ttu-id="e6607-133">Политика установки репозитория задает поведение PowerShell при установке из этого репозитория.</span><span class="sxs-lookup"><span data-stu-id="e6607-133">A repository's installation policy specifies PowerShell behavior when installing from that repository.</span></span> <span data-ttu-id="e6607-134">При установке модулей из ненадежного репозитория пользователю предлагается подтверждение.</span><span class="sxs-lookup"><span data-stu-id="e6607-134">When installing modules from an UnTrusted repository, the user is prompted for confirmation.</span></span>

<span data-ttu-id="e6607-135">**Инсталлатионполици** можно задать с помощью `Set-PSRepository` командлета.</span><span class="sxs-lookup"><span data-stu-id="e6607-135">You can set the **InstallationPolicy** with the `Set-PSRepository` cmdlet.</span></span>

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

### <span data-ttu-id="e6607-136">-Name</span><span class="sxs-lookup"><span data-stu-id="e6607-136">-Name</span></span>

<span data-ttu-id="e6607-137">Указывает имя регистрируемого репозитория.</span><span class="sxs-lookup"><span data-stu-id="e6607-137">Specifies the name of the repository to register.</span></span> <span data-ttu-id="e6607-138">Это имя можно использовать для указания репозитория в командлетах, таких как `Find-Module` и `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="e6607-138">You can use this name to specify the repository in cmdlets such as `Find-Module` and `Install-Module`.</span></span>

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

### <span data-ttu-id="e6607-139">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="e6607-139">-PackageManagementProvider</span></span>

<span data-ttu-id="e6607-140">Указывает поставщика пакетов OneGet.</span><span class="sxs-lookup"><span data-stu-id="e6607-140">Specifies a OneGet package provider.</span></span> <span data-ttu-id="e6607-141">Если не указать значение для этого параметра, PowerShellGet опрашивает доступные поставщики пакетов и связывает этот репозиторий с первым поставщиком пакетов, указывающим, что он может работать с репозиторием.</span><span class="sxs-lookup"><span data-stu-id="e6607-141">If you don't specify a value for this parameter, PowerShellGet polls available package providers and associates this repository with the first package provider that indicates it can handle the repository.</span></span>

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

### <span data-ttu-id="e6607-142">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="e6607-142">-Proxy</span></span>

<span data-ttu-id="e6607-143">Указывает прокси-сервер для запроса, а не напрямуюе подключение к Интернет-ресурсу.</span><span class="sxs-lookup"><span data-stu-id="e6607-143">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

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

### <span data-ttu-id="e6607-144">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="e6607-144">-ProxyCredential</span></span>

<span data-ttu-id="e6607-145">Указывает учетную запись пользователя, имеющую разрешение на использование прокси-сервера, который задается параметром **Proxy** .</span><span class="sxs-lookup"><span data-stu-id="e6607-145">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="e6607-146">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="e6607-146">-PublishLocation</span></span>

<span data-ttu-id="e6607-147">Указывает URI расположения публикации.</span><span class="sxs-lookup"><span data-stu-id="e6607-147">Specifies the URI of the publish location.</span></span> <span data-ttu-id="e6607-148">Например, для репозиториев на основе NuGet расположение публикации аналогично `https://someNuGetUrl.com/api/v2/Packages` .</span><span class="sxs-lookup"><span data-stu-id="e6607-148">For example, for NuGet-based repositories, the publish location is similar to `https://someNuGetUrl.com/api/v2/Packages`.</span></span>

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

### <span data-ttu-id="e6607-149">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="e6607-149">-ScriptPublishLocation</span></span>

<span data-ttu-id="e6607-150">Указывает расположение публикации скрипта.</span><span class="sxs-lookup"><span data-stu-id="e6607-150">Specifies the script publish location.</span></span>

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

### <span data-ttu-id="e6607-151">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="e6607-151">-ScriptSourceLocation</span></span>

<span data-ttu-id="e6607-152">Указывает расположение источника скрипта.</span><span class="sxs-lookup"><span data-stu-id="e6607-152">Specifies the script source location.</span></span>

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

### <span data-ttu-id="e6607-153">-SourceLocation</span><span class="sxs-lookup"><span data-stu-id="e6607-153">-SourceLocation</span></span>

<span data-ttu-id="e6607-154">Указывает URI для обнаружения и установки модулей из этого репозитория.</span><span class="sxs-lookup"><span data-stu-id="e6607-154">Specifies the URI for discovering and installing modules from this repository.</span></span> <span data-ttu-id="e6607-155">URI может быть веб-каналом сервера NuGet (наиболее распространенной ситуацией), HTTP, HTTPS, FTP или расположением файла.</span><span class="sxs-lookup"><span data-stu-id="e6607-155">A URI can be a NuGet server feed (most common situation), HTTP, HTTPS, FTP or file location.</span></span>

<span data-ttu-id="e6607-156">Например, для репозиториев на основе NuGet исходное расположение аналогично `https://someNuGetUrl.com/api/v2` .</span><span class="sxs-lookup"><span data-stu-id="e6607-156">For example, for NuGet-based repositories, the source location is similar to `https://someNuGetUrl.com/api/v2`.</span></span>

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

### <span data-ttu-id="e6607-157">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="e6607-157">CommonParameters</span></span>

<span data-ttu-id="e6607-158">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e6607-158">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e6607-159">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e6607-159">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e6607-160">Входные данные</span><span class="sxs-lookup"><span data-stu-id="e6607-160">INPUTS</span></span>

### <span data-ttu-id="e6607-161">System.Management.Automation.PSCredential</span><span class="sxs-lookup"><span data-stu-id="e6607-161">System.Management.Automation.PSCredential</span></span>

### <span data-ttu-id="e6607-162">System.Uri</span><span class="sxs-lookup"><span data-stu-id="e6607-162">System.Uri</span></span>

## <span data-ttu-id="e6607-163">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="e6607-163">OUTPUTS</span></span>

### <span data-ttu-id="e6607-164">System.Object</span><span class="sxs-lookup"><span data-stu-id="e6607-164">System.Object</span></span>

## <span data-ttu-id="e6607-165">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="e6607-165">NOTES</span></span>

## <span data-ttu-id="e6607-166">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="e6607-166">RELATED LINKS</span></span>

[<span data-ttu-id="e6607-167">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="e6607-167">Get-PSRepository</span></span>](Get-PSRepository.md)

[<span data-ttu-id="e6607-168">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="e6607-168">Set-PSRepository</span></span>](Set-PSRepository.md)

[<span data-ttu-id="e6607-169">Unregister-PSRepository</span><span class="sxs-lookup"><span data-stu-id="e6607-169">Unregister-PSRepository</span></span>](Unregister-PSRepository.md)
