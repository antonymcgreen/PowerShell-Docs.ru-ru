---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/24/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-pssessionconfigurationfile?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSSessionConfigurationFile
ms.openlocfilehash: 939dc011307b4c98340bb376032b96289e1c1bc3
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2020
ms.locfileid: "94345958"
---
# New-PSSessionConfigurationFile

## Краткий обзор
Создает файл, определяющий конфигурацию сеанса.

## SYNTAX

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

## DESCRIPTION

`New-PSSessionConfigurationFile`Командлет создает файл параметров, определяющих конфигурацию сеанса и среду сеансов, которые создаются с помощью конфигурации сеанса.
Чтобы использовать файл в конфигурации сеанса, используйте параметр **path** `Register-PSSessionConfiguration` `Set-PSSessionConfiguration` командлетов или.

Создаваемый файл конфигурации сеанса `New-PSSessionConfigurationFile` является текстовым файлом, доступным для чтения, который содержит хэш-таблицу свойств и значений конфигурации сеанса. Файл имеет `.pssc` расширение имени файла.

Все параметры `New-PSSessionConfigurationFile` являются необязательными, за исключением параметра **path** .
Если параметр пропущен, соответствующий ключ в файле конфигурации сеанса преобразуется в комментарий (за исключением указанных в описании параметра).

Конфигурация сеанса, также известная как конечная точка, представляет собой набор параметров на локальном компьютере, определяющий среду для сеансов PowerShell ( **PSSession** ), которые подключаются к компьютеру. Все **PSSession** используют конфигурацию сеанса. Чтобы указать определенную конфигурацию сеанса, используйте параметр **configurationName** командлетов, которые создают сеанс, например `New-PSSession` командлет.

Файл конфигурации сеанса позволяет легко определить конфигурацию сеанса без сложных скриптов или сборок кода. Параметры в файле используются с необязательным сценарием запуска и всеми сборками в конфигурации сеанса.

Дополнительные сведения о конфигурациях сеансов и файлах конфигурации сеанса см. в разделе [about_Session_Configurations](About/about_Session_Configurations.md) и [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).

Этот командлет появился в PowerShell 3,0.

## Примеры

### Пример 1. Создание и использование сеанса на языке

В этом примере показано, как создать и увидеть последствия использования сеанса без языка.

Для этого нужно выполнить следующие действия:

1. Создайте новый файл конфигурации.
1. Зарегистрируйте конфигурацию.
1. Создайте новый сеанс, использующий конфигурацию.
1. Выполните команды в этом новом сеансе.

Чтобы выполнить команды в этом примере, запустите PowerShell с параметром Запуск от имени администратора. Этот параметр необходим для выполнения `Register-PSSessionConfiguration` командлета.

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

В этом примере `Invoke-Command` происходит сбой, так как для **лангуажемоде** задано значение " **неязыковый** ".

### Пример 2. Создание и использование сеанса Рестриктедлангуаже

В этом примере показано, как создать и увидеть последствия использования сеанса без языка.

Для этого нужно выполнить следующие действия:

1. Создайте новый файл конфигурации.
1. Зарегистрируйте конфигурацию.
1. Создайте новый сеанс, использующий конфигурацию.
1. Выполните команды в этом новом сеансе.

Чтобы выполнить команды в этом примере, запустите PowerShell с параметром Запуск от имени администратора. Этот параметр необходим для выполнения `Register-PSSessionConfiguration` командлета.

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

В этом примере объект `Invoke-Command` выполняется, так как для **лангуажемоде** задано значение **рестриктедлангуаже**.

### Пример 3. Изменение файла конфигурации сеанса

В этом примере показано, как изменить файл конфигурации сеанса, используемый в существующем сеансе с именем «ITTasks». Ранее в этих сеансах были только основные модули и внутренний модуль **ITTasks** . Администратор хочет добавить модуль **PSScheduledJob** в сеансы, созданные с помощью конфигурации сеанса ITTasks.

