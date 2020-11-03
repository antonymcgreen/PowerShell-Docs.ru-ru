---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/clear-recyclebin?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-RecycleBin
ms.openlocfilehash: 7e34db6eb29bf60da5ce1217653db815347d69ae
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229465"
---
# <span data-ttu-id="3903d-103">Clear-RecycleBin</span><span class="sxs-lookup"><span data-stu-id="3903d-103">Clear-RecycleBin</span></span>

## <span data-ttu-id="3903d-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="3903d-104">SYNOPSIS</span></span>
<span data-ttu-id="3903d-105">Очищает содержимое корзины.</span><span class="sxs-lookup"><span data-stu-id="3903d-105">Clears the contents of a recycle bin.</span></span>

## <span data-ttu-id="3903d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3903d-106">SYNTAX</span></span>

### <span data-ttu-id="3903d-107">Все</span><span class="sxs-lookup"><span data-stu-id="3903d-107">All</span></span>

```
Clear-RecycleBin [[-DriveLetter] <String[]>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="3903d-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3903d-108">DESCRIPTION</span></span>

<span data-ttu-id="3903d-109">`Clear-RecycleBin`Командлет удаляет содержимое корзины компьютера.</span><span class="sxs-lookup"><span data-stu-id="3903d-109">The `Clear-RecycleBin` cmdlet deletes the content of a computer's recycle bin.</span></span> <span data-ttu-id="3903d-110">Это действие аналогично использованию **пустой корзины** Windows.</span><span class="sxs-lookup"><span data-stu-id="3903d-110">This action is like using Windows **Empty Recycle Bin** .</span></span>

<span data-ttu-id="3903d-111">Этот командлет был добавлен снова в PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="3903d-111">This cmdlet was readded in PowerShell 7.</span></span>

## <span data-ttu-id="3903d-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="3903d-112">EXAMPLES</span></span>

### <span data-ttu-id="3903d-113">1: очистить все корзины</span><span class="sxs-lookup"><span data-stu-id="3903d-113">1: Clear all recycle bins</span></span>

<span data-ttu-id="3903d-114">В этом примере очищаются все корзины локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="3903d-114">In this example, all the local computer's recycle bins are cleared.</span></span>

```powershell
Clear-RecycleBin
```

```Output
Confirm
Are you sure you want to perform this action?
Performing the operation "Clear-RecycleBin" on target "All of the contents of the Recycle Bin".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="3903d-115">`Clear-RecycleBin` запрашивает у пользователя подтверждение очистки всех корзин на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3903d-115">`Clear-RecycleBin` prompts the user for confirmation to clear all recycle bins on the local computer.</span></span>

### <span data-ttu-id="3903d-116">2: Очистка указанной корзины</span><span class="sxs-lookup"><span data-stu-id="3903d-116">2: Clear a specified recycle bin</span></span>

<span data-ttu-id="3903d-117">В этом примере очищается корзина для указанной буквы диска.</span><span class="sxs-lookup"><span data-stu-id="3903d-117">This example clears the recycle bin for a specified drive letter.</span></span>

```powershell
Clear-RecycleBin -DriveLetter C
```

<span data-ttu-id="3903d-118">`Clear-RecycleBin` использует параметр **буква_диска** для указания корзины на томе **C** .</span><span class="sxs-lookup"><span data-stu-id="3903d-118">`Clear-RecycleBin` uses the **DriveLetter** parameter to specify the recycle bin on the **C** volume.</span></span> <span data-ttu-id="3903d-119">Пользователю будет предложено подтвердить выполнение команды.</span><span class="sxs-lookup"><span data-stu-id="3903d-119">The user is prompted for confirmation to run the command.</span></span>

### <span data-ttu-id="3903d-120">3: очистить все корзины без подтверждения</span><span class="sxs-lookup"><span data-stu-id="3903d-120">3: Clear all recycle bins without confirmation</span></span>

<span data-ttu-id="3903d-121">В этом примере не запрашивается подтверждение очистки корзины локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="3903d-121">This example doesn't prompt for confirmation to clear the local computer's recycle bins.</span></span>

```powershell
Clear-RecycleBin -Force
```

<span data-ttu-id="3903d-122">`Clear-RecycleBin` использует параметр **Force** и не запрашивает у пользователя подтверждение очистки всех корзин на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3903d-122">`Clear-RecycleBin` uses the **Force** parameter and doesn't prompt the user for confirmation to clear all recycle bins on the local computer.</span></span>

<span data-ttu-id="3903d-123">Альтернативой является замена на `-Force` `-Confirm:$false` .</span><span class="sxs-lookup"><span data-stu-id="3903d-123">An alternative is to replace `-Force` with `-Confirm:$false`.</span></span>

## <span data-ttu-id="3903d-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3903d-124">PARAMETERS</span></span>

### <span data-ttu-id="3903d-125">-Буква_диска</span><span class="sxs-lookup"><span data-stu-id="3903d-125">-DriveLetter</span></span>

<span data-ttu-id="3903d-126">Задает очистку корзины для одного диска или массива букв диска.</span><span class="sxs-lookup"><span data-stu-id="3903d-126">Specifies the recycle bin to clear for a single drive letter or an array of drive letters.</span></span>

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

### <span data-ttu-id="3903d-127">-Force</span><span class="sxs-lookup"><span data-stu-id="3903d-127">-Force</span></span>

<span data-ttu-id="3903d-128">Указывает, что пользователю не предлагается подтверждение очистки корзины.</span><span class="sxs-lookup"><span data-stu-id="3903d-128">Specifies that the user isn't prompted for confirmation to clear a recycle bin.</span></span>

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

### <span data-ttu-id="3903d-129">-Confirm</span><span class="sxs-lookup"><span data-stu-id="3903d-129">-Confirm</span></span>

<span data-ttu-id="3903d-130">Запрашивает подтверждение пользователя перед запуском командлета.</span><span class="sxs-lookup"><span data-stu-id="3903d-130">Prompts for user confirmation before running the cmdlet.</span></span> <span data-ttu-id="3903d-131">Пользователю предлагается подтверждение, даже если параметр **Confirm** не указан.</span><span class="sxs-lookup"><span data-stu-id="3903d-131">The user is prompted for confirmation even if the **Confirm** parameter isn't specified.</span></span>

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

### <span data-ttu-id="3903d-132">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="3903d-132">-WhatIf</span></span>

<span data-ttu-id="3903d-133">Показывает, что произойдет при `Clear-RecycleBin` запуске.</span><span class="sxs-lookup"><span data-stu-id="3903d-133">Shows what would happen if `Clear-RecycleBin` runs.</span></span> <span data-ttu-id="3903d-134">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="3903d-134">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="3903d-135">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="3903d-135">CommonParameters</span></span>

<span data-ttu-id="3903d-136">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3903d-136">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3903d-137">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3903d-137">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3903d-138">Входные данные</span><span class="sxs-lookup"><span data-stu-id="3903d-138">INPUTS</span></span>

## <span data-ttu-id="3903d-139">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="3903d-139">OUTPUTS</span></span>

### <span data-ttu-id="3903d-140">Нет</span><span class="sxs-lookup"><span data-stu-id="3903d-140">None</span></span>

## <span data-ttu-id="3903d-141">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="3903d-141">NOTES</span></span>

## <span data-ttu-id="3903d-142">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="3903d-142">RELATED LINKS</span></span>

