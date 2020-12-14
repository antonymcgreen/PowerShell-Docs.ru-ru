---
external help file: PSModule-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PowerShellGet
ms.date: 10/03/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/publish-module?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Publish-Module
ms.openlocfilehash: 3ada5513343a5d6527cf1b091e1ee85e51f7f8de
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "94892255"
---
# <span data-ttu-id="8a973-103">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="8a973-103">Publish-Module</span></span>

## <span data-ttu-id="8a973-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="8a973-104">SYNOPSIS</span></span>
<span data-ttu-id="8a973-105">Публикует указанный модуль с локального компьютера в коллекцию в Интернете.</span><span class="sxs-lookup"><span data-stu-id="8a973-105">Publishes a specified module from the local computer to an online gallery.</span></span>

## <span data-ttu-id="8a973-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8a973-106">SYNTAX</span></span>

### <span data-ttu-id="8a973-107">Модуленамепараметерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="8a973-107">ModuleNameParameterSet (Default)</span></span>

```
Publish-Module -Name <String> [-RequiredVersion <String>] [-NuGetApiKey <String>]
 [-Repository <String>] [-Credential <PSCredential>] [-FormatVersion <Version>]
 [-ReleaseNotes <String[]>] [-Tags <String[]>] [-LicenseUri <Uri>] [-IconUri <Uri>]
 [-ProjectUri <Uri>] [-Exclude <String[]>] [-Force] [-AllowPrerelease] [-SkipAutomaticTags]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="8a973-108">модулепаспараметерсет</span><span class="sxs-lookup"><span data-stu-id="8a973-108">ModulePathParameterSet</span></span>

```
Publish-Module -Path <String> [-NuGetApiKey <String>] [-Repository <String>]
 [-Credential <PSCredential>] [-FormatVersion <Version>] [-ReleaseNotes <String[]>]
 [-Tags <String[]>] [-LicenseUri <Uri>] [-IconUri <Uri>] [-ProjectUri <Uri>] [-Force]
 [-SkipAutomaticTags] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="8a973-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8a973-109">DESCRIPTION</span></span>

<span data-ttu-id="8a973-110">`Publish-Module`Командлет публикует модуль в коллекции на основе NuGet через Интернет, используя ключ API, хранящийся как часть профиля пользователя в коллекции.</span><span class="sxs-lookup"><span data-stu-id="8a973-110">The `Publish-Module` cmdlet publishes a module to an online NuGet-based gallery by using an API key, stored as part of a user's profile in the gallery.</span></span> <span data-ttu-id="8a973-111">Модуль для публикации можно указывать с помощью имени модуля или пути к папке, содержащей модуль.</span><span class="sxs-lookup"><span data-stu-id="8a973-111">You can specify the module to publish either by the module's name, or by the path to the folder containing the module.</span></span>

<span data-ttu-id="8a973-112">При указании модуля по имени `Publish-Module` публикует первый модуль, который можно найти, выполнив `Get-Module -ListAvailable <Name>` .</span><span class="sxs-lookup"><span data-stu-id="8a973-112">When you specify a module by name, `Publish-Module` publishes the first module that would be found by running `Get-Module -ListAvailable <Name>`.</span></span> <span data-ttu-id="8a973-113">Если указана минимальная версия модуля для публикации, `Publish-Module` публикует первый модуль с версией, которая больше или равна указанной минимальной версии.</span><span class="sxs-lookup"><span data-stu-id="8a973-113">If you specify a minimum version of a module to publish, `Publish-Module` publishes the first module with a version that is greater than or equal to the minimum version that you have specified.</span></span>

<span data-ttu-id="8a973-114">Для публикации модуля требуются метаданные, которые отображаются на странице коллекции для этого модуля.</span><span class="sxs-lookup"><span data-stu-id="8a973-114">Publishing a module requires metadata that is displayed on the gallery page for the module.</span></span> <span data-ttu-id="8a973-115">Обязательные метаданные включают имя модуля, версию, описание и автора.</span><span class="sxs-lookup"><span data-stu-id="8a973-115">Required metadata includes the module name, version, description, and author.</span></span> <span data-ttu-id="8a973-116">Хотя большинство метаданных берутся из манифеста модуля, некоторые метаданные должны быть указаны в `Publish-Module` параметрах, таких как **Tag**, **релеасеноте**, **IconUri**, **ProjectUri** и **LicenseUri**, так как эти параметры соответствуют полям в коллекции на основе NuGet.</span><span class="sxs-lookup"><span data-stu-id="8a973-116">Although most metadata is taken from the module manifest, some metadata must be specified in `Publish-Module` parameters, such as **Tag**, **ReleaseNote**, **IconUri**, **ProjectUri**, and **LicenseUri**, because these parameters match fields in a NuGet-based gallery.</span></span>

