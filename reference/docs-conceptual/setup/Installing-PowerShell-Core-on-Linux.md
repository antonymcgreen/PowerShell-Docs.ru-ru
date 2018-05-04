# <a name="installing-powershell-core-on-linux"></a><span data-ttu-id="beb5e-101">Установка PowerShell Core в Linux</span><span class="sxs-lookup"><span data-stu-id="beb5e-101">Installing PowerShell Core on Linux</span></span>

<span data-ttu-id="beb5e-102">Поддерживает [Ubuntu 14.04][u14], [Ubuntu 16.04][u16], [Ubuntu 17.04][u17], [Debian 8][deb8], [Debian 9][deb9], [CentOS 7][cos], [Red Hat Enterprise Linux (RHEL) 7][rhel7], [OpenSUSE 42.2][opensuse], [Fedora 25][fed25], [Fedora 26][fed26] и [Arch Linux][arch].</span><span class="sxs-lookup"><span data-stu-id="beb5e-102">Supports [Ubuntu 14.04][u14], [Ubuntu 16.04][u16], [Ubuntu 17.04][u17], [Debian 8][deb8], [Debian 9][deb9], [CentOS 7][cos], [Red Hat Enterprise Linux (RHEL) 7][rhel7], [OpenSUSE 42.2][opensuse], [Fedora 25][fed25], [Fedora 26][fed26], and [Arch Linux][arch].</span></span>

<span data-ttu-id="beb5e-103">Для дистрибутивов Linux без официальной поддержки попробуйте использовать [PowerShell AppImage][lai].</span><span class="sxs-lookup"><span data-stu-id="beb5e-103">For Linux distributions that are not officially supported, you can try using the [PowerShell AppImage][lai].</span></span>
<span data-ttu-id="beb5e-104">Можно также попытаться развернуть двоичные файлы PowerShell напрямую с помощью [архива`tar.gz`][tar] Linux, но при этом нужно отдельно настроить необходимые зависимости с учетом операционной системы.</span><span class="sxs-lookup"><span data-stu-id="beb5e-104">You can also try deploying PowerShell binaries directly using the Linux [`tar.gz` archive][tar], but you would need to set up the necessary dependencies based on the OS in separate steps.</span></span>

<span data-ttu-id="beb5e-105">Все пакеты доступны на нашей странице [выпусков][] GitHub.</span><span class="sxs-lookup"><span data-stu-id="beb5e-105">All packages are available on our GitHub [releases][] page.</span></span>
<span data-ttu-id="beb5e-106">После установки пакета запустите `pwsh` из терминала.</span><span class="sxs-lookup"><span data-stu-id="beb5e-106">Once the package is installed, run `pwsh` from a terminal.</span></span>

[u14]: #ubuntu-1404
[u16]: #ubuntu-1604
[u17]: #ubuntu-1704
[deb8]: #debian-8
[deb9]: #debian-9
[cos]: #centos-7
[rhel7]: #red-hat-enterprise-linux-rhel-7
[opensuse]: #opensuse-422
[fed25]: #fedora-25
[fed26]: #fedora-26
[arch]: #arch-linux
[lai]: #linux-appimage
[tar]: #binary-archives

## <a name="ubuntu-1404"></a><span data-ttu-id="beb5e-107">Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="beb5e-107">Ubuntu 14.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1404"></a><span data-ttu-id="beb5e-108">Установка с помощью репозитория пакетов — Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="beb5e-108">Installation via Package Repository - Ubuntu 14.04</span></span>

<span data-ttu-id="beb5e-109">Для упрощения установки (и обновления) PowerShell Core для Linux публикуются в репозиториях пакетов.</span><span class="sxs-lookup"><span data-stu-id="beb5e-109">PowerShell Core, for Linux, is published to package repositories for easy installation (and updates).</span></span>
<span data-ttu-id="beb5e-110">Это предпочтительный метод.</span><span class="sxs-lookup"><span data-stu-id="beb5e-110">This is the preferred method.</span></span>

```sh
# Import the public repository GPG keys
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -

# Register the Microsoft Ubuntu repository
curl https://packages.microsoft.com/config/ubuntu/14.04/prod.list | sudo tee /etc/apt/sources.list.d/microsoft.list

# Update the list of products
sudo apt-get update

# Install PowerShell
sudo apt-get install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="beb5e-111">В качестве суперпользователя зарегистрируйте репозиторий Microsoft.</span><span class="sxs-lookup"><span data-stu-id="beb5e-111">As superuser, register the Microsoft repository.</span></span>
<span data-ttu-id="beb5e-112">В дальнейшем для обновления установки необходимо просто использовать `sudo apt-get upgrade powershell`.</span><span class="sxs-lookup"><span data-stu-id="beb5e-112">From then on, you just need to use `sudo apt-get upgrade powershell` to update the installation.</span></span>

### <a name="installation-via-direct-download---ubuntu-1404"></a><span data-ttu-id="beb5e-113">Установка с помощью прямого скачивания — Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="beb5e-113">Installation via Direct Download - Ubuntu 14.04</span></span>

<span data-ttu-id="beb5e-114">Скачайте пакет Debian `powershell_6.0.2-1.ubuntu.14.04_amd64.deb` со страницы [выпусков][] на компьютер с Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="beb5e-114">Download the Debian package `powershell_6.0.2-1.ubuntu.14.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="beb5e-115">Затем выполните в терминале следующую команду:</span><span class="sxs-lookup"><span data-stu-id="beb5e-115">Then execute the following in the terminal:</span></span>

```sh
sudo dpkg -i powershell_6.0.2-1.ubuntu.14.04_amd64.deb
sudo apt-get install -f
```

> <span data-ttu-id="beb5e-116">Обратите внимание, что `dpkg -i` завершится со сбоем из-за несоблюдения зависимостей; следующая команда `apt-get install -f` разрешает их и завершает настройку пакета PowerShell.</span><span class="sxs-lookup"><span data-stu-id="beb5e-116">Please note that `dpkg -i` will fail with unmet dependencies; the next command, `apt-get install -f` resolves these and then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1404"></a><span data-ttu-id="beb5e-117">Удаление — Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="beb5e-117">Uninstallation - Ubuntu 14.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1604"></a><span data-ttu-id="beb5e-118">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="beb5e-118">Ubuntu 16.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1604"></a><span data-ttu-id="beb5e-119">Установка с помощью репозитория пакетов — Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="beb5e-119">Installation via Package Repository - Ubuntu 16.04</span></span>

