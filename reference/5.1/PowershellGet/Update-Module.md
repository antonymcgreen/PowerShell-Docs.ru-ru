---
external help file: PSModule-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/16/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/update-module?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-Module
ms.openlocfilehash: ee94ba7808cb364306826325cfbc3df2cf9834a5
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "94892592"
---
# <span data-ttu-id="c00f7-103">Update-Module</span><span class="sxs-lookup"><span data-stu-id="c00f7-103">Update-Module</span></span>

## <span data-ttu-id="c00f7-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="c00f7-104">SYNOPSIS</span></span>
<span data-ttu-id="c00f7-105">Скачивает последние версии указанных модулей из веб-коллекции и устанавливает их на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="c00f7-105">Downloads and installs the newest version of specified modules from an online gallery to the local computer.</span></span>

## <span data-ttu-id="c00f7-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c00f7-106">SYNTAX</span></span>

### <span data-ttu-id="c00f7-107">Все</span><span class="sxs-lookup"><span data-stu-id="c00f7-107">All</span></span>

```
Update-Module [[-Name] <String[]>] [-RequiredVersion <String>] [-MaximumVersion <String>]
 [-Credential <PSCredential>] [-Scope <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-Force] [-AllowPrerelease] [-AcceptLicense] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="c00f7-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c00f7-108">DESCRIPTION</span></span>

<span data-ttu-id="c00f7-109">`Update-Module`Командлет устанавливает последнюю версию модуля из веб-коллекции.</span><span class="sxs-lookup"><span data-stu-id="c00f7-109">The `Update-Module` cmdlet installs a module's newest version from an online gallery.</span></span> <span data-ttu-id="c00f7-110">Перед установкой появится запрос на подтверждение обновления.</span><span class="sxs-lookup"><span data-stu-id="c00f7-110">You're prompted to confirm the update before it's installed.</span></span> <span data-ttu-id="c00f7-111">Обновления устанавливаются только для модулей, установленных на локальном компьютере с `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="c00f7-111">Updates are installed only for modules that were installed on the local computer with `Install-Module`.</span></span> <span data-ttu-id="c00f7-112">`Update-Module` выполняет поиск `$env:PSModulePath` установленных модулей.</span><span class="sxs-lookup"><span data-stu-id="c00f7-112">`Update-Module` searches `$env:PSModulePath` for installed modules.</span></span>

<span data-ttu-id="c00f7-113">`Update-Module` без указания параметров обновляет все установленные модули.</span><span class="sxs-lookup"><span data-stu-id="c00f7-113">`Update-Module` with no parameters specified updates all installed modules.</span></span> <span data-ttu-id="c00f7-114">Чтобы указать обновляемый модуль, используйте параметр **Name** .</span><span class="sxs-lookup"><span data-stu-id="c00f7-114">To specify a module to update, use the **Name** parameter.</span></span> <span data-ttu-id="c00f7-115">Можно выполнить обновление до определенной версии модуля с помощью параметра **RequiredVersion** .</span><span class="sxs-lookup"><span data-stu-id="c00f7-115">You can update to a module's specific version by using the **RequiredVersion** parameter.</span></span>

<span data-ttu-id="c00f7-116">Если установленный модуль уже является последней версией, модуль не обновляется.</span><span class="sxs-lookup"><span data-stu-id="c00f7-116">If an installed module is already the newest version, the module isn't updated.</span></span> <span data-ttu-id="c00f7-117">Если модуль не найден в `$env:PSModulePath` , выводится сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="c00f7-117">If the module isn't found in `$env:PSModulePath`, an error is displayed.</span></span>

<span data-ttu-id="c00f7-118">Чтобы отобразить установленные модули, используйте `Get-InstalledModule` .</span><span class="sxs-lookup"><span data-stu-id="c00f7-118">To display the installed modules, use `Get-InstalledModule`.</span></span>

## <span data-ttu-id="c00f7-119">Примеры</span><span class="sxs-lookup"><span data-stu-id="c00f7-119">EXAMPLES</span></span>

### <span data-ttu-id="c00f7-120">Пример 1. обновление всех модулей</span><span class="sxs-lookup"><span data-stu-id="c00f7-120">Example 1: Update all modules</span></span>

