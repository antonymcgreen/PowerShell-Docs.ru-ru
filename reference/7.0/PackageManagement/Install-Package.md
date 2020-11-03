---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PackageManagement
ms.date: 05/23/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/install-package?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Install-Package
ms.openlocfilehash: 506775bf4ef58244a04cb13c1cab926d112111bf
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229309"
---
# <span data-ttu-id="22a0a-103">Install-Package</span><span class="sxs-lookup"><span data-stu-id="22a0a-103">Install-Package</span></span>

## <span data-ttu-id="22a0a-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="22a0a-104">SYNOPSIS</span></span>
<span data-ttu-id="22a0a-105">Устанавливает один или несколько пакетов программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="22a0a-105">Installs one or more software packages.</span></span>

## <span data-ttu-id="22a0a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="22a0a-106">SYNTAX</span></span>

### <span data-ttu-id="22a0a-107">Паккажебисеарч (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="22a0a-107">PackageBySearch (Default)</span></span>

```
Install-Package [-Name] <String[]> [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-Source <String[]>] [-Credential <PSCredential>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-ProviderName <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="22a0a-108">паккажебинпутобжект</span><span class="sxs-lookup"><span data-stu-id="22a0a-108">PackageByInputObject</span></span>

```
Install-Package [-InputObject] <SoftwareIdentity[]> [-Credential <PSCredential>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="22a0a-109">NuGet: Паккажебисеарч</span><span class="sxs-lookup"><span data-stu-id="22a0a-109">NuGet:PackageBySearch</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-ConfigFile <String>]
 [-SkipValidate] [-Headers <String[]>] [-FilterOnTag <String[]>] [-Contains <String>]
 [-AllowPrereleaseVersions] [-Destination <String>] [-ExcludeVersion] [-Scope <String>]
 [-SkipDependencies] [<CommonParameters>]
```

### <span data-ttu-id="22a0a-110">NuGet: Паккажебинпутобжект</span><span class="sxs-lookup"><span data-stu-id="22a0a-110">NuGet:PackageByInputObject</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-ConfigFile <String>]
 [-SkipValidate] [-Headers <String[]>] [-FilterOnTag <String[]>] [-Contains <String>]
 [-AllowPrereleaseVersions] [-Destination <String>] [-ExcludeVersion] [-Scope <String>]
 [-SkipDependencies] [<CommonParameters>]
```

### <span data-ttu-id="22a0a-111">PowerShellGet: Паккажебисеарч</span><span class="sxs-lookup"><span data-stu-id="22a0a-111">PowerShellGet:PackageBySearch</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-AllowPrereleaseVersions]
 [-Scope <String>] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [-Type <String>]
 [-Filter <String>] [-Tag <String[]>] [-Includes <String[]>] [-DscResource <String[]>]
 [-RoleCapability <String[]>] [-Command <String[]>] [-AcceptLicense] [-AllowClobber]
 [-SkipPublisherCheck] [-InstallUpdate] [-NoPathUpdate] [<CommonParameters>]
```

### <span data-ttu-id="22a0a-112">PowerShellGet: Паккажебинпутобжект</span><span class="sxs-lookup"><span data-stu-id="22a0a-112">PowerShellGet:PackageByInputObject</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-AllowPrereleaseVersions]
 [-Scope <String>] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [-Type <String>]
 [-Filter <String>] [-Tag <String[]>] [-Includes <String[]>] [-DscResource <String[]>]
 [-RoleCapability <String[]>] [-Command <String[]>] [-AcceptLicense] [-AllowClobber]
 [-SkipPublisherCheck] [-InstallUpdate] [-NoPathUpdate] [<CommonParameters>]
```

## <span data-ttu-id="22a0a-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="22a0a-113">DESCRIPTION</span></span>

<span data-ttu-id="22a0a-114">`Install-Package`Командлет устанавливает один или несколько пакетов программного обеспечения на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="22a0a-114">The `Install-Package` cmdlet installs one or more software packages on the local computer.</span></span> <span data-ttu-id="22a0a-115">При наличии нескольких источников программного обеспечения используйте `Get-PackageProvider` и `Get-PackageSource` для просмотра сведений о поставщиках.</span><span class="sxs-lookup"><span data-stu-id="22a0a-115">If you have multiple software sources, use `Get-PackageProvider` and `Get-PackageSource` to display details about your providers.</span></span>

