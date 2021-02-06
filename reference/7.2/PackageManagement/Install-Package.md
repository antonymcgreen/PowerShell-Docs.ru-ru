---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
Locale: en-US
Module Name: PackageManagement
ms.date: 05/23/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/install-package?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Install-Package
ms.openlocfilehash: 1518be0d34733e36217b46cbbf496e580ec7b649
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "99604287"
---
# <span data-ttu-id="73e7b-102">Install-Package</span><span class="sxs-lookup"><span data-stu-id="73e7b-102">Install-Package</span></span>

## <span data-ttu-id="73e7b-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="73e7b-103">SYNOPSIS</span></span>
<span data-ttu-id="73e7b-104">Устанавливает один или несколько пакетов программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="73e7b-104">Installs one or more software packages.</span></span>

## <span data-ttu-id="73e7b-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="73e7b-105">SYNTAX</span></span>

### <span data-ttu-id="73e7b-106">Паккажебисеарч (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="73e7b-106">PackageBySearch (Default)</span></span>

```
Install-Package [-Name] <String[]> [-RequiredVersion <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-Source <String[]>] [-Credential <PSCredential>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [-ProviderName <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="73e7b-107">паккажебинпутобжект</span><span class="sxs-lookup"><span data-stu-id="73e7b-107">PackageByInputObject</span></span>

```
Install-Package [-InputObject] <SoftwareIdentity[]> [-Credential <PSCredential>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="73e7b-108">NuGet: Паккажебисеарч</span><span class="sxs-lookup"><span data-stu-id="73e7b-108">NuGet:PackageBySearch</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-ConfigFile <String>]
 [-SkipValidate] [-Headers <String[]>] [-FilterOnTag <String[]>] [-Contains <String>]
 [-AllowPrereleaseVersions] [-Destination <String>] [-ExcludeVersion] [-Scope <String>]
 [-SkipDependencies] [<CommonParameters>]
```

### <span data-ttu-id="73e7b-109">NuGet: Паккажебинпутобжект</span><span class="sxs-lookup"><span data-stu-id="73e7b-109">NuGet:PackageByInputObject</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-ConfigFile <String>]
 [-SkipValidate] [-Headers <String[]>] [-FilterOnTag <String[]>] [-Contains <String>]
 [-AllowPrereleaseVersions] [-Destination <String>] [-ExcludeVersion] [-Scope <String>]
 [-SkipDependencies] [<CommonParameters>]
```

### <span data-ttu-id="73e7b-110">PowerShellGet: Паккажебисеарч</span><span class="sxs-lookup"><span data-stu-id="73e7b-110">PowerShellGet:PackageBySearch</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-AllowPrereleaseVersions]
 [-Scope <String>] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [-Type <String>]
 [-Filter <String>] [-Tag <String[]>] [-Includes <String[]>] [-DscResource <String[]>]
 [-RoleCapability <String[]>] [-Command <String[]>] [-AcceptLicense] [-AllowClobber]
 [-SkipPublisherCheck] [-InstallUpdate] [-NoPathUpdate] [<CommonParameters>]
```

### <span data-ttu-id="73e7b-111">PowerShellGet: Паккажебинпутобжект</span><span class="sxs-lookup"><span data-stu-id="73e7b-111">PowerShellGet:PackageByInputObject</span></span>

```
Install-Package [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-AllVersions] [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-AllowPrereleaseVersions]
 [-Scope <String>] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [-Type <String>]
 [-Filter <String>] [-Tag <String[]>] [-Includes <String[]>] [-DscResource <String[]>]
 [-RoleCapability <String[]>] [-Command <String[]>] [-AcceptLicense] [-AllowClobber]
 [-SkipPublisherCheck] [-InstallUpdate] [-NoPathUpdate] [<CommonParameters>]
