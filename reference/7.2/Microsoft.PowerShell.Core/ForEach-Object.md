---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 09/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/foreach-object?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ForEach-Object
ms.openlocfilehash: 8a79dcf9c2af7aed0c52c361467cab23f880a893
ms.sourcegitcommit: fb9bafd041e3615b9dc9fb77c9245581b705cd02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2020
ms.locfileid: "99605531"
---
# <span data-ttu-id="b0df8-102">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="b0df8-102">ForEach-Object</span></span>

## <span data-ttu-id="b0df8-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="b0df8-103">Synopsis</span></span>
<span data-ttu-id="b0df8-104">Выполняет операцию для каждого элемента в коллекции входных объектов.</span><span class="sxs-lookup"><span data-stu-id="b0df8-104">Performs an operation against each item in a collection of input objects.</span></span>

## <span data-ttu-id="b0df8-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b0df8-105">Syntax</span></span>

### <span data-ttu-id="b0df8-106">Скриптблокксет (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="b0df8-106">ScriptBlockSet (Default)</span></span>

```
ForEach-Object [-InputObject <PSObject>] [-Begin <ScriptBlock>] [-Process] <ScriptBlock[]>
 [-End <ScriptBlock>] [-RemainingScripts <ScriptBlock[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="b0df8-107">пропертяндмесодсет</span><span class="sxs-lookup"><span data-stu-id="b0df8-107">PropertyAndMethodSet</span></span>

```
ForEach-Object [-InputObject <PSObject>] [-MemberName] <String> [-ArgumentList <Object[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="b0df8-108">параллелпараметерсет</span><span class="sxs-lookup"><span data-stu-id="b0df8-108">ParallelParameterSet</span></span>

```
ForEach-Object -Parallel <scriptblock> [-InputObject <PSObject>] [-ThrottleLimit <int>]
[-UseNewRunspace] [-TimeoutSeconds <int>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="b0df8-109">Описание</span><span class="sxs-lookup"><span data-stu-id="b0df8-109">Description</span></span>

<span data-ttu-id="b0df8-110">`ForEach-Object`Командлет выполняет операцию над каждым элементом в коллекции входных объектов.</span><span class="sxs-lookup"><span data-stu-id="b0df8-110">The `ForEach-Object` cmdlet performs an operation on each item in a collection of input objects.</span></span> <span data-ttu-id="b0df8-111">Входные объекты можно передать в командлет или указать с помощью параметра **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="b0df8-111">The input objects can be piped to the cmdlet or specified by using the **InputObject** parameter.</span></span>

<span data-ttu-id="b0df8-112">Начиная с Windows PowerShell 3,0 существует два разных способа создания `ForEach-Object` команды.</span><span class="sxs-lookup"><span data-stu-id="b0df8-112">Starting in Windows PowerShell 3.0, there are two different ways to construct a `ForEach-Object` command.</span></span>

- <span data-ttu-id="b0df8-113">**Блок скрипта**.</span><span class="sxs-lookup"><span data-stu-id="b0df8-113">**Script block**.</span></span> <span data-ttu-id="b0df8-114">Можно использовать блок скрипта, чтобы указать операцию.</span><span class="sxs-lookup"><span data-stu-id="b0df8-114">You can use a script block to specify the operation.</span></span> <span data-ttu-id="b0df8-115">В блоке скрипта используйте `$_` переменную для представления текущего объекта.</span><span class="sxs-lookup"><span data-stu-id="b0df8-115">Within the script block, use the `$_` variable to represent the current object.</span></span> <span data-ttu-id="b0df8-116">Блок скрипта — это значение параметра **Process**.</span><span class="sxs-lookup"><span data-stu-id="b0df8-116">The script block is the value of the **Process** parameter.</span></span> <span data-ttu-id="b0df8-117">Блок скрипта может содержать любой сценарий PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b0df8-117">The script block can contain any PowerShell script.</span></span>

  <span data-ttu-id="b0df8-118">Например, следующая команда возвращает значение свойства **ProcessName** каждого процесса на компьютере.</span><span class="sxs-lookup"><span data-stu-id="b0df8-118">For example, the following command gets the value of the **ProcessName** property of each process on the computer.</span></span>

  `Get-Process | ForEach-Object {$_.ProcessName}`

  <span data-ttu-id="b0df8-119">`ForEach-Object` поддерживает `begin` блоки, `process` и, `end` как описано в разделе [about_functions](about/about_functions.md#piping-objects-to-functions).</span><span class="sxs-lookup"><span data-stu-id="b0df8-119">`ForEach-Object` supports the `begin`, `process`, and `end` blocks as described in [about_functions](about/about_functions.md#piping-objects-to-functions).</span></span>

  > [!NOTE]
  > <span data-ttu-id="b0df8-120">Блоки скрипта выполняются в области действия вызывающего объекта.</span><span class="sxs-lookup"><span data-stu-id="b0df8-120">The script blocks run in the caller's scope.</span></span> <span data-ttu-id="b0df8-121">Поэтому блоки имеют доступ к переменным в этой области и могут создавать новые переменные, которые сохраняются в этой области после завершения выполнения командлета.</span><span class="sxs-lookup"><span data-stu-id="b0df8-121">Therefore the blocks have access to variables in that scope and can create new variables that persist in that scope after the cmdlet completes.</span></span>

- <span data-ttu-id="b0df8-122">**Оператор Operation**.</span><span class="sxs-lookup"><span data-stu-id="b0df8-122">**Operation statement**.</span></span> <span data-ttu-id="b0df8-123">Можно также написать оператор операции, который гораздо более похож на естественный язык.</span><span class="sxs-lookup"><span data-stu-id="b0df8-123">You can also write an operation statement, which is much more like natural language.</span></span> <span data-ttu-id="b0df8-124">С помощью инструкции операции можно указать значение свойства или вызвать метод.</span><span class="sxs-lookup"><span data-stu-id="b0df8-124">You can use the operation statement to specify a property value or call a method.</span></span> <span data-ttu-id="b0df8-125">Инструкции операций появились в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="b0df8-125">Operation statements were introduced in Windows PowerShell 3.0.</span></span>

  <span data-ttu-id="b0df8-126">Например, следующая команда также возвращает значение свойства **ProcessName** каждого процесса на компьютере.</span><span class="sxs-lookup"><span data-stu-id="b0df8-126">For example, the following command also gets the value of the **ProcessName** property of each process on the computer.</span></span>

  `Get-Process | ForEach-Object ProcessName`

- <span data-ttu-id="b0df8-127">**Параллельный выполняющийся блок сценария**.</span><span class="sxs-lookup"><span data-stu-id="b0df8-127">**Parallel running script block**.</span></span> <span data-ttu-id="b0df8-128">Начиная с PowerShell 7,0, доступен третий набор параметров, который выполняет каждый блок сценария параллельно.</span><span class="sxs-lookup"><span data-stu-id="b0df8-128">Beginning with PowerShell 7.0, a third parameter set is available that runs each script block in parallel.</span></span> <span data-ttu-id="b0df8-129">Параметр **ThrottleLimit** ограничивает количество параллельных скриптов, выполняемых за раз.</span><span class="sxs-lookup"><span data-stu-id="b0df8-129">The **ThrottleLimit** parameter limits the number of parallel scripts running at a time.</span></span> <span data-ttu-id="b0df8-130">Как и ранее, используйте `$_` переменную для представления текущего входного объекта в блоке script.</span><span class="sxs-lookup"><span data-stu-id="b0df8-130">As before, use the `$_` variable to represent the current input object in the script block.</span></span> <span data-ttu-id="b0df8-131">Используйте `$using:` ключевое слово для передачи ссылок на переменные в выполняемый скрипт.</span><span class="sxs-lookup"><span data-stu-id="b0df8-131">Use the `$using:` keyword to pass variable references to the running script.</span></span>

  <span data-ttu-id="b0df8-132">В PowerShell 7 создается новое пространство выполнения для каждой итерации цикла, чтобы обеспечить максимальную изоляцию.</span><span class="sxs-lookup"><span data-stu-id="b0df8-132">In PowerShell 7, a new runspace is created for each loop iteration to ensure maximum isolation.</span></span>
  <span data-ttu-id="b0df8-133">Это может быть большой производительностью и достижением ресурсов, если работа, которую вы выполняете, невелика по сравнению с созданием новых пространств выполнения или большим количеством итераций, выполняющих значительную работу.</span><span class="sxs-lookup"><span data-stu-id="b0df8-133">This can be a large performance and resource hit if the work you are doing is small compared to creating new runspaces or if there are a lot of iterations performing significant work.</span></span> <span data-ttu-id="b0df8-134">По умолчанию для PowerShell 7,1 пространства выполнения из пула с пространством выполнением используются повторно.</span><span class="sxs-lookup"><span data-stu-id="b0df8-134">As of PowerShell 7.1, runspaces from a runspace pool are reused by default.</span></span> <span data-ttu-id="b0df8-135">Размер пула пространства выполнения определяется параметром **ThrottleLimit** .</span><span class="sxs-lookup"><span data-stu-id="b0df8-135">The runspace pool size is specified by the **ThrottleLimit** parameter.</span></span> <span data-ttu-id="b0df8-136">Размер пула пространства выполнения по умолчанию равен 5.</span><span class="sxs-lookup"><span data-stu-id="b0df8-136">The default runspace pool size is 5.</span></span> <span data-ttu-id="b0df8-137">Вы по-прежнему можете создать новое пространство выполнения для каждой итерации с помощью параметра **усеневрунспаце** .</span><span class="sxs-lookup"><span data-stu-id="b0df8-137">You can still create a new runspace for each iteration using the **UseNewRunspace** switch.</span></span>

  <span data-ttu-id="b0df8-138">По умолчанию параллельный скриптблоккс использует текущий рабочий каталог вызывающей стороны, который запустил параллельные задачи.</span><span class="sxs-lookup"><span data-stu-id="b0df8-138">By default, the parallel scriptblocks use the current working directory of the caller that started the parallel tasks.</span></span>

  <span data-ttu-id="b0df8-139">Неустранимые ошибки записываются в поток ошибок командлета, как это происходит при параллельном выполнении скриптблоккс.</span><span class="sxs-lookup"><span data-stu-id="b0df8-139">Non-terminating errors are written to the cmdlet error stream as they occur in parallel running scriptblocks.</span></span> <span data-ttu-id="b0df8-140">Так как невозможно определить порядок выполнения параллельного сценария ScriptBlock, порядок, в котором ошибки отображаются в потоке ошибок, является случайным.</span><span class="sxs-lookup"><span data-stu-id="b0df8-140">Because parallel scriptblock execution order cannot be determined, the order in which errors appear in the error stream is random.</span></span> <span data-ttu-id="b0df8-141">Аналогичным образом сообщения, записанные в другие потоки данных, такие как предупреждения, подробные сведения или информация, записываются в потоки данных в неопределенном порядке.</span><span class="sxs-lookup"><span data-stu-id="b0df8-141">Likewise, messages written to other data streams, like warning, verbose, or information are written to those data streams in an indeterminate order.</span></span>

  <span data-ttu-id="b0df8-142">Завершающие ошибки, такие как исключения, завершают отдельный параллельный экземпляр скриптблоккс, в котором они происходят.</span><span class="sxs-lookup"><span data-stu-id="b0df8-142">Terminating errors, such as exceptions, terminate the individual parallel instance of the scriptblocks in which they occur.</span></span> <span data-ttu-id="b0df8-143">Завершающая ошибка в одном скриптблоккс может не привести к завершению `Foreach-Object` командлета.</span><span class="sxs-lookup"><span data-stu-id="b0df8-143">A terminating error in one scriptblocks may not cause the termination of the `Foreach-Object` cmdlet.</span></span> <span data-ttu-id="b0df8-144">Другие скриптблоккс, выполняющиеся параллельно, продолжают работать, пока не возникнет завершающей ошибки.</span><span class="sxs-lookup"><span data-stu-id="b0df8-144">The other scriptblocks, running in parallel, continue to run unless they also encounter a terminating error.</span></span> <span data-ttu-id="b0df8-145">Завершающая ошибка записывается в поток данных об ошибке как **ерроррекорд** с **фулликуалифиедеррорид** `PSTaskException` .</span><span class="sxs-lookup"><span data-stu-id="b0df8-145">The terminating error is written to the error data stream as an **ErrorRecord** with a **FullyQualifiedErrorId** of `PSTaskException`.</span></span>
  <span data-ttu-id="b0df8-146">Завершающие ошибки могут быть преобразованы в неустранимые ошибки с помощью блоков try/catch или ловушек PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b0df8-146">Terminating errors can be converted to non-terminating errors using PowerShell try/catch or trap blocks.</span></span>

## <span data-ttu-id="b0df8-147">Примеры</span><span class="sxs-lookup"><span data-stu-id="b0df8-147">Examples</span></span>

### <span data-ttu-id="b0df8-148">Пример 1. деление целых чисел в массиве</span><span class="sxs-lookup"><span data-stu-id="b0df8-148">Example 1: Divide integers in an array</span></span>

<span data-ttu-id="b0df8-149">Этот пример принимает массив из трех целых чисел и делит каждый из них на 1024.</span><span class="sxs-lookup"><span data-stu-id="b0df8-149">This example takes an array of three integers and divides each one of them by 1024.</span></span>

```powershell
30000, 56798, 12432 | ForEach-Object -Process {$_/1024}
```

```Output
29.296875
55.466796875
12.140625
```

### <span data-ttu-id="b0df8-150">Пример 2. Получение длины всех файлов в каталоге</span><span class="sxs-lookup"><span data-stu-id="b0df8-150">Example 2: Get the length of all the files in a directory</span></span>

<span data-ttu-id="b0df8-151">В этом примере выполняется обработка файлов и каталогов в каталоге установки PowerShell `$PSHOME` .</span><span class="sxs-lookup"><span data-stu-id="b0df8-151">This example processes the files and directories in the PowerShell installation directory `$PSHOME`.</span></span>

```powershell
Get-ChildItem $PSHOME |
  ForEach-Object -Process {if (!$_.PSIsContainer) {$_.Name; $_.Length / 1024; " " }}
```

<span data-ttu-id="b0df8-152">Если объект не является каталогом, блок скрипта получает имя файла, делит значение его свойства **length** на 1024 и добавляет пробел (""), чтобы отделить его от следующей записи.</span><span class="sxs-lookup"><span data-stu-id="b0df8-152">If the object is not a directory, the script block gets the name of the file, divides the value of its **Length** property by 1024, and adds a space (" ") to separate it from the next entry.</span></span> <span data-ttu-id="b0df8-153">Командлет использует свойство **PSISContainer** , чтобы определить, является ли объект каталогом.</span><span class="sxs-lookup"><span data-stu-id="b0df8-153">The cmdlet uses the **PSISContainer** property to determine whether an object is a directory.</span></span>

### <span data-ttu-id="b0df8-154">Пример 3. Эксплуатация с самыми последними системными событиями</span><span class="sxs-lookup"><span data-stu-id="b0df8-154">Example 3: Operate on the most recent System events</span></span>

<span data-ttu-id="b0df8-155">Этот пример записывает 1000 последних событий из журнала системных событий в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="b0df8-155">This example writes the 1000 most recent events from the System event log to a text file.</span></span> <span data-ttu-id="b0df8-156">Текущее время отображается до и после обработки событий.</span><span class="sxs-lookup"><span data-stu-id="b0df8-156">The current time is displayed before and after processing the events.</span></span>

```powershell
$Events = Get-EventLog -LogName System -Newest 1000
$events | ForEach-Object -Begin {Get-Date} -Process {Out-File -FilePath Events.txt -Append -InputObject $_.Message} -End {Get-Date}
```

<span data-ttu-id="b0df8-157">`Get-EventLog` Возвращает 1000 последних событий из журнала системных событий и сохраняет их в `$Events` переменной.</span><span class="sxs-lookup"><span data-stu-id="b0df8-157">`Get-EventLog` gets the 1000 most recent events from the System event log and stores them in the `$Events` variable.</span></span> <span data-ttu-id="b0df8-158">`$Events` затем передается в `ForEach-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="b0df8-158">`$Events` is then piped to the `ForEach-Object` cmdlet.</span></span> <span data-ttu-id="b0df8-159">Параметр **Begin** используется для отображения текущей даты и времени.</span><span class="sxs-lookup"><span data-stu-id="b0df8-159">The **Begin** parameter displays the current date and time.</span></span> <span data-ttu-id="b0df8-160">Затем параметр **Process** использует `Out-File` командлет для создания текстового файла с именем events.txt и сохраняет свойство Message каждого события в этом файле.</span><span class="sxs-lookup"><span data-stu-id="b0df8-160">Next, the **Process** parameter uses the `Out-File` cmdlet to create a text file that is named events.txt and stores the message property of each of the events in that file.</span></span> <span data-ttu-id="b0df8-161">Наконец, параметр **End** используется для отображения даты и времени после завершения обработки.</span><span class="sxs-lookup"><span data-stu-id="b0df8-161">Last, the **End** parameter is used to display the date and time after all of the processing has completed.</span></span>

### <span data-ttu-id="b0df8-162">Пример 4. изменение значения раздела реестра</span><span class="sxs-lookup"><span data-stu-id="b0df8-162">Example 4: Change the value of a Registry key</span></span>

<span data-ttu-id="b0df8-163">Этот пример изменяет значение записи реестра **RemotePath** во всех подразделах `HKCU:\Network` раздела на верхний.</span><span class="sxs-lookup"><span data-stu-id="b0df8-163">This example changes the value of the **RemotePath** registry entry in all of the subkeys under the `HKCU:\Network` key to uppercase text.</span></span>

```powershell
Get-ItemProperty -Path HKCU:\Network\* |
  ForEach-Object {Set-ItemProperty -Path $_.PSPath -Name RemotePath -Value $_.RemotePath.ToUpper();}
```

<span data-ttu-id="b0df8-164">Этот формат можно использовать для изменения формы или содержимого раздела реестра.</span><span class="sxs-lookup"><span data-stu-id="b0df8-164">You can use this format to change the form or content of a registry entry value.</span></span>

<span data-ttu-id="b0df8-165">Каждый подраздел в ключе **сети** представляет сопоставленный сетевой диск, который повторно подключается при входе.</span><span class="sxs-lookup"><span data-stu-id="b0df8-165">Each subkey in the **Network** key represents a mapped network drive that reconnects at sign on.</span></span> <span data-ttu-id="b0df8-166">Запись **RemotePath** содержит UNC-путь подключенного диска.</span><span class="sxs-lookup"><span data-stu-id="b0df8-166">The **RemotePath** entry contains the UNC path of the connected drive.</span></span> <span data-ttu-id="b0df8-167">Например, если подключить диск E: к `\\Server\Share` , в параметре реестра  RemotePath будет создан подраздел e `HKCU:\Network` со значением  `\\Server\Share` .</span><span class="sxs-lookup"><span data-stu-id="b0df8-167">For example, if you map the E: drive to `\\Server\Share`, an **E** subkey is created in `HKCU:\Network` with the **RemotePath** registry value set to `\\Server\Share`.</span></span>

<span data-ttu-id="b0df8-168">Команда использует командлет, `Get-ItemProperty` чтобы получить все подразделы **сетевого** ключа и `Set-ItemProperty` командлета, чтобы изменить значение записи реестра **RemotePath** в каждом разделе.</span><span class="sxs-lookup"><span data-stu-id="b0df8-168">The command uses the `Get-ItemProperty` cmdlet to get all of the subkeys of the **Network** key and the `Set-ItemProperty` cmdlet to change the value of the **RemotePath** registry entry in each key.</span></span>
<span data-ttu-id="b0df8-169">В `Set-ItemProperty` команде путь является значением свойства **PSPath** раздела реестра.</span><span class="sxs-lookup"><span data-stu-id="b0df8-169">In the `Set-ItemProperty` command, the path is the value of the **PSPath** property of the registry key.</span></span> <span data-ttu-id="b0df8-170">Это свойство объекта Microsoft .NET Framework, представляющего раздел реестра, а не запись реестра.</span><span class="sxs-lookup"><span data-stu-id="b0df8-170">This is a property of the Microsoft .NET Framework object that represents the registry key, not a registry entry.</span></span> <span data-ttu-id="b0df8-171">Команда использует метод **ToUpper ()** значения **RemotePath** , который является строкой (REG_SZ).</span><span class="sxs-lookup"><span data-stu-id="b0df8-171">The command uses the **ToUpper()** method of the **RemotePath** value, which is a string (REG_SZ).</span></span>

<span data-ttu-id="b0df8-172">Поскольку `Set-ItemProperty` изменяет свойство каждого ключа, `ForEach-Object` для доступа к свойству необходим командлет.</span><span class="sxs-lookup"><span data-stu-id="b0df8-172">Because `Set-ItemProperty` is changing the property of each key, the `ForEach-Object` cmdlet is required to access the property.</span></span>

### <span data-ttu-id="b0df8-173">Пример 5. Использование автоматической переменной $Null</span><span class="sxs-lookup"><span data-stu-id="b0df8-173">Example 5: Use the $Null automatic variable</span></span>

<span data-ttu-id="b0df8-174">В этом примере показан результат передачи `$Null` автоматической переменной в `ForEach-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="b0df8-174">This example shows the effect of piping the `$Null` automatic variable to the `ForEach-Object` cmdlet.</span></span>

```powershell
1, 2, $null, 4 | ForEach-Object {"Hello"}
```

```Output
Hello
Hello
Hello
Hello
```

<span data-ttu-id="b0df8-175">Так как PowerShell обрабатывает значение null как явный заполнитель, `ForEach-Object` командлет создает значение для `$Null` , точно так же, как и для других объектов, которые вы выполняете по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="b0df8-175">Because PowerShell treats null as an explicit placeholder, the `ForEach-Object` cmdlet generates a value for `$Null`, just as it does for other objects that you pipe to it.</span></span>

### <span data-ttu-id="b0df8-176">Пример 6. Получение значений свойств</span><span class="sxs-lookup"><span data-stu-id="b0df8-176">Example 6: Get property values</span></span>

<span data-ttu-id="b0df8-177">Этот пример возвращает значение свойства **path** для всех установленных модулей PowerShell с помощью параметра **MemberName** `ForEach-Object` командлета.</span><span class="sxs-lookup"><span data-stu-id="b0df8-177">This example gets the value of the **Path** property of all installed PowerShell modules by using the **MemberName** parameter of the `ForEach-Object` cmdlet.</span></span>

```powershell
Get-Module -ListAvailable | ForEach-Object -MemberName Path
Get-Module -ListAvailable | Foreach Path
```

<span data-ttu-id="b0df8-178">Вторая команда эквивалента первой.</span><span class="sxs-lookup"><span data-stu-id="b0df8-178">The second command is equivalent to the first.</span></span> <span data-ttu-id="b0df8-179">Он использует `Foreach` псевдоним `ForEach-Object` командлета и опускает имя параметра **MemberName** , которое является необязательным.</span><span class="sxs-lookup"><span data-stu-id="b0df8-179">It uses the `Foreach` alias of the `ForEach-Object` cmdlet and omits the name of the **MemberName** parameter, which is optional.</span></span>

<span data-ttu-id="b0df8-180">`ForEach-Object`Командлет полезен для получения значений свойств, так как он получает значение без изменения типа, в отличие от командлетов **Format** или `Select-Object` командлетов, которые изменяют тип значения свойства.</span><span class="sxs-lookup"><span data-stu-id="b0df8-180">The `ForEach-Object` cmdlet is useful for getting property values, because it gets the value without changing the type, unlike the **Format** cmdlets or the `Select-Object` cmdlet, which change the property value type.</span></span>

### <span data-ttu-id="b0df8-181">Пример 7. разбиение имен модулей по именам компонентов</span><span class="sxs-lookup"><span data-stu-id="b0df8-181">Example 7: Split module names into component names</span></span>

<span data-ttu-id="b0df8-182">В этом примере показано три способа разбиения двух разделенных точками имен модулей в имена их компонентов.</span><span class="sxs-lookup"><span data-stu-id="b0df8-182">This example shows three ways to split two dot-separated module names into their component names.</span></span>

```powershell
"Microsoft.PowerShell.Core", "Microsoft.PowerShell.Host" | ForEach-Object {$_.Split(".")}
"Microsoft.PowerShell.Core", "Microsoft.PowerShell.Host" | ForEach-Object -MemberName Split -ArgumentList "."
"Microsoft.PowerShell.Core", "Microsoft.PowerShell.Host" | Foreach Split "."
```

```Output
Microsoft
PowerShell
Core
Microsoft
PowerShell
Host
```

<span data-ttu-id="b0df8-183">Команда вызывает метод **Split** строк.</span><span class="sxs-lookup"><span data-stu-id="b0df8-183">The commands call the **Split** method of strings.</span></span> <span data-ttu-id="b0df8-184">Три команды используют различный синтаксис, но они эквивалентны и являются взаимозаменяемыми.</span><span class="sxs-lookup"><span data-stu-id="b0df8-184">The three commands use different syntax, but they are equivalent and interchangeable.</span></span>

<span data-ttu-id="b0df8-185">Первая команда использует традиционный синтаксис, который включает блок сценария и текущий оператор Object `$_` .</span><span class="sxs-lookup"><span data-stu-id="b0df8-185">The first command uses the traditional syntax, which includes a script block and the current object operator `$_`.</span></span> <span data-ttu-id="b0df8-186">Точечный синтаксис применяется для указания метода, а аргумент разделителя заключается в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="b0df8-186">It uses the dot syntax to specify the method and parentheses to enclose the delimiter argument.</span></span>

<span data-ttu-id="b0df8-187">Вторая команда использует параметр **MemberName**, чтобы указать метод **Split**, и параметр **ArgumentName** для определения точки (".") в качестве разделителя разбиения.</span><span class="sxs-lookup"><span data-stu-id="b0df8-187">The second command uses the **MemberName** parameter to specify the **Split** method and the **ArgumentName** parameter to identify the dot (".") as the split delimiter.</span></span>

<span data-ttu-id="b0df8-188">Третья команда использует псевдоним **foreach** `ForEach-Object` командлета и опускает имена параметров **MemberName** и **ArgumentList** , которые являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="b0df8-188">The third command uses the **Foreach** alias of the `ForEach-Object` cmdlet and omits the names of the **MemberName** and **ArgumentList** parameters, which are optional.</span></span>

### <span data-ttu-id="b0df8-189">Пример 8. Использование ForEach-Object с двумя блоками сценариев</span><span class="sxs-lookup"><span data-stu-id="b0df8-189">Example 8: Using ForEach-Object with two script blocks</span></span>

<span data-ttu-id="b0df8-190">В этом примере мы передаем два блока сценариев по положению.</span><span class="sxs-lookup"><span data-stu-id="b0df8-190">In this example, we pass two script blocks positionally.</span></span> <span data-ttu-id="b0df8-191">Все блоки скрипта привязываются к параметру **Process** .</span><span class="sxs-lookup"><span data-stu-id="b0df8-191">All the script blocks bind to the **Process** parameter.</span></span> <span data-ttu-id="b0df8-192">Однако они обрабатываются так, как будто они были переданы в параметры **Begin** и **Process** .</span><span class="sxs-lookup"><span data-stu-id="b0df8-192">However, they are treated as if they had been passed to the **Begin** and **Process** parameters.</span></span>

```powershell
1..2 | ForEach-Object { 'begin' } { 'process' }
```

```Output
begin
process
process
```

### <span data-ttu-id="b0df8-193">Пример 9. Использование ForEach-Object с более чем двумя блоками сценариев</span><span class="sxs-lookup"><span data-stu-id="b0df8-193">Example 9: Using ForEach-Object with more than two script blocks</span></span>

<span data-ttu-id="b0df8-194">В этом примере мы передаем два блока сценариев по положению.</span><span class="sxs-lookup"><span data-stu-id="b0df8-194">In this example, we pass two script blocks positionally.</span></span> <span data-ttu-id="b0df8-195">Все блоки скрипта привязываются к параметру **Process** .</span><span class="sxs-lookup"><span data-stu-id="b0df8-195">All the script blocks bind to the **Process** parameter.</span></span> <span data-ttu-id="b0df8-196">Однако они обрабатываются так, как будто они были переданы в параметры **Begin**, **Process** и **End** .</span><span class="sxs-lookup"><span data-stu-id="b0df8-196">However, they are treated as if they had been passed to the **Begin**, **Process**, and **End** parameters.</span></span>

```powershell
1..2 | ForEach-Object { 'begin' } { 'process A' }  { 'process B' }  { 'end' }
```

```Output
begin
process A
process B
process A
process B
end
```

> [!NOTE]
> <span data-ttu-id="b0df8-197">Первый блок сценария всегда сопоставляется с `begin` блоком, последний блок сопоставляется с `end` блоком, а все блоки между ними сопоставлены с `process` блоком.</span><span class="sxs-lookup"><span data-stu-id="b0df8-197">The first script block is always mapped to the `begin` block, the last block is mapped to the `end` block, and the blocks in between are all mapped to the `process` block.</span></span>

### <span data-ttu-id="b0df8-198">Пример 10. Запуск нескольких блоков скрипта для каждого элемента конвейера</span><span class="sxs-lookup"><span data-stu-id="b0df8-198">Example 10: Run multiple script blocks for each pipeline item</span></span>

<span data-ttu-id="b0df8-199">Как показано в предыдущем примере, несколько блоков скрипта, переданных с помощью параметра **Process** , сопоставляются с параметрами **Begin** и **End** .</span><span class="sxs-lookup"><span data-stu-id="b0df8-199">As shown in the previous example, multiple script blocks passed using the **Process** parameter get mapped to the **Begin** and **End** parameters.</span></span> <span data-ttu-id="b0df8-200">Чтобы избежать этого сопоставления, необходимо предоставить явные значения для параметров **Begin** и **End** .</span><span class="sxs-lookup"><span data-stu-id="b0df8-200">To avoid this mapping, you must provide explicit values for the **Begin** and **End** parameters.</span></span>

```powershell
1..2 | ForEach-Object -Begin $null -Process { 'one' }, { 'two' }, { 'three' } -End $null
```

```Output
one
two
three
one
two
three
```

### <span data-ttu-id="b0df8-201">Пример 11. Запуск сценария с задержкой в параллельных пакетах</span><span class="sxs-lookup"><span data-stu-id="b0df8-201">Example 11: Run slow script in parallel batches</span></span>

<span data-ttu-id="b0df8-202">В этом примере выполняется простой блок скрипта, который вычисляет строку и заждет одну секунду.</span><span class="sxs-lookup"><span data-stu-id="b0df8-202">This example runs a simple script block that evaluates a string and sleeps for one second.</span></span>

```powershell
$Message = "Output:"

1..8 | ForEach-Object -Parallel {
    "$using:Message $_"
    Start-Sleep 1
} -ThrottleLimit 4
```

```Output
Output: 1
Output: 2
Output: 3
Output: 4
Output: 5
Output: 6
Output: 7
Output: 8
```

<span data-ttu-id="b0df8-203">Значение параметра **ThrottleLimit** устанавливается равным 4, чтобы входные данные обрабатывались пакетами четырех.</span><span class="sxs-lookup"><span data-stu-id="b0df8-203">The **ThrottleLimit** parameter value is set to 4 so that the input is processed in batches of four.</span></span>
<span data-ttu-id="b0df8-204">`$using:`Ключевое слово используется для передачи `$Message` переменной в каждый параллельный блок скрипта.</span><span class="sxs-lookup"><span data-stu-id="b0df8-204">The `$using:` keyword is used to pass the `$Message` variable into each parallel script block.</span></span>

### <span data-ttu-id="b0df8-205">Пример 12. получение записей журнала в параллельном режиме</span><span class="sxs-lookup"><span data-stu-id="b0df8-205">Example 12: Retrieve log entries in parallel</span></span>

<span data-ttu-id="b0df8-206">Этот пример извлекает записи журнала 50 000 из 5 системных журналов на локальном компьютере Windows.</span><span class="sxs-lookup"><span data-stu-id="b0df8-206">This example retrieves 50,000 log entries from 5 system logs on a local Windows machine.</span></span>

```powershell
$logNames = 'Security','Application','System','Windows PowerShell','Microsoft-Windows-Store/Operational'

$logEntries = $logNames | ForEach-Object -Parallel {
    Get-WinEvent -LogName $_ -MaxEvents 10000
} -ThrottleLimit 5

$logEntries.Count
```

```Output
50000
```

<span data-ttu-id="b0df8-207">С помощью параметра **Parallel** для каждого входного имени журнала указывается блок скрипта, который выполняется параллельно.</span><span class="sxs-lookup"><span data-stu-id="b0df8-207">The **Parallel** parameter specifies the script block that is run in parallel for each input log name.</span></span> <span data-ttu-id="b0df8-208">Параметр **ThrottleLimit** гарантирует, что все пять блоков сценариев выполняются одновременно.</span><span class="sxs-lookup"><span data-stu-id="b0df8-208">The **ThrottleLimit** parameter ensures that all five script blocks run at the same time.</span></span>

### <span data-ttu-id="b0df8-209">Пример 13. Параллельное выполнение в качестве задания</span><span class="sxs-lookup"><span data-stu-id="b0df8-209">Example 13: Run in parallel as a job</span></span>

<span data-ttu-id="b0df8-210">В этом примере простой блок скрипта выполняется параллельно, создавая два фоновых задания за раз.</span><span class="sxs-lookup"><span data-stu-id="b0df8-210">This example runs a simple script block in parallel, creating two background jobs at a time.</span></span>

```powershell
$job = 1..10 | ForEach-Object -Parallel {
    "Output: $_"
    Start-Sleep 1
} -ThrottleLimit 2 -AsJob

$job | Receive-Job -Wait
```

```Output
Output: 1
Output: 2
Output: 3
Output: 4
Output: 5
Output: 6
Output: 7
Output: 8
Output: 9
Output: 10
```

<span data-ttu-id="b0df8-211">`$job`переменная получает объект задания, который собирает выходные данные и отслеживает состояние выполнения.</span><span class="sxs-lookup"><span data-stu-id="b0df8-211">the `$job` variable receives the job object that collects output data and monitors running state.</span></span>
<span data-ttu-id="b0df8-212">Объект задания передается в `Receive-Job` параметре **Wait** .</span><span class="sxs-lookup"><span data-stu-id="b0df8-212">The job object is piped to `Receive-Job` with the **Wait** switch parameter.</span></span> <span data-ttu-id="b0df8-213">И этот поток выводит данные в консоль, как если бы `ForEach-Object -Parallel` она выполнялась без **AsJob**.</span><span class="sxs-lookup"><span data-stu-id="b0df8-213">And this streams output to the console, just as if `ForEach-Object -Parallel` was run without **AsJob**.</span></span>

### <span data-ttu-id="b0df8-214">Пример 14. Использование ссылок на переменные потокобезопасные</span><span class="sxs-lookup"><span data-stu-id="b0df8-214">Example 14: Using thread safe variable references</span></span>

<span data-ttu-id="b0df8-215">В этом примере блоки сценариев вызываются параллельно для получения объектов процессов с уникальными именами.</span><span class="sxs-lookup"><span data-stu-id="b0df8-215">This example invokes script blocks in parallel to collect uniquely named Process objects.</span></span>

```powershell
$threadSafeDictionary = [System.Collections.Concurrent.ConcurrentDictionary[string,object]]::new()
Get-Process | ForEach-Object -Parallel {
    $dict = $using:threadSafeDictionary
    $dict.TryAdd($_.ProcessName, $_)
}

$threadSafeDictionary["pwsh"]
```

```Output
 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
     82    82.87     130.85      15.55    2808   2 pwsh
```

<span data-ttu-id="b0df8-216">Один экземпляр объекта **ConcurrentDictionary** передается в каждый блок сценария для получения объектов.</span><span class="sxs-lookup"><span data-stu-id="b0df8-216">A single instance of a **ConcurrentDictionary** object is passed to each script block to collect the objects.</span></span> <span data-ttu-id="b0df8-217">Так как **ConcurrentDictionary** является потокобезопасным, его можно изменять с помощью каждого параллельного скрипта.</span><span class="sxs-lookup"><span data-stu-id="b0df8-217">Since the **ConcurrentDictionary** is thread safe, it is safe to be modified by each parallel script.</span></span> <span data-ttu-id="b0df8-218">Непотокобезопасный объект, такой как **System. Collections. Generic. Dictionary**, будет ненадежным для использования здесь.</span><span class="sxs-lookup"><span data-stu-id="b0df8-218">A non-thread-safe object, such as **System.Collections.Generic.Dictionary**, would not be safe to use here.</span></span>

> [!NOTE]
> <span data-ttu-id="b0df8-219">Этот пример очень неэффективно использует **параллельный** параметр.</span><span class="sxs-lookup"><span data-stu-id="b0df8-219">This example is a very inefficient use of **Parallel** parameter.</span></span> <span data-ttu-id="b0df8-220">Сценарий просто добавляет входной объект в объект параллельного словаря.</span><span class="sxs-lookup"><span data-stu-id="b0df8-220">The script simply adds the input object to a concurrent dictionary object.</span></span> <span data-ttu-id="b0df8-221">Это тривиальное и не стоит тратить издержки на вызов каждого скрипта в отдельном потоке.</span><span class="sxs-lookup"><span data-stu-id="b0df8-221">It is trivial and not worth the overhead of invoking each script in a separate thread.</span></span> <span data-ttu-id="b0df8-222">`ForEach-Object`Нормальное выполнение без **параллельного** коммутатора является гораздо более эффективным и быстрым.</span><span class="sxs-lookup"><span data-stu-id="b0df8-222">Running `ForEach-Object` normally without the **Parallel** switch is much more efficient and faster.</span></span> <span data-ttu-id="b0df8-223">Этот пример предназначен только для демонстрации использования потокобезопасных переменных.</span><span class="sxs-lookup"><span data-stu-id="b0df8-223">This example is only intended to demonstrate how to use thread safe variables.</span></span>

### <span data-ttu-id="b0df8-224">Пример 15. запись ошибок с параллельным выполнением</span><span class="sxs-lookup"><span data-stu-id="b0df8-224">Example 15: Writing errors with parallel execution</span></span>

<span data-ttu-id="b0df8-225">В этом примере выполняется параллельная запись в поток ошибок, в котором порядок записанных ошибок является случайным.</span><span class="sxs-lookup"><span data-stu-id="b0df8-225">This example writes to the error stream in parallel, where the order of written errors is random.</span></span>

```powershell
1..3 | ForEach-Object -Parallel {
    Write-Error "Error: $_"
}
```

```Output
Write-Error: Error: 1
Write-Error: Error: 3
Write-Error: Error: 2
```

### <span data-ttu-id="b0df8-226">Пример 16. прекращение обработки ошибок в параллельном выполнении</span><span class="sxs-lookup"><span data-stu-id="b0df8-226">Example 16: Terminating errors in parallel execution</span></span>

<span data-ttu-id="b0df8-227">В этом примере демонстрируется завершающая ошибка в одном параллельном выполняющемся блоке сценария.</span><span class="sxs-lookup"><span data-stu-id="b0df8-227">This example demonstrates a terminating error in one parallel running scriptblock.</span></span>

```powershell
1..5 | ForEach-Object -Parallel {
    if ($_ -eq 3)
    {
        throw "Terminating Error: $_"
    }

    Write-Output "Output: $_"
}
```

```Output
Exception: Terminating Error: 3
Output: 1
Output: 4
Output: 2
Output: 5
```

<span data-ttu-id="b0df8-228">`Output: 3` не записывается, так как параллельный блок сценария для этой итерации был завершен.</span><span class="sxs-lookup"><span data-stu-id="b0df8-228">`Output: 3` is never written because the parallel scriptblock for that iteration was terminated.</span></span>

## <span data-ttu-id="b0df8-229">Параметры</span><span class="sxs-lookup"><span data-stu-id="b0df8-229">Parameters</span></span>

### <span data-ttu-id="b0df8-230">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="b0df8-230">-ArgumentList</span></span>

<span data-ttu-id="b0df8-231">Задает массив аргументов для вызова метода.</span><span class="sxs-lookup"><span data-stu-id="b0df8-231">Specifies an array of arguments to a method call.</span></span> <span data-ttu-id="b0df8-232">Дополнительные сведения о поведении **ArgumentList** см. в разделе [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span><span class="sxs-lookup"><span data-stu-id="b0df8-232">For more information about the behavior of **ArgumentList**, see [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span></span>

<span data-ttu-id="b0df8-233">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="b0df8-233">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: PropertyAndMethodSet
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b0df8-234">-Begin</span><span class="sxs-lookup"><span data-stu-id="b0df8-234">-Begin</span></span>

<span data-ttu-id="b0df8-235">Задает блок скрипта, который выполняется перед тем, как этот командлет обрабатывает все входные объекты.</span><span class="sxs-lookup"><span data-stu-id="b0df8-235">Specifies a script block that runs before this cmdlet processes any input objects.</span></span> <span data-ttu-id="b0df8-236">Этот блок сценария выполняется только один раз для всего конвейера.</span><span class="sxs-lookup"><span data-stu-id="b0df8-236">This script block is only run once for the entire pipeline.</span></span> <span data-ttu-id="b0df8-237">Дополнительные сведения о `begin` блоке см. в разделе [about_Functions](about/about_functions.md#piping-objects-to-functions).</span><span class="sxs-lookup"><span data-stu-id="b0df8-237">For more information about the `begin` block, see [about_Functions](about/about_functions.md#piping-objects-to-functions).</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlockSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b0df8-238">-End</span><span class="sxs-lookup"><span data-stu-id="b0df8-238">-End</span></span>

<span data-ttu-id="b0df8-239">Задает блок скрипта, который запускается после того, как этот командлет обрабатывает все входные объекты.</span><span class="sxs-lookup"><span data-stu-id="b0df8-239">Specifies a script block that runs after this cmdlet processes all input objects.</span></span> <span data-ttu-id="b0df8-240">Этот блок сценария выполняется только один раз для всего конвейера.</span><span class="sxs-lookup"><span data-stu-id="b0df8-240">This script block is only run once for the entire pipeline.</span></span> <span data-ttu-id="b0df8-241">Дополнительные сведения о `end` блоке см. в разделе [about_Functions](about/about_functions.md#piping-objects-to-functions).</span><span class="sxs-lookup"><span data-stu-id="b0df8-241">For more information about the `end` block, see [about_Functions](about/about_functions.md#piping-objects-to-functions).</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlockSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b0df8-242">-InputObject</span><span class="sxs-lookup"><span data-stu-id="b0df8-242">-InputObject</span></span>

<span data-ttu-id="b0df8-243">Задает входные объекты.</span><span class="sxs-lookup"><span data-stu-id="b0df8-243">Specifies the input objects.</span></span> <span data-ttu-id="b0df8-244">`ForEach-Object` выполняет блок скрипта или инструкцию Operation для каждого входного объекта.</span><span class="sxs-lookup"><span data-stu-id="b0df8-244">`ForEach-Object` runs the script block or operation statement on each input object.</span></span> <span data-ttu-id="b0df8-245">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="b0df8-245">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

<span data-ttu-id="b0df8-246">При использовании параметра **InputObject** с параметром `ForEach-Object` , а не с результатами команды трубопроводов в `ForEach-Object` значение **InputObject** рассматривается как один объект.</span><span class="sxs-lookup"><span data-stu-id="b0df8-246">When you use the **InputObject** parameter with `ForEach-Object`, instead of piping command results to `ForEach-Object`, the **InputObject** value is treated as a single object.</span></span> <span data-ttu-id="b0df8-247">Это справедливо, даже если значением является коллекция, которая является результатом команды, например `-InputObject (Get-Process)` .</span><span class="sxs-lookup"><span data-stu-id="b0df8-247">This is true even if the value is a collection that is the result of a command, such as `-InputObject (Get-Process)`.</span></span>
<span data-ttu-id="b0df8-248">Поскольку **InputObject** не может возвращать отдельные свойства из массива или коллекции объектов, рекомендуется `ForEach-Object` использовать для выполнения операций с коллекцией объектов для объектов, имеющих определенные значения в определенных свойствах, `ForEach-Object` в конвейере, как показано в примерах этого раздела.</span><span class="sxs-lookup"><span data-stu-id="b0df8-248">Because **InputObject** cannot return individual properties from an array or collection of objects, we recommend that if you use `ForEach-Object` to perform operations on a collection of objects for those objects that have specific values in defined properties, you use `ForEach-Object` in the pipeline, as shown in the examples in this topic.</span></span>

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

### <span data-ttu-id="b0df8-249">-MemberName</span><span class="sxs-lookup"><span data-stu-id="b0df8-249">-MemberName</span></span>

<span data-ttu-id="b0df8-250">Указывает свойство, которое необходимо получить, или метод, который требуется вызвать.</span><span class="sxs-lookup"><span data-stu-id="b0df8-250">Specifies the property to get or the method to call.</span></span>

<span data-ttu-id="b0df8-251">Подстановочные знаки разрешены, но работают только в том случае, если результирующая строка разрешается в уникальное значение.</span><span class="sxs-lookup"><span data-stu-id="b0df8-251">Wildcard characters are permitted, but work only if the resulting string resolves to a unique value.</span></span>
<span data-ttu-id="b0df8-252">Например, если запустить `Get-Process | ForEach -MemberName *Name` , шаблон с подстановочными знаками будет соответствовать более чем одному члену, вызывающему сбой команды.</span><span class="sxs-lookup"><span data-stu-id="b0df8-252">For example, if you run `Get-Process | ForEach -MemberName *Name`, the wildcard pattern matches more than one member causing the command to fail.</span></span>

<span data-ttu-id="b0df8-253">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="b0df8-253">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: PropertyAndMethodSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="b0df8-254">-Process</span><span class="sxs-lookup"><span data-stu-id="b0df8-254">-Process</span></span>

<span data-ttu-id="b0df8-255">Указывает операцию, которая выполняется с каждым входным объектом.</span><span class="sxs-lookup"><span data-stu-id="b0df8-255">Specifies the operation that is performed on each input object.</span></span> <span data-ttu-id="b0df8-256">Этот блок скрипта выполняется для каждого объекта в конвейере.</span><span class="sxs-lookup"><span data-stu-id="b0df8-256">This script block is run for every object in the pipeline.</span></span> <span data-ttu-id="b0df8-257">Дополнительные сведения о `process` блоке см. в разделе [about_Functions](about/about_functions.md#piping-objects-to-functions).</span><span class="sxs-lookup"><span data-stu-id="b0df8-257">For more information about the `process` block, see [about_Functions](about/about_functions.md#piping-objects-to-functions).</span></span>

<span data-ttu-id="b0df8-258">Если параметру **Process** предоставлено несколько блоков скрипта, первый блок сценария всегда сопоставляется с `begin` блоком.</span><span class="sxs-lookup"><span data-stu-id="b0df8-258">When you provide multiple script blocks to the **Process** parameter, the first script block is always mapped to the `begin` block.</span></span> <span data-ttu-id="b0df8-259">При наличии только двух блоков сценариев второй блок сопоставляется с `process` блоком.</span><span class="sxs-lookup"><span data-stu-id="b0df8-259">If there are only two script blocks, the second block is mapped to the `process` block.</span></span> <span data-ttu-id="b0df8-260">При наличии трех или более блоков сценариев первый блок сценария всегда сопоставляется с `begin` блоком, последний блок сопоставляется с `end` блоком, а все блоки между ними сопоставлены с `process` блоком.</span><span class="sxs-lookup"><span data-stu-id="b0df8-260">If there are three or more script blocks, first script block is always mapped to the `begin` block, the last block is mapped to the `end` block, and the blocks in between are all mapped to the `process` block.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock[]
Parameter Sets: ScriptBlockSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b0df8-261">-Ремаинингскриптс</span><span class="sxs-lookup"><span data-stu-id="b0df8-261">-RemainingScripts</span></span>

<span data-ttu-id="b0df8-262">Задает все блоки скриптов, которые не выполняются параметром **Process** .</span><span class="sxs-lookup"><span data-stu-id="b0df8-262">Specifies all script blocks that are not taken by the **Process** parameter.</span></span>

<span data-ttu-id="b0df8-263">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="b0df8-263">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock[]
Parameter Sets: ScriptBlockSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b0df8-264">-Parallel</span><span class="sxs-lookup"><span data-stu-id="b0df8-264">-Parallel</span></span>

<span data-ttu-id="b0df8-265">Задает блок скрипта, используемый для параллельной обработки входных объектов.</span><span class="sxs-lookup"><span data-stu-id="b0df8-265">Specifies the script block to be used for parallel processing of input objects.</span></span> <span data-ttu-id="b0df8-266">Введите блок скрипта, который описывает операцию.</span><span class="sxs-lookup"><span data-stu-id="b0df8-266">Enter a script block that describes the operation.</span></span>

<span data-ttu-id="b0df8-267">Этот параметр появился в PowerShell 7,0.</span><span class="sxs-lookup"><span data-stu-id="b0df8-267">This parameter was introduced in PowerShell 7.0.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ParallelParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b0df8-268">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="b0df8-268">-ThrottleLimit</span></span>

<span data-ttu-id="b0df8-269">Указывает число параллельно обрабатываемых блоков скрипта.</span><span class="sxs-lookup"><span data-stu-id="b0df8-269">Specifies the number of script blocks that in parallel.</span></span> <span data-ttu-id="b0df8-270">Входные объекты блокируются до тех пор, пока число блоков выполняющегося сценария не станет меньше **ThrottleLimit**.</span><span class="sxs-lookup"><span data-stu-id="b0df8-270">Input objects are blocked until the running script block count falls below the **ThrottleLimit**.</span></span> <span data-ttu-id="b0df8-271">Значение по умолчанию — `5`.</span><span class="sxs-lookup"><span data-stu-id="b0df8-271">The default value is `5`.</span></span>

<span data-ttu-id="b0df8-272">Этот параметр появился в PowerShell 7,0.</span><span class="sxs-lookup"><span data-stu-id="b0df8-272">This parameter was introduced in PowerShell 7.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ParallelParameterSet
Aliases:

Required: False
Position: Named
Default value: 5
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b0df8-273">-TimeoutSeconds</span><span class="sxs-lookup"><span data-stu-id="b0df8-273">-TimeoutSeconds</span></span>

<span data-ttu-id="b0df8-274">Указывает время ожидания (в секундах), в течение которого все входные данные будут обрабатываться параллельно.</span><span class="sxs-lookup"><span data-stu-id="b0df8-274">Specifies the number of seconds to wait for all input to be processed in parallel.</span></span> <span data-ttu-id="b0df8-275">По истечении заданного времени ожидания все выполняющиеся сценарии останавливаются.</span><span class="sxs-lookup"><span data-stu-id="b0df8-275">After the specified timeout time, all running scripts are stopped.</span></span> <span data-ttu-id="b0df8-276">И все остальные входные объекты для обработки игнорируются.</span><span class="sxs-lookup"><span data-stu-id="b0df8-276">And any remaining input objects to be processed are ignored.</span></span> <span data-ttu-id="b0df8-277">Значение по умолчанию `0` отключает время ожидания и `ForEach-Object -Parallel` может выполняться бессрочно.</span><span class="sxs-lookup"><span data-stu-id="b0df8-277">Default value of `0` disables the timeout, and `ForEach-Object -Parallel` can run indefinitely.</span></span> <span data-ttu-id="b0df8-278">Команда <kbd>CTRL</kbd> + <kbd>C</kbd> в командной строке останавливает выполнение `ForEach-Object -Parallel` команды.</span><span class="sxs-lookup"><span data-stu-id="b0df8-278">Typing <kbd>Ctrl</kbd>+<kbd>C</kbd> at the command line stops a running `ForEach-Object -Parallel` command.</span></span> <span data-ttu-id="b0df8-279">Этот параметр нельзя использовать вместе с параметром **AsJob** .</span><span class="sxs-lookup"><span data-stu-id="b0df8-279">This parameter cannot be used along with the **AsJob** parameter.</span></span>

<span data-ttu-id="b0df8-280">Этот параметр появился в PowerShell 7,0.</span><span class="sxs-lookup"><span data-stu-id="b0df8-280">This parameter was introduced in PowerShell 7.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ParallelParameterSet
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b0df8-281">-Усеневрунспаце</span><span class="sxs-lookup"><span data-stu-id="b0df8-281">-UseNewRunspace</span></span>

<span data-ttu-id="b0df8-282">Приводит к тому, что параллельный вызов создает новое пространство выполнения для каждой итерации цикла, а не повторно использует пространства выполнения из пула.</span><span class="sxs-lookup"><span data-stu-id="b0df8-282">Causes the parallel invocation to create a new runspace for every loop iteration instead of reusing runspaces from the runspace pool.</span></span>

<span data-ttu-id="b0df8-283">Этот параметр появился в PowerShell 7,1</span><span class="sxs-lookup"><span data-stu-id="b0df8-283">This parameter was introduced in PowerShell 7.1</span></span>

```yml
Type: SwitchParameter
Parameter Sets: ParallelParameterSet
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b0df8-284">-AsJob</span><span class="sxs-lookup"><span data-stu-id="b0df8-284">-AsJob</span></span>

<span data-ttu-id="b0df8-285">Вызывает выполнение параллельного вызова в качестве задания PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b0df8-285">Causes the parallel invocation to run as a PowerShell job.</span></span> <span data-ttu-id="b0df8-286">Вместо выходных данных выполняемых блоков сценария возвращается один объект задания.</span><span class="sxs-lookup"><span data-stu-id="b0df8-286">A single job object is returned instead of output from the running script blocks.</span></span> <span data-ttu-id="b0df8-287">Объект задания содержит дочерние задания для каждого выполняемого блока параллельного скрипта.</span><span class="sxs-lookup"><span data-stu-id="b0df8-287">The job object contains child jobs for each parallel script block that runs.</span></span> <span data-ttu-id="b0df8-288">Объект задания может использоваться всеми командлетами задания PowerShell для отслеживания состояния выполнения и получения данных.</span><span class="sxs-lookup"><span data-stu-id="b0df8-288">The job object can be used by all PowerShell job cmdlets, to monitor running state and retrieve data.</span></span>

<span data-ttu-id="b0df8-289">Этот параметр появился в PowerShell 7,0.</span><span class="sxs-lookup"><span data-stu-id="b0df8-289">This parameter was introduced in PowerShell 7.0.</span></span>

```yaml
Type: SwitchParameter
Parameter Sets: ParallelParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b0df8-290">-Confirm</span><span class="sxs-lookup"><span data-stu-id="b0df8-290">-Confirm</span></span>

<span data-ttu-id="b0df8-291">Запрос подтверждения перед выполнением командлета.</span><span class="sxs-lookup"><span data-stu-id="b0df8-291">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b0df8-292">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="b0df8-292">-WhatIf</span></span>

<span data-ttu-id="b0df8-293">Показывает, что произойдет при запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="b0df8-293">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="b0df8-294">Командлет не выполняется.</span><span class="sxs-lookup"><span data-stu-id="b0df8-294">The cmdlet is not run.</span></span>

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b0df8-295">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="b0df8-295">CommonParameters</span></span>

<span data-ttu-id="b0df8-296">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b0df8-296">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b0df8-297">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b0df8-297">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b0df8-298">Входные данные</span><span class="sxs-lookup"><span data-stu-id="b0df8-298">Inputs</span></span>

### <span data-ttu-id="b0df8-299">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="b0df8-299">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="b0df8-300">В этот командлет можно передать по конвейеру любой объект.</span><span class="sxs-lookup"><span data-stu-id="b0df8-300">You can pipe any object to this cmdlet.</span></span>

## <span data-ttu-id="b0df8-301">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="b0df8-301">Outputs</span></span>

### <span data-ttu-id="b0df8-302">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="b0df8-302">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="b0df8-303">Этот командлет возвращает объекты, определяемые входными данными.</span><span class="sxs-lookup"><span data-stu-id="b0df8-303">This cmdlet returns objects that are determined by the input.</span></span>

## <span data-ttu-id="b0df8-304">Примечания</span><span class="sxs-lookup"><span data-stu-id="b0df8-304">Notes</span></span>

- <span data-ttu-id="b0df8-305">`ForEach-Object`Командлет работает во многом подобно оператору **foreach** , за исключением того, что нельзя передавать входные данные оператору **foreach** .</span><span class="sxs-lookup"><span data-stu-id="b0df8-305">The `ForEach-Object` cmdlet works much like the **Foreach** statement, except that you cannot pipe input to a **Foreach** statement.</span></span> <span data-ttu-id="b0df8-306">Дополнительные сведения об операторе **foreach** см. в разделе [about_Foreach](./About/about_Foreach.md).</span><span class="sxs-lookup"><span data-stu-id="b0df8-306">For more information about the **Foreach** statement, see [about_Foreach](./About/about_Foreach.md).</span></span>

- <span data-ttu-id="b0df8-307">Начиная с PowerShell 4,0, `Where` `ForEach` методы были добавлены для использования с коллекциями.</span><span class="sxs-lookup"><span data-stu-id="b0df8-307">Starting in PowerShell 4.0, `Where` and `ForEach` methods were added for use with collections.</span></span> <span data-ttu-id="b0df8-308">Дополнительные сведения об этих новых методах можно узнать здесь [about_arrays](./About/about_Arrays.md)</span><span class="sxs-lookup"><span data-stu-id="b0df8-308">You can read more about these new methods here [about_arrays](./About/about_Arrays.md)</span></span>

- <span data-ttu-id="b0df8-309">`ForEach-Object -Parallel`Набор параметров использует внутренний API PowerShell для выполнения каждого блока скрипта.</span><span class="sxs-lookup"><span data-stu-id="b0df8-309">The `ForEach-Object -Parallel` parameter set uses PowerShell's internal API to run each script block.</span></span> <span data-ttu-id="b0df8-310">Это значительно больше издержек, чем `ForEach-Object` обычно выполняется с последовательной обработкой.</span><span class="sxs-lookup"><span data-stu-id="b0df8-310">This is significantly more overhead than running `ForEach-Object` normally with sequential processing.</span></span> <span data-ttu-id="b0df8-311">Важно использовать **Parallel** , где затраты на параллельное выполнение выполняются немало по сравнению с работой блока сценария.</span><span class="sxs-lookup"><span data-stu-id="b0df8-311">It is important to use **Parallel** where the overhead of running in parallel is small compared to work the script block performs.</span></span> <span data-ttu-id="b0df8-312">Пример:</span><span class="sxs-lookup"><span data-stu-id="b0df8-312">For example:</span></span>

  - <span data-ttu-id="b0df8-313">Ресурсоемкие сценарии на компьютерах с несколькими ядрами</span><span class="sxs-lookup"><span data-stu-id="b0df8-313">Compute intensive scripts on multi-core machines</span></span>
  - <span data-ttu-id="b0df8-314">Сценарии, которые тратят время на ожидание результатов или выполнение файловых операций</span><span class="sxs-lookup"><span data-stu-id="b0df8-314">Scripts that spend time waiting for results or doing file operations</span></span>

  <span data-ttu-id="b0df8-315">Использование параметра **Parallel** может привести к тому, что скрипты выполняются намного медленнее, чем обычные.</span><span class="sxs-lookup"><span data-stu-id="b0df8-315">Using the **Parallel** parameter can cause scripts to run much slower than normal.</span></span> <span data-ttu-id="b0df8-316">Особенно если параллельные сценарии являются тривиальными.</span><span class="sxs-lookup"><span data-stu-id="b0df8-316">Especially if the parallel scripts are trivial.</span></span> <span data-ttu-id="b0df8-317">Поэкспериментируйте с **Parallel** , чтобы узнать, где это может быть полезно.</span><span class="sxs-lookup"><span data-stu-id="b0df8-317">Experiment with **Parallel** to discover where it can be beneficial.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="b0df8-318">`ForEach-Object -Parallel`Набор параметров запускает блоки сценариев параллельно в отдельных потоках процесса.</span><span class="sxs-lookup"><span data-stu-id="b0df8-318">The `ForEach-Object -Parallel` parameter set runs script blocks in parallel on separate process threads.</span></span> <span data-ttu-id="b0df8-319">`$using:`Ключевое слово позволяет передавать ссылки на переменные из потока вызова командлета в каждый выполняемый поток блока сценария.</span><span class="sxs-lookup"><span data-stu-id="b0df8-319">The `$using:` keyword allows passing variable references from the cmdlet invocation thread to each running script block thread.</span></span> <span data-ttu-id="b0df8-320">Так как блоки скрипта выполняются в разных потоках, объектные переменные, передаваемые по ссылке, должны использоваться безопасно.</span><span class="sxs-lookup"><span data-stu-id="b0df8-320">Since the script blocks run in different threads, the object variables passed by reference must be used safely.</span></span> <span data-ttu-id="b0df8-321">Как правило, можно легко считывать объекты, на которые имеются ссылки, которые не изменяются.</span><span class="sxs-lookup"><span data-stu-id="b0df8-321">Generally it is safe to read from referenced objects that don't change.</span></span> <span data-ttu-id="b0df8-322">Но если состояние объекта изменяется, необходимо использовать потокобезопасные объекты, такие как .NET **System. Collection. Параллельные** типы (см. Пример 11).</span><span class="sxs-lookup"><span data-stu-id="b0df8-322">But if the object state is being modified then you must used thread safe objects, such as .Net **System.Collection.Concurrent** types (See Example 11).</span></span>

## <span data-ttu-id="b0df8-323">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="b0df8-323">Related links</span></span>

[<span data-ttu-id="b0df8-324">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="b0df8-324">Compare-Object</span></span>](../Microsoft.PowerShell.Utility/Compare-Object.md)

[<span data-ttu-id="b0df8-325">Where-Object</span><span class="sxs-lookup"><span data-stu-id="b0df8-325">Where-Object</span></span>](Where-Object.md)

[<span data-ttu-id="b0df8-326">Group-Object</span><span class="sxs-lookup"><span data-stu-id="b0df8-326">Group-Object</span></span>](../Microsoft.PowerShell.Utility/Group-Object.md)

[<span data-ttu-id="b0df8-327">Measure-Object;</span><span class="sxs-lookup"><span data-stu-id="b0df8-327">Measure-Object</span></span>](../Microsoft.PowerShell.Utility/Measure-Object.md)

[<span data-ttu-id="b0df8-328">New-Object</span><span class="sxs-lookup"><span data-stu-id="b0df8-328">New-Object</span></span>](../Microsoft.PowerShell.Utility/New-Object.md)

[<span data-ttu-id="b0df8-329">Select-Object</span><span class="sxs-lookup"><span data-stu-id="b0df8-329">Select-Object</span></span>](../Microsoft.PowerShell.Utility/Select-Object.md)

[<span data-ttu-id="b0df8-330">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="b0df8-330">Sort-Object</span></span>](../Microsoft.PowerShell.Utility/Sort-Object.md)

[<span data-ttu-id="b0df8-331">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="b0df8-331">Tee-Object</span></span>](../Microsoft.PowerShell.Utility/Tee-Object.md)