## <span data-ttu-id="22a0a-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="22a0a-116">EXAMPLES</span></span>

### <span data-ttu-id="22a0a-117">Пример 1. Установка пакета по имени пакета</span><span class="sxs-lookup"><span data-stu-id="22a0a-117">Example 1: Install a package by package name</span></span>

<span data-ttu-id="22a0a-118">`Install-Package`Командлет устанавливает пакет программного обеспечения и его зависимости.</span><span class="sxs-lookup"><span data-stu-id="22a0a-118">The `Install-Package` cmdlet installs a software package and its dependencies.</span></span>

```
PS> Install-Package -Name NuGet.Core -Source MyNuGet -Credential Contoso\TestUser
```

<span data-ttu-id="22a0a-119">`Install-Package` использует параметры для указания **имени** и **источника** пакетов.</span><span class="sxs-lookup"><span data-stu-id="22a0a-119">`Install-Package` uses parameters to specify the packages **Name** and **Source**.</span></span> <span data-ttu-id="22a0a-120">Параметр **Credential** использует учетную запись пользователя домена с разрешениями на установку пакетов.</span><span class="sxs-lookup"><span data-stu-id="22a0a-120">The **Credential** parameter uses a domain user account with permissions to install packages.</span></span> <span data-ttu-id="22a0a-121">Команда запрашивает пароль учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="22a0a-121">The command prompts you for the user account password.</span></span>

### <span data-ttu-id="22a0a-122">Пример 2. Использование Find-Package для установки пакета</span><span class="sxs-lookup"><span data-stu-id="22a0a-122">Example 2: Use Find-Package to install a package</span></span>

<span data-ttu-id="22a0a-123">В этом примере объект, возвращенный, `Find-Package` отправляется по конвейеру и устанавливается `Install-Package` .</span><span class="sxs-lookup"><span data-stu-id="22a0a-123">In this example, the object returned by `Find-Package` is sent down the pipeline and installed by `Install-Package`.</span></span>

```
PS> Find-Package -Name NuGet.Core -Source MyNuGet | Install-Package
```

<span data-ttu-id="22a0a-124">`Find-Package` использует параметры **Name** и **Source** для нахождение пакета.</span><span class="sxs-lookup"><span data-stu-id="22a0a-124">`Find-Package` uses the **Name** and **Source** parameters to locate a package.</span></span> <span data-ttu-id="22a0a-125">Объект отправляется по конвейеру и `Install-Package` устанавливает пакет на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="22a0a-125">The object is sent down the pipeline and `Install-Package` installs the package on the local computer.</span></span>

### <span data-ttu-id="22a0a-126">Пример 3. Установка пакетов путем указания диапазона версий</span><span class="sxs-lookup"><span data-stu-id="22a0a-126">Example 3: Install packages by specifying a range of versions</span></span>

<span data-ttu-id="22a0a-127">`Install-Package` использует параметры **MinimumVersion** и **MaximumVersion** для указания диапазона версий программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="22a0a-127">`Install-Package` uses the **MinimumVersion** and **MaximumVersion** parameters to specify a range of software versions.</span></span>

```
PS> Install-Package -Name NuGet.Core -Source MyNuGet -MinimumVersion 2.8.0 -MaximumVersion 2.9.0
```

<span data-ttu-id="22a0a-128">`Install-Package` использует параметры **Name** и **Source** для поиска пакета.</span><span class="sxs-lookup"><span data-stu-id="22a0a-128">`Install-Package` uses the **Name** and **Source** parameters to find a package.</span></span> <span data-ttu-id="22a0a-129">Параметры **MinimumVersion** и **MaximumVersion** задают диапазон версий программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="22a0a-129">The **MinimumVersion** and **MaximumVersion** parameters specify a range of software versions.</span></span> <span data-ttu-id="22a0a-130">Устанавливается самая высокая версия в диапазоне.</span><span class="sxs-lookup"><span data-stu-id="22a0a-130">The highest version in the range is installed.</span></span>

## <span data-ttu-id="22a0a-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="22a0a-131">PARAMETERS</span></span>

### <span data-ttu-id="22a0a-132">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="22a0a-132">-AcceptLicense</span></span>

 <span data-ttu-id="22a0a-133">**AcceptLicense** автоматически принимает лицензионное соглашение во время установки.</span><span class="sxs-lookup"><span data-stu-id="22a0a-133">**AcceptLicense** automatically accepts the license agreement during installation.</span></span>

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

