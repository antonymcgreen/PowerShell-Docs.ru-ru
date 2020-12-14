---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PackageManagement
ms.date: 04/03/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/set-packagesource?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PackageSource
ms.openlocfilehash: 4d534ebf97f7d7f37115e23f12cbd4d725e2212b
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "94889959"
---
# <span data-ttu-id="eaf40-103">Set-PackageSource</span><span class="sxs-lookup"><span data-stu-id="eaf40-103">Set-PackageSource</span></span>

## <span data-ttu-id="eaf40-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="eaf40-104">SYNOPSIS</span></span>
<span data-ttu-id="eaf40-105">Заменяет источник пакета для указанного поставщика пакетов.</span><span class="sxs-lookup"><span data-stu-id="eaf40-105">Replaces a package source for a specified package provider.</span></span>

## <span data-ttu-id="eaf40-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="eaf40-106">SYNTAX</span></span>

### <span data-ttu-id="eaf40-107">Саурцебисеарч (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="eaf40-107">SourceBySearch (Default)</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [[-Name] <String>] [-Location <String>] [-NewLocation <String>] [-NewName <String>] [-Trusted]
 [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-ProviderName <String>] [<CommonParameters>]
```

### <span data-ttu-id="eaf40-108">саурцебинпутобжект</span><span class="sxs-lookup"><span data-stu-id="eaf40-108">SourceByInputObject</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] -InputObject <PackageSource> [-Force]
 [-ForceBootstrap] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="eaf40-109">NuGet: Саурцебинпутобжект</span><span class="sxs-lookup"><span data-stu-id="eaf40-109">NuGet:SourceByInputObject</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### <span data-ttu-id="eaf40-110">NuGet: Саурцебисеарч</span><span class="sxs-lookup"><span data-stu-id="eaf40-110">NuGet:SourceBySearch</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### <span data-ttu-id="eaf40-111">PowerShellGet: Саурцебинпутобжект</span><span class="sxs-lookup"><span data-stu-id="eaf40-111">PowerShellGet:SourceByInputObject</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

### <span data-ttu-id="eaf40-112">PowerShellGet: Саурцебисеарч</span><span class="sxs-lookup"><span data-stu-id="eaf40-112">PowerShellGet:SourceBySearch</span></span>

```
Set-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>]
 [-NewLocation <String>] [-NewName <String>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

## <span data-ttu-id="eaf40-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="eaf40-113">DESCRIPTION</span></span>

<span data-ttu-id="eaf40-114">`Set-PackageSource`Заменяет источник пакета для указанного поставщика пакетов.</span><span class="sxs-lookup"><span data-stu-id="eaf40-114">The `Set-PackageSource` replaces a package source for a specified package provider.</span></span> <span data-ttu-id="eaf40-115">Источники пакетов всегда управляются поставщиком пакетов.</span><span class="sxs-lookup"><span data-stu-id="eaf40-115">Package sources are always managed by a package provider.</span></span>

## <span data-ttu-id="eaf40-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="eaf40-116">EXAMPLES</span></span>

### <span data-ttu-id="eaf40-117">Пример 1. изменение источника пакета</span><span class="sxs-lookup"><span data-stu-id="eaf40-117">Example 1: Change a package source</span></span>

<span data-ttu-id="eaf40-118">Эта команда изменяет существующее имя источника пакета.</span><span class="sxs-lookup"><span data-stu-id="eaf40-118">This command changes the existing name of a package source.</span></span> <span data-ttu-id="eaf40-119">Источнику присваивается значение **Trusted (доверенный**), что исключает запросы на проверку источника при установке пакетов.</span><span class="sxs-lookup"><span data-stu-id="eaf40-119">The source is set to **Trusted**, which eliminates prompts to verify the source when packages are installed.</span></span>

```
PS C:\> Set-PackageSource -Name MyNuget -NewName NewNuGet -Trusted -ProviderName NuGet
```

## <span data-ttu-id="eaf40-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="eaf40-120">PARAMETERS</span></span>

### <span data-ttu-id="eaf40-121">-ConfigFile</span><span class="sxs-lookup"><span data-stu-id="eaf40-121">-ConfigFile</span></span>

<span data-ttu-id="eaf40-122">Указывает файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="eaf40-122">Specifies a configuration file.</span></span>

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

### <span data-ttu-id="eaf40-123">-Credential</span><span class="sxs-lookup"><span data-stu-id="eaf40-123">-Credential</span></span>

<span data-ttu-id="eaf40-124">Указывает учетную запись пользователя, имеющую разрешение на установку поставщиков пакетов.</span><span class="sxs-lookup"><span data-stu-id="eaf40-124">Specifies a user account that has permission to install package providers.</span></span>

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

### <span data-ttu-id="eaf40-125">-Force</span><span class="sxs-lookup"><span data-stu-id="eaf40-125">-Force</span></span>

<span data-ttu-id="eaf40-126">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="eaf40-126">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="eaf40-127">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="eaf40-127">-ForceBootstrap</span></span>

<span data-ttu-id="eaf40-128">Указывает, что `Set-PackageSource` заставляет **PackageManagement** автоматически устанавливать поставщик пакетов.</span><span class="sxs-lookup"><span data-stu-id="eaf40-128">Indicates that `Set-PackageSource` forces **PackageManagement** to automatically install the package provider.</span></span>

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

### <span data-ttu-id="eaf40-129">-InputObject</span><span class="sxs-lookup"><span data-stu-id="eaf40-129">-InputObject</span></span>

<span data-ttu-id="eaf40-130">Указывает объект исходного идентификатора пакета, представляющий пакет, который необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="eaf40-130">Specifies a package source ID object that represents the package that you want to change.</span></span> <span data-ttu-id="eaf40-131">Идентификаторы источника пакета являются частью результатов `Get-PackageSource` командлета.</span><span class="sxs-lookup"><span data-stu-id="eaf40-131">Package source IDs are part of the results of the `Get-PackageSource` cmdlet.</span></span>

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

### <span data-ttu-id="eaf40-132">— Расположение</span><span class="sxs-lookup"><span data-stu-id="eaf40-132">-Location</span></span>

<span data-ttu-id="eaf40-133">Указывает текущее расположение источника пакета.</span><span class="sxs-lookup"><span data-stu-id="eaf40-133">Specifies the current package source location.</span></span> <span data-ttu-id="eaf40-134">Значением может быть URI, путь к файлу или любой другой формат назначения, поддерживаемый поставщиком пакетов.</span><span class="sxs-lookup"><span data-stu-id="eaf40-134">The value can be a URI, a file path, or any other destination format supported by the package provider.</span></span>

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

### <span data-ttu-id="eaf40-135">-Name</span><span class="sxs-lookup"><span data-stu-id="eaf40-135">-Name</span></span>

<span data-ttu-id="eaf40-136">Указывает имя источника пакета.</span><span class="sxs-lookup"><span data-stu-id="eaf40-136">Specifies a package source's name.</span></span>

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

### <span data-ttu-id="eaf40-137">-NewLocation</span><span class="sxs-lookup"><span data-stu-id="eaf40-137">-NewLocation</span></span>

<span data-ttu-id="eaf40-138">Указывает новое расположение для источника пакета.</span><span class="sxs-lookup"><span data-stu-id="eaf40-138">Specifies the new location for a package source.</span></span> <span data-ttu-id="eaf40-139">Значением может быть URI, путь к файлу или любой другой формат назначения, поддерживаемый поставщиком пакетов.</span><span class="sxs-lookup"><span data-stu-id="eaf40-139">The value can be a URI, a file path, or any other destination format supported by the package provider.</span></span>

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

### <span data-ttu-id="eaf40-140">-NewName</span><span class="sxs-lookup"><span data-stu-id="eaf40-140">-NewName</span></span>

<span data-ttu-id="eaf40-141">Указывает новое имя, назначаемое источнику пакета.</span><span class="sxs-lookup"><span data-stu-id="eaf40-141">Specifies the new name you assign to a package source.</span></span>

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

### <span data-ttu-id="eaf40-142">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="eaf40-142">-PackageManagementProvider</span></span>

<span data-ttu-id="eaf40-143">Указывает поставщика управления пакетами.</span><span class="sxs-lookup"><span data-stu-id="eaf40-143">Specifies a package management provider.</span></span>

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

### <span data-ttu-id="eaf40-144">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="eaf40-144">-ProviderName</span></span>

<span data-ttu-id="eaf40-145">Указывает имя поставщика.</span><span class="sxs-lookup"><span data-stu-id="eaf40-145">Specifies a provider name.</span></span>

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

### <span data-ttu-id="eaf40-146">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="eaf40-146">-Proxy</span></span>

<span data-ttu-id="eaf40-147">Указывает прокси-сервер для запроса, а не напрямуюе подключение к Интернет-ресурсу.</span><span class="sxs-lookup"><span data-stu-id="eaf40-147">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

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

### <span data-ttu-id="eaf40-148">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="eaf40-148">-ProxyCredential</span></span>

<span data-ttu-id="eaf40-149">Указывает учетную запись пользователя, имеющую разрешение на использование прокси-сервера, который задается параметром **Proxy**.</span><span class="sxs-lookup"><span data-stu-id="eaf40-149">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="eaf40-150">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="eaf40-150">-PublishLocation</span></span>

<span data-ttu-id="eaf40-151">Указывает расположение публикации.</span><span class="sxs-lookup"><span data-stu-id="eaf40-151">Specifies the publish location.</span></span>

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

### <span data-ttu-id="eaf40-152">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="eaf40-152">-ScriptPublishLocation</span></span>

<span data-ttu-id="eaf40-153">Указывает расположение публикации скрипта.</span><span class="sxs-lookup"><span data-stu-id="eaf40-153">Specifies the script publish location.</span></span>

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

### <span data-ttu-id="eaf40-154">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="eaf40-154">-ScriptSourceLocation</span></span>

<span data-ttu-id="eaf40-155">Указывает расположение источника скрипта.</span><span class="sxs-lookup"><span data-stu-id="eaf40-155">Specifies the script source location.</span></span>

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

### <span data-ttu-id="eaf40-156">-Скипвалидате</span><span class="sxs-lookup"><span data-stu-id="eaf40-156">-SkipValidate</span></span>

<span data-ttu-id="eaf40-157">Параметр, который пропускает проверку учетных данных источника пакета.</span><span class="sxs-lookup"><span data-stu-id="eaf40-157">Switch that skips validating the credentials of a package source.</span></span>

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

### <span data-ttu-id="eaf40-158">— Доверенный</span><span class="sxs-lookup"><span data-stu-id="eaf40-158">-Trusted</span></span>

<span data-ttu-id="eaf40-159">Указывает, что источником является доверенный поставщик пакетов.</span><span class="sxs-lookup"><span data-stu-id="eaf40-159">Indicates that the source is a trusted package provider.</span></span> <span data-ttu-id="eaf40-160">Надежные источники не запрашивают проверку для установки пакетов.</span><span class="sxs-lookup"><span data-stu-id="eaf40-160">Trusted sources don't prompt for verification to install packages.</span></span>

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

### <span data-ttu-id="eaf40-161">-Confirm</span><span class="sxs-lookup"><span data-stu-id="eaf40-161">-Confirm</span></span>

<span data-ttu-id="eaf40-162">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="eaf40-162">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="eaf40-163">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="eaf40-163">-WhatIf</span></span>

<span data-ttu-id="eaf40-164">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="eaf40-164">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="eaf40-165">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="eaf40-165">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="eaf40-166">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="eaf40-166">CommonParameters</span></span>

<span data-ttu-id="eaf40-167">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="eaf40-167">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="eaf40-168">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="eaf40-168">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="eaf40-169">Входные данные</span><span class="sxs-lookup"><span data-stu-id="eaf40-169">INPUTS</span></span>

### <span data-ttu-id="eaf40-170">`Set-PackageSource` не принимает входные данные конвейера.</span><span class="sxs-lookup"><span data-stu-id="eaf40-170">`Set-PackageSource` doesn't accept pipeline input.</span></span>

## <span data-ttu-id="eaf40-171">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="eaf40-171">OUTPUTS</span></span>

### <span data-ttu-id="eaf40-172">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="eaf40-172">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="eaf40-173">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="eaf40-173">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eaf40-174">По состоянию на апрель 2020 коллекция PowerShell больше не поддерживает TLS-версии 1,0 и 1,1.</span><span class="sxs-lookup"><span data-stu-id="eaf40-174">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="eaf40-175">Если вы не используете TLS 1,2 или более поздней версии, при попытке доступа к коллекция PowerShell возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="eaf40-175">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="eaf40-176">Используйте следующую команду, чтобы убедиться, что используется TLS 1,2:</span><span class="sxs-lookup"><span data-stu-id="eaf40-176">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="eaf40-177">Дополнительные сведения см. в [объявлении](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) в блоге PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eaf40-177">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="eaf40-178">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="eaf40-178">RELATED LINKS</span></span>

[<span data-ttu-id="eaf40-179">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="eaf40-179">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="eaf40-180">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="eaf40-180">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="eaf40-181">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="eaf40-181">Register-PackageSource</span></span>](Register-PackageSource.md)

[<span data-ttu-id="eaf40-182">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="eaf40-182">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)
