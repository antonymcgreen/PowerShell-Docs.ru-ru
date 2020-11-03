---
description: Объединение команд в конвейеры в PowerShell
keywords: powershell,командлет
Locale: en-US
ms.date: 09/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_pipelines?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Pipelines
ms.openlocfilehash: 651ba1f42743d83958d6711cff01fec030fa9a02
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "93233142"
---
# <a name="about-pipelines"></a><span data-ttu-id="d4a65-104">О конвейерах</span><span class="sxs-lookup"><span data-stu-id="d4a65-104">About Pipelines</span></span>

## <a name="short-description"></a><span data-ttu-id="d4a65-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="d4a65-105">Short description</span></span>

<span data-ttu-id="d4a65-106">Объединение команд в конвейеры в PowerShell</span><span class="sxs-lookup"><span data-stu-id="d4a65-106">Combining commands into pipelines in the PowerShell</span></span>

## <a name="long-description"></a><span data-ttu-id="d4a65-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="d4a65-107">Long description</span></span>

<span data-ttu-id="d4a65-108">Конвейер — это серия команд, Соединенных операторами конвейера ( `|` ) (ASCII 124).</span><span class="sxs-lookup"><span data-stu-id="d4a65-108">A pipeline is a series of commands connected by pipeline operators (`|`) (ASCII 124).</span></span> <span data-ttu-id="d4a65-109">Каждый оператор конвейера отправляет результаты предыдущей команды следующей команде.</span><span class="sxs-lookup"><span data-stu-id="d4a65-109">Each pipeline operator sends the results of the preceding command to the next command.</span></span>

<span data-ttu-id="d4a65-110">Выходные данные первой команды можно отправить для обработки в качестве входных данных во вторую команду.</span><span class="sxs-lookup"><span data-stu-id="d4a65-110">The output of the first command can be sent for processing as input to the second command.</span></span> <span data-ttu-id="d4a65-111">И эти выходные данные можно отправить в еще одну команду.</span><span class="sxs-lookup"><span data-stu-id="d4a65-111">And that output can be sent to yet another command.</span></span> <span data-ttu-id="d4a65-112">Результатом является сложная цепочка команд или _конвейер_ , состоящая из ряда простых команд.</span><span class="sxs-lookup"><span data-stu-id="d4a65-112">The result is a complex command chain or _pipeline_ that is composed of a series of simple commands.</span></span>

<span data-ttu-id="d4a65-113">Например, примененная к объекту директива</span><span class="sxs-lookup"><span data-stu-id="d4a65-113">For example,</span></span>

```powershell
Command-1 | Command-2 | Command-3
```

<span data-ttu-id="d4a65-114">В этом примере объекты, `Command-1` порождаемые, отправляются в `Command-2` .</span><span class="sxs-lookup"><span data-stu-id="d4a65-114">In this example, the objects that `Command-1` emits are sent to `Command-2`.</span></span>
<span data-ttu-id="d4a65-115">`Command-2` обрабатывает объекты и отправляет их в `Command-3` .</span><span class="sxs-lookup"><span data-stu-id="d4a65-115">`Command-2` processes the objects and sends them to `Command-3`.</span></span> <span data-ttu-id="d4a65-116">`Command-3` обрабатывает объекты и отправляет их по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="d4a65-116">`Command-3` processes the objects and send them down the pipeline.</span></span> <span data-ttu-id="d4a65-117">Так как в конвейере больше нет команд, результаты отображаются в консоли.</span><span class="sxs-lookup"><span data-stu-id="d4a65-117">Because there are no more commands in the pipeline, the results are displayed at the console.</span></span>

<span data-ttu-id="d4a65-118">В конвейере команды обрабатываются в порядке слева направо.</span><span class="sxs-lookup"><span data-stu-id="d4a65-118">In a pipeline, the commands are processed in order from left to right.</span></span> <span data-ttu-id="d4a65-119">Обработка обрабатывается как одна операция, а выходные данные отображаются по мере их создания.</span><span class="sxs-lookup"><span data-stu-id="d4a65-119">The processing is handled as a single operation and output is displayed as it's generated.</span></span>

<span data-ttu-id="d4a65-120">Вот простой пример.</span><span class="sxs-lookup"><span data-stu-id="d4a65-120">Here is a simple example.</span></span> <span data-ttu-id="d4a65-121">Следующая команда получает процесс блокнота и останавливает его.</span><span class="sxs-lookup"><span data-stu-id="d4a65-121">The following command gets the Notepad process and then stops it.</span></span>

<span data-ttu-id="d4a65-122">Например, примененная к объекту директива</span><span class="sxs-lookup"><span data-stu-id="d4a65-122">For example,</span></span>

```powershell
Get-Process notepad | Stop-Process
```

<span data-ttu-id="d4a65-123">Первая команда использует `Get-Process` командлет для получения объекта, представляющего процесс блокнота.</span><span class="sxs-lookup"><span data-stu-id="d4a65-123">The first command uses the `Get-Process` cmdlet to get an object representing the Notepad process.</span></span> <span data-ttu-id="d4a65-124">Он использует оператор конвейера ( `|` ) для отправки объекта Process в `Stop-Process` командлет, который останавливает процесс блокнота.</span><span class="sxs-lookup"><span data-stu-id="d4a65-124">It uses a pipeline operator (`|`) to send the process object to the `Stop-Process` cmdlet, which stops the Notepad process.</span></span> <span data-ttu-id="d4a65-125">Обратите внимание, что у `Stop-Process` команды нет параметра **Name** или **ID** для указания процесса, так как указанный процесс отправляется через конвейер.</span><span class="sxs-lookup"><span data-stu-id="d4a65-125">Notice that the `Stop-Process` command doesn't have a **Name** or **ID** parameter to specify the process, because the specified process is submitted through the pipeline.</span></span>