## <span data-ttu-id="8a973-117">Примеры</span><span class="sxs-lookup"><span data-stu-id="8a973-117">EXAMPLES</span></span>

### <span data-ttu-id="8a973-118">Пример 1. Публикация модуля</span><span class="sxs-lookup"><span data-stu-id="8a973-118">Example 1: Publish a module</span></span>

<span data-ttu-id="8a973-119">В этом примере Мидскмодуле публикуется в веб-коллекции с помощью ключа API для указания учетной записи коллекции в Интернете владельца модуля.</span><span class="sxs-lookup"><span data-stu-id="8a973-119">In this example, MyDscModule is published to the online gallery by using the API key to indicate the module owner's online gallery account.</span></span> <span data-ttu-id="8a973-120">Если Мидскмодуле не является допустимым модулем манифеста, который указывает имя, версию, описание и автора, возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="8a973-120">If MyDscModule is not a valid manifest module that specifies a name, version, description, and author, an error occurs.</span></span>

```powershell
Publish-Module -Name "MyDscModule" -NuGetApiKey "11e4b435-6cb4-4bf7-8611-5162ed75eb73"
```

### <span data-ttu-id="8a973-121">Пример 2. Публикация модуля с метаданными коллекции</span><span class="sxs-lookup"><span data-stu-id="8a973-121">Example 2: Publish a module with gallery metadata</span></span>

<span data-ttu-id="8a973-122">В этом примере Мидскмодуле публикуется в Интернет-коллекции с помощью ключа API для указания учетной записи коллекции владельца модуля.</span><span class="sxs-lookup"><span data-stu-id="8a973-122">In this example, MyDscModule is published to the online gallery by using the API key to indicate the module owner's gallery account.</span></span> <span data-ttu-id="8a973-123">Дополнительные метаданные отображаются на веб-странице модуля в коллекции.</span><span class="sxs-lookup"><span data-stu-id="8a973-123">The additional metadata provided is displayed on the webpage for the module in the gallery.</span></span> <span data-ttu-id="8a973-124">Владелец добавляет два тега поиска для модуля, соотнесенный с Active Directory; будет добавлена Краткая заметка о выпуске.</span><span class="sxs-lookup"><span data-stu-id="8a973-124">The owner adds two search tags for the module, relating it to Active Directory; a brief release note is added.</span></span> <span data-ttu-id="8a973-125">Если Мидскмодуле не является допустимым модулем манифеста, который указывает имя, версию, описание и автора, возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="8a973-125">If MyDscModule is not a valid manifest module that specifies a name, version, description, and author, an error occurs.</span></span>

```powershell
Publish-Module -Name "MyDscModule" -NuGetApiKey "11e4b435-6cb4-4bf7-8611-5162ed75eb73" -LicenseUri "http://contoso.com/license" -Tag "Active Directory","DSC" -ReleaseNote "Updated the ActiveDirectory DSC Resources to support adding users."
```

## <span data-ttu-id="8a973-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8a973-126">PARAMETERS</span></span>

### <span data-ttu-id="8a973-127">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="8a973-127">-AllowPrerelease</span></span>

<span data-ttu-id="8a973-128">Разрешает публикацию модулей, помеченных как предварительные.</span><span class="sxs-lookup"><span data-stu-id="8a973-128">Allows modules marked as prerelease to be published.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ModuleNameParameterSet
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8a973-129">-Confirm</span><span class="sxs-lookup"><span data-stu-id="8a973-129">-Confirm</span></span>

<span data-ttu-id="8a973-130">Запрашивает подтверждение перед запуском `Publish-Module` .</span><span class="sxs-lookup"><span data-stu-id="8a973-130">Prompts you for confirmation before running the `Publish-Module`.</span></span>

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

### <span data-ttu-id="8a973-131">-Credential</span><span class="sxs-lookup"><span data-stu-id="8a973-131">-Credential</span></span>

<span data-ttu-id="8a973-132">Указывает учетную запись пользователя, имеющую права на публикацию модуля для указанного поставщика пакетов или источника.</span><span class="sxs-lookup"><span data-stu-id="8a973-132">Specifies a user account that has rights to publish a module for a specified package provider or source.</span></span>

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

