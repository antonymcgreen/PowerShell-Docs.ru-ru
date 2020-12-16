---
title: Установка PowerShell в macOS
description: Сведения об установке PowerShell в macOS
ms.date: 11/11/2020
ms.openlocfilehash: 1ce96e993d8fc87edd93fca840ede250d5632577
ms.sourcegitcommit: 3ab2951a5460a39ca5fb3d25ffcb1d8868f4e011
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2020
ms.locfileid: "96535106"
---
# <a name="installing-powershell-on-macos"></a><span data-ttu-id="facbc-103">Установка PowerShell в macOS</span><span class="sxs-lookup"><span data-stu-id="facbc-103">Installing PowerShell on macOS</span></span>

<span data-ttu-id="facbc-104">Для работы с PowerShell 7.0 или более поздней версии требуется macOS 10.13 и выше.</span><span class="sxs-lookup"><span data-stu-id="facbc-104">PowerShell 7.0 or higher require macOS 10.13 and higher.</span></span> <span data-ttu-id="facbc-105">Все пакеты доступны на нашей странице [выпусками][] GitHub.</span><span class="sxs-lookup"><span data-stu-id="facbc-105">All packages are available on our GitHub [releases][] page.</span></span> <span data-ttu-id="facbc-106">После установки пакета запустите `pwsh` из терминала.</span><span class="sxs-lookup"><span data-stu-id="facbc-106">After the package is installed, run `pwsh` from a terminal.</span></span>

