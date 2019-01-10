---
ms.date: 12/14/2018
keywords: powershell,командлет
title: Создание переносимых модулей
ms.openlocfilehash: 38a93b5b030d58784b91292e2cd060b3a2c19a00
ms.sourcegitcommit: d396d0e4cfe3d279f399c17e7337380a31d373ac
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2018
ms.locfileid: "53747727"
---
# <a name="portable-modules"></a>Переносимые модулей

Windows PowerShell, написанные для [.NET Framework][] хотя PowerShell Core записывается для [.NET Core][]. Переносимые модули — это модули, которые работают в Windows PowerShell и PowerShell Core. Хотя .NET Framework и .NET Core и высокий уровень совместимости, существуют различия в доступные интерфейсы API. Существуют различия в API в Windows PowerShell и PowerShell Core. Модули, предназначен для использования в обеих средах должны учитывать эти различия.

## <a name="porting-an-existing-module"></a>Перенос существующего модуля

### <a name="porting-a-pssnapin"></a>Перенос PSSnapIn

Оснастки PowerShell (PSSnapIn) не поддерживаются в PowerShell Core. Тем не менее это просто преобразовать PSSnapIn модуля PowerShell. Как правило, является регистрационный код PSSnapIn в один исходный файл класса, производного от [PSSnapIn][]. Удалить этот исходный файл из построения; больше не используется.

Используйте [New-ModuleManifest][] для создания нового манифеста модуля, который устраняет необходимость для кода регистрации PSSnapIn. Некоторые значения из PSSnapIn (например, описание) могут использоваться повторно в манифесте модуля.

`RootModule` Свойства в манифесте модуля должно быть присвоено имя сборки (dll), реализация командлеты.

### <a name="the-net-portability-analyzer-aka-apiport"></a>Анализатор переносимости .NET (также называемые APIPort)

Порт модули, написанные для Windows PowerShell для работы с PowerShell Core, начните с [анализатор переносимости .NET][]. Запустите это средство для скомпилированной сборки для определения API .NET, используемые в модуле совместимы с .NET Framework, .NET Core и других сред выполнения .NET. Утилита предлагает альтернативные интерфейсы API, если они существуют. В противном случае может потребоваться добавить [проверки времени выполнения][] и ограничить возможности, недоступные в конкретных средах выполнения.

## <a name="creating-a-new-module"></a>Создание нового модуля

Если создается новый модуль, рекомендуется использовать [ИНТЕРФЕЙС КОМАНДНОЙ СТРОКИ .NET][].

### <a name="installing-the-powershell-standard-module-template"></a>Установка модуля PowerShell Standard шаблона

После установки интерфейса командной строки .NET, установите библиотеку шаблонов для создания простого модуля PowerShell.
Модуль будут совместимы с Windows PowerShell, PowerShell Core, Windows, Linux и macOS.

В следующем примере показано, как установить шаблон:

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

После установки шаблона, можно создать новый проект модуля PowerShell с использованием этого шаблона. В этом примере образец модуля называется «myModule».

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

Используйте стандартные команды интерфейса командной строки .NET для сборки проекта.

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

### <a name="testing-the-module"></a>Проверка модуля

После создания модуля, можно импортировать его и выполнить пример командлета.

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

В следующих разделах подробно некоторые технологии, используемые этим шаблоном.

## <a name="net-standard-library"></a>Библиотека .NET standard

[.NET standard][] представляет собой официальную спецификацию интерфейсов API .NET, которые доступны во всех реализациях .NET. Управляемый код, предназначенных для .NET Standard работает с версии .NET Framework и .NET Core, которые совместимы с этой версией .NET Standard.

> [!NOTE]
> Несмотря на то, что API могут существовать в .NET Standard, реализации API в .NET Core может вызывать исключение `PlatformNotSupportedException` во время выполнения, поэтому для проверки совместимости с Windows PowerShell и PowerShell Core, мы рекомендуем проводить тесты для модуля в обеих средах.
> Также выполните тесты в Linux и macOS, если модуль должен быть между различными платформами.

Применение .NET Standard гарантирует, что, по мере развития модуль несовместимых API не случайно введение в модуль. Во время компиляции, а не среды выполнения будут обнаружены несовместимости.

