---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PackageManagement
ms.date: 05/24/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/uninstall-package?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Uninstall-Package
ms.openlocfilehash: 4da97d9643483db0eae4fc7d34e0e6997d16bd04
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228549"
---
# <span data-ttu-id="e7f9a-103">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="e7f9a-103">Uninstall-Package</span></span>

## <span data-ttu-id="e7f9a-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="e7f9a-104">SYNOPSIS</span></span>
<span data-ttu-id="e7f9a-105">Удаляет один или несколько пакетов программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="e7f9a-105">Uninstalls one or more software packages.</span></span>

## <span data-ttu-id="e7f9a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e7f9a-106">SYNTAX</span></span>

### <span data-ttu-id="e7f9a-107">паккажебинпутобжект</span><span class="sxs-lookup"><span data-stu-id="e7f9a-107">PackageByInputObject</span></span>

```
Uninstall-Package [-InputObject] <SoftwareIdentity[]> [-AllVersions] [-Force] [-ForceBootstrap]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="e7f9a-108">паккажебисеарч</span><span class="sxs-lookup"><span data-stu-id="e7f9a-108">PackageBySearch</span></span>

```
Uninstall-Package [-Name] <String[]> [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-ProviderName <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="e7f9a-109">NuGet: Паккажебинпутобжект</span><span class="sxs-lookup"><span data-stu-id="e7f9a-109">NuGet:PackageByInputObject</span></span>

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-Destination <String>] [-ExcludeVersion] [-Scope <String>] [-SkipDependencies]
 [<CommonParameters>]
```

### <span data-ttu-id="e7f9a-110">NuGet: Паккажебисеарч</span><span class="sxs-lookup"><span data-stu-id="e7f9a-110">NuGet:PackageBySearch</span></span>

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-Destination <String>] [-ExcludeVersion] [-Scope <String>] [-SkipDependencies]
 [<CommonParameters>]
```

### <span data-ttu-id="e7f9a-111">PowerShellGet: Паккажебинпутобжект</span><span class="sxs-lookup"><span data-stu-id="e7f9a-111">PowerShellGet:PackageByInputObject</span></span>

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-Scope <String>]
 [-PackageManagementProvider <String>] [-Type <String>] [-AllowClobber] [-SkipPublisherCheck]
 [-InstallUpdate] [-NoPathUpdate] [-AllowPrereleaseVersions] [<CommonParameters>]
```

### <span data-ttu-id="e7f9a-112">PowerShellGet: Паккажебисеарч</span><span class="sxs-lookup"><span data-stu-id="e7f9a-112">PowerShellGet:PackageBySearch</span></span>

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-Scope <String>]
 [-PackageManagementProvider <String>] [-Type <String>] [-AllowClobber] [-SkipPublisherCheck]
 [-InstallUpdate] [-NoPathUpdate] [-AllowPrereleaseVersions] [<CommonParameters>]
```

## <span data-ttu-id="e7f9a-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e7f9a-113">DESCRIPTION</span></span>

<span data-ttu-id="e7f9a-114">`Uninstall-Package`Командлет удаляет один или несколько пакетов программного обеспечения с локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="e7f9a-114">The `Uninstall-Package` cmdlet uninstalls one or more software packages from the local computer.</span></span> <span data-ttu-id="e7f9a-115">Чтобы найти установленные пакеты, используйте `Get-Package` командлет.</span><span class="sxs-lookup"><span data-stu-id="e7f9a-115">To find installed packages, use the `Get-Package` cmdlet.</span></span>

## <span data-ttu-id="e7f9a-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="e7f9a-116">EXAMPLES</span></span>

### <span data-ttu-id="e7f9a-117">Пример 1. Удаление пакета</span><span class="sxs-lookup"><span data-stu-id="e7f9a-117">Example 1: Uninstall a package</span></span>

<span data-ttu-id="e7f9a-118">`Uninstall-Package`Командлет удаляет пакеты.</span><span class="sxs-lookup"><span data-stu-id="e7f9a-118">The `Uninstall-Package` cmdlet uninstalls packages.</span></span> <span data-ttu-id="e7f9a-119">Параметр **Name** указывает пакет для удаления.</span><span class="sxs-lookup"><span data-stu-id="e7f9a-119">The **Name** parameter specifies the package to uninstall.</span></span> <span data-ttu-id="e7f9a-120">При установке нескольких версий пакета удаляется последняя версия.</span><span class="sxs-lookup"><span data-stu-id="e7f9a-120">If multiple versions of a package are installed, the newest version is uninstalled.</span></span>

