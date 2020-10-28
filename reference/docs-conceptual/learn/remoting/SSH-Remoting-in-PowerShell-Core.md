---
title: Удаленное взаимодействие с PowerShell через SSH
ms.date: 10/19/2020
description: Описывается, как настроить протокол SSH для удаленного взаимодействия PowerShell.
ms.openlocfilehash: c3373ac30fd915d42e8c9fb7f1eae348a2aee7f1
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "92501343"
---
# <a name="powershell-remoting-over-ssh"></a><span data-ttu-id="d1c47-103">Удаленное взаимодействие с PowerShell через SSH</span><span class="sxs-lookup"><span data-stu-id="d1c47-103">PowerShell remoting over SSH</span></span>

## <a name="overview"></a><span data-ttu-id="d1c47-104">Обзор</span><span class="sxs-lookup"><span data-stu-id="d1c47-104">Overview</span></span>

<span data-ttu-id="d1c47-105">Функция удаленного взаимодействия PowerShell обычно использует WinRM для согласования соединения и передачи данных.</span><span class="sxs-lookup"><span data-stu-id="d1c47-105">PowerShell remoting normally uses WinRM for connection negotiation and data transport.</span></span> <span data-ttu-id="d1c47-106">Теперь протокол SSH доступен на платформах Linux и Windows, что позволяет осуществлять многоплатформенное удаленное взаимодействие с PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1c47-106">SSH is now available for Linux and Windows platforms and allows true multiplatform PowerShell remoting.</span></span>

<span data-ttu-id="d1c47-107">Служба удаленного управления Windows обеспечивает надежную модель поддержки удаленных сеансов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1c47-107">WinRM provides a robust hosting model for PowerShell remote sessions.</span></span> <span data-ttu-id="d1c47-108">Удаленное взаимодействие по протоколу SSH сейчас не поддерживает настройку удаленных конечных точек и функцию JEA (Just Enough Administration).</span><span class="sxs-lookup"><span data-stu-id="d1c47-108">SSH-based remoting doesn't currently support remote endpoint configuration and Just Enough Administration (JEA).</span></span>

<span data-ttu-id="d1c47-109">Удаленное взаимодействие по SSH позволяет осуществлять базовое удаленное взаимодействие между компьютерами с Windows и Linux в рамках сеансов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1c47-109">SSH remoting lets you do basic PowerShell session remoting between Windows and Linux computers.</span></span> <span data-ttu-id="d1c47-110">Функция удаленного взаимодействия по SSH создает хост-процесс PowerShell на целевом компьютере в качестве подсистемы SSH.</span><span class="sxs-lookup"><span data-stu-id="d1c47-110">SSH remoting creates a PowerShell host process on the target computer as an SSH subsystem.</span></span> <span data-ttu-id="d1c47-111">Со временем для поддержки настройки удаленных конечных точек и функции JEA мы реализуем общую модель размещения, похожую на службе удаленного управления Windows.</span><span class="sxs-lookup"><span data-stu-id="d1c47-111">Eventually we'll implement a general hosting model, similar to WinRM, to support endpoint configuration and JEA.</span></span>

<span data-ttu-id="d1c47-112">Командлеты `New-PSSession`, `Enter-PSSession` и `Invoke-Command` теперь имеют набор новых параметров для поддержки этой возможности удаленного взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="d1c47-112">The `New-PSSession`, `Enter-PSSession`, and `Invoke-Command` cmdlets now have a new parameter set to support this new remoting connection.</span></span>

```
[-HostName <string>]  [-UserName <string>]  [-KeyFilePath <string>]
```

<span data-ttu-id="d1c47-113">Чтобы создать удаленный сеанс, укажите целевой компьютер с помощью параметра **HostName** и имя пользователя с помощью параметра **UserName** .</span><span class="sxs-lookup"><span data-stu-id="d1c47-113">To create a remote session, you specify the target computer with the **HostName** parameter and provide the user name with **UserName** .</span></span> <span data-ttu-id="d1c47-114">При интерактивном выполнении командлетов отображается запрос на ввод пароля.</span><span class="sxs-lookup"><span data-stu-id="d1c47-114">When running the cmdlets interactively, you're prompted for a password.</span></span> <span data-ttu-id="d1c47-115">Вы также можете использовать проверку подлинности ключа SSH с помощью файла закрытого ключа с параметром **KeyFilePath** .</span><span class="sxs-lookup"><span data-stu-id="d1c47-115">You can also use SSH key authentication using a private key file with the **KeyFilePath** parameter.</span></span> <span data-ttu-id="d1c47-116">Способ создания ключей для проверки подлинности по протоколу SSH зависит от платформы.</span><span class="sxs-lookup"><span data-stu-id="d1c47-116">Creating keys for SSH authentication varies by platform.</span></span>

