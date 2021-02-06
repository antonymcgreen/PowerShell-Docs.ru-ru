---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 08/03/2020
online version: https://docs.microsoft.com/powershell/module/powershellget/install-module?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Install-Module
ms.openlocfilehash: f4fcf349c439baf4813c37af4bf56c26a46c7877
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "99604727"
---
# <span data-ttu-id="2dbe7-102">Install-Module</span><span class="sxs-lookup"><span data-stu-id="2dbe7-102">Install-Module</span></span>

## <span data-ttu-id="2dbe7-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="2dbe7-103">SYNOPSIS</span></span>
<span data-ttu-id="2dbe7-104">Скачивает один или несколько модулей из репозитория и устанавливает их на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-104">Downloads one or more modules from a repository, and installs them on the local computer.</span></span>

## <span data-ttu-id="2dbe7-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2dbe7-105">SYNTAX</span></span>

### <span data-ttu-id="2dbe7-106">NameParameterSet (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="2dbe7-106">NameParameterSet (Default)</span></span>

```
Install-Module [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] [-Credential <PSCredential>] [-Scope <String>]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-AllowClobber] [-SkipPublisherCheck] [-Force]
 [-AllowPrerelease] [-AcceptLicense] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="2dbe7-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="2dbe7-107">InputObject</span></span>

```
Install-Module [-InputObject] <PSObject[]> [-Credential <PSCredential>] [-Scope <String>]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-AllowClobber] [-SkipPublisherCheck] [-Force]
 [-AcceptLicense] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="2dbe7-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2dbe7-108">DESCRIPTION</span></span>

<span data-ttu-id="2dbe7-109">`Install-Module`Командлет возвращает один или несколько модулей, соответствующих указанным критериям из Интернет-репозитория.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-109">The `Install-Module` cmdlet gets one or more modules that meet specified criteria from an online repository.</span></span> <span data-ttu-id="2dbe7-110">Командлет проверяет, что результаты поиска являются допустимыми модулями, и копирует папки модулей в расположение установки.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-110">The cmdlet verifies that search results are valid modules and copies the module folders to the installation location.</span></span> <span data-ttu-id="2dbe7-111">Установленные модули не импортируются автоматически после установки.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-111">Installed modules are not automatically imported after installation.</span></span>
<span data-ttu-id="2dbe7-112">Вы можете отфильтровать, какой модуль установлен на основе минимальной, максимальной и точной версий указанных модулей.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-112">You can filter which module is installed based on the minimum, maximum, and exact versions of specified modules.</span></span>

<span data-ttu-id="2dbe7-113">Если устанавливаемый модуль имеет то же имя или версию или содержит команды в существующем модуле, отображаются предупреждающие сообщения.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-113">If the module being installed has the same name or version, or contains commands in an existing module, warning messages are displayed.</span></span> <span data-ttu-id="2dbe7-114">Убедившись, что вы хотите установить модуль и переопределить предупреждения, используйте `-Force` `-AllowClobber` Параметры и.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-114">After you confirm that you want to install the module and override the warnings, use the `-Force` and `-AllowClobber` parameters.</span></span> <span data-ttu-id="2dbe7-115">В зависимости от параметров репозитория может потребоваться ответить на запрос установки модуля, чтобы продолжить.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-115">Dependent upon your repository settings, you might need to answer a prompt for the module installation to continue.</span></span>