### <span data-ttu-id="22a0a-134">-AllowClobber</span><span class="sxs-lookup"><span data-stu-id="22a0a-134">-AllowClobber</span></span>

<span data-ttu-id="22a0a-135">Переопределяет предупреждающие сообщения о конфликтах с существующими командами.</span><span class="sxs-lookup"><span data-stu-id="22a0a-135">Overrides warning messages about conflicts with existing commands.</span></span> <span data-ttu-id="22a0a-136">Перезаписывает существующие команды, имена которых совпадают с именами устанавливаемых команд.</span><span class="sxs-lookup"><span data-stu-id="22a0a-136">Overwrites existing commands that have the same name as commands being installed.</span></span>

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

### <span data-ttu-id="22a0a-137">-Алловпререлеасеверсионс</span><span class="sxs-lookup"><span data-stu-id="22a0a-137">-AllowPrereleaseVersions</span></span>

<span data-ttu-id="22a0a-138">Разрешает установку пакетов, помеченных как предварительные.</span><span class="sxs-lookup"><span data-stu-id="22a0a-138">Allows the installation of packages marked as prerelease.</span></span>

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

### <span data-ttu-id="22a0a-139">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="22a0a-139">-AllVersions</span></span>

<span data-ttu-id="22a0a-140">`Install-Package` устанавливает все доступные версии пакета.</span><span class="sxs-lookup"><span data-stu-id="22a0a-140">`Install-Package` installs all available versions of the package.</span></span> <span data-ttu-id="22a0a-141">По умолчанию установлена только последняя версия.</span><span class="sxs-lookup"><span data-stu-id="22a0a-141">By default, only the newest version is installed.</span></span>

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

### <span data-ttu-id="22a0a-142">-Command</span><span class="sxs-lookup"><span data-stu-id="22a0a-142">-Command</span></span>

<span data-ttu-id="22a0a-143">Указывает одну или несколько команд, выполняющих `Install-Package` Поиск.</span><span class="sxs-lookup"><span data-stu-id="22a0a-143">Specifies one or more commands that `Install-Package` searches.</span></span>

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

### <span data-ttu-id="22a0a-144">-ConfigFile</span><span class="sxs-lookup"><span data-stu-id="22a0a-144">-ConfigFile</span></span>

<span data-ttu-id="22a0a-145">Указывает путь, который содержит файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="22a0a-145">Specifies a path that contains a configuration file.</span></span>

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

### <span data-ttu-id="22a0a-146">— Содержит</span><span class="sxs-lookup"><span data-stu-id="22a0a-146">-Contains</span></span>

<span data-ttu-id="22a0a-147">`Install-Package` Возвращает объекты, если параметр **содержит** указывает значение, совпадающее с любым из значений свойств объекта.</span><span class="sxs-lookup"><span data-stu-id="22a0a-147">`Install-Package` gets objects if the **Contains** parameter specifies a value that matches any of the object's property values.</span></span>

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

### <span data-ttu-id="22a0a-148">-Credential</span><span class="sxs-lookup"><span data-stu-id="22a0a-148">-Credential</span></span>

<span data-ttu-id="22a0a-149">Указывает учетную запись пользователя, имеющую разрешение на доступ к компьютеру и выполнение команд.</span><span class="sxs-lookup"><span data-stu-id="22a0a-149">Specifies a user account that has permission to access the computer and run commands.</span></span> <span data-ttu-id="22a0a-150">Введите имя пользователя, например **User01** , **Domain01\User01** , или введите объект **PSCredential** , созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="22a0a-150">Type a user name, such as **User01** , **Domain01\User01** , or enter a **PSCredential** object, generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="22a0a-151">Если ввести имя пользователя, будет предложено ввести пароль.</span><span class="sxs-lookup"><span data-stu-id="22a0a-151">If you type a user name, you're prompted for a password.</span></span>

<span data-ttu-id="22a0a-152">Если параметр **Credential** не указан, `Install-Package` использует текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="22a0a-152">When the **Credential** parameter isn't specified, `Install-Package` uses the current user.</span></span>

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

