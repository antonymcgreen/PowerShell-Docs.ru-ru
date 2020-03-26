---
title: Установка PowerShell в Windows
description: Сведения об установке PowerShell в Windows
ms.date: 08/06/2018
ms.openlocfilehash: bb0971b6c4ac99bde70b226da2becf2f4ed82083
ms.sourcegitcommit: d36db3a1bc44aee6bc97422b557041c3aece4c67
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80082778"
---
# <a name="installing-powershell-on-windows"></a><span data-ttu-id="f0c31-103">Установка PowerShell в Windows</span><span class="sxs-lookup"><span data-stu-id="f0c31-103">Installing PowerShell on Windows</span></span>

<span data-ttu-id="f0c31-104">Есть несколько способов установки PowerShell в Windows.</span><span class="sxs-lookup"><span data-stu-id="f0c31-104">There are multiple ways to install PowerShell in Windows.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f0c31-105">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="f0c31-105">Prerequisites</span></span>

<span data-ttu-id="f0c31-106">Чтобы включить удаленное взаимодействие PowerShell через WSMan, нужно выполнить следующие условия:</span><span class="sxs-lookup"><span data-stu-id="f0c31-106">To enable PowerShell remoting over WSMan, the following prerequisites need to be met:</span></span>

- <span data-ttu-id="f0c31-107">Установите [универсальную среду выполнения C](https://www.microsoft.com/download/details.aspx?id=50410) в версиях Windows, предшествующих Windows 10.</span><span class="sxs-lookup"><span data-stu-id="f0c31-107">Install the [Universal C Runtime](https://www.microsoft.com/download/details.aspx?id=50410) on Windows versions prior to Windows 10.</span></span> <span data-ttu-id="f0c31-108">Ее можно скачать самостоятельно или через Центр обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="f0c31-108">It is available via direct download or Windows Update.</span></span> <span data-ttu-id="f0c31-109">Поддерживаемые системы, где установлены все исправления (включая дополнительные пакеты), уже содержат ее.</span><span class="sxs-lookup"><span data-stu-id="f0c31-109">Fully patched (including optional packages), supported systems will already have this installed.</span></span>
- <span data-ttu-id="f0c31-110">Установите Windows Management Framework (WMF) 4.0 или более поздней версии в Windows 7 и Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="f0c31-110">Install the Windows Management Framework (WMF) 4.0 or newer on Windows 7 and Windows Server 2008 R2.</span></span> <span data-ttu-id="f0c31-111">Подробные сведения о WMF см. в статье с [обзором WMF](/powershell/scripting/wmf/overview).</span><span class="sxs-lookup"><span data-stu-id="f0c31-111">For more information about WMF, see [WMF Overview](/powershell/scripting/wmf/overview).</span></span>

## <a name="installing-the-msi-package"></a><span data-ttu-id="f0c31-112"><a id="msi" />Установка пакета MSI</span><span class="sxs-lookup"><span data-stu-id="f0c31-112"><a id="msi" />Installing the MSI package</span></span>

<span data-ttu-id="f0c31-113">Чтобы установить PowerShell на клиенте Windows или в Windows Server (работает в Windows 7 с пакетом обновления 1 (SP1), Server 2008 R2 и более поздних версий), скачайте пакет MSI из с нашей страницы [выпусков][releases] GitHub.</span><span class="sxs-lookup"><span data-stu-id="f0c31-113">To install PowerShell on a Windows client or Windows Server (works on Windows 7 SP1, Server 2008 R2, and later), download the MSI package from our GitHub [releases][releases] page.</span></span> <span data-ttu-id="f0c31-114">Прокрутите вниз до раздела **Ресурсы** в выпуске, который вы хотите установить.</span><span class="sxs-lookup"><span data-stu-id="f0c31-114">Scroll down to the **Assets** section of the Release you want to install.</span></span> <span data-ttu-id="f0c31-115">Раздел "Ресурсы" может быть свернут. В таком случае щелкните его, чтобы развернуть.</span><span class="sxs-lookup"><span data-stu-id="f0c31-115">The Assets section may be collapsed, so you may need to click to expand it.</span></span>

<span data-ttu-id="f0c31-116">MSI-файл имеет следующий вид: `PowerShell-<version>-win-<os-arch>.msi`.</span><span class="sxs-lookup"><span data-stu-id="f0c31-116">The MSI file looks like this - `PowerShell-<version>-win-<os-arch>.msi`</span></span>

<span data-ttu-id="f0c31-117">После скачивания дважды щелкните установщик и следуйте инструкциям на экране.</span><span class="sxs-lookup"><span data-stu-id="f0c31-117">Once downloaded, double-click the installer and follow the prompts.</span></span>

<span data-ttu-id="f0c31-118">Программа установки создает ярлык в меню Windows "Пуск".</span><span class="sxs-lookup"><span data-stu-id="f0c31-118">The installer creates a shortcut in the Windows Start Menu.</span></span>

- <span data-ttu-id="f0c31-119">По умолчанию пакет устанавливается в каталог `$env:ProgramFiles\PowerShell\<version>`.</span><span class="sxs-lookup"><span data-stu-id="f0c31-119">By default the package is installed to `$env:ProgramFiles\PowerShell\<version>`</span></span>
- <span data-ttu-id="f0c31-120">Вы можете запустить PowerShell с помощью меню "Пуск" или файла `$env:ProgramFiles\PowerShell\<version>\pwsh.exe`.</span><span class="sxs-lookup"><span data-stu-id="f0c31-120">You can launch PowerShell via the Start Menu or `$env:ProgramFiles\PowerShell\<version>\pwsh.exe`</span></span>

> [!NOTE]
> <span data-ttu-id="f0c31-121">PowerShell 7 устанавливается в новом каталоге и работает параллельно с Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="f0c31-121">PowerShell 7 installs to a new directory and runs side-by-side with Windows PowerShell 5.1.</span></span> <span data-ttu-id="f0c31-122">Для PowerShell Core 6.x версия PowerShell 7 является обновлением на месте, при установке которого PowerShell Core 6.x удаляется.</span><span class="sxs-lookup"><span data-stu-id="f0c31-122">For PowerShell Core 6.x, PowerShell 7 is an in-place upgrade that removes PowerShell Core 6.x.</span></span>
>
> - <span data-ttu-id="f0c31-123">PowerShell 7 устанавливается в папке `%programfiles%\PowerShell\7`.</span><span class="sxs-lookup"><span data-stu-id="f0c31-123">PowerShell 7 is installed to `%programfiles%\PowerShell\7`</span></span>
> - <span data-ttu-id="f0c31-124">Папка `%programfiles%\PowerShell\7` добавляется в переменную `$env:PATH`.</span><span class="sxs-lookup"><span data-stu-id="f0c31-124">The `%programfiles%\PowerShell\7` folder is added to `$env:PATH`</span></span>
> - <span data-ttu-id="f0c31-125">Папка `%programfiles%\PowerShell\6` удалена.</span><span class="sxs-lookup"><span data-stu-id="f0c31-125">The `%programfiles%\PowerShell\6` folder is deleted</span></span>
>
> <span data-ttu-id="f0c31-126">Если вы хотите запускать PowerShell 6 параллельно с PowerShell 7, переустановите PowerShell 6 с использованием [ZIP-архива](#zip).</span><span class="sxs-lookup"><span data-stu-id="f0c31-126">If you need to run PowerShell 6 side-by-side with PowerShell 7, reinstall PowerShell 6 using the [ZIP install](#zip) method.</span></span>

### <a name="administrative-install-from-the-command-line"></a><span data-ttu-id="f0c31-127">Установка администратором из командной строки</span><span class="sxs-lookup"><span data-stu-id="f0c31-127">Administrative install from the command line</span></span>

<span data-ttu-id="f0c31-128">Пакеты MSI можно установить из командной строки.</span><span class="sxs-lookup"><span data-stu-id="f0c31-128">MSI packages can be installed from the command line.</span></span> <span data-ttu-id="f0c31-129">Это позволяет администраторам развертывать пакеты без участия пользователя.</span><span class="sxs-lookup"><span data-stu-id="f0c31-129">This allows administrators to deploy packages without user interaction.</span></span> <span data-ttu-id="f0c31-130">Пакет MSI для PowerShell включает в себя следующие свойства для управления параметрами установки:</span><span class="sxs-lookup"><span data-stu-id="f0c31-130">The MSI package for PowerShell includes the following properties to control the installation options:</span></span>

- <span data-ttu-id="f0c31-131">**ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL**. Это свойство позволяет добавлять пункт **Открыть PowerShell** в контекстное меню проводника.</span><span class="sxs-lookup"><span data-stu-id="f0c31-131">**ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL** - This property controls the option for adding the **Open PowerShell** item to the context menu in Windows Explorer.</span></span>
- <span data-ttu-id="f0c31-132">**ENABLE_PSREMOTING**. Это свойство позволяет включать удаленное взаимодействие PowerShell во время установки.</span><span class="sxs-lookup"><span data-stu-id="f0c31-132">**ENABLE_PSREMOTING** - This property controls the option for enabling PowerShell remoting during installation.</span></span>
- <span data-ttu-id="f0c31-133">**REGISTER_MANIFEST**. Это свойство позволяет регистрировать манифест ведения журнала событий Windows.</span><span class="sxs-lookup"><span data-stu-id="f0c31-133">**REGISTER_MANIFEST** - This property controls the option for registering the Windows Event Logging manifest.</span></span>

<span data-ttu-id="f0c31-134">В следующих примерах показано, как выполнить автоматическую установку PowerShell со всеми включенными параметрами установки.</span><span class="sxs-lookup"><span data-stu-id="f0c31-134">The following examples shows how to silently install PowerShell with all the install options enabled.</span></span>

```powershell
msiexec.exe /package PowerShell-<version>-win-<os-arch>.msi /quiet ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL=1 ENABLE_PSREMOTING=1 REGISTER_MANIFEST=1
```

<span data-ttu-id="f0c31-135">См. [полный список параметров командной строки для Msiexec.exe](/windows/desktop/Msi/command-line-options).</span><span class="sxs-lookup"><span data-stu-id="f0c31-135">For a full list of command line options for Msiexec.exe, see [Command line options](/windows/desktop/Msi/command-line-options).</span></span>

## <a name="installing-the-msix-package"></a><span data-ttu-id="f0c31-136"><a id="msix" />Установка пакета MSIX</span><span class="sxs-lookup"><span data-stu-id="f0c31-136"><a id="msix" />Installing the MSIX package</span></span>

<span data-ttu-id="f0c31-137">Чтобы вручную установить пакет MSIX на клиент Windows 10, скачайте пакет MSIX на странице GitHub с [выпусками][releases].</span><span class="sxs-lookup"><span data-stu-id="f0c31-137">To manually install the MSIX package on a Windows 10 client, download the MSIX package from our GitHub [releases][releases] page.</span></span> <span data-ttu-id="f0c31-138">Прокрутите вниз до раздела **Ресурсы** в выпуске, который вы хотите установить.</span><span class="sxs-lookup"><span data-stu-id="f0c31-138">Scroll down to the **Assets** section of the Release you want to install.</span></span> <span data-ttu-id="f0c31-139">Раздел "Ресурсы" может быть свернут. В таком случае щелкните его, чтобы развернуть.</span><span class="sxs-lookup"><span data-stu-id="f0c31-139">The Assets section may be collapsed, so you may need to click to expand it.</span></span>

<span data-ttu-id="f0c31-140">MSIX-файл выглядит примерно так: `PowerShell-<version>-win-<os-arch>.msix`</span><span class="sxs-lookup"><span data-stu-id="f0c31-140">The MSIX file looks like this - `PowerShell-<version>-win-<os-arch>.msix`</span></span>

<span data-ttu-id="f0c31-141">После скачивания вы не сможете просто дважды щелкнуть установщик, так как для этого пакета требуются невиртуализованные ресурсы.</span><span class="sxs-lookup"><span data-stu-id="f0c31-141">Once downloaded, you cannot simply double-click on the installer as this package requires use of un-virtualized resources.</span></span>  <span data-ttu-id="f0c31-142">Для установки используйте командлет `Add-AppxPackage`.</span><span class="sxs-lookup"><span data-stu-id="f0c31-142">To install, you must use the `Add-AppxPackage` cmdlet:</span></span>

```powershell
Add-AppxPackage PowerShell-<version>-win-<os-arch>.msix
```

## <a name="installing-the-zip-package"></a><span data-ttu-id="f0c31-143"><a id="zip" />Установка ZIP-пакета</span><span class="sxs-lookup"><span data-stu-id="f0c31-143"><a id="zip" />Installing the ZIP package</span></span>

<span data-ttu-id="f0c31-144">Для поддержки расширенных сценариев развертывания доступны ZIP-архивы двоичных файлов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f0c31-144">PowerShell binary ZIP archives are provided to enable advanced deployment scenarios.</span></span> <span data-ttu-id="f0c31-145">Следует отметить, что при использовании ZIP-архива проверка предварительных условий, как в случае с пакетом MSI, не производится.</span><span class="sxs-lookup"><span data-stu-id="f0c31-145">Be noted that when using the ZIP archive, you won't get the prerequisites check as in the MSI package.</span></span> <span data-ttu-id="f0c31-146">Для правильной настройки удаленного взаимодействия с помощью WSMan необходимо выполнить [предварительные требования](#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="f0c31-146">For remoting over WSMan to work properly, ensure that you have met the [prerequisites](#prerequisites).</span></span>

## <a name="deploying-on-windows-iot"></a><span data-ttu-id="f0c31-147">Развертывание в Windows IoT</span><span class="sxs-lookup"><span data-stu-id="f0c31-147">Deploying on Windows IoT</span></span>

<span data-ttu-id="f0c31-148">Windows IoT поставляется с Windows PowerShell, который можно использовать для развертывания PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="f0c31-148">Windows IoT already comes with Windows PowerShell which we can use to deploy PowerShell 7.</span></span>

1. <span data-ttu-id="f0c31-149">Создайте `PSSession` для целевого устройства</span><span class="sxs-lookup"><span data-stu-id="f0c31-149">Create `PSSession` to target device</span></span>

   ```powershell
   Set-Item -Path WSMan:\localhost\Client\TrustedHosts <deviceip>
   $S = New-PSSession -ComputerName <deviceIp> -Credential Administrator
   ```

2. <span data-ttu-id="f0c31-150">Скопируйте ZIP-файл на устройство</span><span class="sxs-lookup"><span data-stu-id="f0c31-150">Copy the ZIP package to the device</span></span>

   ```powershell
   # change the destination to however you had partitioned it with sufficient
   # space for the zip and the unzipped contents
   # the path should be local to the device
   Copy-Item .\PowerShell-<version>-win-<os-arch>.zip -Destination u:\users\administrator\Downloads -ToSession $s
   ```

3. <span data-ttu-id="f0c31-151">Присоединитесь к устройству и извлеките архив</span><span class="sxs-lookup"><span data-stu-id="f0c31-151">Connect to the device and expand the archive</span></span>

   ```powershell
   Enter-PSSession $s
   Set-Location u:\users\administrator\downloads
   Expand-Archive .\PowerShell-<version>-win-<os-arch>.zip
   ```

4. <span data-ttu-id="f0c31-152">Удаленное взаимодействие в PowerShell 7</span><span class="sxs-lookup"><span data-stu-id="f0c31-152">Setup remoting to PowerShell 7</span></span>

   ```powershell
   Set-Location .\PowerShell-<version>-win-<os-arch>
   # Be sure to use the -PowerShellHome parameter otherwise it'll try to create a new
   # endpoint with Windows PowerShell 5.1
   .\Install-PowerShellRemoting.ps1 -PowerShellHome .
   # You'll get an error message and will be disconnected from the device because it has to restart WinRM
   ```

5. <span data-ttu-id="f0c31-153">Подключение к конечной точке PowerShell 7 на устройстве</span><span class="sxs-lookup"><span data-stu-id="f0c31-153">Connect to PowerShell 7 endpoint on device</span></span>

   ```powershell
   # Be sure to use the -Configuration parameter.  If you omit it, you will connect to Windows PowerShell 5.1
   Enter-PSSession -ComputerName <deviceIp> -Credential Administrator -Configuration powershell.<version>
   ```

## <a name="deploying-on-nano-server"></a><span data-ttu-id="f0c31-154">Развертывание на Nano Server</span><span class="sxs-lookup"><span data-stu-id="f0c31-154">Deploying on Nano Server</span></span>

<span data-ttu-id="f0c31-155">Эти инструкции предполагают, что версия PowerShell уже запущена на образе Nano Server и была создана с помощью [Nano Server Image Builder](/windows-server/get-started/deploy-nano-server).</span><span class="sxs-lookup"><span data-stu-id="f0c31-155">These instructions assume that a version of PowerShell is already running on the Nano Server image and that it has been generated by the [Nano Server Image Builder](/windows-server/get-started/deploy-nano-server).</span></span>
<span data-ttu-id="f0c31-156">Nano Server является "виртуальной" ОС.</span><span class="sxs-lookup"><span data-stu-id="f0c31-156">Nano Server is a "headless" OS.</span></span> <span data-ttu-id="f0c31-157">Двоичные файлы PowerShell можно развернуть двумя разными способами.</span><span class="sxs-lookup"><span data-stu-id="f0c31-157">PowerShell binaries can be deploy using two different methods.</span></span>

1. <span data-ttu-id="f0c31-158">Автономно — подключите виртуальный жесткий диск Nano Server и распакуйте содержимое ZIP-файла в выбранное расположение в этом образе.</span><span class="sxs-lookup"><span data-stu-id="f0c31-158">Offline - Mount the Nano Server VHD and unzip the contents of the zip file to your chosen location within the mounted image.</span></span>
2. <span data-ttu-id="f0c31-159">В сети — передайте ZIP-файл через сеанс PowerShell и распакуйте его в выбранное расположение.</span><span class="sxs-lookup"><span data-stu-id="f0c31-159">Online - Transfer the zip file over a PowerShell Session and unzip it in your chosen location.</span></span>

<span data-ttu-id="f0c31-160">В обоих случаях вам понадобится ZIP-пакет выпуска x64 Windows 10 и потребуется выполнять команды в экземпляре PowerShell с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="f0c31-160">In both cases, you will need the Windows 10 x64 ZIP release package and will need to run the commands within an "Administrator" PowerShell instance.</span></span>

### <a name="offline-deployment-of-powershell"></a><span data-ttu-id="f0c31-161">Автономное развертывание PowerShell</span><span class="sxs-lookup"><span data-stu-id="f0c31-161">Offline Deployment of PowerShell</span></span>

1. <span data-ttu-id="f0c31-162">С помощью любой служебной программы ZIP распакуйте пакет в каталог, находящийся внутри подключенного образа Nano Server.</span><span class="sxs-lookup"><span data-stu-id="f0c31-162">Use your favorite zip utility to unzip the package to a directory within the mounted Nano Server image.</span></span>
2. <span data-ttu-id="f0c31-163">Отключите образ и загрузите его.</span><span class="sxs-lookup"><span data-stu-id="f0c31-163">Unmount the image and boot it.</span></span>
3. <span data-ttu-id="f0c31-164">Подключитесь к входящему экземпляру Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f0c31-164">Connect to the inbox instance of Windows PowerShell.</span></span>
4. <span data-ttu-id="f0c31-165">Следуйте инструкциям, чтобы создать конечную точку удаленного взаимодействия с помощью [методики использования другого экземпляра](../learn/remoting/wsman-remoting-in-powershell-core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).</span><span class="sxs-lookup"><span data-stu-id="f0c31-165">Follow the instructions to create a remoting endpoint using the ["another instance technique"](../learn/remoting/wsman-remoting-in-powershell-core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).</span></span>

### <a name="online-deployment-of-powershell"></a><span data-ttu-id="f0c31-166">Автономное PowerShell в сети</span><span class="sxs-lookup"><span data-stu-id="f0c31-166">Online Deployment of PowerShell</span></span>

<span data-ttu-id="f0c31-167">В следующих шагах описываются инструкции развертывания PowerShell на запущенном экземпляре Nano Server, а также настройка его удаленной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="f0c31-167">The following steps guide you through the deployment of PowerShell to a running instance of Nano Server and the configuration of its remote endpoint.</span></span>

- <span data-ttu-id="f0c31-168">Подключитесь к входящему экземпляру Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f0c31-168">Connect to the inbox instance of Windows PowerShell</span></span>

  ```powershell
  $session = New-PSSession -ComputerName <Nano Server IP address> -Credential <An Administrator account on the system>
  ```

- <span data-ttu-id="f0c31-169">Скопируйте файл на экземпляр Nano Server:</span><span class="sxs-lookup"><span data-stu-id="f0c31-169">Copy the file to the Nano Server instance</span></span>

  ```powershell
  Copy-Item <local PS Core download location>\powershell-<version>-win-x64.zip c:\ -ToSession $session
  ```

- <span data-ttu-id="f0c31-170">Войдите в сеанс:</span><span class="sxs-lookup"><span data-stu-id="f0c31-170">Enter the session</span></span>

  ```powershell
  Enter-PSSession $session
  ```

- <span data-ttu-id="f0c31-171">Извлеките ZIP-файл</span><span class="sxs-lookup"><span data-stu-id="f0c31-171">Extract the ZIP file</span></span>

  ```powershell
  # Insert the appropriate version.
  Expand-Archive -Path C:\powershell-<version>-win-x64.zip -DestinationPath "C:\PowerShell_<version>"
  ```

- <span data-ttu-id="f0c31-172">Если вам требуется удаленное взаимодействие на основе WSMan, следуйте инструкциям, чтобы создать конечную точку удаленного взаимодействия с помощью [методики использования другого экземпляра](../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).</span><span class="sxs-lookup"><span data-stu-id="f0c31-172">If you want WSMan-based remoting, follow the instructions to create a remoting endpoint using the ["another instance technique"](../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).</span></span>

## <a name="install-as-a-net-global-tool"></a><span data-ttu-id="f0c31-173">Установка в качестве глобального средства .NET</span><span class="sxs-lookup"><span data-stu-id="f0c31-173">Install as a .NET Global tool</span></span>

<span data-ttu-id="f0c31-174">Если вы уже установили [пакет SDK для .NET Core](/dotnet/core/sdk), установите PowerShell как [глобальное средство .NET](/dotnet/core/tools/global-tools).</span><span class="sxs-lookup"><span data-stu-id="f0c31-174">If you already have the [.NET Core SDK](/dotnet/core/sdk) installed, it's easy to install PowerShell as a [.NET Global tool](/dotnet/core/tools/global-tools).</span></span>

```
dotnet tool install --global PowerShell
```

<span data-ttu-id="f0c31-175">Установщик инструмента dotnet добавляет `$env:USERPROFILE\dotnet\tools` в переменную среды `$env:PATH`.</span><span class="sxs-lookup"><span data-stu-id="f0c31-175">The dotnet tool installer adds `$env:USERPROFILE\dotnet\tools` to your `$env:PATH` environment variable.</span></span> <span data-ttu-id="f0c31-176">Но в выполняющейся оболочке отсутствует обновленная переменная `$env:PATH`.</span><span class="sxs-lookup"><span data-stu-id="f0c31-176">However, the currently running shell does not have the updated `$env:PATH`.</span></span> <span data-ttu-id="f0c31-177">Вы можете запустить PowerShell из новой оболочки, введя `pwsh`.</span><span class="sxs-lookup"><span data-stu-id="f0c31-177">You should be able to start PowerShell from a new shell by typing `pwsh`.</span></span>

## <a name="how-to-create-a-remoting-endpoint"></a><span data-ttu-id="f0c31-178">Создание конечной точки удаленного взаимодействия</span><span class="sxs-lookup"><span data-stu-id="f0c31-178">How to create a remoting endpoint</span></span>

<span data-ttu-id="f0c31-179">PowerShell поддерживает протокол удаленного взаимодействия PowerShell (PSRP) через SSH и WSMan.</span><span class="sxs-lookup"><span data-stu-id="f0c31-179">PowerShell supports the PowerShell Remoting Protocol (PSRP) over both WSMan and SSH.</span></span> <span data-ttu-id="f0c31-180">Дополнительные сведения см. в разделе:</span><span class="sxs-lookup"><span data-stu-id="f0c31-180">For more information, see:</span></span>

- <span data-ttu-id="f0c31-181">[Удаленное взаимодействие через SSH в PowerShell Core][ssh-remoting]</span><span class="sxs-lookup"><span data-stu-id="f0c31-181">[SSH Remoting in PowerShell Core][ssh-remoting]</span></span>
- <span data-ttu-id="f0c31-182">[Удаленное взаимодействие через WSMan в PowerShell Core][wsman-remoting]</span><span class="sxs-lookup"><span data-stu-id="f0c31-182">[WSMan Remoting in PowerShell Core][wsman-remoting]</span></span>

<!-- [download-center]: TODO -->

[releases]: https://github.com/PowerShell/PowerShell/releases
[ssh-remoting]: ../learn/remoting/SSH-Remoting-in-PowerShell-Core.md
[wsman-remoting]: ../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md
[AppVeyor]: https://ci.appveyor.com/project/PowerShell/powershell
