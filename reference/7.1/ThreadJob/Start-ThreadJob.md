---
external help file: Microsoft.PowerShell.ThreadJob.dll-Help.xml
Locale: en-US
Module Name: ThreadJob
ms.date: 12/05/2020
online version: https://docs.microsoft.com/powershell/module/threadjob/start-threadjob?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-ThreadJob
ms.openlocfilehash: bced2b87c3843833414ebfd189d003e83af9718f
ms.sourcegitcommit: f9d855dd73b916559a22e337672dea3fbb11c634
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/07/2020
ms.locfileid: "96777753"
---
# <span data-ttu-id="1d537-102">Start-ThreadJob</span><span class="sxs-lookup"><span data-stu-id="1d537-102">Start-ThreadJob</span></span>

## <span data-ttu-id="1d537-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="1d537-103">SYNOPSIS</span></span>
<span data-ttu-id="1d537-104">Создает фоновые задания, аналогичные `Start-Job` командлету.</span><span class="sxs-lookup"><span data-stu-id="1d537-104">Creates background jobs similar to the `Start-Job` cmdlet.</span></span>

## <span data-ttu-id="1d537-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1d537-105">SYNTAX</span></span>

### <span data-ttu-id="1d537-106">ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="1d537-106">ScriptBlock</span></span>

```
Start-ThreadJob [-ScriptBlock] <ScriptBlock> [-Name <String>] [-InitializationScript <ScriptBlock>]
 [-InputObject <PSObject>] [-ArgumentList <Object[]>] [-ThrottleLimit <Int32>]
 [-StreamingHost <PSHost>] [<CommonParameters>]
```

### <span data-ttu-id="1d537-107">FilePath</span><span class="sxs-lookup"><span data-stu-id="1d537-107">FilePath</span></span>

```
Start-ThreadJob [-FilePath] <String> [-Name <String>] [-InitializationScript <ScriptBlock>]
 [-InputObject <PSObject>] [-ArgumentList <Object[]>] [-ThrottleLimit <Int32>]
 [-StreamingHost <PSHost>] [<CommonParameters>]
```

## <span data-ttu-id="1d537-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1d537-108">DESCRIPTION</span></span>

<span data-ttu-id="1d537-109">`Start-ThreadJob` создает фоновые задания, аналогичные `Start-Job` командлету.</span><span class="sxs-lookup"><span data-stu-id="1d537-109">`Start-ThreadJob` creates background jobs similar to the `Start-Job` cmdlet.</span></span> <span data-ttu-id="1d537-110">Основное отличие состоит в том, что создаваемые задания выполняются в отдельных потоках внутри локального процесса.</span><span class="sxs-lookup"><span data-stu-id="1d537-110">The main difference is that the jobs which are created run in separate threads within the local process.</span></span> <span data-ttu-id="1d537-111">По умолчанию задания используют текущий рабочий каталог вызывающей стороны, запустившего задание.</span><span class="sxs-lookup"><span data-stu-id="1d537-111">By default, the jobs use the current working directory of the caller that started the job.</span></span>

<span data-ttu-id="1d537-112">Командлет также поддерживает параметр **ThrottleLimit** для ограничения количества заданий, выполняемых в один момент времени.</span><span class="sxs-lookup"><span data-stu-id="1d537-112">The cmdlet also supports a **ThrottleLimit** parameter to limit the number of jobs running at one time.</span></span> <span data-ttu-id="1d537-113">По мере запуска заданий они ставятся в очередь и ожидают, пока текущее число заданий не станет меньше предельного значения регулирования.</span><span class="sxs-lookup"><span data-stu-id="1d537-113">As more jobs are started, they are queued and wait until the current number of jobs drops below the throttle limit.</span></span>

## <span data-ttu-id="1d537-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="1d537-114">EXAMPLES</span></span>

### <span data-ttu-id="1d537-115">Пример 1. Создание фоновых заданий с ограничением потока, равным 2</span><span class="sxs-lookup"><span data-stu-id="1d537-115">Example 1 - Create background jobs with a thread limit of 2</span></span>

