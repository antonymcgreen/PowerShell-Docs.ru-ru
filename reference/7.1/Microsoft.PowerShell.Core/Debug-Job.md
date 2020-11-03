---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/debug-job?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Debug-Job
ms.openlocfilehash: 8ff583fbf0ebf453a5194deecbc1eb42a51242d4
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93229554"
---
# <span data-ttu-id="7a7be-103">Debug-Job</span><span class="sxs-lookup"><span data-stu-id="7a7be-103">Debug-Job</span></span>

## <span data-ttu-id="7a7be-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="7a7be-104">SYNOPSIS</span></span>
<span data-ttu-id="7a7be-105">Выполняет отработку ошибок выполняемого фонового, удаленного или рабочего процесса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7a7be-105">Debugs a running background, remote, or PowerShell Workflow job.</span></span>

## <span data-ttu-id="7a7be-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7a7be-106">SYNTAX</span></span>

### <span data-ttu-id="7a7be-107">Жобпараметерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="7a7be-107">JobParameterSet (Default)</span></span>

```
Debug-Job [-Job] <Job> [-BreakAll] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="7a7be-108">жобнамепараметерсет</span><span class="sxs-lookup"><span data-stu-id="7a7be-108">JobNameParameterSet</span></span>

```
Debug-Job [-Name] <String> [-BreakAll] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="7a7be-109">жобидпараметерсет</span><span class="sxs-lookup"><span data-stu-id="7a7be-109">JobIdParameterSet</span></span>

```
Debug-Job [-Id] <Int32> [-BreakAll] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="7a7be-110">жобинстанцеидпараметерсет</span><span class="sxs-lookup"><span data-stu-id="7a7be-110">JobInstanceIdParameterSet</span></span>

```
Debug-Job [-InstanceId] <Guid> [-BreakAll] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="7a7be-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7a7be-111">DESCRIPTION</span></span>
<span data-ttu-id="7a7be-112">Командлет **Debug-Job** позволяет выполнять отладку скриптов, выполняемых в заданиях.</span><span class="sxs-lookup"><span data-stu-id="7a7be-112">The **Debug-Job** cmdlet lets you debug scripts that are running within jobs.</span></span>
<span data-ttu-id="7a7be-113">Командлет предназначен для отладки заданий рабочего процесса PowerShell, фоновых заданий и заданий, выполняемых в удаленных сеансах.</span><span class="sxs-lookup"><span data-stu-id="7a7be-113">The cmdlet is designed to debug PowerShell Workflow jobs, background jobs, and jobs running in remote sessions.</span></span>
<span data-ttu-id="7a7be-114">**Debug — задание** принимает объект выполняемого задания, имя, идентификатор или идентификатор экземпляра в качестве входных данных и запускает сеанс отладки в выполняемом сценарии.</span><span class="sxs-lookup"><span data-stu-id="7a7be-114">**Debug-Job** accepts a running job object, name, ID, or instance ID as input, and starts a debugging session on the script it is running.</span></span>
<span data-ttu-id="7a7be-115">Команда **Quit** отладчика останавливает задание и запускает сценарий.</span><span class="sxs-lookup"><span data-stu-id="7a7be-115">The debugger **quit** command stops the job and running script.</span></span>
<span data-ttu-id="7a7be-116">Начиная с Windows PowerShell 5,0, команда **Exit** отсоединяет отладчик и позволяет продолжить выполнение задания.</span><span class="sxs-lookup"><span data-stu-id="7a7be-116">Starting in Windows PowerShell 5.0, the **exit** command detaches the debugger, and allows the job to continue to run.</span></span>

## <span data-ttu-id="7a7be-117">Примеры</span><span class="sxs-lookup"><span data-stu-id="7a7be-117">EXAMPLES</span></span>

### <span data-ttu-id="7a7be-118">Пример 1. Отладка задания по ИДЕНТИФИКАТОРу задания</span><span class="sxs-lookup"><span data-stu-id="7a7be-118">Example 1: Debug a job by job ID</span></span>

```
PS C:\> Debug-Job -ID 3
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
3      Job3            RemoteJob       Running       True            PowerShellIx         TestWFDemo1.ps1
          Entering debug mode. Use h or ? for help.

          Hit Line breakpoint on 'C:\TestWFDemo1.ps1:8'

          At C:\TestWFDemo1.ps1:8 char:5
          +     Write-Output -InputObject "Now writing output:"
          +     ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
          [DBG:PowerShellIx]: PS C:\> > list

              3:
              4:  workflow SampleWorkflowTest
              5:  {
              6:      param ($MyOutput)
              7:
              8:*     Write-Output -InputObject "Now writing output:"
              9:      Write-Output -Input $MyOutput
             10:
             11:      Write-Output -InputObject "Get PowerShell process:"
             12:      Get-Process -Name powershell
             13:
             14:      Write-Output -InputObject "Workflow function complete."
             15:  }
             16:
             17:  # Call workflow function
             18:  SampleWorkflowTest -MyOutput "Hello"
```

<span data-ttu-id="7a7be-119">Эта команда разбивается на выполняющееся задание с ИДЕНТИФИКАТОРом 3.</span><span class="sxs-lookup"><span data-stu-id="7a7be-119">This command breaks into a running job with an ID of 3.</span></span>

## <span data-ttu-id="7a7be-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7a7be-120">PARAMETERS</span></span>

