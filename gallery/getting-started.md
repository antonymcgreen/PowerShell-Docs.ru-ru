---
ms.date: 06/12/2017
contributor: JKeithB
ms.topic: conceptual
keywords: коллекции,powershell,командлет,psgallery
title: psgallery_начало_работы
ms.openlocfilehash: c3aafe9e76eda9acdd4787f63dc0f8c71a20d02a
ms.sourcegitcommit: e9ad4d85fd7eb72fb5bc37f6ca3ae1282ae3c6d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2018
---
# <a name="get-started-with-the-powershell-gallery"></a><span data-ttu-id="61ab5-103">Приступая к работе с коллекцией PowerShell</span><span class="sxs-lookup"><span data-stu-id="61ab5-103">Get Started with the PowerShell Gallery</span></span>

<span data-ttu-id="61ab5-104">Для скачивания элементов из коллекции PowerShell требуется модуль [PowerShellGet](/powershell/module/powershellget).</span><span class="sxs-lookup"><span data-stu-id="61ab5-104">Downloading items from the PowerShell Gallery to your system requires the [PowerShellGet](/powershell/module/powershellget) module.</span></span> <span data-ttu-id="61ab5-105">Модуль PowerShellGet можно найти в перечисленных ниже источниках.</span><span class="sxs-lookup"><span data-stu-id="61ab5-105">You can find the PowerShellGet module in any of the following.</span></span> <span data-ttu-id="61ab5-106">Входить в систему для скачивания элементов из коллекции PowerShell необязательно.</span><span class="sxs-lookup"><span data-stu-id="61ab5-106">You do not need to sign in to download items from the PowerShell Gallery.</span></span>

## <a name="discovering-items-from-the-powershell-gallery"></a><span data-ttu-id="61ab5-107">Обнаружение элементов в коллекции PowerShell</span><span class="sxs-lookup"><span data-stu-id="61ab5-107">Discovering items from the PowerShell Gallery</span></span>

<span data-ttu-id="61ab5-108">Найти элементы в коллекции PowerShell можно при помощи элемента управления **Поиск** на сайте или просмотрев страницы "Модули" и "Скрипты".</span><span class="sxs-lookup"><span data-stu-id="61ab5-108">You can find items in the PowerShell Gallery by using the **Search** control on this website, or by browsing through the Modules and Scripts pages.</span></span> <span data-ttu-id="61ab5-109">Найти элементы в коллекции PowerShell можно также при помощи командлетов [Find-Module][] и [Find-Script][] (в зависимости от типа элемента) с параметром `-Repository PSGallery`.</span><span class="sxs-lookup"><span data-stu-id="61ab5-109">You can also find items from the PowerShell Gallery by running the [Find-Module][] and [Find-Script][] cmdlets, depending on the item type, with `-Repository PSGallery`.</span></span>

<span data-ttu-id="61ab5-110">Для фильтрации результатов поиска в коллекции используются следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="61ab5-110">Filtering results from the Gallery can be done by using the following parameters:</span></span>

- <span data-ttu-id="61ab5-111">Name</span><span class="sxs-lookup"><span data-stu-id="61ab5-111">Name</span></span>
- <span data-ttu-id="61ab5-112">AllVersions</span><span class="sxs-lookup"><span data-stu-id="61ab5-112">AllVersions</span></span>
- <span data-ttu-id="61ab5-113">MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="61ab5-113">MinimumVersion</span></span>
- <span data-ttu-id="61ab5-114">RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="61ab5-114">RequiredVersion</span></span>
- <span data-ttu-id="61ab5-115">Tag</span><span class="sxs-lookup"><span data-stu-id="61ab5-115">Tag</span></span>
- <span data-ttu-id="61ab5-116">Includes</span><span class="sxs-lookup"><span data-stu-id="61ab5-116">Includes</span></span>
- <span data-ttu-id="61ab5-117">DscResource</span><span class="sxs-lookup"><span data-stu-id="61ab5-117">DscResource</span></span>
- <span data-ttu-id="61ab5-118">RoleCapability</span><span class="sxs-lookup"><span data-stu-id="61ab5-118">RoleCapability</span></span>
- <span data-ttu-id="61ab5-119">Команда</span><span class="sxs-lookup"><span data-stu-id="61ab5-119">Command</span></span>
- <span data-ttu-id="61ab5-120">Фильтр</span><span class="sxs-lookup"><span data-stu-id="61ab5-120">Filter</span></span>

