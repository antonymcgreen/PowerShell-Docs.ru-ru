---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
Locale: en-US
Module Name: PackageManagement
ms.date: 04/03/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/find-package?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-Package
ms.openlocfilehash: c45ff8443818580dcc57cd1a945822007ae259a8
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "99604111"
---
# <span data-ttu-id="e4432-102">Find-Package</span><span class="sxs-lookup"><span data-stu-id="e4432-102">Find-Package</span></span>

## <span data-ttu-id="e4432-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="e4432-103">SYNOPSIS</span></span>
<span data-ttu-id="e4432-104">Находит пакеты программного обеспечения в доступных источниках пакетов.</span><span class="sxs-lookup"><span data-stu-id="e4432-104">Finds software packages in available package sources.</span></span>

## <span data-ttu-id="e4432-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e4432-105">SYNTAX</span></span>

### <span data-ttu-id="e4432-106">NuGet</span><span class="sxs-lookup"><span data-stu-id="e4432-106">NuGet</span></span>

```
Find-Package [-IncludeDependencies] [-AllVersions] [-Source <String[]>] [-Credential <PSCredential>]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [[-Name] <String[]>] [-RequiredVersion <String>]
 [-MinimumVersion <String>] [-MaximumVersion <String>] [-Force] [-ForceBootstrap]
 [-ProviderName <String[]>] [-ConfigFile <String>] [-SkipValidate] [-Headers <String[]>]
 [-FilterOnTag <String[]>] [-Contains <String>] [-AllowPrereleaseVersions] [<CommonParameters>]
```

### <span data-ttu-id="e4432-107">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="e4432-107">PowerShellGet</span></span>

```
Find-Package [-IncludeDependencies] [-AllVersions] [-Source <String[]>] [-Credential <PSCredential>]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [[-Name] <String[]>] [-RequiredVersion <String>]
 [-MinimumVersion <String>] [-MaximumVersion <String>] [-Force] [-ForceBootstrap]
 [-ProviderName <String[]>] [-AllowPrereleaseVersions] [-PackageManagementProvider <String>]
 [-PublishLocation <String>] [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>]
 [-Type <String>] [-Filter <String>] [-Tag <String[]>] [-Includes <String[]>]
 [-DscResource <String[]>] [-RoleCapability <String[]>] [-Command <String[]>] [-AcceptLicense]
 [<CommonParameters>]
```

## <span data-ttu-id="e4432-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e4432-108">DESCRIPTION</span></span>

<span data-ttu-id="e4432-109">`Find-Package` находит пакеты программного обеспечения, доступные в источниках пакетов.</span><span class="sxs-lookup"><span data-stu-id="e4432-109">`Find-Package` finds software packages that are available in package sources.</span></span> <span data-ttu-id="e4432-110">`Get-PackageProvider` и `Get-PackageSource` отобразит сведения о поставщиках.</span><span class="sxs-lookup"><span data-stu-id="e4432-110">`Get-PackageProvider` and `Get-PackageSource` display details about your providers.</span></span>

## <span data-ttu-id="e4432-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="e4432-111">EXAMPLES</span></span>

### <span data-ttu-id="e4432-112">Пример 1. Поиск всех доступных пакетов от поставщика пакетов</span><span class="sxs-lookup"><span data-stu-id="e4432-112">Example 1: Find all available packages from a package provider</span></span>

<span data-ttu-id="e4432-113">Эта команда находит все доступные пакеты модулей PowerShell в зарегистрированной коллекции.</span><span class="sxs-lookup"><span data-stu-id="e4432-113">This command finds all available PowerShell module packages in a registered gallery.</span></span> <span data-ttu-id="e4432-114">Используйте `Get-PackageProvider` для получения имени поставщика.</span><span class="sxs-lookup"><span data-stu-id="e4432-114">Use `Get-PackageProvider` to get the provider name.</span></span>

```
Find-Package -ProviderName NuGet
```

```Output
Name               Version   Source     Summary
----               -------   ------     -------
NUnit              3.11.0    MyNuGet    NUnit is a unit-testing framework for all .NET langua...
Newtonsoft.Json    12.0.1    MyNuGet    Json.NET is a popular high-performance JSON framework...
EntityFramework    6.2.0     MyNuGet    Entity Framework is Microsoft's recommended data acce...
MySql.Data         8.0.15    MyNuGet    MySql.Data.MySqlClient .Net Core Class Library
bootstrap          4.3.1     MyNuGet    Bootstrap framework in CSS. Includes fonts and JavaSc...
NuGet.Core         2.14.0    MyNuGet    NuGet.Core is the core framework assembly for NuGet...
```

