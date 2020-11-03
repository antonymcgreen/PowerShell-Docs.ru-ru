---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-psdrive?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSDrive
ms.openlocfilehash: 4b9b466be3d52877056b948e4cc373991784416a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227934"
---
# <span data-ttu-id="f04a1-103">Remove-PSDrive</span><span class="sxs-lookup"><span data-stu-id="f04a1-103">Remove-PSDrive</span></span>

## <span data-ttu-id="f04a1-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="f04a1-104">SYNOPSIS</span></span>
<span data-ttu-id="f04a1-105">Удаляет временные диски PowerShell и отключает сопоставленные сетевые диски.</span><span class="sxs-lookup"><span data-stu-id="f04a1-105">Deletes temporary PowerShell drives and disconnects mapped network drives.</span></span>

## <span data-ttu-id="f04a1-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f04a1-106">SYNTAX</span></span>

### <span data-ttu-id="f04a1-107">Имя (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="f04a1-107">Name (Default)</span></span>

```
Remove-PSDrive [-Name] <String[]> [-PSProvider <String[]>] [-Scope <String>] [-Force] [-WhatIf] [-Confirm]
 [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="f04a1-108">литералнаме</span><span class="sxs-lookup"><span data-stu-id="f04a1-108">LiteralName</span></span>

```
Remove-PSDrive [-LiteralName] <String[]> [-PSProvider <String[]>] [-Scope <String>] [-Force] [-WhatIf]
 [-Confirm] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="f04a1-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f04a1-109">DESCRIPTION</span></span>

<span data-ttu-id="f04a1-110">`Remove-PSDrive`Командлет удаляет временные диски PowerShell, созданные с помощью `New-PSDrive` командлета.</span><span class="sxs-lookup"><span data-stu-id="f04a1-110">The `Remove-PSDrive` cmdlet deletes temporary PowerShell drives that were created by using the `New-PSDrive` cmdlet.</span></span>

<span data-ttu-id="f04a1-111">Начиная с Windows PowerShell 3,0, `Remove-PSDrive` также отключает подключенные сетевые диски, включая, но не ограниченные, дисками, созданными с помощью `Persist` параметра `New-PSDrive` .</span><span class="sxs-lookup"><span data-stu-id="f04a1-111">Beginning in Windows PowerShell 3.0, `Remove-PSDrive` also disconnects mapped network drives, including, but not limited to, drives created by using the `Persist` parameter of `New-PSDrive`.</span></span>

<span data-ttu-id="f04a1-112">`Remove-PSDrive` невозможно удалить физические или логические диски Windows.</span><span class="sxs-lookup"><span data-stu-id="f04a1-112">`Remove-PSDrive` cannot delete Windows physical or logical drives.</span></span>

<span data-ttu-id="f04a1-113">Начиная с Windows PowerShell 3,0, когда к компьютеру подключен внешний диск, PowerShell автоматически добавляет PSDrive в файловую систему, представляющую новый диск.</span><span class="sxs-lookup"><span data-stu-id="f04a1-113">Beginning in Windows PowerShell 3.0, when an external drive is connected to the computer, PowerShell automatically adds a PSDrive to the file system that represents the new drive.</span></span>
<span data-ttu-id="f04a1-114">Перезапускать PowerShell не требуется.</span><span class="sxs-lookup"><span data-stu-id="f04a1-114">You do not need to restart PowerShell.</span></span>
<span data-ttu-id="f04a1-115">Аналогично, когда внешний диск отключается от компьютера, PowerShell автоматически удаляет PSDrive, представляющий удаленный диск.</span><span class="sxs-lookup"><span data-stu-id="f04a1-115">Similarly, when an external drive is disconnected from the computer, PowerShell automatically deletes the PSDrive that represents the removed drive.</span></span>

## <span data-ttu-id="f04a1-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="f04a1-116">EXAMPLES</span></span>

### <span data-ttu-id="f04a1-117">Пример 1. Удаление диска файловой системы</span><span class="sxs-lookup"><span data-stu-id="f04a1-117">Example 1: Remove a file system drive</span></span>

