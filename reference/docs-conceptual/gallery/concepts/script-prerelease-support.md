---
ms.date: 10/17/2017
title: Предварительные версии сценариев
description: Модуль PowerShellGet предоставляет поддержку для назначения тегов скриптам с версией, превышающей 1.0.0, в качестве предварительного выпуска с использованием семантического управления версиями.
ms.openlocfilehash: e9873a69148fd80553e566b31c7455a4ecaee5ce
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92661466"
---
---
# <a name="prerelease-versions-of-scripts"></a><span data-ttu-id="c1b31-103">Предварительные версии сценариев</span><span class="sxs-lookup"><span data-stu-id="c1b31-103">Prerelease versions of scripts</span></span>

<span data-ttu-id="c1b31-104">Начиная с версии 1.6.0, PowerShellGet и коллекция PowerShell поддерживают маркировку версий с номерами выше 1.0.0 как предварительных.</span><span class="sxs-lookup"><span data-stu-id="c1b31-104">Starting with version 1.6.0, PowerShellGet and the PowerShell Gallery provide support for tagging versions greater than 1.0.0 as a prerelease.</span></span> <span data-ttu-id="c1b31-105">До этого номера предварительных версий пакетов должны были обязательно начинаться с 0.</span><span class="sxs-lookup"><span data-stu-id="c1b31-105">Prior to this feature, prerelease packages were limited to having a version beginning with 0.</span></span> <span data-ttu-id="c1b31-106">Такая возможность добавлена, чтобы улучшить поддержку соглашения о версиях [SemVer 1.0.0](http://semver.org/spec/v1.0.0.html) и при этом сохранить обратную совместимость с PowerShell версий 3 и выше, а также с текущими версиями PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="c1b31-106">The goal of these features is to provide greater support for [SemVer v1.0.0](http://semver.org/spec/v1.0.0.html) versioning convention without breaking backwards compatibility with PowerShell versions 3 and above, or existing versions of PowerShellGet.</span></span> <span data-ttu-id="c1b31-107">Этот раздел описывает особенности присвоения версий сценариям.</span><span class="sxs-lookup"><span data-stu-id="c1b31-107">This topic focuses on the script-specific features.</span></span> <span data-ttu-id="c1b31-108">Аналогичные возможности для модулей см. в разделе [Предварительные версии модулей](module-prerelease-support.md).</span><span class="sxs-lookup"><span data-stu-id="c1b31-108">The equivalent features for modules are in the [Prerelease Module Versions](module-prerelease-support.md) topic.</span></span> <span data-ttu-id="c1b31-109">Благодаря этой возможности издатель может присвоить своему сценарию предварительную версию 2.5.0-alpha, а затем выпустить готовую к использованию версию 2.5.0, которая заменит предварительную.</span><span class="sxs-lookup"><span data-stu-id="c1b31-109">Using these features, publishers can identify a script as version 2.5.0-alpha, and later release a production-ready version 2.5.0 that supersedes the prerelease version.</span></span>

<span data-ttu-id="c1b31-110">На высоком уровне возможности для предварительных версий сценариев включают:</span><span class="sxs-lookup"><span data-stu-id="c1b31-110">At a high level, the prerelease script features include:</span></span>

- <span data-ttu-id="c1b31-111">добавление суффикса PrereleaseString в строку версии в манифесте сценария.</span><span class="sxs-lookup"><span data-stu-id="c1b31-111">Adding a PrereleaseString suffix to the version string in the script manifest.</span></span> <span data-ttu-id="c1b31-112">При публикации скриптов в коллекцию PowerShell эти данные извлекаются из манифеста и используются для определения предварительных версий пакетов.</span><span class="sxs-lookup"><span data-stu-id="c1b31-112">When the scripts is published to the PowerShell Gallery, this data is extracted from the manifest, and used to identify prerelease packages.</span></span>
- <span data-ttu-id="c1b31-113">Для получения предварительных версий пакетов необходимо добавить флаг -AllowPrerelease к таким командам PowerShellGet, как Find-Script, Install-Script, Update-Script и Save-Script.</span><span class="sxs-lookup"><span data-stu-id="c1b31-113">Acquiring prerelease packages requires adding -AllowPrerelease flag to the PowerShellGet commands Find-Script, Install-Script, Update-Script, and Save-Script.</span></span> <span data-ttu-id="c1b31-114">Если этот флаг не указан, предварительные версии не будут отображаться.</span><span class="sxs-lookup"><span data-stu-id="c1b31-114">If the flag is not specified, prerelease packages will not be shown.</span></span>
- <span data-ttu-id="c1b31-115">Версии сценариев, отображаемые командлетами Find-Script и Get-InstalledScript, а также версии в коллекции PowerShell будут отображаться с параметром PrereleaseString, например: 2.5.0-alpha.</span><span class="sxs-lookup"><span data-stu-id="c1b31-115">Script versions displayed by Find-Script, Get-InstalledScript, and in the PowerShell Gallery will be displayed with the PrereleaseString, as in 2.5.0-alpha.</span></span>

<span data-ttu-id="c1b31-116">Ниже приведено подробное описание этих возможностей.</span><span class="sxs-lookup"><span data-stu-id="c1b31-116">Details for the features are included below.</span></span>

## <a name="identifying-a-script-version-as-a-prerelease"></a><span data-ttu-id="c1b31-117">Определение версии сценария как предварительной</span><span class="sxs-lookup"><span data-stu-id="c1b31-117">Identifying a script version as a prerelease</span></span>

<span data-ttu-id="c1b31-118">Реализация предварительных версий в PowerShellGet для сценариев проще, чем для модулей.</span><span class="sxs-lookup"><span data-stu-id="c1b31-118">PowerShellGet support for prerelease versions is easier for scripts than modules.</span></span> <span data-ttu-id="c1b31-119">Контроль версий сценариев поддерживается только в PowerShellGet, поэтому добавление суффикса к номеру предварительной версии не вызовет проблем совместимости.</span><span class="sxs-lookup"><span data-stu-id="c1b31-119">Script versioning is only supported by PowerShellGet, so there are no compatibility issues caused by adding the prerelease string.</span></span> <span data-ttu-id="c1b31-120">Для определения версии сценария в коллекции PowerShell как предварительной, добавьте суффикс предварительной версии к правильно сформированной строке версии в метаданных сценария.</span><span class="sxs-lookup"><span data-stu-id="c1b31-120">To identify a script in the PowerShell Gallery as a prerelease, add a prerelease suffix to a properly-formatted version string in the script metadata.</span></span>

<span data-ttu-id="c1b31-121">Пример манифеста сценария с предварительной версией</span><span class="sxs-lookup"><span data-stu-id="c1b31-121">An example section of a script manifest with a prerelease version would look like the following:</span></span>

```powershell
<#PSScriptInfo

.VERSION 3.2.1-alpha12

.GUID

...

#>
```

<span data-ttu-id="c1b31-122">Для использования суффикса предварительной версии строка версии должна удовлетворять следующим условиям.</span><span class="sxs-lookup"><span data-stu-id="c1b31-122">To use a prerelease suffix, the version string must meet the following requirements:</span></span>

- <span data-ttu-id="c1b31-123">Суффикс предварительной версии можно указать, только если версия состоит из трех сегментов в виде <основная_версия>.<дополнительная_версия>.<сборка>.</span><span class="sxs-lookup"><span data-stu-id="c1b31-123">A prerelease suffix may only be specified when the Version is 3 segments for Major.Minor.Build.</span></span>
  <span data-ttu-id="c1b31-124">Это соответствует соглашению о версиях SemVer 1.0.0.</span><span class="sxs-lookup"><span data-stu-id="c1b31-124">This aligns with SemVer v1.0.0</span></span>
- <span data-ttu-id="c1b31-125">Суффикс предварительной версии — это строка, которая начинается с дефиса и может содержать буквенно-цифровые символы ASCII [0-9A-Za-z-].</span><span class="sxs-lookup"><span data-stu-id="c1b31-125">The prerelease suffix is a string which begins with a hyphen, and may contain ASCII alphanumerics [0-9A-Za-z-]</span></span>
- <span data-ttu-id="c1b31-126">В настоящий момент поддерживается только SemVer версии 1.0.0, поэтому суффикс предварительной версии **не должен** содержать ни точек, ни символов + [.+], которые допустимы в SemVer 2.0.</span><span class="sxs-lookup"><span data-stu-id="c1b31-126">Only SemVer v1.0.0 prerelease strings are supported at this time, so the prerelease suffix **must not** contain either period or + [.+], which are allowed in SemVer 2.0</span></span>
- <span data-ttu-id="c1b31-127">Пример допустимых строк PrereleaseString: -alpha, -alpha1, -BETA, -update20171020</span><span class="sxs-lookup"><span data-stu-id="c1b31-127">Examples of supported PrereleaseString strings are: -alpha, -alpha1, -BETA, -update20171020</span></span>

### <a name="prerelease-versioning-impact-on-sort-order-and-installation-folders"></a><span data-ttu-id="c1b31-128">Влияние предварительных версий на порядок сортировки и установочные папки</span><span class="sxs-lookup"><span data-stu-id="c1b31-128">Prerelease versioning impact on sort order and installation folders</span></span>

<span data-ttu-id="c1b31-129">При использовании предварительных версий изменяется порядок сортировки, что имеет значение при публикации сценариев в коллекции PowerShell и при установке сценариев с помощью команд PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="c1b31-129">Sort order changes when using a prerelease version, which is important when publishing to the PowerShell Gallery, and when installing scripts using PowerShellGet commands.</span></span> <span data-ttu-id="c1b31-130">Если существует две версии сценария с одним номером, то сортировка производится по части строки, следующей после дефиса.</span><span class="sxs-lookup"><span data-stu-id="c1b31-130">If two scripts versions with the version number exist, the sort order is based on the string portion following the hyphen.</span></span> <span data-ttu-id="c1b31-131">Таким образом версия 2.5.0-alpha меньше, чем 2.5.0-beta, а последняя меньше, чем 2.5.0-gamma.</span><span class="sxs-lookup"><span data-stu-id="c1b31-131">So, version 2.5.0-alpha is less than 2.5.0-beta, which is less than 2.5.0-gamma.</span></span> <span data-ttu-id="c1b31-132">Если два сценария имеют одинаковый номер версии и только у одного из них есть строка PrereleaseString, то готовым к использованию будет считаться сценарий **без** суффикса предварительной версии и при сортировке он будет указываться, как имеющий более высокую версию по отношению к предварительной.</span><span class="sxs-lookup"><span data-stu-id="c1b31-132">If two scripts have the same version number, and only one has a PrereleaseString, the script **without** the prerelease suffix is assumed to be the production-ready version and will be sorted as a greater version than the prerelease version.</span></span> <span data-ttu-id="c1b31-133">Например: при сравнении версий 2.5.0 и 2.5.0-beta, будет считаться, что версия 2.5.0 имеет больший номер.</span><span class="sxs-lookup"><span data-stu-id="c1b31-133">As an example, when comparing releases 2.5.0 and 2.5.0-beta, the 2.5.0 version will be considered the greater of the two.</span></span>

<span data-ttu-id="c1b31-134">По умолчанию при публикации в коллекцию PowerShell новый сценарий обязательно должен иметь более высокую версию, чем все сценарии, опубликованные ранее.</span><span class="sxs-lookup"><span data-stu-id="c1b31-134">When publishing to the PowerShell Gallery, by default the version of the script being published must have a greater version than any previously-published version that is in the PowerShell Gallery.</span></span> <span data-ttu-id="c1b31-135">Издатель может обновить версию 2.5.0-alpha версией 2.5.0-beta или 2.5.0 (без суффикса предварительной версии).</span><span class="sxs-lookup"><span data-stu-id="c1b31-135">A publisher may update version 2.5.0-alpha with 2.5.0-beta, or with 2.5.0 (with no prerelease suffix).</span></span>

## <a name="finding-and-acquiring-prerelease-packages-using-powershellget-commands"></a><span data-ttu-id="c1b31-136">Поиск и получение предварительных версий пакетов с помощью команд PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="c1b31-136">Finding and acquiring prerelease packages using PowerShellGet commands</span></span>

<span data-ttu-id="c1b31-137">Для работы с предварительными версиями пакетов с помощью таких команд PowerShellGet, как Find-Script, Install-Script, Update-Script и Save-Script, необходимо добавлять флаг -AllowPrerelease.</span><span class="sxs-lookup"><span data-stu-id="c1b31-137">Dealing with prerelease packages using PowerShellGet Find-Script, Install-Script, Update-Script, and Save-Script commands requires adding the -AllowPrerelease flag.</span></span> <span data-ttu-id="c1b31-138">Если флаг -AllowPrerelease указан, в результат выполнения команды будут включены доступные предварительные версии пакетов.</span><span class="sxs-lookup"><span data-stu-id="c1b31-138">If -AllowPrerelease is specified, prerelease packages will be included if they are present.</span></span> <span data-ttu-id="c1b31-139">Если флаг -AllowPrerelease не указан, предварительные версии не будут отображаться.</span><span class="sxs-lookup"><span data-stu-id="c1b31-139">If -AllowPrerelease flag is not specified, prerelease packages will not be shown.</span></span>

<span data-ttu-id="c1b31-140">Единственным исключением является команда Get-InstalledScript и в некоторых случаях команда Uninstall-Script.</span><span class="sxs-lookup"><span data-stu-id="c1b31-140">The only exceptions to this in the PowerShellGet script commands are Get-InstalledScript, and some cases with Uninstall-Script.</span></span>

- <span data-ttu-id="c1b31-141">Команда Get-InstalledScript всегда автоматически отображает информацию о предварительных версиях в строке версии при ее наличии.</span><span class="sxs-lookup"><span data-stu-id="c1b31-141">Get-InstalledScript always will automatically show the prerelease information in the version string if it is present.</span></span>
- <span data-ttu-id="c1b31-142">Если **номер версии не указан** , то по умолчанию команда Uninstall-Script удалит самую последнюю версию сценария.</span><span class="sxs-lookup"><span data-stu-id="c1b31-142">Uninstall-Script will by default uninstall the most recent version of a script, if **no version** is specified.</span></span> <span data-ttu-id="c1b31-143">Такое поведение команды осталось неизменным.</span><span class="sxs-lookup"><span data-stu-id="c1b31-143">That behavior has not changed.</span></span> <span data-ttu-id="c1b31-144">Если предварительная версия указана с помощью `-RequiredVersion`, необходимо также указать `-AllowPrerelease`.</span><span class="sxs-lookup"><span data-stu-id="c1b31-144">However, if a prerelease version is specified using `-RequiredVersion`, `-AllowPrerelease` will be required.</span></span>

## <a name="examples"></a><span data-ttu-id="c1b31-145">Примеры</span><span class="sxs-lookup"><span data-stu-id="c1b31-145">Examples</span></span>

```powershell
# Assume the PowerShell Gallery has TestPackage versions 1.8.0 and 1.9.0-alpha.
# If -AllowPrerelease is not specified, only version 1.8.0 will be returned.
C:\windows\system32> Find-Script TestPackage

Version        Name                                Repository           Description
-------        ----                                ----------           -----------
1.8.0          TestPackage                         PSGallery            Package used to validate changes to the PowerShe...

C:\windows\system32> Find-Script TestPackage -AllowPrerelease

Version        Name                                Repository           Description
-------        ----                                ----------           -----------
1.9.0-alpha    TestPackage                         PSGallery            Package used to validate changes to PowerShe...

# To install a prerelease, you must specify -AllowPrerelease. Specifying a prerelease version string is not sufficient.

C:\windows\system32> Install-Script TestPackage -RequiredVersion 1.9.0-alpha

PackageManagement\Find-Package : No match was found for the specified search criteria and script name 'TestPackage'.
Try Get-PSRepository to see all available registered script repositories.
At C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\1.6.0\PSModule.psm1:1455 char:3
+         PackageManagement\Find-Package @PSBoundParameters | Microsoft ...
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (Microsoft.Power...ets.FindPackage:FindPackage)[Find-Package], Exception
    + FullyQualifiedErrorId : NoMatchFoundForCriteria,Microsoft.PowerShell.PackageManagement.Cmdlets.FindPackage

# The previous command failed because -AllowPrerelease was not specified.
# Adding -AllowPrerelease will result in success.

C:\windows\system32> Install-Script TestPackage -RequiredVersion 1.9.0-alpha -AllowPrerelease
C:\windows\system32> Get-InstalledScript TestPackage

Version         Name                                Repository           Description
-------         ----                                ----------           -----------
1.9.0-alpha     TestPackage                         PSGallery            Package used to validate changes to PowerShe...

# Note that Get-InstalledScript shows the prerelease version.
# If -RequiredVersion is not specified, all installed scripts will be displayed by Get-InstalledScript
```

<span data-ttu-id="c1b31-146">Если не задан флаг -RequiredVersion, то команда Uninstall-Script удалит текущую версию сценария.</span><span class="sxs-lookup"><span data-stu-id="c1b31-146">Uninstall-Script will remove the current version of a script when -RequiredVersion is not supplied.</span></span>
<span data-ttu-id="c1b31-147">Если в параметре -RequiredVersion указана предварительная версия, то необходимо обязательно добавить к команде флаг -AllowPrerelease.</span><span class="sxs-lookup"><span data-stu-id="c1b31-147">If -RequiredVersion is specified, and is a prerelease, -AllowPrerelease must be added to the command.</span></span>

``` powershell
C:\windows\system32> Get-InstalledScript TestPackage

Version         Name                                Repository           Description
-------         ----                                ----------           -----------
1.9.0-alpha     TestPackage                         PSGallery            Package used to validate changes to PowerShe...

C:\windows\system32> Uninstall-Script TestPackage -RequiredVersion 1.9.0-alpha
Uninstall-Script: The '-AllowPrerelease' parameter must be specified when using the Prerelease string in
MinimumVersion, MaximumVersion, or RequiredVersion.
At line:1 char:1
+ Uninstall-Script TestPackage -RequiredVersion 1.9.0-beta
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidArgument: (:) [Uninstall-Script], ArgumentException
    + FullyQualifiedErrorId : AllowPrereleaseRequiredToUsePrereleaseStringInVersion,Uninstall-script


C:\windows\system32> Uninstall-Script TestPackage -RequiredVersion 1.9.0-alpha -AllowPrerelease
# Since script versions are not installed side-by-side, the above could be simply "Uninstall-Script TestPackage"

C:\windows\system32> Get-Installedscript TestPackage
PackageManagement\Get-Package : No match was found for the specified search criteria and script names 'testpackage'.
At C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\1.5.0.0\PSModule.psm1:4088 char:9
+         PackageManagement\Get-Package @PSBoundParameters | Microsoft. ...
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (Microsoft.Power...lets.GetPackage:GetPackage) [Get-Package], Exception
    + FullyQualifiedErrorId : NoMatchFound,Microsoft.PowerShell.PackageManagement.Cmdlets.GetPackage
```

## <a name="more-details"></a><span data-ttu-id="c1b31-148">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="c1b31-148">More details</span></span>

- [<span data-ttu-id="c1b31-149">Предварительные версии модулей</span><span class="sxs-lookup"><span data-stu-id="c1b31-149">Prerelease Module Versions</span></span>](module-prerelease-support.md)
- [<span data-ttu-id="c1b31-150">Find-Script</span><span class="sxs-lookup"><span data-stu-id="c1b31-150">Find-script</span></span>](/powershell/module/powershellget/find-script)
- [<span data-ttu-id="c1b31-151">Install-Script</span><span class="sxs-lookup"><span data-stu-id="c1b31-151">Install-script</span></span>](/powershell/module/powershellget/install-script)
- [<span data-ttu-id="c1b31-152">Save-Script</span><span class="sxs-lookup"><span data-stu-id="c1b31-152">Save-script</span></span>](/powershell/module/powershellget/save-script)
- [<span data-ttu-id="c1b31-153">Update-Script</span><span class="sxs-lookup"><span data-stu-id="c1b31-153">Update-script</span></span>](/powershell/module/powershellget/update-script)
- [<span data-ttu-id="c1b31-154">Get-InstalledScript</span><span class="sxs-lookup"><span data-stu-id="c1b31-154">Get-Installedscript</span></span>](/powershell/module/powershellget/get-installedscript)
- [<span data-ttu-id="c1b31-155">Uninstall-Script</span><span class="sxs-lookup"><span data-stu-id="c1b31-155">UnInstall-script</span></span>](/powershell/module/powershellget/uninstall-script)
