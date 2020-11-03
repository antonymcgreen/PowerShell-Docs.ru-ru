---
external help file: PSModule-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/08/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/update-modulemanifest?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-ModuleManifest
ms.openlocfilehash: 81c58a09cb6c4e6cedcc7abfa832af7bb694b0e1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229593"
---
# <span data-ttu-id="86d23-103">Update-ModuleManifest</span><span class="sxs-lookup"><span data-stu-id="86d23-103">Update-ModuleManifest</span></span>

## <span data-ttu-id="86d23-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="86d23-104">SYNOPSIS</span></span>
<span data-ttu-id="86d23-105">Обновляет файл манифеста модуля.</span><span class="sxs-lookup"><span data-stu-id="86d23-105">Updates a module manifest file.</span></span>

## <span data-ttu-id="86d23-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="86d23-106">SYNTAX</span></span>

### <span data-ttu-id="86d23-107">Все</span><span class="sxs-lookup"><span data-stu-id="86d23-107">All</span></span>

```
Update-ModuleManifest [-Path] <String> [-NestedModules <Object[]>] [-Guid <Guid>] [-Author <String>]
 [-CompanyName <String>] [-Copyright <String>] [-RootModule <String>] [-ModuleVersion <Version>]
 [-Description <String>] [-ProcessorArchitecture <ProcessorArchitecture>]
 [-CompatiblePSEditions <String[]>] [-PowerShellVersion <Version>] [-ClrVersion <Version>]
 [-DotNetFrameworkVersion <Version>] [-PowerShellHostName <String>]
 [-PowerShellHostVersion <Version>] [-RequiredModules <Object[]>] [-TypesToProcess <String[]>]
 [-FormatsToProcess <String[]>] [-ScriptsToProcess <String[]>] [-RequiredAssemblies <String[]>]
 [-FileList <String[]>] [-ModuleList <Object[]>] [-FunctionsToExport <String[]>]
 [-AliasesToExport <String[]>] [-VariablesToExport <String[]>] [-CmdletsToExport <String[]>]
 [-DscResourcesToExport <String[]>] [-PrivateData <Hashtable>] [-Tags <String[]>]
 [-ProjectUri <Uri>] [-LicenseUri <Uri>] [-IconUri <Uri>] [-ReleaseNotes <String[]>]
 [-Prerelease <String>] [-HelpInfoUri <Uri>] [-PassThru] [-DefaultCommandPrefix <String>]
 [-ExternalModuleDependencies <String[]>] [-PackageManagementProviders <String[]>]
 [-RequireLicenseAcceptance] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="86d23-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="86d23-108">DESCRIPTION</span></span>

<span data-ttu-id="86d23-109">`Update-ModuleManifest`Командлет обновляет файл манифеста модуля ( `.psd1` ).</span><span class="sxs-lookup"><span data-stu-id="86d23-109">The `Update-ModuleManifest` cmdlet updates a module manifest (`.psd1`) file.</span></span>

## <span data-ttu-id="86d23-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="86d23-110">EXAMPLES</span></span>

### <span data-ttu-id="86d23-111">Пример 1. Обновление манифеста модуля</span><span class="sxs-lookup"><span data-stu-id="86d23-111">Example 1: Update a module manifest</span></span>

<span data-ttu-id="86d23-112">В этом примере обновляется существующий файл манифеста модуля.</span><span class="sxs-lookup"><span data-stu-id="86d23-112">This example updates an existing module manifest file.</span></span> <span data-ttu-id="86d23-113">Сплаттинг используется для передачи значений параметров в `Update-ModuleManifest` .</span><span class="sxs-lookup"><span data-stu-id="86d23-113">Splatting is used to pass parameter values to `Update-ModuleManifest`.</span></span> <span data-ttu-id="86d23-114">Дополнительные сведения см. в разделе [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span><span class="sxs-lookup"><span data-stu-id="86d23-114">For more information, see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span></span>

```powershell
$Parms = @{
  Path = "C:\Test\TestManifest.psd1"
  Author = "TestUser1"
  CompanyName = "Contoso Corporation"
  Copyright = "(c) 2019 Contoso Corporation. All rights reserved."
}

