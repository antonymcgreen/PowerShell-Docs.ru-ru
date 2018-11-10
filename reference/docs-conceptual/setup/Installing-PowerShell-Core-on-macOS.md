---
title: Установка PowerShell Core в macOS
description: Сведения об установке PowerShell Core в macOS
ms.date: 11/02/2018
ms.openlocfilehash: 162e841bf71d708e9db84ea1bb2dbef13924783b
ms.sourcegitcommit: f4247d3f91d06ec392c4cd66921ce7d0456a2bd9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2018
ms.locfileid: "50998509"
---
# <a name="installing-powershell-core-on-macos"></a><span data-ttu-id="b440a-103">Установка PowerShell Core в macOS</span><span class="sxs-lookup"><span data-stu-id="b440a-103">Installing PowerShell Core on macOS</span></span>

<span data-ttu-id="b440a-104">PowerShell Core поддерживает macOS версии 10.12 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="b440a-104">PowerShell Core supports macOS 10.12 and higher.</span></span>
<span data-ttu-id="b440a-105">Все пакеты доступны на нашей странице [выпусков][] GitHub.</span><span class="sxs-lookup"><span data-stu-id="b440a-105">All packages are available on our GitHub [releases][] page.</span></span>
<span data-ttu-id="b440a-106">После установки пакета запустите `pwsh` из терминала.</span><span class="sxs-lookup"><span data-stu-id="b440a-106">Once the package is installed, run `pwsh` from a terminal.</span></span>

## <a name="about-brew"></a><span data-ttu-id="b440a-107">Сведения о Brew</span><span class="sxs-lookup"><span data-stu-id="b440a-107">About Brew</span></span>

<span data-ttu-id="b440a-108">[Homebrew][brew] является предпочтительным диспетчером пакетов для macOS.</span><span class="sxs-lookup"><span data-stu-id="b440a-108">[Homebrew][brew] is the preferred package manager for macOS.</span></span>
<span data-ttu-id="b440a-109">Если команда `brew` не найдена, нужно установить Homebrew по [соответствующим инструкциям][brew].</span><span class="sxs-lookup"><span data-stu-id="b440a-109">If the `brew` command is not found, you need to install Homebrew following [their instructions][brew].</span></span>

## <a name="installation-of-latest-stable-release-via-homebrew-on-macos-1012-or-higher"></a><span data-ttu-id="b440a-110">Установка последнего стабильного выпуска с помощью Homebrew в macOS 10.12 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="b440a-110">Installation of latest stable release via Homebrew on macOS 10.12 or higher</span></span>

