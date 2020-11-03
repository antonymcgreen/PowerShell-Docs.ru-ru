---
external help file: PSModule-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/16/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/update-module?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-Module
ms.openlocfilehash: 42a2b37144d9af188a7204500227fddf4827bdf9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228921"
---
# <span data-ttu-id="52c78-103">Update-Module</span><span class="sxs-lookup"><span data-stu-id="52c78-103">Update-Module</span></span>

## <span data-ttu-id="52c78-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="52c78-104">SYNOPSIS</span></span>
<span data-ttu-id="52c78-105">Скачивает последние версии указанных модулей из веб-коллекции и устанавливает их на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="52c78-105">Downloads and installs the newest version of specified modules from an online gallery to the local computer.</span></span>

## <span data-ttu-id="52c78-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="52c78-106">SYNTAX</span></span>

### <span data-ttu-id="52c78-107">Все</span><span class="sxs-lookup"><span data-stu-id="52c78-107">All</span></span>

```
Update-Module [[-Name] <String[]>] [-RequiredVersion <String>] [-MaximumVersion <String>]
 [-Credential <PSCredential>] [-Scope <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-Force] [-AllowPrerelease] [-AcceptLicense] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="52c78-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="52c78-108">DESCRIPTION</span></span>

<span data-ttu-id="52c78-109">`Update-Module`Командлет устанавливает последнюю версию модуля из веб-коллекции.</span><span class="sxs-lookup"><span data-stu-id="52c78-109">The `Update-Module` cmdlet installs a module's newest version from an online gallery.</span></span> <span data-ttu-id="52c78-110">Перед установкой появится запрос на подтверждение обновления.</span><span class="sxs-lookup"><span data-stu-id="52c78-110">You're prompted to confirm the update before it's installed.</span></span> <span data-ttu-id="52c78-111">Обновления устанавливаются только для модулей, установленных на локальном компьютере с `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="52c78-111">Updates are installed only for modules that were installed on the local computer with `Install-Module`.</span></span> <span data-ttu-id="52c78-112">`Update-Module` выполняет поиск `$env:PSModulePath` установленных модулей.</span><span class="sxs-lookup"><span data-stu-id="52c78-112">`Update-Module` searches `$env:PSModulePath` for installed modules.</span></span>

<span data-ttu-id="52c78-113">`Update-Module` без указания параметров обновляет все установленные модули.</span><span class="sxs-lookup"><span data-stu-id="52c78-113">`Update-Module` with no parameters specified updates all installed modules.</span></span> <span data-ttu-id="52c78-114">Чтобы указать обновляемый модуль, используйте параметр **Name** .</span><span class="sxs-lookup"><span data-stu-id="52c78-114">To specify a module to update, use the **Name** parameter.</span></span> <span data-ttu-id="52c78-115">Можно выполнить обновление до определенной версии модуля с помощью параметра **RequiredVersion** .</span><span class="sxs-lookup"><span data-stu-id="52c78-115">You can update to a module's specific version by using the **RequiredVersion** parameter.</span></span>

<span data-ttu-id="52c78-116">Если установленный модуль уже является последней версией, модуль не обновляется.</span><span class="sxs-lookup"><span data-stu-id="52c78-116">If an installed module is already the newest version, the module isn't updated.</span></span> <span data-ttu-id="52c78-117">Если модуль не найден в `$env:PSModulePath` , выводится сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="52c78-117">If the module isn't found in `$env:PSModulePath`, an error is displayed.</span></span>

<span data-ttu-id="52c78-118">Чтобы отобразить установленные модули, используйте `Get-InstalledModule` .</span><span class="sxs-lookup"><span data-stu-id="52c78-118">To display the installed modules, use `Get-InstalledModule`.</span></span>

## <span data-ttu-id="52c78-119">Примеры</span><span class="sxs-lookup"><span data-stu-id="52c78-119">EXAMPLES</span></span>

