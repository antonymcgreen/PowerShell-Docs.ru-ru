---
ms.date: 06/12/2017
ms.topic: conceptual
keywords: wmf,powershell,установка
title: Усовершенствования в управлении пакетами в WMF 5.1
ms.openlocfilehash: 24ff05d6bf5993826106f1a1d2cee6dad363d1e2
ms.sourcegitcommit: 01b81317029b28dd9b61d167045fd31f1ec7bc06
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2019
ms.locfileid: "65855429"
---
# <a name="improvements-to-package-management-in-wmf-51"></a><span data-ttu-id="d16ea-103">Усовершенствования в управлении пакетами в WMF 5.1</span><span class="sxs-lookup"><span data-stu-id="d16ea-103">Improvements to Package Management in WMF 5.1</span></span>

<span data-ttu-id="d16ea-104">Ниже перечислены исправления, внесенные в WMF 5.1.</span><span class="sxs-lookup"><span data-stu-id="d16ea-104">The following are the fixes made in the WMF 5.1:</span></span>

## <a name="version-alias"></a><span data-ttu-id="d16ea-105">Псевдоним версии</span><span class="sxs-lookup"><span data-stu-id="d16ea-105">Version Alias</span></span>

<span data-ttu-id="d16ea-106">**Ситуация**. Если в системе установлены версии 1.0 и 2.0 пакета P1 и вы хотите удалить версию 1.0, вы выполняете команду `Uninstall-Package -Name P1 -Version 1.0`. При этом вы ожидаете, что после выполнения командлета будет удалена версия 1.0.</span><span class="sxs-lookup"><span data-stu-id="d16ea-106">**Scenario**: If you have version 1.0 and 2.0 of a package, P1, installed on your system, and you want to uninstall version 1.0, you would run `Uninstall-Package -Name P1 -Version 1.0` and expect version 1.0 to be uninstalled after running the cmdlet.</span></span> <span data-ttu-id="d16ea-107">Но в результате удаляется версия 2.0.</span><span class="sxs-lookup"><span data-stu-id="d16ea-107">However the result is that version 2.0 gets uninstalled.</span></span>

<span data-ttu-id="d16ea-108">Это происходит потому, что параметр `-Version` является псевдонимом параметра `-MinimumVersion`.</span><span class="sxs-lookup"><span data-stu-id="d16ea-108">This occurs because the `-Version` parameter is an alias of the `-MinimumVersion` parameter.</span></span> <span data-ttu-id="d16ea-109">Когда модуль PackageManagement ищет подходящий пакет с минимальной версией 1.0, он возвращает последнюю версию.</span><span class="sxs-lookup"><span data-stu-id="d16ea-109">When PackageManagement is looking for a qualified package with the minimum version of 1.0, it returns the latest version.</span></span> <span data-ttu-id="d16ea-110">Такое поведение является нормальным в большинстве случаев, так как обычно требуется найти именно последнюю версию.</span><span class="sxs-lookup"><span data-stu-id="d16ea-110">This behavior is expected in normal cases because finding the latest version is usually the desired result.</span></span> <span data-ttu-id="d16ea-111">Но в случае с `Uninstall-Package` ситуация иная.</span><span class="sxs-lookup"><span data-stu-id="d16ea-111">However, it should not apply to the `Uninstall-Package` case.</span></span>

<span data-ttu-id="d16ea-112">**Решение**. Полностью удалить псевдоним `-Version` в PackageManagement (так называемом</span><span class="sxs-lookup"><span data-stu-id="d16ea-112">**Solution**:removed `-Version` alias entirely in PackageManagement (a.k.a.</span></span> <span data-ttu-id="d16ea-113">OneGet) и PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="d16ea-113">OneGet) and PowerShellGet.</span></span>

## <a name="multiple-prompts-for-bootstrapping-the-nuget-provider"></a><span data-ttu-id="d16ea-114">Несколько запросов на начальную загрузку поставщика NuGet</span><span class="sxs-lookup"><span data-stu-id="d16ea-114">Multiple prompts for bootstrapping the NuGet provider</span></span>

<span data-ttu-id="d16ea-115">**Ситуация**. При первом выполнении командлета `Find-Module`, `Install-Module` или других командлетов PackageManagement на компьютере модуль PackageManagement пытается выполнить начальную загрузку поставщика NuGet.</span><span class="sxs-lookup"><span data-stu-id="d16ea-115">**Scenario**: When you run `Find-Module` or `Install-Module` or other PackageManagement cmdlets on your computer for the first time, PackageManagement tries to bootstrap the NuGet provider.</span></span> <span data-ttu-id="d16ea-116">Связано это с тем, что поставщик PowershellGet также использует поставщик NuGet для скачивания модулей PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d16ea-116">It does this because the PowerShellGet provider also uses the NuGet provider to download PowerShell modules.</span></span>
<span data-ttu-id="d16ea-117">Затем модуль PackageManagement запрашивает у пользователя разрешение на установку поставщика NuGet.</span><span class="sxs-lookup"><span data-stu-id="d16ea-117">PackageManagement then prompts the user for permission to install the NuGet provider.</span></span> <span data-ttu-id="d16ea-118">После того как пользователь разрешает начальную загрузку, устанавливается последняя версия поставщика NuGet.</span><span class="sxs-lookup"><span data-stu-id="d16ea-118">After the user selects "yes" for the bootstrapping, the latest version of the NuGet provider will be installed.</span></span>

