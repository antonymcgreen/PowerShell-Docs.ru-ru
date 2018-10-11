---
title: Установка PowerShell Core в macOS
description: Сведения об установке PowerShell Core в macOS
ms.date: 08/06/2018
ms.openlocfilehash: 042c933dfa83f3ab52e315036e4f817145116d00
ms.sourcegitcommit: aa41249f153bbc6e11667ade60c878980c15abc6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2018
ms.locfileid: "45611493"
---
# <a name="installing-powershell-core-on-macos"></a><span data-ttu-id="60a99-103">Установка PowerShell Core в macOS</span><span class="sxs-lookup"><span data-stu-id="60a99-103">Installing PowerShell Core on macOS</span></span>

<span data-ttu-id="60a99-104">PowerShell Core поддерживает macOS версии 10.12 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="60a99-104">PowerShell Core supports macOS 10.12 and higher.</span></span>
<span data-ttu-id="60a99-105">Все пакеты доступны на нашей странице [выпусков][] GitHub.</span><span class="sxs-lookup"><span data-stu-id="60a99-105">All packages are available on our GitHub [releases][] page.</span></span>
<span data-ttu-id="60a99-106">После установки пакета запустите `pwsh` из терминала.</span><span class="sxs-lookup"><span data-stu-id="60a99-106">Once the package is installed, run `pwsh` from a terminal.</span></span>

## <a name="installation-of-latest-stable-release-via-homebrew-on-macos-1012-or-higher"></a><span data-ttu-id="60a99-107">Установка последнего стабильного выпуска с помощью Homebrew в macOS 10.12 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="60a99-107">Installation of latest stable release via Homebrew on macOS 10.12 or higher</span></span>

<span data-ttu-id="60a99-108">[Homebrew][brew] является предпочтительным диспетчером пакетов для macOS.</span><span class="sxs-lookup"><span data-stu-id="60a99-108">[Homebrew][brew] is the preferred package manager for macOS.</span></span>
<span data-ttu-id="60a99-109">Если команда `brew` не найдена, нужно установить Homebrew по [соответствующим инструкциям][brew].</span><span class="sxs-lookup"><span data-stu-id="60a99-109">If the `brew` command is not found, you need to install Homebrew following [their instructions][brew].</span></span>

<span data-ttu-id="60a99-110">Теперь можно установить PowerShell:</span><span class="sxs-lookup"><span data-stu-id="60a99-110">Now, you can install PowerShell:</span></span>

```sh
brew cask install powershell
```

<span data-ttu-id="60a99-111">И наконец, убедитесь, что установка прошла без ошибок.</span><span class="sxs-lookup"><span data-stu-id="60a99-111">Finally, verify that your install is working properly:</span></span>

```sh
pwsh
```

<span data-ttu-id="60a99-112">После выпуска новых версий PowerShell просто обновите формулы Homebrew и PowerShell:</span><span class="sxs-lookup"><span data-stu-id="60a99-112">When new versions of PowerShell are released, simply update Homebrew's formulae and upgrade PowerShell:</span></span>

```sh
brew update
brew cask upgrade powershell
```

> [!NOTE]
> <span data-ttu-id="60a99-113">Команду, указанную выше, можно вызвать на узле PowerShell (pwsh), но для этого необходимо завершить его обновление. Что в свою очередь будет сделано, когда вы выйдете из PowerShell и перезапустите его.</span><span class="sxs-lookup"><span data-stu-id="60a99-113">The commands above can be called from within a PowerShell (pwsh) host, but then the PowerShell shell must be exited and restarted to complete the upgrade.</span></span>
> <span data-ttu-id="60a99-114">Обновите значения, которые отображаются в $PSVersionTable.</span><span class="sxs-lookup"><span data-stu-id="60a99-114">and refresh the values shown in $PSVersionTable.</span></span>

[brew]: http://brew.sh/

## <a name="installation-of-latest-preview-release-via-homebrew-on-macos-1012-or-higher"></a><span data-ttu-id="60a99-115">Установка последнего предварительного выпуска с помощью Homebrew в macOS 10.12 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="60a99-115">Installation of latest preview release via Homebrew on macOS 10.12 or higher</span></span>

<span data-ttu-id="60a99-116">[Homebrew][brew] является предпочтительным диспетчером пакетов для macOS.</span><span class="sxs-lookup"><span data-stu-id="60a99-116">[Homebrew][brew] is the preferred package manager for macOS.</span></span>
<span data-ttu-id="60a99-117">Если команда `brew` не найдена, нужно установить Homebrew по [соответствующим инструкциям][brew].</span><span class="sxs-lookup"><span data-stu-id="60a99-117">If the `brew` command is not found, you need to install Homebrew following [their instructions][brew].</span></span>

