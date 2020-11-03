---
external help file: PSModule-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/02/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/save-script?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Save-Script
ms.openlocfilehash: aefc9103b182ab232cb986a2ebb2b51f7cd09767
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228274"
---
# <span data-ttu-id="71069-103">Save-Script</span><span class="sxs-lookup"><span data-stu-id="71069-103">Save-Script</span></span>

## <span data-ttu-id="71069-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="71069-104">SYNOPSIS</span></span>
<span data-ttu-id="71069-105">Сохраняет скрипт.</span><span class="sxs-lookup"><span data-stu-id="71069-105">Saves a script.</span></span>

## <span data-ttu-id="71069-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="71069-106">SYNTAX</span></span>

### <span data-ttu-id="71069-107">Намеандпаспараметерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="71069-107">NameAndPathParameterSet (Default)</span></span>

```
Save-Script [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] [-Path] <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AllowPrerelease]
 [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="71069-108">намеандлитералпаспараметерсет</span><span class="sxs-lookup"><span data-stu-id="71069-108">NameAndLiteralPathParameterSet</span></span>

```
Save-Script [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] -LiteralPath <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AllowPrerelease]
 [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="71069-109">инпутобжектандлитералпаспараметерсет</span><span class="sxs-lookup"><span data-stu-id="71069-109">InputObjectAndLiteralPathParameterSet</span></span>

```
Save-Script [-InputObject] <PSObject[]> -LiteralPath <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AcceptLicense] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="71069-110">инпутобжектандпаспараметерсет</span><span class="sxs-lookup"><span data-stu-id="71069-110">InputObjectAndPathParameterSet</span></span>

```
Save-Script [-InputObject] <PSObject[]> [-Path] <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AcceptLicense] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="71069-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="71069-111">DESCRIPTION</span></span>

<span data-ttu-id="71069-112">`Save-Script`Командлет сохраняет указанный скрипт.</span><span class="sxs-lookup"><span data-stu-id="71069-112">The `Save-Script` cmdlet saves the specified script.</span></span>

## <span data-ttu-id="71069-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="71069-113">EXAMPLES</span></span>

### <span data-ttu-id="71069-114">Пример 1. Сохранение скрипта и проверка метаданных скрипта</span><span class="sxs-lookup"><span data-stu-id="71069-114">Example 1: Save a script and validate the script's metadata</span></span>

<span data-ttu-id="71069-115">В этом примере сценарий из репозитория сохраняется на локальном компьютере, а метаданные сценария проверяются.</span><span class="sxs-lookup"><span data-stu-id="71069-115">In this example, a script from a repository is saved to the local computer and the script's metadata is validated.</span></span>

```powershell
Save-Script -Name Install-VSCode -Repository PSGallery -Path C:\Test\Scripts
Test-ScriptFileInfo -Path C:\Test\Scripts\Install-VSCode.ps1
```

```Output
Version   Name              Author      Description
-------   ----              ------      -----------
1.3       Install-VSCode    Microsoft   This script can be used to easily install Visual Studio Code
```

<span data-ttu-id="71069-116">`Save-Script` использует параметр **Name** для указания имени скрипта.</span><span class="sxs-lookup"><span data-stu-id="71069-116">`Save-Script` uses the **Name** parameter to specify the script's name.</span></span> <span data-ttu-id="71069-117">Параметр **репозитория** указывает, где найти скрипт.</span><span class="sxs-lookup"><span data-stu-id="71069-117">The **Repository** parameter specifies where to find the script.</span></span> <span data-ttu-id="71069-118">Скрипт сохраняется в расположении, указанном параметром **path** .</span><span class="sxs-lookup"><span data-stu-id="71069-118">The script is saved in the location specified by the **Path** parameter.</span></span> <span data-ttu-id="71069-119">`Test-ScriptFileInfo` Указывает **путь** и проверяет метаданные скрипта.</span><span class="sxs-lookup"><span data-stu-id="71069-119">`Test-ScriptFileInfo` specifies the **Path** and validates the script's metadata.</span></span>

## <span data-ttu-id="71069-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="71069-120">PARAMETERS</span></span>

### <span data-ttu-id="71069-121">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="71069-121">-AcceptLicense</span></span>

<span data-ttu-id="71069-122">Автоматически принять лицензионное соглашение, если это требуется для сценария.</span><span class="sxs-lookup"><span data-stu-id="71069-122">Automatically accept the license agreement if the script requires it.</span></span>

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

