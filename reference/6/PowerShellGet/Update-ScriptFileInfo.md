---
external help file: PSModule-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/09/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/update-scriptfileinfo?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-ScriptFileInfo
ms.openlocfilehash: ff1d59cd3a956c6e6964bdfc64de6f52ef2e944b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228914"
---
# <span data-ttu-id="53f8e-103">Update-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="53f8e-103">Update-ScriptFileInfo</span></span>

## <span data-ttu-id="53f8e-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="53f8e-104">SYNOPSIS</span></span>
<span data-ttu-id="53f8e-105">Обновляет сведения для скрипта.</span><span class="sxs-lookup"><span data-stu-id="53f8e-105">Updates information for a script.</span></span>

## <span data-ttu-id="53f8e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="53f8e-106">SYNTAX</span></span>

### <span data-ttu-id="53f8e-107">Паспараметерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="53f8e-107">PathParameterSet (Default)</span></span>

```
Update-ScriptFileInfo [-Path] <String> [-Version <String>] [-Author <String>] [-Guid <Guid>]
 [-Description <String>] [-CompanyName <String>] [-Copyright <String>] [-RequiredModules <Object[]>]
 [-ExternalModuleDependencies <String[]>] [-RequiredScripts <String[]>]
 [-ExternalScriptDependencies <String[]>] [-Tags <String[]>] [-ProjectUri <Uri>] [-LicenseUri <Uri>]
 [-IconUri <Uri>] [-ReleaseNotes <String[]>] [-PrivateData <String>] [-PassThru] [-Force] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="53f8e-108">литералпаспараметерсет</span><span class="sxs-lookup"><span data-stu-id="53f8e-108">LiteralPathParameterSet</span></span>

```
Update-ScriptFileInfo [-LiteralPath] <String> [-Version <String>] [-Author <String>] [-Guid <Guid>]
 [-Description <String>] [-CompanyName <String>] [-Copyright <String>] [-RequiredModules <Object[]>]
 [-ExternalModuleDependencies <String[]>] [-RequiredScripts <String[]>]
 [-ExternalScriptDependencies <String[]>] [-Tags <String[]>] [-ProjectUri <Uri>] [-LicenseUri <Uri>]
 [-IconUri <Uri>] [-ReleaseNotes <String[]>] [-PrivateData <String>] [-PassThru] [-Force] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="53f8e-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="53f8e-109">DESCRIPTION</span></span>

<span data-ttu-id="53f8e-110">`Update-ScriptFileInfo`Командлет обновляет значения свойств скрипта.</span><span class="sxs-lookup"><span data-stu-id="53f8e-110">The `Update-ScriptFileInfo` cmdlet updates a script's property values.</span></span> <span data-ttu-id="53f8e-111">Например, значения для версии, автора или описания.</span><span class="sxs-lookup"><span data-stu-id="53f8e-111">For example, the values for version, author, or description.</span></span>

## <span data-ttu-id="53f8e-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="53f8e-112">EXAMPLES</span></span>

### <span data-ttu-id="53f8e-113">Пример 1. Обновление версии файла скрипта</span><span class="sxs-lookup"><span data-stu-id="53f8e-113">Example 1: Update the version of a script file</span></span>

<span data-ttu-id="53f8e-114">В этом примере существующий файл скрипта обновляется новыми значениями свойств.</span><span class="sxs-lookup"><span data-stu-id="53f8e-114">In this example, an existing script file is updated with new property values.</span></span>

<span data-ttu-id="53f8e-115">Сплаттинг используется для передачи параметров в `Update-ScriptFileInfo` командлет.</span><span class="sxs-lookup"><span data-stu-id="53f8e-115">Splatting is used to pass parameters to the `Update-ScriptFileInfo` cmdlet.</span></span> <span data-ttu-id="53f8e-116">Дополнительные сведения см. в разделе [about_Splatting](../Microsoft.Powershell.Core/About/about_splatting.md).</span><span class="sxs-lookup"><span data-stu-id="53f8e-116">For more information, see [about_Splatting](../Microsoft.Powershell.Core/About/about_splatting.md).</span></span>

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