<span data-ttu-id="e4432-115">`Find-Package` использует параметр **provider** для указания **NuGet** поставщика.</span><span class="sxs-lookup"><span data-stu-id="e4432-115">`Find-Package` uses the **Provider** parameter to specify the provider **NuGet**.</span></span>

### <span data-ttu-id="e4432-116">Пример 2. Поиск пакета из источника пакета</span><span class="sxs-lookup"><span data-stu-id="e4432-116">Example 2: Find a package from a package source</span></span>

<span data-ttu-id="e4432-117">Эта команда находит последнюю версию пакета из указанного источника пакета.</span><span class="sxs-lookup"><span data-stu-id="e4432-117">This command finds the newest version of a package from a specified package source.</span></span> <span data-ttu-id="e4432-118">Если источник пакета не указан, `Find-Package` ищет каждый установленный поставщик пакетов и его источники пакетов.</span><span class="sxs-lookup"><span data-stu-id="e4432-118">If a package source isn't provided, `Find-Package` searches each installed package provider and its package sources.</span></span> <span data-ttu-id="e4432-119">Используйте `Get-PackageSource` для получения имени источника.</span><span class="sxs-lookup"><span data-stu-id="e4432-119">Use `Get-PackageSource` to get the source name.</span></span>

```
Find-Package -Name NuGet.Core -Source MyNuGet
```

```Output
Name         Version   Source    Summary
----         -------   ------    -------
NuGet.Core   2.14.0    MyNuGet   NuGet.Core is the core framework assembly for NuGet...
```

<span data-ttu-id="e4432-120">`Find-Package` использует параметр **Name** для указания имени пакета **NuGet. Core**.</span><span class="sxs-lookup"><span data-stu-id="e4432-120">`Find-Package` uses the **Name** parameter to specify the package name **NuGet.Core**.</span></span> <span data-ttu-id="e4432-121">Параметр **Source** определяет поиск пакета в **минужет**.</span><span class="sxs-lookup"><span data-stu-id="e4432-121">The **Source** parameter specifies to search for the package in **MyNuGet**.</span></span>

### <span data-ttu-id="e4432-122">Пример 3. Поиск всех версий пакета</span><span class="sxs-lookup"><span data-stu-id="e4432-122">Example 3: Find all versions of a package</span></span>

<span data-ttu-id="e4432-123">Эта команда находит все доступные версии пакетов от указанного поставщика.</span><span class="sxs-lookup"><span data-stu-id="e4432-123">This command finds all available package versions from a specified provider.</span></span>

```
Find-Package -Name NuGet.Core -Source MyNuGet -AllVersions
```

```Output
Name          Version          Source       Summary
----          -------          ------       -------
NuGet.Core    2.14.0           MyNuGet      NuGet.Core is the core framework assembly for NuGet...
NuGet.Core    2.14.0-rtm-832   MyNuGet      NuGet.Core is the core framework assembly for NuGet...
NuGet.Core    2.13.0           MyNuGet      NuGet.Core is the core framework assembly for NuGet...
...
NuGet.Core    1.1.229.159      MyNuGet      NuGet.Core is the core framework assembly for NuGet...
Nuget.Core    1.0.1120.104     MyNuGet      NuGet.Core is the core framework assembly for NuGet...
```

<span data-ttu-id="e4432-124">`Find-Package` использует параметр **Name** для указания пакета **NuGet. Core**.</span><span class="sxs-lookup"><span data-stu-id="e4432-124">`Find-Package` uses the **Name** parameter to specify the package **NuGet.Core**.</span></span> <span data-ttu-id="e4432-125">Параметр **providerName** определяет поиск пакета в **минужет**.</span><span class="sxs-lookup"><span data-stu-id="e4432-125">The **ProviderName** parameter specifies to search for the package in **MyNuGet**.</span></span> <span data-ttu-id="e4432-126">**AllVersions** указывает, что возвращаются все доступные версии.</span><span class="sxs-lookup"><span data-stu-id="e4432-126">**AllVersions** specifies that all available versions are returned.</span></span>

