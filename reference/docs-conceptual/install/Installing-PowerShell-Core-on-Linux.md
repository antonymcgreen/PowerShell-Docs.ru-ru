---
title: Установка PowerShell в Linux
description: Сведения об установке PowerShell в различных дистрибутивах Linux
ms.date: 02/02/2021
ms.openlocfilehash: 1e7fabdc94ba70a91eb5c6425893bc5af640e584
ms.sourcegitcommit: 4f1c2fe700b8a0544c59e371eb7cfbc6d852b185
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/17/2021
ms.locfileid: "100563303"
---
# <a name="installing-powershell-on-linux"></a>Установка PowerShell в Linux

Все пакеты доступны на нашей странице [выпусками][] GitHub. После установки пакета запустите `pwsh` из терминала. Запустите `pwsh-preview`, если вы установили [выпуск предварительной версии](#installing-preview-releases).

> [!NOTE]
> PowerShell 7 является обновлением на месте, при установке которого PowerShell Core 6.x удаляется.
>
> Папка `/usr/local/microsoft/powershell/6` заменяется на `/usr/local/microsoft/powershell/7`.
>
> Если вы хотите запускать PowerShell 6 параллельно с PowerShell 7, переустановите PowerShell 6 с использованием [двоичного архива](#binary-archives).

Для дистрибутивов Linux без официальной поддержки попробуйте установить PowerShell с помощью [соответствующего Snap-пакета][snap]. Можно также попытаться развернуть двоичные файлы PowerShell напрямую с помощью [архива`tar.gz`][tar] Linux, но при этом нужно отдельно настроить необходимые зависимости с учетом операционной системы.

[snap]: #snap-package
[tar]: #binary-archives

<!-- TODO: Update for supported releases v7.0 & v7.1 -->

Официально поддерживаемые выпуски платформы для PowerShell 7.1:

- Ubuntu 16.04, 18.04 и 20.04 (включая ARM64);
- Ubuntu 19.10 (через snap-пакет);
- Debian 9 и 10;
- CentOS и RHEL 7 и 8;
- Fedora 30
- Alpine 3.11 и более поздних версий (включая ARM64).

Официально поддерживаемые выпуски платформы для PowerShell 7.0:

- Ubuntu 16.04
- Ubuntu 18.04 и 20.04;
- Debian 8
- Debian 9
- Debian 10
- Alpine 3.9 и 3.10
- CentOS 7
- Red Hat Enterprise Linux (RHEL) 7
- Fedora 28
- Fedora 29
- Fedora 30
- openSUSE 42.3
- openSUSE Leap 15

Выпуски, поддерживаемые сообществом:

- Ubuntu 18.10
- Ubuntu 19.10 и 20.10;
- Arch Linux
- Kali
- Raspbian (экспериментальная версия)

Альтернативные методы установки

- Snap-пакет
- Архивы двоичных файлов
- Глобальный инструмент .NET

## <a name="ubuntu-1604"></a>Ubuntu 16.04

### <a name="installation-via-package-repository---ubuntu-1604"></a>Установка с помощью репозитория пакетов — Ubuntu 16.04

Чтобы упростить установку и обновление, PowerShell для Linux публикуется в репозиториях пакетов.

Предпочтительный метод выглядит следующим образом:

```sh
# Update the list of packages
sudo apt-get update
# Install pre-requisite packages.
sudo apt-get install -y wget apt-transport-https software-properties-common
# Download the Microsoft repository GPG keys
wget -q https://packages.microsoft.com/config/ubuntu/16.04/packages-microsoft-prod.deb
# Register the Microsoft repository GPG keys
sudo dpkg -i packages-microsoft-prod.deb
# Update the list of packages after we added packages.microsoft.com
sudo apt-get update
# Install PowerShell
sudo apt-get install -y powershell
# Start PowerShell
pwsh
```

В качестве суперпользователя однократно зарегистрируйте репозиторий Майкрософт. После регистрации можно обновить PowerShell с помощью `sudo apt-get install powershell`.

### <a name="installation-via-direct-download---ubuntu-1604"></a>Установка с помощью прямого скачивания — Ubuntu 16.04

Скачайте пакет Debian `powershell_7.1.2-1.ubuntu.16.04_amd64.deb` со страницы [выпусками][] на компьютер с Ubuntu.

Затем выполните в терминале следующие команды:

```sh
sudo dpkg -i powershell_7.1.2-1.ubuntu.16.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> Команда `dpkg -i` завершается ошибкой при наличии несопоставленных зависимостей. Следующая команда, `apt-get install -f`, разрешает эти ошибки и завершает настройку пакета PowerShell.

### <a name="uninstallation---ubuntu-1604"></a>Удаление — Ubuntu 16.04

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1804"></a>Ubuntu 18.04

### <a name="installation-via-package-repository---ubuntu-1804"></a>Установка с помощью репозитория пакетов — Ubuntu 18.04

Чтобы упростить установку и обновление, PowerShell для Linux публикуется в репозиториях пакетов.

Предпочтительный метод выглядит следующим образом:

```sh
# Update the list of packages
sudo apt-get update
# Install pre-requisite packages.
sudo apt-get install -y wget apt-transport-https software-properties-common
# Download the Microsoft repository GPG keys
wget -q https://packages.microsoft.com/config/ubuntu/18.04/packages-microsoft-prod.deb
# Register the Microsoft repository GPG keys
sudo dpkg -i packages-microsoft-prod.deb
# Update the list of products
sudo apt-get update
# Enable the "universe" repositories
sudo add-apt-repository universe
# Install PowerShell
sudo apt-get install -y powershell
# Start PowerShell
pwsh
```

В качестве суперпользователя однократно зарегистрируйте репозиторий Майкрософт. После регистрации можно обновить PowerShell с помощью `sudo apt-get install powershell`.

### <a name="installation-via-direct-download---ubuntu-1804"></a>Установка с помощью прямого скачивания — Ubuntu 18.04

Скачайте пакет Debian `powershell_7.1.2-1.ubuntu.18.04_amd64.deb` со страницы [выпусками][] на компьютер с Ubuntu.

Затем выполните в терминале следующие команды:

```sh
sudo dpkg -i powershell_7.1.2-1.ubuntu.18.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> Команда `dpkg -i` завершается ошибкой при наличии несопоставленных зависимостей. Следующая команда, `apt-get install -f`, разрешает эти ошибки и завершает настройку пакета PowerShell.

### <a name="uninstallation---ubuntu-1804"></a>Удаление — Ubuntu 18.04

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-2004"></a>Ubuntu 20.04

### <a name="installation-via-package-repository---ubuntu-2004"></a>Установка с помощью репозитория пакетов — Ubuntu 20.04

Чтобы упростить установку и обновление, PowerShell для Linux публикуется в репозиториях пакетов.

Предпочтительный метод выглядит следующим образом:

```sh
# Update the list of packages
sudo apt-get update
# Install pre-requisite packages.
sudo apt-get install -y wget apt-transport-https software-properties-common
# Download the Microsoft repository GPG keys
wget -q https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb
# Register the Microsoft repository GPG keys
sudo dpkg -i packages-microsoft-prod.deb
# Update the list of products
sudo apt-get update
# Enable the "universe" repositories
sudo add-apt-repository universe
# Install PowerShell
sudo apt-get install -y powershell
# Start PowerShell
pwsh
```

В качестве суперпользователя однократно зарегистрируйте репозиторий Майкрософт. После регистрации можно обновить PowerShell с помощью `sudo apt-get install powershell`.

### <a name="installation-via-direct-download---ubuntu-2004"></a>Установка с помощью прямого скачивания — Ubuntu 20.04

Скачайте пакет Debian `powershell_7.1.2-1.ubuntu.20.04_amd64.deb` со страницы [выпусками][] на компьютер с Ubuntu.

Затем выполните в терминале следующие команды:

```sh
sudo dpkg -i powershell_7.1.2-1.ubuntu.20.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> Команда `dpkg -i` завершается ошибкой при наличии несопоставленных зависимостей. Следующая команда, `apt-get install -f`, разрешает эти ошибки и завершает настройку пакета PowerShell.

### <a name="uninstallation---ubuntu-2004"></a>Удаление — Ubuntu 20.04

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1810"></a>Ubuntu 18.10

Поддерживается только установка с помощью `snapd`. Инструкции см. в разделе о [snap-пакете][snap].

> [!NOTE]
> Ubuntu 18.10 — [промежуточный выпуск](https://www.ubuntu.com/about/release-cycle), который [поддерживается сообществом](../powershell-support-lifecycle.md).

## <a name="ubuntu-1910-and-2010"></a>Ubuntu 19.10 и 20.10;

Поддерживается только установка с помощью `snapd`. Инструкции см. в разделе о [snap-пакете][snap].

> [!NOTE]
> Ubuntu 19.10 — [промежуточный выпуск](https://www.ubuntu.com/about/release-cycle), который [поддерживается сообществом](../powershell-support-lifecycle.md).

## <a name="debian-8"></a>Debian 8

### <a name="installation-via-package-repository---debian-8"></a>Установка с помощью репозитория пакетов — Debian 8

Чтобы упростить установку и обновление, PowerShell для Linux публикуется в репозиториях пакетов.

Предпочтительный метод выглядит следующим образом:

```sh
# Install system components
sudo apt-get update
sudo apt-get install -y curl apt-transport-https

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

В качестве суперпользователя однократно зарегистрируйте репозиторий Майкрософт. После регистрации можно обновить PowerShell с помощью `sudo apt-get install powershell`.

## <a name="debian-9"></a>Debian 9

### <a name="installation-via-package-repository---debian-9"></a>Установка с помощью репозитория пакетов — Debian 9

Чтобы упростить установку и обновление, PowerShell для Linux публикуется в репозиториях пакетов.

Предпочтительный метод выглядит следующим образом:

```sh
# Install system components
sudo apt-get update
sudo apt-get install -y curl gnupg apt-transport-https

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

В качестве суперпользователя однократно зарегистрируйте репозиторий Майкрософт. После регистрации можно обновить PowerShell с помощью `sudo apt-get install powershell`.

### <a name="installation-via-direct-download---debian-9"></a>Установка с помощью прямого скачивания — Debian 9

Скачайте пакет Debian `powershell_7.1.2-1.debian.9_amd64.deb` со страницы [выпусками][] на компьютер с Debian.

Затем выполните в терминале следующие команды:

```sh
sudo dpkg -i powershell_7.1.2-1.debian.9_amd64.deb
sudo apt-get install -f
```

### <a name="uninstallation---debian-9"></a>Удаление — Debian 9

```sh
sudo apt-get remove powershell
```

## <a name="debian-10"></a>Debian 10

> [!NOTE]
> Debian 10 поддерживается только в PowerShell 7.0 и более поздних версий.

### <a name="installation-via-package-repository---debian-10"></a>Установка с помощью репозитория пакетов — Debian 10

Чтобы упростить установку и обновление, PowerShell для Linux публикуется в репозиториях пакетов.

Предпочтительный метод выглядит следующим образом:

```sh
# Download the Microsoft repository GPG keys
wget https://packages.microsoft.com/config/debian/10/packages-microsoft-prod.deb

# Register the Microsoft repository GPG keys
sudo dpkg -i packages-microsoft-prod.deb

# Update the list of products
sudo apt-get update

# Install PowerShell
sudo apt-get install -y powershell

# Start PowerShell
pwsh
```

### <a name="installation-via-direct-download---debian-10"></a>Установка с помощью прямого скачивания — Debian 10

Скачайте пакет tar.gz `powershell-7.1.2-linux-x64.tar.gz` на странице с [выпусками][] на компьютер с Debian.

Затем выполните в терминале следующие команды:

```sh
sudo apt-get update
# install the requirements
sudo apt-get install -y \
        less \
        locales \
        ca-certificates \
        libicu63 \
        libssl1.1 \
        libc6 \
        libgcc1 \
        libgssapi-krb5-2 \
        liblttng-ust0 \
        libstdc++6 \
        zlib1g \
        curl

# Download the powershell '.tar.gz' archive
curl -L  https://github.com/PowerShell/PowerShell/releases/download/v7.1.2/powershell-7.1.2-linux-x64.tar.gz -o /tmp/powershell.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /opt/microsoft/powershell/7

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/7

# Set execute permissions
sudo chmod +x /opt/microsoft/powershell/7/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /opt/microsoft/powershell/7/pwsh /usr/bin/pwsh

# Start PowerShell
pwsh
```

## <a name="alpine-39-and-310"></a>Alpine 3.9 и 3.10

> [!NOTE]
> Alpine 3.9 и 3.10 поддерживается только в PowerShell 7.0 и более поздних версий.

### <a name="installation-via-direct-download---alpine-39-and-310"></a>Установка с помощью прямого скачивания — Alpine 3.9 и 3.10

Скачайте пакет tar.gz `powershell-7.1.2-linux-alpine-x64.tar.gz` на странице с [выпусками][] на компьютер с Alpine.

Затем выполните в терминале следующие команды:

```sh
# install the requirements
sudo apk add --no-cache \
    ca-certificates \
    less \
    ncurses-terminfo-base \
    krb5-libs \
    libgcc \
    libintl \
    libssl1.1 \
    libstdc++ \
    tzdata \
    userspace-rcu \
    zlib \
    icu-libs \
    curl

sudo apk -X https://dl-cdn.alpinelinux.org/alpine/edge/main add --no-cache \
    lttng-ust

# Download the powershell '.tar.gz' archive
curl -L https://github.com/PowerShell/PowerShell/releases/download/v7.1.2/powershell-7.1.2-linux-alpine-x64.tar.gz -o /tmp/powershell.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /opt/microsoft/powershell/7

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/7

# Set execute permissions
sudo chmod +x /opt/microsoft/powershell/7/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /opt/microsoft/powershell/7/pwsh /usr/bin/pwsh

# Start PowerShell
pwsh
```

## <a name="centos-7"></a>CentOS 7

> [!NOTE]
> Этот пакет работает в Oracle Linux 7.

### <a name="installation-via-package-repository-preferred---centos-7"></a>Установка с помощью репозитория пакетов (рекомендуется) — CentOS 7

Чтобы упростить установку и обновление, PowerShell для Linux публикуется в официальных репозиториях Майкрософт.

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

В качестве суперпользователя однократно зарегистрируйте репозиторий Майкрософт. После регистрации можно обновить PowerShell с помощью `sudo yum update powershell`.

### <a name="installation-via-direct-download---centos-7"></a>Установка с помощью прямого скачивания — CentOS 7

Используя [CentOS 7][], скачайте пакет RPM `powershell-7.1.2-1.rhel.7.x86_64.rpm` со страницы [выпусками][] на компьютер с CentOS.

Затем выполните в терминале следующие команды:

```sh
sudo yum install powershell-7.1.2-1.rhel.7.x86_64.rpm
```

RPM можно установить без промежуточного скачивания:

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v7.1.2/powershell-7.1.2-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---centos-7"></a>Удаление — CentOS 7

```sh
sudo yum remove powershell
```

[CentOS 7]: https://www.centos.org/download/

## <a name="red-hat-enterprise-linux-rhel-7"></a>Red Hat Enterprise Linux (RHEL) 7

### <a name="installation-via-package-repository-preferred---red-hat-enterprise-linux-rhel-7"></a>Установка с помощью репозитория пакетов (рекомендуется) — Red Hat Enterprise Linux (RHEL) 7

Чтобы упростить установку и обновление, PowerShell для Linux публикуется в официальных репозиториях Майкрософт.

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

В качестве суперпользователя однократно зарегистрируйте репозиторий Майкрософт. После регистрации можно обновить PowerShell с помощью `sudo yum update powershell`.

### <a name="installation-via-direct-download---red-hat-enterprise-linux-rhel-7"></a>Установка с помощью прямого скачивания — Red Hat Enterprise Linux (RHEL) 7

Скачайте пакет RPM `powershell-7.1.2-1.rhel.7.x86_64.rpm` со страницы [выпусками][] на компьютер с Red Hat Enterprise Linux.

Затем выполните в терминале следующие команды:

```sh
sudo yum install powershell-7.1.2-1.rhel.7.x86_64.rpm
```

RPM можно установить без промежуточного скачивания:

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v7.1.2/powershell-7.1.2-1.rhel.7.x86_64.rpm
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
curl -L https://github.com/PowerShell/PowerShell/releases/download/v7.1.2/powershell-7.1.2-linux-x64.tar.gz -o /tmp/powershell.tar.gz

# Create the target folder where powershell will be placed
mkdir -p /opt/microsoft/powershell/7

# Expand powershell to the target folder
tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/7

# Set execute permissions
chmod +x /opt/microsoft/powershell/7/pwsh

# Create the symbolic link that points to pwsh
ln -s /opt/microsoft/powershell/7/pwsh /usr/bin/pwsh

# Start PowerShell
pwsh
```

### <a name="installation---opensuse-leap-15"></a>Установка — openSUSE Leap 15

```sh
# Install dependencies
zypper update && zypper --non-interactive install curl tar gzip libopenssl1_0_0 libicu60_2

# Download the powershell '.tar.gz' archive
curl -L https://github.com/PowerShell/PowerShell/releases/download/v7.1.2/powershell-7.1.2-linux-x64.tar.gz -o /tmp/powershell.tar.gz

# Create the target folder where powershell will be placed
mkdir -p /opt/microsoft/powershell/7

# Expand powershell to the target folder
tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/7

# Set execute permissions
chmod +x /opt/microsoft/powershell/7/pwsh

# Create the symbolic link that points to pwsh
ln -s /opt/microsoft/powershell/7/pwsh /usr/bin/pwsh

# Start PowerShell
pwsh
```

### <a name="uninstallation---opensuse-423-opensuse-leap-15"></a>Удаление — openSUSE 42.3, openSUSE Leap 15

```sh
rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="fedora"></a>Fedora

> [!NOTE]
> Fedora 28 поддерживается только в PowerShell 6.1 и более поздних версий.

> [!NOTE]
> Fedora 29 и 30 поддерживается только в PowerShell 7.0 и более поздних версий.

### <a name="installation-via-package-repository-preferred---fedora-28-29-and-30"></a>Установка с помощью репозитория пакетов (рекомендуется) — Fedora 28, 29 и 30

Чтобы упростить установку и обновление, PowerShell для Linux публикуется в официальных репозиториях Майкрософт.

```sh
# Register the Microsoft signature key
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc

# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Update the list of products
sudo dnf check-update

# Install a system component
sudo dnf install compat-openssl10

# Install PowerShell
sudo dnf install -y powershell

# Start PowerShell
pwsh
```

### <a name="installation-via-direct-download---fedora-28-29-and-30"></a>Установка с помощью прямого скачивания — Fedora 28, 29 и 30

Скачайте пакет RPM `powershell-7.1.2-1.rhel.7.x86_64.rpm` со страницы [выпусками][] на компьютер с Fedora.

Затем выполните в терминале следующие команды:

```sh
sudo dnf install compat-openssl10
sudo dnf install powershell-7.1.2-1.rhel.7.x86_64.rpm
```

RPM можно установить без промежуточного скачивания:

```sh
sudo dnf install compat-openssl10
sudo dnf install https://github.com/PowerShell/PowerShell/releases/download/v7.1.2/powershell-7.1.2-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---fedora-28-29-and-30"></a>Удаление — Fedora 28, 29 и 30

```sh
sudo dnf remove powershell
```

## <a name="arch-linux"></a>Arch Linux

> [!NOTE]
> Arch официально не поддерживается корпорацией Майкрософт, но поддерживается сообществом.

PowerShell можно получить из пользовательского репозитория [Arch Linux][] (AUR).

- Его можно скомпилировать с помощью [последнего выпуска с тегами][arch-release].
- Его можно скомпилировать из [последней фиксации в основной репозиторий][arch-git].
- Его можно установить с помощью [двоичного файла последнего выпуска][arch-bin].

Пакеты в AUR обслуживаются сообществом — официальная поддержка не предусмотрена.

Дополнительные сведения об установке пакетов из AUR см. на [вики-сайте Arch Linux](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) или в статье [Использование PowerShell в Docker](powershell-in-docker.md).

[Arch Linux]: https://www.archlinux.org/download/
[arch-release]: https://aur.archlinux.org/packages/powershell/
[arch-git]: https://aur.archlinux.org/packages/powershell-git/
[arch-bin]: https://aur.archlinux.org/packages/powershell-bin/

## <a name="snap-package"></a>Snap-пакет

### <a name="getting-snapd"></a>Установка Snap

Утилита `snapd` необходима для запуска snap-пакетов. Чтобы убедиться, что утилита `snapd` установлена, воспользуйтесь [этими инструкциями](https://docs.snapcraft.io/core/install).

### <a name="installation-via-snap"></a>Установка с использованием Snap

Чтобы упростить установку и обновление, PowerShell для Linux публикуется в [хранилище Snap](https://snapcraft.io/store).

Предпочтительный метод выглядит следующим образом:

```sh
# Install PowerShell
sudo snap install powershell --classic

# Start PowerShell
pwsh
```

Чтобы установить предварительную версию, используйте следующий метод:

```sh
# Install PowerShell
sudo snap install powershell-preview --classic

# Start PowerShell
pwsh-preview
```

После установки Snap автоматически обновится. Обновление можно активировать с помощью `sudo snap refresh powershell` или `sudo snap refresh powershell-preview`.

### <a name="uninstallation"></a>Удаление

```sh
sudo snap remove powershell
```

или диспетчер конфигурации служб

```sh
sudo snap remove powershell-preview
```

## <a name="kali"></a>Kali

> [!NOTE]
> Kali официально не поддерживается корпорацией Майкрософт, но поддерживается сообществом.

### <a name="installation---kali"></a>Установка — Kali

```sh
# Install PowerShell package
apt update && apt -y install powershell

# Start PowerShell
pwsh
```

### <a name="uninstallation---kali"></a>Удаление — Kali

```sh
# Uninstall PowerShell package
apt -y remove powershell
```

## <a name="raspbian"></a>Raspbian

> [!NOTE]
> Поддержка Raspbian на этапе эксперимента.

Сейчас PowerShell поддерживается только в Raspbian Stretch.

CoreCLR и PowerShell будут работать только на устройствах Pi 2 и Pi 3. На таких устройствах, как [Pi Zero](https://github.com/dotnet/coreclr/issues/10605), установлены процессоры, поддержка которых не предусмотрена.

Загрузите [Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) и следуйте [инструкциям по установке](https://www.raspberrypi.org/documentation/installation/installing-images/README.md), чтобы установить его на свой Pi.

### <a name="installation---raspbian"></a>Установка — Raspbian

```sh
###################################
# Prerequisites

# Update package lists
sudo apt-get update

# Install libunwind8 and libssl1.0
# Regex is used to ensure that we do not install libssl1.0-dev, as it is a variant that is not required
sudo apt-get install '^libssl1.0.[0-9]$' libunwind8 -y

###################################
# Download and extract PowerShell

# Grab the latest tar.gz
wget https://github.com/PowerShell/PowerShell/releases/download/v7.1.2/powershell-7.1.2-linux-arm32.tar.gz

# Make folder to put powershell
mkdir ~/powershell

# Unpack the tar.gz file
tar -xvf ./powershell-7.1.2-linux-arm32.tar.gz -C ~/powershell

# Start PowerShell
~/powershell/pwsh
```

При необходимости можно создать символьную ссылку для запуска PowerShell без указания пути к двоичному файлу `pwsh`.

```sh
# Start PowerShell from bash with sudo to create a symbolic link
sudo ~/powershell/pwsh -c New-Item -ItemType SymbolicLink -Path "/usr/bin/pwsh" -Target "$PSHOME/pwsh" -Force

# alternatively you can run following to create a symbolic link
# sudo ln -s ~/powershell/pwsh /usr/bin/pwsh

# Now to start PowerShell you can just run "pwsh"
```

### <a name="uninstallation---raspbian"></a>Удаление — Raspbian

```sh
rm -rf ~/powershell
```

## <a name="installing-preview-releases"></a>Установка предварительных выпусков

При установке предварительной версии PowerShell для Linux с помощью репозитория пакетов имя пакета меняется с `powershell` на `powershell-preview`.

При установке с помощью прямого скачивания изменяется только имя файла.

В следующей таблице приведены команды для установки пакетов стабильной и предварительной версий с помощью различных диспетчеров пакетов:

| Дистрибутивы |            Команда стабильной версии            |               Команда предварительной версии                |
| --------------- | ------------------------------------ | -------------------------------------------- |
| Ubuntu, Debian  | `sudo apt-get install -y powershell` | `sudo apt-get install -y powershell-preview` |
| CentOS, RedHat  | `sudo yum install -y powershell`     | `sudo yum install -y powershell-preview`     |
| Fedora          | `sudo dnf install -y powershell`     | `sudo dnf install -y powershell-preview`     |

## <a name="install-as-a-net-global-tool"></a>Установка в качестве глобального средства .NET

Если вы уже установили [пакет SDK для .NET Core](/dotnet/core/sdk), установите PowerShell как [глобальное средство .NET](/dotnet/core/tools/global-tools).

```
dotnet tool install --global PowerShell
```

Установщик инструмента dotnet добавляет `~/.dotnet/tools` в переменную среды `PATH`. Но в выполняющейся оболочке отсутствует обновленная переменная `PATH`. Вы можете запустить PowerShell из новой оболочки, введя `pwsh`.

## <a name="binary-archives"></a>Архивы двоичных файлов

Для поддержки расширенных сценариев развертывания на платформах Linux доступны архивы `tar.gz` двоичных файлов PowerShell.

### <a name="dependencies"></a>Зависимости

PowerShell создает переносимые двоичные файлы для всех дистрибутивов Linux. Но среда выполнения .NET Core, как и PowerShell, требует различные зависимости для разных дистрибутивов.

На следующей диаграмме показаны официально поддерживаемые зависимости .NET Core 2.0 для различных дистрибутивов Linux.

| OS                 | Зависимости |
| ------------------ | ------------ |
| Ubuntu 16.04       | libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6, <br> libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu55 |
| Ubuntu 17.10       | libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6, <br> libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu57 |
| Ubuntu 18.04       | libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6, <br> libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu60 |
| Debian 8 (Jessie)  | libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6, <br> libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52 |
| Debian 9 (Stretch) | libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6, <br> libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.2, libicu57 |
| CentOS 7 <br> Oracle Linux 7 <br> RHEL 7 | libunwind, libcurl, openssl-libs, libicu |
| openSUSE 42.3 | libcurl4, libopenssl1_0_0, libicu52_1 |
| openSUSE Leap 15 | libcurl4, libopenssl1_0_0, libicu60_2 |
| Fedora 27 <br> Fedora 28 | libunwind, libcurl, openssl-libs, libicu, compat-openssl10 |

Чтобы развернуть двоичные файлы PowerShell в дистрибутивах Linux, для которых официальная поддержка не предусмотрена, необходимо специально установить необходимые пакеты, чтобы выполнить все требования, касающиеся зависимостей, для целевой ОС. Например, наш [Dockerfile для Amazon Linux][amazon-dockerfile] сначала устанавливает зависимости, а затем извлекает архив Linux `tar.gz`.

[amazon-dockerfile]: https://github.com/PowerShell/PowerShell-Docker/blob/master/release/community-stable/amazonlinux/docker/Dockerfile

### <a name="installation---binary-archives"></a>Установка — архивы двоичных файлов

#### <a name="linux"></a>Linux

```sh
# Download the powershell '.tar.gz' archive
curl -L -o /tmp/powershell.tar.gz https://github.com/PowerShell/PowerShell/releases/download/v7.1.2/powershell-7.1.2-linux-x64.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /opt/microsoft/powershell/7

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/7

# Set execute permissions
sudo chmod +x /opt/microsoft/powershell/7/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /opt/microsoft/powershell/7/pwsh /usr/bin/pwsh
```

### <a name="uninstalling-binary-archives"></a>Удаление архивов двоичных файлов

```sh
sudo rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="paths"></a>Пути

- `$PSHOME` имеет значение `/opt/microsoft/powershell/7/`.
- Профили пользователей будут считаны из `~/.config/powershell/profile.ps1`.
- Профили по умолчанию будут считаны из `$PSHOME/profile.ps1`.
- Модули пользователей будут считаны из `~/.local/share/powershell/Modules`.
- Общие модули будут считаны из `/usr/local/share/powershell/Modules`.
- Модули по умолчанию будут считаны из `$PSHOME/Modules`.
- Журнал PSReadline будет записан в `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`

Профили учитывают конфигурацию PowerShell для отдельных узлов, поэтому профили конкретных узлов по умолчанию находятся в `Microsoft.PowerShell_profile.ps1` в тех же расположениях.

PowerShell отвечает требованиям [спецификации каталога размещения файлов, связанных со средой настольной графической среды (X-сервера), стандартизированного XDG (X Desktop Group)][xdg-bds] в Linux.

## <a name="installation-support"></a>Поддержка установки

Корпорация Майкрософт поддерживает методы установки, изложенные в этом документе. В других источниках могут быть доступны другие методы установки. Хотя такие инструменты и методы могут работать, корпорация Майкрософт не поддерживает их.

<!-- link references -->
[выпусками]: https://aka.ms/PowerShell-Release?tag=stable
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
[distros]: https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md#linux
[Distribution Support Request]: https://github.com/PowerShell/PowerShell/issues/new?assignees=&labels=Distribution-Request&template=Distribution_Request.md&title=Distribution+Support+Request