```
PS> Uninstall-Package -Name NuGet.Core
```

### <span data-ttu-id="e7f9a-121">Пример 2. Использование конвейера для удаления пакета</span><span class="sxs-lookup"><span data-stu-id="e7f9a-121">Example 2: Use the pipeline to uninstall a package</span></span>

<span data-ttu-id="e7f9a-122">`Get-Package` находит конкретный пакет и отправляет объект **софтвареидентити** по конвейеру в `Uninsall-Package` командлет.</span><span class="sxs-lookup"><span data-stu-id="e7f9a-122">`Get-Package` locates a specific package and sends the **SoftwareIdentity** object down the pipeline to the `Uninsall-Package` cmdlet.</span></span>

```
PS> Get-Package -Name NuGet.Core -RequiredVersion 2.14.0 | Uninstall-Package
```

<span data-ttu-id="e7f9a-123">`Get-Package`Для указания пакета командлет использует параметры **Name** и **RequiredVersion** .</span><span class="sxs-lookup"><span data-stu-id="e7f9a-123">The `Get-Package` cmdlet uses the **Name** and **RequiredVersion** parameters to specify a package.</span></span>
<span data-ttu-id="e7f9a-124">Объект **софтвареидентити** отправляется вниз по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="e7f9a-124">A **SoftwareIdentity** object is sent down the pipeline.</span></span> <span data-ttu-id="e7f9a-125">`Uninstall-Package`Командлет получает объект в качестве **InputObject** и удаляет пакет.</span><span class="sxs-lookup"><span data-stu-id="e7f9a-125">The `Uninstall-Package` cmdlet receives the object as an **InputObject** and removes the package.</span></span>

<span data-ttu-id="e7f9a-126">В качестве альтернативы `Uninstall-Package` командлет может указать значение для параметра **InputObject** :</span><span class="sxs-lookup"><span data-stu-id="e7f9a-126">As an alternative, the `Uninstall-Package` cmdlet can specify a value for the **InputObject** parameter:</span></span>

`Uninstall-Package -InputObject ( Get-Package -Name NuGet.Core -RequiredVersion 2.14.0 )`

## <span data-ttu-id="e7f9a-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e7f9a-127">PARAMETERS</span></span>

### <span data-ttu-id="e7f9a-128">-AllowClobber</span><span class="sxs-lookup"><span data-stu-id="e7f9a-128">-AllowClobber</span></span>

<span data-ttu-id="e7f9a-129">Переопределяет предупреждающие сообщения о конфликтах с существующими командами.</span><span class="sxs-lookup"><span data-stu-id="e7f9a-129">Overrides warning messages about conflicts with existing commands.</span></span> <span data-ttu-id="e7f9a-130">Перезаписывает существующие команды, имена которых совпадают с именами устанавливаемых команд.</span><span class="sxs-lookup"><span data-stu-id="e7f9a-130">Overwrites existing commands that have the same name as commands being installed.</span></span>

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

### <span data-ttu-id="e7f9a-131">-Алловпререлеасеверсионс</span><span class="sxs-lookup"><span data-stu-id="e7f9a-131">-AllowPrereleaseVersions</span></span>

<span data-ttu-id="e7f9a-132">Позволяет удалять пакеты, помеченные как предварительные.</span><span class="sxs-lookup"><span data-stu-id="e7f9a-132">Allows packages marked as prerelease to be uninstalled.</span></span>

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

### <span data-ttu-id="e7f9a-133">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="e7f9a-133">-AllVersions</span></span>

<span data-ttu-id="e7f9a-134">Указывает, что этот командлет удаляет все версии пакета.</span><span class="sxs-lookup"><span data-stu-id="e7f9a-134">Indicates that this cmdlet uninstalls all versions of the package.</span></span>

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

### <span data-ttu-id="e7f9a-135">-Destination</span><span class="sxs-lookup"><span data-stu-id="e7f9a-135">-Destination</span></span>

<span data-ttu-id="e7f9a-136">Задает строку пути к входному объекту.</span><span class="sxs-lookup"><span data-stu-id="e7f9a-136">Specifies a string of the path to the input object.</span></span>

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

### <span data-ttu-id="e7f9a-137">-Ексклудеверсион</span><span class="sxs-lookup"><span data-stu-id="e7f9a-137">-ExcludeVersion</span></span>

