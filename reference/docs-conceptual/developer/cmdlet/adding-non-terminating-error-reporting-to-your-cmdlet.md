---
title: Добавление в командлет незавершающего сообщения об ошибках | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 6421d510f3701c12807568ad8786459123e80223
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784594"
---
# <a name="adding-non-terminating-error-reporting-to-your-cmdlet"></a><span data-ttu-id="ed2ea-102">Добавление сообщения о непрерывающей ошибке в командлет</span><span class="sxs-lookup"><span data-stu-id="ed2ea-102">Adding Non-Terminating Error Reporting to Your Cmdlet</span></span>

<span data-ttu-id="ed2ea-103">Командлеты могут сообщать о неустранимых ошибках, вызывая метод [System. Management. Automation. командлет. WriteError][] и продолжая работать с текущим входным объектом или с дальнейшими входящими объектами конвейера.</span><span class="sxs-lookup"><span data-stu-id="ed2ea-103">Cmdlets can report nonterminating errors by calling the [System.Management.Automation.Cmdlet.WriteError][] method and still continue to operate on the current input object or on further incoming pipeline objects.</span></span> <span data-ttu-id="ed2ea-104">В этом разделе объясняется, как создать командлет, сообщающий о неустранимых ошибках из своих методов обработки входных данных.</span><span class="sxs-lookup"><span data-stu-id="ed2ea-104">This section explains how to create a cmdlet that reports nonterminating errors from its input processing methods.</span></span>

<span data-ttu-id="ed2ea-105">Для неустранимых ошибок (а также для прерывания ошибок) командлет должен передать объект [System. Management. Automation. ерроррекорд][] , определяющий ошибку.</span><span class="sxs-lookup"><span data-stu-id="ed2ea-105">For nonterminating errors (as well as terminating errors), the cmdlet must pass an [System.Management.Automation.ErrorRecord][] object identifying the error.</span></span> <span data-ttu-id="ed2ea-106">Каждая запись об ошибке идентифицируется уникальной строкой с именем "Идентификатор ошибки".</span><span class="sxs-lookup"><span data-stu-id="ed2ea-106">Each error record is identified by a unique string called the "error identifier".</span></span> <span data-ttu-id="ed2ea-107">В дополнение к идентификатору Категория каждой ошибки задается константами, определенными перечислением [System. Management. Automation. ErrorCategory][] .</span><span class="sxs-lookup"><span data-stu-id="ed2ea-107">In addition to the identifier, the category of each error is specified by constants defined by a [System.Management.Automation.ErrorCategory][] enumeration.</span></span> <span data-ttu-id="ed2ea-108">Пользователь может просматривать ошибки на основе их категории, присвоив `$ErrorView` переменной значение "категоривиев".</span><span class="sxs-lookup"><span data-stu-id="ed2ea-108">The user can view errors based on their category by setting the `$ErrorView` variable to "CategoryView".</span></span>

<span data-ttu-id="ed2ea-109">Дополнительные сведения о записях об ошибках см. в статье [записи об ошибках Windows PowerShell](./windows-powershell-error-records.md).</span><span class="sxs-lookup"><span data-stu-id="ed2ea-109">For more information about error records, see [Windows PowerShell Error Records](./windows-powershell-error-records.md).</span></span>

## <a name="defining-the-cmdlet"></a><span data-ttu-id="ed2ea-110">Определение командлета</span><span class="sxs-lookup"><span data-stu-id="ed2ea-110">Defining the Cmdlet</span></span>

