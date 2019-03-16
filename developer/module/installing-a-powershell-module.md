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
ms.openlocfilehash: 7c2bfca50de4645676eafc01bbf23d9797e8b758
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58059785"
---
# <a name="installing-a-powershell-module"></a>Установка модуля PowerShell

После создания модуля PowerShell, скорее всего требуется установить модуль в системе, разработанных вами или другими может использовать его. Вообще говоря это просто состоит из копирования файлы модулей (ie, .psm1, или двоичную сборку, манифеста модуля и другие связанные файлы) на каталог на этом компьютере. Для очень небольшого проекта это может быть сложнее, чем копирование и вставка файлов с помощью обозревателя Windows на одном удаленном компьютере; Тем не менее для больших решений вы можете использовать более сложный процесс установки. Независимо от того, как можно получить модуль в систему PowerShell можно использовать ряд приемов, которые помогут пользователям находить и использовать модули. (Дополнительные сведения см. в разделе [импорт модуля PowerShell](./importing-a-powershell-module.md).) Таким образом основная проблема для установки является обеспечение, что PowerShell будут иметь возможность найти ваш модуль.

Данный раздел включает следующие подразделы:

- Правила для установки модулей

- Место установки модулей

- Установка нескольких версий модуля

- Конфликта имен команд обработки

## <a name="rules-for-installing-modules"></a>Правила для установки модулей

Следующее относится ко всем модулям, включая модули, созданные для собственного использования, модули, которые вы получаете от других производителей и модули, которые распределяют другим пользователям.

### <a name="install-modules-in-psmodulepath"></a>Установка модулей в PSModulePath

По возможности установите все модули в пути, указанному в **PSModulePath** переменной среды или добавить путь к модулю для **PSModulePath** значение переменной среды.

**PSModulePath** переменной среды ($Env: PSModulePath) содержит расположения модулей Windows PowerShell. Командлеты используют значение этой переменной среды, чтобы найти модули.

По умолчанию **PSModulePath** значение переменной среды содержит следующие системные и каталоги пользователей модуля, но можно добавить и изменить его.

- $PSHome\Modules (%Windir%\System32\WindowsPowerShell\v1.0\Modules)

  > [!WARNING]
  > Это расположение зарезервирован для модулей, входящие в состав Windows. Не следует устанавливать модули в этом расположении.

- $Home\Documents\WindowsPowerShell\Modules (%UserProfile%\Documents\WindowsPowerShell\Modules)

- $Env:ProgramFiles\WindowsPowerShell\Modules (%ProgramFiles%\WindowsPowerShell\Modules)

  Чтобы получить значение **PSModulePath** переменной среды, используйте один из следующих команд.

  ```powershell
  $Env:PSModulePath
  [Environment]::GetEnvironmentVariable("PSModulePath")
  ```

  Чтобы добавить путь к модулю значение **PSModulePath** переменной среды значение, используйте следующий формат команды. В этом формате используются **SetEnvironmentVariable** метод **System.Environment** класс для изменения независимый от сеанса к **PSModulePath** среды переменная.

  ```powershell

  #Save the current value in the $p variable.
  $p = [Environment]::GetEnvironmentVariable("PSModulePath")

  #Add the new path to the $p variable. Begin with a semi-colon separator.
  $p += ";C:\Program Files (x86)\MyCompany\Modules\"

  #Add the paths in $p to the PSModulePath value.
  [Environment]::SetEnvironmentVariable("PSModulePath",$p)

  ```

  > [!IMPORTANT]
  > После добавления пути к **PSModulePath**, следует широковещательных сообщение среду об изменении. Широковещательная рассылка изменение позволяет другие приложения, например оболочки получить изменения. Для передачи изменений, имеют код установки продукта отправки **WM_SETTINGCHANGE** сообщений с `lParam` равным строке «Среда». Не забудьте отправить сообщение после установки модуля кода был обновлен **PSModulePath**.

### <a name="use-the-correct-module-directory-name"></a>Укажите имя каталога правильный модуль

Модуль «правильного» — это модуль, хранится в каталог, содержащий имя, совпадающее с именем базовое имя хотя бы один файл в каталоге модуля. Если модуль не имеет правильный формат, Windows PowerShell не распознает его как модуль.

