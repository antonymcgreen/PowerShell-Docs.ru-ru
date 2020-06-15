---
title: Модули скриптов
description: Модули скриптов — это простой способ упаковки скриптов и функций в многократно используемый инструмент.
ms.date: 06/02/2020
ms.topic: guide
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
ms.openlocfilehash: 661ba725764e1f31df628f6c5f2d58d760656e37
ms.sourcegitcommit: 0d958eac5bde5ccf5ee2c1bac4f009a63bf71368
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2020
ms.locfileid: "84438285"
---
# <a name="chapter-10---script-modules"></a>Глава 10. Модули скриптов

Преобразование ваших однострочных элементов кода и скриптов в PowerShell в многократно используемые средства станет еще более важным процессом, если вы будете регулярно его выполнять. После упаковки функций в модуль скрипта они выглядят более профессионально, что облегчает их совместное использование.

## <a name="dot-sourcing-functions"></a>Функции вызова с использованием точки

В предыдущей главе мы с вами не рассматривали функции вызова с использованием точки. Если функция в скрипте не является частью модуля, единственный способ загрузить его в память — вызвать файл `.PS1` с точкой, в котором он сохранен.

Следующая функция сохранена как `Get-MrPSVersion.ps1`.

```powershell
function Get-MrPSVersion {
    $PSVersionTable
}
```

При запуске скрипта ничего не происходит.

```powershell
.\Get-MrPSVersion.ps1
```

Если вы попытаетесь вызвать эту функцию, появится сообщение об ошибке.

```powershell
Get-MrPSVersion
```

```Output
Get-MrPSVersion : The term 'Get-MrPSVersion' is not recognized as the name of a cmdlet,
function, script file, or operable program. Check the spelling of the name, or if a path
was included, verify that the path is correct and try again.
At line:1 char:1
+ Get-MrPSVersion
    + CategoryInfo          : ObjectNotFound: (Get-MrPSVersion:String) [], CommandNotFou
   ndException
    + FullyQualifiedErrorId : CommandNotFoundException

```

Вы можете определить, загружаются ли функции в память, если проверите, есть ли они в PSDrive **Function**.

```powershell
Get-ChildItem -Path Function:\Get-MrPSVersion
```

```Output
Get-ChildItem : Cannot find path 'Get-MrPSVersion' because it does not exist.
At line:1 char:1
+ Get-ChildItem -Path Function:\Get-MrPSVersion
    + CategoryInfo          : ObjectNotFound: (Get-MrPSVersion:String) [Get-ChildItem],
   ItemNotFoundException
    + FullyQualifiedErrorId : PathNotFound,Microsoft.PowerShell.Commands.GetChildItemCommand
```

Проблема с вызовом скрипта, содержащего функцию, состоит в том, что функции загружаются в область _Script_. После выполнения скрипта область удаляется и вместе с ней удаляется функция.

Функция должна быть загружена в область _Global_. Это можно сделать вызовом скрипта с точкой, который содержит эту функцию. При этом можно использовать относительный путь.

```powershell
. .\Get-MrPSVersion.ps1
```

Кроме того, можно использовать полный путь.

```powershell
. C:\Demo\Get-MrPSVersion.ps1
```

Если часть пути хранится в переменной, ее можно объединить с оставшейся частью пути.
Для объединения переменной вместе с оставшейся частью пути не нужно использовать объединение строк.

```powershell
$Path = 'C:\'
. $Path\Get-MrPSVersion.ps1
```

Теперь, когда я проверяю PSDrive **Function**, функция `Get-MrPSVersion` существует.

```powershell
Get-ChildItem -Path Function:\Get-MrPSVersion
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Function        Get-MrPSVersion
```

## <a name="script-modules"></a>Модули скриптов

Модуль скрипта в PowerShell — это всего лишь файл, содержащий одну функцию или несколько, сохраненных в виде файла `.PSM1`, а не файла `.PS1`.

Как создать модуль скрипта? Вероятно, вы думаете, что это можно сделать с помощью команды с именем вроде `New-Module`. Ваше предположение будет неверным. Хотя в PowerShell есть команда с именем `New-Module`, она создает динамический модуль, а не модуль скрипта. Обязательно ознакомьтесь со справкой для команды, даже если считаете, что нашли нужную команду.

```powershell
help New-Module
```

