---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
Locale: en-US
Module Name: PackageManagement
ms.date: 04/03/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/save-package?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Save-Package
ms.openlocfilehash: 93ec8264bad588e38554daddcdf5dc9befce053e
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "99600011"
---
# <span data-ttu-id="691b2-102">Save-Package</span><span class="sxs-lookup"><span data-stu-id="691b2-102">Save-Package</span></span>

## <span data-ttu-id="691b2-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="691b2-103">SYNOPSIS</span></span>
<span data-ttu-id="691b2-104">Сохраняет пакеты на локальном компьютере, не устанавливая их.</span><span class="sxs-lookup"><span data-stu-id="691b2-104">Saves packages to the local computer without installing them.</span></span>

## <span data-ttu-id="691b2-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="691b2-105">SYNTAX</span></span>

### <span data-ttu-id="691b2-106">паккажебисеарч</span><span class="sxs-lookup"><span data-stu-id="691b2-106">PackageBySearch</span></span>

```
Save-Package [-Name] <String[]> [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-Source <String[]>] [-Path <String>] [-LiteralPath <String>]
 [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-AllVersions]
 [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-ProviderName <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="691b2-107">паккажебинпутобжект</span><span class="sxs-lookup"><span data-stu-id="691b2-107">PackageByInputObject</span></span>

```
Save-Package [-Path <String>] [-LiteralPath <String>] -InputObject <SoftwareIdentity>
 [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-AllVersions]
 [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="691b2-108">NuGet: Паккажебинпутобжект</span><span class="sxs-lookup"><span data-stu-id="691b2-108">NuGet:PackageByInputObject</span></span>

```
Save-Package [-Path <String>] [-LiteralPath <String>] [-Credential <PSCredential>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-ConfigFile <String>] [-SkipValidate] [-Headers <String[]>] [-FilterOnTag <String[]>]
 [-Contains <String>] [-AllowPrereleaseVersions] [<CommonParameters>]
```

### <span data-ttu-id="691b2-109">NuGet</span><span class="sxs-lookup"><span data-stu-id="691b2-109">NuGet</span></span>

```
Save-Package [-Path <String>] [-LiteralPath <String>] [-Credential <PSCredential>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-ConfigFile <String>] [-SkipValidate] [-Headers <String[]>] [-FilterOnTag <String[]>]
 [-Contains <String>] [-AllowPrereleaseVersions] [<CommonParameters>]
```

### <span data-ttu-id="691b2-110">PowerShellGet: Паккажебинпутобжект</span><span class="sxs-lookup"><span data-stu-id="691b2-110">PowerShellGet:PackageByInputObject</span></span>

```
Save-Package [-Path <String>] [-LiteralPath <String>] [-Credential <PSCredential>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-AllowPrereleaseVersions] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [-Type <String>]
 [-Filter <String>] [-Tag <String[]>] [-Includes <String[]>] [-DscResource <String[]>]
 [-RoleCapability <String[]>] [-Command <String[]>] [-AcceptLicense] [<CommonParameters>]
```

### <span data-ttu-id="691b2-111">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="691b2-111">PowerShellGet</span></span>

```
Save-Package [-Path <String>] [-LiteralPath <String>] [-Credential <PSCredential>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-AllowPrereleaseVersions] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [-Type <String>]
 [-Filter <String>] [-Tag <String[]>] [-Includes <String[]>] [-DscResource <String[]>]
 [-RoleCapability <String[]>] [-Command <String[]>] [-AcceptLicense] [<CommonParameters>]
```

## <span data-ttu-id="691b2-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="691b2-112">DESCRIPTION</span></span>

<span data-ttu-id="691b2-113">`Save-Package`Командлет сохраняет пакеты на локальном компьютере, но не устанавливает пакеты.</span><span class="sxs-lookup"><span data-stu-id="691b2-113">The `Save-Package` cmdlet saves packages to the local computer but doesn't install the packages.</span></span>
<span data-ttu-id="691b2-114">Этот командлет сохраняет последнюю версию пакета, если не указано значение **рекуиредверион**.</span><span class="sxs-lookup"><span data-stu-id="691b2-114">This cmdlet saves the newest version of a package unless you specify a **RequiredVerion**.</span></span> <span data-ttu-id="691b2-115">Параметры **path** и **LiteralPath** являются взаимоисключающими и не могут быть добавлены к одной и той же команде.</span><span class="sxs-lookup"><span data-stu-id="691b2-115">The **Path** and **LiteralPath** parameters are mutually exclusive, and cannot be added to the same command.</span></span>

## <span data-ttu-id="691b2-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="691b2-116">EXAMPLES</span></span>

### <span data-ttu-id="691b2-117">Пример 1. Сохранение пакета на локальном компьютере</span><span class="sxs-lookup"><span data-stu-id="691b2-117">Example 1: Save a package to the local computer</span></span>

<span data-ttu-id="691b2-118">В этом примере сохраняется последняя версия пакета в каталоге на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="691b2-118">This example saves the newest version of the package to a directory on the local computer.</span></span> <span data-ttu-id="691b2-119">Зависимости пакета загружаются вместе с пакетом.</span><span class="sxs-lookup"><span data-stu-id="691b2-119">The package's dependencies are download with the package.</span></span>

```
PS> Save-Package -Name NuGet.Core -ProviderName NuGet -Path C:\LocalPkg
```

```Output
Name                    Version    Source    Summary
----                    -------    ------    -------
Microsoft.Web.Xdt       3.0.0      Nuget     Microsoft Xml Document Transformation (XDT) enables...
NuGet.Core              2.14.0     Nuget     NuGet.Core is the core framework assembly for NuGet...
```

<span data-ttu-id="691b2-120">`Save-Package` использует параметр **Name** для указания пакета.</span><span class="sxs-lookup"><span data-stu-id="691b2-120">`Save-Package` uses the **Name** parameter to specify the package.</span></span> <span data-ttu-id="691b2-121">Пакет загружается из репозитория, указанного параметром **providerName** .</span><span class="sxs-lookup"><span data-stu-id="691b2-121">The package is downloaded from the repository specified by the **ProviderName** parameter.</span></span> <span data-ttu-id="691b2-122">Параметр **path** определяет место сохранения пакета.</span><span class="sxs-lookup"><span data-stu-id="691b2-122">The **Path** parameter determines where the package is saved.</span></span>

### <span data-ttu-id="691b2-123">Пример 2. сохранение определенной версии пакета</span><span class="sxs-lookup"><span data-stu-id="691b2-123">Example 2: Save a specific package version</span></span>

<span data-ttu-id="691b2-124">В этом примере указывается версия пакета и сохраняется в каталоге на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="691b2-124">This example specifies the package version and saves it to a directory on the local computer.</span></span>

```
PS> Save-Package -Name NuGet.Core -RequiredVersion 2.9.0 -ProviderName NuGet -Path C:\LocalPkg
```

```Output
Name                    Version    Source    Summary
----                    -------    ------    -------
Microsoft.Web.Xdt       3.0.0      Nuget     Microsoft Xml Document Transformation (XDT) enables...
NuGet.Core              2.9.0      Nuget     NuGet.Core is the core framework assembly for NuGet...
```

<span data-ttu-id="691b2-125">`Save-Package` использует параметр **Name** для указания пакета.</span><span class="sxs-lookup"><span data-stu-id="691b2-125">`Save-Package` uses the **Name** parameter to specify the package.</span></span> <span data-ttu-id="691b2-126">**RequiredVersion** обозначает конкретную версию пакета.</span><span class="sxs-lookup"><span data-stu-id="691b2-126">**RequiredVersion** indicates a specific package version.</span></span> <span data-ttu-id="691b2-127">Пакет загружается из репозитория, указанного параметром **providerName** .</span><span class="sxs-lookup"><span data-stu-id="691b2-127">The package is downloaded from the repository specified by the **ProviderName** parameter.</span></span> <span data-ttu-id="691b2-128">Параметр **path** определяет место сохранения пакета.</span><span class="sxs-lookup"><span data-stu-id="691b2-128">The **Path** parameter determines where the package is saved.</span></span>

### <span data-ttu-id="691b2-129">Пример 3. Использование Find-Package для сохранения пакета</span><span class="sxs-lookup"><span data-stu-id="691b2-129">Example 3: Use Find-Package to save a package</span></span>

<span data-ttu-id="691b2-130">Эта команда использует `Find-Package` для размещения последней версии пакета и отправляет объект в `Save-Package` .</span><span class="sxs-lookup"><span data-stu-id="691b2-130">This command uses `Find-Package` to locate the newest version of the package and sends the object to `Save-Package`.</span></span>

```
PS> Find-Package -Name NuGet.Core -ProviderName NuGet | Save-Package -Path C:\LocalPkg
```

<span data-ttu-id="691b2-131">`Find-Package` использует параметр **Name** для указания пакета.</span><span class="sxs-lookup"><span data-stu-id="691b2-131">`Find-Package` uses the **Name** parameter to specify the package.</span></span> <span data-ttu-id="691b2-132">Пакет загружается из репозитория, указанного параметром **providerName** .</span><span class="sxs-lookup"><span data-stu-id="691b2-132">The package is downloaded from the repository specified by the **ProviderName** parameter.</span></span> <span data-ttu-id="691b2-133">Объект отправляется по конвейеру в `Save-Package` .</span><span class="sxs-lookup"><span data-stu-id="691b2-133">The object is sent down the pipeline to `Save-Package`.</span></span> <span data-ttu-id="691b2-134">Параметр **path** определяет место сохранения пакета.</span><span class="sxs-lookup"><span data-stu-id="691b2-134">The **Path** parameter determines where the package is saved.</span></span>

### <span data-ttu-id="691b2-135">Пример 4. сохранение и установка пакета</span><span class="sxs-lookup"><span data-stu-id="691b2-135">Example 4: Save and install the package</span></span>

<span data-ttu-id="691b2-136">Последняя версия пакета и его зависимости загружаются и устанавливаются на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="691b2-136">The newest version of the package and its dependencies are downloaded and installed on the local computer.</span></span>

```
PS> Save-Package -Name NuGet.Core -ProviderName NuGet -Path C:\LocalPkg
PS> Install-Package C:\LocalPkg\NuGet.Core.2.14.0.nupkg
```

<span data-ttu-id="691b2-137">`Save-Package` загружает файл пакета и его зависимости на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="691b2-137">`Save-Package` downloads the package file and its dependencies to the local computer.</span></span>
<span data-ttu-id="691b2-138">`Install-Package` устанавливает пакет и зависимости из указанного каталога.</span><span class="sxs-lookup"><span data-stu-id="691b2-138">`Install-Package` installs the package and dependencies from the specified directory.</span></span>

## <span data-ttu-id="691b2-139">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="691b2-139">PARAMETERS</span></span>

### <span data-ttu-id="691b2-140">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="691b2-140">-AcceptLicense</span></span>

<span data-ttu-id="691b2-141">Автоматически принимать лицензионное соглашение во время установки, если оно требуется для пакета.</span><span class="sxs-lookup"><span data-stu-id="691b2-141">Automatically accept the license agreement during installation if the package requires it.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="691b2-142">-Алловпререлеасеверсионс</span><span class="sxs-lookup"><span data-stu-id="691b2-142">-AllowPrereleaseVersions</span></span>

<span data-ttu-id="691b2-143">Разрешает сохранение пакетов, помеченных как предварительные.</span><span class="sxs-lookup"><span data-stu-id="691b2-143">Allows packages marked as Prerelease to be saved.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet:PackageByInputObject, NuGet, PowerShellGet:PackageByInputObject, PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="691b2-144">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="691b2-144">-AllVersions</span></span>

<span data-ttu-id="691b2-145">Указывает, что этот командлет сохраняет все доступные версии пакета.</span><span class="sxs-lookup"><span data-stu-id="691b2-145">Indicates that this cmdlet saves all available versions of the package.</span></span>

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

### <span data-ttu-id="691b2-146">-Command</span><span class="sxs-lookup"><span data-stu-id="691b2-146">-Command</span></span>

<span data-ttu-id="691b2-147">Указывает одну или несколько команд, входящих в пакет.</span><span class="sxs-lookup"><span data-stu-id="691b2-147">Specifies one or more commands included in the package.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="691b2-148">-ConfigFile</span><span class="sxs-lookup"><span data-stu-id="691b2-148">-ConfigFile</span></span>

<span data-ttu-id="691b2-149">Указывает файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="691b2-149">Specifies a configuration File.</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet:PackageByInputObject, NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="691b2-150">— Содержит</span><span class="sxs-lookup"><span data-stu-id="691b2-150">-Contains</span></span>

<span data-ttu-id="691b2-151">`Save-Package` Возвращает объекты, если любой элемент в значениях свойств объекта является точным соответствием для указанного значения.</span><span class="sxs-lookup"><span data-stu-id="691b2-151">`Save-Package` gets objects if any item in the object's property values are an exact match for the specified value.</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet:PackageByInputObject, NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="691b2-152">-Credential</span><span class="sxs-lookup"><span data-stu-id="691b2-152">-Credential</span></span>

<span data-ttu-id="691b2-153">Указывает учетную запись пользователя, имеющую разрешение на сохранение пакета из указанного поставщика пакетов или источника.</span><span class="sxs-lookup"><span data-stu-id="691b2-153">Specifies a user account that has permission to save a package from a specified package provider or source.</span></span>

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

### <span data-ttu-id="691b2-154">-DscResource</span><span class="sxs-lookup"><span data-stu-id="691b2-154">-DscResource</span></span>

<span data-ttu-id="691b2-155">Указывает один или несколько ресурсов DSC для пакета.</span><span class="sxs-lookup"><span data-stu-id="691b2-155">Specifies one or more Desired State Configuration (DSC) resources for the package.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="691b2-156">-Filter</span><span class="sxs-lookup"><span data-stu-id="691b2-156">-Filter</span></span>

<span data-ttu-id="691b2-157">Задает фильтр для пакета.</span><span class="sxs-lookup"><span data-stu-id="691b2-157">Specifies a filter for the package.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="691b2-158">-Филтеронтаг</span><span class="sxs-lookup"><span data-stu-id="691b2-158">-FilterOnTag</span></span>

<span data-ttu-id="691b2-159">Указывает тег, фильтрующий результаты.</span><span class="sxs-lookup"><span data-stu-id="691b2-159">Specifies the tag that filters the results.</span></span> <span data-ttu-id="691b2-160">Исключаются результаты, не содержащие указанный тег.</span><span class="sxs-lookup"><span data-stu-id="691b2-160">Results that don't contain the specified tag are excluded.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NuGet:PackageByInputObject, NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="691b2-161">-Force</span><span class="sxs-lookup"><span data-stu-id="691b2-161">-Force</span></span>

<span data-ttu-id="691b2-162">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="691b2-162">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="691b2-163">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="691b2-163">-ForceBootstrap</span></span>

<span data-ttu-id="691b2-164">Указывает, что `Save-Package` заставляет **PackageManagement** автоматически устанавливать поставщик пакетов для указанного пакета.</span><span class="sxs-lookup"><span data-stu-id="691b2-164">Indicates that `Save-Package` forces **PackageManagement** to automatically install the package provider for the specified package.</span></span>

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

### <span data-ttu-id="691b2-165">-Заголовки</span><span class="sxs-lookup"><span data-stu-id="691b2-165">-Headers</span></span>

<span data-ttu-id="691b2-166">Указывает заголовки для пакета.</span><span class="sxs-lookup"><span data-stu-id="691b2-166">Specifies the headers for the package.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NuGet:PackageByInputObject, NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="691b2-167">— Включает</span><span class="sxs-lookup"><span data-stu-id="691b2-167">-Includes</span></span>

<span data-ttu-id="691b2-168">Указывает ресурсы, которые включает пакет.</span><span class="sxs-lookup"><span data-stu-id="691b2-168">Indicates the resources that the package includes.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet
Aliases:
Accepted values: DscResource, Cmdlet, Function, Workflow, RoleCapability

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="691b2-169">-InputObject</span><span class="sxs-lookup"><span data-stu-id="691b2-169">-InputObject</span></span>

<span data-ttu-id="691b2-170">Объект идентификатора программного обеспечения, представляющий пакет, который необходимо сохранить.</span><span class="sxs-lookup"><span data-stu-id="691b2-170">A software ID object that represents the package that you want to save.</span></span> <span data-ttu-id="691b2-171">Идентификаторы программного обеспечения являются частью результатов `Find-Package` командлета.</span><span class="sxs-lookup"><span data-stu-id="691b2-171">Software IDs are part of the results of the `Find-Package` cmdlet.</span></span>

```yaml
Type: Microsoft.PackageManagement.Packaging.SoftwareIdentity
Parameter Sets: PackageByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="691b2-172">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="691b2-172">-LiteralPath</span></span>

<span data-ttu-id="691b2-173">Указывает литеральный путь, в который необходимо сохранить пакет.</span><span class="sxs-lookup"><span data-stu-id="691b2-173">Specifies the literal path to which you want to save the package.</span></span> <span data-ttu-id="691b2-174">Нельзя добавить оба параметра и параметр **path** в одну и ту же команду.</span><span class="sxs-lookup"><span data-stu-id="691b2-174">You cannot add both this parameter and the **Path** parameter to the same command.</span></span>

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

### <span data-ttu-id="691b2-175">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="691b2-175">-MaximumVersion</span></span>

<span data-ttu-id="691b2-176">Указывает максимальную версию пакета, который необходимо сохранить.</span><span class="sxs-lookup"><span data-stu-id="691b2-176">Specifies the maximum version of the package that you want to save.</span></span>

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

### <span data-ttu-id="691b2-177">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="691b2-177">-MinimumVersion</span></span>

<span data-ttu-id="691b2-178">Указывает минимальную версию пакета, которую необходимо найти.</span><span class="sxs-lookup"><span data-stu-id="691b2-178">Specifies the minimum version of the package that you want to find.</span></span>

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

### <span data-ttu-id="691b2-179">-Name</span><span class="sxs-lookup"><span data-stu-id="691b2-179">-Name</span></span>

<span data-ttu-id="691b2-180">Указывает одно или несколько имен пакетов.</span><span class="sxs-lookup"><span data-stu-id="691b2-180">Specifies one or more package names.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PackageBySearch
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="691b2-181">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="691b2-181">-PackageManagementProvider</span></span>

<span data-ttu-id="691b2-182">Указывает поставщика управления пакетами.</span><span class="sxs-lookup"><span data-stu-id="691b2-182">Specifies a package management provider.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="691b2-183">-Path</span><span class="sxs-lookup"><span data-stu-id="691b2-183">-Path</span></span>

<span data-ttu-id="691b2-184">Указывает расположение на локальном компьютере для хранения пакета.</span><span class="sxs-lookup"><span data-stu-id="691b2-184">Specifies the location on the local computer to store the package.</span></span>

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

### <span data-ttu-id="691b2-185">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="691b2-185">-ProviderName</span></span>

<span data-ttu-id="691b2-186">Указывает одно или несколько имен поставщиков.</span><span class="sxs-lookup"><span data-stu-id="691b2-186">Specifies one or more provider names.</span></span>

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

### <span data-ttu-id="691b2-187">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="691b2-187">-Proxy</span></span>

<span data-ttu-id="691b2-188">Указывает прокси-сервер для запроса, а не прямое подключение к Интернету.</span><span class="sxs-lookup"><span data-stu-id="691b2-188">Specifies a proxy server for the request, rather than a direct connection to the internet resource.</span></span>

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

### <span data-ttu-id="691b2-189">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="691b2-189">-ProxyCredential</span></span>

<span data-ttu-id="691b2-190">Указывает учетную запись пользователя, имеющую разрешение на использование прокси-сервера, который задается параметром **Proxy**.</span><span class="sxs-lookup"><span data-stu-id="691b2-190">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="691b2-191">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="691b2-191">-PublishLocation</span></span>

<span data-ttu-id="691b2-192">Указывает расположение публикации.</span><span class="sxs-lookup"><span data-stu-id="691b2-192">Specifies the publish location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="691b2-193">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="691b2-193">-RequiredVersion</span></span>

<span data-ttu-id="691b2-194">Указывает точную версию пакета для сохранения.</span><span class="sxs-lookup"><span data-stu-id="691b2-194">Specifies the exact version of the package to save.</span></span>

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

### <span data-ttu-id="691b2-195">-RoleCapability</span><span class="sxs-lookup"><span data-stu-id="691b2-195">-RoleCapability</span></span>

<span data-ttu-id="691b2-196">Указывает массив возможностей роли.</span><span class="sxs-lookup"><span data-stu-id="691b2-196">Specifies an array of role capabilities.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="691b2-197">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="691b2-197">-ScriptPublishLocation</span></span>

<span data-ttu-id="691b2-198">Указывает расположение публикации скрипта.</span><span class="sxs-lookup"><span data-stu-id="691b2-198">Specifies the script publish location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="691b2-199">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="691b2-199">-ScriptSourceLocation</span></span>

<span data-ttu-id="691b2-200">Указывает расположение источника скрипта.</span><span class="sxs-lookup"><span data-stu-id="691b2-200">Specifies the script source location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="691b2-201">-Скипвалидате</span><span class="sxs-lookup"><span data-stu-id="691b2-201">-SkipValidate</span></span>

<span data-ttu-id="691b2-202">Параметр, который пропускает проверку учетных данных пакета.</span><span class="sxs-lookup"><span data-stu-id="691b2-202">Switch that skips validating the credentials of a package.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet:PackageByInputObject, NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="691b2-203">-Source</span><span class="sxs-lookup"><span data-stu-id="691b2-203">-Source</span></span>

<span data-ttu-id="691b2-204">Указывает один или несколько источников пакетов.</span><span class="sxs-lookup"><span data-stu-id="691b2-204">Specifies one or more package sources.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PackageBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="691b2-205">-Tag</span><span class="sxs-lookup"><span data-stu-id="691b2-205">-Tag</span></span>

<span data-ttu-id="691b2-206">Указывает тег для поиска в метаданных пакета.</span><span class="sxs-lookup"><span data-stu-id="691b2-206">Specifies a tag to search for within the package metadata.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="691b2-207">-Type</span><span class="sxs-lookup"><span data-stu-id="691b2-207">-Type</span></span>

<span data-ttu-id="691b2-208">Указывает, следует ли выполнять поиск пакетов с помощью модуля, скрипта или либо.</span><span class="sxs-lookup"><span data-stu-id="691b2-208">Specifies whether to search for packages with a module, a script, or either.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageByInputObject, PowerShellGet
Aliases:
Accepted values: Module, Script, All

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="691b2-209">-Confirm</span><span class="sxs-lookup"><span data-stu-id="691b2-209">-Confirm</span></span>

<span data-ttu-id="691b2-210">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="691b2-210">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="691b2-211">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="691b2-211">-WhatIf</span></span>

<span data-ttu-id="691b2-212">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="691b2-212">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="691b2-213">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="691b2-213">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="691b2-214">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="691b2-214">CommonParameters</span></span>

<span data-ttu-id="691b2-215">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="691b2-215">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="691b2-216">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="691b2-216">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="691b2-217">Входные данные</span><span class="sxs-lookup"><span data-stu-id="691b2-217">INPUTS</span></span>

### <span data-ttu-id="691b2-218">`Save-Package` принимает объекты из конвейера.</span><span class="sxs-lookup"><span data-stu-id="691b2-218">`Save-Package` accepts objects from the pipeline.</span></span>

## <span data-ttu-id="691b2-219">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="691b2-219">OUTPUTS</span></span>

### <span data-ttu-id="691b2-220">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="691b2-220">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="691b2-221">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="691b2-221">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="691b2-222">Начиная с апреля 2020 года коллекция PowerShell не поддерживает протокол TLS (Transport Layer Security) версий 1.0 и 1.1.</span><span class="sxs-lookup"><span data-stu-id="691b2-222">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="691b2-223">Если вы не используете TLS 1.2 или более поздней версии, при попытке доступа к коллекции PowerShell возникнет ошибка.</span><span class="sxs-lookup"><span data-stu-id="691b2-223">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="691b2-224">Чтобы проверить, используется ли TLS 1.2, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="691b2-224">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="691b2-225">Дополнительные сведения см. в [объявлении](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) в блоге, посвященном PowerShell.</span><span class="sxs-lookup"><span data-stu-id="691b2-225">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="691b2-226">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="691b2-226">RELATED LINKS</span></span>

[<span data-ttu-id="691b2-227">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="691b2-227">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="691b2-228">Get-Package</span><span class="sxs-lookup"><span data-stu-id="691b2-228">Get-Package</span></span>](Get-Package.md)

[<span data-ttu-id="691b2-229">Install-Package</span><span class="sxs-lookup"><span data-stu-id="691b2-229">Install-Package</span></span>](Install-Package.md)

[<span data-ttu-id="691b2-230">Save-Package</span><span class="sxs-lookup"><span data-stu-id="691b2-230">Save-Package</span></span>](Save-Package.md)

[<span data-ttu-id="691b2-231">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="691b2-231">Uninstall-Package</span></span>](Uninstall-Package.md)
