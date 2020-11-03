---
external help file: PSModule-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/test-scriptfileinfo?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-ScriptFileInfo
ms.openlocfilehash: 24e2ac0c7bd9652c406e05259c57181b373b75f8
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93225634"
---
# Test-ScriptFileInfo

## Краткий обзор
Проверяет блок комментариев для скрипта.

## SYNTAX

### Паспараметерсет (по умолчанию)

```
Test-ScriptFileInfo [-Path] <String> [<CommonParameters>]
```

### литералпаспараметерсет

```
Test-ScriptFileInfo -LiteralPath <String> [<CommonParameters>]
```

## DESCRIPTION

Командлет **Test-ScriptFileInfo** проверяет блок комментариев в начале скрипта, который будет опубликован с помощью командлета Publish-Script.
Если блок комментариев содержит ошибку, этот командлет возвращает сведения о том, где находится ошибка, или о том, как ее исправить.

## Примеры

### Пример 1. Тестирование файла скрипта

```
PS C:\> Test-ScriptFileInfo -Path "C:\temp\temp_scripts\New-ScriptFile.ps1"
Version    Name                      Author               Description
-------    ----                      ------               -----------
1.0        New-ScriptFile            pattif               my new script file test
```

Эта команда проверяет файл скрипта New-ScriptFile.ps1 и отображает результаты.
Файл скрипта содержит допустимые метаданные.

### Пример 2. Тестирование файла скрипта, имеющего значения для всех свойств метаданных

```
PS C:\> Test-ScriptFileInfo -Path "D:\code\Test-Runbook.ps1" | Format-List *
Name                       : Test-Runbook
Path                       : D:\code\Test-Runbook.ps1
ScriptBase                 : D:\code
ReleaseNotes               : {contoso script now supports following features, Feature 1, Feature 2, Feature 3...}
Version                    : 1.0
Guid                       : eb246b19-17da-4392-8c89-7c280f69ad0e
Author                     : pattif
CompanyName                : Microsoft Corporation
Copyright                  : 2015 Microsoft Corporation. All rights reserved.
Tags                       : {Tag1, Tag2, Tag3}
LicenseUri                 : https://contoso.com/License
ProjectUri                 : https://contoso.com/
IconUri                    : https://contoso.com/MyScriptIcon
ExternalModuleDependencies : ExternalModule1
RequiredScripts            : {Start-WFContosoServer, Stop-ContosoServerScript}
ExternalScriptDependencies : Stop-ContosoServerScript
Description                : Contoso Script example
RequiredModules            : {RequiredModule1, @{ ModuleName = 'RequiredModule2'; ModuleVersion = '1.0' }, @{ ModuleName = 'RequiredModule3'; RequiredVersion = '2.0' }, ExternalModule1}
ExportedCommands           : {Test-WebUri, ValidateAndAdd-PSScriptInfoEntry, Get-PSScriptInfo, My-Workflow...}
ExportedFunctions          : {Test-WebUri, ValidateAndAdd-PSScriptInfoEntry, Get-PSScriptInfo, My-AdvPSCmdlet}
ExportedWorkflows          : My-Workflow
```

Эта команда проверяет файл скрипта Test-Runbook.ps1 и использует оператор конвейера для передачи результатов в командлет Format-List для форматирования результатов.

### Пример 3. Тестирование файла скрипта, не имеющего метаданных

```
PS C:\> Test-ScriptFileInfo -Path "D:\code\Hello-World.ps1"
Test-ScriptFileInfo : Script 'D:\code\Hello-World.ps1' is missing required metadata properties. Verify that the script file has Version, Description
and Author properties. You can use the Update-ScriptFileInfo or New-ScriptFileInfo cmdlet to add or update the PSScriptInfo to the script file.
At line:1 char:1
+ Test-ScriptFileInfo D:\code\Hello-World.ps1
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : InvalidArgument: (D:\code\Hello-World.ps1:String) [Test-ScriptFileInfo], ArgumentException

+ FullyQualifiedErrorId : MissingRequiredPSScriptInfoProperties,Test-ScriptFile
```

Эта команда проверяет файл скрипта Hello-World.ps1, с которым не связаны метаданные.

## PARAMETERS

### -LiteralPath

Указывает путь к одному или нескольким расположениям.
В отличие от параметра *path* , значение параметра *LiteralPath* используется точно так же, как оно указано.
Никакие символы не интерпретируются как знаки подстановки.
Если путь содержит escape-символы, заключите их в одинарные кавычки.
Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.

```yaml
Type: System.String
Parameter Sets: LiteralPathParameterSet
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path

Указывает путь к одному или нескольким расположениям.
Разрешено использовать подстановочные знаки.
Расположение по умолчанию — текущий каталог (.).

```yaml
Type: System.String
Parameter Sets: PathParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### Общие параметры

Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable. См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## Входные данные

### System.String

## Выходные данные

### System.Object

## ПРИМЕЧАНИЯ

## Связанные ссылки

[New-ScriptFileInfo](New-ScriptFileInfo.md)

[Publish-Script](Publish-Script.md)

[Update-ScriptFileInfo](Update-ScriptFileInfo.md)
