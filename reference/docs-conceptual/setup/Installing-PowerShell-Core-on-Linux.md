---
title: Установка PowerShell Core в Linux
description: Сведения об установке PowerShell Core в различных дистрибутивах Linux
ms.date: 08/06/2018
ms.openlocfilehash: a20384c768113ed2313591cfa8c29eeadd94f80f
ms.sourcegitcommit: e76665315fd928bf85210778f1fea2be15264fea
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2018
ms.locfileid: "50226004"
---
# <a name="installing-powershell-core-on-linux"></a>Установка PowerShell Core в Linux

Supports [Ubuntu 14.04][u14], [Ubuntu 16.04][u16], [Ubuntu 18.04][u1804], [Ubuntu 18.10][u1810], [Debian 8][deb8], [Debian 9][deb9], [CentOS 7][cos], [Red Hat Enterprise Linux (RHEL) 7][rhel7], [openSUSE 42.3][opensuse], [openSUSE Leap 15][opensuse], [Fedora 27][fedora], [Fedora 28][fedora] и [Arch Linux][arch].

Для дистрибутивов Linux без официальной поддержки попробуйте использовать [snap-пакет PowerShell][snap].
Можно также попытаться развернуть двоичные файлы PowerShell напрямую с помощью [архива`tar.gz`][tar] Linux, но при этом нужно отдельно настроить необходимые зависимости с учетом операционной системы.

Все пакеты доступны на нашей странице [выпусков][] GitHub.
После установки пакета запустите `pwsh` из терминала.

[u14]: #ubuntu-1404
[u16]: #ubuntu-1604
[u1804]: #ubuntu-1804
[u1810]: #ubuntu-1810
[deb8]: #debian-8
[deb9]: #debian-9
[cos]: #centos-7
[rhel7]: #red-hat-enterprise-linux-rhel-7
[opensuse]: #opensuse-423
[fedora]: #fedora
[arch]: #arch-linux
[snap]: #snap-package
[tar]: #binary-archives

## <a name="installing-preview-releases"></a>Установка предварительных выпусков

При установке предварительной версии PowerShell Core для Linux с помощью репозитория пакетов имя пакета меняется с `powershell` на `powershell-preview`.

При установке с помощью прямого скачивания изменяется только имя файла.

Ниже приведена таблица команд для установки пакетов стабильной и предварительной версий с помощью различных диспетчеров пакетов.

|Дистрибутивы|Команда стабильной версии | Команда предварительной версии |
|---------------|---------------|-----------------|
| Ubuntu, Debian |`sudo apt-get install -y powershell`| `sudo apt-get install -y powershell-preview`|
| CentOS, RedHat |`sudo yum install -y powershell` | `sudo yum install -y powershell-preview`|
| Fedora   |`sudo dnf install -y powershell` | `sudo dnf install -y powershell-preview`|

## <a name="ubuntu-1404"></a>Ubuntu 14.04

### <a name="installation-via-package-repository---ubuntu-1404"></a>Установка с помощью репозитория пакетов — Ubuntu 14.04

Для упрощения установки (и обновления) PowerShell Core для Linux публикуются в репозиториях пакетов.
Это предпочтительный метод.

```sh
# Download the Microsoft repository GPG keys
wget -q https://packages.microsoft.com/config/ubuntu/14.04/packages-microsoft-prod.deb

# Register the Microsoft repository GPG keys
sudo dpkg -i packages-microsoft-prod.deb

# Update the list of products
sudo apt-get update

# Install PowerShell
sudo apt-get install -y powershell

# Start PowerShell
pwsh
```

В качестве суперпользователя зарегистрируйте репозиторий Microsoft.
В дальнейшем для обновления установки необходимо просто использовать `sudo apt-get upgrade powershell`.

### <a name="installation-via-direct-download---ubuntu-1404"></a>Установка с помощью прямого скачивания — Ubuntu 14.04

Скачайте пакет Debian `powershell_6.1.0-1.ubuntu.14.04_amd64.deb`
со страницы [выпусков][] на компьютер с Ubuntu.

Затем выполните в терминале следующую команду:

