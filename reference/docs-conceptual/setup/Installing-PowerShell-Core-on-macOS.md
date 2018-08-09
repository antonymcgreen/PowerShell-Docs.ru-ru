---
title: Установка PowerShell Core в macOS
description: Сведения об установке PowerShell Core в macOS
ms.date: 08/06/2018
ms.openlocfilehash: ff1814d95b3ca3fa8497069dff249fd2ad5576ef
ms.sourcegitcommit: 01ac77cd0b00e4e5e964504563a9212e8002e5e0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2018
ms.locfileid: "39587471"
---
# <a name="installing-powershell-core-on-macos"></a><span data-ttu-id="5434c-103">Установка PowerShell Core в macOS</span><span class="sxs-lookup"><span data-stu-id="5434c-103">Installing PowerShell Core on macOS</span></span>

<span data-ttu-id="5434c-104">PowerShell Core поддерживает macOS версии 10.12 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="5434c-104">PowerShell Core supports macOS 10.12 and higher.</span></span>
<span data-ttu-id="5434c-105">Все пакеты доступны на нашей странице [Выпуски][] GitHub.</span><span class="sxs-lookup"><span data-stu-id="5434c-105">All packages are available on our GitHub [releases][] page.</span></span>
<span data-ttu-id="5434c-106">После установки пакета запустите `pwsh` из терминала.</span><span class="sxs-lookup"><span data-stu-id="5434c-106">Once the package is installed, run `pwsh` from a terminal.</span></span>

### <a name="installation-via-homebrew-on-macos-1012"></a><span data-ttu-id="5434c-107">Установка в macOS 10.12+ с помощью Homebrew</span><span class="sxs-lookup"><span data-stu-id="5434c-107">Installation via Homebrew on macOS 10.12+</span></span>

<span data-ttu-id="5434c-108">[Homebrew][brew] является предпочтительным диспетчером пакетов для macOS.</span><span class="sxs-lookup"><span data-stu-id="5434c-108">[Homebrew][brew] is the preferred package manager for macOS.</span></span>
<span data-ttu-id="5434c-109">В окне терминала введите `brew` для запуска Homebrew.</span><span class="sxs-lookup"><span data-stu-id="5434c-109">From a terminal window, type `brew` to run Homebrew.</span></span>  <span data-ttu-id="5434c-110">Если команда `brew` не найдена, нужно установить Homebrew по [соответствующим инструкциям][brew].</span><span class="sxs-lookup"><span data-stu-id="5434c-110">If the `brew` command is not found, you need to install Homebrew following [their instructions][brew].</span></span>

> [!NOTE]
> <span data-ttu-id="5434c-111">Если вы уже установили Homebrew, настоятельно рекомендуется выполнить команды brew update-reset и brew update.</span><span class="sxs-lookup"><span data-stu-id="5434c-111">If you installed Homebrew in the past, it's always a good idea to run 'brew update-reset' && 'brew update'.</span></span>
```sh
brew update-reset
brew update
```

> <span data-ttu-id="5434c-112">Для более старых версий Homebrew использовалось касание caskroom/cask. Сейчас вместо этого используется homebrew/cask.</span><span class="sxs-lookup"><span data-stu-id="5434c-112">Older versions of Homebrew used the tap 'caskroom/cask', which has been deprecated, and migrated into 'homebrew/cask'.</span></span>  <span data-ttu-id="5434c-113">Дополнительные сведения см. в справочнике по [Homebrew-cask][cask].</span><span class="sxs-lookup"><span data-stu-id="5434c-113">More information can be found at [Homebrew-cask][cask].</span></span> <span data-ttu-id="5434c-114">Используйте команду brew tap, чтобы получить список текущих касаний.</span><span class="sxs-lookup"><span data-stu-id="5434c-114">Use the 'brew tap' command to list your current taps.</span></span>  <span data-ttu-id="5434c-115">Если вы видите caskroom/cask, можно использовать brew-update, чтобы выполнить перенос касаний в Homebrew.</span><span class="sxs-lookup"><span data-stu-id="5434c-115">If you see 'caskroom/cask' you can use 'brew update' to have Homebrew migrate the taps.</span></span>

```sh
brew tap
brew update
```

<span data-ttu-id="5434c-116">После установки или обновления Homebrew установка PowerShell не вызывает проблем.</span><span class="sxs-lookup"><span data-stu-id="5434c-116">Once you've installed/updated Homebrew, installing PowerShell is easy.</span></span>

