---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 11/11/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/save-module?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Save-Module
ms.openlocfilehash: df5056b4402664602409388825c8b2b8acd4e02f
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "99601886"
---
# <span data-ttu-id="0c6e7-102">Save-Module</span><span class="sxs-lookup"><span data-stu-id="0c6e7-102">Save-Module</span></span>

## <span data-ttu-id="0c6e7-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="0c6e7-103">SYNOPSIS</span></span>
<span data-ttu-id="0c6e7-104">Сохраняет модуль и его зависимости на локальном компьютере, но не устанавливает модуль.</span><span class="sxs-lookup"><span data-stu-id="0c6e7-104">Saves a module and its dependencies on the local computer but doesn't install the module.</span></span>

## <span data-ttu-id="0c6e7-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0c6e7-105">SYNTAX</span></span>

### <span data-ttu-id="0c6e7-106">Намеандпаспараметерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="0c6e7-106">NameAndPathParameterSet (Default)</span></span>

```
Save-Module [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] [-Path] <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AllowPrerelease]
 [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0c6e7-107">намеандлитералпаспараметерсет</span><span class="sxs-lookup"><span data-stu-id="0c6e7-107">NameAndLiteralPathParameterSet</span></span>

```
Save-Module [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] -LiteralPath <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AllowPrerelease]
 [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0c6e7-108">инпутобжектандлитералпаспараметерсет</span><span class="sxs-lookup"><span data-stu-id="0c6e7-108">InputObjectAndLiteralPathParameterSet</span></span>

```
Save-Module [-InputObject] <PSObject[]> -LiteralPath <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AcceptLicense] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0c6e7-109">инпутобжектандпаспараметерсет</span><span class="sxs-lookup"><span data-stu-id="0c6e7-109">InputObjectAndPathParameterSet</span></span>

```
Save-Module [-InputObject] <PSObject[]> [-Path] <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AcceptLicense] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="0c6e7-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0c6e7-110">DESCRIPTION</span></span>

<span data-ttu-id="0c6e7-111">`Save-Module`Командлет загружает модуль и все зависимости из зарегистрированного репозитория.</span><span class="sxs-lookup"><span data-stu-id="0c6e7-111">The `Save-Module` cmdlet downloads a module and any dependencies from a registered repository.</span></span>
<span data-ttu-id="0c6e7-112">`Save-Module` скачивает и сохраняет самую последнюю версию модуля.</span><span class="sxs-lookup"><span data-stu-id="0c6e7-112">`Save-Module` downloads and saves the most current version of a module.</span></span> <span data-ttu-id="0c6e7-113">Файлы сохраняются по указанному пути на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="0c6e7-113">The files are saved to a specified path on the local computer.</span></span> <span data-ttu-id="0c6e7-114">Модуль не установлен, но содержимое доступно для проверки администратором.</span><span class="sxs-lookup"><span data-stu-id="0c6e7-114">The module isn't installed, but the contents are available for inspection by an administrator.</span></span> <span data-ttu-id="0c6e7-115">Сохраненный модуль можно скопировать в соответствующее `$env:PSModulePath` расположение автономного компьютера.</span><span class="sxs-lookup"><span data-stu-id="0c6e7-115">The saved module can then be copied into the appropriate `$env:PSModulePath` location of the offline machine.</span></span>

<span data-ttu-id="0c6e7-116">`Get-PSRepository` отображает зарегистрированные репозитории локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="0c6e7-116">`Get-PSRepository` displays the local computer's registered repositories.</span></span> <span data-ttu-id="0c6e7-117">`Find-Module`Для поиска в зарегистрированных репозиториях можно использовать командлет.</span><span class="sxs-lookup"><span data-stu-id="0c6e7-117">You can use the `Find-Module` cmdlet to search registered repositories.</span></span>

## <span data-ttu-id="0c6e7-118">Примеры</span><span class="sxs-lookup"><span data-stu-id="0c6e7-118">EXAMPLES</span></span>

