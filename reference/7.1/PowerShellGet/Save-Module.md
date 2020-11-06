---
external help file: PSModule-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PowerShellGet
ms.date: 11/11/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/save-module?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Save-Module
ms.openlocfilehash: 88ce556a366e67a911bf32eb5c13161a543f103f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228485"
---
# <span data-ttu-id="81ee6-103">Save-Module</span><span class="sxs-lookup"><span data-stu-id="81ee6-103">Save-Module</span></span>

## <span data-ttu-id="81ee6-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="81ee6-104">SYNOPSIS</span></span>
<span data-ttu-id="81ee6-105">Сохраняет модуль и его зависимости на локальном компьютере, но не устанавливает модуль.</span><span class="sxs-lookup"><span data-stu-id="81ee6-105">Saves a module and its dependencies on the local computer but doesn't install the module.</span></span>

## <span data-ttu-id="81ee6-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="81ee6-106">SYNTAX</span></span>

### <span data-ttu-id="81ee6-107">Намеандпаспараметерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="81ee6-107">NameAndPathParameterSet (Default)</span></span>

```
Save-Module [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] [-Path] <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AllowPrerelease]
 [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="81ee6-108">намеандлитералпаспараметерсет</span><span class="sxs-lookup"><span data-stu-id="81ee6-108">NameAndLiteralPathParameterSet</span></span>

```
Save-Module [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] -LiteralPath <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AllowPrerelease]
 [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="81ee6-109">инпутобжектандлитералпаспараметерсет</span><span class="sxs-lookup"><span data-stu-id="81ee6-109">InputObjectAndLiteralPathParameterSet</span></span>

```
Save-Module [-InputObject] <PSObject[]> -LiteralPath <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AcceptLicense] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="81ee6-110">инпутобжектандпаспараметерсет</span><span class="sxs-lookup"><span data-stu-id="81ee6-110">InputObjectAndPathParameterSet</span></span>

```
Save-Module [-InputObject] <PSObject[]> [-Path] <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AcceptLicense] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="81ee6-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="81ee6-111">DESCRIPTION</span></span>

<span data-ttu-id="81ee6-112">`Save-Module`Командлет загружает модуль и все зависимости из зарегистрированного репозитория.</span><span class="sxs-lookup"><span data-stu-id="81ee6-112">The `Save-Module` cmdlet downloads a module and any dependencies from a registered repository.</span></span>
<span data-ttu-id="81ee6-113">`Save-Module` скачивает и сохраняет самую последнюю версию модуля.</span><span class="sxs-lookup"><span data-stu-id="81ee6-113">`Save-Module` downloads and saves the most current version of a module.</span></span> <span data-ttu-id="81ee6-114">Файлы сохраняются по указанному пути на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="81ee6-114">The files are saved to a specified path on the local computer.</span></span> <span data-ttu-id="81ee6-115">Модуль не установлен, но содержимое доступно для проверки администратором.</span><span class="sxs-lookup"><span data-stu-id="81ee6-115">The module isn't installed, but the contents are available for inspection by an administrator.</span></span> <span data-ttu-id="81ee6-116">Сохраненный модуль можно скопировать в соответствующее `$env:PSModulePath` расположение автономного компьютера.</span><span class="sxs-lookup"><span data-stu-id="81ee6-116">The saved module can then be copied into the appropriate `$env:PSModulePath` location of the offline machine.</span></span>

<span data-ttu-id="81ee6-117">`Get-PSRepository` отображает зарегистрированные репозитории локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="81ee6-117">`Get-PSRepository` displays the local computer's registered repositories.</span></span> <span data-ttu-id="81ee6-118">`Find-Module`Для поиска в зарегистрированных репозиториях можно использовать командлет.</span><span class="sxs-lookup"><span data-stu-id="81ee6-118">You can use the `Find-Module` cmdlet to search registered repositories.</span></span>

## <span data-ttu-id="81ee6-119">Примеры</span><span class="sxs-lookup"><span data-stu-id="81ee6-119">EXAMPLES</span></span>