<span data-ttu-id="5434c-117">Чтобы установить PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5434c-117">To install PowerShell:</span></span>

```sh
brew cask install powershell
```

<span data-ttu-id="5434c-118">И наконец, убедитесь, что установка прошла без ошибок.</span><span class="sxs-lookup"><span data-stu-id="5434c-118">Finally, verify that your install is working properly:</span></span>

```sh
pwsh
```

<span data-ttu-id="5434c-119">Чтобы выйти из PowerShell и вернуться в bash, используйте команду exit.</span><span class="sxs-lookup"><span data-stu-id="5434c-119">To exit PowerShell, and return to bash, use the 'exit' command.</span></span>
```sh
exit
```

<span data-ttu-id="5434c-120">После выпуска новых версий PowerShell просто обновите формулы Homebrew и PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5434c-120">When new versions of PowerShell are released, simply update Homebrew's formulae and upgrade PowerShell:</span></span>

```sh
brew update
brew cask upgrade powershell
```

> [!NOTE]
> <span data-ttu-id="5434c-121">Приведенные выше команды можно вызвать с узла PowerShell (pwsh), но затем потребуется выйти из оболочки PowerShell и перезапустить ее, чтобы завершить обновление и обновить значения в таблице $PSVersionTable.</span><span class="sxs-lookup"><span data-stu-id="5434c-121">The commands above can be called from within a PowerShell (pwsh) host, but then the PowerShell shell must be exited and restarted to complete the upgrade and refresh the values shown in $PSVersionTable.</span></span>

### <a name="installing-preview-via-homebrew-on-macos-1012"></a><span data-ttu-id="5434c-122">Установка предварительной версии в macOS 10.12+ с помощью Homebrew</span><span class="sxs-lookup"><span data-stu-id="5434c-122">Installing Preview via Homebrew on macOS 10.12+</span></span>

<span data-ttu-id="5434c-123">[Homebrew][brew] является предпочтительным диспетчером пакетов для macOS.</span><span class="sxs-lookup"><span data-stu-id="5434c-123">[Homebrew][brew] is the preferred package manager for macOS.</span></span>
<span data-ttu-id="5434c-124">В окне терминала введите `brew` для запуска Homebrew.</span><span class="sxs-lookup"><span data-stu-id="5434c-124">From a terminal window, type `brew` to run Homebrew.</span></span>  <span data-ttu-id="5434c-125">Если команда `brew` не найдена, нужно установить Homebrew по [соответствующим инструкциям][brew].</span><span class="sxs-lookup"><span data-stu-id="5434c-125">If the `brew` command is not found, you need to install Homebrew following [their instructions][brew].</span></span>

> [!NOTE]
> <span data-ttu-id="5434c-126">Если вы уже установили Homebrew, настоятельно рекомендуется выполнить команды brew update-reset и brew update.</span><span class="sxs-lookup"><span data-stu-id="5434c-126">If you installed Homebrew in the past, it's always a good idea to run 'brew update-reset' && 'brew update'.</span></span>
```sh
brew update-reset
brew update
```

<span data-ttu-id="5434c-127">После этого коснитесь репозитория `versions` casks, чтобы получить пакет предварительной версии:</span><span class="sxs-lookup"><span data-stu-id="5434c-127">Then, you must tap the `versions` casks repository to get the preview package:</span></span>

```sh
brew tap homebrew/cask-versions
```

<span data-ttu-id="5434c-128">Чтобы установить предварительную версию PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5434c-128">To install PowerShell Preview:</span></span>

```sh
brew cask install powershell-preview
```

<span data-ttu-id="5434c-129">И наконец, убедитесь, что установка прошла без ошибок.</span><span class="sxs-lookup"><span data-stu-id="5434c-129">Finally, verify that your install is working properly:</span></span>

```sh
pwsh-preview
```

<span data-ttu-id="5434c-130">После выпуска новых версий PowerShell просто обновите формулы Homebrew и предварительную версию PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5434c-130">When new versions of PowerShell are released, simply update Homebrew's formulae and upgrade PowerShell Preview:</span></span>

```sh
brew update
brew cask upgrade powershell-preview
```

