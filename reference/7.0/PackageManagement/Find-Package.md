---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PackageManagement
ms.date: 04/03/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/find-package?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-Package
ms.openlocfilehash: 9bbcda92b98410835a2380296a06fd053c01b52c
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93226122"
---
# <span data-ttu-id="254a1-103">Find-Package</span><span class="sxs-lookup"><span data-stu-id="254a1-103">Find-Package</span></span>

## <span data-ttu-id="254a1-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="254a1-104">SYNOPSIS</span></span>
<span data-ttu-id="254a1-105">Находит пакеты программного обеспечения в доступных источниках пакетов.</span><span class="sxs-lookup"><span data-stu-id="254a1-105">Finds software packages in available package sources.</span></span>

## <span data-ttu-id="254a1-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="254a1-106">SYNTAX</span></span>

### <span data-ttu-id="254a1-107">NuGet</span><span class="sxs-lookup"><span data-stu-id="254a1-107">NuGet</span></span>

```
Find-Package [-IncludeDependencies] [-AllVersions] [-Source <String[]>] [-Credential <PSCredential>]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [[-Name] <String[]>] [-RequiredVersion <String>]
 [-MinimumVersion <String>] [-MaximumVersion <String>] [-Force] [-ForceBootstrap]
 [-ProviderName <String[]>] [-ConfigFile <String>] [-SkipValidate] [-Headers <String[]>]
 [-FilterOnTag <String[]>] [-Contains <String>] [-AllowPrereleaseVersions] [<CommonParameters>]
```

### <span data-ttu-id="254a1-108">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="254a1-108">PowerShellGet</span></span>

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

## <span data-ttu-id="254a1-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="254a1-109">DESCRIPTION</span></span>

<span data-ttu-id="254a1-110">`Find-Package` находит пакеты программного обеспечения, доступные в источниках пакетов.</span><span class="sxs-lookup"><span data-stu-id="254a1-110">`Find-Package` finds software packages that are available in package sources.</span></span> <span data-ttu-id="254a1-111">`Get-PackageProvider` и `Get-PackageSource` отобразит сведения о поставщиках.</span><span class="sxs-lookup"><span data-stu-id="254a1-111">`Get-PackageProvider` and `Get-PackageSource` display details about your providers.</span></span>

## <span data-ttu-id="254a1-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="254a1-112">EXAMPLES</span></span>

### <span data-ttu-id="254a1-113">Пример 1. Поиск всех доступных пакетов от поставщика пакетов</span><span class="sxs-lookup"><span data-stu-id="254a1-113">Example 1: Find all available packages from a package provider</span></span>

<span data-ttu-id="254a1-114">Эта команда находит все доступные пакеты модулей PowerShell в зарегистрированной коллекции.</span><span class="sxs-lookup"><span data-stu-id="254a1-114">This command finds all available PowerShell module packages in a registered gallery.</span></span> <span data-ttu-id="254a1-115">Используйте `Get-PackageProvider` для получения имени поставщика.</span><span class="sxs-lookup"><span data-stu-id="254a1-115">Use `Get-PackageProvider` to get the provider name.</span></span>

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

<span data-ttu-id="254a1-116">`Find-Package` использует параметр **provider** для указания **NuGet** поставщика.</span><span class="sxs-lookup"><span data-stu-id="254a1-116">`Find-Package` uses the **Provider** parameter to specify the provider **NuGet**.</span></span>

### <span data-ttu-id="254a1-117">Пример 2. Поиск пакета из источника пакета</span><span class="sxs-lookup"><span data-stu-id="254a1-117">Example 2: Find a package from a package source</span></span>

