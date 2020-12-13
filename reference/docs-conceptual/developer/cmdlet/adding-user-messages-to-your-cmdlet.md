---
ms.date: 09/13/2016
ms.topic: reference
title: Добавление пользовательских сообщений в командлет
description: Добавление пользовательских сообщений в командлет
ms.openlocfilehash: de6fcc093af1d01287eed1eb8cc7b81cf5d2fdd8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668343"
---
# <a name="adding-user-messages-to-your-cmdlet"></a><span data-ttu-id="9e324-103">Добавление пользовательских сообщений в командлет</span><span class="sxs-lookup"><span data-stu-id="9e324-103">Adding User Messages to Your Cmdlet</span></span>

<span data-ttu-id="9e324-104">Командлеты могут записывать сообщения нескольких типов, которые могут отображаться для пользователя средой выполнения Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9e324-104">Cmdlets can write several kinds of messages that can be displayed to the user by the Windows PowerShell runtime.</span></span> <span data-ttu-id="9e324-105">Эти сообщения включают следующие типы:</span><span class="sxs-lookup"><span data-stu-id="9e324-105">These messages include the following types:</span></span>

- <span data-ttu-id="9e324-106">Подробные сообщения, содержащие общие сведения о пользователях.</span><span class="sxs-lookup"><span data-stu-id="9e324-106">Verbose messages that contain general user information.</span></span>

- <span data-ttu-id="9e324-107">Сообщения отладки, содержащие сведения об устранении неполадок.</span><span class="sxs-lookup"><span data-stu-id="9e324-107">Debug messages that contain troubleshooting information.</span></span>

- <span data-ttu-id="9e324-108">Предупреждающие сообщения, содержащие уведомление о том, что командлет собирается выполнить операцию, которая может привести к непредвиденным результатам.</span><span class="sxs-lookup"><span data-stu-id="9e324-108">Warning messages that contain a notification that the cmdlet is about to perform an operation that can have unexpected results.</span></span>

- <span data-ttu-id="9e324-109">Сообщения отчета о состоянии, содержащие сведения о том, сколько работы командлета выполнила при выполнении операции, которая занимает много времени.</span><span class="sxs-lookup"><span data-stu-id="9e324-109">Progress report messages that contain information about how much work the cmdlet has completed when performing an operation that takes a long time.</span></span>

<span data-ttu-id="9e324-110">Количество сообщений, которые может записывать командлет, и тип сообщений, записываемых командлетом, не ограничены.</span><span class="sxs-lookup"><span data-stu-id="9e324-110">There are no limits to the number of messages that your cmdlet can write or the type of messages that your cmdlet writes.</span></span> <span data-ttu-id="9e324-111">Каждое сообщение записывается путем выполнения определенного вызова в методе обработки входных данных командлета.</span><span class="sxs-lookup"><span data-stu-id="9e324-111">Each message is written by making a specific call from within the input processing method of your cmdlet.</span></span>

## <a name="defining-the-cmdlet"></a><span data-ttu-id="9e324-112">Определение командлета</span><span class="sxs-lookup"><span data-stu-id="9e324-112">Defining the Cmdlet</span></span>

