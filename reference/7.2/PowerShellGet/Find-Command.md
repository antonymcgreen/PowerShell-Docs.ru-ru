---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/03/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/find-command?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-Command
ms.openlocfilehash: a24d66aa1ce9e353e41cc7a686ee9f910a7106fc
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "99600679"
---
# <span data-ttu-id="f192c-102">Find-Command</span><span class="sxs-lookup"><span data-stu-id="f192c-102">Find-Command</span></span>

## <span data-ttu-id="f192c-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="f192c-103">SYNOPSIS</span></span>
<span data-ttu-id="f192c-104">Ищет команды PowerShell в модулях.</span><span class="sxs-lookup"><span data-stu-id="f192c-104">Finds PowerShell commands in modules.</span></span>

## <span data-ttu-id="f192c-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f192c-105">SYNTAX</span></span>

### <span data-ttu-id="f192c-106">Все</span><span class="sxs-lookup"><span data-stu-id="f192c-106">All</span></span>

```
Find-Command [[-Name] <String[]>] [-ModuleName <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-RequiredVersion <String>] [-AllVersions] [-AllowPrerelease]
 [-Tag <String[]>] [-Filter <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-Repository <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="f192c-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f192c-107">DESCRIPTION</span></span>

<span data-ttu-id="f192c-108">`Find-Command`Командлет находит команды PowerShell, такие как командлеты, псевдонимы, функции и рабочие процессы.</span><span class="sxs-lookup"><span data-stu-id="f192c-108">The `Find-Command` cmdlet finds PowerShell commands such as cmdlets, aliases, functions, and workflows.</span></span> <span data-ttu-id="f192c-109">`Find-Command` Поиск модулей в зарегистрированных репозиториях.</span><span class="sxs-lookup"><span data-stu-id="f192c-109">`Find-Command` searches modules in registered repositories.</span></span>

<span data-ttu-id="f192c-110">Для каждой команды, найденной в `Find-Command` , возвращается объект **PSGetCommandInfo** .</span><span class="sxs-lookup"><span data-stu-id="f192c-110">For each command found by `Find-Command`, a **PSGetCommandInfo** object is returned.</span></span> <span data-ttu-id="f192c-111">Объект **PSGetCommandInfo** может быть отправлен в командлет по конвейеру `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="f192c-111">The **PSGetCommandInfo** object can be sent down the pipeline to the `Install-Module` cmdlet.</span></span>
<span data-ttu-id="f192c-112">`Install-Module` устанавливает модуль, содержащий команду.</span><span class="sxs-lookup"><span data-stu-id="f192c-112">`Install-Module` installs the module that contains the command.</span></span>

## <span data-ttu-id="f192c-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="f192c-113">EXAMPLES</span></span>

### <span data-ttu-id="f192c-114">Пример 1. Поиск всех команд в указанном репозитории</span><span class="sxs-lookup"><span data-stu-id="f192c-114">Example 1: Find all commands in a specified repository</span></span>

<span data-ttu-id="f192c-115">`Find-Command`Командлет выполняет поиск модулей в зарегистрированном репозитории.</span><span class="sxs-lookup"><span data-stu-id="f192c-115">The `Find-Command` cmdlet searches a registered repository for modules.</span></span>

```powershell
Find-Command -Repository PSGallery | Select-Object -First 10
```

```output
Name                                Version    ModuleName          Repository
----                                -------    ----------          ----------
Disable-AzureRmDataCollection       5.8.3      AzureRM.profile     PSGallery
Disable-AzureRmContextAutosave      5.8.3      AzureRM.profile     PSGallery
Enable-AzureRmDataCollection        5.8.3      AzureRM.profile     PSGallery
Enable-AzureRmContextAutosave       5.8.3      AzureRM.profile     PSGallery
Remove-AzureRmEnvironment           5.8.3      AzureRM.profile     PSGallery
Get-AzureRmEnvironment              5.8.3      AzureRM.profile     PSGallery
Set-AzureRmEnvironment              5.8.3      AzureRM.profile     PSGallery
Add-AzureRmEnvironment              5.8.3      AzureRM.profile     PSGallery
Get-AzureRmSubscription             5.8.3      AzureRM.profile     PSGallery
Connect-AzureRmAccount              5.8.3      AzureRM.profile     PSGallery
```

