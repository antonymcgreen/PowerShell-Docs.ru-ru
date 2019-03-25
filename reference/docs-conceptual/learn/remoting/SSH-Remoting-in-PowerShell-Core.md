---
title: Удаленное взаимодействие с PowerShell через SSH
description: Удаленное взаимодействие в PowerShell Core с помощью SSH
ms.date: 08/14/2018
ms.openlocfilehash: 1d7bcb69c7e784bf745cb5c2633106ea53f6226a
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/18/2019
ms.locfileid: "58056538"
---
# <a name="powershell-remoting-over-ssh"></a>Удаленное взаимодействие с PowerShell через SSH

## <a name="overview"></a>Обзор

Функция удаленного взаимодействия PowerShell обычно использует WinRM для согласования соединения и передачи данных. Теперь протокол SSH доступен на платформах Linux и Windows, что позволяет осуществлять многоплатформенное удаленное взаимодействие с PowerShell.

Служба удаленного управления Windows обеспечивает надежную модель поддержки удаленных сеансов PowerShell. Удаленное взаимодействие по протоколу SSH сейчас не поддерживает настройку удаленных конечных точек и функцию JEA (Just Enough Administration).

Удаленное взаимодействие по SSH позволяет осуществлять базовое удаленное взаимодействие между компьютерами Windows и Linux в рамках сеансов PowerShell. Функция удаленного взаимодействия по SSH создает хост-процесс PowerShell на целевом компьютере в качестве подсистемы SSH.
Со временем для поддержки настройки удаленных конечных точек и функции JEA мы реализуем общую модель размещения, похожую на службе удаленного управления Windows.

Командлеты `New-PSSession`, `Enter-PSSession` и `Invoke-Command` теперь имеют набор новых параметров для поддержки этой возможности удаленного взаимодействия.

```
[-HostName <string>]  [-UserName <string>]  [-KeyFilePath <string>]
```

Для создания удаленного сеанса нужно указать целевой компьютер и имя пользователя с помощью параметров `HostName` и `UserName` соответственно. При интерактивном выполнении командлетов отображается запрос на ввод пароля. Также можно настроить аутентификацию по ключу SSH с использованием файла закрытого ключа с помощью параметра `KeyFilePath`.

## <a name="general-setup-information"></a>Общие сведения об установке

Поддержку протокола SSH необходимо реализовать на всех компьютерах. Установите клиент (`ssh.exe`) и сервер (`sshd.exe`) SSH, чтобы осуществлять удаленное взаимодействие между компьютерами. OpenSSH для Windows теперь доступна в Windows 10 сборки 1809 и Windows Server 2019. Дополнительные сведения см. в разделе [OpenSSH для Windows](/windows-server/administration/openssh/openssh_overview). В Linux нужно реализовать поддержку SSH (включая установку сервера sshd) в соответствии с используемой платформой. Также для поддержки удаленного взаимодействия по SSH нужно установить PowerShell Core с сайта GitHub. Для сервера SSH нужно настроить возможность создать подсистему SSH для размещения процесса PowerShell на удаленном компьютере. Также нужно активировать аутентификацию на основе ключа или пароля.

## <a name="set-up-on-windows-machine"></a>Установка на компьютере Windows