<span data-ttu-id="beb5e-120">Для упрощения установки (и обновления) PowerShell Core для Linux публикуются в репозиториях пакетов.</span><span class="sxs-lookup"><span data-stu-id="beb5e-120">PowerShell Core, for Linux, is published to package repositories for easy installation (and updates).</span></span>
<span data-ttu-id="beb5e-121">Это предпочтительный метод.</span><span class="sxs-lookup"><span data-stu-id="beb5e-121">This is the preferred method.</span></span>

```sh
# Import the public repository GPG keys
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -

# Register the Microsoft Ubuntu repository
sudo curl -o /etc/apt/sources.list.d/microsoft.list https://packages.microsoft.com/config/ubuntu/16.04/prod.list

# Update the list of products
sudo apt-get update

# Install PowerShell
sudo apt-get install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="beb5e-122">Зарегистрировав репозиторий Майкрософт в качестве суперпользователя, в дальнейшем вам потребуется лишь использовать `sudo apt-get upgrade powershell` для его обновления.</span><span class="sxs-lookup"><span data-stu-id="beb5e-122">After registering the Microsoft repository once as superuser, from then on, you just need to use `sudo apt-get upgrade powershell` to update it.</span></span>

### <a name="installation-via-direct-download---ubuntu-1604"></a><span data-ttu-id="beb5e-123">Установка с помощью прямого скачивания — Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="beb5e-123">Installation via Direct Download - Ubuntu 16.04</span></span>

<span data-ttu-id="beb5e-124">Скачайте пакет Debian `powershell_6.0.2-1.ubuntu.16.04_amd64.deb` со страницы [выпусков][] на компьютер с Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="beb5e-124">Download the Debian package `powershell_6.0.2-1.ubuntu.16.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="beb5e-125">Затем выполните в терминале следующую команду:</span><span class="sxs-lookup"><span data-stu-id="beb5e-125">Then execute the following in the terminal:</span></span>

```sh
sudo dpkg -i powershell_6.0.2-1.ubuntu.16.04_amd64.deb
sudo apt-get install -f
```

> <span data-ttu-id="beb5e-126">Обратите внимание, что `dpkg -i` завершится со сбоем из-за несоблюдения зависимостей; следующая команда `apt-get install -f` разрешает их и завершает настройку пакета PowerShell.</span><span class="sxs-lookup"><span data-stu-id="beb5e-126">Please note that `dpkg -i` will fail with unmet dependencies; the next command, `apt-get install -f` resolves these and then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1604"></a><span data-ttu-id="beb5e-127">Удаление — Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="beb5e-127">Uninstallation - Ubuntu 16.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1704"></a><span data-ttu-id="beb5e-128">Ubuntu 17.04</span><span class="sxs-lookup"><span data-stu-id="beb5e-128">Ubuntu 17.04</span></span>

### <a name="installation-via-package-repository---ubuntu-1704"></a><span data-ttu-id="beb5e-129">Установка с помощью репозитория пакетов — Ubuntu 17.04</span><span class="sxs-lookup"><span data-stu-id="beb5e-129">Installation via Package Repository - Ubuntu 17.04</span></span>

<span data-ttu-id="beb5e-130">Для упрощения установки (и обновления) PowerShell Core для Linux публикуются в репозиториях пакетов.</span><span class="sxs-lookup"><span data-stu-id="beb5e-130">PowerShell Core, for Linux, is published to package repositories for easy installation (and updates).</span></span>
<span data-ttu-id="beb5e-131">Это предпочтительный метод.</span><span class="sxs-lookup"><span data-stu-id="beb5e-131">This is the preferred method.</span></span>

```sh
# Import the public repository GPG keys
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -

# Register the Microsoft Ubuntu repository
sudo curl -o /etc/apt/sources.list.d/microsoft.list https://packages.microsoft.com/config/ubuntu/17.04/prod.list

# Update the list of products
sudo apt-get update

# Install PowerShell
sudo apt-get install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="beb5e-132">Зарегистрировав репозиторий Майкрософт в качестве суперпользователя, в дальнейшем вам потребуется лишь использовать `sudo apt-get upgrade powershell` для его обновления.</span><span class="sxs-lookup"><span data-stu-id="beb5e-132">After registering the Microsoft repository once as superuser, from then on, you just need to use `sudo apt-get upgrade powershell` to update it.</span></span>

### <a name="installation-via-direct-download---ubuntu-1704"></a><span data-ttu-id="beb5e-133">Установка с помощью прямого скачивания — Ubuntu 17.04</span><span class="sxs-lookup"><span data-stu-id="beb5e-133">Installation via Direct Download - Ubuntu 17.04</span></span>

<span data-ttu-id="beb5e-134">Скачайте пакет Debian `powershell_6.0.2-1.ubuntu.17.04_amd64.deb` со страницы [выпусков][] на компьютер с Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="beb5e-134">Download the Debian package `powershell_6.0.2-1.ubuntu.17.04_amd64.deb` from the [releases][] page onto the Ubuntu machine.</span></span>

<span data-ttu-id="beb5e-135">Затем выполните в терминале следующую команду:</span><span class="sxs-lookup"><span data-stu-id="beb5e-135">Then execute the following in the terminal:</span></span>

```sh
sudo dpkg -i powershell_6.0.2-1.ubuntu.17.04_amd64.deb
sudo apt-get install -f
```

> <span data-ttu-id="beb5e-136">Обратите внимание, что `dpkg -i` завершится со сбоем из-за несоблюдения зависимостей; следующая команда `apt-get install -f` разрешает их и завершает настройку пакета PowerShell.</span><span class="sxs-lookup"><span data-stu-id="beb5e-136">Please note that `dpkg -i` will fail with unmet dependencies; the next command, `apt-get install -f` resolves these and then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---ubuntu-1704"></a><span data-ttu-id="beb5e-137">Удаление — Ubuntu 17.04</span><span class="sxs-lookup"><span data-stu-id="beb5e-137">Uninstallation - Ubuntu 17.04</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="debian-8"></a><span data-ttu-id="beb5e-138">Debian 8</span><span class="sxs-lookup"><span data-stu-id="beb5e-138">Debian 8</span></span>

### <a name="installation-via-package-repository---debian-8"></a><span data-ttu-id="beb5e-139">Установка с помощью репозитория пакетов — Debian 8</span><span class="sxs-lookup"><span data-stu-id="beb5e-139">Installation via Package Repository - Debian 8</span></span>

<span data-ttu-id="beb5e-140">Для упрощения установки (и обновления) PowerShell Core для Linux публикуются в репозиториях пакетов.</span><span class="sxs-lookup"><span data-stu-id="beb5e-140">PowerShell Core, for Linux, is published to package repositories for easy installation (and updates).</span></span>
<span data-ttu-id="beb5e-141">Это предпочтительный метод.</span><span class="sxs-lookup"><span data-stu-id="beb5e-141">This is the preferred method.</span></span>

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

<span data-ttu-id="beb5e-142">Зарегистрировав репозиторий Майкрософт в качестве суперпользователя, в дальнейшем вам потребуется лишь использовать `sudo apt-get upgrade powershell` для его обновления.</span><span class="sxs-lookup"><span data-stu-id="beb5e-142">After registering the Microsoft repository once as superuser, from then on, you just need to use `sudo apt-get upgrade powershell` to update it.</span></span>

### <a name="installation-via-direct-download---debian-8"></a><span data-ttu-id="beb5e-143">Установка с помощью прямого скачивания — Debian 8</span><span class="sxs-lookup"><span data-stu-id="beb5e-143">Installation via Direct Download - Debian 8</span></span>

<span data-ttu-id="beb5e-144">Скачайте пакет Debian `powershell_6.0.2-1.debian.8_amd64.deb` со страницы [выпусков][] на компьютер с Debian.</span><span class="sxs-lookup"><span data-stu-id="beb5e-144">Download the Debian package `powershell_6.0.2-1.debian.8_amd64.deb` from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="beb5e-145">Затем выполните в терминале следующую команду:</span><span class="sxs-lookup"><span data-stu-id="beb5e-145">Then execute the following in the terminal:</span></span>

```sh
sudo dpkg -i powershell_6.0.2-1.debian.8_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="beb5e-146">Обратите внимание на то, что `dpkg -i` не сможет функционировать при наличии неудовлетворенных зависимостей.</span><span class="sxs-lookup"><span data-stu-id="beb5e-146">Please note that `dpkg -i` will fail with unmet dependencies.</span></span>
> <span data-ttu-id="beb5e-147">Команда `apt-get install -f` разрешает все такие зависимости и завершает настройку пакета PowerShell.</span><span class="sxs-lookup"><span data-stu-id="beb5e-147">The next command, `apt-get install -f` resolves these and then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---debian-8"></a><span data-ttu-id="beb5e-148">Удаление — Debian 8</span><span class="sxs-lookup"><span data-stu-id="beb5e-148">Uninstallation - Debian 8</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="debian-9"></a><span data-ttu-id="beb5e-149">Debian 9</span><span class="sxs-lookup"><span data-stu-id="beb5e-149">Debian 9</span></span>

