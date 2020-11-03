---
external help file: Restore-DSCConfiguration.cdxml-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/restore-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Restore-DscConfiguration
ms.openlocfilehash: 823032f7665d9ec83faa59c37560510e049efdd2
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228313"
---
# <span data-ttu-id="0ac92-103">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="0ac92-103">Restore-DscConfiguration</span></span>

## <span data-ttu-id="0ac92-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="0ac92-104">SYNOPSIS</span></span>
<span data-ttu-id="0ac92-105">Повторно применяет предыдущую конфигурацию для узла.</span><span class="sxs-lookup"><span data-stu-id="0ac92-105">Reapplies the previous configuration for the node.</span></span>

## <span data-ttu-id="0ac92-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0ac92-106">SYNTAX</span></span>

```
Restore-DscConfiguration [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="0ac92-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0ac92-107">DESCRIPTION</span></span>
<span data-ttu-id="0ac92-108">Командлет **reapplies-DscConfiguration** повторно применяет предыдущую конфигурацию узла, если существует предыдущая конфигурация.</span><span class="sxs-lookup"><span data-stu-id="0ac92-108">The **Restore-DscConfiguration** cmdlet reapplies the previous configuration for the node, if a previous configuration exists.</span></span>
<span data-ttu-id="0ac92-109">Укажите компьютеры, используя сеансы модели CIM.</span><span class="sxs-lookup"><span data-stu-id="0ac92-109">Specify computers by using Common Information Model (CIM) sessions.</span></span>
<span data-ttu-id="0ac92-110">Если целевой компьютер не указан, командлет восстанавливает конфигурацию на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="0ac92-110">If you do not specify a target computer, the cmdlet restores the configuration of the local computer.</span></span>
<span data-ttu-id="0ac92-111">Если предыдущая конфигурация для конкретного узла отсутствует, этот командлет возвращает сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="0ac92-111">If there is no previous configuration for a particular node, this cmdlet returns an error message.</span></span>

<span data-ttu-id="0ac92-112">Этот командлет не поддерживает параметр **Confirm** .</span><span class="sxs-lookup"><span data-stu-id="0ac92-112">This cmdlet does not support the **Confirm** parameter.</span></span>

## <span data-ttu-id="0ac92-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="0ac92-113">EXAMPLES</span></span>

### <span data-ttu-id="0ac92-114">Пример 1. Восстановление конфигурации для локального компьютера</span><span class="sxs-lookup"><span data-stu-id="0ac92-114">Example 1: Restore the configuration for the local computer</span></span>

```
PS C:\> Restore-DscConfiguration
```

<span data-ttu-id="0ac92-115">Эта команда восстанавливает конфигурацию для локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="0ac92-115">This command restores the configuration for the local computer.</span></span>

### <span data-ttu-id="0ac92-116">Пример 2. Восстановление конфигурации для указанного компьютера</span><span class="sxs-lookup"><span data-stu-id="0ac92-116">Example 2: Restore configuration for a specified computer</span></span>

```
PS C:\> $Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
PS C:\> Restore-DscConfiguration -CimSession $Session
```

<span data-ttu-id="0ac92-117">В этом примере восстанавливается конфигурация на компьютере, указанном сеансом CIM.</span><span class="sxs-lookup"><span data-stu-id="0ac92-117">This example restores configuration on a computer specified by a CIM session.</span></span>
<span data-ttu-id="0ac92-118">Пример создает сеанс CIM для компьютера с именем Server01, чтобы использовать с командлетом.</span><span class="sxs-lookup"><span data-stu-id="0ac92-118">The example creates a CIM session for a computer named Server01 for use with the cmdlet.</span></span>
<span data-ttu-id="0ac92-119">Кроме того, можно создать массив сеансов CIM для применения командлета к нескольким указанным компьютерам.</span><span class="sxs-lookup"><span data-stu-id="0ac92-119">Alternatively, create an array of CIM sessions to apply the cmdlet to multiple specified computers.</span></span>

<span data-ttu-id="0ac92-120">Первая команда создает сеанс CIM, используя командлет **New-CimSession** , а затем сохраняет объект **CimSession** в переменной $Session.</span><span class="sxs-lookup"><span data-stu-id="0ac92-120">The first command creates a CIM session by using the **New-CimSession** cmdlet, and then stores the **CimSession** object in the $Session variable.</span></span>
<span data-ttu-id="0ac92-121">Команда запрашивает пароль.</span><span class="sxs-lookup"><span data-stu-id="0ac92-121">The command prompts you for a password.</span></span>
<span data-ttu-id="0ac92-122">Для получения дополнительных сведений введите `Get-Help New-CimSession`.</span><span class="sxs-lookup"><span data-stu-id="0ac92-122">For more information, type `Get-Help New-CimSession`.</span></span>

<span data-ttu-id="0ac92-123">Вторая команда восстанавливает конфигурацию для компьютеров, определенных объектами **CimSession** , сохраненными в переменной $Session, в данном случае — для компьютера с именем Server01.</span><span class="sxs-lookup"><span data-stu-id="0ac92-123">The second command restores the configuration for the computers identified by the **CimSession** objects stored in the $Session variable, in this case, the computer named Server01.</span></span>

## <span data-ttu-id="0ac92-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0ac92-124">PARAMETERS</span></span>

### <span data-ttu-id="0ac92-125">-AsJob</span><span class="sxs-lookup"><span data-stu-id="0ac92-125">-AsJob</span></span>
<span data-ttu-id="0ac92-126">Указывает, что этот командлет выполняет команду как фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="0ac92-126">Indicates that this cmdlet runs the command as a background job.</span></span>

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

### <span data-ttu-id="0ac92-127">-CimSession</span><span class="sxs-lookup"><span data-stu-id="0ac92-127">-CimSession</span></span>
<span data-ttu-id="0ac92-128">Запуск командлета в удаленном сеансе или на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="0ac92-128">Runs the cmdlet in a remote session or on a remote computer.</span></span>
<span data-ttu-id="0ac92-129">Введите имя компьютера или объект сеанса, например выходные данные командлета **New-CimSession** или **Get-CimSession** .</span><span class="sxs-lookup"><span data-stu-id="0ac92-129">Enter a computer name or a session object, such as the output of a **New-CimSession** or **Get-CimSession** cmdlet.</span></span>

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

### <span data-ttu-id="0ac92-130">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="0ac92-130">-ThrottleLimit</span></span>
<span data-ttu-id="0ac92-131">Указание максимального количества одновременных операций, которые можно выполнять для запуска командлета.</span><span class="sxs-lookup"><span data-stu-id="0ac92-131">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>

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

### <span data-ttu-id="0ac92-132">-Confirm</span><span class="sxs-lookup"><span data-stu-id="0ac92-132">-Confirm</span></span>
<span data-ttu-id="0ac92-133">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="0ac92-133">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="0ac92-134">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="0ac92-134">-WhatIf</span></span>
<span data-ttu-id="0ac92-135">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="0ac92-135">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="0ac92-136">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="0ac92-136">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="0ac92-137">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="0ac92-137">CommonParameters</span></span>
<span data-ttu-id="0ac92-138">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0ac92-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0ac92-139">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0ac92-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0ac92-140">Входные данные</span><span class="sxs-lookup"><span data-stu-id="0ac92-140">INPUTS</span></span>

## <span data-ttu-id="0ac92-141">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="0ac92-141">OUTPUTS</span></span>

## <span data-ttu-id="0ac92-142">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="0ac92-142">NOTES</span></span>

## <span data-ttu-id="0ac92-143">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="0ac92-143">RELATED LINKS</span></span>

[<span data-ttu-id="0ac92-144">Обзор Windows PowerShell Desired State Configuration</span><span class="sxs-lookup"><span data-stu-id="0ac92-144">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="0ac92-145">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="0ac92-145">Get-DscConfiguration</span></span>](Get-DscConfiguration.md)

[<span data-ttu-id="0ac92-146">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="0ac92-146">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)

[<span data-ttu-id="0ac92-147">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="0ac92-147">Start-DscConfiguration</span></span>](Start-DscConfiguration.md)

[<span data-ttu-id="0ac92-148">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="0ac92-148">Test-DscConfiguration</span></span>](Test-DscConfiguration.md)
