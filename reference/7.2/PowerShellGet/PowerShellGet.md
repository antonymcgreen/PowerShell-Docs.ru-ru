---
Download Help Link: https://aka.ms/powershell72-help
Help Version: 7.2.0.0
Locale: en-US
Module Guid: 1d73a601-4a6c-43c5-ba3f-619b18bbb404
Module Name: PowerShellGet
ms.date: 06/09/2017
schema: 2.0.0
title: PowerShellGet
ms.openlocfilehash: 0d4e5e26184558055a17f99bd5321aaf3f3789f7
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "99604726"
---
# <span data-ttu-id="f6285-102">Модуль PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="f6285-102">PowerShellGet Module</span></span>

## <span data-ttu-id="f6285-103">Описание</span><span class="sxs-lookup"><span data-stu-id="f6285-103">Description</span></span>

<span data-ttu-id="f6285-104">PowerShellGet — это модуль с командами для обнаружения, установки, обновления и публикации артефактов PowerShell, таких как модули, ресурсы DSC, возможности ролей и сценарии.</span><span class="sxs-lookup"><span data-stu-id="f6285-104">PowerShellGet is a module with commands for discovering, installing, updating and publishing PowerShell artifacts like Modules, DSC Resources, Role Capabilities, and Scripts.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f6285-105">Начиная с апреля 2020 года коллекция PowerShell не поддерживает протокол TLS (Transport Layer Security) версий 1.0 и 1.1.</span><span class="sxs-lookup"><span data-stu-id="f6285-105">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="f6285-106">Если вы не используете TLS 1.2 или более поздней версии, при попытке доступа к коллекции PowerShell возникнет ошибка.</span><span class="sxs-lookup"><span data-stu-id="f6285-106">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="f6285-107">Чтобы проверить, используется ли TLS 1.2, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f6285-107">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="f6285-108">Дополнительные сведения см. в [объявлении](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) в блоге, посвященном PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f6285-108">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="f6285-109">Командлеты модуля PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="f6285-109">PowerShellGet Cmdlets</span></span>

### [<span data-ttu-id="f6285-110">Find-Command</span><span class="sxs-lookup"><span data-stu-id="f6285-110">Find-Command</span></span>](Find-Command.md)
<span data-ttu-id="f6285-111">Ищет команды PowerShell в модулях.</span><span class="sxs-lookup"><span data-stu-id="f6285-111">Finds PowerShell commands in modules.</span></span>

### [<span data-ttu-id="f6285-112">Find-DscResource</span><span class="sxs-lookup"><span data-stu-id="f6285-112">Find-DscResource</span></span>](Find-DscResource.md)
<span data-ttu-id="f6285-113">Находит ресурсы настройки требуемого состояния (DSC).</span><span class="sxs-lookup"><span data-stu-id="f6285-113">Finds Desired State Configuration (DSC) resources.</span></span>

### [<span data-ttu-id="f6285-114">Find-Module</span><span class="sxs-lookup"><span data-stu-id="f6285-114">Find-Module</span></span>](Find-Module.md)
<span data-ttu-id="f6285-115">Находит модули в репозитории, соответствующие указанным критериям.</span><span class="sxs-lookup"><span data-stu-id="f6285-115">Finds modules in a repository that match specified criteria.</span></span>

### [<span data-ttu-id="f6285-116">Find-RoleCapability</span><span class="sxs-lookup"><span data-stu-id="f6285-116">Find-RoleCapability</span></span>](Find-RoleCapability.md)
<span data-ttu-id="f6285-117">Находит возможности ролей в модулях.</span><span class="sxs-lookup"><span data-stu-id="f6285-117">Finds role capabilities in modules.</span></span>

### [<span data-ttu-id="f6285-118">Find-Script</span><span class="sxs-lookup"><span data-stu-id="f6285-118">Find-Script</span></span>](Find-Script.md)
<span data-ttu-id="f6285-119">Поиск скрипта.</span><span class="sxs-lookup"><span data-stu-id="f6285-119">Finds a script.</span></span>

### [<span data-ttu-id="f6285-120">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="f6285-120">Get-InstalledModule</span></span>](Get-InstalledModule.md)
<span data-ttu-id="f6285-121">Возвращает список модулей на компьютере, которые были установлены с помощью PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="f6285-121">Gets a list of modules on the computer that were installed by PowerShellGet.</span></span>

### [<span data-ttu-id="f6285-122">Get-InstalledScript</span><span class="sxs-lookup"><span data-stu-id="f6285-122">Get-InstalledScript</span></span>](Get-InstalledScript.md)
<span data-ttu-id="f6285-123">Возвращает установленный скрипт.</span><span class="sxs-lookup"><span data-stu-id="f6285-123">Gets an installed script.</span></span>

### [<span data-ttu-id="f6285-124">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="f6285-124">Get-PSRepository</span></span>](Get-PSRepository.md)
<span data-ttu-id="f6285-125">Возвращает репозитории PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f6285-125">Gets PowerShell repositories.</span></span>

### [<span data-ttu-id="f6285-126">Install-Module</span><span class="sxs-lookup"><span data-stu-id="f6285-126">Install-Module</span></span>](Install-Module.md)
<span data-ttu-id="f6285-127">Скачивает один или несколько модулей из репозитория и устанавливает их на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="f6285-127">Downloads one or more modules from a repository, and installs them on the local computer.</span></span>