<span data-ttu-id="d4a65-126">Этот пример конвейера получает текстовые файлы в текущем каталоге, выбирает только те файлы, которые имеют длину более 10 000 байт, сортирует их по длине и отображает имя и длину каждого файла в таблице.</span><span class="sxs-lookup"><span data-stu-id="d4a65-126">This pipeline example gets the text files in the current directory, selects only the files that are more than 10,000 bytes long, sorts them by length, and displays the name and length of each file in a table.</span></span>

```powershell
Get-ChildItem -Path *.txt |
  Where-Object {$_.length -gt 10000} |
    Sort-Object -Property length |
      Format-Table -Property name, length
```

<span data-ttu-id="d4a65-127">Этот конвейер состоит из четырех команд в указанном порядке.</span><span class="sxs-lookup"><span data-stu-id="d4a65-127">This pipeline consists of four commands in the specified order.</span></span> <span data-ttu-id="d4a65-128">На следующем рисунке показаны выходные данные каждой команды, которые передаются в следующую команду конвейера.</span><span class="sxs-lookup"><span data-stu-id="d4a65-128">The following illustration shows the output from each command as it's passed to the next command in the pipeline.</span></span>

```
Get-ChildItem -Path *.txt
| (FileInfo objects for *.txt)
V
Where-Object {$_.length -gt 10000}
| (FileInfo objects for *.txt)
| (      Length > 10000      )
V
Sort-Object -Property Length
| (FileInfo objects for *.txt)
| (      Length > 10000      )
| (     Sorted by length     )
V
Format-Table -Property name, length
| (FileInfo objects for *.txt)
| (      Length > 10000      )
| (     Sorted by length     )
| (   Formatted in a table   )
V

Name                       Length
----                       ------
tmp1.txt                    82920
tmp2.txt                   114000
tmp3.txt                   114000
```

## <a name="using-pipelines"></a><span data-ttu-id="d4a65-129">Использование конвейеров</span><span class="sxs-lookup"><span data-stu-id="d4a65-129">Using pipelines</span></span>

<span data-ttu-id="d4a65-130">Большинство командлетов PowerShell предназначены для поддержки конвейеров.</span><span class="sxs-lookup"><span data-stu-id="d4a65-130">Most PowerShell cmdlets are designed to support pipelines.</span></span> <span data-ttu-id="d4a65-131">В большинстве случаев можно _передать_ результаты командлета **Get** в другой командлет того же существительного.</span><span class="sxs-lookup"><span data-stu-id="d4a65-131">In most cases, you can _pipe_ the results of a **Get** cmdlet to another cmdlet of the same noun.</span></span>
<span data-ttu-id="d4a65-132">Например, выходные данные командлета можно передать в `Get-Service` `Start-Service` `Stop-Service` командлеты или.</span><span class="sxs-lookup"><span data-stu-id="d4a65-132">For example, you can pipe the output of the `Get-Service` cmdlet to the `Start-Service` or `Stop-Service` cmdlets.</span></span>

<span data-ttu-id="d4a65-133">Этот пример конвейера запускает службу WMI на компьютере:</span><span class="sxs-lookup"><span data-stu-id="d4a65-133">This example pipeline starts the WMI service on the computer:</span></span>

```powershell
Get-Service wmi | Start-Service
```

<span data-ttu-id="d4a65-134">Другой пример: можно передать выходные данные `Get-Item` `Get-ChildItem` поставщика реестра PowerShell в `New-ItemProperty` командлет.</span><span class="sxs-lookup"><span data-stu-id="d4a65-134">For another example, you can pipe the output of `Get-Item` or `Get-ChildItem` within the PowerShell registry provider to the `New-ItemProperty` cmdlet.</span></span> <span data-ttu-id="d4a65-135">В этом примере в раздел реестра **MyCompany** добавляется новая запись реестра **NoOfEmployees** со значением **8124** .</span><span class="sxs-lookup"><span data-stu-id="d4a65-135">This example adds a new registry entry, **NoOfEmployees** , with a value of **8124** , to the **MyCompany** registry key.</span></span>

```powershell
Get-Item -Path HKLM:\Software\MyCompany |
  New-ItemProperty -Name NoOfEmployees -Value 8124
```

<span data-ttu-id="d4a65-136">Многие командлеты служебной программы, такие как,,, `Get-Member` `Where-Object` и, `Sort-Object` `Group-Object` `Measure-Object` используются практически исключительно в конвейерах.</span><span class="sxs-lookup"><span data-stu-id="d4a65-136">Many of the utility cmdlets, such as `Get-Member`, `Where-Object`, `Sort-Object`, `Group-Object`, and `Measure-Object` are used almost exclusively in pipelines.</span></span> <span data-ttu-id="d4a65-137">К этим командлетам можно передать любой тип объекта.</span><span class="sxs-lookup"><span data-stu-id="d4a65-137">You can pipe any object type to these cmdlets.</span></span> <span data-ttu-id="d4a65-138">В этом примере показано, как сортировать все процессы на компьютере по количеству открытых дескрипторов в каждом процессе.</span><span class="sxs-lookup"><span data-stu-id="d4a65-138">This example shows how to sort all the processes on the computer by the number of open handles in each process.</span></span>

