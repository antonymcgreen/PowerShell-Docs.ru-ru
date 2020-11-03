---
description: Различные выпуски PowerShell выполняются в разных базовых средах выполнения.
Locale: en-US
ms.date: 03/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_powershell_editions?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PowerShell_Editions
ms.openlocfilehash: 63ee3fffb4d7594920fa7052aecee99aa01ddc7d
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231662"
---
# <a name="about-powershell-editions"></a><span data-ttu-id="17756-103">О выпусках PowerShell</span><span class="sxs-lookup"><span data-stu-id="17756-103">About PowerShell Editions</span></span>

## <a name="short-description"></a><span data-ttu-id="17756-104">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="17756-104">Short Description</span></span>
<span data-ttu-id="17756-105">Различные выпуски PowerShell выполняются в разных базовых средах выполнения.</span><span class="sxs-lookup"><span data-stu-id="17756-105">Different editions of PowerShell run on different underlying runtimes.</span></span>

## <a name="long-description"></a><span data-ttu-id="17756-106">Полное описание</span><span class="sxs-lookup"><span data-stu-id="17756-106">Long Description</span></span>

<span data-ttu-id="17756-107">В PowerShell 5,1 существует несколько *выпусков* PowerShell, которые выполняются в другой среде выполнения .NET.</span><span class="sxs-lookup"><span data-stu-id="17756-107">From PowerShell 5.1, there are multiple *editions* of PowerShell that each run on a different .NET runtime.</span></span> <span data-ttu-id="17756-108">В PowerShell 6,2 существует два выпуска PowerShell:</span><span class="sxs-lookup"><span data-stu-id="17756-108">As of PowerShell 6.2 there are two editions of PowerShell:</span></span>

- <span data-ttu-id="17756-109">**Рабочий стол** , работающий на .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="17756-109">**Desktop** , which runs on .NET Framework.</span></span> <span data-ttu-id="17756-110">PowerShell 4 и ниже, а также PowerShell 5,1 в полнофункциональных выпусках Windows, таких как Windows Desktop, Windows Server, Windows Server Core и большинство других операционных систем Windows, являются настольными выпусками.</span><span class="sxs-lookup"><span data-stu-id="17756-110">PowerShell 4 and below, as well as PowerShell 5.1 on full-featured Windows editions like Windows Desktop, Windows Server, Windows Server Core and most other Windows operating systems are Desktop edition.</span></span>
  <span data-ttu-id="17756-111">Это исходный выпуск PowerShell.</span><span class="sxs-lookup"><span data-stu-id="17756-111">This is the original PowerShell edition.</span></span>
- <span data-ttu-id="17756-112">**Ядро** , работающее на .NET Core.</span><span class="sxs-lookup"><span data-stu-id="17756-112">**Core** , which runs on .NET Core.</span></span> <span data-ttu-id="17756-113">PowerShell 6,0 и более поздних версий, а также PowerShell 5,1 в некоторых уменьшенных выпусках Windows, таких как Windows Nano Server и Windows IoT, где .NET Framework недоступна.</span><span class="sxs-lookup"><span data-stu-id="17756-113">PowerShell 6.0 and above, as well as PowerShell 5.1 on some reduced-footprint Windows editions such as Windows Nano Server and Windows IoT where .NET Framework is unavailable.</span></span>

<span data-ttu-id="17756-114">Поскольку выпуск PowerShell соответствует среде выполнения .NET, он является основным индикатором совместимости .NET API и модуля PowerShell. Некоторые API-интерфейсы .NET, типы или методы недоступны в обеих средах выполнения .NET, и это влияет на сценарии PowerShell и модули, зависящие от них.</span><span class="sxs-lookup"><span data-stu-id="17756-114">Because the edition of PowerShell corresponds to its .NET runtime, it is the primary indicator of .NET API and PowerShell module compatibility; some .NET APIs, types or methods are not available in both .NET runtimes and this affects PowerShell scripts and modules that depend on them.</span></span>

## <a name="the-psedition-automatic-variable"></a><span data-ttu-id="17756-115">`$PSEdition`Автоматическая переменная</span><span class="sxs-lookup"><span data-stu-id="17756-115">The `$PSEdition` automatic variable</span></span>

<span data-ttu-id="17756-116">В PowerShell 5,1 и более поздних версиях можно узнать, какой выпуск вы используете с `$PSEdition` автоматической переменной:</span><span class="sxs-lookup"><span data-stu-id="17756-116">In PowerShell 5.1 and above, you can find out what edition you are running with the `$PSEdition` automatic variable:</span></span>

