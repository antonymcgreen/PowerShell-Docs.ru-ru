---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/16/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/update-module?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-Module
ms.openlocfilehash: f29c208805894634960085cd3816ce7780b7602f
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "99604286"
---
# <span data-ttu-id="13c3b-102">Update-Module</span><span class="sxs-lookup"><span data-stu-id="13c3b-102">Update-Module</span></span>

## <span data-ttu-id="13c3b-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="13c3b-103">SYNOPSIS</span></span>
<span data-ttu-id="13c3b-104">Скачивает последние версии указанных модулей из веб-коллекции и устанавливает их на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="13c3b-104">Downloads and installs the newest version of specified modules from an online gallery to the local computer.</span></span>

## <span data-ttu-id="13c3b-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="13c3b-105">SYNTAX</span></span>

### <span data-ttu-id="13c3b-106">Все</span><span class="sxs-lookup"><span data-stu-id="13c3b-106">All</span></span>

```
Update-Module [[-Name] <String[]>] [-RequiredVersion <String>] [-MaximumVersion <String>]
 [-Credential <PSCredential>] [-Scope <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-Force] [-AllowPrerelease] [-AcceptLicense] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="13c3b-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="13c3b-107">DESCRIPTION</span></span>

<span data-ttu-id="13c3b-108">`Update-Module`Командлет устанавливает последнюю версию модуля из веб-коллекции.</span><span class="sxs-lookup"><span data-stu-id="13c3b-108">The `Update-Module` cmdlet installs a module's newest version from an online gallery.</span></span> <span data-ttu-id="13c3b-109">Перед установкой появится запрос на подтверждение обновления.</span><span class="sxs-lookup"><span data-stu-id="13c3b-109">You're prompted to confirm the update before it's installed.</span></span> <span data-ttu-id="13c3b-110">Обновления устанавливаются только для модулей, установленных на локальном компьютере с `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="13c3b-110">Updates are installed only for modules that were installed on the local computer with `Install-Module`.</span></span> <span data-ttu-id="13c3b-111">`Update-Module` выполняет поиск `$env:PSModulePath` установленных модулей.</span><span class="sxs-lookup"><span data-stu-id="13c3b-111">`Update-Module` searches `$env:PSModulePath` for installed modules.</span></span>

<span data-ttu-id="13c3b-112">`Update-Module` без указания параметров обновляет все установленные модули.</span><span class="sxs-lookup"><span data-stu-id="13c3b-112">`Update-Module` with no parameters specified updates all installed modules.</span></span> <span data-ttu-id="13c3b-113">Чтобы указать обновляемый модуль, используйте параметр **Name** .</span><span class="sxs-lookup"><span data-stu-id="13c3b-113">To specify a module to update, use the **Name** parameter.</span></span> <span data-ttu-id="13c3b-114">Можно выполнить обновление до определенной версии модуля с помощью параметра **RequiredVersion** .</span><span class="sxs-lookup"><span data-stu-id="13c3b-114">You can update to a module's specific version by using the **RequiredVersion** parameter.</span></span>

<span data-ttu-id="13c3b-115">Если установленный модуль уже является последней версией, модуль не обновляется.</span><span class="sxs-lookup"><span data-stu-id="13c3b-115">If an installed module is already the newest version, the module isn't updated.</span></span> <span data-ttu-id="13c3b-116">Если модуль не найден в `$env:PSModulePath` , выводится сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="13c3b-116">If the module isn't found in `$env:PSModulePath`, an error is displayed.</span></span>

<span data-ttu-id="13c3b-117">Чтобы отобразить установленные модули, используйте `Get-InstalledModule` .</span><span class="sxs-lookup"><span data-stu-id="13c3b-117">To display the installed modules, use `Get-InstalledModule`.</span></span>

## <span data-ttu-id="13c3b-118">Примеры</span><span class="sxs-lookup"><span data-stu-id="13c3b-118">EXAMPLES</span></span>

### <span data-ttu-id="13c3b-119">Пример 1. обновление всех модулей</span><span class="sxs-lookup"><span data-stu-id="13c3b-119">Example 1: Update all modules</span></span>