> [!NOTE]
> <span data-ttu-id="5434c-131">Приведенные выше команды можно вызвать с узла PowerShell (pwsh), но затем потребуется выйти из оболочки PowerShell и перезапустить ее, чтобы завершить обновление и обновить значения в таблице $PSVersionTable.</span><span class="sxs-lookup"><span data-stu-id="5434c-131">The commands above can be called from within a PowerShell (pwsh) host, but then the PowerShell shell must be exited and restarted to complete the upgrade and refresh the values shown in $PSVersionTable.</span></span>

### <a name="installation-via-direct-download"></a><span data-ttu-id="5434c-132">Установка с помощью прямого скачивания</span><span class="sxs-lookup"><span data-stu-id="5434c-132">Installation via Direct Download</span></span>

<span data-ttu-id="5434c-133">Для компьютера с macOS пакет PKG `powershell-6.0.2-osx.10.12-x64.pkg` можно загрузить на странице [Выпуски][].</span><span class="sxs-lookup"><span data-stu-id="5434c-133">Download the PKG package `powershell-6.0.2-osx.10.12-x64.pkg` from the [releases][] page onto your macOS machine.</span></span>

<span data-ttu-id="5434c-134">Дважды щелкните файл и следуйте инструкциям на экране либо установите его из командной строки:</span><span class="sxs-lookup"><span data-stu-id="5434c-134">You can double-click the file and follow the prompts, or install it from the terminal:</span></span>

```sh
sudo installer -pkg powershell-6.0.2-osx.10.12-x64.pkg -target /
```

## <a name="binary-archives"></a><span data-ttu-id="5434c-135">Архивы двоичных файлов</span><span class="sxs-lookup"><span data-stu-id="5434c-135">Binary Archives</span></span>

<span data-ttu-id="5434c-136">Для поддержки расширенных сценариев развертывания на платформах macOS и Linux доступны архивы двоичных файлов PowerShell `tar.gz`.</span><span class="sxs-lookup"><span data-stu-id="5434c-136">PowerShell binary `tar.gz` archives are provided for macOS and Linux platforms to enable advanced deployment scenarios.</span></span>

### <a name="installing-binary-archives-on-macos"></a><span data-ttu-id="5434c-137">Установка архивов двоичных файлов в macOS</span><span class="sxs-lookup"><span data-stu-id="5434c-137">Installing binary archives on macOS</span></span>

```sh
# Download the powershell '.tar.gz' archive
curl -L -o /tmp/powershell.tar.gz https://github.com/PowerShell/PowerShell/releases/download/v6.0.2/powershell-6.0.2-osx-x64.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /usr/local/microsoft/powershell/6.0.2

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /usr/local/microsoft/powershell/6.0.2

# Set execute permissions
sudo chmod +x /usr/local/microsoft/powershell/6.0.2/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /usr/local/microsoft/powershell/6.0.2/pwsh /usr/local/bin/pwsh
```

## <a name="uninstalling-powershell-core"></a><span data-ttu-id="5434c-138">Удаление PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="5434c-138">Uninstalling PowerShell Core</span></span>

<span data-ttu-id="5434c-139">Если вы установили PowerShell с помощью Homebrew, удаление осуществляется очень просто:</span><span class="sxs-lookup"><span data-stu-id="5434c-139">If you installed PowerShell with Homebrew, uninstallation is easy:</span></span>

```sh
brew cask uninstall powershell
```

<span data-ttu-id="5434c-140">Если вы установили PowerShell с помощью прямого скачивания, PowerShell нужно удалить вручную:</span><span class="sxs-lookup"><span data-stu-id="5434c-140">If you installed PowerShell via direct download, PowerShell must be removed manually:</span></span>

```sh
sudo rm -rf /usr/local/bin/pwsh /usr/local/microsoft/powershell
```

<span data-ttu-id="5434c-141">Чтобы удалить дополнительные пути PowerShell, ознакомьтесь с разделом [пути][] этой статьи, и удалите необходимые пути с помощью команды `sudo rm`.</span><span class="sxs-lookup"><span data-stu-id="5434c-141">To remove the additional PowerShell paths, please see the [paths][] section in this document and remove the desired the paths using `sudo rm`.</span></span>

> [!NOTE]
> <span data-ttu-id="5434c-142">Это не требуется в случае установки с помощью Homebrew.</span><span class="sxs-lookup"><span data-stu-id="5434c-142">This is not necessary if you installed with Homebrew.</span></span>

[пути]:#paths
[paths]:#paths

## <a name="paths"></a><span data-ttu-id="5434c-144">Пути</span><span class="sxs-lookup"><span data-stu-id="5434c-144">Paths</span></span>