### <span data-ttu-id="0c6e7-119">Пример 1. Сохранение модуля</span><span class="sxs-lookup"><span data-stu-id="0c6e7-119">Example 1: Save a module</span></span>

<span data-ttu-id="0c6e7-120">В этом примере модуль и его зависимости сохраняются на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="0c6e7-120">In this example, a module and its dependencies are saved to the local computer.</span></span>

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

<span data-ttu-id="0c6e7-121">`Save-Module` использует параметр **Name** для указания модуля **PowerShellGet**.</span><span class="sxs-lookup"><span data-stu-id="0c6e7-121">`Save-Module` uses the **Name** parameter to specify the module, **PowerShellGet**.</span></span> <span data-ttu-id="0c6e7-122">Параметр **path** указывает место хранения скачанного модуля.</span><span class="sxs-lookup"><span data-stu-id="0c6e7-122">The **Path** parameter specifies where to store the downloaded module.</span></span> <span data-ttu-id="0c6e7-123">Параметр **репозитория** указывает зарегистрированный репозиторий **PSGallery**.</span><span class="sxs-lookup"><span data-stu-id="0c6e7-123">The **Repository** parameter specifies a registered repository, **PSGallery**.</span></span> <span data-ttu-id="0c6e7-124">По завершении загрузки `Get-ChildItem` отображает содержимое **папки** , в которой хранятся файлы.</span><span class="sxs-lookup"><span data-stu-id="0c6e7-124">After the download is finished, `Get-ChildItem` displays the contents of **Path** where the files are stored.</span></span>

### <span data-ttu-id="0c6e7-125">Пример 2. сохранение определенной версии модуля</span><span class="sxs-lookup"><span data-stu-id="0c6e7-125">Example 2: Save a specific version of a module</span></span>

<span data-ttu-id="0c6e7-126">В этом примере показано, как использовать параметр, например **MaximumVersion**, или **RequiredVersion** , чтобы указать версию модуля.</span><span class="sxs-lookup"><span data-stu-id="0c6e7-126">This example shows how to use a parameter such as **MaximumVersion**, or **RequiredVersion** to specify a module version.</span></span>

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

<span data-ttu-id="0c6e7-127">`Save-Module` использует параметр **Name** для указания модуля **PowerShellGet**.</span><span class="sxs-lookup"><span data-stu-id="0c6e7-127">`Save-Module` uses the **Name** parameter to specify the module, **PowerShellGet**.</span></span> <span data-ttu-id="0c6e7-128">Параметр **path** указывает место хранения скачанного модуля.</span><span class="sxs-lookup"><span data-stu-id="0c6e7-128">The **Path** parameter specifies where to store the downloaded module.</span></span> <span data-ttu-id="0c6e7-129">Параметр **репозитория** указывает зарегистрированный репозиторий **PSGallery**.</span><span class="sxs-lookup"><span data-stu-id="0c6e7-129">The **Repository** parameter specifies a registered repository, **PSGallery**.</span></span> <span data-ttu-id="0c6e7-130">**MaximumVersion** указывает, что версия **2.1.0** скачана и сохранена.</span><span class="sxs-lookup"><span data-stu-id="0c6e7-130">**MaximumVersion** specifies that version **2.1.0** is downloaded and saved.</span></span> <span data-ttu-id="0c6e7-131">По завершении загрузки `Get-ChildItem` отображает содержимое **папки** , в которой хранятся файлы.</span><span class="sxs-lookup"><span data-stu-id="0c6e7-131">After the download is finished, `Get-ChildItem` displays the contents of **Path** where the files are stored.</span></span>

### <span data-ttu-id="0c6e7-132">Пример 3. Поиск и сохранение определенной версии модуля</span><span class="sxs-lookup"><span data-stu-id="0c6e7-132">Example 3: Find and save a specific version of a module</span></span>

<span data-ttu-id="0c6e7-133">В этом примере требуемая версия модуля находится в репозитории и сохраняется на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="0c6e7-133">In this example, a required module version is found in the repository and saved to the local computer.</span></span>

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