<span data-ttu-id="254a1-118">Эта команда находит последнюю версию пакета из указанного источника пакета.</span><span class="sxs-lookup"><span data-stu-id="254a1-118">This command finds the newest version of a package from a specified package source.</span></span> <span data-ttu-id="254a1-119">Если источник пакета не указан, `Find-Package` ищет каждый установленный поставщик пакетов и его источники пакетов.</span><span class="sxs-lookup"><span data-stu-id="254a1-119">If a package source isn't provided, `Find-Package` searches each installed package provider and its package sources.</span></span> <span data-ttu-id="254a1-120">Используйте `Get-PackageSource` для получения имени источника.</span><span class="sxs-lookup"><span data-stu-id="254a1-120">Use `Get-PackageSource` to get the source name.</span></span>

```
Find-Package -Name NuGet.Core -Source MyNuGet
```

```Output
Name         Version   Source    Summary
----         -------   ------    -------
NuGet.Core   2.14.0    MyNuGet   NuGet.Core is the core framework assembly for NuGet...
```

<span data-ttu-id="254a1-121">`Find-Package` использует параметр **Name** для указания имени пакета **NuGet. Core**.</span><span class="sxs-lookup"><span data-stu-id="254a1-121">`Find-Package` uses the **Name** parameter to specify the package name **NuGet.Core**.</span></span> <span data-ttu-id="254a1-122">Параметр **Source** определяет поиск пакета в **минужет**.</span><span class="sxs-lookup"><span data-stu-id="254a1-122">The **Source** parameter specifies to search for the package in **MyNuGet**.</span></span>

### <span data-ttu-id="254a1-123">Пример 3. Поиск всех версий пакета</span><span class="sxs-lookup"><span data-stu-id="254a1-123">Example 3: Find all versions of a package</span></span>

<span data-ttu-id="254a1-124">Эта команда находит все доступные версии пакетов от указанного поставщика.</span><span class="sxs-lookup"><span data-stu-id="254a1-124">This command finds all available package versions from a specified provider.</span></span>

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

<span data-ttu-id="254a1-125">`Find-Package` использует параметр **Name** для указания пакета **NuGet. Core**.</span><span class="sxs-lookup"><span data-stu-id="254a1-125">`Find-Package` uses the **Name** parameter to specify the package **NuGet.Core**.</span></span> <span data-ttu-id="254a1-126">Параметр **providerName** определяет поиск пакета в **минужет**.</span><span class="sxs-lookup"><span data-stu-id="254a1-126">The **ProviderName** parameter specifies to search for the package in **MyNuGet**.</span></span> <span data-ttu-id="254a1-127">**AllVersions** указывает, что возвращаются все доступные версии.</span><span class="sxs-lookup"><span data-stu-id="254a1-127">**AllVersions** specifies that all available versions are returned.</span></span>

### <span data-ttu-id="254a1-128">Пример 4. Поиск пакета с указанным именем и версией</span><span class="sxs-lookup"><span data-stu-id="254a1-128">Example 4: Find a package with a specific name and version</span></span>

<span data-ttu-id="254a1-129">Эта команда находит определенную версию пакета по указанному поставщику.</span><span class="sxs-lookup"><span data-stu-id="254a1-129">This command finds a specific package version from a specified provider.</span></span>

```
Find-Package -Name NuGet.Core -ProviderName NuGet -RequiredVersion 2.9.0
```

```Output
Name          Version          Source       Summary
----          -------          ------       -------
NuGet.Core    2.9.0            MyNuGet      NuGet.Core is the core framework assembly for NuGet...
```

<span data-ttu-id="254a1-130">`Find-Package` использует параметр **Name** для указания имени пакета **NuGet. Core**.</span><span class="sxs-lookup"><span data-stu-id="254a1-130">`Find-Package` uses the **Name** parameter to specify the package name **NuGet.Core**.</span></span> <span data-ttu-id="254a1-131">Параметр **providerName** определяет поиск пакета в **NuGet**.</span><span class="sxs-lookup"><span data-stu-id="254a1-131">The **ProviderName** parameter specifies to search for the package in **NuGet**.</span></span> <span data-ttu-id="254a1-132">**RequiredVersion** указывает, что возвращается только версия **2.9.0** .</span><span class="sxs-lookup"><span data-stu-id="254a1-132">**RequiredVersion** specifies that only version **2.9.0** is returned.</span></span>

