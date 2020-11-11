---
title: Установка PowerShell в Windows
description: Сведения об установке PowerShell в Windows
ms.date: 10/30/2020
ms.openlocfilehash: 825c9066d0a4e4734b9255514520b32f0876ecea
ms.sourcegitcommit: 109ff625773389be56e98e994b7e56146f2b9d93
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2020
ms.locfileid: "93296369"
---
# <a name="installing-powershell-on-windows"></a><span data-ttu-id="59946-103">Установка PowerShell в Windows</span><span class="sxs-lookup"><span data-stu-id="59946-103">Installing PowerShell on Windows</span></span>

<span data-ttu-id="59946-104">Есть несколько способов установки PowerShell в Windows.</span><span class="sxs-lookup"><span data-stu-id="59946-104">There are multiple ways to install PowerShell in Windows.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="59946-105">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="59946-105">Prerequisites</span></span>

<span data-ttu-id="59946-106">Последний выпуск PowerShell поддерживается в Windows 7 с пакетом обновления 1 (SP1), Windows Server 2008 R2 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="59946-106">The latest release of PowerShell is supported on Windows 7 SP1, Server 2008 R2, and later versions.</span></span>

<span data-ttu-id="59946-107">Чтобы включить удаленное взаимодействие PowerShell через WSMan, нужно выполнить следующие условия:</span><span class="sxs-lookup"><span data-stu-id="59946-107">To enable PowerShell remoting over WSMan, the following prerequisites need to be met:</span></span>