«Базовое имя «файла является имя без расширения имени файла. В модуле правильный формат имя каталога, который содержит файлы модуля должно соответствовать имени базового, по крайней мере одного файла в модуле.

Например в модуле Fabrikam образец в каталог, содержащий файлы модулей называется «Fabrikam» и по крайней мере один файл имеет базовое имя, «Fabrikam». В этом случае Fabrikam.psd1 и Fabrikam.dll иметь базовое имя «Fabrikam».

```
C:\Program Files
  Fabrikam Technologies
    Fabrikam Manager
      Modules
        Fabrikam
          Fabrikam.psd1 (module manifest)
          Fabrikam.dll (module assembly)

```

### <a name="effect-of-incorrect-installation"></a>Последствия неправильная установка

Если модуль не является правильным и его расположение не включается в значении параметра **PSModulePath** переменной среды, базового обнаружения функции Windows PowerShell, как указано ниже, не работают.

- Компонент модуля автоматическая загрузка не удается импортировать модуль автоматически.

- `ListAvailable` Параметр [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) командлету не удается найти модуль.

- [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) командлету не удается найти модуль. Чтобы импортировать модуль, необходимо указать полный путь к корневой файл модуля или файлу манифеста модуля.

  Дополнительные возможности, как указано ниже, не работают, если модуль импортируется в сеанс. В модули правильного формата в **PSModulePath** переменной среды, эти функции работают даже в том случае, если модуль не импортируется в сеанс.

- [Get-Command](/powershell/module/Microsoft.PowerShell.Core/Get-Command) командлету не удается найти команды в модуле.

- [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) и [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) командлеты не удается обновить или сохранить файлы справки для модуля.

- [Show-Command](/powershell/module/Microsoft.PowerShell.Utility/Show-Command) командлет не удается найти и отобразить команды в модуле.

  Команды в модуле отсутствуют `Show-Command` окна в Windows PowerShell среды (Интегрированная скриптов).

## <a name="where-to-install-modules"></a>Место установки модулей

В этом разделе объясняется в файловой системе для установки модулей Windows PowerShell. Расположение зависит от того, как используется модуль.

### <a name="installing-modules-for-a-specific-user"></a>Установка модулей для конкретного пользователя

Если создать собственный модуль или получить модуль от другой стороны, таких как веб-сайт сообщества Windows PowerShell, и требуется, чтобы модуль был доступен для учетной записи пользователя только, установите модуль в каталоге модулей конкретного пользователя.

```
$home\Documents\WindowsPowerShell\Modules\<Module Folder>\<Module Files>
```

Каталог Modules конкретного пользователя добавляется к значению **PSModulePath** переменной среды по умолчанию.

### <a name="installing-modules-for-all-users-in-program-files"></a>Установка модулей для всех пользователей в каталоге Program Files

Если требуется, чтобы модуль был доступен всем учетным записям пользователей на компьютере, установите модуль в папке Program Files.

```
$Env:ProgramFiles\WindowsPowerShell\Modules\<Module Folder>\<Module Files>
```