### <span data-ttu-id="52c78-120">Пример 1. обновление всех модулей</span><span class="sxs-lookup"><span data-stu-id="52c78-120">Example 1: Update all modules</span></span>

<span data-ttu-id="52c78-121">В этом примере все установленные модули обновляются до последней версии в интерактивной коллекции.</span><span class="sxs-lookup"><span data-stu-id="52c78-121">This example updates all installed modules to the newest version in an online gallery.</span></span>

```powershell
Update-Module
```

### <span data-ttu-id="52c78-122">Пример 2. обновление модуля по имени</span><span class="sxs-lookup"><span data-stu-id="52c78-122">Example 2: Update a module by name</span></span>

<span data-ttu-id="52c78-123">В этом примере заданный модуль обновляется до последней версии в интерактивной коллекции.</span><span class="sxs-lookup"><span data-stu-id="52c78-123">This example updates a specific module to the newest version in an online gallery.</span></span>

```powershell
Update-Module -Name SpeculationControl
```

<span data-ttu-id="52c78-124">`Update-Module` использует параметр **Name** для обновления конкретного модуля **спекулатионконтрол** .</span><span class="sxs-lookup"><span data-stu-id="52c78-124">`Update-Module` uses the **Name** parameter to update a specific module, **SpeculationControl** .</span></span>

### <span data-ttu-id="52c78-125">Пример 3. Просмотр Update-Module запусков</span><span class="sxs-lookup"><span data-stu-id="52c78-125">Example 3: View what-if Update-Module runs</span></span>

<span data-ttu-id="52c78-126">В этом примере сценарий "что если" показывает, что происходит при `Update-Module` запуске.</span><span class="sxs-lookup"><span data-stu-id="52c78-126">This example does a what-if scenario to show what happens if `Update-Module` is run.</span></span> <span data-ttu-id="52c78-127">Команда не выполняется.</span><span class="sxs-lookup"><span data-stu-id="52c78-127">The command isn't run.</span></span>

```powershell
Update-Module -WhatIf
```

```Output
What if: Performing the operation "Update-Module" on target "Version '2.8.0' of module
  'Carbon', updating to version '2.8.1'".
What if: Performing the operation "Update-Module" on target "Version '1.0.10' of module
  'SpeculationControl', updating to version '1.0.14'".
```

<span data-ttu-id="52c78-128">`Update-Module` использует параметр **WhatIf** , чтобы отобразить, что произойдет при `Update-Module` запуске.</span><span class="sxs-lookup"><span data-stu-id="52c78-128">`Update-Module` uses the **WhatIf** parameter display what would happen if `Update-Module` were run.</span></span>

### <span data-ttu-id="52c78-129">Пример 4. обновление модуля до указанной версии</span><span class="sxs-lookup"><span data-stu-id="52c78-129">Example 4: Update a module to a specified version</span></span>

<span data-ttu-id="52c78-130">В этом примере модуль обновляется до определенной версии.</span><span class="sxs-lookup"><span data-stu-id="52c78-130">In this example, a module is updated to a specific version.</span></span> <span data-ttu-id="52c78-131">Версия должна существовать в интерактивной коллекции, или отображается ошибка.</span><span class="sxs-lookup"><span data-stu-id="52c78-131">The version must exist in the online gallery or an error is displayed.</span></span>

```powershell
Update-Module -Name SpeculationControl -RequiredVersion 1.0.14
```

<span data-ttu-id="52c78-132">`Update-Module` использует параметр **Name** для указания модуля **спекулатионконтрол** .</span><span class="sxs-lookup"><span data-stu-id="52c78-132">`Update-Module` uses the **Name** parameter to specify the module, **SpeculationControl** .</span></span> <span data-ttu-id="52c78-133">Параметр **RequiredVersion** указывает версию **1.0.14** .</span><span class="sxs-lookup"><span data-stu-id="52c78-133">The **RequiredVersion** parameter specifies the version, **1.0.14** .</span></span>

