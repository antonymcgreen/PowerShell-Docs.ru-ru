---
title: Миграция с Windows PowerShell 5.1 на PowerShell 7
description: Обновите PowerShell 5.1 до PowerShell 7 для платформ Windows.
ms.date: 03/25/2020
ms.openlocfilehash: cb14a4f159b6dc33f31386da4264c0ebb640aef8
ms.sourcegitcommit: 077488408c820c860131382324bdd576d0edf52a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "83809210"
---
# <a name="migrating-from-windows-powershell-51-to-powershell-7"></a>Миграция с Windows PowerShell 5.1 на PowerShell 7

Средство PowerShell 7, предназначенное для облачных, локальных и гибридных сред, теперь значительно усовершенствовано и предоставляет [новые возможности](../whats-new/What-s-New-in-PowerShell-70.md):

- установка и работа параллельно с Windows PowerShell;
- увеличенная совместимость с существующими модулями Windows PowerShell;
- новые языковые возможности, такие как тернарные операторы и `ForEach-Object -Parallel`;
- повышение производительности.
- удаленное взаимодействие на основе протокола SSH;
- межплатформенное взаимодействие;
- Поддержка контейнеров Docker

PowerShell 7 работает параллельно с Windows PowerShell, позволяя легко тестировать и сравнивать код в разных выпусках перед развертыванием. Миграция — это простой, быстрый и

PowerShell 7 поддерживается в следующих операционных системах Windows:

- Windows 8.1 и 10;
- Windows Server 2012, 2012 R2, 2016 и 2019

PowerShell 7 также работает в macOS и нескольких дистрибутивах Linux. Список поддерживаемых операционных систем и сведения о жизненном цикле поддержки см. в [этой статье](/powershell/scripting/powershell-support-lifecycle).

## <a name="installing-powershell-7"></a>Установка PowerShell 7

Для обеспечения гибких возможностей и в связи с требованиями ИТ-специалистов, инженеров DevOps, а также разработчиков доступно несколько вариантов установки PowerShell 7. В большинстве случаев варианты установки можно сократить до следующих методов:

- развертывание PowerShell с помощью [MSI-пакета](/powershell/scripting/install/installing-powershell-core-on-windows#installing-the-msi-package);
- развертывание PowerShell с помощью [ZIP-пакета](/powershell/scripting/install/installing-powershell-core-on-windows#installing-the-zip-package).

> [!NOTE]
> MSI-пакет можно развернуть и обновить с помощью таких продуктов для управления, как [System Center Configuration Manager (SCCM)](/configmgr/apps/). Скачайте пакеты на [странице выпусков GitHub](https://github.com/PowerShell/PowerShell/releases).

Для развертывания MSI-пакета требуются привилегии администратора. ZIP-пакет может развернуть любой пользователь. Установка с помощью ZIP-пакета — это самый простой способ установить PowerShell 7 для тестирования перед полной установкой.

## <a name="using-powershell-7-side-by-side-with-windows-powershell-51"></a>Параллельное использование Windows PowerShell 7 с Windows PowerShell 5.1

В средстве PowerShell 7 предусмотрена возможность сосуществовать с Windows PowerShell 5.1. Следующие свойства гарантируют защиту инвестиций в PowerShell и простоту миграции в PowerShell 7:

- отдельный путь установки и исполняемый файл;
- отдельная переменная PSModulePath;
- отдельный профиль для каждой версии;
- увеличенная совместимость модулей;
- новые конечные точки удаленного взаимодействия;
- поддержка групповой политики;
- отдельные журналы событий;

### <a name="separate-installation-path-and-executable-name"></a>Отдельный путь установки и исполняемый файл

PowerShell 7 устанавливается в новом каталоге и работает параллельно с Windows PowerShell 5.1.

Расположения установки по версии:

- Windows PowerShell 5.1: `$env:WINDIR\System32\WindowsPowerShell\v1.0`.
- PowerShell Core 6.x: `$env:ProgramFiles\PowerShell\6`.
- PowerShell 7: `$env:ProgramFiles\PowerShell\7`.

Новое расположение добавляется в переменную PATH, что позволяет запускать параллельно Windows PowerShell 5.1 и PowerShell 7. Если выполняется миграция с PowerShell Core 6.x в PowerShell 7, то PowerShell 6 удаляется и переменная PATH заменяется.

В Windows PowerShell исполняемый файл PowerShell называется `powershell.exe`. В версии 6 и более поздних версиях исполняемый файл называется `pwsh.exe`. Новое имя позволяет легко поддерживать параллельную работу обеих версий.

### <a name="separate-psmodulepath"></a>Отдельная переменная PSModulePath

По умолчанию Windows PowerShell и PowerShell 7 сохраняют модули в разных расположениях. В PowerShell 7 эти расположения объединены в переменную среды `$Env:PSModulePath`. При импорте модуля по имени PowerShell проверяет расположение, указанное с помощью `$Env:PSModulePath`. Это позволяет PowerShell 7 загружать как базовые модули (Core), так и предназначенные для компьютеров.

|            Область установки            |                Windows PowerShell 5.1                 |             PowerShell 7.0             |
| ----------------------------------- | ----------------------------------------------------- | -------------------------------------- |
| Модули PowerShell                  | `$env:WINDIR\system32\WindowsPowerShell\v1.0\Modules` | `$PSHOME\Modules`                      |
| Установленная пользователем<br>область AllUsers    | `$env:ProgramFiles\WindowsPowerShell\Modules`         | `$env:ProgramFiles\PowerShell\Modules` |
| Установленная пользователем<br>область CurrentUser | `$HOME\Documents\WindowsPowerShell\Modules`           | `$HOME\Documents\PowerShell\Modules`   |

В следующих примерах показаны значения `$Env:PSModulePath` по умолчанию для каждой версии.

- Для Windows PowerShell 5.1:

  ```powershell
  $Env:PSModulePath -split (';')
  ```

  ```Output
  C:\Users\<user>\Documents\WindowsPowerShell\Modules
  C:\Program Files\WindowsPowerShell\Modules
  C:\WINDOWS\System32\WindowsPowerShell\v1.0\Modules
  ```

- Для PowerShell 7:

  ```powershell
  $Env:PSModulePath -split (';')
  ```

  ```Output
  C:\Users\<user>\Documents\PowerShell\Modules
  C:\Program Files\PowerShell\Modules
  C:\Program Files\PowerShell\7\Modules
  C:\Program Files\WindowsPowerShell\Modules
  C:\WINDOWS\System32\WindowsPowerShell\v1.0\Modules
  ```

Обратите внимание, что PowerShell 7 включает пути Windows PowerShell и PowerShell 7 для обеспечения автоматической загрузки модулей.

> [!NOTE]
> Могут существовать дополнительные пути, если вы изменили переменную среды PSModulePath или установили пользовательские модули или приложения.

Дополнительные сведения о `PSModulePath` см. в разделе о [переменных среды](/powershell/module/microsoft.powershell.core/about/about_environment_variables#environment-variables-that-store-preferences).

Дополнительные сведения о модулях см. в [этой статье](/powershell/module/Microsoft.PowerShell.Core/About/about_Modules).

### <a name="separate-profiles"></a>Отдельные профили

Профиль PowerShell — это скрипт, который выполняется при запуске PowerShell. Этот скрипт настраивает среду, добавляя команды, псевдонимы, функции, переменные, модули и диски PowerShell. Скрипт профиля обеспечивает доступность этих настроек в каждом сеансе и отсутствие необходимости их повторного создания вручную.

Путь к расположению профиля в PowerShell 7 изменился.

- В Windows PowerShell 5.1 расположение профиля — `$HOME\Documents\WindowsPowerShell`.
- В PowerShell 7 расположение профиля — `$HOME\Documents\PowerShell`.

Имена файлов профилей также изменились:

   ```powershell
   PS> $PROFILE | Select-Object *Host* | Format-List

   AllUsersAllHosts       : C:\Program Files\PowerShell\7\profile.ps1
   AllUsersCurrentHost    : C:\Program Files\PowerShell\7\Microsoft.PowerShell_profile.ps1
   CurrentUserAllHosts    : C:\Users\<user>\Documents\PowerShell\profile.ps1
   CurrentUserCurrentHost : C:\Users\<user>\Documents\PowerShell\Microsoft.PowerShell_profile.ps1
   ```

Дополнительные сведения о профилях см. в [этой статье](/powershell/module/microsoft.powershell.core/about/about_profiles).

### <a name="powershell-7-compatibility-with-windows-powershell-51-modules"></a>Совместимость PowerShell 7 с модулями Windows PowerShell 5.1

Большинство модулей, используемых в Windows PowerShell 5.1, уже работают с PowerShell 7, в том числе Azure PowerShell и Active Directory. Мы продолжаем работать с другими командами над добавлением встроенной поддержки в PowerShell 7 большего числа модулей, в том числе Microsoft Graph, Office 365 и др. Текущий список поддерживаемых модулей см. в статье [Совместимость модулей PowerShell 7](/powershell/scripting/whats-new/module-compatibility).

> [!NOTE]
> В Windows мы также добавили переключатель **UseWindowsPowerShell** в `Import-Module`, чтобы упростить переход на PowerShell 7 для тех, кто использует несовместимые модули. Дополнительные сведения об этих функциональных возможностях см. в статье [О совместимости Windows PowerShell](/powershell/module/Microsoft.PowerShell.Core/About/about_windows_powershell_compatibility).

### <a name="powershell-remoting"></a>Удаленное взаимодействие PowerShell

Удаленное взаимодействие PowerShell позволяет выполнять любую команду PowerShell на одном или нескольких удаленных компьютерах. Вы можете устанавливать постоянные подключения, запускать интерактивные сеансы и выполнять скрипты на удаленных компьютерах.

#### <a name="ws-management-remoting"></a>Удаленное взаимодействие с использованием WS-Management

В Windows PowerShell 5.1 и более ранних версий используйте протокол WS-Management для согласования подключения и передачи данных. Служба удаленного управления Windows (WinRM) использует протокол WS-Management. Если служба WinRM включена, PowerShell 7 использует существующую конечную точку Windows PowerShell 5.1 с именем `Microsoft.PowerShell` для удаленных подключений. Чтобы обновить PowerShell 7 для включения собственной конечной точки, выполните командлет `Enable-PSRemoting`. Сведения о подключении к конкретным конечным точкам см. в статье [Удаленное взаимодействие с WS-Management (WSMan) в PowerShell Core](/powershell/scripting/learn/remoting/wsman-remoting-in-powershell-core).

Чтобы использовать службу удаленного взаимодействия Windows PowerShell, удаленный компьютер должен быть настроен для удаленного управления.
Дополнительные сведения, в том числе инструкции, см. в разделе [about_Remote_Requirements](/powershell/module/microsoft.powershell.core/about/about_remote_requirements).

Дополнительные сведения о работе с удаленным взаимодействием см. в статье [Об удаленном взаимодействии](/powershell/module/microsoft.powershell.core/about/about_remote).

#### <a name="ssh-based-remoting"></a>Удаленное взаимодействие на основе протокола SSH

Удаленное взаимодействие с использованием протокола SSH добавлено в PowerShell Core 6.x для поддержки в других операционных системах, которые не могут использовать собственные компоненты Windows, такие как **WinRM**. Функция удаленного взаимодействия по SSH создает хост-процесс PowerShell на целевом компьютере в качестве подсистемы SSH. Дополнительные сведения и примеры настройки удаленного взаимодействия на основе протокола SSH в Windows или Linux см. в статье [Удаленное взаимодействие PowerShell через SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).

> [!NOTE]
> Коллекция PowerShell (PSGallery) содержит модуль и командлет, который автоматически настраивает удаленное взаимодействие с использованием протокола SSH. Установите модуль `Microsoft.PowerShell.RemotingTools` из [PSGallery](https://www.powershellgallery.com/packages/Microsoft.PowerShell.RemotingTools/0.1.0) и выполните командлет `Enable-SSH`.

Командлеты `New-PSSession`, `Enter-PSSession` и `Invoke-Command` имеют новые наборы параметров для поддержки подключений SSH.

```powershell
[-HostName <string>]  [-UserName <string>]  [-KeyFilePath <string>]
```

Чтобы создать удаленный сеанс, укажите целевой компьютер с помощью параметра **HostName** и имя пользователя с помощью параметра **UserName**. При интерактивном выполнении командлетов отображается запрос на ввод пароля.

```powershell
Enter-PSSession -HostName <Computer> -UserName <Username>
```

Кроме того, при использовании параметра **HostName** укажите имя пользователя, за которым должен следовать символ (`@`) и затем имя компьютера.

```powershell
Enter-PSSession -HostName <Username>@<Computer>
```

Проверку подлинности ключа SSH можно настроить, используя файл закрытого ключа в параметре **KeyFilePath**.
Дополнительные сведения см. в статье [Управление ключами OpenSSH](/windows-server/administration/openssh/openssh_keymanagement).

### <a name="group-policy-supported"></a>Поддержка групповой политики

В PowerShell предусмотрены настройки групповой политики, позволяющие определить согласованные значения параметров для серверов в корпоративной среде. К числу этих параметров относятся следующие:

- Конфигурация сеанса консоли — задает конечную точку конфигурации, в которой выполняется PowerShell.
- "Включить ведение журнала модулей" — задает свойство LogPipelineExecutionDetails модулей.
- "Включить регистрацию блоков сценариев PowerShell" — включает подробное ведение журнала всех скриптов PowerShell.
- "Включить выполнение сценариев" — задает политику выполнения PowerShell.
- "Включить транскрипции PowerShell" — включает запись входных и выходных данных команд PowerShell в виде текстовых расшифровок
- "Задать исходный путь по умолчанию для Update-Help" — задает каталог (не в Интернете) в качестве источника для Updatable-Help (обновляемой справки).

Дополнительные сведения см. в статье [О параметрах групповой политики](/powershell/module/microsoft.powershell.core/about/about_group_policy_settings).

В PowerShell 7 предусмотрены шаблоны групповой политики и скрипт установки в `$PSHOME`.

Инструменты групповой политики используют файлы административных шаблонов (с расширениями `.admx`, `.adml`) для заполнения параметров политики в пользовательском интерфейсе. Это позволяет администраторам управлять параметрами политики на основе реестра. Скрипт `InstallPSCorePolicyDefinitions.ps1` устанавливает административные шаблоны PowerShell Core на локальном компьютере.

```powershell
Get-ChildItem -Path $PSHOME -Filter *Core*Policy*
```

```Output
    Directory: C:\Program Files\PowerShell\7

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           2/27/2020 12:38 AM          15861 InstallPSCorePolicyDefinitions.ps1
-a---           2/27/2020 12:28 AM           9675 PowerShellCoreExecutionPolicy.adml
-a---           2/27/2020 12:28 AM           6201 PowerShellCoreExecutionPolicy.admx
```

### <a name="separate-event-logs"></a>Отдельные журналы событий

Windows PowerShell и PowerShell 7 регистрируют события в отдельных журналах событий. Используйте следующую команду, чтобы получить список журналов PowerShell:

```powershell
Get-WinEvent -ListLog *PowerShell*
```

Дополнительные сведения см. в статье [О ведении журналов Windows](/powershell/module/microsoft.powershell.core/about/about_logging_windows).

## <a name="improved-editing-experience-with-visual-studio-code"></a>Улучшенные возможности редактирования с помощью Visual Studio Code

[Visual Studio Code (VS Code)](https://code.visualstudio.com/) с [расширением PowerShell](https://code.visualstudio.com/docs/languages/powershell) — поддерживаемая среда написания скриптов для PowerShell 7. Интегрированная среда сценариев (ISE) Windows PowerShell поддерживает только Windows PowerShell.

Обновленное расширение PowerShell включает в себя:

- новый режим совместимости ISE;
- PSReadLine в интегрированной консоли, в том числе выделение синтаксиса, многострочное редактирование и обратный поиск;
- повышенную стабильность работы и производительность;
- интеграцию с CodeLens;
- усовершенствованное автоматическое заполнение пути.

Чтобы упростить переход на Visual Studio Code, используйте возможность **Enable ISE Mode** (Включить режим ISE), доступную в **палитре команд**. Эта функция переключает VS Code в режим макета в стиле ISE. Режим макета в стиле ISE предоставляет все новые функции и возможности PowerShell в знакомом пользовательском интерфейсе.

Чтобы переключиться на новый макет ISE, нажмите клавиши <kbd>CTRL</kbd>+<kbd>SHIFT</kbd>+<kbd>P</kbd>, чтобы открыть **палитру команд**, введите `PowerShell` и выберите **PowerShell: Enable ISE Mode** (PowerShell: включить режим ISE).

Чтобы задать исходный макет, откройте **палитру команд** и выберите **PowerShell: Disable ISE Mode (restore to defaults)** (PowerShell: выключить режим ISE (восстановить значения по умолчанию)).

Дополнительные сведения о настройке макета VS Code для ISE см. в статье [Репликация функций интегрированной среды скриптов в Visual Studio Code](/powershell/scripting/components/vscode/how-to-replicate-the-ise-experience-in-vscode).

> [!NOTE]
> Обновления для ISE новыми возможностями сейчас не планируются. ISE в последних версиях Windows 10 и Windows Server теперь может удалить пользователь. Окончательное удаление ISE сейчас не планируется. Команда PowerShell и ее партнеры по работе сейчас работают над совершенствованием возможностей написания скриптов с использованием расширения PowerShell для Visual Studio Code.

## <a name="next-steps"></a>Next Steps

Теперь, когда вы узнали об эффективности миграции, [установите PowerShell 7](/powershell/scripting/install/installing-powershell-core-on-windows).
