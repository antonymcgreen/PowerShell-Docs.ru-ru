---
title: Установка PowerShell Core в macOS
description: Сведения об установке PowerShell Core в macOS
ms.date: 12/12/2018
ms.openlocfilehash: 70f5d64aa8a697a9011d07fbcb2bb821463827e1
ms.sourcegitcommit: 58fb23c854f5a8b40ad1f952d3323aeeccac7a24
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "65229735"
---
# <a name="installing-powershell-core-on-macos"></a><span data-ttu-id="67684-103">Установка PowerShell Core в macOS</span><span class="sxs-lookup"><span data-stu-id="67684-103">Installing PowerShell Core on macOS</span></span>

<span data-ttu-id="67684-104">PowerShell Core поддерживает macOS версии 10.12 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="67684-104">PowerShell Core supports macOS 10.12 and higher.</span></span>
<span data-ttu-id="67684-105">Все пакеты доступны на нашей странице [выпусков][] GitHub.</span><span class="sxs-lookup"><span data-stu-id="67684-105">All packages are available on our GitHub [releases][] page.</span></span>
<span data-ttu-id="67684-106">После установки пакета запустите `pwsh` из терминала.</span><span class="sxs-lookup"><span data-stu-id="67684-106">After the package is installed, run `pwsh` from a terminal.</span></span>

## <a name="about-brew"></a><span data-ttu-id="67684-107">Сведения о Brew</span><span class="sxs-lookup"><span data-stu-id="67684-107">About Brew</span></span>