```powershell
Get-Process | Sort-Object -Property handles
```

<span data-ttu-id="d4a65-139">Объекты можно передавать в командлеты форматирования, экспорта и вывода, такие как,, `Format-List` `Format-Table` `Export-Clixml` , `Export-CSV` и `Out-File` .</span><span class="sxs-lookup"><span data-stu-id="d4a65-139">You can pipe objects to the formatting, export, and output cmdlets, such as `Format-List`, `Format-Table`, `Export-Clixml`, `Export-CSV`, and `Out-File`.</span></span>

<span data-ttu-id="d4a65-140">В этом примере показано, как использовать `Format-List` командлет для отображения списка свойств объекта процесса.</span><span class="sxs-lookup"><span data-stu-id="d4a65-140">This example shows how to use the `Format-List` cmdlet to display a list of properties for a process object.</span></span>

```powershell
Get-Process winlogon | Format-List -Property *
```

<span data-ttu-id="d4a65-141">С небольшой практикой вы обнаружите, что объединение простых команд в конвейеры экономит время и ввод и делает создание сценариев более эффективным.</span><span class="sxs-lookup"><span data-stu-id="d4a65-141">With a bit of practice, you'll find that combining simple commands into pipelines saves time and typing, and makes your scripting more efficient.</span></span>

## <a name="how-pipelines-work"></a><span data-ttu-id="d4a65-142">Принцип работы конвейеров</span><span class="sxs-lookup"><span data-stu-id="d4a65-142">How pipelines work</span></span>

<span data-ttu-id="d4a65-143">В этом разделе объясняется, как входные объекты привязаны к параметрам командлета и обрабатываются во время выполнения конвейера.</span><span class="sxs-lookup"><span data-stu-id="d4a65-143">This section explains how input objects are bound to cmdlet parameters and processed during pipeline execution.</span></span>

### <a name="accepts-pipeline-input"></a><span data-ttu-id="d4a65-144">Принимает входные данные конвейера</span><span class="sxs-lookup"><span data-stu-id="d4a65-144">Accepts pipeline input</span></span>

<span data-ttu-id="d4a65-145">Для поддержки конвейера принимающий командлет должен иметь параметр, который принимает входные данные конвейера.</span><span class="sxs-lookup"><span data-stu-id="d4a65-145">To support pipelining, the receiving cmdlet must have a parameter that accepts pipeline input.</span></span> <span data-ttu-id="d4a65-146">Используйте `Get-Help` команду с параметрами **Full** или **Parameter** , чтобы определить, какие параметры командлета принимают входные данные конвейера.</span><span class="sxs-lookup"><span data-stu-id="d4a65-146">Use the `Get-Help` command with the **Full** or **Parameter** options to determine which parameters of a cmdlet accept pipeline input.</span></span>

<span data-ttu-id="d4a65-147">Например, чтобы определить, какой из параметров `Start-Service` командлета принимает входные данные конвейера, введите:</span><span class="sxs-lookup"><span data-stu-id="d4a65-147">For example, to determine which of the parameters of the `Start-Service` cmdlet accepts pipeline input, type:</span></span>

```powershell
Get-Help Start-Service -Full
```

<span data-ttu-id="d4a65-148">or</span><span class="sxs-lookup"><span data-stu-id="d4a65-148">or</span></span>

```powershell
Get-Help Start-Service -Parameter *
```

<span data-ttu-id="d4a65-149">Справка по `Start-Service` командлету показывает, что только параметры **InputObject** и **Name** принимают входные данные конвейера.</span><span class="sxs-lookup"><span data-stu-id="d4a65-149">The help for the `Start-Service` cmdlet shows that only the **InputObject** and **Name** parameters accept pipeline input.</span></span>

```Output
-InputObject <ServiceController[]>
Specifies ServiceController objects representing the services to be started.
Enter a variable that contains the objects, or type a command or expression
that gets the objects.

Required?                    true
Position?                    0
Default value                None
Accept pipeline input?       True (ByValue)
Accept wildcard characters?  false

-Name <String[]>
Specifies the service names for the service to be started.

The parameter name is optional. You can use Name or its alias, ServiceName,
or you can omit the parameter name.

Required?                    true
Position?                    0
Default value                None
Accept pipeline input?       True (ByPropertyName, ByValue)
Accept wildcard characters?  false
```

<span data-ttu-id="d4a65-150">При отправке объектов через конвейер в `Start-Service` PowerShell пытается связать объекты с параметрами **InputObject** и **Name** .</span><span class="sxs-lookup"><span data-stu-id="d4a65-150">When you send objects through the pipeline to `Start-Service`, PowerShell attempts to associate the objects with the **InputObject** and **Name** parameters.</span></span>

### <a name="methods-of-accepting-pipeline-input"></a><span data-ttu-id="d4a65-151">Методы приема входных данных конвейера</span><span class="sxs-lookup"><span data-stu-id="d4a65-151">Methods of accepting pipeline input</span></span>