### <span data-ttu-id="52c78-134">Пример 5. обновление модуля без подтверждения</span><span class="sxs-lookup"><span data-stu-id="52c78-134">Example 5: Update a module without confirmation</span></span>

<span data-ttu-id="52c78-135">В этом примере не запрашивается подтверждение для обновления модуля до последней версии из интерактивной коллекции.</span><span class="sxs-lookup"><span data-stu-id="52c78-135">This example doesn't request confirmation to update the module to the newest version from an online gallery.</span></span> <span data-ttu-id="52c78-136">Если модуль уже установлен, параметр **Force** переустанавливает модуль.</span><span class="sxs-lookup"><span data-stu-id="52c78-136">If the module is already installed, the **Force** parameter reinstalls the module.</span></span>

```powershell
Update-Module -Name SpeculationControl -Force
```

<span data-ttu-id="52c78-137">`Update-Module` использует параметр **Name** для указания модуля **спекулатионконтрол** .</span><span class="sxs-lookup"><span data-stu-id="52c78-137">`Update-Module` uses the **Name** parameter to specify the module, **SpeculationControl** .</span></span> <span data-ttu-id="52c78-138">Параметр **Force** обновляет модуль без запроса подтверждения пользователя.</span><span class="sxs-lookup"><span data-stu-id="52c78-138">The **Force** parameter updates the module without requesting user confirmation.</span></span>

## <span data-ttu-id="52c78-139">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="52c78-139">PARAMETERS</span></span>

### <span data-ttu-id="52c78-140">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="52c78-140">-AcceptLicense</span></span>

<span data-ttu-id="52c78-141">Автоматически принимать лицензионное соглашение во время установки, если оно требуется для пакета.</span><span class="sxs-lookup"><span data-stu-id="52c78-141">Automatically accept the license agreement during installation if the package requires it.</span></span>

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

### <span data-ttu-id="52c78-142">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="52c78-142">-AllowPrerelease</span></span>

<span data-ttu-id="52c78-143">Позволяет обновить модуль, используя новый модуль, помеченный как предварительный выпуск.</span><span class="sxs-lookup"><span data-stu-id="52c78-143">Allows you to update a module with the newer module marked as a prerelease.</span></span>

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

### <span data-ttu-id="52c78-144">-Confirm</span><span class="sxs-lookup"><span data-stu-id="52c78-144">-Confirm</span></span>

<span data-ttu-id="52c78-145">Запрашивает подтверждение перед запуском `Update-Module` .</span><span class="sxs-lookup"><span data-stu-id="52c78-145">Prompts you for confirmation before running `Update-Module`.</span></span>

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

### <span data-ttu-id="52c78-146">-Credential</span><span class="sxs-lookup"><span data-stu-id="52c78-146">-Credential</span></span>

<span data-ttu-id="52c78-147">Указывает учетную запись пользователя, имеющую разрешение на обновление модуля.</span><span class="sxs-lookup"><span data-stu-id="52c78-147">Specifies a user account that has permission to update a module.</span></span>

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

### <span data-ttu-id="52c78-148">-Force</span><span class="sxs-lookup"><span data-stu-id="52c78-148">-Force</span></span>

<span data-ttu-id="52c78-149">Принудительно обновляет каждый указанный модуль без запроса на подтверждение.</span><span class="sxs-lookup"><span data-stu-id="52c78-149">Forces an update of each specified module without a prompt to request confirmation.</span></span> <span data-ttu-id="52c78-150">Если модуль уже установлен, **принудительно** переустанавливает модуль.</span><span class="sxs-lookup"><span data-stu-id="52c78-150">If the module is already installed, **Force** reinstalls the module.</span></span>

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

### <span data-ttu-id="52c78-151">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="52c78-151">-MaximumVersion</span></span>

