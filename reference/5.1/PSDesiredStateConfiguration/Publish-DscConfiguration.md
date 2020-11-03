---
external help file: Microsoft.Windows.DSC.CoreConfProviders.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/publish-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Publish-DscConfiguration
ms.openlocfilehash: 139de2bfdb88c443e7bc48d36e37e95644556bf5
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228317"
---
# <span data-ttu-id="0b6d9-103">Publish-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="0b6d9-103">Publish-DscConfiguration</span></span>

## <span data-ttu-id="0b6d9-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="0b6d9-104">SYNOPSIS</span></span>
<span data-ttu-id="0b6d9-105">Публикует конфигурацию DSC для набора компьютеров.</span><span class="sxs-lookup"><span data-stu-id="0b6d9-105">Publishes a DSC configuration to a set of computers.</span></span>

## <span data-ttu-id="0b6d9-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0b6d9-106">SYNTAX</span></span>

### <span data-ttu-id="0b6d9-107">Компутернамесет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="0b6d9-107">ComputerNameSet (Default)</span></span>

```
Publish-DscConfiguration [-Path] <String> [-Force] [[-ComputerName] <String[]>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0b6d9-108">Цимсессионсет</span><span class="sxs-lookup"><span data-stu-id="0b6d9-108">CimSessionSet</span></span>

```
Publish-DscConfiguration [-Path] <String> [-Force] [-ThrottleLimit <Int32>] -CimSession <CimSession[]>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="0b6d9-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0b6d9-109">DESCRIPTION</span></span>
<span data-ttu-id="0b6d9-110">Командлет **Publish-DscConfiguration** публикует документ конфигурации Windows PowerShell Desired State Configuration (DSC) на наборе компьютеров.</span><span class="sxs-lookup"><span data-stu-id="0b6d9-110">The **Publish-DscConfiguration** cmdlet publishes a Windows PowerShell Desired State Configuration (DSC) configuration document on set of computers.</span></span>
<span data-ttu-id="0b6d9-111">Этот командлет не применяет конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="0b6d9-111">This cmdlet does not apply the configuration.</span></span>
<span data-ttu-id="0b6d9-112">Конфигурации применяются либо командлетом Start-DscConfiguration, если он используется с параметром *UseExisting* , либо когда ядро DSC выполняет цикл согласованности.</span><span class="sxs-lookup"><span data-stu-id="0b6d9-112">Configurations are applied by either the Start-DscConfiguration cmdlet when it is used with the *UseExisting* parameter or when the DSC engine runs its consistency cycle.</span></span>
<span data-ttu-id="0b6d9-113">Модуль DSC также называется локальным Configuration Manager (LCM).</span><span class="sxs-lookup"><span data-stu-id="0b6d9-113">The DSC engine is also known as the Local Configuration Manager (LCM).</span></span>

<span data-ttu-id="0b6d9-114">Этот командлет особенно полезен при доставке фрагментов нескольких документов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0b6d9-114">This cmdlet is especially useful when fragments of multiple configuration documents are delivered.</span></span>
<span data-ttu-id="0b6d9-115">При доставке нескольких фрагментов документов конфигурации они перезапишут старые фрагменты документа конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0b6d9-115">When multiple configuration documents fragments are delivered, they overwrite the older configuration document fragments.</span></span>

## <span data-ttu-id="0b6d9-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="0b6d9-116">EXAMPLES</span></span>

### <span data-ttu-id="0b6d9-117">Пример 1. Публикация конфигурации на удаленном компьютере</span><span class="sxs-lookup"><span data-stu-id="0b6d9-117">Example 1: Publish a configuration to a remote computer</span></span>

```
PS C:\> Publish-DscConfiguration -Path '$home\WebServer' -ComputerName "ContosoWebServer" -Credential (get-credential Contoso\webadministrator)
```

<span data-ttu-id="0b6d9-118">Эта команда публикует конфигурацию на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="0b6d9-118">This command publishes a configuration to a remote computer.</span></span>
<span data-ttu-id="0b6d9-119">Пользователь, запускающий командлет, должен быть администратором на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="0b6d9-119">The user who runs the cmdlet should be administrator on the remote computer.</span></span>

## <span data-ttu-id="0b6d9-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0b6d9-120">PARAMETERS</span></span>

