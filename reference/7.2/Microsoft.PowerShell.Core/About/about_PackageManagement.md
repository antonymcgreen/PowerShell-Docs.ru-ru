---
description: PackageManagement — это агрегатор для диспетчеров пакетов программного обеспечения.
Locale: en-US
ms.date: 03/30/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_packagemanagement?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PackageManagement
ms.openlocfilehash: 22f47d01063778fca4f51a534b15d485b3beee28
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601281"
---
# <a name="about-packagemanagement"></a><span data-ttu-id="f1894-103">Сведения о PackageManagement</span><span class="sxs-lookup"><span data-stu-id="f1894-103">About PackageManagement</span></span>

## <a name="short-description"></a><span data-ttu-id="f1894-104">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="f1894-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="f1894-105">PackageManagement — это агрегатор для диспетчеров пакетов программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="f1894-105">PackageManagement is an aggregator for software package managers.</span></span>

## <a name="long-description"></a><span data-ttu-id="f1894-106">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="f1894-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="f1894-107">Функция PackageManagement появилась в Windows PowerShell 5,0.</span><span class="sxs-lookup"><span data-stu-id="f1894-107">PackageManagement functionality was introduced in Windows PowerShell 5.0.</span></span>

<span data-ttu-id="f1894-108">PackageManagement — это единый интерфейс для систем управления пакетами программного обеспечения; Командлеты PackageManagement можно использовать для выполнения задач обнаружения программного обеспечения, установки и инвентаризации (СДИИ).</span><span class="sxs-lookup"><span data-stu-id="f1894-108">PackageManagement is a unified interface for software package management systems; you can run PackageManagement cmdlets to perform software discovery, installation, and inventory (SDII) tasks.</span></span> <span data-ttu-id="f1894-109">Независимо от базовой технологии установки можно выполнять общие командлеты в модуле PackageManagement для поиска, установки и удаления пакетов. добавлять, удалять и запрашивать репозитории пакетов; и запускают запросы на компьютере, чтобы определить, какие пакеты программного обеспечения установлены.</span><span class="sxs-lookup"><span data-stu-id="f1894-109">Regardless of the underlying installation technology, you can run the common cmdlets in the PackageManagement module to search for, install, or uninstall packages; add, remove, and query package repositories; and run queries on a computer to determine which software packages are installed.</span></span>

<span data-ttu-id="f1894-110">PackageManagement поддерживает гибкую модель подключаемых модулей, которая обеспечивает поддержку других систем управления пакетами программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="f1894-110">PackageManagement supports a flexible plug-in model that enables support for other software package management systems.</span></span>

<span data-ttu-id="f1894-111">Модуль PackageManagement входит в состав Windows PowerShell 5,0 и более поздних выпусков PowerShell и работает на трех уровнях структуры управления пакетами: поставщиками пакетов, источниками пакетов и самими пакетами.</span><span class="sxs-lookup"><span data-stu-id="f1894-111">The PackageManagement module is included with Windows PowerShell 5.0 and later releases of PowerShell, and works on three levels of package management structure: package providers, package sources, and the packages themselves.</span></span> <span data-ttu-id="f1894-112">Давайте определим некоторые термины:</span><span class="sxs-lookup"><span data-stu-id="f1894-112">Let us define some terms:</span></span>

- <span data-ttu-id="f1894-113">Диспетчер пакетов: система управления пакетами программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="f1894-113">Package manager: Software package management system.</span></span> <span data-ttu-id="f1894-114">В терминах PackageManagement это поставщик пакетов.</span><span class="sxs-lookup"><span data-stu-id="f1894-114">In PackageManagement terms, this is a package provider.</span></span>
- <span data-ttu-id="f1894-115">Поставщик пакетов: термин PackageManagement для диспетчера пакетов.</span><span class="sxs-lookup"><span data-stu-id="f1894-115">Package provider: PackageManagement term for a package manager.</span></span> <span data-ttu-id="f1894-116">Примерами могут быть установщик Windows, шоколад и другие.</span><span class="sxs-lookup"><span data-stu-id="f1894-116">Examples can include Windows Installer, Chocolatey, and others.</span></span>
- <span data-ttu-id="f1894-117">Источник пакета: URL-адрес, локальная папка или общая сетевая папка, в которой поставщики пакетов настраиваются для использования в качестве репозитория.</span><span class="sxs-lookup"><span data-stu-id="f1894-117">Package source: A URL, local folder, or network shared folder that you configure package providers to use as a repository.</span></span>
- <span data-ttu-id="f1894-118">Package — это программное обеспечение, которое управляется поставщиком пакетов и хранится в определенном источнике пакета.</span><span class="sxs-lookup"><span data-stu-id="f1894-118">Package: A piece of software that a package provider manages, and that is stored in a specific package source.</span></span>