<span data-ttu-id="13c3b-120">В этом примере все установленные модули обновляются до последней версии в интерактивной коллекции.</span><span class="sxs-lookup"><span data-stu-id="13c3b-120">This example updates all installed modules to the newest version in an online gallery.</span></span>

```powershell
Update-Module
```

### <span data-ttu-id="13c3b-121">Пример 2. обновление модуля по имени</span><span class="sxs-lookup"><span data-stu-id="13c3b-121">Example 2: Update a module by name</span></span>

<span data-ttu-id="13c3b-122">В этом примере заданный модуль обновляется до последней версии в интерактивной коллекции.</span><span class="sxs-lookup"><span data-stu-id="13c3b-122">This example updates a specific module to the newest version in an online gallery.</span></span>

```powershell
Update-Module -Name SpeculationControl
```

<span data-ttu-id="13c3b-123">`Update-Module` использует параметр **Name** для обновления конкретного модуля **спекулатионконтрол**.</span><span class="sxs-lookup"><span data-stu-id="13c3b-123">`Update-Module` uses the **Name** parameter to update a specific module, **SpeculationControl**.</span></span>

### <span data-ttu-id="13c3b-124">Пример 3. Просмотр Update-Module запусков</span><span class="sxs-lookup"><span data-stu-id="13c3b-124">Example 3: View what-if Update-Module runs</span></span>

<span data-ttu-id="13c3b-125">В этом примере сценарий "что если" показывает, что происходит при `Update-Module` запуске.</span><span class="sxs-lookup"><span data-stu-id="13c3b-125">This example does a what-if scenario to show what happens if `Update-Module` is run.</span></span> <span data-ttu-id="13c3b-126">Команда не выполняется.</span><span class="sxs-lookup"><span data-stu-id="13c3b-126">The command isn't run.</span></span>

```powershell
Update-Module -WhatIf
```

```Output
What if: Performing the operation "Update-Module" on target "Version '2.8.0' of module
  'Carbon', updating to version '2.8.1'".
What if: Performing the operation "Update-Module" on target "Version '1.0.10' of module
  'SpeculationControl', updating to version '1.0.14'".
```

<span data-ttu-id="13c3b-127">`Update-Module` использует параметр **WhatIf** , чтобы отобразить, что произойдет при `Update-Module` запуске.</span><span class="sxs-lookup"><span data-stu-id="13c3b-127">`Update-Module` uses the **WhatIf** parameter display what would happen if `Update-Module` were run.</span></span>

### <span data-ttu-id="13c3b-128">Пример 4. обновление модуля до указанной версии</span><span class="sxs-lookup"><span data-stu-id="13c3b-128">Example 4: Update a module to a specified version</span></span>

<span data-ttu-id="13c3b-129">В этом примере модуль обновляется до определенной версии.</span><span class="sxs-lookup"><span data-stu-id="13c3b-129">In this example, a module is updated to a specific version.</span></span> <span data-ttu-id="13c3b-130">Версия должна существовать в интерактивной коллекции, или отображается ошибка.</span><span class="sxs-lookup"><span data-stu-id="13c3b-130">The version must exist in the online gallery or an error is displayed.</span></span>

```powershell
Update-Module -Name SpeculationControl -RequiredVersion 1.0.14
```

<span data-ttu-id="13c3b-131">`Update-Module` использует параметр **Name** для указания модуля **спекулатионконтрол**.</span><span class="sxs-lookup"><span data-stu-id="13c3b-131">`Update-Module` uses the **Name** parameter to specify the module, **SpeculationControl**.</span></span> <span data-ttu-id="13c3b-132">Параметр **RequiredVersion** указывает версию **1.0.14**.</span><span class="sxs-lookup"><span data-stu-id="13c3b-132">The **RequiredVersion** parameter specifies the version, **1.0.14**.</span></span>

### <span data-ttu-id="13c3b-133">Пример 5. обновление модуля без подтверждения</span><span class="sxs-lookup"><span data-stu-id="13c3b-133">Example 5: Update a module without confirmation</span></span>

