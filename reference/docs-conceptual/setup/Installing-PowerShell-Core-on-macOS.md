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
# <a name="installing-powershell-core-on-macos"></a>Установка PowerShell Core в macOS

PowerShell Core поддерживает macOS версии 10.12 и более поздних версий
Все пакеты доступны на нашей странице [выпусков][] GitHub.
После установки пакета запустите `pwsh` из терминала.

## <a name="installation-of-latest-stable-release-via-homebrew-on-macos-1012-or-higher"></a>Установка последнего стабильного выпуска с помощью Homebrew в macOS 10.12 или более поздней версии

[Homebrew][brew] является предпочтительным диспетчером пакетов для macOS.
Если команда `brew` не найдена, нужно установить Homebrew по [соответствующим инструкциям][brew].

Теперь можно установить PowerShell:

```sh
brew cask install powershell
```

И наконец, убедитесь, что установка прошла без ошибок.

```sh
pwsh
```

После выпуска новых версий PowerShell просто обновите формулы Homebrew и PowerShell:

```sh
brew update
brew cask upgrade powershell
```

> [!NOTE]
> Команду, указанную выше, можно вызвать на узле PowerShell (pwsh), но для этого необходимо завершить его обновление. Что в свою очередь будет сделано, когда вы выйдете из PowerShell и перезапустите его.
> Обновите значения, которые отображаются в $PSVersionTable.

[brew]: http://brew.sh/

## <a name="installation-of-latest-preview-release-via-homebrew-on-macos-1012-or-higher"></a>Установка последнего предварительного выпуска с помощью Homebrew в macOS 10.12 или более поздней версии

[Homebrew][brew] является предпочтительным диспетчером пакетов для macOS.
Если команда `brew` не найдена, нужно установить Homebrew по [соответствующим инструкциям][brew].

После установки Homebrew установка PowerShell не вызывает проблем.
Сначала установите [cask-версии][cask-versions], что позволит устанавливать альтернативные версии cask-пакетов.

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

После выпуска новых версий PowerShell просто обновите формулы Homebrew и PowerShell:

```sh
brew update
brew cask upgrade powershell-preview
```

> [!NOTE]
> Команду, указанную выше, можно вызвать на узле PowerShell (pwsh), но для этого необходимо завершить его обновление. Что в свою очередь будет сделано, когда вы выйдете из PowerShell и перезапустите его.
> Обновите значения, которые отображаются в $PSVersionTable.

## <a name="installation-via-direct-download"></a>Установка с помощью прямого скачивания

Скачайте пакет PKG `powershell-6.1.0-osx-x64.pkg`
со страницы [выпусков][] на компьютер с macOS.

Дважды щелкните файл и следуйте инструкциям на экране либо установите его из командной строки:

```sh
sudo installer -pkg powershell-6.1.0-osx-x64.pkg -target /
```

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

## <a name="uninstalling-powershell-core"></a>Удаление PowerShell Core

Если вы установили PowerShell с помощью Homebrew, удаление осуществляется очень просто:

```sh
brew cask uninstall powershell
```

Если вы установили PowerShell с помощью прямого скачивания, PowerShell нужно удалить вручную:

```sh
sudo rm -rf /usr/local/bin/pwsh /usr/local/microsoft/powershell
```

Чтобы удалить дополнительные пути PowerShell, ознакомьтесь с разделом [пути](#paths) этой статьи, и удалите необходимые пути с помощью команды `sudo rm`.

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
Поэтому профили конкретных узлов по умолчанию находятся в `Microsoft.PowerShell_profile.ps1` в тех же расположениях.

PowerShell отвечает требованиям [спецификации каталога размещения файлов, связанных со средой настольной графической среды (X-сервера), стандартизированного XDG (X Desktop Group)][xdg-bds] в macOS.

Так как macOS является развитием BSD, необходимо использовать префикс `/usr/local` вместо `/opt`.
Таким образом, `$PSHOME` имеет значение `/usr/local/microsoft/powershell/6.1.0/`, а символьная ссылка размещается в `/usr/local/bin/pwsh`.

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
