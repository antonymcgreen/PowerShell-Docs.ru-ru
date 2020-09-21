---
ms.date: 06/10/2020
contributor: manikb
keywords: коллекция,powershell,командлет,psget
title: Модули с совместимыми выпусками PowerShell
ms.openlocfilehash: 522493714916e9fd21f67a6e7bc2cfb165041807
ms.sourcegitcommit: 4a283fe5419f47102e6c1de7060880a934842ee9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/10/2020
ms.locfileid: "84671416"
---
# <a name="modules-with-compatible-powershell-editions"></a><span data-ttu-id="59cef-103">Модули с совместимыми выпусками PowerShell</span><span class="sxs-lookup"><span data-stu-id="59cef-103">Modules with compatible PowerShell Editions</span></span>

<span data-ttu-id="59cef-104">Начиная с версии 5.1, доступны различные выпуски среды PowerShell, что означает различные наборы возможностей и совместимость с разными платформами.</span><span class="sxs-lookup"><span data-stu-id="59cef-104">Starting with version 5.1, PowerShell is available in different editions, which denote varying feature sets and platform compatibility.</span></span>

- <span data-ttu-id="59cef-105">**Desktop Edition:** этот продукт на основе .NET Framework используется с Windows PowerShell версии 4.0 и ниже, а также с Windows PowerShell 5.1 с большинством выпусков Windows, включая Windows Desktop, Windows Server и Windows Server Core.</span><span class="sxs-lookup"><span data-stu-id="59cef-105">**Desktop Edition:** Built on .NET Framework, applies to Windows PowerShell v4.0 and below as well as Windows PowerShell 5.1 on Windows Desktop, Windows Server, Windows Server Core and most other Windows editions.</span></span>
- <span data-ttu-id="59cef-106">**Core Edition:** этот продукт на основе .NET Core используется с PowerShell Core версии 6.0 и выше, а также с Windows PowerShell 5.1 с облегченными выпусками Windows, включая Windows IoT и Windows Nanoserver.</span><span class="sxs-lookup"><span data-stu-id="59cef-106">**Core Edition:** Built on .NET Core, applies to PowerShell Core 6.0 and above as well as Windows PowerShell 5.1 on reduced footprint Windows Editions such as Windows IoT and Windows Nanoserver.</span></span>

<span data-ttu-id="59cef-107">См. дополнительные сведения о [about_PowerShell_Editions][].</span><span class="sxs-lookup"><span data-stu-id="59cef-107">For more information on PowerShell editions, see [about_PowerShell_Editions][].</span></span>

## <a name="declaring-compatible-editions"></a><span data-ttu-id="59cef-108">Объявление совместимых выпусков</span><span class="sxs-lookup"><span data-stu-id="59cef-108">Declaring compatible editions</span></span>

<span data-ttu-id="59cef-109">Авторы модулей могут объявить свои модули совместимыми с одним выпуском PowerShell (или несколькими) с помощью ключа манифеста модуля `CompatiblePSEditions`.</span><span class="sxs-lookup"><span data-stu-id="59cef-109">Module authors can declare their modules to be compatible with one or more PowerShell editions using the `CompatiblePSEditions` module manifest key.</span></span> <span data-ttu-id="59cef-110">Этот ключ поддерживается только в PowerShell 5.1 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="59cef-110">This key is only supported on PowerShell 5.1 or later.</span></span>

> [!NOTE]
> <span data-ttu-id="59cef-111">Манифест модуля невозможно импортировать в PowerShell 4 и более ранних версий, если он уже указан с помощью ключа `CompatiblePSEditions` или использует переменную `$PSEdition`.</span><span class="sxs-lookup"><span data-stu-id="59cef-111">Once a module manifest is specified with the `CompatiblePSEditions` key or uses the `$PSEdition` variable, it can not be imported on PowerShell v4 or lower.</span></span>

```powershell
New-ModuleManifest -Path .\TestModuleWithEdition.psd1 -CompatiblePSEditions Desktop,Core -PowerShellVersion 5.1
$ModuleInfo = Test-ModuleManifest -Path .\TestModuleWithEdition.psd1
$ModuleInfo.CompatiblePSEditions
```

```Output
Desktop
Core
```

```powershell
$ModuleInfo | Get-Member CompatiblePSEditions
```

```Output
   TypeName: System.Management.Automation.PSModuleInfo

Name                 MemberType Definition
----                 ---------- ----------
CompatiblePSEditions Property   System.Collections.Generic.IEnumerable[string] CompatiblePSEditions {get;}
```