<span data-ttu-id="e7f9a-138">Переключитесь, чтобы исключить номер версии из пути к папке.</span><span class="sxs-lookup"><span data-stu-id="e7f9a-138">Switch to exclude the version number in the folder path.</span></span>

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

### <span data-ttu-id="e7f9a-139">-Force</span><span class="sxs-lookup"><span data-stu-id="e7f9a-139">-Force</span></span>

<span data-ttu-id="e7f9a-140">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="e7f9a-140">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="e7f9a-141">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="e7f9a-141">-ForceBootstrap</span></span>

<span data-ttu-id="e7f9a-142">Заставляет службу **PackageManagement** автоматически устанавливать поставщик пакетов для указанного пакета.</span><span class="sxs-lookup"><span data-stu-id="e7f9a-142">Forces **PackageManagement** to automatically install the package provider for the specified package.</span></span>

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

### <span data-ttu-id="e7f9a-143">-InputObject</span><span class="sxs-lookup"><span data-stu-id="e7f9a-143">-InputObject</span></span>

<span data-ttu-id="e7f9a-144">Принимает входные данные конвейера, указывающие объект пакета **софтвареидентити** из `Get-Package` командлета.</span><span class="sxs-lookup"><span data-stu-id="e7f9a-144">Accepts pipeline input that specifies the package's **SoftwareIdentity** object from the `Get-Package` cmdlet.</span></span> <span data-ttu-id="e7f9a-145">**InputObject** принимает объект **софтвареидентити** как `Get-Package` значение или переменную, содержащую объект.</span><span class="sxs-lookup"><span data-stu-id="e7f9a-145">**InputObject** accepts the **SoftwareIdentity** object as a `Get-Package` value or a variable that contains the object.</span></span>

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

### <span data-ttu-id="e7f9a-146">-Инсталлупдате</span><span class="sxs-lookup"><span data-stu-id="e7f9a-146">-InstallUpdate</span></span>

<span data-ttu-id="e7f9a-147">Указывает, что `Uninstall-Package` удаляет обновления.</span><span class="sxs-lookup"><span data-stu-id="e7f9a-147">Indicates that `Uninstall-Package` uninstalls updates.</span></span>

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

### <span data-ttu-id="e7f9a-148">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="e7f9a-148">-MaximumVersion</span></span>

<span data-ttu-id="e7f9a-149">Указывает максимально допустимую версию пакета, которую требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="e7f9a-149">Specifies the maximum allowed package version that you want to uninstall.</span></span> <span data-ttu-id="e7f9a-150">Если этот параметр не указан, `Uninstall-Package` удаляется последняя версия пакета.</span><span class="sxs-lookup"><span data-stu-id="e7f9a-150">If you don't specify this parameter, `Uninstall-Package` uninstalls the package's newest version.</span></span>

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

### <span data-ttu-id="e7f9a-151">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="e7f9a-151">-MinimumVersion</span></span>

<span data-ttu-id="e7f9a-152">Указывает минимальную допустимую версию пакета, которую необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="e7f9a-152">Specifies the minimum allowed package version that you want to uninstall.</span></span> <span data-ttu-id="e7f9a-153">Если вы не добавите этот параметр, `Uninstall-Package` удаляет последнюю версию пакета, соответствующую любой версии, указанной параметром **MaximumVersion** .</span><span class="sxs-lookup"><span data-stu-id="e7f9a-153">If you don't add this parameter, `Uninstall-Package` uninstalls the package's newest version that satisfies any version specified by the **MaximumVersion** parameter.</span></span>

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

### <span data-ttu-id="e7f9a-154">-Name</span><span class="sxs-lookup"><span data-stu-id="e7f9a-154">-Name</span></span>

<span data-ttu-id="e7f9a-155">Указывает одно или несколько имен пакетов.</span><span class="sxs-lookup"><span data-stu-id="e7f9a-155">Specifies one or more package names.</span></span> <span data-ttu-id="e7f9a-156">Несколько имен пакетов должны быть разделены запятыми.</span><span class="sxs-lookup"><span data-stu-id="e7f9a-156">Multiple package names must be separated by commas.</span></span>

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

### <span data-ttu-id="e7f9a-157">-NoPathUpdate</span><span class="sxs-lookup"><span data-stu-id="e7f9a-157">-NoPathUpdate</span></span>

