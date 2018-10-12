---
title: Установка PowerShell Core в Linux
description: Сведения об установке PowerShell Core в различных дистрибутивах Linux
ms.date: 08/06/2018
ms.openlocfilehash: d60e1d5a89b6907b67c19b8cfcde969be156bd60
ms.sourcegitcommit: 6749f67c32e05999e10deb9d45f90f45ac21a599
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/08/2018
ms.locfileid: "48851295"
---
# <a name="installing-powershell-core-on-linux"></a><span data-ttu-id="ee732-103">Установка PowerShell Core в Linux</span><span class="sxs-lookup"><span data-stu-id="ee732-103">Installing PowerShell Core on Linux</span></span>

<span data-ttu-id="ee732-104">Поддерживает [Ubuntu 14.04][u14], [Ubuntu 16.04][u16], [Ubuntu 18.10][u18], [Debian 8][deb8], [Debian 9][deb9], [CentOS 7][cos], [Red Hat Enterprise Linux (RHEL) 7][rhel7], [OpenSUSE 42.3][opensuse], [Fedora 27][fedora], [Fedora 28][fedora] и [Arch Linux][arch].</span><span class="sxs-lookup"><span data-stu-id="ee732-104">Supports [Ubuntu 14.04][u14], [Ubuntu 16.04][u16], [Ubuntu 18.10][u18], [Debian 8][deb8], [Debian 9][deb9], [CentOS 7][cos], [Red Hat Enterprise Linux (RHEL) 7][rhel7], [OpenSUSE 42.3][opensuse], [Fedora 27][fedora], [Fedora 28][fedora], and [Arch Linux][arch].</span></span>

<span data-ttu-id="ee732-105">Для дистрибутивов Linux без официальной поддержки попробуйте использовать [snap-пакет PowerShell][snap].</span><span class="sxs-lookup"><span data-stu-id="ee732-105">For Linux distributions that are not officially supported, you can try using the [PowerShell Snap Package][snap].</span></span>
<span data-ttu-id="ee732-106">Можно также попытаться развернуть двоичные файлы PowerShell напрямую с помощью [архива`tar.gz`][tar] Linux, но при этом нужно отдельно настроить необходимые зависимости с учетом операционной системы.</span><span class="sxs-lookup"><span data-stu-id="ee732-106">You can also try deploying PowerShell binaries directly using the Linux [`tar.gz` archive][tar], but you would need to set up the necessary dependencies based on the OS in separate steps.</span></span>

<span data-ttu-id="ee732-107">Все пакеты доступны на нашей странице [выпусков][] GitHub.</span><span class="sxs-lookup"><span data-stu-id="ee732-107">All packages are available on our GitHub [releases][] page.</span></span>
<span data-ttu-id="ee732-108">После установки пакета запустите `pwsh` из терминала.</span><span class="sxs-lookup"><span data-stu-id="ee732-108">Once the package is installed, run `pwsh` from a terminal.</span></span>

[u14]: #ubuntu-1404
[u16]: #ubuntu-1604
[u18]: #ubuntu-1810
[u18]: #ubuntu-1804
[deb8]: #debian-8
[deb9]: #debian-9
[cos]: #centos-7
[rhel7]: #red-hat-enterprise-linux-rhel-7
[opensuse]: #opensuse-423
[fedora]: #fedora
[arch]: #arch-linux
[snap]: #snap-package
[tar]: #binary-archives

## <a name="installing-preview-releases"></a><span data-ttu-id="ee732-109">Установка предварительных выпусков</span><span class="sxs-lookup"><span data-stu-id="ee732-109">Installing Preview Releases</span></span>

<span data-ttu-id="ee732-110">При установке предварительной версии PowerShell Core для Linux с помощью репозитория пакетов имя пакета меняется с `powershell` на `powershell-preview`.</span><span class="sxs-lookup"><span data-stu-id="ee732-110">When installing a PowerShell Core Preview release for Linux via a Package Repository, the package name changes from `powershell` to `powershell-preview`.</span></span>

<span data-ttu-id="ee732-111">При установке с помощью прямого скачивания изменяется только имя файла.</span><span class="sxs-lookup"><span data-stu-id="ee732-111">Installing via direct download does not change, other than the file name.</span></span>

<span data-ttu-id="ee732-112">Ниже приведена таблица команд для установки пакетов стабильной и предварительной версий с помощью различных диспетчеров пакетов.</span><span class="sxs-lookup"><span data-stu-id="ee732-112">Here is a table of the commands to install the stable and preview packages using the various package managers:</span></span>

|<span data-ttu-id="ee732-113">Дистрибутивы</span><span class="sxs-lookup"><span data-stu-id="ee732-113">Distribution(s)</span></span>|<span data-ttu-id="ee732-114">Команда стабильной версии</span><span class="sxs-lookup"><span data-stu-id="ee732-114">Stable Command</span></span> | <span data-ttu-id="ee732-115">Команда предварительной версии</span><span class="sxs-lookup"><span data-stu-id="ee732-115">Preview Command</span></span> |
|---------------|---------------|-----------------|
| <span data-ttu-id="ee732-116">Ubuntu, Debian</span><span class="sxs-lookup"><span data-stu-id="ee732-116">Ubuntu, Debian</span></span> |`sudo apt-get install -y powershell`| `sudo apt-get install -y powershell-preview`|
| <span data-ttu-id="ee732-117">CentOS, RedHat</span><span class="sxs-lookup"><span data-stu-id="ee732-117">CentOS, RedHat</span></span> |`sudo yum install -y powershell` | `sudo yum install -y powershell-preview`|
| <span data-ttu-id="ee732-118">OpenSUSE</span><span class="sxs-lookup"><span data-stu-id="ee732-118">OpenSUSE</span></span> |`sudo zypper install powershell` | `sudo zypper install powershell-preview`|
| <span data-ttu-id="ee732-119">Fedora</span><span class="sxs-lookup"><span data-stu-id="ee732-119">Fedora</span></span>   |`sudo dnf install -y powershell` | `sudo dnf install -y powershell-preview`|

## <a name="ubuntu-1404"></a><span data-ttu-id="ee732-120">Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="ee732-120">Ubuntu 14.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1404"></a><span data-ttu-id="ee732-121">Установка с помощью репозитория пакетов — Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="ee732-121">Installation via Package Repository - Ubuntu 14.04</span></span>

