---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 03/11/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/find-module?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-Module
ms.openlocfilehash: f9cba90ffa69d04df196f4062c8f190d545b9bc3
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "99600678"
---
# <span data-ttu-id="d1c3d-102">Find-Module</span><span class="sxs-lookup"><span data-stu-id="d1c3d-102">Find-Module</span></span>

## <span data-ttu-id="d1c3d-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="d1c3d-103">SYNOPSIS</span></span>
<span data-ttu-id="d1c3d-104">Находит модули в репозитории, соответствующие указанным критериям.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-104">Finds modules in a repository that match specified criteria.</span></span>

## <span data-ttu-id="d1c3d-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d1c3d-105">SYNTAX</span></span>

### <span data-ttu-id="d1c3d-106">Все</span><span class="sxs-lookup"><span data-stu-id="d1c3d-106">All</span></span>

```
Find-Module [[-Name] <string[]>] [-MinimumVersion <string>] [-MaximumVersion <string>]
 [-RequiredVersion <string>] [-AllVersions] [-IncludeDependencies] [-Filter <string>]
 [-Tag <string[]>] [-Includes <string[]>] [-DscResource <string[]>] [-RoleCapability <string[]>]
 [-Command <string[]>] [-Proxy <uri>] [-ProxyCredential <pscredential>] [-Repository <string[]>]
 [-Credential <pscredential>] [-AllowPrerelease] [<CommonParameters>]
```

## <span data-ttu-id="d1c3d-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d1c3d-107">DESCRIPTION</span></span>

<span data-ttu-id="d1c3d-108">`Find-Module`Командлет находит модули в репозитории, соответствующие указанным критериям.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-108">The `Find-Module` cmdlet finds modules in a repository that match the specified criteria.</span></span>
<span data-ttu-id="d1c3d-109">`Find-Module` Возвращает объект **PSRepositoryItemInfo** для каждого найденного модуля.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-109">`Find-Module` returns a **PSRepositoryItemInfo** object for each module it finds.</span></span> <span data-ttu-id="d1c3d-110">Объекты можно отсылать по конвейеру в командлеты, такие как `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="d1c3d-110">The objects can be sent down the pipeline to cmdlets such as `Install-Module`.</span></span>

<span data-ttu-id="d1c3d-111">В первый раз `Find-Module` при попытке использовать репозиторий может быть предложено установить обновления.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-111">The first time `Find-Module` attempts to use a repository, you might be prompted to install updates.</span></span>
<span data-ttu-id="d1c3d-112">Если источник репозитория не зарегистрирован с помощью `Register-PSRepository` командлета, возвращается ошибка.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-112">If the repository source is not registered with `Register-PSRepository` cmdlet, an error is returned.</span></span>

<span data-ttu-id="d1c3d-113">`Find-Module` Возвращает последнюю версию модуля, если не используются параметры, ограничивающие версию.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-113">`Find-Module` returns the newest version of a module if no parameters are used that limit the version.</span></span> <span data-ttu-id="d1c3d-114">Чтобы получить список версий модуля для репозитория, используйте параметр **AllVersions**.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-114">To get a repository's list of a module's versions, use the parameter **AllVersions**.</span></span>

<span data-ttu-id="d1c3d-115">Если указан параметр **MinimumVersion** , `Find-Module` возвращает версию модуля, которая больше или равна минимальному значению.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-115">If the **MinimumVersion** parameter is specified, `Find-Module` returns the module's version that is equal to or greater than the minimum.</span></span> <span data-ttu-id="d1c3d-116">Если в репозитории доступна более новая версия, возвращается более новая версия.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-116">If there is a newer version available in the repository, the newer version is returned.</span></span>

<span data-ttu-id="d1c3d-117">Если указан параметр **MaximumVersion** , `Find-Module` возвращает последнюю версию модуля, которая не превышает указанную версию.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-117">If the **MaximumVersion** parameter is specified, `Find-Module` returns the newest version of the module that does not exceed the version specified.</span></span>