<span data-ttu-id="2dbe7-116">В этих примерах используется [коллекция PowerShell](https://www.powershellgallery.com/) в качестве единственного зарегистрированного репозитория.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-116">These examples use the [PowerShell Gallery](https://www.powershellgallery.com/) as the only registered repository.</span></span> <span data-ttu-id="2dbe7-117">`Get-PSRepository` отображает зарегистрированные репозитории.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-117">`Get-PSRepository` displays the registered repositories.</span></span> <span data-ttu-id="2dbe7-118">Если у вас есть несколько зарегистрированных репозиториев, используйте `-Repository` параметр, чтобы указать имя репозитория.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-118">If you have multiple registered repositories, use the `-Repository` parameter to specify the repository's name.</span></span>

## <span data-ttu-id="2dbe7-119">Примеры</span><span class="sxs-lookup"><span data-stu-id="2dbe7-119">EXAMPLES</span></span>

### <span data-ttu-id="2dbe7-120">Пример 1. Поиск и установка модуля</span><span class="sxs-lookup"><span data-stu-id="2dbe7-120">Example 1: Find and install a module</span></span>

<span data-ttu-id="2dbe7-121">В этом примере выполняется поиск модуля в репозитории и установка модуля.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-121">This example finds a module in the repository and installs the module.</span></span>

```powershell
Find-Module -Name PowerShellGet | Install-Module
```

<span data-ttu-id="2dbe7-122">`Find-Module`Использует параметр **Name** для указания модуля **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="2dbe7-122">The `Find-Module` uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="2dbe7-123">По умолчанию последняя версия модуля загружается из репозитория.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-123">By default, the newest version of the module is downloaded from the repository.</span></span> <span data-ttu-id="2dbe7-124">Объект отправляется по конвейеру в `Install-Module` командлет.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-124">The object is sent down the pipeline to the `Install-Module` cmdlet.</span></span> <span data-ttu-id="2dbe7-125">`Install-Module` устанавливает модуль для всех пользователей в `$env:ProgramFiles\PowerShell\Modules` .</span><span class="sxs-lookup"><span data-stu-id="2dbe7-125">`Install-Module` installs the module for all users in `$env:ProgramFiles\PowerShell\Modules`.</span></span>

### <span data-ttu-id="2dbe7-126">Пример 2. Установка модуля по имени</span><span class="sxs-lookup"><span data-stu-id="2dbe7-126">Example 2: Install a module by name</span></span>

<span data-ttu-id="2dbe7-127">В этом примере установлена последняя версия модуля **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="2dbe7-127">In this example, the newest version of the **PowerShellGet** module is installed.</span></span>

```powershell
Install-Module -Name PowerShellGet
```

<span data-ttu-id="2dbe7-128">`Install-Module`Использует параметр **Name** для указания модуля **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="2dbe7-128">The `Install-Module` uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="2dbe7-129">По умолчанию последняя версия модуля загружается из репозитория и устанавливается.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-129">By default, the newest version of the module is downloaded from the repository and installed.</span></span>

### <span data-ttu-id="2dbe7-130">Пример 3. Установка модуля с использованием минимальной версии</span><span class="sxs-lookup"><span data-stu-id="2dbe7-130">Example 3: Install a module using its minimum version</span></span>

<span data-ttu-id="2dbe7-131">В этом примере устанавливается минимальная версия модуля **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="2dbe7-131">In this example, the minimum version of the **PowerShellGet** module is installed.</span></span> <span data-ttu-id="2dbe7-132">Параметр **MinimumVersion** указывает самую раннюю версию модуля, который следует установить.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-132">The **MinimumVersion** parameter specifies the lowest version of the module that should be installed.</span></span> <span data-ttu-id="2dbe7-133">Если доступна более новая версия модуля, эта версия скачивается и устанавливается для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-133">If a newer version of the module is available, that version is downloaded and installed for all users.</span></span>

```powershell
Install-Module -Name PowerShellGet -MinimumVersion 2.0.1
```

<span data-ttu-id="2dbe7-134">`Install-Module`Использует параметр **Name** для указания модуля **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="2dbe7-134">The `Install-Module` uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="2dbe7-135">Параметр **MinimumVersion** указывает, что версия **2.0.1** загружается из репозитория и устанавливается.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-135">The **MinimumVersion** parameter specifies that version **2.0.1** is downloaded from the repository and installed.</span></span> <span data-ttu-id="2dbe7-136">Так как доступна версия **2.0.4** , эта версия скачивается и устанавливается для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-136">Because version **2.0.4** is available, that version is downloaded and installed for all users.</span></span>

### <span data-ttu-id="2dbe7-137">Пример 4. Установка определенной версии модуля</span><span class="sxs-lookup"><span data-stu-id="2dbe7-137">Example 4: Install a specific version of a module</span></span>

<span data-ttu-id="2dbe7-138">В этом примере устанавливается определенная версия модуля **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="2dbe7-138">In this example, a specific version of the **PowerShellGet** module is installed.</span></span>

```powershell
Install-Module -Name PowerShellGet -RequiredVersion 2.0.0
```

<span data-ttu-id="2dbe7-139">`Install-Module`Использует параметр **Name** для указания модуля **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="2dbe7-139">The `Install-Module` uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="2dbe7-140">Параметр **RequiredVersion** указывает, что версия **2.0.0** скачивается и устанавливается для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-140">The **RequiredVersion** parameter specifies that version **2.0.0** is downloaded and installed for all users.</span></span>

### <span data-ttu-id="2dbe7-141">Пример 5. Установка модуля только для текущего пользователя</span><span class="sxs-lookup"><span data-stu-id="2dbe7-141">Example 5: Install a module only for the current user</span></span>

<span data-ttu-id="2dbe7-142">В этом примере загружается и устанавливается последняя версия модуля только для текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-142">This example downloads and installs the newest version of a module, only for the current user.</span></span>

```powershell
Install-Module -Name PowerShellGet -Scope CurrentUser
```

<span data-ttu-id="2dbe7-143">`Install-Module`Использует параметр **Name** для указания модуля **PowerShellGet** .</span><span class="sxs-lookup"><span data-stu-id="2dbe7-143">The `Install-Module` uses the **Name** parameter to specify the **PowerShellGet** module.</span></span>
<span data-ttu-id="2dbe7-144">`Install-Module` скачивает и устанавливает последнюю версию **PowerShellGet** в каталог текущего пользователя `$home\Documents\PowerShell\Modules` .</span><span class="sxs-lookup"><span data-stu-id="2dbe7-144">`Install-Module` downloads and installs the newest version of **PowerShellGet** into the current user's directory, `$home\Documents\PowerShell\Modules`.</span></span>

## <span data-ttu-id="2dbe7-145">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2dbe7-145">PARAMETERS</span></span>

### <span data-ttu-id="2dbe7-146">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="2dbe7-146">-AcceptLicense</span></span>

<span data-ttu-id="2dbe7-147">Для модулей, для которых требуется лицензия, **AcceptLicense** автоматически принимает лицензионное соглашение во время установки.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-147">For modules that require a license, **AcceptLicense** automatically accepts the license agreement during installation.</span></span> <span data-ttu-id="2dbe7-148">Дополнительные сведения см. в разделе [модули, требующие принятия условий лицензии](/powershell/scripting/gallery/concepts/module-license-acceptance).</span><span class="sxs-lookup"><span data-stu-id="2dbe7-148">For more information, see [Modules Requiring License Acceptance](/powershell/scripting/gallery/concepts/module-license-acceptance).</span></span>

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

### <span data-ttu-id="2dbe7-149">-AllowClobber</span><span class="sxs-lookup"><span data-stu-id="2dbe7-149">-AllowClobber</span></span>

<span data-ttu-id="2dbe7-150">Переопределяет предупреждающие сообщения о конфликтах установки существующих команд на компьютере.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-150">Overrides warning messages about installation conflicts about existing commands on a computer.</span></span>
<span data-ttu-id="2dbe7-151">Перезаписывает существующие команды, имена которых совпадают с именами команд, устанавливаемых модулем.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-151">Overwrites existing commands that have the same name as commands being installed by a module.</span></span>
<span data-ttu-id="2dbe7-152">**AllowClobber** и **Force** можно использовать вместе в `Install-Module` команде.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-152">**AllowClobber** and **Force** can be used together in an `Install-Module` command.</span></span>

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

### <span data-ttu-id="2dbe7-153">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="2dbe7-153">-AllowPrerelease</span></span>

<span data-ttu-id="2dbe7-154">Позволяет установить модуль, помеченный как предварительный выпуск.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-154">Allows you to install a module marked as a pre-release.</span></span>

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

### <span data-ttu-id="2dbe7-155">-Confirm</span><span class="sxs-lookup"><span data-stu-id="2dbe7-155">-Confirm</span></span>

<span data-ttu-id="2dbe7-156">Запрашивает подтверждение перед запуском `Install-Module` командлета.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-156">Prompts you for confirmation before running the `Install-Module` cmdlet.</span></span>

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

### <span data-ttu-id="2dbe7-157">-Credential</span><span class="sxs-lookup"><span data-stu-id="2dbe7-157">-Credential</span></span>

<span data-ttu-id="2dbe7-158">Указывает учетную запись пользователя, имеющую права на установку модуля для указанного поставщика пакетов или источника.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-158">Specifies a user account that has rights to install a module for a specified package provider or source.</span></span>

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

### <span data-ttu-id="2dbe7-159">-Force</span><span class="sxs-lookup"><span data-stu-id="2dbe7-159">-Force</span></span>

<span data-ttu-id="2dbe7-160">Устанавливает модуль и переопределяет предупреждающие сообщения о конфликтах при установке модулей.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-160">Installs a module and overrides warning messages about module installation conflicts.</span></span> <span data-ttu-id="2dbe7-161">Если на компьютере уже существует модуль с таким именем, **принудительно** установите несколько версий.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-161">If a module with the same name already exists on the computer, **Force** allows for multiple versions to be installed.</span></span> <span data-ttu-id="2dbe7-162">Если имеется существующий модуль с тем же именем и версией, **принудительно** перезаписывает эту версию.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-162">If there is an existing module with the same name and version, **Force** overwrites that version.</span></span> <span data-ttu-id="2dbe7-163">**Force** и **AllowClobber** можно использовать вместе в `Install-Module` команде.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-163">**Force** and **AllowClobber** can be used together in an `Install-Module` command.</span></span>

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

### <span data-ttu-id="2dbe7-164">-InputObject</span><span class="sxs-lookup"><span data-stu-id="2dbe7-164">-InputObject</span></span>

<span data-ttu-id="2dbe7-165">Используется для входных данных конвейера.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-165">Used for pipeline input.</span></span>

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

### <span data-ttu-id="2dbe7-166">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="2dbe7-166">-MaximumVersion</span></span>

<span data-ttu-id="2dbe7-167">Указывает максимальную версию одного модуля для установки.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-167">Specifies the maximum version of a single module to install.</span></span> <span data-ttu-id="2dbe7-168">Установленная версия должна быть меньше или равна **MaximumVersion**.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-168">The version installed must be less than or equal to **MaximumVersion**.</span></span> <span data-ttu-id="2dbe7-169">Если вы хотите установить несколько модулей, вы не сможете использовать **MaximumVersion**.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-169">If you want to install multiple modules, you cannot use **MaximumVersion**.</span></span> <span data-ttu-id="2dbe7-170">В одной команде нельзя использовать **MaximumVersion** и **RequiredVersion** `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="2dbe7-170">**MaximumVersion** and **RequiredVersion** cannot be used in the same `Install-Module` command.</span></span>

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

### <span data-ttu-id="2dbe7-171">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="2dbe7-171">-MinimumVersion</span></span>

<span data-ttu-id="2dbe7-172">Указывает минимальную версию отдельного модуля для установки.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-172">Specifies the minimum version of a single module to install.</span></span> <span data-ttu-id="2dbe7-173">Установленная версия должна быть больше или равна **MinimumVersion**.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-173">The version installed must be greater than or equal to **MinimumVersion**.</span></span> <span data-ttu-id="2dbe7-174">Если доступен более новая версия модуля, устанавливается более новая версия.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-174">If there is a newer version of the module available, the newer version is installed.</span></span> <span data-ttu-id="2dbe7-175">Если требуется установить несколько модулей, нельзя использовать параметр **MinimumVersion**.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-175">If you want to install multiple modules, you cannot use **MinimumVersion**.</span></span>
<span data-ttu-id="2dbe7-176">В одной команде нельзя использовать **MinimumVersion** и **RequiredVersion** `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="2dbe7-176">**MinimumVersion** and **RequiredVersion** cannot be used in the same `Install-Module` command.</span></span>

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

### <span data-ttu-id="2dbe7-177">-Name</span><span class="sxs-lookup"><span data-stu-id="2dbe7-177">-Name</span></span>

<span data-ttu-id="2dbe7-178">Указывает точные имена модулей для установки из Интернет-коллекции.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-178">Specifies the exact names of modules to install from the online gallery.</span></span> <span data-ttu-id="2dbe7-179">Принимается список имен модулей с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-179">A comma-separated list of module names is accepted.</span></span> <span data-ttu-id="2dbe7-180">Имя модуля должно совпадать с именем модуля в репозитории.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-180">The module name must match the module name in the repository.</span></span> <span data-ttu-id="2dbe7-181">Используйте `Find-Module` для получения списка имен модулей.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-181">Use `Find-Module` to get a list of module names.</span></span>

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

### <span data-ttu-id="2dbe7-182">-PassThru</span><span class="sxs-lookup"><span data-stu-id="2dbe7-182">-PassThru</span></span>

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

### <span data-ttu-id="2dbe7-183">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="2dbe7-183">-Proxy</span></span>

<span data-ttu-id="2dbe7-184">Указывает прокси-сервер для запроса, а не напрямуюе подключение к Интернет-ресурсу.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-184">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

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

### <span data-ttu-id="2dbe7-185">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="2dbe7-185">-ProxyCredential</span></span>

<span data-ttu-id="2dbe7-186">Указывает учетную запись пользователя, имеющую разрешение на использование прокси-сервера, который задается параметром **Proxy**.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-186">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="2dbe7-187">— Репозиторий;</span><span class="sxs-lookup"><span data-stu-id="2dbe7-187">-Repository</span></span>

<span data-ttu-id="2dbe7-188">Используйте параметр **репозитория** , чтобы указать, какой репозиторий используется для скачивания и установки модуля.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-188">Use the **Repository** parameter to specify which repository is used to download and install a module.</span></span> <span data-ttu-id="2dbe7-189">Используется при регистрации нескольких репозиториев.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-189">Used when multiple repositories are registered.</span></span> <span data-ttu-id="2dbe7-190">Указывает имя зарегистрированного репозитория в `Install-Module` команде.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-190">Specifies the name of a registered repository in the `Install-Module` command.</span></span> <span data-ttu-id="2dbe7-191">Чтобы зарегистрировать репозиторий, используйте `Register-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="2dbe7-191">To register a repository, use `Register-PSRepository`.</span></span>
<span data-ttu-id="2dbe7-192">Чтобы отобразить зарегистрированные репозитории, используйте `Get-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="2dbe7-192">To display registered repositories, use `Get-PSRepository`.</span></span>

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

### <span data-ttu-id="2dbe7-193">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="2dbe7-193">-RequiredVersion</span></span>

<span data-ttu-id="2dbe7-194">Указывает точную версию отдельного модуля для установки.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-194">Specifies the exact version of a single module to install.</span></span> <span data-ttu-id="2dbe7-195">Если в репозитории для указанной версии нет совпадения, выводится сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-195">If there is no match in the repository for the specified version, an error is displayed.</span></span> <span data-ttu-id="2dbe7-196">Если требуется установить несколько модулей, нельзя использовать **RequiredVersion**.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-196">If you want to install multiple modules, you cannot use **RequiredVersion**.</span></span> <span data-ttu-id="2dbe7-197">Параметр **RequiredVersion** нельзя использовать в той же `Install-Module` команде, что и **MinimumVersion** или **MaximumVersion**.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-197">**RequiredVersion** cannot be used in the same `Install-Module` command as **MinimumVersion** or **MaximumVersion**.</span></span>

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

### <span data-ttu-id="2dbe7-198">-Scope</span><span class="sxs-lookup"><span data-stu-id="2dbe7-198">-Scope</span></span>

<span data-ttu-id="2dbe7-199">Задает область установки модуля.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-199">Specifies the installation scope of the module.</span></span> <span data-ttu-id="2dbe7-200">Допустимые значения для этого параметра: **ALLUSERS** и **CurrentUser**.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-200">The acceptable values for this parameter are **AllUsers** and **CurrentUser**.</span></span>

<span data-ttu-id="2dbe7-201">Область **ALLUSERS** устанавливает модули в расположение, доступное всем пользователям компьютера:</span><span class="sxs-lookup"><span data-stu-id="2dbe7-201">The **AllUsers** scope installs modules in a location that is accessible to all users of the computer:</span></span>

`$env:ProgramFiles\PowerShell\Modules`

<span data-ttu-id="2dbe7-202">Параметр **CurrentUser** устанавливает модули в расположение, доступное только текущему пользователю компьютера.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-202">The **CurrentUser** installs modules in a location that is accessible only to the current user of the computer.</span></span> <span data-ttu-id="2dbe7-203">Пример:</span><span class="sxs-lookup"><span data-stu-id="2dbe7-203">For example:</span></span>

`$home\Documents\PowerShell\Modules`

<span data-ttu-id="2dbe7-204">Если **область** не определена, значение по умолчанию задается на основе версии PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-204">When no **Scope** is defined, the default is set based on the PowerShellGet version.</span></span>

- <span data-ttu-id="2dbe7-205">В PowerShellGet версий 2.0.0 и выше значение по умолчанию — **CurrentUser**, что не требует повышения прав для установки.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-205">In PowerShellGet versions 2.0.0 and above, the default is **CurrentUser**, which does not require elevation for install.</span></span>
- <span data-ttu-id="2dbe7-206">В PowerShellGet версии 1. x значение по умолчанию — **ALLUSERS**, что требует повышения прав для установки.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-206">In PowerShellGet 1.x versions, the default is **AllUsers**, which requires elevation for install.</span></span>

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

### <span data-ttu-id="2dbe7-207">-Скиппублишерчекк</span><span class="sxs-lookup"><span data-stu-id="2dbe7-207">-SkipPublisherCheck</span></span>

<span data-ttu-id="2dbe7-208">Позволяет установить более новую версию модуля, который уже существует на компьютере.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-208">Allows you to install a newer version of a module that already exists on your computer.</span></span> <span data-ttu-id="2dbe7-209">Например, если существующий модуль подписан цифровой подписью доверенного издателя, но в новой версии нет цифровой подписи доверенного издателя.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-209">For example, when an existing module is digitally signed by a trusted publisher but the new version is not digitally signed by a trusted publisher.</span></span>

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

### <span data-ttu-id="2dbe7-210">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="2dbe7-210">-WhatIf</span></span>

<span data-ttu-id="2dbe7-211">Показывает, что произойдет при `Install-Module` выполнении команды.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-211">Shows what would happen if an `Install-Module` command was run.</span></span> <span data-ttu-id="2dbe7-212">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-212">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="2dbe7-213">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="2dbe7-213">CommonParameters</span></span>

<span data-ttu-id="2dbe7-214">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-214">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2dbe7-215">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2dbe7-215">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2dbe7-216">Входные данные</span><span class="sxs-lookup"><span data-stu-id="2dbe7-216">INPUTS</span></span>

### <span data-ttu-id="2dbe7-217">PSRepositoryItemInfo</span><span class="sxs-lookup"><span data-stu-id="2dbe7-217">PSRepositoryItemInfo</span></span>

<span data-ttu-id="2dbe7-218">`Find-Module` создает объекты **PSRepositoryItemInfo** , которые могут быть отправлены по конвейеру в `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="2dbe7-218">`Find-Module` creates **PSRepositoryItemInfo** objects that can be sent down the pipeline to `Install-Module`.</span></span>

### <span data-ttu-id="2dbe7-219">System.String[]</span><span class="sxs-lookup"><span data-stu-id="2dbe7-219">System.String[]</span></span>

### <span data-ttu-id="2dbe7-220">System. Management. Automation. PSObject []</span><span class="sxs-lookup"><span data-stu-id="2dbe7-220">System.Management.Automation.PSObject[]</span></span>

### <span data-ttu-id="2dbe7-221">System.String</span><span class="sxs-lookup"><span data-stu-id="2dbe7-221">System.String</span></span>

### <span data-ttu-id="2dbe7-222">System.Management.Automation.PSCredential</span><span class="sxs-lookup"><span data-stu-id="2dbe7-222">System.Management.Automation.PSCredential</span></span>

### <span data-ttu-id="2dbe7-223">System.Uri</span><span class="sxs-lookup"><span data-stu-id="2dbe7-223">System.Uri</span></span>

## <span data-ttu-id="2dbe7-224">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="2dbe7-224">OUTPUTS</span></span>

### <span data-ttu-id="2dbe7-225">Microsoft. PowerShell. Commands. PSRepositoryItemInfo</span><span class="sxs-lookup"><span data-stu-id="2dbe7-225">Microsoft.PowerShell.Commands.PSRepositoryItemInfo</span></span>

<span data-ttu-id="2dbe7-226">При использовании параметра **PassThru** `Install-Module` выводит объект **PSRepositoryItemInfo** для модуля.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-226">When using the **PassThru** parameter, `Install-Module` outputs a **PSRepositoryItemInfo** object for the module.</span></span> <span data-ttu-id="2dbe7-227">Это те же сведения, которые вы получаете из `Find-Module` командлета.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-227">This is the same information that you get from the `Find-Module` cmdlet.</span></span>

## <span data-ttu-id="2dbe7-228">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="2dbe7-228">NOTES</span></span>

<span data-ttu-id="2dbe7-229">`Install-Module` работает в PowerShell 5,0 или более поздних версиях, в Windows 7 или Windows 2008 R2 и более поздних версиях Windows.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-229">`Install-Module` runs on PowerShell 5.0 or later releases, on Windows 7 or Windows 2008 R2 and later releases of Windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2dbe7-230">Начиная с апреля 2020 года коллекция PowerShell не поддерживает протокол TLS (Transport Layer Security) версий 1.0 и 1.1.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-230">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="2dbe7-231">Если вы не используете TLS 1.2 или более поздней версии, при попытке доступа к коллекции PowerShell возникнет ошибка.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-231">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="2dbe7-232">Чтобы проверить, используется ли TLS 1.2, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="2dbe7-232">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="2dbe7-233">Дополнительные сведения см. в [объявлении](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) в блоге, посвященном PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-233">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

<span data-ttu-id="2dbe7-234">В целях безопасности рекомендуется оценивать код модуля перед первым запуском командлетов или функций.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-234">As a security best practice, evaluate a module's code before running any cmdlets or functions for the first time.</span></span> <span data-ttu-id="2dbe7-235">Чтобы предотвратить выполнение модулей, содержащих вредоносный код, установленные модули не импортируются автоматически после установки.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-235">To prevent running modules that contain malicious code, installed modules are not automatically imported after installation.</span></span>

<span data-ttu-id="2dbe7-236">Если имя модуля, указанное в параметре **Name** , не существует в репозитории, `Install-Module` возвращает ошибку.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-236">If the module name specified by the **Name** parameter does not exist in the repository, `Install-Module` returns an error.</span></span>

<span data-ttu-id="2dbe7-237">Чтобы установить несколько модулей, используйте параметр **Name** и укажите разделенный запятыми массив имен модулей.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-237">To install multiple modules, use the **Name** parameter and specify a comma-separated array of module names.</span></span> <span data-ttu-id="2dbe7-238">При указании нескольких имен модулей нельзя использовать **MinimumVersion**, **MaximumVersion** или **RequiredVersion**.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-238">If you specify multiple module names, you cannot use **MinimumVersion**, **MaximumVersion**, or **RequiredVersion**.</span></span> <span data-ttu-id="2dbe7-239">`Find-Module` создает объекты **PSRepositoryItemInfo** , которые могут быть отправлены по конвейеру в `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="2dbe7-239">`Find-Module` creates **PSRepositoryItemInfo** objects that can be sent down the pipeline to `Install-Module`.</span></span> <span data-ttu-id="2dbe7-240">Конвейер — это еще один способ указать несколько модулей для установки в одной команде.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-240">The pipeline is another way to specify multiple modules to install in a single command.</span></span>

<span data-ttu-id="2dbe7-241">По умолчанию модули для области **ALLUSERS** устанавливаются в `$env:ProgramFiles\PowerShell\Modules` .</span><span class="sxs-lookup"><span data-stu-id="2dbe7-241">By default, modules for the scope of **AllUsers** are installed in `$env:ProgramFiles\PowerShell\Modules`.</span></span> <span data-ttu-id="2dbe7-242">Значение по умолчанию предотвращает путаницу при установке ресурсов DSC для требуемого состояния.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-242">The default prevents confusion when you install PowerShell Desired State Configuration (DSC) resources.</span></span>

<span data-ttu-id="2dbe7-243">Установка модуля завершается сбоем и не может быть импортирована, если в `.psm1` `.psd1` папке отсутствует имя, или `.dll` .</span><span class="sxs-lookup"><span data-stu-id="2dbe7-243">A module installation fails and cannot be imported if it does not have a `.psm1`, `.psd1`, or `.dll` of the same name within the folder.</span></span> <span data-ttu-id="2dbe7-244">Для установки модуля используйте параметр **Force** .</span><span class="sxs-lookup"><span data-stu-id="2dbe7-244">Use the **Force** parameter to install the module.</span></span>

<span data-ttu-id="2dbe7-245">Если версия существующего модуля совпадает с именем, указанным в параметре **Name** , а параметр **MinimumVersion** или **RequiredVersion** не используется, `Install-Module` Автоматическое продолжение не выполняется, но не устанавливает модуль.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-245">If an existing module's version matches the name specified by the **Name** parameter, and the **MinimumVersion** or **RequiredVersion** parameter are not used, `Install-Module` silently continues but does not install the module.</span></span>

<span data-ttu-id="2dbe7-246">Если версия существующего модуля больше значения параметра **MinimumVersion** или равна значению параметра **RequiredVersion** , `Install-Module` Автоматическое продолжение сохраняется, но не устанавливает модуль.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-246">If an existing module's version is greater than the value of the **MinimumVersion** parameter, or equal to the value of the **RequiredVersion** parameter, `Install-Module` silently continues but does not install the module.</span></span>

<span data-ttu-id="2dbe7-247">Если существующий модуль не соответствует значениям, указанным в параметрах **MinimumVersion** или **RequiredVersion** , в команде возникает ошибка `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="2dbe7-247">If the existing module does not match the values specified by the **MinimumVersion** or **RequiredVersion** parameters, an error occurs in the `Install-Module` command.</span></span> <span data-ttu-id="2dbe7-248">Например, если версия существующего установленного модуля ниже значения **MinimumVersion** или не равна значению **RequiredVersion** .</span><span class="sxs-lookup"><span data-stu-id="2dbe7-248">For example, if the version of the existing installed module is lower than the **MinimumVersion** value or not equal to the **RequiredVersion** value.</span></span>

<span data-ttu-id="2dbe7-249">При установке модуля будут также установлены все зависимые модули, указанные в соответствии с требованиями издателя модуля.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-249">A module installation will also install any dependent modules specified as required by the module publisher.</span></span>
<span data-ttu-id="2dbe7-250">Издатель укажет необходимые модули и их версии в манифесте модуля.</span><span class="sxs-lookup"><span data-stu-id="2dbe7-250">The publisher will specify the required modules and their versions in the module manifest.</span></span>

## <span data-ttu-id="2dbe7-251">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="2dbe7-251">RELATED LINKS</span></span>

[<span data-ttu-id="2dbe7-252">Find-Module</span><span class="sxs-lookup"><span data-stu-id="2dbe7-252">Find-Module</span></span>](Find-Module.md)

[<span data-ttu-id="2dbe7-253">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="2dbe7-253">Get-PSRepository</span></span>](Get-PSRepository.md)

[<span data-ttu-id="2dbe7-254">Import-Module</span><span class="sxs-lookup"><span data-stu-id="2dbe7-254">Import-Module</span></span>](../Microsoft.PowerShell.Core/Import-Module.md)

[<span data-ttu-id="2dbe7-255">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="2dbe7-255">Publish-Module</span></span>](Publish-Module.md)

[<span data-ttu-id="2dbe7-256">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="2dbe7-256">Register-PSRepository</span></span>](Register-PSRepository.md)

[<span data-ttu-id="2dbe7-257">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="2dbe7-257">Uninstall-Module</span></span>](Uninstall-Module.md)

[<span data-ttu-id="2dbe7-258">Update-Module</span><span class="sxs-lookup"><span data-stu-id="2dbe7-258">Update-Module</span></span>](Update-Module.md)

[<span data-ttu-id="2dbe7-259">about_Module</span><span class="sxs-lookup"><span data-stu-id="2dbe7-259">about_Module</span></span>](../Microsoft.PowerShell.Core/About/about_Modules.md)
