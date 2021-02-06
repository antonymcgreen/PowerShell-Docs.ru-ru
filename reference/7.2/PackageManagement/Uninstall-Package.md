---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
Locale: en-US
Module Name: PackageManagement
ms.date: 05/24/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/uninstall-package?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Uninstall-Package
ms.openlocfilehash: ca12f7f2118a004a6f474ae8174b04f9dbb9444d
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601095"
---
# <span data-ttu-id="f54c5-102">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="f54c5-102">Uninstall-Package</span></span>

## <span data-ttu-id="f54c5-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="f54c5-103">SYNOPSIS</span></span>
<span data-ttu-id="f54c5-104">Удаляет один или несколько пакетов программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="f54c5-104">Uninstalls one or more software packages.</span></span>

## <span data-ttu-id="f54c5-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f54c5-105">SYNTAX</span></span>

### <span data-ttu-id="f54c5-106">паккажебинпутобжект</span><span class="sxs-lookup"><span data-stu-id="f54c5-106">PackageByInputObject</span></span>

```
Uninstall-Package [-InputObject] <SoftwareIdentity[]> [-AllVersions] [-Force] [-ForceBootstrap]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="f54c5-107">паккажебисеарч</span><span class="sxs-lookup"><span data-stu-id="f54c5-107">PackageBySearch</span></span>

```
Uninstall-Package [-Name] <String[]> [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-ProviderName <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="f54c5-108">NuGet: Паккажебинпутобжект</span><span class="sxs-lookup"><span data-stu-id="f54c5-108">NuGet:PackageByInputObject</span></span>

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-Destination <String>] [-ExcludeVersion] [-Scope <String>] [-SkipDependencies]
 [<CommonParameters>]
```

### <span data-ttu-id="f54c5-109">NuGet: Паккажебисеарч</span><span class="sxs-lookup"><span data-stu-id="f54c5-109">NuGet:PackageBySearch</span></span>

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-Destination <String>] [-ExcludeVersion] [-Scope <String>] [-SkipDependencies]
 [<CommonParameters>]
```

### <span data-ttu-id="f54c5-110">PowerShellGet: Паккажебинпутобжект</span><span class="sxs-lookup"><span data-stu-id="f54c5-110">PowerShellGet:PackageByInputObject</span></span>

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-Scope <String>]
 [-PackageManagementProvider <String>] [-Type <String>] [-AllowClobber] [-SkipPublisherCheck]
 [-InstallUpdate] [-NoPathUpdate] [-AllowPrereleaseVersions] [<CommonParameters>]
```

### <span data-ttu-id="f54c5-111">PowerShellGet: Паккажебисеарч</span><span class="sxs-lookup"><span data-stu-id="f54c5-111">PowerShellGet:PackageBySearch</span></span>

```
Uninstall-Package [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-Scope <String>]
 [-PackageManagementProvider <String>] [-Type <String>] [-AllowClobber] [-SkipPublisherCheck]
 [-InstallUpdate] [-NoPathUpdate] [-AllowPrereleaseVersions] [<CommonParameters>]
