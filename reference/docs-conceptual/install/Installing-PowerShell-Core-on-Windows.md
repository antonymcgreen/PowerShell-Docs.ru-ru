---
title: Установка PowerShell Core в Windows
description: Сведения об установке PowerShell Core в Windows
ms.date: 08/06/2018
ms.openlocfilehash: 7c109c7e1848af2349092c1e70fe4a7a25be54b8
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402888"
---
# <a name="installing-powershell-core-on-windows"></a><span data-ttu-id="e18d3-103">Установка PowerShell Core в Windows</span><span class="sxs-lookup"><span data-stu-id="e18d3-103">Installing PowerShell Core on Windows</span></span>

## <a name="msi"></a><span data-ttu-id="e18d3-104">MSI</span><span class="sxs-lookup"><span data-stu-id="e18d3-104">MSI</span></span>

<span data-ttu-id="e18d3-105">Чтобы установить PowerShell на клиенте Windows или в Windows Server (работает в Windows 7 с пакетом обновления 1 (SP1), Server 2008 R2 и более поздних версий), скачайте пакет MSI из с нашей страницы [выпусков][] GitHub.</span><span class="sxs-lookup"><span data-stu-id="e18d3-105">To install PowerShell on a Windows client or Windows Server (works on Windows 7 SP1, Server 2008 R2, and later), download the MSI package from our GitHub [releases][] page.</span></span>

<span data-ttu-id="e18d3-106">MSI-файл выглядит примерно так: `PowerShell-<version>-win-<os-arch>.msi`
<!-- TODO: should be updated to point to the Download Center as well --></span><span class="sxs-lookup"><span data-stu-id="e18d3-106">The MSI file looks like this - `PowerShell-<version>-win-<os-arch>.msi`
<!-- TODO: should be updated to point to the Download Center as well --></span></span>

<span data-ttu-id="e18d3-107">После скачивания дважды щелкните установщик и следуйте инструкциям на экране.</span><span class="sxs-lookup"><span data-stu-id="e18d3-107">Once downloaded, double-click the installer and follow the prompts.</span></span>

<span data-ttu-id="e18d3-108">После установки в меню "Пуск" появляется ярлык.</span><span class="sxs-lookup"><span data-stu-id="e18d3-108">There is a shortcut placed in the Start Menu upon installation.</span></span>

- <span data-ttu-id="e18d3-109">По умолчанию пакет устанавливается в каталог `$env:ProgramFiles\PowerShell\<version>`.</span><span class="sxs-lookup"><span data-stu-id="e18d3-109">By default the package is installed to `$env:ProgramFiles\PowerShell\<version>`</span></span>
- <span data-ttu-id="e18d3-110">Вы можете запустить PowerShell с помощью меню "Пуск" или файла `$env:ProgramFiles\PowerShell\<version>\pwsh.exe`.</span><span class="sxs-lookup"><span data-stu-id="e18d3-110">You can launch PowerShell via the Start Menu or `$env:ProgramFiles\PowerShell\<version>\pwsh.exe`</span></span>

### <a name="prerequisites"></a><span data-ttu-id="e18d3-111">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="e18d3-111">Prerequisites</span></span>

<span data-ttu-id="e18d3-112">Чтобы включить удаленное взаимодействие PowerShell через WSMan, нужно выполнить следующие условия:</span><span class="sxs-lookup"><span data-stu-id="e18d3-112">To enable PowerShell remoting over WSMan, the following prerequisites need to be met:</span></span>

