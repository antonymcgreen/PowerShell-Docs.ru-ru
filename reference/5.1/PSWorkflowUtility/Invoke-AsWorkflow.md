---
external help file: Microsoft.PowerShell.Workflow.ServiceCore.dll-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: PSWorkflowUtility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflowutility/invoke-asworkflow?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-AsWorkflow
ms.openlocfilehash: b96bce9fe4d574fe2b7e9c7c0f1e05ee0508adce
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93227342"
---
# <span data-ttu-id="01662-103">Invoke-AsWorkflow</span><span class="sxs-lookup"><span data-stu-id="01662-103">Invoke-AsWorkflow</span></span>

## <span data-ttu-id="01662-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="01662-104">SYNOPSIS</span></span>
<span data-ttu-id="01662-105">Выполняет команду или выражение как рабочий процесс Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="01662-105">Runs a command or expression as a Windows PowerShell Workflow.</span></span>

## <span data-ttu-id="01662-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="01662-106">SYNTAX</span></span>

### <span data-ttu-id="01662-107">Команда (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="01662-107">Command (Default)</span></span>

```
Invoke-AsWorkflow [-CommandName <String>] [-Parameter <Hashtable>] [-InputObject <Object>] [<CommonParameters>]
```

### <span data-ttu-id="01662-108">Expression</span><span class="sxs-lookup"><span data-stu-id="01662-108">Expression</span></span>

```
Invoke-AsWorkflow [-Expression <String>] [-InputObject <Object>] [<CommonParameters>]
```

## <span data-ttu-id="01662-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="01662-109">DESCRIPTION</span></span>

<span data-ttu-id="01662-110">`Invoke-AsWorkflow`Рабочий процесс запускает любую команду или выражение в качестве встроенного скрипта в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="01662-110">The `Invoke-AsWorkflow` workflow runs any command or expression as an inline script in a workflow.</span></span>
<span data-ttu-id="01662-111">Эти рабочие процессы используют стандартную семантику рабочих процессов, имеют все общие параметры рабочих процессов и обладают всеми преимуществами рабочих процессов, включая возможность остановки, возобновления и восстановления.</span><span class="sxs-lookup"><span data-stu-id="01662-111">These workflows use the standard workflow semantics, have all workflow common parameters, and have all benefits of workflows, including the ability to stop, resume, and recover.</span></span>

<span data-ttu-id="01662-112">Рабочие процессы предназначены для долго выполняющихся команд, которые осуществляют сбор критически важных данных, однако их можно использовать для выполнения любой команды.</span><span class="sxs-lookup"><span data-stu-id="01662-112">Workflows are designed for long-running commands that collect critical data, but can be used to run any command.</span></span>
<span data-ttu-id="01662-113">Дополнительные сведения см. в разделе [about_Workflows](../PSWorkflow/About/about_Workflows.md).</span><span class="sxs-lookup"><span data-stu-id="01662-113">For more information, see [about_Workflows](../PSWorkflow/About/about_Workflows.md).</span></span>

<span data-ttu-id="01662-114">В эту команду также можно добавить общие параметры рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="01662-114">You can also add workflow common parameters to this command.</span></span>
<span data-ttu-id="01662-115">Дополнительные сведения о общих параметрах рабочего процесса см. в разделе [about_WorkflowCommonParameters](../PSWorkflow/About/about_WorkflowCommonParameters.md)</span><span class="sxs-lookup"><span data-stu-id="01662-115">For more information about workflow common parameters, see [about_WorkflowCommonParameters](../PSWorkflow/About/about_WorkflowCommonParameters.md)</span></span>

<span data-ttu-id="01662-116">Этот рабочий процесс впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="01662-116">This workflow is introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="01662-117">Примеры</span><span class="sxs-lookup"><span data-stu-id="01662-117">EXAMPLES</span></span>

