---
title: Установка PowerShell в macOS
description: Сведения об установке PowerShell в macOS
ms.date: 02/02/2021
ms.openlocfilehash: 3ae1fe0eb29b4d826221a2c11db19bc18c3efba7
ms.sourcegitcommit: 4f1c2fe700b8a0544c59e371eb7cfbc6d852b185
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/17/2021
ms.locfileid: "100563207"
---
# <a name="installing-powershell-on-macos"></a>Установка PowerShell в macOS

Для работы с PowerShell 7.0 или более поздней версии требуется macOS 10.13 и выше. Все пакеты доступны на нашей странице [выпусками][] GitHub. После установки пакета запустите `pwsh` из терминала.

> [!NOTE]
> PowerShell 7.1 является обновлением на месте, при установке которого PowerShell Core версий 6.x и 7.0 удаляется.
>
> Папка `/usr/local/microsoft/powershell/6` заменяется на `/usr/local/microsoft/powershell/7`.
>
> Если вам нужно запустить более раннюю версию PowerShell Core параллельно с PowerShell 7.1, установите нужную версию, используя [архив двоичных файлов](#binary-archives).

Существует несколько способов установки PowerShell в macOS. Выберите для этого один из следующих методов:

- Установка с помощью Homebrew. Homebrew является предпочтительным диспетчером пакетов для macOS.
- Установка PowerShell через [Direct Download](#installation-via-direct-download)
- Установка из [архивов двоичных файлов](#binary-archives).

После установки PowerShell следует установить [OpenSSL](#installing-dependencies). OpenSSL требуется для удаленного взаимодействия PowerShell и операций CIM.

## <a name="installation-of-latest-stable-release-via-homebrew-on-macos-1013-or-higher"></a>Установка последнего стабильного выпуска с помощью Homebrew в macOS 10.13 или более поздней версии

Если команда `brew` не найдена, нужно установить Homebrew по [соответствующим инструкциям][brew].

Теперь можно установить PowerShell:

```sh
brew install --cask powershell
```

И наконец, убедитесь, что установка прошла без ошибок.

```sh
pwsh
```

После выпуска новых версий PowerShell обновите формулы Homebrew и PowerShell:

```sh
brew update
brew upgrade powershell --cask
```

> [!NOTE]
> Приведенные выше команды можно вызвать из узла PowerShell (pwsh), но затем потребуется выйти из оболочки PowerShell и перезапустить ее, чтобы завершить обновление и обновить значения в таблице `$PSVersionTable`.

[brew]: https://brew.sh/

## <a name="installation-of-latest-preview-release-via-homebrew-on-macos-1013-or-higher"></a>Установка последнего предварительного выпуска с помощью Homebrew в macOS 10.13 или более поздней версии

После установки Homebrew можно установить PowerShell. Сначала установите пакет [Cask-Versions][cask-versions], который позволит устанавливать альтернативные версии Cask-пакетов.

```sh
brew tap homebrew/cask-versions
```

Теперь можно установить PowerShell:

```sh
brew install --cask powershell-preview
```

И наконец, убедитесь, что установка прошла без ошибок.

```sh
pwsh-preview
```

После выпуска новых версий PowerShell обновите формулы Homebrew и PowerShell:

```sh
brew update
brew upgrade powershell-preview --cask
```

> [!NOTE]
> Команду, указанную выше, можно вызвать на узле PowerShell (pwsh), но для этого необходимо завершить его обновление. Что в свою очередь будет сделано, когда вы выйдете из PowerShell и перезапустите его.
> Обновите значения, которые отображаются в `$PSVersionTable`.

Установка PowerShell с помощью метода tap Homebrew также поддерживается для стабильных версий и версий LTS.

```sh
brew install powershell/tap/powershell
```

Теперь можно проверить установку.

```sh
pwsh
```

После выпуска новых версий PowerShell просто выполните следующую команду.

```sh
brew upgrade powershell
```

> [!NOTE]
> Если вы используете метод cask или tap при обновлении до более новой версии PowerShell, используйте тот же метод, который применяли для первоначальной установки PowerShell. При использовании другого метода новый сеанс pwsh будет продолжать использовать старую версию PowerShell.
>
> Если вы решите использовать разные методы, существуют способы исправить проблему с помощью [метода Homebrew link](https://docs.brew.sh/Manpage#link-ln-options-formula).

## <a name="installation-via-direct-download"></a>Установка с помощью прямого скачивания

Для компьютера с macOS пакет PKG `powershell-7.1.2-osx-x64.pkg` можно загрузить на странице [Выпуски][].

Дважды щелкните файл и следуйте инструкциям на экране либо установите его из командной строки:

```sh
sudo installer -pkg powershell-7.1.2-osx-x64.pkg -target /
```

Установите [OpenSSL](#installing-dependencies). OpenSSL требуется для удаленного взаимодействия PowerShell и операций CIM.

## <a name="install-as-a-net-global-tool"></a>Установка в качестве глобального средства .NET

Если вы уже установили [пакет SDK для .NET Core](/dotnet/core/sdk), установите PowerShell как [глобальное средство .NET](/dotnet/core/tools/global-tools).

```
dotnet tool install --global PowerShell
```

Установщик инструмента dotnet добавляет `~/.dotnet/tools` в переменную среды `PATH`. Но в выполняющейся оболочке отсутствует обновленная переменная `PATH`. Вы можете запустить PowerShell из новой оболочки, введя `pwsh`.

Установите [OpenSSL](#installing-dependencies). OpenSSL требуется для удаленного взаимодействия PowerShell и операций CIM.

## <a name="binary-archives"></a>Архивы двоичных файлов

Для поддержки расширенных сценариев развертывания на платформе macOS доступны архивы `tar.gz` двоичных файлов PowerShell. При установке с помощью этого метода необходимо также вручную установить все зависимости.

Установите [OpenSSL](#installing-dependencies). OpenSSL требуется для удаленного взаимодействия PowerShell и операций CIM.

### <a name="installing-binary-archives-on-macos"></a>Установка архивов двоичных файлов в macOS

```sh
# Download the powershell '.tar.gz' archive
curl -L -o /tmp/powershell.tar.gz https://github.com/PowerShell/PowerShell/releases/download/v7.1.2/powershell-7.1.2-osx-x64.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /usr/local/microsoft/powershell/7.1.2

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /usr/local/microsoft/powershell/7.1.2

# Set execute permissions
sudo chmod +x /usr/local/microsoft/powershell/7.1.2/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /usr/local/microsoft/powershell/7.1.2/pwsh /usr/local/bin/pwsh
```

## <a name="installing-dependencies"></a>Установка зависимостей

OpenSSL требуется для удаленного взаимодействия PowerShell и операций CIM. При необходимости вы можете установить OpenSSL с помощью MacPorts.

> [!NOTE]
> MacPorts и Homebrew могут приводить к проблемам при совместном использовании в одной системе. Однако у Homebrew нет пакета для OpenSSL 1.0. Дополнительные сведения см. в разделе [Часто задаваемые вопросы о MacPorts](https://trac.macports.org/wiki/FAQ).

1. Установите средства командной строки Xcode. Средства Xcode требуются для MacPorts.

   ```sh
   xcode-select --install
   ```

1. Установите MacPorts. Инструкции см. в [руководстве по установке](https://www.macports.org/install.php).
1. Обновите MacPorts, выполнив команду `sudo port selfupdate`.
1. Обновите пакеты MacPorts, выполнив команду `sudo port upgrade outdated`.
1. Установите OpenSSL, запустив `sudo port install openssl10`.
1. Укажите ссылки на библиотеки, чтобы сделать их доступными для PowerShell:

   ```sh
   sudo mkdir -p /usr/local/opt/openssl
   sudo ln -s /opt/local/lib/openssl-1.0 /usr/local/opt/openssl/lib
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

- `$PSHOME` имеет значение `/usr/local/microsoft/powershell/7.1.2/`.
- Профили пользователей будут считаны из `~/.config/powershell/profile.ps1`.
- Профили по умолчанию будут считаны из `$PSHOME/profile.ps1`.
- Модули пользователей будут считаны из `~/.local/share/powershell/Modules`.
- Общие модули будут считаны из `/usr/local/share/powershell/Modules`.
- Модули по умолчанию будут считаны из `$PSHOME/Modules`.
- Журнал PSReadline будет записан в `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`.

Профили учитывают конфигурацию PowerShell для отдельных узлов. Профиль узла по умолчанию находится в `Microsoft.PowerShell_profile.ps1` в тех же расположениях.

PowerShell отвечает требованиям [спецификации каталога размещения файлов, связанных со средой настольной графической среды (X-сервера), стандартизированного XDG (X Desktop Group)][xdg-bds] в macOS.

Так как macOS является развитием BSD, необходимо использовать префикс `/usr/local` вместо `/opt`. Таким образом, `$PSHOME` имеет значение `/usr/local/microsoft/powershell/7.1.2/`, а символьная ссылка размещается в `/usr/local/bin/pwsh`.

## <a name="installation-support"></a>Поддержка установки

Корпорация Майкрософт поддерживает методы установки, изложенные в этом документе. В других источниках могут быть доступны другие методы установки. Хотя такие инструменты и методы могут работать, корпорация Майкрософт не поддерживает их.

## <a name="additional-resources"></a>Дополнительные ресурсы

- [Homebrew в Интернете][brew]
- [Репозиторий Homebrew на Github][GitHub]
- [Homebrew-Cask][cask]

[brew]: http://brew.sh/
[Cask]: https://github.com/Homebrew/homebrew-cask
[cask-versions]: https://github.com/Homebrew/homebrew-cask-versions
[GitHub]: https://github.com/Homebrew
[выпусками]: https://aka.ms/powershell-release?tag=stable
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
