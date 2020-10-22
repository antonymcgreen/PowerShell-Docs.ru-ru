---
title: Установка модуля PowerShell | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 201679c97acdccae9aa4c2be641ee1da09a8275c
ms.sourcegitcommit: d073e69708bd499ea42642b4b923ce5f11cca295
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/19/2020
ms.locfileid: "92197831"
---
# <a name="installing-a-powershell-module"></a>Установка модуля PowerShell

После создания модуля PowerShell вы, вероятно, захотите установить модуль в системе, чтобы его могли использовать не только вы, но и другие пользователи. В целом, этот процесс включает копирование файлов модулей (файлы PSM1 или двоичной сборки, манифеста модуля и другие связанные файлы) в каталог на этом компьютере. Для очень маленького проекта это может быть просто копирование и вставка файлов с помощью проводника Windows на один удаленный компьютер. Но для более крупных решений может потребоваться более сложный процесс установки. Независимо от того, как вы устанавливаете модуль в системе, PowerShell поддерживает ряд методов, с помощью которых пользователи могут находить и использовать ваши модули. Следовательно, основная задача установки — сделать так, чтобы ваш модуль был доступным для PowerShell. Дополнительные сведения см. в статье [Импорт модуля PowerShell](./importing-a-powershell-module.md).

## <a name="rules-for-installing-modules"></a>Правила установки модулей

Следующие сведения относятся ко всем модулям, включая модули, созданные для собственного использования, получаемые от других сторон и предоставляемые другим пользователям.

### <a name="install-modules-in-psmodulepath"></a>Установка модулей в PSModulePath

По возможности устанавливайте все модули по пути, указанному в переменной среды **PSModulePath**, или добавьте путь к модулю в значение переменной среды **PSModulePath**.

Переменная среды **PSModulePath** ($Env:PSModulePath) содержит сведения о расположении модулей Windows PowerShell. Командлеты используют значение этой переменной среды для поиска модулей.

По умолчанию значение переменной среды **PSModulePath** содержит следующие системные и пользовательские каталоги модулей, но вы можете добавлять и изменять это значение.

- `$PSHome\Modules` (%Windir%\System32\WindowsPowerShell\v1.0\Modules)

  > [!WARNING]
  > Это расположение зарезервировано для модулей, поставляемых с Windows. Не устанавливайте модули в это расположение.

- `$Home\Documents\WindowsPowerShell\Modules` (%UserProfile%\Documents\WindowsPowerShell\Modules)

- `$Env:ProgramFiles\WindowsPowerShell\Modules` (%ProgramFiles%\WindowsPowerShell\Modules)

  Чтобы получить значение переменной среды **PSModulePath**, используйте одну из следующих команд.

  ```powershell
  $Env:PSModulePath
  [Environment]::GetEnvironmentVariable("PSModulePath")
  ```

  Чтобы добавить путь к модулю в значение переменной среды **PSModulePath**, используйте следующий формат команды. В этом формате используется метод **SetEnvironmentVariable** класса **System.Environment**, чтобы сделать изменение переменной среды **PSModulePath** независимым от сеанса.

  ```powershell
  #Save the current value in the $p variable.
  $p = [Environment]::GetEnvironmentVariable("PSModulePath")

  #Add the new path to the $p variable. Begin with a semi-colon separator.
  $p += ";C:\Program Files (x86)\MyCompany\Modules\"

  #Add the paths in $p to the PSModulePath value.
  [Environment]::SetEnvironmentVariable("PSModulePath",$p)

  ```

  > [!IMPORTANT]
  > После добавления пути в **PSModulePath** выполните рассылку сообщения окружения об изменении. Так другие приложения, например оболочка, смогут поддерживать эти изменения. Для этого код установки продукта должен отправить сообщение **WM_SETTINGCHANGE** с параметром `lParam`, для которого задана строка Environment. Не забудьте отправить сообщение после того, как код установки модуля обновит **PSModulePath**.

### <a name="use-the-correct-module-directory-name"></a>Использование правильного имени каталога модулей

Модуль с правильным форматом — это модуль, хранящийся в каталоге, имя которого совпадает с базовым именем хотя бы одного файла в каталоге модуля. Если формат модуля неправильный, Windows PowerShell не распознает его как модуль.

Базовое имя файла — это имя файла без расширения. В модуле с правильным форматом имя каталога, содержащего файлы модулей, должно совпадать с базовым именем хотя бы одного файла в модуле.

