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
# <a name="portable-modules"></a><span data-ttu-id="9d1c1-103">Переносимые модулей</span><span class="sxs-lookup"><span data-stu-id="9d1c1-103">Portable Modules</span></span>

<span data-ttu-id="9d1c1-104">Windows PowerShell, написанные для [.NET Framework][] хотя PowerShell Core записывается для [.NET Core][].</span><span class="sxs-lookup"><span data-stu-id="9d1c1-104">Windows PowerShell is written for [.NET Framework][] while PowerShell Core is written for [.NET Core][].</span></span> <span data-ttu-id="9d1c1-105">Переносимые модули — это модули, которые работают в Windows PowerShell и PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="9d1c1-105">Portable modules are modules that work in both Windows PowerShell and PowerShell Core.</span></span> <span data-ttu-id="9d1c1-106">Хотя .NET Framework и .NET Core и высокий уровень совместимости, существуют различия в доступные интерфейсы API.</span><span class="sxs-lookup"><span data-stu-id="9d1c1-106">While .NET Framework and .NET Core are highly compatible, there are differences in the available APIs between the two.</span></span> <span data-ttu-id="9d1c1-107">Существуют различия в API в Windows PowerShell и PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="9d1c1-107">There are also differences in the APIs available in Windows PowerShell and PowerShell Core.</span></span> <span data-ttu-id="9d1c1-108">Модули, предназначен для использования в обеих средах должны учитывать эти различия.</span><span class="sxs-lookup"><span data-stu-id="9d1c1-108">Modules intended to be used in both environments need to be aware of these differences.</span></span>

## <a name="porting-an-existing-module"></a><span data-ttu-id="9d1c1-109">Перенос существующего модуля</span><span class="sxs-lookup"><span data-stu-id="9d1c1-109">Porting an Existing Module</span></span>

### <a name="porting-a-pssnapin"></a><span data-ttu-id="9d1c1-110">Перенос PSSnapIn</span><span class="sxs-lookup"><span data-stu-id="9d1c1-110">Porting a PSSnapIn</span></span>

<span data-ttu-id="9d1c1-111">Оснастки PowerShell (PSSnapIn) не поддерживаются в PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="9d1c1-111">PowerShell SnapIns (PSSnapIn) aren't supported in PowerShell Core.</span></span> <span data-ttu-id="9d1c1-112">Тем не менее это просто преобразовать PSSnapIn модуля PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9d1c1-112">However, it's trivial to convert a PSSnapIn to a PowerShell module.</span></span> <span data-ttu-id="9d1c1-113">Как правило, является регистрационный код PSSnapIn в один исходный файл класса, производного от [PSSnapIn][].</span><span class="sxs-lookup"><span data-stu-id="9d1c1-113">Typically, the PSSnapIn registration code is in a single source file of a class that derives from [PSSnapIn][].</span></span> <span data-ttu-id="9d1c1-114">Удалить этот исходный файл из построения; больше не используется.</span><span class="sxs-lookup"><span data-stu-id="9d1c1-114">Remove this source file from the build; it's no longer needed.</span></span>

<span data-ttu-id="9d1c1-115">Используйте [New-ModuleManifest][] для создания нового манифеста модуля, который устраняет необходимость для кода регистрации PSSnapIn.</span><span class="sxs-lookup"><span data-stu-id="9d1c1-115">Use [New-ModuleManifest][] to create a new module manifest that replaces the need for the PSSnapIn registration code.</span></span> <span data-ttu-id="9d1c1-116">Некоторые значения из PSSnapIn (например, описание) могут использоваться повторно в манифесте модуля.</span><span class="sxs-lookup"><span data-stu-id="9d1c1-116">Some of the values from the PSSnapIn (such as Description) can be reused within the module manifest.</span></span>

