---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PackageManagement
ms.date: 05/24/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/uninstall-package?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Uninstall-Package
ms.openlocfilehash: 6f22da7040413f64e9e96a7df57401a0701156bd
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227298"
---
# <span data-ttu-id="90e22-103">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="90e22-103">Uninstall-Package</span></span>

## <span data-ttu-id="90e22-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="90e22-104">SYNOPSIS</span></span>
<span data-ttu-id="90e22-105">Удаляет один или несколько пакетов программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="90e22-105">Uninstalls one or more software packages.</span></span>

## <span data-ttu-id="90e22-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="90e22-106">SYNTAX</span></span>

### <span data-ttu-id="90e22-107">паккажебинпутобжект</span><span class="sxs-lookup"><span data-stu-id="90e22-107">PackageByInputObject</span></span>

```
Uninstall-Package [-InputObject] <SoftwareIdentity[]> [-AllVersions] [-Force] [-ForceBootstrap]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="90e22-108">паккажебисеарч</span><span class="sxs-lookup"><span data-stu-id="90e22-108">PackageBySearch</span></span>

```
Uninstall-Package [-Name] <String[]> [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-ProviderName <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="90e22-109">MSI: Паккажебинпутобжект</span><span class="sxs-lookup"><span data-stu-id="90e22-109">msi:PackageByInputObject</span></span>

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-AdditionalArguments <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="90e22-110">MSI: Паккажебисеарч</span><span class="sxs-lookup"><span data-stu-id="90e22-110">msi:PackageBySearch</span></span>

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-AdditionalArguments <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="90e22-111">Программы: Паккажебинпутобжект</span><span class="sxs-lookup"><span data-stu-id="90e22-111">Programs:PackageByInputObject</span></span>

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-IncludeWindowsInstaller] [-IncludeSystemComponent] [<CommonParameters>]
```

### <span data-ttu-id="90e22-112">Программы: Паккажебисеарч</span><span class="sxs-lookup"><span data-stu-id="90e22-112">Programs:PackageBySearch</span></span>

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-IncludeWindowsInstaller] [-IncludeSystemComponent] [<CommonParameters>]
```

### <span data-ttu-id="90e22-113">NuGet: Паккажебинпутобжект</span><span class="sxs-lookup"><span data-stu-id="90e22-113">NuGet:PackageByInputObject</span></span>

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-Destination <String>] [-ExcludeVersion] [-Scope <String>] [-SkipDependencies]
 [<CommonParameters>]
```

### <span data-ttu-id="90e22-114">NuGet: Паккажебисеарч</span><span class="sxs-lookup"><span data-stu-id="90e22-114">NuGet:PackageBySearch</span></span>

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-Destination <String>] [-ExcludeVersion] [-Scope <String>] [-SkipDependencies]
 [<CommonParameters>]
```

### <span data-ttu-id="90e22-115">PowerShellGet: Паккажебинпутобжект</span><span class="sxs-lookup"><span data-stu-id="90e22-115">PowerShellGet:PackageByInputObject</span></span>

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-Scope <String>]
 [-PackageManagementProvider <String>] [-Type <String>] [-AllowClobber] [-SkipPublisherCheck]
 [-InstallUpdate] [-NoPathUpdate] [-AllowPrereleaseVersions] [<CommonParameters>]
```

### <span data-ttu-id="90e22-116">PowerShellGet: Паккажебисеарч</span><span class="sxs-lookup"><span data-stu-id="90e22-116">PowerShellGet:PackageBySearch</span></span>

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-Scope <String>]
 [-PackageManagementProvider <String>] [-Type <String>] [-AllowClobber] [-SkipPublisherCheck]
 [-InstallUpdate] [-NoPathUpdate] [-AllowPrereleaseVersions] [<CommonParameters>]
```

## <span data-ttu-id="90e22-117">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="90e22-117">DESCRIPTION</span></span>