```

## <span data-ttu-id="73e7b-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="73e7b-112">DESCRIPTION</span></span>

<span data-ttu-id="73e7b-113">`Install-Package`Командлет устанавливает один или несколько пакетов программного обеспечения на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="73e7b-113">The `Install-Package` cmdlet installs one or more software packages on the local computer.</span></span> <span data-ttu-id="73e7b-114">При наличии нескольких источников программного обеспечения используйте `Get-PackageProvider` и `Get-PackageSource` для просмотра сведений о поставщиках.</span><span class="sxs-lookup"><span data-stu-id="73e7b-114">If you have multiple software sources, use `Get-PackageProvider` and `Get-PackageSource` to display details about your providers.</span></span>

## <span data-ttu-id="73e7b-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="73e7b-115">EXAMPLES</span></span>

### <span data-ttu-id="73e7b-116">Пример 1. Установка пакета по имени пакета</span><span class="sxs-lookup"><span data-stu-id="73e7b-116">Example 1: Install a package by package name</span></span>

<span data-ttu-id="73e7b-117">`Install-Package`Командлет устанавливает пакет программного обеспечения и его зависимости.</span><span class="sxs-lookup"><span data-stu-id="73e7b-117">The `Install-Package` cmdlet installs a software package and its dependencies.</span></span>

```
PS> Install-Package -Name NuGet.Core -Source MyNuGet -Credential Contoso\TestUser
```

<span data-ttu-id="73e7b-118">`Install-Package` использует параметры для указания **имени** и **источника** пакетов.</span><span class="sxs-lookup"><span data-stu-id="73e7b-118">`Install-Package` uses parameters to specify the packages **Name** and **Source**.</span></span> <span data-ttu-id="73e7b-119">Параметр **Credential** использует учетную запись пользователя домена с разрешениями на установку пакетов.</span><span class="sxs-lookup"><span data-stu-id="73e7b-119">The **Credential** parameter uses a domain user account with permissions to install packages.</span></span> <span data-ttu-id="73e7b-120">Команда запрашивает пароль учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="73e7b-120">The command prompts you for the user account password.</span></span>

### <span data-ttu-id="73e7b-121">Пример 2. Использование Find-Package для установки пакета</span><span class="sxs-lookup"><span data-stu-id="73e7b-121">Example 2: Use Find-Package to install a package</span></span>

<span data-ttu-id="73e7b-122">В этом примере объект, возвращенный, `Find-Package` отправляется по конвейеру и устанавливается `Install-Package` .</span><span class="sxs-lookup"><span data-stu-id="73e7b-122">In this example, the object returned by `Find-Package` is sent down the pipeline and installed by `Install-Package`.</span></span>

```
PS> Find-Package -Name NuGet.Core -Source MyNuGet | Install-Package
```

<span data-ttu-id="73e7b-123">`Find-Package` использует параметры **Name** и **Source** для нахождение пакета.</span><span class="sxs-lookup"><span data-stu-id="73e7b-123">`Find-Package` uses the **Name** and **Source** parameters to locate a package.</span></span> <span data-ttu-id="73e7b-124">Объект отправляется по конвейеру и `Install-Package` устанавливает пакет на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="73e7b-124">The object is sent down the pipeline and `Install-Package` installs the package on the local computer.</span></span>

### <span data-ttu-id="73e7b-125">Пример 3. Установка пакетов путем указания диапазона версий</span><span class="sxs-lookup"><span data-stu-id="73e7b-125">Example 3: Install packages by specifying a range of versions</span></span>

<span data-ttu-id="73e7b-126">`Install-Package` использует параметры **MinimumVersion** и **MaximumVersion** для указания диапазона версий программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="73e7b-126">`Install-Package` uses the **MinimumVersion** and **MaximumVersion** parameters to specify a range of software versions.</span></span>

```
PS> Install-Package -Name NuGet.Core -Source MyNuGet -MinimumVersion 2.8.0 -MaximumVersion 2.9.0
```

<span data-ttu-id="73e7b-127">`Install-Package` использует параметры **Name** и **Source** для поиска пакета.</span><span class="sxs-lookup"><span data-stu-id="73e7b-127">`Install-Package` uses the **Name** and **Source** parameters to find a package.</span></span> <span data-ttu-id="73e7b-128">Параметры **MinimumVersion** и **MaximumVersion** задают диапазон версий программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="73e7b-128">The **MinimumVersion** and **MaximumVersion** parameters specify a range of software versions.</span></span> <span data-ttu-id="73e7b-129">Устанавливается самая высокая версия в диапазоне.</span><span class="sxs-lookup"><span data-stu-id="73e7b-129">The highest version in the range is installed.</span></span>

## <span data-ttu-id="73e7b-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="73e7b-130">PARAMETERS</span></span>

### <span data-ttu-id="73e7b-131">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="73e7b-131">-AcceptLicense</span></span>

 <span data-ttu-id="73e7b-132">**AcceptLicense** автоматически принимает лицензионное соглашение во время установки.</span><span class="sxs-lookup"><span data-stu-id="73e7b-132">**AcceptLicense** automatically accepts the license agreement during installation.</span></span>

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

### <span data-ttu-id="73e7b-133">-AllowClobber</span><span class="sxs-lookup"><span data-stu-id="73e7b-133">-AllowClobber</span></span>

<span data-ttu-id="73e7b-134">Переопределяет предупреждающие сообщения о конфликтах с существующими командами.</span><span class="sxs-lookup"><span data-stu-id="73e7b-134">Overrides warning messages about conflicts with existing commands.</span></span> <span data-ttu-id="73e7b-135">Перезаписывает существующие команды, имена которых совпадают с именами устанавливаемых команд.</span><span class="sxs-lookup"><span data-stu-id="73e7b-135">Overwrites existing commands that have the same name as commands being installed.</span></span>

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

### <span data-ttu-id="73e7b-136">-Алловпререлеасеверсионс</span><span class="sxs-lookup"><span data-stu-id="73e7b-136">-AllowPrereleaseVersions</span></span>

<span data-ttu-id="73e7b-137">Разрешает установку пакетов, помеченных как предварительные.</span><span class="sxs-lookup"><span data-stu-id="73e7b-137">Allows the installation of packages marked as prerelease.</span></span>

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

### <span data-ttu-id="73e7b-138">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="73e7b-138">-AllVersions</span></span>

<span data-ttu-id="73e7b-139">`Install-Package` устанавливает все доступные версии пакета.</span><span class="sxs-lookup"><span data-stu-id="73e7b-139">`Install-Package` installs all available versions of the package.</span></span> <span data-ttu-id="73e7b-140">По умолчанию установлена только последняя версия.</span><span class="sxs-lookup"><span data-stu-id="73e7b-140">By default, only the newest version is installed.</span></span>

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

### <span data-ttu-id="73e7b-141">-Command</span><span class="sxs-lookup"><span data-stu-id="73e7b-141">-Command</span></span>

<span data-ttu-id="73e7b-142">Указывает одну или несколько команд, выполняющих `Install-Package` Поиск.</span><span class="sxs-lookup"><span data-stu-id="73e7b-142">Specifies one or more commands that `Install-Package` searches.</span></span>

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

### <span data-ttu-id="73e7b-143">-ConfigFile</span><span class="sxs-lookup"><span data-stu-id="73e7b-143">-ConfigFile</span></span>

<span data-ttu-id="73e7b-144">Указывает путь, который содержит файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="73e7b-144">Specifies a path that contains a configuration file.</span></span>

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

### <span data-ttu-id="73e7b-145">— Содержит</span><span class="sxs-lookup"><span data-stu-id="73e7b-145">-Contains</span></span>

<span data-ttu-id="73e7b-146">`Install-Package` Возвращает объекты, если параметр **содержит** указывает значение, совпадающее с любым из значений свойств объекта.</span><span class="sxs-lookup"><span data-stu-id="73e7b-146">`Install-Package` gets objects if the **Contains** parameter specifies a value that matches any of the object's property values.</span></span>

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

### <span data-ttu-id="73e7b-147">-Credential</span><span class="sxs-lookup"><span data-stu-id="73e7b-147">-Credential</span></span>

<span data-ttu-id="73e7b-148">Указывает учетную запись пользователя, имеющую разрешение на доступ к компьютеру и выполнение команд.</span><span class="sxs-lookup"><span data-stu-id="73e7b-148">Specifies a user account that has permission to access the computer and run commands.</span></span> <span data-ttu-id="73e7b-149">Введите имя пользователя, например **User01**, **Domain01\User01**, или введите объект **PSCredential** , созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="73e7b-149">Type a user name, such as **User01**, **Domain01\User01**, or enter a **PSCredential** object, generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="73e7b-150">Если ввести имя пользователя, будет предложено ввести пароль.</span><span class="sxs-lookup"><span data-stu-id="73e7b-150">If you type a user name, you're prompted for a password.</span></span>

<span data-ttu-id="73e7b-151">Если параметр **Credential** не указан, `Install-Package` использует текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="73e7b-151">When the **Credential** parameter isn't specified, `Install-Package` uses the current user.</span></span>

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

### <span data-ttu-id="73e7b-152">-Destination</span><span class="sxs-lookup"><span data-stu-id="73e7b-152">-Destination</span></span>

<span data-ttu-id="73e7b-153">Задает путь к входному объекту.</span><span class="sxs-lookup"><span data-stu-id="73e7b-153">Specifies a path to an input object.</span></span>

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

### <span data-ttu-id="73e7b-154">-DscResource</span><span class="sxs-lookup"><span data-stu-id="73e7b-154">-DscResource</span></span>

<span data-ttu-id="73e7b-155">Указывает один или несколько ресурсов DSC, поиск которых выполняется `Install-Package` .</span><span class="sxs-lookup"><span data-stu-id="73e7b-155">Specifies one or more Desired State Configuration (DSC) resources that are searched by `Install-Package`.</span></span> <span data-ttu-id="73e7b-156">Используйте `Find-DscResource` командлет для поиска ресурсов DSC.</span><span class="sxs-lookup"><span data-stu-id="73e7b-156">Use the `Find-DscResource` cmdlet to find DSC resources.</span></span>

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

### <span data-ttu-id="73e7b-157">-Ексклудеверсион</span><span class="sxs-lookup"><span data-stu-id="73e7b-157">-ExcludeVersion</span></span>

<span data-ttu-id="73e7b-158">Переключитесь, чтобы исключить номер версии из пути к папке.</span><span class="sxs-lookup"><span data-stu-id="73e7b-158">Switch to exclude the version number in the folder path.</span></span>

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

### <span data-ttu-id="73e7b-159">-Filter</span><span class="sxs-lookup"><span data-stu-id="73e7b-159">-Filter</span></span>

<span data-ttu-id="73e7b-160">Задает термины для поиска в свойствах **имя** и **Описание** .</span><span class="sxs-lookup"><span data-stu-id="73e7b-160">Specifies terms to search for within the **Name** and **Description** properties.</span></span>

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

### <span data-ttu-id="73e7b-161">-Филтеронтаг</span><span class="sxs-lookup"><span data-stu-id="73e7b-161">-FilterOnTag</span></span>

<span data-ttu-id="73e7b-162">Указывает тег, фильтрующий результаты и исключающий результаты, которые не содержат указанный тег.</span><span class="sxs-lookup"><span data-stu-id="73e7b-162">Specifies a tag that filters results and excludes results that don't contain the specified tag.</span></span>

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

### <span data-ttu-id="73e7b-163">-Force</span><span class="sxs-lookup"><span data-stu-id="73e7b-163">-Force</span></span>

<span data-ttu-id="73e7b-164">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="73e7b-164">Forces the command to run without asking for user confirmation.</span></span> <span data-ttu-id="73e7b-165">Переопределяет ограничения, которые препятствуют `Install-Package` выполнению, за исключением безопасности.</span><span class="sxs-lookup"><span data-stu-id="73e7b-165">Overrides restrictions that prevent `Install-Package` from succeeding, with the exception of security.</span></span>

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

### <span data-ttu-id="73e7b-166">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="73e7b-166">-ForceBootstrap</span></span>

<span data-ttu-id="73e7b-167">Заставляет службу **PackageManagement** автоматически устанавливать поставщик пакетов для указанного пакета.</span><span class="sxs-lookup"><span data-stu-id="73e7b-167">Forces **PackageManagement** to automatically install the package provider for the specified package.</span></span>

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

### <span data-ttu-id="73e7b-168">-Заголовки</span><span class="sxs-lookup"><span data-stu-id="73e7b-168">-Headers</span></span>

<span data-ttu-id="73e7b-169">Указывает заголовки пакета.</span><span class="sxs-lookup"><span data-stu-id="73e7b-169">Specifies the package headers.</span></span>

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

### <span data-ttu-id="73e7b-170">— Включает</span><span class="sxs-lookup"><span data-stu-id="73e7b-170">-Includes</span></span>

<span data-ttu-id="73e7b-171">Указывает `Install-Package` , следует ли найти все типы пакетов.</span><span class="sxs-lookup"><span data-stu-id="73e7b-171">Specifies whether `Install-Package` should find all package types.</span></span> <span data-ttu-id="73e7b-172">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="73e7b-172">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="73e7b-173">Командлет</span><span class="sxs-lookup"><span data-stu-id="73e7b-173">Cmdlet</span></span>
- <span data-ttu-id="73e7b-174">DscResource</span><span class="sxs-lookup"><span data-stu-id="73e7b-174">DscResource</span></span>
- <span data-ttu-id="73e7b-175">Компонент</span><span class="sxs-lookup"><span data-stu-id="73e7b-175">Function</span></span>
- <span data-ttu-id="73e7b-176">RoleCapability</span><span class="sxs-lookup"><span data-stu-id="73e7b-176">RoleCapability</span></span>
- <span data-ttu-id="73e7b-177">Рабочий процесс</span><span class="sxs-lookup"><span data-stu-id="73e7b-177">Workflow</span></span>

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

### <span data-ttu-id="73e7b-178">-InputObject</span><span class="sxs-lookup"><span data-stu-id="73e7b-178">-InputObject</span></span>

<span data-ttu-id="73e7b-179">Принимает входные данные конвейера.</span><span class="sxs-lookup"><span data-stu-id="73e7b-179">Accepts pipeline input.</span></span> <span data-ttu-id="73e7b-180">Указывает пакет с помощью типа **софтвареидентити** пакета.</span><span class="sxs-lookup"><span data-stu-id="73e7b-180">Specifies a package by using the package's **SoftwareIdentity** type.</span></span>
<span data-ttu-id="73e7b-181">`Find-Package` выводит объект **софтвареидентити** .</span><span class="sxs-lookup"><span data-stu-id="73e7b-181">`Find-Package` outputs a **SoftwareIdentity** object.</span></span>

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

### <span data-ttu-id="73e7b-182">-Инсталлупдате</span><span class="sxs-lookup"><span data-stu-id="73e7b-182">-InstallUpdate</span></span>

<span data-ttu-id="73e7b-183">Указывает, что `Install-Package` устанавливает обновления.</span><span class="sxs-lookup"><span data-stu-id="73e7b-183">Indicates that `Install-Package` installs updates.</span></span>

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

### <span data-ttu-id="73e7b-184">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="73e7b-184">-MaximumVersion</span></span>

<span data-ttu-id="73e7b-185">Указывает максимально допустимую версию пакета, которую вы хотите установить.</span><span class="sxs-lookup"><span data-stu-id="73e7b-185">Specifies the maximum allowed package version that you want to install.</span></span> <span data-ttu-id="73e7b-186">Если этот параметр не указан, `Install-Package` устанавливает последнюю версию пакета.</span><span class="sxs-lookup"><span data-stu-id="73e7b-186">If you don't specify this parameter, `Install-Package` installs the package's newest version.</span></span>

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

### <span data-ttu-id="73e7b-187">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="73e7b-187">-MinimumVersion</span></span>

<span data-ttu-id="73e7b-188">Указывает минимальную допустимую версию пакета, которую вы хотите установить.</span><span class="sxs-lookup"><span data-stu-id="73e7b-188">Specifies the minimum allowed package version that you want to install.</span></span> <span data-ttu-id="73e7b-189">Если вы не добавите этот параметр, `Install-Package` устанавливает последнюю версию пакета, соответствующую любой версии, указанной параметром **MaximumVersion** .</span><span class="sxs-lookup"><span data-stu-id="73e7b-189">If you don't add this parameter, `Install-Package` installs the package's newest version that satisfies any version specified by the **MaximumVersion** parameter.</span></span>

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

### <span data-ttu-id="73e7b-190">-Name</span><span class="sxs-lookup"><span data-stu-id="73e7b-190">-Name</span></span>

<span data-ttu-id="73e7b-191">Указывает одно или несколько имен пакетов.</span><span class="sxs-lookup"><span data-stu-id="73e7b-191">Specifies one or more package names.</span></span> <span data-ttu-id="73e7b-192">Несколько имен пакетов должны быть разделены запятыми.</span><span class="sxs-lookup"><span data-stu-id="73e7b-192">Multiple package names must be separated by commas.</span></span>

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

### <span data-ttu-id="73e7b-193">-NoPathUpdate</span><span class="sxs-lookup"><span data-stu-id="73e7b-193">-NoPathUpdate</span></span>

<span data-ttu-id="73e7b-194">**NoPathUpdate** применяется только к `Install-Script` командлету.</span><span class="sxs-lookup"><span data-stu-id="73e7b-194">**NoPathUpdate** only applies to the `Install-Script` cmdlet.</span></span> <span data-ttu-id="73e7b-195">**NoPathUpdate** — это динамический параметр, добавленный поставщиком и не поддерживаемый `Install-Package` .</span><span class="sxs-lookup"><span data-stu-id="73e7b-195">**NoPathUpdate** is a dynamic parameter added by the provider and isn't supported by `Install-Package`.</span></span>

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

### <span data-ttu-id="73e7b-196">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="73e7b-196">-PackageManagementProvider</span></span>

<span data-ttu-id="73e7b-197">Указывает имя поставщика **PackageManagement** .</span><span class="sxs-lookup"><span data-stu-id="73e7b-197">Specifies the name of the **PackageManagement** provider.</span></span>

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

### <span data-ttu-id="73e7b-198">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="73e7b-198">-ProviderName</span></span>

<span data-ttu-id="73e7b-199">Указывает одно или несколько имен поставщиков пакетов, к которым будет отделана область поиска пакета.</span><span class="sxs-lookup"><span data-stu-id="73e7b-199">Specifies one or more package provider names to which to scope your package search.</span></span> <span data-ttu-id="73e7b-200">Чтобы получить имена поставщиков пакетов, выполните командлет `Get-PackageProvider`.</span><span class="sxs-lookup"><span data-stu-id="73e7b-200">You can get package provider names by running the `Get-PackageProvider` cmdlet.</span></span>

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

### <span data-ttu-id="73e7b-201">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="73e7b-201">-Proxy</span></span>

<span data-ttu-id="73e7b-202">Указывает прокси-сервер для запроса, а не напрямуюе подключение к Интернет-ресурсу.</span><span class="sxs-lookup"><span data-stu-id="73e7b-202">Specifies a proxy server for the request, rather than connecting directly to an internet resource.</span></span>

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

### <span data-ttu-id="73e7b-203">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="73e7b-203">-ProxyCredential</span></span>

<span data-ttu-id="73e7b-204">Указывает учетную запись пользователя, имеющую разрешение на использование прокси-сервера, указанного параметром **прокси** .</span><span class="sxs-lookup"><span data-stu-id="73e7b-204">Specifies a user account that has permission to use the proxy server specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="73e7b-205">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="73e7b-205">-PublishLocation</span></span>

<span data-ttu-id="73e7b-206">Указывает путь к опубликованному расположению пакета.</span><span class="sxs-lookup"><span data-stu-id="73e7b-206">Specifies the path to a package's published location.</span></span>

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

### <span data-ttu-id="73e7b-207">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="73e7b-207">-RequiredVersion</span></span>

<span data-ttu-id="73e7b-208">Указывает точную допустимую версию пакета, который требуется установить.</span><span class="sxs-lookup"><span data-stu-id="73e7b-208">Specifies the exact allowed version of the package that you want to install.</span></span> <span data-ttu-id="73e7b-209">Если вы не добавите этот параметр, `Install-Package` устанавливает последнюю версию пакета, соответствующую любой версии, указанной параметром **MaximumVersion** .</span><span class="sxs-lookup"><span data-stu-id="73e7b-209">If you don't add this parameter, `Install-Package` installs the package's newest version that satisfies any version specified by the **MaximumVersion** parameter.</span></span>

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

### <span data-ttu-id="73e7b-210">-RoleCapability</span><span class="sxs-lookup"><span data-stu-id="73e7b-210">-RoleCapability</span></span>

<span data-ttu-id="73e7b-211">Указывает массив возможностей роли.</span><span class="sxs-lookup"><span data-stu-id="73e7b-211">Specifies an array of role capabilities.</span></span>

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

### <span data-ttu-id="73e7b-212">-Scope</span><span class="sxs-lookup"><span data-stu-id="73e7b-212">-Scope</span></span>

<span data-ttu-id="73e7b-213">Задает область, для которой необходимо установить пакет.</span><span class="sxs-lookup"><span data-stu-id="73e7b-213">Specifies the scope for which to install the package.</span></span> <span data-ttu-id="73e7b-214">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="73e7b-214">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="73e7b-215">CurrentUser</span><span class="sxs-lookup"><span data-stu-id="73e7b-215">CurrentUser</span></span>
- <span data-ttu-id="73e7b-216">AllUsers</span><span class="sxs-lookup"><span data-stu-id="73e7b-216">AllUsers</span></span>

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

### <span data-ttu-id="73e7b-217">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="73e7b-217">-ScriptPublishLocation</span></span>

<span data-ttu-id="73e7b-218">Указывает путь к опубликованному расположению скрипта.</span><span class="sxs-lookup"><span data-stu-id="73e7b-218">Specifies the path to a script's published location.</span></span>

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

### <span data-ttu-id="73e7b-219">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="73e7b-219">-ScriptSourceLocation</span></span>

<span data-ttu-id="73e7b-220">Указывает расположение источника скрипта.</span><span class="sxs-lookup"><span data-stu-id="73e7b-220">Specifies the script source location.</span></span>

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

### <span data-ttu-id="73e7b-221">-СкипдепенденЦиес</span><span class="sxs-lookup"><span data-stu-id="73e7b-221">-SkipDependencies</span></span>

<span data-ttu-id="73e7b-222">Пропускает установку зависимостей программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="73e7b-222">Skips the installation of software dependencies.</span></span>

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

### <span data-ttu-id="73e7b-223">-Скиппублишерчекк</span><span class="sxs-lookup"><span data-stu-id="73e7b-223">-SkipPublisherCheck</span></span>

<span data-ttu-id="73e7b-224">Позволяет получить версию пакета, более новую по сравнению с установленной версией.</span><span class="sxs-lookup"><span data-stu-id="73e7b-224">Allows you to get a package version that is newer than your installed version.</span></span> <span data-ttu-id="73e7b-225">Например, установленный пакет с цифровой подписью доверенного издателя, но новая версия не подписана цифровой подписью.</span><span class="sxs-lookup"><span data-stu-id="73e7b-225">For example, an installed package that is digitally signed by a trusted publisher but a new version isn't digitally signed.</span></span>

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

### <span data-ttu-id="73e7b-226">-Скипвалидате</span><span class="sxs-lookup"><span data-stu-id="73e7b-226">-SkipValidate</span></span>

<span data-ttu-id="73e7b-227">Параметр, который пропускает проверку учетных данных пакета.</span><span class="sxs-lookup"><span data-stu-id="73e7b-227">Switch that skips validating the credentials of a package.</span></span>

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

### <span data-ttu-id="73e7b-228">-Source</span><span class="sxs-lookup"><span data-stu-id="73e7b-228">-Source</span></span>

<span data-ttu-id="73e7b-229">Указывает один или несколько источников пакетов.</span><span class="sxs-lookup"><span data-stu-id="73e7b-229">Specifies one or more package sources.</span></span> <span data-ttu-id="73e7b-230">Несколько имен источников пакетов должны быть разделены запятыми.</span><span class="sxs-lookup"><span data-stu-id="73e7b-230">Multiple package source names must be separated by commas.</span></span>
<span data-ttu-id="73e7b-231">Вы можете получить имена источников пакетов, выполнив `Get-PackageSource` командлет.</span><span class="sxs-lookup"><span data-stu-id="73e7b-231">You can get package source names by running the `Get-PackageSource` cmdlet.</span></span>

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

### <span data-ttu-id="73e7b-232">-Tag</span><span class="sxs-lookup"><span data-stu-id="73e7b-232">-Tag</span></span>

<span data-ttu-id="73e7b-233">Указывает одну или несколько строк для поиска в метаданных пакета.</span><span class="sxs-lookup"><span data-stu-id="73e7b-233">Specifies one or more strings to search for in the package metadata.</span></span>

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

### <span data-ttu-id="73e7b-234">-Type</span><span class="sxs-lookup"><span data-stu-id="73e7b-234">-Type</span></span>

<span data-ttu-id="73e7b-235">Указывает, следует ли выполнять поиск пакетов с помощью модуля, скрипта или и того, и другого.</span><span class="sxs-lookup"><span data-stu-id="73e7b-235">Specifies whether to search for packages with a module, a script, or both.</span></span> <span data-ttu-id="73e7b-236">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="73e7b-236">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="73e7b-237">Модуль</span><span class="sxs-lookup"><span data-stu-id="73e7b-237">Module</span></span>
- <span data-ttu-id="73e7b-238">Скрипт</span><span class="sxs-lookup"><span data-stu-id="73e7b-238">Script</span></span>
- <span data-ttu-id="73e7b-239">Все</span><span class="sxs-lookup"><span data-stu-id="73e7b-239">All</span></span>

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

### <span data-ttu-id="73e7b-240">-Confirm</span><span class="sxs-lookup"><span data-stu-id="73e7b-240">-Confirm</span></span>

<span data-ttu-id="73e7b-241">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="73e7b-241">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="73e7b-242">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="73e7b-242">-WhatIf</span></span>

<span data-ttu-id="73e7b-243">Показывает, что произойдет при `Install-Package` запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="73e7b-243">Shows what would happen if `Install-Package` cmdlet is run.</span></span> <span data-ttu-id="73e7b-244">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="73e7b-244">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="73e7b-245">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="73e7b-245">CommonParameters</span></span>

<span data-ttu-id="73e7b-246">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="73e7b-246">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="73e7b-247">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="73e7b-247">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="73e7b-248">Входные данные</span><span class="sxs-lookup"><span data-stu-id="73e7b-248">INPUTS</span></span>

### <span data-ttu-id="73e7b-249">`Install-Package` принимает входные данные из конвейера.</span><span class="sxs-lookup"><span data-stu-id="73e7b-249">`Install-Package` accepts input from the pipeline.</span></span>

## <span data-ttu-id="73e7b-250">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="73e7b-250">OUTPUTS</span></span>

### <span data-ttu-id="73e7b-251">Софтвареидентити []</span><span class="sxs-lookup"><span data-stu-id="73e7b-251">SoftwareIdentity[]</span></span>

## <span data-ttu-id="73e7b-252">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="73e7b-252">NOTES</span></span>

<span data-ttu-id="73e7b-253">Включение поставщика пакетов в команду может сделать динамические параметры доступными для командлета.</span><span class="sxs-lookup"><span data-stu-id="73e7b-253">Including a package provider in a command can make dynamic parameters available to a cmdlet.</span></span> <span data-ttu-id="73e7b-254">Динамические параметры относятся к поставщику пакетов.</span><span class="sxs-lookup"><span data-stu-id="73e7b-254">Dynamic parameters are specific to a package provider.</span></span> <span data-ttu-id="73e7b-255">`Get-Help`Командлет перечисляет наборы параметров командлета и включает набор параметров поставщика.</span><span class="sxs-lookup"><span data-stu-id="73e7b-255">The `Get-Help` cmdlet lists a cmdlet's parameter sets and includes the provider's parameter set.</span></span> <span data-ttu-id="73e7b-256">Например, `Install-Package` имеет набор параметров **PowerShellGet** , включающий `-NoPathUpdate` , `AllowClobber` и `SkipPublisherCheck` .</span><span class="sxs-lookup"><span data-stu-id="73e7b-256">For example, `Install-Package` has the **PowerShellGet** parameter set that includes `-NoPathUpdate`, `AllowClobber`, and `SkipPublisherCheck`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="73e7b-257">Начиная с апреля 2020 года коллекция PowerShell не поддерживает протокол TLS (Transport Layer Security) версий 1.0 и 1.1.</span><span class="sxs-lookup"><span data-stu-id="73e7b-257">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="73e7b-258">Если вы не используете TLS 1.2 или более поздней версии, при попытке доступа к коллекции PowerShell возникнет ошибка.</span><span class="sxs-lookup"><span data-stu-id="73e7b-258">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="73e7b-259">Чтобы проверить, используется ли TLS 1.2, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="73e7b-259">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="73e7b-260">Дополнительные сведения см. в [объявлении](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) в блоге, посвященном PowerShell.</span><span class="sxs-lookup"><span data-stu-id="73e7b-260">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="73e7b-261">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="73e7b-261">RELATED LINKS</span></span>

[<span data-ttu-id="73e7b-262">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="73e7b-262">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="73e7b-263">Find-DscResource</span><span class="sxs-lookup"><span data-stu-id="73e7b-263">Find-DscResource</span></span>](../PowershellGet/Find-DscResource.md)

[<span data-ttu-id="73e7b-264">Get-Help</span><span class="sxs-lookup"><span data-stu-id="73e7b-264">Get-Help</span></span>](../Microsoft.PowerShell.Core/Get-Help.md)

[<span data-ttu-id="73e7b-265">Get-Package</span><span class="sxs-lookup"><span data-stu-id="73e7b-265">Get-Package</span></span>](Get-Package.md)

[<span data-ttu-id="73e7b-266">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="73e7b-266">Get-PackageProvider</span></span>](Get-PackageProvider.md)

[<span data-ttu-id="73e7b-267">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="73e7b-267">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="73e7b-268">Find-Package</span><span class="sxs-lookup"><span data-stu-id="73e7b-268">Find-Package</span></span>](Find-Package.md)

[<span data-ttu-id="73e7b-269">Save-Package</span><span class="sxs-lookup"><span data-stu-id="73e7b-269">Save-Package</span></span>](Save-Package.md)

[<span data-ttu-id="73e7b-270">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="73e7b-270">Uninstall-Package</span></span>](Uninstall-Package.md)
