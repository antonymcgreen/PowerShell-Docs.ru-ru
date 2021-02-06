---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/09/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/update-scriptfileinfo?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-ScriptFileInfo
ms.openlocfilehash: de138a27ed9425057406dc6120a8354b72a3b8a3
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604432"
---
# <span data-ttu-id="b8b19-102">Update-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="b8b19-102">Update-ScriptFileInfo</span></span>

## <span data-ttu-id="b8b19-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="b8b19-103">SYNOPSIS</span></span>
<span data-ttu-id="b8b19-104">Обновляет сведения для скрипта.</span><span class="sxs-lookup"><span data-stu-id="b8b19-104">Updates information for a script.</span></span>

## <span data-ttu-id="b8b19-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b8b19-105">SYNTAX</span></span>

### <span data-ttu-id="b8b19-106">Паспараметерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="b8b19-106">PathParameterSet (Default)</span></span>

```
Update-ScriptFileInfo [-Path] <String> [-Version <String>] [-Author <String>] [-Guid <Guid>]
 [-Description <String>] [-CompanyName <String>] [-Copyright <String>] [-RequiredModules <Object[]>]
 [-ExternalModuleDependencies <String[]>] [-RequiredScripts <String[]>]
 [-ExternalScriptDependencies <String[]>] [-Tags <String[]>] [-ProjectUri <Uri>] [-LicenseUri <Uri>]
 [-IconUri <Uri>] [-ReleaseNotes <String[]>] [-PrivateData <String>] [-PassThru] [-Force] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="b8b19-107">литералпаспараметерсет</span><span class="sxs-lookup"><span data-stu-id="b8b19-107">LiteralPathParameterSet</span></span>

```
Update-ScriptFileInfo [-LiteralPath] <String> [-Version <String>] [-Author <String>] [-Guid <Guid>]
 [-Description <String>] [-CompanyName <String>] [-Copyright <String>] [-RequiredModules <Object[]>]
 [-ExternalModuleDependencies <String[]>] [-RequiredScripts <String[]>]
 [-ExternalScriptDependencies <String[]>] [-Tags <String[]>] [-ProjectUri <Uri>] [-LicenseUri <Uri>]
 [-IconUri <Uri>] [-ReleaseNotes <String[]>] [-PrivateData <String>] [-PassThru] [-Force] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="b8b19-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b8b19-108">DESCRIPTION</span></span>

<span data-ttu-id="b8b19-109">`Update-ScriptFileInfo`Командлет обновляет значения свойств скрипта.</span><span class="sxs-lookup"><span data-stu-id="b8b19-109">The `Update-ScriptFileInfo` cmdlet updates a script's property values.</span></span> <span data-ttu-id="b8b19-110">Например, значения для версии, автора или описания.</span><span class="sxs-lookup"><span data-stu-id="b8b19-110">For example, the values for version, author, or description.</span></span>

## <span data-ttu-id="b8b19-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="b8b19-111">EXAMPLES</span></span>

### <span data-ttu-id="b8b19-112">Пример 1. Обновление версии файла скрипта</span><span class="sxs-lookup"><span data-stu-id="b8b19-112">Example 1: Update the version of a script file</span></span>

<span data-ttu-id="b8b19-113">В этом примере существующий файл скрипта обновляется новыми значениями свойств.</span><span class="sxs-lookup"><span data-stu-id="b8b19-113">In this example, an existing script file is updated with new property values.</span></span>

<span data-ttu-id="b8b19-114">Сплаттинг используется для передачи параметров в `Update-ScriptFileInfo` командлет.</span><span class="sxs-lookup"><span data-stu-id="b8b19-114">Splatting is used to pass parameters to the `Update-ScriptFileInfo` cmdlet.</span></span> <span data-ttu-id="b8b19-115">Дополнительные сведения см. в разделе [about_Splatting](../Microsoft.Powershell.Core/About/about_splatting.md).</span><span class="sxs-lookup"><span data-stu-id="b8b19-115">For more information, see [about_Splatting](../Microsoft.Powershell.Core/About/about_splatting.md).</span></span>

```powershell
$Parms = @{
  Path = "C:\Test\Temp-Scriptfile.ps1"
  Version = "2.0"
  Author = "bob@contoso.com"
  CompanyName = "Contoso"
  Description = "This is the updated description"
  }
Update-ScriptFileInfo @Parms -PassThru
```