```powershell
Start-ThreadJob -ScriptBlock { 1..100 | % { sleep 1; "Output $_" } } -ThrottleLimit 2
Start-ThreadJob -ScriptBlock { 1..100 | % { sleep 1; "Output $_" } }
Start-ThreadJob -ScriptBlock { 1..100 | % { sleep 1; "Output $_" } }
Get-Job
```

```Output
Id   Name   PSJobTypeName   State        HasMoreData   Location     Command
--   ----   -------------   -----        -----------   --------     -------
1    Job1   ThreadJob       Running      True          PowerShell   1..100 | % { sleep 1;...
2    Job2   ThreadJob       Running      True          PowerShell   1..100 | % { sleep 1;...
3    Job3   ThreadJob       NotStarted   False         PowerShell   1..100 | % { sleep 1;...
```

### <span data-ttu-id="1d537-116">Пример 2. Сравнение производительности Start-Job и Start-ThreadJob</span><span class="sxs-lookup"><span data-stu-id="1d537-116">Example 2 - Compare the performance of Start-Job and Start-ThreadJob</span></span>

<span data-ttu-id="1d537-117">В этом примере показано различие между `Start-Job` и `Start-ThreadJob` .</span><span class="sxs-lookup"><span data-stu-id="1d537-117">This example shows the difference between `Start-Job` and `Start-ThreadJob`.</span></span> <span data-ttu-id="1d537-118">Задания запускают `Start-Sleep` командлет в течение 1 секунды.</span><span class="sxs-lookup"><span data-stu-id="1d537-118">The jobs run the `Start-Sleep` cmdlet for 1 second.</span></span> <span data-ttu-id="1d537-119">Так как задания выполняются параллельно, общее время выполнения составляет около 1 секунды, а также любое время, необходимое для создания заданий.</span><span class="sxs-lookup"><span data-stu-id="1d537-119">Since the jobs run in parallel, the total execution time is about 1 second, plus any time required to create the jobs.</span></span>

```powershell
# start five background jobs each running 1 second
Measure-Command {1..5 | % {Start-Job {Start-Sleep 1}} | Wait-Job} | Select-Object TotalSeconds
Measure-Command {1..5 | % {Start-ThreadJob {Start-Sleep 1}} | Wait-Job} | Select-Object TotalSeconds
```

```Output
TotalSeconds
------------
   5.7665849
   1.5735008
```

<span data-ttu-id="1d537-120">После вычитания 1 секунды для времени выполнения можно увидеть, что `Start-Job` для создания пяти заданий потребуется около 4,8 секунд.</span><span class="sxs-lookup"><span data-stu-id="1d537-120">After subtracting 1 second for execution time, you can see that `Start-Job` takes about 4.8 seconds to create five jobs.</span></span> <span data-ttu-id="1d537-121">`Start-ThreadJob` составляет 8 раз быстрее и занимает около 0,6 секунд для создания пяти заданий.</span><span class="sxs-lookup"><span data-stu-id="1d537-121">`Start-ThreadJob` is 8 times faster, taking about 0.6 seconds to create five jobs.</span></span> <span data-ttu-id="1d537-122">Результаты могут различаться в вашей среде, но относительное улучшение должно быть одинаковым.</span><span class="sxs-lookup"><span data-stu-id="1d537-122">The results may vary in your environment but the relative improvement should be the same.</span></span>

### <span data-ttu-id="1d537-123">Пример 3. Создание заданий с помощью InputObject</span><span class="sxs-lookup"><span data-stu-id="1d537-123">Example 3 - Create jobs using InputObject</span></span>

<span data-ttu-id="1d537-124">В этом примере блок скрипта использует `$input` переменную для получения входных данных из параметра **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="1d537-124">In this example, the script block uses the `$input` variable to receive input from the **InputObject** parameter.</span></span> <span data-ttu-id="1d537-125">Это также можно сделать с помощью конвейера объектов в `Start-ThreadJob` .</span><span class="sxs-lookup"><span data-stu-id="1d537-125">This can also be done by piping objects to `Start-ThreadJob`.</span></span>

```powershell
$j = Start-ThreadJob -InputObject (Get-Process pwsh) -ScriptBlock { $input | Out-String }
$j | Wait-Job | Receive-Job
```

```Output
 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
     94   145.80     159.02      18.31   18276   1 pwsh
    101   163.30     222.05      29.00   35928   1 pwsh
```

