---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PackageManagement
ms.date: 05/24/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/unregister-packagesource?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-PackageSource
ms.openlocfilehash: 7f923c3d1b35f956479abd17e14861835dc80497
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228546"
---
# <span data-ttu-id="2d919-103">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="2d919-103">Unregister-PackageSource</span></span>

## <span data-ttu-id="2d919-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="2d919-104">SYNOPSIS</span></span>
<span data-ttu-id="2d919-105">Удаляет зарегистрированный источник пакета.</span><span class="sxs-lookup"><span data-stu-id="2d919-105">Removes a registered package source.</span></span>

## <span data-ttu-id="2d919-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2d919-106">SYNTAX</span></span>

### <span data-ttu-id="2d919-107">саурцебисеарч</span><span class="sxs-lookup"><span data-stu-id="2d919-107">SourceBySearch</span></span>

```
Unregister-PackageSource [[-Source] <String>] [-Location <String>] [-Credential <PSCredential>]
 [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-ProviderName <String>] [<CommonParameters>]
```

### <span data-ttu-id="2d919-108">саурцебинпутобжект</span><span class="sxs-lookup"><span data-stu-id="2d919-108">SourceByInputObject</span></span>

```
Unregister-PackageSource -InputObject <PackageSource[]> [-Credential <PSCredential>] [-Force]
 [-ForceBootstrap] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="2d919-109">NuGet: Саурцебинпутобжект</span><span class="sxs-lookup"><span data-stu-id="2d919-109">NuGet:SourceByInputObject</span></span>

```
Unregister-PackageSource [-Credential <PSCredential>] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### <span data-ttu-id="2d919-110">NuGet: Саурцебисеарч</span><span class="sxs-lookup"><span data-stu-id="2d919-110">NuGet:SourceBySearch</span></span>

```
Unregister-PackageSource [-Credential <PSCredential>] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### <span data-ttu-id="2d919-111">PowerShellGet: Саурцебинпутобжект</span><span class="sxs-lookup"><span data-stu-id="2d919-111">PowerShellGet:SourceByInputObject</span></span>

```
Unregister-PackageSource [-Credential <PSCredential>] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

### <span data-ttu-id="2d919-112">PowerShellGet: Саурцебисеарч</span><span class="sxs-lookup"><span data-stu-id="2d919-112">PowerShellGet:SourceBySearch</span></span>

