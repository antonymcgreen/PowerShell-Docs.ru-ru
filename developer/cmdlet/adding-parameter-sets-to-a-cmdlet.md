---
title: Добавление параметра наборов в командлет | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- parameter sets [PowerShell Programmer's Guide]
ms.assetid: a6131db4-fd6e-45f1-bd47-17e7174afd56
caps.latest.revision: 8
ms.openlocfilehash: f0bff11618c18bf53b9c2a185445795a17306fa3
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068843"
---
# <a name="adding-parameter-sets-to-a-cmdlet"></a><span data-ttu-id="93206-102">Добавление наборов параметров в командлет</span><span class="sxs-lookup"><span data-stu-id="93206-102">Adding Parameter Sets to a Cmdlet</span></span>

<span data-ttu-id="93206-103">В этом разделе описывается добавление наборов параметров в командлет Stop-Proc (описано в разделе [Создание командлет, который изменяет система](./creating-a-cmdlet-that-modifies-the-system.md)).</span><span class="sxs-lookup"><span data-stu-id="93206-103">This section describes how to add parameter sets to the Stop-Proc cmdlet (described in [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md)).</span></span> <span data-ttu-id="93206-104">Как и другие командлеты Stop-Proc, описанные в руководстве по программированию, этот командлет пытается остановить процессы, которые можно получить с помощью командлета Get-Proc (описано в разделе [Создание свой первый командлет](./creating-a-cmdlet-without-parameters.md)).</span><span class="sxs-lookup"><span data-stu-id="93206-104">Similar to the other Stop-Proc cmdlets described in this Programmer's Guide, this cmdlet attempts to stop processes that are retrieved using the Get-Proc cmdlet (described in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md)).</span></span>

<span data-ttu-id="93206-105">Следующие подразделы этого раздела.</span><span class="sxs-lookup"><span data-stu-id="93206-105">Topics in this section include the following:</span></span>

- [<span data-ttu-id="93206-106">Что нужно знать о наборов параметров</span><span class="sxs-lookup"><span data-stu-id="93206-106">Things to Know About Parameter Sets</span></span>](#Adding-Parameter-Sets-to-a-Cmdlet)

- [<span data-ttu-id="93206-107">Объявление класса командлета</span><span class="sxs-lookup"><span data-stu-id="93206-107">Declaring the Cmdlet Class</span></span>](#Declaring-the-Cmdlet-Class)

- [<span data-ttu-id="93206-108">Объявление параметров командлета</span><span class="sxs-lookup"><span data-stu-id="93206-108">Declaring the Parameters of the Cmdlet</span></span>](#Declaring-the-Parameters-of-the-Cmdlet)

- [<span data-ttu-id="93206-109">Переопределив метод обработки входных данных</span><span class="sxs-lookup"><span data-stu-id="93206-109">Overriding an Input Processing Method</span></span>](#Overriding-an-Input-Processing-Method)

- [<span data-ttu-id="93206-110">Пример кода</span><span class="sxs-lookup"><span data-stu-id="93206-110">Code Sample</span></span>](#Declaring-the-Parameters-of-the-Cmdlet)

- [<span data-ttu-id="93206-111">Определение типов объектов и форматирование</span><span class="sxs-lookup"><span data-stu-id="93206-111">Defining Object Types and Formatting</span></span>](#Defining-Object-Types-and-Formatting)

- [<span data-ttu-id="93206-112">Создание командлета</span><span class="sxs-lookup"><span data-stu-id="93206-112">Building the Cmdlet</span></span>](#Building-the-Cmdlet)

- [<span data-ttu-id="93206-113">Тестирование командлет</span><span class="sxs-lookup"><span data-stu-id="93206-113">Testing the Cmdlet</span></span>](#Testing-the-Cmdlet)

## <a name="things-to-know-about-parameter-sets"></a><span data-ttu-id="93206-114">Что нужно знать о наборов параметров</span><span class="sxs-lookup"><span data-stu-id="93206-114">Things to Know About Parameter Sets</span></span>

<span data-ttu-id="93206-115">Windows PowerShell определяет группу параметров, которые работают совместно в качестве параметра.</span><span class="sxs-lookup"><span data-stu-id="93206-115">Windows PowerShell defines a parameter set as a group of parameters that operate together.</span></span> <span data-ttu-id="93206-116">Группируя параметры командлета, можно создать один командлет, который можно изменить его функциональных возможностей, в зависимости от того, какие группу параметров, указанных пользователем.</span><span class="sxs-lookup"><span data-stu-id="93206-116">By grouping the parameters of a cmdlet, you can create a single cmdlet that can change its functionality based on what group of parameters the user specifies.</span></span>

<span data-ttu-id="93206-117">Например, командлет, который использует два набора параметров, чтобы определить различные функции `Get-EventLog` командлет, предоставляемый Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="93206-117">An example of a cmdlet that uses two parameter sets to define different functionalities is the `Get-EventLog` cmdlet that is provided by Windows PowerShell.</span></span> <span data-ttu-id="93206-118">Этот командлет возвращает различные сведения, когда пользователь указывает `List` или `LogName` параметра.</span><span class="sxs-lookup"><span data-stu-id="93206-118">This cmdlet returns different information when the user specifies the `List` or `LogName` parameter.</span></span> <span data-ttu-id="93206-119">Если `LogName` параметр указан, командлет возвращает информацию о событиях в данном журнале событий.</span><span class="sxs-lookup"><span data-stu-id="93206-119">If the `LogName` parameter is specified, the cmdlet returns information about the events in a given event log.</span></span> <span data-ttu-id="93206-120">Если `List` параметр указан, командлет возвращает сведения о журнале файлов самостоятельно (не о событиях в них).</span><span class="sxs-lookup"><span data-stu-id="93206-120">If the `List` parameter is specified, the cmdlet returns information about the log files themselves (not the event information they contain).</span></span> <span data-ttu-id="93206-121">В этом случае `List` и `LogName` параметры определяют две различные наборы параметров.</span><span class="sxs-lookup"><span data-stu-id="93206-121">In this case, the `List` and `LogName` parameters identify two separate parameter sets.</span></span>

<span data-ttu-id="93206-122">Два соображения следует помнить о наборов параметров том, что среда выполнения Windows PowerShell использует только один набор параметров для отдельного входного, и что каждый набор параметров должен иметь по крайней мере один параметр, является уникальным для этого набора параметров.</span><span class="sxs-lookup"><span data-stu-id="93206-122">Two important things to remember about parameter sets is that the Windows PowerShell runtime uses only one parameter set for a particular input, and that each parameter set must have at least one parameter that is unique for that parameter set.</span></span>

<span data-ttu-id="93206-123">Для иллюстрации этой последней точки, этот командлет Stop-Proc использует три набора параметров: `ProcessName`, `ProcessId`, и `InputObject`.</span><span class="sxs-lookup"><span data-stu-id="93206-123">To illustrate that last point, this Stop-Proc cmdlet uses three parameter sets: `ProcessName`, `ProcessId`, and `InputObject`.</span></span> <span data-ttu-id="93206-124">Каждый из этих наборов параметров имеет один параметр, который не находится в другие наборы параметров.</span><span class="sxs-lookup"><span data-stu-id="93206-124">Each of these parameter sets has one parameter that is not in the other parameter sets.</span></span> <span data-ttu-id="93206-125">Наборы параметров может совместно использовать другие параметры, но командлет будет использовать уникальные параметры `ProcessName`, `ProcessId`, и `InputObject` для определения, какой набор параметров, которые следует использовать среды выполнения Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="93206-125">The parameter sets could share other parameters, but the cmdlet uses the unique parameters `ProcessName`, `ProcessId`, and `InputObject` to identify which set of parameters that the Windows PowerShell runtime should use.</span></span>

## <a name="declaring-the-cmdlet-class"></a><span data-ttu-id="93206-126">Объявление класса командлета</span><span class="sxs-lookup"><span data-stu-id="93206-126">Declaring the Cmdlet Class</span></span>

<span data-ttu-id="93206-127">Первым шагом в создании командлет всегда присвоение имени командлета и объявление класса .NET, который реализует командлет.</span><span class="sxs-lookup"><span data-stu-id="93206-127">The first step in cmdlet creation is always naming the cmdlet and declaring the .NET class that implements the cmdlet.</span></span> <span data-ttu-id="93206-128">Для этого командлета используется жизненным циклом команду «Stop», поскольку командлет останавливает системные процессы.</span><span class="sxs-lookup"><span data-stu-id="93206-128">For this cmdlet, the life-cycle verb "Stop" is used because the cmdlet stops system processes.</span></span> <span data-ttu-id="93206-129">Имя существительное «Proc» используется в том случае, так как командлет работает по процессам.</span><span class="sxs-lookup"><span data-stu-id="93206-129">The noun name "Proc" is used because the cmdlet works on processes.</span></span> <span data-ttu-id="93206-130">В приведенном ниже объявлении Обратите внимание, что имя командлета глагол и существительное, отражаются в имени класса cmdlet.</span><span class="sxs-lookup"><span data-stu-id="93206-130">In the declaration below, note that the cmdlet verb and noun name are reflected in the name of the cmdlet class.</span></span>

> [!NOTE]
> <span data-ttu-id="93206-131">Дополнительные сведения о командлет утвержденных глаголов, см. в разделе [имен команд командлет](./approved-verbs-for-windows-powershell-commands.md).</span><span class="sxs-lookup"><span data-stu-id="93206-131">For more information about approved cmdlet verb names, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="93206-132">Следующий код является определение класса для этого командлета Stop-Proc.</span><span class="sxs-lookup"><span data-stu-id="93206-132">The following code is the class definition for this Stop-Proc cmdlet.</span></span>

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

## <a name="declaring-the-parameters-of-the-cmdlet"></a><span data-ttu-id="93206-133">Объявление параметров командлета</span><span class="sxs-lookup"><span data-stu-id="93206-133">Declaring the Parameters of the Cmdlet</span></span>

<span data-ttu-id="93206-134">Этот командлет определяет три параметра, используется в качестве входных данных командлету (эти параметры также определяют наборы параметров), а также `Force` параметр, который управляет действие командлета и `PassThru` параметр, который определяет, отправляет ли командлет выходной объект по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="93206-134">This cmdlet defines three parameters needed as input to the cmdlet (these parameters also define the parameter sets), as well as a `Force` parameter that manages what the cmdlet does and a `PassThru` parameter that determines whether the cmdlet sends an output object through the pipeline.</span></span> <span data-ttu-id="93206-135">По умолчанию этот командлет не передать объект по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="93206-135">By default, this cmdlet does not pass an object through the pipeline.</span></span> <span data-ttu-id="93206-136">Дополнительные сведения об этих двух последних параметрах см. в разделе [Создание командлет, который изменяет система](./creating-a-cmdlet-that-modifies-the-system.md).</span><span class="sxs-lookup"><span data-stu-id="93206-136">For more information about these last two parameters, see [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md).</span></span>

### <a name="declaring-the-name-parameter"></a><span data-ttu-id="93206-137">Объявление параметра Name</span><span class="sxs-lookup"><span data-stu-id="93206-137">Declaring the Name Parameter</span></span>

<span data-ttu-id="93206-138">Данный входной параметр позволяет пользователю указать имена процессов нужно остановить.</span><span class="sxs-lookup"><span data-stu-id="93206-138">This input parameter allows the user to specify the names of the processes to be stopped.</span></span> <span data-ttu-id="93206-139">Обратите внимание, что `ParameterSetName` атрибута ключевое слово [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) атрибут задает `ProcessName` набор параметров для этого параметра.</span><span class="sxs-lookup"><span data-stu-id="93206-139">Note that the `ParameterSetName` attribute keyword of the [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute specifies the `ProcessName` parameter set for this parameter.</span></span>

[!code-csharp[StopProcessSample04.cs](../../powershell-sdk-samples/SDK-2.0/csharp/StopProcessSample04/StopProcessSample04.cs#L44-L58 "StopProcessSample04.cs")]

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

<span data-ttu-id="93206-140">Обратите внимание, что этому параметру присваивается псевдоним «ProcessName».</span><span class="sxs-lookup"><span data-stu-id="93206-140">Note also that the alias "ProcessName" is given to this parameter.</span></span>

### <a name="declaring-the-id-parameter"></a><span data-ttu-id="93206-141">Объявление параметра Id</span><span class="sxs-lookup"><span data-stu-id="93206-141">Declaring the Id Parameter</span></span>

<span data-ttu-id="93206-142">Данный входной параметр позволяет пользователю указать идентификаторы процессов нужно остановить.</span><span class="sxs-lookup"><span data-stu-id="93206-142">This input parameter allows the user to specify the identifiers of the processes to be stopped.</span></span> <span data-ttu-id="93206-143">Обратите внимание, что `ParameterSetName` атрибута ключевое слово [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) атрибут задает `ProcessId` набор параметров.</span><span class="sxs-lookup"><span data-stu-id="93206-143">Note that the `ParameterSetName` attribute keyword of the [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute specifies the `ProcessId` parameter set.</span></span>

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

<span data-ttu-id="93206-144">Обратите внимание, что этому параметру присваивается псевдоним «ProcessId».</span><span class="sxs-lookup"><span data-stu-id="93206-144">Note also that the alias "ProcessId" is given to this parameter.</span></span>

### <a name="declaring-the-inputobject-parameter"></a><span data-ttu-id="93206-145">Объявление параметра InputObject</span><span class="sxs-lookup"><span data-stu-id="93206-145">Declaring the InputObject Parameter</span></span>

<span data-ttu-id="93206-146">Данный входной параметр позволяет пользователю указать входной объект, содержащий сведения о процессах, которые нужно остановить.</span><span class="sxs-lookup"><span data-stu-id="93206-146">This input parameter allows the user to specify an input object that contains information about the processes to be stopped.</span></span> <span data-ttu-id="93206-147">Обратите внимание, что `ParameterSetName` атрибута ключевое слово [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) атрибут задает `InputObject` набор параметров для этого параметра.</span><span class="sxs-lookup"><span data-stu-id="93206-147">Note that the `ParameterSetName` attribute keyword of the [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute specifies the `InputObject` parameter set for this parameter.</span></span>

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

<span data-ttu-id="93206-148">Обратите внимание, что этот параметр не имеет псевдонима.</span><span class="sxs-lookup"><span data-stu-id="93206-148">Note also that this parameter has no alias.</span></span>

### <a name="declaring-parameters-in-multiple-parameter-sets"></a><span data-ttu-id="93206-149">Объявление параметров в несколько наборов параметров</span><span class="sxs-lookup"><span data-stu-id="93206-149">Declaring Parameters in Multiple Parameter Sets</span></span>

<span data-ttu-id="93206-150">Несмотря на то, что должен быть уникальный параметр для каждого набора параметров, параметры могут принадлежать к более чем одним набором параметров.</span><span class="sxs-lookup"><span data-stu-id="93206-150">Although there must be a unique parameter for each parameter set, parameters can belong to more than one parameter set.</span></span> <span data-ttu-id="93206-151">В таких случаях присвойте общий параметр [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) объявление атрибута для каждого параметра, которому принадлежит.</span><span class="sxs-lookup"><span data-stu-id="93206-151">In these cases, give the shared parameter a [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute declaration for each set to which that the parameter belongs.</span></span> <span data-ttu-id="93206-152">Если параметр является во всех наборах параметров, у вас один раз объявить атрибут parameter и не обязательно должны указать имя набора параметров.</span><span class="sxs-lookup"><span data-stu-id="93206-152">If a parameter is in all parameter sets, you only have to declare the parameter attribute once and do not need to specify the parameter set name.</span></span>

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="93206-153">Переопределив метод обработки входных данных</span><span class="sxs-lookup"><span data-stu-id="93206-153">Overriding an Input Processing Method</span></span>

<span data-ttu-id="93206-154">Каждый командлет необходимо переопределить метод обработки входных данных, чаще всего это будет [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) метод.</span><span class="sxs-lookup"><span data-stu-id="93206-154">Every cmdlet must override an input processing method, most often this will be the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span> <span data-ttu-id="93206-155">В этом командлете [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) метод переопределяется, так что этот командлет может обработать любое количество процессов.</span><span class="sxs-lookup"><span data-stu-id="93206-155">In this cmdlet, the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method is overridden so that the cmdlet can process any number of processes.</span></span> <span data-ttu-id="93206-156">Он содержит инструкцию Select, вызывает другой метод на основе какой набор параметров пользователя с указанными.</span><span class="sxs-lookup"><span data-stu-id="93206-156">It contains a Select statement that calls a different method based on which parameter set the user has specified.</span></span>

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

<span data-ttu-id="93206-157">Вспомогательные методы, вызываемые оператором Select здесь не описываются, но вы увидите их реализации в полный пример кода в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="93206-157">The Helper methods called by the Select statement are not described here, but you can see their implementation in the complete code sample in the next section.</span></span>

## <a name="code-sample"></a><span data-ttu-id="93206-158">Пример кода</span><span class="sxs-lookup"><span data-stu-id="93206-158">Code Sample</span></span>

<span data-ttu-id="93206-159">Для полной C# пример кода, см. в разделе [пример StopProcessSample04](./stopprocesssample04-sample.md).</span><span class="sxs-lookup"><span data-stu-id="93206-159">For the complete C# sample code, see [StopProcessSample04 Sample](./stopprocesssample04-sample.md).</span></span>

## <a name="defining-object-types-and-formatting"></a><span data-ttu-id="93206-160">Определение типов объектов и форматирование</span><span class="sxs-lookup"><span data-stu-id="93206-160">Defining Object Types and Formatting</span></span>

<span data-ttu-id="93206-161">Windows PowerShell передает данные между командлетами, используя объекты .NET.</span><span class="sxs-lookup"><span data-stu-id="93206-161">Windows PowerShell passes information between cmdlets using .NET objects.</span></span> <span data-ttu-id="93206-162">Следовательно командлета может потребоваться определить его собственного типа, или командлет может потребоваться расширить существующий тип предоставляемые другому командлету.</span><span class="sxs-lookup"><span data-stu-id="93206-162">Consequently, a cmdlet might need to define its own type, or the cmdlet might need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="93206-163">Дополнительные сведения о определение новых типов или расширения существующих типов, см. в разделе [расширение типов объектов и форматирование](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351).</span><span class="sxs-lookup"><span data-stu-id="93206-163">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="93206-164">Создание командлета</span><span class="sxs-lookup"><span data-stu-id="93206-164">Building the Cmdlet</span></span>

<span data-ttu-id="93206-165">После реализации командлета, необходимо зарегистрировать его с помощью Windows PowerShell через оснастку Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="93206-165">After implementing a cmdlet, you must register it with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="93206-166">Дополнительные сведения о регистрации командлетов см. в разделе [как регистрация командлетов, поставщиков и ведущих приложений](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).</span><span class="sxs-lookup"><span data-stu-id="93206-166">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="93206-167">Тестирование командлет</span><span class="sxs-lookup"><span data-stu-id="93206-167">Testing the Cmdlet</span></span>

<span data-ttu-id="93206-168">Если командлет зарегистрирован с помощью Windows PowerShell, проверьте его, запустив его в командной строке.</span><span class="sxs-lookup"><span data-stu-id="93206-168">When your cmdlet has been registered with Windows PowerShell, test it by running it on the command line.</span></span> <span data-ttu-id="93206-169">Ниже приведены некоторые тесты, которые показывают, каким образом `ProcessId` и `InputObject` параметры могут использоваться для проверки их наборы параметров для остановки процесса.</span><span class="sxs-lookup"><span data-stu-id="93206-169">Here are some tests that show how the `ProcessId` and `InputObject` parameters can be used to test their parameter sets to stop a process.</span></span>

- <span data-ttu-id="93206-170">С помощью Windows PowerShell к работе, выполните командлет Stop-Proc с `ProcessId` задать параметр для остановки процесса на основе его идентификатора.</span><span class="sxs-lookup"><span data-stu-id="93206-170">With Windows PowerShell started, run the Stop-Proc cmdlet with the `ProcessId` parameter set to stop a process based on its identifier.</span></span> <span data-ttu-id="93206-171">В этом случае используется командлет `ProcessId` задать параметр для остановки процесса.</span><span class="sxs-lookup"><span data-stu-id="93206-171">In this case, the cmdlet is using the `ProcessId` parameter set to stop the process.</span></span>

    ```
    PS> stop-proc -Id 444
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (444)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    ```

- <span data-ttu-id="93206-172">С помощью Windows PowerShell к работе, выполните командлет Stop-Proc с `InputObject` параметру для остановки процессов, в блокноте объект, возвращенный командлетом `Get-Process` команды.</span><span class="sxs-lookup"><span data-stu-id="93206-172">With Windows PowerShell started, run the Stop-Proc cmdlet with the `InputObject` parameter set to stop processes on the Notepad object retrieved by the `Get-Process` command.</span></span>

    ```
    PS> get-process notepad | stop-proc
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (444)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

## <a name="see-also"></a><span data-ttu-id="93206-173">См. также</span><span class="sxs-lookup"><span data-stu-id="93206-173">See Also</span></span>

[<span data-ttu-id="93206-174">Создание командлета, который изменяет системы</span><span class="sxs-lookup"><span data-stu-id="93206-174">Creating a Cmdlet that Modifies the System</span></span>](./creating-a-cmdlet-that-modifies-the-system.md)

[<span data-ttu-id="93206-175">Как создать командлет Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="93206-175">How to Create a Windows PowerShell Cmdlet</span></span>](http://msdn.microsoft.com/en-us/0d721742-c849-4d0d-964f-78ddd9cd258c)

[<span data-ttu-id="93206-176">Расширение типов объектов и форматирование</span><span class="sxs-lookup"><span data-stu-id="93206-176">Extending Object Types and Formatting</span></span>](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[<span data-ttu-id="93206-177">Регистрация командлетов, поставщиков и ведущих приложений</span><span class="sxs-lookup"><span data-stu-id="93206-177">How to Register Cmdlets, Providers, and Host Applications</span></span>](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[<span data-ttu-id="93206-178">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="93206-178">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