<span data-ttu-id="53f8e-117">`$Parms` сохраняет значения параметров для **пути** , **версии** , **автора** , **CompanyName** и **описания** .</span><span class="sxs-lookup"><span data-stu-id="53f8e-117">`$Parms` stores the parameter values for **Path** , **Version** , **Author** , **CompanyName** , and **Description** .</span></span> <span data-ttu-id="53f8e-118">`Update-ScriptFileInfo` Возвращает значения параметров из `@Parms` и обновляет скрипт.</span><span class="sxs-lookup"><span data-stu-id="53f8e-118">`Update-ScriptFileInfo` gets the parameter values from `@Parms` and updates the script.</span></span> <span data-ttu-id="53f8e-119">Параметр **PassThru** отображает содержимое скрипта в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="53f8e-119">The **PassThru** parameter displays the script's contents in the PowerShell console.</span></span>

## <span data-ttu-id="53f8e-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="53f8e-120">PARAMETERS</span></span>

### <span data-ttu-id="53f8e-121">-Author</span><span class="sxs-lookup"><span data-stu-id="53f8e-121">-Author</span></span>

<span data-ttu-id="53f8e-122">Указывает автора скрипта.</span><span class="sxs-lookup"><span data-stu-id="53f8e-122">Specifies the script author.</span></span>

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

### <span data-ttu-id="53f8e-123">-CompanyName</span><span class="sxs-lookup"><span data-stu-id="53f8e-123">-CompanyName</span></span>

<span data-ttu-id="53f8e-124">Указывает компанию или поставщика, создавшего скрипт.</span><span class="sxs-lookup"><span data-stu-id="53f8e-124">Specifies the company or vendor who created the script.</span></span>

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

### <span data-ttu-id="53f8e-125">-Confirm</span><span class="sxs-lookup"><span data-stu-id="53f8e-125">-Confirm</span></span>

<span data-ttu-id="53f8e-126">Запрашивает подтверждение перед запуском `Update-ScriptFileInfo` .</span><span class="sxs-lookup"><span data-stu-id="53f8e-126">Prompts you for confirmation before running `Update-ScriptFileInfo`.</span></span>

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

### <span data-ttu-id="53f8e-127">-Copyright</span><span class="sxs-lookup"><span data-stu-id="53f8e-127">-Copyright</span></span>

<span data-ttu-id="53f8e-128">Задает заявление об авторских правах для скрипта.</span><span class="sxs-lookup"><span data-stu-id="53f8e-128">Specifies a copyright statement for the script.</span></span>

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

### <span data-ttu-id="53f8e-129">-Description</span><span class="sxs-lookup"><span data-stu-id="53f8e-129">-Description</span></span>

<span data-ttu-id="53f8e-130">Задает описание скрипта.</span><span class="sxs-lookup"><span data-stu-id="53f8e-130">Specifies a description for the script.</span></span>

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

### <span data-ttu-id="53f8e-131">-ЕкстерналмодуледепенденЦиес</span><span class="sxs-lookup"><span data-stu-id="53f8e-131">-ExternalModuleDependencies</span></span>

<span data-ttu-id="53f8e-132">Указывает массив зависимостей внешних модулей.</span><span class="sxs-lookup"><span data-stu-id="53f8e-132">Specifies an array of external module dependencies.</span></span>

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

### <span data-ttu-id="53f8e-133">-ЕкстерналскриптдепенденЦиес</span><span class="sxs-lookup"><span data-stu-id="53f8e-133">-ExternalScriptDependencies</span></span>

<span data-ttu-id="53f8e-134">Указывает массив зависимостей внешних скриптов.</span><span class="sxs-lookup"><span data-stu-id="53f8e-134">Specifies an array of external script dependencies.</span></span>

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

### <span data-ttu-id="53f8e-135">-Force</span><span class="sxs-lookup"><span data-stu-id="53f8e-135">-Force</span></span>

<span data-ttu-id="53f8e-136">Принудительное `Update-ScriptFileInfo` выполнение без запроса подтверждения пользователя.</span><span class="sxs-lookup"><span data-stu-id="53f8e-136">Forces `Update-ScriptFileInfo` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="53f8e-137">-Guid</span><span class="sxs-lookup"><span data-stu-id="53f8e-137">-Guid</span></span>

