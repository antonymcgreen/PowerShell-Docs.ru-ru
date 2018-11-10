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
# <a name="installing-powershell-core-on-linux"></a><span data-ttu-id="8a50a-103">Установка PowerShell Core в Linux</span><span class="sxs-lookup"><span data-stu-id="8a50a-103">Installing PowerShell Core on Linux</span></span>

<span data-ttu-id="8a50a-104">Supports [Ubuntu 14.04][u14], [Ubuntu 16.04][u16], [Ubuntu 18.04][u1804], [Ubuntu 18.10][u1810], [Debian 8][deb8], [Debian 9][deb9], [CentOS 7][cos], [Red Hat Enterprise Linux (RHEL) 7][rhel7], [openSUSE 42.3][opensuse], [openSUSE Leap 15][opensuse], [Fedora 27][fedora], [Fedora 28][fedora] и [Arch Linux][arch].</span><span class="sxs-lookup"><span data-stu-id="8a50a-104">Supports [Ubuntu 14.04][u14], [Ubuntu 16.04][u16], [Ubuntu 18.04][u1804], [Ubuntu 18.10][u1810], [Debian 8][deb8], [Debian 9][deb9], [CentOS 7][cos], [Red Hat Enterprise Linux (RHEL) 7][rhel7], [openSUSE 42.3][opensuse], [openSUSE Leap 15][opensuse], [Fedora 27][fedora], [Fedora 28][fedora], and [Arch Linux][arch].</span></span>

<span data-ttu-id="8a50a-105">Для дистрибутивов Linux без официальной поддержки попробуйте использовать [snap-пакет PowerShell][snap].</span><span class="sxs-lookup"><span data-stu-id="8a50a-105">For Linux distributions that are not officially supported, you can try using the [PowerShell Snap Package][snap].</span></span>
<span data-ttu-id="8a50a-106">Можно также попытаться развернуть двоичные файлы PowerShell напрямую с помощью [архива`tar.gz`][tar] Linux, но при этом нужно отдельно настроить необходимые зависимости с учетом операционной системы.</span><span class="sxs-lookup"><span data-stu-id="8a50a-106">You can also try deploying PowerShell binaries directly using the Linux [`tar.gz` archive][tar], but you would need to set up the necessary dependencies based on the OS in separate steps.</span></span>

<span data-ttu-id="8a50a-107">Все пакеты доступны на нашей странице [выпусков][] GitHub.</span><span class="sxs-lookup"><span data-stu-id="8a50a-107">All packages are available on our GitHub [releases][] page.</span></span>
<span data-ttu-id="8a50a-108">После установки пакета запустите `pwsh` из терминала.</span><span class="sxs-lookup"><span data-stu-id="8a50a-108">Once the package is installed, run `pwsh` from a terminal.</span></span>

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

## <a name="installing-preview-releases"></a><span data-ttu-id="8a50a-109">Установка предварительных выпусков</span><span class="sxs-lookup"><span data-stu-id="8a50a-109">Installing Preview Releases</span></span>

<span data-ttu-id="8a50a-110">При установке предварительной версии PowerShell Core для Linux с помощью репозитория пакетов имя пакета меняется с `powershell` на `powershell-preview`.</span><span class="sxs-lookup"><span data-stu-id="8a50a-110">When installing a PowerShell Core Preview release for Linux via a Package Repository, the package name changes from `powershell` to `powershell-preview`.</span></span>

<span data-ttu-id="8a50a-111">При установке с помощью прямого скачивания изменяется только имя файла.</span><span class="sxs-lookup"><span data-stu-id="8a50a-111">Installing via direct download does not change, other than the file name.</span></span>

<span data-ttu-id="8a50a-112">Ниже приведена таблица команд для установки пакетов стабильной и предварительной версий с помощью различных диспетчеров пакетов.</span><span class="sxs-lookup"><span data-stu-id="8a50a-112">Here is a table of the commands to install the stable and preview packages using the various package managers:</span></span>

|<span data-ttu-id="8a50a-113">Дистрибутивы</span><span class="sxs-lookup"><span data-stu-id="8a50a-113">Distribution(s)</span></span>|<span data-ttu-id="8a50a-114">Команда стабильной версии</span><span class="sxs-lookup"><span data-stu-id="8a50a-114">Stable Command</span></span> | <span data-ttu-id="8a50a-115">Команда предварительной версии</span><span class="sxs-lookup"><span data-stu-id="8a50a-115">Preview Command</span></span> |
|---------------|---------------|-----------------|
| <span data-ttu-id="8a50a-116">Ubuntu, Debian</span><span class="sxs-lookup"><span data-stu-id="8a50a-116">Ubuntu, Debian</span></span> |`sudo apt-get install -y powershell`| `sudo apt-get install -y powershell-preview`|
| <span data-ttu-id="8a50a-117">CentOS, RedHat</span><span class="sxs-lookup"><span data-stu-id="8a50a-117">CentOS, RedHat</span></span> |`sudo yum install -y powershell` | `sudo yum install -y powershell-preview`|
| <span data-ttu-id="8a50a-118">Fedora</span><span class="sxs-lookup"><span data-stu-id="8a50a-118">Fedora</span></span>   |`sudo dnf install -y powershell` | `sudo dnf install -y powershell-preview`|

## <a name="ubuntu-1404"></a><span data-ttu-id="8a50a-119">Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="8a50a-119">Ubuntu 14.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1404"></a><span data-ttu-id="8a50a-120">Установка с помощью репозитория пакетов — Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="8a50a-120">Installation via Package Repository - Ubuntu 14.04</span></span>

<span data-ttu-id="8a50a-121">Для упрощения установки (и обновления) PowerShell Core для Linux публикуются в репозиториях пакетов.</span><span class="sxs-lookup"><span data-stu-id="8a50a-121">PowerShell Core, for Linux, is published to package repositories for easy installation (and updates).</span></span>
<span data-ttu-id="8a50a-122">Это предпочтительный метод.</span><span class="sxs-lookup"><span data-stu-id="8a50a-122">This is the preferred method.</span></span>

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

