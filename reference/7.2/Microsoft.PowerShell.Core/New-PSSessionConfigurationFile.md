---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/24/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-pssessionconfigurationfile?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSSessionConfigurationFile
ms.openlocfilehash: a41c52bf163aa0a73b54e75b5192389a14da82bb
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600684"
---
# <span data-ttu-id="f8a80-102">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="f8a80-102">New-PSSessionConfigurationFile</span></span>

## <span data-ttu-id="f8a80-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="f8a80-103">SYNOPSIS</span></span>
<span data-ttu-id="f8a80-104">Создает файл, определяющий конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="f8a80-104">Creates a file that defines a session configuration.</span></span>

## <span data-ttu-id="f8a80-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f8a80-105">SYNTAX</span></span>

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

## <span data-ttu-id="f8a80-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f8a80-106">DESCRIPTION</span></span>

<span data-ttu-id="f8a80-107">`New-PSSessionConfigurationFile`Командлет создает файл параметров, определяющих конфигурацию сеанса и среду сеансов, которые создаются с помощью конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="f8a80-107">The `New-PSSessionConfigurationFile` cmdlet creates a file of settings that define a session configuration and the environment of sessions that are created by using the session configuration.</span></span>
<span data-ttu-id="f8a80-108">Чтобы использовать файл в конфигурации сеанса, используйте параметр **path** `Register-PSSessionConfiguration` `Set-PSSessionConfiguration` командлетов или.</span><span class="sxs-lookup"><span data-stu-id="f8a80-108">To use the file in a session configuration, use the **Path** parameter of the `Register-PSSessionConfiguration` or `Set-PSSessionConfiguration` cmdlets.</span></span>

<span data-ttu-id="f8a80-109">Создаваемый файл конфигурации сеанса `New-PSSessionConfigurationFile` является текстовым файлом, доступным для чтения, который содержит хэш-таблицу свойств и значений конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="f8a80-109">The session configuration file that `New-PSSessionConfigurationFile` creates is a human-readable text file that contains a hash table of the session configuration properties and values.</span></span> <span data-ttu-id="f8a80-110">Файл имеет `.pssc` расширение имени файла.</span><span class="sxs-lookup"><span data-stu-id="f8a80-110">The file has a `.pssc` filename extension.</span></span>

<span data-ttu-id="f8a80-111">Все параметры `New-PSSessionConfigurationFile` являются необязательными, за исключением параметра **path** .</span><span class="sxs-lookup"><span data-stu-id="f8a80-111">All parameters of `New-PSSessionConfigurationFile` are optional, except for the **Path** parameter.</span></span>
<span data-ttu-id="f8a80-112">Если параметр пропущен, соответствующий ключ в файле конфигурации сеанса преобразуется в комментарий (за исключением указанных в описании параметра).</span><span class="sxs-lookup"><span data-stu-id="f8a80-112">If you omit a parameter, the corresponding key in the session configuration file is commented-out, except where noted in the parameter description.</span></span>

<span data-ttu-id="f8a80-113">Конфигурация сеанса, также известная как конечная точка, представляет собой набор параметров на локальном компьютере, определяющий среду для сеансов PowerShell (**PSSession**), которые подключаются к компьютеру.</span><span class="sxs-lookup"><span data-stu-id="f8a80-113">A session configuration, also known as an endpoint, is a collection of settings on the local computer that define the environment for PowerShell sessions (**PSSessions**) that connect to the computer.</span></span> <span data-ttu-id="f8a80-114">Все **PSSession** используют конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="f8a80-114">All **PSSessions** use a session configuration.</span></span> <span data-ttu-id="f8a80-115">Чтобы указать определенную конфигурацию сеанса, используйте параметр **configurationName** командлетов, которые создают сеанс, например `New-PSSession` командлет.</span><span class="sxs-lookup"><span data-stu-id="f8a80-115">To specify a particular session configuration, use the **ConfigurationName** parameter of cmdlets that create a session, such as the `New-PSSession` cmdlet.</span></span>

<span data-ttu-id="f8a80-116">Файл конфигурации сеанса позволяет легко определить конфигурацию сеанса без сложных скриптов или сборок кода.</span><span class="sxs-lookup"><span data-stu-id="f8a80-116">A session configuration file makes it easy to define a session configuration without complex scripts or code assemblies.</span></span> <span data-ttu-id="f8a80-117">Параметры в файле используются с необязательным сценарием запуска и всеми сборками в конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="f8a80-117">The settings in the file are used with the optional startup script and any assemblies in the session configuration.</span></span>

