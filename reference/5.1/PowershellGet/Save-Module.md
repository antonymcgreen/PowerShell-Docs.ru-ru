---
external help file: PSModule-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PowerShellGet
ms.date: 11/11/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/save-module?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Save-Module
ms.openlocfilehash: e058bff552b4460d068909f8bf4ab31b976ef978
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "94889731"
---
# <span data-ttu-id="901d4-103">Save-Module</span><span class="sxs-lookup"><span data-stu-id="901d4-103">Save-Module</span></span>

## <span data-ttu-id="901d4-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="901d4-104">SYNOPSIS</span></span>
<span data-ttu-id="901d4-105">Сохраняет модуль и его зависимости на локальном компьютере, но не устанавливает модуль.</span><span class="sxs-lookup"><span data-stu-id="901d4-105">Saves a module and its dependencies on the local computer but doesn't install the module.</span></span>

## <span data-ttu-id="901d4-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="901d4-106">SYNTAX</span></span>

### <span data-ttu-id="901d4-107">Намеандпаспараметерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="901d4-107">NameAndPathParameterSet (Default)</span></span>

```
Save-Module [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] [-Path] <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AllowPrerelease]
 [-AcceptLicense]  [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="901d4-108">намеандлитералпаспараметерсет</span><span class="sxs-lookup"><span data-stu-id="901d4-108">NameAndLiteralPathParameterSet</span></span>

```
Save-Module [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] -LiteralPath <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AllowPrerelease]
 [-AcceptLicense]  [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="901d4-109">инпутобжектандлитералпаспараметерсет</span><span class="sxs-lookup"><span data-stu-id="901d4-109">InputObjectAndLiteralPathParameterSet</span></span>

```
Save-Module [-InputObject] <PSObject[]> -LiteralPath <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AcceptLicense] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="901d4-110">инпутобжектандпаспараметерсет</span><span class="sxs-lookup"><span data-stu-id="901d4-110">InputObjectAndPathParameterSet</span></span>

```
Save-Module [-InputObject] <PSObject[]> [-Path] <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AcceptLicense] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="901d4-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="901d4-111">DESCRIPTION</span></span>

<span data-ttu-id="901d4-112">`Save-Module`Командлет загружает модуль и все зависимости из зарегистрированного репозитория.</span><span class="sxs-lookup"><span data-stu-id="901d4-112">The `Save-Module` cmdlet downloads a module and any dependencies from a registered repository.</span></span>
<span data-ttu-id="901d4-113">`Save-Module` скачивает и сохраняет самую последнюю версию модуля.</span><span class="sxs-lookup"><span data-stu-id="901d4-113">`Save-Module` downloads and saves the most current version of a module.</span></span> <span data-ttu-id="901d4-114">Файлы сохраняются по указанному пути на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="901d4-114">The files are saved to a specified path on the local computer.</span></span> <span data-ttu-id="901d4-115">Модуль не установлен, но содержимое доступно для проверки администратором.</span><span class="sxs-lookup"><span data-stu-id="901d4-115">The module isn't installed, but the contents are available for inspection by an administrator.</span></span> <span data-ttu-id="901d4-116">Сохраненный модуль можно скопировать в соответствующее `$env:PSModulePath` расположение автономного компьютера.</span><span class="sxs-lookup"><span data-stu-id="901d4-116">The saved module can then be copied into the appropriate `$env:PSModulePath` location of the offline machine.</span></span>

<span data-ttu-id="901d4-117">`Get-PSRepository` отображает зарегистрированные репозитории локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="901d4-117">`Get-PSRepository` displays the local computer's registered repositories.</span></span> <span data-ttu-id="901d4-118">`Find-Module`Для поиска в зарегистрированных репозиториях можно использовать командлет.</span><span class="sxs-lookup"><span data-stu-id="901d4-118">You can use the `Find-Module` cmdlet to search registered repositories.</span></span>

## <span data-ttu-id="901d4-119">Примеры</span><span class="sxs-lookup"><span data-stu-id="901d4-119">EXAMPLES</span></span>

### <span data-ttu-id="901d4-120">Пример 1. Сохранение модуля</span><span class="sxs-lookup"><span data-stu-id="901d4-120">Example 1: Save a module</span></span>

<span data-ttu-id="901d4-121">В этом примере модуль и его зависимости сохраняются на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="901d4-121">In this example, a module and its dependencies are saved to the local computer.</span></span>

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

