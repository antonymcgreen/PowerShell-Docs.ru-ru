---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PackageManagement
ms.date: 04/03/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/save-package?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Save-Package
ms.openlocfilehash: c381de5b3c3d9aab701ed1ff9a78b3c9e0f65b3b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228553"
---
# <span data-ttu-id="47660-103">Save-Package</span><span class="sxs-lookup"><span data-stu-id="47660-103">Save-Package</span></span>

## <span data-ttu-id="47660-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="47660-104">SYNOPSIS</span></span>
<span data-ttu-id="47660-105">Сохраняет пакеты на локальном компьютере, не устанавливая их.</span><span class="sxs-lookup"><span data-stu-id="47660-105">Saves packages to the local computer without installing them.</span></span>

## <span data-ttu-id="47660-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="47660-106">SYNTAX</span></span>

### <span data-ttu-id="47660-107">паккажебисеарч</span><span class="sxs-lookup"><span data-stu-id="47660-107">PackageBySearch</span></span>

```
Save-Package [-Name] <String[]> [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-Source <String[]>] [-Path <String>] [-LiteralPath <String>]
 [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-AllVersions]
 [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-ProviderName <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="47660-108">паккажебинпутобжект</span><span class="sxs-lookup"><span data-stu-id="47660-108">PackageByInputObject</span></span>

```
Save-Package [-Path <String>] [-LiteralPath <String>] -InputObject <SoftwareIdentity>
 [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-AllVersions]
 [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="47660-109">NuGet: Паккажебинпутобжект</span><span class="sxs-lookup"><span data-stu-id="47660-109">NuGet:PackageByInputObject</span></span>

```
Save-Package [-Path <String>] [-LiteralPath <String>] [-Credential <PSCredential>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-ConfigFile <String>] [-SkipValidate] [-Headers <String[]>] [-FilterOnTag <String[]>]
 [-Contains <String>] [-AllowPrereleaseVersions] [<CommonParameters>]
```

### <span data-ttu-id="47660-110">NuGet</span><span class="sxs-lookup"><span data-stu-id="47660-110">NuGet</span></span>

```
Save-Package [-Path <String>] [-LiteralPath <String>] [-Credential <PSCredential>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-ConfigFile <String>] [-SkipValidate] [-Headers <String[]>] [-FilterOnTag <String[]>]
 [-Contains <String>] [-AllowPrereleaseVersions] [<CommonParameters>]
```

### <span data-ttu-id="47660-111">PowerShellGet: Паккажебинпутобжект</span><span class="sxs-lookup"><span data-stu-id="47660-111">PowerShellGet:PackageByInputObject</span></span>

```
Save-Package [-Path <String>] [-LiteralPath <String>] [-Credential <PSCredential>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-AllowPrereleaseVersions] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [-Type <String>]
 [-Filter <String>] [-Tag <String[]>] [-Includes <String[]>] [-DscResource <String[]>]
 [-RoleCapability <String[]>] [-Command <String[]>] [-AcceptLicense] [<CommonParameters>]
```

### <span data-ttu-id="47660-112">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="47660-112">PowerShellGet</span></span>

```
Save-Package [-Path <String>] [-LiteralPath <String>] [-Credential <PSCredential>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-AllowPrereleaseVersions] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [-Type <String>]
 [-Filter <String>] [-Tag <String[]>] [-Includes <String[]>] [-DscResource <String[]>]
 [-RoleCapability <String[]>] [-Command <String[]>] [-AcceptLicense] [<CommonParameters>]
```

## <span data-ttu-id="47660-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="47660-113">DESCRIPTION</span></span>

<span data-ttu-id="47660-114">`Save-Package`Командлет сохраняет пакеты на локальном компьютере, но не устанавливает пакеты.</span><span class="sxs-lookup"><span data-stu-id="47660-114">The `Save-Package` cmdlet saves packages to the local computer but doesn't install the packages.</span></span>
<span data-ttu-id="47660-115">Этот командлет сохраняет последнюю версию пакета, если не указано значение **рекуиредверион** .</span><span class="sxs-lookup"><span data-stu-id="47660-115">This cmdlet saves the newest version of a package unless you specify a **RequiredVerion** .</span></span> <span data-ttu-id="47660-116">Параметры **path** и **LiteralPath** являются взаимоисключающими и не могут быть добавлены к одной и той же команде.</span><span class="sxs-lookup"><span data-stu-id="47660-116">The **Path** and **LiteralPath** parameters are mutually exclusive, and cannot be added to the same command.</span></span>

## <span data-ttu-id="47660-117">Примеры</span><span class="sxs-lookup"><span data-stu-id="47660-117">EXAMPLES</span></span>

### <span data-ttu-id="47660-118">Пример 1. Сохранение пакета на локальном компьютере</span><span class="sxs-lookup"><span data-stu-id="47660-118">Example 1: Save a package to the local computer</span></span>

<span data-ttu-id="47660-119">В этом примере сохраняется последняя версия пакета в каталоге на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="47660-119">This example saves the newest version of the package to a directory on the local computer.</span></span> <span data-ttu-id="47660-120">Зависимости пакета загружаются вместе с пакетом.</span><span class="sxs-lookup"><span data-stu-id="47660-120">The package's dependencies are download with the package.</span></span>

```
PS> Save-Package -Name NuGet.Core -ProviderName NuGet -Path C:\LocalPkg
```

```Output
Name                    Version    Source    Summary
----                    -------    ------    -------
Microsoft.Web.Xdt       3.0.0      Nuget     Microsoft Xml Document Transformation (XDT) enables...
NuGet.Core              2.14.0     Nuget     NuGet.Core is the core framework assembly for NuGet...
```

<span data-ttu-id="47660-121">`Save-Package` использует параметр **Name** для указания пакета.</span><span class="sxs-lookup"><span data-stu-id="47660-121">`Save-Package` uses the **Name** parameter to specify the package.</span></span> <span data-ttu-id="47660-122">Пакет загружается из репозитория, указанного параметром **providerName** .</span><span class="sxs-lookup"><span data-stu-id="47660-122">The package is downloaded from the repository specified by the **ProviderName** parameter.</span></span> <span data-ttu-id="47660-123">Параметр **path** определяет место сохранения пакета.</span><span class="sxs-lookup"><span data-stu-id="47660-123">The **Path** parameter determines where the package is saved.</span></span>

### <span data-ttu-id="47660-124">Пример 2. сохранение определенной версии пакета</span><span class="sxs-lookup"><span data-stu-id="47660-124">Example 2: Save a specific package version</span></span>

<span data-ttu-id="47660-125">В этом примере указывается версия пакета и сохраняется в каталоге на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="47660-125">This example specifies the package version and saves it to a directory on the local computer.</span></span>

```
PS> Save-Package -Name NuGet.Core -RequiredVersion 2.9.0 -ProviderName NuGet -Path C:\LocalPkg
```

```Output
Name                    Version    Source    Summary
----                    -------    ------    -------
Microsoft.Web.Xdt       3.0.0      Nuget     Microsoft Xml Document Transformation (XDT) enables...
NuGet.Core              2.9.0      Nuget     NuGet.Core is the core framework assembly for NuGet...
```

<span data-ttu-id="47660-126">`Save-Package` использует параметр **Name** для указания пакета.</span><span class="sxs-lookup"><span data-stu-id="47660-126">`Save-Package` uses the **Name** parameter to specify the package.</span></span> <span data-ttu-id="47660-127">**RequiredVersion** обозначает конкретную версию пакета.</span><span class="sxs-lookup"><span data-stu-id="47660-127">**RequiredVersion** indicates a specific package version.</span></span> <span data-ttu-id="47660-128">Пакет загружается из репозитория, указанного параметром **providerName** .</span><span class="sxs-lookup"><span data-stu-id="47660-128">The package is downloaded from the repository specified by the **ProviderName** parameter.</span></span> <span data-ttu-id="47660-129">Параметр **path** определяет место сохранения пакета.</span><span class="sxs-lookup"><span data-stu-id="47660-129">The **Path** parameter determines where the package is saved.</span></span>

### <span data-ttu-id="47660-130">Пример 3. Использование Find-Package для сохранения пакета</span><span class="sxs-lookup"><span data-stu-id="47660-130">Example 3: Use Find-Package to save a package</span></span>

<span data-ttu-id="47660-131">Эта команда использует `Find-Package` для размещения последней версии пакета и отправляет объект в `Save-Package` .</span><span class="sxs-lookup"><span data-stu-id="47660-131">This command uses `Find-Package` to locate the newest version of the package and sends the object to `Save-Package`.</span></span>

```
PS> Find-Package -Name NuGet.Core -ProviderName NuGet | Save-Package -Path C:\LocalPkg
```

<span data-ttu-id="47660-132">`Find-Package` использует параметр **Name** для указания пакета.</span><span class="sxs-lookup"><span data-stu-id="47660-132">`Find-Package` uses the **Name** parameter to specify the package.</span></span> <span data-ttu-id="47660-133">Пакет загружается из репозитория, указанного параметром **providerName** .</span><span class="sxs-lookup"><span data-stu-id="47660-133">The package is downloaded from the repository specified by the **ProviderName** parameter.</span></span> <span data-ttu-id="47660-134">Объект отправляется по конвейеру в `Save-Package` .</span><span class="sxs-lookup"><span data-stu-id="47660-134">The object is sent down the pipeline to `Save-Package`.</span></span> <span data-ttu-id="47660-135">Параметр **path** определяет место сохранения пакета.</span><span class="sxs-lookup"><span data-stu-id="47660-135">The **Path** parameter determines where the package is saved.</span></span>

### <span data-ttu-id="47660-136">Пример 4. сохранение и установка пакета</span><span class="sxs-lookup"><span data-stu-id="47660-136">Example 4: Save and install the package</span></span>

<span data-ttu-id="47660-137">Последняя версия пакета и его зависимости загружаются и устанавливаются на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="47660-137">The newest version of the package and its dependencies are downloaded and installed on the local computer.</span></span>

```
PS> Save-Package -Name NuGet.Core -ProviderName NuGet -Path C:\LocalPkg
PS> Install-Package C:\LocalPkg\NuGet.Core.2.14.0.nupkg
```

<span data-ttu-id="47660-138">`Save-Package` загружает файл пакета и его зависимости на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="47660-138">`Save-Package` downloads the package file and its dependencies to the local computer.</span></span>
<span data-ttu-id="47660-139">`Install-Package` устанавливает пакет и зависимости из указанного каталога.</span><span class="sxs-lookup"><span data-stu-id="47660-139">`Install-Package` installs the package and dependencies from the specified directory.</span></span>

## <span data-ttu-id="47660-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="47660-140">PARAMETERS</span></span>

### <span data-ttu-id="47660-141">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="47660-141">-AcceptLicense</span></span>

<span data-ttu-id="47660-142">Автоматически принимать лицензионное соглашение во время установки, если оно требуется для пакета.</span><span class="sxs-lookup"><span data-stu-id="47660-142">Automatically accept the license agreement during installation if the package requires it.</span></span>

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

### <span data-ttu-id="47660-143">-Алловпререлеасеверсионс</span><span class="sxs-lookup"><span data-stu-id="47660-143">-AllowPrereleaseVersions</span></span>

<span data-ttu-id="47660-144">Разрешает сохранение пакетов, помеченных как предварительные.</span><span class="sxs-lookup"><span data-stu-id="47660-144">Allows packages marked as Prerelease to be saved.</span></span>

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

### <span data-ttu-id="47660-145">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="47660-145">-AllVersions</span></span>

<span data-ttu-id="47660-146">Указывает, что этот командлет сохраняет все доступные версии пакета.</span><span class="sxs-lookup"><span data-stu-id="47660-146">Indicates that this cmdlet saves all available versions of the package.</span></span>

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

### <span data-ttu-id="47660-147">-Command</span><span class="sxs-lookup"><span data-stu-id="47660-147">-Command</span></span>

<span data-ttu-id="47660-148">Указывает одну или несколько команд, входящих в пакет.</span><span class="sxs-lookup"><span data-stu-id="47660-148">Specifies one or more commands included in the package.</span></span>

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

### <span data-ttu-id="47660-149">-ConfigFile</span><span class="sxs-lookup"><span data-stu-id="47660-149">-ConfigFile</span></span>

<span data-ttu-id="47660-150">Указывает файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="47660-150">Specifies a configuration File.</span></span>

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

### <span data-ttu-id="47660-151">— Содержит</span><span class="sxs-lookup"><span data-stu-id="47660-151">-Contains</span></span>

<span data-ttu-id="47660-152">`Save-Package` Возвращает объекты, если любой элемент в значениях свойств объекта является точным соответствием для указанного значения.</span><span class="sxs-lookup"><span data-stu-id="47660-152">`Save-Package` gets objects if any item in the object's property values are an exact match for the specified value.</span></span>

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

### <span data-ttu-id="47660-153">-Credential</span><span class="sxs-lookup"><span data-stu-id="47660-153">-Credential</span></span>

<span data-ttu-id="47660-154">Указывает учетную запись пользователя, имеющую разрешение на сохранение пакета из указанного поставщика пакетов или источника.</span><span class="sxs-lookup"><span data-stu-id="47660-154">Specifies a user account that has permission to save a package from a specified package provider or source.</span></span>

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

### <span data-ttu-id="47660-155">-DscResource</span><span class="sxs-lookup"><span data-stu-id="47660-155">-DscResource</span></span>

<span data-ttu-id="47660-156">Указывает один или несколько ресурсов DSC для пакета.</span><span class="sxs-lookup"><span data-stu-id="47660-156">Specifies one or more Desired State Configuration (DSC) resources for the package.</span></span>

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

### <span data-ttu-id="47660-157">-Filter</span><span class="sxs-lookup"><span data-stu-id="47660-157">-Filter</span></span>

<span data-ttu-id="47660-158">Задает фильтр для пакета.</span><span class="sxs-lookup"><span data-stu-id="47660-158">Specifies a filter for the package.</span></span>

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

### <span data-ttu-id="47660-159">-Филтеронтаг</span><span class="sxs-lookup"><span data-stu-id="47660-159">-FilterOnTag</span></span>

<span data-ttu-id="47660-160">Указывает тег, фильтрующий результаты.</span><span class="sxs-lookup"><span data-stu-id="47660-160">Specifies the tag that filters the results.</span></span> <span data-ttu-id="47660-161">Исключаются результаты, не содержащие указанный тег.</span><span class="sxs-lookup"><span data-stu-id="47660-161">Results that don't contain the specified tag are excluded.</span></span>

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

### <span data-ttu-id="47660-162">-Force</span><span class="sxs-lookup"><span data-stu-id="47660-162">-Force</span></span>

<span data-ttu-id="47660-163">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="47660-163">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="47660-164">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="47660-164">-ForceBootstrap</span></span>

<span data-ttu-id="47660-165">Указывает, что `Save-Package` заставляет **PackageManagement** автоматически устанавливать поставщик пакетов для указанного пакета.</span><span class="sxs-lookup"><span data-stu-id="47660-165">Indicates that `Save-Package` forces **PackageManagement** to automatically install the package provider for the specified package.</span></span>

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

### <span data-ttu-id="47660-166">-Заголовки</span><span class="sxs-lookup"><span data-stu-id="47660-166">-Headers</span></span>

<span data-ttu-id="47660-167">Указывает заголовки для пакета.</span><span class="sxs-lookup"><span data-stu-id="47660-167">Specifies the headers for the package.</span></span>

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

### <span data-ttu-id="47660-168">— Включает</span><span class="sxs-lookup"><span data-stu-id="47660-168">-Includes</span></span>

<span data-ttu-id="47660-169">Указывает ресурсы, которые включает пакет.</span><span class="sxs-lookup"><span data-stu-id="47660-169">Indicates the resources that the package includes.</span></span>

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

### <span data-ttu-id="47660-170">-InputObject</span><span class="sxs-lookup"><span data-stu-id="47660-170">-InputObject</span></span>

<span data-ttu-id="47660-171">Объект идентификатора программного обеспечения, представляющий пакет, который необходимо сохранить.</span><span class="sxs-lookup"><span data-stu-id="47660-171">A software ID object that represents the package that you want to save.</span></span> <span data-ttu-id="47660-172">Идентификаторы программного обеспечения являются частью результатов `Find-Package` командлета.</span><span class="sxs-lookup"><span data-stu-id="47660-172">Software IDs are part of the results of the `Find-Package` cmdlet.</span></span>

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

### <span data-ttu-id="47660-173">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="47660-173">-LiteralPath</span></span>

<span data-ttu-id="47660-174">Указывает литеральный путь, в который необходимо сохранить пакет.</span><span class="sxs-lookup"><span data-stu-id="47660-174">Specifies the literal path to which you want to save the package.</span></span> <span data-ttu-id="47660-175">Нельзя добавить оба параметра и параметр **path** в одну и ту же команду.</span><span class="sxs-lookup"><span data-stu-id="47660-175">You cannot add both this parameter and the **Path** parameter to the same command.</span></span>

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

### <span data-ttu-id="47660-176">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="47660-176">-MaximumVersion</span></span>

<span data-ttu-id="47660-177">Указывает максимальную версию пакета, который необходимо сохранить.</span><span class="sxs-lookup"><span data-stu-id="47660-177">Specifies the maximum version of the package that you want to save.</span></span>

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

### <span data-ttu-id="47660-178">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="47660-178">-MinimumVersion</span></span>

<span data-ttu-id="47660-179">Указывает минимальную версию пакета, которую необходимо найти.</span><span class="sxs-lookup"><span data-stu-id="47660-179">Specifies the minimum version of the package that you want to find.</span></span>

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

### <span data-ttu-id="47660-180">-Name</span><span class="sxs-lookup"><span data-stu-id="47660-180">-Name</span></span>

<span data-ttu-id="47660-181">Указывает одно или несколько имен пакетов.</span><span class="sxs-lookup"><span data-stu-id="47660-181">Specifies one or more package names.</span></span>

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

### <span data-ttu-id="47660-182">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="47660-182">-PackageManagementProvider</span></span>

<span data-ttu-id="47660-183">Указывает поставщика управления пакетами.</span><span class="sxs-lookup"><span data-stu-id="47660-183">Specifies a package management provider.</span></span>

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

### <span data-ttu-id="47660-184">-Path</span><span class="sxs-lookup"><span data-stu-id="47660-184">-Path</span></span>

<span data-ttu-id="47660-185">Указывает расположение на локальном компьютере для хранения пакета.</span><span class="sxs-lookup"><span data-stu-id="47660-185">Specifies the location on the local computer to store the package.</span></span>

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

### <span data-ttu-id="47660-186">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="47660-186">-ProviderName</span></span>

<span data-ttu-id="47660-187">Указывает одно или несколько имен поставщиков.</span><span class="sxs-lookup"><span data-stu-id="47660-187">Specifies one or more provider names.</span></span>

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

### <span data-ttu-id="47660-188">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="47660-188">-Proxy</span></span>

<span data-ttu-id="47660-189">Указывает прокси-сервер для запроса, а не прямое подключение к Интернету.</span><span class="sxs-lookup"><span data-stu-id="47660-189">Specifies a proxy server for the request, rather than a direct connection to the internet resource.</span></span>

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

### <span data-ttu-id="47660-190">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="47660-190">-ProxyCredential</span></span>

<span data-ttu-id="47660-191">Указывает учетную запись пользователя, имеющую разрешение на использование прокси-сервера, который задается параметром **Proxy** .</span><span class="sxs-lookup"><span data-stu-id="47660-191">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="47660-192">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="47660-192">-PublishLocation</span></span>

<span data-ttu-id="47660-193">Указывает расположение публикации.</span><span class="sxs-lookup"><span data-stu-id="47660-193">Specifies the publish location.</span></span>

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

### <span data-ttu-id="47660-194">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="47660-194">-RequiredVersion</span></span>

<span data-ttu-id="47660-195">Указывает точную версию пакета для сохранения.</span><span class="sxs-lookup"><span data-stu-id="47660-195">Specifies the exact version of the package to save.</span></span>

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

### <span data-ttu-id="47660-196">-RoleCapability</span><span class="sxs-lookup"><span data-stu-id="47660-196">-RoleCapability</span></span>

<span data-ttu-id="47660-197">Указывает массив возможностей роли.</span><span class="sxs-lookup"><span data-stu-id="47660-197">Specifies an array of role capabilities.</span></span>

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

### <span data-ttu-id="47660-198">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="47660-198">-ScriptPublishLocation</span></span>

<span data-ttu-id="47660-199">Указывает расположение публикации скрипта.</span><span class="sxs-lookup"><span data-stu-id="47660-199">Specifies the script publish location.</span></span>

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

### <span data-ttu-id="47660-200">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="47660-200">-ScriptSourceLocation</span></span>

<span data-ttu-id="47660-201">Указывает расположение источника скрипта.</span><span class="sxs-lookup"><span data-stu-id="47660-201">Specifies the script source location.</span></span>

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

### <span data-ttu-id="47660-202">-Скипвалидате</span><span class="sxs-lookup"><span data-stu-id="47660-202">-SkipValidate</span></span>

<span data-ttu-id="47660-203">Параметр, который пропускает проверку учетных данных пакета.</span><span class="sxs-lookup"><span data-stu-id="47660-203">Switch that skips validating the credentials of a package.</span></span>

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

### <span data-ttu-id="47660-204">-Source</span><span class="sxs-lookup"><span data-stu-id="47660-204">-Source</span></span>

<span data-ttu-id="47660-205">Указывает один или несколько источников пакетов.</span><span class="sxs-lookup"><span data-stu-id="47660-205">Specifies one or more package sources.</span></span>

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

### <span data-ttu-id="47660-206">-Tag</span><span class="sxs-lookup"><span data-stu-id="47660-206">-Tag</span></span>

<span data-ttu-id="47660-207">Указывает тег для поиска в метаданных пакета.</span><span class="sxs-lookup"><span data-stu-id="47660-207">Specifies a tag to search for within the package metadata.</span></span>

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

### <span data-ttu-id="47660-208">-Type</span><span class="sxs-lookup"><span data-stu-id="47660-208">-Type</span></span>

<span data-ttu-id="47660-209">Указывает, следует ли выполнять поиск пакетов с помощью модуля, скрипта или либо.</span><span class="sxs-lookup"><span data-stu-id="47660-209">Specifies whether to search for packages with a module, a script, or either.</span></span>

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

### <span data-ttu-id="47660-210">-Confirm</span><span class="sxs-lookup"><span data-stu-id="47660-210">-Confirm</span></span>

<span data-ttu-id="47660-211">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="47660-211">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="47660-212">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="47660-212">-WhatIf</span></span>

<span data-ttu-id="47660-213">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="47660-213">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="47660-214">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="47660-214">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="47660-215">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="47660-215">CommonParameters</span></span>

<span data-ttu-id="47660-216">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="47660-216">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="47660-217">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="47660-217">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="47660-218">Входные данные</span><span class="sxs-lookup"><span data-stu-id="47660-218">INPUTS</span></span>

### <span data-ttu-id="47660-219">`Save-Package` принимает объекты из конвейера.</span><span class="sxs-lookup"><span data-stu-id="47660-219">`Save-Package` accepts objects from the pipeline.</span></span>

## <span data-ttu-id="47660-220">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="47660-220">OUTPUTS</span></span>

### <span data-ttu-id="47660-221">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="47660-221">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="47660-222">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="47660-222">NOTES</span></span>

## <span data-ttu-id="47660-223">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="47660-223">RELATED LINKS</span></span>

[<span data-ttu-id="47660-224">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="47660-224">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="47660-225">Get-Package</span><span class="sxs-lookup"><span data-stu-id="47660-225">Get-Package</span></span>](Get-Package.md)

[<span data-ttu-id="47660-226">Install-Package</span><span class="sxs-lookup"><span data-stu-id="47660-226">Install-Package</span></span>](Install-Package.md)

[<span data-ttu-id="47660-227">Save-Package</span><span class="sxs-lookup"><span data-stu-id="47660-227">Save-Package</span></span>](Save-Package.md)

[<span data-ttu-id="47660-228">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="47660-228">Uninstall-Package</span></span>](Uninstall-Package.md)