### <span data-ttu-id="254a1-133">Пример 5. Поиск пакетов в диапазоне версий</span><span class="sxs-lookup"><span data-stu-id="254a1-133">Example 5: Find packages within a range of versions</span></span>

<span data-ttu-id="254a1-134">Эта команда находит диапазон версий для указанного пакета.</span><span class="sxs-lookup"><span data-stu-id="254a1-134">This command finds a range of versions for a specified package.</span></span>

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

<span data-ttu-id="254a1-135">`Find-Package` использует параметр **Name** для указания имени пакета **NuGet. Core**.</span><span class="sxs-lookup"><span data-stu-id="254a1-135">`Find-Package` uses the **Name** parameter to specify the package name **NuGet.Core**.</span></span> <span data-ttu-id="254a1-136">Параметр **providerName** определяет поиск пакета в **NuGet**.</span><span class="sxs-lookup"><span data-stu-id="254a1-136">The **ProviderName** parameter specifies to search for the package in **NuGet**.</span></span> <span data-ttu-id="254a1-137">**MinimumVersion** указывает самую раннюю версию **2.7.0**.</span><span class="sxs-lookup"><span data-stu-id="254a1-137">**MinimumVersion** specifies the lowest version **2.7.0**.</span></span> <span data-ttu-id="254a1-138">**MaximumVersion** указывает самую старшую версию **2.9.0**.</span><span class="sxs-lookup"><span data-stu-id="254a1-138">**MaximumVersion** specifies the highest version **2.9.0**.</span></span>
<span data-ttu-id="254a1-139">**AllVersions** определяет, что диапазон возвращается в соответствии с минимальным и максимальным значением.</span><span class="sxs-lookup"><span data-stu-id="254a1-139">**AllVersions** determines the range is returned as specified by the minimum and maximum.</span></span>

### <span data-ttu-id="254a1-140">Пример 6. Поиск пакета из файловой системы</span><span class="sxs-lookup"><span data-stu-id="254a1-140">Example 6: Find a package from a file system</span></span>

<span data-ttu-id="254a1-141">Эта команда находит пакеты с расширением файла `.nupkg` , которые хранятся на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="254a1-141">This command finds packages with the file extension `.nupkg` that are stored on the local computer.</span></span>
<span data-ttu-id="254a1-142">Файлы — это пакеты, загружаемые из коллекции, например **NuGet**.</span><span class="sxs-lookup"><span data-stu-id="254a1-142">The files are packages downloaded from a gallery such as the **NuGet**.</span></span>

```
PS> Find-Package -Source C:\LocalPkg
```

```Output
Name                 Version    Source           Summary
----                 -------    ------           -------
Microsoft.Web.Xdt    3.0.0      C:\LocalPkg\     Microsoft Xml Document Transformation (XDT)...
NuGet.Core           2.14.0     C:\LocalPkg\     NuGet.Core is the core framework assembly...
```

## <span data-ttu-id="254a1-143">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="254a1-143">PARAMETERS</span></span>

### <span data-ttu-id="254a1-144">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="254a1-144">-AcceptLicense</span></span>

<span data-ttu-id="254a1-145">Автоматически принимает лицензионное соглашение, если оно требуется для пакета.</span><span class="sxs-lookup"><span data-stu-id="254a1-145">Automatically accepts a license agreement if the package requires it.</span></span>

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

### <span data-ttu-id="254a1-146">-Алловпререлеасеверсионс</span><span class="sxs-lookup"><span data-stu-id="254a1-146">-AllowPrereleaseVersions</span></span>

<span data-ttu-id="254a1-147">Включает пакеты, помеченные как предварительные выпуски в результатах.</span><span class="sxs-lookup"><span data-stu-id="254a1-147">Includes packages marked as a prerelease in the results.</span></span>

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

