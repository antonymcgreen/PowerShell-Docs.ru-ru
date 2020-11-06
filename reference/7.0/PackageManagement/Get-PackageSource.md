---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PackageManagement
ms.date: 03/29/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/get-packagesource?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PackageSource
ms.openlocfilehash: 6fb64b7e95f1f8ddfff6f1be9e880045271706fc
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93225890"
---
# <span data-ttu-id="ca75a-103">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="ca75a-103">Get-PackageSource</span></span>

## <span data-ttu-id="ca75a-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="ca75a-104">SYNOPSIS</span></span>
<span data-ttu-id="ca75a-105">Возвращает список источников пакетов, зарегистрированных для поставщика пакетов.</span><span class="sxs-lookup"><span data-stu-id="ca75a-105">Gets a list of package sources that are registered for a package provider.</span></span>

## <span data-ttu-id="ca75a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ca75a-106">SYNTAX</span></span>

### <span data-ttu-id="ca75a-107">NuGet</span><span class="sxs-lookup"><span data-stu-id="ca75a-107">NuGet</span></span>

```
Get-PackageSource [[-Name] <String>] [-Location <String>] [-Force] [-ForceBootstrap]
 [-ProviderName <String[]>] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### <span data-ttu-id="ca75a-108">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="ca75a-108">PowerShellGet</span></span>

```
Get-PackageSource [[-Name] <String>] [-Location <String>] [-Force] [-ForceBootstrap]
 [-ProviderName <String[]>] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

## <span data-ttu-id="ca75a-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ca75a-109">DESCRIPTION</span></span>

<span data-ttu-id="ca75a-110">`Get-PackageSource`Командлет возвращает список источников пакетов, зарегистрированных с помощью **PackageManagement** , на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ca75a-110">The `Get-PackageSource` cmdlet gets a list of package sources that are registered with **PackageManagement** on the local computer.</span></span> <span data-ttu-id="ca75a-111">При указании поставщика пакетов `Get-PackageSource` получает только те источники, которые связаны с указанным поставщиком.</span><span class="sxs-lookup"><span data-stu-id="ca75a-111">If you specify a package provider, `Get-PackageSource` gets only those sources that are associated with the specified provider.</span></span> <span data-ttu-id="ca75a-112">В противном случае команда возвращает все источники пакетов, зарегистрированные с помощью **PackageManagement**.</span><span class="sxs-lookup"><span data-stu-id="ca75a-112">Otherwise, the command returns all package sources that are registered with **PackageManagement**.</span></span>

## <span data-ttu-id="ca75a-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="ca75a-113">EXAMPLES</span></span>

### <span data-ttu-id="ca75a-114">Пример 1. получение всех источников пакетов</span><span class="sxs-lookup"><span data-stu-id="ca75a-114">Example 1: Get all package sources</span></span>

<span data-ttu-id="ca75a-115">`Get-PackageSource`Командлет возвращает все источники пакетов, зарегистрированные с помощью **PackageManagement** , на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ca75a-115">The `Get-PackageSource` cmdlet gets all package sources that are registered with **PackageManagement** on the local computer.</span></span>

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

### <span data-ttu-id="ca75a-116">Пример 2. получение всех источников пакетов для конкретного поставщика</span><span class="sxs-lookup"><span data-stu-id="ca75a-116">Example 2: Get all package sources for a specific provider</span></span>

<span data-ttu-id="ca75a-117">Эта команда получает источники пакетов, которые зарегистрированы для конкретного поставщика.</span><span class="sxs-lookup"><span data-stu-id="ca75a-117">This command gets package sources that are registered for a specific provider.</span></span>

```powershell
Get-PackageSource -ProviderName NuGet
```

```Output
Name                 ProviderName     IsTrusted  Location
----                 ------------     ---------  --------
LocalPackages        NuGet            False      C:\LocalPkg\
MyNuget              NuGet            False      https://www.nuget.org/api/v2
```