<span data-ttu-id="53f8e-138">Задает уникальный идентификатор скрипта.</span><span class="sxs-lookup"><span data-stu-id="53f8e-138">Specifies a unique ID for a script.</span></span>

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

### <span data-ttu-id="53f8e-139">-IconUri</span><span class="sxs-lookup"><span data-stu-id="53f8e-139">-IconUri</span></span>

<span data-ttu-id="53f8e-140">Задает URL-адрес значка для скрипта.</span><span class="sxs-lookup"><span data-stu-id="53f8e-140">Specifies the URL of an icon for the script.</span></span> <span data-ttu-id="53f8e-141">Указанный значок отображается на веб-странице коллекции скрипта.</span><span class="sxs-lookup"><span data-stu-id="53f8e-141">The specified icon is displayed on the gallery web page for the script.</span></span>

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

### <span data-ttu-id="53f8e-142">-LicenseUri</span><span class="sxs-lookup"><span data-stu-id="53f8e-142">-LicenseUri</span></span>

<span data-ttu-id="53f8e-143">Указывает URL-адрес условий лицензирования.</span><span class="sxs-lookup"><span data-stu-id="53f8e-143">Specifies the URL of licensing terms.</span></span>

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

### <span data-ttu-id="53f8e-144">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="53f8e-144">-LiteralPath</span></span>

<span data-ttu-id="53f8e-145">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="53f8e-145">Specifies a path to one or more locations.</span></span> <span data-ttu-id="53f8e-146">Значение параметра **LiteralPath** используется точно так же, как оно указано.</span><span class="sxs-lookup"><span data-stu-id="53f8e-146">The **LiteralPath** parameter's value is used exactly as it's entered.</span></span> <span data-ttu-id="53f8e-147">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="53f8e-147">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="53f8e-148">Если путь содержит escape-символы, заключите их в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="53f8e-148">If the path includes escape characters, enclose them in single quotation marks.</span></span> <span data-ttu-id="53f8e-149">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="53f8e-149">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="53f8e-150">-PassThru</span><span class="sxs-lookup"><span data-stu-id="53f8e-150">-PassThru</span></span>

<span data-ttu-id="53f8e-151">Возвращает объект, представляющий элемент, с которым выполняется работа.</span><span class="sxs-lookup"><span data-stu-id="53f8e-151">Returns an object that represents the item with which you're working.</span></span> <span data-ttu-id="53f8e-152">По умолчанию `Update-ScriptFileInfo` не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="53f8e-152">By default, `Update-ScriptFileInfo` doesn't generate any output.</span></span>

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

### <span data-ttu-id="53f8e-153">-Path</span><span class="sxs-lookup"><span data-stu-id="53f8e-153">-Path</span></span>

<span data-ttu-id="53f8e-154">Указывает расположение файла скрипта.</span><span class="sxs-lookup"><span data-stu-id="53f8e-154">Specifies the script file's location.</span></span> <span data-ttu-id="53f8e-155">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="53f8e-155">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="53f8e-156">-PrivateData</span><span class="sxs-lookup"><span data-stu-id="53f8e-156">-PrivateData</span></span>

<span data-ttu-id="53f8e-157">Задает закрытые данные для скрипта.</span><span class="sxs-lookup"><span data-stu-id="53f8e-157">Specifies the private data for the script.</span></span>

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

### <span data-ttu-id="53f8e-158">-ProjectUri</span><span class="sxs-lookup"><span data-stu-id="53f8e-158">-ProjectUri</span></span>

<span data-ttu-id="53f8e-159">Указывает URL веб-страницы об этом проекте.</span><span class="sxs-lookup"><span data-stu-id="53f8e-159">Specifies the URL of a web page about this project.</span></span>

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

### <span data-ttu-id="53f8e-160">-ReleaseNotes</span><span class="sxs-lookup"><span data-stu-id="53f8e-160">-ReleaseNotes</span></span>

<span data-ttu-id="53f8e-161">Указывает массив строк, содержащий заметки о выпуске или комментарии, которые должны быть доступны для данной версии скрипта.</span><span class="sxs-lookup"><span data-stu-id="53f8e-161">Specifies a string array that contains release notes or comments that you want available for this version of the script.</span></span>

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