## <a name="general-setup-information"></a><span data-ttu-id="d1c47-117">Общие сведения об установке</span><span class="sxs-lookup"><span data-stu-id="d1c47-117">General setup information</span></span>

<span data-ttu-id="d1c47-118">PowerShell 6 или более поздней версии, и на всех компьютерах должен быть установлен SSH.</span><span class="sxs-lookup"><span data-stu-id="d1c47-118">PowerShell 6 or higher, and SSH must be installed on all computers.</span></span> <span data-ttu-id="d1c47-119">Установите клиент (`ssh.exe`) и сервер (`sshd.exe`) SSH, чтобы осуществлять удаленное взаимодействие между компьютерами.</span><span class="sxs-lookup"><span data-stu-id="d1c47-119">Install both the SSH client (`ssh.exe`) and server (`sshd.exe`) so that you can remote to and from the computers.</span></span> <span data-ttu-id="d1c47-120">Решение OpenSSH для Windows теперь доступно в Windows 10 сборки 1809 и Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d1c47-120">OpenSSH for Windows is now available in Windows 10 build 1809 and Windows Server 2019.</span></span> <span data-ttu-id="d1c47-121">Дополнительные сведения см. в статье [Управление Windows через OpenSSH](/windows-server/administration/openssh/openssh_overview).</span><span class="sxs-lookup"><span data-stu-id="d1c47-121">For more information, see [Manage Windows with OpenSSH](/windows-server/administration/openssh/openssh_overview).</span></span> <span data-ttu-id="d1c47-122">В Linux нужно реализовать поддержку SSH (включая установку сервера sshd) в соответствии с используемой платформой.</span><span class="sxs-lookup"><span data-stu-id="d1c47-122">For Linux, install SSH, including sshd server, that's appropriate for your platform.</span></span> <span data-ttu-id="d1c47-123">Также для поддержки удаленного взаимодействия по SSH нужно установить PowerShell с сайта GitHub.</span><span class="sxs-lookup"><span data-stu-id="d1c47-123">You also need to install PowerShell from GitHub to get the SSH remoting feature.</span></span> <span data-ttu-id="d1c47-124">Для сервера SSH нужно настроить возможность создать подсистему SSH для размещения процесса PowerShell на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="d1c47-124">The SSH server must be configured to create an SSH subsystem to host a PowerShell process on the remote computer.</span></span> <span data-ttu-id="d1c47-125">Также нужно активировать проверку подлинности на основе **пароля** или **ключа** .</span><span class="sxs-lookup"><span data-stu-id="d1c47-125">And, you must enable **password** or **key-based** authentication.</span></span>

## <a name="set-up-on-a-windows-computer"></a><span data-ttu-id="d1c47-126">Настройка на компьютере с Windows</span><span class="sxs-lookup"><span data-stu-id="d1c47-126">Set up on a Windows computer</span></span>

1. <span data-ttu-id="d1c47-127">Установите последнюю версию PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1c47-127">Install the latest version of PowerShell.</span></span> <span data-ttu-id="d1c47-128">Дополнительные сведения см. в статье [Установка PowerShell Core в Windows](../../install/installing-powershell-core-on-windows.md#msi).</span><span class="sxs-lookup"><span data-stu-id="d1c47-128">For more information, see [Installing PowerShell Core on Windows](../../install/installing-powershell-core-on-windows.md#msi).</span></span>

   <span data-ttu-id="d1c47-129">Чтобы убедиться, что в PowerShell есть поддержка удаленного взаимодействия SSH, перечислите наборы параметров `New-PSSession`.</span><span class="sxs-lookup"><span data-stu-id="d1c47-129">You can confirm that PowerShell has SSH remoting support by listing the `New-PSSession` parameter sets.</span></span> <span data-ttu-id="d1c47-130">Обратите внимание на наличие имен наборов параметров, начинающихся с **SSH** .</span><span class="sxs-lookup"><span data-stu-id="d1c47-130">You'll notice there are parameter set names that begin with **SSH** .</span></span> <span data-ttu-id="d1c47-131">К этим наборам параметров относятся параметры **SSH** .</span><span class="sxs-lookup"><span data-stu-id="d1c47-131">Those parameter sets include **SSH** parameters.</span></span>

   ```powershell
   (Get-Command New-PSSession).ParameterSets.Name
   ```

   ```Output
   Name
   ----
   SSHHost
   SSHHostHashParam
   ```

