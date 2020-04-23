---
ms.date: 06/12/2017
ms.topic: conceptual
keywords: wmf,powershell,установка
title: Заметки о выпуске WMF 5.x
ms.openlocfilehash: 3fc712dbcbe184c60ae248b260c8f6800f111fdd
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "79402361"
---
# <a name="windows-management-framework-wmf-5x-release-notes"></a><span data-ttu-id="f6438-103">Заметки о выпуске Windows Management Framework (WMF) 5.x</span><span class="sxs-lookup"><span data-stu-id="f6438-103">Windows Management Framework (WMF) 5.x Release Notes</span></span>

## <a name="wmf-50-changes"></a><span data-ttu-id="f6438-104">Изменения WMF 5.0</span><span class="sxs-lookup"><span data-stu-id="f6438-104">WMF 5.0 Changes</span></span>

- <span data-ttu-id="f6438-105">В PowerShell 5.0 добавлен новый структурированный поток **сведений**</span><span class="sxs-lookup"><span data-stu-id="f6438-105">PowerShell 5.0 adds a new structured **Information** stream</span></span>
- <span data-ttu-id="f6438-106">Усовершенствования DSC, включая четыре новых ресурса DSC:</span><span class="sxs-lookup"><span data-stu-id="f6438-106">Improvements to DSC including four new DSC resources:</span></span>
  - <span data-ttu-id="f6438-107">WindowsFeatureSet</span><span class="sxs-lookup"><span data-stu-id="f6438-107">WindowsFeatureSet</span></span>
  - <span data-ttu-id="f6438-108">WindowsOptionalFeatureSet</span><span class="sxs-lookup"><span data-stu-id="f6438-108">WindowsOptionalFeatureSet</span></span>
  - <span data-ttu-id="f6438-109">ServiceSet</span><span class="sxs-lookup"><span data-stu-id="f6438-109">ServiceSet</span></span>
  - <span data-ttu-id="f6438-110">ProcessSet</span><span class="sxs-lookup"><span data-stu-id="f6438-110">ProcessSet</span></span>
- <span data-ttu-id="f6438-111">Добавлена Just Enough Administration для обеспечения ролевого администрирования через удаленное взаимодействие PowerShell</span><span class="sxs-lookup"><span data-stu-id="f6438-111">Added Just Enough Administration to enable role-based administration through PowerShell remoting</span></span>
- <span data-ttu-id="f6438-112">PowerShell 5.0 расширяет язык, включив пользовательские классы и перечисления</span><span class="sxs-lookup"><span data-stu-id="f6438-112">PowerShell 5.0 extends the language to include user-defined classes and enumerations</span></span>
- <span data-ttu-id="f6438-113">Усовершенствованы функции отладки в интегрированной среде сценариев PowerShell и добавлена удаленная отладка</span><span class="sxs-lookup"><span data-stu-id="f6438-113">Improved debugging features in PowerShell ISE and added remote debugging</span></span>
- <span data-ttu-id="f6438-114">Добавлены модули PowerShellGet и PackageManagement</span><span class="sxs-lookup"><span data-stu-id="f6438-114">Added the PowerShellGet and PackageManagement modules</span></span>
- <span data-ttu-id="f6438-115">Расширено ведение журнала сценариев и записи PowerShell</span><span class="sxs-lookup"><span data-stu-id="f6438-115">Enhanced PowerShell script logging and transcripts</span></span>
- <span data-ttu-id="f6438-116">Добавлены командлеты Cryptographic Message Syntax</span><span class="sxs-lookup"><span data-stu-id="f6438-116">Add Cryptographic Message Syntax cmdlets</span></span>
- <span data-ttu-id="f6438-117">WMF 5.0 включает в себя модуль NetworkSwitchManager для Windows</span><span class="sxs-lookup"><span data-stu-id="f6438-117">WMF 5.0 includes the NetworkSwitchManager module for Windows</span></span>
- <span data-ttu-id="f6438-118">Добавлен модуль Microsoft.PowerShell.ODataUtils</span><span class="sxs-lookup"><span data-stu-id="f6438-118">Added the Microsoft.PowerShell.ODataUtils module</span></span>
- <span data-ttu-id="f6438-119">Добавлена поддержка инвентаризации программного обеспечения (SIL)</span><span class="sxs-lookup"><span data-stu-id="f6438-119">Added support for Software Inventory Logging (SIL)</span></span>
- <span data-ttu-id="f6438-120">Представлены новые или обновленные командлеты сервера по запросам пользователей и для решения проблем</span><span class="sxs-lookup"><span data-stu-id="f6438-120">Sever new or update cmdlets in response to user requests and issues</span></span>