### <span data-ttu-id="22a0a-153">-Destination</span><span class="sxs-lookup"><span data-stu-id="22a0a-153">-Destination</span></span>

<span data-ttu-id="22a0a-154">Задает путь к входному объекту.</span><span class="sxs-lookup"><span data-stu-id="22a0a-154">Specifies a path to an input object.</span></span>

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

### <span data-ttu-id="22a0a-155">-DscResource</span><span class="sxs-lookup"><span data-stu-id="22a0a-155">-DscResource</span></span>

<span data-ttu-id="22a0a-156">Указывает один или несколько ресурсов DSC, поиск которых выполняется `Install-Package` .</span><span class="sxs-lookup"><span data-stu-id="22a0a-156">Specifies one or more Desired State Configuration (DSC) resources that are searched by `Install-Package`.</span></span> <span data-ttu-id="22a0a-157">Используйте `Find-DscResource` командлет для поиска ресурсов DSC.</span><span class="sxs-lookup"><span data-stu-id="22a0a-157">Use the `Find-DscResource` cmdlet to find DSC resources.</span></span>

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

### <span data-ttu-id="22a0a-158">-Ексклудеверсион</span><span class="sxs-lookup"><span data-stu-id="22a0a-158">-ExcludeVersion</span></span>

<span data-ttu-id="22a0a-159">Переключитесь, чтобы исключить номер версии из пути к папке.</span><span class="sxs-lookup"><span data-stu-id="22a0a-159">Switch to exclude the version number in the folder path.</span></span>

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

### <span data-ttu-id="22a0a-160">-Filter</span><span class="sxs-lookup"><span data-stu-id="22a0a-160">-Filter</span></span>

<span data-ttu-id="22a0a-161">Задает термины для поиска в свойствах **имя** и **Описание** .</span><span class="sxs-lookup"><span data-stu-id="22a0a-161">Specifies terms to search for within the **Name** and **Description** properties.</span></span>

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

### <span data-ttu-id="22a0a-162">-Филтеронтаг</span><span class="sxs-lookup"><span data-stu-id="22a0a-162">-FilterOnTag</span></span>

<span data-ttu-id="22a0a-163">Указывает тег, фильтрующий результаты и исключающий результаты, которые не содержат указанный тег.</span><span class="sxs-lookup"><span data-stu-id="22a0a-163">Specifies a tag that filters results and excludes results that don't contain the specified tag.</span></span>

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

### <span data-ttu-id="22a0a-164">-Force</span><span class="sxs-lookup"><span data-stu-id="22a0a-164">-Force</span></span>

<span data-ttu-id="22a0a-165">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="22a0a-165">Forces the command to run without asking for user confirmation.</span></span> <span data-ttu-id="22a0a-166">Переопределяет ограничения, которые препятствуют `Install-Package` выполнению, за исключением безопасности.</span><span class="sxs-lookup"><span data-stu-id="22a0a-166">Overrides restrictions that prevent `Install-Package` from succeeding, with the exception of security.</span></span>

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

### <span data-ttu-id="22a0a-167">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="22a0a-167">-ForceBootstrap</span></span>

<span data-ttu-id="22a0a-168">Заставляет службу **PackageManagement** автоматически устанавливать поставщик пакетов для указанного пакета.</span><span class="sxs-lookup"><span data-stu-id="22a0a-168">Forces **PackageManagement** to automatically install the package provider for the specified package.</span></span>

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

### <span data-ttu-id="22a0a-169">-Заголовки</span><span class="sxs-lookup"><span data-stu-id="22a0a-169">-Headers</span></span>

<span data-ttu-id="22a0a-170">Указывает заголовки пакета.</span><span class="sxs-lookup"><span data-stu-id="22a0a-170">Specifies the package headers.</span></span>

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

### <span data-ttu-id="22a0a-171">— Включает</span><span class="sxs-lookup"><span data-stu-id="22a0a-171">-Includes</span></span>

