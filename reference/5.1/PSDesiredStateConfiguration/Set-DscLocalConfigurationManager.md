---
external help file: Microsoft.Windows.DSC.CoreConfProviders.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 04/29/2020
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/set-dsclocalconfigurationmanager?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DscLocalConfigurationManager
ms.openlocfilehash: 0d35aa56a52f0e6c17abd0e7b2707869e780324c
ms.sourcegitcommit: 0d4d3e47f6979876550591f62061096e7a568f7e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2020
ms.locfileid: "93229673"
---
# <span data-ttu-id="0d7d4-103">Set-DscLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="0d7d4-103">Set-DscLocalConfigurationManager</span></span>

## <span data-ttu-id="0d7d4-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="0d7d4-104">SYNOPSIS</span></span>

<span data-ttu-id="0d7d4-105">Применяет локальные параметры Configuration Manager (LCM) к узлам.</span><span class="sxs-lookup"><span data-stu-id="0d7d4-105">Applies Local Configuration Manager (LCM) settings to nodes.</span></span>

## <span data-ttu-id="0d7d4-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0d7d4-106">SYNTAX</span></span>

### <span data-ttu-id="0d7d4-107">Компутернамесет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="0d7d4-107">ComputerNameSet (Default)</span></span>

```
Set-DscLocalConfigurationManager [-Path] <String> [-Force] [[-ComputerName] <String[]>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0d7d4-108">Цимсессионсет</span><span class="sxs-lookup"><span data-stu-id="0d7d4-108">CimSessionSet</span></span>

```
Set-DscLocalConfigurationManager [-Path] <String> [-Force] [-ThrottleLimit <Int32>] -CimSession <CimSession[]>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="0d7d4-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0d7d4-109">DESCRIPTION</span></span>

<span data-ttu-id="0d7d4-110">`Set-DscLocalConfigurationManager`Командлет применяет параметры LCM или мета-конфигурацию к узлам.</span><span class="sxs-lookup"><span data-stu-id="0d7d4-110">The `Set-DscLocalConfigurationManager` cmdlet applies LCM settings, or meta-configuration, to nodes.</span></span> <span data-ttu-id="0d7d4-111">Укажите компьютеры, выбрав имена компьютеров или используя сеансы модели CIM.</span><span class="sxs-lookup"><span data-stu-id="0d7d4-111">Specify computers by specifying computer names or by using Common Information Model (CIM) sessions.</span></span> <span data-ttu-id="0d7d4-112">Если целевой компьютер не указан, командлет применяет параметры к локальному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="0d7d4-112">If you do not specify a target computer, the cmdlet applies settings to the local computer.</span></span>

## <span data-ttu-id="0d7d4-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="0d7d4-113">EXAMPLES</span></span>

### <span data-ttu-id="0d7d4-114">Пример 1. применение параметров LCM</span><span class="sxs-lookup"><span data-stu-id="0d7d4-114">Example 1: Apply LCM settings</span></span>

```
Set-DscLocalConfigurationManager -Path "C:\DSC\Configurations\"
```