* <span data-ttu-id="5434c-145">`$PSHOME` имеет значение `/usr/local/microsoft/powershell/6.0.2/`.</span><span class="sxs-lookup"><span data-stu-id="5434c-145">`$PSHOME` is `/usr/local/microsoft/powershell/6.0.2/`</span></span>
* <span data-ttu-id="5434c-146">Профили пользователей будут считаны из `~/.config/powershell/profile.ps1`.</span><span class="sxs-lookup"><span data-stu-id="5434c-146">User profiles will be read from `~/.config/powershell/profile.ps1`</span></span>
* <span data-ttu-id="5434c-147">Профили по умолчанию будут считаны из `$PSHOME/profile.ps1`.</span><span class="sxs-lookup"><span data-stu-id="5434c-147">Default profiles will be read from `$PSHOME/profile.ps1`</span></span>
* <span data-ttu-id="5434c-148">Модули пользователей будут считаны из `~/.local/share/powershell/Modules`.</span><span class="sxs-lookup"><span data-stu-id="5434c-148">User modules will be read from `~/.local/share/powershell/Modules`</span></span>
* <span data-ttu-id="5434c-149">Общие модули будут считаны из `/usr/local/share/powershell/Modules`.</span><span class="sxs-lookup"><span data-stu-id="5434c-149">Shared modules will be read from `/usr/local/share/powershell/Modules`</span></span>
* <span data-ttu-id="5434c-150">Модули по умолчанию будут считаны из `$PSHOME/Modules`.</span><span class="sxs-lookup"><span data-stu-id="5434c-150">Default modules will be read from `$PSHOME/Modules`</span></span>
* <span data-ttu-id="5434c-151">Журнал PSReadline будет записан в `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`.</span><span class="sxs-lookup"><span data-stu-id="5434c-151">PSReadline history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="5434c-152">Профили учитывают конфигурацию PowerShell для отдельных узлов.</span><span class="sxs-lookup"><span data-stu-id="5434c-152">The profiles respect PowerShell's per-host configuration.</span></span>
<span data-ttu-id="5434c-153">Поэтому профили конкретных узлов по умолчанию находятся в `Microsoft.PowerShell_profile.ps1` в тех же расположениях.</span><span class="sxs-lookup"><span data-stu-id="5434c-153">So the default host-specific profiles exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="5434c-154">PowerShell отвечает требованиям [спецификации каталога размещения файлов, связанных со средой настольной графической среды (X-сервера), стандартизированного XDG (X Desktop Group)][xdg-bds] в macOS.</span><span class="sxs-lookup"><span data-stu-id="5434c-154">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on macOS.</span></span>

<span data-ttu-id="5434c-155">Так как macOS является развитием BSD, необходимо использовать префикс `/usr/local` вместо `/opt`.</span><span class="sxs-lookup"><span data-stu-id="5434c-155">Because macOS is a derivation of BSD, the prefix `/usr/local` is used instead of `/opt`.</span></span>
<span data-ttu-id="5434c-156">Таким образом, `$PSHOME` имеет значение `/usr/local/microsoft/powershell/6.0.2/`, а символьная ссылка размещается в `/usr/local/bin/pwsh`.</span><span class="sxs-lookup"><span data-stu-id="5434c-156">Thus, `$PSHOME` is `/usr/local/microsoft/powershell/6.0.2/`, and the symlink is placed at `/usr/local/bin/pwsh`.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5434c-157">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="5434c-157">Additional Resources</span></span>

* <span data-ttu-id="5434c-158">[Homebrew Web][brew]</span><span class="sxs-lookup"><span data-stu-id="5434c-158">[Homebrew Web][brew]</span></span>
* <span data-ttu-id="5434c-159">[Репозиторий Github Homebrew][GitHub]</span><span class="sxs-lookup"><span data-stu-id="5434c-159">[Homebrew Github Repository][GitHub]</span></span>
* <span data-ttu-id="5434c-160">[Homebrew-Cask][cask]</span><span class="sxs-lookup"><span data-stu-id="5434c-160">[Homebrew-Cask][cask]</span></span>


[brew]: http://brew.sh/
[GitHub]: https://github.com/Homebrew
[Cask]: https://github.com/Homebrew/homebrew-cask
[Выпуски]: https://github.com/PowerShell/PowerShell/releases/latest
[releases]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
