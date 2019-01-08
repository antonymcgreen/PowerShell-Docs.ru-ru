---
ms.date: 06/12/2017
contributor: manikb
keywords: коллекция,powershell,командлет,psget
title: Модули с совместимыми выпусками PowerShell
ms.openlocfilehash: bda924393d37ea1596fbf0d813c10cbdea33c218
ms.sourcegitcommit: 548547b2d5fc73e726bb9fec6175d452a351d975
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2018
ms.locfileid: "53655333"
---
# <a name="modules-with-compatible-powershell-editions"></a><span data-ttu-id="2093e-103">Модули с совместимыми выпусками PowerShell</span><span class="sxs-lookup"><span data-stu-id="2093e-103">Modules with compatible PowerShell Editions</span></span>

<span data-ttu-id="2093e-104">Начиная с версии 5.1 доступны различные выпуски среды PowerShell, что означает различные наборы возможностей и совместимость с разными платформами.</span><span class="sxs-lookup"><span data-stu-id="2093e-104">Starting with version 5.1, PowerShell is available in different editions which denote varying feature sets and platform compatibility.</span></span>

- <span data-ttu-id="2093e-105">Desktop Edition На платформе .NET Framework и обеспечивает совместимость со скриптами и модулями, предназначенные для версий PowerShell, выполняющихся в полноценных выпусках Windows, такие как ядро сервера и Windows Desktop.</span><span class="sxs-lookup"><span data-stu-id="2093e-105">**Desktop Edition:** Built on .NET Framework and provides compatibility with scripts and modules targeting versions of PowerShell running on full footprint editions of Windows such as Server Core and Windows Desktop.</span></span>
- <span data-ttu-id="2093e-106">**Выпуск Core:** Опирается на .NET Core и обеспечивает совместимость со скриптами и модулями, предназначенные для версий PowerShell, выполняющихся в сокращенных выпусках Windows, таких как Nano Server и Windows IoT.</span><span class="sxs-lookup"><span data-stu-id="2093e-106">**Core Edition:** Built on .NET Core and provides compatibility with scripts and modules targeting versions of PowerShell running on reduced footprint editions of Windows such as Nano Server and Windows IoT.</span></span>

<span data-ttu-id="2093e-107">Запущенный выпуск PowerShell отображается в свойстве PSEdition параметра `$PSVersionTable`.</span><span class="sxs-lookup"><span data-stu-id="2093e-107">The running edition of PowerShell is shown in the PSEdition property of `$PSVersionTable`.</span></span>

```powershell
$PSVersionTable
```

```output
Name                           Value
----                           -----
PSVersion                      5.1.14300.1000
PSEdition                      Desktop
PSCompatibleVersions           {1.0, 2.0, 3.0, 4.0...}
CLRVersion                     4.0.30319.42000
BuildVersion                   10.0.14300.1000
WSManStackVersion              3.0
PSRemotingProtocolVersion      2.3
SerializationVersion           1.1.0.1
```

## <a name="declaring-compatible-editions"></a><span data-ttu-id="2093e-108">Объявление совместимых выпусков</span><span class="sxs-lookup"><span data-stu-id="2093e-108">Declaring compatible editions</span></span>

<span data-ttu-id="2093e-109">Авторы модулей могут объявить свои модули совместимыми с одним выпуском PowerShell (или несколькими) с помощью ключа манифеста модуля CompatiblePSEditions.</span><span class="sxs-lookup"><span data-stu-id="2093e-109">Module authors can declare their modules to be compatible with one or more PowerShell editions using the CompatiblePSEditions module manifest key.</span></span> <span data-ttu-id="2093e-110">Этот ключ поддерживается только в PowerShell 5.1 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="2093e-110">This key is only supported on PowerShell 5.1 or later.</span></span>

