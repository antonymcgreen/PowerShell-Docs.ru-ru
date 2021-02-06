---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
Locale: en-US
Module Name: PackageManagement
ms.date: 03/29/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/get-packagesource?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PackageSource
ms.openlocfilehash: 8b91c5b950e0e16c4ce0821ee2f96b830dab1fc2
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "99600680"
---
# <span data-ttu-id="a6f8d-102">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="a6f8d-102">Get-PackageSource</span></span>

## <span data-ttu-id="a6f8d-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="a6f8d-103">SYNOPSIS</span></span>
<span data-ttu-id="a6f8d-104">Возвращает список источников пакетов, зарегистрированных для поставщика пакетов.</span><span class="sxs-lookup"><span data-stu-id="a6f8d-104">Gets a list of package sources that are registered for a package provider.</span></span>

## <span data-ttu-id="a6f8d-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a6f8d-105">SYNTAX</span></span>

### <span data-ttu-id="a6f8d-106">NuGet</span><span class="sxs-lookup"><span data-stu-id="a6f8d-106">NuGet</span></span>

```
Get-PackageSource [[-Name] <String>] [-Location <String>] [-Force] [-ForceBootstrap]
 [-ProviderName <String[]>] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### <span data-ttu-id="a6f8d-107">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="a6f8d-107">PowerShellGet</span></span>

```
Get-PackageSource [[-Name] <String>] [-Location <String>] [-Force] [-ForceBootstrap]
 [-ProviderName <String[]>] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

## <span data-ttu-id="a6f8d-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a6f8d-108">DESCRIPTION</span></span>

<span data-ttu-id="a6f8d-109">`Get-PackageSource`Командлет возвращает список источников пакетов, зарегистрированных с помощью **PackageManagement** , на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a6f8d-109">The `Get-PackageSource` cmdlet gets a list of package sources that are registered with **PackageManagement** on the local computer.</span></span> <span data-ttu-id="a6f8d-110">При указании поставщика пакетов `Get-PackageSource` получает только те источники, которые связаны с указанным поставщиком.</span><span class="sxs-lookup"><span data-stu-id="a6f8d-110">If you specify a package provider, `Get-PackageSource` gets only those sources that are associated with the specified provider.</span></span> <span data-ttu-id="a6f8d-111">В противном случае команда возвращает все источники пакетов, зарегистрированные с помощью **PackageManagement**.</span><span class="sxs-lookup"><span data-stu-id="a6f8d-111">Otherwise, the command returns all package sources that are registered with **PackageManagement**.</span></span>

## <span data-ttu-id="a6f8d-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="a6f8d-112">EXAMPLES</span></span>

### <span data-ttu-id="a6f8d-113">Пример 1. получение всех источников пакетов</span><span class="sxs-lookup"><span data-stu-id="a6f8d-113">Example 1: Get all package sources</span></span>

<span data-ttu-id="a6f8d-114">`Get-PackageSource`Командлет возвращает все источники пакетов, зарегистрированные с помощью **PackageManagement** , на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a6f8d-114">The `Get-PackageSource` cmdlet gets all package sources that are registered with **PackageManagement** on the local computer.</span></span>

```powershell
Get-PackageSource
```

```Output
Name                 ProviderName     IsTrusted  Location
----                 ------------     ---------  --------
LocalPackages        NuGet            False      C:\LocalPkg\
MyNuget              NuGet            False      https://www.nuget.org/api/v2
PSGallery            PowerShellGet    False      https://www.powershellgallery.com/api/v2
```

### <span data-ttu-id="a6f8d-115">Пример 2. получение всех источников пакетов для конкретного поставщика</span><span class="sxs-lookup"><span data-stu-id="a6f8d-115">Example 2: Get all package sources for a specific provider</span></span>

<span data-ttu-id="a6f8d-116">Эта команда получает источники пакетов, которые зарегистрированы для конкретного поставщика.</span><span class="sxs-lookup"><span data-stu-id="a6f8d-116">This command gets package sources that are registered for a specific provider.</span></span>

```powershell
Get-PackageSource -ProviderName NuGet
```

```Output
Name                 ProviderName     IsTrusted  Location
----                 ------------     ---------  --------
LocalPackages        NuGet            False      C:\LocalPkg\
MyNuget              NuGet            False      https://www.nuget.org/api/v2
```

