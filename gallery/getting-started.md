---
ms.date: 06/12/2017
contributor: JKeithB
keywords: коллекции,powershell,командлет,psgallery
title: Приступая к работе с коллекцией PowerShell
ms.openlocfilehash: 39998df1a2bf9363dd008dc96a802157c8d691d7
ms.sourcegitcommit: e46b868f56f359909ff7c8230b1d1770935cce0e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/13/2018
ms.locfileid: "45523063"
---
# <a name="get-started-with-the-powershell-gallery"></a><span data-ttu-id="22643-103">Приступая к работе с коллекцией PowerShell</span><span class="sxs-lookup"><span data-stu-id="22643-103">Get Started with the PowerShell Gallery</span></span>

<span data-ttu-id="22643-104">Правильным способом установки элементов из коллекции PowerShel является использование командлетов в модуле [PowerShellGet](/powershell/module/powershellget).</span><span class="sxs-lookup"><span data-stu-id="22643-104">The proper way to install items from the PowerShell Gallery is to use the cmdlets in the [PowerShellGet](/powershell/module/powershellget) module.</span></span> <span data-ttu-id="22643-105">Входить в систему для скачивания элементов из коллекции PowerShell необязательно.</span><span class="sxs-lookup"><span data-stu-id="22643-105">You do not need to sign in to download items from the PowerShell Gallery.</span></span>

