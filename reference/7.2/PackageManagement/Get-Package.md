---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
Locale: en-US
Module Name: PackageManagement
ms.date: 05/22/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/get-package?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Package
ms.openlocfilehash: c26365eb5b4833c4982fa54e742521cf72307e99
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "99599797"
---
# <span data-ttu-id="dcdfb-102">Get-Package</span><span class="sxs-lookup"><span data-stu-id="dcdfb-102">Get-Package</span></span>

## <span data-ttu-id="dcdfb-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="dcdfb-103">SYNOPSIS</span></span>
<span data-ttu-id="dcdfb-104">Возвращает список всех пакетов программного обеспечения, установленных с помощью **PackageManagement**.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-104">Returns a list of all software packages that were installed with **PackageManagement**.</span></span>

## <span data-ttu-id="dcdfb-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="dcdfb-105">SYNTAX</span></span>

### <span data-ttu-id="dcdfb-106">NuGet</span><span class="sxs-lookup"><span data-stu-id="dcdfb-106">NuGet</span></span>

```
Get-Package [[-Name] <String[]>] [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-Force] [-ForceBootstrap] [-ProviderName <String[]>]
 [-Destination <String>] [-ExcludeVersion] [-Scope <String>] [-SkipDependencies]
 [<CommonParameters>]
```

### <span data-ttu-id="dcdfb-107">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="dcdfb-107">PowerShellGet</span></span>

```
Get-Package [[-Name] <String[]>] [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-Force] [-ForceBootstrap] [-ProviderName <String[]>]
 [-Scope <String>] [-PackageManagementProvider <String>] [-Type <String>] [-AllowClobber]
 [-SkipPublisherCheck] [-InstallUpdate] [-NoPathUpdate] [-AllowPrereleaseVersions]
 [<CommonParameters>]
```

## <span data-ttu-id="dcdfb-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="dcdfb-108">DESCRIPTION</span></span>

<span data-ttu-id="dcdfb-109">`Get-Package`Командлет возвращает список всех пакетов программного обеспечения на локальном компьютере, которые были установлены с помощью **PackageManagement**.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-109">The `Get-Package` cmdlet returns a list of all software packages on the local computer that were installed with **PackageManagement**.</span></span> <span data-ttu-id="dcdfb-110">Можно запустить `Get-Package` на удаленных компьютерах, запустив его как часть `Invoke-Command` `Enter-PSSession` команды или скрипта.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-110">You can run `Get-Package` on remote computers by running it as part of an `Invoke-Command` or `Enter-PSSession` command or script.</span></span>

## <span data-ttu-id="dcdfb-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="dcdfb-111">EXAMPLES</span></span>

### <span data-ttu-id="dcdfb-112">Пример 1. получение всех установленных пакетов</span><span class="sxs-lookup"><span data-stu-id="dcdfb-112">Example 1: Get all installed packages</span></span>

<span data-ttu-id="dcdfb-113">`Get-Package`Командлет возвращает все пакеты, установленные на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-113">The `Get-Package` cmdlet gets all packages that are installed on the local computer.</span></span>

```powershell
Get-Package
```

```Output
Name           Version      Source                                     ProviderName
----           -------      ------                                     ------------
posh-git       0.7.3        https://www.powershellgallery.com/api/v2   PowerShellGet
```

### <span data-ttu-id="dcdfb-114">Пример 2. получение пакетов, установленных на удаленном компьютере</span><span class="sxs-lookup"><span data-stu-id="dcdfb-114">Example 2: Get packages that are installed on a remote computer</span></span>

<span data-ttu-id="dcdfb-115">Эта команда возвращает список пакетов, которые были установлены средством **PackageManagement** на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-115">This command gets a list of packages that were installed by **PackageManagement** on a remote computer.</span></span> <span data-ttu-id="dcdfb-116">Эта команда предложит указать пароль указанного пользователя.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-116">This command prompts you to provide the specified user's password.</span></span>

```
PS> Invoke-Command -ComputerName Server01 -Credential CONTOSO\TestUser -ScriptBlock {Get-Package}
```

