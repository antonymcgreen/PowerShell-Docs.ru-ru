---
ms.date: 09/11/2018
contributor: JKeithB
keywords: gallery,powershell,psgallery
title: Скачивание пакета вручную
ms.openlocfilehash: c0a96e866dfd27f9b2170ea540ec6dd0c67701fd
ms.sourcegitcommit: 4a2cf30351620a58ba95ff5d76b247e601907589
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/27/2019
ms.locfileid: "71327895"
---
# <a name="manual-package-download"></a><span data-ttu-id="2a916-103">Скачивание пакета вручную</span><span class="sxs-lookup"><span data-stu-id="2a916-103">Manual Package Download</span></span>

<span data-ttu-id="2a916-104">В коллекции Powershell поддерживается прямое скачивание пакета с веб-сайта без использования командлетов PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="2a916-104">The PowerShell Gallery supports downloading a package from the website directly, without using the PowerShellGet cmdlets.</span></span> <span data-ttu-id="2a916-105">Любой пакет можно скачать в формате NuGet (файла с расширением `.nupkg`), который можно копировать во внутренний репозиторий.</span><span class="sxs-lookup"><span data-stu-id="2a916-105">You can download any package as a NuGet package (`.nupkg`) file, which you can then copy to an internal repository.</span></span>

> [!NOTE]
> <span data-ttu-id="2a916-106">Скачивание пакета вручную **не** является заменой использования командлета `Install-Module`.</span><span class="sxs-lookup"><span data-stu-id="2a916-106">Manual package download is **not** intended as a replacement for the `Install-Module` cmdlet.</span></span>
> <span data-ttu-id="2a916-107">При скачивании пакета не выполняется установка модуля или сценария.</span><span class="sxs-lookup"><span data-stu-id="2a916-107">Downloading the package doesn't install the module or script.</span></span> <span data-ttu-id="2a916-108">В скачанном пакете NuGet нет зависимостей.</span><span class="sxs-lookup"><span data-stu-id="2a916-108">Dependencies aren't included in the NuGet package downloaded.</span></span> <span data-ttu-id="2a916-109">Следующие инструкции приводятся только в информационных целях.</span><span class="sxs-lookup"><span data-stu-id="2a916-109">The following instructions are provided for reference purposes only.</span></span>

## <a name="using-manual-download-to-acquire-a-package"></a><span data-ttu-id="2a916-110">Получение пакета с помощью скачивания вручную</span><span class="sxs-lookup"><span data-stu-id="2a916-110">Using manual download to acquire a package</span></span>

<span data-ttu-id="2a916-111">На каждой странице находится ссылка для скачивания вручную, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="2a916-111">Each page has a link for Manual Download, as shown here:</span></span>

![Скачивание вручную](../../Images/packagedisplaypagewithpseditions.png)

<span data-ttu-id="2a916-113">Чтобы скачать пакет вручную, щелкните ссылку **Скачать необработанный NUPKG-файл**.</span><span class="sxs-lookup"><span data-stu-id="2a916-113">To download manually, click on **Download the raw nupkg file**.</span></span> <span data-ttu-id="2a916-114">Копия пакета копируется в папку загрузки с именем `<name>.<version>.nupkg`.</span><span class="sxs-lookup"><span data-stu-id="2a916-114">A copy of the package is copied to the download folder for your browser with the name `<name>.<version>.nupkg`.</span></span>

<span data-ttu-id="2a916-115">Пакет NuGet — это ZIP-архив с дополнительными файлами, содержащими сведения о содержимом пакета.</span><span class="sxs-lookup"><span data-stu-id="2a916-115">A NuGet package is a ZIP archive with extra files containing information about the contents of the package.</span></span> <span data-ttu-id="2a916-116">Некоторые браузеры, например Internet Explorer, автоматически заменяют расширение `.nupkg` на `.zip`.</span><span class="sxs-lookup"><span data-stu-id="2a916-116">Some browsers, like Internet Explorer, automatically replace the `.nupkg` file extension with `.zip`.</span></span> <span data-ttu-id="2a916-117">Чтобы развернуть пакет, при необходимости переименуйте файл `.nupkg` в `.zip`, затем извлеките его содержимое в локальную папку.</span><span class="sxs-lookup"><span data-stu-id="2a916-117">To expand the package, rename the `.nupkg` file to `.zip`, if needed, then extract the contents to a local folder.</span></span>

<span data-ttu-id="2a916-118">Файл пакета NuGet содержит следующие **характерные для NuGet элементы**, которые не являются частью исходного упакованного кода:</span><span class="sxs-lookup"><span data-stu-id="2a916-118">A NuGet package file includes the following **NuGet-specific elements** that aren't part of the original packaged code:</span></span>