<span data-ttu-id="8a50a-123">В качестве суперпользователя зарегистрируйте репозиторий Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8a50a-123">As superuser, register the Microsoft repository.</span></span>
<span data-ttu-id="8a50a-124">В дальнейшем для обновления установки необходимо просто использовать `sudo apt-get upgrade powershell`.</span><span class="sxs-lookup"><span data-stu-id="8a50a-124">From then on, you just need to use `sudo apt-get upgrade powershell` to update the installation.</span></span>

### <a name="installation-via-direct-download---ubuntu-1404"></a><span data-ttu-id="8a50a-125">Установка с помощью прямого скачивания — Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="8a50a-125">Installation via Direct Download - Ubuntu 14.04</span></span>

<span data-ttu-id="8a50a-126">Скачайте пакет Debian `powershell_6.1.0-1.ubuntu.14.04_amd64.deb`</span><span class="sxs-lookup"><span data-stu-id="8a50a-126">Download the Debian package `powershell_6.1.0-1.ubuntu.14.04_amd64.deb`</span></span>
<span data-ttu-id="8a50a-127">со страницы [выпусков][] на компьютер с Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="8a50a-127">from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="8a50a-128">Затем выполните в терминале следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8a50a-128">Then execute the following in the terminal:</span></span>

```sh
sudo dpkg -i powershell_6.1.0-1.ubuntu.14.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="8a50a-129">Команда `dpkg -i` завершается ошибкой при наличии несопоставленных зависимостей.</span><span class="sxs-lookup"><span data-stu-id="8a50a-129">The `dpkg -i` command fails with unmet dependencies.</span></span>
> <span data-ttu-id="8a50a-130">Следующая команда, `apt-get install -f`, разрешает эти ошибки и завершает настройку пакета PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8a50a-130">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1404"></a><span data-ttu-id="8a50a-131">Удаление — Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="8a50a-131">Uninstallation - Ubuntu 14.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1604"></a><span data-ttu-id="8a50a-132">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="8a50a-132">Ubuntu 16.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1604"></a><span data-ttu-id="8a50a-133">Установка с помощью репозитория пакетов — Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="8a50a-133">Installation via Package Repository - Ubuntu 16.04</span></span>

<span data-ttu-id="8a50a-134">Для упрощения установки (и обновления) PowerShell Core для Linux публикуются в репозиториях пакетов.</span><span class="sxs-lookup"><span data-stu-id="8a50a-134">PowerShell Core, for Linux, is published to package repositories for easy installation (and updates).</span></span>
<span data-ttu-id="8a50a-135">Это предпочтительный метод.</span><span class="sxs-lookup"><span data-stu-id="8a50a-135">This is the preferred method.</span></span>

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

<span data-ttu-id="8a50a-136">Зарегистрировав репозиторий Майкрософт в качестве суперпользователя, в дальнейшем вам потребуется лишь использовать `sudo apt-get upgrade powershell` для его обновления.</span><span class="sxs-lookup"><span data-stu-id="8a50a-136">After registering the Microsoft repository once as superuser, from then on, you just need to use `sudo apt-get upgrade powershell` to update it.</span></span>

### <a name="installation-via-direct-download---ubuntu-1604"></a><span data-ttu-id="8a50a-137">Установка с помощью прямого скачивания — Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="8a50a-137">Installation via Direct Download - Ubuntu 16.04</span></span>

<span data-ttu-id="8a50a-138">Скачайте пакет Debian `powershell_6.1.0-1.ubuntu.16.04_amd64.deb`</span><span class="sxs-lookup"><span data-stu-id="8a50a-138">Download the Debian package `powershell_6.1.0-1.ubuntu.16.04_amd64.deb`</span></span>
<span data-ttu-id="8a50a-139">со страницы [выпусков][] на компьютер с Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="8a50a-139">from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="8a50a-140">Затем выполните в терминале следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8a50a-140">Then execute the following in the terminal:</span></span>

```sh
sudo dpkg -i powershell_6.1.0-1.ubuntu.16.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="8a50a-141">Команда `dpkg -i` завершается ошибкой при наличии несопоставленных зависимостей.</span><span class="sxs-lookup"><span data-stu-id="8a50a-141">The `dpkg -i` command fails with unmet dependencies.</span></span>
> <span data-ttu-id="8a50a-142">Следующая команда, `apt-get install -f`, разрешает эти ошибки и завершает настройку пакета PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8a50a-142">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1604"></a><span data-ttu-id="8a50a-143">Удаление — Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="8a50a-143">Uninstallation - Ubuntu 16.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1804"></a><span data-ttu-id="8a50a-144">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="8a50a-144">Ubuntu 18.04</span></span>

> [!NOTE]
> <span data-ttu-id="8a50a-145">Поддержка Ubuntu 18.04 добавлена после `6.1.0-preview.2`</span><span class="sxs-lookup"><span data-stu-id="8a50a-145">Support for Ubuntu 18.04 was added after `6.1.0-preview.2`</span></span>

### <a name="installation-via-package-repository---ubuntu-1804"></a><span data-ttu-id="8a50a-146">Установка с помощью репозитория пакетов — Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="8a50a-146">Installation via Package Repository - Ubuntu 18.04</span></span>

<span data-ttu-id="8a50a-147">Для упрощения установки (и обновления) PowerShell Core для Linux публикуются в репозиториях пакетов.</span><span class="sxs-lookup"><span data-stu-id="8a50a-147">PowerShell Core, for Linux, is published to package repositories for easy installation (and updates).</span></span>
<span data-ttu-id="8a50a-148">Это предпочтительный метод.</span><span class="sxs-lookup"><span data-stu-id="8a50a-148">This is the preferred method.</span></span>

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

<span data-ttu-id="8a50a-149">Зарегистрировав репозиторий Майкрософт в качестве суперпользователя, в дальнейшем вам потребуется лишь использовать `sudo apt-get upgrade powershell` для его обновления.</span><span class="sxs-lookup"><span data-stu-id="8a50a-149">After registering the Microsoft repository once as superuser, from then on, you just need to use `sudo apt-get upgrade powershell` to update it.</span></span>

