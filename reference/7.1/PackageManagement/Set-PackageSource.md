---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PackageManagement
ms.date: 04/03/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/set-packagesource?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PackageSource
ms.openlocfilehash: ad5384f7d708cc708991d4150bf883139007ae1b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228550"
---
# <span data-ttu-id="535a6-103">Set-PackageSource</span><span class="sxs-lookup"><span data-stu-id="535a6-103">Set-PackageSource</span></span>

## <span data-ttu-id="535a6-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="535a6-104">SYNOPSIS</span></span>
<span data-ttu-id="535a6-105">Заменяет источник пакета для указанного поставщика пакетов.</span><span class="sxs-lookup"><span data-stu-id="535a6-105">Replaces a package source for a specified package provider.</span></span>

## <span data-ttu-id="535a6-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="535a6-106">SYNTAX</span></span>

### <span data-ttu-id="535a6-107">Саурцебисеарч (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="535a6-107">SourceBySearch (Default)</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [[-Name] <String>] [-Location <String>] [-NewLocation <String>] [-NewName <String>] [-Trusted]
 [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-ProviderName <String>] [<CommonParameters>]
```

### <span data-ttu-id="535a6-108">саурцебинпутобжект</span><span class="sxs-lookup"><span data-stu-id="535a6-108">SourceByInputObject</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] -InputObject <PackageSource> [-Force]
 [-ForceBootstrap] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="535a6-109">NuGet: Саурцебинпутобжект</span><span class="sxs-lookup"><span data-stu-id="535a6-109">NuGet:SourceByInputObject</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### <span data-ttu-id="535a6-110">NuGet: Саурцебисеарч</span><span class="sxs-lookup"><span data-stu-id="535a6-110">NuGet:SourceBySearch</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### <span data-ttu-id="535a6-111">PowerShellGet: Саурцебинпутобжект</span><span class="sxs-lookup"><span data-stu-id="535a6-111">PowerShellGet:SourceByInputObject</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

### <span data-ttu-id="535a6-112">PowerShellGet: Саурцебисеарч</span><span class="sxs-lookup"><span data-stu-id="535a6-112">PowerShellGet:SourceBySearch</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

## <span data-ttu-id="535a6-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="535a6-113">DESCRIPTION</span></span>

<span data-ttu-id="535a6-114">`Set-PackageSource`Заменяет источник пакета для указанного поставщика пакетов.</span><span class="sxs-lookup"><span data-stu-id="535a6-114">The `Set-PackageSource` replaces a package source for a specified package provider.</span></span> <span data-ttu-id="535a6-115">Источники пакетов всегда управляются поставщиком пакетов.</span><span class="sxs-lookup"><span data-stu-id="535a6-115">Package sources are always managed by a package provider.</span></span>

## <span data-ttu-id="535a6-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="535a6-116">EXAMPLES</span></span>

### <span data-ttu-id="535a6-117">Пример 1. изменение источника пакета</span><span class="sxs-lookup"><span data-stu-id="535a6-117">Example 1: Change a package source</span></span>

<span data-ttu-id="535a6-118">Эта команда изменяет существующее имя источника пакета.</span><span class="sxs-lookup"><span data-stu-id="535a6-118">This command changes the existing name of a package source.</span></span> <span data-ttu-id="535a6-119">Источнику присваивается значение **Trusted (доверенный** ), что исключает запросы на проверку источника при установке пакетов.</span><span class="sxs-lookup"><span data-stu-id="535a6-119">The source is set to **Trusted** , which eliminates prompts to verify the source when packages are installed.</span></span>

```
PS C:\> Set-PackageSource -Name MyNuget -NewName NewNuGet -Trusted -ProviderName NuGet
```

## <span data-ttu-id="535a6-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="535a6-120">PARAMETERS</span></span>

### <span data-ttu-id="535a6-121">-ConfigFile</span><span class="sxs-lookup"><span data-stu-id="535a6-121">-ConfigFile</span></span>

<span data-ttu-id="535a6-122">Указывает файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="535a6-122">Specifies a configuration file.</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet:SourceByInputObject, NuGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="535a6-123">-Credential</span><span class="sxs-lookup"><span data-stu-id="535a6-123">-Credential</span></span>

<span data-ttu-id="535a6-124">Указывает учетную запись пользователя, имеющую разрешение на установку поставщиков пакетов.</span><span class="sxs-lookup"><span data-stu-id="535a6-124">Specifies a user account that has permission to install package providers.</span></span>

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

### <span data-ttu-id="535a6-125">-Force</span><span class="sxs-lookup"><span data-stu-id="535a6-125">-Force</span></span>

<span data-ttu-id="535a6-126">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="535a6-126">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="535a6-127">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="535a6-127">-ForceBootstrap</span></span>

<span data-ttu-id="535a6-128">Указывает, что `Set-PackageSource` заставляет **PackageManagement** автоматически устанавливать поставщик пакетов.</span><span class="sxs-lookup"><span data-stu-id="535a6-128">Indicates that `Set-PackageSource` forces **PackageManagement** to automatically install the package provider.</span></span>

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

### <span data-ttu-id="535a6-129">-InputObject</span><span class="sxs-lookup"><span data-stu-id="535a6-129">-InputObject</span></span>

<span data-ttu-id="535a6-130">Указывает объект исходного идентификатора пакета, представляющий пакет, который необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="535a6-130">Specifies a package source ID object that represents the package that you want to change.</span></span> <span data-ttu-id="535a6-131">Идентификаторы источника пакета являются частью результатов `Get-PackageSource` командлета.</span><span class="sxs-lookup"><span data-stu-id="535a6-131">Package source IDs are part of the results of the `Get-PackageSource` cmdlet.</span></span>

```yaml
Type: Microsoft.PackageManagement.Packaging.PackageSource
Parameter Sets: SourceByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="535a6-132">— Расположение</span><span class="sxs-lookup"><span data-stu-id="535a6-132">-Location</span></span>