### <span data-ttu-id="71069-123">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="71069-123">-AllowPrerelease</span></span>

<span data-ttu-id="71069-124">Позволяет сохранить скрипт, помеченный как предварительный выпуск.</span><span class="sxs-lookup"><span data-stu-id="71069-124">Allows you to save a script marked as a prerelease.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NameAndPathParameterSet, NameAndLiteralPathParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="71069-125">-Confirm</span><span class="sxs-lookup"><span data-stu-id="71069-125">-Confirm</span></span>

<span data-ttu-id="71069-126">Запрашивает подтверждение перед запуском `Save-Script` .</span><span class="sxs-lookup"><span data-stu-id="71069-126">Prompts you for confirmation before running `Save-Script`.</span></span>

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

### <span data-ttu-id="71069-127">-Credential</span><span class="sxs-lookup"><span data-stu-id="71069-127">-Credential</span></span>

<span data-ttu-id="71069-128">Указывает учетную запись пользователя, имеющую разрешение на сохранение скрипта.</span><span class="sxs-lookup"><span data-stu-id="71069-128">Specifies a user account that has permission to save a script.</span></span>

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

### <span data-ttu-id="71069-129">-Force</span><span class="sxs-lookup"><span data-stu-id="71069-129">-Force</span></span>

<span data-ttu-id="71069-130">Принудительное `Save-Script` выполнение без запроса подтверждения пользователя.</span><span class="sxs-lookup"><span data-stu-id="71069-130">Forces `Save-Script` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="71069-131">-InputObject</span><span class="sxs-lookup"><span data-stu-id="71069-131">-InputObject</span></span>

<span data-ttu-id="71069-132">Принимает объект **PSRepositoryItemInfo** .</span><span class="sxs-lookup"><span data-stu-id="71069-132">Accepts a **PSRepositoryItemInfo** object.</span></span> <span data-ttu-id="71069-133">Например, выходные данные переводятся `Find-Script` в переменную и используют эту переменную в качестве аргумента **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="71069-133">For example, output `Find-Script` to a variable and use that variable as the **InputObject** argument.</span></span>

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: InputObjectAndLiteralPathParameterSet, InputObjectAndPathParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="71069-134">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="71069-134">-LiteralPath</span></span>

<span data-ttu-id="71069-135">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="71069-135">Specifies a path to one or more locations.</span></span> <span data-ttu-id="71069-136">Значение параметра **LiteralPath** используется в точности так, как указано.</span><span class="sxs-lookup"><span data-stu-id="71069-136">The value of the **LiteralPath** parameter is used exactly as entered.</span></span> <span data-ttu-id="71069-137">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="71069-137">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="71069-138">Если путь содержит escape-символы, заключите путь в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="71069-138">If the path includes escape characters, enclose the path within single quotation marks.</span></span> <span data-ttu-id="71069-139">PowerShell не интерпретирует символы, заключенные в одинарные кавычки, как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="71069-139">PowerShell doesn't interpret any characters enclosed in single quotation marks as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: NameAndLiteralPathParameterSet, InputObjectAndLiteralPathParameterSet
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="71069-140">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="71069-140">-MaximumVersion</span></span>

<span data-ttu-id="71069-141">Указывает максимальную или самую последнюю версию скрипта для сохранения.</span><span class="sxs-lookup"><span data-stu-id="71069-141">Specifies the maximum, or newest version of the script to save.</span></span> <span data-ttu-id="71069-142">Параметры **MaximumVersion** и **RequiredVersion** нельзя использовать в одной команде.</span><span class="sxs-lookup"><span data-stu-id="71069-142">The **MaximumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: NameAndPathParameterSet, NameAndLiteralPathParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="71069-143">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="71069-143">-MinimumVersion</span></span>

<span data-ttu-id="71069-144">Указывает минимальную версию скрипта для сохранения.</span><span class="sxs-lookup"><span data-stu-id="71069-144">Specifies the minimum version of a script to save.</span></span> <span data-ttu-id="71069-145">Параметры **MinimumVersion** и **RequiredVersion** нельзя использовать в одной команде.</span><span class="sxs-lookup"><span data-stu-id="71069-145">The **MinimumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: NameAndPathParameterSet, NameAndLiteralPathParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="71069-146">-Name</span><span class="sxs-lookup"><span data-stu-id="71069-146">-Name</span></span>