### <a name="installation-via-direct-download---ubuntu-1804"></a><span data-ttu-id="8a50a-150">Установка с помощью прямого скачивания — Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="8a50a-150">Installation via Direct Download - Ubuntu 18.04</span></span>

<span data-ttu-id="8a50a-151">Скачайте пакет Debian `powershell_6.1.0-1.ubuntu.18.04_amd64.deb`</span><span class="sxs-lookup"><span data-stu-id="8a50a-151">Download the Debian package `powershell_6.1.0-1.ubuntu.18.04_amd64.deb`</span></span>
<span data-ttu-id="8a50a-152">со страницы [выпусков][] на компьютер с Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="8a50a-152">from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="8a50a-153">Затем выполните в терминале следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8a50a-153">Then execute the following in the terminal:</span></span>

```sh
sudo dpkg -i powershell_6.1.0-1.ubuntu.18.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="8a50a-154">Команда `dpkg -i` завершается ошибкой при наличии несопоставленных зависимостей.</span><span class="sxs-lookup"><span data-stu-id="8a50a-154">The `dpkg -i` command fails with unmet dependencies.</span></span>
> <span data-ttu-id="8a50a-155">Следующая команда, `apt-get install -f`, разрешает эти ошибки и завершает настройку пакета PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8a50a-155">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1804"></a><span data-ttu-id="8a50a-156">Удаление — Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="8a50a-156">Uninstallation - Ubuntu 18.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1810"></a><span data-ttu-id="8a50a-157">Ubuntu 18.10</span><span class="sxs-lookup"><span data-stu-id="8a50a-157">Ubuntu 18.10</span></span>

> [!NOTE]
> <span data-ttu-id="8a50a-158">Поддержка Ubuntu 18.10 была добавлена после `6.1.0-preview.3`.</span><span class="sxs-lookup"><span data-stu-id="8a50a-158">Support for Ubuntu 18.10 was added after `6.1.0-preview.3`.</span></span>
> <span data-ttu-id="8a50a-159">Так как в версии 18.10 используется ежедневная сборка, эта версия поддерживается только сообществом.</span><span class="sxs-lookup"><span data-stu-id="8a50a-159">As 18.10 is a daily build, it is only community supported.</span></span>

<span data-ttu-id="8a50a-160">Установка версии 18.10 поддерживается с помощью `snapd`.</span><span class="sxs-lookup"><span data-stu-id="8a50a-160">Installing on 18.10 is supported via `snapd`.</span></span> <span data-ttu-id="8a50a-161">Полные инструкции см. в разделе [Snap-пакет][snap].</span><span class="sxs-lookup"><span data-stu-id="8a50a-161">See [Snap Package][snap] for full instructions;</span></span>

## <a name="debian-8"></a><span data-ttu-id="8a50a-162">Debian 8</span><span class="sxs-lookup"><span data-stu-id="8a50a-162">Debian 8</span></span>

### <a name="installation-via-package-repository---debian-8"></a><span data-ttu-id="8a50a-163">Установка с помощью репозитория пакетов — Debian 8</span><span class="sxs-lookup"><span data-stu-id="8a50a-163">Installation via Package Repository - Debian 8</span></span>

<span data-ttu-id="8a50a-164">Для упрощения установки (и обновления) PowerShell Core для Linux публикуются в репозиториях пакетов.</span><span class="sxs-lookup"><span data-stu-id="8a50a-164">PowerShell Core, for Linux, is published to package repositories for easy installation (and updates).</span></span>
<span data-ttu-id="8a50a-165">Это предпочтительный метод.</span><span class="sxs-lookup"><span data-stu-id="8a50a-165">This is the preferred method.</span></span>

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

<span data-ttu-id="8a50a-166">Зарегистрировав репозиторий Майкрософт в качестве суперпользователя, в дальнейшем вам потребуется лишь использовать `sudo apt-get upgrade powershell` для его обновления.</span><span class="sxs-lookup"><span data-stu-id="8a50a-166">After registering the Microsoft repository once as superuser, from then on, you just need to use `sudo apt-get upgrade powershell` to update it.</span></span>

### <a name="installation-via-direct-download---debian-8"></a><span data-ttu-id="8a50a-167">Установка с помощью прямого скачивания — Debian 8</span><span class="sxs-lookup"><span data-stu-id="8a50a-167">Installation via Direct Download - Debian 8</span></span>

<span data-ttu-id="8a50a-168">Скачайте пакет Debian `powershell_6.1.0-1.debian.8_amd64.deb`</span><span class="sxs-lookup"><span data-stu-id="8a50a-168">Download the Debian package `powershell_6.1.0-1.debian.8_amd64.deb`</span></span>
<span data-ttu-id="8a50a-169">со страницы [выпусков][] на компьютер с Debian.</span><span class="sxs-lookup"><span data-stu-id="8a50a-169">from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="8a50a-170">Затем выполните в терминале следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8a50a-170">Then execute the following in the terminal:</span></span>

```sh
sudo dpkg -i powershell_6.1.0-1.debian.8_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="8a50a-171">Команда `dpkg -i` завершается ошибкой при наличии несопоставленных зависимостей.</span><span class="sxs-lookup"><span data-stu-id="8a50a-171">The `dpkg -i` command fails with unmet dependencies.</span></span>
> <span data-ttu-id="8a50a-172">Следующая команда, `apt-get install -f`, разрешает эти ошибки и завершает настройку пакета PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8a50a-172">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---debian-8"></a><span data-ttu-id="8a50a-173">Удаление — Debian 8</span><span class="sxs-lookup"><span data-stu-id="8a50a-173">Uninstallation - Debian 8</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="debian-9"></a><span data-ttu-id="8a50a-174">Debian 9</span><span class="sxs-lookup"><span data-stu-id="8a50a-174">Debian 9</span></span>

### <a name="installation-via-package-repository---debian-9"></a><span data-ttu-id="8a50a-175">Установка с помощью репозитория пакетов — Debian 9</span><span class="sxs-lookup"><span data-stu-id="8a50a-175">Installation via Package Repository - Debian 9</span></span>

