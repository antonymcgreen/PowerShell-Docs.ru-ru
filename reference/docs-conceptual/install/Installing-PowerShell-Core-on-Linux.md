---
title: Установка PowerShell Core в Linux
description: Сведения об установке PowerShell Core в различных дистрибутивах Linux
ms.date: 07/19/2019
ms.openlocfilehash: 9e92958eb6d9c7a6a76331103f42ecadeab978c1
ms.sourcegitcommit: 0e4c69d8b5cf71431592fe41da816dec9b70f1f9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/09/2019
ms.locfileid: "74953812"
---
# <a name="installing-powershell-core-on-linux"></a><span data-ttu-id="f50c5-103">Установка PowerShell Core в Linux</span><span class="sxs-lookup"><span data-stu-id="f50c5-103">Installing PowerShell Core on Linux</span></span>

<span data-ttu-id="f50c5-104">Поддерживает [Ubuntu 16.04][u16], [Ubuntu 18.04][u1804], [Ubuntu 18.10][u1810], [Ubuntu 19.04][u1904], [Debian 8][deb8], [Debian 9][deb9], [Debian 10][deb10], [CentOS 7][cos], [Red Hat Enterprise Linux (RHEL) 7][rhel7], [openSUSE 42.3][opensuse], [openSUSE Leap 15][opensuse], [Fedora 27][fedora], [Fedora 28][fedora] и [Arch Linux][arch].</span><span class="sxs-lookup"><span data-stu-id="f50c5-104">Supports [Ubuntu 16.04][u16], [Ubuntu 18.04][u1804], [Ubuntu 18.10][u1810], [Ubuntu 19.04][u1904], [Debian 8][deb8], [Debian 9][deb9], [Debian 10][deb10], [CentOS 7][cos], [Red Hat Enterprise Linux (RHEL) 7][rhel7], [openSUSE 42.3][opensuse], [openSUSE Leap 15][opensuse], [Fedora 27][fedora], [Fedora 28][fedora], and [Arch Linux][arch].</span></span>

<span data-ttu-id="f50c5-105">Для дистрибутивов Linux без официальной поддержки попробуйте установить PowerShell с помощью [соответствующего Snap-пакета][snap].</span><span class="sxs-lookup"><span data-stu-id="f50c5-105">For Linux distributions that aren't officially supported, you can try to install PowerShell using the [PowerShell Snap Package][snap].</span></span> <span data-ttu-id="f50c5-106">Можно также попытаться развернуть двоичные файлы PowerShell напрямую с помощью [архива`tar.gz`][tar] Linux, но при этом нужно отдельно настроить необходимые зависимости с учетом операционной системы.</span><span class="sxs-lookup"><span data-stu-id="f50c5-106">You can also try deploying PowerShell binaries directly using the Linux [`tar.gz` archive][tar], but you would need to set up the necessary dependencies based on the OS in separate steps.</span></span>