<span data-ttu-id="f192c-116">`Find-Command` использует параметр **репозитория** для указания имени зарегистрированного репозитория.</span><span class="sxs-lookup"><span data-stu-id="f192c-116">`Find-Command` uses the **Repository** parameter to specify a registered repository's name.</span></span> <span data-ttu-id="f192c-117">Объекты отправляются по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="f192c-117">The objects are sent down the pipeline.</span></span> <span data-ttu-id="f192c-118">`Select-Object` Получает объекты и использует **первый** параметр для вывода первых 10 результатов.</span><span class="sxs-lookup"><span data-stu-id="f192c-118">`Select-Object` receives the objects and uses the **First** parameter to display the first 10 results.</span></span>

### <span data-ttu-id="f192c-119">Пример 2. Поиск команды по имени</span><span class="sxs-lookup"><span data-stu-id="f192c-119">Example 2: Find a command by name</span></span>

<span data-ttu-id="f192c-120">`Find-Command` может использовать имя команды для нахождение модуля в репозитории.</span><span class="sxs-lookup"><span data-stu-id="f192c-120">`Find-Command` can use the name of a command to locate the module in a repository.</span></span> <span data-ttu-id="f192c-121">Возможно, имя команды существует в нескольких **модуленамес**.</span><span class="sxs-lookup"><span data-stu-id="f192c-121">It's possible that a command name exists in multiple **ModuleNames**.</span></span>

```powershell
Find-Command -Repository PSGallery -Name Get-TargetResource
```

```Output
Name                  Version    ModuleName                      Repository
----                  -------    ----------                      ----------
Get-TargetResource    3.1.0.0    xPowerShellExecutionPolicy      PSGallery
Get-TargetResource    1.0.0      xInternetExplorerHomePage       PSGallery
Get-TargetResource    1.2.0.0    SystemLocaleDsc                 PSGallery
```

<span data-ttu-id="f192c-122">`Find-Command` использует параметр **репозитория** для поиска в **PSGallery**.</span><span class="sxs-lookup"><span data-stu-id="f192c-122">`Find-Command` uses the **Repository** parameter to search the **PSGallery**.</span></span> <span data-ttu-id="f192c-123">Параметр **Name** указывает команду **Get-TargetResource**.</span><span class="sxs-lookup"><span data-stu-id="f192c-123">The **Name** parameter specifies the command **Get-TargetResource**.</span></span>

### <span data-ttu-id="f192c-124">Пример 3. Поиск команд по имени и установка модуля</span><span class="sxs-lookup"><span data-stu-id="f192c-124">Example 3: Find commands by name and install the module</span></span>

<span data-ttu-id="f192c-125">`Find-Command` может разместить команду и модуль, а затем отправить объект в `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="f192c-125">`Find-Command` can locate the command and module, then send the object to `Install-Module`.</span></span> <span data-ttu-id="f192c-126">Если команда включена в несколько модулей, используйте `Find-Command` параметр **module-name модуля** командлетов.</span><span class="sxs-lookup"><span data-stu-id="f192c-126">If a command is included in multiple modules, use the `Find-Command` cmdlets **Module-Name** parameter.</span></span>
<span data-ttu-id="f192c-127">В противном случае могут быть установлены модули, которые не нужно устанавливать.</span><span class="sxs-lookup"><span data-stu-id="f192c-127">Otherwise, modules might be installed that you didn't want to install.</span></span>

```powershell
PS> Find-Command -Name Get-TargetResource -Repository PSGallery -ModuleName SystemLocaleDsc |
    Install-Module

PS> Get-InstalledModule

