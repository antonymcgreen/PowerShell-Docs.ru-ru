---
ms.date: 06/20/2018
keywords: dsc,powershell,конфигурация,установка
title: Ресурс PackageManagement DSC
ms.openlocfilehash: 18cbbfe0715c82dcfdf4a5fb6ee36ee814e43d3b
ms.sourcegitcommit: e04292a9c10de9a8391d529b7f7aa3753b362dbe
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 01/04/2019
ms.locfileid: "54047716"
---
# <a name="dsc-packagemanagement-resource"></a><span data-ttu-id="8352c-103">Ресурс PackageManagement DSC</span><span class="sxs-lookup"><span data-stu-id="8352c-103">DSC PackageManagement Resource</span></span>

<span data-ttu-id="8352c-104">Область применения. Windows PowerShell 4.0, Windows PowerShell 5.0, Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="8352c-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0, Windows PowerShell 5.1</span></span>

<span data-ttu-id="8352c-105">Ресурс **PackageManagement** в службе настройки требуемого состояния Windows PowerShell (DSC) предоставляет механизм установки пакетов управления пакетами на целевом узле или их удаления.</span><span class="sxs-lookup"><span data-stu-id="8352c-105">The **PackageManagement** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to install or uninstall Package Management packages on a target node.</span></span> <span data-ttu-id="8352c-106">Для этого ресурса требуется модуль **PackageManagement**, доступный из [http://PowerShellGallery.com](http://PowerShellGallery.com).</span><span class="sxs-lookup"><span data-stu-id="8352c-106">This resource requires the **PackageManagement** module, available from [http://PowerShellGallery.com](http://PowerShellGallery.com).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8352c-107">Указанные ниже сведения о свойствах относятся к модулю **PackageManagement** версии 1.1.7.0 и новее.</span><span class="sxs-lookup"><span data-stu-id="8352c-107">The **PackageManagement** module should be at least version 1.1.7.0 for the following property information to be correct.</span></span>

## <a name="syntax"></a><span data-ttu-id="8352c-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8352c-108">Syntax</span></span>

```
PackageManagement [string] #ResourceName
{
    Name = [string]
    [AdditionalParameters = [HashTable]]
    [DependsOn = [string[]]]
    [Ensure = [string]{ Absent | Present }]
    [MaximumVersion = [string]]
    [MinimumVersion = [string]]
    [ProviderName = [string]]
    [PsDscRunAsCredential = [PSCredential]]
    [RequiredVersion = [string]]
    [Source = [string]]
    [SourceCredential = [PSCredential]]
}
```

## <a name="properties"></a><span data-ttu-id="8352c-109">Свойства</span><span class="sxs-lookup"><span data-stu-id="8352c-109">Properties</span></span>

| <span data-ttu-id="8352c-110">Свойство</span><span class="sxs-lookup"><span data-stu-id="8352c-110">Property</span></span> | <span data-ttu-id="8352c-111">Описание</span><span class="sxs-lookup"><span data-stu-id="8352c-111">Description</span></span> |
| --- | --- |
| <span data-ttu-id="8352c-112">Name</span><span class="sxs-lookup"><span data-stu-id="8352c-112">Name</span></span>| <span data-ttu-id="8352c-113">Указывает имя устанавливаемого или удаляемого пакета.</span><span class="sxs-lookup"><span data-stu-id="8352c-113">Specifies the name of the Package to be installed or uninstalled.</span></span>|
| <span data-ttu-id="8352c-114">AdditionalParameters</span><span class="sxs-lookup"><span data-stu-id="8352c-114">AdditionalParameters</span></span>| <span data-ttu-id="8352c-115">Предоставляет определенную хэш-таблицу параметров, которые передаются в аргумент `Get-Package -AdditionalArguments`.</span><span class="sxs-lookup"><span data-stu-id="8352c-115">Provider specific hashtable of parameters that would be passed to `Get-Package -AdditionalArguments`.</span></span> <span data-ttu-id="8352c-116">Например, для поставщика NuGet можно передать дополнительные параметры, такие как DestinationPath.</span><span class="sxs-lookup"><span data-stu-id="8352c-116">For example, for NuGet provider you can pass additional parameters like DestinationPath.</span></span>|
| <span data-ttu-id="8352c-117">Ensure</span><span class="sxs-lookup"><span data-stu-id="8352c-117">Ensure</span></span>| <span data-ttu-id="8352c-118">Определяет, следует ли установить или удалить пакет.</span><span class="sxs-lookup"><span data-stu-id="8352c-118">Determines whether the package is to be installed or uninstalled.</span></span>|
| <span data-ttu-id="8352c-119">MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="8352c-119">MaximumVersion</span></span>|<span data-ttu-id="8352c-120">Указывает максимальную версию пакета, которую требуется найти.</span><span class="sxs-lookup"><span data-stu-id="8352c-120">Specifies the maximum allowed version of the package that you want to find.</span></span> <span data-ttu-id="8352c-121">Если этот параметр не указан, ресурс находит новейшую версию пакета.</span><span class="sxs-lookup"><span data-stu-id="8352c-121">If you do not add this parameter, the resource finds the highest available version of the package.</span></span>|
| <span data-ttu-id="8352c-122">MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="8352c-122">MinimumVersion</span></span>|<span data-ttu-id="8352c-123">Указывает минимальную версию пакета, которую требуется найти.</span><span class="sxs-lookup"><span data-stu-id="8352c-123">Specifies the minimum allowed version of the package that you want to find.</span></span> <span data-ttu-id="8352c-124">Если этот параметр не указан, ресурс находит новейшую доступную версию пакета, номер которой не превышает тот, что указан в параметре _MaximumVersion_.</span><span class="sxs-lookup"><span data-stu-id="8352c-124">If you do not add this parameter, the resource finds the highest available version of the package that also satisfies any maximum specified version specified by the _MaximumVersion_ parameter.</span></span>|
| <span data-ttu-id="8352c-125">ProviderName</span><span class="sxs-lookup"><span data-stu-id="8352c-125">ProviderName</span></span>| <span data-ttu-id="8352c-126">Указывает имя поставщика пакетов, на который распространяется область поиска пакетов.</span><span class="sxs-lookup"><span data-stu-id="8352c-126">Specifies a package provider name to which to scope your package search.</span></span> <span data-ttu-id="8352c-127">Чтобы получить имена поставщиков пакетов, выполните командлет `Get-PackageProvider`.</span><span class="sxs-lookup"><span data-stu-id="8352c-127">You can get package provider names by running the `Get-PackageProvider` cmdlet.</span></span>|
| <span data-ttu-id="8352c-128">RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="8352c-128">RequiredVersion</span></span>| <span data-ttu-id="8352c-129">Указывает точную версию пакета, который вы хотите установить.</span><span class="sxs-lookup"><span data-stu-id="8352c-129">Specifies the exact version of the package that you want to install.</span></span> <span data-ttu-id="8352c-130">Если этот параметр не указан, ресурс DSC устанавливает новейшую версию пакета, номер которой не превышает тот, что указан в параметре _MaximumVersion_.</span><span class="sxs-lookup"><span data-stu-id="8352c-130">If you do not specify this parameter, this DSC resource installs the newest available version of the package that also satisfies any maximum version specified by the _MaximumVersion_ parameter.</span></span>|
| <span data-ttu-id="8352c-131">Источник</span><span class="sxs-lookup"><span data-stu-id="8352c-131">Source</span></span>| <span data-ttu-id="8352c-132">Указывает имя источника пакета, в котором его можно найти.</span><span class="sxs-lookup"><span data-stu-id="8352c-132">Specifies the name of the package source where the package can be found.</span></span> <span data-ttu-id="8352c-133">Это может быть универсальный код ресурса (URI) или источник, зарегистрированный с помощью командлета `Register-PackageSource` или ресурса DSC PackageManagementSource.</span><span class="sxs-lookup"><span data-stu-id="8352c-133">This can either be a URI or a source registered with `Register-PackageSource` or PackageManagementSource DSC resource.</span></span>|
| <span data-ttu-id="8352c-134">SourceCredential</span><span class="sxs-lookup"><span data-stu-id="8352c-134">SourceCredential</span></span> | <span data-ttu-id="8352c-135">Указывает учетную запись пользователя с правами для установки пакета для заданного поставщика или источника пакетов.</span><span class="sxs-lookup"><span data-stu-id="8352c-135">Specifies a user account that has rights to install a package for a specified package provider or source.</span></span>|

## <a name="additional-parameters"></a><span data-ttu-id="8352c-136">Дополнительные параметры</span><span class="sxs-lookup"><span data-stu-id="8352c-136">Additional Parameters</span></span>

<span data-ttu-id="8352c-137">В следующей таблице перечислены параметры свойства AdditionalParameters.</span><span class="sxs-lookup"><span data-stu-id="8352c-137">The following table lists options for the AdditionalParameters property.</span></span>

| <span data-ttu-id="8352c-138">Параметр</span><span class="sxs-lookup"><span data-stu-id="8352c-138">Parameter</span></span> | <span data-ttu-id="8352c-139">Описание</span><span class="sxs-lookup"><span data-stu-id="8352c-139">Description</span></span> |
| --- | --- |
| <span data-ttu-id="8352c-140">DestinationPath</span><span class="sxs-lookup"><span data-stu-id="8352c-140">DestinationPath</span></span>| <span data-ttu-id="8352c-141">Используется поставщиками, такими как встроенный поставщик NuGet.</span><span class="sxs-lookup"><span data-stu-id="8352c-141">Used by providers such as the built-in Nuget Provider.</span></span> <span data-ttu-id="8352c-142">Указывает расположение файла, в котором вы хотите установить пакет.</span><span class="sxs-lookup"><span data-stu-id="8352c-142">Specifies a file location where you want the package to be installed.</span></span>|
| <span data-ttu-id="8352c-143">InstallationPolicy</span><span class="sxs-lookup"><span data-stu-id="8352c-143">InstallationPolicy</span></span>| <span data-ttu-id="8352c-144">Используется поставщиками, такими как встроенный поставщик NuGet.</span><span class="sxs-lookup"><span data-stu-id="8352c-144">Used by providers such as the built-in Nuget Provider.</span></span> <span data-ttu-id="8352c-145">Определяет, доверяете ли вы источнику пакета.</span><span class="sxs-lookup"><span data-stu-id="8352c-145">Determines whether you trust the package's source.</span></span> <span data-ttu-id="8352c-146">`Untrusted` или `Trusted`.</span><span class="sxs-lookup"><span data-stu-id="8352c-146">One of: `Untrusted`, `Trusted`.</span></span>|

## <a name="example"></a><span data-ttu-id="8352c-147">Пример</span><span class="sxs-lookup"><span data-stu-id="8352c-147">Example</span></span>

<span data-ttu-id="8352c-148">В этом примере устанавливается пакет NuGet **JQuery** и модуль PowerShell **GistProvider** с помощью ресурса DSC **PackageManagement**.</span><span class="sxs-lookup"><span data-stu-id="8352c-148">This example installs the **JQuery** NuGet package and **GistProvider** PowerShell module using the **PackageManagement** DSC resource.</span></span> <span data-ttu-id="8352c-149">В этом примере сначала обеспечивается доступность нужных источников пакета, а затем определяется ожидаемое состояние пакетов **JQuery** и **GistProvider** (для NuGet и PowerShell).</span><span class="sxs-lookup"><span data-stu-id="8352c-149">This example first ensures the required package sources are available then defines the expected state of the **JQuery** and **GistProvider** packages (NuGet and PowerShell, respectively).</span></span>

```powershell
Configuration PackageTest
{
    PackageManagementSource SourceRepository
    {
        Ensure      = "Present"
        Name        = "MyNuget"
        ProviderName= "Nuget"
        SourceLocation   = "http://nuget.org/api/v2/"
        InstallationPolicy ="Trusted"
    }

    PackageManagementSource PSGallery
    {
        Ensure      = "Present"
        Name        = "psgallery"
        ProviderName= "PowerShellGet"
        SourceLocation   = "https://www.powershellgallery.com/api/v2/"
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