<span data-ttu-id="13c3b-134">В этом примере не запрашивается подтверждение для обновления модуля до последней версии из интерактивной коллекции.</span><span class="sxs-lookup"><span data-stu-id="13c3b-134">This example doesn't request confirmation to update the module to the newest version from an online gallery.</span></span> <span data-ttu-id="13c3b-135">Если модуль уже установлен, параметр **Force** переустанавливает модуль.</span><span class="sxs-lookup"><span data-stu-id="13c3b-135">If the module is already installed, the **Force** parameter reinstalls the module.</span></span>

```powershell
Update-Module -Name SpeculationControl -Force
```

<span data-ttu-id="13c3b-136">`Update-Module` использует параметр **Name** для указания модуля **спекулатионконтрол**.</span><span class="sxs-lookup"><span data-stu-id="13c3b-136">`Update-Module` uses the **Name** parameter to specify the module, **SpeculationControl**.</span></span> <span data-ttu-id="13c3b-137">Параметр **Force** обновляет модуль без запроса подтверждения пользователя.</span><span class="sxs-lookup"><span data-stu-id="13c3b-137">The **Force** parameter updates the module without requesting user confirmation.</span></span>

## <span data-ttu-id="13c3b-138">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="13c3b-138">PARAMETERS</span></span>

### <span data-ttu-id="13c3b-139">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="13c3b-139">-AcceptLicense</span></span>

<span data-ttu-id="13c3b-140">Автоматически принимать лицензионное соглашение во время установки, если оно требуется для пакета.</span><span class="sxs-lookup"><span data-stu-id="13c3b-140">Automatically accept the license agreement during installation if the package requires it.</span></span>

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

### <span data-ttu-id="13c3b-141">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="13c3b-141">-AllowPrerelease</span></span>

<span data-ttu-id="13c3b-142">Позволяет обновить модуль, используя новый модуль, помеченный как предварительный выпуск.</span><span class="sxs-lookup"><span data-stu-id="13c3b-142">Allows you to update a module with the newer module marked as a prerelease.</span></span>

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

### <span data-ttu-id="13c3b-143">-Confirm</span><span class="sxs-lookup"><span data-stu-id="13c3b-143">-Confirm</span></span>

<span data-ttu-id="13c3b-144">Запрашивает подтверждение перед запуском `Update-Module` .</span><span class="sxs-lookup"><span data-stu-id="13c3b-144">Prompts you for confirmation before running `Update-Module`.</span></span>

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

### <span data-ttu-id="13c3b-145">-Credential</span><span class="sxs-lookup"><span data-stu-id="13c3b-145">-Credential</span></span>

<span data-ttu-id="13c3b-146">Указывает учетную запись пользователя, имеющую разрешение на обновление модуля.</span><span class="sxs-lookup"><span data-stu-id="13c3b-146">Specifies a user account that has permission to update a module.</span></span>

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

### <span data-ttu-id="13c3b-147">-Force</span><span class="sxs-lookup"><span data-stu-id="13c3b-147">-Force</span></span>

<span data-ttu-id="13c3b-148">Принудительно обновляет каждый указанный модуль без запроса на подтверждение.</span><span class="sxs-lookup"><span data-stu-id="13c3b-148">Forces an update of each specified module without a prompt to request confirmation.</span></span> <span data-ttu-id="13c3b-149">Если модуль уже установлен, **принудительно** переустанавливает модуль.</span><span class="sxs-lookup"><span data-stu-id="13c3b-149">If the module is already installed, **Force** reinstalls the module.</span></span>

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

### <span data-ttu-id="13c3b-150">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="13c3b-150">-MaximumVersion</span></span>

<span data-ttu-id="13c3b-151">Указывает максимальную версию одного модуля для обновления.</span><span class="sxs-lookup"><span data-stu-id="13c3b-151">Specifies the maximum version of a single module to update.</span></span> <span data-ttu-id="13c3b-152">Вы не можете добавить этот параметр, если пытаетесь обновить несколько модулей.</span><span class="sxs-lookup"><span data-stu-id="13c3b-152">You can't add this parameter if you're attempting to update multiple modules.</span></span> <span data-ttu-id="13c3b-153">Параметры **MaximumVersion** и **RequiredVersion** нельзя использовать в одной команде.</span><span class="sxs-lookup"><span data-stu-id="13c3b-153">The **MaximumVersion** and the **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="13c3b-154">-Name</span><span class="sxs-lookup"><span data-stu-id="13c3b-154">-Name</span></span>

