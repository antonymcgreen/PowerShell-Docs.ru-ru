---
external help file: PSModule-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/03/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/uninstall-script?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Uninstall-Script
ms.openlocfilehash: 26e32cc3d7330026bd77d33ba6574818559d1c6c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226973"
---
# <span data-ttu-id="22485-103">Uninstall-Script</span><span class="sxs-lookup"><span data-stu-id="22485-103">Uninstall-Script</span></span>

## <span data-ttu-id="22485-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="22485-104">SYNOPSIS</span></span>
<span data-ttu-id="22485-105">Удаляет скрипт.</span><span class="sxs-lookup"><span data-stu-id="22485-105">Uninstalls a script.</span></span>

## <span data-ttu-id="22485-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="22485-106">SYNTAX</span></span>

### <span data-ttu-id="22485-107">NameParameterSet (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="22485-107">NameParameterSet (Default)</span></span>

```
Uninstall-Script [-Name] <String[]> [-MinimumVersion <String>] [-RequiredVersion <String>]
 [-MaximumVersion <String>] [-Force] [-AllowPrerelease] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="22485-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="22485-108">InputObject</span></span>

```
Uninstall-Script [-InputObject] <PSObject[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="22485-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="22485-109">DESCRIPTION</span></span>

<span data-ttu-id="22485-110">`Uninstall-Script`Командлет удаляет указанный скрипт с локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="22485-110">The `Uninstall-Script` cmdlet uninstalls a specified script from the local computer.</span></span>

## <span data-ttu-id="22485-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="22485-111">EXAMPLES</span></span>

### <span data-ttu-id="22485-112">Пример 1. Удаление скрипта</span><span class="sxs-lookup"><span data-stu-id="22485-112">Example 1: Uninstall a script</span></span>

<span data-ttu-id="22485-113">В этом примере удаляется скрипт.</span><span class="sxs-lookup"><span data-stu-id="22485-113">This example uninstalls a script.</span></span>

```powershell
Uninstall-Script -Name UpdateManagement-Template
```

<span data-ttu-id="22485-114">`Uninstall-Script` использует параметр **Name** , чтобы указать скрипт для удаления с локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="22485-114">`Uninstall-Script` uses the **Name** parameter to specify the script to uninstall from the local computer.</span></span>

### <span data-ttu-id="22485-115">Пример 2. Использование конвейера для удаления сценария</span><span class="sxs-lookup"><span data-stu-id="22485-115">Example 2: Use the pipeline to uninstall a script</span></span>

<span data-ttu-id="22485-116">В этом примере конвейер используется для удаления скрипта.</span><span class="sxs-lookup"><span data-stu-id="22485-116">In this example, the pipeline is used to uninstall a script.</span></span>

```powershell
Get-InstalledScript -Name UpdateManagement-Template | Uninstall-Script
```

<span data-ttu-id="22485-117">`Get-InstalledScript` использует параметр **Name** для указания скрипта.</span><span class="sxs-lookup"><span data-stu-id="22485-117">`Get-InstalledScript` uses the **Name** parameter to specify the script.</span></span> <span data-ttu-id="22485-118">Объект отправляется по конвейеру в `Uninstall-Script` и удаляется скрипт.</span><span class="sxs-lookup"><span data-stu-id="22485-118">The object is sent down the pipeline to `Uninstall-Script` and the script is uninstalled.</span></span>

## <span data-ttu-id="22485-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="22485-119">PARAMETERS</span></span>

### <span data-ttu-id="22485-120">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="22485-120">-AllowPrerelease</span></span>

<span data-ttu-id="22485-121">Позволяет удалить скрипт, помеченный как предварительная версия.</span><span class="sxs-lookup"><span data-stu-id="22485-121">Allows you to uninstall a script marked as a prerelease.</span></span>

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

### <span data-ttu-id="22485-122">-Confirm</span><span class="sxs-lookup"><span data-stu-id="22485-122">-Confirm</span></span>

<span data-ttu-id="22485-123">Запрашивает подтверждение перед запуском `Uninstall-Script` .</span><span class="sxs-lookup"><span data-stu-id="22485-123">Prompts you for confirmation before running `Uninstall-Script`.</span></span>

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

### <span data-ttu-id="22485-124">-Force</span><span class="sxs-lookup"><span data-stu-id="22485-124">-Force</span></span>

<span data-ttu-id="22485-125">Принудительное `Uninstall-Script` выполнение без запроса подтверждения пользователя.</span><span class="sxs-lookup"><span data-stu-id="22485-125">Forces `Uninstall-Script` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="22485-126">-InputObject</span><span class="sxs-lookup"><span data-stu-id="22485-126">-InputObject</span></span>

<span data-ttu-id="22485-127">Принимает объект **PSRepositoryItemInfo** .</span><span class="sxs-lookup"><span data-stu-id="22485-127">Accepts a **PSRepositoryItemInfo** object.</span></span> <span data-ttu-id="22485-128">Например, выходные данные переводятся `Get-InstalledScript` в переменную и используют эту переменную в качестве аргумента **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="22485-128">For example, output `Get-InstalledScript` to a variable and use that variable as the **InputObject** argument.</span></span>

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

### <span data-ttu-id="22485-129">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="22485-129">-MaximumVersion</span></span>

<span data-ttu-id="22485-130">Указывает максимальную или самую новую версию скрипта для удаления.</span><span class="sxs-lookup"><span data-stu-id="22485-130">Specifies the maximum, or newest, version of the script to uninstall.</span></span> <span data-ttu-id="22485-131">Параметры **MaximumVersion** и **RequiredVersion** нельзя использовать в одной команде.</span><span class="sxs-lookup"><span data-stu-id="22485-131">The **MaximumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="22485-132">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="22485-132">-MinimumVersion</span></span>

<span data-ttu-id="22485-133">Указывает минимальную версию скрипта для удаления.</span><span class="sxs-lookup"><span data-stu-id="22485-133">Specifies the minimum version of the script to uninstall.</span></span> <span data-ttu-id="22485-134">Параметры **MinimumVersion** и **RequiredVersion** нельзя использовать в одной команде.</span><span class="sxs-lookup"><span data-stu-id="22485-134">The **MinimumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="22485-135">-Name</span><span class="sxs-lookup"><span data-stu-id="22485-135">-Name</span></span>

<span data-ttu-id="22485-136">Указывает массив имен скриптов для удаления.</span><span class="sxs-lookup"><span data-stu-id="22485-136">Specifies an array of script names to uninstall.</span></span>

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

### <span data-ttu-id="22485-137">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="22485-137">-RequiredVersion</span></span>

<span data-ttu-id="22485-138">Указывает точный номер версии скрипта для удаления.</span><span class="sxs-lookup"><span data-stu-id="22485-138">Specifies the exact version number of the script to uninstall.</span></span>

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

### <span data-ttu-id="22485-139">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="22485-139">-WhatIf</span></span>

<span data-ttu-id="22485-140">Показывает, что произойдет при `Uninstall-Script` запуске.</span><span class="sxs-lookup"><span data-stu-id="22485-140">Shows what would happen if `Uninstall-Script` runs.</span></span> <span data-ttu-id="22485-141">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="22485-141">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="22485-142">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="22485-142">CommonParameters</span></span>

<span data-ttu-id="22485-143">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="22485-143">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="22485-144">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="22485-144">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="22485-145">Входные данные</span><span class="sxs-lookup"><span data-stu-id="22485-145">INPUTS</span></span>

### <span data-ttu-id="22485-146">System.String[]</span><span class="sxs-lookup"><span data-stu-id="22485-146">System.String[]</span></span>

### <span data-ttu-id="22485-147">System. Management. Automation. PSObject []</span><span class="sxs-lookup"><span data-stu-id="22485-147">System.Management.Automation.PSObject[]</span></span>

### <span data-ttu-id="22485-148">System.String</span><span class="sxs-lookup"><span data-stu-id="22485-148">System.String</span></span>

## <span data-ttu-id="22485-149">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="22485-149">OUTPUTS</span></span>

### <span data-ttu-id="22485-150">System.Object</span><span class="sxs-lookup"><span data-stu-id="22485-150">System.Object</span></span>

## <span data-ttu-id="22485-151">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="22485-151">NOTES</span></span>

## <span data-ttu-id="22485-152">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="22485-152">RELATED LINKS</span></span>

[<span data-ttu-id="22485-153">Find-Script</span><span class="sxs-lookup"><span data-stu-id="22485-153">Find-Script</span></span>](Find-Script.md)

[<span data-ttu-id="22485-154">Install-Script</span><span class="sxs-lookup"><span data-stu-id="22485-154">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="22485-155">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="22485-155">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="22485-156">Save-Script</span><span class="sxs-lookup"><span data-stu-id="22485-156">Save-Script</span></span>](Save-Script.md)

[<span data-ttu-id="22485-157">Update-Script</span><span class="sxs-lookup"><span data-stu-id="22485-157">Update-Script</span></span>](Update-Script.md)