<span data-ttu-id="ee732-122">Для упрощения установки (и обновления) PowerShell Core для Linux публикуются в репозиториях пакетов.</span><span class="sxs-lookup"><span data-stu-id="ee732-122">PowerShell Core, for Linux, is published to package repositories for easy installation (and updates).</span></span>
<span data-ttu-id="ee732-123">Это предпочтительный метод.</span><span class="sxs-lookup"><span data-stu-id="ee732-123">This is the preferred method.</span></span>

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

<span data-ttu-id="ee732-124">В качестве суперпользователя зарегистрируйте репозиторий Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ee732-124">As superuser, register the Microsoft repository.</span></span>
<span data-ttu-id="ee732-125">В дальнейшем для обновления установки необходимо просто использовать `sudo apt-get upgrade powershell`.</span><span class="sxs-lookup"><span data-stu-id="ee732-125">From then on, you just need to use `sudo apt-get upgrade powershell` to update the installation.</span></span>

### <a name="installation-via-direct-download---ubuntu-1404"></a><span data-ttu-id="ee732-126">Установка с помощью прямого скачивания — Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="ee732-126">Installation via Direct Download - Ubuntu 14.04</span></span>

<span data-ttu-id="ee732-127">Скачайте пакет Debian `powershell_6.1.0-1.ubuntu.14.04_amd64.deb`</span><span class="sxs-lookup"><span data-stu-id="ee732-127">Download the Debian package `powershell_6.1.0-1.ubuntu.14.04_amd64.deb`</span></span>
<span data-ttu-id="ee732-128">со страницы [выпусков][] на компьютер с Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="ee732-128">from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="ee732-129">Затем выполните в терминале следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ee732-129">Then execute the following in the terminal:</span></span>

```sh
sudo dpkg -i powershell_6.1.0-1.ubuntu.14.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="ee732-130">Команда `dpkg -i` завершается ошибкой при наличии несопоставленных зависимостей.</span><span class="sxs-lookup"><span data-stu-id="ee732-130">The `dpkg -i` command fails with unmet dependencies.</span></span>
> <span data-ttu-id="ee732-131">Следующая команда, `apt-get install -f`, разрешает эти ошибки и завершает настройку пакета PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ee732-131">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1404"></a><span data-ttu-id="ee732-132">Удаление — Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="ee732-132">Uninstallation - Ubuntu 14.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1604"></a><span data-ttu-id="ee732-133">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="ee732-133">Ubuntu 16.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1604"></a><span data-ttu-id="ee732-134">Установка с помощью репозитория пакетов — Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="ee732-134">Installation via Package Repository - Ubuntu 16.04</span></span>

<span data-ttu-id="ee732-135">Для упрощения установки (и обновления) PowerShell Core для Linux публикуются в репозиториях пакетов.</span><span class="sxs-lookup"><span data-stu-id="ee732-135">PowerShell Core, for Linux, is published to package repositories for easy installation (and updates).</span></span>
<span data-ttu-id="ee732-136">Это предпочтительный метод.</span><span class="sxs-lookup"><span data-stu-id="ee732-136">This is the preferred method.</span></span>

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

<span data-ttu-id="ee732-137">Зарегистрировав репозиторий Майкрософт в качестве суперпользователя, в дальнейшем вам потребуется лишь использовать `sudo apt-get upgrade powershell` для его обновления.</span><span class="sxs-lookup"><span data-stu-id="ee732-137">After registering the Microsoft repository once as superuser, from then on, you just need to use `sudo apt-get upgrade powershell` to update it.</span></span>

### <a name="installation-via-direct-download---ubuntu-1604"></a><span data-ttu-id="ee732-138">Установка с помощью прямого скачивания — Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="ee732-138">Installation via Direct Download - Ubuntu 16.04</span></span>

<span data-ttu-id="ee732-139">Скачайте пакет Debian `powershell_6.1.0-1.ubuntu.16.04_amd64.deb`</span><span class="sxs-lookup"><span data-stu-id="ee732-139">Download the Debian package `powershell_6.1.0-1.ubuntu.16.04_amd64.deb`</span></span>
<span data-ttu-id="ee732-140">со страницы [выпусков][] на компьютер с Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="ee732-140">from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="ee732-141">Затем выполните в терминале следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ee732-141">Then execute the following in the terminal:</span></span>

```sh
sudo dpkg -i powershell_6.1.0-1.ubuntu.16.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="ee732-142">Команда `dpkg -i` завершается ошибкой при наличии несопоставленных зависимостей.</span><span class="sxs-lookup"><span data-stu-id="ee732-142">The `dpkg -i` command fails with unmet dependencies.</span></span>
> <span data-ttu-id="ee732-143">Следующая команда, `apt-get install -f`, разрешает эти ошибки и завершает настройку пакета PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ee732-143">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1604"></a><span data-ttu-id="ee732-144">Удаление — Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="ee732-144">Uninstallation - Ubuntu 16.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1804"></a><span data-ttu-id="ee732-145">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="ee732-145">Ubuntu 18.04</span></span>

> [!NOTE]
> <span data-ttu-id="ee732-146">Поддержка Ubuntu 18.04 добавлена после `6.1.0-preview.2`</span><span class="sxs-lookup"><span data-stu-id="ee732-146">Support for Ubuntu 18.04 was added after `6.1.0-preview.2`</span></span>

### <a name="installation-via-package-repository---ubuntu-1804"></a><span data-ttu-id="ee732-147">Установка с помощью репозитория пакетов — Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="ee732-147">Installation via Package Repository - Ubuntu 18.04</span></span>

<span data-ttu-id="ee732-148">Для упрощения установки (и обновления) PowerShell Core для Linux публикуются в репозиториях пакетов.</span><span class="sxs-lookup"><span data-stu-id="ee732-148">PowerShell Core, for Linux, is published to package repositories for easy installation (and updates).</span></span>
<span data-ttu-id="ee732-149">Это предпочтительный метод.</span><span class="sxs-lookup"><span data-stu-id="ee732-149">This is the preferred method.</span></span>

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

