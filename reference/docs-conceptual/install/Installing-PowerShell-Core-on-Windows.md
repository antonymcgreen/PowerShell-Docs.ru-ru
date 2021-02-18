---
title: Установка PowerShell в Windows
description: Сведения об установке PowerShell в Windows
ms.date: 02/02/2021
ms.openlocfilehash: 12dedfed8349d243d3f2988fd7cb69c4cfc276bb
ms.sourcegitcommit: 4f1c2fe700b8a0544c59e371eb7cfbc6d852b185
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/17/2021
ms.locfileid: "100563258"
---
# <a name="installing-powershell-on-windows"></a><span data-ttu-id="1b070-103">Установка PowerShell в Windows</span><span class="sxs-lookup"><span data-stu-id="1b070-103">Installing PowerShell on Windows</span></span>

<span data-ttu-id="1b070-104">Есть несколько способов установки PowerShell в Windows.</span><span class="sxs-lookup"><span data-stu-id="1b070-104">There are multiple ways to install PowerShell in Windows.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1b070-105">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="1b070-105">Prerequisites</span></span>

<span data-ttu-id="1b070-106">Последний выпуск PowerShell поддерживается в Windows 7 с пакетом обновления 1 (SP1), Windows Server 2008 R2 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="1b070-106">The latest release of PowerShell is supported on Windows 7 SP1, Server 2008 R2, and later versions.</span></span>

<span data-ttu-id="1b070-107">Чтобы включить удаленное взаимодействие PowerShell через WSMan, нужно выполнить следующие условия:</span><span class="sxs-lookup"><span data-stu-id="1b070-107">To enable PowerShell remoting over WSMan, the following prerequisites need to be met:</span></span>