```sh
sudo dpkg -i powershell_6.1.0-1.ubuntu.14.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> Команда `dpkg -i` завершается ошибкой при наличии несопоставленных зависимостей.
> Следующая команда, `apt-get install -f`, разрешает эти ошибки и завершает настройку пакета PowerShell.

### <a name="uninstallation---ubuntu-1404"></a>Удаление — Ubuntu 14.04

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1604"></a>Ubuntu 16.04

### <a name="installation-via-package-repository---ubuntu-1604"></a>Установка с помощью репозитория пакетов — Ubuntu 16.04

Для упрощения установки (и обновления) PowerShell Core для Linux публикуются в репозиториях пакетов.
Это предпочтительный метод.

```sh
# Download the Microsoft repository GPG keys
wget -q https://packages.microsoft.com/config/ubuntu/16.04/packages-microsoft-prod.deb

# Register the Microsoft repository GPG keys
sudo dpkg -i packages-microsoft-prod.deb

# Update the list of products
sudo apt-get update

# Install PowerShell
sudo apt-get install -y powershell

# Start PowerShell
pwsh
```

Зарегистрировав репозиторий Майкрософт в качестве суперпользователя, в дальнейшем вам потребуется лишь использовать `sudo apt-get upgrade powershell` для его обновления.

### <a name="installation-via-direct-download---ubuntu-1604"></a>Установка с помощью прямого скачивания — Ubuntu 16.04

Скачайте пакет Debian `powershell_6.1.0-1.ubuntu.16.04_amd64.deb`
со страницы [выпусков][] на компьютер с Ubuntu.

Затем выполните в терминале следующую команду:

```sh
sudo dpkg -i powershell_6.1.0-1.ubuntu.16.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> Команда `dpkg -i` завершается ошибкой при наличии несопоставленных зависимостей.
> Следующая команда, `apt-get install -f`, разрешает эти ошибки и завершает настройку пакета PowerShell.

### <a name="uninstallation---ubuntu-1604"></a>Удаление — Ubuntu 16.04

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1804"></a>Ubuntu 18.04

> [!NOTE]
> Поддержка Ubuntu 18.04 добавлена после `6.1.0-preview.2`

### <a name="installation-via-package-repository---ubuntu-1804"></a>Установка с помощью репозитория пакетов — Ubuntu 18.04

Для упрощения установки (и обновления) PowerShell Core для Linux публикуются в репозиториях пакетов.
Это предпочтительный метод.

```sh
# Download the Microsoft repository GPG keys
wget -q https://packages.microsoft.com/config/ubuntu/18.04/packages-microsoft-prod.deb

# Register the Microsoft repository GPG keys
sudo dpkg -i packages-microsoft-prod.deb

# Update the list of products
sudo apt-get update

# Install PowerShell
sudo apt-get install -y powershell

# Start PowerShell
pwsh
```

Зарегистрировав репозиторий Майкрософт в качестве суперпользователя, в дальнейшем вам потребуется лишь использовать `sudo apt-get upgrade powershell` для его обновления.

### <a name="installation-via-direct-download---ubuntu-1804"></a>Установка с помощью прямого скачивания — Ubuntu 18.04

Скачайте пакет Debian `powershell_6.1.0-1.ubuntu.18.04_amd64.deb`
со страницы [выпусков][] на компьютер с Ubuntu.

Затем выполните в терминале следующую команду:

```sh
sudo dpkg -i powershell_6.1.0-1.ubuntu.18.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> Команда `dpkg -i` завершается ошибкой при наличии несопоставленных зависимостей.
> Следующая команда, `apt-get install -f`, разрешает эти ошибки и завершает настройку пакета PowerShell.

### <a name="uninstallation---ubuntu-1804"></a>Удаление — Ubuntu 18.04

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1810"></a>Ubuntu 18.10

> [!NOTE]
> Поддержка Ubuntu 18.10 была добавлена после `6.1.0-preview.3`.
> Так как в версии 18.10 используется ежедневная сборка, эта версия поддерживается только сообществом.

Установка версии 18.10 поддерживается с помощью `snapd`. Полные инструкции см. в разделе [Snap-пакет][snap].

## <a name="debian-8"></a>Debian 8

### <a name="installation-via-package-repository---debian-8"></a>Установка с помощью репозитория пакетов — Debian 8

Для упрощения установки (и обновления) PowerShell Core для Linux публикуются в репозиториях пакетов.
Это предпочтительный метод.

```sh
# Install system components
sudo apt-get update
sudo apt-get install curl apt-transport-https

# Import the public repository GPG keys
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -

# Register the Microsoft Product feed
sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-jessie-prod jessie main" > /etc/apt/sources.list.d/microsoft.list'