### <span data-ttu-id="e4432-127">Пример 4. Поиск пакета с указанным именем и версией</span><span class="sxs-lookup"><span data-stu-id="e4432-127">Example 4: Find a package with a specific name and version</span></span>

<span data-ttu-id="e4432-128">Эта команда находит определенную версию пакета по указанному поставщику.</span><span class="sxs-lookup"><span data-stu-id="e4432-128">This command finds a specific package version from a specified provider.</span></span>

```
Find-Package -Name NuGet.Core -ProviderName NuGet -RequiredVersion 2.9.0
```

```Output
Name          Version          Source       Summary
----          -------          ------       -------
NuGet.Core    2.9.0            MyNuGet      NuGet.Core is the core framework assembly for NuGet...
```

<span data-ttu-id="e4432-129">`Find-Package` использует параметр **Name** для указания имени пакета **NuGet. Core**.</span><span class="sxs-lookup"><span data-stu-id="e4432-129">`Find-Package` uses the **Name** parameter to specify the package name **NuGet.Core**.</span></span> <span data-ttu-id="e4432-130">Параметр **providerName** определяет поиск пакета в **NuGet**.</span><span class="sxs-lookup"><span data-stu-id="e4432-130">The **ProviderName** parameter specifies to search for the package in **NuGet**.</span></span> <span data-ttu-id="e4432-131">**RequiredVersion** указывает, что возвращается только версия **2.9.0** .</span><span class="sxs-lookup"><span data-stu-id="e4432-131">**RequiredVersion** specifies that only version **2.9.0** is returned.</span></span>

### <span data-ttu-id="e4432-132">Пример 5. Поиск пакетов в диапазоне версий</span><span class="sxs-lookup"><span data-stu-id="e4432-132">Example 5: Find packages within a range of versions</span></span>

<span data-ttu-id="e4432-133">Эта команда находит диапазон версий для указанного пакета.</span><span class="sxs-lookup"><span data-stu-id="e4432-133">This command finds a range of versions for a specified package.</span></span>

```
Find-Package -Name NuGet.Core -ProviderName NuGet -MinimumVersion 2.7.0 -MaximumVersion 2.9.0 -AllVersions
```

```Output
Name          Version          Source       Summary
----          -------          ------       -------
NuGet.Core    2.9.0            MyNuGet      NuGet.Core is the core framework assembly for NuGet...
NuGet.Core    2.8.6            MyNuGet      NuGet.Core is the core framework assembly for NuGet...
NuGet.Core    2.8.0            MyNuGet      NuGet.Core is the core framework assembly for NuGet...
NuGet.Core    2.7.0            MyNuGet      NuGet.Core is the core framework assembly for NuGet...
```

<span data-ttu-id="e4432-134">`Find-Package` использует параметр **Name** для указания имени пакета **NuGet. Core**.</span><span class="sxs-lookup"><span data-stu-id="e4432-134">`Find-Package` uses the **Name** parameter to specify the package name **NuGet.Core**.</span></span> <span data-ttu-id="e4432-135">Параметр **providerName** определяет поиск пакета в **NuGet**.</span><span class="sxs-lookup"><span data-stu-id="e4432-135">The **ProviderName** parameter specifies to search for the package in **NuGet**.</span></span> <span data-ttu-id="e4432-136">**MinimumVersion** указывает самую раннюю версию **2.7.0**.</span><span class="sxs-lookup"><span data-stu-id="e4432-136">**MinimumVersion** specifies the lowest version **2.7.0**.</span></span> <span data-ttu-id="e4432-137">**MaximumVersion** указывает самую старшую версию **2.9.0**.</span><span class="sxs-lookup"><span data-stu-id="e4432-137">**MaximumVersion** specifies the highest version **2.9.0**.</span></span>
<span data-ttu-id="e4432-138">**AllVersions** определяет, что диапазон возвращается в соответствии с минимальным и максимальным значением.</span><span class="sxs-lookup"><span data-stu-id="e4432-138">**AllVersions** determines the range is returned as specified by the minimum and maximum.</span></span>

### <span data-ttu-id="e4432-139">Пример 6. Поиск пакета из файловой системы</span><span class="sxs-lookup"><span data-stu-id="e4432-139">Example 6: Find a package from a file system</span></span>

