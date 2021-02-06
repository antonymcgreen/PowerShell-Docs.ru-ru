---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
Locale: en-US
Module Name: PackageManagement
ms.date: 04/01/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/register-packagesource?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-PackageSource
ms.openlocfilehash: 76b3bd49f81f42cc80f4127f4b549acddcd1d906
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "99599402"
---
# <span data-ttu-id="5d827-102">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="5d827-102">Register-PackageSource</span></span>

## <span data-ttu-id="5d827-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="5d827-103">SYNOPSIS</span></span>
<span data-ttu-id="5d827-104">Добавляет источник пакета для указанного поставщика пакетов.</span><span class="sxs-lookup"><span data-stu-id="5d827-104">Adds a package source for a specified package provider.</span></span>

## <span data-ttu-id="5d827-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5d827-105">SYNTAX</span></span>

### <span data-ttu-id="5d827-106">саурцебисеарч</span><span class="sxs-lookup"><span data-stu-id="5d827-106">SourceBySearch</span></span>

```
Register-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [[-Name] <String>]
 [[-Location] <String>] [-Credential <PSCredential>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-ProviderName <String>] [<CommonParameters>]
```

### <span data-ttu-id="5d827-107">NuGet</span><span class="sxs-lookup"><span data-stu-id="5d827-107">NuGet</span></span>