# Update the list of products
sudo apt-get update

# Install PowerShell
sudo apt-get install -y powershell

# Start PowerShell
pwsh
```

Зарегистрировав репозиторий Майкрософт в качестве суперпользователя, в дальнейшем вам потребуется лишь использовать `sudo apt-get upgrade powershell` для его обновления.

### <a name="installation-via-direct-download---debian-8"></a>Установка с помощью прямого скачивания — Debian 8

Скачайте пакет Debian `powershell_6.1.0-1.debian.8_amd64.deb`
со страницы [выпусков][] на компьютер с Debian.

Затем выполните в терминале следующую команду:

```sh
sudo dpkg -i powershell_6.1.0-1.debian.8_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> Команда `dpkg -i` завершается ошибкой при наличии несопоставленных зависимостей.
> Следующая команда, `apt-get install -f`, разрешает эти ошибки и завершает настройку пакета PowerShell.

### <a name="uninstallation---debian-8"></a>Удаление — Debian 8

```sh
sudo apt-get remove powershell
```

## <a name="debian-9"></a>Debian 9

### <a name="installation-via-package-repository---debian-9"></a>Установка с помощью репозитория пакетов — Debian 9

Для упрощения установки (и обновления) PowerShell Core для Linux публикуются в репозиториях пакетов.
Это предпочтительный метод.

```sh
# Install system components
sudo apt-get update
sudo apt-get install curl gnupg apt-transport-https

# Import the public repository GPG keys
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -

# Register the Microsoft Product feed
sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-stretch-prod stretch main" > /etc/apt/sources.list.d/microsoft.list'

# Update the list of products
sudo apt-get update

# Install PowerShell
sudo apt-get install -y powershell

# Start PowerShell
pwsh
```

Зарегистрировав репозиторий Майкрософт в качестве суперпользователя, в дальнейшем вам потребуется лишь использовать `sudo apt-get upgrade powershell` для его обновления.

### <a name="installation-via-direct-download---debian-9"></a>Установка с помощью прямого скачивания — Debian 9

Скачайте пакет Debian `powershell_6.1.0-1.debian.9_amd64.deb`
со страницы [выпусков][] на компьютер с Debian.

Затем выполните в терминале следующую команду:

```sh
sudo dpkg -i powershell_6.1.0-1.debian.9_amd64.deb
sudo apt-get install -f
```

### <a name="uninstallation---debian-9"></a>Удаление — Debian 9

```sh
sudo apt-get remove powershell
```

## <a name="centos-7"></a>CentOS 7

> [!NOTE]
> Этот пакет также работает в Oracle Linux 7.

### <a name="installation-via-package-repository-preferred---centos-7"></a>Установка с помощью репозитория пакетов (рекомендуется) — CentOS 7

Для упрощения установки (и обновления) PowerShell Core для Linux публикуются в официальных репозиториях Майкрософт.

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

Зарегистрировав репозиторий Майкрософт в качестве суперпользователя, в дальнейшем вам потребуется лишь использовать `sudo yum update powershell` для обновления PowerShell.

### <a name="installation-via-direct-download---centos-7"></a>Установка с помощью прямого скачивания — CentOS 7

С помощью [CentOS 7][] скачайте пакет RPM `powershell-6.1.0-1.rhel.7.x86_64.rpm`
со страницы [выпусков][] на компьютер с CentOS.

Затем выполните в терминале следующую команду:

```sh
sudo yum install powershell-6.1.0-1.rhel.7.x86_64.rpm
```

Кроме того, RPM можно установить без промежуточного скачивания:

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v6.1.0/powershell-6.1.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---centos-7"></a>Удаление — CentOS 7

```sh
sudo yum remove powershell
```

[CentOS 7]: https://www.centos.org/download/

## <a name="red-hat-enterprise-linux-rhel-7"></a>Red Hat Enterprise Linux (RHEL) 7

### <a name="installation-via-package-repository-preferred---red-hat-enterprise-linux-rhel-7"></a>Установка с помощью репозитория пакетов (рекомендуется) — Red Hat Enterprise Linux (RHEL) 7

Для упрощения установки (и обновления) PowerShell Core для Linux публикуются в официальных репозиториях Майкрософт.

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

Зарегистрировав репозиторий Майкрософт в качестве суперпользователя, в дальнейшем вам потребуется лишь использовать `sudo yum update powershell` для обновления PowerShell.

