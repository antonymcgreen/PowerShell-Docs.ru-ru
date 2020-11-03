---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PackageManagement
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/packagemanagement/find-packageprovider?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-PackageProvider
ms.openlocfilehash: f24d92e7ac51a7358f437ad638904bdfaf08f508
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228109"
---
# <span data-ttu-id="0733d-103">Find-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="0733d-103">Find-PackageProvider</span></span>

## <span data-ttu-id="0733d-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="0733d-104">SYNOPSIS</span></span>
<span data-ttu-id="0733d-105">Возвращает список поставщиков пакетов Управление пакетами, доступных для установки.</span><span class="sxs-lookup"><span data-stu-id="0733d-105">Returns a list of Package Management package providers available for installation.</span></span>

## <span data-ttu-id="0733d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0733d-106">SYNTAX</span></span>

```
Find-PackageProvider [[-Name] <String[]>] [-AllVersions] [-Source <String[]>] [-IncludeDependencies]
 [-Credential <PSCredential>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-RequiredVersion <String>]
 [-MinimumVersion <String>] [-MaximumVersion <String>] [-Force] [-ForceBootstrap] [<CommonParameters>]
```

## <span data-ttu-id="0733d-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0733d-107">DESCRIPTION</span></span>

<span data-ttu-id="0733d-108">Командлет **Find-PackageProvider** находит соответствующие поставщики PackageManagement, доступные в источниках пакетов, зарегистрированных с помощью PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="0733d-108">The **Find-PackageProvider** cmdlet finds matching PackageManagement providers that are available in package sources registered with PowerShellGet.</span></span>
<span data-ttu-id="0733d-109">Эти поставщики пакетов можно установить с помощью командлета Install-PackageProvider.</span><span class="sxs-lookup"><span data-stu-id="0733d-109">These are package providers available for installation with the Install-PackageProvider cmdlet.</span></span>
<span data-ttu-id="0733d-110">По умолчанию сюда входят модули, доступные в коллекция PowerShell с тегами **PackageManagement** и **provider** .</span><span class="sxs-lookup"><span data-stu-id="0733d-110">By default, this includes modules available in the PowerShell Gallery with the **PackageManagement** and **Provider** tags.</span></span>

<span data-ttu-id="0733d-111">**Find-PackageProvider** также находит соответствующие поставщики Управление пакетами, доступные в хранилище больших двоичных объектов Azure Управление пакетами.</span><span class="sxs-lookup"><span data-stu-id="0733d-111">**Find-PackageProvider** also finds matching Package Management providers that are available in the Package Management Azure Blob store.</span></span>
<span data-ttu-id="0733d-112">Используйте поставщик загрузчика, чтобы найти и установить их.</span><span class="sxs-lookup"><span data-stu-id="0733d-112">Use the bootstrapper provider to find and install them.</span></span>

## <span data-ttu-id="0733d-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="0733d-113">EXAMPLES</span></span>

### <span data-ttu-id="0733d-114">Пример 1. Поиск всех доступных поставщиков пакетов</span><span class="sxs-lookup"><span data-stu-id="0733d-114">Example 1: Find all available package providers</span></span>

```
PS C:\> Find-PackageProvider
```

<span data-ttu-id="0733d-115">Эта команда возвращает список всех поставщиков пакетов, доступных в репозиториях, поддерживаемых Управление пакетами.</span><span class="sxs-lookup"><span data-stu-id="0733d-115">This command gets a list of all package providers that are available on the repositories supported by Package Management.</span></span>
<span data-ttu-id="0733d-116">По умолчанию эти поставщики пакетов доступны на коллекция PowerShell и с помощью приложения начальной загрузки Управление пакетами.</span><span class="sxs-lookup"><span data-stu-id="0733d-116">By default, those package providers are available on the PowerShell Gallery and by using the Package Management bootstrapping application.</span></span>

### <span data-ttu-id="0733d-117">Пример 2. Поиск всех версий поставщика</span><span class="sxs-lookup"><span data-stu-id="0733d-117">Example 2: Find all versions of a provider</span></span>

```
PS C:\> Find-PackageProvider -Name "Nuget" -AllVersions
```

<span data-ttu-id="0733d-118">Эта команда находит все версии поставщика пакетов с именем NuGet.</span><span class="sxs-lookup"><span data-stu-id="0733d-118">This command finds all versions of the package provider named Nuget.</span></span>

