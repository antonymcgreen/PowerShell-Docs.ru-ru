---
Download Help Link: https://go.microsoft.com/fwlink/?linkid=2113634
Help Version: 7.0.1.0
keywords: powershell,командлет
Locale: en-US
Module Guid: 4ae9fd46-338a-459c-8186-07f910774cb8
Module Name: PackageManagement
ms.date: 06/09/2017
schema: 2.0.0
title: PackageManagement
ms.openlocfilehash: 01b1bce187cd0526e56abc812f91b44a2c022a29
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "94890861"
---
# <span data-ttu-id="01ab9-103">Модуль PackageManagement</span><span class="sxs-lookup"><span data-stu-id="01ab9-103">PackageManagement Module</span></span>

## <span data-ttu-id="01ab9-104">Описание</span><span class="sxs-lookup"><span data-stu-id="01ab9-104">Description</span></span>

<span data-ttu-id="01ab9-105">В этом разделе отображаются разделы справки по командлетам Управление пакетами.</span><span class="sxs-lookup"><span data-stu-id="01ab9-105">This topic displays help topics for the Package Management Cmdlets.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="01ab9-106">По состоянию на апрель 2020 коллекция PowerShell больше не поддерживает TLS-версии 1,0 и 1,1.</span><span class="sxs-lookup"><span data-stu-id="01ab9-106">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="01ab9-107">Если вы не используете TLS 1,2 или более поздней версии, при попытке доступа к коллекция PowerShell возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="01ab9-107">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="01ab9-108">Используйте следующую команду, чтобы убедиться, что используется TLS 1,2:</span><span class="sxs-lookup"><span data-stu-id="01ab9-108">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="01ab9-109">Дополнительные сведения см. в [объявлении](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) в блоге PowerShell.</span><span class="sxs-lookup"><span data-stu-id="01ab9-109">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="01ab9-110">Командлеты PackageManagement</span><span class="sxs-lookup"><span data-stu-id="01ab9-110">PackageManagement Cmdlets</span></span>

### [<span data-ttu-id="01ab9-111">Find-Package</span><span class="sxs-lookup"><span data-stu-id="01ab9-111">Find-Package</span></span>](Find-Package.md)
<span data-ttu-id="01ab9-112">Находит пакеты программного обеспечения в доступных источниках пакетов.</span><span class="sxs-lookup"><span data-stu-id="01ab9-112">Finds software packages in available package sources.</span></span>

### [<span data-ttu-id="01ab9-113">Find-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="01ab9-113">Find-PackageProvider</span></span>](Find-PackageProvider.md)
<span data-ttu-id="01ab9-114">Возвращает список поставщиков пакетов Управление пакетами, доступных для установки.</span><span class="sxs-lookup"><span data-stu-id="01ab9-114">Returns a list of Package Management package providers available for installation.</span></span>

### [<span data-ttu-id="01ab9-115">Get-Package</span><span class="sxs-lookup"><span data-stu-id="01ab9-115">Get-Package</span></span>](Get-Package.md)
<span data-ttu-id="01ab9-116">Возвращает список всех пакетов программного обеспечения, установленных с помощью **PackageManagement**.</span><span class="sxs-lookup"><span data-stu-id="01ab9-116">Returns a list of all software packages that were installed with **PackageManagement**.</span></span>

### [<span data-ttu-id="01ab9-117">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="01ab9-117">Get-PackageProvider</span></span>](Get-PackageProvider.md)
<span data-ttu-id="01ab9-118">Возвращает список поставщиков пакетов, подключенных к системе управления пакетами.</span><span class="sxs-lookup"><span data-stu-id="01ab9-118">Returns a list of package providers that are connected to Package Management.</span></span>

### [<span data-ttu-id="01ab9-119">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="01ab9-119">Get-PackageSource</span></span>](Get-PackageSource.md)
<span data-ttu-id="01ab9-120">Возвращает список источников пакетов, зарегистрированных для поставщика пакетов.</span><span class="sxs-lookup"><span data-stu-id="01ab9-120">Gets a list of package sources that are registered for a package provider.</span></span>

### [<span data-ttu-id="01ab9-121">Import-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="01ab9-121">Import-PackageProvider</span></span>](Import-PackageProvider.md)
<span data-ttu-id="01ab9-122">Добавляет поставщики пакетов Управление пакетами в текущий сеанс.</span><span class="sxs-lookup"><span data-stu-id="01ab9-122">Adds Package Management package providers to the current session.</span></span>

### [<span data-ttu-id="01ab9-123">Install-Package</span><span class="sxs-lookup"><span data-stu-id="01ab9-123">Install-Package</span></span>](Install-Package.md)
<span data-ttu-id="01ab9-124">Устанавливает один или несколько пакетов программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="01ab9-124">Installs one or more software packages.</span></span>

### [<span data-ttu-id="01ab9-125">Install-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="01ab9-125">Install-PackageProvider</span></span>](Install-PackageProvider.md)
<span data-ttu-id="01ab9-126">Устанавливает один или несколько поставщиков пакетов Управление пакетами.</span><span class="sxs-lookup"><span data-stu-id="01ab9-126">Installs one or more Package Management package providers.</span></span>

### [<span data-ttu-id="01ab9-127">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="01ab9-127">Register-PackageSource</span></span>](Register-PackageSource.md)
<span data-ttu-id="01ab9-128">Добавляет источник пакета для указанного поставщика пакетов.</span><span class="sxs-lookup"><span data-stu-id="01ab9-128">Adds a package source for a specified package provider.</span></span>

### [<span data-ttu-id="01ab9-129">Save-Package</span><span class="sxs-lookup"><span data-stu-id="01ab9-129">Save-Package</span></span>](Save-Package.md)
<span data-ttu-id="01ab9-130">Сохраняет пакеты на локальном компьютере, не устанавливая их.</span><span class="sxs-lookup"><span data-stu-id="01ab9-130">Saves packages to the local computer without installing them.</span></span>

### [<span data-ttu-id="01ab9-131">Set-PackageSource</span><span class="sxs-lookup"><span data-stu-id="01ab9-131">Set-PackageSource</span></span>](Set-PackageSource.md)
<span data-ttu-id="01ab9-132">Заменяет источник пакета для указанного поставщика пакетов.</span><span class="sxs-lookup"><span data-stu-id="01ab9-132">Replaces a package source for a specified package provider.</span></span>

### [<span data-ttu-id="01ab9-133">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="01ab9-133">Uninstall-Package</span></span>](Uninstall-Package.md)
<span data-ttu-id="01ab9-134">Удаляет один или несколько пакетов программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="01ab9-134">Uninstalls one or more software packages.</span></span>

### [<span data-ttu-id="01ab9-135">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="01ab9-135">Unregister-PackageSource</span></span>](Unregister-PackageSource.md)
<span data-ttu-id="01ab9-136">Удаляет зарегистрированный источник пакета.</span><span class="sxs-lookup"><span data-stu-id="01ab9-136">Removes a registered package source.</span></span>