### <a name="installation-via-package-repository---debian-9"></a><span data-ttu-id="beb5e-150">Установка с помощью репозитория пакетов — Debian 9</span><span class="sxs-lookup"><span data-stu-id="beb5e-150">Installation via Package Repository - Debian 9</span></span>

<span data-ttu-id="beb5e-151">Для упрощения установки (и обновления) PowerShell Core для Linux публикуются в репозиториях пакетов.</span><span class="sxs-lookup"><span data-stu-id="beb5e-151">PowerShell Core, for Linux, is published to package repositories for easy installation (and updates).</span></span>
<span data-ttu-id="beb5e-152">Это предпочтительный метод.</span><span class="sxs-lookup"><span data-stu-id="beb5e-152">This is the preferred method.</span></span>

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

<span data-ttu-id="beb5e-153">Зарегистрировав репозиторий Майкрософт в качестве суперпользователя, в дальнейшем вам потребуется лишь использовать `sudo apt-get upgrade powershell` для его обновления.</span><span class="sxs-lookup"><span data-stu-id="beb5e-153">After registering the Microsoft repository once as superuser, from then on, you just need to use `sudo apt-get upgrade powershell` to update it.</span></span>

### <a name="installation-via-direct-download---debian-9"></a><span data-ttu-id="beb5e-154">Установка с помощью прямого скачивания — Debian 9</span><span class="sxs-lookup"><span data-stu-id="beb5e-154">Installation via Direct Download - Debian 9</span></span>

<span data-ttu-id="beb5e-155">Скачайте пакет Debian `powershell_6.0.2-1.debian.9_amd64.deb` со страницы [выпусков][] на компьютер с Debian.</span><span class="sxs-lookup"><span data-stu-id="beb5e-155">Download the Debian package `powershell_6.0.2-1.debian.9_amd64.deb` from the [releases][] page onto the Debian machine.</span></span>

<span data-ttu-id="beb5e-156">Затем выполните в терминале следующую команду:</span><span class="sxs-lookup"><span data-stu-id="beb5e-156">Then execute the following in the terminal:</span></span>

```sh
sudo dpkg -i powershell_6.0.2-1.debian.9_amd64.deb
sudo apt-get install -f
```

> [!NOTE]
> <span data-ttu-id="beb5e-157">Обратите внимание на то, что `dpkg -i` не сможет функционировать при наличии неудовлетворенных зависимостей.</span><span class="sxs-lookup"><span data-stu-id="beb5e-157">Please note that `dpkg -i` will fail with unmet dependencies.</span></span>
> <span data-ttu-id="beb5e-158">Команда `apt-get install -f` разрешает все такие зависимости и завершает настройку пакета PowerShell.</span><span class="sxs-lookup"><span data-stu-id="beb5e-158">The next command, `apt-get install -f` resolves these and then finishes configuring the PowerShell package.</span></span>

### <a name="uninstallation---debian-9"></a><span data-ttu-id="beb5e-159">Удаление — Debian 9</span><span class="sxs-lookup"><span data-stu-id="beb5e-159">Uninstallation - Debian 9</span></span>

```sh
sudo apt-get remove powershell
```

## <a name="centos-7"></a><span data-ttu-id="beb5e-160">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="beb5e-160">CentOS 7</span></span>

> <span data-ttu-id="beb5e-161">Этот пакет также работает в Oracle Linux 7.</span><span class="sxs-lookup"><span data-stu-id="beb5e-161">This package also works on Oracle Linux 7.</span></span>

### <a name="installation-via-package-repository-preferred---centos-7"></a><span data-ttu-id="beb5e-162">Установка с помощью репозитория пакетов (рекомендуется) — CentOS 7</span><span class="sxs-lookup"><span data-stu-id="beb5e-162">Installation via Package Repository (preferred) - CentOS 7</span></span>

<span data-ttu-id="beb5e-163">Для упрощения установки (и обновления) PowerShell Core для Linux публикуются в официальных репозиториях Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="beb5e-163">PowerShell Core for Linux is published to official Microsoft repositories for easy installation (and updates).</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="beb5e-164">Зарегистрировав репозиторий Майкрософт в качестве суперпользователя, в дальнейшем вам потребуется лишь использовать `sudo yum update powershell` для обновления PowerShell.</span><span class="sxs-lookup"><span data-stu-id="beb5e-164">After registering the Microsoft repository once as superuser, you just need to use `sudo yum update powershell` to update PowerShell.</span></span>

