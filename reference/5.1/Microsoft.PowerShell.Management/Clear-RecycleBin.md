---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 01/29/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/clear-recyclebin?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-RecycleBin
ms.openlocfilehash: f59cc9ff4e6d1b6579292c84f440bbbdd156b65c
ms.sourcegitcommit: 81558c2adb9d109946a027e5b96e4d24b3b13747
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99098569"
---
# <span data-ttu-id="3ad41-102">Clear-RecycleBin</span><span class="sxs-lookup"><span data-stu-id="3ad41-102">Clear-RecycleBin</span></span>

## <span data-ttu-id="3ad41-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="3ad41-103">SYNOPSIS</span></span>
<span data-ttu-id="3ad41-104">Очищает содержимое корзины.</span><span class="sxs-lookup"><span data-stu-id="3ad41-104">Clears the contents of a recycle bin.</span></span>

## <span data-ttu-id="3ad41-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3ad41-105">SYNTAX</span></span>

### <span data-ttu-id="3ad41-106">Все</span><span class="sxs-lookup"><span data-stu-id="3ad41-106">All</span></span>

```
Clear-RecycleBin [[-DriveLetter] <String[]>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="3ad41-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3ad41-107">DESCRIPTION</span></span>

<span data-ttu-id="3ad41-108">`Clear-RecycleBin`Командлет удаляет содержимое корзины компьютера.</span><span class="sxs-lookup"><span data-stu-id="3ad41-108">The `Clear-RecycleBin` cmdlet deletes the content of a computer's recycle bin.</span></span> <span data-ttu-id="3ad41-109">Это действие аналогично использованию **пустой корзины** Windows.</span><span class="sxs-lookup"><span data-stu-id="3ad41-109">This action is like using Windows **Empty Recycle Bin**.</span></span>

## <span data-ttu-id="3ad41-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="3ad41-110">EXAMPLES</span></span>

### <span data-ttu-id="3ad41-111">1: очистить все корзины</span><span class="sxs-lookup"><span data-stu-id="3ad41-111">1: Clear all recycle bins</span></span>

<span data-ttu-id="3ad41-112">В этом примере очищаются все корзины локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="3ad41-112">In this example, all the local computer's recycle bins are cleared.</span></span>

```powershell
Clear-RecycleBin
```

```Output
Confirm
Are you sure you want to perform this action?
Performing the operation "Clear-RecycleBin" on target "All of the contents of the Recycle Bin".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="3ad41-113">`Clear-RecycleBin` запрашивает у пользователя подтверждение очистки всех корзин на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3ad41-113">`Clear-RecycleBin` prompts the user for confirmation to clear all recycle bins on the local computer.</span></span>

### <span data-ttu-id="3ad41-114">2: Очистка указанной корзины</span><span class="sxs-lookup"><span data-stu-id="3ad41-114">2: Clear a specified recycle bin</span></span>

<span data-ttu-id="3ad41-115">В этом примере очищается корзина для указанной буквы диска.</span><span class="sxs-lookup"><span data-stu-id="3ad41-115">This example clears the recycle bin for a specified drive letter.</span></span>

```powershell
Clear-RecycleBin -DriveLetter C
```

<span data-ttu-id="3ad41-116">`Clear-RecycleBin` использует параметр **буква_диска** для указания корзины на томе **C** .</span><span class="sxs-lookup"><span data-stu-id="3ad41-116">`Clear-RecycleBin` uses the **DriveLetter** parameter to specify the recycle bin on the **C** volume.</span></span> <span data-ttu-id="3ad41-117">Пользователю будет предложено подтвердить выполнение команды.</span><span class="sxs-lookup"><span data-stu-id="3ad41-117">The user is prompted for confirmation to run the command.</span></span>

### <span data-ttu-id="3ad41-118">3: очистить все корзины без подтверждения</span><span class="sxs-lookup"><span data-stu-id="3ad41-118">3: Clear all recycle bins without confirmation</span></span>