<span data-ttu-id="61ab5-121">Если вас интересуют только определенные ресурсы DSC в коллекции, выполните командлет [Find-DscResource].</span><span class="sxs-lookup"><span data-stu-id="61ab5-121">If you're only interested in discovering specific DSC resources in the Gallery, you can run the [Find-DscResource] cmdlet.</span></span> <span data-ttu-id="61ab5-122">Командлет Find-DscResource возвращает сведения о ресурсах DSC, содержащихся в коллекции.</span><span class="sxs-lookup"><span data-stu-id="61ab5-122">Find-DscResource returns data on DSC resources contained in the Gallery.</span></span>
<span data-ttu-id="61ab5-123">Поскольку ресурсы DSC всегда являются частью модуля, вам по-прежнему потребуется выполнить командлет [Install-Module][], чтобы установить их.</span><span class="sxs-lookup"><span data-stu-id="61ab5-123">Because DSC resources are always delivered as part of a module, you still need to run [Install-Module][] to install those DSC resources.</span></span>

## <a name="learning-about-items-in-the-powershell-gallery"></a><span data-ttu-id="61ab5-124">Изучение элементов в коллекции PowerShell</span><span class="sxs-lookup"><span data-stu-id="61ab5-124">Learning about items in the PowerShell Gallery</span></span>

<span data-ttu-id="61ab5-125">Когда вы нашли элемент, который вас интересует, о нем можно узнать больше.</span><span class="sxs-lookup"><span data-stu-id="61ab5-125">Once you've identified an item you're interested in, you may want to learn more about it.</span></span> <span data-ttu-id="61ab5-126">Для этого можно изучить страницу конкретного элемента в коллекции.</span><span class="sxs-lookup"><span data-stu-id="61ab5-126">You can do this by examining that item's specific page on the Gallery.</span></span> <span data-ttu-id="61ab5-127">На ней представлены все метаданные, переданные вместе с элементом.</span><span class="sxs-lookup"><span data-stu-id="61ab5-127">On that page, you'll be able to see all of the metadata uploaded with the item.</span></span> <span data-ttu-id="61ab5-128">Эти метаданные предоставляются автором элемента и не проверяются корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="61ab5-128">This metadata for an item is provided by the item's author, and is not verified by Microsoft.</span></span> <span data-ttu-id="61ab5-129">Владелец элемента тесно связан с учетной записью в коллекции, используемой для публикации элемента, поэтому ориентироваться на нее — более надежно, чем на информацию в поле "Автор".</span><span class="sxs-lookup"><span data-stu-id="61ab5-129">The Owner of the item is strongly tied to the Gallery account used to publish the item, and is more trustworthy than the Author field.</span></span>

<span data-ttu-id="61ab5-130">Если вы нашли элемент, который по вашему мнению опубликован с нарушениями, щелкните **Сообщить о нарушении** на странице этого элемента.</span><span class="sxs-lookup"><span data-stu-id="61ab5-130">If you discover an item that you feel is not published in good faith, click **Report Abuse** on that item's page.</span></span>

<span data-ttu-id="61ab5-131">При использовании командлетов [Find-Module][] или [Find-Script][] эти данные можно доступны в возвращенном объекте PSGetModuleInfo.</span><span class="sxs-lookup"><span data-stu-id="61ab5-131">If you're running [Find-Module][] or [Find-Script][], you can view this data in the returned PSGetModuleInfo object.</span></span> <span data-ttu-id="61ab5-132">Например, при выполнении `Find-Module -Name PSReadLine -Repository PSGallery |Get-Member` возвращаются сведения о модуле PSReadLine, содержащемся в коллекции.</span><span class="sxs-lookup"><span data-stu-id="61ab5-132">For example, running `Find-Module -Name PSReadLine -Repository PSGallery |Get-Member` returns data on the PSReadLine module in the Gallery.</span></span>

