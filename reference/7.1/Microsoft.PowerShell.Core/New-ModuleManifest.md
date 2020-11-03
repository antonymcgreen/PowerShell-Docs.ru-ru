---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-modulemanifest?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-ModuleManifest
ms.openlocfilehash: caf67f951beb054e9bedb46d010fe1a5d8db7ab8
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229402"
---
# <span data-ttu-id="d61fa-103">New-ModuleManifest</span><span class="sxs-lookup"><span data-stu-id="d61fa-103">New-ModuleManifest</span></span>

## <span data-ttu-id="d61fa-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="d61fa-104">SYNOPSIS</span></span>
<span data-ttu-id="d61fa-105">Создает новый манифест модуля.</span><span class="sxs-lookup"><span data-stu-id="d61fa-105">Creates a new module manifest.</span></span>

## <span data-ttu-id="d61fa-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d61fa-106">SYNTAX</span></span>

### <span data-ttu-id="d61fa-107">Все</span><span class="sxs-lookup"><span data-stu-id="d61fa-107">All</span></span>

```
New-ModuleManifest [-Path] <String> [-NestedModules <Object[]>] [-Guid <Guid>] [-Author <String>]
 [-CompanyName <String>] [-Copyright <String>] [-RootModule <String>] [-ModuleVersion <Version>]
 [-Description <String>] [-ProcessorArchitecture <ProcessorArchitecture>]
 [-PowerShellVersion <Version>] [-CLRVersion <Version>] [-DotNetFrameworkVersion <Version>]
 [-PowerShellHostName <String>] [-PowerShellHostVersion <Version>] [-RequiredModules <Object[]>]
 [-TypesToProcess <String[]>] [-FormatsToProcess <String[]>] [-ScriptsToProcess <String[]>]
 [-RequiredAssemblies <String[]>] [-FileList <String[]>] [-ModuleList <Object[]>]
 [-FunctionsToExport <String[]>] [-AliasesToExport <String[]>] [-VariablesToExport <String[]>]
 [-CmdletsToExport <String[]>] [-DscResourcesToExport <String[]>] [-CompatiblePSEditions <String[]>]
 [-PrivateData <Object>] [-Tags <String[]>] [-ProjectUri <Uri>] [-LicenseUri <Uri>] [-IconUri <Uri>]
 [-ReleaseNotes <String>] [-Prerelease <String>] [-RequireLicenseAcceptance]
 [-ExternalModuleDependencies <String[]>] [-HelpInfoUri <String>] [-PassThru]
 [-DefaultCommandPrefix <String>] [-WhatIf] [-Confirm]  [<CommonParameters>]
```

## <span data-ttu-id="d61fa-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d61fa-108">DESCRIPTION</span></span>

<span data-ttu-id="d61fa-109">`New-ModuleManifest`Командлет создает новый файл манифеста модуля ( `.psd1` ), заполняет его значения и сохраняет файл манифеста по указанному пути.</span><span class="sxs-lookup"><span data-stu-id="d61fa-109">The `New-ModuleManifest` cmdlet creates a new module manifest (`.psd1`) file, populates its values, and saves the manifest file in the specified path.</span></span>

<span data-ttu-id="d61fa-110">Авторы модулей могут использовать этот командлет для создания манифестов для своих модулей.</span><span class="sxs-lookup"><span data-stu-id="d61fa-110">Module authors can use this cmdlet to create a manifest for their module.</span></span> <span data-ttu-id="d61fa-111">Манифест модуля — это `.psd1` файл, содержащий хэш-таблицу.</span><span class="sxs-lookup"><span data-stu-id="d61fa-111">A module manifest is a `.psd1` file that contains a hash table.</span></span> <span data-ttu-id="d61fa-112">Ключи и значения хэш-таблицы описывают содержимое и атрибуты модуля, определяют требуемые компоненты и задают способ обработки компонентов.</span><span class="sxs-lookup"><span data-stu-id="d61fa-112">The keys and values in the hash table describe the contents and attributes of the module, define the prerequisites, and determine how the components are processed.</span></span> <span data-ttu-id="d61fa-113">Для модуля манифесты не требуются.</span><span class="sxs-lookup"><span data-stu-id="d61fa-113">Manifests aren't required for a module.</span></span>

<span data-ttu-id="d61fa-114">`New-ModuleManifest` создает манифест, который содержит все часто используемые ключи манифеста, поэтому вы можете использовать выходные данные по умолчанию в качестве шаблона манифеста.</span><span class="sxs-lookup"><span data-stu-id="d61fa-114">`New-ModuleManifest` creates a manifest that includes all the commonly used manifest keys, so you can use the default output as a manifest template.</span></span> <span data-ttu-id="d61fa-115">Чтобы добавить или изменить значения или добавить ключи модуля, которые не добавляются с помощью этого командлета, откройте полученный файл в текстовом редакторе.</span><span class="sxs-lookup"><span data-stu-id="d61fa-115">To add or change values, or to add module keys that this cmdlet doesn't add, open the resulting file in a text editor.</span></span>

<span data-ttu-id="d61fa-116">Каждый параметр, за исключением **path** и **PassThru** , создает ключ манифеста модуля и его значение.</span><span class="sxs-lookup"><span data-stu-id="d61fa-116">Each parameter, except for **Path** and **PassThru** , creates a module manifest key and its value.</span></span>
<span data-ttu-id="d61fa-117">Обязательным в манифесте модуля является только ключ **ModuleVersion** .</span><span class="sxs-lookup"><span data-stu-id="d61fa-117">In a module manifest, only the **ModuleVersion** key is required.</span></span> <span data-ttu-id="d61fa-118">Если параметр не указан в описании параметра, то `New-ModuleManifest` создает строку комментария для связанного значения, которое не оказывает никакого влияния.</span><span class="sxs-lookup"><span data-stu-id="d61fa-118">Unless specified in the parameter description, if you omit a parameter from the command, `New-ModuleManifest` creates a comment string for the associated value that has no effect.</span></span>

<span data-ttu-id="d61fa-119">В PowerShell 2,0 `New-ModuleManifest` запрашивает значения часто используемых параметров, которые не указаны в команде, а также необходимые значения параметров.</span><span class="sxs-lookup"><span data-stu-id="d61fa-119">In PowerShell 2.0, `New-ModuleManifest` prompts you for the values of commonly used parameters that aren't specified in the command, in addition to required parameter values.</span></span> <span data-ttu-id="d61fa-120">Начиная с PowerShell 3,0, `New-ModuleManifest` запрос запрашивается только в том случае, если требуемые значения параметров не указаны.</span><span class="sxs-lookup"><span data-stu-id="d61fa-120">Beginning in PowerShell 3.0, `New-ModuleManifest` prompts only when required parameter values aren't specified.</span></span>

