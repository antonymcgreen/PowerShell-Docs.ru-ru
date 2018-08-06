# <a name="installing-powershell-core-on-macos"></a><span data-ttu-id="61786-101">Установка PowerShell Core в macOS</span><span class="sxs-lookup"><span data-stu-id="61786-101">Installing PowerShell Core on macOS</span></span>

<span data-ttu-id="61786-102">PowerShell Core поддерживает macOS версии 10.12 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="61786-102">PowerShell Core supports macOS 10.12 and higher.</span></span>
<span data-ttu-id="61786-103">Все пакеты доступны на нашей странице [Выпуски][] GitHub.</span><span class="sxs-lookup"><span data-stu-id="61786-103">All packages are available on our GitHub [releases][] page.</span></span>
<span data-ttu-id="61786-104">После установки пакета запустите `pwsh` из терминала.</span><span class="sxs-lookup"><span data-stu-id="61786-104">Once the package is installed, run `pwsh` from a terminal.</span></span>

### <a name="installation-via-homebrew-on-macos-1012"></a><span data-ttu-id="61786-105">Установка в macOS 10.12+ с помощью Homebrew</span><span class="sxs-lookup"><span data-stu-id="61786-105">Installation via Homebrew on macOS 10.12+</span></span>

<span data-ttu-id="61786-106">[Homebrew][brew] является предпочтительным диспетчером пакетов для macOS.</span><span class="sxs-lookup"><span data-stu-id="61786-106">[Homebrew][brew] is the preferred package manager for macOS.</span></span>
<span data-ttu-id="61786-107">В окне терминала введите `brew` для запуска Homebrew.</span><span class="sxs-lookup"><span data-stu-id="61786-107">From a terminal window, type `brew` to run Homebrew.</span></span>  <span data-ttu-id="61786-108">Если команда `brew` не найдена, нужно установить Homebrew по [соответствующим инструкциям][brew].</span><span class="sxs-lookup"><span data-stu-id="61786-108">If the `brew` command is not found, you need to install Homebrew following [their instructions][brew].</span></span>

> [!NOTE]
> <span data-ttu-id="61786-109">Если вы уже установили Homebrew, настоятельно рекомендуется выполнить команды brew update-reset и brew update.</span><span class="sxs-lookup"><span data-stu-id="61786-109">If you installed Homebrew in the past, it's always a good idea to run 'brew update-reset' && 'brew update'.</span></span>
```sh
brew update-reset
brew update
```

> <span data-ttu-id="61786-110">Для более старых версий Homebrew использовалось касание caskroom/cask. Сейчас вместо этого используется homebrew/cask.</span><span class="sxs-lookup"><span data-stu-id="61786-110">Older versions of Homebrew used the tap 'caskroom/cask', which has been deprecated, and migrated into 'homebrew/cask'.</span></span>  <span data-ttu-id="61786-111">Дополнительные сведения см. в справочнике по [Homebrew-cask][cask].</span><span class="sxs-lookup"><span data-stu-id="61786-111">More information can be found at [Homebrew-cask][cask].</span></span> <span data-ttu-id="61786-112">Используйте команду brew tap, чтобы получить список текущих касаний.</span><span class="sxs-lookup"><span data-stu-id="61786-112">Use the 'brew tap' command to list your current taps.</span></span>  <span data-ttu-id="61786-113">Если вы видите caskroom/cask, можно использовать brew-update, чтобы выполнить перенос касаний в Homebrew.</span><span class="sxs-lookup"><span data-stu-id="61786-113">If you see 'caskroom/cask' you can use 'brew update' to have Homebrew migrate the taps.</span></span>

```sh
brew tap
brew update
```

<span data-ttu-id="61786-114">После установки или обновления Homebrew установка PowerShell не вызывает проблем.</span><span class="sxs-lookup"><span data-stu-id="61786-114">Once you've installed/updated Homebrew, installing PowerShell is easy.</span></span>

<span data-ttu-id="61786-115">Чтобы установить PowerShell:</span><span class="sxs-lookup"><span data-stu-id="61786-115">To install PowerShell:</span></span>

```sh
brew cask install powershell
```

