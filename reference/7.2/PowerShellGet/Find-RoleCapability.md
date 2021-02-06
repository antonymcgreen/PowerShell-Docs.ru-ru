---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/05/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/find-rolecapability?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-RoleCapability
ms.openlocfilehash: a84dee14872ad5a7d0f7bac8e0057dc527855074
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "99605272"
---
# <span data-ttu-id="e9ff2-102">Find-RoleCapability</span><span class="sxs-lookup"><span data-stu-id="e9ff2-102">Find-RoleCapability</span></span>

## <span data-ttu-id="e9ff2-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="e9ff2-103">SYNOPSIS</span></span>
<span data-ttu-id="e9ff2-104">Находит возможности ролей в модулях.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-104">Finds role capabilities in modules.</span></span>

## <span data-ttu-id="e9ff2-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e9ff2-105">SYNTAX</span></span>

### <span data-ttu-id="e9ff2-106">Все</span><span class="sxs-lookup"><span data-stu-id="e9ff2-106">All</span></span>

```
Find-RoleCapability [[-Name] <String[]>] [-ModuleName <String>] [-MinimumVersion <String>] 
[-MaximumVersion <String>] [-RequiredVersion <String>] [-AllVersions] [-AllowPrerelease] 
[-Tag <String[]>] [-Filter <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>] 
[-Repository <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="e9ff2-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e9ff2-107">DESCRIPTION</span></span>

<span data-ttu-id="e9ff2-108">`Find-RoleCapability`Командлет выполняет поиск в зарегистрированных репозиториях, чтобы найти возможности и модули роли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-108">The `Find-RoleCapability` cmdlet searches registered repositories to find PowerShell role capabilities and modules.</span></span>

<span data-ttu-id="e9ff2-109">Для каждой возможности роли, обнаруженной `Find-RoleCapability` , возвращается объект **PSGetRoleCapabilityInfo** .</span><span class="sxs-lookup"><span data-stu-id="e9ff2-109">For each role capability found by `Find-RoleCapability`, a **PSGetRoleCapabilityInfo** object is returned.</span></span> <span data-ttu-id="e9ff2-110">Объекты **PSGetRoleCapabilityInfo** можно отсылать по конвейеру в `Install-Module` `Save-Module` командлеты или.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-110">**PSGetRoleCapabilityInfo** objects can be sent down the pipeline to the `Install-Module` or `Save-Module` cmdlets.</span></span>

<span data-ttu-id="e9ff2-111">Возможности ролей PowerShell определяют, какие команды и приложения доступны пользователю в достаточной конечной точке администрирования (JEA).</span><span class="sxs-lookup"><span data-stu-id="e9ff2-111">PowerShell role capabilities define which commands and applications are available to a user at a Just Enough Administration (JEA) endpoint.</span></span> <span data-ttu-id="e9ff2-112">Возможности ролей определяются файлами с `.psrc` расширением.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-112">Role capabilities are defined by files with a `.psrc` extension.</span></span>

## <span data-ttu-id="e9ff2-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="e9ff2-113">EXAMPLES</span></span>

### <span data-ttu-id="e9ff2-114">Пример 1. Поиск возможностей ролей</span><span class="sxs-lookup"><span data-stu-id="e9ff2-114">Example 1: Find role capabilities</span></span>

<span data-ttu-id="e9ff2-115">`Find-RoleCapability` находит возможности ролей в каждом зарегистрированном репозитории.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-115">`Find-RoleCapability` finds role capabilities in each registered repository.</span></span> <span data-ttu-id="e9ff2-116">Для поиска в определенном репозитории используйте параметр **репозитория** .</span><span class="sxs-lookup"><span data-stu-id="e9ff2-116">To search a specific repository, use the **Repository** parameter.</span></span>

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

### <span data-ttu-id="e9ff2-117">Пример 2. Поиск возможностей роли по имени</span><span class="sxs-lookup"><span data-stu-id="e9ff2-117">Example 2: Find role capabilities by name</span></span>

<span data-ttu-id="e9ff2-118">`Find-RoleCapability` находит возможности ролей по имени.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-118">`Find-RoleCapability` finds role capabilities by name.</span></span> <span data-ttu-id="e9ff2-119">Используйте запятые для разделения массива имен.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-119">Use commas to separate an array of names.</span></span>

```powershell
Find-RoleCapability -Name General-Lev1, IIS-Lev2
```

```output
Name             Version    ModuleName     Repository
----             -------    ----------     ----------
General-Lev1     1.0        JeaExamples    PSGallery
IIS-Lev2         1.0        JeaExamples    PSGallery
```

### <span data-ttu-id="e9ff2-120">Пример 3. Поиск и сохранение модуля возможностей роли</span><span class="sxs-lookup"><span data-stu-id="e9ff2-120">Example 3: Find and save a role capability's module</span></span>

<span data-ttu-id="e9ff2-121">`Find-RoleCapability`Командлет находит возможность роли и отправляет объект по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-121">The `Find-RoleCapability` cmdlet finds a role capability and sends the object down the pipeline.</span></span>
<span data-ttu-id="e9ff2-122">`Save-Module` сохраняет модуль возможности роли в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-122">`Save-Module` saves the role capability's module to a file system.</span></span> <span data-ttu-id="e9ff2-123">`Get-ChildItem` Отображает содержимое каталога модуля.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-123">`Get-ChildItem` displays the contents of the module's directory.</span></span>

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

<span data-ttu-id="e9ff2-124">`Find-RoleCapability` использует параметр **Name** , чтобы указать возможность роли **общего Lev1** .</span><span class="sxs-lookup"><span data-stu-id="e9ff2-124">`Find-RoleCapability` uses the **Name** parameter to specify the **General-Lev1** role capability.</span></span>
<span data-ttu-id="e9ff2-125">Объект отправляется по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-125">The object is sent down the pipeline.</span></span> <span data-ttu-id="e9ff2-126">`Save-Module` использует параметр **path** для расположения файловой системы, чтобы сохранить модуль.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-126">`Save-Module` uses the **Path** parameter for the file system location to save the module.</span></span> <span data-ttu-id="e9ff2-127">После сохранения модуля `Get-ChildItem` указывает **путь к** модулю и отображает содержимое каталога модуля **жеаексамплес** .</span><span class="sxs-lookup"><span data-stu-id="e9ff2-127">After the module is saved, `Get-ChildItem` specifies the module's **Path** and displays the contents of the **JeaExamples** module's directory.</span></span>

### <span data-ttu-id="e9ff2-128">Пример 4. Поиск и установка модуля возможностей роли</span><span class="sxs-lookup"><span data-stu-id="e9ff2-128">Example 4: Find and install a role capability's module</span></span>

<span data-ttu-id="e9ff2-129">`Find-RoleCapability` находит модуль и отправляет объект по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-129">`Find-RoleCapability` finds the module and sends the object down the pipeline.</span></span> <span data-ttu-id="e9ff2-130">`Install-Module` устанавливает модуль.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-130">`Install-Module` installs the module.</span></span> <span data-ttu-id="e9ff2-131">После установки используйте `Get-InstalledModule` для просмотра результатов.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-131">After the installation, use `Get-InstalledModule` to see the results.</span></span>

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

<span data-ttu-id="e9ff2-132">`Find-RoleCapability` использует параметр **Name** , чтобы указать возможность роли **общего Lev1** .</span><span class="sxs-lookup"><span data-stu-id="e9ff2-132">`Find-RoleCapability` uses the **Name** parameter to specify the **General-Lev1** role capability.</span></span>
<span data-ttu-id="e9ff2-133">Объект отправляется по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-133">The object is sent down the pipeline.</span></span> <span data-ttu-id="e9ff2-134">`Install-Module` использует параметр **verbose** для вывода сообщений о состоянии во время установки.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-134">`Install-Module` uses the **Verbose** parameter to display status messages during the installation.</span></span> <span data-ttu-id="e9ff2-135">После завершения установки на `Get-InstalledModule` выходе будет подтверждено, что модуль **жеаексамплес** был установлен.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-135">After the install is finished, the `Get-InstalledModule` output confirms that the **JeaExamples** module was installed.</span></span>

## <span data-ttu-id="e9ff2-136">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e9ff2-136">PARAMETERS</span></span>

### <span data-ttu-id="e9ff2-137">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="e9ff2-137">-AllowPrerelease</span></span>

<span data-ttu-id="e9ff2-138">Включает ресурсы, помеченные как предварительные версии в результатах.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-138">Includes resources marked as a prerelease in the results.</span></span>

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

### <span data-ttu-id="e9ff2-139">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="e9ff2-139">-AllVersions</span></span>

<span data-ttu-id="e9ff2-140">Указывает, что этот командлет получает все версии модуля.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-140">Indicates that this cmdlet gets all versions of a module.</span></span> <span data-ttu-id="e9ff2-141">Параметр **AllVersions** отображает все доступные версии модуля.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-141">The **AllVersions** parameter displays each of a module's available versions.</span></span>

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

### <span data-ttu-id="e9ff2-142">-Filter</span><span class="sxs-lookup"><span data-stu-id="e9ff2-142">-Filter</span></span>

<span data-ttu-id="e9ff2-143">Находит ресурсы на основе синтаксиса поиска поставщика **PackageManagement** .</span><span class="sxs-lookup"><span data-stu-id="e9ff2-143">Finds resources based on the **PackageManagement** provider's search syntax.</span></span> <span data-ttu-id="e9ff2-144">Например, укажите слова для поиска в свойствах **ModuleName** и **Description** .</span><span class="sxs-lookup"><span data-stu-id="e9ff2-144">For example, specify words to search for within the **ModuleName** and **Description** properties.</span></span>

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

### <span data-ttu-id="e9ff2-145">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="e9ff2-145">-MaximumVersion</span></span>

<span data-ttu-id="e9ff2-146">Указывает максимальную версию модуля для включения в результаты.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-146">Specifies the maximum version of the module to include in results.</span></span> <span data-ttu-id="e9ff2-147">Параметры **MaximumVersion** и **RequiredVersion** нельзя использовать в одной команде.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-147">The **MaximumVersion** and the **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="e9ff2-148">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="e9ff2-148">-MinimumVersion</span></span>

<span data-ttu-id="e9ff2-149">Указывает минимальную версию модуля для включения в результаты.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-149">Specifies the minimum version of the module to include in results.</span></span> <span data-ttu-id="e9ff2-150">Параметры **MinimumVersion** и **RequiredVersion** нельзя использовать в одной команде.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-150">The **MinimumVersion** and the **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="e9ff2-151">-ModuleName</span><span class="sxs-lookup"><span data-stu-id="e9ff2-151">-ModuleName</span></span>

<span data-ttu-id="e9ff2-152">Указывает имя модуля, в котором следует искать возможности ролей.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-152">Specifies the name of the module in which to search for role capabilities.</span></span> <span data-ttu-id="e9ff2-153">По умолчанию все модули.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-153">The default is all modules.</span></span>

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

### <span data-ttu-id="e9ff2-154">-Name</span><span class="sxs-lookup"><span data-stu-id="e9ff2-154">-Name</span></span>

<span data-ttu-id="e9ff2-155">Указывает имя возможности роли.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-155">Specifies the name of a role capability.</span></span> <span data-ttu-id="e9ff2-156">По умолчанию все возможности ролей.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-156">The default is all role capabilities.</span></span> <span data-ttu-id="e9ff2-157">Используйте запятые для разделения массива имен ресурсов.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-157">Use commas to separate an array of resource names.</span></span>

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

### <span data-ttu-id="e9ff2-158">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="e9ff2-158">-Proxy</span></span>

<span data-ttu-id="e9ff2-159">Указывает прокси-сервер для запроса, а не прямое подключение к Интернету.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-159">Specifies a proxy server for the request, rather than a direct connection to the internet resource.</span></span>

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

### <span data-ttu-id="e9ff2-160">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="e9ff2-160">-ProxyCredential</span></span>

<span data-ttu-id="e9ff2-161">Указывает учетную запись пользователя с разрешением на использование прокси-сервера, указанного в параметре **прокси** .</span><span class="sxs-lookup"><span data-stu-id="e9ff2-161">Specifies a user account with permission to use the proxy server specified in the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="e9ff2-162">— Репозиторий;</span><span class="sxs-lookup"><span data-stu-id="e9ff2-162">-Repository</span></span>

<span data-ttu-id="e9ff2-163">Указывает репозиторий для поиска возможностей роли.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-163">Specifies a repository to search for role capabilities.</span></span> <span data-ttu-id="e9ff2-164">Используйте запятые для разделения массива имен репозитория.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-164">Use commas to separate an array of repository names.</span></span>

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

### <span data-ttu-id="e9ff2-165">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="e9ff2-165">-RequiredVersion</span></span>

<span data-ttu-id="e9ff2-166">Указывает точный номер версии модуля для включения в результаты.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-166">Specifies the module's exact version number to include in the results.</span></span> <span data-ttu-id="e9ff2-167">Параметры **RequiredVersion** и **MinimumVersion** нельзя использовать в одной команде.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-167">The **RequiredVersion** and the **MinimumVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="e9ff2-168">-Tag</span><span class="sxs-lookup"><span data-stu-id="e9ff2-168">-Tag</span></span>

<span data-ttu-id="e9ff2-169">Указывает теги, которые классифицируют модули в репозитории.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-169">Specifies tags that categorize modules in a repository.</span></span> <span data-ttu-id="e9ff2-170">Используйте запятые для разделения массива тегов.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-170">Use commas to separate an array of tags.</span></span>

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

### <span data-ttu-id="e9ff2-171">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="e9ff2-171">CommonParameters</span></span>

<span data-ttu-id="e9ff2-172">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-172">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e9ff2-173">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e9ff2-173">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e9ff2-174">Входные данные</span><span class="sxs-lookup"><span data-stu-id="e9ff2-174">INPUTS</span></span>

### <span data-ttu-id="e9ff2-175">System.Uri</span><span class="sxs-lookup"><span data-stu-id="e9ff2-175">System.Uri</span></span>

### <span data-ttu-id="e9ff2-176">System.Management.Automation.PSCredential</span><span class="sxs-lookup"><span data-stu-id="e9ff2-176">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="e9ff2-177">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="e9ff2-177">OUTPUTS</span></span>

### <span data-ttu-id="e9ff2-178">PSGetRoleCapabilityInfo</span><span class="sxs-lookup"><span data-stu-id="e9ff2-178">PSGetRoleCapabilityInfo</span></span>

<span data-ttu-id="e9ff2-179">`Find-RoleCapability`Командлет возвращает объект **PSGetRoleCapabilityInfo** .</span><span class="sxs-lookup"><span data-stu-id="e9ff2-179">The `Find-RoleCapability` cmdlet returns a **PSGetRoleCapabilityInfo** object.</span></span>

## <span data-ttu-id="e9ff2-180">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="e9ff2-180">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e9ff2-181">Начиная с апреля 2020 года коллекция PowerShell не поддерживает протокол TLS (Transport Layer Security) версий 1.0 и 1.1.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-181">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="e9ff2-182">Если вы не используете TLS 1.2 или более поздней версии, при попытке доступа к коллекции PowerShell возникнет ошибка.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-182">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="e9ff2-183">Чтобы проверить, используется ли TLS 1.2, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e9ff2-183">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="e9ff2-184">Дополнительные сведения см. в [объявлении](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) в блоге, посвященном PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e9ff2-184">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="e9ff2-185">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="e9ff2-185">RELATED LINKS</span></span>

[<span data-ttu-id="e9ff2-186">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="e9ff2-186">Get-ChildItem</span></span>](../Microsoft.PowerShell.Management/Get-ChildItem.md)

[<span data-ttu-id="e9ff2-187">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="e9ff2-187">Get-InstalledModule</span></span>](Get-InstalledModule.md)

[<span data-ttu-id="e9ff2-188">Install-Module</span><span class="sxs-lookup"><span data-stu-id="e9ff2-188">Install-Module</span></span>](Install-Module.md)

[<span data-ttu-id="e9ff2-189">New-PSRoleCapabilityFile</span><span class="sxs-lookup"><span data-stu-id="e9ff2-189">New-PSRoleCapabilityFile</span></span>](../Microsoft.PowerShell.Core/New-PSRoleCapabilityFile.md)

[<span data-ttu-id="e9ff2-190">Save-Module</span><span class="sxs-lookup"><span data-stu-id="e9ff2-190">Save-Module</span></span>](Save-Module.md)
