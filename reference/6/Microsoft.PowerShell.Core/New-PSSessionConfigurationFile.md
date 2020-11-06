---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/24/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-pssessionconfigurationfile?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSSessionConfigurationFile
ms.openlocfilehash: 1045c22cdaadb9fe1a45ec01ea86d5d8a276b05a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228870"
---
# <span data-ttu-id="99726-103">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="99726-103">New-PSSessionConfigurationFile</span></span>

## <span data-ttu-id="99726-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="99726-104">SYNOPSIS</span></span>
<span data-ttu-id="99726-105">Создает файл, определяющий конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="99726-105">Creates a file that defines a session configuration.</span></span>

## <span data-ttu-id="99726-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="99726-106">SYNTAX</span></span>

```
New-PSSessionConfigurationFile [-Path] <String> [-SchemaVersion <Version>] [-Guid <Guid>]
 [-Author <String>] [-Description <String>] [-CompanyName <String>] [-Copyright <String>]
 [-SessionType <SessionType>] [-TranscriptDirectory <String>] [-RunAsVirtualAccount]
 [-RunAsVirtualAccountGroups <String[]>] [-MountUserDrive] [-UserDriveMaximumSize <Int64>]
 [-GroupManagedServiceAccount <String>] [-ScriptsToProcess <String[]>]
 [-RoleDefinitions <IDictionary>] [-RequiredGroups <IDictionary>] [-LanguageMode <PSLanguageMode>]
 [-ExecutionPolicy <ExecutionPolicy>] [-PowerShellVersion <Version>] [-ModulesToImport <Object[]>]
 [-VisibleAliases <String[]>] [-VisibleCmdlets <Object[]>] [-VisibleFunctions <Object[]>]
 [-VisibleExternalCommands <String[]>] [-VisibleProviders <String[]>]
 [-AliasDefinitions <IDictionary[]>] [-FunctionDefinitions <IDictionary[]>]
 [-VariableDefinitions <Object>] [-EnvironmentVariables <IDictionary>] [-TypesToProcess <String[]>]
 [-FormatsToProcess <String[]>] [-AssembliesToLoad <String[]>] [-Full] [<CommonParameters>]
```

## <span data-ttu-id="99726-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="99726-107">DESCRIPTION</span></span>

<span data-ttu-id="99726-108">`New-PSSessionConfigurationFile`Командлет создает файл параметров, определяющих конфигурацию сеанса и среду сеансов, которые создаются с помощью конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="99726-108">The `New-PSSessionConfigurationFile` cmdlet creates a file of settings that define a session configuration and the environment of sessions that are created by using the session configuration.</span></span>
<span data-ttu-id="99726-109">Чтобы использовать файл в конфигурации сеанса, используйте параметр **path** `Register-PSSessionConfiguration` `Set-PSSessionConfiguration` командлетов или.</span><span class="sxs-lookup"><span data-stu-id="99726-109">To use the file in a session configuration, use the **Path** parameter of the `Register-PSSessionConfiguration` or `Set-PSSessionConfiguration` cmdlets.</span></span>

<span data-ttu-id="99726-110">Создаваемый файл конфигурации сеанса `New-PSSessionConfigurationFile` является текстовым файлом, доступным для чтения, который содержит хэш-таблицу свойств и значений конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="99726-110">The session configuration file that `New-PSSessionConfigurationFile` creates is a human-readable text file that contains a hash table of the session configuration properties and values.</span></span> <span data-ttu-id="99726-111">Файл имеет `.pssc` расширение имени файла.</span><span class="sxs-lookup"><span data-stu-id="99726-111">The file has a `.pssc` filename extension.</span></span>

<span data-ttu-id="99726-112">Все параметры `New-PSSessionConfigurationFile` являются необязательными, за исключением параметра **path** .</span><span class="sxs-lookup"><span data-stu-id="99726-112">All parameters of `New-PSSessionConfigurationFile` are optional, except for the **Path** parameter.</span></span>
<span data-ttu-id="99726-113">Если параметр пропущен, соответствующий ключ в файле конфигурации сеанса преобразуется в комментарий (за исключением указанных в описании параметра).</span><span class="sxs-lookup"><span data-stu-id="99726-113">If you omit a parameter, the corresponding key in the session configuration file is commented-out, except where noted in the parameter description.</span></span>

<span data-ttu-id="99726-114">Конфигурация сеанса, также известная как конечная точка, представляет собой набор параметров на локальном компьютере, определяющий среду для сеансов PowerShell ( **PSSession** ), которые подключаются к компьютеру.</span><span class="sxs-lookup"><span data-stu-id="99726-114">A session configuration, also known as an endpoint, is a collection of settings on the local computer that define the environment for PowerShell sessions ( **PSSessions** ) that connect to the computer.</span></span> <span data-ttu-id="99726-115">Все **PSSession** используют конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="99726-115">All **PSSessions** use a session configuration.</span></span> <span data-ttu-id="99726-116">Чтобы указать определенную конфигурацию сеанса, используйте параметр **configurationName** командлетов, которые создают сеанс, например `New-PSSession` командлет.</span><span class="sxs-lookup"><span data-stu-id="99726-116">To specify a particular session configuration, use the **ConfigurationName** parameter of cmdlets that create a session, such as the `New-PSSession` cmdlet.</span></span>

<span data-ttu-id="99726-117">Файл конфигурации сеанса позволяет легко определить конфигурацию сеанса без сложных скриптов или сборок кода.</span><span class="sxs-lookup"><span data-stu-id="99726-117">A session configuration file makes it easy to define a session configuration without complex scripts or code assemblies.</span></span> <span data-ttu-id="99726-118">Параметры в файле используются с необязательным сценарием запуска и всеми сборками в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="99726-118">The settings in the file are used with the optional startup script and any assemblies in the session configuration.</span></span>