```
Unregister-PackageSource [-Credential <PSCredential>] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

## <span data-ttu-id="2d919-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2d919-113">DESCRIPTION</span></span>

<span data-ttu-id="2d919-114">`Unregister-PackageSource`Командлет удаляет зарегистрированный источник пакета.</span><span class="sxs-lookup"><span data-stu-id="2d919-114">The `Unregister-PackageSource` cmdlet removes a registered package source.</span></span> <span data-ttu-id="2d919-115">Источники пакетов всегда управляются поставщиком пакетов.</span><span class="sxs-lookup"><span data-stu-id="2d919-115">Package sources are always managed by a package provider.</span></span> <span data-ttu-id="2d919-116">Чтобы найти источники пакетов, используйте `Get-PackageSource` командлет.</span><span class="sxs-lookup"><span data-stu-id="2d919-116">To find package sources, use the `Get-PackageSource` cmdlet.</span></span>

## <span data-ttu-id="2d919-117">Примеры</span><span class="sxs-lookup"><span data-stu-id="2d919-117">EXAMPLES</span></span>

### <span data-ttu-id="2d919-118">Пример 1. Отмена регистрации источника пакета для поставщика NuGet</span><span class="sxs-lookup"><span data-stu-id="2d919-118">Example 1: Unregister a package source for the Nuget provider</span></span>

<span data-ttu-id="2d919-119">`Unregister-PackageSource`Командлет отменяет регистрацию источника пакета на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="2d919-119">The `Unregister-PackageSource` cmdlet unregisters a package source from the local computer.</span></span> <span data-ttu-id="2d919-120">Параметры **расположения** и **поставщика** можно использовать, чтобы дополнительно указать источник для удаления.</span><span class="sxs-lookup"><span data-stu-id="2d919-120">The **Location** and **Provider** parameters can be used to further specify the source to remove.</span></span>

```
PS> Unregister-PackageSource -Source MyNuGet
```

<span data-ttu-id="2d919-121">`Unregister-PackageSource`Командлет использует параметр **Source** , чтобы указать источник для удаления.</span><span class="sxs-lookup"><span data-stu-id="2d919-121">The `Unregister-PackageSource` cmdlet uses the **Source** parameter to specify which source to remove.</span></span>

### <span data-ttu-id="2d919-122">Пример 2. Отмена регистрации пакета с помощью объекта PackageSource</span><span class="sxs-lookup"><span data-stu-id="2d919-122">Example 2: Use a PackageSource object to unregister a package</span></span>

<span data-ttu-id="2d919-123">В этом примере `Get-PackageSource` `Unregister-PackageSource` для отмены регистрации источника пакета используются и.</span><span class="sxs-lookup"><span data-stu-id="2d919-123">This example uses the `Get-PackageSource` and `Unregister-PackageSource` to unregister a package source.</span></span> <span data-ttu-id="2d919-124">Объект **PackageSource** хранится в переменной.</span><span class="sxs-lookup"><span data-stu-id="2d919-124">The **PackageSource** object is stored in a variable.</span></span>

```
PS> $pkgsource = Get-PackageSource -Name MyNuGet
PS> Unregister-PackageSource -InputObject $pkgsource
```

<span data-ttu-id="2d919-125">`$pkgsource`Переменная хранит **PackageSource** , созданные `Get-PackageSource` командлетом.</span><span class="sxs-lookup"><span data-stu-id="2d919-125">The `$pkgsource` variable stores the **PackageSource** created by the `Get-PackageSource` cmdlet.</span></span>
<span data-ttu-id="2d919-126">`Unregister-PackageSource` использует в `$pkgsource` качестве входных данных для параметра **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="2d919-126">`Unregister-PackageSource` uses the `$pkgsource` as input to the **InputObject** parameter.</span></span>

<span data-ttu-id="2d919-127">В качестве альтернативы `Unregister-PackageSource` командлет может указать значение для параметра **InputObject** :</span><span class="sxs-lookup"><span data-stu-id="2d919-127">As an alternative, the `Unregister-PackageSource` cmdlet can specify a value for the **InputObject** parameter:</span></span>

`Unregister-PackageSource -InputObject ( Get-PackageSource -Name MyNuGet )`

## <span data-ttu-id="2d919-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2d919-128">PARAMETERS</span></span>

### <span data-ttu-id="2d919-129">-ConfigFile</span><span class="sxs-lookup"><span data-stu-id="2d919-129">-ConfigFile</span></span>

<span data-ttu-id="2d919-130">Указывает файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2d919-130">Specifies a configuration file.</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet:SourceByInputObject, NuGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2d919-131">-Credential</span><span class="sxs-lookup"><span data-stu-id="2d919-131">-Credential</span></span>

<span data-ttu-id="2d919-132">Указывает учетную запись пользователя, имеющую разрешение на доступ к компьютеру и выполнение команд.</span><span class="sxs-lookup"><span data-stu-id="2d919-132">Specifies a user account that has permission to access the computer and run commands.</span></span> <span data-ttu-id="2d919-133">Введите имя пользователя, например **User01** , **Domain01\User01** , или введите объект **PSCredential** , созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="2d919-133">Type a user name, such as **User01** , **Domain01\User01** , or enter a **PSCredential** object, generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="2d919-134">Если ввести имя пользователя, будет предложено ввести пароль.</span><span class="sxs-lookup"><span data-stu-id="2d919-134">If you type a user name, you're prompted for a password.</span></span>

<span data-ttu-id="2d919-135">Если параметр **Credential** не указан, используется текущая учетная запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="2d919-135">When the **Credential** parameter isn't specified, the current user account is used.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2d919-136">-Force</span><span class="sxs-lookup"><span data-stu-id="2d919-136">-Force</span></span>

<span data-ttu-id="2d919-137">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="2d919-137">Forces the command to run without asking for user confirmation.</span></span> <span data-ttu-id="2d919-138">Переопределяет ограничения, которые препятствуют `Unregister-PackageSource` выполнению, за исключением безопасности.</span><span class="sxs-lookup"><span data-stu-id="2d919-138">Overrides restrictions that prevent `Unregister-PackageSource` from succeeding, with the exception of security.</span></span>

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

### <span data-ttu-id="2d919-139">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="2d919-139">-ForceBootstrap</span></span>

<span data-ttu-id="2d919-140">Указывает, что `Unregister-PackageSource` заставляет **PackageManagement** автоматически удалить поставщик пакетов для указанного источника пакета.</span><span class="sxs-lookup"><span data-stu-id="2d919-140">Indicates that `Unregister-PackageSource` forces **PackageManagement** to automatically uninstall the package provider for the specified package source.</span></span>

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

### <span data-ttu-id="2d919-141">-InputObject</span><span class="sxs-lookup"><span data-stu-id="2d919-141">-InputObject</span></span>

<span data-ttu-id="2d919-142">Принимает входные данные конвейера, указывающие объект **PackageSource** из `Get-PackageSource` командлета.</span><span class="sxs-lookup"><span data-stu-id="2d919-142">Accepts pipeline input that specifies the **PackageSource** object from the `Get-PackageSource` cmdlet.</span></span> <span data-ttu-id="2d919-143">**InputObject** принимает объект **PackageSource** как `Get-PackageSource` значение или переменную, содержащую объект.</span><span class="sxs-lookup"><span data-stu-id="2d919-143">**InputObject** accepts the **PackageSource** object as a `Get-PackageSource` value or a variable that contains the object.</span></span>

```yaml
Type: Microsoft.PackageManagement.Packaging.PackageSource[]
Parameter Sets: SourceByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="2d919-144">— Расположение</span><span class="sxs-lookup"><span data-stu-id="2d919-144">-Location</span></span>