<span data-ttu-id="e4432-140">Эта команда находит пакеты с расширением файла `.nupkg` , которые хранятся на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="e4432-140">This command finds packages with the file extension `.nupkg` that are stored on the local computer.</span></span>
<span data-ttu-id="e4432-141">Файлы — это пакеты, загружаемые из коллекции, например **NuGet**.</span><span class="sxs-lookup"><span data-stu-id="e4432-141">The files are packages downloaded from a gallery such as the **NuGet**.</span></span>

```
PS> Find-Package -Source C:\LocalPkg
```

```Output
Name                 Version    Source           Summary
----                 -------    ------           -------
Microsoft.Web.Xdt    3.0.0      C:\LocalPkg\     Microsoft Xml Document Transformation (XDT)...
NuGet.Core           2.14.0     C:\LocalPkg\     NuGet.Core is the core framework assembly...
```

## <span data-ttu-id="e4432-142">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e4432-142">PARAMETERS</span></span>

### <span data-ttu-id="e4432-143">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="e4432-143">-AcceptLicense</span></span>

<span data-ttu-id="e4432-144">Автоматически принимает лицензионное соглашение, если оно требуется для пакета.</span><span class="sxs-lookup"><span data-stu-id="e4432-144">Automatically accepts a license agreement if the package requires it.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4432-145">-Алловпререлеасеверсионс</span><span class="sxs-lookup"><span data-stu-id="e4432-145">-AllowPrereleaseVersions</span></span>

<span data-ttu-id="e4432-146">Включает пакеты, помеченные как предварительные выпуски в результатах.</span><span class="sxs-lookup"><span data-stu-id="e4432-146">Includes packages marked as a prerelease in the results.</span></span>

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

### <span data-ttu-id="e4432-147">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="e4432-147">-AllVersions</span></span>

<span data-ttu-id="e4432-148">Указывает, что `Find-Package` возвращает все доступные версии пакета.</span><span class="sxs-lookup"><span data-stu-id="e4432-148">Indicates that `Find-Package` returns all available versions of the package.</span></span> <span data-ttu-id="e4432-149">По умолчанию `Find-Package` возвращает только последнюю доступную версию.</span><span class="sxs-lookup"><span data-stu-id="e4432-149">By default, `Find-Package` only returns the newest available version.</span></span>

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

### <span data-ttu-id="e4432-150">-Command</span><span class="sxs-lookup"><span data-stu-id="e4432-150">-Command</span></span>

<span data-ttu-id="e4432-151">Указывает массив команд, в которых выполняется поиск `Find-Package` .</span><span class="sxs-lookup"><span data-stu-id="e4432-151">Specifies an array of commands searched by `Find-Package`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4432-152">-ConfigFile</span><span class="sxs-lookup"><span data-stu-id="e4432-152">-ConfigFile</span></span>

<span data-ttu-id="e4432-153">Указывает файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e4432-153">Specifies a configuration file.</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4432-154">— Содержит</span><span class="sxs-lookup"><span data-stu-id="e4432-154">-Contains</span></span>

<span data-ttu-id="e4432-155">`Find-Package` Возвращает объекты, если любой элемент в значениях свойств объекта является точным соответствием для указанного значения.</span><span class="sxs-lookup"><span data-stu-id="e4432-155">`Find-Package` gets objects if any item in the object's property values are an exact match for the specified value.</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4432-156">-Credential</span><span class="sxs-lookup"><span data-stu-id="e4432-156">-Credential</span></span>

<span data-ttu-id="e4432-157">Указывает учетную запись пользователя, имеющую разрешение на поиск пакетов.</span><span class="sxs-lookup"><span data-stu-id="e4432-157">Specifies a user account that has permission to search for packages.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4432-158">-DscResource</span><span class="sxs-lookup"><span data-stu-id="e4432-158">-DscResource</span></span>

<span data-ttu-id="e4432-159">Указывает массив ресурсов DSC, которые ищет этот командлет.</span><span class="sxs-lookup"><span data-stu-id="e4432-159">Specifies an array of Desired State Configuration (DSC) resources that this cmdlet searches.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4432-160">-Filter</span><span class="sxs-lookup"><span data-stu-id="e4432-160">-Filter</span></span>