```powershell
New-PSSessionConfigurationFile -Path .\New-ITTasks.pssc -ModulesToImport Microsoft*, ITTasks, PSScheduledJob
Set-PSSessionConfiguration -Name ITTasks -Path .\New-ITTasks.pssc
```

`New-PSSessionConfigurationFile`Командлет для создания файла конфигурации сеанса, который импортирует необходимые модули. `Set-PSSessionConfiguration`Командлет заменяет текущий файл конфигурации новым. Эта новая конфигурация влияет только на новые сеансы, созданные после изменения.
Существующие сеансы "ITTasks" не затрагиваются.

### Пример 4. Редактирование файла конфигурации сеанса

В этом примере показано, как изменить конфигурацию сеанса путем редактирования копии конфигурации активного сеанса из файла конфигурации. Чтобы изменить копию конфигурации сеанса файла конфигурации, необходимо иметь полный доступ к файлу. Для этого может потребоваться изменить разрешения для файла.

В этом сценарии мы хотим добавить новый псевдоним для `Select-String` командлета, изменив активный файл конфигурации.

Приведенный ниже пример кода выполняет следующие действия для внесения этого изменения:

1. Получите путь к файлу конфигурации для сеанса Итконфиг.
1. Пользователь редактирует файл конфигурации с помощью **Notepad.exe** для изменения значения **алиасдефинитионс** следующим образом: `AliasDefinitions = @(@{Name='slst';Value='Select-String'})` .
1. Протестируйте обновленный файл конфигурации.

```powershell
$ITConfig = Get-PSSessionConfiguration -Name ITConfig
notepad.exe $ITConfig.ConfigFilePath
Test-PSSessionConfigurationFile -Path $ITConfig.ConfigFilePath
```

```Output
True
```

Используйте параметр **verbose** с для, `Test-PSSessionConfigurationFile` чтобы отобразить обнаруженные ошибки. Командлет возвращает, `$True` Если в файле не обнаружены ошибки.

### Пример 5. Создание образца файла конфигурации

В этом примере показана `New-PSSessionConfigurationFile` команда, использующая все параметры командлета.
Она включена в пример, чтобы показать правильный входной формат для каждого параметра.

Получившийся файл SampleFile.pssc отображается в выходных данных.

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

## PARAMETERS

### -AliasDefinitions

Добавляет указанные псевдонимы сеансы, использующие конфигурацию сеанса. Введите хэш-таблицу со следующими разделами:

- Name — имя псевдонима. Этот раздел обязателен.
- Value — команда, которую представляет псевдоним. Этот раздел обязателен.
- Описание — текстовая строка, описывающая псевдоним. Этот раздел необязателен.
- Параметры — параметры псевдонимов. Этот раздел необязателен. Значение по умолчанию — **None**. Допустимые значения для этого параметра: None, ReadOnly, Constant, private или AllScope.

Пример: `@{Name='hlp';Value='Get-Help';Description='Gets help';Options='ReadOnly'}`

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

### -AssembliesToLoad

Задает сборки для загрузки в сеансы, которые используют конфигурацию сеанса.

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

### -Author

Указывает автора конфигурации сеанса или файла конфигурации. По умолчанию используется текущий пользователь. Значение этого параметра отображается в файле конфигурации сеанса, но не является свойством объекта конфигурации сеанса.

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

### -CompanyName

Указывает компанию, которая создала конфигурацию сеанса или файл конфигурации. Значение по умолчанию — **Unknown**. Значение этого параметра отображается в файле конфигурации сеанса, но не является свойством объекта конфигурации сеанса.

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

### -Copyright

Указывает авторские права на файл конфигурации сеанса. Значение этого параметра отображается в файле конфигурации сеанса, но не является свойством объекта конфигурации сеанса.

Если опустить этот параметр, `New-PSSessionConfigurationFile` создает заявление об авторских правах с помощью значения параметра **Author** .

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

### -Description

Задает описание конфигурации сеанса или файла конфигурации сеанса. Значение этого параметра отображается в файле конфигурации сеанса, но не является свойством объекта конфигурации сеанса.

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