> [!NOTE]
> <span data-ttu-id="facbc-107">PowerShell 7.1 является обновлением на месте, при установке которого PowerShell Core версий 6.x и 7.0 удаляется.</span><span class="sxs-lookup"><span data-stu-id="facbc-107">PowerShell 7.1 is an in-place upgrade that removes PowerShell Core 6.x and 7.0.</span></span>
>
> <span data-ttu-id="facbc-108">Папка `/usr/local/microsoft/powershell/6` заменяется на `/usr/local/microsoft/powershell/7`.</span><span class="sxs-lookup"><span data-stu-id="facbc-108">The `/usr/local/microsoft/powershell/6` folder is replaced by `/usr/local/microsoft/powershell/7`.</span></span>
>
> <span data-ttu-id="facbc-109">Если вам нужно запустить более раннюю версию PowerShell Core параллельно с PowerShell 7.1, установите нужную версию, используя [архив двоичных файлов](#binary-archives).</span><span class="sxs-lookup"><span data-stu-id="facbc-109">If you need to run and older version of PowerShell core side-by-side with PowerShell 7.1, install the version you want using the [binary archive](#binary-archives) method.</span></span>

<span data-ttu-id="facbc-110">Существует несколько способов установки PowerShell в macOS.</span><span class="sxs-lookup"><span data-stu-id="facbc-110">There are several ways to install PowerShell on macOS.</span></span> <span data-ttu-id="facbc-111">Выберите для этого один из следующих методов:</span><span class="sxs-lookup"><span data-stu-id="facbc-111">Choose one of the following methods:</span></span>

- <span data-ttu-id="facbc-112">Установка с помощью Homebrew.</span><span class="sxs-lookup"><span data-stu-id="facbc-112">Install using Homebrew.</span></span> <span data-ttu-id="facbc-113">Homebrew является предпочтительным диспетчером пакетов для macOS.</span><span class="sxs-lookup"><span data-stu-id="facbc-113">Homebrew is the preferred package manager for macOS.</span></span>
- <span data-ttu-id="facbc-114">Установка PowerShell через [Direct Download](#installation-via-direct-download)</span><span class="sxs-lookup"><span data-stu-id="facbc-114">Install PowerShell via [Direct Download](#installation-via-direct-download)</span></span>
- <span data-ttu-id="facbc-115">Установка из [архивов двоичных файлов](#binary-archives).</span><span class="sxs-lookup"><span data-stu-id="facbc-115">Install from [binary archives](#binary-archives).</span></span>

<span data-ttu-id="facbc-116">После установки PowerShell следует установить [OpenSSL](#installing-dependencies).</span><span class="sxs-lookup"><span data-stu-id="facbc-116">After installing PowerShell, you should install [OpenSSL](#installing-dependencies).</span></span> <span data-ttu-id="facbc-117">OpenSSL требуется для удаленного взаимодействия PowerShell и операций CIM.</span><span class="sxs-lookup"><span data-stu-id="facbc-117">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>

## <a name="installation-of-latest-stable-release-via-homebrew-on-macos-1013-or-higher"></a><span data-ttu-id="facbc-118">Установка последнего стабильного выпуска с помощью Homebrew в macOS 10.13 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="facbc-118">Installation of latest stable release via Homebrew on macOS 10.13 or higher</span></span>

<span data-ttu-id="facbc-119">Если команда `brew` не найдена, нужно установить Homebrew по [соответствующим инструкциям][brew].</span><span class="sxs-lookup"><span data-stu-id="facbc-119">If the `brew` command is not found, you need to install Homebrew following [their instructions][brew].</span></span>

<span data-ttu-id="facbc-120">Теперь можно установить PowerShell:</span><span class="sxs-lookup"><span data-stu-id="facbc-120">Now, you can install PowerShell:</span></span>

```sh
brew install --cask powershell
```

<span data-ttu-id="facbc-121">И наконец, убедитесь, что установка прошла без ошибок.</span><span class="sxs-lookup"><span data-stu-id="facbc-121">Finally, verify that your install is working properly:</span></span>

```sh
pwsh
```

<span data-ttu-id="facbc-122">После выпуска новых версий PowerShell обновите формулы Homebrew и PowerShell:</span><span class="sxs-lookup"><span data-stu-id="facbc-122">When new versions of PowerShell are released, update Homebrew's formulae and upgrade PowerShell:</span></span>

```sh
brew update
brew upgrade powershell --cask
```

> [!NOTE]
> <span data-ttu-id="facbc-123">Приведенные выше команды можно вызвать из узла PowerShell (pwsh), но затем потребуется выйти из оболочки PowerShell и перезапустить ее, чтобы завершить обновление и обновить значения в таблице `$PSVersionTable`.</span><span class="sxs-lookup"><span data-stu-id="facbc-123">The commands above can be called from within a PowerShell (pwsh) host, but then the PowerShell shell must be exited and restarted to complete the upgrade and refresh the values shown in `$PSVersionTable`.</span></span>

[brew]: https://brew.sh/

## <a name="installation-of-latest-preview-release-via-homebrew-on-macos-1013-or-higher"></a><span data-ttu-id="facbc-124">Установка последнего предварительного выпуска с помощью Homebrew в macOS 10.13 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="facbc-124">Installation of latest preview release via Homebrew on macOS 10.13 or higher</span></span>

<span data-ttu-id="facbc-125">После установки Homebrew можно установить PowerShell.</span><span class="sxs-lookup"><span data-stu-id="facbc-125">After you've installed Homebrew, you can install PowerShell.</span></span> <span data-ttu-id="facbc-126">Сначала установите пакет [Cask-Versions][cask-versions], который позволит устанавливать альтернативные версии Cask-пакетов.</span><span class="sxs-lookup"><span data-stu-id="facbc-126">First, install the [Cask-Versions][cask-versions] package that lets you install alternative versions of cask packages:</span></span>

```sh
brew tap homebrew/cask-versions
```

<span data-ttu-id="facbc-127">Теперь можно установить PowerShell:</span><span class="sxs-lookup"><span data-stu-id="facbc-127">Now, you can install PowerShell:</span></span>

```sh
brew install --cask powershell-preview
```

<span data-ttu-id="facbc-128">И наконец, убедитесь, что установка прошла без ошибок.</span><span class="sxs-lookup"><span data-stu-id="facbc-128">Finally, verify that your install is working properly:</span></span>

```sh
pwsh-preview
```

<span data-ttu-id="facbc-129">После выпуска новых версий PowerShell обновите формулы Homebrew и PowerShell:</span><span class="sxs-lookup"><span data-stu-id="facbc-129">When new versions of PowerShell are released, update Homebrew's formulae and upgrade PowerShell:</span></span>

```sh
brew update
brew upgrade powershell-preview --cask
```

> [!NOTE]
> <span data-ttu-id="facbc-130">Команду, указанную выше, можно вызвать на узле PowerShell (pwsh), но для этого необходимо завершить его обновление. Что в свою очередь будет сделано, когда вы выйдете из PowerShell и перезапустите его.</span><span class="sxs-lookup"><span data-stu-id="facbc-130">The commands above can be called from within a PowerShell (pwsh) host, but then the PowerShell shell must be exited and restarted to complete the upgrade.</span></span>
> <span data-ttu-id="facbc-131">Обновите значения, которые отображаются в `$PSVersionTable`.</span><span class="sxs-lookup"><span data-stu-id="facbc-131">and refresh the values shown in `$PSVersionTable`.</span></span>

<span data-ttu-id="facbc-132">Установка PowerShell с помощью метода tap Homebrew также поддерживается для стабильных версий и версий LTS.</span><span class="sxs-lookup"><span data-stu-id="facbc-132">Installing PowerShell using the Homebrew tap method is also supported for stable and LTS versions.</span></span>

```sh
brew install powershell/tap/powershell
```

<span data-ttu-id="facbc-133">Теперь можно проверить установку.</span><span class="sxs-lookup"><span data-stu-id="facbc-133">You can now verify your install</span></span>

```sh
pwsh
```

<span data-ttu-id="facbc-134">После выпуска новых версий PowerShell просто выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="facbc-134">When new versions of PowerShell are released, simply run the following command.</span></span>

```sh
brew upgrade powershell
```

> [!NOTE]
> <span data-ttu-id="facbc-135">Если вы используете метод cask или tap при обновлении до более новой версии PowerShell, используйте тот же метод, который применяли для первоначальной установки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="facbc-135">Whether you use the cask or the tap method, when updating to a newer version of PowerShell, use the same method you used to initially install PowerShell.</span></span> <span data-ttu-id="facbc-136">При использовании другого метода новый сеанс pwsh будет продолжать использовать старую версию PowerShell.</span><span class="sxs-lookup"><span data-stu-id="facbc-136">If you use a different method, opening a new pwsh session will continue to use the older version of PowerShell.</span></span>
>
> <span data-ttu-id="facbc-137">Если вы решите использовать разные методы, существуют способы исправить проблему с помощью [метода Homebrew link](https://docs.brew.sh/Manpage#link-ln-options-formula).</span><span class="sxs-lookup"><span data-stu-id="facbc-137">If you do decide to use different methods, there are ways to correct the issue using the [Homebrew link method](https://docs.brew.sh/Manpage#link-ln-options-formula).</span></span>

## <a name="installation-via-direct-download"></a><span data-ttu-id="facbc-138">Установка с помощью прямого скачивания</span><span class="sxs-lookup"><span data-stu-id="facbc-138">Installation via Direct Download</span></span>

<span data-ttu-id="facbc-139">Для компьютера с macOS пакет PKG `powershell-7.1.0-osx-x64.pkg` можно загрузить на странице [Выпуски][].</span><span class="sxs-lookup"><span data-stu-id="facbc-139">Download the PKG package `powershell-7.1.0-osx-x64.pkg` from the [releases][] page onto your macOS machine.</span></span>

<span data-ttu-id="facbc-140">Дважды щелкните файл и следуйте инструкциям на экране либо установите его из командной строки:</span><span class="sxs-lookup"><span data-stu-id="facbc-140">You can double-click the file and follow the prompts, or install it from the terminal:</span></span>

```sh
sudo installer -pkg powershell-7.1.0-osx-x64.pkg -target /
```

<span data-ttu-id="facbc-141">Установите [OpenSSL](#installing-dependencies).</span><span class="sxs-lookup"><span data-stu-id="facbc-141">Install [OpenSSL](#installing-dependencies).</span></span> <span data-ttu-id="facbc-142">OpenSSL требуется для удаленного взаимодействия PowerShell и операций CIM.</span><span class="sxs-lookup"><span data-stu-id="facbc-142">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>

## <a name="install-as-a-net-global-tool"></a><span data-ttu-id="facbc-143">Установка в качестве глобального средства .NET</span><span class="sxs-lookup"><span data-stu-id="facbc-143">Install as a .NET Global tool</span></span>

<span data-ttu-id="facbc-144">Если вы уже установили [пакет SDK для .NET Core](/dotnet/core/sdk), установите PowerShell как [глобальное средство .NET](/dotnet/core/tools/global-tools).</span><span class="sxs-lookup"><span data-stu-id="facbc-144">If you already have the [.NET Core SDK](/dotnet/core/sdk) installed, it's easy to install PowerShell as a [.NET Global tool](/dotnet/core/tools/global-tools).</span></span>

```
dotnet tool install --global PowerShell
```

<span data-ttu-id="facbc-145">Установщик инструмента dotnet добавляет `~/.dotnet/tools` в переменную среды `PATH`.</span><span class="sxs-lookup"><span data-stu-id="facbc-145">The dotnet tool installer adds `~/.dotnet/tools` to your `PATH` environment variable.</span></span> <span data-ttu-id="facbc-146">Но в выполняющейся оболочке отсутствует обновленная переменная `PATH`.</span><span class="sxs-lookup"><span data-stu-id="facbc-146">However, the currently running shell does not have the updated `PATH`.</span></span> <span data-ttu-id="facbc-147">Вы можете запустить PowerShell из новой оболочки, введя `pwsh`.</span><span class="sxs-lookup"><span data-stu-id="facbc-147">You should be able to start PowerShell from a new shell by typing `pwsh`.</span></span>

<span data-ttu-id="facbc-148">Установите [OpenSSL](#installing-dependencies).</span><span class="sxs-lookup"><span data-stu-id="facbc-148">Install [OpenSSL](#installing-dependencies).</span></span> <span data-ttu-id="facbc-149">OpenSSL требуется для удаленного взаимодействия PowerShell и операций CIM.</span><span class="sxs-lookup"><span data-stu-id="facbc-149">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>

## <a name="binary-archives"></a><span data-ttu-id="facbc-150">Архивы двоичных файлов</span><span class="sxs-lookup"><span data-stu-id="facbc-150">Binary Archives</span></span>

<span data-ttu-id="facbc-151">Для поддержки расширенных сценариев развертывания на платформе macOS доступны архивы `tar.gz` двоичных файлов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="facbc-151">PowerShell binary `tar.gz` archives are provided for the macOS platform to enable advanced deployment scenarios.</span></span> <span data-ttu-id="facbc-152">При установке с помощью этого метода необходимо также вручную установить все зависимости.</span><span class="sxs-lookup"><span data-stu-id="facbc-152">When you install using this method you must also manually install any dependencies.</span></span>

<span data-ttu-id="facbc-153">Установите [OpenSSL](#installing-dependencies).</span><span class="sxs-lookup"><span data-stu-id="facbc-153">Install [OpenSSL](#installing-dependencies).</span></span> <span data-ttu-id="facbc-154">OpenSSL требуется для удаленного взаимодействия PowerShell и операций CIM.</span><span class="sxs-lookup"><span data-stu-id="facbc-154">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>

### <a name="installing-binary-archives-on-macos"></a><span data-ttu-id="facbc-155">Установка архивов двоичных файлов в macOS</span><span class="sxs-lookup"><span data-stu-id="facbc-155">Installing binary archives on macOS</span></span>

```sh
# Download the powershell '.tar.gz' archive
curl -L -o /tmp/powershell.tar.gz https://github.com/PowerShell/PowerShell/releases/download/v7.1.0/powershell-7.1.0-osx-x64.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /usr/local/microsoft/powershell/7.1.0

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /usr/local/microsoft/powershell/7.1.0

# Set execute permissions
sudo chmod +x /usr/local/microsoft/powershell/7.1.0/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /usr/local/microsoft/powershell/7.1.0/pwsh /usr/local/bin/pwsh
```

## <a name="installing-dependencies"></a><span data-ttu-id="facbc-156">Установка зависимостей</span><span class="sxs-lookup"><span data-stu-id="facbc-156">Installing dependencies</span></span>

<span data-ttu-id="facbc-157">OpenSSL требуется для удаленного взаимодействия PowerShell и операций CIM.</span><span class="sxs-lookup"><span data-stu-id="facbc-157">OpenSSL is required for PowerShell remoting and CIM operations.</span></span> <span data-ttu-id="facbc-158">При необходимости вы можете установить OpenSSL с помощью MacPorts.</span><span class="sxs-lookup"><span data-stu-id="facbc-158">You can install OpenSSL via MacPorts if needed.</span></span>

> [!NOTE]
> <span data-ttu-id="facbc-159">MacPorts и Homebrew могут приводить к проблемам при совместном использовании в одной системе.</span><span class="sxs-lookup"><span data-stu-id="facbc-159">MacPorts and Homebrew can have problems when used to together on the same system.</span></span> <span data-ttu-id="facbc-160">Однако у Homebrew нет пакета для OpenSSL 1.0.</span><span class="sxs-lookup"><span data-stu-id="facbc-160">However, Homebrew does not have a package for OpenSSL 1.0.</span></span> <span data-ttu-id="facbc-161">Дополнительные сведения см. в разделе [Часто задаваемые вопросы о MacPorts](https://trac.macports.org/wiki/FAQ).</span><span class="sxs-lookup"><span data-stu-id="facbc-161">For more information, see the [MacPorts FAQ](https://trac.macports.org/wiki/FAQ).</span></span>

1. <span data-ttu-id="facbc-162">Установите средства командной строки Xcode.</span><span class="sxs-lookup"><span data-stu-id="facbc-162">Install the Xcode command-line tools.</span></span> <span data-ttu-id="facbc-163">Средства Xcode требуются для MacPorts.</span><span class="sxs-lookup"><span data-stu-id="facbc-163">The Xcode tools are required by MacPorts.</span></span>

   ```sh
   xcode-select --install
   ```

1. <span data-ttu-id="facbc-164">Установите MacPorts.</span><span class="sxs-lookup"><span data-stu-id="facbc-164">Install MacPorts.</span></span> <span data-ttu-id="facbc-165">Инструкции см. в [руководстве по установке](https://www.macports.org/install.php).</span><span class="sxs-lookup"><span data-stu-id="facbc-165">If you need instructions, refer to the [installation guide](https://www.macports.org/install.php).</span></span>
1. <span data-ttu-id="facbc-166">Обновите MacPorts, выполнив команду `sudo port selfupdate`.</span><span class="sxs-lookup"><span data-stu-id="facbc-166">Update MacPorts by running `sudo port selfupdate`.</span></span>
1. <span data-ttu-id="facbc-167">Обновите пакеты MacPorts, выполнив команду `sudo port upgrade outdated`.</span><span class="sxs-lookup"><span data-stu-id="facbc-167">Upgrade MacPorts packages by running `sudo port upgrade outdated`.</span></span>
1. <span data-ttu-id="facbc-168">Установите OpenSSL, запустив `sudo port install openssl10`.</span><span class="sxs-lookup"><span data-stu-id="facbc-168">Install OpenSSL by running `sudo port install openssl10`.</span></span>
1. <span data-ttu-id="facbc-169">Укажите ссылки на библиотеки, чтобы сделать их доступными для PowerShell:</span><span class="sxs-lookup"><span data-stu-id="facbc-169">Link the libraries to make them available to PowerShell:</span></span>

   ```sh
   sudo mkdir -p /usr/local/opt/openssl
   sudo ln -s /opt/local/lib/openssl-1.0 /usr/local/opt/openssl/lib
   ```

## <a name="uninstalling-powershell"></a><span data-ttu-id="facbc-170">Удаление PowerShell</span><span class="sxs-lookup"><span data-stu-id="facbc-170">Uninstalling PowerShell</span></span>

<span data-ttu-id="facbc-171">Если вы установили PowerShell с помощью Homebrew, используйте следующую команду для удаления:</span><span class="sxs-lookup"><span data-stu-id="facbc-171">If you installed PowerShell with Homebrew, use the following command to uninstall:</span></span>

```sh
brew cask uninstall powershell
```

<span data-ttu-id="facbc-172">Если вы установили PowerShell с помощью прямого скачивания, PowerShell нужно удалить вручную:</span><span class="sxs-lookup"><span data-stu-id="facbc-172">If you installed PowerShell via direct download, PowerShell must be removed manually:</span></span>

```sh
sudo rm -rf /usr/local/bin/pwsh /usr/local/microsoft/powershell
```

<span data-ttu-id="facbc-173">Чтобы удалить дополнительные пути PowerShell, ознакомьтесь с разделом [Пути](#paths) этой статьи, и удалите их с помощью команды `sudo rm`.</span><span class="sxs-lookup"><span data-stu-id="facbc-173">To remove the additional PowerShell paths, refer to the [paths](#paths) section in this document and remove the paths using `sudo rm`.</span></span>

> [!NOTE]
> <span data-ttu-id="facbc-174">Это не требуется в случае установки с помощью Homebrew.</span><span class="sxs-lookup"><span data-stu-id="facbc-174">This is not necessary if you installed with Homebrew.</span></span>

## <a name="paths"></a><span data-ttu-id="facbc-175">Пути</span><span class="sxs-lookup"><span data-stu-id="facbc-175">Paths</span></span>

- <span data-ttu-id="facbc-176">`$PSHOME` имеет значение `/usr/local/microsoft/powershell/7.1.0/`.</span><span class="sxs-lookup"><span data-stu-id="facbc-176">`$PSHOME` is `/usr/local/microsoft/powershell/7.1.0/`</span></span>
- <span data-ttu-id="facbc-177">Профили пользователей будут считаны из `~/.config/powershell/profile.ps1`.</span><span class="sxs-lookup"><span data-stu-id="facbc-177">User profiles will be read from `~/.config/powershell/profile.ps1`</span></span>
- <span data-ttu-id="facbc-178">Профили по умолчанию будут считаны из `$PSHOME/profile.ps1`.</span><span class="sxs-lookup"><span data-stu-id="facbc-178">Default profiles will be read from `$PSHOME/profile.ps1`</span></span>
- <span data-ttu-id="facbc-179">Модули пользователей будут считаны из `~/.local/share/powershell/Modules`.</span><span class="sxs-lookup"><span data-stu-id="facbc-179">User modules will be read from `~/.local/share/powershell/Modules`</span></span>
- <span data-ttu-id="facbc-180">Общие модули будут считаны из `/usr/local/share/powershell/Modules`.</span><span class="sxs-lookup"><span data-stu-id="facbc-180">Shared modules will be read from `/usr/local/share/powershell/Modules`</span></span>
- <span data-ttu-id="facbc-181">Модули по умолчанию будут считаны из `$PSHOME/Modules`.</span><span class="sxs-lookup"><span data-stu-id="facbc-181">Default modules will be read from `$PSHOME/Modules`</span></span>
- <span data-ttu-id="facbc-182">Журнал PSReadline будет записан в `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`.</span><span class="sxs-lookup"><span data-stu-id="facbc-182">PSReadline history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="facbc-183">Профили учитывают конфигурацию PowerShell для отдельных узлов.</span><span class="sxs-lookup"><span data-stu-id="facbc-183">The profiles respect PowerShell's per-host configuration.</span></span> <span data-ttu-id="facbc-184">Профиль узла по умолчанию находится в `Microsoft.PowerShell_profile.ps1` в тех же расположениях.</span><span class="sxs-lookup"><span data-stu-id="facbc-184">So the default host-specific profile exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="facbc-185">PowerShell отвечает требованиям [спецификации каталога размещения файлов, связанных со средой настольной графической среды (X-сервера), стандартизированного XDG (X Desktop Group)][xdg-bds] в macOS.</span><span class="sxs-lookup"><span data-stu-id="facbc-185">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on macOS.</span></span>

<span data-ttu-id="facbc-186">Так как macOS является развитием BSD, необходимо использовать префикс `/usr/local` вместо `/opt`.</span><span class="sxs-lookup"><span data-stu-id="facbc-186">Because macOS is a derivation of BSD, the prefix `/usr/local` is used instead of `/opt`.</span></span> <span data-ttu-id="facbc-187">Таким образом, `$PSHOME` имеет значение `/usr/local/microsoft/powershell/7.1.0/`, а символьная ссылка размещается в `/usr/local/bin/pwsh`.</span><span class="sxs-lookup"><span data-stu-id="facbc-187">So, `$PSHOME` is `/usr/local/microsoft/powershell/7.1.0/`, and the symbolic link is placed at `/usr/local/bin/pwsh`.</span></span>

## <a name="installation-support"></a><span data-ttu-id="facbc-188">Поддержка установки</span><span class="sxs-lookup"><span data-stu-id="facbc-188">Installation support</span></span>

<span data-ttu-id="facbc-189">Корпорация Майкрософт поддерживает методы установки, изложенные в этом документе.</span><span class="sxs-lookup"><span data-stu-id="facbc-189">Microsoft supports the installation methods in this document.</span></span> <span data-ttu-id="facbc-190">В других источниках могут быть доступны другие методы установки.</span><span class="sxs-lookup"><span data-stu-id="facbc-190">There may be other methods of installation available from other sources.</span></span> <span data-ttu-id="facbc-191">Хотя такие инструменты и методы могут работать, корпорация Майкрософт не поддерживает их.</span><span class="sxs-lookup"><span data-stu-id="facbc-191">While those tools and methods may work, Microsoft cannot support those methods.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="facbc-192">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="facbc-192">Additional Resources</span></span>

- <span data-ttu-id="facbc-193">[Homebrew в Интернете][brew]</span><span class="sxs-lookup"><span data-stu-id="facbc-193">[Homebrew Web][brew]</span></span>
- <span data-ttu-id="facbc-194">[Репозиторий Homebrew на Github][GitHub]</span><span class="sxs-lookup"><span data-stu-id="facbc-194">[Homebrew Github Repository][GitHub]</span></span>
- <span data-ttu-id="facbc-195">[Homebrew-Cask][cask]</span><span class="sxs-lookup"><span data-stu-id="facbc-195">[Homebrew-Cask][cask]</span></span>

[brew]: http://brew.sh/
[Cask]: https://github.com/Homebrew/homebrew-cask
[cask-versions]: https://github.com/Homebrew/homebrew-cask-versions
[GitHub]: https://github.com/Homebrew
[выпусками]: https://github.com/PowerShell/PowerShell/releases/latest
[releases]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