### <span data-ttu-id="81ee6-120">Пример 1. Сохранение модуля</span><span class="sxs-lookup"><span data-stu-id="81ee6-120">Example 1: Save a module</span></span>

<span data-ttu-id="81ee6-121">В этом примере модуль и его зависимости сохраняются на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="81ee6-121">In this example, a module and its dependencies are saved to the local computer.</span></span>

```powershell
Save-Module -Name PowerShellGet -Path C:\Test\Modules -Repository PSGallery
Get-ChildItem -Path C:\Test\Modules
```

```Output
    Directory: C:\Test\Modules

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----         7/1/2019     13:31                PackageManagement
d-----         7/1/2019     13:31                PowerShellGet
```

<span data-ttu-id="81ee6-122">`Save-Module` использует параметр **Name** для указания модуля **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="81ee6-122">`Save-Module` uses the **Name** parameter to specify the module, **PowerShellGet** .</span></span> <span data-ttu-id="81ee6-123">Параметр **path** указывает место хранения скачанного модуля.</span><span class="sxs-lookup"><span data-stu-id="81ee6-123">The **Path** parameter specifies where to store the downloaded module.</span></span> <span data-ttu-id="81ee6-124">Параметр **репозитория** указывает зарегистрированный репозиторий **PSGallery** .</span><span class="sxs-lookup"><span data-stu-id="81ee6-124">The **Repository** parameter specifies a registered repository, **PSGallery** .</span></span> <span data-ttu-id="81ee6-125">По завершении загрузки `Get-ChildItem` отображает содержимое **папки** , в которой хранятся файлы.</span><span class="sxs-lookup"><span data-stu-id="81ee6-125">After the download is finished, `Get-ChildItem` displays the contents of **Path** where the files are stored.</span></span>

### <span data-ttu-id="81ee6-126">Пример 2. сохранение определенной версии модуля</span><span class="sxs-lookup"><span data-stu-id="81ee6-126">Example 2: Save a specific version of a module</span></span>

<span data-ttu-id="81ee6-127">В этом примере показано, как использовать параметр, например **MaximumVersion** , или **RequiredVersion** , чтобы указать версию модуля.</span><span class="sxs-lookup"><span data-stu-id="81ee6-127">This example shows how to use a parameter such as **MaximumVersion** , or **RequiredVersion** to specify a module version.</span></span>

```powershell
Save-Module -Name PowerShellGet -Path C:\Test\Modules -Repository PSGallery -MaximumVersion 2.1.0
Get-ChildItem -Path C:\Test\Modules\PowerShellGet\
```

```Output
    Directory: C:\Test\Modules\PowerShellGet

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----         7/1/2019     13:40                2.1.0
```

<span data-ttu-id="81ee6-128">`Save-Module` использует параметр **Name** для указания модуля **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="81ee6-128">`Save-Module` uses the **Name** parameter to specify the module, **PowerShellGet** .</span></span> <span data-ttu-id="81ee6-129">Параметр **path** указывает место хранения скачанного модуля.</span><span class="sxs-lookup"><span data-stu-id="81ee6-129">The **Path** parameter specifies where to store the downloaded module.</span></span> <span data-ttu-id="81ee6-130">Параметр **репозитория** указывает зарегистрированный репозиторий **PSGallery** .</span><span class="sxs-lookup"><span data-stu-id="81ee6-130">The **Repository** parameter specifies a registered repository, **PSGallery** .</span></span> <span data-ttu-id="81ee6-131">**MaximumVersion** указывает, что версия **2.1.0** скачана и сохранена.</span><span class="sxs-lookup"><span data-stu-id="81ee6-131">**MaximumVersion** specifies that version **2.1.0** is downloaded and saved.</span></span> <span data-ttu-id="81ee6-132">По завершении загрузки `Get-ChildItem` отображает содержимое **папки** , в которой хранятся файлы.</span><span class="sxs-lookup"><span data-stu-id="81ee6-132">After the download is finished, `Get-ChildItem` displays the contents of **Path** where the files are stored.</span></span>