<span data-ttu-id="60a99-118">После установки Homebrew установка PowerShell не вызывает проблем.</span><span class="sxs-lookup"><span data-stu-id="60a99-118">Once you've installed Homebrew, installing PowerShell is easy.</span></span>
<span data-ttu-id="60a99-119">Сначала установите [cask-версии][cask-versions], что позволит устанавливать альтернативные версии cask-пакетов.</span><span class="sxs-lookup"><span data-stu-id="60a99-119">First, install [Cask-Versions][cask-versions] which lets you install alternative versions of cask packages:</span></span>

```sh
brew tap homebrew/cask-versions
```

<span data-ttu-id="60a99-120">Теперь можно установить PowerShell:</span><span class="sxs-lookup"><span data-stu-id="60a99-120">Now, you can install PowerShell:</span></span>

```sh
brew cask install powershell-preview
```

<span data-ttu-id="60a99-121">И наконец, убедитесь, что установка прошла без ошибок.</span><span class="sxs-lookup"><span data-stu-id="60a99-121">Finally, verify that your install is working properly:</span></span>

```sh
pwsh-preview
```

<span data-ttu-id="60a99-122">После выпуска новых версий PowerShell просто обновите формулы Homebrew и PowerShell:</span><span class="sxs-lookup"><span data-stu-id="60a99-122">When new versions of PowerShell are released, simply update Homebrew's formulae and upgrade PowerShell:</span></span>

```sh
brew update
brew cask upgrade powershell-preview
```

> [!NOTE]
> <span data-ttu-id="60a99-123">Команду, указанную выше, можно вызвать на узле PowerShell (pwsh), но для этого необходимо завершить его обновление. Что в свою очередь будет сделано, когда вы выйдете из PowerShell и перезапустите его.</span><span class="sxs-lookup"><span data-stu-id="60a99-123">The commands above can be called from within a PowerShell (pwsh) host, but then the PowerShell shell must be exited and restarted to complete the upgrade.</span></span>
> <span data-ttu-id="60a99-124">Обновите значения, которые отображаются в $PSVersionTable.</span><span class="sxs-lookup"><span data-stu-id="60a99-124">and refresh the values shown in $PSVersionTable.</span></span>

## <a name="installation-via-direct-download"></a><span data-ttu-id="60a99-125">Установка с помощью прямого скачивания</span><span class="sxs-lookup"><span data-stu-id="60a99-125">Installation via Direct Download</span></span>

<span data-ttu-id="60a99-126">Скачайте пакет PKG `powershell-6.1.0-osx-x64.pkg`</span><span class="sxs-lookup"><span data-stu-id="60a99-126">Download the PKG package `powershell-6.1.0-osx-x64.pkg`</span></span>
<span data-ttu-id="60a99-127">со страницы [выпусков][] на компьютер с macOS.</span><span class="sxs-lookup"><span data-stu-id="60a99-127">from the [releases][] page onto your macOS machine.</span></span>

<span data-ttu-id="60a99-128">Дважды щелкните файл и следуйте инструкциям на экране либо установите его из командной строки:</span><span class="sxs-lookup"><span data-stu-id="60a99-128">You can double-click the file and follow the prompts, or install it from the terminal:</span></span>

```sh
sudo installer -pkg powershell-6.1.0-osx-x64.pkg -target /
```

## <a name="binary-archives"></a><span data-ttu-id="60a99-129">Архивы двоичных файлов</span><span class="sxs-lookup"><span data-stu-id="60a99-129">Binary Archives</span></span>

<span data-ttu-id="60a99-130">Для поддержки расширенных сценариев развертывания на платформе macOS доступны архивы `tar.gz` двоичных файлов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="60a99-130">PowerShell binary `tar.gz` archives are provided for the macOS platform to enable advanced deployment scenarios.</span></span>

### <a name="installing-binary-archives-on-macos"></a><span data-ttu-id="60a99-131">Установка архивов двоичных файлов в macOS</span><span class="sxs-lookup"><span data-stu-id="60a99-131">Installing binary archives on macOS</span></span>

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

## <a name="uninstalling-powershell-core"></a><span data-ttu-id="60a99-132">Удаление PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="60a99-132">Uninstalling PowerShell Core</span></span>

<span data-ttu-id="60a99-133">Если вы установили PowerShell с помощью Homebrew, удаление осуществляется очень просто:</span><span class="sxs-lookup"><span data-stu-id="60a99-133">If you installed PowerShell with Homebrew, uninstallation is easy:</span></span>

```sh
brew cask uninstall powershell
```

<span data-ttu-id="60a99-134">Если вы установили PowerShell с помощью прямого скачивания, PowerShell нужно удалить вручную:</span><span class="sxs-lookup"><span data-stu-id="60a99-134">If you installed PowerShell via direct download, PowerShell must be removed manually:</span></span>

```sh
sudo rm -rf /usr/local/bin/pwsh /usr/local/microsoft/powershell
```

