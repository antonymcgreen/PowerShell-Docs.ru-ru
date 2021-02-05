---
title: Удаленное взаимодействие с PowerShell через SSH
ms.date: 10/19/2020
description: Описывается, как настроить протокол SSH для удаленного взаимодействия PowerShell.
ms.openlocfilehash: c3373ac30fd915d42e8c9fb7f1eae348a2aee7f1
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92501343"
---
# <a name="powershell-remoting-over-ssh"></a>Удаленное взаимодействие с PowerShell через SSH

## <a name="overview"></a>Обзор

Функция удаленного взаимодействия PowerShell обычно использует WinRM для согласования соединения и передачи данных. Теперь протокол SSH доступен на платформах Linux и Windows, что позволяет осуществлять многоплатформенное удаленное взаимодействие с PowerShell.

Служба удаленного управления Windows обеспечивает надежную модель поддержки удаленных сеансов PowerShell. Удаленное взаимодействие по протоколу SSH сейчас не поддерживает настройку удаленных конечных точек и функцию JEA (Just Enough Administration).

Удаленное взаимодействие по SSH позволяет осуществлять базовое удаленное взаимодействие между компьютерами с Windows и Linux в рамках сеансов PowerShell. Функция удаленного взаимодействия по SSH создает хост-процесс PowerShell на целевом компьютере в качестве подсистемы SSH. Со временем для поддержки настройки удаленных конечных точек и функции JEA мы реализуем общую модель размещения, похожую на службе удаленного управления Windows.

Командлеты `New-PSSession`, `Enter-PSSession` и `Invoke-Command` теперь имеют набор новых параметров для поддержки этой возможности удаленного взаимодействия.

```
[-HostName <string>]  [-UserName <string>]  [-KeyFilePath <string>]
```

Чтобы создать удаленный сеанс, укажите целевой компьютер с помощью параметра **HostName** и имя пользователя с помощью параметра **UserName**. При интерактивном выполнении командлетов отображается запрос на ввод пароля. Вы также можете использовать проверку подлинности ключа SSH с помощью файла закрытого ключа с параметром **KeyFilePath**. Способ создания ключей для проверки подлинности по протоколу SSH зависит от платформы.

## <a name="general-setup-information"></a>Общие сведения об установке

PowerShell 6 или более поздней версии, и на всех компьютерах должен быть установлен SSH. Установите клиент (`ssh.exe`) и сервер (`sshd.exe`) SSH, чтобы осуществлять удаленное взаимодействие между компьютерами. Решение OpenSSH для Windows теперь доступно в Windows 10 сборки 1809 и Windows Server 2019. Дополнительные сведения см. в статье [Управление Windows через OpenSSH](/windows-server/administration/openssh/openssh_overview). В Linux нужно реализовать поддержку SSH (включая установку сервера sshd) в соответствии с используемой платформой. Также для поддержки удаленного взаимодействия по SSH нужно установить PowerShell с сайта GitHub. Для сервера SSH нужно настроить возможность создать подсистему SSH для размещения процесса PowerShell на удаленном компьютере. Также нужно активировать проверку подлинности на основе **пароля** или **ключа**.

## <a name="set-up-on-a-windows-computer"></a>Настройка на компьютере с Windows