<span data-ttu-id="c00f7-121">В этом примере все установленные модули обновляются до последней версии в интерактивной коллекции.</span><span class="sxs-lookup"><span data-stu-id="c00f7-121">This example updates all installed modules to the newest version in an online gallery.</span></span>

```powershell
Update-Module
```

### <span data-ttu-id="c00f7-122">Пример 2. обновление модуля по имени</span><span class="sxs-lookup"><span data-stu-id="c00f7-122">Example 2: Update a module by name</span></span>

<span data-ttu-id="c00f7-123">В этом примере заданный модуль обновляется до последней версии в интерактивной коллекции.</span><span class="sxs-lookup"><span data-stu-id="c00f7-123">This example updates a specific module to the newest version in an online gallery.</span></span>

```powershell
Update-Module -Name SpeculationControl
```

<span data-ttu-id="c00f7-124">`Update-Module` использует параметр **Name** для обновления конкретного модуля **спекулатионконтрол**.</span><span class="sxs-lookup"><span data-stu-id="c00f7-124">`Update-Module` uses the **Name** parameter to update a specific module, **SpeculationControl**.</span></span>

### <span data-ttu-id="c00f7-125">Пример 3. Просмотр Update-Module запусков</span><span class="sxs-lookup"><span data-stu-id="c00f7-125">Example 3: View what-if Update-Module runs</span></span>

<span data-ttu-id="c00f7-126">В этом примере сценарий "что если" показывает, что происходит при `Update-Module` запуске.</span><span class="sxs-lookup"><span data-stu-id="c00f7-126">This example does a what-if scenario to show what happens if `Update-Module` is run.</span></span> <span data-ttu-id="c00f7-127">Команда не выполняется.</span><span class="sxs-lookup"><span data-stu-id="c00f7-127">The command isn't run.</span></span>

```powershell
Update-Module -WhatIf
```

```Output
What if: Performing the operation "Update-Module" on target "Version '2.8.0' of module
  'Carbon', updating to version '2.8.1'".
What if: Performing the operation "Update-Module" on target "Version '1.0.10' of module
  'SpeculationControl', updating to version '1.0.14'".
```

<span data-ttu-id="c00f7-128">`Update-Module` использует параметр **WhatIf** , чтобы отобразить, что произойдет при `Update-Module` запуске.</span><span class="sxs-lookup"><span data-stu-id="c00f7-128">`Update-Module` uses the **WhatIf** parameter display what would happen if `Update-Module` were run.</span></span>

### <span data-ttu-id="c00f7-129">Пример 4. обновление модуля до указанной версии</span><span class="sxs-lookup"><span data-stu-id="c00f7-129">Example 4: Update a module to a specified version</span></span>

<span data-ttu-id="c00f7-130">В этом примере модуль обновляется до определенной версии.</span><span class="sxs-lookup"><span data-stu-id="c00f7-130">In this example, a module is updated to a specific version.</span></span> <span data-ttu-id="c00f7-131">Версия должна существовать в интерактивной коллекции, или отображается ошибка.</span><span class="sxs-lookup"><span data-stu-id="c00f7-131">The version must exist in the online gallery or an error is displayed.</span></span>

```powershell
Update-Module -Name SpeculationControl -RequiredVersion 1.0.14
```

<span data-ttu-id="c00f7-132">`Update-Module` использует параметр **Name** для указания модуля **спекулатионконтрол**.</span><span class="sxs-lookup"><span data-stu-id="c00f7-132">`Update-Module` uses the **Name** parameter to specify the module, **SpeculationControl**.</span></span> <span data-ttu-id="c00f7-133">Параметр **RequiredVersion** указывает версию **1.0.14**.</span><span class="sxs-lookup"><span data-stu-id="c00f7-133">The **RequiredVersion** parameter specifies the version, **1.0.14**.</span></span>

### <span data-ttu-id="c00f7-134">Пример 5. обновление модуля без подтверждения</span><span class="sxs-lookup"><span data-stu-id="c00f7-134">Example 5: Update a module without confirmation</span></span>