<span data-ttu-id="f8a80-118">Дополнительные сведения о конфигурациях сеансов и файлах конфигурации сеанса см. в разделе [about_Session_Configurations](About/about_Session_Configurations.md) и [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span><span class="sxs-lookup"><span data-stu-id="f8a80-118">For more information about session configurations and session configuration files, see [about_Session_Configurations](About/about_Session_Configurations.md) and [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span></span>

<span data-ttu-id="f8a80-119">Этот командлет появился в PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="f8a80-119">This cmdlet was introduced in PowerShell 3.0.</span></span>

## <span data-ttu-id="f8a80-120">Примеры</span><span class="sxs-lookup"><span data-stu-id="f8a80-120">EXAMPLES</span></span>

### <span data-ttu-id="f8a80-121">Пример 1. Создание и использование сеанса на языке</span><span class="sxs-lookup"><span data-stu-id="f8a80-121">Example 1: Creating and using a NoLanguage session</span></span>

<span data-ttu-id="f8a80-122">В этом примере показано, как создать и увидеть последствия использования сеанса без языка.</span><span class="sxs-lookup"><span data-stu-id="f8a80-122">This example show how to create and the effects of using a no-language session.</span></span>

<span data-ttu-id="f8a80-123">Для этого нужно выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="f8a80-123">The steps include:</span></span>

1. <span data-ttu-id="f8a80-124">Создайте новый файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f8a80-124">Create a new configuration file.</span></span>
1. <span data-ttu-id="f8a80-125">Зарегистрируйте конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="f8a80-125">Register the configuration.</span></span>
1. <span data-ttu-id="f8a80-126">Создайте новый сеанс, использующий конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="f8a80-126">Create a new session that uses the configuration.</span></span>
1. <span data-ttu-id="f8a80-127">Выполните команды в этом новом сеансе.</span><span class="sxs-lookup"><span data-stu-id="f8a80-127">Run commands in that new session.</span></span>

<span data-ttu-id="f8a80-128">Чтобы выполнить команды в этом примере, запустите PowerShell с параметром Запуск от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="f8a80-128">To run the commands in this example, start PowerShell by using the Run as administrator option.</span></span> <span data-ttu-id="f8a80-129">Этот параметр необходим для выполнения `Register-PSSessionConfiguration` командлета.</span><span class="sxs-lookup"><span data-stu-id="f8a80-129">This option is required to run the `Register-PSSessionConfiguration` cmdlet.</span></span>

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

<span data-ttu-id="f8a80-130">В этом примере `Invoke-Command` происходит сбой, так как для **лангуажемоде** задано значение " **неязыковый**".</span><span class="sxs-lookup"><span data-stu-id="f8a80-130">In this example, the `Invoke-Command` fails because the **LanguageMode** is set to **NoLanguage**.</span></span>

### <span data-ttu-id="f8a80-131">Пример 2. Создание и использование сеанса Рестриктедлангуаже</span><span class="sxs-lookup"><span data-stu-id="f8a80-131">Example 2: Creating and using a RestrictedLanguage session</span></span>

<span data-ttu-id="f8a80-132">В этом примере показано, как создать и увидеть последствия использования сеанса без языка.</span><span class="sxs-lookup"><span data-stu-id="f8a80-132">This example show how to create and the effects of using a no-language session.</span></span>

<span data-ttu-id="f8a80-133">Для этого нужно выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="f8a80-133">The steps include:</span></span>

1. <span data-ttu-id="f8a80-134">Создайте новый файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f8a80-134">Create a new configuration file.</span></span>
1. <span data-ttu-id="f8a80-135">Зарегистрируйте конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="f8a80-135">Register the configuration.</span></span>
1. <span data-ttu-id="f8a80-136">Создайте новый сеанс, использующий конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="f8a80-136">Create a new session that uses the configuration.</span></span>
1. <span data-ttu-id="f8a80-137">Выполните команды в этом новом сеансе.</span><span class="sxs-lookup"><span data-stu-id="f8a80-137">Run commands in that new session.</span></span>

<span data-ttu-id="f8a80-138">Чтобы выполнить команды в этом примере, запустите PowerShell с параметром Запуск от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="f8a80-138">To run the commands in this example, start PowerShell by using the Run as administrator option.</span></span> <span data-ttu-id="f8a80-139">Этот параметр необходим для выполнения `Register-PSSessionConfiguration` командлета.</span><span class="sxs-lookup"><span data-stu-id="f8a80-139">This option is required to run the `Register-PSSessionConfiguration` cmdlet.</span></span>

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

<span data-ttu-id="f8a80-140">В этом примере объект `Invoke-Command` выполняется, так как для **лангуажемоде** задано значение **рестриктедлангуаже**.</span><span class="sxs-lookup"><span data-stu-id="f8a80-140">In this example, the `Invoke-Command` succeeds because the **LanguageMode** is set to **RestrictedLanguage**.</span></span>

### <span data-ttu-id="f8a80-141">Пример 3. Изменение файла конфигурации сеанса</span><span class="sxs-lookup"><span data-stu-id="f8a80-141">Example 3: Changing a Session Configuration File</span></span>

<span data-ttu-id="f8a80-142">В этом примере показано, как изменить файл конфигурации сеанса, используемый в существующем сеансе с именем «ITTasks».</span><span class="sxs-lookup"><span data-stu-id="f8a80-142">This example shows how to change the session configuration file that is used in an existing session named "ITTasks".</span></span> <span data-ttu-id="f8a80-143">Ранее в этих сеансах были только основные модули и внутренний модуль **ITTasks** .</span><span class="sxs-lookup"><span data-stu-id="f8a80-143">Previously, these sessions had only the core modules and an internal **ITTasks** module.</span></span> <span data-ttu-id="f8a80-144">Администратор хочет добавить модуль **PSScheduledJob** в сеансы, созданные с помощью конфигурации сеанса ITTasks.</span><span class="sxs-lookup"><span data-stu-id="f8a80-144">The administrator wants to add the **PSScheduledJob** module to sessions created by using the ITTasks session configuration.</span></span>

```powershell
New-PSSessionConfigurationFile -Path .\New-ITTasks.pssc -ModulesToImport Microsoft*, ITTasks, PSScheduledJob
Set-PSSessionConfiguration -Name ITTasks -Path .\New-ITTasks.pssc
```

<span data-ttu-id="f8a80-145">`New-PSSessionConfigurationFile`Командлет для создания файла конфигурации сеанса, который импортирует необходимые модули.</span><span class="sxs-lookup"><span data-stu-id="f8a80-145">The `New-PSSessionConfigurationFile` cmdlet to create a session configuration file that imports the required modules.</span></span> <span data-ttu-id="f8a80-146">`Set-PSSessionConfiguration`Командлет заменяет текущий файл конфигурации новым.</span><span class="sxs-lookup"><span data-stu-id="f8a80-146">The `Set-PSSessionConfiguration` cmdlet replaces the current configuration file with the new one.</span></span> <span data-ttu-id="f8a80-147">Эта новая конфигурация влияет только на новые сеансы, созданные после изменения.</span><span class="sxs-lookup"><span data-stu-id="f8a80-147">This new configuration only affects new sessions created after the change.</span></span>
<span data-ttu-id="f8a80-148">Существующие сеансы "ITTasks" не затрагиваются.</span><span class="sxs-lookup"><span data-stu-id="f8a80-148">Existing "ITTasks" sessions are not affected.</span></span>

### <span data-ttu-id="f8a80-149">Пример 4. Редактирование файла конфигурации сеанса</span><span class="sxs-lookup"><span data-stu-id="f8a80-149">Example 4: Editing a Session Configuration File</span></span>

<span data-ttu-id="f8a80-150">В этом примере показано, как изменить конфигурацию сеанса путем редактирования копии конфигурации активного сеанса из файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f8a80-150">This example shows how to change a session configuration by editing the active session configuration copy of the configuration file.</span></span> <span data-ttu-id="f8a80-151">Чтобы изменить копию конфигурации сеанса файла конфигурации, необходимо иметь полный доступ к файлу.</span><span class="sxs-lookup"><span data-stu-id="f8a80-151">To modify the session configuration copy of the configuration file, you must have full control access to the file.</span></span> <span data-ttu-id="f8a80-152">Для этого может потребоваться изменить разрешения для файла.</span><span class="sxs-lookup"><span data-stu-id="f8a80-152">This may require you to change the permissions on the file.</span></span>

<span data-ttu-id="f8a80-153">В этом сценарии мы хотим добавить новый псевдоним для `Select-String` командлета, изменив активный файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f8a80-153">In this scenario, we want to add a new alias for the `Select-String` cmdlet by editing the active configuration file.</span></span>

<span data-ttu-id="f8a80-154">Приведенный ниже пример кода выполняет следующие действия для внесения этого изменения:</span><span class="sxs-lookup"><span data-stu-id="f8a80-154">The example code below performs the following steps to make this change:</span></span>

1. <span data-ttu-id="f8a80-155">Получите путь к файлу конфигурации для сеанса Итконфиг.</span><span class="sxs-lookup"><span data-stu-id="f8a80-155">Get the configuration file path for the ITConfig session.</span></span>
1. <span data-ttu-id="f8a80-156">Пользователь редактирует файл конфигурации с помощью **Notepad.exe** для изменения значения **алиасдефинитионс** следующим образом: `AliasDefinitions = @(@{Name='slst';Value='Select-String'})` .</span><span class="sxs-lookup"><span data-stu-id="f8a80-156">The user edits the configuration file using **Notepad.exe** to change the **AliasDefinitions** value as follows: `AliasDefinitions = @(@{Name='slst';Value='Select-String'})`.</span></span>
1. <span data-ttu-id="f8a80-157">Протестируйте обновленный файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f8a80-157">Test the updated configuration file.</span></span>

```powershell
$ITConfig = Get-PSSessionConfiguration -Name ITConfig
notepad.exe $ITConfig.ConfigFilePath
Test-PSSessionConfigurationFile -Path $ITConfig.ConfigFilePath
```

```Output
True
```

<span data-ttu-id="f8a80-158">Используйте параметр **verbose** с для, `Test-PSSessionConfigurationFile` чтобы отобразить обнаруженные ошибки.</span><span class="sxs-lookup"><span data-stu-id="f8a80-158">Use the **Verbose** parameter with `Test-PSSessionConfigurationFile` to display any errors that are detected.</span></span> <span data-ttu-id="f8a80-159">Командлет возвращает, `$True` Если в файле не обнаружены ошибки.</span><span class="sxs-lookup"><span data-stu-id="f8a80-159">The cmdlet returns `$True` if no errors are detected in the file.</span></span>

### <span data-ttu-id="f8a80-160">Пример 5. Создание образца файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="f8a80-160">Example 5: Create a sample configuration file</span></span>

<span data-ttu-id="f8a80-161">В этом примере показана `New-PSSessionConfigurationFile` команда, использующая все параметры командлета.</span><span class="sxs-lookup"><span data-stu-id="f8a80-161">This example shows a `New-PSSessionConfigurationFile` command that uses all the cmdlet parameters.</span></span>
<span data-ttu-id="f8a80-162">Она включена в пример, чтобы показать правильный входной формат для каждого параметра.</span><span class="sxs-lookup"><span data-stu-id="f8a80-162">It is included to show the correct input format for each parameter.</span></span>

<span data-ttu-id="f8a80-163">Получившийся файл SampleFile.pssc отображается в выходных данных.</span><span class="sxs-lookup"><span data-stu-id="f8a80-163">The resulting SampleFile.pssc is displayed in the output.</span></span>

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

## <span data-ttu-id="f8a80-164">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f8a80-164">PARAMETERS</span></span>

### <span data-ttu-id="f8a80-165">-AliasDefinitions</span><span class="sxs-lookup"><span data-stu-id="f8a80-165">-AliasDefinitions</span></span>

<span data-ttu-id="f8a80-166">Добавляет указанные псевдонимы сеансы, использующие конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="f8a80-166">Adds the specified aliases to sessions that use the session configuration.</span></span> <span data-ttu-id="f8a80-167">Введите хэш-таблицу со следующими разделами:</span><span class="sxs-lookup"><span data-stu-id="f8a80-167">Enter a hash table with the following keys:</span></span>

- <span data-ttu-id="f8a80-168">Name — имя псевдонима.</span><span class="sxs-lookup"><span data-stu-id="f8a80-168">Name - Name of the alias.</span></span> <span data-ttu-id="f8a80-169">Этот раздел обязателен.</span><span class="sxs-lookup"><span data-stu-id="f8a80-169">This key is required.</span></span>
- <span data-ttu-id="f8a80-170">Value — команда, которую представляет псевдоним.</span><span class="sxs-lookup"><span data-stu-id="f8a80-170">Value - The command that the alias represents.</span></span> <span data-ttu-id="f8a80-171">Этот раздел обязателен.</span><span class="sxs-lookup"><span data-stu-id="f8a80-171">This key is required.</span></span>
- <span data-ttu-id="f8a80-172">Описание — текстовая строка, описывающая псевдоним.</span><span class="sxs-lookup"><span data-stu-id="f8a80-172">Description - A text string that describes the alias.</span></span> <span data-ttu-id="f8a80-173">Этот раздел необязателен.</span><span class="sxs-lookup"><span data-stu-id="f8a80-173">This key is optional.</span></span>
- <span data-ttu-id="f8a80-174">Параметры — параметры псевдонимов.</span><span class="sxs-lookup"><span data-stu-id="f8a80-174">Options - Alias options.</span></span> <span data-ttu-id="f8a80-175">Этот раздел необязателен.</span><span class="sxs-lookup"><span data-stu-id="f8a80-175">This key is optional.</span></span> <span data-ttu-id="f8a80-176">Значение по умолчанию — **None**.</span><span class="sxs-lookup"><span data-stu-id="f8a80-176">The default value is **None**.</span></span> <span data-ttu-id="f8a80-177">Допустимые значения для этого параметра: None, ReadOnly, Constant, private или AllScope.</span><span class="sxs-lookup"><span data-stu-id="f8a80-177">The acceptable values for this parameter are: None, ReadOnly, Constant, Private, or AllScope.</span></span>

<span data-ttu-id="f8a80-178">Пример: `@{Name='hlp';Value='Get-Help';Description='Gets help';Options='ReadOnly'}`</span><span class="sxs-lookup"><span data-stu-id="f8a80-178">For example: `@{Name='hlp';Value='Get-Help';Description='Gets help';Options='ReadOnly'}`</span></span>

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

### <span data-ttu-id="f8a80-179">-AssembliesToLoad</span><span class="sxs-lookup"><span data-stu-id="f8a80-179">-AssembliesToLoad</span></span>

<span data-ttu-id="f8a80-180">Задает сборки для загрузки в сеансы, которые используют конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="f8a80-180">Specifies the assemblies to load into the sessions that use the session configuration.</span></span>

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

### <span data-ttu-id="f8a80-181">-Author</span><span class="sxs-lookup"><span data-stu-id="f8a80-181">-Author</span></span>

<span data-ttu-id="f8a80-182">Указывает автора конфигурации сеанса или файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f8a80-182">Specifies the author of the session configuration or the configuration file.</span></span> <span data-ttu-id="f8a80-183">По умолчанию используется текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="f8a80-183">The default is the current user.</span></span> <span data-ttu-id="f8a80-184">Значение этого параметра отображается в файле конфигурации сеанса, но не является свойством объекта конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="f8a80-184">The value of this parameter is visible in the session configuration file, but it is not a property of the session configuration object.</span></span>

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

### <span data-ttu-id="f8a80-185">-CompanyName</span><span class="sxs-lookup"><span data-stu-id="f8a80-185">-CompanyName</span></span>

<span data-ttu-id="f8a80-186">Указывает компанию, которая создала конфигурацию сеанса или файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f8a80-186">Specifies the company that created the session configuration or the configuration file.</span></span> <span data-ttu-id="f8a80-187">Значение по умолчанию — **Unknown**.</span><span class="sxs-lookup"><span data-stu-id="f8a80-187">The default value is **Unknown**.</span></span> <span data-ttu-id="f8a80-188">Значение этого параметра отображается в файле конфигурации сеанса, но не является свойством объекта конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="f8a80-188">The value of this parameter is visible in the session configuration file, but it is not a property of the session configuration object.</span></span>

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

### <span data-ttu-id="f8a80-189">-Copyright</span><span class="sxs-lookup"><span data-stu-id="f8a80-189">-Copyright</span></span>

<span data-ttu-id="f8a80-190">Указывает авторские права на файл конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="f8a80-190">Specifies a copyright the session configuration file.</span></span> <span data-ttu-id="f8a80-191">Значение этого параметра отображается в файле конфигурации сеанса, но не является свойством объекта конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="f8a80-191">The value of this parameter is visible in the session configuration file, but it is not a property of the session configuration object.</span></span>

<span data-ttu-id="f8a80-192">Если опустить этот параметр, `New-PSSessionConfigurationFile` создает заявление об авторских правах с помощью значения параметра **Author** .</span><span class="sxs-lookup"><span data-stu-id="f8a80-192">If you omit this parameter, `New-PSSessionConfigurationFile` generates a copyright statement by using the value of the **Author** parameter.</span></span>

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

### <span data-ttu-id="f8a80-193">-Description</span><span class="sxs-lookup"><span data-stu-id="f8a80-193">-Description</span></span>

<span data-ttu-id="f8a80-194">Задает описание конфигурации сеанса или файла конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="f8a80-194">Specifies a description of the session configuration or the session configuration file.</span></span> <span data-ttu-id="f8a80-195">Значение этого параметра отображается в файле конфигурации сеанса, но не является свойством объекта конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="f8a80-195">The value of this parameter is visible in the session configuration file, but it is not a property of the session configuration object.</span></span>

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

### <span data-ttu-id="f8a80-196">-EnvironmentVariables</span><span class="sxs-lookup"><span data-stu-id="f8a80-196">-EnvironmentVariables</span></span>

<span data-ttu-id="f8a80-197">Добавляет переменные среды в сеанс.</span><span class="sxs-lookup"><span data-stu-id="f8a80-197">Adds environment variables to the session.</span></span> <span data-ttu-id="f8a80-198">Введите хэш-таблицу, в которой разделами являются имена переменных среды, а значениями — значения переменных среды.</span><span class="sxs-lookup"><span data-stu-id="f8a80-198">Enter a hash table in which the keys are the environment variable names and the values are the environment variable values.</span></span>

<span data-ttu-id="f8a80-199">Пример: `EnvironmentVariables=@{TestShare='\\Server01\TestShare'}`</span><span class="sxs-lookup"><span data-stu-id="f8a80-199">For example: `EnvironmentVariables=@{TestShare='\\Server01\TestShare'}`</span></span>

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

### <span data-ttu-id="f8a80-200">-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="f8a80-200">-ExecutionPolicy</span></span>

<span data-ttu-id="f8a80-201">Указывает политику выполнения сеансов, использующих конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="f8a80-201">Specifies the execution policy of sessions that use the session configuration.</span></span> <span data-ttu-id="f8a80-202">Если опустить этот параметр, значение ключа **ExecutionPolicy** в файле конфигурации сеанса будет **ограничено**.</span><span class="sxs-lookup"><span data-stu-id="f8a80-202">If you omit this parameter, the value of the **ExecutionPolicy** key in the session configuration file is **Restricted**.</span></span> <span data-ttu-id="f8a80-203">Дополнительные сведения о политиках выполнения в PowerShell см. в разделе [about_Execution_Policies](about/about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="f8a80-203">For information about execution policies in PowerShell, see [about_Execution_Policies](about/about_Execution_Policies.md).</span></span>

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

### <span data-ttu-id="f8a80-204">-FormatsToProcess</span><span class="sxs-lookup"><span data-stu-id="f8a80-204">-FormatsToProcess</span></span>

<span data-ttu-id="f8a80-205">Указывает файлы форматирования (PS1XML-файлы), выполняющиеся в сеансах, которые используют конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="f8a80-205">Specifies the formatting files (.ps1xml) that run in sessions that use the session configuration.</span></span>
<span data-ttu-id="f8a80-206">Значение этого параметра должно быть полным или абсолютным путем к файлам форматирования.</span><span class="sxs-lookup"><span data-stu-id="f8a80-206">The value of this parameter must be a full or absolute path of the formatting files.</span></span>

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

### <span data-ttu-id="f8a80-207">-Full</span><span class="sxs-lookup"><span data-stu-id="f8a80-207">-Full</span></span>

<span data-ttu-id="f8a80-208">Указывает, что эта операция включает все возможные свойства конфигурации в файле конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="f8a80-208">Indicates that this operation includes all possible configuration properties in the session configuration file.</span></span>

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

### <span data-ttu-id="f8a80-209">-FunctionDefinitions</span><span class="sxs-lookup"><span data-stu-id="f8a80-209">-FunctionDefinitions</span></span>

<span data-ttu-id="f8a80-210">Добавляет в сеансы указанные функции, использующие конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="f8a80-210">Adds the specified functions to sessions that use the session configuration.</span></span> <span data-ttu-id="f8a80-211">Введите хэш-таблицу со следующими разделами:</span><span class="sxs-lookup"><span data-stu-id="f8a80-211">Enter a hash table with the following keys:</span></span>

- <span data-ttu-id="f8a80-212">Name — имя функции.</span><span class="sxs-lookup"><span data-stu-id="f8a80-212">Name - Name of the function.</span></span> <span data-ttu-id="f8a80-213">Этот раздел обязателен.</span><span class="sxs-lookup"><span data-stu-id="f8a80-213">This key is required.</span></span>
- <span data-ttu-id="f8a80-214">ScriptBlock — тело функции.</span><span class="sxs-lookup"><span data-stu-id="f8a80-214">ScriptBlock - Function body.</span></span> <span data-ttu-id="f8a80-215">Введите блок сценария.</span><span class="sxs-lookup"><span data-stu-id="f8a80-215">Enter a script block.</span></span> <span data-ttu-id="f8a80-216">Этот раздел обязателен.</span><span class="sxs-lookup"><span data-stu-id="f8a80-216">This key is required.</span></span>
- <span data-ttu-id="f8a80-217">Параметры — параметры функции.</span><span class="sxs-lookup"><span data-stu-id="f8a80-217">Options - Function options.</span></span> <span data-ttu-id="f8a80-218">Этот раздел необязателен.</span><span class="sxs-lookup"><span data-stu-id="f8a80-218">This key is optional.</span></span> <span data-ttu-id="f8a80-219">Значение по умолчанию — **None**.</span><span class="sxs-lookup"><span data-stu-id="f8a80-219">The default value is **None**.</span></span> <span data-ttu-id="f8a80-220">Допустимые значения для этого параметра: None, ReadOnly, Constant, private или AllScope.</span><span class="sxs-lookup"><span data-stu-id="f8a80-220">The acceptable values for this parameter are: None, ReadOnly, Constant, Private, or AllScope.</span></span>

<span data-ttu-id="f8a80-221">Пример: `@{Name='Get-PowerShellProcess';ScriptBlock={Get-Process PowerShell};Options='AllScope'}`</span><span class="sxs-lookup"><span data-stu-id="f8a80-221">For example: `@{Name='Get-PowerShellProcess';ScriptBlock={Get-Process PowerShell};Options='AllScope'}`</span></span>

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

### <span data-ttu-id="f8a80-222">-Граупманажедсервицеаккаунт</span><span class="sxs-lookup"><span data-stu-id="f8a80-222">-GroupManagedServiceAccount</span></span>

<span data-ttu-id="f8a80-223">Настраивает сеансы, использующие эту конфигурацию сеанса, для запуска в контексте указанной групповой управляемой учетной записи службы.</span><span class="sxs-lookup"><span data-stu-id="f8a80-223">Configures sessions using this session configuration to run under the context of the specified Group Managed Service Account.</span></span> <span data-ttu-id="f8a80-224">Компьютер, на котором зарегистрирована эта конфигурация сеанса, должен иметь разрешение на запрос пароля gMSA для успешного создания сеансов.</span><span class="sxs-lookup"><span data-stu-id="f8a80-224">The machine where this session configuration is registered must have permission to request the gMSA password in order for sessions to be created successfully.</span></span> <span data-ttu-id="f8a80-225">Это поле нельзя использовать с параметром **RunAsVirtualAccount** .</span><span class="sxs-lookup"><span data-stu-id="f8a80-225">This field cannot be used with the **RunAsVirtualAccount** parameter.</span></span>

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

### <span data-ttu-id="f8a80-226">-Guid</span><span class="sxs-lookup"><span data-stu-id="f8a80-226">-Guid</span></span>

<span data-ttu-id="f8a80-227">Указывает уникальный идентификатор для файла конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="f8a80-227">Specifies a unique identifier for the session configuration file.</span></span> <span data-ttu-id="f8a80-228">Если опустить этот параметр, `New-PSSessionConfigurationFile` создает идентификатор GUID для файла.</span><span class="sxs-lookup"><span data-stu-id="f8a80-228">If you omit this parameter, `New-PSSessionConfigurationFile` generates a GUID for the file.</span></span> <span data-ttu-id="f8a80-229">Чтобы создать новый GUID в PowerShell, введите `New-Guid` .</span><span class="sxs-lookup"><span data-stu-id="f8a80-229">To create a new GUID in PowerShell, type `New-Guid`.</span></span>

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

### <span data-ttu-id="f8a80-230">-LanguageMode</span><span class="sxs-lookup"><span data-stu-id="f8a80-230">-LanguageMode</span></span>

<span data-ttu-id="f8a80-231">Определяет, какие элементы языка PowerShell разрешены в сеансах, использующих эту конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="f8a80-231">Determines which elements of the PowerShell language are permitted in sessions that use this session configuration.</span></span> <span data-ttu-id="f8a80-232">Этот параметр можно использовать для ограничения команд, которые определенные пользователи могут выполнять на компьютере.</span><span class="sxs-lookup"><span data-stu-id="f8a80-232">You can use this parameter to restrict the commands that particular users can run on the computer.</span></span>

<span data-ttu-id="f8a80-233">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="f8a80-233">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="f8a80-234">Фулллангуаже — разрешены все языковые элементы.</span><span class="sxs-lookup"><span data-stu-id="f8a80-234">FullLanguage - All language elements are permitted.</span></span>
- <span data-ttu-id="f8a80-235">ConstrainedLanguage — команды, содержащие скрипты для оценки, не допускаются.</span><span class="sxs-lookup"><span data-stu-id="f8a80-235">ConstrainedLanguage - Commands that contain scripts to be evaluated are not allowed.</span></span> <span data-ttu-id="f8a80-236">Режим ConstrainedLanguage ограничивает доступ пользователя к типам, объектам или методам Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f8a80-236">The ConstrainedLanguage mode restricts user access to Microsoft .NET Framework types, objects, or methods.</span></span>
- <span data-ttu-id="f8a80-237">Неязыковый — пользователи могут запускать командлеты и функции, но не могут использовать элементы языка, такие как блоки скриптов, переменные или операторы.</span><span class="sxs-lookup"><span data-stu-id="f8a80-237">NoLanguage - Users may run cmdlets and functions, but are not permitted to use any language elements, such as script blocks, variables, or operators.</span></span>
- <span data-ttu-id="f8a80-238">Рестриктедлангуаже — пользователи могут запускать командлеты и функции, но не могут использовать блоки скриптов или переменные, за исключением следующих разрешенных переменных: `$PSCulture` , `$PSUICulture` , `$True` , `$False` и `$Null` .</span><span class="sxs-lookup"><span data-stu-id="f8a80-238">RestrictedLanguage - Users may run cmdlets and functions, but are not permitted to use script blocks or variables except for the following permitted variables: `$PSCulture`, `$PSUICulture`, `$True`, `$False`, and `$Null`.</span></span> <span data-ttu-id="f8a80-239">Пользователи могут использовать только базовые операторы сравнения ( `-eq` , `-gt` , `-lt` ).</span><span class="sxs-lookup"><span data-stu-id="f8a80-239">Users may use only the basic comparison operators (`-eq`, `-gt`, `-lt`).</span></span> <span data-ttu-id="f8a80-240">Операторы присваивания, ссылки на свойство и вызовы методов не разрешены.</span><span class="sxs-lookup"><span data-stu-id="f8a80-240">Assignment statements, property references, and method calls are not permitted.</span></span>

<span data-ttu-id="f8a80-241">Значение параметра **LanguageMode** по умолчанию зависит от значения параметра **SessionType**.</span><span class="sxs-lookup"><span data-stu-id="f8a80-241">The default value of the **LanguageMode** parameter depends on the value of the **SessionType** parameter.</span></span>

- <span data-ttu-id="f8a80-242">Пустой-неязык</span><span class="sxs-lookup"><span data-stu-id="f8a80-242">Empty - NoLanguage</span></span>
- <span data-ttu-id="f8a80-243">RestrictedRemoteServer-неязык</span><span class="sxs-lookup"><span data-stu-id="f8a80-243">RestrictedRemoteServer - NoLanguage</span></span>
- <span data-ttu-id="f8a80-244">По умолчанию — Фулллангуаже</span><span class="sxs-lookup"><span data-stu-id="f8a80-244">Default - FullLanguage</span></span>

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

### <span data-ttu-id="f8a80-245">-ModulesToImport</span><span class="sxs-lookup"><span data-stu-id="f8a80-245">-ModulesToImport</span></span>

<span data-ttu-id="f8a80-246">Указывает модули и оснастки, которые автоматически импортируются в сеансы, использующие конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="f8a80-246">Specifies the modules and snap-ins that are automatically imported into sessions that use the session configuration.</span></span>

<span data-ttu-id="f8a80-247">По умолчанию только оснастка **Microsoft. PowerShell. Core** импортируется в удаленные сеансы, но если эти командлеты не исключены, пользователи могут использовать `Import-Module` `Add-PSSnapin` командлеты и для добавления модулей и оснасток в сеанс.</span><span class="sxs-lookup"><span data-stu-id="f8a80-247">By default, only the **Microsoft.PowerShell.Core** snap-in is imported into remote sessions, but unless the cmdlets are excluded, users can use the `Import-Module` and `Add-PSSnapin` cmdlets to add modules and snap-ins to the session.</span></span>

<span data-ttu-id="f8a80-248">Каждый модуль или оснастка в значении этого параметра может быть представлен в виде строки или хэш-таблицы.</span><span class="sxs-lookup"><span data-stu-id="f8a80-248">Each module or snap-in in the value of this parameter can be represented by a string or as a hash table.</span></span> <span data-ttu-id="f8a80-249">Строка модуля состоит из имени модуля или оснастки.</span><span class="sxs-lookup"><span data-stu-id="f8a80-249">A module string consists only of the name of the module or snap-in.</span></span> <span data-ttu-id="f8a80-250">Хэш-таблица модуля может включать разделы **ModuleName**, **ModuleVersion** и **GUID**.</span><span class="sxs-lookup"><span data-stu-id="f8a80-250">A module hash table can include **ModuleName**, **ModuleVersion**, and **GUID** keys.</span></span> <span data-ttu-id="f8a80-251">Обязателен только раздел **ModuleName**.</span><span class="sxs-lookup"><span data-stu-id="f8a80-251">Only the **ModuleName** key is required.</span></span>

<span data-ttu-id="f8a80-252">Например, следующее значение состоит из строки и хэш-таблицы.</span><span class="sxs-lookup"><span data-stu-id="f8a80-252">For example, the following value consists of a string and a hash table.</span></span> <span data-ttu-id="f8a80-253">Допустимо любое сочетание строк и хэш-таблиц в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="f8a80-253">Any combination of strings and hash tables, in any order, is valid.</span></span>

`'TroubleshootingPack', @{ModuleName='PSDiagnostics'; ModuleVersion='1.0.0.0';GUID='c61d6278-02a3-4618-ae37-a524d40a7f44'}`

<span data-ttu-id="f8a80-254">Значение параметра **ModulesToImport** `Register-PSSessionConfiguration` командлета имеет приоритет над значением ключа **ModulesToImport** в файле конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="f8a80-254">The value of the **ModulesToImport** parameter of the `Register-PSSessionConfiguration` cmdlet takes precedence over the value of the **ModulesToImport** key in the session configuration file.</span></span>

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

### <span data-ttu-id="f8a80-255">-Маунтусердриве</span><span class="sxs-lookup"><span data-stu-id="f8a80-255">-MountUserDrive</span></span>

<span data-ttu-id="f8a80-256">Настраивает сеансы, использующие эту конфигурацию сеанса, для предоставления `User:` PSDrive.</span><span class="sxs-lookup"><span data-stu-id="f8a80-256">Configures sessions that use this session configuration to expose the `User:` PSDrive.</span></span> <span data-ttu-id="f8a80-257">Пользовательские диски уникальны для каждого подключающегося пользователя и позволяют пользователям копировать данные в конечные точки PowerShell и из них, даже если поставщик файловой системы не предоставляется.</span><span class="sxs-lookup"><span data-stu-id="f8a80-257">User drives are unique for each connecting user and allow users to copy data to and from PowerShell endpoints even if the File System provider is not exposed.</span></span> <span data-ttu-id="f8a80-258">Корни диска пользователя создаются в `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell\DriveRoots\` .</span><span class="sxs-lookup"><span data-stu-id="f8a80-258">User drive roots are created under `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell\DriveRoots\`.</span></span> <span data-ttu-id="f8a80-259">Для каждого пользователя, подключающегося к конечной точке, создается папка с именем `$env:USERDOMAIN_$env:USERNAME`.</span><span class="sxs-lookup"><span data-stu-id="f8a80-259">For each user connecting to the endpoint, a folder is created with the name `$env:USERDOMAIN_$env:USERNAME`.</span></span>

<span data-ttu-id="f8a80-260">Содержимое диска пользователя сохраняется во всех пользовательских сеансах и не удаляется автоматически.</span><span class="sxs-lookup"><span data-stu-id="f8a80-260">Contents in the user drive persist across user sessions and are not automatically removed.</span></span> <span data-ttu-id="f8a80-261">По умолчанию пользователи могут хранить до 50 МБ данных на диске пользователя.</span><span class="sxs-lookup"><span data-stu-id="f8a80-261">By default, users can only store up to 50MB of data in the user drive.</span></span> <span data-ttu-id="f8a80-262">Это можно настроить с помощью параметра **усердривемаксимумсизе** .</span><span class="sxs-lookup"><span data-stu-id="f8a80-262">This can be customized with the **UserDriveMaximumSize** parameter.</span></span>

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

### <span data-ttu-id="f8a80-263">-Path</span><span class="sxs-lookup"><span data-stu-id="f8a80-263">-Path</span></span>

<span data-ttu-id="f8a80-264">Указывает путь и имя файла конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="f8a80-264">Specifies the path and filename of the session configuration file.</span></span> <span data-ttu-id="f8a80-265">Файл должен иметь `.pssc` расширение имени файла.</span><span class="sxs-lookup"><span data-stu-id="f8a80-265">The file must have a `.pssc` file name extension.</span></span>

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

### <span data-ttu-id="f8a80-266">-PowerShellVersion</span><span class="sxs-lookup"><span data-stu-id="f8a80-266">-PowerShellVersion</span></span>

<span data-ttu-id="f8a80-267">Указывает версию обработчика PowerShell в сеансах, использующих конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="f8a80-267">Specifies the version of the PowerShell engine in sessions that use the session configuration.</span></span> <span data-ttu-id="f8a80-268">Допустимые значения для этого параметра: 2,0 и 3,0.</span><span class="sxs-lookup"><span data-stu-id="f8a80-268">The acceptable values for this parameter are: 2.0 and 3.0.</span></span> <span data-ttu-id="f8a80-269">Если опустить этот параметр, ключ **PowerShellVersion** будет снабжен комментариями и в сеансе будут выполняться новейшие версии PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f8a80-269">If you omit this parameter, the **PowerShellVersion** key is commented-out and newest version of PowerShell runs in the session.</span></span>

<span data-ttu-id="f8a80-270">Значение параметра **PSVersion** `Register-PSSessionConfiguration` командлета имеет приоритет над значением ключа **PowerShellVersion** в файле конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="f8a80-270">The value of the **PSVersion** parameter of the `Register-PSSessionConfiguration` cmdlet takes precedence over the value of the **PowerShellVersion** key in the session configuration file.</span></span>

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

### <span data-ttu-id="f8a80-271">-RequiredGroups</span><span class="sxs-lookup"><span data-stu-id="f8a80-271">-RequiredGroups</span></span>

<span data-ttu-id="f8a80-272">Указывает правила условного доступа для пользователей, подключающихся к сеансам, использующим эту конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="f8a80-272">Specifies conditional access rules for users connecting to sessions that use this session configuration.</span></span>

<span data-ttu-id="f8a80-273">Введите хэш-таблицу, чтобы составить список правил, используя только один ключ на Hashtable, "and" или "or", и присвоить значение массиву имен групп безопасности или дополнительных хэш-таблиц.</span><span class="sxs-lookup"><span data-stu-id="f8a80-273">Enter a hashtable to compose your list of rules using only 1 key per hashtable, 'And' or 'Or', and set the value to an array of security group names or additional hashtables.</span></span>

<span data-ttu-id="f8a80-274">Пример, при котором пользователи должны быть членами одной группы: `@{ And = 'MyRequiredGroup' }`</span><span class="sxs-lookup"><span data-stu-id="f8a80-274">Example requiring connecting users to be members of a single group: `@{ And = 'MyRequiredGroup' }`</span></span>

<span data-ttu-id="f8a80-275">Пример, в котором пользователи должны принадлежать к группе A или обеим группам B и C для доступа к конечной точке: `@{ Or = 'GroupA', @{ And = 'GroupB', 'GroupC' } }`</span><span class="sxs-lookup"><span data-stu-id="f8a80-275">Example requiring users to belong to group A, or both groups B and C, to access the endpoint: `@{ Or = 'GroupA', @{ And = 'GroupB', 'GroupC' } }`</span></span>

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

### <span data-ttu-id="f8a80-276">-RoleDefinitions</span><span class="sxs-lookup"><span data-stu-id="f8a80-276">-RoleDefinitions</span></span>

<span data-ttu-id="f8a80-277">Указывает сопоставление между группами безопасности (или пользователями) и возможностями ролей.</span><span class="sxs-lookup"><span data-stu-id="f8a80-277">Specifies the mapping between security groups (or users) and role capabilities.</span></span> <span data-ttu-id="f8a80-278">Пользователям будет предоставлен доступ ко всем возможностям ролей, которые применяются к их членству в группе во время создания сеанса.</span><span class="sxs-lookup"><span data-stu-id="f8a80-278">Users will be granted access to all role capabilities which apply to their group membership at the time the session is created.</span></span>

<span data-ttu-id="f8a80-279">Введите хэш-таблицу, в которой ключи являются именем группы безопасности, а значения — хэш-таблицами, которые содержат список возможностей роли, которые должны быть доступны группе безопасности.</span><span class="sxs-lookup"><span data-stu-id="f8a80-279">Enter a hash table in which the keys are the name of the security group and the values are hash tables that contain a list of role capabilities that should be made available to the security group.</span></span>

<span data-ttu-id="f8a80-280">Пример: `@{'Contoso\Level 2 Helpdesk Users' = @{ RoleCapabilities = 'Maintenance', 'ADHelpDesk' }}`</span><span class="sxs-lookup"><span data-stu-id="f8a80-280">For example: `@{'Contoso\Level 2 Helpdesk Users' = @{ RoleCapabilities = 'Maintenance', 'ADHelpDesk' }}`</span></span>

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

### <span data-ttu-id="f8a80-281">-RunAsVirtualAccount</span><span class="sxs-lookup"><span data-stu-id="f8a80-281">-RunAsVirtualAccount</span></span>

<span data-ttu-id="f8a80-282">Настраивает сеансы, использующие эту конфигурацию сеанса, в качестве учетной записи администратора компьютера (виртуального).</span><span class="sxs-lookup"><span data-stu-id="f8a80-282">Configures sessions using this session configuration to be run as the computer's (virtual) administrator account.</span></span> <span data-ttu-id="f8a80-283">Это поле нельзя использовать с параметром **граупманажедсервицеаккаунт** .</span><span class="sxs-lookup"><span data-stu-id="f8a80-283">This field cannot be used with the **GroupManagedServiceAccount** parameter.</span></span>

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

### <span data-ttu-id="f8a80-284">-Рунасвиртуалаккаунтграупс</span><span class="sxs-lookup"><span data-stu-id="f8a80-284">-RunAsVirtualAccountGroups</span></span>

<span data-ttu-id="f8a80-285">Указывает группы безопасности, которые будут связаны с виртуальной учетной записью, если сеанс, использующий конфигурацию сеанса, выполняется как виртуальная учетная запись.</span><span class="sxs-lookup"><span data-stu-id="f8a80-285">Specifies the security groups to be associated with the virtual account when a session that uses the session configuration is run as a virtual account.</span></span> <span data-ttu-id="f8a80-286">Если этот параметр не указан, виртуальная учетная запись принадлежит администраторам домена на контроллерах домена и администраторах на всех остальных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="f8a80-286">If omitted, the virtual account belongs to Domain Admins on domain controllers and Administrators on all other computers.</span></span>

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

### <span data-ttu-id="f8a80-287">-SchemaVersion</span><span class="sxs-lookup"><span data-stu-id="f8a80-287">-SchemaVersion</span></span>

<span data-ttu-id="f8a80-288">Указывает версию схемы файла конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="f8a80-288">Specifies the version of the session configuration file schema.</span></span> <span data-ttu-id="f8a80-289">Значение по умолчанию: 1.0.0.0.</span><span class="sxs-lookup"><span data-stu-id="f8a80-289">The default value is "1.0.0.0".</span></span>

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

### <span data-ttu-id="f8a80-290">-ScriptsToProcess</span><span class="sxs-lookup"><span data-stu-id="f8a80-290">-ScriptsToProcess</span></span>

<span data-ttu-id="f8a80-291">Добавляет указанные сценарии в сеансы, использующие конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="f8a80-291">Adds the specified scripts to sessions that use the session configuration.</span></span> <span data-ttu-id="f8a80-292">Введите путь и имена файлов сценариев.</span><span class="sxs-lookup"><span data-stu-id="f8a80-292">Enter the path and file names of the scripts.</span></span> <span data-ttu-id="f8a80-293">Значение этого параметра должно быть полным или абсолютным путем к именам файлов скриптов.</span><span class="sxs-lookup"><span data-stu-id="f8a80-293">The value of this parameter must be a full or absolute path of script file names.</span></span>

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

### <span data-ttu-id="f8a80-294">-SessionType</span><span class="sxs-lookup"><span data-stu-id="f8a80-294">-SessionType</span></span>

<span data-ttu-id="f8a80-295">Указывает тип сеанса, создаваемого при использовании конфигурации сеанса.</span><span class="sxs-lookup"><span data-stu-id="f8a80-295">Specifies the type of session that is created by using the session configuration.</span></span> <span data-ttu-id="f8a80-296">Значение по умолчанию — Default.</span><span class="sxs-lookup"><span data-stu-id="f8a80-296">The default value is Default.</span></span> <span data-ttu-id="f8a80-297">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="f8a80-297">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="f8a80-298">Пусто. модули по умолчанию не добавляются в сеанс.</span><span class="sxs-lookup"><span data-stu-id="f8a80-298">Empty - No modules are added to session by default.</span></span> <span data-ttu-id="f8a80-299">Параметры этого командлета позволяют добавить в сеанс модули, функции, скрипты и другие элементы.</span><span class="sxs-lookup"><span data-stu-id="f8a80-299">Use the parameters of this cmdlet to add modules, functions, scripts, and other features to the session.</span></span> <span data-ttu-id="f8a80-300">Этот параметр предназначен для создания пользовательских сеансов путем добавления выбранных команд.</span><span class="sxs-lookup"><span data-stu-id="f8a80-300">This option is designed for you to create custom sessions by adding selected commands.</span></span> <span data-ttu-id="f8a80-301">Если вы не добавите команды в пустой сеанс, сеанс ограничивается выражениями и может не работать.</span><span class="sxs-lookup"><span data-stu-id="f8a80-301">If you do not add commands to an empty session, the session is limited to expressions and might not be usable.</span></span>
- <span data-ttu-id="f8a80-302">По умолчанию — добавляет модуль Microsoft. PowerShell. Core в сеанс.</span><span class="sxs-lookup"><span data-stu-id="f8a80-302">Default - Adds the Microsoft.PowerShell.Core module to the session.</span></span> <span data-ttu-id="f8a80-303">Этот модуль включает `Import-Module` командлет, который пользователи могут использовать для импорта других модулей, если этот командлет явно не запрещен.</span><span class="sxs-lookup"><span data-stu-id="f8a80-303">This module includes the `Import-Module` cmdlet that users can use to import other modules unless you explicitly prohibit this cmdlet.</span></span>
- <span data-ttu-id="f8a80-304">RestrictedRemoteServer.</span><span class="sxs-lookup"><span data-stu-id="f8a80-304">RestrictedRemoteServer.</span></span> <span data-ttu-id="f8a80-305">Включает в себя только следующие функции-посредники: `Exit-PSSession` ,,,,, и `Get-Command` `Get-FormatData` `Get-Help` `Measure-Object` `Out-Default` `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="f8a80-305">Includes only the following proxy functions: `Exit-PSSession`, `Get-Command`, `Get-FormatData`, `Get-Help`, `Measure-Object`, `Out-Default`, and `Select-Object`.</span></span>
  <span data-ttu-id="f8a80-306">Параметры этого командлета позволяют добавить в сеанс модули, функции, скрипты и другие элементы.</span><span class="sxs-lookup"><span data-stu-id="f8a80-306">Use the parameters of this cmdlet to add modules, functions, scripts, and other features to the session.</span></span>

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

### <span data-ttu-id="f8a80-307">-TranscriptDirectory</span><span class="sxs-lookup"><span data-stu-id="f8a80-307">-TranscriptDirectory</span></span>

<span data-ttu-id="f8a80-308">Указывает каталог для размещения записей сеанса для сеансов, использующих эту конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="f8a80-308">Specifies the directory to place session transcripts for sessions using this session configuration.</span></span>

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

### <span data-ttu-id="f8a80-309">-TypesToProcess</span><span class="sxs-lookup"><span data-stu-id="f8a80-309">-TypesToProcess</span></span>

<span data-ttu-id="f8a80-310">Добавляет указанные `.ps1xml` файлы типов в сеансы, которые используют конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="f8a80-310">Adds the specified `.ps1xml` type files to sessions that use the session configuration.</span></span> <span data-ttu-id="f8a80-311">Введите имена файлов.</span><span class="sxs-lookup"><span data-stu-id="f8a80-311">Enter the type filenames.</span></span> <span data-ttu-id="f8a80-312">Значение этого параметра должно быть полным или абсолютным путем к типу filename.</span><span class="sxs-lookup"><span data-stu-id="f8a80-312">The value of this parameter must be a full or absolute path to type filenames.</span></span>

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

### <span data-ttu-id="f8a80-313">-Усердривемаксимумсизе</span><span class="sxs-lookup"><span data-stu-id="f8a80-313">-UserDriveMaximumSize</span></span>

<span data-ttu-id="f8a80-314">Указывает максимальный размер для дисков пользователей, доступных в сеансах, использующих эту конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="f8a80-314">Specifies the maximum size for user drives exposed in sessions that use this session configuration.</span></span>
<span data-ttu-id="f8a80-315">Если этот параметр опущен, размер каждого корня диска по умолчанию `User:` — 50 МБ.</span><span class="sxs-lookup"><span data-stu-id="f8a80-315">When omitted, the default size of each `User:` drive root is 50MB.</span></span>

<span data-ttu-id="f8a80-316">Этот параметр следует использовать с **маунтусердриве**.</span><span class="sxs-lookup"><span data-stu-id="f8a80-316">This parameter should be used with **MountUserDrive**.</span></span>

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

### <span data-ttu-id="f8a80-317">-VariableDefinitions</span><span class="sxs-lookup"><span data-stu-id="f8a80-317">-VariableDefinitions</span></span>

<span data-ttu-id="f8a80-318">Добавляет указанные переменные в сеансы, использующие конфигурацию сеанса.</span><span class="sxs-lookup"><span data-stu-id="f8a80-318">Adds the specified variables to sessions that use the session configuration.</span></span> <span data-ttu-id="f8a80-319">Введите хэш-таблицу со следующими разделами:</span><span class="sxs-lookup"><span data-stu-id="f8a80-319">Enter a hash table with the following keys:</span></span>

- <span data-ttu-id="f8a80-320">Name — имя переменной.</span><span class="sxs-lookup"><span data-stu-id="f8a80-320">Name - Name of the variable.</span></span> <span data-ttu-id="f8a80-321">Этот раздел обязателен.</span><span class="sxs-lookup"><span data-stu-id="f8a80-321">This key is required.</span></span>
- <span data-ttu-id="f8a80-322">Значение — значение переменной.</span><span class="sxs-lookup"><span data-stu-id="f8a80-322">Value - Variable value.</span></span> <span data-ttu-id="f8a80-323">Этот раздел обязателен.</span><span class="sxs-lookup"><span data-stu-id="f8a80-323">This key is required.</span></span>
- <span data-ttu-id="f8a80-324">Параметры — параметры переменных.</span><span class="sxs-lookup"><span data-stu-id="f8a80-324">Options - Variable options.</span></span> <span data-ttu-id="f8a80-325">Этот раздел необязателен.</span><span class="sxs-lookup"><span data-stu-id="f8a80-325">This key is optional.</span></span> <span data-ttu-id="f8a80-326">Значение по умолчанию — **None**.</span><span class="sxs-lookup"><span data-stu-id="f8a80-326">The default value is **None**.</span></span> <span data-ttu-id="f8a80-327">Допустимые значения для этого параметра: None, ReadOnly, Constant, private или AllScope.</span><span class="sxs-lookup"><span data-stu-id="f8a80-327">The acceptable values for this parameter are: None, ReadOnly, Constant, Private, or AllScope.</span></span>

<span data-ttu-id="f8a80-328">Пример: `@{Name='WarningPreference';Value='SilentlyContinue';Options='AllScope'}`</span><span class="sxs-lookup"><span data-stu-id="f8a80-328">For example: `@{Name='WarningPreference';Value='SilentlyContinue';Options='AllScope'}`</span></span>

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

### <span data-ttu-id="f8a80-329">-VisibleAliases</span><span class="sxs-lookup"><span data-stu-id="f8a80-329">-VisibleAliases</span></span>

<span data-ttu-id="f8a80-330">Ограничивает псевдонимы в сеансе теми, которые указаны в значении этого параметра, а также всеми псевдонимами, определенными в параметре **AliasDefinition**.</span><span class="sxs-lookup"><span data-stu-id="f8a80-330">Limits the aliases in the session to those specified in the value of this parameter, plus any aliases that you define in the **AliasDefinition** parameter.</span></span> <span data-ttu-id="f8a80-331">Поддерживаются подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="f8a80-331">Wildcard characters are supported.</span></span> <span data-ttu-id="f8a80-332">По умолчанию все псевдонимы, определенные подсистемой PowerShell и все псевдонимы, которые экспортируются модулями, видимы в сеансе.</span><span class="sxs-lookup"><span data-stu-id="f8a80-332">By default, all aliases that are defined by the PowerShell engine and all aliases that modules export are visible in the session.</span></span>

<span data-ttu-id="f8a80-333">Пример: `VisibleAliases='gcm', 'gp'`</span><span class="sxs-lookup"><span data-stu-id="f8a80-333">For example: `VisibleAliases='gcm', 'gp'`</span></span>

<span data-ttu-id="f8a80-334">Если любой **видимый** параметр включен в файл конфигурации сеанса, PowerShell удаляет `Import-Module` командлет и его псевдоним IPMO из сеанса.</span><span class="sxs-lookup"><span data-stu-id="f8a80-334">When any **Visible** parameter is included in the session configuration file, PowerShell removes the `Import-Module` cmdlet and its ipmo alias from the session.</span></span>

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

### <span data-ttu-id="f8a80-335">-VisibleCmdlets</span><span class="sxs-lookup"><span data-stu-id="f8a80-335">-VisibleCmdlets</span></span>

<span data-ttu-id="f8a80-336">Ограничивает командлеты в сеансе теми, которые указаны в значении этого параметра.</span><span class="sxs-lookup"><span data-stu-id="f8a80-336">Limits the cmdlets in the session to those specified in the value of this parameter.</span></span> <span data-ttu-id="f8a80-337">Поддерживаются подстановочные знаки и полные имена модулей.</span><span class="sxs-lookup"><span data-stu-id="f8a80-337">Wildcard characters and Module Qualified Names are supported.</span></span>

<span data-ttu-id="f8a80-338">По умолчанию все командлеты, экспортируемые модулями в сеансе, отображаются в сеансе.</span><span class="sxs-lookup"><span data-stu-id="f8a80-338">By default, all cmdlets that modules in the session export are visible in the session.</span></span> <span data-ttu-id="f8a80-339">Используйте параметры **SessionType** и **ModulesToImport**, чтобы определить, какие модули и оснастки импортируются в сеанс.</span><span class="sxs-lookup"><span data-stu-id="f8a80-339">Use the **SessionType** and **ModulesToImport** parameters to determine which modules and snap-ins are imported into the session.</span></span> <span data-ttu-id="f8a80-340">Если ни один из модулей в **ModulesToImport** не предоставляет командлет, соответствующий модуль будет пытаться выполнить автозагрузку.</span><span class="sxs-lookup"><span data-stu-id="f8a80-340">If no modules in **ModulesToImport** expose the cmdlet, the appropriate module will attempt to be autoloaded.</span></span>

<span data-ttu-id="f8a80-341">Если любой **видимый** параметр включен в файл конфигурации сеанса, PowerShell удаляет `Import-Module` командлет и его псевдоним IPMO из сеанса.</span><span class="sxs-lookup"><span data-stu-id="f8a80-341">When any **Visible** parameter is included in the session configuration file, PowerShell removes the `Import-Module` cmdlet and its ipmo alias from the session.</span></span>

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

### <span data-ttu-id="f8a80-342">-VisibleExternalCommands</span><span class="sxs-lookup"><span data-stu-id="f8a80-342">-VisibleExternalCommands</span></span>

<span data-ttu-id="f8a80-343">Ограничивает внешние двоичные файлы, скрипты и команды, которые могут выполняться в сеансе, с теми, которые указаны в значении этого параметра.</span><span class="sxs-lookup"><span data-stu-id="f8a80-343">Limits the external binaries, scripts, and commands that can be executed in the session to those specified in the value of this parameter.</span></span> <span data-ttu-id="f8a80-344">Поддерживаются подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="f8a80-344">Wildcard characters are supported.</span></span>

<span data-ttu-id="f8a80-345">По умолчанию в сеансе не отображаются никакие внешние команды.</span><span class="sxs-lookup"><span data-stu-id="f8a80-345">By default, no external commands are visible in the session.</span></span>

<span data-ttu-id="f8a80-346">Если любой **видимый** параметр включен в файл конфигурации сеанса, PowerShell удаляет `Import-Module` командлет и его псевдоним IPMO из сеанса.</span><span class="sxs-lookup"><span data-stu-id="f8a80-346">When any **Visible** parameter is included in the session configuration file, PowerShell, removes the `Import-Module` cmdlet and its ipmo alias from the session.</span></span>

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

### <span data-ttu-id="f8a80-347">-VisibleFunctions</span><span class="sxs-lookup"><span data-stu-id="f8a80-347">-VisibleFunctions</span></span>

<span data-ttu-id="f8a80-348">Ограничивает функции в сеансе теми, которые указаны в значении этого параметра, а также всеми функциями, определенными в параметре **FunctionDefinition**.</span><span class="sxs-lookup"><span data-stu-id="f8a80-348">Limits the functions in the session to those specified in the value of this parameter, plus any functions that you define in the **FunctionDefinition** parameter.</span></span> <span data-ttu-id="f8a80-349">Поддерживаются подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="f8a80-349">Wildcard characters are supported.</span></span>

<span data-ttu-id="f8a80-350">По умолчанию все функции, экспортируемые модулями в сеансе, отображаются в сеансе.</span><span class="sxs-lookup"><span data-stu-id="f8a80-350">By default, all functions that modules in the session export are visible in the session.</span></span> <span data-ttu-id="f8a80-351">Используйте параметры **SessionType** и **ModulesToImport**, чтобы определить, какие модули и оснастки импортируются в сеанс.</span><span class="sxs-lookup"><span data-stu-id="f8a80-351">Use the **SessionType** and **ModulesToImport** parameters to determine which modules and snap-ins are imported into the session.</span></span>

<span data-ttu-id="f8a80-352">Если любой **видимый** параметр включен в файл конфигурации сеанса, PowerShell удаляет `Import-Module` командлет и его псевдоним IPMO из сеанса.</span><span class="sxs-lookup"><span data-stu-id="f8a80-352">When any **Visible** parameter is included in the session configuration file, PowerShell removes the `Import-Module` cmdlet and its ipmo alias from the session.</span></span>

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

### <span data-ttu-id="f8a80-353">-VisibleProviders</span><span class="sxs-lookup"><span data-stu-id="f8a80-353">-VisibleProviders</span></span>

<span data-ttu-id="f8a80-354">Ограничивает поставщиков PowerShell в сеансе теми, которые указаны в значении этого параметра.</span><span class="sxs-lookup"><span data-stu-id="f8a80-354">Limits the PowerShell providers in the session to those specified in the value of this parameter.</span></span>
<span data-ttu-id="f8a80-355">Поддерживаются подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="f8a80-355">Wildcard characters are supported.</span></span>

<span data-ttu-id="f8a80-356">По умолчанию все поставщики, экспортируемые модулями в сеансе, отображаются в сеансе.</span><span class="sxs-lookup"><span data-stu-id="f8a80-356">By default, all providers that modules in the session export are visible in the session.</span></span> <span data-ttu-id="f8a80-357">Используйте параметры **SessionType** и **ModulesToImport** , чтобы определить, какие модули импортируются в сеанс.</span><span class="sxs-lookup"><span data-stu-id="f8a80-357">Use the **SessionType** and **ModulesToImport** parameters to determine which modules are imported into the session.</span></span>

<span data-ttu-id="f8a80-358">Если любой **видимый** параметр включен в файл конфигурации сеанса, PowerShell удаляет `Import-Module` командлет и его `ipmo` псевдоним из сеанса.</span><span class="sxs-lookup"><span data-stu-id="f8a80-358">When any **Visible** parameter is included in the session configuration file, PowerShell removes the `Import-Module` cmdlet and its `ipmo` alias from the session.</span></span>

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

### <span data-ttu-id="f8a80-359">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="f8a80-359">CommonParameters</span></span>

<span data-ttu-id="f8a80-360">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f8a80-360">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f8a80-361">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f8a80-361">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f8a80-362">Входные данные</span><span class="sxs-lookup"><span data-stu-id="f8a80-362">INPUTS</span></span>

### <span data-ttu-id="f8a80-363">None</span><span class="sxs-lookup"><span data-stu-id="f8a80-363">None</span></span>

<span data-ttu-id="f8a80-364">В этот командлет нельзя передать по конвейеру ни один объект.</span><span class="sxs-lookup"><span data-stu-id="f8a80-364">You cannot pipe any objects to this cmdlet.</span></span>

## <span data-ttu-id="f8a80-365">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="f8a80-365">OUTPUTS</span></span>

### <span data-ttu-id="f8a80-366">None</span><span class="sxs-lookup"><span data-stu-id="f8a80-366">None</span></span>

<span data-ttu-id="f8a80-367">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="f8a80-367">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="f8a80-368">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="f8a80-368">NOTES</span></span>

<span data-ttu-id="f8a80-369">Этот командлет доступен только на платформах Windows.</span><span class="sxs-lookup"><span data-stu-id="f8a80-369">This cmdlet is only available on Windows platforms.</span></span>

- <span data-ttu-id="f8a80-370">Параметры, такие как **VisibleCmdlets** и **VisibleProviders**, не импортируют элементы в сеанс.</span><span class="sxs-lookup"><span data-stu-id="f8a80-370">Parameters, such as **VisibleCmdlets** and **VisibleProviders**, do not import items into the session.</span></span> <span data-ttu-id="f8a80-371">Вместо этого они отбирают элементы, импортированные в сеанс.</span><span class="sxs-lookup"><span data-stu-id="f8a80-371">Instead, they select from among the items imported into the session.</span></span> <span data-ttu-id="f8a80-372">Например, если значение параметра **VisibleProviders** является поставщиком сертификата, но в параметре **ModulesToImport** не указан модуль **Microsoft. PowerShell. Security** , который содержит поставщик сертификата, то поставщик сертификата не отображается в сеансе.</span><span class="sxs-lookup"><span data-stu-id="f8a80-372">For example, if the value of the **VisibleProviders** parameter is the Certificate provider, but the **ModulesToImport** parameter does not specify the **Microsoft.PowerShell.Security** module that contains the Certificate provider, the Certificate provider is not visible in the session.</span></span>
- <span data-ttu-id="f8a80-373">`New-PSSessionConfigurationFile` создает файл конфигурации сеанса с расширением имени файла pssc в пути, указанном в параметре **path** .</span><span class="sxs-lookup"><span data-stu-id="f8a80-373">`New-PSSessionConfigurationFile` creates a session configuration file that has a .pssc file name extension in the path that you specify in the **Path** parameter.</span></span> <span data-ttu-id="f8a80-374">При использовании файла конфигурации сеанса для создания конфигурации сеанса `Register-PSSessionConfiguration` командлет копирует файл конфигурации и сохраняет активную копию файла в подкаталоге **сессионконфиг** `$PSHOME` каталога.</span><span class="sxs-lookup"><span data-stu-id="f8a80-374">When you use the session configuration file to create a session configuration, the `Register-PSSessionConfiguration` cmdlet copies the configuration file and saves an active copy of the file in the **SessionConfig** subdirectory of the `$PSHOME` directory.</span></span>

  <span data-ttu-id="f8a80-375">Свойство **конфигфилепас** конфигурации сеанса содержит полный путь к файлу конфигурации активного сеанса.</span><span class="sxs-lookup"><span data-stu-id="f8a80-375">The **ConfigFilePath** property of the session configuration contains the fully qualified path of the active session configuration file.</span></span> <span data-ttu-id="f8a80-376">Активный файл конфигурации в каталоге можно изменить в `$PSHOME` любое время с помощью любого текстового редактора.</span><span class="sxs-lookup"><span data-stu-id="f8a80-376">You can modify the active configuration file in the `$PSHOME` directory at any time using any text editor.</span></span> <span data-ttu-id="f8a80-377">Внесенные изменения влияют на все новые сеансы, которые используют конфигурацию сеанса, но не на текущие сеансы.</span><span class="sxs-lookup"><span data-stu-id="f8a80-377">The changes that you make affect all new sessions that use the session configuration, but not existing sessions.</span></span>

  <span data-ttu-id="f8a80-378">Прежде чем использовать измененный файл конфигурации сеанса, используйте `Test-PSSessionConfigurationFile` командлет, чтобы проверить допустимость записей в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f8a80-378">Before using an edited session configuration file, use the `Test-PSSessionConfigurationFile` cmdlet to verify that the configuration file entries are valid.</span></span>

## <span data-ttu-id="f8a80-379">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="f8a80-379">RELATED LINKS</span></span>

[<span data-ttu-id="f8a80-380">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="f8a80-380">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="f8a80-381">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="f8a80-381">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="f8a80-382">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="f8a80-382">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="f8a80-383">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="f8a80-383">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="f8a80-384">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="f8a80-384">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="f8a80-385">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="f8a80-385">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="f8a80-386">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="f8a80-386">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="f8a80-387">Поставщик WSMan</span><span class="sxs-lookup"><span data-stu-id="f8a80-387">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="f8a80-388">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="f8a80-388">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="f8a80-389">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="f8a80-389">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)