<span data-ttu-id="e4432-161">Задает термины для поиска в свойствах **имя** и **Описание** .</span><span class="sxs-lookup"><span data-stu-id="e4432-161">Specifies terms to search for within the **Name** and **Description** properties.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4432-162">-Филтеронтаг</span><span class="sxs-lookup"><span data-stu-id="e4432-162">-FilterOnTag</span></span>

<span data-ttu-id="e4432-163">Указывает тег, фильтрующий результаты.</span><span class="sxs-lookup"><span data-stu-id="e4432-163">Specifies the tag that filters the results.</span></span> <span data-ttu-id="e4432-164">Исключаются результаты, не содержащие указанный тег.</span><span class="sxs-lookup"><span data-stu-id="e4432-164">Results that don't contain the specified tag are excluded.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4432-165">-Force</span><span class="sxs-lookup"><span data-stu-id="e4432-165">-Force</span></span>

<span data-ttu-id="e4432-166">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="e4432-166">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="e4432-167">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="e4432-167">-ForceBootstrap</span></span>

<span data-ttu-id="e4432-168">Указывает, что `Find-Package` заставляет **PackageManagement** автоматически устанавливать поставщик пакетов.</span><span class="sxs-lookup"><span data-stu-id="e4432-168">Indicates that `Find-Package` forces **PackageManagement** to automatically install the package provider.</span></span>

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

### <span data-ttu-id="e4432-169">-Заголовки</span><span class="sxs-lookup"><span data-stu-id="e4432-169">-Headers</span></span>

<span data-ttu-id="e4432-170">Указывает заголовки для пакета.</span><span class="sxs-lookup"><span data-stu-id="e4432-170">Specifies the headers for the package.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4432-171">-IncludeDependencies</span><span class="sxs-lookup"><span data-stu-id="e4432-171">-IncludeDependencies</span></span>

<span data-ttu-id="e4432-172">Указывает, что этот командлет включает в результаты зависимости пакетов.</span><span class="sxs-lookup"><span data-stu-id="e4432-172">Indicates that this cmdlet includes package dependencies in the results.</span></span>

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

### <span data-ttu-id="e4432-173">— Включает</span><span class="sxs-lookup"><span data-stu-id="e4432-173">-Includes</span></span>

<span data-ttu-id="e4432-174">Указывает `Find-Package` , следует ли найти все пакеты в категории.</span><span class="sxs-lookup"><span data-stu-id="e4432-174">Specifies whether `Find-Package` should find all packages within a category.</span></span>

<span data-ttu-id="e4432-175">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="e4432-175">The accepted values are as follows:</span></span>

- <span data-ttu-id="e4432-176">Командлет</span><span class="sxs-lookup"><span data-stu-id="e4432-176">Cmdlet</span></span>
- <span data-ttu-id="e4432-177">DscResource</span><span class="sxs-lookup"><span data-stu-id="e4432-177">DscResource</span></span>
- <span data-ttu-id="e4432-178">Компонент</span><span class="sxs-lookup"><span data-stu-id="e4432-178">Function</span></span>
- <span data-ttu-id="e4432-179">RoleCapability</span><span class="sxs-lookup"><span data-stu-id="e4432-179">RoleCapability</span></span>
- <span data-ttu-id="e4432-180">Рабочий процесс</span><span class="sxs-lookup"><span data-stu-id="e4432-180">Workflow</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet
Aliases:
Accepted values: Cmdlet, DscResource, Function, RoleCapability, Workflow

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4432-181">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="e4432-181">-MaximumVersion</span></span>

<span data-ttu-id="e4432-182">Указывает максимальную версию пакета, которую нужно найти.</span><span class="sxs-lookup"><span data-stu-id="e4432-182">Specifies the maximum package version that you want to find.</span></span>

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

### <span data-ttu-id="e4432-183">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="e4432-183">-MinimumVersion</span></span>

<span data-ttu-id="e4432-184">Указывает минимальную версию пакета, которую нужно найти.</span><span class="sxs-lookup"><span data-stu-id="e4432-184">Specifies the minimum package version that you want to find.</span></span> <span data-ttu-id="e4432-185">Если доступна более высокая версия, возвращается эта версия.</span><span class="sxs-lookup"><span data-stu-id="e4432-185">If a higher version is available, that version is returned.</span></span>

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