### <a name="installation-via-direct-download---centos-7"></a><span data-ttu-id="beb5e-165">Установка с помощью прямого скачивания — CentOS 7</span><span class="sxs-lookup"><span data-stu-id="beb5e-165">Installation via Direct Download - CentOS 7</span></span>

<span data-ttu-id="beb5e-166">Используя [CentOS 7][], скачайте пакет RPM `powershell-6.0.2-1.rhel.7.x86_64.rpm` со страницы [выпусков][] на компьютер с CentOS.</span><span class="sxs-lookup"><span data-stu-id="beb5e-166">Using [CentOS 7][], download the RPM package `powershell-6.0.2-1.rhel.7.x86_64.rpm` from the [releases][] page onto the CentOS machine.</span></span>

<span data-ttu-id="beb5e-167">Затем выполните в терминале следующую команду:</span><span class="sxs-lookup"><span data-stu-id="beb5e-167">Then execute the following in the terminal:</span></span>

```sh
sudo yum install powershell-6.0.2-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="beb5e-168">Кроме того, RPM можно установить без промежуточного скачивания:</span><span class="sxs-lookup"><span data-stu-id="beb5e-168">You can also install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v6.0.2/powershell-6.0.2-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---centos-7"></a><span data-ttu-id="beb5e-169">Удаление — CentOS 7</span><span class="sxs-lookup"><span data-stu-id="beb5e-169">Uninstallation - CentOS 7</span></span>

```sh
sudo yum remove powershell
```

[CentOS 7]: https://www.centos.org/download/

## <a name="red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="beb5e-171">Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="beb5e-171">Red Hat Enterprise Linux (RHEL) 7</span></span>

### <a name="installation-via-package-repository-preferred---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="beb5e-172">Установка с помощью репозитория пакетов (рекомендуется) — Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="beb5e-172">Installation via Package Repository (preferred) - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="beb5e-173">Для упрощения установки (и обновления) PowerShell Core для Linux публикуются в официальных репозиториях Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="beb5e-173">PowerShell Core for Linux is published to official Microsoft repositories for easy installation (and updates).</span></span>

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

<span data-ttu-id="beb5e-174">Зарегистрировав репозиторий Майкрософт в качестве суперпользователя, в дальнейшем вам потребуется лишь использовать `sudo yum update powershell` для обновления PowerShell.</span><span class="sxs-lookup"><span data-stu-id="beb5e-174">After registering the Microsoft repository once as superuser, you just need to use `sudo yum update powershell` to update PowerShell.</span></span>

### <a name="installation-via-direct-download---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="beb5e-175">Установка с помощью прямого скачивания — Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="beb5e-175">Installation via Direct Download - Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="beb5e-176">Скачайте пакет RPM `powershell-6.0.2-1.rhel.7.x86_64.rpm` со страницы [выпусков][] на компьютер с Red Hat Enterprise Linux.</span><span class="sxs-lookup"><span data-stu-id="beb5e-176">Download the RPM package `powershell-6.0.2-1.rhel.7.x86_64.rpm` from the [releases][] page onto the Red Hat Enterprise Linux machine.</span></span>

<span data-ttu-id="beb5e-177">Затем выполните в терминале следующую команду:</span><span class="sxs-lookup"><span data-stu-id="beb5e-177">Then execute the following in the terminal:</span></span>

```sh
sudo yum install powershell-6.0.2-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="beb5e-178">Кроме того, RPM можно установить без промежуточного скачивания:</span><span class="sxs-lookup"><span data-stu-id="beb5e-178">You can also install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v6.0.2/powershell-6.0.2-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="beb5e-179">Удаление — Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="beb5e-179">Uninstallation - Red Hat Enterprise Linux (RHEL) 7</span></span>

```sh
sudo yum remove powershell
```

## <a name="opensuse-422"></a><span data-ttu-id="beb5e-180">OpenSUSE 42.2</span><span class="sxs-lookup"><span data-stu-id="beb5e-180">OpenSUSE 42.2</span></span>

> [!NOTE]
> <span data-ttu-id="beb5e-181">В процессе установки PowerShell Core `zypper` может выдать предупреждение о следующей ошибке:</span><span class="sxs-lookup"><span data-stu-id="beb5e-181">When installing PowerShell Core, `zypper` may report the following error:</span></span>
>
> ```Output
> Problem: nothing provides libcurl needed by powershell-6.0.1-1.rhel.7.x86_64
>  Solution 1: do not install powershell-6.0.1-1.rhel.7.x86_64
>  Solution 2: break powershell-6.0.1-1.rhel.7.x86_64 by ignoring some of its dependencies
> ```
>
> <span data-ttu-id="beb5e-182">В этом случае убедитесь в наличии совместимой библиотеки `libcurl`, проверив, что в результате выполнения следующей команды пакет `libcurl4` отображается как установленный:</span><span class="sxs-lookup"><span data-stu-id="beb5e-182">In this case, verify that a compatible `libcurl` library is present by checking that the following command shows the `libcurl4` package as installed:</span></span>
>
> ```sh
> zypper search --file-list --match-exact '/usr/lib64/libcurl.so.4'
> ```
>
> <span data-ttu-id="beb5e-183">Далее, при установке пакета PowerShell, выберите решение `break powershell-6.0.1-1.rhel.7.x86_64 by ignoring some of its dependencies`.</span><span class="sxs-lookup"><span data-stu-id="beb5e-183">Then choose the `break powershell-6.0.1-1.rhel.7.x86_64 by ignoring some of its dependencies` solution when installing the PowerShell package.</span></span>

### <a name="installation-via-package-repository-preferred---opensuse-422"></a><span data-ttu-id="beb5e-184">Установка с помощью репозитория пакетов (рекомендуется) — OpenSUSE 42.2</span><span class="sxs-lookup"><span data-stu-id="beb5e-184">Installation via Package Repository (preferred) - OpenSUSE 42.2</span></span>

<span data-ttu-id="beb5e-185">Для упрощения установки (и обновления) PowerShell Core для Linux публикуются в официальных репозиториях Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="beb5e-185">PowerShell Core for Linux is published to official Microsoft repositories for easy installation (and updates).</span></span>

```sh
# Register the Microsoft signature key
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc

# Add the Microsoft Product feed
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/zypp/repos.d/microsoft.repo

# Update the list of products
sudo zypper update

# Install PowerShell
sudo zypper install powershell

# Start PowerShell
pwsh
```

