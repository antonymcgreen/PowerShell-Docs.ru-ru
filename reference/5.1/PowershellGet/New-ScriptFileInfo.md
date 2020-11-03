---
external help file: PSModule-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/01/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/new-scriptfileinfo?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-ScriptFileInfo
ms.openlocfilehash: 551fe34d266cb9330e4f30e823972458255c7f49
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228285"
---
# <span data-ttu-id="309bc-103">New-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="309bc-103">New-ScriptFileInfo</span></span>

## <span data-ttu-id="309bc-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="309bc-104">SYNOPSIS</span></span>
<span data-ttu-id="309bc-105">Создание файла сценария с метаданными.</span><span class="sxs-lookup"><span data-stu-id="309bc-105">Creates a script file with metadata.</span></span>

## <span data-ttu-id="309bc-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="309bc-106">SYNTAX</span></span>

### <span data-ttu-id="309bc-107">Все</span><span class="sxs-lookup"><span data-stu-id="309bc-107">All</span></span>

```
New-ScriptFileInfo [[-Path] <String>] [-Version <String>] [-Author <String>] -Description <String>
 [-Guid <Guid>] [-CompanyName <String>] [-Copyright <String>] [-RequiredModules <Object[]>]
 [-ExternalModuleDependencies <String[]>] [-RequiredScripts <String[]>]
 [-ExternalScriptDependencies <String[]>] [-Tags <String[]>] [-ProjectUri <Uri>] [-LicenseUri <Uri>]
 [-IconUri <Uri>] [-ReleaseNotes <String[]>] [-PrivateData <String>] [-PassThru] [-Force]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="309bc-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="309bc-108">DESCRIPTION</span></span>

<span data-ttu-id="309bc-109">`New-ScriptFileInfo`Командлет создает файл сценария PowerShell, включая метаданные о скрипте.</span><span class="sxs-lookup"><span data-stu-id="309bc-109">The `New-ScriptFileInfo` cmdlet creates a PowerShell script file, including metadata about the script.</span></span>

<span data-ttu-id="309bc-110">В примерах для передачи параметров в командлет используется Сплаттинг `New-ScriptFileInfo` .</span><span class="sxs-lookup"><span data-stu-id="309bc-110">The examples use splatting to pass parameters to the `New-ScriptFileInfo` cmdlet.</span></span> <span data-ttu-id="309bc-111">Дополнительные сведения см. в разделе [about_Splatting](../Microsoft.Powershell.Core/About/about_splatting.md).</span><span class="sxs-lookup"><span data-stu-id="309bc-111">For more information, see [about_Splatting](../Microsoft.Powershell.Core/About/about_splatting.md).</span></span>

## <span data-ttu-id="309bc-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="309bc-112">EXAMPLES</span></span>

### <span data-ttu-id="309bc-113">Пример 1. Создание файла скрипта и указание его версии, автора и описания</span><span class="sxs-lookup"><span data-stu-id="309bc-113">Example 1: Create a script file and specify its version, author, and description</span></span>

<span data-ttu-id="309bc-114">В этом примере создается файл скрипта, и его содержимое отображается в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="309bc-114">In this example, a script file is created and its contents are displayed in the PowerShell console.</span></span>

```powershell
$Parms = @{
  Path = "C:\Test\Temp-Scriptfile.ps1"
  Version = "1.0"
  Author = "pattif@contoso.com"
  Description = "My test script file description goes here"
  }
New-ScriptFileInfo @Parms
Get-Content -Path C:\Test\Temp-Scriptfile.ps1
```

```Output
<#PSScriptInfo

.VERSION 1.0

.GUID 3bb10ee7-38c1-41b9-88ea-16899164fc19

.AUTHOR pattif@contoso.com

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

.PRIVATEDATA

#>

<#

.DESCRIPTION
 My test script file description goes here

