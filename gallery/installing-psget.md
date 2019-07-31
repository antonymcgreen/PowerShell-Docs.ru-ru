---
ms.date: 06/12/2017
contributor: manikb
keywords: коллекция,powershell,командлет,psget
title: Установка PowerShellGet
ms.openlocfilehash: 2d3ba8c4d4d4c7ee023c7e6a948a29d8f47ea242
ms.sourcegitcommit: 8d47eb41445ffaf10fcd68874e397c9a1703d898
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2019
ms.locfileid: "68601415"
---
# <a name="installing-powershellget"></a><span data-ttu-id="5f8f5-103">Установка PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="5f8f5-103">Installing PowerShellGet</span></span>

## <a name="powershellget-is-an-in-box-module-in-the-following-releases"></a><span data-ttu-id="5f8f5-104">Модуль PowerShellGet входит в комплект поставки в следующих выпусках:</span><span class="sxs-lookup"><span data-stu-id="5f8f5-104">PowerShellGet is an in-box module in the following releases</span></span>

- <span data-ttu-id="5f8f5-105">[Windows 10](https://www.microsoft.com/windows) или более поздняя версия;</span><span class="sxs-lookup"><span data-stu-id="5f8f5-105">[Windows 10](https://www.microsoft.com/windows) or newer</span></span>
- <span data-ttu-id="5f8f5-106">[Windows Server 2016](/windows-server/windows-server) или более поздняя версия;</span><span class="sxs-lookup"><span data-stu-id="5f8f5-106">[Windows Server 2016](/windows-server/windows-server) or newer</span></span>
- <span data-ttu-id="5f8f5-107">[Windows Management Framework (WMF) 5.0](https://www.microsoft.com/download/details.aspx?id=50395) или более поздняя версия;</span><span class="sxs-lookup"><span data-stu-id="5f8f5-107">[Windows Management Framework (WMF) 5.0](https://www.microsoft.com/download/details.aspx?id=50395) or newer</span></span>
- <span data-ttu-id="5f8f5-108">[PowerShell 6](https://github.com/PowerShell/PowerShell/releases).</span><span class="sxs-lookup"><span data-stu-id="5f8f5-108">[PowerShell 6](https://github.com/PowerShell/PowerShell/releases)</span></span>

## <a name="get-powershellget-module-for-powershell-versions-30-and-40"></a><span data-ttu-id="5f8f5-109">Получение модуля PowerShellGet для PowerShell версии 3.0 и 4.0</span><span class="sxs-lookup"><span data-stu-id="5f8f5-109">Get PowerShellGet module for PowerShell versions 3.0 and 4.0</span></span>

- [<span data-ttu-id="5f8f5-110">PackageManagement MSI</span><span class="sxs-lookup"><span data-stu-id="5f8f5-110">PackageManagement MSI</span></span>](https://www.microsoft.com/download/details.aspx?id=51451)

## <a name="get-the-latest-version-from-powershell-gallery"></a><span data-ttu-id="5f8f5-111">Получение последней версии из коллекции PowerShell</span><span class="sxs-lookup"><span data-stu-id="5f8f5-111">Get the latest version from PowerShell Gallery</span></span>

- <span data-ttu-id="5f8f5-112">Перед обновлением PowerShellGet всегда устанавливайте последний поставщик Nuget.</span><span class="sxs-lookup"><span data-stu-id="5f8f5-112">Before updating PowerShellGet, you should always install the latest Nuget provider.</span></span> <span data-ttu-id="5f8f5-113">Для этого выполните следующую команду в сеансе PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="5f8f5-113">To do that, run the following in an elevated PowerShell session.</span></span>

  ```powershell
  Install-PackageProvider Nuget -Force
  Exit
  ```

### <a name="for-systems-with-powershell-50-or-newer-you-can-install-the-latest-powershellget"></a><span data-ttu-id="5f8f5-114">Для систем с PowerShell 5.0 (или более поздней версии) можно установить последнюю версию PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="5f8f5-114">For systems with PowerShell 5.0 (or newer) you can install the latest PowerShellGet</span></span>

- <span data-ttu-id="5f8f5-115">Чтобы сделать это в Windows 10, Windows Server 2016, любой системе с установленным WMF 5.0 или 5.1 или любой системе с PowerShell 6, выполните следующие команды из сеанса PowerShell с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="5f8f5-115">To do this on Windows 10, Windows Server 2016, any system with WMF 5.0 or 5.1 installed, or any system with PowerShell 6, run the following commands from an elevated PowerShell session.</span></span>

  ```powershell
  Install-Module -Name PowerShellGet -Force
  Exit
  ```

- <span data-ttu-id="5f8f5-116">`Update-Module` позволяет получить более новые версии.</span><span class="sxs-lookup"><span data-stu-id="5f8f5-116">Use `Update-Module` to get newer versions.</span></span>

  ```powershell
  Update-Module -Name PowerShellGet
  Exit
  ```

### <a name="for-systems-running-powershell-3-or-powershell-4-that-have-installed-the-packagemanagement-msihttpswwwmicrosoftcomdownloaddetailsaspxid51451"></a><span data-ttu-id="5f8f5-117">Для систем под управлением PowerShell 3 или PowerShell 4, на которых установлено [PackageManagement MSI](https://www.microsoft.com/download/details.aspx?id=51451)</span><span class="sxs-lookup"><span data-stu-id="5f8f5-117">For systems running PowerShell 3 or PowerShell 4, that have installed the [PackageManagement MSI](https://www.microsoft.com/download/details.aspx?id=51451)</span></span>

- <span data-ttu-id="5f8f5-118">Используйте командлеты PowerShellGet ниже из сеанса PowerShell с повышенными привилегиями, чтобы сохранить модули в локальный каталог.</span><span class="sxs-lookup"><span data-stu-id="5f8f5-118">Use below PowerShellGet cmdlet from an elevated PowerShell session to save the modules to a local directory</span></span>

  ```powershell
  Save-Module PowerShellGet -Path C:\LocalFolder
  Exit
  ```

- <span data-ttu-id="5f8f5-119">Убедитесь, что модули PowerShellGet и PackageManagement не загружены в других процессах.</span><span class="sxs-lookup"><span data-stu-id="5f8f5-119">Ensure that PowerShellGet and PackageManagement modules are not loaded in any other processes.</span></span>
- <span data-ttu-id="5f8f5-120">Удалите содержимое папок `$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\` и `$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\`.</span><span class="sxs-lookup"><span data-stu-id="5f8f5-120">Delete contents of `$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\` and  `$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\` folders.</span></span>
- <span data-ttu-id="5f8f5-121">Снова откройте консоль PS с повышенным уровнем разрешений, а затем выполните следующие команды.</span><span class="sxs-lookup"><span data-stu-id="5f8f5-121">Re-open the PS Console with elevated permissions then run the following commands.</span></span>

  ```powershell
  Copy-Item "C:\LocalFolder\PowerShellGet\*" "$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\" -Recurse -Force
  Copy-Item "C:\LocalFolder\PackageManagement\*" "$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\" -Recurse -Force
  ```