```Output
NAME
    New-Module

SYNOPSIS
    Creates a new dynamic module that exists only in memory.

SYNTAX
    New-Module [-Name] <String> [-ScriptBlock] <ScriptBlock> [-ArgumentList <Object[]>]
    [-AsCustomObject] [-Cmdlet <String[]>] [-Function <String[]>] [-ReturnResult]
    [<CommonParameters>]

DESCRIPTION
    The New-Module cmdlet creates a dynamic module from a script block. The members of
    the dynamic module, such as functions and variables, are immediately available in
    the session and remain available until you close the session.

    Like static modules, by default, the cmdlets and functions in a dynamic module are
    exported and the variables and aliases are not. However, you can use the
    Export-ModuleMember cmdlet and the parameters of New-Module to override the defaults.

    You can also use the AsCustomObject parameter of New-Module to return the dynamic
    module as a custom object. The members of the modules, such as functions, are
    implemented as script methods of the custom object instead of being imported into
    the session.

    Dynamic modules exist only in memory, not on disk. Like all modules, the members of
    dynamic modules run in a private module scope that is a child of the global scope.
    Get-Module cannot get a dynamic module, but Get-Command can get the exported members.

    To make a dynamic module available to Get-Module , pipe a New-Module command to
    Import-Module, or pipe the module object that New-Module returns to Import-Module .
    This action adds the dynamic module to the Get-Module list, but it does not save the
    module to disk or make it persistent.

RELATED LINKS
    Online Version: http://go.microsoft.com/fwlink/?LinkId=821495
    Export-ModuleMember
    Get-Module
    Import-Module
    Remove-Module

REMARKS
    To see the examples, type: "get-help New-Module -examples".
    For more information, type: "get-help New-Module -detailed".
    For technical information, type: "get-help New-Module -full".
    For online help, type: "get-help New-Module -online"
```

В предыдущей главе я говорил, что функции должны использовать утвержденные команды, иначе при импорте модуля будет появляться предупреждающее сообщение. В следующем коде командлет `New-Module` используется для создания динамического модуля в памяти. Этот модуль демонстрирует предупреждение о неутвержденной команде.

```powershell
New-Module -Name MyModule -ScriptBlock {

    function Return-MrOsVersion {
        Get-CimInstance -ClassName Win32_OperatingSystem |
        Select-Object -Property @{label='OperatingSystem';expression={$_.Caption}}
    }

    Export-ModuleMember -Function Return-MrOsVersion

} | Import-Module
```

```Output
WARNING: The names of some imported commands from the module 'MyModule' include
unapproved verbs that might make them less discoverable. To find the commands with
unapproved verbs, run the Import-Module command again with the Verbose parameter. For a
list of approved verbs, type Get-Verb.
```

Хотя в предыдущем примере использовался командлет `New-Module`, эта команда используется только для повторной итерации, а не для создания модулей скрипта в PowerShell.

Сохраните следующие две функции в файле с именем `MyScriptModule.psm1`.

```powershell
function Get-MrPSVersion {
    $PSVersionTable
}

function Get-MrComputerName {
    $env:COMPUTERNAME
}
```

Попробуйте вызвать одну из функций.

```powershell
Get-MrComputerName
```

```Output
Get-MrComputerName : The term 'Get-MrComputerName' is not recognized as the name of a
cmdlet, function, script file, or operable program. Check the spelling of the name, or
if a path was included, verify that the path is correct and try again.
At line:1 char:1
+ Get-MrComputerName
    + CategoryInfo          : ObjectNotFound: (Get-MrComputerName:String) [], CommandNot
   FoundException
    + FullyQualifiedErrorId : CommandNotFoundException
```

Появится сообщение об ошибке, в котором говорится, что функция не найдена. Кроме того, вы можете проверить PSDrive **Function** так, как делали это раньше, и увидите, что ее там тоже нет.

Вы можете импортировать файл вручную с помощью командлета `Import-Module`.

```powershell
Import-Module C:\MyScriptModule.psm1
```

Функция автозагрузки модулей появилась в PowerShell версии 3. Чтобы воспользоваться преимуществами автозагрузки модулей, необходимо сохранить модуль скрипта в папке с тем же базовым именем, что и файл `.PSM1`, и в расположении, указанном в `$env:PSModulePath`.

```powershell
$env:PSModulePath
```

```Output
C:\Users\mike-ladm\Documents\WindowsPowerShell\Modules;C:\Program Files\WindowsPowerShell\
Modules;C:\Windows\system32\WindowsPowerShell\v1.0\Modules;C:\Program Files (x86)\Microsof
t SQL Server\130\Tools\PowerShell\Modules\
```

Полученные результаты будет нелегко прочитать. Так как пути разделяются точкой с запятой, можно разбить результаты, чтобы вернуть каждый путь на отдельной строке. Так их легче будет прочитать.

```powershell
$env:PSModulePath -split ';'
```

```Output
C:\Users\mike-ladm\Documents\WindowsPowerShell\Modules
C:\Program Files\WindowsPowerShell\Modules
C:\Windows\system32\WindowsPowerShell\v1.0\Modules
C:\Program Files (x86)\Microsoft SQL Server\130\Tools\PowerShell\Modules\
```

Первые три пути в списке стандартные. При установке SQL Server Management Studio был добавлен последний путь. Для работы автозагрузки модулей файл `MyScriptModule.psm1` должен находиться в папке с именем `MyScriptModule` непосредственно в одном из этих путей.

Не так быстро. У меня текущий путь пользователя не находится первым в списке. Я почти никогда не использую этот путь, так как вхожу в систему Windows под учетной записью пользователя, отличной от той, которую я использую для запуска PowerShell. Это означает, что этот путь находится не в моей обычной папке "Документы".