## <a name="wmf-51-changes"></a><span data-ttu-id="f6438-121">Изменения WMF 5.1</span><span class="sxs-lookup"><span data-stu-id="f6438-121">WMF 5.1 Changes</span></span>

<span data-ttu-id="f6438-122">WMF 5.1 включает компоненты PowerShell, WMI, WinRM и Software Inventory Logging (SIL), которые были выпущены с Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="f6438-122">WMF 5.1 includes the PowerShell, WMI, WinRM, and Software Inventory Logging (SIL) components that were released with Windows Server 2016.</span></span> <span data-ttu-id="f6438-123">Службу WMF 5.1 можно установить на Windows 7, Windows 8.1, Windows Server 2008 R2, 2012 и 2012 R2; она предоставляет ряд улучшений в WMF 5.0, включая следующие:</span><span class="sxs-lookup"><span data-stu-id="f6438-123">WMF 5.1 can be installed on Windows 7, Windows 8.1, Windows Server 2008 R2, 2012, and 2012 R2, and provides several improvements over WMF 5.0 including:</span></span>

- <span data-ttu-id="f6438-124">Новые командлеты</span><span class="sxs-lookup"><span data-stu-id="f6438-124">New cmdlets</span></span>
- <span data-ttu-id="f6438-125">Улучшения PowerShellGet включают принудительное подписание модулей и установку модулей JEA.</span><span class="sxs-lookup"><span data-stu-id="f6438-125">PowerShellGet improvements include enforcing signed modules, and installing JEA modules</span></span>
- <span data-ttu-id="f6438-126">Дополнительная поддержка PackageManagement для контейнеров, установка CBS, установка на основе EXE, пакеты CAB.</span><span class="sxs-lookup"><span data-stu-id="f6438-126">PackageManagement added support for Containers, CBS Setup, EXE-based setup, CAB packages</span></span>
- <span data-ttu-id="f6438-127">Улучшения отладки для классов DSC и PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f6438-127">Debugging improvements for DSC and PowerShell classes</span></span>
- <span data-ttu-id="f6438-128">Улучшения для системы безопасности, включая принудительное использование модулей, подписанных каталогом и полученных от опрашивающего сервера, а также при использовании командлетов PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="f6438-128">Security enhancements including enforcement of catalog-signed modules coming from the Pull Server and when using PowerShellGet cmdlets</span></span>
- <span data-ttu-id="f6438-129">Ответы на разные запросы пользователей и решение проблем.</span><span class="sxs-lookup"><span data-stu-id="f6438-129">Responses to a number of user requests and issues</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f6438-130">Перед установкой WMF 5.1 в Windows Server 2008 или Windows 7 убедитесь, что WMF 3.0 не установлен.</span><span class="sxs-lookup"><span data-stu-id="f6438-130">Before you install WMF 5.1 on Windows Server 2008 or Windows 7, confirm that WMF 3.0 isn't installed.</span></span> <span data-ttu-id="f6438-131">Дополнительные сведения см. в статье о [предварительных требованиях WMF 5.1 для Windows Server 2008 R2 с пакетом обновления 1 (SP1) и Windows 7 с пакетом обновления 1 (SP1)](../setup/install-configure.md#wmf-51-prerequisites-for-windows-server-2008-r2-sp1-and-windows-7-sp1).</span><span class="sxs-lookup"><span data-stu-id="f6438-131">For more information, see [WMF 5.1 Prerequisites for Windows Server 2008 R2 SP1 and Windows 7 SP1](../setup/install-configure.md#wmf-51-prerequisites-for-windows-server-2008-r2-sp1-and-windows-7-sp1).</span></span>

