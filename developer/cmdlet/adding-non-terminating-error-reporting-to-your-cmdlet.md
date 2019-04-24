---
title: Добавление устранимую командлета отчетов об ошибках | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2a1531a-a92a-4606-9d54-c5df80d34f33
caps.latest.revision: 8
ms.openlocfilehash: 3741982f81efa04d8fe7ab448fba5f2fdf4b0c01
ms.sourcegitcommit: f4bd4e116e22c8b5bfcb61680a7c42e58b4da93e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2019
ms.locfileid: "59984244"
---
# <a name="adding-non-terminating-error-reporting-to-your-cmdlet"></a><span data-ttu-id="c91d6-102">Добавление сообщения о непрерывающей ошибке в командлет</span><span class="sxs-lookup"><span data-stu-id="c91d6-102">Adding Non-Terminating Error Reporting to Your Cmdlet</span></span>

<span data-ttu-id="c91d6-103">Командлеты можно сообщить устранимые ошибки путем вызова [System.Management.Automation.Cmdlet.WriteError][] метода и продолжить работу на текущий входной объект или на Дополнительные Входящие конвейер объектов.</span><span class="sxs-lookup"><span data-stu-id="c91d6-103">Cmdlets can report nonterminating errors by calling the [System.Management.Automation.Cmdlet.WriteError][] method and still continue to operate on the current input object or on further incoming pipeline objects.</span></span>
<span data-ttu-id="c91d6-104">В этом разделе объясняется, как создать командлет, который сообщает устранимые ошибки из его методов обработки ввода.</span><span class="sxs-lookup"><span data-stu-id="c91d6-104">This section explains how to create a cmdlet that reports nonterminating errors from its input processing methods.</span></span>

<span data-ttu-id="c91d6-105">Устранимые ошибки (а также прерывающие ошибки), командлет необходимо передать [System.Management.Automation.ErrorRecord][] объект, определяющий ошибку.</span><span class="sxs-lookup"><span data-stu-id="c91d6-105">For nonterminating errors (as well as terminating errors), the cmdlet must pass an [System.Management.Automation.ErrorRecord][] object identifying the error.</span></span>
<span data-ttu-id="c91d6-106">Каждая ошибка запись идентифицируется по уникальной строки, называемой «идентификатор ошибка».</span><span class="sxs-lookup"><span data-stu-id="c91d6-106">Each error record is identified by a unique string called the "error identifier".</span></span>
<span data-ttu-id="c91d6-107">Кроме идентификатора категории каждой ошибки определяется константы, определенные в [System.Management.Automation.ErrorCategory][] перечисления.</span><span class="sxs-lookup"><span data-stu-id="c91d6-107">In addition to the identifier, the category of each error is specified by constants defined by a [System.Management.Automation.ErrorCategory][] enumeration.</span></span>
<span data-ttu-id="c91d6-108">Пользователь может просмотреть ошибки, на основе их категории, установив `$ErrorView` переменной «CategoryView».</span><span class="sxs-lookup"><span data-stu-id="c91d6-108">The user can view errors based on their category by setting the `$ErrorView` variable to "CategoryView".</span></span>

<span data-ttu-id="c91d6-109">Дополнительные сведения о записи об ошибках, см. в разделе [записи об ошибках Windows PowerShell](./windows-powershell-error-records.md).</span><span class="sxs-lookup"><span data-stu-id="c91d6-109">For more information about error records, see [Windows PowerShell Error Records](./windows-powershell-error-records.md).</span></span>

## <a name="defining-the-cmdlet"></a><span data-ttu-id="c91d6-110">Определение командлета</span><span class="sxs-lookup"><span data-stu-id="c91d6-110">Defining the Cmdlet</span></span>

