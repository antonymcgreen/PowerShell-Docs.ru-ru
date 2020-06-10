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
# <a name="how-to-create-a-standard-library-binary-module"></a><span data-ttu-id="a15b7-103">Как создать двоичный модуль библиотеки Standard</span><span class="sxs-lookup"><span data-stu-id="a15b7-103">How to create a Standard Library binary module</span></span>

<span data-ttu-id="a15b7-104">Предположим, что нам нужен двоичный модуль.</span><span class="sxs-lookup"><span data-stu-id="a15b7-104">I recently had an idea for module that I wanted to implement as a binary module.</span></span> <span data-ttu-id="a15b7-105">Создадим его с помощью [Библиотека PowerShell Standard][].</span><span class="sxs-lookup"><span data-stu-id="a15b7-105">I have yet to create one using the [PowerShell Standard Library][] so this felt like a good opportunity.</span></span> <span data-ttu-id="a15b7-106">Нужные инструкции вы найдете в [Создание межплатформенного двоичного модуля][].</span><span class="sxs-lookup"><span data-stu-id="a15b7-106">I used the [Creating a cross-platform binary module][] guide to create this module without any roadblocks.</span></span>
<span data-ttu-id="a15b7-107">Здесь мы сделаем то же самое, но с дополнительными комментариями.</span><span class="sxs-lookup"><span data-stu-id="a15b7-107">We're going to walk that same process and I'll add a little extra commentary along the way.</span></span>

> [!NOTE]
> <span data-ttu-id="a15b7-108">[Оригинал статьи][] этой статьи впервые был опубликован в блоге автора [@KevinMarquette][].</span><span class="sxs-lookup"><span data-stu-id="a15b7-108">The [original version][] of this article appeared on the blog written by [@KevinMarquette][].</span></span> <span data-ttu-id="a15b7-109">Команда разработчиков PowerShell благодарит Кевина за то, что он поделился с нами этим материалом.</span><span class="sxs-lookup"><span data-stu-id="a15b7-109">The PowerShell team thanks Kevin for sharing this content with us.</span></span> <span data-ttu-id="a15b7-110">Читайте его блог — [PowerShellExplained.com][].</span><span class="sxs-lookup"><span data-stu-id="a15b7-110">Please check out his blog at [PowerShellExplained.com][].</span></span>

## <a name="what-is-the-powershell-standard-library"></a><span data-ttu-id="a15b7-111">Что собой представляет библиотека PowerShell Standard</span><span class="sxs-lookup"><span data-stu-id="a15b7-111">What is the PowerShell Standard Library?</span></span>

<span data-ttu-id="a15b7-112">Она позволяет создавать межплатформенные модули, которые работают как в PowerShell Core, так и в Windows PowerShell 5.1 (и 3.0).</span><span class="sxs-lookup"><span data-stu-id="a15b7-112">The PowerShell Standard Library allows us to create cross platform modules that work in both PowerShell Core and with Windows PowerShell 5.1 (or 3.0).</span></span>

## <a name="planning-our-module"></a><span data-ttu-id="a15b7-113">Планирование модуля</span><span class="sxs-lookup"><span data-stu-id="a15b7-113">Planning our module</span></span>

<span data-ttu-id="a15b7-114">План для этого модуля включает создание папки `src` для кода C# и структурирование остальных компонентов в виде модуля скрипта.</span><span class="sxs-lookup"><span data-stu-id="a15b7-114">The plan for this module is to create a `src` folder for the C# code and structure the rest like I would for a script module.</span></span> <span data-ttu-id="a15b7-115">Для этого понадобится скрипт сборки, чтобы скомпилировать все компоненты в папку `output`.</span><span class="sxs-lookup"><span data-stu-id="a15b7-115">This includes using a build script to compile everything into an `output` folder.</span></span> <span data-ttu-id="a15b7-116">Она имеет следующую структуру:</span><span class="sxs-lookup"><span data-stu-id="a15b7-116">The folder structure looks like this:</span></span>

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

## <a name="getting-started"></a><span data-ttu-id="a15b7-117">Приступая к работе</span><span class="sxs-lookup"><span data-stu-id="a15b7-117">Getting Started</span></span>