### <a name="installation-via-direct-download---red-hat-enterprise-linux-rhel-7"></a>Установка с помощью прямого скачивания — Red Hat Enterprise Linux (RHEL) 7

Скачайте пакет RPM `powershell-6.1.0-1.rhel.7.x86_64.rpm`
со страницы [выпусков][] на компьютер с Red Hat Enterprise Linux.

Затем выполните в терминале следующую команду:

```sh
sudo yum install powershell-6.1.0-1.rhel.7.x86_64.rpm
```

Кроме того, RPM можно установить без промежуточного скачивания:

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v6.1.0/powershell-6.1.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---red-hat-enterprise-linux-rhel-7"></a>Удаление — Red Hat Enterprise Linux (RHEL) 7

```sh
sudo yum remove powershell
```

## <a name="opensuse"></a>openSUSE

### <a name="installation---opensuse-423"></a>Установка — openSUSE 42.3

```sh
# Install dependencies
zypper update && zypper --non-interactive install curl tar libicu52_1

# Download the powershell '.tar.gz' archive
curl -L https://github.com/PowerShell/PowerShell/releases/download/v6.1.0/powershell-6.1.0-linux-x64.tar.gz -o /tmp/powershell.tar.gz

# Create the target folder where powershell will be placed
mkdir -p /opt/microsoft/powershell/6.1.0

# Expand powershell to the target folder
tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/6.1.0

# Set execute permissions
chmod +x /opt/microsoft/powershell/6.1.0/pwsh

# Create the symbolic link that points to pwsh
ln -s /opt/microsoft/powershell/6.1.0/pwsh /usr/bin/pwsh

# Start PowerShell
pwsh
```

### <a name="installation---opensuse-leap-15"></a>Установка — openSUSE Leap 15

```sh
# Install dependencies
zypper update && zypper --non-interactive install curl tar gzip libopenssl1_0_0 libicu60_2

# Download the powershell '.tar.gz' archive
curl -L https://github.com/PowerShell/PowerShell/releases/download/v6.1.0/powershell-6.1.0-linux-x64.tar.gz -o /tmp/powershell.tar.gz

# Create the target folder where powershell will be placed
mkdir -p /opt/microsoft/powershell/6.1.0

# Expand powershell to the target folder
tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/6.1.0

# Set execute permissions
chmod +x /opt/microsoft/powershell/6.1.0/pwsh

# Create the symbolic link that points to pwsh
ln -s /opt/microsoft/powershell/6.1.0/pwsh /usr/bin/pwsh

# Start PowerShell
pwsh
```

### <a name="uninstallation---opensuse-423-opensuse-leap-15"></a>Удаление — openSUSE 42.3, openSUSE Leap 15

```sh
rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="fedora"></a>Fedora

> [!NOTE]
> Fedora 28 поддерживается только в PowerShell Core 6.1 и более поздних версий.

### <a name="installation-via-package-repository-preferred---fedora-27-fedora-28"></a>Установка с помощью репозитория пакетов (рекомендуется) — Fedora 27, Fedora 28

Для упрощения установки (и обновления) PowerShell Core для Linux публикуются в официальных репозиториях Майкрософт.

```sh
# Register the Microsoft signature key
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc

# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Update the list of products
sudo dnf update

# Install a system component
sudo dnf install compat-openssl10

# Install PowerShell
sudo dnf install -y powershell

# Start PowerShell
pwsh
```

### <a name="installation-via-direct-download---fedora-27-fedora-28"></a>Установка с помощью прямого скачивания — Fedora 27, Fedora 28

Скачайте пакет RPM `powershell-6.1.0-1.rhel.7.x86_64.rpm`
со страницы [выпусков][] на компьютер с Fedora.

Затем выполните в терминале следующую команду:

```sh
sudo dnf install compat-openssl10
sudo dnf install powershell-6.1.0-1.rhel.7.x86_64.rpm
```

Кроме того, RPM можно установить без промежуточного скачивания:

```sh
sudo dnf install compat-openssl10
sudo dnf install https://github.com/PowerShell/PowerShell/releases/download/v6.1.0/powershell-6.1.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---fedora-27-fedora-28"></a>Удаление — Fedora 27, Fedora 28

```sh
sudo dnf remove powershell
```

## <a name="arch-linux"></a>Arch Linux

