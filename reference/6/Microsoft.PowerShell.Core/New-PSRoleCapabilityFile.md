---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 09/11/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-psrolecapabilityfile?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSRoleCapabilityFile
ms.openlocfilehash: 617deb71605462833c3ed816fb4391c88ccd2da8
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228873"
---
# New-PSRoleCapabilityFile

## Краткий обзор
Создает файл, который определяет набор возможностей, предоставляемых через конфигурацию сеанса.

## SYNTAX

```
New-PSRoleCapabilityFile [-Path] <String> [-Guid <Guid>] [-Author <String>] [-Description <String>]
 [-CompanyName <String>] [-Copyright <String>] [-ModulesToImport <Object[]>] [-VisibleAliases <String[]>]
 [-VisibleCmdlets <Object[]>] [-VisibleFunctions <Object[]>] [-VisibleExternalCommands <String[]>]
 [-VisibleProviders <String[]>] [-ScriptsToProcess <String[]>] [-AliasDefinitions <IDictionary[]>]
 [-FunctionDefinitions <IDictionary[]>] [-VariableDefinitions <Object>] [-EnvironmentVariables <IDictionary>]
 [-TypesToProcess <String[]>] [-FormatsToProcess <String[]>] [-AssembliesToLoad <String[]>]
 [<CommonParameters>]
```

## DESCRIPTION

`New-PSRoleCapabilityFile`Командлет создает файл, который определяет набор возможностей пользователя, которые могут быть предоставлены через файлы конфигурации сеанса. Это включает определение того, какие командлеты, функции и скрипты доступны пользователям. Файл возможностей — это текстовый файл, доступный для чтения и содержащий хэш-таблицу свойств и значений конфигурации сеанса. Файл имеет расширение pSrc и может использоваться более чем в одной конфигурации сеанса.

Все параметры `New-PSRoleCapabilityFile` являются необязательными, за исключением параметра **path** , который указывает путь к файлу для файла. Если параметр не включен при выполнении командлета, соответствующий ключ в файле конфигурации сеанса заносится в комментарий, за исключением тех случаев, где указано в описании параметра. Например, если не включить параметр **ассемблиестолоад** , то этот раздел файла конфигурации сеанса будет добавлен в комментарий.

Чтобы использовать файл возможностей роли в конфигурации сеанса, сначала поместите файл во вложенную папку **RoleCapabilities** допустимой папки модуля PowerShell. Затем сослаться на файл по имени в поле **RoleDefinitions** в файле конфигурации сеанса PowerShell (. pssc).

Этот командлет появился в Windows PowerShell 5,0.

## Примеры

### Пример 1. Создание пустого файла возможностей роли

В этом примере создается новый файл возможностей роли, который использует значения по умолчанию (пустые). Затем файл можно изменить в текстовом редакторе для изменения этих параметров конфигурации.

```powershell
New-PSRoleCapabilityFile -Path ".\ExampleFile.psrc"
```

### Пример 2. Создание файла возможностей роли, позволяющего пользователям перезапускать службы и любой компьютер VDI

В этом примере создается пример файла возможностей роли, который позволяет пользователям перезапускать службы и компьютеры, соответствующие определенному шаблону имени. Фильтрация имен определяется путем присвоения параметру **ValidatePattern** регулярного выражения `VDI\d+` .

```powershell
$roleParameters = @{
    Path = ".\Maintenance.psrc"
    Author = "User01"
    CompanyName = "Fabrikam Corporation"
    Description = "This role enables users to restart any service and restart any VDI computer."
    ModulesToImport = "Microsoft.PowerShell.Core"
    VisibleCmdlets = "Restart-Service", @{
                      Name = "Restart-Computer"
                      Parameters = @{ Name = "ComputerName"; ValidatePattern = "VDI\d+" }
    }
}
New-PSRoleCapabilityFile @roleParameters
```

## PARAMETERS

### -AliasDefinitions

Добавляет указанные псевдонимы в сеансы, которые используют файл возможностей роли. Введите хэш-таблицу со следующими разделами:

- Название Имя псевдонима. Этот раздел обязателен.
- Значение. Команда, которая представляет псевдоним. Этот раздел обязателен.
- Описание. Текстовая строка с описанием псевдонима. Этот раздел необязателен.
- Параметры. Параметры псевдонима. Этот раздел необязателен. По умолчанию используется None. Допустимые значения для этого параметра: None, ReadOnly, Constant, private или AllScope.

Пример: `@{Name="hlp";Value="Get-Help";Description="Gets help";Options="ReadOnly"}`

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

Указывает сборки, которые необходимо загрузить в сеансы, использующие файл возможностей роли.

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

Указывает пользователя, создавшего файл возможностей роли.

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

Идентифицирует компанию, которая создала файл возможностей роли.
Значение по умолчанию — Unknown.

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

### -Copyright

Указывает авторские права на файл возможностей роли. Если опустить этот параметр, `New-PSRoleCapabilityFile` создает заявление об авторских правах с помощью значения параметра **Author** .

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

Задает описание для файла возможностей роли.

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

Указывает переменные среды для сеансов, которые предоставляют этот файл возможностей роли. Введите хэш-таблицу, в которой разделами являются имена переменных среды, а значениями — значения переменных среды.

Пример: `EnvironmentVariables=@{TestShare="\\\\Server01\TestShare"}`

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

### -FormatsToProcess

Указывает файлы форматирования (. ps1xml), которые выполняются в сеансах, использующих файл возможностей ролей. Значение этого параметра должно быть полным или абсолютным путем к файлам форматирования.

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

### -FunctionDefinitions