Тем не менее он не требуется для .NET Standard, для модуля для работы с Windows PowerShell и PowerShell Core, до тех пор, пока вы используете совместимые интерфейсы API. Промежуточный язык (IL) совместим между двумя средами выполнения. Можно создавать решения .NET Framework 4.6.1, которая совместима с .NET Standard 2.0. Если вы не используете API вне .NET Standard 2.0, затем модуль работает с PowerShell Core 6 без повторной компиляции.

## <a name="powershell-standard-library"></a>PowerShell стандартной библиотеке

[Стандартный PowerShell][] библиотека — это Формальная спецификация API-интерфейсы PowerShell доступен во всех версиях PowerShell, не меньше версии этого стандарта.

Например [Стандартный PowerShell 5.1][] является совместимым с Windows PowerShell 5.1 и PowerShell Core 6.0 или более поздней версии.

Мы рекомендуем компиляции модуля с помощью библиотеки Standard PowerShell. Библиотека гарантирует, что API-интерфейсы будут доступны и реализованных в Windows PowerShell и PowerShell Core 6.
Стандартный PowerShell позволяет всегда пересылает совместимой. Модуль, созданные с помощью PowerShell стандартные библиотеки 5.1 всегда был совместим с будущими версиями PowerShell.

## <a name="module-manifest"></a>Манифест модуля

### <a name="indicating-compatibility-with-windows-powershell-and-powershell-core"></a>Указывающее, совместимость с Windows PowerShell и PowerShell Core

После проверки работы вашего модуля с помощью Windows PowerShell и PowerShell Core, манифеста модуля следует явно указать совместимости с помощью [CompatiblePSEditions][] свойство. Значение `Desktop` означает, что модуль совместима с Windows PowerShell, то время как значение из `Core` означает, что модуль является совместимым с PowerShell Core. Включая `Desktop` и `Core` означает, что модуль совместима с Windows PowerShell и PowerShell Core.

> [!NOTE]
> `Core` не означает, что модуль совместима с Windows, Linux и macOS.
> **CompatiblePSEditions** свойство появилось в PowerShell версии 5. Модуль манифесты, использующих **CompatiblePSEditions** свойства не удалось загрузить в версиях до PowerShell версии 5.

### <a name="indicating-os-compatibility"></a>Указывающее, совместимость ОС

Во-первых проверьте, что модуль работает в Linux и macOS. Затем результатами означают совместимость с этими операционными системами в манифесте модуля. Это поможет пользователям найти модуль для своей операционной системы, при публикации [Коллекция PowerShell][].

В манифесте модуля `PrivateData` свойство имеет `PSData` подчиненных свойств. Необязательный `Tags` свойство `PSData` принимает массив значений, которые отображаются в коллекции PowerShell. В коллекции PowerShell поддерживает следующие значения совместимости:

| Tag               | Описание                                |
|-------------------|--------------------------------------------|
| PSEdition_Core    | Совместимость с PowerShell Core 6          |
| PSEdition_Desktop | Совместимость с Windows PowerShell         |
| Windows           | Совместимость с Windows                    |
| Linux             | Совместимость с Linux (не дистрибутиву) |
| macOS             | Совместимый с macOS                      |

Пример:

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

<!-- reference links -->
[.NET Framework]: /dotnet/framework/
[.NET Core]: /dotnet/core/
[PSSnapIn]: /dotnet/api/system.management.automation.pssnapin
[New-ModuleManifest]: /powershell/module/microsoft.powershell.core/new-modulemanifest
[проверки времени выполнения]: /dotnet/api/system.runtime.interopservices.runtimeinformation.frameworkdescription#System_Runtime_InteropServices_RuntimeInformation_FrameworkDescription
[ИНТЕРФЕЙС КОМАНДНОЙ СТРОКИ .NET]: /dotnet/core/tools/?tabs=netcore2x
[.NET Standard]: /dotnet/standard/net-standard
[Стандартный PowerShell]: https://github.com/PowerShell/PowerShellStandard
[Стандартный PowerShell 5.1]: https://www.nuget.org/packages/PowerShellStandard.Library/5.1.0
[Коллекция PowerShell]: https://www.powershellgallery.com
[Анализатор переносимости .NET]: https://github.com/Microsoft/dotnet-apiport
[CompatiblePSEditions]: /powershell/gallery/concepts/module-psedition-support
