---
title: Добавление параметров, обрабатывающих входные данные конвейера | Документация Майкрософт
ms.date: 09/13/2016
helpviewer_keywords:
- cmdlets [PowerShell Programmer's Guide], pipeline input
- parameters [PowerShell Programmer's Guide], pipeline input
ms.openlocfilehash: a678df30a13086b317d5680ee0fbc4d3c3391235
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784560"
---
# <a name="adding-parameters-that-process-pipeline-input"></a><span data-ttu-id="ffc08-102">Добавление параметров для обработки входных данных конвейера</span><span class="sxs-lookup"><span data-stu-id="ffc08-102">Adding Parameters that Process Pipeline Input</span></span>

<span data-ttu-id="ffc08-103">Один источник входных данных для командлета — это объект в конвейере, исходящий из вышестоящего командлета.</span><span class="sxs-lookup"><span data-stu-id="ffc08-103">One source of input for a cmdlet is an object on the pipeline that originates from an upstream cmdlet.</span></span> <span data-ttu-id="ffc08-104">В этом разделе описывается, как добавить параметр в командлет Get-proc (описывается в разделе [Создание первого командлета](./creating-a-cmdlet-without-parameters.md)), чтобы командлет мог обрабатывать объекты конвейера.</span><span class="sxs-lookup"><span data-stu-id="ffc08-104">This section describes how to add a parameter to the Get-Proc cmdlet (described in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md)) so that the cmdlet can process pipeline objects.</span></span>

<span data-ttu-id="ffc08-105">Этот командлет Get-proc использует `Name` параметр, который принимает входные данные из объекта конвейера, извлекает сведения о процессе с локального компьютера на основе заданных имен, а затем отображает сведения о процессах в командной строке.</span><span class="sxs-lookup"><span data-stu-id="ffc08-105">This Get-Proc cmdlet uses a `Name` parameter that accepts input from a pipeline object, retrieves process information from the local computer based on the supplied names, and then displays information about the processes at the command line.</span></span>

## <a name="defining-the-cmdlet-class"></a><span data-ttu-id="ffc08-106">Определение класса командлета</span><span class="sxs-lookup"><span data-stu-id="ffc08-106">Defining the Cmdlet Class</span></span>

<span data-ttu-id="ffc08-107">Первым шагом при создании командлета всегда является присвоение имени командлета и объявление класса .NET, реализующего командлет.</span><span class="sxs-lookup"><span data-stu-id="ffc08-107">The first step in cmdlet creation is always naming the cmdlet and declaring the .NET class that implements the cmdlet.</span></span> <span data-ttu-id="ffc08-108">Этот командлет извлекает сведения о процессе, поэтому выбранное здесь имя команды — Get.</span><span class="sxs-lookup"><span data-stu-id="ffc08-108">This cmdlet retrieves process information, so the verb name chosen here is "Get".</span></span> <span data-ttu-id="ffc08-109">(Практически любой командлет, который способен получить информацию, может обрабатывать входные данные командной строки.) Дополнительные сведения о утвержденных командах командлетов см. в разделе [имена глаголов командлетов](./approved-verbs-for-windows-powershell-commands.md).</span><span class="sxs-lookup"><span data-stu-id="ffc08-109">(Almost any sort of cmdlet that is capable of retrieving information can process command-line input.) For more information about approved cmdlet verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="ffc08-110">Ниже приведено определение для командлета Get-proc.</span><span class="sxs-lookup"><span data-stu-id="ffc08-110">The following is the definition for this Get-Proc cmdlet.</span></span> <span data-ttu-id="ffc08-111">Подробные сведения об этом определении приведены в [создании первого командлета](./creating-a-cmdlet-without-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="ffc08-111">Details of this definition are given in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md).</span></span>

```csharp
[Cmdlet(VerbsCommon.Get, "proc")]
public class GetProcCommand : Cmdlet
```

```vb
<Cmdlet(VerbsCommon.Get, "Proc")> _
Public Class GetProcCommand
    Inherits Cmdlet
```

## <a name="defining-input-from-the-pipeline"></a><span data-ttu-id="ffc08-112">Определение входных данных из конвейера</span><span class="sxs-lookup"><span data-stu-id="ffc08-112">Defining Input from the Pipeline</span></span>

<span data-ttu-id="ffc08-113">В этом разделе описывается, как определить входные данные из конвейера для командлета.</span><span class="sxs-lookup"><span data-stu-id="ffc08-113">This section describes how to define input from the pipeline for a cmdlet.</span></span> <span data-ttu-id="ffc08-114">Этот командлет Get-proc определяет свойство, представляющее `Name` параметр, как описано в разделе [Добавление параметров, обрабатывающих вход командной строки](./adding-parameters-that-process-command-line-input.md).</span><span class="sxs-lookup"><span data-stu-id="ffc08-114">This Get-Proc cmdlet defines a property that represents the `Name` parameter as described in [Adding Parameters that Process Command Line Input](./adding-parameters-that-process-command-line-input.md).</span></span>
<span data-ttu-id="ffc08-115">(Общие сведения об объявлении параметров см. в этом разделе.)</span><span class="sxs-lookup"><span data-stu-id="ffc08-115">(See that topic for general information about declaring parameters.)</span></span>

<span data-ttu-id="ffc08-116">Однако если командлету необходимо обработать входные данные конвейера, он должен быть привязан к входным значениям среды выполнения Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ffc08-116">However, when a cmdlet needs to process pipeline input, it must have its parameters bound to input values by the Windows PowerShell runtime.</span></span> <span data-ttu-id="ffc08-117">Для этого необходимо добавить `ValueFromPipeline` ключевое слово или добавить `ValueFromPipelineByProperty` ключевое слово в объявление атрибута [System. Management. Automation. параметераттрибуте](/dotnet/api/System.Management.Automation.ParameterAttribute) .</span><span class="sxs-lookup"><span data-stu-id="ffc08-117">To do this, you must add the `ValueFromPipeline` keyword or add the `ValueFromPipelineByProperty` keyword to the [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute declaration.</span></span> <span data-ttu-id="ffc08-118">Укажите `ValueFromPipeline` ключевое слово, если командлет обращается к полному входному объекту.</span><span class="sxs-lookup"><span data-stu-id="ffc08-118">Specify the `ValueFromPipeline` keyword if the cmdlet accesses the complete input object.</span></span> <span data-ttu-id="ffc08-119">Укажите, `ValueFromPipelineByProperty` Если командлет обращается только к свойству объекта.</span><span class="sxs-lookup"><span data-stu-id="ffc08-119">Specify the `ValueFromPipelineByProperty` if the cmdlet accesses only a property of the object.</span></span>

<span data-ttu-id="ffc08-120">Ниже приведено объявление параметра для `Name` параметра командлета Get-proc, принимающего входные данные конвейера.</span><span class="sxs-lookup"><span data-stu-id="ffc08-120">Here is the parameter declaration for the `Name` parameter of this Get-Proc cmdlet that accepts pipeline input.</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample03/GetProcessSample03.cs" range="35-44":::

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

<span data-ttu-id="ffc08-121">В предыдущем объявлении ключевому слову присваивается значение, чтобы `ValueFromPipeline` `true` Среда выполнения Windows PowerShell привязать параметр к входящему объекту, если объект имеет тот же тип, что и параметр, или если он может быть приведен к тому же типу.</span><span class="sxs-lookup"><span data-stu-id="ffc08-121">The previous declaration sets the `ValueFromPipeline` keyword to `true` so that the Windows PowerShell runtime will bind the parameter to the incoming object if the object is the same type as the parameter, or if it can be coerced to the same type.</span></span> <span data-ttu-id="ffc08-122">`ValueFromPipelineByPropertyName`Ключевое слово также имеет значение, чтобы `true` Среда выполнения Windows PowerShell проверит входящий объект для `Name` Свойства.</span><span class="sxs-lookup"><span data-stu-id="ffc08-122">The `ValueFromPipelineByPropertyName` keyword is also set to `true` so that the Windows PowerShell runtime will check the incoming object for a `Name` property.</span></span> <span data-ttu-id="ffc08-123">Если входящий объект имеет такое свойство, среда выполнения привязывает `Name` параметр к `Name` свойству входящего объекта.</span><span class="sxs-lookup"><span data-stu-id="ffc08-123">If the incoming object has such a property, the runtime will bind the `Name` parameter to the `Name` property of the incoming object.</span></span>

> [!NOTE]
> <span data-ttu-id="ffc08-124">Значение `ValueFromPipeline` ключевого слова атрибута для параметра имеет приоритет над параметром `ValueFromPipelineByPropertyName` ключевого слова.</span><span class="sxs-lookup"><span data-stu-id="ffc08-124">The setting of the `ValueFromPipeline` attribute keyword for a parameter takes precedence over the setting for the `ValueFromPipelineByPropertyName` keyword.</span></span>

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="ffc08-125">Переопределение метода обработки входных данных</span><span class="sxs-lookup"><span data-stu-id="ffc08-125">Overriding an Input Processing Method</span></span>

<span data-ttu-id="ffc08-126">Если командлет обрабатывает входные данные конвейера, необходимо переопределить соответствующие методы обработки входных данных.</span><span class="sxs-lookup"><span data-stu-id="ffc08-126">If your cmdlet is to handle pipeline input, it needs to override the appropriate input processing methods.</span></span> <span data-ttu-id="ffc08-127">Основные методы обработки ввода представлены при [создании первого командлета](./creating-a-cmdlet-without-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="ffc08-127">The basic input processing methods are introduced in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md).</span></span>

<span data-ttu-id="ffc08-128">Этот командлет Get-proc переопределяет метод [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) для управления `Name` входными параметрами, предоставленными пользователем или сценарием.</span><span class="sxs-lookup"><span data-stu-id="ffc08-128">This Get-Proc cmdlet overrides the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method to handle the `Name` parameter input provided by the user or a script.</span></span> <span data-ttu-id="ffc08-129">Этот метод получит процессы для каждого запрошенного имени процесса или всех процессов, если имя не указано.</span><span class="sxs-lookup"><span data-stu-id="ffc08-129">This method will get the processes for each requested process name or all processes if no name is provided.</span></span> <span data-ttu-id="ffc08-130">Обратите внимание, что в [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)вызов [WriteObject (System. Object, System. Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) является механизмом вывода для отправки выходных объектов в конвейер.</span><span class="sxs-lookup"><span data-stu-id="ffc08-130">Notice that within [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord), the call to [WriteObject(System.Object,System.Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) is the output mechanism for sending output objects to the pipeline.</span></span> <span data-ttu-id="ffc08-131">Второй параметр этого вызова, `enumerateCollection` ,, имеет значение, чтобы `true` сообщить среде выполнения Windows PowerShell о необходимости перечисления массива объектов процессов и записывать в командную строку один процесс.</span><span class="sxs-lookup"><span data-stu-id="ffc08-131">The second parameter of this call, `enumerateCollection`, is set to `true` to tell the Windows PowerShell runtime to enumerate the array of process objects, and write one process at a time to the command line.</span></span>

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

## <a name="code-sample"></a><span data-ttu-id="ffc08-132">Образец кода</span><span class="sxs-lookup"><span data-stu-id="ffc08-132">Code Sample</span></span>

<span data-ttu-id="ffc08-133">Полный пример кода на C# см. в разделе [GetProcessSample03 Sample](./getprocesssample03-sample.md).</span><span class="sxs-lookup"><span data-stu-id="ffc08-133">For the complete C# sample code, see [GetProcessSample03 Sample](./getprocesssample03-sample.md).</span></span>

## <a name="defining-object-types-and-formatting"></a><span data-ttu-id="ffc08-134">Определение типов объектов и форматирование</span><span class="sxs-lookup"><span data-stu-id="ffc08-134">Defining Object Types and Formatting</span></span>

<span data-ttu-id="ffc08-135">Windows PowerShell передает сведения между командлетами с помощью объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="ffc08-135">Windows PowerShell passes information between cmdlets using .Net objects.</span></span> <span data-ttu-id="ffc08-136">Следовательно, командлету может потребоваться определить собственный тип, или командлету может потребоваться расширить существующий тип, предоставленный другим командлетом.</span><span class="sxs-lookup"><span data-stu-id="ffc08-136">Consequently, a cmdlet may need to define its own type, or the cmdlet may need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="ffc08-137">Дополнительные сведения об определении новых типов или расширении существующих типов см. в разделе [расширение типов объектов и форматирование](/previous-versions//ms714665(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="ffc08-137">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85)).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="ffc08-138">Создание командлета</span><span class="sxs-lookup"><span data-stu-id="ffc08-138">Building the Cmdlet</span></span>

<span data-ttu-id="ffc08-139">После реализации командлета его необходимо зарегистрировать в Windows PowerShell с помощью оснастки Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ffc08-139">After implementing a cmdlet it must be registered with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="ffc08-140">Дополнительные сведения о регистрации командлетов см. [в разделе Регистрация командлетов, поставщиков и ведущих приложений](/previous-versions//ms714644(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="ffc08-140">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85)).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="ffc08-141">Тестирование командлета</span><span class="sxs-lookup"><span data-stu-id="ffc08-141">Testing the Cmdlet</span></span>

<span data-ttu-id="ffc08-142">После регистрации командлета в Windows PowerShell проверьте его, запустив в командной строке.</span><span class="sxs-lookup"><span data-stu-id="ffc08-142">When your cmdlet has been registered with Windows PowerShell, test it by running it on the command line.</span></span> <span data-ttu-id="ffc08-143">Например, протестируйте код для примера командлета.</span><span class="sxs-lookup"><span data-stu-id="ffc08-143">For example, test the code for the sample cmdlet.</span></span> <span data-ttu-id="ffc08-144">Дополнительные сведения об использовании командлетов из командной строки см. в [Начало работы с помощью Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="ffc08-144">For more information about using cmdlets from the command line, see the [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span></span>

- <span data-ttu-id="ffc08-145">В командной строке Windows PowerShell введите следующие команды, чтобы получить имена процессов через конвейер.</span><span class="sxs-lookup"><span data-stu-id="ffc08-145">At the Windows PowerShell prompt, enter the following commands to retrieve the process names through the pipeline.</span></span>

  ```powershell
  PS> type ProcessNames | get-proc
  ```

  <span data-ttu-id="ffc08-146">Появится следующий результат.</span><span class="sxs-lookup"><span data-stu-id="ffc08-146">The following output appears.</span></span>

  ```
  Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)    Id  ProcessName
  -------  ------  -----   ----- -----   ------    --  -----------
      809      21  40856    4448    147    9.50  2288  iexplore
      737      21  26036   16348    144   22.03  3860  iexplore
       39       2   1024     388     30    0.08  3396  notepad
     3927      62  71836   26984    467  195.19  1848  OUTLOOK
  ```

- <span data-ttu-id="ffc08-147">Введите следующие строки, чтобы получить объекты процесса со `Name` свойством из процессов с именем "iexplore".</span><span class="sxs-lookup"><span data-stu-id="ffc08-147">Enter the following lines to get the process objects that have a `Name` property from the processes called "IEXPLORE".</span></span> <span data-ttu-id="ffc08-148">В этом примере используется `Get-Process` командлет (предоставленный Windows PowerShell) в качестве вышестоящей команды для получения процессов iexplore.</span><span class="sxs-lookup"><span data-stu-id="ffc08-148">This example uses the `Get-Process` cmdlet (provided by Windows PowerShell) as an upstream command to retrieve the "IEXPLORE" processes.</span></span>

  ```powershell
  PS> get-process iexplore | get-proc
  ```

  <span data-ttu-id="ffc08-149">Появится следующий результат.</span><span class="sxs-lookup"><span data-stu-id="ffc08-149">The following output appears.</span></span>

  ```
  Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)    Id  ProcessName
  -------  ------  -----   ----- -----   ------    --  -----------
      801      21  40720    6544    142    9.52  2288  iexplore
      726      21  25872   16652    138   22.09  3860  iexplore
      801      21  40720    6544    142    9.52  2288  iexplore
      726      21  25872   16652    138   22.09  3860  iexplore
  ```

## <a name="see-also"></a><span data-ttu-id="ffc08-150">См. также</span><span class="sxs-lookup"><span data-stu-id="ffc08-150">See Also</span></span>

[<span data-ttu-id="ffc08-151">Добавление параметров, обрабатывающих вход командной строки</span><span class="sxs-lookup"><span data-stu-id="ffc08-151">Adding Parameters that Process Command Line Input</span></span>](./adding-parameters-that-process-command-line-input.md)

[<span data-ttu-id="ffc08-152">Создание первого командлета</span><span class="sxs-lookup"><span data-stu-id="ffc08-152">Creating Your First Cmdlet</span></span>](./creating-a-cmdlet-without-parameters.md)

<span data-ttu-id="ffc08-153">[Расширение типов объектов и форматирование](/previous-versions//ms714665(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="ffc08-153">[Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85))</span></span>

<span data-ttu-id="ffc08-154">[Регистрация командлетов, поставщиков и ведущих приложений](/previous-versions//ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="ffc08-154">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85))</span></span>

[<span data-ttu-id="ffc08-155">Справочник по Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ffc08-155">Windows PowerShell Reference</span></span>](../windows-powershell-reference.md)

[<span data-ttu-id="ffc08-156">Примеры командлетов</span><span class="sxs-lookup"><span data-stu-id="ffc08-156">Cmdlet Samples</span></span>](./cmdlet-samples.md)