Добавляет указанные функции к сеансам, которые предоставляют возможность роли. Введите хэш-таблицу со следующими разделами:

- Название Имя функции. Этот раздел обязателен.
- ScriptBlock. Тело функции. Введите блок сценария. Этот раздел обязателен.
- Параметры. Параметры функции. Этот раздел необязателен. По умолчанию используется None. Допустимые значения для этого параметра: "None", "ReadOnly", "Constant", "Private" или "AllScope".

Пример:

`@{Name="Get-PowerShellProcess";ScriptBlock={Get-Process PowerShell};Options="AllScope"}`

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

### -Guid

Указывает уникальный идентификатор для файла возможностей роли. Если опустить этот параметр, `New-PSRoleCapabilityFile` создает идентификатор GUID для файла. Чтобы создать новый GUID в PowerShell, введите `[guid]::NewGuid()` .

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

### -ModulesToImport

Указывает модули, которые автоматически импортируются в сеансы, использующие файл возможностей роли. По умолчанию все команды в списке модулей видимы. При использовании с **VisibleCmdlets** или **VisibleFunctions** команды, видимые из указанных модулей, могут быть ограничены.

Каждый модуль, используемый в значении этого параметра, может быть представлен строкой или хэш-таблицей. Строка модуля состоит только из имени модуля. Хэш-таблица модуля может включать разделы **ModuleName** , **ModuleVersion** и **GUID** . Обязателен только раздел **ModuleName** .

Например, следующее значение состоит из строки и хэш-таблицы. Допустимо любое сочетание строк и хэш-таблиц в любом порядке.

`"TroubleshootingPack", @{ModuleName="PSDiagnostics"; ModuleVersion="1.0.0.0";GUID="c61d6278-02a3-4618-ae37-a524d40a7f44"}`

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

### -Path

Указывает путь и имя файла возможностей роли. Файл должен иметь `.psrc` расширение имени файла.

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

### -ScriptsToProcess

Указывает скрипты, добавляемые в сеансы, в которых используется файл возможностей ролей. Введите путь и имена файлов сценариев. Значение этого параметра должно быть полным или абсолютным путем к именам файлов скриптов.

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

### -TypesToProcess

Указывает файлы типов (. ps1xml) для добавления в сеансы, в которых используется файл возможностей ролей. Введите имена файлов. Значение этого параметра должно быть полным или абсолютным путем к типу filename.

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

### -VariableDefinitions

Указывает переменные для добавления в сеансы, в которых используется файл возможностей роли. Введите хэш-таблицу со следующими разделами:

- Название Имя переменной. Этот раздел обязателен.
- Значение. Значение переменной. Этот раздел обязателен.
- Параметры. Параметры переменных. Этот раздел необязателен. По умолчанию используется None. Допустимые значения для этого параметра: "None", "ReadOnly", "Constant", "Private" или "AllScope".

Пример: `@{Name="WarningPreference";Value="SilentlyContinue";Options="AllScope"}`

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

Ограничивает псевдонимы в сеансе псевдонимами, указанными в значении этого параметра, а также любыми псевдонимами, определенными в параметре **алиасдефинитион** . Поддерживаются подстановочные знаки.
По умолчанию все псевдонимы, определенные подсистемой PowerShell и все псевдонимы, которые экспортируются модулями, видимы в сеансе.

Например, чтобы ограничить доступные псевдонимы GM и GCM, используйте следующий синтаксис: `VisibleAliases="gcm", "gp"`

Если любой **видимый** параметр включен в файл возможностей роли, PowerShell удаляет `Import-Module` командлет и его `ipmo` псевдоним из сеанса.

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

По умолчанию все командлеты, экспортируемые модулями в сеансе, видимы в сеансе. Используйте параметры **SessionType** и **ModulesToImport** , чтобы определить, какие модули и оснастки импортируются в сеанс. Если ни один из модулей в **ModulesToImport** не предоставляет командлет, `New-PSRoleCapabilityFile` пытается загрузить соответствующий модуль.

Если любой **видимый** параметр включен в файл конфигурации сеанса, PowerShell удаляет `Import-Module` командлет и его `ipmo` псевдоним из сеанса.

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

### -VisibleExternalCommands

Ограничивает внешние двоичные файлы, скрипты и команды, которые могут выполняться в сеансе, с теми, которые указаны в значении этого параметра.

По умолчанию в этом сеансе нет видимых внешних команд.

Если любой **видимый** параметр включен в файл конфигурации сеанса, PowerShell удаляет `Import-Module` командлет и его `ipmo` псевдоним из сеанса.

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

### -VisibleFunctions

Ограничивает функции в сеансе значениями, указанными в значении этого параметра, а также всеми функциями, определенными в параметре **функтиондефинитионс** . Поддерживаются подстановочные знаки.

По умолчанию все функции, экспортируемые модулями в сеансе, видимы в этом сеансе. Используйте параметры **SessionType** и **ModulesToImport** , чтобы определить, какие модули импортируются в сеанс.

Если любой **видимый** параметр включен в файл конфигурации сеанса, PowerShell удаляет `Import-Module` командлет и его `ipmo` псевдоним из сеанса.

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

По умолчанию все поставщики, экспортированные модулем в сеансе, видимы в сеансе. Используйте параметры **SessionType** и **ModulesToImport** , чтобы определить, какие модули импортируются в сеанс.

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

## Выходные данные

## ПРИМЕЧАНИЯ

## Связанные ссылки

[New-PSSessionConfigurationFile](New-PSSessionConfigurationFile.md)

[Get-PSSessionCapability](Get-PSSessionCapability.md)
