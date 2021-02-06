---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/debug-runspace?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Debug-Runspace
ms.openlocfilehash: 3f01b7624ffcbca472b09bdb83a7440f3526db43
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604584"
---
# <span data-ttu-id="8cbaa-102">Debug-Runspace</span><span class="sxs-lookup"><span data-stu-id="8cbaa-102">Debug-Runspace</span></span>

## <span data-ttu-id="8cbaa-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="8cbaa-103">SYNOPSIS</span></span>
<span data-ttu-id="8cbaa-104">Запускает интерактивный сеанс отладки с пространством выполнения.</span><span class="sxs-lookup"><span data-stu-id="8cbaa-104">Starts an interactive debugging session with a runspace.</span></span>

## <span data-ttu-id="8cbaa-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8cbaa-105">SYNTAX</span></span>

### <span data-ttu-id="8cbaa-106">Рунспацепараметерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="8cbaa-106">RunspaceParameterSet (Default)</span></span>

```
Debug-Runspace [-Runspace] <Runspace> [-BreakAll] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="8cbaa-107">намепараметерсет</span><span class="sxs-lookup"><span data-stu-id="8cbaa-107">NameParameterSet</span></span>

```
Debug-Runspace [-Name] <String> [-BreakAll] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="8cbaa-108">идпараметерсет</span><span class="sxs-lookup"><span data-stu-id="8cbaa-108">IdParameterSet</span></span>

```
Debug-Runspace [-Id] <Int32> [-BreakAll] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="8cbaa-109">инстанцеидпараметерсет</span><span class="sxs-lookup"><span data-stu-id="8cbaa-109">InstanceIdParameterSet</span></span>

```
Debug-Runspace [-InstanceId] <Guid> [-BreakAll] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="8cbaa-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8cbaa-110">DESCRIPTION</span></span>

<span data-ttu-id="8cbaa-111">`Debug-Runspace`Командлет запускает интерактивный сеанс отладки с локальным или удаленным активным пространством выполнения.</span><span class="sxs-lookup"><span data-stu-id="8cbaa-111">The `Debug-Runspace` cmdlet starts an interactive debugging session with a local or remote active runspace.</span></span> <span data-ttu-id="8cbaa-112">Для поиска процессов, связанных с PowerShell, можно найти пространство выполнения, которое необходимо отладить `Get-Process` , `Enter-PSHostProcess` а затем указать идентификатор процесса, указанный в параметре **ID** , чтобы присоединиться к процессу, а затем `Get-Runspace` вывести список пространств в хост-процессе PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8cbaa-112">You can find a runspace that you want to debug by first running `Get-Process` to find processes associated with PowerShell, then `Enter-PSHostProcess` with the process ID specified in the **Id** parameter to attach to the process, and then `Get-Runspace` to list runspaces within the PowerShell host process.</span></span>

<span data-ttu-id="8cbaa-113">После выбора пространства выполнения для отладки, если пространство выполнения в данный момент выполняет команду или сценарий или если скрипт остановлен в точке останова, PowerShell открывает сеанс удаленного отладчика для пространства выполнения.</span><span class="sxs-lookup"><span data-stu-id="8cbaa-113">After you have selected a runspace to debug, if the runspace is currently running a command or script, or if the script has stopped at a breakpoint, PowerShell opens a remote debugger session for the runspace.</span></span> <span data-ttu-id="8cbaa-114">Скрипт пространства выполнения можно отлаживать таким же образом, как и сценарии удаленного сеанса.</span><span class="sxs-lookup"><span data-stu-id="8cbaa-114">You can debug the runspace script in the same way remote session scripts are debugged.</span></span>

<span data-ttu-id="8cbaa-115">Подключиться к хост-процессу PowerShell можно только при наличии прав администратора на компьютере, на котором выполняется процесс, или при запуске скрипта, который требуется отладить.</span><span class="sxs-lookup"><span data-stu-id="8cbaa-115">You can only attach to a PowerShell host process if you are an administrator on the computer that is running the process, or you are running the script that you want to debug.</span></span> <span data-ttu-id="8cbaa-116">Кроме того, невозможно ввести ведущий процесс, выполняющий текущий сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8cbaa-116">Also, you cannot enter the host process that is running the current PowerShell session.</span></span> <span data-ttu-id="8cbaa-117">Можно ввести только ведущий процесс, выполняющий другой сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8cbaa-117">You can only enter a host process that is running a different PowerShell session.</span></span>