<span data-ttu-id="d4a65-152">Параметры командлетов могут принимать входные данные конвейера одним из двух способов:</span><span class="sxs-lookup"><span data-stu-id="d4a65-152">Cmdlets parameters can accept pipeline input in one of two different ways:</span></span>

- <span data-ttu-id="d4a65-153">**Бивалуе** : параметр принимает значения, которые соответствуют ожидаемому типу .NET или могут быть преобразованы в этот тип.</span><span class="sxs-lookup"><span data-stu-id="d4a65-153">**ByValue** : The parameter accepts values that match the expected .NET type or that can be converted to that type.</span></span>

  <span data-ttu-id="d4a65-154">Например, параметр **Name** `Start-Service` принимает входные данные конвейера по значению.</span><span class="sxs-lookup"><span data-stu-id="d4a65-154">For example, the **Name** parameter of `Start-Service` accepts pipeline input by value.</span></span> <span data-ttu-id="d4a65-155">Он может принимать строковые объекты или объекты, которые могут быть преобразованы в строки.</span><span class="sxs-lookup"><span data-stu-id="d4a65-155">It can accept string objects or objects that can be converted to strings.</span></span>

- <span data-ttu-id="d4a65-156">**Бипропертинаме** : параметр принимает входные данные только в том случае, если входной объект имеет свойство с тем же именем, что и параметр.</span><span class="sxs-lookup"><span data-stu-id="d4a65-156">**ByPropertyName** : The parameter accepts input only when the input object has a property of the same name as the parameter.</span></span>

  <span data-ttu-id="d4a65-157">Например, параметр Name объекта `Start-Service` может принимать объекты со свойством **Name** .</span><span class="sxs-lookup"><span data-stu-id="d4a65-157">For example, the Name parameter of `Start-Service` can accept objects that have a **Name** property.</span></span> <span data-ttu-id="d4a65-158">Чтобы получить список свойств объекта, передайте его по конвейеру `Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="d4a65-158">To list the properties of an object, pipe it to `Get-Member`.</span></span>

<span data-ttu-id="d4a65-159">Некоторые параметры могут принимать объекты по значению или имени свойства, что упрощает получение входных данных из конвейера.</span><span class="sxs-lookup"><span data-stu-id="d4a65-159">Some parameters can accept objects by both value or property name, making it easier to take input from the pipeline.</span></span>

### <a name="parameter-binding"></a><span data-ttu-id="d4a65-160">Привязка параметра</span><span class="sxs-lookup"><span data-stu-id="d4a65-160">Parameter binding</span></span>

<span data-ttu-id="d4a65-161">При передаче объектов из одной команды в другую команда PowerShell пытается связать переданный объект с параметром командлета получения.</span><span class="sxs-lookup"><span data-stu-id="d4a65-161">When you pipe objects from one command to another command, PowerShell attempts to associate the piped objects with a parameter of the receiving cmdlet.</span></span>

<span data-ttu-id="d4a65-162">Компонент привязки параметров PowerShell связывает входные объекты с параметрами командлета в соответствии со следующими критериями:</span><span class="sxs-lookup"><span data-stu-id="d4a65-162">PowerShell's parameter binding component associates the input objects with cmdlet parameters according to the following criteria:</span></span>

- <span data-ttu-id="d4a65-163">Параметр должен принимать входные данные из конвейера.</span><span class="sxs-lookup"><span data-stu-id="d4a65-163">The parameter must accept input from a pipeline.</span></span>
- <span data-ttu-id="d4a65-164">Параметр должен принимать тип отправляемого объекта или тип, который может быть преобразован в ожидаемый тип.</span><span class="sxs-lookup"><span data-stu-id="d4a65-164">The parameter must accept the type of object being sent or a type that can be converted to the expected type.</span></span>
- <span data-ttu-id="d4a65-165">Параметр не использовался в команде.</span><span class="sxs-lookup"><span data-stu-id="d4a65-165">The parameter wasn't used in the command.</span></span>

<span data-ttu-id="d4a65-166">Например, `Start-Service` у командлета есть много параметров, но только два из них, **Name** и **InputObject** принимают входные данные конвейера.</span><span class="sxs-lookup"><span data-stu-id="d4a65-166">For example, the `Start-Service` cmdlet has many parameters, but only two of them, **Name** and **InputObject** accept pipeline input.</span></span> <span data-ttu-id="d4a65-167">Параметр **Name** принимает строки, а параметр **InputObject** принимает объекты службы.</span><span class="sxs-lookup"><span data-stu-id="d4a65-167">The **Name** parameter takes strings and the **InputObject** parameter takes service objects.</span></span> <span data-ttu-id="d4a65-168">Таким образом, можно передать строки, объекты служб и объекты со свойствами, которые могут быть преобразованы в строковые или служебные объекты.</span><span class="sxs-lookup"><span data-stu-id="d4a65-168">Therefore, you can pipe strings, service objects, and objects with properties that can be converted to string or service objects.</span></span>

<span data-ttu-id="d4a65-169">PowerShell управляет привязкой параметров как можно эффективнее.</span><span class="sxs-lookup"><span data-stu-id="d4a65-169">PowerShell manages parameter binding as efficiently as possible.</span></span> <span data-ttu-id="d4a65-170">Нельзя предложить или принудительно выполнить привязку PowerShell к конкретному параметру.</span><span class="sxs-lookup"><span data-stu-id="d4a65-170">You can't suggest or force the PowerShell to bind to a specific parameter.</span></span> <span data-ttu-id="d4a65-171">Команда завершается ошибкой, если PowerShell не удается привязать перенаправленные объекты.</span><span class="sxs-lookup"><span data-stu-id="d4a65-171">The command fails if PowerShell can't bind the piped objects.</span></span>

<span data-ttu-id="d4a65-172">Дополнительные сведения об устранении ошибок привязки см. в разделе [исследование ошибок конвейера](#investigating-pipeline-errors) далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="d4a65-172">For more information about troubleshooting binding errors, see [Investigating Pipeline Errors](#investigating-pipeline-errors) later in this article.</span></span>

### <a name="one-at-a-time-processing"></a><span data-ttu-id="d4a65-173">Однократная обработка</span><span class="sxs-lookup"><span data-stu-id="d4a65-173">One-at-a-time processing</span></span>

<span data-ttu-id="d4a65-174">Передача объектов в команду во многом аналогична использованию параметра команды для отправки объектов.</span><span class="sxs-lookup"><span data-stu-id="d4a65-174">Piping objects to a command is much like using a parameter of the command to submit the objects.</span></span> <span data-ttu-id="d4a65-175">Рассмотрим пример конвейера.</span><span class="sxs-lookup"><span data-stu-id="d4a65-175">Let's look at a pipeline example.</span></span> <span data-ttu-id="d4a65-176">В этом примере мы используем конвейер для вывода таблицы объектов службы.</span><span class="sxs-lookup"><span data-stu-id="d4a65-176">In this example, we use a pipeline to display a table of service objects.</span></span>

```powershell
Get-Service | Format-Table -Property Name, DependentServices
```

<span data-ttu-id="d4a65-177">Функционально, это аналогично использованию параметра **InputObject** объекта `Format-Table` для отправки коллекции объектов.</span><span class="sxs-lookup"><span data-stu-id="d4a65-177">Functionally, this is like using the **InputObject** parameter of `Format-Table` to submit the object collection.</span></span>

<span data-ttu-id="d4a65-178">Например, можно сохранить коллекцию служб в переменную, которая передается с помощью параметра **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="d4a65-178">For example, we can save the collection of services to a variable that is passed using the **InputObject** parameter.</span></span>

```powershell
$services = Get-Service
Format-Table -InputObject $services -Property Name, DependentServices
```

<span data-ttu-id="d4a65-179">Или можно внедрить команду в параметр **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="d4a65-179">Or we can embed the command in the **InputObject** parameter.</span></span>

```powershell
Format-Table -InputObject (Get-Service) -Property Name, DependentServices
```

<span data-ttu-id="d4a65-180">Однако есть и важное отличие.</span><span class="sxs-lookup"><span data-stu-id="d4a65-180">However, there's an important difference.</span></span> <span data-ttu-id="d4a65-181">При передаче нескольких объектов команде PowerShell по одной команде отправляет объекты в команду по одному.</span><span class="sxs-lookup"><span data-stu-id="d4a65-181">When you pipe multiple objects to a command, PowerShell sends the objects to the command one at a time.</span></span> <span data-ttu-id="d4a65-182">При использовании параметра команды объекты отправляются как один объект массива.</span><span class="sxs-lookup"><span data-stu-id="d4a65-182">When you use a command parameter, the objects are sent as a single array object.</span></span> <span data-ttu-id="d4a65-183">Это небольшое различие имеет значительные последствия.</span><span class="sxs-lookup"><span data-stu-id="d4a65-183">This minor difference has significant consequences.</span></span>

<span data-ttu-id="d4a65-184">При выполнении конвейера PowerShell автоматически перечисляет любой тип, реализующий интерфейс, `IEnumerable` и отправляет элементы по одному в конвейере.</span><span class="sxs-lookup"><span data-stu-id="d4a65-184">When executing a pipeline, PowerShell automatically enumerates any type that implements the `IEnumerable` interface and sends the members through the pipeline one at a time.</span></span> <span data-ttu-id="d4a65-185">Исключением является `[hashtable]` , что требует вызова `GetEnumerator()` метода.</span><span class="sxs-lookup"><span data-stu-id="d4a65-185">The exception is `[hashtable]`, which requires a call to the `GetEnumerator()` method.</span></span>

<span data-ttu-id="d4a65-186">В следующих примерах массив и хэш-таблица передаются в `Measure-Object` командлет для подсчета количества объектов, полученных из конвейера.</span><span class="sxs-lookup"><span data-stu-id="d4a65-186">In the following examples, an array and a hashtable are piped to the `Measure-Object` cmdlet to count the number of objects received from the pipeline.</span></span> <span data-ttu-id="d4a65-187">Массив содержит несколько элементов, а таблица Hashtable содержит несколько пар "ключ-значение".</span><span class="sxs-lookup"><span data-stu-id="d4a65-187">The array has multiple members, and the hashtable has multiple key-value pairs.</span></span> <span data-ttu-id="d4a65-188">Только массив перечисляется по одному за раз.</span><span class="sxs-lookup"><span data-stu-id="d4a65-188">Only the array is enumerated one at a time.</span></span>

```powershell
@(1,2,3) | Measure-Object
```

```Output
Count    : 3
Average  :
Sum      :
Maximum  :
Minimum  :
Property :
```

```powershell
@{"One"=1;"Two"=2} | Measure-Object
```

```Output
Count    : 1
Average  :
Sum      :
Maximum  :
Minimum  :
Property :
```

<span data-ttu-id="d4a65-189">Аналогично, если передать несколько объектов Process из `Get-Process` командлета в `Get-Member` командлет, PowerShell отправляет каждый объект процесса по одному за раз в `Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="d4a65-189">Similarly, if you pipe multiple process objects from the `Get-Process` cmdlet to the `Get-Member` cmdlet, PowerShell sends each process object, one at a time, to `Get-Member`.</span></span> <span data-ttu-id="d4a65-190">`Get-Member` Отображает класс .NET (тип) объектов процесса, а также их свойства и методы.</span><span class="sxs-lookup"><span data-stu-id="d4a65-190">`Get-Member` displays the .NET class (type) of the process objects, and their properties and methods.</span></span>