<span data-ttu-id="0c6e7-134">`Find-Module` использует параметр **Name** для указания модуля **PowerShellGet**.</span><span class="sxs-lookup"><span data-stu-id="0c6e7-134">`Find-Module` uses the **Name** parameter to specify the module, **PowerShellGet**.</span></span> <span data-ttu-id="0c6e7-135">Параметр **репозитория** указывает зарегистрированный репозиторий **PSGallery**.</span><span class="sxs-lookup"><span data-stu-id="0c6e7-135">The **Repository** parameter specifies a registered repository, **PSGallery**.</span></span> <span data-ttu-id="0c6e7-136">**RequiredVersion** указывает версию **1.6.5**.</span><span class="sxs-lookup"><span data-stu-id="0c6e7-136">**RequiredVersion** specifies version **1.6.5**.</span></span>

<span data-ttu-id="0c6e7-137">Объект отправляется по конвейеру в `Save-Module` .</span><span class="sxs-lookup"><span data-stu-id="0c6e7-137">The object is sent down the pipeline to `Save-Module`.</span></span> <span data-ttu-id="0c6e7-138">Параметр **path** указывает место хранения скачанного модуля.</span><span class="sxs-lookup"><span data-stu-id="0c6e7-138">The **Path** parameter specifies where to store the downloaded module.</span></span> <span data-ttu-id="0c6e7-139">По завершении загрузки `Get-ChildItem` отображает содержимое **папки** , в которой хранятся файлы.</span><span class="sxs-lookup"><span data-stu-id="0c6e7-139">After the download is finished, `Get-ChildItem` displays the contents of **Path** where the files are stored.</span></span>

## <span data-ttu-id="0c6e7-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0c6e7-140">PARAMETERS</span></span>

### <span data-ttu-id="0c6e7-141">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="0c6e7-141">-AcceptLicense</span></span>

<span data-ttu-id="0c6e7-142">Автоматически принять лицензионное соглашение, если оно требуется для пакета.</span><span class="sxs-lookup"><span data-stu-id="0c6e7-142">Automatically accept the license agreement if the package requires it.</span></span>

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

### <span data-ttu-id="0c6e7-143">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="0c6e7-143">-AllowPrerelease</span></span>

<span data-ttu-id="0c6e7-144">Позволяет сохранить модуль, помеченный как предварительный выпуск.</span><span class="sxs-lookup"><span data-stu-id="0c6e7-144">Allows you to save a module marked as a prerelease.</span></span>

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

### <span data-ttu-id="0c6e7-145">-Confirm</span><span class="sxs-lookup"><span data-stu-id="0c6e7-145">-Confirm</span></span>

<span data-ttu-id="0c6e7-146">Запрашивает подтверждение перед запуском `Save-Module` .</span><span class="sxs-lookup"><span data-stu-id="0c6e7-146">Prompts you for confirmation before running the `Save-Module`.</span></span>

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

### <span data-ttu-id="0c6e7-147">-Credential</span><span class="sxs-lookup"><span data-stu-id="0c6e7-147">-Credential</span></span>

<span data-ttu-id="0c6e7-148">Указывает учетную запись пользователя, имеющую права на сохранение модуля.</span><span class="sxs-lookup"><span data-stu-id="0c6e7-148">Specifies a user account that has rights to save a module.</span></span>

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

### <span data-ttu-id="0c6e7-149">-Force</span><span class="sxs-lookup"><span data-stu-id="0c6e7-149">-Force</span></span>

<span data-ttu-id="0c6e7-150">Принудительное `Save-Module` выполнение без запроса подтверждения пользователя.</span><span class="sxs-lookup"><span data-stu-id="0c6e7-150">Forces `Save-Module` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="0c6e7-151">-InputObject</span><span class="sxs-lookup"><span data-stu-id="0c6e7-151">-InputObject</span></span>

<span data-ttu-id="0c6e7-152">Принимает объект **PSRepositoryItemInfo** .</span><span class="sxs-lookup"><span data-stu-id="0c6e7-152">Accepts a **PSRepositoryItemInfo** object.</span></span> <span data-ttu-id="0c6e7-153">Например, выходные данные переводятся `Find-Module` в переменную и используют эту переменную в качестве аргумента **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="0c6e7-153">For example, output `Find-Module` to a variable and use that variable as the **InputObject** argument.</span></span>

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