<span data-ttu-id="a15b7-118">Обычно я использую шаблон Plaster, но в нем нет поддержки двоичных модулей.</span><span class="sxs-lookup"><span data-stu-id="a15b7-118">I normally use a Plaster template but my current template doesn't have any binary module support yet.</span></span> <span data-ttu-id="a15b7-119">Не беда,</span><span class="sxs-lookup"><span data-stu-id="a15b7-119">Not a big deal.</span></span> <span data-ttu-id="a15b7-120">я создам шаблон самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="a15b7-120">I'll create this one by hand this time.</span></span>

<span data-ttu-id="a15b7-121">Сначала нужно создать папку и репозиторий Git.</span><span class="sxs-lookup"><span data-stu-id="a15b7-121">First I need to create the folder and create the git repo.</span></span> <span data-ttu-id="a15b7-122">Назовем модуль `$module`.</span><span class="sxs-lookup"><span data-stu-id="a15b7-122">I'm using `$module` as a placeholder for the module name.</span></span> <span data-ttu-id="a15b7-123">Это упростит повторное использование этих примеров при необходимости.</span><span class="sxs-lookup"><span data-stu-id="a15b7-123">This should make it easier for you to reuse these examples if needed.</span></span>

```powershell
$module = 'MyModule'
New-Item -Path $module -Type Directory
Set-Location $module
git init
```

<span data-ttu-id="a15b7-124">Затем создайте папки корневого уровня.</span><span class="sxs-lookup"><span data-stu-id="a15b7-124">Then create the root level folders.</span></span>

```powershell
New-Item -Path 'src' -Type Directory
New-Item -Path 'Output' -Type Directory
New-Item -Path 'Tests' -Type Directory
New-Item -Path $module -Type Directory
```

### <a name="binary-module-setup"></a><span data-ttu-id="a15b7-125">Настройка двоичного модуля</span><span class="sxs-lookup"><span data-stu-id="a15b7-125">Binary module setup</span></span>

<span data-ttu-id="a15b7-126">Статья о создании двоичного модуля, поэтому сосредоточимся на этом.</span><span class="sxs-lookup"><span data-stu-id="a15b7-126">This article os focused on the binary module so that is where we'll start.</span></span> <span data-ttu-id="a15b7-127">В этом разделе используются примеры из руководства по [Создание межплатформенного двоичного модуля][].</span><span class="sxs-lookup"><span data-stu-id="a15b7-127">This section pulls examples from the [Creating a cross-platform binary module][] guide.</span></span> <span data-ttu-id="a15b7-128">Ознакомьтесь с ним, если вам нужно что-то уточнить или возникли какие либо проблемы.</span><span class="sxs-lookup"><span data-stu-id="a15b7-128">Review that guide if you need more details or have any issues.</span></span>

<span data-ttu-id="a15b7-129">Сначала необходимо проверить версию установленного [Пакет SDK для .NET Core][].</span><span class="sxs-lookup"><span data-stu-id="a15b7-129">First thing we want to do is check the version of the [dotnet core SDK][] that we installed.</span></span> <span data-ttu-id="a15b7-130">Я использую 2.1.4, но вам для работы пригодится любая версия, начиная с 2.0.0.</span><span class="sxs-lookup"><span data-stu-id="a15b7-130">I'm using 2.1.4, but you should have 2.0.0 or newer before continuing.</span></span>

```powershell
PS> dotnet --version
2.1.4
```

<span data-ttu-id="a15b7-131">В следующем разделе используется папка `src`.</span><span class="sxs-lookup"><span data-stu-id="a15b7-131">I'm working out of the `src` folder for this section.</span></span>

```powershell
Set-Location 'src'
```

<span data-ttu-id="a15b7-132">Создайте библиотеку классов с помощью команды dotnet.</span><span class="sxs-lookup"><span data-stu-id="a15b7-132">Using the dotnet command, create a new class library.</span></span>

```powershell
dotnet new classlib --name $module
```

<span data-ttu-id="a15b7-133">При этом проект библиотеки будет создан во вложенной папке. Мне так неудобно,</span><span class="sxs-lookup"><span data-stu-id="a15b7-133">This created the library project in a subfolder but I don't want that extra level of nesting.</span></span> <span data-ttu-id="a15b7-134">поэтому я перемещу эти файлы на уровень выше.</span><span class="sxs-lookup"><span data-stu-id="a15b7-134">I'm going to move those files up a level.</span></span>

```powershell
Move-Item -Path .\$module\* -Destination .\
Remove-Item $module -Recurse
```