## <a name="downloading-items-from-the-powershell-gallery"></a><span data-ttu-id="61ab5-133">Скачивание элементов из коллекции PowerShell</span><span class="sxs-lookup"><span data-stu-id="61ab5-133">Downloading items from the PowerShell Gallery</span></span>

<span data-ttu-id="61ab5-134">При скачивании элементов из коллекции PowerShell рекомендуется использовать следующий процесс.</span><span class="sxs-lookup"><span data-stu-id="61ab5-134">We encourage the following process when downloading items from the PowerShell Gallery:</span></span>

### <a name="inspect"></a><span data-ttu-id="61ab5-135">Изучение</span><span class="sxs-lookup"><span data-stu-id="61ab5-135">Inspect</span></span>

<span data-ttu-id="61ab5-136">Чтобы скачать элемент из коллекции для изучения, выполните командлет [Save-Module][] или [Save-Script][] в зависимости от типа элемента.</span><span class="sxs-lookup"><span data-stu-id="61ab5-136">To download an item from the Gallery for inspection, run either the [Save-Module][] or [Save-Script][] cmdlet, depending on the item type.</span></span> <span data-ttu-id="61ab5-137">Так вы сможете сохранить элемент локально без установки и проверить его содержимое.</span><span class="sxs-lookup"><span data-stu-id="61ab5-137">This lets you save the item locally without installing it, and inspect the item contents.</span></span> <span data-ttu-id="61ab5-138">Не забудьте удалить элемент, сохраненный вручную.</span><span class="sxs-lookup"><span data-stu-id="61ab5-138">Remember to delete the saved item manually.</span></span>

<span data-ttu-id="61ab5-139">Некоторые из этих элементов созданы корпорацией Майкрософт, а другие — сообществом PowerShell.</span><span class="sxs-lookup"><span data-stu-id="61ab5-139">Some of these items are authored by Microsoft, and others are authored by the PowerShell community.</span></span>
<span data-ttu-id="61ab5-140">Корпорация Майкрософт рекомендует ознакомиться с содержимым и кодом элементов в этой коллекции перед их установкой.</span><span class="sxs-lookup"><span data-stu-id="61ab5-140">Microsoft recommends that you review the contents and code of items on this gallery prior to installation.</span></span>

<span data-ttu-id="61ab5-141">Если вы нашли элемент, который по вашему мнению опубликован с нарушениями, щелкните **Сообщить о нарушении** на странице этого элемента.</span><span class="sxs-lookup"><span data-stu-id="61ab5-141">If you discover an item that you feel is not published in good faith, click **Report Abuse** on that item's page.</span></span>

### <a name="install"></a><span data-ttu-id="61ab5-142">Установка</span><span class="sxs-lookup"><span data-stu-id="61ab5-142">Install</span></span>

<span data-ttu-id="61ab5-143">Чтобы установить элемент из коллекции для использования, выполните командлет [Install-Module][] или [Install-Script][] в зависимости от типа элемента.</span><span class="sxs-lookup"><span data-stu-id="61ab5-143">To install an item from the Gallery for use, run either the [Install-Module][] or [Install-Script][] cmdlet, depending on the item type.</span></span>

<span data-ttu-id="61ab5-144">Командлет [Install-Module][] устанавливает модуль в `$env:ProgramFiles\WindowsPowerShell\Modules` по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="61ab5-144">[Install-Module][] installs the module to `$env:ProgramFiles\WindowsPowerShell\Modules` by default.</span></span>
<span data-ttu-id="61ab5-145">Для выполнения этой операции необходима учетная запись администратора.</span><span class="sxs-lookup"><span data-stu-id="61ab5-145">This requires an administrator account.</span></span> <span data-ttu-id="61ab5-146">При добавлении параметра `-Scope CurrentUser` модуль будет установлен в каталог `$env:USERPROFILE\Documents\WindowsPowerShell\Modules`.</span><span class="sxs-lookup"><span data-stu-id="61ab5-146">If you add the `-Scope CurrentUser` parameter, the module is installed to `$env:USERPROFILE\Documents\WindowsPowerShell\Modules` .</span></span>