### <span data-ttu-id="254a1-148">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="254a1-148">-AllVersions</span></span>

<span data-ttu-id="254a1-149">Указывает, что `Find-Package` возвращает все доступные версии пакета.</span><span class="sxs-lookup"><span data-stu-id="254a1-149">Indicates that `Find-Package` returns all available versions of the package.</span></span> <span data-ttu-id="254a1-150">По умолчанию `Find-Package` возвращает только последнюю доступную версию.</span><span class="sxs-lookup"><span data-stu-id="254a1-150">By default, `Find-Package` only returns the newest available version.</span></span>

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

### <span data-ttu-id="254a1-151">-Command</span><span class="sxs-lookup"><span data-stu-id="254a1-151">-Command</span></span>

<span data-ttu-id="254a1-152">Указывает массив команд, в которых выполняется поиск `Find-Package` .</span><span class="sxs-lookup"><span data-stu-id="254a1-152">Specifies an array of commands searched by `Find-Package`.</span></span>

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

### <span data-ttu-id="254a1-153">-ConfigFile</span><span class="sxs-lookup"><span data-stu-id="254a1-153">-ConfigFile</span></span>

<span data-ttu-id="254a1-154">Указывает файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="254a1-154">Specifies a configuration file.</span></span>

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

### <span data-ttu-id="254a1-155">— Содержит</span><span class="sxs-lookup"><span data-stu-id="254a1-155">-Contains</span></span>

<span data-ttu-id="254a1-156">`Find-Package` Возвращает объекты, если любой элемент в значениях свойств объекта является точным соответствием для указанного значения.</span><span class="sxs-lookup"><span data-stu-id="254a1-156">`Find-Package` gets objects if any item in the object's property values are an exact match for the specified value.</span></span>

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

### <span data-ttu-id="254a1-157">-Credential</span><span class="sxs-lookup"><span data-stu-id="254a1-157">-Credential</span></span>

<span data-ttu-id="254a1-158">Указывает учетную запись пользователя, имеющую разрешение на поиск пакетов.</span><span class="sxs-lookup"><span data-stu-id="254a1-158">Specifies a user account that has permission to search for packages.</span></span>

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

### <span data-ttu-id="254a1-159">-DscResource</span><span class="sxs-lookup"><span data-stu-id="254a1-159">-DscResource</span></span>

<span data-ttu-id="254a1-160">Указывает массив ресурсов DSC, которые ищет этот командлет.</span><span class="sxs-lookup"><span data-stu-id="254a1-160">Specifies an array of Desired State Configuration (DSC) resources that this cmdlet searches.</span></span>

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

### <span data-ttu-id="254a1-161">-Filter</span><span class="sxs-lookup"><span data-stu-id="254a1-161">-Filter</span></span>

<span data-ttu-id="254a1-162">Задает термины для поиска в свойствах **имя** и **Описание** .</span><span class="sxs-lookup"><span data-stu-id="254a1-162">Specifies terms to search for within the **Name** and **Description** properties.</span></span>

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

### <span data-ttu-id="254a1-163">-Филтеронтаг</span><span class="sxs-lookup"><span data-stu-id="254a1-163">-FilterOnTag</span></span>

<span data-ttu-id="254a1-164">Указывает тег, фильтрующий результаты.</span><span class="sxs-lookup"><span data-stu-id="254a1-164">Specifies the tag that filters the results.</span></span> <span data-ttu-id="254a1-165">Исключаются результаты, не содержащие указанный тег.</span><span class="sxs-lookup"><span data-stu-id="254a1-165">Results that don't contain the specified tag are excluded.</span></span>

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

### <span data-ttu-id="254a1-166">-Force</span><span class="sxs-lookup"><span data-stu-id="254a1-166">-Force</span></span>

