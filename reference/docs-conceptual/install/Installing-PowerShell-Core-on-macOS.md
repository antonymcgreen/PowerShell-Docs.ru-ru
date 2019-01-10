---
title: Установка PowerShell Core в macOS
description: Сведения об установке PowerShell Core в macOS
ms.date: 12/12/2018
ms.openlocfilehash: 91e64cace7d4ed988da56109dde9bf2a80528eb4
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402560"
---
# <a name="installing-powershell-core-on-macos"></a>Установка PowerShell Core в macOS

PowerShell Core поддерживает macOS версии 10.12 и более поздних версий
Все пакеты доступны на нашей странице [выпусков][] GitHub.
После установки пакета запустите `pwsh` из терминала.

## <a name="about-brew"></a>Сведения о Brew

[Homebrew][brew] является предпочтительным диспетчером пакетов для macOS.
Если команда `brew` не найдена, нужно установить Homebrew по [соответствующим инструкциям][brew].

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

При выходе новых версий PowerShell, обновите формулы Homebrew и обновить PowerShell:

```sh
brew update
brew cask upgrade powershell
```

> [!NOTE]
> Приведенные выше команды могут вызываться из узла PowerShell (pwsh), но затем необходимо завершила работу и перезапуска для завершения обновления и обновления значений, приведенных в оболочке PowerShell `$PSVersionTable`.

[brew]: http://brew.sh/

## <a name="installation-of-latest-preview-release-via-homebrew-on-macos-1012-or-higher"></a>Установка последнего предварительного выпуска с помощью Homebrew в macOS 10.12 или более поздней версии

См. дополнительные сведения о [Brew](#about-brew).

После установки Homebrew, вы можете установить PowerShell.
Сначала установите [Cask версии] [ cask-versions] пакет, позволяющий установить альтернативные версии cask пакетов:

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

При выходе новых версий PowerShell, обновите формулы Homebrew и обновить PowerShell:

```sh
brew update
brew cask upgrade powershell-preview
```

> [!NOTE]
> Команду, указанную выше, можно вызвать на узле PowerShell (pwsh), но для этого необходимо завершить его обновление. Что в свою очередь будет сделано, когда вы выйдете из PowerShell и перезапустите его.
> и обновите значения, показанные на `$PSVersionTable`.

## <a name="installation-via-direct-download"></a>Установка с помощью прямого скачивания

Скачайте пакет PKG `powershell-6.1.0-osx-x64.pkg`
со страницы [выпусков][] на компьютер с macOS.

Дважды щелкните файл и следуйте инструкциям на экране либо установите его из командной строки:

```sh
sudo installer -pkg powershell-6.1.0-osx-x64.pkg -target /
```

Установите [OpenSSL](#install-openssl). OpenSSL требуется для удаленного взаимодействия PowerShell и операций CIM.

## <a name="binary-archives"></a>Архивы двоичных файлов

Для поддержки расширенных сценариев развертывания на платформе macOS доступны архивы `tar.gz` двоичных файлов PowerShell.

### <a name="installing-binary-archives-on-macos"></a>Установка архивов двоичных файлов в macOS

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

Чтобы установить OpenSSL, выполните `brew install openssl`.

#### <a name="install-openssl-via-macports"></a>Установка OpenSSL с помощью MacPorts

1. Установка [командной строки xcode](#install-xcode-command-line-tools).
1. Установите MacPorts.
   Если вам нужны инструкции, см. раздел [руководство по установке](https://guide.macports.org/chunked/installing.macports.html).
1. Обновите MacPorts, выполнив команду `sudo port selfupdate`.
1. Обновите пакеты MacPorts, выполнив команду `sudo port upgrade outdated`.
1. Установите OpenSSL, выполнив `sudo port install openssl`.
1. Привязывать библиотеки, чтобы сделать их доступными для PowerShell:

```sh
sudo mkdir -p /usr/local/opt/openssl
sudo ln -s /opt/local/lib /usr/local/opt/openssl/lib
```

## <a name="uninstalling-powershell-core"></a>Удаление PowerShell Core

Если вы установили PowerShell с помощью Homebrew, используйте следующую команду для удаления:

```sh
brew cask uninstall powershell
```

Если вы установили PowerShell с помощью прямого скачивания, PowerShell нужно удалить вручную:

```sh
sudo rm -rf /usr/local/bin/pwsh /usr/local/microsoft/powershell
```

Удалить дополнительные пути PowerShell, см. в статье [пути](#paths) этой статьи и удалить с помощью путей `sudo rm`.

> [!NOTE]
> Это не требуется в случае установки с помощью Homebrew.

## <a name="paths"></a>Пути

* `$PSHOME` имеет значение `/usr/local/microsoft/powershell/6.1.0/`.
* Профили пользователей будут считаны из `~/.config/powershell/profile.ps1`.
* Профили по умолчанию будут считаны из `$PSHOME/profile.ps1`.
* Модули пользователей будут считаны из `~/.local/share/powershell/Modules`.
* Общие модули будут считаны из `/usr/local/share/powershell/Modules`.
* Модули по умолчанию будут считаны из `$PSHOME/Modules`.
* Журнал PSReadline будет записан в `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`.

Профили учитывают конфигурацию PowerShell для отдельных узлов.
Поэтому профиль конкретных узлов по умолчанию находятся в `Microsoft.PowerShell_profile.ps1` в тех же расположениях.

PowerShell отвечает требованиям [спецификации каталога размещения файлов, связанных со средой настольной графической среды (X-сервера), стандартизированного XDG (X Desktop Group)][xdg-bds] в macOS.

Так как macOS является развитием BSD, необходимо использовать префикс `/usr/local` вместо `/opt`.
Таким образом `$PSHOME` — `/usr/local/microsoft/powershell/6.1.0/`, и символьную ссылку, размещаемый в `/usr/local/bin/pwsh`.

## <a name="additional-resources"></a>Дополнительные ресурсы

* [Homebrew Web][brew]
* [Репозиторий Github Homebrew][GitHub]
* [Homebrew-Cask][cask]

[brew]: http://brew.sh/
[Cask]: https://github.com/Homebrew/homebrew-cask
[cask-versions]: https://github.com/Homebrew/homebrew-cask-versions
[GitHub]: https://github.com/Homebrew
[выпусков]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