Update-ModuleManifest @Parms
```

<span data-ttu-id="86d23-115">`$Parms` — Это со звездочкой, в котором хранятся значения параметров для **пути** , **автора** , **CompanyName** и **авторских прав** .</span><span class="sxs-lookup"><span data-stu-id="86d23-115">`$Parms` is a splat that stores the parameter values for **Path** , **Author** , **CompanyName** , and **Copyright** .</span></span> <span data-ttu-id="86d23-116">`Update-ModuleManifest` Возвращает значения параметров из `@Parms` и обновляет манифест модуля **TestManifest.psd1** .</span><span class="sxs-lookup"><span data-stu-id="86d23-116">`Update-ModuleManifest` gets the parameter values from `@Parms` and updates the module manifest, **TestManifest.psd1** .</span></span>

## <span data-ttu-id="86d23-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="86d23-117">PARAMETERS</span></span>

### <span data-ttu-id="86d23-118">-Алиасестоекспорт</span><span class="sxs-lookup"><span data-stu-id="86d23-118">-AliasesToExport</span></span>

<span data-ttu-id="86d23-119">Задает экспортируемые модулем псевдонимы.</span><span class="sxs-lookup"><span data-stu-id="86d23-119">Specifies the aliases that the module exports.</span></span> <span data-ttu-id="86d23-120">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="86d23-120">Wildcards are permitted.</span></span>

<span data-ttu-id="86d23-121">Используйте этот параметр, чтобы ограничить псевдонимы, экспортируемые модулем.</span><span class="sxs-lookup"><span data-stu-id="86d23-121">Use this parameter to restrict the aliases that are exported by the module.</span></span> <span data-ttu-id="86d23-122">**Алиасестоекспорт** может удалять псевдонимы из списка экспортируемых псевдонимов, но не может добавлять в список псевдонимы.</span><span class="sxs-lookup"><span data-stu-id="86d23-122">**AliasesToExport** can remove aliases from the list of exported aliases, but it can't add aliases to the list.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="86d23-123">-Author</span><span class="sxs-lookup"><span data-stu-id="86d23-123">-Author</span></span>

<span data-ttu-id="86d23-124">Задает автора модуля.</span><span class="sxs-lookup"><span data-stu-id="86d23-124">Specifies the module author.</span></span>

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

### <span data-ttu-id="86d23-125">-ClrVersion</span><span class="sxs-lookup"><span data-stu-id="86d23-125">-ClrVersion</span></span>

<span data-ttu-id="86d23-126">Задает минимальную версию среды CLR платформы Microsoft .NET Framework, которая требуется для работы модуля.</span><span class="sxs-lookup"><span data-stu-id="86d23-126">Specifies the minimum version of the Common Language Runtime (CLR) of the Microsoft .NET Framework that the module requires.</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="86d23-127">-CmdletsToExport</span><span class="sxs-lookup"><span data-stu-id="86d23-127">-CmdletsToExport</span></span>

<span data-ttu-id="86d23-128">Задает экспортируемые модулем командлеты.</span><span class="sxs-lookup"><span data-stu-id="86d23-128">Specifies the cmdlets that the module exports.</span></span> <span data-ttu-id="86d23-129">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="86d23-129">Wildcards are permitted.</span></span>

<span data-ttu-id="86d23-130">Используйте этот параметр, чтобы ограничить командлеты, экспортируемые модулем.</span><span class="sxs-lookup"><span data-stu-id="86d23-130">Use this parameter to restrict the cmdlets that are exported by the module.</span></span> <span data-ttu-id="86d23-131">**CmdletsToExport** может удалять командлеты из списка экспортированных командлетов, но не может добавлять командлеты в список.</span><span class="sxs-lookup"><span data-stu-id="86d23-131">**CmdletsToExport** can remove cmdlets from the list of exported cmdlets, but it can't add cmdlets to the list.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="86d23-132">-CompanyName</span><span class="sxs-lookup"><span data-stu-id="86d23-132">-CompanyName</span></span>

<span data-ttu-id="86d23-133">Указывает компанию или поставщика, создавшего модуль.</span><span class="sxs-lookup"><span data-stu-id="86d23-133">Specifies the company or vendor who created the module.</span></span>

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

### <span data-ttu-id="86d23-134">-CompatiblePSEditions</span><span class="sxs-lookup"><span data-stu-id="86d23-134">-CompatiblePSEditions</span></span>

<span data-ttu-id="86d23-135">Указывает совместимый **PSEditions** модуля.</span><span class="sxs-lookup"><span data-stu-id="86d23-135">Specifies the compatible **PSEditions** of the module.</span></span> <span data-ttu-id="86d23-136">Сведения о **PSEdition** см. [в разделе модули с совместимыми выпусками PowerShell](/powershell/scripting/gallery/concepts/module-psedition-support).</span><span class="sxs-lookup"><span data-stu-id="86d23-136">For information about **PSEdition** , see [Modules with compatible PowerShell Editions](/powershell/scripting/gallery/concepts/module-psedition-support).</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:
Accepted values: Desktop, Core

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="86d23-137">-Confirm</span><span class="sxs-lookup"><span data-stu-id="86d23-137">-Confirm</span></span>

<span data-ttu-id="86d23-138">Запрашивает подтверждение перед запуском `Update-ModuleManifest` .</span><span class="sxs-lookup"><span data-stu-id="86d23-138">Prompts you for confirmation before running `Update-ModuleManifest`.</span></span>

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

### <span data-ttu-id="86d23-139">-Copyright</span><span class="sxs-lookup"><span data-stu-id="86d23-139">-Copyright</span></span>

<span data-ttu-id="86d23-140">Задает заявление об авторских правах на модуль.</span><span class="sxs-lookup"><span data-stu-id="86d23-140">Specifies a copyright statement for the module.</span></span>

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

### <span data-ttu-id="86d23-141">-DefaultCommandPrefix</span><span class="sxs-lookup"><span data-stu-id="86d23-141">-DefaultCommandPrefix</span></span>

<span data-ttu-id="86d23-142">Указывает префикс команды по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="86d23-142">Specifies the default command prefix.</span></span>

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

### <span data-ttu-id="86d23-143">-Description</span><span class="sxs-lookup"><span data-stu-id="86d23-143">-Description</span></span>

<span data-ttu-id="86d23-144">Задает описание модуля.</span><span class="sxs-lookup"><span data-stu-id="86d23-144">Specifies a description of the module.</span></span>

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

### <span data-ttu-id="86d23-145">-Дотнетфрамеворкверсион</span><span class="sxs-lookup"><span data-stu-id="86d23-145">-DotNetFrameworkVersion</span></span>

<span data-ttu-id="86d23-146">Указывает минимальную версию платформу Microsoft .NET, которая требуется для работы модуля.</span><span class="sxs-lookup"><span data-stu-id="86d23-146">Specifies the minimum version of the Microsoft .NET Framework that the module requires.</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="86d23-147">-DscResourcesToExport</span><span class="sxs-lookup"><span data-stu-id="86d23-147">-DscResourcesToExport</span></span>

<span data-ttu-id="86d23-148">Указывает ресурсы настройки требуемого состояния (DSC), которые экспортирует модуль.</span><span class="sxs-lookup"><span data-stu-id="86d23-148">Specifies the Desired State Configuration (DSC) resources that the module exports.</span></span> <span data-ttu-id="86d23-149">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="86d23-149">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="86d23-150">-ЕкстерналмодуледепенденЦиес</span><span class="sxs-lookup"><span data-stu-id="86d23-150">-ExternalModuleDependencies</span></span>

<span data-ttu-id="86d23-151">Указывает массив зависимостей внешних модулей.</span><span class="sxs-lookup"><span data-stu-id="86d23-151">Specifies an array of external module dependencies.</span></span>

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

### <span data-ttu-id="86d23-152">-FileList</span><span class="sxs-lookup"><span data-stu-id="86d23-152">-FileList</span></span>

<span data-ttu-id="86d23-153">Задает все элементы, включенные в модуль.</span><span class="sxs-lookup"><span data-stu-id="86d23-153">Specifies all items that are included in the module.</span></span>

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

### <span data-ttu-id="86d23-154">-FormatsToProcess</span><span class="sxs-lookup"><span data-stu-id="86d23-154">-FormatsToProcess</span></span>

<span data-ttu-id="86d23-155">Задает файлы форматирования ( `.ps1xml` ), которые выполняются при импорте модуля.</span><span class="sxs-lookup"><span data-stu-id="86d23-155">Specifies the formatting files (`.ps1xml`) that run when the module is imported.</span></span>

<span data-ttu-id="86d23-156">При импорте модуля PowerShell запускает `Update-FormatData` командлет с указанными файлами.</span><span class="sxs-lookup"><span data-stu-id="86d23-156">When you import a module, PowerShell runs the `Update-FormatData` cmdlet with the specified files.</span></span>
<span data-ttu-id="86d23-157">Так как файлы форматирования не находятся в области, они влияют на все состояния сеанса в сеансе.</span><span class="sxs-lookup"><span data-stu-id="86d23-157">Because formatting files aren't scoped, they affect all session states in the session.</span></span>

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

### <span data-ttu-id="86d23-158">-FunctionsToExport</span><span class="sxs-lookup"><span data-stu-id="86d23-158">-FunctionsToExport</span></span>

<span data-ttu-id="86d23-159">Задает экспортируемые модулем функции.</span><span class="sxs-lookup"><span data-stu-id="86d23-159">Specifies the functions that the module exports.</span></span> <span data-ttu-id="86d23-160">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="86d23-160">Wildcards are permitted.</span></span>

<span data-ttu-id="86d23-161">Используйте этот параметр, чтобы ограничить функции, экспортируемые модулем.</span><span class="sxs-lookup"><span data-stu-id="86d23-161">Use this parameter to restrict the functions that are exported by the module.</span></span> <span data-ttu-id="86d23-162">**FunctionsToExport** может удалять функции из списка экспортируемых псевдонимов, но не может добавлять функции в список.</span><span class="sxs-lookup"><span data-stu-id="86d23-162">**FunctionsToExport** can remove functions from the list of exported aliases, but it can't add functions to the list.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="86d23-163">-Guid</span><span class="sxs-lookup"><span data-stu-id="86d23-163">-Guid</span></span>

<span data-ttu-id="86d23-164">Задает уникальный идентификатор модуля.</span><span class="sxs-lookup"><span data-stu-id="86d23-164">Specifies a unique identifier for the module.</span></span> <span data-ttu-id="86d23-165">GUID позволяет отличать модули с одинаковыми именами.</span><span class="sxs-lookup"><span data-stu-id="86d23-165">The GUID can be used to distinguish among modules with the same name.</span></span>

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

### <span data-ttu-id="86d23-166">-HelpInfoUri</span><span class="sxs-lookup"><span data-stu-id="86d23-166">-HelpInfoUri</span></span>

<span data-ttu-id="86d23-167">Указывает адрес **XML-** файла модуля HelpInfo в Интернете.</span><span class="sxs-lookup"><span data-stu-id="86d23-167">Specifies the internet address of the module's **HelpInfo XML** file.</span></span> <span data-ttu-id="86d23-168">Введите универсальный код ресурса (URI), который начинается с **http** или **HTTPS** .</span><span class="sxs-lookup"><span data-stu-id="86d23-168">Enter a Uniform Resource Identifier (URI) that begins with **http** or **https** .</span></span>

<span data-ttu-id="86d23-169">**XML-файл HelpInfo** поддерживает функцию обновляемой справки, которая появилась в PowerShell версии 3,0.</span><span class="sxs-lookup"><span data-stu-id="86d23-169">The **HelpInfo XML** file supports the Updatable Help feature that was introduced in PowerShell version 3.0.</span></span> <span data-ttu-id="86d23-170">Он содержит сведения о расположении загружаемых файлов справки модуля и номера версий самых новых файлов справки для каждого поддерживаемого языкового стандарта.</span><span class="sxs-lookup"><span data-stu-id="86d23-170">It contains information about the location of the module's downloadable help files and the version numbers of the newest help files for each supported locale.</span></span>

<span data-ttu-id="86d23-171">Сведения об обновляемой справке см. в разделе [about_Updatable_Help](../Microsoft.PowerShell.Core/About/about_Updatable_Help.md).</span><span class="sxs-lookup"><span data-stu-id="86d23-171">For information about Updatable Help, see [about_Updatable_Help](../Microsoft.PowerShell.Core/About/about_Updatable_Help.md).</span></span>
<span data-ttu-id="86d23-172">Сведения о **XML-файле HelpInfo** см. в разделе [Поддержка обновляемой справки](/powershell/scripting/developer/module/supporting-updatable-help).</span><span class="sxs-lookup"><span data-stu-id="86d23-172">For information about the **HelpInfo XML** file, see [Supporting Updatable Help](/powershell/scripting/developer/module/supporting-updatable-help).</span></span>

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

### <span data-ttu-id="86d23-173">-IconUri</span><span class="sxs-lookup"><span data-stu-id="86d23-173">-IconUri</span></span>

<span data-ttu-id="86d23-174">Задает URL-адрес значка для модуля.</span><span class="sxs-lookup"><span data-stu-id="86d23-174">Specifies the URL of an icon for the module.</span></span> <span data-ttu-id="86d23-175">Указанный значок отображается на веб-странице коллекции модуля.</span><span class="sxs-lookup"><span data-stu-id="86d23-175">The specified icon is displayed on the gallery web page for the module.</span></span>

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

### <span data-ttu-id="86d23-176">-LicenseUri</span><span class="sxs-lookup"><span data-stu-id="86d23-176">-LicenseUri</span></span>

<span data-ttu-id="86d23-177">Указывает URL-адрес условий лицензирования для модуля.</span><span class="sxs-lookup"><span data-stu-id="86d23-177">Specifies the URL of licensing terms for the module.</span></span>

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

### <span data-ttu-id="86d23-178">-Модулелист</span><span class="sxs-lookup"><span data-stu-id="86d23-178">-ModuleList</span></span>

<span data-ttu-id="86d23-179">Указывает массив модулей, которые включены в модуль.</span><span class="sxs-lookup"><span data-stu-id="86d23-179">Specifies an array of modules that are included in the module.</span></span>

<span data-ttu-id="86d23-180">Введите имя каждого модуля в виде строки или хэш-таблицы с ключами **ModuleName** и **ModuleVersion** .</span><span class="sxs-lookup"><span data-stu-id="86d23-180">Enter each module name as a string or as a hash table with **ModuleName** and **ModuleVersion** keys.</span></span> <span data-ttu-id="86d23-181">Хэш-таблица может иметь дополнительный ключ **GUID** .</span><span class="sxs-lookup"><span data-stu-id="86d23-181">The hash table can also have an optional **GUID** key.</span></span> <span data-ttu-id="86d23-182">В значении параметра строки и хэш-таблицы можно объединять.</span><span class="sxs-lookup"><span data-stu-id="86d23-182">You can combine strings and hash tables in the parameter value.</span></span>

<span data-ttu-id="86d23-183">Этот ключ выполняет функцию полного списка ресурсов модуля.</span><span class="sxs-lookup"><span data-stu-id="86d23-183">This key is designed to act as a module inventory.</span></span> <span data-ttu-id="86d23-184">Модули, указанные в значении этого ключа, не обрабатываются автоматически.</span><span class="sxs-lookup"><span data-stu-id="86d23-184">The modules that are listed in the value of this key aren't automatically processed.</span></span>

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

### <span data-ttu-id="86d23-185">-Истечение</span><span class="sxs-lookup"><span data-stu-id="86d23-185">-ModuleVersion</span></span>

<span data-ttu-id="86d23-186">Указывает версию модуля.</span><span class="sxs-lookup"><span data-stu-id="86d23-186">Specifies the version of the module.</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="86d23-187">-NestedModules</span><span class="sxs-lookup"><span data-stu-id="86d23-187">-NestedModules</span></span>

<span data-ttu-id="86d23-188">Задает модули скрипта ( `.psm1` ) и двоичные модули ( `.dll` ), которые импортируются в состояние сеанса модуля.</span><span class="sxs-lookup"><span data-stu-id="86d23-188">Specifies script modules (`.psm1`) and binary modules (`.dll`) that are imported into the module's session state.</span></span> <span data-ttu-id="86d23-189">Файлы в ключе **NestedModules** выполняются в том порядке, в котором они указаны в значении.</span><span class="sxs-lookup"><span data-stu-id="86d23-189">The files in the **NestedModules** key run in the order in which they're listed in the value.</span></span>

<span data-ttu-id="86d23-190">Введите имя каждого модуля в виде строки или хэш-таблицы с ключами **ModuleName** и **ModuleVersion** .</span><span class="sxs-lookup"><span data-stu-id="86d23-190">Enter each module name as a string or as a hash table with **ModuleName** and **ModuleVersion** keys.</span></span> <span data-ttu-id="86d23-191">Хэш-таблица может иметь дополнительный ключ **GUID** .</span><span class="sxs-lookup"><span data-stu-id="86d23-191">The hash table can also have an optional **GUID** key.</span></span> <span data-ttu-id="86d23-192">В значении параметра строки и хэш-таблицы можно объединять.</span><span class="sxs-lookup"><span data-stu-id="86d23-192">You can combine strings and hash tables in the parameter value.</span></span>

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

### <span data-ttu-id="86d23-193">-Паккажеманажементпровидерс</span><span class="sxs-lookup"><span data-stu-id="86d23-193">-PackageManagementProviders</span></span>

<span data-ttu-id="86d23-194">Указывает массив поставщиков управления пакетами.</span><span class="sxs-lookup"><span data-stu-id="86d23-194">Specifies an array of package management providers.</span></span>

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

### <span data-ttu-id="86d23-195">-PassThru</span><span class="sxs-lookup"><span data-stu-id="86d23-195">-PassThru</span></span>

<span data-ttu-id="86d23-196">Возвращает объект, представляющий элемент, с которым выполняется работа.</span><span class="sxs-lookup"><span data-stu-id="86d23-196">Returns an object representing the item with which you're working.</span></span> <span data-ttu-id="86d23-197">По умолчанию `Update-ModuleManifest` не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="86d23-197">By default, `Update-ModuleManifest` doesn't generate any output.</span></span>

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

### <span data-ttu-id="86d23-198">-Path</span><span class="sxs-lookup"><span data-stu-id="86d23-198">-Path</span></span>

<span data-ttu-id="86d23-199">Указывает путь и имя файла манифеста модуля.</span><span class="sxs-lookup"><span data-stu-id="86d23-199">Specifies the path and file name of the module manifest.</span></span> <span data-ttu-id="86d23-200">Введите путь и имя файла с `.psd1` расширением имени файла, например `$PSHOME\Modules\MyModule\MyModule.psd1` .</span><span class="sxs-lookup"><span data-stu-id="86d23-200">Enter a path and file name with a `.psd1` file name extension, such as `$PSHOME\Modules\MyModule\MyModule.psd1`.</span></span>

<span data-ttu-id="86d23-201">При указании пути к существующему файлу `Update-ModuleManifest` заменяет файл без предупреждения, если только файл не имеет атрибута только для чтения.</span><span class="sxs-lookup"><span data-stu-id="86d23-201">If you specify the path to an existing file, `Update-ModuleManifest` replaces the file without warning unless the file has the read-only attribute.</span></span>

<span data-ttu-id="86d23-202">Манифест должен находиться в каталоге модуля, а имя файла манифеста должно совпадать с именем каталога модуля, но с `.psd1` расширением.</span><span class="sxs-lookup"><span data-stu-id="86d23-202">The manifest should be located in the module's directory, and the manifest file name should be the same as the module directory name, but with a `.psd1` extension.</span></span>

<span data-ttu-id="86d23-203">`$PSHOME` `$HOME` В ответ на запрос значения параметра **path** нельзя использовать переменные, например или.</span><span class="sxs-lookup"><span data-stu-id="86d23-203">You can't use variables, such as `$PSHOME` or `$HOME`, in response to a prompt for a **Path** parameter value.</span></span> <span data-ttu-id="86d23-204">Чтобы использовать переменную, включите параметр **Path** в команду.</span><span class="sxs-lookup"><span data-stu-id="86d23-204">To use a variable, include the **Path** parameter in the command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="86d23-205">-Повершеллхостнаме</span><span class="sxs-lookup"><span data-stu-id="86d23-205">-PowerShellHostName</span></span>

<span data-ttu-id="86d23-206">Указывает имя основной программы PowerShell, требуемой для модуля.</span><span class="sxs-lookup"><span data-stu-id="86d23-206">Specifies the name of the PowerShell host program that the module requires.</span></span> <span data-ttu-id="86d23-207">Введите имя основной программы, например, узел интегрированной среды сценариев PowerShell или ConsoleHost.</span><span class="sxs-lookup"><span data-stu-id="86d23-207">Enter the name of the host program, such as PowerShell ISE Host or ConsoleHost.</span></span> <span data-ttu-id="86d23-208">Подстановочные знаки не допускаются.</span><span class="sxs-lookup"><span data-stu-id="86d23-208">Wildcards aren't permitted.</span></span>

<span data-ttu-id="86d23-209">Чтобы найти имя основной программы, в программе введите `$Host.Name` .</span><span class="sxs-lookup"><span data-stu-id="86d23-209">To find the name of a host program, in the program, type `$Host.Name`.</span></span>

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

### <span data-ttu-id="86d23-210">-Повершеллхостверсион</span><span class="sxs-lookup"><span data-stu-id="86d23-210">-PowerShellHostVersion</span></span>

<span data-ttu-id="86d23-211">Указывает минимальную версию основной программы PowerShell, которая работает с модулем.</span><span class="sxs-lookup"><span data-stu-id="86d23-211">Specifies the minimum version of the PowerShell host program that works with the module.</span></span> <span data-ttu-id="86d23-212">Введите номер версии, например, 1.1.</span><span class="sxs-lookup"><span data-stu-id="86d23-212">Enter a version number, such as 1.1.</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="86d23-213">-PowerShellVersion</span><span class="sxs-lookup"><span data-stu-id="86d23-213">-PowerShellVersion</span></span>

<span data-ttu-id="86d23-214">Указывает минимальную версию PowerShell, которая будет работать с этим модулем.</span><span class="sxs-lookup"><span data-stu-id="86d23-214">Specifies the minimum version of PowerShell that will work with this module.</span></span> <span data-ttu-id="86d23-215">Например, в качестве значения этого параметра можно указать 3,0, 4,0 или 5,0.</span><span class="sxs-lookup"><span data-stu-id="86d23-215">For example, you can specify 3.0, 4.0, or 5.0 as the value of this parameter.</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="86d23-216">— Предварительный выпуск</span><span class="sxs-lookup"><span data-stu-id="86d23-216">-Prerelease</span></span>

<span data-ttu-id="86d23-217">Указывает, что модуль является предварительным выпуском.</span><span class="sxs-lookup"><span data-stu-id="86d23-217">Indicates the module is prerelease.</span></span>

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

### <span data-ttu-id="86d23-218">-PrivateData</span><span class="sxs-lookup"><span data-stu-id="86d23-218">-PrivateData</span></span>

<span data-ttu-id="86d23-219">Указывает данные, которые передаются в модуль при его импорте.</span><span class="sxs-lookup"><span data-stu-id="86d23-219">Specifies data that is passed to the module when it's imported.</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="86d23-220">-ProcessorArchitecture</span><span class="sxs-lookup"><span data-stu-id="86d23-220">-ProcessorArchitecture</span></span>

<span data-ttu-id="86d23-221">Указывает архитектуру процессора, необходимую для этого модуля.</span><span class="sxs-lookup"><span data-stu-id="86d23-221">Specifies the processor architecture that the module requires.</span></span>

<span data-ttu-id="86d23-222">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="86d23-222">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="86d23-223">AMD64</span><span class="sxs-lookup"><span data-stu-id="86d23-223">Amd64</span></span>
- <span data-ttu-id="86d23-224">Arm</span><span class="sxs-lookup"><span data-stu-id="86d23-224">Arm</span></span>
- <span data-ttu-id="86d23-225">IA64</span><span class="sxs-lookup"><span data-stu-id="86d23-225">IA64</span></span>
- <span data-ttu-id="86d23-226">MSIL</span><span class="sxs-lookup"><span data-stu-id="86d23-226">MSIL</span></span>
- <span data-ttu-id="86d23-227">Нет (неизвестно или не указано)</span><span class="sxs-lookup"><span data-stu-id="86d23-227">None (unknown or unspecified)</span></span>
- <span data-ttu-id="86d23-228">X86</span><span class="sxs-lookup"><span data-stu-id="86d23-228">X86</span></span>

```yaml
Type: System.Reflection.ProcessorArchitecture
Parameter Sets: (All)
Aliases:
Accepted values: None, MSIL, X86, IA64, Amd64, Arm

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="86d23-229">-ProjectUri</span><span class="sxs-lookup"><span data-stu-id="86d23-229">-ProjectUri</span></span>

