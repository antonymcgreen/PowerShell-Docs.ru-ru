---
title: Удаленное взаимодействие с PowerShell через SSH
description: Удаленное взаимодействие в PowerShell Core с помощью SSH
ms.date: 08/14/2018
ms.openlocfilehash: 1de034d667aa9a377e5460e7eb474402c690cb42
ms.sourcegitcommit: 56b9be8503a5a1342c0b85b36f5ba6f57c281b63
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2018
ms.locfileid: "43133113"
---
# <a name="powershell-remoting-over-ssh"></a><span data-ttu-id="3f045-103">Удаленное взаимодействие с PowerShell через SSH</span><span class="sxs-lookup"><span data-stu-id="3f045-103">PowerShell Remoting Over SSH</span></span>

## <a name="overview"></a><span data-ttu-id="3f045-104">Обзор</span><span class="sxs-lookup"><span data-stu-id="3f045-104">Overview</span></span>

<span data-ttu-id="3f045-105">Функция удаленного взаимодействия PowerShell обычно использует WinRM для согласования соединения и передачи данных.</span><span class="sxs-lookup"><span data-stu-id="3f045-105">PowerShell remoting normally uses WinRM for connection negotiation and data transport.</span></span> <span data-ttu-id="3f045-106">Теперь протокол SSH доступен на платформах Linux и Windows, что позволяет осуществлять многоплатформенное удаленное взаимодействие с PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3f045-106">SSH is now available for Linux and Windows platforms and allows true multiplatform PowerShell remoting.</span></span>

<span data-ttu-id="3f045-107">Служба удаленного управления Windows обеспечивает надежную модель поддержки удаленных сеансов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3f045-107">WinRM provides a robust hosting model for PowerShell remote sessions.</span></span> <span data-ttu-id="3f045-108">Эта реализация удаленного взаимодействия по протоколу SSH сейчас не поддерживает настройку удаленных конечных точек и функцию JEA (Just Enough Administration).</span><span class="sxs-lookup"><span data-stu-id="3f045-108">which this implementation SSH-based remoting doesn't currently support remote endpoint configuration and JEA (Just Enough Administration).</span></span>

<span data-ttu-id="3f045-109">Удаленное взаимодействие по SSH позволяет осуществлять базовое удаленное взаимодействие между компьютерами Windows и Linux в рамках сеансов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3f045-109">SSH remoting lets you do basic PowerShell session remoting between Windows and Linux machines.</span></span> <span data-ttu-id="3f045-110">Функция удаленного взаимодействия по SSH создает хост-процесс PowerShell на целевом компьютере в качестве подсистемы SSH.</span><span class="sxs-lookup"><span data-stu-id="3f045-110">SSH Remoting creates a PowerShell host process on the target machine as an SSH subsystem.</span></span>
<span data-ttu-id="3f045-111">Со временем для поддержки настройки удаленных конечных точек и функции JEA мы реализуем общую модель размещения, похожую на службе удаленного управления Windows.</span><span class="sxs-lookup"><span data-stu-id="3f045-111">Eventually we'll implement a general hosting model, similar to WinRM, to support endpoint configuration and JEA.</span></span>

<span data-ttu-id="3f045-112">Командлеты `New-PSSession`, `Enter-PSSession` и `Invoke-Command` теперь имеют набор новых параметров для поддержки этой возможности удаленного взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="3f045-112">The `New-PSSession`, `Enter-PSSession`, and `Invoke-Command` cmdlets now have a new parameter set to support this new remoting connection.</span></span>

```
[-HostName <string>]  [-UserName <string>]  [-KeyFilePath <string>]
```

<span data-ttu-id="3f045-113">Для создания удаленного сеанса нужно указать целевой компьютер и имя пользователя с помощью параметров `HostName` и `UserName` соответственно.</span><span class="sxs-lookup"><span data-stu-id="3f045-113">To create a remote session, you specify the target machine with the `HostName` parameter and provide the user name with `UserName`.</span></span> <span data-ttu-id="3f045-114">При интерактивном выполнении командлетов отображается запрос на ввод пароля.</span><span class="sxs-lookup"><span data-stu-id="3f045-114">When running the cmdlets interactively, you're prompted for a password.</span></span> <span data-ttu-id="3f045-115">Также можно настроить аутентификацию по ключу SSH с использованием файла закрытого ключа с помощью параметра `KeyFilePath`.</span><span class="sxs-lookup"><span data-stu-id="3f045-115">You can also, use SSH key authentication using a private key file with the `KeyFilePath` parameter.</span></span>