<span data-ttu-id="c00f7-135">В этом примере не запрашивается подтверждение для обновления модуля до последней версии из интерактивной коллекции.</span><span class="sxs-lookup"><span data-stu-id="c00f7-135">This example doesn't request confirmation to update the module to the newest version from an online gallery.</span></span> <span data-ttu-id="c00f7-136">Если модуль уже установлен, параметр **Force** переустанавливает модуль.</span><span class="sxs-lookup"><span data-stu-id="c00f7-136">If the module is already installed, the **Force** parameter reinstalls the module.</span></span>

```powershell
Update-Module -Name SpeculationControl -Force
```

<span data-ttu-id="c00f7-137">`Update-Module` использует параметр **Name** для указания модуля **спекулатионконтрол**.</span><span class="sxs-lookup"><span data-stu-id="c00f7-137">`Update-Module` uses the **Name** parameter to specify the module, **SpeculationControl**.</span></span> <span data-ttu-id="c00f7-138">Параметр **Force** обновляет модуль без запроса подтверждения пользователя.</span><span class="sxs-lookup"><span data-stu-id="c00f7-138">The **Force** parameter updates the module without requesting user confirmation.</span></span>

## <span data-ttu-id="c00f7-139">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c00f7-139">PARAMETERS</span></span>

### <span data-ttu-id="c00f7-140">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="c00f7-140">-AcceptLicense</span></span>

<span data-ttu-id="c00f7-141">Автоматически принимать лицензионное соглашение во время установки, если оно требуется для пакета.</span><span class="sxs-lookup"><span data-stu-id="c00f7-141">Automatically accept the license agreement during installation if the package requires it.</span></span>

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

### <span data-ttu-id="c00f7-142">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="c00f7-142">-AllowPrerelease</span></span>

<span data-ttu-id="c00f7-143">Позволяет обновить модуль, используя новый модуль, помеченный как предварительный выпуск.</span><span class="sxs-lookup"><span data-stu-id="c00f7-143">Allows you to update a module with the newer module marked as a prerelease.</span></span>

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

### <span data-ttu-id="c00f7-144">-Confirm</span><span class="sxs-lookup"><span data-stu-id="c00f7-144">-Confirm</span></span>

<span data-ttu-id="c00f7-145">Запрашивает подтверждение перед запуском `Update-Module` .</span><span class="sxs-lookup"><span data-stu-id="c00f7-145">Prompts you for confirmation before running `Update-Module`.</span></span>

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

### <span data-ttu-id="c00f7-146">-Credential</span><span class="sxs-lookup"><span data-stu-id="c00f7-146">-Credential</span></span>

<span data-ttu-id="c00f7-147">Указывает учетную запись пользователя, имеющую разрешение на обновление модуля.</span><span class="sxs-lookup"><span data-stu-id="c00f7-147">Specifies a user account that has permission to update a module.</span></span>

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

### <span data-ttu-id="c00f7-148">-Force</span><span class="sxs-lookup"><span data-stu-id="c00f7-148">-Force</span></span>

<span data-ttu-id="c00f7-149">Принудительно обновляет каждый указанный модуль без запроса на подтверждение.</span><span class="sxs-lookup"><span data-stu-id="c00f7-149">Forces an update of each specified module without a prompt to request confirmation.</span></span> <span data-ttu-id="c00f7-150">Если модуль уже установлен, **принудительно** переустанавливает модуль.</span><span class="sxs-lookup"><span data-stu-id="c00f7-150">If the module is already installed, **Force** reinstalls the module.</span></span>

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

### <span data-ttu-id="c00f7-151">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="c00f7-151">-MaximumVersion</span></span>

<span data-ttu-id="c00f7-152">Указывает максимальную версию одного модуля для обновления.</span><span class="sxs-lookup"><span data-stu-id="c00f7-152">Specifies the maximum version of a single module to update.</span></span> <span data-ttu-id="c00f7-153">Вы не можете добавить этот параметр, если пытаетесь обновить несколько модулей.</span><span class="sxs-lookup"><span data-stu-id="c00f7-153">You can't add this parameter if you're attempting to update multiple modules.</span></span> <span data-ttu-id="c00f7-154">Параметры **MaximumVersion** и **RequiredVersion** нельзя использовать в одной команде.</span><span class="sxs-lookup"><span data-stu-id="c00f7-154">The **MaximumVersion** and the **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="c00f7-155">-Name</span><span class="sxs-lookup"><span data-stu-id="c00f7-155">-Name</span></span>

