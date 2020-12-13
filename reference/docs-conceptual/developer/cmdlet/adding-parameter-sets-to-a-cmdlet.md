---
ms.date: 09/13/2016
ms.topic: reference
title: Добавление наборов параметров в командлет
description: Добавление наборов параметров в командлет
ms.openlocfilehash: dd5ee2a880a4d516ea82e5afe0ced12369197243
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648655"
---
# <a name="adding-parameter-sets-to-a-cmdlet"></a><span data-ttu-id="20242-103">Добавление наборов параметров в командлет</span><span class="sxs-lookup"><span data-stu-id="20242-103">Adding Parameter Sets to a Cmdlet</span></span>

## <a name="things-to-know-about-parameter-sets"></a><span data-ttu-id="20242-104">Сведения о наборах параметров</span><span class="sxs-lookup"><span data-stu-id="20242-104">Things to Know About Parameter Sets</span></span>

<span data-ttu-id="20242-105">Windows PowerShell определяет набор параметров как группу параметров, которые работают вместе.</span><span class="sxs-lookup"><span data-stu-id="20242-105">Windows PowerShell defines a parameter set as a group of parameters that operate together.</span></span> <span data-ttu-id="20242-106">Группируя параметры командлета, можно создать один командлет, который может изменить его функциональность в зависимости от того, какую группу параметров указывает пользователь.</span><span class="sxs-lookup"><span data-stu-id="20242-106">By grouping the parameters of a cmdlet, you can create a single cmdlet that can change its functionality based on what group of parameters the user specifies.</span></span>

<span data-ttu-id="20242-107">Примером командлета, использующего два набора параметров для определения различных функциональных возможностей, является `Get-EventLog` командлет, предоставляемый Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="20242-107">An example of a cmdlet that uses two parameter sets to define different functionalities is the `Get-EventLog` cmdlet that is provided by Windows PowerShell.</span></span> <span data-ttu-id="20242-108">Этот командлет возвращает другие сведения, когда пользователь указывает `List` параметр или `LogName` .</span><span class="sxs-lookup"><span data-stu-id="20242-108">This cmdlet returns different information when the user specifies the `List` or `LogName` parameter.</span></span> <span data-ttu-id="20242-109">Если `LogName` указан параметр, командлет возвращает сведения о событиях в заданном журнале событий.</span><span class="sxs-lookup"><span data-stu-id="20242-109">If the `LogName` parameter is specified, the cmdlet returns information about the events in a given event log.</span></span> <span data-ttu-id="20242-110">Если `List` указан параметр, командлет возвращает сведения о самих файлах журнала (а не сведения о событиях, которые они содержат).</span><span class="sxs-lookup"><span data-stu-id="20242-110">If the `List` parameter is specified, the cmdlet returns information about the log files themselves (not the event information they contain).</span></span> <span data-ttu-id="20242-111">В этом случае `List` `LogName` Параметры и указывают два отдельных набора параметров.</span><span class="sxs-lookup"><span data-stu-id="20242-111">In this case, the `List` and `LogName` parameters identify two separate parameter sets.</span></span>

<span data-ttu-id="20242-112">Два важных момента, о которых следует помнить, — это то, что среда выполнения Windows PowerShell использует только один набор параметров для конкретного входа и что каждый набор параметров должен иметь по крайней мере один параметр, уникальный для этого набора параметров.</span><span class="sxs-lookup"><span data-stu-id="20242-112">Two important things to remember about parameter sets is that the Windows PowerShell runtime uses only one parameter set for a particular input, and that each parameter set must have at least one parameter that is unique for that parameter set.</span></span>