> [!NOTE]
> Поддержка Arch на этапе эксперимента.

PowerShell можно получить из пользовательского репозитория [Arch Linux][] (AUR).

* Его можно скомпилировать с помощью [последнего выпуска с тегами][arch-release].
* Его можно скомпилировать из [последней фиксации в основной репозиторий][arch-git].
* Его можно установить с помощью [двоичного файла последнего выпуска][arch-bin].

Пакеты в AUR обслуживаются сообществом — официальная поддержка отсутствует.

Дополнительные сведения об установке пакетов из AUR см. на [вики-сайте Arch Linux](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) или в [DockerFile](https://github.com/PowerShell/PowerShell/blob/master/docker/community/archlinux/Dockerfile) сообщества.

[Arch Linux]: https://www.archlinux.org/download/
[arch-release]: https://aur.archlinux.org/packages/powershell/
[arch-git]: https://aur.archlinux.org/packages/powershell-git/
[arch-bin]: https://aur.archlinux.org/packages/powershell-bin/

## <a name="snap-package"></a>Snap-пакет

### <a name="getting-snapd"></a>Установка Snap

Утилита `snapd` необходима для запуска snap-пакетов.
Чтобы убедиться, что утилита `snapd` установлена, воспользуйтесь [этими инструкциями](https://docs.snapcraft.io/core/install).

### <a name="installation-via-snap"></a>Установка с использованием Snap

Для упрощения установки (и обновления) PowerShell Core для Linux опубликован в [хранилище Snap](https://snapcraft.io/store).
Это предпочтительный метод.

```sh
# Install PowerShell
sudo snap install powershell --classic

# Start PowerShell
pwsh
```

Если вы хотите установить предварительную версию, используйте следующий метод.

```sh
# Install PowerShell
sudo snap install powershell-preview --classic

# Start PowerShell
pwsh-preview
```

После установки Snap будет автоматически обновлен, но вы можете активировать обновление с помощью `sudo snap refresh powershell` или `sudo snap refresh powershell-preview`.

### <a name="uninstallation"></a>Удаление

```sh
sudo snap remove powershell
```

или

```sh
sudo snap remove powershell-preview
```

## <a name="kali"></a>Kali

### <a name="installation---kali"></a>Установка — Kali

```sh
# Download & Install prerequisites
wget http://ftp.us.debian.org/debian/pool/main/i/icu/libicu57_57.1-9_amd64.deb
dpkg -i libicu57_57.1-9_amd64.deb
apt-get update && apt-get install -y curl gnupg apt-transport-https

# Add Microsoft public repository key to APT
curl https://packages.microsoft.com/keys/microsoft.asc | apt-key add -

# Add Microsoft package repository to the source list
echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-stretch-prod stretch main" | tee /etc/apt/sources.list.d/powershell.list

# Install PowerShell package
apt-get update && apt-get install -y powershell

# Start PowerShell
pwsh
```

### <a name="uninstallation---kali"></a>Удаление — Kali

```sh
# Uninstall PowerShell package
apt-get remove -y powershell
```

## <a name="raspbian"></a>Raspbian

> [!NOTE]
> Поддержка Raspbian на этапе эксперимента.

Сейчас PowerShell поддерживается только в Raspbian Stretch.

Кроме того, CoreCLR (а соответственно и PowerShell Core) будет работать только на устройствах Pi 2 и Pi 3, в то время как в устройствах наподобие [Pi Zero](https://github.com/dotnet/coreclr/issues/10605) установлены процессоры, поддержка которых не предусмотрена.

Загрузите [Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) и следуйте [инструкциям по установке](https://www.raspberrypi.org/documentation/installation/installing-images/README.md), чтобы установить его на свой Pi.

### <a name="installation---raspbian"></a>Установка — Raspbian

```sh
# Install prerequisites
sudo apt-get install libunwind8

# Grab the latest tar.gz
wget https://github.com/PowerShell/PowerShell/releases/download/v6.1.0/powershell-6.1.0-linux-arm32.tar.gz

# Make folder to put powershell
mkdir ~/powershell

# Unpack the tar.gz file
tar -xvf ./powershell-6.1.0-linux-arm32.tar.gz -C ~/powershell

# Start PowerShell
~/powershell/pwsh
```

При необходимости можно создать символьную ссылку, позволяющую запустить PowerShell без указания пути к двоичному файлу pwsh

```sh
# Start PowerShell from bash with sudo to create a symbolic link
sudo ~/powershell/pwsh -c New-Item -ItemType SymbolicLink -Path "/usr/bin/pwsh" -Target "\$PSHOME/pwsh" -Force

# alternatively you can run following to create a symbolic link
# sudo ln -s ~/powershell/pwsh /usr/bin/pwsh

# Now to start PowerShell you can just run "pwsh"
```

### <a name="uninstallation---raspbian"></a>Удаление — Raspbian

```sh
rm -rf ~/powershell
```

## <a name="binary-archives"></a>Архивы двоичных файлов

Для поддержки расширенных сценариев развертывания на платформах Linux доступны архивы `tar.gz` двоичных файлов PowerShell.

### <a name="dependencies"></a>Зависимости

PowerShell создает переносимые двоичные файлы для всех дистрибутивов Linux.
Однако среда выполнения .NET Core требует различные зависимости для разных дистрибутивов, и поэтому то же самое делает и PowerShell.

На следующей диаграмме показаны официально поддерживаемые зависимости .NET Core 2.0 для различных дистрибутивов Linux.

| ОС                 | Зависимости |
| ------------------ | ------------ |
| Ubuntu 14.04       | libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6, <br> libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52 |
| Ubuntu 16.04       | libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6, <br> libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu55 |
| Ubuntu 17.10       | libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6, <br> libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu57 |
| Ubuntu 18.04       | libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6, <br> libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu60 |
| Debian 8 (Jessie)  | libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6, <br> libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52 |
| Debian 9 (Stretch) | libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6, <br> libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.2, libicu57 |
| CentOS 7 <br> Oracle Linux 7 <br> RHEL 7 | libunwind, libcurl, openssl-libs, libicu |
| openSUSE 42.3 | libcurl4, libopenssl1_0_0, libicu52_1 |
| openSUSE Leap 15 | libcurl4, libopenssl1_0_0, libicu60_2 |
| Fedora 27 <br> Fedora 28 | libunwind, libcurl, openssl-libs, libicu, compat-openssl10 |

Чтобы развернуть двоичные файлы PowerShell в дистрибутивах Linux, для которых официальная поддержка не предусмотрена, необходимо специально установить необходимые пакеты, чтобы удовлетворить всем требованиям по зависимостям для целевой ОС.
Например, наш [Amazon Linux dockerfile][amazon-dockerfile] сначала устанавливает зависимости, а затем извлекает архив Linux `tar.gz`.

[amazon-dockerfile]: https://github.com/PowerShell/PowerShell/blob/master/docker/community/amazonlinux/Dockerfile

### <a name="installation---binary-archives"></a>Установка — архивы двоичных файлов

#### <a name="linux"></a>Linux

```sh
# Download the powershell '.tar.gz' archive
curl -L -o /tmp/powershell.tar.gz https://github.com/PowerShell/PowerShell/releases/download/v6.1.0/powershell-6.1.0-linux-x64.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /opt/microsoft/powershell/6.1.0

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/6.1.0

# Set execute permissions
sudo chmod +x /opt/microsoft/powershell/6.1.0/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /opt/microsoft/powershell/6.1.0/pwsh /usr/bin/pwsh
```

### <a name="uninstalling-binary-archives"></a>Удаление архивов двоичных файлов

```sh
sudo rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="paths"></a>Пути

* `$PSHOME` имеет значение `/opt/microsoft/powershell/6.1.0/`.
* Профили пользователей будут считаны из `~/.config/powershell/profile.ps1`.
* Профили по умолчанию будут считаны из `$PSHOME/profile.ps1`.
* Модули пользователей будут считаны из `~/.local/share/powershell/Modules`.
* Общие модули будут считаны из `/usr/local/share/powershell/Modules`.
* Модули по умолчанию будут считаны из `$PSHOME/Modules`.
* Журнал PSReadline будет записан в `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`.

Профили учитывают конфигурацию PowerShell для отдельных узлов, поэтому профили конкретных узлов по умолчанию находятся в `Microsoft.PowerShell_profile.ps1` в тех же расположениях.

PowerShell отвечает требованиям [спецификации каталога размещения файлов, связанных со средой настольной графической среды (X-сервера), стандартизированного XDG (X Desktop Group)][xdg-bds] в Linux.

[выпусков]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
