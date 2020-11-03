---
external help file: PSModule-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PowerShellGet
ms.date: 03/11/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/find-module?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-Module
ms.openlocfilehash: 5795d48b2b76b4853d80d0cd79cb99d62332a39b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228669"
---
# <span data-ttu-id="4b1bb-103">Find-Module</span><span class="sxs-lookup"><span data-stu-id="4b1bb-103">Find-Module</span></span>

## <span data-ttu-id="4b1bb-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="4b1bb-104">SYNOPSIS</span></span>
<span data-ttu-id="4b1bb-105">Находит модули в репозитории, соответствующие указанным критериям.</span><span class="sxs-lookup"><span data-stu-id="4b1bb-105">Finds modules in a repository that match specified criteria.</span></span>

## <span data-ttu-id="4b1bb-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4b1bb-106">SYNTAX</span></span>

### <span data-ttu-id="4b1bb-107">Все</span><span class="sxs-lookup"><span data-stu-id="4b1bb-107">All</span></span>

```
Find-Module [[-Name] <string[]>] [-MinimumVersion <string>] [-MaximumVersion <string>]
 [-RequiredVersion <string>] [-AllVersions] [-IncludeDependencies] [-Filter <string>]
 [-Tag <string[]>] [-Includes <string[]>] [-DscResource <string[]>] [-RoleCapability <string[]>]
 [-Command <string[]>] [-Proxy <uri>] [-ProxyCredential <pscredential>] [-Repository <string[]>]
 [-Credential <pscredential>] [-AllowPrerelease] [<CommonParameters>]
```

## <span data-ttu-id="4b1bb-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4b1bb-108">DESCRIPTION</span></span>