```Output
<#PSScriptInfo

.VERSION 2.0

.GUID 4609f00c-e850-4d3f-9c69-3741e56e4133

.AUTHOR bob@contoso.com

.COMPANYNAME Contoso

.COPYRIGHT

.TAGS

.LICENSEURI

.PROJECTURI

.ICONURI

.EXTERNALMODULEDEPENDENCIES

.REQUIREDSCRIPTS

.EXTERNALSCRIPTDEPENDENCIES

.RELEASENOTES

.PRIVATEDATA

#>

<#

.DESCRIPTION
This is the updated description

#>
Param()
```

<span data-ttu-id="b8b19-116">`$Parms` сохраняет значения параметров для **пути**, **версии**, **автора**, **CompanyName** и **описания**.</span><span class="sxs-lookup"><span data-stu-id="b8b19-116">`$Parms` stores the parameter values for **Path**, **Version**, **Author**, **CompanyName**, and **Description**.</span></span> <span data-ttu-id="b8b19-117">`Update-ScriptFileInfo` Возвращает значения параметров из `@Parms` и обновляет скрипт.</span><span class="sxs-lookup"><span data-stu-id="b8b19-117">`Update-ScriptFileInfo` gets the parameter values from `@Parms` and updates the script.</span></span> <span data-ttu-id="b8b19-118">Параметр **PassThru** отображает содержимое скрипта в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b8b19-118">The **PassThru** parameter displays the script's contents in the PowerShell console.</span></span>

## <span data-ttu-id="b8b19-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b8b19-119">PARAMETERS</span></span>

### <span data-ttu-id="b8b19-120">-Author</span><span class="sxs-lookup"><span data-stu-id="b8b19-120">-Author</span></span>

<span data-ttu-id="b8b19-121">Указывает автора скрипта.</span><span class="sxs-lookup"><span data-stu-id="b8b19-121">Specifies the script author.</span></span>

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

### <span data-ttu-id="b8b19-122">-CompanyName</span><span class="sxs-lookup"><span data-stu-id="b8b19-122">-CompanyName</span></span>

<span data-ttu-id="b8b19-123">Указывает компанию или поставщика, создавшего скрипт.</span><span class="sxs-lookup"><span data-stu-id="b8b19-123">Specifies the company or vendor who created the script.</span></span>

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

### <span data-ttu-id="b8b19-124">-Confirm</span><span class="sxs-lookup"><span data-stu-id="b8b19-124">-Confirm</span></span>

<span data-ttu-id="b8b19-125">Запрашивает подтверждение перед запуском `Update-ScriptFileInfo` .</span><span class="sxs-lookup"><span data-stu-id="b8b19-125">Prompts you for confirmation before running `Update-ScriptFileInfo`.</span></span>

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

### <span data-ttu-id="b8b19-126">-Copyright</span><span class="sxs-lookup"><span data-stu-id="b8b19-126">-Copyright</span></span>

<span data-ttu-id="b8b19-127">Задает заявление об авторских правах для скрипта.</span><span class="sxs-lookup"><span data-stu-id="b8b19-127">Specifies a copyright statement for the script.</span></span>

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

### <span data-ttu-id="b8b19-128">-Description</span><span class="sxs-lookup"><span data-stu-id="b8b19-128">-Description</span></span>

<span data-ttu-id="b8b19-129">Задает описание скрипта.</span><span class="sxs-lookup"><span data-stu-id="b8b19-129">Specifies a description for the script.</span></span>

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

### <span data-ttu-id="b8b19-130">-ЕкстерналмодуледепенденЦиес</span><span class="sxs-lookup"><span data-stu-id="b8b19-130">-ExternalModuleDependencies</span></span>

<span data-ttu-id="b8b19-131">Указывает массив зависимостей внешних модулей.</span><span class="sxs-lookup"><span data-stu-id="b8b19-131">Specifies an array of external module dependencies.</span></span>

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

### <span data-ttu-id="b8b19-132">-ЕкстерналскриптдепенденЦиес</span><span class="sxs-lookup"><span data-stu-id="b8b19-132">-ExternalScriptDependencies</span></span>

<span data-ttu-id="b8b19-133">Указывает массив зависимостей внешних скриптов.</span><span class="sxs-lookup"><span data-stu-id="b8b19-133">Specifies an array of external script dependencies.</span></span>

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