### <span data-ttu-id="0c6e7-154">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="0c6e7-154">-LiteralPath</span></span>

<span data-ttu-id="0c6e7-155">Указывает путь к одному или нескольким расположениям.</span><span class="sxs-lookup"><span data-stu-id="0c6e7-155">Specifies a path to one or more locations.</span></span> <span data-ttu-id="0c6e7-156">Значение параметра **LiteralPath** используется в точности так, как указано.</span><span class="sxs-lookup"><span data-stu-id="0c6e7-156">The value of the **LiteralPath** parameter is used exactly as entered.</span></span> <span data-ttu-id="0c6e7-157">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="0c6e7-157">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="0c6e7-158">Если путь содержит escape-символы, заключите их в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="0c6e7-158">If the path includes escape characters, enclose them in single quotation marks.</span></span> <span data-ttu-id="0c6e7-159">PowerShell не интерпретирует символы, заключенные в одинарные кавычки, как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="0c6e7-159">PowerShell does not interpret any characters enclosed in single quotation marks as escape sequences.</span></span>

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

### <span data-ttu-id="0c6e7-160">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="0c6e7-160">-MaximumVersion</span></span>

<span data-ttu-id="0c6e7-161">Указывает максимальную или самую новую версию модуля для сохранения.</span><span class="sxs-lookup"><span data-stu-id="0c6e7-161">Specifies the maximum, or newest, version of the module to save.</span></span> <span data-ttu-id="0c6e7-162">Параметры **MaximumVersion** и **RequiredVersion** нельзя использовать в одной команде.</span><span class="sxs-lookup"><span data-stu-id="0c6e7-162">The **MaximumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="0c6e7-163">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="0c6e7-163">-MinimumVersion</span></span>

<span data-ttu-id="0c6e7-164">Указывает минимальную версию одного модуля для сохранения.</span><span class="sxs-lookup"><span data-stu-id="0c6e7-164">Specifies the minimum version of a single module to save.</span></span> <span data-ttu-id="0c6e7-165">Этот параметр нельзя добавить, если вы пытаетесь установить несколько модулей.</span><span class="sxs-lookup"><span data-stu-id="0c6e7-165">You cannot add this parameter if you are attempting to install multiple modules.</span></span> <span data-ttu-id="0c6e7-166">Параметры **MinimumVersion** и **RequiredVersion** нельзя использовать в одной команде.</span><span class="sxs-lookup"><span data-stu-id="0c6e7-166">The **MinimumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="0c6e7-167">-Name</span><span class="sxs-lookup"><span data-stu-id="0c6e7-167">-Name</span></span>

<span data-ttu-id="0c6e7-168">Указывает массив имен модулей для сохранения.</span><span class="sxs-lookup"><span data-stu-id="0c6e7-168">Specifies an array of names of modules to save.</span></span>

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

### <span data-ttu-id="0c6e7-169">-Path</span><span class="sxs-lookup"><span data-stu-id="0c6e7-169">-Path</span></span>

<span data-ttu-id="0c6e7-170">Указывает место на локальном компьютере для хранения сохраненного модуля.</span><span class="sxs-lookup"><span data-stu-id="0c6e7-170">Specifies the location on the local computer to store a saved module.</span></span> <span data-ttu-id="0c6e7-171">Принимает подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="0c6e7-171">Accepts wildcard characters.</span></span>

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

### <span data-ttu-id="0c6e7-172">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="0c6e7-172">-Proxy</span></span>

<span data-ttu-id="0c6e7-173">Указывает прокси-сервер для запроса, а не напрямуюе подключение к Интернет-ресурсу.</span><span class="sxs-lookup"><span data-stu-id="0c6e7-173">Specifies a proxy server for the request, rather than connecting directly to the internet resource.</span></span>

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

