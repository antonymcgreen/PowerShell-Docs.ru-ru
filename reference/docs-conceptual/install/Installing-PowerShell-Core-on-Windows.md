---
title: Установка PowerShell в Windows
description: Сведения об установке PowerShell в Windows
ms.date: 11/11/2020
ms.openlocfilehash: 039db904a315bd3ad3f4e1358d414c98c3a84be5
ms.sourcegitcommit: 7f712e12ec5b3f3f3e695da804b050ea0ce58b3a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "94661432"
---
# <a name="installing-powershell-on-windows"></a><span data-ttu-id="f472f-103">Установка PowerShell в Windows</span><span class="sxs-lookup"><span data-stu-id="f472f-103">Installing PowerShell on Windows</span></span>

<span data-ttu-id="f472f-104">Есть несколько способов установки PowerShell в Windows.</span><span class="sxs-lookup"><span data-stu-id="f472f-104">There are multiple ways to install PowerShell in Windows.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f472f-105">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="f472f-105">Prerequisites</span></span>

<span data-ttu-id="f472f-106">Последний выпуск PowerShell поддерживается в Windows 7 с пакетом обновления 1 (SP1), Windows Server 2008 R2 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="f472f-106">The latest release of PowerShell is supported on Windows 7 SP1, Server 2008 R2, and later versions.</span></span>

<span data-ttu-id="f472f-107">Чтобы включить удаленное взаимодействие PowerShell через WSMan, нужно выполнить следующие условия:</span><span class="sxs-lookup"><span data-stu-id="f472f-107">To enable PowerShell remoting over WSMan, the following prerequisites need to be met:</span></span>