### <span data-ttu-id="8a973-133">-Exclude</span><span class="sxs-lookup"><span data-stu-id="8a973-133">-Exclude</span></span>

<span data-ttu-id="8a973-134">Определяет файлы, исключаемые из опубликованного модуля.</span><span class="sxs-lookup"><span data-stu-id="8a973-134">Defines files to exclude from the published module.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ModuleNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8a973-135">-Force</span><span class="sxs-lookup"><span data-stu-id="8a973-135">-Force</span></span>

<span data-ttu-id="8a973-136">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="8a973-136">Forces the command to run without asking for user confirmation.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8a973-137">-FormatVersion</span><span class="sxs-lookup"><span data-stu-id="8a973-137">-FormatVersion</span></span>

<span data-ttu-id="8a973-138">Принимает только допустимые значения, указанные в атрибуте **Validate** .</span><span class="sxs-lookup"><span data-stu-id="8a973-138">Accepts only valid values specified by the **ValidateSet** attribute.</span></span>

<span data-ttu-id="8a973-139">Дополнительные сведения см. в [статьях объявление атрибута](/powershell/scripting/developer/cmdlet/validateset-attribute-declaration) и [валидатесетаттрибуте](/dotnet/api/system.management.automation.validatesetattribute).</span><span class="sxs-lookup"><span data-stu-id="8a973-139">For more information, see [ValidateSet Attribute Declaration](/powershell/scripting/developer/cmdlet/validateset-attribute-declaration) and [ValidateSetAttribute](/dotnet/api/system.management.automation.validatesetattribute).</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:
Accepted values: 2.0

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8a973-140">-IconUri</span><span class="sxs-lookup"><span data-stu-id="8a973-140">-IconUri</span></span>

<span data-ttu-id="8a973-141">Задает URL-адрес значка для модуля.</span><span class="sxs-lookup"><span data-stu-id="8a973-141">Specifies the URL of an icon for the module.</span></span> <span data-ttu-id="8a973-142">Указанный значок отображается на веб-странице коллекции модуля.</span><span class="sxs-lookup"><span data-stu-id="8a973-142">The specified icon is displayed on the gallery webpage for the module.</span></span>

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

### <span data-ttu-id="8a973-143">-LicenseUri</span><span class="sxs-lookup"><span data-stu-id="8a973-143">-LicenseUri</span></span>

<span data-ttu-id="8a973-144">Указывает URL-адрес условий лицензирования для модуля, который вы хотите опубликовать.</span><span class="sxs-lookup"><span data-stu-id="8a973-144">Specifies the URL of licensing terms for the module you want to publish.</span></span>

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

### <span data-ttu-id="8a973-145">-Name</span><span class="sxs-lookup"><span data-stu-id="8a973-145">-Name</span></span>

<span data-ttu-id="8a973-146">Указывает имя модуля, который необходимо опубликовать.</span><span class="sxs-lookup"><span data-stu-id="8a973-146">Specifies the name of the module that you want to publish.</span></span> <span data-ttu-id="8a973-147">`Publish-Module` выполняет поиск указанного имени модуля в `$Env:PSModulePath` .</span><span class="sxs-lookup"><span data-stu-id="8a973-147">`Publish-Module` searches for the specified module name in `$Env:PSModulePath`.</span></span>

```yaml
Type: System.String
Parameter Sets: ModuleNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8a973-148">-NuGetApiKey</span><span class="sxs-lookup"><span data-stu-id="8a973-148">-NuGetApiKey</span></span>

<span data-ttu-id="8a973-149">Указывает ключ API, который вы хотите использовать для публикации модуля в интерактивной коллекции.</span><span class="sxs-lookup"><span data-stu-id="8a973-149">Specifies the API key that you want to use to publish a module to the online gallery.</span></span> <span data-ttu-id="8a973-150">Ключ API является частью вашего профиля в интерактивной коллекции, и его можно найти на странице учетной записи пользователя в коллекции.</span><span class="sxs-lookup"><span data-stu-id="8a973-150">The API key is part of your profile in the online gallery, and can be found on your user account page in the gallery.</span></span> <span data-ttu-id="8a973-151">Ключ API — это специальные функции NuGet.</span><span class="sxs-lookup"><span data-stu-id="8a973-151">The API key is NuGet-specific functionality.</span></span>

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

### <span data-ttu-id="8a973-152">-Path</span><span class="sxs-lookup"><span data-stu-id="8a973-152">-Path</span></span>

<span data-ttu-id="8a973-153">Указывает путь к модулю, который необходимо опубликовать.</span><span class="sxs-lookup"><span data-stu-id="8a973-153">Specifies the path to the module that you want to publish.</span></span> <span data-ttu-id="8a973-154">Этот параметр принимает путь к папке, содержащей модуль.</span><span class="sxs-lookup"><span data-stu-id="8a973-154">This parameter accepts the path to the folder that contains the module.</span></span>

```yaml
Type: System.String
Parameter Sets: ModulePathParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8a973-155">-ProjectUri</span><span class="sxs-lookup"><span data-stu-id="8a973-155">-ProjectUri</span></span>