<span data-ttu-id="9d1c1-117">`RootModule` Свойства в манифесте модуля должно быть присвоено имя сборки (dll), реализация командлеты.</span><span class="sxs-lookup"><span data-stu-id="9d1c1-117">The `RootModule` property in the module manifest should be set to the name of the assembly (dll) implementing the cmdlets.</span></span>

### <a name="the-net-portability-analyzer-aka-apiport"></a><span data-ttu-id="9d1c1-118">Анализатор переносимости .NET (также называемые APIPort)</span><span class="sxs-lookup"><span data-stu-id="9d1c1-118">The .NET Portability Analyzer (aka APIPort)</span></span>

<span data-ttu-id="9d1c1-119">Порт модули, написанные для Windows PowerShell для работы с PowerShell Core, начните с [анализатор переносимости .NET][].</span><span class="sxs-lookup"><span data-stu-id="9d1c1-119">To port modules written for Windows PowerShell to work with PowerShell Core, start with the [.NET Portability Analyzer][].</span></span> <span data-ttu-id="9d1c1-120">Запустите это средство для скомпилированной сборки для определения API .NET, используемые в модуле совместимы с .NET Framework, .NET Core и других сред выполнения .NET.</span><span class="sxs-lookup"><span data-stu-id="9d1c1-120">Run this tool against your compiled assembly to determine if the .NET APIs used in the module are compatible with .NET Framework, .NET Core, and other .NET runtimes.</span></span> <span data-ttu-id="9d1c1-121">Утилита предлагает альтернативные интерфейсы API, если они существуют.</span><span class="sxs-lookup"><span data-stu-id="9d1c1-121">The tool suggests alternate APIs if they exist.</span></span> <span data-ttu-id="9d1c1-122">В противном случае может потребоваться добавить [проверки времени выполнения][] и ограничить возможности, недоступные в конкретных средах выполнения.</span><span class="sxs-lookup"><span data-stu-id="9d1c1-122">Otherwise, you may need to add [runtime checks][] and restrict capabilities not available in specific runtimes.</span></span>

## <a name="creating-a-new-module"></a><span data-ttu-id="9d1c1-123">Создание нового модуля</span><span class="sxs-lookup"><span data-stu-id="9d1c1-123">Creating a New Module</span></span>

<span data-ttu-id="9d1c1-124">Если создается новый модуль, рекомендуется использовать [ИНТЕРФЕЙС КОМАНДНОЙ СТРОКИ .NET][].</span><span class="sxs-lookup"><span data-stu-id="9d1c1-124">If creating a new module, the recommendation is to use the [.NET CLI][].</span></span>

### <a name="installing-the-powershell-standard-module-template"></a><span data-ttu-id="9d1c1-125">Установка модуля PowerShell Standard шаблона</span><span class="sxs-lookup"><span data-stu-id="9d1c1-125">Installing the PowerShell Standard Module Template</span></span>

<span data-ttu-id="9d1c1-126">После установки интерфейса командной строки .NET, установите библиотеку шаблонов для создания простого модуля PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9d1c1-126">Once the .NET CLI is installed, install a template library to generate a simple PowerShell module.</span></span>
<span data-ttu-id="9d1c1-127">Модуль будут совместимы с Windows PowerShell, PowerShell Core, Windows, Linux и macOS.</span><span class="sxs-lookup"><span data-stu-id="9d1c1-127">The module will be compatible with Windows PowerShell, PowerShell Core, Windows, Linux, and macOS.</span></span>

<span data-ttu-id="9d1c1-128">В следующем примере показано, как установить шаблон:</span><span class="sxs-lookup"><span data-stu-id="9d1c1-128">The following example shows how to install the template:</span></span>

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

### <a name="creating-a-new-module-project"></a><span data-ttu-id="9d1c1-129">Создание проекта модуля</span><span class="sxs-lookup"><span data-stu-id="9d1c1-129">Creating a New Module Project</span></span>

