---
title: Установка PowerShell в macOS
description: Сведения об установке PowerShell в macOS
ms.date: 05/21/2020
ms.openlocfilehash: 32b3ebf3eb4017af41fc1a062f2f0a2e08629a58
ms.sourcegitcommit: fd6a33b9fac973b3554fecfea7f51475e650a606
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83791477"
---
# <a name="installing-powershell-on-macos"></a><span data-ttu-id="4a62b-103">Установка PowerShell в macOS</span><span class="sxs-lookup"><span data-stu-id="4a62b-103">Installing PowerShell on macOS</span></span>

<span data-ttu-id="4a62b-104">PowerShell поддерживает macOS версии 10.12 и более поздних.</span><span class="sxs-lookup"><span data-stu-id="4a62b-104">PowerShell supports macOS 10.12 and higher.</span></span>
<span data-ttu-id="4a62b-105">Все пакеты доступны на нашей странице [выпусков][] GitHub.</span><span class="sxs-lookup"><span data-stu-id="4a62b-105">All packages are available on our GitHub [releases][] page.</span></span>
<span data-ttu-id="4a62b-106">После установки пакета запустите `pwsh` из терминала.</span><span class="sxs-lookup"><span data-stu-id="4a62b-106">After the package is installed, run `pwsh` from a terminal.</span></span>