<span data-ttu-id="c00f7-156">Указывает имена одного или нескольких модулей для обновления.</span><span class="sxs-lookup"><span data-stu-id="c00f7-156">Specifies the names of one or more modules to update.</span></span> <span data-ttu-id="c00f7-157">`Update-Module` выполняет поиск `$env:PSModulePath` модулей для обновления.</span><span class="sxs-lookup"><span data-stu-id="c00f7-157">`Update-Module` searches `$env:PSModulePath` for the modules to update.</span></span> <span data-ttu-id="c00f7-158">Если в `$env:PSModulePath` для указанного имени модуля не найдено совпадений, возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="c00f7-158">If no matches are found in `$env:PSModulePath` for the specified module name, an error occurs.</span></span>

<span data-ttu-id="c00f7-159">Подстановочные знаки принимаются в именах модулей.</span><span class="sxs-lookup"><span data-stu-id="c00f7-159">Wildcards are accepted in module names.</span></span> <span data-ttu-id="c00f7-160">Если добавить подстановочные знаки к указанному имени и совпадений не найдено, ошибка не возникает.</span><span class="sxs-lookup"><span data-stu-id="c00f7-160">If you add wildcard characters to the specified name and no matches are found, no error occurs.</span></span>

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

### <span data-ttu-id="c00f7-161">-PassThru</span><span class="sxs-lookup"><span data-stu-id="c00f7-161">-PassThru</span></span>

<span data-ttu-id="c00f7-162">Возвращает объект, представляющий элемент, с которым вы работаете.</span><span class="sxs-lookup"><span data-stu-id="c00f7-162">Returns an object representing the item with which you are working.</span></span> <span data-ttu-id="c00f7-163">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="c00f7-163">By default, this cmdlet does not generate any output.</span></span> <span data-ttu-id="c00f7-164">Поддержка параметра **PassThru** была добавлена в **PowerShellGet** 2.0.0</span><span class="sxs-lookup"><span data-stu-id="c00f7-164">The **PassThru** parameter support was added in **PowerShellGet** 2.0.0</span></span>

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

### <span data-ttu-id="c00f7-165">Прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="c00f7-165">-Proxy</span></span>

<span data-ttu-id="c00f7-166">Указывает прокси-сервер для запроса, а не напрямуюе подключение к Интернет-ресурсу.</span><span class="sxs-lookup"><span data-stu-id="c00f7-166">Specifies a proxy server for the request, rather than connecting directly to an internet resource.</span></span>

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

### <span data-ttu-id="c00f7-167">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="c00f7-167">-ProxyCredential</span></span>

<span data-ttu-id="c00f7-168">Указывает учетную запись пользователя, имеющую разрешение на использование прокси-сервера, указанного параметром **прокси** .</span><span class="sxs-lookup"><span data-stu-id="c00f7-168">Specifies a user account that has permission to use the proxy server specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="c00f7-169">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="c00f7-169">-RequiredVersion</span></span>

<span data-ttu-id="c00f7-170">Указывает точную версию, до которой будет обновлен существующий установленный модуль.</span><span class="sxs-lookup"><span data-stu-id="c00f7-170">Specifies the exact version to which the existing installed module will be updated.</span></span> <span data-ttu-id="c00f7-171">Версия, указанная в параметре **RequiredVersion** , должна существовать в интерактивной коллекции, иначе отображается ошибка.</span><span class="sxs-lookup"><span data-stu-id="c00f7-171">The version specified by **RequiredVersion** must exist in the online gallery or an error is displayed.</span></span> <span data-ttu-id="c00f7-172">Если в одной команде обновляется несколько модулей, нельзя использовать **RequiredVersion**.</span><span class="sxs-lookup"><span data-stu-id="c00f7-172">If more than one module is updated in a single command, you can't use **RequiredVersion**.</span></span>

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

### <span data-ttu-id="c00f7-173">-Scope</span><span class="sxs-lookup"><span data-stu-id="c00f7-173">-Scope</span></span>

