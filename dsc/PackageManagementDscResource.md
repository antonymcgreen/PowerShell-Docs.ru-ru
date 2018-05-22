---
ms.date: 06/12/2017
keywords: dsc,powershell,конфигурация,установка
title: Ресурс PackageManagement DSC
ms.openlocfilehash: f850c389214fe5adf139c3bd01fb60addc5ec238
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/16/2018
---
# <a name="dsc-packagemanagement-resource"></a><span data-ttu-id="d4a29-103">Ресурс PackageManagement DSC</span><span class="sxs-lookup"><span data-stu-id="d4a29-103">DSC PackageManagement Resource</span></span>

> <span data-ttu-id="d4a29-104">Область применения: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="d4a29-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="d4a29-105">Ресурс **PackageManagement** в службе настройки требуемого состояния Windows PowerShell (DSC) предоставляет механизм установки пакетов управления пакетами на целевом узле или их удаления.</span><span class="sxs-lookup"><span data-stu-id="d4a29-105">The **PackageManagement** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to install or uninstall Package Management packages on a target node.</span></span> <span data-ttu-id="d4a29-106">Для этого ресурса требуется модуль **PackageManagement**, доступный из http://PowerShellGallery.com.</span><span class="sxs-lookup"><span data-stu-id="d4a29-106">This resource requires the **PackageManagement** module, available from http://PowerShellGallery.com.</span></span>

## <a name="syntax"></a><span data-ttu-id="d4a29-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d4a29-107">Syntax</span></span>

```
PackageManagement [string] #ResourceName
{
    Name = [string]
    [ Source = [string] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ RequiredVersion = [string] ]
    [ MinimumVersion = [string] ]
    [ MaximumVersion = [string] ]
    [ SourceCredential = [PSCredential] ]
    [ ProviderName = [string] ]
    [ AdditionalParameters = [Microsoft.Management.Infrastructure.CimInstance[]] ]
}
```