1. <span data-ttu-id="d1c47-132">Установите последнюю версию Win32 OpenSSH.</span><span class="sxs-lookup"><span data-stu-id="d1c47-132">Install the latest Win32 OpenSSH.</span></span> <span data-ttu-id="d1c47-133">Инструкции по установке см. в разделе [Начало работы с OpenSSH](/windows-server/administration/openssh/openssh_install_firstuse).</span><span class="sxs-lookup"><span data-stu-id="d1c47-133">For installation instructions, see [Getting started with OpenSSH](/windows-server/administration/openssh/openssh_install_firstuse).</span></span>

   > [!NOTE]
   > <span data-ttu-id="d1c47-134">Если вы хотите задать PowerShell в качестве оболочки по умолчанию для OpenSSH, см. раздел [Настройка Windows для OpenSSH](/windows-server/administration/openssh/openssh_server_configuration).</span><span class="sxs-lookup"><span data-stu-id="d1c47-134">If you want to set PowerShell as the default shell for OpenSSH, see [Configuring Windows for OpenSSH](/windows-server/administration/openssh/openssh_server_configuration).</span></span>

1. <span data-ttu-id="d1c47-135">Измените файл `sshd_config`, расположенный в `$env:ProgramData\ssh`.</span><span class="sxs-lookup"><span data-stu-id="d1c47-135">Edit the `sshd_config` file located at `$env:ProgramData\ssh`.</span></span>

   <span data-ttu-id="d1c47-136">Включите проверку подлинности с помощью пароля:</span><span class="sxs-lookup"><span data-stu-id="d1c47-136">Make sure password authentication is enabled:</span></span>

   ```
   PasswordAuthentication yes
   ```

   <span data-ttu-id="d1c47-137">Создайте подсистему SSH, в которой размещается процесс PowerShell на удаленном компьютере:</span><span class="sxs-lookup"><span data-stu-id="d1c47-137">Create the SSH subsystem that hosts a PowerShell process on the remote computer:</span></span>

   ```
   Subsystem powershell c:/progra~1/powershell/7/pwsh.exe -sshs -NoLogo
   ```

   > [!NOTE]
   > <span data-ttu-id="d1c47-138">Расположение исполняемого файла PowerShell по умолчанию — `c:/progra~1/powershell/7/pwsh.exe`.</span><span class="sxs-lookup"><span data-stu-id="d1c47-138">The default location of the PowerShell executable is `c:/progra~1/powershell/7/pwsh.exe`.</span></span> <span data-ttu-id="d1c47-139">Расположение может различаться в зависимости от способа установки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1c47-139">The location can vary depending on how you installed PowerShell.</span></span>
   >
   > <span data-ttu-id="d1c47-140">Необходимо использовать краткое имя 8.3 для всех путей к файлам, содержащим пробелы.</span><span class="sxs-lookup"><span data-stu-id="d1c47-140">You must use the 8.3 short name for any file paths that contain spaces.</span></span> <span data-ttu-id="d1c47-141">В OpenSSH для Windows обнаружена ошибка, блокирующая работу пробелов в путях к исполняемым файлам подсистемы.</span><span class="sxs-lookup"><span data-stu-id="d1c47-141">There's a bug in OpenSSH for Windows that prevents spaces from working in subsystem executable paths.</span></span> <span data-ttu-id="d1c47-142">См. дополнительные сведения на [сайте GitHub](https://github.com/PowerShell/Win32-OpenSSH/issues/784).</span><span class="sxs-lookup"><span data-stu-id="d1c47-142">For more information, see this [GitHub issue](https://github.com/PowerShell/Win32-OpenSSH/issues/784).</span></span>
   >
   > <span data-ttu-id="d1c47-143">Обычно краткое имя 8.3 для папки `Program Files` в Windows — это `Progra~1`.</span><span class="sxs-lookup"><span data-stu-id="d1c47-143">The 8.3 short name for the `Program Files` folder in Windows is usually `Progra~1`.</span></span> <span data-ttu-id="d1c47-144">Тем не менее для проверки можно использовать следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d1c47-144">However, you can use the following command to make sure:</span></span>
   >
   > ```powershell
   > Get-CimInstance Win32_Directory -Filter 'Name="C:\\Program Files"' |
   >   Select-Object EightDotThreeFileName
   > ```
   >
   > ```Output
   > EightDotThreeFileName
   > ---------------------
   > c:\progra~1
   > ```

   <span data-ttu-id="d1c47-145">При необходимости включите проверку подлинности на основе ключа:</span><span class="sxs-lookup"><span data-stu-id="d1c47-145">Optionally, enable key authentication:</span></span>

   ```
   PubkeyAuthentication yes
   ```

   <span data-ttu-id="d1c47-146">Дополнительные сведения см. в статье [Управление ключами OpenSSH](/windows-server/administration/openssh/openssh_keymanagement).</span><span class="sxs-lookup"><span data-stu-id="d1c47-146">For more information, see [Managing OpenSSH Keys](/windows-server/administration/openssh/openssh_keymanagement).</span></span>