<span data-ttu-id="c91d6-111">Первым шагом в создании командлет всегда присвоение имени командлета и объявление класса .NET, который реализует командлет.</span><span class="sxs-lookup"><span data-stu-id="c91d6-111">The first step in cmdlet creation is always naming the cmdlet and declaring the .NET class that implements the cmdlet.</span></span>
<span data-ttu-id="c91d6-112">Этот командлет извлекает сведения о процессе, чтобы имя команды, выбираем «Get».</span><span class="sxs-lookup"><span data-stu-id="c91d6-112">This cmdlet retrieves process information, so the verb name chosen here is "Get".</span></span>
<span data-ttu-id="c91d6-113">(Почти любого вида командлет, который поддерживает получение сведений о может обрабатывать входные данные командной строки). Дополнительные сведения о командлет утвержденные глаголы, см. в разделе [имен команд командлет](approved-verbs-for-windows-powershell-commands.md).</span><span class="sxs-lookup"><span data-stu-id="c91d6-113">(Almost any sort of cmdlet that is capable of retrieving information can process command-line input.) For more information about approved cmdlet verbs, see [Cmdlet Verb Names](approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="c91d6-114">Ниже приведено определение для этого командлета Get-Proc.</span><span class="sxs-lookup"><span data-stu-id="c91d6-114">The following is the definition for this Get-Proc cmdlet.</span></span>
<span data-ttu-id="c91d6-115">Сведения из этого определения приведены [Создание свой первый командлет](creating-a-cmdlet-without-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="c91d6-115">Details of this definition are given in [Creating Your First Cmdlet](creating-a-cmdlet-without-parameters.md).</span></span>

```csharp
[Cmdlet(VerbsCommon.Get, "proc")]
public class GetProcCommand: Cmdlet
```

```vb
<Cmdlet(VerbsCommon.Get, "Proc")> _
Public Class GetProcCommand
    Inherits Cmdlet
```

## <a name="defining-parameters"></a><span data-ttu-id="c91d6-116">Определение параметров</span><span class="sxs-lookup"><span data-stu-id="c91d6-116">Defining Parameters</span></span>

<span data-ttu-id="c91d6-117">При необходимости в командлете необходимо определить параметры для обработки входных данных.</span><span class="sxs-lookup"><span data-stu-id="c91d6-117">If necessary, your cmdlet must define parameters for processing input.</span></span>
<span data-ttu-id="c91d6-118">Этот командлет Get-Proc определяет **имя** параметра, как описано в разделе [Добавление параметров командной строки этого процесса входа](adding-parameters-that-process-command-line-input.md).</span><span class="sxs-lookup"><span data-stu-id="c91d6-118">This Get-Proc cmdlet defines a **Name** parameter as described in [Adding Parameters that Process Command-Line Input](adding-parameters-that-process-command-line-input.md).</span></span>

<span data-ttu-id="c91d6-119">Ниже приведено объявление параметра для **имя** из параметров командлета Get-Proc.</span><span class="sxs-lookup"><span data-stu-id="c91d6-119">Here is the parameter declaration for the **Name** parameter of this Get-Proc cmdlet.</span></span>

```csharp
[Parameter(
           Position = 0,
           ValueFromPipeline = true,
           ValueFromPipelineByPropertyName = true
)]
[ValidateNotNullOrEmpty]
public string[] Name
{
  get { return processNames; }
  set { processNames = value; }
}
private string[] processNames;
```

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

## <a name="overriding-input-processing-methods"></a><span data-ttu-id="c91d6-120">Переопределяя методы обработки ввода</span><span class="sxs-lookup"><span data-stu-id="c91d6-120">Overriding Input Processing Methods</span></span>

<span data-ttu-id="c91d6-121">Все командлеты необходимо переопределить хотя бы один из методов, предоставляемых обработки ввода [System.Management.Automation.Cmdlet][] класса.</span><span class="sxs-lookup"><span data-stu-id="c91d6-121">All cmdlets must override at least one of the input processing methods provided by the [System.Management.Automation.Cmdlet][] class.</span></span>
<span data-ttu-id="c91d6-122">Эти методы описаны в [Создание свой первый командлет](creating-a-cmdlet-without-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="c91d6-122">These methods are discussed in [Creating Your First Cmdlet](creating-a-cmdlet-without-parameters.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c91d6-123">Командлет для независимой обработки каждой записи.</span><span class="sxs-lookup"><span data-stu-id="c91d6-123">Your cmdlet should handle each record as independently as possible.</span></span>

<span data-ttu-id="c91d6-124">Этот командлет Get-Proc переопределяет [System.Management.Automation.Cmdlet.ProcessRecord][] метод для обработки **имя** параметр для входных данных, предоставленных пользователю или сценарий.</span><span class="sxs-lookup"><span data-stu-id="c91d6-124">This Get-Proc cmdlet overrides the [System.Management.Automation.Cmdlet.ProcessRecord][] method to handle the **Name** parameter for input provided by the user or a script.</span></span>
<span data-ttu-id="c91d6-125">Этот метод будет получения процессов для каждого имени запрошенного процесса и всех процессов, если имя не указано.</span><span class="sxs-lookup"><span data-stu-id="c91d6-125">This method will get the processes for each requested process name or all processes if no name is provided.</span></span>
<span data-ttu-id="c91d6-126">Сведения о это переопределение приведены в [Создание свой первый командлет](creating-a-cmdlet-without-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="c91d6-126">Details of this override are given in [Creating Your First Cmdlet](creating-a-cmdlet-without-parameters.md).</span></span>

### <a name="things-to-remember-when-reporting-errors"></a><span data-ttu-id="c91d6-127">О чем следует помнить при сообщении об ошибках</span><span class="sxs-lookup"><span data-stu-id="c91d6-127">Things to Remember When Reporting Errors</span></span>

<span data-ttu-id="c91d6-128">[System.Management.Automation.ErrorRecord][] объекта, что командлет передает при записи ошибки требует исключение по своей сути.</span><span class="sxs-lookup"><span data-stu-id="c91d6-128">The [System.Management.Automation.ErrorRecord][] object that the cmdlet passes when writing an error requires an exception at its core.</span></span>
<span data-ttu-id="c91d6-129">Следуйте рекомендациям .NET, при определении исключение для использования.</span><span class="sxs-lookup"><span data-stu-id="c91d6-129">Follow the .NET guidelines when determining the exception to use.</span></span>
<span data-ttu-id="c91d6-130">По сути Если ошибка является семантически так же, как существующие исключения, этот командлет следует использовать, или являются производными от этого исключения.</span><span class="sxs-lookup"><span data-stu-id="c91d6-130">Basically, if the error is semantically the same as an existing exception, the cmdlet should use or derive from that exception.</span></span>
<span data-ttu-id="c91d6-131">В противном случае он должен быть производным новое исключение, либо иерархия исключений непосредственно из [System.Exception][] класса.</span><span class="sxs-lookup"><span data-stu-id="c91d6-131">Otherwise, it should derive a new exception or exception hierarchy directly from the [System.Exception][] class.</span></span>

<span data-ttu-id="c91d6-132">При создании ошибки идентификаторы (через свойство FullyQualifiedErrorId класса ErrorRecord) Имейте в виду следующее.</span><span class="sxs-lookup"><span data-stu-id="c91d6-132">When creating error identifiers (accessed through the FullyQualifiedErrorId property of the ErrorRecord class) keep the following in mind.</span></span>

- <span data-ttu-id="c91d6-133">Использование строк, которые предназначены для диагностики, чтобы при проверке полный идентификатор можно определить, какие ошибки — и там, где ошибка возникла.</span><span class="sxs-lookup"><span data-stu-id="c91d6-133">Use strings that are targeted for diagnostic purposes so that when inspecting the fully qualified identifier you can determine what the error is and where the error came from.</span></span>

- <span data-ttu-id="c91d6-134">Идентификатор корректность полное ошибка может выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="c91d6-134">A well formed fully qualified error identifier might be as follows.</span></span>

`CommandNotFoundException,Microsoft.PowerShell.Commands.GetCommandCommand`

<span data-ttu-id="c91d6-135">Обратите внимание на то, что в предыдущем примере, код ошибки (первый токен) обозначает ошибку, а оставшиеся части показывает происхождения ошибки.</span><span class="sxs-lookup"><span data-stu-id="c91d6-135">Notice that in the previous example, the error identifier (the first token) designates what the error is and the remaining part indicates where the error came from.</span></span>

- <span data-ttu-id="c91d6-136">Для более сложных сценариев код ошибки может быть маркер точки с запятыми, который может быть проанализирован для проверки.</span><span class="sxs-lookup"><span data-stu-id="c91d6-136">For more complex scenarios, the error identifier can be a dot separated token that can be parsed on inspection.</span></span>
  <span data-ttu-id="c91d6-137">Это позволяет слишком ветви на тех частях идентификатор ошибки, а также идентификатор и ошибка категорию ошибки.</span><span class="sxs-lookup"><span data-stu-id="c91d6-137">This allows you too branch on the parts of the error identifier as well as the error identifier and error category.</span></span>

<span data-ttu-id="c91d6-138">Командлет следует назначить конкретной ошибке идентификаторы разных путей кода.</span><span class="sxs-lookup"><span data-stu-id="c91d6-138">The cmdlet should assign specific error identifiers to different code paths.</span></span>
<span data-ttu-id="c91d6-139">Учитывайте следующие сведения для назначения идентификаторов, ошибка:</span><span class="sxs-lookup"><span data-stu-id="c91d6-139">Keep the following information in mind for assignment of error identifiers:</span></span>

- <span data-ttu-id="c91d6-140">Идентификатор ошибки должны оставаться неизменным на протяжении всего жизненного цикла командлета.</span><span class="sxs-lookup"><span data-stu-id="c91d6-140">An error identifier should remain constant throughout the cmdlet life cycle.</span></span>
  <span data-ttu-id="c91d6-141">Не изменяет семантику идентификатора ошибка между версиями командлет.</span><span class="sxs-lookup"><span data-stu-id="c91d6-141">Do not change the semantics of an error identifier between cmdlet versions.</span></span>

- <span data-ttu-id="c91d6-142">Используйте текст ошибки идентификатор, который соответствует кратко сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="c91d6-142">Use text for an error identifier that tersely corresponds to the error being reported.</span></span>
  <span data-ttu-id="c91d6-143">Не используйте пробелы или знаки препинания.</span><span class="sxs-lookup"><span data-stu-id="c91d6-143">Do not use white space or punctuation.</span></span>

- <span data-ttu-id="c91d6-144">У командлета создавать только идентификаторы ошибки, воспроизводимый.</span><span class="sxs-lookup"><span data-stu-id="c91d6-144">Have your cmdlet generate only error identifiers that are reproducible.</span></span>
  <span data-ttu-id="c91d6-145">Например она не должна создавать идентификатор, который включает идентификатор процесса.</span><span class="sxs-lookup"><span data-stu-id="c91d6-145">For example, it should not generate an identifier that includes a process identifier.</span></span>
  <span data-ttu-id="c91d6-146">Ошибка идентификаторы полезны пользователю только в том случае, если они соответствуют идентификаторы, которые будут видны другим пользователям, столкнувшимся с этой проблемы.</span><span class="sxs-lookup"><span data-stu-id="c91d6-146">Error identifiers are useful to a user only when they correspond to identifiers that are seen by other users experiencing the same problem.</span></span>

<span data-ttu-id="c91d6-147">Необработанные исключения не перехватываются PowerShell в следующих ситуациях:</span><span class="sxs-lookup"><span data-stu-id="c91d6-147">Unhandled exceptions are not caught by PowerShell in the following conditions:</span></span>

- <span data-ttu-id="c91d6-148">Если командлет создает новый поток и код, выполняемый в том, что поток вызывает необработанное исключение, не перехватывает ошибку и завершает процесс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c91d6-148">If a cmdlet creates a new thread and code running in that thread throws an unhandled exception, PowerShell will not catch the error and will terminate the process.</span></span>

- <span data-ttu-id="c91d6-149">Если объект имеет код в его деструктор или метод Dispose, который приводит к возникновению необработанного исключения, не перехватывает ошибку и завершает процесс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c91d6-149">If an object has code in its destructor or Dispose methods that causes an unhandled exception, PowerShell will not catch the error and will terminate the process.</span></span>

## <a name="reporting-nonterminating-errors"></a><span data-ttu-id="c91d6-150">Устранимые ошибки</span><span class="sxs-lookup"><span data-stu-id="c91d6-150">Reporting Nonterminating Errors</span></span>

<span data-ttu-id="c91d6-151">Один из методов обработки ввода, может сообщать устранимые ошибки в поток вывода с помощью [System.Management.Automation.Cmdlet.WriteError][] метод.</span><span class="sxs-lookup"><span data-stu-id="c91d6-151">Any one of the input processing methods can report a nonterminating error to the output stream using the [System.Management.Automation.Cmdlet.WriteError][] method.</span></span>

<span data-ttu-id="c91d6-152">Ниже приведен пример кода из этого демонстрируется вызов командлета Get-Proc [System.Management.Automation.Cmdlet.WriteError][] из в переопределенной [System.Management.Automation.Cmdlet.ProcessRecord][] метод.</span><span class="sxs-lookup"><span data-stu-id="c91d6-152">Here is a code example from this Get-Proc cmdlet that illustrates the call to [System.Management.Automation.Cmdlet.WriteError][] from within the override of the [System.Management.Automation.Cmdlet.ProcessRecord][] method.</span></span>
<span data-ttu-id="c91d6-153">В этом случае вызов выполняется, если командлет не удается найти процесс для идентификатора указанного процесса.</span><span class="sxs-lookup"><span data-stu-id="c91d6-153">In this case, the call is made if the cmdlet cannot find a process for a specified process identifier.</span></span>

```csharp
protected override void ProcessRecord()
{
  // If no name parameter passed to cmdlet, get all processes.
  if (processNames == null)
  {
    WriteObject(Process.GetProcesses(), true);
  }
    else
    {
      // If a name parameter is passed to cmdlet, get and write
      // the associated processes.
      // Write a nonterminating error for failure to retrieve
      // a process.
      foreach (string name in processNames)
      {
        Process[] processes;

        try
        {
          processes = Process.GetProcessesByName(name);
        }
        catch (InvalidOperationException ex)
        {
          WriteError(new ErrorRecord(
                     ex,
                     "NameNotFound",
                     ErrorCategory.InvalidOperation,
                     name));
          continue;
        }

        WriteObject(processes, true);
      } // foreach (...
    } // else
  }
```

### <a name="things-to-remember-about-writing-nonterminating-errors"></a><span data-ttu-id="c91d6-154">О чем следует помнить о написании устранимые ошибки</span><span class="sxs-lookup"><span data-stu-id="c91d6-154">Things to Remember About Writing Nonterminating Errors</span></span>

<span data-ttu-id="c91d6-155">Устранимые ошибки командлет необходимо создать идентификатор конкретной ошибки для каждого конкретного входного объекта.</span><span class="sxs-lookup"><span data-stu-id="c91d6-155">For a nonterminating error, the cmdlet must generate a specific error identifier for each specific input object.</span></span>

<span data-ttu-id="c91d6-156">Командлет часто необходимо изменить действие PowerShell, созданные устранимые ошибки.</span><span class="sxs-lookup"><span data-stu-id="c91d6-156">A cmdlet frequently needs to modify the PowerShell action produced by a nonterminating error.</span></span>
<span data-ttu-id="c91d6-157">Можно сделать путем определения `ErrorAction` и `ErrorVariable` параметров.</span><span class="sxs-lookup"><span data-stu-id="c91d6-157">It can do this by defining the `ErrorAction` and `ErrorVariable` parameters.</span></span>
<span data-ttu-id="c91d6-158">Если определение `ErrorAction` параметр, командлет представлены параметры пользователя [System.Management.Automation.ActionPreference][], можно также непосредственно влияют на действие, задав `$ErrorActionPreference` переменной.</span><span class="sxs-lookup"><span data-stu-id="c91d6-158">If defining the `ErrorAction` parameter, the cmdlet presents the user options [System.Management.Automation.ActionPreference][], you can also directly influence the action by setting the `$ErrorActionPreference` variable.</span></span>

<span data-ttu-id="c91d6-159">Командлет можно сохранить устранимые ошибки в переменной с помощью `ErrorVariable` параметр, который не зависит от параметра `ErrorAction`.</span><span class="sxs-lookup"><span data-stu-id="c91d6-159">The cmdlet can save nonterminating errors to a variable using the `ErrorVariable` parameter, which is not affected by the setting of `ErrorAction`.</span></span>
<span data-ttu-id="c91d6-160">Сбои можно добавить в существующую переменную ошибки, добавив знак плюс (+) в начале имени переменной.</span><span class="sxs-lookup"><span data-stu-id="c91d6-160">Failures can be appended to an existing error variable by adding a plus sign (+) to the front of the variable name.</span></span>

## <a name="code-sample"></a><span data-ttu-id="c91d6-161">Пример кода</span><span class="sxs-lookup"><span data-stu-id="c91d6-161">Code Sample</span></span>

<span data-ttu-id="c91d6-162">Для полной C# пример кода, см. в разделе [пример GetProcessSample04](./getprocesssample04-sample.md).</span><span class="sxs-lookup"><span data-stu-id="c91d6-162">For the complete C# sample code, see [GetProcessSample04 Sample](./getprocesssample04-sample.md).</span></span>

## <a name="define-object-types-and-formatting"></a><span data-ttu-id="c91d6-163">Определение типов объектов и форматирования</span><span class="sxs-lookup"><span data-stu-id="c91d6-163">Define Object Types and Formatting</span></span>

<span data-ttu-id="c91d6-164">PowerShell передает данные между командлетами, используя объекты .NET.</span><span class="sxs-lookup"><span data-stu-id="c91d6-164">PowerShell passes information between cmdlets using .NET objects.</span></span>
<span data-ttu-id="c91d6-165">Следовательно командлета может потребоваться определить его собственного типа, или командлет может потребоваться расширить существующий тип предоставляемые другому командлету.</span><span class="sxs-lookup"><span data-stu-id="c91d6-165">Consequently, a cmdlet might need to define its own type, or the cmdlet might need to extend an existing type provided by another cmdlet.</span></span>
<span data-ttu-id="c91d6-166">Дополнительные сведения о определение новых типов или расширения существующих типов, см. в разделе [расширение типов объектов и форматирование](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351).</span><span class="sxs-lookup"><span data-stu-id="c91d6-166">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="c91d6-167">Создание командлета</span><span class="sxs-lookup"><span data-stu-id="c91d6-167">Building the Cmdlet</span></span>

<span data-ttu-id="c91d6-168">После реализации командлета, необходимо зарегистрировать его с помощью Windows PowerShell через оснастку Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c91d6-168">After implementing a cmdlet, you must register it with Windows PowerShell through a Windows PowerShell snap-in.</span></span>
<span data-ttu-id="c91d6-169">Дополнительные сведения о регистрации командлетов см. в разделе [как регистрация командлетов, поставщиков и ведущих приложений](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).</span><span class="sxs-lookup"><span data-stu-id="c91d6-169">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="c91d6-170">Тестирование командлет</span><span class="sxs-lookup"><span data-stu-id="c91d6-170">Testing the Cmdlet</span></span>

<span data-ttu-id="c91d6-171">При командлета был зарегистрирован с помощью PowerShell, его можно проверить, запустив его в командной строке.</span><span class="sxs-lookup"><span data-stu-id="c91d6-171">When your cmdlet has been registered with PowerShell, you can test it by running it on the command line.</span></span>
<span data-ttu-id="c91d6-172">Давайте протестируем командлету Get-Proc пример см. в разделе ли она сообщает об ошибке:</span><span class="sxs-lookup"><span data-stu-id="c91d6-172">Let's test the sample Get-Proc cmdlet to see whether it reports an error:</span></span>

- <span data-ttu-id="c91d6-173">Запустите PowerShell и используйте командлет Get-Proc для получения процессов, с именем «TEST».</span><span class="sxs-lookup"><span data-stu-id="c91d6-173">Start PowerShell, and use the Get-Proc cmdlet to retrieve the processes named "TEST".</span></span>

    ```powershell
    PS> get-proc -name test
    ```

<span data-ttu-id="c91d6-174">Появляется следующий результат.</span><span class="sxs-lookup"><span data-stu-id="c91d6-174">The following output appears.</span></span>

    ```
    get-proc : Operation is not valid due to the current state of the object.
    At line:1 char:9
    + get-proc  <<<< -name test
    ```

## <a name="see-also"></a><span data-ttu-id="c91d6-175">См. также</span><span class="sxs-lookup"><span data-stu-id="c91d6-175">See Also</span></span>

[<span data-ttu-id="c91d6-176">Добавление параметров конвейера обработки входных данных</span><span class="sxs-lookup"><span data-stu-id="c91d6-176">Adding Parameters that Process Pipeline Input</span></span>](./adding-parameters-that-process-pipeline-input.md)

[<span data-ttu-id="c91d6-177">Добавление параметров, которые обрабатывают данные в командной строке</span><span class="sxs-lookup"><span data-stu-id="c91d6-177">Adding Parameters that Process Command-Line Input</span></span>](./adding-parameters-that-process-command-line-input.md)

[<span data-ttu-id="c91d6-178">Создайте свой первый командлет</span><span class="sxs-lookup"><span data-stu-id="c91d6-178">Creating Your First Cmdlet</span></span>](./creating-a-cmdlet-without-parameters.md)

[<span data-ttu-id="c91d6-179">Расширение типов объектов и форматирование</span><span class="sxs-lookup"><span data-stu-id="c91d6-179">Extending Object Types and Formatting</span></span>](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[<span data-ttu-id="c91d6-180">Регистрация командлетов, поставщиков и ведущих приложений</span><span class="sxs-lookup"><span data-stu-id="c91d6-180">How to Register Cmdlets, Providers, and Host Applications</span></span>](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[<span data-ttu-id="c91d6-181">Справочник по Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c91d6-181">Windows PowerShell Reference</span></span>](../windows-powershell-reference.md)

[<span data-ttu-id="c91d6-182">Примеры командлетов</span><span class="sxs-lookup"><span data-stu-id="c91d6-182">Cmdlet Samples</span></span>](./cmdlet-samples.md)

[System.Exception]: /dotnet/api/System.Exception
[System.Management.Automation.ActionPreference]: /dotnet/api/System.Management.Automation.ActionPreference
[System.Management.Automation.Cmdlet.ProcessRecord]: /dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord
[System.Management.Automation.Cmdlet.WriteError]: /dotnet/api/System.Management.Automation.Cmdlet.WriteError
[System.Management.Automation.Cmdlet]: /dotnet/api/System.Management.Automation.Cmdlet
[System.Management.Automation.ErrorCategory]: /dotnet/api/System.Management.Automation.ErrorCategory
[System.Management.Automation.ErrorRecord]: /dotnet/api/System.Management.Automation.ErrorRecord