<span data-ttu-id="13c3b-155">Указывает имена одного или нескольких модулей для обновления.</span><span class="sxs-lookup"><span data-stu-id="13c3b-155">Specifies the names of one or more modules to update.</span></span> <span data-ttu-id="13c3b-156">`Update-Module` выполняет поиск `$env:PSModulePath` модулей для обновления.</span><span class="sxs-lookup"><span data-stu-id="13c3b-156">`Update-Module` searches `$env:PSModulePath` for the modules to update.</span></span> <span data-ttu-id="13c3b-157">Если в `$env:PSModulePath` для указанного имени модуля не найдено совпадений, возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="13c3b-157">If no matches are found in `$env:PSModulePath` for the specified module name, an error occurs.</span></span>

<span data-ttu-id="13c3b-158">Подстановочные знаки принимаются в именах модулей.</span><span class="sxs-lookup"><span data-stu-id="13c3b-158">Wildcards are accepted in module names.</span></span> <span data-ttu-id="13c3b-159">Если добавить подстановочные знаки к указанному имени и совпадений не найдено, ошибка не возникает.</span><span class="sxs-lookup"><span data-stu-id="13c3b-159">If you add wildcard characters to the specified name and no matches are found, no error occurs.</span></span>

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

### <span data-ttu-id="13c3b-160">-PassThru</span><span class="sxs-lookup"><span data-stu-id="13c3b-160">-PassThru</span></span>

<span data-ttu-id="13c3b-161">Возвращает объект, представляющий элемент, с которым вы работаете.</span><span class="sxs-lookup"><span data-stu-id="13c3b-161">Returns an object representing the item with which you are working.</span></span> <span data-ttu-id="13c3b-162">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="13c3b-162">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="13c3b-163">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="13c3b-163">-Proxy</span></span>

<span data-ttu-id="13c3b-164">Указывает прокси-сервер для запроса, а не напрямуюе подключение к Интернет-ресурсу.</span><span class="sxs-lookup"><span data-stu-id="13c3b-164">Specifies a proxy server for the request, rather than connecting directly to an internet resource.</span></span>

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

### <span data-ttu-id="13c3b-165">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="13c3b-165">-ProxyCredential</span></span>

<span data-ttu-id="13c3b-166">Указывает учетную запись пользователя, имеющую разрешение на использование прокси-сервера, указанного параметром **прокси** .</span><span class="sxs-lookup"><span data-stu-id="13c3b-166">Specifies a user account that has permission to use the proxy server specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="13c3b-167">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="13c3b-167">-RequiredVersion</span></span>

<span data-ttu-id="13c3b-168">Указывает точную версию, до которой будет обновлен существующий установленный модуль.</span><span class="sxs-lookup"><span data-stu-id="13c3b-168">Specifies the exact version to which the existing installed module will be updated.</span></span> <span data-ttu-id="13c3b-169">Версия, указанная в параметре **RequiredVersion** , должна существовать в интерактивной коллекции, иначе отображается ошибка.</span><span class="sxs-lookup"><span data-stu-id="13c3b-169">The version specified by **RequiredVersion** must exist in the online gallery or an error is displayed.</span></span> <span data-ttu-id="13c3b-170">Если в одной команде обновляется несколько модулей, нельзя использовать **RequiredVersion**.</span><span class="sxs-lookup"><span data-stu-id="13c3b-170">If more than one module is updated in a single command, you can't use **RequiredVersion**.</span></span>

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

### <span data-ttu-id="13c3b-171">-Scope</span><span class="sxs-lookup"><span data-stu-id="13c3b-171">-Scope</span></span>