<span data-ttu-id="a15b7-135">Задайте версию пакета SDK для .NET Core для проекта.</span><span class="sxs-lookup"><span data-stu-id="a15b7-135">Set the .NET core SDK version for the project.</span></span> <span data-ttu-id="a15b7-136">У меня пакет SDK 2.1, поэтому я укажу 2.1.0.</span><span class="sxs-lookup"><span data-stu-id="a15b7-136">I have the 2.1 SDK so I'm going to specify 2.1.0.</span></span>
<span data-ttu-id="a15b7-137">Если у вас SDK 2.0, укажите 2.0.0.</span><span class="sxs-lookup"><span data-stu-id="a15b7-137">Use 2.0.0 if you're using the 2.0 SDK.</span></span>

```powershell
dotnet new globaljson --sdk-version 2.1.0
```

<span data-ttu-id="a15b7-138">Добавьте в проект [пакет NuGet][] библиотеки PowerShell Standard.</span><span class="sxs-lookup"><span data-stu-id="a15b7-138">Add the PowerShell Standard Library [NuGet package][] to the project.</span></span> <span data-ttu-id="a15b7-139">Убедитесь, что вы используете самую последнюю версию для необходимого уровня совместимости.</span><span class="sxs-lookup"><span data-stu-id="a15b7-139">Make sure you use the most recent version available for the level of compatibility that you need.</span></span> <span data-ttu-id="a15b7-140">По умолчанию я бы использовал последнюю версию, но не думаю, что этот модуль использует возможности версий старше PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="a15b7-140">I would default to the latest version but I don't think this module leverages any features newer than PowerShell 3.0.</span></span>

```powershell
dotnet add package PowerShellStandard.Library --version 7.0.0-preview.1
```

<span data-ttu-id="a15b7-141">Наша папка src должна иметь примерно такой вид:</span><span class="sxs-lookup"><span data-stu-id="a15b7-141">We should have a src folder that looks like this:</span></span>

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

<span data-ttu-id="a15b7-142">Теперь можно добавить свой код в проект.</span><span class="sxs-lookup"><span data-stu-id="a15b7-142">Now we're ready to add our own code to the project.</span></span>

### <a name="building-a-binary-cmdlet"></a><span data-ttu-id="a15b7-143">Создание двоичного командлета</span><span class="sxs-lookup"><span data-stu-id="a15b7-143">Building a binary cmdlet</span></span>

<span data-ttu-id="a15b7-144">Нам необходимо обновить `src\Class1.cs`, чтобы он содержал начальный командлет:</span><span class="sxs-lookup"><span data-stu-id="a15b7-144">We need to update the `src\Class1.cs` to contain this starter cmdlet:</span></span>

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

<span data-ttu-id="a15b7-145">Переименуйте файл в соответствии с именем класса.</span><span class="sxs-lookup"><span data-stu-id="a15b7-145">Rename the file to match the class name.</span></span>

```powershell
Rename-Item .\Class1.cs .\ResolveMyCmdletCommand.cs
```

<span data-ttu-id="a15b7-146">Затем мы можем создать нужный модуль.</span><span class="sxs-lookup"><span data-stu-id="a15b7-146">Then we can build our module.</span></span>

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

<span data-ttu-id="a15b7-147">Можно вызвать `Import-Module` для новой библиотеки DLL, чтобы загрузить новый командлет.</span><span class="sxs-lookup"><span data-stu-id="a15b7-147">We can call `Import-Module` on the new dll to load our new CMDlet.</span></span>

```powershell
PS> Import-Module .\bin\Debug\netstandard2.0\$module.dll
PS> Get-Command -Module $module

CommandType Name                    Version Source
----------- ----                    ------- ------
Cmdlet      Resolve-MyCmdlet        1.0.0.0 MyModule
```

<span data-ttu-id="a15b7-148">Если операция импорта завершается сбоем, попробуйте обновить .NET до версии 4.7.1 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="a15b7-148">If the import fails on your system, try updating .NET to 4.7.1 or newer.</span></span> <span data-ttu-id="a15b7-149">В [Создание межплатформенного двоичного модуля][] содержится больше сведений о поддержке .NET и совместимости с предыдущими версиями .NET.</span><span class="sxs-lookup"><span data-stu-id="a15b7-149">The [Creating a cross-platform binary module][] guide goes into more details on .NET support and compatibility for older versions of .NET.</span></span>