<span data-ttu-id="4b1bb-109">`Find-Module`Командлет находит модули в репозитории, соответствующие указанным критериям.</span><span class="sxs-lookup"><span data-stu-id="4b1bb-109">The `Find-Module` cmdlet finds modules in a repository that match the specified criteria.</span></span>
<span data-ttu-id="4b1bb-110">`Find-Module` Возвращает объект **PSRepositoryItemInfo** для каждого найденного модуля.</span><span class="sxs-lookup"><span data-stu-id="4b1bb-110">`Find-Module` returns a **PSRepositoryItemInfo** object for each module it finds.</span></span> <span data-ttu-id="4b1bb-111">Объекты можно отсылать по конвейеру в командлеты, такие как `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="4b1bb-111">The objects can be sent down the pipeline to cmdlets such as `Install-Module`.</span></span>

<span data-ttu-id="4b1bb-112">В первый раз `Find-Module` при попытке использовать репозиторий может быть предложено установить обновления.</span><span class="sxs-lookup"><span data-stu-id="4b1bb-112">The first time `Find-Module` attempts to use a repository, you might be prompted to install updates.</span></span>
<span data-ttu-id="4b1bb-113">Если источник репозитория не зарегистрирован с помощью `Register-PSRepository` командлета, возвращается ошибка.</span><span class="sxs-lookup"><span data-stu-id="4b1bb-113">If the repository source is not registered with `Register-PSRepository` cmdlet, an error is returned.</span></span>

<span data-ttu-id="4b1bb-114">`Find-Module` Возвращает последнюю версию модуля, если не используются параметры, ограничивающие версию.</span><span class="sxs-lookup"><span data-stu-id="4b1bb-114">`Find-Module` returns the newest version of a module if no parameters are used that limit the version.</span></span> <span data-ttu-id="4b1bb-115">Чтобы получить список версий модуля для репозитория, используйте параметр **AllVersions** .</span><span class="sxs-lookup"><span data-stu-id="4b1bb-115">To get a repository's list of a module's versions, use the parameter **AllVersions** .</span></span>

<span data-ttu-id="4b1bb-116">Если указан параметр **MinimumVersion** , `Find-Module` возвращает версию модуля, которая больше или равна минимальному значению.</span><span class="sxs-lookup"><span data-stu-id="4b1bb-116">If the **MinimumVersion** parameter is specified, `Find-Module` returns the module's version that is equal to or greater than the minimum.</span></span> <span data-ttu-id="4b1bb-117">Если в репозитории доступна более новая версия, возвращается более новая версия.</span><span class="sxs-lookup"><span data-stu-id="4b1bb-117">If there is a newer version available in the repository, the newer version is returned.</span></span>

<span data-ttu-id="4b1bb-118">Если указан параметр **MaximumVersion** , `Find-Module` возвращает последнюю версию модуля, которая не превышает указанную версию.</span><span class="sxs-lookup"><span data-stu-id="4b1bb-118">If the **MaximumVersion** parameter is specified, `Find-Module` returns the newest version of the module that does not exceed the version specified.</span></span>

<span data-ttu-id="4b1bb-119">Если указан параметр **RequiredVersion** , то `Find-Module` возвращает только версию модуля, точно совпадающую с указанной версией.</span><span class="sxs-lookup"><span data-stu-id="4b1bb-119">If the **RequiredVersion** parameter is specified, `Find-Module` only returns the module version that is an exact match to the specified version.</span></span> <span data-ttu-id="4b1bb-120">`Find-Module` выполняет поиск во всех доступных модулях, так как может происходить конфликт имен между источниками.</span><span class="sxs-lookup"><span data-stu-id="4b1bb-120">`Find-Module` searches through all available modules, because name conflicts between sources can occur.</span></span>

<span data-ttu-id="4b1bb-121">В следующих примерах используется [коллекция PowerShell](https://www.powershellgallery.com/) в качестве единственного зарегистрированного репозитория.</span><span class="sxs-lookup"><span data-stu-id="4b1bb-121">The following examples use the [PowerShell Gallery](https://www.powershellgallery.com/) as the only registered repository.</span></span> <span data-ttu-id="4b1bb-122">`Get-PSRepository` отображает зарегистрированные репозитории.</span><span class="sxs-lookup"><span data-stu-id="4b1bb-122">`Get-PSRepository` displays the registered repositories.</span></span> <span data-ttu-id="4b1bb-123">Если у вас есть несколько зарегистрированных репозиториев, используйте `-Repository` параметр, чтобы указать имя репозитория.</span><span class="sxs-lookup"><span data-stu-id="4b1bb-123">If you have multiple registered repositories, use the `-Repository` parameter to specify the repository's name.</span></span>

## <span data-ttu-id="4b1bb-124">Примеры</span><span class="sxs-lookup"><span data-stu-id="4b1bb-124">EXAMPLES</span></span>

### <span data-ttu-id="4b1bb-125">Пример 1. Поиск модуля по имени</span><span class="sxs-lookup"><span data-stu-id="4b1bb-125">Example 1: Find a module by name</span></span>

<span data-ttu-id="4b1bb-126">В этом примере выполняется поиск модуля в репозитории по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4b1bb-126">This example finds a module in the default repository.</span></span>

```powershell
Find-Module -Name PowerShellGet
```

```Output
Version   Name              Repository           Description
-------   ----              ----------           -----------
2.1.0     PowerShellGet     PSGallery            PowerShell module with commands for discovering...
```

<span data-ttu-id="4b1bb-127">`Find-Module`Командлет использует параметр **Name** для указания модуля **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="4b1bb-127">The `Find-Module` cmdlet uses the **Name** parameter to specify the **PowerShellGet** module.</span></span>

### <span data-ttu-id="4b1bb-128">Пример 2. Поиск модулей с одинаковыми именами</span><span class="sxs-lookup"><span data-stu-id="4b1bb-128">Example 2: Find modules with similar names</span></span>

<span data-ttu-id="4b1bb-129">В этом примере используется `*` подстановочный знак звездочки () для поиска модулей с похожими именами.</span><span class="sxs-lookup"><span data-stu-id="4b1bb-129">This example uses the asterisk (`*`) wildcard to find modules with similar names.</span></span>

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

<span data-ttu-id="4b1bb-130">`Find-Module` **Name** `*` Для поиска всех модулей, содержащих **PowerShell** , командлет использует параметр Name с подстановочным знаком звездочки ().</span><span class="sxs-lookup"><span data-stu-id="4b1bb-130">The `Find-Module` cmdlet uses the **Name** parameter with the asterisk (`*`) wildcard to find all modules that contain **PowerShell** .</span></span>

### <span data-ttu-id="4b1bb-131">Пример 3. Поиск модуля по минимальной версии</span><span class="sxs-lookup"><span data-stu-id="4b1bb-131">Example 3: Find a module by minimum version</span></span>

<span data-ttu-id="4b1bb-132">В этом примере выполняется поиск минимальной версии модуля.</span><span class="sxs-lookup"><span data-stu-id="4b1bb-132">This example searches for a module's minimum version.</span></span> <span data-ttu-id="4b1bb-133">Если репозиторий содержит более новую версию модуля, возвращается более новая версия.</span><span class="sxs-lookup"><span data-stu-id="4b1bb-133">If the repository contains a newer version of the module, the newer version is returned.</span></span>

```powershell
Find-Module -Name PowerShellGet -MinimumVersion 1.6.5
```

```Output
Version   Name             Repository     Description
-------   ----             ----------     -----------
2.1.0     PowerShellGet    PSGallery      PowerShell module with commands for discovering...
```

<span data-ttu-id="4b1bb-134">`Find-Module`Командлет использует параметр **Name** для указания модуля **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="4b1bb-134">The `Find-Module` cmdlet uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="4b1bb-135">Параметр **MinimumVersion** указывает версию **1.6.5** .</span><span class="sxs-lookup"><span data-stu-id="4b1bb-135">The **MinimumVersion** specifies version **1.6.5** .</span></span> <span data-ttu-id="4b1bb-136">`Find-Module` Возвращает PowerShellGet версии **2.1.0** , так как она превышает минимальную версию и является самой последней версией.</span><span class="sxs-lookup"><span data-stu-id="4b1bb-136">`Find-Module` returns PowerShellGet version **2.1.0** because it exceeds the minimum version and is the most current version.</span></span>

### <span data-ttu-id="4b1bb-137">Пример 4. Поиск модуля по определенной версии</span><span class="sxs-lookup"><span data-stu-id="4b1bb-137">Example 4: Find a module by specific version</span></span>

<span data-ttu-id="4b1bb-138">В этом примере возвращается объект, представляющий конкретную версию модуля.</span><span class="sxs-lookup"><span data-stu-id="4b1bb-138">This example returns an object that represents a module's specific version.</span></span> <span data-ttu-id="4b1bb-139">Если указанная версия не найдена, возвращается ошибка.</span><span class="sxs-lookup"><span data-stu-id="4b1bb-139">If the specified version is not found, an error is returned.</span></span>

```powershell
Find-Module -Name PowerShellGet -RequiredVersion 1.6.5
```

```Output
Version   Name             Repository     Description
-------   ----             ----------     -----------
1.6.5     PowerShellGet    PSGallery      PowerShell module with commands for discovering...
```

<span data-ttu-id="4b1bb-140">`Find-Module`Командлет использует параметр **Name** для указания модуля **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="4b1bb-140">The `Find-Module` cmdlet uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="4b1bb-141">Параметр **RequiredVersion** указывает версию **1.6.5** .</span><span class="sxs-lookup"><span data-stu-id="4b1bb-141">The **RequiredVersion** parameter specifies version **1.6.5** .</span></span>

### <span data-ttu-id="4b1bb-142">Пример 5. Поиск модуля в определенном репозитории</span><span class="sxs-lookup"><span data-stu-id="4b1bb-142">Example 5: Find a module in a specific repository</span></span>

<span data-ttu-id="4b1bb-143">В этом примере используется параметр **репозитория** для поиска модуля в определенном репозитории.</span><span class="sxs-lookup"><span data-stu-id="4b1bb-143">This example uses the **Repository** parameter to find a module in a specific repository.</span></span>

```powershell
Find-Module -Name PowerShellGet -Repository PSGallery
```

```Output
Version   Name             Repository     Description
-------   ----             ----------     -----------
2.1.0     PowerShellGet    PSGallery      PowerShell module with commands for discovering...
```

<span data-ttu-id="4b1bb-144">`Find-Module`Командлет использует параметр **Name** для указания модуля **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="4b1bb-144">The `Find-Module` cmdlet uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="4b1bb-145">Параметр **репозитория** задает поиск в репозитории **PSGallery** .</span><span class="sxs-lookup"><span data-stu-id="4b1bb-145">The **Repository** parameter specifies to search the **PSGallery** repository.</span></span>

### <span data-ttu-id="4b1bb-146">Пример 6. Поиск модуля в нескольких репозиториях</span><span class="sxs-lookup"><span data-stu-id="4b1bb-146">Example 6: Find a module in multiple repositories</span></span>

<span data-ttu-id="4b1bb-147">В этом примере используется `Register-PSRepository` для указания репозитория.</span><span class="sxs-lookup"><span data-stu-id="4b1bb-147">This example uses the `Register-PSRepository` to specify a repository.</span></span> <span data-ttu-id="4b1bb-148">`Find-Module` использует репозиторий для поиска модуля.</span><span class="sxs-lookup"><span data-stu-id="4b1bb-148">`Find-Module` uses the repository to search for a module.</span></span>

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

<span data-ttu-id="4b1bb-149">`Register-PSRepository`Командлет регистрирует новый репозиторий.</span><span class="sxs-lookup"><span data-stu-id="4b1bb-149">The `Register-PSRepository` cmdlet registers a new repository.</span></span> <span data-ttu-id="4b1bb-150">Параметр **Name** назначает имя **mysource** .</span><span class="sxs-lookup"><span data-stu-id="4b1bb-150">The **Name** parameter assigns the name **MySource** .</span></span> <span data-ttu-id="4b1bb-151">Параметр **SourceLocation** указывает адрес репозитория.</span><span class="sxs-lookup"><span data-stu-id="4b1bb-151">The **SourceLocation** parameter specifies the repository's address.</span></span>

<span data-ttu-id="4b1bb-152">`Find-Module`Командлет использует параметр **Name** с подстановочным знаком звездочки ( `*` ) для указания модуля **contoso** .</span><span class="sxs-lookup"><span data-stu-id="4b1bb-152">The `Find-Module` cmdlet uses the **Name** parameter with the asterisk (`*`) wildcard to specify the **Contoso** module.</span></span> <span data-ttu-id="4b1bb-153">Параметр **репозитория** определяет Поиск двух репозиториев, **PSGallery** и **mysource** .</span><span class="sxs-lookup"><span data-stu-id="4b1bb-153">The **Repository** parameter specifies to search two repositories, **PSGallery** and **MySource** .</span></span>

### <span data-ttu-id="4b1bb-154">Пример 7. Поиск модуля, содержащего ресурс DSC</span><span class="sxs-lookup"><span data-stu-id="4b1bb-154">Example 7: Find a module that contains a DSC resource</span></span>

<span data-ttu-id="4b1bb-155">Эта команда возвращает модули, которые содержат ресурсы DSC.</span><span class="sxs-lookup"><span data-stu-id="4b1bb-155">This command returns modules that contain DSC resources.</span></span> <span data-ttu-id="4b1bb-156">Параметр **включает** четыре стандартные функции, которые используются для поиска в репозитории.</span><span class="sxs-lookup"><span data-stu-id="4b1bb-156">The **Includes** parameter has four predefined functionalities that are used to search the repository.</span></span> <span data-ttu-id="4b1bb-157">Используйте клавишу TAB для вывода четырех функций, поддерживаемых параметром **включает** .</span><span class="sxs-lookup"><span data-stu-id="4b1bb-157">Use tab-complete to display the four functionalities supported by the **Includes** parameter.</span></span>

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

<span data-ttu-id="4b1bb-158">`Find-Module`Командлет использует параметр **репозитория** для поиска в репозитории, **PSGallery** .</span><span class="sxs-lookup"><span data-stu-id="4b1bb-158">The `Find-Module` cmdlet uses the **Repository** parameter to search the repository, **PSGallery** .</span></span>
<span data-ttu-id="4b1bb-159">Параметр **содержит** указывает **DscResource** , которая является функцией, которую параметр может искать в репозитории.</span><span class="sxs-lookup"><span data-stu-id="4b1bb-159">The **Includes** parameter specifies **DscResource** , which is a functionality that the parameter can search for in the repository.</span></span>

### <span data-ttu-id="4b1bb-160">Пример 8. Поиск модуля с фильтром</span><span class="sxs-lookup"><span data-stu-id="4b1bb-160">Example 8: Find a module with a filter</span></span>

<span data-ttu-id="4b1bb-161">В этом примере, чтобы найти модули, используется фильтр для поиска в репозитории.</span><span class="sxs-lookup"><span data-stu-id="4b1bb-161">In this example, to find modules, a filter is used to search the repository.</span></span>

<span data-ttu-id="4b1bb-162">Для репозитория на основе NuGet параметр **Filter** выполняет поиск по имени, описанию и тегам для аргумента.</span><span class="sxs-lookup"><span data-stu-id="4b1bb-162">For a NuGet-based repository, the **Filter** parameter searches through the name, description, and tags for the argument.</span></span>

```powershell
Find-Module -Filter AppDomain
```

```Output
Version    Name              Repository           Description
-------    ----              ----------           -----------
1.0.0.0  AppDomainConfig     PSGallery            Manipulate AppDomain configuration...
1.1.0    ClassExplorer       PSGallery            Quickly search the AppDomain for classes...
```

<span data-ttu-id="4b1bb-163">`Find-Module`Командлет использует параметр **Filter** для поиска в репозитории для **AppDomain** .</span><span class="sxs-lookup"><span data-stu-id="4b1bb-163">The `Find-Module` cmdlet uses the **Filter** parameter to search the repository for **AppDomain** .</span></span>

## <span data-ttu-id="4b1bb-164">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4b1bb-164">PARAMETERS</span></span>

### <span data-ttu-id="4b1bb-165">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="4b1bb-165">-AllowPrerelease</span></span>

<span data-ttu-id="4b1bb-166">Включает в модули результатов, помеченные как предварительные версии.</span><span class="sxs-lookup"><span data-stu-id="4b1bb-166">Includes in the results modules marked as a pre-release.</span></span>

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

### <span data-ttu-id="4b1bb-167">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="4b1bb-167">-AllVersions</span></span>

<span data-ttu-id="4b1bb-168">Указывает, что в результаты включаются все версии модуля.</span><span class="sxs-lookup"><span data-stu-id="4b1bb-168">Specifies to include all versions of a module in the results.</span></span> <span data-ttu-id="4b1bb-169">Параметр **AllVersions** нельзя использовать с параметрами **MinimumVersion** , **MaximumVersion** или **RequiredVersion** .</span><span class="sxs-lookup"><span data-stu-id="4b1bb-169">You cannot use the **AllVersions** parameter with the **MinimumVersion** , **MaximumVersion** , or **RequiredVersion** parameters.</span></span>

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

### <span data-ttu-id="4b1bb-170">-Command</span><span class="sxs-lookup"><span data-stu-id="4b1bb-170">-Command</span></span>

<span data-ttu-id="4b1bb-171">Указывает массив команд для поиска в модулях.</span><span class="sxs-lookup"><span data-stu-id="4b1bb-171">Specifies an array of commands to find in modules.</span></span> <span data-ttu-id="4b1bb-172">Команда может быть функцией или рабочим процессом.</span><span class="sxs-lookup"><span data-stu-id="4b1bb-172">A command can be a function or workflow.</span></span>

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

### <span data-ttu-id="4b1bb-173">-Credential</span><span class="sxs-lookup"><span data-stu-id="4b1bb-173">-Credential</span></span>

<span data-ttu-id="4b1bb-174">Указывает учетную запись пользователя, имеющую права на установку модуля для указанного поставщика пакетов или источника.</span><span class="sxs-lookup"><span data-stu-id="4b1bb-174">Specifies a user account that has rights to install a module for a specified package provider or source.</span></span>

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

### <span data-ttu-id="4b1bb-175">-DscResource</span><span class="sxs-lookup"><span data-stu-id="4b1bb-175">-DscResource</span></span>

<span data-ttu-id="4b1bb-176">Задает имя или часть имени модулей, содержащих ресурсы DSC.</span><span class="sxs-lookup"><span data-stu-id="4b1bb-176">Specifies the name, or part of the name, of modules that contain DSC resources.</span></span> <span data-ttu-id="4b1bb-177">Для каждого соглашения PowerShell выполняет поиск **или** , если вы предоставляете несколько аргументов.</span><span class="sxs-lookup"><span data-stu-id="4b1bb-177">Per PowerShell conventions, performs an **OR** search when you provide multiple arguments.</span></span>

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

### <span data-ttu-id="4b1bb-178">-Filter</span><span class="sxs-lookup"><span data-stu-id="4b1bb-178">-Filter</span></span>

<span data-ttu-id="4b1bb-179">Задает фильтр на основе синтаксиса поиска, зависящего от поставщика **PackageManagement** .</span><span class="sxs-lookup"><span data-stu-id="4b1bb-179">Specifies a filter based on the **PackageManagement** provider-specific search syntax.</span></span> <span data-ttu-id="4b1bb-180">Для модулей NuGet этот параметр эквивалентен поиску с помощью панели поиска на веб-сайте [коллекция PowerShell](https://www.powershellgallery.com/) .</span><span class="sxs-lookup"><span data-stu-id="4b1bb-180">For NuGet modules, this parameter is the equivalent of searching by using the Search bar on the [PowerShell Gallery](https://www.powershellgallery.com/) website.</span></span>

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

### <span data-ttu-id="4b1bb-181">-IncludeDependencies</span><span class="sxs-lookup"><span data-stu-id="4b1bb-181">-IncludeDependencies</span></span>

<span data-ttu-id="4b1bb-182">Указывает, что эта операция включает все модули, зависящие от модуля, указанного в параметре **Name** .</span><span class="sxs-lookup"><span data-stu-id="4b1bb-182">Indicates that this operation includes all modules that are dependent upon the module specified in the **Name** parameter.</span></span>

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

### <span data-ttu-id="4b1bb-183">— Включает</span><span class="sxs-lookup"><span data-stu-id="4b1bb-183">-Includes</span></span>

<span data-ttu-id="4b1bb-184">Возвращает только те модули, которые включают в себя определенные виды функций PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4b1bb-184">Returns only those modules that include specific kinds of PowerShell functionality.</span></span> <span data-ttu-id="4b1bb-185">Например, может потребоваться найти только модули, включающие **DSCResource** .</span><span class="sxs-lookup"><span data-stu-id="4b1bb-185">For example, you might only want to find modules that include **DSCResource** .</span></span> <span data-ttu-id="4b1bb-186">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="4b1bb-186">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="4b1bb-187">Командлет</span><span class="sxs-lookup"><span data-stu-id="4b1bb-187">Cmdlet</span></span>
- <span data-ttu-id="4b1bb-188">DscResource</span><span class="sxs-lookup"><span data-stu-id="4b1bb-188">DscResource</span></span>
- <span data-ttu-id="4b1bb-189">Компонент</span><span class="sxs-lookup"><span data-stu-id="4b1bb-189">Function</span></span>
- <span data-ttu-id="4b1bb-190">RoleCapability</span><span class="sxs-lookup"><span data-stu-id="4b1bb-190">RoleCapability</span></span>

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

### <span data-ttu-id="4b1bb-191">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="4b1bb-191">-MaximumVersion</span></span>

<span data-ttu-id="4b1bb-192">Указывает максимальную или последнюю версию модуля для включения в результаты поиска.</span><span class="sxs-lookup"><span data-stu-id="4b1bb-192">Specifies the maximum, or latest, version of the module to include in the search results.</span></span>
<span data-ttu-id="4b1bb-193">В одной команде нельзя использовать **MaximumVersion** и **RequiredVersion** .</span><span class="sxs-lookup"><span data-stu-id="4b1bb-193">**MaximumVersion** and **RequiredVersion** cannot be used in the same command.</span></span>

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

### <span data-ttu-id="4b1bb-194">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="4b1bb-194">-MinimumVersion</span></span>

<span data-ttu-id="4b1bb-195">Указывает минимальную версию модуля для включения в результаты.</span><span class="sxs-lookup"><span data-stu-id="4b1bb-195">Specifies the minimum version of the module to include in results.</span></span> <span data-ttu-id="4b1bb-196">В одной команде нельзя использовать **MinimumVersion** и **RequiredVersion** .</span><span class="sxs-lookup"><span data-stu-id="4b1bb-196">**MinimumVersion** and **RequiredVersion** cannot be used in the same command.</span></span>

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

### <span data-ttu-id="4b1bb-197">-Name</span><span class="sxs-lookup"><span data-stu-id="4b1bb-197">-Name</span></span>

<span data-ttu-id="4b1bb-198">Указывает имена модулей для поиска в репозитории.</span><span class="sxs-lookup"><span data-stu-id="4b1bb-198">Specifies the names of modules to search for in the repository.</span></span> <span data-ttu-id="4b1bb-199">Принимается список имен модулей с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="4b1bb-199">A comma-separated list of module names is accepted.</span></span> <span data-ttu-id="4b1bb-200">Подстановочные знаки принимаются.</span><span class="sxs-lookup"><span data-stu-id="4b1bb-200">Wildcards are accepted.</span></span>

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

### <span data-ttu-id="4b1bb-201">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="4b1bb-201">-Proxy</span></span>

<span data-ttu-id="4b1bb-202">Указывает прокси-сервер для запроса, а не напрямуюе подключение к Интернет-ресурсу.</span><span class="sxs-lookup"><span data-stu-id="4b1bb-202">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

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

### <span data-ttu-id="4b1bb-203">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="4b1bb-203">-ProxyCredential</span></span>

<span data-ttu-id="4b1bb-204">Указывает учетную запись пользователя, имеющую разрешение на использование прокси-сервера, который задается параметром **Proxy** .</span><span class="sxs-lookup"><span data-stu-id="4b1bb-204">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="4b1bb-205">— Репозиторий;</span><span class="sxs-lookup"><span data-stu-id="4b1bb-205">-Repository</span></span>

<span data-ttu-id="4b1bb-206">Используйте параметр **репозитория** , чтобы указать репозиторий для поиска модуля.</span><span class="sxs-lookup"><span data-stu-id="4b1bb-206">Use the **Repository** parameter to specify which repository to search for a module.</span></span> <span data-ttu-id="4b1bb-207">Используется при регистрации нескольких репозиториев.</span><span class="sxs-lookup"><span data-stu-id="4b1bb-207">Used when multiple repositories are registered.</span></span> <span data-ttu-id="4b1bb-208">Принимает разделенный запятыми список репозиториев.</span><span class="sxs-lookup"><span data-stu-id="4b1bb-208">Accepts a comma-separated list of repositories.</span></span> <span data-ttu-id="4b1bb-209">Чтобы зарегистрировать репозиторий, используйте `Register-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="4b1bb-209">To register a repository, use `Register-PSRepository`.</span></span> <span data-ttu-id="4b1bb-210">Чтобы отобразить зарегистрированные репозитории, используйте `Get-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="4b1bb-210">To display registered repositories, use `Get-PSRepository`.</span></span>

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

### <span data-ttu-id="4b1bb-211">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="4b1bb-211">-RequiredVersion</span></span>

<span data-ttu-id="4b1bb-212">Указывает точный номер версии модуля, который должен быть включен в результаты.</span><span class="sxs-lookup"><span data-stu-id="4b1bb-212">Specifies the exact version number of the module to include in the results.</span></span> <span data-ttu-id="4b1bb-213">Параметр **RequiredVersion** нельзя использовать в той же команде, что и **MinimumVersion** или **MaximumVersion** .</span><span class="sxs-lookup"><span data-stu-id="4b1bb-213">**RequiredVersion** cannot be used in the same command as **MinimumVersion** or **MaximumVersion** .</span></span>

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

### <span data-ttu-id="4b1bb-214">-RoleCapability</span><span class="sxs-lookup"><span data-stu-id="4b1bb-214">-RoleCapability</span></span>

<span data-ttu-id="4b1bb-215">Указывает массив возможностей роли.</span><span class="sxs-lookup"><span data-stu-id="4b1bb-215">Specifies an array of role capabilities.</span></span>

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

### <span data-ttu-id="4b1bb-216">-Tag</span><span class="sxs-lookup"><span data-stu-id="4b1bb-216">-Tag</span></span>

<span data-ttu-id="4b1bb-217">Задает массив тегов.</span><span class="sxs-lookup"><span data-stu-id="4b1bb-217">Specifies an array of tags.</span></span> <span data-ttu-id="4b1bb-218">Примеры тегов: **десиредстатеконфигуратион** , **DSC** , **дскресаурцекит** или **PSModule** .</span><span class="sxs-lookup"><span data-stu-id="4b1bb-218">Example tags include **DesiredStateConfiguration** , **DSC** , **DSCResourceKit** , or **PSModule** .</span></span>

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

### <span data-ttu-id="4b1bb-219">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="4b1bb-219">CommonParameters</span></span>

<span data-ttu-id="4b1bb-220">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4b1bb-220">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4b1bb-221">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4b1bb-221">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4b1bb-222">Входные данные</span><span class="sxs-lookup"><span data-stu-id="4b1bb-222">INPUTS</span></span>

### <span data-ttu-id="4b1bb-223">System.String[]</span><span class="sxs-lookup"><span data-stu-id="4b1bb-223">System.String[]</span></span>

### <span data-ttu-id="4b1bb-224">System.String</span><span class="sxs-lookup"><span data-stu-id="4b1bb-224">System.String</span></span>

### <span data-ttu-id="4b1bb-225">System.Uri</span><span class="sxs-lookup"><span data-stu-id="4b1bb-225">System.Uri</span></span>

### <span data-ttu-id="4b1bb-226">System.Management.Automation.PSCredential</span><span class="sxs-lookup"><span data-stu-id="4b1bb-226">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="4b1bb-227">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="4b1bb-227">OUTPUTS</span></span>

### <span data-ttu-id="4b1bb-228">PSRepositoryItemInfo</span><span class="sxs-lookup"><span data-stu-id="4b1bb-228">PSRepositoryItemInfo</span></span>

<span data-ttu-id="4b1bb-229">`Find-Module` создает объекты **PSRepositoryItemInfo** , которые можно отсылать по конвейеру в командлеты, такие как `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="4b1bb-229">`Find-Module` creates **PSRepositoryItemInfo** objects that can be sent down the pipeline to cmdlets such as `Install-Module`.</span></span>