```powershell
Get-Process | Get-Member
```

```Output
TypeName: System.Diagnostics.Process

Name      MemberType     Definition
----      ----------     ----------
Handles   AliasProperty  Handles = Handlecount
Name      AliasProperty  Name = ProcessName
NPM       AliasProperty  NPM = NonpagedSystemMemorySize
...
```

> [!NOTE]
> <span data-ttu-id="d4a65-191">`Get-Member` устраняет дубликаты, поэтому, если все объекты имеют одинаковый тип, он отображает только один тип объекта.</span><span class="sxs-lookup"><span data-stu-id="d4a65-191">`Get-Member` eliminates duplicates, so if the objects are all of the same type, it only displays one object type.</span></span>

<span data-ttu-id="d4a65-192">Однако если используется параметр **InputObject** из `Get-Member` , то `Get-Member` получает массив объектов **System. Diagnostics. Process** как единый блок.</span><span class="sxs-lookup"><span data-stu-id="d4a65-192">However, if you use the **InputObject** parameter of `Get-Member`, then `Get-Member` receives an array of **System.Diagnostics.Process** objects as a single unit.</span></span> <span data-ttu-id="d4a65-193">Он отображает свойства массива объектов.</span><span class="sxs-lookup"><span data-stu-id="d4a65-193">It displays the properties of an array of objects.</span></span> <span data-ttu-id="d4a65-194">(Обратите внимание на символ массива ( `[]` ) после имени типа **System. Object** .)</span><span class="sxs-lookup"><span data-stu-id="d4a65-194">(Note the array symbol (`[]`) after the **System.Object** type name.)</span></span>

