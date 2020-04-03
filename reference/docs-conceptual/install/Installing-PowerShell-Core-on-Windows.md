---
title: Установка PowerShell в Windows
description: Сведения об установке PowerShell в Windows
ms.date: 08/06/2018
ms.openlocfilehash: ea5432725f4baea8c688fb8e67482910e2c3981e
ms.sourcegitcommit: b6cf10224eb9f32919a505cdffbe5968241c18a1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2020
ms.locfileid: "80374898"
---
# <a name="installing-powershell-on-windows"></a><span data-ttu-id="8f7b8-103">Установка PowerShell в Windows</span><span class="sxs-lookup"><span data-stu-id="8f7b8-103">Installing PowerShell on Windows</span></span>

<span data-ttu-id="8f7b8-104">Есть несколько способов установки PowerShell в Windows.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-104">There are multiple ways to install PowerShell in Windows.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8f7b8-105">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="8f7b8-105">Prerequisites</span></span>

<span data-ttu-id="8f7b8-106">Последний выпуск PowerShell поддерживается в Windows 7 с пакетом обновления 1 (SP1), Windows Server 2008 R2 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-106">The latest release of PowerShell is supported on Windows 7 SP1, Server 2008 R2, and later versions.</span></span>

<span data-ttu-id="8f7b8-107">Чтобы включить удаленное взаимодействие PowerShell через WSMan, нужно выполнить следующие условия:</span><span class="sxs-lookup"><span data-stu-id="8f7b8-107">To enable PowerShell remoting over WSMan, the following prerequisites need to be met:</span></span>

