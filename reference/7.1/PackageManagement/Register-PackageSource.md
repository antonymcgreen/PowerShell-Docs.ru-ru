---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PackageManagement
ms.date: 04/01/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/register-packagesource?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-PackageSource
ms.openlocfilehash: 8b57540658a88fa56533c3f5c360273913c3543b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228554"
---
# <span data-ttu-id="d65a3-103">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="d65a3-103">Register-PackageSource</span></span>

## <span data-ttu-id="d65a3-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="d65a3-104">SYNOPSIS</span></span>
<span data-ttu-id="d65a3-105">Добавляет источник пакета для указанного поставщика пакетов.</span><span class="sxs-lookup"><span data-stu-id="d65a3-105">Adds a package source for a specified package provider.</span></span>

## <span data-ttu-id="d65a3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d65a3-106">SYNTAX</span></span>

### <span data-ttu-id="d65a3-107">саурцебисеарч</span><span class="sxs-lookup"><span data-stu-id="d65a3-107">SourceBySearch</span></span>

```
Register-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [[-Name] <String>]
 [[-Location] <String>] [-Credential <PSCredential>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-ProviderName <String>] [<CommonParameters>]
```

### <span data-ttu-id="d65a3-108">NuGet</span><span class="sxs-lookup"><span data-stu-id="d65a3-108">NuGet</span></span>

