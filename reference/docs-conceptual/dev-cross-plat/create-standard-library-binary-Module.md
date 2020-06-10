---
title: Как создать двоичный модуль библиотеки Standard
description: Библиотека PowerShell Standard позволяет создавать межплатформенные модули, которые работают как в PowerShell Core, так и в Windows PowerShell 5.1.
ms.date: 05/23/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: 51734fd9232e7c33b11c6c5a6abddbcc1f28413c
ms.sourcegitcommit: ed4a895d672334c7b02fb7ef6e950dbc2ba4a197
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/28/2020
ms.locfileid: "84149417"
---
# <a name="how-to-create-a-standard-library-binary-module"></a>Как создать двоичный модуль библиотеки Standard

Предположим, что нам нужен двоичный модуль. Создадим его с помощью [Библиотека PowerShell Standard][]. Нужные инструкции вы найдете в [Создание межплатформенного двоичного модуля][].
Здесь мы сделаем то же самое, но с дополнительными комментариями.

> [!NOTE]
> [Оригинал статьи][] этой статьи впервые был опубликован в блоге автора [@KevinMarquette][]. Команда разработчиков PowerShell благодарит Кевина за то, что он поделился с нами этим материалом. Читайте его блог — [PowerShellExplained.com][].

## <a name="what-is-the-powershell-standard-library"></a>Что собой представляет библиотека PowerShell Standard

Она позволяет создавать межплатформенные модули, которые работают как в PowerShell Core, так и в Windows PowerShell 5.1 (и 3.0).

## <a name="planning-our-module"></a>Планирование модуля

План для этого модуля включает создание папки `src` для кода C# и структурирование остальных компонентов в виде модуля скрипта. Для этого понадобится скрипт сборки, чтобы скомпилировать все компоненты в папку `output`. Она имеет следующую структуру:

```
MyModule
├───src
├───Output
│   └───MyModule
├───MyModule
│   ├───Data
│   ├───Private
│   └───Public
└───Tests
```

## <a name="getting-started"></a>Приступая к работе

Обычно я использую шаблон Plaster, но в нем нет поддержки двоичных модулей. Не беда, я создам шаблон самостоятельно.

Сначала нужно создать папку и репозиторий Git. Назовем модуль `$module`. Это упростит повторное использование этих примеров при необходимости.

```powershell
$module = 'MyModule'
New-Item -Path $module -Type Directory
Set-Location $module
git init
```

Затем создайте папки корневого уровня.

```powershell
New-Item -Path 'src' -Type Directory
New-Item -Path 'Output' -Type Directory
New-Item -Path 'Tests' -Type Directory
New-Item -Path $module -Type Directory
```

### <a name="binary-module-setup"></a>Настройка двоичного модуля

Статья о создании двоичного модуля, поэтому сосредоточимся на этом. В этом разделе используются примеры из руководства по [Создание межплатформенного двоичного модуля][]. Ознакомьтесь с ним, если вам нужно что-то уточнить или возникли какие либо проблемы.

Сначала необходимо проверить версию установленного [Пакет SDK для .NET Core][]. Я использую 2.1.4, но вам для работы пригодится любая версия, начиная с 2.0.0.

```powershell
PS> dotnet --version
2.1.4
```

В следующем разделе используется папка `src`.

```powershell
Set-Location 'src'
```

Создайте библиотеку классов с помощью команды dotnet.

```powershell
dotnet new classlib --name $module
```

При этом проект библиотеки будет создан во вложенной папке. Мне так неудобно, поэтому я перемещу эти файлы на уровень выше.

```powershell
Move-Item -Path .\$module\* -Destination .\
Remove-Item $module -Recurse
```

Задайте версию пакета SDK для .NET Core для проекта. У меня пакет SDK 2.1, поэтому я укажу 2.1.0.
Если у вас SDK 2.0, укажите 2.0.0.

```powershell
dotnet new globaljson --sdk-version 2.1.0
```

Добавьте в проект [пакет NuGet][] библиотеки PowerShell Standard. Убедитесь, что вы используете самую последнюю версию для необходимого уровня совместимости. По умолчанию я бы использовал последнюю версию, но не думаю, что этот модуль использует возможности версий старше PowerShell 3.0.

```powershell
dotnet add package PowerShellStandard.Library --version 7.0.0-preview.1
```

Наша папка src должна иметь примерно такой вид:

```powershell
PS> Get-ChildItem
    Directory: \MyModule\src

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        7/14/2018   9:51 PM                obj
-a----        7/14/2018   9:51 PM             86 Class1.cs
-a----        7/14/2018  10:03 PM            259 MyModule.csproj
-a----        7/14/2018  10:05 PM             45 global.json
```

Теперь можно добавить свой код в проект.

### <a name="building-a-binary-cmdlet"></a>Создание двоичного командлета

Нам необходимо обновить `src\Class1.cs`, чтобы он содержал начальный командлет:

```csharp
using System;
using System.Management.Automation;

namespace MyModule
{
    [Cmdlet( VerbsDiagnostic.Resolve , "MyCmdlet")]
    public class ResolveMyCmdletCommand : PSCmdlet
    {
        [Parameter(Position=0)]
        public Object InputObject { get; set; }

        protected override void EndProcessing()
        {
            this.WriteObject(this.InputObject);
            base.EndProcessing();
        }
    }
}
```

Переименуйте файл в соответствии с именем класса.

```powershell
Rename-Item .\Class1.cs .\ResolveMyCmdletCommand.cs
```

Затем мы можем создать нужный модуль.

```powershell
PS> dotnet build

Microsoft (R) Build Engine version 15.5.180.51428 for .NET Core
Copyright (C) Microsoft Corporation. All rights reserved.

Restore completed in 18.19 ms for C:\workspace\MyModule\src\MyModule.csproj.
MyModule -> C:\workspace\MyModule\src\bin\Debug\netstandard2.0\MyModule.dll

Build succeeded.
    0 Warning(s)
    0 Error(s)

Time Elapsed 00:00:02.19
```

Можно вызвать `Import-Module` для новой библиотеки DLL, чтобы загрузить новый командлет.

```powershell
PS> Import-Module .\bin\Debug\netstandard2.0\$module.dll
PS> Get-Command -Module $module

CommandType Name                    Version Source
----------- ----                    ------- ------
Cmdlet      Resolve-MyCmdlet        1.0.0.0 MyModule
```

Если операция импорта завершается сбоем, попробуйте обновить .NET до версии 4.7.1 или более поздней. В [Создание межплатформенного двоичного модуля][] содержится больше сведений о поддержке .NET и совместимости с предыдущими версиями .NET.

### <a name="module-manifest"></a>Манифест модуля

Итак, у нас получилось импортировать библиотеку DLL и создать рабочий модуль. Теперь давайте создадим манифест модуля. Манифест нужен для того, чтобы впоследствии опубликовать модуль в PSGallery.

Чтобы создать манифест модуля, в корневом каталоге проекта нужно выполнить следующую команду.

```powershell
$manifestSplat = @{
    Path              = ".\$module\$module.psd1"
    Author            = 'Kevin Marquette'
    NestedModules     = @('bin\MyModule.dll')
    RootModule        = "$module.psm1"
    FunctionsToExport = @('Resolve-MyCmdlet')
}
New-ModuleManifest @manifestSplat
```

Я также создам пустой корневой модуль для функций PowerShell, которые будут реализованы позже.

```powershell
Set-Content -Value '' -Path ".\$module\$module.psm1"
```

Это позволит внедрить в проект как обычные функции PowerShell, так и двоичные командлеты.

### <a name="building-the-full-module"></a>Создание модуля

Я компилирую все вместе в выходную папку. Для этого нам необходимо создать скрипт сборки. Обычно я добавляю это в скрипт `Invoke-Build`, но не будем ничего усложнять в этом примере. Добавьте следующий код к `build.ps1` в корне проекта.

```powershell
$module = 'MyModule'
Push-Location $PSScriptRoot

dotnet build $PSScriptRoot\src -o $PSScriptRoot\output\$module\bin
Copy-Item "$PSScriptRoot\$module\*" "$PSScriptRoot\output\$module" -Recurse -Force

Import-Module "$PSScriptRoot\Output\$module\$module.psd1"
Invoke-Pester "$PSScriptRoot\Tests"
```

Эти команды создают библиотеку DLL и размещают ее в папке `output\$module\bin`. Затем другие файлы модуля копируются в нужное место.

```
Output
└───MyModule
    │   MyModule.psd1
    │   MyModule.psm1
    │
    └───bin
            MyModule.deps.json
            MyModule.dll
            MyModule.pdb
```

На этом этапе мы можем импортировать наш модуль с помощью файла psd1.

```powershell
Import-Module ".\Output\$module\$module.psd1"
```

Сейчас можно переместить папку `.\Output\$module` в каталог `$env:PSModulePath`, откуда она будет автоматически загружать нашу команду при необходимости.

### <a name="update-dotnet-new-psmodule"></a>Новый шаблон PSModule для dotnet

Я узнал, что для `dotnet` появился шаблон `PSModule`.

Все описанные выше действия по-прежнему актуальны, но этот шаблон устраняет необходимость во многих из них. Он достаточно нов и пока дорабатывается, но со временем должен стать только лучше.

Далее показано, как установить и использовать шаблон PSModule.

```powershell
dotnet new -i Microsoft.PowerShell.Standard.Module.Template
dotnet new psmodule
dotnet build
Import-Module "bin\Debug\netstandard2.0\$module.dll"
Get-Module $module
```

Этот пока несовершенный шаблон добавляет пакет SDK для .NET, устанавливает библиотеку PowerShell Standard и создает пример класса в проекте. Вы уже можете скомпилировать и запустить его.

## <a name="important-details"></a>Важные сведения

Прежде чем закончить эту статью, ознакомьтесь с другими важными сведениями.