<span data-ttu-id="a6f8d-117">`Get-PackageSource` использует параметр **providerName** для получения источников пакетов, зарегистрированных для поставщика **NuGet** .</span><span class="sxs-lookup"><span data-stu-id="a6f8d-117">`Get-PackageSource` uses the **ProviderName** parameter to get package sources that are registered for the **NuGet** provider.</span></span>

### <span data-ttu-id="a6f8d-118">Пример 3. получение источников из поставщика пакетов</span><span class="sxs-lookup"><span data-stu-id="a6f8d-118">Example 3: Get sources from a package provider</span></span>

<span data-ttu-id="a6f8d-119">Эта команда использует поставщик пакетов для получения источников пакетов.</span><span class="sxs-lookup"><span data-stu-id="a6f8d-119">This command uses a package provider to get package sources.</span></span>

```powershell
Get-PackageProvider -Name NuGet | Get-PackageSource
```

```Output
Name                 ProviderName     IsTrusted  Location
----                 ------------     ---------  --------
LocalPackages        NuGet            False      C:\LocalPkg\
MyNuget              NuGet            False      https://www.nuget.org/api/v2
```

<span data-ttu-id="a6f8d-120">`Get-PackageProvider` использует параметр **Name** , чтобы указать имя поставщика, **NuGet**.</span><span class="sxs-lookup"><span data-stu-id="a6f8d-120">`Get-PackageProvider` uses the **Name** parameter specify the provider name, **NuGet**.</span></span> <span data-ttu-id="a6f8d-121">Объект отправляется по конвейеру в `Get-PackageSource` .</span><span class="sxs-lookup"><span data-stu-id="a6f8d-121">The object is sent down the pipeline to `Get-PackageSource`.</span></span>

## <span data-ttu-id="a6f8d-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a6f8d-122">PARAMETERS</span></span>

### <span data-ttu-id="a6f8d-123">-ConfigFile</span><span class="sxs-lookup"><span data-stu-id="a6f8d-123">-ConfigFile</span></span>

<span data-ttu-id="a6f8d-124">Указывает файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a6f8d-124">Specifies a configuration file.</span></span>

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

### <span data-ttu-id="a6f8d-125">-Force</span><span class="sxs-lookup"><span data-stu-id="a6f8d-125">-Force</span></span>

<span data-ttu-id="a6f8d-126">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="a6f8d-126">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="a6f8d-127">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="a6f8d-127">-ForceBootstrap</span></span>

<span data-ttu-id="a6f8d-128">Указывает, что этот командлет заставляет службу **PackageManagement** автоматически установить поставщик пакетов.</span><span class="sxs-lookup"><span data-stu-id="a6f8d-128">Indicates that this cmdlet forces **PackageManagement** to automatically install a package provider.</span></span>

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

### <span data-ttu-id="a6f8d-129">— Расположение</span><span class="sxs-lookup"><span data-stu-id="a6f8d-129">-Location</span></span>

<span data-ttu-id="a6f8d-130">Указывает расположение источника или репозитория управления пакетами.</span><span class="sxs-lookup"><span data-stu-id="a6f8d-130">Specifies the location of a package management source or repository.</span></span>

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

### <span data-ttu-id="a6f8d-131">-Name</span><span class="sxs-lookup"><span data-stu-id="a6f8d-131">-Name</span></span>

<span data-ttu-id="a6f8d-132">Указывает имя источника управления пакетами.</span><span class="sxs-lookup"><span data-stu-id="a6f8d-132">Specifies the name of a package management source.</span></span>

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

### <span data-ttu-id="a6f8d-133">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="a6f8d-133">-PackageManagementProvider</span></span>

<span data-ttu-id="a6f8d-134">Указывает поставщика управления пакетами.</span><span class="sxs-lookup"><span data-stu-id="a6f8d-134">Specifies a package management provider.</span></span>

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

### <span data-ttu-id="a6f8d-135">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="a6f8d-135">-ProviderName</span></span>

<span data-ttu-id="a6f8d-136">Указывает одно или несколько имен поставщиков пакетов.</span><span class="sxs-lookup"><span data-stu-id="a6f8d-136">Specifies one or more package provider names.</span></span> <span data-ttu-id="a6f8d-137">Несколько имен поставщиков пакетов следует разделять запятыми.</span><span class="sxs-lookup"><span data-stu-id="a6f8d-137">Separate multiple package provider names with commas.</span></span>
<span data-ttu-id="a6f8d-138">Используйте `Get-PackageProvider` для получения списка доступных поставщиков пакетов.</span><span class="sxs-lookup"><span data-stu-id="a6f8d-138">Use `Get-PackageProvider` to get a list of available package providers.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Provider
Accepted values: Bootstrap, NuGet, PowerShellGet

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a6f8d-139">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="a6f8d-139">-PublishLocation</span></span>