<span data-ttu-id="f1894-119">Модуль PackageManagement содержит следующие командлеты.</span><span class="sxs-lookup"><span data-stu-id="f1894-119">The PackageManagement module includes the following cmdlets.</span></span> <span data-ttu-id="f1894-120">Дополнительные сведения см. в справке [PackageManagement](/powershell/module/packagemanagement) .</span><span class="sxs-lookup"><span data-stu-id="f1894-120">For more information, see the [PackageManagement](/powershell/module/packagemanagement) help.</span></span>

- <span data-ttu-id="f1894-121">`Get-PackageProvider`: Возвращает список поставщиков пакетов, подключенных к PackageManagement.</span><span class="sxs-lookup"><span data-stu-id="f1894-121">`Get-PackageProvider`: Returns a list of package providers that are  connected to PackageManagement.</span></span>
- <span data-ttu-id="f1894-122">`Get-PackageSource`: Возвращает список источников пакетов, зарегистрированных для поставщика пакетов.</span><span class="sxs-lookup"><span data-stu-id="f1894-122">`Get-PackageSource`: Gets a list of package sources that are registered for a package provider.</span></span>
- <span data-ttu-id="f1894-123">`Register-PackageSource`: Добавляет источник пакета для указанного поставщика пакетов.</span><span class="sxs-lookup"><span data-stu-id="f1894-123">`Register-PackageSource`: Adds a package source for a specified package provider.</span></span>
- <span data-ttu-id="f1894-124">`Set-PackageSource`: Задает свойства для существующего источника пакета.</span><span class="sxs-lookup"><span data-stu-id="f1894-124">`Set-PackageSource`: Sets properties on an existing package source.</span></span>
- <span data-ttu-id="f1894-125">`Unregister-PackageSource`: Удаляет зарегистрированный источник пакета.</span><span class="sxs-lookup"><span data-stu-id="f1894-125">`Unregister-PackageSource`: Removes a registered package source.</span></span>
- <span data-ttu-id="f1894-126">`Get-Package`: Возвращает список установленных программных пакетов.</span><span class="sxs-lookup"><span data-stu-id="f1894-126">`Get-Package`: Returns a list of installed software packages.</span></span>
- <span data-ttu-id="f1894-127">`Find-Package`: Поиск пакетов программного обеспечения в доступных источниках пакетов.</span><span class="sxs-lookup"><span data-stu-id="f1894-127">`Find-Package`: Finds software packages in available package sources.</span></span>
- <span data-ttu-id="f1894-128">`Install-Package`: Устанавливает один или несколько пакетов программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="f1894-128">`Install-Package`: Installs one or more software packages.</span></span>
- <span data-ttu-id="f1894-129">`Save-Package`: Сохраняет пакеты на локальном компьютере, не устанавливая их.</span><span class="sxs-lookup"><span data-stu-id="f1894-129">`Save-Package`: Saves packages to the local computer without installing them.</span></span>
- <span data-ttu-id="f1894-130">`Uninstall-Package`: Удаляет один или несколько пакетов программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="f1894-130">`Uninstall-Package`: Uninstalls one or more software packages.</span></span>

### <a name="package-provider-bootstrapping-and-dynamic-cmdlet-parameters"></a><span data-ttu-id="f1894-131">Начальная загрузка поставщика пакетов и параметры динамических командлетов</span><span class="sxs-lookup"><span data-stu-id="f1894-131">Package Provider Bootstrapping and Dynamic Cmdlet Parameters</span></span>

<span data-ttu-id="f1894-132">По умолчанию PackageManagement поставляется с основным поставщиком начальной загрузки.</span><span class="sxs-lookup"><span data-stu-id="f1894-132">By default, PackageManagement ships with a core bootstrap provider.</span></span> <span data-ttu-id="f1894-133">Вы можете установить дополнительные поставщики пакетов по мере необходимости, заполнив начальную загрузку поставщиков. Это значит, что отвечает на запрос на автоматическую установку поставщика из веб-службы.</span><span class="sxs-lookup"><span data-stu-id="f1894-133">You can install additional package providers as you need them by bootstrapping the providers; that is, responding to a prompt to install the provider automatically, from a web service.</span></span> <span data-ttu-id="f1894-134">Поставщик пакетов можно указать с помощью любого командлета PackageManagement; Если указанный поставщик недоступен, PackageManagement предлагает выполнить начальную загрузку (или автоматическую установку) поставщика.</span><span class="sxs-lookup"><span data-stu-id="f1894-134">You can specify a package provider with any PackageManagement cmdlet; if the specified provider is not available, PackageManagement prompts you to bootstrap (or automatically install) the provider.</span></span> <span data-ttu-id="f1894-135">В следующих примерах, если поставщик шоколада еще не установлен, начальная загрузка PackageManagement устанавливает поставщик.</span><span class="sxs-lookup"><span data-stu-id="f1894-135">In the following examples, if the Chocolatey provider is not already installed, PackageManagement bootstrapping installs the provider.</span></span>