- <span data-ttu-id="2a916-119">Папка `_rels` содержит файл `.rels` со списком зависимостей.</span><span class="sxs-lookup"><span data-stu-id="2a916-119">A folder named `_rels` - contains a `.rels` file that lists the dependencies</span></span>
- <span data-ttu-id="2a916-120">Папка `package` содержит характерные для NuGet данные.</span><span class="sxs-lookup"><span data-stu-id="2a916-120">A folder named `package` - contains the NuGet-specific data</span></span>
- <span data-ttu-id="2a916-121">Файл `[Content_Types].xml` описывает работу расширений, например PowerShellGet, с помощью NuGet.</span><span class="sxs-lookup"><span data-stu-id="2a916-121">A file named `[Content_Types].xml` - describes how extensions like PowerShellGet work with NuGet</span></span>
- <span data-ttu-id="2a916-122">Файл `<name>.nuspec` содержит основной объем метаданных.</span><span class="sxs-lookup"><span data-stu-id="2a916-122">A file named `<name>.nuspec` - contains the bulk of the metadata</span></span>

## <a name="installing-powershell-modules-from-a-nuget-package"></a><span data-ttu-id="2a916-123">Установка модулей PowerShell из пакета NuGet</span><span class="sxs-lookup"><span data-stu-id="2a916-123">Installing PowerShell modules from a NuGet package</span></span>

> [!NOTE]
> <span data-ttu-id="2a916-124">Результат выполнения этих инструкций **отличается** от результата запуска командлета `Install-Module`.</span><span class="sxs-lookup"><span data-stu-id="2a916-124">These instructions **DO NOT** give the same result as running `Install-Module`.</span></span> <span data-ttu-id="2a916-125">Эти инструкции отвечают минимальным требованиям.</span><span class="sxs-lookup"><span data-stu-id="2a916-125">These instructions fulfill the minimum requirements.</span></span> <span data-ttu-id="2a916-126">Они не предназначены для использования в качестве замены `Install-Module`.</span><span class="sxs-lookup"><span data-stu-id="2a916-126">They aren't intended to be a replacement for `Install-Module`.</span></span>
> <span data-ttu-id="2a916-127">Некоторые шаги, выполняемые командлетом `Install-Module`, не указаны.</span><span class="sxs-lookup"><span data-stu-id="2a916-127">Some steps performed by `Install-Module` aren't included.</span></span>