<span data-ttu-id="9e324-113">Первым шагом при создании командлета всегда является присвоение имени командлета и объявление класса .NET, реализующего командлет.</span><span class="sxs-lookup"><span data-stu-id="9e324-113">The first step in cmdlet creation is always naming the cmdlet and declaring the .NET class that implements the cmdlet.</span></span> <span data-ttu-id="9e324-114">Любой командлет может записывать пользовательские уведомления из своих методов обработки входных данных. Таким образом, можно присвоить этому командлету имя, используя любую команду, которая указывает, какие изменения системы выполняет командлет.</span><span class="sxs-lookup"><span data-stu-id="9e324-114">Any sort of cmdlet can write user notifications from its input processing methods; so, in general, you can name this cmdlet using any verb that indicates what system modifications the cmdlet performs.</span></span> <span data-ttu-id="9e324-115">Дополнительные сведения о утвержденных командах командлетов см. в разделе [имена глаголов командлетов](./approved-verbs-for-windows-powershell-commands.md).</span><span class="sxs-lookup"><span data-stu-id="9e324-115">For more information about approved cmdlet verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="9e324-116">Командлет Stop-Proc предназначен для изменения системы; Поэтому объявление [System. Management. Automation. CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) для класса .NET должно включать `SupportsShouldProcess` ключевое слово Attribute и иметь значение `true` .</span><span class="sxs-lookup"><span data-stu-id="9e324-116">The Stop-Proc cmdlet is designed to modify the system; therefore, the [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) declaration for the .NET class must include the `SupportsShouldProcess` attribute keyword and be set to `true`.</span></span>

<span data-ttu-id="9e324-117">Следующий код является определением для данного класса командлета Stop-Proc.</span><span class="sxs-lookup"><span data-stu-id="9e324-117">The following code is the definition for this Stop-Proc cmdlet class.</span></span> <span data-ttu-id="9e324-118">Дополнительные сведения об этом определении см. в разделе [Создание командлета, изменяющего систему](./creating-a-cmdlet-that-modifies-the-system.md).</span><span class="sxs-lookup"><span data-stu-id="9e324-118">For more information about this definition, see [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md).</span></span>

```csharp
[Cmdlet(VerbsLifecycle.Stop, "proc",
        SupportsShouldProcess = true)]
public class StopProcCommand : Cmdlet
```

## <a name="defining-parameters-for-system-modification"></a><span data-ttu-id="9e324-119">Определение параметров для изменения системы</span><span class="sxs-lookup"><span data-stu-id="9e324-119">Defining Parameters for System Modification</span></span>

<span data-ttu-id="9e324-120">Командлет Stop-Proc определяет три параметра: `Name` , `Force` и `PassThru` .</span><span class="sxs-lookup"><span data-stu-id="9e324-120">The Stop-Proc cmdlet defines three parameters: `Name`, `Force`, and `PassThru`.</span></span> <span data-ttu-id="9e324-121">Дополнительные сведения об определении этих параметров см. в разделе [Создание командлета, изменяющего систему](./creating-a-cmdlet-that-modifies-the-system.md).</span><span class="sxs-lookup"><span data-stu-id="9e324-121">For more information about defining these parameters, see [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md).</span></span>

<span data-ttu-id="9e324-122">Ниже приведено объявление параметра для командлета Stop-Proc.</span><span class="sxs-lookup"><span data-stu-id="9e324-122">Here is the parameter declaration for the Stop-Proc cmdlet.</span></span>

```csharp
[Parameter(
           Position = 0,
           Mandatory = true,
           ValueFromPipeline = true,
           ValueFromPipelineByPropertyName = true
)]
public string[] Name
{
  get { return processNames; }
  set { processNames = value; }
}
private string[] processNames;

/// <summary>
/// Specify the Force parameter that allows the user to override
/// the ShouldContinue call to force the stop operation. This
/// parameter should always be used with caution.
/// </summary>
[Parameter]
public SwitchParameter Force
{
  get { return force; }
  set { force = value; }
}
private bool force;

/// <summary>
/// Specify the PassThru parameter that allows the user to specify
/// that the cmdlet should pass the process object down the pipeline
/// after the process has been stopped.
/// </summary>
[Parameter]
public SwitchParameter PassThru
{
  get { return passThru; }
  set { passThru = value; }
}
private bool passThru;
```

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="9e324-123">Переопределение метода обработки входных данных</span><span class="sxs-lookup"><span data-stu-id="9e324-123">Overriding an Input Processing Method</span></span>