<span data-ttu-id="dcdfb-117">`Invoke-Command` использует параметр **ComputerName** для указания удаленного компьютера **Server01**.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-117">`Invoke-Command` uses the **ComputerName** parameter to specify a remote computer, **Server01**.</span></span> <span data-ttu-id="dcdfb-118">Параметр **Credential** указывает домен и имя пользователя с разрешениями на выполнение команд на компьютере.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-118">The **Credential** parameter specifies a domain and user name with permissions to run commands on the computer.</span></span> <span data-ttu-id="dcdfb-119">Параметр **ScriptBlock** запускает `Get-Package` командлет на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-119">The **ScriptBlock** parameter runs the `Get-Package` cmdlet on the remote computer.</span></span>

### <span data-ttu-id="dcdfb-120">Пример 3. получение пакетов для указанного поставщика</span><span class="sxs-lookup"><span data-stu-id="dcdfb-120">Example 3: Get packages for a specified provider</span></span>

<span data-ttu-id="dcdfb-121">Эта команда получает пакеты программного обеспечения, установленные на локальном компьютере, от определенного поставщика.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-121">This command gets software packages installed on the local computer from a specific provider.</span></span>

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

<span data-ttu-id="dcdfb-122">`Get-Package` использует параметр **providerName** для указания конкретного поставщика, **PowerShellGet**.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-122">`Get-Package` uses the **ProviderName** parameter to specify a specific provider, **PowerShellGet**.</span></span>
<span data-ttu-id="dcdfb-123">Параметр **все-Versions** отображает каждую установленную версию.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-123">The **All-Versions** parameter displays each version that is installed.</span></span>

### <span data-ttu-id="dcdfb-124">Пример 4. получение точной версии конкретного пакета</span><span class="sxs-lookup"><span data-stu-id="dcdfb-124">Example 4: Get an exact version of a specific package</span></span>

<span data-ttu-id="dcdfb-125">Эта команда возвращает определенную версию установленного пакета.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-125">This command gets a specific version of an installed package.</span></span> <span data-ttu-id="dcdfb-126">Можно установить более одной версии пакета.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-126">More than one version of a package can be installed.</span></span>

```powershell
Get-Package -Name PackageManagement -ProviderName PowerShellGet -RequiredVersion 1.3.1
```

```Output
Name                  Version      Source                                     ProviderName
----                  -------      ------                                     ------------
PackageManagement     1.3.1        https://www.powershellgallery.com/api/v2   PowerShellGet
```

<span data-ttu-id="dcdfb-127">`Get-Package` использует параметр **Name** для указания имени пакета, **PackageManagement**.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-127">`Get-Package` uses **Name** parameter to specify the package name, **PackageManagement**.</span></span> <span data-ttu-id="dcdfb-128">Параметр **providerName** указывает поставщика, **PowerShellGet**.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-128">The **ProviderName** parameter specifies the provider, **PowerShellGet**.</span></span> <span data-ttu-id="dcdfb-129">Параметр **требуемой версии** указывает установленную версию.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-129">The **Required-Version** parameter specifies an installed version.</span></span>

### <span data-ttu-id="dcdfb-130">Пример 5. Удаление пакета</span><span class="sxs-lookup"><span data-stu-id="dcdfb-130">Example 5: Uninstall a package</span></span>

<span data-ttu-id="dcdfb-131">В этом примере получается информация о пакете, а затем удаляется пакет.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-131">This example gets package information and then uninstalls the package.</span></span>

```powershell
Get-Package -Name posh-git -RequiredVersion 0.7.3 | Uninstall-Package
```

<span data-ttu-id="dcdfb-132">`Get-Package` использует параметр **Name** для указания имени пакета **Posh-Git**.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-132">`Get-Package` uses the **Name** parameter to specify the package name, **posh-git**.</span></span> <span data-ttu-id="dcdfb-133">Параметр **RequiredVersion** — это конкретная версия пакета.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-133">The **RequiredVersion** parameter is a specific version of the package.</span></span> <span data-ttu-id="dcdfb-134">Объект отправляется по конвейеру в `Uninstall-Package` командлет.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-134">The object is sent down the pipeline to the `Uninstall-Package` cmdlet.</span></span> <span data-ttu-id="dcdfb-135">`Uninstall-Package` Удаляет пакет.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-135">`Uninstall-Package` removes the package.</span></span>