<span data-ttu-id="901d4-122">`Save-Module` использует параметр **Name** для указания модуля **PowerShellGet**.</span><span class="sxs-lookup"><span data-stu-id="901d4-122">`Save-Module` uses the **Name** parameter to specify the module, **PowerShellGet**.</span></span> <span data-ttu-id="901d4-123">Параметр **path** указывает место хранения скачанного модуля.</span><span class="sxs-lookup"><span data-stu-id="901d4-123">The **Path** parameter specifies where to store the downloaded module.</span></span> <span data-ttu-id="901d4-124">Параметр **репозитория** указывает зарегистрированный репозиторий **PSGallery**.</span><span class="sxs-lookup"><span data-stu-id="901d4-124">The **Repository** parameter specifies a registered repository, **PSGallery**.</span></span> <span data-ttu-id="901d4-125">По завершении загрузки `Get-ChildItem` отображает содержимое **папки** , в которой хранятся файлы.</span><span class="sxs-lookup"><span data-stu-id="901d4-125">After the download is finished, `Get-ChildItem` displays the contents of **Path** where the files are stored.</span></span>

### <span data-ttu-id="901d4-126">Пример 2. сохранение определенной версии модуля</span><span class="sxs-lookup"><span data-stu-id="901d4-126">Example 2: Save a specific version of a module</span></span>

<span data-ttu-id="901d4-127">В этом примере показано, как использовать параметр, например **MaximumVersion**, или **RequiredVersion** , чтобы указать версию модуля.</span><span class="sxs-lookup"><span data-stu-id="901d4-127">This example shows how to use a parameter such as **MaximumVersion**, or **RequiredVersion** to specify a module version.</span></span>

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

<span data-ttu-id="901d4-128">`Save-Module` использует параметр **Name** для указания модуля **PowerShellGet**.</span><span class="sxs-lookup"><span data-stu-id="901d4-128">`Save-Module` uses the **Name** parameter to specify the module, **PowerShellGet**.</span></span> <span data-ttu-id="901d4-129">Параметр **path** указывает место хранения скачанного модуля.</span><span class="sxs-lookup"><span data-stu-id="901d4-129">The **Path** parameter specifies where to store the downloaded module.</span></span> <span data-ttu-id="901d4-130">Параметр **репозитория** указывает зарегистрированный репозиторий **PSGallery**.</span><span class="sxs-lookup"><span data-stu-id="901d4-130">The **Repository** parameter specifies a registered repository, **PSGallery**.</span></span> <span data-ttu-id="901d4-131">**MaximumVersion** указывает, что версия **2.1.0** скачана и сохранена.</span><span class="sxs-lookup"><span data-stu-id="901d4-131">**MaximumVersion** specifies that version **2.1.0** is downloaded and saved.</span></span> <span data-ttu-id="901d4-132">По завершении загрузки `Get-ChildItem` отображает содержимое **папки** , в которой хранятся файлы.</span><span class="sxs-lookup"><span data-stu-id="901d4-132">After the download is finished, `Get-ChildItem` displays the contents of **Path** where the files are stored.</span></span>

### <span data-ttu-id="901d4-133">Пример 3. Поиск и сохранение определенной версии модуля</span><span class="sxs-lookup"><span data-stu-id="901d4-133">Example 3: Find and save a specific version of a module</span></span>

<span data-ttu-id="901d4-134">В этом примере требуемая версия модуля находится в репозитории и сохраняется на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="901d4-134">In this example, a required module version is found in the repository and saved to the local computer.</span></span>

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

<span data-ttu-id="901d4-135">`Find-Module` использует параметр **Name** для указания модуля **PowerShellGet**.</span><span class="sxs-lookup"><span data-stu-id="901d4-135">`Find-Module` uses the **Name** parameter to specify the module, **PowerShellGet**.</span></span> <span data-ttu-id="901d4-136">Параметр **репозитория** указывает зарегистрированный репозиторий **PSGallery**.</span><span class="sxs-lookup"><span data-stu-id="901d4-136">The **Repository** parameter specifies a registered repository, **PSGallery**.</span></span> <span data-ttu-id="901d4-137">**RequiredVersion** указывает версию **1.6.5**.</span><span class="sxs-lookup"><span data-stu-id="901d4-137">**RequiredVersion** specifies version **1.6.5**.</span></span>

<span data-ttu-id="901d4-138">Объект отправляется по конвейеру в `Save-Module` .</span><span class="sxs-lookup"><span data-stu-id="901d4-138">The object is sent down the pipeline to `Save-Module`.</span></span> <span data-ttu-id="901d4-139">Параметр **path** указывает место хранения скачанного модуля.</span><span class="sxs-lookup"><span data-stu-id="901d4-139">The **Path** parameter specifies where to store the downloaded module.</span></span> <span data-ttu-id="901d4-140">По завершении загрузки `Get-ChildItem` отображает содержимое **папки** , в которой хранятся файлы.</span><span class="sxs-lookup"><span data-stu-id="901d4-140">After the download is finished, `Get-ChildItem` displays the contents of **Path** where the files are stored.</span></span>