<span data-ttu-id="9e324-124">Командлет должен переопределять метод обработки ввода, чаще всего это будет [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord).</span><span class="sxs-lookup"><span data-stu-id="9e324-124">Your cmdlet must override an input processing method, most often it will be [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord).</span></span> <span data-ttu-id="9e324-125">Этот командлет Stop-Proc переопределяет метод обработки ввода [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) .</span><span class="sxs-lookup"><span data-stu-id="9e324-125">This Stop-Proc cmdlet overrides the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) input processing method.</span></span> <span data-ttu-id="9e324-126">В этой реализации командлета Stop-Proc выполняются вызовы для записи подробных сообщений, сообщений отладки и предупреждающих сообщений.</span><span class="sxs-lookup"><span data-stu-id="9e324-126">In this implementation of the Stop-Proc cmdlet, calls are made to write verbose messages, debug messages, and warning messages.</span></span>

> [!NOTE]
> <span data-ttu-id="9e324-127">Дополнительные сведения о том, как этот метод вызывает методы [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) и [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) , см. в разделе [Создание командлета, изменяющего систему](./creating-a-cmdlet-that-modifies-the-system.md).</span><span class="sxs-lookup"><span data-stu-id="9e324-127">For more information about how this method calls the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) methods, see [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md).</span></span>

## <a name="writing-a-verbose-message"></a><span data-ttu-id="9e324-128">Запись подробного сообщения</span><span class="sxs-lookup"><span data-stu-id="9e324-128">Writing a Verbose Message</span></span>

<span data-ttu-id="9e324-129">Метод [System. Management. Automation. командлет. вритевербосе](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) используется для записи общих сведений на уровне пользователя, не связанных с конкретными условиями ошибок.</span><span class="sxs-lookup"><span data-stu-id="9e324-129">The [System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) method is used to write general user-level information that is unrelated to specific error conditions.</span></span> <span data-ttu-id="9e324-130">Затем системный администратор может использовать эти сведения для продолжения обработки других команд.</span><span class="sxs-lookup"><span data-stu-id="9e324-130">The system administrator can then use that information to continue processing other commands.</span></span> <span data-ttu-id="9e324-131">Кроме того, любые сведения, написанные с помощью этого метода, должны быть локализованы по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="9e324-131">In addition, any information written using this method should be localized as needed.</span></span>

<span data-ttu-id="9e324-132">В следующем коде из этого командлета Stop-Proc показаны два вызова метода [System. Management. Automation. командлет. вритевербосе](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) из переопределения метода [System. Management. Automation. командлета. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) .</span><span class="sxs-lookup"><span data-stu-id="9e324-132">The following code from this Stop-Proc cmdlet shows two calls to the [System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) method from the override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span>

```csharp
message = String.Format("Attempting to stop process \"{0}\".", name);
WriteVerbose(message);
```

```csharp
message = String.Format("Stopped process \"{0}\", pid {1}.",
                        processName, process.Id);

WriteVerbose(message);
```

## <a name="writing-a-debug-message"></a><span data-ttu-id="9e324-133">Запись сообщения об отладке</span><span class="sxs-lookup"><span data-stu-id="9e324-133">Writing a Debug Message</span></span>

<span data-ttu-id="9e324-134">Метод [System. Management. Automation. командлет. вритедебуг](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) используется для записи отладочных сообщений, которые можно использовать для устранения неполадок в работе командлета.</span><span class="sxs-lookup"><span data-stu-id="9e324-134">The [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) method is used to write debug messages that can be used to troubleshoot the operation of the cmdlet.</span></span> <span data-ttu-id="9e324-135">Вызов выполняется из метода обработки входных данных.</span><span class="sxs-lookup"><span data-stu-id="9e324-135">The call is made from an input processing method.</span></span>