## <span data-ttu-id="4b1bb-230">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="4b1bb-230">NOTES</span></span>

<span data-ttu-id="4b1bb-231">Этот командлет выполняется в PowerShell 5,0 или более поздних версиях PowerShell, в Windows 7 или Windows 2008 R2 и более поздних версиях Windows.</span><span class="sxs-lookup"><span data-stu-id="4b1bb-231">This cmdlet runs on PowerShell 5.0 or later releases of PowerShell, on Windows 7, or Windows 2008 R2 and later releases of Windows.</span></span>

## <span data-ttu-id="4b1bb-232">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="4b1bb-232">RELATED LINKS</span></span>

[<span data-ttu-id="4b1bb-233">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="4b1bb-233">Get-PSRepository</span></span>](Get-PSRepository.md)

[<span data-ttu-id="4b1bb-234">Install-Module</span><span class="sxs-lookup"><span data-stu-id="4b1bb-234">Install-Module</span></span>](Install-Module.md)

[<span data-ttu-id="4b1bb-235">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="4b1bb-235">Publish-Module</span></span>](Publish-Module.md)

[<span data-ttu-id="4b1bb-236">Save-Module</span><span class="sxs-lookup"><span data-stu-id="4b1bb-236">Save-Module</span></span>](Save-Module.md)

[<span data-ttu-id="4b1bb-237">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="4b1bb-237">Uninstall-Module</span></span>](Uninstall-Module.md)

[<span data-ttu-id="4b1bb-238">Update-Module</span><span class="sxs-lookup"><span data-stu-id="4b1bb-238">Update-Module</span></span>](Update-Module.md)

[<span data-ttu-id="4b1bb-239">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="4b1bb-239">Register-PSRepository</span></span>](Register-PSRepository.md)