<span data-ttu-id="20242-113">Чтобы проиллюстрировать этот последний момент, этот командлет Stop-Proc использует три набора параметров: `ProcessName` , `ProcessId` и `InputObject` .</span><span class="sxs-lookup"><span data-stu-id="20242-113">To illustrate that last point, this Stop-Proc cmdlet uses three parameter sets: `ProcessName`, `ProcessId`, and `InputObject`.</span></span> <span data-ttu-id="20242-114">Каждый из этих наборов параметров имеет один параметр, который не входит в другие наборы параметров.</span><span class="sxs-lookup"><span data-stu-id="20242-114">Each of these parameter sets has one parameter that is not in the other parameter sets.</span></span> <span data-ttu-id="20242-115">Наборы параметров могут совместно использовать другие параметры, но командлет использует уникальные параметры, `ProcessName` `ProcessId` и, `InputObject` чтобы определить, какой набор параметров следует использовать в среде выполнения Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="20242-115">The parameter sets could share other parameters, but the cmdlet uses the unique parameters `ProcessName`, `ProcessId`, and `InputObject` to identify which set of parameters that the Windows PowerShell runtime should use.</span></span>

## <a name="declaring-the-cmdlet-class"></a><span data-ttu-id="20242-116">Объявление класса командлета</span><span class="sxs-lookup"><span data-stu-id="20242-116">Declaring the Cmdlet Class</span></span>

<span data-ttu-id="20242-117">Первым шагом при создании командлета всегда является присвоение имени командлета и объявление класса .NET, реализующего командлет.</span><span class="sxs-lookup"><span data-stu-id="20242-117">The first step in cmdlet creation is always naming the cmdlet and declaring the .NET class that implements the cmdlet.</span></span> <span data-ttu-id="20242-118">Для этого командлета используется команда жизненного цикла "Stop", так как командлет останавливает системные процессы.</span><span class="sxs-lookup"><span data-stu-id="20242-118">For this cmdlet, the lifecycle verb "Stop" is used because the cmdlet stops system processes.</span></span> <span data-ttu-id="20242-119">Имя существительное "proc" используется, так как командлет работает с процессами.</span><span class="sxs-lookup"><span data-stu-id="20242-119">The noun name "Proc" is used because the cmdlet works on processes.</span></span> <span data-ttu-id="20242-120">Обратите внимание, что в приведенном ниже объявлении команда командлета и имя существительное отражаются в имени класса командлета.</span><span class="sxs-lookup"><span data-stu-id="20242-120">In the declaration below, note that the cmdlet verb and noun name are reflected in the name of the cmdlet class.</span></span>

> [!NOTE]
> <span data-ttu-id="20242-121">Дополнительные сведения о утвержденных именах глаголов командлетов см. в разделе [имена глаголов командлетов](./approved-verbs-for-windows-powershell-commands.md).</span><span class="sxs-lookup"><span data-stu-id="20242-121">For more information about approved cmdlet verb names, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="20242-122">Следующий код является определением класса для этого командлета Stop-Proc.</span><span class="sxs-lookup"><span data-stu-id="20242-122">The following code is the class definition for this Stop-Proc cmdlet.</span></span>

```csharp
[Cmdlet(VerbsLifecycle.Stop, "Proc",
        DefaultParameterSetName = "ProcessId",
        SupportsShouldProcess = true)]
public class StopProcCommand : PSCmdlet
```

```vb
<Cmdlet(VerbsLifecycle.Stop, "Proc", DefaultParameterSetName:="ProcessId", _
SupportsShouldProcess:=True)> _
Public Class StopProcCommand
    Inherits PSCmdlet
```

## <a name="declaring-the-parameters-of-the-cmdlet"></a><span data-ttu-id="20242-123">Объявление параметров командлета</span><span class="sxs-lookup"><span data-stu-id="20242-123">Declaring the Parameters of the Cmdlet</span></span>