<span data-ttu-id="ee732-150">Зарегистрировав репозиторий Майкрософт в качестве суперпользователя, в дальнейшем вам потребуется лишь использовать `sudo apt-get upgrade powershell` для его обновления.</span><span class="sxs-lookup"><span data-stu-id="ee732-150">After registering the Microsoft repository once as superuser, from then on, you just need to use `sudo apt-get upgrade powershell` to update it.</span></span>

### <a name="installation-via-direct-download---ubuntu-1804"></a><span data-ttu-id="ee732-151">Установка с помощью прямого скачивания — Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="ee732-151">Installation via Direct Download - Ubuntu 18.04</span></span>

<span data-ttu-id="ee732-152">Скачайте пакет Debian `powershell_6.1.0-1.ubuntu.18.04_amd64.deb`</span><span class="sxs-lookup"><span data-stu-id="ee732-152">Download the Debian package `powershell_6.1.0-1.ubuntu.18.04_amd64.deb`</span></span>
<span data-ttu-id="ee732-153">со страницы [выпусков][] на компьютер с Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="ee732-153">from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="ee732-154">Затем выполните в терминале следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ee732-154">Then execute the following in the terminal:</span></span>

```sh
sudo dpkg -i powershell_6.1.0-1.ubuntu.18.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="ee732-155">Команда `dpkg -i` завершается ошибкой при наличии несопоставленных зависимостей.</span><span class="sxs-lookup"><span data-stu-id="ee732-155">The `dpkg -i` command fails with unmet dependencies.</span></span>
> <span data-ttu-id="ee732-156">Следующая команда, `apt-get install -f`, разрешает эти ошибки и завершает настройку пакета PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ee732-156">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1804"></a><span data-ttu-id="ee732-157">Удаление — Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="ee732-157">Uninstallation - Ubuntu 18.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1810"></a><span data-ttu-id="ee732-158">Ubuntu 18.10</span><span class="sxs-lookup"><span data-stu-id="ee732-158">Ubuntu 18.10</span></span>

> [!NOTE]
> <span data-ttu-id="ee732-159">Поддержка Ubuntu 18.10 была добавлена после `6.1.0-preview.3`.</span><span class="sxs-lookup"><span data-stu-id="ee732-159">Support for Ubuntu 18.10 was added after `6.1.0-preview.3`.</span></span>
> <span data-ttu-id="ee732-160">Так как в версии 18.10 используется ежедневная сборка, эта версия поддерживается только сообществом.</span><span class="sxs-lookup"><span data-stu-id="ee732-160">As 18.10 is a daily build, it is only community supported.</span></span>

<span data-ttu-id="ee732-161">Установка версии 18.10 поддерживается с помощью `snapd`.</span><span class="sxs-lookup"><span data-stu-id="ee732-161">Installing on 18.10 is supported via `snapd`.</span></span> <span data-ttu-id="ee732-162">Полные инструкции см. в разделе [Snap-пакет][snap].</span><span class="sxs-lookup"><span data-stu-id="ee732-162">See [Snap Package][snap] for full instructions;</span></span>

## <a name="debian-8"></a><span data-ttu-id="ee732-163">Debian 8</span><span class="sxs-lookup"><span data-stu-id="ee732-163">Debian 8</span></span>

### <a name="installation-via-package-repository---debian-8"></a><span data-ttu-id="ee732-164">Установка с помощью репозитория пакетов — Debian 8</span><span class="sxs-lookup"><span data-stu-id="ee732-164">Installation via Package Repository - Debian 8</span></span>

<span data-ttu-id="ee732-165">Для упрощения установки (и обновления) PowerShell Core для Linux публикуются в репозиториях пакетов.</span><span class="sxs-lookup"><span data-stu-id="ee732-165">PowerShell Core, for Linux, is published to package repositories for easy installation (and updates).</span></span>
<span data-ttu-id="ee732-166">Это предпочтительный метод.</span><span class="sxs-lookup"><span data-stu-id="ee732-166">This is the preferred method.</span></span>

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

<span data-ttu-id="ee732-167">Зарегистрировав репозиторий Майкрософт в качестве суперпользователя, в дальнейшем вам потребуется лишь использовать `sudo apt-get upgrade powershell` для его обновления.</span><span class="sxs-lookup"><span data-stu-id="ee732-167">After registering the Microsoft repository once as superuser, from then on, you just need to use `sudo apt-get upgrade powershell` to update it.</span></span>

### <a name="installation-via-direct-download---debian-8"></a><span data-ttu-id="ee732-168">Установка с помощью прямого скачивания — Debian 8</span><span class="sxs-lookup"><span data-stu-id="ee732-168">Installation via Direct Download - Debian 8</span></span>

<span data-ttu-id="ee732-169">Скачайте пакет Debian `powershell_6.1.0-1.debian.8_amd64.deb`</span><span class="sxs-lookup"><span data-stu-id="ee732-169">Download the Debian package `powershell_6.1.0-1.debian.8_amd64.deb`</span></span>
<span data-ttu-id="ee732-170">со страницы [выпусков][] на компьютер с Debian.</span><span class="sxs-lookup"><span data-stu-id="ee732-170">from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="ee732-171">Затем выполните в терминале следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ee732-171">Then execute the following in the terminal:</span></span>

```sh
sudo dpkg -i powershell_6.1.0-1.debian.8_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="ee732-172">Команда `dpkg -i` завершается ошибкой при наличии несопоставленных зависимостей.</span><span class="sxs-lookup"><span data-stu-id="ee732-172">The `dpkg -i` command fails with unmet dependencies.</span></span>
> <span data-ttu-id="ee732-173">Следующая команда, `apt-get install -f`, разрешает эти ошибки и завершает настройку пакета PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ee732-173">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---debian-8"></a><span data-ttu-id="ee732-174">Удаление — Debian 8</span><span class="sxs-lookup"><span data-stu-id="ee732-174">Uninstallation - Debian 8</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="debian-9"></a><span data-ttu-id="ee732-175">Debian 9</span><span class="sxs-lookup"><span data-stu-id="ee732-175">Debian 9</span></span>

### <a name="installation-via-package-repository---debian-9"></a><span data-ttu-id="ee732-176">Установка с помощью репозитория пакетов — Debian 9</span><span class="sxs-lookup"><span data-stu-id="ee732-176">Installation via Package Repository - Debian 9</span></span>

