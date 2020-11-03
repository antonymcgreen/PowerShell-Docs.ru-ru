---
external help file: PSModule-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/02/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/uninstall-module?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Uninstall-Module
ms.openlocfilehash: 9ba7e786acad0ffb2fffd8459561516ea8541109
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228926"
---
# <span data-ttu-id="a9c21-103">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="a9c21-103">Uninstall-Module</span></span>

## <span data-ttu-id="a9c21-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="a9c21-104">SYNOPSIS</span></span>
<span data-ttu-id="a9c21-105">Удаляет модуль.</span><span class="sxs-lookup"><span data-stu-id="a9c21-105">Uninstalls a module.</span></span>

## <span data-ttu-id="a9c21-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a9c21-106">SYNTAX</span></span>

### <span data-ttu-id="a9c21-107">NameParameterSet (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="a9c21-107">NameParameterSet (Default)</span></span>

```
Uninstall-Module [-Name] <String[]> [-MinimumVersion <String>] [-RequiredVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-Force] [-AllowPrerelease] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="a9c21-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="a9c21-108">InputObject</span></span>

```
Uninstall-Module [-InputObject] <PSObject[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="a9c21-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a9c21-109">DESCRIPTION</span></span>

<span data-ttu-id="a9c21-110">`Uninstall-Module`Командлет удаляет указанный модуль с локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="a9c21-110">The `Uninstall-Module` cmdlet uninstalls a specified module from the local computer.</span></span> <span data-ttu-id="a9c21-111">Вы не можете удалить модуль, если он содержит другие модули в качестве зависимостей.</span><span class="sxs-lookup"><span data-stu-id="a9c21-111">You can't uninstall a module if it has other modules as dependencies.</span></span>

## <span data-ttu-id="a9c21-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="a9c21-112">EXAMPLES</span></span>

### <span data-ttu-id="a9c21-113">Пример 1. Удаление модуля</span><span class="sxs-lookup"><span data-stu-id="a9c21-113">Example 1: Uninstall a module</span></span>

<span data-ttu-id="a9c21-114">В этом примере удаляется модуль.</span><span class="sxs-lookup"><span data-stu-id="a9c21-114">This example uninstalls a module.</span></span>

```powershell
Uninstall-Module -Name SpeculationControl
```

<span data-ttu-id="a9c21-115">`Uninstall-Module` использует параметр **Name** , чтобы указать модуль для удаления с локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="a9c21-115">`Uninstall-Module` uses the **Name** parameter to specify the module to uninstall from the local computer.</span></span>

### <span data-ttu-id="a9c21-116">Пример 2. Использование конвейера для удаления модуля</span><span class="sxs-lookup"><span data-stu-id="a9c21-116">Example 2: Use the pipeline to uninstall a module</span></span>

<span data-ttu-id="a9c21-117">В этом примере конвейер используется для удаления модуля.</span><span class="sxs-lookup"><span data-stu-id="a9c21-117">In this example, the pipeline is used to uninstall a module.</span></span>

```powershell
Get-InstalledModule -Name SpeculationControl | Uninstall-Module
```

<span data-ttu-id="a9c21-118">`Get-InstalledModule` Задает модуль с помощью параметра **Name** .</span><span class="sxs-lookup"><span data-stu-id="a9c21-118">`Get-InstalledModule` uses the **Name** parameter to specify the module.</span></span> <span data-ttu-id="a9c21-119">Объект отправляется по конвейеру в `Uninstall-Module` и удаляется.</span><span class="sxs-lookup"><span data-stu-id="a9c21-119">The object is sent down the pipeline to `Uninstall-Module` and is uninstalled.</span></span>

## <span data-ttu-id="a9c21-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a9c21-120">PARAMETERS</span></span>

### <span data-ttu-id="a9c21-121">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="a9c21-121">-AllowPrerelease</span></span>

<span data-ttu-id="a9c21-122">Позволяет удалить модуль, помеченный как предварительный выпуск.</span><span class="sxs-lookup"><span data-stu-id="a9c21-122">Allows you to uninstall a module marked as a prerelease.</span></span>

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

### <span data-ttu-id="a9c21-123">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="a9c21-123">-AllVersions</span></span>

<span data-ttu-id="a9c21-124">Указывает, что необходимо включить все доступные версии модуля.</span><span class="sxs-lookup"><span data-stu-id="a9c21-124">Specifies that you want to include all available versions of a module.</span></span> <span data-ttu-id="a9c21-125">Параметр **AllVersions** нельзя использовать с параметрами **MinimumVersion** , **MaximumVersion** или **RequiredVersion** .</span><span class="sxs-lookup"><span data-stu-id="a9c21-125">You can't use the **AllVersions** parameter with the **MinimumVersion** , **MaximumVersion** , or **RequiredVersion** parameters.</span></span>

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

### <span data-ttu-id="a9c21-126">-Confirm</span><span class="sxs-lookup"><span data-stu-id="a9c21-126">-Confirm</span></span>

<span data-ttu-id="a9c21-127">Запрашивает подтверждение перед запуском `Uninstall-Module` .</span><span class="sxs-lookup"><span data-stu-id="a9c21-127">Prompts you for confirmation before running the `Uninstall-Module`.</span></span>

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

### <span data-ttu-id="a9c21-128">-Force</span><span class="sxs-lookup"><span data-stu-id="a9c21-128">-Force</span></span>

<span data-ttu-id="a9c21-129">Принудительное `Uninstall-Module` выполнение без запроса подтверждения пользователя.</span><span class="sxs-lookup"><span data-stu-id="a9c21-129">Forces `Uninstall-Module` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="a9c21-130">-InputObject</span><span class="sxs-lookup"><span data-stu-id="a9c21-130">-InputObject</span></span>

<span data-ttu-id="a9c21-131">Принимает объект **PSRepositoryItemInfo** .</span><span class="sxs-lookup"><span data-stu-id="a9c21-131">Accepts a **PSRepositoryItemInfo** object.</span></span> <span data-ttu-id="a9c21-132">Например, выходные данные переводятся `Get-InstalledModule` в переменную и используют эту переменную в качестве аргумента **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="a9c21-132">For example, output `Get-InstalledModule` to a variable and use that variable as the **InputObject** argument.</span></span>

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

### <span data-ttu-id="a9c21-133">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="a9c21-133">-MaximumVersion</span></span>

<span data-ttu-id="a9c21-134">Указывает максимальную или самую новую версию модуля для удаления.</span><span class="sxs-lookup"><span data-stu-id="a9c21-134">Specifies the maximum, or newest, version of the module to uninstall.</span></span> <span data-ttu-id="a9c21-135">Параметры **MaximumVersion** и **RequiredVersion** нельзя использовать в одной команде.</span><span class="sxs-lookup"><span data-stu-id="a9c21-135">The **MaximumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="a9c21-136">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="a9c21-136">-MinimumVersion</span></span>

<span data-ttu-id="a9c21-137">Указывает минимальную версию модуля для удаления.</span><span class="sxs-lookup"><span data-stu-id="a9c21-137">Specifies the minimum version of the module to uninstall.</span></span> <span data-ttu-id="a9c21-138">Параметры **MinimumVersion** и **RequiredVersion** нельзя использовать в одной команде.</span><span class="sxs-lookup"><span data-stu-id="a9c21-138">The **MinimumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="a9c21-139">-Name</span><span class="sxs-lookup"><span data-stu-id="a9c21-139">-Name</span></span>

<span data-ttu-id="a9c21-140">Указывает массив имен модулей для удаления.</span><span class="sxs-lookup"><span data-stu-id="a9c21-140">Specifies an array of module names to uninstall.</span></span>

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

### <span data-ttu-id="a9c21-141">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="a9c21-141">-RequiredVersion</span></span>

<span data-ttu-id="a9c21-142">Указывает точный номер версии модуля для удаления.</span><span class="sxs-lookup"><span data-stu-id="a9c21-142">Specifies the exact version number of the module to uninstall.</span></span>

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

### <span data-ttu-id="a9c21-143">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="a9c21-143">-WhatIf</span></span>

<span data-ttu-id="a9c21-144">Показывает, что произойдет при `Uninstall-Module` запуске.</span><span class="sxs-lookup"><span data-stu-id="a9c21-144">Shows what would happen if `Uninstall-Module` runs.</span></span> <span data-ttu-id="a9c21-145">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="a9c21-145">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="a9c21-146">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="a9c21-146">CommonParameters</span></span>

<span data-ttu-id="a9c21-147">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a9c21-147">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a9c21-148">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a9c21-148">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a9c21-149">Входные данные</span><span class="sxs-lookup"><span data-stu-id="a9c21-149">INPUTS</span></span>

### <span data-ttu-id="a9c21-150">System.String[]</span><span class="sxs-lookup"><span data-stu-id="a9c21-150">System.String[]</span></span>

### <span data-ttu-id="a9c21-151">System. Management. Automation. PSObject []</span><span class="sxs-lookup"><span data-stu-id="a9c21-151">System.Management.Automation.PSObject[]</span></span>

### <span data-ttu-id="a9c21-152">System.String</span><span class="sxs-lookup"><span data-stu-id="a9c21-152">System.String</span></span>

## <span data-ttu-id="a9c21-153">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="a9c21-153">OUTPUTS</span></span>

### <span data-ttu-id="a9c21-154">System.Object</span><span class="sxs-lookup"><span data-stu-id="a9c21-154">System.Object</span></span>

## <span data-ttu-id="a9c21-155">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="a9c21-155">NOTES</span></span>

## <span data-ttu-id="a9c21-156">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="a9c21-156">RELATED LINKS</span></span>

[<span data-ttu-id="a9c21-157">Find-Module</span><span class="sxs-lookup"><span data-stu-id="a9c21-157">Find-Module</span></span>](Find-Module.md)

[<span data-ttu-id="a9c21-158">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="a9c21-158">Get-InstalledModule</span></span>](Get-InstalledModule.md)

[<span data-ttu-id="a9c21-159">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="a9c21-159">Publish-Module</span></span>](Publish-Module.md)

[<span data-ttu-id="a9c21-160">Save-Module</span><span class="sxs-lookup"><span data-stu-id="a9c21-160">Save-Module</span></span>](Save-Module.md)

[<span data-ttu-id="a9c21-161">Update-Module</span><span class="sxs-lookup"><span data-stu-id="a9c21-161">Update-Module</span></span>](Update-Module.md)