<span data-ttu-id="8a973-156">Указывает URL-адрес веб-страницы об этом проекте.</span><span class="sxs-lookup"><span data-stu-id="8a973-156">Specifies the URL of a webpage about this project.</span></span>

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

### <span data-ttu-id="8a973-157">-ReleaseNotes</span><span class="sxs-lookup"><span data-stu-id="8a973-157">-ReleaseNotes</span></span>

<span data-ttu-id="8a973-158">Указывает строку, содержащую заметки о выпуске или комментарии, которые должны быть доступны пользователям данной версии модуля.</span><span class="sxs-lookup"><span data-stu-id="8a973-158">Specifies a string containing release notes or comments that you want to be available to users of this version of the module.</span></span>

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

### <span data-ttu-id="8a973-159">— Репозиторий;</span><span class="sxs-lookup"><span data-stu-id="8a973-159">-Repository</span></span>

<span data-ttu-id="8a973-160">Указывает понятное имя репозитория, зарегистрированного при выполнении `Register-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="8a973-160">Specifies the friendly name of a repository that has been registered by running `Register-PSRepository`.</span></span> <span data-ttu-id="8a973-161">Репозиторий должен иметь **публишлокатион**, который является допустимым URI NuGet.</span><span class="sxs-lookup"><span data-stu-id="8a973-161">The repository must have a **PublishLocation**, which is a valid NuGet URI.</span></span>
<span data-ttu-id="8a973-162">**Публишлокатион** можно задать, выполнив `Set-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="8a973-162">The **PublishLocation** can be set by running `Set-PSRepository`.</span></span>

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

### <span data-ttu-id="8a973-163">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="8a973-163">-RequiredVersion</span></span>

<span data-ttu-id="8a973-164">Указывает точную версию одного модуля для публикации.</span><span class="sxs-lookup"><span data-stu-id="8a973-164">Specifies the exact version of a single module to publish.</span></span>