> [!NOTE]
> <span data-ttu-id="9e324-136">Windows PowerShell также определяет `Debug` параметр, который предоставляет как подробную, так и отладочную информацию.</span><span class="sxs-lookup"><span data-stu-id="9e324-136">Windows PowerShell also defines a `Debug` parameter that presents both verbose and debug information.</span></span> <span data-ttu-id="9e324-137">Если командлет поддерживает этот параметр, ему не нужно вызывать [System. Management. Automation. командлет. вритедебуг](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) в том же коде, который вызывает [System. Management. Automation. командлет. вритевербосе](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose).</span><span class="sxs-lookup"><span data-stu-id="9e324-137">If your cmdlet supports this parameter, it does not need to call [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) in the same code that calls [System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose).</span></span>

<span data-ttu-id="9e324-138">Следующие два раздела кода из примера Stop-Proc командлета показывают вызовы метода [System. Management. Automation. командлет. вритедебуг](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) из переопределения метода [System. Management. Automation. командлета. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) .</span><span class="sxs-lookup"><span data-stu-id="9e324-138">The following two sections of code from the sample Stop-Proc cmdlet show calls to the [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) method from the override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span>

<span data-ttu-id="9e324-139">Это сообщение отладки записывается непосредственно перед вызовом [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) .</span><span class="sxs-lookup"><span data-stu-id="9e324-139">This debug message is written immediately before [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) is called.</span></span>

```csharp
message =
          String.Format("Acquired name for pid {0} : \"{1}\"",
                       process.Id, processName);
WriteDebug(message);
```

<span data-ttu-id="9e324-140">Это сообщение отладки записывается непосредственно перед вызовом [System. Management. Automation. командлет. WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) .</span><span class="sxs-lookup"><span data-stu-id="9e324-140">This debug message is written immediately before [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) is called.</span></span>

```csharp
message =
         String.Format("Writing process \"{0}\" to pipeline",
         processName);
WriteDebug(message);
WriteObject(process);
```

<span data-ttu-id="9e324-141">Windows PowerShell автоматически направляет все вызовы [System. Management. Automation. командлет. вритедебуг](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) в инфраструктуру и командлеты трассировки.</span><span class="sxs-lookup"><span data-stu-id="9e324-141">Windows PowerShell automatically routes any [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) calls to the tracing infrastructure and cmdlets.</span></span> <span data-ttu-id="9e324-142">Это позволяет отслеживать вызовы методов для ведущего приложения, файла или отладчика без необходимости выполнять какие-либо дополнительные действия по разработке в командлете.</span><span class="sxs-lookup"><span data-stu-id="9e324-142">This allows the method calls to be traced to the hosting application, a file, or a debugger without your having to do any extra development work within the cmdlet.</span></span> <span data-ttu-id="9e324-143">Следующая запись командной строки реализует операцию трассировки.</span><span class="sxs-lookup"><span data-stu-id="9e324-143">The following command-line entry implements a tracing operation.</span></span>

<span data-ttu-id="9e324-144">**PS> трассировка-выражение "Trace-proc-File proc. log-Command"**</span><span class="sxs-lookup"><span data-stu-id="9e324-144">**PS> trace-expression stop-proc -file proc.log -command stop-proc notepad**</span></span>

## <a name="writing-a-warning-message"></a><span data-ttu-id="9e324-145">Создание сообщения с предупреждением</span><span class="sxs-lookup"><span data-stu-id="9e324-145">Writing a Warning Message</span></span>

<span data-ttu-id="9e324-146">Метод [System. Management. Automation. командлет. вритеварнинг](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) используется для записи предупреждения о том, что командлет собирается выполнить операцию, которая может иметь непредвиденный результат, например перезапись файла, доступного только для чтения.</span><span class="sxs-lookup"><span data-stu-id="9e324-146">The [System.Management.Automation.Cmdlet.WriteWarning](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) method is used to write a warning when the cmdlet is about to perform an operation that might have an unexpected result, for example, overwriting a read-only file.</span></span>