<span data-ttu-id="13c3b-172">Задает область установки модуля.</span><span class="sxs-lookup"><span data-stu-id="13c3b-172">Specifies the installation scope of the module.</span></span> <span data-ttu-id="13c3b-173">Допустимые значения для этого параметра: **ALLUSERS** и **CurrentUser**.</span><span class="sxs-lookup"><span data-stu-id="13c3b-173">The acceptable values for this parameter are **AllUsers** and **CurrentUser**.</span></span> <span data-ttu-id="13c3b-174">Если **область** не указана, обновление устанавливается в области **CurrentUser** .</span><span class="sxs-lookup"><span data-stu-id="13c3b-174">If **Scope** isn't specified, the update is installed in the **CurrentUser** scope.</span></span>

<span data-ttu-id="13c3b-175">Область **ALLUSERS** требует повышенных разрешений и устанавливает модули в расположение, доступное всем пользователям компьютера:</span><span class="sxs-lookup"><span data-stu-id="13c3b-175">The **AllUsers** scope requires elevated permissions and installs modules in a location that is accessible to all users of the computer:</span></span>

`$env:ProgramFiles\PowerShell\Modules`

<span data-ttu-id="13c3b-176">Параметр **CurrentUser** не требует повышенных разрешений и устанавливает модули в расположении, доступном только текущему пользователю компьютера:</span><span class="sxs-lookup"><span data-stu-id="13c3b-176">The **CurrentUser** doesn't require elevated permissions and installs modules in a location that is accessible only to the current user of the computer:</span></span>

`$home\Documents\PowerShell\Modules`

<span data-ttu-id="13c3b-177">Если **область** не определена, значение по умолчанию задается на основе версии PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="13c3b-177">When no **Scope** is defined, the default is set based on the PowerShellGet version.</span></span>

- <span data-ttu-id="13c3b-178">В PowerShellGet версий 2.0.0 и выше значение по умолчанию — **CurrentUser**, что не требует повышения прав для установки.</span><span class="sxs-lookup"><span data-stu-id="13c3b-178">In PowerShellGet versions 2.0.0 and above, the default is **CurrentUser**, which does not require elevation for install.</span></span>
- <span data-ttu-id="13c3b-179">В PowerShellGet версии 1. x значение по умолчанию — **ALLUSERS**, что требует повышения прав для установки.</span><span class="sxs-lookup"><span data-stu-id="13c3b-179">In PowerShellGet 1.x versions, the default is **AllUsers**, which requires elevation for install.</span></span>

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

### <span data-ttu-id="13c3b-180">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="13c3b-180">-WhatIf</span></span>

<span data-ttu-id="13c3b-181">Показывает, что произойдет при `Update-Module` запуске.</span><span class="sxs-lookup"><span data-stu-id="13c3b-181">Shows what would happen if `Update-Module` runs.</span></span> <span data-ttu-id="13c3b-182">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="13c3b-182">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="13c3b-183">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="13c3b-183">CommonParameters</span></span>

<span data-ttu-id="13c3b-184">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="13c3b-184">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="13c3b-185">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="13c3b-185">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="13c3b-186">Входные данные</span><span class="sxs-lookup"><span data-stu-id="13c3b-186">INPUTS</span></span>

### <span data-ttu-id="13c3b-187">System.String[]</span><span class="sxs-lookup"><span data-stu-id="13c3b-187">System.String[]</span></span>

### <span data-ttu-id="13c3b-188">System.String</span><span class="sxs-lookup"><span data-stu-id="13c3b-188">System.String</span></span>

### <span data-ttu-id="13c3b-189">System.Management.Automation.PSCredential</span><span class="sxs-lookup"><span data-stu-id="13c3b-189">System.Management.Automation.PSCredential</span></span>

### <span data-ttu-id="13c3b-190">System.Uri</span><span class="sxs-lookup"><span data-stu-id="13c3b-190">System.Uri</span></span>

## <span data-ttu-id="13c3b-191">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="13c3b-191">OUTPUTS</span></span>

### <span data-ttu-id="13c3b-192">System.Object</span><span class="sxs-lookup"><span data-stu-id="13c3b-192">System.Object</span></span>

## <span data-ttu-id="13c3b-193">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="13c3b-193">NOTES</span></span>