> [!NOTE]
> <span data-ttu-id="22643-106">Можно скачать пакет непосредственно из коллекции PowerShell, но делать это не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="22643-106">It is possible to download a package from the PowerShell Gallery directly, but this is not a recommended approach.</span></span> <span data-ttu-id="22643-107">Дополнительные сведения см. в статье [Скачивание пакета вручную](https://msdn.microsoft.com/en-us/powershell/gallery/psgallery/how-to/working-with-items/manual-download.md).</span><span class="sxs-lookup"><span data-stu-id="22643-107">For more details, see [Manual Package Download](https://msdn.microsoft.com/en-us/powershell/gallery/psgallery/how-to/working-with-items/manual-download.md).</span></span>  


## <a name="discovering-items-from-the-powershell-gallery"></a><span data-ttu-id="22643-108">Обнаружение элементов в коллекции PowerShell</span><span class="sxs-lookup"><span data-stu-id="22643-108">Discovering items from the PowerShell Gallery</span></span>

<span data-ttu-id="22643-109">Найти элементы в коллекции PowerShell можно при помощи элемента управления **Поиск** на сайте или просмотрев страницы "Модули" и "Скрипты".</span><span class="sxs-lookup"><span data-stu-id="22643-109">You can find items in the PowerShell Gallery by using the **Search** control on this website, or by browsing through the Modules and Scripts pages.</span></span> <span data-ttu-id="22643-110">Найти элементы в коллекции PowerShell можно также при помощи командлетов [Find-Module][] и [Find-Script][] (в зависимости от типа элемента) с параметром `-Repository PSGallery`.</span><span class="sxs-lookup"><span data-stu-id="22643-110">You can also find items from the PowerShell Gallery by running the [Find-Module][] and [Find-Script][] cmdlets, depending on the item type, with `-Repository PSGallery`.</span></span>

<span data-ttu-id="22643-111">Для фильтрации результатов поиска в коллекции используются следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="22643-111">Filtering results from the Gallery can be done by using the following parameters:</span></span>

- <span data-ttu-id="22643-112">Name</span><span class="sxs-lookup"><span data-stu-id="22643-112">Name</span></span>
- <span data-ttu-id="22643-113">AllVersions</span><span class="sxs-lookup"><span data-stu-id="22643-113">AllVersions</span></span>
- <span data-ttu-id="22643-114">MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="22643-114">MinimumVersion</span></span>
- <span data-ttu-id="22643-115">RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="22643-115">RequiredVersion</span></span>
- <span data-ttu-id="22643-116">Tag</span><span class="sxs-lookup"><span data-stu-id="22643-116">Tag</span></span>
- <span data-ttu-id="22643-117">Includes</span><span class="sxs-lookup"><span data-stu-id="22643-117">Includes</span></span>
- <span data-ttu-id="22643-118">DscResource</span><span class="sxs-lookup"><span data-stu-id="22643-118">DscResource</span></span>
- <span data-ttu-id="22643-119">RoleCapability</span><span class="sxs-lookup"><span data-stu-id="22643-119">RoleCapability</span></span>
- <span data-ttu-id="22643-120">Команда</span><span class="sxs-lookup"><span data-stu-id="22643-120">Command</span></span>
- <span data-ttu-id="22643-121">Фильтр</span><span class="sxs-lookup"><span data-stu-id="22643-121">Filter</span></span>

<span data-ttu-id="22643-122">Если вас интересуют только определенные ресурсы DSC в коллекции, выполните командлет [Find-DscResource].</span><span class="sxs-lookup"><span data-stu-id="22643-122">If you're only interested in discovering specific DSC resources in the Gallery, you can run the [Find-DscResource] cmdlet.</span></span> <span data-ttu-id="22643-123">Командлет Find-DscResource возвращает сведения о ресурсах DSC, содержащихся в коллекции.</span><span class="sxs-lookup"><span data-stu-id="22643-123">Find-DscResource returns data on DSC resources contained in the Gallery.</span></span>
<span data-ttu-id="22643-124">Поскольку ресурсы DSC всегда являются частью модуля, вам по-прежнему потребуется выполнить командлет [Install-Module][], чтобы установить их.</span><span class="sxs-lookup"><span data-stu-id="22643-124">Because DSC resources are always delivered as part of a module, you still need to run [Install-Module][] to install those DSC resources.</span></span>

## <a name="learning-about-items-in-the-powershell-gallery"></a><span data-ttu-id="22643-125">Изучение элементов в коллекции PowerShell</span><span class="sxs-lookup"><span data-stu-id="22643-125">Learning about items in the PowerShell Gallery</span></span>

<span data-ttu-id="22643-126">Когда вы нашли элемент, который вас интересует, о нем можно узнать больше.</span><span class="sxs-lookup"><span data-stu-id="22643-126">Once you've identified an item you're interested in, you may want to learn more about it.</span></span> <span data-ttu-id="22643-127">Для этого можно изучить страницу конкретного элемента в коллекции.</span><span class="sxs-lookup"><span data-stu-id="22643-127">You can do this by examining that item's specific page on the Gallery.</span></span> <span data-ttu-id="22643-128">На ней представлены все метаданные, переданные вместе с элементом.</span><span class="sxs-lookup"><span data-stu-id="22643-128">On that page, you'll be able to see all of the metadata uploaded with the item.</span></span> <span data-ttu-id="22643-129">Эти метаданные предоставляются автором элемента и не проверяются корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="22643-129">This metadata for an item is provided by the item's author, and is not verified by Microsoft.</span></span> <span data-ttu-id="22643-130">Владелец элемента тесно связан с учетной записью в коллекции, используемой для публикации элемента, поэтому ориентироваться на нее — более надежно, чем на информацию в поле "Автор".</span><span class="sxs-lookup"><span data-stu-id="22643-130">The Owner of the item is strongly tied to the Gallery account used to publish the item, and is more trustworthy than the Author field.</span></span>

<span data-ttu-id="22643-131">Если вы нашли элемент, который по вашему мнению опубликован с нарушениями, щелкните **Сообщить о нарушении** на странице этого элемента.</span><span class="sxs-lookup"><span data-stu-id="22643-131">If you discover an item that you feel is not published in good faith, click **Report Abuse** on that item's page.</span></span>

<span data-ttu-id="22643-132">При использовании командлетов [Find-Module][] или [Find-Script][] эти данные можно доступны в возвращенном объекте PSGetModuleInfo.</span><span class="sxs-lookup"><span data-stu-id="22643-132">If you're running [Find-Module][] or [Find-Script][], you can view this data in the returned PSGetModuleInfo object.</span></span> <span data-ttu-id="22643-133">Например, при выполнении `Find-Module -Name PSReadLine -Repository PSGallery |Get-Member`</span><span class="sxs-lookup"><span data-stu-id="22643-133">For example, running `Find-Module -Name PSReadLine -Repository PSGallery |Get-Member`</span></span>
<span data-ttu-id="22643-134">возвращаются сведения о модуле PSReadLine, содержащемся в коллекции.</span><span class="sxs-lookup"><span data-stu-id="22643-134">returns data on the PSReadLine module in the Gallery.</span></span>

## <a name="downloading-items-from-the-powershell-gallery"></a><span data-ttu-id="22643-135">Скачивание элементов из коллекции PowerShell</span><span class="sxs-lookup"><span data-stu-id="22643-135">Downloading items from the PowerShell Gallery</span></span>

<span data-ttu-id="22643-136">При скачивании элементов из коллекции PowerShell рекомендуется использовать следующий процесс.</span><span class="sxs-lookup"><span data-stu-id="22643-136">We encourage the following process when downloading items from the PowerShell Gallery:</span></span>

### <a name="inspect"></a><span data-ttu-id="22643-137">Изучение</span><span class="sxs-lookup"><span data-stu-id="22643-137">Inspect</span></span>

<span data-ttu-id="22643-138">Чтобы скачать элемент из коллекции для изучения, выполните командлет [Save-Module][] или [Save-Script][] в зависимости от типа элемента.</span><span class="sxs-lookup"><span data-stu-id="22643-138">To download an item from the Gallery for inspection, run either the [Save-Module][] or [Save-Script][] cmdlet, depending on the item type.</span></span> <span data-ttu-id="22643-139">Так вы сможете сохранить элемент локально без установки и проверить его содержимое.</span><span class="sxs-lookup"><span data-stu-id="22643-139">This lets you save the item locally without installing it, and inspect the item contents.</span></span> <span data-ttu-id="22643-140">Не забудьте удалить элемент, сохраненный вручную.</span><span class="sxs-lookup"><span data-stu-id="22643-140">Remember to delete the saved item manually.</span></span>

<span data-ttu-id="22643-141">Некоторые из этих элементов созданы корпорацией Майкрософт, а другие — сообществом PowerShell.</span><span class="sxs-lookup"><span data-stu-id="22643-141">Some of these items are authored by Microsoft, and others are authored by the PowerShell community.</span></span>
<span data-ttu-id="22643-142">Корпорация Майкрософт рекомендует ознакомиться с содержимым и кодом элементов в этой коллекции перед их установкой.</span><span class="sxs-lookup"><span data-stu-id="22643-142">Microsoft recommends that you review the contents and code of items on this gallery prior to installation.</span></span>

<span data-ttu-id="22643-143">Если вы нашли элемент, который по вашему мнению опубликован с нарушениями, щелкните **Сообщить о нарушении** на странице этого элемента.</span><span class="sxs-lookup"><span data-stu-id="22643-143">If you discover an item that you feel is not published in good faith, click **Report Abuse** on that item's page.</span></span>

### <a name="install"></a><span data-ttu-id="22643-144">Установка</span><span class="sxs-lookup"><span data-stu-id="22643-144">Install</span></span>

<span data-ttu-id="22643-145">Чтобы установить элемент из коллекции для использования, выполните командлет [Install-Module][] или [Install-Script][] в зависимости от типа элемента.</span><span class="sxs-lookup"><span data-stu-id="22643-145">To install an item from the Gallery for use, run either the [Install-Module][] or [Install-Script][] cmdlet, depending on the item type.</span></span>

<span data-ttu-id="22643-146">Командлет [Install-Module][] устанавливает модуль в `$env:ProgramFiles\WindowsPowerShell\Modules` по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="22643-146">[Install-Module][] installs the module to `$env:ProgramFiles\WindowsPowerShell\Modules` by default.</span></span>
<span data-ttu-id="22643-147">Для выполнения этой операции необходима учетная запись администратора.</span><span class="sxs-lookup"><span data-stu-id="22643-147">This requires an administrator account.</span></span> <span data-ttu-id="22643-148">При добавлении параметра `-Scope CurrentUser` модуль будет установлен в каталог `$env:USERPROFILE\Documents\WindowsPowerShell\Modules`.</span><span class="sxs-lookup"><span data-stu-id="22643-148">If you add the `-Scope CurrentUser` parameter, the module is installed to `$env:USERPROFILE\Documents\WindowsPowerShell\Modules` .</span></span>

<span data-ttu-id="22643-149">Командлет [Install-Script][] по умолчанию устанавливает скрипт в каталог `$env:ProgramFiles\WindowsPowerShell\Scripts`.</span><span class="sxs-lookup"><span data-stu-id="22643-149">[Install-Script][] installs the script to `$env:ProgramFiles\WindowsPowerShell\Scripts` by default.</span></span>
<span data-ttu-id="22643-150">Для выполнения этой операции необходима учетная запись администратора.</span><span class="sxs-lookup"><span data-stu-id="22643-150">This requires an administrator account.</span></span> <span data-ttu-id="22643-151">При добавлении параметра `-Scope CurrentUser` скрипт будет установлен в каталог `$env:USERPROFILE\Documents\WindowsPowerShell\Scripts`.</span><span class="sxs-lookup"><span data-stu-id="22643-151">If you add the `-Scope CurrentUser` parameter, the script is installed to `$env:USERPROFILE\Documents\WindowsPowerShell\Scripts` .</span></span>

<span data-ttu-id="22643-152">По умолчанию командлеты [Install-Module][] and [Install-Script][] устанавливают последнюю версию элемента.</span><span class="sxs-lookup"><span data-stu-id="22643-152">By default, [Install-Module][] and [Install-Script][] installs the most current version of an item.</span></span>
<span data-ttu-id="22643-153">Чтобы установить более раннюю версию элемента, добавьте параметр `-RequiredVersion`.</span><span class="sxs-lookup"><span data-stu-id="22643-153">To install an older version of the item, add the `-RequiredVersion` parameter.</span></span>

### <a name="deploy"></a><span data-ttu-id="22643-154">Развертывание</span><span class="sxs-lookup"><span data-stu-id="22643-154">Deploy</span></span>

<span data-ttu-id="22643-155">Чтобы развернуть элемент из коллекции PowerShell в службе автоматизации Azure, нажмите кнопку **Развернуть в службе автоматизации Azure** на странице подробностей об элементе.</span><span class="sxs-lookup"><span data-stu-id="22643-155">To deploy an item from the PowerShell Gallery to Azure Automation, click **Deploy to Azure Automation** on the item details page.</span></span> <span data-ttu-id="22643-156">После этого вы будете перенаправлены на портал управления Azure, на который нужно войти с использованием учетных данных учетной записи Azure.</span><span class="sxs-lookup"><span data-stu-id="22643-156">You will be redirected to the Azure Management Portal, where you sign in by using your Azure account credentials.</span></span> <span data-ttu-id="22643-157">Обратите внимание, что развертывание элементов с зависимостями приводит к развертыванию всех зависимостей в службе автоматизации Azure.</span><span class="sxs-lookup"><span data-stu-id="22643-157">Note that deploying items with dependencies will deploy all the dependencies to Azure Automation.</span></span> <span data-ttu-id="22643-158">Кнопку "Развернуть в службе автоматизации Azure" можно отключить, добавив тег **AzureAutomationNotSupported** в метаданные элемента.</span><span class="sxs-lookup"><span data-stu-id="22643-158">The 'Deploy to Azure Automation' button can be disabled by adding the **AzureAutomationNotSupported** tag to your item metadata.</span></span>

<span data-ttu-id="22643-159">Дополнительные сведения о службе автоматизации Azure см. в [соответствующей](/azure/automation) документации.</span><span class="sxs-lookup"><span data-stu-id="22643-159">To learn more about Azure Automation, see the [Azure Automation](/azure/automation) documentation.</span></span>

## <a name="updating-items-from-the-powershell-gallery"></a><span data-ttu-id="22643-160">Обновление элементов из коллекции PowerShell</span><span class="sxs-lookup"><span data-stu-id="22643-160">Updating items from the PowerShell Gallery</span></span>

<span data-ttu-id="22643-161">Чтобы обновить элементы, установленные из коллекции PowerShell, выполните командлет [Update-Module][] или [Update-Script][].</span><span class="sxs-lookup"><span data-stu-id="22643-161">To update items installed from the PowerShell Gallery, run either the [Update-Module][] or [Update-Script][] cmdlet.</span></span> <span data-ttu-id="22643-162">При запуске без дополнительных параметров [Update-Module][] пытается обновить каждый модуль, установленный командлетом [Install-Module][].</span><span class="sxs-lookup"><span data-stu-id="22643-162">When run without any additional parameters, [Update-Module][] attempts to update each module installed by running [Install-Module][].</span></span> <span data-ttu-id="22643-163">Чтобы выборочно обновить модули, добавьте параметр `-Name`.</span><span class="sxs-lookup"><span data-stu-id="22643-163">To selectively update modules, add the `-Name` parameter.</span></span>

<span data-ttu-id="22643-164">Аналогично при запуске без дополнительных параметров [Update-Script][] пытается обновить каждый сценарий, установленный командлетом [Install-Script][].</span><span class="sxs-lookup"><span data-stu-id="22643-164">Similarly, when run without any additional parameters, [Update-Script][] also attempts to update each script installed by running [Install-Script][].</span></span> <span data-ttu-id="22643-165">Чтобы выборочно обновить скрипты, добавьте параметр `-Name`.</span><span class="sxs-lookup"><span data-stu-id="22643-165">To selectively update scripts, add the `-Name` parameter.</span></span>

## <a name="list-items-that-you-have-installed-from-the-powershell-gallery"></a><span data-ttu-id="22643-166">Перечисление элементов, установленных из коллекции PowerShell</span><span class="sxs-lookup"><span data-stu-id="22643-166">List items that you have installed from the PowerShell Gallery</span></span>

<span data-ttu-id="22643-167">Чтобы узнать, какие модули вы установили из коллекции PowerShell, выполните командлет [Get-InstalledModule][].</span><span class="sxs-lookup"><span data-stu-id="22643-167">To find out which modules you have installed from the PowerShell Gallery, run the [Get-InstalledModule][] cmdlet.</span></span> <span data-ttu-id="22643-168">Эта команда перечисляет все модули в системе, установленные непосредственно из коллекции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="22643-168">This command lists all of the modules you have on your system that were installed directly from the PowerShell Gallery.</span></span>

<span data-ttu-id="22643-169">Аналогично, чтобы узнать, какие скрипты были установлены из коллекции PowerShell, выполните командлет [Get-InstalledScript][].</span><span class="sxs-lookup"><span data-stu-id="22643-169">Similarly, to find out which scripts you have installed from the PowerShell Gallery, run the [Get-InstalledScript][] cmdlet.</span></span> <span data-ttu-id="22643-170">Эта команда перечисляет все скрипты в системе, установленные непосредственно из коллекции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="22643-170">This command lists all of the scripts you have on your system that were installed directly from the PowerShell Gallery.</span></span>

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