- <span data-ttu-id="59946-108">Установите [универсальную среду выполнения C](https://www.microsoft.com/download/details.aspx?id=50410) в Windows предшествующих Windows 10 версий.</span><span class="sxs-lookup"><span data-stu-id="59946-108">Install the [Universal C Runtime](https://www.microsoft.com/download/details.aspx?id=50410) on Windows versions predating Windows 10.</span></span> <span data-ttu-id="59946-109">Ее можно скачать самостоятельно или через Центр обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="59946-109">It's available via direct download or Windows Update.</span></span> <span data-ttu-id="59946-110">Этот пакет уже установлен в полностью исправленных системах.</span><span class="sxs-lookup"><span data-stu-id="59946-110">Fully patched systems already have this package installed.</span></span>
- <span data-ttu-id="59946-111">Установите Windows Management Framework (WMF) 4.0 или более поздней версии в Windows 7 и Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="59946-111">Install the Windows Management Framework (WMF) 4.0 or newer on Windows 7 and Windows Server 2008 R2.</span></span> <span data-ttu-id="59946-112">Подробные сведения о WMF см. в статье с [обзором WMF](/powershell/scripting/wmf/overview).</span><span class="sxs-lookup"><span data-stu-id="59946-112">For more information about WMF, see [WMF Overview](/powershell/scripting/wmf/overview).</span></span>

## <a name="download-the-installer-package"></a><span data-ttu-id="59946-113">Скачивание скрипта установщика</span><span class="sxs-lookup"><span data-stu-id="59946-113">Download the installer package</span></span>

<span data-ttu-id="59946-114">Чтобы установить PowerShell в Windows скачайте [актуальный][] пакет установки с GitHub.</span><span class="sxs-lookup"><span data-stu-id="59946-114">To install PowerShell on Windows, download the [latest][] install package from GitHub.</span></span> <span data-ttu-id="59946-115">Также доступна актуальная предварительная версия на странице [выпуски][].</span><span class="sxs-lookup"><span data-stu-id="59946-115">You can also find the latest preview version on the [releases][] page.</span></span> <span data-ttu-id="59946-116">Прокрутите страницу вниз до раздела **ресурсов**.</span><span class="sxs-lookup"><span data-stu-id="59946-116">Scroll down to the **Assets** section of the Release page.</span></span> <span data-ttu-id="59946-117">Раздел **ресурсов** может быть свернут. В таком случае щелкните его, чтобы развернуть.</span><span class="sxs-lookup"><span data-stu-id="59946-117">The **Assets** section may be collapsed, so you may need to click to expand it.</span></span>

## <a name="installing-the-msi-package"></a><span data-ttu-id="59946-118"><a id="msi" />Установка пакета MSI</span><span class="sxs-lookup"><span data-stu-id="59946-118"><a id="msi" />Installing the MSI package</span></span>

<span data-ttu-id="59946-119">MSI-файл выглядит примерно так: `PowerShell-<version>-win-<os-arch>.msi`.</span><span class="sxs-lookup"><span data-stu-id="59946-119">The MSI file looks like `PowerShell-<version>-win-<os-arch>.msi`.</span></span> <span data-ttu-id="59946-120">Пример:</span><span class="sxs-lookup"><span data-stu-id="59946-120">For example:</span></span>

- `PowerShell-7.0.3-win-x64.msi`
- `PowerShell-7.0.3-win-x86.msi`

<span data-ttu-id="59946-121">После скачивания дважды щелкните установщик и следуйте инструкциям на экране.</span><span class="sxs-lookup"><span data-stu-id="59946-121">Once downloaded, double-click the installer and follow the prompts.</span></span>

<span data-ttu-id="59946-122">Программа установки создает ярлык в меню Windows "Пуск".</span><span class="sxs-lookup"><span data-stu-id="59946-122">The installer creates a shortcut in the Windows Start Menu.</span></span>

- <span data-ttu-id="59946-123">По умолчанию пакет устанавливается в каталог `$env:ProgramFiles\PowerShell\<version>`.</span><span class="sxs-lookup"><span data-stu-id="59946-123">By default the package is installed to `$env:ProgramFiles\PowerShell\<version>`</span></span>
- <span data-ttu-id="59946-124">Вы можете запустить PowerShell с помощью меню "Пуск" или файла `$env:ProgramFiles\PowerShell\<version>\pwsh.exe`.</span><span class="sxs-lookup"><span data-stu-id="59946-124">You can launch PowerShell via the Start Menu or `$env:ProgramFiles\PowerShell\<version>\pwsh.exe`</span></span>

> [!NOTE]
> <span data-ttu-id="59946-125">PowerShell 7 устанавливается в новом каталоге и работает параллельно с Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="59946-125">PowerShell 7 installs to a new directory and runs side-by-side with Windows PowerShell 5.1.</span></span> <span data-ttu-id="59946-126">Для PowerShell Core 6.x версия PowerShell 7 является обновлением на месте, при установке которого PowerShell Core 6.x удаляется.</span><span class="sxs-lookup"><span data-stu-id="59946-126">For PowerShell Core 6.x, PowerShell 7 is an in-place upgrade that removes PowerShell Core 6.x.</span></span>
>
> - <span data-ttu-id="59946-127">PowerShell 7 устанавливается в папке `$env:ProgramFiles\PowerShell\7`.</span><span class="sxs-lookup"><span data-stu-id="59946-127">PowerShell 7 is installed to `$env:ProgramFiles\PowerShell\7`</span></span>
> - <span data-ttu-id="59946-128">Папка `$env:ProgramFiles\PowerShell\7` добавляется в переменную `$env:PATH`.</span><span class="sxs-lookup"><span data-stu-id="59946-128">The `$env:ProgramFiles\PowerShell\7` folder is added to `$env:PATH`</span></span>
> - <span data-ttu-id="59946-129">Папка `$env:ProgramFiles\PowerShell\6` удалена.</span><span class="sxs-lookup"><span data-stu-id="59946-129">The `$env:ProgramFiles\PowerShell\6` folder is deleted</span></span>
>
> <span data-ttu-id="59946-130">Если вы хотите запускать PowerShell 6 параллельно с PowerShell 7, переустановите PowerShell 6 с использованием [ZIP-архива](#zip).</span><span class="sxs-lookup"><span data-stu-id="59946-130">If you need to run PowerShell 6 side-by-side with PowerShell 7, reinstall PowerShell 6 using the [ZIP install](#zip) method.</span></span>

### <a name="administrative-install-from-the-command-line"></a><span data-ttu-id="59946-131">Установка администратором из командной строки</span><span class="sxs-lookup"><span data-stu-id="59946-131">Administrative install from the command line</span></span>

<span data-ttu-id="59946-132">MSI-пакеты можно устанавливать из командной строки, что позволяет администраторам развертывать их без взаимодействия с пользователем.</span><span class="sxs-lookup"><span data-stu-id="59946-132">MSI packages can be installed from the command line allowing administrators to deploy packages without user interaction.</span></span> <span data-ttu-id="59946-133">MSI-пакет включает в себя следующие свойства для управления параметрами установки:</span><span class="sxs-lookup"><span data-stu-id="59946-133">The MSI package includes the following properties to control the installation options:</span></span>

- <span data-ttu-id="59946-134">**ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL**. Это свойство позволяет добавлять пункт **Открыть PowerShell** в контекстное меню проводника.</span><span class="sxs-lookup"><span data-stu-id="59946-134">**ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL** - This property controls the option for adding the **Open PowerShell** item to the context menu in Windows Explorer.</span></span>
- <span data-ttu-id="59946-135">**ENABLE_PSREMOTING**. Это свойство позволяет включать удаленное взаимодействие PowerShell во время установки.</span><span class="sxs-lookup"><span data-stu-id="59946-135">**ENABLE_PSREMOTING** - This property controls the option for enabling PowerShell remoting during installation.</span></span>
- <span data-ttu-id="59946-136">**REGISTER_MANIFEST**. Это свойство позволяет регистрировать манифест ведения журнала событий Windows.</span><span class="sxs-lookup"><span data-stu-id="59946-136">**REGISTER_MANIFEST** - This property controls the option for registering the Windows Event Logging manifest.</span></span>

<span data-ttu-id="59946-137">В следующих примерах показано, как выполнить автоматическую установку PowerShell со всеми включенными параметрами.</span><span class="sxs-lookup"><span data-stu-id="59946-137">The following example shows how to silently install PowerShell with all the install options enabled.</span></span>

```powershell
msiexec.exe /package PowerShell-7.0.3-win-x64.msi /quiet ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL=1 ENABLE_PSREMOTING=1 REGISTER_MANIFEST=1
```

<span data-ttu-id="59946-138">Полный список параметров командной строки для `Msiexec.exe` см. [здесь](/windows/desktop/Msi/command-line-options).</span><span class="sxs-lookup"><span data-stu-id="59946-138">For a full list of command-line options for `Msiexec.exe`, see [Command line options](/windows/desktop/Msi/command-line-options).</span></span>

### <a name="registry-keys-created-during-installation"></a><span data-ttu-id="59946-139">Разделы реестра, созданные во время установки</span><span class="sxs-lookup"><span data-stu-id="59946-139">Registry keys created during installation</span></span>

<span data-ttu-id="59946-140">Начиная с версии PowerShell 7.1, пакет MSI создает разделы реестра, которые хранят данные о расположении установки и версии PowerShell.</span><span class="sxs-lookup"><span data-stu-id="59946-140">Beginning in PowerShell 7.1, the MSI package creates registry keys that store the installation location and version of PowerShell.</span></span> <span data-ttu-id="59946-141">Эти значения можно найти в разделе `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\<GUID>`.</span><span class="sxs-lookup"><span data-stu-id="59946-141">These values are located in `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\<GUID>`.</span></span> <span data-ttu-id="59946-142">Значение `<GUID>` уникально для каждого типа сборки (выпуск или предварительная версия), основного номера версии и архитектуры.</span><span class="sxs-lookup"><span data-stu-id="59946-142">The value of `<GUID>` is unique for each build type (release or preview), major version, and architecture.</span></span>

|    <span data-ttu-id="59946-143">Release</span><span class="sxs-lookup"><span data-stu-id="59946-143">Release</span></span>    | <span data-ttu-id="59946-144">Architecture</span><span class="sxs-lookup"><span data-stu-id="59946-144">Architecture</span></span> |                                          <span data-ttu-id="59946-145">Ключ реестра</span><span class="sxs-lookup"><span data-stu-id="59946-145">Registry Key</span></span>                                           |
| ------------- | :----------: | ----------------------------------------------------------------------------------------------- |
| <span data-ttu-id="59946-146">Выпуск версии 7.1.x</span><span class="sxs-lookup"><span data-stu-id="59946-146">7.1.x Release</span></span> |     <span data-ttu-id="59946-147">x86</span><span class="sxs-lookup"><span data-stu-id="59946-147">x86</span></span>      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\1d00683b-0f84-4db8-a64f-2f98ad42fe06` |
| <span data-ttu-id="59946-148">Выпуск версии 7.1.x</span><span class="sxs-lookup"><span data-stu-id="59946-148">7.1.x Release</span></span> |     <span data-ttu-id="59946-149">X64</span><span class="sxs-lookup"><span data-stu-id="59946-149">x64</span></span>      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\31ab5147-9a97-4452-8443-d9709f0516e1` |
| <span data-ttu-id="59946-150">Предварительная версия 7.1.x</span><span class="sxs-lookup"><span data-stu-id="59946-150">7.1.x Preview</span></span> |     <span data-ttu-id="59946-151">x86</span><span class="sxs-lookup"><span data-stu-id="59946-151">x86</span></span>      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\86abcfbd-1ccc-4a88-b8b2-0facfde29094` |
| <span data-ttu-id="59946-152">Предварительная версия 7.1.x</span><span class="sxs-lookup"><span data-stu-id="59946-152">7.1.x Preview</span></span> |     <span data-ttu-id="59946-153">X64</span><span class="sxs-lookup"><span data-stu-id="59946-153">x64</span></span>      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\39243d76-adaf-42b1-94fb-16ecf83237c8` |

<span data-ttu-id="59946-154">Может использоваться администраторами и разработчиками для поиска пути к PowerShell.</span><span class="sxs-lookup"><span data-stu-id="59946-154">This can be used by administrators and developers to find the path to PowerShell.</span></span> <span data-ttu-id="59946-155">Значения `<GUID>` будут одинаковыми для всех выпусков предварительных и дополнительных версий.</span><span class="sxs-lookup"><span data-stu-id="59946-155">The `<GUID>` values will be the same for all preview and minor version releases.</span></span> <span data-ttu-id="59946-156">Значения `<GUID>` отличаются для каждого выпуска основной версии.</span><span class="sxs-lookup"><span data-stu-id="59946-156">The `<GUID>` values are changed for each major release.</span></span>

## <a name="installing-the-msix-package"></a><span data-ttu-id="59946-157"><a id="msix" />Установка пакета MSIX</span><span class="sxs-lookup"><span data-stu-id="59946-157"><a id="msix" />Installing the MSIX package</span></span>

> [!NOTE]
> <span data-ttu-id="59946-158">В настоящее время пакет MSIX не поддерживается официально.</span><span class="sxs-lookup"><span data-stu-id="59946-158">The MSIX package is not officially supported at this time.</span></span> <span data-ttu-id="59946-159">Но мы будем и дальше работать над этим продуктом, используемым только для внутреннего тестирования.</span><span class="sxs-lookup"><span data-stu-id="59946-159">We continue to build the package for internal testing purposes only.</span></span>

<span data-ttu-id="59946-160">Чтобы вручную установить пакет MSIX на клиенте Windows 10, скачайте пакет MSIX на странице [выпуски][выпуски] в GitHub.</span><span class="sxs-lookup"><span data-stu-id="59946-160">To manually install the MSIX package on a Windows 10 client, download the MSIX package from our GitHub [releases][releases] page.</span></span> <span data-ttu-id="59946-161">Прокрутите вниз до раздела **Ресурсы** в выпуске, который вы хотите установить.</span><span class="sxs-lookup"><span data-stu-id="59946-161">Scroll down to the **Assets** section of the Release you want to install.</span></span> <span data-ttu-id="59946-162">Раздел "Ресурсы" может быть свернут. В таком случае щелкните его, чтобы развернуть.</span><span class="sxs-lookup"><span data-stu-id="59946-162">The Assets section may be collapsed, so you may need to click to expand it.</span></span>

<span data-ttu-id="59946-163">MSIX-файл выглядит примерно так: `PowerShell-<version>-win-<os-arch>.msix`</span><span class="sxs-lookup"><span data-stu-id="59946-163">The MSIX file looks like this - `PowerShell-<version>-win-<os-arch>.msix`</span></span>

<span data-ttu-id="59946-164">Для установки пакета необходимо использовать командлет `Add-AppxPackage`.</span><span class="sxs-lookup"><span data-stu-id="59946-164">To install the package, you must use the `Add-AppxPackage` cmdlet.</span></span>

```powershell
Add-AppxPackage PowerShell-<version>-win-<os-arch>.msix
```

## <a name="installing-the-zip-package"></a><span data-ttu-id="59946-165"><a id="zip" />Установка ZIP-пакета</span><span class="sxs-lookup"><span data-stu-id="59946-165"><a id="zip" />Installing the ZIP package</span></span>

<span data-ttu-id="59946-166">Для поддержки расширенных сценариев развертывания доступны ZIP-архивы двоичных файлов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="59946-166">PowerShell binary ZIP archives are provided to enable advanced deployment scenarios.</span></span> <span data-ttu-id="59946-167">Скачайте один из следующих ZIP-архивов на странице [выпуски][выпуски].</span><span class="sxs-lookup"><span data-stu-id="59946-167">Download one of the following ZIP archives from the [releases][releases] page.</span></span>

- <span data-ttu-id="59946-168">PowerShell-7.0.3-win-x64.zip</span><span class="sxs-lookup"><span data-stu-id="59946-168">PowerShell-7.0.3-win-x64.zip</span></span>
- <span data-ttu-id="59946-169">PowerShell-7.0.3-win-x86.zip</span><span class="sxs-lookup"><span data-stu-id="59946-169">PowerShell-7.0.3-win-x86.zip</span></span>
- <span data-ttu-id="59946-170">PowerShell-7.0.3-win-arm64.zip</span><span class="sxs-lookup"><span data-stu-id="59946-170">PowerShell-7.0.3-win-arm64.zip</span></span>
- <span data-ttu-id="59946-171">PowerShell-7.0.3-win-arm32.zip</span><span class="sxs-lookup"><span data-stu-id="59946-171">PowerShell-7.0.3-win-arm32.zip</span></span>

<span data-ttu-id="59946-172">В зависимости от способа загрузки файла может потребоваться разблокировать файл с помощью командлета `Unblock-File`.</span><span class="sxs-lookup"><span data-stu-id="59946-172">Depending on how you download the file you may need to unblock the file using the `Unblock-File` cmdlet.</span></span> <span data-ttu-id="59946-173">Распакуйте содержимое в выбранное расположение и запустите `pwsh.exe`.</span><span class="sxs-lookup"><span data-stu-id="59946-173">Unzip the contents to the location of your choice and run `pwsh.exe` from there.</span></span> <span data-ttu-id="59946-174">В отличие от установки пакетов MSI при установке ZIP-архива не выполняется проверка соответствия предварительным требованиям.</span><span class="sxs-lookup"><span data-stu-id="59946-174">Unlike installing the MSI packages, installing the ZIP archive doesn't check for prerequisites.</span></span> <span data-ttu-id="59946-175">Для правильного удаленного взаимодействия с помощью WSMan необходимо обеспечить соответствие [предварительным требованиям](#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="59946-175">For remoting over WSMan to work properly, ensure that you've met the [prerequisites](#prerequisites).</span></span>

<span data-ttu-id="59946-176">Используйте этот метод для установки версии PowerShell на основе ARM на таких компьютерах, как Microsoft Surface Pro X. Чтобы получить оптимальные результаты, устанавливайте PowerShell в папку `$env:ProgramFiles\PowerShell\7`.</span><span class="sxs-lookup"><span data-stu-id="59946-176">Use this method to install the ARM-based version of PowerShell on computers like the Microsoft Surface Pro X. For best results, install PowerShell to the to `$env:ProgramFiles\PowerShell\7` folder.</span></span>

## <a name="deploying-on-windows-10-iot-enterprise"></a><span data-ttu-id="59946-177">Развертывание в Windows 10 IoT Корпоративная</span><span class="sxs-lookup"><span data-stu-id="59946-177">Deploying on Windows 10 IoT Enterprise</span></span>

<span data-ttu-id="59946-178">Windows 10 IoT Корпоративная поставляется со средой Windows PowerShell, которую можно использовать для развертывания PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="59946-178">Windows 10 IoT Enterprise comes with Windows PowerShell, which we can use to deploy PowerShell 7.</span></span>

1. <span data-ttu-id="59946-179">Создайте `PSSession` для целевого устройства</span><span class="sxs-lookup"><span data-stu-id="59946-179">Create `PSSession` to target device</span></span>

   ```powershell
   Set-Item -Path WSMan:\localhost\Client\TrustedHosts <deviceip>
   $S = New-PSSession -ComputerName <deviceIp> -Credential Administrator
   ```

1. <span data-ttu-id="59946-180">Скопируйте ZIP-файл на устройство</span><span class="sxs-lookup"><span data-stu-id="59946-180">Copy the ZIP package to the device</span></span>

   ```powershell
   # change the destination to however you had partitioned it with sufficient
   # space for the zip and the unzipped contents
   # the path should be local to the device
   Copy-Item .\PowerShell-<version>-win-<os-arch>.zip -Destination u:\users\administrator\Downloads -ToSession $s
   ```

1. <span data-ttu-id="59946-181">Присоединитесь к устройству и извлеките архив</span><span class="sxs-lookup"><span data-stu-id="59946-181">Connect to the device and expand the archive</span></span>

   ```powershell
   Enter-PSSession $s
   Set-Location u:\users\administrator\downloads
   Expand-Archive .\PowerShell-<version>-win-<os-arch>.zip
   ```

1. <span data-ttu-id="59946-182">Настройте удаленное взаимодействие с PowerShell 7</span><span class="sxs-lookup"><span data-stu-id="59946-182">Set up remoting to PowerShell 7</span></span>

   ```powershell
   Set-Location .\PowerShell-<version>-win-<os-arch>
   # Be sure to use the -PowerShellHome parameter otherwise it'll try to create a new
   # endpoint with Windows PowerShell 5.1
   .\Install-PowerShellRemoting.ps1 -PowerShellHome .
   # You'll get an error message and will be disconnected from the device because
   # it has to restart WinRM
   ```

1. <span data-ttu-id="59946-183">Подключение к конечной точке PowerShell 7 на устройстве</span><span class="sxs-lookup"><span data-stu-id="59946-183">Connect to PowerShell 7 endpoint on device</span></span>

   ```powershell
   # Be sure to use the -Configuration parameter. If you omit it, you will connect to Windows PowerShell 5.1
   Enter-PSSession -ComputerName <deviceIp> -Credential Administrator -Configuration powershell.<version>
   ```

## <a name="deploying-on-windows-10-iot-core"></a><span data-ttu-id="59946-184">Развертывание в Windows 10 IoT Базовая</span><span class="sxs-lookup"><span data-stu-id="59946-184">Deploying on Windows 10 IoT Core</span></span>

<span data-ttu-id="59946-185">Windows PowerShell добавляется в Windows 10 IoT Базовая, если вы включаете функцию _IOT_POWERSHELL_ , которую можно использовать для развертывания PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="59946-185">Windows 10 IoT Core adds Windows PowerShell when you include _IOT_POWERSHELL_ feature, which we can use to deploy PowerShell 7.</span></span> <span data-ttu-id="59946-186">Действия, описанные выше для Windows 10 IoT Корпоративная, могут быть выполнены и для центра Интернета вещей.</span><span class="sxs-lookup"><span data-stu-id="59946-186">The steps defined above for Windows 10 IoT Enterprise can be followed for IoT Core as well.</span></span>

<span data-ttu-id="59946-187">Чтобы добавить последнюю версию PowerShell в образ для доставки, используйте команду [Import-PSCoreRelease][] для включения пакета в рабочую область и добавления _OPENSRC_POWERSHELL_ в образ.</span><span class="sxs-lookup"><span data-stu-id="59946-187">For adding the latest PowerShell in the shipping image, use [Import-PSCoreRelease][] command to include the package in the workarea and add _OPENSRC_POWERSHELL_ feature to your image.</span></span>

> [!NOTE]
> <span data-ttu-id="59946-188">В архитектуре ARM64 Windows PowerShell не добавляется при включении _IOT_POWERSHELL_.</span><span class="sxs-lookup"><span data-stu-id="59946-188">For ARM64 architecture, Windows PowerShell is not added when you include _IOT_POWERSHELL_.</span></span> <span data-ttu-id="59946-189">Поэтому установка на основе ZIP-файла не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="59946-189">So the zip based install will not work.</span></span> <span data-ttu-id="59946-190">Для добавления в образ используйте команду `Import-PSCoreRelease`.</span><span class="sxs-lookup"><span data-stu-id="59946-190">You will need to use `Import-PSCoreRelease` command to add it in the image.</span></span>

## <a name="deploying-on-nano-server"></a><span data-ttu-id="59946-191">Развертывание на Nano Server</span><span class="sxs-lookup"><span data-stu-id="59946-191">Deploying on Nano Server</span></span>

<span data-ttu-id="59946-192">В этих указаниях предполагается, что Nano Server — это операционная система для удаленного управления, в которой уже работает какая-либо версия PowerShell.</span><span class="sxs-lookup"><span data-stu-id="59946-192">These instructions assume that the Nano Server is a "headless" OS that has a version of PowerShell is already running on it.</span></span> <span data-ttu-id="59946-193">Дополнительные сведения см. в разделе о [средстве создания образов Nano Server](/windows-server/get-started/deploy-nano-server).</span><span class="sxs-lookup"><span data-stu-id="59946-193">For more information, see the [Nano Server Image Builder](/windows-server/get-started/deploy-nano-server) documentation.</span></span>

<span data-ttu-id="59946-194">Двоичные файлы PowerShell можно развернуть двумя разными способами:</span><span class="sxs-lookup"><span data-stu-id="59946-194">PowerShell binaries can be deployed using two different methods.</span></span>

1. <span data-ttu-id="59946-195">Автономно — подключите виртуальный жесткий диск Nano Server и распакуйте содержимое ZIP-файла в выбранное расположение в этом образе.</span><span class="sxs-lookup"><span data-stu-id="59946-195">Offline - Mount the Nano Server VHD and unzip the contents of the zip file to your chosen location within the mounted image.</span></span>
1. <span data-ttu-id="59946-196">В сети — передайте ZIP-файл через сеанс PowerShell и распакуйте его в выбранное расположение.</span><span class="sxs-lookup"><span data-stu-id="59946-196">Online - Transfer the zip file over a PowerShell Session and unzip it in your chosen location.</span></span>

<span data-ttu-id="59946-197">В обоих случаях требуется ZIP-пакет выпуска Windows 10 семейства x64.</span><span class="sxs-lookup"><span data-stu-id="59946-197">In both cases, you need the Windows 10 x64 ZIP release package.</span></span> <span data-ttu-id="59946-198">Выполните команды в экземпляре PowerShell с ролью администратора.</span><span class="sxs-lookup"><span data-stu-id="59946-198">Run the commands within an "Administrator" instance of PowerShell.</span></span>

### <a name="offline-deployment-of-powershell"></a><span data-ttu-id="59946-199">Автономное развертывание PowerShell</span><span class="sxs-lookup"><span data-stu-id="59946-199">Offline Deployment of PowerShell</span></span>

1. <span data-ttu-id="59946-200">С помощью любой служебной программы ZIP распакуйте пакет в каталог, находящийся внутри подключенного образа Nano Server.</span><span class="sxs-lookup"><span data-stu-id="59946-200">Use your favorite zip utility to unzip the package to a directory within the mounted Nano Server image.</span></span>
1. <span data-ttu-id="59946-201">Отключите образ и загрузите его.</span><span class="sxs-lookup"><span data-stu-id="59946-201">Unmount the image and boot it.</span></span>
1. <span data-ttu-id="59946-202">Подключитесь к встроенному экземпляру Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="59946-202">Connect to the built-in instance of Windows PowerShell.</span></span>
1. <span data-ttu-id="59946-203">Следуйте инструкциям, чтобы создать конечную точку удаленного взаимодействия с помощью [методики использования другого экземпляра][].</span><span class="sxs-lookup"><span data-stu-id="59946-203">Follow the instructions to create a remoting endpoint using the ["another instance technique"][].</span></span>

### <a name="online-deployment-of-powershell"></a><span data-ttu-id="59946-204">Автономное PowerShell в сети</span><span class="sxs-lookup"><span data-stu-id="59946-204">Online Deployment of PowerShell</span></span>

<span data-ttu-id="59946-205">Разверните PowerShell в Nano Server, выполнив действия ниже.</span><span class="sxs-lookup"><span data-stu-id="59946-205">Deploy PowerShell to Nano Server using the following steps.</span></span>

- <span data-ttu-id="59946-206">Подключитесь к встроенному экземпляру Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="59946-206">Connect to the built-in instance of Windows PowerShell</span></span>

  ```powershell
  $session = New-PSSession -ComputerName <Nano Server IP address> -Credential <An Administrator account on the system>
  ```

- <span data-ttu-id="59946-207">Скопируйте файл на экземпляр Nano Server:</span><span class="sxs-lookup"><span data-stu-id="59946-207">Copy the file to the Nano Server instance</span></span>

  ```powershell
  Copy-Item <local PS Core download location>\powershell-<version>-win-x64.zip c:\ -ToSession $session
  ```

- <span data-ttu-id="59946-208">Войдите в сеанс:</span><span class="sxs-lookup"><span data-stu-id="59946-208">Enter the session</span></span>

  ```powershell
  Enter-PSSession $session
  ```

- <span data-ttu-id="59946-209">Извлеките ZIP-файл</span><span class="sxs-lookup"><span data-stu-id="59946-209">Extract the ZIP file</span></span>

  ```powershell
  # Insert the appropriate version.
  Expand-Archive -Path C:\powershell-<version>-win-x64.zip -DestinationPath "C:\PowerShell_<version>"
  ```

- <span data-ttu-id="59946-210">Если вам требуется удаленное взаимодействие на основе WSMan, следуйте инструкциям, чтобы создать конечную точку удаленного взаимодействия с помощью [методики использования другого экземпляра][].</span><span class="sxs-lookup"><span data-stu-id="59946-210">If you want WSMan-based remoting, follow the instructions to create a remoting endpoint using the ["another instance technique"][].</span></span>

## <a name="install-as-a-net-global-tool"></a><span data-ttu-id="59946-211">Установка в качестве глобального средства .NET</span><span class="sxs-lookup"><span data-stu-id="59946-211">Install as a .NET Global tool</span></span>

<span data-ttu-id="59946-212">Если вы уже установили [пакет SDK для .NET Core](/dotnet/core/sdk), установите PowerShell как [глобальное средство .NET](/dotnet/core/tools/global-tools).</span><span class="sxs-lookup"><span data-stu-id="59946-212">If you already have the [.NET Core SDK](/dotnet/core/sdk) installed, it's easy to install PowerShell as a [.NET Global tool](/dotnet/core/tools/global-tools).</span></span>

```
dotnet tool install --global PowerShell
```

<span data-ttu-id="59946-213">Установщик инструмента dotnet добавляет `$env:USERPROFILE\dotnet\tools` в переменную среды `$env:PATH`.</span><span class="sxs-lookup"><span data-stu-id="59946-213">The dotnet tool installer adds `$env:USERPROFILE\dotnet\tools` to your `$env:PATH` environment variable.</span></span> <span data-ttu-id="59946-214">Но в выполняющейся оболочке нет обновленной переменной `$env:PATH`.</span><span class="sxs-lookup"><span data-stu-id="59946-214">However, the currently running shell doesn't have the updated `$env:PATH`.</span></span> <span data-ttu-id="59946-215">Вы можете запустить PowerShell из новой оболочки, введя `pwsh`.</span><span class="sxs-lookup"><span data-stu-id="59946-215">You can start PowerShell from a new shell by typing `pwsh`.</span></span>

## <a name="install-powershell-via-winget"></a><span data-ttu-id="59946-216">Установка PowerShell через Winget</span><span class="sxs-lookup"><span data-stu-id="59946-216">Install PowerShell via Winget</span></span>

<span data-ttu-id="59946-217">Программа командной строки `winget` позволяет разработчикам обнаруживать, устанавливать, обновлять, удалять и настраивать приложения на компьютерах Windows 10.</span><span class="sxs-lookup"><span data-stu-id="59946-217">The `winget` command-line tool enables developers to discover, install, upgrade, remove, and configure applications on Windows 10 computers.</span></span> <span data-ttu-id="59946-218">Она является клиентским интерфейсом для службы Диспетчера пакетов Windows.</span><span class="sxs-lookup"><span data-stu-id="59946-218">This tool is the client interface to the Windows Package Manager service.</span></span>

> [!NOTE]
> <span data-ttu-id="59946-219">В настоящее время инструмент `winget` предоставляется в предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="59946-219">The `winget` tool is currently a preview.</span></span> <span data-ttu-id="59946-220">Сейчас доступны не все запланированные функции.</span><span class="sxs-lookup"><span data-stu-id="59946-220">Not all planned functionality is available at this time.</span></span>
> <span data-ttu-id="59946-221">Не используйте этот метод в сценарии развертывания в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="59946-221">You should not use this method in a production deployment scenario.</span></span> <span data-ttu-id="59946-222">Список системных требований и инструкции по установке см. в документации по [winget].</span><span class="sxs-lookup"><span data-stu-id="59946-222">See the [winget] documentation for a list of system requirements and install instructions.</span></span>

<span data-ttu-id="59946-223">Для установки PowerShell с помощью опубликованных пакетов `winget` можно использовать следующие команды:</span><span class="sxs-lookup"><span data-stu-id="59946-223">The following commands can be used to install PowerShell using the published `winget` packages:</span></span>

1. <span data-ttu-id="59946-224">Найдите последнюю версию PowerShell.</span><span class="sxs-lookup"><span data-stu-id="59946-224">Search for the latest version of PowerShell</span></span>

   ```powershell
   winget search Microsoft.PowerShell
   ```

   ```Output
   Name               Id                           Version
   ---------------------------------------------------------------
   PowerShell         Microsoft.PowerShell         7.0.3
   PowerShell-Preview Microsoft.PowerShell-Preview 7.1.0-preview.5
   ```

1. <span data-ttu-id="59946-225">Установите версию PowerShell, используя параметр `--exact`.</span><span class="sxs-lookup"><span data-stu-id="59946-225">Install a version of PowerShell using the `--exact` parameter</span></span>

   ```powershell
   winget install --name PowerShell --exact
   winget install --name PowerShell-Preview --exact
   ```

## <a name="how-to-create-a-remoting-endpoint"></a><span data-ttu-id="59946-226">Создание конечной точки удаленного взаимодействия</span><span class="sxs-lookup"><span data-stu-id="59946-226">How to create a remoting endpoint</span></span>

<span data-ttu-id="59946-227">PowerShell поддерживает протокол удаленного взаимодействия PowerShell (PSRP) через SSH и WSMan.</span><span class="sxs-lookup"><span data-stu-id="59946-227">PowerShell supports the PowerShell Remoting Protocol (PSRP) over both WSMan and SSH.</span></span> <span data-ttu-id="59946-228">Дополнительные сведения см. в разделе:</span><span class="sxs-lookup"><span data-stu-id="59946-228">For more information, see:</span></span>

- <span data-ttu-id="59946-229">[Удаленное взаимодействие через SSH в PowerShell Core][ssh-remoting]</span><span class="sxs-lookup"><span data-stu-id="59946-229">[SSH Remoting in PowerShell Core][ssh-remoting]</span></span>
- <span data-ttu-id="59946-230">[Удаленное взаимодействие через WSMan в PowerShell Core][wsman-remoting]</span><span class="sxs-lookup"><span data-stu-id="59946-230">[WSMan Remoting in PowerShell Core][wsman-remoting]</span></span>

## <a name="upgrading-an-existing-installation"></a><span data-ttu-id="59946-231">Обновление существующей установки</span><span class="sxs-lookup"><span data-stu-id="59946-231">Upgrading an existing installation</span></span>

<span data-ttu-id="59946-232">Для получения оптимального результата при обновлении используйте тот же метод установки, который вы использовали при первой установке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="59946-232">For best results when upgrading, you should use the same install method you used when you first installed PowerShell.</span></span> <span data-ttu-id="59946-233">При использовании разных методов установки PowerShell устанавливается в разные расположения.</span><span class="sxs-lookup"><span data-stu-id="59946-233">Each installation method installs PowerShell in a different location.</span></span> <span data-ttu-id="59946-234">Если вы не знаете, как была выполнена установка PowerShell, вы можете сравнить расположение установки со сведениями о пакетах из этой статьи.</span><span class="sxs-lookup"><span data-stu-id="59946-234">If you are not sure how PowerShell was installed, you can compare the installed location with the package information in this article.</span></span> <span data-ttu-id="59946-235">Если установка выполнена с помощью пакета MSI, эти сведения будут отображаться в разделе **Программы и компоненты** Панели управления.</span><span class="sxs-lookup"><span data-stu-id="59946-235">If you installed via the MSI package, that information appears in the **Programs and Features** Control Panel.</span></span>

## <a name="installation-support"></a><span data-ttu-id="59946-236">Поддержка установки</span><span class="sxs-lookup"><span data-stu-id="59946-236">Installation support</span></span>

<span data-ttu-id="59946-237">Корпорация Майкрософт поддерживает методы установки, изложенные в этом документе.</span><span class="sxs-lookup"><span data-stu-id="59946-237">Microsoft supports the installation methods in this document.</span></span> <span data-ttu-id="59946-238">В других источниках могут быть доступны другие методы установки.</span><span class="sxs-lookup"><span data-stu-id="59946-238">There may be other methods of installation available from other sources.</span></span> <span data-ttu-id="59946-239">Хотя такие инструменты и методы могут работать, корпорация Майкрософт не поддерживает их.</span><span class="sxs-lookup"><span data-stu-id="59946-239">While those tools and methods may work, Microsoft cannot support those methods.</span></span>

<!-- link references -->

[выпусками]: https://github.com/PowerShell/PowerShell/releases
[releases]: https://github.com/PowerShell/PowerShell/releases
[Актуальная]: https://github.com/PowerShell/PowerShell/releases/latest
[latest]: https://github.com/PowerShell/PowerShell/releases/latest
[ssh-remoting]: ../learn/remoting/SSH-Remoting-in-PowerShell-Core.md
[wsman-remoting]: ../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md
[AppVeyor]: https://ci.appveyor.com/project/PowerShell/powershell
[winget]: /windows/package-manager/winget
["еще один метод экземпляра"]: ../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register
["another instance technique"]: ../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register
[Import-PSCoreRelease]: https://github.com/ms-iot/iot-adk-addonkit/blob/master/Tools/IoTCoreImaging/Docs/Import-PSCoreRelease.md#Import-PSCoreRelease
