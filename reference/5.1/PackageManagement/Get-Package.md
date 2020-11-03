---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PackageManagement
ms.date: 05/22/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/get-package?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Package
ms.openlocfilehash: aad8b6f033674c65b4cc56708e09e5320bb046dd
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227337"
---
# <span data-ttu-id="c9cb0-103">Get-Package</span><span class="sxs-lookup"><span data-stu-id="c9cb0-103">Get-Package</span></span>

## <span data-ttu-id="c9cb0-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="c9cb0-104">SYNOPSIS</span></span>
<span data-ttu-id="c9cb0-105">Возвращает список всех пакетов программного обеспечения, установленных с помощью **PackageManagement** .</span><span class="sxs-lookup"><span data-stu-id="c9cb0-105">Returns a list of all software packages that were installed with **PackageManagement** .</span></span>

## <span data-ttu-id="c9cb0-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c9cb0-106">SYNTAX</span></span>

### <span data-ttu-id="c9cb0-107">MSI</span><span class="sxs-lookup"><span data-stu-id="c9cb0-107">msi</span></span>

```
Get-Package [[-Name] <String[]>] [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-Force] [-ForceBootstrap] [-ProviderName <String[]>]
 [-AdditionalArguments <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="c9cb0-108">Программы</span><span class="sxs-lookup"><span data-stu-id="c9cb0-108">Programs</span></span>

```
Get-Package [[-Name] <String[]>] [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-Force] [-ForceBootstrap] [-ProviderName <String[]>]
 [-IncludeWindowsInstaller] [-IncludeSystemComponent] [<CommonParameters>]
```

### <span data-ttu-id="c9cb0-109">NuGet</span><span class="sxs-lookup"><span data-stu-id="c9cb0-109">NuGet</span></span>

```
Get-Package [[-Name] <String[]>] [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-Force] [-ForceBootstrap] [-ProviderName <String[]>]
 [-Destination <String>] [-ExcludeVersion] [-Scope <String>] [-SkipDependencies]
 [<CommonParameters>]
```

### <span data-ttu-id="c9cb0-110">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="c9cb0-110">PowerShellGet</span></span>

```
Get-Package [[-Name] <String[]>] [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-Force] [-ForceBootstrap] [-ProviderName <String[]>]
 [-Scope <String>] [-PackageManagementProvider <String>] [-Type <String>] [-AllowClobber]
 [-SkipPublisherCheck] [-InstallUpdate] [-NoPathUpdate] [-AllowPrereleaseVersions]
 [<CommonParameters>]