## <a name="powershell-editions"></a><span data-ttu-id="f6438-132">Выпуски PowerShell</span><span class="sxs-lookup"><span data-stu-id="f6438-132">PowerShell Editions</span></span>

<span data-ttu-id="f6438-133">Начиная с версии 5.1 доступны различные выпуски среды PowerShell, что означает различные наборы возможностей и совместимость с разными платформами.</span><span class="sxs-lookup"><span data-stu-id="f6438-133">Starting with version 5.1, PowerShell is available in different editions that denote varying feature sets and platform compatibility.</span></span>

- <span data-ttu-id="f6438-134">**Выпуск Desktop:** создан на базе платформы .NET Framework и обеспечивает совместимость со сценариями и модулями, предназначенными для версий PowerShell в полноценных выпусках Windows, таких как Server Core и Windows Desktop.</span><span class="sxs-lookup"><span data-stu-id="f6438-134">**Desktop Edition:** Built on .NET Framework and provides compatibility with scripts and modules targeting versions of PowerShell running on full footprint editions of Windows such as Server Core and Windows Desktop.</span></span>
- <span data-ttu-id="f6438-135">**Выпуск Core Edition:** построен на основе .NET Core и обеспечивает совместимость со скриптами и модулями, которые предназначены для версий PowerShell, выполняющихся в выпусках Windows с ограниченными возможностями, таких как Nano Server и Windows IoT.</span><span class="sxs-lookup"><span data-stu-id="f6438-135">**Core Edition:** Built on .NET Core and provides compatibility with scripts and modules targeting versions of PowerShell running on reduced footprint editions of Windows such as Nano Server and Windows IoT.</span></span>

### <a name="learn-more-about-using-powershell-editions"></a><span data-ttu-id="f6438-136">Дополнительные сведения об использовании выпусков PowerShell</span><span class="sxs-lookup"><span data-stu-id="f6438-136">Learn more about using PowerShell Editions</span></span>