```powershell
$PSEdition
```

```Output
Core
```

<span data-ttu-id="17756-117">В PowerShell 4 и ниже эта переменная не существует.</span><span class="sxs-lookup"><span data-stu-id="17756-117">In PowerShell 4 and below, this variable does not exist.</span></span> <span data-ttu-id="17756-118">`$PSEdition` значение null должно рассматриваться так же, как и при наличии значения `Desktop` .</span><span class="sxs-lookup"><span data-stu-id="17756-118">`$PSEdition` being null should be treated as the same as having the value `Desktop`.</span></span>

### <a name="edition-in-psversiontable"></a><span data-ttu-id="17756-119">Выпуск в `$PSVersionTable`</span><span class="sxs-lookup"><span data-stu-id="17756-119">Edition in `$PSVersionTable`</span></span>

<span data-ttu-id="17756-120">`$PSVersionTable`Автоматическая переменная также содержит сведения о выпуске в PowerShell 5,1 и более поздних версиях:</span><span class="sxs-lookup"><span data-stu-id="17756-120">The `$PSVersionTable` automatic variable also has edition information in PowerShell 5.1 and above:</span></span>

```powershell
$PSVersionTable
```

```Output
Name                           Value
----                           -----
PSVersion                      6.2.0-rc.1
PSEdition                      Core           # <-- Edition information
GitCommitId                    6.2.0-rc.1
OS                             Microsoft Windows 10.0.18865
Platform                       Win32NT
PSCompatibleVersions           {1.0, 2.0, 3.0, 4.0...}
PSRemotingProtocolVersion      2.3
SerializationVersion           1.1.0.1
WSManStackVersion              3.0
```

<span data-ttu-id="17756-121">`PSEdition`Поле будет иметь то же значение, что и `$PSEdition` Автоматическая переменная.</span><span class="sxs-lookup"><span data-stu-id="17756-121">The `PSEdition` field will have the same value as the `$PSEdition` automatic variable.</span></span>

## <a name="the-compatiblepseditions-module-manifest-field"></a><span data-ttu-id="17756-122">`CompatiblePSEditions`Поле манифеста модуля</span><span class="sxs-lookup"><span data-stu-id="17756-122">The `CompatiblePSEditions` module manifest field</span></span>

<span data-ttu-id="17756-123">Модули PowerShell могут объявлять, какие выпуски PowerShell совместимы с, используя `CompatiblePSEditions` поле манифеста модуля.</span><span class="sxs-lookup"><span data-stu-id="17756-123">PowerShell modules can declare what editions of PowerShell they are compatible with using the `CompatiblePSEditions` field of the module manifest.</span></span>

<span data-ttu-id="17756-124">Например, манифест модуля, объявляющий совместимость с и с `Desktop` `Core` выпусками PowerShell:</span><span class="sxs-lookup"><span data-stu-id="17756-124">For example, a module manifest declaring compatibility with both `Desktop` and `Core` editions of PowerShell:</span></span>

```powershell
@{
    ModuleVersion = '1.0'
    FunctionsToExport = @('Test-MyModule')
    CompatiblePSEditions = @('Desktop', 'Core')
}
```

<span data-ttu-id="17756-125">Пример манифеста модуля только с `Desktop` совместимостью:</span><span class="sxs-lookup"><span data-stu-id="17756-125">An example of a module manifest with only `Desktop` compatibility:</span></span>

```powershell
@{
    ModuleVersion = '1.0'
    FunctionsToExport = @('Test-MyModule')
    CompatiblePSEditions = @('Desktop')
}
```

<span data-ttu-id="17756-126">Пропуск `CompatiblePSEditions` поля из манифеста модуля приведет к тому же результату, что и установка `Desktop` , так как модули, созданные до этого поля, были неявно написаны для этого выпуска.</span><span class="sxs-lookup"><span data-stu-id="17756-126">Omitting the `CompatiblePSEditions` field from a module manifest will have the same effect as setting it to `Desktop`, since modules created before this field was introduced were implicitly written for this edition.</span></span>

<span data-ttu-id="17756-127">Для модулей, не поставляемых в составе Windows (т. е. модулей, которые вы пишете или устанавливаете из коллекции), это поле является информационным. PowerShell не изменяет поведение на основе `CompatiblePSEditions` поля, но предоставляет его `PSModuleInfo` для объекта (возвращаемого `Get-Module` ) для собственной логики:</span><span class="sxs-lookup"><span data-stu-id="17756-127">For modules not shipped as part of Windows (i.e. modules you write or install from the gallery), this field is informational only; PowerShell does not change behavior based on the `CompatiblePSEditions` field, but does expose it on the `PSModuleInfo` object (returned by `Get-Module`) for your own logic:</span></span>

