---
ms.date: 07/15/2020
ms.topic: reference
title: Ресурс PackageManagement DSC
description: Ресурс PackageManagement DSC
ms.openlocfilehash: 83839adbef8bd8d3265a06b44a3101108b2a4486
ms.sourcegitcommit: 196c7f8cd24560cac70c88acc89909f17a86aea9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2020
ms.locfileid: "93142911"
---
# <a name="dsc-packagemanagement-resource"></a><span data-ttu-id="612de-103">Ресурс PackageManagement DSC</span><span class="sxs-lookup"><span data-stu-id="612de-103">DSC PackageManagement Resource</span></span>

<span data-ttu-id="612de-104">Область применения: Windows PowerShell 4.0, Windows PowerShell 5.0, Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="612de-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0, Windows PowerShell 5.1</span></span>

<span data-ttu-id="612de-105">Ресурс **PackageManagement** в службе настройки требуемого состояния Windows PowerShell (DSC) предоставляет механизм установки пакетов управления пакетами на целевом узле или их удаления.</span><span class="sxs-lookup"><span data-stu-id="612de-105">The **PackageManagement** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to install or uninstall Package Management packages on a target node.</span></span> <span data-ttu-id="612de-106">Для этого ресурса требуется модуль **PackageManagement** , доступный из [https://PowerShellGallery.com](https://PowerShellGallery.com).</span><span class="sxs-lookup"><span data-stu-id="612de-106">This resource requires the **PackageManagement** module, available from [https://PowerShellGallery.com](https://PowerShellGallery.com).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="612de-107">Указанные ниже сведения о свойствах относятся к модулю **PackageManagement** версии 1.1.7.0 и новее.</span><span class="sxs-lookup"><span data-stu-id="612de-107">The **PackageManagement** module should be at least version 1.1.7.0 for the following property information to be correct.</span></span>

[!INCLUDE [Updated DSC Resources](../../../../../includes/dsc-resources.md)]

## <a name="syntax"></a><span data-ttu-id="612de-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="612de-108">Syntax</span></span>

```Syntax
PackageManagement [string] #ResourceName
{
    Name = [string]
    [ AdditionalParameters = [HashTable] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string]{ Absent | Present } ]
    [ MaximumVersion = [string] ]
    [ MinimumVersion = [string] ]
    [ ProviderName = [string] ]
    [ PsDscRunAsCredential = [PSCredential] ]
    [ RequiredVersion = [string] ]
    [ Source = [string] ]
    [ SourceCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="612de-109">Свойства</span><span class="sxs-lookup"><span data-stu-id="612de-109">Properties</span></span>

|<span data-ttu-id="612de-110">Свойство</span><span class="sxs-lookup"><span data-stu-id="612de-110">Property</span></span> |<span data-ttu-id="612de-111">Описание</span><span class="sxs-lookup"><span data-stu-id="612de-111">Description</span></span> |
|---|---|
|<span data-ttu-id="612de-112">Имя</span><span class="sxs-lookup"><span data-stu-id="612de-112">Name</span></span> |<span data-ttu-id="612de-113">Указывает имя устанавливаемого или удаляемого пакета.</span><span class="sxs-lookup"><span data-stu-id="612de-113">Specifies the name of the Package to be installed or uninstalled.</span></span> |
|<span data-ttu-id="612de-114">AdditionalParameters</span><span class="sxs-lookup"><span data-stu-id="612de-114">AdditionalParameters</span></span> |<span data-ttu-id="612de-115">Предоставляет определенную хэш-таблицу параметров, которые передаются в аргумент `Get-Package -AdditionalArguments`.</span><span class="sxs-lookup"><span data-stu-id="612de-115">Provider specific hashtable of parameters that would be passed to `Get-Package -AdditionalArguments`.</span></span> <span data-ttu-id="612de-116">Например, для поставщика NuGet можно передать дополнительные параметры, такие как DestinationPath.</span><span class="sxs-lookup"><span data-stu-id="612de-116">For example, for NuGet provider you can pass additional parameters like DestinationPath.</span></span> |
|<span data-ttu-id="612de-117">MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="612de-117">MaximumVersion</span></span> |<span data-ttu-id="612de-118">Указывает максимальную версию пакета, которую требуется найти.</span><span class="sxs-lookup"><span data-stu-id="612de-118">Specifies the maximum allowed version of the package that you want to find.</span></span> <span data-ttu-id="612de-119">Если этот параметр не указан, ресурс находит новейшую версию пакета.</span><span class="sxs-lookup"><span data-stu-id="612de-119">If you do not add this parameter, the resource finds the highest available version of the package.</span></span> |
|<span data-ttu-id="612de-120">MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="612de-120">MinimumVersion</span></span> |<span data-ttu-id="612de-121">Указывает минимальную версию пакета, которую требуется найти.</span><span class="sxs-lookup"><span data-stu-id="612de-121">Specifies the minimum allowed version of the package that you want to find.</span></span> <span data-ttu-id="612de-122">Если этот параметр не указан, ресурс находит новейшую доступную версию пакета, номер которой не превышает тот, что указан в параметре **MaximumVersion** .</span><span class="sxs-lookup"><span data-stu-id="612de-122">If you do not add this parameter, the resource finds the highest available version of the package that also satisfies any maximum specified version specified by the **MaximumVersion** parameter.</span></span> |
|<span data-ttu-id="612de-123">ProviderName</span><span class="sxs-lookup"><span data-stu-id="612de-123">ProviderName</span></span> |<span data-ttu-id="612de-124">Указывает имя поставщика пакетов, на который распространяется область поиска пакетов.</span><span class="sxs-lookup"><span data-stu-id="612de-124">Specifies a package provider name to which to scope your package search.</span></span> <span data-ttu-id="612de-125">Чтобы получить имена поставщиков пакетов, выполните командлет `Get-PackageProvider`.</span><span class="sxs-lookup"><span data-stu-id="612de-125">You can get package provider names by running the `Get-PackageProvider` cmdlet.</span></span> |
|<span data-ttu-id="612de-126">RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="612de-126">RequiredVersion</span></span> |<span data-ttu-id="612de-127">Указывает точную версию пакета, который вы хотите установить.</span><span class="sxs-lookup"><span data-stu-id="612de-127">Specifies the exact version of the package that you want to install.</span></span> <span data-ttu-id="612de-128">Если этот параметр не указан, ресурс DSC устанавливает новейшую версию пакета, номер которой не превышает тот, что указан в параметре **MaximumVersion** .</span><span class="sxs-lookup"><span data-stu-id="612de-128">If you do not specify this parameter, this DSC resource installs the newest available version of the package that also satisfies any maximum version specified by the **MaximumVersion** parameter.</span></span> |
|<span data-ttu-id="612de-129">Источник</span><span class="sxs-lookup"><span data-stu-id="612de-129">Source</span></span> |<span data-ttu-id="612de-130">Указывает имя источника пакета, в котором его можно найти.</span><span class="sxs-lookup"><span data-stu-id="612de-130">Specifies the name of the package source where the package can be found.</span></span> <span data-ttu-id="612de-131">Это может быть универсальный код ресурса (URI) или источник, зарегистрированный с помощью командлета `Register-PackageSource` или ресурса DSC PackageManagementSource.</span><span class="sxs-lookup"><span data-stu-id="612de-131">This can either be a URI or a source registered with `Register-PackageSource` or PackageManagementSource DSC resource.</span></span> |
|<span data-ttu-id="612de-132">SourceCredential</span><span class="sxs-lookup"><span data-stu-id="612de-132">SourceCredential</span></span> |<span data-ttu-id="612de-133">Указывает учетную запись пользователя с правами для установки пакета для заданного поставщика или источника пакетов.</span><span class="sxs-lookup"><span data-stu-id="612de-133">Specifies a user account that has rights to install a package for a specified package provider or source.</span></span> |

## <a name="additional-parameters"></a><span data-ttu-id="612de-134">Дополнительные параметры</span><span class="sxs-lookup"><span data-stu-id="612de-134">Additional Parameters</span></span>

<span data-ttu-id="612de-135">В следующей таблице перечислены параметры свойства AdditionalParameters.</span><span class="sxs-lookup"><span data-stu-id="612de-135">The following table lists options for the AdditionalParameters property.</span></span>

|<span data-ttu-id="612de-136">Параметр</span><span class="sxs-lookup"><span data-stu-id="612de-136">Parameter</span></span> |<span data-ttu-id="612de-137">Описание</span><span class="sxs-lookup"><span data-stu-id="612de-137">Description</span></span> |
|---|---|
|<span data-ttu-id="612de-138">DestinationPath</span><span class="sxs-lookup"><span data-stu-id="612de-138">DestinationPath</span></span> |<span data-ttu-id="612de-139">Используется поставщиками, такими как встроенный поставщик NuGet.</span><span class="sxs-lookup"><span data-stu-id="612de-139">Used by providers such as the built-in Nuget Provider.</span></span> <span data-ttu-id="612de-140">Указывает расположение файла, в котором вы хотите установить пакет.</span><span class="sxs-lookup"><span data-stu-id="612de-140">Specifies a file location where you want the package to be installed.</span></span> |
|<span data-ttu-id="612de-141">InstallationPolicy</span><span class="sxs-lookup"><span data-stu-id="612de-141">InstallationPolicy</span></span> |<span data-ttu-id="612de-142">Используется поставщиками, такими как встроенный поставщик NuGet.</span><span class="sxs-lookup"><span data-stu-id="612de-142">Used by providers such as the built-in Nuget Provider.</span></span> <span data-ttu-id="612de-143">Определяет, доверяете ли вы источнику пакета.</span><span class="sxs-lookup"><span data-stu-id="612de-143">Determines whether you trust the package's source.</span></span> <span data-ttu-id="612de-144">Одно из двух значений: **Untrusted** или **Trusted** .</span><span class="sxs-lookup"><span data-stu-id="612de-144">One of: **Untrusted** or **Trusted** .</span></span> |

## <a name="common-properties"></a><span data-ttu-id="612de-145">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="612de-145">Common properties</span></span>

|<span data-ttu-id="612de-146">Свойство</span><span class="sxs-lookup"><span data-stu-id="612de-146">Property</span></span> |<span data-ttu-id="612de-147">Описание</span><span class="sxs-lookup"><span data-stu-id="612de-147">Description</span></span> |
|---|---|
|<span data-ttu-id="612de-148">DependsOn</span><span class="sxs-lookup"><span data-stu-id="612de-148">DependsOn</span></span> |<span data-ttu-id="612de-149">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="612de-149">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="612de-150">Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="612de-150">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="612de-151">Ensure</span><span class="sxs-lookup"><span data-stu-id="612de-151">Ensure</span></span> |<span data-ttu-id="612de-152">Определяет, следует ли установить или удалить пакет.</span><span class="sxs-lookup"><span data-stu-id="612de-152">Determines whether the package is to be installed or uninstalled.</span></span> <span data-ttu-id="612de-153">Значение по умолчанию — **Present** .</span><span class="sxs-lookup"><span data-stu-id="612de-153">The default value is **Present** .</span></span> |
|<span data-ttu-id="612de-154">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="612de-154">PsDscRunAsCredential</span></span> |<span data-ttu-id="612de-155">Задает учетные данные для выполнения всего ресурса от другого имени.</span><span class="sxs-lookup"><span data-stu-id="612de-155">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="612de-156">В WMF 5.0 было добавлено общее свойство **PsDscRunAsCredential** , разрешающее запуск любого ресурса DSC в контексте других учетных данных.</span><span class="sxs-lookup"><span data-stu-id="612de-156">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="612de-157">Дополнительные сведения см. в разделе [Использование учетных данных с ресурсами DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="612de-157">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="612de-158">Пример</span><span class="sxs-lookup"><span data-stu-id="612de-158">Example</span></span>

<span data-ttu-id="612de-159">В этом примере устанавливается пакет NuGet **JQuery** и модуль PowerShell **GistProvider** с помощью ресурса DSC **PackageManagement** .</span><span class="sxs-lookup"><span data-stu-id="612de-159">This example installs the **JQuery** NuGet package and **GistProvider** PowerShell module using the **PackageManagement** DSC resource.</span></span> <span data-ttu-id="612de-160">В этом примере сначала обеспечивается доступность нужных источников пакета, а затем определяется ожидаемое состояние пакетов **JQuery** и **GistProvider** (для NuGet и PowerShell).</span><span class="sxs-lookup"><span data-stu-id="612de-160">This example first ensures the required package sources are available then defines the expected state of the **JQuery** and **GistProvider** packages (NuGet and PowerShell, respectively).</span></span>

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
        SourceLocation   = "https://www.powershellgallery.com/api/v2"
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