<span data-ttu-id="9d1c1-130">После установки шаблона, можно создать новый проект модуля PowerShell с использованием этого шаблона.</span><span class="sxs-lookup"><span data-stu-id="9d1c1-130">After the template is installed, you can create a new PowerShell module project using that template.</span></span> <span data-ttu-id="9d1c1-131">В этом примере образец модуля называется «myModule».</span><span class="sxs-lookup"><span data-stu-id="9d1c1-131">In this example, the sample module is called 'myModule'.</span></span>

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

### <a name="building-the-module"></a><span data-ttu-id="9d1c1-132">Создание модуля</span><span class="sxs-lookup"><span data-stu-id="9d1c1-132">Building the Module</span></span>

<span data-ttu-id="9d1c1-133">Используйте стандартные команды интерфейса командной строки .NET для сборки проекта.</span><span class="sxs-lookup"><span data-stu-id="9d1c1-133">Use standard .NET CLI commands to build the project.</span></span>

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

### <a name="testing-the-module"></a><span data-ttu-id="9d1c1-134">Проверка модуля</span><span class="sxs-lookup"><span data-stu-id="9d1c1-134">Testing the Module</span></span>

<span data-ttu-id="9d1c1-135">После создания модуля, можно импортировать его и выполнить пример командлета.</span><span class="sxs-lookup"><span data-stu-id="9d1c1-135">After building the module, you can import it and execute the sample cmdlet.</span></span>

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

<span data-ttu-id="9d1c1-136">В следующих разделах подробно некоторые технологии, используемые этим шаблоном.</span><span class="sxs-lookup"><span data-stu-id="9d1c1-136">The following sections describe in detail some of the technologies used by this template.</span></span>

## <a name="net-standard-library"></a><span data-ttu-id="9d1c1-137">Библиотека .NET standard</span><span class="sxs-lookup"><span data-stu-id="9d1c1-137">.NET Standard Library</span></span>

<span data-ttu-id="9d1c1-138">[.NET standard][] представляет собой официальную спецификацию интерфейсов API .NET, которые доступны во всех реализациях .NET.</span><span class="sxs-lookup"><span data-stu-id="9d1c1-138">[.NET Standard][] is a formal specification of .NET APIs that are available in all .NET implementations.</span></span> <span data-ttu-id="9d1c1-139">Управляемый код, предназначенных для .NET Standard работает с версии .NET Framework и .NET Core, которые совместимы с этой версией .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="9d1c1-139">Managed code targeting .NET Standard works with the .NET Framework and .NET Core versions that are compatible with that version of the .NET Standard.</span></span>

> [!NOTE]
> <span data-ttu-id="9d1c1-140">Несмотря на то, что API могут существовать в .NET Standard, реализации API в .NET Core может вызывать исключение `PlatformNotSupportedException` во время выполнения, поэтому для проверки совместимости с Windows PowerShell и PowerShell Core, мы рекомендуем проводить тесты для модуля в обеих средах.</span><span class="sxs-lookup"><span data-stu-id="9d1c1-140">Although an API may exist in .NET Standard, the API implementation in .NET Core may throw a `PlatformNotSupportedException` at runtime, so to verify compatibility with Windows PowerShell and PowerShell Core, the best practice is to run tests for your module within both environments.</span></span>
> <span data-ttu-id="9d1c1-141">Также выполните тесты в Linux и macOS, если модуль должен быть между различными платформами.</span><span class="sxs-lookup"><span data-stu-id="9d1c1-141">Also run tests on Linux and macOS if your module is intended to be cross-platform.</span></span>

<span data-ttu-id="9d1c1-142">Применение .NET Standard гарантирует, что, по мере развития модуль несовместимых API не случайно введение в модуль.</span><span class="sxs-lookup"><span data-stu-id="9d1c1-142">Targeting .NET Standard helps ensure that, as the module evolves, incompatible APIs don't accidentally get introduced into the module.</span></span> <span data-ttu-id="9d1c1-143">Во время компиляции, а не среды выполнения будут обнаружены несовместимости.</span><span class="sxs-lookup"><span data-stu-id="9d1c1-143">Incompatibilities are discovered at compile time instead of runtime.</span></span>

