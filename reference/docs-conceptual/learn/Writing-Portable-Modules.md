---
ms.date: 01/10/2020
keywords: powershell,командлет
title: Создание переносимых модулей
ms.openlocfilehash: 124e6efadfd07b8c5214a5c0446b1589f7142388
ms.sourcegitcommit: cab4e4e67dbed024864887c7f8984abb4db3a78b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2020
ms.locfileid: "76022242"
---
# <a name="portable-modules"></a>Переносимые модули

Средство Windows PowerShell написано для [.NET Framework][], в то время как PowerShell Core написано для [.NET Core][]. Переносимые модули — это модули, которые работают как в Windows PowerShell, так и в PowerShell Core. Хотя .NET Framework и .NET Core обладают высокой совместимостью, между ними есть различия касательно доступных API-интерфейсов. Существуют также различия в API-интерфейсах, доступных в Windows PowerShell и PowerShell Core. В модулях, которые предназначены для использования в обеих средах, должны учитываться эти различия.

## <a name="porting-an-existing-module"></a>Перенос существующего модуля

### <a name="porting-a-pssnapin"></a>Перенос оснастки PSSnapIn

Оснастки PowerShell ([SnapIns](/powershell/scripting/developer/cmdlet/modules-and-snap-ins)) не поддерживаются в PowerShell Core. Тем не менее PSSnapIn можно легко преобразовать в модуль PowerShell. Как правило, регистрационный код PSSnapIn находится в одном исходном файле класса, который наследуется от [PSSnapIn][].
Удалите этот исходный файл из сборки, так как он больше не нужен.

Чтобы создать манифест модуля, который заменяет необходимость в регистрационном коде PSSnapIn, используйте командлет [New-ModuleManifest][]. Некоторые значения из **PSSnapIn** (например, **Description**) можно повторно использовать в манифесте модуля.

Для свойства **RootModule** в манифесте модуля должно быть указано имя сборки (DLL), реализующей командлеты.

### <a name="the-net-portability-analyzer-aka-apiport"></a>Средство .NET Portability Analyzer (оно же APIPort)

Чтобы перенести модули, написанные для Windows PowerShell, для работы с PowerShell Core, используйте [.NET Portability Analyzer][]. Запустите это средство для вашей скомпилированной сборки, чтобы определить совместимость используемых в модуле интерфейсов API .NET с .NET Framework, .NET Core и другими средами выполнения .NET. Средство предлагает альтернативные API-интерфейсы, если они существуют. В противном случае вам может потребоваться добавить [Проверки среды выполнения][] и ограничить возможности, недоступные в определенных средах выполнения.

## <a name="creating-a-new-module"></a>Создание модуля

При создании модуля рекомендуется использовать [Интерфейс командной строки.NET][].

### <a name="installing-the-powershell-standard-module-template"></a>Установка шаблона стандартного модуля PowerShell

После установки интерфейса командной строки .NET установите библиотеку шаблонов, чтобы создать простой модуль PowerShell.
Модуль будет совместим с Windows PowerShell, PowerShell Core, Windows, Linux и macOS.

В следующем примере показана установка шаблона:

```powershell
dotnet new -i Microsoft.PowerShell.Standard.Module.Template
```

```output
  Restoring packages for C:\Users\Steve\.templateengine\dotnetcli\v2.1.302\scratch\restore.csproj...
  Installing Microsoft.PowerShell.Standard.Module.Template 0.1.3.
  Generating MSBuild file C:\Users\Steve\.templateengine\dotnetcli\v2.1.302\scratch\obj\restore.csproj.nuget.g.props.
  Generating MSBuild file C:\Users\Steve\.templateengine\dotnetcli\v2.1.302\scratch\obj\restore.csproj.nuget.g.targets.
  Restore completed in 1.66 sec for C:\Users\Steve\.templateengine\dotnetcli\v2.1.302\scratch\restore.csproj.

Usage: new [options]

Options:
  -h, --help          Displays help for this command.
  -l, --list          Lists templates containing the specified name. If no name is specified, lists all templates.
  -n, --name          The name for the output being created. If no name is specified, the name of the current directory is used.
  -o, --output        Location to place the generated output.
  -i, --install       Installs a source or a template pack.
  -u, --uninstall     Uninstalls a source or a template pack.
  --nuget-source      Specifies a NuGet source to use during install.
  --type              Filters templates based on available types. Predefined values are "project", "item" or "other".
  --force             Forces content to be generated even if it would change existing files.
  -lang, --language   Filters templates based on language and specifies the language of the template to create.


Templates                                         Short Name         Language          Tags
----------------------------------------------------------------------------------------------------------------------------
Console Application                               console            [C#], F#, VB      Common/Console
Class library                                     classlib           [C#], F#, VB      Common/Library
PowerShell Standard Module                        psmodule           [C#]              Library/PowerShell/Module
...
```