Например, в примере модуля Fabrikam каталог, содержащий файлы модулей, называется Fabrikam, и хотя бы один файл имеет базовое имя Fabrikam. В этом случае и Fabrikam.psd1, и Fabrikam.dll имеют базовое имя Fabrikam.

```
C:\Program Files
  Fabrikam Technologies
    Fabrikam Manager
      Modules
        Fabrikam
          Fabrikam.psd1 (module manifest)
          Fabrikam.dll (module assembly)

```

### <a name="effect-of-incorrect-installation"></a>Результат неправильной установки

Если модуль имеет неправильный формат и его расположение не включено в значение переменной среды **PSModulePath**, основные функции обнаружения Windows PowerShell, описанные ниже, не будут работать.

- Функция автоматической загрузки модуля не сможет автоматически импортировать модуль.

- Параметр `ListAvailable` командлета [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) не сможет найти модуль.

- Командлет [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) не сможет найти модуль. Чтобы импортировать модуль, необходимо указать полный путь к файлу корневого модуля или файлу манифеста модуля.

  Дополнительные функции, описанные ниже, не будут работать, если модуль не импортируется в сеанс. В модулях с правильным форматом в переменной среды **PSModulePath** эти функции будут работать, даже если модуль не импортируется в сеанс.

- Командлет [Get-Command](/powershell/module/Microsoft.PowerShell.Core/Get-Command) не сможет найти команды в модуле.

- Командлеты [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) и [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) не смогут обновить или сохранить справку для модуля.

- Командлет [Show-Command](/powershell/module/Microsoft.PowerShell.Utility/Show-Command) не сможет найти и отобразить команды в модуле.

  Команды в модуле будут отсутствовать в окне `Show-Command` в интегрированной среде скриптов Windows PowerShell (ISE).

## <a name="where-to-install-modules"></a>Расположение для установки модулей

В этом разделе описывается, где в файловой системе устанавливаются модули Windows PowerShell. Расположение зависит от того, как используется модуль.

### <a name="installing-modules-for-a-specific-user"></a>Установка модулей для определенного пользователя

Если вы создаете собственный модуль или получаете модуль от другой стороны, например с веб-сайта сообщества Windows PowerShell, и вам нужно, чтобы модуль был доступен только для вашей учетной записи пользователя, установите модуль в пользовательском каталоге модулей.

`$home\Documents\WindowsPowerShell\Modules\<Module Folder>\<Module Files>`

Этот каталог добавляется в значение переменной среды **PSModulePath** по умолчанию.

### <a name="installing-modules-for-all-users-in-program-files"></a>Установка модулей для всех пользователей в программных файлах

Если вам нужно, чтобы модуль был доступен для всех учетных записей пользователей на компьютере, установите модуль в папку с программными файлами.

`$Env:ProgramFiles\WindowsPowerShell\Modules\<Module Folder>\<Module Files>`

> [!NOTE]
> Это расположение добавляется в значение переменной среды PSModulePath по умолчанию в Windows PowerShell 4.0 и более поздних версиях. Для более ранних версий Windows PowerShell можно вручную создать расположение программных файлов (%ProgramFiles%\WindowsPowerShell\Modules) и добавить этот путь в переменную среды PSModulePath, как описано выше.

### <a name="installing-modules-in-a-product-directory"></a>Установка модулей в каталоге продукта

Если вы предоставляете модуль другим сторонам, используйте каталог с программными файлами по умолчанию, как описано выше, или создайте собственный подкаталог для компании или продукта в каталоге %ProgramFiles%.

Например вымышленная компания Fabrikam Technologies предоставляет модуль Windows PowerShell для своего продукта Fabrikam Manager. Установщик модуля создает подкаталог Modules в подкаталоге продукта Fabrikam Manager.

```
C:\Program Files
  Fabrikam Technologies
    Fabrikam Manager
      Modules
        Fabrikam
          Fabrikam.psd1 (module manifest)
          Fabrikam.dll (module assembly)

```

Чтобы включить функции обнаружения модулей Windows PowerShell для поиска модуля Fabrikam, установщик модуля Fabrikam добавляет расположение модуля в значение переменной среды **PSModulePath**.

```powershell
$p = [Environment]::GetEnvironmentVariable("PSModulePath")
$p += ";C:\Program Files\Fabrikam Technologies\Fabrikam Manager\Modules\"
[Environment]::SetEnvironmentVariable("PSModulePath",$p)
```

### <a name="installing-modules-in-the-common-files-directory"></a>Установка модулей в каталоге с общими файлами

Если модуль используется несколькими компонентами или версиями продукта, установите модуль в подкаталог для модуля в подкаталоге %ProgramFiles%\Common Files\Modules.

