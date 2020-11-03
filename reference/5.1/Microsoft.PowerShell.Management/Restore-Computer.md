---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restore-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Restore-Computer
ms.openlocfilehash: 824e9a24693c7a7de01358a048a0df55be333263
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227902"
---
# <span data-ttu-id="3b7a0-103">Restore-Computer</span><span class="sxs-lookup"><span data-stu-id="3b7a0-103">Restore-Computer</span></span>

## <span data-ttu-id="3b7a0-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="3b7a0-104">SYNOPSIS</span></span>
<span data-ttu-id="3b7a0-105">Запускает восстановление системы на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3b7a0-105">Starts a system restore on the local computer.</span></span>

## <span data-ttu-id="3b7a0-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3b7a0-106">SYNTAX</span></span>

```
Restore-Computer [-RestorePoint] <Int32> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="3b7a0-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3b7a0-107">DESCRIPTION</span></span>
<span data-ttu-id="3b7a0-108">Командлет **Restore-Computer** восстанавливает локальный компьютер до указанной точки восстановления системы.</span><span class="sxs-lookup"><span data-stu-id="3b7a0-108">The **Restore-Computer** cmdlet restores the local computer to the specified system restore point.</span></span>

<span data-ttu-id="3b7a0-109">**Restart-Computer** перезагружает компьютер.</span><span class="sxs-lookup"><span data-stu-id="3b7a0-109">**Restore-Computer** restarts the computer.</span></span>
<span data-ttu-id="3b7a0-110">Восстановление завершается при выполнении перезагрузки.</span><span class="sxs-lookup"><span data-stu-id="3b7a0-110">The restore is completed during the restart operation.</span></span>

<span data-ttu-id="3b7a0-111">Точки восстановления системы и **Восстановление компьютера** поддерживаются только в клиентских операционных системах, таких как Windows 7, Windows Vista и Windows XP.</span><span class="sxs-lookup"><span data-stu-id="3b7a0-111">System restore points and **Restore-Computer** are supported only on client operating systems, such as Windows 7, Windows Vista, and Windows XP.</span></span>

## <span data-ttu-id="3b7a0-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="3b7a0-112">EXAMPLES</span></span>

### <span data-ttu-id="3b7a0-113">Пример 1. Восстановление локального компьютера</span><span class="sxs-lookup"><span data-stu-id="3b7a0-113">Example 1: Restore the local computer</span></span>

```
PS C:\> Restore-Computer -RestorePoint 253
```

<span data-ttu-id="3b7a0-114">Эта команда восстанавливает локальный компьютер в точке восстановления с порядковым номером 253.</span><span class="sxs-lookup"><span data-stu-id="3b7a0-114">This command restores the local computer to the restore point that has sequence number 253.</span></span>

### <span data-ttu-id="3b7a0-115">Пример 2. Восстановление локального компьютера с подтверждением</span><span class="sxs-lookup"><span data-stu-id="3b7a0-115">Example 2: Restore the local computer with confirmation</span></span>

```
PS C:\> Restore-Computer -RestorePoint 255 -Confirm
Confirm
Are you sure you want to perform this action?
Performing operation "Restore-Computer" .
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="3b7a0-116">Эта команда восстанавливает локальный компьютер в точке восстановления с порядковым номером 255.</span><span class="sxs-lookup"><span data-stu-id="3b7a0-116">This command restores the local computer to the restore point that has sequence number 255.</span></span>
<span data-ttu-id="3b7a0-117">Он использует параметр *Confirm* для запроса пользователя перед фактическим выполнением операции.</span><span class="sxs-lookup"><span data-stu-id="3b7a0-117">It uses the *Confirm* parameter to prompt the user before actually performing the operation.</span></span>

### <span data-ttu-id="3b7a0-118">Пример 3. Восстановление компьютера и проверка состояния</span><span class="sxs-lookup"><span data-stu-id="3b7a0-118">Example 3: Restore a computer and check the status</span></span>

```
PS C:\> Get-ComputerRestorePoint
PS C:\> Restore-Computer -RestorePoint 255
PS C:\> Get-ComputerRestorePoint -LastStatus
```

<span data-ttu-id="3b7a0-119">Эти команды выполняют восстановление системы и затем проверяют его результат.</span><span class="sxs-lookup"><span data-stu-id="3b7a0-119">These commands run a system restore and then check its status.</span></span>

<span data-ttu-id="3b7a0-120">Первая команда использует **Get-ComputerRestorePoint** для получения точек восстановления на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="3b7a0-120">The first command uses **Get-ComputerRestorePoint** to get the restore points on the local computer.</span></span>

<span data-ttu-id="3b7a0-121">Вторая команда восстанавливает компьютер до точки восстановления с порядковым номером 255.</span><span class="sxs-lookup"><span data-stu-id="3b7a0-121">The second command restores the computer to the restore point with sequence number 255.</span></span>