<span data-ttu-id="ca75a-118">`Get-PackageSource` использует параметр **providerName** для получения источников пакетов, зарегистрированных для поставщика **NuGet** .</span><span class="sxs-lookup"><span data-stu-id="ca75a-118">`Get-PackageSource` uses the **ProviderName** parameter to get package sources that are registered for the **NuGet** provider.</span></span>

### <span data-ttu-id="ca75a-119">Пример 3. получение источников из поставщика пакетов</span><span class="sxs-lookup"><span data-stu-id="ca75a-119">Example 3: Get sources from a package provider</span></span>

<span data-ttu-id="ca75a-120">Эта команда использует поставщик пакетов для получения источников пакетов.</span><span class="sxs-lookup"><span data-stu-id="ca75a-120">This command uses a package provider to get package sources.</span></span>

```powershell
Get-PackageProvider -Name NuGet | Get-PackageSource
```

```Output
Name                 ProviderName     IsTrusted  Location
----                 ------------     ---------  --------
LocalPackages        NuGet            False      C:\LocalPkg\
MyNuget              NuGet            False      https://www.nuget.org/api/v2
```

<span data-ttu-id="ca75a-121">`Get-PackageProvider` использует параметр **Name** , чтобы указать имя поставщика, **NuGet**.</span><span class="sxs-lookup"><span data-stu-id="ca75a-121">`Get-PackageProvider` uses the **Name** parameter specify the provider name, **NuGet**.</span></span> <span data-ttu-id="ca75a-122">Объект отправляется по конвейеру в `Get-PackageSource` .</span><span class="sxs-lookup"><span data-stu-id="ca75a-122">The object is sent down the pipeline to `Get-PackageSource`.</span></span>

## <span data-ttu-id="ca75a-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ca75a-123">PARAMETERS</span></span>

### <span data-ttu-id="ca75a-124">-ConfigFile</span><span class="sxs-lookup"><span data-stu-id="ca75a-124">-ConfigFile</span></span>

<span data-ttu-id="ca75a-125">Указывает файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ca75a-125">Specifies a configuration file.</span></span>

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

### <span data-ttu-id="ca75a-126">-Force</span><span class="sxs-lookup"><span data-stu-id="ca75a-126">-Force</span></span>

<span data-ttu-id="ca75a-127">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="ca75a-127">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="ca75a-128">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="ca75a-128">-ForceBootstrap</span></span>

<span data-ttu-id="ca75a-129">Указывает, что этот командлет заставляет службу **PackageManagement** автоматически установить поставщик пакетов.</span><span class="sxs-lookup"><span data-stu-id="ca75a-129">Indicates that this cmdlet forces **PackageManagement** to automatically install a package provider.</span></span>

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

### <span data-ttu-id="ca75a-130">— Расположение</span><span class="sxs-lookup"><span data-stu-id="ca75a-130">-Location</span></span>

<span data-ttu-id="ca75a-131">Указывает расположение источника или репозитория управления пакетами.</span><span class="sxs-lookup"><span data-stu-id="ca75a-131">Specifies the location of a package management source or repository.</span></span>

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

### <span data-ttu-id="ca75a-132">-Name</span><span class="sxs-lookup"><span data-stu-id="ca75a-132">-Name</span></span>

<span data-ttu-id="ca75a-133">Указывает имя источника управления пакетами.</span><span class="sxs-lookup"><span data-stu-id="ca75a-133">Specifies the name of a package management source.</span></span>

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

### <span data-ttu-id="ca75a-134">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="ca75a-134">-PackageManagementProvider</span></span>

<span data-ttu-id="ca75a-135">Указывает поставщика управления пакетами.</span><span class="sxs-lookup"><span data-stu-id="ca75a-135">Specifies a package management provider.</span></span>

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

### <span data-ttu-id="ca75a-136">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="ca75a-136">-ProviderName</span></span>

