---
external help file: PSModule-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/test-scriptfileinfo?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-ScriptFileInfo
ms.openlocfilehash: c773b247d5f0da4071517134b7187ba674bfbfbd
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228945"
---
# <span data-ttu-id="7f6a3-103">Test-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="7f6a3-103">Test-ScriptFileInfo</span></span>

## <span data-ttu-id="7f6a3-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="7f6a3-104">SYNOPSIS</span></span>
<span data-ttu-id="7f6a3-105">Проверяет блок комментариев для скрипта.</span><span class="sxs-lookup"><span data-stu-id="7f6a3-105">Validates a comment block for a script.</span></span>

## <span data-ttu-id="7f6a3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7f6a3-106">SYNTAX</span></span>

### <span data-ttu-id="7f6a3-107">Паспараметерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="7f6a3-107">PathParameterSet (Default)</span></span>

```
Test-ScriptFileInfo [-Path] <String> [<CommonParameters>]
```

### <span data-ttu-id="7f6a3-108">литералпаспараметерсет</span><span class="sxs-lookup"><span data-stu-id="7f6a3-108">LiteralPathParameterSet</span></span>

```
Test-ScriptFileInfo -LiteralPath <String> [<CommonParameters>]
```

## <span data-ttu-id="7f6a3-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7f6a3-109">DESCRIPTION</span></span>

<span data-ttu-id="7f6a3-110">Командлет **Test-ScriptFileInfo** проверяет блок комментариев в начале скрипта, который будет опубликован с помощью командлета Publish-Script.</span><span class="sxs-lookup"><span data-stu-id="7f6a3-110">The **Test-ScriptFileInfo** cmdlet validates the comment block at the beginning of a script that will be published with the Publish-Script cmdlet.</span></span>
<span data-ttu-id="7f6a3-111">Если блок комментариев содержит ошибку, этот командлет возвращает сведения о том, где находится ошибка, или о том, как ее исправить.</span><span class="sxs-lookup"><span data-stu-id="7f6a3-111">If the comment block has an error, this cmdlet returns information about where the error is located or how to correct it.</span></span>

## <span data-ttu-id="7f6a3-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="7f6a3-112">EXAMPLES</span></span>

### <span data-ttu-id="7f6a3-113">Пример 1. Тестирование файла скрипта</span><span class="sxs-lookup"><span data-stu-id="7f6a3-113">Example 1: Test a script file</span></span>

```
PS C:\> Test-ScriptFileInfo -Path "C:\temp\temp_scripts\New-ScriptFile.ps1"
Version    Name                      Author               Description
-------    ----                      ------               -----------
1.0        New-ScriptFile            pattif               my new script file test
```

<span data-ttu-id="7f6a3-114">Эта команда проверяет файл скрипта New-ScriptFile.ps1 и отображает результаты.</span><span class="sxs-lookup"><span data-stu-id="7f6a3-114">This command tests the New-ScriptFile.ps1 script file and displays the results.</span></span>
<span data-ttu-id="7f6a3-115">Файл скрипта содержит допустимые метаданные.</span><span class="sxs-lookup"><span data-stu-id="7f6a3-115">The script file includes valid metadata.</span></span>

### <span data-ttu-id="7f6a3-116">Пример 2. Тестирование файла скрипта, имеющего значения для всех свойств метаданных</span><span class="sxs-lookup"><span data-stu-id="7f6a3-116">Example 2: Test a script file that has values for all metadata properties</span></span>

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

<span data-ttu-id="7f6a3-117">Эта команда проверяет файл скрипта Test-Runbook.ps1 и использует оператор конвейера для передачи результатов в командлет Format-List для форматирования результатов.</span><span class="sxs-lookup"><span data-stu-id="7f6a3-117">This command tests the script file Test-Runbook.ps1 and uses the pipeline operator to pass the results to the Format-List cmdlet to format the results.</span></span>

### <span data-ttu-id="7f6a3-118">Пример 3. Тестирование файла скрипта, не имеющего метаданных</span><span class="sxs-lookup"><span data-stu-id="7f6a3-118">Example 3: Test a script file that has no metadata</span></span>

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

<span data-ttu-id="7f6a3-119">Эта команда проверяет файл скрипта Hello-World.ps1, с которым не связаны метаданные.</span><span class="sxs-lookup"><span data-stu-id="7f6a3-119">This command tests the script file Hello-World.ps1, which has no metadata associated with it.</span></span>

## <span data-ttu-id="7f6a3-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7f6a3-120">PARAMETERS</span></span>

### <span data-ttu-id="7f6a3-121">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="7f6a3-121">-LiteralPath</span></span>

<span data-ttu-id="7f6a3-122">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="7f6a3-122">Specifies a path to one or more locations.</span></span>
<span data-ttu-id="7f6a3-123">В отличие от параметра *path* , значение параметра *LiteralPath* используется точно так же, как оно указано.</span><span class="sxs-lookup"><span data-stu-id="7f6a3-123">Unlike the *Path* parameter, the value of the *LiteralPath* parameter is used exactly as it is entered.</span></span>
<span data-ttu-id="7f6a3-124">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="7f6a3-124">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="7f6a3-125">Если путь содержит escape-символы, заключите их в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="7f6a3-125">If the path includes escape characters, enclose them in single quotation marks.</span></span>
<span data-ttu-id="7f6a3-126">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="7f6a3-126">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="7f6a3-127">-Path</span><span class="sxs-lookup"><span data-stu-id="7f6a3-127">-Path</span></span>

<span data-ttu-id="7f6a3-128">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="7f6a3-128">Specifies a path to one or more locations.</span></span>
<span data-ttu-id="7f6a3-129">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="7f6a3-129">Wildcards are permitted.</span></span>
<span data-ttu-id="7f6a3-130">Расположение по умолчанию — текущий каталог (.).</span><span class="sxs-lookup"><span data-stu-id="7f6a3-130">The default location is the current directory (.).</span></span>

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

### <span data-ttu-id="7f6a3-131">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="7f6a3-131">CommonParameters</span></span>

<span data-ttu-id="7f6a3-132">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7f6a3-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7f6a3-133">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="7f6a3-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7f6a3-134">Входные данные</span><span class="sxs-lookup"><span data-stu-id="7f6a3-134">INPUTS</span></span>

### <span data-ttu-id="7f6a3-135">System.String</span><span class="sxs-lookup"><span data-stu-id="7f6a3-135">System.String</span></span>

## <span data-ttu-id="7f6a3-136">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="7f6a3-136">OUTPUTS</span></span>

### <span data-ttu-id="7f6a3-137">System.Object</span><span class="sxs-lookup"><span data-stu-id="7f6a3-137">System.Object</span></span>

## <span data-ttu-id="7f6a3-138">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="7f6a3-138">NOTES</span></span>

## <span data-ttu-id="7f6a3-139">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="7f6a3-139">RELATED LINKS</span></span>

[<span data-ttu-id="7f6a3-140">New-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="7f6a3-140">New-ScriptFileInfo</span></span>](New-ScriptFileInfo.md)

[<span data-ttu-id="7f6a3-141">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="7f6a3-141">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="7f6a3-142">Update-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="7f6a3-142">Update-ScriptFileInfo</span></span>](Update-ScriptFileInfo.md)