#>
Param()
```

<span data-ttu-id="309bc-115">`New-ScriptFileInfo`Командлет использует Сплаттинг для настройки нескольких параметров скрипта.</span><span class="sxs-lookup"><span data-stu-id="309bc-115">The `New-ScriptFileInfo` cmdlet uses splatting to configure several parameters for the script.</span></span>
<span data-ttu-id="309bc-116">**Path** задает расположение и имя скрипта.</span><span class="sxs-lookup"><span data-stu-id="309bc-116">**Path** sets the location and name of the script.</span></span> <span data-ttu-id="309bc-117">**Version** указывает номер версии скрипта.</span><span class="sxs-lookup"><span data-stu-id="309bc-117">**Version** specifies the script's version number.</span></span> <span data-ttu-id="309bc-118">**Автор** — это адрес электронной почты пользователя, создавшего скрипт.</span><span class="sxs-lookup"><span data-stu-id="309bc-118">**Author** is the email address of the person who created the script.</span></span> <span data-ttu-id="309bc-119">**Описание** описывает назначение сценария.</span><span class="sxs-lookup"><span data-stu-id="309bc-119">**Description** explains the script's purpose.</span></span>

<span data-ttu-id="309bc-120">После создания скрипта `Get-Content` использует параметр **path** для поиска скрипта.</span><span class="sxs-lookup"><span data-stu-id="309bc-120">After the script is created, `Get-Content` uses the **Path** parameter to locate the script.</span></span> <span data-ttu-id="309bc-121">Содержимое скрипта отображается в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="309bc-121">The script's contents are displayed in the PowerShell console.</span></span>

### <span data-ttu-id="309bc-122">Пример 2. Тестирование файла скрипта</span><span class="sxs-lookup"><span data-stu-id="309bc-122">Example 2: Test a script file</span></span>

<span data-ttu-id="309bc-123">В этом примере тестируется метаданные для скрипта, созданного в **примере 1** .</span><span class="sxs-lookup"><span data-stu-id="309bc-123">In this example, the metadata for the script created in **Example 1** is tested.</span></span>

```powershell
Test-ScriptFileInfo -Path C:\Test\Temp-Scriptfile.ps1
```

```Output
Version   Name                  Author               Description
-------   ----                  ------               -----------
1.0       Temp-Scriptfile       pattif@contoso.com   My test script file description goes here
```

<span data-ttu-id="309bc-124">`Test-ScriptFileInfo`Командлет использует параметр **path** , чтобы указать расположение файла скрипта.</span><span class="sxs-lookup"><span data-stu-id="309bc-124">The `Test-ScriptFileInfo` cmdlet uses the **Path** parameter to specify the script file's location.</span></span>

### <span data-ttu-id="309bc-125">Пример 3. Создание файла скрипта со всеми свойствами метаданных</span><span class="sxs-lookup"><span data-stu-id="309bc-125">Example 3: Create a script file with all the metadata properties</span></span>

<span data-ttu-id="309bc-126">В этом примере используется Сплаттинг для создания файла скрипта с именем `New-ScriptFile.ps1` , включающего все его свойства метаданных.</span><span class="sxs-lookup"><span data-stu-id="309bc-126">This example uses splatting to create a script file named `New-ScriptFile.ps1` that includes all its metadata properties.</span></span> <span data-ttu-id="309bc-127">Параметр **verbose** указывает, что подробный вывод отображается при создании скрипта.</span><span class="sxs-lookup"><span data-stu-id="309bc-127">The **Verbose** parameter specifies that verbose output is displayed as the script is created.</span></span>

```powershell
$Parms = @{
 Path = "C:\Test\New-ScriptFile.ps1"
 Verbose = $True
 Version = "1.0"
 Author = "pattif@contoso.com"
 Description = "My new script file test"
 CompanyName = "Contoso Corporation"
 Copyright = "2019 Contoso Corporation. All rights reserved."
 ExternalModuleDependencies = "ff","bb"
 RequiredScripts = "Start-WFContosoServer", "Stop-ContosoServerScript"
 ExternalScriptDependencies = "Stop-ContosoServerScript"
 Tags = @("Tag1", "Tag2", "Tag3")
 ProjectUri = "https://contoso.com"
 LicenseUri = "https://contoso.com/License"
 IconUri = "https://contoso.com/Icon"
 PassThru = $True
 ReleaseNotes = @("Contoso script now supports the following features:",
   "Feature 1",
   "Feature 2",
   "Feature 3",
   "Feature 4",
   "Feature 5")
 RequiredModules =
   "1",
   "2",
   "RequiredModule1",
   @{ModuleName="RequiredModule2";ModuleVersion="1.0"},
   @{ModuleName="RequiredModule3";RequiredVersion="2.0"},
   "ExternalModule1"
 }