<span data-ttu-id="61786-116">И наконец, убедитесь, что установка прошла без ошибок.</span><span class="sxs-lookup"><span data-stu-id="61786-116">Finally, verify that your install is working properly:</span></span>

```sh
pwsh
```

<span data-ttu-id="61786-117">Чтобы выйти из PowerShell и вернуться в bash, используйте команду exit.</span><span class="sxs-lookup"><span data-stu-id="61786-117">To exit PowerShell, and return to bash, use the 'exit' command.</span></span> 
```sh
exit
```

<span data-ttu-id="61786-118">После выпуска новых версий PowerShell просто обновите формулы Homebrew и PowerShell:</span><span class="sxs-lookup"><span data-stu-id="61786-118">When new versions of PowerShell are released, simply update Homebrew's formulae and upgrade PowerShell:</span></span>

```sh
brew update
brew cask upgrade powershell
```

> [!NOTE]
> <span data-ttu-id="61786-119">Приведенные выше команды можно вызвать с узла PowerShell (pwsh), но затем потребуется выйти из оболочки PowerShell и перезапустить ее, чтобы завершить обновление и обновить значения в таблице $PSVersionTable.</span><span class="sxs-lookup"><span data-stu-id="61786-119">The commands above can be called from within a PowerShell (pwsh) host, but then the PowerShell shell must be exited and restarted to complete the upgrade and refresh the values shown in $PSVersionTable.</span></span>

### <a name="installing-preview-via-homebrew-on-macos-1012"></a><span data-ttu-id="61786-120">Установка предварительной версии в macOS 10.12+ с помощью Homebrew</span><span class="sxs-lookup"><span data-stu-id="61786-120">Installing Preview via Homebrew on macOS 10.12+</span></span>

<span data-ttu-id="61786-121">[Homebrew][brew] является предпочтительным диспетчером пакетов для macOS.</span><span class="sxs-lookup"><span data-stu-id="61786-121">[Homebrew][brew] is the preferred package manager for macOS.</span></span>
<span data-ttu-id="61786-122">В окне терминала введите `brew` для запуска Homebrew.</span><span class="sxs-lookup"><span data-stu-id="61786-122">From a terminal window, type `brew` to run Homebrew.</span></span>  <span data-ttu-id="61786-123">Если команда `brew` не найдена, нужно установить Homebrew по [соответствующим инструкциям][brew].</span><span class="sxs-lookup"><span data-stu-id="61786-123">If the `brew` command is not found, you need to install Homebrew following [their instructions][brew].</span></span>

> [!NOTE]
> <span data-ttu-id="61786-124">Если вы уже установили Homebrew, настоятельно рекомендуется выполнить команды brew update-reset и brew update.</span><span class="sxs-lookup"><span data-stu-id="61786-124">If you installed Homebrew in the past, it's always a good idea to run 'brew update-reset' && 'brew update'.</span></span>
```sh
brew update-reset
brew update
```

<span data-ttu-id="61786-125">После этого коснитесь репозитория `versions` casks, чтобы получить пакет предварительной версии:</span><span class="sxs-lookup"><span data-stu-id="61786-125">Then, you must tap the `versions` casks repository to get the preview package:</span></span>

```sh
brew tap homebrew/cask-versions
```

<span data-ttu-id="61786-126">Чтобы установить предварительную версию PowerShell:</span><span class="sxs-lookup"><span data-stu-id="61786-126">To install PowerShell Preview:</span></span>

```sh
brew cask install powershell-preview
```

<span data-ttu-id="61786-127">И наконец, убедитесь, что установка прошла без ошибок.</span><span class="sxs-lookup"><span data-stu-id="61786-127">Finally, verify that your install is working properly:</span></span>

```sh
pwsh-preview
```

<span data-ttu-id="61786-128">После выпуска новых версий PowerShell просто обновите формулы Homebrew и предварительную версию PowerShell:</span><span class="sxs-lookup"><span data-stu-id="61786-128">When new versions of PowerShell are released, simply update Homebrew's formulae and upgrade PowerShell Preview:</span></span>

```sh
brew update
brew cask upgrade powershell-preview
```

