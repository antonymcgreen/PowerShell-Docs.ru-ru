---
external help file: Get-DSCConfiguration.cdxml-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/get-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DscConfiguration
ms.openlocfilehash: 42b24e72de4c4bcc9326d52861c08a05853b18e0
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228342"
---
# <span data-ttu-id="38b50-103">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="38b50-103">Get-DscConfiguration</span></span>

## <span data-ttu-id="38b50-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="38b50-104">SYNOPSIS</span></span>
<span data-ttu-id="38b50-105">Возвращает текущую конфигурацию узлов.</span><span class="sxs-lookup"><span data-stu-id="38b50-105">Gets the current configuration of the nodes.</span></span>

## <span data-ttu-id="38b50-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="38b50-106">SYNTAX</span></span>

```
Get-DscConfiguration [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## <span data-ttu-id="38b50-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="38b50-107">DESCRIPTION</span></span>
<span data-ttu-id="38b50-108">Командлет **Get-DscConfiguration** возвращает текущую конфигурацию узлов, если такая конфигурация существует.</span><span class="sxs-lookup"><span data-stu-id="38b50-108">The **Get-DscConfiguration** cmdlet gets the current configuration of the nodes, if the configuration exists.</span></span>
<span data-ttu-id="38b50-109">Укажите компьютеры, используя сеансы модели CIM.</span><span class="sxs-lookup"><span data-stu-id="38b50-109">Specify computers by using Common Information Model (CIM) sessions.</span></span>
<span data-ttu-id="38b50-110">Если целевой компьютер не указан, командлет возвращает конфигурацию с локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="38b50-110">If you do not specify a target computer, the cmdlet gets the configuration from the local computer.</span></span>

## <span data-ttu-id="38b50-111">Примеры</span><span class="sxs-lookup"><span data-stu-id="38b50-111">EXAMPLES</span></span>

### <span data-ttu-id="38b50-112">Пример 1. получение конфигурации для локального компьютера</span><span class="sxs-lookup"><span data-stu-id="38b50-112">Example 1: Get the configuration for the local computer</span></span>

```
PS C:\> Get-DscConfiguration
```

<span data-ttu-id="38b50-113">Эта команда возвращает текущее состояние для локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="38b50-113">This command gets the current state for the local computer.</span></span>

### <span data-ttu-id="38b50-114">Пример 2. получение конфигурации для указанного компьютера</span><span class="sxs-lookup"><span data-stu-id="38b50-114">Example 2: Get the configuration for a specified computer</span></span>

```
PS C:\> $Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
PS C:\> Get-DscConfiguration -CimSession $Session
```

<span data-ttu-id="38b50-115">Этот пример получает текущее состояние с компьютера, указанного в сеансе CIM.</span><span class="sxs-lookup"><span data-stu-id="38b50-115">This example gets the current state from a computer specified by a CIM session.</span></span>
<span data-ttu-id="38b50-116">Пример создает сеанс CIM для компьютера с именем Server01, чтобы использовать с командлетом.</span><span class="sxs-lookup"><span data-stu-id="38b50-116">The example creates a CIM session for a computer named Server01 for use with the cmdlet.</span></span>
<span data-ttu-id="38b50-117">Кроме того, можно создать массив сеансов CIM для применения командлета к нескольким указанным компьютерам.</span><span class="sxs-lookup"><span data-stu-id="38b50-117">Alternatively, create an array of CIM sessions to apply the cmdlet to multiple specified computers.</span></span>

<span data-ttu-id="38b50-118">Первая команда создает сеанс CIM, используя командлет **New-CimSession** , а затем сохраняет объект **CimSession** в переменной **$Session** .</span><span class="sxs-lookup"><span data-stu-id="38b50-118">The first command creates a CIM session by using the **New-CimSession** cmdlet, and then stores the **CimSession** object in the **$Session** variable.</span></span>
<span data-ttu-id="38b50-119">Команда запрашивает пароль.</span><span class="sxs-lookup"><span data-stu-id="38b50-119">The command prompts you for a password.</span></span>
<span data-ttu-id="38b50-120">Для получения дополнительных сведений введите `Get-Help New-CimSession`.</span><span class="sxs-lookup"><span data-stu-id="38b50-120">For more information, type `Get-Help New-CimSession`.</span></span>

<span data-ttu-id="38b50-121">Вторая команда возвращает текущую конфигурацию для компьютеров, определенных объектами **CimSession** , сохраненными в переменной **$Session** , в данном случае — для компьютера с именем Server01.</span><span class="sxs-lookup"><span data-stu-id="38b50-121">The second command gets the current configuration for the computers identified by the **CimSession** objects stored in the **$Session** variable, in this case, the computer named Server01.</span></span>

## <span data-ttu-id="38b50-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="38b50-122">PARAMETERS</span></span>

### <span data-ttu-id="38b50-123">-AsJob</span><span class="sxs-lookup"><span data-stu-id="38b50-123">-AsJob</span></span>
<span data-ttu-id="38b50-124">Указывает, что этот командлет выполняет команду как фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="38b50-124">Indicates that this cmdlet runs the command as a background job.</span></span>

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

### <span data-ttu-id="38b50-125">-CimSession</span><span class="sxs-lookup"><span data-stu-id="38b50-125">-CimSession</span></span>
<span data-ttu-id="38b50-126">Запуск командлета в удаленном сеансе или на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="38b50-126">Runs the cmdlet in a remote session or on a remote computer.</span></span>
<span data-ttu-id="38b50-127">Введите имя компьютера или объект сеанса, например выходные данные командлета [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) или [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) .</span><span class="sxs-lookup"><span data-stu-id="38b50-127">Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet.</span></span>
<span data-ttu-id="38b50-128">Сеанс по умолчанию — текущий сеанс на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="38b50-128">The default is the current session on the local computer.</span></span>

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

### <span data-ttu-id="38b50-129">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="38b50-129">-ThrottleLimit</span></span>
<span data-ttu-id="38b50-130">Указание максимального количества одновременных операций, которые можно выполнять для запуска командлета.</span><span class="sxs-lookup"><span data-stu-id="38b50-130">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>
<span data-ttu-id="38b50-131">Если этот параметр пропущен или указано значение `0` , Windows PowerShell вычисляет оптимальное ограничение регулирования для командлета на основе числа командлетов CIM, выполняемых на компьютере.</span><span class="sxs-lookup"><span data-stu-id="38b50-131">If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.</span></span>
<span data-ttu-id="38b50-132">Предел регулирования применим только к текущему командлету, а не к сеансу или компьютеру.</span><span class="sxs-lookup"><span data-stu-id="38b50-132">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="38b50-133">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="38b50-133">CommonParameters</span></span>
<span data-ttu-id="38b50-134">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="38b50-134">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="38b50-135">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="38b50-135">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="38b50-136">Входные данные</span><span class="sxs-lookup"><span data-stu-id="38b50-136">INPUTS</span></span>

## <span data-ttu-id="38b50-137">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="38b50-137">OUTPUTS</span></span>

## <span data-ttu-id="38b50-138">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="38b50-138">NOTES</span></span>

## <span data-ttu-id="38b50-139">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="38b50-139">RELATED LINKS</span></span>

[<span data-ttu-id="38b50-140">Обзор Windows PowerShell Desired State Configuration</span><span class="sxs-lookup"><span data-stu-id="38b50-140">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="38b50-141">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="38b50-141">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)

[<span data-ttu-id="38b50-142">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="38b50-142">Restore-DscConfiguration</span></span>](Restore-DscConfiguration.md)

[<span data-ttu-id="38b50-143">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="38b50-143">Start-DscConfiguration</span></span>](Start-DscConfiguration.md)

[<span data-ttu-id="38b50-144">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="38b50-144">Test-DscConfiguration</span></span>](Test-DscConfiguration.md)
