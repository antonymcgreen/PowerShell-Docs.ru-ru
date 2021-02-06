---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 03/27/2020
online version: https://docs.microsoft.com/powershell/module/powershellget/publish-script?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Publish-Script
ms.openlocfilehash: 344a789c9daced51b549d562b7fd74677fe403dc
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "99605268"
---
# <span data-ttu-id="2971f-102">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="2971f-102">Publish-Script</span></span>

## <span data-ttu-id="2971f-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="2971f-103">SYNOPSIS</span></span>
<span data-ttu-id="2971f-104">Публикует скрипт.</span><span class="sxs-lookup"><span data-stu-id="2971f-104">Publishes a script.</span></span>

## <span data-ttu-id="2971f-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2971f-105">SYNTAX</span></span>

### <span data-ttu-id="2971f-106">Паспараметерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="2971f-106">PathParameterSet (Default)</span></span>

```
Publish-Script -Path <String> [-NuGetApiKey <String>] [-Repository <String>]
 [-Credential <PSCredential>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="2971f-107">литералпаспараметерсет</span><span class="sxs-lookup"><span data-stu-id="2971f-107">LiteralPathParameterSet</span></span>

```
Publish-Script -LiteralPath <String> [-NuGetApiKey <String>] [-Repository <String>]
 [-Credential <PSCredential>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="2971f-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2971f-108">DESCRIPTION</span></span>

<span data-ttu-id="2971f-109">`Publish-Script`Командлет публикует указанный скрипт в веб-коллекции.</span><span class="sxs-lookup"><span data-stu-id="2971f-109">The `Publish-Script` cmdlet publishes the specified script to the online gallery.</span></span>

## <span data-ttu-id="2971f-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="2971f-110">EXAMPLES</span></span>

### <span data-ttu-id="2971f-111">Пример 1. Создание файла скрипта, добавление в него содержимого и его публикация</span><span class="sxs-lookup"><span data-stu-id="2971f-111">Example 1: Create a script file, add content to it, and publish it</span></span>

<span data-ttu-id="2971f-112">`New-ScriptFileInfo`Командлет создает файл скрипта с именем `Demo-Script.ps1` .</span><span class="sxs-lookup"><span data-stu-id="2971f-112">The `New-ScriptFileInfo` cmdlet creates a script file named `Demo-Script.ps1`.</span></span> <span data-ttu-id="2971f-113">`Get-Content` Отображает содержимое `Demo-Script.ps1` .</span><span class="sxs-lookup"><span data-stu-id="2971f-113">`Get-Content` displays the content of `Demo-Script.ps1`.</span></span> <span data-ttu-id="2971f-114">`Add-Content`Командлет добавляет функцию и рабочий процесс в `Demo-Script.ps1` .</span><span class="sxs-lookup"><span data-stu-id="2971f-114">The `Add-Content` cmdlet adds a function and a workflow to `Demo-Script.ps1`.</span></span>

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

<span data-ttu-id="2971f-115">`Test-ScriptFileInfo`Командлет проверяет `Demo-Script.ps1` .</span><span class="sxs-lookup"><span data-stu-id="2971f-115">The `Test-ScriptFileInfo` cmdlet validates `Demo-Script.ps1`.</span></span> <span data-ttu-id="2971f-116">`Publish-Script`Командлет публикует скрипт в репозитории **LocalRepo1** .</span><span class="sxs-lookup"><span data-stu-id="2971f-116">The `Publish-Script` cmdlet publishes the script to the **LocalRepo1** repository.</span></span> <span data-ttu-id="2971f-117">И наконец.</span><span class="sxs-lookup"><span data-stu-id="2971f-117">Finally.</span></span> <span data-ttu-id="2971f-118">`Find-Script` используется для поиска `Demo-Script.ps1` в репозитории **LocalRepo1** .</span><span class="sxs-lookup"><span data-stu-id="2971f-118">`Find-Script` is used to search for `Demo-Script.ps1` in the **LocalRepo1** repository.</span></span>

## <span data-ttu-id="2971f-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2971f-119">PARAMETERS</span></span>

### <span data-ttu-id="2971f-120">-Confirm</span><span class="sxs-lookup"><span data-stu-id="2971f-120">-Confirm</span></span>

<span data-ttu-id="2971f-121">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="2971f-121">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="2971f-122">-Credential</span><span class="sxs-lookup"><span data-stu-id="2971f-122">-Credential</span></span>

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

### <span data-ttu-id="2971f-123">-Force</span><span class="sxs-lookup"><span data-stu-id="2971f-123">-Force</span></span>

<span data-ttu-id="2971f-124">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="2971f-124">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="2971f-125">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="2971f-125">-LiteralPath</span></span>

<span data-ttu-id="2971f-126">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="2971f-126">Specifies a path to one or more locations.</span></span> <span data-ttu-id="2971f-127">В отличие от параметра **path** , значение параметра **LiteralPath** используется в точности так, как указано.</span><span class="sxs-lookup"><span data-stu-id="2971f-127">Unlike the **Path** parameter, the value of the **LiteralPath** parameter is used exactly as entered.</span></span> <span data-ttu-id="2971f-128">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="2971f-128">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="2971f-129">Если путь содержит escape-символы, заключите их в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="2971f-129">If the path includes escape characters, enclose them in single quotation marks.</span></span> <span data-ttu-id="2971f-130">Это позволит Windows PowerShell не интерпретировать какие-либо символы как символы Escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="2971f-130">Single quotation marks tell Windows PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="2971f-131">-NuGetApiKey</span><span class="sxs-lookup"><span data-stu-id="2971f-131">-NuGetApiKey</span></span>

<span data-ttu-id="2971f-132">Указывает ключ API, который будет использоваться для публикации скрипта в интерактивной коллекции.</span><span class="sxs-lookup"><span data-stu-id="2971f-132">Specifies the API key that you want to use to publish a script to the online gallery.</span></span> <span data-ttu-id="2971f-133">Ключ API является частью вашего профиля в интерактивной коллекции.</span><span class="sxs-lookup"><span data-stu-id="2971f-133">The API key is part of your profile in the online gallery.</span></span> <span data-ttu-id="2971f-134">Дополнительные сведения см. в статье [Управление ключами API](/powershell/scripting/gallery/how-to/managing-profile/creating-apikeys).</span><span class="sxs-lookup"><span data-stu-id="2971f-134">For more information see [Managing API keys](/powershell/scripting/gallery/how-to/managing-profile/creating-apikeys).</span></span>

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

### <span data-ttu-id="2971f-135">-Path</span><span class="sxs-lookup"><span data-stu-id="2971f-135">-Path</span></span>

<span data-ttu-id="2971f-136">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="2971f-136">Specifies a path to one or more locations.</span></span> <span data-ttu-id="2971f-137">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="2971f-137">Wildcards are permitted.</span></span> <span data-ttu-id="2971f-138">Местоположением по умолчанию является текущий каталог.</span><span class="sxs-lookup"><span data-stu-id="2971f-138">The default location is the current directory.</span></span>

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

### <span data-ttu-id="2971f-139">— Репозиторий;</span><span class="sxs-lookup"><span data-stu-id="2971f-139">-Repository</span></span>

<span data-ttu-id="2971f-140">Указывает понятное имя репозитория, зарегистрированного при выполнении `Register-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="2971f-140">Specifies the friendly name of a repository that has been registered by running `Register-PSRepository`.</span></span>

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

### <span data-ttu-id="2971f-141">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="2971f-141">-WhatIf</span></span>

<span data-ttu-id="2971f-142">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="2971f-142">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="2971f-143">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="2971f-143">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="2971f-144">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="2971f-144">CommonParameters</span></span>

<span data-ttu-id="2971f-145">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2971f-145">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2971f-146">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2971f-146">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2971f-147">Входные данные</span><span class="sxs-lookup"><span data-stu-id="2971f-147">INPUTS</span></span>

### <span data-ttu-id="2971f-148">System.String</span><span class="sxs-lookup"><span data-stu-id="2971f-148">System.String</span></span>

### <span data-ttu-id="2971f-149">System.Management.Automation.PSCredential</span><span class="sxs-lookup"><span data-stu-id="2971f-149">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="2971f-150">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="2971f-150">OUTPUTS</span></span>

### <span data-ttu-id="2971f-151">System.Object</span><span class="sxs-lookup"><span data-stu-id="2971f-151">System.Object</span></span>

## <span data-ttu-id="2971f-152">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="2971f-152">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2971f-153">Начиная с апреля 2020 года коллекция PowerShell не поддерживает протокол TLS (Transport Layer Security) версий 1.0 и 1.1.</span><span class="sxs-lookup"><span data-stu-id="2971f-153">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="2971f-154">Если вы не используете TLS 1.2 или более поздней версии, при попытке доступа к коллекции PowerShell возникнет ошибка.</span><span class="sxs-lookup"><span data-stu-id="2971f-154">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="2971f-155">Чтобы проверить, используется ли TLS 1.2, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="2971f-155">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="2971f-156">Дополнительные сведения см. в [объявлении](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) в блоге, посвященном PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2971f-156">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="2971f-157">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="2971f-157">RELATED LINKS</span></span>

[<span data-ttu-id="2971f-158">Find-Script</span><span class="sxs-lookup"><span data-stu-id="2971f-158">Find-Script</span></span>](Find-Script.md)

[<span data-ttu-id="2971f-159">Install-Script</span><span class="sxs-lookup"><span data-stu-id="2971f-159">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="2971f-160">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="2971f-160">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="2971f-161">Save-Script</span><span class="sxs-lookup"><span data-stu-id="2971f-161">Save-Script</span></span>](Save-Script.md)

[<span data-ttu-id="2971f-162">Update-Script</span><span class="sxs-lookup"><span data-stu-id="2971f-162">Update-Script</span></span>](Update-Script.md)
