---
description: PackageManagement — это агрегатор для диспетчеров пакетов программного обеспечения.
keywords: powershell,командлет
Locale: en-US
ms.date: 03/30/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_packagemanagement?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PackageManagement
ms.openlocfilehash: 8fd5d8e059d09556f0e7efa6b68ab4a7c018d3c0
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231378"
---
# <a name="about-packagemanagement"></a><span data-ttu-id="88de0-104">Сведения о PackageManagement</span><span class="sxs-lookup"><span data-stu-id="88de0-104">About PackageManagement</span></span>

## <a name="short-description"></a><span data-ttu-id="88de0-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="88de0-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="88de0-106">PackageManagement — это агрегатор для диспетчеров пакетов программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="88de0-106">PackageManagement is an aggregator for software package managers.</span></span>

## <a name="long-description"></a><span data-ttu-id="88de0-107">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="88de0-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="88de0-108">Функция PackageManagement появилась в Windows PowerShell 5,0.</span><span class="sxs-lookup"><span data-stu-id="88de0-108">PackageManagement functionality was introduced in Windows PowerShell 5.0.</span></span>

<span data-ttu-id="88de0-109">PackageManagement — это единый интерфейс для систем управления пакетами программного обеспечения; Командлеты PackageManagement можно использовать для выполнения задач обнаружения программного обеспечения, установки и инвентаризации (СДИИ).</span><span class="sxs-lookup"><span data-stu-id="88de0-109">PackageManagement is a unified interface for software package management systems; you can run PackageManagement cmdlets to perform software discovery, installation, and inventory (SDII) tasks.</span></span> <span data-ttu-id="88de0-110">Независимо от базовой технологии установки можно выполнять общие командлеты в модуле PackageManagement для поиска, установки и удаления пакетов. добавлять, удалять и запрашивать репозитории пакетов; и запускают запросы на компьютере, чтобы определить, какие пакеты программного обеспечения установлены.</span><span class="sxs-lookup"><span data-stu-id="88de0-110">Regardless of the underlying installation technology, you can run the common cmdlets in the PackageManagement module to search for, install, or uninstall packages; add, remove, and query package repositories; and run queries on a computer to determine which software packages are installed.</span></span>

<span data-ttu-id="88de0-111">PackageManagement поддерживает гибкую модель подключаемых модулей, которая обеспечивает поддержку других систем управления пакетами программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="88de0-111">PackageManagement supports a flexible plug-in model that enables support for other software package management systems.</span></span>

<span data-ttu-id="88de0-112">Модуль PackageManagement входит в состав Windows PowerShell 5,0 и более поздних выпусков PowerShell и работает на трех уровнях структуры управления пакетами: поставщиками пакетов, источниками пакетов и самими пакетами.</span><span class="sxs-lookup"><span data-stu-id="88de0-112">The PackageManagement module is included with Windows PowerShell 5.0 and later releases of PowerShell, and works on three levels of package management structure: package providers, package sources, and the packages themselves.</span></span> <span data-ttu-id="88de0-113">Давайте определим некоторые термины:</span><span class="sxs-lookup"><span data-stu-id="88de0-113">Let us define some terms:</span></span>

- <span data-ttu-id="88de0-114">Диспетчер пакетов: система управления пакетами программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="88de0-114">Package manager: Software package management system.</span></span> <span data-ttu-id="88de0-115">В терминах PackageManagement это поставщик пакетов.</span><span class="sxs-lookup"><span data-stu-id="88de0-115">In PackageManagement terms, this is a package provider.</span></span>
- <span data-ttu-id="88de0-116">Поставщик пакетов: термин PackageManagement для диспетчера пакетов.</span><span class="sxs-lookup"><span data-stu-id="88de0-116">Package provider: PackageManagement term for a package manager.</span></span> <span data-ttu-id="88de0-117">Примерами могут быть установщик Windows, шоколад и другие.</span><span class="sxs-lookup"><span data-stu-id="88de0-117">Examples can include Windows Installer, Chocolatey, and others.</span></span>
- <span data-ttu-id="88de0-118">Источник пакета: URL-адрес, локальная папка или общая сетевая папка, в которой поставщики пакетов настраиваются для использования в качестве репозитория.</span><span class="sxs-lookup"><span data-stu-id="88de0-118">Package source: A URL, local folder, or network shared folder that you configure package providers to use as a repository.</span></span>
- <span data-ttu-id="88de0-119">Package — это программное обеспечение, которое управляется поставщиком пакетов и хранится в определенном источнике пакета.</span><span class="sxs-lookup"><span data-stu-id="88de0-119">Package: A piece of software that a package provider manages, and that is stored in a specific package source.</span></span>

