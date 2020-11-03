---
external help file: ThreadJob.dll-Help.xml
Locale: en-US
Module Name: ThreadJob
ms.date: 01/28/2020
online version: https://docs.microsoft.com/powershell/module/threadjob/start-threadjob?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-ThreadJob
ms.openlocfilehash: debe4002ec4d7ba7651f739316c4127243d8ebd3
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228913"
---
# <span data-ttu-id="aab05-102">Start-ThreadJob</span><span class="sxs-lookup"><span data-stu-id="aab05-102">Start-ThreadJob</span></span>

## <span data-ttu-id="aab05-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="aab05-103">SYNOPSIS</span></span>
<span data-ttu-id="aab05-104">Создает фоновые задания, аналогичные `Start-Job` командлету.</span><span class="sxs-lookup"><span data-stu-id="aab05-104">Creates background jobs similar to the `Start-Job` cmdlet.</span></span>

## <span data-ttu-id="aab05-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="aab05-105">SYNTAX</span></span>

### <span data-ttu-id="aab05-106">ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="aab05-106">ScriptBlock</span></span>

```
Start-ThreadJob [-ScriptBlock] <ScriptBlock> [-Name <String>] [-InitializationScript <ScriptBlock>]
 [-InputObject <PSObject>] [-ArgumentList <Object[]>] [-ThrottleLimit <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="aab05-107">FilePath</span><span class="sxs-lookup"><span data-stu-id="aab05-107">FilePath</span></span>

```
Start-ThreadJob [-FilePath] <String> [-Name <String>] [-InitializationScript <ScriptBlock>]
 [-InputObject <PSObject>] [-ArgumentList <Object[]>] [-ThrottleLimit <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="aab05-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="aab05-108">DESCRIPTION</span></span>

<span data-ttu-id="aab05-109">`Start-ThreadJob` создает фоновые задания, аналогичные `Start-Job` командлету.</span><span class="sxs-lookup"><span data-stu-id="aab05-109">`Start-ThreadJob` creates background jobs similar to the `Start-Job` cmdlet.</span></span> <span data-ttu-id="aab05-110">Основное отличие состоит в том, что создаваемые задания выполняются в отдельных потоках внутри локального процесса.</span><span class="sxs-lookup"><span data-stu-id="aab05-110">The main difference is that the jobs which are created run in separate threads within the local process.</span></span> <span data-ttu-id="aab05-111">По умолчанию задания используют текущий рабочий каталог вызывающей стороны, запустившего задание.</span><span class="sxs-lookup"><span data-stu-id="aab05-111">By default, the jobs use the current working directory of the caller that started the job.</span></span>

<span data-ttu-id="aab05-112">Командлет также поддерживает параметр **ThrottleLimit** для ограничения количества заданий, выполняемых в один момент времени.</span><span class="sxs-lookup"><span data-stu-id="aab05-112">The cmdlet also supports a **ThrottleLimit** parameter to limit the number of jobs running at one time.</span></span> <span data-ttu-id="aab05-113">По мере запуска заданий они ставятся в очередь и ожидают, пока текущее число заданий не станет меньше предельного значения регулирования.</span><span class="sxs-lookup"><span data-stu-id="aab05-113">As more jobs are started, they are queued and wait until the current number of jobs drops below the throttle limit.</span></span>

## <span data-ttu-id="aab05-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="aab05-114">EXAMPLES</span></span>

### <span data-ttu-id="aab05-115">Пример 1. Создание фоновых заданий с ограничением потока, равным 2</span><span class="sxs-lookup"><span data-stu-id="aab05-115">Example 1 - Create background jobs with a thread limit of 2</span></span>

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

### <span data-ttu-id="aab05-116">Пример 2. Сравнение производительности Start-Job и Start-ThreadJob</span><span class="sxs-lookup"><span data-stu-id="aab05-116">Example 2 - Compare the performance of Start-Job and Start-ThreadJob</span></span>

<span data-ttu-id="aab05-117">В этом примере показано различие между `Start-Job` и `Start-ThreadJob` .</span><span class="sxs-lookup"><span data-stu-id="aab05-117">This example shows the difference between `Start-Job` and `Start-ThreadJob`.</span></span> <span data-ttu-id="aab05-118">Задания запускают `Start-Sleep` командлет в течение 1 секунды.</span><span class="sxs-lookup"><span data-stu-id="aab05-118">The jobs run the `Start-Sleep` cmdlet for 1 second.</span></span> <span data-ttu-id="aab05-119">Так как задания выполняются параллельно, общее время выполнения составляет около 1 секунды, а также любое время, необходимое для создания заданий.</span><span class="sxs-lookup"><span data-stu-id="aab05-119">Since the jobs run in parallel, the total execution time is about 1 second, plus any time required to create the jobs.</span></span>

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

<span data-ttu-id="aab05-120">После вычитания 1 секунды для времени выполнения можно увидеть, что `Start-Job` для создания пяти заданий потребуется около 4,8 секунд.</span><span class="sxs-lookup"><span data-stu-id="aab05-120">After subtracting 1 second for execution time, you can see that `Start-Job` takes about 4.8 seconds to create five jobs.</span></span> <span data-ttu-id="aab05-121">`Start-ThreadJob` составляет 8 раз быстрее и занимает около 0,6 секунд для создания пяти заданий.</span><span class="sxs-lookup"><span data-stu-id="aab05-121">`Start-ThreadJob` is 8 times faster, taking about 0.6 seconds to create five jobs.</span></span> <span data-ttu-id="aab05-122">Результаты могут различаться в вашей среде, но относительное улучшение должно быть одинаковым.</span><span class="sxs-lookup"><span data-stu-id="aab05-122">The results may vary in your environment but the relative improvement should be the same.</span></span>

### <span data-ttu-id="aab05-123">Пример 3. Создание заданий с помощью InputObject</span><span class="sxs-lookup"><span data-stu-id="aab05-123">Example 3 - Create jobs using InputObject</span></span>

<span data-ttu-id="aab05-124">В этом примере блок скрипта использует `$input` переменную для получения входных данных из параметра **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="aab05-124">In this example, the script block uses the `$input` variable to receive input from the **InputObject** parameter.</span></span> <span data-ttu-id="aab05-125">Это также можно сделать с помощью конвейера объектов в `Start-ThreadJob` .</span><span class="sxs-lookup"><span data-stu-id="aab05-125">This can also be done by piping objects to `Start-ThreadJob`.</span></span>

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

## <span data-ttu-id="aab05-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="aab05-126">PARAMETERS</span></span>

### <span data-ttu-id="aab05-127">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="aab05-127">-ArgumentList</span></span>

<span data-ttu-id="aab05-128">Задает массив аргументов или значений параметров для скрипта, заданного параметрами **FilePath** или **ScriptBlock** .</span><span class="sxs-lookup"><span data-stu-id="aab05-128">Specifies an array of arguments, or parameter values, for the script that is specified by the **FilePath** or **ScriptBlock** parameters.</span></span>

<span data-ttu-id="aab05-129">**ArgumentList** должен быть последним параметром в командной строке.</span><span class="sxs-lookup"><span data-stu-id="aab05-129">**ArgumentList** must be the last parameter on the command line.</span></span> <span data-ttu-id="aab05-130">Все значения, следующие за именем параметра, являются интерпретированными значениями в списке аргументов.</span><span class="sxs-lookup"><span data-stu-id="aab05-130">All the values that follow the parameter name are interpreted values in the argument list.</span></span>

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

### <span data-ttu-id="aab05-131">-FilePath</span><span class="sxs-lookup"><span data-stu-id="aab05-131">-FilePath</span></span>

<span data-ttu-id="aab05-132">Указывает файл скрипта для запуска в качестве фонового задания.</span><span class="sxs-lookup"><span data-stu-id="aab05-132">Specifies a script file to run as a background job.</span></span> <span data-ttu-id="aab05-133">Введите путь и имя файла скрипта.</span><span class="sxs-lookup"><span data-stu-id="aab05-133">Enter the path and filename of the script.</span></span> <span data-ttu-id="aab05-134">Сценарий должен находиться на локальном компьютере или в папке, к которой может получить доступ локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="aab05-134">The script must be on the local computer or in a folder that the local computer can access.</span></span>

<span data-ttu-id="aab05-135">При использовании этого параметра PowerShell преобразует содержимое указанного файла скрипта в блок скрипта и запускает блок скрипта в качестве фонового задания.</span><span class="sxs-lookup"><span data-stu-id="aab05-135">When you use this parameter, PowerShell converts the contents of the specified script file to a script block and runs the script block as a background job.</span></span>

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

### <span data-ttu-id="aab05-136">-Инитиализатионскрипт</span><span class="sxs-lookup"><span data-stu-id="aab05-136">-InitializationScript</span></span>

<span data-ttu-id="aab05-137">Указывает команды, выполняемые перед запуском задания.</span><span class="sxs-lookup"><span data-stu-id="aab05-137">Specifies commands that run before the job starts.</span></span> <span data-ttu-id="aab05-138">Заключите команды в фигурные скобки ( `{}` ), чтобы создать блок скрипта.</span><span class="sxs-lookup"><span data-stu-id="aab05-138">Enclose the commands in braces (`{}`) to create a script block.</span></span>

<span data-ttu-id="aab05-139">Используйте этот параметр для подготовки сеанса, в рамках которого выполняется задание.</span><span class="sxs-lookup"><span data-stu-id="aab05-139">Use this parameter to prepare the session in which the job runs.</span></span> <span data-ttu-id="aab05-140">Например, его можно использовать для добавления функций и модулей в сеанс.</span><span class="sxs-lookup"><span data-stu-id="aab05-140">For example, you can use it to add functions and modules to the session.</span></span>

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

### <span data-ttu-id="aab05-141">-InputObject</span><span class="sxs-lookup"><span data-stu-id="aab05-141">-InputObject</span></span>

<span data-ttu-id="aab05-142">Указывает объекты, используемые в качестве входных данных для блока скрипта.</span><span class="sxs-lookup"><span data-stu-id="aab05-142">Specifies the objects used as input to the script block.</span></span> <span data-ttu-id="aab05-143">Он также позволяет выполнять входные данные конвейера.</span><span class="sxs-lookup"><span data-stu-id="aab05-143">It also allows for pipeline input.</span></span> <span data-ttu-id="aab05-144">Используйте `$input` автоматическую переменную в блоке скрипта для доступа к входным объектам.</span><span class="sxs-lookup"><span data-stu-id="aab05-144">Use the `$input` automatic variable in the script block to access the input objects.</span></span>

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

### <span data-ttu-id="aab05-145">-Name</span><span class="sxs-lookup"><span data-stu-id="aab05-145">-Name</span></span>

<span data-ttu-id="aab05-146">Указывает понятное имя нового задания.</span><span class="sxs-lookup"><span data-stu-id="aab05-146">Specifies a friendly name for the new job.</span></span> <span data-ttu-id="aab05-147">С помощью имени можно указать задание для других командлетов задания, например `Stop-Job` командлета.</span><span class="sxs-lookup"><span data-stu-id="aab05-147">You can use the name to identify the job to other job cmdlets, such as the `Stop-Job` cmdlet.</span></span>

<span data-ttu-id="aab05-148">Понятное имя по умолчанию — Job #, где "#" — порядковый номер, увеличивающийся для каждого задания.</span><span class="sxs-lookup"><span data-stu-id="aab05-148">The default friendly name is "Job#", where "#" is an ordinal number that is incremented for each job.</span></span>

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

### <span data-ttu-id="aab05-149">-ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="aab05-149">-ScriptBlock</span></span>

<span data-ttu-id="aab05-150">Указывает команды, которые нужно выполнить в фоновом задании.</span><span class="sxs-lookup"><span data-stu-id="aab05-150">Specifies the commands to run in the background job.</span></span> <span data-ttu-id="aab05-151">Заключите команды в фигурные скобки ( `{}` ), чтобы создать блок скрипта.</span><span class="sxs-lookup"><span data-stu-id="aab05-151">Enclose the commands in braces (`{}`) to create a script block.</span></span> <span data-ttu-id="aab05-152">Используйте `$Input` автоматическую переменную для доступа к значению параметра **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="aab05-152">Use the `$Input` automatic variable to access the value of the **InputObject** parameter.</span></span> <span data-ttu-id="aab05-153">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="aab05-153">This parameter is required.</span></span>

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

### <span data-ttu-id="aab05-154">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="aab05-154">-ThrottleLimit</span></span>

<span data-ttu-id="aab05-155">Этот параметр ограничивает количество заданий, выполняемых за один раз.</span><span class="sxs-lookup"><span data-stu-id="aab05-155">This parameter limits the number of jobs running at one time.</span></span> <span data-ttu-id="aab05-156">При запуске заданий они помещаются в очередь и ожидают, пока поток не будет доступен в пуле потоков для выполнения задания.</span><span class="sxs-lookup"><span data-stu-id="aab05-156">As jobs are started, they are queued and wait until a thread is available in the thread pool to run the job.</span></span> <span data-ttu-id="aab05-157">Ограничение по умолчанию — 5 потоков.</span><span class="sxs-lookup"><span data-stu-id="aab05-157">The default limit is 5 threads.</span></span>

<span data-ttu-id="aab05-158">Размер пула потоков является глобальным по отношению к сеансу PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aab05-158">The thread pool size is global to the PowerShell session.</span></span> <span data-ttu-id="aab05-159">Указание **ThrottleLimit** в одном вызове задает ограничение для последующих вызовов в одном сеансе.</span><span class="sxs-lookup"><span data-stu-id="aab05-159">Specifying a **ThrottleLimit** in one call sets the limit for subsequent calls in the same session.</span></span>

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

### <span data-ttu-id="aab05-160">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="aab05-160">CommonParameters</span></span>

<span data-ttu-id="aab05-161">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="aab05-161">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="aab05-162">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="aab05-162">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="aab05-163">Входные данные</span><span class="sxs-lookup"><span data-stu-id="aab05-163">INPUTS</span></span>

### <span data-ttu-id="aab05-164">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="aab05-164">System.Management.Automation.PSObject</span></span>

## <span data-ttu-id="aab05-165">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="aab05-165">OUTPUTS</span></span>

### <span data-ttu-id="aab05-166">Среаджоб. Среаджоб</span><span class="sxs-lookup"><span data-stu-id="aab05-166">ThreadJob.ThreadJob</span></span>

## <span data-ttu-id="aab05-167">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="aab05-167">NOTES</span></span>

## <span data-ttu-id="aab05-168">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="aab05-168">RELATED LINKS</span></span>

[<span data-ttu-id="aab05-169">Start-Job</span><span class="sxs-lookup"><span data-stu-id="aab05-169">Start-Job</span></span>](../Microsoft.PowerShell.Core/Start-Job.md)

[<span data-ttu-id="aab05-170">Stop-Job.</span><span class="sxs-lookup"><span data-stu-id="aab05-170">Stop-Job</span></span>](../Microsoft.PowerShell.Core/Stop-Job.md)

[<span data-ttu-id="aab05-171">Receive-Job.</span><span class="sxs-lookup"><span data-stu-id="aab05-171">Receive-Job</span></span>](../Microsoft.PowerShell.Core/Receive-Job.md)