### <span data-ttu-id="0b6d9-121">-CimSession</span><span class="sxs-lookup"><span data-stu-id="0b6d9-121">-CimSession</span></span>
<span data-ttu-id="0b6d9-122">Запуск командлета в удаленном сеансе или на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="0b6d9-122">Runs the cmdlet in a remote session or on a remote computer.</span></span>
<span data-ttu-id="0b6d9-123">Введите имя компьютера или объект сеанса, например выходные данные командлета [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) или [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) .</span><span class="sxs-lookup"><span data-stu-id="0b6d9-123">Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet.</span></span>
<span data-ttu-id="0b6d9-124">Сеанс по умолчанию — текущий сеанс на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="0b6d9-124">The default is the current session on the local computer.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: CimSessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="0b6d9-125">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="0b6d9-125">-ComputerName</span></span>
<span data-ttu-id="0b6d9-126">Указывает один или несколько компьютеров, на которых этот командлет публикует конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="0b6d9-126">Specifies one or more computers on which this cmdlet publishes the configuration.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerNameSet
Aliases: CN, ServerName

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="0b6d9-127">-Credential</span><span class="sxs-lookup"><span data-stu-id="0b6d9-127">-Credential</span></span>
<span data-ttu-id="0b6d9-128">Указывает учетные данные, используемые для доступа к целевому устройству.</span><span class="sxs-lookup"><span data-stu-id="0b6d9-128">Specifies credentials that are used to access the target device.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerNameSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0b6d9-129">-Force</span><span class="sxs-lookup"><span data-stu-id="0b6d9-129">-Force</span></span>
<span data-ttu-id="0b6d9-130">Принудительное завершение командлета.</span><span class="sxs-lookup"><span data-stu-id="0b6d9-130">Forces the cmdlet to finish.</span></span>
<span data-ttu-id="0b6d9-131">Если для локального режима обновления Configuration Manager задано значение PULL, использование этого параметра приводит к изменению его на ПРИНУДИТЕЛЬную отправку и включает публикацию конфигурации DSC.</span><span class="sxs-lookup"><span data-stu-id="0b6d9-131">If the Local Configuration Manager refresh mode is set to PULL, usage of this parameter changes it to PUSH and enables publication of the DSC configuration.</span></span>
<span data-ttu-id="0b6d9-132">Кроме того, при наличии ожидающей конфигурации DSC использование этого параметра перезаписывает конфигурацию, ожидающую выполнения.</span><span class="sxs-lookup"><span data-stu-id="0b6d9-132">Also, if a pending DSC configuration exists, usage of this parameter overwrites that pending configuration.</span></span>

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

### <span data-ttu-id="0b6d9-133">-Path</span><span class="sxs-lookup"><span data-stu-id="0b6d9-133">-Path</span></span>
<span data-ttu-id="0b6d9-134">Указывает путь, содержащий конфигурации для публикации на конечных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="0b6d9-134">Specifies a path that contains configurations to publish to target computers.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0b6d9-135">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="0b6d9-135">-ThrottleLimit</span></span>
<span data-ttu-id="0b6d9-136">Указание максимального количества одновременных операций, которые можно выполнять для запуска командлета.</span><span class="sxs-lookup"><span data-stu-id="0b6d9-136">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>
<span data-ttu-id="0b6d9-137">Если этот параметр пропущен или указано значение `0` , Windows PowerShell вычисляет оптимальное ограничение регулирования для командлета на основе числа командлетов CIM, выполняемых на компьютере.</span><span class="sxs-lookup"><span data-stu-id="0b6d9-137">If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.</span></span>
<span data-ttu-id="0b6d9-138">Предел регулирования применим только к текущему командлету, а не к сеансу или компьютеру.</span><span class="sxs-lookup"><span data-stu-id="0b6d9-138">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="0b6d9-139">-Confirm</span><span class="sxs-lookup"><span data-stu-id="0b6d9-139">-Confirm</span></span>
<span data-ttu-id="0b6d9-140">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="0b6d9-140">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="0b6d9-141">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="0b6d9-141">-WhatIf</span></span>
<span data-ttu-id="0b6d9-142">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="0b6d9-142">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="0b6d9-143">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="0b6d9-143">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="0b6d9-144">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="0b6d9-144">CommonParameters</span></span>
<span data-ttu-id="0b6d9-145">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0b6d9-145">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0b6d9-146">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0b6d9-146">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0b6d9-147">Входные данные</span><span class="sxs-lookup"><span data-stu-id="0b6d9-147">INPUTS</span></span>

## <span data-ttu-id="0b6d9-148">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="0b6d9-148">OUTPUTS</span></span>

## <span data-ttu-id="0b6d9-149">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="0b6d9-149">NOTES</span></span>

## <span data-ttu-id="0b6d9-150">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="0b6d9-150">RELATED LINKS</span></span>

[<span data-ttu-id="0b6d9-151">Обзор Windows PowerShell Desired State Configuration</span><span class="sxs-lookup"><span data-stu-id="0b6d9-151">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="0b6d9-152">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="0b6d9-152">Get-DscConfiguration</span></span>](Get-DscConfiguration.md)

[<span data-ttu-id="0b6d9-153">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="0b6d9-153">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)

[<span data-ttu-id="0b6d9-154">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="0b6d9-154">Restore-DscConfiguration</span></span>](Restore-DscConfiguration.md)

[<span data-ttu-id="0b6d9-155">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="0b6d9-155">Start-DscConfiguration</span></span>](Start-DscConfiguration.md)

[<span data-ttu-id="0b6d9-156">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="0b6d9-156">Test-DscConfiguration</span></span>](Test-DscConfiguration.md)