<span data-ttu-id="535a6-133">Указывает текущее расположение источника пакета.</span><span class="sxs-lookup"><span data-stu-id="535a6-133">Specifies the current package source location.</span></span> <span data-ttu-id="535a6-134">Значением может быть URI, путь к файлу или любой другой формат назначения, поддерживаемый поставщиком пакетов.</span><span class="sxs-lookup"><span data-stu-id="535a6-134">The value can be a URI, a file path, or any other destination format supported by the package provider.</span></span>

```yaml
Type: System.String
Parameter Sets: SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="535a6-135">-Name</span><span class="sxs-lookup"><span data-stu-id="535a6-135">-Name</span></span>

<span data-ttu-id="535a6-136">Указывает имя источника пакета.</span><span class="sxs-lookup"><span data-stu-id="535a6-136">Specifies a package source's name.</span></span>

```yaml
Type: System.String
Parameter Sets: SourceBySearch
Aliases: SourceName

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="535a6-137">-NewLocation</span><span class="sxs-lookup"><span data-stu-id="535a6-137">-NewLocation</span></span>

<span data-ttu-id="535a6-138">Указывает новое расположение для источника пакета.</span><span class="sxs-lookup"><span data-stu-id="535a6-138">Specifies the new location for a package source.</span></span> <span data-ttu-id="535a6-139">Значением может быть URI, путь к файлу или любой другой формат назначения, поддерживаемый поставщиком пакетов.</span><span class="sxs-lookup"><span data-stu-id="535a6-139">The value can be a URI, a file path, or any other destination format supported by the package provider.</span></span>

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

### <span data-ttu-id="535a6-140">-NewName</span><span class="sxs-lookup"><span data-stu-id="535a6-140">-NewName</span></span>

<span data-ttu-id="535a6-141">Указывает новое имя, назначаемое источнику пакета.</span><span class="sxs-lookup"><span data-stu-id="535a6-141">Specifies the new name you assign to a package source.</span></span>

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

### <span data-ttu-id="535a6-142">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="535a6-142">-PackageManagementProvider</span></span>

<span data-ttu-id="535a6-143">Указывает поставщика управления пакетами.</span><span class="sxs-lookup"><span data-stu-id="535a6-143">Specifies a package management provider.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:SourceByInputObject, PowerShellGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="535a6-144">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="535a6-144">-ProviderName</span></span>

<span data-ttu-id="535a6-145">Указывает имя поставщика.</span><span class="sxs-lookup"><span data-stu-id="535a6-145">Specifies a provider name.</span></span>