<span data-ttu-id="20242-124">Этот командлет определяет три параметра, необходимые в качестве входных данных для командлета (эти параметры также определяют наборы параметров), а также `Force` параметр, который управляет действием командлета и `PassThru` параметром, который определяет, отправляет ли командлет выходной объект через конвейер.</span><span class="sxs-lookup"><span data-stu-id="20242-124">This cmdlet defines three parameters needed as input to the cmdlet (these parameters also define the parameter sets), as well as a `Force` parameter that manages what the cmdlet does and a `PassThru` parameter that determines whether the cmdlet sends an output object through the pipeline.</span></span> <span data-ttu-id="20242-125">По умолчанию этот командлет не передает объект через конвейер.</span><span class="sxs-lookup"><span data-stu-id="20242-125">By default, this cmdlet does not pass an object through the pipeline.</span></span> <span data-ttu-id="20242-126">Дополнительные сведения об этих двух последних параметрах см. в разделе [Создание командлета, изменяющего систему](./creating-a-cmdlet-that-modifies-the-system.md).</span><span class="sxs-lookup"><span data-stu-id="20242-126">For more information about these last two parameters, see [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md).</span></span>

### <a name="declaring-the-name-parameter"></a><span data-ttu-id="20242-127">Объявление параметра Name</span><span class="sxs-lookup"><span data-stu-id="20242-127">Declaring the Name Parameter</span></span>