<span data-ttu-id="67684-108">[Homebrew][brew] является предпочтительным диспетчером пакетов для macOS.</span><span class="sxs-lookup"><span data-stu-id="67684-108">[Homebrew][brew] is the preferred package manager for macOS.</span></span>
<span data-ttu-id="67684-109">Если команда `brew` не найдена, нужно установить Homebrew по [соответствующим инструкциям][brew].</span><span class="sxs-lookup"><span data-stu-id="67684-109">If the `brew` command is not found, you need to install Homebrew following [their instructions][brew].</span></span>
<span data-ttu-id="67684-110">Вы также можете установить PowerShell с помощью [прямого скачивания](#installation-via-direct-download) или из [архивов двоичных файлов](#binary-archives).</span><span class="sxs-lookup"><span data-stu-id="67684-110">Otherwise you may install PowerShell via [Direct Download](#installation-via-direct-download) or from [Binary Archives](#binary-archives).</span></span>

## <a name="installation-of-latest-stable-release-via-homebrew-on-macos-1012-or-higher"></a><span data-ttu-id="67684-111">Установка последнего стабильного выпуска с помощью Homebrew в macOS 10.12 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="67684-111">Installation of latest stable release via Homebrew on macOS 10.12 or higher</span></span>

<span data-ttu-id="67684-112">См. дополнительные сведения о [Brew](#about-brew).</span><span class="sxs-lookup"><span data-stu-id="67684-112">See [About Brew](#about-brew) for information about Brew.</span></span>

<span data-ttu-id="67684-113">Теперь можно установить PowerShell:</span><span class="sxs-lookup"><span data-stu-id="67684-113">Now, you can install PowerShell:</span></span>

```sh
brew cask install powershell
```

<span data-ttu-id="67684-114">И наконец, убедитесь, что установка прошла без ошибок.</span><span class="sxs-lookup"><span data-stu-id="67684-114">Finally, verify that your install is working properly:</span></span>

```sh
pwsh
```

<span data-ttu-id="67684-115">После выпуска новых версий PowerShell обновите формулы Homebrew и PowerShell:</span><span class="sxs-lookup"><span data-stu-id="67684-115">When new versions of PowerShell are released, update Homebrew's formulae and upgrade PowerShell:</span></span>

```sh
brew update
brew cask upgrade powershell
```

> [!NOTE]
> <span data-ttu-id="67684-116">Приведенные выше команды можно вызвать из узла PowerShell (pwsh), но затем потребуется выйти из оболочки PowerShell и перезапустить ее, чтобы завершить обновление и обновить значения в таблице `$PSVersionTable`.</span><span class="sxs-lookup"><span data-stu-id="67684-116">The commands above can be called from within a PowerShell (pwsh) host, but then the PowerShell shell must be exited and restarted to complete the upgrade and refresh the values shown in `$PSVersionTable`.</span></span>

[brew]: http://brew.sh/

## <a name="installation-of-latest-preview-release-via-homebrew-on-macos-1012-or-higher"></a><span data-ttu-id="67684-117">Установка последнего предварительного выпуска с помощью Homebrew в macOS 10.12 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="67684-117">Installation of latest preview release via Homebrew on macOS 10.12 or higher</span></span>

<span data-ttu-id="67684-118">См. дополнительные сведения о [Brew](#about-brew).</span><span class="sxs-lookup"><span data-stu-id="67684-118">See [About Brew](#about-brew) for information about Brew.</span></span>

<span data-ttu-id="67684-119">После установки Homebrew можно установить PowerShell.</span><span class="sxs-lookup"><span data-stu-id="67684-119">After you've installed Homebrew, you can install PowerShell.</span></span>
<span data-ttu-id="67684-120">Сначала установите пакет [Cask-Versions][cask-versions], который позволит устанавливать альтернативные версии Cask-пакетов.</span><span class="sxs-lookup"><span data-stu-id="67684-120">First, install the [Cask-Versions][cask-versions] package that lets you install alternative versions of cask packages:</span></span>

```sh
brew tap homebrew/cask-versions
```

<span data-ttu-id="67684-121">Теперь можно установить PowerShell:</span><span class="sxs-lookup"><span data-stu-id="67684-121">Now, you can install PowerShell:</span></span>

```sh
brew cask install powershell-preview
```

<span data-ttu-id="67684-122">И наконец, убедитесь, что установка прошла без ошибок.</span><span class="sxs-lookup"><span data-stu-id="67684-122">Finally, verify that your install is working properly:</span></span>

```sh
pwsh-preview
```

<span data-ttu-id="67684-123">После выпуска новых версий PowerShell обновите формулы Homebrew и PowerShell:</span><span class="sxs-lookup"><span data-stu-id="67684-123">When new versions of PowerShell are released, update Homebrew's formulae and upgrade PowerShell:</span></span>

```sh
brew update
brew cask upgrade powershell-preview
```

> [!NOTE]
> <span data-ttu-id="67684-124">Команду, указанную выше, можно вызвать на узле PowerShell (pwsh), но для этого необходимо завершить его обновление. Что в свою очередь будет сделано, когда вы выйдете из PowerShell и перезапустите его.</span><span class="sxs-lookup"><span data-stu-id="67684-124">The commands above can be called from within a PowerShell (pwsh) host, but then the PowerShell shell must be exited and restarted to complete the upgrade.</span></span>
> <span data-ttu-id="67684-125">Обновите значения, которые отображаются в `$PSVersionTable`.</span><span class="sxs-lookup"><span data-stu-id="67684-125">and refresh the values shown in `$PSVersionTable`.</span></span>

## <a name="installation-via-direct-download"></a><span data-ttu-id="67684-126">Установка с помощью прямого скачивания</span><span class="sxs-lookup"><span data-stu-id="67684-126">Installation via Direct Download</span></span>

<span data-ttu-id="67684-127">Скачайте пакет PKG `powershell-6.2.0-osx-x64.pkg`</span><span class="sxs-lookup"><span data-stu-id="67684-127">Download the PKG package `powershell-6.2.0-osx-x64.pkg`</span></span>
<span data-ttu-id="67684-128">со страницы [выпусков][] на компьютер с macOS.</span><span class="sxs-lookup"><span data-stu-id="67684-128">from the [releases][] page onto your macOS machine.</span></span>

<span data-ttu-id="67684-129">Дважды щелкните файл и следуйте инструкциям на экране либо установите его из командной строки:</span><span class="sxs-lookup"><span data-stu-id="67684-129">You can double-click the file and follow the prompts, or install it from the terminal:</span></span>

```sh
sudo installer -pkg powershell-6.2.0-osx-x64.pkg -target /
```

<span data-ttu-id="67684-130">Установите [OpenSSL](#install-openssl).</span><span class="sxs-lookup"><span data-stu-id="67684-130">Install [OpenSSL](#install-openssl).</span></span> <span data-ttu-id="67684-131">OpenSSL требуется для удаленного взаимодействия PowerShell и операций CIM.</span><span class="sxs-lookup"><span data-stu-id="67684-131">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>

## <a name="binary-archives"></a><span data-ttu-id="67684-132">Архивы двоичных файлов</span><span class="sxs-lookup"><span data-stu-id="67684-132">Binary Archives</span></span>

<span data-ttu-id="67684-133">Для поддержки расширенных сценариев развертывания на платформе macOS доступны архивы `tar.gz` двоичных файлов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="67684-133">PowerShell binary `tar.gz` archives are provided for the macOS platform to enable advanced deployment scenarios.</span></span>

### <a name="installing-binary-archives-on-macos"></a><span data-ttu-id="67684-134">Установка архивов двоичных файлов в macOS</span><span class="sxs-lookup"><span data-stu-id="67684-134">Installing binary archives on macOS</span></span>

```sh
# Download the powershell '.tar.gz' archive
curl -L -o /tmp/powershell.tar.gz https://github.com/PowerShell/PowerShell/releases/download/v6.2.0/powershell-6.2.0-osx-x64.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /usr/local/microsoft/powershell/6.2.0

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /usr/local/microsoft/powershell/6.2.0

# Set execute permissions
sudo chmod +x /usr/local/microsoft/powershell/6.2.0/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /usr/local/microsoft/powershell/6.2.0/pwsh /usr/local/bin/pwsh
```

<span data-ttu-id="67684-135">Установите [OpenSSL](#install-openssl).</span><span class="sxs-lookup"><span data-stu-id="67684-135">Install [OpenSSL](#install-openssl).</span></span> <span data-ttu-id="67684-136">OpenSSL требуется для удаленного взаимодействия PowerShell и операций CIM.</span><span class="sxs-lookup"><span data-stu-id="67684-136">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>

## <a name="installing-dependencies"></a><span data-ttu-id="67684-137">Установка зависимостей</span><span class="sxs-lookup"><span data-stu-id="67684-137">Installing dependencies</span></span>

### <a name="install-xcode-command-line-tools"></a><span data-ttu-id="67684-138">Установка средств командной строки XCode</span><span class="sxs-lookup"><span data-stu-id="67684-138">Install XCode command-line tools</span></span>

```sh
xcode-select --install
```

### <a name="install-openssl"></a><span data-ttu-id="67684-139">Установка OpenSSL</span><span class="sxs-lookup"><span data-stu-id="67684-139">Install OpenSSL</span></span>

<span data-ttu-id="67684-140">OpenSSL требуется для удаленного взаимодействия PowerShell и операций CIM.</span><span class="sxs-lookup"><span data-stu-id="67684-140">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span> <span data-ttu-id="67684-141">Установка возможна с помощью MacPorts или Brew.</span><span class="sxs-lookup"><span data-stu-id="67684-141">You can install via MacPorts or Brew.</span></span>

#### <a name="install-openssl-via-brew"></a><span data-ttu-id="67684-142">Установка OpenSSL с помощью Brew</span><span class="sxs-lookup"><span data-stu-id="67684-142">Install OpenSSL via Brew</span></span>

<span data-ttu-id="67684-143">См. дополнительные сведения о [Brew](#about-brew).</span><span class="sxs-lookup"><span data-stu-id="67684-143">See [About Brew](#about-brew) for information about Brew.</span></span>

<span data-ttu-id="67684-144">Запустите `brew install openssl`, чтобы установить OpenSSL.</span><span class="sxs-lookup"><span data-stu-id="67684-144">To install OpenSSL, run `brew install openssl`.</span></span>

#### <a name="install-openssl-via-macports"></a><span data-ttu-id="67684-145">Установка OpenSSL с помощью MacPorts</span><span class="sxs-lookup"><span data-stu-id="67684-145">Install OpenSSL via MacPorts</span></span>

1. <span data-ttu-id="67684-146">Установите [средство командной строки XCode](#install-xcode-command-line-tools).</span><span class="sxs-lookup"><span data-stu-id="67684-146">Install the [XCode command line tools](#install-xcode-command-line-tools).</span></span>
1. <span data-ttu-id="67684-147">Установите MacPorts.</span><span class="sxs-lookup"><span data-stu-id="67684-147">Install MacPorts.</span></span>
   <span data-ttu-id="67684-148">Инструкции см. в [руководстве по установке](https://guide.macports.org/chunked/installing.macports.html).</span><span class="sxs-lookup"><span data-stu-id="67684-148">If you need instructions, refer to the [installation guide](https://guide.macports.org/chunked/installing.macports.html).</span></span>
1. <span data-ttu-id="67684-149">Обновите MacPorts, выполнив команду `sudo port selfupdate`.</span><span class="sxs-lookup"><span data-stu-id="67684-149">Update MacPorts by running `sudo port selfupdate`.</span></span>
1. <span data-ttu-id="67684-150">Обновите пакеты MacPorts, выполнив команду `sudo port upgrade outdated`.</span><span class="sxs-lookup"><span data-stu-id="67684-150">Upgrade MacPorts packages by running `sudo port upgrade outdated`.</span></span>
1. <span data-ttu-id="67684-151">Установите OpenSSL, запустив `sudo port install openssl`.</span><span class="sxs-lookup"><span data-stu-id="67684-151">Install OpenSSL by running `sudo port install openssl`.</span></span>
1. <span data-ttu-id="67684-152">Укажите ссылки на библиотеки, чтобы сделать их доступными для PowerShell:</span><span class="sxs-lookup"><span data-stu-id="67684-152">Link the libraries to make them available to PowerShell:</span></span>

```sh
sudo mkdir -p /usr/local/opt/openssl
sudo ln -s /opt/local/lib /usr/local/opt/openssl/lib
```

## <a name="uninstalling-powershell-core"></a><span data-ttu-id="67684-153">Удаление PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="67684-153">Uninstalling PowerShell Core</span></span>

<span data-ttu-id="67684-154">Если вы установили PowerShell с помощью Homebrew, используйте следующую команду для удаления:</span><span class="sxs-lookup"><span data-stu-id="67684-154">If you installed PowerShell with Homebrew, use the following command to uninstall:</span></span>

```sh
brew cask uninstall powershell
```

<span data-ttu-id="67684-155">Если вы установили PowerShell с помощью прямого скачивания, PowerShell нужно удалить вручную:</span><span class="sxs-lookup"><span data-stu-id="67684-155">If you installed PowerShell via direct download, PowerShell must be removed manually:</span></span>

```sh
sudo rm -rf /usr/local/bin/pwsh /usr/local/microsoft/powershell
```

<span data-ttu-id="67684-156">Чтобы удалить дополнительные пути PowerShell, ознакомьтесь с разделом [Пути](#paths) этой статьи, и удалите их с помощью команды `sudo rm`.</span><span class="sxs-lookup"><span data-stu-id="67684-156">To remove the additional PowerShell paths, refer to the [paths](#paths) section in this document and remove the paths using `sudo rm`.</span></span>

> [!NOTE]
> <span data-ttu-id="67684-157">Это не требуется в случае установки с помощью Homebrew.</span><span class="sxs-lookup"><span data-stu-id="67684-157">This is not necessary if you installed with Homebrew.</span></span>

## <a name="paths"></a><span data-ttu-id="67684-158">Пути</span><span class="sxs-lookup"><span data-stu-id="67684-158">Paths</span></span>

* <span data-ttu-id="67684-159">`$PSHOME` имеет значение `/usr/local/microsoft/powershell/6.2.0/`.</span><span class="sxs-lookup"><span data-stu-id="67684-159">`$PSHOME` is `/usr/local/microsoft/powershell/6.2.0/`</span></span>
* <span data-ttu-id="67684-160">Профили пользователей будут считаны из `~/.config/powershell/profile.ps1`.</span><span class="sxs-lookup"><span data-stu-id="67684-160">User profiles will be read from `~/.config/powershell/profile.ps1`</span></span>
* <span data-ttu-id="67684-161">Профили по умолчанию будут считаны из `$PSHOME/profile.ps1`.</span><span class="sxs-lookup"><span data-stu-id="67684-161">Default profiles will be read from `$PSHOME/profile.ps1`</span></span>
* <span data-ttu-id="67684-162">Модули пользователей будут считаны из `~/.local/share/powershell/Modules`.</span><span class="sxs-lookup"><span data-stu-id="67684-162">User modules will be read from `~/.local/share/powershell/Modules`</span></span>
* <span data-ttu-id="67684-163">Общие модули будут считаны из `/usr/local/share/powershell/Modules`.</span><span class="sxs-lookup"><span data-stu-id="67684-163">Shared modules will be read from `/usr/local/share/powershell/Modules`</span></span>
* <span data-ttu-id="67684-164">Модули по умолчанию будут считаны из `$PSHOME/Modules`.</span><span class="sxs-lookup"><span data-stu-id="67684-164">Default modules will be read from `$PSHOME/Modules`</span></span>
* <span data-ttu-id="67684-165">Журнал PSReadline будет записан в `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`.</span><span class="sxs-lookup"><span data-stu-id="67684-165">PSReadline history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="67684-166">Профили учитывают конфигурацию PowerShell для отдельных узлов.</span><span class="sxs-lookup"><span data-stu-id="67684-166">The profiles respect PowerShell's per-host configuration.</span></span>
<span data-ttu-id="67684-167">Профиль узла по умолчанию находится в `Microsoft.PowerShell_profile.ps1` в тех же расположениях.</span><span class="sxs-lookup"><span data-stu-id="67684-167">So the default host-specific profile exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="67684-168">PowerShell отвечает требованиям [спецификации каталога размещения файлов, связанных со средой настольной графической среды (X-сервера), стандартизированного XDG (X Desktop Group)][xdg-bds] в macOS.</span><span class="sxs-lookup"><span data-stu-id="67684-168">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on macOS.</span></span>

<span data-ttu-id="67684-169">Так как macOS является развитием BSD, необходимо использовать префикс `/usr/local` вместо `/opt`.</span><span class="sxs-lookup"><span data-stu-id="67684-169">Because macOS is a derivation of BSD, the prefix `/usr/local` is used instead of `/opt`.</span></span>
<span data-ttu-id="67684-170">Таким образом, `$PSHOME` имеет значение `/usr/local/microsoft/powershell/6.2.0/`, а символьная ссылка размещается в `/usr/local/bin/pwsh`.</span><span class="sxs-lookup"><span data-stu-id="67684-170">So, `$PSHOME` is `/usr/local/microsoft/powershell/6.2.0/`, and the symbolic link is placed at `/usr/local/bin/pwsh`.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="67684-171">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="67684-171">Additional Resources</span></span>

* <span data-ttu-id="67684-172">[Homebrew Web][brew]</span><span class="sxs-lookup"><span data-stu-id="67684-172">[Homebrew Web][brew]</span></span>
* <span data-ttu-id="67684-173">[Репозиторий Github Homebrew][GitHub]</span><span class="sxs-lookup"><span data-stu-id="67684-173">[Homebrew Github Repository][GitHub]</span></span>
* <span data-ttu-id="67684-174">[Homebrew-Cask][cask]</span><span class="sxs-lookup"><span data-stu-id="67684-174">[Homebrew-Cask][cask]</span></span>

[brew]: http://brew.sh/
[Cask]: https://github.com/Homebrew/homebrew-cask
[cask-versions]: https://github.com/Homebrew/homebrew-cask-versions
[GitHub]: https://github.com/Homebrew
[выпусков]: https://github.com/PowerShell/PowerShell/releases/latest
[releases]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