## <span data-ttu-id="901d4-141">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="901d4-141">PARAMETERS</span></span>

### <span data-ttu-id="901d4-142">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="901d4-142">-AcceptLicense</span></span>

<span data-ttu-id="901d4-143">Автоматически принять лицензионное соглашение, если оно требуется для пакета.</span><span class="sxs-lookup"><span data-stu-id="901d4-143">Automatically accept the license agreement if the package requires it.</span></span>

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

### <span data-ttu-id="901d4-144">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="901d4-144">-AllowPrerelease</span></span>

<span data-ttu-id="901d4-145">Позволяет сохранить модуль, помеченный как предварительный выпуск.</span><span class="sxs-lookup"><span data-stu-id="901d4-145">Allows you to save a module marked as a prerelease.</span></span>

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

### <span data-ttu-id="901d4-146">-Confirm</span><span class="sxs-lookup"><span data-stu-id="901d4-146">-Confirm</span></span>

<span data-ttu-id="901d4-147">Запрашивает подтверждение перед запуском `Save-Module` .</span><span class="sxs-lookup"><span data-stu-id="901d4-147">Prompts you for confirmation before running the `Save-Module`.</span></span>

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

### <span data-ttu-id="901d4-148">-Credential</span><span class="sxs-lookup"><span data-stu-id="901d4-148">-Credential</span></span>

<span data-ttu-id="901d4-149">Указывает учетную запись пользователя, имеющую права на сохранение модуля.</span><span class="sxs-lookup"><span data-stu-id="901d4-149">Specifies a user account that has rights to save a module.</span></span>

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

### <span data-ttu-id="901d4-150">-Force</span><span class="sxs-lookup"><span data-stu-id="901d4-150">-Force</span></span>

<span data-ttu-id="901d4-151">Принудительное `Save-Module` выполнение без запроса подтверждения пользователя.</span><span class="sxs-lookup"><span data-stu-id="901d4-151">Forces `Save-Module` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="901d4-152">-InputObject</span><span class="sxs-lookup"><span data-stu-id="901d4-152">-InputObject</span></span>

<span data-ttu-id="901d4-153">Принимает объект **PSRepositoryItemInfo** .</span><span class="sxs-lookup"><span data-stu-id="901d4-153">Accepts a **PSRepositoryItemInfo** object.</span></span> <span data-ttu-id="901d4-154">Например, выходные данные переводятся `Find-Module` в переменную и используют эту переменную в качестве аргумента **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="901d4-154">For example, output `Find-Module` to a variable and use that variable as the **InputObject** argument.</span></span>

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

### <span data-ttu-id="901d4-155">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="901d4-155">-LiteralPath</span></span>

<span data-ttu-id="901d4-156">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="901d4-156">Specifies a path to one or more locations.</span></span> <span data-ttu-id="901d4-157">Значение параметра **LiteralPath** используется в точности так, как указано.</span><span class="sxs-lookup"><span data-stu-id="901d4-157">The value of the **LiteralPath** parameter is used exactly as entered.</span></span> <span data-ttu-id="901d4-158">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="901d4-158">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="901d4-159">Если путь содержит escape-символы, заключите их в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="901d4-159">If the path includes escape characters, enclose them in single quotation marks.</span></span> <span data-ttu-id="901d4-160">PowerShell не интерпретирует символы, заключенные в одинарные кавычки, как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="901d4-160">PowerShell does not interpret any characters enclosed in single quotation marks as escape sequences.</span></span>

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

### <span data-ttu-id="901d4-161">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="901d4-161">-MaximumVersion</span></span>

<span data-ttu-id="901d4-162">Указывает максимальную или самую новую версию модуля для сохранения.</span><span class="sxs-lookup"><span data-stu-id="901d4-162">Specifies the maximum, or newest, version of the module to save.</span></span> <span data-ttu-id="901d4-163">Параметры **MaximumVersion** и **RequiredVersion** нельзя использовать в одной команде.</span><span class="sxs-lookup"><span data-stu-id="901d4-163">The **MaximumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="901d4-164">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="901d4-164">-MinimumVersion</span></span>

