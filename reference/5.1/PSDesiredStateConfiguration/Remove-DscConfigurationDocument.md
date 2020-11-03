---
external help file: Remove-DscConfigurationDocument.cdxml-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/remove-dscconfigurationdocument?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-DscConfigurationDocument
ms.openlocfilehash: d3e9b15dfeea94921503247adc08b291eed9d7d7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228314"
---
# <span data-ttu-id="a0b3b-103">Remove-DscConfigurationDocument</span><span class="sxs-lookup"><span data-stu-id="a0b3b-103">Remove-DscConfigurationDocument</span></span>

## <span data-ttu-id="a0b3b-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="a0b3b-104">SYNOPSIS</span></span>
<span data-ttu-id="a0b3b-105">Удаляет документ конфигурации из хранилища конфигураций DSC.</span><span class="sxs-lookup"><span data-stu-id="a0b3b-105">Removes a configuration document from the DSC configuration store.</span></span>

## <span data-ttu-id="a0b3b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a0b3b-106">SYNTAX</span></span>

```
Remove-DscConfigurationDocument -Stage <Stage> [-Force] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="a0b3b-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a0b3b-107">DESCRIPTION</span></span>
<span data-ttu-id="a0b3b-108">`Remove-DscConfigurationDocument`Командлет удаляет документ конфигурации (MOF-файл) из хранилища конфигурации Desired State Configuration (DSC) Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a0b3b-108">The `Remove-DscConfigurationDocument` cmdlet removes a configuration document (.mof file) from the Windows PowerShell Desired State Configuration (DSC) configuration store.</span></span>
<span data-ttu-id="a0b3b-109">Во время настройки `Start-DscConfiguration` командлет копирует MOF-файл в папку на целевом компьютере.</span><span class="sxs-lookup"><span data-stu-id="a0b3b-109">During configuration, the `Start-DscConfiguration` cmdlet copies a .mof file to a folder on the target computer.</span></span>
<span data-ttu-id="a0b3b-110">Этот командлет удаляет этот документ конфигурации и выполняет дополнительную очистку.</span><span class="sxs-lookup"><span data-stu-id="a0b3b-110">This cmdlet removes that configuration document and does additional cleanup.</span></span>

<span data-ttu-id="a0b3b-111">Этот командлет доступен только в составе [накопительного пакета обновления за ноябрь 2014 для Windows RT 8,1, Windows 8.1 и Windows Server 2012 R2](https://support.microsoft.com/kb/3000850) из библиотеки служба поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a0b3b-111">This cmdlet is available only as part of the [November 2014 update rollup for Windows RT 8.1, Windows 8.1, and Windows Server 2012 R2](https://support.microsoft.com/kb/3000850) from the Microsoft Support library.</span></span>

## <span data-ttu-id="a0b3b-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="a0b3b-112">EXAMPLES</span></span>

### <span data-ttu-id="a0b3b-113">Пример 1. Удаление текущего документа конфигурации</span><span class="sxs-lookup"><span data-stu-id="a0b3b-113">Example 1: Remove the current configuration document</span></span>

```
PS C:\> $Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
PS C:\> Remove-DscConfigurationDocument -Stage Current -CimSession $Session
```

<span data-ttu-id="a0b3b-114">Первая команда создает сеанс CIM, используя командлет **New-CimSession** , а затем сохраняет объект **CimSession** в переменной $Session.</span><span class="sxs-lookup"><span data-stu-id="a0b3b-114">The first command creates a CIM session by using the **New-CimSession** cmdlet, and then stores the **CimSession** object in the $Session variable.</span></span>
<span data-ttu-id="a0b3b-115">Команда запрашивает пароль.</span><span class="sxs-lookup"><span data-stu-id="a0b3b-115">The command prompts you for a password.</span></span>
<span data-ttu-id="a0b3b-116">Для получения дополнительных сведений введите `Get-Help New-CimSession`.</span><span class="sxs-lookup"><span data-stu-id="a0b3b-116">For more information, type `Get-Help New-CimSession`.</span></span>

<span data-ttu-id="a0b3b-117">Вторая команда удаляет текущий документ конфигурации для компьютера, указанного в параметре **CimSession** , хранящегося в $Session.</span><span class="sxs-lookup"><span data-stu-id="a0b3b-117">The second command removes the current configuration document for the computer specified in the **CimSession** stored in $Session.</span></span>

## <span data-ttu-id="a0b3b-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a0b3b-118">PARAMETERS</span></span>

### <span data-ttu-id="a0b3b-119">-AsJob</span><span class="sxs-lookup"><span data-stu-id="a0b3b-119">-AsJob</span></span>
<span data-ttu-id="a0b3b-120">Указывает, что этот командлет выполняет команду как фоновое задание.</span><span class="sxs-lookup"><span data-stu-id="a0b3b-120">Indicates that this cmdlet runs the command as a background job.</span></span>

<span data-ttu-id="a0b3b-121">Если указать параметр *AsJob* , команда возвращает объект, представляющий задание, а затем появляется командная строка.</span><span class="sxs-lookup"><span data-stu-id="a0b3b-121">If you specify the *AsJob* parameter, the command returns an object that represents the job, and then displays the command prompt.</span></span>
<span data-ttu-id="a0b3b-122">Вы можете продолжить работу в рамках данного сеанса, пока задание не будет завершено.</span><span class="sxs-lookup"><span data-stu-id="a0b3b-122">You can continue to work in the session until the job finishes.</span></span>
<span data-ttu-id="a0b3b-123">Задание создается на локальном компьютере, а результаты с удаленных компьютеров автоматически возвращаются на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="a0b3b-123">The job is created on the local computer and the results from remote computers are automatically returned to the local computer.</span></span>
<span data-ttu-id="a0b3b-124">Для управления заданием используйте командлеты Job.</span><span class="sxs-lookup"><span data-stu-id="a0b3b-124">To manage the job, use the Job cmdlets.</span></span>
<span data-ttu-id="a0b3b-125">Чтобы получить результаты задания, используйте командлет Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="a0b3b-125">To get the job results, use the Receive-Job cmdlet.</span></span>

<span data-ttu-id="a0b3b-126">Чтобы использовать этот параметр, локальный и удаленный компьютеры должны быть настроены для удаленного взаимодействия, а в Windows Vista и более поздних версиях операционной системы Windows необходимо также запустить Windows PowerShell от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="a0b3b-126">To use this parameter, the local and remote computers must be configured for remoting, and on Windows Vista and later versions of the Windows operating system, you must open Windows PowerShell with the Run as administrator option.</span></span>
<span data-ttu-id="a0b3b-127">Дополнительные сведения см. в разделе [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0b3b-127">For more information, see [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).</span></span>

<span data-ttu-id="a0b3b-128">Дополнительные сведения о фоновых заданиях Windows PowerShell см. в разделах [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) и [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md).</span><span class="sxs-lookup"><span data-stu-id="a0b3b-128">For more information about Windows PowerShell background jobs, see [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) and [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md).</span></span>

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

### <span data-ttu-id="a0b3b-129">-CimSession</span><span class="sxs-lookup"><span data-stu-id="a0b3b-129">-CimSession</span></span>
<span data-ttu-id="a0b3b-130">Запуск командлета в удаленном сеансе или на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a0b3b-130">Runs the cmdlet in a remote session or on a remote computer.</span></span>
<span data-ttu-id="a0b3b-131">Введите имя компьютера или объект сеанса, например выходные данные командлета **New-CimSession** или **Get-CimSession** .</span><span class="sxs-lookup"><span data-stu-id="a0b3b-131">Enter a computer name or a session object, such as the output of a **New-CimSession** or **Get-CimSession** cmdlet.</span></span>

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

### <span data-ttu-id="a0b3b-132">-Force</span><span class="sxs-lookup"><span data-stu-id="a0b3b-132">-Force</span></span>
<span data-ttu-id="a0b3b-133">Указывает, что этот командлет останавливает выполняющееся задание конфигурации перед удалением документа конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a0b3b-133">Indicates that this cmdlet stops the running configuration job before it removes the configuration document.</span></span>
<span data-ttu-id="a0b3b-134">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="a0b3b-134">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="a0b3b-135">— Этап</span><span class="sxs-lookup"><span data-stu-id="a0b3b-135">-Stage</span></span>
<span data-ttu-id="a0b3b-136">Указывает, какой документ конфигурации необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="a0b3b-136">Specifies which configuration document to remove.</span></span>
<span data-ttu-id="a0b3b-137">Можно указать несколько документов.</span><span class="sxs-lookup"><span data-stu-id="a0b3b-137">You can specify multiple documents.</span></span>
<span data-ttu-id="a0b3b-138">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="a0b3b-138">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="a0b3b-139">Текущий.</span><span class="sxs-lookup"><span data-stu-id="a0b3b-139">Current.</span></span>
<span data-ttu-id="a0b3b-140">Удалите документ конфигурации, описывающий текущее состояние системы.</span><span class="sxs-lookup"><span data-stu-id="a0b3b-140">Remove the configuration document that describes the current state of the system.</span></span>
- <span data-ttu-id="a0b3b-141">Ожидание.</span><span class="sxs-lookup"><span data-stu-id="a0b3b-141">Pending.</span></span>
<span data-ttu-id="a0b3b-142">Удалите документ конфигурации, описывающий состояние ожидания системы.</span><span class="sxs-lookup"><span data-stu-id="a0b3b-142">Remove the configuration document that describes the pending state of the system.</span></span>
- <span data-ttu-id="a0b3b-143">Прошлом.</span><span class="sxs-lookup"><span data-stu-id="a0b3b-143">Previous.</span></span>
<span data-ttu-id="a0b3b-144">Удалите документ конфигурации, описывающий предыдущее состояние системы.</span><span class="sxs-lookup"><span data-stu-id="a0b3b-144">Remove the configuration document that describes the previous state of the system.</span></span>

```yaml
Type: Microsoft.PowerShell.Cmdletization.GeneratedTypes.RemoveDscConfigurationDocument.Stage
Parameter Sets: (All)
Aliases:
Accepted values: Current, Pending, Previous

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a0b3b-145">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="a0b3b-145">-ThrottleLimit</span></span>
<span data-ttu-id="a0b3b-146">Указание максимального количества одновременных операций, которые можно выполнять для запуска командлета.</span><span class="sxs-lookup"><span data-stu-id="a0b3b-146">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>
<span data-ttu-id="a0b3b-147">Если этот параметр пропущен или указано значение `0` , Windows PowerShell вычисляет оптимальное ограничение регулирования для командлета на основе числа командлетов CIM, выполняемых на компьютере.</span><span class="sxs-lookup"><span data-stu-id="a0b3b-147">If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.</span></span>
<span data-ttu-id="a0b3b-148">Предел регулирования применим только к текущему командлету, а не к сеансу или компьютеру.</span><span class="sxs-lookup"><span data-stu-id="a0b3b-148">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="a0b3b-149">-Confirm</span><span class="sxs-lookup"><span data-stu-id="a0b3b-149">-Confirm</span></span>
<span data-ttu-id="a0b3b-150">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="a0b3b-150">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="a0b3b-151">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="a0b3b-151">-WhatIf</span></span>
<span data-ttu-id="a0b3b-152">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="a0b3b-152">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="a0b3b-153">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="a0b3b-153">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="a0b3b-154">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="a0b3b-154">CommonParameters</span></span>
<span data-ttu-id="a0b3b-155">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a0b3b-155">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a0b3b-156">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a0b3b-156">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a0b3b-157">Входные данные</span><span class="sxs-lookup"><span data-stu-id="a0b3b-157">INPUTS</span></span>

### <span data-ttu-id="a0b3b-158">Нет</span><span class="sxs-lookup"><span data-stu-id="a0b3b-158">None</span></span>

## <span data-ttu-id="a0b3b-159">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="a0b3b-159">OUTPUTS</span></span>

### <span data-ttu-id="a0b3b-160">Нет</span><span class="sxs-lookup"><span data-stu-id="a0b3b-160">None</span></span>

## <span data-ttu-id="a0b3b-161">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="a0b3b-161">NOTES</span></span>

## <span data-ttu-id="a0b3b-162">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="a0b3b-162">RELATED LINKS</span></span>

[<span data-ttu-id="a0b3b-163">Обзор Windows PowerShell Desired State Configuration</span><span class="sxs-lookup"><span data-stu-id="a0b3b-163">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="a0b3b-164">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="a0b3b-164">Get-DscConfiguration</span></span>](Get-DscConfiguration.md)

[<span data-ttu-id="a0b3b-165">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="a0b3b-165">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)