### <a name="unloading-dlls"></a>Выгрузка библиотек DLL

После загрузки двоичного модуля его нельзя выгрузить. DLL-файл блокируется до своей выгрузки. Это может быть неудобно при разработке, поскольку каждый раз при внесении изменений и выполнении сборки файл часто оказывается заблокированным. Единственным надежным способом решения этой задачи является закрытие сеанса PowerShell, который загрузил библиотеку DLL.

### <a name="vs-code-reload-window-action"></a>Перезагрузка окна в VS Code

Я занимаюсь разработкой преимущественно в [Код VS][]. При работе с двоичным модулем (или модулем с классами) я обычно перезагружаю VS Code перед каждой сборкой.
Сочетание клавиш <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> выводит окно команд, где в вверху у меня всегда располагается `Reload Window`.

### <a name="nested-powershell-sessions"></a>Вложенные сеансы PowerShell

Еще один вариант — подготовить надлежащее тестирование Pester. При этом можно настроить скрипт build.ps1 так, чтобы он запускал новый сеанс PowerShell, выполнял сборку, проверял работу кода и закрывал сеанс.

### <a name="updating-installed-modules"></a>Обновление установленных модулей

Эта блокировка мешает при обновлении локально установленного модуля. Всякий раз, когда он загружен сеансом, приходится искать его и закрывать. Это не так проблематично при установке из PSGallery, так как управление версиями модуля помещает новый модуль в другую папку.

Вы можете создать локальный экземпляр PSGallery и публиковать код в него при сборке. Затем можно выполнить локальную установку из этого экземпляра PSGallery. Все это может показаться трудоемким, но на деле это так же просто, как запуск контейнера Docker. Я подробно расскажу о том, как это сделать, в [Использование сервера NuGet для PSRepository][].

## <a name="why-binary-modules"></a>Зачем нужны двоичные модули

Я сразу взялся объяснять, как создать двоичный модуль, не сказав, зачем он нужен. Если вы пишете код на C#, то часто лишаетесь возможностей, предоставляемых командлетами и функциями PowerShell. Это основная причина, почему я не использовал двоичные модули раньше.

Но если вы создаете модуль, который не зависит от множества других команд PowerShell, преимущество в производительности может оказаться значительным. С переходом на C# вы избавляетесь от издержек, связанных с работой PowerShell. Оболочка PowerShell оптимизирована для работы администраторов, а не компьютера, и это несколько снижает скорость выполнения кода.

В нашей среде выполняется один критически важный процесс — обработка большого массива JSON-файлов и хэш-таблиц. Мы максимально оптимизировали работу PowerShell, но выполнение этого процесса все равно занимало 12 минут. Модуль уже содержал много кода C#, выполняемого PowerShell, что упростило переход на использование двоичного модуля. В результате время выполнения процесса сократилось с 12 до менее 4 минут.

### <a name="hybrid-modules"></a>Гибридные модули

Вы можете сочетать двоичные командлеты с расширенными функциями PowerShell. Это именно то, что демонстрируется в этом руководстве. При этом вы также можете применить все свои знания о модулях скриптов.
Пустой файл `psm1` я здесь создал для того, чтобы вы могли позднее добавить в него другие функции PowerShell.

Почти все скомпилированные командлеты, которые мы создали, сначала были функциями PowerShell. Все наши двоичные модули на самом деле являются гибридными модулями.

### <a name="build-scripts"></a>Скрипты сборки

Со скриптом сборки все просто. Я обычно использую большой скрипт `Invoke-Build` как элемент конвейера CI/CD. Он выполняет много задач, таких как тесты Pester, выполнение PSScriptAnalyzer, управление версиями и публикация в PSGallery. Когда я начал использовать скрипт сборки для модулей, обнаружилось много вещей, которые можно добавить в него.

## <a name="final-thoughts"></a>В заключение

Двоичные модули легко создавать. Я не рассматривал синтаксис C# для создания командлета, так как в [Пакет SDK для Windows PowerShell][] есть масса документации по нему. С модулями определенно стоит поэкспериментировать на начальном этапе изучения C#.

<!-- link references -->
[Оригинал статьи]: https://powershellexplained.com/2018-08-04-Powershell-Standard-Library-Binary-Module/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[Библиотека PowerShell Standard]: https://github.com/PowerShell/PowerShellStandard
[Создание межплатформенного двоичного модуля]: https://github.com/PowerShell/PowerShell/blob/master/docs/cmdlet-example/command-line-simple-example.md
[Пакет SDK для .NET Core]: https://www.microsoft.com/net/download/core
[Использование сервера NuGet для PSRepository]: https://powershellexplained.com/2018-03-03-Powershell-Using-a-NuGet-server-for-a-PSRepository/
[Пакет SDK для Windows PowerShell]: /powershell/scripting/developer/windows-powershell-reference
[Код VS]: https://code.visualstudio.com
[Пакет NuGet]: https://www.nuget.org/packages/PowerShellStandard.Library/
