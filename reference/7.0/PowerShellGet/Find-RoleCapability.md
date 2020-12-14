---
external help file: PSModule-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/05/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/find-rolecapability?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-RoleCapability
ms.openlocfilehash: 1cee4ac54bf83d387f61a4842104a80512a8b223
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "94891530"
---
# <span data-ttu-id="3d7d5-103">Find-RoleCapability</span><span class="sxs-lookup"><span data-stu-id="3d7d5-103">Find-RoleCapability</span></span>

## <span data-ttu-id="3d7d5-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="3d7d5-104">SYNOPSIS</span></span>
<span data-ttu-id="3d7d5-105">Находит возможности ролей в модулях.</span><span class="sxs-lookup"><span data-stu-id="3d7d5-105">Finds role capabilities in modules.</span></span>

## <span data-ttu-id="3d7d5-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3d7d5-106">SYNTAX</span></span>

### <span data-ttu-id="3d7d5-107">Все</span><span class="sxs-lookup"><span data-stu-id="3d7d5-107">All</span></span>

```
Find-RoleCapability [[-Name] <String[]>] [-ModuleName <String>] [-MinimumVersion <String>] 
[-MaximumVersion <String>] [-RequiredVersion <String>] [-AllVersions] [-AllowPrerelease] 
[-Tag <String[]>] [-Filter <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>] 
[-Repository <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="3d7d5-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3d7d5-108">DESCRIPTION</span></span>

<span data-ttu-id="3d7d5-109">`Find-RoleCapability`Командлет выполняет поиск в зарегистрированных репозиториях, чтобы найти возможности и модули роли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3d7d5-109">The `Find-RoleCapability` cmdlet searches registered repositories to find PowerShell role capabilities and modules.</span></span>

<span data-ttu-id="3d7d5-110">Для каждой возможности роли, обнаруженной `Find-RoleCapability` , возвращается объект **PSGetRoleCapabilityInfo** .</span><span class="sxs-lookup"><span data-stu-id="3d7d5-110">For each role capability found by `Find-RoleCapability`, a **PSGetRoleCapabilityInfo** object is returned.</span></span> <span data-ttu-id="3d7d5-111">Объекты **PSGetRoleCapabilityInfo** можно отсылать по конвейеру в `Install-Module` `Save-Module` командлеты или.</span><span class="sxs-lookup"><span data-stu-id="3d7d5-111">**PSGetRoleCapabilityInfo** objects can be sent down the pipeline to the `Install-Module` or `Save-Module` cmdlets.</span></span>

<span data-ttu-id="3d7d5-112">Возможности ролей PowerShell определяют, какие команды и приложения доступны пользователю в достаточной конечной точке администрирования (JEA).</span><span class="sxs-lookup"><span data-stu-id="3d7d5-112">PowerShell role capabilities define which commands and applications are available to a user at a Just Enough Administration (JEA) endpoint.</span></span> <span data-ttu-id="3d7d5-113">Возможности ролей определяются файлами с `.psrc` расширением.</span><span class="sxs-lookup"><span data-stu-id="3d7d5-113">Role capabilities are defined by files with a `.psrc` extension.</span></span>

## <span data-ttu-id="3d7d5-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="3d7d5-114">EXAMPLES</span></span>

### <span data-ttu-id="3d7d5-115">Пример 1. Поиск возможностей ролей</span><span class="sxs-lookup"><span data-stu-id="3d7d5-115">Example 1: Find role capabilities</span></span>

<span data-ttu-id="3d7d5-116">`Find-RoleCapability` находит возможности ролей в каждом зарегистрированном репозитории.</span><span class="sxs-lookup"><span data-stu-id="3d7d5-116">`Find-RoleCapability` finds role capabilities in each registered repository.</span></span> <span data-ttu-id="3d7d5-117">Для поиска в определенном репозитории используйте параметр **репозитория** .</span><span class="sxs-lookup"><span data-stu-id="3d7d5-117">To search a specific repository, use the **Repository** parameter.</span></span>

```powershell
Find-RoleCapability
```

```output
Name             Version    ModuleName     Repository
----             -------    ----------     ----------
General-Lev1     1.0        JeaExamples    PSGallery
General-Lev2     1.0        JeaExamples    PSGallery
IIS-Lev1         1.0        JeaExamples    PSGallery
IIS-Lev2         1.0        JeaExamples    PSGallery
```

### <span data-ttu-id="3d7d5-118">Пример 2. Поиск возможностей роли по имени</span><span class="sxs-lookup"><span data-stu-id="3d7d5-118">Example 2: Find role capabilities by name</span></span>

<span data-ttu-id="3d7d5-119">`Find-RoleCapability` находит возможности ролей по имени.</span><span class="sxs-lookup"><span data-stu-id="3d7d5-119">`Find-RoleCapability` finds role capabilities by name.</span></span> <span data-ttu-id="3d7d5-120">Используйте запятые для разделения массива имен.</span><span class="sxs-lookup"><span data-stu-id="3d7d5-120">Use commas to separate an array of names.</span></span>

```powershell
Find-RoleCapability -Name General-Lev1, IIS-Lev2
```

```output
Name             Version    ModuleName     Repository
----             -------    ----------     ----------
General-Lev1     1.0        JeaExamples    PSGallery
IIS-Lev2         1.0        JeaExamples    PSGallery
```

### <span data-ttu-id="3d7d5-121">Пример 3. Поиск и сохранение модуля возможностей роли</span><span class="sxs-lookup"><span data-stu-id="3d7d5-121">Example 3: Find and save a role capability's module</span></span>

<span data-ttu-id="3d7d5-122">`Find-RoleCapability`Командлет находит возможность роли и отправляет объект по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="3d7d5-122">The `Find-RoleCapability` cmdlet finds a role capability and sends the object down the pipeline.</span></span>
<span data-ttu-id="3d7d5-123">`Save-Module` сохраняет модуль возможности роли в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="3d7d5-123">`Save-Module` saves the role capability's module to a file system.</span></span> <span data-ttu-id="3d7d5-124">`Get-ChildItem` Отображает содержимое каталога модуля.</span><span class="sxs-lookup"><span data-stu-id="3d7d5-124">`Get-ChildItem` displays the contents of the module's directory.</span></span>

```
PS> Find-RoleCapability -Name General-Lev1 | Save-Module -Path C:\Test\Modules