Version   Name               Repository   Description
-------   ----               ----------   -----------
1.2.0.0   SystemLocaleDsc    PSGallery    This DSC Resource allows configuration of the Windows...
```

<span data-ttu-id="f192c-128">`Find-Command` использует параметр **Name** для указания команды **Get-TargetResource**.</span><span class="sxs-lookup"><span data-stu-id="f192c-128">`Find-Command` uses the **Name** parameter to specify the command **Get-TargetResource**.</span></span> <span data-ttu-id="f192c-129">Параметр **репозитория** выполняет поиск в **PSGallery**.</span><span class="sxs-lookup"><span data-stu-id="f192c-129">The **Repository** parameter searches the **PSGallery**.</span></span> <span data-ttu-id="f192c-130">Параметр **ModuleName** указывает модуль, который необходимо установить, **системлокаледск**.</span><span class="sxs-lookup"><span data-stu-id="f192c-130">The **ModuleName** parameter specifies the module you want to install, **SystemLocaleDsc**.</span></span> <span data-ttu-id="f192c-131">Объект отправляется по конвейеру в `Install-Module` и устанавливается модуль.</span><span class="sxs-lookup"><span data-stu-id="f192c-131">The object is sent down the pipeline to `Install-Module` and the module is installed.</span></span> <span data-ttu-id="f192c-132">После завершения установки можно использовать `Get-InstalledModule` для вывода результатов.</span><span class="sxs-lookup"><span data-stu-id="f192c-132">After the installation finishes, you can use `Get-InstalledModule` to display the results.</span></span>

### <span data-ttu-id="f192c-133">Пример 4. Поиск команды и сохранение ее модуля</span><span class="sxs-lookup"><span data-stu-id="f192c-133">Example 4: Find a command and save its module</span></span>

```
PS> Find-Command -Name Invoke-ScriptAnalyzer -Repository PSGallery | Save-Module -Path C:\Test\Modules -Verbose