**AllUsers** — это второй путь. В этом месте я храню все свои модули.

Третий путь находится под `C:\Windows\System32`. Хранить модули в этом расположении должна только корпорация Майкрософт, так как оно находится в папке операционных систем.

После того как файл `.PSM1` будет размещен в правильном пути, модуль будет автоматически загружаться при вызове одной из команд.

## <a name="module-manifests"></a>Манифесты модулей

Каждый модуль имеет манифест модуля. Манифест модуля содержит метаданные о вашем модуле.
Расширение файла для файла манифеста модуля — `.PSD1`. Не все файлы с расширением `.PSD1` являются манифестами модулей. Кроме того, их можно использовать для хранения части среды конфигурации DSC. `New-ModuleManifest` используется для создания манифеста модуля. **Path** — единственное значение, которое необходимо указать. При этом модуль не будет работать, если не указан параметр **RootModule**. Лучше указать параметры **Author** и **Description** на тот случай, если вы решите передать модуль в репозиторий NuGet с помощью PowerShellGet, так как эти значения необходимо указать в приведенном сценарии.

Версия модуля без манифеста — 0.0. Это явное доказательство того, что модуль не имеет манифеста.

```powershell
Get-Module -Name MyScriptModule
```

```Output
ModuleType Version    Name                                ExportedCommands
---------- -------    ----                                ----------------
Script     0.0        myscriptmodule                      {Get-MrComputerName, Get-MrP...
```

Манифест модуля можно создать с помощью всех рекомендуемых данных.

```powershell
New-ModuleManifest -Path $env:ProgramFiles\WindowsPowerShell\Modules\MyScriptModule\MyScriptModule.psd1 -RootModule MyScriptModule -Author 'Mike F Robbins' -Description 'MyScriptModule' -CompanyName 'mikefrobbins.com'
```

Если во время первоначального создания манифеста модуля какие-либо данные отсутствуют, их можно добавить или обновить позже с помощью `Update-ModuleManifest`. Не создавайте манифест повторно с помощью `New-ModuleManifest` после того, как он уже создан, так как в этом случае изменится идентификатор GUID.

## <a name="defining-public-and-private-functions"></a>Определение общих и частных функций

Возможно, у вас есть вспомогательные функции, которые вы хотите сделать частными и доступными только для других функций в модуле. Вспомогательные функции не предназначены для доступа пользователям вашего модуля. Это можно сделать двумя способами.

Если вы не следуете рекомендациям и у вас есть только файл `.PSM1`, единственный вариант для вас — использовать командлет `Export-ModuleMember`.

```powershell
function Get-MrPSVersion {
    $PSVersionTable
}

function Get-MrComputerName {
    $env:COMPUTERNAME
}

Export-ModuleMember -Function Get-MrPSVersion
```

В предыдущем примере для пользователей модуля доступна только функция `Get-MrPSVersion`, при этом функция `Get-MrComputerName` доступна для других функций в самом модуле.

```powershell
Get-Command -Module MyScriptModule

CommandType     Name                        Version    Source
-----------     ----                        -------    ------
Function        Get-MrPSVersion             1.0        MyScript...
```

Если вы добавили в модуль манифест модуля (а это необходимо), советую указать отдельные функции, которые вам нужно экспортировать, в раздел **FunctionsToExport** манифеста модуля.

```powershell
FunctionsToExport = 'Get-MrPSVersion'
```

Нет необходимости использовать оба `Export-ModuleMember` в файле `.PSM1` и в разделе **FunctionsToExport** манифеста модуля. Достаточно использовать один из них.

## <a name="summary"></a>Сводка

В этой главе вы узнали, как преобразовать функции в модуль скрипта в PowerShell. Кроме того, вы рассмотрели некоторые рекомендации по созданию модулей скриптов, например создание манифеста модуля для модуля скрипта.

## <a name="review"></a>Просмотр

1. Как создать модуль скрипта в PowerShell?
1. Почему для ваших функций важно использовать утвержденную команду?
1. Как создать манифест модуля в PowerShell?
1. С помощью каких двух способов экспортируются только определенные функции из модуля?
1. Что требуется для автоматической загрузки модулей при вызове команды?

## <a name="recommended-reading"></a>Рекомендуем прочесть

- [Как создать модули скриптов PowerShell и манифесты модулей][]
- [about_Modules][]
- [New-ModuleManifest][]
- [Export-ModuleMember][]

<!-- link references -->
[Как создать модули скриптов PowerShell и манифесты модулей]: https://mikefrobbins.com/2013/07/04/how-to-create-powershell-script-modules-and-module-manifests/
[about_Modules]: /powershell/module/microsoft.powershell.core/about/about_modules
[New-ModuleManifest]: /powershell/module/microsoft.powershell.core/new-modulemanifest
[Export-ModuleMember]: /powershell/module/microsoft.powershell.core/export-modulemember