<span data-ttu-id="60a99-135">Чтобы удалить дополнительные пути PowerShell, ознакомьтесь с разделом [пути](#paths) этой статьи, и удалите необходимые пути с помощью команды `sudo rm`.</span><span class="sxs-lookup"><span data-stu-id="60a99-135">To remove the additional PowerShell paths, please see the [paths](#paths) section in this document and remove the desired the paths using `sudo rm`.</span></span>

> [!NOTE]
> <span data-ttu-id="60a99-136">Это не требуется в случае установки с помощью Homebrew.</span><span class="sxs-lookup"><span data-stu-id="60a99-136">This is not necessary if you installed with Homebrew.</span></span>

## <a name="paths"></a><span data-ttu-id="60a99-137">Пути</span><span class="sxs-lookup"><span data-stu-id="60a99-137">Paths</span></span>

* <span data-ttu-id="60a99-138">`$PSHOME` имеет значение `/usr/local/microsoft/powershell/6.1.0/`.</span><span class="sxs-lookup"><span data-stu-id="60a99-138">`$PSHOME` is `/usr/local/microsoft/powershell/6.1.0/`</span></span>
* <span data-ttu-id="60a99-139">Профили пользователей будут считаны из `~/.config/powershell/profile.ps1`.</span><span class="sxs-lookup"><span data-stu-id="60a99-139">User profiles will be read from `~/.config/powershell/profile.ps1`</span></span>
* <span data-ttu-id="60a99-140">Профили по умолчанию будут считаны из `$PSHOME/profile.ps1`.</span><span class="sxs-lookup"><span data-stu-id="60a99-140">Default profiles will be read from `$PSHOME/profile.ps1`</span></span>
* <span data-ttu-id="60a99-141">Модули пользователей будут считаны из `~/.local/share/powershell/Modules`.</span><span class="sxs-lookup"><span data-stu-id="60a99-141">User modules will be read from `~/.local/share/powershell/Modules`</span></span>
* <span data-ttu-id="60a99-142">Общие модули будут считаны из `/usr/local/share/powershell/Modules`.</span><span class="sxs-lookup"><span data-stu-id="60a99-142">Shared modules will be read from `/usr/local/share/powershell/Modules`</span></span>
* <span data-ttu-id="60a99-143">Модули по умолчанию будут считаны из `$PSHOME/Modules`.</span><span class="sxs-lookup"><span data-stu-id="60a99-143">Default modules will be read from `$PSHOME/Modules`</span></span>
* <span data-ttu-id="60a99-144">Журнал PSReadline будет записан в `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`.</span><span class="sxs-lookup"><span data-stu-id="60a99-144">PSReadline history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="60a99-145">Профили учитывают конфигурацию PowerShell для отдельных узлов.</span><span class="sxs-lookup"><span data-stu-id="60a99-145">The profiles respect PowerShell's per-host configuration.</span></span>
<span data-ttu-id="60a99-146">Поэтому профили конкретных узлов по умолчанию находятся в `Microsoft.PowerShell_profile.ps1` в тех же расположениях.</span><span class="sxs-lookup"><span data-stu-id="60a99-146">So the default host-specific profiles exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="60a99-147">PowerShell отвечает требованиям [спецификации каталога размещения файлов, связанных со средой настольной графической среды (X-сервера), стандартизированного XDG (X Desktop Group)][xdg-bds] в macOS.</span><span class="sxs-lookup"><span data-stu-id="60a99-147">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on macOS.</span></span>

<span data-ttu-id="60a99-148">Так как macOS является развитием BSD, необходимо использовать префикс `/usr/local` вместо `/opt`.</span><span class="sxs-lookup"><span data-stu-id="60a99-148">Because macOS is a derivation of BSD, the prefix `/usr/local` is used instead of `/opt`.</span></span>
<span data-ttu-id="60a99-149">Таким образом, `$PSHOME` имеет значение `/usr/local/microsoft/powershell/6.1.0/`, а символьная ссылка размещается в `/usr/local/bin/pwsh`.</span><span class="sxs-lookup"><span data-stu-id="60a99-149">Thus, `$PSHOME` is `/usr/local/microsoft/powershell/6.1.0/`, and the symlink is placed at `/usr/local/bin/pwsh`.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="60a99-150">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="60a99-150">Additional Resources</span></span>

* <span data-ttu-id="60a99-151">[Homebrew Web][brew]</span><span class="sxs-lookup"><span data-stu-id="60a99-151">[Homebrew Web][brew]</span></span>
* <span data-ttu-id="60a99-152">[Репозиторий Github Homebrew][GitHub]</span><span class="sxs-lookup"><span data-stu-id="60a99-152">[Homebrew Github Repository][GitHub]</span></span>
* <span data-ttu-id="60a99-153">[Homebrew-Cask][cask]</span><span class="sxs-lookup"><span data-stu-id="60a99-153">[Homebrew-Cask][cask]</span></span>

[brew]: http://brew.sh/
[Cask]: https://github.com/Homebrew/homebrew-cask
[cask-versions]: https://github.com/Homebrew/homebrew-cask-versions
[GitHub]: https://github.com/Homebrew
[выпусков]: https://github.com/PowerShell/PowerShell/releases/latest
[releases]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
