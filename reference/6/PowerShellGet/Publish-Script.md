---
external help file: PSModule-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PowerShellGet
ms.date: 03/27/2020
online version: https://docs.microsoft.com/powershell/module/powershellget/publish-script?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Publish-Script
ms.openlocfilehash: 95dadef6a1cbc4e730fed21fd8bda629f4c04563
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228630"
---
# <span data-ttu-id="d0f72-103">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="d0f72-103">Publish-Script</span></span>

## <span data-ttu-id="d0f72-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="d0f72-104">SYNOPSIS</span></span>
<span data-ttu-id="d0f72-105">Публикует скрипт.</span><span class="sxs-lookup"><span data-stu-id="d0f72-105">Publishes a script.</span></span>

## <span data-ttu-id="d0f72-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d0f72-106">SYNTAX</span></span>

### <span data-ttu-id="d0f72-107">Паспараметерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="d0f72-107">PathParameterSet (Default)</span></span>

```
Publish-Script -Path <String> [-NuGetApiKey <String>] [-Repository <String>]
 [-Credential <PSCredential>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="d0f72-108">литералпаспараметерсет</span><span class="sxs-lookup"><span data-stu-id="d0f72-108">LiteralPathParameterSet</span></span>

```
Publish-Script -LiteralPath <String> [-NuGetApiKey <String>] [-Repository <String>]
 [-Credential <PSCredential>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="d0f72-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d0f72-109">DESCRIPTION</span></span>

<span data-ttu-id="d0f72-110">`Publish-Script`Командлет публикует указанный скрипт в веб-коллекции.</span><span class="sxs-lookup"><span data-stu-id="d0f72-110">The `Publish-Script` cmdlet publishes the specified script to the online gallery.</span></span>

## <span data-ttu-id="d0f72-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="d0f72-111">EXAMPLES</span></span>

### <span data-ttu-id="d0f72-112">Пример 1. Создание файла скрипта, добавление в него содержимого и его публикация</span><span class="sxs-lookup"><span data-stu-id="d0f72-112">Example 1: Create a script file, add content to it, and publish it</span></span>

<span data-ttu-id="d0f72-113">`New-ScriptFileInfo`Командлет создает файл скрипта с именем `Demo-Script.ps1` .</span><span class="sxs-lookup"><span data-stu-id="d0f72-113">The `New-ScriptFileInfo` cmdlet creates a script file named `Demo-Script.ps1`.</span></span> <span data-ttu-id="d0f72-114">`Get-Content` Отображает содержимое `Demo-Script.ps1` .</span><span class="sxs-lookup"><span data-stu-id="d0f72-114">`Get-Content` displays the content of `Demo-Script.ps1`.</span></span> <span data-ttu-id="d0f72-115">`Add-Content`Командлет добавляет функцию и рабочий процесс в `Demo-Script.ps1` .</span><span class="sxs-lookup"><span data-stu-id="d0f72-115">The `Add-Content` cmdlet adds a function and a workflow to `Demo-Script.ps1`.</span></span>

```powershell
$newScriptInfo = @{
  Path = 'D:\ScriptSharingDemo\Demo-Script.ps1'
  Version = '1.0'
  Author = 'author@contoso.com'
  Description = "my test script file description goes here"
}
New-ScriptFileInfo @newScriptInfo
Get-Content -Path $newScriptInfo.Path
```

```Output
<#PSScriptInfo

.VERSION 1.0

.AUTHOR pattif@microsoft.com

.COMPANYNAME

.COPYRIGHT

.TAGS

.LICENSEURI

.PROJECTURI

.ICONURI

.EXTERNALMODULEDEPENDENCIES

.REQUIREDSCRIPTS

.EXTERNALSCRIPTDEPENDENCIES

.RELEASENOTES
#>

<#
.DESCRIPTION
 my test script file description goes here
#>
Param()
```

```powershell
Add-Content -Path D:\ScriptSharingDemo\Demo-Script.ps1 -Value @"

Function Demo-ScriptFunction { 'Demo-ScriptFunction' }

Workflow Demo-ScriptWorkflow { 'Demo-ScriptWorkflow' }

Demo-ScriptFunction
Demo-ScriptWorkflow
"@
Test-ScriptFileInfo -Path D:\ScriptSharingDemo\Demo-Script.ps1
```

```Output
Version    Name                 Author                   Description
-------    ----                 ------                   -----------
1.0        Demo-Script          author@contoso.com       my test script file description goes here
```

```powershell
Publish-Script -Path D:\ScriptSharingDemo\Demo-Script.ps1 -Repository LocalRepo1
Find-Script -Repository LocalRepo1 -Name "Demo-Script"
```

```Output
Version    Name                 Type       Repository    Description
-------    ----                 ----       ----------    -----------
1.0        Demo-Script          Script     LocalRepo1    my test script file description goes here
```

<span data-ttu-id="d0f72-116">`Test-ScriptFileInfo`Командлет проверяет `Demo-Script.ps1` .</span><span class="sxs-lookup"><span data-stu-id="d0f72-116">The `Test-ScriptFileInfo` cmdlet validates `Demo-Script.ps1`.</span></span> <span data-ttu-id="d0f72-117">`Publish-Script`Командлет публикует скрипт в репозитории **LocalRepo1** .</span><span class="sxs-lookup"><span data-stu-id="d0f72-117">The `Publish-Script` cmdlet publishes the script to the **LocalRepo1** repository.</span></span> <span data-ttu-id="d0f72-118">И наконец.</span><span class="sxs-lookup"><span data-stu-id="d0f72-118">Finally.</span></span> <span data-ttu-id="d0f72-119">`Find-Script` используется для поиска `Demo-Script.ps1` в репозитории **LocalRepo1** .</span><span class="sxs-lookup"><span data-stu-id="d0f72-119">`Find-Script` is used to search for `Demo-Script.ps1` in the **LocalRepo1** repository.</span></span>

## <span data-ttu-id="d0f72-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d0f72-120">PARAMETERS</span></span>

### <span data-ttu-id="d0f72-121">-Credential</span><span class="sxs-lookup"><span data-stu-id="d0f72-121">-Credential</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d0f72-122">-Force</span><span class="sxs-lookup"><span data-stu-id="d0f72-122">-Force</span></span>

<span data-ttu-id="d0f72-123">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="d0f72-123">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="d0f72-124">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="d0f72-124">-LiteralPath</span></span>

<span data-ttu-id="d0f72-125">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="d0f72-125">Specifies a path to one or more locations.</span></span> <span data-ttu-id="d0f72-126">В отличие от параметра **path** , значение параметра **LiteralPath** используется в точности так, как указано.</span><span class="sxs-lookup"><span data-stu-id="d0f72-126">Unlike the **Path** parameter, the value of the **LiteralPath** parameter is used exactly as entered.</span></span> <span data-ttu-id="d0f72-127">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="d0f72-127">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="d0f72-128">Если путь содержит escape-символы, заключите их в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="d0f72-128">If the path includes escape characters, enclose them in single quotation marks.</span></span> <span data-ttu-id="d0f72-129">Это позволит Windows PowerShell не интерпретировать какие-либо символы как символы Escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="d0f72-129">Single quotation marks tell Windows PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="d0f72-130">-NuGetApiKey</span><span class="sxs-lookup"><span data-stu-id="d0f72-130">-NuGetApiKey</span></span>

<span data-ttu-id="d0f72-131">Указывает ключ API, который будет использоваться для публикации скрипта в интерактивной коллекции.</span><span class="sxs-lookup"><span data-stu-id="d0f72-131">Specifies the API key that you want to use to publish a script to the online gallery.</span></span> <span data-ttu-id="d0f72-132">Ключ API является частью вашего профиля в интерактивной коллекции.</span><span class="sxs-lookup"><span data-stu-id="d0f72-132">The API key is part of your profile in the online gallery.</span></span> <span data-ttu-id="d0f72-133">Дополнительные сведения см. в статье [Управление ключами API](/powershell/scripting/gallery/how-to/managing-profile/creating-apikeys).</span><span class="sxs-lookup"><span data-stu-id="d0f72-133">For more information see [Managing API keys](/powershell/scripting/gallery/how-to/managing-profile/creating-apikeys).</span></span>

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

### <span data-ttu-id="d0f72-134">-Path</span><span class="sxs-lookup"><span data-stu-id="d0f72-134">-Path</span></span>

<span data-ttu-id="d0f72-135">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="d0f72-135">Specifies a path to one or more locations.</span></span> <span data-ttu-id="d0f72-136">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="d0f72-136">Wildcards are permitted.</span></span> <span data-ttu-id="d0f72-137">Местоположением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="d0f72-137">The default location is the current directory.</span></span>

```yaml
Type: System.String
Parameter Sets: PathParameterSet
Aliases:

Required: True
Position: Named
Default value: <Current location>
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="d0f72-138">— Репозиторий;</span><span class="sxs-lookup"><span data-stu-id="d0f72-138">-Repository</span></span>

<span data-ttu-id="d0f72-139">Указывает понятное имя репозитория, зарегистрированного при выполнении `Register-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="d0f72-139">Specifies the friendly name of a repository that has been registered by running `Register-PSRepository`.</span></span>

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

### <span data-ttu-id="d0f72-140">-Confirm</span><span class="sxs-lookup"><span data-stu-id="d0f72-140">-Confirm</span></span>

<span data-ttu-id="d0f72-141">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="d0f72-141">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="d0f72-142">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="d0f72-142">-WhatIf</span></span>

<span data-ttu-id="d0f72-143">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="d0f72-143">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="d0f72-144">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="d0f72-144">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="d0f72-145">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="d0f72-145">CommonParameters</span></span>

<span data-ttu-id="d0f72-146">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d0f72-146">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d0f72-147">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d0f72-147">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d0f72-148">Входные данные</span><span class="sxs-lookup"><span data-stu-id="d0f72-148">INPUTS</span></span>

### <span data-ttu-id="d0f72-149">System.String</span><span class="sxs-lookup"><span data-stu-id="d0f72-149">System.String</span></span>

### <span data-ttu-id="d0f72-150">System.Management.Automation.PSCredential</span><span class="sxs-lookup"><span data-stu-id="d0f72-150">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="d0f72-151">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="d0f72-151">OUTPUTS</span></span>

### <span data-ttu-id="d0f72-152">System.Object</span><span class="sxs-lookup"><span data-stu-id="d0f72-152">System.Object</span></span>

## <span data-ttu-id="d0f72-153">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="d0f72-153">NOTES</span></span>

## <span data-ttu-id="d0f72-154">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="d0f72-154">RELATED LINKS</span></span>

[<span data-ttu-id="d0f72-155">Find-Script</span><span class="sxs-lookup"><span data-stu-id="d0f72-155">Find-Script</span></span>](Find-Script.md)

[<span data-ttu-id="d0f72-156">Install-Script</span><span class="sxs-lookup"><span data-stu-id="d0f72-156">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="d0f72-157">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="d0f72-157">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="d0f72-158">Save-Script</span><span class="sxs-lookup"><span data-stu-id="d0f72-158">Save-Script</span></span>](Save-Script.md)

[<span data-ttu-id="d0f72-159">Update-Script</span><span class="sxs-lookup"><span data-stu-id="d0f72-159">Update-Script</span></span>](Update-Script.md)