<span data-ttu-id="f50c5-107">Все пакеты доступны на нашей странице [выпусками][] GitHub.</span><span class="sxs-lookup"><span data-stu-id="f50c5-107">All packages are available on our GitHub [releases][] page.</span></span> <span data-ttu-id="f50c5-108">После установки пакета запустите `pwsh` из терминала.</span><span class="sxs-lookup"><span data-stu-id="f50c5-108">After the package is installed, run `pwsh` from a terminal.</span></span> <span data-ttu-id="f50c5-109">Запустите `pwsh-preview`, если вы установили [выпуск предварительной версии](#installing-preview-releases).</span><span class="sxs-lookup"><span data-stu-id="f50c5-109">Run `pwsh-preview` if you installed a [Preview release](#installing-preview-releases).</span></span>

[u16]: #ubuntu-1604
[u1804]: #ubuntu-1804
[u1810]: #ubuntu-1810
[u1904]: #ubuntu-1904
[deb8]: #debian-8
[deb9]: #debian-9
[deb10]: #debian-10
[cos]: #centos-7
[rhel7]: #red-hat-enterprise-linux-rhel-7
[opensuse]: #opensuse
[fedora]: #fedora
[arch]: #arch-linux
[snap]: #snap-package
[tar]: #binary-archives

> [!TIP]
> <span data-ttu-id="f50c5-110">Если вы уже установили [пакет SDK для .NET Core](/dotnet/core/sdk), установите PowerShell как [глобальный инструмент .NET](/dotnet/core/tools/global-tools).</span><span class="sxs-lookup"><span data-stu-id="f50c5-110">If you already have the [.NET Core SDK](/dotnet/core/sdk) installed, it’s easy to install PowerShell as a [.NET Global tool](/dotnet/core/tools/global-tools).</span></span>
>
> ```
> dotnet tool install --global PowerShell
> ```

## <a name="installing-preview-releases"></a><span data-ttu-id="f50c5-111">Установка предварительных выпусков</span><span class="sxs-lookup"><span data-stu-id="f50c5-111">Installing Preview Releases</span></span>

<span data-ttu-id="f50c5-112">При установке предварительной версии PowerShell Core для Linux с помощью репозитория пакетов имя пакета меняется с `powershell` на `powershell-preview`.</span><span class="sxs-lookup"><span data-stu-id="f50c5-112">When installing a PowerShell Core Preview release for Linux via a Package Repository, the package name changes from `powershell` to `powershell-preview`.</span></span>

<span data-ttu-id="f50c5-113">При установке с помощью прямого скачивания изменяется только имя файла.</span><span class="sxs-lookup"><span data-stu-id="f50c5-113">Installing via direct download doesn't change, other than the file name.</span></span>

<span data-ttu-id="f50c5-114">В следующей таблице приведены команды для установки пакетов стабильной и предварительной версий с помощью различных диспетчеров пакетов:</span><span class="sxs-lookup"><span data-stu-id="f50c5-114">The following table contains the commands to install the stable and preview packages using the various package managers:</span></span>

|<span data-ttu-id="f50c5-115">Дистрибутивы</span><span class="sxs-lookup"><span data-stu-id="f50c5-115">Distribution(s)</span></span>|<span data-ttu-id="f50c5-116">Команда стабильной версии</span><span class="sxs-lookup"><span data-stu-id="f50c5-116">Stable Command</span></span> | <span data-ttu-id="f50c5-117">Команда предварительной версии</span><span class="sxs-lookup"><span data-stu-id="f50c5-117">Preview Command</span></span> |
|---------------|---------------|-----------------|
| <span data-ttu-id="f50c5-118">Ubuntu, Debian</span><span class="sxs-lookup"><span data-stu-id="f50c5-118">Ubuntu, Debian</span></span> |`sudo apt-get install -y powershell`| `sudo apt-get install -y powershell-preview`|
| <span data-ttu-id="f50c5-119">CentOS, RedHat</span><span class="sxs-lookup"><span data-stu-id="f50c5-119">CentOS, RedHat</span></span> |`sudo yum install -y powershell` | `sudo yum install -y powershell-preview`|
| <span data-ttu-id="f50c5-120">Fedora</span><span class="sxs-lookup"><span data-stu-id="f50c5-120">Fedora</span></span>   |`sudo dnf install -y powershell` | `sudo dnf install -y powershell-preview`|

## <a name="ubuntu-1604"></a><span data-ttu-id="f50c5-121">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="f50c5-121">Ubuntu 16.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1604"></a><span data-ttu-id="f50c5-122">Установка с помощью репозитория пакетов — Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="f50c5-122">Installation via Package Repository - Ubuntu 16.04</span></span>

<span data-ttu-id="f50c5-123">Чтобы упростить установку и обновление, PowerShell Core для Linux публикуется в репозиториях пакетов.</span><span class="sxs-lookup"><span data-stu-id="f50c5-123">PowerShell Core for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="f50c5-124">Предпочтительный метод выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f50c5-124">The preferred method is as follows:</span></span>

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

<span data-ttu-id="f50c5-125">В качестве суперпользователя однократно зарегистрируйте репозиторий Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f50c5-125">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="f50c5-126">После регистрации можно обновить PowerShell с помощью `sudo apt-get upgrade powershell`.</span><span class="sxs-lookup"><span data-stu-id="f50c5-126">After registration, you can update PowerShell with `sudo apt-get upgrade powershell`.</span></span>

### <a name="installation-via-direct-download---ubuntu-1604"></a><span data-ttu-id="f50c5-127">Установка с помощью прямого скачивания — Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="f50c5-127">Installation via Direct Download - Ubuntu 16.04</span></span>

<span data-ttu-id="f50c5-128">Скачайте пакет Debian `powershell_6.2.0-1.ubuntu.16.04_amd64.deb` со страницы [выпусками][] на компьютер с Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="f50c5-128">Download the Debian package `powershell_6.2.0-1.ubuntu.16.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="f50c5-129">Затем выполните в терминале следующие команды:</span><span class="sxs-lookup"><span data-stu-id="f50c5-129">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell_6.2.0-1.ubuntu.16.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="f50c5-130">Команда `dpkg -i` завершается ошибкой при наличии несопоставленных зависимостей.</span><span class="sxs-lookup"><span data-stu-id="f50c5-130">The `dpkg -i` command fails with unmet dependencies.</span></span> <span data-ttu-id="f50c5-131">Следующая команда, `apt-get install -f`, разрешает эти ошибки и завершает настройку пакета PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f50c5-131">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1604"></a><span data-ttu-id="f50c5-132">Удаление — Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="f50c5-132">Uninstallation - Ubuntu 16.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1804"></a><span data-ttu-id="f50c5-133">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="f50c5-133">Ubuntu 18.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1804"></a><span data-ttu-id="f50c5-134">Установка с помощью репозитория пакетов — Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="f50c5-134">Installation via Package Repository - Ubuntu 18.04</span></span>

<span data-ttu-id="f50c5-135">Чтобы упростить установку и обновление, PowerShell Core для Linux публикуется в репозиториях пакетов.</span><span class="sxs-lookup"><span data-stu-id="f50c5-135">PowerShell Core for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="f50c5-136">Предпочтительный метод выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f50c5-136">The preferred method is as follows:</span></span>

```sh
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

<span data-ttu-id="f50c5-137">В качестве суперпользователя однократно зарегистрируйте репозиторий Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f50c5-137">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="f50c5-138">После регистрации можно обновить PowerShell с помощью `sudo apt-get upgrade powershell`.</span><span class="sxs-lookup"><span data-stu-id="f50c5-138">After registration, you can update PowerShell with `sudo apt-get upgrade powershell`.</span></span>

### <a name="installation-via-direct-download---ubuntu-1804"></a><span data-ttu-id="f50c5-139">Установка с помощью прямого скачивания — Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="f50c5-139">Installation via Direct Download - Ubuntu 18.04</span></span>

<span data-ttu-id="f50c5-140">Скачайте пакет Debian `powershell_6.2.0-1.ubuntu.18.04_amd64.deb` со страницы [выпусками][] на компьютер с Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="f50c5-140">Download the Debian package `powershell_6.2.0-1.ubuntu.18.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="f50c5-141">Затем выполните в терминале следующие команды:</span><span class="sxs-lookup"><span data-stu-id="f50c5-141">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell_6.2.0-1.ubuntu.18.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="f50c5-142">Команда `dpkg -i` завершается ошибкой при наличии несопоставленных зависимостей.</span><span class="sxs-lookup"><span data-stu-id="f50c5-142">The `dpkg -i` command fails with unmet dependencies.</span></span> <span data-ttu-id="f50c5-143">Следующая команда, `apt-get install -f`, разрешает эти ошибки и завершает настройку пакета PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f50c5-143">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1804"></a><span data-ttu-id="f50c5-144">Удаление — Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="f50c5-144">Uninstallation - Ubuntu 18.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1810"></a><span data-ttu-id="f50c5-145">Ubuntu 18.10</span><span class="sxs-lookup"><span data-stu-id="f50c5-145">Ubuntu 18.10</span></span>

<span data-ttu-id="f50c5-146">Поддерживается только установка с помощью `snapd`.</span><span class="sxs-lookup"><span data-stu-id="f50c5-146">Installation is supported via `snapd`.</span></span> <span data-ttu-id="f50c5-147">Инструкции см. в разделе о [snap-пакете][snap].</span><span class="sxs-lookup"><span data-stu-id="f50c5-147">For instructions, see [Snap Package][snap].</span></span>

> [!NOTE]
> <span data-ttu-id="f50c5-148">Ubuntu 18.10 — [промежуточный выпуск](https://www.ubuntu.com/about/release-cycle), который [поддерживается сообществом](../powershell-support-lifecycle.md).</span><span class="sxs-lookup"><span data-stu-id="f50c5-148">Ubuntu 18.10 is an [interim release](https://www.ubuntu.com/about/release-cycle) that's [community supported](../powershell-support-lifecycle.md).</span></span>

## <a name="ubuntu-1904"></a><span data-ttu-id="f50c5-149">Ubuntu 19.04</span><span class="sxs-lookup"><span data-stu-id="f50c5-149">Ubuntu 19.04</span></span>

<span data-ttu-id="f50c5-150">Поддерживается только установка с помощью `snapd`.</span><span class="sxs-lookup"><span data-stu-id="f50c5-150">Installation is supported via `snapd`.</span></span> <span data-ttu-id="f50c5-151">Инструкции см. в разделе о [snap-пакете][snap].</span><span class="sxs-lookup"><span data-stu-id="f50c5-151">For instructions, see [Snap Package][snap].</span></span>

> [!NOTE]
> <span data-ttu-id="f50c5-152">Ubuntu 19.04 — [промежуточный выпуск](https://www.ubuntu.com/about/release-cycle), который [поддерживается сообществом](../powershell-support-lifecycle.md).</span><span class="sxs-lookup"><span data-stu-id="f50c5-152">Ubuntu 19.04 is an [interim release](https://www.ubuntu.com/about/release-cycle) that's [community supported](../powershell-support-lifecycle.md).</span></span>

## <a name="debian-8"></a><span data-ttu-id="f50c5-153">Debian 8</span><span class="sxs-lookup"><span data-stu-id="f50c5-153">Debian 8</span></span>

### <a name="installation-via-package-repository---debian-8"></a><span data-ttu-id="f50c5-154">Установка с помощью репозитория пакетов — Debian 8</span><span class="sxs-lookup"><span data-stu-id="f50c5-154">Installation via Package Repository - Debian 8</span></span>

<span data-ttu-id="f50c5-155">Чтобы упростить установку и обновление, PowerShell Core для Linux публикуется в репозиториях пакетов.</span><span class="sxs-lookup"><span data-stu-id="f50c5-155">PowerShell Core for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="f50c5-156">Предпочтительный метод выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f50c5-156">The preferred method is as follows:</span></span>

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

<span data-ttu-id="f50c5-157">В качестве суперпользователя однократно зарегистрируйте репозиторий Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f50c5-157">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="f50c5-158">После регистрации можно обновить PowerShell с помощью `sudo apt-get upgrade powershell`.</span><span class="sxs-lookup"><span data-stu-id="f50c5-158">After registration, you can update PowerShell with `sudo apt-get upgrade powershell`.</span></span>

## <a name="debian-9"></a><span data-ttu-id="f50c5-159">Debian 9</span><span class="sxs-lookup"><span data-stu-id="f50c5-159">Debian 9</span></span>

### <a name="installation-via-package-repository---debian-9"></a><span data-ttu-id="f50c5-160">Установка с помощью репозитория пакетов — Debian 9</span><span class="sxs-lookup"><span data-stu-id="f50c5-160">Installation via Package Repository - Debian 9</span></span>

<span data-ttu-id="f50c5-161">Чтобы упростить установку и обновление, PowerShell Core для Linux публикуется в репозиториях пакетов.</span><span class="sxs-lookup"><span data-stu-id="f50c5-161">PowerShell Core for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="f50c5-162">Предпочтительный метод выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f50c5-162">The preferred method is as follows:</span></span>

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

<span data-ttu-id="f50c5-163">В качестве суперпользователя однократно зарегистрируйте репозиторий Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f50c5-163">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="f50c5-164">После регистрации можно обновить PowerShell с помощью `sudo apt-get upgrade powershell`.</span><span class="sxs-lookup"><span data-stu-id="f50c5-164">After registration, you can update PowerShell with `sudo apt-get upgrade powershell`.</span></span>

### <a name="installation-via-direct-download---debian-9"></a><span data-ttu-id="f50c5-165">Установка с помощью прямого скачивания — Debian 9</span><span class="sxs-lookup"><span data-stu-id="f50c5-165">Installation via Direct Download - Debian 9</span></span>

<span data-ttu-id="f50c5-166">Скачайте пакет Debian `powershell_6.2.0-1.debian.9_amd64.deb` со страницы [выпусками][] на компьютер с Debian.</span><span class="sxs-lookup"><span data-stu-id="f50c5-166">Download the Debian package `powershell_6.2.0-1.debian.9_amd64.deb` from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="f50c5-167">Затем выполните в терминале следующие команды:</span><span class="sxs-lookup"><span data-stu-id="f50c5-167">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell_6.2.0-1.debian.9_amd64.deb
sudo apt-get install -f
```

### <a name="uninstallation---debian-9"></a><span data-ttu-id="f50c5-168">Удаление — Debian 9</span><span class="sxs-lookup"><span data-stu-id="f50c5-168">Uninstallation - Debian 9</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="debian-10"></a><span data-ttu-id="f50c5-169">Debian 10</span><span class="sxs-lookup"><span data-stu-id="f50c5-169">Debian 10</span></span>

> [!NOTE]
> <span data-ttu-id="f50c5-170">Debian 10 поддерживается только в PowerShell 7.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="f50c5-170">Debian 10 is only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-direct-download---debian-10"></a><span data-ttu-id="f50c5-171">Установка с помощью прямого скачивания — Debian 10</span><span class="sxs-lookup"><span data-stu-id="f50c5-171">Installation via Direct Download - Debian 10</span></span>

<span data-ttu-id="f50c5-172">Скачайте пакет tar.gz `powershell_7.0.0-preview-7-linux-x64.tar.gz` на странице с [выпусками][] на компьютер с Debian.</span><span class="sxs-lookup"><span data-stu-id="f50c5-172">Download the tar.gz package `powershell_7.0.0-preview-7-linux-x64.tar.gz` from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="f50c5-173">Затем выполните в терминале следующие команды:</span><span class="sxs-lookup"><span data-stu-id="f50c5-173">Then, in the terminal, execute the following commands:</span></span>

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
curl -L https://github.com/PowerShell/PowerShell/releases/download/v7.0.0-preview.4/powershell-7.0.0-preview.4-linux-x64.tar.gz -o /tmp/powershell.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /opt/microsoft/powershell/7-preview

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/7-preview

# Set execute permissions
sudo chmod +x /opt/microsoft/powershell/7-preview/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /opt/microsoft/powershell/7-preview/pwsh /usr/bin/pwsh-preview

# Start PowerShell
pwsh-preview
```

## <a name="alpine-39-and-310"></a><span data-ttu-id="f50c5-174">Alpine 3.9 и 3.10</span><span class="sxs-lookup"><span data-stu-id="f50c5-174">Alpine 3.9 and 3.10</span></span>

> [!NOTE]
> <span data-ttu-id="f50c5-175">Alpine 3.9 и 3.10 поддерживается только в PowerShell 7.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="f50c5-175">Alpine 3.9 and 3.10 are only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-direct-download---alpine-39-and-310"></a><span data-ttu-id="f50c5-176">Установка с помощью прямого скачивания — Alpine 3.9 и 3.10</span><span class="sxs-lookup"><span data-stu-id="f50c5-176">Installation via Direct Download - Alpine 3.9 and 3.10</span></span>

<span data-ttu-id="f50c5-177">Скачайте пакет tar.gz `powershell_7.0.0-preview-7-linux-x64.tar.gz` на странице с [выпусками][] на компьютер с Alpine.</span><span class="sxs-lookup"><span data-stu-id="f50c5-177">Download the tar.gz package `powershell_7.0.0-preview-7-linux-x64.tar.gz` from the [releases][] page onto the Alpine machine.</span></span>

<span data-ttu-id="f50c5-178">Затем выполните в терминале следующие команды:</span><span class="sxs-lookup"><span data-stu-id="f50c5-178">Then, in the terminal, execute the following commands:</span></span>

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
curl -L https://github.com/PowerShell/PowerShell/releases/download/v7.0.0-preview.4/powershell-7.0.0-preview.4-linux-alpine-x64.tar.gz -o /tmp/powershell.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /opt/microsoft/powershell/7-preview

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/7-preview

# Set execute permissions
sudo chmod +x /opt/microsoft/powershell/7-preview/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /opt/microsoft/powershell/7-preview/pwsh /usr/bin/pwsh-preview

# Start PowerShell
pwsh-preview
```

## <a name="centos-7"></a><span data-ttu-id="f50c5-179">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="f50c5-179">CentOS 7</span></span>

> [!NOTE]
> <span data-ttu-id="f50c5-180">Этот пакет работает в Oracle Linux 7.</span><span class="sxs-lookup"><span data-stu-id="f50c5-180">This package works on Oracle Linux 7.</span></span>

### <a name="installation-via-package-repository-preferred---centos-7"></a><span data-ttu-id="f50c5-181">Установка с помощью репозитория пакетов (рекомендуется) — CentOS 7</span><span class="sxs-lookup"><span data-stu-id="f50c5-181">Installation via Package Repository (preferred) - CentOS 7</span></span>

<span data-ttu-id="f50c5-182">Чтобы упростить установку и обновление, PowerShell Core для Linux публикуется в официальных репозиториях Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f50c5-182">PowerShell Core for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="f50c5-183">В качестве суперпользователя однократно зарегистрируйте репозиторий Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f50c5-183">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="f50c5-184">После регистрации можно обновить PowerShell с помощью `sudo yum update powershell`.</span><span class="sxs-lookup"><span data-stu-id="f50c5-184">After registration, you can update PowerShell with `sudo yum update powershell`.</span></span>

### <a name="installation-via-direct-download---centos-7"></a><span data-ttu-id="f50c5-185">Установка с помощью прямого скачивания — CentOS 7</span><span class="sxs-lookup"><span data-stu-id="f50c5-185">Installation via Direct Download - CentOS 7</span></span>

<span data-ttu-id="f50c5-186">Используя [CentOS 7][], скачайте пакет RPM `powershell-6.2.0-1.rhel.7.x86_64.rpm` со страницы [выпусками][] на компьютер с CentOS.</span><span class="sxs-lookup"><span data-stu-id="f50c5-186">Using [CentOS 7][], download the RPM package `powershell-6.2.0-1.rhel.7.x86_64.rpm` from the [releases][] page onto the CentOS machine.</span></span>

<span data-ttu-id="f50c5-187">Затем выполните в терминале следующие команды:</span><span class="sxs-lookup"><span data-stu-id="f50c5-187">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo yum install powershell-6.2.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="f50c5-188">RPM можно установить без промежуточного скачивания:</span><span class="sxs-lookup"><span data-stu-id="f50c5-188">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v6.2.0/powershell-6.2.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---centos-7"></a><span data-ttu-id="f50c5-189">Удаление — CentOS 7</span><span class="sxs-lookup"><span data-stu-id="f50c5-189">Uninstallation - CentOS 7</span></span>

```sh
sudo yum remove powershell
```

[CentOS 7]: https://www.centos.org/download/

## <a name="red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="f50c5-191">Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="f50c5-191">Red Hat Enterprise Linux (RHEL) 7</span></span>

### <a name="installation-via-package-repository-preferred---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="f50c5-192">Установка с помощью репозитория пакетов (рекомендуется) — Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="f50c5-192">Installation via Package Repository (preferred) - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="f50c5-193">Чтобы упростить установку и обновление, PowerShell Core для Linux публикуется в официальных репозиториях Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f50c5-193">PowerShell Core for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="f50c5-194">В качестве суперпользователя однократно зарегистрируйте репозиторий Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f50c5-194">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="f50c5-195">После регистрации можно обновить PowerShell с помощью `sudo yum update powershell`.</span><span class="sxs-lookup"><span data-stu-id="f50c5-195">After registration, you can update PowerShell with `sudo yum update powershell`.</span></span>

### <a name="installation-via-direct-download---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="f50c5-196">Установка с помощью прямого скачивания — Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="f50c5-196">Installation via Direct Download - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="f50c5-197">Скачайте пакет RPM `powershell-6.2.0-1.rhel.7.x86_64.rpm` со страницы [выпусками][] на компьютер с Red Hat Enterprise Linux.</span><span class="sxs-lookup"><span data-stu-id="f50c5-197">Download the RPM package `powershell-6.2.0-1.rhel.7.x86_64.rpm` from the [releases][] page onto the Red Hat Enterprise Linux machine.</span></span>

<span data-ttu-id="f50c5-198">Затем выполните в терминале следующие команды:</span><span class="sxs-lookup"><span data-stu-id="f50c5-198">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo yum install powershell-6.2.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="f50c5-199">RPM можно установить без промежуточного скачивания:</span><span class="sxs-lookup"><span data-stu-id="f50c5-199">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v6.2.0/powershell-6.2.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="f50c5-200">Удаление — Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="f50c5-200">Uninstallation - Red Hat Enterprise Linux (RHEL) 7</span></span>

```sh
sudo yum remove powershell
```

## <a name="opensuse"></a><span data-ttu-id="f50c5-201">openSUSE</span><span class="sxs-lookup"><span data-stu-id="f50c5-201">openSUSE</span></span>

### <a name="installation---opensuse-423"></a><span data-ttu-id="f50c5-202">Установка — openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="f50c5-202">Installation - openSUSE 42.3</span></span>

```sh
# Install dependencies
zypper update && zypper --non-interactive install curl tar libicu52_1

# Download the powershell '.tar.gz' archive
curl -L https://github.com/PowerShell/PowerShell/releases/download/v6.2.0/powershell-6.2.0-linux-x64.tar.gz -o /tmp/powershell.tar.gz

# Create the target folder where powershell will be placed
mkdir -p /opt/microsoft/powershell/6.2.0

# Expand powershell to the target folder
tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/6.2.0

# Set execute permissions
chmod +x /opt/microsoft/powershell/6.2.0/pwsh

# Create the symbolic link that points to pwsh
ln -s /opt/microsoft/powershell/6.2.0/pwsh /usr/bin/pwsh

# Start PowerShell
pwsh
```

### <a name="installation---opensuse-leap-15"></a><span data-ttu-id="f50c5-203">Установка — openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="f50c5-203">Installation - openSUSE Leap 15</span></span>

```sh
# Install dependencies
zypper update && zypper --non-interactive install curl tar gzip libopenssl1_0_0 libicu60_2

# Download the powershell '.tar.gz' archive
curl -L https://github.com/PowerShell/PowerShell/releases/download/v6.2.0/powershell-6.2.0-linux-x64.tar.gz -o /tmp/powershell.tar.gz

# Create the target folder where powershell will be placed
mkdir -p /opt/microsoft/powershell/6.2.0

# Expand powershell to the target folder
tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/6.2.0

# Set execute permissions
chmod +x /opt/microsoft/powershell/6.2.0/pwsh

# Create the symbolic link that points to pwsh
ln -s /opt/microsoft/powershell/6.2.0/pwsh /usr/bin/pwsh

# Start PowerShell
pwsh
```

### <a name="uninstallation---opensuse-423-opensuse-leap-15"></a><span data-ttu-id="f50c5-204">Удаление — openSUSE 42.3, openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="f50c5-204">Uninstallation - openSUSE 42.3, openSUSE Leap 15</span></span>

```sh
rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="fedora"></a><span data-ttu-id="f50c5-205">Fedora</span><span class="sxs-lookup"><span data-stu-id="f50c5-205">Fedora</span></span>

> [!NOTE]
> <span data-ttu-id="f50c5-206">Fedora 28 поддерживается только в PowerShell Core 6.1 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="f50c5-206">Fedora 28 is only supported in PowerShell Core 6.1 and newer.</span></span>

> [!NOTE]
> <span data-ttu-id="f50c5-207">Fedora 29 и 30 поддерживается только в PowerShell 7.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="f50c5-207">Fedora 29 and 30 are only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-package-repository-preferred---fedora-28-29-and-30"></a><span data-ttu-id="f50c5-208">Установка с помощью репозитория пакетов (рекомендуется) — Fedora 28, 29 и 30</span><span class="sxs-lookup"><span data-stu-id="f50c5-208">Installation via Package Repository (preferred) - Fedora 28, 29, and 30</span></span>

<span data-ttu-id="f50c5-209">Чтобы упростить установку и обновление, PowerShell Core для Linux публикуется в официальных репозиториях Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f50c5-209">PowerShell Core for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

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

### <a name="installation-via-direct-download---fedora-28-29-and-30"></a><span data-ttu-id="f50c5-210">Установка с помощью прямого скачивания — Fedora 28, 29 и 30</span><span class="sxs-lookup"><span data-stu-id="f50c5-210">Installation via Direct Download - Fedora 28, 29, and 30</span></span>

<span data-ttu-id="f50c5-211">Скачайте пакет RPM `powershell-6.2.0-1.rhel.7.x86_64.rpm` со страницы [выпусками][] на компьютер с Fedora.</span><span class="sxs-lookup"><span data-stu-id="f50c5-211">Download the RPM package `powershell-6.2.0-1.rhel.7.x86_64.rpm` from the [releases][] page onto the Fedora machine.</span></span>

<span data-ttu-id="f50c5-212">Затем выполните в терминале следующие команды:</span><span class="sxs-lookup"><span data-stu-id="f50c5-212">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install powershell-6.2.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="f50c5-213">RPM можно установить без промежуточного скачивания:</span><span class="sxs-lookup"><span data-stu-id="f50c5-213">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install https://github.com/PowerShell/PowerShell/releases/download/v6.2.0/powershell-6.2.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---fedora-28-29-and-30"></a><span data-ttu-id="f50c5-214">Удаление — Fedora 28, 29 и 30</span><span class="sxs-lookup"><span data-stu-id="f50c5-214">Uninstallation - Fedora 28, 29, and 30</span></span>

```sh
sudo dnf remove powershell
```

## <a name="arch-linux"></a><span data-ttu-id="f50c5-215">Arch Linux</span><span class="sxs-lookup"><span data-stu-id="f50c5-215">Arch Linux</span></span>

> [!NOTE]
> <span data-ttu-id="f50c5-216">Arch официально не поддерживается корпорацией Майкрософт, но поддерживается сообществом.</span><span class="sxs-lookup"><span data-stu-id="f50c5-216">Arch support is not officially supported by Microsoft and is maintained by the community.</span></span>

<span data-ttu-id="f50c5-217">PowerShell можно получить из пользовательского репозитория [Arch Linux][] (AUR).</span><span class="sxs-lookup"><span data-stu-id="f50c5-217">PowerShell is available from the [Arch Linux][] User Repository (AUR).</span></span>

* <span data-ttu-id="f50c5-218">Его можно скомпилировать с помощью [последнего выпуска с тегами][arch-release].</span><span class="sxs-lookup"><span data-stu-id="f50c5-218">It can be compiled with the [latest tagged release][arch-release]</span></span>
* <span data-ttu-id="f50c5-219">Его можно скомпилировать из [последней фиксации в основной репозиторий][arch-git].</span><span class="sxs-lookup"><span data-stu-id="f50c5-219">It can be compiled from the [latest commit to master][arch-git]</span></span>
* <span data-ttu-id="f50c5-220">Его можно установить с помощью [двоичного файла последнего выпуска][arch-bin].</span><span class="sxs-lookup"><span data-stu-id="f50c5-220">It can be installed using the [latest release binary][arch-bin]</span></span>

<span data-ttu-id="f50c5-221">Пакеты в AUR обслуживаются сообществом — официальная поддержка не предусмотрена.</span><span class="sxs-lookup"><span data-stu-id="f50c5-221">Packages in the AUR are community maintained; there's no official support.</span></span>

<span data-ttu-id="f50c5-222">Дополнительные сведения об установке пакетов из AUR см. на [вики-сайте Arch Linux](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) или в [DockerFile](https://github.com/PowerShell/PowerShell/blob/master/docker/community/archlinux/Dockerfile) сообщества.</span><span class="sxs-lookup"><span data-stu-id="f50c5-222">For more information on installing packages from the AUR, see the [Arch Linux wiki](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) or the community [DockerFile](https://github.com/PowerShell/PowerShell/blob/master/docker/community/archlinux/Dockerfile).</span></span>

[Arch Linux]: https://www.archlinux.org/download/
[arch-release]: https://aur.archlinux.org/packages/powershell/
[arch-git]: https://aur.archlinux.org/packages/powershell-git/
[arch-bin]: https://aur.archlinux.org/packages/powershell-bin/

## <a name="snap-package"></a><span data-ttu-id="f50c5-224">Snap-пакет</span><span class="sxs-lookup"><span data-stu-id="f50c5-224">Snap Package</span></span>

### <a name="getting-snapd"></a><span data-ttu-id="f50c5-225">Установка Snap</span><span class="sxs-lookup"><span data-stu-id="f50c5-225">Getting snapd</span></span>

<span data-ttu-id="f50c5-226">Утилита `snapd` необходима для запуска snap-пакетов.</span><span class="sxs-lookup"><span data-stu-id="f50c5-226">`snapd` is required to run snaps.</span></span> <span data-ttu-id="f50c5-227">Чтобы убедиться, что утилита `snapd` установлена, воспользуйтесь [этими инструкциями](https://docs.snapcraft.io/core/install).</span><span class="sxs-lookup"><span data-stu-id="f50c5-227">Use [these instructions](https://docs.snapcraft.io/core/install) to make sure you have `snapd` installed.</span></span>

### <a name="installation-via-snap"></a><span data-ttu-id="f50c5-228">Установка с использованием Snap</span><span class="sxs-lookup"><span data-stu-id="f50c5-228">Installation via Snap</span></span>

<span data-ttu-id="f50c5-229">Чтобы упростить установку и обновление, PowerShell Core для Linux публикуется в [хранилище Snap](https://snapcraft.io/store).</span><span class="sxs-lookup"><span data-stu-id="f50c5-229">PowerShell Core for Linux is published to the [Snap store](https://snapcraft.io/store) for easy installation and updates.</span></span>

<span data-ttu-id="f50c5-230">Предпочтительный метод выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f50c5-230">The preferred method is as follows:</span></span>

```sh
# Install PowerShell
sudo snap install powershell --classic

# Start PowerShell
pwsh
```

<span data-ttu-id="f50c5-231">Чтобы установить предварительную версию, используйте следующий метод:</span><span class="sxs-lookup"><span data-stu-id="f50c5-231">To install a preview version, use the following method:</span></span>

```sh
# Install PowerShell
sudo snap install powershell-preview --classic

# Start PowerShell
pwsh-preview
```

<span data-ttu-id="f50c5-232">После установки Snap автоматически обновится.</span><span class="sxs-lookup"><span data-stu-id="f50c5-232">After installation, Snap will automatically upgrade.</span></span> <span data-ttu-id="f50c5-233">Обновление можно активировать с помощью `sudo snap refresh powershell` или `sudo snap refresh powershell-preview`.</span><span class="sxs-lookup"><span data-stu-id="f50c5-233">You can trigger an upgrade using `sudo snap refresh powershell` or `sudo snap refresh powershell-preview`.</span></span>

### <a name="uninstallation"></a><span data-ttu-id="f50c5-234">Удаление</span><span class="sxs-lookup"><span data-stu-id="f50c5-234">Uninstallation</span></span>

```sh
sudo snap remove powershell
```

<span data-ttu-id="f50c5-235">или</span><span class="sxs-lookup"><span data-stu-id="f50c5-235">or</span></span>

```sh
sudo snap remove powershell-preview
```

## <a name="kali"></a><span data-ttu-id="f50c5-236">Kali</span><span class="sxs-lookup"><span data-stu-id="f50c5-236">Kali</span></span>

> [!NOTE]
> <span data-ttu-id="f50c5-237">Kali официально не поддерживается корпорацией Майкрософт, но поддерживается сообществом.</span><span class="sxs-lookup"><span data-stu-id="f50c5-237">Kali support is not officially supported by Microsoft and is maintained by the community.</span></span>

### <a name="installation---kali"></a><span data-ttu-id="f50c5-238">Установка — Kali</span><span class="sxs-lookup"><span data-stu-id="f50c5-238">Installation - Kali</span></span>

```sh
# Download & Install prerequisites
wget http://ftp.us.debian.org/debian/pool/main/i/icu/libicu57_57.1-6+deb9u2_amd64.deb
dpkg -i libicu57_57.1-6+deb9u2_amd64.deb
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

### <a name="uninstallation---kali"></a><span data-ttu-id="f50c5-239">Удаление — Kali</span><span class="sxs-lookup"><span data-stu-id="f50c5-239">Uninstallation - Kali</span></span>

```sh
# Uninstall PowerShell package
apt-get remove -y powershell
```

## <a name="raspbian"></a><span data-ttu-id="f50c5-240">Raspbian</span><span class="sxs-lookup"><span data-stu-id="f50c5-240">Raspbian</span></span>

> [!NOTE]
> <span data-ttu-id="f50c5-241">Поддержка Raspbian на этапе эксперимента.</span><span class="sxs-lookup"><span data-stu-id="f50c5-241">Raspbian support is experimental.</span></span>

<span data-ttu-id="f50c5-242">Сейчас PowerShell поддерживается только в Raspbian Stretch.</span><span class="sxs-lookup"><span data-stu-id="f50c5-242">Currently, PowerShell is only supported on Raspbian Stretch.</span></span>

<span data-ttu-id="f50c5-243">CoreCLR и PowerShell Core будут работать только на устройствах Pi 2 и Pi 3. На таких устройствах, как [Pi Zero](https://github.com/dotnet/coreclr/issues/10605), установлены процессоры, поддержка которых не предусмотрена.</span><span class="sxs-lookup"><span data-stu-id="f50c5-243">CoreCLR and PowerShell Core will only work on Pi 2 and Pi 3 devices as other devices, like [Pi Zero](https://github.com/dotnet/coreclr/issues/10605), have an unsupported processor.</span></span>

<span data-ttu-id="f50c5-244">Загрузите [Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) и следуйте [инструкциям по установке](https://www.raspberrypi.org/documentation/installation/installing-images/README.md), чтобы установить его на свой Pi.</span><span class="sxs-lookup"><span data-stu-id="f50c5-244">Download [Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) and follow the [installation instructions](https://www.raspberrypi.org/documentation/installation/installing-images/README.md) to get it onto your Pi.</span></span>

### <a name="installation---raspbian"></a><span data-ttu-id="f50c5-245">Установка — Raspbian</span><span class="sxs-lookup"><span data-stu-id="f50c5-245">Installation - Raspbian</span></span>

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
wget https://github.com/PowerShell/PowerShell/releases/download/v6.2.0/powershell-6.2.0-linux-arm32.tar.gz

# Make folder to put powershell
mkdir ~/powershell

# Unpack the tar.gz file
tar -xvf ./powershell-6.2.0-linux-arm32.tar.gz -C ~/powershell

# Start PowerShell
~/powershell/pwsh
```

<span data-ttu-id="f50c5-246">При необходимости можно создать символьную ссылку для запуска PowerShell без указания пути к двоичному файлу `pwsh`.</span><span class="sxs-lookup"><span data-stu-id="f50c5-246">Optionally, you can create a symbolic link to start PowerShell without specifying the path to the `pwsh` binary.</span></span>

```sh
# Start PowerShell from bash with sudo to create a symbolic link
sudo ~/powershell/pwsh -c New-Item -ItemType SymbolicLink -Path "/usr/bin/pwsh" -Target "\$PSHOME/pwsh" -Force

# alternatively you can run following to create a symbolic link
# sudo ln -s ~/powershell/pwsh /usr/bin/pwsh

# Now to start PowerShell you can just run "pwsh"
```

### <a name="uninstallation---raspbian"></a><span data-ttu-id="f50c5-247">Удаление — Raspbian</span><span class="sxs-lookup"><span data-stu-id="f50c5-247">Uninstallation - Raspbian</span></span>

```sh
rm -rf ~/powershell
```

## <a name="binary-archives"></a><span data-ttu-id="f50c5-248">Архивы двоичных файлов</span><span class="sxs-lookup"><span data-stu-id="f50c5-248">Binary Archives</span></span>

<span data-ttu-id="f50c5-249">Для поддержки расширенных сценариев развертывания на платформах Linux доступны архивы `tar.gz` двоичных файлов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f50c5-249">PowerShell binary `tar.gz` archives are provided for Linux platforms to enable advanced deployment scenarios.</span></span>

### <a name="dependencies"></a><span data-ttu-id="f50c5-250">Зависимости</span><span class="sxs-lookup"><span data-stu-id="f50c5-250">Dependencies</span></span>

<span data-ttu-id="f50c5-251">PowerShell создает переносимые двоичные файлы для всех дистрибутивов Linux.</span><span class="sxs-lookup"><span data-stu-id="f50c5-251">PowerShell builds portable binaries for all Linux distributions.</span></span> <span data-ttu-id="f50c5-252">Но среда выполнения .NET Core, как и PowerShell, требует различные зависимости для разных дистрибутивов.</span><span class="sxs-lookup"><span data-stu-id="f50c5-252">But, .NET Core runtime requires different dependencies on different distributions, and PowerShell does too.</span></span>

<span data-ttu-id="f50c5-253">На следующей диаграмме показаны официально поддерживаемые зависимости .NET Core 2.0 для различных дистрибутивов Linux.</span><span class="sxs-lookup"><span data-stu-id="f50c5-253">The following chart shows the .NET Core 2.0 dependencies that are officially supported on different Linux distributions.</span></span>

| <span data-ttu-id="f50c5-254">ОС</span><span class="sxs-lookup"><span data-stu-id="f50c5-254">OS</span></span>                 | <span data-ttu-id="f50c5-255">Зависимости</span><span class="sxs-lookup"><span data-stu-id="f50c5-255">Dependencies</span></span> |
| ------------------ | ------------ |
| <span data-ttu-id="f50c5-256">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="f50c5-256">Ubuntu 16.04</span></span>       | <span data-ttu-id="f50c5-257">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="f50c5-257">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="f50c5-258">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu55</span><span class="sxs-lookup"><span data-stu-id="f50c5-258">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu55</span></span> |
| <span data-ttu-id="f50c5-259">Ubuntu 17.10</span><span class="sxs-lookup"><span data-stu-id="f50c5-259">Ubuntu 17.10</span></span>       | <span data-ttu-id="f50c5-260">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="f50c5-260">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="f50c5-261">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu57</span><span class="sxs-lookup"><span data-stu-id="f50c5-261">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu57</span></span> |
| <span data-ttu-id="f50c5-262">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="f50c5-262">Ubuntu 18.04</span></span>       | <span data-ttu-id="f50c5-263">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="f50c5-263">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="f50c5-264">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu60</span><span class="sxs-lookup"><span data-stu-id="f50c5-264">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu60</span></span> |
| <span data-ttu-id="f50c5-265">Debian 8 (Jessie)</span><span class="sxs-lookup"><span data-stu-id="f50c5-265">Debian 8 (Jessie)</span></span>  | <span data-ttu-id="f50c5-266">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="f50c5-266">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="f50c5-267">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span><span class="sxs-lookup"><span data-stu-id="f50c5-267">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span></span> |
| <span data-ttu-id="f50c5-268">Debian 9 (Stretch)</span><span class="sxs-lookup"><span data-stu-id="f50c5-268">Debian 9 (Stretch)</span></span> | <span data-ttu-id="f50c5-269">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="f50c5-269">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="f50c5-270">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.2, libicu57</span><span class="sxs-lookup"><span data-stu-id="f50c5-270">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.2, libicu57</span></span> |
| <span data-ttu-id="f50c5-271">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="f50c5-271">CentOS 7</span></span> <br> <span data-ttu-id="f50c5-272">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="f50c5-272">Oracle Linux 7</span></span> <br> <span data-ttu-id="f50c5-273">RHEL 7</span><span class="sxs-lookup"><span data-stu-id="f50c5-273">RHEL 7</span></span> | <span data-ttu-id="f50c5-274">libunwind, libcurl, openssl-libs, libicu</span><span class="sxs-lookup"><span data-stu-id="f50c5-274">libunwind, libcurl, openssl-libs, libicu</span></span> |
| <span data-ttu-id="f50c5-275">openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="f50c5-275">openSUSE 42.3</span></span> | <span data-ttu-id="f50c5-276">libcurl4, libopenssl1_0_0, libicu52_1</span><span class="sxs-lookup"><span data-stu-id="f50c5-276">libcurl4, libopenssl1_0_0, libicu52_1</span></span> |
| <span data-ttu-id="f50c5-277">openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="f50c5-277">openSUSE Leap 15</span></span> | <span data-ttu-id="f50c5-278">libcurl4, libopenssl1_0_0, libicu60_2</span><span class="sxs-lookup"><span data-stu-id="f50c5-278">libcurl4, libopenssl1_0_0, libicu60_2</span></span> |
| <span data-ttu-id="f50c5-279">Fedora 27</span><span class="sxs-lookup"><span data-stu-id="f50c5-279">Fedora 27</span></span> <br> <span data-ttu-id="f50c5-280">Fedora 28</span><span class="sxs-lookup"><span data-stu-id="f50c5-280">Fedora 28</span></span> | <span data-ttu-id="f50c5-281">libunwind, libcurl, openssl-libs, libicu, compat-openssl10</span><span class="sxs-lookup"><span data-stu-id="f50c5-281">libunwind, libcurl, openssl-libs, libicu, compat-openssl10</span></span> |

<span data-ttu-id="f50c5-282">Чтобы развернуть двоичные файлы PowerShell в дистрибутивах Linux, для которых официальная поддержка не предусмотрена, необходимо специально установить необходимые пакеты, чтобы выполнить все требования, касающиеся зависимостей, для целевой ОС.</span><span class="sxs-lookup"><span data-stu-id="f50c5-282">To deploy PowerShell binaries on Linux distributions that aren't officially supported, you need to install the necessary dependencies for the target OS in separate steps.</span></span> <span data-ttu-id="f50c5-283">Например, наш [Dockerfile для Amazon Linux][amazon-dockerfile] сначала устанавливает зависимости, а затем извлекает архив Linux `tar.gz`.</span><span class="sxs-lookup"><span data-stu-id="f50c5-283">For example, our [Amazon Linux dockerfile][amazon-dockerfile] installs dependencies first, and then extracts the Linux `tar.gz` archive.</span></span>

[amazon-dockerfile]: https://github.com/PowerShell/PowerShell-Docker/blob/master/release/community-stable/amazonlinux/docker/Dockerfile

### <a name="installation---binary-archives"></a><span data-ttu-id="f50c5-284">Установка — архивы двоичных файлов</span><span class="sxs-lookup"><span data-stu-id="f50c5-284">Installation - Binary Archives</span></span>

#### <a name="linux"></a><span data-ttu-id="f50c5-285">Linux</span><span class="sxs-lookup"><span data-stu-id="f50c5-285">Linux</span></span>

```sh
# Download the powershell '.tar.gz' archive
curl -L -o /tmp/powershell.tar.gz https://github.com/PowerShell/PowerShell/releases/download/v6.2.0/powershell-6.2.0-linux-x64.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /opt/microsoft/powershell/6.2.0

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/6.2.0

# Set execute permissions
sudo chmod +x /opt/microsoft/powershell/6.2.0/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /opt/microsoft/powershell/6.2.0/pwsh /usr/bin/pwsh
```

### <a name="uninstalling-binary-archives"></a><span data-ttu-id="f50c5-286">Удаление архивов двоичных файлов</span><span class="sxs-lookup"><span data-stu-id="f50c5-286">Uninstalling binary archives</span></span>

```sh
sudo rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="paths"></a><span data-ttu-id="f50c5-287">Пути</span><span class="sxs-lookup"><span data-stu-id="f50c5-287">Paths</span></span>

* <span data-ttu-id="f50c5-288">`$PSHOME` имеет значение `/opt/microsoft/powershell/6.2.0/`.</span><span class="sxs-lookup"><span data-stu-id="f50c5-288">`$PSHOME` is `/opt/microsoft/powershell/6.2.0/`</span></span>
* <span data-ttu-id="f50c5-289">Профили пользователей будут считаны из `~/.config/powershell/profile.ps1`.</span><span class="sxs-lookup"><span data-stu-id="f50c5-289">User profiles will be read from `~/.config/powershell/profile.ps1`</span></span>
* <span data-ttu-id="f50c5-290">Профили по умолчанию будут считаны из `$PSHOME/profile.ps1`.</span><span class="sxs-lookup"><span data-stu-id="f50c5-290">Default profiles will be read from `$PSHOME/profile.ps1`</span></span>
* <span data-ttu-id="f50c5-291">Модули пользователей будут считаны из `~/.local/share/powershell/Modules`.</span><span class="sxs-lookup"><span data-stu-id="f50c5-291">User modules will be read from `~/.local/share/powershell/Modules`</span></span>
* <span data-ttu-id="f50c5-292">Общие модули будут считаны из `/usr/local/share/powershell/Modules`.</span><span class="sxs-lookup"><span data-stu-id="f50c5-292">Shared modules will be read from `/usr/local/share/powershell/Modules`</span></span>
* <span data-ttu-id="f50c5-293">Модули по умолчанию будут считаны из `$PSHOME/Modules`.</span><span class="sxs-lookup"><span data-stu-id="f50c5-293">Default modules will be read from `$PSHOME/Modules`</span></span>
* <span data-ttu-id="f50c5-294">Журнал PSReadline будет записан в `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`.</span><span class="sxs-lookup"><span data-stu-id="f50c5-294">PSReadline history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="f50c5-295">Профили учитывают конфигурацию PowerShell для отдельных узлов, поэтому профили конкретных узлов по умолчанию находятся в `Microsoft.PowerShell_profile.ps1` в тех же расположениях.</span><span class="sxs-lookup"><span data-stu-id="f50c5-295">The profiles respect PowerShell's per-host configuration, so the default host-specific profiles exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="f50c5-296">PowerShell отвечает требованиям [спецификации каталога размещения файлов, связанных со средой настольной графической среды (X-сервера), стандартизированного XDG (X Desktop Group)][xdg-bds] в Linux.</span><span class="sxs-lookup"><span data-stu-id="f50c5-296">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on Linux.</span></span>

[выпусками]: https://github.com/PowerShell/PowerShell/releases/latest
[releases]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