> [!NOTE]
> <span data-ttu-id="2093e-111">После указания манифеста модуля с помощью ключа CompatiblePSEditions манифест невозможно импортировать в более ранние выпуски PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2093e-111">Once a module manifest is specified with the CompatiblePSEditions key, it can not be imported on lower versions of PowerShell.</span></span>

```powershell
New-ModuleManifest -Path .\TestModuleWithEdition.psd1 -CompatiblePSEditions Desktop,Core -PowerShellVersion 5.1
$ModuleInfo = Test-ModuleManifest -Path .\TestModuleWithEdition.psd1
$ModuleInfo.CompatiblePSEditions
```

```output
Desktop
Core
```

```powershell
$ModuleInfo | Get-Member CompatiblePSEditions
```

```output
   TypeName: System.Management.Automation.PSModuleInfo

Name                 MemberType Definition
----                 ---------- ----------
CompatiblePSEditions Property   System.Collections.Generic.IEnumerable[string] CompatiblePSEditions {get;}
```

<span data-ttu-id="2093e-112">При получении списка доступных модулей его можно отфильтровать по выпуску PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2093e-112">When getting a list of available modules, you can filter the list by PowerShell edition.</span></span>

```powershell
Get-Module -ListAvailable -PSEdition Desktop
```

```output
    Directory: C:\Program Files\WindowsPowerShell\Modules


ModuleType Version    Name                                ExportedCommands
---------- -------    ----                                ----------------
Manifest   1.0        ModuleWithPSEditions
```

```powershell
Get-Module -ListAvailable -PSEdition Core | % CompatiblePSEditions
```

```output
Desktop
Core
```

## <a name="targeting-multiple-editions"></a><span data-ttu-id="2093e-113">Использование совместимых выпусков</span><span class="sxs-lookup"><span data-stu-id="2093e-113">Targeting multiple editions</span></span>

<span data-ttu-id="2093e-114">Авторы модулей могут опубликовать один модуль, предназначенный для одного или обоих выпусков PowerShell (Desktop и Core).</span><span class="sxs-lookup"><span data-stu-id="2093e-114">Module authors can publish a single module targeting to either or both PowerShell editions (Desktop and Core).</span></span>

<span data-ttu-id="2093e-115">Один модуль может работать в выпусках Desktop и Core; в таком модуле автор должен указать нужную логику в RootModule или в манифесте модуля с помощью переменной $PSEdition.</span><span class="sxs-lookup"><span data-stu-id="2093e-115">A single module can work on both Desktop and Core editions, in that module author has to add required logic in either RootModule or in the module manifest using $PSEdition variable.</span></span> <span data-ttu-id="2093e-116">Модули могут иметь два набора скомпилированных библиотек DLL, предназначенных для CoreCLR и FullCLR.</span><span class="sxs-lookup"><span data-stu-id="2093e-116">Modules can have two sets of compiled DLLs targeting both CoreCLR and FullCLR.</span></span> <span data-ttu-id="2093e-117">Ниже представлены несколько вариантов упаковки модуля с логикой для загрузки надлежащих библиотек DLL.</span><span class="sxs-lookup"><span data-stu-id="2093e-117">Here are the couple of options to package your module with logic for loading proper dlls.</span></span>

### <a name="option-1-packaging-a-module-for-targeting-multiple-versions-and-multiple-editions-of-powershell"></a><span data-ttu-id="2093e-118">Вариант 1. Упаковка модуля для нескольких версий и нескольких выпусков PowerShell</span><span class="sxs-lookup"><span data-stu-id="2093e-118">Option 1: Packaging a module for targeting multiple versions and multiple editions of PowerShell</span></span>

<span data-ttu-id="2093e-119">Содержимое папки модуля</span><span class="sxs-lookup"><span data-stu-id="2093e-119">Module folder contents</span></span>