<span data-ttu-id="ee732-177">Для упрощения установки (и обновления) PowerShell Core для Linux публикуются в репозиториях пакетов.</span><span class="sxs-lookup"><span data-stu-id="ee732-177">PowerShell Core, for Linux, is published to package repositories for easy installation (and updates).</span></span>
<span data-ttu-id="ee732-178">Это предпочтительный метод.</span><span class="sxs-lookup"><span data-stu-id="ee732-178">This is the preferred method.</span></span>

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

<span data-ttu-id="ee732-179">Зарегистрировав репозиторий Майкрософт в качестве суперпользователя, в дальнейшем вам потребуется лишь использовать `sudo apt-get upgrade powershell` для его обновления.</span><span class="sxs-lookup"><span data-stu-id="ee732-179">After registering the Microsoft repository once as superuser, from then on, you just need to use `sudo apt-get upgrade powershell` to update it.</span></span>

### <a name="installation-via-direct-download---debian-9"></a><span data-ttu-id="ee732-180">Установка с помощью прямого скачивания — Debian 9</span><span class="sxs-lookup"><span data-stu-id="ee732-180">Installation via Direct Download - Debian 9</span></span>

<span data-ttu-id="ee732-181">Скачайте пакет Debian `powershell_6.1.0-1.debian.9_amd64.deb`</span><span class="sxs-lookup"><span data-stu-id="ee732-181">Download the Debian package `powershell_6.1.0-1.debian.9_amd64.deb`</span></span>
<span data-ttu-id="ee732-182">со страницы [выпусков][] на компьютер с Debian.</span><span class="sxs-lookup"><span data-stu-id="ee732-182">from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="ee732-183">Затем выполните в терминале следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ee732-183">Then execute the following in the terminal:</span></span>

```sh
sudo dpkg -i powershell_6.1.0-1.debian.9_amd64.deb
sudo apt-get install -f
```

### <a name="uninstallation---debian-9"></a><span data-ttu-id="ee732-184">Удаление — Debian 9</span><span class="sxs-lookup"><span data-stu-id="ee732-184">Uninstallation - Debian 9</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="centos-7"></a><span data-ttu-id="ee732-185">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="ee732-185">CentOS 7</span></span>

> [!NOTE]
> <span data-ttu-id="ee732-186">Этот пакет также работает в Oracle Linux 7.</span><span class="sxs-lookup"><span data-stu-id="ee732-186">This package also works on Oracle Linux 7.</span></span>

### <a name="installation-via-package-repository-preferred---centos-7"></a><span data-ttu-id="ee732-187">Установка с помощью репозитория пакетов (рекомендуется) — CentOS 7</span><span class="sxs-lookup"><span data-stu-id="ee732-187">Installation via Package Repository (preferred) - CentOS 7</span></span>

<span data-ttu-id="ee732-188">Для упрощения установки (и обновления) PowerShell Core для Linux публикуются в официальных репозиториях Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="ee732-188">PowerShell Core for Linux is published to official Microsoft repositories for easy installation (and updates).</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="ee732-189">Зарегистрировав репозиторий Майкрософт в качестве суперпользователя, в дальнейшем вам потребуется лишь использовать `sudo yum update powershell` для обновления PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ee732-189">After registering the Microsoft repository once as superuser, you just need to use `sudo yum update powershell` to update PowerShell.</span></span>

### <a name="installation-via-direct-download---centos-7"></a><span data-ttu-id="ee732-190">Установка с помощью прямого скачивания — CentOS 7</span><span class="sxs-lookup"><span data-stu-id="ee732-190">Installation via Direct Download - CentOS 7</span></span>

<span data-ttu-id="ee732-191">С помощью [CentOS 7][] скачайте пакет RPM `powershell-6.1.0-1.rhel.7.x86_64.rpm`</span><span class="sxs-lookup"><span data-stu-id="ee732-191">Using [CentOS 7][], download the RPM package `powershell-6.1.0-1.rhel.7.x86_64.rpm`</span></span>
<span data-ttu-id="ee732-192">со страницы [выпусков][] на компьютер с CentOS.</span><span class="sxs-lookup"><span data-stu-id="ee732-192">from the [releases][] page onto the CentOS machine.</span></span>

<span data-ttu-id="ee732-193">Затем выполните в терминале следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ee732-193">Then execute the following in the terminal:</span></span>

```sh
sudo yum install powershell-6.1.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="ee732-194">Кроме того, RPM можно установить без промежуточного скачивания:</span><span class="sxs-lookup"><span data-stu-id="ee732-194">You can also install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v6.1.0/powershell-6.1.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---centos-7"></a><span data-ttu-id="ee732-195">Удаление — CentOS 7</span><span class="sxs-lookup"><span data-stu-id="ee732-195">Uninstallation - CentOS 7</span></span>

```sh
sudo yum remove powershell
```

[CentOS 7]: https://www.centos.org/download/

## <a name="red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="ee732-197">Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="ee732-197">Red Hat Enterprise Linux (RHEL) 7</span></span>

### <a name="installation-via-package-repository-preferred---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="ee732-198">Установка с помощью репозитория пакетов (рекомендуется) — Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="ee732-198">Installation via Package Repository (preferred) - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="ee732-199">Для упрощения установки (и обновления) PowerShell Core для Linux публикуются в официальных репозиториях Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="ee732-199">PowerShell Core for Linux is published to official Microsoft repositories for easy installation (and updates).</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="ee732-200">Зарегистрировав репозиторий Майкрософт в качестве суперпользователя, в дальнейшем вам потребуется лишь использовать `sudo yum update powershell` для обновления PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ee732-200">After registering the Microsoft repository once as superuser, you just need to use `sudo yum update powershell` to update PowerShell.</span></span>

### <a name="installation-via-direct-download---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="ee732-201">Установка с помощью прямого скачивания — Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="ee732-201">Installation via Direct Download - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="ee732-202">Скачайте пакет RPM `powershell-6.1.0-1.rhel.7.x86_64.rpm`</span><span class="sxs-lookup"><span data-stu-id="ee732-202">Download the RPM package `powershell-6.1.0-1.rhel.7.x86_64.rpm`</span></span>
<span data-ttu-id="ee732-203">со страницы [выпусков][] на компьютер с Red Hat Enterprise Linux.</span><span class="sxs-lookup"><span data-stu-id="ee732-203">from the [releases][] page onto the Red Hat Enterprise Linux machine.</span></span>

<span data-ttu-id="ee732-204">Затем выполните в терминале следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ee732-204">Then execute the following in the terminal:</span></span>

```sh
sudo yum install powershell-6.1.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="ee732-205">Кроме того, RPM можно установить без промежуточного скачивания:</span><span class="sxs-lookup"><span data-stu-id="ee732-205">You can also install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v6.1.0/powershell-6.1.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="ee732-206">Удаление — Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="ee732-206">Uninstallation - Red Hat Enterprise Linux (RHEL) 7</span></span>