```

## <span data-ttu-id="c9cb0-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c9cb0-111">DESCRIPTION</span></span>

<span data-ttu-id="c9cb0-112">`Get-Package`Командлет возвращает список всех пакетов программного обеспечения на локальном компьютере, которые были установлены с помощью **PackageManagement** .</span><span class="sxs-lookup"><span data-stu-id="c9cb0-112">The `Get-Package` cmdlet returns a list of all software packages on the local computer that were installed with **PackageManagement** .</span></span> <span data-ttu-id="c9cb0-113">Можно запустить `Get-Package` на удаленных компьютерах, запустив его как часть `Invoke-Command` `Enter-PSSession` команды или скрипта.</span><span class="sxs-lookup"><span data-stu-id="c9cb0-113">You can run `Get-Package` on remote computers by running it as part of an `Invoke-Command` or `Enter-PSSession` command or script.</span></span>

## <span data-ttu-id="c9cb0-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="c9cb0-114">EXAMPLES</span></span>

### <span data-ttu-id="c9cb0-115">Пример 1. получение всех установленных пакетов</span><span class="sxs-lookup"><span data-stu-id="c9cb0-115">Example 1: Get all installed packages</span></span>

<span data-ttu-id="c9cb0-116">`Get-Package`Командлет возвращает все пакеты, установленные на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="c9cb0-116">The `Get-Package` cmdlet gets all packages that are installed on the local computer.</span></span>

```powershell
Get-Package
```

```Output
Name           Version      Source                                     ProviderName
----           -------      ------                                     ------------
posh-git       0.7.3        https://www.powershellgallery.com/api/v2   PowerShellGet
```

### <span data-ttu-id="c9cb0-117">Пример 2. получение пакетов, установленных на удаленном компьютере</span><span class="sxs-lookup"><span data-stu-id="c9cb0-117">Example 2: Get packages that are installed on a remote computer</span></span>

<span data-ttu-id="c9cb0-118">Эта команда возвращает список пакетов, которые были установлены средством **PackageManagement** на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="c9cb0-118">This command gets a list of packages that were installed by **PackageManagement** on a remote computer.</span></span> <span data-ttu-id="c9cb0-119">Эта команда предложит указать пароль указанного пользователя.</span><span class="sxs-lookup"><span data-stu-id="c9cb0-119">This command prompts you to provide the specified user's password.</span></span>

```
PS> Invoke-Command -ComputerName Server01 -Credential CONTOSO\TestUser -ScriptBlock {Get-Package}
```

<span data-ttu-id="c9cb0-120">`Invoke-Command` использует параметр **ComputerName** для указания удаленного компьютера **Server01** .</span><span class="sxs-lookup"><span data-stu-id="c9cb0-120">`Invoke-Command` uses the **ComputerName** parameter to specify a remote computer, **Server01** .</span></span> <span data-ttu-id="c9cb0-121">Параметр **Credential** указывает домен и имя пользователя с разрешениями на выполнение команд на компьютере.</span><span class="sxs-lookup"><span data-stu-id="c9cb0-121">The **Credential** parameter specifies a domain and user name with permissions to run commands on the computer.</span></span> <span data-ttu-id="c9cb0-122">Параметр **ScriptBlock** запускает `Get-Package` командлет на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="c9cb0-122">The **ScriptBlock** parameter runs the `Get-Package` cmdlet on the remote computer.</span></span>

### <span data-ttu-id="c9cb0-123">Пример 3. получение пакетов для указанного поставщика</span><span class="sxs-lookup"><span data-stu-id="c9cb0-123">Example 3: Get packages for a specified provider</span></span>

<span data-ttu-id="c9cb0-124">Эта команда получает пакеты программного обеспечения, установленные на локальном компьютере, от определенного поставщика.</span><span class="sxs-lookup"><span data-stu-id="c9cb0-124">This command gets software packages installed on the local computer from a specific provider.</span></span>

```powershell
Get-Package -ProviderName PowerShellGet -AllVersions
```

```Output
Name                  Version      Source                                     ProviderName
----                  -------      ------                                     ------------
PackageManagement     1.2.2        https://www.powershellgallery.com/api/v2   PowerShellGet
PackageManagement     1.3.1        https://www.powershellgallery.com/api/v2   PowerShellGet
posh-git              0.7.3        https://www.powershellgallery.com/api/v2   PowerShellGet
PowerShellGet         2.0.1        https://www.powershellgallery.com/api/v2   PowerShellGet
```

<span data-ttu-id="c9cb0-125">`Get-Package` использует параметр **providerName** для указания конкретного поставщика, **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="c9cb0-125">`Get-Package` uses the **ProviderName** parameter to specify a specific provider, **PowerShellGet** .</span></span>
<span data-ttu-id="c9cb0-126">Параметр **все-Versions** отображает каждую установленную версию.</span><span class="sxs-lookup"><span data-stu-id="c9cb0-126">The **All-Versions** parameter displays each version that is installed.</span></span>

### <span data-ttu-id="c9cb0-127">Пример 4. получение точной версии конкретного пакета</span><span class="sxs-lookup"><span data-stu-id="c9cb0-127">Example 4: Get an exact version of a specific package</span></span>

<span data-ttu-id="c9cb0-128">Эта команда возвращает определенную версию установленного пакета.</span><span class="sxs-lookup"><span data-stu-id="c9cb0-128">This command gets a specific version of an installed package.</span></span> <span data-ttu-id="c9cb0-129">Можно установить более одной версии пакета.</span><span class="sxs-lookup"><span data-stu-id="c9cb0-129">More than one version of a package can be installed.</span></span>

```powershell
Get-Package -Name PackageManagement -ProviderName PowerShellGet -RequiredVersion 1.3.1
```

```Output
Name                  Version      Source                                     ProviderName
----                  -------      ------                                     ------------
PackageManagement     1.3.1        https://www.powershellgallery.com/api/v2   PowerShellGet
```

<span data-ttu-id="c9cb0-130">`Get-Package` использует параметр **Name** для указания имени пакета, **PackageManagement** .</span><span class="sxs-lookup"><span data-stu-id="c9cb0-130">`Get-Package` uses **Name** parameter to specify the package name, **PackageManagement** .</span></span> <span data-ttu-id="c9cb0-131">Параметр **providerName** указывает поставщика, **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="c9cb0-131">The **ProviderName** parameter specifies the provider, **PowerShellGet** .</span></span> <span data-ttu-id="c9cb0-132">Параметр **требуемой версии** указывает установленную версию.</span><span class="sxs-lookup"><span data-stu-id="c9cb0-132">The **Required-Version** parameter specifies an installed version.</span></span>

### <span data-ttu-id="c9cb0-133">Пример 5. Удаление пакета</span><span class="sxs-lookup"><span data-stu-id="c9cb0-133">Example 5: Uninstall a package</span></span>

<span data-ttu-id="c9cb0-134">В этом примере получается информация о пакете, а затем удаляется пакет.</span><span class="sxs-lookup"><span data-stu-id="c9cb0-134">This example gets package information and then uninstalls the package.</span></span>

```powershell
Get-Package -Name posh-git -RequiredVersion 0.7.3 | Uninstall-Package
```

<span data-ttu-id="c9cb0-135">`Get-Package` использует параметр **Name** для указания имени пакета **Posh-Git** .</span><span class="sxs-lookup"><span data-stu-id="c9cb0-135">`Get-Package` uses the **Name** parameter to specify the package name, **posh-git** .</span></span> <span data-ttu-id="c9cb0-136">Параметр **RequiredVersion** — это конкретная версия пакета.</span><span class="sxs-lookup"><span data-stu-id="c9cb0-136">The **RequiredVersion** parameter is a specific version of the package.</span></span> <span data-ttu-id="c9cb0-137">Объект отправляется по конвейеру в `Uninstall-Package` командлет.</span><span class="sxs-lookup"><span data-stu-id="c9cb0-137">The object is sent down the pipeline to the `Uninstall-Package` cmdlet.</span></span> <span data-ttu-id="c9cb0-138">`Uninstall-Package` Удаляет пакет.</span><span class="sxs-lookup"><span data-stu-id="c9cb0-138">`Uninstall-Package` removes the package.</span></span>

## <span data-ttu-id="c9cb0-139">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c9cb0-139">PARAMETERS</span></span>

### <span data-ttu-id="c9cb0-140">-AllowClobber</span><span class="sxs-lookup"><span data-stu-id="c9cb0-140">-AllowClobber</span></span>

<span data-ttu-id="c9cb0-141">Переопределяет предупреждающие сообщения о конфликтах с существующими командами.</span><span class="sxs-lookup"><span data-stu-id="c9cb0-141">Overrides warning messages about conflicts with existing commands.</span></span> <span data-ttu-id="c9cb0-142">Перезаписывает существующие команды, имена которых совпадают с именами команд, устанавливаемых модулем.</span><span class="sxs-lookup"><span data-stu-id="c9cb0-142">Overwrites existing commands that have the same name as commands being installed by a module.</span></span>

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

### <span data-ttu-id="c9cb0-143">-Алловпререлеасеверсионс</span><span class="sxs-lookup"><span data-stu-id="c9cb0-143">-AllowPrereleaseVersions</span></span>

<span data-ttu-id="c9cb0-144">Включает пакеты, помеченные как предварительные выпуски в результатах.</span><span class="sxs-lookup"><span data-stu-id="c9cb0-144">Includes packages marked as a prerelease in the results.</span></span>

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

### <span data-ttu-id="c9cb0-145">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="c9cb0-145">-AllVersions</span></span>

<span data-ttu-id="c9cb0-146">Указывает, что `Get-Package` возвращает все доступные версии пакета.</span><span class="sxs-lookup"><span data-stu-id="c9cb0-146">Indicates that `Get-Package` returns all available versions of the package.</span></span> <span data-ttu-id="c9cb0-147">По умолчанию `Get-Package` возвращает только последнюю доступную версию.</span><span class="sxs-lookup"><span data-stu-id="c9cb0-147">By default, `Get-Package` only returns the newest available version.</span></span>

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

### <span data-ttu-id="c9cb0-148">-Destination</span><span class="sxs-lookup"><span data-stu-id="c9cb0-148">-Destination</span></span>

<span data-ttu-id="c9cb0-149">Указывает путь к каталогу, содержащему извлеченные файлы пакета.</span><span class="sxs-lookup"><span data-stu-id="c9cb0-149">Specifies the path to a directory that contains extracted package files.</span></span>

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

### <span data-ttu-id="c9cb0-150">-Ексклудеверсион</span><span class="sxs-lookup"><span data-stu-id="c9cb0-150">-ExcludeVersion</span></span>

<span data-ttu-id="c9cb0-151">Переключитесь, чтобы исключить номер версии из пути к папке.</span><span class="sxs-lookup"><span data-stu-id="c9cb0-151">Switch to exclude the version number in the folder path.</span></span>

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

### <span data-ttu-id="c9cb0-152">-Force</span><span class="sxs-lookup"><span data-stu-id="c9cb0-152">-Force</span></span>

<span data-ttu-id="c9cb0-153">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="c9cb0-153">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="c9cb0-154">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="c9cb0-154">-ForceBootstrap</span></span>

<span data-ttu-id="c9cb0-155">Указывает, что `Get-Package` заставляет **PackageManagement** автоматически устанавливать поставщик пакетов.</span><span class="sxs-lookup"><span data-stu-id="c9cb0-155">Indicates that `Get-Package` forces **PackageManagement** to automatically install the package provider.</span></span>

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

### <span data-ttu-id="c9cb0-156">-Инсталлупдате</span><span class="sxs-lookup"><span data-stu-id="c9cb0-156">-InstallUpdate</span></span>

<span data-ttu-id="c9cb0-157">Указывает, что этот командлет устанавливает обновления.</span><span class="sxs-lookup"><span data-stu-id="c9cb0-157">Indicates that this cmdlet installs updates.</span></span>

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

### <span data-ttu-id="c9cb0-158">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="c9cb0-158">-MaximumVersion</span></span>

<span data-ttu-id="c9cb0-159">Указывает максимальную версию пакета, которую нужно найти.</span><span class="sxs-lookup"><span data-stu-id="c9cb0-159">Specifies the maximum package version that you want to find.</span></span>

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

### <span data-ttu-id="c9cb0-160">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="c9cb0-160">-MinimumVersion</span></span>

<span data-ttu-id="c9cb0-161">Указывает минимальную версию пакета, которую нужно найти.</span><span class="sxs-lookup"><span data-stu-id="c9cb0-161">Specifies the minimum package version that you want to find.</span></span> <span data-ttu-id="c9cb0-162">Если доступна более высокая версия, возвращается эта версия.</span><span class="sxs-lookup"><span data-stu-id="c9cb0-162">If a higher version is available, that version is returned.</span></span>

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

### <span data-ttu-id="c9cb0-163">-Name</span><span class="sxs-lookup"><span data-stu-id="c9cb0-163">-Name</span></span>

<span data-ttu-id="c9cb0-164">Указывает одно или несколько имен пакетов или имена пакетов с подстановочными знаками.</span><span class="sxs-lookup"><span data-stu-id="c9cb0-164">Specifies one or more package names, or package names with wildcard characters.</span></span> <span data-ttu-id="c9cb0-165">Несколько имен пакетов следует разделять запятыми.</span><span class="sxs-lookup"><span data-stu-id="c9cb0-165">Separate multiple package names with commas.</span></span>

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

### <span data-ttu-id="c9cb0-166">-NoPathUpdate</span><span class="sxs-lookup"><span data-stu-id="c9cb0-166">-NoPathUpdate</span></span>

<span data-ttu-id="c9cb0-167">**NoPathUpdate** применяется только к `Install-Script` командлету.</span><span class="sxs-lookup"><span data-stu-id="c9cb0-167">**NoPathUpdate** only applies to the `Install-Script` cmdlet.</span></span> <span data-ttu-id="c9cb0-168">**NoPathUpdate** — это динамический параметр, добавленный поставщиком и не поддерживаемый `Get-Package` .</span><span class="sxs-lookup"><span data-stu-id="c9cb0-168">**NoPathUpdate** is a dynamic parameter added by the provider and isn't supported by `Get-Package`.</span></span>

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

### <span data-ttu-id="c9cb0-169">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="c9cb0-169">-PackageManagementProvider</span></span>

<span data-ttu-id="c9cb0-170">Указывает имя поставщика управления пакетами.</span><span class="sxs-lookup"><span data-stu-id="c9cb0-170">Specifies the name of a package management provider.</span></span>

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

### <span data-ttu-id="c9cb0-171">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="c9cb0-171">-ProviderName</span></span>

<span data-ttu-id="c9cb0-172">Указывает одно или несколько имен поставщиков пакетов.</span><span class="sxs-lookup"><span data-stu-id="c9cb0-172">Specifies one or more package provider names.</span></span> <span data-ttu-id="c9cb0-173">Несколько имен поставщиков пакетов следует разделять запятыми.</span><span class="sxs-lookup"><span data-stu-id="c9cb0-173">Separate multiple package provider names with commas.</span></span>
<span data-ttu-id="c9cb0-174">Используйте `Get-PackageProvider` для получения списка доступных поставщиков пакетов.</span><span class="sxs-lookup"><span data-stu-id="c9cb0-174">Use `Get-PackageProvider` to get a list of available package providers.</span></span>

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

### <span data-ttu-id="c9cb0-175">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="c9cb0-175">-RequiredVersion</span></span>

<span data-ttu-id="c9cb0-176">Указывает точную версию пакета для поиска.</span><span class="sxs-lookup"><span data-stu-id="c9cb0-176">Specifies the exact version of the package to find.</span></span>

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

### <span data-ttu-id="c9cb0-177">-Scope</span><span class="sxs-lookup"><span data-stu-id="c9cb0-177">-Scope</span></span>

<span data-ttu-id="c9cb0-178">Указывает область поиска для пакета.</span><span class="sxs-lookup"><span data-stu-id="c9cb0-178">Specifies the search scope for the package.</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet, PowerShellGet
Aliases:
Accepted values: CurrentUser, AllUsers

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c9cb0-179">-СкипдепенденЦиес</span><span class="sxs-lookup"><span data-stu-id="c9cb0-179">-SkipDependencies</span></span>

<span data-ttu-id="c9cb0-180">Параметр, задающий пропуск поиска зависимостей пакетов.</span><span class="sxs-lookup"><span data-stu-id="c9cb0-180">Switch that specifies to skip finding any package dependencies.</span></span>

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

### <span data-ttu-id="c9cb0-181">-Скиппублишерчекк</span><span class="sxs-lookup"><span data-stu-id="c9cb0-181">-SkipPublisherCheck</span></span>

<span data-ttu-id="c9cb0-182">Позволяет получить версию пакета, более новую по сравнению с установленной версией.</span><span class="sxs-lookup"><span data-stu-id="c9cb0-182">Allows you to get a package version that is newer than your installed version.</span></span> <span data-ttu-id="c9cb0-183">Например, установленный пакет с цифровой подписью доверенного издателя, но новая версия не подписана цифровой подписью.</span><span class="sxs-lookup"><span data-stu-id="c9cb0-183">For example, an installed package that is digitally signed by a trusted publisher but a new version isn't digitally signed.</span></span>

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

### <span data-ttu-id="c9cb0-184">-Type</span><span class="sxs-lookup"><span data-stu-id="c9cb0-184">-Type</span></span>

<span data-ttu-id="c9cb0-185">Указывает, следует ли выполнять поиск пакетов с помощью модуля, скрипта или либо.</span><span class="sxs-lookup"><span data-stu-id="c9cb0-185">Specifies whether to search for packages with a module, a script, or either.</span></span>

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

### <span data-ttu-id="c9cb0-186">-Аддитионаларгументс</span><span class="sxs-lookup"><span data-stu-id="c9cb0-186">-AdditionalArguments</span></span>

<span data-ttu-id="c9cb0-187">Задает дополнительные аргументы.</span><span class="sxs-lookup"><span data-stu-id="c9cb0-187">Specifies additional arguments.</span></span>

```yaml
Type: System.String[]
Parameter Sets: msi
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c9cb0-188">-Инклудесистемкомпонент</span><span class="sxs-lookup"><span data-stu-id="c9cb0-188">-IncludeSystemComponent</span></span>