### -EnvironmentVariables

Добавляет переменные среды в сеанс. Введите хэш-таблицу, в которой разделами являются имена переменных среды, а значениями — значения переменных среды.

Пример: `EnvironmentVariables=@{TestShare='\\Server01\TestShare'}`

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

### -ExecutionPolicy

Указывает политику выполнения сеансов, использующих конфигурацию сеанса. Если опустить этот параметр, значение ключа **ExecutionPolicy** в файле конфигурации сеанса будет **ограничено**. Дополнительные сведения о политиках выполнения в PowerShell см. в разделе [about_Execution_Policies](about/about_Execution_Policies.md).

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

### -FormatsToProcess

Указывает файлы форматирования (PS1XML-файлы), выполняющиеся в сеансах, которые используют конфигурацию сеанса.
Значение этого параметра должно быть полным или абсолютным путем к файлам форматирования.

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

### -Full

Указывает, что эта операция включает все возможные свойства конфигурации в файле конфигурации сеанса.

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

### -FunctionDefinitions

Добавляет в сеансы указанные функции, использующие конфигурацию сеанса. Введите хэш-таблицу со следующими разделами:

- Name — имя функции. Этот раздел обязателен.
- ScriptBlock — тело функции. Введите блок сценария. Этот раздел обязателен.
- Параметры — параметры функции. Этот раздел необязателен. Значение по умолчанию — **None**. Допустимые значения для этого параметра: None, ReadOnly, Constant, private или AllScope.

Пример: `@{Name='Get-PowerShellProcess';ScriptBlock={Get-Process PowerShell};Options='AllScope'}`

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

### -Граупманажедсервицеаккаунт

Настраивает сеансы, использующие эту конфигурацию сеанса, для запуска в контексте указанной групповой управляемой учетной записи службы. Компьютер, на котором зарегистрирована эта конфигурация сеанса, должен иметь разрешение на запрос пароля gMSA для успешного создания сеансов. Это поле нельзя использовать с параметром **RunAsVirtualAccount** .

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

### -Guid

Указывает уникальный идентификатор для файла конфигурации сеанса. Если опустить этот параметр, `New-PSSessionConfigurationFile` создает идентификатор GUID для файла. Чтобы создать новый GUID в PowerShell, введите `New-Guid` .

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

### -LanguageMode

Определяет, какие элементы языка PowerShell разрешены в сеансах, использующих эту конфигурацию сеанса. Этот параметр можно использовать для ограничения команд, которые определенные пользователи могут выполнять на компьютере.

Допустимые значения для этого параметра:

- Фулллангуаже — разрешены все языковые элементы.
- ConstrainedLanguage — команды, содержащие скрипты для оценки, не допускаются. Режим ConstrainedLanguage ограничивает доступ пользователя к типам, объектам или методам Microsoft .NET Framework.
- Неязыковый — пользователи могут запускать командлеты и функции, но не могут использовать элементы языка, такие как блоки скриптов, переменные или операторы.
- Рестриктедлангуаже — пользователи могут запускать командлеты и функции, но не могут использовать блоки скриптов или переменные, за исключением следующих разрешенных переменных: `$PSCulture` , `$PSUICulture` , `$True` , `$False` и `$Null` . Пользователи могут использовать только базовые операторы сравнения ( `-eq` , `-gt` , `-lt` ). Операторы присваивания, ссылки на свойство и вызовы методов не разрешены.

Значение параметра **LanguageMode** по умолчанию зависит от значения параметра **SessionType**.

- Пустой-неязык
- RestrictedRemoteServer-неязык
- По умолчанию — Фулллангуаже

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

### -ModulesToImport

Указывает модули и оснастки, которые автоматически импортируются в сеансы, использующие конфигурацию сеанса.

По умолчанию только оснастка **Microsoft. PowerShell. Core** импортируется в удаленные сеансы, но если эти командлеты не исключены, пользователи могут использовать `Import-Module` `Add-PSSnapin` командлеты и для добавления модулей и оснасток в сеанс.