<span data-ttu-id="e7f9a-158">**NoPathUpdate** применяется только к `Install-Script` командлету.</span><span class="sxs-lookup"><span data-stu-id="e7f9a-158">**NoPathUpdate** only applies to the `Install-Script` cmdlet.</span></span> <span data-ttu-id="e7f9a-159">**NoPathUpdate** — это динамический параметр, добавленный поставщиком и не поддерживаемый `Uninstall-Package` .</span><span class="sxs-lookup"><span data-stu-id="e7f9a-159">**NoPathUpdate** is a dynamic parameter added by the provider and isn't supported by `Uninstall-Package`.</span></span>

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

### <span data-ttu-id="e7f9a-160">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="e7f9a-160">-PackageManagementProvider</span></span>

<span data-ttu-id="e7f9a-161">Указывает поставщика **PackageManagement** .</span><span class="sxs-lookup"><span data-stu-id="e7f9a-161">Specifies the **PackageManagement** provider.</span></span>

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

### <span data-ttu-id="e7f9a-162">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="e7f9a-162">-ProviderName</span></span>

<span data-ttu-id="e7f9a-163">Указывает одно или несколько имен поставщиков пакетов для поиска пакетов.</span><span class="sxs-lookup"><span data-stu-id="e7f9a-163">Specifies one or more package provider names to search for packages.</span></span> <span data-ttu-id="e7f9a-164">Чтобы получить имена поставщиков пакетов, выполните командлет `Get-PackageProvider`.</span><span class="sxs-lookup"><span data-stu-id="e7f9a-164">You can get package provider names by running the `Get-PackageProvider` cmdlet.</span></span>

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

### <span data-ttu-id="e7f9a-165">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="e7f9a-165">-RequiredVersion</span></span>

<span data-ttu-id="e7f9a-166">Указывает точную допустимую версию пакета, который требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="e7f9a-166">Specifies the exact allowed version of the package that you want to uninstall.</span></span> <span data-ttu-id="e7f9a-167">Если вы не добавите этот параметр, `Uninstall-Package` удаляет последнюю версию пакета, соответствующую любой версии, указанной параметром **MaximumVersion** .</span><span class="sxs-lookup"><span data-stu-id="e7f9a-167">If you don't add this parameter, `Uninstall-Package` uninstalls the package's newest version that satisfies any version specified by the **MaximumVersion** parameter.</span></span>

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

### <span data-ttu-id="e7f9a-168">-Scope</span><span class="sxs-lookup"><span data-stu-id="e7f9a-168">-Scope</span></span>

<span data-ttu-id="e7f9a-169">Указывает область, для которой необходимо удалить пакет.</span><span class="sxs-lookup"><span data-stu-id="e7f9a-169">Specifies the scope for which to uninstall the package.</span></span> <span data-ttu-id="e7f9a-170">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="e7f9a-170">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="e7f9a-171">CurrentUser</span><span class="sxs-lookup"><span data-stu-id="e7f9a-171">CurrentUser</span></span>
- <span data-ttu-id="e7f9a-172">AllUsers</span><span class="sxs-lookup"><span data-stu-id="e7f9a-172">AllUsers</span></span>

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

### <span data-ttu-id="e7f9a-173">-СкипдепенденЦиес</span><span class="sxs-lookup"><span data-stu-id="e7f9a-173">-SkipDependencies</span></span>

<span data-ttu-id="e7f9a-174">Пропускает удаление зависимостей программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="e7f9a-174">Skips the uninstallation of software dependencies.</span></span>

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

### <span data-ttu-id="e7f9a-175">-Скиппублишерчекк</span><span class="sxs-lookup"><span data-stu-id="e7f9a-175">-SkipPublisherCheck</span></span>

<span data-ttu-id="e7f9a-176">Позволяет получить версию пакета, более новую по сравнению с установленной версией.</span><span class="sxs-lookup"><span data-stu-id="e7f9a-176">Allows you to get a package version that is newer than your installed version.</span></span> <span data-ttu-id="e7f9a-177">Например, установленный пакет с цифровой подписью доверенного издателя, но новая версия не подписана цифровой подписью.</span><span class="sxs-lookup"><span data-stu-id="e7f9a-177">For example, an installed package that is digitally signed by a trusted publisher but a new version isn't digitally signed.</span></span>

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

### <span data-ttu-id="e7f9a-178">-Type</span><span class="sxs-lookup"><span data-stu-id="e7f9a-178">-Type</span></span>

