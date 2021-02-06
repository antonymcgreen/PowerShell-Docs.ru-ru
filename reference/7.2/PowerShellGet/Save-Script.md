---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/02/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/save-script?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Save-Script
ms.openlocfilehash: 2f672cbb814b0641411bb11ffb17bd1ecef96dda
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "99602477"
---
# <span data-ttu-id="29dcc-102">Save-Script</span><span class="sxs-lookup"><span data-stu-id="29dcc-102">Save-Script</span></span>

## <span data-ttu-id="29dcc-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="29dcc-103">SYNOPSIS</span></span>
<span data-ttu-id="29dcc-104">Сохраняет скрипт.</span><span class="sxs-lookup"><span data-stu-id="29dcc-104">Saves a script.</span></span>

## <span data-ttu-id="29dcc-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="29dcc-105">SYNTAX</span></span>

### <span data-ttu-id="29dcc-106">Намеандпаспараметерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="29dcc-106">NameAndPathParameterSet (Default)</span></span>

```
Save-Script [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] [-Path] <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AllowPrerelease]
 [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="29dcc-107">намеандлитералпаспараметерсет</span><span class="sxs-lookup"><span data-stu-id="29dcc-107">NameAndLiteralPathParameterSet</span></span>

```
Save-Script [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] -LiteralPath <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AllowPrerelease]
 [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="29dcc-108">инпутобжектандлитералпаспараметерсет</span><span class="sxs-lookup"><span data-stu-id="29dcc-108">InputObjectAndLiteralPathParameterSet</span></span>

```
Save-Script [-InputObject] <PSObject[]> -LiteralPath <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AcceptLicense] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="29dcc-109">инпутобжектандпаспараметерсет</span><span class="sxs-lookup"><span data-stu-id="29dcc-109">InputObjectAndPathParameterSet</span></span>

```
Save-Script [-InputObject] <PSObject[]> [-Path] <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AcceptLicense] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="29dcc-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="29dcc-110">DESCRIPTION</span></span>

<span data-ttu-id="29dcc-111">`Save-Script`Командлет сохраняет указанный скрипт.</span><span class="sxs-lookup"><span data-stu-id="29dcc-111">The `Save-Script` cmdlet saves the specified script.</span></span>

## <span data-ttu-id="29dcc-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="29dcc-112">EXAMPLES</span></span>

### <span data-ttu-id="29dcc-113">Пример 1. Сохранение скрипта и проверка метаданных скрипта</span><span class="sxs-lookup"><span data-stu-id="29dcc-113">Example 1: Save a script and validate the script's metadata</span></span>

<span data-ttu-id="29dcc-114">В этом примере сценарий из репозитория сохраняется на локальном компьютере, а метаданные сценария проверяются.</span><span class="sxs-lookup"><span data-stu-id="29dcc-114">In this example, a script from a repository is saved to the local computer and the script's metadata is validated.</span></span>

```powershell
Save-Script -Name Install-VSCode -Repository PSGallery -Path C:\Test\Scripts
Test-ScriptFileInfo -Path C:\Test\Scripts\Install-VSCode.ps1
```

```Output
Version   Name              Author      Description
-------   ----              ------      -----------
1.3       Install-VSCode    Microsoft   This script can be used to easily install Visual Studio Code
```

<span data-ttu-id="29dcc-115">`Save-Script` использует параметр **Name** для указания имени скрипта.</span><span class="sxs-lookup"><span data-stu-id="29dcc-115">`Save-Script` uses the **Name** parameter to specify the script's name.</span></span> <span data-ttu-id="29dcc-116">Параметр **репозитория** указывает, где найти скрипт.</span><span class="sxs-lookup"><span data-stu-id="29dcc-116">The **Repository** parameter specifies where to find the script.</span></span> <span data-ttu-id="29dcc-117">Скрипт сохраняется в расположении, указанном параметром **path** .</span><span class="sxs-lookup"><span data-stu-id="29dcc-117">The script is saved in the location specified by the **Path** parameter.</span></span> <span data-ttu-id="29dcc-118">`Test-ScriptFileInfo` Указывает **путь** и проверяет метаданные скрипта.</span><span class="sxs-lookup"><span data-stu-id="29dcc-118">`Test-ScriptFileInfo` specifies the **Path** and validates the script's metadata.</span></span>

## <span data-ttu-id="29dcc-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="29dcc-119">PARAMETERS</span></span>

### <span data-ttu-id="29dcc-120">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="29dcc-120">-AcceptLicense</span></span>

<span data-ttu-id="29dcc-121">Автоматически принять лицензионное соглашение, если это требуется для сценария.</span><span class="sxs-lookup"><span data-stu-id="29dcc-121">Automatically accept the license agreement if the script requires it.</span></span>

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

### <span data-ttu-id="29dcc-122">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="29dcc-122">-AllowPrerelease</span></span>

<span data-ttu-id="29dcc-123">Позволяет сохранить скрипт, помеченный как предварительный выпуск.</span><span class="sxs-lookup"><span data-stu-id="29dcc-123">Allows you to save a script marked as a prerelease.</span></span>

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