<span data-ttu-id="d16ea-119">Но если на компьютере установлена старая версия поставщика NuGet, она иногда может загружаться первой в сеанс PowerShell (и в PackageManagement возникает состояние гонки).</span><span class="sxs-lookup"><span data-stu-id="d16ea-119">However, in some cases, when you have an old version of NuGet provider installed on your computer, the older version of NuGet sometimes gets loaded first into the PowerShell session (that's the race condition in PackageManagement).</span></span> <span data-ttu-id="d16ea-120">Но модуль PowerShellGet требует, чтобы работала последняя версия поставщика NuGet, поэтому он еще раз запрашивает начальную загрузку поставщика NuGet у модуля PackageManagement.</span><span class="sxs-lookup"><span data-stu-id="d16ea-120">However PowerShellGet requires the later version of the NuGet provider to work, so PowerShellGet asks PackageManagement to bootstrap the NuGet provider again.</span></span>
<span data-ttu-id="d16ea-121">Это приводит к выводу нескольких запросов на начальную загрузку поставщика NuGet.</span><span class="sxs-lookup"><span data-stu-id="d16ea-121">This results in multiple prompts for bootstrapping the NuGet provider.</span></span>

<span data-ttu-id="d16ea-122">**Решение**. В WMF 5.1 модуль PackageManagement теперь загружает последнюю версию поставщика NuGet во избежание вывода нескольких запросов на начальную загрузку поставщика NuGet.</span><span class="sxs-lookup"><span data-stu-id="d16ea-122">**Solution**: In WMF5.1, PackageManagement loads the latest version of the NuGet provider to avoid multiple prompts for bootstrapping the NuGet provider.</span></span>

<span data-ttu-id="d16ea-123">Также имеется обходной путь: вы можете вручную удалить старую версию поставщика NuGet (NuGet-Anycpu.exe), если она существует, из папок $env:ProgramFiles\PackageManagement\ProviderAssemblies и $env:LOCALAPPDATA\PackageManagement\ProviderAssemblies</span><span class="sxs-lookup"><span data-stu-id="d16ea-123">You could also work around this issue by manually deleting the old version of the NuGet provider (NuGet-Anycpu.exe) if exists from $env:ProgramFiles\PackageManagement\ProviderAssemblies $env:LOCALAPPDATA\PackageManagement\ProviderAssemblies</span></span>

## <a name="support-for-packagemanagement-on-computers-with-intranet-access-only"></a><span data-ttu-id="d16ea-124">Поддержка PackageManagement на компьютерах с доступом только к интрасети</span><span class="sxs-lookup"><span data-stu-id="d16ea-124">Support for PackageManagement on computers with Intranet access only</span></span>

<span data-ttu-id="d16ea-125">**Ситуация**. В средах предприятий у пользователей может быть доступ только к интрасети, но не к Интернету.</span><span class="sxs-lookup"><span data-stu-id="d16ea-125">**Scenario**: For the enterprise scenario, people are working under an environment where there is no Internet access but Intranet only.</span></span> <span data-ttu-id="d16ea-126">Модуль PackageManagement не поддерживал такую ситуацию в WMF 5.0.</span><span class="sxs-lookup"><span data-stu-id="d16ea-126">PackageManagement did not support this case in WMF 5.0.</span></span>

<span data-ttu-id="d16ea-127">**Ситуация**. В WMF 5.0 модуль PackageManagement не поддерживался на компьютерах с доступом только к интрасети (но не к Интернету).</span><span class="sxs-lookup"><span data-stu-id="d16ea-127">**Scenario**: In WMF 5.0, PackageManagement did not support computers that have only Intranet (but not Internet) access.</span></span>

<span data-ttu-id="d16ea-128">**Решение**. Чтобы обеспечить использование PackageManagement на компьютерах в интрасети, в WMF 5.1 можно выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d16ea-128">**Solution**: In WMF 5.1, you can follow these steps to allow Intranet computers to use PackageManagement:</span></span>

1. <span data-ttu-id="d16ea-129">Скачайте поставщик NuGet с другого компьютера, имеющего подключение к Интернету, выполнив команду `Install-PackageProvider -Name NuGet`.</span><span class="sxs-lookup"><span data-stu-id="d16ea-129">Download the NuGet provider using another computer that has an Internet connection by using `Install-PackageProvider -Name NuGet`.</span></span>

2. <span data-ttu-id="d16ea-130">Поставщик NuGet находится в `$env:ProgramFiles\PackageManagement\ProviderAssemblies\nuget` или `$env:LOCALAPPDATA\PackageManagement\ProviderAssemblies\nuget`.</span><span class="sxs-lookup"><span data-stu-id="d16ea-130">Find the NuGet provider under either `$env:ProgramFiles\PackageManagement\ProviderAssemblies\nuget` or `$env:LOCALAPPDATA\PackageManagement\ProviderAssemblies\nuget`.</span></span>

3. <span data-ttu-id="d16ea-131">Скопируйте двоичные файлы в папку или сетевую папку, к которой есть доступ у компьютера в интрасети, и установите поставщик NuGet, выполнив команду `Install-PackageProvider -Name NuGet -Source <Path to folder>`.</span><span class="sxs-lookup"><span data-stu-id="d16ea-131">Copy the binaries to a folder or network share location that the Intranet computer can access, and then install the NuGet provider with `Install-PackageProvider -Name NuGet -Source <Path to folder>`.</span></span>


## <a name="event-logging-improvements"></a><span data-ttu-id="d16ea-132">Усовершенствования, касающиеся ведения журнала событий</span><span class="sxs-lookup"><span data-stu-id="d16ea-132">Event logging improvements</span></span>

<span data-ttu-id="d16ea-133">При установке пакетов состояние компьютера меняется.</span><span class="sxs-lookup"><span data-stu-id="d16ea-133">When you install packages, you are changing the state of the computer.</span></span> <span data-ttu-id="d16ea-134">В WMF 5.1 модуль PackageManagement записывает события в журнал событий Windows для действий `Install-Package`, `Uninstall-Package` и `Save-Package`.</span><span class="sxs-lookup"><span data-stu-id="d16ea-134">In WMF 5.1, PackageManagement now logs events to the Windows event log for `Install-Package`, `Uninstall-Package`, and `Save-Package` activities.</span></span> <span data-ttu-id="d16ea-135">Журнал событий совпадает с журналом событий для PowerShell, т. е. `Microsoft-Windows-PowerShell, Operational`.</span><span class="sxs-lookup"><span data-stu-id="d16ea-135">The Event log is the same as for PowerShell, that is, `Microsoft-Windows-PowerShell, Operational`.</span></span>

## <a name="support-for-basic-authentication"></a><span data-ttu-id="d16ea-136">Поддержка обычной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="d16ea-136">Support for basic authentication</span></span>

<span data-ttu-id="d16ea-137">В WMF 5.1 модуль PackageManagement поддерживает поиск и установку пакетов из репозитория, требующего обычной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="d16ea-137">In WMF 5.1, PackageManagement supports finding and installing packages from a repository that requires basic authentication.</span></span> <span data-ttu-id="d16ea-138">Можно указать учетные данные в командлетах `Find-Package` и `Install-Package`.</span><span class="sxs-lookup"><span data-stu-id="d16ea-138">You can supply your credentials to the `Find-Package` and `Install-Package` cmdlets.</span></span> <span data-ttu-id="d16ea-139">Например:</span><span class="sxs-lookup"><span data-stu-id="d16ea-139">For example:</span></span>

```powershell
Find-Package -Source <SourceWithCredential> -Credential (Get-Credential)
```

## <a name="support-for-using-packagemanagement-behind-a-proxy"></a><span data-ttu-id="d16ea-140">Поддержка использования PackageManagement через прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="d16ea-140">Support for using PackageManagement behind a proxy</span></span>

<span data-ttu-id="d16ea-141">В WMF 5.1 модуль PackageManagement принимает новые параметры прокси-сервера, `-ProxyCredential` и `-Proxy`.</span><span class="sxs-lookup"><span data-stu-id="d16ea-141">In WMF 5.1, PackageManagement now takes new proxy parameters `-ProxyCredential` and `-Proxy`.</span></span> <span data-ttu-id="d16ea-142">В этих параметрах можно указать URL-адрес и учетные данные прокси-сервера для командлетов PackageManagement.</span><span class="sxs-lookup"><span data-stu-id="d16ea-142">Using these parameters, you can specify the proxy URL and credentials to PackageManagement cmdlets.</span></span> <span data-ttu-id="d16ea-143">По умолчанию используются системные настройки прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="d16ea-143">By default, system proxy settings are used.</span></span> <span data-ttu-id="d16ea-144">Например:</span><span class="sxs-lookup"><span data-stu-id="d16ea-144">For example:</span></span>

```powershell
Find-Package -Source http://www.nuget.org/api/v2/ -Proxy http://www.myproxyserver.com -ProxyCredential (Get-Credential)
```