## <span data-ttu-id="dcdfb-136">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="dcdfb-136">PARAMETERS</span></span>

### <span data-ttu-id="dcdfb-137">-AllowClobber</span><span class="sxs-lookup"><span data-stu-id="dcdfb-137">-AllowClobber</span></span>

<span data-ttu-id="dcdfb-138">Переопределяет предупреждающие сообщения о конфликтах с существующими командами.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-138">Overrides warning messages about conflicts with existing commands.</span></span> <span data-ttu-id="dcdfb-139">Перезаписывает существующие команды, имена которых совпадают с именами команд, устанавливаемых модулем.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-139">Overwrites existing commands that have the same name as commands being installed by a module.</span></span>

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

### <span data-ttu-id="dcdfb-140">-Алловпререлеасеверсионс</span><span class="sxs-lookup"><span data-stu-id="dcdfb-140">-AllowPrereleaseVersions</span></span>

<span data-ttu-id="dcdfb-141">Включает пакеты, помеченные как предварительные выпуски в результатах.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-141">Includes packages marked as a prerelease in the results.</span></span>

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

### <span data-ttu-id="dcdfb-142">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="dcdfb-142">-AllVersions</span></span>

<span data-ttu-id="dcdfb-143">Указывает, что `Get-Package` возвращает все доступные версии пакета.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-143">Indicates that `Get-Package` returns all available versions of the package.</span></span> <span data-ttu-id="dcdfb-144">По умолчанию `Get-Package` возвращает только последнюю доступную версию.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-144">By default, `Get-Package` only returns the newest available version.</span></span>

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

### <span data-ttu-id="dcdfb-145">-Destination</span><span class="sxs-lookup"><span data-stu-id="dcdfb-145">-Destination</span></span>

<span data-ttu-id="dcdfb-146">Указывает путь к каталогу, содержащему извлеченные файлы пакета.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-146">Specifies the path to a directory that contains extracted package files.</span></span>

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

### <span data-ttu-id="dcdfb-147">-Ексклудеверсион</span><span class="sxs-lookup"><span data-stu-id="dcdfb-147">-ExcludeVersion</span></span>

<span data-ttu-id="dcdfb-148">Переключитесь, чтобы исключить номер версии из пути к папке.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-148">Switch to exclude the version number in the folder path.</span></span>

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

### <span data-ttu-id="dcdfb-149">-Force</span><span class="sxs-lookup"><span data-stu-id="dcdfb-149">-Force</span></span>

<span data-ttu-id="dcdfb-150">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-150">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="dcdfb-151">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="dcdfb-151">-ForceBootstrap</span></span>

<span data-ttu-id="dcdfb-152">Указывает, что `Get-Package` заставляет **PackageManagement** автоматически устанавливать поставщик пакетов.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-152">Indicates that `Get-Package` forces **PackageManagement** to automatically install the package provider.</span></span>

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

### <span data-ttu-id="dcdfb-153">-Инсталлупдате</span><span class="sxs-lookup"><span data-stu-id="dcdfb-153">-InstallUpdate</span></span>

<span data-ttu-id="dcdfb-154">Указывает, что этот командлет устанавливает обновления.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-154">Indicates that this cmdlet installs updates.</span></span>

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

### <span data-ttu-id="dcdfb-155">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="dcdfb-155">-MaximumVersion</span></span>

<span data-ttu-id="dcdfb-156">Указывает максимальную версию пакета, которую нужно найти.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-156">Specifies the maximum package version that you want to find.</span></span>

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

### <span data-ttu-id="dcdfb-157">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="dcdfb-157">-MinimumVersion</span></span>

<span data-ttu-id="dcdfb-158">Указывает минимальную версию пакета, которую нужно найти.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-158">Specifies the minimum package version that you want to find.</span></span> <span data-ttu-id="dcdfb-159">Если доступна более высокая версия, возвращается эта версия.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-159">If a higher version is available, that version is returned.</span></span>

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