## <a name="properties"></a><span data-ttu-id="d4a29-108">Свойства</span><span class="sxs-lookup"><span data-stu-id="d4a29-108">Properties</span></span>
|  <span data-ttu-id="d4a29-109">Свойство</span><span class="sxs-lookup"><span data-stu-id="d4a29-109">Property</span></span>  |  <span data-ttu-id="d4a29-110">Описание</span><span class="sxs-lookup"><span data-stu-id="d4a29-110">Description</span></span>   |
|---|---|
| <span data-ttu-id="d4a29-111">Name</span><span class="sxs-lookup"><span data-stu-id="d4a29-111">Name</span></span>| <span data-ttu-id="d4a29-112">Указывает имя устанавливаемого или удаляемого пакета.</span><span class="sxs-lookup"><span data-stu-id="d4a29-112">Specifies the name of the Package to be installed or uninstalled.</span></span>|
| <span data-ttu-id="d4a29-113">Источник</span><span class="sxs-lookup"><span data-stu-id="d4a29-113">Source</span></span>| <span data-ttu-id="d4a29-114">Указывает имя источника пакета, в котором его можно найти.</span><span class="sxs-lookup"><span data-stu-id="d4a29-114">Specifies the name of the package source where the package can be found.</span></span> <span data-ttu-id="d4a29-115">Это может быть URI или источник, зарегистрированный с помощью ресурса DSC Register-PackageSource или PackageManagementSource.</span><span class="sxs-lookup"><span data-stu-id="d4a29-115">This can either be a URI or a source registered with Register-PackageSource or PackageManagementSource DSC resource.</span></span> <span data-ttu-id="d4a29-116">MSFT_PackageManagementSource ресурса DSC может также зарегистрировать источник пакета.</span><span class="sxs-lookup"><span data-stu-id="d4a29-116">The DSC resource MSFT_PackageManagementSource can also register a package source.</span></span>|
| <span data-ttu-id="d4a29-117">Ensure</span><span class="sxs-lookup"><span data-stu-id="d4a29-117">Ensure</span></span>| <span data-ttu-id="d4a29-118">Определяет, следует ли установить или удалить пакет.</span><span class="sxs-lookup"><span data-stu-id="d4a29-118">Determines whether the package is to be installed or uninstalled.</span></span>|
| <span data-ttu-id="d4a29-119">RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="d4a29-119">RequiredVersion</span></span>| <span data-ttu-id="d4a29-120">Указывает точную версию пакета, который вы хотите установить.</span><span class="sxs-lookup"><span data-stu-id="d4a29-120">Specifies the exact version of the package that you want to install.</span></span> <span data-ttu-id="d4a29-121">Если вы не укажете этот параметр, ресурс DSC установит новейшую версию пакета, соответствующую максимальной версии, указанной в параметре MaximumVersion.</span><span class="sxs-lookup"><span data-stu-id="d4a29-121">If you do not specify this parameter, this DSC resource installs the newest available version of the package that also satisfies any maximum version specified by the MaximumVersion parameter.</span></span>|
| <span data-ttu-id="d4a29-122">MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="d4a29-122">MinimumVersion</span></span>| <span data-ttu-id="d4a29-123">Указывает минимальную версию пакета, которую вы хотите установить.</span><span class="sxs-lookup"><span data-stu-id="d4a29-123">Specifies the minimum allowed version of the package that you want to install.</span></span> <span data-ttu-id="d4a29-124">Если вы не добавите этот параметр, ресурс DSC установит новейшую версию пакета, соответствующую максимальной версии, указанной в параметре MaximumVersion.</span><span class="sxs-lookup"><span data-stu-id="d4a29-124">If you do not add this parameter, this DSC resource intalls the highest available version of the package that also satisfies any maximum specified version specified by the MaximumVersion parameter.</span></span>|
| <span data-ttu-id="d4a29-125">MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="d4a29-125">MaximumVersion</span></span>| <span data-ttu-id="d4a29-126">Указывает максимальную версию пакета, которую вы хотите установить.</span><span class="sxs-lookup"><span data-stu-id="d4a29-126">Specifies the maximum allowed version of the package that you want to install.</span></span> <span data-ttu-id="d4a29-127">Если вы не укажете этот параметр, ресурс DSC установит новейшую версию пакета.</span><span class="sxs-lookup"><span data-stu-id="d4a29-127">If you do not specify this parameter, this DSC resource installs the highest-numbered available version of the package.</span></span>|
| <span data-ttu-id="d4a29-128">SourceCredential</span><span class="sxs-lookup"><span data-stu-id="d4a29-128">SourceCredential</span></span> | <span data-ttu-id="d4a29-129">Указывает учетную запись пользователя с правами для установки пакета для заданного поставщика или источника пакетов.</span><span class="sxs-lookup"><span data-stu-id="d4a29-129">Specifies a user account that has rights to install a package for a specified package provider or source.</span></span>|
| <span data-ttu-id="d4a29-130">ProviderName</span><span class="sxs-lookup"><span data-stu-id="d4a29-130">ProviderName</span></span>| <span data-ttu-id="d4a29-131">Указывает имя поставщика пакетов, на который распространяется область поиска пакетов.</span><span class="sxs-lookup"><span data-stu-id="d4a29-131">Specifies a package provider name to which to scope your package search.</span></span> <span data-ttu-id="d4a29-132">Чтобы получить имена поставщика, запустите командлет Get-PackageProvider.</span><span class="sxs-lookup"><span data-stu-id="d4a29-132">You can get package provider names by running the Get-PackageProvider cmdlet.</span></span>|
| <span data-ttu-id="d4a29-133">AdditionalParameters</span><span class="sxs-lookup"><span data-stu-id="d4a29-133">AdditionalParameters</span></span>| <span data-ttu-id="d4a29-134">Специальные параметры поставщика, которые передаются как хэш-таблица.</span><span class="sxs-lookup"><span data-stu-id="d4a29-134">Provider specific parameters that are passed as an Hashtable.</span></span> <span data-ttu-id="d4a29-135">Например, для поставщика NuGet можно передать дополнительные параметры, такие как DestinationPath.</span><span class="sxs-lookup"><span data-stu-id="d4a29-135">For example, for NuGet provider you can pass additional parameters like DestinationPath.</span></span>|