<span data-ttu-id="254a1-167">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="254a1-167">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="254a1-168">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="254a1-168">-ForceBootstrap</span></span>

<span data-ttu-id="254a1-169">Указывает, что `Find-Package` заставляет **PackageManagement** автоматически устанавливать поставщик пакетов.</span><span class="sxs-lookup"><span data-stu-id="254a1-169">Indicates that `Find-Package` forces **PackageManagement** to automatically install the package provider.</span></span>

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

### <span data-ttu-id="254a1-170">-Заголовки</span><span class="sxs-lookup"><span data-stu-id="254a1-170">-Headers</span></span>

<span data-ttu-id="254a1-171">Указывает заголовки для пакета.</span><span class="sxs-lookup"><span data-stu-id="254a1-171">Specifies the headers for the package.</span></span>

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

### <span data-ttu-id="254a1-172">-IncludeDependencies</span><span class="sxs-lookup"><span data-stu-id="254a1-172">-IncludeDependencies</span></span>

<span data-ttu-id="254a1-173">Указывает, что этот командлет включает в результаты зависимости пакетов.</span><span class="sxs-lookup"><span data-stu-id="254a1-173">Indicates that this cmdlet includes package dependencies in the results.</span></span>

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

### <span data-ttu-id="254a1-174">— Включает</span><span class="sxs-lookup"><span data-stu-id="254a1-174">-Includes</span></span>

<span data-ttu-id="254a1-175">Указывает `Find-Package` , следует ли найти все пакеты в категории.</span><span class="sxs-lookup"><span data-stu-id="254a1-175">Specifies whether `Find-Package` should find all packages within a category.</span></span>

<span data-ttu-id="254a1-176">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="254a1-176">The accepted values are as follows:</span></span>

- <span data-ttu-id="254a1-177">Командлет</span><span class="sxs-lookup"><span data-stu-id="254a1-177">Cmdlet</span></span>
- <span data-ttu-id="254a1-178">DscResource</span><span class="sxs-lookup"><span data-stu-id="254a1-178">DscResource</span></span>
- <span data-ttu-id="254a1-179">Компонент</span><span class="sxs-lookup"><span data-stu-id="254a1-179">Function</span></span>
- <span data-ttu-id="254a1-180">RoleCapability</span><span class="sxs-lookup"><span data-stu-id="254a1-180">RoleCapability</span></span>
- <span data-ttu-id="254a1-181">Рабочий процесс</span><span class="sxs-lookup"><span data-stu-id="254a1-181">Workflow</span></span>

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

### <span data-ttu-id="254a1-182">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="254a1-182">-MaximumVersion</span></span>

<span data-ttu-id="254a1-183">Указывает максимальную версию пакета, которую нужно найти.</span><span class="sxs-lookup"><span data-stu-id="254a1-183">Specifies the maximum package version that you want to find.</span></span>

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

### <span data-ttu-id="254a1-184">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="254a1-184">-MinimumVersion</span></span>

<span data-ttu-id="254a1-185">Указывает минимальную версию пакета, которую нужно найти.</span><span class="sxs-lookup"><span data-stu-id="254a1-185">Specifies the minimum package version that you want to find.</span></span> <span data-ttu-id="254a1-186">Если доступна более высокая версия, возвращается эта версия.</span><span class="sxs-lookup"><span data-stu-id="254a1-186">If a higher version is available, that version is returned.</span></span>

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

### <span data-ttu-id="254a1-187">-Name</span><span class="sxs-lookup"><span data-stu-id="254a1-187">-Name</span></span>

<span data-ttu-id="254a1-188">Указывает одно или несколько имен пакетов или имена пакетов с подстановочными знаками.</span><span class="sxs-lookup"><span data-stu-id="254a1-188">Specifies one or more package names, or package names with wildcard characters.</span></span> <span data-ttu-id="254a1-189">Несколько имен пакетов следует разделять запятыми.</span><span class="sxs-lookup"><span data-stu-id="254a1-189">Separate multiple package names with commas.</span></span>

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

