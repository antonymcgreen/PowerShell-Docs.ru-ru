---
title: Установка модуля PowerShell | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb82827e-fdb7-4cbf-b3d4-093e72b3ff0e
caps.latest.revision: 28
ms.openlocfilehash: 60ac4bf9089232a9fa879e835e32da53422489fd
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "72367073"
---
# <a name="installing-a-powershell-module"></a>Установка модуля PowerShell

После создания модуля PowerShell, вероятно, потребуется установить модуль в системе, чтобы вы или другие могли его использовать. В целом, это состоит из копирования файлов модулей (Internet Explorer,. PSM1 или двоичной сборки, манифеста модуля и других связанных файлов) в каталог на этом компьютере. Для очень маленького проекта это может быть просто копированием и вставлением файлов с помощью проводника Windows на один удаленный компьютер. Однако для более крупных решений может потребоваться более сложный процесс установки. Независимо от того, как вы получаете модуль в системе, PowerShell может использовать ряд методов, позволяющих пользователям находить и использовать ваши модули. Поэтому основная ошибка установки гарантирует, что PowerShell сможет найти ваш модуль. Дополнительные сведения см. [в разделе Импорт модуля PowerShell](./importing-a-powershell-module.md).

## <a name="rules-for-installing-modules"></a>Правила установки модулей

Следующие сведения относятся ко всем модулям, включая модули, созданные для собственного использования, модули, получаемые от других сторон, и модули, распространяемые другим пользователям.

### <a name="install-modules-in-psmodulepath"></a>Установка модулей в PSModulePath

Когда это возможно, установите все модули в пути, указанном в переменной среды **PSModulePath** , или добавьте путь к модулю в значение переменной среды **PSModulePath** .

Переменная среды **PSModulePath** ($env:P смодулепас) содержит расположение модулей Windows PowerShell. Командлеты используют значение этой переменной среды для поиска модулей.

По умолчанию значение переменной среды **PSModulePath** содержит следующие системные и пользовательские каталоги модулей, но можно добавлять и изменять значения.

- `$PSHome\Modules` (%Windir%\System32\WindowsPowerShell\v1.0\Modules)

  > [!WARNING]
  > Это расположение зарезервировано для модулей, поставляемых с Windows. Не устанавливайте модули в это расположение.

- `$Home\Documents\WindowsPowerShell\Modules` (%Усерпрофиле%\документс\виндовсповершелл\модулес)

- `$Env:ProgramFiles\WindowsPowerShell\Modules` (%Програмфилес%\виндовсповершелл\модулес)

  Чтобы получить значение переменной среды **PSModulePath** , используйте одну из следующих команд.

  ```powershell
  $Env:PSModulePath
  [Environment]::GetEnvironmentVariable("PSModulePath")
  ```

  Чтобы добавить путь к модулю в значение переменной среды **PSModulePath** , используйте следующий формат команды: Этот формат использует метод **SetEnvironmentVariable** класса **System. Environment** , чтобы сделать независимым от сеанса изменение переменной среды **PSModulePath** .

  ```powershell
  #Save the current value in the $p variable.
  $p = [Environment]::GetEnvironmentVariable("PSModulePath")

  #Add the new path to the $p variable. Begin with a semi-colon separator.
  $p += ";C:\Program Files (x86)\MyCompany\Modules\"

  #Add the paths in $p to the PSModulePath value.
  [Environment]::SetEnvironmentVariable("PSModulePath",$p)

  ```

  > [!IMPORTANT]
  > После добавления пути к **PSModulePath**следует транслировать сообщение окружения об изменении. Широковещательная рассылка изменений позволяет другим приложениям, таким как оболочка, принимать изменения. Чтобы выполнить широковещательную рассылку изменений, попросите код установки продукта отправить **WM_SETTINGCHANGE** сообщение с `lParam` для строки "Environment". Не забудьте отправить сообщение после того, как код установки модуля обновил **PSModulePath**.

### <a name="use-the-correct-module-directory-name"></a>Использовать правильное имя каталога модулей

Правильно сформированный модуль — это модуль, хранящийся в каталоге, имя которого совпадает с базовым именем по крайней мере одного файла в каталоге модуля. Если модуль не имеет правильного формата, Windows PowerShell не распознает его как модуль.