<span data-ttu-id="86d23-230">Указывает URL веб-страницы об этом проекте.</span><span class="sxs-lookup"><span data-stu-id="86d23-230">Specifies the URL of a web page about this project.</span></span>

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

### <span data-ttu-id="86d23-231">-ReleaseNotes</span><span class="sxs-lookup"><span data-stu-id="86d23-231">-ReleaseNotes</span></span>

<span data-ttu-id="86d23-232">Указывает массив строк, содержащий заметки о выпуске или комментарии, которые должны быть доступны для данной версии скрипта.</span><span class="sxs-lookup"><span data-stu-id="86d23-232">Specifies a string array that contains release notes or comments that you want available for this version of the script.</span></span>

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

### <span data-ttu-id="86d23-233">-Рекуиредассемблиес</span><span class="sxs-lookup"><span data-stu-id="86d23-233">-RequiredAssemblies</span></span>

<span data-ttu-id="86d23-234">Указывает файлы сборки ( `.dll` ), необходимые для работы модуля.</span><span class="sxs-lookup"><span data-stu-id="86d23-234">Specifies the assembly (`.dll`) files that the module requires.</span></span> <span data-ttu-id="86d23-235">Введите имена файлов сборки.</span><span class="sxs-lookup"><span data-stu-id="86d23-235">Enter the assembly file names.</span></span>
<span data-ttu-id="86d23-236">PowerShell загружает указанные сборки перед обновлением типов или форматов, импортом вложенных модулей или импортом файла модуля, который указан в значении ключа **RootModule** .</span><span class="sxs-lookup"><span data-stu-id="86d23-236">PowerShell loads the specified assemblies before updating types or formats, importing nested modules, or importing the module file that is specified in the value of the **RootModule** key.</span></span>

