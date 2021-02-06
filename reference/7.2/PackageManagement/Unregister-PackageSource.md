---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
Locale: en-US
Module Name: PackageManagement
ms.date: 05/24/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/unregister-packagesource?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-PackageSource
ms.openlocfilehash: 6ef89e9143fe8883bc98723d10775bf739fe72f9
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599993"
---
# <span data-ttu-id="80fd7-102">Unregister-PackageSource</span><span class="sxs-lookup"><span data-stu-id="80fd7-102">Unregister-PackageSource</span></span>

## <span data-ttu-id="80fd7-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="80fd7-103">SYNOPSIS</span></span>
<span data-ttu-id="80fd7-104">Удаляет зарегистрированный источник пакета.</span><span class="sxs-lookup"><span data-stu-id="80fd7-104">Removes a registered package source.</span></span>

## <span data-ttu-id="80fd7-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="80fd7-105">SYNTAX</span></span>

### <span data-ttu-id="80fd7-106">саурцебисеарч</span><span class="sxs-lookup"><span data-stu-id="80fd7-106">SourceBySearch</span></span>

```
Unregister-PackageSource [[-Source] <String>] [-Location <String>] [-Credential <PSCredential>]
 [-Force] [-ForceBootstrap] [-WhatIf] [-Confirm] [-ProviderName <String>] [<CommonParameters>]
```

### <span data-ttu-id="80fd7-107">саурцебинпутобжект</span><span class="sxs-lookup"><span data-stu-id="80fd7-107">SourceByInputObject</span></span>

```
Unregister-PackageSource -InputObject <PackageSource[]> [-Credential <PSCredential>] [-Force]
 [-ForceBootstrap] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="80fd7-108">NuGet: Саурцебинпутобжект</span><span class="sxs-lookup"><span data-stu-id="80fd7-108">NuGet:SourceByInputObject</span></span>

```
Unregister-PackageSource [-Credential <PSCredential>] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### <span data-ttu-id="80fd7-109">NuGet: Саурцебисеарч</span><span class="sxs-lookup"><span data-stu-id="80fd7-109">NuGet:SourceBySearch</span></span>

```
Unregister-PackageSource [-Credential <PSCredential>] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-ConfigFile <String>] [-SkipValidate] [<CommonParameters>]
```

### <span data-ttu-id="80fd7-110">PowerShellGet: Саурцебинпутобжект</span><span class="sxs-lookup"><span data-stu-id="80fd7-110">PowerShellGet:SourceByInputObject</span></span>

```
Unregister-PackageSource [-Credential <PSCredential>] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

### <span data-ttu-id="80fd7-111">PowerShellGet: Саурцебисеарч</span><span class="sxs-lookup"><span data-stu-id="80fd7-111">PowerShellGet:SourceBySearch</span></span>

```
Unregister-PackageSource [-Credential <PSCredential>] [-Force] [-ForceBootstrap] [-WhatIf]
 [-Confirm] [-PackageManagementProvider <String>] [-PublishLocation <String>]
 [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>] [<CommonParameters>]