<span data-ttu-id="52c78-152">Указывает максимальную версию одного модуля для обновления.</span><span class="sxs-lookup"><span data-stu-id="52c78-152">Specifies the maximum version of a single module to update.</span></span> <span data-ttu-id="52c78-153">Вы не можете добавить этот параметр, если пытаетесь обновить несколько модулей.</span><span class="sxs-lookup"><span data-stu-id="52c78-153">You can't add this parameter if you're attempting to update multiple modules.</span></span> <span data-ttu-id="52c78-154">Параметры **MaximumVersion** и **RequiredVersion** нельзя использовать в одной команде.</span><span class="sxs-lookup"><span data-stu-id="52c78-154">The **MaximumVersion** and the **RequiredVersion** parameters can't be used in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="52c78-155">-Name</span><span class="sxs-lookup"><span data-stu-id="52c78-155">-Name</span></span>

<span data-ttu-id="52c78-156">Указывает имена одного или нескольких модулей для обновления.</span><span class="sxs-lookup"><span data-stu-id="52c78-156">Specifies the names of one or more modules to update.</span></span> <span data-ttu-id="52c78-157">`Update-Module` выполняет поиск `$env:PSModulePath` модулей для обновления.</span><span class="sxs-lookup"><span data-stu-id="52c78-157">`Update-Module` searches `$env:PSModulePath` for the modules to update.</span></span> <span data-ttu-id="52c78-158">Если в `$env:PSModulePath` для указанного имени модуля не найдено совпадений, возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="52c78-158">If no matches are found in `$env:PSModulePath` for the specified module name, an error occurs.</span></span>

<span data-ttu-id="52c78-159">Подстановочные знаки принимаются в именах модулей.</span><span class="sxs-lookup"><span data-stu-id="52c78-159">Wildcards are accepted in module names.</span></span> <span data-ttu-id="52c78-160">Если добавить подстановочные знаки к указанному имени и совпадений не найдено, ошибка не возникает.</span><span class="sxs-lookup"><span data-stu-id="52c78-160">If you add wildcard characters to the specified name and no matches are found, no error occurs.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="52c78-161">-PassThru</span><span class="sxs-lookup"><span data-stu-id="52c78-161">-PassThru</span></span>

<span data-ttu-id="52c78-162">Возвращает объект, представляющий элемент, с которым вы работаете.</span><span class="sxs-lookup"><span data-stu-id="52c78-162">Returns an object representing the item with which you are working.</span></span> <span data-ttu-id="52c78-163">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="52c78-163">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="52c78-164">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="52c78-164">-Proxy</span></span>

<span data-ttu-id="52c78-165">Указывает прокси-сервер для запроса, а не напрямуюе подключение к Интернет-ресурсу.</span><span class="sxs-lookup"><span data-stu-id="52c78-165">Specifies a proxy server for the request, rather than connecting directly to an internet resource.</span></span>

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

### <span data-ttu-id="52c78-166">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="52c78-166">-ProxyCredential</span></span>

<span data-ttu-id="52c78-167">Указывает учетную запись пользователя, имеющую разрешение на использование прокси-сервера, указанного параметром **прокси** .</span><span class="sxs-lookup"><span data-stu-id="52c78-167">Specifies a user account that has permission to use the proxy server specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="52c78-168">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="52c78-168">-RequiredVersion</span></span>

<span data-ttu-id="52c78-169">Указывает точную версию, до которой будет обновлен существующий установленный модуль.</span><span class="sxs-lookup"><span data-stu-id="52c78-169">Specifies the exact version to which the existing installed module will be updated.</span></span> <span data-ttu-id="52c78-170">Версия, указанная в параметре **RequiredVersion** , должна существовать в интерактивной коллекции, иначе отображается ошибка.</span><span class="sxs-lookup"><span data-stu-id="52c78-170">The version specified by **RequiredVersion** must exist in the online gallery or an error is displayed.</span></span> <span data-ttu-id="52c78-171">Если в одной команде обновляется несколько модулей, нельзя использовать **RequiredVersion** .</span><span class="sxs-lookup"><span data-stu-id="52c78-171">If more than one module is updated in a single command, you can't use **RequiredVersion** .</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="52c78-172">-Scope</span><span class="sxs-lookup"><span data-stu-id="52c78-172">-Scope</span></span>