- <span data-ttu-id="2093e-120">Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll</span><span class="sxs-lookup"><span data-stu-id="2093e-120">Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll</span></span>
- <span data-ttu-id="2093e-121">Microsoft.Windows.PowerShell.ScriptAnalyzer.dll</span><span class="sxs-lookup"><span data-stu-id="2093e-121">Microsoft.Windows.PowerShell.ScriptAnalyzer.dll</span></span>
- <span data-ttu-id="2093e-122">PSScriptAnalyzer.psd1</span><span class="sxs-lookup"><span data-stu-id="2093e-122">PSScriptAnalyzer.psd1</span></span>
- <span data-ttu-id="2093e-123">PSScriptAnalyzer.psm1</span><span class="sxs-lookup"><span data-stu-id="2093e-123">PSScriptAnalyzer.psm1</span></span>
- <span data-ttu-id="2093e-124">ScriptAnalyzer.format.ps1xml</span><span class="sxs-lookup"><span data-stu-id="2093e-124">ScriptAnalyzer.format.ps1xml</span></span>
- <span data-ttu-id="2093e-125">ScriptAnalyzer.types.ps1xml</span><span class="sxs-lookup"><span data-stu-id="2093e-125">ScriptAnalyzer.types.ps1xml</span></span>
- <span data-ttu-id="2093e-126">coreclr\Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll</span><span class="sxs-lookup"><span data-stu-id="2093e-126">coreclr\Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll</span></span>
- <span data-ttu-id="2093e-127">coreclr\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll</span><span class="sxs-lookup"><span data-stu-id="2093e-127">coreclr\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll</span></span>
- <span data-ttu-id="2093e-128">en-US\about_PSScriptAnalyzer.help.txt</span><span class="sxs-lookup"><span data-stu-id="2093e-128">en-US\about_PSScriptAnalyzer.help.txt</span></span>
- <span data-ttu-id="2093e-129">en-US\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll-Help.xml</span><span class="sxs-lookup"><span data-stu-id="2093e-129">en-US\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll-Help.xml</span></span>
- <span data-ttu-id="2093e-130">PSv3\Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll</span><span class="sxs-lookup"><span data-stu-id="2093e-130">PSv3\Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll</span></span>
- <span data-ttu-id="2093e-131">PSv3\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll</span><span class="sxs-lookup"><span data-stu-id="2093e-131">PSv3\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll</span></span>
- <span data-ttu-id="2093e-132">Settings\CmdletDesign.psd1</span><span class="sxs-lookup"><span data-stu-id="2093e-132">Settings\CmdletDesign.psd1</span></span>
- <span data-ttu-id="2093e-133">Settings\DSC.psd1</span><span class="sxs-lookup"><span data-stu-id="2093e-133">Settings\DSC.psd1</span></span>
- <span data-ttu-id="2093e-134">Settings\ScriptFunctions.psd1</span><span class="sxs-lookup"><span data-stu-id="2093e-134">Settings\ScriptFunctions.psd1</span></span>
- <span data-ttu-id="2093e-135">Settings\ScriptingStyle.psd1</span><span class="sxs-lookup"><span data-stu-id="2093e-135">Settings\ScriptingStyle.psd1</span></span>
- <span data-ttu-id="2093e-136">Settings\ScriptSecurity.psd1</span><span class="sxs-lookup"><span data-stu-id="2093e-136">Settings\ScriptSecurity.psd1</span></span>

<span data-ttu-id="2093e-137">Содержимое файла PSScriptAnalyzer.psd1</span><span class="sxs-lookup"><span data-stu-id="2093e-137">Contents of PSScriptAnalyzer.psd1 file</span></span>

```powershell
@{

# Author of this module
Author = 'Microsoft Corporation'

# Script module or binary module file associated with this manifest.
RootModule = 'PSScriptAnalyzer.psm1'

# Version number of this module.
ModuleVersion = '1.6.1'

# ---
}
```

<span data-ttu-id="2093e-138">Представленная ниже логика загружает необходимые сборки в зависимости от текущего выпуска или версии.</span><span class="sxs-lookup"><span data-stu-id="2093e-138">Below logic loads the required assemblies depending on the current edition or version.</span></span>