- <span data-ttu-id="1b070-108">Установите [универсальную среду выполнения C](https://www.microsoft.com/download/details.aspx?id=50410) в Windows предшествующих Windows 10 версий.</span><span class="sxs-lookup"><span data-stu-id="1b070-108">Install the [Universal C Runtime](https://www.microsoft.com/download/details.aspx?id=50410) on Windows versions predating Windows 10.</span></span> <span data-ttu-id="1b070-109">Ее можно скачать самостоятельно или через Центр обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="1b070-109">It's available via direct download or Windows Update.</span></span> <span data-ttu-id="1b070-110">Этот пакет уже установлен в полностью исправленных системах.</span><span class="sxs-lookup"><span data-stu-id="1b070-110">Fully patched systems already have this package installed.</span></span>
- <span data-ttu-id="1b070-111">Установите Windows Management Framework (WMF) 4.0 или более поздней версии в Windows 7 и Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="1b070-111">Install the Windows Management Framework (WMF) 4.0 or newer on Windows 7 and Windows Server 2008 R2.</span></span> <span data-ttu-id="1b070-112">Подробные сведения о WMF см. в статье с [обзором WMF](/powershell/scripting/wmf/overview).</span><span class="sxs-lookup"><span data-stu-id="1b070-112">For more information about WMF, see [WMF Overview](/powershell/scripting/wmf/overview).</span></span>

## <a name="download-the-installer-package"></a><span data-ttu-id="1b070-113">Скачивание скрипта установщика</span><span class="sxs-lookup"><span data-stu-id="1b070-113">Download the installer package</span></span>

<span data-ttu-id="1b070-114">Чтобы установить PowerShell в Windows скачайте [актуальный][] пакет установки с GitHub.</span><span class="sxs-lookup"><span data-stu-id="1b070-114">To install PowerShell on Windows, download the [latest][] install package from GitHub.</span></span> <span data-ttu-id="1b070-115">Также доступна актуальная [предварительная версия][].</span><span class="sxs-lookup"><span data-stu-id="1b070-115">You can also find the latest [preview][] version.</span></span> <span data-ttu-id="1b070-116">Прокрутите страницу вниз до раздела **ресурсов**.</span><span class="sxs-lookup"><span data-stu-id="1b070-116">Scroll down to the **Assets** section of the Release page.</span></span> <span data-ttu-id="1b070-117">Раздел **ресурсов** может быть свернут. В таком случае щелкните его, чтобы развернуть.</span><span class="sxs-lookup"><span data-stu-id="1b070-117">The **Assets** section may be collapsed, so you may need to click to expand it.</span></span>

## <a name="installing-the-msi-package"></a><span data-ttu-id="1b070-118"><a id="msi" />Установка пакета MSI</span><span class="sxs-lookup"><span data-stu-id="1b070-118"><a id="msi" />Installing the MSI package</span></span>

<span data-ttu-id="1b070-119">MSI-файл выглядит примерно так: `PowerShell-<version>-win-<os-arch>.msi`.</span><span class="sxs-lookup"><span data-stu-id="1b070-119">The MSI file looks like `PowerShell-<version>-win-<os-arch>.msi`.</span></span> <span data-ttu-id="1b070-120">Пример:</span><span class="sxs-lookup"><span data-stu-id="1b070-120">For example:</span></span>

- `PowerShell-7.1.2-win-x64.msi`
- `PowerShell-7.1.2-win-x86.msi`

<span data-ttu-id="1b070-121">После скачивания дважды щелкните установщик и следуйте инструкциям на экране.</span><span class="sxs-lookup"><span data-stu-id="1b070-121">Once downloaded, double-click the installer and follow the prompts.</span></span>

<span data-ttu-id="1b070-122">Программа установки создает ярлык в меню Windows "Пуск".</span><span class="sxs-lookup"><span data-stu-id="1b070-122">The installer creates a shortcut in the Windows Start Menu.</span></span>

- <span data-ttu-id="1b070-123">По умолчанию пакет устанавливается в каталог `$env:ProgramFiles\PowerShell\<version>`.</span><span class="sxs-lookup"><span data-stu-id="1b070-123">By default the package is installed to `$env:ProgramFiles\PowerShell\<version>`</span></span>
- <span data-ttu-id="1b070-124">Вы можете запустить PowerShell с помощью меню "Пуск" или файла `$env:ProgramFiles\PowerShell\<version>\pwsh.exe`.</span><span class="sxs-lookup"><span data-stu-id="1b070-124">You can launch PowerShell via the Start Menu or `$env:ProgramFiles\PowerShell\<version>\pwsh.exe`</span></span>

> [!NOTE]
> <span data-ttu-id="1b070-125">PowerShell 7.1 устанавливается в новом каталоге и работает параллельно с Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="1b070-125">PowerShell 7.1 installs to a new directory and runs side-by-side with Windows PowerShell 5.1.</span></span>
> <span data-ttu-id="1b070-126">PowerShell 7.1 устанавливается как обновление на месте взамен PowerShell 6.x</span><span class="sxs-lookup"><span data-stu-id="1b070-126">PowerShell 7.1 is an in-place upgrade that replaces PowerShell 6.x.</span></span> <span data-ttu-id="1b070-127">или PowerShell 7.0.</span><span class="sxs-lookup"><span data-stu-id="1b070-127">or PowerShell 7.0.</span></span>
>
> - <span data-ttu-id="1b070-128">PowerShell 7.1 устанавливается в папке `$env:ProgramFiles\PowerShell\7`.</span><span class="sxs-lookup"><span data-stu-id="1b070-128">PowerShell 7.1 is installed to `$env:ProgramFiles\PowerShell\7`</span></span>
> - <span data-ttu-id="1b070-129">Папка `$env:ProgramFiles\PowerShell\7` добавляется в переменную `$env:PATH`.</span><span class="sxs-lookup"><span data-stu-id="1b070-129">The `$env:ProgramFiles\PowerShell\7` folder is added to `$env:PATH`</span></span>
> - <span data-ttu-id="1b070-130">Папка `$env:ProgramFiles\PowerShell\6` удалена.</span><span class="sxs-lookup"><span data-stu-id="1b070-130">The `$env:ProgramFiles\PowerShell\6` folder is deleted</span></span>
>
> <span data-ttu-id="1b070-131">Если вам нужно запустить PowerShell 7.1 параллельно с другими версиями, используйте метод [установки ZIP-архива](#zip), чтобы установить новую версию в другую папку.</span><span class="sxs-lookup"><span data-stu-id="1b070-131">If you need to run PowerShell 7.1 side-by-side with other versions, use the [ZIP install](#zip) method to install the other version to a different folder.</span></span>

### <a name="administrative-install-from-the-command-line"></a><span data-ttu-id="1b070-132">Установка администратором из командной строки</span><span class="sxs-lookup"><span data-stu-id="1b070-132">Administrative install from the command line</span></span>

<span data-ttu-id="1b070-133">MSI-пакеты можно устанавливать из командной строки, что позволяет администраторам развертывать их без взаимодействия с пользователем.</span><span class="sxs-lookup"><span data-stu-id="1b070-133">MSI packages can be installed from the command line allowing administrators to deploy packages without user interaction.</span></span> <span data-ttu-id="1b070-134">MSI-пакет включает в себя следующие свойства для управления параметрами установки:</span><span class="sxs-lookup"><span data-stu-id="1b070-134">The MSI package includes the following properties to control the installation options:</span></span>

- <span data-ttu-id="1b070-135">**ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL**. Это свойство позволяет добавлять пункт **Открыть PowerShell** в контекстное меню проводника.</span><span class="sxs-lookup"><span data-stu-id="1b070-135">**ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL** - This property controls the option for adding the **Open PowerShell** item to the context menu in Windows Explorer.</span></span>
- <span data-ttu-id="1b070-136">**ADD_FILE_CONTEXT_MENU_RUNPOWERSHELL**. Это свойство позволяет добавлять пункт **Выполнить с помощью PowerShell** в контекстное меню проводника Windows.</span><span class="sxs-lookup"><span data-stu-id="1b070-136">**ADD_FILE_CONTEXT_MENU_RUNPOWERSHELL** - This property controls the option for adding the **Run with PowerShell** item to the context menu in Windows Explorer.</span></span>
- <span data-ttu-id="1b070-137">**ENABLE_PSREMOTING**. Это свойство позволяет включать удаленное взаимодействие PowerShell во время установки.</span><span class="sxs-lookup"><span data-stu-id="1b070-137">**ENABLE_PSREMOTING** - This property controls the option for enabling PowerShell remoting during installation.</span></span>
- <span data-ttu-id="1b070-138">**REGISTER_MANIFEST**. Это свойство позволяет регистрировать манифест ведения журнала событий Windows.</span><span class="sxs-lookup"><span data-stu-id="1b070-138">**REGISTER_MANIFEST** - This property controls the option for registering the Windows Event Logging manifest.</span></span>

<span data-ttu-id="1b070-139">В следующих примерах показано, как выполнить автоматическую установку PowerShell со всеми включенными параметрами.</span><span class="sxs-lookup"><span data-stu-id="1b070-139">The following example shows how to silently install PowerShell with all the install options enabled.</span></span>

```powershell
msiexec.exe /package PowerShell-7.1.2-win-x64.msi /quiet ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL=1 ENABLE_PSREMOTING=1 REGISTER_MANIFEST=1
```

<span data-ttu-id="1b070-140">Полный список параметров командной строки для `Msiexec.exe` см. [здесь](/windows/desktop/Msi/command-line-options).</span><span class="sxs-lookup"><span data-stu-id="1b070-140">For a full list of command-line options for `Msiexec.exe`, see [Command line options](/windows/desktop/Msi/command-line-options).</span></span>

### <a name="registry-keys-created-during-installation"></a><span data-ttu-id="1b070-141">Разделы реестра, созданные во время установки</span><span class="sxs-lookup"><span data-stu-id="1b070-141">Registry keys created during installation</span></span>

<span data-ttu-id="1b070-142">Начиная с версии PowerShell 7.1, пакет MSI создает разделы реестра, которые хранят данные о расположении установки и версии PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1b070-142">Beginning in PowerShell 7.1, the MSI package creates registry keys that store the installation location and version of PowerShell.</span></span> <span data-ttu-id="1b070-143">Эти значения можно найти в разделе `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\<GUID>`.</span><span class="sxs-lookup"><span data-stu-id="1b070-143">These values are located in `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\<GUID>`.</span></span> <span data-ttu-id="1b070-144">Значение `<GUID>` уникально для каждого типа сборки (выпуск или предварительная версия), основного номера версии и архитектуры.</span><span class="sxs-lookup"><span data-stu-id="1b070-144">The value of `<GUID>` is unique for each build type (release or preview), major version, and architecture.</span></span>

|    <span data-ttu-id="1b070-145">Release</span><span class="sxs-lookup"><span data-stu-id="1b070-145">Release</span></span>    | <span data-ttu-id="1b070-146">Architecture</span><span class="sxs-lookup"><span data-stu-id="1b070-146">Architecture</span></span> |                                          <span data-ttu-id="1b070-147">Ключ реестра</span><span class="sxs-lookup"><span data-stu-id="1b070-147">Registry Key</span></span>                                           |
| ------------- | :----------: | ----------------------------------------------------------------------------------------------- |
| <span data-ttu-id="1b070-148">Выпуск версии 7.1.x</span><span class="sxs-lookup"><span data-stu-id="1b070-148">7.1.x Release</span></span> |     <span data-ttu-id="1b070-149">x86</span><span class="sxs-lookup"><span data-stu-id="1b070-149">x86</span></span>      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\1d00683b-0f84-4db8-a64f-2f98ad42fe06` |
| <span data-ttu-id="1b070-150">Выпуск версии 7.1.x</span><span class="sxs-lookup"><span data-stu-id="1b070-150">7.1.x Release</span></span> |     <span data-ttu-id="1b070-151">X64</span><span class="sxs-lookup"><span data-stu-id="1b070-151">x64</span></span>      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\31ab5147-9a97-4452-8443-d9709f0516e1` |
| <span data-ttu-id="1b070-152">Предварительная версия 7.1.x</span><span class="sxs-lookup"><span data-stu-id="1b070-152">7.1.x Preview</span></span> |     <span data-ttu-id="1b070-153">x86</span><span class="sxs-lookup"><span data-stu-id="1b070-153">x86</span></span>      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\86abcfbd-1ccc-4a88-b8b2-0facfde29094` |
| <span data-ttu-id="1b070-154">Предварительная версия 7.1.x</span><span class="sxs-lookup"><span data-stu-id="1b070-154">7.1.x Preview</span></span> |     <span data-ttu-id="1b070-155">X64</span><span class="sxs-lookup"><span data-stu-id="1b070-155">x64</span></span>      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\39243d76-adaf-42b1-94fb-16ecf83237c8` |

<span data-ttu-id="1b070-156">Может использоваться администраторами и разработчиками для поиска пути к PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1b070-156">This can be used by administrators and developers to find the path to PowerShell.</span></span> <span data-ttu-id="1b070-157">Значения `<GUID>` будут одинаковыми для всех выпусков предварительных и дополнительных версий.</span><span class="sxs-lookup"><span data-stu-id="1b070-157">The `<GUID>` values will be the same for all preview and minor version releases.</span></span> <span data-ttu-id="1b070-158">Значения `<GUID>` отличаются для каждого выпуска основной версии.</span><span class="sxs-lookup"><span data-stu-id="1b070-158">The `<GUID>` values are changed for each major release.</span></span>

## <a name="installing-the-zip-package"></a><span data-ttu-id="1b070-159"><a id="zip" />Установка ZIP-пакета</span><span class="sxs-lookup"><span data-stu-id="1b070-159"><a id="zip" />Installing the ZIP package</span></span>

<span data-ttu-id="1b070-160">Для поддержки расширенных сценариев развертывания доступны ZIP-архивы двоичных файлов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1b070-160">PowerShell binary ZIP archives are provided to enable advanced deployment scenarios.</span></span> <span data-ttu-id="1b070-161">Скачайте один из следующих ZIP-архивов на странице с [выпусками][выпуски].</span><span class="sxs-lookup"><span data-stu-id="1b070-161">Download one of the following ZIP archives from the [releases][releases] page.</span></span>

- <span data-ttu-id="1b070-162">PowerShell-7.1.2-win-x64.zip</span><span class="sxs-lookup"><span data-stu-id="1b070-162">PowerShell-7.1.2-win-x64.zip</span></span>
- <span data-ttu-id="1b070-163">PowerShell-7.1.2-win-x86.zip</span><span class="sxs-lookup"><span data-stu-id="1b070-163">PowerShell-7.1.2-win-x86.zip</span></span>
- <span data-ttu-id="1b070-164">PowerShell-7.1.2-win-arm64.zip</span><span class="sxs-lookup"><span data-stu-id="1b070-164">PowerShell-7.1.2-win-arm64.zip</span></span>
- <span data-ttu-id="1b070-165">PowerShell-7.1.2-win-arm32.zip</span><span class="sxs-lookup"><span data-stu-id="1b070-165">PowerShell-7.1.2-win-arm32.zip</span></span>

<span data-ttu-id="1b070-166">В зависимости от способа загрузки файла может потребоваться разблокировать файл с помощью командлета `Unblock-File`.</span><span class="sxs-lookup"><span data-stu-id="1b070-166">Depending on how you download the file you may need to unblock the file using the `Unblock-File` cmdlet.</span></span> <span data-ttu-id="1b070-167">Распакуйте содержимое в выбранное расположение и запустите `pwsh.exe`.</span><span class="sxs-lookup"><span data-stu-id="1b070-167">Unzip the contents to the location of your choice and run `pwsh.exe` from there.</span></span> <span data-ttu-id="1b070-168">В отличие от установки пакетов MSI при установке ZIP-архива не выполняется проверка соответствия предварительным требованиям.</span><span class="sxs-lookup"><span data-stu-id="1b070-168">Unlike installing the MSI packages, installing the ZIP archive doesn't check for prerequisites.</span></span> <span data-ttu-id="1b070-169">Для правильного удаленного взаимодействия с помощью WSMan необходимо обеспечить соответствие [предварительным требованиям](#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="1b070-169">For remoting over WSMan to work properly, ensure that you've met the [prerequisites](#prerequisites).</span></span>

<span data-ttu-id="1b070-170">Используйте этот метод для установки версии PowerShell на основе ARM на таких компьютерах, как Microsoft Surface Pro X. Чтобы получить оптимальные результаты, устанавливайте PowerShell в папку `$env:ProgramFiles\PowerShell\7`.</span><span class="sxs-lookup"><span data-stu-id="1b070-170">Use this method to install the ARM-based version of PowerShell on computers like the Microsoft Surface Pro X. For best results, install PowerShell to the to `$env:ProgramFiles\PowerShell\7` folder.</span></span>

## <a name="deploying-on-windows-10-iot-enterprise"></a><span data-ttu-id="1b070-171">Развертывание в Windows 10 IoT Корпоративная</span><span class="sxs-lookup"><span data-stu-id="1b070-171">Deploying on Windows 10 IoT Enterprise</span></span>

<span data-ttu-id="1b070-172">Windows 10 IoT Корпоративная поставляется со средой Windows PowerShell, которую можно использовать для развертывания PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="1b070-172">Windows 10 IoT Enterprise comes with Windows PowerShell, which we can use to deploy PowerShell 7.</span></span>

1. <span data-ttu-id="1b070-173">Создайте `PSSession` для целевого устройства</span><span class="sxs-lookup"><span data-stu-id="1b070-173">Create `PSSession` to target device</span></span>

   ```powershell
   Set-Item -Path WSMan:\localhost\Client\TrustedHosts <deviceip>
   $S = New-PSSession -ComputerName <deviceIp> -Credential Administrator
   ```

1. <span data-ttu-id="1b070-174">Скопируйте ZIP-файл на устройство</span><span class="sxs-lookup"><span data-stu-id="1b070-174">Copy the ZIP package to the device</span></span>

   ```powershell
   # change the destination to however you had partitioned it with sufficient
   # space for the zip and the unzipped contents
   # the path should be local to the device
   Copy-Item .\PowerShell-<version>-win-<os-arch>.zip -Destination u:\users\administrator\Downloads -ToSession $s
   ```

1. <span data-ttu-id="1b070-175">Присоединитесь к устройству и извлеките архив</span><span class="sxs-lookup"><span data-stu-id="1b070-175">Connect to the device and expand the archive</span></span>

   ```powershell
   Enter-PSSession $s
   Set-Location u:\users\administrator\downloads
   Expand-Archive .\PowerShell-<version>-win-<os-arch>.zip
   ```

1. <span data-ttu-id="1b070-176">Настройте удаленное взаимодействие с PowerShell 7</span><span class="sxs-lookup"><span data-stu-id="1b070-176">Set up remoting to PowerShell 7</span></span>

   ```powershell
   Set-Location .\PowerShell-<version>-win-<os-arch>
   # Be sure to use the -PowerShellHome parameter otherwise it'll try to create a new
   # endpoint with Windows PowerShell 5.1
   .\Install-PowerShellRemoting.ps1 -PowerShellHome .
   # You'll get an error message and will be disconnected from the device because
   # it has to restart WinRM
   ```

1. <span data-ttu-id="1b070-177">Подключение к конечной точке PowerShell 7 на устройстве</span><span class="sxs-lookup"><span data-stu-id="1b070-177">Connect to PowerShell 7 endpoint on device</span></span>

   ```powershell
   # Be sure to use the -Configuration parameter. If you omit it, you will connect to Windows PowerShell 5.1
   Enter-PSSession -ComputerName <deviceIp> -Credential Administrator -Configuration powershell.<version>
   ```

## <a name="deploying-on-windows-10-iot-core"></a><span data-ttu-id="1b070-178">Развертывание в Windows 10 IoT Базовая</span><span class="sxs-lookup"><span data-stu-id="1b070-178">Deploying on Windows 10 IoT Core</span></span>

<span data-ttu-id="1b070-179">Windows PowerShell добавляется в Windows 10 IoT Базовая, если вы включаете функцию _IOT_POWERSHELL_, которую можно использовать для развертывания PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="1b070-179">Windows 10 IoT Core adds Windows PowerShell when you include _IOT_POWERSHELL_ feature, which we can use to deploy PowerShell 7.</span></span> <span data-ttu-id="1b070-180">Действия, описанные выше для Windows 10 IoT Корпоративная, могут быть выполнены и для центра Интернета вещей.</span><span class="sxs-lookup"><span data-stu-id="1b070-180">The steps defined above for Windows 10 IoT Enterprise can be followed for IoT Core as well.</span></span>

<span data-ttu-id="1b070-181">Чтобы добавить последнюю версию PowerShell в образ для доставки, используйте команду [Import-PSCoreRelease][] для включения пакета в рабочую область и добавления _OPENSRC_POWERSHELL_ в образ.</span><span class="sxs-lookup"><span data-stu-id="1b070-181">For adding the latest PowerShell in the shipping image, use [Import-PSCoreRelease][] command to include the package in the workarea and add _OPENSRC_POWERSHELL_ feature to your image.</span></span>

> [!NOTE]
> <span data-ttu-id="1b070-182">В архитектуре ARM64 Windows PowerShell не добавляется при включении _IOT_POWERSHELL_.</span><span class="sxs-lookup"><span data-stu-id="1b070-182">For ARM64 architecture, Windows PowerShell is not added when you include _IOT_POWERSHELL_.</span></span> <span data-ttu-id="1b070-183">Поэтому установка на основе ZIP-файла не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="1b070-183">So the zip based install will not work.</span></span> <span data-ttu-id="1b070-184">Для добавления в образ используйте команду `Import-PSCoreRelease`.</span><span class="sxs-lookup"><span data-stu-id="1b070-184">You will need to use `Import-PSCoreRelease` command to add it in the image.</span></span>

## <a name="deploying-on-nano-server"></a><span data-ttu-id="1b070-185">Развертывание на Nano Server</span><span class="sxs-lookup"><span data-stu-id="1b070-185">Deploying on Nano Server</span></span>

<span data-ttu-id="1b070-186">В этих указаниях предполагается, что Nano Server — это операционная система для удаленного управления, в которой уже работает какая-либо версия PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1b070-186">These instructions assume that the Nano Server is a "headless" OS that has a version of PowerShell is already running on it.</span></span> <span data-ttu-id="1b070-187">Дополнительные сведения см. в разделе о [средстве создания образов Nano Server](/windows-server/get-started/deploy-nano-server).</span><span class="sxs-lookup"><span data-stu-id="1b070-187">For more information, see the [Nano Server Image Builder](/windows-server/get-started/deploy-nano-server) documentation.</span></span>

<span data-ttu-id="1b070-188">Двоичные файлы PowerShell можно развернуть двумя разными способами:</span><span class="sxs-lookup"><span data-stu-id="1b070-188">PowerShell binaries can be deployed using two different methods.</span></span>

1. <span data-ttu-id="1b070-189">Автономно — подключите виртуальный жесткий диск Nano Server и распакуйте содержимое ZIP-файла в выбранное расположение в этом образе.</span><span class="sxs-lookup"><span data-stu-id="1b070-189">Offline - Mount the Nano Server VHD and unzip the contents of the zip file to your chosen location within the mounted image.</span></span>
1. <span data-ttu-id="1b070-190">В сети — передайте ZIP-файл через сеанс PowerShell и распакуйте его в выбранное расположение.</span><span class="sxs-lookup"><span data-stu-id="1b070-190">Online - Transfer the zip file over a PowerShell Session and unzip it in your chosen location.</span></span>

<span data-ttu-id="1b070-191">В обоих случаях требуется ZIP-пакет выпуска Windows 10 семейства x64.</span><span class="sxs-lookup"><span data-stu-id="1b070-191">In both cases, you need the Windows 10 x64 ZIP release package.</span></span> <span data-ttu-id="1b070-192">Выполните команды в экземпляре PowerShell с ролью администратора.</span><span class="sxs-lookup"><span data-stu-id="1b070-192">Run the commands within an "Administrator" instance of PowerShell.</span></span>

### <a name="offline-deployment-of-powershell"></a><span data-ttu-id="1b070-193">Автономное развертывание PowerShell</span><span class="sxs-lookup"><span data-stu-id="1b070-193">Offline Deployment of PowerShell</span></span>

1. <span data-ttu-id="1b070-194">С помощью любой служебной программы ZIP распакуйте пакет в каталог, находящийся внутри подключенного образа Nano Server.</span><span class="sxs-lookup"><span data-stu-id="1b070-194">Use your favorite zip utility to unzip the package to a directory within the mounted Nano Server image.</span></span>
1. <span data-ttu-id="1b070-195">Отключите образ и загрузите его.</span><span class="sxs-lookup"><span data-stu-id="1b070-195">Unmount the image and boot it.</span></span>
1. <span data-ttu-id="1b070-196">Подключитесь к встроенному экземпляру Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1b070-196">Connect to the built-in instance of Windows PowerShell.</span></span>
1. <span data-ttu-id="1b070-197">Следуйте инструкциям, чтобы создать конечную точку удаленного взаимодействия с помощью [методики использования другого экземпляра][].</span><span class="sxs-lookup"><span data-stu-id="1b070-197">Follow the instructions to create a remoting endpoint using the ["another instance technique"][].</span></span>

### <a name="online-deployment-of-powershell"></a><span data-ttu-id="1b070-198">Автономное PowerShell в сети</span><span class="sxs-lookup"><span data-stu-id="1b070-198">Online Deployment of PowerShell</span></span>

<span data-ttu-id="1b070-199">Разверните PowerShell в Nano Server, выполнив действия ниже.</span><span class="sxs-lookup"><span data-stu-id="1b070-199">Deploy PowerShell to Nano Server using the following steps.</span></span>

- <span data-ttu-id="1b070-200">Подключитесь к встроенному экземпляру Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1b070-200">Connect to the built-in instance of Windows PowerShell</span></span>

  ```powershell
  $session = New-PSSession -ComputerName <Nano Server IP address> -Credential <An Administrator account on the system>
  ```

- <span data-ttu-id="1b070-201">Скопируйте файл на экземпляр Nano Server:</span><span class="sxs-lookup"><span data-stu-id="1b070-201">Copy the file to the Nano Server instance</span></span>

  ```powershell
  Copy-Item <local PS Core download location>\powershell-<version>-win-x64.zip c:\ -ToSession $session
  ```

- <span data-ttu-id="1b070-202">Войдите в сеанс:</span><span class="sxs-lookup"><span data-stu-id="1b070-202">Enter the session</span></span>

  ```powershell
  Enter-PSSession $session
  ```

- <span data-ttu-id="1b070-203">Извлеките ZIP-файл</span><span class="sxs-lookup"><span data-stu-id="1b070-203">Extract the ZIP file</span></span>

  ```powershell
  # Insert the appropriate version.
  Expand-Archive -Path C:\powershell-<version>-win-x64.zip -DestinationPath "C:\PowerShell_<version>"
  ```

- <span data-ttu-id="1b070-204">Если вам требуется удаленное взаимодействие на основе WSMan, следуйте инструкциям, чтобы создать конечную точку удаленного взаимодействия с помощью [методики использования другого экземпляра][].</span><span class="sxs-lookup"><span data-stu-id="1b070-204">If you want WSMan-based remoting, follow the instructions to create a remoting endpoint using the ["another instance technique"][].</span></span>

## <a name="install-as-a-net-global-tool"></a><span data-ttu-id="1b070-205">Установка в качестве глобального средства .NET</span><span class="sxs-lookup"><span data-stu-id="1b070-205">Install as a .NET Global tool</span></span>

<span data-ttu-id="1b070-206">Если вы уже установили [пакет SDK для .NET Core](/dotnet/core/sdk), установите PowerShell как [глобальное средство .NET](/dotnet/core/tools/global-tools).</span><span class="sxs-lookup"><span data-stu-id="1b070-206">If you already have the [.NET Core SDK](/dotnet/core/sdk) installed, it's easy to install PowerShell as a [.NET Global tool](/dotnet/core/tools/global-tools).</span></span>

```
dotnet tool install --global PowerShell
```

<span data-ttu-id="1b070-207">Установщик инструмента dotnet добавляет `$env:USERPROFILE\dotnet\tools` в переменную среды `$env:PATH`.</span><span class="sxs-lookup"><span data-stu-id="1b070-207">The dotnet tool installer adds `$env:USERPROFILE\dotnet\tools` to your `$env:PATH` environment variable.</span></span> <span data-ttu-id="1b070-208">Но в выполняющейся оболочке нет обновленной переменной `$env:PATH`.</span><span class="sxs-lookup"><span data-stu-id="1b070-208">However, the currently running shell doesn't have the updated `$env:PATH`.</span></span> <span data-ttu-id="1b070-209">Вы можете запустить PowerShell из новой оболочки, введя `pwsh`.</span><span class="sxs-lookup"><span data-stu-id="1b070-209">You can start PowerShell from a new shell by typing `pwsh`.</span></span>

## <a name="install-powershell-via-winget"></a><span data-ttu-id="1b070-210">Установка PowerShell через Winget</span><span class="sxs-lookup"><span data-stu-id="1b070-210">Install PowerShell via Winget</span></span>

<span data-ttu-id="1b070-211">Программа командной строки `winget` позволяет разработчикам обнаруживать, устанавливать, обновлять, удалять и настраивать приложения на компьютерах Windows 10.</span><span class="sxs-lookup"><span data-stu-id="1b070-211">The `winget` command-line tool enables developers to discover, install, upgrade, remove, and configure applications on Windows 10 computers.</span></span> <span data-ttu-id="1b070-212">Она является клиентским интерфейсом для службы Диспетчера пакетов Windows.</span><span class="sxs-lookup"><span data-stu-id="1b070-212">This tool is the client interface to the Windows Package Manager service.</span></span>

> [!NOTE]
> <span data-ttu-id="1b070-213">В настоящее время инструмент `winget` предоставляется в предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="1b070-213">The `winget` tool is currently a preview.</span></span> <span data-ttu-id="1b070-214">Сейчас доступны не все запланированные функции.</span><span class="sxs-lookup"><span data-stu-id="1b070-214">Not all planned functionality is available at this time.</span></span>
> <span data-ttu-id="1b070-215">Не используйте этот метод в сценарии развертывания в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="1b070-215">You should not use this method in a production deployment scenario.</span></span> <span data-ttu-id="1b070-216">Список системных требований и инструкции по установке см. в документации по [winget].</span><span class="sxs-lookup"><span data-stu-id="1b070-216">See the [winget] documentation for a list of system requirements and install instructions.</span></span>

<span data-ttu-id="1b070-217">Для установки PowerShell с помощью опубликованных пакетов `winget` можно использовать следующие команды:</span><span class="sxs-lookup"><span data-stu-id="1b070-217">The following commands can be used to install PowerShell using the published `winget` packages:</span></span>

1. <span data-ttu-id="1b070-218">Найдите последнюю версию PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1b070-218">Search for the latest version of PowerShell</span></span>

   ```powershell
   winget search Microsoft.PowerShell
   ```

   ```Output
   Name               Id                           Version
   ---------------------------------------------------------------
   PowerShell         Microsoft.PowerShell         7.1.2
   PowerShell-Preview Microsoft.PowerShell-Preview 7.1.2-preview.5
   ```

1. <span data-ttu-id="1b070-219">Установите версию PowerShell, используя параметр `--exact`.</span><span class="sxs-lookup"><span data-stu-id="1b070-219">Install a version of PowerShell using the `--exact` parameter</span></span>

   ```powershell
   winget install --name PowerShell --exact
   winget install --name PowerShell-Preview --exact
   ```

## <a name="installing-from-the-microsoft-store"></a><span data-ttu-id="1b070-220"><a id="msix" />Установка из Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="1b070-220"><a id="msix" />Installing from the Microsoft Store</span></span>

<span data-ttu-id="1b070-221">Версия PowerShell 7.1 опубликована в Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="1b070-221">PowerShell 7.1 has been published to the Microsoft Store.</span></span> <span data-ttu-id="1b070-222">Этот выпуск PowerShell можно найти на веб-сайте [Microsoft Store](https://www.microsoft.com/store/apps/9MZ1SNWT0N5D) или в приложении Store в ОС Windows.</span><span class="sxs-lookup"><span data-stu-id="1b070-222">You can find the PowerShell release on the [Microsoft Store](https://www.microsoft.com/store/apps/9MZ1SNWT0N5D) website or in the Store application in Windows.</span></span>

<span data-ttu-id="1b070-223">Пакет Microsoft Store обеспечивает следующие преимущества:</span><span class="sxs-lookup"><span data-stu-id="1b070-223">Benefits of the Microsoft Store package:</span></span>

- <span data-ttu-id="1b070-224">автоматические обновления, встроенные в основной механизм Windows 10;</span><span class="sxs-lookup"><span data-stu-id="1b070-224">Automatic updates built right into Windows 10</span></span>
- <span data-ttu-id="1b070-225">интеграция с другими механизмами распространения программного обеспечения, такими как Intune и SCCM.</span><span class="sxs-lookup"><span data-stu-id="1b070-225">Integrates with other software distribution mechanisms like Intune and SCCM</span></span>

<span data-ttu-id="1b070-226">Ограничения</span><span class="sxs-lookup"><span data-stu-id="1b070-226">Limitations:</span></span>

<span data-ttu-id="1b070-227">Пакеты MSIX выполняются в песочнице приложения, которая виртуализует доступ к некоторым расположениям в файловой системе и реестре.</span><span class="sxs-lookup"><span data-stu-id="1b070-227">MSIX packages run in an application sandbox that virtualizes access to some filesystem and registry locations.</span></span>

- <span data-ttu-id="1b070-228">Все изменения реестра в разделе HKEY_CURRENT_USER при записи копируются в закрытое хранилище, отдельно для каждого пользователя и приложения.</span><span class="sxs-lookup"><span data-stu-id="1b070-228">All registry changes under HKEY_CURRENT_USER are copied on write to a private, per-user, per-app location.</span></span> <span data-ttu-id="1b070-229">Таким образом, эти значения недоступны для других приложений.</span><span class="sxs-lookup"><span data-stu-id="1b070-229">Therefore, those values are not available to other applications.</span></span>
- <span data-ttu-id="1b070-230">Параметры конфигурации системного уровня, хранящиеся в `$PSHOME`, нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="1b070-230">Any system-level configuration settings stored in `$PSHOME` cannot be modified.</span></span> <span data-ttu-id="1b070-231">Это относится и к конфигурации WSMAN.</span><span class="sxs-lookup"><span data-stu-id="1b070-231">This includes the WSMAN configuration.</span></span> <span data-ttu-id="1b070-232">Это означает, что вы не сможете подключать удаленные сеансы к установкам PowerShell на основе хранилища.</span><span class="sxs-lookup"><span data-stu-id="1b070-232">This prevents remote sessions from connecting to Store-based installs of PowerShell.</span></span> <span data-ttu-id="1b070-233">Поддерживаются конфигурации уровня пользователя и удаленное взаимодействие по SSH.</span><span class="sxs-lookup"><span data-stu-id="1b070-233">User-level configurations and SSH remoting are supported.</span></span>

<span data-ttu-id="1b070-234">Подробнее см. [Основные сведения о работе упакованных классических приложений в Windows](/windows/msix/desktop/desktop-to-uwp-behind-the-scenes).</span><span class="sxs-lookup"><span data-stu-id="1b070-234">For more information, see [Understanding how packaged desktop apps run on Windows](/windows/msix/desktop/desktop-to-uwp-behind-the-scenes).</span></span>

### <a name="using-the-msix-package"></a><span data-ttu-id="1b070-235">Использование пакета MSIX</span><span class="sxs-lookup"><span data-stu-id="1b070-235">Using the MSIX package</span></span>

> [!NOTE]
> <span data-ttu-id="1b070-236">Предварительные сборки PowerShell включают пакет MSIX.</span><span class="sxs-lookup"><span data-stu-id="1b070-236">The preview builds of PowerShell include an MSIX package.</span></span> <span data-ttu-id="1b070-237">Пакет MSIX не поддерживается официально.</span><span class="sxs-lookup"><span data-stu-id="1b070-237">The MSIX package is not officially supported.</span></span> <span data-ttu-id="1b070-238">Этот пакет создан исключительно для тестовых целей и только на период действия предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="1b070-238">The package is built for testing purposes during the preview period.</span></span>

<span data-ttu-id="1b070-239">Чтобы вручную установить пакет MSIX на клиенте Windows 10, скачайте пакет MSIX на странице GitHub с [выпусками][выпуски].</span><span class="sxs-lookup"><span data-stu-id="1b070-239">To manually install the MSIX package on a Windows 10 client, download the MSIX package from our GitHub [releases][releases] page.</span></span> <span data-ttu-id="1b070-240">Прокрутите вниз до раздела **Ресурсы** в выпуске, который вы хотите установить.</span><span class="sxs-lookup"><span data-stu-id="1b070-240">Scroll down to the **Assets** section of the Release you want to install.</span></span> <span data-ttu-id="1b070-241">Раздел "Ресурсы" может быть свернут. В таком случае щелкните его, чтобы развернуть.</span><span class="sxs-lookup"><span data-stu-id="1b070-241">The Assets section may be collapsed, so you may need to click to expand it.</span></span>

<span data-ttu-id="1b070-242">MSIX-файл выглядит примерно так: `PowerShell-<version>-win-<os-arch>.msix`</span><span class="sxs-lookup"><span data-stu-id="1b070-242">The MSIX file looks like this - `PowerShell-<version>-win-<os-arch>.msix`</span></span>

<span data-ttu-id="1b070-243">Для установки пакета необходимо использовать командлет `Add-AppxPackage`.</span><span class="sxs-lookup"><span data-stu-id="1b070-243">To install the package, you must use the `Add-AppxPackage` cmdlet.</span></span>

```powershell
Add-AppxPackage PowerShell-<version>-win-<os-arch>.msix
```

## <a name="how-to-create-a-remoting-endpoint"></a><span data-ttu-id="1b070-244">Создание конечной точки удаленного взаимодействия</span><span class="sxs-lookup"><span data-stu-id="1b070-244">How to create a remoting endpoint</span></span>

<span data-ttu-id="1b070-245">PowerShell поддерживает протокол удаленного взаимодействия PowerShell (PSRP) через SSH и WSMan.</span><span class="sxs-lookup"><span data-stu-id="1b070-245">PowerShell supports the PowerShell Remoting Protocol (PSRP) over both WSMan and SSH.</span></span> <span data-ttu-id="1b070-246">Дополнительные сведения см. в разделе:</span><span class="sxs-lookup"><span data-stu-id="1b070-246">For more information, see:</span></span>

- <span data-ttu-id="1b070-247">[Удаленное взаимодействие через SSH в PowerShell Core][ssh-remoting]</span><span class="sxs-lookup"><span data-stu-id="1b070-247">[SSH Remoting in PowerShell Core][ssh-remoting]</span></span>
- <span data-ttu-id="1b070-248">[Удаленное взаимодействие через WSMan в PowerShell Core][wsman-remoting]</span><span class="sxs-lookup"><span data-stu-id="1b070-248">[WSMan Remoting in PowerShell Core][wsman-remoting]</span></span>

## <a name="upgrading-an-existing-installation"></a><span data-ttu-id="1b070-249">Обновление существующей установки</span><span class="sxs-lookup"><span data-stu-id="1b070-249">Upgrading an existing installation</span></span>

<span data-ttu-id="1b070-250">Для получения оптимального результата при обновлении используйте тот же метод установки, который вы использовали при первой установке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1b070-250">For best results when upgrading, you should use the same install method you used when you first installed PowerShell.</span></span> <span data-ttu-id="1b070-251">При использовании разных методов установки PowerShell устанавливается в разные расположения.</span><span class="sxs-lookup"><span data-stu-id="1b070-251">Each installation method installs PowerShell in a different location.</span></span> <span data-ttu-id="1b070-252">Если вы не знаете, как была выполнена установка PowerShell, вы можете сравнить расположение установки со сведениями о пакетах из этой статьи.</span><span class="sxs-lookup"><span data-stu-id="1b070-252">If you are not sure how PowerShell was installed, you can compare the installed location with the package information in this article.</span></span> <span data-ttu-id="1b070-253">Если установка выполнена с помощью пакета MSI, эти сведения будут отображаться в разделе **Программы и компоненты** Панели управления.</span><span class="sxs-lookup"><span data-stu-id="1b070-253">If you installed via the MSI package, that information appears in the **Programs and Features** Control Panel.</span></span>

## <a name="installation-support"></a><span data-ttu-id="1b070-254">Поддержка установки</span><span class="sxs-lookup"><span data-stu-id="1b070-254">Installation support</span></span>

<span data-ttu-id="1b070-255">Корпорация Майкрософт поддерживает методы установки, изложенные в этом документе.</span><span class="sxs-lookup"><span data-stu-id="1b070-255">Microsoft supports the installation methods in this document.</span></span> <span data-ttu-id="1b070-256">В других источниках могут быть доступны другие методы установки.</span><span class="sxs-lookup"><span data-stu-id="1b070-256">There may be other methods of installation available from other sources.</span></span> <span data-ttu-id="1b070-257">Хотя такие инструменты и методы могут работать, корпорация Майкрософт не поддерживает их.</span><span class="sxs-lookup"><span data-stu-id="1b070-257">While those tools and methods may work, Microsoft cannot support those methods.</span></span>

<!-- link references -->

[предварительная версия]: https://aka.ms/powershell-release?tag=preview
[preview]: https://aka.ms/powershell-release?tag=preview
[Актуальная]: https://aka.ms/powershell-release?tag=stable
[latest]: https://aka.ms/powershell-release?tag=stable
[ssh-remoting]: ../learn/remoting/SSH-Remoting-in-PowerShell-Core.md
[wsman-remoting]: ../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md
[AppVeyor]: https://ci.appveyor.com/project/PowerShell/powershell
[winget]: /windows/package-manager/winget
["еще один метод экземпляра"]: ../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register
["another instance technique"]: ../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register
[Import-PSCoreRelease]: https://github.com/ms-iot/iot-adk-addonkit/blob/master/Tools/IoTCoreImaging/Docs/Import-PSCoreRelease.md#Import-PSCoreRelease