- <span data-ttu-id="e18d3-113">Установите [универсальную среду выполнения C](https://www.microsoft.com/download/details.aspx?id=50410) в версиях Windows, предшествующих Windows 10.</span><span class="sxs-lookup"><span data-stu-id="e18d3-113">Install the [Universal C Runtime](https://www.microsoft.com/download/details.aspx?id=50410) on Windows versions prior to Windows 10.</span></span>
  <span data-ttu-id="e18d3-114">Ее можно скачать самостоятельно или через Центр обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="e18d3-114">It is available via direct download or Windows Update.</span></span>
  <span data-ttu-id="e18d3-115">Поддерживаемые системы, где установлены все исправления (включая дополнительные пакеты), уже содержат ее.</span><span class="sxs-lookup"><span data-stu-id="e18d3-115">Fully patched (including optional packages), supported systems will already have this installed.</span></span>
- <span data-ttu-id="e18d3-116">Установите Windows Management Framework (WMF) 4.0 или более поздней версии в Windows 7 и Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="e18d3-116">Install the Windows Management Framework (WMF) 4.0 or newer on Windows 7 and Windows Server 2008 R2.</span></span>

## <a name="zip"></a><span data-ttu-id="e18d3-117">ZIP</span><span class="sxs-lookup"><span data-stu-id="e18d3-117">ZIP</span></span>

<span data-ttu-id="e18d3-118">Для поддержки расширенных сценариев развертывания доступны ZIP-архивы двоичных файлов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e18d3-118">PowerShell binary ZIP archives are provided to enable advanced deployment scenarios.</span></span>
<span data-ttu-id="e18d3-119">Следует отметить, что при использовании ZIP-архива проверка предварительных условий, как в случае с пакетом MSI, не производится.</span><span class="sxs-lookup"><span data-stu-id="e18d3-119">Be noted that when using the ZIP archive, you won't get the prerequisites check as in the MSI package.</span></span>
<span data-ttu-id="e18d3-120">Поэтому для правильной работы удаленного взаимодействия через WSMan в версиях Windows, предшествующих Windows 10, убедитесь, что [предварительные условия](#prerequisites) соблюдены.</span><span class="sxs-lookup"><span data-stu-id="e18d3-120">So in order for remoting over WSMan to work properly on Windows versions prior to Windows 10, you need to make sure the [prerequisites](#prerequisites) are met.</span></span>

## <a name="deploying-on-windows-iot"></a><span data-ttu-id="e18d3-121">Развертывание в Windows IoT</span><span class="sxs-lookup"><span data-stu-id="e18d3-121">Deploying on Windows IoT</span></span>

<span data-ttu-id="e18d3-122">Windows IoT поставляется с Windows PowerShell, который будет использоваться для развертывания PowerShell Core 6.</span><span class="sxs-lookup"><span data-stu-id="e18d3-122">Windows IoT already comes with Windows PowerShell which we will use to deploy PowerShell Core 6.</span></span>

1. <span data-ttu-id="e18d3-123">Создайте `PSSession` для целевого устройства</span><span class="sxs-lookup"><span data-stu-id="e18d3-123">Create `PSSession` to target device</span></span>

   ```powershell
   $s = New-PSSession -ComputerName <deviceIp> -Credential Administrator
   ```

2. <span data-ttu-id="e18d3-124">Скопируйте ZIP-файл на устройство</span><span class="sxs-lookup"><span data-stu-id="e18d3-124">Copy the ZIP package to the device</span></span>

   ```powershell
   # change the destination to however you had partitioned it with sufficient
   # space for the zip and the unzipped contents
   # the path should be local to the device
   Copy-Item .\PowerShell-6.1.0-win-arm32.zip -Destination u:\users\administrator\Downloads -ToSession $s
   ```

3. <span data-ttu-id="e18d3-125">Присоединитесь к устройству и извлеките архив</span><span class="sxs-lookup"><span data-stu-id="e18d3-125">Connect to the device and expand the archive</span></span>

   ```powershell
   Enter-PSSession $s
   Set-Location u:\users\administrator\downloads
   Expand-Archive .\PowerShell-6.1.0-win-arm32.zip
   ```

4. <span data-ttu-id="e18d3-126">Удаленное взаимодействие в PowerShell Core 6</span><span class="sxs-lookup"><span data-stu-id="e18d3-126">Setup remoting to PowerShell Core 6</span></span>

   ```powershell
   Set-Location .\PowerShell-6.1.0-win-arm32
   # Be sure to use the -PowerShellHome parameter otherwise it'll try to create a new
   # endpoint with Windows PowerShell 5.1
   .\Install-PowerShellRemoting.ps1 -PowerShellHome .
   # You'll get an error message and will be disconnected from the device because it has to restart WinRM
   ```

5. <span data-ttu-id="e18d3-127">Подключение к конечной точке PowerShell Core 6 на устройстве</span><span class="sxs-lookup"><span data-stu-id="e18d3-127">Connect to PowerShell Core 6 endpoint on device</span></span>

   ```powershell
   # Be sure to use the -Configuration parameter.  If you omit it, you will connect to Windows PowerShell 5.1
   Enter-PSSession -ComputerName <deviceIp> -Credential Administrator -Configuration powershell.6.1.0
   ```

## <a name="deploying-on-nano-server"></a><span data-ttu-id="e18d3-128">Развертывание на Nano Server</span><span class="sxs-lookup"><span data-stu-id="e18d3-128">Deploying on Nano Server</span></span>

<span data-ttu-id="e18d3-129">Эти инструкции предполагают, что версия PowerShell уже запущена на образе Nano Server и была создана с помощью [Nano Server Image Builder](/windows-server/get-started/deploy-nano-server).</span><span class="sxs-lookup"><span data-stu-id="e18d3-129">These instructions assume that a version of PowerShell is already running on the Nano Server image and that it has been generated by the [Nano Server Image Builder](/windows-server/get-started/deploy-nano-server).</span></span>
<span data-ttu-id="e18d3-130">Nano Server является "виртуальной" ОС.</span><span class="sxs-lookup"><span data-stu-id="e18d3-130">Nano Server is a "headless" OS.</span></span> <span data-ttu-id="e18d3-131">Двоичные файлы ядра можно развернуть двумя разными методами.</span><span class="sxs-lookup"><span data-stu-id="e18d3-131">Core binaries can be deploy using two different methods.</span></span>

1. <span data-ttu-id="e18d3-132">Автономно — подключите виртуальный жесткий диск Nano Server и распакуйте содержимое ZIP-файла в выбранное расположение в этом образе.</span><span class="sxs-lookup"><span data-stu-id="e18d3-132">Offline - Mount the Nano Server VHD and unzip the contents of the zip file to your chosen location within the mounted image.</span></span>
2. <span data-ttu-id="e18d3-133">В сети — передайте ZIP-файл через сеанс PowerShell и распакуйте его в выбранное расположение.</span><span class="sxs-lookup"><span data-stu-id="e18d3-133">Online - Transfer the zip file over a PowerShell Session and unzip it in your chosen location.</span></span>

<span data-ttu-id="e18d3-134">В обоих случаях вам понадобится ZIP-пакет выпуска x64 Windows 10 и потребуется выполнять команды в экземпляре PowerShell с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="e18d3-134">In both cases, you will need the Windows 10 x64 ZIP release package and will need to run the commands within an "Administrator" PowerShell instance.</span></span>

### <a name="offline-deployment-of-powershell-core"></a><span data-ttu-id="e18d3-135">Автономное развертывание PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="e18d3-135">Offline Deployment of PowerShell Core</span></span>

1. <span data-ttu-id="e18d3-136">С помощью любой служебной программы ZIP распакуйте пакет в каталог, находящийся внутри подключенного образа Nano Server.</span><span class="sxs-lookup"><span data-stu-id="e18d3-136">Use your favorite zip utility to unzip the package to a directory within the mounted Nano Server image.</span></span>
2. <span data-ttu-id="e18d3-137">Отключите образ и загрузите его.</span><span class="sxs-lookup"><span data-stu-id="e18d3-137">Unmount the image and boot it.</span></span>
3. <span data-ttu-id="e18d3-138">Подключитесь к входящему экземпляру Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e18d3-138">Connect to the inbox instance of Windows PowerShell.</span></span>
4. <span data-ttu-id="e18d3-139">Следуйте инструкциям, чтобы создать конечную точку удаленного взаимодействия с помощью [методики использования другого экземпляра](../learn/remoting/wsman-remoting-in-powershell-core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).</span><span class="sxs-lookup"><span data-stu-id="e18d3-139">Follow the instructions to create a remoting endpoint using the ["another instance technique"](../learn/remoting/wsman-remoting-in-powershell-core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).</span></span>

### <a name="online-deployment-of-powershell-core"></a><span data-ttu-id="e18d3-140">Автономное PowerShell Core в сети</span><span class="sxs-lookup"><span data-stu-id="e18d3-140">Online Deployment of PowerShell Core</span></span>

<span data-ttu-id="e18d3-141">В следующих шагах описываются инструкции развертывания PowerShell Core в запущенном экземпляре Nano Server, а также настройка его удаленной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="e18d3-141">The following steps guide you through the deployment of PowerShell Core to a running instance of Nano Server and the configuration of its remote endpoint.</span></span>

- <span data-ttu-id="e18d3-142">Подключитесь к входящему экземпляру Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e18d3-142">Connect to the inbox instance of Windows PowerShell</span></span>

  ```powershell
  $session = New-PSSession -ComputerName <Nano Server IP address> -Credential <An Administrator account on the system>
  ```

- <span data-ttu-id="e18d3-143">Скопируйте файл на экземпляр Nano Server:</span><span class="sxs-lookup"><span data-stu-id="e18d3-143">Copy the file to the Nano Server instance</span></span>

  ```powershell
  Copy-Item <local PS Core download location>\powershell-<version>-win-x64.zip c:\ -ToSession $session
  ```

- <span data-ttu-id="e18d3-144">Войдите в сеанс:</span><span class="sxs-lookup"><span data-stu-id="e18d3-144">Enter the session</span></span>

  ```powershell
  Enter-PSSession $session
  ```

- <span data-ttu-id="e18d3-145">Извлеките ZIP-файл</span><span class="sxs-lookup"><span data-stu-id="e18d3-145">Extract the ZIP file</span></span>

  ```powershell
  # Insert the appropriate version.
  Expand-Archive -Path C:\powershell-<version>-win-x64.zip -DestinationPath "C:\PowerShellCore_<version>"
  ```

- <span data-ttu-id="e18d3-146">Если вам требуется удаленное взаимодействие на основе WSMan, следуйте инструкциям, чтобы создать конечную точку удаленного взаимодействия с помощью [методики использования другого экземпляра](../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).</span><span class="sxs-lookup"><span data-stu-id="e18d3-146">If you want WSMan-based remoting, follow the instructions to create a remoting endpoint using the ["another instance technique"](../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).</span></span>

## <a name="instructions-to-create-a-remoting-endpoint"></a><span data-ttu-id="e18d3-147">Инструкции по созданию конечной точки удаленного взаимодействия</span><span class="sxs-lookup"><span data-stu-id="e18d3-147">Instructions to Create a Remoting Endpoint</span></span>

<span data-ttu-id="e18d3-148">PowerShell Core поддерживает протокол удаленного взаимодействия PowerShell (PSRP) через SSH и WSMan.</span><span class="sxs-lookup"><span data-stu-id="e18d3-148">PowerShell Core supports the PowerShell Remoting Protocol (PSRP) over both WSMan and SSH.</span></span>
<span data-ttu-id="e18d3-149">Дополнительная информация:</span><span class="sxs-lookup"><span data-stu-id="e18d3-149">For more information, see:</span></span>

- <span data-ttu-id="e18d3-150">[Удаленное взаимодействие через SSH в PowerShell Core][ssh-remoting]</span><span class="sxs-lookup"><span data-stu-id="e18d3-150">[SSH Remoting in PowerShell Core][ssh-remoting]</span></span>
- <span data-ttu-id="e18d3-151">[Удаленное взаимодействие через WSMan в PowerShell Core][wsman-remoting]</span><span class="sxs-lookup"><span data-stu-id="e18d3-151">[WSMan Remoting in PowerShell Core][wsman-remoting]</span></span>

## <a name="artifact-installation-instructions"></a><span data-ttu-id="e18d3-152">Указания по установке артефакта</span><span class="sxs-lookup"><span data-stu-id="e18d3-152">Artifact Installation Instructions</span></span>

<span data-ttu-id="e18d3-153">Мы публикуем архив с кодом CoreCLR для каждой сборки CI с [AppVeyor][].</span><span class="sxs-lookup"><span data-stu-id="e18d3-153">We publish an archive with CoreCLR bits on every CI build with [AppVeyor][].</span></span>

<span data-ttu-id="e18d3-154">Чтобы установить PowerShell Core из CoreCLR Artifact, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="e18d3-154">To install PowerShell Core from the CoreCLR Artifact:</span></span>

1. <span data-ttu-id="e18d3-155">Скачайте ZIP-пакет с вкладки **Артефакты** конкретной сборки.</span><span class="sxs-lookup"><span data-stu-id="e18d3-155">Download ZIP package from **artifacts** tab of the particular build.</span></span>
2. <span data-ttu-id="e18d3-156">Разблокируйте ZIP-файл: щелкните правой кнопкой мыши в проводнике, выберите "Свойства", установите флажок "Разблокировать" и выберите "Применить".</span><span class="sxs-lookup"><span data-stu-id="e18d3-156">Unblock ZIP file: right-click in File Explorer -> Properties -> check 'Unblock' box -> apply</span></span>
3. <span data-ttu-id="e18d3-157">Извлеките содержимое ZIP-файла в каталог `bin`.</span><span class="sxs-lookup"><span data-stu-id="e18d3-157">Extract zip file to `bin` directory</span></span>
4. `./bin/pwsh.exe`

<!-- [download-center]: TODO -->

[выпусков]: https://github.com/PowerShell/PowerShell/releases
[releases]: https://github.com/PowerShell/PowerShell/releases
[ssh-remoting]: ../core-powershell/SSH-Remoting-in-PowerShell-Core.md
[wsman-remoting]: ../core-powershell/WSMan-Remoting-in-PowerShell-Core.md
[AppVeyor]: https://ci.appveyor.com/project/PowerShell/powershell