### <span data-ttu-id="0733d-119">Пример 3. Поиск поставщика из указанного источника</span><span class="sxs-lookup"><span data-stu-id="0733d-119">Example 3: Find a provider from a specified source</span></span>

```
PS C:\> Find-PackageProvider -Name "Gistprovider" -Source "PSGallery"
```

<span data-ttu-id="0733d-120">Эта команда находит поставщик пакетов, доступный с помощью указанного источника пакета.</span><span class="sxs-lookup"><span data-stu-id="0733d-120">This command finds a package provider available by using a specified package source.</span></span>

## <span data-ttu-id="0733d-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0733d-121">PARAMETERS</span></span>

### <span data-ttu-id="0733d-122">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="0733d-122">-AllVersions</span></span>

<span data-ttu-id="0733d-123">Указывает, что этот командлет возвращает все доступные версии поставщика пакетов.</span><span class="sxs-lookup"><span data-stu-id="0733d-123">Indicates that this cmdlet returns all available versions of the package provider.</span></span>
<span data-ttu-id="0733d-124">По умолчанию командлет **Find-PackageProvider** возвращает только последнюю доступную версию.</span><span class="sxs-lookup"><span data-stu-id="0733d-124">By default, **Find-PackageProvider** only returns the newest available version.</span></span>

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

### <span data-ttu-id="0733d-125">-Credential</span><span class="sxs-lookup"><span data-stu-id="0733d-125">-Credential</span></span>

<span data-ttu-id="0733d-126">Указывает учетную запись пользователя, имеющую разрешение на поиск поставщиков пакетов.</span><span class="sxs-lookup"><span data-stu-id="0733d-126">Specifies a user account that has permission to search for package providers.</span></span>

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

### <span data-ttu-id="0733d-127">-Force</span><span class="sxs-lookup"><span data-stu-id="0733d-127">-Force</span></span>

<span data-ttu-id="0733d-128">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="0733d-128">Forces the command to run without asking for user confirmation.</span></span>
<span data-ttu-id="0733d-129">В настоящее время это эквивалентно параметру *форцебутстрап* .</span><span class="sxs-lookup"><span data-stu-id="0733d-129">Currently, this is equivalent to the *ForceBootstrap* parameter.</span></span>

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

### <span data-ttu-id="0733d-130">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="0733d-130">-ForceBootstrap</span></span>

<span data-ttu-id="0733d-131">Указывает, что этот командлет заставляет систему управления пакетами автоматически установить поставщик пакетов.</span><span class="sxs-lookup"><span data-stu-id="0733d-131">Indicates that this cmdlet forces Package Management to automatically install the package provider.</span></span>

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

### <span data-ttu-id="0733d-132">-IncludeDependencies</span><span class="sxs-lookup"><span data-stu-id="0733d-132">-IncludeDependencies</span></span>

<span data-ttu-id="0733d-133">Указывает, что этот командлет включает зависимости.</span><span class="sxs-lookup"><span data-stu-id="0733d-133">Indicates that this cmdlet includes dependencies.</span></span>

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

### <span data-ttu-id="0733d-134">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="0733d-134">-MaximumVersion</span></span>

<span data-ttu-id="0733d-135">Указывает максимально допустимую версию поставщика пакетов, которую необходимо найти.</span><span class="sxs-lookup"><span data-stu-id="0733d-135">Specifies the maximum allowed version of the package provider that you want to find.</span></span>
<span data-ttu-id="0733d-136">Если этот параметр не добавлен, командлет **Find-PackageProvider** находит самую новую доступную версию поставщика.</span><span class="sxs-lookup"><span data-stu-id="0733d-136">If you do not add this parameter, **Find-PackageProvider** finds the highest available version of the provider.</span></span>

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

### <span data-ttu-id="0733d-137">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="0733d-137">-MinimumVersion</span></span>

<span data-ttu-id="0733d-138">Указывает минимально допустимую версию поставщика пакетов, которую необходимо найти.</span><span class="sxs-lookup"><span data-stu-id="0733d-138">Specifies the minimum allowed version of the package provider that you want to find.</span></span>
<span data-ttu-id="0733d-139">Если этот параметр не указан, командлет **Find-PackageProvider** находит самую новую доступную версию пакета, которая также соответствует максимальной заданной версии, заданной параметром *MaximumVersion* .</span><span class="sxs-lookup"><span data-stu-id="0733d-139">If you do not add this parameter, **Find-PackageProvider** finds the highest available version of the package that also satisfies any maximum specified version specified by the *MaximumVersion* parameter.</span></span>

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

