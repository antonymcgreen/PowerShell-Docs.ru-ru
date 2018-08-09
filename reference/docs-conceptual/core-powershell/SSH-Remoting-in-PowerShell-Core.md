---
title: Удаленное взаимодействие с PowerShell через SSH
description: Удаленное взаимодействие в PowerShell Core с помощью SSH
ms.date: 08/06/2018
ms.openlocfilehash: 27a8fc5623796a270a2ea67aa550c9a0998e766b
ms.sourcegitcommit: 01ac77cd0b00e4e5e964504563a9212e8002e5e0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2018
ms.locfileid: "39587505"
---
# <a name="powershell-remoting-over-ssh"></a>Удаленное взаимодействие с PowerShell через SSH

## <a name="overview"></a>Обзор

Функция удаленного взаимодействия PowerShell обычно использует WinRM для согласования соединения и передачи данных. Протокол SSH был выбран для этой реализации удаленного взаимодействия, так как он теперь доступен для платформ Linux и Windows и позволяет реализовать действительно многоплатформенное удаленное взаимодействие PowerShell. Однако WinRM также предоставляет надежную модель размещения для удаленных сеансов PowerShell, которой пока нет в этой реализации. Это значит, что конфигурация удаленной конечной точки PowerShell и JEA (Just Enough Administration) в этой реализации пока не поддерживается.

Удаленное взаимодействие по SSH в PowerShell позволяет выполнять базовые операции удаленной работы с сеансами PowerShell между компьютерами с Windows и Linux. Для этого на целевом компьютере создается ведущий процесс PowerShell в качестве подсистемы SSH. В конечном счете, все это будет заменено более общей моделью размещения, которая аналогична тому, как WinRM обеспечивает поддержку конфигурации конечной точки и JEA.

Командлеты `New-PSSession`, `Enter-PSSession` и `Invoke-Command` теперь имеют новый набор параметров, призванный упростить новое удаленное подключение.

```
[-HostName <string>]  [-UserName <string>]  [-KeyFilePath <string>]
```

Этот новый набор параметров, скорее всего, изменится, но сейчас он позволяет создавать сеансы SSH PSSession, с которыми можно взаимодействовать с помощью командной строки либо вызова команд и сценариев. Вы можете указать целевой компьютер с помощью параметра HostName и имя пользователя с помощью параметра UserName. При интерактивном выполнении командлетов в командной строке PowerShell вам будет предложено ввести пароль. Но вы также можете использовать проверку подлинности на основе ключа SSH и указать путь к файлу закрытого ключа с помощью параметра KeyFilePath.

## <a name="general-setup-information"></a>Общие сведения об установке