<span data-ttu-id="88de0-120">Модуль PackageManagement содержит следующие командлеты.</span><span class="sxs-lookup"><span data-stu-id="88de0-120">The PackageManagement module includes the following cmdlets.</span></span> <span data-ttu-id="88de0-121">Дополнительные сведения см. в справке [PackageManagement](/powershell/module/packagemanagement) .</span><span class="sxs-lookup"><span data-stu-id="88de0-121">For more information, see the [PackageManagement](/powershell/module/packagemanagement) help.</span></span>

- <span data-ttu-id="88de0-122">`Get-PackageProvider`: Возвращает список поставщиков пакетов, подключенных к PackageManagement.</span><span class="sxs-lookup"><span data-stu-id="88de0-122">`Get-PackageProvider`: Returns a list of package providers that are  connected to PackageManagement.</span></span>
- <span data-ttu-id="88de0-123">`Get-PackageSource`: Возвращает список источников пакетов, зарегистрированных для поставщика пакетов.</span><span class="sxs-lookup"><span data-stu-id="88de0-123">`Get-PackageSource`: Gets a list of package sources that are registered for a package provider.</span></span>
- <span data-ttu-id="88de0-124">`Register-PackageSource`: Добавляет источник пакета для указанного поставщика пакетов.</span><span class="sxs-lookup"><span data-stu-id="88de0-124">`Register-PackageSource`: Adds a package source for a specified package provider.</span></span>
- <span data-ttu-id="88de0-125">`Set-PackageSource`: Задает свойства для существующего источника пакета.</span><span class="sxs-lookup"><span data-stu-id="88de0-125">`Set-PackageSource`: Sets properties on an existing package source.</span></span>
- <span data-ttu-id="88de0-126">`Unregister-PackageSource`: Удаляет зарегистрированный источник пакета.</span><span class="sxs-lookup"><span data-stu-id="88de0-126">`Unregister-PackageSource`: Removes a registered package source.</span></span>
- <span data-ttu-id="88de0-127">`Get-Package`: Возвращает список установленных программных пакетов.</span><span class="sxs-lookup"><span data-stu-id="88de0-127">`Get-Package`: Returns a list of installed software packages.</span></span>
- <span data-ttu-id="88de0-128">`Find-Package`: Поиск пакетов программного обеспечения в доступных источниках пакетов.</span><span class="sxs-lookup"><span data-stu-id="88de0-128">`Find-Package`: Finds software packages in available package sources.</span></span>
- <span data-ttu-id="88de0-129">`Install-Package`: Устанавливает один или несколько пакетов программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="88de0-129">`Install-Package`: Installs one or more software packages.</span></span>
- <span data-ttu-id="88de0-130">`Save-Package`: Сохраняет пакеты на локальном компьютере, не устанавливая их.</span><span class="sxs-lookup"><span data-stu-id="88de0-130">`Save-Package`: Saves packages to the local computer without installing them.</span></span>
- <span data-ttu-id="88de0-131">`Uninstall-Package`: Удаляет один или несколько пакетов программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="88de0-131">`Uninstall-Package`: Uninstalls one or more software packages.</span></span>

### <a name="package-provider-bootstrapping-and-dynamic-cmdlet-parameters"></a><span data-ttu-id="88de0-132">Начальная загрузка поставщика пакетов и параметры динамических командлетов</span><span class="sxs-lookup"><span data-stu-id="88de0-132">Package Provider Bootstrapping and Dynamic Cmdlet Parameters</span></span>

<span data-ttu-id="88de0-133">По умолчанию PackageManagement поставляется с основным поставщиком начальной загрузки.</span><span class="sxs-lookup"><span data-stu-id="88de0-133">By default, PackageManagement ships with a core bootstrap provider.</span></span> <span data-ttu-id="88de0-134">Вы можете установить дополнительные поставщики пакетов по мере необходимости, заполнив начальную загрузку поставщиков. Это значит, что отвечает на запрос на автоматическую установку поставщика из веб-службы.</span><span class="sxs-lookup"><span data-stu-id="88de0-134">You can install additional package providers as you need them by bootstrapping the providers; that is, responding to a prompt to install the provider automatically, from a web service.</span></span> <span data-ttu-id="88de0-135">Поставщик пакетов можно указать с помощью любого командлета PackageManagement; Если указанный поставщик недоступен, PackageManagement предлагает выполнить начальную загрузку (или автоматическую установку) поставщика.</span><span class="sxs-lookup"><span data-stu-id="88de0-135">You can specify a package provider with any PackageManagement cmdlet; if the specified provider is not available, PackageManagement prompts you to bootstrap (or automatically install) the provider.</span></span> <span data-ttu-id="88de0-136">В следующих примерах, если поставщик шоколада еще не установлен, начальная загрузка PackageManagement устанавливает поставщик.</span><span class="sxs-lookup"><span data-stu-id="88de0-136">In the following examples, if the Chocolatey provider is not already installed, PackageManagement bootstrapping installs the provider.</span></span>

