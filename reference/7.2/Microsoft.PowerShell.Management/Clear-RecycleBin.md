---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 01/29/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/clear-recyclebin?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-RecycleBin
ms.openlocfilehash: e7ce0f2bcd1ece0bb737aea1297641c37337f3e5
ms.sourcegitcommit: 81558c2adb9d109946a027e5b96e4d24b3b13747
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99602299"
---
# <span data-ttu-id="9738f-102">Clear-RecycleBin</span><span class="sxs-lookup"><span data-stu-id="9738f-102">Clear-RecycleBin</span></span>

## <span data-ttu-id="9738f-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="9738f-103">SYNOPSIS</span></span>
<span data-ttu-id="9738f-104">Очищает содержимое корзины.</span><span class="sxs-lookup"><span data-stu-id="9738f-104">Clears the contents of a recycle bin.</span></span>

## <span data-ttu-id="9738f-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9738f-105">SYNTAX</span></span>

### <span data-ttu-id="9738f-106">Все</span><span class="sxs-lookup"><span data-stu-id="9738f-106">All</span></span>

```
Clear-RecycleBin [[-DriveLetter] <String[]>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="9738f-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9738f-107">DESCRIPTION</span></span>

<span data-ttu-id="9738f-108">`Clear-RecycleBin`Командлет удаляет содержимое корзины компьютера.</span><span class="sxs-lookup"><span data-stu-id="9738f-108">The `Clear-RecycleBin` cmdlet deletes the content of a computer's recycle bin.</span></span> <span data-ttu-id="9738f-109">Это действие аналогично использованию **пустой корзины** Windows.</span><span class="sxs-lookup"><span data-stu-id="9738f-109">This action is like using Windows **Empty Recycle Bin**.</span></span>

<span data-ttu-id="9738f-110">Этот командлет был добавлен снова в PowerShell 7.</span><span class="sxs-lookup"><span data-stu-id="9738f-110">This cmdlet was readded in PowerShell 7.</span></span>

## <span data-ttu-id="9738f-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="9738f-111">EXAMPLES</span></span>

### <span data-ttu-id="9738f-112">1: очистить все корзины</span><span class="sxs-lookup"><span data-stu-id="9738f-112">1: Clear all recycle bins</span></span>

<span data-ttu-id="9738f-113">В этом примере очищаются все корзины локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="9738f-113">In this example, all the local computer's recycle bins are cleared.</span></span>

```powershell
Clear-RecycleBin
```

```Output
Confirm
Are you sure you want to perform this action?
Performing the operation "Clear-RecycleBin" on target "All of the contents of the Recycle Bin".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="9738f-114">`Clear-RecycleBin` запрашивает у пользователя подтверждение очистки всех корзин на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="9738f-114">`Clear-RecycleBin` prompts the user for confirmation to clear all recycle bins on the local computer.</span></span>

### <span data-ttu-id="9738f-115">2: Очистка указанной корзины</span><span class="sxs-lookup"><span data-stu-id="9738f-115">2: Clear a specified recycle bin</span></span>

<span data-ttu-id="9738f-116">В этом примере очищается корзина для указанной буквы диска.</span><span class="sxs-lookup"><span data-stu-id="9738f-116">This example clears the recycle bin for a specified drive letter.</span></span>

```powershell
Clear-RecycleBin -DriveLetter C
```

<span data-ttu-id="9738f-117">`Clear-RecycleBin` использует параметр **буква_диска** для указания корзины на томе **C** .</span><span class="sxs-lookup"><span data-stu-id="9738f-117">`Clear-RecycleBin` uses the **DriveLetter** parameter to specify the recycle bin on the **C** volume.</span></span> <span data-ttu-id="9738f-118">Пользователю будет предложено подтвердить выполнение команды.</span><span class="sxs-lookup"><span data-stu-id="9738f-118">The user is prompted for confirmation to run the command.</span></span>

### <span data-ttu-id="9738f-119">3: очистить все корзины без подтверждения</span><span class="sxs-lookup"><span data-stu-id="9738f-119">3: Clear all recycle bins without confirmation</span></span>

