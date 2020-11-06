---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/debug-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Debug-Job
ms.openlocfilehash: d36d15194ce1d4a48a59ad8bb8621b3c9c1a74ac
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226721"
---
# <span data-ttu-id="9f01a-103">Debug-Job</span><span class="sxs-lookup"><span data-stu-id="9f01a-103">Debug-Job</span></span>

## <span data-ttu-id="9f01a-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="9f01a-104">SYNOPSIS</span></span>
<span data-ttu-id="9f01a-105">Выполняет отладку выполняемого фонового, удаленного или рабочего процесса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9f01a-105">Debugs a running background, remote, or Windows PowerShell Workflow job.</span></span>

## <span data-ttu-id="9f01a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9f01a-106">SYNTAX</span></span>

### <span data-ttu-id="9f01a-107">Жобпараметерсет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="9f01a-107">JobParameterSet (Default)</span></span>

```
Debug-Job [-Job] <Job> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9f01a-108">жобнамепараметерсет</span><span class="sxs-lookup"><span data-stu-id="9f01a-108">JobNameParameterSet</span></span>

```
Debug-Job [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9f01a-109">жобидпараметерсет</span><span class="sxs-lookup"><span data-stu-id="9f01a-109">JobIdParameterSet</span></span>

```
Debug-Job [-Id] <Int32> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9f01a-110">жобинстанцеидпараметерсет</span><span class="sxs-lookup"><span data-stu-id="9f01a-110">JobInstanceIdParameterSet</span></span>

```
Debug-Job [-InstanceId] <Guid> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="9f01a-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9f01a-111">DESCRIPTION</span></span>
<span data-ttu-id="9f01a-112">Командлет **Debug-Job** позволяет выполнять отладку скриптов, выполняемых в заданиях.</span><span class="sxs-lookup"><span data-stu-id="9f01a-112">The **Debug-Job** cmdlet lets you debug scripts that are running within jobs.</span></span>
<span data-ttu-id="9f01a-113">Командлет предназначен для отладки заданий рабочего процесса Windows PowerShell, фоновых заданий и заданий, выполняемых в удаленных сеансах.</span><span class="sxs-lookup"><span data-stu-id="9f01a-113">The cmdlet is designed to debug Windows PowerShell Workflow jobs, background jobs, and jobs running in remote sessions.</span></span>
<span data-ttu-id="9f01a-114">**Debug — задание** принимает объект выполняемого задания, имя, идентификатор или идентификатор экземпляра в качестве входных данных и запускает сеанс отладки в выполняемом сценарии.</span><span class="sxs-lookup"><span data-stu-id="9f01a-114">**Debug-Job** accepts a running job object, name, ID, or instance ID as input, and starts a debugging session on the script it is running.</span></span>
<span data-ttu-id="9f01a-115">Команда **Quit** отладчика останавливает задание и запускает сценарий.</span><span class="sxs-lookup"><span data-stu-id="9f01a-115">The debugger **quit** command stops the job and running script.</span></span>
<span data-ttu-id="9f01a-116">Начиная с Windows PowerShell 5,0, команда **Exit** отсоединяет отладчик и позволяет продолжить выполнение задания.</span><span class="sxs-lookup"><span data-stu-id="9f01a-116">Starting in Windows PowerShell 5.0, the **exit** command detaches the debugger, and allows the job to continue to run.</span></span>

## <span data-ttu-id="9f01a-117">Примеры</span><span class="sxs-lookup"><span data-stu-id="9f01a-117">EXAMPLES</span></span>

### <span data-ttu-id="9f01a-118">Пример 1. Отладка задания по ИДЕНТИФИКАТОРу задания</span><span class="sxs-lookup"><span data-stu-id="9f01a-118">Example 1: Debug a job by job ID</span></span>

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

<span data-ttu-id="9f01a-119">Эта команда разбивается на выполняющееся задание с ИДЕНТИФИКАТОРом 3.</span><span class="sxs-lookup"><span data-stu-id="9f01a-119">This command breaks into a running job with an ID of 3.</span></span>

## <span data-ttu-id="9f01a-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9f01a-120">PARAMETERS</span></span>

### <span data-ttu-id="9f01a-121">-Id</span><span class="sxs-lookup"><span data-stu-id="9f01a-121">-Id</span></span>
<span data-ttu-id="9f01a-122">Указывает ИДЕНТИФИКАЦИОНный номер выполняемого задания.</span><span class="sxs-lookup"><span data-stu-id="9f01a-122">Specifies the ID number of a running job.</span></span>
<span data-ttu-id="9f01a-123">Чтобы получить ИДЕНТИФИКАЦИОНный номер задания, выполните командлет Get-Job.</span><span class="sxs-lookup"><span data-stu-id="9f01a-123">To get the ID number of a job, run the Get-Job cmdlet.</span></span>

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

### <span data-ttu-id="9f01a-124">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="9f01a-124">-InstanceId</span></span>
<span data-ttu-id="9f01a-125">Указывает идентификатор GUID экземпляра выполняющегося задания.</span><span class="sxs-lookup"><span data-stu-id="9f01a-125">Specifies the instance ID GUID of a running job.</span></span>
<span data-ttu-id="9f01a-126">Чтобы получить значение *InstanceId* задания, выполните командлет **Get-Job** , передав результаты в командлет **Format-** \*, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="9f01a-126">To get the *InstanceId* of a job, run the **Get-Job** cmdlet, piping the results into a **Format-** \* cmdlet, as shown in the following example:</span></span>

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

### <span data-ttu-id="9f01a-127">-Job</span><span class="sxs-lookup"><span data-stu-id="9f01a-127">-Job</span></span>
<span data-ttu-id="9f01a-128">Указывает выполняющийся объект задания.</span><span class="sxs-lookup"><span data-stu-id="9f01a-128">Specifies a running job object.</span></span>
<span data-ttu-id="9f01a-129">Самый простой способ использовать этот параметр — Сохранить результаты выполнения команды **Get-Job** , возвращающей выполняемое задание, которое необходимо отладить, в переменной, а затем указать переменную в качестве значения этого параметра.</span><span class="sxs-lookup"><span data-stu-id="9f01a-129">The simplest way to use this parameter is to save the results of a **Get-Job** command that returns the running job that you want to debug in a variable, and then specify the variable as the value of this parameter.</span></span>

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

### <span data-ttu-id="9f01a-130">-Name</span><span class="sxs-lookup"><span data-stu-id="9f01a-130">-Name</span></span>
<span data-ttu-id="9f01a-131">Указывает задание по понятному имени задания.</span><span class="sxs-lookup"><span data-stu-id="9f01a-131">Specifies a job by the friendly name of the job.</span></span>
<span data-ttu-id="9f01a-132">При запуске задания можно указать имя задания, добавив параметр *JobName* в командлетах, таких как Invoke-Command и Start-Job.</span><span class="sxs-lookup"><span data-stu-id="9f01a-132">When you start a job, you can specify a job name by adding the *JobName* parameter, in cmdlets such as Invoke-Command and Start-Job.</span></span>

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

### <span data-ttu-id="9f01a-133">-Confirm</span><span class="sxs-lookup"><span data-stu-id="9f01a-133">-Confirm</span></span>
<span data-ttu-id="9f01a-134">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="9f01a-134">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="9f01a-135">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="9f01a-135">-WhatIf</span></span>
<span data-ttu-id="9f01a-136">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="9f01a-136">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="9f01a-137">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="9f01a-137">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="9f01a-138">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="9f01a-138">CommonParameters</span></span>
<span data-ttu-id="9f01a-139">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="9f01a-139">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9f01a-140">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="9f01a-140">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9f01a-141">Входные данные</span><span class="sxs-lookup"><span data-stu-id="9f01a-141">INPUTS</span></span>

### <span data-ttu-id="9f01a-142">System. Management. Automation. Ремотингжоб</span><span class="sxs-lookup"><span data-stu-id="9f01a-142">System.Management.Automation.RemotingJob</span></span>

## <span data-ttu-id="9f01a-143">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="9f01a-143">OUTPUTS</span></span>

## <span data-ttu-id="9f01a-144">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="9f01a-144">NOTES</span></span>

## <span data-ttu-id="9f01a-145">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="9f01a-145">RELATED LINKS</span></span>

[<span data-ttu-id="9f01a-146">Get-Job.</span><span class="sxs-lookup"><span data-stu-id="9f01a-146">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="9f01a-147">Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="9f01a-147">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="9f01a-148">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="9f01a-148">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="9f01a-149">Resume-Job</span><span class="sxs-lookup"><span data-stu-id="9f01a-149">Resume-Job</span></span>](Resume-Job.md)

[<span data-ttu-id="9f01a-150">Start-Job</span><span class="sxs-lookup"><span data-stu-id="9f01a-150">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="9f01a-151">Stop-Job.</span><span class="sxs-lookup"><span data-stu-id="9f01a-151">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="9f01a-152">Suspend-Job</span><span class="sxs-lookup"><span data-stu-id="9f01a-152">Suspend-Job</span></span>](Suspend-Job.md)

[<span data-ttu-id="9f01a-153">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="9f01a-153">Wait-Job</span></span>](Wait-Job.md)