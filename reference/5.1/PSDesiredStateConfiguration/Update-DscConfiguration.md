---
external help file: Microsoft.Windows.DSC.CoreConfProviders.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/update-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-DscConfiguration
ms.openlocfilehash: 13365902ab317a3daa41b9a951d5e2fa6e4f1b37
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227450"
---
# <span data-ttu-id="35370-103">Update-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="35370-103">Update-DscConfiguration</span></span>

## <span data-ttu-id="35370-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="35370-104">SYNOPSIS</span></span>
<span data-ttu-id="35370-105">Проверяет наличие обновленной конфигурации опрашивающего сервера и применяет его.</span><span class="sxs-lookup"><span data-stu-id="35370-105">Checks the pull server for an updated configuration and applies it.</span></span>

## <span data-ttu-id="35370-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="35370-106">SYNTAX</span></span>

### <span data-ttu-id="35370-107">Компутернамесет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="35370-107">ComputerNameSet (Default)</span></span>

```
Update-DscConfiguration [-Wait] [-JobName <String>] [[-ComputerName] <String[]>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="35370-108">Цимсессионсет</span><span class="sxs-lookup"><span data-stu-id="35370-108">CimSessionSet</span></span>

```
Update-DscConfiguration [-Wait] [-JobName <String>] [-ThrottleLimit <Int32>] -CimSession <CimSession[]>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="35370-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="35370-109">DESCRIPTION</span></span>
<span data-ttu-id="35370-110">`Update-DscConfiguration`Командлет подключается к опрашивающем серверу, загружает конфигурацию, если она отличается от текущей на узле, а затем применяет конфигурацию к компьютеру.</span><span class="sxs-lookup"><span data-stu-id="35370-110">The `Update-DscConfiguration` cmdlet connects to a pull server, downloads the configuration if it differs from what is current on the node, and then applies the configuration to the computer.</span></span>