<span data-ttu-id="9d1c1-144">Тем не менее он не требуется для .NET Standard, для модуля для работы с Windows PowerShell и PowerShell Core, до тех пор, пока вы используете совместимые интерфейсы API.</span><span class="sxs-lookup"><span data-stu-id="9d1c1-144">However, it isn't required to target .NET Standard for a module to work with both Windows PowerShell and PowerShell Core, as long as you use compatible APIs.</span></span> <span data-ttu-id="9d1c1-145">Промежуточный язык (IL) совместим между двумя средами выполнения.</span><span class="sxs-lookup"><span data-stu-id="9d1c1-145">The Intermediate Language (IL) is compatible between the two runtimes.</span></span> <span data-ttu-id="9d1c1-146">Можно создавать решения .NET Framework 4.6.1, которая совместима с .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="9d1c1-146">You can target .NET Framework 4.6.1, which is compatible with .NET Standard 2.0.</span></span> <span data-ttu-id="9d1c1-147">Если вы не используете API вне .NET Standard 2.0, затем модуль работает с PowerShell Core 6 без повторной компиляции.</span><span class="sxs-lookup"><span data-stu-id="9d1c1-147">If you don't use APIs outside of .NET Standard 2.0, then your module works with PowerShell Core 6 without recompilation.</span></span>

## <a name="powershell-standard-library"></a><span data-ttu-id="9d1c1-148">PowerShell стандартной библиотеке</span><span class="sxs-lookup"><span data-stu-id="9d1c1-148">PowerShell Standard Library</span></span>

<span data-ttu-id="9d1c1-149">[Стандартный PowerShell][] библиотека — это Формальная спецификация API-интерфейсы PowerShell доступен во всех версиях PowerShell, не меньше версии этого стандарта.</span><span class="sxs-lookup"><span data-stu-id="9d1c1-149">The [PowerShell Standard][] library is a formal specification of PowerShell APIs available in all PowerShell versions greater than or equal to the version of that standard.</span></span>

<span data-ttu-id="9d1c1-150">Например [Стандартный PowerShell 5.1][] является совместимым с Windows PowerShell 5.1 и PowerShell Core 6.0 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="9d1c1-150">For example, [PowerShell Standard 5.1][] is compatible with both Windows PowerShell 5.1 and PowerShell Core 6.0 or newer.</span></span>

<span data-ttu-id="9d1c1-151">Мы рекомендуем компиляции модуля с помощью библиотеки Standard PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9d1c1-151">We recommend you compile your module using PowerShell Standard Library.</span></span> <span data-ttu-id="9d1c1-152">Библиотека гарантирует, что API-интерфейсы будут доступны и реализованных в Windows PowerShell и PowerShell Core 6.</span><span class="sxs-lookup"><span data-stu-id="9d1c1-152">The library ensures the APIs are available and implemented in both Windows PowerShell and PowerShell Core 6.</span></span>
<span data-ttu-id="9d1c1-153">Стандартный PowerShell позволяет всегда пересылает совместимой.</span><span class="sxs-lookup"><span data-stu-id="9d1c1-153">PowerShell Standard is intended to always be forwards-compatible.</span></span> <span data-ttu-id="9d1c1-154">Модуль, созданные с помощью PowerShell стандартные библиотеки 5.1 всегда был совместим с будущими версиями PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9d1c1-154">A module built using PowerShell Standard Library 5.1 will always be compatible with future versions of PowerShell.</span></span>

## <a name="module-manifest"></a><span data-ttu-id="9d1c1-155">Манифест модуля</span><span class="sxs-lookup"><span data-stu-id="9d1c1-155">Module Manifest</span></span>