<span data-ttu-id="22a0a-172">Указывает `Install-Package` , следует ли найти все типы пакетов.</span><span class="sxs-lookup"><span data-stu-id="22a0a-172">Specifies whether `Install-Package` should find all package types.</span></span> <span data-ttu-id="22a0a-173">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="22a0a-173">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="22a0a-174">Командлет</span><span class="sxs-lookup"><span data-stu-id="22a0a-174">Cmdlet</span></span>
- <span data-ttu-id="22a0a-175">DscResource</span><span class="sxs-lookup"><span data-stu-id="22a0a-175">DscResource</span></span>
- <span data-ttu-id="22a0a-176">Компонент</span><span class="sxs-lookup"><span data-stu-id="22a0a-176">Function</span></span>
- <span data-ttu-id="22a0a-177">RoleCapability</span><span class="sxs-lookup"><span data-stu-id="22a0a-177">RoleCapability</span></span>
- <span data-ttu-id="22a0a-178">Рабочий процесс</span><span class="sxs-lookup"><span data-stu-id="22a0a-178">Workflow</span></span>

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

### <span data-ttu-id="22a0a-179">-InputObject</span><span class="sxs-lookup"><span data-stu-id="22a0a-179">-InputObject</span></span>

<span data-ttu-id="22a0a-180">Принимает входные данные конвейера.</span><span class="sxs-lookup"><span data-stu-id="22a0a-180">Accepts pipeline input.</span></span> <span data-ttu-id="22a0a-181">Указывает пакет с помощью типа **софтвареидентити** пакета.</span><span class="sxs-lookup"><span data-stu-id="22a0a-181">Specifies a package by using the package's **SoftwareIdentity** type.</span></span>
<span data-ttu-id="22a0a-182">`Find-Package` выводит объект **софтвареидентити** .</span><span class="sxs-lookup"><span data-stu-id="22a0a-182">`Find-Package` outputs a **SoftwareIdentity** object.</span></span>

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

### <span data-ttu-id="22a0a-183">-Инсталлупдате</span><span class="sxs-lookup"><span data-stu-id="22a0a-183">-InstallUpdate</span></span>

<span data-ttu-id="22a0a-184">Указывает, что `Install-Package` устанавливает обновления.</span><span class="sxs-lookup"><span data-stu-id="22a0a-184">Indicates that `Install-Package` installs updates.</span></span>

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

### <span data-ttu-id="22a0a-185">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="22a0a-185">-MaximumVersion</span></span>

<span data-ttu-id="22a0a-186">Указывает максимально допустимую версию пакета, которую вы хотите установить.</span><span class="sxs-lookup"><span data-stu-id="22a0a-186">Specifies the maximum allowed package version that you want to install.</span></span> <span data-ttu-id="22a0a-187">Если этот параметр не указан, `Install-Package` устанавливает последнюю версию пакета.</span><span class="sxs-lookup"><span data-stu-id="22a0a-187">If you don't specify this parameter, `Install-Package` installs the package's newest version.</span></span>

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

### <span data-ttu-id="22a0a-188">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="22a0a-188">-MinimumVersion</span></span>

<span data-ttu-id="22a0a-189">Указывает минимальную допустимую версию пакета, которую вы хотите установить.</span><span class="sxs-lookup"><span data-stu-id="22a0a-189">Specifies the minimum allowed package version that you want to install.</span></span> <span data-ttu-id="22a0a-190">Если вы не добавите этот параметр, `Install-Package` устанавливает последнюю версию пакета, соответствующую любой версии, указанной параметром **MaximumVersion** .</span><span class="sxs-lookup"><span data-stu-id="22a0a-190">If you don't add this parameter, `Install-Package` installs the package's newest version that satisfies any version specified by the **MaximumVersion** parameter.</span></span>

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

### <span data-ttu-id="22a0a-191">-Name</span><span class="sxs-lookup"><span data-stu-id="22a0a-191">-Name</span></span>

<span data-ttu-id="22a0a-192">Указывает одно или несколько имен пакетов.</span><span class="sxs-lookup"><span data-stu-id="22a0a-192">Specifies one or more package names.</span></span> <span data-ttu-id="22a0a-193">Несколько имен пакетов должны быть разделены запятыми.</span><span class="sxs-lookup"><span data-stu-id="22a0a-193">Multiple package names must be separated by commas.</span></span>

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

### <span data-ttu-id="22a0a-194">-NoPathUpdate</span><span class="sxs-lookup"><span data-stu-id="22a0a-194">-NoPathUpdate</span></span>