<span data-ttu-id="9e324-147">В следующем коде из командлета Sample Stop-Proc показан вызов метода [System. Management. Automation. командлет. вритеварнинг](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) из переопределения метода [System. Management. Automation. командлета. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) .</span><span class="sxs-lookup"><span data-stu-id="9e324-147">The following code from the sample Stop-Proc cmdlet shows the call to the [System.Management.Automation.Cmdlet.WriteWarning](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) method from the override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span>

```csharp
 if (criticalProcess)
 {
   message =
             String.Format("Stopping the critical process \"{0}\".",
                           processName);
   WriteWarning(message);
} // if (criticalProcess...
```

## <a name="writing-a-progress-message"></a><span data-ttu-id="9e324-148">Запись сообщения о ходе выполнения</span><span class="sxs-lookup"><span data-stu-id="9e324-148">Writing a Progress Message</span></span>

<span data-ttu-id="9e324-149">[System. Management. Automation. командлет. вритепрогресс](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) используется для записи сообщений о ходе выполнения, когда выполнение операций командлета занимает продолжительное время.</span><span class="sxs-lookup"><span data-stu-id="9e324-149">The [System.Management.Automation.Cmdlet.WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) is used to write progress messages when cmdlet operations take an extended amount of time to complete.</span></span> <span data-ttu-id="9e324-150">Вызов [System. Management. Automation. командлет. вритепрогресс](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) передает объект [System. Management. Automation. Progressrecord](/dotnet/api/System.Management.Automation.ProgressRecord) , который отправляется в приложение размещения для отрисовки пользователю.</span><span class="sxs-lookup"><span data-stu-id="9e324-150">A call to [System.Management.Automation.Cmdlet.WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) passes a [System.Management.Automation.Progressrecord](/dotnet/api/System.Management.Automation.ProgressRecord) object that is sent to the hosting application for rendering to the user.</span></span>

> [!NOTE]
> <span data-ttu-id="9e324-151">Этот командлет Stop-Proc не включает вызов метода [System. Management. Automation. командлета. вритепрогресс](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) .</span><span class="sxs-lookup"><span data-stu-id="9e324-151">This Stop-Proc cmdlet does not include a call to the [System.Management.Automation.Cmdlet.WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) method.</span></span>

<span data-ttu-id="9e324-152">Следующий код является примером сообщения о ходе выполнения, написанного командлетом, который пытается скопировать элемент.</span><span class="sxs-lookup"><span data-stu-id="9e324-152">The following code is an example of a progress message written by a cmdlet that is attempting to copy an item.</span></span>

```csharp
int myId = 0;
string myActivity = "Copy-item: Copying *.* to c:\abc";
string myStatus = "Copying file bar.txt";
ProgressRecord pr = new ProgressRecord(myId, myActivity, myStatus);
WriteProgress(pr);

pr.RecordType = ProgressRecordType.Completed;
WriteProgress(pr);
```

## <a name="code-sample"></a><span data-ttu-id="9e324-153">Образец кода</span><span class="sxs-lookup"><span data-stu-id="9e324-153">Code Sample</span></span>

<span data-ttu-id="9e324-154">Полный пример кода на C# см. в разделе [StopProcessSample02 Sample](./stopprocesssample02-sample.md).</span><span class="sxs-lookup"><span data-stu-id="9e324-154">For the complete C# sample code, see [StopProcessSample02 Sample](./stopprocesssample02-sample.md).</span></span>

## <a name="define-object-types-and-formatting"></a><span data-ttu-id="9e324-155">Определение типов объектов и форматирование</span><span class="sxs-lookup"><span data-stu-id="9e324-155">Define Object Types and Formatting</span></span>