<span data-ttu-id="8a50a-176">Для упрощения установки (и обновления) PowerShell Core для Linux публикуются в репозиториях пакетов.</span><span class="sxs-lookup"><span data-stu-id="8a50a-176">PowerShell Core, for Linux, is published to package repositories for easy installation (and updates).</span></span>
<span data-ttu-id="8a50a-177">Это предпочтительный метод.</span><span class="sxs-lookup"><span data-stu-id="8a50a-177">This is the preferred method.</span></span>

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

<span data-ttu-id="8a50a-178">Зарегистрировав репозиторий Майкрософт в качестве суперпользователя, в дальнейшем вам потребуется лишь использовать `sudo apt-get upgrade powershell` для его обновления.</span><span class="sxs-lookup"><span data-stu-id="8a50a-178">After registering the Microsoft repository once as superuser, from then on, you just need to use `sudo apt-get upgrade powershell` to update it.</span></span>

### <a name="installation-via-direct-download---debian-9"></a><span data-ttu-id="8a50a-179">Установка с помощью прямого скачивания — Debian 9</span><span class="sxs-lookup"><span data-stu-id="8a50a-179">Installation via Direct Download - Debian 9</span></span>

<span data-ttu-id="8a50a-180">Скачайте пакет Debian `powershell_6.1.0-1.debian.9_amd64.deb`</span><span class="sxs-lookup"><span data-stu-id="8a50a-180">Download the Debian package `powershell_6.1.0-1.debian.9_amd64.deb`</span></span>
<span data-ttu-id="8a50a-181">со страницы [выпусков][] на компьютер с Debian.</span><span class="sxs-lookup"><span data-stu-id="8a50a-181">from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="8a50a-182">Затем выполните в терминале следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8a50a-182">Then execute the following in the terminal:</span></span>

```sh
sudo dpkg -i powershell_6.1.0-1.debian.9_amd64.deb
sudo apt-get install -f
```

### <a name="uninstallation---debian-9"></a><span data-ttu-id="8a50a-183">Удаление — Debian 9</span><span class="sxs-lookup"><span data-stu-id="8a50a-183">Uninstallation - Debian 9</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="centos-7"></a><span data-ttu-id="8a50a-184">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="8a50a-184">CentOS 7</span></span>

> [!NOTE]
> <span data-ttu-id="8a50a-185">Этот пакет также работает в Oracle Linux 7.</span><span class="sxs-lookup"><span data-stu-id="8a50a-185">This package also works on Oracle Linux 7.</span></span>

### <a name="installation-via-package-repository-preferred---centos-7"></a><span data-ttu-id="8a50a-186">Установка с помощью репозитория пакетов (рекомендуется) — CentOS 7</span><span class="sxs-lookup"><span data-stu-id="8a50a-186">Installation via Package Repository (preferred) - CentOS 7</span></span>

<span data-ttu-id="8a50a-187">Для упрощения установки (и обновления) PowerShell Core для Linux публикуются в официальных репозиториях Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="8a50a-187">PowerShell Core for Linux is published to official Microsoft repositories for easy installation (and updates).</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="8a50a-188">Зарегистрировав репозиторий Майкрософт в качестве суперпользователя, в дальнейшем вам потребуется лишь использовать `sudo yum update powershell` для обновления PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8a50a-188">After registering the Microsoft repository once as superuser, you just need to use `sudo yum update powershell` to update PowerShell.</span></span>

### <a name="installation-via-direct-download---centos-7"></a><span data-ttu-id="8a50a-189">Установка с помощью прямого скачивания — CentOS 7</span><span class="sxs-lookup"><span data-stu-id="8a50a-189">Installation via Direct Download - CentOS 7</span></span>

<span data-ttu-id="8a50a-190">С помощью [CentOS 7][] скачайте пакет RPM `powershell-6.1.0-1.rhel.7.x86_64.rpm`</span><span class="sxs-lookup"><span data-stu-id="8a50a-190">Using [CentOS 7][], download the RPM package `powershell-6.1.0-1.rhel.7.x86_64.rpm`</span></span>
<span data-ttu-id="8a50a-191">со страницы [выпусков][] на компьютер с CentOS.</span><span class="sxs-lookup"><span data-stu-id="8a50a-191">from the [releases][] page onto the CentOS machine.</span></span>

<span data-ttu-id="8a50a-192">Затем выполните в терминале следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8a50a-192">Then execute the following in the terminal:</span></span>

```sh
sudo yum install powershell-6.1.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="8a50a-193">Кроме того, RPM можно установить без промежуточного скачивания:</span><span class="sxs-lookup"><span data-stu-id="8a50a-193">You can also install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v6.1.0/powershell-6.1.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---centos-7"></a><span data-ttu-id="8a50a-194">Удаление — CentOS 7</span><span class="sxs-lookup"><span data-stu-id="8a50a-194">Uninstallation - CentOS 7</span></span>

```sh
sudo yum remove powershell
```

[CentOS 7]: https://www.centos.org/download/

## <a name="red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="8a50a-196">Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="8a50a-196">Red Hat Enterprise Linux (RHEL) 7</span></span>

### <a name="installation-via-package-repository-preferred---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="8a50a-197">Установка с помощью репозитория пакетов (рекомендуется) — Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="8a50a-197">Installation via Package Repository (preferred) - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="8a50a-198">Для упрощения установки (и обновления) PowerShell Core для Linux публикуются в официальных репозиториях Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="8a50a-198">PowerShell Core for Linux is published to official Microsoft repositories for easy installation (and updates).</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="8a50a-199">Зарегистрировав репозиторий Майкрософт в качестве суперпользователя, в дальнейшем вам потребуется лишь использовать `sudo yum update powershell` для обновления PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8a50a-199">After registering the Microsoft repository once as superuser, you just need to use `sudo yum update powershell` to update PowerShell.</span></span>

### <a name="installation-via-direct-download---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="8a50a-200">Установка с помощью прямого скачивания — Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="8a50a-200">Installation via Direct Download - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="8a50a-201">Скачайте пакет RPM `powershell-6.1.0-1.rhel.7.x86_64.rpm`</span><span class="sxs-lookup"><span data-stu-id="8a50a-201">Download the RPM package `powershell-6.1.0-1.rhel.7.x86_64.rpm`</span></span>
<span data-ttu-id="8a50a-202">со страницы [выпусков][] на компьютер с Red Hat Enterprise Linux.</span><span class="sxs-lookup"><span data-stu-id="8a50a-202">from the [releases][] page onto the Red Hat Enterprise Linux machine.</span></span>

<span data-ttu-id="8a50a-203">Затем выполните в терминале следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8a50a-203">Then execute the following in the terminal:</span></span>

```sh
sudo yum install powershell-6.1.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="8a50a-204">Кроме того, RPM можно установить без промежуточного скачивания:</span><span class="sxs-lookup"><span data-stu-id="8a50a-204">You can also install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v6.1.0/powershell-6.1.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="8a50a-205">Удаление — Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="8a50a-205">Uninstallation - Red Hat Enterprise Linux (RHEL) 7</span></span>