<span data-ttu-id="c00f7-174">Задает область установки модуля.</span><span class="sxs-lookup"><span data-stu-id="c00f7-174">Specifies the installation scope of the module.</span></span> <span data-ttu-id="c00f7-175">Допустимые значения для этого параметра: **ALLUSERS** и **CurrentUser**.</span><span class="sxs-lookup"><span data-stu-id="c00f7-175">The acceptable values for this parameter are **AllUsers** and **CurrentUser**.</span></span> <span data-ttu-id="c00f7-176">Если **область** не указана, обновление устанавливается в области **CurrentUser** .</span><span class="sxs-lookup"><span data-stu-id="c00f7-176">If **Scope** isn't specified, the update is installed in the **CurrentUser** scope.</span></span>

<span data-ttu-id="c00f7-177">Область **ALLUSERS** требует повышенных разрешений и устанавливает модули в расположение, доступное всем пользователям компьютера:</span><span class="sxs-lookup"><span data-stu-id="c00f7-177">The **AllUsers** scope requires elevated permissions and installs modules in a location that is accessible to all users of the computer:</span></span>

`$env:ProgramFiles\PowerShell\Modules`

<span data-ttu-id="c00f7-178">Параметр **CurrentUser** не требует повышенных разрешений и устанавливает модули в расположении, доступном только текущему пользователю компьютера:</span><span class="sxs-lookup"><span data-stu-id="c00f7-178">The **CurrentUser** doesn't require elevated permissions and installs modules in a location that is accessible only to the current user of the computer:</span></span>

`$home\Documents\PowerShell\Modules`

<span data-ttu-id="c00f7-179">Если **область** не определена, значение по умолчанию задается на основе версии PowerShellGet.</span><span class="sxs-lookup"><span data-stu-id="c00f7-179">When no **Scope** is defined, the default is set based on the PowerShellGet version.</span></span>

- <span data-ttu-id="c00f7-180">В PowerShellGet версий 2.0.0 и выше значение по умолчанию — **ALLUSERS** при запуске сеанса с повышенными правами и **CurrentUser** для всех остальных.</span><span class="sxs-lookup"><span data-stu-id="c00f7-180">In PowerShellGet versions 2.0.0 and above, the default is **AllUsers** when running an elevated session and **CurrentUser** for all others.</span></span>
- <span data-ttu-id="c00f7-181">В PowerShellGet версии 1. x значение по умолчанию — **ALLUSERS**, что требует повышения прав для установки.</span><span class="sxs-lookup"><span data-stu-id="c00f7-181">In PowerShellGet 1.x versions, the default is **AllUsers**, which requires elevation for install.</span></span>

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

### <span data-ttu-id="c00f7-182">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="c00f7-182">-WhatIf</span></span>

<span data-ttu-id="c00f7-183">Показывает, что произойдет при `Update-Module` запуске.</span><span class="sxs-lookup"><span data-stu-id="c00f7-183">Shows what would happen if `Update-Module` runs.</span></span> <span data-ttu-id="c00f7-184">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="c00f7-184">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="c00f7-185">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="c00f7-185">CommonParameters</span></span>

<span data-ttu-id="c00f7-186">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c00f7-186">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c00f7-187">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c00f7-187">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c00f7-188">Входные данные</span><span class="sxs-lookup"><span data-stu-id="c00f7-188">INPUTS</span></span>

### <span data-ttu-id="c00f7-189">System.String[]</span><span class="sxs-lookup"><span data-stu-id="c00f7-189">System.String[]</span></span>

### <span data-ttu-id="c00f7-190">System.String</span><span class="sxs-lookup"><span data-stu-id="c00f7-190">System.String</span></span>

### <span data-ttu-id="c00f7-191">System.Management.Automation.PSCredential</span><span class="sxs-lookup"><span data-stu-id="c00f7-191">System.Management.Automation.PSCredential</span></span>

### <span data-ttu-id="c00f7-192">System.Uri</span><span class="sxs-lookup"><span data-stu-id="c00f7-192">System.Uri</span></span>

## <span data-ttu-id="c00f7-193">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="c00f7-193">OUTPUTS</span></span>

### <span data-ttu-id="c00f7-194">System.Object</span><span class="sxs-lookup"><span data-stu-id="c00f7-194">System.Object</span></span>

## <span data-ttu-id="c00f7-195">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="c00f7-195">NOTES</span></span>