<span data-ttu-id="90e22-118">`Uninstall-Package`Командлет удаляет один или несколько пакетов программного обеспечения с локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="90e22-118">The `Uninstall-Package` cmdlet uninstalls one or more software packages from the local computer.</span></span> <span data-ttu-id="90e22-119">Чтобы найти установленные пакеты, используйте `Get-Package` командлет.</span><span class="sxs-lookup"><span data-stu-id="90e22-119">To find installed packages, use the `Get-Package` cmdlet.</span></span>

## <span data-ttu-id="90e22-120">Примеры</span><span class="sxs-lookup"><span data-stu-id="90e22-120">EXAMPLES</span></span>

### <span data-ttu-id="90e22-121">Пример 1. Удаление пакета</span><span class="sxs-lookup"><span data-stu-id="90e22-121">Example 1: Uninstall a package</span></span>

<span data-ttu-id="90e22-122">`Uninstall-Package`Командлет удаляет пакеты.</span><span class="sxs-lookup"><span data-stu-id="90e22-122">The `Uninstall-Package` cmdlet uninstalls packages.</span></span> <span data-ttu-id="90e22-123">Параметр **Name** указывает пакет для удаления.</span><span class="sxs-lookup"><span data-stu-id="90e22-123">The **Name** parameter specifies the package to uninstall.</span></span> <span data-ttu-id="90e22-124">При установке нескольких версий пакета удаляется последняя версия.</span><span class="sxs-lookup"><span data-stu-id="90e22-124">If multiple versions of a package are installed, the newest version is uninstalled.</span></span>

```
PS> Uninstall-Package -Name NuGet.Core
```

### <span data-ttu-id="90e22-125">Пример 2. Использование конвейера для удаления пакета</span><span class="sxs-lookup"><span data-stu-id="90e22-125">Example 2: Use the pipeline to uninstall a package</span></span>

<span data-ttu-id="90e22-126">`Get-Package` находит конкретный пакет и отправляет объект **софтвареидентити** по конвейеру в `Uninsall-Package` командлет.</span><span class="sxs-lookup"><span data-stu-id="90e22-126">`Get-Package` locates a specific package and sends the **SoftwareIdentity** object down the pipeline to the `Uninsall-Package` cmdlet.</span></span>

```
PS> Get-Package -Name NuGet.Core -RequiredVersion 2.14.0 | Uninstall-Package
```

<span data-ttu-id="90e22-127">`Get-Package`Для указания пакета командлет использует параметры **Name** и **RequiredVersion** .</span><span class="sxs-lookup"><span data-stu-id="90e22-127">The `Get-Package` cmdlet uses the **Name** and **RequiredVersion** parameters to specify a package.</span></span>
<span data-ttu-id="90e22-128">Объект **софтвареидентити** отправляется вниз по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="90e22-128">A **SoftwareIdentity** object is sent down the pipeline.</span></span> <span data-ttu-id="90e22-129">`Uninstall-Package`Командлет получает объект в качестве **InputObject** и удаляет пакет.</span><span class="sxs-lookup"><span data-stu-id="90e22-129">The `Uninstall-Package` cmdlet receives the object as an **InputObject** and removes the package.</span></span>

<span data-ttu-id="90e22-130">В качестве альтернативы `Uninstall-Package` командлет может указать значение для параметра **InputObject** :</span><span class="sxs-lookup"><span data-stu-id="90e22-130">As an alternative, the `Uninstall-Package` cmdlet can specify a value for the **InputObject** parameter:</span></span>

`Uninstall-Package -InputObject ( Get-Package -Name NuGet.Core -RequiredVersion 2.14.0 )`

## <span data-ttu-id="90e22-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="90e22-131">PARAMETERS</span></span>

### <span data-ttu-id="90e22-132">-AllowClobber</span><span class="sxs-lookup"><span data-stu-id="90e22-132">-AllowClobber</span></span>