- [<span data-ttu-id="f6438-137">Определение запущенного выпуска PowerShell с использованием $PSVersionTable</span><span class="sxs-lookup"><span data-stu-id="f6438-137">Determine running edition of PowerShell using $PSVersionTable</span></span>](/powershell/module/microsoft.powershell.core/about/about_automatic_variables)
- [<span data-ttu-id="f6438-138">Фильтрация результатов командлета Get-Module по CompatiblePSEditions с помощью параметра PSEdition</span><span class="sxs-lookup"><span data-stu-id="f6438-138">Filter Get-Module results by CompatiblePSEditions using PSEdition parameter</span></span>](/powershell/module/microsoft.powershell.core/get-module)
- [<span data-ttu-id="f6438-139">Запрет на выполнение сценариев в несовместимых выпусках PowerShell</span><span class="sxs-lookup"><span data-stu-id="f6438-139">Prevent script execution unless run on a compatible edition of PowerShell</span></span>](/powershell/scripting/gallery/concepts/script-psedition-support)
- [<span data-ttu-id="f6438-140">Объявление совместимости модуля с определенными версиями PowerShell</span><span class="sxs-lookup"><span data-stu-id="f6438-140">Declare a module's compatibility to specific PowerShell versions</span></span>](/powershell/scripting/gallery/concepts/module-psedition-support)

## <a name="module-analysis-cache"></a><span data-ttu-id="f6438-141">Кэш анализа модуля</span><span class="sxs-lookup"><span data-stu-id="f6438-141">Module Analysis Cache</span></span>

<span data-ttu-id="f6438-142">Начиная с версии WMF 5.1 среда PowerShell предоставляет средства управления файлом, в котором кэшируются сведения о модуле, например экспортируемые им команды.</span><span class="sxs-lookup"><span data-stu-id="f6438-142">Starting with WMF 5.1, PowerShell provides control over the file that is used to cache data about a module, such as the commands it exports.</span></span>

<span data-ttu-id="f6438-143">По умолчанию этот кэш хранится в файле `${env:LOCALAPPDATA}\Microsoft\Windows\PowerShell\ModuleAnalysisCache`.</span><span class="sxs-lookup"><span data-stu-id="f6438-143">By default, this cache is stored in the file `${env:LOCALAPPDATA}\Microsoft\Windows\PowerShell\ModuleAnalysisCache`.</span></span> <span data-ttu-id="f6438-144">Кэш обычно считывается при запуске в процессе поиска команды и записывается в фоновом потоке через некоторое время после импорта модуля.</span><span class="sxs-lookup"><span data-stu-id="f6438-144">The cache is typically read at startup while searching for a command and is written on a background thread sometime after a module is imported.</span></span>

<span data-ttu-id="f6438-145">Чтобы изменить расположение кэша по умолчанию, присвойте значение переменной среды `$env:PSModuleAnalysisCachePath` перед запуском PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f6438-145">To change the default location of the cache, set the `$env:PSModuleAnalysisCachePath` environment variable before starting PowerShell.</span></span> <span data-ttu-id="f6438-146">Изменения, вносимые в эту переменную среды, влияют только на дочерние процессы.</span><span class="sxs-lookup"><span data-stu-id="f6438-146">Changes to this environment variable will only affect children processes.</span></span> <span data-ttu-id="f6438-147">Значение должно быть полным путем (включая имя файла), на создание и запись файлов по которому у среды PowerShell есть разрешение.</span><span class="sxs-lookup"><span data-stu-id="f6438-147">The value should name a full path (including filename) that PowerShell has permission to create and write files.</span></span> <span data-ttu-id="f6438-148">Чтобы отключить файловый кэш, укажите в качестве этого значения недопустимое расположение, например:</span><span class="sxs-lookup"><span data-stu-id="f6438-148">To disable the file cache, set this value to an invalid location, for example:</span></span>

```powershell
$env:PSModuleAnalysisCachePath = 'nul'
```

<span data-ttu-id="f6438-149">Таким образом задается путь к недопустимому устройству.</span><span class="sxs-lookup"><span data-stu-id="f6438-149">This sets the path to an invalid device.</span></span> <span data-ttu-id="f6438-150">Если среда PowerShell не может осуществлять запись по указанному пути, ошибка не выводится; сообщения об ошибках можно получить, используя трассировщик:</span><span class="sxs-lookup"><span data-stu-id="f6438-150">If PowerShell can't write to the path, no error is returned, but you can see error reporting by using a tracer:</span></span>

```powershell
Trace-Command -PSHost -Name Modules -Expression { Import-Module Microsoft.PowerShell.Management -Force }
```

<span data-ttu-id="f6438-151">При выгрузке кэша среда PowerShell ищет модули, которые больше не существуют, чтобы кэш не был излишне большим.</span><span class="sxs-lookup"><span data-stu-id="f6438-151">When writing out the cache, PowerShell will check for modules that no longer exist to avoid an unnecessarily large cache.</span></span> <span data-ttu-id="f6438-152">Иногда эти проверки нежелательны. В этом случае их можно отключить, задав</span><span class="sxs-lookup"><span data-stu-id="f6438-152">Sometimes these checks are not desirable, in which case you can turn them off by setting:</span></span>

```powershell
$env:PSDisableModuleAnalysisCacheCleanup = 1
```

<span data-ttu-id="f6438-153">Новое значение этой переменной среды вступает в силу немедленно в текущем процессе.</span><span class="sxs-lookup"><span data-stu-id="f6438-153">Setting this environment variable will take effect immediately in the current process.</span></span>

## <a name="specifying-module-version"></a><span data-ttu-id="f6438-154">Указание версии модуля</span><span class="sxs-lookup"><span data-stu-id="f6438-154">Specifying module version</span></span>

<span data-ttu-id="f6438-155">В WMF 5.1 `using module` работает так же, как другие связанные с модулями конструкции в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f6438-155">In WMF 5.1, `using module` behaves the same way as other module-related constructions in PowerShell.</span></span>
<span data-ttu-id="f6438-156">Ранее не было возможности указать определенную версию модуля; при наличии нескольких версий возникала ошибка.</span><span class="sxs-lookup"><span data-stu-id="f6438-156">Previously, you had no way to specify a particular module version; if there were multiple versions present, this resulted in an error.</span></span>

<span data-ttu-id="f6438-157">В WMF 5.1:</span><span class="sxs-lookup"><span data-stu-id="f6438-157">In WMF 5.1:</span></span>

- <span data-ttu-id="f6438-158">Вы можете использовать [конструктор ModuleSpecification (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor?view=powershellsdk-1.1.0#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).</span><span class="sxs-lookup"><span data-stu-id="f6438-158">You can use [ModuleSpecification Constructor (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor?view=powershellsdk-1.1.0#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).</span></span>

  <span data-ttu-id="f6438-159">Она имеет тот же формат, что и `Get-Module -FullyQualifiedName`.</span><span class="sxs-lookup"><span data-stu-id="f6438-159">This hash table has the same format as `Get-Module -FullyQualifiedName`.</span></span>

  <span data-ttu-id="f6438-160">**Пример:** `using module @{ModuleName = 'PSReadLine'; RequiredVersion = '1.1'}`</span><span class="sxs-lookup"><span data-stu-id="f6438-160">**Example:** `using module @{ModuleName = 'PSReadLine'; RequiredVersion = '1.1'}`</span></span>

- <span data-ttu-id="f6438-161">Если имеется несколько версий модуля, в PowerShell используется **та же логика разрешения**, что и в `Import-Module`, и ошибка не выводится. Это поведение аналогично поведению `Import-Module` и `Import-DscResource`.</span><span class="sxs-lookup"><span data-stu-id="f6438-161">If there are multiple versions of the module, PowerShell uses the **same resolution logic** as `Import-Module` and doesn't return an error--the same behavior as `Import-Module` and `Import-DscResource`.</span></span>

## <a name="improvements-to-pester"></a><span data-ttu-id="f6438-162">Усовершенствования Pester</span><span class="sxs-lookup"><span data-stu-id="f6438-162">Improvements to Pester</span></span>

<span data-ttu-id="f6438-163">В WMF 5.1 обновлена версия Pester, распространяемая с PowerShell, с 3.3.5 до 3.4.0.</span><span class="sxs-lookup"><span data-stu-id="f6438-163">In WMF 5.1, the version of Pester that ships with PowerShell has been updated from 3.3.5 to 3.4.0.</span></span>
<span data-ttu-id="f6438-164">Это обновление улучшает работу Pester на сервере Nano Server.</span><span class="sxs-lookup"><span data-stu-id="f6438-164">This update enables better behavior for Pester on Nano Server.</span></span>

<span data-ttu-id="f6438-165">Изменения в Pest можно просмотреть в [журнале изменений](https://github.com/pester/Pester/blob/master/CHANGELOG.md) в репозитории GitHub.</span><span class="sxs-lookup"><span data-stu-id="f6438-165">You can review the changes in Pest by inspecting the [ChangeLog](https://github.com/pester/Pester/blob/master/CHANGELOG.md) in the GitHub repository.</span></span>