<span data-ttu-id="61ab5-147">Командлет [Install-Script][] по умолчанию устанавливает скрипт в каталог `$env:ProgramFiles\WindowsPowerShell\Scripts`.</span><span class="sxs-lookup"><span data-stu-id="61ab5-147">[Install-Script][] installs the script to `$env:ProgramFiles\WindowsPowerShell\Scripts` by default.</span></span>
<span data-ttu-id="61ab5-148">Для выполнения этой операции необходима учетная запись администратора.</span><span class="sxs-lookup"><span data-stu-id="61ab5-148">This requires an administrator account.</span></span> <span data-ttu-id="61ab5-149">При добавлении параметра `-Scope CurrentUser` скрипт будет установлен в каталог `$env:USERPROFILE\Documents\WindowsPowerShell\Scripts`.</span><span class="sxs-lookup"><span data-stu-id="61ab5-149">If you add the `-Scope CurrentUser` parameter, the script is installed to `$env:USERPROFILE\Documents\WindowsPowerShell\Scripts` .</span></span>

<span data-ttu-id="61ab5-150">По умолчанию командлеты [Install-Module][] and [Install-Script][] устанавливают последнюю версию элемента.</span><span class="sxs-lookup"><span data-stu-id="61ab5-150">By default, [Install-Module][] and [Install-Script][] installs the most current version of an item.</span></span>
<span data-ttu-id="61ab5-151">Чтобы установить более раннюю версию элемента, добавьте параметр `-RequiredVersion`.</span><span class="sxs-lookup"><span data-stu-id="61ab5-151">To install an older version of the item, add the `-RequiredVersion` parameter.</span></span>

### <a name="deploy"></a><span data-ttu-id="61ab5-152">Развертывание</span><span class="sxs-lookup"><span data-stu-id="61ab5-152">Deploy</span></span>

<span data-ttu-id="61ab5-153">Чтобы развернуть элемент из коллекции PowerShell в службе автоматизации Azure, нажмите кнопку **Развернуть в службе автоматизации Azure** на странице подробностей об элементе.</span><span class="sxs-lookup"><span data-stu-id="61ab5-153">To deploy an item from the PowerShell Gallery to Azure Automation, click **Deploy to Azure Automation** on the item details page.</span></span> <span data-ttu-id="61ab5-154">После этого вы будете перенаправлены на портал управления Azure, на который нужно войти с использованием учетных данных учетной записи Azure.</span><span class="sxs-lookup"><span data-stu-id="61ab5-154">You will be redirected to the Azure Management Portal, where you sign in by using your Azure account credentials.</span></span> <span data-ttu-id="61ab5-155">Обратите внимание, что развертывание элементов с зависимостями приводит к развертыванию всех зависимостей в службе автоматизации Azure.</span><span class="sxs-lookup"><span data-stu-id="61ab5-155">Note that deploying items with dependencies will deploy all the dependencies to Azure Automation.</span></span> <span data-ttu-id="61ab5-156">Кнопку "Развернуть в службе автоматизации Azure" можно отключить, добавив тег **AzureAutomationNotSupported** в метаданные элемента.</span><span class="sxs-lookup"><span data-stu-id="61ab5-156">The 'Deploy to Azure Automation' button can be disabled by adding the **AzureAutomationNotSupported** tag to your item metadata.</span></span>

<span data-ttu-id="61ab5-157">Дополнительные сведения о службе автоматизации Azure см. в [соответствующей](/azure/automation) документации.</span><span class="sxs-lookup"><span data-stu-id="61ab5-157">To learn more about Azure Automation, see the [Azure Automation](/azure/automation) documentation.</span></span>

## <a name="updating-items-from-the-powershell-gallery"></a><span data-ttu-id="61ab5-158">Обновление элементов из коллекции PowerShell</span><span class="sxs-lookup"><span data-stu-id="61ab5-158">Updating items from the PowerShell Gallery</span></span>