### <a name="creating-a-new-module-project"></a>Создание проекта модуля

После установки шаблона можно создать проект модуля PowerShell с использованием этого шаблона. У нас пример модуля называется myModule.

```
PS> mkdir myModule

    Directory: C:\Users\Steve

Mode LastWriteTime Length Name
---- ------------- ------ ----
d----- 8/3/2018 2:41 PM myModule

PS> cd myModule
PS C:\Users\Steve\myModule> dotnet new psmodule

The template "PowerShell Standard Module" was created successfully.

Processing post-creation actions...
Running 'dotnet restore' on C:\Users\Steve\myModule\myModule.csproj...
  Restoring packages for C:\Users\Steve\myModule\myModule.csproj...
  Installing PowerShellStandard.Library 5.1.0.
  Generating MSBuild file C:\Users\Steve\myModule\obj\myModule.csproj.nuget.g.props.
  Generating MSBuild file C:\Users\Steve\myModule\obj\myModule.csproj.nuget.g.targets.
  Restore completed in 1.76 sec for C:\Users\Steve\myModule\myModule.csproj.

Restore succeeded.
```

### <a name="building-the-module"></a>Создание модуля

Используйте стандартные команды интерфейса командной строки .NET для создания проекта.

```powershell
dotnet build
```

```output
PS C:\Users\Steve\myModule> dotnet build
Microsoft (R) Build Engine version 15.7.179.6572 for .NET Core
Copyright (C) Microsoft Corporation. All rights reserved.

  Restore completed in 76.85 ms for C:\Users\Steve\myModule\myModule.csproj.
  myModule -> C:\Users\Steve\myModule\bin\Debug\netstandard2.0\myModule.dll

Build succeeded.
    0 Warning(s)
    0 Error(s)

Time Elapsed 00:00:05.40
```

### <a name="testing-the-module"></a>Тестирование модуля

После создания модуля вы можете импортировать его и выполнить пример командлета.

```powershell
ipmo .\bin\Debug\netstandard2.0\myModule.dll
Test-SampleCmdlet -?
Test-SampleCmdlet -FavoriteNumber 7 -FavoritePet Cat
```

```output
PS C:\Users\Steve\myModule> ipmo .\bin\Debug\netstandard2.0\myModule.dll
PS C:\Users\Steve\myModule> Test-SampleCmdlet -?

NAME
    Test-SampleCmdlet

SYNTAX
    Test-SampleCmdlet [-FavoriteNumber] <int> [[-FavoritePet] {Cat | Dog | Horse}] [<CommonParameters>]


ALIASES
    None


REMARKS
    None


PS C:\Users\Steve\myModule> Test-SampleCmdlet -FavoriteNumber 7 -FavoritePet Cat

FavoriteNumber FavoritePet
-------------- -----------
             7 Cat
```

В следующих разделах подробно описаны некоторые технологии, используемые этим шаблоном.

## <a name="net-standard-library"></a>Библиотека .NET Standard

[.NET Standard][] — это формальная спецификация API-интерфейсов .NET, доступных во всех реализациях .NET. Управляемый код, предназначенный для .NET Standard, работает с версиями .NET Framework и .NET Core, совместимыми с этой версией .NET Standard.