```powershell
New-ModuleManifest -Path .\TestModuleWithEdition.psd1 -CompatiblePSEditions Desktop,Core -PowerShellVersion '5.1'
$ModuleInfo = Test-ModuleManifest -Path .\TestModuleWithEdition.psd1
$ModuleInfo.CompatiblePSEditions
```

```Output
Desktop
Core
```

> [!NOTE]
> <span data-ttu-id="17756-128">`CompatiblePSEditions`Поле Module совместимо только с PowerShell 5,1 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="17756-128">The `CompatiblePSEditions` module field is only compatible with PowerShell 5.1 and above.</span></span>
> <span data-ttu-id="17756-129">Включение этого поля приведет к тому, что модуль будет несовместим с PowerShell 4 и ниже.</span><span class="sxs-lookup"><span data-stu-id="17756-129">Including this field will cause a module to be incompatible with PowerShell 4 and below.</span></span>
> <span data-ttu-id="17756-130">Поскольку поле является исключительно информационным, его можно спокойно опустить в последующих версиях PowerShell.</span><span class="sxs-lookup"><span data-stu-id="17756-130">Since the field is purely informational, it can be safely omitted in later PowerShell versions.</span></span>

<span data-ttu-id="17756-131">В PowerShell 6,1 `Get-Module -ListAvailable` модуль форматирования был обновлен для просмотра совместимости каждого модуля с выпуском:</span><span class="sxs-lookup"><span data-stu-id="17756-131">In PowerShell 6.1, `Get-Module -ListAvailable` has had its formatter updated to display the edition-compatibility of each module:</span></span>

```PowerShell
Get-Module -ListAvailable
```

```Output

    Directory: C:\Users\me\Documents\PowerShell\Modules

ModuleType Version    Name                                PSEdition ExportedCommands
---------- -------    ----                                --------- ----------------
Script     1.4.0      Az                                  Core,Desk
Script     1.3.1      Az.Accounts                         Core,Desk {Disable-AzDataCollection, Disable-AzContextAutosave, E...
Script     1.0.1      Az.Aks                              Core,Desk {Get-AzAks, New-AzAks, Remove-AzAks, Import-AzAksCreden...

...

Script     4.4.0      Pester                              Desk      {Describe, Context, It, Should...}
Script     1.18.0     PSScriptAnalyzer                    Desk      {Get-ScriptAnalyzerRule, Invoke-ScriptAnalyzer, Invoke-...
Script     1.0.0      WindowsCompatibility                Core      {Initialize-WinSession, Add-WinFunction, Invoke-WinComm...

```

## <a name="edition-compatibility-for-modules-that-ship-as-part-of-windows"></a><span data-ttu-id="17756-132">Совместимость выпусков для модулей, поставляемых в составе Windows</span><span class="sxs-lookup"><span data-stu-id="17756-132">Edition-compatibility for modules that ship as part of Windows</span></span>

<span data-ttu-id="17756-133">Для модулей, входящих в состав Windows (или устанавливаемых в составе роли или компонента), PowerShell 6,1 и выше обрабатывают поле по- `CompatiblePSEditions` разному.</span><span class="sxs-lookup"><span data-stu-id="17756-133">For modules that come as part of Windows (or are installed as part of a role or feature), PowerShell 6.1 and above treat the `CompatiblePSEditions` field differently.</span></span> <span data-ttu-id="17756-134">Такие модули находятся в каталоге системных модулей Windows PowerShell ( `%windir%\System\WindowsPowerShell\v1.0\Modules` ).</span><span class="sxs-lookup"><span data-stu-id="17756-134">Such modules are found in the Windows PowerShell system modules directory (`%windir%\System\WindowsPowerShell\v1.0\Modules`).</span></span>

<span data-ttu-id="17756-135">Для модулей, загруженных из этого каталога или найденных в этом каталоге, в PowerShell 6,1 и более поздних версий используется `CompatiblePSEditions` поле, чтобы определить, будет ли модуль совместимым с текущим сеансом и работать соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="17756-135">For modules loaded from or found in this directory, PowerShell 6.1 and above uses the `CompatiblePSEditions` field to determine whether the module will be compatible with the current session and behaves accordingly.</span></span>

<span data-ttu-id="17756-136">Если `Import-Module` используется, модуль без `Core` `CompatiblePSEditions` импорта не будет импортирован, и отобразится сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="17756-136">When `Import-Module` is used, a module without `Core` in `CompatiblePSEditions` will not be imported and an error will be displayed:</span></span>

