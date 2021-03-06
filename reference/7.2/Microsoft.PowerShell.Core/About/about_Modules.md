---
description: Объясняет, как устанавливать, импортировать и использовать модули PowerShell.
Locale: en-US
ms.date: 12/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_modules?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Modules
ms.openlocfilehash: b98c8b27b68c213ac43fbd350ecd920f813dec6b
ms.sourcegitcommit: 7b376314e7640c39a53aac9f0db8bb935514a960
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2020
ms.locfileid: "99605292"
---
# <a name="about-modules"></a>О модулях

## <a name="short-description"></a>Краткое описание
Объясняет, как устанавливать, импортировать и использовать модули PowerShell.

## <a name="long-description"></a>Полное описание

Модуль — это пакет, содержащий члены PowerShell, такие как командлеты, поставщики, функции, рабочие процессы, переменные и псевдонимы.

Составляя команды, пользователи могут организовывать их с помощью модулей и передавать их другим пользователям. Пользователи, получающие модули, могут добавлять команды в модули в свои сеансы PowerShell и использовать их так же, как и встроенные команды.

В этом разделе объясняется, как использовать модули PowerShell. Сведения о том, как создавать модули PowerShell, см. в разделе [написание модуля PowerShell](/powershell/scripting/developer/module/writing-a-windows-powershell-module).

## <a name="what-is-a-module"></a>Что такое модуль?

Модуль — это пакет, содержащий члены PowerShell, такие как командлеты, поставщики, функции, рабочие процессы, переменные и псевдонимы. Члены этого пакета могут быть реализованы в сценарии PowerShell, скомпилированной библиотеке DLL или в сочетании обоих типов. Эти файлы обычно группируются в один каталог. Дополнительные сведения см. в разделе [понятие о модуле Windows PowerShell](/powershell/scripting/developer/module/understanding-a-windows-powershell-module) в документации по пакету SDK.

## <a name="module-auto-loading"></a>Автоматическая загрузка модуля

Начиная с PowerShell 3,0, PowerShell автоматически импортирует модули при первом выполнении любой команды в установленном модуле. Теперь для использования команд в модуле не требуется выполнять установку или настройку профиля, поэтому необходимость управления модулями после их установки на компьютере отпадает.

Также упрощен поиск команд в модуле. `Get-Command`Теперь командлет получает все команды во всех установленных модулях, даже если они еще не находятся в сеансе. Вы можете найти команду и использовать ее без импорта, чтобы сначала импортировать модуль.

В каждом из приведенных ниже примеров модуль Цимкмдлетс, который содержит `Get-CimInstance` , будет импортирован в сеанс.

- Выполните команду

  ```powershell
  Get-CimInstance Win32_OperatingSystem
  ```

- Получение команды

  ```powershell
  Get-Command Get-CimInstance
  ```

- Получение справки по команде

  ```powershell
  Get-Help Get-CimInstance
  ```

`Get-Command` команды, содержащие подстановочный знак ( `*` ), считаются для обнаружения, не используют и не импортируют модули.

Автоматически импортируются только те модули, которые хранятся в расположении, указанном в переменной среды PSModulePath. Модули в других расположениях необходимо импортировать, выполнив `Import-Module` командлет.

Кроме того, команды, использующие поставщики PowerShell, не импортируют модуль автоматически. Например, если вы используете команду, для которой требуется диск WSMan:, например `Get-PSSessionConfiguration` командлет, может потребоваться выполнить `Import-Module` командлет, чтобы импортировать модуль **Microsoft. WSMan. Management** , включающий `WSMan:` диск.

Вы по-прежнему можете выполнить `Import-Module` команду, чтобы импортировать модуль и использовать `$PSModuleAutoloadingPreference` переменную для включения, отключения и настройки автоматического импорта модулей. Дополнительные сведения см. в разделе [about_Preference_Variables](about_Preference_Variables.md).

## <a name="how-to-use-a-module"></a>Как использовать модуль

Чтобы воспользоваться модулем, выполните следующие действия.

1. Установите модуль. (Обычно это выполняется автоматически.)
1. Найдите команды, которые добавил модуль.
1. Теперь вы можете использовать эти команды.

В данном разделе описано, как выполнить эти задачи. В нем также содержатся другие полезные сведения об управлении модулями.

## <a name="how-to-install-a-module"></a>Установка модуля

Если вы получаете модуль в качестве папки с файлами в нем, его необходимо установить на компьютере, прежде чем его можно будет использовать в PowerShell.