<span data-ttu-id="71069-147">Указывает массив имен скриптов для сохранения.</span><span class="sxs-lookup"><span data-stu-id="71069-147">Specifies an array of script names to save.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameAndPathParameterSet, NameAndLiteralPathParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="71069-148">-Path</span><span class="sxs-lookup"><span data-stu-id="71069-148">-Path</span></span>

<span data-ttu-id="71069-149">Указывает место на локальном компьютере для хранения сохраненного модуля.</span><span class="sxs-lookup"><span data-stu-id="71069-149">Specifies the location on the local computer to store a saved module.</span></span> <span data-ttu-id="71069-150">Принимает подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="71069-150">Accepts wildcard characters.</span></span>

```yaml
Type: System.String
Parameter Sets: NameAndPathParameterSet, InputObjectAndPathParameterSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="71069-151">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="71069-151">-Proxy</span></span>

<span data-ttu-id="71069-152">Указывает прокси-сервер для запроса, а не напрямуюе подключение к Интернет-ресурсу.</span><span class="sxs-lookup"><span data-stu-id="71069-152">Specifies a proxy server for the request, rather than connecting directly to an internet resource.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="71069-153">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="71069-153">-ProxyCredential</span></span>

<span data-ttu-id="71069-154">Указывает учетную запись пользователя, имеющую разрешение на использование прокси-сервера, указанного параметром **прокси** .</span><span class="sxs-lookup"><span data-stu-id="71069-154">Specifies a user account that has permission to use the proxy server specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="71069-155">— Репозиторий;</span><span class="sxs-lookup"><span data-stu-id="71069-155">-Repository</span></span>

<span data-ttu-id="71069-156">Указывает понятное имя репозитория, зарегистрированного при выполнении `Register-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="71069-156">Specifies the friendly name of a repository that has been registered by running `Register-PSRepository`.</span></span> <span data-ttu-id="71069-157">Используется `Get-PSRepository` для вывода зарегистрированных репозиториев.</span><span class="sxs-lookup"><span data-stu-id="71069-157">Use `Get-PSRepository` to display registered repositories.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameAndPathParameterSet, NameAndLiteralPathParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="71069-158">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="71069-158">-RequiredVersion</span></span>

<span data-ttu-id="71069-159">Указывает точный номер версии скрипта для сохранения.</span><span class="sxs-lookup"><span data-stu-id="71069-159">Specifies the exact version number of the script to save.</span></span>

```yaml
Type: System.String
Parameter Sets: NameAndPathParameterSet, NameAndLiteralPathParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="71069-160">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="71069-160">-WhatIf</span></span>

<span data-ttu-id="71069-161">Показывает, что произойдет при `Save-Script` запуске.</span><span class="sxs-lookup"><span data-stu-id="71069-161">Shows what would happen if `Save-Script` runs.</span></span> <span data-ttu-id="71069-162">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="71069-162">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="71069-163">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="71069-163">CommonParameters</span></span>

<span data-ttu-id="71069-164">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="71069-164">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="71069-165">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="71069-165">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="71069-166">Входные данные</span><span class="sxs-lookup"><span data-stu-id="71069-166">INPUTS</span></span>

## <span data-ttu-id="71069-167">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="71069-167">OUTPUTS</span></span>

## <span data-ttu-id="71069-168">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="71069-168">NOTES</span></span>

## <span data-ttu-id="71069-169">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="71069-169">RELATED LINKS</span></span>

[<span data-ttu-id="71069-170">Find-Script</span><span class="sxs-lookup"><span data-stu-id="71069-170">Find-Script</span></span>](Find-Script.md)

[<span data-ttu-id="71069-171">Install-Script</span><span class="sxs-lookup"><span data-stu-id="71069-171">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="71069-172">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="71069-172">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="71069-173">Test-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="71069-173">Test-ScriptFileInfo</span></span>](Test-ScriptFileInfo.md)

[<span data-ttu-id="71069-174">Uninstall-Script</span><span class="sxs-lookup"><span data-stu-id="71069-174">Uninstall-Script</span></span>](Uninstall-Script.md)

[<span data-ttu-id="71069-175">Update-Script</span><span class="sxs-lookup"><span data-stu-id="71069-175">Update-Script</span></span>](Update-Script.md)
