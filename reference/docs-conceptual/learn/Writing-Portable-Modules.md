---
ms.date: 01/10/2020
keywords: powershell,командлет
title: Создание переносимых модулей
ms.openlocfilehash: 124e6efadfd07b8c5214a5c0446b1589f7142388
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "76022242"
---
# <a name="portable-modules"></a><span data-ttu-id="6b1d0-103">Переносимые модули</span><span class="sxs-lookup"><span data-stu-id="6b1d0-103">Portable Modules</span></span>

<span data-ttu-id="6b1d0-104">Средство Windows PowerShell написано для [.NET Framework][], в то время как PowerShell Core написано для [.NET Core][].</span><span class="sxs-lookup"><span data-stu-id="6b1d0-104">Windows PowerShell is written for [.NET Framework][] while PowerShell Core is written for [.NET Core][].</span></span> <span data-ttu-id="6b1d0-105">Переносимые модули — это модули, которые работают как в Windows PowerShell, так и в PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="6b1d0-105">Portable modules are modules that work in both Windows PowerShell and PowerShell Core.</span></span> <span data-ttu-id="6b1d0-106">Хотя .NET Framework и .NET Core обладают высокой совместимостью, между ними есть различия касательно доступных API-интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="6b1d0-106">While .NET Framework and .NET Core are highly compatible, there are differences in the available APIs between the two.</span></span> <span data-ttu-id="6b1d0-107">Существуют также различия в API-интерфейсах, доступных в Windows PowerShell и PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="6b1d0-107">There are also differences in the APIs available in Windows PowerShell and PowerShell Core.</span></span> <span data-ttu-id="6b1d0-108">В модулях, которые предназначены для использования в обеих средах, должны учитываться эти различия.</span><span class="sxs-lookup"><span data-stu-id="6b1d0-108">Modules intended to be used in both environments need to be aware of these differences.</span></span>

## <a name="porting-an-existing-module"></a><span data-ttu-id="6b1d0-109">Перенос существующего модуля</span><span class="sxs-lookup"><span data-stu-id="6b1d0-109">Porting an Existing Module</span></span>

### <a name="porting-a-pssnapin"></a><span data-ttu-id="6b1d0-110">Перенос оснастки PSSnapIn</span><span class="sxs-lookup"><span data-stu-id="6b1d0-110">Porting a PSSnapIn</span></span>

<span data-ttu-id="6b1d0-111">Оснастки PowerShell ([SnapIns](/powershell/scripting/developer/cmdlet/modules-and-snap-ins)) не поддерживаются в PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="6b1d0-111">PowerShell [SnapIns](/powershell/scripting/developer/cmdlet/modules-and-snap-ins) aren't supported in PowerShell Core.</span></span> <span data-ttu-id="6b1d0-112">Тем не менее PSSnapIn можно легко преобразовать в модуль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6b1d0-112">However, it's trivial to convert a PSSnapIn to a PowerShell module.</span></span> <span data-ttu-id="6b1d0-113">Как правило, регистрационный код PSSnapIn находится в одном исходном файле класса, который наследуется от [PSSnapIn][].</span><span class="sxs-lookup"><span data-stu-id="6b1d0-113">Typically, the PSSnapIn registration code is in a single source file of a class that derives from [PSSnapIn][].</span></span>
<span data-ttu-id="6b1d0-114">Удалите этот исходный файл из сборки, так как он больше не нужен.</span><span class="sxs-lookup"><span data-stu-id="6b1d0-114">Remove this source file from the build; it's no longer needed.</span></span>

<span data-ttu-id="6b1d0-115">Чтобы создать манифест модуля, который заменяет необходимость в регистрационном коде PSSnapIn, используйте командлет [New-ModuleManifest][].</span><span class="sxs-lookup"><span data-stu-id="6b1d0-115">Use [New-ModuleManifest][] to create a new module manifest that replaces the need for the PSSnapIn registration code.</span></span> <span data-ttu-id="6b1d0-116">Некоторые значения из **PSSnapIn** (например, **Description**) можно повторно использовать в манифесте модуля.</span><span class="sxs-lookup"><span data-stu-id="6b1d0-116">Some of the values from the **PSSnapIn** (such as **Description**) can be reused within the module manifest.</span></span>

