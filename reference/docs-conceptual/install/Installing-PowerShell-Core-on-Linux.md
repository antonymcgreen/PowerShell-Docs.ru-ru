---
title: Установка PowerShell в Linux
description: Сведения об установке PowerShell в различных дистрибутивах Linux
ms.date: 03/09/2020
ms.openlocfilehash: 201bb693c3473f6b1f05d860562b1fc132912bb2
ms.sourcegitcommit: 7c7f8bb9afdc592d07bf7ff4179d000a48716f13
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "82174146"
---
# <a name="installing-powershell-on-linux"></a><span data-ttu-id="d9624-103">Установка PowerShell в Linux</span><span class="sxs-lookup"><span data-stu-id="d9624-103">Installing PowerShell on Linux</span></span>

<span data-ttu-id="d9624-104">Все пакеты доступны на нашей странице [выпусками][] GitHub.</span><span class="sxs-lookup"><span data-stu-id="d9624-104">All packages are available on our GitHub [releases][] page.</span></span> <span data-ttu-id="d9624-105">После установки пакета запустите `pwsh` из терминала.</span><span class="sxs-lookup"><span data-stu-id="d9624-105">After the package is installed, run `pwsh` from a terminal.</span></span> <span data-ttu-id="d9624-106">Запустите `pwsh-preview`, если вы установили [выпуск предварительной версии](#installing-preview-releases).</span><span class="sxs-lookup"><span data-stu-id="d9624-106">Run `pwsh-preview` if you installed a [Preview release](#installing-preview-releases).</span></span>

> [!NOTE]
> <span data-ttu-id="d9624-107">PowerShell 7 является обновлением на месте, при установке которого PowerShell Core 6.x удаляется.</span><span class="sxs-lookup"><span data-stu-id="d9624-107">PowerShell 7 is an in-place upgrade that removes PowerShell Core 6.x.</span></span>
>
> <span data-ttu-id="d9624-108">Папка `/usr/local/microsoft/powershell/6` заменяется на `/usr/local/microsoft/powershell/7`.</span><span class="sxs-lookup"><span data-stu-id="d9624-108">The `/usr/local/microsoft/powershell/6` folder is replaced by `/usr/local/microsoft/powershell/7`.</span></span>
>
> <span data-ttu-id="d9624-109">Если вы хотите запускать PowerShell 6 параллельно с PowerShell 7, переустановите PowerShell 6 с использованием [двоичного архива](#binary-archives).</span><span class="sxs-lookup"><span data-stu-id="d9624-109">If you need to run PowerShell 6 side-by-side with PowerShell 7, reinstall PowerShell 6 using the [binary archive](#binary-archives) method.</span></span>

<span data-ttu-id="d9624-110">Для дистрибутивов Linux без официальной поддержки попробуйте установить PowerShell с помощью [соответствующего Snap-пакета][snap].</span><span class="sxs-lookup"><span data-stu-id="d9624-110">For Linux distributions that aren't officially supported, you can try to install PowerShell using the [PowerShell Snap Package][snap].</span></span> <span data-ttu-id="d9624-111">Можно также попытаться развернуть двоичные файлы PowerShell напрямую с помощью [архива`tar.gz`][tar] Linux, но при этом нужно отдельно настроить необходимые зависимости с учетом операционной системы.</span><span class="sxs-lookup"><span data-stu-id="d9624-111">You can also try deploying PowerShell binaries directly using the Linux [`tar.gz` archive][tar], but you would need to set up the necessary dependencies based on the OS in separate steps.</span></span>

[snap]: #snap-package
[tar]: #binary-archives

<span data-ttu-id="d9624-112">Официально поддерживаемые выпуски:</span><span class="sxs-lookup"><span data-stu-id="d9624-112">Officially supported releases</span></span>

- <span data-ttu-id="d9624-113">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="d9624-113">Ubuntu 16.04</span></span>
- <span data-ttu-id="d9624-114">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="d9624-114">Ubuntu 18.04</span></span>
- <span data-ttu-id="d9624-115">Debian 8</span><span class="sxs-lookup"><span data-stu-id="d9624-115">Debian 8</span></span>
- <span data-ttu-id="d9624-116">Debian 9</span><span class="sxs-lookup"><span data-stu-id="d9624-116">Debian 9</span></span>
- <span data-ttu-id="d9624-117">Debian 10</span><span class="sxs-lookup"><span data-stu-id="d9624-117">Debian 10</span></span>
- <span data-ttu-id="d9624-118">Alpine 3.9 и 3.10</span><span class="sxs-lookup"><span data-stu-id="d9624-118">Alpine 3.9 and 3.10</span></span>
- <span data-ttu-id="d9624-119">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="d9624-119">CentOS 7</span></span>
- <span data-ttu-id="d9624-120">Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="d9624-120">Red Hat Enterprise Linux (RHEL) 7</span></span>
- <span data-ttu-id="d9624-121">Fedora 28</span><span class="sxs-lookup"><span data-stu-id="d9624-121">Fedora 28</span></span>
- <span data-ttu-id="d9624-122">Fedora 29</span><span class="sxs-lookup"><span data-stu-id="d9624-122">Fedora 29</span></span>
- <span data-ttu-id="d9624-123">Fedora 30</span><span class="sxs-lookup"><span data-stu-id="d9624-123">Fedora 30</span></span>
- <span data-ttu-id="d9624-124">openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="d9624-124">openSUSE 42.3</span></span>
- <span data-ttu-id="d9624-125">openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="d9624-125">openSUSE Leap 15</span></span>

<span data-ttu-id="d9624-126">Выпуски, поддерживаемые сообществом:</span><span class="sxs-lookup"><span data-stu-id="d9624-126">Community supported releases</span></span>

- <span data-ttu-id="d9624-127">Ubuntu 18.10</span><span class="sxs-lookup"><span data-stu-id="d9624-127">Ubuntu 18.10</span></span>
- <span data-ttu-id="d9624-128">Ubuntu 19.04</span><span class="sxs-lookup"><span data-stu-id="d9624-128">Ubuntu 19.04</span></span>
- <span data-ttu-id="d9624-129">Arch Linux</span><span class="sxs-lookup"><span data-stu-id="d9624-129">Arch Linux</span></span>
- <span data-ttu-id="d9624-130">Kali</span><span class="sxs-lookup"><span data-stu-id="d9624-130">Kali</span></span>
- <span data-ttu-id="d9624-131">Raspbian (экспериментальная версия)</span><span class="sxs-lookup"><span data-stu-id="d9624-131">Raspbian (experimental)</span></span>

<span data-ttu-id="d9624-132">Альтернативные методы установки</span><span class="sxs-lookup"><span data-stu-id="d9624-132">Alternate install methods</span></span>

- <span data-ttu-id="d9624-133">Snap-пакет</span><span class="sxs-lookup"><span data-stu-id="d9624-133">Snap Package</span></span>
- <span data-ttu-id="d9624-134">Архивы двоичных файлов</span><span class="sxs-lookup"><span data-stu-id="d9624-134">Binary Archives</span></span>
- <span data-ttu-id="d9624-135">Глобальный инструмент .NET</span><span class="sxs-lookup"><span data-stu-id="d9624-135">.NET Global tool</span></span>

## <a name="ubuntu-1604"></a><span data-ttu-id="d9624-136">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="d9624-136">Ubuntu 16.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1604"></a><span data-ttu-id="d9624-137">Установка с помощью репозитория пакетов — Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="d9624-137">Installation via Package Repository - Ubuntu 16.04</span></span>

<span data-ttu-id="d9624-138">Чтобы упростить установку и обновление, PowerShell для Linux публикуется в репозиториях пакетов.</span><span class="sxs-lookup"><span data-stu-id="d9624-138">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="d9624-139">Предпочтительный метод выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d9624-139">The preferred method is as follows:</span></span>

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

<span data-ttu-id="d9624-140">В качестве суперпользователя однократно зарегистрируйте репозиторий Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d9624-140">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="d9624-141">После регистрации можно обновить PowerShell с помощью `sudo apt-get upgrade powershell`.</span><span class="sxs-lookup"><span data-stu-id="d9624-141">After registration, you can update PowerShell with `sudo apt-get upgrade powershell`.</span></span>

### <a name="installation-via-direct-download---ubuntu-1604"></a><span data-ttu-id="d9624-142">Установка с помощью прямого скачивания — Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="d9624-142">Installation via Direct Download - Ubuntu 16.04</span></span>

<span data-ttu-id="d9624-143">Скачайте пакет Debian `powershell-lts_7.0.0-1.ubuntu.16.04_amd64.deb` со страницы [выпусками][] на компьютер с Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="d9624-143">Download the Debian package `powershell-lts_7.0.0-1.ubuntu.16.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="d9624-144">Затем выполните в терминале следующие команды:</span><span class="sxs-lookup"><span data-stu-id="d9624-144">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell-lts_7.0.0-1.ubuntu.16.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="d9624-145">Команда `dpkg -i` завершается ошибкой при наличии несопоставленных зависимостей.</span><span class="sxs-lookup"><span data-stu-id="d9624-145">The `dpkg -i` command fails with unmet dependencies.</span></span> <span data-ttu-id="d9624-146">Следующая команда, `apt-get install -f`, разрешает эти ошибки и завершает настройку пакета PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d9624-146">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1604"></a><span data-ttu-id="d9624-147">Удаление — Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="d9624-147">Uninstallation - Ubuntu 16.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1804"></a><span data-ttu-id="d9624-148">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="d9624-148">Ubuntu 18.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1804"></a><span data-ttu-id="d9624-149">Установка с помощью репозитория пакетов — Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="d9624-149">Installation via Package Repository - Ubuntu 18.04</span></span>

<span data-ttu-id="d9624-150">Чтобы упростить установку и обновление, PowerShell для Linux публикуется в репозиториях пакетов.</span><span class="sxs-lookup"><span data-stu-id="d9624-150">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="d9624-151">Предпочтительный метод выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d9624-151">The preferred method is as follows:</span></span>

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

<span data-ttu-id="d9624-152">В качестве суперпользователя однократно зарегистрируйте репозиторий Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d9624-152">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="d9624-153">После регистрации можно обновить PowerShell с помощью `sudo apt-get upgrade powershell`.</span><span class="sxs-lookup"><span data-stu-id="d9624-153">After registration, you can update PowerShell with `sudo apt-get upgrade powershell`.</span></span>

### <a name="installation-via-direct-download---ubuntu-1804"></a><span data-ttu-id="d9624-154">Установка с помощью прямого скачивания — Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="d9624-154">Installation via Direct Download - Ubuntu 18.04</span></span>

<span data-ttu-id="d9624-155">Скачайте пакет Debian `powershell-lts_7.0.0-1.ubuntu.18.04_amd64.deb` со страницы [выпусками][] на компьютер с Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="d9624-155">Download the Debian package `powershell-lts_7.0.0-1.ubuntu.18.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="d9624-156">Затем выполните в терминале следующие команды:</span><span class="sxs-lookup"><span data-stu-id="d9624-156">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell-lts_7.0.0-1.ubuntu.18.04_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="d9624-157">Команда `dpkg -i` завершается ошибкой при наличии несопоставленных зависимостей.</span><span class="sxs-lookup"><span data-stu-id="d9624-157">The `dpkg -i` command fails with unmet dependencies.</span></span> <span data-ttu-id="d9624-158">Следующая команда, `apt-get install -f`, разрешает эти ошибки и завершает настройку пакета PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d9624-158">The next command, `apt-get install -f` resolves these issues then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1804"></a><span data-ttu-id="d9624-159">Удаление — Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="d9624-159">Uninstallation - Ubuntu 18.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1810"></a><span data-ttu-id="d9624-160">Ubuntu 18.10</span><span class="sxs-lookup"><span data-stu-id="d9624-160">Ubuntu 18.10</span></span>

<span data-ttu-id="d9624-161">Поддерживается только установка с помощью `snapd`.</span><span class="sxs-lookup"><span data-stu-id="d9624-161">Installation is supported via `snapd`.</span></span> <span data-ttu-id="d9624-162">Инструкции см. в разделе о [snap-пакете][snap].</span><span class="sxs-lookup"><span data-stu-id="d9624-162">For instructions, see [Snap Package][snap].</span></span>

> [!NOTE]
> <span data-ttu-id="d9624-163">Ubuntu 18.10 — [промежуточный выпуск](https://www.ubuntu.com/about/release-cycle), который [поддерживается сообществом](../powershell-support-lifecycle.md).</span><span class="sxs-lookup"><span data-stu-id="d9624-163">Ubuntu 18.10 is an [interim release](https://www.ubuntu.com/about/release-cycle) that's [community supported](../powershell-support-lifecycle.md).</span></span>

## <a name="ubuntu-1904"></a><span data-ttu-id="d9624-164">Ubuntu 19.04</span><span class="sxs-lookup"><span data-stu-id="d9624-164">Ubuntu 19.04</span></span>

<span data-ttu-id="d9624-165">Поддерживается только установка с помощью `snapd`.</span><span class="sxs-lookup"><span data-stu-id="d9624-165">Installation is supported via `snapd`.</span></span> <span data-ttu-id="d9624-166">Инструкции см. в разделе о [snap-пакете][snap].</span><span class="sxs-lookup"><span data-stu-id="d9624-166">For instructions, see [Snap Package][snap].</span></span>

> [!NOTE]
> <span data-ttu-id="d9624-167">Ubuntu 19.04 — [промежуточный выпуск](https://www.ubuntu.com/about/release-cycle), который [поддерживается сообществом](../powershell-support-lifecycle.md).</span><span class="sxs-lookup"><span data-stu-id="d9624-167">Ubuntu 19.04 is an [interim release](https://www.ubuntu.com/about/release-cycle) that's [community supported](../powershell-support-lifecycle.md).</span></span>

## <a name="debian-8"></a><span data-ttu-id="d9624-168">Debian 8</span><span class="sxs-lookup"><span data-stu-id="d9624-168">Debian 8</span></span>

### <a name="installation-via-package-repository---debian-8"></a><span data-ttu-id="d9624-169">Установка с помощью репозитория пакетов — Debian 8</span><span class="sxs-lookup"><span data-stu-id="d9624-169">Installation via Package Repository - Debian 8</span></span>

<span data-ttu-id="d9624-170">Чтобы упростить установку и обновление, PowerShell для Linux публикуется в репозиториях пакетов.</span><span class="sxs-lookup"><span data-stu-id="d9624-170">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="d9624-171">Предпочтительный метод выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d9624-171">The preferred method is as follows:</span></span>

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

<span data-ttu-id="d9624-172">В качестве суперпользователя однократно зарегистрируйте репозиторий Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d9624-172">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="d9624-173">После регистрации можно обновить PowerShell с помощью `sudo apt-get upgrade powershell`.</span><span class="sxs-lookup"><span data-stu-id="d9624-173">After registration, you can update PowerShell with `sudo apt-get upgrade powershell`.</span></span>

## <a name="debian-9"></a><span data-ttu-id="d9624-174">Debian 9</span><span class="sxs-lookup"><span data-stu-id="d9624-174">Debian 9</span></span>

### <a name="installation-via-package-repository---debian-9"></a><span data-ttu-id="d9624-175">Установка с помощью репозитория пакетов — Debian 9</span><span class="sxs-lookup"><span data-stu-id="d9624-175">Installation via Package Repository - Debian 9</span></span>

<span data-ttu-id="d9624-176">Чтобы упростить установку и обновление, PowerShell для Linux публикуется в репозиториях пакетов.</span><span class="sxs-lookup"><span data-stu-id="d9624-176">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="d9624-177">Предпочтительный метод выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d9624-177">The preferred method is as follows:</span></span>

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

<span data-ttu-id="d9624-178">В качестве суперпользователя однократно зарегистрируйте репозиторий Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d9624-178">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="d9624-179">После регистрации можно обновить PowerShell с помощью `sudo apt-get upgrade powershell`.</span><span class="sxs-lookup"><span data-stu-id="d9624-179">After registration, you can update PowerShell with `sudo apt-get upgrade powershell`.</span></span>

### <a name="installation-via-direct-download---debian-9"></a><span data-ttu-id="d9624-180">Установка с помощью прямого скачивания — Debian 9</span><span class="sxs-lookup"><span data-stu-id="d9624-180">Installation via Direct Download - Debian 9</span></span>

<span data-ttu-id="d9624-181">Скачайте пакет Debian `powershell-lts_7.0.0-1.debian.9_amd64.deb` со страницы [выпусками][] на компьютер с Debian.</span><span class="sxs-lookup"><span data-stu-id="d9624-181">Download the Debian package `powershell-lts_7.0.0-1.debian.9_amd64.deb` from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="d9624-182">Затем выполните в терминале следующие команды:</span><span class="sxs-lookup"><span data-stu-id="d9624-182">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dpkg -i powershell-lts_7.0.0-1.debian.9_amd64.deb
sudo apt-get install -f
```

### <a name="uninstallation---debian-9"></a><span data-ttu-id="d9624-183">Удаление — Debian 9</span><span class="sxs-lookup"><span data-stu-id="d9624-183">Uninstallation - Debian 9</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="debian-10"></a><span data-ttu-id="d9624-184">Debian 10</span><span class="sxs-lookup"><span data-stu-id="d9624-184">Debian 10</span></span>

> [!NOTE]
> <span data-ttu-id="d9624-185">Debian 10 поддерживается только в PowerShell 7.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="d9624-185">Debian 10 is only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-package-repository---debian-10"></a><span data-ttu-id="d9624-186">Установка с помощью репозитория пакетов — Debian 10</span><span class="sxs-lookup"><span data-stu-id="d9624-186">Installation via Package Repository - Debian 10</span></span>

<span data-ttu-id="d9624-187">Чтобы упростить установку и обновление, PowerShell для Linux публикуется в репозиториях пакетов.</span><span class="sxs-lookup"><span data-stu-id="d9624-187">PowerShell for Linux is published to package repositories for easy installation and updates.</span></span>

<span data-ttu-id="d9624-188">Предпочтительный метод выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d9624-188">The preferred method is as follows:</span></span>

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

### <a name="installation-via-direct-download---debian-10"></a><span data-ttu-id="d9624-189">Установка с помощью прямого скачивания — Debian 10</span><span class="sxs-lookup"><span data-stu-id="d9624-189">Installation via Direct Download - Debian 10</span></span>

<span data-ttu-id="d9624-190">Скачайте пакет tar.gz `powershell_7.0.0-linux-x64.tar.gz` на странице с [выпусками][] на компьютер с Debian.</span><span class="sxs-lookup"><span data-stu-id="d9624-190">Download the tar.gz package `powershell_7.0.0-linux-x64.tar.gz` from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="d9624-191">Затем выполните в терминале следующие команды:</span><span class="sxs-lookup"><span data-stu-id="d9624-191">Then, in the terminal, execute the following commands:</span></span>

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

## <a name="alpine-39-and-310"></a><span data-ttu-id="d9624-192">Alpine 3.9 и 3.10</span><span class="sxs-lookup"><span data-stu-id="d9624-192">Alpine 3.9 and 3.10</span></span>

> [!NOTE]
> <span data-ttu-id="d9624-193">Alpine 3.9 и 3.10 поддерживается только в PowerShell 7.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="d9624-193">Alpine 3.9 and 3.10 are only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-direct-download---alpine-39-and-310"></a><span data-ttu-id="d9624-194">Установка с помощью прямого скачивания — Alpine 3.9 и 3.10</span><span class="sxs-lookup"><span data-stu-id="d9624-194">Installation via Direct Download - Alpine 3.9 and 3.10</span></span>

<span data-ttu-id="d9624-195">Скачайте пакет tar.gz `powershell-7.0.0-linux-alpine-x64.tar.gz` на странице с [выпусками][] на компьютер с Alpine.</span><span class="sxs-lookup"><span data-stu-id="d9624-195">Download the tar.gz package `powershell-7.0.0-linux-alpine-x64.tar.gz` from the [releases][] page onto the Alpine machine.</span></span>

<span data-ttu-id="d9624-196">Затем выполните в терминале следующие команды:</span><span class="sxs-lookup"><span data-stu-id="d9624-196">Then, in the terminal, execute the following commands:</span></span>

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

## <a name="centos-7"></a><span data-ttu-id="d9624-197">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="d9624-197">CentOS 7</span></span>

> [!NOTE]
> <span data-ttu-id="d9624-198">Этот пакет работает в Oracle Linux 7.</span><span class="sxs-lookup"><span data-stu-id="d9624-198">This package works on Oracle Linux 7.</span></span>

### <a name="installation-via-package-repository-preferred---centos-7"></a><span data-ttu-id="d9624-199">Установка с помощью репозитория пакетов (рекомендуется) — CentOS 7</span><span class="sxs-lookup"><span data-stu-id="d9624-199">Installation via Package Repository (preferred) - CentOS 7</span></span>

<span data-ttu-id="d9624-200">Чтобы упростить установку и обновление, PowerShell для Linux публикуется в официальных репозиториях Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d9624-200">PowerShell for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="d9624-201">В качестве суперпользователя однократно зарегистрируйте репозиторий Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d9624-201">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="d9624-202">После регистрации можно обновить PowerShell с помощью `sudo yum update powershell`.</span><span class="sxs-lookup"><span data-stu-id="d9624-202">After registration, you can update PowerShell with `sudo yum update powershell`.</span></span>

### <a name="installation-via-direct-download---centos-7"></a><span data-ttu-id="d9624-203">Установка с помощью прямого скачивания — CentOS 7</span><span class="sxs-lookup"><span data-stu-id="d9624-203">Installation via Direct Download - CentOS 7</span></span>

<span data-ttu-id="d9624-204">Используя [CentOS 7][], скачайте пакет RPM `powershell-lts-7.0.0-1.rhel.7.x86_64.rpm` со страницы [выпусками][] на компьютер с CentOS.</span><span class="sxs-lookup"><span data-stu-id="d9624-204">Using [CentOS 7][], download the RPM package `powershell-lts-7.0.0-1.rhel.7.x86_64.rpm` from the [releases][] page onto the CentOS machine.</span></span>

<span data-ttu-id="d9624-205">Затем выполните в терминале следующие команды:</span><span class="sxs-lookup"><span data-stu-id="d9624-205">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo yum install powershell-lts-7.0.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="d9624-206">RPM можно установить без промежуточного скачивания:</span><span class="sxs-lookup"><span data-stu-id="d9624-206">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v7.0.0/powershell-lts-7.0.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---centos-7"></a><span data-ttu-id="d9624-207">Удаление — CentOS 7</span><span class="sxs-lookup"><span data-stu-id="d9624-207">Uninstallation - CentOS 7</span></span>

```sh
sudo yum remove powershell
```

[CentOS 7]: https://www.centos.org/download/

## <a name="red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="d9624-209">Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="d9624-209">Red Hat Enterprise Linux (RHEL) 7</span></span>

### <a name="installation-via-package-repository-preferred---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="d9624-210">Установка с помощью репозитория пакетов (рекомендуется) — Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="d9624-210">Installation via Package Repository (preferred) - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="d9624-211">Чтобы упростить установку и обновление, PowerShell для Linux публикуется в официальных репозиториях Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d9624-211">PowerShell for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="d9624-212">В качестве суперпользователя однократно зарегистрируйте репозиторий Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d9624-212">As superuser, register the Microsoft repository once.</span></span> <span data-ttu-id="d9624-213">После регистрации можно обновить PowerShell с помощью `sudo yum update powershell`.</span><span class="sxs-lookup"><span data-stu-id="d9624-213">After registration, you can update PowerShell with `sudo yum update powershell`.</span></span>

### <a name="installation-via-direct-download---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="d9624-214">Установка с помощью прямого скачивания — Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="d9624-214">Installation via Direct Download - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="d9624-215">Скачайте пакет RPM `powershell-lts-7.0.0-1.rhel.7.x86_64.rpm` со страницы [выпусками][] на компьютер с Red Hat Enterprise Linux.</span><span class="sxs-lookup"><span data-stu-id="d9624-215">Download the RPM package `powershell-lts-7.0.0-1.rhel.7.x86_64.rpm` from the [releases][] page onto the Red Hat Enterprise Linux machine.</span></span>

<span data-ttu-id="d9624-216">Затем выполните в терминале следующие команды:</span><span class="sxs-lookup"><span data-stu-id="d9624-216">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo yum install powershell-lts-7.0.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="d9624-217">RPM можно установить без промежуточного скачивания:</span><span class="sxs-lookup"><span data-stu-id="d9624-217">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v7.0.0/powershell-lts-7.0.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="d9624-218">Удаление — Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="d9624-218">Uninstallation - Red Hat Enterprise Linux (RHEL) 7</span></span>

```sh
sudo yum remove powershell
```

## <a name="opensuse"></a><span data-ttu-id="d9624-219">openSUSE</span><span class="sxs-lookup"><span data-stu-id="d9624-219">openSUSE</span></span>

### <a name="installation---opensuse-423"></a><span data-ttu-id="d9624-220">Установка — openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="d9624-220">Installation - openSUSE 42.3</span></span>

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

### <a name="installation---opensuse-leap-15"></a><span data-ttu-id="d9624-221">Установка — openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="d9624-221">Installation - openSUSE Leap 15</span></span>

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

### <a name="uninstallation---opensuse-423-opensuse-leap-15"></a><span data-ttu-id="d9624-222">Удаление — openSUSE 42.3, openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="d9624-222">Uninstallation - openSUSE 42.3, openSUSE Leap 15</span></span>

```sh
rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="fedora"></a><span data-ttu-id="d9624-223">Fedora</span><span class="sxs-lookup"><span data-stu-id="d9624-223">Fedora</span></span>

> [!NOTE]
> <span data-ttu-id="d9624-224">Fedora 28 поддерживается только в PowerShell 6.1 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="d9624-224">Fedora 28 is only supported in PowerShell 6.1 and newer.</span></span>

> [!NOTE]
> <span data-ttu-id="d9624-225">Fedora 29 и 30 поддерживается только в PowerShell 7.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="d9624-225">Fedora 29 and 30 are only supported in PowerShell 7.0 and newer.</span></span>

### <a name="installation-via-package-repository-preferred---fedora-28-29-and-30"></a><span data-ttu-id="d9624-226">Установка с помощью репозитория пакетов (рекомендуется) — Fedora 28, 29 и 30</span><span class="sxs-lookup"><span data-stu-id="d9624-226">Installation via Package Repository (preferred) - Fedora 28, 29, and 30</span></span>

<span data-ttu-id="d9624-227">Чтобы упростить установку и обновление, PowerShell для Linux публикуется в официальных репозиториях Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d9624-227">PowerShell for Linux is published to official Microsoft repositories for easy installation and updates.</span></span>

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

### <a name="installation-via-direct-download---fedora-28-29-and-30"></a><span data-ttu-id="d9624-228">Установка с помощью прямого скачивания — Fedora 28, 29 и 30</span><span class="sxs-lookup"><span data-stu-id="d9624-228">Installation via Direct Download - Fedora 28, 29, and 30</span></span>

<span data-ttu-id="d9624-229">Скачайте пакет RPM `powershell-7.0.0-1.rhel.7.x86_64.rpm` со страницы [выпусками][] на компьютер с Fedora.</span><span class="sxs-lookup"><span data-stu-id="d9624-229">Download the RPM package `powershell-7.0.0-1.rhel.7.x86_64.rpm` from the [releases][] page onto the Fedora machine.</span></span>

<span data-ttu-id="d9624-230">Затем выполните в терминале следующие команды:</span><span class="sxs-lookup"><span data-stu-id="d9624-230">Then, in the terminal, execute the following commands:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install powershell-7.0.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="d9624-231">RPM можно установить без промежуточного скачивания:</span><span class="sxs-lookup"><span data-stu-id="d9624-231">You can install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo dnf install compat-openssl10
sudo dnf install https://github.com/PowerShell/PowerShell/releases/download/v7.0.0/powershell-7.0.0-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---fedora-28-29-and-30"></a><span data-ttu-id="d9624-232">Удаление — Fedora 28, 29 и 30</span><span class="sxs-lookup"><span data-stu-id="d9624-232">Uninstallation - Fedora 28, 29, and 30</span></span>

```sh
sudo dnf remove powershell
```

## <a name="arch-linux"></a><span data-ttu-id="d9624-233">Arch Linux</span><span class="sxs-lookup"><span data-stu-id="d9624-233">Arch Linux</span></span>

> [!NOTE]
> <span data-ttu-id="d9624-234">Arch официально не поддерживается корпорацией Майкрософт, но поддерживается сообществом.</span><span class="sxs-lookup"><span data-stu-id="d9624-234">Arch support is not officially supported by Microsoft and is maintained by the community.</span></span>

<span data-ttu-id="d9624-235">PowerShell можно получить из пользовательского репозитория [Arch Linux][] (AUR).</span><span class="sxs-lookup"><span data-stu-id="d9624-235">PowerShell is available from the [Arch Linux][] User Repository (AUR).</span></span>

- <span data-ttu-id="d9624-236">Его можно скомпилировать с помощью [последнего выпуска с тегами][arch-release].</span><span class="sxs-lookup"><span data-stu-id="d9624-236">It can be compiled with the [latest tagged release][arch-release]</span></span>
- <span data-ttu-id="d9624-237">Его можно скомпилировать из [последней фиксации в основной репозиторий][arch-git].</span><span class="sxs-lookup"><span data-stu-id="d9624-237">It can be compiled from the [latest commit to master][arch-git]</span></span>
- <span data-ttu-id="d9624-238">Его можно установить с помощью [двоичного файла последнего выпуска][arch-bin].</span><span class="sxs-lookup"><span data-stu-id="d9624-238">It can be installed using the [latest release binary][arch-bin]</span></span>

<span data-ttu-id="d9624-239">Пакеты в AUR обслуживаются сообществом — официальная поддержка не предусмотрена.</span><span class="sxs-lookup"><span data-stu-id="d9624-239">Packages in the AUR are community maintained; there's no official support.</span></span>

<span data-ttu-id="d9624-240">Дополнительные сведения об установке пакетов из AUR см. на [вики-сайте Arch Linux](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) или в статье [Использование PowerShell в Docker](powershell-in-docker.md).</span><span class="sxs-lookup"><span data-stu-id="d9624-240">For more information on installing packages from the AUR, see the [Arch Linux wiki](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) or [Using PowerShell in Docker](powershell-in-docker.md).</span></span>

[Arch Linux]: https://www.archlinux.org/download/
[arch-release]: https://aur.archlinux.org/packages/powershell/
[arch-git]: https://aur.archlinux.org/packages/powershell-git/
[arch-bin]: https://aur.archlinux.org/packages/powershell-bin/

## <a name="snap-package"></a><span data-ttu-id="d9624-242">Snap-пакет</span><span class="sxs-lookup"><span data-stu-id="d9624-242">Snap Package</span></span>

### <a name="getting-snapd"></a><span data-ttu-id="d9624-243">Установка Snap</span><span class="sxs-lookup"><span data-stu-id="d9624-243">Getting snapd</span></span>

<span data-ttu-id="d9624-244">Утилита `snapd` необходима для запуска snap-пакетов.</span><span class="sxs-lookup"><span data-stu-id="d9624-244">`snapd` is required to run snaps.</span></span> <span data-ttu-id="d9624-245">Чтобы убедиться, что утилита `snapd` установлена, воспользуйтесь [этими инструкциями](https://docs.snapcraft.io/core/install).</span><span class="sxs-lookup"><span data-stu-id="d9624-245">Use [these instructions](https://docs.snapcraft.io/core/install) to make sure you have `snapd` installed.</span></span>

### <a name="installation-via-snap"></a><span data-ttu-id="d9624-246">Установка с использованием Snap</span><span class="sxs-lookup"><span data-stu-id="d9624-246">Installation via Snap</span></span>

<span data-ttu-id="d9624-247">Чтобы упростить установку и обновление, PowerShell для Linux публикуется в [хранилище Snap](https://snapcraft.io/store).</span><span class="sxs-lookup"><span data-stu-id="d9624-247">PowerShell for Linux is published to the [Snap store](https://snapcraft.io/store) for easy installation and updates.</span></span>

<span data-ttu-id="d9624-248">Предпочтительный метод выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d9624-248">The preferred method is as follows:</span></span>

```sh
# Install PowerShell
sudo snap install powershell --classic

# Start PowerShell
pwsh
```

<span data-ttu-id="d9624-249">Чтобы установить предварительную версию, используйте следующий метод:</span><span class="sxs-lookup"><span data-stu-id="d9624-249">To install a preview version, use the following method:</span></span>

```sh
# Install PowerShell
sudo snap install powershell-preview --classic

# Start PowerShell
pwsh-preview
```

<span data-ttu-id="d9624-250">После установки Snap автоматически обновится.</span><span class="sxs-lookup"><span data-stu-id="d9624-250">After installation, Snap will automatically upgrade.</span></span> <span data-ttu-id="d9624-251">Обновление можно активировать с помощью `sudo snap refresh powershell` или `sudo snap refresh powershell-preview`.</span><span class="sxs-lookup"><span data-stu-id="d9624-251">You can trigger an upgrade using `sudo snap refresh powershell` or `sudo snap refresh powershell-preview`.</span></span>

### <a name="uninstallation"></a><span data-ttu-id="d9624-252">Удаление</span><span class="sxs-lookup"><span data-stu-id="d9624-252">Uninstallation</span></span>

```sh
sudo snap remove powershell
```

<span data-ttu-id="d9624-253">или диспетчер конфигурации служб</span><span class="sxs-lookup"><span data-stu-id="d9624-253">or</span></span>

```sh
sudo snap remove powershell-preview
```

## <a name="kali"></a><span data-ttu-id="d9624-254">Kali</span><span class="sxs-lookup"><span data-stu-id="d9624-254">Kali</span></span>

> [!NOTE]
> <span data-ttu-id="d9624-255">Kali официально не поддерживается корпорацией Майкрософт, но поддерживается сообществом.</span><span class="sxs-lookup"><span data-stu-id="d9624-255">Kali support is not officially supported by Microsoft and is maintained by the community.</span></span>

### <a name="installation---kali"></a><span data-ttu-id="d9624-256">Установка — Kali</span><span class="sxs-lookup"><span data-stu-id="d9624-256">Installation - Kali</span></span>

```sh
# Install PowerShell package
apt update && apt -y install powershell

# Start PowerShell
pwsh
```

### <a name="uninstallation---kali"></a><span data-ttu-id="d9624-257">Удаление — Kali</span><span class="sxs-lookup"><span data-stu-id="d9624-257">Uninstallation - Kali</span></span>

```sh
# Uninstall PowerShell package
apt -y remove powershell
```

## <a name="raspbian"></a><span data-ttu-id="d9624-258">Raspbian</span><span class="sxs-lookup"><span data-stu-id="d9624-258">Raspbian</span></span>

> [!NOTE]
> <span data-ttu-id="d9624-259">Поддержка Raspbian на этапе эксперимента.</span><span class="sxs-lookup"><span data-stu-id="d9624-259">Raspbian support is experimental.</span></span>

<span data-ttu-id="d9624-260">Сейчас PowerShell поддерживается только в Raspbian Stretch.</span><span class="sxs-lookup"><span data-stu-id="d9624-260">Currently, PowerShell is only supported on Raspbian Stretch.</span></span>

<span data-ttu-id="d9624-261">CoreCLR и PowerShell будут работать только на устройствах Pi 2 и Pi 3. На таких устройствах, как [Pi Zero](https://github.com/dotnet/coreclr/issues/10605), установлены процессоры, поддержка которых не предусмотрена.</span><span class="sxs-lookup"><span data-stu-id="d9624-261">CoreCLR and PowerShell will only work on Pi 2 and Pi 3 devices as other devices, like [Pi Zero](https://github.com/dotnet/coreclr/issues/10605), have an unsupported processor.</span></span>

<span data-ttu-id="d9624-262">Загрузите [Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) и следуйте [инструкциям по установке](https://www.raspberrypi.org/documentation/installation/installing-images/README.md), чтобы установить его на свой Pi.</span><span class="sxs-lookup"><span data-stu-id="d9624-262">Download [Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) and follow the [installation instructions](https://www.raspberrypi.org/documentation/installation/installing-images/README.md) to get it onto your Pi.</span></span>

### <a name="installation---raspbian"></a><span data-ttu-id="d9624-263">Установка — Raspbian</span><span class="sxs-lookup"><span data-stu-id="d9624-263">Installation - Raspbian</span></span>

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

<span data-ttu-id="d9624-264">При необходимости можно создать символьную ссылку для запуска PowerShell без указания пути к двоичному файлу `pwsh`.</span><span class="sxs-lookup"><span data-stu-id="d9624-264">Optionally, you can create a symbolic link to start PowerShell without specifying the path to the `pwsh` binary.</span></span>

```sh
# Start PowerShell from bash with sudo to create a symbolic link
sudo ~/powershell/pwsh -c New-Item -ItemType SymbolicLink -Path "/usr/bin/pwsh" -Target "$PSHOME/pwsh" -Force

# alternatively you can run following to create a symbolic link
# sudo ln -s ~/powershell/pwsh /usr/bin/pwsh

# Now to start PowerShell you can just run "pwsh"
```

### <a name="uninstallation---raspbian"></a><span data-ttu-id="d9624-265">Удаление — Raspbian</span><span class="sxs-lookup"><span data-stu-id="d9624-265">Uninstallation - Raspbian</span></span>

```sh
rm -rf ~/powershell
```

## <a name="installing-preview-releases"></a><span data-ttu-id="d9624-266">Установка предварительных выпусков</span><span class="sxs-lookup"><span data-stu-id="d9624-266">Installing Preview Releases</span></span>

<span data-ttu-id="d9624-267">При установке предварительной версии PowerShell для Linux с помощью репозитория пакетов имя пакета меняется с `powershell` на `powershell-preview`.</span><span class="sxs-lookup"><span data-stu-id="d9624-267">When installing a PowerShell Preview release for Linux via a Package Repository, the package name changes from `powershell` to `powershell-preview`.</span></span>

<span data-ttu-id="d9624-268">При установке с помощью прямого скачивания изменяется только имя файла.</span><span class="sxs-lookup"><span data-stu-id="d9624-268">Installing via direct download doesn't change, other than the file name.</span></span>

<span data-ttu-id="d9624-269">В следующей таблице приведены команды для установки пакетов стабильной и предварительной версий с помощью различных диспетчеров пакетов:</span><span class="sxs-lookup"><span data-stu-id="d9624-269">The following table contains the commands to install the stable and preview packages using the various package managers:</span></span>

| <span data-ttu-id="d9624-270">Дистрибутивы</span><span class="sxs-lookup"><span data-stu-id="d9624-270">Distribution(s)</span></span> |            <span data-ttu-id="d9624-271">Команда стабильной версии</span><span class="sxs-lookup"><span data-stu-id="d9624-271">Stable Command</span></span>            |               <span data-ttu-id="d9624-272">Команда предварительной версии</span><span class="sxs-lookup"><span data-stu-id="d9624-272">Preview Command</span></span>                |
| --------------- | ------------------------------------ | -------------------------------------------- |
| <span data-ttu-id="d9624-273">Ubuntu, Debian</span><span class="sxs-lookup"><span data-stu-id="d9624-273">Ubuntu, Debian</span></span>  | `sudo apt-get install -y powershell` | `sudo apt-get install -y powershell-preview` |
| <span data-ttu-id="d9624-274">CentOS, RedHat</span><span class="sxs-lookup"><span data-stu-id="d9624-274">CentOS, RedHat</span></span>  | `sudo yum install -y powershell`     | `sudo yum install -y powershell-preview`     |
| <span data-ttu-id="d9624-275">Fedora</span><span class="sxs-lookup"><span data-stu-id="d9624-275">Fedora</span></span>          | `sudo dnf install -y powershell`     | `sudo dnf install -y powershell-preview`     |

## <a name="install-as-a-net-global-tool"></a><span data-ttu-id="d9624-276">Установка в качестве глобального средства .NET</span><span class="sxs-lookup"><span data-stu-id="d9624-276">Install as a .NET Global tool</span></span>

<span data-ttu-id="d9624-277">Если вы уже установили [пакет SDK для .NET Core](/dotnet/core/sdk), установите PowerShell как [глобальное средство .NET](/dotnet/core/tools/global-tools).</span><span class="sxs-lookup"><span data-stu-id="d9624-277">If you already have the [.NET Core SDK](/dotnet/core/sdk) installed, it's easy to install PowerShell as a [.NET Global tool](/dotnet/core/tools/global-tools).</span></span>

```
dotnet tool install --global PowerShell
```

<span data-ttu-id="d9624-278">Установщик инструмента dotnet добавляет `~/.dotnet/tools` в переменную среды `PATH`.</span><span class="sxs-lookup"><span data-stu-id="d9624-278">The dotnet tool installer adds `~/.dotnet/tools` to your `PATH` environment variable.</span></span> <span data-ttu-id="d9624-279">Но в выполняющейся оболочке отсутствует обновленная переменная `PATH`.</span><span class="sxs-lookup"><span data-stu-id="d9624-279">However, the currently running shell does not have the updated `PATH`.</span></span> <span data-ttu-id="d9624-280">Вы можете запустить PowerShell из новой оболочки, введя `pwsh`.</span><span class="sxs-lookup"><span data-stu-id="d9624-280">You should be able to start PowerShell from a new shell by typing `pwsh`.</span></span>

## <a name="binary-archives"></a><span data-ttu-id="d9624-281">Архивы двоичных файлов</span><span class="sxs-lookup"><span data-stu-id="d9624-281">Binary Archives</span></span>

<span data-ttu-id="d9624-282">Для поддержки расширенных сценариев развертывания на платформах Linux доступны архивы `tar.gz` двоичных файлов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d9624-282">PowerShell binary `tar.gz` archives are provided for Linux platforms to enable advanced deployment scenarios.</span></span>

### <a name="dependencies"></a><span data-ttu-id="d9624-283">Зависимости</span><span class="sxs-lookup"><span data-stu-id="d9624-283">Dependencies</span></span>

<span data-ttu-id="d9624-284">PowerShell создает переносимые двоичные файлы для всех дистрибутивов Linux.</span><span class="sxs-lookup"><span data-stu-id="d9624-284">PowerShell builds portable binaries for all Linux distributions.</span></span> <span data-ttu-id="d9624-285">Но среда выполнения .NET Core, как и PowerShell, требует различные зависимости для разных дистрибутивов.</span><span class="sxs-lookup"><span data-stu-id="d9624-285">But, .NET Core runtime requires different dependencies on different distributions, and PowerShell does too.</span></span>

<span data-ttu-id="d9624-286">На следующей диаграмме показаны официально поддерживаемые зависимости .NET Core 2.0 для различных дистрибутивов Linux.</span><span class="sxs-lookup"><span data-stu-id="d9624-286">The following chart shows the .NET Core 2.0 dependencies that are officially supported on different Linux distributions.</span></span>

| <span data-ttu-id="d9624-287">OS</span><span class="sxs-lookup"><span data-stu-id="d9624-287">OS</span></span>                 | <span data-ttu-id="d9624-288">Зависимости</span><span class="sxs-lookup"><span data-stu-id="d9624-288">Dependencies</span></span> |
| ------------------ | ------------ |
| <span data-ttu-id="d9624-289">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="d9624-289">Ubuntu 16.04</span></span>       | <span data-ttu-id="d9624-290">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="d9624-290">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="d9624-291">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu55</span><span class="sxs-lookup"><span data-stu-id="d9624-291">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu55</span></span> |
| <span data-ttu-id="d9624-292">Ubuntu 17.10</span><span class="sxs-lookup"><span data-stu-id="d9624-292">Ubuntu 17.10</span></span>       | <span data-ttu-id="d9624-293">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="d9624-293">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="d9624-294">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu57</span><span class="sxs-lookup"><span data-stu-id="d9624-294">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu57</span></span> |
| <span data-ttu-id="d9624-295">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="d9624-295">Ubuntu 18.04</span></span>       | <span data-ttu-id="d9624-296">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="d9624-296">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="d9624-297">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu60</span><span class="sxs-lookup"><span data-stu-id="d9624-297">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu60</span></span> |
| <span data-ttu-id="d9624-298">Debian 8 (Jessie)</span><span class="sxs-lookup"><span data-stu-id="d9624-298">Debian 8 (Jessie)</span></span>  | <span data-ttu-id="d9624-299">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="d9624-299">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="d9624-300">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span><span class="sxs-lookup"><span data-stu-id="d9624-300">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span></span> |
| <span data-ttu-id="d9624-301">Debian 9 (Stretch)</span><span class="sxs-lookup"><span data-stu-id="d9624-301">Debian 9 (Stretch)</span></span> | <span data-ttu-id="d9624-302">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="d9624-302">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="d9624-303">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.2, libicu57</span><span class="sxs-lookup"><span data-stu-id="d9624-303">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.2, libicu57</span></span> |
| <span data-ttu-id="d9624-304">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="d9624-304">CentOS 7</span></span> <br> <span data-ttu-id="d9624-305">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="d9624-305">Oracle Linux 7</span></span> <br> <span data-ttu-id="d9624-306">RHEL 7</span><span class="sxs-lookup"><span data-stu-id="d9624-306">RHEL 7</span></span> | <span data-ttu-id="d9624-307">libunwind, libcurl, openssl-libs, libicu</span><span class="sxs-lookup"><span data-stu-id="d9624-307">libunwind, libcurl, openssl-libs, libicu</span></span> |
| <span data-ttu-id="d9624-308">openSUSE 42.3</span><span class="sxs-lookup"><span data-stu-id="d9624-308">openSUSE 42.3</span></span> | <span data-ttu-id="d9624-309">libcurl4, libopenssl1_0_0, libicu52_1</span><span class="sxs-lookup"><span data-stu-id="d9624-309">libcurl4, libopenssl1_0_0, libicu52_1</span></span> |
| <span data-ttu-id="d9624-310">openSUSE Leap 15</span><span class="sxs-lookup"><span data-stu-id="d9624-310">openSUSE Leap 15</span></span> | <span data-ttu-id="d9624-311">libcurl4, libopenssl1_0_0, libicu60_2</span><span class="sxs-lookup"><span data-stu-id="d9624-311">libcurl4, libopenssl1_0_0, libicu60_2</span></span> |
| <span data-ttu-id="d9624-312">Fedora 27</span><span class="sxs-lookup"><span data-stu-id="d9624-312">Fedora 27</span></span> <br> <span data-ttu-id="d9624-313">Fedora 28</span><span class="sxs-lookup"><span data-stu-id="d9624-313">Fedora 28</span></span> | <span data-ttu-id="d9624-314">libunwind, libcurl, openssl-libs, libicu, compat-openssl10</span><span class="sxs-lookup"><span data-stu-id="d9624-314">libunwind, libcurl, openssl-libs, libicu, compat-openssl10</span></span> |

<span data-ttu-id="d9624-315">Чтобы развернуть двоичные файлы PowerShell в дистрибутивах Linux, для которых официальная поддержка не предусмотрена, необходимо специально установить необходимые пакеты, чтобы выполнить все требования, касающиеся зависимостей, для целевой ОС.</span><span class="sxs-lookup"><span data-stu-id="d9624-315">To deploy PowerShell binaries on Linux distributions that aren't officially supported, you need to install the necessary dependencies for the target OS in separate steps.</span></span> <span data-ttu-id="d9624-316">Например, наш [Dockerfile для Amazon Linux][amazon-dockerfile] сначала устанавливает зависимости, а затем извлекает архив Linux `tar.gz`.</span><span class="sxs-lookup"><span data-stu-id="d9624-316">For example, our [Amazon Linux dockerfile][amazon-dockerfile] installs dependencies first, and then extracts the Linux `tar.gz` archive.</span></span>

[amazon-dockerfile]: https://github.com/PowerShell/PowerShell-Docker/blob/master/release/community-stable/amazonlinux/docker/Dockerfile

### <a name="installation---binary-archives"></a><span data-ttu-id="d9624-317">Установка — архивы двоичных файлов</span><span class="sxs-lookup"><span data-stu-id="d9624-317">Installation - Binary Archives</span></span>

#### <a name="linux"></a><span data-ttu-id="d9624-318">Linux</span><span class="sxs-lookup"><span data-stu-id="d9624-318">Linux</span></span>

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

### <a name="uninstalling-binary-archives"></a><span data-ttu-id="d9624-319">Удаление архивов двоичных файлов</span><span class="sxs-lookup"><span data-stu-id="d9624-319">Uninstalling binary archives</span></span>

```sh
sudo rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="paths"></a><span data-ttu-id="d9624-320">Пути</span><span class="sxs-lookup"><span data-stu-id="d9624-320">Paths</span></span>

- <span data-ttu-id="d9624-321">`$PSHOME` имеет значение `/opt/microsoft/powershell/7/`.</span><span class="sxs-lookup"><span data-stu-id="d9624-321">`$PSHOME` is `/opt/microsoft/powershell/7/`</span></span>
- <span data-ttu-id="d9624-322">Профили пользователей будут считаны из `~/.config/powershell/profile.ps1`.</span><span class="sxs-lookup"><span data-stu-id="d9624-322">User profiles will be read from `~/.config/powershell/profile.ps1`</span></span>
- <span data-ttu-id="d9624-323">Профили по умолчанию будут считаны из `$PSHOME/profile.ps1`.</span><span class="sxs-lookup"><span data-stu-id="d9624-323">Default profiles will be read from `$PSHOME/profile.ps1`</span></span>
- <span data-ttu-id="d9624-324">Модули пользователей будут считаны из `~/.local/share/powershell/Modules`.</span><span class="sxs-lookup"><span data-stu-id="d9624-324">User modules will be read from `~/.local/share/powershell/Modules`</span></span>
- <span data-ttu-id="d9624-325">Общие модули будут считаны из `/usr/local/share/powershell/Modules`.</span><span class="sxs-lookup"><span data-stu-id="d9624-325">Shared modules will be read from `/usr/local/share/powershell/Modules`</span></span>
- <span data-ttu-id="d9624-326">Модули по умолчанию будут считаны из `$PSHOME/Modules`.</span><span class="sxs-lookup"><span data-stu-id="d9624-326">Default modules will be read from `$PSHOME/Modules`</span></span>
- <span data-ttu-id="d9624-327">Журнал PSReadline будет записан в `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span><span class="sxs-lookup"><span data-stu-id="d9624-327">PSReadLine history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="d9624-328">Профили учитывают конфигурацию PowerShell для отдельных узлов, поэтому профили конкретных узлов по умолчанию находятся в `Microsoft.PowerShell_profile.ps1` в тех же расположениях.</span><span class="sxs-lookup"><span data-stu-id="d9624-328">The profiles respect PowerShell's per-host configuration, so the default host-specific profiles exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="d9624-329">PowerShell отвечает требованиям [спецификации каталога размещения файлов, связанных со средой настольной графической среды (X-сервера), стандартизированного XDG (X Desktop Group)][xdg-bds] в Linux.</span><span class="sxs-lookup"><span data-stu-id="d9624-329">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on Linux.</span></span>

[выпусками]: https://github.com/PowerShell/PowerShell/releases/latest
[releases]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