```

## <span data-ttu-id="f54c5-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f54c5-112">DESCRIPTION</span></span>

<span data-ttu-id="f54c5-113">`Uninstall-Package`Командлет удаляет один или несколько пакетов программного обеспечения с локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="f54c5-113">The `Uninstall-Package` cmdlet uninstalls one or more software packages from the local computer.</span></span> <span data-ttu-id="f54c5-114">Чтобы найти установленные пакеты, используйте `Get-Package` командлет.</span><span class="sxs-lookup"><span data-stu-id="f54c5-114">To find installed packages, use the `Get-Package` cmdlet.</span></span>

## <span data-ttu-id="f54c5-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="f54c5-115">EXAMPLES</span></span>

### <span data-ttu-id="f54c5-116">Пример 1. Удаление пакета</span><span class="sxs-lookup"><span data-stu-id="f54c5-116">Example 1: Uninstall a package</span></span>

<span data-ttu-id="f54c5-117">`Uninstall-Package`Командлет удаляет пакеты.</span><span class="sxs-lookup"><span data-stu-id="f54c5-117">The `Uninstall-Package` cmdlet uninstalls packages.</span></span> <span data-ttu-id="f54c5-118">Параметр **Name** указывает пакет для удаления.</span><span class="sxs-lookup"><span data-stu-id="f54c5-118">The **Name** parameter specifies the package to uninstall.</span></span> <span data-ttu-id="f54c5-119">При установке нескольких версий пакета удаляется последняя версия.</span><span class="sxs-lookup"><span data-stu-id="f54c5-119">If multiple versions of a package are installed, the newest version is uninstalled.</span></span>

```
PS> Uninstall-Package -Name NuGet.Core
```

### <span data-ttu-id="f54c5-120">Пример 2. Использование конвейера для удаления пакета</span><span class="sxs-lookup"><span data-stu-id="f54c5-120">Example 2: Use the pipeline to uninstall a package</span></span>

<span data-ttu-id="f54c5-121">`Get-Package` находит конкретный пакет и отправляет объект **софтвареидентити** по конвейеру в `Uninsall-Package` командлет.</span><span class="sxs-lookup"><span data-stu-id="f54c5-121">`Get-Package` locates a specific package and sends the **SoftwareIdentity** object down the pipeline to the `Uninsall-Package` cmdlet.</span></span>

```
PS> Get-Package -Name NuGet.Core -RequiredVersion 2.14.0 | Uninstall-Package
```

<span data-ttu-id="f54c5-122">`Get-Package`Для указания пакета командлет использует параметры **Name** и **RequiredVersion** .</span><span class="sxs-lookup"><span data-stu-id="f54c5-122">The `Get-Package` cmdlet uses the **Name** and **RequiredVersion** parameters to specify a package.</span></span>
<span data-ttu-id="f54c5-123">Объект **софтвареидентити** отправляется вниз по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="f54c5-123">A **SoftwareIdentity** object is sent down the pipeline.</span></span> <span data-ttu-id="f54c5-124">`Uninstall-Package`Командлет получает объект в качестве **InputObject** и удаляет пакет.</span><span class="sxs-lookup"><span data-stu-id="f54c5-124">The `Uninstall-Package` cmdlet receives the object as an **InputObject** and removes the package.</span></span>

<span data-ttu-id="f54c5-125">В качестве альтернативы `Uninstall-Package` командлет может указать значение для параметра **InputObject** :</span><span class="sxs-lookup"><span data-stu-id="f54c5-125">As an alternative, the `Uninstall-Package` cmdlet can specify a value for the **InputObject** parameter:</span></span>

`Uninstall-Package -InputObject ( Get-Package -Name NuGet.Core -RequiredVersion 2.14.0 )`

## <span data-ttu-id="f54c5-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f54c5-126">PARAMETERS</span></span>

### <span data-ttu-id="f54c5-127">-AllowClobber</span><span class="sxs-lookup"><span data-stu-id="f54c5-127">-AllowClobber</span></span>

<span data-ttu-id="f54c5-128">Переопределяет предупреждающие сообщения о конфликтах с существующими командами.</span><span class="sxs-lookup"><span data-stu-id="f54c5-128">Overrides warning messages about conflicts with existing commands.</span></span> <span data-ttu-id="f54c5-129">Перезаписывает существующие команды, имена которых совпадают с именами устанавливаемых команд.</span><span class="sxs-lookup"><span data-stu-id="f54c5-129">Overwrites existing commands that have the same name as commands being installed.</span></span>

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

### <span data-ttu-id="f54c5-130">-Алловпререлеасеверсионс</span><span class="sxs-lookup"><span data-stu-id="f54c5-130">-AllowPrereleaseVersions</span></span>

<span data-ttu-id="f54c5-131">Позволяет удалять пакеты, помеченные как предварительные.</span><span class="sxs-lookup"><span data-stu-id="f54c5-131">Allows packages marked as prerelease to be uninstalled.</span></span>

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

### <span data-ttu-id="f54c5-132">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="f54c5-132">-AllVersions</span></span>

<span data-ttu-id="f54c5-133">Указывает, что этот командлет удаляет все версии пакета.</span><span class="sxs-lookup"><span data-stu-id="f54c5-133">Indicates that this cmdlet uninstalls all versions of the package.</span></span>

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

### <span data-ttu-id="f54c5-134">-Destination</span><span class="sxs-lookup"><span data-stu-id="f54c5-134">-Destination</span></span>

<span data-ttu-id="f54c5-135">Задает строку пути к входному объекту.</span><span class="sxs-lookup"><span data-stu-id="f54c5-135">Specifies a string of the path to the input object.</span></span>

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

### <span data-ttu-id="f54c5-136">-Ексклудеверсион</span><span class="sxs-lookup"><span data-stu-id="f54c5-136">-ExcludeVersion</span></span>

<span data-ttu-id="f54c5-137">Переключитесь, чтобы исключить номер версии из пути к папке.</span><span class="sxs-lookup"><span data-stu-id="f54c5-137">Switch to exclude the version number in the folder path.</span></span>

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

### <span data-ttu-id="f54c5-138">-Force</span><span class="sxs-lookup"><span data-stu-id="f54c5-138">-Force</span></span>

<span data-ttu-id="f54c5-139">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="f54c5-139">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="f54c5-140">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="f54c5-140">-ForceBootstrap</span></span>

<span data-ttu-id="f54c5-141">Заставляет службу **PackageManagement** автоматически устанавливать поставщик пакетов для указанного пакета.</span><span class="sxs-lookup"><span data-stu-id="f54c5-141">Forces **PackageManagement** to automatically install the package provider for the specified package.</span></span>

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

### <span data-ttu-id="f54c5-142">-InputObject</span><span class="sxs-lookup"><span data-stu-id="f54c5-142">-InputObject</span></span>

<span data-ttu-id="f54c5-143">Принимает входные данные конвейера, указывающие объект пакета **софтвареидентити** из `Get-Package` командлета.</span><span class="sxs-lookup"><span data-stu-id="f54c5-143">Accepts pipeline input that specifies the package's **SoftwareIdentity** object from the `Get-Package` cmdlet.</span></span> <span data-ttu-id="f54c5-144">**InputObject** принимает объект **софтвареидентити** как `Get-Package` значение или переменную, содержащую объект.</span><span class="sxs-lookup"><span data-stu-id="f54c5-144">**InputObject** accepts the **SoftwareIdentity** object as a `Get-Package` value or a variable that contains the object.</span></span>

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

### <span data-ttu-id="f54c5-145">-Инсталлупдате</span><span class="sxs-lookup"><span data-stu-id="f54c5-145">-InstallUpdate</span></span>

<span data-ttu-id="f54c5-146">Указывает, что `Uninstall-Package` удаляет обновления.</span><span class="sxs-lookup"><span data-stu-id="f54c5-146">Indicates that `Uninstall-Package` uninstalls updates.</span></span>

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

### <span data-ttu-id="f54c5-147">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="f54c5-147">-MaximumVersion</span></span>

<span data-ttu-id="f54c5-148">Указывает максимально допустимую версию пакета, которую требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="f54c5-148">Specifies the maximum allowed package version that you want to uninstall.</span></span> <span data-ttu-id="f54c5-149">Если этот параметр не указан, `Uninstall-Package` удаляется последняя версия пакета.</span><span class="sxs-lookup"><span data-stu-id="f54c5-149">If you don't specify this parameter, `Uninstall-Package` uninstalls the package's newest version.</span></span>

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

### <span data-ttu-id="f54c5-150">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="f54c5-150">-MinimumVersion</span></span>

<span data-ttu-id="f54c5-151">Указывает минимальную допустимую версию пакета, которую необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="f54c5-151">Specifies the minimum allowed package version that you want to uninstall.</span></span> <span data-ttu-id="f54c5-152">Если вы не добавите этот параметр, `Uninstall-Package` удаляет последнюю версию пакета, соответствующую любой версии, указанной параметром **MaximumVersion** .</span><span class="sxs-lookup"><span data-stu-id="f54c5-152">If you don't add this parameter, `Uninstall-Package` uninstalls the package's newest version that satisfies any version specified by the **MaximumVersion** parameter.</span></span>

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

### <span data-ttu-id="f54c5-153">-Name</span><span class="sxs-lookup"><span data-stu-id="f54c5-153">-Name</span></span>

<span data-ttu-id="f54c5-154">Указывает одно или несколько имен пакетов.</span><span class="sxs-lookup"><span data-stu-id="f54c5-154">Specifies one or more package names.</span></span> <span data-ttu-id="f54c5-155">Несколько имен пакетов должны быть разделены запятыми.</span><span class="sxs-lookup"><span data-stu-id="f54c5-155">Multiple package names must be separated by commas.</span></span>

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

### <span data-ttu-id="f54c5-156">-NoPathUpdate</span><span class="sxs-lookup"><span data-stu-id="f54c5-156">-NoPathUpdate</span></span>

<span data-ttu-id="f54c5-157">**NoPathUpdate** применяется только к `Install-Script` командлету.</span><span class="sxs-lookup"><span data-stu-id="f54c5-157">**NoPathUpdate** only applies to the `Install-Script` cmdlet.</span></span> <span data-ttu-id="f54c5-158">**NoPathUpdate** — это динамический параметр, добавленный поставщиком и не поддерживаемый `Uninstall-Package` .</span><span class="sxs-lookup"><span data-stu-id="f54c5-158">**NoPathUpdate** is a dynamic parameter added by the provider and isn't supported by `Uninstall-Package`.</span></span>

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

### <span data-ttu-id="f54c5-159">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="f54c5-159">-PackageManagementProvider</span></span>

<span data-ttu-id="f54c5-160">Указывает поставщика **PackageManagement** .</span><span class="sxs-lookup"><span data-stu-id="f54c5-160">Specifies the **PackageManagement** provider.</span></span>

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

### <span data-ttu-id="f54c5-161">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="f54c5-161">-ProviderName</span></span>

<span data-ttu-id="f54c5-162">Указывает одно или несколько имен поставщиков пакетов для поиска пакетов.</span><span class="sxs-lookup"><span data-stu-id="f54c5-162">Specifies one or more package provider names to search for packages.</span></span> <span data-ttu-id="f54c5-163">Чтобы получить имена поставщиков пакетов, выполните командлет `Get-PackageProvider`.</span><span class="sxs-lookup"><span data-stu-id="f54c5-163">You can get package provider names by running the `Get-PackageProvider` cmdlet.</span></span>

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

### <span data-ttu-id="f54c5-164">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="f54c5-164">-RequiredVersion</span></span>

<span data-ttu-id="f54c5-165">Указывает точную допустимую версию пакета, который требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="f54c5-165">Specifies the exact allowed version of the package that you want to uninstall.</span></span> <span data-ttu-id="f54c5-166">Если вы не добавите этот параметр, `Uninstall-Package` удаляет последнюю версию пакета, соответствующую любой версии, указанной параметром **MaximumVersion** .</span><span class="sxs-lookup"><span data-stu-id="f54c5-166">If you don't add this parameter, `Uninstall-Package` uninstalls the package's newest version that satisfies any version specified by the **MaximumVersion** parameter.</span></span>

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

### <span data-ttu-id="f54c5-167">-Scope</span><span class="sxs-lookup"><span data-stu-id="f54c5-167">-Scope</span></span>

<span data-ttu-id="f54c5-168">Указывает область, для которой необходимо удалить пакет.</span><span class="sxs-lookup"><span data-stu-id="f54c5-168">Specifies the scope for which to uninstall the package.</span></span> <span data-ttu-id="f54c5-169">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="f54c5-169">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="f54c5-170">CurrentUser</span><span class="sxs-lookup"><span data-stu-id="f54c5-170">CurrentUser</span></span>
- <span data-ttu-id="f54c5-171">AllUsers</span><span class="sxs-lookup"><span data-stu-id="f54c5-171">AllUsers</span></span>

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

### <span data-ttu-id="f54c5-172">-СкипдепенденЦиес</span><span class="sxs-lookup"><span data-stu-id="f54c5-172">-SkipDependencies</span></span>

<span data-ttu-id="f54c5-173">Пропускает удаление зависимостей программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="f54c5-173">Skips the uninstallation of software dependencies.</span></span>

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

### <span data-ttu-id="f54c5-174">-Скиппублишерчекк</span><span class="sxs-lookup"><span data-stu-id="f54c5-174">-SkipPublisherCheck</span></span>

<span data-ttu-id="f54c5-175">Позволяет получить версию пакета, более новую по сравнению с установленной версией.</span><span class="sxs-lookup"><span data-stu-id="f54c5-175">Allows you to get a package version that is newer than your installed version.</span></span> <span data-ttu-id="f54c5-176">Например, установленный пакет с цифровой подписью доверенного издателя, но новая версия не подписана цифровой подписью.</span><span class="sxs-lookup"><span data-stu-id="f54c5-176">For example, an installed package that is digitally signed by a trusted publisher but a new version isn't digitally signed.</span></span>

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

### <span data-ttu-id="f54c5-177">-Type</span><span class="sxs-lookup"><span data-stu-id="f54c5-177">-Type</span></span>

<span data-ttu-id="f54c5-178">Указывает, следует ли выполнять поиск пакетов с помощью модуля, скрипта или и того, и другого.</span><span class="sxs-lookup"><span data-stu-id="f54c5-178">Specifies whether to search for packages with a module, a script, or both.</span></span> <span data-ttu-id="f54c5-179">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="f54c5-179">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="f54c5-180">Модуль</span><span class="sxs-lookup"><span data-stu-id="f54c5-180">Module</span></span>
- <span data-ttu-id="f54c5-181">Скрипт</span><span class="sxs-lookup"><span data-stu-id="f54c5-181">Script</span></span>
- <span data-ttu-id="f54c5-182">Все</span><span class="sxs-lookup"><span data-stu-id="f54c5-182">All</span></span>

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

### <span data-ttu-id="f54c5-183">-Confirm</span><span class="sxs-lookup"><span data-stu-id="f54c5-183">-Confirm</span></span>

<span data-ttu-id="f54c5-184">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="f54c5-184">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="f54c5-185">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="f54c5-185">-WhatIf</span></span>

<span data-ttu-id="f54c5-186">Показывает, что произойдет при `Uninstall-Package` запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="f54c5-186">Shows what would happen if `Uninstall-Package` cmdlet is run.</span></span> <span data-ttu-id="f54c5-187">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="f54c5-187">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="f54c5-188">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="f54c5-188">CommonParameters</span></span>

<span data-ttu-id="f54c5-189">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f54c5-189">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f54c5-190">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f54c5-190">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f54c5-191">Входные данные</span><span class="sxs-lookup"><span data-stu-id="f54c5-191">INPUTS</span></span>

### <span data-ttu-id="f54c5-192">`Uninstall-Package` принимает объекты **софтвареидентити** из конвейера в качестве входных данных.</span><span class="sxs-lookup"><span data-stu-id="f54c5-192">`Uninstall-Package` accepts **SoftwareIdentity** objects from the pipeline as input.</span></span>

## <span data-ttu-id="f54c5-193">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="f54c5-193">OUTPUTS</span></span>

### <span data-ttu-id="f54c5-194">`Uninstall-Package` не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="f54c5-194">`Uninstall-Package` doesn't generate any output.</span></span>

## <span data-ttu-id="f54c5-195">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="f54c5-195">NOTES</span></span>

<span data-ttu-id="f54c5-196">Включение поставщика пакетов в команду может сделать динамические параметры доступными для командлета.</span><span class="sxs-lookup"><span data-stu-id="f54c5-196">Including a package provider in a command can make dynamic parameters available to a cmdlet.</span></span> <span data-ttu-id="f54c5-197">Динамические параметры относятся к поставщику пакетов.</span><span class="sxs-lookup"><span data-stu-id="f54c5-197">Dynamic parameters are specific to a package provider.</span></span> <span data-ttu-id="f54c5-198">`Get-Help`Командлет перечисляет наборы параметров командлета и включает набор параметров поставщика.</span><span class="sxs-lookup"><span data-stu-id="f54c5-198">The `Get-Help` cmdlet lists a cmdlet's parameter sets and includes the provider's parameter set.</span></span> <span data-ttu-id="f54c5-199">Например, `Uninstall-Package` имеет набор параметров **PowerShellGet** , включающий `-NoPathUpdate` , `AllowClobber` и `SkipPublisherCheck` .</span><span class="sxs-lookup"><span data-stu-id="f54c5-199">For example, `Uninstall-Package` has the **PowerShellGet** parameter set that includes `-NoPathUpdate`, `AllowClobber`, and `SkipPublisherCheck`.</span></span>

## <span data-ttu-id="f54c5-200">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="f54c5-200">RELATED LINKS</span></span>

[<span data-ttu-id="f54c5-201">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="f54c5-201">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="f54c5-202">Find-Package</span><span class="sxs-lookup"><span data-stu-id="f54c5-202">Find-Package</span></span>](Find-Package.md)

[<span data-ttu-id="f54c5-203">Get-Package</span><span class="sxs-lookup"><span data-stu-id="f54c5-203">Get-Package</span></span>](Get-Package.md)

[<span data-ttu-id="f54c5-204">Install-Package</span><span class="sxs-lookup"><span data-stu-id="f54c5-204">Install-Package</span></span>](Install-Package.md)

[<span data-ttu-id="f54c5-205">Save-Package</span><span class="sxs-lookup"><span data-stu-id="f54c5-205">Save-Package</span></span>](Save-Package.md)