<span data-ttu-id="22a0a-195">**NoPathUpdate** применяется только к `Install-Script` командлету.</span><span class="sxs-lookup"><span data-stu-id="22a0a-195">**NoPathUpdate** only applies to the `Install-Script` cmdlet.</span></span> <span data-ttu-id="22a0a-196">**NoPathUpdate** — это динамический параметр, добавленный поставщиком и не поддерживаемый `Install-Package` .</span><span class="sxs-lookup"><span data-stu-id="22a0a-196">**NoPathUpdate** is a dynamic parameter added by the provider and isn't supported by `Install-Package`.</span></span>

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

### <span data-ttu-id="22a0a-197">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="22a0a-197">-PackageManagementProvider</span></span>

<span data-ttu-id="22a0a-198">Указывает имя поставщика **PackageManagement** .</span><span class="sxs-lookup"><span data-stu-id="22a0a-198">Specifies the name of the **PackageManagement** provider.</span></span>

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

### <span data-ttu-id="22a0a-199">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="22a0a-199">-ProviderName</span></span>

<span data-ttu-id="22a0a-200">Указывает одно или несколько имен поставщиков пакетов, к которым будет отделана область поиска пакета.</span><span class="sxs-lookup"><span data-stu-id="22a0a-200">Specifies one or more package provider names to which to scope your package search.</span></span> <span data-ttu-id="22a0a-201">Чтобы получить имена поставщиков пакетов, выполните командлет `Get-PackageProvider`.</span><span class="sxs-lookup"><span data-stu-id="22a0a-201">You can get package provider names by running the `Get-PackageProvider` cmdlet.</span></span>

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

### <span data-ttu-id="22a0a-202">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="22a0a-202">-Proxy</span></span>

<span data-ttu-id="22a0a-203">Указывает прокси-сервер для запроса, а не напрямуюе подключение к Интернет-ресурсу.</span><span class="sxs-lookup"><span data-stu-id="22a0a-203">Specifies a proxy server for the request, rather than connecting directly to an internet resource.</span></span>

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

### <span data-ttu-id="22a0a-204">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="22a0a-204">-ProxyCredential</span></span>

<span data-ttu-id="22a0a-205">Указывает учетную запись пользователя, имеющую разрешение на использование прокси-сервера, указанного параметром **прокси** .</span><span class="sxs-lookup"><span data-stu-id="22a0a-205">Specifies a user account that has permission to use the proxy server specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="22a0a-206">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="22a0a-206">-PublishLocation</span></span>

<span data-ttu-id="22a0a-207">Указывает путь к опубликованному расположению пакета.</span><span class="sxs-lookup"><span data-stu-id="22a0a-207">Specifies the path to a package's published location.</span></span>

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

### <span data-ttu-id="22a0a-208">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="22a0a-208">-RequiredVersion</span></span>

<span data-ttu-id="22a0a-209">Указывает точную допустимую версию пакета, который требуется установить.</span><span class="sxs-lookup"><span data-stu-id="22a0a-209">Specifies the exact allowed version of the package that you want to install.</span></span> <span data-ttu-id="22a0a-210">Если вы не добавите этот параметр, `Install-Package` устанавливает последнюю версию пакета, соответствующую любой версии, указанной параметром **MaximumVersion** .</span><span class="sxs-lookup"><span data-stu-id="22a0a-210">If you don't add this parameter, `Install-Package` installs the package's newest version that satisfies any version specified by the **MaximumVersion** parameter.</span></span>

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

### <span data-ttu-id="22a0a-211">-RoleCapability</span><span class="sxs-lookup"><span data-stu-id="22a0a-211">-RoleCapability</span></span>

<span data-ttu-id="22a0a-212">Указывает массив возможностей роли.</span><span class="sxs-lookup"><span data-stu-id="22a0a-212">Specifies an array of role capabilities.</span></span>

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

### <span data-ttu-id="22a0a-213">-Scope</span><span class="sxs-lookup"><span data-stu-id="22a0a-213">-Scope</span></span>

<span data-ttu-id="22a0a-214">Задает область, для которой необходимо установить пакет.</span><span class="sxs-lookup"><span data-stu-id="22a0a-214">Specifies the scope for which to install the package.</span></span> <span data-ttu-id="22a0a-215">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="22a0a-215">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="22a0a-216">CurrentUser</span><span class="sxs-lookup"><span data-stu-id="22a0a-216">CurrentUser</span></span>
- <span data-ttu-id="22a0a-217">AllUsers</span><span class="sxs-lookup"><span data-stu-id="22a0a-217">AllUsers</span></span>

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