<span data-ttu-id="c9cb0-189">Указывает, что этот командлет включает в результаты все системные компоненты.</span><span class="sxs-lookup"><span data-stu-id="c9cb0-189">Indicates that this cmdlet includes system components in the results.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Programs
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c9cb0-190">-Инклудевиндовсинсталлер</span><span class="sxs-lookup"><span data-stu-id="c9cb0-190">-IncludeWindowsInstaller</span></span>

<span data-ttu-id="c9cb0-191">Указывает, что этот командлет включает в результаты установщик Windows.</span><span class="sxs-lookup"><span data-stu-id="c9cb0-191">Indicates that this cmdlet includes the Windows Installer in the results.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Programs
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c9cb0-192">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="c9cb0-192">CommonParameters</span></span>

<span data-ttu-id="c9cb0-193">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c9cb0-193">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c9cb0-194">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c9cb0-194">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c9cb0-195">Входные данные</span><span class="sxs-lookup"><span data-stu-id="c9cb0-195">INPUTS</span></span>

## <span data-ttu-id="c9cb0-196">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="c9cb0-196">OUTPUTS</span></span>

### <span data-ttu-id="c9cb0-197">Софтвареидентити []</span><span class="sxs-lookup"><span data-stu-id="c9cb0-197">SoftwareIdentity[]</span></span>