SSH должен быть установлен на всех компьютерах. Вам нужно установить клиент (`ssh.exe`) и сервер (`sshd.exe`), чтобы можно было поэкспериментировать с удаленным взаимодействием к компьютерам и с них. Для Windows нужно установить [Win32 OpenSSH из GitHub](https://github.com/PowerShell/Win32-OpenSSH/releases).
Для Linux нужно установить SSH (включая сервер sshd) в соответствии с используемой платформой. Вам также потребуется новая версия сборки или пакета PowerShell с GitHub, где есть функция удаленного взаимодействия SSH.
Подсистемы SSH используются для запуска процесса PowerShell на удаленном компьютере, поэтому сервер SSH нужно настроить соответствующим образом. Кроме того, нужно включить проверку подлинности с помощью пароля и при необходимости проверку подлинности на основе ключа.

## <a name="setup-on-windows-machine"></a>Установка на компьютере с Windows

1. Установите последнюю версию [PowerShell Core для Windows].

   - Чтобы узнать о наличии поддержки удаленного взаимодействия SSH, просмотрите набор параметров для `New-PSSession`.

   ```powershell
   Get-Command New-PSSession -syntax
   ```

   ```output
   New-PSSession [-HostName] <string[]> [-Name <string[]>] [-UserName <string>] [-KeyFilePath <string>] [-SSHTransport] [<CommonParameters>]
   ```

2. Установите последнюю версию сборки [Win32 OpenSSH] из GitHub, используя [инструкции по установке].
3. Измените файл sshd_config в том расположении, куда вы установили Win32 OpenSSH.

   - Включите проверку подлинности с помощью пароля:

     ```
     PasswordAuthentication yes
     ```

     ```
     Subsystem    powershell c:/program files/powershell/6.0.0/pwsh.exe -sshs -NoLogo -NoProfile
     ```

     > [!NOTE]
     > В OpenSSH для Windows обнаружена ошибка, блокирующая работу пробелов в путях к исполняемым файлам подсистемы.
     > Дополнительные сведения об [этой проблеме см. на сайте GitHub](https://github.com/PowerShell/Win32-OpenSSH/issues/784).

     Одно из решений — создать символьную ссылку на каталог установки Powershell, которая не содержит пробелы:

     ```powershell
     mklink /D c:\pwsh "C:\Program Files\PowerShell\6.0.0"
     ```

     а затем ввести ее в подсистеме:

     ```
     Subsystem    powershell c:\pwsh\pwsh.exe -sshs -NoLogo -NoProfile
     ```

     ```
     Subsystem    powershell c:/program files/powershell/6.0.0/pwsh.exe -sshs -NoLogo -NoProfile
     ```

   - При необходимости включите проверку подлинности на основе ключа:

     ```
     PubkeyAuthentication yes
     ```

4. Перезапустите службу sshd.

   ```powershell
   Restart-Service sshd
   ```

5. Добавьте путь установки OpenSSH в свою переменную пути Env.

   - Это нужно сделать в соответствии с `C:\Program Files\OpenSSH\`.
   - Это позволяет найти ssh.exe.

## <a name="setup-on-linux-ubuntu-1404-machine"></a>Установка на компьютере с Linux (Ubuntu 14.04)

1. Установите последнюю сборку [PowerShell Core для Linux] из GitHub.
2. При необходимости установите [Ubuntu SSH].

   ```bash
   sudo apt install openssh-client
   sudo apt install openssh-server
   ```

3. Измените файл sshd_config в расположении /etc/ssh.

   - Включите проверку подлинности с помощью пароля:

   ```
   PasswordAuthentication yes
   ```

   - Добавьте запись подсистемы PowerShell:

   ```
   Subsystem powershell /usr/bin/pwsh -sshs -NoLogo -NoProfile
   ```

   - При необходимости включите проверку подлинности на основе ключа:

   ```
   PubkeyAuthentication yes
   ```

4. Перезапустите службу sshd.

   ```bash
   sudo service sshd restart
   ```

## <a name="setup-on-macos-machine"></a>Установка на компьютере с MacOS

1. Установите последнюю сборку [PowerShell Core для MacOS].

   - Убедитесь, что удаленное взаимодействие SSH включено, выполните следующие действия:
     - Откройте `System Preferences`.
     - Щелкните `Sharing`.
     - Убедитесь, что `Remote Login` имеет значение `Remote Login: On`.
     - Разрешите доступ соответствующим пользователям.

2. Измените файл `sshd_config` в расположении `/private/etc/ssh/sshd_config`.

   - Используйте привычный вам редактор или следующую команду:

     ```bash
     sudo nano /private/etc/ssh/sshd_config
     ```

   - Включите проверку подлинности с помощью пароля:

     ```
     PasswordAuthentication yes
     ```

   - Добавьте запись подсистемы PowerShell:

     ```
     Subsystem powershell /usr/local/bin/pwsh -sshs -NoLogo -NoProfile
     ```

   - При необходимости включите проверку подлинности на основе ключа:

     ```
     PubkeyAuthentication yes
     ```

3. Перезапустите службу sshd.

   ```bash
   sudo launchctl stop com.openssh.sshd
   sudo launchctl start com.openssh.sshd
   ```

## <a name="powershell-remoting-example"></a>Пример удаленного взаимодействия PowerShell

Проще всего проверить удаленное взаимодействие, просто попробовав использовать его на отдельном компьютере. Здесь я создам удаленный сеанс на том же компьютере в окне Linux. Обратите внимание, что я использую командлеты PowerShell из командной строки, поэтому мы видим запросы SSH о проверке главного компьютера, а также запросы на ввод пароля. То же самое можно сделать на компьютере с Windows, чтобы убедиться в работе удаленного взаимодействия, а затем удаленно переключаться между компьютерами, просто изменяя имя узла.

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
 Id Name            ComputerName    ComputerType    State         ConfigurationName     Availability
 -- ----            ------------    ------------    -----         -----------------     ------------
  1 SSH1            UbuntuVM1       RemoteMachine   Opened        DefaultShell             Available
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

### <a name="known-issues"></a>Известные проблемы

Команда sudo не работает во входящем удаленном сеансе на компьютере Linux.

## <a name="see-also"></a>См. также

[PowerShell Core для Windows](../setup/installing-powershell-core-on-windows.md#msi)

[PowerShell Core для Windows](../setup/installing-powershell-core-on-linux.md#ubuntu-1404)

[PowerShell Core для MacOS](../setup/installing-powershell-core-on-macos.md)

[Win32 OpenSSH](https://github.com/PowerShell/Win32-OpenSSH/releases)

[установка](https://github.com/PowerShell/Win32-OpenSSH/wiki/Install-Win32-OpenSSH)

[Ubuntu SSH](https://help.ubuntu.com/lts/serverguide/openssh-server.html)