<span data-ttu-id="b440a-111">См. дополнительные сведения о [Brew](#about-brew).</span><span class="sxs-lookup"><span data-stu-id="b440a-111">See [About Brew](#about-brew) for information about Brew.</span></span>

<span data-ttu-id="b440a-112">Теперь можно установить PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b440a-112">Now, you can install PowerShell:</span></span>

```sh
brew cask install powershell
```

<span data-ttu-id="b440a-113">И наконец, убедитесь, что установка прошла без ошибок.</span><span class="sxs-lookup"><span data-stu-id="b440a-113">Finally, verify that your install is working properly:</span></span>

```sh
pwsh
```

<span data-ttu-id="b440a-114">После выпуска новых версий PowerShell просто обновите формулы Homebrew и PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b440a-114">When new versions of PowerShell are released, simply update Homebrew's formulae and upgrade PowerShell:</span></span>

```sh
brew update
brew cask upgrade powershell
```

> [!NOTE]
> <span data-ttu-id="b440a-115">Приведенные выше команды можно вызвать с узла PowerShell (pwsh), но затем потребуется выйти из оболочки PowerShell и перезапустить ее, чтобы завершить обновление и обновить значения в таблице $PSVersionTable.</span><span class="sxs-lookup"><span data-stu-id="b440a-115">The commands above can be called from within a PowerShell (pwsh) host, but then the PowerShell shell must be exited and restarted to complete the upgrade and refresh the values shown in $PSVersionTable.</span></span>

[brew]: http://brew.sh/

## <a name="installation-of-latest-preview-release-via-homebrew-on-macos-1012-or-higher"></a><span data-ttu-id="b440a-116">Установка последнего предварительного выпуска с помощью Homebrew в macOS 10.12 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="b440a-116">Installation of latest preview release via Homebrew on macOS 10.12 or higher</span></span>

<span data-ttu-id="b440a-117">См. дополнительные сведения о [Brew](#about-brew).</span><span class="sxs-lookup"><span data-stu-id="b440a-117">See [About Brew](#about-brew) for information about Brew.</span></span>

<span data-ttu-id="b440a-118">После установки Homebrew установка PowerShell не вызывает проблем.</span><span class="sxs-lookup"><span data-stu-id="b440a-118">Once you've installed Homebrew, installing PowerShell is easy.</span></span>
<span data-ttu-id="b440a-119">Сначала установите [cask-версии][cask-versions], что позволит устанавливать альтернативные версии cask-пакетов.</span><span class="sxs-lookup"><span data-stu-id="b440a-119">First, install [Cask-Versions][cask-versions] which lets you install alternative versions of cask packages:</span></span>

```sh
brew tap homebrew/cask-versions
```

<span data-ttu-id="b440a-120">Теперь можно установить PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b440a-120">Now, you can install PowerShell:</span></span>

```sh
brew cask install powershell-preview
```

<span data-ttu-id="b440a-121">И наконец, убедитесь, что установка прошла без ошибок.</span><span class="sxs-lookup"><span data-stu-id="b440a-121">Finally, verify that your install is working properly:</span></span>

```sh
pwsh-preview
```

<span data-ttu-id="b440a-122">После выпуска новых версий PowerShell просто обновите формулы Homebrew и PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b440a-122">When new versions of PowerShell are released, simply update Homebrew's formulae and upgrade PowerShell:</span></span>

```sh
brew update
brew cask upgrade powershell-preview
```

> [!NOTE]
> <span data-ttu-id="b440a-123">Команду, указанную выше, можно вызвать на узле PowerShell (pwsh), но для этого необходимо завершить его обновление. Что в свою очередь будет сделано, когда вы выйдете из PowerShell и перезапустите его.</span><span class="sxs-lookup"><span data-stu-id="b440a-123">The commands above can be called from within a PowerShell (pwsh) host, but then the PowerShell shell must be exited and restarted to complete the upgrade.</span></span>
> <span data-ttu-id="b440a-124">Обновите значения, которые отображаются в $PSVersionTable.</span><span class="sxs-lookup"><span data-stu-id="b440a-124">and refresh the values shown in $PSVersionTable.</span></span>

## <a name="installation-via-direct-download"></a><span data-ttu-id="b440a-125">Установка с помощью прямого скачивания</span><span class="sxs-lookup"><span data-stu-id="b440a-125">Installation via Direct Download</span></span>

<span data-ttu-id="b440a-126">Скачайте пакет PKG `powershell-6.1.0-osx-x64.pkg`</span><span class="sxs-lookup"><span data-stu-id="b440a-126">Download the PKG package `powershell-6.1.0-osx-x64.pkg`</span></span>
<span data-ttu-id="b440a-127">со страницы [выпусков][] на компьютер с macOS.</span><span class="sxs-lookup"><span data-stu-id="b440a-127">from the [releases][] page onto your macOS machine.</span></span>

<span data-ttu-id="b440a-128">Дважды щелкните файл и следуйте инструкциям на экране либо установите его из командной строки:</span><span class="sxs-lookup"><span data-stu-id="b440a-128">You can double-click the file and follow the prompts, or install it from the terminal:</span></span>

```sh
sudo installer -pkg powershell-6.1.0-osx-x64.pkg -target /
```

<span data-ttu-id="b440a-129">Установите [OpenSSL](#install-openssl), так как это требуется для удаленного взаимодействия PowerShell и операций CIM.</span><span class="sxs-lookup"><span data-stu-id="b440a-129">Install [OpenSSL](#install-openssl) as this is needed for PowerShell remoting and CIM operations.</span></span>

## <a name="binary-archives"></a><span data-ttu-id="b440a-130">Архивы двоичных файлов</span><span class="sxs-lookup"><span data-stu-id="b440a-130">Binary Archives</span></span>

<span data-ttu-id="b440a-131">Для поддержки расширенных сценариев развертывания на платформе macOS доступны архивы `tar.gz` двоичных файлов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b440a-131">PowerShell binary `tar.gz` archives are provided for the macOS platform to enable advanced deployment scenarios.</span></span>

### <a name="installing-binary-archives-on-macos"></a><span data-ttu-id="b440a-132">Установка архивов двоичных файлов в macOS</span><span class="sxs-lookup"><span data-stu-id="b440a-132">Installing binary archives on macOS</span></span>

```sh
# Download the powershell '.tar.gz' archive
curl -L -o /tmp/powershell.tar.gz https://github.com/PowerShell/PowerShell/releases/download/v6.1.0/powershell-6.1.0-osx-x64.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /usr/local/microsoft/powershell/6.1.0

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /usr/local/microsoft/powershell/6.1.0

# Set execute permissions
sudo chmod +x /usr/local/microsoft/powershell/6.1.0/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /usr/local/microsoft/powershell/6.1.0/pwsh /usr/local/bin/pwsh
```

<span data-ttu-id="b440a-133">Установите [OpenSSL](#install-openssl), так как это требуется для удаленного взаимодействия PowerShell и операций CIM.</span><span class="sxs-lookup"><span data-stu-id="b440a-133">Install [OpenSSL](#install-openssl) as this is needed for PowerShell remoting and CIM operations.</span></span>

## <a name="installing-dependencies"></a><span data-ttu-id="b440a-134">Установка зависимостей</span><span class="sxs-lookup"><span data-stu-id="b440a-134">Installing dependencies</span></span>

### <a name="install-xcode-command-line-tools"></a><span data-ttu-id="b440a-135">Установка средств командной строки XCode</span><span class="sxs-lookup"><span data-stu-id="b440a-135">Install XCode command line tools</span></span>

```shell
xcode-select -install
```

### <a name="install-openssl"></a><span data-ttu-id="b440a-136">Установка OpenSSL</span><span class="sxs-lookup"><span data-stu-id="b440a-136">Install OpenSSL</span></span>

<span data-ttu-id="b440a-137">OpenSSL требуется для удаленного взаимодействия PowerShell и операций CIM.</span><span class="sxs-lookup"><span data-stu-id="b440a-137">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>  <span data-ttu-id="b440a-138">Установка возможна с помощью MacPorts или Brew.</span><span class="sxs-lookup"><span data-stu-id="b440a-138">You can install via MacPorts or Brew.</span></span>

#### <a name="install-openssl-via-brew"></a><span data-ttu-id="b440a-139">Установка OpenSSL с помощью Brew</span><span class="sxs-lookup"><span data-stu-id="b440a-139">Install OpenSSL via Brew</span></span>

<span data-ttu-id="b440a-140">См. дополнительные сведения о [Brew](#about-brew).</span><span class="sxs-lookup"><span data-stu-id="b440a-140">See [About Brew](#about-brew) for information about Brew.</span></span>

<span data-ttu-id="b440a-141">Запустите `brew install openssl`, чтобы установить OpenSSL.</span><span class="sxs-lookup"><span data-stu-id="b440a-141">Run `brew install openssl` to install OpenSSL.</span></span>

#### <a name="install-openssl-via-macports"></a><span data-ttu-id="b440a-142">Установка OpenSSL с помощью MacPorts</span><span class="sxs-lookup"><span data-stu-id="b440a-142">Install OpenSSL via MacPorts</span></span>

1. <span data-ttu-id="b440a-143">Установите [средство командной строки XCode](#install-xcode-command-line-tools).</span><span class="sxs-lookup"><span data-stu-id="b440a-143">Instal the [XCode command line tools](#install-xcode-command-line-tools)</span></span>
1. <span data-ttu-id="b440a-144">Установите MacPorts.</span><span class="sxs-lookup"><span data-stu-id="b440a-144">Install MacPorts.</span></span>
   <span data-ttu-id="b440a-145">Инструкции см. в [руководстве по установке](https://guide.macports.org/chunked/installing.macports.html).</span><span class="sxs-lookup"><span data-stu-id="b440a-145">See the [installation guide](https://guide.macports.org/chunked/installing.macports.html) if you need instructions.</span></span>
1. <span data-ttu-id="b440a-146">Обновите MacPorts, запустив `sudo port selfupdate`.</span><span class="sxs-lookup"><span data-stu-id="b440a-146">Update MacPorts by running `sudo port selfupdate`</span></span>
1. <span data-ttu-id="b440a-147">Обновите пакеты MacPorts, запустив `sudo port upgrade outdated`.</span><span class="sxs-lookup"><span data-stu-id="b440a-147">Upgrade MacPorts packages by running `sudo port upgrade outdated`</span></span>
1. <span data-ttu-id="b440a-148">Установите OpenSSL, запустив `sudo port instal openssl`.</span><span class="sxs-lookup"><span data-stu-id="b440a-148">Install OpenSSL by running by running `sudo port instal openssl`</span></span>
1. <span data-ttu-id="b440a-149">Создайте ссылку на библиотеки, чтобы их можно было использовать в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b440a-149">Link the libraries so that PowerShell can use it.</span></span>

```shell
sudo mkdir -p /usr/local/opt/openssl
sudo ln -s /opt/local/lib /usr/local/opt/openssl/lib
```

## <a name="uninstalling-powershell-core"></a><span data-ttu-id="b440a-150">Удаление PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="b440a-150">Uninstalling PowerShell Core</span></span>

<span data-ttu-id="b440a-151">Если вы установили PowerShell с помощью Homebrew, удаление осуществляется очень просто:</span><span class="sxs-lookup"><span data-stu-id="b440a-151">If you installed PowerShell with Homebrew, uninstallation is easy:</span></span>

```sh
brew cask uninstall powershell
```

<span data-ttu-id="b440a-152">Если вы установили PowerShell с помощью прямого скачивания, PowerShell нужно удалить вручную:</span><span class="sxs-lookup"><span data-stu-id="b440a-152">If you installed PowerShell via direct download, PowerShell must be removed manually:</span></span>

```sh
sudo rm -rf /usr/local/bin/pwsh /usr/local/microsoft/powershell
```

<span data-ttu-id="b440a-153">Чтобы удалить дополнительные пути PowerShell, ознакомьтесь с разделом [пути](#paths) этой статьи, и удалите необходимые пути с помощью команды `sudo rm`.</span><span class="sxs-lookup"><span data-stu-id="b440a-153">To remove the additional PowerShell paths, please see the [paths](#paths) section in this document and remove the desired the paths using `sudo rm`.</span></span>

> [!NOTE]
> <span data-ttu-id="b440a-154">Это не требуется в случае установки с помощью Homebrew.</span><span class="sxs-lookup"><span data-stu-id="b440a-154">This is not necessary if you installed with Homebrew.</span></span>

## <a name="paths"></a><span data-ttu-id="b440a-155">Пути</span><span class="sxs-lookup"><span data-stu-id="b440a-155">Paths</span></span>

* <span data-ttu-id="b440a-156">`$PSHOME` имеет значение `/usr/local/microsoft/powershell/6.1.0/`.</span><span class="sxs-lookup"><span data-stu-id="b440a-156">`$PSHOME` is `/usr/local/microsoft/powershell/6.1.0/`</span></span>
* <span data-ttu-id="b440a-157">Профили пользователей будут считаны из `~/.config/powershell/profile.ps1`.</span><span class="sxs-lookup"><span data-stu-id="b440a-157">User profiles will be read from `~/.config/powershell/profile.ps1`</span></span>
* <span data-ttu-id="b440a-158">Профили по умолчанию будут считаны из `$PSHOME/profile.ps1`.</span><span class="sxs-lookup"><span data-stu-id="b440a-158">Default profiles will be read from `$PSHOME/profile.ps1`</span></span>
* <span data-ttu-id="b440a-159">Модули пользователей будут считаны из `~/.local/share/powershell/Modules`.</span><span class="sxs-lookup"><span data-stu-id="b440a-159">User modules will be read from `~/.local/share/powershell/Modules`</span></span>
* <span data-ttu-id="b440a-160">Общие модули будут считаны из `/usr/local/share/powershell/Modules`.</span><span class="sxs-lookup"><span data-stu-id="b440a-160">Shared modules will be read from `/usr/local/share/powershell/Modules`</span></span>
* <span data-ttu-id="b440a-161">Модули по умолчанию будут считаны из `$PSHOME/Modules`.</span><span class="sxs-lookup"><span data-stu-id="b440a-161">Default modules will be read from `$PSHOME/Modules`</span></span>
* <span data-ttu-id="b440a-162">Журнал PSReadline будет записан в `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`.</span><span class="sxs-lookup"><span data-stu-id="b440a-162">PSReadline history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="b440a-163">Профили учитывают конфигурацию PowerShell для отдельных узлов.</span><span class="sxs-lookup"><span data-stu-id="b440a-163">The profiles respect PowerShell's per-host configuration.</span></span>
<span data-ttu-id="b440a-164">Поэтому профили конкретных узлов по умолчанию находятся в `Microsoft.PowerShell_profile.ps1` в тех же расположениях.</span><span class="sxs-lookup"><span data-stu-id="b440a-164">So the default host-specific profiles exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="b440a-165">PowerShell отвечает требованиям [спецификации каталога размещения файлов, связанных со средой настольной графической среды (X-сервера), стандартизированного XDG (X Desktop Group)][xdg-bds] в macOS.</span><span class="sxs-lookup"><span data-stu-id="b440a-165">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on macOS.</span></span>

<span data-ttu-id="b440a-166">Так как macOS является развитием BSD, необходимо использовать префикс `/usr/local` вместо `/opt`.</span><span class="sxs-lookup"><span data-stu-id="b440a-166">Because macOS is a derivation of BSD, the prefix `/usr/local` is used instead of `/opt`.</span></span>
<span data-ttu-id="b440a-167">Таким образом, `$PSHOME` имеет значение `/usr/local/microsoft/powershell/6.1.0/`, а символьная ссылка размещается в `/usr/local/bin/pwsh`.</span><span class="sxs-lookup"><span data-stu-id="b440a-167">Thus, `$PSHOME` is `/usr/local/microsoft/powershell/6.1.0/`, and the symbolic link is placed at `/usr/local/bin/pwsh`.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b440a-168">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="b440a-168">Additional Resources</span></span>

* <span data-ttu-id="b440a-169">[Homebrew Web][brew]</span><span class="sxs-lookup"><span data-stu-id="b440a-169">[Homebrew Web][brew]</span></span>
* <span data-ttu-id="b440a-170">[Репозиторий Github Homebrew][GitHub]</span><span class="sxs-lookup"><span data-stu-id="b440a-170">[Homebrew Github Repository][GitHub]</span></span>
* <span data-ttu-id="b440a-171">[Homebrew-Cask][cask]</span><span class="sxs-lookup"><span data-stu-id="b440a-171">[Homebrew-Cask][cask]</span></span>

[brew]: http://brew.sh/
[Cask]: https://github.com/Homebrew/homebrew-cask
[cask-versions]: https://github.com/Homebrew/homebrew-cask-versions
[GitHub]: https://github.com/Homebrew
[выпусков]: https://github.com/PowerShell/PowerShell/releases/latest
[releases]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