## <span data-ttu-id="c9cb0-198">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="c9cb0-198">NOTES</span></span>

<span data-ttu-id="c9cb0-199">Включение поставщика пакетов в команду может сделать динамические параметры доступными для командлета.</span><span class="sxs-lookup"><span data-stu-id="c9cb0-199">Including a package provider in a command can make dynamic parameters available to a cmdlet.</span></span> <span data-ttu-id="c9cb0-200">Динамические параметры относятся к поставщику пакетов.</span><span class="sxs-lookup"><span data-stu-id="c9cb0-200">Dynamic parameters are specific to a package provider.</span></span> <span data-ttu-id="c9cb0-201">`Get-Help`Командлет перечисляет наборы параметров командлета и включает набор параметров поставщика.</span><span class="sxs-lookup"><span data-stu-id="c9cb0-201">The `Get-Help` cmdlet lists a cmdlet's parameter sets and includes the provider's parameter set.</span></span> <span data-ttu-id="c9cb0-202">Например, `Get-Package` имеет набор параметров **PowerShellGet** , включающий `-NoPathUpdate` , `AllowClobber` и `SkipPublisherCheck` .</span><span class="sxs-lookup"><span data-stu-id="c9cb0-202">For example, `Get-Package` has the **PowerShellGet** parameter set that includes `-NoPathUpdate`, `AllowClobber`, and `SkipPublisherCheck`.</span></span>