### <span data-ttu-id="81ee6-133">Пример 3. Поиск и сохранение определенной версии модуля</span><span class="sxs-lookup"><span data-stu-id="81ee6-133">Example 3: Find and save a specific version of a module</span></span>

<span data-ttu-id="81ee6-134">В этом примере требуемая версия модуля находится в репозитории и сохраняется на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="81ee6-134">In this example, a required module version is found in the repository and saved to the local computer.</span></span>

```powershell
Find-Module -Name PowerShellGet -Repository PSGallery -RequiredVersion 1.6.5 |
  Save-Module -Path C:\Test\Modules
Get-ChildItem -Path C:\Test\Modules\PowerShellGet
```

```Output
    Directory: C:\Test\Modules\PowerShellGet

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----         7/1/2019     14:04                1.6.5
```

<span data-ttu-id="81ee6-135">`Find-Module` использует параметр **Name** для указания модуля **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="81ee6-135">`Find-Module` uses the **Name** parameter to specify the module, **PowerShellGet** .</span></span> <span data-ttu-id="81ee6-136">Параметр **репозитория** указывает зарегистрированный репозиторий **PSGallery** .</span><span class="sxs-lookup"><span data-stu-id="81ee6-136">The **Repository** parameter specifies a registered repository, **PSGallery** .</span></span> <span data-ttu-id="81ee6-137">**RequiredVersion** указывает версию **1.6.5** .</span><span class="sxs-lookup"><span data-stu-id="81ee6-137">**RequiredVersion** specifies version **1.6.5** .</span></span>

<span data-ttu-id="81ee6-138">Объект отправляется по конвейеру в `Save-Module` .</span><span class="sxs-lookup"><span data-stu-id="81ee6-138">The object is sent down the pipeline to `Save-Module`.</span></span> <span data-ttu-id="81ee6-139">Параметр **path** указывает место хранения скачанного модуля.</span><span class="sxs-lookup"><span data-stu-id="81ee6-139">The **Path** parameter specifies where to store the downloaded module.</span></span> <span data-ttu-id="81ee6-140">По завершении загрузки `Get-ChildItem` отображает содержимое **папки** , в которой хранятся файлы.</span><span class="sxs-lookup"><span data-stu-id="81ee6-140">After the download is finished, `Get-ChildItem` displays the contents of **Path** where the files are stored.</span></span>

## <span data-ttu-id="81ee6-141">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="81ee6-141">PARAMETERS</span></span>

### <span data-ttu-id="81ee6-142">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="81ee6-142">-AcceptLicense</span></span>

<span data-ttu-id="81ee6-143">Автоматически принять лицензионное соглашение, если оно требуется для пакета.</span><span class="sxs-lookup"><span data-stu-id="81ee6-143">Automatically accept the license agreement if the package requires it.</span></span>

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

### <span data-ttu-id="81ee6-144">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="81ee6-144">-AllowPrerelease</span></span>

<span data-ttu-id="81ee6-145">Позволяет сохранить модуль, помеченный как предварительный выпуск.</span><span class="sxs-lookup"><span data-stu-id="81ee6-145">Allows you to save a module marked as a prerelease.</span></span>

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

### <span data-ttu-id="81ee6-146">-Confirm</span><span class="sxs-lookup"><span data-stu-id="81ee6-146">-Confirm</span></span>

<span data-ttu-id="81ee6-147">Запрашивает подтверждение перед запуском `Save-Module` .</span><span class="sxs-lookup"><span data-stu-id="81ee6-147">Prompts you for confirmation before running the `Save-Module`.</span></span>

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

### <span data-ttu-id="81ee6-148">-Credential</span><span class="sxs-lookup"><span data-stu-id="81ee6-148">-Credential</span></span>

<span data-ttu-id="81ee6-149">Указывает учетную запись пользователя, имеющую права на сохранение модуля.</span><span class="sxs-lookup"><span data-stu-id="81ee6-149">Specifies a user account that has rights to save a module.</span></span>

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