```

## <span data-ttu-id="80fd7-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="80fd7-112">DESCRIPTION</span></span>

<span data-ttu-id="80fd7-113">`Unregister-PackageSource`Командлет удаляет зарегистрированный источник пакета.</span><span class="sxs-lookup"><span data-stu-id="80fd7-113">The `Unregister-PackageSource` cmdlet removes a registered package source.</span></span> <span data-ttu-id="80fd7-114">Источники пакетов всегда управляются поставщиком пакетов.</span><span class="sxs-lookup"><span data-stu-id="80fd7-114">Package sources are always managed by a package provider.</span></span> <span data-ttu-id="80fd7-115">Чтобы найти источники пакетов, используйте `Get-PackageSource` командлет.</span><span class="sxs-lookup"><span data-stu-id="80fd7-115">To find package sources, use the `Get-PackageSource` cmdlet.</span></span>

## <span data-ttu-id="80fd7-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="80fd7-116">EXAMPLES</span></span>

### <span data-ttu-id="80fd7-117">Пример 1. Отмена регистрации источника пакета для поставщика NuGet</span><span class="sxs-lookup"><span data-stu-id="80fd7-117">Example 1: Unregister a package source for the Nuget provider</span></span>

<span data-ttu-id="80fd7-118">`Unregister-PackageSource`Командлет отменяет регистрацию источника пакета на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="80fd7-118">The `Unregister-PackageSource` cmdlet unregisters a package source from the local computer.</span></span> <span data-ttu-id="80fd7-119">Параметры **расположения** и **поставщика** можно использовать, чтобы дополнительно указать источник для удаления.</span><span class="sxs-lookup"><span data-stu-id="80fd7-119">The **Location** and **Provider** parameters can be used to further specify the source to remove.</span></span>

```
PS> Unregister-PackageSource -Source MyNuGet
```

<span data-ttu-id="80fd7-120">`Unregister-PackageSource`Командлет использует параметр **Source** , чтобы указать источник для удаления.</span><span class="sxs-lookup"><span data-stu-id="80fd7-120">The `Unregister-PackageSource` cmdlet uses the **Source** parameter to specify which source to remove.</span></span>

### <span data-ttu-id="80fd7-121">Пример 2. Отмена регистрации пакета с помощью объекта PackageSource</span><span class="sxs-lookup"><span data-stu-id="80fd7-121">Example 2: Use a PackageSource object to unregister a package</span></span>

<span data-ttu-id="80fd7-122">В этом примере `Get-PackageSource` `Unregister-PackageSource` для отмены регистрации источника пакета используются и.</span><span class="sxs-lookup"><span data-stu-id="80fd7-122">This example uses the `Get-PackageSource` and `Unregister-PackageSource` to unregister a package source.</span></span> <span data-ttu-id="80fd7-123">Объект **PackageSource** хранится в переменной.</span><span class="sxs-lookup"><span data-stu-id="80fd7-123">The **PackageSource** object is stored in a variable.</span></span>

```
PS> $pkgsource = Get-PackageSource -Name MyNuGet
PS> Unregister-PackageSource -InputObject $pkgsource
```

<span data-ttu-id="80fd7-124">`$pkgsource`Переменная хранит **PackageSource** , созданные `Get-PackageSource` командлетом.</span><span class="sxs-lookup"><span data-stu-id="80fd7-124">The `$pkgsource` variable stores the **PackageSource** created by the `Get-PackageSource` cmdlet.</span></span>
<span data-ttu-id="80fd7-125">`Unregister-PackageSource` использует в `$pkgsource` качестве входных данных для параметра **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="80fd7-125">`Unregister-PackageSource` uses the `$pkgsource` as input to the **InputObject** parameter.</span></span>

<span data-ttu-id="80fd7-126">В качестве альтернативы `Unregister-PackageSource` командлет может указать значение для параметра **InputObject** :</span><span class="sxs-lookup"><span data-stu-id="80fd7-126">As an alternative, the `Unregister-PackageSource` cmdlet can specify a value for the **InputObject** parameter:</span></span>

`Unregister-PackageSource -InputObject ( Get-PackageSource -Name MyNuGet )`

## <span data-ttu-id="80fd7-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="80fd7-127">PARAMETERS</span></span>

### <span data-ttu-id="80fd7-128">-ConfigFile</span><span class="sxs-lookup"><span data-stu-id="80fd7-128">-ConfigFile</span></span>

<span data-ttu-id="80fd7-129">Указывает файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="80fd7-129">Specifies a configuration file.</span></span>

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

### <span data-ttu-id="80fd7-130">-Credential</span><span class="sxs-lookup"><span data-stu-id="80fd7-130">-Credential</span></span>

<span data-ttu-id="80fd7-131">Указывает учетную запись пользователя, имеющую разрешение на доступ к компьютеру и выполнение команд.</span><span class="sxs-lookup"><span data-stu-id="80fd7-131">Specifies a user account that has permission to access the computer and run commands.</span></span> <span data-ttu-id="80fd7-132">Введите имя пользователя, например **User01**, **Domain01\User01**, или введите объект **PSCredential** , созданный `Get-Credential` командлетом.</span><span class="sxs-lookup"><span data-stu-id="80fd7-132">Type a user name, such as **User01**, **Domain01\User01**, or enter a **PSCredential** object, generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="80fd7-133">Если ввести имя пользователя, будет предложено ввести пароль.</span><span class="sxs-lookup"><span data-stu-id="80fd7-133">If you type a user name, you're prompted for a password.</span></span>

<span data-ttu-id="80fd7-134">Если параметр **Credential** не указан, используется текущая учетная запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="80fd7-134">When the **Credential** parameter isn't specified, the current user account is used.</span></span>

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

### <span data-ttu-id="80fd7-135">-Force</span><span class="sxs-lookup"><span data-stu-id="80fd7-135">-Force</span></span>

<span data-ttu-id="80fd7-136">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="80fd7-136">Forces the command to run without asking for user confirmation.</span></span> <span data-ttu-id="80fd7-137">Переопределяет ограничения, которые препятствуют `Unregister-PackageSource` выполнению, за исключением безопасности.</span><span class="sxs-lookup"><span data-stu-id="80fd7-137">Overrides restrictions that prevent `Unregister-PackageSource` from succeeding, with the exception of security.</span></span>

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

### <span data-ttu-id="80fd7-138">-ForceBootstrap</span><span class="sxs-lookup"><span data-stu-id="80fd7-138">-ForceBootstrap</span></span>

<span data-ttu-id="80fd7-139">Указывает, что `Unregister-PackageSource` заставляет **PackageManagement** автоматически удалить поставщик пакетов для указанного источника пакета.</span><span class="sxs-lookup"><span data-stu-id="80fd7-139">Indicates that `Unregister-PackageSource` forces **PackageManagement** to automatically uninstall the package provider for the specified package source.</span></span>

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

### <span data-ttu-id="80fd7-140">-InputObject</span><span class="sxs-lookup"><span data-stu-id="80fd7-140">-InputObject</span></span>

<span data-ttu-id="80fd7-141">Принимает входные данные конвейера, указывающие объект **PackageSource** из `Get-PackageSource` командлета.</span><span class="sxs-lookup"><span data-stu-id="80fd7-141">Accepts pipeline input that specifies the **PackageSource** object from the `Get-PackageSource` cmdlet.</span></span> <span data-ttu-id="80fd7-142">**InputObject** принимает объект **PackageSource** как `Get-PackageSource` значение или переменную, содержащую объект.</span><span class="sxs-lookup"><span data-stu-id="80fd7-142">**InputObject** accepts the **PackageSource** object as a `Get-PackageSource` value or a variable that contains the object.</span></span>

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

### <span data-ttu-id="80fd7-143">— Расположение</span><span class="sxs-lookup"><span data-stu-id="80fd7-143">-Location</span></span>

<span data-ttu-id="80fd7-144">Задает расположение, на которое указывает источник пакета.</span><span class="sxs-lookup"><span data-stu-id="80fd7-144">Specifies the location to which a package source points.</span></span> <span data-ttu-id="80fd7-145">Значением этого параметра может быть URI, путь к файлу или любой другой формат назначения, поддерживаемый поставщиком пакетов.</span><span class="sxs-lookup"><span data-stu-id="80fd7-145">The value of this parameter can be a URI, a file path, or any other destination format that is supported by the package provider.</span></span>

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

### <span data-ttu-id="80fd7-146">-PackageManagementProvider</span><span class="sxs-lookup"><span data-stu-id="80fd7-146">-PackageManagementProvider</span></span>

<span data-ttu-id="80fd7-147">Указывает поставщика **PackageManagement** .</span><span class="sxs-lookup"><span data-stu-id="80fd7-147">Specifies the **PackageManagement** provider.</span></span>

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

### <span data-ttu-id="80fd7-148">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="80fd7-148">-ProviderName</span></span>

<span data-ttu-id="80fd7-149">Указывает имя поставщика.</span><span class="sxs-lookup"><span data-stu-id="80fd7-149">Specifies the provider name.</span></span>

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

### <span data-ttu-id="80fd7-150">-PublishLocation</span><span class="sxs-lookup"><span data-stu-id="80fd7-150">-PublishLocation</span></span>

<span data-ttu-id="80fd7-151">Указывает расположение публикации.</span><span class="sxs-lookup"><span data-stu-id="80fd7-151">Specifies the publish location.</span></span>

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

### <span data-ttu-id="80fd7-152">-ScriptPublishLocation</span><span class="sxs-lookup"><span data-stu-id="80fd7-152">-ScriptPublishLocation</span></span>

<span data-ttu-id="80fd7-153">Указывает расположение публикации скрипта.</span><span class="sxs-lookup"><span data-stu-id="80fd7-153">Specifies the script publish location.</span></span>

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

### <span data-ttu-id="80fd7-154">-ScriptSourceLocation</span><span class="sxs-lookup"><span data-stu-id="80fd7-154">-ScriptSourceLocation</span></span>

<span data-ttu-id="80fd7-155">Указывает расположение источника скрипта.</span><span class="sxs-lookup"><span data-stu-id="80fd7-155">Specifies the script source location.</span></span>

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

### <span data-ttu-id="80fd7-156">-Скипвалидате</span><span class="sxs-lookup"><span data-stu-id="80fd7-156">-SkipValidate</span></span>

<span data-ttu-id="80fd7-157">Параметр, который пропускает проверку учетных данных источника пакета.</span><span class="sxs-lookup"><span data-stu-id="80fd7-157">Switch that skips validating the credentials of a package source.</span></span>

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

### <span data-ttu-id="80fd7-158">-Source</span><span class="sxs-lookup"><span data-stu-id="80fd7-158">-Source</span></span>

<span data-ttu-id="80fd7-159">Указывает понятное имя источника пакета.</span><span class="sxs-lookup"><span data-stu-id="80fd7-159">Specifies the friendly name of the package source.</span></span>

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

### <span data-ttu-id="80fd7-160">-Confirm</span><span class="sxs-lookup"><span data-stu-id="80fd7-160">-Confirm</span></span>

<span data-ttu-id="80fd7-161">Запрашивает подтверждение перед `Unregister-PackageSource` запуском.</span><span class="sxs-lookup"><span data-stu-id="80fd7-161">Prompts you for confirmation before `Unregister-PackageSource` is run.</span></span>

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

### <span data-ttu-id="80fd7-162">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="80fd7-162">-WhatIf</span></span>

<span data-ttu-id="80fd7-163">Показывает, что произойдет при `Unregister-PackageSource` запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="80fd7-163">Shows what would happen if `Unregister-PackageSource` cmdlet is run.</span></span> <span data-ttu-id="80fd7-164">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="80fd7-164">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="80fd7-165">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="80fd7-165">CommonParameters</span></span>

<span data-ttu-id="80fd7-166">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="80fd7-166">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="80fd7-167">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="80fd7-167">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="80fd7-168">Входные данные</span><span class="sxs-lookup"><span data-stu-id="80fd7-168">INPUTS</span></span>

### <span data-ttu-id="80fd7-169">`Unregister-PackageSource` принимает объекты **PackageSource** из конвейера в качестве входных данных.</span><span class="sxs-lookup"><span data-stu-id="80fd7-169">`Unregister-PackageSource` accepts **PackageSource** objects from the pipeline as input.</span></span>

## <span data-ttu-id="80fd7-170">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="80fd7-170">OUTPUTS</span></span>

### <span data-ttu-id="80fd7-171">`Unregister-PackageSource` не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="80fd7-171">`Unregister-PackageSource` doesn't generate any output.</span></span>

## <span data-ttu-id="80fd7-172">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="80fd7-172">NOTES</span></span>

<span data-ttu-id="80fd7-173">Включение поставщика пакетов в команду может сделать динамические параметры доступными для командлета.</span><span class="sxs-lookup"><span data-stu-id="80fd7-173">Including a package provider in a command can make dynamic parameters available to a cmdlet.</span></span> <span data-ttu-id="80fd7-174">Динамические параметры относятся к поставщику пакетов.</span><span class="sxs-lookup"><span data-stu-id="80fd7-174">Dynamic parameters are specific to a package provider.</span></span> <span data-ttu-id="80fd7-175">`Get-Help`Командлет перечисляет наборы параметров командлета и включает набор параметров поставщика.</span><span class="sxs-lookup"><span data-stu-id="80fd7-175">The `Get-Help` cmdlet lists a cmdlet's parameter sets and includes the provider's parameter set.</span></span>

## <span data-ttu-id="80fd7-176">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="80fd7-176">RELATED LINKS</span></span>

[<span data-ttu-id="80fd7-177">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="80fd7-177">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="80fd7-178">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="80fd7-178">Get-Credential</span></span>](../Microsoft.PowerShell.Security/Get-Credential.md)

[<span data-ttu-id="80fd7-179">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="80fd7-179">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="80fd7-180">Register-PackageSource</span><span class="sxs-lookup"><span data-stu-id="80fd7-180">Register-PackageSource</span></span>](Register-PackageSource.md)

[<span data-ttu-id="80fd7-181">Set-PackageSource</span><span class="sxs-lookup"><span data-stu-id="80fd7-181">Set-PackageSource</span></span>](Set-PackageSource.md)

