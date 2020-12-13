---
title: Отображение хода выполнения при многопоточности
description: Использование Write-Progress для нескольких потоков с помощью Foreach-Object -Parallel
ms.date: 08/02/2020
ms.openlocfilehash: 909fc1bbdeded8845b1955e3384fb55db7173030
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "89410848"
---
# <a name="writing-progress-across-multiple-threads-with-foreach-parallel"></a><span data-ttu-id="ad4b2-103">Запись хода выполнения для нескольких потоков с помощью Foreach Parallel</span><span class="sxs-lookup"><span data-stu-id="ad4b2-103">Writing Progress across multiple threads with Foreach Parallel</span></span>

<span data-ttu-id="ad4b2-104">Начиная с PowerShell 7.0, возможность одновременной работы в нескольких потоках реализуется с помощью параметра **Parallel** в командлете [ForEach-Object](/powershell/module/Microsoft.PowerShell.Core/Foreach-Object).</span><span class="sxs-lookup"><span data-stu-id="ad4b2-104">Starting in PowerShell 7.0, the ability to work in multiple threads simultaneously is possible using the **Parallel** parameter in the [Foreach-Object](/powershell/module/Microsoft.PowerShell.Core/Foreach-Object) cmdlet.</span></span> <span data-ttu-id="ad4b2-105">Однако наблюдение за ходом выполнения этих потоков может оказаться сложной задачей.</span><span class="sxs-lookup"><span data-stu-id="ad4b2-105">Monitoring the progress of these threads can be a challenge though.</span></span> <span data-ttu-id="ad4b2-106">Обычно вы можете отслеживать ход выполнения процесса с помощью [Write-Progress](/powershell/module/Microsoft.PowerShell.Utility/Write-Progress).</span><span class="sxs-lookup"><span data-stu-id="ad4b2-106">Normally, you can monitor the progress of a process using [Write-Progress](/powershell/module/Microsoft.PowerShell.Utility/Write-Progress).</span></span>
<span data-ttu-id="ad4b2-107">Но поскольку PowerShell использует отдельное пространство выполнения для каждого потока при использовании параметра **Parallel**, для передачи сведений о ходе выполнения обратно на узел недостаточно просто использовать `Write-Progress`.</span><span class="sxs-lookup"><span data-stu-id="ad4b2-107">However, since PowerShell uses a separate runspace for each thread when using **Parallel**, reporting the progress back to the host isn't as straight forward as normal use of `Write-Progress`.</span></span>

## <a name="using-a-synced-hashtable-to-track-progress"></a><span data-ttu-id="ad4b2-108">Использование синхронизированной хэш-таблицы для отслеживания хода выполнения</span><span class="sxs-lookup"><span data-stu-id="ad4b2-108">Using a synced hashtable to track progress</span></span>

<span data-ttu-id="ad4b2-109">При записи хода выполнения из нескольких потоков отслеживание усложняется, поскольку при выполнении параллельных процессов в PowerShell каждый процесс имеет собственное пространство выполнения.</span><span class="sxs-lookup"><span data-stu-id="ad4b2-109">When writing the progress from multiple threads, tracking becomes difficult because when running parallel processes in PowerShell, each process has it's own runspace.</span></span> <span data-ttu-id="ad4b2-110">Чтобы обойти эту особенность, можно использовать [синхронизированную хэш-таблицу](/dotnet/api/system.collections.hashtable.synchronized).</span><span class="sxs-lookup"><span data-stu-id="ad4b2-110">To get around this, you can use a [synchronized hashtable](/dotnet/api/system.collections.hashtable.synchronized).</span></span> <span data-ttu-id="ad4b2-111">Синхронизированная хэш-таблица представляет собой потокобезопасную структуру данных, которая может изменяться несколькими потоками одновременно без возникновения ошибки.</span><span class="sxs-lookup"><span data-stu-id="ad4b2-111">A synced hashtable is a thread safe data structure that can be modified by multiple threads simultaneously without throwing an error.</span></span>

### <a name="set-up"></a><span data-ttu-id="ad4b2-112">Настройка</span><span class="sxs-lookup"><span data-stu-id="ad4b2-112">Set up</span></span>

<span data-ttu-id="ad4b2-113">Один из недостатков этого подхода заключается в том, что для безошибочной работы требуется довольно сложная настройка.</span><span class="sxs-lookup"><span data-stu-id="ad4b2-113">One of the downsides to this approach is it takes a, somewhat, complex set up to ensure everything runs without error.</span></span>

```powershell
$dataset = @(
    @{
        Id   = 1
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
    @{
        Id   = 2
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
    @{
        Id   = 3
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
    @{
        Id   = 4
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
    @{
        Id   = 5
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
)

# Create a hashtable for process.
# Keys should be ID's of the processes
$origin = @{}
$dataset | Foreach-Object {$origin.($_.id) = @{}}

# Create synced hashtable
$sync = [System.Collections.Hashtable]::Synchronized($origin)
```