В следующем примере модуль Fabrikam устанавливается в подкаталог Fabrikam в подкаталоге `%ProgramFiles%\Common Files\Modules`. Обратите внимание, что каждый модуль находится в отдельном подкаталоге в подкаталоге Modules.

```
C:\Program Files
  Common Files
    Modules
      Fabrikam
        Fabrikam.psd1 (module manifest)
        Fabrikam.dll (module assembly)
```

Затем установщик проверяет, что значение переменной среды **PSModulePath** содержит путь к подкаталогу модуля с общими файлами.

```powershell
$m = $env:ProgramFiles + '\Common Files\Modules'
$p = [Environment]::GetEnvironmentVariable("PSModulePath")
$q = $p -split ';'
if ($q -notContains $m) {
    $q += ";$m"
}
$p = $q -join ';'
[Environment]::SetEnvironmentVariable("PSModulePath", $p)
```

## <a name="installing-multiple-versions-of-a-module"></a>Установка нескольких версий модуля

Чтобы установить несколько версий одного модуля, выполните следующую процедуру.

1. Создайте каталог для каждой версии модуля. Включите номер версии в имя каталога.
2. Создайте манифест модуля для каждой версии модуля. В качестве значения ключа **ModuleVersion** в манифесте укажите номер версии модуля. Сохраните файл манифеста (.psd1) в каталоге для версии модуля.
3. Добавьте путь к корневой папке модуля в значение переменной среды **PSModulePath**, как показано в следующих примерах.

Чтобы импортировать определенную версию модуля, пользователь может использовать параметры `MinimumVersion` или `RequiredVersion` командлета [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module).

Например, если модуль Fabrikam доступен в версиях 8.0 и 9.0, структура каталогов модуля Fabrikam может выглядеть следующим образом:

 ```
C:\Program Files
Fabrikam Manager
  Fabrikam8
    Fabrikam
      Fabrikam.psd1 (module manifest: ModuleVersion = "8.0")
      Fabrikam.dll (module assembly)
  Fabrikam9
    Fabrikam
      Fabrikam.psd1 (module manifest: ModuleVersion = "9.0")
      Fabrikam.dll (module assembly)
```

Установщик добавляет оба пути к модулю в значение переменной среды **PSModulePath**.

```powershell
$p = [Environment]::GetEnvironmentVariable("PSModulePath")
$p += ";C:\Program Files\Fabrikam\Fabrikam8;C:\Program Files\Fabrikam\Fabrikam9"
[Environment]::SetEnvironmentVariable("PSModulePath",$p)
```

После выполнения этих действий параметр **ListAvailable** командлета [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) получает оба модуля Fabrikam. Чтобы импортировать определенный модуль, используйте параметры `MinimumVersion` или `RequiredVersion` командлета [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module).

Если оба модуля, которые содержат командлеты с одинаковыми именами, импортируются в один сеанс, в этом сеансе будут доступными командлеты, импортированные последними.

## <a name="handling-command-name-conflicts"></a>Обработка конфликтов имен команд

Конфликты имен команд могут возникать, когда команды, экспортируемые модулем, имеют те же имена, что и команды в сеансе пользователя.

Если сеанс содержит две команды с одинаковым именем, Windows PowerShell выполняет команду согласно приоритету по типу. Если сеанс содержит две команды с одинаковыми именем и типом, Windows PowerShell выполняет команду, которая была добавлена в сеанс последней. Чтобы выполнить команду, которая не выполняется по умолчанию, пользователи могут определить ее имя, используя имя модуля.

Например, если сеанс содержит функцию `Get-Date` и командлет `Get-Date`, Windows PowerShell по умолчанию выполняет эту функцию. Чтобы выполнить командлет, укажите перед командой имя модуля, например:

```powershell
Microsoft.PowerShell.Utility\Get-Date
```

Чтобы предотвратить конфликты имен, авторы модулей могут использовать ключ **DefaultCommandPrefix** в манифесте модуля, чтобы указать префикс существительного для всех команд, экспортируемых из модуля.

Чтобы применить альтернативный префикс, пользователи могут использовать параметр **Prefix** командлета `Import-Module`. Значение параметра **Prefix** имеет приоритет над значением ключа **DefaultCommandPrefix**.

## <a name="see-also"></a>См. также:

[about_Command_Precedence](/powershell/module/microsoft.powershell.core/about/about_command_precedence)

[Написание модуля Windows PowerShell](./writing-a-windows-powershell-module.md)