```powershell
Find-Package -Provider Chocolatey <PackageName>
```

<span data-ttu-id="f1894-136">Если поставщик шоколад еще не установлен, при выполнении предыдущей команды будет предложено установить его.</span><span class="sxs-lookup"><span data-stu-id="f1894-136">If the Chocolatey provider is not already installed, when you run the preceding command, you are prompted to install it.</span></span>

```powershell
Install-Package <Chocolatey package Name> -ForceBootstrap
```

<span data-ttu-id="f1894-137">Если поставщик шоколад еще не установлен, при выполнении предыдущей команды поставщик устанавливается; Но поскольку в команду был добавлен параметр Форцебутстрап, вам не будет предложено установить его. как поставщик, так и пакет устанавливаются автоматически.</span><span class="sxs-lookup"><span data-stu-id="f1894-137">If the Chocolatey provider is not already installed, when you run the preceding command, the provider is installed; but because the ForceBootstrap parameter has been added to the command, you are not prompted to install it; both the provider and the package are installed automatically.</span></span>

<span data-ttu-id="f1894-138">При попытке установить пакет, если у вас еще не установлен поставщик поддержки и вы не добавили в команду параметр Форцебутстрап, PackageManagement предложит установить поставщик.</span><span class="sxs-lookup"><span data-stu-id="f1894-138">When you try to install a package, if you do not already have the supporting provider installed, and you do not add the ForceBootstrap parameter to your command, PackageManagement prompts you to install the provider.</span></span>

<span data-ttu-id="f1894-139">При указании поставщика пакетов в команде PackageManagement могут быть доступны динамические параметры, характерные для данного поставщика пакетов.</span><span class="sxs-lookup"><span data-stu-id="f1894-139">Specifying a package provider in your PackageManagement command can make dynamic parameters available that are specific to that package provider.</span></span> <span data-ttu-id="f1894-140">При запуске Get-Help для конкретного командлета PackageManagement возвращается список наборов параметров, объединяющий динамические параметры для доступных поставщиков пакетов в отдельных наборах параметров.</span><span class="sxs-lookup"><span data-stu-id="f1894-140">When you run Get-Help for a specific PackageManagement cmdlet, a list of parameter sets are returned, grouping dynamic parameters for available package providers in separate parameter sets.</span></span>

<span data-ttu-id="f1894-141">Дополнительные сведения о проекте PackageManagement</span><span class="sxs-lookup"><span data-stu-id="f1894-141">More Information About the PackageManagement Project</span></span>

<span data-ttu-id="f1894-142">Дополнительные сведения о проекте PackageManagement Open Development, включая создание поставщика пакетов PackageManagement, см. в проекте PackageManagement на сайте GitHub по адресу https://oneget.org .</span><span class="sxs-lookup"><span data-stu-id="f1894-142">For more information about the PackageManagement open development project, including how to create a PackageManagement package provider, see the PackageManagement project on GitHub at https://oneget.org.</span></span>

## <a name="see-also"></a><span data-ttu-id="f1894-143">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="f1894-143">SEE ALSO</span></span>

[<span data-ttu-id="f1894-144">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="f1894-144">Get-PackageProvider</span></span>](xref:PackageManagement.Get-PackageProvider)

[<span data-ttu-id="f1894-145">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="f1894-145">Get-PackageSource</span></span>](xref:PackageManagement.Get-PackageSource)

[<span data-ttu-id="f1894-146">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="f1894-146">Register-PackageSource</span></span>](xref:PackageManagement.Register-PackageSource)

[<span data-ttu-id="f1894-147">Set-PackageSource</span><span class="sxs-lookup"><span data-stu-id="f1894-147">Set-PackageSource</span></span>](xref:PackageManagement.Set-PackageSource)

[<span data-ttu-id="f1894-148">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="f1894-148">Unregister-PackageSource</span></span>](xref:PackageManagement.Unregister-PackageSource)

[<span data-ttu-id="f1894-149">Get-Package</span><span class="sxs-lookup"><span data-stu-id="f1894-149">Get-Package</span></span>](xref:PackageManagement.Get-Package)

[<span data-ttu-id="f1894-150">Find-Package</span><span class="sxs-lookup"><span data-stu-id="f1894-150">Find-Package</span></span>](xref:PackageManagement.Find-Package)

[<span data-ttu-id="f1894-151">Install-Package</span><span class="sxs-lookup"><span data-stu-id="f1894-151">Install-Package</span></span>](xref:PackageManagement.Install-Package)

[<span data-ttu-id="f1894-152">Save-Package</span><span class="sxs-lookup"><span data-stu-id="f1894-152">Save-Package</span></span>](xref:PackageManagement.Save-Package)

[<span data-ttu-id="f1894-153">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="f1894-153">Uninstall-Package</span></span>](xref:PackageManagement.Uninstall-Package)