<span data-ttu-id="d4a65-195">Например, примененная к объекту директива</span><span class="sxs-lookup"><span data-stu-id="d4a65-195">For example,</span></span>

```powershell
Get-Member -InputObject (Get-Process)
```

```Output
TypeName: System.Object[]

Name               MemberType    Definition
----               ----------    ----------
Count              AliasProperty Count = Length
Address            Method        System.Object& Address(Int32 )
Clone              Method        System.Object Clone()
...
```

<span data-ttu-id="d4a65-196">Этот результат может быть не так, как планировалось.</span><span class="sxs-lookup"><span data-stu-id="d4a65-196">This result might not be what you intended.</span></span> <span data-ttu-id="d4a65-197">Но после того, как вы понимаете его, вы можете использовать его.</span><span class="sxs-lookup"><span data-stu-id="d4a65-197">But after you understand it, you can use it.</span></span> <span data-ttu-id="d4a65-198">Например, все объекты массива имеют свойство **Count** .</span><span class="sxs-lookup"><span data-stu-id="d4a65-198">For example, all array objects have a **Count** property.</span></span> <span data-ttu-id="d4a65-199">Его можно использовать для подсчета количества процессов, запущенных на компьютере.</span><span class="sxs-lookup"><span data-stu-id="d4a65-199">You can use that to count the number of processes running on the computer.</span></span>

<span data-ttu-id="d4a65-200">Например, примененная к объекту директива</span><span class="sxs-lookup"><span data-stu-id="d4a65-200">For example,</span></span>

```powershell
(Get-Process).count
```

<span data-ttu-id="d4a65-201">Важно помнить, что объекты, отправленные по конвейеру, доставляются по одному за раз.</span><span class="sxs-lookup"><span data-stu-id="d4a65-201">It's important to remember that objects sent down the pipeline are delivered one at a time.</span></span>

## <a name="investigating-pipeline-errors"></a><span data-ttu-id="d4a65-202">Исследование ошибок конвейера</span><span class="sxs-lookup"><span data-stu-id="d4a65-202">Investigating pipeline errors</span></span>

<span data-ttu-id="d4a65-203">Если PowerShell не может связать переданный объект с параметром командлета получения, команда завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="d4a65-203">When PowerShell can't associate the piped objects with a parameter of the receiving cmdlet, the command fails.</span></span>