"Базовое имя" файла — это имя без расширения имени файла. В правильно оформленном модуле имя каталога, содержащего файлы модулей, должно совпадать с базовым именем по крайней мере одного файла в модуле.

Например, в примере модуля Fabrikam каталог, содержащий файлы модулей, называется Fabrikam, а по крайней мере один файл имеет базовое имя "Fabrikam". В этом случае Fabrikam. PSD1 и Fabrikam. DLL имеют базовое имя "Fabrikam".

```
C:\Program Files
  Fabrikam Technologies
    Fabrikam Manager
      Modules
        Fabrikam
          Fabrikam.psd1 (module manifest)
          Fabrikam.dll (module assembly)

```

### <a name="effect-of-incorrect-installation"></a>Воздействие неправильной установки

Если модуль не имеет правильного формата и его расположение не включено в значение переменной среды **PSModulePath** , основные функции обнаружения Windows PowerShell, такие как следующие, не работают.

- Функция автоматической загрузки модуля не может автоматически импортировать модуль.

- Параметр `ListAvailable` командлета [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) не может найти модуль.

- Командлету [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) не удается найти модуль. Чтобы импортировать модуль, необходимо указать полный путь к файлу корневого модуля или файла манифеста модуля.

  Дополнительные функции, например следующие, не работают, если модуль не импортируется в сеанс. В модулях с правильным форматом в переменной среды **PSModulePath** эти функции работают даже в том случае, если модуль не импортируется в сеанс.

- Командлету [Get-Command](/powershell/module/Microsoft.PowerShell.Core/Get-Command) не удается найти команды в модуле.

- Командлеты [Update — Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) и [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) не могут обновить или сохранить справку для модуля.

- Командлету " [Показать-команда](/powershell/module/Microsoft.PowerShell.Utility/Show-Command) " не удается найти и отобразить команды в модуле.

  Команды в модуле отсутствуют в окне `Show-Command` в интегрированной среде сценариев Windows PowerShell (ISE).

## <a name="where-to-install-modules"></a>Место установки модулей

В этом разделе описывается, где в файловой системе устанавливаются модули Windows PowerShell. Расположение зависит от того, как используется модуль.

### <a name="installing-modules-for-a-specific-user"></a>Установка модулей для определенного пользователя

Если вы создаете собственный модуль или получаете модуль от другой стороны, например веб-сайт сообщества Windows PowerShell, и вам требуется, чтобы модуль был доступен только для вашей учетной записи пользователя, установите модуль в каталоге модулей для конкретных пользователей.

`$home\Documents\WindowsPowerShell\Modules\<Module Folder>\<Module Files>`

Каталог пользовательских модулей добавляется к значению переменной среды **PSModulePath** по умолчанию.

### <a name="installing-modules-for-all-users-in-program-files"></a>Установка модулей для всех пользователей в программных файлах

Если требуется, чтобы модуль был доступен для всех учетных записей пользователей на компьютере, установите модуль в папку Program Files.

`$Env:ProgramFiles\WindowsPowerShell\Modules\<Module Folder>\<Module Files>`