### <a name="module-manifest"></a><span data-ttu-id="a15b7-150">Манифест модуля</span><span class="sxs-lookup"><span data-stu-id="a15b7-150">Module manifest</span></span>

<span data-ttu-id="a15b7-151">Итак, у нас получилось импортировать библиотеку DLL и создать рабочий модуль.</span><span class="sxs-lookup"><span data-stu-id="a15b7-151">It's cool that we can import the dll and have a working module.</span></span> <span data-ttu-id="a15b7-152">Теперь давайте создадим манифест модуля.</span><span class="sxs-lookup"><span data-stu-id="a15b7-152">I like to keep going with it and create a module manifest.</span></span> <span data-ttu-id="a15b7-153">Манифест нужен для того, чтобы впоследствии опубликовать модуль в PSGallery.</span><span class="sxs-lookup"><span data-stu-id="a15b7-153">We need the manifest if we want to publish to the PSGallery later.</span></span>

<span data-ttu-id="a15b7-154">Чтобы создать манифест модуля, в корневом каталоге проекта нужно выполнить следующую команду.</span><span class="sxs-lookup"><span data-stu-id="a15b7-154">From the root of our project, we can run this command to create the module manifest that we need.</span></span>

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

<span data-ttu-id="a15b7-155">Я также создам пустой корневой модуль для функций PowerShell, которые будут реализованы позже.</span><span class="sxs-lookup"><span data-stu-id="a15b7-155">I'm also going to create an empty root module for future PowerShell functions.</span></span>

```powershell
Set-Content -Value '' -Path ".\$module\$module.psm1"
```

<span data-ttu-id="a15b7-156">Это позволит внедрить в проект как обычные функции PowerShell, так и двоичные командлеты.</span><span class="sxs-lookup"><span data-stu-id="a15b7-156">This allows me to mix both normal PowerShell functions and binary Cmdlets in the same project.</span></span>

### <a name="building-the-full-module"></a><span data-ttu-id="a15b7-157">Создание модуля</span><span class="sxs-lookup"><span data-stu-id="a15b7-157">Building the full module</span></span>

<span data-ttu-id="a15b7-158">Я компилирую все вместе в выходную папку.</span><span class="sxs-lookup"><span data-stu-id="a15b7-158">I compile everything together into an output folder.</span></span> <span data-ttu-id="a15b7-159">Для этого нам необходимо создать скрипт сборки.</span><span class="sxs-lookup"><span data-stu-id="a15b7-159">We need to create a build script to do that.</span></span> <span data-ttu-id="a15b7-160">Обычно я добавляю это в скрипт `Invoke-Build`, но не будем ничего усложнять в этом примере.</span><span class="sxs-lookup"><span data-stu-id="a15b7-160">I would normally add this to an `Invoke-Build` script, but we can keep it simple for this example.</span></span> <span data-ttu-id="a15b7-161">Добавьте следующий код к `build.ps1` в корне проекта.</span><span class="sxs-lookup"><span data-stu-id="a15b7-161">Add this to a `build.ps1` at the root of the project.</span></span>

```powershell
$module = 'MyModule'
Push-Location $PSScriptRoot

dotnet build $PSScriptRoot\src -o $PSScriptRoot\output\$module\bin
Copy-Item "$PSScriptRoot\$module\*" "$PSScriptRoot\output\$module" -Recurse -Force

Import-Module "$PSScriptRoot\Output\$module\$module.psd1"
Invoke-Pester "$PSScriptRoot\Tests"
```

<span data-ttu-id="a15b7-162">Эти команды создают библиотеку DLL и размещают ее в папке `output\$module\bin`.</span><span class="sxs-lookup"><span data-stu-id="a15b7-162">These commands build our DLL and place it into our `output\$module\bin` folder.</span></span> <span data-ttu-id="a15b7-163">Затем другие файлы модуля копируются в нужное место.</span><span class="sxs-lookup"><span data-stu-id="a15b7-163">It then copies the other module files into place.</span></span>

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

<span data-ttu-id="a15b7-164">На этом этапе мы можем импортировать наш модуль с помощью файла psd1.</span><span class="sxs-lookup"><span data-stu-id="a15b7-164">At this point, we can import our module with the psd1 file.</span></span>

```powershell
Import-Module ".\Output\$module\$module.psd1"
```

