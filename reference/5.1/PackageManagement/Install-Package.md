---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PackageManagement
ms.date: 05/23/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/install-package?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Install-Package
ms.openlocfilehash: 058ed7f90e63bd7ca7a29cf6c89864a30255662a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227310"
---
# <span data-ttu-id="aade7-103">Install-Package</span><span class="sxs-lookup"><span data-stu-id="aade7-103">Install-Package</span></span>

## <span data-ttu-id="aade7-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="aade7-104">SYNOPSIS</span></span>
<span data-ttu-id="aade7-105">Устанавливает один или несколько пакетов программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="aade7-105">Installs one or more software packages.</span></span>

## <span data-ttu-id="aade7-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="aade7-106">SYNTAX</span></span>

### <span data-ttu-id="aade7-107">Паккажебисеарч (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="aade7-107">PackageBySearch (Default)</span></span>

```
Install-Package [-Name] <String[]> [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-Source <String[]>] [-Credential <PSCredential>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-ProviderName <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="aade7-108">паккажебинпутобжект</span><span class="sxs-lookup"><span data-stu-id="aade7-108">PackageByInputObject</span></span>

```
Install-Package [-InputObject] <SoftwareIdentity[]> [-Credential <PSCredential>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="aade7-109">Программы: Паккажебисеарч</span><span class="sxs-lookup"><span data-stu-id="aade7-109">Programs:PackageBySearch</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-IncludeWindowsInstaller]
 [-IncludeSystemComponent] [<CommonParameters>]
```

### <span data-ttu-id="aade7-110">Программы: Паккажебинпутобжект</span><span class="sxs-lookup"><span data-stu-id="aade7-110">Programs:PackageByInputObject</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-IncludeWindowsInstaller]
 [-IncludeSystemComponent] [<CommonParameters>]
```

### <span data-ttu-id="aade7-111">MSI: Паккажебисеарч</span><span class="sxs-lookup"><span data-stu-id="aade7-111">msi:PackageBySearch</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-AdditionalArguments <String[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="aade7-112">MSI: Паккажебинпутобжект</span><span class="sxs-lookup"><span data-stu-id="aade7-112">msi:PackageByInputObject</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-AdditionalArguments <String[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="aade7-113">NuGet: Паккажебисеарч</span><span class="sxs-lookup"><span data-stu-id="aade7-113">NuGet:PackageBySearch</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-ConfigFile <String>]
 [-SkipValidate] [-Headers <String[]>] [-FilterOnTag <String[]>] [-Contains <String>]
 [-AllowPrereleaseVersions] [-Destination <String>] [-ExcludeVersion] [-Scope <String>]
 [-SkipDependencies] [<CommonParameters>]
```

### <span data-ttu-id="aade7-114">NuGet: Паккажебинпутобжект</span><span class="sxs-lookup"><span data-stu-id="aade7-114">NuGet:PackageByInputObject</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-ConfigFile <String>]
 [-SkipValidate] [-Headers <String[]>] [-FilterOnTag <String[]>] [-Contains <String>]
 [-AllowPrereleaseVersions] [-Destination <String>] [-ExcludeVersion] [-Scope <String>]
 [-SkipDependencies] [<CommonParameters>]
```

### <span data-ttu-id="aade7-115">PowerShellGet: Паккажебисеарч</span><span class="sxs-lookup"><span data-stu-id="aade7-115">PowerShellGet:PackageBySearch</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-AllowPrereleaseVersions]
 [-Scope <String>] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [-Type <String>]
 [-Filter <String>] [-Tag <String[]>] [-Includes <String[]>] [-DscResource <String[]>]
 [-RoleCapability <String[]>] [-Command <String[]>] [-AcceptLicense] [-AllowClobber]
 [-SkipPublisherCheck] [-InstallUpdate] [-NoPathUpdate] [<CommonParameters>]
```

### <span data-ttu-id="aade7-116">PowerShellGet: Паккажебинпутобжект</span><span class="sxs-lookup"><span data-stu-id="aade7-116">PowerShellGet:PackageByInputObject</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-AllowPrereleaseVersions]
 [-Scope <String>] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [-Type <String>]
 [-Filter <String>] [-Tag <String[]>] [-Includes <String[]>] [-DscResource <String[]>]
 [-RoleCapability <String[]>] [-Command <String[]>] [-AcceptLicense] [-AllowClobber]
 [-SkipPublisherCheck] [-InstallUpdate] [-NoPathUpdate] [<CommonParameters>]
```