<span data-ttu-id="ad4b2-114">В этом разделе создаются три структуры данных для трех различных целей.</span><span class="sxs-lookup"><span data-stu-id="ad4b2-114">This section creates three different data structures, for three different purposes.</span></span>

<span data-ttu-id="ad4b2-115">Переменная `$dataSet` хранит массив хэш-таблиц, который используется для координации дальнейших действий без риска изменения.</span><span class="sxs-lookup"><span data-stu-id="ad4b2-115">The `$dataSet` variable stores an array of hashtables that is used to coordinate the next steps without the risk of being modified.</span></span> <span data-ttu-id="ad4b2-116">При изменении коллекции объектов во время итерации по коллекции PowerShell выдает ошибку.</span><span class="sxs-lookup"><span data-stu-id="ad4b2-116">If an object collection is modified while iterating through the collection, PowerShell throws an error.</span></span> <span data-ttu-id="ad4b2-117">Коллекция объектов должна существовать в цикле отдельно от изменяемых объектов.</span><span class="sxs-lookup"><span data-stu-id="ad4b2-117">You must keep the object collection in the loop separate from the objects being modified.</span></span> <span data-ttu-id="ad4b2-118">Ключ `Id` в каждой хэш-таблице — это идентификатор макета процесса.</span><span class="sxs-lookup"><span data-stu-id="ad4b2-118">The `Id` key in each hashtable is the identifier for a mock process.</span></span> <span data-ttu-id="ad4b2-119">Ключ `Wait` моделирует рабочую нагрузку для каждого отслеживаемого макета процесса.</span><span class="sxs-lookup"><span data-stu-id="ad4b2-119">The `Wait` key simulates the workload of each mock process being tracked.</span></span>

<span data-ttu-id="ad4b2-120">Переменная `$origin` сохраняет вложенную хэш-таблицу, в которой каждый ключ представляет собой идентификатор одного из макетов процесса.</span><span class="sxs-lookup"><span data-stu-id="ad4b2-120">The `$origin` variable stores a nested hashtable with each key being one of the mock process id's.</span></span>
<span data-ttu-id="ad4b2-121">Затем он используется для расконсервации синхронизированной хэш-таблицы, хранящейся в переменной `$sync`.</span><span class="sxs-lookup"><span data-stu-id="ad4b2-121">Then, it is used to hydrate the synchronized hashtable stored in the `$sync` variable.</span></span> <span data-ttu-id="ad4b2-122">Переменная `$sync` отвечает за сообщение о ходе выполнения обратно родительскому пространству выполнения, которое отображает ход выполнения.</span><span class="sxs-lookup"><span data-stu-id="ad4b2-122">The `$sync` variable is responsible for reporting the progress back to the parent runspace, which displays the progress.</span></span>

### <a name="running-the-processes"></a><span data-ttu-id="ad4b2-123">Выполнение процессов</span><span class="sxs-lookup"><span data-stu-id="ad4b2-123">Running the processes</span></span>

<span data-ttu-id="ad4b2-124">В этом разделе запускаются многопоточные процессы и создаются выходные данные, используемые для отображения хода выполнения.</span><span class="sxs-lookup"><span data-stu-id="ad4b2-124">This section runs the multi-threaded processes and creates some of the output used to display progress.</span></span>

```powershell
$job = $dataset | Foreach-Object -ThrottleLimit 3 -AsJob -Parallel {
    $syncCopy = $using:sync
    $process = $syncCopy.$($PSItem.Id)

    $process.Id = $PSItem.Id
    $process.Activity = "Id $($PSItem.Id) starting"
    $process.Status = "Processing"

    # Fake workload start up that takes x amount of time to complete
    start-sleep -Milliseconds ($PSItem.wait*5)

    # Process. update activity
    $process.Activity = "Id $($PSItem.id) processing"
    foreach ($percent in 1..100)
    {
        # Update process on status
        $process.Status = "Handling $percent/100"
        $process.PercentComplete = (($percent / 100) * 100)

        # Fake workload that takes x amount of time to complete
        Start-Sleep -Milliseconds $PSItem.Wait
    }

    # Mark process as completed
    $process.Completed = $true
}
```

<span data-ttu-id="ad4b2-125">Макеты процесса отправляются в `Foreach-Object` и запускаются как задания.</span><span class="sxs-lookup"><span data-stu-id="ad4b2-125">The mock processes are sent to `Foreach-Object` and started as jobs.</span></span> <span data-ttu-id="ad4b2-126">**ThrottleLimit** имеет значение **3**, чтобы указать выполнение нескольких процессов в очереди.</span><span class="sxs-lookup"><span data-stu-id="ad4b2-126">The **ThrottleLimit** is set to **3** to highlight running multiple processes in a queue.</span></span> <span data-ttu-id="ad4b2-127">Задания хранятся в переменной `$job`, и мы увидим, когда все процессы будут завершены.</span><span class="sxs-lookup"><span data-stu-id="ad4b2-127">The jobs are stored in the `$job` variable and allows us to know when all the processes have finished later on.</span></span>