PS> Get-ChildItem -Path C:\Test\Modules\JeaExamples\1.0\

    Directory: C:\Test\Modules\JeaExamples\1.0

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----          6/4/2019    16:37                RoleCapabilities
-a----          2/5/2019    18:46           1702 CreateRegisterPSSC.ps1
-a----          2/5/2019    18:46           7656 JeaExamples.psd1
-a----         10/1/2018    08:16            595 JeaExamples.psm1
```

<span data-ttu-id="3d7d5-125">`Find-RoleCapability` использует параметр **Name** , чтобы указать возможность роли **общего Lev1** .</span><span class="sxs-lookup"><span data-stu-id="3d7d5-125">`Find-RoleCapability` uses the **Name** parameter to specify the **General-Lev1** role capability.</span></span>
<span data-ttu-id="3d7d5-126">Объект отправляется по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="3d7d5-126">The object is sent down the pipeline.</span></span> <span data-ttu-id="3d7d5-127">`Save-Module` использует параметр **path** для расположения файловой системы, чтобы сохранить модуль.</span><span class="sxs-lookup"><span data-stu-id="3d7d5-127">`Save-Module` uses the **Path** parameter for the file system location to save the module.</span></span> <span data-ttu-id="3d7d5-128">После сохранения модуля `Get-ChildItem` указывает **путь к** модулю и отображает содержимое каталога модуля **жеаексамплес** .</span><span class="sxs-lookup"><span data-stu-id="3d7d5-128">After the module is saved, `Get-ChildItem` specifies the module's **Path** and displays the contents of the **JeaExamples** module's directory.</span></span>

### <span data-ttu-id="3d7d5-129">Пример 4. Поиск и установка модуля возможностей роли</span><span class="sxs-lookup"><span data-stu-id="3d7d5-129">Example 4: Find and install a role capability's module</span></span>

<span data-ttu-id="3d7d5-130">`Find-RoleCapability` находит модуль и отправляет объект по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="3d7d5-130">`Find-RoleCapability` finds the module and sends the object down the pipeline.</span></span> <span data-ttu-id="3d7d5-131">`Install-Module` устанавливает модуль.</span><span class="sxs-lookup"><span data-stu-id="3d7d5-131">`Install-Module` installs the module.</span></span> <span data-ttu-id="3d7d5-132">После установки используйте `Get-InstalledModule` для просмотра результатов.</span><span class="sxs-lookup"><span data-stu-id="3d7d5-132">After the installation, use `Get-InstalledModule` to see the results.</span></span>

```
PS> Find-RoleCapability -Name General-Lev1 | Install-Module -Verbose