1. <span data-ttu-id="d1c47-147">Перезапустите службу **sshd** .</span><span class="sxs-lookup"><span data-stu-id="d1c47-147">Restart the **sshd** service.</span></span>

   ```powershell
   Restart-Service sshd
   ```

1. <span data-ttu-id="d1c47-148">Добавьте путь установки OpenSSH в свою переменную среды Path.</span><span class="sxs-lookup"><span data-stu-id="d1c47-148">Add the path where OpenSSH is installed to your Path environment variable.</span></span> <span data-ttu-id="d1c47-149">Например, `C:\Program Files\OpenSSH\`.</span><span class="sxs-lookup"><span data-stu-id="d1c47-149">For example, `C:\Program Files\OpenSSH\`.</span></span> <span data-ttu-id="d1c47-150">Это позволит найти файл `ssh.exe`.</span><span class="sxs-lookup"><span data-stu-id="d1c47-150">This entry allows for the `ssh.exe` to be found.</span></span>

## <a name="set-up-on-an-ubuntu-1604-linux-computer"></a><span data-ttu-id="d1c47-151">Настройка на компьютере с Ubuntu 16.04 Linux</span><span class="sxs-lookup"><span data-stu-id="d1c47-151">Set up on an Ubuntu 16.04 Linux computer</span></span>

1. <span data-ttu-id="d1c47-152">Установите последнюю версию PowerShell, см. раздел [Установка PowerShell Core в Linux](../../install/installing-powershell-core-on-linux.md#ubuntu-1604).</span><span class="sxs-lookup"><span data-stu-id="d1c47-152">Install the latest version of PowerShell, see [Installing PowerShell Core on Linux](../../install/installing-powershell-core-on-linux.md#ubuntu-1604).</span></span>
1. <span data-ttu-id="d1c47-153">Установите [сервер OpenSSH для Ubuntu](https://help.ubuntu.com/lts/serverguide/openssh-server.html).</span><span class="sxs-lookup"><span data-stu-id="d1c47-153">Install [Ubuntu OpenSSH Server](https://help.ubuntu.com/lts/serverguide/openssh-server.html).</span></span>

   ```bash
   sudo apt install openssh-client
   sudo apt install openssh-server
   ```

1. <span data-ttu-id="d1c47-154">Измените файл `sshd_config` в расположении `/etc/ssh`.</span><span class="sxs-lookup"><span data-stu-id="d1c47-154">Edit the `sshd_config` file at location `/etc/ssh`.</span></span>

   <span data-ttu-id="d1c47-155">Включите проверку подлинности с помощью пароля:</span><span class="sxs-lookup"><span data-stu-id="d1c47-155">Make sure password authentication is enabled:</span></span>

   ```
   PasswordAuthentication yes
   ```

   <span data-ttu-id="d1c47-156">При необходимости включите проверку подлинности на основе ключа:</span><span class="sxs-lookup"><span data-stu-id="d1c47-156">Optionally, enable key authentication:</span></span>

   ```
   PubkeyAuthentication yes
   ```

   <span data-ttu-id="d1c47-157">Дополнительные сведения о создании ключей SSH в Ubuntu см. на странице справки по [ssh-keygen](http://manpages.ubuntu.com/manpages/xenial/man1/ssh-keygen.1.html).</span><span class="sxs-lookup"><span data-stu-id="d1c47-157">For more information about creating SSH keys on Ubuntu, see the manpage for [ssh-keygen](http://manpages.ubuntu.com/manpages/xenial/man1/ssh-keygen.1.html).</span></span>

   <span data-ttu-id="d1c47-158">Добавьте запись подсистемы PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d1c47-158">Add a PowerShell subsystem entry:</span></span>

   ```
   Subsystem powershell /usr/bin/pwsh -sshs -NoLogo
   ```

   > [!NOTE]
   > <span data-ttu-id="d1c47-159">Расположение исполняемого файла PowerShell по умолчанию — `/usr/bin/pwsh`.</span><span class="sxs-lookup"><span data-stu-id="d1c47-159">The default location of the PowerShell executable is `/usr/bin/pwsh`.</span></span> <span data-ttu-id="d1c47-160">Расположение может различаться в зависимости от способа установки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1c47-160">The location can vary depending on how you installed PowerShell.</span></span>

   <span data-ttu-id="d1c47-161">При необходимости включите проверку подлинности на основе ключа:</span><span class="sxs-lookup"><span data-stu-id="d1c47-161">Optionally, enable key authentication:</span></span>

   ```
   PubkeyAuthentication yes
   ```

1. <span data-ttu-id="d1c47-162">Перезапустите службу **ssh** .</span><span class="sxs-lookup"><span data-stu-id="d1c47-162">Restart the **ssh** service.</span></span>

   ```bash
   sudo service ssh restart
   ```

## <a name="set-up-on-a-macos-computer"></a><span data-ttu-id="d1c47-163">Настройка на компьютере с macOS</span><span class="sxs-lookup"><span data-stu-id="d1c47-163">Set up on a macOS computer</span></span>

1. <span data-ttu-id="d1c47-164">Установите последнюю версию PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1c47-164">Install the latest version of PowerShell.</span></span> <span data-ttu-id="d1c47-165">Дополнительные сведения см. в статье [Установка PowerShell Core в macOS](../../install/installing-powershell-core-on-macos.md).</span><span class="sxs-lookup"><span data-stu-id="d1c47-165">For more information, [Installing PowerShell Core on macOS](../../install/installing-powershell-core-on-macos.md).</span></span>

   <span data-ttu-id="d1c47-166">Убедитесь, что удаленное взаимодействие SSH включено, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="d1c47-166">Make sure SSH Remoting is enabled by following these steps:</span></span>

   1. <span data-ttu-id="d1c47-167">Откройте среду `System Preferences`.</span><span class="sxs-lookup"><span data-stu-id="d1c47-167">Open `System Preferences`.</span></span>
   1. <span data-ttu-id="d1c47-168">Щелкните `Sharing`.</span><span class="sxs-lookup"><span data-stu-id="d1c47-168">Click on `Sharing`.</span></span>
   1. <span data-ttu-id="d1c47-169">Установите флажок `Remote Login`, чтобы задать `Remote Login: On`.</span><span class="sxs-lookup"><span data-stu-id="d1c47-169">Check `Remote Login` to set `Remote Login: On`.</span></span>
   1. <span data-ttu-id="d1c47-170">Разрешите доступ соответствующим пользователям.</span><span class="sxs-lookup"><span data-stu-id="d1c47-170">Allow access to the appropriate users.</span></span>

1. <span data-ttu-id="d1c47-171">Измените файл `sshd_config` в расположении `/private/etc/ssh/sshd_config`.</span><span class="sxs-lookup"><span data-stu-id="d1c47-171">Edit the `sshd_config` file at location `/private/etc/ssh/sshd_config`.</span></span>

   <span data-ttu-id="d1c47-172">Используйте текстовый редактор, например **nano** :</span><span class="sxs-lookup"><span data-stu-id="d1c47-172">Use a text editor such as **nano** :</span></span>

   ```bash
   sudo nano /private/etc/ssh/sshd_config
   ```

   <span data-ttu-id="d1c47-173">Включите проверку подлинности с помощью пароля:</span><span class="sxs-lookup"><span data-stu-id="d1c47-173">Make sure password authentication is enabled:</span></span>

   ```
   PasswordAuthentication yes
   ```

   <span data-ttu-id="d1c47-174">Добавьте запись подсистемы PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d1c47-174">Add a PowerShell subsystem entry:</span></span>

   ```
   Subsystem powershell /usr/local/bin/pwsh -sshs -NoLogo
   ```

   > [!NOTE]
   > <span data-ttu-id="d1c47-175">Расположение исполняемого файла PowerShell по умолчанию — `/usr/local/bin/pwsh`.</span><span class="sxs-lookup"><span data-stu-id="d1c47-175">The default location of the PowerShell executable is `/usr/local/bin/pwsh`.</span></span> <span data-ttu-id="d1c47-176">Расположение может различаться в зависимости от способа установки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1c47-176">The location can vary depending on how you installed PowerShell.</span></span>

   <span data-ttu-id="d1c47-177">При необходимости включите проверку подлинности на основе ключа:</span><span class="sxs-lookup"><span data-stu-id="d1c47-177">Optionally, enable key authentication:</span></span>

   ```
   PubkeyAuthentication yes
   ```

1. <span data-ttu-id="d1c47-178">Перезапустите службу **sshd** .</span><span class="sxs-lookup"><span data-stu-id="d1c47-178">Restart the **sshd** service.</span></span>

   ```bash
   sudo launchctl stop com.openssh.sshd
   sudo launchctl start com.openssh.sshd
   ```

## <a name="authentication"></a><span data-ttu-id="d1c47-179">Аутентификация</span><span class="sxs-lookup"><span data-stu-id="d1c47-179">Authentication</span></span>

<span data-ttu-id="d1c47-180">При удаленном взаимодействии с PowerShell через SSH используется обмен данными для проверки подлинности между клиентом SSH и службой SSH. Схемы проверки подлинности в его рамках не реализуются.</span><span class="sxs-lookup"><span data-stu-id="d1c47-180">PowerShell remoting over SSH relies on the authentication exchange between the SSH client and SSH service and doesn't implement any authentication schemes itself.</span></span> <span data-ttu-id="d1c47-181">Это означает, что любые настроенные схемы проверки подлинности, включая многофакторную проверку подлинности, обрабатываются протоколом SSH независимо от PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1c47-181">The result is that any configured authentication schemes including multi-factor authentication are handled by SSH and independent of PowerShell.</span></span> <span data-ttu-id="d1c47-182">Например, в службе SSH можно настроить обязательное применение проверки подлинности на основе открытых ключей, а также разовых паролей для усиления безопасности.</span><span class="sxs-lookup"><span data-stu-id="d1c47-182">For example, you can configure the SSH service to require public key authentication and a one-time password for added security.</span></span> <span data-ttu-id="d1c47-183">Настройка многофакторной проверки подлинности выходит за рамки настоящего документа.</span><span class="sxs-lookup"><span data-stu-id="d1c47-183">Configuration of multi-factor authentication is outside the scope of this documentation.</span></span> <span data-ttu-id="d1c47-184">Сведения о том, как правильно настроить многофакторную проверку подлинности и проверить ее работу вне PowerShell, прежде чем пытаться использовать ее для удаленного взаимодействия с PowerShell, см. в документации по SSH.</span><span class="sxs-lookup"><span data-stu-id="d1c47-184">Refer to documentation for SSH on how to correctly configure multi-factor authentication and validate it works outside of PowerShell before attempting to use it with PowerShell remoting.</span></span>

> [!NOTE]
> <span data-ttu-id="d1c47-185">Пользователи сохраняют те же привилегии в удаленных сеансах.</span><span class="sxs-lookup"><span data-stu-id="d1c47-185">Users retain the same privileges in remote sessions.</span></span> <span data-ttu-id="d1c47-186">Это означает, что администраторы имеют доступ к оболочке с повышенными правами, а обычные пользователи — нет.</span><span class="sxs-lookup"><span data-stu-id="d1c47-186">Meaning, Administrators have access to an elevated shell, and normal users will not.</span></span>

## <a name="powershell-remoting-example"></a><span data-ttu-id="d1c47-187">Пример удаленного взаимодействия PowerShell</span><span class="sxs-lookup"><span data-stu-id="d1c47-187">PowerShell remoting example</span></span>

<span data-ttu-id="d1c47-188">Проще всего проверить удаленное взаимодействие на одном компьютере.</span><span class="sxs-lookup"><span data-stu-id="d1c47-188">The easiest way to test remoting is to try it on a single computer.</span></span> <span data-ttu-id="d1c47-189">В этом примере мы создадим удаленный сеанс с одним и тем же компьютером Linux.</span><span class="sxs-lookup"><span data-stu-id="d1c47-189">In this example, we create a remote session back to the same Linux computer.</span></span> <span data-ttu-id="d1c47-190">Командлеты PowerShell мы выполняем в интерактивном режиме, поэтому мы увидим запрос от SSH на проверку удаленного компьютера, а также запрос на ввод пароля.</span><span class="sxs-lookup"><span data-stu-id="d1c47-190">We're using PowerShell cmdlets interactively so we see prompts from SSH asking to verify the host computer and prompting for a password.</span></span> <span data-ttu-id="d1c47-191">Чтобы убедиться, что удаленное взаимодействие работает, те же операции можно выполнить на компьютере Windows.</span><span class="sxs-lookup"><span data-stu-id="d1c47-191">You can do the same thing on a Windows computer to ensure remoting is working.</span></span> <span data-ttu-id="d1c47-192">Затем установите удаленное подключение между компьютерами, изменив имя узла.</span><span class="sxs-lookup"><span data-stu-id="d1c47-192">Then, remote between computers by changing the host name.</span></span>

```powershell
# Linux to Linux
#
$session = New-PSSession -HostName UbuntuVM1 -UserName TestUser
```

```Output
The authenticity of host 'UbuntuVM1 (9.129.17.107)' cannot be established.
ECDSA key fingerprint is SHA256:2kCbnhT2dUE6WCGgVJ8Hyfu1z2wE4lifaJXLO7QJy0Y.
Are you sure you want to continue connecting (yes/no)?
TestUser@UbuntuVM1s password:
```

```powershell
$session
```

```Output
 Id Name   ComputerName    ComputerType    State    ConfigurationName     Availability
 -- ----   ------------    ------------    -----    -----------------     ------------
  1 SSH1   UbuntuVM1       RemoteMachine   Opened   DefaultShell             Available