<span data-ttu-id="a15b7-165">Сейчас можно переместить папку `.\Output\$module` в каталог `$env:PSModulePath`, откуда она будет автоматически загружать нашу команду при необходимости.</span><span class="sxs-lookup"><span data-stu-id="a15b7-165">From here, we can drop the `.\Output\$module` folder into our `$env:PSModulePath` directory and it autoloads our command whenever we need it.</span></span>

### <a name="update-dotnet-new-psmodule"></a><span data-ttu-id="a15b7-166">Новый шаблон PSModule для dotnet</span><span class="sxs-lookup"><span data-stu-id="a15b7-166">Update: dotnet new PSModule</span></span>

<span data-ttu-id="a15b7-167">Я узнал, что для `dotnet` появился шаблон `PSModule`.</span><span class="sxs-lookup"><span data-stu-id="a15b7-167">I learned that the `dotnet` tool has a `PSModule` template.</span></span>

<span data-ttu-id="a15b7-168">Все описанные выше действия по-прежнему актуальны, но этот шаблон устраняет необходимость во многих из них. Он достаточно нов и пока дорабатывается,</span><span class="sxs-lookup"><span data-stu-id="a15b7-168">All the steps that I outlined above are still valid, but this template cuts many pf them out. It's still a fairly new template that is still getting some polish placed on it.</span></span> <span data-ttu-id="a15b7-169">но со временем должен стать только лучше.</span><span class="sxs-lookup"><span data-stu-id="a15b7-169">Expect it to keep getting better from here.</span></span>

<span data-ttu-id="a15b7-170">Далее показано, как установить и использовать шаблон PSModule.</span><span class="sxs-lookup"><span data-stu-id="a15b7-170">This is how you use install and use the PSModule template.</span></span>

```powershell
dotnet new -i Microsoft.PowerShell.Standard.Module.Template
dotnet new psmodule
dotnet build
Import-Module "bin\Debug\netstandard2.0\$module.dll"
Get-Module $module
```

<span data-ttu-id="a15b7-171">Этот пока несовершенный шаблон добавляет пакет SDK для .NET, устанавливает библиотеку PowerShell Standard и создает пример класса в проекте.</span><span class="sxs-lookup"><span data-stu-id="a15b7-171">This minimally-viable template takes care of adding the .NET SDK, PowerShell Standard Library, and creates an example class in the project.</span></span> <span data-ttu-id="a15b7-172">Вы уже можете скомпилировать и запустить его.</span><span class="sxs-lookup"><span data-stu-id="a15b7-172">You can build it and run it right away.</span></span>

## <a name="important-details"></a><span data-ttu-id="a15b7-173">Важные сведения</span><span class="sxs-lookup"><span data-stu-id="a15b7-173">Important details</span></span>

<span data-ttu-id="a15b7-174">Прежде чем закончить эту статью, ознакомьтесь с другими важными сведениями.</span><span class="sxs-lookup"><span data-stu-id="a15b7-174">Before we end this article, here are a few other details worth mentioning.</span></span>

### <a name="unloading-dlls"></a><span data-ttu-id="a15b7-175">Выгрузка библиотек DLL</span><span class="sxs-lookup"><span data-stu-id="a15b7-175">Unloading DLLs</span></span>

<span data-ttu-id="a15b7-176">После загрузки двоичного модуля его нельзя выгрузить.</span><span class="sxs-lookup"><span data-stu-id="a15b7-176">Once a binary module is loaded, you can't really unload it.</span></span> <span data-ttu-id="a15b7-177">DLL-файл блокируется до своей выгрузки.</span><span class="sxs-lookup"><span data-stu-id="a15b7-177">The DLL file is locked until you unload it.</span></span> <span data-ttu-id="a15b7-178">Это может быть неудобно при разработке, поскольку каждый раз при внесении изменений и выполнении сборки файл часто оказывается заблокированным.</span><span class="sxs-lookup"><span data-stu-id="a15b7-178">This can be annoying when developing because every time you make a change and want to build it, the file is often locked.</span></span> <span data-ttu-id="a15b7-179">Единственным надежным способом решения этой задачи является закрытие сеанса PowerShell, который загрузил библиотеку DLL.</span><span class="sxs-lookup"><span data-stu-id="a15b7-179">The only reliable way to resolve this is to close the PowerShell session that loaded the DLL.</span></span>