<span data-ttu-id="3b7a0-122">Третья команда использует параметр *LastStatus* командлета *Get-ComputerRestorePoint* для проверки состояния операции восстановления.</span><span class="sxs-lookup"><span data-stu-id="3b7a0-122">The third command uses the *LastStatus* parameter of *Get-ComputerRestorePoint* cmdlet to check the status of the restore operation.</span></span>
<span data-ttu-id="3b7a0-123">Так как **Restart-Computer** принудительно перезапускается, эта команда будет выполнена после перезагрузки компьютера.</span><span class="sxs-lookup"><span data-stu-id="3b7a0-123">Because **Restore-Computer** forces a restart, this command would be entered after the computer restarts.</span></span>

## <span data-ttu-id="3b7a0-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3b7a0-124">PARAMETERS</span></span>

### <span data-ttu-id="3b7a0-125">-Ресторепоинт</span><span class="sxs-lookup"><span data-stu-id="3b7a0-125">-RestorePoint</span></span>
<span data-ttu-id="3b7a0-126">Задает порядковый номер точки восстановления.</span><span class="sxs-lookup"><span data-stu-id="3b7a0-126">Specifies the sequence number of the restore point.</span></span>
<span data-ttu-id="3b7a0-127">Чтобы найти порядковый номер, используйте командлет Get-ComputerRestorePoint.</span><span class="sxs-lookup"><span data-stu-id="3b7a0-127">To find the sequence number, use the Get-ComputerRestorePoint cmdlet.</span></span>
<span data-ttu-id="3b7a0-128">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="3b7a0-128">This parameter is required.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: SequenceNumber, SN, RP

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3b7a0-129">-Confirm</span><span class="sxs-lookup"><span data-stu-id="3b7a0-129">-Confirm</span></span>
<span data-ttu-id="3b7a0-130">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="3b7a0-130">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="3b7a0-131">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="3b7a0-131">-WhatIf</span></span>
<span data-ttu-id="3b7a0-132">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="3b7a0-132">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="3b7a0-133">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="3b7a0-133">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="3b7a0-134">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="3b7a0-134">CommonParameters</span></span>
<span data-ttu-id="3b7a0-135">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3b7a0-135">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3b7a0-136">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3b7a0-136">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3b7a0-137">Входные данные</span><span class="sxs-lookup"><span data-stu-id="3b7a0-137">INPUTS</span></span>

### <span data-ttu-id="3b7a0-138">Нет</span><span class="sxs-lookup"><span data-stu-id="3b7a0-138">None</span></span>
<span data-ttu-id="3b7a0-139">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="3b7a0-139">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="3b7a0-140">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="3b7a0-140">OUTPUTS</span></span>

### <span data-ttu-id="3b7a0-141">Нет</span><span class="sxs-lookup"><span data-stu-id="3b7a0-141">None</span></span>
<span data-ttu-id="3b7a0-142">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="3b7a0-142">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="3b7a0-143">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="3b7a0-143">NOTES</span></span>

* <span data-ttu-id="3b7a0-144">Чтобы выполнить команду Restore-Computer в Windows Vista и более поздних версиях операционной системы Windows, откройте Windows PowerShell с помощью команды Запуск от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="3b7a0-144">To run a Restore-Computer command on Windows Vista and later versions of the Windows operating system, open Windows PowerShell by using the Run as administrator option.</span></span>
* <span data-ttu-id="3b7a0-145">Этот командлет использует класс инструментарий управления Windows (WMI) (WMI) **SystemRestore** .</span><span class="sxs-lookup"><span data-stu-id="3b7a0-145">This cmdlet uses the Windows Management Instrumentation (WMI) **SystemRestore** class.</span></span>

## <span data-ttu-id="3b7a0-146">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="3b7a0-146">RELATED LINKS</span></span>

[<span data-ttu-id="3b7a0-147">Checkpoint-Computer</span><span class="sxs-lookup"><span data-stu-id="3b7a0-147">Checkpoint-Computer</span></span>](Checkpoint-Computer.md)

[<span data-ttu-id="3b7a0-148">Disable-ComputerRestore</span><span class="sxs-lookup"><span data-stu-id="3b7a0-148">Disable-ComputerRestore</span></span>](Disable-ComputerRestore.md)

[<span data-ttu-id="3b7a0-149">Enable-ComputerRestore</span><span class="sxs-lookup"><span data-stu-id="3b7a0-149">Enable-ComputerRestore</span></span>](Enable-ComputerRestore.md)

[<span data-ttu-id="3b7a0-150">Get-ComputerRestorePoint</span><span class="sxs-lookup"><span data-stu-id="3b7a0-150">Get-ComputerRestorePoint</span></span>](Get-ComputerRestorePoint.md)

[<span data-ttu-id="3b7a0-151">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="3b7a0-151">Restart-Computer</span></span>](Restart-Computer.md)