```powershell
$j = Get-Process pwsh | Start-ThreadJob -ScriptBlock { $input | Out-String }
$j | Wait-Job | Receive-Job
```

```Output
 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
     94   145.80     159.02      18.31   18276   1 pwsh
    101   163.30     222.05      29.00   35928   1 pwsh
```

### <span data-ttu-id="1d537-126">Пример 4. вывод выходных данных задания в потоке на родительский узел</span><span class="sxs-lookup"><span data-stu-id="1d537-126">Example 4 - Stream job output to parent host</span></span>

<span data-ttu-id="1d537-127">С помощью параметра **стреамингхост** можно указать заданию перенаправление всех выходных данных узла на конкретный узел.</span><span class="sxs-lookup"><span data-stu-id="1d537-127">Using the **StreamingHost** parameter you can tell a job to direct all host output to a specific host.</span></span> <span data-ttu-id="1d537-128">Без этого параметра выходные данные передаются в коллекцию потока данных задания и не отображаются в консоли узла до тех пор, пока не будут получены выходные данные задания.</span><span class="sxs-lookup"><span data-stu-id="1d537-128">Without this parameter the output goes to the job data stream collection and doesn't appear in a host console until you receive the output from the job.</span></span>

<span data-ttu-id="1d537-129">В этом примере текущий узел передается `Start-ThreadJob` с помощью `$Host` автоматической переменной.</span><span class="sxs-lookup"><span data-stu-id="1d537-129">For this example, the current host is passed to `Start-ThreadJob` using the `$Host` automatic variable.</span></span>

```powershell
PS> Start-ThreadJob -ScriptBlock { Read-Host 'Say hello'; Write-Warning 'Warning output' } -StreamingHost $Host

Id   Name   PSJobTypeName   State         HasMoreData     Location      Command
--   ----   -------------   -----         -----------     --------      -------
7    Job7   ThreadJob       NotStarted    False           PowerShell    Read-Host 'Say hello'; �

PS> Say hello: Hello
WARNING: Warning output
PS> Receive-Job -Id 7
Hello
WARNING: Warning output
PS>
```

<span data-ttu-id="1d537-130">Обратите внимание, что отображается запрос из, `Read-Host` и вы можете ввести ввод.</span><span class="sxs-lookup"><span data-stu-id="1d537-130">Notice that the prompt from `Read-Host` is displayed and you are able to type input.</span></span> <span data-ttu-id="1d537-131">Затем отображается сообщение из `Write-Warning` .</span><span class="sxs-lookup"><span data-stu-id="1d537-131">Then, the message from `Write-Warning` is displayed.</span></span> <span data-ttu-id="1d537-132">`Receive-Job`Командлет возвращает все выходные данные задания.</span><span class="sxs-lookup"><span data-stu-id="1d537-132">The `Receive-Job` cmdlet returns all the output from the job.</span></span>

## <span data-ttu-id="1d537-133">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1d537-133">PARAMETERS</span></span>

### <span data-ttu-id="1d537-134">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="1d537-134">-ArgumentList</span></span>

<span data-ttu-id="1d537-135">Задает массив аргументов или значений параметров для скрипта, заданного параметрами **FilePath** или **ScriptBlock** .</span><span class="sxs-lookup"><span data-stu-id="1d537-135">Specifies an array of arguments, or parameter values, for the script that is specified by the **FilePath** or **ScriptBlock** parameters.</span></span>

<span data-ttu-id="1d537-136">**ArgumentList** должен быть последним параметром в командной строке.</span><span class="sxs-lookup"><span data-stu-id="1d537-136">**ArgumentList** must be the last parameter on the command line.</span></span> <span data-ttu-id="1d537-137">Все значения, следующие за именем параметра, являются интерпретированными значениями в списке аргументов.</span><span class="sxs-lookup"><span data-stu-id="1d537-137">All the values that follow the parameter name are interpreted values in the argument list.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1d537-138">-FilePath</span><span class="sxs-lookup"><span data-stu-id="1d537-138">-FilePath</span></span>