### <span data-ttu-id="01662-118">Пример 1. Запуск командлета в качестве рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="01662-118">Example 1: Run a cmdlet as a workflow</span></span>

```powershell
Invoke-AsWorkflow -PSComputerName (Get-Content Servers.txt) -CommandName Get-ExecutionPolicy
```

```output
PSComputerName                     PSSourceJobInstanceId                   Value
--------------                     ---------------------                   -----
Server01                           77b1cdf8-8226-4662-9067-cd2fa5c3b711    AllSigned
Server02                           a33542d7-3cdd-4339-ab99-0e7cd8e59462    Unrestricted
Server03                           279bac28-066a-4646-9497-8fcdcfe9757e    AllSigned
localhost                          0d858009-2cc4-47a4-a2e0-da17dc2883d0    RemoteSigned
```

<span data-ttu-id="01662-119">Эта команда запускает `Get-ExecutionPolicy` командлет в качестве рабочего процесса на сотнях компьютеров.</span><span class="sxs-lookup"><span data-stu-id="01662-119">This command runs the `Get-ExecutionPolicy` cmdlet as a workflow on hundreds of computers.</span></span>

<span data-ttu-id="01662-120">Команда использует параметр **CommandName** , чтобы указать командлет, выполняемый в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="01662-120">The command uses the **CommandName** parameter to specify the cmdlet that runs in the workflow.</span></span>
<span data-ttu-id="01662-121">Оно использует общий параметр **PSComputerName** рабочего процесса для указания компьютеров, на которых выполняется команда.</span><span class="sxs-lookup"><span data-stu-id="01662-121">It uses the **PSComputerName** workflow common parameter to specify the computers on which the command runs.</span></span>
<span data-ttu-id="01662-122">Значение параметра **PSComputerName** — это `Get-Content` команда, которая получает список имен компьютеров из файла Servers.txt.</span><span class="sxs-lookup"><span data-stu-id="01662-122">The value of the **PSComputerName** parameter is a `Get-Content` command that gets a list of computer names from the Servers.txt file.</span></span>
<span data-ttu-id="01662-123">Значение параметра заключается в круглые скобки, чтобы Windows PowerShell выполнял `Get-Command` команду перед использованием значения.</span><span class="sxs-lookup"><span data-stu-id="01662-123">The parameter value is enclosed in parentheses to direct Windows PowerShell to run the `Get-Command` command before using the value.</span></span>

<span data-ttu-id="01662-124">Как в случае со всеми удаленными командами, если команда выполняется на локальном компьютере (если локальный компьютер указан в значении параметра PSComputerName), необходимо запустить Windows PowerShell с помощью параметра "Запуск от имени администратора".</span><span class="sxs-lookup"><span data-stu-id="01662-124">As with all remote commands, if the command runs on the local computer, (if the value of the PSComputerName parameter includes the local computer), you must start Windows PowerShell with the "Run as administrator" option.</span></span>

### <span data-ttu-id="01662-125">Пример 2. Запуск командлета с параметрами</span><span class="sxs-lookup"><span data-stu-id="01662-125">Example 2: Run a cmdlet with parameters</span></span>

```powershell
$s = Import-Csv .\Servers.csv -Header ServerName, ServerID
Invoke-AsWorkflow -CommandName Get-ExecutionPolicy -Parameter @{Scope="Process"} -PSComputerName {$s.ServerName} -PSConnectionRetryCount 5
```

<span data-ttu-id="01662-126">Первая команда использует `Import-Csv` командлет для создания объекта из содержимого в файле Servers.csv.</span><span class="sxs-lookup"><span data-stu-id="01662-126">The first command uses the `Import-Csv` cmdlet to create an object from the content in the Servers.csv file.</span></span> <span data-ttu-id="01662-127">Команда использует параметр, `Header` чтобы создать `ServerName` свойство для столбца, содержащего имена конечных компьютеров, также известные как "Удаленные узлы".</span><span class="sxs-lookup"><span data-stu-id="01662-127">The command uses the `Header` parameter to create a `ServerName` property for the column that contains the names of the target computers, also known as "remote nodes."</span></span> <span data-ttu-id="01662-128">Команда сохраняет результат в `$s` переменной.</span><span class="sxs-lookup"><span data-stu-id="01662-128">The command saves the result in the `$s` variable.</span></span>