### <span data-ttu-id="81ee6-150">-Force</span><span class="sxs-lookup"><span data-stu-id="81ee6-150">-Force</span></span>

<span data-ttu-id="81ee6-151">Принудительное `Save-Module` выполнение без запроса подтверждения пользователя.</span><span class="sxs-lookup"><span data-stu-id="81ee6-151">Forces `Save-Module` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="81ee6-152">-InputObject</span><span class="sxs-lookup"><span data-stu-id="81ee6-152">-InputObject</span></span>

<span data-ttu-id="81ee6-153">Принимает объект **PSRepositoryItemInfo** .</span><span class="sxs-lookup"><span data-stu-id="81ee6-153">Accepts a **PSRepositoryItemInfo** object.</span></span> <span data-ttu-id="81ee6-154">Например, выходные данные переводятся `Find-Module` в переменную и используют эту переменную в качестве аргумента **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="81ee6-154">For example, output `Find-Module` to a variable and use that variable as the **InputObject** argument.</span></span>

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

### <span data-ttu-id="81ee6-155">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="81ee6-155">-LiteralPath</span></span>

<span data-ttu-id="81ee6-156">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="81ee6-156">Specifies a path to one or more locations.</span></span> <span data-ttu-id="81ee6-157">Значение параметра **LiteralPath** используется в точности так, как указано.</span><span class="sxs-lookup"><span data-stu-id="81ee6-157">The value of the **LiteralPath** parameter is used exactly as entered.</span></span> <span data-ttu-id="81ee6-158">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="81ee6-158">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="81ee6-159">Если путь содержит escape-символы, заключите их в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="81ee6-159">If the path includes escape characters, enclose them in single quotation marks.</span></span> <span data-ttu-id="81ee6-160">PowerShell не интерпретирует символы, заключенные в одинарные кавычки, как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="81ee6-160">PowerShell does not interpret any characters enclosed in single quotation marks as escape sequences.</span></span>

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

### <span data-ttu-id="81ee6-161">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="81ee6-161">-MaximumVersion</span></span>

<span data-ttu-id="81ee6-162">Указывает максимальную или самую новую версию модуля для сохранения.</span><span class="sxs-lookup"><span data-stu-id="81ee6-162">Specifies the maximum, or newest, version of the module to save.</span></span> <span data-ttu-id="81ee6-163">Параметры **MaximumVersion** и **RequiredVersion** нельзя использовать в одной команде.</span><span class="sxs-lookup"><span data-stu-id="81ee6-163">The **MaximumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="81ee6-164">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="81ee6-164">-MinimumVersion</span></span>

<span data-ttu-id="81ee6-165">Указывает минимальную версию одного модуля для сохранения.</span><span class="sxs-lookup"><span data-stu-id="81ee6-165">Specifies the minimum version of a single module to save.</span></span> <span data-ttu-id="81ee6-166">Этот параметр нельзя добавить, если вы пытаетесь установить несколько модулей.</span><span class="sxs-lookup"><span data-stu-id="81ee6-166">You cannot add this parameter if you are attempting to install multiple modules.</span></span> <span data-ttu-id="81ee6-167">Параметры **MinimumVersion** и **RequiredVersion** нельзя использовать в одной команде.</span><span class="sxs-lookup"><span data-stu-id="81ee6-167">The **MinimumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="81ee6-168">-Name</span><span class="sxs-lookup"><span data-stu-id="81ee6-168">-Name</span></span>

<span data-ttu-id="81ee6-169">Указывает массив имен модулей для сохранения.</span><span class="sxs-lookup"><span data-stu-id="81ee6-169">Specifies an array of names of modules to save.</span></span>

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

### <span data-ttu-id="81ee6-170">-Path</span><span class="sxs-lookup"><span data-stu-id="81ee6-170">-Path</span></span>

