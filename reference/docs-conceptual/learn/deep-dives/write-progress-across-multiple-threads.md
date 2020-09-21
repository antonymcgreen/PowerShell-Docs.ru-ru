---
title: Отображение хода выполнения при многопоточности
description: Использование Write-Progress для нескольких потоков с помощью Foreach-Object -Parallel
ms.date: 08/02/2020
ms.openlocfilehash: 909fc1bbdeded8845b1955e3384fb55db7173030
ms.sourcegitcommit: 640646992955116def23d16dd12c221857d37b68
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2020
ms.locfileid: "89410848"
---
# <a name="writing-progress-across-multiple-threads-with-foreach-parallel"></a>Запись хода выполнения для нескольких потоков с помощью Foreach Parallel

Начиная с PowerShell 7.0, возможность одновременной работы в нескольких потоках реализуется с помощью параметра **Parallel** в командлете [ForEach-Object](/powershell/module/Microsoft.PowerShell.Core/Foreach-Object). Однако наблюдение за ходом выполнения этих потоков может оказаться сложной задачей. Обычно вы можете отслеживать ход выполнения процесса с помощью [Write-Progress](/powershell/module/Microsoft.PowerShell.Utility/Write-Progress).
Но поскольку PowerShell использует отдельное пространство выполнения для каждого потока при использовании параметра **Parallel**, для передачи сведений о ходе выполнения обратно на узел недостаточно просто использовать `Write-Progress`.

## <a name="using-a-synced-hashtable-to-track-progress"></a>Использование синхронизированной хэш-таблицы для отслеживания хода выполнения

При записи хода выполнения из нескольких потоков отслеживание усложняется, поскольку при выполнении параллельных процессов в PowerShell каждый процесс имеет собственное пространство выполнения. Чтобы обойти эту особенность, можно использовать [синхронизированную хэш-таблицу](/dotnet/api/system.collections.hashtable.synchronized). Синхронизированная хэш-таблица представляет собой потокобезопасную структуру данных, которая может изменяться несколькими потоками одновременно без возникновения ошибки.

### <a name="set-up"></a>Настройка

Один из недостатков этого подхода заключается в том, что для безошибочной работы требуется довольно сложная настройка.

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

В этом разделе создаются три структуры данных для трех различных целей.

Переменная `$dataSet` хранит массив хэш-таблиц, который используется для координации дальнейших действий без риска изменения. При изменении коллекции объектов во время итерации по коллекции PowerShell выдает ошибку. Коллекция объектов должна существовать в цикле отдельно от изменяемых объектов. Ключ `Id` в каждой хэш-таблице — это идентификатор макета процесса. Ключ `Wait` моделирует рабочую нагрузку для каждого отслеживаемого макета процесса.

Переменная `$origin` сохраняет вложенную хэш-таблицу, в которой каждый ключ представляет собой идентификатор одного из макетов процесса.
Затем он используется для расконсервации синхронизированной хэш-таблицы, хранящейся в переменной `$sync`. Переменная `$sync` отвечает за сообщение о ходе выполнения обратно родительскому пространству выполнения, которое отображает ход выполнения.

### <a name="running-the-processes"></a>Выполнение процессов

В этом разделе запускаются многопоточные процессы и создаются выходные данные, используемые для отображения хода выполнения.

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

Макеты процесса отправляются в `Foreach-Object` и запускаются как задания. **ThrottleLimit** имеет значение **3**, чтобы указать выполнение нескольких процессов в очереди. Задания хранятся в переменной `$job`, и мы увидим, когда все процессы будут завершены.

При использовании оператора `using:` для ссылки на переменную родительской области в PowerShell нельзя сделать ее динамической с помощью выражений. Например, если вы попытались создать переменную `$process` таким образом, `$process = $using:sync.$($PSItem.id)`, может появиться сообщение об ошибке, в котором указано, что вы не можете использовать выражения. Таким образом, мы создаем переменную `$syncCopy`, которая может ссылаться на переменную `$sync` и изменять ее без риска сбоя.

Далее мы создаем хэш-таблицу для представления хода выполнения процесса, который в данный момент находится в цикле, с помощью переменной `$process`, ссылаясь на синхронизированные ключи хэш-таблицы. Ключи **действия** и **состояния** используются в качестве значений параметров для `Write-Progress`, чтобы отобразить состояние данного макета процесса в следующем разделе.

Цикл `foreach` — это просто способ имитировать рабочий процесс. Он сгенерирован случайным образом на основе атрибута `$dataSet` **Wait**, чтобы задать `Start-Sleep` в миллисекундах. Существуют разные способы вычисления хода выполнения процесса.

### <a name="displaying-the-progress-of-multiple-processes"></a>Отображение хода выполнения нескольких процессов

Теперь, когда макеты процесса выполняются как задания, мы можем начать записывать ход выполнения процессов в окно PowerShell.

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

Переменная `$job` содержит родительское **задание** и имеет дочернее **задание** для каждого из макетов процесса. Пока все дочерние задания выполняются, родительское задание будет иметь **состояние** "Выполнение". Это позволяет использовать цикл `while` для постоянного обновления хода выполнения каждого процесса до тех пор, пока все процессы не будут завершены.

В цикле while мы проходим по каждому из ключей в переменной `$sync`. Поскольку это синхронизированная хэш-таблица, она постоянно обновляется, но доступ к ней по-прежнему возможен без ошибок.

Можно убедиться, что процесс, о котором мы получаем сведения, на самом деле выполняется. Для этого используйте метод `IsNullOrEmpty()`. Если процесс не был запущен, цикл не будет сообщать о нем и будет переходить к следующему, пока не дойдет до запущенного процесса. Если процесс запущен, хэш-таблица из текущего ключа используется для передачи параметров в `Write-Progress`.

### <a name="full-example"></a>Полный пример

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

## <a name="related-links"></a>Связанные ссылки

- [about_Jobs](/powershell/module/Microsoft.PowerShell.Core/About/about_Jobs)
- [about_Scopes](/powershell/module/Microsoft.PowerShell.Core/About/about_Scopes)
- [about_Splatting](/powershell/module/Microsoft.PowerShell.Core/About/about_Splatting)