### <a name="installation-via-direct-download---opensuse-422"></a><span data-ttu-id="beb5e-186">Установка с помощью прямого скачивания — OpenSUSE 42.2</span><span class="sxs-lookup"><span data-stu-id="beb5e-186">Installation via Direct Download - OpenSUSE 42.2</span></span>

<span data-ttu-id="beb5e-187">Скачайте пакет RPM `powershell-6.0.2-1.rhel.7.x86_64.rpm` со страницы [выпусков][] на компьютер с OpenSUSE.</span><span class="sxs-lookup"><span data-stu-id="beb5e-187">Download the RPM package `powershell-6.0.2-1.rhel.7.x86_64.rpm` from the [releases][] page onto the OpenSUSE machine.</span></span>

```sh
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo zypper install powershell-6.0.2-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="beb5e-188">Кроме того, RPM можно установить без промежуточного скачивания:</span><span class="sxs-lookup"><span data-stu-id="beb5e-188">You can also install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo zypper install https://github.com/PowerShell/PowerShell/releases/download/v6.0.2/powershell-6.0.2-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---opensuse-422"></a><span data-ttu-id="beb5e-189">Удаление — OpenSUSE 42.2</span><span class="sxs-lookup"><span data-stu-id="beb5e-189">Uninstallation - OpenSUSE 42.2</span></span>

```sh
sudo zypper remove powershell
```

## <a name="fedora-25"></a><span data-ttu-id="beb5e-190">Fedora 25</span><span class="sxs-lookup"><span data-stu-id="beb5e-190">Fedora 25</span></span>

### <a name="installation-via-package-repository-preferred---fedora-25"></a><span data-ttu-id="beb5e-191">Установка с помощью репозитория пакетов (рекомендуется) — Fedora 25</span><span class="sxs-lookup"><span data-stu-id="beb5e-191">Installation via Package Repository (preferred) - Fedora 25</span></span>

<span data-ttu-id="beb5e-192">Для упрощения установки (и обновления) PowerShell Core для Linux публикуются в официальных репозиториях Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="beb5e-192">PowerShell Core for Linux is published to official Microsoft repositories for easy installation (and updates).</span></span>

```sh
# Register the Microsoft signature key
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc

# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Update the list of products
sudo dnf update

# Install PowerShell
sudo dnf install -y powershell

# Start PowerShell
pwsh
```

### <a name="installation-via-direct-download---fedora-25"></a><span data-ttu-id="beb5e-193">Установка с помощью прямого скачивания — Fedora 25</span><span class="sxs-lookup"><span data-stu-id="beb5e-193">Installation via Direct Download - Fedora 25</span></span>

<span data-ttu-id="beb5e-194">Скачайте пакет RPM `powershell-6.0.2-1.rhel.7.x86_64.rpm` со страницы [выпусков][] на компьютер с Fedora.</span><span class="sxs-lookup"><span data-stu-id="beb5e-194">Download the RPM package `powershell-6.0.2-1.rhel.7.x86_64.rpm` from the [releases][] page onto the Fedora machine.</span></span>

```sh
wget https://github.com/PowerShell/PowerShell/releases/download/v6.0.0/powershell-6.0.0-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="beb5e-195">Затем выполните в терминале следующую команду:</span><span class="sxs-lookup"><span data-stu-id="beb5e-195">Then execute the following in the terminal:</span></span>

```sh
sudo dnf install powershell-6.0.2-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="beb5e-196">Кроме того, RPM можно установить без промежуточного скачивания:</span><span class="sxs-lookup"><span data-stu-id="beb5e-196">You can also install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo dnf install https://github.com/PowerShell/PowerShell/releases/download/v6.0.2/powershell-6.0.2-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---fedora-25"></a><span data-ttu-id="beb5e-197">Удаление — Fedora 25</span><span class="sxs-lookup"><span data-stu-id="beb5e-197">Uninstallation - Fedora 25</span></span>

```sh
sudo dnf remove powershell
```

## <a name="fedora-26"></a><span data-ttu-id="beb5e-198">Fedora 26</span><span class="sxs-lookup"><span data-stu-id="beb5e-198">Fedora 26</span></span>

### <a name="installation-via-package-repository-preferred---fedora-26"></a><span data-ttu-id="beb5e-199">Установка с помощью репозитория пакетов (рекомендуется) — Fedora 26</span><span class="sxs-lookup"><span data-stu-id="beb5e-199">Installation via Package Repository (preferred) - Fedora 26</span></span>

<span data-ttu-id="beb5e-200">Для упрощения установки (и обновления) PowerShell Core для Linux публикуются в официальных репозиториях Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="beb5e-200">PowerShell Core for Linux is published to official Microsoft repositories for easy installation (and updates).</span></span>

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

### <a name="installation-via-direct-download---fedora-26"></a><span data-ttu-id="beb5e-201">Установка с помощью прямого скачивания — Fedora 26</span><span class="sxs-lookup"><span data-stu-id="beb5e-201">Installation via Direct Download - Fedora 26</span></span>

<span data-ttu-id="beb5e-202">Скачайте пакет RPM `powershell-6.0.2-1.rhel.7.x86_64.rpm` со страницы [выпусков][] на компьютер с Fedora.</span><span class="sxs-lookup"><span data-stu-id="beb5e-202">Download the RPM package `powershell-6.0.2-1.rhel.7.x86_64.rpm` from the [releases][] page onto the Fedora machine.</span></span>

<span data-ttu-id="beb5e-203">Затем выполните в терминале следующую команду:</span><span class="sxs-lookup"><span data-stu-id="beb5e-203">Then execute the following in the terminal:</span></span>

```sh
sudo dnf update
sudo dnf install compat-openssl10
sudo dnf install powershell-6.0.2-1.rhel.7.x86_64.rpm
```

<span data-ttu-id="beb5e-204">Кроме того, RPM можно установить без промежуточного скачивания:</span><span class="sxs-lookup"><span data-stu-id="beb5e-204">You can also install the RPM without the intermediate step of downloading it:</span></span>

```sh
sudo dnf update
sudo dnf install compat-openssl10
sudo dnf install https://github.com/PowerShell/PowerShell/releases/download/v6.0.2/powershell-6.0.2-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---fedora-26"></a><span data-ttu-id="beb5e-205">Удаление — Fedora 26</span><span class="sxs-lookup"><span data-stu-id="beb5e-205">Uninstallation - Fedora 26</span></span>

```sh
sudo dnf remove powershell
```