<span data-ttu-id="81ee6-171">Указывает место на локальном компьютере для хранения сохраненного модуля.</span><span class="sxs-lookup"><span data-stu-id="81ee6-171">Specifies the location on the local computer to store a saved module.</span></span> <span data-ttu-id="81ee6-172">Принимает подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="81ee6-172">Accepts wildcard characters.</span></span>

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

### <span data-ttu-id="81ee6-173">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="81ee6-173">-Proxy</span></span>

<span data-ttu-id="81ee6-174">Указывает прокси-сервер для запроса, а не напрямуюе подключение к Интернет-ресурсу.</span><span class="sxs-lookup"><span data-stu-id="81ee6-174">Specifies a proxy server for the request, rather than connecting directly to the internet resource.</span></span>

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

### <span data-ttu-id="81ee6-175">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="81ee6-175">-ProxyCredential</span></span>

<span data-ttu-id="81ee6-176">Указывает учетную запись пользователя, имеющую разрешение на использование прокси-сервера, который задается параметром **Proxy** .</span><span class="sxs-lookup"><span data-stu-id="81ee6-176">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="81ee6-177">— Репозиторий;</span><span class="sxs-lookup"><span data-stu-id="81ee6-177">-Repository</span></span>

<span data-ttu-id="81ee6-178">Указывает понятное имя репозитория, зарегистрированного при выполнении `Register-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="81ee6-178">Specifies the friendly name of a repository that has been registered by running `Register-PSRepository`.</span></span> <span data-ttu-id="81ee6-179">Используется `Get-PSRepository` для вывода зарегистрированных репозиториев.</span><span class="sxs-lookup"><span data-stu-id="81ee6-179">Use `Get-PSRepository` to display registered repositories.</span></span>

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

### <span data-ttu-id="81ee6-180">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="81ee6-180">-RequiredVersion</span></span>

<span data-ttu-id="81ee6-181">Указывает точный номер версии для сохраняемого модуля.</span><span class="sxs-lookup"><span data-stu-id="81ee6-181">Specifies the exact version number of the module to save.</span></span>

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

### <span data-ttu-id="81ee6-182">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="81ee6-182">-WhatIf</span></span>

<span data-ttu-id="81ee6-183">Показывает, что произойдет при `Save-Module` выполнении.</span><span class="sxs-lookup"><span data-stu-id="81ee6-183">Shows what would happen if the `Save-Module` runs.</span></span> <span data-ttu-id="81ee6-184">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="81ee6-184">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="81ee6-185">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="81ee6-185">CommonParameters</span></span>

<span data-ttu-id="81ee6-186">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="81ee6-186">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="81ee6-187">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="81ee6-187">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="81ee6-188">Входные данные</span><span class="sxs-lookup"><span data-stu-id="81ee6-188">INPUTS</span></span>

### <span data-ttu-id="81ee6-189">System.String[]</span><span class="sxs-lookup"><span data-stu-id="81ee6-189">System.String[]</span></span>

### <span data-ttu-id="81ee6-190">System. Management. Automation. PSObject []</span><span class="sxs-lookup"><span data-stu-id="81ee6-190">System.Management.Automation.PSObject[]</span></span>

### <span data-ttu-id="81ee6-191">System.String</span><span class="sxs-lookup"><span data-stu-id="81ee6-191">System.String</span></span>

### <span data-ttu-id="81ee6-192">System.Uri</span><span class="sxs-lookup"><span data-stu-id="81ee6-192">System.Uri</span></span>

### <span data-ttu-id="81ee6-193">System.Management.Automation.PSCredential</span><span class="sxs-lookup"><span data-stu-id="81ee6-193">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="81ee6-194">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="81ee6-194">OUTPUTS</span></span>

### <span data-ttu-id="81ee6-195">System.Object</span><span class="sxs-lookup"><span data-stu-id="81ee6-195">System.Object</span></span>

## <span data-ttu-id="81ee6-196">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="81ee6-196">NOTES</span></span>

## <span data-ttu-id="81ee6-197">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="81ee6-197">RELATED LINKS</span></span>