<span data-ttu-id="9e324-156">Windows PowerShell передает сведения между командлетами с помощью объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="9e324-156">Windows PowerShell passes information between cmdlets using .NET objects.</span></span> <span data-ttu-id="9e324-157">Следовательно, командлету может потребоваться определить собственный тип, или командлету может потребоваться расширить существующий тип, предоставленный другим командлетом.</span><span class="sxs-lookup"><span data-stu-id="9e324-157">Consequently, a cmdlet might need to define its own type, or the cmdlet might need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="9e324-158">Дополнительные сведения об определении новых типов или расширении существующих типов см. в разделе [расширение типов объектов и форматирование](/previous-versions//ms714665(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="9e324-158">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85)).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="9e324-159">Создание командлета</span><span class="sxs-lookup"><span data-stu-id="9e324-159">Building the Cmdlet</span></span>

<span data-ttu-id="9e324-160">После реализации командлета его необходимо зарегистрировать в Windows PowerShell с помощью оснастки Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9e324-160">After implementing a cmdlet, it must be registered with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="9e324-161">Дополнительные сведения о регистрации командлетов см. [в разделе Регистрация командлетов, поставщиков и ведущих приложений](/previous-versions//ms714644(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="9e324-161">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85)).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="9e324-162">Тестирование командлета</span><span class="sxs-lookup"><span data-stu-id="9e324-162">Testing the Cmdlet</span></span>

<span data-ttu-id="9e324-163">Если командлет зарегистрирован в Windows PowerShell, его можно проверить, запустив его в командной строке.</span><span class="sxs-lookup"><span data-stu-id="9e324-163">When your cmdlet has been registered with Windows PowerShell, you can test it by running it on the command line.</span></span> <span data-ttu-id="9e324-164">Давайте протестируем пример командлета Stop-Proc.</span><span class="sxs-lookup"><span data-stu-id="9e324-164">Let's test the sample Stop-Proc cmdlet.</span></span> <span data-ttu-id="9e324-165">Дополнительные сведения об использовании командлетов из командной строки см. в [Начало работы с помощью Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="9e324-165">For more information about using cmdlets from the command line, see the [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span></span>

- <span data-ttu-id="9e324-166">Следующая запись командной строки использует Stop-Proc для завершения процесса с именем "Блокнот", предоставления подробных уведомлений и печати отладочной информации.</span><span class="sxs-lookup"><span data-stu-id="9e324-166">The following command-line entry uses Stop-Proc to stop the process named "NOTEPAD", provide verbose notifications, and print debug information.</span></span>

    ```powershell
    PS> stop-proc -Name notepad -Verbose -Debug
    ```

    <span data-ttu-id="9e324-167">Появится следующий результат.</span><span class="sxs-lookup"><span data-stu-id="9e324-167">The following output appears.</span></span>

    ```
    VERBOSE: Attempting to stop process " notepad ".
    DEBUG: Acquired name for pid 5584 : "notepad"

    Confirm
    Continue with this operation?
    [Y] Yes  [A] Yes to All  [H] Halt Command  [S] Suspend  [?] Help (default is "Y"): Y

    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (5584)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    VERBOSE: Stopped process "notepad", pid 5584.
    ```

## <a name="see-also"></a><span data-ttu-id="9e324-168">См. также:</span><span class="sxs-lookup"><span data-stu-id="9e324-168">See Also</span></span>

[<span data-ttu-id="9e324-169">Создание командлета, изменяющего систему</span><span class="sxs-lookup"><span data-stu-id="9e324-169">Create a Cmdlet that Modifies the System</span></span>](./creating-a-cmdlet-that-modifies-the-system.md)

[<span data-ttu-id="9e324-170">Создание командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9e324-170">How to Create a Windows PowerShell Cmdlet</span></span>](/powershell/scripting/developer/cmdlet/writing-a-windows-powershell-cmdlet)

<span data-ttu-id="9e324-171">[Расширение типов объектов и форматирование](/previous-versions//ms714665(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="9e324-171">[Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85))</span></span>

<span data-ttu-id="9e324-172">[Регистрация командлетов, поставщиков и ведущих приложений](/previous-versions//ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="9e324-172">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85))</span></span>

[<span data-ttu-id="9e324-173">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9e324-173">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