<span data-ttu-id="90e22-133">Переопределяет предупреждающие сообщения о конфликтах с существующими командами.</span><span class="sxs-lookup"><span data-stu-id="90e22-133">Overrides warning messages about conflicts with existing commands.</span></span> <span data-ttu-id="90e22-134">Перезаписывает существующие команды, имена которых совпадают с именами устанавливаемых команд.</span><span class="sxs-lookup"><span data-stu-id="90e22-134">Overwrites existing commands that have the same name as commands being installed.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="90e22-135">-Алловпререлеасеверсионс</span><span class="sxs-lookup"><span data-stu-id="90e22-135">-AllowPrereleaseVersions</span></span>

<span data-ttu-id="90e22-136">Позволяет удалять пакеты, помеченные как предварительные.</span><span class="sxs-lookup"><span data-stu-id="90e22-136">Allows packages marked as prerelease to be uninstalled.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="90e22-137">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="90e22-137">-AllVersions</span></span>

<span data-ttu-id="90e22-138">Указывает, что этот командлет удаляет все версии пакета.</span><span class="sxs-lookup"><span data-stu-id="90e22-138">Indicates that this cmdlet uninstalls all versions of the package.</span></span>

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

### <span data-ttu-id="90e22-139">-Destination</span><span class="sxs-lookup"><span data-stu-id="90e22-139">-Destination</span></span>

<span data-ttu-id="90e22-140">Задает строку пути к входному объекту.</span><span class="sxs-lookup"><span data-stu-id="90e22-140">Specifies a string of the path to the input object.</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet:PackageByInputObject, NuGet:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="90e22-141">-Ексклудеверсион</span><span class="sxs-lookup"><span data-stu-id="90e22-141">-ExcludeVersion</span></span>

<span data-ttu-id="90e22-142">Переключитесь, чтобы исключить номер версии из пути к папке.</span><span class="sxs-lookup"><span data-stu-id="90e22-142">Switch to exclude the version number in the folder path.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet:PackageByInputObject, NuGet:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="90e22-143">-Force</span><span class="sxs-lookup"><span data-stu-id="90e22-143">-Force</span></span>

<span data-ttu-id="90e22-144">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="90e22-144">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="90e22-145">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="90e22-145">-ForceBootstrap</span></span>

<span data-ttu-id="90e22-146">Заставляет службу **PackageManagement** автоматически устанавливать поставщик пакетов для указанного пакета.</span><span class="sxs-lookup"><span data-stu-id="90e22-146">Forces **PackageManagement** to automatically install the package provider for the specified package.</span></span>

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

### <span data-ttu-id="90e22-147">-InputObject</span><span class="sxs-lookup"><span data-stu-id="90e22-147">-InputObject</span></span>

<span data-ttu-id="90e22-148">Принимает входные данные конвейера, указывающие объект пакета **софтвареидентити** из `Get-Package` командлета.</span><span class="sxs-lookup"><span data-stu-id="90e22-148">Accepts pipeline input that specifies the package's **SoftwareIdentity** object from the `Get-Package` cmdlet.</span></span> <span data-ttu-id="90e22-149">**InputObject** принимает объект **софтвареидентити** как `Get-Package` значение или переменную, содержащую объект.</span><span class="sxs-lookup"><span data-stu-id="90e22-149">**InputObject** accepts the **SoftwareIdentity** object as a `Get-Package` value or a variable that contains the object.</span></span>

```yaml
Type: Microsoft.PackageManagement.Packaging.SoftwareIdentity[]
Parameter Sets: PackageByInputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="90e22-150">-Инсталлупдате</span><span class="sxs-lookup"><span data-stu-id="90e22-150">-InstallUpdate</span></span>

<span data-ttu-id="90e22-151">Указывает, что `Uninstall-Package` удаляет обновления.</span><span class="sxs-lookup"><span data-stu-id="90e22-151">Indicates that `Uninstall-Package` uninstalls updates.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="90e22-152">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="90e22-152">-MaximumVersion</span></span>

<span data-ttu-id="90e22-153">Указывает максимально допустимую версию пакета, которую требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="90e22-153">Specifies the maximum allowed package version that you want to uninstall.</span></span> <span data-ttu-id="90e22-154">Если этот параметр не указан, `Uninstall-Package` удаляется последняя версия пакета.</span><span class="sxs-lookup"><span data-stu-id="90e22-154">If you don't specify this parameter, `Uninstall-Package` uninstalls the package's newest version.</span></span>

```yaml
Type: System.String
Parameter Sets: PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="90e22-155">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="90e22-155">-MinimumVersion</span></span>