<span data-ttu-id="86d23-237">Используйте этот параметр, чтобы указать все сборки, необходимые для работы модуля, включая сборки, которые должны быть загружены для обновления любых файлов форматирования или типов, перечисленных в ключах **форматстопроцесс** или **типестопроцесс** , даже если эти сборки также указаны как двоичные модули в ключе **NestedModules** .</span><span class="sxs-lookup"><span data-stu-id="86d23-237">Use this parameter to specify all the assemblies that the module requires, including assemblies that must be loaded to update any formatting or type files that are listed in the **FormatsToProcess** or **TypesToProcess** keys, even if those assemblies are also listed as binary modules in the **NestedModules** key.</span></span>

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

### <span data-ttu-id="86d23-238">-RequiredModules</span><span class="sxs-lookup"><span data-stu-id="86d23-238">-RequiredModules</span></span>

<span data-ttu-id="86d23-239">Определяет модули, которые должны присутствовать в глобальном состоянии сеанса.</span><span class="sxs-lookup"><span data-stu-id="86d23-239">Specifies modules that must be in the global session state.</span></span> <span data-ttu-id="86d23-240">Если требуемые модули не находятся в глобальном состоянии сеанса, PowerShell импортирует их.</span><span class="sxs-lookup"><span data-stu-id="86d23-240">If the required modules aren't in the global session state, PowerShell imports them.</span></span> <span data-ttu-id="86d23-241">Если требуемые модули недоступны, `Import-Module` команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="86d23-241">If the required modules aren't available, the `Import-Module` command fails.</span></span>

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

