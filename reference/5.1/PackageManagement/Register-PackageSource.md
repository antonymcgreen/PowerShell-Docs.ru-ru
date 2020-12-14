---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PackageManagement
ms.date: 04/01/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/register-packagesource?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-PackageSource
ms.openlocfilehash: 323d59724507cfec5cde086e3b8e2a2c2f34b96e
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "94891318"
---
# <span data-ttu-id="9a8d9-103">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="9a8d9-103">Register-PackageSource</span></span>

## <span data-ttu-id="9a8d9-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="9a8d9-104">SYNOPSIS</span></span>
<span data-ttu-id="9a8d9-105">Добавляет источник пакета для указанного поставщика пакетов.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-105">Adds a package source for a specified package provider.</span></span>

## <span data-ttu-id="9a8d9-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9a8d9-106">SYNTAX</span></span>

### <span data-ttu-id="9a8d9-107">саурцебисеарч</span><span class="sxs-lookup"><span data-stu-id="9a8d9-107">SourceBySearch</span></span>

```
Register-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [[-Name] <String>]
 [[-Location] <String>] [-Credential <PSCredential>] [-Trusted] [-Force] [-ForceBootstrap]
 [-WhatIf] [-Confirm] [-ProviderName <String>] [<CommonParameters>]
```

### <span data-ttu-id="9a8d9-108">NuGet</span><span class="sxs-lookup"><span data-stu-id="9a8d9-108">NuGet</span></span>