### <span data-ttu-id="b8b19-134">-Force</span><span class="sxs-lookup"><span data-stu-id="b8b19-134">-Force</span></span>

<span data-ttu-id="b8b19-135">Принудительное `Update-ScriptFileInfo` выполнение без запроса подтверждения пользователя.</span><span class="sxs-lookup"><span data-stu-id="b8b19-135">Forces `Update-ScriptFileInfo` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="b8b19-136">-Guid</span><span class="sxs-lookup"><span data-stu-id="b8b19-136">-Guid</span></span>

<span data-ttu-id="b8b19-137">Задает уникальный идентификатор скрипта.</span><span class="sxs-lookup"><span data-stu-id="b8b19-137">Specifies a unique ID for a script.</span></span>

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

### <span data-ttu-id="b8b19-138">-IconUri</span><span class="sxs-lookup"><span data-stu-id="b8b19-138">-IconUri</span></span>

<span data-ttu-id="b8b19-139">Задает URL-адрес значка для скрипта.</span><span class="sxs-lookup"><span data-stu-id="b8b19-139">Specifies the URL of an icon for the script.</span></span> <span data-ttu-id="b8b19-140">Указанный значок отображается на веб-странице коллекции скрипта.</span><span class="sxs-lookup"><span data-stu-id="b8b19-140">The specified icon is displayed on the gallery web page for the script.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b8b19-141">-LicenseUri</span><span class="sxs-lookup"><span data-stu-id="b8b19-141">-LicenseUri</span></span>

<span data-ttu-id="b8b19-142">Указывает URL-адрес условий лицензирования.</span><span class="sxs-lookup"><span data-stu-id="b8b19-142">Specifies the URL of licensing terms.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b8b19-143">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="b8b19-143">-LiteralPath</span></span>

<span data-ttu-id="b8b19-144">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="b8b19-144">Specifies a path to one or more locations.</span></span> <span data-ttu-id="b8b19-145">Значение параметра **LiteralPath** используется точно так же, как оно указано.</span><span class="sxs-lookup"><span data-stu-id="b8b19-145">The **LiteralPath** parameter's value is used exactly as it's entered.</span></span> <span data-ttu-id="b8b19-146">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="b8b19-146">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="b8b19-147">Если путь содержит escape-символы, заключите их в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="b8b19-147">If the path includes escape characters, enclose them in single quotation marks.</span></span> <span data-ttu-id="b8b19-148">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="b8b19-148">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: LiteralPathParameterSet
Aliases: PSPath

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b8b19-149">-PassThru</span><span class="sxs-lookup"><span data-stu-id="b8b19-149">-PassThru</span></span>

<span data-ttu-id="b8b19-150">Возвращает объект, представляющий элемент, с которым выполняется работа.</span><span class="sxs-lookup"><span data-stu-id="b8b19-150">Returns an object that represents the item with which you're working.</span></span> <span data-ttu-id="b8b19-151">По умолчанию `Update-ScriptFileInfo` не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="b8b19-151">By default, `Update-ScriptFileInfo` doesn't generate any output.</span></span>

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

### <span data-ttu-id="b8b19-152">-Path</span><span class="sxs-lookup"><span data-stu-id="b8b19-152">-Path</span></span>

<span data-ttu-id="b8b19-153">Указывает расположение файла скрипта.</span><span class="sxs-lookup"><span data-stu-id="b8b19-153">Specifies the script file's location.</span></span> <span data-ttu-id="b8b19-154">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="b8b19-154">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="b8b19-155">-PrivateData</span><span class="sxs-lookup"><span data-stu-id="b8b19-155">-PrivateData</span></span>

<span data-ttu-id="b8b19-156">Задает закрытые данные для скрипта.</span><span class="sxs-lookup"><span data-stu-id="b8b19-156">Specifies the private data for the script.</span></span>

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

### <span data-ttu-id="b8b19-157">-ProjectUri</span><span class="sxs-lookup"><span data-stu-id="b8b19-157">-ProjectUri</span></span>

<span data-ttu-id="b8b19-158">Указывает URL веб-страницы об этом проекте.</span><span class="sxs-lookup"><span data-stu-id="b8b19-158">Specifies the URL of a web page about this project.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b8b19-159">-ReleaseNotes</span><span class="sxs-lookup"><span data-stu-id="b8b19-159">-ReleaseNotes</span></span>