<span data-ttu-id="f04a1-118">Эта команда удаляет временный диск файловой системы с именем smp.</span><span class="sxs-lookup"><span data-stu-id="f04a1-118">This command removes a temporary file system drive named "smp".</span></span>

```powershell
Remove-PSDrive -Name smp
```

### <span data-ttu-id="f04a1-119">Пример 2. удаление сопоставленных сетевых дисков</span><span class="sxs-lookup"><span data-stu-id="f04a1-119">Example 2: Remove mapped network drives</span></span>

<span data-ttu-id="f04a1-120">Эта команда использует `Remove-PSDrive` для отключения подключенных сетевых дисков X: и S:.</span><span class="sxs-lookup"><span data-stu-id="f04a1-120">This command uses `Remove-PSDrive` to disconnect the X: and S: mapped network drives.</span></span>

```powershell
Get-PSDrive X, S | Remove-PSDrive
```

## <span data-ttu-id="f04a1-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f04a1-121">PARAMETERS</span></span>

### <span data-ttu-id="f04a1-122">-Force</span><span class="sxs-lookup"><span data-stu-id="f04a1-122">-Force</span></span>

<span data-ttu-id="f04a1-123">Удаляет текущий диск PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f04a1-123">Removes the current PowerShell drive.</span></span>

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

### <span data-ttu-id="f04a1-124">-Литералнаме</span><span class="sxs-lookup"><span data-stu-id="f04a1-124">-LiteralName</span></span>

<span data-ttu-id="f04a1-125">Задает имя диска.</span><span class="sxs-lookup"><span data-stu-id="f04a1-125">Specifies the name of the drive.</span></span>

<span data-ttu-id="f04a1-126">Значение параметра **LiteralName** используется именно так, как оно введено.</span><span class="sxs-lookup"><span data-stu-id="f04a1-126">The value of **LiteralName** is used exactly as typed.</span></span>
<span data-ttu-id="f04a1-127">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="f04a1-127">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="f04a1-128">Если в имени есть escape-символы, заключите их в одиночные кавычки (').</span><span class="sxs-lookup"><span data-stu-id="f04a1-128">If the name includes escape characters, enclose it in single quotation marks (').</span></span>
<span data-ttu-id="f04a1-129">Одинарные кавычки предписывает PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="f04a1-129">Single quotation marks instruct PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="f04a1-130">-Name</span><span class="sxs-lookup"><span data-stu-id="f04a1-130">-Name</span></span>

<span data-ttu-id="f04a1-131">Указывает имена дисков, которые нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="f04a1-131">Specifies the names of the drives to remove.</span></span>
<span data-ttu-id="f04a1-132">Не ставьте двоеточие (:) после имени диска.</span><span class="sxs-lookup"><span data-stu-id="f04a1-132">Do not type a colon (:) after the drive name.</span></span>

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

### <span data-ttu-id="f04a1-133">-PSProvider</span><span class="sxs-lookup"><span data-stu-id="f04a1-133">-PSProvider</span></span>

<span data-ttu-id="f04a1-134">Указывает массив объектов **psprovider** .</span><span class="sxs-lookup"><span data-stu-id="f04a1-134">Specifies an array of **PSProvider** objects.</span></span>
<span data-ttu-id="f04a1-135">Этот командлет удаляет и отключает все диски, связанные с указанным поставщиком PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f04a1-135">This cmdlet removes and disconnects all of the drives associated with the specified PowerShell provider.</span></span>

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

### <span data-ttu-id="f04a1-136">-Scope</span><span class="sxs-lookup"><span data-stu-id="f04a1-136">-Scope</span></span>