> [!NOTE]
> Хотя API-интерфейс может существовать в .NET Standard, реализация API в .NET Core во время выполнения может вызывать исключение `PlatformNotSupportedException`, поэтому для проверки совместимости с Windows PowerShell и PowerShell Core рекомендуется выполнить тестирование вашего модуля в обеих средах.
> Если ваш модуль должен быть кроссплатформенным, запустите также тестирование в Linux и macOS.

Нацеленность на .NET Standard гарантирует, что по мере развития модуля несовместимые API-интерфейсы не будут случайно введены в модуль. Несовместимости обнаруживаются во время компиляции, а не во время выполнения.

Однако для работы модуля как с Windows PowerShell, так и с PowerShell Core не требуется указывать платформу .NET Standard как целевую, если используются совместимые API-интерфейсы. Промежуточный язык (IL) совместим с двумя средами выполнения. Вы можете указать как целевую версию .NET Framework 4.6.1, которая совместима с .NET Standard 2.0. Если вы не используете API-интерфейсы за пределами. NET Standard 2.0, тогда ваш модуль будет работать с PowerShell Core 6 без повторной компиляции.

## <a name="powershell-standard-library"></a>Библиотека PowerShell Standard

[PowerShell Standard][] — это формальная спецификация API-интерфейсов PowerShell, доступная во всех версиях PowerShell, которые больше версии этого стандарта или соответствуют ей.

Например, [PowerShell Standard 5.1][] совместима как с Windows PowerShell 5.1, так и с PowerShell Core 6.0 или более поздней версией.

Мы советуем вам скомпилировать свой модуль с помощью библиотеки PowerShell Standard. Библиотека гарантирует, что API-интерфейсы будут доступны и реализованы как в Windows PowerShell, так и в PowerShell Core 6.
PowerShell Standard предназначена для постоянной совместимости с новыми версиями. Модуль, созданный с использованием библиотеки PowerShell Standard 5.1, всегда будет совместим с будущими версиями PowerShell.

## <a name="module-manifest"></a>Манифест модуля

### <a name="indicating-compatibility-with-windows-powershell-and-powershell-core"></a>Указание на совместимость с Windows PowerShell и PowerShell Core

После проверки работы модуля с Windows PowerShell и с PowerShell Core манифест модуля должен явно указывать совместимость с помощью свойства [CompatiblePSEditions][]. Значение `Desktop` означает, что модуль совместим с Windows PowerShell, а значение `Core` указывает на совместимость с PowerShell Core. Наличие обоих значений (`Desktop` и `Core`) означает, что модуль совместим как с Windows PowerShell, так и с PowerShell Core.

> [!NOTE]
> `Core` необязательно означает, что модуль совместим с Windows, Linux и macOS.
> Свойство **CompatiblePSEditions** впервые появилось в PowerShell версии 5. Манифесты модуля, которые используют свойство **CompatiblePSEditions**, не будут загружаться в версиях, предшествующих PowerShell версии 5.

### <a name="indicating-os-compatibility"></a>Указание на совместимость с ОС

Сначала убедитесь, что ваш модуль работает в Linux и macOS. Далее укажите совместимость с этими операционными системами в манифесте модуля. В результате пользователям будет проще искать ваш модуль для требуемых операционных систем, когда он будет опубликован в [Коллекция PowerShell][].

В манифесте модуля у свойства `PrivateData` есть вложенное свойство `PSData`. Необязательное свойство `Tags` раздела `PSData` принимает массив значений, которые отображаются в коллекции PowerShell. Коллекция PowerShell поддерживает следующие значения совместимости:

| Тег               | Описание                                |
|-------------------|--------------------------------------------|
| PSEdition_Core    | Совместимость с PowerShell Core 6          |
| PSEdition_Desktop | Совместимость с Windows PowerShell         |
| Windows           | Совместимость с Windows                    |
| Linux             | Совместимость с Linux (любой дистрибутив) |
| macOS             | Совместимость с macOS                      |

Пример