- <span data-ttu-id="f472f-108">Установите [универсальную среду выполнения C](https://www.microsoft.com/download/details.aspx?id=50410) в Windows предшествующих Windows 10 версий.</span><span class="sxs-lookup"><span data-stu-id="f472f-108">Install the [Universal C Runtime](https://www.microsoft.com/download/details.aspx?id=50410) on Windows versions predating Windows 10.</span></span> <span data-ttu-id="f472f-109">Ее можно скачать самостоятельно или через Центр обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="f472f-109">It's available via direct download or Windows Update.</span></span> <span data-ttu-id="f472f-110">Этот пакет уже установлен в полностью исправленных системах.</span><span class="sxs-lookup"><span data-stu-id="f472f-110">Fully patched systems already have this package installed.</span></span>
- <span data-ttu-id="f472f-111">Установите Windows Management Framework (WMF) 4.0 или более поздней версии в Windows 7 и Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="f472f-111">Install the Windows Management Framework (WMF) 4.0 or newer on Windows 7 and Windows Server 2008 R2.</span></span> <span data-ttu-id="f472f-112">Подробные сведения о WMF см. в статье с [обзором WMF](/powershell/scripting/wmf/overview).</span><span class="sxs-lookup"><span data-stu-id="f472f-112">For more information about WMF, see [WMF Overview](/powershell/scripting/wmf/overview).</span></span>

## <a name="download-the-installer-package"></a><span data-ttu-id="f472f-113">Скачивание скрипта установщика</span><span class="sxs-lookup"><span data-stu-id="f472f-113">Download the installer package</span></span>

<span data-ttu-id="f472f-114">Чтобы установить PowerShell в Windows скачайте [актуальный][] пакет установки с GitHub.</span><span class="sxs-lookup"><span data-stu-id="f472f-114">To install PowerShell on Windows, download the [latest][] install package from GitHub.</span></span> <span data-ttu-id="f472f-115">Также доступна актуальная предварительная версия на странице [выпуски][].</span><span class="sxs-lookup"><span data-stu-id="f472f-115">You can also find the latest preview version on the [releases][] page.</span></span> <span data-ttu-id="f472f-116">Прокрутите страницу вниз до раздела **ресурсов**.</span><span class="sxs-lookup"><span data-stu-id="f472f-116">Scroll down to the **Assets** section of the Release page.</span></span> <span data-ttu-id="f472f-117">Раздел **ресурсов** может быть свернут. В таком случае щелкните его, чтобы развернуть.</span><span class="sxs-lookup"><span data-stu-id="f472f-117">The **Assets** section may be collapsed, so you may need to click to expand it.</span></span>

## <a name="installing-the-msi-package"></a><span data-ttu-id="f472f-118"><a id="msi" />Установка пакета MSI</span><span class="sxs-lookup"><span data-stu-id="f472f-118"><a id="msi" />Installing the MSI package</span></span>

<span data-ttu-id="f472f-119">MSI-файл выглядит примерно так: `PowerShell-<version>-win-<os-arch>.msi`.</span><span class="sxs-lookup"><span data-stu-id="f472f-119">The MSI file looks like `PowerShell-<version>-win-<os-arch>.msi`.</span></span> <span data-ttu-id="f472f-120">Пример:</span><span class="sxs-lookup"><span data-stu-id="f472f-120">For example:</span></span>

- `PowerShell-7.1.0-win-x64.msi`
- `PowerShell-7.1.0-win-x86.msi`

<span data-ttu-id="f472f-121">После скачивания дважды щелкните установщик и следуйте инструкциям на экране.</span><span class="sxs-lookup"><span data-stu-id="f472f-121">Once downloaded, double-click the installer and follow the prompts.</span></span>

<span data-ttu-id="f472f-122">Программа установки создает ярлык в меню Windows "Пуск".</span><span class="sxs-lookup"><span data-stu-id="f472f-122">The installer creates a shortcut in the Windows Start Menu.</span></span>

- <span data-ttu-id="f472f-123">По умолчанию пакет устанавливается в каталог `$env:ProgramFiles\PowerShell\<version>`.</span><span class="sxs-lookup"><span data-stu-id="f472f-123">By default the package is installed to `$env:ProgramFiles\PowerShell\<version>`</span></span>
- <span data-ttu-id="f472f-124">Вы можете запустить PowerShell с помощью меню "Пуск" или файла `$env:ProgramFiles\PowerShell\<version>\pwsh.exe`.</span><span class="sxs-lookup"><span data-stu-id="f472f-124">You can launch PowerShell via the Start Menu or `$env:ProgramFiles\PowerShell\<version>\pwsh.exe`</span></span>

> [!NOTE]
> <span data-ttu-id="f472f-125">PowerShell 7.1 устанавливается в новом каталоге и работает параллельно с Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="f472f-125">PowerShell 7.1 installs to a new directory and runs side-by-side with Windows PowerShell 5.1.</span></span>
> <span data-ttu-id="f472f-126">PowerShell 7.1 устанавливается как обновление на месте взамен PowerShell 6.x</span><span class="sxs-lookup"><span data-stu-id="f472f-126">PowerShell 7.1 is an in-place upgrade that replaces PowerShell 6.x.</span></span> <span data-ttu-id="f472f-127">или PowerShell 7.0.</span><span class="sxs-lookup"><span data-stu-id="f472f-127">or PowerShell 7.0.</span></span>
>
> - <span data-ttu-id="f472f-128">PowerShell 7.1 устанавливается в папке `$env:ProgramFiles\PowerShell\7`.</span><span class="sxs-lookup"><span data-stu-id="f472f-128">PowerShell 7.1 is installed to `$env:ProgramFiles\PowerShell\7`</span></span>
> - <span data-ttu-id="f472f-129">Папка `$env:ProgramFiles\PowerShell\7` добавляется в переменную `$env:PATH`.</span><span class="sxs-lookup"><span data-stu-id="f472f-129">The `$env:ProgramFiles\PowerShell\7` folder is added to `$env:PATH`</span></span>
> - <span data-ttu-id="f472f-130">Папка `$env:ProgramFiles\PowerShell\6` удалена.</span><span class="sxs-lookup"><span data-stu-id="f472f-130">The `$env:ProgramFiles\PowerShell\6` folder is deleted</span></span>
>
> <span data-ttu-id="f472f-131">Если вам нужно запустить PowerShell 7.1 параллельно с другими версиями, используйте метод [установки ZIP-архива](#zip), чтобы установить новую версию в другую папку.</span><span class="sxs-lookup"><span data-stu-id="f472f-131">If you need to run PowerShell 7.1 side-by-side with other versions, use the [ZIP install](#zip) method to install the other version to a different folder.</span></span>

### <a name="administrative-install-from-the-command-line"></a><span data-ttu-id="f472f-132">Установка администратором из командной строки</span><span class="sxs-lookup"><span data-stu-id="f472f-132">Administrative install from the command line</span></span>

<span data-ttu-id="f472f-133">MSI-пакеты можно устанавливать из командной строки, что позволяет администраторам развертывать их без взаимодействия с пользователем.</span><span class="sxs-lookup"><span data-stu-id="f472f-133">MSI packages can be installed from the command line allowing administrators to deploy packages without user interaction.</span></span> <span data-ttu-id="f472f-134">MSI-пакет включает в себя следующие свойства для управления параметрами установки:</span><span class="sxs-lookup"><span data-stu-id="f472f-134">The MSI package includes the following properties to control the installation options:</span></span>

- <span data-ttu-id="f472f-135">**ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL**. Это свойство позволяет добавлять пункт **Открыть PowerShell** в контекстное меню проводника.</span><span class="sxs-lookup"><span data-stu-id="f472f-135">**ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL** - This property controls the option for adding the **Open PowerShell** item to the context menu in Windows Explorer.</span></span>
- <span data-ttu-id="f472f-136">**ENABLE_PSREMOTING**. Это свойство позволяет включать удаленное взаимодействие PowerShell во время установки.</span><span class="sxs-lookup"><span data-stu-id="f472f-136">**ENABLE_PSREMOTING** - This property controls the option for enabling PowerShell remoting during installation.</span></span>
- <span data-ttu-id="f472f-137">**REGISTER_MANIFEST**. Это свойство позволяет регистрировать манифест ведения журнала событий Windows.</span><span class="sxs-lookup"><span data-stu-id="f472f-137">**REGISTER_MANIFEST** - This property controls the option for registering the Windows Event Logging manifest.</span></span>

<span data-ttu-id="f472f-138">В следующих примерах показано, как выполнить автоматическую установку PowerShell со всеми включенными параметрами.</span><span class="sxs-lookup"><span data-stu-id="f472f-138">The following example shows how to silently install PowerShell with all the install options enabled.</span></span>

```powershell
msiexec.exe /package PowerShell-7.1.0-win-x64.msi /quiet ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL=1 ENABLE_PSREMOTING=1 REGISTER_MANIFEST=1
```

<span data-ttu-id="f472f-139">Полный список параметров командной строки для `Msiexec.exe` см. [здесь](/windows/desktop/Msi/command-line-options).</span><span class="sxs-lookup"><span data-stu-id="f472f-139">For a full list of command-line options for `Msiexec.exe`, see [Command line options](/windows/desktop/Msi/command-line-options).</span></span>

### <a name="registry-keys-created-during-installation"></a><span data-ttu-id="f472f-140">Разделы реестра, созданные во время установки</span><span class="sxs-lookup"><span data-stu-id="f472f-140">Registry keys created during installation</span></span>

<span data-ttu-id="f472f-141">Начиная с версии PowerShell 7.1, пакет MSI создает разделы реестра, которые хранят данные о расположении установки и версии PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f472f-141">Beginning in PowerShell 7.1, the MSI package creates registry keys that store the installation location and version of PowerShell.</span></span> <span data-ttu-id="f472f-142">Эти значения можно найти в разделе `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\<GUID>`.</span><span class="sxs-lookup"><span data-stu-id="f472f-142">These values are located in `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\<GUID>`.</span></span> <span data-ttu-id="f472f-143">Значение `<GUID>` уникально для каждого типа сборки (выпуск или предварительная версия), основного номера версии и архитектуры.</span><span class="sxs-lookup"><span data-stu-id="f472f-143">The value of `<GUID>` is unique for each build type (release or preview), major version, and architecture.</span></span>

|    <span data-ttu-id="f472f-144">Release</span><span class="sxs-lookup"><span data-stu-id="f472f-144">Release</span></span>    | <span data-ttu-id="f472f-145">Architecture</span><span class="sxs-lookup"><span data-stu-id="f472f-145">Architecture</span></span> |                                          <span data-ttu-id="f472f-146">Ключ реестра</span><span class="sxs-lookup"><span data-stu-id="f472f-146">Registry Key</span></span>                                           |
| ------------- | :----------: | ----------------------------------------------------------------------------------------------- |
| <span data-ttu-id="f472f-147">Выпуск версии 7.1.x</span><span class="sxs-lookup"><span data-stu-id="f472f-147">7.1.x Release</span></span> |     <span data-ttu-id="f472f-148">x86</span><span class="sxs-lookup"><span data-stu-id="f472f-148">x86</span></span>      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\1d00683b-0f84-4db8-a64f-2f98ad42fe06` |
| <span data-ttu-id="f472f-149">Выпуск версии 7.1.x</span><span class="sxs-lookup"><span data-stu-id="f472f-149">7.1.x Release</span></span> |     <span data-ttu-id="f472f-150">X64</span><span class="sxs-lookup"><span data-stu-id="f472f-150">x64</span></span>      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\31ab5147-9a97-4452-8443-d9709f0516e1` |
| <span data-ttu-id="f472f-151">Предварительная версия 7.1.x</span><span class="sxs-lookup"><span data-stu-id="f472f-151">7.1.x Preview</span></span> |     <span data-ttu-id="f472f-152">x86</span><span class="sxs-lookup"><span data-stu-id="f472f-152">x86</span></span>      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\86abcfbd-1ccc-4a88-b8b2-0facfde29094` |
| <span data-ttu-id="f472f-153">Предварительная версия 7.1.x</span><span class="sxs-lookup"><span data-stu-id="f472f-153">7.1.x Preview</span></span> |     <span data-ttu-id="f472f-154">X64</span><span class="sxs-lookup"><span data-stu-id="f472f-154">x64</span></span>      | `HKLM\Software\Microsoft\PowerShellCore\InstalledVersions\39243d76-adaf-42b1-94fb-16ecf83237c8` |

<span data-ttu-id="f472f-155">Может использоваться администраторами и разработчиками для поиска пути к PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f472f-155">This can be used by administrators and developers to find the path to PowerShell.</span></span> <span data-ttu-id="f472f-156">Значения `<GUID>` будут одинаковыми для всех выпусков предварительных и дополнительных версий.</span><span class="sxs-lookup"><span data-stu-id="f472f-156">The `<GUID>` values will be the same for all preview and minor version releases.</span></span> <span data-ttu-id="f472f-157">Значения `<GUID>` отличаются для каждого выпуска основной версии.</span><span class="sxs-lookup"><span data-stu-id="f472f-157">The `<GUID>` values are changed for each major release.</span></span>

## <a name="installing-the-zip-package"></a><span data-ttu-id="f472f-158"><a id="zip" />Установка ZIP-пакета</span><span class="sxs-lookup"><span data-stu-id="f472f-158"><a id="zip" />Installing the ZIP package</span></span>

<span data-ttu-id="f472f-159">Для поддержки расширенных сценариев развертывания доступны ZIP-архивы двоичных файлов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f472f-159">PowerShell binary ZIP archives are provided to enable advanced deployment scenarios.</span></span> <span data-ttu-id="f472f-160">Скачайте один из следующих ZIP-архивов на странице [выпуски][выпуски].</span><span class="sxs-lookup"><span data-stu-id="f472f-160">Download one of the following ZIP archives from the [releases][releases] page.</span></span>

- <span data-ttu-id="f472f-161">PowerShell-7.1.0-win-x64.zip;</span><span class="sxs-lookup"><span data-stu-id="f472f-161">PowerShell-7.1.0-win-x64.zip</span></span>
- <span data-ttu-id="f472f-162">PowerShell-7.1.0-win-x86.zip;</span><span class="sxs-lookup"><span data-stu-id="f472f-162">PowerShell-7.1.0-win-x86.zip</span></span>
- <span data-ttu-id="f472f-163">PowerShell-7.1.0-win-arm64.zip;</span><span class="sxs-lookup"><span data-stu-id="f472f-163">PowerShell-7.1.0-win-arm64.zip</span></span>
- <span data-ttu-id="f472f-164">PowerShell-7.1.0-win-arm32.zip.</span><span class="sxs-lookup"><span data-stu-id="f472f-164">PowerShell-7.1.0-win-arm32.zip</span></span>

<span data-ttu-id="f472f-165">В зависимости от способа загрузки файла может потребоваться разблокировать файл с помощью командлета `Unblock-File`.</span><span class="sxs-lookup"><span data-stu-id="f472f-165">Depending on how you download the file you may need to unblock the file using the `Unblock-File` cmdlet.</span></span> <span data-ttu-id="f472f-166">Распакуйте содержимое в выбранное расположение и запустите `pwsh.exe`.</span><span class="sxs-lookup"><span data-stu-id="f472f-166">Unzip the contents to the location of your choice and run `pwsh.exe` from there.</span></span> <span data-ttu-id="f472f-167">В отличие от установки пакетов MSI при установке ZIP-архива не выполняется проверка соответствия предварительным требованиям.</span><span class="sxs-lookup"><span data-stu-id="f472f-167">Unlike installing the MSI packages, installing the ZIP archive doesn't check for prerequisites.</span></span> <span data-ttu-id="f472f-168">Для правильного удаленного взаимодействия с помощью WSMan необходимо обеспечить соответствие [предварительным требованиям](#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="f472f-168">For remoting over WSMan to work properly, ensure that you've met the [prerequisites](#prerequisites).</span></span>

<span data-ttu-id="f472f-169">Используйте этот метод для установки версии PowerShell на основе ARM на таких компьютерах, как Microsoft Surface Pro X. Чтобы получить оптимальные результаты, устанавливайте PowerShell в папку `$env:ProgramFiles\PowerShell\7`.</span><span class="sxs-lookup"><span data-stu-id="f472f-169">Use this method to install the ARM-based version of PowerShell on computers like the Microsoft Surface Pro X. For best results, install PowerShell to the to `$env:ProgramFiles\PowerShell\7` folder.</span></span>

## <a name="deploying-on-windows-10-iot-enterprise"></a><span data-ttu-id="f472f-170">Развертывание в Windows 10 IoT Корпоративная</span><span class="sxs-lookup"><span data-stu-id="f472f-170">Deploying on Windows 10 IoT Enterprise</span></span>

<span data-ttu-id="f472f-171">Windows 10 IoT Корпоративная поставляется со средой Windows PowerShell, которую можно использовать для развертывания PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="f472f-171">Windows 10 IoT Enterprise comes with Windows PowerShell, which we can use to deploy PowerShell 7.</span></span>

1. <span data-ttu-id="f472f-172">Создайте `PSSession` для целевого устройства</span><span class="sxs-lookup"><span data-stu-id="f472f-172">Create `PSSession` to target device</span></span>

   ```powershell
   Set-Item -Path WSMan:\localhost\Client\TrustedHosts <deviceip>
   $S = New-PSSession -ComputerName <deviceIp> -Credential Administrator
   ```

1. <span data-ttu-id="f472f-173">Скопируйте ZIP-файл на устройство</span><span class="sxs-lookup"><span data-stu-id="f472f-173">Copy the ZIP package to the device</span></span>

   ```powershell
   # change the destination to however you had partitioned it with sufficient
   # space for the zip and the unzipped contents
   # the path should be local to the device
   Copy-Item .\PowerShell-<version>-win-<os-arch>.zip -Destination u:\users\administrator\Downloads -ToSession $s
   ```

1. <span data-ttu-id="f472f-174">Присоединитесь к устройству и извлеките архив</span><span class="sxs-lookup"><span data-stu-id="f472f-174">Connect to the device and expand the archive</span></span>

   ```powershell
   Enter-PSSession $s
   Set-Location u:\users\administrator\downloads
   Expand-Archive .\PowerShell-<version>-win-<os-arch>.zip
   ```

1. <span data-ttu-id="f472f-175">Настройте удаленное взаимодействие с PowerShell 7</span><span class="sxs-lookup"><span data-stu-id="f472f-175">Set up remoting to PowerShell 7</span></span>

   ```powershell
   Set-Location .\PowerShell-<version>-win-<os-arch>
   # Be sure to use the -PowerShellHome parameter otherwise it'll try to create a new
   # endpoint with Windows PowerShell 5.1
   .\Install-PowerShellRemoting.ps1 -PowerShellHome .
   # You'll get an error message and will be disconnected from the device because
   # it has to restart WinRM
   ```

1. <span data-ttu-id="f472f-176">Подключение к конечной точке PowerShell 7 на устройстве</span><span class="sxs-lookup"><span data-stu-id="f472f-176">Connect to PowerShell 7 endpoint on device</span></span>

   ```powershell
   # Be sure to use the -Configuration parameter. If you omit it, you will connect to Windows PowerShell 5.1
   Enter-PSSession -ComputerName <deviceIp> -Credential Administrator -Configuration powershell.<version>
   ```

## <a name="deploying-on-windows-10-iot-core"></a><span data-ttu-id="f472f-177">Развертывание в Windows 10 IoT Базовая</span><span class="sxs-lookup"><span data-stu-id="f472f-177">Deploying on Windows 10 IoT Core</span></span>

<span data-ttu-id="f472f-178">Windows PowerShell добавляется в Windows 10 IoT Базовая, если вы включаете функцию _IOT_POWERSHELL_, которую можно использовать для развертывания PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="f472f-178">Windows 10 IoT Core adds Windows PowerShell when you include _IOT_POWERSHELL_ feature, which we can use to deploy PowerShell 7.</span></span> <span data-ttu-id="f472f-179">Действия, описанные выше для Windows 10 IoT Корпоративная, могут быть выполнены и для центра Интернета вещей.</span><span class="sxs-lookup"><span data-stu-id="f472f-179">The steps defined above for Windows 10 IoT Enterprise can be followed for IoT Core as well.</span></span>

<span data-ttu-id="f472f-180">Чтобы добавить последнюю версию PowerShell в образ для доставки, используйте команду [Import-PSCoreRelease][] для включения пакета в рабочую область и добавления _OPENSRC_POWERSHELL_ в образ.</span><span class="sxs-lookup"><span data-stu-id="f472f-180">For adding the latest PowerShell in the shipping image, use [Import-PSCoreRelease][] command to include the package in the workarea and add _OPENSRC_POWERSHELL_ feature to your image.</span></span>

> [!NOTE]
> <span data-ttu-id="f472f-181">В архитектуре ARM64 Windows PowerShell не добавляется при включении _IOT_POWERSHELL_.</span><span class="sxs-lookup"><span data-stu-id="f472f-181">For ARM64 architecture, Windows PowerShell is not added when you include _IOT_POWERSHELL_.</span></span> <span data-ttu-id="f472f-182">Поэтому установка на основе ZIP-файла не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="f472f-182">So the zip based install will not work.</span></span> <span data-ttu-id="f472f-183">Для добавления в образ используйте команду `Import-PSCoreRelease`.</span><span class="sxs-lookup"><span data-stu-id="f472f-183">You will need to use `Import-PSCoreRelease` command to add it in the image.</span></span>

## <a name="deploying-on-nano-server"></a><span data-ttu-id="f472f-184">Развертывание на Nano Server</span><span class="sxs-lookup"><span data-stu-id="f472f-184">Deploying on Nano Server</span></span>

<span data-ttu-id="f472f-185">В этих указаниях предполагается, что Nano Server — это операционная система для удаленного управления, в которой уже работает какая-либо версия PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f472f-185">These instructions assume that the Nano Server is a "headless" OS that has a version of PowerShell is already running on it.</span></span> <span data-ttu-id="f472f-186">Дополнительные сведения см. в разделе о [средстве создания образов Nano Server](/windows-server/get-started/deploy-nano-server).</span><span class="sxs-lookup"><span data-stu-id="f472f-186">For more information, see the [Nano Server Image Builder](/windows-server/get-started/deploy-nano-server) documentation.</span></span>

<span data-ttu-id="f472f-187">Двоичные файлы PowerShell можно развернуть двумя разными способами:</span><span class="sxs-lookup"><span data-stu-id="f472f-187">PowerShell binaries can be deployed using two different methods.</span></span>

1. <span data-ttu-id="f472f-188">Автономно — подключите виртуальный жесткий диск Nano Server и распакуйте содержимое ZIP-файла в выбранное расположение в этом образе.</span><span class="sxs-lookup"><span data-stu-id="f472f-188">Offline - Mount the Nano Server VHD and unzip the contents of the zip file to your chosen location within the mounted image.</span></span>
1. <span data-ttu-id="f472f-189">В сети — передайте ZIP-файл через сеанс PowerShell и распакуйте его в выбранное расположение.</span><span class="sxs-lookup"><span data-stu-id="f472f-189">Online - Transfer the zip file over a PowerShell Session and unzip it in your chosen location.</span></span>

<span data-ttu-id="f472f-190">В обоих случаях требуется ZIP-пакет выпуска Windows 10 семейства x64.</span><span class="sxs-lookup"><span data-stu-id="f472f-190">In both cases, you need the Windows 10 x64 ZIP release package.</span></span> <span data-ttu-id="f472f-191">Выполните команды в экземпляре PowerShell с ролью администратора.</span><span class="sxs-lookup"><span data-stu-id="f472f-191">Run the commands within an "Administrator" instance of PowerShell.</span></span>

### <a name="offline-deployment-of-powershell"></a><span data-ttu-id="f472f-192">Автономное развертывание PowerShell</span><span class="sxs-lookup"><span data-stu-id="f472f-192">Offline Deployment of PowerShell</span></span>

1. <span data-ttu-id="f472f-193">С помощью любой служебной программы ZIP распакуйте пакет в каталог, находящийся внутри подключенного образа Nano Server.</span><span class="sxs-lookup"><span data-stu-id="f472f-193">Use your favorite zip utility to unzip the package to a directory within the mounted Nano Server image.</span></span>
1. <span data-ttu-id="f472f-194">Отключите образ и загрузите его.</span><span class="sxs-lookup"><span data-stu-id="f472f-194">Unmount the image and boot it.</span></span>
1. <span data-ttu-id="f472f-195">Подключитесь к встроенному экземпляру Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f472f-195">Connect to the built-in instance of Windows PowerShell.</span></span>
1. <span data-ttu-id="f472f-196">Следуйте инструкциям, чтобы создать конечную точку удаленного взаимодействия с помощью [методики использования другого экземпляра][].</span><span class="sxs-lookup"><span data-stu-id="f472f-196">Follow the instructions to create a remoting endpoint using the ["another instance technique"][].</span></span>

### <a name="online-deployment-of-powershell"></a><span data-ttu-id="f472f-197">Автономное PowerShell в сети</span><span class="sxs-lookup"><span data-stu-id="f472f-197">Online Deployment of PowerShell</span></span>

<span data-ttu-id="f472f-198">Разверните PowerShell в Nano Server, выполнив действия ниже.</span><span class="sxs-lookup"><span data-stu-id="f472f-198">Deploy PowerShell to Nano Server using the following steps.</span></span>

- <span data-ttu-id="f472f-199">Подключитесь к встроенному экземпляру Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f472f-199">Connect to the built-in instance of Windows PowerShell</span></span>

  ```powershell
  $session = New-PSSession -ComputerName <Nano Server IP address> -Credential <An Administrator account on the system>
  ```

- <span data-ttu-id="f472f-200">Скопируйте файл на экземпляр Nano Server:</span><span class="sxs-lookup"><span data-stu-id="f472f-200">Copy the file to the Nano Server instance</span></span>

  ```powershell
  Copy-Item <local PS Core download location>\powershell-<version>-win-x64.zip c:\ -ToSession $session
  ```

- <span data-ttu-id="f472f-201">Войдите в сеанс:</span><span class="sxs-lookup"><span data-stu-id="f472f-201">Enter the session</span></span>

  ```powershell
  Enter-PSSession $session
  ```

- <span data-ttu-id="f472f-202">Извлеките ZIP-файл</span><span class="sxs-lookup"><span data-stu-id="f472f-202">Extract the ZIP file</span></span>

  ```powershell
  # Insert the appropriate version.
  Expand-Archive -Path C:\powershell-<version>-win-x64.zip -DestinationPath "C:\PowerShell_<version>"
  ```

- <span data-ttu-id="f472f-203">Если вам требуется удаленное взаимодействие на основе WSMan, следуйте инструкциям, чтобы создать конечную точку удаленного взаимодействия с помощью [методики использования другого экземпляра][].</span><span class="sxs-lookup"><span data-stu-id="f472f-203">If you want WSMan-based remoting, follow the instructions to create a remoting endpoint using the ["another instance technique"][].</span></span>

## <a name="install-as-a-net-global-tool"></a><span data-ttu-id="f472f-204">Установка в качестве глобального средства .NET</span><span class="sxs-lookup"><span data-stu-id="f472f-204">Install as a .NET Global tool</span></span>

<span data-ttu-id="f472f-205">Если вы уже установили [пакет SDK для .NET Core](/dotnet/core/sdk), установите PowerShell как [глобальное средство .NET](/dotnet/core/tools/global-tools).</span><span class="sxs-lookup"><span data-stu-id="f472f-205">If you already have the [.NET Core SDK](/dotnet/core/sdk) installed, it's easy to install PowerShell as a [.NET Global tool](/dotnet/core/tools/global-tools).</span></span>

```
dotnet tool install --global PowerShell
```

<span data-ttu-id="f472f-206">Установщик инструмента dotnet добавляет `$env:USERPROFILE\dotnet\tools` в переменную среды `$env:PATH`.</span><span class="sxs-lookup"><span data-stu-id="f472f-206">The dotnet tool installer adds `$env:USERPROFILE\dotnet\tools` to your `$env:PATH` environment variable.</span></span> <span data-ttu-id="f472f-207">Но в выполняющейся оболочке нет обновленной переменной `$env:PATH`.</span><span class="sxs-lookup"><span data-stu-id="f472f-207">However, the currently running shell doesn't have the updated `$env:PATH`.</span></span> <span data-ttu-id="f472f-208">Вы можете запустить PowerShell из новой оболочки, введя `pwsh`.</span><span class="sxs-lookup"><span data-stu-id="f472f-208">You can start PowerShell from a new shell by typing `pwsh`.</span></span>

## <a name="install-powershell-via-winget"></a><span data-ttu-id="f472f-209">Установка PowerShell через Winget</span><span class="sxs-lookup"><span data-stu-id="f472f-209">Install PowerShell via Winget</span></span>

<span data-ttu-id="f472f-210">Программа командной строки `winget` позволяет разработчикам обнаруживать, устанавливать, обновлять, удалять и настраивать приложения на компьютерах Windows 10.</span><span class="sxs-lookup"><span data-stu-id="f472f-210">The `winget` command-line tool enables developers to discover, install, upgrade, remove, and configure applications on Windows 10 computers.</span></span> <span data-ttu-id="f472f-211">Она является клиентским интерфейсом для службы Диспетчера пакетов Windows.</span><span class="sxs-lookup"><span data-stu-id="f472f-211">This tool is the client interface to the Windows Package Manager service.</span></span>

> [!NOTE]
> <span data-ttu-id="f472f-212">В настоящее время инструмент `winget` предоставляется в предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="f472f-212">The `winget` tool is currently a preview.</span></span> <span data-ttu-id="f472f-213">Сейчас доступны не все запланированные функции.</span><span class="sxs-lookup"><span data-stu-id="f472f-213">Not all planned functionality is available at this time.</span></span>
> <span data-ttu-id="f472f-214">Не используйте этот метод в сценарии развертывания в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="f472f-214">You should not use this method in a production deployment scenario.</span></span> <span data-ttu-id="f472f-215">Список системных требований и инструкции по установке см. в документации по [winget].</span><span class="sxs-lookup"><span data-stu-id="f472f-215">See the [winget] documentation for a list of system requirements and install instructions.</span></span>

<span data-ttu-id="f472f-216">Для установки PowerShell с помощью опубликованных пакетов `winget` можно использовать следующие команды:</span><span class="sxs-lookup"><span data-stu-id="f472f-216">The following commands can be used to install PowerShell using the published `winget` packages:</span></span>

1. <span data-ttu-id="f472f-217">Найдите последнюю версию PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f472f-217">Search for the latest version of PowerShell</span></span>

   ```powershell
   winget search Microsoft.PowerShell
   ```

   ```Output
   Name               Id                           Version
   ---------------------------------------------------------------
   PowerShell         Microsoft.PowerShell         7.1.0
   PowerShell-Preview Microsoft.PowerShell-Preview 7.1.0-preview.5
   ```

1. <span data-ttu-id="f472f-218">Установите версию PowerShell, используя параметр `--exact`.</span><span class="sxs-lookup"><span data-stu-id="f472f-218">Install a version of PowerShell using the `--exact` parameter</span></span>

   ```powershell
   winget install --name PowerShell --exact
   winget install --name PowerShell-Preview --exact
   ```

## <a name="installing-from-the-microsoft-store"></a><span data-ttu-id="f472f-219"><a id="msix" />Установка из Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="f472f-219"><a id="msix" />Installing from the Microsoft Store</span></span>

<span data-ttu-id="f472f-220">Версия PowerShell 7.1 опубликована в Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="f472f-220">PowerShell 7.1 has been published to the Microsoft Store.</span></span> <span data-ttu-id="f472f-221">Этот выпуск PowerShell можно найти на веб-сайте [Microsoft Store](https://www.microsoft.com/store/apps/9MZ1SNWT0N5D) или в приложении Store в ОС Windows.</span><span class="sxs-lookup"><span data-stu-id="f472f-221">You can find the PowerShell release on the [Microsoft Store](https://www.microsoft.com/store/apps/9MZ1SNWT0N5D) website or in the Store application in Windows.</span></span>

<span data-ttu-id="f472f-222">Пакет Microsoft Store обеспечивает следующие преимущества:</span><span class="sxs-lookup"><span data-stu-id="f472f-222">Benefits of the Microsoft Store package:</span></span>

- <span data-ttu-id="f472f-223">автоматические обновления, встроенные в основной механизм Windows 10;</span><span class="sxs-lookup"><span data-stu-id="f472f-223">Automatic updates built right into Windows 10</span></span>
- <span data-ttu-id="f472f-224">интеграция с другими механизмами распространения программного обеспечения, такими как Intune и SCCM.</span><span class="sxs-lookup"><span data-stu-id="f472f-224">Integrates with other software distribution mechanisms like Intune and SCCM</span></span>

<span data-ttu-id="f472f-225">Ограничения</span><span class="sxs-lookup"><span data-stu-id="f472f-225">Limitations:</span></span>

<span data-ttu-id="f472f-226">Пакеты MSIX выполняются в песочнице приложения, которая виртуализует доступ к некоторым расположениям в файловой системе и реестре.</span><span class="sxs-lookup"><span data-stu-id="f472f-226">MSIX packages run in an application sandbox that virtualizes access to some filesystem and registry locations.</span></span>

- <span data-ttu-id="f472f-227">Все изменения реестра в разделе HKEY_CURRENT_USER при записи копируются в закрытое хранилище, отдельно для каждого пользователя и приложения.</span><span class="sxs-lookup"><span data-stu-id="f472f-227">All registry changes under HKEY_CURRENT_USER are copied on write to a private, per-user, per-app location.</span></span> <span data-ttu-id="f472f-228">Таким образом, эти значения недоступны для других приложений.</span><span class="sxs-lookup"><span data-stu-id="f472f-228">Therefore, those values are not available to other applications.</span></span>
- <span data-ttu-id="f472f-229">Параметры конфигурации системного уровня, хранящиеся в `$PSHOME`, нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="f472f-229">Any system-level configuration settings stored in `$PSHOME` cannot be modified.</span></span> <span data-ttu-id="f472f-230">Это относится и к конфигурации WSMAN.</span><span class="sxs-lookup"><span data-stu-id="f472f-230">This includes the WSMAN configuration.</span></span> <span data-ttu-id="f472f-231">Это означает, что вы не сможете подключать удаленные сеансы к установкам PowerShell на основе хранилища.</span><span class="sxs-lookup"><span data-stu-id="f472f-231">This prevents remote sessions from connecting to Store-based installs of PowerShell.</span></span> <span data-ttu-id="f472f-232">Поддерживаются конфигурации уровня пользователя и удаленное взаимодействие по SSH.</span><span class="sxs-lookup"><span data-stu-id="f472f-232">User-level configurations and SSH remoting are supported.</span></span>

<span data-ttu-id="f472f-233">Подробнее см. [Основные сведения о работе упакованных классических приложений в Windows](/windows/msix/desktop/desktop-to-uwp-behind-the-scenes).</span><span class="sxs-lookup"><span data-stu-id="f472f-233">For more information, see [Understanding how packaged desktop apps run on Windows](/windows/msix/desktop/desktop-to-uwp-behind-the-scenes).</span></span>

### <a name="using-the-msix-package"></a><span data-ttu-id="f472f-234">Использование пакета MSIX</span><span class="sxs-lookup"><span data-stu-id="f472f-234">Using the MSIX package</span></span>

> [!NOTE]
> <span data-ttu-id="f472f-235">Предварительные сборки PowerShell включают пакет MSIX.</span><span class="sxs-lookup"><span data-stu-id="f472f-235">The preview builds of PowerShell include an MSIX package.</span></span> <span data-ttu-id="f472f-236">Пакет MSIX не поддерживается официально.</span><span class="sxs-lookup"><span data-stu-id="f472f-236">The MSIX package is not officially supported.</span></span> <span data-ttu-id="f472f-237">Этот пакет создан исключительно для тестовых целей и только на период действия предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="f472f-237">The package is built for testing purposes during the preview period.</span></span>

<span data-ttu-id="f472f-238">Чтобы вручную установить пакет MSIX на клиенте Windows 10, скачайте пакет MSIX на странице [выпуски][выпуски] в GitHub.</span><span class="sxs-lookup"><span data-stu-id="f472f-238">To manually install the MSIX package on a Windows 10 client, download the MSIX package from our GitHub [releases][releases] page.</span></span> <span data-ttu-id="f472f-239">Прокрутите вниз до раздела **Ресурсы** в выпуске, который вы хотите установить.</span><span class="sxs-lookup"><span data-stu-id="f472f-239">Scroll down to the **Assets** section of the Release you want to install.</span></span> <span data-ttu-id="f472f-240">Раздел "Ресурсы" может быть свернут. В таком случае щелкните его, чтобы развернуть.</span><span class="sxs-lookup"><span data-stu-id="f472f-240">The Assets section may be collapsed, so you may need to click to expand it.</span></span>

<span data-ttu-id="f472f-241">MSIX-файл выглядит примерно так: `PowerShell-<version>-win-<os-arch>.msix`</span><span class="sxs-lookup"><span data-stu-id="f472f-241">The MSIX file looks like this - `PowerShell-<version>-win-<os-arch>.msix`</span></span>

<span data-ttu-id="f472f-242">Для установки пакета необходимо использовать командлет `Add-AppxPackage`.</span><span class="sxs-lookup"><span data-stu-id="f472f-242">To install the package, you must use the `Add-AppxPackage` cmdlet.</span></span>

```powershell
Add-AppxPackage PowerShell-<version>-win-<os-arch>.msix
```

## <a name="how-to-create-a-remoting-endpoint"></a><span data-ttu-id="f472f-243">Создание конечной точки удаленного взаимодействия</span><span class="sxs-lookup"><span data-stu-id="f472f-243">How to create a remoting endpoint</span></span>

<span data-ttu-id="f472f-244">PowerShell поддерживает протокол удаленного взаимодействия PowerShell (PSRP) через SSH и WSMan.</span><span class="sxs-lookup"><span data-stu-id="f472f-244">PowerShell supports the PowerShell Remoting Protocol (PSRP) over both WSMan and SSH.</span></span> <span data-ttu-id="f472f-245">Дополнительные сведения см. в разделе:</span><span class="sxs-lookup"><span data-stu-id="f472f-245">For more information, see:</span></span>

- <span data-ttu-id="f472f-246">[Удаленное взаимодействие через SSH в PowerShell Core][ssh-remoting]</span><span class="sxs-lookup"><span data-stu-id="f472f-246">[SSH Remoting in PowerShell Core][ssh-remoting]</span></span>
- <span data-ttu-id="f472f-247">[Удаленное взаимодействие через WSMan в PowerShell Core][wsman-remoting]</span><span class="sxs-lookup"><span data-stu-id="f472f-247">[WSMan Remoting in PowerShell Core][wsman-remoting]</span></span>

## <a name="upgrading-an-existing-installation"></a><span data-ttu-id="f472f-248">Обновление существующей установки</span><span class="sxs-lookup"><span data-stu-id="f472f-248">Upgrading an existing installation</span></span>

<span data-ttu-id="f472f-249">Для получения оптимального результата при обновлении используйте тот же метод установки, который вы использовали при первой установке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f472f-249">For best results when upgrading, you should use the same install method you used when you first installed PowerShell.</span></span> <span data-ttu-id="f472f-250">При использовании разных методов установки PowerShell устанавливается в разные расположения.</span><span class="sxs-lookup"><span data-stu-id="f472f-250">Each installation method installs PowerShell in a different location.</span></span> <span data-ttu-id="f472f-251">Если вы не знаете, как была выполнена установка PowerShell, вы можете сравнить расположение установки со сведениями о пакетах из этой статьи.</span><span class="sxs-lookup"><span data-stu-id="f472f-251">If you are not sure how PowerShell was installed, you can compare the installed location with the package information in this article.</span></span> <span data-ttu-id="f472f-252">Если установка выполнена с помощью пакета MSI, эти сведения будут отображаться в разделе **Программы и компоненты** Панели управления.</span><span class="sxs-lookup"><span data-stu-id="f472f-252">If you installed via the MSI package, that information appears in the **Programs and Features** Control Panel.</span></span>

## <a name="installation-support"></a><span data-ttu-id="f472f-253">Поддержка установки</span><span class="sxs-lookup"><span data-stu-id="f472f-253">Installation support</span></span>

<span data-ttu-id="f472f-254">Корпорация Майкрософт поддерживает методы установки, изложенные в этом документе.</span><span class="sxs-lookup"><span data-stu-id="f472f-254">Microsoft supports the installation methods in this document.</span></span> <span data-ttu-id="f472f-255">В других источниках могут быть доступны другие методы установки.</span><span class="sxs-lookup"><span data-stu-id="f472f-255">There may be other methods of installation available from other sources.</span></span> <span data-ttu-id="f472f-256">Хотя такие инструменты и методы могут работать, корпорация Майкрософт не поддерживает их.</span><span class="sxs-lookup"><span data-stu-id="f472f-256">While those tools and methods may work, Microsoft cannot support those methods.</span></span>

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
