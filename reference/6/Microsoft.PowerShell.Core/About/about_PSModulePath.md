---
description: Переменная среды PSModulePath содержит список расположений папок, в которых выполняется поиск модулей и ресурсов.
keywords: powershell,командлет
Locale: en-US
ms.date: 04/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_PSModulePath?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PSModulePath
ms.openlocfilehash: 80f64af01a76c00e61beeb7a113c51244b9e5750
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231390"
---
# <a name="about-psmodulepath"></a>О PSModulePath

`$env:PSModulePath`Переменная среды содержит список расположений папок, в которых выполняется поиск модулей и ресурсов.

По умолчанию действующие расположения, назначенные, `$env:PSModulePath` являются:

- Расположения на уровне системы. Эти папки содержат модули, поставляемые с PowerShell. Эти модули хранятся в `$PSHOME\Modules` папке. Это также расположение, в котором установлены модули управления Windows.

- Модули, установленные пользователем: это модули, установленные пользователем.
  `Install-Module` имеет параметр **области** , который позволяет указать, установлен ли модуль для текущего пользователя или для всех пользователей. Дополнительные сведения см. в разделе [Install-Module](xref:PowerShellGet.Install-Module).

  - В Windows расположением определяемой пользователем области **CurrentUser** является `$HOME\Documents\PowerShell\Modules` Папка. Областью **ALLUSERS** является расположение `$env:ProgramFiles\PowerShell\Modules` .
  - В системах, отличных от Windows, расположением определяемой пользователем области **CurrentUser** является `$HOME/.local/share/powershell/Modules` Папка. Областью **ALLUSERS** является расположение `/usr/local/share/powershell/Modules` .

Кроме того, программы установки, устанавливающие модули в других каталогах, например каталог Program Files, могут добавлять свои расположения к значению `$env:PSModulePath` .

> [!NOTE]
> В Windows пользовательское расположение — это `PowerShell\Modules` Папка, расположенная в папке **документы** в профиле пользователя. Конкретный путь к этому расположению зависит от версии Windows, а также от того, используется ли перенаправление папок. Microsoft OneDrive также может изменить расположение папки **документов** . Расположение папки **документов** можно проверить с помощью следующей команды: `[Environment]::GetFolderPath('MyDocuments')` .

## <a name="modifying-psmodulepath"></a>Изменение PSModulePath

Чтобы изменить каталоги модулей по умолчанию для текущего сеанса, используйте следующий формат команды, чтобы изменить значение `PSModulePath` переменной среды.

Например, чтобы добавить `C:\Program Files\Fabrikam\Modules` Каталог к значению переменной среды PSModulePath, введите:

```powershell
$Env:PSModulePath = $Env:PSModulePath+";C:\Program Files\Fabrikam\Modules"
```

Точка с запятой ( `;` ) в команде отделяет новый путь от пути, расположенного перед ним в списке. На платформах, отличных от Windows, двоеточие ( `:` ) разделяет расположения путей в переменной среды.

Чтобы изменить значение `PSModulePath` в каждом сеансе, добавьте предыдущую команду в профиль PowerShell или используйте метод **SetEnvironmentVariable** класса **Environment** .

Следующая команда использует метод **GetEnvironmentVariable** для получения параметра компьютера, `PSModulePath` а метод **SetEnvironmentVariable** — для добавления `C:\Program Files\Fabrikam\Modules` пути к значению.

```powershell
$path = [Environment]::GetEnvironmentVariable('PSModulePath', 'Machine')
$newpath = $path + ';C:\Program Files\Fabrikam\Modules'
[Environment]::SetEnvironmentVariable('PSModulePath', $newpath, 'Machine')
```

Чтобы добавить путь к пользовательскому параметру, измените целевое значение на " **пользователь** ".

```powershell
$path = [Environment]::GetEnvironmentVariable('PSModulePath', 'User')
$newpath = $path + ';C:\Program Files\Fabrikam\Modules'
[Environment]::SetEnvironmentVariable('PSModulePath', $newpath, 'User')
```

Дополнительные сведения о методах класса **System. Environment** см. в разделе [методы среды](/dotnet/api/system.environment).

## <a name="powershell-psmodulepath-construction"></a>Создание PSModulePath PowerShell

Значение формируется `$env:PSModulePath` каждый раз при запуске PowerShell.
Значение зависит от версии PowerShell и способа ее запуска.

### <a name="windows-powershell-startup"></a>Запуск Windows PowerShell