```

```powershell
Enter-PSSession $session
```

```Output
[UbuntuVM1]: PS /home/TestUser> uname -a
Linux TestUser-UbuntuVM1 4.2.0-42-generic 49~16.04.1-Ubuntu SMP Wed Jun 29 20:22:11 UTC 2016 x86_64 x86_64 x86_64 GNU/Linux

[UbuntuVM1]: PS /home/TestUser> Exit-PSSession
```

```powershell
Invoke-Command $session -ScriptBlock { Get-Process powershell }
```

```Output
Handles  NPM(K)    PM(K)      WS(K)     CPU(s)     Id  SI ProcessName                    PSComputerName
-------  ------    -----      -----     ------     --  -- -----------                    --------------
      0       0        0         19       3.23  10635 635 powershell                     UbuntuVM1
      0       0        0         21       4.92  11033 017 powershell                     UbuntuVM1
      0       0        0         20       3.07  11076 076 powershell                     UbuntuVM1
```

```powershell
#
# Linux to Windows
#
Enter-PSSession -HostName WinVM1 -UserName PTestName
```

```
PTestName@WinVM1s password:
```

```powershell
[WinVM1]: PS C:\Users\PTestName\Documents> cmd /c ver
```

```Output
Microsoft Windows [Version 10.0.10586]
```

```powershell
#
# Windows to Windows
#
C:\Users\PSUser\Documents>pwsh.exe
```

```Output
PowerShell
Copyright (c) Microsoft Corporation. All rights reserved.
```

```powershell
$session = New-PSSession -HostName WinVM2 -UserName PSRemoteUser
```

```Output
The authenticity of host 'WinVM2 (10.13.37.3)' can't be established.
ECDSA key fingerprint is SHA256:kSU6slAROyQVMEynVIXAdxSiZpwDBigpAF/TXjjWjmw.
Are you sure you want to continue connecting (yes/no)?
Warning: Permanently added 'WinVM2,10.13.37.3' (ECDSA) to the list of known hosts.
PSRemoteUser@WinVM2's password:
```

```powershell
$session
```

```Output
 Id Name            ComputerName    ComputerType    State         ConfigurationName     Availability
 -- ----            ------------    ------------    -----         -----------------     ------------
  1 SSH1            WinVM2          RemoteMachine   Opened        DefaultShell             Available
