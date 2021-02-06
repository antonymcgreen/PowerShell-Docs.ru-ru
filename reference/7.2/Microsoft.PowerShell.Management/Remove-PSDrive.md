---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-psdrive?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSDrive
ms.openlocfilehash: d20a348f3f5ba193eb85e0f9d0e2cc11ad083b47
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604362"
---
# <span data-ttu-id="f06f0-102">Remove-PSDrive</span><span class="sxs-lookup"><span data-stu-id="f06f0-102">Remove-PSDrive</span></span>

## <span data-ttu-id="f06f0-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="f06f0-103">SYNOPSIS</span></span>
<span data-ttu-id="f06f0-104">Удаляет временные диски PowerShell и отключает сопоставленные сетевые диски.</span><span class="sxs-lookup"><span data-stu-id="f06f0-104">Deletes temporary PowerShell drives and disconnects mapped network drives.</span></span>

## <span data-ttu-id="f06f0-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f06f0-105">SYNTAX</span></span>

### <span data-ttu-id="f06f0-106">Имя (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="f06f0-106">Name (Default)</span></span>

```
Remove-PSDrive [-Name] <String[]> [-PSProvider <String[]>] [-Scope <String>] [-Force]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="f06f0-107">литералнаме</span><span class="sxs-lookup"><span data-stu-id="f06f0-107">LiteralName</span></span>

```
Remove-PSDrive [-LiteralName] <String[]> [-PSProvider <String[]>] [-Scope <String>] [-Force]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="f06f0-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f06f0-108">DESCRIPTION</span></span>

<span data-ttu-id="f06f0-109">`Remove-PSDrive`Командлет удаляет временные диски PowerShell, созданные с помощью `New-PSDrive` командлета.</span><span class="sxs-lookup"><span data-stu-id="f06f0-109">The `Remove-PSDrive` cmdlet deletes temporary PowerShell drives that were created by using the `New-PSDrive` cmdlet.</span></span>

<span data-ttu-id="f06f0-110">Начиная с Windows PowerShell 3,0, `Remove-PSDrive` также отключает подключенные сетевые диски, включая, но не ограниченные, дисками, созданными с помощью `Persist` параметра `New-PSDrive` .</span><span class="sxs-lookup"><span data-stu-id="f06f0-110">Beginning in Windows PowerShell 3.0, `Remove-PSDrive` also disconnects mapped network drives, including, but not limited to, drives created by using the `Persist` parameter of `New-PSDrive`.</span></span>

<span data-ttu-id="f06f0-111">`Remove-PSDrive` невозможно удалить физические или логические диски Windows.</span><span class="sxs-lookup"><span data-stu-id="f06f0-111">`Remove-PSDrive` cannot delete Windows physical or logical drives.</span></span>

<span data-ttu-id="f06f0-112">Начиная с Windows PowerShell 3,0, когда к компьютеру подключен внешний диск, PowerShell автоматически добавляет PSDrive в файловую систему, представляющую новый диск.</span><span class="sxs-lookup"><span data-stu-id="f06f0-112">Beginning in Windows PowerShell 3.0, when an external drive is connected to the computer, PowerShell automatically adds a PSDrive to the file system that represents the new drive.</span></span>
<span data-ttu-id="f06f0-113">Перезапускать PowerShell не требуется.</span><span class="sxs-lookup"><span data-stu-id="f06f0-113">You do not need to restart PowerShell.</span></span>
<span data-ttu-id="f06f0-114">Аналогично, когда внешний диск отключается от компьютера, PowerShell автоматически удаляет PSDrive, представляющий удаленный диск.</span><span class="sxs-lookup"><span data-stu-id="f06f0-114">Similarly, when an external drive is disconnected from the computer, PowerShell automatically deletes the PSDrive that represents the removed drive.</span></span>

## <span data-ttu-id="f06f0-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="f06f0-115">EXAMPLES</span></span>

### <span data-ttu-id="f06f0-116">Пример 1. Удаление диска файловой системы</span><span class="sxs-lookup"><span data-stu-id="f06f0-116">Example 1: Remove a file system drive</span></span>

<span data-ttu-id="f06f0-117">Эта команда удаляет временный диск файловой системы с именем smp.</span><span class="sxs-lookup"><span data-stu-id="f06f0-117">This command removes a temporary file system drive named "smp".</span></span>

```powershell
Remove-PSDrive -Name smp
```

### <span data-ttu-id="f06f0-118">Пример 2. удаление сопоставленных сетевых дисков</span><span class="sxs-lookup"><span data-stu-id="f06f0-118">Example 2: Remove mapped network drives</span></span>

<span data-ttu-id="f06f0-119">Эта команда использует `Remove-PSDrive` для отключения подключенных сетевых дисков X: и S:.</span><span class="sxs-lookup"><span data-stu-id="f06f0-119">This command uses `Remove-PSDrive` to disconnect the X: and S: mapped network drives.</span></span>

```powershell
Get-PSDrive X, S | Remove-PSDrive
```

## <span data-ttu-id="f06f0-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f06f0-120">PARAMETERS</span></span>

### <span data-ttu-id="f06f0-121">-Force</span><span class="sxs-lookup"><span data-stu-id="f06f0-121">-Force</span></span>

<span data-ttu-id="f06f0-122">Удаляет текущий диск PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f06f0-122">Removes the current PowerShell drive.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f06f0-123">-Литералнаме</span><span class="sxs-lookup"><span data-stu-id="f06f0-123">-LiteralName</span></span>

<span data-ttu-id="f06f0-124">Задает имя диска.</span><span class="sxs-lookup"><span data-stu-id="f06f0-124">Specifies the name of the drive.</span></span>