<span data-ttu-id="ad4b2-128">При использовании оператора `using:` для ссылки на переменную родительской области в PowerShell нельзя сделать ее динамической с помощью выражений.</span><span class="sxs-lookup"><span data-stu-id="ad4b2-128">When using the `using:` statement to reference a parent scope variable in PowerShell, you can't use expressions to make it dynamic.</span></span> <span data-ttu-id="ad4b2-129">Например, если вы попытались создать переменную `$process` таким образом, `$process = $using:sync.$($PSItem.id)`, может появиться сообщение об ошибке, в котором указано, что вы не можете использовать выражения.</span><span class="sxs-lookup"><span data-stu-id="ad4b2-129">For example, if you tried to create the `$process` variable like this, `$process = $using:sync.$($PSItem.id)`, you would get an error stating you can't use expressions there.</span></span> <span data-ttu-id="ad4b2-130">Таким образом, мы создаем переменную `$syncCopy`, которая может ссылаться на переменную `$sync` и изменять ее без риска сбоя.</span><span class="sxs-lookup"><span data-stu-id="ad4b2-130">So, we create the `$syncCopy` variable to be able to reference and modify the `$sync` variable without the risk of it failing.</span></span>

<span data-ttu-id="ad4b2-131">Далее мы создаем хэш-таблицу для представления хода выполнения процесса, который в данный момент находится в цикле, с помощью переменной `$process`, ссылаясь на синхронизированные ключи хэш-таблицы.</span><span class="sxs-lookup"><span data-stu-id="ad4b2-131">Next, we build out a hashtable to represent the progress of the process currently in the loop using the `$process` variable by referencing the synchronized hashtable keys.</span></span> <span data-ttu-id="ad4b2-132">Ключи **действия** и **состояния** используются в качестве значений параметров для `Write-Progress`, чтобы отобразить состояние данного макета процесса в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="ad4b2-132">The **Activity** and the **Status** keys are used as parameter values for `Write-Progress` to display the status of a given mock process in the next section.</span></span>

<span data-ttu-id="ad4b2-133">Цикл `foreach` — это просто способ имитировать рабочий процесс. Он сгенерирован случайным образом на основе атрибута `$dataSet` **Wait**, чтобы задать `Start-Sleep` в миллисекундах.</span><span class="sxs-lookup"><span data-stu-id="ad4b2-133">The `foreach` loop is just a way to simulate the process working and is randomized based on the `$dataSet` **Wait** attribute to set `Start-Sleep` using milliseconds.</span></span> <span data-ttu-id="ad4b2-134">Существуют разные способы вычисления хода выполнения процесса.</span><span class="sxs-lookup"><span data-stu-id="ad4b2-134">How you calculate the progress of your process may vary.</span></span>

### <a name="displaying-the-progress-of-multiple-processes"></a><span data-ttu-id="ad4b2-135">Отображение хода выполнения нескольких процессов</span><span class="sxs-lookup"><span data-stu-id="ad4b2-135">Displaying the progress of multiple processes</span></span>

<span data-ttu-id="ad4b2-136">Теперь, когда макеты процесса выполняются как задания, мы можем начать записывать ход выполнения процессов в окно PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ad4b2-136">Now that the mock processes are running as jobs, we can start to write the processes progress to the PowerShell window.</span></span>

```powershell
while($job.State -eq 'Running')
{
    $sync.Keys | Foreach-Object {
        # If key is not defined, ignore
        if(![string]::IsNullOrEmpty($sync.$_.keys))
        {
            # Create parameter hashtable to splat
            $param = $sync.$_

            # Execute Write-Progress
            Write-Progress @param
        }
    }

    # Wait to refresh to not overload gui
    Start-Sleep -Seconds 0.1
}
```

<span data-ttu-id="ad4b2-137">Переменная `$job` содержит родительское **задание** и имеет дочернее **задание** для каждого из макетов процесса.</span><span class="sxs-lookup"><span data-stu-id="ad4b2-137">The `$job` variable contains the parent **job** and has a child **job** for each of the mock processes.</span></span> <span data-ttu-id="ad4b2-138">Пока все дочерние задания выполняются, родительское задание будет иметь **состояние** "Выполнение".</span><span class="sxs-lookup"><span data-stu-id="ad4b2-138">While any of the child jobs are still running, the parent job **State** will remain "Running".</span></span> <span data-ttu-id="ad4b2-139">Это позволяет использовать цикл `while` для постоянного обновления хода выполнения каждого процесса до тех пор, пока все процессы не будут завершены.</span><span class="sxs-lookup"><span data-stu-id="ad4b2-139">This allows us to use the `while` loop to continually update the progress of every process until all processes are finished.</span></span>