### <span data-ttu-id="86d23-242">-RequireLicenseAcceptance</span><span class="sxs-lookup"><span data-stu-id="86d23-242">-RequireLicenseAcceptance</span></span>

<span data-ttu-id="86d23-243">Указывает, что для модуля требуется принятие условий лицензии.</span><span class="sxs-lookup"><span data-stu-id="86d23-243">Specifies that a license acceptance is required for the module.</span></span>

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

### <span data-ttu-id="86d23-244">-RootModule</span><span class="sxs-lookup"><span data-stu-id="86d23-244">-RootModule</span></span>

<span data-ttu-id="86d23-245">Указывает первичный или корневой файл модуля.</span><span class="sxs-lookup"><span data-stu-id="86d23-245">Specifies the primary or root file of the module.</span></span> <span data-ttu-id="86d23-246">Введите имя файла скрипта ( `.ps1` ), модуля скрипта ( `.psm1` ), манифеста модуля ( `.psd1` ), сборки ( `.dll` ), XML-файла определения командлета ( `.cdxml` ) или рабочего процесса ( `.xaml` ).</span><span class="sxs-lookup"><span data-stu-id="86d23-246">Enter the file name of a script (`.ps1`), a script module (`.psm1`), a module manifest (`.psd1`), an assembly (`.dll`), a cmdlet definition XML file (`.cdxml`), or a workflow (`.xaml`).</span></span> <span data-ttu-id="86d23-247">При импорте модуля элементы, экспортируемые из корневого файла модуля, импортируются в состояние сеанса вызывающего объекта.</span><span class="sxs-lookup"><span data-stu-id="86d23-247">When the module is imported, the members that are exported from the root module file are imported into the caller's session state.</span></span>