```
Register-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [[-Name] <String>]
 [[-Location] <String>] [-Credential <PSCredential>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### <span data-ttu-id="5d827-108">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="5d827-108">PowerShellGet</span></span>

```
Register-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [[-Name] <String>]
 [[-Location] <String>] [-Credential <PSCredential>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

## <span data-ttu-id="5d827-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5d827-109">DESCRIPTION</span></span>

<span data-ttu-id="5d827-110">`Register-PackageSource`Командлет добавляет источник пакета для указанного поставщика пакетов.</span><span class="sxs-lookup"><span data-stu-id="5d827-110">The `Register-PackageSource` cmdlet adds a package source for a specified package provider.</span></span> <span data-ttu-id="5d827-111">Источники пакетов всегда управляются поставщиком пакетов.</span><span class="sxs-lookup"><span data-stu-id="5d827-111">Package sources are always managed by a package provider.</span></span> <span data-ttu-id="5d827-112">Если поставщик пакетов не может добавить или заменить источник пакета, поставщик выдает сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="5d827-112">If the package provider cannot add or replace a package source, the provider generates an error message.</span></span>

## <span data-ttu-id="5d827-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="5d827-113">EXAMPLES</span></span>

### <span data-ttu-id="5d827-114">Пример 1. регистрация источника пакета для поставщика NuGet</span><span class="sxs-lookup"><span data-stu-id="5d827-114">Example 1: Register a package source for the NuGet provider</span></span>

<span data-ttu-id="5d827-115">Эта команда регистрирует источник пакета, веб-расположение для поставщика **NuGet** .</span><span class="sxs-lookup"><span data-stu-id="5d827-115">This command registers a package source, a web-based location for the **NuGet** provider.</span></span> <span data-ttu-id="5d827-116">По умолчанию источники не являются доверенными.</span><span class="sxs-lookup"><span data-stu-id="5d827-116">By default, sources aren't trusted.</span></span> <span data-ttu-id="5d827-117">Перед установкой пакетов вам будет предложено подтвердить, что источник является доверенным.</span><span class="sxs-lookup"><span data-stu-id="5d827-117">You are prompted to confirm the source is trusted before packages are installed.</span></span> <span data-ttu-id="5d827-118">Чтобы переопределить значение по умолчанию, используйте `-Trusted` параметр.</span><span class="sxs-lookup"><span data-stu-id="5d827-118">To override the default, use the `-Trusted` parameter.</span></span>

```powershell
Register-PackageSource -Name MyNuGet -Location https://www.nuget.org/api/v2 -ProviderName NuGet
```

```Output
Name          ProviderName     IsTrusted  Location
----          ------------     ---------  --------
MyNuGet       NuGet            False      https://www.nuget.org/api/v2
```

## <span data-ttu-id="5d827-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5d827-119">PARAMETERS</span></span>

### <span data-ttu-id="5d827-120">-ConfigFile</span><span class="sxs-lookup"><span data-stu-id="5d827-120">-ConfigFile</span></span>

<span data-ttu-id="5d827-121">Указывает файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="5d827-121">Specifies a configuration file.</span></span>

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

### <span data-ttu-id="5d827-122">-Credential</span><span class="sxs-lookup"><span data-stu-id="5d827-122">-Credential</span></span>

<span data-ttu-id="5d827-123">Указывает учетную запись пользователя, имеющую разрешение на доступ к расположению, прошедшему проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="5d827-123">Specifies a user account that has permission to access the authenticated location.</span></span>

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

### <span data-ttu-id="5d827-124">-Force</span><span class="sxs-lookup"><span data-stu-id="5d827-124">-Force</span></span>

<span data-ttu-id="5d827-125">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="5d827-125">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="5d827-126">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="5d827-126">-ForceBootstrap</span></span>

<span data-ttu-id="5d827-127">Указывает, что этот командлет автоматически устанавливает поставщик пакетов.</span><span class="sxs-lookup"><span data-stu-id="5d827-127">Indicates that this cmdlet automatically installs the package provider.</span></span>

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

### <span data-ttu-id="5d827-128">— Расположение</span><span class="sxs-lookup"><span data-stu-id="5d827-128">-Location</span></span>

<span data-ttu-id="5d827-129">Указывает расположение источника пакета.</span><span class="sxs-lookup"><span data-stu-id="5d827-129">Specifies the package source location.</span></span>

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

### <span data-ttu-id="5d827-130">-Name</span><span class="sxs-lookup"><span data-stu-id="5d827-130">-Name</span></span>

<span data-ttu-id="5d827-131">Указывает имя регистрируемого источника пакета.</span><span class="sxs-lookup"><span data-stu-id="5d827-131">Specifies the name of the package source to register.</span></span>

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

### <span data-ttu-id="5d827-132">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="5d827-132">-PackageManagementProvider</span></span>

<span data-ttu-id="5d827-133">Указывает поставщика Управление пакетами.</span><span class="sxs-lookup"><span data-stu-id="5d827-133">Specifies the Package Management provider.</span></span>

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

### <span data-ttu-id="5d827-134">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="5d827-134">-ProviderName</span></span>

<span data-ttu-id="5d827-135">Указывает имя поставщика пакета.</span><span class="sxs-lookup"><span data-stu-id="5d827-135">Specifies the package provider's name.</span></span>

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

### <span data-ttu-id="5d827-136">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="5d827-136">-Proxy</span></span>

<span data-ttu-id="5d827-137">Указывает прокси-сервер для запроса, а не прямое подключение к Интернету.</span><span class="sxs-lookup"><span data-stu-id="5d827-137">Specifies a proxy server for the request, rather than a direct connection to the internet resource.</span></span>

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

### <span data-ttu-id="5d827-138">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="5d827-138">-ProxyCredential</span></span>

<span data-ttu-id="5d827-139">Указывает учетную запись пользователя, имеющую разрешение на использование прокси-сервера, который задается параметром **Proxy**.</span><span class="sxs-lookup"><span data-stu-id="5d827-139">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="5d827-140">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="5d827-140">-PublishLocation</span></span>

<span data-ttu-id="5d827-141">Указывает расположение публикации.</span><span class="sxs-lookup"><span data-stu-id="5d827-141">Specifies the publish location.</span></span>

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

### <span data-ttu-id="5d827-142">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="5d827-142">-ScriptPublishLocation</span></span>

<span data-ttu-id="5d827-143">Указывает расположение публикации скрипта.</span><span class="sxs-lookup"><span data-stu-id="5d827-143">Specifies the script publish location.</span></span>

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

### <span data-ttu-id="5d827-144">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="5d827-144">-ScriptSourceLocation</span></span>

<span data-ttu-id="5d827-145">Указывает расположение источника скрипта.</span><span class="sxs-lookup"><span data-stu-id="5d827-145">Specifies the script source location.</span></span>

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

### <span data-ttu-id="5d827-146">-Скипвалидате</span><span class="sxs-lookup"><span data-stu-id="5d827-146">-SkipValidate</span></span>

<span data-ttu-id="5d827-147">Параметр, который пропускает проверку учетных данных источника пакета.</span><span class="sxs-lookup"><span data-stu-id="5d827-147">Switch that skips validating the credentials of a package source.</span></span>

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

### <span data-ttu-id="5d827-148">— Доверенный</span><span class="sxs-lookup"><span data-stu-id="5d827-148">-Trusted</span></span>

<span data-ttu-id="5d827-149">Указывает, что источник пакета является доверенным.</span><span class="sxs-lookup"><span data-stu-id="5d827-149">Indicates that the package source is trusted.</span></span>

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

### <span data-ttu-id="5d827-150">-Confirm</span><span class="sxs-lookup"><span data-stu-id="5d827-150">-Confirm</span></span>

<span data-ttu-id="5d827-151">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="5d827-151">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="5d827-152">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="5d827-152">-WhatIf</span></span>

<span data-ttu-id="5d827-153">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="5d827-153">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="5d827-154">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="5d827-154">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="5d827-155">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="5d827-155">CommonParameters</span></span>

<span data-ttu-id="5d827-156">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5d827-156">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5d827-157">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5d827-157">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5d827-158">Входные данные</span><span class="sxs-lookup"><span data-stu-id="5d827-158">INPUTS</span></span>

## <span data-ttu-id="5d827-159">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="5d827-159">OUTPUTS</span></span>

## <span data-ttu-id="5d827-160">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="5d827-160">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5d827-161">Начиная с апреля 2020 года коллекция PowerShell не поддерживает протокол TLS (Transport Layer Security) версий 1.0 и 1.1.</span><span class="sxs-lookup"><span data-stu-id="5d827-161">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="5d827-162">Если вы не используете TLS 1.2 или более поздней версии, при попытке доступа к коллекции PowerShell возникнет ошибка.</span><span class="sxs-lookup"><span data-stu-id="5d827-162">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="5d827-163">Чтобы проверить, используется ли TLS 1.2, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5d827-163">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="5d827-164">Дополнительные сведения см. в [объявлении](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) в блоге, посвященном PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5d827-164">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="5d827-165">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="5d827-165">RELATED LINKS</span></span>

[<span data-ttu-id="5d827-166">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="5d827-166">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="5d827-167">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="5d827-167">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="5d827-168">Set-PackageSource</span><span class="sxs-lookup"><span data-stu-id="5d827-168">Set-PackageSource</span></span>](Set-PackageSource.md)

[<span data-ttu-id="5d827-169">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="5d827-169">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)