<span data-ttu-id="2d919-145">Задает расположение, на которое указывает источник пакета.</span><span class="sxs-lookup"><span data-stu-id="2d919-145">Specifies the location to which a package source points.</span></span> <span data-ttu-id="2d919-146">Значением этого параметра может быть URI, путь к файлу или любой другой формат назначения, поддерживаемый поставщиком пакетов.</span><span class="sxs-lookup"><span data-stu-id="2d919-146">The value of this parameter can be a URI, a file path, or any other destination format that is supported by the package provider.</span></span>

```yaml
Type: System.String
Parameter Sets: SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2d919-147">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="2d919-147">-PackageManagementProvider</span></span>

<span data-ttu-id="2d919-148">Указывает поставщика **PackageManagement** .</span><span class="sxs-lookup"><span data-stu-id="2d919-148">Specifies the **PackageManagement** provider.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:SourceByInputObject, PowerShellGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2d919-149">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="2d919-149">-ProviderName</span></span>

<span data-ttu-id="2d919-150">Указывает имя поставщика.</span><span class="sxs-lookup"><span data-stu-id="2d919-150">Specifies the provider name.</span></span>

```yaml
Type: System.String
Parameter Sets: SourceBySearch
Aliases: Provider
Accepted values: Bootstrap, NuGet, PowerShellGet

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="2d919-151">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="2d919-151">-PublishLocation</span></span>

<span data-ttu-id="2d919-152">Указывает расположение публикации.</span><span class="sxs-lookup"><span data-stu-id="2d919-152">Specifies the publish location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:SourceByInputObject, PowerShellGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2d919-153">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="2d919-153">-ScriptPublishLocation</span></span>

<span data-ttu-id="2d919-154">Указывает расположение публикации скрипта.</span><span class="sxs-lookup"><span data-stu-id="2d919-154">Specifies the script publish location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:SourceByInputObject, PowerShellGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2d919-155">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="2d919-155">-ScriptSourceLocation</span></span>

