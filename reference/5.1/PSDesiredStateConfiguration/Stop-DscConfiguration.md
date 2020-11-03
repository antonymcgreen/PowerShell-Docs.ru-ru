---
external help file: Stop-DscConfiguration.cdxml-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 08/19/2019
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/stop-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-DscConfiguration
ms.openlocfilehash: 93c8585ae948dfa360a2ae8e2563670de8fd6e93
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227465"
---
# <span data-ttu-id="fc3b6-103">Stop-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="fc3b6-103">Stop-DscConfiguration</span></span>

## <span data-ttu-id="fc3b6-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="fc3b6-104">SYNOPSIS</span></span>
<span data-ttu-id="fc3b6-105">Останавливает выполняемое задание настройки.</span><span class="sxs-lookup"><span data-stu-id="fc3b6-105">Stops a configuration job that is running.</span></span>

## <span data-ttu-id="fc3b6-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fc3b6-106">SYNTAX</span></span>

### <span data-ttu-id="fc3b6-107">Все</span><span class="sxs-lookup"><span data-stu-id="fc3b6-107">All</span></span>

```
Stop-DscConfiguration [-Force] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="fc3b6-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fc3b6-108">DESCRIPTION</span></span>

<span data-ttu-id="fc3b6-109">`Stop-DscConfiguration`Командлет останавливает выполняемое задание настройки.</span><span class="sxs-lookup"><span data-stu-id="fc3b6-109">The `Stop-DscConfiguration` cmdlet stops a configuration job that is running.</span></span> <span data-ttu-id="fc3b6-110">Укажите компьютеры, к которым применяется этот командлет, с помощью сеансов модель CIM (CIM).</span><span class="sxs-lookup"><span data-stu-id="fc3b6-110">Specify which computers this cmdlet applies to by using Common Information Model (CIM) sessions.</span></span> <span data-ttu-id="fc3b6-111">Если задание конфигурации не запускается, этот командлет возвращает предупреждающее сообщение.</span><span class="sxs-lookup"><span data-stu-id="fc3b6-111">If there's no configuration job running, this cmdlet returns a warning message.</span></span>

<span data-ttu-id="fc3b6-112">`Stop-DscConfiguration` доступно только в составе [накопительного пакета обновления за ноябрь 2014 для Windows RT 8,1, Windows 8.1 и Windows Server 2012 R2](https://support.microsoft.com/kb/3000850) из библиотеки служба поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="fc3b6-112">`Stop-DscConfiguration` is only available as part of the [November 2014 update rollup for Windows RT 8.1, Windows 8.1, and Windows Server 2012 R2](https://support.microsoft.com/kb/3000850) from the Microsoft Support library.</span></span> <span data-ttu-id="fc3b6-113">Перед использованием этого командлета ознакомьтесь со сведениями в подразделах [что нового в Windows PowerShell 5,0](/powershell/scripting/whats-new/What-s-New-in-Windows-PowerShell-50)</span><span class="sxs-lookup"><span data-stu-id="fc3b6-113">Before you use this cmdlet, review the information in [What's New in Windows PowerShell 5.0](/powershell/scripting/whats-new/What-s-New-in-Windows-PowerShell-50)</span></span>

## <span data-ttu-id="fc3b6-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="fc3b6-114">EXAMPLES</span></span>

### <span data-ttu-id="fc3b6-115">Пример 1. завершение задания конфигурации</span><span class="sxs-lookup"><span data-stu-id="fc3b6-115">Example 1: Stop a configuration job</span></span>

<span data-ttu-id="fc3b6-116">В этом примере создается сеанс CIM с помощью `New-CimSession` командлета.</span><span class="sxs-lookup"><span data-stu-id="fc3b6-116">In this example, a CIM session is created using the `New-CimSession` cmdlet.</span></span> <span data-ttu-id="fc3b6-117">Объект **CimSession** используется для завершения выполняющегося задания конфигурации.</span><span class="sxs-lookup"><span data-stu-id="fc3b6-117">The **CimSession** object is used to stop a running configuration job.</span></span>

```powershell
$Session = New-CimSession -ComputerName Server01 -Credential ACCOUNTS\User01
Stop-DscConfiguration -CimSession $Session
```

<span data-ttu-id="fc3b6-118">`New-CimSession` использует параметр **ComputerName** для указания компьютера Server01.</span><span class="sxs-lookup"><span data-stu-id="fc3b6-118">`New-CimSession` uses the **ComputerName** parameter to specify the Server01 computer.</span></span> <span data-ttu-id="fc3b6-119">Параметр **Credential** указывает учетную запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="fc3b6-119">The **Credential** parameter specifies the user account.</span></span> <span data-ttu-id="fc3b6-120">Объект **CimSession** хранится в `$Session` переменной.</span><span class="sxs-lookup"><span data-stu-id="fc3b6-120">The **CimSession** object is stored in the `$Session` variable.</span></span> <span data-ttu-id="fc3b6-121">При выполнении команды вам будет предложено ввести пароль учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="fc3b6-121">When the command is run, you're prompted for the user account's password.</span></span>

<span data-ttu-id="fc3b6-122">`Stop-DscConfiguration` использует параметр **CimSession** и объект, хранящийся в `$Session` , для завершения задания настройки.</span><span class="sxs-lookup"><span data-stu-id="fc3b6-122">`Stop-DscConfiguration` uses the **CimSession** parameter and the object stored in `$Session` to stop the configuration job.</span></span>

## <span data-ttu-id="fc3b6-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fc3b6-123">PARAMETERS</span></span>

### <span data-ttu-id="fc3b6-124">-AsJob</span><span class="sxs-lookup"><span data-stu-id="fc3b6-124">-AsJob</span></span>

<span data-ttu-id="fc3b6-125">Указывает, что этот командлет выполняет команду как фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="fc3b6-125">Indicates that this cmdlet runs the command as a background job.</span></span> <span data-ttu-id="fc3b6-126">Дополнительные сведения о фоновых заданиях PowerShell см. в разделе [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) и [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="fc3b6-126">For more information about PowerShell background jobs, see [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) and [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md).</span></span>

<span data-ttu-id="fc3b6-127">Для использования параметра **AsJob** локальный и удаленный компьютеры должны быть настроены для удаленного взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="fc3b6-127">To use the **AsJob** parameter, the local and remote computers must be configured for remoting.</span></span> <span data-ttu-id="fc3b6-128">В Windows Vista и более поздних версиях операционной системы Windows необходимо открыть PowerShell с параметром **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="fc3b6-128">On Windows Vista and later versions of the Windows operating system, you must open PowerShell with the **Run as administrator** option.</span></span> <span data-ttu-id="fc3b6-129">Дополнительные сведения см. в разделе [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc3b6-129">For more information, see [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).</span></span>

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

### <span data-ttu-id="fc3b6-130">-CimSession</span><span class="sxs-lookup"><span data-stu-id="fc3b6-130">-CimSession</span></span>

<span data-ttu-id="fc3b6-131">Запуск командлета в удаленном сеансе или на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="fc3b6-131">Runs the cmdlet in a remote session or on a remote computer.</span></span> <span data-ttu-id="fc3b6-132">Введите имя компьютера или объект сеанса, например выходные данные из `New-CimSession` или `Get-CimSession` .</span><span class="sxs-lookup"><span data-stu-id="fc3b6-132">Enter a computer name or a session object, such as the output from `New-CimSession` or `Get-CimSession`.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fc3b6-133">-Confirm</span><span class="sxs-lookup"><span data-stu-id="fc3b6-133">-Confirm</span></span>

<span data-ttu-id="fc3b6-134">`Stop-DscConfiguration` не поддерживает параметр **Confirm** .</span><span class="sxs-lookup"><span data-stu-id="fc3b6-134">`Stop-DscConfiguration` doesn't support the **Confirm** parameter.</span></span> <span data-ttu-id="fc3b6-135">Если используется параметр **Confirm** , выводится сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="fc3b6-135">If the **Confirm** parameter is used, an error is displayed.</span></span>

<span data-ttu-id="fc3b6-136">Для командлетов PowerShell, поддерживающих **Confirm** , с помощью параметра запрашиваются подтверждение перед выполнением команды.</span><span class="sxs-lookup"><span data-stu-id="fc3b6-136">For PowerShell cmdlets that support **Confirm** , using the parameter prompts you for verification before a command is run.</span></span>

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

### <span data-ttu-id="fc3b6-137">-Force</span><span class="sxs-lookup"><span data-stu-id="fc3b6-137">-Force</span></span>

<span data-ttu-id="fc3b6-138">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="fc3b6-138">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="fc3b6-139">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="fc3b6-139">-ThrottleLimit</span></span>

<span data-ttu-id="fc3b6-140">Указание максимального количества одновременных операций, которые можно выполнять для запуска командлета.</span><span class="sxs-lookup"><span data-stu-id="fc3b6-140">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>

<span data-ttu-id="fc3b6-141">Если этот параметр пропущен или указано значение `0` , PowerShell вычисляет оптимальное ограничение регулирования на основе числа командлетов CIM, выполняемых на компьютере.</span><span class="sxs-lookup"><span data-stu-id="fc3b6-141">If this parameter is omitted or a value of `0` is entered, PowerShell calculates an optimum throttle limit based on the number of CIM cmdlets that are running on the computer.</span></span> <span data-ttu-id="fc3b6-142">Предел регулирования применим только к текущему командлету, а не к сеансу или компьютеру.</span><span class="sxs-lookup"><span data-stu-id="fc3b6-142">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fc3b6-143">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="fc3b6-143">-WhatIf</span></span>

<span data-ttu-id="fc3b6-144">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="fc3b6-144">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="fc3b6-145">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="fc3b6-145">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="fc3b6-146">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="fc3b6-146">CommonParameters</span></span>

<span data-ttu-id="fc3b6-147">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="fc3b6-147">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fc3b6-148">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="fc3b6-148">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fc3b6-149">Входные данные</span><span class="sxs-lookup"><span data-stu-id="fc3b6-149">INPUTS</span></span>

### <span data-ttu-id="fc3b6-150">Нет</span><span class="sxs-lookup"><span data-stu-id="fc3b6-150">None</span></span>

## <span data-ttu-id="fc3b6-151">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="fc3b6-151">OUTPUTS</span></span>

### <span data-ttu-id="fc3b6-152">Нет</span><span class="sxs-lookup"><span data-stu-id="fc3b6-152">None</span></span>

## <span data-ttu-id="fc3b6-153">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="fc3b6-153">NOTES</span></span>

## <span data-ttu-id="fc3b6-154">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="fc3b6-154">RELATED LINKS</span></span>

[<span data-ttu-id="fc3b6-155">Get-CimSession</span><span class="sxs-lookup"><span data-stu-id="fc3b6-155">Get-CimSession</span></span>](../CimCmdlets/Get-CimSession.md)

[<span data-ttu-id="fc3b6-156">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="fc3b6-156">Get-DscConfiguration</span></span>](Get-DscConfiguration.md)

[<span data-ttu-id="fc3b6-157">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="fc3b6-157">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)

[<span data-ttu-id="fc3b6-158">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="fc3b6-158">New-CimSession</span></span>](../CimCmdlets/New-CimSession.md)

[<span data-ttu-id="fc3b6-159">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="fc3b6-159">Restore-DscConfiguration</span></span>](Restore-DscConfiguration.md)

[<span data-ttu-id="fc3b6-160">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="fc3b6-160">Start-DscConfiguration</span></span>](Start-DscConfiguration.md)

[<span data-ttu-id="fc3b6-161">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="fc3b6-161">Test-DscConfiguration</span></span>](Test-DscConfiguration.md)

[<span data-ttu-id="fc3b6-162">Update-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="fc3b6-162">Update-DscConfiguration</span></span>](Update-DscConfiguration.md)

[<span data-ttu-id="fc3b6-163">Обзор Windows PowerShell Desired State Configuration</span><span class="sxs-lookup"><span data-stu-id="fc3b6-163">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/overview)
