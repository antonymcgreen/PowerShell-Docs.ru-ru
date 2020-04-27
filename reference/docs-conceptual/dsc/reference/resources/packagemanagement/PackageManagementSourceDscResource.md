---
ms.date: 09/20/2019
keywords: dsc,powershell,конфигурация,установка
title: Ресурс PackageManagementSource DSC
ms.openlocfilehash: 20b7851e44751d4bd0add718d2f7294d5215ab70
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "71954791"
---
# <a name="dsc-packagemanagementsource-resource"></a><span data-ttu-id="425fa-103">Ресурс PackageManagementSource DSC</span><span class="sxs-lookup"><span data-stu-id="425fa-103">DSC PackageManagementSource Resource</span></span>

> <span data-ttu-id="425fa-104">Область применения: Windows PowerShell 4.0, Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="425fa-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="425fa-105">Ресурс **PackageManagementSource** в службе настройки требуемого состояния Windows PowerShell (DSC) предоставляет механизм регистрации или ее отмены для источников управления пакетами на целевом узле.</span><span class="sxs-lookup"><span data-stu-id="425fa-105">The **PackageManagementSource** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to register or unregister Package Management sources on a target node.</span></span>
<span data-ttu-id="425fa-106">**Источники управления пакетами, зарегистрированные этим способом, регистрируются в контексте системы, доступной для учетной записи системы или подсистемы DSC.**</span><span class="sxs-lookup"><span data-stu-id="425fa-106">**Package Management sources registered in this way are registered under the System context, usable by the System account or by the DSC engine.**</span></span> <span data-ttu-id="425fa-107">Для этого ресурса требуется модуль **PackageManagement** из [Коллекции PowerShell](https://PowerShellGallery.com).</span><span class="sxs-lookup"><span data-stu-id="425fa-107">This resource requires the **PackageManagement** module, available from the [PowerShell Gallery](https://PowerShellGallery.com).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="425fa-108">Указанные ниже сведения о свойствах относятся к модулю **PackageManagement** версии 1.1.7.0 и новее.</span><span class="sxs-lookup"><span data-stu-id="425fa-108">The **PackageManagement** module should be at least version 1.1.7.0 for the following property information to be correct.</span></span>

## <a name="syntax"></a><span data-ttu-id="425fa-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="425fa-109">Syntax</span></span>

```Syntax
PackageManagementSource [String] #ResourceName
{
    Name = [string]
    ProviderName = [string]
    SourceLocation = [string]
    [ InstallationPolicy = [string]{ Trusted | Untrusted } ]
    [ SourceCredential = [PSCredential] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string]{ Absent | Present } ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="425fa-110">Свойства</span><span class="sxs-lookup"><span data-stu-id="425fa-110">Properties</span></span>

|<span data-ttu-id="425fa-111">Свойство</span><span class="sxs-lookup"><span data-stu-id="425fa-111">Property</span></span> |<span data-ttu-id="425fa-112">Описание</span><span class="sxs-lookup"><span data-stu-id="425fa-112">Description</span></span> |
|---|---|
|<span data-ttu-id="425fa-113">Имя</span><span class="sxs-lookup"><span data-stu-id="425fa-113">Name</span></span> |<span data-ttu-id="425fa-114">Указывает имя источника пакета, который будет зарегистрирован в системе или регистрация которого будет отменена.</span><span class="sxs-lookup"><span data-stu-id="425fa-114">Specifies the name of the package source to be registered or unregistered on your system.</span></span> |
|<span data-ttu-id="425fa-115">ProviderName</span><span class="sxs-lookup"><span data-stu-id="425fa-115">ProviderName</span></span> |<span data-ttu-id="425fa-116">Указывает имя поставщика OneGet, с помощью которого вы можете взаимодействовать с источником пакета.</span><span class="sxs-lookup"><span data-stu-id="425fa-116">Specifies the name of the OneGet provider through which you can interop with the package source.</span></span> |
|<span data-ttu-id="425fa-117">SourceLocation</span><span class="sxs-lookup"><span data-stu-id="425fa-117">SourceLocation</span></span> |<span data-ttu-id="425fa-118">Указывает URI источника пакета.</span><span class="sxs-lookup"><span data-stu-id="425fa-118">Specifies the URI of the package source.</span></span> |
|<span data-ttu-id="425fa-119">InstallationPolicy</span><span class="sxs-lookup"><span data-stu-id="425fa-119">InstallationPolicy</span></span> |<span data-ttu-id="425fa-120">Используется поставщиками, такими как встроенный поставщик NuGet.</span><span class="sxs-lookup"><span data-stu-id="425fa-120">Used by providers such as the built-in Nuget Provider.</span></span> <span data-ttu-id="425fa-121">Определяет, доверяете ли вы источнику пакета.</span><span class="sxs-lookup"><span data-stu-id="425fa-121">Determines whether you trust the package's source.</span></span> <span data-ttu-id="425fa-122">Одно из двух значений: **Untrusted** или **Trusted**.</span><span class="sxs-lookup"><span data-stu-id="425fa-122">One of: **Untrusted** or **Trusted**.</span></span> |
|<span data-ttu-id="425fa-123">SourceCredential</span><span class="sxs-lookup"><span data-stu-id="425fa-123">SourceCredential</span></span> |<span data-ttu-id="425fa-124">Предоставляет доступ к пакету в удаленном источнике.</span><span class="sxs-lookup"><span data-stu-id="425fa-124">Provides access to the package on a remote source.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="425fa-125">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="425fa-125">Common properties</span></span>

|<span data-ttu-id="425fa-126">Свойство</span><span class="sxs-lookup"><span data-stu-id="425fa-126">Property</span></span> |<span data-ttu-id="425fa-127">Описание</span><span class="sxs-lookup"><span data-stu-id="425fa-127">Description</span></span> |
|---|---|
|<span data-ttu-id="425fa-128">DependsOn</span><span class="sxs-lookup"><span data-stu-id="425fa-128">DependsOn</span></span> |<span data-ttu-id="425fa-129">Указывает, что перед настройкой этого ресурса необходимо запустить настройку другого ресурса.</span><span class="sxs-lookup"><span data-stu-id="425fa-129">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="425fa-130">Например, если идентификатор первого запускаемого блока сценария для конфигурации ресурса — ResourceName, а его тип — ResourceType, то синтаксис использования этого свойства таков: `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="425fa-130">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="425fa-131">Ensure</span><span class="sxs-lookup"><span data-stu-id="425fa-131">Ensure</span></span> |<span data-ttu-id="425fa-132">Определяет, будет ли зарегистрирован источник пакета или его регистрация будет отменена.</span><span class="sxs-lookup"><span data-stu-id="425fa-132">Determines whether the package source is to be registered or unregistered.</span></span> <span data-ttu-id="425fa-133">Значение по умолчанию — **Present**.</span><span class="sxs-lookup"><span data-stu-id="425fa-133">The default value is **Present**.</span></span> |
|<span data-ttu-id="425fa-134">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="425fa-134">PsDscRunAsCredential</span></span> |<span data-ttu-id="425fa-135">Задает учетные данные для выполнения всего ресурса от другого имени.</span><span class="sxs-lookup"><span data-stu-id="425fa-135">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="425fa-136">В WMF 5.0 было добавлено общее свойство **PsDscRunAsCredential**, разрешающее запуск любого ресурса DSC в контексте других учетных данных.</span><span class="sxs-lookup"><span data-stu-id="425fa-136">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="425fa-137">Дополнительные сведения см. в разделе [Использование учетных данных с ресурсами DSC](../../../configurations/runasuser.md).</span><span class="sxs-lookup"><span data-stu-id="425fa-137">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="425fa-138">Пример</span><span class="sxs-lookup"><span data-stu-id="425fa-138">Example</span></span>

<span data-ttu-id="425fa-139">В этом примере регистрируется источник пакета `https://nuget.org` с помощью ресурса DSC **PackageManagementSource**.</span><span class="sxs-lookup"><span data-stu-id="425fa-139">This example registers the `https://nuget.org` package source using the **PackageManagementSource** DSC resource.</span></span>

```powershell
Configuration PackageManagementSourceTest
{
    PackageManagementSource SourceRepository
    {
        Ensure      = "Present"
        Name        = "MyNuget"
        ProviderName= "Nuget"
        SourceLocation   = "https://api.nuget.org/api/v3/"
        InstallationPolicy ="Trusted"
    }
}
```