```

```powershell
Enter-PSSession -Session $session
```

```Output
[WinVM2]: PS C:\Users\PSRemoteUser\Documents> $PSVersionTable

Name                           Value
----                           -----
PSEdition                      Core
PSCompatibleVersions           {1.0, 2.0, 3.0, 4.0...}
SerializationVersion           1.1.0.1
BuildVersion                   3.0.0.0
CLRVersion
PSVersion                      6.0.0-alpha
WSManStackVersion              3.0
PSRemotingProtocolVersion      2.3
GitCommitId                    v6.0.0-alpha.17


[WinVM2]: PS C:\Users\PSRemoteUser\Documents>
```

### <a name="limitations"></a><span data-ttu-id="d1c47-193">Ограничения</span><span class="sxs-lookup"><span data-stu-id="d1c47-193">Limitations</span></span>

- <span data-ttu-id="d1c47-194">Команда **sudo** не работает в рамках сеанса удаленного взаимодействия с компьютером Linux.</span><span class="sxs-lookup"><span data-stu-id="d1c47-194">The **sudo** command doesn't work in a remote session to a Linux computer.</span></span>

- <span data-ttu-id="d1c47-195">PSRemoting через SSH не поддерживает профили и не имеет доступа к `$PROFILE`.</span><span class="sxs-lookup"><span data-stu-id="d1c47-195">PSRemoting over SSH does not support Profiles and does not have access to `$PROFILE`.</span></span> <span data-ttu-id="d1c47-196">После входа в сеанс можно загрузить профиль с помощью вызова с точкой, указав полный путь к профилю.</span><span class="sxs-lookup"><span data-stu-id="d1c47-196">Once in a session, you can load a profile by dot sourcing the profile with the full filepath.</span></span> <span data-ttu-id="d1c47-197">Это не связано с профилями SSH.</span><span class="sxs-lookup"><span data-stu-id="d1c47-197">This is not related to SSH profiles.</span></span> <span data-ttu-id="d1c47-198">Вы можете настроить SSH-сервер для использования PowerShell в качестве оболочки по умолчанию и для загрузки профиля через SSH.</span><span class="sxs-lookup"><span data-stu-id="d1c47-198">You can configure the SSH server to use PowerShell as the default shell and to load a profile through SSH.</span></span> <span data-ttu-id="d1c47-199">Дополнительные сведения см. в документации по SSH.</span><span class="sxs-lookup"><span data-stu-id="d1c47-199">See the SSH documentation for more information.</span></span>

- <span data-ttu-id="d1c47-200">До PowerShell 7.1 удаленное взаимодействие по SSH не поддерживало удаленные сеансы со вторым прыжком.</span><span class="sxs-lookup"><span data-stu-id="d1c47-200">Prior to PowerShell 7.1, remoting over SSH did not support second-hop remote sessions.</span></span> <span data-ttu-id="d1c47-201">Эта возможность была ограничена сеансами через WinRM.</span><span class="sxs-lookup"><span data-stu-id="d1c47-201">This capability was limited to sessions using WinRM.</span></span> <span data-ttu-id="d1c47-202">PowerShell 7.1 позволяет `Enter-PSSession` и `Enter-PSHostProcess` работать в любом интерактивном удаленном сеансе.</span><span class="sxs-lookup"><span data-stu-id="d1c47-202">PowerShell 7.1 allows `Enter-PSSession` and `Enter-PSHostProcess` to work from within any interactive remote session.</span></span>

## <a name="see-also"></a><span data-ttu-id="d1c47-203">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d1c47-203">See also</span></span>

[<span data-ttu-id="d1c47-204">Установка PowerShell Core в Linux</span><span class="sxs-lookup"><span data-stu-id="d1c47-204">Installing PowerShell Core on Linux</span></span>](../../install/installing-powershell-core-on-linux.md#ubuntu-1604)

[<span data-ttu-id="d1c47-205">Установка PowerShell Core в macOS</span><span class="sxs-lookup"><span data-stu-id="d1c47-205">Installing PowerShell Core on macOS</span></span>](../../install/installing-powershell-core-on-macos.md)

[<span data-ttu-id="d1c47-206">Установка PowerShell Core в Windows</span><span class="sxs-lookup"><span data-stu-id="d1c47-206">Installing PowerShell Core on Windows</span></span>](../../install/installing-powershell-core-on-windows.md#msi)

[<span data-ttu-id="d1c47-207">Управление Windows с помощью OpenSSH</span><span class="sxs-lookup"><span data-stu-id="d1c47-207">Manage Windows with OpenSSH</span></span>](/windows-server/administration/openssh/openssh_overview)

[<span data-ttu-id="d1c47-208">Управление ключами OpenSSH</span><span class="sxs-lookup"><span data-stu-id="d1c47-208">Managing OpenSSH Keys</span></span>](/windows-server/administration/openssh/openssh_keymanagement)

[<span data-ttu-id="d1c47-209">Ubuntu SSH</span><span class="sxs-lookup"><span data-stu-id="d1c47-209">Ubuntu SSH</span></span>](https://help.ubuntu.com/lts/serverguide/openssh-server.html)