<span data-ttu-id="3ad41-119">В этом примере не запрашивается подтверждение очистки корзины локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="3ad41-119">This example doesn't prompt for confirmation to clear the local computer's recycle bins.</span></span>

```powershell
Clear-RecycleBin -Force
```

<span data-ttu-id="3ad41-120">`Clear-RecycleBin` использует параметр **Force** и не запрашивает у пользователя подтверждение очистки всех корзин на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3ad41-120">`Clear-RecycleBin` uses the **Force** parameter and doesn't prompt the user for confirmation to clear all recycle bins on the local computer.</span></span>

<span data-ttu-id="3ad41-121">Альтернативой является замена на `-Force` `-Confirm:$false` .</span><span class="sxs-lookup"><span data-stu-id="3ad41-121">An alternative is to replace `-Force` with `-Confirm:$false`.</span></span>

## <span data-ttu-id="3ad41-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3ad41-122">PARAMETERS</span></span>

### <span data-ttu-id="3ad41-123">-Буква_диска</span><span class="sxs-lookup"><span data-stu-id="3ad41-123">-DriveLetter</span></span>

<span data-ttu-id="3ad41-124">Задает очистку корзины для одного диска или массива букв диска.</span><span class="sxs-lookup"><span data-stu-id="3ad41-124">Specifies the recycle bin to clear for a single drive letter or an array of drive letters.</span></span>

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

### <span data-ttu-id="3ad41-125">-Force</span><span class="sxs-lookup"><span data-stu-id="3ad41-125">-Force</span></span>

<span data-ttu-id="3ad41-126">Указывает, что пользователю не предлагается подтверждение очистки корзины.</span><span class="sxs-lookup"><span data-stu-id="3ad41-126">Specifies that the user isn't prompted for confirmation to clear a recycle bin.</span></span> <span data-ttu-id="3ad41-127">Параметр **Force** также переопределяет параметры **WhatIf** и **Confirm** .</span><span class="sxs-lookup"><span data-stu-id="3ad41-127">The **Force** parameter also overrides the **WhatIf** and **Confirm** parameters.</span></span>

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

### <span data-ttu-id="3ad41-128">-Confirm</span><span class="sxs-lookup"><span data-stu-id="3ad41-128">-Confirm</span></span>

<span data-ttu-id="3ad41-129">Запрашивает подтверждение пользователя перед запуском командлета.</span><span class="sxs-lookup"><span data-stu-id="3ad41-129">Prompts for user confirmation before running the cmdlet.</span></span> <span data-ttu-id="3ad41-130">Пользователю предлагается подтверждение, даже если параметр **Confirm** не указан.</span><span class="sxs-lookup"><span data-stu-id="3ad41-130">The user is prompted for confirmation even if the **Confirm** parameter isn't specified.</span></span>

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

### <span data-ttu-id="3ad41-131">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="3ad41-131">-WhatIf</span></span>

<span data-ttu-id="3ad41-132">Показывает, что произойдет при `Clear-RecycleBin` запуске.</span><span class="sxs-lookup"><span data-stu-id="3ad41-132">Shows what would happen if `Clear-RecycleBin` runs.</span></span> <span data-ttu-id="3ad41-133">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="3ad41-133">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="3ad41-134">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="3ad41-134">CommonParameters</span></span>

<span data-ttu-id="3ad41-135">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3ad41-135">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3ad41-136">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3ad41-136">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3ad41-137">Входные данные</span><span class="sxs-lookup"><span data-stu-id="3ad41-137">INPUTS</span></span>

## <span data-ttu-id="3ad41-138">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="3ad41-138">OUTPUTS</span></span>

### <span data-ttu-id="3ad41-139">Нет</span><span class="sxs-lookup"><span data-stu-id="3ad41-139">None</span></span>

## <span data-ttu-id="3ad41-140">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="3ad41-140">NOTES</span></span>

## <span data-ttu-id="3ad41-141">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="3ad41-141">RELATED LINKS</span></span>
