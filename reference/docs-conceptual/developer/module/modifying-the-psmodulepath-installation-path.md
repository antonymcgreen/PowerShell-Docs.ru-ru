---
title: Изменение пути установки PSModulePath | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dc5ce5a2-50e9-4c88-abf1-ac148a8a6b7b
caps.latest.revision: 15
ms.openlocfilehash: b176d8439025ac132962859f79e72ae6f9703e82
ms.sourcegitcommit: 4a26c05f162c4fa347a9d67e339f8a33e230b9ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78405034"
---
# <a name="modifying-the-psmodulepath-installation-path"></a>Изменение пути установки PSModulePath

Переменная среды `PSModulePath` сохраняет пути к расположениям модулей, установленных на диске. PowerShell использует эту переменную для поиска модулей, когда пользователь не указал полный путь к модулю. Пути в этой переменной ищутся в том порядке, в котором они отображаются.

При запуске PowerShell `PSModulePath` создается как системная переменная среды со следующим значением по умолчанию: `$HOME\Documents\PowerShell\Modules; $PSHOME\Modules` в Windows и `$HOME/.local/share/powershell/Modules: usr/local/share/powershell/Modules` в Linux или Mac, а также `$HOME\Documents\WindowsPowerShell\Modules; $PSHOME\Modules` для Windows PowerShell.

> [!NOTE]
> Заданное пользователем расположение **CurrentUser** — это папка `WindowsPowerShell\Modules`, расположенная в папке **Documents** в профиле пользователя. Конкретный путь к этому расположению зависит от версии Windows, а также от того, используется ли перенаправление папок. По умолчанию в Windows 10 это расположение `$HOME\Documents\WindowsPowerShell\Modules`.

## <a name="to-view-the-psmodulepath-variable"></a>Просмотр переменной PSModulePath

Чтобы просмотреть пути, указанные в переменной `PSModulePath`, введите следующую команду:

`$env:PSModulePath`

## <a name="to-add-locations-to-the-psmodulepath-variable"></a>Добавление расположений в переменную PSModulePath

Чтобы добавить пути к этой переменной, используйте один из следующих методов.

- Чтобы добавить временное значение, доступное только для текущего сеанса, выполните в командной строке следующую команду:

  `$env:PSModulePath = $env:PSModulePath + "$([System.IO.Path]::PathSeparator)$MyModulePath"`

- Чтобы добавить постоянное значение, доступное при каждом открытии сеанса, добавьте приведенную выше команду в файл профиля PowerShell (`$PROFILE`) >

  Дополнительные сведения о профилях см. в разделе [about_Profiles](/powershell/module/microsoft.powershell.core/about/about_profiles).

- Чтобы добавить постоянную переменную в реестр, создайте новую переменную среды пользователя с именем `PSModulePath`, используя редактор переменных среды в диалоговом окне " **Свойства системы** ".

- Чтобы добавить постоянную переменную с помощью скрипта, используйте метод .NET [SetEnvironmentVariable](https://docs.microsoft.com/dotnet/api/system.environment.setenvironmentvariable) в классе [System. Environment](https://docs.microsoft.com/dotnet/api/system.environment) . Например, следующий скрипт добавляет путь `C:\Program Files\Fabrikam\Module` к значению переменной среды `PSModulePath` для компьютера. Чтобы добавить путь к пользовательской переменной среды `PSModulePath`, задайте для целевого объекта значение "User".

  ```powershell
  $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine")
  [Environment]::SetEnvironmentVariable("PSModulePath", $CurrentValue + [System.IO.Path]::PathSeparator + "C:\Program Files\Fabrikam\Modules", "Machine")

  ```

## <a name="to-remove-locations-from-the-psmodulepath"></a>Удаление расположений из PSModulePath

Вы можете удалить пути из переменной с помощью аналогичных методов: например, `$env:PSModulePath = $env:PSModulePath -replace "$([System.IO.Path]::PathSeparator)c:\\ModulePath"` удалит путь **к:\модулепас** из текущего сеанса.

## <a name="see-also"></a>См. также:

[Написание модуля Windows PowerShell](./writing-a-windows-powershell-module.md)

[about_Modules](/powershell/module/microsoft.powershell.core/about/about_modules)