> [!NOTE]
> <span data-ttu-id="61786-129">Приведенные выше команды можно вызвать с узла PowerShell (pwsh), но затем потребуется выйти из оболочки PowerShell и перезапустить ее, чтобы завершить обновление и обновить значения в таблице $PSVersionTable.</span><span class="sxs-lookup"><span data-stu-id="61786-129">The commands above can be called from within a PowerShell (pwsh) host, but then the PowerShell shell must be exited and restarted to complete the upgrade and refresh the values shown in $PSVersionTable.</span></span>

### <a name="installation-via-direct-download"></a><span data-ttu-id="61786-130">Установка с помощью прямого скачивания</span><span class="sxs-lookup"><span data-stu-id="61786-130">Installation via Direct Download</span></span>

<span data-ttu-id="61786-131">Для компьютера с macOS пакет PKG `powershell-6.0.2-osx.10.12-x64.pkg` можно загрузить на странице [Выпуски][].</span><span class="sxs-lookup"><span data-stu-id="61786-131">Download the PKG package `powershell-6.0.2-osx.10.12-x64.pkg` from the [releases][] page onto your macOS machine.</span></span>

<span data-ttu-id="61786-132">Дважды щелкните файл и следуйте инструкциям на экране либо установите его из командной строки:</span><span class="sxs-lookup"><span data-stu-id="61786-132">You can double-click the file and follow the prompts, or install it from the terminal:</span></span>

```sh
sudo installer -pkg powershell-6.0.2-osx.10.12-x64.pkg -target /
```

## <a name="binary-archives"></a><span data-ttu-id="61786-133">Архивы двоичных файлов</span><span class="sxs-lookup"><span data-stu-id="61786-133">Binary Archives</span></span>

<span data-ttu-id="61786-134">Для поддержки расширенных сценариев развертывания на платформах macOS и Linux доступны архивы двоичных файлов PowerShell `tar.gz`.</span><span class="sxs-lookup"><span data-stu-id="61786-134">PowerShell binary `tar.gz` archives are provided for macOS and Linux platforms to enable advanced deployment scenarios.</span></span>

### <a name="installing-binary-archives-on-macos"></a><span data-ttu-id="61786-135">Установка архивов двоичных файлов в macOS</span><span class="sxs-lookup"><span data-stu-id="61786-135">Installing binary archives on macOS</span></span>

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

## <a name="uninstalling-powershell-core"></a><span data-ttu-id="61786-136">Удаление PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="61786-136">Uninstalling PowerShell Core</span></span>

<span data-ttu-id="61786-137">Если вы установили PowerShell с помощью Homebrew, удаление осуществляется очень просто:</span><span class="sxs-lookup"><span data-stu-id="61786-137">If you installed PowerShell with Homebrew, uninstallation is easy:</span></span>

```sh
brew cask uninstall powershell
```

<span data-ttu-id="61786-138">Если вы установили PowerShell с помощью прямого скачивания, PowerShell нужно удалить вручную:</span><span class="sxs-lookup"><span data-stu-id="61786-138">If you installed PowerShell via direct download, PowerShell must be removed manually:</span></span>

```sh
sudo rm -rf /usr/local/bin/pwsh /usr/local/microsoft/powershell
```

<span data-ttu-id="61786-139">Чтобы удалить дополнительные пути PowerShell, ознакомьтесь с разделом [пути][] этой статьи, и удалите необходимые пути с помощью команды `sudo rm`.</span><span class="sxs-lookup"><span data-stu-id="61786-139">To remove the additional PowerShell paths, please see the [paths][] section in this document and remove the desired the paths using `sudo rm`.</span></span>

> [!NOTE]
> <span data-ttu-id="61786-140">Это не требуется в случае установки с помощью Homebrew.</span><span class="sxs-lookup"><span data-stu-id="61786-140">This is not necessary if you installed with Homebrew.</span></span>

[пути]:#paths
[paths]:#paths

## <a name="paths"></a><span data-ttu-id="61786-142">Пути</span><span class="sxs-lookup"><span data-stu-id="61786-142">Paths</span></span>