VERBOSE: Downloading 'https://www.powershellgallery.com/api/v2/package/JeaExamples/1.0.0'.
VERBOSE: Completed downloading 'https://www.powershellgallery.com/api/v2/package/JeaExamples/1.0.0'.
VERBOSE: Completed downloading 'JeaExamples'.
VERBOSE: InstallPackageLocal' - name='JeaExamples', version='1.0',
VERBOSE: Validating the 'JeaExamples' module contents
VERBOSE: Test-ModuleManifest successfully validated the module manifest file
VERBOSE: Module 'JeaExamples' was installed successfully to path

PS> Get-InstalledModule

Version    Name            Repository     Description
-------    ----            ----------     -----------
1.0        JeaExamples     PSGallery      Some example Jea roles for general server maintenance...
```

<span data-ttu-id="3d7d5-133">`Find-RoleCapability` использует параметр **Name** , чтобы указать возможность роли **общего Lev1** .</span><span class="sxs-lookup"><span data-stu-id="3d7d5-133">`Find-RoleCapability` uses the **Name** parameter to specify the **General-Lev1** role capability.</span></span>
<span data-ttu-id="3d7d5-134">Объект отправляется по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="3d7d5-134">The object is sent down the pipeline.</span></span> <span data-ttu-id="3d7d5-135">`Install-Module` использует параметр **verbose** для вывода сообщений о состоянии во время установки.</span><span class="sxs-lookup"><span data-stu-id="3d7d5-135">`Install-Module` uses the **Verbose** parameter to display status messages during the installation.</span></span> <span data-ttu-id="3d7d5-136">После завершения установки на `Get-InstalledModule` выходе будет подтверждено, что модуль **жеаексамплес** был установлен.</span><span class="sxs-lookup"><span data-stu-id="3d7d5-136">After the install is finished, the `Get-InstalledModule` output confirms that the **JeaExamples** module was installed.</span></span>

## <span data-ttu-id="3d7d5-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3d7d5-137">PARAMETERS</span></span>

### <span data-ttu-id="3d7d5-138">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="3d7d5-138">-AllowPrerelease</span></span>

<span data-ttu-id="3d7d5-139">Включает ресурсы, помеченные как предварительные версии в результатах.</span><span class="sxs-lookup"><span data-stu-id="3d7d5-139">Includes resources marked as a prerelease in the results.</span></span>

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

### <span data-ttu-id="3d7d5-140">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="3d7d5-140">-AllVersions</span></span>

<span data-ttu-id="3d7d5-141">Указывает, что этот командлет получает все версии модуля.</span><span class="sxs-lookup"><span data-stu-id="3d7d5-141">Indicates that this cmdlet gets all versions of a module.</span></span> <span data-ttu-id="3d7d5-142">Параметр **AllVersions** отображает все доступные версии модуля.</span><span class="sxs-lookup"><span data-stu-id="3d7d5-142">The **AllVersions** parameter displays each of a module's available versions.</span></span>

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

### <span data-ttu-id="3d7d5-143">-Filter</span><span class="sxs-lookup"><span data-stu-id="3d7d5-143">-Filter</span></span>

<span data-ttu-id="3d7d5-144">Находит ресурсы на основе синтаксиса поиска поставщика **PackageManagement** .</span><span class="sxs-lookup"><span data-stu-id="3d7d5-144">Finds resources based on the **PackageManagement** provider's search syntax.</span></span> <span data-ttu-id="3d7d5-145">Например, укажите слова для поиска в свойствах **ModuleName** и **Description** .</span><span class="sxs-lookup"><span data-stu-id="3d7d5-145">For example, specify words to search for within the **ModuleName** and **Description** properties.</span></span>

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

### <span data-ttu-id="3d7d5-146">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="3d7d5-146">-MaximumVersion</span></span>

<span data-ttu-id="3d7d5-147">Указывает максимальную версию модуля для включения в результаты.</span><span class="sxs-lookup"><span data-stu-id="3d7d5-147">Specifies the maximum version of the module to include in results.</span></span> <span data-ttu-id="3d7d5-148">Параметры **MaximumVersion** и **RequiredVersion** нельзя использовать в одной команде.</span><span class="sxs-lookup"><span data-stu-id="3d7d5-148">The **MaximumVersion** and the **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="3d7d5-149">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="3d7d5-149">-MinimumVersion</span></span>

<span data-ttu-id="3d7d5-150">Указывает минимальную версию модуля для включения в результаты.</span><span class="sxs-lookup"><span data-stu-id="3d7d5-150">Specifies the minimum version of the module to include in results.</span></span> <span data-ttu-id="3d7d5-151">Параметры **MinimumVersion** и **RequiredVersion** нельзя использовать в одной команде.</span><span class="sxs-lookup"><span data-stu-id="3d7d5-151">The **MinimumVersion** and the **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="3d7d5-152">-ModuleName</span><span class="sxs-lookup"><span data-stu-id="3d7d5-152">-ModuleName</span></span>

<span data-ttu-id="3d7d5-153">Указывает имя модуля, в котором следует искать возможности ролей.</span><span class="sxs-lookup"><span data-stu-id="3d7d5-153">Specifies the name of the module in which to search for role capabilities.</span></span> <span data-ttu-id="3d7d5-154">По умолчанию все модули.</span><span class="sxs-lookup"><span data-stu-id="3d7d5-154">The default is all modules.</span></span>

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

### <span data-ttu-id="3d7d5-155">-Name</span><span class="sxs-lookup"><span data-stu-id="3d7d5-155">-Name</span></span>

<span data-ttu-id="3d7d5-156">Указывает имя возможности роли.</span><span class="sxs-lookup"><span data-stu-id="3d7d5-156">Specifies the name of a role capability.</span></span> <span data-ttu-id="3d7d5-157">По умолчанию все возможности ролей.</span><span class="sxs-lookup"><span data-stu-id="3d7d5-157">The default is all role capabilities.</span></span> <span data-ttu-id="3d7d5-158">Используйте запятые для разделения массива имен ресурсов.</span><span class="sxs-lookup"><span data-stu-id="3d7d5-158">Use commas to separate an array of resource names.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3d7d5-159">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="3d7d5-159">-Proxy</span></span>

<span data-ttu-id="3d7d5-160">Указывает прокси-сервер для запроса, а не прямое подключение к Интернету.</span><span class="sxs-lookup"><span data-stu-id="3d7d5-160">Specifies a proxy server for the request, rather than a direct connection to the internet resource.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="3d7d5-161">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="3d7d5-161">-ProxyCredential</span></span>

<span data-ttu-id="3d7d5-162">Указывает учетную запись пользователя с разрешением на использование прокси-сервера, указанного в параметре **прокси** .</span><span class="sxs-lookup"><span data-stu-id="3d7d5-162">Specifies a user account with permission to use the proxy server specified in the **Proxy** parameter.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="3d7d5-163">— Репозиторий;</span><span class="sxs-lookup"><span data-stu-id="3d7d5-163">-Repository</span></span>

<span data-ttu-id="3d7d5-164">Указывает репозиторий для поиска возможностей роли.</span><span class="sxs-lookup"><span data-stu-id="3d7d5-164">Specifies a repository to search for role capabilities.</span></span> <span data-ttu-id="3d7d5-165">Используйте запятые для разделения массива имен репозитория.</span><span class="sxs-lookup"><span data-stu-id="3d7d5-165">Use commas to separate an array of repository names.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3d7d5-166">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="3d7d5-166">-RequiredVersion</span></span>

<span data-ttu-id="3d7d5-167">Указывает точный номер версии модуля для включения в результаты.</span><span class="sxs-lookup"><span data-stu-id="3d7d5-167">Specifies the module's exact version number to include in the results.</span></span> <span data-ttu-id="3d7d5-168">Параметры **RequiredVersion** и **MinimumVersion** нельзя использовать в одной команде.</span><span class="sxs-lookup"><span data-stu-id="3d7d5-168">The **RequiredVersion** and the **MinimumVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="3d7d5-169">-Tag</span><span class="sxs-lookup"><span data-stu-id="3d7d5-169">-Tag</span></span>

<span data-ttu-id="3d7d5-170">Указывает теги, которые классифицируют модули в репозитории.</span><span class="sxs-lookup"><span data-stu-id="3d7d5-170">Specifies tags that categorize modules in a repository.</span></span> <span data-ttu-id="3d7d5-171">Используйте запятые для разделения массива тегов.</span><span class="sxs-lookup"><span data-stu-id="3d7d5-171">Use commas to separate an array of tags.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3d7d5-172">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="3d7d5-172">CommonParameters</span></span>

<span data-ttu-id="3d7d5-173">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3d7d5-173">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3d7d5-174">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3d7d5-174">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3d7d5-175">Входные данные</span><span class="sxs-lookup"><span data-stu-id="3d7d5-175">INPUTS</span></span>

### <span data-ttu-id="3d7d5-176">System.Uri</span><span class="sxs-lookup"><span data-stu-id="3d7d5-176">System.Uri</span></span>

### <span data-ttu-id="3d7d5-177">System.Management.Automation.PSCredential</span><span class="sxs-lookup"><span data-stu-id="3d7d5-177">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="3d7d5-178">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="3d7d5-178">OUTPUTS</span></span>

### <span data-ttu-id="3d7d5-179">PSGetRoleCapabilityInfo</span><span class="sxs-lookup"><span data-stu-id="3d7d5-179">PSGetRoleCapabilityInfo</span></span>

<span data-ttu-id="3d7d5-180">`Find-RoleCapability`Командлет возвращает объект **PSGetRoleCapabilityInfo** .</span><span class="sxs-lookup"><span data-stu-id="3d7d5-180">The `Find-RoleCapability` cmdlet returns a **PSGetRoleCapabilityInfo** object.</span></span>

## <span data-ttu-id="3d7d5-181">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="3d7d5-181">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3d7d5-182">По состоянию на апрель 2020 коллекция PowerShell больше не поддерживает TLS-версии 1,0 и 1,1.</span><span class="sxs-lookup"><span data-stu-id="3d7d5-182">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="3d7d5-183">Если вы не используете TLS 1,2 или более поздней версии, при попытке доступа к коллекция PowerShell возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="3d7d5-183">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="3d7d5-184">Используйте следующую команду, чтобы убедиться, что используется TLS 1,2:</span><span class="sxs-lookup"><span data-stu-id="3d7d5-184">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="3d7d5-185">Дополнительные сведения см. в [объявлении](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) в блоге PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3d7d5-185">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="3d7d5-186">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="3d7d5-186">RELATED LINKS</span></span>

[<span data-ttu-id="3d7d5-187">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="3d7d5-187">Get-ChildItem</span></span>](../Microsoft.PowerShell.Management/Get-ChildItem.md)

[<span data-ttu-id="3d7d5-188">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="3d7d5-188">Get-InstalledModule</span></span>](Get-InstalledModule.md)

[<span data-ttu-id="3d7d5-189">Install-Module</span><span class="sxs-lookup"><span data-stu-id="3d7d5-189">Install-Module</span></span>](Install-Module.md)

[<span data-ttu-id="3d7d5-190">New-PSRoleCapabilityFile</span><span class="sxs-lookup"><span data-stu-id="3d7d5-190">New-PSRoleCapabilityFile</span></span>](../Microsoft.PowerShell.Core/New-PSRoleCapabilityFile.md)

[<span data-ttu-id="3d7d5-191">Save-Module</span><span class="sxs-lookup"><span data-stu-id="3d7d5-191">Save-Module</span></span>](Save-Module.md)