<span data-ttu-id="13c3b-194">Для PowerShell версии 6,0 и более поздней областью установки по умолчанию всегда является **CurrentUser**.</span><span class="sxs-lookup"><span data-stu-id="13c3b-194">For PowerShell version 6.0 and above, the default installation scope is always **CurrentUser**.</span></span>
<span data-ttu-id="13c3b-195">Обновления модулей для **CurrentUser**, `$home\Documents\PowerShell\Modules` не требуют повышенных разрешений.</span><span class="sxs-lookup"><span data-stu-id="13c3b-195">Module updates for **CurrentUser**, `$home\Documents\PowerShell\Modules`, don't need elevated permissions.</span></span> <span data-ttu-id="13c3b-196">Обновления модулей для **ALLUSERS**, `$env:ProgramFiles\PowerShell\Modules` требуют повышенных разрешений.</span><span class="sxs-lookup"><span data-stu-id="13c3b-196">Module updates for **AllUsers**, `$env:ProgramFiles\PowerShell\Modules`, need elevated permissions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="13c3b-197">Начиная с апреля 2020 года коллекция PowerShell не поддерживает протокол TLS (Transport Layer Security) версий 1.0 и 1.1.</span><span class="sxs-lookup"><span data-stu-id="13c3b-197">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="13c3b-198">Если вы не используете TLS 1.2 или более поздней версии, при попытке доступа к коллекции PowerShell возникнет ошибка.</span><span class="sxs-lookup"><span data-stu-id="13c3b-198">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="13c3b-199">Чтобы проверить, используется ли TLS 1.2, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="13c3b-199">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="13c3b-200">Дополнительные сведения см. в [объявлении](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) в блоге, посвященном PowerShell.</span><span class="sxs-lookup"><span data-stu-id="13c3b-200">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

<span data-ttu-id="13c3b-201">`Update-Module` работает в PowerShell 3,0 или более поздних версиях PowerShell, в Windows 7 или Windows 2008 R2 и более поздних версиях Windows.</span><span class="sxs-lookup"><span data-stu-id="13c3b-201">`Update-Module` runs on PowerShell 3.0 or later releases of PowerShell, on Windows 7 or Windows 2008 R2 and later releases of Windows.</span></span>

<span data-ttu-id="13c3b-202">Если модуль, указанный с параметром **Name** , не был установлен с помощью `Install-Module` , возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="13c3b-202">If the module that you specify with the **Name** parameter wasn't installed by using `Install-Module`, an error occurs.</span></span>

<span data-ttu-id="13c3b-203">Вы можете работать только с `Update-Module` модулями, установленными из коллекции в Интернете, запустив `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="13c3b-203">You can only run `Update-Module` on modules that you installed from the online gallery by running `Install-Module`.</span></span>

<span data-ttu-id="13c3b-204">При `Update-Module` попытке обновить двоичные файлы, которые используются, `Update-Module` возвращает ошибку, определяющую проблемные процессы.</span><span class="sxs-lookup"><span data-stu-id="13c3b-204">If `Update-Module` attempts to update binaries that are in use, `Update-Module` returns an error that identifies the problem processes.</span></span> <span data-ttu-id="13c3b-205">Пользователю будет сообщено повторить попытку `Update-Module` после остановки процессов.</span><span class="sxs-lookup"><span data-stu-id="13c3b-205">The user is informed to retry `Update-Module` after the processes are stopped.</span></span>

## <span data-ttu-id="13c3b-206">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="13c3b-206">RELATED LINKS</span></span>

[<span data-ttu-id="13c3b-207">Find-Module</span><span class="sxs-lookup"><span data-stu-id="13c3b-207">Find-Module</span></span>](Find-Module.md)

[<span data-ttu-id="13c3b-208">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="13c3b-208">Get-InstalledModule</span></span>](Get-InstalledModule.md)

[<span data-ttu-id="13c3b-209">Install-Module</span><span class="sxs-lookup"><span data-stu-id="13c3b-209">Install-Module</span></span>](Install-Module.md)

[<span data-ttu-id="13c3b-210">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="13c3b-210">Publish-Module</span></span>](Publish-Module.md)

[<span data-ttu-id="13c3b-211">Uninstall — Module</span><span class="sxs-lookup"><span data-stu-id="13c3b-211">Uninstall-Module</span></span>](Uninstall-Module.md)