<span data-ttu-id="c00f7-196">Для PowerShell 5,1 или ниже областью по умолчанию в сеансе с повышенными правами является **ALLUSERS** и в сеансе без повышенных привилегий **CurrentUser**.</span><span class="sxs-lookup"><span data-stu-id="c00f7-196">For PowerShell 5.1 or below, the default scope in an elevated session is **AllUsers**, and in a non-elevated session, **CurrentUser**.</span></span> <span data-ttu-id="c00f7-197">Обновления модулей для **ALLUSERS**, `$env:ProgramFiles\PowerShell\Modules` требуют повышенных разрешений.</span><span class="sxs-lookup"><span data-stu-id="c00f7-197">Module updates for **AllUsers**, `$env:ProgramFiles\PowerShell\Modules`, need elevated permissions.</span></span> <span data-ttu-id="c00f7-198">Обновления модулей для **CurrentUser**, `$home\Documents\PowerShell\Modules` не требуют повышенных разрешений.</span><span class="sxs-lookup"><span data-stu-id="c00f7-198">Module updates for **CurrentUser**, `$home\Documents\PowerShell\Modules`, don't need elevated permissions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c00f7-199">По состоянию на апрель 2020 коллекция PowerShell больше не поддерживает TLS-версии 1,0 и 1,1.</span><span class="sxs-lookup"><span data-stu-id="c00f7-199">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="c00f7-200">Если вы не используете TLS 1,2 или более поздней версии, при попытке доступа к коллекция PowerShell возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="c00f7-200">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="c00f7-201">Используйте следующую команду, чтобы убедиться, что используется TLS 1,2:</span><span class="sxs-lookup"><span data-stu-id="c00f7-201">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="c00f7-202">Дополнительные сведения см. в [объявлении](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) в блоге PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c00f7-202">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

<span data-ttu-id="c00f7-203">`Update-Module` работает в PowerShell 3,0 или более поздних версиях PowerShell, в Windows 7 или Windows 2008 R2 и более поздних версиях Windows.</span><span class="sxs-lookup"><span data-stu-id="c00f7-203">`Update-Module` runs on PowerShell 3.0 or later releases of PowerShell, on Windows 7 or Windows 2008 R2 and later releases of Windows.</span></span>

<span data-ttu-id="c00f7-204">Если модуль, указанный с параметром **Name** , не был установлен с помощью `Install-Module` , возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="c00f7-204">If the module that you specify with the **Name** parameter wasn't installed by using `Install-Module`, an error occurs.</span></span>

<span data-ttu-id="c00f7-205">Вы можете работать только с `Update-Module` модулями, установленными из коллекции в Интернете, запустив `Install-Module` .</span><span class="sxs-lookup"><span data-stu-id="c00f7-205">You can only run `Update-Module` on modules that you installed from the online gallery by running `Install-Module`.</span></span>

<span data-ttu-id="c00f7-206">При `Update-Module` попытке обновить двоичные файлы, которые используются, `Update-Module` возвращает ошибку, определяющую проблемные процессы.</span><span class="sxs-lookup"><span data-stu-id="c00f7-206">If `Update-Module` attempts to update binaries that are in use, `Update-Module` returns an error that identifies the problem processes.</span></span> <span data-ttu-id="c00f7-207">Пользователю будет сообщено повторить попытку `Update-Module` после остановки процессов.</span><span class="sxs-lookup"><span data-stu-id="c00f7-207">The user is informed to retry `Update-Module` after the processes are stopped.</span></span>

## <span data-ttu-id="c00f7-208">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="c00f7-208">RELATED LINKS</span></span>

[<span data-ttu-id="c00f7-209">Find-Module</span><span class="sxs-lookup"><span data-stu-id="c00f7-209">Find-Module</span></span>](Find-Module.md)

[<span data-ttu-id="c00f7-210">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="c00f7-210">Get-InstalledModule</span></span>](Get-InstalledModule.md)

[<span data-ttu-id="c00f7-211">Install-Module</span><span class="sxs-lookup"><span data-stu-id="c00f7-211">Install-Module</span></span>](Install-Module.md)

[<span data-ttu-id="c00f7-212">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="c00f7-212">Publish-Module</span></span>](Publish-Module.md)

[<span data-ttu-id="c00f7-213">Uninstall — Module</span><span class="sxs-lookup"><span data-stu-id="c00f7-213">Uninstall-Module</span></span>](Uninstall-Module.md)
