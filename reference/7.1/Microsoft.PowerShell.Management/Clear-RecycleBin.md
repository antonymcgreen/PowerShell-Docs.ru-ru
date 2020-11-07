---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/clear-recyclebin?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-RecycleBin
ms.openlocfilehash: caae499b6d6b896acad94e2d83462676d0225165
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2020
ms.locfileid: "94347454"
---
# <span data-ttu-id="5c525-103">Clear-RecycleBin</span><span class="sxs-lookup"><span data-stu-id="5c525-103">Clear-RecycleBin</span></span>

## <span data-ttu-id="5c525-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="5c525-104">SYNOPSIS</span></span>
<span data-ttu-id="5c525-105">Очищает содержимое корзины.</span><span class="sxs-lookup"><span data-stu-id="5c525-105">Clears the contents of a recycle bin.</span></span>

## <span data-ttu-id="5c525-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5c525-106">SYNTAX</span></span>

### <span data-ttu-id="5c525-107">Все</span><span class="sxs-lookup"><span data-stu-id="5c525-107">All</span></span>

```
Clear-RecycleBin [[-DriveLetter] <String[]>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="5c525-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5c525-108">DESCRIPTION</span></span>

<span data-ttu-id="5c525-109">`Clear-RecycleBin`Командлет удаляет содержимое корзины компьютера.</span><span class="sxs-lookup"><span data-stu-id="5c525-109">The `Clear-RecycleBin` cmdlet deletes the content of a computer's recycle bin.</span></span> <span data-ttu-id="5c525-110">Это действие аналогично использованию **пустой корзины** Windows.</span><span class="sxs-lookup"><span data-stu-id="5c525-110">This action is like using Windows **Empty Recycle Bin**.</span></span>

<span data-ttu-id="5c525-111">Этот командлет был добавлен снова в PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="5c525-111">This cmdlet was readded in PowerShell 7.</span></span>

## <span data-ttu-id="5c525-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="5c525-112">EXAMPLES</span></span>

### <span data-ttu-id="5c525-113">1: очистить все корзины</span><span class="sxs-lookup"><span data-stu-id="5c525-113">1: Clear all recycle bins</span></span>

<span data-ttu-id="5c525-114">В этом примере очищаются все корзины локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="5c525-114">In this example, all the local computer's recycle bins are cleared.</span></span>

```powershell
Clear-RecycleBin
```

```Output
Confirm
Are you sure you want to perform this action?
Performing the operation "Clear-RecycleBin" on target "All of the contents of the Recycle Bin".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="5c525-115">`Clear-RecycleBin` запрашивает у пользователя подтверждение очистки всех корзин на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="5c525-115">`Clear-RecycleBin` prompts the user for confirmation to clear all recycle bins on the local computer.</span></span>

### <span data-ttu-id="5c525-116">2: Очистка указанной корзины</span><span class="sxs-lookup"><span data-stu-id="5c525-116">2: Clear a specified recycle bin</span></span>

<span data-ttu-id="5c525-117">В этом примере очищается корзина для указанной буквы диска.</span><span class="sxs-lookup"><span data-stu-id="5c525-117">This example clears the recycle bin for a specified drive letter.</span></span>

```powershell
Clear-RecycleBin -DriveLetter C
```

<span data-ttu-id="5c525-118">`Clear-RecycleBin` использует параметр **буква_диска** для указания корзины на томе **C** .</span><span class="sxs-lookup"><span data-stu-id="5c525-118">`Clear-RecycleBin` uses the **DriveLetter** parameter to specify the recycle bin on the **C** volume.</span></span> <span data-ttu-id="5c525-119">Пользователю будет предложено подтвердить выполнение команды.</span><span class="sxs-lookup"><span data-stu-id="5c525-119">The user is prompted for confirmation to run the command.</span></span>