<span data-ttu-id="2093e-139">Содержимое файла PSScriptAnalyzer.psm1:</span><span class="sxs-lookup"><span data-stu-id="2093e-139">Contents of PSScriptAnalyzer.psm1 file:</span></span>

```powershell
#
# Script module for module 'PSScriptAnalyzer'
#
Set-StrictMode -Version Latest

# Set up some helper variables to make it easier to work with the module
$PSModule = $ExecutionContext.SessionState.Module
$PSModuleRoot = $PSModule.ModuleBase

# Import the appropriate nested binary module based on the current PowerShell version
$binaryModuleRoot = $PSModuleRoot


if (($PSVersionTable.Keys -contains "PSEdition") -and ($PSVersionTable.PSEdition -ne 'Desktop')) {
    $binaryModuleRoot = Join-Path -Path $PSModuleRoot -ChildPath 'coreclr'
}
else
{
    if ($PSVersionTable.PSVersion -lt [Version]'5.0')
    {
        $binaryModuleRoot = Join-Path -Path $PSModuleRoot -ChildPath 'PSv3'
    }
}

$binaryModulePath = Join-Path -Path $binaryModuleRoot -ChildPath 'Microsoft.Windows.PowerShell.ScriptAnalyzer.dll'
$binaryModule = Import-Module -Name $binaryModulePath -PassThru

# When the module is unloaded, remove the nested binary module that was loaded with it
$PSModule.OnRemove = {
    Remove-Module -ModuleInfo $binaryModule
}
```

### <a name="option-2-use-psedition-variable-in-the-psd1-file-to-load-the-proper-dlls-and-nestedrequired-modules"></a><span data-ttu-id="2093e-140">Вариант 2. Использование переменной $PSEdition в psd1-файл для загрузки надлежащих библиотек DLL и вложенных или необходимых модулей</span><span class="sxs-lookup"><span data-stu-id="2093e-140">Option 2: Use $PSEdition variable in the PSD1 file to load the proper DLLs and Nested/Required modules</span></span>

<span data-ttu-id="2093e-141">В PS 5.1 или более поздней версии в файле манифеста модуля разрешается использовать глобальную переменную $PSEdition.</span><span class="sxs-lookup"><span data-stu-id="2093e-141">In PS 5.1 or newer, $PSEdition global variable is allowed in the module manifest file.</span></span> <span data-ttu-id="2093e-142">С помощью этой переменной автор модуля может указать условные значения в файле манифеста модуля.</span><span class="sxs-lookup"><span data-stu-id="2093e-142">Using this variable, module author can specify the conditional values in the module manifest file.</span></span> <span data-ttu-id="2093e-143">Переменная $PSEdition может указываться в ограниченном языковом режиме или в разделе Data.</span><span class="sxs-lookup"><span data-stu-id="2093e-143">$PSEdition variable can be referenced in restricted language mode or a Data section.</span></span>

> [!NOTE]
> <span data-ttu-id="2093e-144">Манифест модуля невозможно импортировать в более ранние версии PowerShell, указав манифеста с помощью ключа CompatiblePSEditions или после использования в манифесте переменной `$PSEdition`.</span><span class="sxs-lookup"><span data-stu-id="2093e-144">Once a module manifest is specified with the CompatiblePSEditions key or uses `$PSEdition` variable, it can not be imported on lower versions of PowerShell.</span></span>

<span data-ttu-id="2093e-145">Пример файла манифеста модуля с ключом CompatiblePSEditions</span><span class="sxs-lookup"><span data-stu-id="2093e-145">Sample module manifest file with CompatiblePSEditions key</span></span>