> [!NOTE]
> Расположение программных файлов добавляется в значение переменной среды PSModulePath по умолчанию в Windows PowerShell 4,0 и более поздних версиях. Для более ранних версий Windows PowerShell можно вручную создать расположение программных файлов ((%Програмфилес%\виндовсповершелл\модулес) и добавить этот путь в переменную среды PSModulePath, как описано выше.

### <a name="installing-modules-in-a-product-directory"></a>Установка модулей в каталоге продукта

Если вы распространяете модуль другим сторонам, используйте расположение программных файлов по умолчанию, описанное выше, или создайте собственный подкаталог, относящийся к конкретной компании или продукт, в каталоге% ProgramFiles%.

Например, технологии Fabrikam, вымышленная компания, поставляют модуль Windows PowerShell для своего продукта Fabrikam Manager. Установщик модуля создает подкаталог modules в подкаталоге продукта Fabrikam Manager.

```
C:\Program Files
  Fabrikam Technologies
    Fabrikam Manager
      Modules
        Fabrikam
          Fabrikam.psd1 (module manifest)
          Fabrikam.dll (module assembly)

```

Чтобы включить функции обнаружения модулей Windows PowerShell для поиска модуля Fabrikam, Установщик модуля Fabrikam добавляет расположение модуля в значение переменной среды **PSModulePath** .

```powershell
$p = [Environment]::GetEnvironmentVariable("PSModulePath")
$p += ";C:\Program Files\Fabrikam Technologies\Fabrikam Manager\Modules\"
[Environment]::SetEnvironmentVariable("PSModulePath",$p)
```

### <a name="installing-modules-in-the-common-files-directory"></a>Установка модулей в каталоге общих файлов

Если модуль используется несколькими компонентами продукта или несколькими версиями продукта, установите модуль в подкаталог, зависящий от модуля, в подкаталоге%ProgramFiles%\Common Филес\модулес.

В следующем примере модуль Fabrikam устанавливается в подкаталог Fabrikam подкаталога `%ProgramFiles%\Common Files\Modules`. Обратите внимание, что каждый модуль находится в отдельном подкаталоге в подкаталоге modules.

```
C:\Program Files
  Common Files
    Modules
      Fabrikam
        Fabrikam.psd1 (module manifest)
        Fabrikam.dll (module assembly)
```

Затем установщик гарантирует, что значение переменной среды **PSModulePath** включает путь к подкаталогу Common Files modules.

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

1. Создайте каталог для каждой версии модуля. Включить номер версии в имя каталога.
2. Создайте манифест модуля для каждой версии модуля. В поле **значение ключа "** в манифесте" введите номер версии модуля. Сохраните файл манифеста (. PSD1) в каталоге, зависящем от версии, для модуля.
3. Добавьте путь к корневой папке модуля в значение переменной среды **PSModulePath** , как показано в следующих примерах.

Чтобы импортировать определенную версию модуля, конечный пользователь может использовать `MinimumVersion` или `RequiredVersion` параметры командлета [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) .

Например, если модуль Fabrikam доступен в версиях 8,0 и 9,0, структура каталогов модуля Fabrikam может выглядеть следующим образом.

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

Установщик добавляет оба пути к модулю в значение переменной среды **PSModulePath** .

```powershell
$p = [Environment]::GetEnvironmentVariable("PSModulePath")
$p += ";C:\Program Files\Fabrikam\Fabrikam8;C:\Program Files\Fabrikam\Fabrikam9"
[Environment]::SetEnvironmentVariable("PSModulePath",$p)
```

После выполнения этих действий параметр **ListAvailable** командлета [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) получает оба модуля Fabrikam. Чтобы импортировать определенный модуль, используйте параметры `MinimumVersion` или `RequiredVersion` командлета [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) .

Если оба модуля импортируются в один сеанс, а модули содержат командлеты с одинаковыми именами, командлеты, импортируемые последними, вступают в силу в этом сеансе.

## <a name="handling-command-name-conflicts"></a>Обработка конфликтов имен команд

Конфликты имен команд могут возникать, когда команды, экспортируемые модулем, имеют те же имена, что и команды в сеансе пользователя.

Если сеанс содержит две команды с одинаковыми именами, Windows PowerShell выполняет тип команды, имеющий приоритет. Если сеанс содержит две команды с одинаковым именем и одним и тем же типом, Windows PowerShell выполняет команду, которая была добавлена в сеанс в последнее время. Чтобы выполнить команду, которая не выполняется по умолчанию, пользователи могут указать имя модуля в качестве имени команды.

Например, если сеанс содержит функцию `Get-Date` и командлет `Get-Date`, Windows PowerShell по умолчанию выполняет эту функцию. Чтобы выполнить командлет, перед командой введите имя модуля, например:

```powershell
Microsoft.PowerShell.Utility\Get-Date
```

Чтобы предотвратить конфликты имен, авторы модулей могут использовать ключ **DefaultCommandPrefix** в манифесте модуля, чтобы указать префикс существительное для всех команд, экспортируемых из модуля.

Пользователи могут использовать параметр **prefix** командлета `Import-Module` для использования альтернативного префикса. Значение параметра **prefix** имеет приоритет над значением ключа **DefaultCommandPrefix** .

## <a name="see-also"></a>См. также:

[about_Command_Precedence](/powershell/module/microsoft.powershell.core/about/about_command_precedence)

[Написание модуля Windows PowerShell](./writing-a-windows-powershell-module.md)