- <span data-ttu-id="8f7b8-108">Установите [универсальную среду выполнения C](https://www.microsoft.com/download/details.aspx?id=50410) в Windows предшествующих Windows 10 версий.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-108">Install the [Universal C Runtime](https://www.microsoft.com/download/details.aspx?id=50410) on Windows versions predating Windows 10.</span></span> <span data-ttu-id="8f7b8-109">Ее можно скачать самостоятельно или через Центр обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-109">It's available via direct download or Windows Update.</span></span> <span data-ttu-id="8f7b8-110">Этот пакет уже установлен в полностью исправленных системах.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-110">Fully patched systems already have this package installed.</span></span>
- <span data-ttu-id="8f7b8-111">Установите Windows Management Framework (WMF) 4.0 или более поздней версии в Windows 7 и Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-111">Install the Windows Management Framework (WMF) 4.0 or newer on Windows 7 and Windows Server 2008 R2.</span></span> <span data-ttu-id="8f7b8-112">Подробные сведения о WMF см. в статье с [обзором WMF](/powershell/scripting/wmf/overview).</span><span class="sxs-lookup"><span data-stu-id="8f7b8-112">For more information about WMF, see [WMF Overview](/powershell/scripting/wmf/overview).</span></span>

## <a name="download-the-installer-package"></a><span data-ttu-id="8f7b8-113">Скачивание скрипта установщика</span><span class="sxs-lookup"><span data-stu-id="8f7b8-113">Download the installer package</span></span>

<span data-ttu-id="8f7b8-114">Чтобы установить PowerShell в Windows, скачайте установочный пакет со страницы [выпусков][releases] GitHub.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-114">To install PowerShell on Windows, download the install package from our GitHub [releases][releases] page.</span></span> <span data-ttu-id="8f7b8-115">Прокрутите страницу вниз до раздела **ресурсов**.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-115">Scroll down to the **Assets** section of the Release page.</span></span> <span data-ttu-id="8f7b8-116">Раздел **ресурсов** может быть свернут. В таком случае щелкните его, чтобы развернуть.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-116">The **Assets** section may be collapsed, so you may need to click to expand it.</span></span>

## <a name="installing-the-msi-package"></a><span data-ttu-id="8f7b8-117"><a id="msi" />Установка пакета MSI</span><span class="sxs-lookup"><span data-stu-id="8f7b8-117"><a id="msi" />Installing the MSI package</span></span>

<span data-ttu-id="8f7b8-118">MSI-файл выглядит примерно так: `PowerShell-<version>-win-<os-arch>.msi`.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-118">The MSI file looks like `PowerShell-<version>-win-<os-arch>.msi`.</span></span> <span data-ttu-id="8f7b8-119">Пример:</span><span class="sxs-lookup"><span data-stu-id="8f7b8-119">For example:</span></span>

- `PowerShell-7.0.0-win-x64.msi`
- `PowerShell-7.0.0-win-x86.msi`

<span data-ttu-id="8f7b8-120">После скачивания дважды щелкните установщик и следуйте инструкциям на экране.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-120">Once downloaded, double-click the installer and follow the prompts.</span></span>

<span data-ttu-id="8f7b8-121">Программа установки создает ярлык в меню Windows "Пуск".</span><span class="sxs-lookup"><span data-stu-id="8f7b8-121">The installer creates a shortcut in the Windows Start Menu.</span></span>

- <span data-ttu-id="8f7b8-122">По умолчанию пакет устанавливается в каталог `$env:ProgramFiles\PowerShell\<version>`.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-122">By default the package is installed to `$env:ProgramFiles\PowerShell\<version>`</span></span>
- <span data-ttu-id="8f7b8-123">Вы можете запустить PowerShell с помощью меню "Пуск" или файла `$env:ProgramFiles\PowerShell\<version>\pwsh.exe`.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-123">You can launch PowerShell via the Start Menu or `$env:ProgramFiles\PowerShell\<version>\pwsh.exe`</span></span>

> [!NOTE]
> <span data-ttu-id="8f7b8-124">PowerShell 7 устанавливается в новом каталоге и работает параллельно с Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-124">PowerShell 7 installs to a new directory and runs side-by-side with Windows PowerShell 5.1.</span></span> <span data-ttu-id="8f7b8-125">Для PowerShell Core 6.x версия PowerShell 7 является обновлением на месте, при установке которого PowerShell Core 6.x удаляется.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-125">For PowerShell Core 6.x, PowerShell 7 is an in-place upgrade that removes PowerShell Core 6.x.</span></span>
>
> - <span data-ttu-id="8f7b8-126">PowerShell 7 устанавливается в папке `$env:ProgramFiles\PowerShell\7`.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-126">PowerShell 7 is installed to `$env:ProgramFiles\PowerShell\7`</span></span>
> - <span data-ttu-id="8f7b8-127">Папка `$env:ProgramFiles\PowerShell\7` добавляется в переменную `$env:PATH`.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-127">The `$env:ProgramFiles\PowerShell\7` folder is added to `$env:PATH`</span></span>
> - <span data-ttu-id="8f7b8-128">Папка `$env:ProgramFiles\PowerShell\6` удалена.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-128">The `$env:ProgramFiles\PowerShell\6` folder is deleted</span></span>
>
> <span data-ttu-id="8f7b8-129">Если вы хотите запускать PowerShell 6 параллельно с PowerShell 7, переустановите PowerShell 6 с использованием [ZIP-архива](#zip).</span><span class="sxs-lookup"><span data-stu-id="8f7b8-129">If you need to run PowerShell 6 side-by-side with PowerShell 7, reinstall PowerShell 6 using the [ZIP install](#zip) method.</span></span>

### <a name="administrative-install-from-the-command-line"></a><span data-ttu-id="8f7b8-130">Установка администратором из командной строки</span><span class="sxs-lookup"><span data-stu-id="8f7b8-130">Administrative install from the command line</span></span>

<span data-ttu-id="8f7b8-131">MSI-пакеты можно устанавливать из командной строки, что позволяет администраторам развертывать их без взаимодействия с пользователем.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-131">MSI packages can be installed from the command line allowing administrators to deploy packages without user interaction.</span></span> <span data-ttu-id="8f7b8-132">MSI-пакет включает в себя следующие свойства для управления параметрами установки:</span><span class="sxs-lookup"><span data-stu-id="8f7b8-132">The MSI package includes the following properties to control the installation options:</span></span>

- <span data-ttu-id="8f7b8-133">**ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL**. Это свойство позволяет добавлять пункт **Открыть PowerShell** в контекстное меню проводника.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-133">**ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL** - This property controls the option for adding the **Open PowerShell** item to the context menu in Windows Explorer.</span></span>
- <span data-ttu-id="8f7b8-134">**ENABLE_PSREMOTING**. Это свойство позволяет включать удаленное взаимодействие PowerShell во время установки.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-134">**ENABLE_PSREMOTING** - This property controls the option for enabling PowerShell remoting during installation.</span></span>
- <span data-ttu-id="8f7b8-135">**REGISTER_MANIFEST**. Это свойство позволяет регистрировать манифест ведения журнала событий Windows.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-135">**REGISTER_MANIFEST** - This property controls the option for registering the Windows Event Logging manifest.</span></span>

<span data-ttu-id="8f7b8-136">В следующих примерах показано, как выполнить автоматическую установку PowerShell со всеми включенными параметрами.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-136">The following example shows how to silently install PowerShell with all the install options enabled.</span></span>

```powershell
msiexec.exe /package PowerShell-7.0.0-win-x64.msi /quiet ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL=1 ENABLE_PSREMOTING=1 REGISTER_MANIFEST=1
```

<span data-ttu-id="8f7b8-137">Полный список параметров командной строки для `Msiexec.exe` см. [здесь](/windows/desktop/Msi/command-line-options).</span><span class="sxs-lookup"><span data-stu-id="8f7b8-137">For a full list of command-line options for `Msiexec.exe`, see [Command line options](/windows/desktop/Msi/command-line-options).</span></span>

## <a name="installing-the-msix-package"></a><span data-ttu-id="8f7b8-138"><a id="msix" />Установка пакета MSIX</span><span class="sxs-lookup"><span data-stu-id="8f7b8-138"><a id="msix" />Installing the MSIX package</span></span>

<span data-ttu-id="8f7b8-139">Чтобы вручную установить пакет MSIX на клиент Windows 10, скачайте пакет MSIX на странице GitHub с [выпусками][releases].</span><span class="sxs-lookup"><span data-stu-id="8f7b8-139">To manually install the MSIX package on a Windows 10 client, download the MSIX package from our GitHub [releases][releases] page.</span></span> <span data-ttu-id="8f7b8-140">Прокрутите вниз до раздела **Ресурсы** в выпуске, который вы хотите установить.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-140">Scroll down to the **Assets** section of the Release you want to install.</span></span> <span data-ttu-id="8f7b8-141">Раздел "Ресурсы" может быть свернут. В таком случае щелкните его, чтобы развернуть.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-141">The Assets section may be collapsed, so you may need to click to expand it.</span></span>

<span data-ttu-id="8f7b8-142">MSIX-файл выглядит примерно так: `PowerShell-<version>-win-<os-arch>.msix`</span><span class="sxs-lookup"><span data-stu-id="8f7b8-142">The MSIX file looks like this - `PowerShell-<version>-win-<os-arch>.msix`</span></span>

<span data-ttu-id="8f7b8-143">Для установки пакета необходимо использовать командлет `Add-AppxPackage`.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-143">To install the package, you must use the `Add-AppxPackage` cmdlet.</span></span>

```powershell
Add-AppxPackage PowerShell-<version>-win-<os-arch>.msix
```

> [!NOTE]
> <span data-ttu-id="8f7b8-144">MSIX-пакет еще не выпущен.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-144">The MSIX package has not been released yet.</span></span> <span data-ttu-id="8f7b8-145">После выпуска пакет будет доступен в Microsoft Store и на странице [выпусков][releases] GitHub.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-145">When released, the package will be available in the Microsoft Store and from the GitHub [releases][releases] page.</span></span>

## <a name="installing-the-zip-package"></a><span data-ttu-id="8f7b8-146"><a id="zip" />Установка ZIP-пакета</span><span class="sxs-lookup"><span data-stu-id="8f7b8-146"><a id="zip" />Installing the ZIP package</span></span>

<span data-ttu-id="8f7b8-147">Для поддержки расширенных сценариев развертывания доступны ZIP-архивы двоичных файлов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-147">PowerShell binary ZIP archives are provided to enable advanced deployment scenarios.</span></span> <span data-ttu-id="8f7b8-148">При установке ZIP-архив не проверяется на соответствие требованиям, как при установке MSI-пакетов.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-148">Installing the ZIP archive doesn't check the prerequisites like the MSI packages do.</span></span> <span data-ttu-id="8f7b8-149">Для правильного удаленного взаимодействия с помощью WSMan необходимо обеспечить соответствие [предварительным требованиям](#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="8f7b8-149">For remoting over WSMan to work properly, ensure that you've met the [prerequisites](#prerequisites).</span></span>

## <a name="deploying-on-windows-iot"></a><span data-ttu-id="8f7b8-150">Развертывание в Windows IoT</span><span class="sxs-lookup"><span data-stu-id="8f7b8-150">Deploying on Windows IoT</span></span>

<span data-ttu-id="8f7b8-151">Windows IoT поставляется с Windows PowerShell, который можно использовать для развертывания PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-151">Windows IoT comes with Windows PowerShell, which we can use to deploy PowerShell 7.</span></span>

1. <span data-ttu-id="8f7b8-152">Создайте `PSSession` для целевого устройства</span><span class="sxs-lookup"><span data-stu-id="8f7b8-152">Create `PSSession` to target device</span></span>

   ```powershell
   Set-Item -Path WSMan:\localhost\Client\TrustedHosts <deviceip>
   $S = New-PSSession -ComputerName <deviceIp> -Credential Administrator
   ```

2. <span data-ttu-id="8f7b8-153">Скопируйте ZIP-файл на устройство</span><span class="sxs-lookup"><span data-stu-id="8f7b8-153">Copy the ZIP package to the device</span></span>

   ```powershell
   # change the destination to however you had partitioned it with sufficient
   # space for the zip and the unzipped contents
   # the path should be local to the device
   Copy-Item .\PowerShell-<version>-win-<os-arch>.zip -Destination u:\users\administrator\Downloads -ToSession $s
   ```

3. <span data-ttu-id="8f7b8-154">Присоединитесь к устройству и извлеките архив</span><span class="sxs-lookup"><span data-stu-id="8f7b8-154">Connect to the device and expand the archive</span></span>

   ```powershell
   Enter-PSSession $s
   Set-Location u:\users\administrator\downloads
   Expand-Archive .\PowerShell-<version>-win-<os-arch>.zip
   ```

4. <span data-ttu-id="8f7b8-155">Настройте удаленное взаимодействие с PowerShell 7</span><span class="sxs-lookup"><span data-stu-id="8f7b8-155">Set up remoting to PowerShell 7</span></span>

   ```powershell
   Set-Location .\PowerShell-<version>-win-<os-arch>
   # Be sure to use the -PowerShellHome parameter otherwise it'll try to create a new
   # endpoint with Windows PowerShell 5.1
   .\Install-PowerShellRemoting.ps1 -PowerShellHome .
   # You'll get an error message and will be disconnected from the device because it has to restart WinRM
   ```

5. <span data-ttu-id="8f7b8-156">Подключение к конечной точке PowerShell 7 на устройстве</span><span class="sxs-lookup"><span data-stu-id="8f7b8-156">Connect to PowerShell 7 endpoint on device</span></span>

   ```powershell
   # Be sure to use the -Configuration parameter.  If you omit it, you will connect to Windows PowerShell 5.1
   Enter-PSSession -ComputerName <deviceIp> -Credential Administrator -Configuration powershell.<version>
   ```

## <a name="deploying-on-nano-server"></a><span data-ttu-id="8f7b8-157">Развертывание на Nano Server</span><span class="sxs-lookup"><span data-stu-id="8f7b8-157">Deploying on Nano Server</span></span>

<span data-ttu-id="8f7b8-158">В этих указаниях предполагается, что Nano Server — это операционная система для удаленного управления, в которой уже работает какая-либо версия PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-158">These instructions assume that the Nano Server is a "headless" OS that has a version of PowerShell is already running on it.</span></span> <span data-ttu-id="8f7b8-159">Дополнительные сведения см. в разделе о [средстве создания образов Nano Server](/windows-server/get-started/deploy-nano-server).</span><span class="sxs-lookup"><span data-stu-id="8f7b8-159">For more information, see the [Nano Server Image Builder](/windows-server/get-started/deploy-nano-server) documentation.</span></span>

<span data-ttu-id="8f7b8-160">Двоичные файлы PowerShell можно развернуть двумя разными способами:</span><span class="sxs-lookup"><span data-stu-id="8f7b8-160">PowerShell binaries can be deployed using two different methods.</span></span>

1. <span data-ttu-id="8f7b8-161">Автономно — подключите виртуальный жесткий диск Nano Server и распакуйте содержимое ZIP-файла в выбранное расположение в этом образе.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-161">Offline - Mount the Nano Server VHD and unzip the contents of the zip file to your chosen location within the mounted image.</span></span>
2. <span data-ttu-id="8f7b8-162">В сети — передайте ZIP-файл через сеанс PowerShell и распакуйте его в выбранное расположение.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-162">Online - Transfer the zip file over a PowerShell Session and unzip it in your chosen location.</span></span>

<span data-ttu-id="8f7b8-163">В обоих случаях требуется ZIP-пакет выпуска Windows 10 семейства x64.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-163">In both cases, you need the Windows 10 x64 ZIP release package.</span></span> <span data-ttu-id="8f7b8-164">Выполните команды в экземпляре PowerShell с ролью администратора.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-164">Run the commands within an "Administrator" instance of PowerShell.</span></span>

### <a name="offline-deployment-of-powershell"></a><span data-ttu-id="8f7b8-165">Автономное развертывание PowerShell</span><span class="sxs-lookup"><span data-stu-id="8f7b8-165">Offline Deployment of PowerShell</span></span>

1. <span data-ttu-id="8f7b8-166">С помощью любой служебной программы ZIP распакуйте пакет в каталог, находящийся внутри подключенного образа Nano Server.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-166">Use your favorite zip utility to unzip the package to a directory within the mounted Nano Server image.</span></span>
2. <span data-ttu-id="8f7b8-167">Отключите образ и загрузите его.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-167">Unmount the image and boot it.</span></span>
3. <span data-ttu-id="8f7b8-168">Подключитесь к входящему экземпляру Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-168">Connect to the inbox instance of Windows PowerShell.</span></span>
4. <span data-ttu-id="8f7b8-169">Следуйте инструкциям, чтобы создать конечную точку удаленного взаимодействия с помощью [методики использования другого экземпляра](../learn/remoting/wsman-remoting-in-powershell-core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).</span><span class="sxs-lookup"><span data-stu-id="8f7b8-169">Follow the instructions to create a remoting endpoint using the ["another instance technique"](../learn/remoting/wsman-remoting-in-powershell-core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).</span></span>

### <a name="online-deployment-of-powershell"></a><span data-ttu-id="8f7b8-170">Автономное PowerShell в сети</span><span class="sxs-lookup"><span data-stu-id="8f7b8-170">Online Deployment of PowerShell</span></span>

<span data-ttu-id="8f7b8-171">Разверните PowerShell в Nano Server, выполнив действия ниже.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-171">Deploy PowerShell to Nano Server using the following steps.</span></span>

- <span data-ttu-id="8f7b8-172">Подключитесь к входящему экземпляру Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8f7b8-172">Connect to the inbox instance of Windows PowerShell</span></span>

  ```powershell
  $session = New-PSSession -ComputerName <Nano Server IP address> -Credential <An Administrator account on the system>
  ```

- <span data-ttu-id="8f7b8-173">Скопируйте файл на экземпляр Nano Server:</span><span class="sxs-lookup"><span data-stu-id="8f7b8-173">Copy the file to the Nano Server instance</span></span>

  ```powershell
  Copy-Item <local PS Core download location>\powershell-<version>-win-x64.zip c:\ -ToSession $session
  ```

- <span data-ttu-id="8f7b8-174">Войдите в сеанс:</span><span class="sxs-lookup"><span data-stu-id="8f7b8-174">Enter the session</span></span>

  ```powershell
  Enter-PSSession $session
  ```

- <span data-ttu-id="8f7b8-175">Извлеките ZIP-файл</span><span class="sxs-lookup"><span data-stu-id="8f7b8-175">Extract the ZIP file</span></span>

  ```powershell
  # Insert the appropriate version.
  Expand-Archive -Path C:\powershell-<version>-win-x64.zip -DestinationPath "C:\PowerShell_<version>"
  ```

- <span data-ttu-id="8f7b8-176">Если вам требуется удаленное взаимодействие на основе WSMan, следуйте инструкциям, чтобы создать конечную точку удаленного взаимодействия с помощью [методики использования другого экземпляра](../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).</span><span class="sxs-lookup"><span data-stu-id="8f7b8-176">If you want WSMan-based remoting, follow the instructions to create a remoting endpoint using the ["another instance technique"](../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).</span></span>

## <a name="install-as-a-net-global-tool"></a><span data-ttu-id="8f7b8-177">Установка в качестве глобального средства .NET</span><span class="sxs-lookup"><span data-stu-id="8f7b8-177">Install as a .NET Global tool</span></span>

<span data-ttu-id="8f7b8-178">Если вы уже установили [пакет SDK для .NET Core](/dotnet/core/sdk), установите PowerShell как [глобальное средство .NET](/dotnet/core/tools/global-tools).</span><span class="sxs-lookup"><span data-stu-id="8f7b8-178">If you already have the [.NET Core SDK](/dotnet/core/sdk) installed, it's easy to install PowerShell as a [.NET Global tool](/dotnet/core/tools/global-tools).</span></span>

```
dotnet tool install --global PowerShell
```

<span data-ttu-id="8f7b8-179">Установщик инструмента dotnet добавляет `$env:USERPROFILE\dotnet\tools` в переменную среды `$env:PATH`.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-179">The dotnet tool installer adds `$env:USERPROFILE\dotnet\tools` to your `$env:PATH` environment variable.</span></span> <span data-ttu-id="8f7b8-180">Но в выполняющейся оболочке нет обновленной переменной `$env:PATH`.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-180">However, the currently running shell doesn't have the updated `$env:PATH`.</span></span> <span data-ttu-id="8f7b8-181">Вы можете запустить PowerShell из новой оболочки, введя `pwsh`.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-181">You can start PowerShell from a new shell by typing `pwsh`.</span></span>

## <a name="how-to-create-a-remoting-endpoint"></a><span data-ttu-id="8f7b8-182">Создание конечной точки удаленного взаимодействия</span><span class="sxs-lookup"><span data-stu-id="8f7b8-182">How to create a remoting endpoint</span></span>

<span data-ttu-id="8f7b8-183">PowerShell поддерживает протокол удаленного взаимодействия PowerShell (PSRP) через SSH и WSMan.</span><span class="sxs-lookup"><span data-stu-id="8f7b8-183">PowerShell supports the PowerShell Remoting Protocol (PSRP) over both WSMan and SSH.</span></span> <span data-ttu-id="8f7b8-184">Дополнительные сведения см. в разделе:</span><span class="sxs-lookup"><span data-stu-id="8f7b8-184">For more information, see:</span></span>

- <span data-ttu-id="8f7b8-185">[Удаленное взаимодействие через SSH в PowerShell Core][ssh-remoting]</span><span class="sxs-lookup"><span data-stu-id="8f7b8-185">[SSH Remoting in PowerShell Core][ssh-remoting]</span></span>
- <span data-ttu-id="8f7b8-186">[Удаленное взаимодействие через WSMan в PowerShell Core][wsman-remoting]</span><span class="sxs-lookup"><span data-stu-id="8f7b8-186">[WSMan Remoting in PowerShell Core][wsman-remoting]</span></span>

<!-- [download-center]: TODO -->

[releases]: https://github.com/PowerShell/PowerShell/releases
[ssh-remoting]: ../learn/remoting/SSH-Remoting-in-PowerShell-Core.md
[wsman-remoting]: ../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md
[AppVeyor]: https://ci.appveyor.com/project/PowerShell/powershell
