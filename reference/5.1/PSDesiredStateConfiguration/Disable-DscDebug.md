---
external help file: Disable-DscDebug.cdxml-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/disable-dscdebug?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-DscDebug
ms.openlocfilehash: fdaba8358772f559a33117c796a923d774b009cb
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228341"
---
# <span data-ttu-id="61044-103">Disable-DscDebug</span><span class="sxs-lookup"><span data-stu-id="61044-103">Disable-DscDebug</span></span>

## <span data-ttu-id="61044-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="61044-104">SYNOPSIS</span></span>
<span data-ttu-id="61044-105">Останавливает отладку ресурсов службы настройки требуемого состояния (DSC).</span><span class="sxs-lookup"><span data-stu-id="61044-105">Stops debugging of DSC resources.</span></span>

## <span data-ttu-id="61044-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="61044-106">SYNTAX</span></span>

```
Disable-DscDebug [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="61044-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="61044-107">DESCRIPTION</span></span>
<span data-ttu-id="61044-108">Командлет **Disable-DscDebug** отправляет к подсистеме службы настройки требуемого состояния Windows PowerShell запрос на остановку отладки ресурсов DSC.</span><span class="sxs-lookup"><span data-stu-id="61044-108">The **Disable-DscDebug** cmdlet requests that the Windows PowerShell Desired State Configuration (DSC) engine stop debugging of DSC resources.</span></span>
<span data-ttu-id="61044-109">Если в настоящее время подсистема DSC не находится в режиме отладки, этот командлет не выполняет никаких действий.</span><span class="sxs-lookup"><span data-stu-id="61044-109">This cmdlet has no effect if the DSC engine is not currently in debugging mode.</span></span>

## <span data-ttu-id="61044-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="61044-110">EXAMPLES</span></span>

### <span data-ttu-id="61044-111">Пример 1. Остановка отладки ресурсов</span><span class="sxs-lookup"><span data-stu-id="61044-111">Example 1: Stop resource debugging</span></span>

```
PS C:\> Disable-DscDebug
```

<span data-ttu-id="61044-112">Эта команда указывает подсистеме DSC в локальном диспетчере конфигураций остановить отладку ресурсов DSC.</span><span class="sxs-lookup"><span data-stu-id="61044-112">This command indicates to the DSC engine on the Local Configuration Manager (LCM) to stop resource debugging.</span></span>

### <span data-ttu-id="61044-113">Пример 2. Проверка состояния подсистемы и остановка отладки</span><span class="sxs-lookup"><span data-stu-id="61044-113">Example 2: Check the engine state and stop debugging</span></span>

```
PS C:\> if((Get-DscLocalConfigurationManager).DebugMode -like '*Break*'){Disable-DscDebug}
```

<span data-ttu-id="61044-114">Эта команда проверяет состояние подсистемы DSC и, если она уже находится в режиме отладки, останавливает этот процесс.</span><span class="sxs-lookup"><span data-stu-id="61044-114">This command checks the DSC engine state, and stops resource debugging only if it is already in debugging mode</span></span>

## <span data-ttu-id="61044-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="61044-115">PARAMETERS</span></span>

### <span data-ttu-id="61044-116">-AsJob</span><span class="sxs-lookup"><span data-stu-id="61044-116">-AsJob</span></span>
<span data-ttu-id="61044-117">Указывает, что этот командлет выполняет команду как фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="61044-117">Indicates that this cmdlet runs the command as a background job.</span></span>

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

### <span data-ttu-id="61044-118">-CimSession</span><span class="sxs-lookup"><span data-stu-id="61044-118">-CimSession</span></span>
<span data-ttu-id="61044-119">Запуск командлета в удаленном сеансе или на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="61044-119">Runs the cmdlet in a remote session or on a remote computer.</span></span>
<span data-ttu-id="61044-120">Введите имя компьютера или объект сеанса, например выходные данные командлета [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) или [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) .</span><span class="sxs-lookup"><span data-stu-id="61044-120">Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet.</span></span>
<span data-ttu-id="61044-121">Сеанс по умолчанию — текущий сеанс на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="61044-121">The default is the current session on the local computer.</span></span>

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

### <span data-ttu-id="61044-122">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="61044-122">-ThrottleLimit</span></span>
<span data-ttu-id="61044-123">Указание максимального количества одновременных операций, которые можно выполнять для запуска командлета.</span><span class="sxs-lookup"><span data-stu-id="61044-123">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>
<span data-ttu-id="61044-124">Если этот параметр пропущен или указано значение `0` , Windows PowerShell вычисляет оптимальное ограничение регулирования для командлета на основе числа командлетов CIM, выполняемых на компьютере.</span><span class="sxs-lookup"><span data-stu-id="61044-124">If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.</span></span>
<span data-ttu-id="61044-125">Предел регулирования применим только к текущему командлету, а не к сеансу или компьютеру.</span><span class="sxs-lookup"><span data-stu-id="61044-125">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="61044-126">-Confirm</span><span class="sxs-lookup"><span data-stu-id="61044-126">-Confirm</span></span>
<span data-ttu-id="61044-127">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="61044-127">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="61044-128">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="61044-128">-WhatIf</span></span>
<span data-ttu-id="61044-129">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="61044-129">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="61044-130">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="61044-130">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="61044-131">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="61044-131">CommonParameters</span></span>
<span data-ttu-id="61044-132">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="61044-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="61044-133">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="61044-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="61044-134">Входные данные</span><span class="sxs-lookup"><span data-stu-id="61044-134">INPUTS</span></span>

## <span data-ttu-id="61044-135">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="61044-135">OUTPUTS</span></span>

## <span data-ttu-id="61044-136">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="61044-136">NOTES</span></span>

## <span data-ttu-id="61044-137">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="61044-137">RELATED LINKS</span></span>

[<span data-ttu-id="61044-138">Обзор Windows PowerShell Desired State Configuration</span><span class="sxs-lookup"><span data-stu-id="61044-138">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="61044-139">Enable-DscDebug</span><span class="sxs-lookup"><span data-stu-id="61044-139">Enable-DscDebug</span></span>](Enable-DscDebug.md)

[<span data-ttu-id="61044-140">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="61044-140">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)

[<span data-ttu-id="61044-141">Get-DscLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="61044-141">Get-DscLocalConfigurationManager</span></span>](Get-DscLocalConfigurationManager.md)

[<span data-ttu-id="61044-142">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="61044-142">Restore-DscConfiguration</span></span>](Restore-DscConfiguration.md)

[<span data-ttu-id="61044-143">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="61044-143">Start-DscConfiguration</span></span>](Start-DscConfiguration.md)

[<span data-ttu-id="61044-144">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="61044-144">Test-DscConfiguration</span></span>](Test-DscConfiguration.md)