<span data-ttu-id="ad4b2-140">В цикле while мы проходим по каждому из ключей в переменной `$sync`.</span><span class="sxs-lookup"><span data-stu-id="ad4b2-140">Within the while loop, we loop through each of the keys in the `$sync` variable.</span></span> <span data-ttu-id="ad4b2-141">Поскольку это синхронизированная хэш-таблица, она постоянно обновляется, но доступ к ней по-прежнему возможен без ошибок.</span><span class="sxs-lookup"><span data-stu-id="ad4b2-141">Since this is a synchronized hashtable, it is constantly updated but can still be accessed without throwing any errors.</span></span>

<span data-ttu-id="ad4b2-142">Можно убедиться, что процесс, о котором мы получаем сведения, на самом деле выполняется. Для этого используйте метод `IsNullOrEmpty()`.</span><span class="sxs-lookup"><span data-stu-id="ad4b2-142">There is a check to ensure that the process being reported is actually running using the `IsNullOrEmpty()` method.</span></span> <span data-ttu-id="ad4b2-143">Если процесс не был запущен, цикл не будет сообщать о нем и будет переходить к следующему, пока не дойдет до запущенного процесса.</span><span class="sxs-lookup"><span data-stu-id="ad4b2-143">If the process hasn't been started, the loop won't report on it and move on to the next until it gets to a process that has been started.</span></span> <span data-ttu-id="ad4b2-144">Если процесс запущен, хэш-таблица из текущего ключа используется для передачи параметров в `Write-Progress`.</span><span class="sxs-lookup"><span data-stu-id="ad4b2-144">If the process is started, the hashtable from the current key is used to splat the parameters to `Write-Progress`.</span></span>

### <a name="full-example"></a><span data-ttu-id="ad4b2-145">Полный пример</span><span class="sxs-lookup"><span data-stu-id="ad4b2-145">Full example</span></span>

```powershell
# Example workload
$dataset = @(
    @{
        Id   = 1
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
    @{
        Id   = 2
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
    @{
        Id   = 3
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
    @{
        Id   = 4
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
    @{
        Id   = 5
        Wait = 3..10 | get-random | Foreach-Object {$_*100}
    }
)

# Create a hashtable for process.
# Keys should be ID's of the processes
$origin = @{}
$dataset | Foreach-Object {$origin.($_.id) = @{}}

# Create synced hashtable
$sync = [System.Collections.Hashtable]::Synchronized($origin)

$job = $dataset | Foreach-Object -ThrottleLimit 3 -AsJob -Parallel {
    $syncCopy = $using:sync
    $process = $syncCopy.$($PSItem.Id)

    $process.Id = $PSItem.Id
    $process.Activity = "Id $($PSItem.Id) starting"
    $process.Status = "Processing"

    # Fake workload start up that takes x amount of time to complete
    start-sleep -Milliseconds ($PSItem.wait*5)

    # Process. update activity
    $process.Activity = "Id $($PSItem.id) processing"
    foreach ($percent in 1..100)
    {
        # Update process on status
        $process.Status = "Handling $percent/100"
        $process.PercentComplete = (($percent / 100) * 100)

        # Fake workload that takes x amount of time to complete
        Start-Sleep -Milliseconds $PSItem.Wait
    }

    # Mark process as completed
    $process.Completed = $true
}

while($job.State -eq 'Running')
{
    $sync.Keys | Foreach-Object {
        # If key is not defined, ignore
        if(![string]::IsNullOrEmpty($sync.$_.keys))
        {
            # Create parameter hashtable to splat
            $param = $sync.$_

            # Execute Write-Progress
            Write-Progress @param
        }
    }

    # Wait to refresh to not overload gui
    Start-Sleep -Seconds 0.1
}
```

## <a name="related-links"></a><span data-ttu-id="ad4b2-146">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="ad4b2-146">Related Links</span></span>

- [<span data-ttu-id="ad4b2-147">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="ad4b2-147">about_Jobs</span></span>](/powershell/module/Microsoft.PowerShell.Core/About/about_Jobs)
- [<span data-ttu-id="ad4b2-148">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="ad4b2-148">about_Scopes</span></span>](/powershell/module/Microsoft.PowerShell.Core/About/about_Scopes)
- [<span data-ttu-id="ad4b2-149">about_Splatting</span><span class="sxs-lookup"><span data-stu-id="ad4b2-149">about_Splatting</span></span>](/powershell/module/Microsoft.PowerShell.Core/About/about_Splatting)
