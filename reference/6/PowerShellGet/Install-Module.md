---
external help file: PSModule-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PowerShellGet
ms.date: 08/03/2020
online version: https://docs.microsoft.com/powershell/module/powershellget/install-module?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Install-Module
ms.openlocfilehash: 67d68427ba8e3c305b50ccbc19c6d48d574e3351
ms.sourcegitcommit: 4fc8cf397cb725ae973751d1d5d542f34f0db2d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/03/2020
ms.locfileid: "93230217"
---
# <span data-ttu-id="351db-103">Install-Module</span><span class="sxs-lookup"><span data-stu-id="351db-103">Install-Module</span></span>

## <span data-ttu-id="351db-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="351db-104">SYNOPSIS</span></span>
<span data-ttu-id="351db-105">Скачивает один или несколько модулей из репозитория и устанавливает их на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="351db-105">Downloads one or more modules from a repository, and installs them on the local computer.</span></span>

## <span data-ttu-id="351db-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="351db-106">SYNTAX</span></span>

### <span data-ttu-id="351db-107">NameParameterSet (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="351db-107">NameParameterSet (Default)</span></span>

```
Install-Module [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] [-Credential <PSCredential>] [-Scope <String>]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-AllowClobber] [-SkipPublisherCheck] [-Force]
 [-AllowPrerelease] [-AcceptLicense] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="351db-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="351db-108">InputObject</span></span>

```
Install-Module [-InputObject] <PSObject[]> [-Credential <PSCredential>] [-Scope <String>]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-AllowClobber] [-SkipPublisherCheck] [-Force]
 [-AcceptLicense] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="351db-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="351db-109">DESCRIPTION</span></span>

<span data-ttu-id="351db-110">`Install-Module`Командлет возвращает один или несколько модулей, соответствующих указанным критериям из Интернет-репозитория.</span><span class="sxs-lookup"><span data-stu-id="351db-110">The `Install-Module` cmdlet gets one or more modules that meet specified criteria from an online repository.</span></span> <span data-ttu-id="351db-111">Командлет проверяет, что результаты поиска являются допустимыми модулями, и копирует папки модулей в расположение установки.</span><span class="sxs-lookup"><span data-stu-id="351db-111">The cmdlet verifies that search results are valid modules and copies the module folders to the installation location.</span></span> <span data-ttu-id="351db-112">Установленные модули не импортируются автоматически после установки.</span><span class="sxs-lookup"><span data-stu-id="351db-112">Installed modules are not automatically imported after installation.</span></span>
<span data-ttu-id="351db-113">Вы можете отфильтровать, какой модуль установлен на основе минимальной, максимальной и точной версий указанных модулей.</span><span class="sxs-lookup"><span data-stu-id="351db-113">You can filter which module is installed based on the minimum, maximum, and exact versions of specified modules.</span></span>

<span data-ttu-id="351db-114">Если устанавливаемый модуль имеет то же имя или версию или содержит команды в существующем модуле, отображаются предупреждающие сообщения.</span><span class="sxs-lookup"><span data-stu-id="351db-114">If the module being installed has the same name or version, or contains commands in an existing module, warning messages are displayed.</span></span> <span data-ttu-id="351db-115">Убедившись, что вы хотите установить модуль и переопределить предупреждения, используйте `-Force` `-AllowClobber` Параметры и.</span><span class="sxs-lookup"><span data-stu-id="351db-115">After you confirm that you want to install the module and override the warnings, use the `-Force` and `-AllowClobber` parameters.</span></span> <span data-ttu-id="351db-116">В зависимости от параметров репозитория может потребоваться ответить на запрос установки модуля, чтобы продолжить.</span><span class="sxs-lookup"><span data-stu-id="351db-116">Dependent upon your repository settings, you might need to answer a prompt for the module installation to continue.</span></span>