<span data-ttu-id="99726-119">Дополнительные сведения о конфигурациях сеансов и файлах конфигурации сеанса см. в разделе [about_Session_Configurations](About/about_Session_Configurations.md) и [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span><span class="sxs-lookup"><span data-stu-id="99726-119">For more information about session configurations and session configuration files, see [about_Session_Configurations](About/about_Session_Configurations.md) and [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span></span>

<span data-ttu-id="99726-120">Этот командлет появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="99726-120">This cmdlet was introduced in PowerShell 3.0.</span></span>

## <span data-ttu-id="99726-121">Примеры</span><span class="sxs-lookup"><span data-stu-id="99726-121">EXAMPLES</span></span>

### <span data-ttu-id="99726-122">Пример 1. Создание и использование сеанса на языке</span><span class="sxs-lookup"><span data-stu-id="99726-122">Example 1: Creating and using a NoLanguage session</span></span>

<span data-ttu-id="99726-123">В этом примере показано, как создать и увидеть последствия использования сеанса без языка.</span><span class="sxs-lookup"><span data-stu-id="99726-123">This example show how to create and the effects of using a no-language session.</span></span>

<span data-ttu-id="99726-124">Для этого нужно выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="99726-124">The steps include:</span></span>

1. <span data-ttu-id="99726-125">Создайте новый файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="99726-125">Create a new configuration file.</span></span>
1. <span data-ttu-id="99726-126">Зарегистрируйте конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="99726-126">Register the configuration.</span></span>
1. <span data-ttu-id="99726-127">Создайте новый сеанс, использующий конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="99726-127">Create a new session that uses the configuration.</span></span>
1. <span data-ttu-id="99726-128">Выполните команды в этом новом сеансе.</span><span class="sxs-lookup"><span data-stu-id="99726-128">Run commands in that new session.</span></span>

<span data-ttu-id="99726-129">Чтобы выполнить команды в этом примере, запустите PowerShell с параметром Запуск от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="99726-129">To run the commands in this example, start PowerShell by using the Run as administrator option.</span></span> <span data-ttu-id="99726-130">Этот параметр необходим для выполнения `Register-PSSessionConfiguration` командлета.</span><span class="sxs-lookup"><span data-stu-id="99726-130">This option is required to run the `Register-PSSessionConfiguration` cmdlet.</span></span>

```powershell
New-PSSessionConfigurationFile -Path .\NoLanguage.pssc -LanguageMode NoLanguage
Register-PSSessionConfiguration -Path .\NoLanguage.pssc -Name NoLanguage -Force
$NoLanguageSession = New-PSSession -ComputerName Srv01 -ConfigurationName NoLanguage
Invoke-Command -Session $NoLanguageSession -ScriptBlock {
  if ((Get-Date) -lt '1January2099') {'Before'} else {'After'}
}
```

```Output
The syntax is not supported by this runspace. This might be because it is in no-language mode.
    + CategoryInfo          : ParserError: (if ((Get-Date) ...') {'Before'}  :String) [], ParseException
    + FullyQualifiedErrorId : ScriptsNotAllowed
    + PSComputerName        : localhost
```

<span data-ttu-id="99726-131">В этом примере `Invoke-Command` происходит сбой, так как для **лангуажемоде** задано значение " **неязыковый** ".</span><span class="sxs-lookup"><span data-stu-id="99726-131">In this example, the `Invoke-Command` fails because the **LanguageMode** is set to **NoLanguage** .</span></span>

### <span data-ttu-id="99726-132">Пример 2. Создание и использование сеанса Рестриктедлангуаже</span><span class="sxs-lookup"><span data-stu-id="99726-132">Example 2: Creating and using a RestrictedLanguage session</span></span>

<span data-ttu-id="99726-133">В этом примере показано, как создать и увидеть последствия использования сеанса без языка.</span><span class="sxs-lookup"><span data-stu-id="99726-133">This example show how to create and the effects of using a no-language session.</span></span>

<span data-ttu-id="99726-134">Для этого нужно выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="99726-134">The steps include:</span></span>

1. <span data-ttu-id="99726-135">Создайте новый файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="99726-135">Create a new configuration file.</span></span>
1. <span data-ttu-id="99726-136">Зарегистрируйте конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="99726-136">Register the configuration.</span></span>
1. <span data-ttu-id="99726-137">Создайте новый сеанс, использующий конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="99726-137">Create a new session that uses the configuration.</span></span>
1. <span data-ttu-id="99726-138">Выполните команды в этом новом сеансе.</span><span class="sxs-lookup"><span data-stu-id="99726-138">Run commands in that new session.</span></span>

<span data-ttu-id="99726-139">Чтобы выполнить команды в этом примере, запустите PowerShell с параметром Запуск от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="99726-139">To run the commands in this example, start PowerShell by using the Run as administrator option.</span></span> <span data-ttu-id="99726-140">Этот параметр необходим для выполнения `Register-PSSessionConfiguration` командлета.</span><span class="sxs-lookup"><span data-stu-id="99726-140">This option is required to run the `Register-PSSessionConfiguration` cmdlet.</span></span>

```powershell
New-PSSessionConfigurationFile -Path .\NoLanguage.pssc -LanguageMode RestrictedLanguage
Register-PSSessionConfiguration -Path .\NoLanguage.pssc -Name RestrictedLanguage -Force
$RestrictedSession = New-PSSession -ComputerName Srv01 -ConfigurationName RestrictedLanguage
Invoke-Command -Session $RestrictedSession -ScriptBlock {
  if ((Get-Date) -lt '1January2099') {'Before'} else {'After'}
}
```

```Output
Before
```

<span data-ttu-id="99726-141">В этом примере объект `Invoke-Command` выполняется, так как для **лангуажемоде** задано значение **рестриктедлангуаже** .</span><span class="sxs-lookup"><span data-stu-id="99726-141">In this example, the `Invoke-Command` succeeds because the **LanguageMode** is set to **RestrictedLanguage** .</span></span>

### <span data-ttu-id="99726-142">Пример 3. Изменение файла конфигурации сеанса</span><span class="sxs-lookup"><span data-stu-id="99726-142">Example 3: Changing a Session Configuration File</span></span>

<span data-ttu-id="99726-143">В этом примере показано, как изменить файл конфигурации сеанса, используемый в существующем сеансе с именем «ITTasks».</span><span class="sxs-lookup"><span data-stu-id="99726-143">This example shows how to change the session configuration file that is used in an existing session named "ITTasks".</span></span> <span data-ttu-id="99726-144">Ранее в этих сеансах были только основные модули и внутренний модуль **ITTasks** .</span><span class="sxs-lookup"><span data-stu-id="99726-144">Previously, these sessions had only the core modules and an internal **ITTasks** module.</span></span> <span data-ttu-id="99726-145">Администратор хочет добавить модуль **PSScheduledJob** в сеансы, созданные с помощью конфигурации сеанса ITTasks.</span><span class="sxs-lookup"><span data-stu-id="99726-145">The administrator wants to add the **PSScheduledJob** module to sessions created by using the ITTasks session configuration.</span></span>

```powershell
New-PSSessionConfigurationFile -Path .\New-ITTasks.pssc -ModulesToImport Microsoft*, ITTasks, PSScheduledJob
Set-PSSessionConfiguration -Name ITTasks -Path .\New-ITTasks.pssc
```

<span data-ttu-id="99726-146">`New-PSSessionConfigurationFile`Командлет для создания файла конфигурации сеанса, который импортирует необходимые модули.</span><span class="sxs-lookup"><span data-stu-id="99726-146">The `New-PSSessionConfigurationFile` cmdlet to create a session configuration file that imports the required modules.</span></span> <span data-ttu-id="99726-147">`Set-PSSessionConfiguration`Командлет заменяет текущий файл конфигурации новым.</span><span class="sxs-lookup"><span data-stu-id="99726-147">The `Set-PSSessionConfiguration` cmdlet replaces the current configuration file with the new one.</span></span> <span data-ttu-id="99726-148">Эта новая конфигурация влияет только на новые сеансы, созданные после изменения.</span><span class="sxs-lookup"><span data-stu-id="99726-148">This new configuration only affects new sessions created after the change.</span></span>
<span data-ttu-id="99726-149">Существующие сеансы "ITTasks" не затрагиваются.</span><span class="sxs-lookup"><span data-stu-id="99726-149">Existing "ITTasks" sessions are not affected.</span></span>

### <span data-ttu-id="99726-150">Пример 4. Редактирование файла конфигурации сеанса</span><span class="sxs-lookup"><span data-stu-id="99726-150">Example 4: Editing a Session Configuration File</span></span>

<span data-ttu-id="99726-151">В этом примере показано, как изменить конфигурацию сеанса путем редактирования копии конфигурации активного сеанса из файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="99726-151">This example shows how to change a session configuration by editing the active session configuration copy of the configuration file.</span></span> <span data-ttu-id="99726-152">Чтобы изменить копию конфигурации сеанса файла конфигурации, необходимо иметь полный доступ к файлу.</span><span class="sxs-lookup"><span data-stu-id="99726-152">To modify the session configuration copy of the configuration file, you must have full control access to the file.</span></span> <span data-ttu-id="99726-153">Для этого может потребоваться изменить разрешения для файла.</span><span class="sxs-lookup"><span data-stu-id="99726-153">This may require you to change the permissions on the file.</span></span>

<span data-ttu-id="99726-154">В этом сценарии мы хотим добавить новый псевдоним для `Select-String` командлета, изменив активный файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="99726-154">In this scenario, we want to add a new alias for the `Select-String` cmdlet by editing the active configuration file.</span></span>

<span data-ttu-id="99726-155">Приведенный ниже пример кода выполняет следующие действия для внесения этого изменения:</span><span class="sxs-lookup"><span data-stu-id="99726-155">The example code below performs the following steps to make this change:</span></span>

1. <span data-ttu-id="99726-156">Получите путь к файлу конфигурации для сеанса Итконфиг.</span><span class="sxs-lookup"><span data-stu-id="99726-156">Get the configuration file path for the ITConfig session.</span></span>
1. <span data-ttu-id="99726-157">Пользователь редактирует файл конфигурации с помощью **Notepad.exe** для изменения значения **алиасдефинитионс** следующим образом: `AliasDefinitions = @(@{Name='slst';Value='Select-String'})` .</span><span class="sxs-lookup"><span data-stu-id="99726-157">The user edits the configuration file using **Notepad.exe** to change the **AliasDefinitions** value as follows: `AliasDefinitions = @(@{Name='slst';Value='Select-String'})`.</span></span>
1. <span data-ttu-id="99726-158">Протестируйте обновленный файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="99726-158">Test the updated configuration file.</span></span>

```powershell
$ITConfig = Get-PSSessionConfiguration -Name ITConfig
notepad.exe $ITConfig.ConfigFilePath
Test-PSSessionConfigurationFile -Path $ITConfig.ConfigFilePath
```

```Output
True
```

<span data-ttu-id="99726-159">Используйте параметр **verbose** с для, `Test-PSSessionConfigurationFile` чтобы отобразить обнаруженные ошибки.</span><span class="sxs-lookup"><span data-stu-id="99726-159">Use the **Verbose** parameter with `Test-PSSessionConfigurationFile` to display any errors that are detected.</span></span> <span data-ttu-id="99726-160">Командлет возвращает, `$True` Если в файле не обнаружены ошибки.</span><span class="sxs-lookup"><span data-stu-id="99726-160">The cmdlet returns `$True` if no errors are detected in the file.</span></span>

### <span data-ttu-id="99726-161">Пример 5. Создание образца файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="99726-161">Example 5: Create a sample configuration file</span></span>

<span data-ttu-id="99726-162">В этом примере показана `New-PSSessionConfigurationFile` команда, использующая все параметры командлета.</span><span class="sxs-lookup"><span data-stu-id="99726-162">This example shows a `New-PSSessionConfigurationFile` command that uses all the cmdlet parameters.</span></span>
<span data-ttu-id="99726-163">Она включена в пример, чтобы показать правильный входной формат для каждого параметра.</span><span class="sxs-lookup"><span data-stu-id="99726-163">It is included to show the correct input format for each parameter.</span></span>

<span data-ttu-id="99726-164">Получившийся файл SampleFile.pssc отображается в выходных данных.</span><span class="sxs-lookup"><span data-stu-id="99726-164">The resulting SampleFile.pssc is displayed in the output.</span></span>

```powershell
$configSettings = @{
    Path = '.\SampleFile.pssc'
    SchemaVersion = '1.0.0.0'
    Author = 'User01'
    Copyright = '(c) Fabrikam Corporation. All rights reserved.'
    CompanyName = 'Fabrikam Corporation'
    Description = 'This is a sample file.'
    ExecutionPolicy = 'AllSigned'
    PowerShellVersion = '3.0'
    LanguageMode = 'FullLanguage'
    SessionType = 'Default'
    EnvironmentVariables = @{TESTSHARE='\\Test2\Test'}
    ModulesToImport = @{ModuleName='PSScheduledJob'; ModuleVersion='1.0.0.0'; GUID='50cdb55f-5ab7-489f-9e94-4ec21ff51e59'},'PSDiagnostics'
    AssembliesToLoad = 'System.Web.Services','FSharp.Compiler.CodeDom.dll'
    TypesToProcess = 'Types1.ps1xml','Types2.ps1xml'
    FormatsToProcess = 'CustomFormats.ps1xml'
    ScriptsToProcess = 'Get-Inputs.ps1'
    AliasDefinitions = @{Name='hlp';Value='Get-Help';Description='Gets help.';Options='AllScope'},
        @{Name='Update';Value='Update-Help';Description='Updates help';Options='ReadOnly'}
    FunctionDefinitions = @{Name='Get-Function';ScriptBlock={Get-Command -CommandType Function};Options='ReadOnly'}
    VariableDefinitions = @{Name='WarningPreference';Value='SilentlyContinue'}
    VisibleAliases = 'c*','g*','i*','s*'
    VisibleCmdlets = 'Get*'
    VisibleFunctions = 'Get*'
    VisibleProviders = 'FileSystem','Function','Variable'
    RunAsVirtualAccount = $true
    RunAsVirtualAccountGroups = 'Backup Operators'
}
New-PSSessionConfigurationFile @configSettings
Get-Content SampleFile.pssc
```

```Output
@{

# Version number of the schema used for this document
SchemaVersion = '1.0.0.0'

# ID used to uniquely identify this document
GUID = '1caeff7f-27ca-4360-97cf-37846f594235'

# Author of this document
Author = 'User01'

# Description of the functionality provided by these settings
Description = 'This is a sample file.'

# Company associated with this document
CompanyName = 'Fabrikam Corporation'

# Copyright statement for this document
Copyright = '(c) Fabrikam Corporation. All rights reserved.'

# Session type defaults to apply for this session configuration. Can be 'RestrictedRemoteServer' (recommended), 'Empty', or 'Default'
SessionType = 'Default'

# Directory to place session transcripts for this session configuration
# TranscriptDirectory = 'C:\Transcripts\'

# Whether to run this session configuration as the machine's (virtual) administrator account
RunAsVirtualAccount = $true

# Groups associated with machine's (virtual) administrator account
RunAsVirtualAccountGroups = 'Backup Operators'

# Scripts to run when applied to a session
ScriptsToProcess = 'Get-Inputs.ps1'

# User roles (security groups), and the role capabilities that should be applied to them when applied to a session
# RoleDefinitions = @{ 'CONTOSO\SqlAdmins' = @{ RoleCapabilities = 'SqlAdministration' }; 'CONTOSO\SqlManaged' = @{ RoleCapabilityFiles = 'C:\RoleCapability\SqlManaged.psrc' }; 'CONTOSO\ServerMonitors' = @{ VisibleCmdlets = 'Get-Process' } }

# Language mode to apply when applied to a session. Can be 'NoLanguage' (recommended), 'RestrictedLanguage', 'ConstrainedLanguage', or 'FullLanguage'
LanguageMode = 'FullLanguage'

# Execution policy to apply when applied to a session
ExecutionPolicy = 'AllSigned'

# Version of the PowerShell engine to use when applied to a session
PowerShellVersion = '3.0'

# Modules to import when applied to a session
ModulesToImport = @{
    'GUID' = '50cdb55f-5ab7-489f-9e94-4ec21ff51e59'
    'ModuleName' = 'PSScheduledJob'
    'ModuleVersion' = '1.0.0.0' }, 'PSDiagnostics'

# Aliases to make visible when applied to a session
VisibleAliases = 'c*', 'g*', 'i*', 's*'

# Cmdlets to make visible when applied to a session
VisibleCmdlets = 'Get*'

# Functions to make visible when applied to a session
VisibleFunctions = 'Get*'

# Providers to make visible when applied to a session
VisibleProviders = 'FileSystem', 'Function', 'Variable'

# Aliases to be defined when applied to a session
AliasDefinitions = @{
    'Description' = 'Gets help.'
    'Name' = 'hlp'
    'Options' = 'AllScope'
    'Value' = 'Get-Help' }, @{
    'Description' = 'Updates help'
    'Name' = 'Update'
    'Options' = 'ReadOnly'
    'Value' = 'Update-Help' }

# Functions to define when applied to a session
FunctionDefinitions = @{
    'Name' = 'Get-Function'
    'Options' = 'ReadOnly'
    'ScriptBlock' = {Get-Command -CommandType Function} }

# Variables to define when applied to a session
VariableDefinitions = @{
    'Name' = 'WarningPreference'
    'Value' = 'SilentlyContinue' }

# Environment variables to define when applied to a session
EnvironmentVariables = @{
    'TESTSHARE' = '\\Test2\Test' }

# Type files (.ps1xml) to load when applied to a session
TypesToProcess = 'Types1.ps1xml', 'Types2.ps1xml'

# Format files (.ps1xml) to load when applied to a session
FormatsToProcess = 'CustomFormats.ps1xml'

# Assemblies to load when applied to a session
AssembliesToLoad = 'System.Web.Services', 'FSharp.Compiler.CodeDom.dll'

}
```

## <span data-ttu-id="99726-165">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="99726-165">PARAMETERS</span></span>

### <span data-ttu-id="99726-166">-AliasDefinitions</span><span class="sxs-lookup"><span data-stu-id="99726-166">-AliasDefinitions</span></span>

<span data-ttu-id="99726-167">Добавляет указанные псевдонимы сеансы, использующие конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="99726-167">Adds the specified aliases to sessions that use the session configuration.</span></span> <span data-ttu-id="99726-168">Введите хэш-таблицу со следующими разделами:</span><span class="sxs-lookup"><span data-stu-id="99726-168">Enter a hash table with the following keys:</span></span>

- <span data-ttu-id="99726-169">Name — имя псевдонима.</span><span class="sxs-lookup"><span data-stu-id="99726-169">Name - Name of the alias.</span></span> <span data-ttu-id="99726-170">Этот раздел обязателен.</span><span class="sxs-lookup"><span data-stu-id="99726-170">This key is required.</span></span>
- <span data-ttu-id="99726-171">Value — команда, которую представляет псевдоним.</span><span class="sxs-lookup"><span data-stu-id="99726-171">Value - The command that the alias represents.</span></span> <span data-ttu-id="99726-172">Этот раздел обязателен.</span><span class="sxs-lookup"><span data-stu-id="99726-172">This key is required.</span></span>
- <span data-ttu-id="99726-173">Описание — текстовая строка, описывающая псевдоним.</span><span class="sxs-lookup"><span data-stu-id="99726-173">Description - A text string that describes the alias.</span></span> <span data-ttu-id="99726-174">Этот раздел необязателен.</span><span class="sxs-lookup"><span data-stu-id="99726-174">This key is optional.</span></span>
- <span data-ttu-id="99726-175">Параметры — параметры псевдонимов.</span><span class="sxs-lookup"><span data-stu-id="99726-175">Options - Alias options.</span></span> <span data-ttu-id="99726-176">Этот раздел необязателен.</span><span class="sxs-lookup"><span data-stu-id="99726-176">This key is optional.</span></span> <span data-ttu-id="99726-177">Значение по умолчанию — **None** .</span><span class="sxs-lookup"><span data-stu-id="99726-177">The default value is **None** .</span></span> <span data-ttu-id="99726-178">Допустимые значения для этого параметра: None, ReadOnly, Constant, private или AllScope.</span><span class="sxs-lookup"><span data-stu-id="99726-178">The acceptable values for this parameter are: None, ReadOnly, Constant, Private, or AllScope.</span></span>

<span data-ttu-id="99726-179">Пример: `@{Name='hlp';Value='Get-Help';Description='Gets help';Options='ReadOnly'}`</span><span class="sxs-lookup"><span data-stu-id="99726-179">For example: `@{Name='hlp';Value='Get-Help';Description='Gets help';Options='ReadOnly'}`</span></span>

```yaml
Type: System.Collections.IDictionary[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="99726-180">-AssembliesToLoad</span><span class="sxs-lookup"><span data-stu-id="99726-180">-AssembliesToLoad</span></span>

<span data-ttu-id="99726-181">Задает сборки для загрузки в сеансы, которые используют конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="99726-181">Specifies the assemblies to load into the sessions that use the session configuration.</span></span>

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

### <span data-ttu-id="99726-182">-Author</span><span class="sxs-lookup"><span data-stu-id="99726-182">-Author</span></span>

<span data-ttu-id="99726-183">Указывает автора конфигурации сеанса или файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="99726-183">Specifies the author of the session configuration or the configuration file.</span></span> <span data-ttu-id="99726-184">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="99726-184">The default is the current user.</span></span> <span data-ttu-id="99726-185">Значение этого параметра отображается в файле конфигурации сеанса, но не является свойством объекта конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="99726-185">The value of this parameter is visible in the session configuration file, but it is not a property of the session configuration object.</span></span>

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

### <span data-ttu-id="99726-186">-CompanyName</span><span class="sxs-lookup"><span data-stu-id="99726-186">-CompanyName</span></span>

<span data-ttu-id="99726-187">Указывает компанию, которая создала конфигурацию сеанса или файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="99726-187">Specifies the company that created the session configuration or the configuration file.</span></span> <span data-ttu-id="99726-188">Значение по умолчанию — **Unknown** .</span><span class="sxs-lookup"><span data-stu-id="99726-188">The default value is **Unknown** .</span></span> <span data-ttu-id="99726-189">Значение этого параметра отображается в файле конфигурации сеанса, но не является свойством объекта конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="99726-189">The value of this parameter is visible in the session configuration file, but it is not a property of the session configuration object.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Unknown
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="99726-190">-Copyright</span><span class="sxs-lookup"><span data-stu-id="99726-190">-Copyright</span></span>

<span data-ttu-id="99726-191">Указывает авторские права на файл конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="99726-191">Specifies a copyright the session configuration file.</span></span> <span data-ttu-id="99726-192">Значение этого параметра отображается в файле конфигурации сеанса, но не является свойством объекта конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="99726-192">The value of this parameter is visible in the session configuration file, but it is not a property of the session configuration object.</span></span>

<span data-ttu-id="99726-193">Если опустить этот параметр, `New-PSSessionConfigurationFile` создает заявление об авторских правах с помощью значения параметра **Author** .</span><span class="sxs-lookup"><span data-stu-id="99726-193">If you omit this parameter, `New-PSSessionConfigurationFile` generates a copyright statement by using the value of the **Author** parameter.</span></span>

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

### <span data-ttu-id="99726-194">-Description</span><span class="sxs-lookup"><span data-stu-id="99726-194">-Description</span></span>

<span data-ttu-id="99726-195">Задает описание конфигурации сеанса или файла конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="99726-195">Specifies a description of the session configuration or the session configuration file.</span></span> <span data-ttu-id="99726-196">Значение этого параметра отображается в файле конфигурации сеанса, но не является свойством объекта конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="99726-196">The value of this parameter is visible in the session configuration file, but it is not a property of the session configuration object.</span></span>

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

### <span data-ttu-id="99726-197">-EnvironmentVariables</span><span class="sxs-lookup"><span data-stu-id="99726-197">-EnvironmentVariables</span></span>

<span data-ttu-id="99726-198">Добавляет переменные среды в сеанс.</span><span class="sxs-lookup"><span data-stu-id="99726-198">Adds environment variables to the session.</span></span> <span data-ttu-id="99726-199">Введите хэш-таблицу, в которой разделами являются имена переменных среды, а значениями — значения переменных среды.</span><span class="sxs-lookup"><span data-stu-id="99726-199">Enter a hash table in which the keys are the environment variable names and the values are the environment variable values.</span></span>

<span data-ttu-id="99726-200">Пример: `EnvironmentVariables=@{TestShare='\\Server01\TestShare'}`</span><span class="sxs-lookup"><span data-stu-id="99726-200">For example: `EnvironmentVariables=@{TestShare='\\Server01\TestShare'}`</span></span>

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="99726-201">-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="99726-201">-ExecutionPolicy</span></span>

<span data-ttu-id="99726-202">Указывает политику выполнения сеансов, использующих конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="99726-202">Specifies the execution policy of sessions that use the session configuration.</span></span> <span data-ttu-id="99726-203">Если опустить этот параметр, значение ключа **ExecutionPolicy** в файле конфигурации сеанса будет **ограничено** .</span><span class="sxs-lookup"><span data-stu-id="99726-203">If you omit this parameter, the value of the **ExecutionPolicy** key in the session configuration file is **Restricted** .</span></span> <span data-ttu-id="99726-204">Дополнительные сведения о политиках выполнения в PowerShell см. в разделе [about_Execution_Policies](about/about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="99726-204">For information about execution policies in PowerShell, see [about_Execution_Policies](about/about_Execution_Policies.md).</span></span>

```yaml
Type: Microsoft.PowerShell.ExecutionPolicy
Parameter Sets: (All)
Aliases:
Accepted values: Unrestricted, RemoteSigned, AllSigned, Restricted, Default, Bypass, Undefined

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="99726-205">-FormatsToProcess</span><span class="sxs-lookup"><span data-stu-id="99726-205">-FormatsToProcess</span></span>

<span data-ttu-id="99726-206">Указывает файлы форматирования (PS1XML-файлы), выполняющиеся в сеансах, которые используют конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="99726-206">Specifies the formatting files (.ps1xml) that run in sessions that use the session configuration.</span></span>
<span data-ttu-id="99726-207">Значение этого параметра должно быть полным или абсолютным путем к файлам форматирования.</span><span class="sxs-lookup"><span data-stu-id="99726-207">The value of this parameter must be a full or absolute path of the formatting files.</span></span>

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

### <span data-ttu-id="99726-208">-Full</span><span class="sxs-lookup"><span data-stu-id="99726-208">-Full</span></span>

<span data-ttu-id="99726-209">Указывает, что эта операция включает все возможные свойства конфигурации в файле конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="99726-209">Indicates that this operation includes all possible configuration properties in the session configuration file.</span></span>

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

### <span data-ttu-id="99726-210">-FunctionDefinitions</span><span class="sxs-lookup"><span data-stu-id="99726-210">-FunctionDefinitions</span></span>

<span data-ttu-id="99726-211">Добавляет в сеансы указанные функции, использующие конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="99726-211">Adds the specified functions to sessions that use the session configuration.</span></span> <span data-ttu-id="99726-212">Введите хэш-таблицу со следующими разделами:</span><span class="sxs-lookup"><span data-stu-id="99726-212">Enter a hash table with the following keys:</span></span>

- <span data-ttu-id="99726-213">Name — имя функции.</span><span class="sxs-lookup"><span data-stu-id="99726-213">Name - Name of the function.</span></span> <span data-ttu-id="99726-214">Этот раздел обязателен.</span><span class="sxs-lookup"><span data-stu-id="99726-214">This key is required.</span></span>
- <span data-ttu-id="99726-215">ScriptBlock — тело функции.</span><span class="sxs-lookup"><span data-stu-id="99726-215">ScriptBlock - Function body.</span></span> <span data-ttu-id="99726-216">Введите блок сценария.</span><span class="sxs-lookup"><span data-stu-id="99726-216">Enter a script block.</span></span> <span data-ttu-id="99726-217">Этот раздел обязателен.</span><span class="sxs-lookup"><span data-stu-id="99726-217">This key is required.</span></span>
- <span data-ttu-id="99726-218">Параметры — параметры функции.</span><span class="sxs-lookup"><span data-stu-id="99726-218">Options - Function options.</span></span> <span data-ttu-id="99726-219">Этот раздел необязателен.</span><span class="sxs-lookup"><span data-stu-id="99726-219">This key is optional.</span></span> <span data-ttu-id="99726-220">Значение по умолчанию — **None** .</span><span class="sxs-lookup"><span data-stu-id="99726-220">The default value is **None** .</span></span> <span data-ttu-id="99726-221">Допустимые значения для этого параметра: None, ReadOnly, Constant, private или AllScope.</span><span class="sxs-lookup"><span data-stu-id="99726-221">The acceptable values for this parameter are: None, ReadOnly, Constant, Private, or AllScope.</span></span>

<span data-ttu-id="99726-222">Пример: `@{Name='Get-PowerShellProcess';ScriptBlock={Get-Process PowerShell};Options='AllScope'}`</span><span class="sxs-lookup"><span data-stu-id="99726-222">For example: `@{Name='Get-PowerShellProcess';ScriptBlock={Get-Process PowerShell};Options='AllScope'}`</span></span>

```yaml
Type: System.Collections.IDictionary[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="99726-223">-Граупманажедсервицеаккаунт</span><span class="sxs-lookup"><span data-stu-id="99726-223">-GroupManagedServiceAccount</span></span>

<span data-ttu-id="99726-224">Настраивает сеансы, использующие эту конфигурацию сеанса, для запуска в контексте указанной групповой управляемой учетной записи службы.</span><span class="sxs-lookup"><span data-stu-id="99726-224">Configures sessions using this session configuration to run under the context of the specified Group Managed Service Account.</span></span> <span data-ttu-id="99726-225">Компьютер, на котором зарегистрирована эта конфигурация сеанса, должен иметь разрешение на запрос пароля gMSA для успешного создания сеансов.</span><span class="sxs-lookup"><span data-stu-id="99726-225">The machine where this session configuration is registered must have permission to request the gMSA password in order for sessions to be created successfully.</span></span> <span data-ttu-id="99726-226">Это поле нельзя использовать с параметром **RunAsVirtualAccount** .</span><span class="sxs-lookup"><span data-stu-id="99726-226">This field cannot be used with the **RunAsVirtualAccount** parameter.</span></span>

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

### <span data-ttu-id="99726-227">-Guid</span><span class="sxs-lookup"><span data-stu-id="99726-227">-Guid</span></span>

<span data-ttu-id="99726-228">Указывает уникальный идентификатор для файла конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="99726-228">Specifies a unique identifier for the session configuration file.</span></span> <span data-ttu-id="99726-229">Если опустить этот параметр, `New-PSSessionConfigurationFile` создает идентификатор GUID для файла.</span><span class="sxs-lookup"><span data-stu-id="99726-229">If you omit this parameter, `New-PSSessionConfigurationFile` generates a GUID for the file.</span></span> <span data-ttu-id="99726-230">Чтобы создать новый GUID в PowerShell, введите `New-Guid` .</span><span class="sxs-lookup"><span data-stu-id="99726-230">To create a new GUID in PowerShell, type `New-Guid`.</span></span>

```yaml
Type: System.Guid
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="99726-231">-LanguageMode</span><span class="sxs-lookup"><span data-stu-id="99726-231">-LanguageMode</span></span>

<span data-ttu-id="99726-232">Определяет, какие элементы языка PowerShell разрешены в сеансах, использующих эту конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="99726-232">Determines which elements of the PowerShell language are permitted in sessions that use this session configuration.</span></span> <span data-ttu-id="99726-233">Этот параметр можно использовать для ограничения команд, которые определенные пользователи могут выполнять на компьютере.</span><span class="sxs-lookup"><span data-stu-id="99726-233">You can use this parameter to restrict the commands that particular users can run on the computer.</span></span>

<span data-ttu-id="99726-234">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="99726-234">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="99726-235">Фулллангуаже — разрешены все языковые элементы.</span><span class="sxs-lookup"><span data-stu-id="99726-235">FullLanguage - All language elements are permitted.</span></span>
- <span data-ttu-id="99726-236">ConstrainedLanguage — команды, содержащие скрипты для оценки, не допускаются.</span><span class="sxs-lookup"><span data-stu-id="99726-236">ConstrainedLanguage - Commands that contain scripts to be evaluated are not allowed.</span></span> <span data-ttu-id="99726-237">Режим ConstrainedLanguage ограничивает доступ пользователя к типам, объектам или методам Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="99726-237">The ConstrainedLanguage mode restricts user access to Microsoft .NET Framework types, objects, or methods.</span></span>
- <span data-ttu-id="99726-238">Неязыковый — пользователи могут запускать командлеты и функции, но не могут использовать элементы языка, такие как блоки скриптов, переменные или операторы.</span><span class="sxs-lookup"><span data-stu-id="99726-238">NoLanguage - Users may run cmdlets and functions, but are not permitted to use any language elements, such as script blocks, variables, or operators.</span></span>
- <span data-ttu-id="99726-239">Рестриктедлангуаже — пользователи могут запускать командлеты и функции, но не могут использовать блоки скриптов или переменные, за исключением следующих разрешенных переменных: `$PSCulture` , `$PSUICulture` , `$True` , `$False` и `$Null` .</span><span class="sxs-lookup"><span data-stu-id="99726-239">RestrictedLanguage - Users may run cmdlets and functions, but are not permitted to use script blocks or variables except for the following permitted variables: `$PSCulture`, `$PSUICulture`, `$True`, `$False`, and `$Null`.</span></span> <span data-ttu-id="99726-240">Пользователи могут использовать только базовые операторы сравнения ( `-eq` , `-gt` , `-lt` ).</span><span class="sxs-lookup"><span data-stu-id="99726-240">Users may use only the basic comparison operators (`-eq`, `-gt`, `-lt`).</span></span> <span data-ttu-id="99726-241">Операторы присваивания, ссылки на свойство и вызовы методов не разрешены.</span><span class="sxs-lookup"><span data-stu-id="99726-241">Assignment statements, property references, and method calls are not permitted.</span></span>

<span data-ttu-id="99726-242">Значение параметра **LanguageMode** по умолчанию зависит от значения параметра **SessionType** .</span><span class="sxs-lookup"><span data-stu-id="99726-242">The default value of the **LanguageMode** parameter depends on the value of the **SessionType** parameter.</span></span>

- <span data-ttu-id="99726-243">Пустой-неязык</span><span class="sxs-lookup"><span data-stu-id="99726-243">Empty - NoLanguage</span></span>
- <span data-ttu-id="99726-244">RestrictedRemoteServer-неязык</span><span class="sxs-lookup"><span data-stu-id="99726-244">RestrictedRemoteServer - NoLanguage</span></span>
- <span data-ttu-id="99726-245">По умолчанию — Фулллангуаже</span><span class="sxs-lookup"><span data-stu-id="99726-245">Default - FullLanguage</span></span>

```yaml
Type: System.Management.Automation.PSLanguageMode
Parameter Sets: (All)
Aliases:
Accepted values: FullLanguage, RestrictedLanguage, NoLanguage, ConstrainedLanguage

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="99726-246">-ModulesToImport</span><span class="sxs-lookup"><span data-stu-id="99726-246">-ModulesToImport</span></span>

<span data-ttu-id="99726-247">Указывает модули и оснастки, которые автоматически импортируются в сеансы, использующие конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="99726-247">Specifies the modules and snap-ins that are automatically imported into sessions that use the session configuration.</span></span>

<span data-ttu-id="99726-248">По умолчанию только оснастка **Microsoft. PowerShell. Core** импортируется в удаленные сеансы, но если эти командлеты не исключены, пользователи могут использовать `Import-Module` `Add-PSSnapin` командлеты и для добавления модулей и оснасток в сеанс.</span><span class="sxs-lookup"><span data-stu-id="99726-248">By default, only the **Microsoft.PowerShell.Core** snap-in is imported into remote sessions, but unless the cmdlets are excluded, users can use the `Import-Module` and `Add-PSSnapin` cmdlets to add modules and snap-ins to the session.</span></span>

<span data-ttu-id="99726-249">Каждый модуль или оснастка в значении этого параметра может быть представлен в виде строки или хэш-таблицы.</span><span class="sxs-lookup"><span data-stu-id="99726-249">Each module or snap-in in the value of this parameter can be represented by a string or as a hash table.</span></span> <span data-ttu-id="99726-250">Строка модуля состоит из имени модуля или оснастки.</span><span class="sxs-lookup"><span data-stu-id="99726-250">A module string consists only of the name of the module or snap-in.</span></span> <span data-ttu-id="99726-251">Хэш-таблица модуля может включать разделы **ModuleName** , **ModuleVersion** и **GUID** .</span><span class="sxs-lookup"><span data-stu-id="99726-251">A module hash table can include **ModuleName** , **ModuleVersion** , and **GUID** keys.</span></span> <span data-ttu-id="99726-252">Обязателен только раздел **ModuleName** .</span><span class="sxs-lookup"><span data-stu-id="99726-252">Only the **ModuleName** key is required.</span></span>

<span data-ttu-id="99726-253">Например, следующее значение состоит из строки и хэш-таблицы.</span><span class="sxs-lookup"><span data-stu-id="99726-253">For example, the following value consists of a string and a hash table.</span></span> <span data-ttu-id="99726-254">Допустимо любое сочетание строк и хэш-таблиц в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="99726-254">Any combination of strings and hash tables, in any order, is valid.</span></span>

`'TroubleshootingPack', @{ModuleName='PSDiagnostics'; ModuleVersion='1.0.0.0';GUID='c61d6278-02a3-4618-ae37-a524d40a7f44'}`

<span data-ttu-id="99726-255">Значение параметра **ModulesToImport** `Register-PSSessionConfiguration` командлета имеет приоритет над значением ключа **ModulesToImport** в файле конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="99726-255">The value of the **ModulesToImport** parameter of the `Register-PSSessionConfiguration` cmdlet takes precedence over the value of the **ModulesToImport** key in the session configuration file.</span></span>

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

### <span data-ttu-id="99726-256">-Маунтусердриве</span><span class="sxs-lookup"><span data-stu-id="99726-256">-MountUserDrive</span></span>

<span data-ttu-id="99726-257">Настраивает сеансы, использующие эту конфигурацию сеанса, для предоставления `User:` PSDrive.</span><span class="sxs-lookup"><span data-stu-id="99726-257">Configures sessions that use this session configuration to expose the `User:` PSDrive.</span></span> <span data-ttu-id="99726-258">Пользовательские диски уникальны для каждого подключающегося пользователя и позволяют пользователям копировать данные в конечные точки PowerShell и из них, даже если поставщик файловой системы не предоставляется.</span><span class="sxs-lookup"><span data-stu-id="99726-258">User drives are unique for each connecting user and allow users to copy data to and from PowerShell endpoints even if the File System provider is not exposed.</span></span> <span data-ttu-id="99726-259">Корни диска пользователя создаются в `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell\DriveRoots\` .</span><span class="sxs-lookup"><span data-stu-id="99726-259">User drive roots are created under `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell\DriveRoots\`.</span></span> <span data-ttu-id="99726-260">Для каждого пользователя, подключающегося к конечной точке, создается папка с именем `$env:USERDOMAIN_$env:USERNAME`.</span><span class="sxs-lookup"><span data-stu-id="99726-260">For each user connecting to the endpoint, a folder is created with the name `$env:USERDOMAIN_$env:USERNAME`.</span></span>

<span data-ttu-id="99726-261">Содержимое диска пользователя сохраняется во всех пользовательских сеансах и не удаляется автоматически.</span><span class="sxs-lookup"><span data-stu-id="99726-261">Contents in the user drive persist across user sessions and are not automatically removed.</span></span> <span data-ttu-id="99726-262">По умолчанию пользователи могут хранить до 50 МБ данных на диске пользователя.</span><span class="sxs-lookup"><span data-stu-id="99726-262">By default, users can only store up to 50MB of data in the user drive.</span></span> <span data-ttu-id="99726-263">Это можно настроить с помощью параметра **усердривемаксимумсизе** .</span><span class="sxs-lookup"><span data-stu-id="99726-263">This can be customized with the **UserDriveMaximumSize** parameter.</span></span>

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

### <span data-ttu-id="99726-264">-Path</span><span class="sxs-lookup"><span data-stu-id="99726-264">-Path</span></span>

<span data-ttu-id="99726-265">Указывает путь и имя файла конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="99726-265">Specifies the path and filename of the session configuration file.</span></span> <span data-ttu-id="99726-266">Файл должен иметь `.pssc` расширение имени файла.</span><span class="sxs-lookup"><span data-stu-id="99726-266">The file must have a `.pssc` file name extension.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="99726-267">-PowerShellVersion</span><span class="sxs-lookup"><span data-stu-id="99726-267">-PowerShellVersion</span></span>

<span data-ttu-id="99726-268">Указывает версию обработчика PowerShell в сеансах, использующих конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="99726-268">Specifies the version of the PowerShell engine in sessions that use the session configuration.</span></span> <span data-ttu-id="99726-269">Допустимые значения для этого параметра: 2,0 и 3,0.</span><span class="sxs-lookup"><span data-stu-id="99726-269">The acceptable values for this parameter are: 2.0 and 3.0.</span></span> <span data-ttu-id="99726-270">Если опустить этот параметр, ключ **PowerShellVersion** будет снабжен комментариями и в сеансе будут выполняться новейшие версии PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99726-270">If you omit this parameter, the **PowerShellVersion** key is commented-out and newest version of PowerShell runs in the session.</span></span>

<span data-ttu-id="99726-271">Значение параметра **PSVersion** `Register-PSSessionConfiguration` командлета имеет приоритет над значением ключа **PowerShellVersion** в файле конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="99726-271">The value of the **PSVersion** parameter of the `Register-PSSessionConfiguration` cmdlet takes precedence over the value of the **PowerShellVersion** key in the session configuration file.</span></span>

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

### <span data-ttu-id="99726-272">-RequiredGroups</span><span class="sxs-lookup"><span data-stu-id="99726-272">-RequiredGroups</span></span>

<span data-ttu-id="99726-273">Указывает правила условного доступа для пользователей, подключающихся к сеансам, использующим эту конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="99726-273">Specifies conditional access rules for users connecting to sessions that use this session configuration.</span></span>

<span data-ttu-id="99726-274">Введите хэш-таблицу, чтобы составить список правил, используя только один ключ на Hashtable, "and" или "or", и присвоить значение массиву имен групп безопасности или дополнительных хэш-таблиц.</span><span class="sxs-lookup"><span data-stu-id="99726-274">Enter a hashtable to compose your list of rules using only 1 key per hashtable, 'And' or 'Or', and set the value to an array of security group names or additional hashtables.</span></span>

<span data-ttu-id="99726-275">Пример, при котором пользователи должны быть членами одной группы: `@{ And = 'MyRequiredGroup' }`</span><span class="sxs-lookup"><span data-stu-id="99726-275">Example requiring connecting users to be members of a single group: `@{ And = 'MyRequiredGroup' }`</span></span>

<span data-ttu-id="99726-276">Пример, в котором пользователи должны принадлежать к группе A или обеим группам B и C для доступа к конечной точке: `@{ Or = 'GroupA', @{ And = 'GroupB', 'GroupC' } }`</span><span class="sxs-lookup"><span data-stu-id="99726-276">Example requiring users to belong to group A, or both groups B and C, to access the endpoint: `@{ Or = 'GroupA', @{ And = 'GroupB', 'GroupC' } }`</span></span>

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="99726-277">-RoleDefinitions</span><span class="sxs-lookup"><span data-stu-id="99726-277">-RoleDefinitions</span></span>

<span data-ttu-id="99726-278">Указывает сопоставление между группами безопасности (или пользователями) и возможностями ролей.</span><span class="sxs-lookup"><span data-stu-id="99726-278">Specifies the mapping between security groups (or users) and role capabilities.</span></span> <span data-ttu-id="99726-279">Пользователям будет предоставлен доступ ко всем возможностям ролей, которые применяются к их членству в группе во время создания сеанса.</span><span class="sxs-lookup"><span data-stu-id="99726-279">Users will be granted access to all role capabilities which apply to their group membership at the time the session is created.</span></span>

<span data-ttu-id="99726-280">Введите хэш-таблицу, в которой ключи являются именем группы безопасности, а значения — хэш-таблицами, которые содержат список возможностей роли, которые должны быть доступны группе безопасности.</span><span class="sxs-lookup"><span data-stu-id="99726-280">Enter a hash table in which the keys are the name of the security group and the values are hash tables that contain a list of role capabilities that should be made available to the security group.</span></span>

<span data-ttu-id="99726-281">Пример: `@{'Contoso\Level 2 Helpdesk Users' = @{ RoleCapabilities = 'Maintenance', 'ADHelpDesk' }}`</span><span class="sxs-lookup"><span data-stu-id="99726-281">For example: `@{'Contoso\Level 2 Helpdesk Users' = @{ RoleCapabilities = 'Maintenance', 'ADHelpDesk' }}`</span></span>

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="99726-282">-RunAsVirtualAccount</span><span class="sxs-lookup"><span data-stu-id="99726-282">-RunAsVirtualAccount</span></span>

<span data-ttu-id="99726-283">Настраивает сеансы, использующие эту конфигурацию сеанса, в качестве учетной записи администратора компьютера (виртуального).</span><span class="sxs-lookup"><span data-stu-id="99726-283">Configures sessions using this session configuration to be run as the computer's (virtual) administrator account.</span></span> <span data-ttu-id="99726-284">Это поле нельзя использовать с параметром **граупманажедсервицеаккаунт** .</span><span class="sxs-lookup"><span data-stu-id="99726-284">This field cannot be used with the **GroupManagedServiceAccount** parameter.</span></span>

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

### <span data-ttu-id="99726-285">-Рунасвиртуалаккаунтграупс</span><span class="sxs-lookup"><span data-stu-id="99726-285">-RunAsVirtualAccountGroups</span></span>

<span data-ttu-id="99726-286">Указывает группы безопасности, которые будут связаны с виртуальной учетной записью, если сеанс, использующий конфигурацию сеанса, выполняется как виртуальная учетная запись.</span><span class="sxs-lookup"><span data-stu-id="99726-286">Specifies the security groups to be associated with the virtual account when a session that uses the session configuration is run as a virtual account.</span></span> <span data-ttu-id="99726-287">Если этот параметр не указан, виртуальная учетная запись принадлежит администраторам домена на контроллерах домена и администраторах на всех остальных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="99726-287">If omitted, the virtual account belongs to Domain Admins on domain controllers and Administrators on all other computers.</span></span>

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

### <span data-ttu-id="99726-288">-SchemaVersion</span><span class="sxs-lookup"><span data-stu-id="99726-288">-SchemaVersion</span></span>

<span data-ttu-id="99726-289">Указывает версию схемы файла конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="99726-289">Specifies the version of the session configuration file schema.</span></span> <span data-ttu-id="99726-290">Значение по умолчанию: 1.0.0.0.</span><span class="sxs-lookup"><span data-stu-id="99726-290">The default value is "1.0.0.0".</span></span>

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

### <span data-ttu-id="99726-291">-ScriptsToProcess</span><span class="sxs-lookup"><span data-stu-id="99726-291">-ScriptsToProcess</span></span>

<span data-ttu-id="99726-292">Добавляет указанные сценарии в сеансы, использующие конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="99726-292">Adds the specified scripts to sessions that use the session configuration.</span></span> <span data-ttu-id="99726-293">Введите путь и имена файлов сценариев.</span><span class="sxs-lookup"><span data-stu-id="99726-293">Enter the path and file names of the scripts.</span></span> <span data-ttu-id="99726-294">Значение этого параметра должно быть полным или абсолютным путем к именам файлов скриптов.</span><span class="sxs-lookup"><span data-stu-id="99726-294">The value of this parameter must be a full or absolute path of script file names.</span></span>

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

### <span data-ttu-id="99726-295">-SessionType</span><span class="sxs-lookup"><span data-stu-id="99726-295">-SessionType</span></span>

<span data-ttu-id="99726-296">Указывает тип сеанса, создаваемого при использовании конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="99726-296">Specifies the type of session that is created by using the session configuration.</span></span> <span data-ttu-id="99726-297">Значение по умолчанию — Default.</span><span class="sxs-lookup"><span data-stu-id="99726-297">The default value is Default.</span></span> <span data-ttu-id="99726-298">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="99726-298">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="99726-299">Пусто. модули по умолчанию не добавляются в сеанс.</span><span class="sxs-lookup"><span data-stu-id="99726-299">Empty - No modules are added to session by default.</span></span> <span data-ttu-id="99726-300">Параметры этого командлета позволяют добавить в сеанс модули, функции, скрипты и другие элементы.</span><span class="sxs-lookup"><span data-stu-id="99726-300">Use the parameters of this cmdlet to add modules, functions, scripts, and other features to the session.</span></span> <span data-ttu-id="99726-301">Этот параметр предназначен для создания пользовательских сеансов путем добавления выбранных команд.</span><span class="sxs-lookup"><span data-stu-id="99726-301">This option is designed for you to create custom sessions by adding selected commands.</span></span> <span data-ttu-id="99726-302">Если вы не добавите команды в пустой сеанс, сеанс ограничивается выражениями и может не работать.</span><span class="sxs-lookup"><span data-stu-id="99726-302">If you do not add commands to an empty session, the session is limited to expressions and might not be usable.</span></span>
- <span data-ttu-id="99726-303">По умолчанию — добавляет модуль Microsoft. PowerShell. Core в сеанс.</span><span class="sxs-lookup"><span data-stu-id="99726-303">Default - Adds the Microsoft.PowerShell.Core module to the session.</span></span> <span data-ttu-id="99726-304">Этот модуль включает `Import-Module` командлет, который пользователи могут использовать для импорта других модулей, если этот командлет явно не запрещен.</span><span class="sxs-lookup"><span data-stu-id="99726-304">This module includes the `Import-Module` cmdlet that users can use to import other modules unless you explicitly prohibit this cmdlet.</span></span>
- <span data-ttu-id="99726-305">RestrictedRemoteServer.</span><span class="sxs-lookup"><span data-stu-id="99726-305">RestrictedRemoteServer.</span></span> <span data-ttu-id="99726-306">Включает в себя только следующие функции-посредники: `Exit-PSSession` ,,,,, и `Get-Command` `Get-FormatData` `Get-Help` `Measure-Object` `Out-Default` `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="99726-306">Includes only the following proxy functions: `Exit-PSSession`, `Get-Command`, `Get-FormatData`, `Get-Help`, `Measure-Object`, `Out-Default`, and `Select-Object`.</span></span>
  <span data-ttu-id="99726-307">Параметры этого командлета позволяют добавить в сеанс модули, функции, скрипты и другие элементы.</span><span class="sxs-lookup"><span data-stu-id="99726-307">Use the parameters of this cmdlet to add modules, functions, scripts, and other features to the session.</span></span>

```yaml
Type: System.Management.Automation.Remoting.SessionType
Parameter Sets: (All)
Aliases:
Accepted values: Empty, RestrictedRemoteServer, Default

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="99726-308">-TranscriptDirectory</span><span class="sxs-lookup"><span data-stu-id="99726-308">-TranscriptDirectory</span></span>

<span data-ttu-id="99726-309">Указывает каталог для размещения записей сеанса для сеансов, использующих эту конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="99726-309">Specifies the directory to place session transcripts for sessions using this session configuration.</span></span>

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

### <span data-ttu-id="99726-310">-TypesToProcess</span><span class="sxs-lookup"><span data-stu-id="99726-310">-TypesToProcess</span></span>

<span data-ttu-id="99726-311">Добавляет указанные `.ps1xml` файлы типов в сеансы, которые используют конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="99726-311">Adds the specified `.ps1xml` type files to sessions that use the session configuration.</span></span> <span data-ttu-id="99726-312">Введите имена файлов.</span><span class="sxs-lookup"><span data-stu-id="99726-312">Enter the type filenames.</span></span> <span data-ttu-id="99726-313">Значение этого параметра должно быть полным или абсолютным путем к типу filename.</span><span class="sxs-lookup"><span data-stu-id="99726-313">The value of this parameter must be a full or absolute path to type filenames.</span></span>

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

### <span data-ttu-id="99726-314">-Усердривемаксимумсизе</span><span class="sxs-lookup"><span data-stu-id="99726-314">-UserDriveMaximumSize</span></span>

<span data-ttu-id="99726-315">Указывает максимальный размер для дисков пользователей, доступных в сеансах, использующих эту конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="99726-315">Specifies the maximum size for user drives exposed in sessions that use this session configuration.</span></span>
<span data-ttu-id="99726-316">Если этот параметр опущен, размер каждого корня диска по умолчанию `User:` — 50 МБ.</span><span class="sxs-lookup"><span data-stu-id="99726-316">When omitted, the default size of each `User:` drive root is 50MB.</span></span>

<span data-ttu-id="99726-317">Этот параметр следует использовать с **маунтусердриве** .</span><span class="sxs-lookup"><span data-stu-id="99726-317">This parameter should be used with **MountUserDrive** .</span></span>

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="99726-318">-VariableDefinitions</span><span class="sxs-lookup"><span data-stu-id="99726-318">-VariableDefinitions</span></span>

<span data-ttu-id="99726-319">Добавляет указанные переменные в сеансы, использующие конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="99726-319">Adds the specified variables to sessions that use the session configuration.</span></span> <span data-ttu-id="99726-320">Введите хэш-таблицу со следующими разделами:</span><span class="sxs-lookup"><span data-stu-id="99726-320">Enter a hash table with the following keys:</span></span>

- <span data-ttu-id="99726-321">Name — имя переменной.</span><span class="sxs-lookup"><span data-stu-id="99726-321">Name - Name of the variable.</span></span> <span data-ttu-id="99726-322">Этот раздел обязателен.</span><span class="sxs-lookup"><span data-stu-id="99726-322">This key is required.</span></span>
- <span data-ttu-id="99726-323">Значение — значение переменной.</span><span class="sxs-lookup"><span data-stu-id="99726-323">Value - Variable value.</span></span> <span data-ttu-id="99726-324">Этот раздел обязателен.</span><span class="sxs-lookup"><span data-stu-id="99726-324">This key is required.</span></span>
- <span data-ttu-id="99726-325">Параметры — параметры переменных.</span><span class="sxs-lookup"><span data-stu-id="99726-325">Options - Variable options.</span></span> <span data-ttu-id="99726-326">Этот раздел необязателен.</span><span class="sxs-lookup"><span data-stu-id="99726-326">This key is optional.</span></span> <span data-ttu-id="99726-327">Значение по умолчанию — **None** .</span><span class="sxs-lookup"><span data-stu-id="99726-327">The default value is **None** .</span></span> <span data-ttu-id="99726-328">Допустимые значения для этого параметра: None, ReadOnly, Constant, private или AllScope.</span><span class="sxs-lookup"><span data-stu-id="99726-328">The acceptable values for this parameter are: None, ReadOnly, Constant, Private, or AllScope.</span></span>

<span data-ttu-id="99726-329">Пример: `@{Name='WarningPreference';Value='SilentlyContinue';Options='AllScope'}`</span><span class="sxs-lookup"><span data-stu-id="99726-329">For example: `@{Name='WarningPreference';Value='SilentlyContinue';Options='AllScope'}`</span></span>

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

### <span data-ttu-id="99726-330">-VisibleAliases</span><span class="sxs-lookup"><span data-stu-id="99726-330">-VisibleAliases</span></span>

<span data-ttu-id="99726-331">Ограничивает псевдонимы в сеансе теми, которые указаны в значении этого параметра, а также всеми псевдонимами, определенными в параметре **AliasDefinition** .</span><span class="sxs-lookup"><span data-stu-id="99726-331">Limits the aliases in the session to those specified in the value of this parameter, plus any aliases that you define in the **AliasDefinition** parameter.</span></span> <span data-ttu-id="99726-332">Поддерживаются подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="99726-332">Wildcard characters are supported.</span></span> <span data-ttu-id="99726-333">По умолчанию все псевдонимы, определенные подсистемой PowerShell и все псевдонимы, которые экспортируются модулями, видимы в сеансе.</span><span class="sxs-lookup"><span data-stu-id="99726-333">By default, all aliases that are defined by the PowerShell engine and all aliases that modules export are visible in the session.</span></span>

<span data-ttu-id="99726-334">Пример: `VisibleAliases='gcm', 'gp'`</span><span class="sxs-lookup"><span data-stu-id="99726-334">For example: `VisibleAliases='gcm', 'gp'`</span></span>

<span data-ttu-id="99726-335">Если любой **видимый** параметр включен в файл конфигурации сеанса, PowerShell удаляет `Import-Module` командлет и его псевдоним IPMO из сеанса.</span><span class="sxs-lookup"><span data-stu-id="99726-335">When any **Visible** parameter is included in the session configuration file, PowerShell removes the `Import-Module` cmdlet and its ipmo alias from the session.</span></span>

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

### <span data-ttu-id="99726-336">-VisibleCmdlets</span><span class="sxs-lookup"><span data-stu-id="99726-336">-VisibleCmdlets</span></span>

<span data-ttu-id="99726-337">Ограничивает командлеты в сеансе теми, которые указаны в значении этого параметра.</span><span class="sxs-lookup"><span data-stu-id="99726-337">Limits the cmdlets in the session to those specified in the value of this parameter.</span></span> <span data-ttu-id="99726-338">Поддерживаются подстановочные знаки и полные имена модулей.</span><span class="sxs-lookup"><span data-stu-id="99726-338">Wildcard characters and Module Qualified Names are supported.</span></span>

<span data-ttu-id="99726-339">По умолчанию все командлеты, экспортируемые модулями в сеансе, отображаются в сеансе.</span><span class="sxs-lookup"><span data-stu-id="99726-339">By default, all cmdlets that modules in the session export are visible in the session.</span></span> <span data-ttu-id="99726-340">Используйте параметры **SessionType** и **ModulesToImport** , чтобы определить, какие модули и оснастки импортируются в сеанс.</span><span class="sxs-lookup"><span data-stu-id="99726-340">Use the **SessionType** and **ModulesToImport** parameters to determine which modules and snap-ins are imported into the session.</span></span> <span data-ttu-id="99726-341">Если ни один из модулей в **ModulesToImport** не предоставляет командлет, соответствующий модуль будет пытаться выполнить автозагрузку.</span><span class="sxs-lookup"><span data-stu-id="99726-341">If no modules in **ModulesToImport** expose the cmdlet, the appropriate module will attempt to be autoloaded.</span></span>

<span data-ttu-id="99726-342">Если любой **видимый** параметр включен в файл конфигурации сеанса, PowerShell удаляет `Import-Module` командлет и его псевдоним IPMO из сеанса.</span><span class="sxs-lookup"><span data-stu-id="99726-342">When any **Visible** parameter is included in the session configuration file, PowerShell removes the `Import-Module` cmdlet and its ipmo alias from the session.</span></span>

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

### <span data-ttu-id="99726-343">-VisibleExternalCommands</span><span class="sxs-lookup"><span data-stu-id="99726-343">-VisibleExternalCommands</span></span>

<span data-ttu-id="99726-344">Ограничивает внешние двоичные файлы, скрипты и команды, которые могут выполняться в сеансе, с теми, которые указаны в значении этого параметра.</span><span class="sxs-lookup"><span data-stu-id="99726-344">Limits the external binaries, scripts, and commands that can be executed in the session to those specified in the value of this parameter.</span></span> <span data-ttu-id="99726-345">Поддерживаются подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="99726-345">Wildcard characters are supported.</span></span>

<span data-ttu-id="99726-346">По умолчанию в сеансе не отображаются никакие внешние команды.</span><span class="sxs-lookup"><span data-stu-id="99726-346">By default, no external commands are visible in the session.</span></span>

<span data-ttu-id="99726-347">Если любой **видимый** параметр включен в файл конфигурации сеанса, PowerShell удаляет `Import-Module` командлет и его псевдоним IPMO из сеанса.</span><span class="sxs-lookup"><span data-stu-id="99726-347">When any **Visible** parameter is included in the session configuration file, PowerShell, removes the `Import-Module` cmdlet and its ipmo alias from the session.</span></span>

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

### <span data-ttu-id="99726-348">-VisibleFunctions</span><span class="sxs-lookup"><span data-stu-id="99726-348">-VisibleFunctions</span></span>

<span data-ttu-id="99726-349">Ограничивает функции в сеансе теми, которые указаны в значении этого параметра, а также всеми функциями, определенными в параметре **FunctionDefinition** .</span><span class="sxs-lookup"><span data-stu-id="99726-349">Limits the functions in the session to those specified in the value of this parameter, plus any functions that you define in the **FunctionDefinition** parameter.</span></span> <span data-ttu-id="99726-350">Поддерживаются подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="99726-350">Wildcard characters are supported.</span></span>

<span data-ttu-id="99726-351">По умолчанию все функции, экспортируемые модулями в сеансе, отображаются в сеансе.</span><span class="sxs-lookup"><span data-stu-id="99726-351">By default, all functions that modules in the session export are visible in the session.</span></span> <span data-ttu-id="99726-352">Используйте параметры **SessionType** и **ModulesToImport** , чтобы определить, какие модули и оснастки импортируются в сеанс.</span><span class="sxs-lookup"><span data-stu-id="99726-352">Use the **SessionType** and **ModulesToImport** parameters to determine which modules and snap-ins are imported into the session.</span></span>

<span data-ttu-id="99726-353">Если любой **видимый** параметр включен в файл конфигурации сеанса, PowerShell удаляет `Import-Module` командлет и его псевдоним IPMO из сеанса.</span><span class="sxs-lookup"><span data-stu-id="99726-353">When any **Visible** parameter is included in the session configuration file, PowerShell removes the `Import-Module` cmdlet and its ipmo alias from the session.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="99726-354">-VisibleProviders</span><span class="sxs-lookup"><span data-stu-id="99726-354">-VisibleProviders</span></span>

<span data-ttu-id="99726-355">Ограничивает поставщиков PowerShell в сеансе теми, которые указаны в значении этого параметра.</span><span class="sxs-lookup"><span data-stu-id="99726-355">Limits the PowerShell providers in the session to those specified in the value of this parameter.</span></span>
<span data-ttu-id="99726-356">Поддерживаются подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="99726-356">Wildcard characters are supported.</span></span>

<span data-ttu-id="99726-357">По умолчанию все поставщики, экспортируемые модулями в сеансе, отображаются в сеансе.</span><span class="sxs-lookup"><span data-stu-id="99726-357">By default, all providers that modules in the session export are visible in the session.</span></span> <span data-ttu-id="99726-358">Используйте параметры **SessionType** и **ModulesToImport** , чтобы определить, какие модули импортируются в сеанс.</span><span class="sxs-lookup"><span data-stu-id="99726-358">Use the **SessionType** and **ModulesToImport** parameters to determine which modules are imported into the session.</span></span>

<span data-ttu-id="99726-359">Если любой **видимый** параметр включен в файл конфигурации сеанса, PowerShell удаляет `Import-Module` командлет и его `ipmo` псевдоним из сеанса.</span><span class="sxs-lookup"><span data-stu-id="99726-359">When any **Visible** parameter is included in the session configuration file, PowerShell removes the `Import-Module` cmdlet and its `ipmo` alias from the session.</span></span>

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

### <span data-ttu-id="99726-360">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="99726-360">CommonParameters</span></span>

<span data-ttu-id="99726-361">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="99726-361">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="99726-362">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="99726-362">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="99726-363">Входные данные</span><span class="sxs-lookup"><span data-stu-id="99726-363">INPUTS</span></span>

### <span data-ttu-id="99726-364">Нет</span><span class="sxs-lookup"><span data-stu-id="99726-364">None</span></span>

<span data-ttu-id="99726-365">В этот командлет нельзя передать по конвейеру ни один объект.</span><span class="sxs-lookup"><span data-stu-id="99726-365">You cannot pipe any objects to this cmdlet.</span></span>

## <span data-ttu-id="99726-366">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="99726-366">OUTPUTS</span></span>

### <span data-ttu-id="99726-367">Нет</span><span class="sxs-lookup"><span data-stu-id="99726-367">None</span></span>

<span data-ttu-id="99726-368">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="99726-368">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="99726-369">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="99726-369">NOTES</span></span>

- <span data-ttu-id="99726-370">Параметры, такие как **VisibleCmdlets** и **VisibleProviders** , не импортируют элементы в сеанс.</span><span class="sxs-lookup"><span data-stu-id="99726-370">Parameters, such as **VisibleCmdlets** and **VisibleProviders** , do not import items into the session.</span></span> <span data-ttu-id="99726-371">Вместо этого они отбирают элементы, импортированные в сеанс.</span><span class="sxs-lookup"><span data-stu-id="99726-371">Instead, they select from among the items imported into the session.</span></span> <span data-ttu-id="99726-372">Например, если значение параметра **VisibleProviders** является поставщиком сертификата, но в параметре **ModulesToImport** не указан модуль **Microsoft. PowerShell. Security** , который содержит поставщик сертификата, то поставщик сертификата не отображается в сеансе.</span><span class="sxs-lookup"><span data-stu-id="99726-372">For example, if the value of the **VisibleProviders** parameter is the Certificate provider, but the **ModulesToImport** parameter does not specify the **Microsoft.PowerShell.Security** module that contains the Certificate provider, the Certificate provider is not visible in the session.</span></span>
- <span data-ttu-id="99726-373">`New-PSSessionConfigurationFile` создает файл конфигурации сеанса с расширением имени файла pssc в пути, указанном в параметре **path** .</span><span class="sxs-lookup"><span data-stu-id="99726-373">`New-PSSessionConfigurationFile` creates a session configuration file that has a .pssc file name extension in the path that you specify in the **Path** parameter.</span></span> <span data-ttu-id="99726-374">При использовании файла конфигурации сеанса для создания конфигурации сеанса `Register-PSSessionConfiguration` командлет копирует файл конфигурации и сохраняет активную копию файла в подкаталоге **сессионконфиг** `$PSHOME` каталога.</span><span class="sxs-lookup"><span data-stu-id="99726-374">When you use the session configuration file to create a session configuration, the `Register-PSSessionConfiguration` cmdlet copies the configuration file and saves an active copy of the file in the **SessionConfig** subdirectory of the `$PSHOME` directory.</span></span>

  <span data-ttu-id="99726-375">Свойство **конфигфилепас** конфигурации сеанса содержит полный путь к файлу конфигурации активного сеанса.</span><span class="sxs-lookup"><span data-stu-id="99726-375">The **ConfigFilePath** property of the session configuration contains the fully qualified path of the active session configuration file.</span></span> <span data-ttu-id="99726-376">Активный файл конфигурации в каталоге можно изменить в `$PSHOME` любое время с помощью любого текстового редактора.</span><span class="sxs-lookup"><span data-stu-id="99726-376">You can modify the active configuration file in the `$PSHOME` directory at any time using any text editor.</span></span> <span data-ttu-id="99726-377">Внесенные изменения влияют на все новые сеансы, которые используют конфигурацию сеанса, но не на текущие сеансы.</span><span class="sxs-lookup"><span data-stu-id="99726-377">The changes that you make affect all new sessions that use the session configuration, but not existing sessions.</span></span>

  <span data-ttu-id="99726-378">Прежде чем использовать измененный файл конфигурации сеанса, используйте `Test-PSSessionConfigurationFile` командлет, чтобы проверить допустимость записей в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="99726-378">Before using an edited session configuration file, use the `Test-PSSessionConfigurationFile` cmdlet to verify that the configuration file entries are valid.</span></span>

## <span data-ttu-id="99726-379">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="99726-379">RELATED LINKS</span></span>

[<span data-ttu-id="99726-380">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="99726-380">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="99726-381">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="99726-381">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="99726-382">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="99726-382">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="99726-383">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="99726-383">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="99726-384">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="99726-384">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="99726-385">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="99726-385">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="99726-386">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="99726-386">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="99726-387">Поставщик WSMan</span><span class="sxs-lookup"><span data-stu-id="99726-387">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="99726-388">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="99726-388">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="99726-389">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="99726-389">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)