### <span data-ttu-id="22a0a-218">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="22a0a-218">-ScriptPublishLocation</span></span>

<span data-ttu-id="22a0a-219">Указывает путь к опубликованному расположению скрипта.</span><span class="sxs-lookup"><span data-stu-id="22a0a-219">Specifies the path to a script's published location.</span></span>

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

### <span data-ttu-id="22a0a-220">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="22a0a-220">-ScriptSourceLocation</span></span>

<span data-ttu-id="22a0a-221">Указывает расположение источника скрипта.</span><span class="sxs-lookup"><span data-stu-id="22a0a-221">Specifies the script source location.</span></span>

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

### <span data-ttu-id="22a0a-222">-СкипдепенденЦиес</span><span class="sxs-lookup"><span data-stu-id="22a0a-222">-SkipDependencies</span></span>

<span data-ttu-id="22a0a-223">Пропускает установку зависимостей программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="22a0a-223">Skips the installation of software dependencies.</span></span>

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

### <span data-ttu-id="22a0a-224">-Скиппублишерчекк</span><span class="sxs-lookup"><span data-stu-id="22a0a-224">-SkipPublisherCheck</span></span>

<span data-ttu-id="22a0a-225">Позволяет получить версию пакета, более новую по сравнению с установленной версией.</span><span class="sxs-lookup"><span data-stu-id="22a0a-225">Allows you to get a package version that is newer than your installed version.</span></span> <span data-ttu-id="22a0a-226">Например, установленный пакет с цифровой подписью доверенного издателя, но новая версия не подписана цифровой подписью.</span><span class="sxs-lookup"><span data-stu-id="22a0a-226">For example, an installed package that is digitally signed by a trusted publisher but a new version isn't digitally signed.</span></span>

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

### <span data-ttu-id="22a0a-227">-Скипвалидате</span><span class="sxs-lookup"><span data-stu-id="22a0a-227">-SkipValidate</span></span>

<span data-ttu-id="22a0a-228">Параметр, который пропускает проверку учетных данных пакета.</span><span class="sxs-lookup"><span data-stu-id="22a0a-228">Switch that skips validating the credentials of a package.</span></span>

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

### <span data-ttu-id="22a0a-229">-Source</span><span class="sxs-lookup"><span data-stu-id="22a0a-229">-Source</span></span>

<span data-ttu-id="22a0a-230">Указывает один или несколько источников пакетов.</span><span class="sxs-lookup"><span data-stu-id="22a0a-230">Specifies one or more package sources.</span></span> <span data-ttu-id="22a0a-231">Несколько имен источников пакетов должны быть разделены запятыми.</span><span class="sxs-lookup"><span data-stu-id="22a0a-231">Multiple package source names must be separated by commas.</span></span>
<span data-ttu-id="22a0a-232">Вы можете получить имена источников пакетов, выполнив `Get-PackageSource` командлет.</span><span class="sxs-lookup"><span data-stu-id="22a0a-232">You can get package source names by running the `Get-PackageSource` cmdlet.</span></span>

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

### <span data-ttu-id="22a0a-233">-Tag</span><span class="sxs-lookup"><span data-stu-id="22a0a-233">-Tag</span></span>

<span data-ttu-id="22a0a-234">Указывает одну или несколько строк для поиска в метаданных пакета.</span><span class="sxs-lookup"><span data-stu-id="22a0a-234">Specifies one or more strings to search for in the package metadata.</span></span>

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

### <span data-ttu-id="22a0a-235">-Type</span><span class="sxs-lookup"><span data-stu-id="22a0a-235">-Type</span></span>

<span data-ttu-id="22a0a-236">Указывает, следует ли выполнять поиск пакетов с помощью модуля, скрипта или и того, и другого.</span><span class="sxs-lookup"><span data-stu-id="22a0a-236">Specifies whether to search for packages with a module, a script, or both.</span></span> <span data-ttu-id="22a0a-237">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="22a0a-237">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="22a0a-238">Модуль</span><span class="sxs-lookup"><span data-stu-id="22a0a-238">Module</span></span>
- <span data-ttu-id="22a0a-239">Скрипт</span><span class="sxs-lookup"><span data-stu-id="22a0a-239">Script</span></span>
- <span data-ttu-id="22a0a-240">Все</span><span class="sxs-lookup"><span data-stu-id="22a0a-240">All</span></span>

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