<span data-ttu-id="86d23-248">Если у модуля есть файл манифеста и корневой файл не указан в ключе **RootModule** , манифест станет первичным файлом для модуля.</span><span class="sxs-lookup"><span data-stu-id="86d23-248">If a module has a manifest file and no root file has been specified in the **RootModule** key, the manifest becomes the primary file for the module.</span></span> <span data-ttu-id="86d23-249">И модуль превращается в модуль манифеста (ModuleType = manifest).</span><span class="sxs-lookup"><span data-stu-id="86d23-249">And, the module becomes a manifest module (ModuleType = Manifest).</span></span>

<span data-ttu-id="86d23-250">Чтобы экспортировать элементы из `.psm1` `.dll` файла или в модуль с манифестом, имена этих файлов должны быть указаны в значениях ключей **RootModule** или **NestedModules** в манифесте.</span><span class="sxs-lookup"><span data-stu-id="86d23-250">To export members from `.psm1` or `.dll` files in a module that has a manifest, the names of those files must be specified in the values of the **RootModule** or **NestedModules** keys in the manifest.</span></span> <span data-ttu-id="86d23-251">В противном случае их члены не экспортируются.</span><span class="sxs-lookup"><span data-stu-id="86d23-251">Otherwise, their members aren't exported.</span></span>