```powershell
Find-Package -Provider Chocolatey <PackageName>
```

<span data-ttu-id="88de0-137">Если поставщик шоколад еще не установлен, при выполнении предыдущей команды будет предложено установить его.</span><span class="sxs-lookup"><span data-stu-id="88de0-137">If the Chocolatey provider is not already installed, when you run the preceding command, you are prompted to install it.</span></span>

```powershell
Install-Package <Chocolatey package Name> -ForceBootstrap
```

<span data-ttu-id="88de0-138">Если поставщик шоколад еще не установлен, при выполнении предыдущей команды поставщик устанавливается; Но поскольку в команду был добавлен параметр Форцебутстрап, вам не будет предложено установить его. как поставщик, так и пакет устанавливаются автоматически.</span><span class="sxs-lookup"><span data-stu-id="88de0-138">If the Chocolatey provider is not already installed, when you run the preceding command, the provider is installed; but because the ForceBootstrap parameter has been added to the command, you are not prompted to install it; both the provider and the package are installed automatically.</span></span>

<span data-ttu-id="88de0-139">При попытке установить пакет, если у вас еще не установлен поставщик поддержки и вы не добавили в команду параметр Форцебутстрап, PackageManagement предложит установить поставщик.</span><span class="sxs-lookup"><span data-stu-id="88de0-139">When you try to install a package, if you do not already have the supporting provider installed, and you do not add the ForceBootstrap parameter to your command, PackageManagement prompts you to install the provider.</span></span>

<span data-ttu-id="88de0-140">При указании поставщика пакетов в команде PackageManagement могут быть доступны динамические параметры, характерные для данного поставщика пакетов.</span><span class="sxs-lookup"><span data-stu-id="88de0-140">Specifying a package provider in your PackageManagement command can make dynamic parameters available that are specific to that package provider.</span></span> <span data-ttu-id="88de0-141">При запуске Get-Help для конкретного командлета PackageManagement возвращается список наборов параметров, объединяющий динамические параметры для доступных поставщиков пакетов в отдельных наборах параметров.</span><span class="sxs-lookup"><span data-stu-id="88de0-141">When you run Get-Help for a specific PackageManagement cmdlet, a list of parameter sets are returned, grouping dynamic parameters for available package providers in separate parameter sets.</span></span>

<span data-ttu-id="88de0-142">Дополнительные сведения о проекте PackageManagement</span><span class="sxs-lookup"><span data-stu-id="88de0-142">More Information About the PackageManagement Project</span></span>

<span data-ttu-id="88de0-143">Дополнительные сведения о проекте PackageManagement Open Development, включая создание поставщика пакетов PackageManagement, см. в проекте PackageManagement на сайте GitHub по адресу https://oneget.org .</span><span class="sxs-lookup"><span data-stu-id="88de0-143">For more information about the PackageManagement open development project, including how to create a PackageManagement package provider, see the PackageManagement project on GitHub at https://oneget.org.</span></span>

## <a name="see-also"></a><span data-ttu-id="88de0-144">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="88de0-144">SEE ALSO</span></span>

[<span data-ttu-id="88de0-145">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="88de0-145">Get-PackageProvider</span></span>](xref:PackageManagement.Get-PackageProvider)

[<span data-ttu-id="88de0-146">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="88de0-146">Get-PackageSource</span></span>](xref:PackageManagement.Get-PackageSource)

[<span data-ttu-id="88de0-147">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="88de0-147">Register-PackageSource</span></span>](xref:PackageManagement.Register-PackageSource)

[<span data-ttu-id="88de0-148">Set-PackageSource</span><span class="sxs-lookup"><span data-stu-id="88de0-148">Set-PackageSource</span></span>](xref:PackageManagement.Set-PackageSource)

[<span data-ttu-id="88de0-149">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="88de0-149">Unregister-PackageSource</span></span>](xref:PackageManagement.Unregister-PackageSource)

[<span data-ttu-id="88de0-150">Get-Package</span><span class="sxs-lookup"><span data-stu-id="88de0-150">Get-Package</span></span>](xref:PackageManagement.Get-Package)

[<span data-ttu-id="88de0-151">Find-Package</span><span class="sxs-lookup"><span data-stu-id="88de0-151">Find-Package</span></span>](xref:PackageManagement.Find-Package)

[<span data-ttu-id="88de0-152">Install-Package</span><span class="sxs-lookup"><span data-stu-id="88de0-152">Install-Package</span></span>](xref:PackageManagement.Install-Package)

[<span data-ttu-id="88de0-153">Save-Package</span><span class="sxs-lookup"><span data-stu-id="88de0-153">Save-Package</span></span>](xref:PackageManagement.Save-Package)

[<span data-ttu-id="88de0-154">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="88de0-154">Uninstall-Package</span></span>](xref:PackageManagement.Uninstall-Package)