<span data-ttu-id="90e22-156">Указывает минимальную допустимую версию пакета, которую необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="90e22-156">Specifies the minimum allowed package version that you want to uninstall.</span></span> <span data-ttu-id="90e22-157">Если вы не добавите этот параметр, `Uninstall-Package` удаляет последнюю версию пакета, соответствующую любой версии, указанной параметром **MaximumVersion** .</span><span class="sxs-lookup"><span data-stu-id="90e22-157">If you don't add this parameter, `Uninstall-Package` uninstalls the package's newest version that satisfies any version specified by the **MaximumVersion** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="90e22-158">-Name</span><span class="sxs-lookup"><span data-stu-id="90e22-158">-Name</span></span>

<span data-ttu-id="90e22-159">Указывает одно или несколько имен пакетов.</span><span class="sxs-lookup"><span data-stu-id="90e22-159">Specifies one or more package names.</span></span> <span data-ttu-id="90e22-160">Несколько имен пакетов должны быть разделены запятыми.</span><span class="sxs-lookup"><span data-stu-id="90e22-160">Multiple package names must be separated by commas.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PackageBySearch
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="90e22-161">-NoPathUpdate</span><span class="sxs-lookup"><span data-stu-id="90e22-161">-NoPathUpdate</span></span>

<span data-ttu-id="90e22-162">**NoPathUpdate** применяется только к `Install-Script` командлету.</span><span class="sxs-lookup"><span data-stu-id="90e22-162">**NoPathUpdate** only applies to the `Install-Script` cmdlet.</span></span> <span data-ttu-id="90e22-163">**NoPathUpdate** — это динамический параметр, добавленный поставщиком и не поддерживаемый `Uninstall-Package` .</span><span class="sxs-lookup"><span data-stu-id="90e22-163">**NoPathUpdate** is a dynamic parameter added by the provider and isn't supported by `Uninstall-Package`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="90e22-164">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="90e22-164">-PackageManagementProvider</span></span>

<span data-ttu-id="90e22-165">Указывает поставщика **PackageManagement** .</span><span class="sxs-lookup"><span data-stu-id="90e22-165">Specifies the **PackageManagement** provider.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="90e22-166">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="90e22-166">-ProviderName</span></span>

<span data-ttu-id="90e22-167">Указывает одно или несколько имен поставщиков пакетов для поиска пакетов.</span><span class="sxs-lookup"><span data-stu-id="90e22-167">Specifies one or more package provider names to search for packages.</span></span> <span data-ttu-id="90e22-168">Чтобы получить имена поставщиков пакетов, выполните командлет `Get-PackageProvider`.</span><span class="sxs-lookup"><span data-stu-id="90e22-168">You can get package provider names by running the `Get-PackageProvider` cmdlet.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PackageBySearch
Aliases: Provider
Accepted values: Bootstrap, NuGet, PowerShellGet

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="90e22-169">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="90e22-169">-RequiredVersion</span></span>

<span data-ttu-id="90e22-170">Указывает точную допустимую версию пакета, который требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="90e22-170">Specifies the exact allowed version of the package that you want to uninstall.</span></span> <span data-ttu-id="90e22-171">Если вы не добавите этот параметр, `Uninstall-Package` удаляет последнюю версию пакета, соответствующую любой версии, указанной параметром **MaximumVersion** .</span><span class="sxs-lookup"><span data-stu-id="90e22-171">If you don't add this parameter, `Uninstall-Package` uninstalls the package's newest version that satisfies any version specified by the **MaximumVersion** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="90e22-172">-Scope</span><span class="sxs-lookup"><span data-stu-id="90e22-172">-Scope</span></span>

