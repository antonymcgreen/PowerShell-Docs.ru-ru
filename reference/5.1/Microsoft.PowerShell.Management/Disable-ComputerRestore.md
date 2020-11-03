---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/disable-computerrestore?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-ComputerRestore
ms.openlocfilehash: 941829c3caa0f6bb2f5712dda9eb7d8c36908062
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228413"
---
# <span data-ttu-id="42a49-103">Disable-ComputerRestore</span><span class="sxs-lookup"><span data-stu-id="42a49-103">Disable-ComputerRestore</span></span>

## <span data-ttu-id="42a49-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="42a49-104">SYNOPSIS</span></span>
<span data-ttu-id="42a49-105">Отключает функцию восстановления системы на указанном диске файловой системы.</span><span class="sxs-lookup"><span data-stu-id="42a49-105">Disables the System Restore feature on the specified file system drive.</span></span>

## <span data-ttu-id="42a49-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="42a49-106">SYNTAX</span></span>

```
Disable-ComputerRestore [-Drive] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="42a49-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="42a49-107">DESCRIPTION</span></span>
<span data-ttu-id="42a49-108">Командлет **Disable-ComputerRestore** отключает функцию восстановления системы на одном или нескольких дисках файловой системы.</span><span class="sxs-lookup"><span data-stu-id="42a49-108">The **Disable-ComputerRestore** cmdlet turns off the System Restore feature on one or more file system drives.</span></span>
<span data-ttu-id="42a49-109">В результате попытки восстановить компьютер не затрагивают указанный диск.</span><span class="sxs-lookup"><span data-stu-id="42a49-109">As a result, attempts to restore the computer do not affect the specified drive.</span></span>

<span data-ttu-id="42a49-110">Чтобы отключить функцию восстановления системы на любом диске, ее необходимо отключить на системном диске либо предварительно, либо одновременно.</span><span class="sxs-lookup"><span data-stu-id="42a49-110">To disable System Restore on any drive, it must be disabled on the system drive, either first or concurrently.</span></span>

<span data-ttu-id="42a49-111">Чтобы повторно включить восстановление системы, используйте командлет Enable-ComputerRestore.</span><span class="sxs-lookup"><span data-stu-id="42a49-111">To re-enable System Restore, use the Enable-ComputerRestore cmdlet.</span></span>
<span data-ttu-id="42a49-112">Чтобы определить состояние функции восстановления системы для каждого диска, используйте программу Rstrui.exe.</span><span class="sxs-lookup"><span data-stu-id="42a49-112">To find the state of System Restore for each drive, use Rstrui.exe.</span></span>

<span data-ttu-id="42a49-113">Точки восстановления системы и командлеты ComputerRestore поддерживаются только в клиентских операционных системах. таких как Windows 7, Windows Vista и Windows XP.</span><span class="sxs-lookup"><span data-stu-id="42a49-113">System restore points and the ComputerRestore cmdlets are supported only on client operating systems, such as Windows 7, Windows Vista, and Windows XP.</span></span>

## <span data-ttu-id="42a49-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="42a49-114">EXAMPLES</span></span>

### <span data-ttu-id="42a49-115">Пример 1. Отключение восстановления системы на указанном диске</span><span class="sxs-lookup"><span data-stu-id="42a49-115">Example 1: Disable System Restore on the specified drive</span></span>

```
PS C:\> Disable-ComputerRestore -Drive "C:\"
```

<span data-ttu-id="42a49-116">Эта команда отключает восстановление системы на диске C:.</span><span class="sxs-lookup"><span data-stu-id="42a49-116">This command disables System Restore on the C: drive.</span></span>

### <span data-ttu-id="42a49-117">Пример 2. Отключение восстановления системы на нескольких дисках</span><span class="sxs-lookup"><span data-stu-id="42a49-117">Example 2: Disable System Restore on multiple drives</span></span>

```
PS C:\> Disable-ComputerRestore "C:\", "D:\"
```

<span data-ttu-id="42a49-118">Эта команда отключает восстановление системы на дисках C: и D:.</span><span class="sxs-lookup"><span data-stu-id="42a49-118">This command disables System Restore on the C: and D: drives.</span></span>
<span data-ttu-id="42a49-119">В команде используется параметр *Drive* , но имя параметра диска опускается.</span><span class="sxs-lookup"><span data-stu-id="42a49-119">The command uses the *Drive* parameter, but it omits the Drive parameter name.</span></span>

## <span data-ttu-id="42a49-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="42a49-120">PARAMETERS</span></span>

### <span data-ttu-id="42a49-121">-Диск</span><span class="sxs-lookup"><span data-stu-id="42a49-121">-Drive</span></span>
<span data-ttu-id="42a49-122">Определяет диски файловой системы.</span><span class="sxs-lookup"><span data-stu-id="42a49-122">Specifies the file system drives.</span></span>
<span data-ttu-id="42a49-123">Введите одну или несколько букв диска файловой системы, а затем двоеточие и обратную косую черту, а также заключите их в кавычки, например C:\. или Д:\.</span><span class="sxs-lookup"><span data-stu-id="42a49-123">Enter one or more file system drive letters, each followed by a colon and a backslash and enclosed in quotation marks, such as C:\ or D:\.</span></span>
<span data-ttu-id="42a49-124">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="42a49-124">This parameter is required.</span></span>

<span data-ttu-id="42a49-125">С помощью командлета нельзя отключить восстановление системы на удаленном сетевом диске, даже если он сопоставлен с локальным компьютером, и на дисках, на которых использование восстановления системы невозможно, например на внешних дисках.</span><span class="sxs-lookup"><span data-stu-id="42a49-125">You cannot use this cmdlet to disable System Restore on a remote network drive, even if the drive is mapped to the local computer, and you cannot disable System Restore on drives that are not eligible for System Restore, such as external drives.</span></span>

<span data-ttu-id="42a49-126">Чтобы отключить функцию восстановления системы на любом диске, ее необходимо отключить на системном диске либо предварительно, либо одновременно.</span><span class="sxs-lookup"><span data-stu-id="42a49-126">To disable System Restore on any drive, System Restore must be disabled on the system drive, either before or concurrently.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="42a49-127">-Confirm</span><span class="sxs-lookup"><span data-stu-id="42a49-127">-Confirm</span></span>
<span data-ttu-id="42a49-128">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="42a49-128">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="42a49-129">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="42a49-129">-WhatIf</span></span>
<span data-ttu-id="42a49-130">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="42a49-130">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="42a49-131">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="42a49-131">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="42a49-132">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="42a49-132">CommonParameters</span></span>
<span data-ttu-id="42a49-133">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="42a49-133">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="42a49-134">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="42a49-134">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="42a49-135">Входные данные</span><span class="sxs-lookup"><span data-stu-id="42a49-135">INPUTS</span></span>

### <span data-ttu-id="42a49-136">Нет</span><span class="sxs-lookup"><span data-stu-id="42a49-136">None</span></span>
<span data-ttu-id="42a49-137">В этот командлет нельзя передать входные данные.</span><span class="sxs-lookup"><span data-stu-id="42a49-137">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="42a49-138">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="42a49-138">OUTPUTS</span></span>

### <span data-ttu-id="42a49-139">Нет</span><span class="sxs-lookup"><span data-stu-id="42a49-139">None</span></span>
<span data-ttu-id="42a49-140">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="42a49-140">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="42a49-141">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="42a49-141">NOTES</span></span>

* <span data-ttu-id="42a49-142">Чтобы запустить этот командлет в Windows Vista и более поздних версиях Windows, откройте Windows PowerShell с параметром Запуск от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="42a49-142">To run this cmdlet on Windows Vista and later versions of Windows, open Windows PowerShell with the Run as administrator option.</span></span>

  <span data-ttu-id="42a49-143">Чтобы найти диски файловой системы, подходящие для восстановления системы, в разделе "система" панели управления перейдите на вкладку "Защита системы". Чтобы открыть эту вкладку в Windows PowerShell, введите `SystemPropertiesProtection` .</span><span class="sxs-lookup"><span data-stu-id="42a49-143">To find the file system drives that are eligible for system restore, in System in Control Panel, see the System Protection tab. To open this tab in Windows PowerShell, type `SystemPropertiesProtection`.</span></span>

  <span data-ttu-id="42a49-144">Этот командлет использует класс инструментарий управления Windows (WMI) (WMI) **SystemRestore** .</span><span class="sxs-lookup"><span data-stu-id="42a49-144">This cmdlet uses the Windows Management Instrumentation (WMI) **SystemRestore** class.</span></span>

*

## <span data-ttu-id="42a49-145">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="42a49-145">RELATED LINKS</span></span>

[<span data-ttu-id="42a49-146">Checkpoint-Computer</span><span class="sxs-lookup"><span data-stu-id="42a49-146">Checkpoint-Computer</span></span>](Checkpoint-Computer.md)

[<span data-ttu-id="42a49-147">Enable-ComputerRestore</span><span class="sxs-lookup"><span data-stu-id="42a49-147">Enable-ComputerRestore</span></span>](Enable-ComputerRestore.md)

[<span data-ttu-id="42a49-148">Get-ComputerRestorePoint</span><span class="sxs-lookup"><span data-stu-id="42a49-148">Get-ComputerRestorePoint</span></span>](Get-ComputerRestorePoint.md)

[<span data-ttu-id="42a49-149">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="42a49-149">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="42a49-150">Restore-Computer</span><span class="sxs-lookup"><span data-stu-id="42a49-150">Restore-Computer</span></span>](Restore-Computer.md)