<span data-ttu-id="d61fa-121">Если вы планируете опубликовать модуль в коллекция PowerShell, манифест должен содержать значения для определенных свойств.</span><span class="sxs-lookup"><span data-stu-id="d61fa-121">If you are planning to publish your module in the PowerShell Gallery, the manifest must contain values for certain properties.</span></span> <span data-ttu-id="d61fa-122">Дополнительные сведения см. в разделе [необходимые метаданные для элементов, опубликованных в коллекция PowerShell](/powershell/scripting/gallery/how-to/publishing-packages/publishing-a-package#required-metadata-for-items-published-to-the-powershell-gallery) в документации по коллекции.</span><span class="sxs-lookup"><span data-stu-id="d61fa-122">For more information, see [Required metadata for items published to the PowerShell Gallery](/powershell/scripting/gallery/how-to/publishing-packages/publishing-a-package#required-metadata-for-items-published-to-the-powershell-gallery) in the Gallery documentation.</span></span>

## <span data-ttu-id="d61fa-123">Примеры</span><span class="sxs-lookup"><span data-stu-id="d61fa-123">EXAMPLES</span></span>

### <span data-ttu-id="d61fa-124">Пример 1. Создание нового манифеста модуля</span><span class="sxs-lookup"><span data-stu-id="d61fa-124">Example 1 - Create a new module manifest</span></span>

<span data-ttu-id="d61fa-125">В этом примере создается новый манифест модуля в файле, указанном параметром **path** .</span><span class="sxs-lookup"><span data-stu-id="d61fa-125">This example creates a new module manifest in the file that is specified by the **Path** parameter.</span></span>
<span data-ttu-id="d61fa-126">Параметр **PassThru** отправляет выходные данные в конвейер и в файл.</span><span class="sxs-lookup"><span data-stu-id="d61fa-126">The **PassThru** parameter sends the output to the pipeline and to the file.</span></span>

<span data-ttu-id="d61fa-127">Выходные данные содержат значения всех ключей в манифесте по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d61fa-127">The output shows the default values of all keys in the manifest.</span></span>

```powershell
New-ModuleManifest -Path C:\ps-test\Test-Module\Test-Module.psd1 -PassThru
```

```Output
#
# Module manifest for module 'Test-Module'
#
# Generated by: ContosoAdmin
#
# Generated on: 7/12/2019
#

@{

# Script module or binary module file associated with this manifest.
# RootModule = ''

# Version number of this module.
ModuleVersion = '0.0.1'

# Supported PSEditions
# CompatiblePSEditions = @()

# ID used to uniquely identify this module
GUID = 'e1826c6e-c420-4eef-9ac8-185e3669ca6a'

# Author of this module
Author = 'ContosoAdmin'

# Company or vendor of this module
CompanyName = 'Unknown'

# Copyright statement for this module
Copyright = '(c) ContosoAdmin. All rights reserved.'

# Description of the functionality provided by this module
# Description = ''

# Minimum version of the PowerShell engine required by this module
# PowerShellVersion = ''

# Name of the PowerShell host required by this module
# PowerShellHostName = ''

# Minimum version of the PowerShell host required by this module
# PowerShellHostVersion = ''

# Minimum version of Microsoft .NET Framework required by this module. This prerequisite is valid for the PowerShell Desktop edition only.
# DotNetFrameworkVersion = ''

# Minimum version of the common language runtime (CLR) required by this module. This prerequisite is valid for the PowerShell Desktop edition only.
# CLRVersion = ''

# Processor architecture (None, X86, Amd64) required by this module
# ProcessorArchitecture = ''

# Modules that must be imported into the global environment prior to importing this module
# RequiredModules = @()

# Assemblies that must be loaded prior to importing this module
# RequiredAssemblies = @()

# Script files (.ps1) that are run in the caller's environment prior to importing this module.
# ScriptsToProcess = @()

# Type files (.ps1xml) to be loaded when importing this module
# TypesToProcess = @()

# Format files (.ps1xml) to be loaded when importing this module
# FormatsToProcess = @()

# Modules to import as nested modules of the module specified in RootModule/ModuleToProcess
# NestedModules = @()

# Functions to export from this module, for best performance, do not use wildcards and do not delete the entry, use an empty array if there are no functions to export.
FunctionsToExport = @()

# Cmdlets to export from this module, for best performance, do not use wildcards and do not delete the entry, use an empty array if there are no cmdlets to export.
CmdletsToExport = @()

# Variables to export from this module
VariablesToExport = '*'

# Aliases to export from this module, for best performance, do not use wildcards and do not delete the entry, use an empty array if there are no aliases to export.
AliasesToExport = @()

# DSC resources to export from this module
# DscResourcesToExport = @()

# List of all modules packaged with this module
# ModuleList = @()

# List of all files packaged with this module
# FileList = @()

# Private data to pass to the module specified in RootModule/ModuleToProcess. This may also contain a PSData hashtable with additional module metadata used by PowerShell.
PrivateData = @{

    PSData = @{

        # Tags applied to this module. These help with module discovery in online galleries.
        # Tags = @()

        # A URL to the license for this module.
        # LicenseUri = ''

        # A URL to the main website for this project.
        # ProjectUri = ''

        # A URL to an icon representing this module.
        # IconUri = ''

        # ReleaseNotes of this module
        # ReleaseNotes = ''

        # Prerelease string of this module
        # Prerelease = ''

        # Flag to indicate whether the module requires explicit user acceptance for install/update/save
        # RequireLicenseAcceptance = $false

        # External dependent modules of this module
        # ExternalModuleDependencies = @()

    } # End of PSData hashtable

} # End of PrivateData hashtable

# HelpInfo URI of this module
# HelpInfoURI = ''

# Default prefix for commands exported from this module. Override the default prefix using Import-Module -Prefix.
# DefaultCommandPrefix = ''

}
```

### <span data-ttu-id="d61fa-128">Пример 2. Создание нового манифеста с предварительно заполненными параметрами</span><span class="sxs-lookup"><span data-stu-id="d61fa-128">Example 2 - Create a new manifest with some prepopulated settings</span></span>

<span data-ttu-id="d61fa-129">В этом примере создается новый манифест модуля.</span><span class="sxs-lookup"><span data-stu-id="d61fa-129">This example creates a new module manifest.</span></span> <span data-ttu-id="d61fa-130">Команда включает параметры **PowerShellVersion** и **AliasesToExport** , позволяющие добавить значения в соответствующие ключи манифеста.</span><span class="sxs-lookup"><span data-stu-id="d61fa-130">It uses the **PowerShellVersion** and **AliasesToExport** parameters to add values to the corresponding manifest keys.</span></span>

```powershell
New-ModuleManifest -PowerShellVersion 1.0 -AliasesToExport JKBC, DRC, TAC -Path C:\ps-test\ManifestTest.psd1
```

### <span data-ttu-id="d61fa-131">Пример 3. Создание манифеста, для которого требуются другие модули</span><span class="sxs-lookup"><span data-stu-id="d61fa-131">Example 3 - Create a manifest that requires other modules</span></span>

<span data-ttu-id="d61fa-132">В этом примере используется формат строки для указания имени модуля **BitsTransfer** и формата хэш-таблицы для указания имени, **идентификатора GUID** и версии модуля **PSScheduledJob** .</span><span class="sxs-lookup"><span data-stu-id="d61fa-132">This example uses a string format to specify the name of the **BitsTransfer** module and the hash table format to specify the name, a **GUID** , and a version of the **PSScheduledJob** module.</span></span>

```powershell
$moduleSettings = @{
  RequiredModules = ("BitsTransfer", @{
    ModuleName="PSScheduledJob"
    ModuleVersion="1.0.0.0";
    GUID="50cdb55f-5ab7-489f-9e94-4ec21ff51e59"
  })
  Path = 'C:\ps-test\ManifestTest.psd1'
}
New-ModuleManifest @moduleSettings
```

<span data-ttu-id="d61fa-133">В этом примере показано, как использовать форматы строк и хэш-таблиц для параметра **модулелист** , **RequiredModules** и **NestedModules** .</span><span class="sxs-lookup"><span data-stu-id="d61fa-133">This example shows how to use the string and hash table formats of the **ModuleList** , **RequiredModules** , and **NestedModules** parameter.</span></span> <span data-ttu-id="d61fa-134">В одном и том же значении параметра строки и хэш-таблицы можно объединять.</span><span class="sxs-lookup"><span data-stu-id="d61fa-134">You can combine strings and hash tables in the same parameter value.</span></span>

### <span data-ttu-id="d61fa-135">Пример 4. Создание манифеста, поддерживающего обновляемую справку</span><span class="sxs-lookup"><span data-stu-id="d61fa-135">Example 4 - Create a manifest that supports updateable help</span></span>

<span data-ttu-id="d61fa-136">В этом примере используется параметр **HelpInfoUri** для создания ключа **HelpInfoUri** в манифесте модуля.</span><span class="sxs-lookup"><span data-stu-id="d61fa-136">This example uses the **HelpInfoUri** parameter to create a **HelpInfoUri** key in the module manifest.</span></span> <span data-ttu-id="d61fa-137">Значение параметра и ключ должны начинаться с **http** или **HTTPS** .</span><span class="sxs-lookup"><span data-stu-id="d61fa-137">The value of the parameter and the key must begin with **http** or **https** .</span></span> <span data-ttu-id="d61fa-138">Оно сообщает системе обновляемой справки, где найти XML-файл обновляемой справки HelpInfo для этого модуля.</span><span class="sxs-lookup"><span data-stu-id="d61fa-138">This value tells the Updatable Help system where to find the HelpInfo XML updatable help information file for the module.</span></span>

```powershell
$moduleSettings = @{
  HelpInfoUri = 'http://https://go.microsoft.com/fwlink/?LinkID=603'
  Path = 'C:\ps-test\ManifestTest.psd1'
}
New-ModuleManifest @moduleSettings
```

<span data-ttu-id="d61fa-139">Сведения об обновляемой справке см. в разделе [about_Updatable_Help](./About/about_Updatable_Help.md).</span><span class="sxs-lookup"><span data-stu-id="d61fa-139">For information about Updatable Help, see [about_Updatable_Help](./About/about_Updatable_Help.md).</span></span>
<span data-ttu-id="d61fa-140">Сведения о XML-файле HelpInfo см. в разделе [Поддержка обновляемой справки](/powershell/scripting/developer/module/supporting-updatable-help).</span><span class="sxs-lookup"><span data-stu-id="d61fa-140">For information about the HelpInfo XML file, see [Supporting Updatable Help](/powershell/scripting/developer/module/supporting-updatable-help).</span></span>

### <span data-ttu-id="d61fa-141">Пример 5. Получение сведений о модуле</span><span class="sxs-lookup"><span data-stu-id="d61fa-141">Example 5 - Getting module information</span></span>

<span data-ttu-id="d61fa-142">В этом примере показано, как получить значения конфигурации модуля.</span><span class="sxs-lookup"><span data-stu-id="d61fa-142">This example shows how to get the configuration values of a module.</span></span> <span data-ttu-id="d61fa-143">Значения в манифесте модуля отражаются в значениях свойств объекта Module.</span><span class="sxs-lookup"><span data-stu-id="d61fa-143">The values in the module manifest are reflected in the values of properties of the module object.</span></span>

<span data-ttu-id="d61fa-144">`Get-Module`Командлет используется для получения модуля **Microsoft. PowerShell. Diagnostics** с помощью параметра **List** .</span><span class="sxs-lookup"><span data-stu-id="d61fa-144">The `Get-Module` cmdlet is used to get the **Microsoft.PowerShell.Diagnostics** module using the **List** parameter.</span></span> <span data-ttu-id="d61fa-145">Команда отправляет модуль в `Format-List` командлет для вывода всех свойств и значений объекта Module.</span><span class="sxs-lookup"><span data-stu-id="d61fa-145">The command sends the module to the `Format-List` cmdlet to display all properties and values of the module object.</span></span>

```powershell
Get-Module Microsoft.PowerShell.Diagnostics -List | Format-List -Property *
```

```Output
LogPipelineExecutionDetails : False
Name                        : Microsoft.PowerShell.Diagnostics
Path                        : C:\Windows\system32\WindowsPowerShell\v1.0\Modules\Microsoft.PowerShell.Diagnostics\Micro
                              soft.PowerShell.Diagnostics.psd1
Definition                  :
Description                 :
Guid                        : ca046f10-ca64-4740-8ff9-2565dba61a4f
HelpInfoUri                 : https://go.microsoft.com/fwlink/?LinkID=210596
ModuleBase                  : C:\Windows\system32\WindowsPowerShell\v1.0\Modules\Microsoft.PowerShell.Diagnostics
PrivateData                 :
Version                     : 3.0.0.0
ModuleType                  : Manifest
Author                      : Microsoft Corporation
AccessMode                  : ReadWrite
ClrVersion                  : 4.0
CompanyName                 : Microsoft Corporation
Copyright                   : Microsoft Corporation. All rights reserved.
DotNetFrameworkVersion      :
ExportedFunctions           : {}
ExportedCmdlets             : {[Get-WinEvent, Get-WinEvent], [Get-Counter, Get-Counter], [Import-Counter,
                              Import-Counter], [Export-Counter, Export-Counter]...}
ExportedCommands            : {[Get-WinEvent, Get-WinEvent], [Get-Counter, Get-Counter], [Import-Counter,
                              Import-Counter], [Export-Counter, Export-Counter]...}
FileList                    : {}
ModuleList                  : {}
NestedModules               : {}
PowerShellHostName          :
PowerShellHostVersion       :
PowerShellVersion           : 3.0
ProcessorArchitecture       : None
Scripts                     : {}
RequiredAssemblies          : {}
RequiredModules             : {}
RootModule                  :
ExportedVariables           : {}
ExportedAliases             : {}
ExportedWorkflows           : {}
SessionState                :
OnRemove                    :
ExportedFormatFiles         : {C:\Windows\system32\WindowsPowerShell\v1.0\Event.format.ps1xml,
                              C:\Windows\system32\WindowsPowerShell\v1.0\Diagnostics.format.ps1xml}
ExportedTypeFiles           : {C:\Windows\system32\WindowsPowerShell\v1.0\GetEvent.types.ps1xml}
```

## <span data-ttu-id="d61fa-146">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d61fa-146">PARAMETERS</span></span>

### <span data-ttu-id="d61fa-147">-Алиасестоекспорт</span><span class="sxs-lookup"><span data-stu-id="d61fa-147">-AliasesToExport</span></span>

<span data-ttu-id="d61fa-148">Задает экспортируемые модулем псевдонимы.</span><span class="sxs-lookup"><span data-stu-id="d61fa-148">Specifies the aliases that the module exports.</span></span> <span data-ttu-id="d61fa-149">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="d61fa-149">Wildcards are permitted.</span></span>

<span data-ttu-id="d61fa-150">Этот параметр можно использовать для ограничения экспортируемых модулем псевдонимов.</span><span class="sxs-lookup"><span data-stu-id="d61fa-150">You can use this parameter to restrict the aliases that are exported by the module.</span></span> <span data-ttu-id="d61fa-151">Он может удалять псевдонимы из списка экспортируемых псевдонимов, но не может добавлять в список псевдонимы.</span><span class="sxs-lookup"><span data-stu-id="d61fa-151">It can remove aliases from the list of exported aliases, but it can't add aliases to the list.</span></span>

<span data-ttu-id="d61fa-152">Если опустить этот параметр, `New-ModuleManifest` создает ключ **алиасестоекспорт** со значением `*` (ALL), что означает, что все псевдонимы, определенные в модуле, экспортируются манифестом.</span><span class="sxs-lookup"><span data-stu-id="d61fa-152">If you omit this parameter, `New-ModuleManifest` creates an **AliasesToExport** key with a value of `*` (all), meaning that all aliases defined in the module are exported by the manifest.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: * (all)
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="d61fa-153">-Author</span><span class="sxs-lookup"><span data-stu-id="d61fa-153">-Author</span></span>

<span data-ttu-id="d61fa-154">Задает автора модуля.</span><span class="sxs-lookup"><span data-stu-id="d61fa-154">Specifies the module author.</span></span>

<span data-ttu-id="d61fa-155">Если этот параметр не задан, `New-ModuleManifest` создает ключ **автора** с именем текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="d61fa-155">If you omit this parameter, `New-ModuleManifest` creates an **Author** key with the name of the current user.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Name of the current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d61fa-156">-CmdletsToExport</span><span class="sxs-lookup"><span data-stu-id="d61fa-156">-CmdletsToExport</span></span>

<span data-ttu-id="d61fa-157">Задает экспортируемые модулем командлеты.</span><span class="sxs-lookup"><span data-stu-id="d61fa-157">Specifies the cmdlets that the module exports.</span></span> <span data-ttu-id="d61fa-158">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="d61fa-158">Wildcards are permitted.</span></span>

<span data-ttu-id="d61fa-159">Этот параметр можно использовать для ограничения экспортируемых модулем командлетов.</span><span class="sxs-lookup"><span data-stu-id="d61fa-159">You can use this parameter to restrict the cmdlets that are exported by the module.</span></span> <span data-ttu-id="d61fa-160">Он может удалить командлеты из списка экспортированных командлетов, но не может добавить командлеты в список.</span><span class="sxs-lookup"><span data-stu-id="d61fa-160">It can remove cmdlets from the list of exported cmdlets, but it can't add cmdlets to the list.</span></span>

<span data-ttu-id="d61fa-161">Если опустить этот параметр, `New-ModuleManifest` создает ключ **CmdletsToExport** со значением `*` (ALL), что означает, что все командлеты, определенные в модуле, экспортируются манифестом.</span><span class="sxs-lookup"><span data-stu-id="d61fa-161">If you omit this parameter, `New-ModuleManifest` creates a **CmdletsToExport** key with a value of `*` (all), meaning that all cmdlets defined in the module are exported by the manifest.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: * (all)
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="d61fa-162">-CompanyName</span><span class="sxs-lookup"><span data-stu-id="d61fa-162">-CompanyName</span></span>

<span data-ttu-id="d61fa-163">Указывает компанию или поставщика, создавшего модуль.</span><span class="sxs-lookup"><span data-stu-id="d61fa-163">Identifies the company or vendor who created the module.</span></span>

<span data-ttu-id="d61fa-164">Если опустить этот параметр, `New-ModuleManifest` создает ключ **CompanyName** со значением Unknown.</span><span class="sxs-lookup"><span data-stu-id="d61fa-164">If you omit this parameter, `New-ModuleManifest` creates a **CompanyName** key with a value of "Unknown".</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: "Unknown"
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d61fa-165">-CompatiblePSEditions</span><span class="sxs-lookup"><span data-stu-id="d61fa-165">-CompatiblePSEditions</span></span>

<span data-ttu-id="d61fa-166">Указывает совместимый PSEditions модуля.</span><span class="sxs-lookup"><span data-stu-id="d61fa-166">Specifies the module's compatible PSEditions.</span></span> <span data-ttu-id="d61fa-167">Сведения о PSEdition см. [в разделе модули с совместимыми выпусками PowerShell](/powershell/scripting/gallery/concepts/module-psedition-support).</span><span class="sxs-lookup"><span data-stu-id="d61fa-167">For information about PSEdition, see [Modules with compatible PowerShell Editions](/powershell/scripting/gallery/concepts/module-psedition-support).</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:
Accepted values: Desktop, Core

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d61fa-168">-Copyright</span><span class="sxs-lookup"><span data-stu-id="d61fa-168">-Copyright</span></span>

<span data-ttu-id="d61fa-169">Задает заявление об авторских правах на модуль.</span><span class="sxs-lookup"><span data-stu-id="d61fa-169">Specifies a copyright statement for the module.</span></span>

<span data-ttu-id="d61fa-170">Если опустить этот параметр, `New-ModuleManifest` создает ключ **авторского права** со значением, `(c) <year> <username>. All rights reserved.` где `<year>` — текущий год, а `<username>` — значением ключа **автора** .</span><span class="sxs-lookup"><span data-stu-id="d61fa-170">If you omit this parameter, `New-ModuleManifest` creates a **Copyright** key with a value of `(c) <year> <username>. All rights reserved.` where `<year>` is the current year and `<username>` is the value of the **Author** key.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (c) <year> <username>. All rights reserved.
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d61fa-171">-DefaultCommandPrefix</span><span class="sxs-lookup"><span data-stu-id="d61fa-171">-DefaultCommandPrefix</span></span>

<span data-ttu-id="d61fa-172">Задает префикс, добавляемый в начало существительных всех команд в модуле при их импорте в сеанс.</span><span class="sxs-lookup"><span data-stu-id="d61fa-172">Specifies a prefix that is prepended to the nouns of all commands in the module when they're imported into a session.</span></span> <span data-ttu-id="d61fa-173">Введите строку префикса.</span><span class="sxs-lookup"><span data-stu-id="d61fa-173">Enter a prefix string.</span></span> <span data-ttu-id="d61fa-174">Префиксы предотвращают конфликты имен команд в сеансе пользователя.</span><span class="sxs-lookup"><span data-stu-id="d61fa-174">Prefixes prevent command name conflicts in a user's session.</span></span>

<span data-ttu-id="d61fa-175">Пользователи модуля могут переопределить этот префикс, указав параметр **prefix** `Import-Module` командлета.</span><span class="sxs-lookup"><span data-stu-id="d61fa-175">Module users can override this prefix by specifying the **Prefix** parameter of the `Import-Module` cmdlet.</span></span>

<span data-ttu-id="d61fa-176">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="d61fa-176">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d61fa-177">-Description</span><span class="sxs-lookup"><span data-stu-id="d61fa-177">-Description</span></span>

<span data-ttu-id="d61fa-178">Описывает содержимое модуля.</span><span class="sxs-lookup"><span data-stu-id="d61fa-178">Describes the contents of the module.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d61fa-179">-Дотнетфрамеворкверсион</span><span class="sxs-lookup"><span data-stu-id="d61fa-179">-DotNetFrameworkVersion</span></span>

<span data-ttu-id="d61fa-180">Указывает минимальную версию платформу Microsoft .NET, которая требуется для работы модуля.</span><span class="sxs-lookup"><span data-stu-id="d61fa-180">Specifies the minimum version of the Microsoft .NET Framework that the module requires.</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d61fa-181">-DscResourcesToExport</span><span class="sxs-lookup"><span data-stu-id="d61fa-181">-DscResourcesToExport</span></span>

<span data-ttu-id="d61fa-182">Указывает ресурсы настройки требуемого состояния (DSC), которые экспортирует модуль.</span><span class="sxs-lookup"><span data-stu-id="d61fa-182">Specifies the Desired State Configuration (DSC) resources that the module exports.</span></span> <span data-ttu-id="d61fa-183">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="d61fa-183">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="d61fa-184">-ЕкстерналмодуледепенденЦиес</span><span class="sxs-lookup"><span data-stu-id="d61fa-184">-ExternalModuleDependencies</span></span>

<span data-ttu-id="d61fa-185">Список внешних модулей, от которых зависит этот модуль.</span><span class="sxs-lookup"><span data-stu-id="d61fa-185">A list of external modules that this module is depends on.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d61fa-186">-FileList</span><span class="sxs-lookup"><span data-stu-id="d61fa-186">-FileList</span></span>

<span data-ttu-id="d61fa-187">Задает все элементы, включенные в модуль.</span><span class="sxs-lookup"><span data-stu-id="d61fa-187">Specifies all items that are included in the module.</span></span>

<span data-ttu-id="d61fa-188">Этот ключ выполняет функцию полного списка ресурсов модуля.</span><span class="sxs-lookup"><span data-stu-id="d61fa-188">This key is designed to act as a module inventory.</span></span> <span data-ttu-id="d61fa-189">Файлы, перечисленные в разделе, включаются при публикации модуля, но любые функции не экспортируются автоматически.</span><span class="sxs-lookup"><span data-stu-id="d61fa-189">The files listed in the key are included when the module is published, but any functions aren't automatically exported.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d61fa-190">-FormatsToProcess</span><span class="sxs-lookup"><span data-stu-id="d61fa-190">-FormatsToProcess</span></span>

<span data-ttu-id="d61fa-191">Задает файлы форматирования ( `.ps1xml` ), которые выполняются при импорте модуля.</span><span class="sxs-lookup"><span data-stu-id="d61fa-191">Specifies the formatting files (`.ps1xml`) that run when the module is imported.</span></span>

<span data-ttu-id="d61fa-192">При импорте модуля PowerShell запускает `Update-FormatData` командлет с указанными файлами.</span><span class="sxs-lookup"><span data-stu-id="d61fa-192">When you import a module, PowerShell runs the `Update-FormatData` cmdlet with the specified files.</span></span>
<span data-ttu-id="d61fa-193">Так как файлы форматирования не находятся в области, они влияют на все состояния сеанса в сеансе.</span><span class="sxs-lookup"><span data-stu-id="d61fa-193">Because formatting files aren't scoped, they affect all session states in the session.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d61fa-194">-FunctionsToExport</span><span class="sxs-lookup"><span data-stu-id="d61fa-194">-FunctionsToExport</span></span>

<span data-ttu-id="d61fa-195">Задает экспортируемые модулем функции.</span><span class="sxs-lookup"><span data-stu-id="d61fa-195">Specifies the functions that the module exports.</span></span> <span data-ttu-id="d61fa-196">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="d61fa-196">Wildcards are permitted.</span></span>

<span data-ttu-id="d61fa-197">Этот параметр можно использовать для ограничения экспортируемых модулем функций.</span><span class="sxs-lookup"><span data-stu-id="d61fa-197">You can use this parameter to restrict the functions that are exported by the module.</span></span> <span data-ttu-id="d61fa-198">Он может удалять функции из списка экспортируемых псевдонимов, но не может добавлять функции в список.</span><span class="sxs-lookup"><span data-stu-id="d61fa-198">It can remove functions from the list of exported aliases, but it can't add functions to the list.</span></span>

<span data-ttu-id="d61fa-199">Если опустить этот параметр, `New-ModuleManifest` создает ключ **FunctionsToExport** со значением `*` (ALL), что означает, что все функции, определенные в модуле, экспортируются манифестом.</span><span class="sxs-lookup"><span data-stu-id="d61fa-199">If you omit this parameter, `New-ModuleManifest` creates an **FunctionsToExport** key with a value of `*` (all), meaning that all functions defined in the module are exported by the manifest.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: * (all)
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="d61fa-200">-Guid</span><span class="sxs-lookup"><span data-stu-id="d61fa-200">-Guid</span></span>

<span data-ttu-id="d61fa-201">Задает уникальный идентификатор модуля.</span><span class="sxs-lookup"><span data-stu-id="d61fa-201">Specifies a unique identifier for the module.</span></span> <span data-ttu-id="d61fa-202">**GUID** можно использовать для различения модулей с одинаковыми именами.</span><span class="sxs-lookup"><span data-stu-id="d61fa-202">The **GUID** can be used to distinguish among modules with the same name.</span></span>

<span data-ttu-id="d61fa-203">Если этот параметр не указан, `New-ModuleManifest` создает ключ **GUID** в манифесте и создает **идентификатор GUID** для значения.</span><span class="sxs-lookup"><span data-stu-id="d61fa-203">If you omit this parameter, `New-ModuleManifest` creates a **GUID** key in the manifest and generates a **GUID** for the value.</span></span>

<span data-ttu-id="d61fa-204">Чтобы создать новый **GUID** в PowerShell, введите `[guid]::NewGuid()` .</span><span class="sxs-lookup"><span data-stu-id="d61fa-204">To create a new **GUID** in PowerShell, type `[guid]::NewGuid()`.</span></span>

```yaml
Type: System.Guid
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: A GUID generated for the module
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d61fa-205">-HelpInfoUri</span><span class="sxs-lookup"><span data-stu-id="d61fa-205">-HelpInfoUri</span></span>

<span data-ttu-id="d61fa-206">Указывает адрес XML-файла HelpInfo для модуля.</span><span class="sxs-lookup"><span data-stu-id="d61fa-206">Specifies the internet address of the HelpInfo XML file for the module.</span></span> <span data-ttu-id="d61fa-207">Введите универсальный код ресурса (URI), который начинается с **http** или **HTTPS** .</span><span class="sxs-lookup"><span data-stu-id="d61fa-207">Enter a Uniform Resource Identifier (URI) that begins with **http** or **https** .</span></span>

<span data-ttu-id="d61fa-208">XML-файл HelpInfo поддерживает функцию обновляемой справки, которая появилась в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="d61fa-208">The HelpInfo XML file supports the Updatable Help feature that was introduced in PowerShell 3.0.</span></span> <span data-ttu-id="d61fa-209">Он содержит сведения о расположении загружаемых файлов справки для модуля и номера версий последних файлов справки для каждого поддерживаемого языка.</span><span class="sxs-lookup"><span data-stu-id="d61fa-209">It contains information about the location of downloadable help files for the module and the version numbers of the newest help files for each supported locale.</span></span>

<span data-ttu-id="d61fa-210">Сведения об обновляемой справке см. в разделе [about_Updatable_Help](./About/about_Updatable_Help.md).</span><span class="sxs-lookup"><span data-stu-id="d61fa-210">For information about Updatable Help, see [about_Updatable_Help](./About/about_Updatable_Help.md).</span></span>
<span data-ttu-id="d61fa-211">Сведения о XML-файле HelpInfo см. в разделе [Поддержка обновляемой справки](/powershell/scripting/developer/module/supporting-updatable-help).</span><span class="sxs-lookup"><span data-stu-id="d61fa-211">For information about the HelpInfo XML file, see [Supporting Updatable Help](/powershell/scripting/developer/module/supporting-updatable-help).</span></span>

<span data-ttu-id="d61fa-212">Этот параметр появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="d61fa-212">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d61fa-213">-IconUri</span><span class="sxs-lookup"><span data-stu-id="d61fa-213">-IconUri</span></span>

<span data-ttu-id="d61fa-214">Задает URL-адрес значка для модуля.</span><span class="sxs-lookup"><span data-stu-id="d61fa-214">Specifies the URL of an icon for the module.</span></span> <span data-ttu-id="d61fa-215">Указанный значок отображается на веб-странице коллекции модуля.</span><span class="sxs-lookup"><span data-stu-id="d61fa-215">The specified icon is displayed on the gallery web page for the module.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d61fa-216">-LicenseUri</span><span class="sxs-lookup"><span data-stu-id="d61fa-216">-LicenseUri</span></span>

<span data-ttu-id="d61fa-217">Указывает URL-адрес условий лицензирования для модуля.</span><span class="sxs-lookup"><span data-stu-id="d61fa-217">Specifies the URL of licensing terms for the module.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d61fa-218">-Модулелист</span><span class="sxs-lookup"><span data-stu-id="d61fa-218">-ModuleList</span></span>

<span data-ttu-id="d61fa-219">Выводит список всех модулей, включенных в данный модуль.</span><span class="sxs-lookup"><span data-stu-id="d61fa-219">Lists all modules that are included in this module.</span></span>

<span data-ttu-id="d61fa-220">Введите имя каждого модуля в виде строки или хэш-таблицы с ключами **ModuleName** и **ModuleVersion** .</span><span class="sxs-lookup"><span data-stu-id="d61fa-220">Enter each module name as a string or as a hash table with **ModuleName** and **ModuleVersion** keys.</span></span> <span data-ttu-id="d61fa-221">Хэш-таблица может иметь дополнительный ключ **GUID** .</span><span class="sxs-lookup"><span data-stu-id="d61fa-221">The hash table can also have an optional **GUID** key.</span></span> <span data-ttu-id="d61fa-222">В значении параметра строки и хэш-таблицы можно объединять.</span><span class="sxs-lookup"><span data-stu-id="d61fa-222">You can combine strings and hash tables in the parameter value.</span></span>

<span data-ttu-id="d61fa-223">Этот ключ выполняет функцию полного списка ресурсов модуля.</span><span class="sxs-lookup"><span data-stu-id="d61fa-223">This key is designed to act as a module inventory.</span></span> <span data-ttu-id="d61fa-224">Модули, указанные в значении этого ключа, не обрабатываются автоматически.</span><span class="sxs-lookup"><span data-stu-id="d61fa-224">The modules that are listed in the value of this key aren't automatically processed.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d61fa-225">-Истечение</span><span class="sxs-lookup"><span data-stu-id="d61fa-225">-ModuleVersion</span></span>

<span data-ttu-id="d61fa-226">Указывает версию модуля.</span><span class="sxs-lookup"><span data-stu-id="d61fa-226">Specifies the module's version.</span></span>

<span data-ttu-id="d61fa-227">Этот параметр не является обязательным, но **в манифесте требуется ключ "** ключом".</span><span class="sxs-lookup"><span data-stu-id="d61fa-227">This parameter isn't required, but a **ModuleVersion** key is required in the manifest.</span></span> <span data-ttu-id="d61fa-228">Если этот параметр не указан, `New-ModuleManifest` создает ключ **ModuleVersion** пересчета со значением 1,0.</span><span class="sxs-lookup"><span data-stu-id="d61fa-228">If you omit this parameter, `New-ModuleManifest` creates a **ModuleVersion** key with a value of 1.0.</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 1.0
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d61fa-229">-NestedModules</span><span class="sxs-lookup"><span data-stu-id="d61fa-229">-NestedModules</span></span>

<span data-ttu-id="d61fa-230">Задает модули скрипта ( `.psm1` ) и двоичные модули ( `.dll` ), которые импортируются в состояние сеанса модуля.</span><span class="sxs-lookup"><span data-stu-id="d61fa-230">Specifies script modules (`.psm1`) and binary modules (`.dll`) that are imported into the module's session state.</span></span> <span data-ttu-id="d61fa-231">Файлы в ключе **NestedModules** выполняются в том порядке, в котором они указаны в значении.</span><span class="sxs-lookup"><span data-stu-id="d61fa-231">The files in the **NestedModules** key run in the order in which they're listed in the value.</span></span>

<span data-ttu-id="d61fa-232">Введите имя каждого модуля в виде строки или хэш-таблицы с ключами **ModuleName** и **ModuleVersion** .</span><span class="sxs-lookup"><span data-stu-id="d61fa-232">Enter each module name as a string or as a hash table with **ModuleName** and **ModuleVersion** keys.</span></span> <span data-ttu-id="d61fa-233">Хэш-таблица может иметь дополнительный ключ **GUID** .</span><span class="sxs-lookup"><span data-stu-id="d61fa-233">The hash table can also have an optional **GUID** key.</span></span> <span data-ttu-id="d61fa-234">В значении параметра строки и хэш-таблицы можно объединять.</span><span class="sxs-lookup"><span data-stu-id="d61fa-234">You can combine strings and hash tables in the parameter value.</span></span>

<span data-ttu-id="d61fa-235">Обычно вложенные модули содержат команды, необходимые основному модулю для внутренней обработки.</span><span class="sxs-lookup"><span data-stu-id="d61fa-235">Typically, nested modules contain commands that the root module needs for its internal processing.</span></span>
<span data-ttu-id="d61fa-236">По умолчанию команды во вложенных модулях экспортируются из состояния сеанса модуля в состояние сеанса вызывающего объекта, но корневой модуль может ограничивать экспортируемые команды.</span><span class="sxs-lookup"><span data-stu-id="d61fa-236">By default, the commands in nested modules are exported from the module's session state into the caller's session state, but the root module can restrict the commands that it exports.</span></span> <span data-ttu-id="d61fa-237">Например, с помощью `Export-ModuleMember` команды.</span><span class="sxs-lookup"><span data-stu-id="d61fa-237">For example, by using an `Export-ModuleMember` command.</span></span>

<span data-ttu-id="d61fa-238">Вложенные модули в состоянии сеанса модуля доступны для корневого модуля, но не возвращаются `Get-Module` командой в состоянии сеанса вызывающего.</span><span class="sxs-lookup"><span data-stu-id="d61fa-238">Nested modules in the module session state are available to the root module, but they aren't returned by a `Get-Module` command in the caller's session state.</span></span>

<span data-ttu-id="d61fa-239">Скрипты ( `.ps1` ), перечисленные в ключе **NestedModules** , выполняются в состоянии сеанса модуля, а не в состоянии сеанса вызывающего.</span><span class="sxs-lookup"><span data-stu-id="d61fa-239">Scripts (`.ps1`) that are listed in the **NestedModules** key are run in the module's session state, not in the caller's session state.</span></span> <span data-ttu-id="d61fa-240">Чтобы запустить скрипт в состоянии сеанса вызывающего объекта, укажите имя файла скрипта в значении ключа **ScriptsToProcess** манифеста.</span><span class="sxs-lookup"><span data-stu-id="d61fa-240">To run a script in the caller's session state, list the script file name in the value of the **ScriptsToProcess** key in the manifest.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d61fa-241">-PassThru</span><span class="sxs-lookup"><span data-stu-id="d61fa-241">-PassThru</span></span>

<span data-ttu-id="d61fa-242">Записывает полученный манифест модуля в консоль и создает `.psd1` файл.</span><span class="sxs-lookup"><span data-stu-id="d61fa-242">Writes the resulting module manifest to the console and creates a `.psd1` file.</span></span> <span data-ttu-id="d61fa-243">По умолчанию этот командлет не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="d61fa-243">By default, this cmdlet doesn't generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d61fa-244">-Path</span><span class="sxs-lookup"><span data-stu-id="d61fa-244">-Path</span></span>

<span data-ttu-id="d61fa-245">Указывает путь и имя файла нового манифеста модуля.</span><span class="sxs-lookup"><span data-stu-id="d61fa-245">Specifies the path and file name of the new module manifest.</span></span> <span data-ttu-id="d61fa-246">Введите путь и имя файла с `.psd1` расширением имени файла, например `$pshome\Modules\MyModule\MyModule.psd1` .</span><span class="sxs-lookup"><span data-stu-id="d61fa-246">Enter a path and file name with a `.psd1` file name extension, such as `$pshome\Modules\MyModule\MyModule.psd1`.</span></span> <span data-ttu-id="d61fa-247">Параметр **path** является обязательным.</span><span class="sxs-lookup"><span data-stu-id="d61fa-247">The **Path** parameter is required.</span></span>

<span data-ttu-id="d61fa-248">При указании пути к существующему файлу `New-ModuleManifest` заменяет файл без предупреждения, если только файл не имеет атрибута только для чтения.</span><span class="sxs-lookup"><span data-stu-id="d61fa-248">If you specify the path to an existing file, `New-ModuleManifest` replaces the file without warning unless the file has the read-only attribute.</span></span>

<span data-ttu-id="d61fa-249">Манифест должен находиться в каталоге модуля, а имя файла манифеста должно совпадать с именем каталога модуля, но с `.psd1` расширением имени файла.</span><span class="sxs-lookup"><span data-stu-id="d61fa-249">The manifest should be located in the module's directory, and the manifest file name should be the same as the module directory name, but with a `.psd1` file name extension.</span></span>

> [!NOTE]
> <span data-ttu-id="d61fa-250">Нельзя использовать переменные, например `$PSHOME` или `$HOME` , в ответ на запрос значения параметра **path** .</span><span class="sxs-lookup"><span data-stu-id="d61fa-250">You cannot use variables, such as `$PSHOME` or `$HOME`, in response to a prompt for a **Path** parameter value.</span></span> <span data-ttu-id="d61fa-251">Чтобы использовать переменную, включите параметр **Path** в команду.</span><span class="sxs-lookup"><span data-stu-id="d61fa-251">To use a variable, include the **Path** parameter in the command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d61fa-252">-Повершеллхостнаме</span><span class="sxs-lookup"><span data-stu-id="d61fa-252">-PowerShellHostName</span></span>

<span data-ttu-id="d61fa-253">Указывает имя основной программы PowerShell, требуемой для модуля.</span><span class="sxs-lookup"><span data-stu-id="d61fa-253">Specifies the name of the PowerShell host program that the module requires.</span></span> <span data-ttu-id="d61fa-254">Введите имя основной программы, например **Windows POWERSHELL ISE Host** или **ConsoleHost** .</span><span class="sxs-lookup"><span data-stu-id="d61fa-254">Enter the name of the host program, such as **Windows PowerShell ISE Host** or **ConsoleHost** .</span></span> <span data-ttu-id="d61fa-255">Подстановочные знаки не допускаются.</span><span class="sxs-lookup"><span data-stu-id="d61fa-255">Wildcards aren't permitted.</span></span>

<span data-ttu-id="d61fa-256">Чтобы найти имя основной программы, в программе введите `$Host.Name` .</span><span class="sxs-lookup"><span data-stu-id="d61fa-256">To find the name of a host program, in the program, type `$Host.Name`.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d61fa-257">-Повершеллхостверсион</span><span class="sxs-lookup"><span data-stu-id="d61fa-257">-PowerShellHostVersion</span></span>

<span data-ttu-id="d61fa-258">Указывает минимальную версию основной программы PowerShell, которая работает с модулем.</span><span class="sxs-lookup"><span data-stu-id="d61fa-258">Specifies the minimum version of the PowerShell host program that works with the module.</span></span> <span data-ttu-id="d61fa-259">Введите номер версии, например, 1.1.</span><span class="sxs-lookup"><span data-stu-id="d61fa-259">Enter a version number, such as 1.1.</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d61fa-260">-PowerShellVersion</span><span class="sxs-lookup"><span data-stu-id="d61fa-260">-PowerShellVersion</span></span>

<span data-ttu-id="d61fa-261">Указывает минимальную версию PowerShell, которая работает с этим модулем.</span><span class="sxs-lookup"><span data-stu-id="d61fa-261">Specifies the minimum version of PowerShell that works with this module.</span></span> <span data-ttu-id="d61fa-262">Например, в качестве значения параметра можно ввести 1,0, 2,0 или 3,0.</span><span class="sxs-lookup"><span data-stu-id="d61fa-262">For example, you can enter 1.0, 2.0, or 3.0 as the parameter's value.</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d61fa-263">— Предварительный выпуск</span><span class="sxs-lookup"><span data-stu-id="d61fa-263">-Prerelease</span></span>

<span data-ttu-id="d61fa-264">Строка предварительной версии этого модуля.</span><span class="sxs-lookup"><span data-stu-id="d61fa-264">Prerelease string of this module.</span></span> <span data-ttu-id="d61fa-265">Добавление строки предварительной версии означает, что модуль является предварительной версией.</span><span class="sxs-lookup"><span data-stu-id="d61fa-265">Adding a Prerelease string identifies the module as a prerelease version.</span></span> <span data-ttu-id="d61fa-266">При публикации модуля в коллекция PowerShell эти данные используются для обнаружения пакетов предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="d61fa-266">When the module is published to the PowerShell Gallery, this data is used to identify prerelease packages.</span></span> <span data-ttu-id="d61fa-267">Чтобы получить пакеты предварительной версии из коллекции, необходимо использовать параметр **AllowPrerelease** с командами PowerShellGet,, `Find-Module` `Install-Module` `Update-Module` и `Save-Module` .</span><span class="sxs-lookup"><span data-stu-id="d61fa-267">To acquire prerelease packages from the Gallery, you must use the **AllowPrerelease** parameter with the PowerShellGet commands `Find-Module`, `Install-Module`, `Update-Module`, and `Save-Module`.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d61fa-268">-PrivateData</span><span class="sxs-lookup"><span data-stu-id="d61fa-268">-PrivateData</span></span>

<span data-ttu-id="d61fa-269">Указывает данные, которые передаются в модуль при его импорте.</span><span class="sxs-lookup"><span data-stu-id="d61fa-269">Specifies data that is passed to the module when it's imported.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d61fa-270">-ProcessorArchitecture</span><span class="sxs-lookup"><span data-stu-id="d61fa-270">-ProcessorArchitecture</span></span>

<span data-ttu-id="d61fa-271">Указывает архитектуру процессора, необходимую для этого модуля.</span><span class="sxs-lookup"><span data-stu-id="d61fa-271">Specifies the processor architecture that the module requires.</span></span> <span data-ttu-id="d61fa-272">Допустимые значения: x86, AMD64, IA64, MSIL и None (неизвестный или не указан).</span><span class="sxs-lookup"><span data-stu-id="d61fa-272">Valid values are x86, AMD64, IA64, MSIL, and None (unknown or unspecified).</span></span>

```yaml
Type: System.Reflection.ProcessorArchitecture
Parameter Sets: (All)
Aliases:
Accepted values: None, MSIL, X86, IA64, Amd64, Arm

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d61fa-273">-ProjectUri</span><span class="sxs-lookup"><span data-stu-id="d61fa-273">-ProjectUri</span></span>

<span data-ttu-id="d61fa-274">Указывает URL веб-страницы об этом проекте.</span><span class="sxs-lookup"><span data-stu-id="d61fa-274">Specifies the URL of a web page about this project.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d61fa-275">-ReleaseNotes</span><span class="sxs-lookup"><span data-stu-id="d61fa-275">-ReleaseNotes</span></span>

<span data-ttu-id="d61fa-276">Указывает заметки о выпуске.</span><span class="sxs-lookup"><span data-stu-id="d61fa-276">Specifies release notes.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d61fa-277">-Рекуиредассемблиес</span><span class="sxs-lookup"><span data-stu-id="d61fa-277">-RequiredAssemblies</span></span>

<span data-ttu-id="d61fa-278">Указывает файлы сборки ( `.dll` ), необходимые для работы модуля.</span><span class="sxs-lookup"><span data-stu-id="d61fa-278">Specifies the assembly (`.dll`) files that the module requires.</span></span> <span data-ttu-id="d61fa-279">Введите имена файлов сборки.</span><span class="sxs-lookup"><span data-stu-id="d61fa-279">Enter the assembly file names.</span></span>
<span data-ttu-id="d61fa-280">PowerShell загружает указанные сборки перед обновлением типов или форматов, импортом вложенных модулей или импортом файла модуля, который указан в значении ключа **RootModule** .</span><span class="sxs-lookup"><span data-stu-id="d61fa-280">PowerShell loads the specified assemblies before updating types or formats, importing nested modules, or importing the module file that is specified in the value of the **RootModule** key.</span></span>

<span data-ttu-id="d61fa-281">Используйте этот параметр для перечисления всех необходимых модулю сборок, включая сборки, загрузка которых требуется для обновления файлов форматирования или файлов типов, указанных в ключах **FormatsToProcess** и **TypesToProcess** , даже если эти сборки также указаны как двоичные модули в ключе **NestedModules** .</span><span class="sxs-lookup"><span data-stu-id="d61fa-281">Use this parameter to list all the assemblies that the module requires, including assemblies that must be loaded to update any formatting or type files that are listed in the **FormatsToProcess** or **TypesToProcess** keys, even if those assemblies are also listed as binary modules in the **NestedModules** key.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d61fa-282">-RequiredModules</span><span class="sxs-lookup"><span data-stu-id="d61fa-282">-RequiredModules</span></span>

<span data-ttu-id="d61fa-283">Определяет модули, которые должны присутствовать в глобальном состоянии сеанса.</span><span class="sxs-lookup"><span data-stu-id="d61fa-283">Specifies modules that must be in the global session state.</span></span> <span data-ttu-id="d61fa-284">Если требуемые модули не находятся в глобальном состоянии сеанса, PowerShell импортирует их.</span><span class="sxs-lookup"><span data-stu-id="d61fa-284">If the required modules aren't in the global session state, PowerShell imports them.</span></span> <span data-ttu-id="d61fa-285">Если требуемые модули недоступны, `Import-Module` команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="d61fa-285">If the required modules aren't available, the `Import-Module` command fails.</span></span>

<span data-ttu-id="d61fa-286">Введите имя каждого модуля в виде строки или хэш-таблицы с ключами **ModuleName** и **ModuleVersion** .</span><span class="sxs-lookup"><span data-stu-id="d61fa-286">Enter each module name as a string or as a hash table with **ModuleName** and **ModuleVersion** keys.</span></span> <span data-ttu-id="d61fa-287">Хэш-таблица может иметь дополнительный ключ **GUID** .</span><span class="sxs-lookup"><span data-stu-id="d61fa-287">The hash table can also have an optional **GUID** key.</span></span> <span data-ttu-id="d61fa-288">В значении параметра строки и хэш-таблицы можно объединять.</span><span class="sxs-lookup"><span data-stu-id="d61fa-288">You can combine strings and hash tables in the parameter value.</span></span>

<span data-ttu-id="d61fa-289">В PowerShell 2,0 `Import-Module` не импортирует необходимые модули автоматически.</span><span class="sxs-lookup"><span data-stu-id="d61fa-289">In PowerShell 2.0, `Import-Module` doesn't import required modules automatically.</span></span> <span data-ttu-id="d61fa-290">Он только проверяет наличие необходимых модулей в глобальном состоянии сеанса.</span><span class="sxs-lookup"><span data-stu-id="d61fa-290">It just verifies that the required modules are in the global session state.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d61fa-291">-RequireLicenseAcceptance</span><span class="sxs-lookup"><span data-stu-id="d61fa-291">-RequireLicenseAcceptance</span></span>

<span data-ttu-id="d61fa-292">Флаг, указывающий, требует ли модуль явное согласие пользователя на установку, обновление, орсаве.</span><span class="sxs-lookup"><span data-stu-id="d61fa-292">Flag to indicate whether the module requires explicit user acceptance for install, update, orsave.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d61fa-293">-RootModule</span><span class="sxs-lookup"><span data-stu-id="d61fa-293">-RootModule</span></span>

<span data-ttu-id="d61fa-294">Указывает первичный или корневой файл модуля.</span><span class="sxs-lookup"><span data-stu-id="d61fa-294">Specifies the primary or root file of the module.</span></span> <span data-ttu-id="d61fa-295">Введите имя файла скрипта ( `.ps1` ), модуля скрипта ( `.psm1` ), манифеста модуля ( `.psd1` ), сборки ( `.dll` ), XML-файла определения командлета ( `.cdxml` ) или рабочего процесса ( `.xaml` ).</span><span class="sxs-lookup"><span data-stu-id="d61fa-295">Enter the file name of a script (`.ps1`), a script module (`.psm1`), a module manifest(`.psd1`), an assembly (`.dll`), a cmdlet definition XML file (`.cdxml`), or a workflow (`.xaml`).</span></span> <span data-ttu-id="d61fa-296">При импорте модуля элементы, экспортируемые из корневого файла модуля, импортируются в состояние сеанса вызывающего объекта.</span><span class="sxs-lookup"><span data-stu-id="d61fa-296">When the module is imported, the members that are exported from the root module file are imported into the caller's session state.</span></span>

<span data-ttu-id="d61fa-297">Если у модуля есть файл манифеста и корневой файл не был назначен в ключе **RootModule** , манифест станет первичным файлом для модуля, а модуль станет модулем манифеста (ModuleType = manifest).</span><span class="sxs-lookup"><span data-stu-id="d61fa-297">If a module has a manifest file and no root file was designated in the **RootModule** key, the manifest becomes the primary file for the module, and the module becomes a manifest module (ModuleType = Manifest).</span></span>

<span data-ttu-id="d61fa-298">Чтобы экспортировать элементы из `.psm1` `.dll` файла или в модуль с манифестом, имена этих файлов должны быть указаны в значениях ключей **RootModule** или **NestedModules** в манифесте.</span><span class="sxs-lookup"><span data-stu-id="d61fa-298">To export members from `.psm1` or `.dll` files in a module that has a manifest, the names of those files must be specified in the values of the **RootModule** or **NestedModules** keys in the manifest.</span></span> <span data-ttu-id="d61fa-299">В противном случае их члены не экспортируются.</span><span class="sxs-lookup"><span data-stu-id="d61fa-299">Otherwise, their members aren't exported.</span></span>

> [!NOTE]
> <span data-ttu-id="d61fa-300">В PowerShell 2,0 этот ключ назывался **модулетопроцесс** .</span><span class="sxs-lookup"><span data-stu-id="d61fa-300">In PowerShell 2.0, this key was called **ModuleToProcess** .</span></span> <span data-ttu-id="d61fa-301">Можно использовать имя параметра **RootModule** или его псевдоним **модулетопроцесс** .</span><span class="sxs-lookup"><span data-stu-id="d61fa-301">You can use the **RootModule** parameter name or its **ModuleToProcess** alias.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ModuleToProcess

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d61fa-302">-ScriptsToProcess</span><span class="sxs-lookup"><span data-stu-id="d61fa-302">-ScriptsToProcess</span></span>

<span data-ttu-id="d61fa-303">Указывает файлы скрипта ( `.ps1` ), которые выполняются в состоянии сеанса вызывающего объекта при импорте модуля.</span><span class="sxs-lookup"><span data-stu-id="d61fa-303">Specifies script (`.ps1`) files that run in the caller's session state when the module is imported.</span></span>
<span data-ttu-id="d61fa-304">Эти скрипты можно использовать для подготовки среды таким же образом, как и скрипт входа в систему.</span><span class="sxs-lookup"><span data-stu-id="d61fa-304">You can use these scripts to prepare an environment, just as you might use a login script.</span></span>

<span data-ttu-id="d61fa-305">Чтобы указать скрипты, которые будут выполняться в состоянии сеанса модуля, используйте ключ **NestedModules** .</span><span class="sxs-lookup"><span data-stu-id="d61fa-305">To specify scripts that run in the module's session state, use the **NestedModules** key.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d61fa-306">-Теги</span><span class="sxs-lookup"><span data-stu-id="d61fa-306">-Tags</span></span>

<span data-ttu-id="d61fa-307">Задает массив тегов.</span><span class="sxs-lookup"><span data-stu-id="d61fa-307">Specifies an array of tags.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d61fa-308">-TypesToProcess</span><span class="sxs-lookup"><span data-stu-id="d61fa-308">-TypesToProcess</span></span>

<span data-ttu-id="d61fa-309">Указывает файлы типов ( `.ps1xml` ), которые выполняются при импорте модуля.</span><span class="sxs-lookup"><span data-stu-id="d61fa-309">Specifies the type files (`.ps1xml`) that run when the module is imported.</span></span>

<span data-ttu-id="d61fa-310">При импорте модуля PowerShell запускает `Update-TypeData` командлет с указанными файлами.</span><span class="sxs-lookup"><span data-stu-id="d61fa-310">When you import the module, PowerShell runs the `Update-TypeData` cmdlet with the specified files.</span></span>
<span data-ttu-id="d61fa-311">Так как файлы типов не находятся в области, они влияют на все состояния сеанса в сеансе.</span><span class="sxs-lookup"><span data-stu-id="d61fa-311">Because type files aren't scoped, they affect all session states in the session.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d61fa-312">-Вариаблестоекспорт</span><span class="sxs-lookup"><span data-stu-id="d61fa-312">-VariablesToExport</span></span>

<span data-ttu-id="d61fa-313">Задает экспортируемые модулем переменные.</span><span class="sxs-lookup"><span data-stu-id="d61fa-313">Specifies the variables that the module exports.</span></span> <span data-ttu-id="d61fa-314">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="d61fa-314">Wildcards are permitted.</span></span>

<span data-ttu-id="d61fa-315">Этот параметр можно использовать для ограничения экспортируемых модулем переменных.</span><span class="sxs-lookup"><span data-stu-id="d61fa-315">You can use this parameter to restrict the variables that are exported by the module.</span></span> <span data-ttu-id="d61fa-316">Он может удалять переменные из списка экспортированных переменных, но не может добавлять переменные в список.</span><span class="sxs-lookup"><span data-stu-id="d61fa-316">It can remove variables from the list of exported variables, but it can't add variables to the list.</span></span>

<span data-ttu-id="d61fa-317">Если опустить этот параметр, `New-ModuleManifest` создает ключ **вариаблестоекспорт** со значением `*` (ALL), что означает, что все переменные, определенные в модуле, экспортируются манифестом.</span><span class="sxs-lookup"><span data-stu-id="d61fa-317">If you omit this parameter, `New-ModuleManifest` creates a **VariablesToExport** key with a value of `*` (all), meaning that all variables defined in the module are exported by the manifest.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: * (all)
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="d61fa-318">-Confirm</span><span class="sxs-lookup"><span data-stu-id="d61fa-318">-Confirm</span></span>

<span data-ttu-id="d61fa-319">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="d61fa-319">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d61fa-320">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="d61fa-320">-WhatIf</span></span>

<span data-ttu-id="d61fa-321">Показывает, что произойдет при `New-ModuleManifest` запуске.</span><span class="sxs-lookup"><span data-stu-id="d61fa-321">Shows what would happen if `New-ModuleManifest` runs.</span></span> <span data-ttu-id="d61fa-322">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="d61fa-322">The cmdlet isn't run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d61fa-323">-ClrVersion</span><span class="sxs-lookup"><span data-stu-id="d61fa-323">-ClrVersion</span></span>

<span data-ttu-id="d61fa-324">Задает минимальную версию среды CLR платформы Microsoft .NET Framework, которая требуется для работы модуля.</span><span class="sxs-lookup"><span data-stu-id="d61fa-324">Specifies the minimum version of the Common Language Runtime (CLR) of the Microsoft .NET Framework that the module requires.</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d61fa-325">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="d61fa-325">CommonParameters</span></span>
<span data-ttu-id="d61fa-326">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d61fa-326">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d61fa-327">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d61fa-327">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d61fa-328">Входные данные</span><span class="sxs-lookup"><span data-stu-id="d61fa-328">INPUTS</span></span>

### <span data-ttu-id="d61fa-329">Нет</span><span class="sxs-lookup"><span data-stu-id="d61fa-329">None</span></span>

<span data-ttu-id="d61fa-330">Вы не можете передать входные данные в этот командлет.</span><span class="sxs-lookup"><span data-stu-id="d61fa-330">You can't pipe input to this cmdlet.</span></span>

## <span data-ttu-id="d61fa-331">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="d61fa-331">OUTPUTS</span></span>

### <span data-ttu-id="d61fa-332">Нет или System.String</span><span class="sxs-lookup"><span data-stu-id="d61fa-332">None or System.String</span></span>

<span data-ttu-id="d61fa-333">По умолчанию `New-ModuleManifest` не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="d61fa-333">By default, `New-ModuleManifest` doesn't generate any output.</span></span> <span data-ttu-id="d61fa-334">Однако при использовании параметра **PassThru** создается объект **System. String** , представляющий манифест модуля.</span><span class="sxs-lookup"><span data-stu-id="d61fa-334">However, if you use the **PassThru** parameter, it generates a **System.String** object representing the module manifest.</span></span>

## <span data-ttu-id="d61fa-335">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="d61fa-335">NOTES</span></span>

<span data-ttu-id="d61fa-336">`New-ModuleManifest` При работе в Windows и на платформах, отличных от Windows, создаются файлы манифеста модуля ( `.psd1` ), закодированные как **UTF8NoBOM** .</span><span class="sxs-lookup"><span data-stu-id="d61fa-336">`New-ModuleManifest` running on Windows and non-Windows platforms creates module manifest (`.psd1`) files encoded as **UTF8NoBOM** .</span></span>

<span data-ttu-id="d61fa-337">Обычно манифесты не являются обязательным условием для работы модуля.</span><span class="sxs-lookup"><span data-stu-id="d61fa-337">Module manifests are usually optional.</span></span> <span data-ttu-id="d61fa-338">При этом манифест модуля необходим для экспорта сборки, установленной в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="d61fa-338">However, a module manifest is required to export an assembly that is installed in the global assembly cache.</span></span>

<span data-ttu-id="d61fa-339">Чтобы добавить или изменить файлы в `$pshome\Modules` каталоге, запустите PowerShell с параметром **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="d61fa-339">To add or change files in the `$pshome\Modules` directory, start PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="d61fa-340">В PowerShell 2,0 многие параметры `New-ModuleManifest` были обязательными, даже если они не требовались в манифесте модуля.</span><span class="sxs-lookup"><span data-stu-id="d61fa-340">In PowerShell 2.0, many parameters of `New-ModuleManifest` were mandatory, even though they weren't required in a module manifest.</span></span> <span data-ttu-id="d61fa-341">Начиная с PowerShell 3,0, только параметр **path** является обязательным.</span><span class="sxs-lookup"><span data-stu-id="d61fa-341">Beginning in PowerShell 3.0, only the **Path** parameter is mandatory.</span></span>

<span data-ttu-id="d61fa-342">Сеанс — это экземпляр среды выполнения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d61fa-342">A session is an instance of the PowerShell execution environment.</span></span> <span data-ttu-id="d61fa-343">Сеанс может иметь одно или несколько состояний.</span><span class="sxs-lookup"><span data-stu-id="d61fa-343">A session can have one or more session states.</span></span> <span data-ttu-id="d61fa-344">По умолчанию сеанс имеет только глобальное состояние сеанса, но каждый импортированный модуль имеет собственное состояние сеанса.</span><span class="sxs-lookup"><span data-stu-id="d61fa-344">By default, a session has only a global session state, but each imported module has its own session state.</span></span> <span data-ttu-id="d61fa-345">Состояния сеансов позволяют выполнять команды в модуле, не влияя на глобальное состояние сеанса.</span><span class="sxs-lookup"><span data-stu-id="d61fa-345">Session states allow the commands in a module to run without affecting the global session state.</span></span>

<span data-ttu-id="d61fa-346">Состояние сеанса вызывающего объекта — это состояние сеанса, в котором импортируется модуль.</span><span class="sxs-lookup"><span data-stu-id="d61fa-346">The caller's session state is the session state into which a module is imported.</span></span> <span data-ttu-id="d61fa-347">Как правило, он ссылается на глобальное состояние сеанса, но когда модуль импортирует вложенные модули, вызывающий объект является модулем, а состояние сеанса вызывающего объекта — состояние сеанса модуля.</span><span class="sxs-lookup"><span data-stu-id="d61fa-347">Typically, it refers to the global session state, but when a module imports nested modules, the caller is the module and the caller's session state is the module's session state.</span></span>

## <span data-ttu-id="d61fa-348">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="d61fa-348">RELATED LINKS</span></span>

[<span data-ttu-id="d61fa-349">Export-ModuleMember</span><span class="sxs-lookup"><span data-stu-id="d61fa-349">Export-ModuleMember</span></span>](Export-ModuleMember.md)

[<span data-ttu-id="d61fa-350">Get-Module</span><span class="sxs-lookup"><span data-stu-id="d61fa-350">Get-Module</span></span>](Get-Module.md)

[<span data-ttu-id="d61fa-351">Import-Module</span><span class="sxs-lookup"><span data-stu-id="d61fa-351">Import-Module</span></span>](Import-Module.md)

[<span data-ttu-id="d61fa-352">New-Module</span><span class="sxs-lookup"><span data-stu-id="d61fa-352">New-Module</span></span>](New-Module.md)

[<span data-ttu-id="d61fa-353">Remove-Module</span><span class="sxs-lookup"><span data-stu-id="d61fa-353">Remove-Module</span></span>](Remove-Module.md)

[<span data-ttu-id="d61fa-354">Test-ModuleManifest</span><span class="sxs-lookup"><span data-stu-id="d61fa-354">Test-ModuleManifest</span></span>](Test-ModuleManifest.md)

[<span data-ttu-id="d61fa-355">about_Modules</span><span class="sxs-lookup"><span data-stu-id="d61fa-355">about_Modules</span></span>](./About/about_Modules.md)