```powershell
Import-Module BitsTransfer
```

```Output
Import-Module : Module 'C:\WINDOWS\system32\WindowsPowerShell\v1.0\Modules\BitsTransfer\BitsTransfer.psd1' does not support current PowerShell edition 'Core'. Its supported editions are 'Desktop'. Use 'Import-Module -SkipEditionCheck' to ignore the compatibility of this module.
At line:1 char:1
+ Import-Module BitsTransfer
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : ResourceUnavailable: (C:\WINDOWS\system32\u2026r\BitsTransfer.psd1:String) [Import-Module], InvalidOperationException
+ FullyQualifiedErrorId : Modules_PSEditionNotSupported,Microsoft.PowerShell.Commands.ImportModuleCommand
```

<span data-ttu-id="17756-137">Когда `Get-Module -ListAvailable` используется, модули без `Core` в `CompatiblePSEditions` не будут отображаться:</span><span class="sxs-lookup"><span data-stu-id="17756-137">When `Get-Module -ListAvailable` is used, modules without `Core` in `CompatiblePSEditions` will not be displayed:</span></span>

```powershell
Get-Module -ListAvailable BitsTransfer
```

```Output
# No output
```

<span data-ttu-id="17756-138">В обоих случаях `-SkipEditionCheck` параметр switch можно использовать для переопределения этого поведения:</span><span class="sxs-lookup"><span data-stu-id="17756-138">In both cases, the `-SkipEditionCheck` switch parameter can be used to override this behavior:</span></span>

```powershell
Get-Module -ListAvailable -SkipEditionCheck BitsTransfer
```

```Output

    Directory: C:\WINDOWS\system32\WindowsPowerShell\v1.0\Modules

ModuleType Version    Name                                PSEdition ExportedCommands
---------- -------    ----                                --------- ----------------
Manifest   2.0.0.0    BitsTransfer                        Desk      {Add-BitsFile, Complete-BitsTransfer, Get-BitsTransfer,...

```

> [!WARNING]
> <span data-ttu-id="17756-139">`Import-Module -SkipEditionCheck` может показаться успешным для модуля, но использование этого модуля вызывает риск возникновения несовместимости позже; При первоначальной загрузке модуля команда может впоследствии вызвать несовместимый API и завершиться неудачно.</span><span class="sxs-lookup"><span data-stu-id="17756-139">`Import-Module -SkipEditionCheck` may appear to succeed for a module, but using that module runs the risk of encountering an incompatibility later on; while loading the module initially succeeds, a command may later call an incompatible API and fail spontaneously.</span></span>

## <a name="authoring-powershell-modules-for-edition-cross-compatibility"></a><span data-ttu-id="17756-140">Создание перекрестной совместимости для модулей PowerShell</span><span class="sxs-lookup"><span data-stu-id="17756-140">Authoring PowerShell modules for edition cross-compatibility</span></span>

<span data-ttu-id="17756-141">При написании модуля PowerShell, предназначенного для `Desktop` и `Core` выпусков PowerShell, существуют вещи, которые можно выполнить для обеспечения совместимости между выпусками.</span><span class="sxs-lookup"><span data-stu-id="17756-141">When writing a PowerShell module to target both `Desktop` and `Core` editions of PowerShell, there are things you can do to ensure cross-edition compatibility.</span></span>

<span data-ttu-id="17756-142">Единственным верным способом подтверждения и регулярной проверки совместимости является написание тестов для скрипта или модуля и их запуск во всех версиях и выпусках PowerShell, для которых требуется совместимость с.</span><span class="sxs-lookup"><span data-stu-id="17756-142">The only true way to confirm and continually validate compatibility however is to write tests for your script or module and run them on all versions and editions of PowerShell you need compatibility with.</span></span> <span data-ttu-id="17756-143">Рекомендуемая платформа тестирования для этого — [Pester][].</span><span class="sxs-lookup"><span data-stu-id="17756-143">A recommended testing framework for this is [Pester][].</span></span>

### <a name="powershell-script"></a><span data-ttu-id="17756-144">Сценарий PowerShell</span><span class="sxs-lookup"><span data-stu-id="17756-144">PowerShell script</span></span>

<span data-ttu-id="17756-145">В качестве языка PowerShell работает одинаково в разных выпусках. Это используемые командлеты, модули и API-интерфейсы .NET, которые зависят от совместимости выпуска.</span><span class="sxs-lookup"><span data-stu-id="17756-145">As a language, PowerShell works the same between editions; it is the cmdlets, modules and .NET APIs you use that are affected by edition compatibility.</span></span>