<span data-ttu-id="01662-129">Вторая команда использует `Invoke-AsWorkflow` Рабочий процесс для выполнения `Get-ExecutionPolicy` команды на компьютерах в Servers.csvном файле.</span><span class="sxs-lookup"><span data-stu-id="01662-129">The second command uses the `Invoke-AsWorkflow` workflow to run a `Get-ExecutionPolicy` command on the computers in the Servers.csv file.</span></span> <span data-ttu-id="01662-130">Команда использует параметр **CommandName** параметра, `Invoke-AsWorkflow`  чтобы указать команду для выполнения в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="01662-130">The command uses the **CommandName** parameter of `Invoke-AsWorkflow`  to specify the command to run in the workflow.</span></span> <span data-ttu-id="01662-131">В нем используется `Parameter` параметр класса `Invoke-AsWorkflow` для указания `Scope` параметра `Get-ExecutionPolicy` командлета со значением **Process** . Команда также использует `PSConnectionRetryCount` общий параметр рабочего процесса, чтобы ограничить число попыток выполнения команды пятью попытками на каждом компьютере и `PSComputerName` общий параметр рабочего процесса, чтобы указать имена удаленных узлов (конечных компьютеров).</span><span class="sxs-lookup"><span data-stu-id="01662-131">It uses the `Parameter` parameter of `Invoke-AsWorkflow` to specify the `Scope` parameter of the `Get-ExecutionPolicy` cmdlet with a value of **Process** .The command also uses the `PSConnectionRetryCount` workflow common parameter to limit the command to five attempts on each computer and the `PSComputerName` workflow common parameter to specify the names of the remote nodes (target computers).</span></span> <span data-ttu-id="01662-132">Значение `PSComputerName` параметра является выражением, которое получает `ServerName` свойство каждого объекта в `$s` переменной.</span><span class="sxs-lookup"><span data-stu-id="01662-132">The value of the `PSComputerName` parameter is an expression that gets the `ServerName` property of every object in the `$s` variable.</span></span>

<span data-ttu-id="01662-133">Эти команды выполняют `Get-ExecutionPolicy` команду как рабочий процесс на сотнях компьютеров.</span><span class="sxs-lookup"><span data-stu-id="01662-133">These commands run a `Get-ExecutionPolicy` command as a workflow on hundreds of computers.</span></span>
<span data-ttu-id="01662-134">Команда использует `Scope` параметр `Get-ExecutionPolicy` командлета со значением **Process** , чтобы получить политику выполнения в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="01662-134">The command uses the `Scope` parameter of the `Get-ExecutionPolicy` cmdlet with a value of **Process** to get the execution policy in the current session.</span></span>

### <span data-ttu-id="01662-135">Пример 3. Запуск выражения в качестве рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="01662-135">Example 3: Run an expression as a workflow</span></span>

```powershell
Invoke-AsWorkflow -Expression "ipconfig /all" -PSComputerName (Get-Content DomainControllers.txt) -AsJob -JobName IPConfig
```

```output
Id     Name          PSJobTypeName   State         HasMoreData   Location                Command
--     ----          -------------   -----         -----------   --------                -------
2      IpConfig      PSWorkflowJob   Completed     True          Server01, Server01...   Invoke-AsWorkflow
```

<span data-ttu-id="01662-136">Эта команда использует `Invoke-AsWorkflow` Рабочий процесс для выполнения команды ipconfig в качестве задания рабочего процесса на компьютерах, перечисленных в файле DomainControllers.txt.</span><span class="sxs-lookup"><span data-stu-id="01662-136">This command uses the `Invoke-AsWorkflow` workflow to run an Ipconfig command as a workflow job on the computers listed in the DomainControllers.txt file.</span></span>