### <span data-ttu-id="29dcc-124">-Confirm</span><span class="sxs-lookup"><span data-stu-id="29dcc-124">-Confirm</span></span>

<span data-ttu-id="29dcc-125">Запрашивает подтверждение перед запуском `Save-Script` .</span><span class="sxs-lookup"><span data-stu-id="29dcc-125">Prompts you for confirmation before running `Save-Script`.</span></span>

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

### <span data-ttu-id="29dcc-126">-Credential</span><span class="sxs-lookup"><span data-stu-id="29dcc-126">-Credential</span></span>

<span data-ttu-id="29dcc-127">Указывает учетную запись пользователя, имеющую разрешение на сохранение скрипта.</span><span class="sxs-lookup"><span data-stu-id="29dcc-127">Specifies a user account that has permission to save a script.</span></span>

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

### <span data-ttu-id="29dcc-128">-Force</span><span class="sxs-lookup"><span data-stu-id="29dcc-128">-Force</span></span>

<span data-ttu-id="29dcc-129">Принудительное `Save-Script` выполнение без запроса подтверждения пользователя.</span><span class="sxs-lookup"><span data-stu-id="29dcc-129">Forces `Save-Script` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="29dcc-130">-InputObject</span><span class="sxs-lookup"><span data-stu-id="29dcc-130">-InputObject</span></span>

<span data-ttu-id="29dcc-131">Принимает объект **PSRepositoryItemInfo** .</span><span class="sxs-lookup"><span data-stu-id="29dcc-131">Accepts a **PSRepositoryItemInfo** object.</span></span> <span data-ttu-id="29dcc-132">Например, выходные данные переводятся `Find-Script` в переменную и используют эту переменную в качестве аргумента **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="29dcc-132">For example, output `Find-Script` to a variable and use that variable as the **InputObject** argument.</span></span>

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

### <span data-ttu-id="29dcc-133">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="29dcc-133">-LiteralPath</span></span>

<span data-ttu-id="29dcc-134">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="29dcc-134">Specifies a path to one or more locations.</span></span> <span data-ttu-id="29dcc-135">Значение параметра **LiteralPath** используется в точности так, как указано.</span><span class="sxs-lookup"><span data-stu-id="29dcc-135">The value of the **LiteralPath** parameter is used exactly as entered.</span></span> <span data-ttu-id="29dcc-136">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="29dcc-136">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="29dcc-137">Если путь содержит escape-символы, заключите путь в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="29dcc-137">If the path includes escape characters, enclose the path within single quotation marks.</span></span> <span data-ttu-id="29dcc-138">PowerShell не интерпретирует символы, заключенные в одинарные кавычки, как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="29dcc-138">PowerShell doesn't interpret any characters enclosed in single quotation marks as escape sequences.</span></span>

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

### <span data-ttu-id="29dcc-139">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="29dcc-139">-MaximumVersion</span></span>

<span data-ttu-id="29dcc-140">Указывает максимальную или самую последнюю версию скрипта для сохранения.</span><span class="sxs-lookup"><span data-stu-id="29dcc-140">Specifies the maximum, or newest version of the script to save.</span></span> <span data-ttu-id="29dcc-141">Параметры **MaximumVersion** и **RequiredVersion** нельзя использовать в одной команде.</span><span class="sxs-lookup"><span data-stu-id="29dcc-141">The **MaximumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="29dcc-142">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="29dcc-142">-MinimumVersion</span></span>

<span data-ttu-id="29dcc-143">Указывает минимальную версию скрипта для сохранения.</span><span class="sxs-lookup"><span data-stu-id="29dcc-143">Specifies the minimum version of a script to save.</span></span> <span data-ttu-id="29dcc-144">Параметры **MinimumVersion** и **RequiredVersion** нельзя использовать в одной команде.</span><span class="sxs-lookup"><span data-stu-id="29dcc-144">The **MinimumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="29dcc-145">-Name</span><span class="sxs-lookup"><span data-stu-id="29dcc-145">-Name</span></span>

<span data-ttu-id="29dcc-146">Указывает массив имен скриптов для сохранения.</span><span class="sxs-lookup"><span data-stu-id="29dcc-146">Specifies an array of script names to save.</span></span>

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

### <span data-ttu-id="29dcc-147">-Path</span><span class="sxs-lookup"><span data-stu-id="29dcc-147">-Path</span></span>

<span data-ttu-id="29dcc-148">Указывает место на локальном компьютере для хранения сохраненного модуля.</span><span class="sxs-lookup"><span data-stu-id="29dcc-148">Specifies the location on the local computer to store a saved module.</span></span> <span data-ttu-id="29dcc-149">Принимает подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="29dcc-149">Accepts wildcard characters.</span></span>

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

### <span data-ttu-id="29dcc-150">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="29dcc-150">-Proxy</span></span>

<span data-ttu-id="29dcc-151">Указывает прокси-сервер для запроса, а не напрямуюе подключение к Интернет-ресурсу.</span><span class="sxs-lookup"><span data-stu-id="29dcc-151">Specifies a proxy server for the request, rather than connecting directly to an internet resource.</span></span>

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