Windows PowerShell использует следующую логику для создания `PSModulePath` при запуске.

- Если `PSModulePath` не существует, объедините пути **CurrentUser** , **ALLUSERS** и `$PSHOME` modules.
- Если `PSModulePath` существует:
  - Если `PSModulePath` содержит `$PSHOME` путь к модулям:
    - Путь к модулям **ALLUSERS** вставляется перед `$PSHOME` путем к модулям
  - Кроме
    - Просто используйте `PSModulePath` , как определено, так как пользователь намеренно удалил `$PSHOME` расположение.

Путь к модулю **CurrentUser** имеет префикс, только если область пользователя `$env:PSModulePath` не существует. В противном случае область пользователя `$env:PSModulePath` будет использоваться как определенная.

### <a name="powershell-core-6-startup"></a>Запуск PowerShell Core 6

PowerShell Core 6 не использует содержимое, `$env:PSModulePath` если обнаруживает, что оно было запущено из PowerShell. Он перезаписывает его следующим образом:

- Модули **CurrentUser** путь + **ALLUSERS** модули путь + `$PSHOME` модули путь + `$PSHOME` путь к модулям Windows PowerShell.

### <a name="powershell-7-startup"></a>Запуск PowerShell 7

В Windows для большинства переменных среды, если переменная уровня пользователя существует, новый процесс использует это значение только в том случае, если переменная уровня компьютера с таким же именем существует.

В PowerShell 7 `PSModulePath` обрабатывается аналогично тому, как `Path` переменная среды обрабатывается в Windows. В Windows обрабатывается иначе, чем `Path` в других переменных среды. При запуске процесса Windows объединяет область пользователя `Path` с областью действия компьютера `Path` .

- Получение области пользователя `PSModulePath`
- Сравнить с наследуемой `PSModulePath` переменной среды
  - Если это так:
    - Добавьте **ALLUSERS** `PSModulePath` в конец, следующий за семантикой `Path` переменной среды
    - Путь Windows `System32` берется из определенного компьютера, `PSModulePath` поэтому его не нужно добавлять явно.
  - Если они отличаются, то следует рассматривать, как будто пользователь явно изменил его и не добавил **ALLUSERS**`PSModulePath`
- Префикс с PS7 пользователя, системой и `$PSHOME` путями в этом порядке
  - Если параметр `powershell.config.json` содержит пользовательскую область `PSModulePath` , используйте его вместо значения по умолчанию для пользователя.
  - Если `powershell.config.json` содержит область системы `PSModulePath` , используйте ее вместо значения по умолчанию для системы

В системах UNIX не существует разделения переменных среды пользователя и системы.
`PSModulePath` является унаследованным, а пути, зависящие от PS7, являются префиксами, если они еще не определены.

### <a name="starting-windows-powershell-from-powershell-7"></a>Запуск Windows PowerShell из PowerShell 7

В этом обсуждении _Windows PowerShell_ означает `powershell.exe` и, и `powershell_ise.exe` .

Значение `$env:PSModulePath` копируется в `WinPSModulePath` со следующими изменениями:

- Удалить PS7 путь к пользовательскому модулю
- Удалить PS7 путь к системному модулю
- Удалить PS7 в `$PSHOME` пути к модулю

Пути PS7 удаляются, чтобы модули PS7 не загружались в Windows PowerShell. `WinPSModulePath`Значение используется при запуске Windows PowerShell.

### <a name="starting-powershell-7-from-windows-powershell"></a>Запуск PowerShell 7 из Windows PowerShell

Запуск PowerShell 7 продолжится "как есть" с добавлением путей наследования, добавленных Windows PowerShell. Так как пути, относящиеся к PS7, являются префиксами, функциональные проблемы отсутствуют.

### <a name="starting-powershell-6-from-powershell-7"></a>Запуск PowerShell 6 из PowerShell 7

PowerShell Core 6 перезаписывает `$env:PSModulePath` . Изменения не вносятся.

### <a name="starting-powershell-7-from-powershell-6"></a>Запуск PowerShell 7 из PowerShell 6

Запуск PowerShell 7 продолжится как есть с добавлением путей, добавленных PowerShell Core 6. Так как пути, относящиеся к PS7, являются префиксами, функциональные проблемы отсутствуют.

## <a name="see-also"></a>См. также статью

- [about_Modules](about_Modules.md)
- [Методы среды](/dotnet/api/system.environment)