<span data-ttu-id="59cef-112">При получении списка доступных модулей его можно отфильтровать по выпуску PowerShell.</span><span class="sxs-lookup"><span data-stu-id="59cef-112">When getting a list of available modules, you can filter the list by PowerShell edition.</span></span>

```powershell
Get-Module -ListAvailable -PSEdition Desktop
```

```Output
    Directory: C:\Program Files\WindowsPowerShell\Modules

ModuleType Version    Name                                ExportedCommands
---------- -------    ----                                ----------------
Manifest   1.0        ModuleWithPSEditions
```

```powershell
Get-Module -ListAvailable -PSEdition Core | % CompatiblePSEditions
```

```Output
Desktop
Core
```

<span data-ttu-id="59cef-113">Начиная с PowerShell 6, значение `CompatiblePSEditions` используется для определения совместимости модуля при импорте модулей из `$env:windir\System32\WindowsPowerShell\v1.0\Modules`.</span><span class="sxs-lookup"><span data-stu-id="59cef-113">Beginning in PowerShell 6, the `CompatiblePSEditions` value is used to decide if a module is compatible when modules are imported from `$env:windir\System32\WindowsPowerShell\v1.0\Modules`.</span></span>
<span data-ttu-id="59cef-114">Это поведение применимо только к Windows.</span><span class="sxs-lookup"><span data-stu-id="59cef-114">This behavior only applies to Windows.</span></span> <span data-ttu-id="59cef-115">За пределами этого сценария значение используется только в качестве метаданных.</span><span class="sxs-lookup"><span data-stu-id="59cef-115">Outside of this scenario, the value is only used as metadata.</span></span>

## <a name="finding-compatible-modules"></a><span data-ttu-id="59cef-116">Поиск совместимых модулей</span><span class="sxs-lookup"><span data-stu-id="59cef-116">Finding compatible modules</span></span>

<span data-ttu-id="59cef-117">Пользователи коллекции PowerShell могут найти список модулей, поддерживаемых в определенной версии PowerShell, с помощью тегов **PSEdition_Desktop** и **PSEdition_Core**.</span><span class="sxs-lookup"><span data-stu-id="59cef-117">PowerShell Gallery users can find the list of modules supported on a specific PowerShell Edition using tags **PSEdition_Desktop** and **PSEdition_Core**.</span></span>

<span data-ttu-id="59cef-118">Считается, что модули без тегов **PSEdition_Desktop** и **PSEdition_Core** работают в выпусках PowerShell Desktop.</span><span class="sxs-lookup"><span data-stu-id="59cef-118">Modules without **PSEdition_Desktop** and **PSEdition_Core** tags are considered to work fine on PowerShell Desktop editions.</span></span>

```powershell
# Find modules supported on PowerShell Desktop edition
Find-Module -Tag PSEdition_Desktop

# Find modules supported on PowerShell Core editions
Find-Module -Tag PSEdition_Core
```

## <a name="targeting-multiple-editions"></a><span data-ttu-id="59cef-119">Использование совместимых выпусков</span><span class="sxs-lookup"><span data-stu-id="59cef-119">Targeting multiple editions</span></span>

<span data-ttu-id="59cef-120">Авторы модулей могут опубликовать один модуль, предназначенный для одного или обоих выпусков PowerShell (Desktop и Core).</span><span class="sxs-lookup"><span data-stu-id="59cef-120">Module authors can publish a single module targeting to either or both PowerShell editions (Desktop and Core).</span></span>

<span data-ttu-id="59cef-121">Один модуль может работать в выпусках Desktop и Core; в таком модуле автор должен указать нужную логику в RootModule или в манифесте модуля с помощью переменной `$PSEdition`.</span><span class="sxs-lookup"><span data-stu-id="59cef-121">A single module can work on both Desktop and Core editions, in that module author has to add required logic in either RootModule or in the module manifest using `$PSEdition` variable.</span></span> <span data-ttu-id="59cef-122">Модули могут иметь два набора скомпилированных библиотек DLL, предназначенных для **CoreCLR** и **FullCLR**.</span><span class="sxs-lookup"><span data-stu-id="59cef-122">Modules can have two sets of compiled DLLs targeting both **CoreCLR** and **FullCLR**.</span></span> <span data-ttu-id="59cef-123">Ниже приведены варианты упаковки с логикой для загрузки правильных библиотек DLL.</span><span class="sxs-lookup"><span data-stu-id="59cef-123">Here are the packaging options with logic for loading proper DLLs.</span></span>

### <a name="option-1-packaging-a-module-for-targeting-multiple-versions-and-multiple-editions-of-powershell"></a><span data-ttu-id="59cef-124">Вариант 1. Упаковка модуля для нескольких версий и нескольких выпусков PowerShell</span><span class="sxs-lookup"><span data-stu-id="59cef-124">Option 1: Packaging a module for targeting multiple versions and multiple editions of PowerShell</span></span>