### <span data-ttu-id="0733d-140">-Name</span><span class="sxs-lookup"><span data-stu-id="0733d-140">-Name</span></span>

<span data-ttu-id="0733d-141">Указывает одно или несколько имен модулей поставщика пакетов или имена поставщиков с подстановочными знаками.</span><span class="sxs-lookup"><span data-stu-id="0733d-141">Specifies one or more package provider module names, or provider names with wildcard characters.</span></span>
<span data-ttu-id="0733d-142">Несколько имен пакетов следует разделять запятыми.</span><span class="sxs-lookup"><span data-stu-id="0733d-142">Separate multiple package names with commas.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="0733d-143">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="0733d-143">-Proxy</span></span>

<span data-ttu-id="0733d-144">Указывает прокси-сервер для запроса, а не напрямуюе подключение к Интернет-ресурсу.</span><span class="sxs-lookup"><span data-stu-id="0733d-144">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

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

### <span data-ttu-id="0733d-145">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="0733d-145">-ProxyCredential</span></span>

<span data-ttu-id="0733d-146">Указывает учетную запись пользователя, имеющую разрешение на использование прокси-сервера, который задается параметром **Proxy** .</span><span class="sxs-lookup"><span data-stu-id="0733d-146">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="0733d-147">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="0733d-147">-RequiredVersion</span></span>

<span data-ttu-id="0733d-148">Указывает точную разрешенную версию поставщика пакета, который требуется найти.</span><span class="sxs-lookup"><span data-stu-id="0733d-148">Specifies the exact allowed version of the package provider that you want to find.</span></span>
<span data-ttu-id="0733d-149">Если этот параметр не указан, командлет **Find-PackageProvider** находит самую новую доступную версию поставщика, которая также соответствует максимальной версии, указанной в параметре *MaximumVersion* .</span><span class="sxs-lookup"><span data-stu-id="0733d-149">If you do not add this parameter, **Find-PackageProvider** finds the highest available version of the provider that also satisfies any maximum version specified by the *MaximumVersion* parameter.</span></span>

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

### <span data-ttu-id="0733d-150">-Source</span><span class="sxs-lookup"><span data-stu-id="0733d-150">-Source</span></span>

<span data-ttu-id="0733d-151">Указывает один или несколько источников пакетов.</span><span class="sxs-lookup"><span data-stu-id="0733d-151">Specifies one or more package sources.</span></span>
<span data-ttu-id="0733d-152">Список доступных источников пакетов можно получить с помощью командлета Get-PackageSource.</span><span class="sxs-lookup"><span data-stu-id="0733d-152">You can get a list of available package sources by using the Get-PackageSource cmdlet.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="0733d-153">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="0733d-153">CommonParameters</span></span>

<span data-ttu-id="0733d-154">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0733d-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0733d-155">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0733d-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0733d-156">Входные данные</span><span class="sxs-lookup"><span data-stu-id="0733d-156">INPUTS</span></span>

## <span data-ttu-id="0733d-157">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="0733d-157">OUTPUTS</span></span>

### <span data-ttu-id="0733d-158">Microsoft. PackageManagement. Packaging. Софтвареидентити</span><span class="sxs-lookup"><span data-stu-id="0733d-158">Microsoft.PackageManagement.Packaging.SoftwareIdentity</span></span>

<span data-ttu-id="0733d-159">Этот командлет возвращает объект **софтвареидентити** .</span><span class="sxs-lookup"><span data-stu-id="0733d-159">This cmdlet returns a **SoftwareIdentity** object.</span></span>
<span data-ttu-id="0733d-160">Объект **софтвареидентити** можно передать в командлет **Install-PackageProvider** , чтобы установить результаты командлета **Find-PackageProvider** .</span><span class="sxs-lookup"><span data-stu-id="0733d-160">A **SoftwareIdentity** object can be piped into **Install-PackageProvider** to install the results of **Find-PackageProvider** .</span></span>

## <span data-ttu-id="0733d-161">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="0733d-161">NOTES</span></span>

## <span data-ttu-id="0733d-162">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="0733d-162">RELATED LINKS</span></span>

[<span data-ttu-id="0733d-163">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="0733d-163">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="0733d-164">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="0733d-164">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)

[<span data-ttu-id="0733d-165">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="0733d-165">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="0733d-166">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="0733d-166">Register-PackageSource</span></span>](Register-PackageSource.md)

[<span data-ttu-id="0733d-167">Install-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="0733d-167">Install-PackageProvider</span></span>](Install-PackageProvider.md)