```powershell
@{
    GUID = "4ae9fd46-338a-459c-8186-07f910774cb8"
    Author = "Microsoft Corporation"
    CompanyName = "Microsoft Corporation"
    Copyright = "(C) Microsoft Corporation. All rights reserved."
    HelpInfoUri = "https://go.microsoft.com/fwlink/?linkid=855962"
    ModuleVersion = "1.2.4"
    PowerShellVersion = "3.0"
    ClrVersion = "4.0"
    RootModule = "PackageManagement.psm1"
    Description = 'PackageManagement (a.k.a. OneGet) is a new way to discover and install software packages from around the web.
 It is a manager or multiplexer of existing package managers (also called package providers) that unifies Windows package management with a single Windows PowerShell interface. With PackageManagement, you can do the following.
  - Manage a list of software repositories in which packages can be searched, acquired and installed
  - Discover software packages
  - Seamlessly install, uninstall, and inventory packages from one or more software repositories'

    CmdletsToExport = @(
        'Find-Package',
        'Get-Package',
        'Get-PackageProvider',
        'Get-PackageSource',
        'Install-Package',
        'Import-PackageProvider'
        'Find-PackageProvider'
        'Install-PackageProvider'
        'Register-PackageSource',
        'Set-PackageSource',
        'Unregister-PackageSource',
        'Uninstall-Package'
        'Save-Package'
    )

    FormatsToProcess  = @('PackageManagement.format.ps1xml')

    PrivateData = @{
        PSData = @{
            Tags = @('PackageManagement', 'PSEdition_Core', 'PSEdition_Desktop', 'Windows', 'Linux', 'macOS')
            ProjectUri = 'https://oneget.org'
        }
    }
}
```

## <a name="dependency-on-native-libraries"></a>Зависимость от собственных библиотек

Модули, предназначенные для использования в разных операционных системах или архитектурах процессоров, могут зависеть от управляемой библиотеки, которая в свою очередь зависит от некоторых собственных библиотек.

До выпуска PowerShell 7 нужно было применять пользовательский код для загрузки соответствующей собственной библиотеки, чтобы управляемая библиотека могла найти ее.

Но в PowerShell 7 поиск собственных двоичных файлов для загрузки выполняется во вложенных папках в расположении управляемой библиотеки в соответствии с нотацией для [Каталог идентификаторов сред выполнения в .NET][].

```
managed.dll folder
                |
                |--- 'win-x64' folder
                |       |--- native.dll
                |
                |--- 'win-x86' folder
                |       |--- native.dll
                |
                |--- 'win-arm' folder
                |       |--- native.dll
                |
                |--- 'win-arm64' folder
                |       |--- native.dll
                |
                |--- 'linux-x64' folder
                |       |--- native.so
                |
                |--- 'linux-x86' folder
                |       |--- native.so
                |
                |--- 'linux-arm' folder
                |       |--- native.so
                |
                |--- 'linux-arm64' folder
                |       |--- native.so
                |
                |--- 'osx-x64' folder
                |       |--- native.dylib
```

<!-- reference links -->
[.NET Framework]: /dotnet/framework/
[.NET Core]: /dotnet/core/
[PSSnapIn]: /dotnet/api/system.management.automation.pssnapin
[New-ModuleManifest]: /powershell/module/microsoft.powershell.core/new-modulemanifest
[Проверки среды выполнения]: /dotnet/api/system.runtime.interopservices.runtimeinformation.frameworkdescription#System_Runtime_InteropServices_RuntimeInformation_FrameworkDescription
[Интерфейс командной строки.NET]: /dotnet/core/tools/?tabs=netcore2x
[.NET Standard]: /dotnet/standard/net-standard
[PowerShell Standard]: https://github.com/PowerShell/PowerShellStandard
[PowerShell Standard 5.1]: https://www.nuget.org/packages/PowerShellStandard.Library/5.1.0
[Коллекция PowerShell]: https://www.powershellgallery.com
[.NET Portability Analyzer]: https://github.com/Microsoft/dotnet-apiport
[CompatiblePSEditions]: /powershell/scripting/gallery/concepts/module-psedition-support
[Каталог идентификаторов сред выполнения в .NET]: https://docs.microsoft.com/dotnet/core/rid-catalog