<span data-ttu-id="1d537-139">Указывает файл скрипта для запуска в качестве фонового задания.</span><span class="sxs-lookup"><span data-stu-id="1d537-139">Specifies a script file to run as a background job.</span></span> <span data-ttu-id="1d537-140">Введите путь и имя файла скрипта.</span><span class="sxs-lookup"><span data-stu-id="1d537-140">Enter the path and filename of the script.</span></span> <span data-ttu-id="1d537-141">Сценарий должен находиться на локальном компьютере или в папке, к которой может получить доступ локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="1d537-141">The script must be on the local computer or in a folder that the local computer can access.</span></span>

<span data-ttu-id="1d537-142">При использовании этого параметра PowerShell преобразует содержимое указанного файла скрипта в блок скрипта и запускает блок скрипта в качестве фонового задания.</span><span class="sxs-lookup"><span data-stu-id="1d537-142">When you use this parameter, PowerShell converts the contents of the specified script file to a script block and runs the script block as a background job.</span></span>

```yaml
Type: System.String
Parameter Sets: FilePath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1d537-143">-Инитиализатионскрипт</span><span class="sxs-lookup"><span data-stu-id="1d537-143">-InitializationScript</span></span>

<span data-ttu-id="1d537-144">Указывает команды, выполняемые перед запуском задания.</span><span class="sxs-lookup"><span data-stu-id="1d537-144">Specifies commands that run before the job starts.</span></span> <span data-ttu-id="1d537-145">Заключите команды в фигурные скобки ( `{}` ), чтобы создать блок скрипта.</span><span class="sxs-lookup"><span data-stu-id="1d537-145">Enclose the commands in braces (`{}`) to create a script block.</span></span>

<span data-ttu-id="1d537-146">Используйте этот параметр для подготовки сеанса, в рамках которого выполняется задание.</span><span class="sxs-lookup"><span data-stu-id="1d537-146">Use this parameter to prepare the session in which the job runs.</span></span> <span data-ttu-id="1d537-147">Например, его можно использовать для добавления функций и модулей в сеанс.</span><span class="sxs-lookup"><span data-stu-id="1d537-147">For example, you can use it to add functions and modules to the session.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1d537-148">-InputObject</span><span class="sxs-lookup"><span data-stu-id="1d537-148">-InputObject</span></span>

<span data-ttu-id="1d537-149">Указывает объекты, используемые в качестве входных данных для блока скрипта.</span><span class="sxs-lookup"><span data-stu-id="1d537-149">Specifies the objects used as input to the script block.</span></span> <span data-ttu-id="1d537-150">Он также позволяет выполнять входные данные конвейера.</span><span class="sxs-lookup"><span data-stu-id="1d537-150">It also allows for pipeline input.</span></span> <span data-ttu-id="1d537-151">Используйте `$input` автоматическую переменную в блоке скрипта для доступа к входным объектам.</span><span class="sxs-lookup"><span data-stu-id="1d537-151">Use the `$input` automatic variable in the script block to access the input objects.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="1d537-152">-Name</span><span class="sxs-lookup"><span data-stu-id="1d537-152">-Name</span></span>

<span data-ttu-id="1d537-153">Указывает понятное имя нового задания.</span><span class="sxs-lookup"><span data-stu-id="1d537-153">Specifies a friendly name for the new job.</span></span> <span data-ttu-id="1d537-154">С помощью имени можно указать задание для других командлетов задания, например `Stop-Job` командлета.</span><span class="sxs-lookup"><span data-stu-id="1d537-154">You can use the name to identify the job to other job cmdlets, such as the `Stop-Job` cmdlet.</span></span>

<span data-ttu-id="1d537-155">Понятное имя по умолчанию — Job #, где "#" — порядковый номер, увеличивающийся для каждого задания.</span><span class="sxs-lookup"><span data-stu-id="1d537-155">The default friendly name is "Job#", where "#" is an ordinal number that is incremented for each job.</span></span>

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

### <span data-ttu-id="1d537-156">-ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="1d537-156">-ScriptBlock</span></span>

<span data-ttu-id="1d537-157">Указывает команды, которые нужно выполнить в фоновом задании.</span><span class="sxs-lookup"><span data-stu-id="1d537-157">Specifies the commands to run in the background job.</span></span> <span data-ttu-id="1d537-158">Заключите команды в фигурные скобки ( `{}` ), чтобы создать блок скрипта.</span><span class="sxs-lookup"><span data-stu-id="1d537-158">Enclose the commands in braces (`{}`) to create a script block.</span></span> <span data-ttu-id="1d537-159">Используйте `$Input` автоматическую переменную для доступа к значению параметра **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="1d537-159">Use the `$Input` automatic variable to access the value of the **InputObject** parameter.</span></span> <span data-ttu-id="1d537-160">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="1d537-160">This parameter is required.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlock
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1d537-161">-Стреамингхост</span><span class="sxs-lookup"><span data-stu-id="1d537-161">-StreamingHost</span></span>

<span data-ttu-id="1d537-162">Этот параметр обеспечивает потокобезопасный способ, позволяющий передавать `Write-Host` выходные данные непосредственно в переданный объект **PSHost** .</span><span class="sxs-lookup"><span data-stu-id="1d537-162">This parameter provides a thread safe way to allow `Write-Host` output to go directly to the passed in **PSHost** object.</span></span> <span data-ttu-id="1d537-163">Без него выходные данные передаются в `Write-Host` коллекцию потока данных о задании и не отображаются в консоли узла до тех пор, пока не завершится выполнение заданий.</span><span class="sxs-lookup"><span data-stu-id="1d537-163">Without it, `Write-Host` output goes to the job information data stream collection and doesn't appear in a host console until after the jobs finish running.</span></span>

```yaml
Type: System.Management.Automation.Host.PSHost
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1d537-164">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="1d537-164">-ThrottleLimit</span></span>