## <span data-ttu-id="8cbaa-118">Примеры</span><span class="sxs-lookup"><span data-stu-id="8cbaa-118">EXAMPLES</span></span>

### <span data-ttu-id="8cbaa-119">Пример 1. Отладка удаленного пространства выполнения</span><span class="sxs-lookup"><span data-stu-id="8cbaa-119">Example 1: Debug a remote runspace</span></span>

```
PS C:\> Get-Process -ComputerName "WS10TestServer" -Name "*powershell*"

Handles      WS(K)   VM(M)      CPU(s)    Id  ProcessName
-------      -----   -----      ------    --  -----------
    377      69912     63     2.09      2420  powershell
    399     123396    829     4.48      1152  powershell_ise

PS C:\> Enter-PSSession -ComputerName "WS10TestServer"
[WS10TestServer]:PS C:\> Enter-PSHostProcess -Id 1152
[WS10TestServer:][Process:1152]: PS C:\Users\Test\Documents> Get-Runspace

Id Name            ComputerName    Type          State         Availability
-- ----            ------------    ----          -----         ------------
 1 Runspace1       WS10TestServer  Remote        Opened        Available
 2 RemoteHost      WS10TestServer  Remote        Opened        Busy

PS C:\> [WS10TestServer][Process:1152]: PS C:\Users\Test\Documents> Debug-Runspace -Id 2

Hit Line breakpoint on 'C:\TestWFVar1.ps1:83'
At C:\TestWFVar1.ps1:83 char:1
+ $scriptVar = "Script Variable"
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
[Process:1152]: [RSDBG: 2]: PS C:\> >
```

<span data-ttu-id="8cbaa-120">В этом примере выполняется отладка пространства выполнения, открытого на удаленном компьютере WS10TestServer.</span><span class="sxs-lookup"><span data-stu-id="8cbaa-120">In this example, you debug a runspace that is open on a remote computer, WS10TestServer.</span></span> <span data-ttu-id="8cbaa-121">В первой строке команды вы запускаете `Get-Process` на удаленном компьютере и выполняете фильтрацию для процессов узла Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8cbaa-121">In the first line of the command, you run `Get-Process` on the remote computer, and filter for Windows PowerShell host processes.</span></span> <span data-ttu-id="8cbaa-122">В этом примере вы хотите отладить процесс с ИДЕНТИФИКАТОРом 1152, ведущий процесс Windows PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="8cbaa-122">In this example, you want to debug process ID 1152, the Windows PowerShell ISE host process.</span></span>

<span data-ttu-id="8cbaa-123">Во второй команде запускается, `Enter-PSSession` чтобы открыть удаленный сеанс на WS10TestServer.</span><span class="sxs-lookup"><span data-stu-id="8cbaa-123">In the second command, you run `Enter-PSSession` to open a remote session on WS10TestServer.</span></span> <span data-ttu-id="8cbaa-124">В третьей команде вы подключаетесь к ведущему процессу Windows PowerShell ISE, работающему на удаленном сервере, запустив `Enter-PSHostProcess` и УКАЗАВ идентификатор хостового процесса, полученный в первой команде 1152.</span><span class="sxs-lookup"><span data-stu-id="8cbaa-124">In the third command, you attach to the Windows PowerShell ISE host process running on the remote server by running `Enter-PSHostProcess`, and specifying the ID of the host process that you obtained in the first command, 1152.</span></span>

<span data-ttu-id="8cbaa-125">В четвертой команде вы перечислите доступные пространства выполнения для идентификатора процесса 1152, выполнив команду `Get-Runspace` .</span><span class="sxs-lookup"><span data-stu-id="8cbaa-125">In the fourth command, you list available runspaces for process ID 1152 by running `Get-Runspace`.</span></span>
<span data-ttu-id="8cbaa-126">Вы запомните ИДЕНТИФИКАЦИОНный номер занятого пространства выполнения; Он выполняет сценарий, который требуется отладить.</span><span class="sxs-lookup"><span data-stu-id="8cbaa-126">You note the ID number of the Busy runspace; it is running a script that you want to debug.</span></span>

