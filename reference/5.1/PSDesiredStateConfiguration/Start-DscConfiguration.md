---
external help file: Microsoft.Windows.DSC.CoreConfProviders.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/start-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-DscConfiguration
ms.openlocfilehash: c34754aeb7fce99030cf4ddb235e3e7e8161f3eb
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228309"
---
# <span data-ttu-id="0eda7-103">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="0eda7-103">Start-DscConfiguration</span></span>

## <span data-ttu-id="0eda7-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="0eda7-104">SYNOPSIS</span></span>
<span data-ttu-id="0eda7-105">Применяет конфигурацию к узлам.</span><span class="sxs-lookup"><span data-stu-id="0eda7-105">Applies configuration to nodes.</span></span>

## <span data-ttu-id="0eda7-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0eda7-106">SYNTAX</span></span>

### <span data-ttu-id="0eda7-107">Компутернамеандпассет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="0eda7-107">ComputerNameAndPathSet (Default)</span></span>

```
Start-DscConfiguration [-Wait] [-Force] [[-Path] <String>] [[-ComputerName] <String[]>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-JobName <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="0eda7-108">Цимсессионандпассет</span><span class="sxs-lookup"><span data-stu-id="0eda7-108">CimSessionAndPathSet</span></span>

```
Start-DscConfiguration [-Wait] [-Force] [[-Path] <String>] -CimSession <CimSession[]> [-ThrottleLimit <Int32>]
 [-JobName <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0eda7-109">компутернамеандусиксистингсет</span><span class="sxs-lookup"><span data-stu-id="0eda7-109">ComputerNameAndUseExistingSet</span></span>

```
Start-DscConfiguration [-Wait] [-Force] [[-ComputerName] <String[]>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-UseExisting] [-JobName <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0eda7-110">Цимсессионандусиксистингсет</span><span class="sxs-lookup"><span data-stu-id="0eda7-110">CimSessionAndUseExistingSet</span></span>

```
Start-DscConfiguration [-Wait] [-Force] -CimSession <CimSession[]> [-ThrottleLimit <Int32>] [-UseExisting]
 [-JobName <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="0eda7-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0eda7-111">DESCRIPTION</span></span>
<span data-ttu-id="0eda7-112">Командлет **Start-DscConfiguration** применяет конфигурацию к узлам.</span><span class="sxs-lookup"><span data-stu-id="0eda7-112">The **Start-DscConfiguration** cmdlet applies configuration to nodes.</span></span>
<span data-ttu-id="0eda7-113">При использовании с параметром *UseExisting* применяется существующая конфигурация на целевом компьютере.</span><span class="sxs-lookup"><span data-stu-id="0eda7-113">When used with the *UseExisting* parameter, the existing configuration on the target computer is applied.</span></span>
<span data-ttu-id="0eda7-114">Укажите компьютеры, к которым требуется применить конфигурацию, указав имена компьютеров или используя сеансы модель CIM (CIM).</span><span class="sxs-lookup"><span data-stu-id="0eda7-114">Specify which computers that you want to apply configuration to by specifying computer names or by using Common Information Model (CIM) sessions.</span></span>

<span data-ttu-id="0eda7-115">По умолчанию этот командлет создает задание и возвращает объект **Job** .</span><span class="sxs-lookup"><span data-stu-id="0eda7-115">By default, this cmdlet creates a job and returns a **Job** object.</span></span>
<span data-ttu-id="0eda7-116">Для получения дополнительных сведений о фоновых заданиях введите `Get-Help about_Jobs` .</span><span class="sxs-lookup"><span data-stu-id="0eda7-116">For more information about background jobs, type `Get-Help about_Jobs`.</span></span>
<span data-ttu-id="0eda7-117">Чтобы использовать этот командлет в интерактивном режиме, укажите параметр *Wait* .</span><span class="sxs-lookup"><span data-stu-id="0eda7-117">To use this cmdlet interactively, specify the *Wait* parameter.</span></span>

<span data-ttu-id="0eda7-118">Задайте параметр *Verbose* , чтобы посмотреть сведения о действиях командлета при применении параметров конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0eda7-118">Specify the *Verbose* parameter to see details of what the cmdlet does when it applies configuration settings.</span></span>

## <span data-ttu-id="0eda7-119">Примеры</span><span class="sxs-lookup"><span data-stu-id="0eda7-119">EXAMPLES</span></span>

### <span data-ttu-id="0eda7-120">Пример 1. применение параметров конфигурации</span><span class="sxs-lookup"><span data-stu-id="0eda7-120">Example 1: Apply configuration settings</span></span>

```
PS C:\> Start-DscConfiguration -Path "C:\DSC\Configurations\"
```

<span data-ttu-id="0eda7-121">Эта команда применяет параметры конфигурации из каталога C:\DSC\Configurations\ ко всем компьютерам, имеющим параметры в этой папке.</span><span class="sxs-lookup"><span data-stu-id="0eda7-121">This command applies the configuration settings from C:\DSC\Configurations\ to the every computer that has settings in that folder.</span></span>
<span data-ttu-id="0eda7-122">Команда возвращает объекты **Job** для каждого целевого узла, в котором они развернуты.</span><span class="sxs-lookup"><span data-stu-id="0eda7-122">The command returns **Job** objects for each target node deployed to.</span></span>

### <span data-ttu-id="0eda7-123">Пример 2. применение параметров конфигурации и ожидание завершения настройки</span><span class="sxs-lookup"><span data-stu-id="0eda7-123">Example 2: Apply configuration settings and wait for configuration to complete</span></span>

```
PS C:\> Start-DscConfiguration -Path "C:\DSC\Configurations\" -Wait -Verbose
```

<span data-ttu-id="0eda7-124">Эта команда применяет конфигурацию из каталога C:\DSC\Configurations\ к локальному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="0eda7-124">This command applies the configuration from C:\DSC\Configurations\ to the local computer.</span></span>
<span data-ttu-id="0eda7-125">Команда возвращает объекты **Job** для каждого целевого узла, в котором они развернуты (в данном случае просто  локальный компьютер).</span><span class="sxs-lookup"><span data-stu-id="0eda7-125">The command returns **Job** objects for each target node deployed to, in this case, just the local computer.</span></span>
<span data-ttu-id="0eda7-126">В этом примере задается параметр *verbose* .</span><span class="sxs-lookup"><span data-stu-id="0eda7-126">This example specifies the *Verbose* parameter.</span></span>
<span data-ttu-id="0eda7-127">Таким образом, команда отправляет сообщения на консоль по мере продолжения.</span><span class="sxs-lookup"><span data-stu-id="0eda7-127">Therefore, the command sends messages to the console as it proceeds.</span></span>
<span data-ttu-id="0eda7-128">Команда включает параметр *Wait* .</span><span class="sxs-lookup"><span data-stu-id="0eda7-128">The command includes the *Wait* parameter.</span></span>
<span data-ttu-id="0eda7-129">Поэтому вы не можете использовать консоль, пока команда не завершит все задачи настройки.</span><span class="sxs-lookup"><span data-stu-id="0eda7-129">Therefore, you cannot use the console until the command finishes all configuration tasks.</span></span>

### <span data-ttu-id="0eda7-130">Пример 3. применение параметров конфигурации с помощью сеанса CIM</span><span class="sxs-lookup"><span data-stu-id="0eda7-130">Example 3: Apply configuration settings by using a CIM session</span></span>

```
PS C:\> $Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
PS C:\> Start-DscConfiguration -Path "C:\DSC\Configurations\" -CimSession $Session
```

<span data-ttu-id="0eda7-131">В этом примере к указанному компьютеру применяются параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0eda7-131">This example applies configuration settings to a specified computer.</span></span>
<span data-ttu-id="0eda7-132">Пример создает сеанс CIM для компьютера с именем Server01, чтобы использовать с командлетом.</span><span class="sxs-lookup"><span data-stu-id="0eda7-132">The example creates a CIM session for a computer named Server01 for use with the cmdlet.</span></span>
<span data-ttu-id="0eda7-133">Кроме того, можно создать массив сеансов CIM для применения командлета к нескольким указанным компьютерам.</span><span class="sxs-lookup"><span data-stu-id="0eda7-133">Alternatively, create an array of CIM sessions to apply the cmdlet to multiple specified computers.</span></span>

<span data-ttu-id="0eda7-134">Первая команда создает сеанс CIM, используя командлет **New-CimSession** , а затем сохраняет объект **CimSession** в переменной $Session.</span><span class="sxs-lookup"><span data-stu-id="0eda7-134">The first command creates a CIM session by using the **New-CimSession** cmdlet, and then stores the **CimSession** object in the $Session variable.</span></span>
<span data-ttu-id="0eda7-135">Команда запрашивает пароль.</span><span class="sxs-lookup"><span data-stu-id="0eda7-135">The command prompts you for a password.</span></span>
<span data-ttu-id="0eda7-136">Для получения дополнительных сведений введите `Get-Help NewCimSession`.</span><span class="sxs-lookup"><span data-stu-id="0eda7-136">For more information, type `Get-Help NewCimSession`.</span></span>

<span data-ttu-id="0eda7-137">Вторая команда применяет параметры конфигурации из каталога c:\dsc\configurations\ к компьютерам, идентифицируемым объектами **CimSession** , хранящимися в переменной $Session.</span><span class="sxs-lookup"><span data-stu-id="0eda7-137">The second command applies the configuration settings from C:\DSC\Configurations\ to the computers identified by the **CimSession** objects stored in the $Session variable.</span></span>
<span data-ttu-id="0eda7-138">В этом примере переменная $Session содержит сеанс CIM только для компьютера с именем Server01.</span><span class="sxs-lookup"><span data-stu-id="0eda7-138">In this example, the $Session variable contains a CIM session only for the computer named Server01.</span></span>
<span data-ttu-id="0eda7-139">Команда применяет конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="0eda7-139">The command applies the configuration.</span></span>
<span data-ttu-id="0eda7-140">Команда создает объекты **Job** для каждого настроенного компьютера.</span><span class="sxs-lookup"><span data-stu-id="0eda7-140">The command creates **Job** objects for each configured computer.</span></span>

## <span data-ttu-id="0eda7-141">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0eda7-141">PARAMETERS</span></span>

### <span data-ttu-id="0eda7-142">-CimSession</span><span class="sxs-lookup"><span data-stu-id="0eda7-142">-CimSession</span></span>
<span data-ttu-id="0eda7-143">Запуск командлета в удаленном сеансе или на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="0eda7-143">Runs the cmdlet in a remote session or on a remote computer.</span></span>
<span data-ttu-id="0eda7-144">Введите имя компьютера или объект сеанса, например выходные данные командлета [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) или [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) .</span><span class="sxs-lookup"><span data-stu-id="0eda7-144">Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet.</span></span>
<span data-ttu-id="0eda7-145">Сеанс по умолчанию — текущий сеанс на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="0eda7-145">The default is the current session on the local computer.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: CimSessionAndPathSet, CimSessionAndUseExistingSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="0eda7-146">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="0eda7-146">-ComputerName</span></span>
<span data-ttu-id="0eda7-147">Указывает массив имен компьютеров.</span><span class="sxs-lookup"><span data-stu-id="0eda7-147">Specifies an array of computer names.</span></span>
<span data-ttu-id="0eda7-148">Этот параметр позволяет ограничивать компьютеры, на которых имеются документы конфигурации в параметре *path* , на указанные в массиве.</span><span class="sxs-lookup"><span data-stu-id="0eda7-148">This parameter restricts the computers that have configuration documents in the *Path* parameter to those specified in the array.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerNameAndPathSet, ComputerNameAndUseExistingSet
Aliases: CN, ServerName

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="0eda7-149">-Credential</span><span class="sxs-lookup"><span data-stu-id="0eda7-149">-Credential</span></span>
<span data-ttu-id="0eda7-150">Указывает имя пользователя и пароль как объект **PSCredential** для целевого компьютера.</span><span class="sxs-lookup"><span data-stu-id="0eda7-150">Specifies a user name and password, as a **PSCredential** object, for the target computer.</span></span>
<span data-ttu-id="0eda7-151">Чтобы получить объект **PSCredential** , используйте командлет Get-Credential.</span><span class="sxs-lookup"><span data-stu-id="0eda7-151">To obtain a **PSCredential** object, use the Get-Credential cmdlet.</span></span>
<span data-ttu-id="0eda7-152">Для получения дополнительных сведений введите `Get-Help Get-Credential`.</span><span class="sxs-lookup"><span data-stu-id="0eda7-152">For more information, type `Get-Help Get-Credential`.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerNameAndPathSet, ComputerNameAndUseExistingSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0eda7-153">-Force</span><span class="sxs-lookup"><span data-stu-id="0eda7-153">-Force</span></span>
<span data-ttu-id="0eda7-154">Останавливает операцию настройки, которая выполняется на целевом компьютере, и начинает новую операцию Start-Configuration.</span><span class="sxs-lookup"><span data-stu-id="0eda7-154">Stops the configuration operation currently running on the target computer and begins the new Start-Configuration operation.</span></span>
<span data-ttu-id="0eda7-155">Если свойство **RefreshMode** локального Configuration Manager имеет значение **Pull** , то при указании этого параметра он изменяется на **Push** .</span><span class="sxs-lookup"><span data-stu-id="0eda7-155">If the **RefreshMode** property of the Local Configuration Manager is set to **Pull** , specifying this parameter changes it to **Push** .</span></span>

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

### <span data-ttu-id="0eda7-156">-JobName</span><span class="sxs-lookup"><span data-stu-id="0eda7-156">-JobName</span></span>
<span data-ttu-id="0eda7-157">Задает понятное имя для задания.</span><span class="sxs-lookup"><span data-stu-id="0eda7-157">Specifies a friendly name for a job.</span></span>
<span data-ttu-id="0eda7-158">Если указать этот параметр, командлет выполняется как задание и возвращает объект **Job** .</span><span class="sxs-lookup"><span data-stu-id="0eda7-158">If you specify this parameter, the cmdlet runs as a job, and it returns a **Job** object.</span></span>

<span data-ttu-id="0eda7-159">По умолчанию Windows PowerShell назначает имя Жобн, где N — целое число.</span><span class="sxs-lookup"><span data-stu-id="0eda7-159">By default, Windows PowerShell assigns the name JobN where N is an integer.</span></span>

<span data-ttu-id="0eda7-160">Если параметр *Wait* указан, не указывайте этот параметр.</span><span class="sxs-lookup"><span data-stu-id="0eda7-160">If you specify the *Wait* parameter, do not specify this parameter.</span></span>

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

### <span data-ttu-id="0eda7-161">-Path</span><span class="sxs-lookup"><span data-stu-id="0eda7-161">-Path</span></span>
<span data-ttu-id="0eda7-162">Указывает путь к файлу папки, которая содержит файлы параметров конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0eda7-162">Specifies a file path of a folder that contains configuration settings files.</span></span>
<span data-ttu-id="0eda7-163">Этот командлет публикует и применяет эти параметры конфигурации к компьютерам, имеющим файлы параметров по указанному пути.</span><span class="sxs-lookup"><span data-stu-id="0eda7-163">This cmdlet publishes and applies these configuration settings to computers that have settings files in the specified path.</span></span>
<span data-ttu-id="0eda7-164">Каждый целевой узел должен иметь файл параметров следующего формата: NetBIOS Name. mof.</span><span class="sxs-lookup"><span data-stu-id="0eda7-164">Each target node must have a settings file of the following format: NetBIOS Name.mof.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerNameAndPathSet, CimSessionAndPathSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0eda7-165">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="0eda7-165">-ThrottleLimit</span></span>
<span data-ttu-id="0eda7-166">Указание максимального количества одновременных операций, которые можно выполнять для запуска командлета.</span><span class="sxs-lookup"><span data-stu-id="0eda7-166">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>
<span data-ttu-id="0eda7-167">Если этот параметр пропущен или указано значение `0` , Windows PowerShell вычисляет оптимальное ограничение регулирования для командлета на основе числа командлетов CIM, выполняемых на компьютере.</span><span class="sxs-lookup"><span data-stu-id="0eda7-167">If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.</span></span>
<span data-ttu-id="0eda7-168">Предел регулирования применим только к текущему командлету, а не к сеансу или компьютеру.</span><span class="sxs-lookup"><span data-stu-id="0eda7-168">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="0eda7-169">-UseExisting</span><span class="sxs-lookup"><span data-stu-id="0eda7-169">-UseExisting</span></span>
<span data-ttu-id="0eda7-170">Указывает, что этот командлет применяет существующую конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="0eda7-170">Indicates that this cmdlet applies the existing configuration.</span></span>
<span data-ttu-id="0eda7-171">Конфигурация может существовать на целевом компьютере путем внедрения с помощью командлета **Start-DscConfiguration** или публикации с помощью Publish-DscConfiguration.</span><span class="sxs-lookup"><span data-stu-id="0eda7-171">The configuration can exist on the target computer by enactment using **Start-DscConfiguration** or by publication using the Publish-DscConfiguration cmdlet.</span></span>

<span data-ttu-id="0eda7-172">Прежде чем указать этот параметр для этого командлета, ознакомьтесь со сведениями в подразделах [что нового в Windows PowerShell 5,0](/powershell/scripting/whats-new/what-s-new-in-windows-powershell-50)</span><span class="sxs-lookup"><span data-stu-id="0eda7-172">Before you specify this parameter for this cmdlet, review the information in [What's New in Windows PowerShell 5.0](/powershell/scripting/whats-new/what-s-new-in-windows-powershell-50)</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerNameAndUseExistingSet, CimSessionAndUseExistingSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0eda7-173">-Wait</span><span class="sxs-lookup"><span data-stu-id="0eda7-173">-Wait</span></span>
<span data-ttu-id="0eda7-174">Указывает, что командлет блокирует консоль до тех пор, пока не завершит все задачи настройки.</span><span class="sxs-lookup"><span data-stu-id="0eda7-174">Indicates that the cmdlet blocks the console until it finishes all configuration tasks.</span></span>

<span data-ttu-id="0eda7-175">Если этот параметр указан, не указывайте параметр *JobName* .</span><span class="sxs-lookup"><span data-stu-id="0eda7-175">If you specify this parameter, do not specify the *JobName* parameter.</span></span>

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

### <span data-ttu-id="0eda7-176">-Confirm</span><span class="sxs-lookup"><span data-stu-id="0eda7-176">-Confirm</span></span>
<span data-ttu-id="0eda7-177">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="0eda7-177">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="0eda7-178">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="0eda7-178">-WhatIf</span></span>
<span data-ttu-id="0eda7-179">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="0eda7-179">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="0eda7-180">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="0eda7-180">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="0eda7-181">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="0eda7-181">CommonParameters</span></span>
<span data-ttu-id="0eda7-182">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0eda7-182">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0eda7-183">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0eda7-183">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0eda7-184">Входные данные</span><span class="sxs-lookup"><span data-stu-id="0eda7-184">INPUTS</span></span>

## <span data-ttu-id="0eda7-185">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="0eda7-185">OUTPUTS</span></span>

## <span data-ttu-id="0eda7-186">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="0eda7-186">NOTES</span></span>

## <span data-ttu-id="0eda7-187">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="0eda7-187">RELATED LINKS</span></span>

[<span data-ttu-id="0eda7-188">Обзор Windows PowerShell Desired State Configuration</span><span class="sxs-lookup"><span data-stu-id="0eda7-188">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/overview)

[<span data-ttu-id="0eda7-189">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="0eda7-189">Get-DscConfiguration</span></span>](Get-DscConfiguration.md)

[<span data-ttu-id="0eda7-190">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="0eda7-190">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)

[<span data-ttu-id="0eda7-191">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="0eda7-191">Restore-DscConfiguration</span></span>](Restore-DscConfiguration.md)

[<span data-ttu-id="0eda7-192">Stop-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="0eda7-192">Stop-DscConfiguration</span></span>](Stop-DscConfiguration.md)

[<span data-ttu-id="0eda7-193">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="0eda7-193">Test-DscConfiguration</span></span>](Test-DscConfiguration.md)

[<span data-ttu-id="0eda7-194">Update-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="0eda7-194">Update-DscConfiguration</span></span>](Update-DscConfiguration.md)