<span data-ttu-id="0d7d4-115">Эта команда применяет параметры LCM `C:\DSC\Configurations\` к целевым узлам.</span><span class="sxs-lookup"><span data-stu-id="0d7d4-115">This command applies the LCM settings from `C:\DSC\Configurations\` to the targeted nodes.</span></span> <span data-ttu-id="0d7d4-116">После получения параметров LCM обрабатывает их.</span><span class="sxs-lookup"><span data-stu-id="0d7d4-116">After receiving the settings, LCM processes them.</span></span>

> [!WARNING]
> <span data-ttu-id="0d7d4-117">Если для одного и того же компьютера, хранящегося в указанной папке, существует несколько мета-MOF, будет применен только первый объект meta MOF.</span><span class="sxs-lookup"><span data-stu-id="0d7d4-117">If there are multiple meta mofs for the same computer stored in the specified folder, only the first meta mof will be applied.</span></span>

### <span data-ttu-id="0d7d4-118">Пример 2. применение параметров LCM с помощью сеанса CIM</span><span class="sxs-lookup"><span data-stu-id="0d7d4-118">Example 2: Apply LCM settings by using a CIM session</span></span>

```
$Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
Set-DscLocalConfigurationManager -Path "C:\DSC\Configurations\" -CimSession $Session
```

<span data-ttu-id="0d7d4-119">Этот пример применяет параметры LCM к компьютеру и применяет параметры.</span><span class="sxs-lookup"><span data-stu-id="0d7d4-119">This example applies LCM settings to a computer and applies the settings.</span></span> <span data-ttu-id="0d7d4-120">Пример создает сеанс CIM для компьютера с именем Server01, чтобы использовать с командлетом.</span><span class="sxs-lookup"><span data-stu-id="0d7d4-120">The example creates a CIM session for a computer named Server01 for use with the cmdlet.</span></span> <span data-ttu-id="0d7d4-121">Кроме того, можно создать массив сеансов CIM для применения командлета к нескольким указанным компьютерам.</span><span class="sxs-lookup"><span data-stu-id="0d7d4-121">Alternatively, create an array of CIM sessions to apply the cmdlet to multiple specified computers.</span></span>

<span data-ttu-id="0d7d4-122">Первая команда создает сеанс CIM с помощью `New-CimSession` командлета, а затем сохраняет объект **CimSession** в `$Session` переменной.</span><span class="sxs-lookup"><span data-stu-id="0d7d4-122">The first command creates a CIM session by using the `New-CimSession` cmdlet, and then stores the **CimSession** object in the `$Session` variable.</span></span> <span data-ttu-id="0d7d4-123">Команда запрашивает пароль.</span><span class="sxs-lookup"><span data-stu-id="0d7d4-123">The command prompts you for a password.</span></span> <span data-ttu-id="0d7d4-124">Для получения дополнительных сведений введите `Get-Help New-CimSession`.</span><span class="sxs-lookup"><span data-stu-id="0d7d4-124">For more information, type `Get-Help New-CimSession`.</span></span>

<span data-ttu-id="0d7d4-125">Вторая команда применяет параметры LCM к целевому узлу с `C:\DSC\Configurations\` компьютера, определяемого объектами **CimSession** , хранящимися в `$Session` переменной.</span><span class="sxs-lookup"><span data-stu-id="0d7d4-125">The second command applies LCM settings for the targeted node from `C:\DSC\Configurations\` to the computer identified by the **CimSession** objects stored in the `$Session` variable.</span></span> <span data-ttu-id="0d7d4-126">В этом примере `$Session` переменная содержит сеанс CIM только для компьютера с именем Server01.</span><span class="sxs-lookup"><span data-stu-id="0d7d4-126">In this example, the `$Session` variable contains a CIM session only for the computer named Server01.</span></span> <span data-ttu-id="0d7d4-127">Команда применяет параметры.</span><span class="sxs-lookup"><span data-stu-id="0d7d4-127">The command applies the settings.</span></span> <span data-ttu-id="0d7d4-128">После получения параметров LCM обрабатывает их.</span><span class="sxs-lookup"><span data-stu-id="0d7d4-128">After receiving the settings, LCM processes them.</span></span>

## <span data-ttu-id="0d7d4-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0d7d4-129">PARAMETERS</span></span>

### <span data-ttu-id="0d7d4-130">-CimSession</span><span class="sxs-lookup"><span data-stu-id="0d7d4-130">-CimSession</span></span>

<span data-ttu-id="0d7d4-131">Запуск командлета в удаленном сеансе или на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="0d7d4-131">Runs the cmdlet in a remote session or on a remote computer.</span></span> <span data-ttu-id="0d7d4-132">Введите имя компьютера или объект сеанса, например выходные данные командлета [New-CimSession](/powershell/module/CimCmdlets/New-CimSession) или [Get-CimSession](/powershell/module/CimCmdlets/Get-CimSession) .</span><span class="sxs-lookup"><span data-stu-id="0d7d4-132">Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/CimCmdlets/New-CimSession) or [Get-CimSession](/powershell/module/CimCmdlets/Get-CimSession) cmdlet.</span></span>
<span data-ttu-id="0d7d4-133">Сеанс по умолчанию — текущий сеанс на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="0d7d4-133">The default is the current session on the local computer.</span></span>

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

### <span data-ttu-id="0d7d4-134">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="0d7d4-134">-ComputerName</span></span>

<span data-ttu-id="0d7d4-135">Указывает массив имен компьютеров.</span><span class="sxs-lookup"><span data-stu-id="0d7d4-135">Specifies an array of computer names.</span></span> <span data-ttu-id="0d7d4-136">Этот параметр позволяет задать для компьютеров с документами мета-конфигурации в параметре **path** значения, указанные в массиве.</span><span class="sxs-lookup"><span data-stu-id="0d7d4-136">This parameter restricts the computers that have meta-configuration documents in the **Path** parameter to those specified in the array.</span></span>

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

### <span data-ttu-id="0d7d4-137">-Credential</span><span class="sxs-lookup"><span data-stu-id="0d7d4-137">-Credential</span></span>

<span data-ttu-id="0d7d4-138">Указывает имя пользователя и пароль как объект **PSCredential** для целевого компьютера.</span><span class="sxs-lookup"><span data-stu-id="0d7d4-138">Specifies a user name and password, as a **PSCredential** object, for the target computer.</span></span> <span data-ttu-id="0d7d4-139">Чтобы получить объект **PSCredential** , используйте командлет Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="0d7d4-139">To obtain a **PSCredential** object, use the Get-Credential cmdlet.</span></span> <span data-ttu-id="0d7d4-140">Для получения дополнительных сведений введите `Get-Help Get-Credential`.</span><span class="sxs-lookup"><span data-stu-id="0d7d4-140">For more information, type `Get-Help Get-Credential`.</span></span>

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

### <span data-ttu-id="0d7d4-141">-Force</span><span class="sxs-lookup"><span data-stu-id="0d7d4-141">-Force</span></span>

<span data-ttu-id="0d7d4-142">Принудительное выполнение команды без запроса на подтверждение пользователем.</span><span class="sxs-lookup"><span data-stu-id="0d7d4-142">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="0d7d4-143">-Path</span><span class="sxs-lookup"><span data-stu-id="0d7d4-143">-Path</span></span>

<span data-ttu-id="0d7d4-144">Указывает путь к файлу папки, которая содержит файлы параметров конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0d7d4-144">Specifies a file path of a folder that contains configuration settings files.</span></span> <span data-ttu-id="0d7d4-145">Командлет публикует и применяет эти параметры LCM к компьютерам, имеющим файлы параметров по указанному пути.</span><span class="sxs-lookup"><span data-stu-id="0d7d4-145">The cmdlet publishes and applies these LCM settings to computers that have settings files in the specified path.</span></span> <span data-ttu-id="0d7d4-146">Каждый целевой узел должен иметь файл параметров следующего формата: `NetBIOS Name.meta.mof` .</span><span class="sxs-lookup"><span data-stu-id="0d7d4-146">Each target node must have a settings file of the following format: `NetBIOS Name.meta.mof`.</span></span>

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

### <span data-ttu-id="0d7d4-147">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="0d7d4-147">-ThrottleLimit</span></span>

<span data-ttu-id="0d7d4-148">Указание максимального количества одновременных операций, которые можно выполнять для запуска командлета.</span><span class="sxs-lookup"><span data-stu-id="0d7d4-148">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span> <span data-ttu-id="0d7d4-149">Если этот параметр пропущен или указано значение `0` , Windows PowerShell вычисляет оптимальное ограничение регулирования для командлета на основе числа командлетов CIM, выполняемых на компьютере.</span><span class="sxs-lookup"><span data-stu-id="0d7d4-149">If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.</span></span> <span data-ttu-id="0d7d4-150">Предел регулирования применим только к текущему командлету, а не к сеансу или компьютеру.</span><span class="sxs-lookup"><span data-stu-id="0d7d4-150">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="0d7d4-151">-Confirm</span><span class="sxs-lookup"><span data-stu-id="0d7d4-151">-Confirm</span></span>

<span data-ttu-id="0d7d4-152">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="0d7d4-152">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="0d7d4-153">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="0d7d4-153">-WhatIf</span></span>

<span data-ttu-id="0d7d4-154">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="0d7d4-154">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="0d7d4-155">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="0d7d4-155">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="0d7d4-156">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="0d7d4-156">CommonParameters</span></span>

<span data-ttu-id="0d7d4-157">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0d7d4-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0d7d4-158">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0d7d4-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0d7d4-159">Входные данные</span><span class="sxs-lookup"><span data-stu-id="0d7d4-159">INPUTS</span></span>

## <span data-ttu-id="0d7d4-160">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="0d7d4-160">OUTPUTS</span></span>

## <span data-ttu-id="0d7d4-161">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="0d7d4-161">NOTES</span></span>

## <span data-ttu-id="0d7d4-162">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="0d7d4-162">RELATED LINKS</span></span>

[<span data-ttu-id="0d7d4-163">Обзор Windows PowerShell Desired State Configuration</span><span class="sxs-lookup"><span data-stu-id="0d7d4-163">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/overview)

[<span data-ttu-id="0d7d4-164">Get-DscLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="0d7d4-164">Get-DscLocalConfigurationManager</span></span>](Get-DscLocalConfigurationManager.md)
