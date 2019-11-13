---
title: Установка PowerShell Core в Windows
description: Сведения об установке PowerShell Core в Windows
ms.date: 08/06/2018
ms.openlocfilehash: c06eba06e376c3f795ab9c0fae9270cf6cf8f2ce
ms.sourcegitcommit: 36e4c79afda2ce11febd93951e143687245f0b50
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/02/2019
ms.locfileid: "73444457"
---
# <a name="installing-powershell-core-on-windows"></a><span data-ttu-id="22e14-103">Установка PowerShell Core в Windows</span><span class="sxs-lookup"><span data-stu-id="22e14-103">Installing PowerShell Core on Windows</span></span>

<span data-ttu-id="22e14-104">Есть несколько способов установки PowerShell Core в Windows.</span><span class="sxs-lookup"><span data-stu-id="22e14-104">There are multiple ways to install PowerShell Core in Windows.</span></span>

> [!TIP]
> <span data-ttu-id="22e14-105">Если вы уже установили [пакет SDK для .NET Core](/dotnet/core/sdk), установите PowerShell как [глобальный инструмент .NET](/dotnet/core/tools/global-tools).</span><span class="sxs-lookup"><span data-stu-id="22e14-105">If you already have the [.NET Core SDK](/dotnet/core/sdk) installed, it’s easy to install PowerShell as a [.NET Global tool](/dotnet/core/tools/global-tools).</span></span>
>
> ```
> dotnet tool install --global PowerShell
> ```

## <a name="prerequisites"></a><span data-ttu-id="22e14-106">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="22e14-106">Prerequisites</span></span>

<span data-ttu-id="22e14-107">Чтобы включить удаленное взаимодействие PowerShell через WSMan, нужно выполнить следующие условия:</span><span class="sxs-lookup"><span data-stu-id="22e14-107">To enable PowerShell remoting over WSMan, the following prerequisites need to be met:</span></span>