## <a name="general-setup-information"></a><span data-ttu-id="3f045-116">Общие сведения об установке</span><span class="sxs-lookup"><span data-stu-id="3f045-116">General setup information</span></span>

<span data-ttu-id="3f045-117">Поддержку протокола SSH необходимо реализовать на всех компьютерах.</span><span class="sxs-lookup"><span data-stu-id="3f045-117">SSH must be installed on all machines.</span></span> <span data-ttu-id="3f045-118">Установите клиент (`ssh.exe`) и сервер (`sshd.exe`) SSH, чтобы осуществлять удаленное взаимодействие между компьютерами.</span><span class="sxs-lookup"><span data-stu-id="3f045-118">Install both the SSH client (`ssh.exe`) and server (`sshd.exe`) so that you can remote to and from the machines.</span></span> <span data-ttu-id="3f045-119">В Windows установите [OpenSSH Win32 с сайта GitHub](https://github.com/PowerShell/Win32-OpenSSH/releases).</span><span class="sxs-lookup"><span data-stu-id="3f045-119">For Windows, install [Win32 OpenSSH from GitHub](https://github.com/PowerShell/Win32-OpenSSH/releases).</span></span>
<span data-ttu-id="3f045-120">В Linux нужно реализовать поддержку SSH (включая установку сервера sshd) в соответствии с используемой платформой.</span><span class="sxs-lookup"><span data-stu-id="3f045-120">For Linux, install SSH (including sshd server) appropriate to your platform.</span></span> <span data-ttu-id="3f045-121">Также для поддержки удаленного взаимодействия по SSH нужно установить PowerShell Core с сайта GitHub.</span><span class="sxs-lookup"><span data-stu-id="3f045-121">You also need to install PowerShell Core from GitHub to get the SSH remoting feature.</span></span> <span data-ttu-id="3f045-122">Для сервера SSH нужно настроить возможность создать подсистему SSH для размещения процесса PowerShell на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3f045-122">The SSH server must be configured to create an SSH subsystem to host a PowerShell process on the remote machine.</span></span> <span data-ttu-id="3f045-123">Также нужно активировать аутентификацию на основе ключа или пароля.</span><span class="sxs-lookup"><span data-stu-id="3f045-123">You also must configure enable password or key-based authentication.</span></span>

## <a name="set-up-on-windows-machine"></a><span data-ttu-id="3f045-124">Установка на компьютере Windows</span><span class="sxs-lookup"><span data-stu-id="3f045-124">Set up on Windows Machine</span></span>

1. <span data-ttu-id="3f045-125">Установите последнюю версию [PowerShell Core для Windows].</span><span class="sxs-lookup"><span data-stu-id="3f045-125">Install the latest version of [PowerShell Core for Windows]</span></span>

   - <span data-ttu-id="3f045-126">Чтобы узнать о наличии поддержки удаленного взаимодействия SSH, просмотрите набор параметров для `New-PSSession`.</span><span class="sxs-lookup"><span data-stu-id="3f045-126">You can tell if it has the SSH remoting support by looking at the parameter sets for `New-PSSession`</span></span>

   ```powershell
   Get-Command New-PSSession -syntax
   ```

   ```output
   New-PSSession [-HostName] <string[]> [-Name <string[]>] [-UserName <string>] [-KeyFilePath <string>] [-SSHTransport] [<CommonParameters>]
   ```

2. <span data-ttu-id="3f045-127">Установите последнюю версию сборки [Win32 OpenSSH] из GitHub, используя [инструкции по установке].</span><span class="sxs-lookup"><span data-stu-id="3f045-127">Install the latest [Win32 OpenSSH] build from GitHub using the [installation] instructions</span></span>
3. <span data-ttu-id="3f045-128">Измените файл sshd_config в том расположении, куда вы установили Win32 OpenSSH.</span><span class="sxs-lookup"><span data-stu-id="3f045-128">Edit the sshd_config file at the location where you installed Win32 OpenSSH</span></span>

   - <span data-ttu-id="3f045-129">Включите проверку подлинности с помощью пароля:</span><span class="sxs-lookup"><span data-stu-id="3f045-129">Make sure password authentication is enabled</span></span>

     ```
     PasswordAuthentication yes
     ```

     ```
     Subsystem    powershell c:/program files/powershell/6.0.4/pwsh.exe -sshs -NoLogo -NoProfile
     ```

     > [!NOTE]
     > <span data-ttu-id="3f045-130">В OpenSSH для Windows обнаружена ошибка, блокирующая работу пробелов в путях к исполняемым файлам подсистемы.</span><span class="sxs-lookup"><span data-stu-id="3f045-130">There is a bug in OpenSSH for Windows that prevents spaces from working in subsystem executable paths.</span></span> <span data-ttu-id="3f045-131">См. дополнительные сведения на [сайте GitHub](https://github.com/PowerShell/Win32-OpenSSH/issues/784).</span><span class="sxs-lookup"><span data-stu-id="3f045-131">For more information, see [this GitHub issue](https://github.com/PowerShell/Win32-OpenSSH/issues/784).</span></span>

     <span data-ttu-id="3f045-132">Одно из решений — создать символьную ссылку на папку установки Powershell, которая не содержит пробелы:</span><span class="sxs-lookup"><span data-stu-id="3f045-132">One solution is to create a symlink to the Powershell installation directory that doesn't have spaces:</span></span>

     ```powershell
     mklink /D c:\pwsh "C:\Program Files\PowerShell\6.0.4"
     ```

     <span data-ttu-id="3f045-133">а затем ввести ее в подсистеме:</span><span class="sxs-lookup"><span data-stu-id="3f045-133">and then enter it in the subsystem:</span></span>

     ```
     Subsystem    powershell c:\pwsh\pwsh.exe -sshs -NoLogo -NoProfile
     ```

   - <span data-ttu-id="3f045-134">При необходимости включите проверку подлинности на основе ключа:</span><span class="sxs-lookup"><span data-stu-id="3f045-134">Optionally enable key authentication</span></span>

     ```
     PubkeyAuthentication yes
     ```

4. <span data-ttu-id="3f045-135">Перезапустите службу sshd.</span><span class="sxs-lookup"><span data-stu-id="3f045-135">Restart the sshd service</span></span>

   ```powershell
   Restart-Service sshd
   ```

5. <span data-ttu-id="3f045-136">Добавьте путь установки OpenSSH в свою переменную среды Path.</span><span class="sxs-lookup"><span data-stu-id="3f045-136">Add the path where OpenSSH is installed to your Path environment variable.</span></span> <span data-ttu-id="3f045-137">Например, `C:\Program Files\OpenSSH\`.</span><span class="sxs-lookup"><span data-stu-id="3f045-137">For example, `C:\Program Files\OpenSSH\`.</span></span> <span data-ttu-id="3f045-138">Это позволит найти файл ssh.exe.</span><span class="sxs-lookup"><span data-stu-id="3f045-138">This entry allows for the ssh.exe to be found.</span></span>

## <a name="set-up-on-linux-ubuntu-1404-machine"></a><span data-ttu-id="3f045-139">Установка на компьютере Linux (Ubuntu 14.04)</span><span class="sxs-lookup"><span data-stu-id="3f045-139">Set up on Linux (Ubuntu 14.04) Machine</span></span>

1. <span data-ttu-id="3f045-140">Установите последнюю сборку [PowerShell Core для Linux] из GitHub.</span><span class="sxs-lookup"><span data-stu-id="3f045-140">Install the latest [PowerShell Core for Linux] build from GitHub</span></span>
2. <span data-ttu-id="3f045-141">При необходимости установите [Ubuntu SSH].</span><span class="sxs-lookup"><span data-stu-id="3f045-141">Install [Ubuntu SSH] as needed</span></span>

   ```bash
   sudo apt install openssh-client
   sudo apt install openssh-server
   ```

3. <span data-ttu-id="3f045-142">Измените файл sshd_config в расположении /etc/ssh.</span><span class="sxs-lookup"><span data-stu-id="3f045-142">Edit the sshd_config file at location /etc/ssh</span></span>

   - <span data-ttu-id="3f045-143">Включите проверку подлинности с помощью пароля:</span><span class="sxs-lookup"><span data-stu-id="3f045-143">Make sure password authentication is enabled</span></span>

   ```
   PasswordAuthentication yes
   ```

   - <span data-ttu-id="3f045-144">Добавьте запись подсистемы PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3f045-144">Add a PowerShell subsystem entry</span></span>

   ```
   Subsystem powershell /usr/bin/pwsh -sshs -NoLogo -NoProfile
   ```

   - <span data-ttu-id="3f045-145">При необходимости включите проверку подлинности на основе ключа:</span><span class="sxs-lookup"><span data-stu-id="3f045-145">Optionally enable key authentication</span></span>

   ```
   PubkeyAuthentication yes
   ```

4. <span data-ttu-id="3f045-146">Перезапустите службу sshd.</span><span class="sxs-lookup"><span data-stu-id="3f045-146">Restart the sshd service</span></span>

   ```bash
   sudo service sshd restart
   ```

## <a name="set-up-on-macos-machine"></a><span data-ttu-id="3f045-147">Установка на компьютере MacOS</span><span class="sxs-lookup"><span data-stu-id="3f045-147">Set up on MacOS Machine</span></span>

1. <span data-ttu-id="3f045-148">Установите последнюю сборку [PowerShell Core для MacOS].</span><span class="sxs-lookup"><span data-stu-id="3f045-148">Install the latest [PowerShell Core for MacOS] build</span></span>

   - <span data-ttu-id="3f045-149">Убедитесь, что удаленное взаимодействие SSH включено, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="3f045-149">Make sure SSH Remoting is enabled by following these steps:</span></span>
     - <span data-ttu-id="3f045-150">Откройте `System Preferences`.</span><span class="sxs-lookup"><span data-stu-id="3f045-150">Open `System Preferences`</span></span>
     - <span data-ttu-id="3f045-151">Щелкните `Sharing`.</span><span class="sxs-lookup"><span data-stu-id="3f045-151">Click on `Sharing`</span></span>
     - <span data-ttu-id="3f045-152">Убедитесь, что `Remote Login` имеет значение `Remote Login: On`.</span><span class="sxs-lookup"><span data-stu-id="3f045-152">Check `Remote Login` - Should say `Remote Login: On`</span></span>
     - <span data-ttu-id="3f045-153">Разрешите доступ соответствующим пользователям.</span><span class="sxs-lookup"><span data-stu-id="3f045-153">Allow access to appropriate users</span></span>

2. <span data-ttu-id="3f045-154">Измените файл `sshd_config` в расположении `/private/etc/ssh/sshd_config`.</span><span class="sxs-lookup"><span data-stu-id="3f045-154">Edit the `sshd_config` file at location `/private/etc/ssh/sshd_config`</span></span>

   - <span data-ttu-id="3f045-155">Используйте привычный вам редактор или следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3f045-155">Use your favorite editor or</span></span>

     ```bash
     sudo nano /private/etc/ssh/sshd_config
     ```

   - <span data-ttu-id="3f045-156">Включите проверку подлинности с помощью пароля:</span><span class="sxs-lookup"><span data-stu-id="3f045-156">Make sure password authentication is enabled</span></span>

     ```
     PasswordAuthentication yes
     ```

   - <span data-ttu-id="3f045-157">Добавьте запись подсистемы PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3f045-157">Add a PowerShell subsystem entry</span></span>

     ```
     Subsystem powershell /usr/local/bin/pwsh -sshs -NoLogo -NoProfile
     ```

   - <span data-ttu-id="3f045-158">При необходимости включите проверку подлинности на основе ключа:</span><span class="sxs-lookup"><span data-stu-id="3f045-158">Optionally enable key authentication</span></span>

     ```
     PubkeyAuthentication yes
     ```

3. <span data-ttu-id="3f045-159">Перезапустите службу sshd.</span><span class="sxs-lookup"><span data-stu-id="3f045-159">Restart the sshd service</span></span>

   ```bash
   sudo launchctl stop com.openssh.sshd
   sudo launchctl start com.openssh.sshd
   ```

## <a name="powershell-remoting-example"></a><span data-ttu-id="3f045-160">Пример удаленного взаимодействия PowerShell</span><span class="sxs-lookup"><span data-stu-id="3f045-160">PowerShell Remoting Example</span></span>

<span data-ttu-id="3f045-161">Проще всего проверить удаленное взаимодействие на одном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3f045-161">The easiest way to test remoting is to try it on a single machine.</span></span> <span data-ttu-id="3f045-162">В этом примере мы создадим удаленный сеанс с одним и тем же компьютером Linux.</span><span class="sxs-lookup"><span data-stu-id="3f045-162">In this example, we create a remote session back to the same Linux machine.</span></span> <span data-ttu-id="3f045-163">Командлеты PowerShell мы выполняем в интерактивном режиме, поэтому мы увидим запрос от SSH на проверку удаленного компьютера, а также запрос на ввод пароля.</span><span class="sxs-lookup"><span data-stu-id="3f045-163">We are using PowerShell cmdlets interactively so we see prompts from SSH asking to verify the host computer and prompting for a password.</span></span> <span data-ttu-id="3f045-164">Чтобы убедиться, что удаленное взаимодействие работает, те же операции можно выполнить на компьютере Windows.</span><span class="sxs-lookup"><span data-stu-id="3f045-164">You can do the same thing on a Windows machine to ensure remoting is working.</span></span> <span data-ttu-id="3f045-165">Затем установите удаленное подключение между компьютерами, изменив имя узла.</span><span class="sxs-lookup"><span data-stu-id="3f045-165">Then remote between machines by changing the host name.</span></span>

```powershell
#
# Linux to Linux
#
$session = New-PSSession -HostName UbuntuVM1 -UserName TestUser
```

```output
The authenticity of host 'UbuntuVM1 (9.129.17.107)' cannot be established.
ECDSA key fingerprint is SHA256:2kCbnhT2dUE6WCGgVJ8Hyfu1z2wE4lifaJXLO7QJy0Y.
Are you sure you want to continue connecting (yes/no)?
TestUser@UbuntuVM1s password:
```

```powershell
$session
```

```output
 Id Name   ComputerName    ComputerType    State    ConfigurationName     Availability
 -- ----   ------------    ------------    -----    -----------------     ------------
  1 SSH1   UbuntuVM1       RemoteMachine   Opened   DefaultShell             Available
```

```powershell
Enter-PSSession $session
```

```output
[UbuntuVM1]: PS /home/TestUser> uname -a
Linux TestUser-UbuntuVM1 4.2.0-42-generic 49~14.04.1-Ubuntu SMP Wed Jun 29 20:22:11 UTC 2016 x86_64 x86_64 x86_64 GNU/Linux

[UbuntuVM1]: PS /home/TestUser> Exit-PSSession
```

```powershell
Invoke-Command $session -ScriptBlock { Get-Process powershell }
```

```output
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

```output
PTestName@WinVM1s password:
```

```powershell
[WinVM1]: PS C:\Users\PTestName\Documents> cmd /c ver
```

```output
Microsoft Windows [Version 10.0.10586]
```

```powershell
#
# Windows to Windows
#
C:\Users\PSUser\Documents>pwsh.exe
```

```output
PowerShell
Copyright (c) Microsoft Corporation. All rights reserved.
```

```powershell
$session = New-PSSession -HostName WinVM2 -UserName PSRemoteUser
```

```output
The authenticity of host 'WinVM2 (10.13.37.3)' can't be established.
ECDSA key fingerprint is SHA256:kSU6slAROyQVMEynVIXAdxSiZpwDBigpAF/TXjjWjmw.
Are you sure you want to continue connecting (yes/no)?
Warning: Permanently added 'WinVM2,10.13.37.3' (ECDSA) to the list of known hosts.
PSRemoteUser@WinVM2's password:
```

```powershell
$session
```

```output
 Id Name            ComputerName    ComputerType    State         ConfigurationName     Availability
 -- ----            ------------    ------------    -----         -----------------     ------------
  1 SSH1            WinVM2          RemoteMachine   Opened        DefaultShell             Available
```

```powershell
Enter-PSSession -Session $session
```

```output
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

### <a name="known-issues"></a><span data-ttu-id="3f045-166">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="3f045-166">Known Issues</span></span>

<span data-ttu-id="3f045-167">Команда sudo не работает в рамках сеанса удаленного взаимодействия с компьютером Linux.</span><span class="sxs-lookup"><span data-stu-id="3f045-167">The sudo command doesn't work in remote session to Linux machine.</span></span>

## <a name="see-also"></a><span data-ttu-id="3f045-168">См. также</span><span class="sxs-lookup"><span data-stu-id="3f045-168">See Also</span></span>

[<span data-ttu-id="3f045-169">PowerShell Core для Windows</span><span class="sxs-lookup"><span data-stu-id="3f045-169">PowerShell Core for Windows</span></span>](../setup/installing-powershell-core-on-windows.md#msi)

[<span data-ttu-id="3f045-170">PowerShell Core для Windows</span><span class="sxs-lookup"><span data-stu-id="3f045-170">PowerShell Core for Linux</span></span>](../setup/installing-powershell-core-on-linux.md#ubuntu-1404)

[<span data-ttu-id="3f045-171">PowerShell Core для MacOS</span><span class="sxs-lookup"><span data-stu-id="3f045-171">PowerShell Core for MacOS</span></span>](../setup/installing-powershell-core-on-macos.md)

[<span data-ttu-id="3f045-172">Win32 OpenSSH</span><span class="sxs-lookup"><span data-stu-id="3f045-172">Win32 OpenSSH</span></span>](https://github.com/PowerShell/Win32-OpenSSH/releases)

[<span data-ttu-id="3f045-173">установка</span><span class="sxs-lookup"><span data-stu-id="3f045-173">installation</span></span>](https://github.com/PowerShell/Win32-OpenSSH/wiki/Install-Win32-OpenSSH)

[<span data-ttu-id="3f045-174">Ubuntu SSH</span><span class="sxs-lookup"><span data-stu-id="3f045-174">Ubuntu SSH</span></span>](https://help.ubuntu.com/lts/serverguide/openssh-server.html)
