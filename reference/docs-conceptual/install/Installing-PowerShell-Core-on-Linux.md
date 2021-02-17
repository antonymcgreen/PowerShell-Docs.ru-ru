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
# <a name="installing-powershell-on-linux"></a><span data-ttu-id="7a6b1-103">Установка PowerShell в Linux</span><span class="sxs-lookup"><span data-stu-id="7a6b1-103">Installing PowerShell on Linux</span></span>

<span data-ttu-id="7a6b1-104">Все пакеты доступны на нашей странице [выпусками][] GitHub.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-104">All packages are available on our GitHub [releases][] page.</span></span> <span data-ttu-id="7a6b1-105">После установки пакета запустите `pwsh` из терминала.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-105">After the package is installed, run `pwsh` from a terminal.</span></span> <span data-ttu-id="7a6b1-106">Запустите `pwsh-preview`, если вы установили [выпуск предварительной версии](#installing-preview-releases).</span><span class="sxs-lookup"><span data-stu-id="7a6b1-106">Run `pwsh-preview` if you installed a [Preview release](#installing-preview-releases).</span></span>

> [!NOTE]
> <span data-ttu-id="7a6b1-107">PowerShell 7 является обновлением на месте, при установке которого PowerShell Core 6.x удаляется.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-107">PowerShell 7 is an in-place upgrade that removes PowerShell Core 6.x.</span></span>
>
> <span data-ttu-id="7a6b1-108">Папка `/usr/local/microsoft/powershell/6` заменяется на `/usr/local/microsoft/powershell/7`.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-108">The `/usr/local/microsoft/powershell/6` folder is replaced by `/usr/local/microsoft/powershell/7`.</span></span>
>
> <span data-ttu-id="7a6b1-109">Если вы хотите запускать PowerShell 6 параллельно с PowerShell 7, переустановите PowerShell 6 с использованием [двоичного архива](#binary-archives).</span><span class="sxs-lookup"><span data-stu-id="7a6b1-109">If you need to run PowerShell 6 side-by-side with PowerShell 7, reinstall PowerShell 6 using the [binary archive](#binary-archives) method.</span></span>

<span data-ttu-id="7a6b1-110">Для дистрибутивов Linux без официальной поддержки попробуйте установить PowerShell с помощью [соответствующего Snap-пакета][snap].</span><span class="sxs-lookup"><span data-stu-id="7a6b1-110">For Linux distributions that aren't officially supported, you can try to install PowerShell using the [PowerShell Snap Package][snap].</span></span> <span data-ttu-id="7a6b1-111">Можно также попытаться развернуть двоичные файлы PowerShell напрямую с помощью [архива`tar.gz`][tar] Linux, но при этом нужно отдельно настроить необходимые зависимости с учетом операционной системы.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-111">You can also try deploying PowerShell binaries directly using the Linux [`tar.gz` archive][tar], but you would need to set up the necessary dependencies based on the OS in separate steps.</span></span>

[snap]: #snap-package
[tar]: #binary-archives

<!-- TODO: Update for supported releases v7.0 & v7.1 -->

<span data-ttu-id="7a6b1-112">Официально поддерживаемые выпуски платформы для PowerShell 7.1:</span><span class="sxs-lookup"><span data-stu-id="7a6b1-112">Officially supported platform releases for PowerShell 7.1</span></span>

- <span data-ttu-id="7a6b1-113">Ubuntu 16.04, 18.04 и 20.04 (включая ARM64);</span><span class="sxs-lookup"><span data-stu-id="7a6b1-113">Ubuntu 16.04/18.04/20.04 (including ARM64)</span></span>
- <span data-ttu-id="7a6b1-114">Ubuntu 19.10 (через snap-пакет);</span><span class="sxs-lookup"><span data-stu-id="7a6b1-114">Ubuntu 19.10 (via Snap package)</span></span>
- <span data-ttu-id="7a6b1-115">Debian 9 и 10;</span><span class="sxs-lookup"><span data-stu-id="7a6b1-115">Debian 9/10</span></span>
- <span data-ttu-id="7a6b1-116">CentOS и RHEL 7 и 8;</span><span class="sxs-lookup"><span data-stu-id="7a6b1-116">CentOS and RHEL 7/8</span></span>
- <span data-ttu-id="7a6b1-117">Fedora 30</span><span class="sxs-lookup"><span data-stu-id="7a6b1-117">Fedora 30</span></span>
- <span data-ttu-id="7a6b1-118">Alpine 3.11 и более поздних версий (включая ARM64).</span><span class="sxs-lookup"><span data-stu-id="7a6b1-118">Alpine 3.11+ (including ARM64)</span></span>

<span data-ttu-id="7a6b1-119">Официально поддерживаемые выпуски платформы для PowerShell 7.0:</span><span class="sxs-lookup"><span data-stu-id="7a6b1-119">Officially supported platform releases for PowerShell 7.0</span></span>

- <span data-ttu-id="7a6b1-120">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="7a6b1-120">Ubuntu 16.04</span></span>
- <span data-ttu-id="7a6b1-121">Ubuntu 18.04 и 20.04;</span><span class="sxs-lookup"><span data-stu-id="7a6b1-121">Ubuntu 18.04 and 20.04</span></span>
- <span data-ttu-id="7a6b1-122">Debian 8</span><span class="sxs-lookup"><span data-stu-id="7a6b1-122">Debian 8</span></span>
- <span data-ttu-id="7a6b1-123">Debian 9</span><span class="sxs-lookup"><span data-stu-id="7a6b1-123">Debian 9</span></span>
- <span data-ttu-id="7a6b1-124">Debian 10</span><span class="sxs-lookup"><span data-stu-id="7a6b1-124">Debian 10</span></span>
- <span data-ttu-id="7a6b1-125">Alpine 3.9 и 3.10</span><span class="sxs-lookup"><span data-stu-id="7a6b1-125">Alpine 3.9 and 3.10</span></span>
- <span data-ttu-id="7a6b1-126">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="7a6b1-126">CentOS 7</span></span>
- <span data-ttu-id="7a6b1-127">Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="7a6b1-127">Red Hat Enterprise Linux (RHEL) 7</span></span>
- <span data-ttu-id="7a6b1-128">Fedora 28</span><span class="sxs-lookup"><span data-stu-id="7a6b1-128">Fedora 28</span></span>
- <span data-ttu-id="7a6b1-129">Fedora 29</span><span class="sxs-lookup"><span data-stu-id="7a6b1-129">Fedora 29</span></span>
- <span data-ttu-id="7a6b1-130">Fedora 30</span><span class="sxs-lookup"><span data-stu-id="7a6b1-130">Fedora 30</span></span>
- <span data-ttu-id="7a6b1-131">openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="7a6b1-131">openSUSE 42.3</span></span>
- <span data-ttu-id="7a6b1-132">openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="7a6b1-132">openSUSE Leap 15</span></span>

<span data-ttu-id="7a6b1-133">Выпуски, поддерживаемые сообществом:</span><span class="sxs-lookup"><span data-stu-id="7a6b1-133">Community supported releases</span></span>

- <span data-ttu-id="7a6b1-134">Ubuntu 18.10</span><span class="sxs-lookup"><span data-stu-id="7a6b1-134">Ubuntu 18.10</span></span>
- <span data-ttu-id="7a6b1-135">Ubuntu 19.10 и 20.10;</span><span class="sxs-lookup"><span data-stu-id="7a6b1-135">Ubuntu 19.10 and 20.10</span></span>
- <span data-ttu-id="7a6b1-136">Arch Linux</span><span class="sxs-lookup"><span data-stu-id="7a6b1-136">Arch Linux</span></span>
- <span data-ttu-id="7a6b1-137">Kali</span><span class="sxs-lookup"><span data-stu-id="7a6b1-137">Kali</span></span>
- <span data-ttu-id="7a6b1-138">Raspbian (экспериментальная версия)</span><span class="sxs-lookup"><span data-stu-id="7a6b1-138">Raspbian (experimental)</span></span>

<span data-ttu-id="7a6b1-139">Альтернативные методы установки</span><span class="sxs-lookup"><span data-stu-id="7a6b1-139">Alternate install methods</span></span>

- <span data-ttu-id="7a6b1-140">Snap-пакет</span><span class="sxs-lookup"><span data-stu-id="7a6b1-140">Snap Package</span></span>
- <span data-ttu-id="7a6b1-141">Архивы двоичных файлов</span><span class="sxs-lookup"><span data-stu-id="7a6b1-141">Binary Archives</span></span>
- <span data-ttu-id="7a6b1-142">Глобальный инструмент .NET</span><span class="sxs-lookup"><span data-stu-id="7a6b1-142">.NET Global tool</span></span>

## <a name="ubuntu-1604"></a><span data-ttu-id="7a6b1-143">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="7a6b1-143">Ubuntu 16.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1604"></a><span data-ttu-id="7a6b1-144">Установка с помощью репозитория пакетов — Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="7a6b1-144">Installation via Package Repository - Ubuntu 16.04</span></span>

<span data-ttu-id="7a6b1-145">Чтобы упростить установку и обновление, PowerShell для Linux публикуется в репозиториях пакетов.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-145">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="7a6b1-146">Предпочтительный метод выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7a6b1-146">The preferred method is as follows:</span></span>

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

<span data-ttu-id="7a6b1-147">В качестве суперпользователя однократно зарегистрируйте репозиторий Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-147">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="7a6b1-148">После регистрации можно обновить PowerShell с помощью `sudo apt-get install powershell`.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-148">After registration, you can update PowerShell with `sudo apt-get install powershell`.</span></span>

### <a name="installation-via-direct-download---ubuntu-1604"></a><span data-ttu-id="7a6b1-149">Установка с помощью прямого скачивания — Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="7a6b1-149">Installation via Direct Download - Ubuntu 16.04</span></span>

<span data-ttu-id="7a6b1-150">Скачайте пакет Debian `powershell_7.1.2-1.ubuntu.16.04_amd64.deb` со страницы [выпусками][] на компьютер с Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-150">Download the Debian package `powershell_7.1.2-1.ubuntu.16.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="7a6b1-151">Затем выполните в терминале следующие команды:</span><span class="sxs-lookup"><span data-stu-id="7a6b1-151">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell_7.1.2-1.ubuntu.16.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="7a6b1-152">Команда `dpkg -i` завершается ошибкой при наличии несопоставленных зависимостей.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-152">The `dpkg -i` command fails with unmet dependencies.</span></span> <span data-ttu-id="7a6b1-153">Следующая команда, `apt-get install -f`, разрешает эти ошибки и завершает настройку пакета PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-153">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1604"></a><span data-ttu-id="7a6b1-154">Удаление — Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="7a6b1-154">Uninstallation - Ubuntu 16.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1804"></a><span data-ttu-id="7a6b1-155">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="7a6b1-155">Ubuntu 18.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1804"></a><span data-ttu-id="7a6b1-156">Установка с помощью репозитория пакетов — Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="7a6b1-156">Installation via Package Repository - Ubuntu 18.04</span></span>

<span data-ttu-id="7a6b1-157">Чтобы упростить установку и обновление, PowerShell для Linux публикуется в репозиториях пакетов.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-157">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="7a6b1-158">Предпочтительный метод выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7a6b1-158">The preferred method is as follows:</span></span>

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

<span data-ttu-id="7a6b1-159">В качестве суперпользователя однократно зарегистрируйте репозиторий Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-159">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="7a6b1-160">После регистрации можно обновить PowerShell с помощью `sudo apt-get install powershell`.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-160">After registration, you can update PowerShell with `sudo apt-get install powershell`.</span></span>

### <a name="installation-via-direct-download---ubuntu-1804"></a><span data-ttu-id="7a6b1-161">Установка с помощью прямого скачивания — Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="7a6b1-161">Installation via Direct Download - Ubuntu 18.04</span></span>

<span data-ttu-id="7a6b1-162">Скачайте пакет Debian `powershell_7.1.2-1.ubuntu.18.04_amd64.deb` со страницы [выпусками][] на компьютер с Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-162">Download the Debian package `powershell_7.1.2-1.ubuntu.18.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="7a6b1-163">Затем выполните в терминале следующие команды:</span><span class="sxs-lookup"><span data-stu-id="7a6b1-163">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell_7.1.2-1.ubuntu.18.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="7a6b1-164">Команда `dpkg -i` завершается ошибкой при наличии несопоставленных зависимостей.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-164">The `dpkg -i` command fails with unmet dependencies.</span></span> <span data-ttu-id="7a6b1-165">Следующая команда, `apt-get install -f`, разрешает эти ошибки и завершает настройку пакета PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-165">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1804"></a><span data-ttu-id="7a6b1-166">Удаление — Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="7a6b1-166">Uninstallation - Ubuntu 18.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-2004"></a><span data-ttu-id="7a6b1-167">Ubuntu 20.04</span><span class="sxs-lookup"><span data-stu-id="7a6b1-167">Ubuntu 20.04</span></span>

### <a name="installation-via-package-repository---ubuntu-2004"></a><span data-ttu-id="7a6b1-168">Установка с помощью репозитория пакетов — Ubuntu 20.04</span><span class="sxs-lookup"><span data-stu-id="7a6b1-168">Installation via Package Repository - Ubuntu 20.04</span></span>

<span data-ttu-id="7a6b1-169">Чтобы упростить установку и обновление, PowerShell для Linux публикуется в репозиториях пакетов.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-169">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="7a6b1-170">Предпочтительный метод выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7a6b1-170">The preferred method is as follows:</span></span>

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

<span data-ttu-id="7a6b1-171">В качестве суперпользователя однократно зарегистрируйте репозиторий Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-171">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="7a6b1-172">После регистрации можно обновить PowerShell с помощью `sudo apt-get install powershell`.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-172">After registration, you can update PowerShell with `sudo apt-get install powershell`.</span></span>

### <a name="installation-via-direct-download---ubuntu-2004"></a><span data-ttu-id="7a6b1-173">Установка с помощью прямого скачивания — Ubuntu 20.04</span><span class="sxs-lookup"><span data-stu-id="7a6b1-173">Installation via Direct Download - Ubuntu 20.04</span></span>

<span data-ttu-id="7a6b1-174">Скачайте пакет Debian `powershell_7.1.2-1.ubuntu.20.04_amd64.deb` со страницы [выпусками][] на компьютер с Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-174">Download the Debian package `powershell_7.1.2-1.ubuntu.20.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="7a6b1-175">Затем выполните в терминале следующие команды:</span><span class="sxs-lookup"><span data-stu-id="7a6b1-175">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell_7.1.2-1.ubuntu.20.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="7a6b1-176">Команда `dpkg -i` завершается ошибкой при наличии несопоставленных зависимостей.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-176">The `dpkg -i` command fails with unmet dependencies.</span></span> <span data-ttu-id="7a6b1-177">Следующая команда, `apt-get install -f`, разрешает эти ошибки и завершает настройку пакета PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-177">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-2004"></a><span data-ttu-id="7a6b1-178">Удаление — Ubuntu 20.04</span><span class="sxs-lookup"><span data-stu-id="7a6b1-178">Uninstallation - Ubuntu 20.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1810"></a><span data-ttu-id="7a6b1-179">Ubuntu 18.10</span><span class="sxs-lookup"><span data-stu-id="7a6b1-179">Ubuntu 18.10</span></span>

<span data-ttu-id="7a6b1-180">Поддерживается только установка с помощью `snapd`.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-180">Installation is supported via `snapd`.</span></span> <span data-ttu-id="7a6b1-181">Инструкции см. в разделе о [snap-пакете][snap].</span><span class="sxs-lookup"><span data-stu-id="7a6b1-181">For instructions, see [Snap Package][snap].</span></span>

> [!NOTE]
> <span data-ttu-id="7a6b1-182">Ubuntu 18.10 — [промежуточный выпуск](https://www.ubuntu.com/about/release-cycle), который [поддерживается сообществом](../powershell-support-lifecycle.md).</span><span class="sxs-lookup"><span data-stu-id="7a6b1-182">Ubuntu 18.10 is an [interim release](https://www.ubuntu.com/about/release-cycle) that's [community supported](../powershell-support-lifecycle.md).</span></span>

## <a name="ubuntu-1910-and-2010"></a><span data-ttu-id="7a6b1-183">Ubuntu 19.10 и 20.10;</span><span class="sxs-lookup"><span data-stu-id="7a6b1-183">Ubuntu 19.10 and 20.10</span></span>

<span data-ttu-id="7a6b1-184">Поддерживается только установка с помощью `snapd`.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-184">Installation is supported via `snapd`.</span></span> <span data-ttu-id="7a6b1-185">Инструкции см. в разделе о [snap-пакете][snap].</span><span class="sxs-lookup"><span data-stu-id="7a6b1-185">For instructions, see [Snap Package][snap].</span></span>

> [!NOTE]
> <span data-ttu-id="7a6b1-186">Ubuntu 19.10 — [промежуточный выпуск](https://www.ubuntu.com/about/release-cycle), который [поддерживается сообществом](../powershell-support-lifecycle.md).</span><span class="sxs-lookup"><span data-stu-id="7a6b1-186">Ubuntu 19.10 is an [interim release](https://www.ubuntu.com/about/release-cycle) that's [community supported](../powershell-support-lifecycle.md).</span></span>

## <a name="debian-8"></a><span data-ttu-id="7a6b1-187">Debian 8</span><span class="sxs-lookup"><span data-stu-id="7a6b1-187">Debian 8</span></span>

### <a name="installation-via-package-repository---debian-8"></a><span data-ttu-id="7a6b1-188">Установка с помощью репозитория пакетов — Debian 8</span><span class="sxs-lookup"><span data-stu-id="7a6b1-188">Installation via Package Repository - Debian 8</span></span>

<span data-ttu-id="7a6b1-189">Чтобы упростить установку и обновление, PowerShell для Linux публикуется в репозиториях пакетов.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-189">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="7a6b1-190">Предпочтительный метод выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7a6b1-190">The preferred method is as follows:</span></span>

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

<span data-ttu-id="7a6b1-191">В качестве суперпользователя однократно зарегистрируйте репозиторий Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-191">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="7a6b1-192">После регистрации можно обновить PowerShell с помощью `sudo apt-get install powershell`.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-192">After registration, you can update PowerShell with `sudo apt-get install powershell`.</span></span>

## <a name="debian-9"></a><span data-ttu-id="7a6b1-193">Debian 9</span><span class="sxs-lookup"><span data-stu-id="7a6b1-193">Debian 9</span></span>

### <a name="installation-via-package-repository---debian-9"></a><span data-ttu-id="7a6b1-194">Установка с помощью репозитория пакетов — Debian 9</span><span class="sxs-lookup"><span data-stu-id="7a6b1-194">Installation via Package Repository - Debian 9</span></span>

<span data-ttu-id="7a6b1-195">Чтобы упростить установку и обновление, PowerShell для Linux публикуется в репозиториях пакетов.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-195">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="7a6b1-196">Предпочтительный метод выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7a6b1-196">The preferred method is as follows:</span></span>

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

<span data-ttu-id="7a6b1-197">В качестве суперпользователя однократно зарегистрируйте репозиторий Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-197">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="7a6b1-198">После регистрации можно обновить PowerShell с помощью `sudo apt-get install powershell`.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-198">After registration, you can update PowerShell with `sudo apt-get install powershell`.</span></span>

### <a name="installation-via-direct-download---debian-9"></a><span data-ttu-id="7a6b1-199">Установка с помощью прямого скачивания — Debian 9</span><span class="sxs-lookup"><span data-stu-id="7a6b1-199">Installation via Direct Download - Debian 9</span></span>

<span data-ttu-id="7a6b1-200">Скачайте пакет Debian `powershell_7.1.2-1.debian.9_amd64.deb` со страницы [выпусками][] на компьютер с Debian.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-200">Download the Debian package `powershell_7.1.2-1.debian.9_amd64.deb` from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="7a6b1-201">Затем выполните в терминале следующие команды:</span><span class="sxs-lookup"><span data-stu-id="7a6b1-201">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell_7.1.2-1.debian.9_amd64.deb
sudo apt-get install -f
```

### <a name="uninstallation---debian-9"></a><span data-ttu-id="7a6b1-202">Удаление — Debian 9</span><span class="sxs-lookup"><span data-stu-id="7a6b1-202">Uninstallation - Debian 9</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="debian-10"></a><span data-ttu-id="7a6b1-203">Debian 10</span><span class="sxs-lookup"><span data-stu-id="7a6b1-203">Debian 10</span></span>

> [!NOTE]
> <span data-ttu-id="7a6b1-204">Debian 10 поддерживается только в PowerShell 7.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-204">Debian 10 is only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-package-repository---debian-10"></a><span data-ttu-id="7a6b1-205">Установка с помощью репозитория пакетов — Debian 10</span><span class="sxs-lookup"><span data-stu-id="7a6b1-205">Installation via Package Repository - Debian 10</span></span>

<span data-ttu-id="7a6b1-206">Чтобы упростить установку и обновление, PowerShell для Linux публикуется в репозиториях пакетов.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-206">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="7a6b1-207">Предпочтительный метод выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7a6b1-207">The preferred method is as follows:</span></span>

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

### <a name="installation-via-direct-download---debian-10"></a><span data-ttu-id="7a6b1-208">Установка с помощью прямого скачивания — Debian 10</span><span class="sxs-lookup"><span data-stu-id="7a6b1-208">Installation via Direct Download - Debian 10</span></span>

<span data-ttu-id="7a6b1-209">Скачайте пакет tar.gz `powershell-7.1.2-linux-x64.tar.gz` на странице с [выпусками][] на компьютер с Debian.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-209">Download the tar.gz package `powershell-7.1.2-linux-x64.tar.gz` from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="7a6b1-210">Затем выполните в терминале следующие команды:</span><span class="sxs-lookup"><span data-stu-id="7a6b1-210">Then, in the terminal, execute the following commands:</span></span>

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

## <a name="alpine-39-and-310"></a><span data-ttu-id="7a6b1-211">Alpine 3.9 и 3.10</span><span class="sxs-lookup"><span data-stu-id="7a6b1-211">Alpine 3.9 and 3.10</span></span>

> [!NOTE]
> <span data-ttu-id="7a6b1-212">Alpine 3.9 и 3.10 поддерживается только в PowerShell 7.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-212">Alpine 3.9 and 3.10 are only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-direct-download---alpine-39-and-310"></a><span data-ttu-id="7a6b1-213">Установка с помощью прямого скачивания — Alpine 3.9 и 3.10</span><span class="sxs-lookup"><span data-stu-id="7a6b1-213">Installation via Direct Download - Alpine 3.9 and 3.10</span></span>

<span data-ttu-id="7a6b1-214">Скачайте пакет tar.gz `powershell-7.1.2-linux-alpine-x64.tar.gz` на странице с [выпусками][] на компьютер с Alpine.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-214">Download the tar.gz package `powershell-7.1.2-linux-alpine-x64.tar.gz` from the [releases][] page onto the Alpine machine.</span></span>

<span data-ttu-id="7a6b1-215">Затем выполните в терминале следующие команды:</span><span class="sxs-lookup"><span data-stu-id="7a6b1-215">Then, in the terminal, execute the following commands:</span></span>

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

## <a name="centos-7"></a><span data-ttu-id="7a6b1-216">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="7a6b1-216">CentOS 7</span></span>

> [!NOTE]
> <span data-ttu-id="7a6b1-217">Этот пакет работает в Oracle Linux 7.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-217">This package works on Oracle Linux 7.</span></span>

### <a name="installation-via-package-repository-preferred---centos-7"></a><span data-ttu-id="7a6b1-218">Установка с помощью репозитория пакетов (рекомендуется) — CentOS 7</span><span class="sxs-lookup"><span data-stu-id="7a6b1-218">Installation via Package Repository (preferred) - CentOS 7</span></span>

<span data-ttu-id="7a6b1-219">Чтобы упростить установку и обновление, PowerShell для Linux публикуется в официальных репозиториях Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-219">PowerShell for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="7a6b1-220">В качестве суперпользователя однократно зарегистрируйте репозиторий Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-220">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="7a6b1-221">После регистрации можно обновить PowerShell с помощью `sudo yum update powershell`.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-221">After registration, you can update PowerShell with `sudo yum update powershell`.</span></span>

### <a name="installation-via-direct-download---centos-7"></a><span data-ttu-id="7a6b1-222">Установка с помощью прямого скачивания — CentOS 7</span><span class="sxs-lookup"><span data-stu-id="7a6b1-222">Installation via Direct Download - CentOS 7</span></span>

<span data-ttu-id="7a6b1-223">Используя [CentOS 7][], скачайте пакет RPM `powershell-7.1.2-1.rhel.7.x86_64.rpm` со страницы [выпусками][] на компьютер с CentOS.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-223">Using [CentOS 7][], download the RPM package `powershell-7.1.2-1.rhel.7.x86_64.rpm` from the [releases][] page onto the CentOS machine.</span></span>

<span data-ttu-id="7a6b1-224">Затем выполните в терминале следующие команды:</span><span class="sxs-lookup"><span data-stu-id="7a6b1-224">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo yum install powershell-7.1.2-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="7a6b1-225">RPM можно установить без промежуточного скачивания:</span><span class="sxs-lookup"><span data-stu-id="7a6b1-225">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v7.1.2/powershell-7.1.2-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---centos-7"></a><span data-ttu-id="7a6b1-226">Удаление — CentOS 7</span><span class="sxs-lookup"><span data-stu-id="7a6b1-226">Uninstallation - CentOS 7</span></span>

```sh
sudo yum remove powershell
```

[CentOS 7]: https://www.centos.org/download/

## <a name="red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="7a6b1-228">Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="7a6b1-228">Red Hat Enterprise Linux (RHEL) 7</span></span>

### <a name="installation-via-package-repository-preferred---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="7a6b1-229">Установка с помощью репозитория пакетов (рекомендуется) — Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="7a6b1-229">Installation via Package Repository (preferred) - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="7a6b1-230">Чтобы упростить установку и обновление, PowerShell для Linux публикуется в официальных репозиториях Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-230">PowerShell for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="7a6b1-231">В качестве суперпользователя однократно зарегистрируйте репозиторий Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-231">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="7a6b1-232">После регистрации можно обновить PowerShell с помощью `sudo yum update powershell`.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-232">After registration, you can update PowerShell with `sudo yum update powershell`.</span></span>

### <a name="installation-via-direct-download---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="7a6b1-233">Установка с помощью прямого скачивания — Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="7a6b1-233">Installation via Direct Download - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="7a6b1-234">Скачайте пакет RPM `powershell-7.1.2-1.rhel.7.x86_64.rpm` со страницы [выпусками][] на компьютер с Red Hat Enterprise Linux.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-234">Download the RPM package `powershell-7.1.2-1.rhel.7.x86_64.rpm` from the [releases][] page onto the Red Hat Enterprise Linux machine.</span></span>

<span data-ttu-id="7a6b1-235">Затем выполните в терминале следующие команды:</span><span class="sxs-lookup"><span data-stu-id="7a6b1-235">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo yum install powershell-7.1.2-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="7a6b1-236">RPM можно установить без промежуточного скачивания:</span><span class="sxs-lookup"><span data-stu-id="7a6b1-236">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v7.1.2/powershell-7.1.2-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="7a6b1-237">Удаление — Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="7a6b1-237">Uninstallation - Red Hat Enterprise Linux (RHEL) 7</span></span>

```sh
sudo yum remove powershell
```

## <a name="opensuse"></a><span data-ttu-id="7a6b1-238">openSUSE</span><span class="sxs-lookup"><span data-stu-id="7a6b1-238">openSUSE</span></span>

### <a name="installation---opensuse-423"></a><span data-ttu-id="7a6b1-239">Установка — openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="7a6b1-239">Installation - openSUSE 42.3</span></span>

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

### <a name="installation---opensuse-leap-15"></a><span data-ttu-id="7a6b1-240">Установка — openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="7a6b1-240">Installation - openSUSE Leap 15</span></span>

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

### <a name="uninstallation---opensuse-423-opensuse-leap-15"></a><span data-ttu-id="7a6b1-241">Удаление — openSUSE 42.3, openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="7a6b1-241">Uninstallation - openSUSE 42.3, openSUSE Leap 15</span></span>

```sh
rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="fedora"></a><span data-ttu-id="7a6b1-242">Fedora</span><span class="sxs-lookup"><span data-stu-id="7a6b1-242">Fedora</span></span>

> [!NOTE]
> <span data-ttu-id="7a6b1-243">Fedora 28 поддерживается только в PowerShell 6.1 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-243">Fedora 28 is only supported in PowerShell 6.1 and newer.</span></span>

> [!NOTE]
> <span data-ttu-id="7a6b1-244">Fedora 29 и 30 поддерживается только в PowerShell 7.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-244">Fedora 29 and 30 are only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-package-repository-preferred---fedora-28-29-and-30"></a><span data-ttu-id="7a6b1-245">Установка с помощью репозитория пакетов (рекомендуется) — Fedora 28, 29 и 30</span><span class="sxs-lookup"><span data-stu-id="7a6b1-245">Installation via Package Repository (preferred) - Fedora 28, 29, and 30</span></span>

<span data-ttu-id="7a6b1-246">Чтобы упростить установку и обновление, PowerShell для Linux публикуется в официальных репозиториях Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-246">PowerShell for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

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

### <a name="installation-via-direct-download---fedora-28-29-and-30"></a><span data-ttu-id="7a6b1-247">Установка с помощью прямого скачивания — Fedora 28, 29 и 30</span><span class="sxs-lookup"><span data-stu-id="7a6b1-247">Installation via Direct Download - Fedora 28, 29, and 30</span></span>

<span data-ttu-id="7a6b1-248">Скачайте пакет RPM `powershell-7.1.2-1.rhel.7.x86_64.rpm` со страницы [выпусками][] на компьютер с Fedora.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-248">Download the RPM package `powershell-7.1.2-1.rhel.7.x86_64.rpm` from the [releases][] page onto the Fedora machine.</span></span>

<span data-ttu-id="7a6b1-249">Затем выполните в терминале следующие команды:</span><span class="sxs-lookup"><span data-stu-id="7a6b1-249">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install powershell-7.1.2-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="7a6b1-250">RPM можно установить без промежуточного скачивания:</span><span class="sxs-lookup"><span data-stu-id="7a6b1-250">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install https://github.com/PowerShell/PowerShell/releases/download/v7.1.2/powershell-7.1.2-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---fedora-28-29-and-30"></a><span data-ttu-id="7a6b1-251">Удаление — Fedora 28, 29 и 30</span><span class="sxs-lookup"><span data-stu-id="7a6b1-251">Uninstallation - Fedora 28, 29, and 30</span></span>

```sh
sudo dnf remove powershell
```

## <a name="arch-linux"></a><span data-ttu-id="7a6b1-252">Arch Linux</span><span class="sxs-lookup"><span data-stu-id="7a6b1-252">Arch Linux</span></span>

> [!NOTE]
> <span data-ttu-id="7a6b1-253">Arch официально не поддерживается корпорацией Майкрософт, но поддерживается сообществом.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-253">Arch support is not officially supported by Microsoft and is maintained by the community.</span></span>

<span data-ttu-id="7a6b1-254">PowerShell можно получить из пользовательского репозитория [Arch Linux][] (AUR).</span><span class="sxs-lookup"><span data-stu-id="7a6b1-254">PowerShell is available from the [Arch Linux][] User Repository (AUR).</span></span>

- <span data-ttu-id="7a6b1-255">Его можно скомпилировать с помощью [последнего выпуска с тегами][arch-release].</span><span class="sxs-lookup"><span data-stu-id="7a6b1-255">It can be compiled with the [latest tagged release][arch-release]</span></span>
- <span data-ttu-id="7a6b1-256">Его можно скомпилировать из [последней фиксации в основной репозиторий][arch-git].</span><span class="sxs-lookup"><span data-stu-id="7a6b1-256">It can be compiled from the [latest commit to master][arch-git]</span></span>
- <span data-ttu-id="7a6b1-257">Его можно установить с помощью [двоичного файла последнего выпуска][arch-bin].</span><span class="sxs-lookup"><span data-stu-id="7a6b1-257">It can be installed using the [latest release binary][arch-bin]</span></span>

<span data-ttu-id="7a6b1-258">Пакеты в AUR обслуживаются сообществом — официальная поддержка не предусмотрена.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-258">Packages in the AUR are community maintained; there's no official support.</span></span>

<span data-ttu-id="7a6b1-259">Дополнительные сведения об установке пакетов из AUR см. на [вики-сайте Arch Linux](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) или в статье [Использование PowerShell в Docker](powershell-in-docker.md).</span><span class="sxs-lookup"><span data-stu-id="7a6b1-259">For more information on installing packages from the AUR, see the [Arch Linux wiki](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) or [Using PowerShell in Docker](powershell-in-docker.md).</span></span>

[Arch Linux]: https://www.archlinux.org/download/
[arch-release]: https://aur.archlinux.org/packages/powershell/
[arch-git]: https://aur.archlinux.org/packages/powershell-git/
[arch-bin]: https://aur.archlinux.org/packages/powershell-bin/

## <a name="snap-package"></a><span data-ttu-id="7a6b1-261">Snap-пакет</span><span class="sxs-lookup"><span data-stu-id="7a6b1-261">Snap Package</span></span>

### <a name="getting-snapd"></a><span data-ttu-id="7a6b1-262">Установка Snap</span><span class="sxs-lookup"><span data-stu-id="7a6b1-262">Getting snapd</span></span>

<span data-ttu-id="7a6b1-263">Утилита `snapd` необходима для запуска snap-пакетов.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-263">`snapd` is required to run snaps.</span></span> <span data-ttu-id="7a6b1-264">Чтобы убедиться, что утилита `snapd` установлена, воспользуйтесь [этими инструкциями](https://docs.snapcraft.io/core/install).</span><span class="sxs-lookup"><span data-stu-id="7a6b1-264">Use [these instructions](https://docs.snapcraft.io/core/install) to make sure you have `snapd` installed.</span></span>

### <a name="installation-via-snap"></a><span data-ttu-id="7a6b1-265">Установка с использованием Snap</span><span class="sxs-lookup"><span data-stu-id="7a6b1-265">Installation via Snap</span></span>

<span data-ttu-id="7a6b1-266">Чтобы упростить установку и обновление, PowerShell для Linux публикуется в [хранилище Snap](https://snapcraft.io/store).</span><span class="sxs-lookup"><span data-stu-id="7a6b1-266">PowerShell for Linux is published to the [Snap store](https://snapcraft.io/store) for easy installation and updates.</span></span>

<span data-ttu-id="7a6b1-267">Предпочтительный метод выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7a6b1-267">The preferred method is as follows:</span></span>

```sh
# Install PowerShell
sudo snap install powershell --classic

# Start PowerShell
pwsh
```

<span data-ttu-id="7a6b1-268">Чтобы установить предварительную версию, используйте следующий метод:</span><span class="sxs-lookup"><span data-stu-id="7a6b1-268">To install a preview version, use the following method:</span></span>

```sh
# Install PowerShell
sudo snap install powershell-preview --classic

# Start PowerShell
pwsh-preview
```

<span data-ttu-id="7a6b1-269">После установки Snap автоматически обновится.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-269">After installation, Snap will automatically upgrade.</span></span> <span data-ttu-id="7a6b1-270">Обновление можно активировать с помощью `sudo snap refresh powershell` или `sudo snap refresh powershell-preview`.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-270">You can trigger an upgrade using `sudo snap refresh powershell` or `sudo snap refresh powershell-preview`.</span></span>

### <a name="uninstallation"></a><span data-ttu-id="7a6b1-271">Удаление</span><span class="sxs-lookup"><span data-stu-id="7a6b1-271">Uninstallation</span></span>

```sh
sudo snap remove powershell
```

<span data-ttu-id="7a6b1-272">или диспетчер конфигурации служб</span><span class="sxs-lookup"><span data-stu-id="7a6b1-272">or</span></span>

```sh
sudo snap remove powershell-preview
```

## <a name="kali"></a><span data-ttu-id="7a6b1-273">Kali</span><span class="sxs-lookup"><span data-stu-id="7a6b1-273">Kali</span></span>

> [!NOTE]
> <span data-ttu-id="7a6b1-274">Kali официально не поддерживается корпорацией Майкрософт, но поддерживается сообществом.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-274">Kali support is not officially supported by Microsoft and is maintained by the community.</span></span>

### <a name="installation---kali"></a><span data-ttu-id="7a6b1-275">Установка — Kali</span><span class="sxs-lookup"><span data-stu-id="7a6b1-275">Installation - Kali</span></span>

```sh
# Install PowerShell package
apt update && apt -y install powershell

# Start PowerShell
pwsh
```

### <a name="uninstallation---kali"></a><span data-ttu-id="7a6b1-276">Удаление — Kali</span><span class="sxs-lookup"><span data-stu-id="7a6b1-276">Uninstallation - Kali</span></span>

```sh
# Uninstall PowerShell package
apt -y remove powershell
```

## <a name="raspbian"></a><span data-ttu-id="7a6b1-277">Raspbian</span><span class="sxs-lookup"><span data-stu-id="7a6b1-277">Raspbian</span></span>

> [!NOTE]
> <span data-ttu-id="7a6b1-278">Поддержка Raspbian на этапе эксперимента.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-278">Raspbian support is experimental.</span></span>

<span data-ttu-id="7a6b1-279">Сейчас PowerShell поддерживается только в Raspbian Stretch.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-279">Currently, PowerShell is only supported on Raspbian Stretch.</span></span>

<span data-ttu-id="7a6b1-280">CoreCLR и PowerShell будут работать только на устройствах Pi 2 и Pi 3. На таких устройствах, как [Pi Zero](https://github.com/dotnet/coreclr/issues/10605), установлены процессоры, поддержка которых не предусмотрена.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-280">CoreCLR and PowerShell will only work on Pi 2 and Pi 3 devices as other devices, like [Pi Zero](https://github.com/dotnet/coreclr/issues/10605), have an unsupported processor.</span></span>

<span data-ttu-id="7a6b1-281">Загрузите [Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) и следуйте [инструкциям по установке](https://www.raspberrypi.org/documentation/installation/installing-images/README.md), чтобы установить его на свой Pi.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-281">Download [Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) and follow the [installation instructions](https://www.raspberrypi.org/documentation/installation/installing-images/README.md) to get it onto your Pi.</span></span>

### <a name="installation---raspbian"></a><span data-ttu-id="7a6b1-282">Установка — Raspbian</span><span class="sxs-lookup"><span data-stu-id="7a6b1-282">Installation - Raspbian</span></span>

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

<span data-ttu-id="7a6b1-283">При необходимости можно создать символьную ссылку для запуска PowerShell без указания пути к двоичному файлу `pwsh`.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-283">Optionally, you can create a symbolic link to start PowerShell without specifying the path to the `pwsh` binary.</span></span>

```sh
# Start PowerShell from bash with sudo to create a symbolic link
sudo ~/powershell/pwsh -c New-Item -ItemType SymbolicLink -Path "/usr/bin/pwsh" -Target "$PSHOME/pwsh" -Force

# alternatively you can run following to create a symbolic link
# sudo ln -s ~/powershell/pwsh /usr/bin/pwsh

# Now to start PowerShell you can just run "pwsh"
```

### <a name="uninstallation---raspbian"></a><span data-ttu-id="7a6b1-284">Удаление — Raspbian</span><span class="sxs-lookup"><span data-stu-id="7a6b1-284">Uninstallation - Raspbian</span></span>

```sh
rm -rf ~/powershell
```

## <a name="installing-preview-releases"></a><span data-ttu-id="7a6b1-285">Установка предварительных выпусков</span><span class="sxs-lookup"><span data-stu-id="7a6b1-285">Installing Preview Releases</span></span>

<span data-ttu-id="7a6b1-286">При установке предварительной версии PowerShell для Linux с помощью репозитория пакетов имя пакета меняется с `powershell` на `powershell-preview`.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-286">When installing a PowerShell Preview release for Linux via a Package Repository, the package name changes from `powershell` to `powershell-preview`.</span></span>

<span data-ttu-id="7a6b1-287">При установке с помощью прямого скачивания изменяется только имя файла.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-287">Installing via direct download doesn't change, other than the file name.</span></span>

<span data-ttu-id="7a6b1-288">В следующей таблице приведены команды для установки пакетов стабильной и предварительной версий с помощью различных диспетчеров пакетов:</span><span class="sxs-lookup"><span data-stu-id="7a6b1-288">The following table contains the commands to install the stable and preview packages using the various package managers:</span></span>

| <span data-ttu-id="7a6b1-289">Дистрибутивы</span><span class="sxs-lookup"><span data-stu-id="7a6b1-289">Distribution(s)</span></span> |            <span data-ttu-id="7a6b1-290">Команда стабильной версии</span><span class="sxs-lookup"><span data-stu-id="7a6b1-290">Stable Command</span></span>            |               <span data-ttu-id="7a6b1-291">Команда предварительной версии</span><span class="sxs-lookup"><span data-stu-id="7a6b1-291">Preview Command</span></span>                |
| --------------- | ------------------------------------ | -------------------------------------------- |
| <span data-ttu-id="7a6b1-292">Ubuntu, Debian</span><span class="sxs-lookup"><span data-stu-id="7a6b1-292">Ubuntu, Debian</span></span>  | `sudo apt-get install -y powershell` | `sudo apt-get install -y powershell-preview` |
| <span data-ttu-id="7a6b1-293">CentOS, RedHat</span><span class="sxs-lookup"><span data-stu-id="7a6b1-293">CentOS, RedHat</span></span>  | `sudo yum install -y powershell`     | `sudo yum install -y powershell-preview`     |
| <span data-ttu-id="7a6b1-294">Fedora</span><span class="sxs-lookup"><span data-stu-id="7a6b1-294">Fedora</span></span>          | `sudo dnf install -y powershell`     | `sudo dnf install -y powershell-preview`     |

## <a name="install-as-a-net-global-tool"></a><span data-ttu-id="7a6b1-295">Установка в качестве глобального средства .NET</span><span class="sxs-lookup"><span data-stu-id="7a6b1-295">Install as a .NET Global tool</span></span>

<span data-ttu-id="7a6b1-296">Если вы уже установили [пакет SDK для .NET Core](/dotnet/core/sdk), установите PowerShell как [глобальное средство .NET](/dotnet/core/tools/global-tools).</span><span class="sxs-lookup"><span data-stu-id="7a6b1-296">If you already have the [.NET Core SDK](/dotnet/core/sdk) installed, it's easy to install PowerShell as a [.NET Global tool](/dotnet/core/tools/global-tools).</span></span>

```
dotnet tool install --global PowerShell
```

<span data-ttu-id="7a6b1-297">Установщик инструмента dotnet добавляет `~/.dotnet/tools` в переменную среды `PATH`.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-297">The dotnet tool installer adds `~/.dotnet/tools` to your `PATH` environment variable.</span></span> <span data-ttu-id="7a6b1-298">Но в выполняющейся оболочке отсутствует обновленная переменная `PATH`.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-298">However, the currently running shell does not have the updated `PATH`.</span></span> <span data-ttu-id="7a6b1-299">Вы можете запустить PowerShell из новой оболочки, введя `pwsh`.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-299">You should be able to start PowerShell from a new shell by typing `pwsh`.</span></span>

## <a name="binary-archives"></a><span data-ttu-id="7a6b1-300">Архивы двоичных файлов</span><span class="sxs-lookup"><span data-stu-id="7a6b1-300">Binary Archives</span></span>

<span data-ttu-id="7a6b1-301">Для поддержки расширенных сценариев развертывания на платформах Linux доступны архивы `tar.gz` двоичных файлов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-301">PowerShell binary `tar.gz` archives are provided for Linux platforms to enable advanced deployment scenarios.</span></span>

### <a name="dependencies"></a><span data-ttu-id="7a6b1-302">Зависимости</span><span class="sxs-lookup"><span data-stu-id="7a6b1-302">Dependencies</span></span>

<span data-ttu-id="7a6b1-303">PowerShell создает переносимые двоичные файлы для всех дистрибутивов Linux.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-303">PowerShell builds portable binaries for all Linux distributions.</span></span> <span data-ttu-id="7a6b1-304">Но среда выполнения .NET Core, как и PowerShell, требует различные зависимости для разных дистрибутивов.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-304">But, .NET Core runtime requires different dependencies on different distributions, and PowerShell does too.</span></span>

<span data-ttu-id="7a6b1-305">На следующей диаграмме показаны официально поддерживаемые зависимости .NET Core 2.0 для различных дистрибутивов Linux.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-305">The following chart shows the .NET Core 2.0 dependencies that are officially supported on different Linux distributions.</span></span>

| <span data-ttu-id="7a6b1-306">OS</span><span class="sxs-lookup"><span data-stu-id="7a6b1-306">OS</span></span>                 | <span data-ttu-id="7a6b1-307">Зависимости</span><span class="sxs-lookup"><span data-stu-id="7a6b1-307">Dependencies</span></span> |
| ------------------ | ------------ |
| <span data-ttu-id="7a6b1-308">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="7a6b1-308">Ubuntu 16.04</span></span>       | <span data-ttu-id="7a6b1-309">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="7a6b1-309">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="7a6b1-310">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu55</span><span class="sxs-lookup"><span data-stu-id="7a6b1-310">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu55</span></span> |
| <span data-ttu-id="7a6b1-311">Ubuntu 17.10</span><span class="sxs-lookup"><span data-stu-id="7a6b1-311">Ubuntu 17.10</span></span>       | <span data-ttu-id="7a6b1-312">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="7a6b1-312">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="7a6b1-313">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu57</span><span class="sxs-lookup"><span data-stu-id="7a6b1-313">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu57</span></span> |
| <span data-ttu-id="7a6b1-314">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="7a6b1-314">Ubuntu 18.04</span></span>       | <span data-ttu-id="7a6b1-315">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="7a6b1-315">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="7a6b1-316">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu60</span><span class="sxs-lookup"><span data-stu-id="7a6b1-316">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu60</span></span> |
| <span data-ttu-id="7a6b1-317">Debian 8 (Jessie)</span><span class="sxs-lookup"><span data-stu-id="7a6b1-317">Debian 8 (Jessie)</span></span>  | <span data-ttu-id="7a6b1-318">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="7a6b1-318">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="7a6b1-319">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span><span class="sxs-lookup"><span data-stu-id="7a6b1-319">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span></span> |
| <span data-ttu-id="7a6b1-320">Debian 9 (Stretch)</span><span class="sxs-lookup"><span data-stu-id="7a6b1-320">Debian 9 (Stretch)</span></span> | <span data-ttu-id="7a6b1-321">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="7a6b1-321">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="7a6b1-322">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.2, libicu57</span><span class="sxs-lookup"><span data-stu-id="7a6b1-322">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.2, libicu57</span></span> |
| <span data-ttu-id="7a6b1-323">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="7a6b1-323">CentOS 7</span></span> <br> <span data-ttu-id="7a6b1-324">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="7a6b1-324">Oracle Linux 7</span></span> <br> <span data-ttu-id="7a6b1-325">RHEL 7</span><span class="sxs-lookup"><span data-stu-id="7a6b1-325">RHEL 7</span></span> | <span data-ttu-id="7a6b1-326">libunwind, libcurl, openssl-libs, libicu</span><span class="sxs-lookup"><span data-stu-id="7a6b1-326">libunwind, libcurl, openssl-libs, libicu</span></span> |
| <span data-ttu-id="7a6b1-327">openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="7a6b1-327">openSUSE 42.3</span></span> | <span data-ttu-id="7a6b1-328">libcurl4, libopenssl1_0_0, libicu52_1</span><span class="sxs-lookup"><span data-stu-id="7a6b1-328">libcurl4, libopenssl1_0_0, libicu52_1</span></span> |
| <span data-ttu-id="7a6b1-329">openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="7a6b1-329">openSUSE Leap 15</span></span> | <span data-ttu-id="7a6b1-330">libcurl4, libopenssl1_0_0, libicu60_2</span><span class="sxs-lookup"><span data-stu-id="7a6b1-330">libcurl4, libopenssl1_0_0, libicu60_2</span></span> |
| <span data-ttu-id="7a6b1-331">Fedora 27</span><span class="sxs-lookup"><span data-stu-id="7a6b1-331">Fedora 27</span></span> <br> <span data-ttu-id="7a6b1-332">Fedora 28</span><span class="sxs-lookup"><span data-stu-id="7a6b1-332">Fedora 28</span></span> | <span data-ttu-id="7a6b1-333">libunwind, libcurl, openssl-libs, libicu, compat-openssl10</span><span class="sxs-lookup"><span data-stu-id="7a6b1-333">libunwind, libcurl, openssl-libs, libicu, compat-openssl10</span></span> |

<span data-ttu-id="7a6b1-334">Чтобы развернуть двоичные файлы PowerShell в дистрибутивах Linux, для которых официальная поддержка не предусмотрена, необходимо специально установить необходимые пакеты, чтобы выполнить все требования, касающиеся зависимостей, для целевой ОС.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-334">To deploy PowerShell binaries on Linux distributions that aren't officially supported, you need to install the necessary dependencies for the target OS in separate steps.</span></span> <span data-ttu-id="7a6b1-335">Например, наш [Dockerfile для Amazon Linux][amazon-dockerfile] сначала устанавливает зависимости, а затем извлекает архив Linux `tar.gz`.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-335">For example, our [Amazon Linux dockerfile][amazon-dockerfile] installs dependencies first, and then extracts the Linux `tar.gz` archive.</span></span>

[amazon-dockerfile]: https://github.com/PowerShell/PowerShell-Docker/blob/master/release/community-stable/amazonlinux/docker/Dockerfile

### <a name="installation---binary-archives"></a><span data-ttu-id="7a6b1-336">Установка — архивы двоичных файлов</span><span class="sxs-lookup"><span data-stu-id="7a6b1-336">Installation - Binary Archives</span></span>

#### <a name="linux"></a><span data-ttu-id="7a6b1-337">Linux</span><span class="sxs-lookup"><span data-stu-id="7a6b1-337">Linux</span></span>

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

### <a name="uninstalling-binary-archives"></a><span data-ttu-id="7a6b1-338">Удаление архивов двоичных файлов</span><span class="sxs-lookup"><span data-stu-id="7a6b1-338">Uninstalling binary archives</span></span>

```sh
sudo rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="paths"></a><span data-ttu-id="7a6b1-339">Пути</span><span class="sxs-lookup"><span data-stu-id="7a6b1-339">Paths</span></span>

- <span data-ttu-id="7a6b1-340">`$PSHOME` имеет значение `/opt/microsoft/powershell/7/`.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-340">`$PSHOME` is `/opt/microsoft/powershell/7/`</span></span>
- <span data-ttu-id="7a6b1-341">Профили пользователей будут считаны из `~/.config/powershell/profile.ps1`.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-341">User profiles will be read from `~/.config/powershell/profile.ps1`</span></span>
- <span data-ttu-id="7a6b1-342">Профили по умолчанию будут считаны из `$PSHOME/profile.ps1`.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-342">Default profiles will be read from `$PSHOME/profile.ps1`</span></span>
- <span data-ttu-id="7a6b1-343">Модули пользователей будут считаны из `~/.local/share/powershell/Modules`.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-343">User modules will be read from `~/.local/share/powershell/Modules`</span></span>
- <span data-ttu-id="7a6b1-344">Общие модули будут считаны из `/usr/local/share/powershell/Modules`.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-344">Shared modules will be read from `/usr/local/share/powershell/Modules`</span></span>
- <span data-ttu-id="7a6b1-345">Модули по умолчанию будут считаны из `$PSHOME/Modules`.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-345">Default modules will be read from `$PSHOME/Modules`</span></span>
- <span data-ttu-id="7a6b1-346">Журнал PSReadline будет записан в `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span><span class="sxs-lookup"><span data-stu-id="7a6b1-346">PSReadLine history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="7a6b1-347">Профили учитывают конфигурацию PowerShell для отдельных узлов, поэтому профили конкретных узлов по умолчанию находятся в `Microsoft.PowerShell_profile.ps1` в тех же расположениях.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-347">The profiles respect PowerShell's per-host configuration, so the default host-specific profiles exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="7a6b1-348">PowerShell отвечает требованиям [спецификации каталога размещения файлов, связанных со средой настольной графической среды (X-сервера), стандартизированного XDG (X Desktop Group)][xdg-bds] в Linux.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-348">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on Linux.</span></span>

## <a name="installation-support"></a><span data-ttu-id="7a6b1-349">Поддержка установки</span><span class="sxs-lookup"><span data-stu-id="7a6b1-349">Installation support</span></span>

<span data-ttu-id="7a6b1-350">Корпорация Майкрософт поддерживает методы установки, изложенные в этом документе.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-350">Microsoft supports the installation methods in this document.</span></span> <span data-ttu-id="7a6b1-351">В других источниках могут быть доступны другие методы установки.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-351">There may be other methods of installation available from other sources.</span></span> <span data-ttu-id="7a6b1-352">Хотя такие инструменты и методы могут работать, корпорация Майкрософт не поддерживает их.</span><span class="sxs-lookup"><span data-stu-id="7a6b1-352">While those tools and methods may work, Microsoft cannot support those methods.</span></span>

<!-- link references -->
[выпусками]: https://aka.ms/PowerShell-Release?tag=stable
[releases]: https://aka.ms/PowerShell-Release?tag=stable
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
[distros]: https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md#linux
[Distribution Support Request]: https://github.com/PowerShell/PowerShell/issues/new?assignees=&labels=Distribution-Request&template=Distribution_Request.md&title=Distribution+Support+Request