<span data-ttu-id="20242-128">Этот входной параметр позволяет пользователю указать имена процессов, которые должны быть остановлены.</span><span class="sxs-lookup"><span data-stu-id="20242-128">This input parameter allows the user to specify the names of the processes to be stopped.</span></span> <span data-ttu-id="20242-129">Обратите внимание, что `ParameterSetName` ключевое слово Attribute атрибута [System. Management. Automation. параметераттрибуте](/dotnet/api/System.Management.Automation.ParameterAttribute) задает `ProcessName` набор параметров для этого параметра.</span><span class="sxs-lookup"><span data-stu-id="20242-129">Note that the `ParameterSetName` attribute keyword of the [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute specifies the `ProcessName` parameter set for this parameter.</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/StopProcessSample04/StopProcessSample04.cs" range="44-58":::

```vb
<Parameter(Position:=0, ParameterSetName:="ProcessName", _
Mandatory:=True, _
ValueFromPipeline:=True, ValueFromPipelineByPropertyName:=True, _
HelpMessage:="The name of one or more processes to stop. " & _
    "Wildcards are permitted."), [Alias]("ProcessName")> _
Public Property Name() As String()
    Get
        Return processNames
    End Get
    Set(ByVal value As String())
        processNames = value
    End Set
End Property

Private processNames() As String
```

<span data-ttu-id="20242-130">Обратите внимание, что этому параметру присваивается псевдоним «ProcessName».</span><span class="sxs-lookup"><span data-stu-id="20242-130">Note also that the alias "ProcessName" is given to this parameter.</span></span>

### <a name="declaring-the-id-parameter"></a><span data-ttu-id="20242-131">Объявление параметра ID</span><span class="sxs-lookup"><span data-stu-id="20242-131">Declaring the Id Parameter</span></span>

<span data-ttu-id="20242-132">Этот входной параметр позволяет пользователю указать идентификаторы процессов, которые должны быть остановлены.</span><span class="sxs-lookup"><span data-stu-id="20242-132">This input parameter allows the user to specify the identifiers of the processes to be stopped.</span></span> <span data-ttu-id="20242-133">Обратите внимание, что `ParameterSetName` ключевое слово Attribute атрибута [System. Management. Automation. параметераттрибуте](/dotnet/api/System.Management.Automation.ParameterAttribute) задает `ProcessId` набор параметров.</span><span class="sxs-lookup"><span data-stu-id="20242-133">Note that the `ParameterSetName` attribute keyword of the [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute specifies the `ProcessId` parameter set.</span></span>

```csharp
[Parameter(
           ParameterSetName = "ProcessId",
           Mandatory = true,
           ValueFromPipelineByPropertyName = true,
           ValueFromPipeline = true
)]
[Alias("ProcessId")]
public int[] Id
{
  get { return processIds; }
  set { processIds = value; }
}
private int[] processIds;
```

```vb
<Parameter(ParameterSetName:="ProcessId", _
Mandatory:=True, _
ValueFromPipelineByPropertyName:=True, _
ValueFromPipeline:=True), [Alias]("ProcessId")> _
Public Property Id() As Integer()
    Get
        Return processIds
    End Get
    Set(ByVal value As Integer())
        processIds = value
    End Set
End Property
Private processIds() As Integer
```

<span data-ttu-id="20242-134">Обратите внимание, что этому параметру присваивается псевдоним «ProcessId».</span><span class="sxs-lookup"><span data-stu-id="20242-134">Note also that the alias "ProcessId" is given to this parameter.</span></span>

### <a name="declaring-the-inputobject-parameter"></a><span data-ttu-id="20242-135">Объявление параметра InputObject</span><span class="sxs-lookup"><span data-stu-id="20242-135">Declaring the InputObject Parameter</span></span>

<span data-ttu-id="20242-136">Этот входной параметр позволяет пользователю указать входной объект, содержащий сведения о останавливаемых процессах.</span><span class="sxs-lookup"><span data-stu-id="20242-136">This input parameter allows the user to specify an input object that contains information about the processes to be stopped.</span></span> <span data-ttu-id="20242-137">Обратите внимание, что `ParameterSetName` ключевое слово Attribute атрибута [System. Management. Automation. параметераттрибуте](/dotnet/api/System.Management.Automation.ParameterAttribute) задает `InputObject` набор параметров для этого параметра.</span><span class="sxs-lookup"><span data-stu-id="20242-137">Note that the `ParameterSetName` attribute keyword of the [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute specifies the `InputObject` parameter set for this parameter.</span></span>

```csharp
[Parameter(
           ParameterSetName = "InputObject",
           Mandatory = true,
           ValueFromPipeline = true)]
public Process[] InputObject
{
  get { return inputObject; }
  set { inputObject = value; }
}
private Process[] inputObject;
```

```vb
<Parameter(ParameterSetName:="InputObject", _
Mandatory:=True, ValueFromPipeline:=True)> _
Public Property InputObject() As Process()
    Get
        Return myInputObject
    End Get
    Set(ByVal value As Process())
        myInputObject = value
    End Set
End Property
Private myInputObject() As Process
```

<span data-ttu-id="20242-138">Обратите внимание, что у этого параметра нет псевдонима.</span><span class="sxs-lookup"><span data-stu-id="20242-138">Note also that this parameter has no alias.</span></span>

### <a name="declaring-parameters-in-multiple-parameter-sets"></a><span data-ttu-id="20242-139">Объявление параметров в нескольких наборах параметров</span><span class="sxs-lookup"><span data-stu-id="20242-139">Declaring Parameters in Multiple Parameter Sets</span></span>

<span data-ttu-id="20242-140">Хотя для каждого набора параметров должен существовать уникальный параметр, параметры могут принадлежать нескольким наборам параметров.</span><span class="sxs-lookup"><span data-stu-id="20242-140">Although there must be a unique parameter for each parameter set, parameters can belong to more than one parameter set.</span></span> <span data-ttu-id="20242-141">В этих случаях предоставьте общему параметру объявление атрибута [System. Management. Automation. параметераттрибуте](/dotnet/api/System.Management.Automation.ParameterAttribute) для каждого набора, которому принадлежит параметр.</span><span class="sxs-lookup"><span data-stu-id="20242-141">In these cases, give the shared parameter a [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute declaration for each set to which that the parameter belongs.</span></span> <span data-ttu-id="20242-142">Если параметр находится во всех наборах параметров, достаточно объявить атрибут Parameter только один раз и не нужно указывать имя набора параметров.</span><span class="sxs-lookup"><span data-stu-id="20242-142">If a parameter is in all parameter sets, you only have to declare the parameter attribute once and do not need to specify the parameter set name.</span></span>

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="20242-143">Переопределение метода обработки входных данных</span><span class="sxs-lookup"><span data-stu-id="20242-143">Overriding an Input Processing Method</span></span>

<span data-ttu-id="20242-144">Каждый командлет должен переопределять метод обработки ввода, чаще всего это будет метод [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) .</span><span class="sxs-lookup"><span data-stu-id="20242-144">Every cmdlet must override an input processing method, most often this will be the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span> <span data-ttu-id="20242-145">В этом командлете метод [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) переопределен, чтобы командлет мог обработать любое количество процессов.</span><span class="sxs-lookup"><span data-stu-id="20242-145">In this cmdlet, the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method is overridden so that the cmdlet can process any number of processes.</span></span> <span data-ttu-id="20242-146">Он содержит инструкцию SELECT, которая вызывает другой метод в зависимости от того, какой набор параметров задан пользователем.</span><span class="sxs-lookup"><span data-stu-id="20242-146">It contains a Select statement that calls a different method based on which parameter set the user has specified.</span></span>

```csharp
protected override void ProcessRecord()
{
  switch (ParameterSetName)
  {
    case "ProcessName":
         ProcessByName();
         break;

    case "ProcessId":
         ProcessById();
         break;

    case "InputObject":
         foreach (Process process in inputObject)
         {
           SafeStopProcess(process);
         }
         break;

    default:
         throw new ArgumentException("Bad ParameterSet Name");
  } // switch (ParameterSetName...
} // ProcessRecord
```

```vb
Protected Overrides Sub ProcessRecord()
    Select Case ParameterSetName
        Case "ProcessName"
            ProcessByName()

        Case "ProcessId"
            ProcessById()

        Case "InputObject"
            Dim process As Process
            For Each process In myInputObject
                SafeStopProcess(process)
            Next process

        Case Else
            Throw New ArgumentException("Bad ParameterSet Name")
    End Select

End Sub 'ProcessRecord ' ProcessRecord
```

<span data-ttu-id="20242-147">Вспомогательные методы, вызываемые инструкцией SELECT, не описаны здесь, но их реализация можно увидеть в полном примере кода в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="20242-147">The Helper methods called by the Select statement are not described here, but you can see their implementation in the complete code sample in the next section.</span></span>

## <a name="code-sample"></a><span data-ttu-id="20242-148">Образец кода</span><span class="sxs-lookup"><span data-stu-id="20242-148">Code Sample</span></span>

<span data-ttu-id="20242-149">Полный пример кода на C# см. в разделе [StopProcessSample04 Sample](./stopprocesssample04-sample.md).</span><span class="sxs-lookup"><span data-stu-id="20242-149">For the complete C# sample code, see [StopProcessSample04 Sample](./stopprocesssample04-sample.md).</span></span>

## <a name="defining-object-types-and-formatting"></a><span data-ttu-id="20242-150">Определение типов объектов и форматирование</span><span class="sxs-lookup"><span data-stu-id="20242-150">Defining Object Types and Formatting</span></span>

<span data-ttu-id="20242-151">Windows PowerShell передает сведения между командлетами с помощью объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="20242-151">Windows PowerShell passes information between cmdlets using .NET objects.</span></span> <span data-ttu-id="20242-152">Следовательно, командлету может потребоваться определить собственный тип, или командлету может потребоваться расширить существующий тип, предоставленный другим командлетом.</span><span class="sxs-lookup"><span data-stu-id="20242-152">Consequently, a cmdlet might need to define its own type, or the cmdlet might need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="20242-153">Дополнительные сведения об определении новых типов или расширении существующих типов см. в разделе [расширение типов объектов и форматирование](/previous-versions//ms714665(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="20242-153">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85)).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="20242-154">Создание командлета</span><span class="sxs-lookup"><span data-stu-id="20242-154">Building the Cmdlet</span></span>

<span data-ttu-id="20242-155">После реализации командлета необходимо зарегистрировать его в Windows PowerShell с помощью оснастки Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="20242-155">After implementing a cmdlet, you must register it with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="20242-156">Дополнительные сведения о регистрации командлетов см. [в разделе Регистрация командлетов, поставщиков и ведущих приложений](/previous-versions//ms714644(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="20242-156">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85)).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="20242-157">Тестирование командлета</span><span class="sxs-lookup"><span data-stu-id="20242-157">Testing the Cmdlet</span></span>

<span data-ttu-id="20242-158">После регистрации командлета в Windows PowerShell проверьте его, запустив в командной строке.</span><span class="sxs-lookup"><span data-stu-id="20242-158">When your cmdlet has been registered with Windows PowerShell, test it by running it on the command line.</span></span> <span data-ttu-id="20242-159">Ниже приведены некоторые тесты, показывающие, как `ProcessId` `InputObject` можно использовать параметры и для проверки наборов параметров для завершения процесса.</span><span class="sxs-lookup"><span data-stu-id="20242-159">Here are some tests that show how the `ProcessId` and `InputObject` parameters can be used to test their parameter sets to stop a process.</span></span>

- <span data-ttu-id="20242-160">После запуска Windows PowerShell выполните командлет Stop-Proc с `ProcessId` набором параметров, чтобы приступить к прерыванию процесса на основе его идентификатора.</span><span class="sxs-lookup"><span data-stu-id="20242-160">With Windows PowerShell started, run the Stop-Proc cmdlet with the `ProcessId` parameter set to stop a process based on its identifier.</span></span> <span data-ttu-id="20242-161">В этом случае командлет использует `ProcessId` набор параметров для завершения процесса.</span><span class="sxs-lookup"><span data-stu-id="20242-161">In this case, the cmdlet is using the `ProcessId` parameter set to stop the process.</span></span>

  ```
  PS> stop-proc -Id 444
  Confirm
  Are you sure you want to perform this action?
  Performing operation "stop-proc" on Target "notepad (444)".
  [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
  ```

- <span data-ttu-id="20242-162">После запуска Windows PowerShell выполните командлет Stop-Proc с параметром, равным, `InputObject` чтобы останавливаются процессы объекта Notepad, полученного с помощью `Get-Process` команды.</span><span class="sxs-lookup"><span data-stu-id="20242-162">With Windows PowerShell started, run the Stop-Proc cmdlet with the `InputObject` parameter set to stop processes on the Notepad object retrieved by the `Get-Process` command.</span></span>

  ```
  PS> get-process notepad | stop-proc
  Confirm
  Are you sure you want to perform this action?
  Performing operation "stop-proc" on Target "notepad (444)".
  [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
  ```

## <a name="see-also"></a><span data-ttu-id="20242-163">См. также:</span><span class="sxs-lookup"><span data-stu-id="20242-163">See Also</span></span>

[<span data-ttu-id="20242-164">Создание командлета, который изменяет систему</span><span class="sxs-lookup"><span data-stu-id="20242-164">Creating a Cmdlet that Modifies the System</span></span>](./creating-a-cmdlet-that-modifies-the-system.md)

[<span data-ttu-id="20242-165">Создание командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="20242-165">How to Create a Windows PowerShell Cmdlet</span></span>](/powershell/scripting/developer/cmdlet/writing-a-windows-powershell-cmdlet)

<span data-ttu-id="20242-166">[Расширение типов объектов и форматирование](/previous-versions//ms714665(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="20242-166">[Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85))</span></span>

<span data-ttu-id="20242-167">[Регистрация командлетов, поставщиков и ведущих приложений](/previous-versions//ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="20242-167">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85))</span></span>

[<span data-ttu-id="20242-168">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="20242-168">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
