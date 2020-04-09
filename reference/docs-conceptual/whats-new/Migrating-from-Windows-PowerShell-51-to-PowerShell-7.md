---
title: Миграция с Windows PowerShell 5.1 на PowerShell 7
description: Обновите PowerShell 5.1 до PowerShell 7 для платформ Windows.
ms.date: 03/25/2020
ms.openlocfilehash: e3881b1758f50119444969ad39541aec694cebe5
ms.sourcegitcommit: 30ccbbb32915b551c4cd4c91ef1df96b5b7514c4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2020
ms.locfileid: "80500503"
---
# <a name="migrating-from-windows-powershell-51-to-powershell-7"></a><span data-ttu-id="56472-103">Миграция с Windows PowerShell 5.1 на PowerShell 7</span><span class="sxs-lookup"><span data-stu-id="56472-103">Migrating from Windows PowerShell 5.1 to PowerShell 7</span></span>

<span data-ttu-id="56472-104">Средство PowerShell 7, предназначенное для облачных, локальных и гибридных сред, теперь значительно усовершенствовано и предоставляет [новые возможности](What-s-New-in-PowerShell-70.md):</span><span class="sxs-lookup"><span data-stu-id="56472-104">Designed for cloud, on-premises, and hybrid environments, PowerShell 7 is packed with enhancements and [new features](What-s-New-in-PowerShell-70.md).</span></span>

- <span data-ttu-id="56472-105">установка и работа параллельно с Windows PowerShell;</span><span class="sxs-lookup"><span data-stu-id="56472-105">Installs and runs side-by-side with Windows PowerShell</span></span>
- <span data-ttu-id="56472-106">увеличенная совместимость с существующими модулями Windows PowerShell;</span><span class="sxs-lookup"><span data-stu-id="56472-106">Improved compatibility with existing Windows PowerShell modules</span></span>
- <span data-ttu-id="56472-107">новые языковые возможности, такие как тернарные операторы и `ForEach-Object -Parallel`;</span><span class="sxs-lookup"><span data-stu-id="56472-107">New language features, like ternary operators and `ForEach-Object -Parallel`</span></span>
- <span data-ttu-id="56472-108">повышение производительности.</span><span class="sxs-lookup"><span data-stu-id="56472-108">Improved performance</span></span>
- <span data-ttu-id="56472-109">удаленное взаимодействие на основе протокола SSH;</span><span class="sxs-lookup"><span data-stu-id="56472-109">SSH-based remoting</span></span>
- <span data-ttu-id="56472-110">межплатформенное взаимодействие;</span><span class="sxs-lookup"><span data-stu-id="56472-110">Cross-platform interoperability</span></span>
- <span data-ttu-id="56472-111">Поддержка контейнеров Docker</span><span class="sxs-lookup"><span data-stu-id="56472-111">Support for Docker containers</span></span>

<span data-ttu-id="56472-112">PowerShell 7 работает параллельно с Windows PowerShell, позволяя легко тестировать и сравнивать код в разных выпусках перед развертыванием.</span><span class="sxs-lookup"><span data-stu-id="56472-112">PowerShell 7 works side-by-side with Windows PowerShell letting you easily test and compare between editions before deployment.</span></span> <span data-ttu-id="56472-113">Миграция — это простой, быстрый и</span><span class="sxs-lookup"><span data-stu-id="56472-113">Migration is simple, quick, and safe.</span></span> <span data-ttu-id="56472-114">надежный процесс.</span><span class="sxs-lookup"><span data-stu-id="56472-114">failure.</span></span>

<span data-ttu-id="56472-115">PowerShell 7 поддерживается в следующих операционных системах Windows:</span><span class="sxs-lookup"><span data-stu-id="56472-115">PowerShell 7 is supported on the following Windows operating systems:</span></span>

- <span data-ttu-id="56472-116">Windows 8.1 и 10;</span><span class="sxs-lookup"><span data-stu-id="56472-116">Windows 8.1 and 10</span></span>
- <span data-ttu-id="56472-117">Windows Server 2012, 2012 R2, 2016 и 2019</span><span class="sxs-lookup"><span data-stu-id="56472-117">Windows Server 2012, 2012 R2, 2016, and 2019</span></span>

<span data-ttu-id="56472-118">PowerShell 7 также работает в macOS и нескольких дистрибутивах Linux.</span><span class="sxs-lookup"><span data-stu-id="56472-118">PowerShell 7 also runs on macOS and several Linux distributions.</span></span> <span data-ttu-id="56472-119">Список поддерживаемых операционных систем и сведения о жизненном цикле поддержки см. в [этой статье](/powershell/scripting/powershell-support-lifecycle).</span><span class="sxs-lookup"><span data-stu-id="56472-119">For a list of supported operating systems and information about the support lifecycle, see the [PowerShell Support Lifecycle](/powershell/scripting/powershell-support-lifecycle).</span></span>

## <a name="installing-powershell-7"></a><span data-ttu-id="56472-120">Установка PowerShell 7</span><span class="sxs-lookup"><span data-stu-id="56472-120">Installing PowerShell 7</span></span>

<span data-ttu-id="56472-121">Для обеспечения гибких возможностей и в связи с требованиями ИТ-специалистов, инженеров DevOps, а также разработчиков доступно несколько вариантов установки PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="56472-121">For flexibility and to support the needs of IT, DevOps engineers, and developers, there are several options available to install PowerShell 7.</span></span> <span data-ttu-id="56472-122">В большинстве случаев варианты установки можно сократить до следующих методов:</span><span class="sxs-lookup"><span data-stu-id="56472-122">In most cases, the installation options can be reduced to the following methods:</span></span>