### <span data-ttu-id="e4432-186">-Name</span><span class="sxs-lookup"><span data-stu-id="e4432-186">-Name</span></span>

<span data-ttu-id="e4432-187">Указывает одно или несколько имен пакетов или имена пакетов с подстановочными знаками.</span><span class="sxs-lookup"><span data-stu-id="e4432-187">Specifies one or more package names, or package names with wildcard characters.</span></span> <span data-ttu-id="e4432-188">Несколько имен пакетов следует разделять запятыми.</span><span class="sxs-lookup"><span data-stu-id="e4432-188">Separate multiple package names with commas.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="e4432-189">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="e4432-189">-PackageManagementProvider</span></span>

<span data-ttu-id="e4432-190">Указывает имя поставщика управления пакетами.</span><span class="sxs-lookup"><span data-stu-id="e4432-190">Specifies the name of a package management provider.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4432-191">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="e4432-191">-ProviderName</span></span>

<span data-ttu-id="e4432-192">Указывает одно или несколько имен поставщиков пакетов.</span><span class="sxs-lookup"><span data-stu-id="e4432-192">Specifies one or more package provider names.</span></span> <span data-ttu-id="e4432-193">Несколько имен поставщиков пакетов следует разделять запятыми.</span><span class="sxs-lookup"><span data-stu-id="e4432-193">Separate multiple package provider names with commas.</span></span>
<span data-ttu-id="e4432-194">Используйте `Get-PackageProvider` для получения списка доступных поставщиков пакетов.</span><span class="sxs-lookup"><span data-stu-id="e4432-194">Use `Get-PackageProvider` to get a list of available package providers.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Provider
Accepted values: Bootstrap, NuGet, PowerShellGet

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="e4432-195">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="e4432-195">-Proxy</span></span>

<span data-ttu-id="e4432-196">Указывает прокси-сервер для запроса, а не прямое подключение к Интернету.</span><span class="sxs-lookup"><span data-stu-id="e4432-196">Specifies a proxy server for the request, rather than a direct connection to the internet resource.</span></span>

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

### <span data-ttu-id="e4432-197">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="e4432-197">-ProxyCredential</span></span>

<span data-ttu-id="e4432-198">Указывает учетную запись пользователя, имеющую разрешение на использование прокси-сервера, который задается параметром **Proxy**.</span><span class="sxs-lookup"><span data-stu-id="e4432-198">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4432-199">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="e4432-199">-PublishLocation</span></span>

<span data-ttu-id="e4432-200">Указывает расположение для публикации пакета.</span><span class="sxs-lookup"><span data-stu-id="e4432-200">Specifies a location for publishing the package.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4432-201">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="e4432-201">-RequiredVersion</span></span>

<span data-ttu-id="e4432-202">Указывает точную версию пакета, которую необходимо найти.</span><span class="sxs-lookup"><span data-stu-id="e4432-202">Specifies an exact package version that you want to find.</span></span>

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

### <span data-ttu-id="e4432-203">-RoleCapability</span><span class="sxs-lookup"><span data-stu-id="e4432-203">-RoleCapability</span></span>

<span data-ttu-id="e4432-204">Указывает массив возможностей роли.</span><span class="sxs-lookup"><span data-stu-id="e4432-204">Specifies an array of role capabilities.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4432-205">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="e4432-205">-ScriptPublishLocation</span></span>

<span data-ttu-id="e4432-206">Указывает расположение публикации скрипта для пакета.</span><span class="sxs-lookup"><span data-stu-id="e4432-206">Specifies a script publishing location for the package.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4432-207">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="e4432-207">-ScriptSourceLocation</span></span>

<span data-ttu-id="e4432-208">Указывает расположение источника скрипта.</span><span class="sxs-lookup"><span data-stu-id="e4432-208">Specifies a script source location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4432-209">-Скипвалидате</span><span class="sxs-lookup"><span data-stu-id="e4432-209">-SkipValidate</span></span>

<span data-ttu-id="e4432-210">Параметр, который пропускает проверку учетных данных пакета.</span><span class="sxs-lookup"><span data-stu-id="e4432-210">Switch that skips package credential validation.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4432-211">-Source</span><span class="sxs-lookup"><span data-stu-id="e4432-211">-Source</span></span>

