---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
Locale: en-US
Module Name: PackageManagement
ms.date: 04/03/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/set-packagesource?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PackageSource
ms.openlocfilehash: 9f258c3b02064aafdaf272141f2613ff5cbaf5b5
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "99605047"
---
# <span data-ttu-id="e025a-102">Set-PackageSource</span><span class="sxs-lookup"><span data-stu-id="e025a-102">Set-PackageSource</span></span>

## <span data-ttu-id="e025a-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="e025a-103">SYNOPSIS</span></span>
<span data-ttu-id="e025a-104">Заменяет источник пакета для указанного поставщика пакетов.</span><span class="sxs-lookup"><span data-stu-id="e025a-104">Replaces a package source for a specified package provider.</span></span>

## <span data-ttu-id="e025a-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e025a-105">SYNTAX</span></span>

### <span data-ttu-id="e025a-106">Саурцебисеарч (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="e025a-106">SourceBySearch (Default)</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [[-Name] <String>] [-Location <String>] [-NewLocation <String>] [-NewName <String>] [-Trusted]
 [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-ProviderName <String>] [<CommonParameters>]
```

### <span data-ttu-id="e025a-107">саурцебинпутобжект</span><span class="sxs-lookup"><span data-stu-id="e025a-107">SourceByInputObject</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] -InputObject <PackageSource> [-Force]
 [-ForceBootstrap] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="e025a-108">NuGet: Саурцебинпутобжект</span><span class="sxs-lookup"><span data-stu-id="e025a-108">NuGet:SourceByInputObject</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### <span data-ttu-id="e025a-109">NuGet: Саурцебисеарч</span><span class="sxs-lookup"><span data-stu-id="e025a-109">NuGet:SourceBySearch</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### <span data-ttu-id="e025a-110">PowerShellGet: Саурцебинпутобжект</span><span class="sxs-lookup"><span data-stu-id="e025a-110">PowerShellGet:SourceByInputObject</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

### <span data-ttu-id="e025a-111">PowerShellGet: Саурцебисеарч</span><span class="sxs-lookup"><span data-stu-id="e025a-111">PowerShellGet:SourceBySearch</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

## <span data-ttu-id="e025a-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e025a-112">DESCRIPTION</span></span>

<span data-ttu-id="e025a-113">`Set-PackageSource`Заменяет источник пакета для указанного поставщика пакетов.</span><span class="sxs-lookup"><span data-stu-id="e025a-113">The `Set-PackageSource` replaces a package source for a specified package provider.</span></span> <span data-ttu-id="e025a-114">Источники пакетов всегда управляются поставщиком пакетов.</span><span class="sxs-lookup"><span data-stu-id="e025a-114">Package sources are always managed by a package provider.</span></span>

## <span data-ttu-id="e025a-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="e025a-115">EXAMPLES</span></span>

### <span data-ttu-id="e025a-116">Пример 1. изменение источника пакета</span><span class="sxs-lookup"><span data-stu-id="e025a-116">Example 1: Change a package source</span></span>

<span data-ttu-id="e025a-117">Эта команда изменяет существующее имя источника пакета.</span><span class="sxs-lookup"><span data-stu-id="e025a-117">This command changes the existing name of a package source.</span></span> <span data-ttu-id="e025a-118">Источнику присваивается значение **Trusted (доверенный**), что исключает запросы на проверку источника при установке пакетов.</span><span class="sxs-lookup"><span data-stu-id="e025a-118">The source is set to **Trusted**, which eliminates prompts to verify the source when packages are installed.</span></span>

```
PS C:\> Set-PackageSource -Name MyNuget -NewName NewNuGet -Trusted -ProviderName NuGet
```

## <span data-ttu-id="e025a-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e025a-119">PARAMETERS</span></span>

### <span data-ttu-id="e025a-120">-ConfigFile</span><span class="sxs-lookup"><span data-stu-id="e025a-120">-ConfigFile</span></span>

<span data-ttu-id="e025a-121">Указывает файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e025a-121">Specifies a configuration file.</span></span>

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

### <span data-ttu-id="e025a-122">-Credential</span><span class="sxs-lookup"><span data-stu-id="e025a-122">-Credential</span></span>

<span data-ttu-id="e025a-123">Указывает учетную запись пользователя, имеющую разрешение на установку поставщиков пакетов.</span><span class="sxs-lookup"><span data-stu-id="e025a-123">Specifies a user account that has permission to install package providers.</span></span>

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

### <span data-ttu-id="e025a-124">-Force</span><span class="sxs-lookup"><span data-stu-id="e025a-124">-Force</span></span>

<span data-ttu-id="e025a-125">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="e025a-125">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="e025a-126">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="e025a-126">-ForceBootstrap</span></span>

<span data-ttu-id="e025a-127">Указывает, что `Set-PackageSource` заставляет **PackageManagement** автоматически устанавливать поставщик пакетов.</span><span class="sxs-lookup"><span data-stu-id="e025a-127">Indicates that `Set-PackageSource` forces **PackageManagement** to automatically install the package provider.</span></span>

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

### <span data-ttu-id="e025a-128">-InputObject</span><span class="sxs-lookup"><span data-stu-id="e025a-128">-InputObject</span></span>

<span data-ttu-id="e025a-129">Указывает объект исходного идентификатора пакета, представляющий пакет, который необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="e025a-129">Specifies a package source ID object that represents the package that you want to change.</span></span> <span data-ttu-id="e025a-130">Идентификаторы источника пакета являются частью результатов `Get-PackageSource` командлета.</span><span class="sxs-lookup"><span data-stu-id="e025a-130">Package source IDs are part of the results of the `Get-PackageSource` cmdlet.</span></span>

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

### <span data-ttu-id="e025a-131">— Расположение</span><span class="sxs-lookup"><span data-stu-id="e025a-131">-Location</span></span>

<span data-ttu-id="e025a-132">Указывает текущее расположение источника пакета.</span><span class="sxs-lookup"><span data-stu-id="e025a-132">Specifies the current package source location.</span></span> <span data-ttu-id="e025a-133">Значением может быть URI, путь к файлу или любой другой формат назначения, поддерживаемый поставщиком пакетов.</span><span class="sxs-lookup"><span data-stu-id="e025a-133">The value can be a URI, a file path, or any other destination format supported by the package provider.</span></span>

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

### <span data-ttu-id="e025a-134">-Name</span><span class="sxs-lookup"><span data-stu-id="e025a-134">-Name</span></span>

<span data-ttu-id="e025a-135">Указывает имя источника пакета.</span><span class="sxs-lookup"><span data-stu-id="e025a-135">Specifies a package source's name.</span></span>

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

### <span data-ttu-id="e025a-136">-NewLocation</span><span class="sxs-lookup"><span data-stu-id="e025a-136">-NewLocation</span></span>

<span data-ttu-id="e025a-137">Указывает новое расположение для источника пакета.</span><span class="sxs-lookup"><span data-stu-id="e025a-137">Specifies the new location for a package source.</span></span> <span data-ttu-id="e025a-138">Значением может быть URI, путь к файлу или любой другой формат назначения, поддерживаемый поставщиком пакетов.</span><span class="sxs-lookup"><span data-stu-id="e025a-138">The value can be a URI, a file path, or any other destination format supported by the package provider.</span></span>

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

### <span data-ttu-id="e025a-139">-NewName</span><span class="sxs-lookup"><span data-stu-id="e025a-139">-NewName</span></span>

<span data-ttu-id="e025a-140">Указывает новое имя, назначаемое источнику пакета.</span><span class="sxs-lookup"><span data-stu-id="e025a-140">Specifies the new name you assign to a package source.</span></span>

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

### <span data-ttu-id="e025a-141">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="e025a-141">-PackageManagementProvider</span></span>

<span data-ttu-id="e025a-142">Указывает поставщика управления пакетами.</span><span class="sxs-lookup"><span data-stu-id="e025a-142">Specifies a package management provider.</span></span>

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

### <span data-ttu-id="e025a-143">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="e025a-143">-ProviderName</span></span>

<span data-ttu-id="e025a-144">Указывает имя поставщика.</span><span class="sxs-lookup"><span data-stu-id="e025a-144">Specifies a provider name.</span></span>

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

### <span data-ttu-id="e025a-145">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="e025a-145">-Proxy</span></span>

<span data-ttu-id="e025a-146">Указывает прокси-сервер для запроса, а не напрямуюе подключение к Интернет-ресурсу.</span><span class="sxs-lookup"><span data-stu-id="e025a-146">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

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

### <span data-ttu-id="e025a-147">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="e025a-147">-ProxyCredential</span></span>

<span data-ttu-id="e025a-148">Указывает учетную запись пользователя, имеющую разрешение на использование прокси-сервера, который задается параметром **Proxy**.</span><span class="sxs-lookup"><span data-stu-id="e025a-148">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="e025a-149">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="e025a-149">-PublishLocation</span></span>

<span data-ttu-id="e025a-150">Указывает расположение публикации.</span><span class="sxs-lookup"><span data-stu-id="e025a-150">Specifies the publish location.</span></span>

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

### <span data-ttu-id="e025a-151">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="e025a-151">-ScriptPublishLocation</span></span>

<span data-ttu-id="e025a-152">Указывает расположение публикации скрипта.</span><span class="sxs-lookup"><span data-stu-id="e025a-152">Specifies the script publish location.</span></span>

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

### <span data-ttu-id="e025a-153">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="e025a-153">-ScriptSourceLocation</span></span>

<span data-ttu-id="e025a-154">Указывает расположение источника скрипта.</span><span class="sxs-lookup"><span data-stu-id="e025a-154">Specifies the script source location.</span></span>

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

### <span data-ttu-id="e025a-155">-Скипвалидате</span><span class="sxs-lookup"><span data-stu-id="e025a-155">-SkipValidate</span></span>

<span data-ttu-id="e025a-156">Параметр, который пропускает проверку учетных данных источника пакета.</span><span class="sxs-lookup"><span data-stu-id="e025a-156">Switch that skips validating the credentials of a package source.</span></span>

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

### <span data-ttu-id="e025a-157">— Доверенный</span><span class="sxs-lookup"><span data-stu-id="e025a-157">-Trusted</span></span>

<span data-ttu-id="e025a-158">Указывает, что источником является доверенный поставщик пакетов.</span><span class="sxs-lookup"><span data-stu-id="e025a-158">Indicates that the source is a trusted package provider.</span></span> <span data-ttu-id="e025a-159">Надежные источники не запрашивают проверку для установки пакетов.</span><span class="sxs-lookup"><span data-stu-id="e025a-159">Trusted sources don't prompt for verification to install packages.</span></span>

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

### <span data-ttu-id="e025a-160">-Confirm</span><span class="sxs-lookup"><span data-stu-id="e025a-160">-Confirm</span></span>

<span data-ttu-id="e025a-161">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="e025a-161">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="e025a-162">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="e025a-162">-WhatIf</span></span>

<span data-ttu-id="e025a-163">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="e025a-163">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="e025a-164">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="e025a-164">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="e025a-165">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="e025a-165">CommonParameters</span></span>

<span data-ttu-id="e025a-166">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="e025a-166">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e025a-167">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="e025a-167">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e025a-168">Входные данные</span><span class="sxs-lookup"><span data-stu-id="e025a-168">INPUTS</span></span>

### <span data-ttu-id="e025a-169">`Set-PackageSource` не принимает входные данные конвейера.</span><span class="sxs-lookup"><span data-stu-id="e025a-169">`Set-PackageSource` doesn't accept pipeline input.</span></span>

## <span data-ttu-id="e025a-170">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="e025a-170">OUTPUTS</span></span>

### <span data-ttu-id="e025a-171">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="e025a-171">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="e025a-172">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="e025a-172">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e025a-173">Начиная с апреля 2020 года коллекция PowerShell не поддерживает протокол TLS (Transport Layer Security) версий 1.0 и 1.1.</span><span class="sxs-lookup"><span data-stu-id="e025a-173">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="e025a-174">Если вы не используете TLS 1.2 или более поздней версии, при попытке доступа к коллекции PowerShell возникнет ошибка.</span><span class="sxs-lookup"><span data-stu-id="e025a-174">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="e025a-175">Чтобы проверить, используется ли TLS 1.2, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e025a-175">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="e025a-176">Дополнительные сведения см. в [объявлении](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) в блоге, посвященном PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e025a-176">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="e025a-177">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="e025a-177">RELATED LINKS</span></span>

[<span data-ttu-id="e025a-178">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="e025a-178">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="e025a-179">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="e025a-179">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="e025a-180">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="e025a-180">Register-PackageSource</span></span>](Register-PackageSource.md)

[<span data-ttu-id="e025a-181">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="e025a-181">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)
