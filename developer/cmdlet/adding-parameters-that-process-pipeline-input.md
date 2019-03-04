---
title: Добавление параметров, которые обрабатывают входные данные конвейера | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- cmdlets [PowerShell Programmer's Guide], pipeline input
- parameters [PowerShell Programer's Guide], pipeline input
ms.assetid: 09bf70a9-7c76-4ffe-b3f0-a1d5f10a0931
caps.latest.revision: 8
ms.openlocfilehash: c790d20a792bcdb4a34485e53375560e129433a8
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854540"
---
# <a name="adding-parameters-that-process-pipeline-input"></a><span data-ttu-id="7e85e-102">Добавление параметров для обработки входных данных конвейера</span><span class="sxs-lookup"><span data-stu-id="7e85e-102">Adding Parameters that Process Pipeline Input</span></span>

<span data-ttu-id="7e85e-103">Один источник входных данных для командлета — это объект в конвейер, поступающие из вышестоящего командлет.</span><span class="sxs-lookup"><span data-stu-id="7e85e-103">One source of input for a cmdlet is an object on the pipeline that originates from an upstream cmdlet.</span></span> <span data-ttu-id="7e85e-104">В этом разделе описывается добавление параметра в командлет Get-Proc (описано в разделе [Создание свой первый командлет](./creating-a-cmdlet-without-parameters.md)), чтобы командлет может обрабатывать объекты конвейера.</span><span class="sxs-lookup"><span data-stu-id="7e85e-104">This section describes how to add a parameter to the Get-Proc cmdlet (described in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md)) so that the cmdlet can process pipeline objects.</span></span>

<span data-ttu-id="7e85e-105">Этот командлет Get-Proc использует `Name` параметр, который принимает входные данные из объекта конвейера, извлекает сведения о процессе на локальном компьютере, на основе предоставленных имен и затем отображает сведения о процессах в командной строке.</span><span class="sxs-lookup"><span data-stu-id="7e85e-105">This Get-Proc cmdlet uses a `Name` parameter that accepts input from a pipeline object, retrieves process information from the local computer based on the supplied names, and then displays information about the processes at the command line.</span></span>

<span data-ttu-id="7e85e-106">Следующие подразделы этого раздела.</span><span class="sxs-lookup"><span data-stu-id="7e85e-106">Topics in this section include the following:</span></span>

- [<span data-ttu-id="7e85e-107">Определение класса командлета</span><span class="sxs-lookup"><span data-stu-id="7e85e-107">Defining the Cmdlet Class</span></span>](#Defining-the-Cmdlet-Class)

- [<span data-ttu-id="7e85e-108">Определение входных данных из конвейера</span><span class="sxs-lookup"><span data-stu-id="7e85e-108">Defining Input from the Pipeline</span></span>](#Defining-Input-from-the-Pipeline)

- [<span data-ttu-id="7e85e-109">Переопределив метод обработки входных данных</span><span class="sxs-lookup"><span data-stu-id="7e85e-109">Overriding an Input Processing Method</span></span>](#Overriding-an-Input-Processing-Method)

- [<span data-ttu-id="7e85e-110">Пример кода</span><span class="sxs-lookup"><span data-stu-id="7e85e-110">Code Sample</span></span>](#Code-Sample)

- [<span data-ttu-id="7e85e-111">Определение типов объектов и форматирование</span><span class="sxs-lookup"><span data-stu-id="7e85e-111">Defining Object Types and Formatting</span></span>](#Defining-Object-Types-and-Formatting)

- [<span data-ttu-id="7e85e-112">Создание командлета</span><span class="sxs-lookup"><span data-stu-id="7e85e-112">Building the Cmdlet</span></span>](#Building-the-Cmdlet)

- [<span data-ttu-id="7e85e-113">Тестирование командлет</span><span class="sxs-lookup"><span data-stu-id="7e85e-113">Testing the Cmdlet</span></span>](#Testing-the-Cmdlet)

## <a name="defining-the-cmdlet-class"></a><span data-ttu-id="7e85e-114">Определение класса командлета</span><span class="sxs-lookup"><span data-stu-id="7e85e-114">Defining the Cmdlet Class</span></span>

<span data-ttu-id="7e85e-115">Первым шагом в создании командлет всегда присвоение имени командлета и объявление класса .NET, который реализует командлет.</span><span class="sxs-lookup"><span data-stu-id="7e85e-115">The first step in cmdlet creation is always naming the cmdlet and declaring the .NET class that implements the cmdlet.</span></span> <span data-ttu-id="7e85e-116">Этот командлет извлекает сведения о процессе, чтобы имя команды, выбираем «Get».</span><span class="sxs-lookup"><span data-stu-id="7e85e-116">This cmdlet retrieves process information, so the verb name chosen here is "Get".</span></span> <span data-ttu-id="7e85e-117">(Почти любого вида командлет, который поддерживает получение сведений о может обрабатывать входные данные командной строки). Дополнительные сведения о командлет утвержденные глаголы, см. в разделе [имен команд командлет](./approved-verbs-for-windows-powershell-commands.md).</span><span class="sxs-lookup"><span data-stu-id="7e85e-117">(Almost any sort of cmdlet that is capable of retrieving information can process command-line input.) For more information about approved cmdlet verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="7e85e-118">Ниже приведено определение для этого командлета Get-Proc.</span><span class="sxs-lookup"><span data-stu-id="7e85e-118">The following is the definition for this Get-Proc cmdlet.</span></span> <span data-ttu-id="7e85e-119">Сведения из этого определения приведены [Создание свой первый командлет](./creating-a-cmdlet-without-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="7e85e-119">Details of this definition are given in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md).</span></span>

```csharp
[Cmdlet(VerbsCommon.Get, "proc")]
public class GetProcCommand : Cmdlet
```

```vb
<Cmdlet(VerbsCommon.Get, "Proc")> _
Public Class GetProcCommand
    Inherits Cmdlet
```

## <a name="defining-input-from-the-pipeline"></a><span data-ttu-id="7e85e-120">Определение входных данных из конвейера</span><span class="sxs-lookup"><span data-stu-id="7e85e-120">Defining Input from the Pipeline</span></span>

<span data-ttu-id="7e85e-121">В этом разделе описывается определение входных данных из конвейера для командлета.</span><span class="sxs-lookup"><span data-stu-id="7e85e-121">This section describes how to define input from the pipeline for a cmdlet.</span></span> <span data-ttu-id="7e85e-122">Этот командлет Get-Proc определяет свойство, которое представляет `Name` параметра, как описано в разделе [Добавление параметров командной строки этого процесса входа](./adding-parameters-that-process-command-line-input.md).</span><span class="sxs-lookup"><span data-stu-id="7e85e-122">This Get-Proc cmdlet defines a property that represents the `Name` parameter as described in [Adding Parameters that Process Command Line Input](./adding-parameters-that-process-command-line-input.md).</span></span> <span data-ttu-id="7e85e-123">(См. разделе Общие сведения об объявлении параметров).</span><span class="sxs-lookup"><span data-stu-id="7e85e-123">(See that topic for general information about declaring parameters.)</span></span>

<span data-ttu-id="7e85e-124">Тем не менее если командлет должен обрабатывать входные данные конвейера, он должен иметь его параметры, привязанные к входных значений средой выполнения Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7e85e-124">However, when a cmdlet needs to process pipeline input, it must have its parameters bound to input values by the Windows PowerShell runtime.</span></span> <span data-ttu-id="7e85e-125">Чтобы сделать это, необходимо добавить `ValueFromPipeline` ключевое слово или добавить `ValueFromPipelineByProperty` слово [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) объявление атрибута.</span><span class="sxs-lookup"><span data-stu-id="7e85e-125">To do this, you must add the `ValueFromPipeline` keyword or add the `ValueFromPipelineByProperty` keyword to the [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute declaration.</span></span> <span data-ttu-id="7e85e-126">Укажите `ValueFromPipeline` ключевое слово, если командлет осуществляет доступ к завершения входного объекта.</span><span class="sxs-lookup"><span data-stu-id="7e85e-126">Specify the `ValueFromPipeline` keyword if the cmdlet accesses the complete input object.</span></span> <span data-ttu-id="7e85e-127">Укажите `ValueFromPipelineByProperty` если командлет подключается только к свойству объекта.</span><span class="sxs-lookup"><span data-stu-id="7e85e-127">Specify the `ValueFromPipelineByProperty` if the cmdlet accesses only a property of the object.</span></span>

<span data-ttu-id="7e85e-128">Ниже приведено объявление параметра для `Name` параметр этого командлета Get-Proc, которая принимает входные данные конвейера.</span><span class="sxs-lookup"><span data-stu-id="7e85e-128">Here is the parameter declaration for the `Name` parameter of this Get-Proc cmdlet that accepts pipeline input.</span></span>

[!code-csharp[GetProcessSample03.cs](../../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample03/GetProcessSample03.cs#L35-L44 "GetProcessSample03.cs")]

```vb
<Parameter(Position:=0, ValueFromPipeline:=True, _
ValueFromPipelineByPropertyName:=True), ValidateNotNullOrEmpty()> _
Public Property Name() As String()
    Get
        Return processNames
    End Get

    Set(ByVal value As String())
        processNames = value
    End Set

End Property
```

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesgetproc03#GetProc03VBNameParameter](Msh_samplesgetproc03#GetProc03VBNameParameter)]  -->

<span data-ttu-id="7e85e-129">Предыдущие объявления наборы `ValueFromPipeline` ключевое слово `true` среды выполнения Windows PowerShell будет привязать параметр к входящего объекта, если объект совпадает с типом параметра, или, если он может быть преобразован в один тип.</span><span class="sxs-lookup"><span data-stu-id="7e85e-129">The previous declaration sets the `ValueFromPipeline` keyword to `true` so that the Windows PowerShell runtime will bind the parameter to the incoming object if the object is the same type as the parameter, or if it can be coerced to the same type.</span></span> <span data-ttu-id="7e85e-130">`ValueFromPipelineByPropertyName` Ключевого слова задано также `true` таким образом, чтобы среда выполнения Windows PowerShell будет проверять входящего объекта для `Name` свойство.</span><span class="sxs-lookup"><span data-stu-id="7e85e-130">The `ValueFromPipelineByPropertyName` keyword is also set to `true` so that the Windows PowerShell runtime will check the incoming object for a `Name` property.</span></span> <span data-ttu-id="7e85e-131">Если входящий объект имеет такое свойство, среда выполнения будет привязан `Name` параметр `Name` свойства входящего объекта.</span><span class="sxs-lookup"><span data-stu-id="7e85e-131">If the incoming object has such a property, the runtime will bind the `Name` parameter to the `Name` property of the incoming object.</span></span>

> [!NOTE]
> <span data-ttu-id="7e85e-132">Параметр `ValueFromPipeline` атрибут ключевого слова для параметра имеет приоритет над параметром для `ValueFromPipelineByPropertyName` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="7e85e-132">The setting of the `ValueFromPipeline` attribute keyword for a parameter takes precedence over the setting for the `ValueFromPipelineByPropertyName` keyword.</span></span>

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="7e85e-133">Переопределив метод обработки входных данных</span><span class="sxs-lookup"><span data-stu-id="7e85e-133">Overriding an Input Processing Method</span></span>

<span data-ttu-id="7e85e-134">Если командлет должен обрабатывать входные данные конвейера, ему необходимо переопределить соответствующие методы обработки ввода.</span><span class="sxs-lookup"><span data-stu-id="7e85e-134">If your cmdlet is to handle pipeline input, it needs to override the appropriate input processing methods.</span></span> <span data-ttu-id="7e85e-135">Методы базовую обработку ввода, использованные в [Создание свой первый командлет](./creating-a-cmdlet-without-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="7e85e-135">The basic input processing methods are introduced in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md).</span></span>

<span data-ttu-id="7e85e-136">Этот командлет Get-Proc переопределяет [System.Management.Automation.Cmdlet.Processrecord\*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) метод для обработки `Name` входные параметры, предоставляемые пользователем или сценарий.</span><span class="sxs-lookup"><span data-stu-id="7e85e-136">This Get-Proc cmdlet overrides the [System.Management.Automation.Cmdlet.Processrecord\*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method to handle the `Name` parameter input provided by the user or a script.</span></span> <span data-ttu-id="7e85e-137">Этот метод будет получения процессов для каждого имени запрошенного процесса и всех процессов, если имя не указано.</span><span class="sxs-lookup"><span data-stu-id="7e85e-137">This method will get the processes for each requested process name or all processes if no name is provided.</span></span> <span data-ttu-id="7e85e-138">Обратите внимание, что в [System.Management.Automation.Cmdlet.Processrecord\*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord), вызов [System.Management.Automation.Cmdlet.Writeobject%28System.Object%2Csystem.Boolean%29](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject%28System.Object%2CSystem.Boolean%29) — механизм выходные данные для отправки выходных объектов в конвейере.</span><span class="sxs-lookup"><span data-stu-id="7e85e-138">Notice that within [System.Management.Automation.Cmdlet.Processrecord\*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord), the call to [System.Management.Automation.Cmdlet.Writeobject%28System.Object%2Csystem.Boolean%29](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject%28System.Object%2CSystem.Boolean%29) is the output mechanism for sending output objects to the pipeline.</span></span> <span data-ttu-id="7e85e-139">Второй параметр этой вызов `enumerateCollection`, имеет значение `true` сообщить среде выполнения Windows PowerShell для перечисления массива объектов процессов и один процесс записи за раз в командную строку.</span><span class="sxs-lookup"><span data-stu-id="7e85e-139">The second parameter of this call, `enumerateCollection`, is set to `true` to tell the Windows PowerShell runtime to enumerate the array of process objects, and write one process at a time to the command line.</span></span>

```csharp
protected override void ProcessRecord()
{
  // If no process names are passed to the cmdlet, get all processes.
  if (processNames == null)
  {
      // Write the processes to the pipeline making them available
      // to the next cmdlet. The second argument of this call tells
      // PowerShell to enumerate the array, and send one process at a
      // time to the pipeline.
      WriteObject(Process.GetProcesses(), true);
  }
  else
  {
    // If process names are passed to the cmdlet, get and write
    // the associated processes.
    foreach (string name in processNames)
    {
      WriteObject(Process.GetProcessesByName(name), true);
    } // End foreach (string name...).
  }
}
```

```vb
Protected Overrides Sub ProcessRecord()
    Dim processes As Process()

    '/ If no process names are passed to the cmdlet, get all processes.
    If processNames Is Nothing Then
        processes = Process.GetProcesses()
    Else

        '/ If process names are specified, write the processes to the
        '/ pipeline to display them or make them available to the next cmdlet.
        For Each name As String In processNames
            '/ The second parameter of this call tells PowerShell to enumerate the
            '/ array, and send one process at a time to the pipeline.
            WriteObject(Process.GetProcessesByName(name), True)
        Next
    End If

End Sub 'ProcessRecord
```

## <a name="code-sample"></a><span data-ttu-id="7e85e-140">Пример кода</span><span class="sxs-lookup"><span data-stu-id="7e85e-140">Code Sample</span></span>

<span data-ttu-id="7e85e-141">Для полной C# пример кода, см. в разделе [пример GetProcessSample03](./getprocesssample03-sample.md).</span><span class="sxs-lookup"><span data-stu-id="7e85e-141">For the complete C# sample code, see [GetProcessSample03 Sample](./getprocesssample03-sample.md).</span></span>

## <a name="defining-object-types-and-formatting"></a><span data-ttu-id="7e85e-142">Определение типов объектов и форматирование</span><span class="sxs-lookup"><span data-stu-id="7e85e-142">Defining Object Types and Formatting</span></span>

<span data-ttu-id="7e85e-143">Windows PowerShell передает данные между командлетами, используя объекты .net.</span><span class="sxs-lookup"><span data-stu-id="7e85e-143">Windows PowerShell passes information between cmdlets using .Net objects.</span></span> <span data-ttu-id="7e85e-144">Следовательно командлета может потребоваться определить его собственного типа, или командлет может потребоваться расширить существующий тип предоставляемые другому командлету.</span><span class="sxs-lookup"><span data-stu-id="7e85e-144">Consequently, a cmdlet may need to define its own type, or the cmdlet may need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="7e85e-145">Дополнительные сведения о определение новых типов или расширения существующих типов, см. в разделе [расширение типов объектов и форматирование](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351).</span><span class="sxs-lookup"><span data-stu-id="7e85e-145">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="7e85e-146">Создание командлета</span><span class="sxs-lookup"><span data-stu-id="7e85e-146">Building the Cmdlet</span></span>

<span data-ttu-id="7e85e-147">После реализации командлета он зарегистрирован с помощью Windows PowerShell с помощью оснастки Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7e85e-147">After implementing a cmdlet it must be registered with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="7e85e-148">Дополнительные сведения о регистрации командлетов см. в разделе [как регистрация командлетов, поставщиков и ведущих приложений](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).</span><span class="sxs-lookup"><span data-stu-id="7e85e-148">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="7e85e-149">Тестирование командлет</span><span class="sxs-lookup"><span data-stu-id="7e85e-149">Testing the Cmdlet</span></span>

<span data-ttu-id="7e85e-150">Если командлет зарегистрирован с помощью Windows PowerShell, проверьте его, запустив его в командной строке.</span><span class="sxs-lookup"><span data-stu-id="7e85e-150">When your cmdlet has been registered with Windows PowerShell, test it by running it on the command line.</span></span> <span data-ttu-id="7e85e-151">Например можно тестировать код для командлета пример.</span><span class="sxs-lookup"><span data-stu-id="7e85e-151">For example, test the code for the sample cmdlet.</span></span> <span data-ttu-id="7e85e-152">Дополнительные сведения об использовании командлетов из командной строки см. в разделе [Приступая к работе с Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="7e85e-152">For more information about using cmdlets from the command line, see the [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span></span>

- <span data-ttu-id="7e85e-153">В командной строке Windows PowerShell введите следующие команды, чтобы получить имена процессов по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="7e85e-153">At the Windows PowerShell prompt, enter the following commands to retrieve the process names through the pipeline.</span></span>

    ```powershell
    PS> type ProcessNames | get-proc
    ```

<span data-ttu-id="7e85e-154">Появляется следующий результат.</span><span class="sxs-lookup"><span data-stu-id="7e85e-154">The following output appears.</span></span>

    ```
    Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)    Id  ProcessName
    -------  ------  -----   ----- -----   ------    --  -----------
        809      21  40856    4448    147    9.50  2288  iexplore
        737      21  26036   16348    144   22.03  3860  iexplore
         39       2   1024     388     30    0.08  3396  notepad
       3927      62  71836   26984    467  195.19  1848  OUTLOOK
    ```

- <span data-ttu-id="7e85e-155">Введите следующие строки, чтобы получить объекты процессов, имеющих `Name` свойство с процессами, которые называются «IEXPLORE».</span><span class="sxs-lookup"><span data-stu-id="7e85e-155">Enter the following lines to get the process objects that have a `Name` property from the processes called "IEXPLORE".</span></span> <span data-ttu-id="7e85e-156">В этом примере используется `Get-Process` командлет (предоставляемое Windows PowerShell), как вышестоящий команду для получения процессов «IEXPLORE».</span><span class="sxs-lookup"><span data-stu-id="7e85e-156">This example uses the `Get-Process` cmdlet (provided by Windows PowerShell) as an upstream command to retrieve the "IEXPLORE" processes.</span></span>

    ```powershell
    PS> get-process iexplore | get-proc
    ```

<span data-ttu-id="7e85e-157">Появляется следующий результат.</span><span class="sxs-lookup"><span data-stu-id="7e85e-157">The following output appears.</span></span>

    ```
    Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)    Id  ProcessName
    -------  ------  -----      ----- -----   ------     -- -----------
        801      21  40720    6544    142    9.52  2288  iexplore
        726      21  25872   16652    138   22.09  3860  iexplore
        801      21  40720    6544    142    9.52  2288  iexplore
        726      21  25872   16652    138   22.09  3860  iexplore
    ```

## <a name="see-also"></a><span data-ttu-id="7e85e-158">См. также</span><span class="sxs-lookup"><span data-stu-id="7e85e-158">See Also</span></span>

[<span data-ttu-id="7e85e-159">Добавление параметров, которые обрабатывают входные данные командной строки</span><span class="sxs-lookup"><span data-stu-id="7e85e-159">Adding Parameters that Process Command Line Input</span></span>](./adding-parameters-that-process-command-line-input.md)

[<span data-ttu-id="7e85e-160">Создайте свой первый командлет</span><span class="sxs-lookup"><span data-stu-id="7e85e-160">Creating Your First Cmdlet</span></span>](./creating-a-cmdlet-without-parameters.md)

[<span data-ttu-id="7e85e-161">Расширение типов объектов и форматирование</span><span class="sxs-lookup"><span data-stu-id="7e85e-161">Extending Object Types and Formatting</span></span>](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[<span data-ttu-id="7e85e-162">Регистрация командлетов, поставщиков и ведущих приложений</span><span class="sxs-lookup"><span data-stu-id="7e85e-162">How to Register Cmdlets, Providers, and Host Applications</span></span>](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[<span data-ttu-id="7e85e-163">Справочник по Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7e85e-163">Windows PowerShell Reference</span></span>](../windows-powershell-reference.md)

[<span data-ttu-id="7e85e-164">Примеры командлетов</span><span class="sxs-lookup"><span data-stu-id="7e85e-164">Cmdlet Samples</span></span>](./cmdlet-samples.md)
