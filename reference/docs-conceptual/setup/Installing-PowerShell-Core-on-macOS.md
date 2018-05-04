# <a name="installing-powershell-core-on-macos"></a><span data-ttu-id="db851-101">Установка PowerShell Core в macOS</span><span class="sxs-lookup"><span data-stu-id="db851-101">Installing PowerShell Core on macOS</span></span>

<span data-ttu-id="db851-102">PowerShell Core поддерживает macOS версии 10.12 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="db851-102">PowerShell Core supports macOS 10.12 and higher.</span></span>
<span data-ttu-id="db851-103">Все пакеты доступны на нашей странице [выпусков][] GitHub.</span><span class="sxs-lookup"><span data-stu-id="db851-103">All packages are available on our GitHub [releases][] page.</span></span>
<span data-ttu-id="db851-104">После установки пакета запустите `pwsh` из терминала.</span><span class="sxs-lookup"><span data-stu-id="db851-104">Once the package is installed, run `pwsh` from a terminal.</span></span>

### <a name="installation-via-homebrew-on-macos-1012"></a><span data-ttu-id="db851-105">Установка в macOS 10.12 с помощью Homebrew</span><span class="sxs-lookup"><span data-stu-id="db851-105">Installation via Homebrew on macOS 10.12</span></span>

<span data-ttu-id="db851-106">[Homebrew][brew] является предпочтительным диспетчером пакетов для macOS.</span><span class="sxs-lookup"><span data-stu-id="db851-106">[Homebrew][brew] is the preferred package manager for macOS.</span></span>
<span data-ttu-id="db851-107">Если команда `brew` не найдена, нужно установить Homebrew по [соответствующим инструкциям][brew].</span><span class="sxs-lookup"><span data-stu-id="db851-107">If the `brew` command is not found, you need to install Homebrew following [their instructions][brew].</span></span>

<span data-ttu-id="db851-108">После установки Homebrew установка PowerShell не вызывает проблем.</span><span class="sxs-lookup"><span data-stu-id="db851-108">Once you've installed Homebrew, installing PowerShell is easy.</span></span>
<span data-ttu-id="db851-109">Сначала установите [Homebrew-Cask][cask], чтобы можно было установить дополнительные пакеты:</span><span class="sxs-lookup"><span data-stu-id="db851-109">First, install [Homebrew-Cask][cask], so you can install more packages:</span></span>

```sh
brew tap caskroom/cask
```

<span data-ttu-id="db851-110">Теперь можно установить PowerShell:</span><span class="sxs-lookup"><span data-stu-id="db851-110">Now, you can install PowerShell:</span></span>

```sh
brew cask install powershell
```

<span data-ttu-id="db851-111">И наконец, убедитесь, что установка прошла без ошибок.</span><span class="sxs-lookup"><span data-stu-id="db851-111">Finally, verify that your install is working properly:</span></span>

```sh
pwsh
```

<span data-ttu-id="db851-112">После выпуска новых версий PowerShell просто обновите формулы Homebrew и PowerShell:</span><span class="sxs-lookup"><span data-stu-id="db851-112">When new versions of PowerShell are released, simply update Homebrew's formulae and upgrade PowerShell:</span></span>

```sh
brew update
brew cask upgrade powershell
```

> [!NOTE]
> <span data-ttu-id="db851-113">Команду, указанную выше, можно вызвать на узле PowerShell (pwsh), но для этого необходимо завершить его обновление. Что в свою очередь будет сделано, когда вы выйдете из PowerShell и перезапустите его.</span><span class="sxs-lookup"><span data-stu-id="db851-113">The commands above can be called from within a PowerShell (pwsh) host, but then the PowerShell shell must be exited and restarted to complete the upgrade.</span></span>
> <span data-ttu-id="db851-114">Обновите значения, которые отображаются в $PSVersionTable.</span><span class="sxs-lookup"><span data-stu-id="db851-114">and refresh the values shown in $PSVersionTable.</span></span>

[brew]: http://brew.sh/
[cask]: https://caskroom.github.io/

### <a name="installation-via-direct-download"></a><span data-ttu-id="db851-115">Установка с помощью прямого скачивания</span><span class="sxs-lookup"><span data-stu-id="db851-115">Installation via Direct Download</span></span>

<span data-ttu-id="db851-116">Для компьютера с macOS пакет PKG `powershell-6.0.2-osx.10.12-x64.pkg` можно загрузить на странице [выпусков][].</span><span class="sxs-lookup"><span data-stu-id="db851-116">Download the PKG package `powershell-6.0.2-osx.10.12-x64.pkg` from the [releases][] page onto your macOS machine.</span></span>

<span data-ttu-id="db851-117">Дважды щелкните файл и следуйте инструкциям на экране либо установите его из командной строки:</span><span class="sxs-lookup"><span data-stu-id="db851-117">You can double-click the file and follow the prompts, or install it from the terminal:</span></span>

```sh
sudo installer -pkg powershell-6.0.2-osx.10.12-x64.pkg -target /
```

## <a name="binary-archives"></a><span data-ttu-id="db851-118">Архивы двоичных файлов</span><span class="sxs-lookup"><span data-stu-id="db851-118">Binary Archives</span></span>

<span data-ttu-id="db851-119">Для поддержки расширенных сценариев развертывания на платформах macOS и Linux доступны архивы двоичных файлов PowerShell `tar.gz`.</span><span class="sxs-lookup"><span data-stu-id="db851-119">PowerShell binary `tar.gz` archives are provided for macOS and Linux platforms to enable advanced deployment scenarios.</span></span>