<span data-ttu-id="59cef-125">Содержимое папки модуля</span><span class="sxs-lookup"><span data-stu-id="59cef-125">Module folder contents</span></span>

- <span data-ttu-id="59cef-126">Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll</span><span class="sxs-lookup"><span data-stu-id="59cef-126">Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll</span></span>
- <span data-ttu-id="59cef-127">Microsoft.Windows.PowerShell.ScriptAnalyzer.dll</span><span class="sxs-lookup"><span data-stu-id="59cef-127">Microsoft.Windows.PowerShell.ScriptAnalyzer.dll</span></span>
- <span data-ttu-id="59cef-128">PSScriptAnalyzer.psd1</span><span class="sxs-lookup"><span data-stu-id="59cef-128">PSScriptAnalyzer.psd1</span></span>
- <span data-ttu-id="59cef-129">PSScriptAnalyzer.psm1</span><span class="sxs-lookup"><span data-stu-id="59cef-129">PSScriptAnalyzer.psm1</span></span>
- <span data-ttu-id="59cef-130">ScriptAnalyzer.format.ps1xml</span><span class="sxs-lookup"><span data-stu-id="59cef-130">ScriptAnalyzer.format.ps1xml</span></span>
- <span data-ttu-id="59cef-131">ScriptAnalyzer.types.ps1xml</span><span class="sxs-lookup"><span data-stu-id="59cef-131">ScriptAnalyzer.types.ps1xml</span></span>
- <span data-ttu-id="59cef-132">coreclr\Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll</span><span class="sxs-lookup"><span data-stu-id="59cef-132">coreclr\Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll</span></span>
- <span data-ttu-id="59cef-133">coreclr\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll</span><span class="sxs-lookup"><span data-stu-id="59cef-133">coreclr\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll</span></span>
- <span data-ttu-id="59cef-134">en-US\about_PSScriptAnalyzer.help.txt</span><span class="sxs-lookup"><span data-stu-id="59cef-134">en-US\about_PSScriptAnalyzer.help.txt</span></span>
- <span data-ttu-id="59cef-135">en-US\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll-Help.xml</span><span class="sxs-lookup"><span data-stu-id="59cef-135">en-US\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll-Help.xml</span></span>
- <span data-ttu-id="59cef-136">PSv3\Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll</span><span class="sxs-lookup"><span data-stu-id="59cef-136">PSv3\Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll</span></span>
- <span data-ttu-id="59cef-137">PSv3\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll</span><span class="sxs-lookup"><span data-stu-id="59cef-137">PSv3\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll</span></span>
- <span data-ttu-id="59cef-138">Settings\CmdletDesign.psd1</span><span class="sxs-lookup"><span data-stu-id="59cef-138">Settings\CmdletDesign.psd1</span></span>
- <span data-ttu-id="59cef-139">Settings\DSC.psd1</span><span class="sxs-lookup"><span data-stu-id="59cef-139">Settings\DSC.psd1</span></span>
- <span data-ttu-id="59cef-140">Settings\ScriptFunctions.psd1</span><span class="sxs-lookup"><span data-stu-id="59cef-140">Settings\ScriptFunctions.psd1</span></span>
- <span data-ttu-id="59cef-141">Settings\ScriptingStyle.psd1</span><span class="sxs-lookup"><span data-stu-id="59cef-141">Settings\ScriptingStyle.psd1</span></span>
- <span data-ttu-id="59cef-142">Settings\ScriptSecurity.psd1</span><span class="sxs-lookup"><span data-stu-id="59cef-142">Settings\ScriptSecurity.psd1</span></span>

<span data-ttu-id="59cef-143">Содержимое файла `PSScriptAnalyzer.psd1`</span><span class="sxs-lookup"><span data-stu-id="59cef-143">Contents of `PSScriptAnalyzer.psd1` file</span></span>

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

<span data-ttu-id="59cef-144">Представленная ниже логика загружает необходимые сборки в зависимости от текущего выпуска или версии.</span><span class="sxs-lookup"><span data-stu-id="59cef-144">Below logic loads the required assemblies depending on the current edition or version.</span></span>

<span data-ttu-id="59cef-145">Содержимое файла `PSScriptAnalyzer.psm1`:</span><span class="sxs-lookup"><span data-stu-id="59cef-145">Contents of `PSScriptAnalyzer.psm1` file:</span></span>

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

