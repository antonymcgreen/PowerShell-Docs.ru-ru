---
title: Установка PowerShell в macOS
description: Сведения об установке PowerShell в macOS
ms.date: 08/24/2020
ms.openlocfilehash: 8f38d573d9d67276dbc95cfb70f1fde80af62bb6
ms.sourcegitcommit: ea9270bacee7dd1b9df2519384de277576357ce2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88857907"
---
# <a name="installing-powershell-on-macos"></a><span data-ttu-id="e11d0-103">Установка PowerShell в macOS</span><span class="sxs-lookup"><span data-stu-id="e11d0-103">Installing PowerShell on macOS</span></span>

<span data-ttu-id="e11d0-104">PowerShell поддерживает macOS версии 10.12 и более поздних.</span><span class="sxs-lookup"><span data-stu-id="e11d0-104">PowerShell supports macOS 10.12 and higher.</span></span> <span data-ttu-id="e11d0-105">Для PowerShell 7.0.3 или более поздней версии и предварительных версий PowerShell 7.1.0 или более поздней версии требуется macOS 10.13 и более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="e11d0-105">PowerShell 7.0.3 or higher and PowerShell Preview 7.1.0 or higher require macOS 10.13 and higher.</span></span> <span data-ttu-id="e11d0-106">Все пакеты доступны на нашей странице [выпусками][] GitHub.</span><span class="sxs-lookup"><span data-stu-id="e11d0-106">All packages are available on our GitHub [releases][] page.</span></span> <span data-ttu-id="e11d0-107">После установки пакета запустите `pwsh` из терминала.</span><span class="sxs-lookup"><span data-stu-id="e11d0-107">After the package is installed, run `pwsh` from a terminal.</span></span>