## <span data-ttu-id="aade7-117">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="aade7-117">DESCRIPTION</span></span>

<span data-ttu-id="aade7-118">`Install-Package`Командлет устанавливает один или несколько пакетов программного обеспечения на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="aade7-118">The `Install-Package` cmdlet installs one or more software packages on the local computer.</span></span> <span data-ttu-id="aade7-119">При наличии нескольких источников программного обеспечения используйте `Get-PackageProvider` и `Get-PackageSource` для просмотра сведений о поставщиках.</span><span class="sxs-lookup"><span data-stu-id="aade7-119">If you have multiple software sources, use `Get-PackageProvider` and `Get-PackageSource` to display details about your providers.</span></span>

## <span data-ttu-id="aade7-120">Примеры</span><span class="sxs-lookup"><span data-stu-id="aade7-120">EXAMPLES</span></span>

### <span data-ttu-id="aade7-121">Пример 1. Установка пакета по имени пакета</span><span class="sxs-lookup"><span data-stu-id="aade7-121">Example 1: Install a package by package name</span></span>

<span data-ttu-id="aade7-122">`Install-Package`Командлет устанавливает пакет программного обеспечения и его зависимости.</span><span class="sxs-lookup"><span data-stu-id="aade7-122">The `Install-Package` cmdlet installs a software package and its dependencies.</span></span>

```
PS> Install-Package -Name NuGet.Core -Source MyNuGet -Credential Contoso\TestUser
```

<span data-ttu-id="aade7-123">`Install-Package` использует параметры для указания **имени** и **источника** пакетов.</span><span class="sxs-lookup"><span data-stu-id="aade7-123">`Install-Package` uses parameters to specify the packages **Name** and **Source**.</span></span> <span data-ttu-id="aade7-124">Параметр **Credential** использует учетную запись пользователя домена с разрешениями на установку пакетов.</span><span class="sxs-lookup"><span data-stu-id="aade7-124">The **Credential** parameter uses a domain user account with permissions to install packages.</span></span> <span data-ttu-id="aade7-125">Команда запрашивает пароль учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="aade7-125">The command prompts you for the user account password.</span></span>

### <span data-ttu-id="aade7-126">Пример 2. Использование Find-Package для установки пакета</span><span class="sxs-lookup"><span data-stu-id="aade7-126">Example 2: Use Find-Package to install a package</span></span>

<span data-ttu-id="aade7-127">В этом примере объект, возвращенный, `Find-Package` отправляется по конвейеру и устанавливается `Install-Package` .</span><span class="sxs-lookup"><span data-stu-id="aade7-127">In this example, the object returned by `Find-Package` is sent down the pipeline and installed by `Install-Package`.</span></span>

```
PS> Find-Package -Name NuGet.Core -Source MyNuGet | Install-Package
```

<span data-ttu-id="aade7-128">`Find-Package` использует параметры **Name** и **Source** для нахождение пакета.</span><span class="sxs-lookup"><span data-stu-id="aade7-128">`Find-Package` uses the **Name** and **Source** parameters to locate a package.</span></span> <span data-ttu-id="aade7-129">Объект отправляется по конвейеру и `Install-Package` устанавливает пакет на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="aade7-129">The object is sent down the pipeline and `Install-Package` installs the package on the local computer.</span></span>

### <span data-ttu-id="aade7-130">Пример 3. Установка пакетов путем указания диапазона версий</span><span class="sxs-lookup"><span data-stu-id="aade7-130">Example 3: Install packages by specifying a range of versions</span></span>

<span data-ttu-id="aade7-131">`Install-Package` использует параметры **MinimumVersion** и **MaximumVersion** для указания диапазона версий программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="aade7-131">`Install-Package` uses the **MinimumVersion** and **MaximumVersion** parameters to specify a range of software versions.</span></span>

```
PS> Install-Package -Name NuGet.Core -Source MyNuGet -MinimumVersion 2.8.0 -MaximumVersion 2.9.0
```

<span data-ttu-id="aade7-132">`Install-Package` использует параметры **Name** и **Source** для поиска пакета.</span><span class="sxs-lookup"><span data-stu-id="aade7-132">`Install-Package` uses the **Name** and **Source** parameters to find a package.</span></span> <span data-ttu-id="aade7-133">Параметры **MinimumVersion** и **MaximumVersion** задают диапазон версий программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="aade7-133">The **MinimumVersion** and **MaximumVersion** parameters specify a range of software versions.</span></span> <span data-ttu-id="aade7-134">Устанавливается самая высокая версия в диапазоне.</span><span class="sxs-lookup"><span data-stu-id="aade7-134">The highest version in the range is installed.</span></span>