<span data-ttu-id="f06f0-125">Значение параметра **LiteralName** используется именно так, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="f06f0-125">The value of **LiteralName** is used exactly as typed.</span></span>
<span data-ttu-id="f06f0-126">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="f06f0-126">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="f06f0-127">Если в имени есть escape-символы, заключите их в одиночные кавычки (').</span><span class="sxs-lookup"><span data-stu-id="f06f0-127">If the name includes escape characters, enclose it in single quotation marks (').</span></span>
<span data-ttu-id="f06f0-128">Одинарные кавычки предписывает PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="f06f0-128">Single quotation marks instruct PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="f06f0-129">-Name</span><span class="sxs-lookup"><span data-stu-id="f06f0-129">-Name</span></span>

<span data-ttu-id="f06f0-130">Указывает имена дисков, которые нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="f06f0-130">Specifies the names of the drives to remove.</span></span>
<span data-ttu-id="f06f0-131">Не ставьте двоеточие (:) после имени диска.</span><span class="sxs-lookup"><span data-stu-id="f06f0-131">Do not type a colon (:) after the drive name.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="f06f0-132">-PSProvider</span><span class="sxs-lookup"><span data-stu-id="f06f0-132">-PSProvider</span></span>

<span data-ttu-id="f06f0-133">Указывает массив объектов **psprovider** .</span><span class="sxs-lookup"><span data-stu-id="f06f0-133">Specifies an array of **PSProvider** objects.</span></span>
<span data-ttu-id="f06f0-134">Этот командлет удаляет и отключает все диски, связанные с указанным поставщиком PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f06f0-134">This cmdlet removes and disconnects all of the drives associated with the specified PowerShell provider.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="f06f0-135">-Scope</span><span class="sxs-lookup"><span data-stu-id="f06f0-135">-Scope</span></span>

<span data-ttu-id="f06f0-136">Указывает область для диска.</span><span class="sxs-lookup"><span data-stu-id="f06f0-136">Specifies a scope for the drive.</span></span>
<span data-ttu-id="f06f0-137">Допустимые значения для этого параметра: Global, Local и script или Number, относящихся к текущей области.</span><span class="sxs-lookup"><span data-stu-id="f06f0-137">The acceptable values for this parameter are: Global, Local, and Script, or a number relative to the current scope.</span></span> <span data-ttu-id="f06f0-138">Области с номером 0 по числу областей.</span><span class="sxs-lookup"><span data-stu-id="f06f0-138">Scopes number 0 through the number of scopes.</span></span> <span data-ttu-id="f06f0-139">Текущий номер области равен 0, а его родительский элемент — 1.</span><span class="sxs-lookup"><span data-stu-id="f06f0-139">The current scope number is 0 and its parent is 1.</span></span>
<span data-ttu-id="f06f0-140">Дополнительные сведения см. в разделе [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="f06f0-140">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Local
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="f06f0-141">-Confirm</span><span class="sxs-lookup"><span data-stu-id="f06f0-141">-Confirm</span></span>

<span data-ttu-id="f06f0-142">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="f06f0-142">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="f06f0-143">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="f06f0-143">-WhatIf</span></span>

<span data-ttu-id="f06f0-144">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="f06f0-144">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="f06f0-145">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="f06f0-145">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="f06f0-146">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="f06f0-146">CommonParameters</span></span>

<span data-ttu-id="f06f0-147">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f06f0-147">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f06f0-148">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="f06f0-148">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="f06f0-149">Входные данные</span><span class="sxs-lookup"><span data-stu-id="f06f0-149">INPUTS</span></span>

### <span data-ttu-id="f06f0-150">System.Management.Automation.PSDРивеинфо</span><span class="sxs-lookup"><span data-stu-id="f06f0-150">System.Management.Automation.PSDriveInfo</span></span>

<span data-ttu-id="f06f0-151">Вы можете передать в командлет объект Drive, например один из `Get-PSDrive` командлетов `Remove-PSDrive` .</span><span class="sxs-lookup"><span data-stu-id="f06f0-151">You can pipe a drive object, such as one from the `Get-PSDrive` cmdlet, to the `Remove-PSDrive` cmdlet.</span></span>

## <span data-ttu-id="f06f0-152">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="f06f0-152">OUTPUTS</span></span>

### <span data-ttu-id="f06f0-153">None</span><span class="sxs-lookup"><span data-stu-id="f06f0-153">None</span></span>

<span data-ttu-id="f06f0-154">Этот командлет не возвращает никакие выходные данные.</span><span class="sxs-lookup"><span data-stu-id="f06f0-154">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="f06f0-155">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="f06f0-155">NOTES</span></span>

- <span data-ttu-id="f06f0-156">`Remove-PSDrive`Командлет предназначен для работы с данными, предоставляемыми любым поставщиком PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f06f0-156">The `Remove-PSDrive` cmdlet is designed to work with the data exposed by any PowerShell provider.</span></span> <span data-ttu-id="f06f0-157">Чтобы получить список поставщиков в сеансе, используйте `Get-PSProvider` командлет.</span><span class="sxs-lookup"><span data-stu-id="f06f0-157">To list the providers in your session, use the `Get-PSProvider` cmdlet.</span></span> <span data-ttu-id="f06f0-158">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="f06f0-158">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="f06f0-159">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="f06f0-159">RELATED LINKS</span></span>

[<span data-ttu-id="f06f0-160">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="f06f0-160">Get-PSDrive</span></span>](Get-PSDrive.md)

[<span data-ttu-id="f06f0-161">New-PSDrive</span><span class="sxs-lookup"><span data-stu-id="f06f0-161">New-PSDrive</span></span>](New-PSDrive.md)

[<span data-ttu-id="f06f0-162">about_Providers</span><span class="sxs-lookup"><span data-stu-id="f06f0-162">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