> [!NOTE]
> <span data-ttu-id="e11d0-108">PowerShell 7 является обновлением на месте, при установке которого PowerShell Core 6.x удаляется.</span><span class="sxs-lookup"><span data-stu-id="e11d0-108">PowerShell 7 is an in-place upgrade that removes PowerShell Core 6.x.</span></span>
>
> <span data-ttu-id="e11d0-109">Папка `/usr/local/microsoft/powershell/6` заменяется на `/usr/local/microsoft/powershell/7`.</span><span class="sxs-lookup"><span data-stu-id="e11d0-109">The `/usr/local/microsoft/powershell/6` folder is replaced by `/usr/local/microsoft/powershell/7`.</span></span>
>
> <span data-ttu-id="e11d0-110">Если вы хотите запускать PowerShell 6 параллельно с PowerShell 7, переустановите PowerShell 6 с использованием [двоичного архива](#binary-archives).</span><span class="sxs-lookup"><span data-stu-id="e11d0-110">If you need to run PowerShell 6 side-by-side with PowerShell 7, reinstall PowerShell 6 using the [binary archive](#binary-archives) method.</span></span>

<span data-ttu-id="e11d0-111">Существует несколько способов установки PowerShell в macOS.</span><span class="sxs-lookup"><span data-stu-id="e11d0-111">There are several ways to install PowerShell on macOS.</span></span> <span data-ttu-id="e11d0-112">Выберите для этого один из следующих методов:</span><span class="sxs-lookup"><span data-stu-id="e11d0-112">Choose one of the following methods:</span></span>

- <span data-ttu-id="e11d0-113">Установка с помощью Homebrew.</span><span class="sxs-lookup"><span data-stu-id="e11d0-113">Install using Homebrew.</span></span> <span data-ttu-id="e11d0-114">Homebrew является предпочтительным диспетчером пакетов для macOS.</span><span class="sxs-lookup"><span data-stu-id="e11d0-114">Homebrew is the preferred package manager for macOS.</span></span>
- <span data-ttu-id="e11d0-115">Установка PowerShell через [Direct Download](#installation-via-direct-download)</span><span class="sxs-lookup"><span data-stu-id="e11d0-115">Install PowerShell via [Direct Download](#installation-via-direct-download)</span></span>
- <span data-ttu-id="e11d0-116">Установка из [архивов двоичных файлов](#binary-archives).</span><span class="sxs-lookup"><span data-stu-id="e11d0-116">Install from [binary archives](#binary-archives).</span></span>

<span data-ttu-id="e11d0-117">После установки PowerShell следует установить [OpenSSL](#installing-dependencies).</span><span class="sxs-lookup"><span data-stu-id="e11d0-117">After installing PowerShell, you should install [OpenSSL](#installing-dependencies).</span></span> <span data-ttu-id="e11d0-118">OpenSSL требуется для удаленного взаимодействия PowerShell и операций CIM.</span><span class="sxs-lookup"><span data-stu-id="e11d0-118">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>

## <a name="installation-of-latest-stable-release-via-homebrew-on-macos-1013-or-higher"></a><span data-ttu-id="e11d0-119">Установка последнего стабильного выпуска с помощью Homebrew в macOS 10.13 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="e11d0-119">Installation of latest stable release via Homebrew on macOS 10.13 or higher</span></span>

<span data-ttu-id="e11d0-120">Если команда `brew` не найдена, нужно установить Homebrew по [соответствующим инструкциям][brew].</span><span class="sxs-lookup"><span data-stu-id="e11d0-120">If the `brew` command is not found, you need to install Homebrew following [their instructions][brew].</span></span>

<span data-ttu-id="e11d0-121">Теперь можно установить PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e11d0-121">Now, you can install PowerShell:</span></span>

```sh
brew cask install powershell
```

<span data-ttu-id="e11d0-122">И наконец, убедитесь, что установка прошла без ошибок.</span><span class="sxs-lookup"><span data-stu-id="e11d0-122">Finally, verify that your install is working properly:</span></span>

```sh
pwsh
```

<span data-ttu-id="e11d0-123">После выпуска новых версий PowerShell обновите формулы Homebrew и PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e11d0-123">When new versions of PowerShell are released, update Homebrew's formulae and upgrade PowerShell:</span></span>

```sh
brew update
brew cask upgrade powershell
```

> [!NOTE]
> <span data-ttu-id="e11d0-124">Приведенные выше команды можно вызвать из узла PowerShell (pwsh), но затем потребуется выйти из оболочки PowerShell и перезапустить ее, чтобы завершить обновление и обновить значения в таблице `$PSVersionTable`.</span><span class="sxs-lookup"><span data-stu-id="e11d0-124">The commands above can be called from within a PowerShell (pwsh) host, but then the PowerShell shell must be exited and restarted to complete the upgrade and refresh the values shown in `$PSVersionTable`.</span></span>

[brew]: https://brew.sh/

## <a name="installation-of-latest-preview-release-via-homebrew-on-macos-1013-or-higher"></a><span data-ttu-id="e11d0-125">Установка последнего предварительного выпуска с помощью Homebrew в macOS 10.13 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="e11d0-125">Installation of latest preview release via Homebrew on macOS 10.13 or higher</span></span>

<span data-ttu-id="e11d0-126">После установки Homebrew можно установить PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e11d0-126">After you've installed Homebrew, you can install PowerShell.</span></span> <span data-ttu-id="e11d0-127">Сначала установите пакет [Cask-Versions][cask-versions], который позволит устанавливать альтернативные версии Cask-пакетов.</span><span class="sxs-lookup"><span data-stu-id="e11d0-127">First, install the [Cask-Versions][cask-versions] package that lets you install alternative versions of cask packages:</span></span>

```sh
brew tap homebrew/cask-versions
```

<span data-ttu-id="e11d0-128">Теперь можно установить PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e11d0-128">Now, you can install PowerShell:</span></span>

```sh
brew cask install powershell-preview
```

<span data-ttu-id="e11d0-129">И наконец, убедитесь, что установка прошла без ошибок.</span><span class="sxs-lookup"><span data-stu-id="e11d0-129">Finally, verify that your install is working properly:</span></span>

```sh
pwsh-preview
```

<span data-ttu-id="e11d0-130">После выпуска новых версий PowerShell обновите формулы Homebrew и PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e11d0-130">When new versions of PowerShell are released, update Homebrew's formulae and upgrade PowerShell:</span></span>

```sh
brew update
brew cask upgrade powershell-preview
```

> [!NOTE]
> <span data-ttu-id="e11d0-131">Команду, указанную выше, можно вызвать на узле PowerShell (pwsh), но для этого необходимо завершить его обновление. Что в свою очередь будет сделано, когда вы выйдете из PowerShell и перезапустите его.</span><span class="sxs-lookup"><span data-stu-id="e11d0-131">The commands above can be called from within a PowerShell (pwsh) host, but then the PowerShell shell must be exited and restarted to complete the upgrade.</span></span>
> <span data-ttu-id="e11d0-132">Обновите значения, которые отображаются в `$PSVersionTable`.</span><span class="sxs-lookup"><span data-stu-id="e11d0-132">and refresh the values shown in `$PSVersionTable`.</span></span>

<span data-ttu-id="e11d0-133">Установка PowerShell с помощью метода tap Homebrew также поддерживается для стабильных версий и версий LTS.</span><span class="sxs-lookup"><span data-stu-id="e11d0-133">Installing PowerShell using the Homebrew tap method is also supported for stable and LTS versions.</span></span>

```sh
brew install powershell/tap/powershell
```

<span data-ttu-id="e11d0-134">Теперь можно проверить установку.</span><span class="sxs-lookup"><span data-stu-id="e11d0-134">You can now verify your install</span></span>

```sh
pwsh
```

<span data-ttu-id="e11d0-135">После выпуска новых версий PowerShell просто выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="e11d0-135">When new versions of PowerShell are released, simply run the following command.</span></span>

```sh
brew upgrade powershell
```

> [!NOTE]
> <span data-ttu-id="e11d0-136">Если вы используете метод cask или tap при обновлении до более новой версии PowerShell, используйте тот же метод, который применяли для первоначальной установки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e11d0-136">Whether you use the cask or the tap method, when updating to a newer version of PowerShell, use the same method you used to initially install PowerShell.</span></span> <span data-ttu-id="e11d0-137">При использовании другого метода новый сеанс pwsh будет продолжать использовать старую версию PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e11d0-137">If you use a different method, opening a new pwsh session will continue to use the older version of PowerShell.</span></span>
>
> <span data-ttu-id="e11d0-138">Если вы решите использовать разные методы, существуют способы исправить проблему с помощью [метода Homebrew link](https://docs.brew.sh/Manpage#link-ln-options-formula).</span><span class="sxs-lookup"><span data-stu-id="e11d0-138">If you do decide to use different methods, there are ways to correct the issue using the [Homebrew link method](https://docs.brew.sh/Manpage#link-ln-options-formula).</span></span>

## <a name="installation-via-direct-download"></a><span data-ttu-id="e11d0-139">Установка с помощью прямого скачивания</span><span class="sxs-lookup"><span data-stu-id="e11d0-139">Installation via Direct Download</span></span>

<span data-ttu-id="e11d0-140">Для компьютера с macOS пакет PKG `powershell-lts-7.0.3-osx-x64.pkg` можно загрузить на странице [Выпуски][].</span><span class="sxs-lookup"><span data-stu-id="e11d0-140">Download the PKG package `powershell-lts-7.0.3-osx-x64.pkg` from the [releases][] page onto your macOS machine.</span></span>

<span data-ttu-id="e11d0-141">Дважды щелкните файл и следуйте инструкциям на экране либо установите его из командной строки:</span><span class="sxs-lookup"><span data-stu-id="e11d0-141">You can double-click the file and follow the prompts, or install it from the terminal:</span></span>

```sh
sudo installer -pkg powershell-lts-7.0.3-osx-x64.pkg -target /
```

<span data-ttu-id="e11d0-142">Установите [OpenSSL](#installing-dependencies).</span><span class="sxs-lookup"><span data-stu-id="e11d0-142">Install [OpenSSL](#installing-dependencies).</span></span> <span data-ttu-id="e11d0-143">OpenSSL требуется для удаленного взаимодействия PowerShell и операций CIM.</span><span class="sxs-lookup"><span data-stu-id="e11d0-143">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>

## <a name="install-as-a-net-global-tool"></a><span data-ttu-id="e11d0-144">Установка в качестве глобального средства .NET</span><span class="sxs-lookup"><span data-stu-id="e11d0-144">Install as a .NET Global tool</span></span>

<span data-ttu-id="e11d0-145">Если вы уже установили [пакет SDK для .NET Core](/dotnet/core/sdk), установите PowerShell как [глобальное средство .NET](/dotnet/core/tools/global-tools).</span><span class="sxs-lookup"><span data-stu-id="e11d0-145">If you already have the [.NET Core SDK](/dotnet/core/sdk) installed, it's easy to install PowerShell as a [.NET Global tool](/dotnet/core/tools/global-tools).</span></span>

```
dotnet tool install --global PowerShell
```

<span data-ttu-id="e11d0-146">Установщик инструмента dotnet добавляет `~/.dotnet/tools` в переменную среды `PATH`.</span><span class="sxs-lookup"><span data-stu-id="e11d0-146">The dotnet tool installer adds `~/.dotnet/tools` to your `PATH` environment variable.</span></span> <span data-ttu-id="e11d0-147">Но в выполняющейся оболочке отсутствует обновленная переменная `PATH`.</span><span class="sxs-lookup"><span data-stu-id="e11d0-147">However, the currently running shell does not have the updated `PATH`.</span></span> <span data-ttu-id="e11d0-148">Вы можете запустить PowerShell из новой оболочки, введя `pwsh`.</span><span class="sxs-lookup"><span data-stu-id="e11d0-148">You should be able to start PowerShell from a new shell by typing `pwsh`.</span></span>

<span data-ttu-id="e11d0-149">Установите [OpenSSL](#installing-dependencies).</span><span class="sxs-lookup"><span data-stu-id="e11d0-149">Install [OpenSSL](#installing-dependencies).</span></span> <span data-ttu-id="e11d0-150">OpenSSL требуется для удаленного взаимодействия PowerShell и операций CIM.</span><span class="sxs-lookup"><span data-stu-id="e11d0-150">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>

## <a name="binary-archives"></a><span data-ttu-id="e11d0-151">Архивы двоичных файлов</span><span class="sxs-lookup"><span data-stu-id="e11d0-151">Binary Archives</span></span>

<span data-ttu-id="e11d0-152">Для поддержки расширенных сценариев развертывания на платформе macOS доступны архивы `tar.gz` двоичных файлов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e11d0-152">PowerShell binary `tar.gz` archives are provided for the macOS platform to enable advanced deployment scenarios.</span></span> <span data-ttu-id="e11d0-153">При установке с помощью этого метода необходимо также вручную установить все зависимости.</span><span class="sxs-lookup"><span data-stu-id="e11d0-153">When you install using this method you must also manually install any dependencies.</span></span>

<span data-ttu-id="e11d0-154">Установите [OpenSSL](#installing-dependencies).</span><span class="sxs-lookup"><span data-stu-id="e11d0-154">Install [OpenSSL](#installing-dependencies).</span></span> <span data-ttu-id="e11d0-155">OpenSSL требуется для удаленного взаимодействия PowerShell и операций CIM.</span><span class="sxs-lookup"><span data-stu-id="e11d0-155">OpenSSL is needed for PowerShell remoting and CIM operations.</span></span>

### <a name="installing-binary-archives-on-macos"></a><span data-ttu-id="e11d0-156">Установка архивов двоичных файлов в macOS</span><span class="sxs-lookup"><span data-stu-id="e11d0-156">Installing binary archives on macOS</span></span>

```sh
# Download the powershell '.tar.gz' archive
curl -L -o /tmp/powershell.tar.gz https://github.com/PowerShell/PowerShell/releases/download/v7.0.3/powershell-7.0.3-osx-x64.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /usr/local/microsoft/powershell/7.0.3

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /usr/local/microsoft/powershell/7.0.3

# Set execute permissions
sudo chmod +x /usr/local/microsoft/powershell/7.0.3/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /usr/local/microsoft/powershell/7.0.3/pwsh /usr/local/bin/pwsh
```

## <a name="installing-dependencies"></a><span data-ttu-id="e11d0-157">Установка зависимостей</span><span class="sxs-lookup"><span data-stu-id="e11d0-157">Installing dependencies</span></span>

<span data-ttu-id="e11d0-158">OpenSSL требуется для удаленного взаимодействия PowerShell и операций CIM.</span><span class="sxs-lookup"><span data-stu-id="e11d0-158">OpenSSL is required for PowerShell remoting and CIM operations.</span></span> <span data-ttu-id="e11d0-159">При необходимости вы можете установить OpenSSL с помощью MacPorts.</span><span class="sxs-lookup"><span data-stu-id="e11d0-159">You can install OpenSSL via MacPorts if needed.</span></span>

> [!NOTE]
> <span data-ttu-id="e11d0-160">MacPorts и Homebrew могут приводить к проблемам при совместном использовании в одной системе.</span><span class="sxs-lookup"><span data-stu-id="e11d0-160">MacPorts and Homebrew can have problems when used to together on the same system.</span></span> <span data-ttu-id="e11d0-161">Однако у Homebrew нет пакета для OpenSSL 1.0.</span><span class="sxs-lookup"><span data-stu-id="e11d0-161">However, Homebrew does not have a package for OpenSSL 1.0.</span></span> <span data-ttu-id="e11d0-162">Дополнительные сведения см. в разделе [Часто задаваемые вопросы о MacPorts](https://trac.macports.org/wiki/FAQ).</span><span class="sxs-lookup"><span data-stu-id="e11d0-162">For more information, see the [MacPorts FAQ](https://trac.macports.org/wiki/FAQ).</span></span>

1. <span data-ttu-id="e11d0-163">Установите средства командной строки Xcode.</span><span class="sxs-lookup"><span data-stu-id="e11d0-163">Install the Xcode command-line tools.</span></span> <span data-ttu-id="e11d0-164">Средства Xcode требуются для MacPorts.</span><span class="sxs-lookup"><span data-stu-id="e11d0-164">The Xcode tools are required by MacPorts.</span></span>

   ```sh
   xcode-select --install
   ```

1. <span data-ttu-id="e11d0-165">Установите MacPorts.</span><span class="sxs-lookup"><span data-stu-id="e11d0-165">Install MacPorts.</span></span> <span data-ttu-id="e11d0-166">Инструкции см. в [руководстве по установке](https://www.macports.org/install.php).</span><span class="sxs-lookup"><span data-stu-id="e11d0-166">If you need instructions, refer to the [installation guide](https://www.macports.org/install.php).</span></span>
1. <span data-ttu-id="e11d0-167">Обновите MacPorts, выполнив команду `sudo port selfupdate`.</span><span class="sxs-lookup"><span data-stu-id="e11d0-167">Update MacPorts by running `sudo port selfupdate`.</span></span>
1. <span data-ttu-id="e11d0-168">Обновите пакеты MacPorts, выполнив команду `sudo port upgrade outdated`.</span><span class="sxs-lookup"><span data-stu-id="e11d0-168">Upgrade MacPorts packages by running `sudo port upgrade outdated`.</span></span>
1. <span data-ttu-id="e11d0-169">Установите OpenSSL, запустив `sudo port install openssl10`.</span><span class="sxs-lookup"><span data-stu-id="e11d0-169">Install OpenSSL by running `sudo port install openssl10`.</span></span>
1. <span data-ttu-id="e11d0-170">Укажите ссылки на библиотеки, чтобы сделать их доступными для PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e11d0-170">Link the libraries to make them available to PowerShell:</span></span>

   ```sh
   sudo mkdir -p /usr/local/opt/openssl
   sudo ln -s /opt/local/lib/openssl-1.0 /usr/local/opt/openssl/lib
   ```

## <a name="uninstalling-powershell"></a><span data-ttu-id="e11d0-171">Удаление PowerShell</span><span class="sxs-lookup"><span data-stu-id="e11d0-171">Uninstalling PowerShell</span></span>

<span data-ttu-id="e11d0-172">Если вы установили PowerShell с помощью Homebrew, используйте следующую команду для удаления:</span><span class="sxs-lookup"><span data-stu-id="e11d0-172">If you installed PowerShell with Homebrew, use the following command to uninstall:</span></span>

```sh
brew cask uninstall powershell
```

<span data-ttu-id="e11d0-173">Если вы установили PowerShell с помощью прямого скачивания, PowerShell нужно удалить вручную:</span><span class="sxs-lookup"><span data-stu-id="e11d0-173">If you installed PowerShell via direct download, PowerShell must be removed manually:</span></span>

```sh
sudo rm -rf /usr/local/bin/pwsh /usr/local/microsoft/powershell
```

<span data-ttu-id="e11d0-174">Чтобы удалить дополнительные пути PowerShell, ознакомьтесь с разделом [Пути](#paths) этой статьи, и удалите их с помощью команды `sudo rm`.</span><span class="sxs-lookup"><span data-stu-id="e11d0-174">To remove the additional PowerShell paths, refer to the [paths](#paths) section in this document and remove the paths using `sudo rm`.</span></span>

> [!NOTE]
> <span data-ttu-id="e11d0-175">Это не требуется в случае установки с помощью Homebrew.</span><span class="sxs-lookup"><span data-stu-id="e11d0-175">This is not necessary if you installed with Homebrew.</span></span>

## <a name="paths"></a><span data-ttu-id="e11d0-176">Пути</span><span class="sxs-lookup"><span data-stu-id="e11d0-176">Paths</span></span>

- <span data-ttu-id="e11d0-177">`$PSHOME` имеет значение `/usr/local/microsoft/powershell/7.0.3/`.</span><span class="sxs-lookup"><span data-stu-id="e11d0-177">`$PSHOME` is `/usr/local/microsoft/powershell/7.0.3/`</span></span>
- <span data-ttu-id="e11d0-178">Профили пользователей будут считаны из `~/.config/powershell/profile.ps1`.</span><span class="sxs-lookup"><span data-stu-id="e11d0-178">User profiles will be read from `~/.config/powershell/profile.ps1`</span></span>
- <span data-ttu-id="e11d0-179">Профили по умолчанию будут считаны из `$PSHOME/profile.ps1`.</span><span class="sxs-lookup"><span data-stu-id="e11d0-179">Default profiles will be read from `$PSHOME/profile.ps1`</span></span>
- <span data-ttu-id="e11d0-180">Модули пользователей будут считаны из `~/.local/share/powershell/Modules`.</span><span class="sxs-lookup"><span data-stu-id="e11d0-180">User modules will be read from `~/.local/share/powershell/Modules`</span></span>
- <span data-ttu-id="e11d0-181">Общие модули будут считаны из `/usr/local/share/powershell/Modules`.</span><span class="sxs-lookup"><span data-stu-id="e11d0-181">Shared modules will be read from `/usr/local/share/powershell/Modules`</span></span>
- <span data-ttu-id="e11d0-182">Модули по умолчанию будут считаны из `$PSHOME/Modules`.</span><span class="sxs-lookup"><span data-stu-id="e11d0-182">Default modules will be read from `$PSHOME/Modules`</span></span>
- <span data-ttu-id="e11d0-183">Журнал PSReadline будет записан в `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`.</span><span class="sxs-lookup"><span data-stu-id="e11d0-183">PSReadline history will be recorded to `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`</span></span>

<span data-ttu-id="e11d0-184">Профили учитывают конфигурацию PowerShell для отдельных узлов.</span><span class="sxs-lookup"><span data-stu-id="e11d0-184">The profiles respect PowerShell's per-host configuration.</span></span> <span data-ttu-id="e11d0-185">Профиль узла по умолчанию находится в `Microsoft.PowerShell_profile.ps1` в тех же расположениях.</span><span class="sxs-lookup"><span data-stu-id="e11d0-185">So the default host-specific profile exists at `Microsoft.PowerShell_profile.ps1` in the same locations.</span></span>

<span data-ttu-id="e11d0-186">PowerShell отвечает требованиям [спецификации каталога размещения файлов, связанных со средой настольной графической среды (X-сервера), стандартизированного XDG (X Desktop Group)][xdg-bds] в macOS.</span><span class="sxs-lookup"><span data-stu-id="e11d0-186">PowerShell respects the [XDG Base Directory Specification][xdg-bds] on macOS.</span></span>

<span data-ttu-id="e11d0-187">Так как macOS является развитием BSD, необходимо использовать префикс `/usr/local` вместо `/opt`.</span><span class="sxs-lookup"><span data-stu-id="e11d0-187">Because macOS is a derivation of BSD, the prefix `/usr/local` is used instead of `/opt`.</span></span> <span data-ttu-id="e11d0-188">Таким образом, `$PSHOME` имеет значение `/usr/local/microsoft/powershell/7.0.3/`, а символьная ссылка размещается в `/usr/local/bin/pwsh`.</span><span class="sxs-lookup"><span data-stu-id="e11d0-188">So, `$PSHOME` is `/usr/local/microsoft/powershell/7.0.3/`, and the symbolic link is placed at `/usr/local/bin/pwsh`.</span></span>

## <a name="installation-support"></a><span data-ttu-id="e11d0-189">Поддержка установки</span><span class="sxs-lookup"><span data-stu-id="e11d0-189">Installation support</span></span>

<span data-ttu-id="e11d0-190">Корпорация Майкрософт поддерживает методы установки, изложенные в этом документе.</span><span class="sxs-lookup"><span data-stu-id="e11d0-190">Microsoft supports the installation methods in this document.</span></span> <span data-ttu-id="e11d0-191">В других источниках могут быть доступны другие методы установки.</span><span class="sxs-lookup"><span data-stu-id="e11d0-191">There may be other methods of installation available from other sources.</span></span> <span data-ttu-id="e11d0-192">Хотя такие инструменты и методы могут работать, корпорация Майкрософт не поддерживает их.</span><span class="sxs-lookup"><span data-stu-id="e11d0-192">While those tools and methods may work, Microsoft cannot support those methods.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e11d0-193">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="e11d0-193">Additional Resources</span></span>

- <span data-ttu-id="e11d0-194">[Homebrew в Интернете][brew]</span><span class="sxs-lookup"><span data-stu-id="e11d0-194">[Homebrew Web][brew]</span></span>
- <span data-ttu-id="e11d0-195">[Репозиторий Homebrew на Github][GitHub]</span><span class="sxs-lookup"><span data-stu-id="e11d0-195">[Homebrew Github Repository][GitHub]</span></span>
- <span data-ttu-id="e11d0-196">[Homebrew-Cask][cask]</span><span class="sxs-lookup"><span data-stu-id="e11d0-196">[Homebrew-Cask][cask]</span></span>

[brew]: http://brew.sh/
[Cask]: https://github.com/Homebrew/homebrew-cask
[cask-versions]: https://github.com/Homebrew/homebrew-cask-versions
[GitHub]: https://github.com/Homebrew
[выпусками]: https://github.com/PowerShell/PowerShell/releases/latest
[releases]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
