---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/test-scriptfileinfo?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-ScriptFileInfo
ms.openlocfilehash: 35de1c9b7c975a68ac2f5a01c97a78eeef6d1184
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605267"
---
# <span data-ttu-id="3de89-102">Test-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="3de89-102">Test-ScriptFileInfo</span></span>

## <span data-ttu-id="3de89-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="3de89-103">SYNOPSIS</span></span>
<span data-ttu-id="3de89-104">Проверяет блок комментариев для скрипта.</span><span class="sxs-lookup"><span data-stu-id="3de89-104">Validates a comment block for a script.</span></span>

## <span data-ttu-id="3de89-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3de89-105">SYNTAX</span></span>

### <span data-ttu-id="3de89-106">Паспараметерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="3de89-106">PathParameterSet (Default)</span></span>

```
Test-ScriptFileInfo [-Path] <String> [<CommonParameters>]
```

### <span data-ttu-id="3de89-107">литералпаспараметерсет</span><span class="sxs-lookup"><span data-stu-id="3de89-107">LiteralPathParameterSet</span></span>

```
Test-ScriptFileInfo -LiteralPath <String> [<CommonParameters>]
```

## <span data-ttu-id="3de89-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3de89-108">DESCRIPTION</span></span>

<span data-ttu-id="3de89-109">Командлет **Test-ScriptFileInfo** проверяет блок комментариев в начале скрипта, который будет опубликован с помощью командлета Publish-Script.</span><span class="sxs-lookup"><span data-stu-id="3de89-109">The **Test-ScriptFileInfo** cmdlet validates the comment block at the beginning of a script that will be published with the Publish-Script cmdlet.</span></span>
<span data-ttu-id="3de89-110">Если блок комментариев содержит ошибку, этот командлет возвращает сведения о том, где находится ошибка, или о том, как ее исправить.</span><span class="sxs-lookup"><span data-stu-id="3de89-110">If the comment block has an error, this cmdlet returns information about where the error is located or how to correct it.</span></span>

## <span data-ttu-id="3de89-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="3de89-111">EXAMPLES</span></span>

### <span data-ttu-id="3de89-112">Пример 1. Тестирование файла скрипта</span><span class="sxs-lookup"><span data-stu-id="3de89-112">Example 1: Test a script file</span></span>

```
PS C:\> Test-ScriptFileInfo -Path "C:\temp\temp_scripts\New-ScriptFile.ps1"
Version    Name                      Author               Description
-------    ----                      ------               -----------
1.0        New-ScriptFile            pattif               my new script file test
```

<span data-ttu-id="3de89-113">Эта команда проверяет файл скрипта New-ScriptFile.ps1 и отображает результаты.</span><span class="sxs-lookup"><span data-stu-id="3de89-113">This command tests the New-ScriptFile.ps1 script file and displays the results.</span></span>
<span data-ttu-id="3de89-114">Файл скрипта содержит допустимые метаданные.</span><span class="sxs-lookup"><span data-stu-id="3de89-114">The script file includes valid metadata.</span></span>

### <span data-ttu-id="3de89-115">Пример 2. Тестирование файла скрипта, имеющего значения для всех свойств метаданных</span><span class="sxs-lookup"><span data-stu-id="3de89-115">Example 2: Test a script file that has values for all metadata properties</span></span>

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

<span data-ttu-id="3de89-116">Эта команда проверяет файл скрипта Test-Runbook.ps1 и использует оператор конвейера для передачи результатов в командлет Format-List для форматирования результатов.</span><span class="sxs-lookup"><span data-stu-id="3de89-116">This command tests the script file Test-Runbook.ps1 and uses the pipeline operator to pass the results to the Format-List cmdlet to format the results.</span></span>

### <span data-ttu-id="3de89-117">Пример 3. Тестирование файла скрипта, не имеющего метаданных</span><span class="sxs-lookup"><span data-stu-id="3de89-117">Example 3: Test a script file that has no metadata</span></span>

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

<span data-ttu-id="3de89-118">Эта команда проверяет файл скрипта Hello-World.ps1, с которым не связаны метаданные.</span><span class="sxs-lookup"><span data-stu-id="3de89-118">This command tests the script file Hello-World.ps1, which has no metadata associated with it.</span></span>

## <span data-ttu-id="3de89-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3de89-119">PARAMETERS</span></span>

### <span data-ttu-id="3de89-120">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="3de89-120">-LiteralPath</span></span>

<span data-ttu-id="3de89-121">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="3de89-121">Specifies a path to one or more locations.</span></span>
<span data-ttu-id="3de89-122">В отличие от параметра *path* , значение параметра *LiteralPath* используется точно так же, как оно указано.</span><span class="sxs-lookup"><span data-stu-id="3de89-122">Unlike the *Path* parameter, the value of the *LiteralPath* parameter is used exactly as it is entered.</span></span>
<span data-ttu-id="3de89-123">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="3de89-123">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="3de89-124">Если путь содержит escape-символы, заключите их в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="3de89-124">If the path includes escape characters, enclose them in single quotation marks.</span></span>
<span data-ttu-id="3de89-125">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="3de89-125">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="3de89-126">-Path</span><span class="sxs-lookup"><span data-stu-id="3de89-126">-Path</span></span>

<span data-ttu-id="3de89-127">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="3de89-127">Specifies a path to one or more locations.</span></span>
<span data-ttu-id="3de89-128">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="3de89-128">Wildcards are permitted.</span></span>
<span data-ttu-id="3de89-129">Расположение по умолчанию — текущий каталог (.).</span><span class="sxs-lookup"><span data-stu-id="3de89-129">The default location is the current directory (.).</span></span>

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

### <span data-ttu-id="3de89-130">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="3de89-130">CommonParameters</span></span>

<span data-ttu-id="3de89-131">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3de89-131">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3de89-132">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3de89-132">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3de89-133">Входные данные</span><span class="sxs-lookup"><span data-stu-id="3de89-133">INPUTS</span></span>

### <span data-ttu-id="3de89-134">System.String</span><span class="sxs-lookup"><span data-stu-id="3de89-134">System.String</span></span>

## <span data-ttu-id="3de89-135">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="3de89-135">OUTPUTS</span></span>

### <span data-ttu-id="3de89-136">System.Object</span><span class="sxs-lookup"><span data-stu-id="3de89-136">System.Object</span></span>

## <span data-ttu-id="3de89-137">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="3de89-137">NOTES</span></span>

## <span data-ttu-id="3de89-138">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="3de89-138">RELATED LINKS</span></span>

[<span data-ttu-id="3de89-139">New-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="3de89-139">New-ScriptFileInfo</span></span>](New-ScriptFileInfo.md)

[<span data-ttu-id="3de89-140">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="3de89-140">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="3de89-141">Update-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="3de89-141">Update-ScriptFileInfo</span></span>](Update-ScriptFileInfo.md)