<span data-ttu-id="ed2ea-111">Первым шагом при создании командлета всегда является присвоение имени командлета и объявление класса .NET, реализующего командлет.</span><span class="sxs-lookup"><span data-stu-id="ed2ea-111">The first step in cmdlet creation is always naming the cmdlet and declaring the .NET class that implements the cmdlet.</span></span> <span data-ttu-id="ed2ea-112">Этот командлет извлекает сведения о процессе, поэтому выбранное здесь имя команды — Get.</span><span class="sxs-lookup"><span data-stu-id="ed2ea-112">This cmdlet retrieves process information, so the verb name chosen here is "Get".</span></span> <span data-ttu-id="ed2ea-113">(Практически любой командлет, который способен получить информацию, может обрабатывать входные данные командной строки.) Дополнительные сведения о утвержденных командах командлетов см. в разделе [имена глаголов командлетов](approved-verbs-for-windows-powershell-commands.md).</span><span class="sxs-lookup"><span data-stu-id="ed2ea-113">(Almost any sort of cmdlet that is capable of retrieving information can process command-line input.) For more information about approved cmdlet verbs, see [Cmdlet Verb Names](approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="ed2ea-114">Ниже приведено определение для этого `Get-Proc` командлета.</span><span class="sxs-lookup"><span data-stu-id="ed2ea-114">The following is the definition for this `Get-Proc` cmdlet.</span></span> <span data-ttu-id="ed2ea-115">Подробные сведения об этом определении приведены в [создании первого командлета](creating-a-cmdlet-without-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="ed2ea-115">Details of this definition are given in [Creating Your First Cmdlet](creating-a-cmdlet-without-parameters.md).</span></span>

```csharp
[Cmdlet(VerbsCommon.Get, "proc")]
public class GetProcCommand: Cmdlet
```

```vb
<Cmdlet(VerbsCommon.Get, "Proc")> _
Public Class GetProcCommand
    Inherits Cmdlet
```

## <a name="defining-parameters"></a><span data-ttu-id="ed2ea-116">Определение параметров</span><span class="sxs-lookup"><span data-stu-id="ed2ea-116">Defining Parameters</span></span>

<span data-ttu-id="ed2ea-117">При необходимости командлет должен определить параметры для обработки входных данных.</span><span class="sxs-lookup"><span data-stu-id="ed2ea-117">If necessary, your cmdlet must define parameters for processing input.</span></span> <span data-ttu-id="ed2ea-118">Этот командлет Get-proc определяет параметр **Name** , как описано в разделе [Добавление параметров, обрабатывающих вход командной строки](adding-parameters-that-process-command-line-input.md).</span><span class="sxs-lookup"><span data-stu-id="ed2ea-118">This Get-Proc cmdlet defines a **Name** parameter as described in [Adding Parameters that Process Command-Line Input](adding-parameters-that-process-command-line-input.md).</span></span>

<span data-ttu-id="ed2ea-119">Ниже приведено объявление параметра для параметра **Name** командлета Get-proc.</span><span class="sxs-lookup"><span data-stu-id="ed2ea-119">Here is the parameter declaration for the **Name** parameter of this Get-Proc cmdlet.</span></span>

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

## <a name="overriding-input-processing-methods"></a><span data-ttu-id="ed2ea-120">Переопределение методов обработки входных данных</span><span class="sxs-lookup"><span data-stu-id="ed2ea-120">Overriding Input Processing Methods</span></span>

<span data-ttu-id="ed2ea-121">Все командлеты должны переопределять по крайней мере один из методов обработки ввода, предоставляемых классом [System. Management. Automation. командлет][] .</span><span class="sxs-lookup"><span data-stu-id="ed2ea-121">All cmdlets must override at least one of the input processing methods provided by the [System.Management.Automation.Cmdlet][] class.</span></span> <span data-ttu-id="ed2ea-122">Эти методы обсуждаются в разделе [Создание первого командлета](creating-a-cmdlet-without-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="ed2ea-122">These methods are discussed in [Creating Your First Cmdlet](creating-a-cmdlet-without-parameters.md).</span></span>

> [!NOTE]
> <span data-ttu-id="ed2ea-123">Командлет должен обрабатывать каждую запись как можно независимо.</span><span class="sxs-lookup"><span data-stu-id="ed2ea-123">Your cmdlet should handle each record as independently as possible.</span></span>

<span data-ttu-id="ed2ea-124">Этот командлет Get-proc переопределяет метод [System. Management. Automation. командлет. ProcessRecord][] для работы с параметром **Name** для входных данных, предоставленных пользователем или сценарием.</span><span class="sxs-lookup"><span data-stu-id="ed2ea-124">This Get-Proc cmdlet overrides the [System.Management.Automation.Cmdlet.ProcessRecord][] method to handle the **Name** parameter for input provided by the user or a script.</span></span> <span data-ttu-id="ed2ea-125">Этот метод получит процессы для каждого запрошенного имени процесса или всех процессов, если имя не указано.</span><span class="sxs-lookup"><span data-stu-id="ed2ea-125">This method will get the processes for each requested process name or all processes if no name is provided.</span></span> <span data-ttu-id="ed2ea-126">Сведения об этом переопределении приведены в [создании первого командлета](creating-a-cmdlet-without-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="ed2ea-126">Details of this override are given in [Creating Your First Cmdlet](creating-a-cmdlet-without-parameters.md).</span></span>

### <a name="things-to-remember-when-reporting-errors"></a><span data-ttu-id="ed2ea-127">Вопросы, которые следует помнить при сообщении об ошибках</span><span class="sxs-lookup"><span data-stu-id="ed2ea-127">Things to Remember When Reporting Errors</span></span>

<span data-ttu-id="ed2ea-128">Объект [System. Management. Automation. ерроррекорд][] , который передается командлетом при записи ошибки, требует возникновения исключения в ядре.</span><span class="sxs-lookup"><span data-stu-id="ed2ea-128">The [System.Management.Automation.ErrorRecord][] object that the cmdlet passes when writing an error requires an exception at its core.</span></span> <span data-ttu-id="ed2ea-129">При определении используемого исключения следуйте рекомендациям .NET.</span><span class="sxs-lookup"><span data-stu-id="ed2ea-129">Follow the .NET guidelines when determining the exception to use.</span></span>
<span data-ttu-id="ed2ea-130">В основном, если ошибка семантически аналогична существующему исключению, командлет должен использовать или наследовать его от этого исключения.</span><span class="sxs-lookup"><span data-stu-id="ed2ea-130">Basically, if the error is semantically the same as an existing exception, the cmdlet should use or derive from that exception.</span></span> <span data-ttu-id="ed2ea-131">В противном случае он должен создать новое исключение или иерархию исключений непосредственно из класса [System. Exception][] .</span><span class="sxs-lookup"><span data-stu-id="ed2ea-131">Otherwise, it should derive a new exception or exception hierarchy directly from the [System.Exception][] class.</span></span>

<span data-ttu-id="ed2ea-132">При создании идентификаторов ошибок (доступ к которым осуществляется через свойство Фулликуалифиедеррорид класса Ерроррекорд) учитывайте следующее.</span><span class="sxs-lookup"><span data-stu-id="ed2ea-132">When creating error identifiers (accessed through the FullyQualifiedErrorId property of the ErrorRecord class) keep the following in mind.</span></span>

- <span data-ttu-id="ed2ea-133">Используйте строки, предназначенные для диагностики, чтобы при проверке полного идентификатора можно было определить причину ошибки и источник ошибки.</span><span class="sxs-lookup"><span data-stu-id="ed2ea-133">Use strings that are targeted for diagnostic purposes so that when inspecting the fully qualified identifier you can determine what the error is and where the error came from.</span></span>

- <span data-ttu-id="ed2ea-134">Правильно сформированный полный идентификатор ошибки может выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="ed2ea-134">A well formed fully qualified error identifier might be as follows.</span></span>

  `CommandNotFoundException,Microsoft.PowerShell.Commands.GetCommandCommand`

<span data-ttu-id="ed2ea-135">Обратите внимание, что в предыдущем примере идентификатор ошибки (первый маркер) обозначает, что такое ошибка, а оставшаяся часть указывает, откуда поступила ошибка.</span><span class="sxs-lookup"><span data-stu-id="ed2ea-135">Notice that in the previous example, the error identifier (the first token) designates what the error is and the remaining part indicates where the error came from.</span></span>

- <span data-ttu-id="ed2ea-136">Для более сложных сценариев Идентификатор ошибки может быть маркером, разделенным точкой, который может быть проанализирован при проверке.</span><span class="sxs-lookup"><span data-stu-id="ed2ea-136">For more complex scenarios, the error identifier can be a dot separated token that can be parsed on inspection.</span></span> <span data-ttu-id="ed2ea-137">Это позволяет создать ветвь для частей идентификатора ошибки, а также идентификатор ошибки и категорию ошибки.</span><span class="sxs-lookup"><span data-stu-id="ed2ea-137">This allows you too branch on the parts of the error identifier as well as the error identifier and error category.</span></span>

<span data-ttu-id="ed2ea-138">Командлет должен назначить определенные идентификаторы ошибок различным путям кода.</span><span class="sxs-lookup"><span data-stu-id="ed2ea-138">The cmdlet should assign specific error identifiers to different code paths.</span></span> <span data-ttu-id="ed2ea-139">При назначении идентификаторов ошибок учитывайте следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="ed2ea-139">Keep the following information in mind for assignment of error identifiers:</span></span>

- <span data-ttu-id="ed2ea-140">Идентификатор ошибки должен оставаться постоянным в течение жизненного цикла командлета.</span><span class="sxs-lookup"><span data-stu-id="ed2ea-140">An error identifier should remain constant throughout the cmdlet life cycle.</span></span> <span data-ttu-id="ed2ea-141">Не изменяйте семантику идентификатора ошибки между версиями командлетов.</span><span class="sxs-lookup"><span data-stu-id="ed2ea-141">Do not change the semantics of an error identifier between cmdlet versions.</span></span>
- <span data-ttu-id="ed2ea-142">Используйте текст для идентификатора ошибки, который кратко соответствует сообщению об ошибке.</span><span class="sxs-lookup"><span data-stu-id="ed2ea-142">Use text for an error identifier that tersely corresponds to the error being reported.</span></span> <span data-ttu-id="ed2ea-143">Не используйте пробелы или знаки препинания.</span><span class="sxs-lookup"><span data-stu-id="ed2ea-143">Do not use white space or punctuation.</span></span>
- <span data-ttu-id="ed2ea-144">Создайте командлет, который создает только воспроизводимые идентификаторы ошибок.</span><span class="sxs-lookup"><span data-stu-id="ed2ea-144">Have your cmdlet generate only error identifiers that are reproducible.</span></span> <span data-ttu-id="ed2ea-145">Например, он не должен создавать идентификатор, включающий идентификатор процесса.</span><span class="sxs-lookup"><span data-stu-id="ed2ea-145">For example, it should not generate an identifier that includes a process identifier.</span></span> <span data-ttu-id="ed2ea-146">Идентификаторы ошибок полезны для пользователя только в том случае, если они соответствуют идентификаторам, которые видят другие пользователи, испытывающие ту же проблему.</span><span class="sxs-lookup"><span data-stu-id="ed2ea-146">Error identifiers are useful to a user only when they correspond to identifiers that are seen by other users experiencing the same problem.</span></span>

<span data-ttu-id="ed2ea-147">Необработанные исключения не перехватываются PowerShell в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="ed2ea-147">Unhandled exceptions are not caught by PowerShell in the following conditions:</span></span>

- <span data-ttu-id="ed2ea-148">Если командлет создает новый поток и код, выполняющийся в этом потоке, создает необработанное исключение, PowerShell не будет перехватывать ошибку и завершит процесс.</span><span class="sxs-lookup"><span data-stu-id="ed2ea-148">If a cmdlet creates a new thread and code running in that thread throws an unhandled exception, PowerShell will not catch the error and will terminate the process.</span></span>
- <span data-ttu-id="ed2ea-149">Если у объекта есть код в его деструкторе или методы Dispose, вызывающие необработанное исключение, PowerShell не будет перехватывать ошибку и завершит процесс.</span><span class="sxs-lookup"><span data-stu-id="ed2ea-149">If an object has code in its destructor or Dispose methods that causes an unhandled exception, PowerShell will not catch the error and will terminate the process.</span></span>

## <a name="reporting-nonterminating-errors"></a><span data-ttu-id="ed2ea-150">Сообщает о неустранимых ошибках</span><span class="sxs-lookup"><span data-stu-id="ed2ea-150">Reporting Nonterminating Errors</span></span>

<span data-ttu-id="ed2ea-151">Любой из методов обработки входных данных может сообщить о неустранимой ошибке в поток вывода с помощью метода [System. Management. Automation. командлет. WriteError][] .</span><span class="sxs-lookup"><span data-stu-id="ed2ea-151">Any one of the input processing methods can report a nonterminating error to the output stream using the [System.Management.Automation.Cmdlet.WriteError][] method.</span></span>

<span data-ttu-id="ed2ea-152">Ниже приведен пример кода из этого командлета Get-proc, который иллюстрирует вызов [System. Management. Automation. командлет. WriteError][] из переопределения метода [System. Management. Automation. командлета. ProcessRecord][] .</span><span class="sxs-lookup"><span data-stu-id="ed2ea-152">Here is a code example from this Get-Proc cmdlet that illustrates the call to [System.Management.Automation.Cmdlet.WriteError][] from within the override of the [System.Management.Automation.Cmdlet.ProcessRecord][] method.</span></span> <span data-ttu-id="ed2ea-153">В этом случае вызов выполняется, если командлет не может найти процесс для указанного идентификатора процесса.</span><span class="sxs-lookup"><span data-stu-id="ed2ea-153">In this case, the call is made if the cmdlet cannot find a process for a specified process identifier.</span></span>

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

### <a name="things-to-remember-about-writing-nonterminating-errors"></a><span data-ttu-id="ed2ea-154">Важные сведения о написании неустранимых ошибок</span><span class="sxs-lookup"><span data-stu-id="ed2ea-154">Things to Remember About Writing Nonterminating Errors</span></span>

<span data-ttu-id="ed2ea-155">Для незавершающей ошибки командлет должен создать конкретный идентификатор ошибки для каждого конкретного входного объекта.</span><span class="sxs-lookup"><span data-stu-id="ed2ea-155">For a nonterminating error, the cmdlet must generate a specific error identifier for each specific input object.</span></span>

<span data-ttu-id="ed2ea-156">Командлету часто требуется изменить действие PowerShell, созданное неустранимой ошибкой.</span><span class="sxs-lookup"><span data-stu-id="ed2ea-156">A cmdlet frequently needs to modify the PowerShell action produced by a nonterminating error.</span></span> <span data-ttu-id="ed2ea-157">Это можно сделать, определив `ErrorAction` `ErrorVariable` Параметры и.</span><span class="sxs-lookup"><span data-stu-id="ed2ea-157">It can do this by defining the `ErrorAction` and `ErrorVariable` parameters.</span></span> <span data-ttu-id="ed2ea-158">При определении `ErrorAction` параметра командлет представляет пользовательский параметр [System. Management. Automation. действие][]. Вы также можете напрямую повлиять на действие, задав `$ErrorActionPreference` переменную.</span><span class="sxs-lookup"><span data-stu-id="ed2ea-158">If defining the `ErrorAction` parameter, the cmdlet presents the user options [System.Management.Automation.ActionPreference][], you can also directly influence the action by setting the `$ErrorActionPreference` variable.</span></span>

<span data-ttu-id="ed2ea-159">Командлет может сохранять неустранимые ошибки в переменную с помощью `ErrorVariable` параметра, который не зависит от значения параметра `ErrorAction` .</span><span class="sxs-lookup"><span data-stu-id="ed2ea-159">The cmdlet can save nonterminating errors to a variable using the `ErrorVariable` parameter, which is not affected by the setting of `ErrorAction`.</span></span> <span data-ttu-id="ed2ea-160">Ошибки можно добавить к существующей переменной ошибки, добавив знак «плюс» (+) перед именем переменной.</span><span class="sxs-lookup"><span data-stu-id="ed2ea-160">Failures can be appended to an existing error variable by adding a plus sign (+) to the front of the variable name.</span></span>

## <a name="code-sample"></a><span data-ttu-id="ed2ea-161">Образец кода</span><span class="sxs-lookup"><span data-stu-id="ed2ea-161">Code Sample</span></span>

<span data-ttu-id="ed2ea-162">Полный пример кода на C# см. в разделе [GetProcessSample04 Sample](./getprocesssample04-sample.md).</span><span class="sxs-lookup"><span data-stu-id="ed2ea-162">For the complete C# sample code, see [GetProcessSample04 Sample](./getprocesssample04-sample.md).</span></span>

## <a name="define-object-types-and-formatting"></a><span data-ttu-id="ed2ea-163">Определение типов объектов и форматирование</span><span class="sxs-lookup"><span data-stu-id="ed2ea-163">Define Object Types and Formatting</span></span>

<span data-ttu-id="ed2ea-164">PowerShell передает сведения между командлетами с помощью объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="ed2ea-164">PowerShell passes information between cmdlets using .NET objects.</span></span> <span data-ttu-id="ed2ea-165">Следовательно, командлету может потребоваться определить собственный тип, или командлету может потребоваться расширить существующий тип, предоставленный другим командлетом.</span><span class="sxs-lookup"><span data-stu-id="ed2ea-165">Consequently, a cmdlet might need to define its own type, or the cmdlet might need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="ed2ea-166">Дополнительные сведения об определении новых типов или расширении существующих типов см. в разделе [расширение типов объектов и форматирование](/previous-versions/ms714665(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="ed2ea-166">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](/previous-versions/ms714665(v=vs.85)).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="ed2ea-167">Создание командлета</span><span class="sxs-lookup"><span data-stu-id="ed2ea-167">Building the Cmdlet</span></span>

<span data-ttu-id="ed2ea-168">После реализации командлета необходимо зарегистрировать его в Windows PowerShell с помощью оснастки Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ed2ea-168">After implementing a cmdlet, you must register it with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="ed2ea-169">Дополнительные сведения о регистрации командлетов см. [в разделе Регистрация командлетов, поставщиков и ведущих приложений](/previous-versions//ms714644(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="ed2ea-169">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85)).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="ed2ea-170">Тестирование командлета</span><span class="sxs-lookup"><span data-stu-id="ed2ea-170">Testing the Cmdlet</span></span>

<span data-ttu-id="ed2ea-171">Если командлет зарегистрирован в PowerShell, его можно проверить, запустив его в командной строке.</span><span class="sxs-lookup"><span data-stu-id="ed2ea-171">When your cmdlet has been registered with PowerShell, you can test it by running it on the command line.</span></span> <span data-ttu-id="ed2ea-172">Давайте проверим пример командлета Get-proc, чтобы проверить, сообщает ли он об ошибке:</span><span class="sxs-lookup"><span data-stu-id="ed2ea-172">Let's test the sample Get-Proc cmdlet to see whether it reports an error:</span></span>

- <span data-ttu-id="ed2ea-173">Запустите PowerShell и используйте командлет Get-proc, чтобы получить процессы с именем TEST.</span><span class="sxs-lookup"><span data-stu-id="ed2ea-173">Start PowerShell, and use the Get-Proc cmdlet to retrieve the processes named "TEST".</span></span>

  ```powershell
  get-proc -name test
  ```

  <span data-ttu-id="ed2ea-174">Появится следующий результат.</span><span class="sxs-lookup"><span data-stu-id="ed2ea-174">The following output appears.</span></span>

  ```
  get-proc : Operation is not valid due to the current state of the object.
  At line:1 char:9
  + get-proc  <<<< -name test
  ```

## <a name="see-also"></a><span data-ttu-id="ed2ea-175">См. также:</span><span class="sxs-lookup"><span data-stu-id="ed2ea-175">See Also</span></span>

[<span data-ttu-id="ed2ea-176">Добавление параметров для обработки входных данных конвейера</span><span class="sxs-lookup"><span data-stu-id="ed2ea-176">Adding Parameters that Process Pipeline Input</span></span>](./adding-parameters-that-process-pipeline-input.md)

[<span data-ttu-id="ed2ea-177">Добавление параметров, обрабатывающих входные данные командной строки</span><span class="sxs-lookup"><span data-stu-id="ed2ea-177">Adding Parameters that Process Command-Line Input</span></span>](./adding-parameters-that-process-command-line-input.md)

[<span data-ttu-id="ed2ea-178">Создание первого командлета</span><span class="sxs-lookup"><span data-stu-id="ed2ea-178">Creating Your First Cmdlet</span></span>](./creating-a-cmdlet-without-parameters.md)

<span data-ttu-id="ed2ea-179">[Расширение типов объектов и форматирование](/previous-versions/ms714665(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="ed2ea-179">[Extending Object Types and Formatting](/previous-versions/ms714665(v=vs.85))</span></span>

<span data-ttu-id="ed2ea-180">[Регистрация командлетов, поставщиков и ведущих приложений](/previous-versions/ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="ed2ea-180">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions/ms714644(v=vs.85))</span></span>

[<span data-ttu-id="ed2ea-181">Справочник по Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ed2ea-181">Windows PowerShell Reference</span></span>](../windows-powershell-reference.md)

[<span data-ttu-id="ed2ea-182">Примеры командлетов</span><span class="sxs-lookup"><span data-stu-id="ed2ea-182">Cmdlet Samples</span></span>](./cmdlet-samples.md)

[System. Exception]: /dotnet/api/System.Exception
[System.Exception]: /dotnet/api/System.Exception
[System. Management. Automation. действие]: /dotnet/api/System.Management.Automation.ActionPreference
[System.Management.Automation.ActionPreference]: /dotnet/api/System.Management.Automation.ActionPreference
[System. Management. Automation. командлет. ProcessRecord]: /dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord
[System.Management.Automation.Cmdlet.ProcessRecord]: /dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord
[System. Management. Automation. командлет. WriteError]: /dotnet/api/System.Management.Automation.Cmdlet.WriteError
[System.Management.Automation.Cmdlet.WriteError]: /dotnet/api/System.Management.Automation.Cmdlet.WriteError
[System. Management. Automation. командлет]: /dotnet/api/System.Management.Automation.Cmdlet
[System.Management.Automation.Cmdlet]: /dotnet/api/System.Management.Automation.Cmdlet
[System. Management. Automation. ErrorCategory]: /dotnet/api/System.Management.Automation.ErrorCategory
[System.Management.Automation.ErrorCategory]: /dotnet/api/System.Management.Automation.ErrorCategory
[System. Management. Automation. Ерроррекорд]: /dotnet/api/System.Management.Automation.ErrorRecord
[System.Management.Automation.ErrorRecord]: /dotnet/api/System.Management.Automation.ErrorRecord