- <span data-ttu-id="22e14-108">Установите [универсальную среду выполнения C](https://www.microsoft.com/download/details.aspx?id=50410) в версиях Windows, предшествующих Windows 10.</span><span class="sxs-lookup"><span data-stu-id="22e14-108">Install the [Universal C Runtime](https://www.microsoft.com/download/details.aspx?id=50410) on Windows versions prior to Windows 10.</span></span> <span data-ttu-id="22e14-109">Ее можно скачать самостоятельно или через Центр обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="22e14-109">It is available via direct download or Windows Update.</span></span> <span data-ttu-id="22e14-110">Поддерживаемые системы, где установлены все исправления (включая дополнительные пакеты), уже содержат ее.</span><span class="sxs-lookup"><span data-stu-id="22e14-110">Fully patched (including optional packages), supported systems will already have this installed.</span></span>
- <span data-ttu-id="22e14-111">Установите Windows Management Framework (WMF) 4.0 или более поздней версии в Windows 7 и Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="22e14-111">Install the Windows Management Framework (WMF) 4.0 or newer on Windows 7 and Windows Server 2008 R2.</span></span> <span data-ttu-id="22e14-112">Подробные сведения о WMF см. в статье с [обзором WMF](/powershell/wmf/overview).</span><span class="sxs-lookup"><span data-stu-id="22e14-112">For more information about WMF, see [WMF Overview](/powershell/wmf/overview).</span></span>

## <a name="a-idmsi-installing-the-msi-package"></a><span data-ttu-id="22e14-113"><a id="msi" />Установка пакета MSI</span><span class="sxs-lookup"><span data-stu-id="22e14-113"><a id="msi" />Installing the MSI package</span></span>

<span data-ttu-id="22e14-114">Чтобы установить PowerShell на клиенте Windows или в Windows Server (работает в Windows 7 с пакетом обновления 1 (SP1), Server 2008 R2 и более поздних версий), скачайте пакет MSI из с нашей страницы [выпусков][releases] GitHub.</span><span class="sxs-lookup"><span data-stu-id="22e14-114">To install PowerShell on a Windows client or Windows Server (works on Windows 7 SP1, Server 2008 R2, and later), download the MSI package from our GitHub [releases][releases] page.</span></span> <span data-ttu-id="22e14-115">Прокрутите вниз до раздела **Ресурсы** в выпуске, который вы хотите установить.</span><span class="sxs-lookup"><span data-stu-id="22e14-115">Scroll down to the **Assets** section of the Release you want to install.</span></span> <span data-ttu-id="22e14-116">Раздел "Ресурсы" может быть свернут. В таком случае щелкните его, чтобы развернуть.</span><span class="sxs-lookup"><span data-stu-id="22e14-116">The Assets section may be collapsed, so you may need to click to expand it.</span></span>

<span data-ttu-id="22e14-117">MSI-файл имеет следующий вид: `PowerShell-<version>-win-<os-arch>.msi`.</span><span class="sxs-lookup"><span data-stu-id="22e14-117">The MSI file looks like this - `PowerShell-<version>-win-<os-arch>.msi`</span></span>
<!-- TODO: should be updated to point to the Download Center as well -->

<span data-ttu-id="22e14-118">После скачивания дважды щелкните установщик и следуйте инструкциям на экране.</span><span class="sxs-lookup"><span data-stu-id="22e14-118">Once downloaded, double-click the installer and follow the prompts.</span></span>

<span data-ttu-id="22e14-119">Программа установки создает ярлык в меню Windows "Пуск".</span><span class="sxs-lookup"><span data-stu-id="22e14-119">The installer creates a shortcut in the Windows Start Menu.</span></span>

- <span data-ttu-id="22e14-120">По умолчанию пакет устанавливается в каталог `$env:ProgramFiles\PowerShell\<version>`.</span><span class="sxs-lookup"><span data-stu-id="22e14-120">By default the package is installed to `$env:ProgramFiles\PowerShell\<version>`</span></span>
- <span data-ttu-id="22e14-121">Вы можете запустить PowerShell с помощью меню "Пуск" или файла `$env:ProgramFiles\PowerShell\<version>\pwsh.exe`.</span><span class="sxs-lookup"><span data-stu-id="22e14-121">You can launch PowerShell via the Start Menu or `$env:ProgramFiles\PowerShell\<version>\pwsh.exe`</span></span>

### <a name="administrative-install-from-the-command-line"></a><span data-ttu-id="22e14-122">Установка администратором из командной строки</span><span class="sxs-lookup"><span data-stu-id="22e14-122">Administrative install from the command line</span></span>

<span data-ttu-id="22e14-123">Пакеты MSI можно установить из командной строки.</span><span class="sxs-lookup"><span data-stu-id="22e14-123">MSI packages can be installed from the command line.</span></span> <span data-ttu-id="22e14-124">Это позволяет администраторам развертывать пакеты без участия пользователя.</span><span class="sxs-lookup"><span data-stu-id="22e14-124">This allows administrators to deploy packages without user interaction.</span></span> <span data-ttu-id="22e14-125">Пакет MSI для PowerShell включает в себя следующие свойства для управления параметрами установки:</span><span class="sxs-lookup"><span data-stu-id="22e14-125">The MSI package for PowerShell includes the following properties to control the installation options:</span></span>

- <span data-ttu-id="22e14-126">**ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL**. Это свойство позволяет добавлять пункт **Открыть PowerShell** в контекстное меню проводника.</span><span class="sxs-lookup"><span data-stu-id="22e14-126">**ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL** - This property controls the option for adding the **Open PowerShell** item to the context menu in Windows Explorer.</span></span>
- <span data-ttu-id="22e14-127">**ENABLE_PSREMOTING**. Это свойство позволяет включать удаленное взаимодействие PowerShell во время установки.</span><span class="sxs-lookup"><span data-stu-id="22e14-127">**ENABLE_PSREMOTING** - This property controls the option for enabling PowerShell remoting during installation.</span></span>
- <span data-ttu-id="22e14-128">**REGISTER_MANIFEST**. Это свойство позволяет регистрировать манифест ведения журнала событий Windows.</span><span class="sxs-lookup"><span data-stu-id="22e14-128">**REGISTER_MANIFEST** - This property controls the option for registering the Windows Event Logging manifest.</span></span>

<span data-ttu-id="22e14-129">В следующих примерах показано, как выполнить автоматическую установку PowerShell Core со всеми включенными параметрами установки.</span><span class="sxs-lookup"><span data-stu-id="22e14-129">The following examples shows how to silently install PowerShell Core with all the install options enabled.</span></span>

```powershell
msiexec.exe /package PowerShell-<version>-win-<os-arch>.msi /quiet ADD_EXPLORER_CONTEXT_MENU_OPENPOWERSHELL=1 ENABLE_PSREMOTING=1 REGISTER_MANIFEST=1
```

<span data-ttu-id="22e14-130">См. [полный список параметров командной строки для Msiexec.exe](/windows/desktop/Msi/command-line-options).</span><span class="sxs-lookup"><span data-stu-id="22e14-130">For a full list of command line options for Msiexec.exe, see [Command line options](/windows/desktop/Msi/command-line-options).</span></span>

## <a name="a-idzip-installing-the-zip-package"></a><span data-ttu-id="22e14-131"><a id="zip" />Установка ZIP-пакета</span><span class="sxs-lookup"><span data-stu-id="22e14-131"><a id="zip" />Installing the ZIP package</span></span>

<span data-ttu-id="22e14-132">Для поддержки расширенных сценариев развертывания доступны ZIP-архивы двоичных файлов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="22e14-132">PowerShell binary ZIP archives are provided to enable advanced deployment scenarios.</span></span> <span data-ttu-id="22e14-133">Следует отметить, что при использовании ZIP-архива проверка предварительных условий, как в случае с пакетом MSI, не производится.</span><span class="sxs-lookup"><span data-stu-id="22e14-133">Be noted that when using the ZIP archive, you won't get the prerequisites check as in the MSI package.</span></span> <span data-ttu-id="22e14-134">Для правильной настройки удаленного взаимодействия с помощью WSMan необходимо выполнить [предварительные требования](#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="22e14-134">For remoting over WSMan to work properly, ensure that you have met the [prerequisites](#prerequisites).</span></span>

## <a name="deploying-on-windows-iot"></a><span data-ttu-id="22e14-135">Развертывание в Windows IoT</span><span class="sxs-lookup"><span data-stu-id="22e14-135">Deploying on Windows IoT</span></span>

<span data-ttu-id="22e14-136">Windows IoT поставляется с Windows PowerShell, который будет использоваться для развертывания PowerShell Core 6.</span><span class="sxs-lookup"><span data-stu-id="22e14-136">Windows IoT already comes with Windows PowerShell which we will use to deploy PowerShell Core 6.</span></span>

1. <span data-ttu-id="22e14-137">Создайте `PSSession` для целевого устройства</span><span class="sxs-lookup"><span data-stu-id="22e14-137">Create `PSSession` to target device</span></span>

   ```powershell
   $s = New-PSSession -ComputerName <deviceIp> -Credential Administrator
   ```

2. <span data-ttu-id="22e14-138">Скопируйте ZIP-файл на устройство</span><span class="sxs-lookup"><span data-stu-id="22e14-138">Copy the ZIP package to the device</span></span>

   ```powershell
   # change the destination to however you had partitioned it with sufficient
   # space for the zip and the unzipped contents
   # the path should be local to the device
   Copy-Item .\PowerShell-<version>-win-<os-arch>.zip -Destination u:\users\administrator\Downloads -ToSession $s
   ```

3. <span data-ttu-id="22e14-139">Присоединитесь к устройству и извлеките архив</span><span class="sxs-lookup"><span data-stu-id="22e14-139">Connect to the device and expand the archive</span></span>

   ```powershell
   Enter-PSSession $s
   Set-Location u:\users\administrator\downloads
   Expand-Archive .\PowerShell-<version>-win-<os-arch>.zip
   ```

4. <span data-ttu-id="22e14-140">Удаленное взаимодействие в PowerShell Core 6</span><span class="sxs-lookup"><span data-stu-id="22e14-140">Setup remoting to PowerShell Core 6</span></span>

   ```powershell
   Set-Location .\PowerShell-<version>-win-<os-arch>
   # Be sure to use the -PowerShellHome parameter otherwise it'll try to create a new
   # endpoint with Windows PowerShell 5.1
   .\Install-PowerShellRemoting.ps1 -PowerShellHome .
   # You'll get an error message and will be disconnected from the device because it has to restart WinRM
   ```

5. <span data-ttu-id="22e14-141">Подключение к конечной точке PowerShell Core 6 на устройстве</span><span class="sxs-lookup"><span data-stu-id="22e14-141">Connect to PowerShell Core 6 endpoint on device</span></span>

   ```powershell
   # Be sure to use the -Configuration parameter.  If you omit it, you will connect to Windows PowerShell 5.1
   Enter-PSSession -ComputerName <deviceIp> -Credential Administrator -Configuration powershell.<version>
   ```

## <a name="deploying-on-nano-server"></a><span data-ttu-id="22e14-142">Развертывание на Nano Server</span><span class="sxs-lookup"><span data-stu-id="22e14-142">Deploying on Nano Server</span></span>

<span data-ttu-id="22e14-143">Эти инструкции предполагают, что версия PowerShell уже запущена на образе Nano Server и была создана с помощью [Nano Server Image Builder](/windows-server/get-started/deploy-nano-server).</span><span class="sxs-lookup"><span data-stu-id="22e14-143">These instructions assume that a version of PowerShell is already running on the Nano Server image and that it has been generated by the [Nano Server Image Builder](/windows-server/get-started/deploy-nano-server).</span></span>
<span data-ttu-id="22e14-144">Nano Server является "виртуальной" ОС.</span><span class="sxs-lookup"><span data-stu-id="22e14-144">Nano Server is a "headless" OS.</span></span> <span data-ttu-id="22e14-145">Двоичные файлы ядра можно развернуть двумя разными методами.</span><span class="sxs-lookup"><span data-stu-id="22e14-145">Core binaries can be deploy using two different methods.</span></span>

1. <span data-ttu-id="22e14-146">Автономно — подключите виртуальный жесткий диск Nano Server и распакуйте содержимое ZIP-файла в выбранное расположение в этом образе.</span><span class="sxs-lookup"><span data-stu-id="22e14-146">Offline - Mount the Nano Server VHD and unzip the contents of the zip file to your chosen location within the mounted image.</span></span>
2. <span data-ttu-id="22e14-147">В сети — передайте ZIP-файл через сеанс PowerShell и распакуйте его в выбранное расположение.</span><span class="sxs-lookup"><span data-stu-id="22e14-147">Online - Transfer the zip file over a PowerShell Session and unzip it in your chosen location.</span></span>

<span data-ttu-id="22e14-148">В обоих случаях вам понадобится ZIP-пакет выпуска x64 Windows 10 и потребуется выполнять команды в экземпляре PowerShell с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="22e14-148">In both cases, you will need the Windows 10 x64 ZIP release package and will need to run the commands within an "Administrator" PowerShell instance.</span></span>

### <a name="offline-deployment-of-powershell-core"></a><span data-ttu-id="22e14-149">Автономное развертывание PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="22e14-149">Offline Deployment of PowerShell Core</span></span>

1. <span data-ttu-id="22e14-150">С помощью любой служебной программы ZIP распакуйте пакет в каталог, находящийся внутри подключенного образа Nano Server.</span><span class="sxs-lookup"><span data-stu-id="22e14-150">Use your favorite zip utility to unzip the package to a directory within the mounted Nano Server image.</span></span>
2. <span data-ttu-id="22e14-151">Отключите образ и загрузите его.</span><span class="sxs-lookup"><span data-stu-id="22e14-151">Unmount the image and boot it.</span></span>
3. <span data-ttu-id="22e14-152">Подключитесь к входящему экземпляру Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="22e14-152">Connect to the inbox instance of Windows PowerShell.</span></span>
4. <span data-ttu-id="22e14-153">Следуйте инструкциям, чтобы создать конечную точку удаленного взаимодействия с помощью [методики использования другого экземпляра](../learn/remoting/wsman-remoting-in-powershell-core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).</span><span class="sxs-lookup"><span data-stu-id="22e14-153">Follow the instructions to create a remoting endpoint using the ["another instance technique"](../learn/remoting/wsman-remoting-in-powershell-core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).</span></span>

### <a name="online-deployment-of-powershell-core"></a><span data-ttu-id="22e14-154">Автономное PowerShell Core в сети</span><span class="sxs-lookup"><span data-stu-id="22e14-154">Online Deployment of PowerShell Core</span></span>

<span data-ttu-id="22e14-155">В следующих шагах описываются инструкции развертывания PowerShell Core в запущенном экземпляре Nano Server, а также настройка его удаленной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="22e14-155">The following steps guide you through the deployment of PowerShell Core to a running instance of Nano Server and the configuration of its remote endpoint.</span></span>

- <span data-ttu-id="22e14-156">Подключитесь к входящему экземпляру Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="22e14-156">Connect to the inbox instance of Windows PowerShell</span></span>

  ```powershell
  $session = New-PSSession -ComputerName <Nano Server IP address> -Credential <An Administrator account on the system>
  ```

- <span data-ttu-id="22e14-157">Скопируйте файл на экземпляр Nano Server:</span><span class="sxs-lookup"><span data-stu-id="22e14-157">Copy the file to the Nano Server instance</span></span>

  ```powershell
  Copy-Item <local PS Core download location>\powershell-<version>-win-x64.zip c:\ -ToSession $session
  ```

- <span data-ttu-id="22e14-158">Войдите в сеанс:</span><span class="sxs-lookup"><span data-stu-id="22e14-158">Enter the session</span></span>

  ```powershell
  Enter-PSSession $session
  ```

- <span data-ttu-id="22e14-159">Извлеките ZIP-файл</span><span class="sxs-lookup"><span data-stu-id="22e14-159">Extract the ZIP file</span></span>

  ```powershell
  # Insert the appropriate version.
  Expand-Archive -Path C:\powershell-<version>-win-x64.zip -DestinationPath "C:\PowerShellCore_<version>"
  ```

- <span data-ttu-id="22e14-160">Если вам требуется удаленное взаимодействие на основе WSMan, следуйте инструкциям, чтобы создать конечную точку удаленного взаимодействия с помощью [методики использования другого экземпляра](../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).</span><span class="sxs-lookup"><span data-stu-id="22e14-160">If you want WSMan-based remoting, follow the instructions to create a remoting endpoint using the ["another instance technique"](../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).</span></span>

## <a name="how-to-create-a-remoting-endpoint"></a><span data-ttu-id="22e14-161">Создание конечной точки удаленного взаимодействия</span><span class="sxs-lookup"><span data-stu-id="22e14-161">How to create a remoting endpoint</span></span>

<span data-ttu-id="22e14-162">PowerShell Core поддерживает протокол удаленного взаимодействия PowerShell (PSRP) через SSH и WSMan.</span><span class="sxs-lookup"><span data-stu-id="22e14-162">PowerShell Core supports the PowerShell Remoting Protocol (PSRP) over both WSMan and SSH.</span></span> <span data-ttu-id="22e14-163">Дополнительная информация:</span><span class="sxs-lookup"><span data-stu-id="22e14-163">For more information, see:</span></span>

- <span data-ttu-id="22e14-164">[Удаленное взаимодействие через SSH в PowerShell Core][ssh-remoting]</span><span class="sxs-lookup"><span data-stu-id="22e14-164">[SSH Remoting in PowerShell Core][ssh-remoting]</span></span>
- <span data-ttu-id="22e14-165">[Удаленное взаимодействие через WSMan в PowerShell Core][wsman-remoting]</span><span class="sxs-lookup"><span data-stu-id="22e14-165">[WSMan Remoting in PowerShell Core][wsman-remoting]</span></span>

<!-- [download-center]: TODO -->

[releases]: https://github.com/PowerShell/PowerShell/releases
[ssh-remoting]: ../learn/remoting/SSH-Remoting-in-PowerShell-Core.md
[wsman-remoting]: ../learn/remoting/WSMan-Remoting-in-PowerShell-Core.md
[AppVeyor]: https://ci.appveyor.com/project/PowerShell/powershell
