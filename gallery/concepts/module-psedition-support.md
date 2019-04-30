---
ms.date: 03/28/2019
contributor: manikb
keywords: коллекция,powershell,командлет,psget
title: Модули с совместимыми выпусками PowerShell
ms.openlocfilehash: 425588c168a4f864fdc0c52aa53cfd748b80dc98
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62084731"
---
# <a name="modules-with-compatible-powershell-editions"></a>Модули с совместимыми выпусками PowerShell

Начиная с версии 5.1 доступны различные выпуски среды PowerShell, что означает различные наборы возможностей и совместимость с разными платформами.

- **Desktop Edition:** этот продукт на основе .NET Framework используется с Windows PowerShell версии 4.0 и ниже, а также с Windows PowerShell 5.1 с большинством выпусков Windows, включая Windows Desktop, Windows Server и Windows Server Core.
- **Core Edition:** этот продукт на основе .NET Core используется с PowerShell Core версии 6.0 и выше, а также с Windows PowerShell 5.1 с облегченными выпусками Windows, включая Windows IoT и Windows Nanoserver.

См. дополнительные сведения о [about_PowerShell_Editions][].

## <a name="declaring-compatible-editions"></a>Объявление совместимых выпусков

Авторы модулей могут объявить свои модули совместимыми с одним выпуском PowerShell (или несколькими) с помощью ключа манифеста модуля CompatiblePSEditions. Этот ключ поддерживается только в PowerShell 5.1 или более поздней версии.

> [!NOTE]
> Когда манифест модуля будет определен с помощью ключа CompatiblePSEditions, манифест нельзя будет импортировать в PowerShell версии 4 и ниже.

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

При получении списка доступных модулей его можно отфильтровать по выпуску PowerShell.

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

## <a name="targeting-multiple-editions"></a>Использование совместимых выпусков

Авторы модулей могут опубликовать один модуль, предназначенный для одного или обоих выпусков PowerShell (Desktop и Core).

Один модуль может работать в выпусках Desktop и Core; в таком модуле автор должен указать нужную логику в RootModule или в манифесте модуля с помощью переменной $PSEdition. Модули могут иметь два набора скомпилированных библиотек DLL, предназначенных для CoreCLR и FullCLR. Ниже представлены несколько вариантов упаковки модуля с логикой для загрузки надлежащих библиотек DLL.

### <a name="option-1-packaging-a-module-for-targeting-multiple-versions-and-multiple-editions-of-powershell"></a>Вариант 1. Упаковка модуля для нескольких версий и нескольких выпусков PowerShell

Содержимое папки модуля

- Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll
- Microsoft.Windows.PowerShell.ScriptAnalyzer.dll
- PSScriptAnalyzer.psd1
- PSScriptAnalyzer.psm1
- ScriptAnalyzer.format.ps1xml
- ScriptAnalyzer.types.ps1xml
- coreclr\Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll
- coreclr\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll
- en-US\about_PSScriptAnalyzer.help.txt
- en-US\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll-Help.xml
- PSv3\Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll
- PSv3\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll
- Settings\CmdletDesign.psd1
- Settings\DSC.psd1
- Settings\ScriptFunctions.psd1
- Settings\ScriptingStyle.psd1
- Settings\ScriptSecurity.psd1

Содержимое файла PSScriptAnalyzer.psd1

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

Представленная ниже логика загружает необходимые сборки в зависимости от текущего выпуска или версии.

Содержимое файла PSScriptAnalyzer.psm1:

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

### <a name="option-2-use-psedition-variable-in-the-psd1-file-to-load-the-proper-dlls-and-nestedrequired-modules"></a>Вариант 2. Использование переменной $PSEdition в PSD1-файле для загрузки надлежащих библиотек DLL и вложенных или необходимых модулей

В PS 5.1 или более поздней версии в файле манифеста модуля разрешается использовать глобальную переменную $PSEdition. С помощью этой переменной автор модуля может указать условные значения в файле манифеста модуля. Переменная $PSEdition может указываться в ограниченном языковом режиме или в разделе Data.

> [!NOTE]
> Манифест модуля невозможно импортировать в более ранние версии PowerShell, указав манифеста с помощью ключа CompatiblePSEditions или после использования в манифесте переменной `$PSEdition`.

Пример файла манифеста модуля с ключом CompatiblePSEditions

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

### <a name="module-contents"></a>Содержимое модуля

```powershell
dir -Recurse
```

```Output
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

Пользователи коллекции PowerShell могут найти список модулей, поддерживаемых в определенной версии PowerShell, с помощью тегов PSEdition_Desktop и PSEdition_Core.

Считается, что модули без тегов PSEdition_Desktop и PSEdition_Core работают в выпусках PowerShell Desktop.

```powershell
# Find modules supported on PowerShell Desktop edition
Find-Module -Tag PSEdition_Desktop

# Find modules supported on PowerShell Core editions
Find-Module -Tag PSEdition_Core
```

## <a name="more-details"></a>Дополнительные подробности

[Сценарии с PSEditions](script-psedition-support.md)

[Поддержка PSEditions в коллекции PowerShell](../how-to/finding-packages/searching-by-compatibility.md)

[Обновление манифеста модулей](/powershell/module/powershellget/update-modulemanifest)

[about_PowerShell_Editions][]

[about_PowerShell_Editions]: /powershell/module/Microsoft.PowerShell.Core/About/about_PowerShell_Editions