```
Register-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [[-Name] <String>]
 [[-Location] <String>] [-Credential <PSCredential>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### <span data-ttu-id="d65a3-109">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="d65a3-109">PowerShellGet</span></span>

```
Register-PackageSource [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [[-Name] <String>]
 [[-Location] <String>] [-Credential <PSCredential>] [-Trusted] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

## <span data-ttu-id="d65a3-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d65a3-110">DESCRIPTION</span></span>

<span data-ttu-id="d65a3-111">`Register-PackageSource`Командлет добавляет источник пакета для указанного поставщика пакетов.</span><span class="sxs-lookup"><span data-stu-id="d65a3-111">The `Register-PackageSource` cmdlet adds a package source for a specified package provider.</span></span> <span data-ttu-id="d65a3-112">Источники пакетов всегда управляются поставщиком пакетов.</span><span class="sxs-lookup"><span data-stu-id="d65a3-112">Package sources are always managed by a package provider.</span></span> <span data-ttu-id="d65a3-113">Если поставщик пакетов не может добавить или заменить источник пакета, поставщик выдает сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="d65a3-113">If the package provider cannot add or replace a package source, the provider generates an error message.</span></span>

## <span data-ttu-id="d65a3-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="d65a3-114">EXAMPLES</span></span>

### <span data-ttu-id="d65a3-115">Пример 1. регистрация источника пакета для поставщика NuGet</span><span class="sxs-lookup"><span data-stu-id="d65a3-115">Example 1: Register a package source for the NuGet provider</span></span>

<span data-ttu-id="d65a3-116">Эта команда регистрирует источник пакета, веб-расположение для поставщика **NuGet** .</span><span class="sxs-lookup"><span data-stu-id="d65a3-116">This command registers a package source, a web-based location for the **NuGet** provider.</span></span> <span data-ttu-id="d65a3-117">По умолчанию источники не являются доверенными.</span><span class="sxs-lookup"><span data-stu-id="d65a3-117">By default, sources aren't trusted.</span></span> <span data-ttu-id="d65a3-118">Перед установкой пакетов вам будет предложено подтвердить, что источник является доверенным.</span><span class="sxs-lookup"><span data-stu-id="d65a3-118">You are prompted to confirm the source is trusted before packages are installed.</span></span> <span data-ttu-id="d65a3-119">Чтобы переопределить значение по умолчанию, используйте `-Trusted` параметр.</span><span class="sxs-lookup"><span data-stu-id="d65a3-119">To override the default, use the `-Trusted` parameter.</span></span>

```powershell
Register-PackageSource -Name MyNuGet -Location https://www.nuget.org/api/v2 -ProviderName NuGet
```

```Output
Name          ProviderName     IsTrusted  Location
----          ------------     ---------  --------
MyNuGet       NuGet            False      https://www.nuget.org/api/v2
```

## <span data-ttu-id="d65a3-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d65a3-120">PARAMETERS</span></span>

### <span data-ttu-id="d65a3-121">-ConfigFile</span><span class="sxs-lookup"><span data-stu-id="d65a3-121">-ConfigFile</span></span>

<span data-ttu-id="d65a3-122">Указывает файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d65a3-122">Specifies a configuration file.</span></span>

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

### <span data-ttu-id="d65a3-123">-Credential</span><span class="sxs-lookup"><span data-stu-id="d65a3-123">-Credential</span></span>

<span data-ttu-id="d65a3-124">Указывает учетную запись пользователя, имеющую разрешение на доступ к расположению, прошедшему проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="d65a3-124">Specifies a user account that has permission to access the authenticated location.</span></span>

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

### <span data-ttu-id="d65a3-125">-Force</span><span class="sxs-lookup"><span data-stu-id="d65a3-125">-Force</span></span>

<span data-ttu-id="d65a3-126">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="d65a3-126">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="d65a3-127">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="d65a3-127">-ForceBootstrap</span></span>

<span data-ttu-id="d65a3-128">Указывает, что этот командлет автоматически устанавливает поставщик пакетов.</span><span class="sxs-lookup"><span data-stu-id="d65a3-128">Indicates that this cmdlet automatically installs the package provider.</span></span>

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

### <span data-ttu-id="d65a3-129">— Расположение</span><span class="sxs-lookup"><span data-stu-id="d65a3-129">-Location</span></span>

<span data-ttu-id="d65a3-130">Указывает расположение источника пакета.</span><span class="sxs-lookup"><span data-stu-id="d65a3-130">Specifies the package source location.</span></span>

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

### <span data-ttu-id="d65a3-131">-Name</span><span class="sxs-lookup"><span data-stu-id="d65a3-131">-Name</span></span>

<span data-ttu-id="d65a3-132">Указывает имя регистрируемого источника пакета.</span><span class="sxs-lookup"><span data-stu-id="d65a3-132">Specifies the name of the package source to register.</span></span>

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

### <span data-ttu-id="d65a3-133">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="d65a3-133">-PackageManagementProvider</span></span>

<span data-ttu-id="d65a3-134">Указывает поставщика Управление пакетами.</span><span class="sxs-lookup"><span data-stu-id="d65a3-134">Specifies the Package Management provider.</span></span>

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

### <span data-ttu-id="d65a3-135">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="d65a3-135">-ProviderName</span></span>

<span data-ttu-id="d65a3-136">Указывает имя поставщика пакета.</span><span class="sxs-lookup"><span data-stu-id="d65a3-136">Specifies the package provider's name.</span></span>

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

### <span data-ttu-id="d65a3-137">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="d65a3-137">-Proxy</span></span>

<span data-ttu-id="d65a3-138">Указывает прокси-сервер для запроса, а не прямое подключение к Интернету.</span><span class="sxs-lookup"><span data-stu-id="d65a3-138">Specifies a proxy server for the request, rather than a direct connection to the internet resource.</span></span>

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

### <span data-ttu-id="d65a3-139">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="d65a3-139">-ProxyCredential</span></span>

<span data-ttu-id="d65a3-140">Указывает учетную запись пользователя, имеющую разрешение на использование прокси-сервера, который задается параметром **Proxy** .</span><span class="sxs-lookup"><span data-stu-id="d65a3-140">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="d65a3-141">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="d65a3-141">-PublishLocation</span></span>

<span data-ttu-id="d65a3-142">Указывает расположение публикации.</span><span class="sxs-lookup"><span data-stu-id="d65a3-142">Specifies the publish location.</span></span>

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

### <span data-ttu-id="d65a3-143">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="d65a3-143">-ScriptPublishLocation</span></span>

<span data-ttu-id="d65a3-144">Указывает расположение публикации скрипта.</span><span class="sxs-lookup"><span data-stu-id="d65a3-144">Specifies the script publish location.</span></span>

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

### <span data-ttu-id="d65a3-145">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="d65a3-145">-ScriptSourceLocation</span></span>

<span data-ttu-id="d65a3-146">Указывает расположение источника скрипта.</span><span class="sxs-lookup"><span data-stu-id="d65a3-146">Specifies the script source location.</span></span>

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

### <span data-ttu-id="d65a3-147">-Скипвалидате</span><span class="sxs-lookup"><span data-stu-id="d65a3-147">-SkipValidate</span></span>

<span data-ttu-id="d65a3-148">Параметр, который пропускает проверку учетных данных источника пакета.</span><span class="sxs-lookup"><span data-stu-id="d65a3-148">Switch that skips validating the credentials of a package source.</span></span>

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

### <span data-ttu-id="d65a3-149">— Доверенный</span><span class="sxs-lookup"><span data-stu-id="d65a3-149">-Trusted</span></span>

<span data-ttu-id="d65a3-150">Указывает, что источник пакета является доверенным.</span><span class="sxs-lookup"><span data-stu-id="d65a3-150">Indicates that the package source is trusted.</span></span>

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

### <span data-ttu-id="d65a3-151">-Confirm</span><span class="sxs-lookup"><span data-stu-id="d65a3-151">-Confirm</span></span>

<span data-ttu-id="d65a3-152">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="d65a3-152">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="d65a3-153">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="d65a3-153">-WhatIf</span></span>

<span data-ttu-id="d65a3-154">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="d65a3-154">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="d65a3-155">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="d65a3-155">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="d65a3-156">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="d65a3-156">CommonParameters</span></span>

<span data-ttu-id="d65a3-157">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d65a3-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d65a3-158">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d65a3-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d65a3-159">Входные данные</span><span class="sxs-lookup"><span data-stu-id="d65a3-159">INPUTS</span></span>

## <span data-ttu-id="d65a3-160">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="d65a3-160">OUTPUTS</span></span>

## <span data-ttu-id="d65a3-161">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="d65a3-161">NOTES</span></span>

## <span data-ttu-id="d65a3-162">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="d65a3-162">RELATED LINKS</span></span>

[<span data-ttu-id="d65a3-163">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="d65a3-163">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="d65a3-164">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="d65a3-164">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="d65a3-165">Set-PackageSource</span><span class="sxs-lookup"><span data-stu-id="d65a3-165">Set-PackageSource</span></span>](Set-PackageSource.md)

[<span data-ttu-id="d65a3-166">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="d65a3-166">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)