## <a name="arch-linux"></a><span data-ttu-id="beb5e-206">Arch Linux</span><span class="sxs-lookup"><span data-stu-id="beb5e-206">Arch Linux</span></span>

<span data-ttu-id="beb5e-207">PowerShell можно получить из пользовательского репозитория [Arch Linux][] (AUR).</span><span class="sxs-lookup"><span data-stu-id="beb5e-207">PowerShell is available from the [Arch Linux][] User Repository (AUR).</span></span>

* <span data-ttu-id="beb5e-208">Его можно скомпилировать с помощью [последнего выпуска с тегами][arch-release].</span><span class="sxs-lookup"><span data-stu-id="beb5e-208">It can be compiled with the [latest tagged release][arch-release]</span></span>
* <span data-ttu-id="beb5e-209">Его можно скомпилировать из [последней фиксации в основной репозиторий][arch-git].</span><span class="sxs-lookup"><span data-stu-id="beb5e-209">It can be compiled from the [latest commit to master][arch-git]</span></span>
* <span data-ttu-id="beb5e-210">Его можно установить с помощью [двоичного файла последнего выпуска][arch-bin].</span><span class="sxs-lookup"><span data-stu-id="beb5e-210">It can be installed using the [latest release binary][arch-bin]</span></span>

<span data-ttu-id="beb5e-211">Пакеты в AUR обслуживаются сообществом — официальная поддержка отсутствует.</span><span class="sxs-lookup"><span data-stu-id="beb5e-211">Packages in the AUR are community maintained - there is no official support.</span></span>