### <a name="vs-code-reload-window-action"></a><span data-ttu-id="a15b7-180">Перезагрузка окна в VS Code</span><span class="sxs-lookup"><span data-stu-id="a15b7-180">VS Code reload window action</span></span>

<span data-ttu-id="a15b7-181">Я занимаюсь разработкой преимущественно в [Код VS][].</span><span class="sxs-lookup"><span data-stu-id="a15b7-181">I do most of my PowerShell dev work in [VS Code][].</span></span> <span data-ttu-id="a15b7-182">При работе с двоичным модулем (или модулем с классами) я обычно перезагружаю VS Code перед каждой сборкой.</span><span class="sxs-lookup"><span data-stu-id="a15b7-182">When I'm working on a binary module (or a module with classes), I've gotten into the habit of reloading VS Code every time I build.</span></span>
<span data-ttu-id="a15b7-183">Сочетание клавиш <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> выводит окно команд, где в вверху у меня всегда располагается `Reload Window`.</span><span class="sxs-lookup"><span data-stu-id="a15b7-183"><kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> pops the command window and `Reload Window` is always at the top of my list.</span></span>

### <a name="nested-powershell-sessions"></a><span data-ttu-id="a15b7-184">Вложенные сеансы PowerShell</span><span class="sxs-lookup"><span data-stu-id="a15b7-184">Nested PowerShell sessions</span></span>

<span data-ttu-id="a15b7-185">Еще один вариант — подготовить надлежащее тестирование Pester.</span><span class="sxs-lookup"><span data-stu-id="a15b7-185">One other option is to have good Pester test coverage.</span></span> <span data-ttu-id="a15b7-186">При этом можно настроить скрипт build.ps1 так, чтобы он запускал новый сеанс PowerShell, выполнял сборку, проверял работу кода и закрывал сеанс.</span><span class="sxs-lookup"><span data-stu-id="a15b7-186">Then you can adjust the build.ps1 script to start a new PowerShell session, perform the build, run the tests, and close the session.</span></span>

### <a name="updating-installed-modules"></a><span data-ttu-id="a15b7-187">Обновление установленных модулей</span><span class="sxs-lookup"><span data-stu-id="a15b7-187">Updating installed modules</span></span>

<span data-ttu-id="a15b7-188">Эта блокировка мешает при обновлении локально установленного модуля.</span><span class="sxs-lookup"><span data-stu-id="a15b7-188">This locking can be annoying when trying to update your locally installed module.</span></span> <span data-ttu-id="a15b7-189">Всякий раз, когда он загружен сеансом, приходится искать его и закрывать.</span><span class="sxs-lookup"><span data-stu-id="a15b7-189">If any session has it loaded, you have to go hunt it down and close it.</span></span> <span data-ttu-id="a15b7-190">Это не так проблематично при установке из PSGallery, так как управление версиями модуля помещает новый модуль в другую папку.</span><span class="sxs-lookup"><span data-stu-id="a15b7-190">This is less of an issue when installing from a PSGallery because module versioning places the new one in a different folder.</span></span>

<span data-ttu-id="a15b7-191">Вы можете создать локальный экземпляр PSGallery и публиковать код в него при сборке.</span><span class="sxs-lookup"><span data-stu-id="a15b7-191">You can set up a local PSGallery and publish to that as part of your build.</span></span> <span data-ttu-id="a15b7-192">Затем можно выполнить локальную установку из этого экземпляра PSGallery.</span><span class="sxs-lookup"><span data-stu-id="a15b7-192">Then do your local install from that PSGallery.</span></span> <span data-ttu-id="a15b7-193">Все это может показаться трудоемким, но на деле это так же просто, как запуск контейнера Docker.</span><span class="sxs-lookup"><span data-stu-id="a15b7-193">This sounds like a lot of work, but this can be as simple as starting a docker container.</span></span> <span data-ttu-id="a15b7-194">Я подробно расскажу о том, как это сделать, в [Использование сервера NuGet для PSRepository][].</span><span class="sxs-lookup"><span data-stu-id="a15b7-194">I cover a way to do that in my post on [Using a NuGet server for a PSRepository][].</span></span>

## <a name="why-binary-modules"></a><span data-ttu-id="a15b7-195">Зачем нужны двоичные модули</span><span class="sxs-lookup"><span data-stu-id="a15b7-195">Why binary modules?</span></span>