### <span data-ttu-id="29dcc-152">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="29dcc-152">-ProxyCredential</span></span>

<span data-ttu-id="29dcc-153">Указывает учетную запись пользователя, имеющую разрешение на использование прокси-сервера, указанного параметром **прокси** .</span><span class="sxs-lookup"><span data-stu-id="29dcc-153">Specifies a user account that has permission to use the proxy server specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="29dcc-154">— Репозиторий;</span><span class="sxs-lookup"><span data-stu-id="29dcc-154">-Repository</span></span>

<span data-ttu-id="29dcc-155">Указывает понятное имя репозитория, зарегистрированного при выполнении `Register-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="29dcc-155">Specifies the friendly name of a repository that has been registered by running `Register-PSRepository`.</span></span> <span data-ttu-id="29dcc-156">Используется `Get-PSRepository` для вывода зарегистрированных репозиториев.</span><span class="sxs-lookup"><span data-stu-id="29dcc-156">Use `Get-PSRepository` to display registered repositories.</span></span>

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

### <span data-ttu-id="29dcc-157">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="29dcc-157">-RequiredVersion</span></span>

<span data-ttu-id="29dcc-158">Указывает точный номер версии скрипта для сохранения.</span><span class="sxs-lookup"><span data-stu-id="29dcc-158">Specifies the exact version number of the script to save.</span></span>

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

### <span data-ttu-id="29dcc-159">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="29dcc-159">-WhatIf</span></span>

<span data-ttu-id="29dcc-160">Показывает, что произойдет при `Save-Script` запуске.</span><span class="sxs-lookup"><span data-stu-id="29dcc-160">Shows what would happen if `Save-Script` runs.</span></span> <span data-ttu-id="29dcc-161">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="29dcc-161">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="29dcc-162">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="29dcc-162">CommonParameters</span></span>

<span data-ttu-id="29dcc-163">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="29dcc-163">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="29dcc-164">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="29dcc-164">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="29dcc-165">Входные данные</span><span class="sxs-lookup"><span data-stu-id="29dcc-165">INPUTS</span></span>

### <span data-ttu-id="29dcc-166">System.String[]</span><span class="sxs-lookup"><span data-stu-id="29dcc-166">System.String[]</span></span>

### <span data-ttu-id="29dcc-167">System. Management. Automation. PSObject []</span><span class="sxs-lookup"><span data-stu-id="29dcc-167">System.Management.Automation.PSObject[]</span></span>

### <span data-ttu-id="29dcc-168">System.String</span><span class="sxs-lookup"><span data-stu-id="29dcc-168">System.String</span></span>

### <span data-ttu-id="29dcc-169">System.Uri</span><span class="sxs-lookup"><span data-stu-id="29dcc-169">System.Uri</span></span>

### <span data-ttu-id="29dcc-170">System.Management.Automation.PSCredential</span><span class="sxs-lookup"><span data-stu-id="29dcc-170">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="29dcc-171">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="29dcc-171">OUTPUTS</span></span>

### <span data-ttu-id="29dcc-172">System.Object</span><span class="sxs-lookup"><span data-stu-id="29dcc-172">System.Object</span></span>

## <span data-ttu-id="29dcc-173">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="29dcc-173">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="29dcc-174">Начиная с апреля 2020 года коллекция PowerShell не поддерживает протокол TLS (Transport Layer Security) версий 1.0 и 1.1.</span><span class="sxs-lookup"><span data-stu-id="29dcc-174">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="29dcc-175">Если вы не используете TLS 1.2 или более поздней версии, при попытке доступа к коллекции PowerShell возникнет ошибка.</span><span class="sxs-lookup"><span data-stu-id="29dcc-175">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="29dcc-176">Чтобы проверить, используется ли TLS 1.2, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="29dcc-176">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="29dcc-177">Дополнительные сведения см. в [объявлении](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) в блоге, посвященном PowerShell.</span><span class="sxs-lookup"><span data-stu-id="29dcc-177">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="29dcc-178">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="29dcc-178">RELATED LINKS</span></span>

[<span data-ttu-id="29dcc-179">Find-Script</span><span class="sxs-lookup"><span data-stu-id="29dcc-179">Find-Script</span></span>](Find-Script.md)

[<span data-ttu-id="29dcc-180">Install-Script</span><span class="sxs-lookup"><span data-stu-id="29dcc-180">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="29dcc-181">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="29dcc-181">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="29dcc-182">Test-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="29dcc-182">Test-ScriptFileInfo</span></span>](Test-ScriptFileInfo.md)

[<span data-ttu-id="29dcc-183">Uninstall-Script</span><span class="sxs-lookup"><span data-stu-id="29dcc-183">Uninstall-Script</span></span>](Uninstall-Script.md)

[<span data-ttu-id="29dcc-184">Update-Script</span><span class="sxs-lookup"><span data-stu-id="29dcc-184">Update-Script</span></span>](Update-Script.md)