### <a name="indicating-compatibility-with-windows-powershell-and-powershell-core"></a><span data-ttu-id="9d1c1-156">Указывающее, совместимость с Windows PowerShell и PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="9d1c1-156">Indicating Compatibility With Windows PowerShell and PowerShell Core</span></span>

<span data-ttu-id="9d1c1-157">После проверки работы вашего модуля с помощью Windows PowerShell и PowerShell Core, манифеста модуля следует явно указать совместимости с помощью [CompatiblePSEditions][] свойство.</span><span class="sxs-lookup"><span data-stu-id="9d1c1-157">After validating that your module works with both Windows PowerShell and PowerShell Core, the module manifest should explicitly indicate compatibility by using the [CompatiblePSEditions][] property.</span></span> <span data-ttu-id="9d1c1-158">Значение `Desktop` означает, что модуль совместима с Windows PowerShell, то время как значение из `Core` означает, что модуль является совместимым с PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="9d1c1-158">A value of `Desktop` means that the module is compatible with Windows PowerShell, while a value of `Core` means that the module is compatible with PowerShell Core.</span></span> <span data-ttu-id="9d1c1-159">Включая `Desktop` и `Core` означает, что модуль совместима с Windows PowerShell и PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="9d1c1-159">Including both `Desktop` and `Core` means that the module is compatible with both Windows PowerShell and PowerShell Core.</span></span>

> [!NOTE]
> <span data-ttu-id="9d1c1-160">`Core` не означает, что модуль совместима с Windows, Linux и macOS.</span><span class="sxs-lookup"><span data-stu-id="9d1c1-160">`Core` does not automatically mean that the module is compatible with Windows, Linux, and macOS.</span></span>
> <span data-ttu-id="9d1c1-161">**CompatiblePSEditions** свойство появилось в PowerShell версии 5.</span><span class="sxs-lookup"><span data-stu-id="9d1c1-161">The **CompatiblePSEditions** property was introduced in PowerShell v5.</span></span> <span data-ttu-id="9d1c1-162">Модуль манифесты, использующих **CompatiblePSEditions** свойства не удалось загрузить в версиях до PowerShell версии 5.</span><span class="sxs-lookup"><span data-stu-id="9d1c1-162">Module manifests that use the **CompatiblePSEditions** property fail to load in versions prior to PowerShell v5.</span></span>

### <a name="indicating-os-compatibility"></a><span data-ttu-id="9d1c1-163">Указывающее, совместимость ОС</span><span class="sxs-lookup"><span data-stu-id="9d1c1-163">Indicating OS Compatibility</span></span>

<span data-ttu-id="9d1c1-164">Во-первых проверьте, что модуль работает в Linux и macOS.</span><span class="sxs-lookup"><span data-stu-id="9d1c1-164">First, validate that your module works on Linux and macOS.</span></span> <span data-ttu-id="9d1c1-165">Затем результатами означают совместимость с этими операционными системами в манифесте модуля.</span><span class="sxs-lookup"><span data-stu-id="9d1c1-165">Next, indicate compatibility with those operating systems in the module manifest.</span></span> <span data-ttu-id="9d1c1-166">Это поможет пользователям найти модуль для своей операционной системы, при публикации [Коллекция PowerShell][].</span><span class="sxs-lookup"><span data-stu-id="9d1c1-166">This makes it easier for users to find your module for their operating system when published to the [PowerShell Gallery][].</span></span>

<span data-ttu-id="9d1c1-167">В манифесте модуля `PrivateData` свойство имеет `PSData` подчиненных свойств.</span><span class="sxs-lookup"><span data-stu-id="9d1c1-167">Within the module manifest, the `PrivateData` property has a `PSData` sub-property.</span></span> <span data-ttu-id="9d1c1-168">Необязательный `Tags` свойство `PSData` принимает массив значений, которые отображаются в коллекции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9d1c1-168">The optional `Tags` property of `PSData` takes an array of values that show up in PowerShell Gallery.</span></span> <span data-ttu-id="9d1c1-169">В коллекции PowerShell поддерживает следующие значения совместимости:</span><span class="sxs-lookup"><span data-stu-id="9d1c1-169">The PowerShell Gallery supports the following compatibility values:</span></span>

