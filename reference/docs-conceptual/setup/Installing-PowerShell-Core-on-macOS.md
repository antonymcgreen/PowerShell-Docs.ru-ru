# <a name="installing-powershell-core-on-macos"></a>Установка PowerShell Core в macOS

PowerShell Core поддерживает macOS версии 10.12 и более поздних версий
Все пакеты доступны на нашей странице [выпусков][] GitHub.
После установки пакета запустите `pwsh` из терминала.

### <a name="installation-via-homebrew-on-macos-1012"></a>Установка в macOS 10.12 с помощью Homebrew

[Homebrew][brew] является предпочтительным диспетчером пакетов для macOS.
Если команда `brew` не найдена, нужно установить Homebrew по [соответствующим инструкциям][brew].

После установки Homebrew установка PowerShell не вызывает проблем.
Сначала установите [Homebrew-Cask][cask], чтобы можно было установить дополнительные пакеты:

```sh
brew tap caskroom/cask
```

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
> Приведенные выше команды можно вызвать с узла PowerShell (pwsh), но затем потребуется выйти из оболочки PowerShell и перезапустить ее, чтобы завершить обновление и обновить значения в таблице $PSVersionTable.

[brew]: http://brew.sh/
[cask]: https://caskroom.github.io/

### <a name="installation-via-direct-download"></a>Установка с помощью прямого скачивания

Для компьютера с macOS пакет PKG `powershell-6.0.2-osx.10.12-x64.pkg` можно загрузить на странице [выпусков][].

Дважды щелкните файл и следуйте инструкциям на экране либо установите его из командной строки:

```sh
sudo installer -pkg powershell-6.0.2-osx.10.12-x64.pkg -target /
```

## <a name="binary-archives"></a>Архивы двоичных файлов

Для поддержки расширенных сценариев развертывания на платформах macOS и Linux доступны архивы двоичных файлов PowerShell `tar.gz`.

### <a name="installing-binary-archives-on-macos"></a>Установка архивов двоичных файлов в macOS

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

## <a name="uninstalling-powershell-core"></a>Удаление PowerShell Core

Если вы установили PowerShell с помощью Homebrew, удаление осуществляется очень просто:

```sh
brew cask uninstall powershell
```

Если вы установили PowerShell с помощью прямого скачивания, PowerShell нужно удалить вручную:

```sh
sudo rm -rf /usr/local/bin/pwsh /usr/local/microsoft/powershell
```

Чтобы удалить дополнительные пути PowerShell, ознакомьтесь с разделом [пути][] этой статьи, и удалите необходимые пути с помощью команды `sudo rm`.

> [!NOTE]
> Это не требуется в случае установки с помощью Homebrew.

[пути]:#paths

## <a name="paths"></a>Пути

* `$PSHOME` имеет значение `/usr/local/microsoft/powershell/6.0.2/`.
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
Таким образом, `$PSHOME` имеет значение `/usr/local/microsoft/powershell/6.0.2/`, а символьная ссылка размещается в `/usr/local/bin/pwsh`.

[выпусков]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
