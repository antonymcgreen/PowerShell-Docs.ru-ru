---
external help file: Enable-DscDebug.cdxml-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/enable-dscdebug?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-DscDebug
ms.openlocfilehash: 136481c5a1945c3d5cbd1ca7fc8ce5f580c39b0f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228345"
---
# <span data-ttu-id="973aa-103">Enable-DscDebug</span><span class="sxs-lookup"><span data-stu-id="973aa-103">Enable-DscDebug</span></span>

## <span data-ttu-id="973aa-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="973aa-104">SYNOPSIS</span></span>
<span data-ttu-id="973aa-105">Запускает отладку всех ресурсов DSC.</span><span class="sxs-lookup"><span data-stu-id="973aa-105">Starts debugging of all DSC resources.</span></span>

## <span data-ttu-id="973aa-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="973aa-106">SYNTAX</span></span>

```
Enable-DscDebug [-BreakAll] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="973aa-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="973aa-107">DESCRIPTION</span></span>
<span data-ttu-id="973aa-108">Командлет **Enable-DscDebug** включает отладку ресурсов Desired State Configuration (DSC) Windows PowerShell модулем DSC, который также называется локальным Configuration Manager (LCM).</span><span class="sxs-lookup"><span data-stu-id="973aa-108">The **Enable-DscDebug** cmdlet enables Windows PowerShell Desired State Configuration (DSC) resource debugging by the DSC engine, which is also known as the Local Configuration Manager (LCM).</span></span>
<span data-ttu-id="973aa-109">По умолчанию все экземпляры ресурсов разбиваются на отладчик.</span><span class="sxs-lookup"><span data-stu-id="973aa-109">By default, all resource instances break into the debugger.</span></span>

## <span data-ttu-id="973aa-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="973aa-110">EXAMPLES</span></span>

### <span data-ttu-id="973aa-111">Пример 1. Запуск отладки</span><span class="sxs-lookup"><span data-stu-id="973aa-111">Example 1: Start debugging</span></span>

```
PS C:\> Enable-DscDebug -BreakAll
```

<span data-ttu-id="973aa-112">Эта команда указывает модулю DSC или LCM запустить отладку ресурсов.</span><span class="sxs-lookup"><span data-stu-id="973aa-112">This command indicates to the DSC engine or LCM to start resource debugging.</span></span>
<span data-ttu-id="973aa-113">При следующем запуске конфигурации процесс переходит в отладчик.</span><span class="sxs-lookup"><span data-stu-id="973aa-113">The next time the configuration is run, the process enters the debugger.</span></span>

### <span data-ttu-id="973aa-114">Пример 2. Запуск удаленной отладки</span><span class="sxs-lookup"><span data-stu-id="973aa-114">Example 2: Start remote debugging</span></span>

```
PS C:\> Enable-DscDebug -BreakAll -CimSession DeploymentServer
```

<span data-ttu-id="973aa-115">Эта команда указывает модулю DSC удаленного компьютера запустить отладку ресурсов.</span><span class="sxs-lookup"><span data-stu-id="973aa-115">This command indicates to the DSC engine of the remote computer to start resource debugging.</span></span>

## <span data-ttu-id="973aa-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="973aa-116">PARAMETERS</span></span>

### <span data-ttu-id="973aa-117">-AsJob</span><span class="sxs-lookup"><span data-stu-id="973aa-117">-AsJob</span></span>
<span data-ttu-id="973aa-118">Указывает, что этот командлет выполняет команду как фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="973aa-118">Indicates that this cmdlet runs the command as a background job.</span></span>

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

### <span data-ttu-id="973aa-119">-BreakAll</span><span class="sxs-lookup"><span data-stu-id="973aa-119">-BreakAll</span></span>
<span data-ttu-id="973aa-120">Указывает, что все ресурсы вводят отладчик при выполнении конфигурации.</span><span class="sxs-lookup"><span data-stu-id="973aa-120">Indicates that all resources enter the debugger when a configuration runs.</span></span>

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

### <span data-ttu-id="973aa-121">-CimSession</span><span class="sxs-lookup"><span data-stu-id="973aa-121">-CimSession</span></span>
<span data-ttu-id="973aa-122">Запуск командлета в удаленном сеансе или на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="973aa-122">Runs the cmdlet in a remote session or on a remote computer.</span></span>
<span data-ttu-id="973aa-123">Введите имя компьютера или объект сеанса, например выходные данные командлета [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) или [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) .</span><span class="sxs-lookup"><span data-stu-id="973aa-123">Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet.</span></span>
<span data-ttu-id="973aa-124">Сеанс по умолчанию — текущий сеанс на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="973aa-124">The default is the current session on the local computer.</span></span>

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

### <span data-ttu-id="973aa-125">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="973aa-125">-ThrottleLimit</span></span>
<span data-ttu-id="973aa-126">Указание максимального количества одновременных операций, которые можно выполнять для запуска командлета.</span><span class="sxs-lookup"><span data-stu-id="973aa-126">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>
<span data-ttu-id="973aa-127">Если этот параметр пропущен или указано значение `0` , Windows PowerShell вычисляет оптимальное ограничение регулирования для командлета на основе числа командлетов CIM, выполняемых на компьютере.</span><span class="sxs-lookup"><span data-stu-id="973aa-127">If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.</span></span>
<span data-ttu-id="973aa-128">Предел регулирования применим только к текущему командлету, а не к сеансу или компьютеру.</span><span class="sxs-lookup"><span data-stu-id="973aa-128">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="973aa-129">-Confirm</span><span class="sxs-lookup"><span data-stu-id="973aa-129">-Confirm</span></span>
<span data-ttu-id="973aa-130">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="973aa-130">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="973aa-131">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="973aa-131">-WhatIf</span></span>
<span data-ttu-id="973aa-132">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="973aa-132">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="973aa-133">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="973aa-133">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="973aa-134">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="973aa-134">CommonParameters</span></span>
<span data-ttu-id="973aa-135">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="973aa-135">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="973aa-136">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="973aa-136">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="973aa-137">Входные данные</span><span class="sxs-lookup"><span data-stu-id="973aa-137">INPUTS</span></span>

## <span data-ttu-id="973aa-138">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="973aa-138">OUTPUTS</span></span>

## <span data-ttu-id="973aa-139">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="973aa-139">NOTES</span></span>

## <span data-ttu-id="973aa-140">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="973aa-140">RELATED LINKS</span></span>

[<span data-ttu-id="973aa-141">Обзор Windows PowerShell Desired State Configuration</span><span class="sxs-lookup"><span data-stu-id="973aa-141">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="973aa-142">Disable-DscDebug</span><span class="sxs-lookup"><span data-stu-id="973aa-142">Disable-DscDebug</span></span>](Disable-DscDebug.md)

[<span data-ttu-id="973aa-143">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="973aa-143">Get-DscConfiguration</span></span>](Get-DscConfiguration.md)

[<span data-ttu-id="973aa-144">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="973aa-144">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)

[<span data-ttu-id="973aa-145">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="973aa-145">Restore-DscConfiguration</span></span>](Restore-DscConfiguration.md)

[<span data-ttu-id="973aa-146">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="973aa-146">Start-DscConfiguration</span></span>](Start-DscConfiguration.md)

[<span data-ttu-id="973aa-147">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="973aa-147">Test-DscConfiguration</span></span>](Test-DscConfiguration.md)