<span data-ttu-id="6b1d0-117">Для свойства **RootModule** в манифесте модуля должно быть указано имя сборки (DLL), реализующей командлеты.</span><span class="sxs-lookup"><span data-stu-id="6b1d0-117">The **RootModule** property in the module manifest should be set to the name of the assembly (dll) implementing the cmdlets.</span></span>

### <a name="the-net-portability-analyzer-aka-apiport"></a><span data-ttu-id="6b1d0-118">Средство .NET Portability Analyzer (оно же APIPort)</span><span class="sxs-lookup"><span data-stu-id="6b1d0-118">The .NET Portability Analyzer (aka APIPort)</span></span>

<span data-ttu-id="6b1d0-119">Чтобы перенести модули, написанные для Windows PowerShell, для работы с PowerShell Core, используйте [.NET Portability Analyzer][].</span><span class="sxs-lookup"><span data-stu-id="6b1d0-119">To port modules written for Windows PowerShell to work with PowerShell Core, start with the [.NET Portability Analyzer][].</span></span> <span data-ttu-id="6b1d0-120">Запустите это средство для вашей скомпилированной сборки, чтобы определить совместимость используемых в модуле интерфейсов API .NET с .NET Framework, .NET Core и другими средами выполнения .NET.</span><span class="sxs-lookup"><span data-stu-id="6b1d0-120">Run this tool against your compiled assembly to determine if the .NET APIs used in the module are compatible with .NET Framework, .NET Core, and other .NET runtimes.</span></span> <span data-ttu-id="6b1d0-121">Средство предлагает альтернативные API-интерфейсы, если они существуют.</span><span class="sxs-lookup"><span data-stu-id="6b1d0-121">The tool suggests alternate APIs if they exist.</span></span> <span data-ttu-id="6b1d0-122">В противном случае вам может потребоваться добавить [Проверки среды выполнения][] и ограничить возможности, недоступные в определенных средах выполнения.</span><span class="sxs-lookup"><span data-stu-id="6b1d0-122">Otherwise, you may need to add [runtime checks][] and restrict capabilities not available in specific runtimes.</span></span>

## <a name="creating-a-new-module"></a><span data-ttu-id="6b1d0-123">Создание модуля</span><span class="sxs-lookup"><span data-stu-id="6b1d0-123">Creating a New Module</span></span>

<span data-ttu-id="6b1d0-124">При создании модуля рекомендуется использовать [Интерфейс командной строки.NET][].</span><span class="sxs-lookup"><span data-stu-id="6b1d0-124">If creating a new module, the recommendation is to use the [.NET CLI][].</span></span>

### <a name="installing-the-powershell-standard-module-template"></a><span data-ttu-id="6b1d0-125">Установка шаблона стандартного модуля PowerShell</span><span class="sxs-lookup"><span data-stu-id="6b1d0-125">Installing the PowerShell Standard Module Template</span></span>

<span data-ttu-id="6b1d0-126">После установки интерфейса командной строки .NET установите библиотеку шаблонов, чтобы создать простой модуль PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6b1d0-126">Once the .NET CLI is installed, install a template library to generate a simple PowerShell module.</span></span>
<span data-ttu-id="6b1d0-127">Модуль будет совместим с Windows PowerShell, PowerShell Core, Windows, Linux и macOS.</span><span class="sxs-lookup"><span data-stu-id="6b1d0-127">The module will be compatible with Windows PowerShell, PowerShell Core, Windows, Linux, and macOS.</span></span>

<span data-ttu-id="6b1d0-128">В следующем примере показана установка шаблона:</span><span class="sxs-lookup"><span data-stu-id="6b1d0-128">The following example shows how to install the template:</span></span>

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

### <a name="creating-a-new-module-project"></a><span data-ttu-id="6b1d0-129">Создание проекта модуля</span><span class="sxs-lookup"><span data-stu-id="6b1d0-129">Creating a New Module Project</span></span>

<span data-ttu-id="6b1d0-130">После установки шаблона можно создать проект модуля PowerShell с использованием этого шаблона.</span><span class="sxs-lookup"><span data-stu-id="6b1d0-130">After the template is installed, you can create a new PowerShell module project using that template.</span></span> <span data-ttu-id="6b1d0-131">У нас пример модуля называется myModule.</span><span class="sxs-lookup"><span data-stu-id="6b1d0-131">In this example, the sample module is called 'myModule'.</span></span>

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