## <span data-ttu-id="aade7-135">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="aade7-135">PARAMETERS</span></span>

### <span data-ttu-id="aade7-136">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="aade7-136">-AcceptLicense</span></span>

 <span data-ttu-id="aade7-137">**AcceptLicense** автоматически принимает лицензионное соглашение во время установки.</span><span class="sxs-lookup"><span data-stu-id="aade7-137">**AcceptLicense** automatically accepts the license agreement during installation.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aade7-138">-AllowClobber</span><span class="sxs-lookup"><span data-stu-id="aade7-138">-AllowClobber</span></span>

<span data-ttu-id="aade7-139">Переопределяет предупреждающие сообщения о конфликтах с существующими командами.</span><span class="sxs-lookup"><span data-stu-id="aade7-139">Overrides warning messages about conflicts with existing commands.</span></span> <span data-ttu-id="aade7-140">Перезаписывает существующие команды, имена которых совпадают с именами устанавливаемых команд.</span><span class="sxs-lookup"><span data-stu-id="aade7-140">Overwrites existing commands that have the same name as commands being installed.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aade7-141">-Алловпререлеасеверсионс</span><span class="sxs-lookup"><span data-stu-id="aade7-141">-AllowPrereleaseVersions</span></span>

<span data-ttu-id="aade7-142">Разрешает установку пакетов, помеченных как предварительные.</span><span class="sxs-lookup"><span data-stu-id="aade7-142">Allows the installation of packages marked as prerelease.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet:PackageBySearch, NuGet:PackageByInputObject, PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aade7-143">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="aade7-143">-AllVersions</span></span>

<span data-ttu-id="aade7-144">`Install-Package` устанавливает все доступные версии пакета.</span><span class="sxs-lookup"><span data-stu-id="aade7-144">`Install-Package` installs all available versions of the package.</span></span> <span data-ttu-id="aade7-145">По умолчанию установлена только последняя версия.</span><span class="sxs-lookup"><span data-stu-id="aade7-145">By default, only the newest version is installed.</span></span>

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

### <span data-ttu-id="aade7-146">-Command</span><span class="sxs-lookup"><span data-stu-id="aade7-146">-Command</span></span>

<span data-ttu-id="aade7-147">Указывает одну или несколько команд, выполняющих `Install-Package` Поиск.</span><span class="sxs-lookup"><span data-stu-id="aade7-147">Specifies one or more commands that `Install-Package` searches.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aade7-148">-ConfigFile</span><span class="sxs-lookup"><span data-stu-id="aade7-148">-ConfigFile</span></span>

<span data-ttu-id="aade7-149">Указывает путь, который содержит файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="aade7-149">Specifies a path that contains a configuration file.</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet:PackageBySearch, NuGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aade7-150">— Содержит</span><span class="sxs-lookup"><span data-stu-id="aade7-150">-Contains</span></span>

<span data-ttu-id="aade7-151">`Install-Package` Возвращает объекты, если параметр **содержит** указывает значение, совпадающее с любым из значений свойств объекта.</span><span class="sxs-lookup"><span data-stu-id="aade7-151">`Install-Package` gets objects if the **Contains** parameter specifies a value that matches any of the object's property values.</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet:PackageBySearch, NuGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aade7-152">-Credential</span><span class="sxs-lookup"><span data-stu-id="aade7-152">-Credential</span></span>

<span data-ttu-id="aade7-153">Указывает учетную запись пользователя, имеющую разрешение на доступ к компьютеру и выполнение команд.</span><span class="sxs-lookup"><span data-stu-id="aade7-153">Specifies a user account that has permission to access the computer and run commands.</span></span> <span data-ttu-id="aade7-154">Введите имя пользователя, например **User01** , **Domain01\User01** , или введите объект **PSCredential** , созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="aade7-154">Type a user name, such as **User01** , **Domain01\User01** , or enter a **PSCredential** object, generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="aade7-155">Если ввести имя пользователя, будет предложено ввести пароль.</span><span class="sxs-lookup"><span data-stu-id="aade7-155">If you type a user name, you're prompted for a password.</span></span>