<span data-ttu-id="e4432-212">Указывает один или несколько источников пакетов.</span><span class="sxs-lookup"><span data-stu-id="e4432-212">Specifies one or more package sources.</span></span> <span data-ttu-id="e4432-213">Используйте `Get-PackageSource` для получения списка доступных источников пакетов.</span><span class="sxs-lookup"><span data-stu-id="e4432-213">Use `Get-PackageSource` to get a list of available package sources.</span></span> <span data-ttu-id="e4432-214">Каталог файловой системы можно использовать в качестве источника для скачивания пакетов.</span><span class="sxs-lookup"><span data-stu-id="e4432-214">A file system directory can be used as a source for download packages.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="e4432-215">-Tag</span><span class="sxs-lookup"><span data-stu-id="e4432-215">-Tag</span></span>

<span data-ttu-id="e4432-216">Указывает одну или несколько строк для поиска в метаданных пакета.</span><span class="sxs-lookup"><span data-stu-id="e4432-216">Specifies one or more strings to search for in the package metadata.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4432-217">-Type</span><span class="sxs-lookup"><span data-stu-id="e4432-217">-Type</span></span>

<span data-ttu-id="e4432-218">Указывает, следует ли выполнять поиск пакетов с помощью модуля, скрипта или либо.</span><span class="sxs-lookup"><span data-stu-id="e4432-218">Specifies whether to search for packages with a module, a script, or either.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet
Aliases:
Accepted values: Module, Script, All

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4432-219">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="e4432-219">CommonParameters</span></span>

<span data-ttu-id="e4432-220">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e4432-220">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e4432-221">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e4432-221">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e4432-222">Входные данные</span><span class="sxs-lookup"><span data-stu-id="e4432-222">INPUTS</span></span>

### <span data-ttu-id="e4432-223">None</span><span class="sxs-lookup"><span data-stu-id="e4432-223">None</span></span>

<span data-ttu-id="e4432-224">`Find-Package` не принимает входные данные из конвейера.</span><span class="sxs-lookup"><span data-stu-id="e4432-224">`Find-Package` doesn't accept input from the pipeline.</span></span>

## <span data-ttu-id="e4432-225">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="e4432-225">OUTPUTS</span></span>

### <span data-ttu-id="e4432-226">Софтвареидентифи []</span><span class="sxs-lookup"><span data-stu-id="e4432-226">SoftwareIdentify[]</span></span>

<span data-ttu-id="e4432-227">`Find-Package` выводит объект **софтвареидентити** .</span><span class="sxs-lookup"><span data-stu-id="e4432-227">`Find-Package` outputs a **SoftwareIdentity** object.</span></span>

## <span data-ttu-id="e4432-228">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="e4432-228">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e4432-229">Начиная с апреля 2020 года коллекция PowerShell не поддерживает протокол TLS (Transport Layer Security) версий 1.0 и 1.1.</span><span class="sxs-lookup"><span data-stu-id="e4432-229">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="e4432-230">Если вы не используете TLS 1.2 или более поздней версии, при попытке доступа к коллекции PowerShell возникнет ошибка.</span><span class="sxs-lookup"><span data-stu-id="e4432-230">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="e4432-231">Чтобы проверить, используется ли TLS 1.2, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e4432-231">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="e4432-232">Дополнительные сведения см. в [объявлении](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) в блоге, посвященном PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e4432-232">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="e4432-233">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="e4432-233">RELATED LINKS</span></span>

[<span data-ttu-id="e4432-234">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="e4432-234">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="e4432-235">Get-Package</span><span class="sxs-lookup"><span data-stu-id="e4432-235">Get-Package</span></span>](Get-Package.md)

[<span data-ttu-id="e4432-236">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="e4432-236">Get-PackageProvider</span></span>](Get-PackageProvider.md)

[<span data-ttu-id="e4432-237">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="e4432-237">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="e4432-238">Install-Package</span><span class="sxs-lookup"><span data-stu-id="e4432-238">Install-Package</span></span>](Install-Package.md)

[<span data-ttu-id="e4432-239">Save-Package</span><span class="sxs-lookup"><span data-stu-id="e4432-239">Save-Package</span></span>](Save-Package.md)

[<span data-ttu-id="e4432-240">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="e4432-240">Uninstall-Package</span></span>](Uninstall-Package.md)
