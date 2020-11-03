---
description: Описание функций совместимости Windows PowerShell для PowerShell 7.
keywords: powershell,командлет
Locale: en-US
ms.date: 04/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_windows_powershell_compatibility?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Windows_PowerShell_Compatibility
ms.openlocfilehash: 522c9d2169e49584915450813ad28dfc5e0d5ca2
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231073"
---
# <a name="about-windows-powershell-compatibility"></a>О совместимости с Windows PowerShell

## <a name="short-description"></a>КРАТКОЕ ОПИСАНИЕ

Описание функций совместимости Windows PowerShell для PowerShell 7.

## <a name="long-description"></a>ПОДРОБНОЕ ОПИСАНИЕ

Если манифест модуля не указывает на то, что модуль совместим с PowerShell Core, модули в `%windir%\system32\WindowsPowerShell\v1.0\Modules` папке загружаются в фоновом режиме Windows powershell 5,1 с помощью функции совместимости Windows PowerShell.

### <a name="using-the-compatibility-feature"></a>Использование функции совместимости

Когда первый модуль импортируется с помощью функции совместимости Windows PowerShell, PowerShell создает удаленный сеанс с именем `WinPSCompatSession` , который выполняется в фоновом процессе Windows powershell 5,1. Этот процесс создается, когда функция совместимости импортирует первый модуль. Процесс закрывается при удалении последнего такого модуля (с помощью `Remove-Module` ) или при завершении работы процесса PowerShell.

Модули, загруженные в `WinPSCompatSession` сеансе, используются через неявное удаленное взаимодействие и отражаются в текущем сеансе PowerShell. Это тот же метод транспорта, который используется для заданий PowerShell.

При импорте модуля в `WinPSCompatSession` сеанс Неявное удаленное взаимодействие создает модуль прокси в `$env:Temp` каталоге пользователя и импортирует этот модуль прокси в текущий сеанс PowerShell. Это позволяет PowerShell обнаружить, что модуль был загружен с помощью функции совместимости Windows PowerShell.

После создания сеанса его можно использовать для операций, которые неправильно работают в десериализованных объектах. Весь конвейер выполняется в Windows PowerShell, и возвращается только окончательный результат. Пример:

```powershell
$s = Get-PSSession -Name WinPSCompatSession
Invoke-Command -Session $s -ScriptBlock {
  "Running in Windows PowerShell version $($PSVersionTable.PSVersion)"
}
```

Функцию совместимости можно вызвать двумя способами:

- Явным образом путем импорта модуля с помощью параметра **усевиндовсповершелл**

   ```powershell
   Import-Module -Name ScheduledTasks -UseWindowsPowerShell
   ```

- Неявным образом Импортируйте модуль Windows PowerShell по имени модуля, пути или автозагрузке с помощью обнаружения команд.

   ```powershell
   Import-Module -Name ServerManager
   Get-AppLockerPolicy -Local
   ```

   Если он еще не загружен, модуль AppLocker будет выгружен при запуске  `Get-AppLockerPolicy` .

Совместимость Windows PowerShell блокирует загрузку модулей, перечисленных в `WindowsPowerShellCompatibilityModuleDenyList` параметре в файле конфигурации PowerShell.

Значение этого параметра по умолчанию:

```json
"WindowsPowerShellCompatibilityModuleDenyList":  [
   "PSScheduledJob","BestPractices","UpdateServices"
]
```

### <a name="managing-implicit-module-loading"></a>Управление неявной загрузкой модуля

Чтобы отключить неявное поведение импорта функции совместимости Windows PowerShell, используйте `DisableImplicitWinCompat` параметр в файле конфигурации PowerShell. Этот параметр можно добавить в `powershell.config.json` файл. Дополнительные сведения см. в разделе [about_powershell_config](about_powershell_config.md).

В этом примере показано, как создать файл конфигурации, который отключает функцию неявной загрузки модуля для совместимости с Windows PowerShell.

```powershell
$ConfigPath = "$PSHOME\DisableWinCompat.powershell.config.json"
$ConfigJSON = ConvertTo-Json -InputObject @{
  "DisableImplicitWinCompat" = $true
  "Microsoft.PowerShell:ExecutionPolicy" = "RemoteSigned"
}
$ConfigJSON | Out-File -Force $ConfigPath
pwsh -settingsFile $ConfigPath
```

Последние сведения о совместимости модулей см. в списке [совместимости модулей PowerShell 7](https://aka.ms/PSModuleCompat) .

### <a name="managing-cmdlet-clobbering"></a>Управление командлетами клобберинг

Функция совместимости Windows PowerShell использует неявное удаленное взаимодействие для загрузки модулей в режиме совместимости. В результате команды, экспортированные модулем, имеют приоритет над командами с тем же именем в текущем сеансе PowerShell 7. В 7.0.0 выпуске PowerShell включены основные модули, поставляемые с PowerShell.

В PowerShell 7,1 поведение было изменено таким образом, чтобы следующие базовые модули PowerShell не затерт:

- Microsoft. PowerShell. ConsoleHost
- Microsoft.PowerShell.Diagnostics
- Microsoft.PowerShell.Host
- Microsoft.PowerShell.Management
- Microsoft.PowerShell.Security
- Microsoft.PowerShell.Utility
- Microsoft.WSMan.Management

В PowerShell 7,1 также добавлена возможность перечисления дополнительных модулей, которые не должны быть затерт в режиме совместимости.

Вы можете добавить `WindowsPowerShellCompatibilityNoClobberModuleList` параметр в файл конфигурации PowerShell. Значение этого параметра представляет собой разделенный запятыми список имен модулей. Значение этого параметра по умолчанию:

```json
"WindowsPowerShellCompatibilityNoClobberModuleList": [ ]
```

## <a name="limitations"></a>Ограничения

Функции совместимости Windows PowerShell:

1. Работает только локально на компьютерах Windows
1. Требует, чтобы Windows PowerShell 5,1
1. Работает с сериализованными параметрами командлета и возвращаемыми значениями, а не с активными объектами.
1. Все модули, импортированные в сеанс удаленного взаимодействия Windows PowerShell, совместно используют одно и то же пространство выполнения.

## <a name="keywords"></a>Keywords

about_Windows_PowerShell_Compatibility

## <a name="see-also"></a>См. также статью

[about_Modules](about_Modules.md)

[Import-Module](xref:Microsoft.PowerShell.Core.Import-Module)