<span data-ttu-id="ca75a-137">Указывает одно или несколько имен поставщиков пакетов.</span><span class="sxs-lookup"><span data-stu-id="ca75a-137">Specifies one or more package provider names.</span></span> <span data-ttu-id="ca75a-138">Несколько имен поставщиков пакетов следует разделять запятыми.</span><span class="sxs-lookup"><span data-stu-id="ca75a-138">Separate multiple package provider names with commas.</span></span>
<span data-ttu-id="ca75a-139">Используйте `Get-PackageProvider` для получения списка доступных поставщиков пакетов.</span><span class="sxs-lookup"><span data-stu-id="ca75a-139">Use `Get-PackageProvider` to get a list of available package providers.</span></span>

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

### <span data-ttu-id="ca75a-140">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="ca75a-140">-PublishLocation</span></span>

<span data-ttu-id="ca75a-141">Указывает расположение публикации для источника пакета.</span><span class="sxs-lookup"><span data-stu-id="ca75a-141">Specifies the publish location for the package source.</span></span>

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

### <span data-ttu-id="ca75a-142">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="ca75a-142">-ScriptPublishLocation</span></span>

<span data-ttu-id="ca75a-143">Указывает расположение публикации скрипта.</span><span class="sxs-lookup"><span data-stu-id="ca75a-143">Specifies the script publish location.</span></span>

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

### <span data-ttu-id="ca75a-144">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="ca75a-144">-ScriptSourceLocation</span></span>

<span data-ttu-id="ca75a-145">Указывает расположение источника скрипта.</span><span class="sxs-lookup"><span data-stu-id="ca75a-145">Specifies the script source location.</span></span>

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

### <span data-ttu-id="ca75a-146">-Скипвалидате</span><span class="sxs-lookup"><span data-stu-id="ca75a-146">-SkipValidate</span></span>

<span data-ttu-id="ca75a-147">Параметр, который пропускает проверку учетных данных источника пакета.</span><span class="sxs-lookup"><span data-stu-id="ca75a-147">Switch that skips validating the credentials of a package source.</span></span>

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

### <span data-ttu-id="ca75a-148">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="ca75a-148">CommonParameters</span></span>

<span data-ttu-id="ca75a-149">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="ca75a-149">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ca75a-150">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="ca75a-150">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ca75a-151">Входные данные</span><span class="sxs-lookup"><span data-stu-id="ca75a-151">INPUTS</span></span>

## <span data-ttu-id="ca75a-152">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="ca75a-152">OUTPUTS</span></span>

### <span data-ttu-id="ca75a-153">PackageSource []</span><span class="sxs-lookup"><span data-stu-id="ca75a-153">PackageSource[]</span></span>

<span data-ttu-id="ca75a-154">Указывает один или несколько источников пакетов.</span><span class="sxs-lookup"><span data-stu-id="ca75a-154">Specifies one or more package sources.</span></span>

## <span data-ttu-id="ca75a-155">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="ca75a-155">NOTES</span></span>

## <span data-ttu-id="ca75a-156">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="ca75a-156">RELATED LINKS</span></span>

[<span data-ttu-id="ca75a-157">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="ca75a-157">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="ca75a-158">Find-Package</span><span class="sxs-lookup"><span data-stu-id="ca75a-158">Find-Package</span></span>](Find-Package.md)

[<span data-ttu-id="ca75a-159">Get-Package</span><span class="sxs-lookup"><span data-stu-id="ca75a-159">Get-Package</span></span>](Get-Package.md)

[<span data-ttu-id="ca75a-160">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="ca75a-160">Get-PackageProvider</span></span>](Get-PackageProvider.md)

[<span data-ttu-id="ca75a-161">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="ca75a-161">Register-PackageSource</span></span>](Register-PackageSource.md)

[<span data-ttu-id="ca75a-162">Set-PackageSource</span><span class="sxs-lookup"><span data-stu-id="ca75a-162">Set-PackageSource</span></span>](Set-PackageSource.md)

[<span data-ttu-id="ca75a-163">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="ca75a-163">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)