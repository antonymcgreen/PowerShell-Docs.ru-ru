---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/enable-computerrestore?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-ComputerRestore
ms.openlocfilehash: f9616a7f9af4dd2fa45e150bb64eef65427b4947
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228410"
---
# <span data-ttu-id="bfa21-103">Enable-ComputerRestore</span><span class="sxs-lookup"><span data-stu-id="bfa21-103">Enable-ComputerRestore</span></span>

## <span data-ttu-id="bfa21-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="bfa21-104">SYNOPSIS</span></span>
<span data-ttu-id="bfa21-105">Включает функцию восстановления на указанном диске файловой системы.</span><span class="sxs-lookup"><span data-stu-id="bfa21-105">Enables the System Restore feature on the specified file system drive.</span></span>

## <span data-ttu-id="bfa21-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bfa21-106">SYNTAX</span></span>

```
Enable-ComputerRestore [-Drive] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="bfa21-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bfa21-107">DESCRIPTION</span></span>
<span data-ttu-id="bfa21-108">Командлет **Enable-ComputerRestore** включает функцию восстановления системы на одном или нескольких дисках файловой системы.</span><span class="sxs-lookup"><span data-stu-id="bfa21-108">The **Enable-ComputerRestore** cmdlet turns on the System Restore feature on one or more file system drives.</span></span>
<span data-ttu-id="bfa21-109">В результате такие средства как командлет Restore-Computer можно использовать для восстановления компьютера в предыдущее состояние.</span><span class="sxs-lookup"><span data-stu-id="bfa21-109">As a result, you can use tools, such as the Restore-Computer cmdlet, to restore the computer to a previous state.</span></span>

<span data-ttu-id="bfa21-110">По умолчанию функция восстановления системы включена на всех соответствующих дисках, но ее можно отключить, например, с помощью командлета Disable-ComputerRestore.</span><span class="sxs-lookup"><span data-stu-id="bfa21-110">By default, System Restore is enabled on all eligible drives, but you can disable it, such as by using the Disable-ComputerRestore cmdlet.</span></span>
<span data-ttu-id="bfa21-111">Чтобы включить (или повторно включить) функцию восстановления системы на каком-либо диске, ее необходимо включить на системном диске (предварительно или одновременно).</span><span class="sxs-lookup"><span data-stu-id="bfa21-111">To enable (or re-enable) System Restore on any drive, it must be enabled on the system drive, either first or concurrently.</span></span>
<span data-ttu-id="bfa21-112">Чтобы определить состояние функции восстановления системы для каждого диска, используйте программу Rstrui.exe.</span><span class="sxs-lookup"><span data-stu-id="bfa21-112">To find the state of System Restore for each drive, use Rstrui.exe.</span></span>

<span data-ttu-id="bfa21-113">Точки восстановления системы и командлеты ComputerRestore поддерживаются только в клиентских операционных системах. таких как Windows 7, Windows Vista и Windows XP.</span><span class="sxs-lookup"><span data-stu-id="bfa21-113">System restore points and the ComputerRestore cmdlets are supported only on client operating systems, such as Windows 7, Windows Vista, and Windows XP.</span></span>

## <span data-ttu-id="bfa21-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="bfa21-114">EXAMPLES</span></span>

### <span data-ttu-id="bfa21-115">Пример 1. Включение восстановления системы на указанном диске</span><span class="sxs-lookup"><span data-stu-id="bfa21-115">Example 1: Enable System Restore on the specified drive</span></span>

```
PS C:\> Enable-ComputerRestore -Drive "C:\"
```

<span data-ttu-id="bfa21-116">Эта команда включает восстановление системы на диске C: локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="bfa21-116">This command enables System Restore on the C: drive of the local computer.</span></span>

### <span data-ttu-id="bfa21-117">Пример 2. Включение восстановления системы на нескольких дисках</span><span class="sxs-lookup"><span data-stu-id="bfa21-117">Example 2: Enable System Restore on multiple drives</span></span>

```
PS C:\> Enable-ComputerRestore -Drive "C:\", "D:\"
```

<span data-ttu-id="bfa21-118">Эта команда включает восстановление системы на дисках C: и D: локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="bfa21-118">This command enables System Restore on the C: and D: drives of the local computer.</span></span>

## <span data-ttu-id="bfa21-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bfa21-119">PARAMETERS</span></span>

### <span data-ttu-id="bfa21-120">-Диск</span><span class="sxs-lookup"><span data-stu-id="bfa21-120">-Drive</span></span>
<span data-ttu-id="bfa21-121">Определяет диски файловой системы.</span><span class="sxs-lookup"><span data-stu-id="bfa21-121">Specifies the file system drives.</span></span>
<span data-ttu-id="bfa21-122">Введите одну или несколько букв диска файловой системы, а затем двоеточие и обратную косую черту, а также заключите их в кавычки, например C:\. или Д:\.</span><span class="sxs-lookup"><span data-stu-id="bfa21-122">Enter one or more file system drive letters, each followed by a colon and a backslash and enclosed in quotation marks, such as C:\ or D:\.</span></span>
<span data-ttu-id="bfa21-123">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="bfa21-123">This parameter is required.</span></span>

<span data-ttu-id="bfa21-124">С помощью этого командлета нельзя включить функцию восстановления системы на удаленном сетевом диске, даже если он подключен к локальному компьютеру, а также на дисках, не подходящих для ее использования, например, на внешних дисках.</span><span class="sxs-lookup"><span data-stu-id="bfa21-124">You cannot use this cmdlet to enable System Restore on a remote network drive, even if the drive is mapped to the local computer, and you cannot enable System Restore on drives that are not eligible for System Restore, such as external drives.</span></span>

<span data-ttu-id="bfa21-125">Чтобы включить функцию восстановления системы на каком-либо диске, ее необходимо включить на системном диске (предварительно или одновременно).</span><span class="sxs-lookup"><span data-stu-id="bfa21-125">To enable System Restore on any drive, System Restore must be enabled on the system drive, either before or concurrently.</span></span>

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

### <span data-ttu-id="bfa21-126">-Confirm</span><span class="sxs-lookup"><span data-stu-id="bfa21-126">-Confirm</span></span>
<span data-ttu-id="bfa21-127">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="bfa21-127">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="bfa21-128">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="bfa21-128">-WhatIf</span></span>
<span data-ttu-id="bfa21-129">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="bfa21-129">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="bfa21-130">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="bfa21-130">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="bfa21-131">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="bfa21-131">CommonParameters</span></span>
<span data-ttu-id="bfa21-132">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="bfa21-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bfa21-133">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="bfa21-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="bfa21-134">Входные данные</span><span class="sxs-lookup"><span data-stu-id="bfa21-134">INPUTS</span></span>

### <span data-ttu-id="bfa21-135">Нет</span><span class="sxs-lookup"><span data-stu-id="bfa21-135">None</span></span>
<span data-ttu-id="bfa21-136">Нельзя передать объекты в этот командлет с помощью конвейера.</span><span class="sxs-lookup"><span data-stu-id="bfa21-136">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="bfa21-137">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="bfa21-137">OUTPUTS</span></span>

### <span data-ttu-id="bfa21-138">Нет</span><span class="sxs-lookup"><span data-stu-id="bfa21-138">None</span></span>
<span data-ttu-id="bfa21-139">Этот командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="bfa21-139">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="bfa21-140">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="bfa21-140">NOTES</span></span>

* <span data-ttu-id="bfa21-141">Чтобы запустить этот командлет в Windows Vista и более поздних версиях Windows, откройте Windows PowerShell с параметром Запуск от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="bfa21-141">To run this cmdlet on Windows Vista and later versions of Windows, open Windows PowerShell with the Run as administrator option.</span></span>

  <span data-ttu-id="bfa21-142">Чтобы найти диски файловой системы, подходящие для восстановления системы, в разделе "система" панели управления перейдите на вкладку "Защита системы". Чтобы открыть эту вкладку в Windows PowerShell, введите `SystemPropertiesProtection` .</span><span class="sxs-lookup"><span data-stu-id="bfa21-142">To find the file system drives that are eligible for system restore, in System in Control Panel, see the System Protection tab. To open this tab in Windows PowerShell, type `SystemPropertiesProtection`.</span></span>

  <span data-ttu-id="bfa21-143">Этот командлет использует класс инструментарий управления Windows (WMI) (WMI) **SystemRestore** .</span><span class="sxs-lookup"><span data-stu-id="bfa21-143">This cmdlet uses the Windows Management Instrumentation (WMI) **SystemRestore** class.</span></span>

*

## <span data-ttu-id="bfa21-144">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="bfa21-144">RELATED LINKS</span></span>

[<span data-ttu-id="bfa21-145">Checkpoint-Computer</span><span class="sxs-lookup"><span data-stu-id="bfa21-145">Checkpoint-Computer</span></span>](Checkpoint-Computer.md)

[<span data-ttu-id="bfa21-146">Disable-ComputerRestore</span><span class="sxs-lookup"><span data-stu-id="bfa21-146">Disable-ComputerRestore</span></span>](Disable-ComputerRestore.md)

[<span data-ttu-id="bfa21-147">Get-ComputerRestorePoint</span><span class="sxs-lookup"><span data-stu-id="bfa21-147">Get-ComputerRestorePoint</span></span>](Get-ComputerRestorePoint.md)

[<span data-ttu-id="bfa21-148">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="bfa21-148">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="bfa21-149">Restore-Computer</span><span class="sxs-lookup"><span data-stu-id="bfa21-149">Restore-Computer</span></span>](Restore-Computer.md)