### <a name="installing-binary-archives-on-macos"></a><span data-ttu-id="db851-120">Установка архивов двоичных файлов в macOS</span><span class="sxs-lookup"><span data-stu-id="db851-120">Installing binary archives on macOS</span></span>

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

## <a name="uninstalling-powershell-core"></a><span data-ttu-id="db851-121">Удаление PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="db851-121">Uninstalling PowerShell Core</span></span>

<span data-ttu-id="db851-122">Если вы установили PowerShell с помощью Homebrew, удаление осуществляется очень просто:</span><span class="sxs-lookup"><span data-stu-id="db851-122">If you installed PowerShell with Homebrew, uninstallation is easy:</span></span>

```sh
brew cask uninstall powershell
```

<span data-ttu-id="db851-123">Если вы установили PowerShell с помощью прямого скачивания, PowerShell нужно удалить вручную:</span><span class="sxs-lookup"><span data-stu-id="db851-123">If you installed PowerShell via direct download, PowerShell must be removed manually:</span></span>

```sh
sudo rm -rf /usr/local/bin/pwsh /usr/local/microsoft/powershell
```

<span data-ttu-id="db851-124">Чтобы удалить дополнительные пути PowerShell, ознакомьтесь с разделом [пути][] этой статьи, и удалите необходимые пути с помощью команды `sudo rm`.</span><span class="sxs-lookup"><span data-stu-id="db851-124">To remove the additional PowerShell paths, please see the [paths][] section in this document and remove the desired the paths using `sudo rm`.</span></span>

> [!NOTE]
> <span data-ttu-id="db851-125">Это не требуется в случае установки с помощью Homebrew.</span><span class="sxs-lookup"><span data-stu-id="db851-125">This is not necessary if you installed with Homebrew.</span></span>

[пути]:#paths
[paths]:#paths

## <a name="paths"></a><span data-ttu-id="db851-127">Пути</span><span class="sxs-lookup"><span data-stu-id="db851-127">Paths</span></span>

* <span data-ttu-id="db851-128">`$PSHOME` имеет значение `/opt/microsoft/powershell/6.0.0/`.</span><span class="sxs-lookup"><span data-stu-id="db851-128">`$PSHOME` is `/opt/microsoft/powershell/6.0.0/`</span></span>
* <span data-ttu-id="db851-129">Профили пользователей будут считаны из `~/.config/powershell/profile.ps1`.</span><span class="sxs-lookup"><span data-stu-id="db851-129">User profiles will be read from `~/.config/powershell/profile.ps1`</span></span>
* <span data-ttu-id="db851-130">Профили по умолчанию будут считаны из `$PSHOME/profile.ps1`.</span><span class="sxs-lookup"><span data-stu-id="db851-130">Default profiles will be read from `$PSHOME/profile.ps1`</span></span>
* <span data-ttu-id="db851-131">Модули пользователей будут считаны из `~/.local/share/powershell/Modules`.</span><span class="sxs-lookup"><span data-stu-id="db851-131">User modules will be read from `~/.local/share/powershell/Modules`</span></span>
* <span data-ttu-id="db851-132">Общие модули будут считаны из `/usr/local/share/powershell/Modules`.</span><span class="sxs-lookup"><span data-stu-id="db851-132">Shared modules will be read from `/usr/local/share/powershell/Modules`</span></span>
* <span data-ttu-id="db851-133">Модули по умолчанию будут считаны из `$PSHOME/Modules`.</span><span class="sxs-lookup"><span data-stu-id="db851-133">Default modules will be read from `$PSHOME/Modules`</span></span>
* <span data-ttu-id="db851-134">Журнал PSReadline будет записан в `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`.</span><span class="sxs-lookup"><span data-stu-id="db851-134">PSReadline history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="db851-135">Профили учитывают конфигурацию PowerShell для отдельных узлов.</span><span class="sxs-lookup"><span data-stu-id="db851-135">The profiles respect PowerShell's per-host configuration.</span></span>
<span data-ttu-id="db851-136">Поэтому профили конкретных узлов по умолчанию находятся в `Microsoft.PowerShell_profile.ps1` в тех же расположениях.</span><span class="sxs-lookup"><span data-stu-id="db851-136">So the default host-specific profiles exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="db851-137">PowerShell отвечает требованиям [спецификации каталога размещения файлов, связанных со средой настольной графической среды (X-сервера), стандартизированного XDG (X Desktop Group)][xdg-bds] в macOS.</span><span class="sxs-lookup"><span data-stu-id="db851-137">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on macOS.</span></span>

<span data-ttu-id="db851-138">Так как macOS является развитием BSD, необходимо использовать префикс `/usr/local` вместо `/opt`.</span><span class="sxs-lookup"><span data-stu-id="db851-138">Because macOS is a derivation of BSD, the prefix `/usr/local` is used instead of `/opt`.</span></span>
<span data-ttu-id="db851-139">Таким образом, `$PSHOME` имеет значение `/usr/local/microsoft/powershell/6.0.0/`, а символьная ссылка размещается в `/usr/local/bin/pwsh`.</span><span class="sxs-lookup"><span data-stu-id="db851-139">Thus, `$PSHOME` is `/usr/local/microsoft/powershell/6.0.0/`, and the symlink is placed at `/usr/local/bin/pwsh`.</span></span>

[выпусков]: https://github.com/PowerShell/PowerShell/releases/latest
[releases]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
