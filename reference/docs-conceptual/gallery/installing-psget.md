---
ms.date: 09/19/2019
title: Установка PowerShellGet
description: В этой статье описывается, как установить модуль PowerShellGet в разных версиях PowerShell.
ms.openlocfilehash: 06ec331446849784bb8464912fbce0e5a940823f
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92662151"
---
# <a name="installing-powershellget"></a><span data-ttu-id="b14ec-103">Установка PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="b14ec-103">Installing PowerShellGet</span></span>

## <a name="powershellget-is-an-in-box-module-in-the-following-releases"></a><span data-ttu-id="b14ec-104">Модуль PowerShellGet входит в комплект поставки в следующих выпусках:</span><span class="sxs-lookup"><span data-stu-id="b14ec-104">PowerShellGet is an in-box module in the following releases</span></span>

- <span data-ttu-id="b14ec-105">[Windows 10](https://www.microsoft.com/windows) или более поздняя версия;</span><span class="sxs-lookup"><span data-stu-id="b14ec-105">[Windows 10](https://www.microsoft.com/windows) or newer</span></span>
- <span data-ttu-id="b14ec-106">[Windows Server 2016](/windows-server/windows-server) или более поздняя версия;</span><span class="sxs-lookup"><span data-stu-id="b14ec-106">[Windows Server 2016](/windows-server/windows-server) or newer</span></span>
- <span data-ttu-id="b14ec-107">[Windows Management Framework (WMF) 5.0](https://www.microsoft.com/download/details.aspx?id=50395) или более поздняя версия;</span><span class="sxs-lookup"><span data-stu-id="b14ec-107">[Windows Management Framework (WMF) 5.0](https://www.microsoft.com/download/details.aspx?id=50395) or newer</span></span>
- <span data-ttu-id="b14ec-108">[PowerShell 6](https://github.com/PowerShell/PowerShell/releases).</span><span class="sxs-lookup"><span data-stu-id="b14ec-108">[PowerShell 6](https://github.com/PowerShell/PowerShell/releases)</span></span>

## <a name="get-the-latest-version-from-powershell-gallery"></a><span data-ttu-id="b14ec-109">Получение последней версии из коллекции PowerShell</span><span class="sxs-lookup"><span data-stu-id="b14ec-109">Get the latest version from PowerShell Gallery</span></span>

<span data-ttu-id="b14ec-110">Перед обновлением **PowerShellGet** всегда устанавливайте последний поставщик **NuGet**.</span><span class="sxs-lookup"><span data-stu-id="b14ec-110">Before updating **PowerShellGet** , you should always install the latest **NuGet** provider.</span></span> <span data-ttu-id="b14ec-111">Откройте сеанс PowerShell с повышенными привилегиями и выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="b14ec-111">From an elevated PowerShell session, run the following command.</span></span>

```powershell
Install-PackageProvider -Name NuGet -Force
```

### <a name="for-systems-with-powershell-50-or-newer-you-can-install-the-latest-powershellget"></a><span data-ttu-id="b14ec-112">Для систем с PowerShell 5.0 (или более поздней версии) можно установить последнюю версию PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="b14ec-112">For systems with PowerShell 5.0 (or newer) you can install the latest PowerShellGet</span></span>

<span data-ttu-id="b14ec-113">Чтобы установить PowerShellGet в Windows 10, Windows Server 2016, а также любой системе с WMF 5.0, 5.1 или PowerShell 6, выполните следующие команды из сеанса PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="b14ec-113">To install PowerShellGet on Windows 10, Windows Server 2016, any system with WMF 5.0 or 5.1 installed, or any system with PowerShell 6, run the following commands from an elevated PowerShell session.</span></span>

```powershell
Install-Module -Name PowerShellGet -Force
```

<span data-ttu-id="b14ec-114">`Update-Module` позволяет получить более новые версии.</span><span class="sxs-lookup"><span data-stu-id="b14ec-114">Use `Update-Module` to get newer versions.</span></span>

```powershell
Update-Module -Name PowerShellGet
Exit
```

### <a name="for-computers-running-powershell-30-or-powershell-40"></a><span data-ttu-id="b14ec-115">Для компьютеров с PowerShell 3.0 или 4.0</span><span class="sxs-lookup"><span data-stu-id="b14ec-115">For computers running PowerShell 3.0 or PowerShell 4.0</span></span>

<span data-ttu-id="b14ec-116">Эти инструкции применимы к компьютерам, на которых установлена предварительная версия **PackageManagement** или не установлены никакие версии **PowerShellGet**.</span><span class="sxs-lookup"><span data-stu-id="b14ec-116">These instructions apply to computers that have the **PackageManagement Preview** installed or don't have any version of **PowerShellGet** installed.</span></span>

<span data-ttu-id="b14ec-117">Командлет `Save-Module` используется в обоих наборах инструкций.</span><span class="sxs-lookup"><span data-stu-id="b14ec-117">The `Save-Module` cmdlet is used in both sets of instructions.</span></span> <span data-ttu-id="b14ec-118">`Save-Module` скачивает и сохраняет модуль и все зависимости из зарегистрированного репозитория.</span><span class="sxs-lookup"><span data-stu-id="b14ec-118">`Save-Module` downloads and saves a module and any dependencies from a registered repository.</span></span> <span data-ttu-id="b14ec-119">Самая последняя версия модуля сохраняется по указанному пути на локальном компьютере, но не устанавливается.</span><span class="sxs-lookup"><span data-stu-id="b14ec-119">The module's most current version is saved to a specified path on the local computer, but isn't installed.</span></span> <span data-ttu-id="b14ec-120">Чтобы установить модули в PowerShell 3.0 или 4.0, скопируйте сохраненные папки модуля в `$env:ProgramFiles\WindowsPowerShell\Modules`.</span><span class="sxs-lookup"><span data-stu-id="b14ec-120">To install the modules in PowerShell 3.0 or 4.0, copy the module saved folders to `$env:ProgramFiles\WindowsPowerShell\Modules`.</span></span>

<span data-ttu-id="b14ec-121">Дополнительные сведения см. в статье [Save-Module](/powershell/module/PowershellGet/Save-Module).</span><span class="sxs-lookup"><span data-stu-id="b14ec-121">For more information, see [Save-Module](/powershell/module/PowershellGet/Save-Module).</span></span>

> [!NOTE]
> <span data-ttu-id="b14ec-122">PowerShell 3.0 и 4.0 поддерживают только одну версию модуля.</span><span class="sxs-lookup"><span data-stu-id="b14ec-122">PowerShell 3.0 and PowerShell 4.0 only supported one version of a module.</span></span> <span data-ttu-id="b14ec-123">Начиная с версии PowerShell 5.0 модули устанавливаются в папку `<modulename>\<version>`.</span><span class="sxs-lookup"><span data-stu-id="b14ec-123">Starting in PowerShell 5.0, modules are installed in `<modulename>\<version>`.</span></span> <span data-ttu-id="b14ec-124">Это позволяет устанавливать несколько версий параллельно.</span><span class="sxs-lookup"><span data-stu-id="b14ec-124">This allows you to install multiple versions side-by-side.</span></span> <span data-ttu-id="b14ec-125">Скачав модуль с помощью `Save-Module`, необходимо скопировать файлы из `<modulename>\<version>` в папку `<modulename>` на целевом компьютере, как показано в приведенных ниже инструкциях.</span><span class="sxs-lookup"><span data-stu-id="b14ec-125">After downloading the module using `Save-Module` you must copy the files from the `<modulename>\<version>` to the `<modulename>` folder on the destination machine, as shown in the instructions below.</span></span>

#### <a name="preparatory-step-on-computers-running-powershell-30"></a><span data-ttu-id="b14ec-126">Подготовительные действия на компьютерах с PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="b14ec-126">Preparatory Step on computers running PowerShell 3.0</span></span>

<span data-ttu-id="b14ec-127">Инструкции, приведенные в разделах ниже, устанавливают модули в каталоге `$env:ProgramFiles\WindowsPowerShell\Modules`.</span><span class="sxs-lookup"><span data-stu-id="b14ec-127">The instructions in the sections below install the modules in directory `$env:ProgramFiles\WindowsPowerShell\Modules`.</span></span>
<span data-ttu-id="b14ec-128">В PowerShell 3.0 этот каталог отсутствует в `$env:PSModulePath` по умолчанию, поэтому его необходимо добавить, чтобы модули загружались автоматически.</span><span class="sxs-lookup"><span data-stu-id="b14ec-128">In PowerShell 3.0, this directory isn't listed in `$env:PSModulePath` by default, so you'll need to add it in order for the modules to be auto-loaded.</span></span>

<span data-ttu-id="b14ec-129">Откройте сеанс Windows PowerShell с повышенными привилегиями и выполните в нем следующую команду (действие будет заметно в будущих сеансах).</span><span class="sxs-lookup"><span data-stu-id="b14ec-129">Open an elevated PowerShell session and run the following command (which will take effect in future sessions):</span></span>

```powershell
[Environment]::SetEnvironmentVariable(
  'PSModulePath',
  ((([Environment]::GetEnvironmentVariable('PSModulePath', 'Machine') -split ';') + "$env:ProgramFiles\WindowsPowerShell\Modules") -join ';'),
  'Machine'
)
```

#### <a name="computers-with-the-packagemanagement-preview-installed"></a><span data-ttu-id="b14ec-130">Компьютеры с установленной предварительной версией PackageManagement</span><span class="sxs-lookup"><span data-stu-id="b14ec-130">Computers with the PackageManagement Preview installed</span></span>

> [!NOTE]
> <span data-ttu-id="b14ec-131">Предварительная версия PackageManagement была загружаемым компонентом, который обеспечивал доступность PowerShellGet для PowerShell версий 3 и 4, но сейчас он недоступен.</span><span class="sxs-lookup"><span data-stu-id="b14ec-131">PackageManagement Preview was a downloadable component that made PowerShellGet available to PowerShell versions 3 and 4, but it is no longer available.</span></span>
> <span data-ttu-id="b14ec-132">Чтобы проверить, установлен ли он на данном компьютере, выполните `Get-Module -ListAvailable PowerShellGet`.</span><span class="sxs-lookup"><span data-stu-id="b14ec-132">To test if it was installed on a given computer, run `Get-Module -ListAvailable PowerShellGet`.</span></span>

1. <span data-ttu-id="b14ec-133">В сеансе PowerShell используйте `Save-Module`, чтобы скачать текущую версию **PowerShellGet**.</span><span class="sxs-lookup"><span data-stu-id="b14ec-133">From a PowerShell session, use `Save-Module` to download the current version of **PowerShellGet**.</span></span> <span data-ttu-id="b14ec-134">Скачиваются две папки: **PowerShellGet** и **PackageManagement**.</span><span class="sxs-lookup"><span data-stu-id="b14ec-134">Two folders are downloaded: **PowerShellGet** and **PackageManagement**.</span></span> <span data-ttu-id="b14ec-135">Каждая папка содержит вложенную папку с номером версии.</span><span class="sxs-lookup"><span data-stu-id="b14ec-135">Each folder contains a subfolder with a version number.</span></span>

   ```powershell
   Save-Module -Name PowerShellGet -Path C:\LocalFolder -Repository PSGallery
   ```

1. <span data-ttu-id="b14ec-136">Убедитесь, что модули **PowerShellGet** и **PackageManagement** не загружаются в других процессах.</span><span class="sxs-lookup"><span data-stu-id="b14ec-136">Ensure that the **PowerShellGet** and **PackageManagement** modules aren't loaded in any other processes.</span></span>

1. <span data-ttu-id="b14ec-137">Снова откройте консоль PowerShell с повышенными привилегиями, а затем выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="b14ec-137">Reopen the PowerShell console with elevated permissions and run the following command.</span></span>

   ```powershell
   'PowerShellGet', 'PackageManagement' | % {
     $targetDir = "$env:ProgramFiles\WindowsPowerShell\Modules\$_"
     Remove-Item $targetDir\* -Recurse -Force
     Copy-Item C:\LocalFolder\$_\*\* $targetDir\ -Recurse -Force
   }
   ```

#### <a name="computers-without-powershellget"></a><span data-ttu-id="b14ec-138">Компьютеры без PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="b14ec-138">Computers without PowerShellGet</span></span>

<span data-ttu-id="b14ec-139">Если на компьютере нет какой-либо версии **PowerShellGet** (проверьте это командой `Get-Module -ListAvailable PowerShellGet`), для скачивания модулей необходим компьютер с **PowerShellGet**.</span><span class="sxs-lookup"><span data-stu-id="b14ec-139">For computers without any version of **PowerShellGet** installed (test with `Get-Module -ListAvailable PowerShellGet`), a computer with **PowerShellGet** installed is needed to download the modules.</span></span>

1. <span data-ttu-id="b14ec-140">На компьютере с установленным **PowerShellGet** используйте `Save-Module`, чтобы скачать текущую версию **PowerShellGet**.</span><span class="sxs-lookup"><span data-stu-id="b14ec-140">From the computer that has **PowerShellGet** installed, use `Save-Module` to download the current version of **PowerShellGet**.</span></span> <span data-ttu-id="b14ec-141">Скачиваются две папки: **PowerShellGet** и **PackageManagement**.</span><span class="sxs-lookup"><span data-stu-id="b14ec-141">Two folders are downloaded: **PowerShellGet** and **PackageManagement**.</span></span> <span data-ttu-id="b14ec-142">Каждая папка содержит вложенную папку с номером версии.</span><span class="sxs-lookup"><span data-stu-id="b14ec-142">Each folder contains a subfolder with a version number.</span></span>

   ```powershell
   Save-Module -Name PowerShellGet -Path C:\LocalFolder -Repository PSGallery
   ```

1. <span data-ttu-id="b14ec-143">Скопируйте соответствующую вложенную папку `<version>` в папках **PowerShellGet** и **PackageManagement** на компьютер, на котором не установлен **PowerShellGet** , в папки `$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\` и `$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\` соответственно (требуется сеанс с повышенными правами).</span><span class="sxs-lookup"><span data-stu-id="b14ec-143">Copy the respective `<version>` subfolder in the **PowerShellGet** and **PackageManagement** folders to the computer that doesn't have **PowerShellGet** installed, into folders `$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\` and `$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\` respectively, which requires an elevated session.</span></span>

1. <span data-ttu-id="b14ec-144">Например, если у вас есть доступ к папке загрузки на другом компьютере (скажем, `ws1`), с целевого компьютера по UNC-пути (допустим, `\\ws1\C$\LocalFolder`) откройте консоль PowerShell с повышенными правами и выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="b14ec-144">For instance, if you can access the download folder on the other computer, say `ws1`, from the target computer via a UNC path, say `\\ws1\C$\LocalFolder`, open a PowerShell console with elevated permissions and run the following command:</span></span>

   ```powershell
   'PowerShellGet', 'PackageManagement' | % {
     $targetDir = "$env:ProgramFiles\WindowsPowerShell\Modules\$_"
     $null = New-Item -Type Directory -Force $targetDir
     $fromComputer = 'ws1'  # Specify the name of the other computer here.
     Copy-Item \\$fromComputer\C$\LocalFolder\$_\*\* $targetDir -Recurse -Force
     if (-not (Get-ChildItem $targetDir)) { Throw "Copying failed." }
   }
   ```