Каждый модуль или оснастка в значении этого параметра может быть представлен в виде строки или хэш-таблицы. Строка модуля состоит из имени модуля или оснастки. Хэш-таблица модуля может включать разделы **ModuleName** , **ModuleVersion** и **GUID**. Обязателен только раздел **ModuleName**.

Например, следующее значение состоит из строки и хэш-таблицы. Допустимо любое сочетание строк и хэш-таблиц в любом порядке.

`'TroubleshootingPack', @{ModuleName='PSDiagnostics'; ModuleVersion='1.0.0.0';GUID='c61d6278-02a3-4618-ae37-a524d40a7f44'}`

Значение параметра **ModulesToImport** `Register-PSSessionConfiguration` командлета имеет приоритет над значением ключа **ModulesToImport** в файле конфигурации сеанса.

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

### -Маунтусердриве

Настраивает сеансы, использующие эту конфигурацию сеанса, для предоставления `User:` PSDrive. Пользовательские диски уникальны для каждого подключающегося пользователя и позволяют пользователям копировать данные в конечные точки PowerShell и из них, даже если поставщик файловой системы не предоставляется. Корни диска пользователя создаются в `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell\DriveRoots\` . Для каждого пользователя, подключающегося к конечной точке, создается папка с именем `$env:USERDOMAIN_$env:USERNAME`.

Содержимое диска пользователя сохраняется во всех пользовательских сеансах и не удаляется автоматически. По умолчанию пользователи могут хранить до 50 МБ данных на диске пользователя. Это можно настроить с помощью параметра **усердривемаксимумсизе** .

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

### -Path

Указывает путь и имя файла конфигурации сеанса. Файл должен иметь `.pssc` расширение имени файла.

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

### -PowerShellVersion

Указывает версию обработчика PowerShell в сеансах, использующих конфигурацию сеанса. Допустимые значения для этого параметра: 2,0 и 3,0. Если опустить этот параметр, ключ **PowerShellVersion** будет снабжен комментариями и в сеансе будут выполняться новейшие версии PowerShell.

Значение параметра **PSVersion** `Register-PSSessionConfiguration` командлета имеет приоритет над значением ключа **PowerShellVersion** в файле конфигурации сеанса.

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

### -RequiredGroups

Указывает правила условного доступа для пользователей, подключающихся к сеансам, использующим эту конфигурацию сеанса.

Введите хэш-таблицу, чтобы составить список правил, используя только один ключ на Hashtable, "and" или "or", и присвоить значение массиву имен групп безопасности или дополнительных хэш-таблиц.

Пример, при котором пользователи должны быть членами одной группы: `@{ And = 'MyRequiredGroup' }`

Пример, в котором пользователи должны принадлежать к группе A или обеим группам B и C для доступа к конечной точке: `@{ Or = 'GroupA', @{ And = 'GroupB', 'GroupC' } }`

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

### -RoleDefinitions

Указывает сопоставление между группами безопасности (или пользователями) и возможностями ролей. Пользователям будет предоставлен доступ ко всем возможностям ролей, которые применяются к их членству в группе во время создания сеанса.

Введите хэш-таблицу, в которой ключи являются именем группы безопасности, а значения — хэш-таблицами, которые содержат список возможностей роли, которые должны быть доступны группе безопасности.

Пример: `@{'Contoso\Level 2 Helpdesk Users' = @{ RoleCapabilities = 'Maintenance', 'ADHelpDesk' }}`

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

### -RunAsVirtualAccount

Настраивает сеансы, использующие эту конфигурацию сеанса, в качестве учетной записи администратора компьютера (виртуального). Это поле нельзя использовать с параметром **граупманажедсервицеаккаунт** .

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

### -Рунасвиртуалаккаунтграупс

Указывает группы безопасности, которые будут связаны с виртуальной учетной записью, если сеанс, использующий конфигурацию сеанса, выполняется как виртуальная учетная запись. Если этот параметр не указан, виртуальная учетная запись принадлежит администраторам домена на контроллерах домена и администраторах на всех остальных компьютерах.

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

### -SchemaVersion

Указывает версию схемы файла конфигурации сеанса. Значение по умолчанию: 1.0.0.0.

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

### -ScriptsToProcess

Добавляет указанные сценарии в сеансы, использующие конфигурацию сеанса. Введите путь и имена файлов сценариев. Значение этого параметра должно быть полным или абсолютным путем к именам файлов скриптов.

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

### -SessionType

Указывает тип сеанса, создаваемого при использовании конфигурации сеанса. Значение по умолчанию — Default. Допустимые значения для этого параметра:

- Пусто. модули по умолчанию не добавляются в сеанс. Параметры этого командлета позволяют добавить в сеанс модули, функции, скрипты и другие элементы. Этот параметр предназначен для создания пользовательских сеансов путем добавления выбранных команд. Если вы не добавите команды в пустой сеанс, сеанс ограничивается выражениями и может не работать.
- По умолчанию — добавляет модуль Microsoft. PowerShell. Core в сеанс. Этот модуль включает `Import-Module` командлет, который пользователи могут использовать для импорта других модулей, если этот командлет явно не запрещен.
- RestrictedRemoteServer. Включает в себя только следующие функции-посредники: `Exit-PSSession` ,,,,, и `Get-Command` `Get-FormatData` `Get-Help` `Measure-Object` `Out-Default` `Select-Object` .
  Параметры этого командлета позволяют добавить в сеанс модули, функции, скрипты и другие элементы.

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

### -TranscriptDirectory

Указывает каталог для размещения записей сеанса для сеансов, использующих эту конфигурацию сеанса.

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

### -TypesToProcess

Добавляет указанные `.ps1xml` файлы типов в сеансы, которые используют конфигурацию сеанса. Введите имена файлов. Значение этого параметра должно быть полным или абсолютным путем к типу filename.

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

### -Усердривемаксимумсизе

Указывает максимальный размер для дисков пользователей, доступных в сеансах, использующих эту конфигурацию сеанса.
Если этот параметр опущен, размер каждого корня диска по умолчанию `User:` — 50 МБ.

Этот параметр следует использовать с **маунтусердриве**.

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

### -VariableDefinitions

Добавляет указанные переменные в сеансы, использующие конфигурацию сеанса. Введите хэш-таблицу со следующими разделами:

- Name — имя переменной. Этот раздел обязателен.
- Значение — значение переменной. Этот раздел обязателен.
- Параметры — параметры переменных. Этот раздел необязателен. Значение по умолчанию — **None**. Допустимые значения для этого параметра: None, ReadOnly, Constant, private или AllScope.

Пример: `@{Name='WarningPreference';Value='SilentlyContinue';Options='AllScope'}`

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

### -VisibleAliases

Ограничивает псевдонимы в сеансе теми, которые указаны в значении этого параметра, а также всеми псевдонимами, определенными в параметре **AliasDefinition**. Поддерживаются подстановочные знаки. По умолчанию все псевдонимы, определенные подсистемой PowerShell и все псевдонимы, которые экспортируются модулями, видимы в сеансе.

Пример: `VisibleAliases='gcm', 'gp'`

Если любой **видимый** параметр включен в файл конфигурации сеанса, PowerShell удаляет `Import-Module` командлет и его псевдоним IPMO из сеанса.

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

### -VisibleCmdlets

Ограничивает командлеты в сеансе теми, которые указаны в значении этого параметра. Поддерживаются подстановочные знаки и полные имена модулей.

По умолчанию все командлеты, экспортируемые модулями в сеансе, отображаются в сеансе. Используйте параметры **SessionType** и **ModulesToImport** , чтобы определить, какие модули и оснастки импортируются в сеанс. Если ни один из модулей в **ModulesToImport** не предоставляет командлет, соответствующий модуль будет пытаться выполнить автозагрузку.

Если любой **видимый** параметр включен в файл конфигурации сеанса, PowerShell удаляет `Import-Module` командлет и его псевдоним IPMO из сеанса.

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

### -VisibleExternalCommands

Ограничивает внешние двоичные файлы, скрипты и команды, которые могут выполняться в сеансе, с теми, которые указаны в значении этого параметра. Поддерживаются подстановочные знаки.

По умолчанию в сеансе не отображаются никакие внешние команды.

Если любой **видимый** параметр включен в файл конфигурации сеанса, PowerShell удаляет `Import-Module` командлет и его псевдоним IPMO из сеанса.

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

### -VisibleFunctions

Ограничивает функции в сеансе теми, которые указаны в значении этого параметра, а также всеми функциями, определенными в параметре **FunctionDefinition**. Поддерживаются подстановочные знаки.

По умолчанию все функции, экспортируемые модулями в сеансе, отображаются в сеансе. Используйте параметры **SessionType** и **ModulesToImport** , чтобы определить, какие модули и оснастки импортируются в сеанс.

Если любой **видимый** параметр включен в файл конфигурации сеанса, PowerShell удаляет `Import-Module` командлет и его псевдоним IPMO из сеанса.

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

### -VisibleProviders

Ограничивает поставщиков PowerShell в сеансе теми, которые указаны в значении этого параметра.
Поддерживаются подстановочные знаки.

По умолчанию все поставщики, экспортируемые модулями в сеансе, отображаются в сеансе. Используйте параметры **SessionType** и **ModulesToImport** , чтобы определить, какие модули импортируются в сеанс.

Если любой **видимый** параметр включен в файл конфигурации сеанса, PowerShell удаляет `Import-Module` командлет и его `ipmo` псевдоним из сеанса.

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

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### Нет

В этот командлет нельзя передать по конвейеру ни один объект.

## Выходные данные

### Нет

Этот командлет не формирует никаких выходных данных.

## ПРИМЕЧАНИЯ

Этот командлет доступен только на платформах Windows.

- Параметры, такие как **VisibleCmdlets** и **VisibleProviders** , не импортируют элементы в сеанс. Вместо этого они отбирают элементы, импортированные в сеанс. Например, если значение параметра **VisibleProviders** является поставщиком сертификата, но в параметре **ModulesToImport** не указан модуль **Microsoft. PowerShell. Security** , который содержит поставщик сертификата, то поставщик сертификата не отображается в сеансе.
- `New-PSSessionConfigurationFile` создает файл конфигурации сеанса с расширением имени файла pssc в пути, указанном в параметре **path** . При использовании файла конфигурации сеанса для создания конфигурации сеанса `Register-PSSessionConfiguration` командлет копирует файл конфигурации и сохраняет активную копию файла в подкаталоге **сессионконфиг** `$PSHOME` каталога.

  Свойство **конфигфилепас** конфигурации сеанса содержит полный путь к файлу конфигурации активного сеанса. Активный файл конфигурации в каталоге можно изменить в `$PSHOME` любое время с помощью любого текстового редактора. Внесенные изменения влияют на все новые сеансы, которые используют конфигурацию сеанса, но не на текущие сеансы.

  Прежде чем использовать измененный файл конфигурации сеанса, используйте `Test-PSSessionConfigurationFile` командлет, чтобы проверить допустимость записей в файле конфигурации.

## Связанные ссылки

[Disable-PSSessionConfiguration](Disable-PSSessionConfiguration.md)

[Enable-PSSessionConfiguration](Enable-PSSessionConfiguration.md)

[Get-PSSessionConfiguration](Get-PSSessionConfiguration.md)

[Register-PSSessionConfiguration](Register-PSSessionConfiguration.md)

[Set-PSSessionConfiguration](Set-PSSessionConfiguration.md)

[Test-PSSessionConfigurationFile](Test-PSSessionConfigurationFile.md)

[Unregister-PSSessionConfiguration](Unregister-PSSessionConfiguration.md)

[Поставщик WSMan](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[about_Session_Configurations](About/about_Session_Configurations.md)

[about_Session_Configuration_Files](About/about_Session_Configuration_Files.md)