<span data-ttu-id="aade7-156">Если параметр **Credential** не указан, `Install-Package` использует текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="aade7-156">When the **Credential** parameter isn't specified, `Install-Package` uses the current user.</span></span>

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

### <span data-ttu-id="aade7-157">-Destination</span><span class="sxs-lookup"><span data-stu-id="aade7-157">-Destination</span></span>

<span data-ttu-id="aade7-158">Задает путь к входному объекту.</span><span class="sxs-lookup"><span data-stu-id="aade7-158">Specifies a path to an input object.</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet:PackageBySearch, NuGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aade7-159">-DscResource</span><span class="sxs-lookup"><span data-stu-id="aade7-159">-DscResource</span></span>

<span data-ttu-id="aade7-160">Указывает один или несколько ресурсов DSC, поиск которых выполняется `Install-Package` .</span><span class="sxs-lookup"><span data-stu-id="aade7-160">Specifies one or more Desired State Configuration (DSC) resources that are searched by `Install-Package`.</span></span> <span data-ttu-id="aade7-161">Используйте `Find-DscResource` командлет для поиска ресурсов DSC.</span><span class="sxs-lookup"><span data-stu-id="aade7-161">Use the `Find-DscResource` cmdlet to find DSC resources.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aade7-162">-Ексклудеверсион</span><span class="sxs-lookup"><span data-stu-id="aade7-162">-ExcludeVersion</span></span>

<span data-ttu-id="aade7-163">Переключитесь, чтобы исключить номер версии из пути к папке.</span><span class="sxs-lookup"><span data-stu-id="aade7-163">Switch to exclude the version number in the folder path.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet:PackageBySearch, NuGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aade7-164">-Filter</span><span class="sxs-lookup"><span data-stu-id="aade7-164">-Filter</span></span>

<span data-ttu-id="aade7-165">Задает термины для поиска в свойствах **имя** и **Описание** .</span><span class="sxs-lookup"><span data-stu-id="aade7-165">Specifies terms to search for within the **Name** and **Description** properties.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aade7-166">-Филтеронтаг</span><span class="sxs-lookup"><span data-stu-id="aade7-166">-FilterOnTag</span></span>

<span data-ttu-id="aade7-167">Указывает тег, фильтрующий результаты и исключающий результаты, которые не содержат указанный тег.</span><span class="sxs-lookup"><span data-stu-id="aade7-167">Specifies a tag that filters results and excludes results that don't contain the specified tag.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NuGet:PackageBySearch, NuGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aade7-168">-Force</span><span class="sxs-lookup"><span data-stu-id="aade7-168">-Force</span></span>

<span data-ttu-id="aade7-169">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="aade7-169">Forces the command to run without asking for user confirmation.</span></span> <span data-ttu-id="aade7-170">Переопределяет ограничения, которые препятствуют `Install-Package` выполнению, за исключением безопасности.</span><span class="sxs-lookup"><span data-stu-id="aade7-170">Overrides restrictions that prevent `Install-Package` from succeeding, with the exception of security.</span></span>

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

### <span data-ttu-id="aade7-171">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="aade7-171">-ForceBootstrap</span></span>

<span data-ttu-id="aade7-172">Заставляет службу **PackageManagement** автоматически устанавливать поставщик пакетов для указанного пакета.</span><span class="sxs-lookup"><span data-stu-id="aade7-172">Forces **PackageManagement** to automatically install the package provider for the specified package.</span></span>

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

### <span data-ttu-id="aade7-173">-Заголовки</span><span class="sxs-lookup"><span data-stu-id="aade7-173">-Headers</span></span>

<span data-ttu-id="aade7-174">Указывает заголовки пакета.</span><span class="sxs-lookup"><span data-stu-id="aade7-174">Specifies the package headers.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NuGet:PackageBySearch, NuGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aade7-175">— Включает</span><span class="sxs-lookup"><span data-stu-id="aade7-175">-Includes</span></span>