### <a name="building-the-module"></a><span data-ttu-id="6b1d0-132">Создание модуля</span><span class="sxs-lookup"><span data-stu-id="6b1d0-132">Building the Module</span></span>

<span data-ttu-id="6b1d0-133">Используйте стандартные команды интерфейса командной строки .NET для создания проекта.</span><span class="sxs-lookup"><span data-stu-id="6b1d0-133">Use standard .NET CLI commands to build the project.</span></span>

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

### <a name="testing-the-module"></a><span data-ttu-id="6b1d0-134">Тестирование модуля</span><span class="sxs-lookup"><span data-stu-id="6b1d0-134">Testing the Module</span></span>

<span data-ttu-id="6b1d0-135">После создания модуля вы можете импортировать его и выполнить пример командлета.</span><span class="sxs-lookup"><span data-stu-id="6b1d0-135">After building the module, you can import it and execute the sample cmdlet.</span></span>

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

<span data-ttu-id="6b1d0-136">В следующих разделах подробно описаны некоторые технологии, используемые этим шаблоном.</span><span class="sxs-lookup"><span data-stu-id="6b1d0-136">The following sections describe in detail some of the technologies used by this template.</span></span>

## <a name="net-standard-library"></a><span data-ttu-id="6b1d0-137">Библиотека .NET Standard</span><span class="sxs-lookup"><span data-stu-id="6b1d0-137">.NET Standard Library</span></span>

<span data-ttu-id="6b1d0-138">[.NET Standard][] — это формальная спецификация API-интерфейсов .NET, доступных во всех реализациях .NET.</span><span class="sxs-lookup"><span data-stu-id="6b1d0-138">[.NET Standard][] is a formal specification of .NET APIs that are available in all .NET implementations.</span></span> <span data-ttu-id="6b1d0-139">Управляемый код, предназначенный для .NET Standard, работает с версиями .NET Framework и .NET Core, совместимыми с этой версией .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="6b1d0-139">Managed code targeting .NET Standard works with the .NET Framework and .NET Core versions that are compatible with that version of the .NET Standard.</span></span>

> [!NOTE]
> <span data-ttu-id="6b1d0-140">Хотя API-интерфейс может существовать в .NET Standard, реализация API в .NET Core во время выполнения может вызывать исключение `PlatformNotSupportedException`, поэтому для проверки совместимости с Windows PowerShell и PowerShell Core рекомендуется выполнить тестирование вашего модуля в обеих средах.</span><span class="sxs-lookup"><span data-stu-id="6b1d0-140">Although an API may exist in .NET Standard, the API implementation in .NET Core may throw a `PlatformNotSupportedException` at runtime, so to verify compatibility with Windows PowerShell and PowerShell Core, the best practice is to run tests for your module within both environments.</span></span>
> <span data-ttu-id="6b1d0-141">Если ваш модуль должен быть кроссплатформенным, запустите также тестирование в Linux и macOS.</span><span class="sxs-lookup"><span data-stu-id="6b1d0-141">Also run tests on Linux and macOS if your module is intended to be cross-platform.</span></span>

<span data-ttu-id="6b1d0-142">Нацеленность на .NET Standard гарантирует, что по мере развития модуля несовместимые API-интерфейсы не будут случайно введены в модуль.</span><span class="sxs-lookup"><span data-stu-id="6b1d0-142">Targeting .NET Standard helps ensure that, as the module evolves, incompatible APIs don't accidentally get introduced into the module.</span></span> <span data-ttu-id="6b1d0-143">Несовместимости обнаруживаются во время компиляции, а не во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="6b1d0-143">Incompatibilities are discovered at compile time instead of runtime.</span></span>