<span data-ttu-id="90e22-173">Указывает область, для которой необходимо удалить пакет.</span><span class="sxs-lookup"><span data-stu-id="90e22-173">Specifies the scope for which to uninstall the package.</span></span> <span data-ttu-id="90e22-174">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="90e22-174">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="90e22-175">CurrentUser</span><span class="sxs-lookup"><span data-stu-id="90e22-175">CurrentUser</span></span>
- <span data-ttu-id="90e22-176">AllUsers</span><span class="sxs-lookup"><span data-stu-id="90e22-176">AllUsers</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet:PackageByInputObject, NuGet:PackageBySearch, PowerShellGet:PackageByInputObject, PowerShellGet:PackageBySearch
Aliases:
Accepted values: CurrentUser, AllUsers

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="90e22-177">-СкипдепенденЦиес</span><span class="sxs-lookup"><span data-stu-id="90e22-177">-SkipDependencies</span></span>

<span data-ttu-id="90e22-178">Пропускает удаление зависимостей программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="90e22-178">Skips the uninstallation of software dependencies.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet:PackageByInputObject, NuGet:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="90e22-179">-Скиппублишерчекк</span><span class="sxs-lookup"><span data-stu-id="90e22-179">-SkipPublisherCheck</span></span>

<span data-ttu-id="90e22-180">Позволяет получить версию пакета, более новую по сравнению с установленной версией.</span><span class="sxs-lookup"><span data-stu-id="90e22-180">Allows you to get a package version that is newer than your installed version.</span></span> <span data-ttu-id="90e22-181">Например, установленный пакет с цифровой подписью доверенного издателя, но новая версия не подписана цифровой подписью.</span><span class="sxs-lookup"><span data-stu-id="90e22-181">For example, an installed package that is digitally signed by a trusted publisher but a new version isn't digitally signed.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="90e22-182">-Type</span><span class="sxs-lookup"><span data-stu-id="90e22-182">-Type</span></span>

<span data-ttu-id="90e22-183">Указывает, следует ли выполнять поиск пакетов с помощью модуля, скрипта или и того, и другого.</span><span class="sxs-lookup"><span data-stu-id="90e22-183">Specifies whether to search for packages with a module, a script, or both.</span></span> <span data-ttu-id="90e22-184">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="90e22-184">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="90e22-185">Модуль</span><span class="sxs-lookup"><span data-stu-id="90e22-185">Module</span></span>
- <span data-ttu-id="90e22-186">Скрипт</span><span class="sxs-lookup"><span data-stu-id="90e22-186">Script</span></span>
- <span data-ttu-id="90e22-187">Все</span><span class="sxs-lookup"><span data-stu-id="90e22-187">All</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet:PackageBySearch
Aliases:
Accepted values: Module, Script, All

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="90e22-188">-Confirm</span><span class="sxs-lookup"><span data-stu-id="90e22-188">-Confirm</span></span>

<span data-ttu-id="90e22-189">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="90e22-189">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="90e22-190">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="90e22-190">-WhatIf</span></span>

<span data-ttu-id="90e22-191">Показывает, что произойдет при `Uninstall-Package` запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="90e22-191">Shows what would happen if `Uninstall-Package` cmdlet is run.</span></span> <span data-ttu-id="90e22-192">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="90e22-192">The cmdlet isn't run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="90e22-193">-Аддитионаларгументс</span><span class="sxs-lookup"><span data-stu-id="90e22-193">-AdditionalArguments</span></span>

<span data-ttu-id="90e22-194">Задает дополнительные аргументы.</span><span class="sxs-lookup"><span data-stu-id="90e22-194">Specifies additional arguments.</span></span>