### <span data-ttu-id="254a1-190">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="254a1-190">-PackageManagementProvider</span></span>

<span data-ttu-id="254a1-191">Указывает имя поставщика управления пакетами.</span><span class="sxs-lookup"><span data-stu-id="254a1-191">Specifies the name of a package management provider.</span></span>

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

### <span data-ttu-id="254a1-192">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="254a1-192">-ProviderName</span></span>

<span data-ttu-id="254a1-193">Указывает одно или несколько имен поставщиков пакетов.</span><span class="sxs-lookup"><span data-stu-id="254a1-193">Specifies one or more package provider names.</span></span> <span data-ttu-id="254a1-194">Несколько имен поставщиков пакетов следует разделять запятыми.</span><span class="sxs-lookup"><span data-stu-id="254a1-194">Separate multiple package provider names with commas.</span></span>
<span data-ttu-id="254a1-195">Используйте `Get-PackageProvider` для получения списка доступных поставщиков пакетов.</span><span class="sxs-lookup"><span data-stu-id="254a1-195">Use `Get-PackageProvider` to get a list of available package providers.</span></span>

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

### <span data-ttu-id="254a1-196">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="254a1-196">-Proxy</span></span>

<span data-ttu-id="254a1-197">Указывает прокси-сервер для запроса, а не прямое подключение к Интернету.</span><span class="sxs-lookup"><span data-stu-id="254a1-197">Specifies a proxy server for the request, rather than a direct connection to the internet resource.</span></span>

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

### <span data-ttu-id="254a1-198">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="254a1-198">-ProxyCredential</span></span>

<span data-ttu-id="254a1-199">Указывает учетную запись пользователя, имеющую разрешение на использование прокси-сервера, который задается параметром **Proxy**.</span><span class="sxs-lookup"><span data-stu-id="254a1-199">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="254a1-200">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="254a1-200">-PublishLocation</span></span>

<span data-ttu-id="254a1-201">Указывает расположение для публикации пакета.</span><span class="sxs-lookup"><span data-stu-id="254a1-201">Specifies a location for publishing the package.</span></span>

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

### <span data-ttu-id="254a1-202">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="254a1-202">-RequiredVersion</span></span>

<span data-ttu-id="254a1-203">Указывает точную версию пакета, которую необходимо найти.</span><span class="sxs-lookup"><span data-stu-id="254a1-203">Specifies an exact package version that you want to find.</span></span>

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

### <span data-ttu-id="254a1-204">-RoleCapability</span><span class="sxs-lookup"><span data-stu-id="254a1-204">-RoleCapability</span></span>

<span data-ttu-id="254a1-205">Указывает массив возможностей роли.</span><span class="sxs-lookup"><span data-stu-id="254a1-205">Specifies an array of role capabilities.</span></span>

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

### <span data-ttu-id="254a1-206">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="254a1-206">-ScriptPublishLocation</span></span>

<span data-ttu-id="254a1-207">Указывает расположение публикации скрипта для пакета.</span><span class="sxs-lookup"><span data-stu-id="254a1-207">Specifies a script publishing location for the package.</span></span>

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

### <span data-ttu-id="254a1-208">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="254a1-208">-ScriptSourceLocation</span></span>

<span data-ttu-id="254a1-209">Указывает расположение источника скрипта.</span><span class="sxs-lookup"><span data-stu-id="254a1-209">Specifies a script source location.</span></span>

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

### <span data-ttu-id="254a1-210">-Скипвалидате</span><span class="sxs-lookup"><span data-stu-id="254a1-210">-SkipValidate</span></span>

<span data-ttu-id="254a1-211">Параметр, который пропускает проверку учетных данных пакета.</span><span class="sxs-lookup"><span data-stu-id="254a1-211">Switch that skips package credential validation.</span></span>

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