### <span data-ttu-id="5c525-120">3: очистить все корзины без подтверждения</span><span class="sxs-lookup"><span data-stu-id="5c525-120">3: Clear all recycle bins without confirmation</span></span>

<span data-ttu-id="5c525-121">В этом примере не запрашивается подтверждение очистки корзины локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="5c525-121">This example doesn't prompt for confirmation to clear the local computer's recycle bins.</span></span>

```powershell
Clear-RecycleBin -Force
```

<span data-ttu-id="5c525-122">`Clear-RecycleBin` использует параметр **Force** и не запрашивает у пользователя подтверждение очистки всех корзин на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="5c525-122">`Clear-RecycleBin` uses the **Force** parameter and doesn't prompt the user for confirmation to clear all recycle bins on the local computer.</span></span>

<span data-ttu-id="5c525-123">Альтернативой является замена на `-Force` `-Confirm:$false` .</span><span class="sxs-lookup"><span data-stu-id="5c525-123">An alternative is to replace `-Force` with `-Confirm:$false`.</span></span>

## <span data-ttu-id="5c525-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5c525-124">PARAMETERS</span></span>

### <span data-ttu-id="5c525-125">-Буква_диска</span><span class="sxs-lookup"><span data-stu-id="5c525-125">-DriveLetter</span></span>

<span data-ttu-id="5c525-126">Задает очистку корзины для одного диска или массива букв диска.</span><span class="sxs-lookup"><span data-stu-id="5c525-126">Specifies the recycle bin to clear for a single drive letter or an array of drive letters.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="5c525-127">-Force</span><span class="sxs-lookup"><span data-stu-id="5c525-127">-Force</span></span>

<span data-ttu-id="5c525-128">Указывает, что пользователю не предлагается подтверждение очистки корзины.</span><span class="sxs-lookup"><span data-stu-id="5c525-128">Specifies that the user isn't prompted for confirmation to clear a recycle bin.</span></span>

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

### <span data-ttu-id="5c525-129">-Confirm</span><span class="sxs-lookup"><span data-stu-id="5c525-129">-Confirm</span></span>

<span data-ttu-id="5c525-130">Запрашивает подтверждение пользователя перед запуском командлета.</span><span class="sxs-lookup"><span data-stu-id="5c525-130">Prompts for user confirmation before running the cmdlet.</span></span> <span data-ttu-id="5c525-131">Пользователю предлагается подтверждение, даже если параметр **Confirm** не указан.</span><span class="sxs-lookup"><span data-stu-id="5c525-131">The user is prompted for confirmation even if the **Confirm** parameter isn't specified.</span></span>

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

### <span data-ttu-id="5c525-132">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="5c525-132">-WhatIf</span></span>

<span data-ttu-id="5c525-133">Показывает, что произойдет при `Clear-RecycleBin` запуске.</span><span class="sxs-lookup"><span data-stu-id="5c525-133">Shows what would happen if `Clear-RecycleBin` runs.</span></span> <span data-ttu-id="5c525-134">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="5c525-134">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="5c525-135">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="5c525-135">CommonParameters</span></span>

<span data-ttu-id="5c525-136">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5c525-136">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5c525-137">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5c525-137">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5c525-138">Входные данные</span><span class="sxs-lookup"><span data-stu-id="5c525-138">INPUTS</span></span>

## <span data-ttu-id="5c525-139">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="5c525-139">OUTPUTS</span></span>

### <span data-ttu-id="5c525-140">Нет</span><span class="sxs-lookup"><span data-stu-id="5c525-140">None</span></span>

## <span data-ttu-id="5c525-141">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="5c525-141">NOTES</span></span>

<span data-ttu-id="5c525-142">Этот командлет доступен только на платформах Windows.</span><span class="sxs-lookup"><span data-stu-id="5c525-142">This cmdlet is only available on Windows platforms.</span></span>

## <span data-ttu-id="5c525-143">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="5c525-143">RELATED LINKS</span></span>