```sh
sudo yum remove powershell
```

## <a name="opensuse-423"></a><span data-ttu-id="ee732-207">OpenSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="ee732-207">OpenSUSE 42.3</span></span>

<span data-ttu-id="ee732-208">В процессе установки PowerShell Core `zypper` может выдать предупреждение о следующей ошибке:</span><span class="sxs-lookup"><span data-stu-id="ee732-208">When installing PowerShell Core, `zypper` may report the following error:</span></span>

```Output
Problem: nothing provides libcurl needed by powershell-6.1.0-1.rhel.7.x86_64
 Solution 1: do not install powershell-6.1.0-1.rhel.7.x86_64
 Solution 2: break powershell-6.1.0-1.rhel.7.x86_64 by ignoring some of its dependencies
```

<span data-ttu-id="ee732-209">В этом случае убедитесь в наличии совместимой библиотеки `libcurl`, проверив, что в результате выполнения следующей команды пакет `libcurl4` отображается как установленный:</span><span class="sxs-lookup"><span data-stu-id="ee732-209">In this case, verify that a compatible `libcurl` library is present by checking that the following command shows the `libcurl4` package as installed:</span></span>

```sh
zypper search --file-list --match-exact '/usr/lib64/libcurl.so.4'
```

<span data-ttu-id="ee732-210">Далее, при установке пакета PowerShell, выберите решение `break powershell-6.1.0-1.rhel.7.x86_64 by ignoring some of its dependencies`.</span><span class="sxs-lookup"><span data-stu-id="ee732-210">Then choose the `break powershell-6.1.0-1.rhel.7.x86_64 by ignoring some of its dependencies` solution when installing the PowerShell package.</span></span>

### <a name="installation-via-package-repository-preferred---opensuse-423"></a><span data-ttu-id="ee732-211">Установка с помощью репозитория пакетов (рекомендуется) — OpenSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="ee732-211">Installation via Package Repository (preferred) - OpenSUSE 42.3</span></span>

<span data-ttu-id="ee732-212">Для упрощения установки (и обновления) PowerShell Core для Linux публикуются в официальных репозиториях Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="ee732-212">PowerShell Core for Linux is published to official Microsoft repositories for easy installation (and updates).</span></span>

```sh
# Register the Microsoft signature key
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc

# Add the Microsoft Repository
zypper ar https://packages.microsoft.com/rhel/7/prod/

# Update the list of products
sudo zypper update

# Install PowerShell
sudo zypper install powershell

# Start PowerShell
pwsh
```

### <a name="installation-via-direct-download---opensuse-423"></a><span data-ttu-id="ee732-213">Установка с помощью прямого скачивания — OpenSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="ee732-213">Installation via Direct Download - OpenSUSE 42.3</span></span>

<span data-ttu-id="ee732-214">Скачайте пакет RPM `powershell-6.1.0-1.rhel.7.x86_64.rpm` со страницы [выпусков][] на компьютер с OpenSUSE.</span><span class="sxs-lookup"><span data-stu-id="ee732-214">Download the RPM package `powershell-6.1.0-1.rhel.7.x86_64.rpm` from the [releases][] page onto the OpenSUSE machine.</span></span>