<span data-ttu-id="8cbaa-127">В последней команде вы начинаете отладку открытого пространства выполнения, в котором выполняется скрипт, TestWFVar1.ps1, путем запуска `Debug-Runspace` и идентификации пространства выполнения по его идентификатору (2) путем добавления параметра **ID** .</span><span class="sxs-lookup"><span data-stu-id="8cbaa-127">In the last command, you start debugging an opened runspace that is running a script, TestWFVar1.ps1, by running `Debug-Runspace`, and identifying the runspace by its ID, 2, by adding the **Id** parameter.</span></span> <span data-ttu-id="8cbaa-128">Так как в скрипте есть точка останова, откроется отладчик.</span><span class="sxs-lookup"><span data-stu-id="8cbaa-128">Because there's a breakpoint in the script, the debugger opens.</span></span>

## <span data-ttu-id="8cbaa-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8cbaa-129">PARAMETERS</span></span>

### <span data-ttu-id="8cbaa-130">-Id</span><span class="sxs-lookup"><span data-stu-id="8cbaa-130">-Id</span></span>

<span data-ttu-id="8cbaa-131">Указывает ИДЕНТИФИКАЦИОНный номер пространства выполнения.</span><span class="sxs-lookup"><span data-stu-id="8cbaa-131">Specifies the ID number of a runspace.</span></span> <span data-ttu-id="8cbaa-132">Вы можете запустить `Get-Runspace` , чтобы отобразить идентификаторы пространства выполнения.</span><span class="sxs-lookup"><span data-stu-id="8cbaa-132">You can run `Get-Runspace` to show runspace IDs.</span></span>

```yaml
Type: System.Int32
Parameter Sets: IdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8cbaa-133">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="8cbaa-133">-InstanceId</span></span>

<span data-ttu-id="8cbaa-134">Задает пространство выполнения по ИДЕНТИФИКАТОРу экземпляра, GUID, который можно отобразить, выполнив `Get-Runspace` .</span><span class="sxs-lookup"><span data-stu-id="8cbaa-134">Specifies a runspace by its instance ID, a GUID that you can show by running `Get-Runspace`.</span></span>

```yaml
Type: System.Guid
Parameter Sets: InstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8cbaa-135">-Name</span><span class="sxs-lookup"><span data-stu-id="8cbaa-135">-Name</span></span>

<span data-ttu-id="8cbaa-136">Задает пространство выполнения по имени.</span><span class="sxs-lookup"><span data-stu-id="8cbaa-136">Specifies a runspace by its name.</span></span> <span data-ttu-id="8cbaa-137">`Get-Runspace`Для отображения имен пространств выполнения можно запустить.</span><span class="sxs-lookup"><span data-stu-id="8cbaa-137">You can run `Get-Runspace` to show the names of runspaces.</span></span>

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8cbaa-138">-Пространство выполнения</span><span class="sxs-lookup"><span data-stu-id="8cbaa-138">-Runspace</span></span>

<span data-ttu-id="8cbaa-139">Задает объект пространства выполнения.</span><span class="sxs-lookup"><span data-stu-id="8cbaa-139">Specifies a runspace object.</span></span> <span data-ttu-id="8cbaa-140">Самый простой способ предоставить значение для этого параметра — указать переменную, содержащую результаты фильтрованной `Get-Runspace` команды.</span><span class="sxs-lookup"><span data-stu-id="8cbaa-140">The simplest way to provide a value for this parameter is to specify a variable that contains the results of a filtered `Get-Runspace` command.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.Runspace
Parameter Sets: RunspaceParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="8cbaa-141">-Confirm</span><span class="sxs-lookup"><span data-stu-id="8cbaa-141">-Confirm</span></span>

<span data-ttu-id="8cbaa-142">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="8cbaa-142">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8cbaa-143">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="8cbaa-143">-WhatIf</span></span>

<span data-ttu-id="8cbaa-144">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="8cbaa-144">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="8cbaa-145">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="8cbaa-145">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8cbaa-146">-BreakAll</span><span class="sxs-lookup"><span data-stu-id="8cbaa-146">-BreakAll</span></span>

<span data-ttu-id="8cbaa-147">{{Fill BreakAll Description}}</span><span class="sxs-lookup"><span data-stu-id="8cbaa-147">{{ Fill BreakAll Description }}</span></span>

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

### <span data-ttu-id="8cbaa-148">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="8cbaa-148">CommonParameters</span></span>