<span data-ttu-id="2d919-156">Указывает расположение источника скрипта.</span><span class="sxs-lookup"><span data-stu-id="2d919-156">Specifies the script source location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet:SourceByInputObject, PowerShellGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2d919-157">-Скипвалидате</span><span class="sxs-lookup"><span data-stu-id="2d919-157">-SkipValidate</span></span>

<span data-ttu-id="2d919-158">Параметр, который пропускает проверку учетных данных источника пакета.</span><span class="sxs-lookup"><span data-stu-id="2d919-158">Switch that skips validating the credentials of a package source.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet:SourceByInputObject, NuGet:SourceBySearch
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2d919-159">-Source</span><span class="sxs-lookup"><span data-stu-id="2d919-159">-Source</span></span>

<span data-ttu-id="2d919-160">Указывает понятное имя источника пакета.</span><span class="sxs-lookup"><span data-stu-id="2d919-160">Specifies the friendly name of the package source.</span></span>

```yaml
Type: System.String
Parameter Sets: SourceBySearch
Aliases: Name

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2d919-161">-Confirm</span><span class="sxs-lookup"><span data-stu-id="2d919-161">-Confirm</span></span>

<span data-ttu-id="2d919-162">Запрашивает подтверждение перед `Unregister-PackageSource` запуском.</span><span class="sxs-lookup"><span data-stu-id="2d919-162">Prompts you for confirmation before `Unregister-PackageSource` is run.</span></span>

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

### <span data-ttu-id="2d919-163">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="2d919-163">-WhatIf</span></span>

<span data-ttu-id="2d919-164">Показывает, что произойдет при `Unregister-PackageSource` запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="2d919-164">Shows what would happen if `Unregister-PackageSource` cmdlet is run.</span></span> <span data-ttu-id="2d919-165">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="2d919-165">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="2d919-166">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="2d919-166">CommonParameters</span></span>

<span data-ttu-id="2d919-167">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="2d919-167">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2d919-168">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2d919-168">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2d919-169">Входные данные</span><span class="sxs-lookup"><span data-stu-id="2d919-169">INPUTS</span></span>

### <span data-ttu-id="2d919-170">`Unregister-PackageSource` принимает объекты **PackageSource** из конвейера в качестве входных данных.</span><span class="sxs-lookup"><span data-stu-id="2d919-170">`Unregister-PackageSource` accepts **PackageSource** objects from the pipeline as input.</span></span>

## <span data-ttu-id="2d919-171">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="2d919-171">OUTPUTS</span></span>

### <span data-ttu-id="2d919-172">`Unregister-PackageSource` не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="2d919-172">`Unregister-PackageSource` doesn't generate any output.</span></span>

## <span data-ttu-id="2d919-173">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="2d919-173">NOTES</span></span>

<span data-ttu-id="2d919-174">Включение поставщика пакетов в команду может сделать динамические параметры доступными для командлета.</span><span class="sxs-lookup"><span data-stu-id="2d919-174">Including a package provider in a command can make dynamic parameters available to a cmdlet.</span></span> <span data-ttu-id="2d919-175">Динамические параметры относятся к поставщику пакетов.</span><span class="sxs-lookup"><span data-stu-id="2d919-175">Dynamic parameters are specific to a package provider.</span></span> <span data-ttu-id="2d919-176">`Get-Help`Командлет перечисляет наборы параметров командлета и включает набор параметров поставщика.</span><span class="sxs-lookup"><span data-stu-id="2d919-176">The `Get-Help` cmdlet lists a cmdlet's parameter sets and includes the provider's parameter set.</span></span>

## <span data-ttu-id="2d919-177">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="2d919-177">RELATED LINKS</span></span>

[<span data-ttu-id="2d919-178">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="2d919-178">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="2d919-179">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="2d919-179">Get-Credential</span></span>](../Microsoft.PowerShell.Security/Get-Credential.md)

[<span data-ttu-id="2d919-180">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="2d919-180">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="2d919-181">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="2d919-181">Register-PackageSource</span></span>](Register-PackageSource.md)

[<span data-ttu-id="2d919-182">Set-PackageSource</span><span class="sxs-lookup"><span data-stu-id="2d919-182">Set-PackageSource</span></span>](Set-PackageSource.md)

