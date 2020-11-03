---
description: Описание новых функций, которые входят в Windows PowerShell 5,1.
keywords: powershell,командлет
Locale: en-US
ms.date: 01/17/2018
online version: https://docs.microsoft.com/powershell/module/?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Windows_PowerShell_5.1
ms.openlocfilehash: 567af048dd137c0287c6eba4ccc42a77055c0c92
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "93233118"
---
# <a name="about_windows_powershell_51"></a><span data-ttu-id="22721-104">about_Windows_PowerShell_5.1</span><span class="sxs-lookup"><span data-stu-id="22721-104">about_Windows_PowerShell_5.1</span></span>

## <a name="short-description"></a><span data-ttu-id="22721-105">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="22721-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="22721-106">Описание новых функций, которые входят в Windows PowerShell 5,1.</span><span class="sxs-lookup"><span data-stu-id="22721-106">Describes new features that are included in Windows PowerShell 5.1.</span></span>

## <a name="long-description"></a><span data-ttu-id="22721-107">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="22721-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="22721-108">Windows PowerShell 5,1 включает в себя значительные новые функции, расширяющие возможности использования, улучшая удобство использования и позволяя более легко и полно управлять средами на основе Windows и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="22721-108">Windows PowerShell 5.1 includes significant new features that extend its use, improve its usability, and allow you to control and manage Windows-based environments more easily and comprehensively.</span></span>

<span data-ttu-id="22721-109">Windows PowerShell 5,1 обеспечивает обратную совместимость.</span><span class="sxs-lookup"><span data-stu-id="22721-109">Windows PowerShell 5.1 is backward-compatible.</span></span> <span data-ttu-id="22721-110">Командлеты, поставщики, модули, оснастки, сценарии, функции и профили, разработанные для Windows PowerShell 4,0, Windows PowerShell 3,0 и Windows PowerShell 2,0, обычно работают в Windows PowerShell 5,1 без изменений.</span><span class="sxs-lookup"><span data-stu-id="22721-110">Cmdlets, providers, modules, snap-ins, scripts, functions, and profiles that were designed for Windows PowerShell 4.0, Windows PowerShell 3.0, and Windows PowerShell 2.0 generally work in Windows PowerShell 5.1 without changes.</span></span>

- <span data-ttu-id="22721-111">Новые командлеты: локальные пользователи и группы; Get-ComputerInfo.</span><span class="sxs-lookup"><span data-stu-id="22721-111">New cmdlets: local users and groups; Get-ComputerInfo</span></span>
- <span data-ttu-id="22721-112">Улучшения PowerShellGet включают принудительное подписание модулей и установку модулей JEA.</span><span class="sxs-lookup"><span data-stu-id="22721-112">PowerShellGet improvements include enforcing signed modules, and installing JEA modules</span></span>
- <span data-ttu-id="22721-113">Дополнительная поддержка PackageManagement для контейнеров, установка CBS, установка на основе EXE, пакеты CAB.</span><span class="sxs-lookup"><span data-stu-id="22721-113">PackageManagement added support for Containers, CBS Setup, EXE-based setup, CAB packages</span></span>
- <span data-ttu-id="22721-114">Улучшения отладки для классов DSC и PowerShell.</span><span class="sxs-lookup"><span data-stu-id="22721-114">Debugging improvements for DSC and PowerShell classes</span></span>
- <span data-ttu-id="22721-115">Улучшения для системы безопасности, включая принудительное использование модулей, подписанных каталогом и полученных от опрашивающего сервера, а также при использовании командлетов PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="22721-115">Security enhancements including enforcement of catalog-signed modules coming from the Pull Server and when using PowerShellGet cmdlets</span></span>
- <span data-ttu-id="22721-116">Ответы на разные запросы пользователей и решение проблем.</span><span class="sxs-lookup"><span data-stu-id="22721-116">Responses to a number of user requests and issues</span></span>