<span data-ttu-id="8cbaa-149">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="8cbaa-149">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8cbaa-150">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="8cbaa-150">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8cbaa-151">Входные данные</span><span class="sxs-lookup"><span data-stu-id="8cbaa-151">INPUTS</span></span>

### <span data-ttu-id="8cbaa-152">System. Management. Automation. пространства выполнения</span><span class="sxs-lookup"><span data-stu-id="8cbaa-152">System.Management.Automation.Runspaces.Runspace</span></span>

<span data-ttu-id="8cbaa-153">Результаты команды можно передать `Get-Runspace` в **Debug-пространство** с помощью конвейера.</span><span class="sxs-lookup"><span data-stu-id="8cbaa-153">You can pipe the results of a `Get-Runspace` command to **Debug-Runspace.**</span></span>

## <span data-ttu-id="8cbaa-154">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="8cbaa-154">OUTPUTS</span></span>

## <span data-ttu-id="8cbaa-155">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="8cbaa-155">NOTES</span></span>

<span data-ttu-id="8cbaa-156">`Debug-Runspace` работает с пространствами выполнения, которые находятся в открытом состоянии.</span><span class="sxs-lookup"><span data-stu-id="8cbaa-156">`Debug-Runspace` works on runspaces that are in the Opened state.</span></span> <span data-ttu-id="8cbaa-157">Если состояние выполнения изменяется с открытого на другое, это пространство выполнения автоматически удаляется из списка выполняемых.</span><span class="sxs-lookup"><span data-stu-id="8cbaa-157">If a runspace state changes from Opened to another state, that runspace is automatically removed from the running list.</span></span> <span data-ttu-id="8cbaa-158">Пространство выполнения добавляется в выполняемый список только в том случае, если оно соответствует следующим критериям.</span><span class="sxs-lookup"><span data-stu-id="8cbaa-158">A runspace is added to the running list only if it meets the following criteria.</span></span>

- <span data-ttu-id="8cbaa-159">Значение, если оно поступает из Invoke-Command; то есть у него есть `Invoke-Command` идентификатор GUID.</span><span class="sxs-lookup"><span data-stu-id="8cbaa-159">If it is coming from Invoke-Command; that is, it has an `Invoke-Command` GUID ID.</span></span>
- <span data-ttu-id="8cbaa-160">Если он поступает из, то есть `Debug-Runspace` имеет `Debug-Runspace` идентификатор GUID.</span><span class="sxs-lookup"><span data-stu-id="8cbaa-160">If it is coming from `Debug-Runspace`; that is, it has a `Debug-Runspace` GUID ID.</span></span>
- <span data-ttu-id="8cbaa-161">Если он поступает из рабочего процесса PowerShell, идентификатор задания рабочего процесса совпадает с идентификатором текущего активного задания рабочего процесса отладчика.</span><span class="sxs-lookup"><span data-stu-id="8cbaa-161">If it is coming from a PowerShell workflow, and its workflow job ID is the same as the current active debugger workflow job ID.</span></span>

## <span data-ttu-id="8cbaa-162">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="8cbaa-162">RELATED LINKS</span></span>

[<span data-ttu-id="8cbaa-163">about_Debuggers</span><span class="sxs-lookup"><span data-stu-id="8cbaa-163">about_Debuggers</span></span>](../Microsoft.PowerShell.Core/About/about_Debuggers.md)

[<span data-ttu-id="8cbaa-164">Debug-Job</span><span class="sxs-lookup"><span data-stu-id="8cbaa-164">Debug-Job</span></span>](../Microsoft.PowerShell.Core/Debug-Job.md)

[<span data-ttu-id="8cbaa-165">Get-Runspace</span><span class="sxs-lookup"><span data-stu-id="8cbaa-165">Get-Runspace</span></span>](Get-Runspace.md)

[<span data-ttu-id="8cbaa-166">Get-Process</span><span class="sxs-lookup"><span data-stu-id="8cbaa-166">Get-Process</span></span>](../Microsoft.PowerShell.Management/Get-Process.md)

[<span data-ttu-id="8cbaa-167">Enter-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="8cbaa-167">Enter-PSHostProcess</span></span>](../Microsoft.PowerShell.Core/Enter-PSHostProcess.md)

[<span data-ttu-id="8cbaa-168">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="8cbaa-168">Enter-PSSession</span></span>](../Microsoft.PowerShell.Core/Enter-PSSession.md)