```sh
sudo yum remove powershell
```

## <a name="opensuse"></a><span data-ttu-id="8a50a-206">openSUSE</span><span class="sxs-lookup"><span data-stu-id="8a50a-206">openSUSE</span></span>

### <a name="installation---opensuse-423"></a><span data-ttu-id="8a50a-207">Установка — openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="8a50a-207">Installation - openSUSE 42.3</span></span>

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

### <a name="installation---opensuse-leap-15"></a><span data-ttu-id="8a50a-208">Установка — openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="8a50a-208">Installation - openSUSE Leap 15</span></span>

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

### <a name="uninstallation---opensuse-423-opensuse-leap-15"></a><span data-ttu-id="8a50a-209">Удаление — openSUSE 42.3, openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="8a50a-209">Uninstallation - openSUSE 42.3, openSUSE Leap 15</span></span>

```sh
rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="fedora"></a><span data-ttu-id="8a50a-210">Fedora</span><span class="sxs-lookup"><span data-stu-id="8a50a-210">Fedora</span></span>

> [!NOTE]
> <span data-ttu-id="8a50a-211">Fedora 28 поддерживается только в PowerShell Core 6.1 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="8a50a-211">Fedora 28 is only supported in PowerShell Core 6.1 and newer.</span></span>

### <a name="installation-via-package-repository-preferred---fedora-27-fedora-28"></a><span data-ttu-id="8a50a-212">Установка с помощью репозитория пакетов (рекомендуется) — Fedora 27, Fedora 28</span><span class="sxs-lookup"><span data-stu-id="8a50a-212">Installation via Package Repository (preferred) - Fedora 27, Fedora 28</span></span>

<span data-ttu-id="8a50a-213">Для упрощения установки (и обновления) PowerShell Core для Linux публикуются в официальных репозиториях Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="8a50a-213">PowerShell Core for Linux is published to official Microsoft repositories for easy installation (and updates).</span></span>

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

### <a name="installation-via-direct-download---fedora-27-fedora-28"></a><span data-ttu-id="8a50a-214">Установка с помощью прямого скачивания — Fedora 27, Fedora 28</span><span class="sxs-lookup"><span data-stu-id="8a50a-214">Installation via Direct Download - Fedora 27, Fedora 28</span></span>

<span data-ttu-id="8a50a-215">Скачайте пакет RPM `powershell-6.1.0-1.rhel.7.x86_64.rpm`</span><span class="sxs-lookup"><span data-stu-id="8a50a-215">Download the RPM package `powershell-6.1.0-1.rhel.7.x86_64.rpm`</span></span>
<span data-ttu-id="8a50a-216">со страницы [выпусков][] на компьютер с Fedora.</span><span class="sxs-lookup"><span data-stu-id="8a50a-216">from the [releases][] page onto the Fedora machine.</span></span>

<span data-ttu-id="8a50a-217">Затем выполните в терминале следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8a50a-217">Then execute the following in the terminal:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install powershell-6.1.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="8a50a-218">Кроме того, RPM можно установить без промежуточного скачивания:</span><span class="sxs-lookup"><span data-stu-id="8a50a-218">You can also install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install https://github.com/PowerShell/PowerShell/releases/download/v6.1.0/powershell-6.1.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---fedora-27-fedora-28"></a><span data-ttu-id="8a50a-219">Удаление — Fedora 27, Fedora 28</span><span class="sxs-lookup"><span data-stu-id="8a50a-219">Uninstallation - Fedora 27, Fedora 28</span></span>

```sh
sudo dnf remove powershell
```

## <a name="arch-linux"></a><span data-ttu-id="8a50a-220">Arch Linux</span><span class="sxs-lookup"><span data-stu-id="8a50a-220">Arch Linux</span></span>

> [!NOTE]
> <span data-ttu-id="8a50a-221">Поддержка Arch на этапе эксперимента.</span><span class="sxs-lookup"><span data-stu-id="8a50a-221">Arch support is experimental.</span></span>

<span data-ttu-id="8a50a-222">PowerShell можно получить из пользовательского репозитория [Arch Linux][] (AUR).</span><span class="sxs-lookup"><span data-stu-id="8a50a-222">PowerShell is available from the [Arch Linux][] User Repository (AUR).</span></span>

* <span data-ttu-id="8a50a-223">Его можно скомпилировать с помощью [последнего выпуска с тегами][arch-release].</span><span class="sxs-lookup"><span data-stu-id="8a50a-223">It can be compiled with the [latest tagged release][arch-release]</span></span>
* <span data-ttu-id="8a50a-224">Его можно скомпилировать из [последней фиксации в основной репозиторий][arch-git].</span><span class="sxs-lookup"><span data-stu-id="8a50a-224">It can be compiled from the [latest commit to master][arch-git]</span></span>
* <span data-ttu-id="8a50a-225">Его можно установить с помощью [двоичного файла последнего выпуска][arch-bin].</span><span class="sxs-lookup"><span data-stu-id="8a50a-225">It can be installed using the [latest release binary][arch-bin]</span></span>

<span data-ttu-id="8a50a-226">Пакеты в AUR обслуживаются сообществом — официальная поддержка отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8a50a-226">Packages in the AUR are community maintained - there is no official support.</span></span>

<span data-ttu-id="8a50a-227">Дополнительные сведения об установке пакетов из AUR см. на [вики-сайте Arch Linux](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) или в [DockerFile](https://github.com/PowerShell/PowerShell/blob/master/docker/community/archlinux/Dockerfile) сообщества.</span><span class="sxs-lookup"><span data-stu-id="8a50a-227">For more information on installing packages from the AUR, see the [Arch Linux wiki](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) or the community [DockerFile](https://github.com/PowerShell/PowerShell/blob/master/docker/community/archlinux/Dockerfile).</span></span>

[Arch Linux]: https://www.archlinux.org/download/
[arch-release]: https://aur.archlinux.org/packages/powershell/
[arch-git]: https://aur.archlinux.org/packages/powershell-git/
[arch-bin]: https://aur.archlinux.org/packages/powershell-bin/

## <a name="snap-package"></a><span data-ttu-id="8a50a-229">Snap-пакет</span><span class="sxs-lookup"><span data-stu-id="8a50a-229">Snap Package</span></span>

### <a name="getting-snapd"></a><span data-ttu-id="8a50a-230">Установка Snap</span><span class="sxs-lookup"><span data-stu-id="8a50a-230">Getting snapd</span></span>

<span data-ttu-id="8a50a-231">Утилита `snapd` необходима для запуска snap-пакетов.</span><span class="sxs-lookup"><span data-stu-id="8a50a-231">`snapd` is required to run snaps.</span></span>
<span data-ttu-id="8a50a-232">Чтобы убедиться, что утилита `snapd` установлена, воспользуйтесь [этими инструкциями](https://docs.snapcraft.io/core/install).</span><span class="sxs-lookup"><span data-stu-id="8a50a-232">Use [these instructions](https://docs.snapcraft.io/core/install) to make sure you have `snapd` installed.</span></span>

### <a name="installation-via-snap"></a><span data-ttu-id="8a50a-233">Установка с использованием Snap</span><span class="sxs-lookup"><span data-stu-id="8a50a-233">Installation via Snap</span></span>

<span data-ttu-id="8a50a-234">Для упрощения установки (и обновления) PowerShell Core для Linux опубликован в [хранилище Snap](https://snapcraft.io/store).</span><span class="sxs-lookup"><span data-stu-id="8a50a-234">PowerShell Core, for Linux, is published to the [Snap store](https://snapcraft.io/store) for easy installation (and updates).</span></span>
<span data-ttu-id="8a50a-235">Это предпочтительный метод.</span><span class="sxs-lookup"><span data-stu-id="8a50a-235">This is the preferred method.</span></span>

```sh
# Install PowerShell
sudo snap install powershell --classic