<span data-ttu-id="b8b19-160">Указывает массив строк, содержащий заметки о выпуске или комментарии, которые должны быть доступны для данной версии скрипта.</span><span class="sxs-lookup"><span data-stu-id="b8b19-160">Specifies a string array that contains release notes or comments that you want available for this version of the script.</span></span>

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

### <span data-ttu-id="b8b19-161">-RequiredModules</span><span class="sxs-lookup"><span data-stu-id="b8b19-161">-RequiredModules</span></span>

<span data-ttu-id="b8b19-162">Определяет модули, которые должны присутствовать в глобальном состоянии сеанса.</span><span class="sxs-lookup"><span data-stu-id="b8b19-162">Specifies modules that must be in the global session state.</span></span> <span data-ttu-id="b8b19-163">Если требуемые модули не находятся в глобальном состоянии сеанса, PowerShell импортирует их.</span><span class="sxs-lookup"><span data-stu-id="b8b19-163">If the required modules aren't in the global session state, PowerShell imports them.</span></span>

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

### <span data-ttu-id="b8b19-164">-Рекуиредскриптс</span><span class="sxs-lookup"><span data-stu-id="b8b19-164">-RequiredScripts</span></span>

<span data-ttu-id="b8b19-165">Указывает массив обязательных скриптов.</span><span class="sxs-lookup"><span data-stu-id="b8b19-165">Specifies an array of required scripts.</span></span>

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

### <span data-ttu-id="b8b19-166">-Теги</span><span class="sxs-lookup"><span data-stu-id="b8b19-166">-Tags</span></span>

<span data-ttu-id="b8b19-167">Задает массив тегов.</span><span class="sxs-lookup"><span data-stu-id="b8b19-167">Specifies an array of tags.</span></span>

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

### <span data-ttu-id="b8b19-168">-Version</span><span class="sxs-lookup"><span data-stu-id="b8b19-168">-Version</span></span>

<span data-ttu-id="b8b19-169">Указывает версию скрипта.</span><span class="sxs-lookup"><span data-stu-id="b8b19-169">Specifies the script's version.</span></span>

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

### <span data-ttu-id="b8b19-170">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="b8b19-170">-WhatIf</span></span>

<span data-ttu-id="b8b19-171">Показывает, что произойдет при `Update-ScriptFileInfo` запуске.</span><span class="sxs-lookup"><span data-stu-id="b8b19-171">Shows what would happen if `Update-ScriptFileInfo` runs.</span></span> <span data-ttu-id="b8b19-172">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="b8b19-172">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="b8b19-173">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="b8b19-173">CommonParameters</span></span>

<span data-ttu-id="b8b19-174">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b8b19-174">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b8b19-175">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b8b19-175">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b8b19-176">Входные данные</span><span class="sxs-lookup"><span data-stu-id="b8b19-176">INPUTS</span></span>

### <span data-ttu-id="b8b19-177">System.String</span><span class="sxs-lookup"><span data-stu-id="b8b19-177">System.String</span></span>

## <span data-ttu-id="b8b19-178">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="b8b19-178">OUTPUTS</span></span>

### <span data-ttu-id="b8b19-179">System.Object</span><span class="sxs-lookup"><span data-stu-id="b8b19-179">System.Object</span></span>

## <span data-ttu-id="b8b19-180">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="b8b19-180">NOTES</span></span>

<span data-ttu-id="b8b19-181">Используйте `Test-ScriptFileInfo` командлет для проверки метаданных скрипта.</span><span class="sxs-lookup"><span data-stu-id="b8b19-181">Use the `Test-ScriptFileInfo` cmdlet to validate a script's metadata.</span></span> <span data-ttu-id="b8b19-182">Скрипты должны включать значения для версии, GUID, описания и автора.</span><span class="sxs-lookup"><span data-stu-id="b8b19-182">Scripts must include values for version, GUID, description, and author.</span></span>

## <span data-ttu-id="b8b19-183">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="b8b19-183">RELATED LINKS</span></span>

[<span data-ttu-id="b8b19-184">New-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="b8b19-184">New-ScriptFileInfo</span></span>](New-ScriptFileInfo.md)

[<span data-ttu-id="b8b19-185">Test-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="b8b19-185">Test-ScriptFileInfo</span></span>](Test-ScriptFileInfo.md)