<span data-ttu-id="beb5e-212">Дополнительные сведения об установке пакетов из AUR см. на [вики-сайте Arch Linux](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) или в [DockerFile](https://github.com/PowerShell/PowerShell/blob/master/docker/community/archlinux/Dockerfile) сообщества.</span><span class="sxs-lookup"><span data-stu-id="beb5e-212">For more information on installing packages from the AUR, see the [Arch Linux wiki](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) or the community [DockerFile](https://github.com/PowerShell/PowerShell/blob/master/docker/community/archlinux/Dockerfile).</span></span>

[Arch Linux]: https://www.archlinux.org/download/
[arch-release]: https://aur.archlinux.org/packages/powershell/
[arch-git]: https://aur.archlinux.org/packages/powershell-git/
[arch-bin]: https://aur.archlinux.org/packages/powershell-bin/

## <a name="linux-appimage"></a><span data-ttu-id="beb5e-214">Linux AppImage</span><span class="sxs-lookup"><span data-stu-id="beb5e-214">Linux AppImage</span></span>

<span data-ttu-id="beb5e-215">Используя последний дистрибутив Linux, скачайте AppImage `powershell-6.0.1-x86_64.AppImage` со страницы [выпусков][] на компьютер с Linux.</span><span class="sxs-lookup"><span data-stu-id="beb5e-215">Using a recent Linux distribution, download the AppImage `powershell-6.0.1-x86_64.AppImage` from the [releases][] page onto the Linux machine.</span></span>

<span data-ttu-id="beb5e-216">Затем выполните в терминале следующую команду:</span><span class="sxs-lookup"><span data-stu-id="beb5e-216">Then execute the following in the terminal:</span></span>

```bash
chmod a+x powershell-6.0.1-x86_64.AppImage
./powershell-6.0.1-x86_64.AppImage
```

<span data-ttu-id="beb5e-217">[AppImage][] позволяет запустить PowerShell, не устанавливая его.</span><span class="sxs-lookup"><span data-stu-id="beb5e-217">The [AppImage][] lets you run PowerShell without installing it.</span></span>
<span data-ttu-id="beb5e-218">Это переносимое приложение, которое объединяет PowerShell и его зависимости (включая системные зависимости .NET Core) в единый пакет.</span><span class="sxs-lookup"><span data-stu-id="beb5e-218">It is a portable application that bundles PowerShell and its dependencies (including .NET Core's system dependencies) into one cohesive package.</span></span>
<span data-ttu-id="beb5e-219">Данный пакет представляет собой отдельный двоичный файл, работающий независимо от пользовательского дистрибутива Linux.</span><span class="sxs-lookup"><span data-stu-id="beb5e-219">This package  is a single binary that works independently of the user's Linux distribution.</span></span>

[appimage]: http://appimage.org/

## <a name="kali"></a><span data-ttu-id="beb5e-221">Kali</span><span class="sxs-lookup"><span data-stu-id="beb5e-221">Kali</span></span>

### <a name="installation"></a><span data-ttu-id="beb5e-222">Установка</span><span class="sxs-lookup"><span data-stu-id="beb5e-222">Installation</span></span>

```sh
# Download & Install prerequisites
sudo apt-get install libunwind8 libicu55
wget http://security.debian.org/debian-security/pool/updates/main/o/openssl/libssl1.0.0_1.0.1t-1+deb8u6_amd64.deb
sudo dpkg -i libssl1.0.0_1.0.1t-1+deb8u6_amd64.deb

# Install PowerShell
sudo dpkg -i powershell_6.0.2-1.ubuntu.16.04_amd64.deb

# Start PowerShell
pwsh
```

### <a name="run-powershell-in-latest-kali-kali-gnulinux-rolling-without-installing-it"></a><span data-ttu-id="beb5e-223">Запуск PowerShell в последней версии Kali (Kali GNU/Linux Rolling) без его установки</span><span class="sxs-lookup"><span data-stu-id="beb5e-223">Run PowerShell in latest Kali (Kali GNU/Linux Rolling) without installing it</span></span>

```sh
# Grab the latest App Image
wget https://github.com/PowerShell/PowerShell/releases/download/v6.0.2/powershell-6.0.2-x86_64.AppImage

# Make executable
chmod a+x powershell-6.0.2-x86_64.AppImage

# Start PowerShell
./powershell-6.0.2-x86_64.AppImage
```

### <a name="uninstallation---kali"></a><span data-ttu-id="beb5e-224">Удаление — Kali</span><span class="sxs-lookup"><span data-stu-id="beb5e-224">Uninstallation - Kali</span></span>

```sh
sudo dpkg -r powershell_6.0.2-1.ubuntu.16.04_amd64.deb
```

## <a name="raspbian"></a><span data-ttu-id="beb5e-225">Raspbian</span><span class="sxs-lookup"><span data-stu-id="beb5e-225">Raspbian</span></span>

<span data-ttu-id="beb5e-226">Сейчас PowerShell поддерживается только в Raspbian Stretch.</span><span class="sxs-lookup"><span data-stu-id="beb5e-226">Currently, PowerShell is only supported on Raspbian Stretch.</span></span>

<span data-ttu-id="beb5e-227">Кроме того, CoreCLR (а соответственно и PowerShell Core) будет работать только на устройствах Pi 2 и Pi 3, в то время как в устройствах наподобие [Pi Zero](https://github.com/dotnet/coreclr/issues/10605) установлены процессоры, поддержка которых не предусмотрена.</span><span class="sxs-lookup"><span data-stu-id="beb5e-227">Also CoreCLR (and thus PowerShell Core) will only work on Pi 2 and Pi 3 devices as other devices, like [Pi Zero](https://github.com/dotnet/coreclr/issues/10605), have an unsupported processor.</span></span>

<span data-ttu-id="beb5e-228">Загрузите [Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) и следуйте [инструкциям по установке](https://www.raspberrypi.org/documentation/installation/installing-images/README.md), чтобы установить его на свой Pi.</span><span class="sxs-lookup"><span data-stu-id="beb5e-228">Download [Raspbian Stretch](https://www.raspberrypi.org/downloads/raspbian/) and follow the [installation instructions](https://www.raspberrypi.org/documentation/installation/installing-images/README.md) to get it onto your Pi.</span></span>

### <a name="installation"></a><span data-ttu-id="beb5e-229">Установка</span><span class="sxs-lookup"><span data-stu-id="beb5e-229">Installation</span></span>

```sh
# Install prerequisites
sudo apt-get install libunwind8

# Grab the latest tar.gz
wget https://github.com/PowerShell/PowerShell/releases/download/v6.0.2/powershell-6.0.2-linux-arm32.tar.gz

# Make folder to put powershell
mkdir ~/powershell

# Unpack the tar.gz file
tar -xvf ./powershell-6.0.2-linux-arm32.tar.gz -C ~/powershell

# Start PowerShell
~/powershell/pwsh
```

<span data-ttu-id="beb5e-230">При необходимости можно создать символьную ссылку, позволяющую запустить PowerShell без указания пути к двоичному файлу pwsh</span><span class="sxs-lookup"><span data-stu-id="beb5e-230">Optionally you can create a symbolic link to be able to start PowerShell without specifying path to the "pwsh" binary</span></span>

```sh
# Start PowerShell from bash with sudo to create a symbolic link
sudo ~/powershell/pwsh -c New-Item -ItemType SymbolicLink -Path "/usr/bin/pwsh" -Target "\$PSHOME/pwsh" -Force

# alternatively you can run following to create a symbolic link
# sudo ln -s ~/powershell/pwsh /usr/bin/pwsh

# Now to start PowerShell you can just run "pwsh"
```

### <a name="uninstallation---raspbian"></a><span data-ttu-id="beb5e-231">Удаление — Raspbian</span><span class="sxs-lookup"><span data-stu-id="beb5e-231">Uninstallation - Raspbian</span></span>

```sh
rm -rf ~/powershell
```

## <a name="binary-archives"></a><span data-ttu-id="beb5e-232">Архивы двоичных файлов</span><span class="sxs-lookup"><span data-stu-id="beb5e-232">Binary Archives</span></span>

<span data-ttu-id="beb5e-233">Для поддержки расширенных сценариев развертывания на платформах Linux доступны архивы `tar.gz` двоичных файлов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="beb5e-233">PowerShell binary `tar.gz` archives are provided for Linux platforms to enable advanced deployment scenarios.</span></span>

### <a name="dependencies"></a><span data-ttu-id="beb5e-234">Зависимости</span><span class="sxs-lookup"><span data-stu-id="beb5e-234">Dependencies</span></span>

<span data-ttu-id="beb5e-235">PowerShell создает переносимые двоичные файлы для всех дистрибутивов Linux.</span><span class="sxs-lookup"><span data-stu-id="beb5e-235">PowerShell builds portable binaries for all Linux distributions.</span></span>
<span data-ttu-id="beb5e-236">Однако среда выполнения .NET Core требует различные зависимости для разных дистрибутивов, и поэтому то же самое делает и PowerShell.</span><span class="sxs-lookup"><span data-stu-id="beb5e-236">But .NET Core runtime requires different dependencies on different distributions, and hence PowerShell does the same.</span></span>

<span data-ttu-id="beb5e-237">На следующей диаграмме показаны официально поддерживаемые зависимости .NET Core 2.0 для различных дистрибутивов Linux.</span><span class="sxs-lookup"><span data-stu-id="beb5e-237">The following chart shows the .NET Core 2.0 dependencies that are officially supported on different Linux distributions.</span></span>

| <span data-ttu-id="beb5e-238">ОС</span><span class="sxs-lookup"><span data-stu-id="beb5e-238">OS</span></span>                 | <span data-ttu-id="beb5e-239">Зависимости</span><span class="sxs-lookup"><span data-stu-id="beb5e-239">Dependencies</span></span> |
| ------------------ | ------------ |
| <span data-ttu-id="beb5e-240">Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="beb5e-240">Ubuntu 14.04</span></span>       | <span data-ttu-id="beb5e-241">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="beb5e-241">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="beb5e-242">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span><span class="sxs-lookup"><span data-stu-id="beb5e-242">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span></span> |
| <span data-ttu-id="beb5e-243">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="beb5e-243">Ubuntu 16.04</span></span>       | <span data-ttu-id="beb5e-244">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="beb5e-244">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="beb5e-245">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu55</span><span class="sxs-lookup"><span data-stu-id="beb5e-245">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu55</span></span> |
| <span data-ttu-id="beb5e-246">Ubuntu 17.04</span><span class="sxs-lookup"><span data-stu-id="beb5e-246">Ubuntu 17.04</span></span>       | <span data-ttu-id="beb5e-247">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="beb5e-247">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="beb5e-248">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu57</span><span class="sxs-lookup"><span data-stu-id="beb5e-248">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu57</span></span> |
| <span data-ttu-id="beb5e-249">Debian 8 (Jessie)</span><span class="sxs-lookup"><span data-stu-id="beb5e-249">Debian 8 (Jessie)</span></span>  | <span data-ttu-id="beb5e-250">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="beb5e-250">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="beb5e-251">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span><span class="sxs-lookup"><span data-stu-id="beb5e-251">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52</span></span> |
| <span data-ttu-id="beb5e-252">Debian 9 (Stretch)</span><span class="sxs-lookup"><span data-stu-id="beb5e-252">Debian 9 (Stretch)</span></span> | <span data-ttu-id="beb5e-253">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span><span class="sxs-lookup"><span data-stu-id="beb5e-253">libc6, libgcc1, libgssapi-krb5-2, liblttng-ust0, libstdc++6,</span></span> <br> <span data-ttu-id="beb5e-254">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.2, libicu57</span><span class="sxs-lookup"><span data-stu-id="beb5e-254">libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.2, libicu57</span></span> |
| <span data-ttu-id="beb5e-255">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="beb5e-255">CentOS 7</span></span> <br> <span data-ttu-id="beb5e-256">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="beb5e-256">Oracle Linux 7</span></span> <br> <span data-ttu-id="beb5e-257">RHEL 7</span><span class="sxs-lookup"><span data-stu-id="beb5e-257">RHEL 7</span></span> <br> <span data-ttu-id="beb5e-258">OpenSUSE 42.2</span><span class="sxs-lookup"><span data-stu-id="beb5e-258">OpenSUSE 42.2</span></span> <br> <span data-ttu-id="beb5e-259">Fedora 25</span><span class="sxs-lookup"><span data-stu-id="beb5e-259">Fedora 25</span></span> | <span data-ttu-id="beb5e-260">libunwind, libcurl, openssl-libs, libicu</span><span class="sxs-lookup"><span data-stu-id="beb5e-260">libunwind, libcurl, openssl-libs, libicu</span></span> |
| <span data-ttu-id="beb5e-261">Fedora 26</span><span class="sxs-lookup"><span data-stu-id="beb5e-261">Fedora 26</span></span>          | <span data-ttu-id="beb5e-262">libunwind, libcurl, openssl-libs, libicu, compat-openssl10</span><span class="sxs-lookup"><span data-stu-id="beb5e-262">libunwind, libcurl, openssl-libs, libicu, compat-openssl10</span></span> |

<span data-ttu-id="beb5e-263">Чтобы развернуть двоичные файлы PowerShell в дистрибутивах Linux, для которых официальная поддержка не предусмотрена, необходимо специально установить необходимые пакеты, чтобы удовлетворить всем требованиям по зависимостям для целевой ОС.</span><span class="sxs-lookup"><span data-stu-id="beb5e-263">To deploy PowerShell binaries on Linux distributions that are not officially supported, you need to install the necessary dependencies for the target OS in separate steps.</span></span>
<span data-ttu-id="beb5e-264">Например, наш [Amazon Linux dockerfile][amazon-dockerfile] сначала устанавливает зависимости, а затем извлекает архив Linux `tar.gz`.</span><span class="sxs-lookup"><span data-stu-id="beb5e-264">For example, our [Amazon Linux dockerfile][amazon-dockerfile] installs dependencies first, and then extracts the Linux `tar.gz` archive.</span></span>

[amazon-dockerfile]: https://github.com/PowerShell/PowerShell/blob/master/docker/community/amazonlinux/Dockerfile

### <a name="installation---binary-archives"></a><span data-ttu-id="beb5e-265">Установка — архивы двоичных файлов</span><span class="sxs-lookup"><span data-stu-id="beb5e-265">Installation - Binary Archives</span></span>

#### <a name="linux"></a><span data-ttu-id="beb5e-266">Linux</span><span class="sxs-lookup"><span data-stu-id="beb5e-266">Linux</span></span>

```sh
# Download the powershell '.tar.gz' archive
curl -L -o /tmp/powershell.tar.gz https://github.com/PowerShell/PowerShell/releases/download/v6.0.2/powershell-6.0.2-linux-x64.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /opt/microsoft/powershell/6.0.2

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/6.0.2

# Set execute permissions
sudo chmod +x /opt/microsoft/powershell/6.0.2/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /opt/microsoft/powershell/6.0.2/pwsh /usr/bin/pwsh
```

### <a name="uninstalling-binary-archives"></a><span data-ttu-id="beb5e-267">Удаление архивов двоичных файлов</span><span class="sxs-lookup"><span data-stu-id="beb5e-267">Uninstalling binary archives</span></span>

```sh
sudo rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

## <a name="paths"></a><span data-ttu-id="beb5e-268">Пути</span><span class="sxs-lookup"><span data-stu-id="beb5e-268">Paths</span></span>

* <span data-ttu-id="beb5e-269">`$PSHOME` имеет значение `/opt/microsoft/powershell/6.0.2/`.</span><span class="sxs-lookup"><span data-stu-id="beb5e-269">`$PSHOME` is `/opt/microsoft/powershell/6.0.2/`</span></span>
* <span data-ttu-id="beb5e-270">Профили пользователей будут считаны из `~/.config/powershell/profile.ps1`.</span><span class="sxs-lookup"><span data-stu-id="beb5e-270">User profiles will be read from `~/.config/powershell/profile.ps1`</span></span>
* <span data-ttu-id="beb5e-271">Профили по умолчанию будут считаны из `$PSHOME/profile.ps1`.</span><span class="sxs-lookup"><span data-stu-id="beb5e-271">Default profiles will be read from `$PSHOME/profile.ps1`</span></span>
* <span data-ttu-id="beb5e-272">Модули пользователей будут считаны из `~/.local/share/powershell/Modules`.</span><span class="sxs-lookup"><span data-stu-id="beb5e-272">User modules will be read from `~/.local/share/powershell/Modules`</span></span>
* <span data-ttu-id="beb5e-273">Общие модули будут считаны из `/usr/local/share/powershell/Modules`.</span><span class="sxs-lookup"><span data-stu-id="beb5e-273">Shared modules will be read from `/usr/local/share/powershell/Modules`</span></span>
* <span data-ttu-id="beb5e-274">Модули по умолчанию будут считаны из `$PSHOME/Modules`.</span><span class="sxs-lookup"><span data-stu-id="beb5e-274">Default modules will be read from `$PSHOME/Modules`</span></span>
* <span data-ttu-id="beb5e-275">Журнал PSReadline будет записан в `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`.</span><span class="sxs-lookup"><span data-stu-id="beb5e-275">PSReadline history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="beb5e-276">Профили учитывают конфигурацию PowerShell для отдельных узлов, поэтому профили конкретных узлов по умолчанию находятся в `Microsoft.PowerShell_profile.ps1` в тех же расположениях.</span><span class="sxs-lookup"><span data-stu-id="beb5e-276">The profiles respect PowerShell's per-host configuration, so the default host-specific profiles exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="beb5e-277">PowerShell отвечает требованиям [спецификации каталога размещения файлов, связанных со средой настольной графической среды (X-сервера), стандартизированного XDG (X Desktop Group)][xdg-bds] в Linux.</span><span class="sxs-lookup"><span data-stu-id="beb5e-277">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on Linux.</span></span>

[выпусков]: https://github.com/PowerShell/PowerShell/releases/latest
[releases]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
