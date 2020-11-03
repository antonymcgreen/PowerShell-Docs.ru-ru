---
external help file: PSModule-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/05/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/find-rolecapability?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-RoleCapability
ms.openlocfilehash: c7392423f4b915716ed1ef911fcfddd215337639
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227270"
---
# <span data-ttu-id="9ec75-103">Find-RoleCapability</span><span class="sxs-lookup"><span data-stu-id="9ec75-103">Find-RoleCapability</span></span>

## <span data-ttu-id="9ec75-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="9ec75-104">SYNOPSIS</span></span>
<span data-ttu-id="9ec75-105">Находит возможности ролей в модулях.</span><span class="sxs-lookup"><span data-stu-id="9ec75-105">Finds role capabilities in modules.</span></span>

## <span data-ttu-id="9ec75-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9ec75-106">SYNTAX</span></span>

### <span data-ttu-id="9ec75-107">Все</span><span class="sxs-lookup"><span data-stu-id="9ec75-107">All</span></span>

```
Find-RoleCapability [[-Name] <String[]>] [-ModuleName <String>] [-MinimumVersion <String>] 
[-MaximumVersion <String>] [-RequiredVersion <String>] [-AllVersions] [-AllowPrerelease] 
[-Tag <String[]>] [-Filter <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>] 
[-Repository <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="9ec75-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9ec75-108">DESCRIPTION</span></span>

<span data-ttu-id="9ec75-109">`Find-RoleCapability`Командлет выполняет поиск в зарегистрированных репозиториях, чтобы найти возможности и модули роли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9ec75-109">The `Find-RoleCapability` cmdlet searches registered repositories to find PowerShell role capabilities and modules.</span></span>

<span data-ttu-id="9ec75-110">Для каждой возможности роли, обнаруженной `Find-RoleCapability` , возвращается объект **PSGetRoleCapabilityInfo** .</span><span class="sxs-lookup"><span data-stu-id="9ec75-110">For each role capability found by `Find-RoleCapability`, a **PSGetRoleCapabilityInfo** object is returned.</span></span> <span data-ttu-id="9ec75-111">Объекты **PSGetRoleCapabilityInfo** можно отсылать по конвейеру в `Install-Module` `Save-Module` командлеты или.</span><span class="sxs-lookup"><span data-stu-id="9ec75-111">**PSGetRoleCapabilityInfo** objects can be sent down the pipeline to the `Install-Module` or `Save-Module` cmdlets.</span></span>

<span data-ttu-id="9ec75-112">Возможности ролей PowerShell определяют, какие команды и приложения доступны пользователю в достаточной конечной точке администрирования (JEA).</span><span class="sxs-lookup"><span data-stu-id="9ec75-112">PowerShell role capabilities define which commands and applications are available to a user at a Just Enough Administration (JEA) endpoint.</span></span> <span data-ttu-id="9ec75-113">Возможности ролей определяются файлами с `.psrc` расширением.</span><span class="sxs-lookup"><span data-stu-id="9ec75-113">Role capabilities are defined by files with a `.psrc` extension.</span></span>

## <span data-ttu-id="9ec75-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="9ec75-114">EXAMPLES</span></span>

### <span data-ttu-id="9ec75-115">Пример 1. Поиск возможностей ролей</span><span class="sxs-lookup"><span data-stu-id="9ec75-115">Example 1: Find role capabilities</span></span>

<span data-ttu-id="9ec75-116">`Find-RoleCapability` находит возможности ролей в каждом зарегистрированном репозитории.</span><span class="sxs-lookup"><span data-stu-id="9ec75-116">`Find-RoleCapability` finds role capabilities in each registered repository.</span></span> <span data-ttu-id="9ec75-117">Для поиска в определенном репозитории используйте параметр **репозитория** .</span><span class="sxs-lookup"><span data-stu-id="9ec75-117">To search a specific repository, use the **Repository** parameter.</span></span>

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

### <span data-ttu-id="9ec75-118">Пример 2. Поиск возможностей роли по имени</span><span class="sxs-lookup"><span data-stu-id="9ec75-118">Example 2: Find role capabilities by name</span></span>

<span data-ttu-id="9ec75-119">`Find-RoleCapability` находит возможности ролей по имени.</span><span class="sxs-lookup"><span data-stu-id="9ec75-119">`Find-RoleCapability` finds role capabilities by name.</span></span> <span data-ttu-id="9ec75-120">Используйте запятые для разделения массива имен.</span><span class="sxs-lookup"><span data-stu-id="9ec75-120">Use commas to separate an array of names.</span></span>

```powershell
Find-RoleCapability -Name General-Lev1, IIS-Lev2
```

```output
Name             Version    ModuleName     Repository
----             -------    ----------     ----------
General-Lev1     1.0        JeaExamples    PSGallery
IIS-Lev2         1.0        JeaExamples    PSGallery
```

### <span data-ttu-id="9ec75-121">Пример 3. Поиск и сохранение модуля возможностей роли</span><span class="sxs-lookup"><span data-stu-id="9ec75-121">Example 3: Find and save a role capability's module</span></span>

<span data-ttu-id="9ec75-122">`Find-RoleCapability`Командлет находит возможность роли и отправляет объект по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="9ec75-122">The `Find-RoleCapability` cmdlet finds a role capability and sends the object down the pipeline.</span></span>
<span data-ttu-id="9ec75-123">`Save-Module` сохраняет модуль возможности роли в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="9ec75-123">`Save-Module` saves the role capability's module to a file system.</span></span> <span data-ttu-id="9ec75-124">`Get-ChildItem` Отображает содержимое каталога модуля.</span><span class="sxs-lookup"><span data-stu-id="9ec75-124">`Get-ChildItem` displays the contents of the module's directory.</span></span>

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

<span data-ttu-id="9ec75-125">`Find-RoleCapability` использует параметр **Name** , чтобы указать возможность роли **общего Lev1** .</span><span class="sxs-lookup"><span data-stu-id="9ec75-125">`Find-RoleCapability` uses the **Name** parameter to specify the **General-Lev1** role capability.</span></span>
<span data-ttu-id="9ec75-126">Объект отправляется по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="9ec75-126">The object is sent down the pipeline.</span></span> <span data-ttu-id="9ec75-127">`Save-Module` использует параметр **path** для расположения файловой системы, чтобы сохранить модуль.</span><span class="sxs-lookup"><span data-stu-id="9ec75-127">`Save-Module` uses the **Path** parameter for the file system location to save the module.</span></span> <span data-ttu-id="9ec75-128">После сохранения модуля `Get-ChildItem` указывает **путь к** модулю и отображает содержимое каталога модуля **жеаексамплес** .</span><span class="sxs-lookup"><span data-stu-id="9ec75-128">After the module is saved, `Get-ChildItem` specifies the module's **Path** and displays the contents of the **JeaExamples** module's directory.</span></span>

### <span data-ttu-id="9ec75-129">Пример 4. Поиск и установка модуля возможностей роли</span><span class="sxs-lookup"><span data-stu-id="9ec75-129">Example 4: Find and install a role capability's module</span></span>

<span data-ttu-id="9ec75-130">`Find-RoleCapability` находит модуль и отправляет объект по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="9ec75-130">`Find-RoleCapability` finds the module and sends the object down the pipeline.</span></span> <span data-ttu-id="9ec75-131">`Install-Module` устанавливает модуль.</span><span class="sxs-lookup"><span data-stu-id="9ec75-131">`Install-Module` installs the module.</span></span> <span data-ttu-id="9ec75-132">После установки используйте `Get-InstalledModule` для просмотра результатов.</span><span class="sxs-lookup"><span data-stu-id="9ec75-132">After the installation, use `Get-InstalledModule` to see the results.</span></span>

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

<span data-ttu-id="9ec75-133">`Find-RoleCapability` использует параметр **Name** , чтобы указать возможность роли **общего Lev1** .</span><span class="sxs-lookup"><span data-stu-id="9ec75-133">`Find-RoleCapability` uses the **Name** parameter to specify the **General-Lev1** role capability.</span></span>
<span data-ttu-id="9ec75-134">Объект отправляется по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="9ec75-134">The object is sent down the pipeline.</span></span> <span data-ttu-id="9ec75-135">`Install-Module` использует параметр **verbose** для вывода сообщений о состоянии во время установки.</span><span class="sxs-lookup"><span data-stu-id="9ec75-135">`Install-Module` uses the **Verbose** parameter to display status messages during the installation.</span></span> <span data-ttu-id="9ec75-136">После завершения установки на `Get-InstalledModule` выходе будет подтверждено, что модуль **жеаексамплес** был установлен.</span><span class="sxs-lookup"><span data-stu-id="9ec75-136">After the install is finished, the `Get-InstalledModule` output confirms that the **JeaExamples** module was installed.</span></span>

## <span data-ttu-id="9ec75-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9ec75-137">PARAMETERS</span></span>

### <span data-ttu-id="9ec75-138">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="9ec75-138">-AllowPrerelease</span></span>

<span data-ttu-id="9ec75-139">Включает ресурсы, помеченные как предварительные версии в результатах.</span><span class="sxs-lookup"><span data-stu-id="9ec75-139">Includes resources marked as a prerelease in the results.</span></span>

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

### <span data-ttu-id="9ec75-140">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="9ec75-140">-AllVersions</span></span>

<span data-ttu-id="9ec75-141">Указывает, что этот командлет получает все версии модуля.</span><span class="sxs-lookup"><span data-stu-id="9ec75-141">Indicates that this cmdlet gets all versions of a module.</span></span> <span data-ttu-id="9ec75-142">Параметр **AllVersions** отображает все доступные версии модуля.</span><span class="sxs-lookup"><span data-stu-id="9ec75-142">The **AllVersions** parameter displays each of a module's available versions.</span></span>

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

### <span data-ttu-id="9ec75-143">-Filter</span><span class="sxs-lookup"><span data-stu-id="9ec75-143">-Filter</span></span>

<span data-ttu-id="9ec75-144">Находит ресурсы на основе синтаксиса поиска поставщика **PackageManagement** .</span><span class="sxs-lookup"><span data-stu-id="9ec75-144">Finds resources based on the **PackageManagement** provider's search syntax.</span></span> <span data-ttu-id="9ec75-145">Например, укажите слова для поиска в свойствах **ModuleName** и **Description** .</span><span class="sxs-lookup"><span data-stu-id="9ec75-145">For example, specify words to search for within the **ModuleName** and **Description** properties.</span></span>

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

### <span data-ttu-id="9ec75-146">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="9ec75-146">-MaximumVersion</span></span>

<span data-ttu-id="9ec75-147">Указывает максимальную версию модуля для включения в результаты.</span><span class="sxs-lookup"><span data-stu-id="9ec75-147">Specifies the maximum version of the module to include in results.</span></span> <span data-ttu-id="9ec75-148">Параметры **MaximumVersion** и **RequiredVersion** нельзя использовать в одной команде.</span><span class="sxs-lookup"><span data-stu-id="9ec75-148">The **MaximumVersion** and the **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="9ec75-149">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="9ec75-149">-MinimumVersion</span></span>

<span data-ttu-id="9ec75-150">Указывает минимальную версию модуля для включения в результаты.</span><span class="sxs-lookup"><span data-stu-id="9ec75-150">Specifies the minimum version of the module to include in results.</span></span> <span data-ttu-id="9ec75-151">Параметры **MinimumVersion** и **RequiredVersion** нельзя использовать в одной команде.</span><span class="sxs-lookup"><span data-stu-id="9ec75-151">The **MinimumVersion** and the **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="9ec75-152">-ModuleName</span><span class="sxs-lookup"><span data-stu-id="9ec75-152">-ModuleName</span></span>

<span data-ttu-id="9ec75-153">Указывает имя модуля, в котором следует искать возможности ролей.</span><span class="sxs-lookup"><span data-stu-id="9ec75-153">Specifies the name of the module in which to search for role capabilities.</span></span> <span data-ttu-id="9ec75-154">По умолчанию все модули.</span><span class="sxs-lookup"><span data-stu-id="9ec75-154">The default is all modules.</span></span>

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

### <span data-ttu-id="9ec75-155">-Name</span><span class="sxs-lookup"><span data-stu-id="9ec75-155">-Name</span></span>

<span data-ttu-id="9ec75-156">Указывает имя возможности роли.</span><span class="sxs-lookup"><span data-stu-id="9ec75-156">Specifies the name of a role capability.</span></span> <span data-ttu-id="9ec75-157">По умолчанию все возможности ролей.</span><span class="sxs-lookup"><span data-stu-id="9ec75-157">The default is all role capabilities.</span></span> <span data-ttu-id="9ec75-158">Используйте запятые для разделения массива имен ресурсов.</span><span class="sxs-lookup"><span data-stu-id="9ec75-158">Use commas to separate an array of resource names.</span></span>

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

### <span data-ttu-id="9ec75-159">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="9ec75-159">-Proxy</span></span>

<span data-ttu-id="9ec75-160">Указывает прокси-сервер для запроса, а не прямое подключение к Интернету.</span><span class="sxs-lookup"><span data-stu-id="9ec75-160">Specifies a proxy server for the request, rather than a direct connection to the internet resource.</span></span>

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

### <span data-ttu-id="9ec75-161">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="9ec75-161">-ProxyCredential</span></span>

<span data-ttu-id="9ec75-162">Указывает учетную запись пользователя с разрешением на использование прокси-сервера, указанного в параметре **прокси** .</span><span class="sxs-lookup"><span data-stu-id="9ec75-162">Specifies a user account with permission to use the proxy server specified in the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="9ec75-163">— Репозиторий;</span><span class="sxs-lookup"><span data-stu-id="9ec75-163">-Repository</span></span>

<span data-ttu-id="9ec75-164">Указывает репозиторий для поиска возможностей роли.</span><span class="sxs-lookup"><span data-stu-id="9ec75-164">Specifies a repository to search for role capabilities.</span></span> <span data-ttu-id="9ec75-165">Используйте запятые для разделения массива имен репозитория.</span><span class="sxs-lookup"><span data-stu-id="9ec75-165">Use commas to separate an array of repository names.</span></span>

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

### <span data-ttu-id="9ec75-166">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="9ec75-166">-RequiredVersion</span></span>

<span data-ttu-id="9ec75-167">Указывает точный номер версии модуля для включения в результаты.</span><span class="sxs-lookup"><span data-stu-id="9ec75-167">Specifies the module's exact version number to include in the results.</span></span> <span data-ttu-id="9ec75-168">Параметры **RequiredVersion** и **MinimumVersion** нельзя использовать в одной команде.</span><span class="sxs-lookup"><span data-stu-id="9ec75-168">The **RequiredVersion** and the **MinimumVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="9ec75-169">-Tag</span><span class="sxs-lookup"><span data-stu-id="9ec75-169">-Tag</span></span>

<span data-ttu-id="9ec75-170">Указывает теги, которые классифицируют модули в репозитории.</span><span class="sxs-lookup"><span data-stu-id="9ec75-170">Specifies tags that categorize modules in a repository.</span></span> <span data-ttu-id="9ec75-171">Используйте запятые для разделения массива тегов.</span><span class="sxs-lookup"><span data-stu-id="9ec75-171">Use commas to separate an array of tags.</span></span>

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

### <span data-ttu-id="9ec75-172">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="9ec75-172">CommonParameters</span></span>

<span data-ttu-id="9ec75-173">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9ec75-173">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9ec75-174">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9ec75-174">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9ec75-175">Входные данные</span><span class="sxs-lookup"><span data-stu-id="9ec75-175">INPUTS</span></span>

## <span data-ttu-id="9ec75-176">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="9ec75-176">OUTPUTS</span></span>

### <span data-ttu-id="9ec75-177">PSGetRoleCapabilityInfo</span><span class="sxs-lookup"><span data-stu-id="9ec75-177">PSGetRoleCapabilityInfo</span></span>

<span data-ttu-id="9ec75-178">`Find-RoleCapability`Командлет возвращает объект **PSGetRoleCapabilityInfo** .</span><span class="sxs-lookup"><span data-stu-id="9ec75-178">The `Find-RoleCapability` cmdlet returns a **PSGetRoleCapabilityInfo** object.</span></span>

## <span data-ttu-id="9ec75-179">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="9ec75-179">NOTES</span></span>

## <span data-ttu-id="9ec75-180">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="9ec75-180">RELATED LINKS</span></span>

[<span data-ttu-id="9ec75-181">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="9ec75-181">Get-ChildItem</span></span>](../Microsoft.PowerShell.Management/Get-ChildItem.md)

[<span data-ttu-id="9ec75-182">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="9ec75-182">Get-InstalledModule</span></span>](Get-InstalledModule.md)

[<span data-ttu-id="9ec75-183">Install-Module</span><span class="sxs-lookup"><span data-stu-id="9ec75-183">Install-Module</span></span>](Install-Module.md)

[<span data-ttu-id="9ec75-184">New-PSRoleCapabilityFile</span><span class="sxs-lookup"><span data-stu-id="9ec75-184">New-PSRoleCapabilityFile</span></span>](../Microsoft.PowerShell.Core/New-PSRoleCapabilityFile.md)

[<span data-ttu-id="9ec75-185">Save-Module</span><span class="sxs-lookup"><span data-stu-id="9ec75-185">Save-Module</span></span>](Save-Module.md)