<span data-ttu-id="aade7-176">Указывает `Install-Package` , следует ли найти все типы пакетов.</span><span class="sxs-lookup"><span data-stu-id="aade7-176">Specifies whether `Install-Package` should find all package types.</span></span> <span data-ttu-id="aade7-177">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="aade7-177">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="aade7-178">Командлет</span><span class="sxs-lookup"><span data-stu-id="aade7-178">Cmdlet</span></span>
- <span data-ttu-id="aade7-179">DscResource</span><span class="sxs-lookup"><span data-stu-id="aade7-179">DscResource</span></span>
- <span data-ttu-id="aade7-180">Компонент</span><span class="sxs-lookup"><span data-stu-id="aade7-180">Function</span></span>
- <span data-ttu-id="aade7-181">RoleCapability</span><span class="sxs-lookup"><span data-stu-id="aade7-181">RoleCapability</span></span>
- <span data-ttu-id="aade7-182">Рабочий процесс</span><span class="sxs-lookup"><span data-stu-id="aade7-182">Workflow</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:
Accepted values: Cmdlet, DscResource, Function, RoleCapability, Workflow

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aade7-183">-InputObject</span><span class="sxs-lookup"><span data-stu-id="aade7-183">-InputObject</span></span>

<span data-ttu-id="aade7-184">Принимает входные данные конвейера.</span><span class="sxs-lookup"><span data-stu-id="aade7-184">Accepts pipeline input.</span></span> <span data-ttu-id="aade7-185">Указывает пакет с помощью типа **софтвареидентити** пакета.</span><span class="sxs-lookup"><span data-stu-id="aade7-185">Specifies a package by using the package's **SoftwareIdentity** type.</span></span>
<span data-ttu-id="aade7-186">`Find-Package` выводит объект **софтвареидентити** .</span><span class="sxs-lookup"><span data-stu-id="aade7-186">`Find-Package` outputs a **SoftwareIdentity** object.</span></span>

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

### <span data-ttu-id="aade7-187">-Инсталлупдате</span><span class="sxs-lookup"><span data-stu-id="aade7-187">-InstallUpdate</span></span>

<span data-ttu-id="aade7-188">Указывает, что `Install-Package` устанавливает обновления.</span><span class="sxs-lookup"><span data-stu-id="aade7-188">Indicates that `Install-Package` installs updates.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aade7-189">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="aade7-189">-MaximumVersion</span></span>

<span data-ttu-id="aade7-190">Указывает максимально допустимую версию пакета, которую вы хотите установить.</span><span class="sxs-lookup"><span data-stu-id="aade7-190">Specifies the maximum allowed package version that you want to install.</span></span> <span data-ttu-id="aade7-191">Если этот параметр не указан, `Install-Package` устанавливает последнюю версию пакета.</span><span class="sxs-lookup"><span data-stu-id="aade7-191">If you don't specify this parameter, `Install-Package` installs the package's newest version.</span></span>

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

### <span data-ttu-id="aade7-192">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="aade7-192">-MinimumVersion</span></span>

<span data-ttu-id="aade7-193">Указывает минимальную допустимую версию пакета, которую вы хотите установить.</span><span class="sxs-lookup"><span data-stu-id="aade7-193">Specifies the minimum allowed package version that you want to install.</span></span> <span data-ttu-id="aade7-194">Если вы не добавите этот параметр, `Install-Package` устанавливает последнюю версию пакета, соответствующую любой версии, указанной параметром **MaximumVersion** .</span><span class="sxs-lookup"><span data-stu-id="aade7-194">If you don't add this parameter, `Install-Package` installs the package's newest version that satisfies any version specified by the **MaximumVersion** parameter.</span></span>

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

### <span data-ttu-id="aade7-195">-Name</span><span class="sxs-lookup"><span data-stu-id="aade7-195">-Name</span></span>

<span data-ttu-id="aade7-196">Указывает одно или несколько имен пакетов.</span><span class="sxs-lookup"><span data-stu-id="aade7-196">Specifies one or more package names.</span></span> <span data-ttu-id="aade7-197">Несколько имен пакетов должны быть разделены запятыми.</span><span class="sxs-lookup"><span data-stu-id="aade7-197">Multiple package names must be separated by commas.</span></span>

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

### <span data-ttu-id="aade7-198">-NoPathUpdate</span><span class="sxs-lookup"><span data-stu-id="aade7-198">-NoPathUpdate</span></span>

<span data-ttu-id="aade7-199">**NoPathUpdate** применяется только к `Install-Script` командлету.</span><span class="sxs-lookup"><span data-stu-id="aade7-199">**NoPathUpdate** only applies to the `Install-Script` cmdlet.</span></span> <span data-ttu-id="aade7-200">**NoPathUpdate** — это динамический параметр, добавленный поставщиком и не поддерживаемый `Install-Package` .</span><span class="sxs-lookup"><span data-stu-id="aade7-200">**NoPathUpdate** is a dynamic parameter added by the provider and isn't supported by `Install-Package`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aade7-201">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="aade7-201">-PackageManagementProvider</span></span>