<span data-ttu-id="22721-117">Windows PowerShell 5,1 устанавливается по умолчанию в Windows Server 2016 и Windows 10.</span><span class="sxs-lookup"><span data-stu-id="22721-117">Windows PowerShell 5.1 is installed by default on Windows Server 2016 and Windows 10.</span></span> <span data-ttu-id="22721-118">Чтобы установить Windows PowerShell 5,1 на Windows Server 2012 R2, Windows 8.1 Enterprise или Windows 8.1 Pro, см. статью [Установка и настройка WMF 5,1](/powershell/scripting/wmf/setup/install-configure).</span><span class="sxs-lookup"><span data-stu-id="22721-118">To install Windows PowerShell 5.1 on Windows Server 2012 R2, Windows 8.1 Enterprise, or Windows 8.1 Pro, see [Install and Configure WMF 5.1](/powershell/scripting/wmf/setup/install-configure).</span></span>
<span data-ttu-id="22721-119">Перед установкой Windows Management Framework 5,1 обязательно прочтите сведения о скачивании и выполните все требования к системе.</span><span class="sxs-lookup"><span data-stu-id="22721-119">Be sure to read the download details, and meet all system requirements, before you install Windows Management Framework 5.1.</span></span>

<span data-ttu-id="22721-120">Вы также можете ознакомиться с изменениями в Windows PowerShell 5,1 в статье [новые возможности Windows PowerShell](/powershell/scripting/windows-powershell/whats-new/what-s-new-in-windows-powershell-50).</span><span class="sxs-lookup"><span data-stu-id="22721-120">You can also read about changes to Windows PowerShell 5.1 in [What's New in Windows PowerShell](/powershell/scripting/windows-powershell/whats-new/what-s-new-in-windows-powershell-50).</span></span>

## <a name="new-scenarios-and-features-in-wmf-51"></a><span data-ttu-id="22721-121">Новые сценарии и возможности в WMF 5.1</span><span class="sxs-lookup"><span data-stu-id="22721-121">New Scenarios and Features in WMF 5.1</span></span>

> <span data-ttu-id="22721-122">Примечание. Эта информация является предварительной и может быть изменена.</span><span class="sxs-lookup"><span data-stu-id="22721-122">Note: This information is preliminary and subject to change.</span></span>

### <a name="powershell-editions"></a><span data-ttu-id="22721-123">Выпуски PowerShell</span><span class="sxs-lookup"><span data-stu-id="22721-123">PowerShell Editions</span></span>
<span data-ttu-id="22721-124">Начиная с версии 5.1, среда PowerShell доступна в разных выпусках, обладающих различными наборами функций и совместимостью с платформами.</span><span class="sxs-lookup"><span data-stu-id="22721-124">Starting with version 5.1, PowerShell is available in different editions which denote varying feature sets and platform compatibility.</span></span>

- <span data-ttu-id="22721-125">**Выпуск Desktop** создан на базе платформы .NET Framework и обеспечивает совместимость со скриптами и модулями, предназначенными для версий PowerShell в полноценных выпусках Windows, таких как Server Core и Windows Desktop.</span><span class="sxs-lookup"><span data-stu-id="22721-125">**Desktop Edition:** Built on .NET Framework and provides compatibility with scripts and modules targeting versions of PowerShell running on full footprint editions of Windows such as Server Core and Windows Desktop.</span></span>
- <span data-ttu-id="22721-126">**Core Edition:** построен на основе .NET Core и обеспечивает совместимость со скриптами и модулями, которые предназначены для версий PowerShell, выполняющихся в выпусках Windows с ограниченными возможностями, таких как Nano Server и Windows IoT.</span><span class="sxs-lookup"><span data-stu-id="22721-126">**Core Edition:** Built on .NET Core and provides compatibility with scripts and modules targeting versions of PowerShell running on reduced footprint editions of Windows such as Nano Server and Windows IoT.</span></span>

<span data-ttu-id="22721-127">**Дополнительные сведения об использовании выпусков PowerShell**</span><span class="sxs-lookup"><span data-stu-id="22721-127">**Learn more about using PowerShell Editions**</span></span>

- [<span data-ttu-id="22721-128">Определение запущенного выпуска PowerShell с использованием $PSVersionTable</span><span class="sxs-lookup"><span data-stu-id="22721-128">Determine running edition of PowerShell using $PSVersionTable</span></span>](/powershell/module/microsoft.powershell.core/about/about_automatic_variables)
- [<span data-ttu-id="22721-129">Фильтрация результатов командлета Get-Module по CompatiblePSEditions с помощью параметра PSEdition</span><span class="sxs-lookup"><span data-stu-id="22721-129">Filter Get-Module results by CompatiblePSEditions using PSEdition parameter</span></span>](/powershell/module/microsoft.powershell.core/get-module)
- [<span data-ttu-id="22721-130">Запрет на выполнение сценариев в несовместимых выпусках PowerShell</span><span class="sxs-lookup"><span data-stu-id="22721-130">Prevent script execution unless run on a compatible edition of PowerShell</span></span>](/powershell/scripting/gallery/concepts/script-psedition-support)
- [<span data-ttu-id="22721-131">Объявление совместимости модуля с определенными версиями PowerShell</span><span class="sxs-lookup"><span data-stu-id="22721-131">Declare a module's compatibility to specific PowerShell versions</span></span>](/powershell/scripting/gallery/concepts/module-psedition-support)

### <a name="catalog-cmdlets"></a><span data-ttu-id="22721-132">Командлеты для работы с каталогами</span><span class="sxs-lookup"><span data-stu-id="22721-132">Catalog Cmdlets</span></span>

<span data-ttu-id="22721-133">Мы добавили два новых командлета для создания и проверки файлов каталога Windows в модуль [Microsoft.Powershell.Security](/previous-versions/windows/powershell-scripting/hh847877(v=wps.640)).</span><span class="sxs-lookup"><span data-stu-id="22721-133">Two new cmdlets have been added in the [Microsoft.PowerShell.Security](/previous-versions/windows/powershell-scripting/hh847877(v=wps.640)) module; these generate and validate Windows catalog files.</span></span>

#### <a name="new-filecatalog"></a><span data-ttu-id="22721-134">New-FileCatalog</span><span class="sxs-lookup"><span data-stu-id="22721-134">New-FileCatalog</span></span>

<span data-ttu-id="22721-135">Командлет New-FileCatalog создает файл каталога Windows для набора файлов и папок.</span><span class="sxs-lookup"><span data-stu-id="22721-135">New-FileCatalog creates a Windows catalog file for set of folders and files.</span></span>
<span data-ttu-id="22721-136">Файл каталога содержит хэши для всех файлов, находящихся по указанным путям.</span><span class="sxs-lookup"><span data-stu-id="22721-136">This catalog file contains hashes for all files in specified paths.</span></span> <span data-ttu-id="22721-137">Пользователь может распространять набор папок вместе с соответствующим файлом каталога, представляющим этих папки.</span><span class="sxs-lookup"><span data-stu-id="22721-137">Users can distribute the set of folders along with corresponding catalog file representing those folders.</span></span> <span data-ttu-id="22721-138">С помощью файла каталога получатель может проверить, были ли изменены папки с момента создания каталога.</span><span class="sxs-lookup"><span data-stu-id="22721-138">This information is useful to validate whether any changes have been made to the folders since catalog creation time.</span></span>

```
New-FileCatalog [-CatalogFilePath] <string> [[-Path] <string[]>]
 [-CatalogVersion <int>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

<span data-ttu-id="22721-139">Поддерживаются каталоги версий 1 и 2.</span><span class="sxs-lookup"><span data-stu-id="22721-139">Catalog versions 1 and 2 are supported.</span></span> <span data-ttu-id="22721-140">В версии 1 для создания хэшей файлов используется алгоритм хэширования SHA1, в версии 2 — SHA256.</span><span class="sxs-lookup"><span data-stu-id="22721-140">Version 1 uses the SHA1 hashing algorithm to create file hashes; version 2 uses SHA256.</span></span> <span data-ttu-id="22721-141">Каталог версии 2 не поддерживается в *Windows Server 2008 R2* и *Windows 7* .</span><span class="sxs-lookup"><span data-stu-id="22721-141">Catalog version 2 is not supported on *Windows Server 2008 R2* or *Windows 7* .</span></span> <span data-ttu-id="22721-142">На платформах *Windows 8* , *Windows Server 2012* и более поздней версии рекомендуется использовать каталог версии 2.</span><span class="sxs-lookup"><span data-stu-id="22721-142">You should use catalog version 2 on *Windows 8* , *Windows Server 2012* , and later operating systems.</span></span>

<span data-ttu-id="22721-143">Для проверки целостности файла каталога (Pester.cat в приведенном выше примере) его нужно подписать с помощью командлета [Set-AuthenticodeSignature](/powershell/module/microsoft.powershell.security/set-authenticodesignature).</span><span class="sxs-lookup"><span data-stu-id="22721-143">To verify the integrity of catalog file (Pester.cat in above example), sign it using [Set-AuthenticodeSignature](/powershell/module/microsoft.powershell.security/set-authenticodesignature) cmdlet.</span></span>

#### <a name="test-filecatalog"></a><span data-ttu-id="22721-144">Test-FileCatalog</span><span class="sxs-lookup"><span data-stu-id="22721-144">Test-FileCatalog</span></span>

<span data-ttu-id="22721-145">Командлет Test-FileCatalog проверяет каталог, представляющий набор папок.</span><span class="sxs-lookup"><span data-stu-id="22721-145">Test-FileCatalog validates the catalog representing a set of folders.</span></span>

```
Test-FileCatalog [-Detailed] [-FilesToSkip <String[]>]
 [-CatalogFilePath] <String> [[-Path] <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

<span data-ttu-id="22721-146">Этот командлет сравнивает все хэши файлов и их относительные пути в *каталоге* с хэшами и относительными путями на *диске* .</span><span class="sxs-lookup"><span data-stu-id="22721-146">This cmdlet compares all the files hashes and their relative paths found in *catalog* with ones on *disk* .</span></span> <span data-ttu-id="22721-147">При обнаружении любого несоответствия между хэшами файлов и путями он возвращает состояние *ValidationFailed* .</span><span class="sxs-lookup"><span data-stu-id="22721-147">If it detects any mismatch between file hashes and paths it returns the status as *ValidationFailed* .</span></span> <span data-ttu-id="22721-148">Все эти данные можно получить с помощью параметра *-Detailed* .</span><span class="sxs-lookup"><span data-stu-id="22721-148">Users can retrieve all this information by using the *-Detailed* parameter.</span></span> <span data-ttu-id="22721-149">Командлет также отображает состояние подписи каталога в свойстве *Signature* . Подпись также можно определить, вызвав командлет [Get-AuthenticodeSignature](/powershell/module/microsoft.powershell.security/get-authenticodesignature) и указав файл каталога.</span><span class="sxs-lookup"><span data-stu-id="22721-149">It also displays signing status of catalog in *Signature* property which is equivalent to calling [Get-AuthenticodeSignature](/powershell/module/microsoft.powershell.security/get-authenticodesignature) cmdlet on the catalog file.</span></span> <span data-ttu-id="22721-150">Также можно исключить любые файлы из проверки, указав их в параметре *-FilesToSkip* .</span><span class="sxs-lookup"><span data-stu-id="22721-150">Users can also skip any file during validation by using the *-FilesToSkip* parameter.</span></span>

### <a name="module-analysis-cache"></a><span data-ttu-id="22721-151">Кэш анализа модуля</span><span class="sxs-lookup"><span data-stu-id="22721-151">Module Analysis Cache</span></span>

<span data-ttu-id="22721-152">Начиная с версии WMF 5.1 среда PowerShell предоставляет средства управления файлом, в котором кэшируются сведения о модуле, например экспортируемые им команды.</span><span class="sxs-lookup"><span data-stu-id="22721-152">Starting with WMF 5.1, PowerShell provides control over the file that is used to cache data about a module, such as the commands it exports.</span></span>

<span data-ttu-id="22721-153">По умолчанию этот кэш хранится в файле `${env:LOCALAPPDATA}\Microsoft\Windows\PowerShell\ModuleAnalysisCache`.</span><span class="sxs-lookup"><span data-stu-id="22721-153">By default, this cache is stored in the file `${env:LOCALAPPDATA}\Microsoft\Windows\PowerShell\ModuleAnalysisCache`.</span></span> <span data-ttu-id="22721-154">Кэш обычно считывается при запуске в процессе поиска команды и записывается в фоновом потоке через некоторое время после импорта модуля.</span><span class="sxs-lookup"><span data-stu-id="22721-154">The cache is typically read at startup while searching for a command and is written on a background thread sometime after a module is imported.</span></span>

<span data-ttu-id="22721-155">Чтобы изменить расположение кэша по умолчанию, присвойте значение переменной среды `$env:PSModuleAnalysisCachePath` перед запуском PowerShell.</span><span class="sxs-lookup"><span data-stu-id="22721-155">To change the default location of the cache, set the `$env:PSModuleAnalysisCachePath` environment variable before starting PowerShell.</span></span> <span data-ttu-id="22721-156">Изменения, вносимые в эту переменную среды, влияют только на дочерние процессы.</span><span class="sxs-lookup"><span data-stu-id="22721-156">Changes to this environment variable will only affect children processes.</span></span> <span data-ttu-id="22721-157">Значение должно быть полным путем (включая имя файла), на создание и запись файлов по которому у среды PowerShell есть разрешение.</span><span class="sxs-lookup"><span data-stu-id="22721-157">The value should name a full path (including filename) that PowerShell has permission to create and write files.</span></span> <span data-ttu-id="22721-158">Чтобы отключить файловый кэш, укажите в качестве этого значения недопустимое расположение, например:</span><span class="sxs-lookup"><span data-stu-id="22721-158">To disable the file cache, set this value to an invalid location, for example:</span></span>

```powershell
$env:PSModuleAnalysisCachePath = 'nul'
```

<span data-ttu-id="22721-159">Таким образом задается путь к недопустимому устройству.</span><span class="sxs-lookup"><span data-stu-id="22721-159">This sets the path to an invalid device.</span></span> <span data-ttu-id="22721-160">Если среда PowerShell не может осуществлять запись по указанному пути, ошибка не выводится; сообщения об ошибках можно получить, используя трассировщик:</span><span class="sxs-lookup"><span data-stu-id="22721-160">If PowerShell can't write to the path, no error is returned, but you can see error reporting by using a tracer:</span></span>

```powershell
Trace-Command -PSHost -Name Modules -Expression {
  Import-Module Microsoft.PowerShell.Management -Force
}
```

<span data-ttu-id="22721-161">При выгрузке кэша среда PowerShell ищет модули, которые больше не существуют, чтобы кэш не был излишне большим.</span><span class="sxs-lookup"><span data-stu-id="22721-161">When writing out the cache, PowerShell will check for modules that no longer exist to avoid an unnecessarily large cache.</span></span> <span data-ttu-id="22721-162">Иногда эти проверки нежелательны. В этом случае их можно отключить, задав</span><span class="sxs-lookup"><span data-stu-id="22721-162">Sometimes these checks are not desirable, in which case you can turn them off by setting:</span></span>

```powershell
$env:PSDisableModuleAnalysisCacheCleanup = 1
```

<span data-ttu-id="22721-163">Новое значение этой переменной среды вступает в силу немедленно в текущем процессе.</span><span class="sxs-lookup"><span data-stu-id="22721-163">Setting this environment variable will take effect immediately in the current process.</span></span>

### <a name="specifying-module-version"></a><span data-ttu-id="22721-164">Указание версии модуля</span><span class="sxs-lookup"><span data-stu-id="22721-164">Specifying module version</span></span>

<span data-ttu-id="22721-165">В WMF 5.1 `using module` работает так же, как другие связанные с модулями конструкции в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="22721-165">In WMF 5.1, `using module` behaves the same way as other module-related constructions in PowerShell.</span></span> <span data-ttu-id="22721-166">Ранее не было возможности указать определенную версию модуля; при наличии нескольких версий возникала ошибка.</span><span class="sxs-lookup"><span data-stu-id="22721-166">Previously, you had no way to specify a particular module version; if there were multiple versions present, this resulted in an error.</span></span>

<span data-ttu-id="22721-167">В WMF 5.1:</span><span class="sxs-lookup"><span data-stu-id="22721-167">In WMF 5.1:</span></span>

* <span data-ttu-id="22721-168">Вы можете использовать [конструктор ModuleSpecification (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor).</span><span class="sxs-lookup"><span data-stu-id="22721-168">You can use [ModuleSpecification Constructor (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor).</span></span>
  <span data-ttu-id="22721-169">Она имеет тот же формат, что и `Get-Module -FullyQualifiedName`.</span><span class="sxs-lookup"><span data-stu-id="22721-169">This hash table has the same format as `Get-Module -FullyQualifiedName`.</span></span>

  <span data-ttu-id="22721-170">**Пример:** `using module @{ModuleName = 'PSReadLine'; RequiredVersion = '1.1'}`</span><span class="sxs-lookup"><span data-stu-id="22721-170">**Example:** `using module @{ModuleName = 'PSReadLine'; RequiredVersion = '1.1'}`</span></span>

* <span data-ttu-id="22721-171">Если имеется несколько версий модуля, в PowerShell используется **та же логика разрешения** , что и в `Import-Module`, и ошибка не выводится. Это поведение аналогично поведению `Import-Module` и `Import-DscResource`.</span><span class="sxs-lookup"><span data-stu-id="22721-171">If there are multiple versions of the module, PowerShell uses the **same resolution logic** as `Import-Module` and doesn't return an error--the same behavior as `Import-Module` and `Import-DscResource`.</span></span>

### <a name="improvements-to-pester"></a><span data-ttu-id="22721-172">Усовершенствования Pester</span><span class="sxs-lookup"><span data-stu-id="22721-172">Improvements to Pester</span></span>

<span data-ttu-id="22721-173">В WMF 5,1 версия Pester, входящая в состав PowerShell, была обновлена с 3.3.5 на 3.4.0, с добавлением GitHub [PR # 484](https://github.com/pester/Pester/pull/484), что обеспечивает лучшее поведение для Pester на Nano Server.</span><span class="sxs-lookup"><span data-stu-id="22721-173">In WMF 5.1, the version of Pester that ships with PowerShell has been updated from 3.3.5 to 3.4.0, with the addition of GitHub [PR# 484](https://github.com/pester/Pester/pull/484), which enables better behavior for Pester on Nano Server.</span></span>

<span data-ttu-id="22721-174">Чтобы просмотреть изменения в версиях с 3.3.5 по 3.4.0, откройте файл ChangeLog.md: https://github.com/pester/Pester/blob/master/CHANGELOG.md</span><span class="sxs-lookup"><span data-stu-id="22721-174">You can review the changes in versions 3.3.5 to 3.4.0 by inspecting the ChangeLog.md file at: https://github.com/pester/Pester/blob/master/CHANGELOG.md</span></span>

## <a name="keywords"></a><span data-ttu-id="22721-175">СЛОВАМИ</span><span class="sxs-lookup"><span data-stu-id="22721-175">KEYWORDS</span></span>

<span data-ttu-id="22721-176">Новые возможности Windows PowerShell 5,1</span><span class="sxs-lookup"><span data-stu-id="22721-176">What's New in Windows PowerShell 5.1</span></span>