<span data-ttu-id="a15b7-196">Я сразу взялся объяснять, как создать двоичный модуль, не сказав, зачем он нужен.</span><span class="sxs-lookup"><span data-stu-id="a15b7-196">I jumped right into how to make a binary module and didn't mention why you want to make one.</span></span> <span data-ttu-id="a15b7-197">Если вы пишете код на C#, то часто лишаетесь возможностей, предоставляемых командлетами и функциями PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a15b7-197">In reality, you are writing C# and give up easy access to PowerShell Cmdlets and functions.</span></span> <span data-ttu-id="a15b7-198">Это основная причина, почему я не использовал двоичные модули раньше.</span><span class="sxs-lookup"><span data-stu-id="a15b7-198">That is the main reason why I have not shifted to binary modules sooner.</span></span>

<span data-ttu-id="a15b7-199">Но если вы создаете модуль, который не зависит от множества других команд PowerShell, преимущество в производительности может оказаться значительным.</span><span class="sxs-lookup"><span data-stu-id="a15b7-199">But if you are creating a module that doesn't depend on a lot of other PowerShell commands, the performance benefit can be significant.</span></span> <span data-ttu-id="a15b7-200">С переходом на C# вы избавляетесь от издержек, связанных с работой PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a15b7-200">By dropping into C#, you get to shed the overhead added by PowerShell.</span></span> <span data-ttu-id="a15b7-201">Оболочка PowerShell оптимизирована для работы администраторов, а не компьютера, и это несколько снижает скорость выполнения кода.</span><span class="sxs-lookup"><span data-stu-id="a15b7-201">PowerShell was optimized for the administrator, not the computer, and that adds a little overhead.</span></span>

<span data-ttu-id="a15b7-202">В нашей среде выполняется один критически важный процесс — обработка большого массива JSON-файлов и хэш-таблиц.</span><span class="sxs-lookup"><span data-stu-id="a15b7-202">At work, we have a critical process that does a lot of work with JSON and Hashtables.</span></span> <span data-ttu-id="a15b7-203">Мы максимально оптимизировали работу PowerShell, но выполнение этого процесса все равно занимало 12 минут.</span><span class="sxs-lookup"><span data-stu-id="a15b7-203">We optimized the PowerShell as much as we could but this process was still running for 12 minutes.</span></span> <span data-ttu-id="a15b7-204">Модуль уже содержал много кода C#, выполняемого PowerShell,</span><span class="sxs-lookup"><span data-stu-id="a15b7-204">The module already contained a lot of C# style PowerShell.</span></span> <span data-ttu-id="a15b7-205">что упростило переход на использование двоичного модуля.</span><span class="sxs-lookup"><span data-stu-id="a15b7-205">This made the conversion to a binary module clean and easy to do.</span></span> <span data-ttu-id="a15b7-206">В результате время выполнения процесса сократилось с 12 до менее 4 минут.</span><span class="sxs-lookup"><span data-stu-id="a15b7-206">Our conversion cut that process down from over 12 minutes to under four minutes.</span></span>

### <a name="hybrid-modules"></a><span data-ttu-id="a15b7-207">Гибридные модули</span><span class="sxs-lookup"><span data-stu-id="a15b7-207">Hybrid modules</span></span>

<span data-ttu-id="a15b7-208">Вы можете сочетать двоичные командлеты с расширенными функциями PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a15b7-208">You can mix binary Cmdlets with PowerShell advanced functions.</span></span> <span data-ttu-id="a15b7-209">Это именно то, что демонстрируется в этом руководстве.</span><span class="sxs-lookup"><span data-stu-id="a15b7-209">That is exactly what I'm doing in this guide.</span></span> <span data-ttu-id="a15b7-210">При этом вы также можете применить все свои знания о модулях скриптов.</span><span class="sxs-lookup"><span data-stu-id="a15b7-210">You can take everything you know about script modules and it all applies the same way.</span></span>
<span data-ttu-id="a15b7-211">Пустой файл `psm1` я здесь создал для того, чтобы вы могли позднее добавить в него другие функции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a15b7-211">The empty `psm1` file that I created today is there just so you can drop in other PowerShell functions later.</span></span>