### <a name="option-2-use-psedition-variable-in-the-psd1-file-to-load-the-proper-dlls"></a><span data-ttu-id="59cef-146">Вариант 2. Использование переменной $PSEdition в PSD1-файле для загрузки надлежащих библиотек DLL</span><span class="sxs-lookup"><span data-stu-id="59cef-146">Option 2: Use $PSEdition variable in the PSD1 file to load the proper DLLs</span></span>

<span data-ttu-id="59cef-147">В PS 5.1 или более поздней версии в файле манифеста модуля разрешается использовать глобальную переменную `$PSEdition`.</span><span class="sxs-lookup"><span data-stu-id="59cef-147">In PS 5.1 or newer, `$PSEdition` global variable is allowed in the module manifest file.</span></span> <span data-ttu-id="59cef-148">С помощью этой переменной автор модуля может указать условные значения в файле манифеста модуля.</span><span class="sxs-lookup"><span data-stu-id="59cef-148">Using this variable, module author can specify the conditional values in the module manifest file.</span></span> <span data-ttu-id="59cef-149">Переменная `$PSEdition` может указываться в ограниченном языковом режиме или в разделе Data.</span><span class="sxs-lookup"><span data-stu-id="59cef-149">`$PSEdition` variable can be referenced in restricted language mode or a Data section.</span></span>

<span data-ttu-id="59cef-150">Пример файла манифеста модуля с ключом `CompatiblePSEditions`.</span><span class="sxs-lookup"><span data-stu-id="59cef-150">Sample module manifest file with `CompatiblePSEditions` key.</span></span>

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

<span data-ttu-id="59cef-151">Содержимое модуля</span><span class="sxs-lookup"><span data-stu-id="59cef-151">Module contents</span></span>

- <span data-ttu-id="59cef-152">ModuleWithEditions\ModuleWithEditions.psd1</span><span class="sxs-lookup"><span data-stu-id="59cef-152">ModuleWithEditions\ModuleWithEditions.psd1</span></span>
- <span data-ttu-id="59cef-153">ModuleWithEditions\clr\MyFullClrNM1.dll</span><span class="sxs-lookup"><span data-stu-id="59cef-153">ModuleWithEditions\clr\MyFullClrNM1.dll</span></span>
- <span data-ttu-id="59cef-154">ModuleWithEditions\clr\MyFullClrNM2.dll</span><span class="sxs-lookup"><span data-stu-id="59cef-154">ModuleWithEditions\clr\MyFullClrNM2.dll</span></span>
- <span data-ttu-id="59cef-155">ModuleWithEditions\clr\MyFullClrRM.dll</span><span class="sxs-lookup"><span data-stu-id="59cef-155">ModuleWithEditions\clr\MyFullClrRM.dll</span></span>
- <span data-ttu-id="59cef-156">ModuleWithEditions\coreclr\MyCoreClrNM1.dll</span><span class="sxs-lookup"><span data-stu-id="59cef-156">ModuleWithEditions\coreclr\MyCoreClrNM1.dll</span></span>
- <span data-ttu-id="59cef-157">ModuleWithEditions\coreclr\MyCoreClrNM2.dll</span><span class="sxs-lookup"><span data-stu-id="59cef-157">ModuleWithEditions\coreclr\MyCoreClrNM2.dll</span></span>
- <span data-ttu-id="59cef-158">ModuleWithEditions\coreclr\MyCoreClrRM.dll</span><span class="sxs-lookup"><span data-stu-id="59cef-158">ModuleWithEditions\coreclr\MyCoreClrRM.dll</span></span>

## <a name="more-details"></a><span data-ttu-id="59cef-159">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="59cef-159">More details</span></span>

[<span data-ttu-id="59cef-160">Сценарии с PSEditions</span><span class="sxs-lookup"><span data-stu-id="59cef-160">Scripts with PSEditions</span></span>](script-psedition-support.md)

[<span data-ttu-id="59cef-161">Поддержка PSEditions в коллекции PowerShell</span><span class="sxs-lookup"><span data-stu-id="59cef-161">PSEditions support on PowerShellGallery</span></span>](../how-to/finding-packages/searching-by-compatibility.md)

[<span data-ttu-id="59cef-162">Обновление манифеста модулей</span><span class="sxs-lookup"><span data-stu-id="59cef-162">Update module manifest</span></span>](/powershell/module/powershellget/update-modulemanifest)

<span data-ttu-id="59cef-163">[about_PowerShell_Editions][]</span><span class="sxs-lookup"><span data-stu-id="59cef-163">[about_PowerShell_Editions][]</span></span>

[about_PowerShell_Editions]: /powershell/module/Microsoft.PowerShell.Core/About/about_PowerShell_Editions