```sh
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo zypper install powershell-6.1.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="ee732-215">Кроме того, RPM можно установить без промежуточного скачивания:</span><span class="sxs-lookup"><span data-stu-id="ee732-215">You can also install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo zypper install https://github.com/PowerShell/PowerShell/releases/download/v6.1.0/powershell-6.1.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---opensuse-423"></a><span data-ttu-id="ee732-216">Удаление — OpenSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="ee732-216">Uninstallation - OpenSUSE 42.3</span></span>

```sh
sudo zypper remove powershell
```

## <a name="fedora"></a><span data-ttu-id="ee732-217">Fedora</span><span class="sxs-lookup"><span data-stu-id="ee732-217">Fedora</span></span>

> [!NOTE]
> <span data-ttu-id="ee732-218">Fedora 28 поддерживается только в PowerShell Core 6.1 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="ee732-218">Fedora 28 is only supported in PowerShell Core 6.1 and newer.</span></span>

### <a name="installation-via-package-repository-preferred---fedora-27-fedora-28"></a><span data-ttu-id="ee732-219">Установка с помощью репозитория пакетов (рекомендуется) — Fedora 27, Fedora 28</span><span class="sxs-lookup"><span data-stu-id="ee732-219">Installation via Package Repository (preferred) - Fedora 27, Fedora 28</span></span>

<span data-ttu-id="ee732-220">Для упрощения установки (и обновления) PowerShell Core для Linux публикуются в официальных репозиториях Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="ee732-220">PowerShell Core for Linux is published to official Microsoft repositories for easy installation (and updates).</span></span>

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

### <a name="installation-via-direct-download---fedora-27-fedora-28"></a><span data-ttu-id="ee732-221">Установка с помощью прямого скачивания — Fedora 27, Fedora 28</span><span class="sxs-lookup"><span data-stu-id="ee732-221">Installation via Direct Download - Fedora 27, Fedora 28</span></span>

<span data-ttu-id="ee732-222">Скачайте пакет RPM `powershell-6.1.0-1.rhel.7.x86_64.rpm`</span><span class="sxs-lookup"><span data-stu-id="ee732-222">Download the RPM package `powershell-6.1.0-1.rhel.7.x86_64.rpm`</span></span>
<span data-ttu-id="ee732-223">со страницы [выпусков][] на компьютер с Fedora.</span><span class="sxs-lookup"><span data-stu-id="ee732-223">from the [releases][] page onto the Fedora machine.</span></span>

<span data-ttu-id="ee732-224">Затем выполните в терминале следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ee732-224">Then execute the following in the terminal:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install powershell-6.1.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="ee732-225">Кроме того, RPM можно установить без промежуточного скачивания:</span><span class="sxs-lookup"><span data-stu-id="ee732-225">You can also install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install https://github.com/PowerShell/PowerShell/releases/download/v6.1.0/powershell-6.1.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---fedora-27-fedora-28"></a><span data-ttu-id="ee732-226">Удаление — Fedora 27, Fedora 28</span><span class="sxs-lookup"><span data-stu-id="ee732-226">Uninstallation - Fedora 27, Fedora 28</span></span>

```sh
sudo dnf remove powershell
```

## <a name="arch-linux"></a><span data-ttu-id="ee732-227">Arch Linux</span><span class="sxs-lookup"><span data-stu-id="ee732-227">Arch Linux</span></span>

> [!NOTE]
> <span data-ttu-id="ee732-228">Поддержка Arch на этапе эксперимента.</span><span class="sxs-lookup"><span data-stu-id="ee732-228">Arch support is experimental.</span></span>

<span data-ttu-id="ee732-229">PowerShell можно получить из пользовательского репозитория [Arch Linux][] (AUR).</span><span class="sxs-lookup"><span data-stu-id="ee732-229">PowerShell is available from the [Arch Linux][] User Repository (AUR).</span></span>

* <span data-ttu-id="ee732-230">Его можно скомпилировать с помощью [последнего выпуска с тегами][arch-release].</span><span class="sxs-lookup"><span data-stu-id="ee732-230">It can be compiled with the [latest tagged release][arch-release]</span></span>
* <span data-ttu-id="ee732-231">Его можно скомпилировать из [последней фиксации в основной репозиторий][arch-git].</span><span class="sxs-lookup"><span data-stu-id="ee732-231">It can be compiled from the [latest commit to master][arch-git]</span></span>
* <span data-ttu-id="ee732-232">Его можно установить с помощью [двоичного файла последнего выпуска][arch-bin].</span><span class="sxs-lookup"><span data-stu-id="ee732-232">It can be installed using the [latest release binary][arch-bin]</span></span>

<span data-ttu-id="ee732-233">Пакеты в AUR обслуживаются сообществом — официальная поддержка отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ee732-233">Packages in the AUR are community maintained - there is no official support.</span></span>

<span data-ttu-id="ee732-234">Дополнительные сведения об установке пакетов из AUR см. на [вики-сайте Arch Linux](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) или в [DockerFile](https://github.com/PowerShell/PowerShell/blob/master/docker/community/archlinux/Dockerfile) сообщества.</span><span class="sxs-lookup"><span data-stu-id="ee732-234">For more information on installing packages from the AUR, see the [Arch Linux wiki](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) or the community [DockerFile](https://github.com/PowerShell/PowerShell/blob/master/docker/community/archlinux/Dockerfile).</span></span>

[Arch Linux]: https://www.archlinux.org/download/
[arch-release]: https://aur.archlinux.org/packages/powershell/
[arch-git]: https://aur.archlinux.org/packages/powershell-git/
[arch-bin]: https://aur.archlinux.org/packages/powershell-bin/

## <a name="snap-package"></a><span data-ttu-id="ee732-236">Snap-пакет</span><span class="sxs-lookup"><span data-stu-id="ee732-236">Snap Package</span></span>

### <a name="getting-snapd"></a><span data-ttu-id="ee732-237">Установка Snap</span><span class="sxs-lookup"><span data-stu-id="ee732-237">Getting snapd</span></span>

<span data-ttu-id="ee732-238">Утилита `snapd` необходима для запуска snap-пакетов.</span><span class="sxs-lookup"><span data-stu-id="ee732-238">`snapd` is required to run snaps.</span></span>
<span data-ttu-id="ee732-239">Чтобы убедиться, что утилита `snapd` установлена, воспользуйтесь [этими инструкциями](https://docs.snapcraft.io/core/install).</span><span class="sxs-lookup"><span data-stu-id="ee732-239">Use [these instructions](https://docs.snapcraft.io/core/install) to make sure you have `snapd` installed.</span></span>

### <a name="installation-via-snap"></a><span data-ttu-id="ee732-240">Установка с использованием Snap</span><span class="sxs-lookup"><span data-stu-id="ee732-240">Installation via Snap</span></span>

<span data-ttu-id="ee732-241">Для упрощения установки (и обновления) PowerShell Core для Linux опубликован в [хранилище Snap](https://snapcraft.io/store).</span><span class="sxs-lookup"><span data-stu-id="ee732-241">PowerShell Core, for Linux, is published to the [Snap store](https://snapcraft.io/store) for easy installation (and updates).</span></span>
<span data-ttu-id="ee732-242">Это предпочтительный метод.</span><span class="sxs-lookup"><span data-stu-id="ee732-242">This is the preferred method.</span></span>

```sh
# Install PowerShell
sudo snap install powershell-preview --classic

