---
ms.date: 06/20/2018
keywords: dsc,powershell,конфигурация,установка
title: Ресурс PackageManagementSource DSC
ms.openlocfilehash: 5d049b05c387cafe27edb202d569852b10852dce
ms.sourcegitcommit: 01d6985ed190a222e9da1da41596f524f607a5bc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "34753776"
---
# <a name="dsc-packagemanagementsource-resource"></a><span data-ttu-id="9a81f-103">Ресурс PackageManagementSource DSC</span><span class="sxs-lookup"><span data-stu-id="9a81f-103">DSC PackageManagementSource Resource</span></span>

> <span data-ttu-id="9a81f-104">Область применения: Windows PowerShell 4.0, Windows PowerShell 5.0, Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="9a81f-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0, Windows PowerShell 5.1</span></span>

<span data-ttu-id="9a81f-105">Ресурс **PackageManagementSource** в службе настройки требуемого состояния Windows PowerShell (DSC) предоставляет механизм регистрации или ее отмены для источников управления пакетами на целевом узле.</span><span class="sxs-lookup"><span data-stu-id="9a81f-105">The **PackageManagementSource** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to register or unregister Package Management sources on a target node.</span></span> <span data-ttu-id="9a81f-106">**Источники управления пакетами, зарегистрированные этим способом, регистрируются в контексте системы, доступной для учетной записи системы или подсистемы DSC.**</span><span class="sxs-lookup"><span data-stu-id="9a81f-106">**Package Management sources registered in this way are registered under the System context, usable by the System account or by the DSC engine.**</span></span> <span data-ttu-id="9a81f-107">Для этого ресурса требуется модуль **PackageManagement**, доступный из http://PowerShellGallery.com.</span><span class="sxs-lookup"><span data-stu-id="9a81f-107">This resource requires the **PackageManagement** module, available from http://PowerShellGallery.com.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9a81f-108">Указанные ниже сведения о свойствах относятся к модулю **PackageManagement** версии 1.1.7.0 и новее.</span><span class="sxs-lookup"><span data-stu-id="9a81f-108">The **PackageManagement** module should be at least version 1.1.7.0 for the following property information to be correct.</span></span>

## <a name="syntax"></a><span data-ttu-id="9a81f-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9a81f-109">Syntax</span></span>

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

## <a name="properties"></a><span data-ttu-id="9a81f-110">Свойства</span><span class="sxs-lookup"><span data-stu-id="9a81f-110">Properties</span></span>

|  <span data-ttu-id="9a81f-111">Свойство</span><span class="sxs-lookup"><span data-stu-id="9a81f-111">Property</span></span>  |  <span data-ttu-id="9a81f-112">Описание</span><span class="sxs-lookup"><span data-stu-id="9a81f-112">Description</span></span>   |
|---|---|
| <span data-ttu-id="9a81f-113">Name</span><span class="sxs-lookup"><span data-stu-id="9a81f-113">Name</span></span>| <span data-ttu-id="9a81f-114">Указывает имя источника пакета, который будет зарегистрирован в системе или регистрация которого будет отменена.</span><span class="sxs-lookup"><span data-stu-id="9a81f-114">Specifies the name of the package source to be registered or unregistered on your system.</span></span>|
| <span data-ttu-id="9a81f-115">ProviderName</span><span class="sxs-lookup"><span data-stu-id="9a81f-115">ProviderName</span></span>| <span data-ttu-id="9a81f-116">Указывает имя поставщика OneGet, с помощью которого вы можете взаимодействовать с источником пакета.</span><span class="sxs-lookup"><span data-stu-id="9a81f-116">Specifies the name of the OneGet provider through which you can interop with the package source.</span></span>|
| <span data-ttu-id="9a81f-117">SourceLocation</span><span class="sxs-lookup"><span data-stu-id="9a81f-117">SourceLocation</span></span>| <span data-ttu-id="9a81f-118">Указывает URI источника пакета.</span><span class="sxs-lookup"><span data-stu-id="9a81f-118">Specifies the URI of the package source.</span></span>|
| <span data-ttu-id="9a81f-119">Ensure</span><span class="sxs-lookup"><span data-stu-id="9a81f-119">Ensure</span></span>| <span data-ttu-id="9a81f-120">Определяет, будет ли зарегистрирован источник пакета или его регистрация будет отменена.</span><span class="sxs-lookup"><span data-stu-id="9a81f-120">Determines whether the package source is to be registered or unregistered.</span></span>|
| <span data-ttu-id="9a81f-121">InstallationPolicy</span><span class="sxs-lookup"><span data-stu-id="9a81f-121">InstallationPolicy</span></span>| <span data-ttu-id="9a81f-122">Используется поставщиками, такими как встроенный поставщик NuGet.</span><span class="sxs-lookup"><span data-stu-id="9a81f-122">Used by providers such as the built-in Nuget Provider.</span></span> <span data-ttu-id="9a81f-123">Определяет, доверяете ли вы источнику пакета.</span><span class="sxs-lookup"><span data-stu-id="9a81f-123">Determines whether you trust the package's source.</span></span> <span data-ttu-id="9a81f-124">Одно из двух значений: "Untrusted", "Trusted".</span><span class="sxs-lookup"><span data-stu-id="9a81f-124">One of: "Untrusted", "Trusted".</span></span>|
| <span data-ttu-id="9a81f-125">SourceCredential</span><span class="sxs-lookup"><span data-stu-id="9a81f-125">SourceCredential</span></span>| <span data-ttu-id="9a81f-126">Предоставляет доступ к пакету в удаленном источнике.</span><span class="sxs-lookup"><span data-stu-id="9a81f-126">Provides access to the package on a remote source.</span></span>|

## <a name="example"></a><span data-ttu-id="9a81f-127">Пример</span><span class="sxs-lookup"><span data-stu-id="9a81f-127">Example</span></span>

<span data-ttu-id="9a81f-128">В этом примере регистрируется источник пакета http://nuget.org с помощью ресурса DSC **PackageManagementSource**.</span><span class="sxs-lookup"><span data-stu-id="9a81f-128">This example registers the http://nuget.org package source using the **PackageManagementSource** DSC resource.</span></span>

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