<span data-ttu-id="01662-137">Команда использует параметр, `Expression` чтобы указать выражение для выполнения.</span><span class="sxs-lookup"><span data-stu-id="01662-137">The command uses the `Expression` parameter to specify the expression to run.</span></span>
<span data-ttu-id="01662-138">В нем используется `PSComputerName` общий параметр рабочего процесса для указания имен удаленных узлов (конечных компьютеров).</span><span class="sxs-lookup"><span data-stu-id="01662-138">It uses the `PSComputerName` workflow common parameter to specify the names of the remote nodes (target computers).</span></span>

<span data-ttu-id="01662-139">Команда также использует `AsJob` `JobName` Общие параметры рабочего процесса и для запуска рабочего процесса в качестве фонового задания на каждом компьютере с именем задания ipconfig.</span><span class="sxs-lookup"><span data-stu-id="01662-139">The command also uses the `AsJob` and `JobName` workflow common parameters to run the workflow as a background job on each computer with the "Ipconfig" job name.</span></span>

<span data-ttu-id="01662-140">Команда возвращает `ContainerParentJob` объект ( `System.Management.Automation.ContainerParentJob` ), содержащий задания рабочего процесса на каждом компьютере.</span><span class="sxs-lookup"><span data-stu-id="01662-140">The command returns a `ContainerParentJob` object (`System.Management.Automation.ContainerParentJob`) that contains the workflow jobs on each computer.</span></span>

## <span data-ttu-id="01662-141">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="01662-141">PARAMETERS</span></span>

### <span data-ttu-id="01662-142">-CommandName</span><span class="sxs-lookup"><span data-stu-id="01662-142">-CommandName</span></span>

<span data-ttu-id="01662-143">Выполняет указанный командлет или дополнительную функцию как рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="01662-143">Runs the specified cmdlet or advanced function as a workflow.</span></span>
<span data-ttu-id="01662-144">Введите имя командлета или функции, например `Update-Help` , `Set-ExecutionPolicy` или `Set-NetFirewallRule` .</span><span class="sxs-lookup"><span data-stu-id="01662-144">Enter the cmdlet or function name, such as `Update-Help`, `Set-ExecutionPolicy`, or `Set-NetFirewallRule`.</span></span>

```yaml
Type: System.String
Parameter Sets: Command
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="01662-145">-Expression</span><span class="sxs-lookup"><span data-stu-id="01662-145">-Expression</span></span>

<span data-ttu-id="01662-146">Указывает выражение, выполняемое этим командлетом в качестве рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="01662-146">Specifies the  expression that this cmdlet runs as a workflow.</span></span>
<span data-ttu-id="01662-147">Введите выражение в виде строки, например `"ipconfig /all"` .</span><span class="sxs-lookup"><span data-stu-id="01662-147">Enter the expression as a string, such as `"ipconfig /all"`.</span></span>
<span data-ttu-id="01662-148">Если выражение содержит пробелы или специальные символы, необходимо заключить его в кавычки.</span><span class="sxs-lookup"><span data-stu-id="01662-148">If the expression includes spaces or special characters, enclose the expression in quotation marks.</span></span>

```yaml
Type: System.String
Parameter Sets: Expression
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="01662-149">-Parameter</span><span class="sxs-lookup"><span data-stu-id="01662-149">-Parameter</span></span>

<span data-ttu-id="01662-150">Задает параметры и значения параметров команды, указанной в `CommandName` параметре.</span><span class="sxs-lookup"><span data-stu-id="01662-150">Specifies the parameters and parameter values of the command that is specified in the `CommandName` parameter.</span></span>
<span data-ttu-id="01662-151">Введите хэш-таблицу, в которой каждый ключ является именем параметра, а его значение — значением параметра, например `@{ExecutionPolicy="AllSigned"}` .</span><span class="sxs-lookup"><span data-stu-id="01662-151">Enter a hash table in which each key is a parameter name and its value is the parameter value, such as `@{ExecutionPolicy="AllSigned"}`.</span></span>