1. Установите последнюю версию [PowerShell Core для Windows](../../install/installing-powershell-core-on-windows.md#msi).

   - Чтобы узнать о наличии поддержки удаленного взаимодействия SSH, просмотрите набор параметров для `New-PSSession`.

   ```powershell
   Get-Command New-PSSession -syntax
   ```

   ```output
   New-PSSession [-HostName] <string[]> [-Name <string[]>] [-UserName <string>] [-KeyFilePath <string>] [-SSHTransport] [<CommonParameters>]
   ```

2. Установите последнюю версию Win32 OpenSSH. Инструкции по установке см. в статье [Установка OpenSSH](/windows-server/administration/openssh/openssh_install_firstuse).
3. Измените файл `sshd_config`, расположенный в `$env:ProgramData\ssh`.

   - Включите проверку подлинности с помощью пароля:

     ```
     PasswordAuthentication yes
     ```

     ```
     Subsystem    powershell c:/program files/powershell/6/pwsh.exe -sshs -NoLogo -NoProfile
     ```

     > [!NOTE]
     > В OpenSSH для Windows обнаружена ошибка, блокирующая работу пробелов в путях к исполняемым файлам подсистемы. См. дополнительные сведения на [сайте GitHub](https://github.com/PowerShell/Win32-OpenSSH/issues/784).

     Одно из решений — создать символьную ссылку на папку установки PowerShell, которая не содержит пробелы:

     ```powershell
     mklink /D c:\pwsh "C:\Program Files\PowerShell\6"
     ```

     а затем ввести ее в подсистеме:

     ```
     Subsystem    powershell c:\pwsh\pwsh.exe -sshs -NoLogo -NoProfile
     ```

   - При необходимости включите проверку подлинности на основе ключа:

     ```
     PubkeyAuthentication yes
     ```

4. Перезапустите службу sshd.

   ```powershell
   Restart-Service sshd
   ```

5. Добавьте путь установки OpenSSH в свою переменную среды Path. Например, `C:\Program Files\OpenSSH\`. Это позволит найти файл ssh.exe.

## <a name="set-up-on-linux-ubuntu-1404-machine"></a>Установка на компьютере Linux (Ubuntu 14.04)

1. Установите последнюю сборку [PowerShell Core для Linux](../../install/installing-powershell-core-on-linux.md#ubuntu-1404) из GitHub.
2. При необходимости установите [Ubuntu SSH](https://help.ubuntu.com/lts/serverguide/openssh-server.html).

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

## <a name="set-up-on-macos-machine"></a>Установка на компьютере MacOS

1. Установите последнюю сборку [PowerShell Core для MacOS](../../install/installing-powershell-core-on-macos.md).

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

## <a name="authentication"></a>Проверка подлинности

При удаленном взаимодействии с PowerShell через SSH используется обмен данными для проверки подлинности между клиентом SSH и службой SSH. Схемы проверки подлинности в его рамках не реализуются.
Это означает, что любые настроенные схемы проверки подлинности, включая многофакторную проверку подлинности, обрабатываются протоколом SSH независимо от PowerShell.
Например, в службе SSH можно настроить обязательное применение проверки подлинности на основе открытых ключей, а также разовых паролей для усиления безопасности.
Настройка многофакторной проверки подлинности выходит за рамки настоящего документа.
Сведения о том, как правильно настроить многофакторную проверку подлинности и проверить ее работу вне PowerShell, прежде чем пытаться использовать ее для удаленного взаимодействия с PowerShell, см. в документации по SSH.

## <a name="powershell-remoting-example"></a>Пример удаленного взаимодействия PowerShell

Проще всего проверить удаленное взаимодействие на одном компьютере. В этом примере мы создадим удаленный сеанс с одним и тем же компьютером Linux. Командлеты PowerShell мы выполняем в интерактивном режиме, поэтому мы увидим запрос от SSH на проверку удаленного компьютера, а также запрос на ввод пароля. Чтобы убедиться, что удаленное взаимодействие работает, те же операции можно выполнить на компьютере Windows. Затем установите удаленное подключение между компьютерами, изменив имя узла.

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

### <a name="known-issues"></a>Известные проблемы

Команда sudo не работает в рамках сеанса удаленного взаимодействия с компьютером Linux.

## <a name="see-also"></a>См. также

[PowerShell Core для Windows](../../install/installing-powershell-core-on-windows.md#msi)

[PowerShell Core для Windows](../../install/installing-powershell-core-on-linux.md#ubuntu-1404)

[PowerShell Core для MacOS](../../install/installing-powershell-core-on-macos.md)

[OpenSSH для Windows](/windows-server/administration/openssh/openssh_overview)

[Ubuntu SSH](https://help.ubuntu.com/lts/serverguide/openssh-server.html)