### [<span data-ttu-id="f6285-128">Install-Script</span><span class="sxs-lookup"><span data-stu-id="f6285-128">Install-Script</span></span>](Install-Script.md)
<span data-ttu-id="f6285-129">Устанавливает скрипт.</span><span class="sxs-lookup"><span data-stu-id="f6285-129">Installs a script.</span></span>

### [<span data-ttu-id="f6285-130">New-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="f6285-130">New-ScriptFileInfo</span></span>](New-ScriptFileInfo.md)
<span data-ttu-id="f6285-131">Создание файла сценария с метаданными.</span><span class="sxs-lookup"><span data-stu-id="f6285-131">Creates a script file with metadata.</span></span>

### [<span data-ttu-id="f6285-132">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="f6285-132">Publish-Module</span></span>](Publish-Module.md)
<span data-ttu-id="f6285-133">Публикует указанный модуль с локального компьютера в коллекцию в Интернете.</span><span class="sxs-lookup"><span data-stu-id="f6285-133">Publishes a specified module from the local computer to an online gallery.</span></span>

### [<span data-ttu-id="f6285-134">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="f6285-134">Publish-Script</span></span>](Publish-Script.md)
<span data-ttu-id="f6285-135">Публикует скрипт.</span><span class="sxs-lookup"><span data-stu-id="f6285-135">Publishes a script.</span></span>

### [<span data-ttu-id="f6285-136">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="f6285-136">Register-PSRepository</span></span>](Register-PSRepository.md)
<span data-ttu-id="f6285-137">Регистрирует репозиторий PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f6285-137">Registers a PowerShell repository.</span></span>

### [<span data-ttu-id="f6285-138">Save-Module</span><span class="sxs-lookup"><span data-stu-id="f6285-138">Save-Module</span></span>](Save-Module.md)
<span data-ttu-id="f6285-139">Сохраняет модуль и его зависимости на локальном компьютере, но не устанавливает модуль.</span><span class="sxs-lookup"><span data-stu-id="f6285-139">Saves a module and its dependencies on the local computer but doesn't install the module.</span></span>

### [<span data-ttu-id="f6285-140">Save-Script</span><span class="sxs-lookup"><span data-stu-id="f6285-140">Save-Script</span></span>](Save-Script.md)
<span data-ttu-id="f6285-141">Сохраняет скрипт.</span><span class="sxs-lookup"><span data-stu-id="f6285-141">Saves a script.</span></span>

### [<span data-ttu-id="f6285-142">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="f6285-142">Set-PSRepository</span></span>](Set-PSRepository.md)
<span data-ttu-id="f6285-143">Задает значения для зарегистрированного репозитория.</span><span class="sxs-lookup"><span data-stu-id="f6285-143">Sets values for a registered repository.</span></span>

### [<span data-ttu-id="f6285-144">Test-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="f6285-144">Test-ScriptFileInfo</span></span>](Test-ScriptFileInfo.md)
<span data-ttu-id="f6285-145">Проверяет блок комментариев для скрипта.</span><span class="sxs-lookup"><span data-stu-id="f6285-145">Validates a comment block for a script.</span></span>

### [<span data-ttu-id="f6285-146">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="f6285-146">Uninstall-Module</span></span>](Uninstall-Module.md)
<span data-ttu-id="f6285-147">Удаляет модуль.</span><span class="sxs-lookup"><span data-stu-id="f6285-147">Uninstalls a module.</span></span>

### [<span data-ttu-id="f6285-148">Uninstall-Script</span><span class="sxs-lookup"><span data-stu-id="f6285-148">Uninstall-Script</span></span>](Uninstall-Script.md)
<span data-ttu-id="f6285-149">Удаляет скрипт.</span><span class="sxs-lookup"><span data-stu-id="f6285-149">Uninstalls a script.</span></span>

### [<span data-ttu-id="f6285-150">Unregister-PSRepository</span><span class="sxs-lookup"><span data-stu-id="f6285-150">Unregister-PSRepository</span></span>](Unregister-PSRepository.md)
<span data-ttu-id="f6285-151">Отмена регистрации репозитория.</span><span class="sxs-lookup"><span data-stu-id="f6285-151">Unregisters a repository.</span></span>

### [<span data-ttu-id="f6285-152">Update-Module</span><span class="sxs-lookup"><span data-stu-id="f6285-152">Update-Module</span></span>](Update-Module.md)
<span data-ttu-id="f6285-153">Скачивает последние версии указанных модулей из веб-коллекции и устанавливает их на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="f6285-153">Downloads and installs the newest version of specified modules from an online gallery to the local computer.</span></span>

### [<span data-ttu-id="f6285-154">Update-ModuleManifest</span><span class="sxs-lookup"><span data-stu-id="f6285-154">Update-ModuleManifest</span></span>](Update-ModuleManifest.md)
<span data-ttu-id="f6285-155">Обновляет файл манифеста модуля.</span><span class="sxs-lookup"><span data-stu-id="f6285-155">Updates a module manifest file.</span></span>

### [<span data-ttu-id="f6285-156">Update-Script</span><span class="sxs-lookup"><span data-stu-id="f6285-156">Update-Script</span></span>](Update-Script.md)
<span data-ttu-id="f6285-157">Обновляет скрипт.</span><span class="sxs-lookup"><span data-stu-id="f6285-157">Updates a script.</span></span>

### [<span data-ttu-id="f6285-158">Update-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="f6285-158">Update-ScriptFileInfo</span></span>](Update-ScriptFileInfo.md)
<span data-ttu-id="f6285-159">Обновляет сведения для скрипта.</span><span class="sxs-lookup"><span data-stu-id="f6285-159">Updates information for a script.</span></span>
