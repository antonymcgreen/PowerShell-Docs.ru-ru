---
title: Изменение пути установки PSModulePath | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 795f2bd52aeceddd3c0ca092d0c0cf2ef44bcf23
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784849"
---
# <a name="modifying-the-psmodulepath-installation-path"></a>Изменение пути установки PSModulePath

`PSModulePath`Переменная среды сохраняет пути к расположениям модулей, установленных на диске. PowerShell использует эту переменную для поиска модулей, когда пользователь не указал полный путь к модулю. Пути в этой переменной ищутся в том порядке, в котором они отображаются.

При запуске PowerShell `PSModulePath` создается как системная переменная среды со следующим значением по умолчанию: `$HOME\Documents\PowerShell\Modules; $PSHOME\Modules` в Windows и `$HOME/.local/share/powershell/Modules: usr/local/share/powershell/Modules` в Linux или Mac, а также `$HOME\Documents\WindowsPowerShell\Modules; $PSHOME\Modules` для Windows PowerShell.

> [!NOTE]
> Заданное пользователем расположение **CurrentUser** — это `WindowsPowerShell\Modules` Папка, расположенная в папке **Documents** в профиле пользователя. Конкретный путь к этому расположению зависит от версии Windows, а также от того, используется ли перенаправление папок. По умолчанию в Windows 10 это расположение имеет значение `$HOME\Documents\WindowsPowerShell\Modules` .

## <a name="to-view-the-psmodulepath-variable"></a>Просмотр переменной PSModulePath

Чтобы просмотреть пути, указанные в `PSModulePath` переменной, введите следующую команду:

`$env:PSModulePath`

## <a name="to-add-locations-to-the-psmodulepath-variable"></a>Добавление расположений в переменную PSModulePath

Чтобы добавить пути к этой переменной, используйте один из следующих методов.

- Чтобы добавить временное значение, доступное только для текущего сеанса, выполните в командной строке следующую команду:

  `$env:PSModulePath = $env:PSModulePath + "$([System.IO.Path]::PathSeparator)$MyModulePath"`

- Чтобы добавить постоянное значение, доступное при каждом открытии сеанса, добавьте приведенную выше команду в файл профиля PowerShell ( `$PROFILE` ) >

  Дополнительные сведения о профилях см. в разделе [about_Profiles](/powershell/module/microsoft.powershell.core/about/about_profiles).

- Чтобы добавить постоянную переменную в реестр, создайте новую переменную среды пользователя `PSModulePath` с именем, используя редактор переменных среды в диалоговом окне **Свойства системы** .

- Чтобы добавить постоянную переменную с помощью скрипта, используйте метод .NET [SetEnvironmentVariable](/dotnet/api/system.environment.setenvironmentvariable) в классе [System. Environment](/dotnet/api/system.environment) . Например, следующий скрипт добавляет `C:\Program Files\Fabrikam\Module` путь к значению `PSModulePath` переменной среды для компьютера. Чтобы добавить путь к `PSModulePath` переменной среды пользователя, задайте для целевого объекта значение "User".

  ```powershell
  $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine")
  [Environment]::SetEnvironmentVariable("PSModulePath", $CurrentValue + [System.IO.Path]::PathSeparator + "C:\Program Files\Fabrikam\Modules", "Machine")

  ```

## <a name="to-remove-locations-from-the-psmodulepath"></a>Удаление расположений из PSModulePath

Вы можете удалить пути из переменной с помощью аналогичных методов: например, `$env:PSModulePath = $env:PSModulePath -replace "$([System.IO.Path]::PathSeparator)c:\\ModulePath"` удалит путь **к:\модулепас** из текущего сеанса.

## <a name="see-also"></a>См. также

[Написание модуля Windows PowerShell](./writing-a-windows-powershell-module.md)

[about_Modules](/powershell/module/microsoft.powershell.core/about/about_modules)