```yaml
Type: System.String
Parameter Sets: ModuleNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8a973-165">-Скипаутоматиктагс</span><span class="sxs-lookup"><span data-stu-id="8a973-165">-SkipAutomaticTags</span></span>

<span data-ttu-id="8a973-166">Удаляет команды и ресурсы из включения в качестве тегов.</span><span class="sxs-lookup"><span data-stu-id="8a973-166">Removes commands and resources from being included as tags.</span></span> <span data-ttu-id="8a973-167">Пропускает автоматическое добавление тегов в модуль.</span><span class="sxs-lookup"><span data-stu-id="8a973-167">Skips automatically adding tags to a module.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8a973-168">-Теги</span><span class="sxs-lookup"><span data-stu-id="8a973-168">-Tags</span></span>

<span data-ttu-id="8a973-169">Добавляет один или несколько тегов в публикуемый модуль.</span><span class="sxs-lookup"><span data-stu-id="8a973-169">Adds one or more tags to the module that you are publishing.</span></span> <span data-ttu-id="8a973-170">Примеры тегов: Десиредстатеконфигуратион, DSC, Дскресаурцекит или PSModule.</span><span class="sxs-lookup"><span data-stu-id="8a973-170">Example tags include DesiredStateConfiguration, DSC, DSCResourceKit, or PSModule.</span></span> <span data-ttu-id="8a973-171">Несколько тегов разделяются запятыми.</span><span class="sxs-lookup"><span data-stu-id="8a973-171">Separate multiple tags with commas.</span></span>

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

### <span data-ttu-id="8a973-172">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="8a973-172">-WhatIf</span></span>

<span data-ttu-id="8a973-173">Показывает, что произойдет при `Publish-Module` выполнении.</span><span class="sxs-lookup"><span data-stu-id="8a973-173">Shows what would happen if the `Publish-Module` runs.</span></span> <span data-ttu-id="8a973-174">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="8a973-174">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="8a973-175">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="8a973-175">CommonParameters</span></span>

<span data-ttu-id="8a973-176">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="8a973-176">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8a973-177">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="8a973-177">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8a973-178">Входные данные</span><span class="sxs-lookup"><span data-stu-id="8a973-178">INPUTS</span></span>

### <span data-ttu-id="8a973-179">System.String</span><span class="sxs-lookup"><span data-stu-id="8a973-179">System.String</span></span>

### <span data-ttu-id="8a973-180">System.Management.Automation.PSCredential</span><span class="sxs-lookup"><span data-stu-id="8a973-180">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="8a973-181">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="8a973-181">OUTPUTS</span></span>

### <span data-ttu-id="8a973-182">System.Object</span><span class="sxs-lookup"><span data-stu-id="8a973-182">System.Object</span></span>

## <span data-ttu-id="8a973-183">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="8a973-183">NOTES</span></span>

<span data-ttu-id="8a973-184">`Publish-Module` работает в PowerShell 3,0 или более поздних версиях PowerShell, в Windows 7 или Windows 2008 R2 и более поздних версиях Windows.</span><span class="sxs-lookup"><span data-stu-id="8a973-184">`Publish-Module` runs on PowerShell 3.0 or later releases of PowerShell, on Windows 7 or Windows 2008 R2 and later releases of Windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8a973-185">По состоянию на апрель 2020 коллекция PowerShell больше не поддерживает TLS-версии 1,0 и 1,1.</span><span class="sxs-lookup"><span data-stu-id="8a973-185">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="8a973-186">Если вы не используете TLS 1,2 или более поздней версии, при попытке доступа к коллекция PowerShell возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="8a973-186">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="8a973-187">Используйте следующую команду, чтобы убедиться, что используется TLS 1,2:</span><span class="sxs-lookup"><span data-stu-id="8a973-187">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="8a973-188">Дополнительные сведения см. в [объявлении](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) в блоге PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8a973-188">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

<span data-ttu-id="8a973-189">Для публикации модуля требуются метаданные, которые отображаются на странице коллекции для этого модуля.</span><span class="sxs-lookup"><span data-stu-id="8a973-189">Publishing a module requires metadata that is displayed on the gallery page for the module.</span></span> <span data-ttu-id="8a973-190">Обязательные метаданные включают имя модуля, версию, описание и автора.</span><span class="sxs-lookup"><span data-stu-id="8a973-190">Required metadata includes the module name, version, description, and author.</span></span> <span data-ttu-id="8a973-191">Большинство метаданных берутся из манифеста модуля, но некоторые метаданные могут быть указаны в `Publish-Module` параметрах, таких как **Tag**, **релеасеноте**, **IconUri**, **ProjectUri** и **LicenseUri**.</span><span class="sxs-lookup"><span data-stu-id="8a973-191">Most metadata is taken from the module manifest, but some metadata can be specified in `Publish-Module` parameters, such as **Tag**, **ReleaseNote**, **IconUri**, **ProjectUri**, and **LicenseUri**.</span></span> <span data-ttu-id="8a973-192">Дополнительные сведения см. [в разделе значения манифеста пакета, которые влияют на коллекция PowerShell пользовательский интерфейс](/powershell/scripting/gallery/concepts/package-manifest-affecting-ui).</span><span class="sxs-lookup"><span data-stu-id="8a973-192">For more information, see [Package manifest values that impact the PowerShell Gallery UI](/powershell/scripting/gallery/concepts/package-manifest-affecting-ui).</span></span>

## <span data-ttu-id="8a973-193">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="8a973-193">RELATED LINKS</span></span>

[<span data-ttu-id="8a973-194">Find-Module</span><span class="sxs-lookup"><span data-stu-id="8a973-194">Find-Module</span></span>](Find-Module.md)

[<span data-ttu-id="8a973-195">Install-Module</span><span class="sxs-lookup"><span data-stu-id="8a973-195">Install-Module</span></span>](Install-Module.md)

[<span data-ttu-id="8a973-196">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="8a973-196">Register-PSRepository</span></span>](Register-PSRepository.md)

[<span data-ttu-id="8a973-197">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="8a973-197">Set-PSRepository</span></span>](Set-PSRepository.md)

[<span data-ttu-id="8a973-198">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="8a973-198">Uninstall-Module</span></span>](Uninstall-Module.md)

[<span data-ttu-id="8a973-199">Update-Module</span><span class="sxs-lookup"><span data-stu-id="8a973-199">Update-Module</span></span>](Update-Module.md)