<span data-ttu-id="6b1d0-144">Однако для работы модуля как с Windows PowerShell, так и с PowerShell Core не требуется указывать платформу .NET Standard как целевую, если используются совместимые API-интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="6b1d0-144">However, it isn't required to target .NET Standard for a module to work with both Windows PowerShell and PowerShell Core, as long as you use compatible APIs.</span></span> <span data-ttu-id="6b1d0-145">Промежуточный язык (IL) совместим с двумя средами выполнения.</span><span class="sxs-lookup"><span data-stu-id="6b1d0-145">The Intermediate Language (IL) is compatible between the two runtimes.</span></span> <span data-ttu-id="6b1d0-146">Вы можете указать как целевую версию .NET Framework 4.6.1, которая совместима с .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="6b1d0-146">You can target .NET Framework 4.6.1, which is compatible with .NET Standard 2.0.</span></span> <span data-ttu-id="6b1d0-147">Если вы не используете API-интерфейсы за пределами. NET Standard 2.0, тогда ваш модуль будет работать с PowerShell Core 6 без повторной компиляции.</span><span class="sxs-lookup"><span data-stu-id="6b1d0-147">If you don't use APIs outside of .NET Standard 2.0, then your module works with PowerShell Core 6 without recompilation.</span></span>

## <a name="powershell-standard-library"></a><span data-ttu-id="6b1d0-148">Библиотека PowerShell Standard</span><span class="sxs-lookup"><span data-stu-id="6b1d0-148">PowerShell Standard Library</span></span>

<span data-ttu-id="6b1d0-149">[PowerShell Standard][] — это формальная спецификация API-интерфейсов PowerShell, доступная во всех версиях PowerShell, которые больше версии этого стандарта или соответствуют ей.</span><span class="sxs-lookup"><span data-stu-id="6b1d0-149">The [PowerShell Standard][] library is a formal specification of PowerShell APIs available in all PowerShell versions greater than or equal to the version of that standard.</span></span>

<span data-ttu-id="6b1d0-150">Например, [PowerShell Standard 5.1][] совместима как с Windows PowerShell 5.1, так и с PowerShell Core 6.0 или более поздней версией.</span><span class="sxs-lookup"><span data-stu-id="6b1d0-150">For example, [PowerShell Standard 5.1][] is compatible with both Windows PowerShell 5.1 and PowerShell Core 6.0 or newer.</span></span>

<span data-ttu-id="6b1d0-151">Мы советуем вам скомпилировать свой модуль с помощью библиотеки PowerShell Standard.</span><span class="sxs-lookup"><span data-stu-id="6b1d0-151">We recommend you compile your module using PowerShell Standard Library.</span></span> <span data-ttu-id="6b1d0-152">Библиотека гарантирует, что API-интерфейсы будут доступны и реализованы как в Windows PowerShell, так и в PowerShell Core 6.</span><span class="sxs-lookup"><span data-stu-id="6b1d0-152">The library ensures the APIs are available and implemented in both Windows PowerShell and PowerShell Core 6.</span></span>
<span data-ttu-id="6b1d0-153">PowerShell Standard предназначена для постоянной совместимости с новыми версиями.</span><span class="sxs-lookup"><span data-stu-id="6b1d0-153">PowerShell Standard is intended to always be forwards-compatible.</span></span> <span data-ttu-id="6b1d0-154">Модуль, созданный с использованием библиотеки PowerShell Standard 5.1, всегда будет совместим с будущими версиями PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6b1d0-154">A module built using PowerShell Standard Library 5.1 will always be compatible with future versions of PowerShell.</span></span>

## <a name="module-manifest"></a><span data-ttu-id="6b1d0-155">Манифест модуля</span><span class="sxs-lookup"><span data-stu-id="6b1d0-155">Module Manifest</span></span>

### <a name="indicating-compatibility-with-windows-powershell-and-powershell-core"></a><span data-ttu-id="6b1d0-156">Указание на совместимость с Windows PowerShell и PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="6b1d0-156">Indicating Compatibility With Windows PowerShell and PowerShell Core</span></span>

<span data-ttu-id="6b1d0-157">После проверки работы модуля с Windows PowerShell и с PowerShell Core манифест модуля должен явно указывать совместимость с помощью свойства [CompatiblePSEditions][].</span><span class="sxs-lookup"><span data-stu-id="6b1d0-157">After validating that your module works with both Windows PowerShell and PowerShell Core, the module manifest should explicitly indicate compatibility by using the [CompatiblePSEditions][] property.</span></span> <span data-ttu-id="6b1d0-158">Значение `Desktop` означает, что модуль совместим с Windows PowerShell, а значение `Core` указывает на совместимость с PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="6b1d0-158">A value of `Desktop` means that the module is compatible with Windows PowerShell, while a value of `Core` means that the module is compatible with PowerShell Core.</span></span> <span data-ttu-id="6b1d0-159">Наличие обоих значений (`Desktop` и `Core`) означает, что модуль совместим как с Windows PowerShell, так и с PowerShell Core.</span><span class="sxs-lookup"><span data-stu-id="6b1d0-159">Including both `Desktop` and `Core` means that the module is compatible with both Windows PowerShell and PowerShell Core.</span></span>