* <span data-ttu-id="61786-143">`$PSHOME` имеет значение `/usr/local/microsoft/powershell/6.0.2/`.</span><span class="sxs-lookup"><span data-stu-id="61786-143">`$PSHOME` is `/usr/local/microsoft/powershell/6.0.2/`</span></span>
* <span data-ttu-id="61786-144">Профили пользователей будут считаны из `~/.config/powershell/profile.ps1`.</span><span class="sxs-lookup"><span data-stu-id="61786-144">User profiles will be read from `~/.config/powershell/profile.ps1`</span></span>
* <span data-ttu-id="61786-145">Профили по умолчанию будут считаны из `$PSHOME/profile.ps1`.</span><span class="sxs-lookup"><span data-stu-id="61786-145">Default profiles will be read from `$PSHOME/profile.ps1`</span></span>
* <span data-ttu-id="61786-146">Модули пользователей будут считаны из `~/.local/share/powershell/Modules`.</span><span class="sxs-lookup"><span data-stu-id="61786-146">User modules will be read from `~/.local/share/powershell/Modules`</span></span>
* <span data-ttu-id="61786-147">Общие модули будут считаны из `/usr/local/share/powershell/Modules`.</span><span class="sxs-lookup"><span data-stu-id="61786-147">Shared modules will be read from `/usr/local/share/powershell/Modules`</span></span>
* <span data-ttu-id="61786-148">Модули по умолчанию будут считаны из `$PSHOME/Modules`.</span><span class="sxs-lookup"><span data-stu-id="61786-148">Default modules will be read from `$PSHOME/Modules`</span></span>
* <span data-ttu-id="61786-149">Журнал PSReadline будет записан в `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`.</span><span class="sxs-lookup"><span data-stu-id="61786-149">PSReadline history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="61786-150">Профили учитывают конфигурацию PowerShell для отдельных узлов.</span><span class="sxs-lookup"><span data-stu-id="61786-150">The profiles respect PowerShell's per-host configuration.</span></span>
<span data-ttu-id="61786-151">Поэтому профили конкретных узлов по умолчанию находятся в `Microsoft.PowerShell_profile.ps1` в тех же расположениях.</span><span class="sxs-lookup"><span data-stu-id="61786-151">So the default host-specific profiles exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="61786-152">PowerShell отвечает требованиям [спецификации каталога размещения файлов, связанных со средой настольной графической среды (X-сервера), стандартизированного XDG (X Desktop Group)][xdg-bds] в macOS.</span><span class="sxs-lookup"><span data-stu-id="61786-152">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on macOS.</span></span>

<span data-ttu-id="61786-153">Так как macOS является развитием BSD, необходимо использовать префикс `/usr/local` вместо `/opt`.</span><span class="sxs-lookup"><span data-stu-id="61786-153">Because macOS is a derivation of BSD, the prefix `/usr/local` is used instead of `/opt`.</span></span>
<span data-ttu-id="61786-154">Таким образом, `$PSHOME` имеет значение `/usr/local/microsoft/powershell/6.0.2/`, а символьная ссылка размещается в `/usr/local/bin/pwsh`.</span><span class="sxs-lookup"><span data-stu-id="61786-154">Thus, `$PSHOME` is `/usr/local/microsoft/powershell/6.0.2/`, and the symlink is placed at `/usr/local/bin/pwsh`.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="61786-155">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="61786-155">Additional Resources</span></span>

* <span data-ttu-id="61786-156">[Homebrew Web][brew]</span><span class="sxs-lookup"><span data-stu-id="61786-156">[Homebrew Web][brew]</span></span>
* <span data-ttu-id="61786-157">[Репозиторий Github Homebrew][GitHub]</span><span class="sxs-lookup"><span data-stu-id="61786-157">[Homebrew Github Repository][GitHub]</span></span>
* <span data-ttu-id="61786-158">[Homebrew-Cask][cask]</span><span class="sxs-lookup"><span data-stu-id="61786-158">[Homebrew-Cask][cask]</span></span>


[brew]: http://brew.sh/
[GitHub]: https://github.com/Homebrew
[Cask]: https://github.com/Homebrew/homebrew-cask
[Выпуски]: https://github.com/PowerShell/PowerShell/releases/latest
[releases]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