New-ScriptFileInfo @Parms
```

```Output
VERBOSE: Performing the operation "Creating the 'C:\Test\New-ScriptFile.ps1'
  PowerShell Script file" on target "C:\Test\New-ScriptFile.ps1".

<#PSScriptInfo

.VERSION 1.0

.GUID 4fabe8c7-7862-45b1-a72e-1352a433b77d

.AUTHOR pattif@contoso.com

.COMPANYNAME Contoso Corporation

.COPYRIGHT 2019 Contoso Corporation. All rights reserved.

.TAGS Tag1 Tag2 Tag3

.LICENSEURI https://contoso.com/License

.PROJECTURI https://contoso.com/

.ICONURI https://contoso.com/Icon

.EXTERNALMODULEDEPENDENCIES ff,bb

.REQUIREDSCRIPTS Start-WFContosoServer,Stop-ContosoServerScript

.EXTERNALSCRIPTDEPENDENCIES Stop-ContosoServerScript

.RELEASENOTES
Contoso script now supports the following features:
Feature 1
Feature 2
Feature 3
Feature 4
Feature 5

.PRIVATEDATA

#>

#Requires -Module 1
#Requires -Module 2
#Requires -Module RequiredModule1
#Requires -Module @{ModuleName = 'RequiredModule2'; ModuleVersion = '1.0'}
#Requires -Module @{RequiredVersion = '2.0'; ModuleName = 'RequiredModule3'}
#Requires -Module ExternalModule1

<#

.DESCRIPTION
 My new script file test