<span data-ttu-id="f04a1-137">Указывает область для диска.</span><span class="sxs-lookup"><span data-stu-id="f04a1-137">Specifies a scope for the drive.</span></span>
<span data-ttu-id="f04a1-138">Допустимые значения для этого параметра: Global, Local и script или Number, относящихся к текущей области.</span><span class="sxs-lookup"><span data-stu-id="f04a1-138">The acceptable values for this parameter are: Global, Local, and Script, or a number relative to the current scope.</span></span> <span data-ttu-id="f04a1-139">Области с номером 0 по числу областей.</span><span class="sxs-lookup"><span data-stu-id="f04a1-139">Scopes number 0 through the number of scopes.</span></span> <span data-ttu-id="f04a1-140">Текущий номер области равен 0, а его родительский элемент — 1.</span><span class="sxs-lookup"><span data-stu-id="f04a1-140">The current scope number is 0 and its parent is 1.</span></span>
<span data-ttu-id="f04a1-141">Дополнительные сведения см. в разделе [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="f04a1-141">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

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

### <span data-ttu-id="f04a1-142">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="f04a1-142">-UseTransaction</span></span>

<span data-ttu-id="f04a1-143">Включает команду в активную транзакцию.</span><span class="sxs-lookup"><span data-stu-id="f04a1-143">Includes the command in the active transaction.</span></span>
<span data-ttu-id="f04a1-144">Этот параметр доступен только при выполнении транзакции.</span><span class="sxs-lookup"><span data-stu-id="f04a1-144">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="f04a1-145">Дополнительные сведения см. в разделе about_Transactions.</span><span class="sxs-lookup"><span data-stu-id="f04a1-145">For more information, see about_Transactions.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f04a1-146">-Confirm</span><span class="sxs-lookup"><span data-stu-id="f04a1-146">-Confirm</span></span>

<span data-ttu-id="f04a1-147">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="f04a1-147">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="f04a1-148">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="f04a1-148">-WhatIf</span></span>

<span data-ttu-id="f04a1-149">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="f04a1-149">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="f04a1-150">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="f04a1-150">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="f04a1-151">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="f04a1-151">CommonParameters</span></span>

<span data-ttu-id="f04a1-152">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f04a1-152">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f04a1-153">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="f04a1-153">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="f04a1-154">Входные данные</span><span class="sxs-lookup"><span data-stu-id="f04a1-154">INPUTS</span></span>

### <span data-ttu-id="f04a1-155">System.Management.Automation.PSDРивеинфо</span><span class="sxs-lookup"><span data-stu-id="f04a1-155">System.Management.Automation.PSDriveInfo</span></span>

<span data-ttu-id="f04a1-156">Вы можете передать в командлет объект Drive, например один из `Get-PSDrive` командлетов `Remove-PSDrive` .</span><span class="sxs-lookup"><span data-stu-id="f04a1-156">You can pipe a drive object, such as one from the `Get-PSDrive` cmdlet, to the `Remove-PSDrive` cmdlet.</span></span>

## <span data-ttu-id="f04a1-157">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="f04a1-157">OUTPUTS</span></span>

### <span data-ttu-id="f04a1-158">Нет</span><span class="sxs-lookup"><span data-stu-id="f04a1-158">None</span></span>

<span data-ttu-id="f04a1-159">Этот командлет не возвращает никакие выходные данные.</span><span class="sxs-lookup"><span data-stu-id="f04a1-159">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="f04a1-160">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="f04a1-160">NOTES</span></span>

- <span data-ttu-id="f04a1-161">`Remove-PSDrive`Командлет предназначен для работы с данными, предоставляемыми любым поставщиком PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f04a1-161">The `Remove-PSDrive` cmdlet is designed to work with the data exposed by any PowerShell provider.</span></span> <span data-ttu-id="f04a1-162">Чтобы получить список поставщиков в сеансе, используйте `Get-PSProvider` командлет.</span><span class="sxs-lookup"><span data-stu-id="f04a1-162">To list the providers in your session, use the `Get-PSProvider` cmdlet.</span></span> <span data-ttu-id="f04a1-163">Дополнительные сведения см. в разделе [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="f04a1-163">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="f04a1-164">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="f04a1-164">RELATED LINKS</span></span>

[<span data-ttu-id="f04a1-165">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="f04a1-165">Get-PSDrive</span></span>](Get-PSDrive.md)

[<span data-ttu-id="f04a1-166">New-PSDrive</span><span class="sxs-lookup"><span data-stu-id="f04a1-166">New-PSDrive</span></span>](New-PSDrive.md)

[<span data-ttu-id="f04a1-167">about_Providers</span><span class="sxs-lookup"><span data-stu-id="f04a1-167">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