### <span data-ttu-id="53f8e-162">-RequiredModules</span><span class="sxs-lookup"><span data-stu-id="53f8e-162">-RequiredModules</span></span>

<span data-ttu-id="53f8e-163">Определяет модули, которые должны присутствовать в глобальном состоянии сеанса.</span><span class="sxs-lookup"><span data-stu-id="53f8e-163">Specifies modules that must be in the global session state.</span></span> <span data-ttu-id="53f8e-164">Если требуемые модули не находятся в глобальном состоянии сеанса, PowerShell импортирует их.</span><span class="sxs-lookup"><span data-stu-id="53f8e-164">If the required modules aren't in the global session state, PowerShell imports them.</span></span>

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

### <span data-ttu-id="53f8e-165">-Рекуиредскриптс</span><span class="sxs-lookup"><span data-stu-id="53f8e-165">-RequiredScripts</span></span>

<span data-ttu-id="53f8e-166">Указывает массив обязательных скриптов.</span><span class="sxs-lookup"><span data-stu-id="53f8e-166">Specifies an array of required scripts.</span></span>

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

### <span data-ttu-id="53f8e-167">-Теги</span><span class="sxs-lookup"><span data-stu-id="53f8e-167">-Tags</span></span>

<span data-ttu-id="53f8e-168">Задает массив тегов.</span><span class="sxs-lookup"><span data-stu-id="53f8e-168">Specifies an array of tags.</span></span>

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

### <span data-ttu-id="53f8e-169">-Version</span><span class="sxs-lookup"><span data-stu-id="53f8e-169">-Version</span></span>

<span data-ttu-id="53f8e-170">Указывает версию скрипта.</span><span class="sxs-lookup"><span data-stu-id="53f8e-170">Specifies the script's version.</span></span>

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

### <span data-ttu-id="53f8e-171">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="53f8e-171">-WhatIf</span></span>

<span data-ttu-id="53f8e-172">Показывает, что произойдет при `Update-ScriptFileInfo` запуске.</span><span class="sxs-lookup"><span data-stu-id="53f8e-172">Shows what would happen if `Update-ScriptFileInfo` runs.</span></span> <span data-ttu-id="53f8e-173">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="53f8e-173">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="53f8e-174">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="53f8e-174">CommonParameters</span></span>

<span data-ttu-id="53f8e-175">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="53f8e-175">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="53f8e-176">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="53f8e-176">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="53f8e-177">Входные данные</span><span class="sxs-lookup"><span data-stu-id="53f8e-177">INPUTS</span></span>

### <span data-ttu-id="53f8e-178">System.String</span><span class="sxs-lookup"><span data-stu-id="53f8e-178">System.String</span></span>

## <span data-ttu-id="53f8e-179">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="53f8e-179">OUTPUTS</span></span>

### <span data-ttu-id="53f8e-180">System.Object</span><span class="sxs-lookup"><span data-stu-id="53f8e-180">System.Object</span></span>

## <span data-ttu-id="53f8e-181">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="53f8e-181">NOTES</span></span>

<span data-ttu-id="53f8e-182">Используйте `Test-ScriptFileInfo` командлет для проверки метаданных скрипта.</span><span class="sxs-lookup"><span data-stu-id="53f8e-182">Use the `Test-ScriptFileInfo` cmdlet to validate a script's metadata.</span></span> <span data-ttu-id="53f8e-183">Скрипты должны включать значения для версии, GUID, описания и автора.</span><span class="sxs-lookup"><span data-stu-id="53f8e-183">Scripts must include values for version, GUID, description, and author.</span></span>

## <span data-ttu-id="53f8e-184">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="53f8e-184">RELATED LINKS</span></span>

[<span data-ttu-id="53f8e-185">New-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="53f8e-185">New-ScriptFileInfo</span></span>](New-ScriptFileInfo.md)

[<span data-ttu-id="53f8e-186">Test-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="53f8e-186">Test-ScriptFileInfo</span></span>](Test-ScriptFileInfo.md)