### <span data-ttu-id="7a7be-121">-Id</span><span class="sxs-lookup"><span data-stu-id="7a7be-121">-Id</span></span>
<span data-ttu-id="7a7be-122">Указывает ИДЕНТИФИКАЦИОНный номер выполняемого задания.</span><span class="sxs-lookup"><span data-stu-id="7a7be-122">Specifies the ID number of a running job.</span></span>
<span data-ttu-id="7a7be-123">Чтобы получить ИДЕНТИФИКАЦИОНный номер задания, выполните командлет Get-Job.</span><span class="sxs-lookup"><span data-stu-id="7a7be-123">To get the ID number of a job, run the Get-Job cmdlet.</span></span>

```yaml
Type: System.Int32
Parameter Sets: JobIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7a7be-124">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="7a7be-124">-InstanceId</span></span>
<span data-ttu-id="7a7be-125">Указывает идентификатор GUID экземпляра выполняющегося задания.</span><span class="sxs-lookup"><span data-stu-id="7a7be-125">Specifies the instance ID GUID of a running job.</span></span>
<span data-ttu-id="7a7be-126">Чтобы получить значение *InstanceId* задания, выполните командлет **Get-Job** , передав результаты в командлет **Format-** \*, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="7a7be-126">To get the *InstanceId* of a job, run the **Get-Job** cmdlet, piping the results into a **Format-** \* cmdlet, as shown in the following example:</span></span>

`Get-Job | Format-List -Property Id,Name,InstanceId,State`

```yaml
Type: System.Guid
Parameter Sets: JobInstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7a7be-127">-Job</span><span class="sxs-lookup"><span data-stu-id="7a7be-127">-Job</span></span>
<span data-ttu-id="7a7be-128">Указывает выполняющийся объект задания.</span><span class="sxs-lookup"><span data-stu-id="7a7be-128">Specifies a running job object.</span></span>
<span data-ttu-id="7a7be-129">Самый простой способ использовать этот параметр — Сохранить результаты выполнения команды **Get-Job** , возвращающей выполняемое задание, которое необходимо отладить, в переменной, а затем указать переменную в качестве значения этого параметра.</span><span class="sxs-lookup"><span data-stu-id="7a7be-129">The simplest way to use this parameter is to save the results of a **Get-Job** command that returns the running job that you want to debug in a variable, and then specify the variable as the value of this parameter.</span></span>

```yaml
Type: System.Management.Automation.Job
Parameter Sets: JobParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="7a7be-130">-Name</span><span class="sxs-lookup"><span data-stu-id="7a7be-130">-Name</span></span>
<span data-ttu-id="7a7be-131">Указывает задание по понятному имени задания.</span><span class="sxs-lookup"><span data-stu-id="7a7be-131">Specifies a job by the friendly name of the job.</span></span>
<span data-ttu-id="7a7be-132">При запуске задания можно указать имя задания, добавив параметр *JobName* в командлетах, таких как Invoke-Command и Start-Job.</span><span class="sxs-lookup"><span data-stu-id="7a7be-132">When you start a job, you can specify a job name by adding the *JobName* parameter, in cmdlets such as Invoke-Command and Start-Job.</span></span>

```yaml
Type: System.String
Parameter Sets: JobNameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7a7be-133">-Confirm</span><span class="sxs-lookup"><span data-stu-id="7a7be-133">-Confirm</span></span>
<span data-ttu-id="7a7be-134">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="7a7be-134">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="7a7be-135">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="7a7be-135">-WhatIf</span></span>
<span data-ttu-id="7a7be-136">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="7a7be-136">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="7a7be-137">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="7a7be-137">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="7a7be-138">-BreakAll</span><span class="sxs-lookup"><span data-stu-id="7a7be-138">-BreakAll</span></span>

<span data-ttu-id="7a7be-139">{{Fill BreakAll Description}}</span><span class="sxs-lookup"><span data-stu-id="7a7be-139">{{ Fill BreakAll Description }}</span></span>

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

### <span data-ttu-id="7a7be-140">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="7a7be-140">CommonParameters</span></span>
<span data-ttu-id="7a7be-141">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7a7be-141">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7a7be-142">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="7a7be-142">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7a7be-143">Входные данные</span><span class="sxs-lookup"><span data-stu-id="7a7be-143">INPUTS</span></span>

### <span data-ttu-id="7a7be-144">System. Management. Automation. Ремотингжоб</span><span class="sxs-lookup"><span data-stu-id="7a7be-144">System.Management.Automation.RemotingJob</span></span>

## <span data-ttu-id="7a7be-145">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="7a7be-145">OUTPUTS</span></span>

## <span data-ttu-id="7a7be-146">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="7a7be-146">NOTES</span></span>

## <span data-ttu-id="7a7be-147">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="7a7be-147">RELATED LINKS</span></span>

[<span data-ttu-id="7a7be-148">Get-Job.</span><span class="sxs-lookup"><span data-stu-id="7a7be-148">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="7a7be-149">Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="7a7be-149">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="7a7be-150">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="7a7be-150">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="7a7be-151">Start-Job</span><span class="sxs-lookup"><span data-stu-id="7a7be-151">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="7a7be-152">Stop-Job.</span><span class="sxs-lookup"><span data-stu-id="7a7be-152">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="7a7be-153">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="7a7be-153">Wait-Job</span></span>](Wait-Job.md)

