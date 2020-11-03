---
external help file: Get-DscConfigurationStatus.cdxml-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/get-dscconfigurationstatus?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DscConfigurationStatus
ms.openlocfilehash: 0d59ce58a70eab68441ea1fe6097bbdf7792a54f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228346"
---
# <span data-ttu-id="20458-103">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="20458-103">Get-DscConfigurationStatus</span></span>

## <span data-ttu-id="20458-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="20458-104">SYNOPSIS</span></span>
<span data-ttu-id="20458-105">Извлекает данные о завершенных запусках конфигурации.</span><span class="sxs-lookup"><span data-stu-id="20458-105">Retrieves data about completed configuration runs.</span></span>

## <span data-ttu-id="20458-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="20458-106">SYNTAX</span></span>

```
Get-DscConfigurationStatus [-All] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## <span data-ttu-id="20458-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="20458-107">DESCRIPTION</span></span>
<span data-ttu-id="20458-108">Командлет **Get-DscConfigurationStatus** извлекает подробные сведения о завершенных запусках конфигурации в системе.</span><span class="sxs-lookup"><span data-stu-id="20458-108">The **Get-DscConfigurationStatus** cmdlet retrieves detailed information about completed configuration runs on the system.</span></span>
<span data-ttu-id="20458-109">По умолчанию он возвращает сведения о последнем запуске конфигурации.</span><span class="sxs-lookup"><span data-stu-id="20458-109">By default, it returns the information about the last configuration run.</span></span>
<span data-ttu-id="20458-110">Этот командлет полезен для поиска исторических сведений о выполнении конфигурации, например при выполнении конфигураций, состоянии выполнения, количестве ресурсов в конфигурациях, а также об успешном или неудачном завершении ресурсов.</span><span class="sxs-lookup"><span data-stu-id="20458-110">This cmdlet is useful for finding historical information about configuration runs, such as when the configurations were run, the status of the runs, the number of resources in the configurations, and which resources succeeded or failed.</span></span>

## <span data-ttu-id="20458-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="20458-111">EXAMPLES</span></span>

### <span data-ttu-id="20458-112">Пример 1. Получение сведений о последнем запуске конфигурации</span><span class="sxs-lookup"><span data-stu-id="20458-112">Example 1: Get information on the last configuration run</span></span>

```
PS C:\> Get-DscConfigurationStatus
```

<span data-ttu-id="20458-113">Эта команда возвращает сведения о последнем запуске конфигурации.</span><span class="sxs-lookup"><span data-stu-id="20458-113">This command gets information on the last configuration run.</span></span>

### <span data-ttu-id="20458-114">Пример 2. Получение сведений обо всех конфигурациях</span><span class="sxs-lookup"><span data-stu-id="20458-114">Example 2: Get information on all configurations</span></span>

```
PS C:\> Get-DscConfigurationStatus -All
```

<span data-ttu-id="20458-115">Эта команда возвращает сведения обо всех конфигурациях, которые были запущены в системе, включая проверку согласованности Desired State Configuration (DSC) Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="20458-115">This command gets information about all the configurations that were run on the system, including the Windows PowerShell Desired State Configuration (DSC) consistency check.</span></span>

### <span data-ttu-id="20458-116">Пример 3. Получение сведений о настройке, выполняемой на удаленном компьютере</span><span class="sxs-lookup"><span data-stu-id="20458-116">Example 3: Get information on the configuration run on a remote computer</span></span>

```
PS C:\> Get-DscConfigurationStatus -CimSession "Server01"
```

<span data-ttu-id="20458-117">Эта команда возвращает сведения о выполнении конфигурации удаленного компьютера с именем Server01.</span><span class="sxs-lookup"><span data-stu-id="20458-117">This command gets the configuration run details of the remote computer named Server01.</span></span>
<span data-ttu-id="20458-118">При этом используется транспорт WSMan для подключения к удаленному компьютеру и требуется, чтобы подключающийся пользователь был администратором на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="20458-118">This uses the WSMan transport to connect to the remote computer and requires that the connecting user be an administrator on the remote computer.</span></span>

## <span data-ttu-id="20458-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="20458-119">PARAMETERS</span></span>

### <span data-ttu-id="20458-120">-All</span><span class="sxs-lookup"><span data-stu-id="20458-120">-All</span></span>
<span data-ttu-id="20458-121">Указывает, что этот командлет извлекает сведения обо всех запусках конфигурации на компьютере, включая приложение конфигурации и проверку согласованности.</span><span class="sxs-lookup"><span data-stu-id="20458-121">Indicates that this cmdlet retrieves information about all the configuration runs on the computer, including the configuration application and the consistency check.</span></span>

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

### <span data-ttu-id="20458-122">-AsJob</span><span class="sxs-lookup"><span data-stu-id="20458-122">-AsJob</span></span>
<span data-ttu-id="20458-123">Указывает, что этот командлет выполняет команду как фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="20458-123">Indicates that this cmdlet runs the command as a background job.</span></span>

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

### <span data-ttu-id="20458-124">-CimSession</span><span class="sxs-lookup"><span data-stu-id="20458-124">-CimSession</span></span>
<span data-ttu-id="20458-125">Запуск командлета в удаленном сеансе или на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="20458-125">Runs the cmdlet in a remote session or on a remote computer.</span></span>
<span data-ttu-id="20458-126">Введите имя компьютера или объект сеанса, например выходные данные командлета [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) или [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) .</span><span class="sxs-lookup"><span data-stu-id="20458-126">Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet.</span></span>
<span data-ttu-id="20458-127">Сеанс по умолчанию — текущий сеанс на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="20458-127">The default is the current session on the local computer.</span></span>

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

### <span data-ttu-id="20458-128">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="20458-128">-ThrottleLimit</span></span>
<span data-ttu-id="20458-129">Указание максимального количества одновременных операций, которые можно выполнять для запуска командлета.</span><span class="sxs-lookup"><span data-stu-id="20458-129">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>
<span data-ttu-id="20458-130">Если этот параметр пропущен или указано значение `0` , Windows PowerShell вычисляет оптимальное ограничение регулирования для командлета на основе числа командлетов CIM, выполняемых на компьютере.</span><span class="sxs-lookup"><span data-stu-id="20458-130">If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.</span></span>
<span data-ttu-id="20458-131">Предел регулирования применим только к текущему командлету, а не к сеансу или компьютеру.</span><span class="sxs-lookup"><span data-stu-id="20458-131">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="20458-132">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="20458-132">CommonParameters</span></span>
<span data-ttu-id="20458-133">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="20458-133">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="20458-134">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="20458-134">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="20458-135">Входные данные</span><span class="sxs-lookup"><span data-stu-id="20458-135">INPUTS</span></span>

## <span data-ttu-id="20458-136">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="20458-136">OUTPUTS</span></span>

## <span data-ttu-id="20458-137">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="20458-137">NOTES</span></span>

## <span data-ttu-id="20458-138">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="20458-138">RELATED LINKS</span></span>

[<span data-ttu-id="20458-139">Обзор Windows PowerShell Desired State Configuration</span><span class="sxs-lookup"><span data-stu-id="20458-139">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="20458-140">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="20458-140">Get-DscConfiguration</span></span>](Get-DscConfiguration.md)

[<span data-ttu-id="20458-141">Get-DscLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="20458-141">Get-DscLocalConfigurationManager</span></span>](Get-DscLocalConfigurationManager.md)

[<span data-ttu-id="20458-142">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="20458-142">Restore-DscConfiguration</span></span>](Restore-DscConfiguration.md)

[<span data-ttu-id="20458-143">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="20458-143">Start-DscConfiguration</span></span>](Start-DscConfiguration.md)

[<span data-ttu-id="20458-144">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="20458-144">Test-DscConfiguration</span></span>](Test-DscConfiguration.md)