<span data-ttu-id="2a916-128">Проще всего удалить характерные для NuGet элементы из папки.</span><span class="sxs-lookup"><span data-stu-id="2a916-128">The easiest approach is to remove the NuGet-specific elements from the folder.</span></span> <span data-ttu-id="2a916-129">При удалении элементов код PowerShell, созданный автором пакета, остается без изменений.</span><span class="sxs-lookup"><span data-stu-id="2a916-129">Removing the elements leaves the PowerShell code created by the package author.</span></span>
<span data-ttu-id="2a916-130">Список элементов, относящихся к NuGet, см. в разделе о [скачивании пакета вручную](#using-manual-download-to-acquire-a-package).</span><span class="sxs-lookup"><span data-stu-id="2a916-130">For the list of NuGet-specific elements, see [Using manual download to acquire a package](#using-manual-download-to-acquire-a-package).</span></span>

<span data-ttu-id="2a916-131">Процесс состоит из следующих этапов.</span><span class="sxs-lookup"><span data-stu-id="2a916-131">The steps are as follows:</span></span>

1. <span data-ttu-id="2a916-132">Извлечь содержимое пакета NuGet в локальную папку.</span><span class="sxs-lookup"><span data-stu-id="2a916-132">Extract the contents of the NuGet package to a local folder.</span></span>
2. <span data-ttu-id="2a916-133">Удалить характерные для NuGet элементы из папки.</span><span class="sxs-lookup"><span data-stu-id="2a916-133">Delete the NuGet-specific elements from the folder.</span></span>
3. <span data-ttu-id="2a916-134">Переименовать папку.</span><span class="sxs-lookup"><span data-stu-id="2a916-134">Rename the folder.</span></span> <span data-ttu-id="2a916-135">По умолчанию используется имя папки `<name>.<version>`.</span><span class="sxs-lookup"><span data-stu-id="2a916-135">The default folder name is usually `<name>.<version>`.</span></span> <span data-ttu-id="2a916-136">Номер версии может содержать `-prerelease`, если модуль помечен как предварительная версия.</span><span class="sxs-lookup"><span data-stu-id="2a916-136">The version can include `-prerelease` if the module is tagged as a prerelease version.</span></span> <span data-ttu-id="2a916-137">Задать для папки имя модуля.</span><span class="sxs-lookup"><span data-stu-id="2a916-137">Rename the folder to just the module name.</span></span> <span data-ttu-id="2a916-138">Например, `azurerm.storage.5.0.4-preview` преобразуется в `azurerm.storage`.</span><span class="sxs-lookup"><span data-stu-id="2a916-138">For example, `azurerm.storage.5.0.4-preview` becomes `azurerm.storage`.</span></span>
4. <span data-ttu-id="2a916-139">Скопируйте папку в одну из папок в `$env:PSModulePath value`.</span><span class="sxs-lookup"><span data-stu-id="2a916-139">Copy the folder to one of the folders in the `$env:PSModulePath value`.</span></span> <span data-ttu-id="2a916-140">`$env:PSModulePath` — это набор разделенных точками с запятой путей, в которых оболочка PowerShell должна искать модули.</span><span class="sxs-lookup"><span data-stu-id="2a916-140">`$env:PSModulePath` is a semicolon-delimited set of paths in which PowerShell should look for modules.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2a916-141">При скачивании вручную не включаются зависимости, необходимые для модуля.</span><span class="sxs-lookup"><span data-stu-id="2a916-141">The manual download doesn't include any dependencies required by the module.</span></span> <span data-ttu-id="2a916-142">Если у пакета есть зависимости, они должны быть установлены в системе для правильной работы этого модуля.</span><span class="sxs-lookup"><span data-stu-id="2a916-142">If the package has dependencies, they must be installed on the system for this module to work correctly.</span></span> <span data-ttu-id="2a916-143">В коллекции PowerShell отображаются все зависимости, необходимые для пакета.</span><span class="sxs-lookup"><span data-stu-id="2a916-143">The PowerShell Gallery shows all dependencies required by the package.</span></span>

## <a name="installing-powershell-scripts-from-a-nuget-package"></a><span data-ttu-id="2a916-144">Установка сценариев PowerShell из пакета NuGet</span><span class="sxs-lookup"><span data-stu-id="2a916-144">Installing PowerShell scripts from a NuGet package</span></span>

> [!NOTE]
> <span data-ttu-id="2a916-145">Результат выполнения этих инструкций **отличается** от результата запуска командлета `Install-Script`.</span><span class="sxs-lookup"><span data-stu-id="2a916-145">These instructions **DO NOT** give the same result as running `Install-Script`.</span></span> <span data-ttu-id="2a916-146">Эти инструкции отвечают минимальным требованиям.</span><span class="sxs-lookup"><span data-stu-id="2a916-146">These instructions fulfill the minimum requirements.</span></span> <span data-ttu-id="2a916-147">Они не предназначены для использования в качестве замены `Install-Script`.</span><span class="sxs-lookup"><span data-stu-id="2a916-147">They aren't intended to be a replacement for `Install-Script`.</span></span>

<span data-ttu-id="2a916-148">Самым простым способом является извлечение пакета NuGet и использование сценария напрямую.</span><span class="sxs-lookup"><span data-stu-id="2a916-148">The easiest approach is to extract the NuGet package, then use the script directly.</span></span>

<span data-ttu-id="2a916-149">Процесс состоит из следующих этапов.</span><span class="sxs-lookup"><span data-stu-id="2a916-149">The steps are as follows:</span></span>

1. <span data-ttu-id="2a916-150">Извлечь содержимое пакета NuGet в локальную папку.</span><span class="sxs-lookup"><span data-stu-id="2a916-150">Extract the contents of the NuGet package.</span></span>
2. <span data-ttu-id="2a916-151">Файл `.PS1` в папке можно использовать прямо из этого расположения.</span><span class="sxs-lookup"><span data-stu-id="2a916-151">The `.PS1` file in the folder can be used directly from this location.</span></span>
3. <span data-ttu-id="2a916-152">Можно удалить характерные для NuGet элементы в папке.</span><span class="sxs-lookup"><span data-stu-id="2a916-152">You may delete the NuGet-specific elements in the folder.</span></span>

<span data-ttu-id="2a916-153">Список элементов, относящихся к NuGet, см. в разделе о [скачивании пакета вручную](#using-manual-download-to-acquire-a-package).</span><span class="sxs-lookup"><span data-stu-id="2a916-153">For the list of NuGet-specific elements, see [Using manual download to acquire a package](#using-manual-download-to-acquire-a-package).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2a916-154">При скачивании вручную не включаются зависимости, необходимые для модуля.</span><span class="sxs-lookup"><span data-stu-id="2a916-154">The manual download doesn't include any dependencies required by the module.</span></span> <span data-ttu-id="2a916-155">Если у пакета есть зависимости, они должны быть установлены в системе для правильной работы этого модуля.</span><span class="sxs-lookup"><span data-stu-id="2a916-155">If the package has dependencies, they must be installed on the system for this module to work correctly.</span></span> <span data-ttu-id="2a916-156">В коллекции PowerShell отображаются все зависимости, необходимые для пакета.</span><span class="sxs-lookup"><span data-stu-id="2a916-156">The PowerShell Gallery shows all dependencies required by the package.</span></span>
