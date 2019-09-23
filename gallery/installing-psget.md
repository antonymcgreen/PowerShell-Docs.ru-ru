---
ms.date: 06/12/2017
contributor: manikb
keywords: коллекция,powershell,командлет,psget
title: Установка PowerShellGet
ms.openlocfilehash: a0ef46a9ee4bbf668a58067256d098967bde48c5
ms.sourcegitcommit: 0a6b562a497860caadba754c75a83215315d37a1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2019
ms.locfileid: "71143597"
---
# <a name="installing-powershellget"></a><span data-ttu-id="3228b-103">Установка PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="3228b-103">Installing PowerShellGet</span></span>

## <a name="powershellget-is-an-in-box-module-in-the-following-releases"></a><span data-ttu-id="3228b-104">Модуль PowerShellGet входит в комплект поставки в следующих выпусках:</span><span class="sxs-lookup"><span data-stu-id="3228b-104">PowerShellGet is an in-box module in the following releases</span></span>

- <span data-ttu-id="3228b-105">[Windows 10](https://www.microsoft.com/windows) или более поздняя версия;</span><span class="sxs-lookup"><span data-stu-id="3228b-105">[Windows 10](https://www.microsoft.com/windows) or newer</span></span>
- <span data-ttu-id="3228b-106">[Windows Server 2016](/windows-server/windows-server) или более поздняя версия;</span><span class="sxs-lookup"><span data-stu-id="3228b-106">[Windows Server 2016](/windows-server/windows-server) or newer</span></span>
- <span data-ttu-id="3228b-107">[Windows Management Framework (WMF) 5.0](https://www.microsoft.com/download/details.aspx?id=50395) или более поздняя версия;</span><span class="sxs-lookup"><span data-stu-id="3228b-107">[Windows Management Framework (WMF) 5.0](https://www.microsoft.com/download/details.aspx?id=50395) or newer</span></span>
- <span data-ttu-id="3228b-108">[PowerShell 6](https://github.com/PowerShell/PowerShell/releases).</span><span class="sxs-lookup"><span data-stu-id="3228b-108">[PowerShell 6](https://github.com/PowerShell/PowerShell/releases)</span></span>

## <a name="get-the-latest-version-from-powershell-gallery"></a><span data-ttu-id="3228b-109">Получение последней версии из коллекции PowerShell</span><span class="sxs-lookup"><span data-stu-id="3228b-109">Get the latest version from PowerShell Gallery</span></span>

<span data-ttu-id="3228b-110">Перед обновлением **PowerShellGet** всегда устанавливайте последний поставщик **NuGet**.</span><span class="sxs-lookup"><span data-stu-id="3228b-110">Before updating **PowerShellGet**, you should always install the latest **NuGet** provider.</span></span> <span data-ttu-id="3228b-111">Откройте сеанс PowerShell с повышенными привилегиями и выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="3228b-111">From an elevated PowerShell session, run the following command.</span></span>

```powershell
Install-PackageProvider -Name NuGet -Force
Exit
```

### <a name="for-systems-with-powershell-50-or-newer-you-can-install-the-latest-powershellget"></a><span data-ttu-id="3228b-112">Для систем с PowerShell 5.0 (или более поздней версии) можно установить последнюю версию PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="3228b-112">For systems with PowerShell 5.0 (or newer) you can install the latest PowerShellGet</span></span>

<span data-ttu-id="3228b-113">Чтобы установить PowerShellGet в Windows 10, Windows Server 2016, а также любой системе с WMF 5.0, 5.1 или PowerShell 6, выполните следующие команды из сеанса PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="3228b-113">To install PowerShellGet on Windows 10, Windows Server 2016, any system with WMF 5.0 or 5.1 installed, or any system with PowerShell 6, run the following commands from an elevated PowerShell session.</span></span>

```powershell
Install-Module -Name PowerShellGet -Force
Exit
```

<span data-ttu-id="3228b-114">`Update-Module` позволяет получить более новые версии.</span><span class="sxs-lookup"><span data-stu-id="3228b-114">Use `Update-Module` to get newer versions.</span></span>

```powershell
Update-Module -Name PowerShellGet
Exit
```

### <a name="for-systems-running-powershell-3-or-powershell-4-that-have-installed-the-packagemanagement-preview"></a><span data-ttu-id="3228b-115">Для систем под управлением PowerShell 3 или PowerShell 4, на которых установлена предварительная версия PackageManagement</span><span class="sxs-lookup"><span data-stu-id="3228b-115">For systems running PowerShell 3 or PowerShell 4, that have installed the PackageManagement Preview</span></span>

1. <span data-ttu-id="3228b-116">В сеансе PowerShell с повышенными привилегиями используйте `Save-Module`, чтобы сохранить модули в локальном каталоге.</span><span class="sxs-lookup"><span data-stu-id="3228b-116">From an elevated PowerShell session, use `Save-Module` to save the modules to a local directory.</span></span>

   ```powershell
   Save-Module -Name PowerShellGet -Path C:\LocalFolder
   Exit
   ```

1. <span data-ttu-id="3228b-117">Убедитесь, что модули **PowerShellGet** и **PackageManagement** не загружаются в других процессах.</span><span class="sxs-lookup"><span data-stu-id="3228b-117">Ensure that the **PowerShellGet** and **PackageManagement** modules aren't loaded in any other processes.</span></span>
1. <span data-ttu-id="3228b-118">Удалите содержимое папок `$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\` и `$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\`.</span><span class="sxs-lookup"><span data-stu-id="3228b-118">Delete the contents of the folders: `$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\` and `$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\`.</span></span>
1. <span data-ttu-id="3228b-119">Снова откройте консоль PowerShell с повышенными привилегиями, а затем выполните следующие команды.</span><span class="sxs-lookup"><span data-stu-id="3228b-119">Reopen the PowerShell console with elevated permissions and run the following commands.</span></span>

   ```powershell
   Copy-Item "C:\LocalFolder\PowerShellGet\*" "$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\" -Recurse -Force
   Copy-Item "C:\LocalFolder\PackageManagement\*" "$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\" -Recurse -Force
   ```