> [!NOTE]
> <span data-ttu-id="6b1d0-160">`Core` необязательно означает, что модуль совместим с Windows, Linux и macOS.</span><span class="sxs-lookup"><span data-stu-id="6b1d0-160">`Core` does not automatically mean that the module is compatible with Windows, Linux, and macOS.</span></span>
> <span data-ttu-id="6b1d0-161">Свойство **CompatiblePSEditions** впервые появилось в PowerShell версии 5.</span><span class="sxs-lookup"><span data-stu-id="6b1d0-161">The **CompatiblePSEditions** property was introduced in PowerShell v5.</span></span> <span data-ttu-id="6b1d0-162">Манифесты модуля, которые используют свойство **CompatiblePSEditions**, не будут загружаться в версиях, предшествующих PowerShell версии 5.</span><span class="sxs-lookup"><span data-stu-id="6b1d0-162">Module manifests that use the **CompatiblePSEditions** property fail to load in versions prior to PowerShell v5.</span></span>

### <a name="indicating-os-compatibility"></a><span data-ttu-id="6b1d0-163">Указание на совместимость с ОС</span><span class="sxs-lookup"><span data-stu-id="6b1d0-163">Indicating OS Compatibility</span></span>

<span data-ttu-id="6b1d0-164">Сначала убедитесь, что ваш модуль работает в Linux и macOS.</span><span class="sxs-lookup"><span data-stu-id="6b1d0-164">First, validate that your module works on Linux and macOS.</span></span> <span data-ttu-id="6b1d0-165">Далее укажите совместимость с этими операционными системами в манифесте модуля.</span><span class="sxs-lookup"><span data-stu-id="6b1d0-165">Next, indicate compatibility with those operating systems in the module manifest.</span></span> <span data-ttu-id="6b1d0-166">В результате пользователям будет проще искать ваш модуль для требуемых операционных систем, когда он будет опубликован в [Коллекция PowerShell][].</span><span class="sxs-lookup"><span data-stu-id="6b1d0-166">This makes it easier for users to find your module for their operating system when published to the [PowerShell Gallery][].</span></span>

<span data-ttu-id="6b1d0-167">В манифесте модуля у свойства `PrivateData` есть вложенное свойство `PSData`.</span><span class="sxs-lookup"><span data-stu-id="6b1d0-167">Within the module manifest, the `PrivateData` property has a `PSData` sub-property.</span></span> <span data-ttu-id="6b1d0-168">Необязательное свойство `Tags` раздела `PSData` принимает массив значений, которые отображаются в коллекции PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6b1d0-168">The optional `Tags` property of `PSData` takes an array of values that show up in PowerShell Gallery.</span></span> <span data-ttu-id="6b1d0-169">Коллекция PowerShell поддерживает следующие значения совместимости:</span><span class="sxs-lookup"><span data-stu-id="6b1d0-169">The PowerShell Gallery supports the following compatibility values:</span></span>