# Start PowerShell
pwsh
```

<span data-ttu-id="8a50a-236">Если вы хотите установить предварительную версию, используйте следующий метод.</span><span class="sxs-lookup"><span data-stu-id="8a50a-236">If you want to install preview version, use following method.</span></span>

```sh
# Install PowerShell
sudo snap install powershell-preview --classic

# Start PowerShell
pwsh-preview
```

<span data-ttu-id="8a50a-237">После установки Snap будет автоматически обновлен, но вы можете активировать обновление с помощью `sudo snap refresh powershell` или `sudo snap refresh powershell-preview`.</span><span class="sxs-lookup"><span data-stu-id="8a50a-237">After installing Snap will automatically upgrade, but you can trigger an upgrade using `sudo snap refresh powershell` or `sudo snap refresh powershell-preview`.</span></span>

### <a name="uninstallation"></a><span data-ttu-id="8a50a-238">Удаление</span><span class="sxs-lookup"><span data-stu-id="8a50a-238">Uninstallation</span></span>

```sh
sudo snap remove powershell
```

<span data-ttu-id="8a50a-239">или</span><span class="sxs-lookup"><span data-stu-id="8a50a-239">or</span></span>

```sh
sudo snap remove powershell-preview
```

## <a name="kali"></a><span data-ttu-id="8a50a-240">Kali</span><span class="sxs-lookup"><span data-stu-id="8a50a-240">Kali</span></span>

### <a name="installation---kali"></a><span data-ttu-id="8a50a-241">Установка — Kali</span><span class="sxs-lookup"><span data-stu-id="8a50a-241">Installation - Kali</span></span>

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

### <a name="uninstallation---kali"></a><span data-ttu-id="8a50a-242">Удаление — Kali</span><span class="sxs-lookup"><span data-stu-id="8a50a-242">Uninstallation - Kali</span></span>

```sh
# Uninstall PowerShell package
apt-get remove -y powershell
```

## <a name="raspbian"></a><span data-ttu-id="8a50a-243">Raspbian</span><span class="sxs-lookup"><span data-stu-id="8a50a-243">Raspbian</span></span>

> [!NOTE]
> <span data-ttu-id="8a50a-244">Поддержка Raspbian на этапе эксперимента.</span><span class="sxs-lookup"><span data-stu-id="8a50a-244">Raspbian support is experimental.</span></span>

<span data-ttu-id="8a50a-245">Сейчас PowerShell поддерживается только в Raspbian Stretch.</span><span class="sxs-lookup"><span data-stu-id="8a50a-245">Currently, PowerShell is only supported on Raspbian Stretch.</span></span>

<span data-ttu-id="8a50a-246">Кроме того, CoreCLR (а соответственно и PowerShell Core) будет работать только на устройствах Pi 2 и Pi 3, в то время как в устройствах наподобие [Pi Zero](https://github.com/dotnet/coreclr/issues/10605) установлены процессоры, поддержка которых не предусмотрена.</span><span class="sxs-lookup"><span data-stu-id="8a50a-246">Also CoreCLR (and thus PowerShell Core) will only work on Pi 2 and Pi 3 devices as other devices, like [Pi Zero](https://github.com/dotnet/coreclr/issues/10605), have an unsupported processor.</span></span>

<span data-ttu-id="8a50a-247">Загрузите [Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) и следуйте [инструкциям по установке](https://www.raspberrypi.org/documentation/installation/installing-images/README.md), чтобы установить его на свой Pi.</span><span class="sxs-lookup"><span data-stu-id="8a50a-247">Download [Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) and follow the [installation instructions](https://www.raspberrypi.org/documentation/installation/installing-images/README.md) to get it onto your Pi.</span></span>

### <a name="installation---raspbian"></a><span data-ttu-id="8a50a-248">Установка — Raspbian</span><span class="sxs-lookup"><span data-stu-id="8a50a-248">Installation - Raspbian</span></span>

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

<span data-ttu-id="8a50a-249">При необходимости можно создать символьную ссылку, позволяющую запустить PowerShell без указания пути к двоичному файлу pwsh</span><span class="sxs-lookup"><span data-stu-id="8a50a-249">Optionally you can create a symbolic link to be able to start PowerShell without specifying path to the "pwsh" binary</span></span>

```sh
# Start PowerShell from bash with sudo to create a symbolic link
sudo ~/powershell/pwsh -c New-Item -ItemType SymbolicLink -Path "/usr/bin/pwsh" -Target "\$PSHOME/pwsh" -Force