<span data-ttu-id="52c78-173">Задает область установки модуля.</span><span class="sxs-lookup"><span data-stu-id="52c78-173">Specifies the installation scope of the module.</span></span> <span data-ttu-id="52c78-174">Допустимые значения для этого параметра: **ALLUSERS** и **CurrentUser** .</span><span class="sxs-lookup"><span data-stu-id="52c78-174">The acceptable values for this parameter are **AllUsers** and **CurrentUser** .</span></span> <span data-ttu-id="52c78-175">Если **область** не указана, обновление устанавливается в области **CurrentUser** .</span><span class="sxs-lookup"><span data-stu-id="52c78-175">If **Scope** isn't specified, the update is installed in the **CurrentUser** scope.</span></span>

<span data-ttu-id="52c78-176">Область **ALLUSERS** требует повышенных разрешений и устанавливает модули в расположение, доступное всем пользователям компьютера:</span><span class="sxs-lookup"><span data-stu-id="52c78-176">The **AllUsers** scope requires elevated permissions and installs modules in a location that is accessible to all users of the computer:</span></span>

`$env:ProgramFiles\PowerShell\Modules`

<span data-ttu-id="52c78-177">Параметр **CurrentUser** не требует повышенных разрешений и устанавливает модули в расположении, доступном только текущему пользователю компьютера:</span><span class="sxs-lookup"><span data-stu-id="52c78-177">The **CurrentUser** doesn't require elevated permissions and installs modules in a location that is accessible only to the current user of the computer:</span></span>

`$home\Documents\PowerShell\Modules`

<span data-ttu-id="52c78-178">Если **область** не определена, значение по умолчанию задается на основе версии PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="52c78-178">When no **Scope** is defined, the default is set based on the PowerShellGet version.</span></span>

- <span data-ttu-id="52c78-179">В PowerShellGet версий 2.0.0 и выше значение по умолчанию — **CurrentUser** , что не требует повышения прав для установки.</span><span class="sxs-lookup"><span data-stu-id="52c78-179">In PowerShellGet versions 2.0.0 and above, the default is **CurrentUser** , which does not require elevation for install.</span></span>
- <span data-ttu-id="52c78-180">В PowerShellGet версии 1. x значение по умолчанию — **ALLUSERS** , что требует повышения прав для установки.</span><span class="sxs-lookup"><span data-stu-id="52c78-180">In PowerShellGet 1.x versions, the default is **AllUsers** , which requires elevation for install.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: CurrentUser, AllUsers

Required: False
Position: Named
Default value: CurrentUser
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="52c78-181">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="52c78-181">-WhatIf</span></span>

<span data-ttu-id="52c78-182">Показывает, что произойдет при `Update-Module` запуске.</span><span class="sxs-lookup"><span data-stu-id="52c78-182">Shows what would happen if `Update-Module` runs.</span></span> <span data-ttu-id="52c78-183">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="52c78-183">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="52c78-184">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="52c78-184">CommonParameters</span></span>

<span data-ttu-id="52c78-185">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="52c78-185">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="52c78-186">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="52c78-186">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="52c78-187">Входные данные</span><span class="sxs-lookup"><span data-stu-id="52c78-187">INPUTS</span></span>

### <span data-ttu-id="52c78-188">System.String[]</span><span class="sxs-lookup"><span data-stu-id="52c78-188">System.String[]</span></span>

### <span data-ttu-id="52c78-189">System.String</span><span class="sxs-lookup"><span data-stu-id="52c78-189">System.String</span></span>

### <span data-ttu-id="52c78-190">System.Management.Automation.PSCredential</span><span class="sxs-lookup"><span data-stu-id="52c78-190">System.Management.Automation.PSCredential</span></span>