<span data-ttu-id="a6f8d-140">Указывает расположение публикации для источника пакета.</span><span class="sxs-lookup"><span data-stu-id="a6f8d-140">Specifies the publish location for the package source.</span></span>

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

### <span data-ttu-id="a6f8d-141">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="a6f8d-141">-ScriptPublishLocation</span></span>

<span data-ttu-id="a6f8d-142">Указывает расположение публикации скрипта.</span><span class="sxs-lookup"><span data-stu-id="a6f8d-142">Specifies the script publish location.</span></span>

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

### <span data-ttu-id="a6f8d-143">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="a6f8d-143">-ScriptSourceLocation</span></span>

<span data-ttu-id="a6f8d-144">Указывает расположение источника скрипта.</span><span class="sxs-lookup"><span data-stu-id="a6f8d-144">Specifies the script source location.</span></span>

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

### <span data-ttu-id="a6f8d-145">-Скипвалидате</span><span class="sxs-lookup"><span data-stu-id="a6f8d-145">-SkipValidate</span></span>

<span data-ttu-id="a6f8d-146">Параметр, который пропускает проверку учетных данных источника пакета.</span><span class="sxs-lookup"><span data-stu-id="a6f8d-146">Switch that skips validating the credentials of a package source.</span></span>

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

### <span data-ttu-id="a6f8d-147">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="a6f8d-147">CommonParameters</span></span>

<span data-ttu-id="a6f8d-148">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a6f8d-148">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a6f8d-149">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a6f8d-149">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a6f8d-150">Входные данные</span><span class="sxs-lookup"><span data-stu-id="a6f8d-150">INPUTS</span></span>

## <span data-ttu-id="a6f8d-151">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="a6f8d-151">OUTPUTS</span></span>

### <span data-ttu-id="a6f8d-152">PackageSource []</span><span class="sxs-lookup"><span data-stu-id="a6f8d-152">PackageSource[]</span></span>

<span data-ttu-id="a6f8d-153">Указывает один или несколько источников пакетов.</span><span class="sxs-lookup"><span data-stu-id="a6f8d-153">Specifies one or more package sources.</span></span>

## <span data-ttu-id="a6f8d-154">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="a6f8d-154">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a6f8d-155">Начиная с апреля 2020 года коллекция PowerShell не поддерживает протокол TLS (Transport Layer Security) версий 1.0 и 1.1.</span><span class="sxs-lookup"><span data-stu-id="a6f8d-155">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="a6f8d-156">Если вы не используете TLS 1.2 или более поздней версии, при попытке доступа к коллекции PowerShell возникнет ошибка.</span><span class="sxs-lookup"><span data-stu-id="a6f8d-156">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="a6f8d-157">Чтобы проверить, используется ли TLS 1.2, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a6f8d-157">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="a6f8d-158">Дополнительные сведения см. в [объявлении](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) в блоге, посвященном PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a6f8d-158">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="a6f8d-159">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="a6f8d-159">RELATED LINKS</span></span>

[<span data-ttu-id="a6f8d-160">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="a6f8d-160">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="a6f8d-161">Find-Package</span><span class="sxs-lookup"><span data-stu-id="a6f8d-161">Find-Package</span></span>](Find-Package.md)

[<span data-ttu-id="a6f8d-162">Get-Package</span><span class="sxs-lookup"><span data-stu-id="a6f8d-162">Get-Package</span></span>](Get-Package.md)

[<span data-ttu-id="a6f8d-163">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="a6f8d-163">Get-PackageProvider</span></span>](Get-PackageProvider.md)

[<span data-ttu-id="a6f8d-164">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="a6f8d-164">Register-PackageSource</span></span>](Register-PackageSource.md)

[<span data-ttu-id="a6f8d-165">Set-PackageSource</span><span class="sxs-lookup"><span data-stu-id="a6f8d-165">Set-PackageSource</span></span>](Set-PackageSource.md)

[<span data-ttu-id="a6f8d-166">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="a6f8d-166">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)