<span data-ttu-id="a15b7-212">Почти все скомпилированные командлеты, которые мы создали, сначала были функциями PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a15b7-212">Almost all of the compiled cmdlets that we created started out as a PowerShell function first.</span></span> <span data-ttu-id="a15b7-213">Все наши двоичные модули на самом деле являются гибридными модулями.</span><span class="sxs-lookup"><span data-stu-id="a15b7-213">All of our binary modules are really hybrid modules.</span></span>

### <a name="build-scripts"></a><span data-ttu-id="a15b7-214">Скрипты сборки</span><span class="sxs-lookup"><span data-stu-id="a15b7-214">Build scripts</span></span>

<span data-ttu-id="a15b7-215">Со скриптом сборки все просто.</span><span class="sxs-lookup"><span data-stu-id="a15b7-215">I kept the build script simple here.</span></span> <span data-ttu-id="a15b7-216">Я обычно использую большой скрипт `Invoke-Build` как элемент конвейера CI/CD.</span><span class="sxs-lookup"><span data-stu-id="a15b7-216">I generally use a large `Invoke-Build` script as part of my CI/CD pipeline.</span></span> <span data-ttu-id="a15b7-217">Он выполняет много задач, таких как тесты Pester, выполнение PSScriptAnalyzer, управление версиями и публикация в PSGallery.</span><span class="sxs-lookup"><span data-stu-id="a15b7-217">It does more magic like running Pester tests, running PSScriptAnalyzer, managing versioning, and publishing to the PSGallery.</span></span> <span data-ttu-id="a15b7-218">Когда я начал использовать скрипт сборки для модулей, обнаружилось много вещей, которые можно добавить в него.</span><span class="sxs-lookup"><span data-stu-id="a15b7-218">Once I started using a build script for my modules, I was able to find lots of things to add to it.</span></span>

## <a name="final-thoughts"></a><span data-ttu-id="a15b7-219">В заключение</span><span class="sxs-lookup"><span data-stu-id="a15b7-219">Final thoughts</span></span>

<span data-ttu-id="a15b7-220">Двоичные модули легко создавать.</span><span class="sxs-lookup"><span data-stu-id="a15b7-220">Binary modules are easy to create.</span></span> <span data-ttu-id="a15b7-221">Я не рассматривал синтаксис C# для создания командлета, так как в [Пакет SDK для Windows PowerShell][] есть масса документации по нему.</span><span class="sxs-lookup"><span data-stu-id="a15b7-221">I didn't touch on the C# syntax for creating a Cmdlet, but there is plenty of documentation on it in the [Windows PowerShell SDK][].</span></span> <span data-ttu-id="a15b7-222">С модулями определенно стоит поэкспериментировать на начальном этапе изучения C#.</span><span class="sxs-lookup"><span data-stu-id="a15b7-222">It is definitely something worth experimenting with as a stepping stone into more serious C#.</span></span>

<!-- link references -->
[Оригинал статьи]: https://powershellexplained.com/2018-08-04-Powershell-Standard-Library-Binary-Module/
[original version]: https://powershellexplained.com/2018-08-04-Powershell-Standard-Library-Binary-Module/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[Библиотека PowerShell Standard]: https://github.com/PowerShell/PowerShellStandard
[PowerShell Standard Library]: https://github.com/PowerShell/PowerShellStandard
[Создание межплатформенного двоичного модуля]: https://github.com/PowerShell/PowerShell/blob/master/docs/cmdlet-example/command-line-simple-example.md
[Creating a cross-platform binary module]: https://github.com/PowerShell/PowerShell/blob/master/docs/cmdlet-example/command-line-simple-example.md
[Пакет SDK для .NET Core]: https://www.microsoft.com/net/download/core
[dotnet core SDK]: https://www.microsoft.com/net/download/core
[Использование сервера NuGet для PSRepository]: https://powershellexplained.com/2018-03-03-Powershell-Using-a-NuGet-server-for-a-PSRepository/
[Using a NuGet server for a PSRepository]: https://powershellexplained.com/2018-03-03-Powershell-Using-a-NuGet-server-for-a-PSRepository/
[Пакет SDK для Windows PowerShell]: /powershell/scripting/developer/windows-powershell-reference
[Windows PowerShell SDK]: /powershell/scripting/developer/windows-powershell-reference
[Код VS]: https://code.visualstudio.com
[VS Code]: https://code.visualstudio.com
[Пакет NuGet]: https://www.nuget.org/packages/PowerShellStandard.Library/
[nuget package]: https://www.nuget.org/packages/PowerShellStandard.Library/