### <span data-ttu-id="52c78-191">System.Uri</span><span class="sxs-lookup"><span data-stu-id="52c78-191">System.Uri</span></span>

## <span data-ttu-id="52c78-192">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="52c78-192">OUTPUTS</span></span>

### <span data-ttu-id="52c78-193">System.Object</span><span class="sxs-lookup"><span data-stu-id="52c78-193">System.Object</span></span>

## <span data-ttu-id="52c78-194">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="52c78-194">NOTES</span></span>

<span data-ttu-id="52c78-195">Для PowerShell версии 6,0 и более поздней областью установки по умолчанию всегда является **CurrentUser** .</span><span class="sxs-lookup"><span data-stu-id="52c78-195">For PowerShell version 6.0 and above, the default installation scope is always **CurrentUser** .</span></span>
<span data-ttu-id="52c78-196">Обновления модулей для **CurrentUser** , `$home\Documents\PowerShell\Modules` не требуют повышенных разрешений.</span><span class="sxs-lookup"><span data-stu-id="52c78-196">Module updates for **CurrentUser** , `$home\Documents\PowerShell\Modules`, don't need elevated permissions.</span></span> <span data-ttu-id="52c78-197">Обновления модулей для **ALLUSERS** , `$env:ProgramFiles\PowerShell\Modules` требуют повышенных разрешений.</span><span class="sxs-lookup"><span data-stu-id="52c78-197">Module updates for **AllUsers** , `$env:ProgramFiles\PowerShell\Modules`, need elevated permissions.</span></span>

<span data-ttu-id="52c78-198">`Update-Module` работает в PowerShell 3,0 или более поздних версиях PowerShell, в Windows 7 или Windows 2008 R2 и более поздних версиях Windows.</span><span class="sxs-lookup"><span data-stu-id="52c78-198">`Update-Module` runs on PowerShell 3.0 or later releases of PowerShell, on Windows 7 or Windows 2008 R2 and later releases of Windows.</span></span>

<span data-ttu-id="52c78-199">Если модуль, указанный с параметром **Name** , не был установлен с помощью `Install-Module` , возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="52c78-199">If the module that you specify with the **Name** parameter wasn't installed by using `Install-Module`, an error occurs.</span></span>

<span data-ttu-id="52c78-200">Вы можете работать только с `Update-Module` модулями, установленными из коллекции в Интернете, запустив `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="52c78-200">You can only run `Update-Module` on modules that you installed from the online gallery by running `Install-Module`.</span></span>

<span data-ttu-id="52c78-201">При `Update-Module` попытке обновить двоичные файлы, которые используются, `Update-Module` возвращает ошибку, определяющую проблемные процессы.</span><span class="sxs-lookup"><span data-stu-id="52c78-201">If `Update-Module` attempts to update binaries that are in use, `Update-Module` returns an error that identifies the problem processes.</span></span> <span data-ttu-id="52c78-202">Пользователю будет сообщено повторить попытку `Update-Module` после остановки процессов.</span><span class="sxs-lookup"><span data-stu-id="52c78-202">The user is informed to retry `Update-Module` after the processes are stopped.</span></span>

## <span data-ttu-id="52c78-203">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="52c78-203">RELATED LINKS</span></span>

[<span data-ttu-id="52c78-204">Find-Module</span><span class="sxs-lookup"><span data-stu-id="52c78-204">Find-Module</span></span>](Find-Module.md)

[<span data-ttu-id="52c78-205">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="52c78-205">Get-InstalledModule</span></span>](Get-InstalledModule.md)

[<span data-ttu-id="52c78-206">Install-Module</span><span class="sxs-lookup"><span data-stu-id="52c78-206">Install-Module</span></span>](Install-Module.md)

[<span data-ttu-id="52c78-207">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="52c78-207">Publish-Module</span></span>](Publish-Module.md)

[<span data-ttu-id="52c78-208">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="52c78-208">Uninstall-Module</span></span>](Uninstall-Module.md)