```yaml
Type: System.String
Parameter Sets: SourceBySearch
Aliases: Provider
Accepted values: Bootstrap, NuGet, PowerShellGet

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="535a6-146">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="535a6-146">-Proxy</span></span>

<span data-ttu-id="535a6-147">Указывает прокси-сервер для запроса, а не напрямуюе подключение к Интернет-ресурсу.</span><span class="sxs-lookup"><span data-stu-id="535a6-147">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

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

### <span data-ttu-id="535a6-148">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="535a6-148">-ProxyCredential</span></span>

<span data-ttu-id="535a6-149">Указывает учетную запись пользователя, имеющую разрешение на использование прокси-сервера, который задается параметром **Proxy** .</span><span class="sxs-lookup"><span data-stu-id="535a6-149">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="535a6-150">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="535a6-150">-PublishLocation</span></span>

<span data-ttu-id="535a6-151">Указывает расположение публикации.</span><span class="sxs-lookup"><span data-stu-id="535a6-151">Specifies the publish location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:SourceByInputObject, PowerShellGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="535a6-152">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="535a6-152">-ScriptPublishLocation</span></span>

<span data-ttu-id="535a6-153">Указывает расположение публикации скрипта.</span><span class="sxs-lookup"><span data-stu-id="535a6-153">Specifies the script publish location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:SourceByInputObject, PowerShellGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="535a6-154">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="535a6-154">-ScriptSourceLocation</span></span>

<span data-ttu-id="535a6-155">Указывает расположение источника скрипта.</span><span class="sxs-lookup"><span data-stu-id="535a6-155">Specifies the script source location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:SourceByInputObject, PowerShellGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="535a6-156">-Скипвалидате</span><span class="sxs-lookup"><span data-stu-id="535a6-156">-SkipValidate</span></span>

<span data-ttu-id="535a6-157">Параметр, который пропускает проверку учетных данных источника пакета.</span><span class="sxs-lookup"><span data-stu-id="535a6-157">Switch that skips validating the credentials of a package source.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet:SourceByInputObject, NuGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="535a6-158">— Доверенный</span><span class="sxs-lookup"><span data-stu-id="535a6-158">-Trusted</span></span>

<span data-ttu-id="535a6-159">Указывает, что источником является доверенный поставщик пакетов.</span><span class="sxs-lookup"><span data-stu-id="535a6-159">Indicates that the source is a trusted package provider.</span></span> <span data-ttu-id="535a6-160">Надежные источники не запрашивают проверку для установки пакетов.</span><span class="sxs-lookup"><span data-stu-id="535a6-160">Trusted sources don't prompt for verification to install packages.</span></span>

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

### <span data-ttu-id="535a6-161">-Confirm</span><span class="sxs-lookup"><span data-stu-id="535a6-161">-Confirm</span></span>

<span data-ttu-id="535a6-162">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="535a6-162">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="535a6-163">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="535a6-163">-WhatIf</span></span>

<span data-ttu-id="535a6-164">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="535a6-164">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="535a6-165">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="535a6-165">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="535a6-166">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="535a6-166">CommonParameters</span></span>

<span data-ttu-id="535a6-167">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="535a6-167">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="535a6-168">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="535a6-168">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="535a6-169">Входные данные</span><span class="sxs-lookup"><span data-stu-id="535a6-169">INPUTS</span></span>

### <span data-ttu-id="535a6-170">`Set-PackageSource` не принимает входные данные конвейера.</span><span class="sxs-lookup"><span data-stu-id="535a6-170">`Set-PackageSource` doesn't accept pipeline input.</span></span>

## <span data-ttu-id="535a6-171">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="535a6-171">OUTPUTS</span></span>

### <span data-ttu-id="535a6-172">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="535a6-172">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="535a6-173">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="535a6-173">NOTES</span></span>

## <span data-ttu-id="535a6-174">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="535a6-174">RELATED LINKS</span></span>

[<span data-ttu-id="535a6-175">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="535a6-175">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="535a6-176">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="535a6-176">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="535a6-177">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="535a6-177">Register-PackageSource</span></span>](Register-PackageSource.md)

[<span data-ttu-id="535a6-178">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="535a6-178">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)