> [!NOTE]
> Расположение программных файлов добавляется к значению переменной среды PSModulePath по умолчанию в Windows PowerShell 4.0 и более поздних версий. Для более ранних версиях Windows PowerShell, можно вручную создать ((%ProgramFiles%\WindowsPowerShell\Modules) расположение Program Files и добавить этот путь в переменную среды PSModulePath, как описано выше.

### <a name="installing-modules-in-a-product-directory"></a>Установка модулей в каталоге продуктов

Если планируется распространять модуль другим сторонам, используйте расположение по умолчанию Program Files, описанных выше, или создайте собственные конкретной компании или конкретного продукта подкаталог в каталоге % ProgramFiles %.

Например Fabrikam технологий, вымышленной компании продается модуль Windows PowerShell для своего продукта Fabrikam Manager. Их установщика модулей создает подкаталог модули в подкаталоге продукта Fabrikam Manager.

```
C:\Program Files
  Fabrikam Technologies
    Fabrikam Manager
      Modules
        Fabrikam
          Fabrikam.psd1 (module manifest)
          Fabrikam.dll (module assembly)

```

Чтобы включить функции обнаружения, работающего в модуле Windows PowerShell найти модуль Fabrikam, установщика модулей Fabrikam добавляет расположение модуля значение **PSModulePath** переменной среды.

```powershell
$p = [Environment]::GetEnvironmentVariable("PSModulePath")
$p += "C:\Program Files\Fabrikam Technologies\Fabrikam Manager\Modules\"
[Environment]::SetEnvironmentVariable("PSModulePath",$p)
```

### <a name="installing-modules-in-the-common-files-directory"></a>Установка модулей в каталоге общих файлов

Если модуль используется в нескольких компонентах продукта или несколько версий продукта, установите модуль в подкаталоге каталога конкретного модуля в подкаталог в каталоге %ProgramFiles%\Common Files\Modules.

В следующем примере в подкаталоге каталога Fabrikam в подкаталог в каталоге %ProgramFiles%\Common Files\Modules установлен модуль Fabrikam. Обратите внимание на то, что каждый модуль находится в свой собственный подкаталог в подкаталоге модулей.

```
C:\Program Files
  Common Files
    Modules
      Fabrikam
        Fabrikam.psd1 (module manifest)
        Fabrikam.dll (module assembly)

```

Затем установщик гарантирует значение **PSModulePath** переменной среды включает в себя путь подкаталога, общие файлы модулей.

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

Чтобы установить несколько версий одного модуля, используйте следующую процедуру.

1. Создайте каталог для каждой версии модуля. Включите номер версии в имени каталога.

2. Создание манифеста модуля для каждой версии модуля. В значении параметра **ModuleVersion** ключа в манифесте, введите номер версии модуля. Сохраните файл манифеста (psd1) в каталоге конкретной версии модуля.

3. Добавьте путь к корневой папке модуля значению **PSModulePath** переменной среды, как показано в следующих примерах.

Чтобы импортировать определенную версию модуля, пользователь может использовать `MinimumVersion` или `RequiredVersion` параметры [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) командлета.

К примеру Если модуль Fabrikam доступна в версии 8.0 и 9.0, структура каталога Fabrikam модуля может выглядеть следующим образом.

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

Установщик добавляет Оба модуля путей к **PSModulePath** значение переменной среды.

```powershell
$p = [Environment]::GetEnvironmentVariable("PSModulePath")
$p += ";C:\Program Files\Fabrikam\Fabrikam8;C:\Program Files\Fabrikam\Fabrikam9"
[Environment]::SetEnvironmentVariable("PSModulePath",$p)
```

После выполнения этих действий, **ListAvailable** параметр [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) командлет получает обоих модулей Fabrikam. Чтобы импортировать определенного модуля, используйте `MinimumVersion` или `RequiredVersion` параметры [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) командлета.

Если оба модуля, импортируются в том же сеансе, а модули содержат командлеты с одинаковыми именами, командлеты, которые импортируются последнего вступают в силу в сеансе.

## <a name="handling-command-name-conflicts"></a>Конфликта имен команд обработки

Команда конфликты имен могут возникать, когда команды, которые экспортирует модуль имеют имя, совпадающее с именем команды в сеансе пользователя.

Если сеанс содержит две команды, которые имеют одинаковые имена, Windows PowerShell выполняет тип команды, который имеет более высокий приоритет. Если сеанс содержит две команды, которые имеют то же имя и тот же тип, Windows PowerShell выполняет команду, который был добавлен к сеансу наиболее недавно. Чтобы выполнить команду, которая выполняется не по умолчанию, пользователям можно уточнить имя команды с именем модуля.

Например, если сеанс содержит `Get-Date` функции и `Get-Date` командлета Windows PowerShell выполняет функцию по умолчанию. Для выполнения командлета, введите перед командой имя модуля, такие как:

```powershell
Microsoft.PowerShell.Utility\Get-Date
```

Чтобы предотвратить конфликты имен, авторы модулей могут использовать **DefaultCommandPrefix** экспорта ключа в манифесте модуля, чтобы указать предлог для всех команд из модуля.

Пользователи могут использовать **префикс** параметр `Import-Module` командлет, чтобы использовать альтернативный префикс. Значение **префикса** имеет приоритет над значением **DefaultCommandPrefix** ключ.

## <a name="see-also"></a>См. также

[about_Command_Precedence](/powershell/module/microsoft.powershell.core/about/about_command_precedence)

[Написание модуля Windows PowerShell](./writing-a-windows-powershell-module.md)