VERBOSE: Downloading 'https://www.powershellgallery.com/api/v2/package/PSScriptAnalyzer/1.18.0'.
VERBOSE: Completed downloading 'https://www.powershellgallery.com/api/v2/package/PSScriptAnalyzer/1.18.0'.
VERBOSE: Completed downloading 'PSScriptAnalyzer'.
VERBOSE: Module 'PSScriptAnalyzer' was saved successfully to path 'C:\Test\Modules\PSScriptAnalyzer\1.18.0'.
```

<span data-ttu-id="f192c-134">`Find-Command` использует параметры **имени** и **репозитория** для поиска команды **Invoke-ScriptAnalyzer** в репозитории **PSGallery** .</span><span class="sxs-lookup"><span data-stu-id="f192c-134">`Find-Command` uses the **Name** and **Repository** parameters to search for the command **Invoke-ScriptAnalyzer** in the **PSGallery** repository.</span></span> <span data-ttu-id="f192c-135">Объект отправляется по конвейеру в `Save-Module` .</span><span class="sxs-lookup"><span data-stu-id="f192c-135">The object is sent down the pipeline to `Save-Module`.</span></span> <span data-ttu-id="f192c-136">Параметр **path** определяет расположение для сохранения модуля.</span><span class="sxs-lookup"><span data-stu-id="f192c-136">The **Path** parameter determines the location to save the module.</span></span> <span data-ttu-id="f192c-137">**Verbose** является необязательным параметром, но отображает выходные данные состояния в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f192c-137">**Verbose** is an optional parameter, but displays status output in the PowerShell console.</span></span> <span data-ttu-id="f192c-138">Подробные выходные данные полезны для устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="f192c-138">The verbose output is beneficial for troubleshooting.</span></span>

## <span data-ttu-id="f192c-139">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f192c-139">PARAMETERS</span></span>

### <span data-ttu-id="f192c-140">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="f192c-140">-AllowPrerelease</span></span>

<span data-ttu-id="f192c-141">Включает модули, помеченные как предварительные версии в результатах.</span><span class="sxs-lookup"><span data-stu-id="f192c-141">Includes modules marked as a prerelease in the results.</span></span>

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

### <span data-ttu-id="f192c-142">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="f192c-142">-AllVersions</span></span>

<span data-ttu-id="f192c-143">Указывает, что этот командлет получает все версии модуля.</span><span class="sxs-lookup"><span data-stu-id="f192c-143">Indicates that this cmdlet gets all versions of a module.</span></span>

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

### <span data-ttu-id="f192c-144">-Filter</span><span class="sxs-lookup"><span data-stu-id="f192c-144">-Filter</span></span>

<span data-ttu-id="f192c-145">Находит модули на основе синтаксиса поиска поставщика **PackageManagement** .</span><span class="sxs-lookup"><span data-stu-id="f192c-145">Finds modules based on the **PackageManagement** provider's search syntax.</span></span> <span data-ttu-id="f192c-146">Например, укажите слова для поиска в свойствах **ModuleName** и **Description** .</span><span class="sxs-lookup"><span data-stu-id="f192c-146">For example, specify words to search for within the **ModuleName** and **Description** properties.</span></span>

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

### <span data-ttu-id="f192c-147">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="f192c-147">-MaximumVersion</span></span>

<span data-ttu-id="f192c-148">Указывает максимальную версию модуля для включения в результаты.</span><span class="sxs-lookup"><span data-stu-id="f192c-148">Specifies the maximum version of the module to include in results.</span></span> <span data-ttu-id="f192c-149">Параметры **MaximumVersion** и **RequiredVersion** нельзя использовать в одной команде.</span><span class="sxs-lookup"><span data-stu-id="f192c-149">The **MaximumVersion** and the **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="f192c-150">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="f192c-150">-MinimumVersion</span></span>

<span data-ttu-id="f192c-151">Указывает минимальную версию модуля для включения в результаты.</span><span class="sxs-lookup"><span data-stu-id="f192c-151">Specifies the minimum version of the module to include in results.</span></span> <span data-ttu-id="f192c-152">Параметры **MinimumVersion** и **RequiredVersion** нельзя использовать в одной команде.</span><span class="sxs-lookup"><span data-stu-id="f192c-152">The **MinimumVersion** and the **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="f192c-153">-ModuleName</span><span class="sxs-lookup"><span data-stu-id="f192c-153">-ModuleName</span></span>

<span data-ttu-id="f192c-154">Указывает имя модуля для поиска команд.</span><span class="sxs-lookup"><span data-stu-id="f192c-154">Specifies the name of a module to search for commands.</span></span> <span data-ttu-id="f192c-155">По умолчанию все модули.</span><span class="sxs-lookup"><span data-stu-id="f192c-155">The default is all modules.</span></span>

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

### <span data-ttu-id="f192c-156">-Name</span><span class="sxs-lookup"><span data-stu-id="f192c-156">-Name</span></span>

<span data-ttu-id="f192c-157">Указывает имя команды для поиска в репозитории.</span><span class="sxs-lookup"><span data-stu-id="f192c-157">Specifies the command name to search for in a repository.</span></span> <span data-ttu-id="f192c-158">Используйте запятые для разделения массива имен команд.</span><span class="sxs-lookup"><span data-stu-id="f192c-158">Use commas to separate an array of command names.</span></span>

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

### <span data-ttu-id="f192c-159">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="f192c-159">-Proxy</span></span>

<span data-ttu-id="f192c-160">Указывает прокси-сервер для запроса, а не прямое подключение к Интернету.</span><span class="sxs-lookup"><span data-stu-id="f192c-160">Specifies a proxy server for the request, rather than a direct connection to the internet resource.</span></span>

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

### <span data-ttu-id="f192c-161">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="f192c-161">-ProxyCredential</span></span>

<span data-ttu-id="f192c-162">Указывает учетную запись пользователя, имеющую разрешение на использование прокси-сервера, который задается параметром **Proxy**.</span><span class="sxs-lookup"><span data-stu-id="f192c-162">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="f192c-163">— Репозиторий;</span><span class="sxs-lookup"><span data-stu-id="f192c-163">-Repository</span></span>

<span data-ttu-id="f192c-164">Указывает репозиторий для поиска команд.</span><span class="sxs-lookup"><span data-stu-id="f192c-164">Specifies the repository to search for commands.</span></span> <span data-ttu-id="f192c-165">Используйте запятые для разделения массива имен репозитория.</span><span class="sxs-lookup"><span data-stu-id="f192c-165">Use commas to separate an array of repository names.</span></span> <span data-ttu-id="f192c-166">Значение по умолчанию — все репозитории.</span><span class="sxs-lookup"><span data-stu-id="f192c-166">The default is all repositories.</span></span>

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

### <span data-ttu-id="f192c-167">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="f192c-167">-RequiredVersion</span></span>

<span data-ttu-id="f192c-168">Указывает версию модуля для включения в результаты.</span><span class="sxs-lookup"><span data-stu-id="f192c-168">Specifies the version of the module to include in the results.</span></span>

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

### <span data-ttu-id="f192c-169">-Tag</span><span class="sxs-lookup"><span data-stu-id="f192c-169">-Tag</span></span>

<span data-ttu-id="f192c-170">Указывает теги, которые классифицируют модули в репозитории.</span><span class="sxs-lookup"><span data-stu-id="f192c-170">Specifies tags that categorize modules in a repository.</span></span> <span data-ttu-id="f192c-171">Используйте запятые для разделения массива тегов.</span><span class="sxs-lookup"><span data-stu-id="f192c-171">Use commas to separate an array of tags.</span></span>

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

### <span data-ttu-id="f192c-172">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="f192c-172">CommonParameters</span></span>

<span data-ttu-id="f192c-173">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f192c-173">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f192c-174">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f192c-174">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f192c-175">Входные данные</span><span class="sxs-lookup"><span data-stu-id="f192c-175">INPUTS</span></span>

## <span data-ttu-id="f192c-176">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="f192c-176">OUTPUTS</span></span>

### <span data-ttu-id="f192c-177">PSGetCommandInfo</span><span class="sxs-lookup"><span data-stu-id="f192c-177">PSGetCommandInfo</span></span>

<span data-ttu-id="f192c-178">`Find-Command` выводит объект **PSGetCommandInfo** .</span><span class="sxs-lookup"><span data-stu-id="f192c-178">`Find-Command` outputs a **PSGetCommandInfo** object.</span></span>

## <span data-ttu-id="f192c-179">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="f192c-179">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f192c-180">Начиная с апреля 2020 года коллекция PowerShell не поддерживает протокол TLS (Transport Layer Security) версий 1.0 и 1.1.</span><span class="sxs-lookup"><span data-stu-id="f192c-180">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="f192c-181">Если вы не используете TLS 1.2 или более поздней версии, при попытке доступа к коллекции PowerShell возникнет ошибка.</span><span class="sxs-lookup"><span data-stu-id="f192c-181">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="f192c-182">Чтобы проверить, используется ли TLS 1.2, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f192c-182">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="f192c-183">Дополнительные сведения см. в [объявлении](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) в блоге, посвященном PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f192c-183">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="f192c-184">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="f192c-184">RELATED LINKS</span></span>

[<span data-ttu-id="f192c-185">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="f192c-185">Get-InstalledModule</span></span>](Get-InstalledModule.md)

[<span data-ttu-id="f192c-186">Install-Module</span><span class="sxs-lookup"><span data-stu-id="f192c-186">Install-Module</span></span>](Install-Module.md)

[<span data-ttu-id="f192c-187">Save-Module</span><span class="sxs-lookup"><span data-stu-id="f192c-187">Save-Module</span></span>](Save-Module.md)

[<span data-ttu-id="f192c-188">Select-Object</span><span class="sxs-lookup"><span data-stu-id="f192c-188">Select-Object</span></span>](../Microsoft.PowerShell.Utility/Select-Object.md)

[<span data-ttu-id="f192c-189">Uninstall — Module</span><span class="sxs-lookup"><span data-stu-id="f192c-189">Uninstall-Module</span></span>](Uninstall-Module.md)