<span data-ttu-id="61ab5-159">Чтобы обновить элементы, установленные из коллекции PowerShell, выполните командлет [Update-Module][] или [Update-Script][].</span><span class="sxs-lookup"><span data-stu-id="61ab5-159">To update items installed from the PowerShell Gallery, run either the [Update-Module][] or [Update-Script][] cmdlet.</span></span> <span data-ttu-id="61ab5-160">При запуске без дополнительных параметров [Update-Module][] пытается обновить каждый модуль, установленный командлетом [Install-Module][].</span><span class="sxs-lookup"><span data-stu-id="61ab5-160">When run without any additional parameters, [Update-Module][] attempts to update each module installed by running [Install-Module][].</span></span> <span data-ttu-id="61ab5-161">Чтобы выборочно обновить модули, добавьте параметр `-Name`.</span><span class="sxs-lookup"><span data-stu-id="61ab5-161">To selectively update modules, add the `-Name` parameter.</span></span>

<span data-ttu-id="61ab5-162">Аналогично при запуске без дополнительных параметров [Update-Script][] пытается обновить каждый сценарий, установленный командлетом [Install-Script][].</span><span class="sxs-lookup"><span data-stu-id="61ab5-162">Similarly, when run without any additional parameters, [Update-Script][] also attempts to update each script installed by running [Install-Script][].</span></span> <span data-ttu-id="61ab5-163">Чтобы выборочно обновить скрипты, добавьте параметр `-Name`.</span><span class="sxs-lookup"><span data-stu-id="61ab5-163">To selectively update scripts, add the `-Name` parameter.</span></span>

## <a name="list-items-that-you-have-installed-from-the-powershell-gallery"></a><span data-ttu-id="61ab5-164">Перечисление элементов, установленных из коллекции PowerShell</span><span class="sxs-lookup"><span data-stu-id="61ab5-164">List items that you have installed from the PowerShell Gallery</span></span>

<span data-ttu-id="61ab5-165">Чтобы узнать, какие модули вы установили из коллекции PowerShell, выполните командлет [Get-InstalledModule][].</span><span class="sxs-lookup"><span data-stu-id="61ab5-165">To find out which modules you have installed from the PowerShell Gallery, run the [Get-InstalledModule][] cmdlet.</span></span> <span data-ttu-id="61ab5-166">Эта команда перечисляет все модули в системе, установленные непосредственно из коллекции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="61ab5-166">This command lists all of the modules you have on your system that were installed directly from the PowerShell Gallery.</span></span>

<span data-ttu-id="61ab5-167">Аналогично, чтобы узнать, какие скрипты были установлены из коллекции PowerShell, выполните командлет [Get-InstalledScript][].</span><span class="sxs-lookup"><span data-stu-id="61ab5-167">Similarly, to find out which scripts you have installed from the PowerShell Gallery, run the [Get-InstalledScript][] cmdlet.</span></span> <span data-ttu-id="61ab5-168">Эта команда перечисляет все скрипты в системе, установленные непосредственно из коллекции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="61ab5-168">This command lists all of the scripts you have on your system that were installed directly from the PowerShell Gallery.</span></span>

[Find-DscResource]: /powershell/module/powershellget/Find-DscResource
[Find-Module]: /powershell/module/powershellget/Find-Module
[Find-Script]: /powershell/module/powershellget/Find-Script
[Get-InstalledModule]: /powershell/module/powershellget/Get-InstalledModule
[Get-InstalledScript]: /powershell/module/powershellget/Get-InstalledScript
[Install-Module]: /powershell/module/powershellget/Install-Module
[Install-Script]: /powershell/module/powershellget/Install-Script
[Publish-Module]: /powershell/module/powershellget/Publish-Module
[Publish-Script]: /powershell/module/powershellget/Publish-Script
[Register-PSRepository]: /powershell/module/powershellget/Register-Repository
[Save-Module]: /powershell/module/powershellget/Save-Module
[Save-Script]: /powershell/module/powershellget/Save-Script