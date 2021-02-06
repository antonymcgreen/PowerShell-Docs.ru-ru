---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/02/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/uninstall-module?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Uninstall-Module
ms.openlocfilehash: 0df911ad8b1f7b4516eef4a1c2b0180893013e3e
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600021"
---
# <span data-ttu-id="867f7-102">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="867f7-102">Uninstall-Module</span></span>

## <span data-ttu-id="867f7-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="867f7-103">SYNOPSIS</span></span>
<span data-ttu-id="867f7-104">Удаляет модуль.</span><span class="sxs-lookup"><span data-stu-id="867f7-104">Uninstalls a module.</span></span>

## <span data-ttu-id="867f7-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="867f7-105">SYNTAX</span></span>

### <span data-ttu-id="867f7-106">NameParameterSet (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="867f7-106">NameParameterSet (Default)</span></span>

```
Uninstall-Module [-Name] <String[]> [-MinimumVersion <String>] [-RequiredVersion <String>]
 [-MaximumVersion <String>] [-AllVersions] [-Force] [-AllowPrerelease] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="867f7-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="867f7-107">InputObject</span></span>

```
Uninstall-Module [-InputObject] <PSObject[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="867f7-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="867f7-108">DESCRIPTION</span></span>

<span data-ttu-id="867f7-109">`Uninstall-Module`Командлет удаляет указанный модуль с локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="867f7-109">The `Uninstall-Module` cmdlet uninstalls a specified module from the local computer.</span></span> <span data-ttu-id="867f7-110">Вы не можете удалить модуль, если он содержит другие модули в качестве зависимостей.</span><span class="sxs-lookup"><span data-stu-id="867f7-110">You can't uninstall a module if it has other modules as dependencies.</span></span>

## <span data-ttu-id="867f7-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="867f7-111">EXAMPLES</span></span>

### <span data-ttu-id="867f7-112">Пример 1. Удаление модуля</span><span class="sxs-lookup"><span data-stu-id="867f7-112">Example 1: Uninstall a module</span></span>

<span data-ttu-id="867f7-113">В этом примере удаляется модуль.</span><span class="sxs-lookup"><span data-stu-id="867f7-113">This example uninstalls a module.</span></span>

```powershell
Uninstall-Module -Name SpeculationControl
```

<span data-ttu-id="867f7-114">`Uninstall-Module` использует параметр **Name** , чтобы указать модуль для удаления с локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="867f7-114">`Uninstall-Module` uses the **Name** parameter to specify the module to uninstall from the local computer.</span></span>

### <span data-ttu-id="867f7-115">Пример 2. Использование конвейера для удаления модуля</span><span class="sxs-lookup"><span data-stu-id="867f7-115">Example 2: Use the pipeline to uninstall a module</span></span>

<span data-ttu-id="867f7-116">В этом примере конвейер используется для удаления модуля.</span><span class="sxs-lookup"><span data-stu-id="867f7-116">In this example, the pipeline is used to uninstall a module.</span></span>

```powershell
Get-InstalledModule -Name SpeculationControl | Uninstall-Module
```

<span data-ttu-id="867f7-117">`Get-InstalledModule` Задает модуль с помощью параметра **Name** .</span><span class="sxs-lookup"><span data-stu-id="867f7-117">`Get-InstalledModule` uses the **Name** parameter to specify the module.</span></span> <span data-ttu-id="867f7-118">Объект отправляется по конвейеру в `Uninstall-Module` и удаляется.</span><span class="sxs-lookup"><span data-stu-id="867f7-118">The object is sent down the pipeline to `Uninstall-Module` and is uninstalled.</span></span>

## <span data-ttu-id="867f7-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="867f7-119">PARAMETERS</span></span>

### <span data-ttu-id="867f7-120">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="867f7-120">-AllowPrerelease</span></span>

<span data-ttu-id="867f7-121">Позволяет удалить модуль, помеченный как предварительный выпуск.</span><span class="sxs-lookup"><span data-stu-id="867f7-121">Allows you to uninstall a module marked as a prerelease.</span></span>

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

### <span data-ttu-id="867f7-122">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="867f7-122">-AllVersions</span></span>

<span data-ttu-id="867f7-123">Указывает, что необходимо включить все доступные версии модуля.</span><span class="sxs-lookup"><span data-stu-id="867f7-123">Specifies that you want to include all available versions of a module.</span></span> <span data-ttu-id="867f7-124">Параметр **AllVersions** нельзя использовать с параметрами **MinimumVersion**, **MaximumVersion** или **RequiredVersion** .</span><span class="sxs-lookup"><span data-stu-id="867f7-124">You can't use the **AllVersions** parameter with the **MinimumVersion**, **MaximumVersion**, or **RequiredVersion** parameters.</span></span>

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

### <span data-ttu-id="867f7-125">-Confirm</span><span class="sxs-lookup"><span data-stu-id="867f7-125">-Confirm</span></span>

<span data-ttu-id="867f7-126">Запрашивает подтверждение перед запуском `Uninstall-Module` .</span><span class="sxs-lookup"><span data-stu-id="867f7-126">Prompts you for confirmation before running the `Uninstall-Module`.</span></span>

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

### <span data-ttu-id="867f7-127">-Force</span><span class="sxs-lookup"><span data-stu-id="867f7-127">-Force</span></span>

<span data-ttu-id="867f7-128">Принудительное `Uninstall-Module` выполнение без запроса подтверждения пользователя.</span><span class="sxs-lookup"><span data-stu-id="867f7-128">Forces `Uninstall-Module` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="867f7-129">-InputObject</span><span class="sxs-lookup"><span data-stu-id="867f7-129">-InputObject</span></span>

<span data-ttu-id="867f7-130">Принимает объект **PSRepositoryItemInfo** .</span><span class="sxs-lookup"><span data-stu-id="867f7-130">Accepts a **PSRepositoryItemInfo** object.</span></span> <span data-ttu-id="867f7-131">Например, выходные данные переводятся `Get-InstalledModule` в переменную и используют эту переменную в качестве аргумента **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="867f7-131">For example, output `Get-InstalledModule` to a variable and use that variable as the **InputObject** argument.</span></span>

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

### <span data-ttu-id="867f7-132">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="867f7-132">-MaximumVersion</span></span>

<span data-ttu-id="867f7-133">Указывает максимальную или самую новую версию модуля для удаления.</span><span class="sxs-lookup"><span data-stu-id="867f7-133">Specifies the maximum, or newest, version of the module to uninstall.</span></span> <span data-ttu-id="867f7-134">Параметры **MaximumVersion** и **RequiredVersion** нельзя использовать в одной команде.</span><span class="sxs-lookup"><span data-stu-id="867f7-134">The **MaximumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="867f7-135">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="867f7-135">-MinimumVersion</span></span>

<span data-ttu-id="867f7-136">Указывает минимальную версию модуля для удаления.</span><span class="sxs-lookup"><span data-stu-id="867f7-136">Specifies the minimum version of the module to uninstall.</span></span> <span data-ttu-id="867f7-137">Параметры **MinimumVersion** и **RequiredVersion** нельзя использовать в одной команде.</span><span class="sxs-lookup"><span data-stu-id="867f7-137">The **MinimumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="867f7-138">-Name</span><span class="sxs-lookup"><span data-stu-id="867f7-138">-Name</span></span>

<span data-ttu-id="867f7-139">Указывает массив имен модулей для удаления.</span><span class="sxs-lookup"><span data-stu-id="867f7-139">Specifies an array of module names to uninstall.</span></span>

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

### <span data-ttu-id="867f7-140">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="867f7-140">-RequiredVersion</span></span>

<span data-ttu-id="867f7-141">Указывает точный номер версии модуля для удаления.</span><span class="sxs-lookup"><span data-stu-id="867f7-141">Specifies the exact version number of the module to uninstall.</span></span>

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

### <span data-ttu-id="867f7-142">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="867f7-142">-WhatIf</span></span>

<span data-ttu-id="867f7-143">Показывает, что произойдет при `Uninstall-Module` запуске.</span><span class="sxs-lookup"><span data-stu-id="867f7-143">Shows what would happen if `Uninstall-Module` runs.</span></span> <span data-ttu-id="867f7-144">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="867f7-144">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="867f7-145">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="867f7-145">CommonParameters</span></span>

<span data-ttu-id="867f7-146">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="867f7-146">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="867f7-147">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="867f7-147">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="867f7-148">Входные данные</span><span class="sxs-lookup"><span data-stu-id="867f7-148">INPUTS</span></span>

### <span data-ttu-id="867f7-149">System.String[]</span><span class="sxs-lookup"><span data-stu-id="867f7-149">System.String[]</span></span>

### <span data-ttu-id="867f7-150">System. Management. Automation. PSObject []</span><span class="sxs-lookup"><span data-stu-id="867f7-150">System.Management.Automation.PSObject[]</span></span>

### <span data-ttu-id="867f7-151">System.String</span><span class="sxs-lookup"><span data-stu-id="867f7-151">System.String</span></span>

## <span data-ttu-id="867f7-152">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="867f7-152">OUTPUTS</span></span>

### <span data-ttu-id="867f7-153">System.Object</span><span class="sxs-lookup"><span data-stu-id="867f7-153">System.Object</span></span>

## <span data-ttu-id="867f7-154">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="867f7-154">NOTES</span></span>

## <span data-ttu-id="867f7-155">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="867f7-155">RELATED LINKS</span></span>

[<span data-ttu-id="867f7-156">Find-Module</span><span class="sxs-lookup"><span data-stu-id="867f7-156">Find-Module</span></span>](Find-Module.md)

[<span data-ttu-id="867f7-157">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="867f7-157">Get-InstalledModule</span></span>](Get-InstalledModule.md)

[<span data-ttu-id="867f7-158">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="867f7-158">Publish-Module</span></span>](Publish-Module.md)

[<span data-ttu-id="867f7-159">Save-Module</span><span class="sxs-lookup"><span data-stu-id="867f7-159">Save-Module</span></span>](Save-Module.md)

[<span data-ttu-id="867f7-160">Update-Module</span><span class="sxs-lookup"><span data-stu-id="867f7-160">Update-Module</span></span>](Update-Module.md)