# alternatively you can run following to create a symbolic link
# sudo ln -s ~/powershell/pwsh /usr/bin/pwsh

# Now to start PowerShell you can just run "pwsh"
```

### <a name="uninstallation---raspbian"></a><span data-ttu-id="8a50a-250">Удаление — Raspbian</span><span class="sxs-lookup"><span data-stu-id="8a50a-250">Uninstallation - Raspbian</span></span>

```sh
rm -rf ~/powershell
```

## <a name="binary-archives"></a><span data-ttu-id="8a50a-251">Архивы двоичных файлов</span><span class="sxs-lookup"><span data-stu-id="8a50a-251">Binary Archives</span></span>

<span data-ttu-id="8a50a-252">Для поддержки расширенных сценариев развертывания на платформах Linux доступны архивы `tar.gz` двоичных файлов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8a50a-252">PowerShell binary `tar.gz` archives are provided for Linux platforms to enable advanced deployment scenarios.</span></span>

### <a name="dependencies"></a><span data-ttu-id="8a50a-253">Зависимости</span><span class="sxs-lookup"><span data-stu-id="8a50a-253">Dependencies</span></span>

<span data-ttu-id="8a50a-254">PowerShell создает переносимые двоичные файлы для всех дистрибутивов Linux.</span><span class="sxs-lookup"><span data-stu-id="8a50a-254">PowerShell builds portable binaries for all Linux distributions.</span></span>
<span data-ttu-id="8a50a-255">Однако среда выполнения .NET Core требует различные зависимости для разных дистрибутивов, и поэтому то же самое делает и PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8a50a-255">But .NET Core runtime requires different dependencies on different distributions, and hence PowerShell does the same.</span></span>

<span data-ttu-id="8a50a-256">На следующей диаграмме показаны официально поддерживаемые зависимости .NET Core 2.0 для различных дистрибутивов Linux.</span><span class="sxs-lookup"><span data-stu-id="8a50a-256">The following chart shows the .NET Core 2.0 dependencies that are officially supported on different Linux distributions.</span></span>

| <span data-ttu-id="8a50a-257">ОС</span><span class="sxs-lookup"><span data-stu-id="8a50a-257">OS</span></span>                 | <span data-ttu-id="8a50a-258">Зависимости</span><span class="sxs-lookup"><span data-stu-id="8a50a-258">Dependencies</span></span> |
| ------------------ | ------------ |
| <span data-ttu-id="8a50a-259">Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="8a50a-259">Ubuntu 14.04</span></span>       | <span data-ttu-id="8a50a-260">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="8a50a-260">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="8a50a-261">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span><span class="sxs-lookup"><span data-stu-id="8a50a-261">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span></span> |
| <span data-ttu-id="8a50a-262">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="8a50a-262">Ubuntu 16.04</span></span>       | <span data-ttu-id="8a50a-263">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="8a50a-263">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="8a50a-264">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu55</span><span class="sxs-lookup"><span data-stu-id="8a50a-264">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu55</span></span> |
| <span data-ttu-id="8a50a-265">Ubuntu 17.10</span><span class="sxs-lookup"><span data-stu-id="8a50a-265">Ubuntu 17.10</span></span>       | <span data-ttu-id="8a50a-266">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="8a50a-266">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="8a50a-267">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu57</span><span class="sxs-lookup"><span data-stu-id="8a50a-267">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu57</span></span> |
| <span data-ttu-id="8a50a-268">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="8a50a-268">Ubuntu 18.04</span></span>       | <span data-ttu-id="8a50a-269">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="8a50a-269">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="8a50a-270">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu60</span><span class="sxs-lookup"><span data-stu-id="8a50a-270">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu60</span></span> |
| <span data-ttu-id="8a50a-271">Debian 8 (Jessie)</span><span class="sxs-lookup"><span data-stu-id="8a50a-271">Debian 8 (Jessie)</span></span>  | <span data-ttu-id="8a50a-272">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="8a50a-272">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="8a50a-273">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span><span class="sxs-lookup"><span data-stu-id="8a50a-273">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span></span> |
| <span data-ttu-id="8a50a-274">Debian 9 (Stretch)</span><span class="sxs-lookup"><span data-stu-id="8a50a-274">Debian 9 (Stretch)</span></span> | <span data-ttu-id="8a50a-275">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="8a50a-275">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="8a50a-276">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.2, libicu57</span><span class="sxs-lookup"><span data-stu-id="8a50a-276">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.2, libicu57</span></span> |
| <span data-ttu-id="8a50a-277">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="8a50a-277">CentOS 7</span></span> <br> <span data-ttu-id="8a50a-278">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="8a50a-278">Oracle Linux 7</span></span> <br> <span data-ttu-id="8a50a-279">RHEL 7</span><span class="sxs-lookup"><span data-stu-id="8a50a-279">RHEL 7</span></span> | <span data-ttu-id="8a50a-280">libunwind, libcurl, openssl-libs, libicu</span><span class="sxs-lookup"><span data-stu-id="8a50a-280">libunwind, libcurl, openssl-libs, libicu</span></span> |
| <span data-ttu-id="8a50a-281">openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="8a50a-281">openSUSE 42.3</span></span> | <span data-ttu-id="8a50a-282">libcurl4, libopenssl1_0_0, libicu52_1</span><span class="sxs-lookup"><span data-stu-id="8a50a-282">libcurl4, libopenssl1_0_0, libicu52_1</span></span> |
| <span data-ttu-id="8a50a-283">openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="8a50a-283">openSUSE Leap 15</span></span> | <span data-ttu-id="8a50a-284">libcurl4, libopenssl1_0_0, libicu60_2</span><span class="sxs-lookup"><span data-stu-id="8a50a-284">libcurl4, libopenssl1_0_0, libicu60_2</span></span> |
| <span data-ttu-id="8a50a-285">Fedora 27</span><span class="sxs-lookup"><span data-stu-id="8a50a-285">Fedora 27</span></span> <br> <span data-ttu-id="8a50a-286">Fedora 28</span><span class="sxs-lookup"><span data-stu-id="8a50a-286">Fedora 28</span></span> | <span data-ttu-id="8a50a-287">libunwind, libcurl, openssl-libs, libicu, compat-openssl10</span><span class="sxs-lookup"><span data-stu-id="8a50a-287">libunwind, libcurl, openssl-libs, libicu, compat-openssl10</span></span> |

<span data-ttu-id="8a50a-288">Чтобы развернуть двоичные файлы PowerShell в дистрибутивах Linux, для которых официальная поддержка не предусмотрена, необходимо специально установить необходимые пакеты, чтобы удовлетворить всем требованиям по зависимостям для целевой ОС.</span><span class="sxs-lookup"><span data-stu-id="8a50a-288">To deploy PowerShell binaries on Linux distributions that are not officially supported, you need to install the necessary dependencies for the target OS in separate steps.</span></span>
<span data-ttu-id="8a50a-289">Например, наш [Amazon Linux dockerfile][amazon-dockerfile] сначала устанавливает зависимости, а затем извлекает архив Linux `tar.gz`.</span><span class="sxs-lookup"><span data-stu-id="8a50a-289">For example, our [Amazon Linux dockerfile][amazon-dockerfile] installs dependencies first, and then extracts the Linux `tar.gz` archive.</span></span>

[amazon-dockerfile]: https://github.com/PowerShell/PowerShell/blob/master/docker/community/amazonlinux/Dockerfile

### <a name="installation---binary-archives"></a><span data-ttu-id="8a50a-290">Установка — архивы двоичных файлов</span><span class="sxs-lookup"><span data-stu-id="8a50a-290">Installation - Binary Archives</span></span>

#### <a name="linux"></a><span data-ttu-id="8a50a-291">Linux</span><span class="sxs-lookup"><span data-stu-id="8a50a-291">Linux</span></span>

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

### <a name="uninstalling-binary-archives"></a><span data-ttu-id="8a50a-292">Удаление архивов двоичных файлов</span><span class="sxs-lookup"><span data-stu-id="8a50a-292">Uninstalling binary archives</span></span>

```sh
sudo rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="paths"></a><span data-ttu-id="8a50a-293">Пути</span><span class="sxs-lookup"><span data-stu-id="8a50a-293">Paths</span></span>