1. Установите последнюю версию PowerShell. Дополнительные сведения см. в статье [Установка PowerShell Core в Windows](../../install/installing-powershell-core-on-windows.md#msi).

   Чтобы убедиться, что в PowerShell есть поддержка удаленного взаимодействия SSH, перечислите наборы параметров `New-PSSession`. Обратите внимание на наличие имен наборов параметров, начинающихся с **SSH**. К этим наборам параметров относятся параметры **SSH**.

   ```powershell
   (Get-Command New-PSSession).ParameterSets.Name
   ```

   ```Output
   Name
   ----
   SSHHost
   SSHHostHashParam
   ```

1. Установите последнюю версию Win32 OpenSSH. Инструкции по установке см. в разделе [Начало работы с OpenSSH](/windows-server/administration/openssh/openssh_install_firstuse).

   > [!NOTE]
   > Если вы хотите задать PowerShell в качестве оболочки по умолчанию для OpenSSH, см. раздел [Настройка Windows для OpenSSH](/windows-server/administration/openssh/openssh_server_configuration).

1. Измените файл `sshd_config`, расположенный в `$env:ProgramData\ssh`.

   Включите проверку подлинности с помощью пароля:

   ```
   PasswordAuthentication yes
   ```

   Создайте подсистему SSH, в которой размещается процесс PowerShell на удаленном компьютере:

   ```
   Subsystem powershell c:/progra~1/powershell/7/pwsh.exe -sshs -NoLogo
   ```

   > [!NOTE]
   > Расположение исполняемого файла PowerShell по умолчанию — `c:/progra~1/powershell/7/pwsh.exe`. Расположение может различаться в зависимости от способа установки PowerShell.
   >
   > Необходимо использовать краткое имя 8.3 для всех путей к файлам, содержащим пробелы. В OpenSSH для Windows обнаружена ошибка, блокирующая работу пробелов в путях к исполняемым файлам подсистемы. См. дополнительные сведения на [сайте GitHub](https://github.com/PowerShell/Win32-OpenSSH/issues/784).
   >
   > Обычно краткое имя 8.3 для папки `Program Files` в Windows — это `Progra~1`. Тем не менее для проверки можно использовать следующую команду:
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

   При необходимости включите проверку подлинности на основе ключа:

   ```
   PubkeyAuthentication yes
   ```

   Дополнительные сведения см. в статье [Управление ключами OpenSSH](/windows-server/administration/openssh/openssh_keymanagement).

1. Перезапустите службу **sshd**.

   ```powershell
   Restart-Service sshd
   ```

1. Добавьте путь установки OpenSSH в свою переменную среды Path. Например, `C:\Program Files\OpenSSH\`. Это позволит найти файл `ssh.exe`.

## <a name="set-up-on-an-ubuntu-1604-linux-computer"></a>Настройка на компьютере с Ubuntu 16.04 Linux

1. Установите последнюю версию PowerShell, см. раздел [Установка PowerShell Core в Linux](../../install/installing-powershell-core-on-linux.md#ubuntu-1604).
1. Установите [сервер OpenSSH для Ubuntu](https://help.ubuntu.com/lts/serverguide/openssh-server.html).

   ```bash
   sudo apt install openssh-client
   sudo apt install openssh-server
   ```

1. Измените файл `sshd_config` в расположении `/etc/ssh`.

   Включите проверку подлинности с помощью пароля:

   ```
   PasswordAuthentication yes
   ```

   При необходимости включите проверку подлинности на основе ключа:

   ```
   PubkeyAuthentication yes
   ```

   Дополнительные сведения о создании ключей SSH в Ubuntu см. на странице справки по [ssh-keygen](http://manpages.ubuntu.com/manpages/xenial/man1/ssh-keygen.1.html).

   Добавьте запись подсистемы PowerShell:

   ```
   Subsystem powershell /usr/bin/pwsh -sshs -NoLogo
   ```

   > [!NOTE]
   > Расположение исполняемого файла PowerShell по умолчанию — `/usr/bin/pwsh`. Расположение может различаться в зависимости от способа установки PowerShell.

   При необходимости включите проверку подлинности на основе ключа:

   ```
   PubkeyAuthentication yes
   ```

1. Перезапустите службу **ssh**.

   ```bash
   sudo service ssh restart
   ```

## <a name="set-up-on-a-macos-computer"></a>Настройка на компьютере с macOS

1. Установите последнюю версию PowerShell. Дополнительные сведения см. в статье [Установка PowerShell Core в macOS](../../install/installing-powershell-core-on-macos.md).

   Убедитесь, что удаленное взаимодействие SSH включено, выполните следующие действия:

   1. Откройте среду `System Preferences`.
   1. Щелкните `Sharing`.
   1. Установите флажок `Remote Login`, чтобы задать `Remote Login: On`.
   1. Разрешите доступ соответствующим пользователям.

1. Измените файл `sshd_config` в расположении `/private/etc/ssh/sshd_config`.

   Используйте текстовый редактор, например **nano**:

   ```bash
   sudo nano /private/etc/ssh/sshd_config
   ```

   Включите проверку подлинности с помощью пароля:

   ```
   PasswordAuthentication yes
   ```

   Добавьте запись подсистемы PowerShell:

   ```
   Subsystem powershell /usr/local/bin/pwsh -sshs -NoLogo
   ```

   > [!NOTE]
   > Расположение исполняемого файла PowerShell по умолчанию — `/usr/local/bin/pwsh`. Расположение может различаться в зависимости от способа установки PowerShell.

   При необходимости включите проверку подлинности на основе ключа:

   ```
   PubkeyAuthentication yes
   ```

1. Перезапустите службу **sshd**.

   ```bash
   sudo launchctl stop com.openssh.sshd
   sudo launchctl start com.openssh.sshd
   ```

## <a name="authentication"></a>Аутентификация

При удаленном взаимодействии с PowerShell через SSH используется обмен данными для проверки подлинности между клиентом SSH и службой SSH. Схемы проверки подлинности в его рамках не реализуются. Это означает, что любые настроенные схемы проверки подлинности, включая многофакторную проверку подлинности, обрабатываются протоколом SSH независимо от PowerShell. Например, в службе SSH можно настроить обязательное применение проверки подлинности на основе открытых ключей, а также разовых паролей для усиления безопасности. Настройка многофакторной проверки подлинности выходит за рамки настоящего документа. Сведения о том, как правильно настроить многофакторную проверку подлинности и проверить ее работу вне PowerShell, прежде чем пытаться использовать ее для удаленного взаимодействия с PowerShell, см. в документации по SSH.

> [!NOTE]
> Пользователи сохраняют те же привилегии в удаленных сеансах. Это означает, что администраторы имеют доступ к оболочке с повышенными правами, а обычные пользователи — нет.

## <a name="powershell-remoting-example"></a>Пример удаленного взаимодействия PowerShell

Проще всего проверить удаленное взаимодействие на одном компьютере. В этом примере мы создадим удаленный сеанс с одним и тем же компьютером Linux. Командлеты PowerShell мы выполняем в интерактивном режиме, поэтому мы увидим запрос от SSH на проверку удаленного компьютера, а также запрос на ввод пароля. Чтобы убедиться, что удаленное взаимодействие работает, те же операции можно выполнить на компьютере Windows. Затем установите удаленное подключение между компьютерами, изменив имя узла.

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

### <a name="limitations"></a>Ограничения

- Команда **sudo** не работает в рамках сеанса удаленного взаимодействия с компьютером Linux.

- PSRemoting через SSH не поддерживает профили и не имеет доступа к `$PROFILE`. После входа в сеанс можно загрузить профиль с помощью вызова с точкой, указав полный путь к профилю. Это не связано с профилями SSH. Вы можете настроить SSH-сервер для использования PowerShell в качестве оболочки по умолчанию и для загрузки профиля через SSH. Дополнительные сведения см. в документации по SSH.

- До PowerShell 7.1 удаленное взаимодействие по SSH не поддерживало удаленные сеансы со вторым прыжком. Эта возможность была ограничена сеансами через WinRM. PowerShell 7.1 позволяет `Enter-PSSession` и `Enter-PSHostProcess` работать в любом интерактивном удаленном сеансе.

## <a name="see-also"></a>См. также раздел

[Установка PowerShell Core в Linux](../../install/installing-powershell-core-on-linux.md#ubuntu-1604)

[Установка PowerShell Core в macOS](../../install/installing-powershell-core-on-macos.md)

[Установка PowerShell Core в Windows](../../install/installing-powershell-core-on-windows.md#msi)

[Управление Windows с помощью OpenSSH](/windows-server/administration/openssh/openssh_overview)

[Управление ключами OpenSSH](/windows-server/administration/openssh/openssh_keymanagement)

[Ubuntu SSH](https://help.ubuntu.com/lts/serverguide/openssh-server.html)