### <span data-ttu-id="22a0a-241">-Confirm</span><span class="sxs-lookup"><span data-stu-id="22a0a-241">-Confirm</span></span>

<span data-ttu-id="22a0a-242">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="22a0a-242">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="22a0a-243">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="22a0a-243">-WhatIf</span></span>

<span data-ttu-id="22a0a-244">Показывает, что произойдет при `Install-Package` запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="22a0a-244">Shows what would happen if `Install-Package` cmdlet is run.</span></span> <span data-ttu-id="22a0a-245">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="22a0a-245">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="22a0a-246">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="22a0a-246">CommonParameters</span></span>

<span data-ttu-id="22a0a-247">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="22a0a-247">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="22a0a-248">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="22a0a-248">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="22a0a-249">Входные данные</span><span class="sxs-lookup"><span data-stu-id="22a0a-249">INPUTS</span></span>

### <span data-ttu-id="22a0a-250">`Install-Package` принимает входные данные из конвейера.</span><span class="sxs-lookup"><span data-stu-id="22a0a-250">`Install-Package` accepts input from the pipeline.</span></span>

## <span data-ttu-id="22a0a-251">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="22a0a-251">OUTPUTS</span></span>

### <span data-ttu-id="22a0a-252">Софтвареидентити []</span><span class="sxs-lookup"><span data-stu-id="22a0a-252">SoftwareIdentity[]</span></span>

## <span data-ttu-id="22a0a-253">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="22a0a-253">NOTES</span></span>

<span data-ttu-id="22a0a-254">Включение поставщика пакетов в команду может сделать динамические параметры доступными для командлета.</span><span class="sxs-lookup"><span data-stu-id="22a0a-254">Including a package provider in a command can make dynamic parameters available to a cmdlet.</span></span> <span data-ttu-id="22a0a-255">Динамические параметры относятся к поставщику пакетов.</span><span class="sxs-lookup"><span data-stu-id="22a0a-255">Dynamic parameters are specific to a package provider.</span></span> <span data-ttu-id="22a0a-256">`Get-Help`Командлет перечисляет наборы параметров командлета и включает набор параметров поставщика.</span><span class="sxs-lookup"><span data-stu-id="22a0a-256">The `Get-Help` cmdlet lists a cmdlet's parameter sets and includes the provider's parameter set.</span></span> <span data-ttu-id="22a0a-257">Например, `Install-Package` имеет набор параметров **PowerShellGet** , включающий `-NoPathUpdate` , `AllowClobber` и `SkipPublisherCheck` .</span><span class="sxs-lookup"><span data-stu-id="22a0a-257">For example, `Install-Package` has the **PowerShellGet** parameter set that includes `-NoPathUpdate`, `AllowClobber`, and `SkipPublisherCheck`.</span></span>

## <span data-ttu-id="22a0a-258">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="22a0a-258">RELATED LINKS</span></span>

[<span data-ttu-id="22a0a-259">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="22a0a-259">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="22a0a-260">Find-DscResource</span><span class="sxs-lookup"><span data-stu-id="22a0a-260">Find-DscResource</span></span>](../PowershellGet/Find-DscResource.md)

[<span data-ttu-id="22a0a-261">Get-Help</span><span class="sxs-lookup"><span data-stu-id="22a0a-261">Get-Help</span></span>](../Microsoft.PowerShell.Core/Get-Help.md)

[<span data-ttu-id="22a0a-262">Get-Package</span><span class="sxs-lookup"><span data-stu-id="22a0a-262">Get-Package</span></span>](Get-Package.md)

[<span data-ttu-id="22a0a-263">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="22a0a-263">Get-PackageProvider</span></span>](Get-PackageProvider.md)

[<span data-ttu-id="22a0a-264">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="22a0a-264">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="22a0a-265">Find-Package</span><span class="sxs-lookup"><span data-stu-id="22a0a-265">Find-Package</span></span>](Find-Package.md)

[<span data-ttu-id="22a0a-266">Save-Package</span><span class="sxs-lookup"><span data-stu-id="22a0a-266">Save-Package</span></span>](Save-Package.md)

[<span data-ttu-id="22a0a-267">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="22a0a-267">Uninstall-Package</span></span>](Uninstall-Package.md)