```powershell
@{
    # Script module or binary module file associated with this manifest.
    RootModule = if($PSEdition -eq 'Core')
    {
        'coreclr\MyCoreClrRM.dll'
    }
    else # Desktop
    {
        'clr\MyFullClrRM.dll'
    }

    # Supported PSEditions
    CompatiblePSEditions = 'Desktop', 'Core'

    # Modules to import as nested modules of the module specified in RootModule/ModuleToProcess
    NestedModules = if($PSEdition -eq 'Core')
    {
        'coreclr\MyCoreClrNM1.dll',
        'coreclr\MyCoreClrNM2.dll'
    }
    else # Desktop
    {
        'clr\MyFullClrNM1.dll',
        'clr\MyFullClrNM2.dll'
    }
}
```

### <a name="module-contents"></a><span data-ttu-id="2093e-146">Содержимое модуля</span><span class="sxs-lookup"><span data-stu-id="2093e-146">Module contents</span></span>

```powershell
dir -Recurse
```

```output
    Directory: C:\Users\manikb\Documents\WindowsPowerShell\Modules\ModuleWithEditions

Mode           LastWriteTime   Length Name
----           -------------   ------ ----
d-----    7/5/2016   1:37 PM          clr
d-----    7/5/2016   1:36 PM          coreclr
-a----    7/5/2016   1:34 PM     4906 ModuleWithEditions.psd1

    Directory: C:\Users\manikb\Documents\WindowsPowerShell\Modules\ModuleWithEditions\clr

Mode           LastWriteTime    Length Name
----           -------------    ------ ----
-a----    7/5/2016   1:35 PM         0 MyFullClrNM1.dll
-a----    7/5/2016   1:35 PM         0 MyFullClrNM2.dll
-a----    7/5/2016   1:35 PM         0 MyFullClrRM.dl

    Directory: C:\Users\manikb\Documents\WindowsPowerShell\Modules\ModuleWithEditions\coreclr

Mode           LastWriteTime   Length Name
----           -------------   ------ ----
-a----    7/5/2016   1:35 PM        0 MyCoreClrNM1.dll
-a----    7/5/2016   1:35 PM        0 MyCoreClrNM2.dll
-a----    7/5/2016   1:35 PM        0 MyCoreClrRM.dl
```

<span data-ttu-id="2093e-147">Пользователи коллекции PowerShell могут найти список модулей, поддерживаемых в определенной версии PowerShell, с помощью тегов PSEdition_Desktop и PSEdition_Core.</span><span class="sxs-lookup"><span data-stu-id="2093e-147">PowerShell Gallery users can find the list of modules supported on a specific PowerShell Edition using tags PSEdition_Desktop and PSEdition_Core.</span></span>

<span data-ttu-id="2093e-148">Считается, что модули без тегов PSEdition_Desktop и PSEdition_Core работают в выпусках PowerShell Desktop.</span><span class="sxs-lookup"><span data-stu-id="2093e-148">Modules without PSEdition_Desktop and PSEdition_Core tags are considered to work fine on PowerShell Desktop editions.</span></span>

```powershell
# Find modules supported on PowerShell Desktop edition
Find-Module -Tag PSEdition_Desktop

# Find modules supported on PowerShell Core editions
Find-Module -Tag PSEdition_Core
```

## <a name="more-details"></a><span data-ttu-id="2093e-149">Дополнительные подробности</span><span class="sxs-lookup"><span data-stu-id="2093e-149">More details</span></span>

[<span data-ttu-id="2093e-150">Сценарии с PSEditions</span><span class="sxs-lookup"><span data-stu-id="2093e-150">Scripts with PSEditions</span></span>](script-psedition-support.md)

[<span data-ttu-id="2093e-151">Поддержка PSEditions в коллекции PowerShell</span><span class="sxs-lookup"><span data-stu-id="2093e-151">PSEditions support on PowerShellGallery</span></span>](../how-to/finding-packages/searching-by-compatibility.md)

[<span data-ttu-id="2093e-152">Обновление манифеста модулей</span><span class="sxs-lookup"><span data-stu-id="2093e-152">Update module manifest</span></span>](/powershell/module/powershellget/update-modulemanifest)