<span data-ttu-id="35370-111">Этот командлет доступен только в составе [накопительного пакета обновления за ноябрь 2014 для Windows RT 8,1, Windows 8.1 и Windows Server 2012 R2](https://support.microsoft.com/kb/3000850) из библиотеки служба поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="35370-111">This cmdlet is available only as part of the [November 2014 update rollup for Windows RT 8.1, Windows 8.1, and Windows Server 2012 R2](https://support.microsoft.com/kb/3000850) from the Microsoft Support library.</span></span>

## <span data-ttu-id="35370-112">Примеры</span><span class="sxs-lookup"><span data-stu-id="35370-112">EXAMPLES</span></span>

### <span data-ttu-id="35370-113">Пример 1. Обновление конфигурации</span><span class="sxs-lookup"><span data-stu-id="35370-113">Example 1: Update a configuration</span></span>

```
PS C:\> Update-DscConfiguration -Wait -Verbose
```

<span data-ttu-id="35370-114">После выполнения этой команды сервер будет подключаться к зарегистрированной опрашивающей службе, загрузить последнюю назначенную конфигурацию и применить ее.</span><span class="sxs-lookup"><span data-stu-id="35370-114">After running this command, the server will connect to the registered pull service, download the latest assigned configuration, and then apply it.</span></span>
<span data-ttu-id="35370-115">Параметры-Wait и-verbose являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="35370-115">The -Wait and -Verbose parameters are optional.</span></span>
<span data-ttu-id="35370-116">При работе в интерактивном режиме эти параметры позволяют оставить отзыв о ходе выполнения и успехе или сбое при применении конфигурации.</span><span class="sxs-lookup"><span data-stu-id="35370-116">When working interactively, these parameters combined enable real-time feedback about progress and success or failure when applying the configuration.</span></span>

### <span data-ttu-id="35370-117">Пример 2. Обновление конфигурации путем подключения через сеанс CIM</span><span class="sxs-lookup"><span data-stu-id="35370-117">Example 2: Update a configuration by connecting over a CIM session</span></span>

```
PS C:\> $Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
PS C:\> Update-DscConfiguration -CimSession $Session -Wait
```

<span data-ttu-id="35370-118">Первая команда создает сеанс CIM, используя командлет **New-CimSession** , а затем сохраняет объект **CimSession** в переменной $Session.</span><span class="sxs-lookup"><span data-stu-id="35370-118">The first command creates a CIM session by using the **New-CimSession** cmdlet, and then stores the **CimSession** object in the $Session variable.</span></span>
<span data-ttu-id="35370-119">Команда запрашивает пароль.</span><span class="sxs-lookup"><span data-stu-id="35370-119">The command prompts you for a password.</span></span>
<span data-ttu-id="35370-120">Для получения дополнительных сведений введите `Get-Help New-CimSession`.</span><span class="sxs-lookup"><span data-stu-id="35370-120">For more information, type `Get-Help New-CimSession`.</span></span>

<span data-ttu-id="35370-121">Вторая команда обновляет компьютер, указанный в параметре **CimSession** , который хранится в $Session.</span><span class="sxs-lookup"><span data-stu-id="35370-121">The second command updates the computer specified in the **CimSession** stored in $Session.</span></span>
<span data-ttu-id="35370-122">Команда задает параметр *Wait* .</span><span class="sxs-lookup"><span data-stu-id="35370-122">The command specifies the *Wait* parameter.</span></span>
<span data-ttu-id="35370-123">Консоль не принимает дополнительные команды до тех пор, пока текущая команда не будет завершена.</span><span class="sxs-lookup"><span data-stu-id="35370-123">The console does not accept additional commands until the current command finishes.</span></span>

## <span data-ttu-id="35370-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="35370-124">PARAMETERS</span></span>

### <span data-ttu-id="35370-125">-CimSession</span><span class="sxs-lookup"><span data-stu-id="35370-125">-CimSession</span></span>
<span data-ttu-id="35370-126">Запуск командлета в удаленном сеансе или на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="35370-126">Runs the cmdlet in a remote session or on a remote computer.</span></span>
<span data-ttu-id="35370-127">Введите имя компьютера или объект сеанса, например выходные данные командлета [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) или [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) .</span><span class="sxs-lookup"><span data-stu-id="35370-127">Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet.</span></span>
<span data-ttu-id="35370-128">Сеанс по умолчанию — текущий сеанс на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="35370-128">The default is the current session on the local computer.</span></span>

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

### <span data-ttu-id="35370-129">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="35370-129">-ComputerName</span></span>
<span data-ttu-id="35370-130">Указывает массив имен компьютеров.</span><span class="sxs-lookup"><span data-stu-id="35370-130">Specifies an array of computer names.</span></span>
<span data-ttu-id="35370-131">Командлет применяет параметры конфигурации к компьютерам, указанному этим параметром.</span><span class="sxs-lookup"><span data-stu-id="35370-131">The cmdlet applies the configuration settings to the computers that this parameter specifies.</span></span>

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

### <span data-ttu-id="35370-132">-Credential</span><span class="sxs-lookup"><span data-stu-id="35370-132">-Credential</span></span>
<span data-ttu-id="35370-133">Указывает имя пользователя и пароль как объект **PSCredential** для целевого компьютера.</span><span class="sxs-lookup"><span data-stu-id="35370-133">Specifies a user name and password, as a **PSCredential** object, for the target computer.</span></span>
<span data-ttu-id="35370-134">Чтобы получить объект **PSCredential** , используйте командлет Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="35370-134">To obtain a **PSCredential** object, use the Get-Credential cmdlet.</span></span>
<span data-ttu-id="35370-135">Для получения дополнительных сведений введите `Get-Help Get-Credential`.</span><span class="sxs-lookup"><span data-stu-id="35370-135">For more information, type `Get-Help Get-Credential`.</span></span>

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

### <span data-ttu-id="35370-136">-JobName</span><span class="sxs-lookup"><span data-stu-id="35370-136">-JobName</span></span>
<span data-ttu-id="35370-137">Задает понятное имя для задания.</span><span class="sxs-lookup"><span data-stu-id="35370-137">Specifies a friendly name for a job.</span></span>
<span data-ttu-id="35370-138">Если указать этот параметр, командлет выполняется как задание и возвращает объект **Job** .</span><span class="sxs-lookup"><span data-stu-id="35370-138">If you specify this parameter, the cmdlet runs as a job, and it returns a **Job** object.</span></span>

<span data-ttu-id="35370-139">По умолчанию Windows PowerShell назначает имя Жобн, где N — целое число.</span><span class="sxs-lookup"><span data-stu-id="35370-139">By default, Windows PowerShell assigns the name JobN where N is an integer.</span></span>

<span data-ttu-id="35370-140">Если параметр *Wait* указан, не указывайте этот параметр.</span><span class="sxs-lookup"><span data-stu-id="35370-140">If you specify the *Wait* parameter, do not specify this parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="35370-141">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="35370-141">-ThrottleLimit</span></span>
<span data-ttu-id="35370-142">Указание максимального количества одновременных операций, которые можно выполнять для запуска командлета.</span><span class="sxs-lookup"><span data-stu-id="35370-142">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>
<span data-ttu-id="35370-143">Если этот параметр пропущен или указано значение `0` , Windows PowerShell вычисляет оптимальное ограничение регулирования для командлета на основе числа командлетов CIM, выполняемых на компьютере.</span><span class="sxs-lookup"><span data-stu-id="35370-143">If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.</span></span>
<span data-ttu-id="35370-144">Предел регулирования применим только к текущему командлету, а не к сеансу или компьютеру.</span><span class="sxs-lookup"><span data-stu-id="35370-144">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="35370-145">-Wait</span><span class="sxs-lookup"><span data-stu-id="35370-145">-Wait</span></span>
<span data-ttu-id="35370-146">Указывает, что командлет блокирует консоль до тех пор, пока не завершит все задачи настройки.</span><span class="sxs-lookup"><span data-stu-id="35370-146">Indicates that the cmdlet blocks the console until it finishes all configuration tasks.</span></span>

<span data-ttu-id="35370-147">Если этот параметр указан, не указывайте параметр *JobName* .</span><span class="sxs-lookup"><span data-stu-id="35370-147">If you specify this parameter, do not specify the *JobName* parameter.</span></span>

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

### <span data-ttu-id="35370-148">-Confirm</span><span class="sxs-lookup"><span data-stu-id="35370-148">-Confirm</span></span>
<span data-ttu-id="35370-149">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="35370-149">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="35370-150">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="35370-150">-WhatIf</span></span>
<span data-ttu-id="35370-151">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="35370-151">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="35370-152">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="35370-152">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="35370-153">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="35370-153">CommonParameters</span></span>
<span data-ttu-id="35370-154">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="35370-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="35370-155">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="35370-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="35370-156">Входные данные</span><span class="sxs-lookup"><span data-stu-id="35370-156">INPUTS</span></span>

## <span data-ttu-id="35370-157">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="35370-157">OUTPUTS</span></span>

## <span data-ttu-id="35370-158">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="35370-158">NOTES</span></span>

## <span data-ttu-id="35370-159">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="35370-159">RELATED LINKS</span></span>

[<span data-ttu-id="35370-160">Обзор Windows PowerShell Desired State Configuration</span><span class="sxs-lookup"><span data-stu-id="35370-160">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="35370-161">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="35370-161">Get-DscConfiguration</span></span>](Get-DscConfiguration.md)

[<span data-ttu-id="35370-162">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="35370-162">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)

[<span data-ttu-id="35370-163">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="35370-163">Restore-DscConfiguration</span></span>](Restore-DscConfiguration.md)

[<span data-ttu-id="35370-164">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="35370-164">Start-DscConfiguration</span></span>](Start-DscConfiguration.md)

[<span data-ttu-id="35370-165">Stop-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="35370-165">Stop-DscConfiguration</span></span>](Stop-DscConfiguration.md)

[<span data-ttu-id="35370-166">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="35370-166">Test-DscConfiguration</span></span>](Test-DscConfiguration.md)