# Start PowerShell
pwsh-preview
```

<span data-ttu-id="ee732-243">После установки Snap будет автоматически обновлен, но вы можете запустить обновление с помощью `sudo snap refresh powershell-preview`.</span><span class="sxs-lookup"><span data-stu-id="ee732-243">After installing Snap will automatically upgrade, but you can trigger an upgrade using `sudo snap refresh powershell-preview`.</span></span>

### <a name="uninstallation"></a><span data-ttu-id="ee732-244">Удаление</span><span class="sxs-lookup"><span data-stu-id="ee732-244">Uninstallation</span></span>

```sh
sudo snap remove powershell-preview
```

## <a name="kali"></a><span data-ttu-id="ee732-245">Kali</span><span class="sxs-lookup"><span data-stu-id="ee732-245">Kali</span></span>

### <a name="installation"></a><span data-ttu-id="ee732-246">Установка</span><span class="sxs-lookup"><span data-stu-id="ee732-246">Installation</span></span>

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

### <a name="uninstallation---kali"></a><span data-ttu-id="ee732-247">Удаление — Kali</span><span class="sxs-lookup"><span data-stu-id="ee732-247">Uninstallation - Kali</span></span>

```sh
# Uninstall PowerShell package
apt-get remove -y powershell
```

## <a name="raspbian"></a><span data-ttu-id="ee732-248">Raspbian</span><span class="sxs-lookup"><span data-stu-id="ee732-248">Raspbian</span></span>

> [!NOTE]
> <span data-ttu-id="ee732-249">Поддержка Raspbian на этапе эксперимента.</span><span class="sxs-lookup"><span data-stu-id="ee732-249">Raspbian support is experimental.</span></span>

<span data-ttu-id="ee732-250">Сейчас PowerShell поддерживается только в Raspbian Stretch.</span><span class="sxs-lookup"><span data-stu-id="ee732-250">Currently, PowerShell is only supported on Raspbian Stretch.</span></span>

<span data-ttu-id="ee732-251">Кроме того, CoreCLR (а соответственно и PowerShell Core) будет работать только на устройствах Pi 2 и Pi 3, в то время как в устройствах наподобие [Pi Zero](https://github.com/dotnet/coreclr/issues/10605) установлены процессоры, поддержка которых не предусмотрена.</span><span class="sxs-lookup"><span data-stu-id="ee732-251">Also CoreCLR (and thus PowerShell Core) will only work on Pi 2 and Pi 3 devices as other devices, like [Pi Zero](https://github.com/dotnet/coreclr/issues/10605), have an unsupported processor.</span></span>

<span data-ttu-id="ee732-252">Загрузите [Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) и следуйте [инструкциям по установке](https://www.raspberrypi.org/documentation/installation/installing-images/README.md), чтобы установить его на свой Pi.</span><span class="sxs-lookup"><span data-stu-id="ee732-252">Download [Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) and follow the [installation instructions](https://www.raspberrypi.org/documentation/installation/installing-images/README.md) to get it onto your Pi.</span></span>

### <a name="installation"></a><span data-ttu-id="ee732-253">Установка</span><span class="sxs-lookup"><span data-stu-id="ee732-253">Installation</span></span>

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

<span data-ttu-id="ee732-254">При необходимости можно создать символьную ссылку, позволяющую запустить PowerShell без указания пути к двоичному файлу pwsh</span><span class="sxs-lookup"><span data-stu-id="ee732-254">Optionally you can create a symbolic link to be able to start PowerShell without specifying path to the "pwsh" binary</span></span>

```sh
# Start PowerShell from bash with sudo to create a symbolic link
sudo ~/powershell/pwsh -c New-Item -ItemType SymbolicLink -Path "/usr/bin/pwsh" -Target "\$PSHOME/pwsh" -Force

# alternatively you can run following to create a symbolic link
# sudo ln -s ~/powershell/pwsh /usr/bin/pwsh