## <span data-ttu-id="c9cb0-203">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="c9cb0-203">RELATED LINKS</span></span>

[<span data-ttu-id="c9cb0-204">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="c9cb0-204">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="c9cb0-205">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="c9cb0-205">Enter-PSSession</span></span>](../Microsoft.PowerShell.Core/Enter-PSSession.md)

[<span data-ttu-id="c9cb0-206">Find-Package</span><span class="sxs-lookup"><span data-stu-id="c9cb0-206">Find-Package</span></span>](Find-Package.md)

[<span data-ttu-id="c9cb0-207">Get-Help</span><span class="sxs-lookup"><span data-stu-id="c9cb0-207">Get-Help</span></span>](../Microsoft.PowerShell.Core/Get-Help.md)

[<span data-ttu-id="c9cb0-208">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="c9cb0-208">Get-PackageProvider</span></span>](Get-PackageProvider.md)

[<span data-ttu-id="c9cb0-209">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="c9cb0-209">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="c9cb0-210">Install-Package</span><span class="sxs-lookup"><span data-stu-id="c9cb0-210">Install-Package</span></span>](Install-Package.md)

[<span data-ttu-id="c9cb0-211">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="c9cb0-211">Invoke-Command</span></span>](../Microsoft.PowerShell.Core/Invoke-Command.md)

[<span data-ttu-id="c9cb0-212">Save-Package</span><span class="sxs-lookup"><span data-stu-id="c9cb0-212">Save-Package</span></span>](Save-Package.md)

[<span data-ttu-id="c9cb0-213">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="c9cb0-213">Uninstall-Package</span></span>](Uninstall-Package.md)