<span data-ttu-id="1d537-165">Этот параметр ограничивает количество заданий, выполняемых за один раз.</span><span class="sxs-lookup"><span data-stu-id="1d537-165">This parameter limits the number of jobs running at one time.</span></span> <span data-ttu-id="1d537-166">При запуске заданий они помещаются в очередь и ожидают, пока поток не будет доступен в пуле потоков для выполнения задания.</span><span class="sxs-lookup"><span data-stu-id="1d537-166">As jobs are started, they are queued and wait until a thread is available in the thread pool to run the job.</span></span> <span data-ttu-id="1d537-167">Ограничение по умолчанию — 5 потоков.</span><span class="sxs-lookup"><span data-stu-id="1d537-167">The default limit is 5 threads.</span></span>

<span data-ttu-id="1d537-168">Размер пула потоков является глобальным по отношению к сеансу PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1d537-168">The thread pool size is global to the PowerShell session.</span></span> <span data-ttu-id="1d537-169">Указание **ThrottleLimit** в одном вызове задает ограничение для последующих вызовов в одном сеансе.</span><span class="sxs-lookup"><span data-stu-id="1d537-169">Specifying a **ThrottleLimit** in one call sets the limit for subsequent calls in the same session.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 5
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1d537-170">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="1d537-170">CommonParameters</span></span>

<span data-ttu-id="1d537-171">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1d537-171">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1d537-172">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1d537-172">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1d537-173">Входные данные</span><span class="sxs-lookup"><span data-stu-id="1d537-173">INPUTS</span></span>

### <span data-ttu-id="1d537-174">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="1d537-174">System.Management.Automation.PSObject</span></span>

## <span data-ttu-id="1d537-175">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="1d537-175">OUTPUTS</span></span>

### <span data-ttu-id="1d537-176">Среаджоб. Среаджоб</span><span class="sxs-lookup"><span data-stu-id="1d537-176">ThreadJob.ThreadJob</span></span>

## <span data-ttu-id="1d537-177">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="1d537-177">NOTES</span></span>

## <span data-ttu-id="1d537-178">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="1d537-178">RELATED LINKS</span></span>

[<span data-ttu-id="1d537-179">Start-Job</span><span class="sxs-lookup"><span data-stu-id="1d537-179">Start-Job</span></span>](../Microsoft.PowerShell.Core/Start-Job.md)

[<span data-ttu-id="1d537-180">Stop-Job.</span><span class="sxs-lookup"><span data-stu-id="1d537-180">Stop-Job</span></span>](../Microsoft.PowerShell.Core/Stop-Job.md)

[<span data-ttu-id="1d537-181">Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="1d537-181">Receive-Job</span></span>](../Microsoft.PowerShell.Core/Receive-Job.md)