<span data-ttu-id="d1c3d-118">Если указан параметр **RequiredVersion** , то `Find-Module` возвращает только версию модуля, точно совпадающую с указанной версией.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-118">If the **RequiredVersion** parameter is specified, `Find-Module` only returns the module version that is an exact match to the specified version.</span></span> <span data-ttu-id="d1c3d-119">`Find-Module` выполняет поиск во всех доступных модулях, так как может происходить конфликт имен между источниками.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-119">`Find-Module` searches through all available modules, because name conflicts between sources can occur.</span></span>

<span data-ttu-id="d1c3d-120">В следующих примерах используется [коллекция PowerShell](https://www.powershellgallery.com/) в качестве единственного зарегистрированного репозитория.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-120">The following examples use the [PowerShell Gallery](https://www.powershellgallery.com/) as the only registered repository.</span></span> <span data-ttu-id="d1c3d-121">`Get-PSRepository` отображает зарегистрированные репозитории.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-121">`Get-PSRepository` displays the registered repositories.</span></span> <span data-ttu-id="d1c3d-122">Если у вас есть несколько зарегистрированных репозиториев, используйте `-Repository` параметр, чтобы указать имя репозитория.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-122">If you have multiple registered repositories, use the `-Repository` parameter to specify the repository's name.</span></span>

## <span data-ttu-id="d1c3d-123">Примеры</span><span class="sxs-lookup"><span data-stu-id="d1c3d-123">EXAMPLES</span></span>

### <span data-ttu-id="d1c3d-124">Пример 1. Поиск модуля по имени</span><span class="sxs-lookup"><span data-stu-id="d1c3d-124">Example 1: Find a module by name</span></span>

<span data-ttu-id="d1c3d-125">В этом примере выполняется поиск модуля в репозитории по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-125">This example finds a module in the default repository.</span></span>

```powershell
Find-Module -Name PowerShellGet
```

```Output
Version   Name              Repository           Description
-------   ----              ----------           -----------
2.1.0     PowerShellGet     PSGallery            PowerShell module with commands for discovering...
```

<span data-ttu-id="d1c3d-126">`Find-Module`Командлет использует параметр **Name** для указания модуля **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="d1c3d-126">The `Find-Module` cmdlet uses the **Name** parameter to specify the **PowerShellGet** module.</span></span>

### <span data-ttu-id="d1c3d-127">Пример 2. Поиск модулей с одинаковыми именами</span><span class="sxs-lookup"><span data-stu-id="d1c3d-127">Example 2: Find modules with similar names</span></span>

<span data-ttu-id="d1c3d-128">В этом примере используется `*` подстановочный знак звездочки () для поиска модулей с похожими именами.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-128">This example uses the asterisk (`*`) wildcard to find modules with similar names.</span></span>

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

<span data-ttu-id="d1c3d-129">`Find-Module`  `*` Для поиска всех модулей, содержащих **PowerShell**, командлет использует параметр Name с подстановочным знаком звездочки ().</span><span class="sxs-lookup"><span data-stu-id="d1c3d-129">The `Find-Module` cmdlet uses the **Name** parameter with the asterisk (`*`) wildcard to find all modules that contain **PowerShell**.</span></span>

### <span data-ttu-id="d1c3d-130">Пример 3. Поиск модуля по минимальной версии</span><span class="sxs-lookup"><span data-stu-id="d1c3d-130">Example 3: Find a module by minimum version</span></span>

<span data-ttu-id="d1c3d-131">В этом примере выполняется поиск минимальной версии модуля.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-131">This example searches for a module's minimum version.</span></span> <span data-ttu-id="d1c3d-132">Если репозиторий содержит более новую версию модуля, возвращается более новая версия.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-132">If the repository contains a newer version of the module, the newer version is returned.</span></span>

```powershell
Find-Module -Name PowerShellGet -MinimumVersion 1.6.5
```

```Output
Version   Name             Repository     Description
-------   ----             ----------     -----------
2.1.0     PowerShellGet    PSGallery      PowerShell module with commands for discovering...
```

<span data-ttu-id="d1c3d-133">`Find-Module`Командлет использует параметр **Name** для указания модуля **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="d1c3d-133">The `Find-Module` cmdlet uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="d1c3d-134">Параметр **MinimumVersion** указывает версию **1.6.5**.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-134">The **MinimumVersion** specifies version **1.6.5**.</span></span> <span data-ttu-id="d1c3d-135">`Find-Module` Возвращает PowerShellGet версии **2.1.0** , так как она превышает минимальную версию и является самой последней версией.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-135">`Find-Module` returns PowerShellGet version **2.1.0** because it exceeds the minimum version and is the most current version.</span></span>

### <span data-ttu-id="d1c3d-136">Пример 4. Поиск модуля по определенной версии</span><span class="sxs-lookup"><span data-stu-id="d1c3d-136">Example 4: Find a module by specific version</span></span>

<span data-ttu-id="d1c3d-137">В этом примере возвращается объект, представляющий конкретную версию модуля.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-137">This example returns an object that represents a module's specific version.</span></span> <span data-ttu-id="d1c3d-138">Если указанная версия не найдена, возвращается ошибка.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-138">If the specified version is not found, an error is returned.</span></span>

```powershell
Find-Module -Name PowerShellGet -RequiredVersion 1.6.5
```

```Output
Version   Name             Repository     Description
-------   ----             ----------     -----------
1.6.5     PowerShellGet    PSGallery      PowerShell module with commands for discovering...
```

<span data-ttu-id="d1c3d-139">`Find-Module`Командлет использует параметр **Name** для указания модуля **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="d1c3d-139">The `Find-Module` cmdlet uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="d1c3d-140">Параметр **RequiredVersion** указывает версию **1.6.5**.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-140">The **RequiredVersion** parameter specifies version **1.6.5**.</span></span>

### <span data-ttu-id="d1c3d-141">Пример 5. Поиск модуля в определенном репозитории</span><span class="sxs-lookup"><span data-stu-id="d1c3d-141">Example 5: Find a module in a specific repository</span></span>

<span data-ttu-id="d1c3d-142">В этом примере используется параметр **репозитория** для поиска модуля в определенном репозитории.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-142">This example uses the **Repository** parameter to find a module in a specific repository.</span></span>

```powershell
Find-Module -Name PowerShellGet -Repository PSGallery
```

```Output
Version   Name             Repository     Description
-------   ----             ----------     -----------
2.1.0     PowerShellGet    PSGallery      PowerShell module with commands for discovering...
```

<span data-ttu-id="d1c3d-143">`Find-Module`Командлет использует параметр **Name** для указания модуля **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="d1c3d-143">The `Find-Module` cmdlet uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="d1c3d-144">Параметр **репозитория** задает поиск в репозитории **PSGallery** .</span><span class="sxs-lookup"><span data-stu-id="d1c3d-144">The **Repository** parameter specifies to search the **PSGallery** repository.</span></span>

### <span data-ttu-id="d1c3d-145">Пример 6. Поиск модуля в нескольких репозиториях</span><span class="sxs-lookup"><span data-stu-id="d1c3d-145">Example 6: Find a module in multiple repositories</span></span>

<span data-ttu-id="d1c3d-146">В этом примере используется `Register-PSRepository` для указания репозитория.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-146">This example uses the `Register-PSRepository` to specify a repository.</span></span> <span data-ttu-id="d1c3d-147">`Find-Module` использует репозиторий для поиска модуля.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-147">`Find-Module` uses the repository to search for a module.</span></span>

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

<span data-ttu-id="d1c3d-148">`Register-PSRepository`Командлет регистрирует новый репозиторий.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-148">The `Register-PSRepository` cmdlet registers a new repository.</span></span> <span data-ttu-id="d1c3d-149">Параметр **Name** назначает имя **mysource**.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-149">The **Name** parameter assigns the name **MySource**.</span></span> <span data-ttu-id="d1c3d-150">Параметр **SourceLocation** указывает адрес репозитория.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-150">The **SourceLocation** parameter specifies the repository's address.</span></span>

<span data-ttu-id="d1c3d-151">`Find-Module`Командлет использует параметр **Name** с подстановочным знаком звездочки ( `*` ) для указания модуля **contoso** .</span><span class="sxs-lookup"><span data-stu-id="d1c3d-151">The `Find-Module` cmdlet uses the **Name** parameter with the asterisk (`*`) wildcard to specify the **Contoso** module.</span></span> <span data-ttu-id="d1c3d-152">Параметр **репозитория** определяет Поиск двух репозиториев, **PSGallery** и **mysource**.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-152">The **Repository** parameter specifies to search two repositories, **PSGallery** and **MySource**.</span></span>

### <span data-ttu-id="d1c3d-153">Пример 7. Поиск модуля, содержащего ресурс DSC</span><span class="sxs-lookup"><span data-stu-id="d1c3d-153">Example 7: Find a module that contains a DSC resource</span></span>

<span data-ttu-id="d1c3d-154">Эта команда возвращает модули, которые содержат ресурсы DSC.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-154">This command returns modules that contain DSC resources.</span></span> <span data-ttu-id="d1c3d-155">Параметр **включает** четыре стандартные функции, которые используются для поиска в репозитории.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-155">The **Includes** parameter has four predefined functionalities that are used to search the repository.</span></span> <span data-ttu-id="d1c3d-156">Используйте клавишу TAB для вывода четырех функций, поддерживаемых параметром **включает** .</span><span class="sxs-lookup"><span data-stu-id="d1c3d-156">Use tab-complete to display the four functionalities supported by the **Includes** parameter.</span></span>

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

<span data-ttu-id="d1c3d-157">`Find-Module`Командлет использует параметр **репозитория** для поиска в репозитории, **PSGallery**.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-157">The `Find-Module` cmdlet uses the **Repository** parameter to search the repository, **PSGallery**.</span></span>
<span data-ttu-id="d1c3d-158">Параметр **содержит** указывает **DscResource**, которая является функцией, которую параметр может искать в репозитории.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-158">The **Includes** parameter specifies **DscResource**, which is a functionality that the parameter can search for in the repository.</span></span>

### <span data-ttu-id="d1c3d-159">Пример 8. Поиск модуля с фильтром</span><span class="sxs-lookup"><span data-stu-id="d1c3d-159">Example 8: Find a module with a filter</span></span>

<span data-ttu-id="d1c3d-160">В этом примере, чтобы найти модули, используется фильтр для поиска в репозитории.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-160">In this example, to find modules, a filter is used to search the repository.</span></span>

<span data-ttu-id="d1c3d-161">Для репозитория на основе NuGet параметр **Filter** выполняет поиск по имени, описанию и тегам для аргумента.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-161">For a NuGet-based repository, the **Filter** parameter searches through the name, description, and tags for the argument.</span></span>

```powershell
Find-Module -Filter AppDomain
```

```Output
Version    Name              Repository           Description
-------    ----              ----------           -----------
1.0.0.0  AppDomainConfig     PSGallery            Manipulate AppDomain configuration...
1.1.0    ClassExplorer       PSGallery            Quickly search the AppDomain for classes...
```

<span data-ttu-id="d1c3d-162">`Find-Module`Командлет использует параметр **Filter** для поиска в репозитории для **AppDomain**.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-162">The `Find-Module` cmdlet uses the **Filter** parameter to search the repository for **AppDomain**.</span></span>

## <span data-ttu-id="d1c3d-163">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d1c3d-163">PARAMETERS</span></span>

### <span data-ttu-id="d1c3d-164">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="d1c3d-164">-AllowPrerelease</span></span>

<span data-ttu-id="d1c3d-165">Включает в модули результатов, помеченные как предварительные версии.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-165">Includes in the results modules marked as a pre-release.</span></span>

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

### <span data-ttu-id="d1c3d-166">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="d1c3d-166">-AllVersions</span></span>

<span data-ttu-id="d1c3d-167">Указывает, что в результаты включаются все версии модуля.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-167">Specifies to include all versions of a module in the results.</span></span> <span data-ttu-id="d1c3d-168">Параметр **AllVersions** нельзя использовать с параметрами **MinimumVersion**, **MaximumVersion** или **RequiredVersion** .</span><span class="sxs-lookup"><span data-stu-id="d1c3d-168">You cannot use the **AllVersions** parameter with the **MinimumVersion**, **MaximumVersion**, or **RequiredVersion** parameters.</span></span>

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

### <span data-ttu-id="d1c3d-169">-Command</span><span class="sxs-lookup"><span data-stu-id="d1c3d-169">-Command</span></span>

<span data-ttu-id="d1c3d-170">Указывает массив команд для поиска в модулях.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-170">Specifies an array of commands to find in modules.</span></span> <span data-ttu-id="d1c3d-171">Команда может быть функцией или рабочим процессом.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-171">A command can be a function or workflow.</span></span>

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

### <span data-ttu-id="d1c3d-172">-Credential</span><span class="sxs-lookup"><span data-stu-id="d1c3d-172">-Credential</span></span>

<span data-ttu-id="d1c3d-173">Указывает учетную запись пользователя, имеющую права на установку модуля для указанного поставщика пакетов или источника.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-173">Specifies a user account that has rights to install a module for a specified package provider or source.</span></span>

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

### <span data-ttu-id="d1c3d-174">-DscResource</span><span class="sxs-lookup"><span data-stu-id="d1c3d-174">-DscResource</span></span>

<span data-ttu-id="d1c3d-175">Задает имя или часть имени модулей, содержащих ресурсы DSC.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-175">Specifies the name, or part of the name, of modules that contain DSC resources.</span></span> <span data-ttu-id="d1c3d-176">Для каждого соглашения PowerShell выполняет поиск **или** , если вы предоставляете несколько аргументов.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-176">Per PowerShell conventions, performs an **OR** search when you provide multiple arguments.</span></span>

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

### <span data-ttu-id="d1c3d-177">-Filter</span><span class="sxs-lookup"><span data-stu-id="d1c3d-177">-Filter</span></span>

<span data-ttu-id="d1c3d-178">Задает фильтр на основе синтаксиса поиска, зависящего от поставщика **PackageManagement** .</span><span class="sxs-lookup"><span data-stu-id="d1c3d-178">Specifies a filter based on the **PackageManagement** provider-specific search syntax.</span></span> <span data-ttu-id="d1c3d-179">Для модулей NuGet этот параметр эквивалентен поиску с помощью панели поиска на веб-сайте [коллекция PowerShell](https://www.powershellgallery.com/) .</span><span class="sxs-lookup"><span data-stu-id="d1c3d-179">For NuGet modules, this parameter is the equivalent of searching by using the Search bar on the [PowerShell Gallery](https://www.powershellgallery.com/) website.</span></span>

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

### <span data-ttu-id="d1c3d-180">-IncludeDependencies</span><span class="sxs-lookup"><span data-stu-id="d1c3d-180">-IncludeDependencies</span></span>

<span data-ttu-id="d1c3d-181">Указывает, что эта операция включает все модули, зависящие от модуля, указанного в параметре **Name** .</span><span class="sxs-lookup"><span data-stu-id="d1c3d-181">Indicates that this operation includes all modules that are dependent upon the module specified in the **Name** parameter.</span></span>

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

### <span data-ttu-id="d1c3d-182">— Включает</span><span class="sxs-lookup"><span data-stu-id="d1c3d-182">-Includes</span></span>

<span data-ttu-id="d1c3d-183">Возвращает только те модули, которые включают в себя определенные виды функций PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-183">Returns only those modules that include specific kinds of PowerShell functionality.</span></span> <span data-ttu-id="d1c3d-184">Например, может потребоваться найти только модули, включающие **DSCResource**.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-184">For example, you might only want to find modules that include **DSCResource**.</span></span> <span data-ttu-id="d1c3d-185">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="d1c3d-185">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="d1c3d-186">Командлет</span><span class="sxs-lookup"><span data-stu-id="d1c3d-186">Cmdlet</span></span>
- <span data-ttu-id="d1c3d-187">DscResource</span><span class="sxs-lookup"><span data-stu-id="d1c3d-187">DscResource</span></span>
- <span data-ttu-id="d1c3d-188">Компонент</span><span class="sxs-lookup"><span data-stu-id="d1c3d-188">Function</span></span>
- <span data-ttu-id="d1c3d-189">RoleCapability</span><span class="sxs-lookup"><span data-stu-id="d1c3d-189">RoleCapability</span></span>

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

### <span data-ttu-id="d1c3d-190">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="d1c3d-190">-MaximumVersion</span></span>

<span data-ttu-id="d1c3d-191">Указывает максимальную или последнюю версию модуля для включения в результаты поиска.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-191">Specifies the maximum, or latest, version of the module to include in the search results.</span></span>
<span data-ttu-id="d1c3d-192">В одной команде нельзя использовать **MaximumVersion** и **RequiredVersion** .</span><span class="sxs-lookup"><span data-stu-id="d1c3d-192">**MaximumVersion** and **RequiredVersion** cannot be used in the same command.</span></span>

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

### <span data-ttu-id="d1c3d-193">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="d1c3d-193">-MinimumVersion</span></span>

<span data-ttu-id="d1c3d-194">Указывает минимальную версию модуля для включения в результаты.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-194">Specifies the minimum version of the module to include in results.</span></span> <span data-ttu-id="d1c3d-195">В одной команде нельзя использовать **MinimumVersion** и **RequiredVersion** .</span><span class="sxs-lookup"><span data-stu-id="d1c3d-195">**MinimumVersion** and **RequiredVersion** cannot be used in the same command.</span></span>

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

### <span data-ttu-id="d1c3d-196">-Name</span><span class="sxs-lookup"><span data-stu-id="d1c3d-196">-Name</span></span>

<span data-ttu-id="d1c3d-197">Указывает имена модулей для поиска в репозитории.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-197">Specifies the names of modules to search for in the repository.</span></span> <span data-ttu-id="d1c3d-198">Принимается список имен модулей с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-198">A comma-separated list of module names is accepted.</span></span> <span data-ttu-id="d1c3d-199">Подстановочные знаки принимаются.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-199">Wildcards are accepted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d1c3d-200">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="d1c3d-200">-Proxy</span></span>

<span data-ttu-id="d1c3d-201">Указывает прокси-сервер для запроса, а не напрямуюе подключение к Интернет-ресурсу.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-201">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

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

### <span data-ttu-id="d1c3d-202">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="d1c3d-202">-ProxyCredential</span></span>

<span data-ttu-id="d1c3d-203">Указывает учетную запись пользователя, имеющую разрешение на использование прокси-сервера, который задается параметром **Proxy**.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-203">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="d1c3d-204">— Репозиторий;</span><span class="sxs-lookup"><span data-stu-id="d1c3d-204">-Repository</span></span>

<span data-ttu-id="d1c3d-205">Используйте параметр **репозитория** , чтобы указать репозиторий для поиска модуля.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-205">Use the **Repository** parameter to specify which repository to search for a module.</span></span> <span data-ttu-id="d1c3d-206">Используется при регистрации нескольких репозиториев.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-206">Used when multiple repositories are registered.</span></span> <span data-ttu-id="d1c3d-207">Принимает разделенный запятыми список репозиториев.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-207">Accepts a comma-separated list of repositories.</span></span> <span data-ttu-id="d1c3d-208">Чтобы зарегистрировать репозиторий, используйте `Register-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="d1c3d-208">To register a repository, use `Register-PSRepository`.</span></span> <span data-ttu-id="d1c3d-209">Чтобы отобразить зарегистрированные репозитории, используйте `Get-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="d1c3d-209">To display registered repositories, use `Get-PSRepository`.</span></span>

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

### <span data-ttu-id="d1c3d-210">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="d1c3d-210">-RequiredVersion</span></span>

<span data-ttu-id="d1c3d-211">Указывает точный номер версии модуля, который должен быть включен в результаты.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-211">Specifies the exact version number of the module to include in the results.</span></span> <span data-ttu-id="d1c3d-212">Параметр **RequiredVersion** нельзя использовать в той же команде, что и **MinimumVersion** или **MaximumVersion**.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-212">**RequiredVersion** cannot be used in the same command as **MinimumVersion** or **MaximumVersion**.</span></span>

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

### <span data-ttu-id="d1c3d-213">-RoleCapability</span><span class="sxs-lookup"><span data-stu-id="d1c3d-213">-RoleCapability</span></span>

<span data-ttu-id="d1c3d-214">Указывает массив возможностей роли.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-214">Specifies an array of role capabilities.</span></span>

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

### <span data-ttu-id="d1c3d-215">-Tag</span><span class="sxs-lookup"><span data-stu-id="d1c3d-215">-Tag</span></span>

<span data-ttu-id="d1c3d-216">Задает массив тегов.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-216">Specifies an array of tags.</span></span> <span data-ttu-id="d1c3d-217">Примеры тегов: **десиредстатеконфигуратион**, **DSC**, **дскресаурцекит** или **PSModule**.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-217">Example tags include **DesiredStateConfiguration**, **DSC**, **DSCResourceKit**, or **PSModule**.</span></span>

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

### <span data-ttu-id="d1c3d-218">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="d1c3d-218">CommonParameters</span></span>

<span data-ttu-id="d1c3d-219">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-219">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d1c3d-220">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d1c3d-220">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d1c3d-221">Входные данные</span><span class="sxs-lookup"><span data-stu-id="d1c3d-221">INPUTS</span></span>

### <span data-ttu-id="d1c3d-222">System.String[]</span><span class="sxs-lookup"><span data-stu-id="d1c3d-222">System.String[]</span></span>

### <span data-ttu-id="d1c3d-223">System.String</span><span class="sxs-lookup"><span data-stu-id="d1c3d-223">System.String</span></span>

### <span data-ttu-id="d1c3d-224">System.Uri</span><span class="sxs-lookup"><span data-stu-id="d1c3d-224">System.Uri</span></span>

### <span data-ttu-id="d1c3d-225">System.Management.Automation.PSCredential</span><span class="sxs-lookup"><span data-stu-id="d1c3d-225">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="d1c3d-226">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="d1c3d-226">OUTPUTS</span></span>

### <span data-ttu-id="d1c3d-227">PSRepositoryItemInfo</span><span class="sxs-lookup"><span data-stu-id="d1c3d-227">PSRepositoryItemInfo</span></span>

<span data-ttu-id="d1c3d-228">`Find-Module` создает объекты **PSRepositoryItemInfo** , которые можно отсылать по конвейеру в командлеты, такие как `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="d1c3d-228">`Find-Module` creates **PSRepositoryItemInfo** objects that can be sent down the pipeline to cmdlets such as `Install-Module`.</span></span>

## <span data-ttu-id="d1c3d-229">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="d1c3d-229">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d1c3d-230">Начиная с апреля 2020 года коллекция PowerShell не поддерживает протокол TLS (Transport Layer Security) версий 1.0 и 1.1.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-230">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="d1c3d-231">Если вы не используете TLS 1.2 или более поздней версии, при попытке доступа к коллекции PowerShell возникнет ошибка.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-231">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="d1c3d-232">Чтобы проверить, используется ли TLS 1.2, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d1c3d-232">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="d1c3d-233">Дополнительные сведения см. в [объявлении](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) в блоге, посвященном PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1c3d-233">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="d1c3d-234">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="d1c3d-234">RELATED LINKS</span></span>

[<span data-ttu-id="d1c3d-235">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="d1c3d-235">Get-PSRepository</span></span>](Get-PSRepository.md)

[<span data-ttu-id="d1c3d-236">Install-Module</span><span class="sxs-lookup"><span data-stu-id="d1c3d-236">Install-Module</span></span>](Install-Module.md)

[<span data-ttu-id="d1c3d-237">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="d1c3d-237">Publish-Module</span></span>](Publish-Module.md)

[<span data-ttu-id="d1c3d-238">Save-Module</span><span class="sxs-lookup"><span data-stu-id="d1c3d-238">Save-Module</span></span>](Save-Module.md)

[<span data-ttu-id="d1c3d-239">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="d1c3d-239">Uninstall-Module</span></span>](Uninstall-Module.md)

[<span data-ttu-id="d1c3d-240">Update-Module</span><span class="sxs-lookup"><span data-stu-id="d1c3d-240">Update-Module</span></span>](Update-Module.md)

[<span data-ttu-id="d1c3d-241">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="d1c3d-241">Register-PSRepository</span></span>](Register-PSRepository.md)