| <span data-ttu-id="6b1d0-170">Тег</span><span class="sxs-lookup"><span data-stu-id="6b1d0-170">Tag</span></span>               | <span data-ttu-id="6b1d0-171">Description</span><span class="sxs-lookup"><span data-stu-id="6b1d0-171">Description</span></span>                                |
|-------------------|--------------------------------------------|
| <span data-ttu-id="6b1d0-172">PSEdition_Core</span><span class="sxs-lookup"><span data-stu-id="6b1d0-172">PSEdition_Core</span></span>    | <span data-ttu-id="6b1d0-173">Совместимость с PowerShell Core 6</span><span class="sxs-lookup"><span data-stu-id="6b1d0-173">Compatible with PowerShell Core 6</span></span>          |
| <span data-ttu-id="6b1d0-174">PSEdition_Desktop</span><span class="sxs-lookup"><span data-stu-id="6b1d0-174">PSEdition_Desktop</span></span> | <span data-ttu-id="6b1d0-175">Совместимость с Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6b1d0-175">Compatible with Windows PowerShell</span></span>         |
| <span data-ttu-id="6b1d0-176">Windows</span><span class="sxs-lookup"><span data-stu-id="6b1d0-176">Windows</span></span>           | <span data-ttu-id="6b1d0-177">Совместимость с Windows</span><span class="sxs-lookup"><span data-stu-id="6b1d0-177">Compatible with Windows</span></span>                    |
| <span data-ttu-id="6b1d0-178">Linux</span><span class="sxs-lookup"><span data-stu-id="6b1d0-178">Linux</span></span>             | <span data-ttu-id="6b1d0-179">Совместимость с Linux (любой дистрибутив)</span><span class="sxs-lookup"><span data-stu-id="6b1d0-179">Compatible with Linux (no specific distro)</span></span> |
| <span data-ttu-id="6b1d0-180">macOS</span><span class="sxs-lookup"><span data-stu-id="6b1d0-180">macOS</span></span>             | <span data-ttu-id="6b1d0-181">Совместимость с macOS</span><span class="sxs-lookup"><span data-stu-id="6b1d0-181">Compatible with macOS</span></span>                      |

<span data-ttu-id="6b1d0-182">Пример</span><span class="sxs-lookup"><span data-stu-id="6b1d0-182">Example:</span></span>

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

## <a name="dependency-on-native-libraries"></a><span data-ttu-id="6b1d0-183">Зависимость от собственных библиотек</span><span class="sxs-lookup"><span data-stu-id="6b1d0-183">Dependency on Native Libraries</span></span>

<span data-ttu-id="6b1d0-184">Модули, предназначенные для использования в разных операционных системах или архитектурах процессоров, могут зависеть от управляемой библиотеки, которая в свою очередь зависит от некоторых собственных библиотек.</span><span class="sxs-lookup"><span data-stu-id="6b1d0-184">Modules intended for use across different operating systems or processor architectures may depend on a managed library that itself depends on some native libraries.</span></span>

<span data-ttu-id="6b1d0-185">До выпуска PowerShell 7 нужно было применять пользовательский код для загрузки соответствующей собственной библиотеки, чтобы управляемая библиотека могла найти ее.</span><span class="sxs-lookup"><span data-stu-id="6b1d0-185">Prior to PowerShell 7, one would have to have custom code to load the appropriate native dll so that the managed library can find it correctly.</span></span>

<span data-ttu-id="6b1d0-186">Но в PowerShell 7 поиск собственных двоичных файлов для загрузки выполняется во вложенных папках в расположении управляемой библиотеки в соответствии с нотацией для [Каталог идентификаторов сред выполнения в .NET][].</span><span class="sxs-lookup"><span data-stu-id="6b1d0-186">With PowerShell 7, native binaries to load are searched in sub-folders within the managed library's location following a subset of the [.NET RID Catalog][] notation.</span></span>

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
[runtime checks]: /dotnet/api/system.runtime.interopservices.runtimeinformation.frameworkdescription#System_Runtime_InteropServices_RuntimeInformation_FrameworkDescription
[Интерфейс командной строки.NET]: /dotnet/core/tools/?tabs=netcore2x
[.NET CLI]: /dotnet/core/tools/?tabs=netcore2x
[.NET Standard]: /dotnet/standard/net-standard
[PowerShell Standard]: https://github.com/PowerShell/PowerShellStandard
[PowerShell Standard 5.1]: https://www.nuget.org/packages/PowerShellStandard.Library/5.1.0
[PowerShell Standard 5.1]: https://www.nuget.org/packages/PowerShellStandard.Library/5.1.0
[Коллекция PowerShell]: https://www.powershellgallery.com
[PowerShell Gallery]: https://www.powershellgallery.com
[.NET Portability Analyzer]: https://github.com/Microsoft/dotnet-apiport
[CompatiblePSEditions]: /powershell/scripting/gallery/concepts/module-psedition-support
[Каталог идентификаторов сред выполнения в .NET]: https://docs.microsoft.com/dotnet/core/rid-catalog
[.NET RID Catalog]: https://docs.microsoft.com/dotnet/core/rid-catalog
