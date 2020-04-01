---
title: Установка PowerShell в macOS
description: Сведения об установке PowerShell в macOS
ms.date: 12/12/2018
ms.openlocfilehash: 3a5e71d0f69d0c39f9b7f3fa667863d7ec0a31dd
ms.sourcegitcommit: bf71c8c5e2a4fc7d5c3a67a537db1285089d03a7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/30/2020
ms.locfileid: "80394994"
---
# <a name="installing-powershell-on-macos"></a>Установка PowerShell в macOS

PowerShell поддерживает macOS версии 10.12 и более поздних.
Все пакеты доступны на нашей странице [выпусков][] GitHub.
После установки пакета запустите `pwsh` из терминала.

> [!NOTE]
> PowerShell 7 является обновлением на месте, при установке которого PowerShell Core 6.x удаляется.
>
> Папка `/usr/local/microsoft/powershell/6` заменяется на `/usr/local/microsoft/powershell/7`.
>
> Если вы хотите запускать PowerShell 6 параллельно с PowerShell 7, переустановите PowerShell 6 с использованием [двоичного архива](#binary-archives).

## <a name="about-brew"></a>Сведения о Brew

[Homebrew][brew] является предпочтительным диспетчером пакетов для macOS. Если команда `brew` не найдена, нужно установить Homebrew по [соответствующим инструкциям][brew]. Вы также можете установить PowerShell с помощью [прямого скачивания](#installation-via-direct-download) или из [архивов двоичных файлов](#binary-archives).

## <a name="installation-of-latest-stable-release-via-homebrew-on-macos-1012-or-higher"></a>Установка последнего стабильного выпуска с помощью Homebrew в macOS 10.12 или более поздней версии

См. дополнительные сведения о [Brew](#about-brew).

Теперь можно установить PowerShell:

```sh
brew cask install powershell
```

И наконец, убедитесь, что установка прошла без ошибок.

```sh
pwsh
```

После выпуска новых версий PowerShell обновите формулы Homebrew и PowerShell:

```sh
brew update
brew cask upgrade powershell
```

> [!NOTE]
> Приведенные выше команды можно вызвать из узла PowerShell (pwsh), но затем потребуется выйти из оболочки PowerShell и перезапустить ее, чтобы завершить обновление и обновить значения в таблице `$PSVersionTable`.

[brew]: https://brew.sh/

## <a name="installation-of-latest-preview-release-via-homebrew-on-macos-1012-or-higher"></a>Установка последнего предварительного выпуска с помощью Homebrew в macOS 10.12 или более поздней версии

См. дополнительные сведения о [Brew](#about-brew).

После установки Homebrew можно установить PowerShell.
Сначала установите пакет [Cask-Versions][cask-versions], который позволит устанавливать альтернативные версии Cask-пакетов.

```sh
brew tap homebrew/cask-versions
```

Теперь можно установить PowerShell:

```sh
brew cask install powershell-preview
```

И наконец, убедитесь, что установка прошла без ошибок.

```sh
pwsh-preview
```

После выпуска новых версий PowerShell обновите формулы Homebrew и PowerShell:

```sh
brew update
brew cask upgrade powershell-preview
```

> [!NOTE]
> Команду, указанную выше, можно вызвать на узле PowerShell (pwsh), но для этого необходимо завершить его обновление. Что в свою очередь будет сделано, когда вы выйдете из PowerShell и перезапустите его.
> Обновите значения, которые отображаются в `$PSVersionTable`.

## <a name="installation-via-direct-download"></a>Установка с помощью прямого скачивания

Скачайте пакет PKG `powershell-lts-7.0.0-osx-x64.pkg`
со страницы [выпусков][] на компьютер с macOS.

Дважды щелкните файл и следуйте инструкциям на экране либо установите его из командной строки:

```sh
sudo installer -pkg powershell-lts-7.0.0-osx-x64.pkg -target /
```

Установите [OpenSSL](#install-openssl). OpenSSL требуется для удаленного взаимодействия PowerShell и операций CIM.

## <a name="install-as-a-net-global-tool"></a>Установка в качестве глобального средства .NET

Если вы уже установили [пакет SDK для .NET Core](/dotnet/core/sdk), установите PowerShell как [глобальное средство .NET](/dotnet/core/tools/global-tools).

```
dotnet tool install --global PowerShell
```

Установщик инструмента dotnet добавляет `~/.dotnet/tools` в переменную среды `PATH`. Но в выполняющейся оболочке отсутствует обновленная переменная `PATH`. Вы можете запустить PowerShell из новой оболочки, введя `pwsh`.

## <a name="binary-archives"></a>Архивы двоичных файлов

Для поддержки расширенных сценариев развертывания на платформе macOS доступны архивы `tar.gz` двоичных файлов PowerShell.

### <a name="installing-binary-archives-on-macos"></a>Установка архивов двоичных файлов в macOS

```sh
# Download the powershell '.tar.gz' archive
curl -L -o /tmp/powershell.tar.gz https://github.com/PowerShell/PowerShell/releases/download/v7.0.0/powershell-7.0.0-osx-x64.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /usr/local/microsoft/powershell/7.0.0

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /usr/local/microsoft/powershell/7.0.0

# Set execute permissions
sudo chmod +x /usr/local/microsoft/powershell/7.0.0/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /usr/local/microsoft/powershell/7.0.0/pwsh /usr/local/bin/pwsh
```

Установите [OpenSSL](#install-openssl). OpenSSL требуется для удаленного взаимодействия PowerShell и операций CIM.

## <a name="installing-dependencies"></a>Установка зависимостей

### <a name="install-xcode-command-line-tools"></a>Установка средств командной строки XCode

```sh
xcode-select --install
```

### <a name="install-openssl"></a>Установка OpenSSL

OpenSSL требуется для удаленного взаимодействия PowerShell и операций CIM. Установка возможна с помощью MacPorts или Brew.

#### <a name="install-openssl-via-brew"></a>Установка OpenSSL с помощью Brew

См. дополнительные сведения о [Brew](#about-brew).

Запустите `brew install openssl`, чтобы установить OpenSSL.

#### <a name="install-openssl-via-macports"></a>Установка OpenSSL с помощью MacPorts

1. Установите [средство командной строки XCode](#install-xcode-command-line-tools).
1. Установите MacPorts.
   Инструкции см. в [руководстве по установке](https://guide.macports.org/chunked/installing.macports.html).
1. Обновите MacPorts, выполнив команду `sudo port selfupdate`.
1. Обновите пакеты MacPorts, выполнив команду `sudo port upgrade outdated`.
1. Установите OpenSSL, запустив `sudo port install openssl`.
1. Укажите ссылки на библиотеки, чтобы сделать их доступными для PowerShell:

```sh
sudo mkdir -p /usr/local/opt/openssl
sudo ln -s /opt/local/lib /usr/local/opt/openssl/lib
```

## <a name="uninstalling-powershell"></a>Удаление PowerShell

Если вы установили PowerShell с помощью Homebrew, используйте следующую команду для удаления:

```sh
brew cask uninstall powershell
```

Если вы установили PowerShell с помощью прямого скачивания, PowerShell нужно удалить вручную:

```sh
sudo rm -rf /usr/local/bin/pwsh /usr/local/microsoft/powershell
```

Чтобы удалить дополнительные пути PowerShell, ознакомьтесь с разделом [Пути](#paths) этой статьи, и удалите их с помощью команды `sudo rm`.

> [!NOTE]
> Это не требуется в случае установки с помощью Homebrew.

## <a name="paths"></a>Пути

* `$PSHOME` имеет значение `/usr/local/microsoft/powershell/7.0.0/`.
* Профили пользователей будут считаны из `~/.config/powershell/profile.ps1`.
* Профили по умолчанию будут считаны из `$PSHOME/profile.ps1`.
* Модули пользователей будут считаны из `~/.local/share/powershell/Modules`.
* Общие модули будут считаны из `/usr/local/share/powershell/Modules`.
* Модули по умолчанию будут считаны из `$PSHOME/Modules`.
* Журнал PSReadline будет записан в `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`.

Профили учитывают конфигурацию PowerShell для отдельных узлов.
Профиль узла по умолчанию находится в `Microsoft.PowerShell_profile.ps1` в тех же расположениях.

PowerShell отвечает требованиям [спецификации каталога размещения файлов, связанных со средой настольной графической среды (X-сервера), стандартизированного XDG (X Desktop Group)][xdg-bds] в macOS.

Так как macOS является развитием BSD, необходимо использовать префикс `/usr/local` вместо `/opt`.
Таким образом, `$PSHOME` имеет значение `/usr/local/microsoft/powershell/7.0.0/`, а символьная ссылка размещается в `/usr/local/bin/pwsh`.

## <a name="additional-resources"></a>Дополнительные ресурсы

* [Homebrew в Интернете][brew]
* [Репозиторий Homebrew на Github][GitHub]
* [Homebrew-Cask][cask]

[brew]: http://brew.sh/
[Cask]: https://github.com/Homebrew/homebrew-cask
[cask-versions]: https://github.com/Homebrew/homebrew-cask-versions
[GitHub]: https://github.com/Homebrew
[выпусков]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
