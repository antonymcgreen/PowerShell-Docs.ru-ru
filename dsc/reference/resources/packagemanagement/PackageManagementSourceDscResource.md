---
ms.date: 06/20/2018
keywords: dsc,powershell,конфигурация,установка
title: Ресурс PackageManagementSource DSC
ms.openlocfilehash: e51b5318288bef458567dd4b58d17caaea3ed69b
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62077591"
---
# <a name="dsc-packagemanagementsource-resource"></a><span data-ttu-id="cf44d-103">Ресурс PackageManagementSource DSC</span><span class="sxs-lookup"><span data-stu-id="cf44d-103">DSC PackageManagementSource Resource</span></span>

> <span data-ttu-id="cf44d-104">Область применения. Windows PowerShell 4.0, Windows PowerShell 5.0, Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="cf44d-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0, Windows PowerShell 5.1</span></span>

<span data-ttu-id="cf44d-105">Ресурс **PackageManagementSource** в службе настройки требуемого состояния Windows PowerShell (DSC) предоставляет механизм регистрации или ее отмены для источников управления пакетами на целевом узле.</span><span class="sxs-lookup"><span data-stu-id="cf44d-105">The **PackageManagementSource** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to register or unregister Package Management sources on a target node.</span></span> <span data-ttu-id="cf44d-106">**Источники управления пакетами, зарегистрированные этим способом, регистрируются в контексте системы, доступной для учетной записи системы или подсистемы DSC.**</span><span class="sxs-lookup"><span data-stu-id="cf44d-106">**Package Management sources registered in this way are registered under the System context, usable by the System account or by the DSC engine.**</span></span> <span data-ttu-id="cf44d-107">Для этого ресурса требуется модуль **PackageManagement**, доступный из http://PowerShellGallery.com.</span><span class="sxs-lookup"><span data-stu-id="cf44d-107">This resource requires the **PackageManagement** module, available from http://PowerShellGallery.com.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cf44d-108">Указанные ниже сведения о свойствах относятся к модулю **PackageManagement** версии 1.1.7.0 и новее.</span><span class="sxs-lookup"><span data-stu-id="cf44d-108">The **PackageManagement** module should be at least version 1.1.7.0 for the following property information to be correct.</span></span>

## <a name="syntax"></a><span data-ttu-id="cf44d-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cf44d-109">Syntax</span></span>

```
PackageManagementSource [String] #ResourceName
{
    Name = [string]
    ProviderName = [string]
    SourceLocation = [string]
    [DependsOn = [string[]]]
    [Ensure = [string]{ Absent | Present }]
    [InstallationPolicy = [string]{ Trusted | Untrusted }]
    [PsDscRunAsCredential = [PSCredential]]
    [SourceCredential = [PSCredential]]
}
```

## <a name="properties"></a><span data-ttu-id="cf44d-110">Свойства</span><span class="sxs-lookup"><span data-stu-id="cf44d-110">Properties</span></span>

|  <span data-ttu-id="cf44d-111">Свойство</span><span class="sxs-lookup"><span data-stu-id="cf44d-111">Property</span></span>  |  <span data-ttu-id="cf44d-112">Описание</span><span class="sxs-lookup"><span data-stu-id="cf44d-112">Description</span></span>   |
|---|---|
| <span data-ttu-id="cf44d-113">Name</span><span class="sxs-lookup"><span data-stu-id="cf44d-113">Name</span></span>| <span data-ttu-id="cf44d-114">Указывает имя источника пакета, который будет зарегистрирован в системе или регистрация которого будет отменена.</span><span class="sxs-lookup"><span data-stu-id="cf44d-114">Specifies the name of the package source to be registered or unregistered on your system.</span></span>|
| <span data-ttu-id="cf44d-115">ProviderName</span><span class="sxs-lookup"><span data-stu-id="cf44d-115">ProviderName</span></span>| <span data-ttu-id="cf44d-116">Указывает имя поставщика OneGet, с помощью которого вы можете взаимодействовать с источником пакета.</span><span class="sxs-lookup"><span data-stu-id="cf44d-116">Specifies the name of the OneGet provider through which you can interop with the package source.</span></span>|
| <span data-ttu-id="cf44d-117">SourceLocation</span><span class="sxs-lookup"><span data-stu-id="cf44d-117">SourceLocation</span></span>| <span data-ttu-id="cf44d-118">Указывает URI источника пакета.</span><span class="sxs-lookup"><span data-stu-id="cf44d-118">Specifies the URI of the package source.</span></span>|
| <span data-ttu-id="cf44d-119">Ensure</span><span class="sxs-lookup"><span data-stu-id="cf44d-119">Ensure</span></span>| <span data-ttu-id="cf44d-120">Определяет, будет ли зарегистрирован источник пакета или его регистрация будет отменена.</span><span class="sxs-lookup"><span data-stu-id="cf44d-120">Determines whether the package source is to be registered or unregistered.</span></span>|
| <span data-ttu-id="cf44d-121">InstallationPolicy</span><span class="sxs-lookup"><span data-stu-id="cf44d-121">InstallationPolicy</span></span>| <span data-ttu-id="cf44d-122">Используется поставщиками, такими как встроенный поставщик NuGet.</span><span class="sxs-lookup"><span data-stu-id="cf44d-122">Used by providers such as the built-in Nuget Provider.</span></span> <span data-ttu-id="cf44d-123">Определяет, доверяете ли вы источнику пакета.</span><span class="sxs-lookup"><span data-stu-id="cf44d-123">Determines whether you trust the package's source.</span></span> <span data-ttu-id="cf44d-124">Одно из двух значений: "Untrusted", "Trusted".</span><span class="sxs-lookup"><span data-stu-id="cf44d-124">One of: "Untrusted", "Trusted".</span></span>|
| <span data-ttu-id="cf44d-125">SourceCredential</span><span class="sxs-lookup"><span data-stu-id="cf44d-125">SourceCredential</span></span>| <span data-ttu-id="cf44d-126">Предоставляет доступ к пакету в удаленном источнике.</span><span class="sxs-lookup"><span data-stu-id="cf44d-126">Provides access to the package on a remote source.</span></span>|

## <a name="example"></a><span data-ttu-id="cf44d-127">Пример</span><span class="sxs-lookup"><span data-stu-id="cf44d-127">Example</span></span>

<span data-ttu-id="cf44d-128">В этом примере регистрируется источник пакета http://nuget.org с помощью ресурса DSC **PackageManagementSource**.</span><span class="sxs-lookup"><span data-stu-id="cf44d-128">This example registers the http://nuget.org package source using the **PackageManagementSource** DSC resource.</span></span>

```powershell
Configuration PackageManagementSourceTest
{
    PackageManagementSource SourceRepository
    {
        Ensure      = "Present"
        Name        = "MyNuget"
        ProviderName= "Nuget"
        SourceLocation   = "http://nuget.org/api/v2/"
        InstallationPolicy ="Trusted"
    }
}
```