<span data-ttu-id="aade7-202">Указывает имя поставщика **PackageManagement** .</span><span class="sxs-lookup"><span data-stu-id="aade7-202">Specifies the name of the **PackageManagement** provider.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aade7-203">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="aade7-203">-ProviderName</span></span>

<span data-ttu-id="aade7-204">Указывает одно или несколько имен поставщиков пакетов, к которым будет отделана область поиска пакета.</span><span class="sxs-lookup"><span data-stu-id="aade7-204">Specifies one or more package provider names to which to scope your package search.</span></span> <span data-ttu-id="aade7-205">Чтобы получить имена поставщиков пакетов, выполните командлет `Get-PackageProvider`.</span><span class="sxs-lookup"><span data-stu-id="aade7-205">You can get package provider names by running the `Get-PackageProvider` cmdlet.</span></span>

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

### <span data-ttu-id="aade7-206">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="aade7-206">-Proxy</span></span>

<span data-ttu-id="aade7-207">Указывает прокси-сервер для запроса, а не напрямуюе подключение к Интернет-ресурсу.</span><span class="sxs-lookup"><span data-stu-id="aade7-207">Specifies a proxy server for the request, rather than connecting directly to an internet resource.</span></span>

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

### <span data-ttu-id="aade7-208">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="aade7-208">-ProxyCredential</span></span>

<span data-ttu-id="aade7-209">Указывает учетную запись пользователя, имеющую разрешение на использование прокси-сервера, указанного параметром **прокси** .</span><span class="sxs-lookup"><span data-stu-id="aade7-209">Specifies a user account that has permission to use the proxy server specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="aade7-210">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="aade7-210">-PublishLocation</span></span>

<span data-ttu-id="aade7-211">Указывает путь к опубликованному расположению пакета.</span><span class="sxs-lookup"><span data-stu-id="aade7-211">Specifies the path to a package's published location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aade7-212">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="aade7-212">-RequiredVersion</span></span>

<span data-ttu-id="aade7-213">Указывает точную допустимую версию пакета, который требуется установить.</span><span class="sxs-lookup"><span data-stu-id="aade7-213">Specifies the exact allowed version of the package that you want to install.</span></span> <span data-ttu-id="aade7-214">Если вы не добавите этот параметр, `Install-Package` устанавливает последнюю версию пакета, соответствующую любой версии, указанной параметром **MaximumVersion** .</span><span class="sxs-lookup"><span data-stu-id="aade7-214">If you don't add this parameter, `Install-Package` installs the package's newest version that satisfies any version specified by the **MaximumVersion** parameter.</span></span>

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

### <span data-ttu-id="aade7-215">-RoleCapability</span><span class="sxs-lookup"><span data-stu-id="aade7-215">-RoleCapability</span></span>

<span data-ttu-id="aade7-216">Указывает массив возможностей роли.</span><span class="sxs-lookup"><span data-stu-id="aade7-216">Specifies an array of role capabilities.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aade7-217">-Scope</span><span class="sxs-lookup"><span data-stu-id="aade7-217">-Scope</span></span>

<span data-ttu-id="aade7-218">Задает область, для которой необходимо установить пакет.</span><span class="sxs-lookup"><span data-stu-id="aade7-218">Specifies the scope for which to install the package.</span></span> <span data-ttu-id="aade7-219">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="aade7-219">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="aade7-220">CurrentUser</span><span class="sxs-lookup"><span data-stu-id="aade7-220">CurrentUser</span></span>
- <span data-ttu-id="aade7-221">AllUsers</span><span class="sxs-lookup"><span data-stu-id="aade7-221">AllUsers</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet:PackageBySearch, NuGet:PackageByInputObject, PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:
Accepted values: CurrentUser, AllUsers

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aade7-222">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="aade7-222">-ScriptPublishLocation</span></span>

<span data-ttu-id="aade7-223">Указывает путь к опубликованному расположению скрипта.</span><span class="sxs-lookup"><span data-stu-id="aade7-223">Specifies the path to a script's published location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aade7-224">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="aade7-224">-ScriptSourceLocation</span></span>

<span data-ttu-id="aade7-225">Указывает расположение источника скрипта.</span><span class="sxs-lookup"><span data-stu-id="aade7-225">Specifies the script source location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aade7-226">-СкипдепенденЦиес</span><span class="sxs-lookup"><span data-stu-id="aade7-226">-SkipDependencies</span></span>

