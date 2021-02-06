---
Download Help Link: https://aka.ms/powershell72-help
Help Version: 7.2.0.0
Locale: en-US
Module Guid: 4ae9fd46-338a-459c-8186-07f910774cb8
Module Name: PackageManagement
ms.date: 06/09/2017
schema: 2.0.0
title: PackageManagement
ms.openlocfilehash: 86e6f37f6f7f0527c5dcca309cf581cb6f1b4de5
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "99599994"
---
# <span data-ttu-id="b50e9-102">Модуль PackageManagement</span><span class="sxs-lookup"><span data-stu-id="b50e9-102">PackageManagement Module</span></span>

## <span data-ttu-id="b50e9-103">Описание</span><span class="sxs-lookup"><span data-stu-id="b50e9-103">Description</span></span>

<span data-ttu-id="b50e9-104">В этом разделе отображаются разделы справки по командлетам Управление пакетами.</span><span class="sxs-lookup"><span data-stu-id="b50e9-104">This topic displays help topics for the Package Management Cmdlets.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b50e9-105">Начиная с апреля 2020 года коллекция PowerShell не поддерживает протокол TLS (Transport Layer Security) версий 1.0 и 1.1.</span><span class="sxs-lookup"><span data-stu-id="b50e9-105">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="b50e9-106">Если вы не используете TLS 1.2 или более поздней версии, при попытке доступа к коллекции PowerShell возникнет ошибка.</span><span class="sxs-lookup"><span data-stu-id="b50e9-106">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="b50e9-107">Чтобы проверить, используется ли TLS 1.2, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b50e9-107">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="b50e9-108">Дополнительные сведения см. в [объявлении](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) в блоге, посвященном PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b50e9-108">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="b50e9-109">Командлеты PackageManagement</span><span class="sxs-lookup"><span data-stu-id="b50e9-109">PackageManagement Cmdlets</span></span>

### [<span data-ttu-id="b50e9-110">Find-Package</span><span class="sxs-lookup"><span data-stu-id="b50e9-110">Find-Package</span></span>](Find-Package.md)
<span data-ttu-id="b50e9-111">Находит пакеты программного обеспечения в доступных источниках пакетов.</span><span class="sxs-lookup"><span data-stu-id="b50e9-111">Finds software packages in available package sources.</span></span>

### [<span data-ttu-id="b50e9-112">Find-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="b50e9-112">Find-PackageProvider</span></span>](Find-PackageProvider.md)
<span data-ttu-id="b50e9-113">Возвращает список поставщиков пакетов Управление пакетами, доступных для установки.</span><span class="sxs-lookup"><span data-stu-id="b50e9-113">Returns a list of Package Management package providers available for installation.</span></span>

### [<span data-ttu-id="b50e9-114">Get-Package</span><span class="sxs-lookup"><span data-stu-id="b50e9-114">Get-Package</span></span>](Get-Package.md)
<span data-ttu-id="b50e9-115">Возвращает список всех пакетов программного обеспечения, установленных с помощью **PackageManagement**.</span><span class="sxs-lookup"><span data-stu-id="b50e9-115">Returns a list of all software packages that were installed with **PackageManagement**.</span></span>

### [<span data-ttu-id="b50e9-116">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="b50e9-116">Get-PackageProvider</span></span>](Get-PackageProvider.md)
<span data-ttu-id="b50e9-117">Возвращает список поставщиков пакетов, подключенных к системе управления пакетами.</span><span class="sxs-lookup"><span data-stu-id="b50e9-117">Returns a list of package providers that are connected to Package Management.</span></span>

### [<span data-ttu-id="b50e9-118">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="b50e9-118">Get-PackageSource</span></span>](Get-PackageSource.md)
<span data-ttu-id="b50e9-119">Возвращает список источников пакетов, зарегистрированных для поставщика пакетов.</span><span class="sxs-lookup"><span data-stu-id="b50e9-119">Gets a list of package sources that are registered for a package provider.</span></span>

### [<span data-ttu-id="b50e9-120">Import-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="b50e9-120">Import-PackageProvider</span></span>](Import-PackageProvider.md)
<span data-ttu-id="b50e9-121">Добавляет поставщики пакетов Управление пакетами в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="b50e9-121">Adds Package Management package providers to the current session.</span></span>

### [<span data-ttu-id="b50e9-122">Install-Package</span><span class="sxs-lookup"><span data-stu-id="b50e9-122">Install-Package</span></span>](Install-Package.md)
<span data-ttu-id="b50e9-123">Устанавливает один или несколько пакетов программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="b50e9-123">Installs one or more software packages.</span></span>

### [<span data-ttu-id="b50e9-124">Install-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="b50e9-124">Install-PackageProvider</span></span>](Install-PackageProvider.md)
<span data-ttu-id="b50e9-125">Устанавливает один или несколько поставщиков пакетов Управление пакетами.</span><span class="sxs-lookup"><span data-stu-id="b50e9-125">Installs one or more Package Management package providers.</span></span>

### [<span data-ttu-id="b50e9-126">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="b50e9-126">Register-PackageSource</span></span>](Register-PackageSource.md)
<span data-ttu-id="b50e9-127">Добавляет источник пакета для указанного поставщика пакетов.</span><span class="sxs-lookup"><span data-stu-id="b50e9-127">Adds a package source for a specified package provider.</span></span>

### [<span data-ttu-id="b50e9-128">Save-Package</span><span class="sxs-lookup"><span data-stu-id="b50e9-128">Save-Package</span></span>](Save-Package.md)
<span data-ttu-id="b50e9-129">Сохраняет пакеты на локальном компьютере, не устанавливая их.</span><span class="sxs-lookup"><span data-stu-id="b50e9-129">Saves packages to the local computer without installing them.</span></span>

### [<span data-ttu-id="b50e9-130">Set-PackageSource</span><span class="sxs-lookup"><span data-stu-id="b50e9-130">Set-PackageSource</span></span>](Set-PackageSource.md)
<span data-ttu-id="b50e9-131">Заменяет источник пакета для указанного поставщика пакетов.</span><span class="sxs-lookup"><span data-stu-id="b50e9-131">Replaces a package source for a specified package provider.</span></span>

### [<span data-ttu-id="b50e9-132">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="b50e9-132">Uninstall-Package</span></span>](Uninstall-Package.md)
<span data-ttu-id="b50e9-133">Удаляет один или несколько пакетов программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="b50e9-133">Uninstalls one or more software packages.</span></span>

### [<span data-ttu-id="b50e9-134">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="b50e9-134">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)
<span data-ttu-id="b50e9-135">Удаляет зарегистрированный источник пакета.</span><span class="sxs-lookup"><span data-stu-id="b50e9-135">Removes a registered package source.</span></span>
