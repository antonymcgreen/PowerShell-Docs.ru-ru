---
title: Установка PowerShell Core в macOS
description: Сведения об установке PowerShell Core в macOS
ms.date: 12/12/2018
ms.openlocfilehash: 7db8ca0cb6d13db8ce7f11b4a4b03b7d3f9b6feb
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62086465"
---
# <a name="installing-powershell-core-on-macos"></a><span data-ttu-id="88a2e-103">Установка PowerShell Core в macOS</span><span class="sxs-lookup"><span data-stu-id="88a2e-103">Installing PowerShell Core on macOS</span></span>

<span data-ttu-id="88a2e-104">PowerShell Core поддерживает macOS версии 10.12 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="88a2e-104">PowerShell Core supports macOS 10.12 and higher.</span></span>
<span data-ttu-id="88a2e-105">Все пакеты доступны на нашей странице [выпусков][] GitHub.</span><span class="sxs-lookup"><span data-stu-id="88a2e-105">All packages are available on our GitHub [releases][] page.</span></span>
<span data-ttu-id="88a2e-106">После установки пакета запустите `pwsh` из терминала.</span><span class="sxs-lookup"><span data-stu-id="88a2e-106">After the package is installed, run `pwsh` from a terminal.</span></span>

## <a name="about-brew"></a><span data-ttu-id="88a2e-107">Сведения о Brew</span><span class="sxs-lookup"><span data-stu-id="88a2e-107">About Brew</span></span>

<span data-ttu-id="88a2e-108">[Homebrew][brew] является предпочтительным диспетчером пакетов для macOS.</span><span class="sxs-lookup"><span data-stu-id="88a2e-108">[Homebrew][brew] is the preferred package manager for macOS.</span></span>
<span data-ttu-id="88a2e-109">Если команда `brew` не найдена, нужно установить Homebrew по [соответствующим инструкциям][brew].</span><span class="sxs-lookup"><span data-stu-id="88a2e-109">If the `brew` command is not found, you need to install Homebrew following [their instructions][brew].</span></span>

## <a name="installation-of-latest-stable-release-via-homebrew-on-macos-1012-or-higher"></a><span data-ttu-id="88a2e-110">Установка последнего стабильного выпуска с помощью Homebrew в macOS 10.12 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="88a2e-110">Installation of latest stable release via Homebrew on macOS 10.12 or higher</span></span>