Обычно модули устанавливаются автоматически. PowerShell поставляется с несколькими предварительно установленными модулями, которые иногда называют _основными_ модулями. На компьютерах под управлением Windows, если компоненты, включенные в операционную систему, имеют командлеты для управления ими, эти модули предварительно устанавливаются. При установке компонента Windows с помощью, например, мастера добавления ролей и компонентов в диспетчер сервера или в диалоговом окне Включение или отключение компонентов Windows на панели управления, устанавливаются все модули PowerShell, которые являются частью компонента. Многие модули поставляются с программой установки, выполняющей установку модуля.

Чтобы создать каталог **modules** для текущего пользователя, используйте следующую команду:

```powershell
New-Item -Type Directory -Path $HOME\Documents\PowerShell\Modules
```

Полностью скопируйте папку модуля в каталог Modules. Для копирования папки можно использовать любой метод, в том числе проводник Windows и Cmd.exe, а также PowerShell. В PowerShell используйте `Copy-Item` командлет. Например, чтобы скопировать папку MyModule из `C:\ps-test\MyModule` в каталог modules, введите:

```powershell
Copy-Item -Path C:\ps-test\MyModule -Destination `
    $HOME\Documents\PowerShell\Modules
```

Установить модуль можно в любое местоположение, однако если всегда устанавливать их в местоположение модулей по умолчанию, ими проще управлять. Дополнительные сведения о расположениях модулей по умолчанию см. в разделе [модули и расположения ресурсов DSC и PSModulePath](#module-and-dsc-resource-locations-and-psmodulepath) .

## <a name="how-to-find-installed-modules"></a>Поиск установленных модулей

Чтобы найти модули, установленные в местоположении модулей по умолчанию, но еще не импортированные в сеанс, введите следующее:

```powershell
Get-Module -ListAvailable
```

Чтобы найти модули, которые уже были импортированы в сеанс, в командной строке PowerShell введите следующую команду:

```powershell
Get-Module
```

Дополнительные сведения о `Get-Module` командлете см. в разделе [Get-Module](xref:Microsoft.PowerShell.Core.Get-Module).

## <a name="how-to-find-the-commands-in-a-module"></a>Как найти команды в модуле

Используйте `Get-Command` командлет, чтобы найти все доступные команды. Параметры `Get-Command` командлета можно использовать для фильтрации команд, таких как Module, Name и существительное.

Чтобы найти все команды в модуле, введите:

```powershell
Get-Command -Module <module-name>
```

Например, чтобы найти команды в модуле BitsTransfer, введите:

```powershell
Get-Command -Module BitsTransfer
```

Дополнительные сведения о `Get-Command` командлете см. в разделе [Get-Command](xref:Microsoft.PowerShell.Core.Get-Command).

## <a name="how-to-get-help-for-the-commands-in-a-module"></a>Получение справки по командам в модуле

Если модуль содержит файлы справки для экспортируемых команд, то в `Get-Help` командлете будут отображаться разделы справки. Используйте тот же `Get-Help` Формат команды, который используется для получения справки по любой команде в PowerShell.

Начиная с PowerShell 3,0 можно скачать файлы справки для модуля и загрузить обновления в файлы справки, чтобы они никогда не были устаревшими.

Чтобы найти раздел справки по содержащимся в модуле командам, введите следующее:

```powershell
Get-Help <command-name>
```

Чтобы получить справку в Интернете для команды в модуле, введите:

```powershell
Get-Help <command-name> -Online
```

Чтобы скачать и установить файлы справки для команд в модуле, введите:

```powershell
Update-Help -Module <module-name>
```

Дополнительные сведения см. в разделе [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) и [Update-Help](xref:Microsoft.PowerShell.Core.Update-Help).

## <a name="how-to-import-a-module"></a>Импорт модуля

Может потребоваться выполнить импорт модуля или файла модуля. Импорт требуется, если модуль не установлен в расположениях, указанных в переменной среды **PSModulePath** , `$env:PSModulePath` или модуль состоит из файла, такого как DLL или PSM1, вместо обычного модуля, который доставляется в виде папки.

Можно также импортировать модуль, чтобы можно было использовать параметры `Import-Module` команды, такие как параметр prefix, который добавляет отличительный префикс к именам существительных всех импортированных команд или параметр **NoClobber** , который предотвращает добавление в модуль команд, которые скрывают или заменяют существующие команды в сеансе.

Чтобы импортировать модули, используйте `Import-Module` командлет.

Чтобы импортировать модули в расположении PSModulePath в текущий сеанс, используйте следующий формат команды.

```powershell
Import-Module <module-name>
```

Например, следующая команда импортирует модуль BitsTransfer в текущий сеанс.

```powershell
Import-Module BitsTransfer
```

Чтобы импортировать модуль, не находящийся в местоположении по умолчанию, укажите в команде полный путь к папке этого модуля.

Например, чтобы добавить модуль TestCmdlets в `C:\ps-test` Каталог сеанса, введите:

```powershell
Import-Module C:\ps-test\TestCmdlets
```

Чтобы импортировать файл модуля, который не расположен в папке модуля, укажите в команде полный путь к файлу модуля.

Например, чтобы добавить модуль TestCmdlets.dll в `C:\ps-test` Каталог сеанса, введите:

```powershell
Import-Module C:\ps-test\TestCmdlets.dll
```

Дополнительные сведения о добавлении модулей в сеанс см. в разделе [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module).

## <a name="how-to-import-a-module-into-every-session"></a>Импорт модуля в каждый сеанс

`Import-Module`Команда импортирует модули в текущий сеанс PowerShell. Чтобы импортировать модуль в каждый запущенный сеанс PowerShell, добавьте `Import-Module` команду в профиль PowerShell.

Дополнительные сведения о профилях см. в разделе [about_Profiles](about_Profiles.md).

## <a name="how-to-remove-a-module"></a>Удаление модуля

Если удалить модуль, добавленные им команды удаляются из сеанса.

Чтобы удалить модуль из сеанса, используйте следующий формат команды:

```powershell
Remove-Module <module-name>
```

Например, следующая команда удаляет модуль BitsTransfer из текущего сеанса.

```powershell
Remove-Module BitsTransfer
```

Удаление модуля отменяет операцию импорта модуля. При этом установка модуля не отменяется. Дополнительные сведения см. в разделе [Remove-Module](xref:Microsoft.PowerShell.Core.Remove-Module).

## <a name="module-and-dsc-resource-locations-and-psmodulepath"></a>Расположение модулей и ресурсов DSC, а PSModulePath

`$env:PSModulePath`Переменная среды содержит список расположений папок, в которых выполняется поиск модулей и ресурсов.

По умолчанию действующие расположения, назначенные, `$env:PSModulePath` являются:

- Расположение на уровне системы: `$PSHOME\Modules`

  Эти папки содержат модули, поставляемые с Windows и PowerShell.

  Ресурсы DSC, входящие в состав PowerShell, хранятся в `$PSHOME\Modules\PSDesiredStateConfiguration\DSCResources` папке.

- Пользовательские модули: это модули, устанавливаемые пользователем в области пользователя. `Install-Module` имеет параметр **области** , который позволяет указать, установлен ли модуль для текущего пользователя или для всех пользователей. Дополнительные сведения см. в разделе [Install-Module](xref:PowerShellGet.Install-Module).

  Расположение **CurrentUser** для конкретного пользователя в Windows — это `PowerShell\Modules` Папка, расположенная в папке **Documents** в профиле пользователя. Конкретный путь к этому расположению зависит от версии Windows, а также от того, используется ли перенаправление папок. Microsoft OneDrive также может изменить расположение папки **документов** .

  По умолчанию в Windows 10 это расположение имеет значение `$HOME\Documents\PowerShell\Modules` . В Linux или Mac расположение **CurrentUser** — `$HOME/.local/share/powershell/Modules` .

  > [!NOTE]
  > Расположение папки **документов** можно проверить с помощью следующей команды: `[Environment]::GetFolderPath('MyDocuments')` .

- Расположение **ALLUSERS** находится `$env:PROGRAMFILES\PowerShell\Modules` в Windows. В Linux или Mac модули хранятся в `/usr/local/share/powershell/Modules` .

> [!NOTE]
> Чтобы добавить или изменить файлы в `$env:Windir\System32` каталоге, запустите PowerShell с параметром **Запуск от имени администратора** .

Вы можете изменить расположение модулей по умолчанию в системе, изменив значение переменной среды **PSModulePath** , `$Env:PSModulePath` . Переменная среды **PSModulePath** моделируется в переменной среды PATH и имеет тот же формат.

Чтобы отобразить местоположения модулей по умолчанию, введите следующую команду:

```powershell
$Env:PSModulePath
```

Чтобы добавить местоположение модулей по умолчанию, используйте следующий формат команды:

```powershell
$Env:PSModulePath = $Env:PSModulePath + ";<path>"
```

Точка с запятой ( `;` ) в команде отделяет новый путь от пути, расположенного перед ним в списке.

Например, чтобы добавить `C:\ps-test\Modules` каталог, введите:

```powershell
$Env:PSModulePath + ";C:\ps-test\Modules"
```

Чтобы добавить расположение модуля по умолчанию в Linux или MacOS, используйте следующий формат команды:

```powershell
$Env:PSModulePath += ":<path>"
```

Например, чтобы добавить `/usr/local/Fabrikam/Modules` Каталог к значению переменной среды **PSModulePath** , введите:

```powershell
$Env:PSModulePath += ":/usr/local/Fabrikam/Modules"
```

В Linux или MacOS двоеточие ( `:` ) в команде отделяет новый путь от пути, расположенного перед ним в списке.

При добавлении пути к **PSModulePath** `Get-Module` `Import-Module` команды также включают модули в этом пути.

Задаваемое значение влияет только на текущий сеанс. Чтобы сделать это изменение постоянным, добавьте команду в профиль PowerShell или используйте элемент система на панели управления, чтобы изменить значение переменной среды **PSModulePath** в реестре.

Кроме того, чтобы сделать это изменение постоянным, можно также использовать метод **SetEnvironmentVariable** класса **System. Environment** , чтобы добавить путь к переменной среды **PSModulePath** .

Дополнительные сведения о переменной **PSModulePath** см. в разделе [about_Environment_Variables](about_Environment_Variables.md).

## <a name="modules-and-name-conflicts"></a>Конфликты модулей и имен

Конфликт имен происходит, когда в сеансе имеется несколько команд с одинаковым именем. При импорте модуля возникает конфликт имен, если содержащиеся в нем команды имеют такие же имена, как команды или элементы, уже имеющиеся в сеансе.

Конфликты имен могут возникать в результате скрытия или замены команд.

### <a name="hidden"></a>Скрытый

Скрытой называется команда, не выполняемая при вводе ее имени, но выполняемая другими способами (например, с указанием имени модуля или оснастки, из которой добавлена команда).

### <a name="replaced"></a>Замененный текст

Замененной называется команда, которую невозможно выполнить, поскольку поверх нее записана команда с таким же именем. Даже если удалить модуль, являющийся причиной конфликта, выполнить замененную команду можно только после перезапуска сеанса.

`Import-Module` может добавлять команды, которые скрывают и заменяют команды в текущем сеансе. Кроме того, команды в текущем сеансе могут скрыть команды, добавленные модулем.

Чтобы обнаружить конфликты имен, используйте параметр **ALL** `Get-Command` командлета. Начиная с PowerShell 3,0, `Get-Command` получает только те команды, которые выполняются при вводе имени команды. Параметр **ALL** получает все команды с указанным именем в сеансе.

Чтобы предотвратить конфликты имен, используйте параметры **NoClobber** или **prefix** `Import-Module` командлета. Параметр **prefix** добавляет префикс к именам импортированных команд, чтобы они были уникальными в сеансе. Параметр **NoClobber** не импортирует команды, которые скрывают или заменяют существующие команды в сеансе.

Можно также использовать параметры **псевдонима**, **командлета**, **функции** и **переменной** , `Import-Module` чтобы выбрать только те команды, которые необходимо импортировать, а также исключить команды, вызывающие конфликты имен в сеансе.

Авторы модулей могут предотвратить конфликты имен, используя свойство **DefaultCommandPrefix** манифеста модуля для добавления префикса по умолчанию ко всем именам команд.
Значение параметра **prefix** имеет приоритет над значением **DefaultCommandPrefix**.

Даже если команда скрыта, можно выполнить ее, указав (помимо ее имени) имя модуля или оснастки, из которой она добавлена.

Правила очередности команд PowerShell определяют, какие команды выполняются, когда сеанс включает команды с тем же именем.

Например, если сеанс включает функцию и командлет с тем же именем, по умолчанию PowerShell выполняет эту функцию. Если сеанс содержит команды одинакового типа (например, два командлета) с одинаковым именем, по умолчанию выполняется команда, добавленная последней.

Дополнительные сведения, включая описание правил приоритета и инструкции по выполнению скрытых команд, см. в разделе [about_Command_Precedence](about_Command_Precedence.md).

## <a name="modules-and-snap-ins"></a>Модули и оснастки

В сеанс можно добавлять команды из модулей и оснасток. Модули могут добавлять все типы команд, в том числе командлеты, поставщики и функции, а также элементы, такие как переменные, псевдонимы и диски PowerShell. Из оснасток можно добавлять только командлеты и поставщики.

Прежде чем удалить модуль или оснастку из сеанса, с помощью следующих команд определите, какие команды будут при этом удалены

Чтобы найти источник командлета в сеансе, используйте следующий формат команды:

```powershell
Get-Command <cmdlet-name> | Format-List -Property verb,noun,pssnapin,module
```

Например, чтобы найти источник `Get-Date` командлета, введите:

```powershell
Get-Command Get-Date | Format-List -Property verb,noun,module
```

## <a name="module-related-warnings-and-errors"></a>Предупреждения и ошибки, связанные с модулем

Команды, экспортируемые модулем, должны следовать правилам именования команд PowerShell. Если импортируемый модуль экспортирует командлеты или функции с неодобренными командами в именах, `Import-Module` командлет выводит следующее предупреждающее сообщение.

> ПРЕДУПРЕЖДЕНИЕ. Некоторые импортированные имена команд включают неутвержденные команды, которые могут сделать их менее обнаруживаемыми. Чтобы получить подробные сведения, используйте параметр Verbose, или введите Get-Verb, чтобы просмотреть список утвержденных команд.

Это сообщение является всего лишь предупреждением. Импорт осуществляется для всего модуля, включая недопустимые команды. Хотя это сообщение отображается для пользователей модуля, проблема с именованием должна быть устранена автором модуля.

Чтобы отключить предупреждающее сообщение, используйте параметр **DisableNameChecking** `Import-Module` командлета.

## <a name="built-in-modules-and-snap-ins"></a>Встроенные модули и оснастки

В PowerShell 2,0 и в более старых основных программах в PowerShell 3,0 и более поздних версиях основные команды, устанавливаемые с помощью PowerShell, упаковываются в оснастки, которые автоматически добавляются во все сеансы PowerShell.

Начиная с PowerShell 3,0, для ведущих программ, которые реализуют `InitialSessionState.CreateDefault2` начальный API состояния сеанса, оснастка Microsoft. PowerShell. Core добавляется в каждый сеанс по умолчанию. Модули загружаются автоматически при первом использовании.

> [!NOTE]
> Удаленные сеансы, включая сеансы, запущенные с помощью `New-PSSession` командлета, — это сеансы предыдущих версий, в которых встроенные команды упаковываются в оснастки.

Следующие модули (или оснастки) устанавливаются с помощью PowerShell.

- CimCmdlets
- Microsoft.PowerShell.Archive
- Microsoft.PowerShell.Core
- Microsoft.PowerShell.Diagnostics
- Microsoft.PowerShell.Host
- Microsoft.PowerShell.Management
- Microsoft.PowerShell.Security
- Microsoft.PowerShell.Utility
- Microsoft.WSMan.Management
- PackageManagement
- PowerShellGet
- PSDesiredStateConfiguration
- PSDiagnostics
- PSReadline

## <a name="logging-module-events"></a>События модуля ведения журнала

Начиная с версии PowerShell 3,0 можно записывать события выполнения для командлетов и функций в модулях PowerShell и оснастках, установив свойство **LogPipelineExecutionDetails** модулей и оснасток в значение `$True` .
Можно также использовать параметр групповая политика, включить ведение журнала модуля, чтобы включить ведение журнала модуля во всех сеансах PowerShell. Дополнительные сведения см. в статьях ведение журналов и групповая политика.

## <a name="see-also"></a>См. также:

[about_Logging_Windows](about_Logging_Windows.md)

[about_Logging_Non — Windows](about_Logging_Non-Windows.md)

[about_Group_Policy_Settings](about_Group_Policy_Settings.md)

[about_Command_Precedence](about_Command_Precedence.md)

[about_Group_Policy_Settings](about_Group_Policy_Settings.md)

[Get-Command](xref:Microsoft.PowerShell.Core.Get-Command)

[Get-Help](xref:Microsoft.PowerShell.Core.Get-Help)

[Get-Module](xref:Microsoft.PowerShell.Core.Get-Module)

[Import-Module](xref:Microsoft.PowerShell.Core.Import-Module)

[Remove-Module](xref:Microsoft.PowerShell.Core.Remove-Module)