```yaml
Type: System.String[]
Parameter Sets: msi:PackageByInputObject, msi:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="90e22-195">-Инклудесистемкомпонент</span><span class="sxs-lookup"><span data-stu-id="90e22-195">-IncludeSystemComponent</span></span>

<span data-ttu-id="90e22-196">Указывает, что этот командлет удаляет компоненты системы.</span><span class="sxs-lookup"><span data-stu-id="90e22-196">Specifies that this cmdlet uninstalls system components.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Programs:PackageByInputObject, Programs:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="90e22-197">-Инклудевиндовсинсталлер</span><span class="sxs-lookup"><span data-stu-id="90e22-197">-IncludeWindowsInstaller</span></span>

<span data-ttu-id="90e22-198">Указывает, что этот командлет удаляет пакет с помощью установщик Windows.</span><span class="sxs-lookup"><span data-stu-id="90e22-198">Indicates that this cmdlet uninstalls the package through Windows Installer.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Programs:PackageByInputObject, Programs:PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="90e22-199">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="90e22-199">CommonParameters</span></span>

<span data-ttu-id="90e22-200">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="90e22-200">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="90e22-201">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="90e22-201">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="90e22-202">Входные данные</span><span class="sxs-lookup"><span data-stu-id="90e22-202">INPUTS</span></span>

### <span data-ttu-id="90e22-203">`Uninstall-Package` принимает объекты **софтвареидентити** из конвейера в качестве входных данных.</span><span class="sxs-lookup"><span data-stu-id="90e22-203">`Uninstall-Package` accepts **SoftwareIdentity** objects from the pipeline as input.</span></span>

## <span data-ttu-id="90e22-204">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="90e22-204">OUTPUTS</span></span>

### <span data-ttu-id="90e22-205">`Uninstall-Package` не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="90e22-205">`Uninstall-Package` doesn't generate any output.</span></span>

## <span data-ttu-id="90e22-206">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="90e22-206">NOTES</span></span>

<span data-ttu-id="90e22-207">Включение поставщика пакетов в команду может сделать динамические параметры доступными для командлета.</span><span class="sxs-lookup"><span data-stu-id="90e22-207">Including a package provider in a command can make dynamic parameters available to a cmdlet.</span></span> <span data-ttu-id="90e22-208">Динамические параметры относятся к поставщику пакетов.</span><span class="sxs-lookup"><span data-stu-id="90e22-208">Dynamic parameters are specific to a package provider.</span></span> <span data-ttu-id="90e22-209">`Get-Help`Командлет перечисляет наборы параметров командлета и включает набор параметров поставщика.</span><span class="sxs-lookup"><span data-stu-id="90e22-209">The `Get-Help` cmdlet lists a cmdlet's parameter sets and includes the provider's parameter set.</span></span> <span data-ttu-id="90e22-210">Например, `Uninstall-Package` имеет набор параметров **PowerShellGet** , включающий `-NoPathUpdate` , `AllowClobber` и `SkipPublisherCheck` .</span><span class="sxs-lookup"><span data-stu-id="90e22-210">For example, `Uninstall-Package` has the **PowerShellGet** parameter set that includes `-NoPathUpdate`, `AllowClobber`, and `SkipPublisherCheck`.</span></span>

## <span data-ttu-id="90e22-211">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="90e22-211">RELATED LINKS</span></span>

[<span data-ttu-id="90e22-212">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="90e22-212">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="90e22-213">Find-Package</span><span class="sxs-lookup"><span data-stu-id="90e22-213">Find-Package</span></span>](Find-Package.md)

[<span data-ttu-id="90e22-214">Get-Package</span><span class="sxs-lookup"><span data-stu-id="90e22-214">Get-Package</span></span>](Get-Package.md)

[<span data-ttu-id="90e22-215">Install-Package</span><span class="sxs-lookup"><span data-stu-id="90e22-215">Install-Package</span></span>](Install-Package.md)

[<span data-ttu-id="90e22-216">Save-Package</span><span class="sxs-lookup"><span data-stu-id="90e22-216">Save-Package</span></span>](Save-Package.md)
