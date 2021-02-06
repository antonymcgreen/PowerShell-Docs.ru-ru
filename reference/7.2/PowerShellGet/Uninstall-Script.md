---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/03/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/uninstall-script?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Uninstall-Script
ms.openlocfilehash: 2cd8b51e1d4ef11a0a5f9e3542ff89e094854d8c
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600010"
---
# <span data-ttu-id="3b9f3-102">Uninstall-Script</span><span class="sxs-lookup"><span data-stu-id="3b9f3-102">Uninstall-Script</span></span>

## <span data-ttu-id="3b9f3-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="3b9f3-103">SYNOPSIS</span></span>
<span data-ttu-id="3b9f3-104">Удаляет скрипт.</span><span class="sxs-lookup"><span data-stu-id="3b9f3-104">Uninstalls a script.</span></span>

## <span data-ttu-id="3b9f3-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3b9f3-105">SYNTAX</span></span>

### <span data-ttu-id="3b9f3-106">NameParameterSet (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="3b9f3-106">NameParameterSet (Default)</span></span>

```
Uninstall-Script [-Name] <String[]> [-MinimumVersion <String>] [-RequiredVersion <String>]
 [-MaximumVersion <String>] [-Force] [-AllowPrerelease] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="3b9f3-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="3b9f3-107">InputObject</span></span>

```
Uninstall-Script [-InputObject] <PSObject[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="3b9f3-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3b9f3-108">DESCRIPTION</span></span>

<span data-ttu-id="3b9f3-109">`Uninstall-Script`Командлет удаляет указанный скрипт с локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="3b9f3-109">The `Uninstall-Script` cmdlet uninstalls a specified script from the local computer.</span></span>

## <span data-ttu-id="3b9f3-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="3b9f3-110">EXAMPLES</span></span>

### <span data-ttu-id="3b9f3-111">Пример 1. Удаление скрипта</span><span class="sxs-lookup"><span data-stu-id="3b9f3-111">Example 1: Uninstall a script</span></span>

<span data-ttu-id="3b9f3-112">В этом примере удаляется скрипт.</span><span class="sxs-lookup"><span data-stu-id="3b9f3-112">This example uninstalls a script.</span></span>

```powershell
Uninstall-Script -Name UpdateManagement-Template
```

<span data-ttu-id="3b9f3-113">`Uninstall-Script` использует параметр **Name** , чтобы указать скрипт для удаления с локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="3b9f3-113">`Uninstall-Script` uses the **Name** parameter to specify the script to uninstall from the local computer.</span></span>

### <span data-ttu-id="3b9f3-114">Пример 2. Использование конвейера для удаления сценария</span><span class="sxs-lookup"><span data-stu-id="3b9f3-114">Example 2: Use the pipeline to uninstall a script</span></span>

<span data-ttu-id="3b9f3-115">В этом примере конвейер используется для удаления скрипта.</span><span class="sxs-lookup"><span data-stu-id="3b9f3-115">In this example, the pipeline is used to uninstall a script.</span></span>

```powershell
Get-InstalledScript -Name UpdateManagement-Template | Uninstall-Script
```

<span data-ttu-id="3b9f3-116">`Get-InstalledScript` использует параметр **Name** для указания скрипта.</span><span class="sxs-lookup"><span data-stu-id="3b9f3-116">`Get-InstalledScript` uses the **Name** parameter to specify the script.</span></span> <span data-ttu-id="3b9f3-117">Объект отправляется по конвейеру в `Uninstall-Script` и удаляется скрипт.</span><span class="sxs-lookup"><span data-stu-id="3b9f3-117">The object is sent down the pipeline to `Uninstall-Script` and the script is uninstalled.</span></span>

## <span data-ttu-id="3b9f3-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3b9f3-118">PARAMETERS</span></span>

### <span data-ttu-id="3b9f3-119">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="3b9f3-119">-AllowPrerelease</span></span>

<span data-ttu-id="3b9f3-120">Позволяет удалить скрипт, помеченный как предварительная версия.</span><span class="sxs-lookup"><span data-stu-id="3b9f3-120">Allows you to uninstall a script marked as a prerelease.</span></span>

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

### <span data-ttu-id="3b9f3-121">-Confirm</span><span class="sxs-lookup"><span data-stu-id="3b9f3-121">-Confirm</span></span>

<span data-ttu-id="3b9f3-122">Запрашивает подтверждение перед запуском `Uninstall-Script` .</span><span class="sxs-lookup"><span data-stu-id="3b9f3-122">Prompts you for confirmation before running `Uninstall-Script`.</span></span>

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

### <span data-ttu-id="3b9f3-123">-Force</span><span class="sxs-lookup"><span data-stu-id="3b9f3-123">-Force</span></span>

<span data-ttu-id="3b9f3-124">Принудительное `Uninstall-Script` выполнение без запроса подтверждения пользователя.</span><span class="sxs-lookup"><span data-stu-id="3b9f3-124">Forces `Uninstall-Script` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="3b9f3-125">-InputObject</span><span class="sxs-lookup"><span data-stu-id="3b9f3-125">-InputObject</span></span>

<span data-ttu-id="3b9f3-126">Принимает объект **PSRepositoryItemInfo** .</span><span class="sxs-lookup"><span data-stu-id="3b9f3-126">Accepts a **PSRepositoryItemInfo** object.</span></span> <span data-ttu-id="3b9f3-127">Например, выходные данные переводятся `Get-InstalledScript` в переменную и используют эту переменную в качестве аргумента **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="3b9f3-127">For example, output `Get-InstalledScript` to a variable and use that variable as the **InputObject** argument.</span></span>

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

### <span data-ttu-id="3b9f3-128">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="3b9f3-128">-MaximumVersion</span></span>

<span data-ttu-id="3b9f3-129">Указывает максимальную или самую новую версию скрипта для удаления.</span><span class="sxs-lookup"><span data-stu-id="3b9f3-129">Specifies the maximum, or newest, version of the script to uninstall.</span></span> <span data-ttu-id="3b9f3-130">Параметры **MaximumVersion** и **RequiredVersion** нельзя использовать в одной команде.</span><span class="sxs-lookup"><span data-stu-id="3b9f3-130">The **MaximumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="3b9f3-131">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="3b9f3-131">-MinimumVersion</span></span>

<span data-ttu-id="3b9f3-132">Указывает минимальную версию скрипта для удаления.</span><span class="sxs-lookup"><span data-stu-id="3b9f3-132">Specifies the minimum version of the script to uninstall.</span></span> <span data-ttu-id="3b9f3-133">Параметры **MinimumVersion** и **RequiredVersion** нельзя использовать в одной команде.</span><span class="sxs-lookup"><span data-stu-id="3b9f3-133">The **MinimumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="3b9f3-134">-Name</span><span class="sxs-lookup"><span data-stu-id="3b9f3-134">-Name</span></span>

<span data-ttu-id="3b9f3-135">Указывает массив имен скриптов для удаления.</span><span class="sxs-lookup"><span data-stu-id="3b9f3-135">Specifies an array of script names to uninstall.</span></span>

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

### <span data-ttu-id="3b9f3-136">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="3b9f3-136">-RequiredVersion</span></span>

<span data-ttu-id="3b9f3-137">Указывает точный номер версии скрипта для удаления.</span><span class="sxs-lookup"><span data-stu-id="3b9f3-137">Specifies the exact version number of the script to uninstall.</span></span>

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

### <span data-ttu-id="3b9f3-138">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="3b9f3-138">-WhatIf</span></span>

<span data-ttu-id="3b9f3-139">Показывает, что произойдет при `Uninstall-Script` запуске.</span><span class="sxs-lookup"><span data-stu-id="3b9f3-139">Shows what would happen if `Uninstall-Script` runs.</span></span> <span data-ttu-id="3b9f3-140">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="3b9f3-140">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="3b9f3-141">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="3b9f3-141">CommonParameters</span></span>

<span data-ttu-id="3b9f3-142">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3b9f3-142">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3b9f3-143">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3b9f3-143">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3b9f3-144">Входные данные</span><span class="sxs-lookup"><span data-stu-id="3b9f3-144">INPUTS</span></span>

### <span data-ttu-id="3b9f3-145">System.String[]</span><span class="sxs-lookup"><span data-stu-id="3b9f3-145">System.String[]</span></span>

### <span data-ttu-id="3b9f3-146">System. Management. Automation. PSObject []</span><span class="sxs-lookup"><span data-stu-id="3b9f3-146">System.Management.Automation.PSObject[]</span></span>

### <span data-ttu-id="3b9f3-147">System.String</span><span class="sxs-lookup"><span data-stu-id="3b9f3-147">System.String</span></span>

## <span data-ttu-id="3b9f3-148">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="3b9f3-148">OUTPUTS</span></span>

### <span data-ttu-id="3b9f3-149">System.Object</span><span class="sxs-lookup"><span data-stu-id="3b9f3-149">System.Object</span></span>

## <span data-ttu-id="3b9f3-150">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="3b9f3-150">NOTES</span></span>

## <span data-ttu-id="3b9f3-151">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="3b9f3-151">RELATED LINKS</span></span>

[<span data-ttu-id="3b9f3-152">Find-Script</span><span class="sxs-lookup"><span data-stu-id="3b9f3-152">Find-Script</span></span>](Find-Script.md)

[<span data-ttu-id="3b9f3-153">Install-Script</span><span class="sxs-lookup"><span data-stu-id="3b9f3-153">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="3b9f3-154">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="3b9f3-154">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="3b9f3-155">Save-Script</span><span class="sxs-lookup"><span data-stu-id="3b9f3-155">Save-Script</span></span>](Save-Script.md)

[<span data-ttu-id="3b9f3-156">Update-Script</span><span class="sxs-lookup"><span data-stu-id="3b9f3-156">Update-Script</span></span>](Update-Script.md)

