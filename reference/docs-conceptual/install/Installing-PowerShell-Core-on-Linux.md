---
title: Установка PowerShell в Linux
description: Сведения об установке PowerShell в различных дистрибутивах Linux
ms.date: 03/09/2020
ms.openlocfilehash: e04d8a91999cd6e9b2d669230c7a1b412f11eeb8
ms.sourcegitcommit: 4eda0bc902658d4a188159bd7310e64399f6e178
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83271905"
---
# <a name="installing-powershell-on-linux"></a><span data-ttu-id="f6cd6-103">Установка PowerShell в Linux</span><span class="sxs-lookup"><span data-stu-id="f6cd6-103">Installing PowerShell on Linux</span></span>

<span data-ttu-id="f6cd6-104">Все пакеты доступны на нашей странице [выпусками][] GitHub.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-104">All packages are available on our GitHub [releases][] page.</span></span> <span data-ttu-id="f6cd6-105">После установки пакета запустите `pwsh` из терминала.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-105">After the package is installed, run `pwsh` from a terminal.</span></span> <span data-ttu-id="f6cd6-106">Запустите `pwsh-preview`, если вы установили [выпуск предварительной версии](#installing-preview-releases).</span><span class="sxs-lookup"><span data-stu-id="f6cd6-106">Run `pwsh-preview` if you installed a [Preview release](#installing-preview-releases).</span></span>

> [!NOTE]
> <span data-ttu-id="f6cd6-107">PowerShell 7 является обновлением на месте, при установке которого PowerShell Core 6.x удаляется.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-107">PowerShell 7 is an in-place upgrade that removes PowerShell Core 6.x.</span></span>
>
> <span data-ttu-id="f6cd6-108">Папка `/usr/local/microsoft/powershell/6` заменяется на `/usr/local/microsoft/powershell/7`.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-108">The `/usr/local/microsoft/powershell/6` folder is replaced by `/usr/local/microsoft/powershell/7`.</span></span>
>
> <span data-ttu-id="f6cd6-109">Если вы хотите запускать PowerShell 6 параллельно с PowerShell 7, переустановите PowerShell 6 с использованием [двоичного архива](#binary-archives).</span><span class="sxs-lookup"><span data-stu-id="f6cd6-109">If you need to run PowerShell 6 side-by-side with PowerShell 7, reinstall PowerShell 6 using the [binary archive](#binary-archives) method.</span></span>

<span data-ttu-id="f6cd6-110">Для дистрибутивов Linux без официальной поддержки попробуйте установить PowerShell с помощью [соответствующего Snap-пакета][snap].</span><span class="sxs-lookup"><span data-stu-id="f6cd6-110">For Linux distributions that aren't officially supported, you can try to install PowerShell using the [PowerShell Snap Package][snap].</span></span> <span data-ttu-id="f6cd6-111">Можно также попытаться развернуть двоичные файлы PowerShell напрямую с помощью [архива`tar.gz`][tar] Linux, но при этом нужно отдельно настроить необходимые зависимости с учетом операционной системы.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-111">You can also try deploying PowerShell binaries directly using the Linux [`tar.gz` archive][tar], but you would need to set up the necessary dependencies based on the OS in separate steps.</span></span>

[snap]: #snap-package
[tar]: #binary-archives

<span data-ttu-id="f6cd6-112">Официально поддерживаемые выпуски:</span><span class="sxs-lookup"><span data-stu-id="f6cd6-112">Officially supported releases</span></span>

- <span data-ttu-id="f6cd6-113">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="f6cd6-113">Ubuntu 16.04</span></span>
- <span data-ttu-id="f6cd6-114">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="f6cd6-114">Ubuntu 18.04</span></span>
- <span data-ttu-id="f6cd6-115">Debian 8</span><span class="sxs-lookup"><span data-stu-id="f6cd6-115">Debian 8</span></span>
- <span data-ttu-id="f6cd6-116">Debian 9</span><span class="sxs-lookup"><span data-stu-id="f6cd6-116">Debian 9</span></span>
- <span data-ttu-id="f6cd6-117">Debian 10</span><span class="sxs-lookup"><span data-stu-id="f6cd6-117">Debian 10</span></span>
- <span data-ttu-id="f6cd6-118">Alpine 3.9 и 3.10</span><span class="sxs-lookup"><span data-stu-id="f6cd6-118">Alpine 3.9 and 3.10</span></span>
- <span data-ttu-id="f6cd6-119">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="f6cd6-119">CentOS 7</span></span>
- <span data-ttu-id="f6cd6-120">Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="f6cd6-120">Red Hat Enterprise Linux (RHEL) 7</span></span>
- <span data-ttu-id="f6cd6-121">Fedora 28</span><span class="sxs-lookup"><span data-stu-id="f6cd6-121">Fedora 28</span></span>
- <span data-ttu-id="f6cd6-122">Fedora 29</span><span class="sxs-lookup"><span data-stu-id="f6cd6-122">Fedora 29</span></span>
- <span data-ttu-id="f6cd6-123">Fedora 30</span><span class="sxs-lookup"><span data-stu-id="f6cd6-123">Fedora 30</span></span>
- <span data-ttu-id="f6cd6-124">openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="f6cd6-124">openSUSE 42.3</span></span>
- <span data-ttu-id="f6cd6-125">openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="f6cd6-125">openSUSE Leap 15</span></span>

<span data-ttu-id="f6cd6-126">Выпуски, поддерживаемые сообществом:</span><span class="sxs-lookup"><span data-stu-id="f6cd6-126">Community supported releases</span></span>

- <span data-ttu-id="f6cd6-127">Ubuntu 18.10</span><span class="sxs-lookup"><span data-stu-id="f6cd6-127">Ubuntu 18.10</span></span>
- <span data-ttu-id="f6cd6-128">Ubuntu 19.04</span><span class="sxs-lookup"><span data-stu-id="f6cd6-128">Ubuntu 19.04</span></span>
- <span data-ttu-id="f6cd6-129">Arch Linux</span><span class="sxs-lookup"><span data-stu-id="f6cd6-129">Arch Linux</span></span>
- <span data-ttu-id="f6cd6-130">Kali</span><span class="sxs-lookup"><span data-stu-id="f6cd6-130">Kali</span></span>
- <span data-ttu-id="f6cd6-131">Raspbian (экспериментальная версия)</span><span class="sxs-lookup"><span data-stu-id="f6cd6-131">Raspbian (experimental)</span></span>

<span data-ttu-id="f6cd6-132">Альтернативные методы установки</span><span class="sxs-lookup"><span data-stu-id="f6cd6-132">Alternate install methods</span></span>

- <span data-ttu-id="f6cd6-133">Snap-пакет</span><span class="sxs-lookup"><span data-stu-id="f6cd6-133">Snap Package</span></span>
- <span data-ttu-id="f6cd6-134">Архивы двоичных файлов</span><span class="sxs-lookup"><span data-stu-id="f6cd6-134">Binary Archives</span></span>
- <span data-ttu-id="f6cd6-135">Глобальный инструмент .NET</span><span class="sxs-lookup"><span data-stu-id="f6cd6-135">.NET Global tool</span></span>

<span data-ttu-id="f6cd6-136">Сейчас не поддерживается</span><span class="sxs-lookup"><span data-stu-id="f6cd6-136">Not currently supported</span></span> 

- <span data-ttu-id="f6cd6-137">Ubuntu 20.04</span><span class="sxs-lookup"><span data-stu-id="f6cd6-137">Ubuntu 20.04</span></span>

## <a name="ubuntu-1604"></a><span data-ttu-id="f6cd6-138">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="f6cd6-138">Ubuntu 16.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1604"></a><span data-ttu-id="f6cd6-139">Установка с помощью репозитория пакетов — Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="f6cd6-139">Installation via Package Repository - Ubuntu 16.04</span></span>

<span data-ttu-id="f6cd6-140">Чтобы упростить установку и обновление, PowerShell для Linux публикуется в репозиториях пакетов.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-140">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="f6cd6-141">Предпочтительный метод выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f6cd6-141">The preferred method is as follows:</span></span>

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

<span data-ttu-id="f6cd6-142">В качестве суперпользователя однократно зарегистрируйте репозиторий Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-142">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="f6cd6-143">После регистрации можно обновить PowerShell с помощью `sudo apt-get upgrade powershell`.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-143">After registration, you can update PowerShell with `sudo apt-get upgrade powershell`.</span></span>

### <a name="installation-via-direct-download---ubuntu-1604"></a><span data-ttu-id="f6cd6-144">Установка с помощью прямого скачивания — Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="f6cd6-144">Installation via Direct Download - Ubuntu 16.04</span></span>

<span data-ttu-id="f6cd6-145">Скачайте пакет Debian `powershell-lts_7.0.0-1.ubuntu.16.04_amd64.deb` со страницы [выпусками][] на компьютер с Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-145">Download the Debian package `powershell-lts_7.0.0-1.ubuntu.16.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="f6cd6-146">Затем выполните в терминале следующие команды:</span><span class="sxs-lookup"><span data-stu-id="f6cd6-146">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell-lts_7.0.0-1.ubuntu.16.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="f6cd6-147">Команда `dpkg -i` завершается ошибкой при наличии несопоставленных зависимостей.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-147">The `dpkg -i` command fails with unmet dependencies.</span></span> <span data-ttu-id="f6cd6-148">Следующая команда, `apt-get install -f`, разрешает эти ошибки и завершает настройку пакета PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-148">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1604"></a><span data-ttu-id="f6cd6-149">Удаление — Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="f6cd6-149">Uninstallation - Ubuntu 16.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1804"></a><span data-ttu-id="f6cd6-150">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="f6cd6-150">Ubuntu 18.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1804"></a><span data-ttu-id="f6cd6-151">Установка с помощью репозитория пакетов — Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="f6cd6-151">Installation via Package Repository - Ubuntu 18.04</span></span>

<span data-ttu-id="f6cd6-152">Чтобы упростить установку и обновление, PowerShell для Linux публикуется в репозиториях пакетов.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-152">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="f6cd6-153">Предпочтительный метод выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f6cd6-153">The preferred method is as follows:</span></span>

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

<span data-ttu-id="f6cd6-154">В качестве суперпользователя однократно зарегистрируйте репозиторий Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-154">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="f6cd6-155">После регистрации можно обновить PowerShell с помощью `sudo apt-get upgrade powershell`.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-155">After registration, you can update PowerShell with `sudo apt-get upgrade powershell`.</span></span>

### <a name="installation-via-direct-download---ubuntu-1804"></a><span data-ttu-id="f6cd6-156">Установка с помощью прямого скачивания — Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="f6cd6-156">Installation via Direct Download - Ubuntu 18.04</span></span>

<span data-ttu-id="f6cd6-157">Скачайте пакет Debian `powershell-lts_7.0.0-1.ubuntu.18.04_amd64.deb` со страницы [выпусками][] на компьютер с Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-157">Download the Debian package `powershell-lts_7.0.0-1.ubuntu.18.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="f6cd6-158">Затем выполните в терминале следующие команды:</span><span class="sxs-lookup"><span data-stu-id="f6cd6-158">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell-lts_7.0.0-1.ubuntu.18.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="f6cd6-159">Команда `dpkg -i` завершается ошибкой при наличии несопоставленных зависимостей.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-159">The `dpkg -i` command fails with unmet dependencies.</span></span> <span data-ttu-id="f6cd6-160">Следующая команда, `apt-get install -f`, разрешает эти ошибки и завершает настройку пакета PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-160">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1804"></a><span data-ttu-id="f6cd6-161">Удаление — Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="f6cd6-161">Uninstallation - Ubuntu 18.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1810"></a><span data-ttu-id="f6cd6-162">Ubuntu 18.10</span><span class="sxs-lookup"><span data-stu-id="f6cd6-162">Ubuntu 18.10</span></span>

<span data-ttu-id="f6cd6-163">Поддерживается только установка с помощью `snapd`.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-163">Installation is supported via `snapd`.</span></span> <span data-ttu-id="f6cd6-164">Инструкции см. в разделе о [snap-пакете][snap].</span><span class="sxs-lookup"><span data-stu-id="f6cd6-164">For instructions, see [Snap Package][snap].</span></span>

> [!NOTE]
> <span data-ttu-id="f6cd6-165">Ubuntu 18.10 — [промежуточный выпуск](https://www.ubuntu.com/about/release-cycle), который [поддерживается сообществом](../powershell-support-lifecycle.md).</span><span class="sxs-lookup"><span data-stu-id="f6cd6-165">Ubuntu 18.10 is an [interim release](https://www.ubuntu.com/about/release-cycle) that's [community supported](../powershell-support-lifecycle.md).</span></span>

## <a name="ubuntu-1904"></a><span data-ttu-id="f6cd6-166">Ubuntu 19.04</span><span class="sxs-lookup"><span data-stu-id="f6cd6-166">Ubuntu 19.04</span></span>

<span data-ttu-id="f6cd6-167">Поддерживается только установка с помощью `snapd`.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-167">Installation is supported via `snapd`.</span></span> <span data-ttu-id="f6cd6-168">Инструкции см. в разделе о [snap-пакете][snap].</span><span class="sxs-lookup"><span data-stu-id="f6cd6-168">For instructions, see [Snap Package][snap].</span></span>

> [!NOTE]
> <span data-ttu-id="f6cd6-169">Ubuntu 19.04 — [промежуточный выпуск](https://www.ubuntu.com/about/release-cycle), который [поддерживается сообществом](../powershell-support-lifecycle.md).</span><span class="sxs-lookup"><span data-stu-id="f6cd6-169">Ubuntu 19.04 is an [interim release](https://www.ubuntu.com/about/release-cycle) that's [community supported](../powershell-support-lifecycle.md).</span></span>

## <a name="ubuntu-2004"></a><span data-ttu-id="f6cd6-170">Ubuntu 20.04</span><span class="sxs-lookup"><span data-stu-id="f6cd6-170">Ubuntu 20.04</span></span>

<span data-ttu-id="f6cd6-171">Ubuntu 20.04 — это выпуск LTS.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-171">Ubuntu 20.04 is an LTS release.</span></span> <span data-ttu-id="f6cd6-172">PowerShell сейчас не поддерживает эту версию.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-172">PowerShell does not currently support this version.</span></span> <span data-ttu-id="f6cd6-173">В настоящее время рассматривается добавление поддержки этой версии в выпуске PowerShell 7.1.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-173">Support for this version is being considered for the PowerShell 7.1 release.</span></span> <span data-ttu-id="f6cd6-174">Проголосуйте за этот [запрос](https://github.com/PowerShell/PowerShell/issues/12626), если вам требуется поддержка Ubuntu 20.04.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-174">Please upvote this [request](https://github.com/PowerShell/PowerShell/issues/12626) if you would like support for Ubuntu 20.04.</span></span>

## <a name="debian-8"></a><span data-ttu-id="f6cd6-175">Debian 8</span><span class="sxs-lookup"><span data-stu-id="f6cd6-175">Debian 8</span></span>

### <a name="installation-via-package-repository---debian-8"></a><span data-ttu-id="f6cd6-176">Установка с помощью репозитория пакетов — Debian 8</span><span class="sxs-lookup"><span data-stu-id="f6cd6-176">Installation via Package Repository - Debian 8</span></span>

<span data-ttu-id="f6cd6-177">Чтобы упростить установку и обновление, PowerShell для Linux публикуется в репозиториях пакетов.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-177">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="f6cd6-178">Предпочтительный метод выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f6cd6-178">The preferred method is as follows:</span></span>

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

<span data-ttu-id="f6cd6-179">В качестве суперпользователя однократно зарегистрируйте репозиторий Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-179">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="f6cd6-180">После регистрации можно обновить PowerShell с помощью `sudo apt-get upgrade powershell`.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-180">After registration, you can update PowerShell with `sudo apt-get upgrade powershell`.</span></span>

## <a name="debian-9"></a><span data-ttu-id="f6cd6-181">Debian 9</span><span class="sxs-lookup"><span data-stu-id="f6cd6-181">Debian 9</span></span>

### <a name="installation-via-package-repository---debian-9"></a><span data-ttu-id="f6cd6-182">Установка с помощью репозитория пакетов — Debian 9</span><span class="sxs-lookup"><span data-stu-id="f6cd6-182">Installation via Package Repository - Debian 9</span></span>

<span data-ttu-id="f6cd6-183">Чтобы упростить установку и обновление, PowerShell для Linux публикуется в репозиториях пакетов.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-183">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="f6cd6-184">Предпочтительный метод выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f6cd6-184">The preferred method is as follows:</span></span>

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

<span data-ttu-id="f6cd6-185">В качестве суперпользователя однократно зарегистрируйте репозиторий Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-185">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="f6cd6-186">После регистрации можно обновить PowerShell с помощью `sudo apt-get upgrade powershell`.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-186">After registration, you can update PowerShell with `sudo apt-get upgrade powershell`.</span></span>

### <a name="installation-via-direct-download---debian-9"></a><span data-ttu-id="f6cd6-187">Установка с помощью прямого скачивания — Debian 9</span><span class="sxs-lookup"><span data-stu-id="f6cd6-187">Installation via Direct Download - Debian 9</span></span>

<span data-ttu-id="f6cd6-188">Скачайте пакет Debian `powershell-lts_7.0.0-1.debian.9_amd64.deb` со страницы [выпусками][] на компьютер с Debian.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-188">Download the Debian package `powershell-lts_7.0.0-1.debian.9_amd64.deb` from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="f6cd6-189">Затем выполните в терминале следующие команды:</span><span class="sxs-lookup"><span data-stu-id="f6cd6-189">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell-lts_7.0.0-1.debian.9_amd64.deb
sudo apt-get install -f
```

### <a name="uninstallation---debian-9"></a><span data-ttu-id="f6cd6-190">Удаление — Debian 9</span><span class="sxs-lookup"><span data-stu-id="f6cd6-190">Uninstallation - Debian 9</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="debian-10"></a><span data-ttu-id="f6cd6-191">Debian 10</span><span class="sxs-lookup"><span data-stu-id="f6cd6-191">Debian 10</span></span>

> [!NOTE]
> <span data-ttu-id="f6cd6-192">Debian 10 поддерживается только в PowerShell 7.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-192">Debian 10 is only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-package-repository---debian-10"></a><span data-ttu-id="f6cd6-193">Установка с помощью репозитория пакетов — Debian 10</span><span class="sxs-lookup"><span data-stu-id="f6cd6-193">Installation via Package Repository - Debian 10</span></span>

<span data-ttu-id="f6cd6-194">Чтобы упростить установку и обновление, PowerShell для Linux публикуется в репозиториях пакетов.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-194">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="f6cd6-195">Предпочтительный метод выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f6cd6-195">The preferred method is as follows:</span></span>

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

### <a name="installation-via-direct-download---debian-10"></a><span data-ttu-id="f6cd6-196">Установка с помощью прямого скачивания — Debian 10</span><span class="sxs-lookup"><span data-stu-id="f6cd6-196">Installation via Direct Download - Debian 10</span></span>

<span data-ttu-id="f6cd6-197">Скачайте пакет tar.gz `powershell_7.0.0-linux-x64.tar.gz` на странице с [выпусками][] на компьютер с Debian.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-197">Download the tar.gz package `powershell_7.0.0-linux-x64.tar.gz` from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="f6cd6-198">Затем выполните в терминале следующие команды:</span><span class="sxs-lookup"><span data-stu-id="f6cd6-198">Then, in the terminal, execute the following commands:</span></span>

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
curl -L  https://github.com/PowerShell/PowerShell/releases/download/v7.0.0/powershell-7.0.0-linux-x64.tar.gz -o /tmp/powershell.tar.gz

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

## <a name="alpine-39-and-310"></a><span data-ttu-id="f6cd6-199">Alpine 3.9 и 3.10</span><span class="sxs-lookup"><span data-stu-id="f6cd6-199">Alpine 3.9 and 3.10</span></span>

> [!NOTE]
> <span data-ttu-id="f6cd6-200">Alpine 3.9 и 3.10 поддерживается только в PowerShell 7.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-200">Alpine 3.9 and 3.10 are only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-direct-download---alpine-39-and-310"></a><span data-ttu-id="f6cd6-201">Установка с помощью прямого скачивания — Alpine 3.9 и 3.10</span><span class="sxs-lookup"><span data-stu-id="f6cd6-201">Installation via Direct Download - Alpine 3.9 and 3.10</span></span>

<span data-ttu-id="f6cd6-202">Скачайте пакет tar.gz `powershell-7.0.0-linux-alpine-x64.tar.gz` на странице с [выпусками][] на компьютер с Alpine.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-202">Download the tar.gz package `powershell-7.0.0-linux-alpine-x64.tar.gz` from the [releases][] page onto the Alpine machine.</span></span>

<span data-ttu-id="f6cd6-203">Затем выполните в терминале следующие команды:</span><span class="sxs-lookup"><span data-stu-id="f6cd6-203">Then, in the terminal, execute the following commands:</span></span>

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
curl -L https://github.com/PowerShell/PowerShell/releases/download/v7.0.0/powershell-7.0.0-linux-alpine-x64.tar.gz -o /tmp/powershell.tar.gz

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

## <a name="centos-7"></a><span data-ttu-id="f6cd6-204">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="f6cd6-204">CentOS 7</span></span>

> [!NOTE]
> <span data-ttu-id="f6cd6-205">Этот пакет работает в Oracle Linux 7.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-205">This package works on Oracle Linux 7.</span></span>

### <a name="installation-via-package-repository-preferred---centos-7"></a><span data-ttu-id="f6cd6-206">Установка с помощью репозитория пакетов (рекомендуется) — CentOS 7</span><span class="sxs-lookup"><span data-stu-id="f6cd6-206">Installation via Package Repository (preferred) - CentOS 7</span></span>

<span data-ttu-id="f6cd6-207">Чтобы упростить установку и обновление, PowerShell для Linux публикуется в официальных репозиториях Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-207">PowerShell for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="f6cd6-208">В качестве суперпользователя однократно зарегистрируйте репозиторий Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-208">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="f6cd6-209">После регистрации можно обновить PowerShell с помощью `sudo yum update powershell`.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-209">After registration, you can update PowerShell with `sudo yum update powershell`.</span></span>

### <a name="installation-via-direct-download---centos-7"></a><span data-ttu-id="f6cd6-210">Установка с помощью прямого скачивания — CentOS 7</span><span class="sxs-lookup"><span data-stu-id="f6cd6-210">Installation via Direct Download - CentOS 7</span></span>

<span data-ttu-id="f6cd6-211">Используя [CentOS 7][], скачайте пакет RPM `powershell-lts-7.0.0-1.rhel.7.x86_64.rpm` со страницы [выпусками][] на компьютер с CentOS.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-211">Using [CentOS 7][], download the RPM package `powershell-lts-7.0.0-1.rhel.7.x86_64.rpm` from the [releases][] page onto the CentOS machine.</span></span>

<span data-ttu-id="f6cd6-212">Затем выполните в терминале следующие команды:</span><span class="sxs-lookup"><span data-stu-id="f6cd6-212">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo yum install powershell-lts-7.0.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="f6cd6-213">RPM можно установить без промежуточного скачивания:</span><span class="sxs-lookup"><span data-stu-id="f6cd6-213">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v7.0.0/powershell-lts-7.0.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---centos-7"></a><span data-ttu-id="f6cd6-214">Удаление — CentOS 7</span><span class="sxs-lookup"><span data-stu-id="f6cd6-214">Uninstallation - CentOS 7</span></span>

```sh
sudo yum remove powershell
```

[CentOS 7]: https://www.centos.org/download/

## <a name="red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="f6cd6-216">Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="f6cd6-216">Red Hat Enterprise Linux (RHEL) 7</span></span>

### <a name="installation-via-package-repository-preferred---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="f6cd6-217">Установка с помощью репозитория пакетов (рекомендуется) — Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="f6cd6-217">Installation via Package Repository (preferred) - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="f6cd6-218">Чтобы упростить установку и обновление, PowerShell для Linux публикуется в официальных репозиториях Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-218">PowerShell for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="f6cd6-219">В качестве суперпользователя однократно зарегистрируйте репозиторий Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-219">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="f6cd6-220">После регистрации можно обновить PowerShell с помощью `sudo yum update powershell`.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-220">After registration, you can update PowerShell with `sudo yum update powershell`.</span></span>

### <a name="installation-via-direct-download---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="f6cd6-221">Установка с помощью прямого скачивания — Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="f6cd6-221">Installation via Direct Download - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="f6cd6-222">Скачайте пакет RPM `powershell-lts-7.0.0-1.rhel.7.x86_64.rpm` со страницы [выпусками][] на компьютер с Red Hat Enterprise Linux.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-222">Download the RPM package `powershell-lts-7.0.0-1.rhel.7.x86_64.rpm` from the [releases][] page onto the Red Hat Enterprise Linux machine.</span></span>

<span data-ttu-id="f6cd6-223">Затем выполните в терминале следующие команды:</span><span class="sxs-lookup"><span data-stu-id="f6cd6-223">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo yum install powershell-lts-7.0.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="f6cd6-224">RPM можно установить без промежуточного скачивания:</span><span class="sxs-lookup"><span data-stu-id="f6cd6-224">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v7.0.0/powershell-lts-7.0.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="f6cd6-225">Удаление — Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="f6cd6-225">Uninstallation - Red Hat Enterprise Linux (RHEL) 7</span></span>

```sh
sudo yum remove powershell
```

## <a name="opensuse"></a><span data-ttu-id="f6cd6-226">openSUSE</span><span class="sxs-lookup"><span data-stu-id="f6cd6-226">openSUSE</span></span>

### <a name="installation---opensuse-423"></a><span data-ttu-id="f6cd6-227">Установка — openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="f6cd6-227">Installation - openSUSE 42.3</span></span>

```sh
# Install dependencies
zypper update && zypper --non-interactive install curl tar libicu52_1

# Download the powershell '.tar.gz' archive
curl -L https://github.com/PowerShell/PowerShell/releases/download/v7.0.0/powershell-7.0.0-linux-x64.tar.gz -o /tmp/powershell.tar.gz

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

### <a name="installation---opensuse-leap-15"></a><span data-ttu-id="f6cd6-228">Установка — openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="f6cd6-228">Installation - openSUSE Leap 15</span></span>

```sh
# Install dependencies
zypper update && zypper --non-interactive install curl tar gzip libopenssl1_0_0 libicu60_2

# Download the powershell '.tar.gz' archive
curl -L https://github.com/PowerShell/PowerShell/releases/download/v7.0.0/powershell-7.0.0-linux-x64.tar.gz -o /tmp/powershell.tar.gz

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

### <a name="uninstallation---opensuse-423-opensuse-leap-15"></a><span data-ttu-id="f6cd6-229">Удаление — openSUSE 42.3, openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="f6cd6-229">Uninstallation - openSUSE 42.3, openSUSE Leap 15</span></span>

```sh
rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="fedora"></a><span data-ttu-id="f6cd6-230">Fedora</span><span class="sxs-lookup"><span data-stu-id="f6cd6-230">Fedora</span></span>

> [!NOTE]
> <span data-ttu-id="f6cd6-231">Fedora 28 поддерживается только в PowerShell 6.1 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-231">Fedora 28 is only supported in PowerShell 6.1 and newer.</span></span>

> [!NOTE]
> <span data-ttu-id="f6cd6-232">Fedora 29 и 30 поддерживается только в PowerShell 7.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-232">Fedora 29 and 30 are only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-package-repository-preferred---fedora-28-29-and-30"></a><span data-ttu-id="f6cd6-233">Установка с помощью репозитория пакетов (рекомендуется) — Fedora 28, 29 и 30</span><span class="sxs-lookup"><span data-stu-id="f6cd6-233">Installation via Package Repository (preferred) - Fedora 28, 29, and 30</span></span>

<span data-ttu-id="f6cd6-234">Чтобы упростить установку и обновление, PowerShell для Linux публикуется в официальных репозиториях Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-234">PowerShell for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

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

### <a name="installation-via-direct-download---fedora-28-29-and-30"></a><span data-ttu-id="f6cd6-235">Установка с помощью прямого скачивания — Fedora 28, 29 и 30</span><span class="sxs-lookup"><span data-stu-id="f6cd6-235">Installation via Direct Download - Fedora 28, 29, and 30</span></span>

<span data-ttu-id="f6cd6-236">Скачайте пакет RPM `powershell-7.0.0-1.rhel.7.x86_64.rpm` со страницы [выпусками][] на компьютер с Fedora.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-236">Download the RPM package `powershell-7.0.0-1.rhel.7.x86_64.rpm` from the [releases][] page onto the Fedora machine.</span></span>

<span data-ttu-id="f6cd6-237">Затем выполните в терминале следующие команды:</span><span class="sxs-lookup"><span data-stu-id="f6cd6-237">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install powershell-7.0.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="f6cd6-238">RPM можно установить без промежуточного скачивания:</span><span class="sxs-lookup"><span data-stu-id="f6cd6-238">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install https://github.com/PowerShell/PowerShell/releases/download/v7.0.0/powershell-7.0.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---fedora-28-29-and-30"></a><span data-ttu-id="f6cd6-239">Удаление — Fedora 28, 29 и 30</span><span class="sxs-lookup"><span data-stu-id="f6cd6-239">Uninstallation - Fedora 28, 29, and 30</span></span>

```sh
sudo dnf remove powershell
```

## <a name="arch-linux"></a><span data-ttu-id="f6cd6-240">Arch Linux</span><span class="sxs-lookup"><span data-stu-id="f6cd6-240">Arch Linux</span></span>

> [!NOTE]
> <span data-ttu-id="f6cd6-241">Arch официально не поддерживается корпорацией Майкрософт, но поддерживается сообществом.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-241">Arch support is not officially supported by Microsoft and is maintained by the community.</span></span>

<span data-ttu-id="f6cd6-242">PowerShell можно получить из пользовательского репозитория [Arch Linux][] (AUR).</span><span class="sxs-lookup"><span data-stu-id="f6cd6-242">PowerShell is available from the [Arch Linux][] User Repository (AUR).</span></span>

- <span data-ttu-id="f6cd6-243">Его можно скомпилировать с помощью [последнего выпуска с тегами][arch-release].</span><span class="sxs-lookup"><span data-stu-id="f6cd6-243">It can be compiled with the [latest tagged release][arch-release]</span></span>
- <span data-ttu-id="f6cd6-244">Его можно скомпилировать из [последней фиксации в основной репозиторий][arch-git].</span><span class="sxs-lookup"><span data-stu-id="f6cd6-244">It can be compiled from the [latest commit to master][arch-git]</span></span>
- <span data-ttu-id="f6cd6-245">Его можно установить с помощью [двоичного файла последнего выпуска][arch-bin].</span><span class="sxs-lookup"><span data-stu-id="f6cd6-245">It can be installed using the [latest release binary][arch-bin]</span></span>

<span data-ttu-id="f6cd6-246">Пакеты в AUR обслуживаются сообществом — официальная поддержка не предусмотрена.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-246">Packages in the AUR are community maintained; there's no official support.</span></span>

<span data-ttu-id="f6cd6-247">Дополнительные сведения об установке пакетов из AUR см. на [вики-сайте Arch Linux](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) или в статье [Использование PowerShell в Docker](powershell-in-docker.md).</span><span class="sxs-lookup"><span data-stu-id="f6cd6-247">For more information on installing packages from the AUR, see the [Arch Linux wiki](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) or [Using PowerShell in Docker](powershell-in-docker.md).</span></span>

[Arch Linux]: https://www.archlinux.org/download/
[arch-release]: https://aur.archlinux.org/packages/powershell/
[arch-git]: https://aur.archlinux.org/packages/powershell-git/
[arch-bin]: https://aur.archlinux.org/packages/powershell-bin/

## <a name="snap-package"></a><span data-ttu-id="f6cd6-249">Snap-пакет</span><span class="sxs-lookup"><span data-stu-id="f6cd6-249">Snap Package</span></span>

### <a name="getting-snapd"></a><span data-ttu-id="f6cd6-250">Установка Snap</span><span class="sxs-lookup"><span data-stu-id="f6cd6-250">Getting snapd</span></span>

<span data-ttu-id="f6cd6-251">Утилита `snapd` необходима для запуска snap-пакетов.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-251">`snapd` is required to run snaps.</span></span> <span data-ttu-id="f6cd6-252">Чтобы убедиться, что утилита `snapd` установлена, воспользуйтесь [этими инструкциями](https://docs.snapcraft.io/core/install).</span><span class="sxs-lookup"><span data-stu-id="f6cd6-252">Use [these instructions](https://docs.snapcraft.io/core/install) to make sure you have `snapd` installed.</span></span>

### <a name="installation-via-snap"></a><span data-ttu-id="f6cd6-253">Установка с использованием Snap</span><span class="sxs-lookup"><span data-stu-id="f6cd6-253">Installation via Snap</span></span>

<span data-ttu-id="f6cd6-254">Чтобы упростить установку и обновление, PowerShell для Linux публикуется в [хранилище Snap](https://snapcraft.io/store).</span><span class="sxs-lookup"><span data-stu-id="f6cd6-254">PowerShell for Linux is published to the [Snap store](https://snapcraft.io/store) for easy installation and updates.</span></span>

<span data-ttu-id="f6cd6-255">Предпочтительный метод выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f6cd6-255">The preferred method is as follows:</span></span>

```sh
# Install PowerShell
sudo snap install powershell --classic

# Start PowerShell
pwsh
```

<span data-ttu-id="f6cd6-256">Чтобы установить предварительную версию, используйте следующий метод:</span><span class="sxs-lookup"><span data-stu-id="f6cd6-256">To install a preview version, use the following method:</span></span>

```sh
# Install PowerShell
sudo snap install powershell-preview --classic

# Start PowerShell
pwsh-preview
```

<span data-ttu-id="f6cd6-257">После установки Snap автоматически обновится.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-257">After installation, Snap will automatically upgrade.</span></span> <span data-ttu-id="f6cd6-258">Обновление можно активировать с помощью `sudo snap refresh powershell` или `sudo snap refresh powershell-preview`.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-258">You can trigger an upgrade using `sudo snap refresh powershell` or `sudo snap refresh powershell-preview`.</span></span>

### <a name="uninstallation"></a><span data-ttu-id="f6cd6-259">Удаление</span><span class="sxs-lookup"><span data-stu-id="f6cd6-259">Uninstallation</span></span>

```sh
sudo snap remove powershell
```

<span data-ttu-id="f6cd6-260">или диспетчер конфигурации служб</span><span class="sxs-lookup"><span data-stu-id="f6cd6-260">or</span></span>

```sh
sudo snap remove powershell-preview
```

## <a name="kali"></a><span data-ttu-id="f6cd6-261">Kali</span><span class="sxs-lookup"><span data-stu-id="f6cd6-261">Kali</span></span>

> [!NOTE]
> <span data-ttu-id="f6cd6-262">Kali официально не поддерживается корпорацией Майкрософт, но поддерживается сообществом.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-262">Kali support is not officially supported by Microsoft and is maintained by the community.</span></span>

### <a name="installation---kali"></a><span data-ttu-id="f6cd6-263">Установка — Kali</span><span class="sxs-lookup"><span data-stu-id="f6cd6-263">Installation - Kali</span></span>

```sh
# Install PowerShell package
apt update && apt -y install powershell

# Start PowerShell
pwsh
```

### <a name="uninstallation---kali"></a><span data-ttu-id="f6cd6-264">Удаление — Kali</span><span class="sxs-lookup"><span data-stu-id="f6cd6-264">Uninstallation - Kali</span></span>

```sh
# Uninstall PowerShell package
apt -y remove powershell
```

## <a name="raspbian"></a><span data-ttu-id="f6cd6-265">Raspbian</span><span class="sxs-lookup"><span data-stu-id="f6cd6-265">Raspbian</span></span>

> [!NOTE]
> <span data-ttu-id="f6cd6-266">Поддержка Raspbian на этапе эксперимента.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-266">Raspbian support is experimental.</span></span>

<span data-ttu-id="f6cd6-267">Сейчас PowerShell поддерживается только в Raspbian Stretch.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-267">Currently, PowerShell is only supported on Raspbian Stretch.</span></span>

<span data-ttu-id="f6cd6-268">CoreCLR и PowerShell будут работать только на устройствах Pi 2 и Pi 3. На таких устройствах, как [Pi Zero](https://github.com/dotnet/coreclr/issues/10605), установлены процессоры, поддержка которых не предусмотрена.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-268">CoreCLR and PowerShell will only work on Pi 2 and Pi 3 devices as other devices, like [Pi Zero](https://github.com/dotnet/coreclr/issues/10605), have an unsupported processor.</span></span>

<span data-ttu-id="f6cd6-269">Загрузите [Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) и следуйте [инструкциям по установке](https://www.raspberrypi.org/documentation/installation/installing-images/README.md), чтобы установить его на свой Pi.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-269">Download [Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) and follow the [installation instructions](https://www.raspberrypi.org/documentation/installation/installing-images/README.md) to get it onto your Pi.</span></span>

### <a name="installation---raspbian"></a><span data-ttu-id="f6cd6-270">Установка — Raspbian</span><span class="sxs-lookup"><span data-stu-id="f6cd6-270">Installation - Raspbian</span></span>

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
wget https://github.com/PowerShell/PowerShell/releases/download/v7.0.0/powershell-7.0.0-linux-arm32.tar.gz

# Make folder to put powershell
mkdir ~/powershell

# Unpack the tar.gz file
tar -xvf ./powershell-7.0.0-linux-arm32.tar.gz -C ~/powershell

# Start PowerShell
~/powershell/pwsh
```

<span data-ttu-id="f6cd6-271">При необходимости можно создать символьную ссылку для запуска PowerShell без указания пути к двоичному файлу `pwsh`.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-271">Optionally, you can create a symbolic link to start PowerShell without specifying the path to the `pwsh` binary.</span></span>

```sh
# Start PowerShell from bash with sudo to create a symbolic link
sudo ~/powershell/pwsh -c New-Item -ItemType SymbolicLink -Path "/usr/bin/pwsh" -Target "$PSHOME/pwsh" -Force

# alternatively you can run following to create a symbolic link
# sudo ln -s ~/powershell/pwsh /usr/bin/pwsh

# Now to start PowerShell you can just run "pwsh"
```

### <a name="uninstallation---raspbian"></a><span data-ttu-id="f6cd6-272">Удаление — Raspbian</span><span class="sxs-lookup"><span data-stu-id="f6cd6-272">Uninstallation - Raspbian</span></span>

```sh
rm -rf ~/powershell
```

## <a name="installing-preview-releases"></a><span data-ttu-id="f6cd6-273">Установка предварительных выпусков</span><span class="sxs-lookup"><span data-stu-id="f6cd6-273">Installing Preview Releases</span></span>

<span data-ttu-id="f6cd6-274">При установке предварительной версии PowerShell для Linux с помощью репозитория пакетов имя пакета меняется с `powershell` на `powershell-preview`.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-274">When installing a PowerShell Preview release for Linux via a Package Repository, the package name changes from `powershell` to `powershell-preview`.</span></span>

<span data-ttu-id="f6cd6-275">При установке с помощью прямого скачивания изменяется только имя файла.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-275">Installing via direct download doesn't change, other than the file name.</span></span>

<span data-ttu-id="f6cd6-276">В следующей таблице приведены команды для установки пакетов стабильной и предварительной версий с помощью различных диспетчеров пакетов:</span><span class="sxs-lookup"><span data-stu-id="f6cd6-276">The following table contains the commands to install the stable and preview packages using the various package managers:</span></span>

| <span data-ttu-id="f6cd6-277">Дистрибутивы</span><span class="sxs-lookup"><span data-stu-id="f6cd6-277">Distribution(s)</span></span> |            <span data-ttu-id="f6cd6-278">Команда стабильной версии</span><span class="sxs-lookup"><span data-stu-id="f6cd6-278">Stable Command</span></span>            |               <span data-ttu-id="f6cd6-279">Команда предварительной версии</span><span class="sxs-lookup"><span data-stu-id="f6cd6-279">Preview Command</span></span>                |
| --------------- | ------------------------------------ | -------------------------------------------- |
| <span data-ttu-id="f6cd6-280">Ubuntu, Debian</span><span class="sxs-lookup"><span data-stu-id="f6cd6-280">Ubuntu, Debian</span></span>  | `sudo apt-get install -y powershell` | `sudo apt-get install -y powershell-preview` |
| <span data-ttu-id="f6cd6-281">CentOS, RedHat</span><span class="sxs-lookup"><span data-stu-id="f6cd6-281">CentOS, RedHat</span></span>  | `sudo yum install -y powershell`     | `sudo yum install -y powershell-preview`     |
| <span data-ttu-id="f6cd6-282">Fedora</span><span class="sxs-lookup"><span data-stu-id="f6cd6-282">Fedora</span></span>          | `sudo dnf install -y powershell`     | `sudo dnf install -y powershell-preview`     |

## <a name="install-as-a-net-global-tool"></a><span data-ttu-id="f6cd6-283">Установка в качестве глобального средства .NET</span><span class="sxs-lookup"><span data-stu-id="f6cd6-283">Install as a .NET Global tool</span></span>

<span data-ttu-id="f6cd6-284">Если вы уже установили [пакет SDK для .NET Core](/dotnet/core/sdk), установите PowerShell как [глобальное средство .NET](/dotnet/core/tools/global-tools).</span><span class="sxs-lookup"><span data-stu-id="f6cd6-284">If you already have the [.NET Core SDK](/dotnet/core/sdk) installed, it's easy to install PowerShell as a [.NET Global tool](/dotnet/core/tools/global-tools).</span></span>

```
dotnet tool install --global PowerShell
```

<span data-ttu-id="f6cd6-285">Установщик инструмента dotnet добавляет `~/.dotnet/tools` в переменную среды `PATH`.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-285">The dotnet tool installer adds `~/.dotnet/tools` to your `PATH` environment variable.</span></span> <span data-ttu-id="f6cd6-286">Но в выполняющейся оболочке отсутствует обновленная переменная `PATH`.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-286">However, the currently running shell does not have the updated `PATH`.</span></span> <span data-ttu-id="f6cd6-287">Вы можете запустить PowerShell из новой оболочки, введя `pwsh`.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-287">You should be able to start PowerShell from a new shell by typing `pwsh`.</span></span>

## <a name="binary-archives"></a><span data-ttu-id="f6cd6-288">Архивы двоичных файлов</span><span class="sxs-lookup"><span data-stu-id="f6cd6-288">Binary Archives</span></span>

<span data-ttu-id="f6cd6-289">Для поддержки расширенных сценариев развертывания на платформах Linux доступны архивы `tar.gz` двоичных файлов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-289">PowerShell binary `tar.gz` archives are provided for Linux platforms to enable advanced deployment scenarios.</span></span>

### <a name="dependencies"></a><span data-ttu-id="f6cd6-290">Зависимости</span><span class="sxs-lookup"><span data-stu-id="f6cd6-290">Dependencies</span></span>

<span data-ttu-id="f6cd6-291">PowerShell создает переносимые двоичные файлы для всех дистрибутивов Linux.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-291">PowerShell builds portable binaries for all Linux distributions.</span></span> <span data-ttu-id="f6cd6-292">Но среда выполнения .NET Core, как и PowerShell, требует различные зависимости для разных дистрибутивов.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-292">But, .NET Core runtime requires different dependencies on different distributions, and PowerShell does too.</span></span>

<span data-ttu-id="f6cd6-293">На следующей диаграмме показаны официально поддерживаемые зависимости .NET Core 2.0 для различных дистрибутивов Linux.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-293">The following chart shows the .NET Core 2.0 dependencies that are officially supported on different Linux distributions.</span></span>

| <span data-ttu-id="f6cd6-294">OS</span><span class="sxs-lookup"><span data-stu-id="f6cd6-294">OS</span></span>                 | <span data-ttu-id="f6cd6-295">Зависимости</span><span class="sxs-lookup"><span data-stu-id="f6cd6-295">Dependencies</span></span> |
| ------------------ | ------------ |
| <span data-ttu-id="f6cd6-296">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="f6cd6-296">Ubuntu 16.04</span></span>       | <span data-ttu-id="f6cd6-297">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="f6cd6-297">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="f6cd6-298">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu55</span><span class="sxs-lookup"><span data-stu-id="f6cd6-298">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu55</span></span> |
| <span data-ttu-id="f6cd6-299">Ubuntu 17.10</span><span class="sxs-lookup"><span data-stu-id="f6cd6-299">Ubuntu 17.10</span></span>       | <span data-ttu-id="f6cd6-300">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="f6cd6-300">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="f6cd6-301">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu57</span><span class="sxs-lookup"><span data-stu-id="f6cd6-301">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu57</span></span> |
| <span data-ttu-id="f6cd6-302">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="f6cd6-302">Ubuntu 18.04</span></span>       | <span data-ttu-id="f6cd6-303">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="f6cd6-303">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="f6cd6-304">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu60</span><span class="sxs-lookup"><span data-stu-id="f6cd6-304">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu60</span></span> |
| <span data-ttu-id="f6cd6-305">Debian 8 (Jessie)</span><span class="sxs-lookup"><span data-stu-id="f6cd6-305">Debian 8 (Jessie)</span></span>  | <span data-ttu-id="f6cd6-306">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="f6cd6-306">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="f6cd6-307">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span><span class="sxs-lookup"><span data-stu-id="f6cd6-307">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span></span> |
| <span data-ttu-id="f6cd6-308">Debian 9 (Stretch)</span><span class="sxs-lookup"><span data-stu-id="f6cd6-308">Debian 9 (Stretch)</span></span> | <span data-ttu-id="f6cd6-309">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="f6cd6-309">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="f6cd6-310">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.2, libicu57</span><span class="sxs-lookup"><span data-stu-id="f6cd6-310">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.2, libicu57</span></span> |
| <span data-ttu-id="f6cd6-311">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="f6cd6-311">CentOS 7</span></span> <br> <span data-ttu-id="f6cd6-312">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="f6cd6-312">Oracle Linux 7</span></span> <br> <span data-ttu-id="f6cd6-313">RHEL 7</span><span class="sxs-lookup"><span data-stu-id="f6cd6-313">RHEL 7</span></span> | <span data-ttu-id="f6cd6-314">libunwind, libcurl, openssl-libs, libicu</span><span class="sxs-lookup"><span data-stu-id="f6cd6-314">libunwind, libcurl, openssl-libs, libicu</span></span> |
| <span data-ttu-id="f6cd6-315">openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="f6cd6-315">openSUSE 42.3</span></span> | <span data-ttu-id="f6cd6-316">libcurl4, libopenssl1_0_0, libicu52_1</span><span class="sxs-lookup"><span data-stu-id="f6cd6-316">libcurl4, libopenssl1_0_0, libicu52_1</span></span> |
| <span data-ttu-id="f6cd6-317">openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="f6cd6-317">openSUSE Leap 15</span></span> | <span data-ttu-id="f6cd6-318">libcurl4, libopenssl1_0_0, libicu60_2</span><span class="sxs-lookup"><span data-stu-id="f6cd6-318">libcurl4, libopenssl1_0_0, libicu60_2</span></span> |
| <span data-ttu-id="f6cd6-319">Fedora 27</span><span class="sxs-lookup"><span data-stu-id="f6cd6-319">Fedora 27</span></span> <br> <span data-ttu-id="f6cd6-320">Fedora 28</span><span class="sxs-lookup"><span data-stu-id="f6cd6-320">Fedora 28</span></span> | <span data-ttu-id="f6cd6-321">libunwind, libcurl, openssl-libs, libicu, compat-openssl10</span><span class="sxs-lookup"><span data-stu-id="f6cd6-321">libunwind, libcurl, openssl-libs, libicu, compat-openssl10</span></span> |

<span data-ttu-id="f6cd6-322">Чтобы развернуть двоичные файлы PowerShell в дистрибутивах Linux, для которых официальная поддержка не предусмотрена, необходимо специально установить необходимые пакеты, чтобы выполнить все требования, касающиеся зависимостей, для целевой ОС.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-322">To deploy PowerShell binaries on Linux distributions that aren't officially supported, you need to install the necessary dependencies for the target OS in separate steps.</span></span> <span data-ttu-id="f6cd6-323">Например, наш [Dockerfile для Amazon Linux][amazon-dockerfile] сначала устанавливает зависимости, а затем извлекает архив Linux `tar.gz`.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-323">For example, our [Amazon Linux dockerfile][amazon-dockerfile] installs dependencies first, and then extracts the Linux `tar.gz` archive.</span></span>

[amazon-dockerfile]: https://github.com/PowerShell/PowerShell-Docker/blob/master/release/community-stable/amazonlinux/docker/Dockerfile

### <a name="installation---binary-archives"></a><span data-ttu-id="f6cd6-324">Установка — архивы двоичных файлов</span><span class="sxs-lookup"><span data-stu-id="f6cd6-324">Installation - Binary Archives</span></span>

#### <a name="linux"></a><span data-ttu-id="f6cd6-325">Linux</span><span class="sxs-lookup"><span data-stu-id="f6cd6-325">Linux</span></span>

```sh
# Download the powershell '.tar.gz' archive
curl -L -o /tmp/powershell.tar.gz https://github.com/PowerShell/PowerShell/releases/download/v7.0.0/powershell-7.0.0-linux-x64.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /opt/microsoft/powershell/7

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/7

# Set execute permissions
sudo chmod +x /opt/microsoft/powershell/7/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /opt/microsoft/powershell/7/pwsh /usr/bin/pwsh
```

### <a name="uninstalling-binary-archives"></a><span data-ttu-id="f6cd6-326">Удаление архивов двоичных файлов</span><span class="sxs-lookup"><span data-stu-id="f6cd6-326">Uninstalling binary archives</span></span>

```sh
sudo rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="paths"></a><span data-ttu-id="f6cd6-327">Пути</span><span class="sxs-lookup"><span data-stu-id="f6cd6-327">Paths</span></span>

- <span data-ttu-id="f6cd6-328">`$PSHOME` имеет значение `/opt/microsoft/powershell/7/`.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-328">`$PSHOME` is `/opt/microsoft/powershell/7/`</span></span>
- <span data-ttu-id="f6cd6-329">Профили пользователей будут считаны из `~/.config/powershell/profile.ps1`.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-329">User profiles will be read from `~/.config/powershell/profile.ps1`</span></span>
- <span data-ttu-id="f6cd6-330">Профили по умолчанию будут считаны из `$PSHOME/profile.ps1`.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-330">Default profiles will be read from `$PSHOME/profile.ps1`</span></span>
- <span data-ttu-id="f6cd6-331">Модули пользователей будут считаны из `~/.local/share/powershell/Modules`.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-331">User modules will be read from `~/.local/share/powershell/Modules`</span></span>
- <span data-ttu-id="f6cd6-332">Общие модули будут считаны из `/usr/local/share/powershell/Modules`.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-332">Shared modules will be read from `/usr/local/share/powershell/Modules`</span></span>
- <span data-ttu-id="f6cd6-333">Модули по умолчанию будут считаны из `$PSHOME/Modules`.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-333">Default modules will be read from `$PSHOME/Modules`</span></span>
- <span data-ttu-id="f6cd6-334">Журнал PSReadline будет записан в `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span><span class="sxs-lookup"><span data-stu-id="f6cd6-334">PSReadLine history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="f6cd6-335">Профили учитывают конфигурацию PowerShell для отдельных узлов, поэтому профили конкретных узлов по умолчанию находятся в `Microsoft.PowerShell_profile.ps1` в тех же расположениях.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-335">The profiles respect PowerShell's per-host configuration, so the default host-specific profiles exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="f6cd6-336">PowerShell отвечает требованиям [спецификации каталога размещения файлов, связанных со средой настольной графической среды (X-сервера), стандартизированного XDG (X Desktop Group)][xdg-bds] в Linux.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-336">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on Linux.</span></span>

[выпусками]: https://github.com/PowerShell/PowerShell/releases/latest
[releases]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