<span data-ttu-id="aade7-227">Пропускает установку зависимостей программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="aade7-227">Skips the installation of software dependencies.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet:PackageBySearch, NuGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aade7-228">-Скиппублишерчекк</span><span class="sxs-lookup"><span data-stu-id="aade7-228">-SkipPublisherCheck</span></span>

<span data-ttu-id="aade7-229">Позволяет получить версию пакета, более новую по сравнению с установленной версией.</span><span class="sxs-lookup"><span data-stu-id="aade7-229">Allows you to get a package version that is newer than your installed version.</span></span> <span data-ttu-id="aade7-230">Например, установленный пакет с цифровой подписью доверенного издателя, но новая версия не подписана цифровой подписью.</span><span class="sxs-lookup"><span data-stu-id="aade7-230">For example, an installed package that is digitally signed by a trusted publisher but a new version isn't digitally signed.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aade7-231">-Скипвалидате</span><span class="sxs-lookup"><span data-stu-id="aade7-231">-SkipValidate</span></span>

<span data-ttu-id="aade7-232">Параметр, который пропускает проверку учетных данных пакета.</span><span class="sxs-lookup"><span data-stu-id="aade7-232">Switch that skips validating the credentials of a package.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet:PackageBySearch, NuGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aade7-233">-Source</span><span class="sxs-lookup"><span data-stu-id="aade7-233">-Source</span></span>

<span data-ttu-id="aade7-234">Указывает один или несколько источников пакетов.</span><span class="sxs-lookup"><span data-stu-id="aade7-234">Specifies one or more package sources.</span></span> <span data-ttu-id="aade7-235">Несколько имен источников пакетов должны быть разделены запятыми.</span><span class="sxs-lookup"><span data-stu-id="aade7-235">Multiple package source names must be separated by commas.</span></span>
<span data-ttu-id="aade7-236">Вы можете получить имена источников пакетов, выполнив `Get-PackageSource` командлет.</span><span class="sxs-lookup"><span data-stu-id="aade7-236">You can get package source names by running the `Get-PackageSource` cmdlet.</span></span>

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

### <span data-ttu-id="aade7-237">-Tag</span><span class="sxs-lookup"><span data-stu-id="aade7-237">-Tag</span></span>

<span data-ttu-id="aade7-238">Указывает одну или несколько строк для поиска в метаданных пакета.</span><span class="sxs-lookup"><span data-stu-id="aade7-238">Specifies one or more strings to search for in the package metadata.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aade7-239">-Type</span><span class="sxs-lookup"><span data-stu-id="aade7-239">-Type</span></span>

<span data-ttu-id="aade7-240">Указывает, следует ли выполнять поиск пакетов с помощью модуля, скрипта или и того, и другого.</span><span class="sxs-lookup"><span data-stu-id="aade7-240">Specifies whether to search for packages with a module, a script, or both.</span></span> <span data-ttu-id="aade7-241">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="aade7-241">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="aade7-242">Модуль</span><span class="sxs-lookup"><span data-stu-id="aade7-242">Module</span></span>
- <span data-ttu-id="aade7-243">Скрипт</span><span class="sxs-lookup"><span data-stu-id="aade7-243">Script</span></span>
- <span data-ttu-id="aade7-244">Все</span><span class="sxs-lookup"><span data-stu-id="aade7-244">All</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:PackageBySearch, PowerShellGet:PackageByInputObject
Aliases:
Accepted values: Module, Script, All

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aade7-245">-Confirm</span><span class="sxs-lookup"><span data-stu-id="aade7-245">-Confirm</span></span>

<span data-ttu-id="aade7-246">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="aade7-246">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="aade7-247">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="aade7-247">-WhatIf</span></span>

<span data-ttu-id="aade7-248">Показывает, что произойдет при `Install-Package` запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="aade7-248">Shows what would happen if `Install-Package` cmdlet is run.</span></span> <span data-ttu-id="aade7-249">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="aade7-249">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="aade7-250">-Аддитионаларгументс</span><span class="sxs-lookup"><span data-stu-id="aade7-250">-AdditionalArguments</span></span>

<span data-ttu-id="aade7-251">Указывает один или несколько дополнительных аргументов для установки.</span><span class="sxs-lookup"><span data-stu-id="aade7-251">Specifies one or more additional arguments for installation.</span></span>