<span data-ttu-id="351db-117">В этих примерах используется [коллекция PowerShell](https://www.powershellgallery.com/) в качестве единственного зарегистрированного репозитория.</span><span class="sxs-lookup"><span data-stu-id="351db-117">These examples use the [PowerShell Gallery](https://www.powershellgallery.com/) as the only registered repository.</span></span> <span data-ttu-id="351db-118">`Get-PSRepository` отображает зарегистрированные репозитории.</span><span class="sxs-lookup"><span data-stu-id="351db-118">`Get-PSRepository` displays the registered repositories.</span></span> <span data-ttu-id="351db-119">Если у вас есть несколько зарегистрированных репозиториев, используйте `-Repository` параметр, чтобы указать имя репозитория.</span><span class="sxs-lookup"><span data-stu-id="351db-119">If you have multiple registered repositories, use the `-Repository` parameter to specify the repository's name.</span></span>

## <span data-ttu-id="351db-120">Примеры</span><span class="sxs-lookup"><span data-stu-id="351db-120">EXAMPLES</span></span>

### <span data-ttu-id="351db-121">Пример 1. Поиск и установка модуля</span><span class="sxs-lookup"><span data-stu-id="351db-121">Example 1: Find and install a module</span></span>

<span data-ttu-id="351db-122">В этом примере выполняется поиск модуля в репозитории и установка модуля.</span><span class="sxs-lookup"><span data-stu-id="351db-122">This example finds a module in the repository and installs the module.</span></span>

```powershell
Find-Module -Name PowerShellGet | Install-Module
```

<span data-ttu-id="351db-123">`Find-Module`Использует параметр **Name** для указания модуля **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="351db-123">The `Find-Module` uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="351db-124">По умолчанию последняя версия модуля загружается из репозитория.</span><span class="sxs-lookup"><span data-stu-id="351db-124">By default, the newest version of the module is downloaded from the repository.</span></span> <span data-ttu-id="351db-125">Объект отправляется по конвейеру в `Install-Module` командлет.</span><span class="sxs-lookup"><span data-stu-id="351db-125">The object is sent down the pipeline to the `Install-Module` cmdlet.</span></span> <span data-ttu-id="351db-126">`Install-Module` устанавливает модуль для всех пользователей в `$env:ProgramFiles\PowerShell\Modules` .</span><span class="sxs-lookup"><span data-stu-id="351db-126">`Install-Module` installs the module for all users in `$env:ProgramFiles\PowerShell\Modules`.</span></span>

### <span data-ttu-id="351db-127">Пример 2. Установка модуля по имени</span><span class="sxs-lookup"><span data-stu-id="351db-127">Example 2: Install a module by name</span></span>

<span data-ttu-id="351db-128">В этом примере установлена последняя версия модуля **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="351db-128">In this example, the newest version of the **PowerShellGet** module is installed.</span></span>

```powershell
Install-Module -Name PowerShellGet
```

<span data-ttu-id="351db-129">`Install-Module`Использует параметр **Name** для указания модуля **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="351db-129">The `Install-Module` uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="351db-130">По умолчанию последняя версия модуля загружается из репозитория и устанавливается.</span><span class="sxs-lookup"><span data-stu-id="351db-130">By default, the newest version of the module is downloaded from the repository and installed.</span></span>

### <span data-ttu-id="351db-131">Пример 3. Установка модуля с использованием минимальной версии</span><span class="sxs-lookup"><span data-stu-id="351db-131">Example 3: Install a module using its minimum version</span></span>

<span data-ttu-id="351db-132">В этом примере устанавливается минимальная версия модуля **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="351db-132">In this example, the minimum version of the **PowerShellGet** module is installed.</span></span> <span data-ttu-id="351db-133">Параметр **MinimumVersion** указывает самую раннюю версию модуля, который следует установить.</span><span class="sxs-lookup"><span data-stu-id="351db-133">The **MinimumVersion** parameter specifies the lowest version of the module that should be installed.</span></span> <span data-ttu-id="351db-134">Если доступна более новая версия модуля, эта версия скачивается и устанавливается для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="351db-134">If a newer version of the module is available, that version is downloaded and installed for all users.</span></span>

```powershell
Install-Module -Name PowerShellGet -MinimumVersion 2.0.1
```

<span data-ttu-id="351db-135">`Install-Module`Использует параметр **Name** для указания модуля **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="351db-135">The `Install-Module` uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="351db-136">Параметр **MinimumVersion** указывает, что версия **2.0.1** загружается из репозитория и устанавливается.</span><span class="sxs-lookup"><span data-stu-id="351db-136">The **MinimumVersion** parameter specifies that version **2.0.1** is downloaded from the repository and installed.</span></span> <span data-ttu-id="351db-137">Так как доступна версия **2.0.4** , эта версия скачивается и устанавливается для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="351db-137">Because version **2.0.4** is available, that version is downloaded and installed for all users.</span></span>

### <span data-ttu-id="351db-138">Пример 4. Установка определенной версии модуля</span><span class="sxs-lookup"><span data-stu-id="351db-138">Example 4: Install a specific version of a module</span></span>

<span data-ttu-id="351db-139">В этом примере устанавливается определенная версия модуля **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="351db-139">In this example, a specific version of the **PowerShellGet** module is installed.</span></span>

```powershell
Install-Module -Name PowerShellGet -RequiredVersion 2.0.0
```

<span data-ttu-id="351db-140">`Install-Module`Использует параметр **Name** для указания модуля **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="351db-140">The `Install-Module` uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="351db-141">Параметр **RequiredVersion** указывает, что версия **2.0.0** скачивается и устанавливается для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="351db-141">The **RequiredVersion** parameter specifies that version **2.0.0** is downloaded and installed for all users.</span></span>

### <span data-ttu-id="351db-142">Пример 5. Установка модуля только для текущего пользователя</span><span class="sxs-lookup"><span data-stu-id="351db-142">Example 5: Install a module only for the current user</span></span>

<span data-ttu-id="351db-143">В этом примере загружается и устанавливается последняя версия модуля только для текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="351db-143">This example downloads and installs the newest version of a module, only for the current user.</span></span>

```powershell
Install-Module -Name PowerShellGet -Scope CurrentUser
```

<span data-ttu-id="351db-144">`Install-Module`Использует параметр **Name** для указания модуля **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="351db-144">The `Install-Module` uses the **Name** parameter to specify the **PowerShellGet** module.</span></span>
<span data-ttu-id="351db-145">`Install-Module` скачивает и устанавливает последнюю версию **PowerShellGet** в каталог текущего пользователя `$home\Documents\PowerShell\Modules` .</span><span class="sxs-lookup"><span data-stu-id="351db-145">`Install-Module` downloads and installs the newest version of **PowerShellGet** into the current user's directory, `$home\Documents\PowerShell\Modules`.</span></span>

## <span data-ttu-id="351db-146">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="351db-146">PARAMETERS</span></span>

### <span data-ttu-id="351db-147">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="351db-147">-AcceptLicense</span></span>

<span data-ttu-id="351db-148">Для модулей, для которых требуется лицензия, **AcceptLicense** автоматически принимает лицензионное соглашение во время установки.</span><span class="sxs-lookup"><span data-stu-id="351db-148">For modules that require a license, **AcceptLicense** automatically accepts the license agreement during installation.</span></span> <span data-ttu-id="351db-149">Дополнительные сведения см. в разделе [модули, требующие принятия условий лицензии](/powershell/scripting/gallery/concepts/module-license-acceptance).</span><span class="sxs-lookup"><span data-stu-id="351db-149">For more information, see [Modules Requiring License Acceptance](/powershell/scripting/gallery/concepts/module-license-acceptance).</span></span>

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

### <span data-ttu-id="351db-150">-AllowClobber</span><span class="sxs-lookup"><span data-stu-id="351db-150">-AllowClobber</span></span>

<span data-ttu-id="351db-151">Переопределяет предупреждающие сообщения о конфликтах установки существующих команд на компьютере.</span><span class="sxs-lookup"><span data-stu-id="351db-151">Overrides warning messages about installation conflicts about existing commands on a computer.</span></span>
<span data-ttu-id="351db-152">Перезаписывает существующие команды, имена которых совпадают с именами команд, устанавливаемых модулем.</span><span class="sxs-lookup"><span data-stu-id="351db-152">Overwrites existing commands that have the same name as commands being installed by a module.</span></span>
<span data-ttu-id="351db-153">**AllowClobber** и **Force** можно использовать вместе в `Install-Module` команде.</span><span class="sxs-lookup"><span data-stu-id="351db-153">**AllowClobber** and **Force** can be used together in an `Install-Module` command.</span></span>

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

### <span data-ttu-id="351db-154">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="351db-154">-AllowPrerelease</span></span>

<span data-ttu-id="351db-155">Позволяет установить модуль, помеченный как предварительный выпуск.</span><span class="sxs-lookup"><span data-stu-id="351db-155">Allows you to install a module marked as a pre-release.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="351db-156">-Confirm</span><span class="sxs-lookup"><span data-stu-id="351db-156">-Confirm</span></span>

<span data-ttu-id="351db-157">Запрашивает подтверждение перед запуском `Install-Module` командлета.</span><span class="sxs-lookup"><span data-stu-id="351db-157">Prompts you for confirmation before running the `Install-Module` cmdlet.</span></span>

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

### <span data-ttu-id="351db-158">-Credential</span><span class="sxs-lookup"><span data-stu-id="351db-158">-Credential</span></span>

<span data-ttu-id="351db-159">Указывает учетную запись пользователя, имеющую права на установку модуля для указанного поставщика пакетов или источника.</span><span class="sxs-lookup"><span data-stu-id="351db-159">Specifies a user account that has rights to install a module for a specified package provider or source.</span></span>

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

### <span data-ttu-id="351db-160">-Force</span><span class="sxs-lookup"><span data-stu-id="351db-160">-Force</span></span>

<span data-ttu-id="351db-161">Устанавливает модуль и переопределяет предупреждающие сообщения о конфликтах при установке модулей.</span><span class="sxs-lookup"><span data-stu-id="351db-161">Installs a module and overrides warning messages about module installation conflicts.</span></span> <span data-ttu-id="351db-162">Если на компьютере уже существует модуль с таким именем, **принудительно** установите несколько версий.</span><span class="sxs-lookup"><span data-stu-id="351db-162">If a module with the same name already exists on the computer, **Force** allows for multiple versions to be installed.</span></span> <span data-ttu-id="351db-163">Если имеется существующий модуль с тем же именем и версией, **принудительно** перезаписывает эту версию.</span><span class="sxs-lookup"><span data-stu-id="351db-163">If there is an existing module with the same name and version, **Force** overwrites that version.</span></span> <span data-ttu-id="351db-164">**Force** и **AllowClobber** можно использовать вместе в `Install-Module` команде.</span><span class="sxs-lookup"><span data-stu-id="351db-164">**Force** and **AllowClobber** can be used together in an `Install-Module` command.</span></span>

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

### <span data-ttu-id="351db-165">-InputObject</span><span class="sxs-lookup"><span data-stu-id="351db-165">-InputObject</span></span>

<span data-ttu-id="351db-166">Используется для входных данных конвейера.</span><span class="sxs-lookup"><span data-stu-id="351db-166">Used for pipeline input.</span></span>

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="351db-167">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="351db-167">-MaximumVersion</span></span>

<span data-ttu-id="351db-168">Указывает максимальную версию одного модуля для установки.</span><span class="sxs-lookup"><span data-stu-id="351db-168">Specifies the maximum version of a single module to install.</span></span> <span data-ttu-id="351db-169">Установленная версия должна быть меньше или равна **MaximumVersion** .</span><span class="sxs-lookup"><span data-stu-id="351db-169">The version installed must be less than or equal to **MaximumVersion** .</span></span> <span data-ttu-id="351db-170">Если вы хотите установить несколько модулей, вы не сможете использовать **MaximumVersion** .</span><span class="sxs-lookup"><span data-stu-id="351db-170">If you want to install multiple modules, you cannot use **MaximumVersion** .</span></span> <span data-ttu-id="351db-171">В одной команде нельзя использовать **MaximumVersion** и **RequiredVersion** `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="351db-171">**MaximumVersion** and **RequiredVersion** cannot be used in the same `Install-Module` command.</span></span>

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="351db-172">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="351db-172">-MinimumVersion</span></span>

<span data-ttu-id="351db-173">Указывает минимальную версию отдельного модуля для установки.</span><span class="sxs-lookup"><span data-stu-id="351db-173">Specifies the minimum version of a single module to install.</span></span> <span data-ttu-id="351db-174">Установленная версия должна быть больше или равна **MinimumVersion** .</span><span class="sxs-lookup"><span data-stu-id="351db-174">The version installed must be greater than or equal to **MinimumVersion** .</span></span> <span data-ttu-id="351db-175">Если доступен более новая версия модуля, устанавливается более новая версия.</span><span class="sxs-lookup"><span data-stu-id="351db-175">If there is a newer version of the module available, the newer version is installed.</span></span> <span data-ttu-id="351db-176">Если требуется установить несколько модулей, нельзя использовать параметр **MinimumVersion** .</span><span class="sxs-lookup"><span data-stu-id="351db-176">If you want to install multiple modules, you cannot use **MinimumVersion** .</span></span>
<span data-ttu-id="351db-177">В одной команде нельзя использовать **MinimumVersion** и **RequiredVersion** `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="351db-177">**MinimumVersion** and **RequiredVersion** cannot be used in the same `Install-Module` command.</span></span>

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="351db-178">-Name</span><span class="sxs-lookup"><span data-stu-id="351db-178">-Name</span></span>

<span data-ttu-id="351db-179">Указывает точные имена модулей для установки из Интернет-коллекции.</span><span class="sxs-lookup"><span data-stu-id="351db-179">Specifies the exact names of modules to install from the online gallery.</span></span> <span data-ttu-id="351db-180">Принимается список имен модулей с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="351db-180">A comma-separated list of module names is accepted.</span></span> <span data-ttu-id="351db-181">Имя модуля должно совпадать с именем модуля в репозитории.</span><span class="sxs-lookup"><span data-stu-id="351db-181">The module name must match the module name in the repository.</span></span> <span data-ttu-id="351db-182">Используйте `Find-Module` для получения списка имен модулей.</span><span class="sxs-lookup"><span data-stu-id="351db-182">Use `Find-Module` to get a list of module names.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="351db-183">-PassThru</span><span class="sxs-lookup"><span data-stu-id="351db-183">-PassThru</span></span>

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

### <span data-ttu-id="351db-184">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="351db-184">-Proxy</span></span>

<span data-ttu-id="351db-185">Указывает прокси-сервер для запроса, а не напрямуюе подключение к Интернет-ресурсу.</span><span class="sxs-lookup"><span data-stu-id="351db-185">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

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

### <span data-ttu-id="351db-186">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="351db-186">-ProxyCredential</span></span>

<span data-ttu-id="351db-187">Указывает учетную запись пользователя, имеющую разрешение на использование прокси-сервера, который задается параметром **Proxy** .</span><span class="sxs-lookup"><span data-stu-id="351db-187">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="351db-188">— Репозиторий;</span><span class="sxs-lookup"><span data-stu-id="351db-188">-Repository</span></span>

<span data-ttu-id="351db-189">Используйте параметр **репозитория** , чтобы указать, какой репозиторий используется для скачивания и установки модуля.</span><span class="sxs-lookup"><span data-stu-id="351db-189">Use the **Repository** parameter to specify which repository is used to download and install a module.</span></span> <span data-ttu-id="351db-190">Используется при регистрации нескольких репозиториев.</span><span class="sxs-lookup"><span data-stu-id="351db-190">Used when multiple repositories are registered.</span></span> <span data-ttu-id="351db-191">Указывает имя зарегистрированного репозитория в `Install-Module` команде.</span><span class="sxs-lookup"><span data-stu-id="351db-191">Specifies the name of a registered repository in the `Install-Module` command.</span></span> <span data-ttu-id="351db-192">Чтобы зарегистрировать репозиторий, используйте `Register-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="351db-192">To register a repository, use `Register-PSRepository`.</span></span>
<span data-ttu-id="351db-193">Чтобы отобразить зарегистрированные репозитории, используйте `Get-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="351db-193">To display registered repositories, use `Get-PSRepository`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="351db-194">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="351db-194">-RequiredVersion</span></span>

<span data-ttu-id="351db-195">Указывает точную версию отдельного модуля для установки.</span><span class="sxs-lookup"><span data-stu-id="351db-195">Specifies the exact version of a single module to install.</span></span> <span data-ttu-id="351db-196">Если в репозитории для указанной версии нет совпадения, выводится сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="351db-196">If there is no match in the repository for the specified version, an error is displayed.</span></span> <span data-ttu-id="351db-197">Если требуется установить несколько модулей, нельзя использовать **RequiredVersion** .</span><span class="sxs-lookup"><span data-stu-id="351db-197">If you want to install multiple modules, you cannot use **RequiredVersion** .</span></span> <span data-ttu-id="351db-198">Параметр **RequiredVersion** нельзя использовать в той же `Install-Module` команде, что и **MinimumVersion** или **MaximumVersion** .</span><span class="sxs-lookup"><span data-stu-id="351db-198">**RequiredVersion** cannot be used in the same `Install-Module` command as **MinimumVersion** or **MaximumVersion** .</span></span>

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="351db-199">-Scope</span><span class="sxs-lookup"><span data-stu-id="351db-199">-Scope</span></span>

<span data-ttu-id="351db-200">Задает область установки модуля.</span><span class="sxs-lookup"><span data-stu-id="351db-200">Specifies the installation scope of the module.</span></span> <span data-ttu-id="351db-201">Допустимые значения для этого параметра: **ALLUSERS** и **CurrentUser** .</span><span class="sxs-lookup"><span data-stu-id="351db-201">The acceptable values for this parameter are **AllUsers** and **CurrentUser** .</span></span>

<span data-ttu-id="351db-202">Область **ALLUSERS** устанавливает модули в расположение, доступное всем пользователям компьютера:</span><span class="sxs-lookup"><span data-stu-id="351db-202">The **AllUsers** scope installs modules in a location that is accessible to all users of the computer:</span></span>

`$env:ProgramFiles\PowerShell\Modules`

<span data-ttu-id="351db-203">Параметр **CurrentUser** устанавливает модули в расположение, доступное только текущему пользователю компьютера.</span><span class="sxs-lookup"><span data-stu-id="351db-203">The **CurrentUser** installs modules in a location that is accessible only to the current user of the computer.</span></span> <span data-ttu-id="351db-204">Пример:</span><span class="sxs-lookup"><span data-stu-id="351db-204">For example:</span></span>

`$home\Documents\PowerShell\Modules`

<span data-ttu-id="351db-205">Если **область** не определена, значение по умолчанию задается на основе версии PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="351db-205">When no **Scope** is defined, the default is set based on the PowerShellGet version.</span></span>

- <span data-ttu-id="351db-206">В PowerShellGet версий 2.0.0 и выше значение по умолчанию — **CurrentUser** , что не требует повышения прав для установки.</span><span class="sxs-lookup"><span data-stu-id="351db-206">In PowerShellGet versions 2.0.0 and above, the default is **CurrentUser** , which does not require elevation for install.</span></span>
- <span data-ttu-id="351db-207">В PowerShellGet версии 1. x значение по умолчанию — **ALLUSERS** , что требует повышения прав для установки.</span><span class="sxs-lookup"><span data-stu-id="351db-207">In PowerShellGet 1.x versions, the default is **AllUsers** , which requires elevation for install.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: CurrentUser, AllUsers

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="351db-208">-Скиппублишерчекк</span><span class="sxs-lookup"><span data-stu-id="351db-208">-SkipPublisherCheck</span></span>

<span data-ttu-id="351db-209">Позволяет установить более новую версию модуля, который уже существует на компьютере.</span><span class="sxs-lookup"><span data-stu-id="351db-209">Allows you to install a newer version of a module that already exists on your computer.</span></span> <span data-ttu-id="351db-210">Например, если существующий модуль подписан цифровой подписью доверенного издателя, но в новой версии нет цифровой подписи доверенного издателя.</span><span class="sxs-lookup"><span data-stu-id="351db-210">For example, when an existing module is digitally signed by a trusted publisher but the new version is not digitally signed by a trusted publisher.</span></span>

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

### <span data-ttu-id="351db-211">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="351db-211">-WhatIf</span></span>

<span data-ttu-id="351db-212">Показывает, что произойдет при `Install-Module` выполнении команды.</span><span class="sxs-lookup"><span data-stu-id="351db-212">Shows what would happen if an `Install-Module` command was run.</span></span> <span data-ttu-id="351db-213">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="351db-213">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="351db-214">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="351db-214">CommonParameters</span></span>

<span data-ttu-id="351db-215">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="351db-215">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="351db-216">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="351db-216">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="351db-217">Входные данные</span><span class="sxs-lookup"><span data-stu-id="351db-217">INPUTS</span></span>

### <span data-ttu-id="351db-218">PSRepositoryItemInfo</span><span class="sxs-lookup"><span data-stu-id="351db-218">PSRepositoryItemInfo</span></span>

<span data-ttu-id="351db-219">`Find-Module` создает объекты **PSRepositoryItemInfo** , которые могут быть отправлены по конвейеру в `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="351db-219">`Find-Module` creates **PSRepositoryItemInfo** objects that can be sent down the pipeline to `Install-Module`.</span></span>

### <span data-ttu-id="351db-220">System.String[]</span><span class="sxs-lookup"><span data-stu-id="351db-220">System.String[]</span></span>

### <span data-ttu-id="351db-221">System. Management. Automation. PSObject []</span><span class="sxs-lookup"><span data-stu-id="351db-221">System.Management.Automation.PSObject[]</span></span>

### <span data-ttu-id="351db-222">System.String</span><span class="sxs-lookup"><span data-stu-id="351db-222">System.String</span></span>

### <span data-ttu-id="351db-223">System.Management.Automation.PSCredential</span><span class="sxs-lookup"><span data-stu-id="351db-223">System.Management.Automation.PSCredential</span></span>

### <span data-ttu-id="351db-224">System.Uri</span><span class="sxs-lookup"><span data-stu-id="351db-224">System.Uri</span></span>

## <span data-ttu-id="351db-225">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="351db-225">OUTPUTS</span></span>

### <span data-ttu-id="351db-226">Microsoft. PowerShell. Commands. PSRepositoryItemInfo</span><span class="sxs-lookup"><span data-stu-id="351db-226">Microsoft.PowerShell.Commands.PSRepositoryItemInfo</span></span>

<span data-ttu-id="351db-227">При использовании параметра **PassThru** `Install-Module` выводит объект **PSRepositoryItemInfo** для модуля.</span><span class="sxs-lookup"><span data-stu-id="351db-227">When using the **PassThru** parameter, `Install-Module` outputs a **PSRepositoryItemInfo** object for the module.</span></span> <span data-ttu-id="351db-228">Это те же сведения, которые вы получаете из `Find-Module` командлета.</span><span class="sxs-lookup"><span data-stu-id="351db-228">This is the same information that you get from the `Find-Module` cmdlet.</span></span>

## <span data-ttu-id="351db-229">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="351db-229">NOTES</span></span>

<span data-ttu-id="351db-230">`Install-Module` работает в PowerShell 5,0 или более поздних версиях, в Windows 7 или Windows 2008 R2 и более поздних версиях Windows.</span><span class="sxs-lookup"><span data-stu-id="351db-230">`Install-Module` runs on PowerShell 5.0 or later releases, on Windows 7 or Windows 2008 R2 and later releases of Windows.</span></span>

<span data-ttu-id="351db-231">В целях безопасности рекомендуется оценивать код модуля перед первым запуском командлетов или функций.</span><span class="sxs-lookup"><span data-stu-id="351db-231">As a security best practice, evaluate a module's code before running any cmdlets or functions for the first time.</span></span> <span data-ttu-id="351db-232">Чтобы предотвратить выполнение модулей, содержащих вредоносный код, установленные модули не импортируются автоматически после установки.</span><span class="sxs-lookup"><span data-stu-id="351db-232">To prevent running modules that contain malicious code, installed modules are not automatically imported after installation.</span></span>

<span data-ttu-id="351db-233">Если имя модуля, указанное в параметре **Name** , не существует в репозитории, `Install-Module` возвращает ошибку.</span><span class="sxs-lookup"><span data-stu-id="351db-233">If the module name specified by the **Name** parameter does not exist in the repository, `Install-Module` returns an error.</span></span>

<span data-ttu-id="351db-234">Чтобы установить несколько модулей, используйте параметр **Name** и укажите разделенный запятыми массив имен модулей.</span><span class="sxs-lookup"><span data-stu-id="351db-234">To install multiple modules, use the **Name** parameter and specify a comma-separated array of module names.</span></span> <span data-ttu-id="351db-235">При указании нескольких имен модулей нельзя использовать **MinimumVersion** , **MaximumVersion** или **RequiredVersion** .</span><span class="sxs-lookup"><span data-stu-id="351db-235">If you specify multiple module names, you cannot use **MinimumVersion** , **MaximumVersion** , or **RequiredVersion** .</span></span> <span data-ttu-id="351db-236">`Find-Module` создает объекты **PSRepositoryItemInfo** , которые могут быть отправлены по конвейеру в `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="351db-236">`Find-Module` creates **PSRepositoryItemInfo** objects that can be sent down the pipeline to `Install-Module`.</span></span> <span data-ttu-id="351db-237">Конвейер — это еще один способ указать несколько модулей для установки в одной команде.</span><span class="sxs-lookup"><span data-stu-id="351db-237">The pipeline is another way to specify multiple modules to install in a single command.</span></span>

<span data-ttu-id="351db-238">По умолчанию модули для области **ALLUSERS** устанавливаются в `$env:ProgramFiles\PowerShell\Modules` .</span><span class="sxs-lookup"><span data-stu-id="351db-238">By default, modules for the scope of **AllUsers** are installed in `$env:ProgramFiles\PowerShell\Modules`.</span></span> <span data-ttu-id="351db-239">Значение по умолчанию предотвращает путаницу при установке ресурсов DSC для требуемого состояния.</span><span class="sxs-lookup"><span data-stu-id="351db-239">The default prevents confusion when you install PowerShell Desired State Configuration (DSC) resources.</span></span>

<span data-ttu-id="351db-240">Установка модуля завершается сбоем и не может быть импортирована, если в `.psm1` `.psd1` папке отсутствует имя, или `.dll` .</span><span class="sxs-lookup"><span data-stu-id="351db-240">A module installation fails and cannot be imported if it does not have a `.psm1`, `.psd1`, or `.dll` of the same name within the folder.</span></span> <span data-ttu-id="351db-241">Для установки модуля используйте параметр **Force** .</span><span class="sxs-lookup"><span data-stu-id="351db-241">Use the **Force** parameter to install the module.</span></span>

<span data-ttu-id="351db-242">Если версия существующего модуля совпадает с именем, указанным в параметре **Name** , а параметр **MinimumVersion** или **RequiredVersion** не используется, `Install-Module` Автоматическое продолжение не выполняется, но не устанавливает модуль.</span><span class="sxs-lookup"><span data-stu-id="351db-242">If an existing module's version matches the name specified by the **Name** parameter, and the **MinimumVersion** or **RequiredVersion** parameter are not used, `Install-Module` silently continues but does not install the module.</span></span>

<span data-ttu-id="351db-243">Если версия существующего модуля больше значения параметра **MinimumVersion** или равна значению параметра **RequiredVersion** , `Install-Module` Автоматическое продолжение сохраняется, но не устанавливает модуль.</span><span class="sxs-lookup"><span data-stu-id="351db-243">If an existing module's version is greater than the value of the **MinimumVersion** parameter, or equal to the value of the **RequiredVersion** parameter, `Install-Module` silently continues but does not install the module.</span></span>

<span data-ttu-id="351db-244">Если существующий модуль не соответствует значениям, указанным в параметрах **MinimumVersion** или **RequiredVersion** , в команде возникает ошибка `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="351db-244">If the existing module does not match the values specified by the **MinimumVersion** or **RequiredVersion** parameters, an error occurs in the `Install-Module` command.</span></span> <span data-ttu-id="351db-245">Например, если версия существующего установленного модуля ниже значения **MinimumVersion** или не равна значению **RequiredVersion** .</span><span class="sxs-lookup"><span data-stu-id="351db-245">For example, if the version of the existing installed module is lower than the **MinimumVersion** value or not equal to the **RequiredVersion** value.</span></span>

<span data-ttu-id="351db-246">При установке модуля будут также установлены все зависимые модули, указанные в соответствии с требованиями издателя модуля.</span><span class="sxs-lookup"><span data-stu-id="351db-246">A module installation will also install any dependent modules specified as required by the module publisher.</span></span>
<span data-ttu-id="351db-247">Издатель укажет необходимые модули и их версии в манифесте модуля.</span><span class="sxs-lookup"><span data-stu-id="351db-247">The publisher will specify the required modules and their versions in the module manifest.</span></span>

## <span data-ttu-id="351db-248">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="351db-248">RELATED LINKS</span></span>

[<span data-ttu-id="351db-249">Find-Module</span><span class="sxs-lookup"><span data-stu-id="351db-249">Find-Module</span></span>](Find-Module.md)

[<span data-ttu-id="351db-250">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="351db-250">Get-PSRepository</span></span>](Get-PSRepository.md)

[<span data-ttu-id="351db-251">Import-Module</span><span class="sxs-lookup"><span data-stu-id="351db-251">Import-Module</span></span>](../Microsoft.PowerShell.Core/Import-Module.md)

[<span data-ttu-id="351db-252">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="351db-252">Publish-Module</span></span>](Publish-Module.md)

[<span data-ttu-id="351db-253">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="351db-253">Register-PSRepository</span></span>](Register-PSRepository.md)

[<span data-ttu-id="351db-254">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="351db-254">Uninstall-Module</span></span>](Uninstall-Module.md)

[<span data-ttu-id="351db-255">Update-Module</span><span class="sxs-lookup"><span data-stu-id="351db-255">Update-Module</span></span>](Update-Module.md)

[<span data-ttu-id="351db-256">about_Module</span><span class="sxs-lookup"><span data-stu-id="351db-256">about_Module</span></span>](../Microsoft.PowerShell.Core/About/about_Modules.md)