#>
Param()
```

## <span data-ttu-id="309bc-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="309bc-128">PARAMETERS</span></span>

### <span data-ttu-id="309bc-129">-Author</span><span class="sxs-lookup"><span data-stu-id="309bc-129">-Author</span></span>

<span data-ttu-id="309bc-130">Указывает автора скрипта.</span><span class="sxs-lookup"><span data-stu-id="309bc-130">Specifies the script author.</span></span>

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

### <span data-ttu-id="309bc-131">-CompanyName</span><span class="sxs-lookup"><span data-stu-id="309bc-131">-CompanyName</span></span>

<span data-ttu-id="309bc-132">Указывает компанию или поставщика, создавшего скрипт.</span><span class="sxs-lookup"><span data-stu-id="309bc-132">Specifies the company or vendor who created the script.</span></span>

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

### <span data-ttu-id="309bc-133">-Confirm</span><span class="sxs-lookup"><span data-stu-id="309bc-133">-Confirm</span></span>

<span data-ttu-id="309bc-134">Запрашивает подтверждение перед запуском `New-ScriptFileInfo` .</span><span class="sxs-lookup"><span data-stu-id="309bc-134">Prompts you for confirmation before running the `New-ScriptFileInfo`.</span></span>

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

### <span data-ttu-id="309bc-135">-Copyright</span><span class="sxs-lookup"><span data-stu-id="309bc-135">-Copyright</span></span>

<span data-ttu-id="309bc-136">Задает заявление об авторских правах для скрипта.</span><span class="sxs-lookup"><span data-stu-id="309bc-136">Specifies a copyright statement for the script.</span></span>

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

### <span data-ttu-id="309bc-137">-Description</span><span class="sxs-lookup"><span data-stu-id="309bc-137">-Description</span></span>

<span data-ttu-id="309bc-138">Задает описание скрипта.</span><span class="sxs-lookup"><span data-stu-id="309bc-138">Specifies a description for the script.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="309bc-139">-ЕкстерналмодуледепенденЦиес</span><span class="sxs-lookup"><span data-stu-id="309bc-139">-ExternalModuleDependencies</span></span>

<span data-ttu-id="309bc-140">Указывает массив зависимостей внешних модулей.</span><span class="sxs-lookup"><span data-stu-id="309bc-140">Specifies an array of external module dependencies.</span></span>

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

### <span data-ttu-id="309bc-141">-ЕкстерналскриптдепенденЦиес</span><span class="sxs-lookup"><span data-stu-id="309bc-141">-ExternalScriptDependencies</span></span>

<span data-ttu-id="309bc-142">Указывает массив зависимостей внешних скриптов.</span><span class="sxs-lookup"><span data-stu-id="309bc-142">Specifies an array of external script dependencies.</span></span>

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

### <span data-ttu-id="309bc-143">-Force</span><span class="sxs-lookup"><span data-stu-id="309bc-143">-Force</span></span>

<span data-ttu-id="309bc-144">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="309bc-144">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="309bc-145">-Guid</span><span class="sxs-lookup"><span data-stu-id="309bc-145">-Guid</span></span>

<span data-ttu-id="309bc-146">Задает уникальный идентификатор скрипта.</span><span class="sxs-lookup"><span data-stu-id="309bc-146">Specifies a unique ID for the script.</span></span>

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

### <span data-ttu-id="309bc-147">-IconUri</span><span class="sxs-lookup"><span data-stu-id="309bc-147">-IconUri</span></span>

<span data-ttu-id="309bc-148">Задает URL-адрес значка для скрипта.</span><span class="sxs-lookup"><span data-stu-id="309bc-148">Specifies the URL of an icon for the script.</span></span> <span data-ttu-id="309bc-149">Указанный значок отображается на веб-странице коллекции скрипта.</span><span class="sxs-lookup"><span data-stu-id="309bc-149">The specified icon is displayed on the gallery web page for the script.</span></span>

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

### <span data-ttu-id="309bc-150">-LicenseUri</span><span class="sxs-lookup"><span data-stu-id="309bc-150">-LicenseUri</span></span>

<span data-ttu-id="309bc-151">Указывает URL-адрес условий лицензирования.</span><span class="sxs-lookup"><span data-stu-id="309bc-151">Specifies the URL of licensing terms.</span></span>

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

### <span data-ttu-id="309bc-152">-PassThru</span><span class="sxs-lookup"><span data-stu-id="309bc-152">-PassThru</span></span>

<span data-ttu-id="309bc-153">Возвращает объект, представляющий элемент, с которым выполняется работа.</span><span class="sxs-lookup"><span data-stu-id="309bc-153">Returns an object that represents the item with which you're working.</span></span> <span data-ttu-id="309bc-154">По умолчанию `New-ScriptFileInfo` не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="309bc-154">By default, `New-ScriptFileInfo` doesn't generate any output.</span></span>

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

### <span data-ttu-id="309bc-155">-Path</span><span class="sxs-lookup"><span data-stu-id="309bc-155">-Path</span></span>

<span data-ttu-id="309bc-156">Указывает расположение, в котором сохранен файл скрипта.</span><span class="sxs-lookup"><span data-stu-id="309bc-156">Specifies the location where the script file is saved.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="309bc-157">-PrivateData</span><span class="sxs-lookup"><span data-stu-id="309bc-157">-PrivateData</span></span>

<span data-ttu-id="309bc-158">Задает закрытые данные для скрипта.</span><span class="sxs-lookup"><span data-stu-id="309bc-158">Specifies private data for the script.</span></span>

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

### <span data-ttu-id="309bc-159">-ProjectUri</span><span class="sxs-lookup"><span data-stu-id="309bc-159">-ProjectUri</span></span>

<span data-ttu-id="309bc-160">Указывает URL веб-страницы об этом проекте.</span><span class="sxs-lookup"><span data-stu-id="309bc-160">Specifies the URL of a web page about this project.</span></span>

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

### <span data-ttu-id="309bc-161">-ReleaseNotes</span><span class="sxs-lookup"><span data-stu-id="309bc-161">-ReleaseNotes</span></span>

<span data-ttu-id="309bc-162">Указывает строковый массив, содержащий заметки о выпуске или комментарии, которые должны быть доступны пользователям данной версии скрипта.</span><span class="sxs-lookup"><span data-stu-id="309bc-162">Specifies a string array that contains release notes or comments that you want available to users of this version of the script.</span></span>

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

### <span data-ttu-id="309bc-163">-RequiredModules</span><span class="sxs-lookup"><span data-stu-id="309bc-163">-RequiredModules</span></span>

<span data-ttu-id="309bc-164">Определяет модули, которые должны присутствовать в глобальном состоянии сеанса.</span><span class="sxs-lookup"><span data-stu-id="309bc-164">Specifies modules that must be in the global session state.</span></span> <span data-ttu-id="309bc-165">Если требуемые модули не находятся в глобальном состоянии сеанса, PowerShell импортирует их.</span><span class="sxs-lookup"><span data-stu-id="309bc-165">If the required modules aren't in the global session state, PowerShell imports them.</span></span>

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

### <span data-ttu-id="309bc-166">-Рекуиредскриптс</span><span class="sxs-lookup"><span data-stu-id="309bc-166">-RequiredScripts</span></span>

<span data-ttu-id="309bc-167">Указывает массив обязательных скриптов.</span><span class="sxs-lookup"><span data-stu-id="309bc-167">Specifies an array of required scripts.</span></span>

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

### <span data-ttu-id="309bc-168">-Теги</span><span class="sxs-lookup"><span data-stu-id="309bc-168">-Tags</span></span>

<span data-ttu-id="309bc-169">Задает массив тегов.</span><span class="sxs-lookup"><span data-stu-id="309bc-169">Specifies an array of tags.</span></span>

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

### <span data-ttu-id="309bc-170">-Version</span><span class="sxs-lookup"><span data-stu-id="309bc-170">-Version</span></span>

<span data-ttu-id="309bc-171">Указывает версию скрипта.</span><span class="sxs-lookup"><span data-stu-id="309bc-171">Specifies the version of the script.</span></span>

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

### <span data-ttu-id="309bc-172">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="309bc-172">-WhatIf</span></span>

<span data-ttu-id="309bc-173">Показывает, что произойдет при `New-ScriptFileInfo` запуске.</span><span class="sxs-lookup"><span data-stu-id="309bc-173">Shows what would happen if `New-ScriptFileInfo` runs.</span></span> <span data-ttu-id="309bc-174">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="309bc-174">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="309bc-175">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="309bc-175">CommonParameters</span></span>

<span data-ttu-id="309bc-176">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="309bc-176">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="309bc-177">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="309bc-177">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="309bc-178">Входные данные</span><span class="sxs-lookup"><span data-stu-id="309bc-178">INPUTS</span></span>

## <span data-ttu-id="309bc-179">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="309bc-179">OUTPUTS</span></span>

## <span data-ttu-id="309bc-180">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="309bc-180">NOTES</span></span>

## <span data-ttu-id="309bc-181">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="309bc-181">RELATED LINKS</span></span>

[<span data-ttu-id="309bc-182">about_Splatting</span><span class="sxs-lookup"><span data-stu-id="309bc-182">about_Splatting</span></span>](../Microsoft.Powershell.Core/About/about_splatting.md)

[<span data-ttu-id="309bc-183">Test-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="309bc-183">Test-ScriptFileInfo</span></span>](Test-ScriptFileInfo.md)

[<span data-ttu-id="309bc-184">Update-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="309bc-184">Update-ScriptFileInfo</span></span>](Update-ScriptFileInfo.md)