```yaml
Type: System.String[]
Parameter Sets: msi:PackageBySearch, msi:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aade7-252">-Инклудесистемкомпонент</span><span class="sxs-lookup"><span data-stu-id="aade7-252">-IncludeSystemComponent</span></span>

<span data-ttu-id="aade7-253">Указывает, что этот командлет включает в результаты все системные компоненты.</span><span class="sxs-lookup"><span data-stu-id="aade7-253">Indicates that this cmdlet includes system components in the results.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Programs:PackageBySearch, Programs:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aade7-254">-Инклудевиндовсинсталлер</span><span class="sxs-lookup"><span data-stu-id="aade7-254">-IncludeWindowsInstaller</span></span>

<span data-ttu-id="aade7-255">Указывает, что этот командлет включает в результаты установщик Windows.</span><span class="sxs-lookup"><span data-stu-id="aade7-255">Indicates that this cmdlet includes the Windows installer in the results.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Programs:PackageBySearch, Programs:PackageByInputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aade7-256">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="aade7-256">CommonParameters</span></span>

<span data-ttu-id="aade7-257">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="aade7-257">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="aade7-258">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="aade7-258">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="aade7-259">Входные данные</span><span class="sxs-lookup"><span data-stu-id="aade7-259">INPUTS</span></span>

### <span data-ttu-id="aade7-260">`Install-Package` принимает входные данные из конвейера.</span><span class="sxs-lookup"><span data-stu-id="aade7-260">`Install-Package` accepts input from the pipeline.</span></span>

## <span data-ttu-id="aade7-261">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="aade7-261">OUTPUTS</span></span>

### <span data-ttu-id="aade7-262">Софтвареидентити []</span><span class="sxs-lookup"><span data-stu-id="aade7-262">SoftwareIdentity[]</span></span>

## <span data-ttu-id="aade7-263">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="aade7-263">NOTES</span></span>

<span data-ttu-id="aade7-264">Включение поставщика пакетов в команду может сделать динамические параметры доступными для командлета.</span><span class="sxs-lookup"><span data-stu-id="aade7-264">Including a package provider in a command can make dynamic parameters available to a cmdlet.</span></span> <span data-ttu-id="aade7-265">Динамические параметры относятся к поставщику пакетов.</span><span class="sxs-lookup"><span data-stu-id="aade7-265">Dynamic parameters are specific to a package provider.</span></span> <span data-ttu-id="aade7-266">`Get-Help`Командлет перечисляет наборы параметров командлета и включает набор параметров поставщика.</span><span class="sxs-lookup"><span data-stu-id="aade7-266">The `Get-Help` cmdlet lists a cmdlet's parameter sets and includes the provider's parameter set.</span></span> <span data-ttu-id="aade7-267">Например, `Install-Package` имеет набор параметров **PowerShellGet** , включающий `-NoPathUpdate` , `AllowClobber` и `SkipPublisherCheck` .</span><span class="sxs-lookup"><span data-stu-id="aade7-267">For example, `Install-Package` has the **PowerShellGet** parameter set that includes `-NoPathUpdate`, `AllowClobber`, and `SkipPublisherCheck`.</span></span>

## <span data-ttu-id="aade7-268">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="aade7-268">RELATED LINKS</span></span>

[<span data-ttu-id="aade7-269">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="aade7-269">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="aade7-270">Find-DscResource</span><span class="sxs-lookup"><span data-stu-id="aade7-270">Find-DscResource</span></span>](../PowershellGet/Find-DscResource.md)

[<span data-ttu-id="aade7-271">Get-Help</span><span class="sxs-lookup"><span data-stu-id="aade7-271">Get-Help</span></span>](../Microsoft.PowerShell.Core/Get-Help.md)

[<span data-ttu-id="aade7-272">Get-Package</span><span class="sxs-lookup"><span data-stu-id="aade7-272">Get-Package</span></span>](Get-Package.md)

[<span data-ttu-id="aade7-273">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="aade7-273">Get-PackageProvider</span></span>](Get-PackageProvider.md)

[<span data-ttu-id="aade7-274">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="aade7-274">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="aade7-275">Find-Package</span><span class="sxs-lookup"><span data-stu-id="aade7-275">Find-Package</span></span>](Find-Package.md)

[<span data-ttu-id="aade7-276">Save-Package</span><span class="sxs-lookup"><span data-stu-id="aade7-276">Save-Package</span></span>](Save-Package.md)

[<span data-ttu-id="aade7-277">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="aade7-277">Uninstall-Package</span></span>](Uninstall-Package.md)