### <span data-ttu-id="254a1-212">-Source</span><span class="sxs-lookup"><span data-stu-id="254a1-212">-Source</span></span>

<span data-ttu-id="254a1-213">Указывает один или несколько источников пакетов.</span><span class="sxs-lookup"><span data-stu-id="254a1-213">Specifies one or more package sources.</span></span> <span data-ttu-id="254a1-214">Используйте `Get-PackageSource` для получения списка доступных источников пакетов.</span><span class="sxs-lookup"><span data-stu-id="254a1-214">Use `Get-PackageSource` to get a list of available package sources.</span></span> <span data-ttu-id="254a1-215">Каталог файловой системы можно использовать в качестве источника для скачивания пакетов.</span><span class="sxs-lookup"><span data-stu-id="254a1-215">A file system directory can be used as a source for download packages.</span></span>

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

### <span data-ttu-id="254a1-216">-Tag</span><span class="sxs-lookup"><span data-stu-id="254a1-216">-Tag</span></span>

<span data-ttu-id="254a1-217">Указывает одну или несколько строк для поиска в метаданных пакета.</span><span class="sxs-lookup"><span data-stu-id="254a1-217">Specifies one or more strings to search for in the package metadata.</span></span>

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

### <span data-ttu-id="254a1-218">-Type</span><span class="sxs-lookup"><span data-stu-id="254a1-218">-Type</span></span>

<span data-ttu-id="254a1-219">Указывает, следует ли выполнять поиск пакетов с помощью модуля, скрипта или либо.</span><span class="sxs-lookup"><span data-stu-id="254a1-219">Specifies whether to search for packages with a module, a script, or either.</span></span>

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

### <span data-ttu-id="254a1-220">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="254a1-220">CommonParameters</span></span>

<span data-ttu-id="254a1-221">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="254a1-221">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="254a1-222">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="254a1-222">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="254a1-223">Входные данные</span><span class="sxs-lookup"><span data-stu-id="254a1-223">INPUTS</span></span>

### <span data-ttu-id="254a1-224">Нет</span><span class="sxs-lookup"><span data-stu-id="254a1-224">None</span></span>

<span data-ttu-id="254a1-225">`Find-Package` не принимает входные данные из конвейера.</span><span class="sxs-lookup"><span data-stu-id="254a1-225">`Find-Package` doesn't accept input from the pipeline.</span></span>

## <span data-ttu-id="254a1-226">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="254a1-226">OUTPUTS</span></span>

### <span data-ttu-id="254a1-227">Софтвареидентифи []</span><span class="sxs-lookup"><span data-stu-id="254a1-227">SoftwareIdentify[]</span></span>

<span data-ttu-id="254a1-228">`Find-Package` выводит объект **софтвареидентити** .</span><span class="sxs-lookup"><span data-stu-id="254a1-228">`Find-Package` outputs a **SoftwareIdentity** object.</span></span>

## <span data-ttu-id="254a1-229">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="254a1-229">NOTES</span></span>

## <span data-ttu-id="254a1-230">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="254a1-230">RELATED LINKS</span></span>

[<span data-ttu-id="254a1-231">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="254a1-231">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="254a1-232">Get-Package</span><span class="sxs-lookup"><span data-stu-id="254a1-232">Get-Package</span></span>](Get-Package.md)

[<span data-ttu-id="254a1-233">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="254a1-233">Get-PackageProvider</span></span>](Get-PackageProvider.md)

[<span data-ttu-id="254a1-234">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="254a1-234">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="254a1-235">Install-Package</span><span class="sxs-lookup"><span data-stu-id="254a1-235">Install-Package</span></span>](Install-Package.md)

[<span data-ttu-id="254a1-236">Save-Package</span><span class="sxs-lookup"><span data-stu-id="254a1-236">Save-Package</span></span>](Save-Package.md)

[<span data-ttu-id="254a1-237">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="254a1-237">Uninstall-Package</span></span>](Uninstall-Package.md)