<span data-ttu-id="d4a65-204">В следующем примере мы пытаемся переместить запись реестра из одного раздела реестра в другой.</span><span class="sxs-lookup"><span data-stu-id="d4a65-204">In the following example, we try to move a registry entry from one registry key to another.</span></span> <span data-ttu-id="d4a65-205">`Get-Item`Командлет возвращает путь назначения, который затем передается в `Move-ItemProperty` командлет.</span><span class="sxs-lookup"><span data-stu-id="d4a65-205">The `Get-Item` cmdlet gets the destination path, which is then piped to the `Move-ItemProperty` cmdlet.</span></span> <span data-ttu-id="d4a65-206">`Move-ItemProperty`Команда задает текущий путь и имя перемещаемой записи реестра.</span><span class="sxs-lookup"><span data-stu-id="d4a65-206">The `Move-ItemProperty` command specifies the current path and name of the registry entry to be moved.</span></span>

```powershell
Get-Item -Path HKLM:\Software\MyCompany\sales |
Move-ItemProperty -Path HKLM:\Software\MyCompany\design -Name product
```

<span data-ttu-id="d4a65-207">Команда завершается ошибкой, и PowerShell выводит следующее сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="d4a65-207">The command fails and PowerShell displays the following error message:</span></span>

```Output
Move-ItemProperty : The input object can't be bound to any parameters for
the command either because the command doesn't take pipeline input or the
input and its properties do not match any of the parameters that take
pipeline input.
At line:1 char:23
+ $a | Move-ItemProperty <<<<  -Path HKLM:\Software\MyCompany\design -Name p
```

<span data-ttu-id="d4a65-208">Для изучения используйте `Trace-Command` командлет для трассировки компонента привязки параметров PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d4a65-208">To investigate, use the `Trace-Command` cmdlet to trace the parameter binding component of PowerShell.</span></span> <span data-ttu-id="d4a65-209">В следующем примере выполняется трассировка привязки параметра во время выполнения конвейера.</span><span class="sxs-lookup"><span data-stu-id="d4a65-209">The following example traces parameter binding while the pipeline is executing.</span></span> <span data-ttu-id="d4a65-210">Параметр **PSHost** отображает результаты трассировки в консоли, а параметр **FilePath** отправляет результаты трассировки в `debug.txt` файл для последующей ссылки.</span><span class="sxs-lookup"><span data-stu-id="d4a65-210">The **PSHost** parameter displays the trace results in the console and the **FilePath** parameter send the trace results to the `debug.txt` file for later reference.</span></span>

```powershell
Trace-Command -Name ParameterBinding -PSHost -FilePath debug.txt -Expression {
  Get-Item -Path HKLM:\Software\MyCompany\sales |
    Move-ItemProperty -Path HKLM:\Software\MyCompany\design -Name product
}
```

<span data-ttu-id="d4a65-211">Результаты трассировки имеют длину, но они показывают значения, привязанные к `Get-Item` командлету, а затем именованные значения, привязанные к `Move-ItemProperty` командлету.</span><span class="sxs-lookup"><span data-stu-id="d4a65-211">The results of the trace are lengthy, but they show the values being bound to the `Get-Item` cmdlet and then the named values being bound to the `Move-ItemProperty` cmdlet.</span></span>

```Output
...
BIND NAMED cmd line args [`Move-ItemProperty`]
BIND arg [HKLM:\Software\MyCompany\design] to parameter [Path]
...
BIND arg [product] to parameter [Name]
...
BIND POSITIONAL cmd line args [`Move-ItemProperty`]
...
```

<span data-ttu-id="d4a65-212">Наконец, он показывает, что попытка привязки пути к параметру **назначения** `Move-ItemProperty` не удалась.</span><span class="sxs-lookup"><span data-stu-id="d4a65-212">Finally, it shows that the attempt to bind the path to the **Destination** parameter of `Move-ItemProperty` failed.</span></span>

```Output
...
BIND PIPELINE object to parameters: [`Move-ItemProperty`]
PIPELINE object TYPE = [Microsoft.Win32.RegistryKey]
RESTORING pipeline parameter's original values
Parameter [Destination] PIPELINE INPUT ValueFromPipelineByPropertyName NO
COERCION
Parameter [Credential] PIPELINE INPUT ValueFromPipelineByPropertyName NO
COERCION
...
```

<span data-ttu-id="d4a65-213">Используйте `Get-Help` командлет для просмотра атрибутов **целевого** параметра.</span><span class="sxs-lookup"><span data-stu-id="d4a65-213">Use the `Get-Help` cmdlet to view the attributes of the **Destination** parameter.</span></span>

```Output
Get-Help Move-ItemProperty -Parameter Destination

-Destination <String>
    Specifies the path to the destination location.

    Required?                    true
    Position?                    1
    Default value                None
    Accept pipeline input?       True (ByPropertyName)
    Accept wildcard characters?  false
```

<span data-ttu-id="d4a65-214">Результаты показывают, что **назначение** принимает только входные данные конвейера "по имени свойства".</span><span class="sxs-lookup"><span data-stu-id="d4a65-214">The results show that **Destination** takes pipeline input only "by property name".</span></span> <span data-ttu-id="d4a65-215">Таким образом, объект последовательного объекта должен иметь свойство с именем **Destination** .</span><span class="sxs-lookup"><span data-stu-id="d4a65-215">Therefore, the piped object must have a property named **Destination** .</span></span>

<span data-ttu-id="d4a65-216">Используйте `Get-Member` для просмотра свойств объекта, поступающих из `Get-Item` .</span><span class="sxs-lookup"><span data-stu-id="d4a65-216">Use `Get-Member` to see the properties of the object coming from `Get-Item`.</span></span>