> [!NOTE]
> <span data-ttu-id="4a62b-107">PowerShell 7 является обновлением на месте, при установке которого PowerShell Core 6.x удаляется.</span><span class="sxs-lookup"><span data-stu-id="4a62b-107">PowerShell 7 is an in-place upgrade that removes PowerShell Core 6.x.</span></span>
>
> <span data-ttu-id="4a62b-108">Папка `/usr/local/microsoft/powershell/6` заменяется на `/usr/local/microsoft/powershell/7`.</span><span class="sxs-lookup"><span data-stu-id="4a62b-108">The `/usr/local/microsoft/powershell/6` folder is replaced by `/usr/local/microsoft/powershell/7`.</span></span>
>
> <span data-ttu-id="4a62b-109">Если вы хотите запускать PowerShell 6 параллельно с PowerShell 7, переустановите PowerShell 6 с использованием [двоичного архива](#binary-archives).</span><span class="sxs-lookup"><span data-stu-id="4a62b-109">If you need to run PowerShell 6 side-by-side with PowerShell 7, reinstall PowerShell 6 using the [binary archive](#binary-archives) method.</span></span>

## <a name="about-brew"></a><span data-ttu-id="4a62b-110">Сведения о Brew</span><span class="sxs-lookup"><span data-stu-id="4a62b-110">About Brew</span></span>

<span data-ttu-id="4a62b-111">[Homebrew][brew] является предпочтительным диспетчером пакетов для macOS.</span><span class="sxs-lookup"><span data-stu-id="4a62b-111">[Homebrew][brew] is the preferred package manager for macOS.</span></span> <span data-ttu-id="4a62b-112">Если команда `brew` не найдена, нужно установить Homebrew по [соответствующим инструкциям][brew].</span><span class="sxs-lookup"><span data-stu-id="4a62b-112">If the `brew` command is not found, you need to install Homebrew following [their instructions][brew].</span></span> <span data-ttu-id="4a62b-113">Вы также можете установить PowerShell с помощью [прямого скачивания](#installation-via-direct-download) или из [архивов двоичных файлов](#binary-archives).</span><span class="sxs-lookup"><span data-stu-id="4a62b-113">Otherwise you may install PowerShell via [Direct Download](#installation-via-direct-download) or from [Binary Archives](#binary-archives).</span></span>

## <a name="installation-of-latest-stable-release-via-homebrew-on-macos-1012-or-higher"></a><span data-ttu-id="4a62b-114">Установка последнего стабильного выпуска с помощью Homebrew в macOS 10.12 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="4a62b-114">Installation of latest stable release via Homebrew on macOS 10.12 or higher</span></span>

<span data-ttu-id="4a62b-115">См. дополнительные сведения о [Brew](#about-brew).</span><span class="sxs-lookup"><span data-stu-id="4a62b-115">See [About Brew](#about-brew) for information about Brew.</span></span>

<span data-ttu-id="4a62b-116">Теперь можно установить PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4a62b-116">Now, you can install PowerShell:</span></span>

```sh
brew cask install powershell
```

<span data-ttu-id="4a62b-117">И наконец, убедитесь, что установка прошла без ошибок.</span><span class="sxs-lookup"><span data-stu-id="4a62b-117">Finally, verify that your install is working properly:</span></span>

```sh
pwsh
```

<span data-ttu-id="4a62b-118">После выпуска новых версий PowerShell обновите формулы Homebrew и PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4a62b-118">When new versions of PowerShell are released, update Homebrew's formulae and upgrade PowerShell:</span></span>

```sh
brew update
brew cask upgrade powershell
```

> [!NOTE]
> <span data-ttu-id="4a62b-119">Приведенные выше команды можно вызвать из узла PowerShell (pwsh), но затем потребуется выйти из оболочки PowerShell и перезапустить ее, чтобы завершить обновление и обновить значения в таблице `$PSVersionTable`.</span><span class="sxs-lookup"><span data-stu-id="4a62b-119">The commands above can be called from within a PowerShell (pwsh) host, but then the PowerShell shell must be exited and restarted to complete the upgrade and refresh the values shown in `$PSVersionTable`.</span></span>

[brew]: https://brew.sh/

## <a name="installation-of-latest-preview-release-via-homebrew-on-macos-1012-or-higher"></a><span data-ttu-id="4a62b-120">Установка последнего предварительного выпуска с помощью Homebrew в macOS 10.12 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="4a62b-120">Installation of latest preview release via Homebrew on macOS 10.12 or higher</span></span>

<span data-ttu-id="4a62b-121">См. дополнительные сведения о [Brew](#about-brew).</span><span class="sxs-lookup"><span data-stu-id="4a62b-121">See [About Brew](#about-brew) for information about Brew.</span></span>

<span data-ttu-id="4a62b-122">После установки Homebrew можно установить PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4a62b-122">After you've installed Homebrew, you can install PowerShell.</span></span>
<span data-ttu-id="4a62b-123">Сначала установите пакет [Cask-Versions][cask-versions], который позволит устанавливать альтернативные версии Cask-пакетов.</span><span class="sxs-lookup"><span data-stu-id="4a62b-123">First, install the [Cask-Versions][cask-versions] package that lets you install alternative versions of cask packages:</span></span>

```sh
brew tap homebrew/cask-versions
```

<span data-ttu-id="4a62b-124">Теперь можно установить PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4a62b-124">Now, you can install PowerShell:</span></span>

```sh
brew cask install powershell-preview
```

<span data-ttu-id="4a62b-125">И наконец, убедитесь, что установка прошла без ошибок.</span><span class="sxs-lookup"><span data-stu-id="4a62b-125">Finally, verify that your install is working properly:</span></span>

```sh
pwsh-preview
```

<span data-ttu-id="4a62b-126">После выпуска новых версий PowerShell обновите формулы Homebrew и PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4a62b-126">When new versions of PowerShell are released, update Homebrew's formulae and upgrade PowerShell:</span></span>

```sh
brew update
brew cask upgrade powershell-preview
```

> [!NOTE]
> <span data-ttu-id="4a62b-127">Команду, указанную выше, можно вызвать на узле PowerShell (pwsh), но для этого необходимо завершить его обновление. Что в свою очередь будет сделано, когда вы выйдете из PowerShell и перезапустите его.</span><span class="sxs-lookup"><span data-stu-id="4a62b-127">The commands above can be called from within a PowerShell (pwsh) host, but then the PowerShell shell must be exited and restarted to complete the upgrade.</span></span>
> <span data-ttu-id="4a62b-128">Обновите значения, которые отображаются в `$PSVersionTable`.</span><span class="sxs-lookup"><span data-stu-id="4a62b-128">and refresh the values shown in `$PSVersionTable`.</span></span>

## <a name="installation-via-direct-download"></a><span data-ttu-id="4a62b-129">Установка с помощью прямого скачивания</span><span class="sxs-lookup"><span data-stu-id="4a62b-129">Installation via Direct Download</span></span>

<span data-ttu-id="4a62b-130">Скачайте пакет PKG `powershell-lts-7.0.1-osx-x64.pkg`</span><span class="sxs-lookup"><span data-stu-id="4a62b-130">Download the PKG package `powershell-lts-7.0.1-osx-x64.pkg`</span></span>
<span data-ttu-id="4a62b-131">со страницы [выпусков][] на компьютер с macOS.</span><span class="sxs-lookup"><span data-stu-id="4a62b-131">from the [releases][] page onto your macOS machine.</span></span>

<span data-ttu-id="4a62b-132">Дважды щелкните файл и следуйте инструкциям на экране либо установите его из командной строки:</span><span class="sxs-lookup"><span data-stu-id="4a62b-132">You can double-click the file and follow the prompts, or install it from the terminal:</span></span>

```sh
sudo installer -pkg powershell-lts-7.0.1-osx-x64.pkg -target /
```

<span data-ttu-id="4a62b-133">Установите [OpenSSL](#install-openssl).</span><span class="sxs-lookup"><span data-stu-id="4a62b-133">Install [OpenSSL](#install-openssl).</span></span> <span data-ttu-id="4a62b-134">OpenSSL требуется для удаленного взаимодействия PowerShell и операций CIM.</span><span class="sxs-lookup"><span data-stu-id="4a62b-134">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>

## <a name="install-as-a-net-global-tool"></a><span data-ttu-id="4a62b-135">Установка в качестве глобального средства .NET</span><span class="sxs-lookup"><span data-stu-id="4a62b-135">Install as a .NET Global tool</span></span>

<span data-ttu-id="4a62b-136">Если вы уже установили [пакет SDK для .NET Core](/dotnet/core/sdk), установите PowerShell как [глобальное средство .NET](/dotnet/core/tools/global-tools).</span><span class="sxs-lookup"><span data-stu-id="4a62b-136">If you already have the [.NET Core SDK](/dotnet/core/sdk) installed, it's easy to install PowerShell as a [.NET Global tool](/dotnet/core/tools/global-tools).</span></span>

```
dotnet tool install --global PowerShell
```

<span data-ttu-id="4a62b-137">Установщик инструмента dotnet добавляет `~/.dotnet/tools` в переменную среды `PATH`.</span><span class="sxs-lookup"><span data-stu-id="4a62b-137">The dotnet tool installer adds `~/.dotnet/tools` to your `PATH` environment variable.</span></span> <span data-ttu-id="4a62b-138">Но в выполняющейся оболочке отсутствует обновленная переменная `PATH`.</span><span class="sxs-lookup"><span data-stu-id="4a62b-138">However, the currently running shell does not have the updated `PATH`.</span></span> <span data-ttu-id="4a62b-139">Вы можете запустить PowerShell из новой оболочки, введя `pwsh`.</span><span class="sxs-lookup"><span data-stu-id="4a62b-139">You should be able to start PowerShell from a new shell by typing `pwsh`.</span></span>

## <a name="binary-archives"></a><span data-ttu-id="4a62b-140">Архивы двоичных файлов</span><span class="sxs-lookup"><span data-stu-id="4a62b-140">Binary Archives</span></span>

<span data-ttu-id="4a62b-141">Для поддержки расширенных сценариев развертывания на платформе macOS доступны архивы `tar.gz` двоичных файлов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4a62b-141">PowerShell binary `tar.gz` archives are provided for the macOS platform to enable advanced deployment scenarios.</span></span>

### <a name="installing-binary-archives-on-macos"></a><span data-ttu-id="4a62b-142">Установка архивов двоичных файлов в macOS</span><span class="sxs-lookup"><span data-stu-id="4a62b-142">Installing binary archives on macOS</span></span>

```sh
# Download the powershell '.tar.gz' archive
curl -L -o /tmp/powershell.tar.gz https://github.com/PowerShell/PowerShell/releases/download/v7.0.1/powershell-7.0.1-osx-x64.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /usr/local/microsoft/powershell/7.0.1

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /usr/local/microsoft/powershell/7.0.1

# Set execute permissions
sudo chmod +x /usr/local/microsoft/powershell/7.0.1/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /usr/local/microsoft/powershell/7.0.1/pwsh /usr/local/bin/pwsh
```

<span data-ttu-id="4a62b-143">Установите [OpenSSL](#install-openssl).</span><span class="sxs-lookup"><span data-stu-id="4a62b-143">Install [OpenSSL](#install-openssl).</span></span> <span data-ttu-id="4a62b-144">OpenSSL требуется для удаленного взаимодействия PowerShell и операций CIM.</span><span class="sxs-lookup"><span data-stu-id="4a62b-144">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>

## <a name="installing-dependencies"></a><span data-ttu-id="4a62b-145">Установка зависимостей</span><span class="sxs-lookup"><span data-stu-id="4a62b-145">Installing dependencies</span></span>

### <a name="install-xcode-command-line-tools"></a><span data-ttu-id="4a62b-146">Установка средств командной строки XCode</span><span class="sxs-lookup"><span data-stu-id="4a62b-146">Install XCode command-line tools</span></span>

```sh
xcode-select --install
```

### <a name="install-openssl"></a><span data-ttu-id="4a62b-147">Установка OpenSSL</span><span class="sxs-lookup"><span data-stu-id="4a62b-147">Install OpenSSL</span></span>

<span data-ttu-id="4a62b-148">OpenSSL требуется для удаленного взаимодействия PowerShell и операций CIM.</span><span class="sxs-lookup"><span data-stu-id="4a62b-148">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span> <span data-ttu-id="4a62b-149">Установка возможна с помощью MacPorts.</span><span class="sxs-lookup"><span data-stu-id="4a62b-149">You can install via MacPorts.</span></span>

#### <a name="install-openssl-via-macports"></a><span data-ttu-id="4a62b-150">Установка OpenSSL с помощью MacPorts</span><span class="sxs-lookup"><span data-stu-id="4a62b-150">Install OpenSSL via MacPorts</span></span>

1. <span data-ttu-id="4a62b-151">Установите [средство командной строки XCode](#install-xcode-command-line-tools).</span><span class="sxs-lookup"><span data-stu-id="4a62b-151">Install the [XCode command line tools](#install-xcode-command-line-tools).</span></span>
1. <span data-ttu-id="4a62b-152">Установите MacPorts.</span><span class="sxs-lookup"><span data-stu-id="4a62b-152">Install MacPorts.</span></span>
   <span data-ttu-id="4a62b-153">Инструкции см. в [руководстве по установке](https://guide.macports.org/chunked/installing.macports.html).</span><span class="sxs-lookup"><span data-stu-id="4a62b-153">If you need instructions, refer to the [installation guide](https://guide.macports.org/chunked/installing.macports.html).</span></span>
1. <span data-ttu-id="4a62b-154">Обновите MacPorts, выполнив команду `sudo port selfupdate`.</span><span class="sxs-lookup"><span data-stu-id="4a62b-154">Update MacPorts by running `sudo port selfupdate`.</span></span>
1. <span data-ttu-id="4a62b-155">Обновите пакеты MacPorts, выполнив команду `sudo port upgrade outdated`.</span><span class="sxs-lookup"><span data-stu-id="4a62b-155">Upgrade MacPorts packages by running `sudo port upgrade outdated`.</span></span>
1. <span data-ttu-id="4a62b-156">Установите OpenSSL, запустив `sudo port install openssl10`.</span><span class="sxs-lookup"><span data-stu-id="4a62b-156">Install OpenSSL by running `sudo port install openssl10`.</span></span>
1. <span data-ttu-id="4a62b-157">Укажите ссылки на библиотеки, чтобы сделать их доступными для PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4a62b-157">Link the libraries to make them available to PowerShell:</span></span>

```sh
sudo mkdir -p /usr/local/opt/openssl
sudo ln -s /opt/local/lib/openssl-1.0 /usr/local/opt/openssl/lib
```

## <a name="uninstalling-powershell"></a><span data-ttu-id="4a62b-158">Удаление PowerShell</span><span class="sxs-lookup"><span data-stu-id="4a62b-158">Uninstalling PowerShell</span></span>

<span data-ttu-id="4a62b-159">Если вы установили PowerShell с помощью Homebrew, используйте следующую команду для удаления:</span><span class="sxs-lookup"><span data-stu-id="4a62b-159">If you installed PowerShell with Homebrew, use the following command to uninstall:</span></span>

```sh
brew cask uninstall powershell
```

<span data-ttu-id="4a62b-160">Если вы установили PowerShell с помощью прямого скачивания, PowerShell нужно удалить вручную:</span><span class="sxs-lookup"><span data-stu-id="4a62b-160">If you installed PowerShell via direct download, PowerShell must be removed manually:</span></span>

```sh
sudo rm -rf /usr/local/bin/pwsh /usr/local/microsoft/powershell
```

<span data-ttu-id="4a62b-161">Чтобы удалить дополнительные пути PowerShell, ознакомьтесь с разделом [Пути](#paths) этой статьи, и удалите их с помощью команды `sudo rm`.</span><span class="sxs-lookup"><span data-stu-id="4a62b-161">To remove the additional PowerShell paths, refer to the [paths](#paths) section in this document and remove the paths using `sudo rm`.</span></span>

> [!NOTE]
> <span data-ttu-id="4a62b-162">Это не требуется в случае установки с помощью Homebrew.</span><span class="sxs-lookup"><span data-stu-id="4a62b-162">This is not necessary if you installed with Homebrew.</span></span>

## <a name="paths"></a><span data-ttu-id="4a62b-163">Пути</span><span class="sxs-lookup"><span data-stu-id="4a62b-163">Paths</span></span>

* <span data-ttu-id="4a62b-164">`$PSHOME` имеет значение `/usr/local/microsoft/powershell/7.0.1/`.</span><span class="sxs-lookup"><span data-stu-id="4a62b-164">`$PSHOME` is `/usr/local/microsoft/powershell/7.0.1/`</span></span>
* <span data-ttu-id="4a62b-165">Профили пользователей будут считаны из `~/.config/powershell/profile.ps1`.</span><span class="sxs-lookup"><span data-stu-id="4a62b-165">User profiles will be read from `~/.config/powershell/profile.ps1`</span></span>
* <span data-ttu-id="4a62b-166">Профили по умолчанию будут считаны из `$PSHOME/profile.ps1`.</span><span class="sxs-lookup"><span data-stu-id="4a62b-166">Default profiles will be read from `$PSHOME/profile.ps1`</span></span>
* <span data-ttu-id="4a62b-167">Модули пользователей будут считаны из `~/.local/share/powershell/Modules`.</span><span class="sxs-lookup"><span data-stu-id="4a62b-167">User modules will be read from `~/.local/share/powershell/Modules`</span></span>
* <span data-ttu-id="4a62b-168">Общие модули будут считаны из `/usr/local/share/powershell/Modules`.</span><span class="sxs-lookup"><span data-stu-id="4a62b-168">Shared modules will be read from `/usr/local/share/powershell/Modules`</span></span>
* <span data-ttu-id="4a62b-169">Модули по умолчанию будут считаны из `$PSHOME/Modules`.</span><span class="sxs-lookup"><span data-stu-id="4a62b-169">Default modules will be read from `$PSHOME/Modules`</span></span>
* <span data-ttu-id="4a62b-170">Журнал PSReadline будет записан в `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`.</span><span class="sxs-lookup"><span data-stu-id="4a62b-170">PSReadline history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="4a62b-171">Профили учитывают конфигурацию PowerShell для отдельных узлов.</span><span class="sxs-lookup"><span data-stu-id="4a62b-171">The profiles respect PowerShell's per-host configuration.</span></span>
<span data-ttu-id="4a62b-172">Профиль узла по умолчанию находится в `Microsoft.PowerShell_profile.ps1` в тех же расположениях.</span><span class="sxs-lookup"><span data-stu-id="4a62b-172">So the default host-specific profile exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="4a62b-173">PowerShell отвечает требованиям [спецификации каталога размещения файлов, связанных со средой настольной графической среды (X-сервера), стандартизированного XDG (X Desktop Group)][xdg-bds] в macOS.</span><span class="sxs-lookup"><span data-stu-id="4a62b-173">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on macOS.</span></span>

<span data-ttu-id="4a62b-174">Так как macOS является развитием BSD, необходимо использовать префикс `/usr/local` вместо `/opt`.</span><span class="sxs-lookup"><span data-stu-id="4a62b-174">Because macOS is a derivation of BSD, the prefix `/usr/local` is used instead of `/opt`.</span></span>
<span data-ttu-id="4a62b-175">Таким образом, `$PSHOME` имеет значение `/usr/local/microsoft/powershell/7.0.1/`, а символьная ссылка размещается в `/usr/local/bin/pwsh`.</span><span class="sxs-lookup"><span data-stu-id="4a62b-175">So, `$PSHOME` is `/usr/local/microsoft/powershell/7.0.1/`, and the symbolic link is placed at `/usr/local/bin/pwsh`.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4a62b-176">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="4a62b-176">Additional Resources</span></span>

* <span data-ttu-id="4a62b-177">[Homebrew в Интернете][brew]</span><span class="sxs-lookup"><span data-stu-id="4a62b-177">[Homebrew Web][brew]</span></span>
* <span data-ttu-id="4a62b-178">[Репозиторий Homebrew на Github][GitHub]</span><span class="sxs-lookup"><span data-stu-id="4a62b-178">[Homebrew Github Repository][GitHub]</span></span>
* <span data-ttu-id="4a62b-179">[Homebrew-Cask][cask]</span><span class="sxs-lookup"><span data-stu-id="4a62b-179">[Homebrew-Cask][cask]</span></span>

[brew]: http://brew.sh/
[Cask]: https://github.com/Homebrew/homebrew-cask
[cask-versions]: https://github.com/Homebrew/homebrew-cask-versions
[GitHub]: https://github.com/Homebrew
[выпусков]: https://github.com/PowerShell/PowerShell/releases/latest
[releases]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