- <span data-ttu-id="56472-123">развертывание PowerShell с помощью [MSI-пакета](/powershell/scripting/install/installing-powershell-core-on-windows#installing-the-msi-package);</span><span class="sxs-lookup"><span data-stu-id="56472-123">Deploy PowerShell using the [MSI package](/powershell/scripting/install/installing-powershell-core-on-windows#installing-the-msi-package)</span></span>
- <span data-ttu-id="56472-124">развертывание PowerShell с помощью [ZIP-пакета](/powershell/scripting/install/installing-powershell-core-on-windows#installing-the-zip-package).</span><span class="sxs-lookup"><span data-stu-id="56472-124">Deploy PowerShell using the [ZIP package](/powershell/scripting/install/installing-powershell-core-on-windows#installing-the-zip-package)</span></span>

> [!NOTE]
> <span data-ttu-id="56472-125">MSI-пакет можно развернуть и обновить с помощью таких продуктов для управления, как [System Center Configuration Manager (SCCM)](/configmgr/apps/).</span><span class="sxs-lookup"><span data-stu-id="56472-125">The MSI package can be deployed and updated with management products such as [System Center Configuration Manager (SCCM)](/configmgr/apps/).</span></span> <span data-ttu-id="56472-126">Скачайте пакеты на [странице выпусков GitHub](https://github.com/PowerShell/PowerShell/releases).</span><span class="sxs-lookup"><span data-stu-id="56472-126">Download the packages from [GitHub Release page](https://github.com/PowerShell/PowerShell/releases).</span></span>

<span data-ttu-id="56472-127">Для развертывания MSI-пакета требуются привилегии администратора.</span><span class="sxs-lookup"><span data-stu-id="56472-127">Deploying the MSI package requires Administrator permission.</span></span> <span data-ttu-id="56472-128">ZIP-пакет может развернуть любой пользователь.</span><span class="sxs-lookup"><span data-stu-id="56472-128">The ZIP package can be deployed by any user.</span></span> <span data-ttu-id="56472-129">Установка с помощью ZIP-пакета — это самый простой способ установить PowerShell 7 для тестирования перед полной установкой.</span><span class="sxs-lookup"><span data-stu-id="56472-129">The ZIP package is the easiest way to install PowerShell 7 for testing, before committing to a full installation.</span></span>

## <a name="using-powershell-7-side-by-side-with-windows-powershell-51"></a><span data-ttu-id="56472-130">Параллельное использование Windows PowerShell 7 с Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="56472-130">Using PowerShell 7 side-by-side with Windows PowerShell 5.1</span></span>

<span data-ttu-id="56472-131">В средстве PowerShell 7 предусмотрена возможность сосуществовать с Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="56472-131">PowerShell 7 is designed to coexist with Windows PowerShell 5.1.</span></span> <span data-ttu-id="56472-132">Следующие свойства гарантируют защиту инвестиций в PowerShell и простоту миграции в PowerShell 7:</span><span class="sxs-lookup"><span data-stu-id="56472-132">The following features ensure that your investment in PowerShell is protected and your migration to PowerShell 7 is simple.</span></span>

- <span data-ttu-id="56472-133">отдельный путь установки и исполняемый файл;</span><span class="sxs-lookup"><span data-stu-id="56472-133">Separate installation path and executable name</span></span>
- <span data-ttu-id="56472-134">отдельная переменная PSModulePath;</span><span class="sxs-lookup"><span data-stu-id="56472-134">Separate PSModulePath</span></span>
- <span data-ttu-id="56472-135">отдельный профиль для каждой версии;</span><span class="sxs-lookup"><span data-stu-id="56472-135">Separate profiles for each version</span></span>
- <span data-ttu-id="56472-136">увеличенная совместимость модулей;</span><span class="sxs-lookup"><span data-stu-id="56472-136">Improved module compatibility</span></span>
- <span data-ttu-id="56472-137">новые конечные точки удаленного взаимодействия;</span><span class="sxs-lookup"><span data-stu-id="56472-137">New remoting endpoints</span></span>
- <span data-ttu-id="56472-138">поддержка групповой политики;</span><span class="sxs-lookup"><span data-stu-id="56472-138">Group policy support</span></span>
- <span data-ttu-id="56472-139">отдельные журналы событий;</span><span class="sxs-lookup"><span data-stu-id="56472-139">Separate Event logs</span></span>

### <a name="separate-installation-path-and-executable-name"></a><span data-ttu-id="56472-140">Отдельный путь установки и исполняемый файл</span><span class="sxs-lookup"><span data-stu-id="56472-140">Separate installation path and executable name</span></span>

<span data-ttu-id="56472-141">PowerShell 7 устанавливается в новом каталоге и работает параллельно с Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="56472-141">PowerShell 7 installs to a new directory, enabling side-by-side execution with Windows PowerShell 5.1.</span></span>

<span data-ttu-id="56472-142">Расположения установки по версии:</span><span class="sxs-lookup"><span data-stu-id="56472-142">Install locations by version:</span></span>

- <span data-ttu-id="56472-143">Windows PowerShell 5.1: `$env:WINDIR\System32\WindowsPowerShell\v1.0`.</span><span class="sxs-lookup"><span data-stu-id="56472-143">Windows PowerShell 5.1: `$env:WINDIR\System32\WindowsPowerShell\v1.0`</span></span>
- <span data-ttu-id="56472-144">PowerShell Core 6.x: `$env:ProgramFiles\PowerShell\6`.</span><span class="sxs-lookup"><span data-stu-id="56472-144">PowerShell Core 6.x: `$env:ProgramFiles\PowerShell\6`</span></span>
- <span data-ttu-id="56472-145">PowerShell 7: `$env:ProgramFiles\PowerShell\7`.</span><span class="sxs-lookup"><span data-stu-id="56472-145">PowerShell 7: `$env:ProgramFiles\PowerShell\7`</span></span>

<span data-ttu-id="56472-146">Новое расположение добавляется в переменную PATH, что позволяет запускать параллельно Windows PowerShell 5.1 и PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="56472-146">The new location is added to your PATH allowing you to run both Windows PowerShell 5.1 and PowerShell 7.</span></span> <span data-ttu-id="56472-147">Если выполняется миграция с PowerShell Core 6.x в PowerShell 7, то PowerShell 6 удаляется и переменная PATH заменяется.</span><span class="sxs-lookup"><span data-stu-id="56472-147">If you're migrating from PowerShell Core 6.x to PowerShell 7, PowerShell 6 is removed and the PATH replaced.</span></span>

<span data-ttu-id="56472-148">В Windows PowerShell исполняемый файл PowerShell называется `powershell.exe`.</span><span class="sxs-lookup"><span data-stu-id="56472-148">In Windows PowerShell, the PowerShell executable is named `powershell.exe`.</span></span> <span data-ttu-id="56472-149">В версии 6 и более поздних версиях исполняемый файл называется `pwsh.exe`.</span><span class="sxs-lookup"><span data-stu-id="56472-149">In version 6 and above, the executable is named `pwsh.exe`.</span></span> <span data-ttu-id="56472-150">Новое имя позволяет легко поддерживать параллельную работу обеих версий.</span><span class="sxs-lookup"><span data-stu-id="56472-150">The new name makes it easy to support side-by-side execution of both versions.</span></span>

### <a name="separate-psmodulepath"></a><span data-ttu-id="56472-151">Отдельная переменная PSModulePath</span><span class="sxs-lookup"><span data-stu-id="56472-151">Separate PSModulePath</span></span>

<span data-ttu-id="56472-152">По умолчанию Windows PowerShell и PowerShell 7 сохраняют модули в разных расположениях.</span><span class="sxs-lookup"><span data-stu-id="56472-152">By default, Windows PowerShell and PowerShell 7 store modules in different locations.</span></span> <span data-ttu-id="56472-153">В PowerShell 7 эти расположения объединены в переменную среды `$Env:PSModulePath`.</span><span class="sxs-lookup"><span data-stu-id="56472-153">PowerShell 7 combines those locations in the `$Env:PSModulePath` environment variable.</span></span> <span data-ttu-id="56472-154">При импорте модуля по имени PowerShell проверяет расположение, указанное с помощью `$Env:PSModulePath`.</span><span class="sxs-lookup"><span data-stu-id="56472-154">When importing a module by name, PowerShell checks the location specified by `$Env:PSModulePath`.</span></span> <span data-ttu-id="56472-155">Это позволяет PowerShell 7 загружать как базовые модули (Core), так и предназначенные для компьютеров.</span><span class="sxs-lookup"><span data-stu-id="56472-155">This allows PowerShell 7 to load both Core and Desktop modules.</span></span>

|            <span data-ttu-id="56472-156">Область установки</span><span class="sxs-lookup"><span data-stu-id="56472-156">Install Scope</span></span>            |                <span data-ttu-id="56472-157">Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="56472-157">Windows PowerShell 5.1</span></span>                 |             <span data-ttu-id="56472-158">PowerShell 7.0</span><span class="sxs-lookup"><span data-stu-id="56472-158">PowerShell 7.0</span></span>             |
| ----------------------------------- | ----------------------------------------------------- | -------------------------------------- |
| <span data-ttu-id="56472-159">Модули PowerShell</span><span class="sxs-lookup"><span data-stu-id="56472-159">PowerShell modules</span></span>                  | `$env:WINDIR\system32\WindowsPowerShell\v1.0\Modules` | `$PSHOME\Modules`                      |
| <span data-ttu-id="56472-160">Установленная пользователем</span><span class="sxs-lookup"><span data-stu-id="56472-160">User installed</span></span><br><span data-ttu-id="56472-161">область AllUsers</span><span class="sxs-lookup"><span data-stu-id="56472-161">AllUsers scope</span></span>    | `$env:ProgramFiles\WindowsPowerShell\Modules`         | `$env:ProgramFiles\PowerShell\Modules` |
| <span data-ttu-id="56472-162">Установленная пользователем</span><span class="sxs-lookup"><span data-stu-id="56472-162">User installed</span></span><br><span data-ttu-id="56472-163">область CurrentUser</span><span class="sxs-lookup"><span data-stu-id="56472-163">CurrentUser scope</span></span> | `$HOME\Documents\WindowsPowerShell\Modules`           | `$HOME\Documents\PowerShell\Modules`   |

<span data-ttu-id="56472-164">В следующих примерах показаны значения `$Env:PSModulePath` по умолчанию для каждой версии.</span><span class="sxs-lookup"><span data-stu-id="56472-164">The following examples show the default values of `$Env:PSModulePath` for each version.</span></span>

- <span data-ttu-id="56472-165">Для Windows PowerShell 5.1:</span><span class="sxs-lookup"><span data-stu-id="56472-165">For Windows PowerShell 5.1:</span></span>

  ```powershell
  $Env:PSModulePath -split (';')
  ```

  ```Output
  C:\Users\<user>\Documents\WindowsPowerShell\Modules
  C:\Program Files\WindowsPowerShell\Modules
  C:\WINDOWS\System32\WindowsPowerShell\v1.0\Modules
  ```

- <span data-ttu-id="56472-166">Для PowerShell 7:</span><span class="sxs-lookup"><span data-stu-id="56472-166">For PowerShell 7:</span></span>

  ```powershell
  $Env:PSModulePath -split (';')
  ```

  ```Output
  C:\Users\<user>\Documents\PowerShell\Modules
  C:\Program Files\PowerShell\Modules
  C:\Program Files\PowerShell\7\Modules
  C:\Program Files\WindowsPowerShell\Modules
  C:\WINDOWS\System32\WindowsPowerShell\v1.0\Modules
  ```

<span data-ttu-id="56472-167">Обратите внимание, что PowerShell 7 включает пути Windows PowerShell и PowerShell 7 для обеспечения автоматической загрузки модулей.</span><span class="sxs-lookup"><span data-stu-id="56472-167">Notice that PowerShell 7 includes the Windows PowerShell paths and the PowerShell 7 paths to provide autoloading of modules.</span></span>

> [!NOTE]
> <span data-ttu-id="56472-168">Могут существовать дополнительные пути, если вы изменили переменную среды PSModulePath или установили пользовательские модули или приложения.</span><span class="sxs-lookup"><span data-stu-id="56472-168">Additional paths may exist if you have changed the PSModulePath environment variable or installed custom modules or applications.</span></span>

<span data-ttu-id="56472-169">Дополнительные сведения о `PSModulePath` см. в разделе о [переменных среды](/powershell/module/microsoft.powershell.core/about/about_environment_variables#environment-variables-that-store-preferences).</span><span class="sxs-lookup"><span data-stu-id="56472-169">For more information, see `PSModulePath` in [about_Environment_Variables](/powershell/module/microsoft.powershell.core/about/about_environment_variables#environment-variables-that-store-preferences).</span></span>

<span data-ttu-id="56472-170">Дополнительные сведения о модулях см. в [этой статье](/powershell/module/Microsoft.PowerShell.Core/About/about_Modules).</span><span class="sxs-lookup"><span data-stu-id="56472-170">For more information about Modules, see [about_Modules](/powershell/module/Microsoft.PowerShell.Core/About/about_Modules).</span></span>

### <a name="separate-profiles"></a><span data-ttu-id="56472-171">Отдельные профили</span><span class="sxs-lookup"><span data-stu-id="56472-171">Separate profiles</span></span>

<span data-ttu-id="56472-172">Профиль PowerShell — это скрипт, который выполняется при запуске PowerShell.</span><span class="sxs-lookup"><span data-stu-id="56472-172">A PowerShell profile is a script that executes when PowerShell starts.</span></span> <span data-ttu-id="56472-173">Этот скрипт настраивает среду, добавляя команды, псевдонимы, функции, переменные, модули и диски PowerShell.</span><span class="sxs-lookup"><span data-stu-id="56472-173">This script customizes your environment by adding commands, aliases, functions, variables, modules, and PowerShell drives.</span></span> <span data-ttu-id="56472-174">Скрипт профиля обеспечивает доступность этих настроек в каждом сеансе и отсутствие необходимости их повторного создания вручную.</span><span class="sxs-lookup"><span data-stu-id="56472-174">The profile script makes these customizations available in every session without having to manually recreate them.</span></span>

<span data-ttu-id="56472-175">Путь к расположению профиля в PowerShell 7 изменился.</span><span class="sxs-lookup"><span data-stu-id="56472-175">The path to the location of the profile has changed in PowerShell 7.</span></span>

- <span data-ttu-id="56472-176">В Windows PowerShell 5.1 расположение профиля — `$HOME\Documents\WindowsPowerShell`.</span><span class="sxs-lookup"><span data-stu-id="56472-176">In Windows PowerShell 5.1, the location of the profile is `$HOME\Documents\WindowsPowerShell`.</span></span>
- <span data-ttu-id="56472-177">В PowerShell 7 расположение профиля — `$HOME\Documents\PowerShell`.</span><span class="sxs-lookup"><span data-stu-id="56472-177">In PowerShell 7, the location of the profile is `$HOME\Documents\PowerShell`.</span></span>

<span data-ttu-id="56472-178">Имена файлов профилей также изменились:</span><span class="sxs-lookup"><span data-stu-id="56472-178">The profile filenames have also changed:</span></span>

   ```powershell
   PS> $PROFILE | Select-Object *Host* | Format-List

   AllUsersAllHosts       : C:\Program Files\PowerShell\7\profile.ps1
   AllUsersCurrentHost    : C:\Program Files\PowerShell\7\Microsoft.PowerShell_profile.ps1
   CurrentUserAllHosts    : C:\Users\<user>\Documents\PowerShell\profile.ps1
   CurrentUserCurrentHost : C:\Users\<user>\Documents\PowerShell\Microsoft.PowerShell_profile.ps1
   ```

<span data-ttu-id="56472-179">Дополнительные сведения о профилях см. в [этой статье](/powershell/module/microsoft.powershell.core/about/about_profiles).</span><span class="sxs-lookup"><span data-stu-id="56472-179">For more information [about_Profiles](/powershell/module/microsoft.powershell.core/about/about_profiles).</span></span>

### <a name="powershell-7-compatibility-with-windows-powershell-51-modules"></a><span data-ttu-id="56472-180">Совместимость PowerShell 7 с модулями Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="56472-180">PowerShell 7 compatibility with Windows PowerShell 5.1 modules</span></span>

<span data-ttu-id="56472-181">Большинство модулей, используемых в Windows PowerShell 5.1, уже работают с PowerShell 7, в том числе Azure PowerShell и Active Directory.</span><span class="sxs-lookup"><span data-stu-id="56472-181">Most of the modules you use in Windows PowerShell 5.1 already work with PowerShell 7, including Azure PowerShell and Active Directory.</span></span> <span data-ttu-id="56472-182">Мы продолжаем работать с другими командами над добавлением встроенной поддержки в PowerShell 7 большего числа модулей, в том числе Microsoft Graph, Office 365 и др.</span><span class="sxs-lookup"><span data-stu-id="56472-182">We're continuing to work with other teams to add native PowerShell 7 support for more modules including Microsoft Graph, Office 365, and others.</span></span> <span data-ttu-id="56472-183">Текущий список поддерживаемых модулей см. в статье [Совместимость модулей PowerShell 7](/powershell/scripting/whats-new/module-compatibility).</span><span class="sxs-lookup"><span data-stu-id="56472-183">For the current list of supported modules, see [PowerShell 7 module compatibility](/powershell/scripting/whats-new/module-compatibility).</span></span>

> [!NOTE]
> <span data-ttu-id="56472-184">В Windows мы также добавили переключатель **UseWindowsPowerShell** в `Import-Module`, чтобы упростить переход на PowerShell 7 для тех, кто использует несовместимые модули.</span><span class="sxs-lookup"><span data-stu-id="56472-184">On Windows, we've also added a **UseWindowsPowerShell** switch to `Import-Module` to ease the transition to PowerShell 7 for those using incompatible modules.</span></span> <span data-ttu-id="56472-185">Дополнительные сведения об этих функциональных возможностях см. в статье [О совместимости Windows PowerShell](/powershell/module/Microsoft.PowerShell.Core/About/about_windows_powershell_compatibility).</span><span class="sxs-lookup"><span data-stu-id="56472-185">For more information on this functionality, see [about_Windows_PowerShell_Compatibility](/powershell/module/Microsoft.PowerShell.Core/About/about_windows_powershell_compatibility).</span></span>

### <a name="powershell-remoting"></a><span data-ttu-id="56472-186">Удаленное взаимодействие PowerShell</span><span class="sxs-lookup"><span data-stu-id="56472-186">PowerShell Remoting</span></span>

<span data-ttu-id="56472-187">Удаленное взаимодействие PowerShell позволяет выполнять любую команду PowerShell на одном или нескольких удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="56472-187">PowerShell remoting lets you run any PowerShell command on one or more remote computers.</span></span> <span data-ttu-id="56472-188">Вы можете устанавливать постоянные подключения, запускать интерактивные сеансы и выполнять скрипты на удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="56472-188">You can establish persistent connections, start interactive sessions, and run scripts on remote computers.</span></span>

#### <a name="ws-management-remoting"></a><span data-ttu-id="56472-189">Удаленное взаимодействие с использованием WS-Management</span><span class="sxs-lookup"><span data-stu-id="56472-189">WS-Management remoting</span></span>

<span data-ttu-id="56472-190">В Windows PowerShell 5.1 и более ранних версий используйте протокол WS-Management для согласования подключения и передачи данных.</span><span class="sxs-lookup"><span data-stu-id="56472-190">Windows PowerShell 5.1 and below use the WS-Management (WSMAN) protocol for connection negotiation and data transport.</span></span> <span data-ttu-id="56472-191">Служба удаленного управления Windows (WinRM) использует протокол WS-Management.</span><span class="sxs-lookup"><span data-stu-id="56472-191">Windows Remote Management (WinRM) uses the WSMAN protocol.</span></span> <span data-ttu-id="56472-192">Если служба WinRM включена, PowerShell 7 использует существующую конечную точку Windows PowerShell 5.1 с именем `Microsoft.PowerShell` для удаленных подключений.</span><span class="sxs-lookup"><span data-stu-id="56472-192">If WinRM has been enabled, PowerShell 7 uses the existing Windows PowerShell 5.1 endpoint named `Microsoft.PowerShell` for remoting connections.</span></span> <span data-ttu-id="56472-193">Чтобы обновить PowerShell 7 для включения собственной конечной точки, выполните командлет `Enable-PSRemoting`.</span><span class="sxs-lookup"><span data-stu-id="56472-193">To update PowerShell 7 to include its own endpoint, run the `Enable-PSRemoting` cmdlet.</span></span> <span data-ttu-id="56472-194">Сведения о подключении к конкретным конечным точкам см. в статье [Удаленное взаимодействие с WS-Management (WSMan) в PowerShell Core](/powershell/scripting/learn/remoting/wsman-remoting-in-powershell-core).</span><span class="sxs-lookup"><span data-stu-id="56472-194">For information about connecting to specific endpoints, see [WS-Management Remoting in PowerShell Core](/powershell/scripting/learn/remoting/wsman-remoting-in-powershell-core)</span></span>

<span data-ttu-id="56472-195">Чтобы использовать службу удаленного взаимодействия Windows PowerShell, удаленный компьютер должен быть настроен для удаленного управления.</span><span class="sxs-lookup"><span data-stu-id="56472-195">To use Windows PowerShell remoting, the remote computer must be configured for remote management.</span></span>
<span data-ttu-id="56472-196">Дополнительные сведения, в том числе инструкции, см. в разделе [about_Remote_Requirements](/powershell/module/microsoft.powershell.core/about/about_remote_requirements).</span><span class="sxs-lookup"><span data-stu-id="56472-196">For more information, including instructions, see [About Remote Requirements](/powershell/module/microsoft.powershell.core/about/about_remote_requirements).</span></span>

<span data-ttu-id="56472-197">Дополнительные сведения о работе с удаленным взаимодействием см. в статье [Об удаленном взаимодействии](/powershell/module/microsoft.powershell.core/about/about_remote).</span><span class="sxs-lookup"><span data-stu-id="56472-197">For more information about working with remoting, see [About Remote](/powershell/module/microsoft.powershell.core/about/about_remote)</span></span>

#### <a name="ssh-based-remoting"></a><span data-ttu-id="56472-198">Удаленное взаимодействие на основе протокола SSH</span><span class="sxs-lookup"><span data-stu-id="56472-198">SSH-based remoting</span></span>

<span data-ttu-id="56472-199">Удаленное взаимодействие с использованием протокола SSH добавлено в PowerShell Core 6.x для поддержки в других операционных системах, которые не могут использовать собственные компоненты Windows, такие как **WinRM**.</span><span class="sxs-lookup"><span data-stu-id="56472-199">SSH-based remoting was added in PowerShell Core 6.x to support other operating systems that can't use Windows native components like **WinRM**.</span></span> <span data-ttu-id="56472-200">Функция удаленного взаимодействия по SSH создает хост-процесс PowerShell на целевом компьютере в качестве подсистемы SSH.</span><span class="sxs-lookup"><span data-stu-id="56472-200">SSH remoting creates a PowerShell host process on the target computer as an SSH subsystem.</span></span> <span data-ttu-id="56472-201">Дополнительные сведения и примеры настройки удаленного взаимодействия на основе протокола SSH в Windows или Linux см. в статье [Удаленное взаимодействие PowerShell через SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span><span class="sxs-lookup"><span data-stu-id="56472-201">For details and examples on setting up SSH-based remoting on Windows or Linux, see: [PowerShell remoting over SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span></span>

> [!NOTE]
> <span data-ttu-id="56472-202">Коллекция PowerShell (PSGallery) содержит модуль и командлет, который автоматически настраивает удаленное взаимодействие с использованием протокола SSH.</span><span class="sxs-lookup"><span data-stu-id="56472-202">The PowerShell Gallery (PSGallery) contains a module and cmdlet that automatically configures SSH-based remoting.</span></span> <span data-ttu-id="56472-203">Установите модуль `Microsoft.PowerShell.RemotingTools` из [PSGallery](https://www.powershellgallery.com/packages/Microsoft.PowerShell.RemotingTools/0.1.0) и выполните командлет `Enable-SSH`.</span><span class="sxs-lookup"><span data-stu-id="56472-203">Install the `Microsoft.PowerShell.RemotingTools` module from the [PSGallery](https://www.powershellgallery.com/packages/Microsoft.PowerShell.RemotingTools/0.1.0) and run the `Enable-SSH` cmdlet.</span></span>

<span data-ttu-id="56472-204">Командлеты `New-PSSession`, `Enter-PSSession` и `Invoke-Command` имеют новые наборы параметров для поддержки подключений SSH.</span><span class="sxs-lookup"><span data-stu-id="56472-204">The `New-PSSession`, `Enter-PSSession`, and `Invoke-Command` cmdlets have new parameter sets to support SSH connections.</span></span>

```powershell
[-HostName <string>]  [-UserName <string>]  [-KeyFilePath <string>]
```

<span data-ttu-id="56472-205">Чтобы создать удаленный сеанс, укажите целевой компьютер с помощью параметра **HostName** и имя пользователя с помощью параметра **UserName**.</span><span class="sxs-lookup"><span data-stu-id="56472-205">To create a remote session, specify the target computer with the **HostName** parameter and provide the user name with **UserName**.</span></span> <span data-ttu-id="56472-206">При интерактивном выполнении командлетов отображается запрос на ввод пароля.</span><span class="sxs-lookup"><span data-stu-id="56472-206">When running the cmdlets interactively, you're prompted for a password.</span></span>

```powershell
Enter-PSSession -HostName <Computer> -UserName <Username>
```

<span data-ttu-id="56472-207">Кроме того, при использовании параметра **HostName** укажите имя пользователя, за которым должен следовать символ ('@'), а затем имя компьютера.</span><span class="sxs-lookup"><span data-stu-id="56472-207">Alternatively, when using the **HostName** parameter, provide the username information followed by the at sign ('@'), followed by the computer name.</span></span>

```powershell
Enter-PSSession -HostName <Username>@<Computer>
```

<span data-ttu-id="56472-208">Проверку подлинности ключа SSH можно настроить, используя файл закрытого ключа в параметре **KeyFilePath**.</span><span class="sxs-lookup"><span data-stu-id="56472-208">You may set up SSH key authentication using a private key file with the **KeyFilePath** parameter.</span></span>
<span data-ttu-id="56472-209">Дополнительные сведения см. в статье [Управление ключами OpenSSH](/windows-server/administration/openssh/openssh_keymanagement).</span><span class="sxs-lookup"><span data-stu-id="56472-209">For more information, see [OpenSSH Key Management](/windows-server/administration/openssh/openssh_keymanagement).</span></span>

### <a name="group-policy-supported"></a><span data-ttu-id="56472-210">Поддержка групповой политики</span><span class="sxs-lookup"><span data-stu-id="56472-210">Group Policy supported</span></span>

<span data-ttu-id="56472-211">В PowerShell предусмотрены настройки групповой политики, позволяющие определить согласованные значения параметров для серверов в корпоративной среде.</span><span class="sxs-lookup"><span data-stu-id="56472-211">PowerShell includes Group Policy settings to help you define consistent option values for servers in an enterprise environment.</span></span> <span data-ttu-id="56472-212">К числу этих параметров относятся следующие:</span><span class="sxs-lookup"><span data-stu-id="56472-212">These settings include:</span></span>

- <span data-ttu-id="56472-213">Конфигурация сеанса консоли — задает конечную точку конфигурации, в которой выполняется PowerShell.</span><span class="sxs-lookup"><span data-stu-id="56472-213">Console session configuration: Sets a configuration endpoint in which PowerShell is run.</span></span>
- <span data-ttu-id="56472-214">"Включить ведение журнала модулей" — задает свойство LogPipelineExecutionDetails модулей.</span><span class="sxs-lookup"><span data-stu-id="56472-214">Turn on Module Logging: Sets the LogPipelineExecutionDetails property of modules.</span></span>
- <span data-ttu-id="56472-215">"Включить регистрацию блоков сценариев PowerShell" — включает подробное ведение журнала всех скриптов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="56472-215">Turn on PowerShell Script Block Logging: Enables detailed logging of all PowerShell scripts.</span></span>
- <span data-ttu-id="56472-216">"Включить выполнение сценариев" — задает политику выполнения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="56472-216">Turn on Script Execution: Sets the PowerShell execution policy.</span></span>
- <span data-ttu-id="56472-217">"Включить транскрипции PowerShell" — включает запись входных и выходных данных команд PowerShell в виде текстовых расшифровок</span><span class="sxs-lookup"><span data-stu-id="56472-217">Turn on PowerShell Transcription: enables capturing of input and output of PowerShell commands into text-based transcripts.</span></span>
- <span data-ttu-id="56472-218">"Задать исходный путь по умолчанию для Update-Help" — задает каталог (не в Интернете) в качестве источника для Updatable-Help (обновляемой справки).</span><span class="sxs-lookup"><span data-stu-id="56472-218">Set the default source path for Update-Help: Sets the source for Updatable Help to a directory, not the Internet.</span></span>

<span data-ttu-id="56472-219">Дополнительные сведения см. в статье [О параметрах групповой политики](/powershell/module/microsoft.powershell.core/about/about_group_policy_settings).</span><span class="sxs-lookup"><span data-stu-id="56472-219">For more information, see [about_Group_Policy_Settings](/powershell/module/microsoft.powershell.core/about/about_group_policy_settings).</span></span>

<span data-ttu-id="56472-220">В PowerShell 7 предусмотрены шаблоны групповой политики и скрипт установки в `$PSHOME`.</span><span class="sxs-lookup"><span data-stu-id="56472-220">PowerShell 7 includes Group Policy templates and an installation script in `$PSHOME`.</span></span>

<span data-ttu-id="56472-221">Инструменты групповой политики используют файлы административных шаблонов (с расширениями `.admx`, `.adml`) для заполнения параметров политики в пользовательском интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="56472-221">Group Policy tools use administrative template files (`.admx`, `.adml`) to populate policy settings in the user interface.</span></span> <span data-ttu-id="56472-222">Это позволяет администраторам управлять параметрами политики на основе реестра.</span><span class="sxs-lookup"><span data-stu-id="56472-222">This allows administrators to manage registry-based policy settings.</span></span> <span data-ttu-id="56472-223">Скрипт `InstallPSCorePolicyDefinitions.ps1` устанавливает административные шаблоны PowerShell Core на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="56472-223">The `InstallPSCorePolicyDefinitions.ps1` script installs PowerShell Core Administrative Templates on the local machine.</span></span>

```powershell
Get-ChildItem -Path $PSHOME -Filter *Core*Policy*
```

```Output
    Directory: C:\Program Files\PowerShell\7

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           2/27/2020 12:38 AM          15861 InstallPSCorePolicyDefinitions.ps1
-a---           2/27/2020 12:28 AM           9675 PowerShellCoreExecutionPolicy.adml
-a---           2/27/2020 12:28 AM           6201 PowerShellCoreExecutionPolicy.admx
```

### <a name="separate-event-logs"></a><span data-ttu-id="56472-224">Отдельные журналы событий</span><span class="sxs-lookup"><span data-stu-id="56472-224">Separate Event Logs</span></span>

<span data-ttu-id="56472-225">Windows PowerShell и PowerShell 7 регистрируют события в отдельных журналах событий.</span><span class="sxs-lookup"><span data-stu-id="56472-225">Windows PowerShell and PowerShell 7 log events to separate event logs.</span></span> <span data-ttu-id="56472-226">Используйте следующую команду, чтобы получить список журналов PowerShell:</span><span class="sxs-lookup"><span data-stu-id="56472-226">Use the following command to get a list of the PowerShell logs.</span></span>

```powershell
Get-WinEvent -ListLog *PowerShell*
```

<span data-ttu-id="56472-227">Дополнительные сведения см. в статье [О ведении журналов Windows](/powershell/module/microsoft.powershell.core/about/about_logging_windows).</span><span class="sxs-lookup"><span data-stu-id="56472-227">For more information, see [about_Logging_Windows](/powershell/module/microsoft.powershell.core/about/about_logging_windows).</span></span>

## <a name="improved-editing-experience-with-visual-studio-code"></a><span data-ttu-id="56472-228">Улучшенные возможности редактирования с помощью Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="56472-228">Improved editing experience with Visual Studio Code</span></span>

<span data-ttu-id="56472-229">[Visual Studio Code (VS Code)](https://code.visualstudio.com/) с [расширением PowerShell](https://code.visualstudio.com/docs/languages/powershell) — поддерживаемая среда написания скриптов для PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="56472-229">[Visual Studio Code (VSCode)](https://code.visualstudio.com/) with the [PowerShell Extension](https://code.visualstudio.com/docs/languages/powershell) is the supported scripting environment for PowerShell 7.</span></span> <span data-ttu-id="56472-230">Интегрированная среда сценариев (ISE) Windows PowerShell поддерживает только Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="56472-230">The Windows PowerShell Integrated Scripting Environment (ISE) only supports Windows PowerShell.</span></span>

<span data-ttu-id="56472-231">Обновленное расширение PowerShell включает в себя:</span><span class="sxs-lookup"><span data-stu-id="56472-231">The updated PowerShell extension includes:</span></span>

- <span data-ttu-id="56472-232">новый режим совместимости ISE;</span><span class="sxs-lookup"><span data-stu-id="56472-232">New ISE compatibility mode</span></span>
- <span data-ttu-id="56472-233">PSReadLine в интегрированной консоли, в том числе выделение синтаксиса, многострочное редактирование и обратный поиск;</span><span class="sxs-lookup"><span data-stu-id="56472-233">PSReadLine in the Integrated Console, including syntax highlighting, multi-line editing, and back search</span></span>
- <span data-ttu-id="56472-234">повышенную стабильность работы и производительность;</span><span class="sxs-lookup"><span data-stu-id="56472-234">Stability and performance improvements</span></span>
- <span data-ttu-id="56472-235">интеграцию с CodeLens;</span><span class="sxs-lookup"><span data-stu-id="56472-235">New CodeLens integration</span></span>
- <span data-ttu-id="56472-236">усовершенствованное автоматическое заполнение пути.</span><span class="sxs-lookup"><span data-stu-id="56472-236">Improved path auto-completion</span></span>

<span data-ttu-id="56472-237">Чтобы упростить переход на Visual Studio Code, используйте возможность **Enable ISE Mode** (Включить режим ISE), доступную в **палитре команд**.</span><span class="sxs-lookup"><span data-stu-id="56472-237">To make the transition to Visual Studio Code easier, use the **Enable ISE Mode** function available in the **Command Palette**.</span></span> <span data-ttu-id="56472-238">Эта функция переключает VS Code в режим макета в стиле ISE.</span><span class="sxs-lookup"><span data-stu-id="56472-238">This function switches VSCode into an ISE-style layout.</span></span> <span data-ttu-id="56472-239">Режим макета в стиле ISE предоставляет все новые функции и возможности PowerShell в знакомом пользовательском интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="56472-239">The ISE-style layout gives you all the new features and capabilities of PowerShell in a familiar user experience.</span></span>

<span data-ttu-id="56472-240">Чтобы переключиться на новый макет ISE, нажмите клавиши <kbd>CTRL</kbd>+<kbd>SHIFT</kbd>+<kbd>P</kbd>, чтобы открыть **палитру команд**, введите `PowerShell` и выберите **PowerShell: Enable ISE Mode** (PowerShell: включить режим ISE).</span><span class="sxs-lookup"><span data-stu-id="56472-240">To switch to the new ISE layout, press <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> to open the **Command Palette**, type `PowerShell` and select **PowerShell: Enable ISE Mode**.</span></span>

<span data-ttu-id="56472-241">Чтобы задать исходный макет, откройте **палитру команд** и выберите **PowerShell: Disable ISE Mode (restore to defaults)** (PowerShell: выключить режим ISE (восстановить значения по умолчанию)).</span><span class="sxs-lookup"><span data-stu-id="56472-241">To set the layout to the original layout, open the **Command Palette**, select **PowerShell: Disable ISE Mode (restore to defaults)**.</span></span>

<span data-ttu-id="56472-242">Дополнительные сведения о настройке макета VS Code для ISE см. в статье [Репликация функций интегрированной среды скриптов в Visual Studio Code](/powershell/scripting/components/vscode/how-to-replicate-the-ise-experience-in-vscode).</span><span class="sxs-lookup"><span data-stu-id="56472-242">For details about customizing the VSCode layout to ISE, see [How to Replicate the ISE Experience in Visual Studio Code](/powershell/scripting/components/vscode/how-to-replicate-the-ise-experience-in-vscode)</span></span>

> [!NOTE]
> <span data-ttu-id="56472-243">Обновления для ISE новыми возможностями сейчас не планируются.</span><span class="sxs-lookup"><span data-stu-id="56472-243">There no plans to update the ISE with new features.</span></span> <span data-ttu-id="56472-244">ISE в последних версиях Windows 10 и Windows Server теперь может удалить пользователь.</span><span class="sxs-lookup"><span data-stu-id="56472-244">The ISE is now a user-uninstallable feature in the latest versions of Windows 10 and Windows Server.</span></span> <span data-ttu-id="56472-245">Окончательное удаление ISE сейчас не планируется.</span><span class="sxs-lookup"><span data-stu-id="56472-245">There are no plans to permanently remove the ISE.</span></span> <span data-ttu-id="56472-246">Команда PowerShell и ее партнеры по работе сейчас работают над совершенствованием возможностей написания скриптов с использованием расширения PowerShell для Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="56472-246">The PowerShell Team and its partners are focused on improving the scripting experience in the PowerShell extension for Visual Studio Code.</span></span>

## <a name="next-steps"></a><span data-ttu-id="56472-247">Next Steps</span><span class="sxs-lookup"><span data-stu-id="56472-247">Next Steps</span></span>

<span data-ttu-id="56472-248">Теперь, когда вы узнали об эффективности миграции, [установите PowerShell 7](/powershell/scripting/install/installing-powershell-core-on-windows).</span><span class="sxs-lookup"><span data-stu-id="56472-248">Armed with the knowledge to effectively migrate, [install PowerShell 7](/powershell/scripting/install/installing-powershell-core-on-windows) now!</span></span>