## <a name="additional-parameters"></a><span data-ttu-id="d4a29-136">Дополнительные параметры</span><span class="sxs-lookup"><span data-stu-id="d4a29-136">Additional Parameters</span></span>
<span data-ttu-id="d4a29-137">В следующей таблице перечислены параметры свойства AdditionalParameters.</span><span class="sxs-lookup"><span data-stu-id="d4a29-137">The following table lists options for the AdditionalParameters property.</span></span>
|  <span data-ttu-id="d4a29-138">Параметр</span><span class="sxs-lookup"><span data-stu-id="d4a29-138">Parameter</span></span>  | <span data-ttu-id="d4a29-139">Описание</span><span class="sxs-lookup"><span data-stu-id="d4a29-139">Description</span></span>   |
|---|---|
| <span data-ttu-id="d4a29-140">DestinationPath</span><span class="sxs-lookup"><span data-stu-id="d4a29-140">DestinationPath</span></span>| <span data-ttu-id="d4a29-141">Используется поставщиками, такими как встроенный поставщик NuGet.</span><span class="sxs-lookup"><span data-stu-id="d4a29-141">Used by providers such as the built-in Nuget Provider.</span></span> <span data-ttu-id="d4a29-142">Указывает расположение файла, в котором вы хотите установить пакет.</span><span class="sxs-lookup"><span data-stu-id="d4a29-142">Specifies a file location where you want the package to be installed.</span></span>|
| <span data-ttu-id="d4a29-143">InstallationPolicy</span><span class="sxs-lookup"><span data-stu-id="d4a29-143">InstallationPolicy</span></span>| <span data-ttu-id="d4a29-144">Используется поставщиками, такими как встроенный поставщик NuGet.</span><span class="sxs-lookup"><span data-stu-id="d4a29-144">Used by providers such as the built-in Nuget Provider.</span></span> <span data-ttu-id="d4a29-145">Определяет, доверяете ли вы источнику пакета.</span><span class="sxs-lookup"><span data-stu-id="d4a29-145">Determines whether you trust the package's source.</span></span> <span data-ttu-id="d4a29-146">Одно из двух значений: "Untrusted", "Trusted".</span><span class="sxs-lookup"><span data-stu-id="d4a29-146">One of: "Untrusted", "Trusted".</span></span>|

## <a name="example"></a><span data-ttu-id="d4a29-147">Пример</span><span class="sxs-lookup"><span data-stu-id="d4a29-147">Example</span></span>

<span data-ttu-id="d4a29-148">В этом примере устанавливается пакет NuGet **JQuery** и модуль PowerShell **GistProvider** с помощью ресурса DSC **PackageManagement**.</span><span class="sxs-lookup"><span data-stu-id="d4a29-148">This example installs the **JQuery** NuGet package and **GistProvider** PowerShell module using the **PackageManagement** DSC resource.</span></span> <span data-ttu-id="d4a29-149">В этом примере сначала обеспечивается доступность нужных источников пакета, а затем определяется ожидаемое состояние пакетов **JQuery** и **GistProvider** (для NuGet и PowerShell).</span><span class="sxs-lookup"><span data-stu-id="d4a29-149">This example first ensures the required package sources are available then defines the expected state of the **JQuery** and **GistProvider** packages (NuGet and PowerShell, respectively).</span></span>

```powershell
Configuration PackageTest
{
    PackageManagementSource SourceRepository
    {
        Ensure      = "Present"
        Name        = "MyNuget"
        ProviderName= "Nuget"
        SourceUri   = "http://nuget.org/api/v2/"
        InstallationPolicy ="Trusted"
    }

    PackageManagementSource PSGallery
    {
        Ensure      = "Present"
        Name        = "psgallery"
        ProviderName= "PowerShellGet"
        SourceUri   = "https://www.powershellgallery.com/api/v2/"
        InstallationPolicy ="Trusted"
    }

    PackageManagement NugetPackage
    {
        Ensure               = "Present"
        Name                 = "JQuery"
        AdditionalParameters = "$env:HomeDrive\nuget"
        RequiredVersion      = "2.0.1"
        DependsOn            = "[PackageManagementSource]SourceRepository"
    }

    PackageManagement PSModule
    {
        Ensure               = "Present"
        Name                 = "gistprovider"
        Source               = "PSGallery"
        DependsOn            = "[PackageManagementSource]PSGallery"
    }
}
```