<span data-ttu-id="901d4-165">Указывает минимальную версию одного модуля для сохранения.</span><span class="sxs-lookup"><span data-stu-id="901d4-165">Specifies the minimum version of a single module to save.</span></span> <span data-ttu-id="901d4-166">Этот параметр нельзя добавить, если вы пытаетесь установить несколько модулей.</span><span class="sxs-lookup"><span data-stu-id="901d4-166">You cannot add this parameter if you are attempting to install multiple modules.</span></span> <span data-ttu-id="901d4-167">Параметры **MinimumVersion** и **RequiredVersion** нельзя использовать в одной команде.</span><span class="sxs-lookup"><span data-stu-id="901d4-167">The **MinimumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="901d4-168">-Name</span><span class="sxs-lookup"><span data-stu-id="901d4-168">-Name</span></span>

<span data-ttu-id="901d4-169">Указывает массив имен модулей для сохранения.</span><span class="sxs-lookup"><span data-stu-id="901d4-169">Specifies an array of names of modules to save.</span></span>

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

### <span data-ttu-id="901d4-170">-Path</span><span class="sxs-lookup"><span data-stu-id="901d4-170">-Path</span></span>

<span data-ttu-id="901d4-171">Указывает место на локальном компьютере для хранения сохраненного модуля.</span><span class="sxs-lookup"><span data-stu-id="901d4-171">Specifies the location on the local computer to store a saved module.</span></span> <span data-ttu-id="901d4-172">Принимает подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="901d4-172">Accepts wildcard characters.</span></span>

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

### <span data-ttu-id="901d4-173">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="901d4-173">-Proxy</span></span>

<span data-ttu-id="901d4-174">Указывает прокси-сервер для запроса, а не напрямуюе подключение к Интернет-ресурсу.</span><span class="sxs-lookup"><span data-stu-id="901d4-174">Specifies a proxy server for the request, rather than connecting directly to the internet resource.</span></span>

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

### <span data-ttu-id="901d4-175">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="901d4-175">-ProxyCredential</span></span>

<span data-ttu-id="901d4-176">Указывает учетную запись пользователя, имеющую разрешение на использование прокси-сервера, который задается параметром **Proxy**.</span><span class="sxs-lookup"><span data-stu-id="901d4-176">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="901d4-177">— Репозиторий;</span><span class="sxs-lookup"><span data-stu-id="901d4-177">-Repository</span></span>

<span data-ttu-id="901d4-178">Указывает понятное имя репозитория, зарегистрированного при выполнении `Register-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="901d4-178">Specifies the friendly name of a repository that has been registered by running `Register-PSRepository`.</span></span> <span data-ttu-id="901d4-179">Используется `Get-PSRepository` для вывода зарегистрированных репозиториев.</span><span class="sxs-lookup"><span data-stu-id="901d4-179">Use `Get-PSRepository` to display registered repositories.</span></span>

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

### <span data-ttu-id="901d4-180">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="901d4-180">-RequiredVersion</span></span>

<span data-ttu-id="901d4-181">Указывает точный номер версии для сохраняемого модуля.</span><span class="sxs-lookup"><span data-stu-id="901d4-181">Specifies the exact version number of the module to save.</span></span>

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

### <span data-ttu-id="901d4-182">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="901d4-182">-WhatIf</span></span>

<span data-ttu-id="901d4-183">Показывает, что произойдет при `Save-Module` выполнении.</span><span class="sxs-lookup"><span data-stu-id="901d4-183">Shows what would happen if the `Save-Module` runs.</span></span> <span data-ttu-id="901d4-184">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="901d4-184">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="901d4-185">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="901d4-185">CommonParameters</span></span>

<span data-ttu-id="901d4-186">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="901d4-186">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="901d4-187">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="901d4-187">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="901d4-188">Входные данные</span><span class="sxs-lookup"><span data-stu-id="901d4-188">INPUTS</span></span>

## <span data-ttu-id="901d4-189">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="901d4-189">OUTPUTS</span></span>

## <span data-ttu-id="901d4-190">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="901d4-190">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="901d4-191">По состоянию на апрель 2020 коллекция PowerShell больше не поддерживает TLS-версии 1,0 и 1,1.</span><span class="sxs-lookup"><span data-stu-id="901d4-191">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="901d4-192">Если вы не используете TLS 1,2 или более поздней версии, при попытке доступа к коллекция PowerShell возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="901d4-192">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="901d4-193">Используйте следующую команду, чтобы убедиться, что используется TLS 1,2:</span><span class="sxs-lookup"><span data-stu-id="901d4-193">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="901d4-194">Дополнительные сведения см. в [объявлении](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) в блоге PowerShell.</span><span class="sxs-lookup"><span data-stu-id="901d4-194">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="901d4-195">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="901d4-195">RELATED LINKS</span></span>