<span data-ttu-id="86d23-252">В PowerShell 2,0 этот ключ назывался **модулетопроцесс** .</span><span class="sxs-lookup"><span data-stu-id="86d23-252">In PowerShell 2.0, this key was called **ModuleToProcess** .</span></span>

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

### <span data-ttu-id="86d23-253">-ScriptsToProcess</span><span class="sxs-lookup"><span data-stu-id="86d23-253">-ScriptsToProcess</span></span>

<span data-ttu-id="86d23-254">Указывает файлы скрипта ( `.ps1` ), которые выполняются в состоянии сеанса вызывающего объекта при импорте модуля.</span><span class="sxs-lookup"><span data-stu-id="86d23-254">Specifies script (`.ps1`) files that run in the caller's session state when the module is imported.</span></span>
<span data-ttu-id="86d23-255">Эти скрипты можно использовать для подготовки среды таким же образом, как и скрипт входа в систему.</span><span class="sxs-lookup"><span data-stu-id="86d23-255">You can use these scripts to prepare an environment, just as you might use a login script.</span></span>

<span data-ttu-id="86d23-256">Чтобы указать скрипты, которые будут выполняться в состоянии сеанса модуля, используйте ключ **NestedModules** .</span><span class="sxs-lookup"><span data-stu-id="86d23-256">To specify scripts that run in the module's session state, use the **NestedModules** key.</span></span>

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

