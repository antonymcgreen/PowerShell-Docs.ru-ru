---
external help file: PSModule-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/03/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/uninstall-script?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Uninstall-Script
ms.openlocfilehash: e285391bdfd68211883827babbc7075e4727f06d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228250"
---
# <span data-ttu-id="cabac-103">Uninstall-Script</span><span class="sxs-lookup"><span data-stu-id="cabac-103">Uninstall-Script</span></span>

## <span data-ttu-id="cabac-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="cabac-104">SYNOPSIS</span></span>
<span data-ttu-id="cabac-105">Удаляет скрипт.</span><span class="sxs-lookup"><span data-stu-id="cabac-105">Uninstalls a script.</span></span>

## <span data-ttu-id="cabac-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="cabac-106">SYNTAX</span></span>

### <span data-ttu-id="cabac-107">NameParameterSet (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="cabac-107">NameParameterSet (Default)</span></span>

```
Uninstall-Script [-Name] <String[]> [-MinimumVersion <String>] [-RequiredVersion <String>]
 [-MaximumVersion <String>] [-Force] [-AllowPrerelease] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="cabac-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="cabac-108">InputObject</span></span>

```
Uninstall-Script [-InputObject] <PSObject[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="cabac-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="cabac-109">DESCRIPTION</span></span>

<span data-ttu-id="cabac-110">`Uninstall-Script`Командлет удаляет указанный скрипт с локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="cabac-110">The `Uninstall-Script` cmdlet uninstalls a specified script from the local computer.</span></span>

## <span data-ttu-id="cabac-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="cabac-111">EXAMPLES</span></span>

### <span data-ttu-id="cabac-112">Пример 1. Удаление скрипта</span><span class="sxs-lookup"><span data-stu-id="cabac-112">Example 1: Uninstall a script</span></span>

<span data-ttu-id="cabac-113">В этом примере удаляется скрипт.</span><span class="sxs-lookup"><span data-stu-id="cabac-113">This example uninstalls a script.</span></span>

```powershell
Uninstall-Script -Name UpdateManagement-Template
```

<span data-ttu-id="cabac-114">`Uninstall-Script` использует параметр **Name** , чтобы указать скрипт для удаления с локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="cabac-114">`Uninstall-Script` uses the **Name** parameter to specify the script to uninstall from the local computer.</span></span>

### <span data-ttu-id="cabac-115">Пример 2. Использование конвейера для удаления сценария</span><span class="sxs-lookup"><span data-stu-id="cabac-115">Example 2: Use the pipeline to uninstall a script</span></span>

<span data-ttu-id="cabac-116">В этом примере конвейер используется для удаления скрипта.</span><span class="sxs-lookup"><span data-stu-id="cabac-116">In this example, the pipeline is used to uninstall a script.</span></span>

```powershell
Get-InstalledScript -Name UpdateManagement-Template | Uninstall-Script
```

<span data-ttu-id="cabac-117">`Get-InstalledScript` использует параметр **Name** для указания скрипта.</span><span class="sxs-lookup"><span data-stu-id="cabac-117">`Get-InstalledScript` uses the **Name** parameter to specify the script.</span></span> <span data-ttu-id="cabac-118">Объект отправляется по конвейеру в `Uninstall-Script` и удаляется скрипт.</span><span class="sxs-lookup"><span data-stu-id="cabac-118">The object is sent down the pipeline to `Uninstall-Script` and the script is uninstalled.</span></span>

## <span data-ttu-id="cabac-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="cabac-119">PARAMETERS</span></span>

### <span data-ttu-id="cabac-120">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="cabac-120">-AllowPrerelease</span></span>

<span data-ttu-id="cabac-121">Позволяет удалить скрипт, помеченный как предварительная версия.</span><span class="sxs-lookup"><span data-stu-id="cabac-121">Allows you to uninstall a script marked as a prerelease.</span></span>

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

### <span data-ttu-id="cabac-122">-Confirm</span><span class="sxs-lookup"><span data-stu-id="cabac-122">-Confirm</span></span>

<span data-ttu-id="cabac-123">Запрашивает подтверждение перед запуском `Uninstall-Script` .</span><span class="sxs-lookup"><span data-stu-id="cabac-123">Prompts you for confirmation before running `Uninstall-Script`.</span></span>

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

### <span data-ttu-id="cabac-124">-Force</span><span class="sxs-lookup"><span data-stu-id="cabac-124">-Force</span></span>

<span data-ttu-id="cabac-125">Принудительное `Uninstall-Script` выполнение без запроса подтверждения пользователя.</span><span class="sxs-lookup"><span data-stu-id="cabac-125">Forces `Uninstall-Script` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="cabac-126">-InputObject</span><span class="sxs-lookup"><span data-stu-id="cabac-126">-InputObject</span></span>

<span data-ttu-id="cabac-127">Принимает объект **PSRepositoryItemInfo** .</span><span class="sxs-lookup"><span data-stu-id="cabac-127">Accepts a **PSRepositoryItemInfo** object.</span></span> <span data-ttu-id="cabac-128">Например, выходные данные переводятся `Get-InstalledScript` в переменную и используют эту переменную в качестве аргумента **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="cabac-128">For example, output `Get-InstalledScript` to a variable and use that variable as the **InputObject** argument.</span></span>

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

### <span data-ttu-id="cabac-129">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="cabac-129">-MaximumVersion</span></span>

<span data-ttu-id="cabac-130">Указывает максимальную или самую новую версию скрипта для удаления.</span><span class="sxs-lookup"><span data-stu-id="cabac-130">Specifies the maximum, or newest, version of the script to uninstall.</span></span> <span data-ttu-id="cabac-131">Параметры **MaximumVersion** и **RequiredVersion** нельзя использовать в одной команде.</span><span class="sxs-lookup"><span data-stu-id="cabac-131">The **MaximumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="cabac-132">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="cabac-132">-MinimumVersion</span></span>

<span data-ttu-id="cabac-133">Указывает минимальную версию скрипта для удаления.</span><span class="sxs-lookup"><span data-stu-id="cabac-133">Specifies the minimum version of the script to uninstall.</span></span> <span data-ttu-id="cabac-134">Параметры **MinimumVersion** и **RequiredVersion** нельзя использовать в одной команде.</span><span class="sxs-lookup"><span data-stu-id="cabac-134">The **MinimumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="cabac-135">-Name</span><span class="sxs-lookup"><span data-stu-id="cabac-135">-Name</span></span>

<span data-ttu-id="cabac-136">Указывает массив имен скриптов для удаления.</span><span class="sxs-lookup"><span data-stu-id="cabac-136">Specifies an array of script names to uninstall.</span></span>

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

### <span data-ttu-id="cabac-137">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="cabac-137">-RequiredVersion</span></span>

<span data-ttu-id="cabac-138">Указывает точный номер версии скрипта для удаления.</span><span class="sxs-lookup"><span data-stu-id="cabac-138">Specifies the exact version number of the script to uninstall.</span></span>

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

### <span data-ttu-id="cabac-139">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="cabac-139">-WhatIf</span></span>

<span data-ttu-id="cabac-140">Показывает, что произойдет при `Uninstall-Script` запуске.</span><span class="sxs-lookup"><span data-stu-id="cabac-140">Shows what would happen if `Uninstall-Script` runs.</span></span> <span data-ttu-id="cabac-141">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="cabac-141">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="cabac-142">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="cabac-142">CommonParameters</span></span>

<span data-ttu-id="cabac-143">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="cabac-143">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="cabac-144">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="cabac-144">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="cabac-145">Входные данные</span><span class="sxs-lookup"><span data-stu-id="cabac-145">INPUTS</span></span>

### <span data-ttu-id="cabac-146">System.String[]</span><span class="sxs-lookup"><span data-stu-id="cabac-146">System.String[]</span></span>

### <span data-ttu-id="cabac-147">System. Management. Automation. PSObject []</span><span class="sxs-lookup"><span data-stu-id="cabac-147">System.Management.Automation.PSObject[]</span></span>

<span data-ttu-id="cabac-148">`Uninstall-Script` принимает объекты **PSRepositoryItemInfo** из конвейера.</span><span class="sxs-lookup"><span data-stu-id="cabac-148">`Uninstall-Script` accepts **PSRepositoryItemInfo** objects from the pipeline.</span></span>

### <span data-ttu-id="cabac-149">System.String</span><span class="sxs-lookup"><span data-stu-id="cabac-149">System.String</span></span>

## <span data-ttu-id="cabac-150">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="cabac-150">OUTPUTS</span></span>

### <span data-ttu-id="cabac-151">System.Object</span><span class="sxs-lookup"><span data-stu-id="cabac-151">System.Object</span></span>

## <span data-ttu-id="cabac-152">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="cabac-152">NOTES</span></span>

## <span data-ttu-id="cabac-153">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="cabac-153">RELATED LINKS</span></span>

[<span data-ttu-id="cabac-154">Find-Script</span><span class="sxs-lookup"><span data-stu-id="cabac-154">Find-Script</span></span>](Find-Script.md)

[<span data-ttu-id="cabac-155">Install-Script</span><span class="sxs-lookup"><span data-stu-id="cabac-155">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="cabac-156">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="cabac-156">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="cabac-157">Save-Script</span><span class="sxs-lookup"><span data-stu-id="cabac-157">Save-Script</span></span>](Save-Script.md)

[<span data-ttu-id="cabac-158">Update-Script</span><span class="sxs-lookup"><span data-stu-id="cabac-158">Update-Script</span></span>](Update-Script.md)
