---
external help file: PSModule-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PowerShellGet
ms.date: 03/27/2020
online version: https://docs.microsoft.com/powershell/module/powershellget/publish-script?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Publish-Script
ms.openlocfilehash: e7ac362b853a006da25bacccaa64f671cac30814
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "94892180"
---
# <span data-ttu-id="00481-103">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="00481-103">Publish-Script</span></span>

## <span data-ttu-id="00481-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="00481-104">SYNOPSIS</span></span>
<span data-ttu-id="00481-105">Публикует скрипт.</span><span class="sxs-lookup"><span data-stu-id="00481-105">Publishes a script.</span></span>

## <span data-ttu-id="00481-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="00481-106">SYNTAX</span></span>

### <span data-ttu-id="00481-107">Паспараметерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="00481-107">PathParameterSet (Default)</span></span>

```
Publish-Script -Path <String> [-NuGetApiKey <String>] [-Repository <String>]
 [-Credential <PSCredential>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="00481-108">литералпаспараметерсет</span><span class="sxs-lookup"><span data-stu-id="00481-108">LiteralPathParameterSet</span></span>

```
Publish-Script -LiteralPath <String> [-NuGetApiKey <String>] [-Repository <String>]
 [-Credential <PSCredential>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="00481-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="00481-109">DESCRIPTION</span></span>

<span data-ttu-id="00481-110">`Publish-Script`Командлет публикует указанный скрипт в веб-коллекции.</span><span class="sxs-lookup"><span data-stu-id="00481-110">The `Publish-Script` cmdlet publishes the specified script to the online gallery.</span></span>

## <span data-ttu-id="00481-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="00481-111">EXAMPLES</span></span>

### <span data-ttu-id="00481-112">Пример 1. Создание файла скрипта, добавление в него содержимого и его публикация</span><span class="sxs-lookup"><span data-stu-id="00481-112">Example 1: Create a script file, add content to it, and publish it</span></span>

<span data-ttu-id="00481-113">`New-ScriptFileInfo`Командлет создает файл скрипта с именем `Demo-Script.ps1` .</span><span class="sxs-lookup"><span data-stu-id="00481-113">The `New-ScriptFileInfo` cmdlet creates a script file named `Demo-Script.ps1`.</span></span> <span data-ttu-id="00481-114">`Get-Content` Отображает содержимое `Demo-Script.ps1` .</span><span class="sxs-lookup"><span data-stu-id="00481-114">`Get-Content` displays the content of `Demo-Script.ps1`.</span></span> <span data-ttu-id="00481-115">`Add-Content`Командлет добавляет функцию и рабочий процесс в `Demo-Script.ps1` .</span><span class="sxs-lookup"><span data-stu-id="00481-115">The `Add-Content` cmdlet adds a function and a workflow to `Demo-Script.ps1`.</span></span>

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

<span data-ttu-id="00481-116">`Test-ScriptFileInfo`Командлет проверяет `Demo-Script.ps1` .</span><span class="sxs-lookup"><span data-stu-id="00481-116">The `Test-ScriptFileInfo` cmdlet validates `Demo-Script.ps1`.</span></span> <span data-ttu-id="00481-117">`Publish-Script`Командлет публикует скрипт в репозитории **LocalRepo1** .</span><span class="sxs-lookup"><span data-stu-id="00481-117">The `Publish-Script` cmdlet publishes the script to the **LocalRepo1** repository.</span></span> <span data-ttu-id="00481-118">И наконец.</span><span class="sxs-lookup"><span data-stu-id="00481-118">Finally.</span></span> <span data-ttu-id="00481-119">`Find-Script` используется для поиска `Demo-Script.ps1` в репозитории **LocalRepo1** .</span><span class="sxs-lookup"><span data-stu-id="00481-119">`Find-Script` is used to search for `Demo-Script.ps1` in the **LocalRepo1** repository.</span></span>

## <span data-ttu-id="00481-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="00481-120">PARAMETERS</span></span>

### <span data-ttu-id="00481-121">-Confirm</span><span class="sxs-lookup"><span data-stu-id="00481-121">-Confirm</span></span>

<span data-ttu-id="00481-122">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="00481-122">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="00481-123">-Credential</span><span class="sxs-lookup"><span data-stu-id="00481-123">-Credential</span></span>

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

### <span data-ttu-id="00481-124">-Force</span><span class="sxs-lookup"><span data-stu-id="00481-124">-Force</span></span>

<span data-ttu-id="00481-125">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="00481-125">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="00481-126">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="00481-126">-LiteralPath</span></span>

<span data-ttu-id="00481-127">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="00481-127">Specifies a path to one or more locations.</span></span> <span data-ttu-id="00481-128">В отличие от параметра **path** , значение параметра **LiteralPath** используется в точности так, как указано.</span><span class="sxs-lookup"><span data-stu-id="00481-128">Unlike the **Path** parameter, the value of the **LiteralPath** parameter is used exactly as entered.</span></span> <span data-ttu-id="00481-129">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="00481-129">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="00481-130">Если путь содержит escape-символы, заключите их в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="00481-130">If the path includes escape characters, enclose them in single quotation marks.</span></span> <span data-ttu-id="00481-131">Это позволит Windows PowerShell не интерпретировать какие-либо символы как символы Escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="00481-131">Single quotation marks tell Windows PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="00481-132">-NuGetApiKey</span><span class="sxs-lookup"><span data-stu-id="00481-132">-NuGetApiKey</span></span>

<span data-ttu-id="00481-133">Указывает ключ API, который будет использоваться для публикации скрипта в интерактивной коллекции.</span><span class="sxs-lookup"><span data-stu-id="00481-133">Specifies the API key that you want to use to publish a script to the online gallery.</span></span> <span data-ttu-id="00481-134">Ключ API является частью вашего профиля в интерактивной коллекции.</span><span class="sxs-lookup"><span data-stu-id="00481-134">The API key is part of your profile in the online gallery.</span></span> <span data-ttu-id="00481-135">Дополнительные сведения см. в статье [Управление ключами API](/powershell/scripting/gallery/how-to/managing-profile/creating-apikeys).</span><span class="sxs-lookup"><span data-stu-id="00481-135">For more information see [Managing API keys](/powershell/scripting/gallery/how-to/managing-profile/creating-apikeys).</span></span>

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

### <span data-ttu-id="00481-136">-Path</span><span class="sxs-lookup"><span data-stu-id="00481-136">-Path</span></span>

<span data-ttu-id="00481-137">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="00481-137">Specifies a path to one or more locations.</span></span> <span data-ttu-id="00481-138">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="00481-138">Wildcards are permitted.</span></span> <span data-ttu-id="00481-139">Местоположением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="00481-139">The default location is the current directory.</span></span>

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

### <span data-ttu-id="00481-140">— Репозиторий;</span><span class="sxs-lookup"><span data-stu-id="00481-140">-Repository</span></span>

<span data-ttu-id="00481-141">Указывает понятное имя репозитория, зарегистрированного при выполнении `Register-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="00481-141">Specifies the friendly name of a repository that has been registered by running `Register-PSRepository`.</span></span>

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

### <span data-ttu-id="00481-142">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="00481-142">-WhatIf</span></span>

<span data-ttu-id="00481-143">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="00481-143">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="00481-144">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="00481-144">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="00481-145">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="00481-145">CommonParameters</span></span>

<span data-ttu-id="00481-146">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="00481-146">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="00481-147">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="00481-147">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="00481-148">Входные данные</span><span class="sxs-lookup"><span data-stu-id="00481-148">INPUTS</span></span>

### <span data-ttu-id="00481-149">System.String</span><span class="sxs-lookup"><span data-stu-id="00481-149">System.String</span></span>

### <span data-ttu-id="00481-150">System.Management.Automation.PSCredential</span><span class="sxs-lookup"><span data-stu-id="00481-150">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="00481-151">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="00481-151">OUTPUTS</span></span>

### <span data-ttu-id="00481-152">System.Object</span><span class="sxs-lookup"><span data-stu-id="00481-152">System.Object</span></span>

## <span data-ttu-id="00481-153">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="00481-153">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="00481-154">По состоянию на апрель 2020 коллекция PowerShell больше не поддерживает TLS-версии 1,0 и 1,1.</span><span class="sxs-lookup"><span data-stu-id="00481-154">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="00481-155">Если вы не используете TLS 1,2 или более поздней версии, при попытке доступа к коллекция PowerShell возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="00481-155">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="00481-156">Используйте следующую команду, чтобы убедиться, что используется TLS 1,2:</span><span class="sxs-lookup"><span data-stu-id="00481-156">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="00481-157">Дополнительные сведения см. в [объявлении](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) в блоге PowerShell.</span><span class="sxs-lookup"><span data-stu-id="00481-157">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="00481-158">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="00481-158">RELATED LINKS</span></span>

[<span data-ttu-id="00481-159">Find-Script</span><span class="sxs-lookup"><span data-stu-id="00481-159">Find-Script</span></span>](Find-Script.md)

[<span data-ttu-id="00481-160">Install-Script</span><span class="sxs-lookup"><span data-stu-id="00481-160">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="00481-161">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="00481-161">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="00481-162">Save-Script</span><span class="sxs-lookup"><span data-stu-id="00481-162">Save-Script</span></span>](Save-Script.md)

[<span data-ttu-id="00481-163">Update-Script</span><span class="sxs-lookup"><span data-stu-id="00481-163">Update-Script</span></span>](Update-Script.md)