### <span data-ttu-id="86d23-257">-Теги</span><span class="sxs-lookup"><span data-stu-id="86d23-257">-Tags</span></span>

<span data-ttu-id="86d23-258">Задает массив тегов.</span><span class="sxs-lookup"><span data-stu-id="86d23-258">Specifies an array of tags.</span></span>

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

### <span data-ttu-id="86d23-259">-TypesToProcess</span><span class="sxs-lookup"><span data-stu-id="86d23-259">-TypesToProcess</span></span>

<span data-ttu-id="86d23-260">Указывает файлы типов ( `.ps1xml` ), которые выполняются при импорте модуля.</span><span class="sxs-lookup"><span data-stu-id="86d23-260">Specifies the type files (`.ps1xml`) that run when the module is imported.</span></span>

<span data-ttu-id="86d23-261">При импорте модуля PowerShell запускает `Update-TypeData` командлет с указанными файлами.</span><span class="sxs-lookup"><span data-stu-id="86d23-261">When you import the module, PowerShell runs the `Update-TypeData` cmdlet with the specified files.</span></span>
<span data-ttu-id="86d23-262">Так как файлы типов не находятся в области, они влияют на все состояния сеанса в сеансе.</span><span class="sxs-lookup"><span data-stu-id="86d23-262">Because type files aren't scoped, they affect all session states in the session.</span></span>

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

### <span data-ttu-id="86d23-263">-Вариаблестоекспорт</span><span class="sxs-lookup"><span data-stu-id="86d23-263">-VariablesToExport</span></span>

<span data-ttu-id="86d23-264">Задает экспортируемые модулем переменные.</span><span class="sxs-lookup"><span data-stu-id="86d23-264">Specifies the variables that the module exports.</span></span> <span data-ttu-id="86d23-265">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="86d23-265">Wildcards are permitted.</span></span>

<span data-ttu-id="86d23-266">Используйте этот параметр, чтобы ограничить переменные, экспортируемые модулем.</span><span class="sxs-lookup"><span data-stu-id="86d23-266">Use this parameter to restrict the variables that are exported by the module.</span></span> <span data-ttu-id="86d23-267">**Вариаблестоекспорт** может удалять переменные из списка экспортированных переменных, но не может добавлять переменные в список.</span><span class="sxs-lookup"><span data-stu-id="86d23-267">**VariablesToExport** can remove variables from the list of exported variables, but it can't add variables to the list.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="86d23-268">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="86d23-268">-WhatIf</span></span>

<span data-ttu-id="86d23-269">Показывает, что произойдет при `Update-ModuleManifest` запуске.</span><span class="sxs-lookup"><span data-stu-id="86d23-269">Shows what would happen if `Update-ModuleManifest` runs.</span></span> <span data-ttu-id="86d23-270">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="86d23-270">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="86d23-271">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="86d23-271">CommonParameters</span></span>

<span data-ttu-id="86d23-272">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="86d23-272">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="86d23-273">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="86d23-273">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="86d23-274">Входные данные</span><span class="sxs-lookup"><span data-stu-id="86d23-274">INPUTS</span></span>

### <span data-ttu-id="86d23-275">System.String</span><span class="sxs-lookup"><span data-stu-id="86d23-275">System.String</span></span>

## <span data-ttu-id="86d23-276">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="86d23-276">OUTPUTS</span></span>

### <span data-ttu-id="86d23-277">System.Object</span><span class="sxs-lookup"><span data-stu-id="86d23-277">System.Object</span></span>

## <span data-ttu-id="86d23-278">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="86d23-278">NOTES</span></span>

## <span data-ttu-id="86d23-279">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="86d23-279">RELATED LINKS</span></span>