* <span data-ttu-id="8a50a-294">`$PSHOME` имеет значение `/opt/microsoft/powershell/6.1.0/`.</span><span class="sxs-lookup"><span data-stu-id="8a50a-294">`$PSHOME` is `/opt/microsoft/powershell/6.1.0/`</span></span>
* <span data-ttu-id="8a50a-295">Профили пользователей будут считаны из `~/.config/powershell/profile.ps1`.</span><span class="sxs-lookup"><span data-stu-id="8a50a-295">User profiles will be read from `~/.config/powershell/profile.ps1`</span></span>
* <span data-ttu-id="8a50a-296">Профили по умолчанию будут считаны из `$PSHOME/profile.ps1`.</span><span class="sxs-lookup"><span data-stu-id="8a50a-296">Default profiles will be read from `$PSHOME/profile.ps1`</span></span>
* <span data-ttu-id="8a50a-297">Модули пользователей будут считаны из `~/.local/share/powershell/Modules`.</span><span class="sxs-lookup"><span data-stu-id="8a50a-297">User modules will be read from `~/.local/share/powershell/Modules`</span></span>
* <span data-ttu-id="8a50a-298">Общие модули будут считаны из `/usr/local/share/powershell/Modules`.</span><span class="sxs-lookup"><span data-stu-id="8a50a-298">Shared modules will be read from `/usr/local/share/powershell/Modules`</span></span>
* <span data-ttu-id="8a50a-299">Модули по умолчанию будут считаны из `$PSHOME/Modules`.</span><span class="sxs-lookup"><span data-stu-id="8a50a-299">Default modules will be read from `$PSHOME/Modules`</span></span>
* <span data-ttu-id="8a50a-300">Журнал PSReadline будет записан в `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`.</span><span class="sxs-lookup"><span data-stu-id="8a50a-300">PSReadline history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="8a50a-301">Профили учитывают конфигурацию PowerShell для отдельных узлов, поэтому профили конкретных узлов по умолчанию находятся в `Microsoft.PowerShell_profile.ps1` в тех же расположениях.</span><span class="sxs-lookup"><span data-stu-id="8a50a-301">The profiles respect PowerShell's per-host configuration, so the default host-specific profiles exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="8a50a-302">PowerShell отвечает требованиям [спецификации каталога размещения файлов, связанных со средой настольной графической среды (X-сервера), стандартизированного XDG (X Desktop Group)][xdg-bds] в Linux.</span><span class="sxs-lookup"><span data-stu-id="8a50a-302">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on Linux.</span></span>

[выпусков]: https://github.com/PowerShell/PowerShell/releases/latest
[releases]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