| <span data-ttu-id="9d1c1-170">Tag</span><span class="sxs-lookup"><span data-stu-id="9d1c1-170">Tag</span></span>               | <span data-ttu-id="9d1c1-171">Описание</span><span class="sxs-lookup"><span data-stu-id="9d1c1-171">Description</span></span>                                |
|-------------------|--------------------------------------------|
| <span data-ttu-id="9d1c1-172">PSEdition_Core</span><span class="sxs-lookup"><span data-stu-id="9d1c1-172">PSEdition_Core</span></span>    | <span data-ttu-id="9d1c1-173">Совместимость с PowerShell Core 6</span><span class="sxs-lookup"><span data-stu-id="9d1c1-173">Compatible with PowerShell Core 6</span></span>          |
| <span data-ttu-id="9d1c1-174">PSEdition_Desktop</span><span class="sxs-lookup"><span data-stu-id="9d1c1-174">PSEdition_Desktop</span></span> | <span data-ttu-id="9d1c1-175">Совместимость с Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9d1c1-175">Compatible with Windows PowerShell</span></span>         |
| <span data-ttu-id="9d1c1-176">Windows</span><span class="sxs-lookup"><span data-stu-id="9d1c1-176">Windows</span></span>           | <span data-ttu-id="9d1c1-177">Совместимость с Windows</span><span class="sxs-lookup"><span data-stu-id="9d1c1-177">Compatible with Windows</span></span>                    |
| <span data-ttu-id="9d1c1-178">Linux</span><span class="sxs-lookup"><span data-stu-id="9d1c1-178">Linux</span></span>             | <span data-ttu-id="9d1c1-179">Совместимость с Linux (не дистрибутиву)</span><span class="sxs-lookup"><span data-stu-id="9d1c1-179">Compatible with Linux (no specific distro)</span></span> |
| <span data-ttu-id="9d1c1-180">macOS</span><span class="sxs-lookup"><span data-stu-id="9d1c1-180">macOS</span></span>             | <span data-ttu-id="9d1c1-181">Совместимый с macOS</span><span class="sxs-lookup"><span data-stu-id="9d1c1-181">Compatible with macOS</span></span>                      |

<span data-ttu-id="9d1c1-182">Пример:</span><span class="sxs-lookup"><span data-stu-id="9d1c1-182">Example:</span></span>

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
[runtime checks]: /dotnet/api/system.runtime.interopservices.runtimeinformation.frameworkdescription#System_Runtime_InteropServices_RuntimeInformation_FrameworkDescription
[ИНТЕРФЕЙС КОМАНДНОЙ СТРОКИ .NET]: /dotnet/core/tools/?tabs=netcore2x
[.NET CLI]: /dotnet/core/tools/?tabs=netcore2x
[.NET Standard]: /dotnet/standard/net-standard
[Стандартный PowerShell]: https://github.com/PowerShell/PowerShellStandard
[PowerShell Standard]: https://github.com/PowerShell/PowerShellStandard
[Стандартный PowerShell 5.1]: https://www.nuget.org/packages/PowerShellStandard.Library/5.1.0
[PowerShell Standard 5.1]: https://www.nuget.org/packages/PowerShellStandard.Library/5.1.0
[Коллекция PowerShell]: https://www.powershellgallery.com
[PowerShell Gallery]: https://www.powershellgallery.com
[Анализатор переносимости .NET]: https://github.com/Microsoft/dotnet-apiport
[.NET Portability Analyzer]: https://github.com/Microsoft/dotnet-apiport
[CompatiblePSEditions]: /powershell/gallery/concepts/module-psedition-support