```powershell
Get-Item -Path HKLM:\Software\MyCompany\sales | Get-Member
```

<span data-ttu-id="d4a65-217">Выходные данные показывают, что элемент является объектом **Microsoft. Win32. RegistryKey** , который не имеет **целевого** свойства.</span><span class="sxs-lookup"><span data-stu-id="d4a65-217">The output shows that the item is a **Microsoft.Win32.RegistryKey** object that doesn't have a **Destination** property.</span></span> <span data-ttu-id="d4a65-218">Это объясняет, почему команда завершилась ошибкой.</span><span class="sxs-lookup"><span data-stu-id="d4a65-218">That explains why the command failed.</span></span>

<span data-ttu-id="d4a65-219">Параметр **path** принимает входные данные конвейера по имени или по значению.</span><span class="sxs-lookup"><span data-stu-id="d4a65-219">The **Path** parameter accepts pipeline input by name or by value.</span></span>

```Output
Get-Help Move-ItemProperty -Parameter Path

-Path <String[]>
    Specifies the path to the current location of the property. Wildcard
    characters are permitted.

    Required?                    true
    Position?                    0
    Default value                None
    Accept pipeline input?       True (ByPropertyName, ByValue)
    Accept wildcard characters?  true
```

<span data-ttu-id="d4a65-220">Чтобы исправить эту команду, необходимо указать назначение в `Move-ItemProperty` командлете и использовать `Get-Item` для получения **пути** к элементу, который нужно переместить.</span><span class="sxs-lookup"><span data-stu-id="d4a65-220">To fix the command, we must specify the destination in the `Move-ItemProperty` cmdlet and use `Get-Item` to get the **Path** of the item we want to move.</span></span>

<span data-ttu-id="d4a65-221">Например, примененная к объекту директива</span><span class="sxs-lookup"><span data-stu-id="d4a65-221">For example,</span></span>

```powershell
Get-Item -Path HKLM:\Software\MyCompany\design |
Move-ItemProperty -Destination HKLM:\Software\MyCompany\sales -Name product
```

## <a name="intrinsic-line-continuation"></a><span data-ttu-id="d4a65-222">Внутреннее продолжение строки</span><span class="sxs-lookup"><span data-stu-id="d4a65-222">Intrinsic line continuation</span></span>

<span data-ttu-id="d4a65-223">Как уже говорилось, конвейер — это серия команд, Соединенных операторами конвейера ( `|` ), обычно написанными на одной строке.</span><span class="sxs-lookup"><span data-stu-id="d4a65-223">As already discussed, a pipeline is a series of commands connected by pipeline operators (`|`), usually written on a single line.</span></span> <span data-ttu-id="d4a65-224">Однако для удобства чтения PowerShell позволяет разбить конвейер на несколько строк.</span><span class="sxs-lookup"><span data-stu-id="d4a65-224">However, for readability, PowerShell allows you to split the pipeline across multiple lines.</span></span>
<span data-ttu-id="d4a65-225">Если оператор Pipe является последним маркером в строке, средство синтаксического анализа PowerShell присоединяет следующую строку к текущей команде, чтобы продолжить построение конвейера.</span><span class="sxs-lookup"><span data-stu-id="d4a65-225">When a pipe operator is the last token on the line, the PowerShell parser joins the next line to current command to continue the construction of the pipeline.</span></span>

<span data-ttu-id="d4a65-226">Например, следующий однострочный конвейер:</span><span class="sxs-lookup"><span data-stu-id="d4a65-226">For example, the following single-line pipeline:</span></span>

```powershell
Command-1 | Command-2 | Command-3
```

<span data-ttu-id="d4a65-227">можно записать следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d4a65-227">can be written as:</span></span>

```powershell
Command-1 |
  Command-2 |
    Command-3
```

<span data-ttu-id="d4a65-228">Начальные пробелы в последующих строках не являются значимыми.</span><span class="sxs-lookup"><span data-stu-id="d4a65-228">The leading spaces on the subsequent lines are not significant.</span></span> <span data-ttu-id="d4a65-229">Отступ повышает удобочитаемость.</span><span class="sxs-lookup"><span data-stu-id="d4a65-229">The indentation enhances readability.</span></span>

## <a name="see-also"></a><span data-ttu-id="d4a65-230">См. также:</span><span class="sxs-lookup"><span data-stu-id="d4a65-230">See Also</span></span>

[<span data-ttu-id="d4a65-231">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="d4a65-231">about_PSReadLine</span></span>](../../PSReadLine/About/about_PSReadLine.md)

[<span data-ttu-id="d4a65-232">about_Objects</span><span class="sxs-lookup"><span data-stu-id="d4a65-232">about_Objects</span></span>](about_objects.md)

[<span data-ttu-id="d4a65-233">about_Parameters</span><span class="sxs-lookup"><span data-stu-id="d4a65-233">about_Parameters</span></span>](about_parameters.md)

[<span data-ttu-id="d4a65-234">about_Command_Syntax</span><span class="sxs-lookup"><span data-stu-id="d4a65-234">about_Command_Syntax</span></span>](about_command_syntax.md)

[<span data-ttu-id="d4a65-235">about_ForEach</span><span class="sxs-lookup"><span data-stu-id="d4a65-235">about_ForEach</span></span>](about_foreach.md)