<span data-ttu-id="88a2e-111">См. дополнительные сведения о [Brew](#about-brew).</span><span class="sxs-lookup"><span data-stu-id="88a2e-111">See [About Brew](#about-brew) for information about Brew.</span></span>

<span data-ttu-id="88a2e-112">Теперь можно установить PowerShell:</span><span class="sxs-lookup"><span data-stu-id="88a2e-112">Now, you can install PowerShell:</span></span>

```sh
brew cask install powershell
```

<span data-ttu-id="88a2e-113">И наконец, убедитесь, что установка прошла без ошибок.</span><span class="sxs-lookup"><span data-stu-id="88a2e-113">Finally, verify that your install is working properly:</span></span>

```sh
pwsh
```

<span data-ttu-id="88a2e-114">После выпуска новых версий PowerShell обновите формулы Homebrew и PowerShell:</span><span class="sxs-lookup"><span data-stu-id="88a2e-114">When new versions of PowerShell are released, update Homebrew's formulae and upgrade PowerShell:</span></span>

```sh
brew update
brew cask upgrade powershell
```

> [!NOTE]
> <span data-ttu-id="88a2e-115">Приведенные выше команды можно вызвать из узла PowerShell (pwsh), но затем потребуется выйти из оболочки PowerShell и перезапустить ее, чтобы завершить обновление и обновить значения в таблице `$PSVersionTable`.</span><span class="sxs-lookup"><span data-stu-id="88a2e-115">The commands above can be called from within a PowerShell (pwsh) host, but then the PowerShell shell must be exited and restarted to complete the upgrade and refresh the values shown in `$PSVersionTable`.</span></span>

[brew]: http://brew.sh/

## <a name="installation-of-latest-preview-release-via-homebrew-on-macos-1012-or-higher"></a><span data-ttu-id="88a2e-116">Установка последнего предварительного выпуска с помощью Homebrew в macOS 10.12 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="88a2e-116">Installation of latest preview release via Homebrew on macOS 10.12 or higher</span></span>

<span data-ttu-id="88a2e-117">См. дополнительные сведения о [Brew](#about-brew).</span><span class="sxs-lookup"><span data-stu-id="88a2e-117">See [About Brew](#about-brew) for information about Brew.</span></span>

<span data-ttu-id="88a2e-118">После установки Homebrew можно установить PowerShell.</span><span class="sxs-lookup"><span data-stu-id="88a2e-118">After you've installed Homebrew, you can install PowerShell.</span></span>
<span data-ttu-id="88a2e-119">Сначала установите пакет [Cask-Versions][cask-versions], который позволит устанавливать альтернативные версии Cask-пакетов.</span><span class="sxs-lookup"><span data-stu-id="88a2e-119">First, install the [Cask-Versions][cask-versions] package that lets you install alternative versions of cask packages:</span></span>

```sh
brew tap homebrew/cask-versions
```

<span data-ttu-id="88a2e-120">Теперь можно установить PowerShell:</span><span class="sxs-lookup"><span data-stu-id="88a2e-120">Now, you can install PowerShell:</span></span>

```sh
brew cask install powershell-preview
```

<span data-ttu-id="88a2e-121">И наконец, убедитесь, что установка прошла без ошибок.</span><span class="sxs-lookup"><span data-stu-id="88a2e-121">Finally, verify that your install is working properly:</span></span>

```sh
pwsh-preview
```

<span data-ttu-id="88a2e-122">После выпуска новых версий PowerShell обновите формулы Homebrew и PowerShell:</span><span class="sxs-lookup"><span data-stu-id="88a2e-122">When new versions of PowerShell are released, update Homebrew's formulae and upgrade PowerShell:</span></span>

```sh
brew update
brew cask upgrade powershell-preview
```

> [!NOTE]
> <span data-ttu-id="88a2e-123">Команду, указанную выше, можно вызвать на узле PowerShell (pwsh), но для этого необходимо завершить его обновление. Что в свою очередь будет сделано, когда вы выйдете из PowerShell и перезапустите его.</span><span class="sxs-lookup"><span data-stu-id="88a2e-123">The commands above can be called from within a PowerShell (pwsh) host, but then the PowerShell shell must be exited and restarted to complete the upgrade.</span></span>
> <span data-ttu-id="88a2e-124">Обновите значения, которые отображаются в `$PSVersionTable`.</span><span class="sxs-lookup"><span data-stu-id="88a2e-124">and refresh the values shown in `$PSVersionTable`.</span></span>

## <a name="installation-via-direct-download"></a><span data-ttu-id="88a2e-125">Установка с помощью прямого скачивания</span><span class="sxs-lookup"><span data-stu-id="88a2e-125">Installation via Direct Download</span></span>

<span data-ttu-id="88a2e-126">Скачайте пакет PKG `powershell-6.2.0-osx-x64.pkg`</span><span class="sxs-lookup"><span data-stu-id="88a2e-126">Download the PKG package `powershell-6.2.0-osx-x64.pkg`</span></span>
<span data-ttu-id="88a2e-127">со страницы [выпусков][] на компьютер с macOS.</span><span class="sxs-lookup"><span data-stu-id="88a2e-127">from the [releases][] page onto your macOS machine.</span></span>

<span data-ttu-id="88a2e-128">Дважды щелкните файл и следуйте инструкциям на экране либо установите его из командной строки:</span><span class="sxs-lookup"><span data-stu-id="88a2e-128">You can double-click the file and follow the prompts, or install it from the terminal:</span></span>

```sh
sudo installer -pkg powershell-6.2.0-osx-x64.pkg -target /
```

<span data-ttu-id="88a2e-129">Установите [OpenSSL](#install-openssl).</span><span class="sxs-lookup"><span data-stu-id="88a2e-129">Install [OpenSSL](#install-openssl).</span></span> <span data-ttu-id="88a2e-130">OpenSSL требуется для удаленного взаимодействия PowerShell и операций CIM.</span><span class="sxs-lookup"><span data-stu-id="88a2e-130">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>

## <a name="binary-archives"></a><span data-ttu-id="88a2e-131">Архивы двоичных файлов</span><span class="sxs-lookup"><span data-stu-id="88a2e-131">Binary Archives</span></span>

<span data-ttu-id="88a2e-132">Для поддержки расширенных сценариев развертывания на платформе macOS доступны архивы `tar.gz` двоичных файлов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="88a2e-132">PowerShell binary `tar.gz` archives are provided for the macOS platform to enable advanced deployment scenarios.</span></span>

### <a name="installing-binary-archives-on-macos"></a><span data-ttu-id="88a2e-133">Установка архивов двоичных файлов в macOS</span><span class="sxs-lookup"><span data-stu-id="88a2e-133">Installing binary archives on macOS</span></span>

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

<span data-ttu-id="88a2e-134">Установите [OpenSSL](#install-openssl).</span><span class="sxs-lookup"><span data-stu-id="88a2e-134">Install [OpenSSL](#install-openssl).</span></span> <span data-ttu-id="88a2e-135">OpenSSL требуется для удаленного взаимодействия PowerShell и операций CIM.</span><span class="sxs-lookup"><span data-stu-id="88a2e-135">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>

## <a name="installing-dependencies"></a><span data-ttu-id="88a2e-136">Установка зависимостей</span><span class="sxs-lookup"><span data-stu-id="88a2e-136">Installing dependencies</span></span>

### <a name="install-xcode-command-line-tools"></a><span data-ttu-id="88a2e-137">Установка средств командной строки XCode</span><span class="sxs-lookup"><span data-stu-id="88a2e-137">Install XCode command-line tools</span></span>

```sh
xcode-select --install
```

### <a name="install-openssl"></a><span data-ttu-id="88a2e-138">Установка OpenSSL</span><span class="sxs-lookup"><span data-stu-id="88a2e-138">Install OpenSSL</span></span>

<span data-ttu-id="88a2e-139">OpenSSL требуется для удаленного взаимодействия PowerShell и операций CIM.</span><span class="sxs-lookup"><span data-stu-id="88a2e-139">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span> <span data-ttu-id="88a2e-140">Установка возможна с помощью MacPorts или Brew.</span><span class="sxs-lookup"><span data-stu-id="88a2e-140">You can install via MacPorts or Brew.</span></span>

#### <a name="install-openssl-via-brew"></a><span data-ttu-id="88a2e-141">Установка OpenSSL с помощью Brew</span><span class="sxs-lookup"><span data-stu-id="88a2e-141">Install OpenSSL via Brew</span></span>

<span data-ttu-id="88a2e-142">См. дополнительные сведения о [Brew](#about-brew).</span><span class="sxs-lookup"><span data-stu-id="88a2e-142">See [About Brew](#about-brew) for information about Brew.</span></span>

<span data-ttu-id="88a2e-143">Запустите `brew install openssl`, чтобы установить OpenSSL.</span><span class="sxs-lookup"><span data-stu-id="88a2e-143">To install OpenSSL, run `brew install openssl`.</span></span>

#### <a name="install-openssl-via-macports"></a><span data-ttu-id="88a2e-144">Установка OpenSSL с помощью MacPorts</span><span class="sxs-lookup"><span data-stu-id="88a2e-144">Install OpenSSL via MacPorts</span></span>

1. <span data-ttu-id="88a2e-145">Установите [средство командной строки XCode](#install-xcode-command-line-tools).</span><span class="sxs-lookup"><span data-stu-id="88a2e-145">Install the [XCode command line tools](#install-xcode-command-line-tools).</span></span>
1. <span data-ttu-id="88a2e-146">Установите MacPorts.</span><span class="sxs-lookup"><span data-stu-id="88a2e-146">Install MacPorts.</span></span>
   <span data-ttu-id="88a2e-147">Инструкции см. в [руководстве по установке](https://guide.macports.org/chunked/installing.macports.html).</span><span class="sxs-lookup"><span data-stu-id="88a2e-147">If you need instructions, refer to the [installation guide](https://guide.macports.org/chunked/installing.macports.html).</span></span>
1. <span data-ttu-id="88a2e-148">Обновите MacPorts, выполнив команду `sudo port selfupdate`.</span><span class="sxs-lookup"><span data-stu-id="88a2e-148">Update MacPorts by running `sudo port selfupdate`.</span></span>
1. <span data-ttu-id="88a2e-149">Обновите пакеты MacPorts, выполнив команду `sudo port upgrade outdated`.</span><span class="sxs-lookup"><span data-stu-id="88a2e-149">Upgrade MacPorts packages by running `sudo port upgrade outdated`.</span></span>
1. <span data-ttu-id="88a2e-150">Установите OpenSSL, запустив `sudo port install openssl`.</span><span class="sxs-lookup"><span data-stu-id="88a2e-150">Install OpenSSL by running `sudo port install openssl`.</span></span>
1. <span data-ttu-id="88a2e-151">Укажите ссылки на библиотеки, чтобы сделать их доступными для PowerShell:</span><span class="sxs-lookup"><span data-stu-id="88a2e-151">Link the libraries to make them available to PowerShell:</span></span>

```sh
sudo mkdir -p /usr/local/opt/openssl
sudo ln -s /opt/local/lib /usr/local/opt/openssl/lib
```

## <a name="uninstalling-powershell-core"></a><span data-ttu-id="88a2e-152">Удаление PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="88a2e-152">Uninstalling PowerShell Core</span></span>

<span data-ttu-id="88a2e-153">Если вы установили PowerShell с помощью Homebrew, используйте следующую команду для удаления:</span><span class="sxs-lookup"><span data-stu-id="88a2e-153">If you installed PowerShell with Homebrew, use the following command to uninstall:</span></span>

```sh
brew cask uninstall powershell
```

<span data-ttu-id="88a2e-154">Если вы установили PowerShell с помощью прямого скачивания, PowerShell нужно удалить вручную:</span><span class="sxs-lookup"><span data-stu-id="88a2e-154">If you installed PowerShell via direct download, PowerShell must be removed manually:</span></span>

```sh
sudo rm -rf /usr/local/bin/pwsh /usr/local/microsoft/powershell
```

<span data-ttu-id="88a2e-155">Чтобы удалить дополнительные пути PowerShell, ознакомьтесь с разделом [Пути](#paths) этой статьи, и удалите их с помощью команды `sudo rm`.</span><span class="sxs-lookup"><span data-stu-id="88a2e-155">To remove the additional PowerShell paths, refer to the [paths](#paths) section in this document and remove the paths using `sudo rm`.</span></span>

> [!NOTE]
> <span data-ttu-id="88a2e-156">Это не требуется в случае установки с помощью Homebrew.</span><span class="sxs-lookup"><span data-stu-id="88a2e-156">This is not necessary if you installed with Homebrew.</span></span>

## <a name="paths"></a><span data-ttu-id="88a2e-157">Пути</span><span class="sxs-lookup"><span data-stu-id="88a2e-157">Paths</span></span>

* <span data-ttu-id="88a2e-158">`$PSHOME` имеет значение `/usr/local/microsoft/powershell/6.2.0/`.</span><span class="sxs-lookup"><span data-stu-id="88a2e-158">`$PSHOME` is `/usr/local/microsoft/powershell/6.2.0/`</span></span>
* <span data-ttu-id="88a2e-159">Профили пользователей будут считаны из `~/.config/powershell/profile.ps1`.</span><span class="sxs-lookup"><span data-stu-id="88a2e-159">User profiles will be read from `~/.config/powershell/profile.ps1`</span></span>
* <span data-ttu-id="88a2e-160">Профили по умолчанию будут считаны из `$PSHOME/profile.ps1`.</span><span class="sxs-lookup"><span data-stu-id="88a2e-160">Default profiles will be read from `$PSHOME/profile.ps1`</span></span>
* <span data-ttu-id="88a2e-161">Модули пользователей будут считаны из `~/.local/share/powershell/Modules`.</span><span class="sxs-lookup"><span data-stu-id="88a2e-161">User modules will be read from `~/.local/share/powershell/Modules`</span></span>
* <span data-ttu-id="88a2e-162">Общие модули будут считаны из `/usr/local/share/powershell/Modules`.</span><span class="sxs-lookup"><span data-stu-id="88a2e-162">Shared modules will be read from `/usr/local/share/powershell/Modules`</span></span>
* <span data-ttu-id="88a2e-163">Модули по умолчанию будут считаны из `$PSHOME/Modules`.</span><span class="sxs-lookup"><span data-stu-id="88a2e-163">Default modules will be read from `$PSHOME/Modules`</span></span>
* <span data-ttu-id="88a2e-164">Журнал PSReadline будет записан в `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`.</span><span class="sxs-lookup"><span data-stu-id="88a2e-164">PSReadline history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="88a2e-165">Профили учитывают конфигурацию PowerShell для отдельных узлов.</span><span class="sxs-lookup"><span data-stu-id="88a2e-165">The profiles respect PowerShell's per-host configuration.</span></span>
<span data-ttu-id="88a2e-166">Профиль узла по умолчанию находится в `Microsoft.PowerShell_profile.ps1` в тех же расположениях.</span><span class="sxs-lookup"><span data-stu-id="88a2e-166">So the default host-specific profile exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="88a2e-167">PowerShell отвечает требованиям [спецификации каталога размещения файлов, связанных со средой настольной графической среды (X-сервера), стандартизированного XDG (X Desktop Group)][xdg-bds] в macOS.</span><span class="sxs-lookup"><span data-stu-id="88a2e-167">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on macOS.</span></span>

<span data-ttu-id="88a2e-168">Так как macOS является развитием BSD, необходимо использовать префикс `/usr/local` вместо `/opt`.</span><span class="sxs-lookup"><span data-stu-id="88a2e-168">Because macOS is a derivation of BSD, the prefix `/usr/local` is used instead of `/opt`.</span></span>
<span data-ttu-id="88a2e-169">Таким образом, `$PSHOME` имеет значение `/usr/local/microsoft/powershell/6.2.0/`, а символьная ссылка размещается в `/usr/local/bin/pwsh`.</span><span class="sxs-lookup"><span data-stu-id="88a2e-169">So, `$PSHOME` is `/usr/local/microsoft/powershell/6.2.0/`, and the symbolic link is placed at `/usr/local/bin/pwsh`.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="88a2e-170">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="88a2e-170">Additional Resources</span></span>

* <span data-ttu-id="88a2e-171">[Homebrew Web][brew]</span><span class="sxs-lookup"><span data-stu-id="88a2e-171">[Homebrew Web][brew]</span></span>
* <span data-ttu-id="88a2e-172">[Репозиторий Github Homebrew][GitHub]</span><span class="sxs-lookup"><span data-stu-id="88a2e-172">[Homebrew Github Repository][GitHub]</span></span>
* <span data-ttu-id="88a2e-173">[Homebrew-Cask][cask]</span><span class="sxs-lookup"><span data-stu-id="88a2e-173">[Homebrew-Cask][cask]</span></span>

[brew]: http://brew.sh/
[Cask]: https://github.com/Homebrew/homebrew-cask
[cask-versions]: https://github.com/Homebrew/homebrew-cask-versions
[GitHub]: https://github.com/Homebrew
[выпусков]: https://github.com/PowerShell/PowerShell/releases/latest
[releases]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