<span data-ttu-id="9738f-120">В этом примере не запрашивается подтверждение очистки корзины локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="9738f-120">This example doesn't prompt for confirmation to clear the local computer's recycle bins.</span></span>

```powershell
Clear-RecycleBin -Force
```

<span data-ttu-id="9738f-121">`Clear-RecycleBin` использует параметр **Force** и не запрашивает у пользователя подтверждение очистки всех корзин на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="9738f-121">`Clear-RecycleBin` uses the **Force** parameter and doesn't prompt the user for confirmation to clear all recycle bins on the local computer.</span></span>

<span data-ttu-id="9738f-122">Альтернативой является замена на `-Force` `-Confirm:$false` .</span><span class="sxs-lookup"><span data-stu-id="9738f-122">An alternative is to replace `-Force` with `-Confirm:$false`.</span></span>

## <span data-ttu-id="9738f-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9738f-123">PARAMETERS</span></span>

### <span data-ttu-id="9738f-124">-Буква_диска</span><span class="sxs-lookup"><span data-stu-id="9738f-124">-DriveLetter</span></span>

<span data-ttu-id="9738f-125">Задает очистку корзины для одного диска или массива букв диска.</span><span class="sxs-lookup"><span data-stu-id="9738f-125">Specifies the recycle bin to clear for a single drive letter or an array of drive letters.</span></span>

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

### <span data-ttu-id="9738f-126">-Force</span><span class="sxs-lookup"><span data-stu-id="9738f-126">-Force</span></span>

<span data-ttu-id="9738f-127">Указывает, что пользователю не предлагается подтверждение очистки корзины.</span><span class="sxs-lookup"><span data-stu-id="9738f-127">Specifies that the user isn't prompted for confirmation to clear a recycle bin.</span></span> <span data-ttu-id="9738f-128">Параметр **Force** также переопределяет параметры **WhatIf** и **Confirm** .</span><span class="sxs-lookup"><span data-stu-id="9738f-128">The **Force** parameter also overrides the **WhatIf** and **Confirm** parameters.</span></span>

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

### <span data-ttu-id="9738f-129">-Confirm</span><span class="sxs-lookup"><span data-stu-id="9738f-129">-Confirm</span></span>

<span data-ttu-id="9738f-130">Запрашивает подтверждение пользователя перед запуском командлета.</span><span class="sxs-lookup"><span data-stu-id="9738f-130">Prompts for user confirmation before running the cmdlet.</span></span> <span data-ttu-id="9738f-131">Пользователю предлагается подтверждение, даже если параметр **Confirm** не указан.</span><span class="sxs-lookup"><span data-stu-id="9738f-131">The user is prompted for confirmation even if the **Confirm** parameter isn't specified.</span></span>

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

### <span data-ttu-id="9738f-132">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="9738f-132">-WhatIf</span></span>

<span data-ttu-id="9738f-133">Показывает, что произойдет при `Clear-RecycleBin` запуске.</span><span class="sxs-lookup"><span data-stu-id="9738f-133">Shows what would happen if `Clear-RecycleBin` runs.</span></span> <span data-ttu-id="9738f-134">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="9738f-134">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="9738f-135">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="9738f-135">CommonParameters</span></span>

<span data-ttu-id="9738f-136">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9738f-136">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9738f-137">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9738f-137">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9738f-138">Входные данные</span><span class="sxs-lookup"><span data-stu-id="9738f-138">INPUTS</span></span>

## <span data-ttu-id="9738f-139">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="9738f-139">OUTPUTS</span></span>

### <span data-ttu-id="9738f-140">None</span><span class="sxs-lookup"><span data-stu-id="9738f-140">None</span></span>

## <span data-ttu-id="9738f-141">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="9738f-141">NOTES</span></span>

<span data-ttu-id="9738f-142">Этот командлет доступен только на платформах Windows.</span><span class="sxs-lookup"><span data-stu-id="9738f-142">This cmdlet is only available on Windows platforms.</span></span>

## <span data-ttu-id="9738f-143">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="9738f-143">RELATED LINKS</span></span>