<span data-ttu-id="e7f9a-179">Указывает, следует ли выполнять поиск пакетов с помощью модуля, скрипта или и того, и другого.</span><span class="sxs-lookup"><span data-stu-id="e7f9a-179">Specifies whether to search for packages with a module, a script, or both.</span></span> <span data-ttu-id="e7f9a-180">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="e7f9a-180">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="e7f9a-181">Модуль</span><span class="sxs-lookup"><span data-stu-id="e7f9a-181">Module</span></span>
- <span data-ttu-id="e7f9a-182">Скрипт</span><span class="sxs-lookup"><span data-stu-id="e7f9a-182">Script</span></span>
- <span data-ttu-id="e7f9a-183">Все</span><span class="sxs-lookup"><span data-stu-id="e7f9a-183">All</span></span>

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

### <span data-ttu-id="e7f9a-184">-Confirm</span><span class="sxs-lookup"><span data-stu-id="e7f9a-184">-Confirm</span></span>

<span data-ttu-id="e7f9a-185">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="e7f9a-185">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="e7f9a-186">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="e7f9a-186">-WhatIf</span></span>

<span data-ttu-id="e7f9a-187">Показывает, что произойдет при `Uninstall-Package` запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="e7f9a-187">Shows what would happen if `Uninstall-Package` cmdlet is run.</span></span> <span data-ttu-id="e7f9a-188">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="e7f9a-188">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="e7f9a-189">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="e7f9a-189">CommonParameters</span></span>

<span data-ttu-id="e7f9a-190">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e7f9a-190">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e7f9a-191">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e7f9a-191">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e7f9a-192">Входные данные</span><span class="sxs-lookup"><span data-stu-id="e7f9a-192">INPUTS</span></span>

### <span data-ttu-id="e7f9a-193">`Uninstall-Package` принимает объекты **софтвареидентити** из конвейера в качестве входных данных.</span><span class="sxs-lookup"><span data-stu-id="e7f9a-193">`Uninstall-Package` accepts **SoftwareIdentity** objects from the pipeline as input.</span></span>

## <span data-ttu-id="e7f9a-194">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="e7f9a-194">OUTPUTS</span></span>

### <span data-ttu-id="e7f9a-195">`Uninstall-Package` не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="e7f9a-195">`Uninstall-Package` doesn't generate any output.</span></span>

## <span data-ttu-id="e7f9a-196">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="e7f9a-196">NOTES</span></span>

<span data-ttu-id="e7f9a-197">Включение поставщика пакетов в команду может сделать динамические параметры доступными для командлета.</span><span class="sxs-lookup"><span data-stu-id="e7f9a-197">Including a package provider in a command can make dynamic parameters available to a cmdlet.</span></span> <span data-ttu-id="e7f9a-198">Динамические параметры относятся к поставщику пакетов.</span><span class="sxs-lookup"><span data-stu-id="e7f9a-198">Dynamic parameters are specific to a package provider.</span></span> <span data-ttu-id="e7f9a-199">`Get-Help`Командлет перечисляет наборы параметров командлета и включает набор параметров поставщика.</span><span class="sxs-lookup"><span data-stu-id="e7f9a-199">The `Get-Help` cmdlet lists a cmdlet's parameter sets and includes the provider's parameter set.</span></span> <span data-ttu-id="e7f9a-200">Например, `Uninstall-Package` имеет набор параметров **PowerShellGet** , включающий `-NoPathUpdate` , `AllowClobber` и `SkipPublisherCheck` .</span><span class="sxs-lookup"><span data-stu-id="e7f9a-200">For example, `Uninstall-Package` has the **PowerShellGet** parameter set that includes `-NoPathUpdate`, `AllowClobber`, and `SkipPublisherCheck`.</span></span>

## <span data-ttu-id="e7f9a-201">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="e7f9a-201">RELATED LINKS</span></span>

[<span data-ttu-id="e7f9a-202">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="e7f9a-202">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="e7f9a-203">Find-Package</span><span class="sxs-lookup"><span data-stu-id="e7f9a-203">Find-Package</span></span>](Find-Package.md)

[<span data-ttu-id="e7f9a-204">Get-Package</span><span class="sxs-lookup"><span data-stu-id="e7f9a-204">Get-Package</span></span>](Get-Package.md)

[<span data-ttu-id="e7f9a-205">Install-Package</span><span class="sxs-lookup"><span data-stu-id="e7f9a-205">Install-Package</span></span>](Install-Package.md)

[<span data-ttu-id="e7f9a-206">Save-Package</span><span class="sxs-lookup"><span data-stu-id="e7f9a-206">Save-Package</span></span>](Save-Package.md)