<span data-ttu-id="01662-152">Дополнительные сведения о хэш-таблицах см. в разделе [about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md).</span><span class="sxs-lookup"><span data-stu-id="01662-152">For information about hash tables, see [about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md).</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: Command
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="01662-153">-InputObject</span><span class="sxs-lookup"><span data-stu-id="01662-153">-InputObject</span></span>

<span data-ttu-id="01662-154">Используется, чтобы разрешить входные данные конвейера.</span><span class="sxs-lookup"><span data-stu-id="01662-154">Used to allows pipeline input.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="01662-155">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="01662-155">CommonParameters</span></span>

<span data-ttu-id="01662-156">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="01662-156">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="01662-157">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="01662-157">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

### <span data-ttu-id="01662-158">воркфловкоммонпараметерс</span><span class="sxs-lookup"><span data-stu-id="01662-158">WorkflowCommonParameters</span></span>

<span data-ttu-id="01662-159">Этот командлет также поддерживает общие параметры рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="01662-159">This cmdlet also supports workflow specific common parameters.</span></span>
<span data-ttu-id="01662-160">Дополнительные сведения см. в разделе [about_WorkflowCommonParameters](../PSWorkflow/About/about_WorkflowCommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="01662-160">For information, see [about_WorkflowCommonParameters](../PSWorkflow/About/about_WorkflowCommonParameters.md).</span></span>

## <span data-ttu-id="01662-161">Входные данные</span><span class="sxs-lookup"><span data-stu-id="01662-161">INPUTS</span></span>

### <span data-ttu-id="01662-162">System.Object</span><span class="sxs-lookup"><span data-stu-id="01662-162">System.Object</span></span>

<span data-ttu-id="01662-163">Любой объект можно передать в `InputObject` параметр.</span><span class="sxs-lookup"><span data-stu-id="01662-163">You can pipe any object to the `InputObject` parameter.</span></span>

## <span data-ttu-id="01662-164">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="01662-164">OUTPUTS</span></span>

### <span data-ttu-id="01662-165">Нет</span><span class="sxs-lookup"><span data-stu-id="01662-165">None</span></span>

<span data-ttu-id="01662-166">Эта команда не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="01662-166">This command does not generate any output.</span></span>
<span data-ttu-id="01662-167">Однако она запускает рабочий процесс, который может формировать выходные данные.</span><span class="sxs-lookup"><span data-stu-id="01662-167">However, it runs the workflow, which might generate output.</span></span>

## <span data-ttu-id="01662-168">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="01662-168">NOTES</span></span>

## <span data-ttu-id="01662-169">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="01662-169">RELATED LINKS</span></span>

[<span data-ttu-id="01662-170">New-PSWorkflowExecutionOption</span><span class="sxs-lookup"><span data-stu-id="01662-170">New-PSWorkflowExecutionOption</span></span>](../PSWorkflow/New-PSWorkflowExecutionOption.md)

[<span data-ttu-id="01662-171">New-PSWorkflowSession</span><span class="sxs-lookup"><span data-stu-id="01662-171">New-PSWorkflowSession</span></span>](../PSWorkflow/New-PSWorkflowSession.md)

[<span data-ttu-id="01662-172">about_Workflows</span><span class="sxs-lookup"><span data-stu-id="01662-172">about_Workflows</span></span>](../PSWorkflow/About/about_Workflows.md)

[<span data-ttu-id="01662-173">about_Workflow_Common_Parameters</span><span class="sxs-lookup"><span data-stu-id="01662-173">about_Workflow_Common_Parameters</span></span>](../PSWorkflow/About/about_WorkflowCommonParameters.md)