# Now to start PowerShell you can just run "pwsh"
```

### <a name="uninstallation---raspbian"></a><span data-ttu-id="ee732-255">Удаление — Raspbian</span><span class="sxs-lookup"><span data-stu-id="ee732-255">Uninstallation - Raspbian</span></span>

```sh
rm -rf ~/powershell
```

## <a name="binary-archives"></a><span data-ttu-id="ee732-256">Архивы двоичных файлов</span><span class="sxs-lookup"><span data-stu-id="ee732-256">Binary Archives</span></span>

<span data-ttu-id="ee732-257">Для поддержки расширенных сценариев развертывания на платформах Linux доступны архивы `tar.gz` двоичных файлов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ee732-257">PowerShell binary `tar.gz` archives are provided for Linux platforms to enable advanced deployment scenarios.</span></span>

### <a name="dependencies"></a><span data-ttu-id="ee732-258">Зависимости</span><span class="sxs-lookup"><span data-stu-id="ee732-258">Dependencies</span></span>

<span data-ttu-id="ee732-259">PowerShell создает переносимые двоичные файлы для всех дистрибутивов Linux.</span><span class="sxs-lookup"><span data-stu-id="ee732-259">PowerShell builds portable binaries for all Linux distributions.</span></span>
<span data-ttu-id="ee732-260">Однако среда выполнения .NET Core требует различные зависимости для разных дистрибутивов, и поэтому то же самое делает и PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ee732-260">But .NET Core runtime requires different dependencies on different distributions, and hence PowerShell does the same.</span></span>

<span data-ttu-id="ee732-261">На следующей диаграмме показаны официально поддерживаемые зависимости .NET Core 2.0 для различных дистрибутивов Linux.</span><span class="sxs-lookup"><span data-stu-id="ee732-261">The following chart shows the .NET Core 2.0 dependencies that are officially supported on different Linux distributions.</span></span>

| <span data-ttu-id="ee732-262">ОС</span><span class="sxs-lookup"><span data-stu-id="ee732-262">OS</span></span>                 | <span data-ttu-id="ee732-263">Зависимости</span><span class="sxs-lookup"><span data-stu-id="ee732-263">Dependencies</span></span> |
| ------------------ | ------------ |
| <span data-ttu-id="ee732-264">Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="ee732-264">Ubuntu 14.04</span></span>       | <span data-ttu-id="ee732-265">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="ee732-265">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="ee732-266">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span><span class="sxs-lookup"><span data-stu-id="ee732-266">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span></span> |
| <span data-ttu-id="ee732-267">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="ee732-267">Ubuntu 16.04</span></span>       | <span data-ttu-id="ee732-268">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="ee732-268">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="ee732-269">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu55</span><span class="sxs-lookup"><span data-stu-id="ee732-269">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu55</span></span> |
| <span data-ttu-id="ee732-270">Ubuntu 17.10</span><span class="sxs-lookup"><span data-stu-id="ee732-270">Ubuntu 17.10</span></span>       | <span data-ttu-id="ee732-271">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="ee732-271">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="ee732-272">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu57</span><span class="sxs-lookup"><span data-stu-id="ee732-272">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu57</span></span> |
| <span data-ttu-id="ee732-273">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="ee732-273">Ubuntu 18.04</span></span>       | <span data-ttu-id="ee732-274">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="ee732-274">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="ee732-275">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu60</span><span class="sxs-lookup"><span data-stu-id="ee732-275">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu60</span></span> |
| <span data-ttu-id="ee732-276">Debian 8 (Jessie)</span><span class="sxs-lookup"><span data-stu-id="ee732-276">Debian 8 (Jessie)</span></span>  | <span data-ttu-id="ee732-277">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="ee732-277">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="ee732-278">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span><span class="sxs-lookup"><span data-stu-id="ee732-278">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span></span> |
| <span data-ttu-id="ee732-279">Debian 9 (Stretch)</span><span class="sxs-lookup"><span data-stu-id="ee732-279">Debian 9 (Stretch)</span></span> | <span data-ttu-id="ee732-280">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="ee732-280">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="ee732-281">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.2, libicu57</span><span class="sxs-lookup"><span data-stu-id="ee732-281">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.2, libicu57</span></span> |
| <span data-ttu-id="ee732-282">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="ee732-282">CentOS 7</span></span> <br> <span data-ttu-id="ee732-283">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="ee732-283">Oracle Linux 7</span></span> <br> <span data-ttu-id="ee732-284">RHEL 7</span><span class="sxs-lookup"><span data-stu-id="ee732-284">RHEL 7</span></span> <br> <span data-ttu-id="ee732-285">OpenSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="ee732-285">OpenSUSE OpenSUSE 42.3</span></span> | <span data-ttu-id="ee732-286">libunwind, libcurl, openssl-libs, libicu</span><span class="sxs-lookup"><span data-stu-id="ee732-286">libunwind, libcurl, openssl-libs, libicu</span></span> |
| <span data-ttu-id="ee732-287">Fedora 27</span><span class="sxs-lookup"><span data-stu-id="ee732-287">Fedora 27</span></span> <br> <span data-ttu-id="ee732-288">Fedora 28</span><span class="sxs-lookup"><span data-stu-id="ee732-288">Fedora 28</span></span> | <span data-ttu-id="ee732-289">libunwind, libcurl, openssl-libs, libicu, compat-openssl10</span><span class="sxs-lookup"><span data-stu-id="ee732-289">libunwind, libcurl, openssl-libs, libicu, compat-openssl10</span></span> |

<span data-ttu-id="ee732-290">Чтобы развернуть двоичные файлы PowerShell в дистрибутивах Linux, для которых официальная поддержка не предусмотрена, необходимо специально установить необходимые пакеты, чтобы удовлетворить всем требованиям по зависимостям для целевой ОС.</span><span class="sxs-lookup"><span data-stu-id="ee732-290">To deploy PowerShell binaries on Linux distributions that are not officially supported, you need to install the necessary dependencies for the target OS in separate steps.</span></span>
<span data-ttu-id="ee732-291">Например, наш [Amazon Linux dockerfile][amazon-dockerfile] сначала устанавливает зависимости, а затем извлекает архив Linux `tar.gz`.</span><span class="sxs-lookup"><span data-stu-id="ee732-291">For example, our [Amazon Linux dockerfile][amazon-dockerfile] installs dependencies first, and then extracts the Linux `tar.gz` archive.</span></span>

[amazon-dockerfile]: https://github.com/PowerShell/PowerShell/blob/master/docker/community/amazonlinux/Dockerfile

### <a name="installation---binary-archives"></a><span data-ttu-id="ee732-292">Установка — архивы двоичных файлов</span><span class="sxs-lookup"><span data-stu-id="ee732-292">Installation - Binary Archives</span></span>

#### <a name="linux"></a><span data-ttu-id="ee732-293">Linux</span><span class="sxs-lookup"><span data-stu-id="ee732-293">Linux</span></span>

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

### <a name="uninstalling-binary-archives"></a><span data-ttu-id="ee732-294">Удаление архивов двоичных файлов</span><span class="sxs-lookup"><span data-stu-id="ee732-294">Uninstalling binary archives</span></span>

```sh
sudo rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="paths"></a><span data-ttu-id="ee732-295">Пути</span><span class="sxs-lookup"><span data-stu-id="ee732-295">Paths</span></span>

* <span data-ttu-id="ee732-296">`$PSHOME` имеет значение `/opt/microsoft/powershell/6.1.0/`.</span><span class="sxs-lookup"><span data-stu-id="ee732-296">`$PSHOME` is `/opt/microsoft/powershell/6.1.0/`</span></span>
* <span data-ttu-id="ee732-297">Профили пользователей будут считаны из `~/.config/powershell/profile.ps1`.</span><span class="sxs-lookup"><span data-stu-id="ee732-297">User profiles will be read from `~/.config/powershell/profile.ps1`</span></span>
* <span data-ttu-id="ee732-298">Профили по умолчанию будут считаны из `$PSHOME/profile.ps1`.</span><span class="sxs-lookup"><span data-stu-id="ee732-298">Default profiles will be read from `$PSHOME/profile.ps1`</span></span>
* <span data-ttu-id="ee732-299">Модули пользователей будут считаны из `~/.local/share/powershell/Modules`.</span><span class="sxs-lookup"><span data-stu-id="ee732-299">User modules will be read from `~/.local/share/powershell/Modules`</span></span>
* <span data-ttu-id="ee732-300">Общие модули будут считаны из `/usr/local/share/powershell/Modules`.</span><span class="sxs-lookup"><span data-stu-id="ee732-300">Shared modules will be read from `/usr/local/share/powershell/Modules`</span></span>
* <span data-ttu-id="ee732-301">Модули по умолчанию будут считаны из `$PSHOME/Modules`.</span><span class="sxs-lookup"><span data-stu-id="ee732-301">Default modules will be read from `$PSHOME/Modules`</span></span>
* <span data-ttu-id="ee732-302">Журнал PSReadline будет записан в `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`.</span><span class="sxs-lookup"><span data-stu-id="ee732-302">PSReadline history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="ee732-303">Профили учитывают конфигурацию PowerShell для отдельных узлов, поэтому профили конкретных узлов по умолчанию находятся в `Microsoft.PowerShell_profile.ps1` в тех же расположениях.</span><span class="sxs-lookup"><span data-stu-id="ee732-303">The profiles respect PowerShell's per-host configuration, so the default host-specific profiles exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="ee732-304">PowerShell отвечает требованиям [спецификации каталога размещения файлов, связанных со средой настольной графической среды (X-сервера), стандартизированного XDG (X Desktop Group)][xdg-bds] в Linux.</span><span class="sxs-lookup"><span data-stu-id="ee732-304">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on Linux.</span></span>

[выпусков]: https://github.com/PowerShell/PowerShell/releases/latest
[releases]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