<span data-ttu-id="17756-146">Как правило, скрипты, работающие в PowerShell 6,1 и выше, будут работать с Windows PowerShell 5,1, но есть некоторые исключения.</span><span class="sxs-lookup"><span data-stu-id="17756-146">Generally, scripts that work in PowerShell 6.1 and above will work with Windows PowerShell 5.1, but there are some exceptions.</span></span>

<span data-ttu-id="17756-147">Модуль версии 1.18.0 [PSScriptAnalyzer][] имеет такие правила [`PSUseCompatibleCommands`][] , как и [`PSUseCompatibleTypes`][] , которые способны обнаруживать потенциально несовместимое использование команд и API-интерфейсов .NET в сценариях PowerShell.</span><span class="sxs-lookup"><span data-stu-id="17756-147">Version 1.18.0 [PSScriptAnalyzer][] module has rules like [`PSUseCompatibleCommands`][] and [`PSUseCompatibleTypes`][] that are able to detect possibly incompatible usage of commands and .NET APIs in PowerShell scripts.</span></span>

### <a name="net-assemblies"></a><span data-ttu-id="17756-148">Сборки .NET</span><span class="sxs-lookup"><span data-stu-id="17756-148">.NET assemblies</span></span>

<span data-ttu-id="17756-149">При написании двоичного модуля или модуля, включающего сборки .NET (DLL), созданные на основе исходного кода, следует компилироваться с [.NET Standard][] и [PowerShell Standard][] для проверки совместимости во время компиляции для СОВМЕСТИМОСТИ .NET и PowerShell API.</span><span class="sxs-lookup"><span data-stu-id="17756-149">If you are writing a binary module or a module that incorporates .NET assemblies (DLLs) generated from source code, you should compile against [.NET Standard][] and [PowerShell Standard][] for compile-time compatibility validation of .NET and PowerShell API compatibility.</span></span>

<span data-ttu-id="17756-150">Хотя эти библиотеки могут проверять некоторую совместимость во время компиляции, они не смогут перехватывать возможные различия в поведении между выпусками.</span><span class="sxs-lookup"><span data-stu-id="17756-150">Although these libraries are able to check some compatibility at compile time, they won't be able to catch possible behavioral differences between editions.</span></span> <span data-ttu-id="17756-151">Для этого все еще необходимо писать тесты.</span><span class="sxs-lookup"><span data-stu-id="17756-151">For this you must still write tests.</span></span>

## <a name="see-also"></a><span data-ttu-id="17756-152">См. также статью</span><span class="sxs-lookup"><span data-stu-id="17756-152">See also</span></span>

- [<span data-ttu-id="17756-153">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="17756-153">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)
- [<span data-ttu-id="17756-154">Import-Module</span><span class="sxs-lookup"><span data-stu-id="17756-154">Import-Module</span></span>](xref:Microsoft.PowerShell.Core.Import-Module)
- [<span data-ttu-id="17756-155">Get-Module</span><span class="sxs-lookup"><span data-stu-id="17756-155">Get-Module</span></span>](xref:Microsoft.PowerShell.Core.Get-Module)
- [<span data-ttu-id="17756-156">Модули с совместимыми выпусками PowerShell</span><span class="sxs-lookup"><span data-stu-id="17756-156">Modules with compatible PowerShell Editions</span></span>](/powershell/scripting/gallery/concepts/module-psedition-support)

[Pester]: https://github.com/pester/Pester/wiki/Pester
[PSScriptAnalyzer]: https://github.com/PowerShell/PSScriptAnalyzer
["Псусекомпатиблекоммандс"]: https://github.com/PowerShell/PSScriptAnalyzer/blob/master/RuleDocumentation/UseCompatibleCommands.md
[`PSUseCompatibleCommands`]: https://github.com/PowerShell/PSScriptAnalyzer/blob/master/RuleDocumentation/UseCompatibleCommands.md
["Псусекомпатиблетипес"]: https://github.com/PowerShell/PSScriptAnalyzer/blob/master/RuleDocumentation/UseCompatibleTypes.md
[`PSUseCompatibleTypes`]: https://github.com/PowerShell/PSScriptAnalyzer/blob/master/RuleDocumentation/UseCompatibleTypes.md
[.NET Standard]: /dotnet/standard/net-standard
[PowerShell Standard]: https://devblogs.microsoft.com/powershell/powershell-standard-library-build-single-module-that-works-across-windows-powershell-and-powershell-core/