```
Register-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [[-Name] <String>]
 [[-Location] <String>] [-Credential <PSCredential>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### <span data-ttu-id="9a8d9-109">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="9a8d9-109">PowerShellGet</span></span>

```
Register-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [[-Name] <String>]
 [[-Location] <String>] [-Credential <PSCredential>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

## <span data-ttu-id="9a8d9-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9a8d9-110">DESCRIPTION</span></span>

<span data-ttu-id="9a8d9-111">`Register-PackageSource`Командлет добавляет источник пакета для указанного поставщика пакетов.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-111">The `Register-PackageSource` cmdlet adds a package source for a specified package provider.</span></span> <span data-ttu-id="9a8d9-112">Источники пакетов всегда управляются поставщиком пакетов.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-112">Package sources are always managed by a package provider.</span></span> <span data-ttu-id="9a8d9-113">Если поставщик пакетов не может добавить или заменить источник пакета, поставщик выдает сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-113">If the package provider cannot add or replace a package source, the provider generates an error message.</span></span>

## <span data-ttu-id="9a8d9-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="9a8d9-114">EXAMPLES</span></span>

### <span data-ttu-id="9a8d9-115">Пример 1. регистрация источника пакета для поставщика NuGet</span><span class="sxs-lookup"><span data-stu-id="9a8d9-115">Example 1: Register a package source for the NuGet provider</span></span>

<span data-ttu-id="9a8d9-116">Эта команда регистрирует источник пакета, веб-расположение для поставщика **NuGet** .</span><span class="sxs-lookup"><span data-stu-id="9a8d9-116">This command registers a package source, a web-based location for the **NuGet** provider.</span></span> <span data-ttu-id="9a8d9-117">По умолчанию источники не являются доверенными.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-117">By default, sources aren't trusted.</span></span> <span data-ttu-id="9a8d9-118">Перед установкой пакетов вам будет предложено подтвердить, что источник является доверенным.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-118">You are prompted to confirm the source is trusted before packages are installed.</span></span> <span data-ttu-id="9a8d9-119">Чтобы переопределить значение по умолчанию, используйте `-Trusted` параметр.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-119">To override the default, use the `-Trusted` parameter.</span></span>

```powershell
Register-PackageSource -Name MyNuGet -Location https://www.nuget.org/api/v2 -ProviderName NuGet
```

```Output
Name          ProviderName     IsTrusted  Location
----          ------------     ---------  --------
MyNuGet       NuGet            False      https://www.nuget.org/api/v2
```

## <span data-ttu-id="9a8d9-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9a8d9-120">PARAMETERS</span></span>

### <span data-ttu-id="9a8d9-121">-ConfigFile</span><span class="sxs-lookup"><span data-stu-id="9a8d9-121">-ConfigFile</span></span>

<span data-ttu-id="9a8d9-122">Указывает файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-122">Specifies a configuration file.</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9a8d9-123">-Credential</span><span class="sxs-lookup"><span data-stu-id="9a8d9-123">-Credential</span></span>

<span data-ttu-id="9a8d9-124">Указывает учетную запись пользователя, имеющую разрешение на доступ к расположению, прошедшему проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-124">Specifies a user account that has permission to access the authenticated location.</span></span>

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

### <span data-ttu-id="9a8d9-125">-Force</span><span class="sxs-lookup"><span data-stu-id="9a8d9-125">-Force</span></span>

<span data-ttu-id="9a8d9-126">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-126">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="9a8d9-127">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="9a8d9-127">-ForceBootstrap</span></span>

<span data-ttu-id="9a8d9-128">Указывает, что этот командлет автоматически устанавливает поставщик пакетов.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-128">Indicates that this cmdlet automatically installs the package provider.</span></span>

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

### <span data-ttu-id="9a8d9-129">— Расположение</span><span class="sxs-lookup"><span data-stu-id="9a8d9-129">-Location</span></span>

<span data-ttu-id="9a8d9-130">Указывает расположение источника пакета.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-130">Specifies the package source location.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9a8d9-131">-Name</span><span class="sxs-lookup"><span data-stu-id="9a8d9-131">-Name</span></span>

<span data-ttu-id="9a8d9-132">Указывает имя регистрируемого источника пакета.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-132">Specifies the name of the package source to register.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9a8d9-133">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="9a8d9-133">-PackageManagementProvider</span></span>

<span data-ttu-id="9a8d9-134">Указывает поставщика Управление пакетами.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-134">Specifies the Package Management provider.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9a8d9-135">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="9a8d9-135">-ProviderName</span></span>

<span data-ttu-id="9a8d9-136">Указывает имя поставщика пакета.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-136">Specifies the package provider's name.</span></span>

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

### <span data-ttu-id="9a8d9-137">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="9a8d9-137">-Proxy</span></span>

<span data-ttu-id="9a8d9-138">Указывает прокси-сервер для запроса, а не прямое подключение к Интернету.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-138">Specifies a proxy server for the request, rather than a direct connection to the internet resource.</span></span>

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

### <span data-ttu-id="9a8d9-139">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="9a8d9-139">-ProxyCredential</span></span>

<span data-ttu-id="9a8d9-140">Указывает учетную запись пользователя, имеющую разрешение на использование прокси-сервера, который задается параметром **Proxy**.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-140">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="9a8d9-141">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="9a8d9-141">-PublishLocation</span></span>

<span data-ttu-id="9a8d9-142">Указывает расположение публикации.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-142">Specifies the publish location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9a8d9-143">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="9a8d9-143">-ScriptPublishLocation</span></span>

<span data-ttu-id="9a8d9-144">Указывает расположение публикации скрипта.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-144">Specifies the script publish location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9a8d9-145">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="9a8d9-145">-ScriptSourceLocation</span></span>

<span data-ttu-id="9a8d9-146">Указывает расположение источника скрипта.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-146">Specifies the script source location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9a8d9-147">-Скипвалидате</span><span class="sxs-lookup"><span data-stu-id="9a8d9-147">-SkipValidate</span></span>

<span data-ttu-id="9a8d9-148">Параметр, который пропускает проверку учетных данных источника пакета.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-148">Switch that skips validating the credentials of a package source.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9a8d9-149">— Доверенный</span><span class="sxs-lookup"><span data-stu-id="9a8d9-149">-Trusted</span></span>

<span data-ttu-id="9a8d9-150">Указывает, что источник пакета является доверенным.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-150">Indicates that the package source is trusted.</span></span>

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

### <span data-ttu-id="9a8d9-151">-Confirm</span><span class="sxs-lookup"><span data-stu-id="9a8d9-151">-Confirm</span></span>

<span data-ttu-id="9a8d9-152">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-152">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="9a8d9-153">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="9a8d9-153">-WhatIf</span></span>

<span data-ttu-id="9a8d9-154">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-154">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="9a8d9-155">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-155">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="9a8d9-156">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="9a8d9-156">CommonParameters</span></span>

<span data-ttu-id="9a8d9-157">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9a8d9-158">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9a8d9-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9a8d9-159">Входные данные</span><span class="sxs-lookup"><span data-stu-id="9a8d9-159">INPUTS</span></span>

## <span data-ttu-id="9a8d9-160">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="9a8d9-160">OUTPUTS</span></span>

## <span data-ttu-id="9a8d9-161">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="9a8d9-161">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9a8d9-162">По состоянию на апрель 2020 коллекция PowerShell больше не поддерживает TLS-версии 1,0 и 1,1.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-162">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="9a8d9-163">Если вы не используете TLS 1,2 или более поздней версии, при попытке доступа к коллекция PowerShell возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-163">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="9a8d9-164">Используйте следующую команду, чтобы убедиться, что используется TLS 1,2:</span><span class="sxs-lookup"><span data-stu-id="9a8d9-164">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="9a8d9-165">Дополнительные сведения см. в [объявлении](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) в блоге PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-165">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="9a8d9-166">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="9a8d9-166">RELATED LINKS</span></span>

[<span data-ttu-id="9a8d9-167">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="9a8d9-167">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="9a8d9-168">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="9a8d9-168">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="9a8d9-169">Set-PackageSource</span><span class="sxs-lookup"><span data-stu-id="9a8d9-169">Set-PackageSource</span></span>](Set-PackageSource.md)

[<span data-ttu-id="9a8d9-170">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="9a8d9-170">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)