### <span data-ttu-id="0c6e7-174">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="0c6e7-174">-ProxyCredential</span></span>

<span data-ttu-id="0c6e7-175">Указывает учетную запись пользователя, имеющую разрешение на использование прокси-сервера, который задается параметром **Proxy**.</span><span class="sxs-lookup"><span data-stu-id="0c6e7-175">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="0c6e7-176">— Репозиторий;</span><span class="sxs-lookup"><span data-stu-id="0c6e7-176">-Repository</span></span>

<span data-ttu-id="0c6e7-177">Указывает понятное имя репозитория, зарегистрированного при выполнении `Register-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="0c6e7-177">Specifies the friendly name of a repository that has been registered by running `Register-PSRepository`.</span></span> <span data-ttu-id="0c6e7-178">Используется `Get-PSRepository` для вывода зарегистрированных репозиториев.</span><span class="sxs-lookup"><span data-stu-id="0c6e7-178">Use `Get-PSRepository` to display registered repositories.</span></span>

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

### <span data-ttu-id="0c6e7-179">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="0c6e7-179">-RequiredVersion</span></span>

<span data-ttu-id="0c6e7-180">Указывает точный номер версии для сохраняемого модуля.</span><span class="sxs-lookup"><span data-stu-id="0c6e7-180">Specifies the exact version number of the module to save.</span></span>

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

### <span data-ttu-id="0c6e7-181">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="0c6e7-181">-WhatIf</span></span>

<span data-ttu-id="0c6e7-182">Показывает, что произойдет при `Save-Module` выполнении.</span><span class="sxs-lookup"><span data-stu-id="0c6e7-182">Shows what would happen if the `Save-Module` runs.</span></span> <span data-ttu-id="0c6e7-183">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="0c6e7-183">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="0c6e7-184">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="0c6e7-184">CommonParameters</span></span>

<span data-ttu-id="0c6e7-185">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0c6e7-185">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0c6e7-186">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0c6e7-186">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0c6e7-187">Входные данные</span><span class="sxs-lookup"><span data-stu-id="0c6e7-187">INPUTS</span></span>

### <span data-ttu-id="0c6e7-188">System.String[]</span><span class="sxs-lookup"><span data-stu-id="0c6e7-188">System.String[]</span></span>

### <span data-ttu-id="0c6e7-189">System. Management. Automation. PSObject []</span><span class="sxs-lookup"><span data-stu-id="0c6e7-189">System.Management.Automation.PSObject[]</span></span>

### <span data-ttu-id="0c6e7-190">System.String</span><span class="sxs-lookup"><span data-stu-id="0c6e7-190">System.String</span></span>

### <span data-ttu-id="0c6e7-191">System.Uri</span><span class="sxs-lookup"><span data-stu-id="0c6e7-191">System.Uri</span></span>

### <span data-ttu-id="0c6e7-192">System.Management.Automation.PSCredential</span><span class="sxs-lookup"><span data-stu-id="0c6e7-192">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="0c6e7-193">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="0c6e7-193">OUTPUTS</span></span>

### <span data-ttu-id="0c6e7-194">System.Object</span><span class="sxs-lookup"><span data-stu-id="0c6e7-194">System.Object</span></span>

## <span data-ttu-id="0c6e7-195">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="0c6e7-195">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0c6e7-196">Начиная с апреля 2020 года коллекция PowerShell не поддерживает протокол TLS (Transport Layer Security) версий 1.0 и 1.1.</span><span class="sxs-lookup"><span data-stu-id="0c6e7-196">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="0c6e7-197">Если вы не используете TLS 1.2 или более поздней версии, при попытке доступа к коллекции PowerShell возникнет ошибка.</span><span class="sxs-lookup"><span data-stu-id="0c6e7-197">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="0c6e7-198">Чтобы проверить, используется ли TLS 1.2, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0c6e7-198">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="0c6e7-199">Дополнительные сведения см. в [объявлении](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) в блоге, посвященном PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0c6e7-199">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="0c6e7-200">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="0c6e7-200">RELATED LINKS</span></span>
