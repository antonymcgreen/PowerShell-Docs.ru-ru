---
ms.date: 09/19/2019
contributor: manikb
keywords: коллекция,powershell,командлет,psget
title: Установка PowerShellGet
ms.openlocfilehash: 69dc851c54089b47fb19e5b32990d579d26effb9
ms.sourcegitcommit: 4a2cf30351620a58ba95ff5d76b247e601907589
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/27/2019
ms.locfileid: "71328205"
---
# <a name="installing-powershellget"></a><span data-ttu-id="4c2d2-103">Установка PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="4c2d2-103">Installing PowerShellGet</span></span>

## <a name="powershellget-is-an-in-box-module-in-the-following-releases"></a><span data-ttu-id="4c2d2-104">Модуль PowerShellGet входит в комплект поставки в следующих выпусках:</span><span class="sxs-lookup"><span data-stu-id="4c2d2-104">PowerShellGet is an in-box module in the following releases</span></span>

- <span data-ttu-id="4c2d2-105">[Windows 10](https://www.microsoft.com/windows) или более поздняя версия;</span><span class="sxs-lookup"><span data-stu-id="4c2d2-105">[Windows 10](https://www.microsoft.com/windows) or newer</span></span>
- <span data-ttu-id="4c2d2-106">[Windows Server 2016](/windows-server/windows-server) или более поздняя версия;</span><span class="sxs-lookup"><span data-stu-id="4c2d2-106">[Windows Server 2016](/windows-server/windows-server) or newer</span></span>
- <span data-ttu-id="4c2d2-107">[Windows Management Framework (WMF) 5.0](https://www.microsoft.com/download/details.aspx?id=50395) или более поздняя версия;</span><span class="sxs-lookup"><span data-stu-id="4c2d2-107">[Windows Management Framework (WMF) 5.0](https://www.microsoft.com/download/details.aspx?id=50395) or newer</span></span>
- <span data-ttu-id="4c2d2-108">[PowerShell 6](https://github.com/PowerShell/PowerShell/releases).</span><span class="sxs-lookup"><span data-stu-id="4c2d2-108">[PowerShell 6](https://github.com/PowerShell/PowerShell/releases)</span></span>

## <a name="get-the-latest-version-from-powershell-gallery"></a><span data-ttu-id="4c2d2-109">Получение последней версии из коллекции PowerShell</span><span class="sxs-lookup"><span data-stu-id="4c2d2-109">Get the latest version from PowerShell Gallery</span></span>

<span data-ttu-id="4c2d2-110">Перед обновлением **PowerShellGet** всегда устанавливайте последний поставщик **NuGet**.</span><span class="sxs-lookup"><span data-stu-id="4c2d2-110">Before updating **PowerShellGet**, you should always install the latest **NuGet** provider.</span></span> <span data-ttu-id="4c2d2-111">Откройте сеанс PowerShell с повышенными привилегиями и выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="4c2d2-111">From an elevated PowerShell session, run the following command.</span></span>

```powershell
Install-PackageProvider -Name NuGet -Force
Exit
```

### <a name="for-systems-with-powershell-50-or-newer-you-can-install-the-latest-powershellget"></a><span data-ttu-id="4c2d2-112">Для систем с PowerShell 5.0 (или более поздней версии) можно установить последнюю версию PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="4c2d2-112">For systems with PowerShell 5.0 (or newer) you can install the latest PowerShellGet</span></span>

<span data-ttu-id="4c2d2-113">Чтобы установить PowerShellGet в Windows 10, Windows Server 2016, а также любой системе с WMF 5.0, 5.1 или PowerShell 6, выполните следующие команды из сеанса PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="4c2d2-113">To install PowerShellGet on Windows 10, Windows Server 2016, any system with WMF 5.0 or 5.1 installed, or any system with PowerShell 6, run the following commands from an elevated PowerShell session.</span></span>

```powershell
Install-Module -Name PowerShellGet -Force
Exit
```

<span data-ttu-id="4c2d2-114">`Update-Module` позволяет получить более новые версии.</span><span class="sxs-lookup"><span data-stu-id="4c2d2-114">Use `Update-Module` to get newer versions.</span></span>

```powershell
Update-Module -Name PowerShellGet
Exit
```

### <a name="for-computers-running-powershell-30-or-powershell-40"></a><span data-ttu-id="4c2d2-115">Для компьютеров с PowerShell 3.0 или 4.0</span><span class="sxs-lookup"><span data-stu-id="4c2d2-115">For computers running PowerShell 3.0 or PowerShell 4.0</span></span>

<span data-ttu-id="4c2d2-116">Эти инструкции применимы к компьютерам, на которых установлена предварительная версия **PackageManagement** или не установлены никакие версии **PowerShellGet**.</span><span class="sxs-lookup"><span data-stu-id="4c2d2-116">These instructions apply to computers that have the **PackageManagement Preview** installed or don't have any version of **PowerShellGet** installed.</span></span>

<span data-ttu-id="4c2d2-117">Командлет `Save-Module` используется в обоих наборах инструкций.</span><span class="sxs-lookup"><span data-stu-id="4c2d2-117">The `Save-Module` cmdlet is used in both sets of instructions.</span></span> <span data-ttu-id="4c2d2-118">`Save-Module` скачивает и сохраняет модуль и все зависимости из зарегистрированного репозитория.</span><span class="sxs-lookup"><span data-stu-id="4c2d2-118">`Save-Module` downloads and saves a module and any dependencies from a registered repository.</span></span> <span data-ttu-id="4c2d2-119">Самая последняя версия модуля сохраняется по указанному пути на локальном компьютере, но не устанавливается.</span><span class="sxs-lookup"><span data-stu-id="4c2d2-119">The module's most current version is saved to a specified path on the local computer, but isn't installed.</span></span> <span data-ttu-id="4c2d2-120">Дополнительные сведения см. в статье [Save-Module](/powershell/module/PowershellGet/Save-Module).</span><span class="sxs-lookup"><span data-stu-id="4c2d2-120">For more information, see [Save-Module](/powershell/module/PowershellGet/Save-Module).</span></span>

#### <a name="computers-with-the-packagemanagement-preview-installed"></a><span data-ttu-id="4c2d2-121">Компьютеры с установленной предварительной версией PackageManagement</span><span class="sxs-lookup"><span data-stu-id="4c2d2-121">Computers with the PackageManagement Preview installed</span></span>

1. <span data-ttu-id="4c2d2-122">В сеансе PowerShell используйте `Save-Module`, чтобы сохранить модули в локальном каталоге.</span><span class="sxs-lookup"><span data-stu-id="4c2d2-122">From a PowerShell session, use `Save-Module` to save the modules to a local directory.</span></span>

   ```powershell
   Save-Module -Name PowerShellGet -Path C:\LocalFolder -Repository PSGallery
   ```

1. <span data-ttu-id="4c2d2-123">Убедитесь, что модули **PowerShellGet** и **PackageManagement** не загружаются в других процессах.</span><span class="sxs-lookup"><span data-stu-id="4c2d2-123">Ensure that the **PowerShellGet** and **PackageManagement** modules aren't loaded in any other processes.</span></span>
1. <span data-ttu-id="4c2d2-124">Удалите содержимое папок `$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\` и `$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\`.</span><span class="sxs-lookup"><span data-stu-id="4c2d2-124">Delete the contents of the folders: `$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\` and `$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\`.</span></span>
1. <span data-ttu-id="4c2d2-125">Снова откройте консоль PowerShell с повышенными привилегиями, а затем выполните следующие команды.</span><span class="sxs-lookup"><span data-stu-id="4c2d2-125">Reopen the PowerShell console with elevated permissions and run the following commands.</span></span>

   ```powershell
   Copy-Item "C:\LocalFolder\PowerShellGet\*" "$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\" -Recurse -Force
   Copy-Item "C:\LocalFolder\PackageManagement\*" "$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\" -Recurse -Force
   ```

#### <a name="computers-without-powershellget"></a><span data-ttu-id="4c2d2-126">Компьютеры без PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="4c2d2-126">Computers without PowerShellGet</span></span>

<span data-ttu-id="4c2d2-127">Если на компьютере нет какой-либо версии **PowerShellGet**, для скачивания модулей необходим компьютер с **PowerShellGet**.</span><span class="sxs-lookup"><span data-stu-id="4c2d2-127">For computer's without any version of **PowerShellGet** installed, a computer with **PowerShellGet** installed is needed to download the modules.</span></span>

1. <span data-ttu-id="4c2d2-128">На компьютере с установленным **PowerShellGet** используйте `Save-Module`, чтобы скачать текущую версию **PowerShellGet**.</span><span class="sxs-lookup"><span data-stu-id="4c2d2-128">From the computer that has **PowerShellGet** installed, use `Save-Module` to download the current version of **PowerShellGet**.</span></span> <span data-ttu-id="4c2d2-129">Скачиваются две папки: **PowerShellGet** и **PackageManagement**.</span><span class="sxs-lookup"><span data-stu-id="4c2d2-129">Two folders are downloaded: **PowerShellGet** and **PackageManagement**.</span></span> <span data-ttu-id="4c2d2-130">Каждая папка содержит вложенную папку с номером версии.</span><span class="sxs-lookup"><span data-stu-id="4c2d2-130">Each folder contains a subfolder with a version number.</span></span>

   ```powershell
   Save-Module -Name PowerShellGet -Path C:\LocalFolder -Repository PSGallery
   ```

1. <span data-ttu-id="4c2d2-131">Скопируйте папки **PowerShellGet** и **PackageManagement** на компьютер, на котором не установлен **PowerShellGet**.</span><span class="sxs-lookup"><span data-stu-id="4c2d2-131">Copy the **PowerShellGet** and **PackageManagement** folders to the computer that doesn't have **PowerShellGet** installed.</span></span>

   <span data-ttu-id="4c2d2-132">Каталог назначения: `$env:ProgramFiles\WindowsPowerShell\Modules`.</span><span class="sxs-lookup"><span data-stu-id="4c2d2-132">The destination directory is: `$env:ProgramFiles\WindowsPowerShell\Modules`</span></span>