### <span data-ttu-id="dcdfb-160">-Name</span><span class="sxs-lookup"><span data-stu-id="dcdfb-160">-Name</span></span>

<span data-ttu-id="dcdfb-161">Указывает одно или несколько имен пакетов или имена пакетов с подстановочными знаками.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-161">Specifies one or more package names, or package names with wildcard characters.</span></span> <span data-ttu-id="dcdfb-162">Несколько имен пакетов следует разделять запятыми.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-162">Separate multiple package names with commas.</span></span>

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

### <span data-ttu-id="dcdfb-163">-NoPathUpdate</span><span class="sxs-lookup"><span data-stu-id="dcdfb-163">-NoPathUpdate</span></span>

<span data-ttu-id="dcdfb-164">**NoPathUpdate** применяется только к `Install-Script` командлету.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-164">**NoPathUpdate** only applies to the `Install-Script` cmdlet.</span></span> <span data-ttu-id="dcdfb-165">**NoPathUpdate** — это динамический параметр, добавленный поставщиком и не поддерживаемый `Get-Package` .</span><span class="sxs-lookup"><span data-stu-id="dcdfb-165">**NoPathUpdate** is a dynamic parameter added by the provider and isn't supported by `Get-Package`.</span></span>

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

### <span data-ttu-id="dcdfb-166">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="dcdfb-166">-PackageManagementProvider</span></span>

<span data-ttu-id="dcdfb-167">Указывает имя поставщика управления пакетами.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-167">Specifies the name of a package management provider.</span></span>

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

### <span data-ttu-id="dcdfb-168">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="dcdfb-168">-ProviderName</span></span>

<span data-ttu-id="dcdfb-169">Указывает одно или несколько имен поставщиков пакетов.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-169">Specifies one or more package provider names.</span></span> <span data-ttu-id="dcdfb-170">Несколько имен поставщиков пакетов следует разделять запятыми.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-170">Separate multiple package provider names with commas.</span></span>
<span data-ttu-id="dcdfb-171">Используйте `Get-PackageProvider` для получения списка доступных поставщиков пакетов.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-171">Use `Get-PackageProvider` to get a list of available package providers.</span></span>

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

### <span data-ttu-id="dcdfb-172">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="dcdfb-172">-RequiredVersion</span></span>

<span data-ttu-id="dcdfb-173">Указывает точную версию пакета для поиска.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-173">Specifies the exact version of the package to find.</span></span>

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

### <span data-ttu-id="dcdfb-174">-Scope</span><span class="sxs-lookup"><span data-stu-id="dcdfb-174">-Scope</span></span>

<span data-ttu-id="dcdfb-175">Указывает область поиска для пакета.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-175">Specifies the search scope for the package.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: CurrentUser, AllUsers

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="dcdfb-176">-СкипдепенденЦиес</span><span class="sxs-lookup"><span data-stu-id="dcdfb-176">-SkipDependencies</span></span>

<span data-ttu-id="dcdfb-177">Параметр, задающий пропуск поиска зависимостей пакетов.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-177">Switch that specifies to skip finding any package dependencies.</span></span>

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

### <span data-ttu-id="dcdfb-178">-Скиппублишерчекк</span><span class="sxs-lookup"><span data-stu-id="dcdfb-178">-SkipPublisherCheck</span></span>

<span data-ttu-id="dcdfb-179">Позволяет получить версию пакета, более новую по сравнению с установленной версией.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-179">Allows you to get a package version that is newer than your installed version.</span></span> <span data-ttu-id="dcdfb-180">Например, установленный пакет с цифровой подписью доверенного издателя, но новая версия не подписана цифровой подписью.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-180">For example, an installed package that is digitally signed by a trusted publisher but a new version isn't digitally signed.</span></span>

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

### <span data-ttu-id="dcdfb-181">-Type</span><span class="sxs-lookup"><span data-stu-id="dcdfb-181">-Type</span></span>

<span data-ttu-id="dcdfb-182">Указывает, следует ли выполнять поиск пакетов с помощью модуля, скрипта или либо.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-182">Specifies whether to search for packages with a module, a script, or either.</span></span>

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

### <span data-ttu-id="dcdfb-183">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="dcdfb-183">CommonParameters</span></span>

<span data-ttu-id="dcdfb-184">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-184">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="dcdfb-185">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="dcdfb-185">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="dcdfb-186">Входные данные</span><span class="sxs-lookup"><span data-stu-id="dcdfb-186">INPUTS</span></span>

## <span data-ttu-id="dcdfb-187">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="dcdfb-187">OUTPUTS</span></span>

### <span data-ttu-id="dcdfb-188">Софтвареидентити []</span><span class="sxs-lookup"><span data-stu-id="dcdfb-188">SoftwareIdentity[]</span></span>

## <span data-ttu-id="dcdfb-189">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="dcdfb-189">NOTES</span></span>

<span data-ttu-id="dcdfb-190">Включение поставщика пакетов в команду может сделать динамические параметры доступными для командлета.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-190">Including a package provider in a command can make dynamic parameters available to a cmdlet.</span></span> <span data-ttu-id="dcdfb-191">Динамические параметры относятся к поставщику пакетов.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-191">Dynamic parameters are specific to a package provider.</span></span> <span data-ttu-id="dcdfb-192">`Get-Help`Командлет перечисляет наборы параметров командлета и включает набор параметров поставщика.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-192">The `Get-Help` cmdlet lists a cmdlet's parameter sets and includes the provider's parameter set.</span></span> <span data-ttu-id="dcdfb-193">Например, `Get-Package` имеет набор параметров **PowerShellGet** , включающий `-NoPathUpdate` , `AllowClobber` и `SkipPublisherCheck` .</span><span class="sxs-lookup"><span data-stu-id="dcdfb-193">For example, `Get-Package` has the **PowerShellGet** parameter set that includes `-NoPathUpdate`, `AllowClobber`, and `SkipPublisherCheck`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dcdfb-194">Начиная с апреля 2020 года коллекция PowerShell не поддерживает протокол TLS (Transport Layer Security) версий 1.0 и 1.1.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-194">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="dcdfb-195">Если вы не используете TLS 1.2 или более поздней версии, при попытке доступа к коллекции PowerShell возникнет ошибка.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-195">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="dcdfb-196">Чтобы проверить, используется ли TLS 1.2, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="dcdfb-196">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="dcdfb-197">Дополнительные сведения см. в [объявлении](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) в блоге, посвященном PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dcdfb-197">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="dcdfb-198">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="dcdfb-198">RELATED LINKS</span></span>

[<span data-ttu-id="dcdfb-199">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="dcdfb-199">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="dcdfb-200">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="dcdfb-200">Enter-PSSession</span></span>](../Microsoft.PowerShell.Core/Enter-PSSession.md)

[<span data-ttu-id="dcdfb-201">Find-Package</span><span class="sxs-lookup"><span data-stu-id="dcdfb-201">Find-Package</span></span>](Find-Package.md)

[<span data-ttu-id="dcdfb-202">Get-Help</span><span class="sxs-lookup"><span data-stu-id="dcdfb-202">Get-Help</span></span>](../Microsoft.PowerShell.Core/Get-Help.md)

[<span data-ttu-id="dcdfb-203">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="dcdfb-203">Get-PackageProvider</span></span>](Get-PackageProvider.md)

[<span data-ttu-id="dcdfb-204">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="dcdfb-204">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="dcdfb-205">Install-Package</span><span class="sxs-lookup"><span data-stu-id="dcdfb-205">Install-Package</span></span>](Install-Package.md)

[<span data-ttu-id="dcdfb-206">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="dcdfb-206">Invoke-Command</span></span>](../Microsoft.PowerShell.Core/Invoke-Command.md)

[<span data-ttu-id="dcdfb-207">Save-Package</span><span class="sxs-lookup"><span data-stu-id="dcdfb-207">Save-Package</span></span>](Save-Package.md)

[<span data-ttu-id="dcdfb-208">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="dcdfb-208">Uninstall-Package</span></span>](Uninstall-Package.md)
