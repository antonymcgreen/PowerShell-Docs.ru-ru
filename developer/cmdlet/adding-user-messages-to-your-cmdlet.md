---
title: Добавление пользовательских сообщений командлета | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WriteWarning
- notifications, writing
- progress notification
- WriteVerbose
- Stop-Proc
- WriteProgress
- WriteDebug
- notifications, debug
- ProgressRecord
- samples, Stop-Proc cmdlet
- notifications, progress
- notifications, warning
- WriteObject
- WriteError
- verbose notification
- ProcessRecord
- notifications, verbose
- debug notification
- cmdlet, writing notifications
- warning
- code sample, user notifications
- user notifications
ms.assetid: 14c13acb-f0b7-4613-bc7d-c361d14da1a2
caps.latest.revision: 8
ms.openlocfilehash: 5b3a5f5d5d02c7d5a3c1d622ec1a3740739c694f
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068782"
---
# <a name="adding-user-messages-to-your-cmdlet"></a><span data-ttu-id="12cbb-102">Добавление пользовательских сообщений в командлет</span><span class="sxs-lookup"><span data-stu-id="12cbb-102">Adding User Messages to Your Cmdlet</span></span>

<span data-ttu-id="12cbb-103">Командлеты можно написать несколько типов сообщений, которые могут отображаться для пользователя средой выполнения Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="12cbb-103">Cmdlets can write several kinds of messages that can be displayed to the user by the Windows PowerShell runtime.</span></span> <span data-ttu-id="12cbb-104">Эти сообщения включают следующие типы:</span><span class="sxs-lookup"><span data-stu-id="12cbb-104">These messages include the following types:</span></span>

- <span data-ttu-id="12cbb-105">Подробные сообщения, которые содержат общие сведения о пользователях.</span><span class="sxs-lookup"><span data-stu-id="12cbb-105">Verbose messages that contain general user information.</span></span>

- <span data-ttu-id="12cbb-106">Отладка сообщения, содержащие сведения об устранении неполадок.</span><span class="sxs-lookup"><span data-stu-id="12cbb-106">Debug messages that contain troubleshooting information.</span></span>

- <span data-ttu-id="12cbb-107">Предупреждающие сообщения, содержащие уведомление, которое командлет собирается выполнить операцию, которая может иметь непредвиденные результаты.</span><span class="sxs-lookup"><span data-stu-id="12cbb-107">Warning messages that contain a notification that the cmdlet is about to perform an operation that can have unexpected results.</span></span>

- <span data-ttu-id="12cbb-108">Отчет о ходе выполнения, что сообщения, содержащие сведения о том, какую работать командлет завершения при выполнении операции, которая занимает много времени.</span><span class="sxs-lookup"><span data-stu-id="12cbb-108">Progress report messages that contain information about how much work the cmdlet has completed when performing an operation that takes a long time.</span></span>

<span data-ttu-id="12cbb-109">Отсутствуют ограничения на количество сообщений, командлет может записывать или тип сообщений, которые записывает командлета.</span><span class="sxs-lookup"><span data-stu-id="12cbb-109">There are no limits to the number of messages that your cmdlet can write or the type of messages that your cmdlet writes.</span></span> <span data-ttu-id="12cbb-110">Каждое сообщение записывается из определенных вызовом в метод командлета обработки входных данных.</span><span class="sxs-lookup"><span data-stu-id="12cbb-110">Each message is written by making a specific call from within the input processing method of your cmdlet.</span></span>

## <a name="the-stopproc-cmdlet"></a><span data-ttu-id="12cbb-111">Командлет StopProc</span><span class="sxs-lookup"><span data-stu-id="12cbb-111">The StopProc Cmdlet</span></span>

<span data-ttu-id="12cbb-112">Следующие подразделы этого раздела.</span><span class="sxs-lookup"><span data-stu-id="12cbb-112">Topics in this section include the following:</span></span>

- [<span data-ttu-id="12cbb-113">Определение командлета</span><span class="sxs-lookup"><span data-stu-id="12cbb-113">Defining the Cmdlet</span></span>](#Defining-the-Cmdlet)

- [<span data-ttu-id="12cbb-114">Определение параметров для изменения системы</span><span class="sxs-lookup"><span data-stu-id="12cbb-114">Defining Parameters for System Modification</span></span>](#Defining-Parameters-for-System-Modification)

- [<span data-ttu-id="12cbb-115">Переопределив метод обработки входных данных</span><span class="sxs-lookup"><span data-stu-id="12cbb-115">Overriding an Input Processing Method</span></span>](#Overriding-an-Input-Processing-Method)

- [<span data-ttu-id="12cbb-116">Запись подробных сообщений</span><span class="sxs-lookup"><span data-stu-id="12cbb-116">Writing a Verbose Message</span></span>](#Writing-a-Verbose-Message)

- [<span data-ttu-id="12cbb-117">Запись сообщения отладки</span><span class="sxs-lookup"><span data-stu-id="12cbb-117">Writing a Debug Message</span></span>](#Writing-a-Debug-Message)

- [<span data-ttu-id="12cbb-118">Написание предупреждающее сообщение</span><span class="sxs-lookup"><span data-stu-id="12cbb-118">Writing a Warning Message</span></span>](#Writing-a-Warning-Message)

- [<span data-ttu-id="12cbb-119">Запись сообщения о ходе выполнения</span><span class="sxs-lookup"><span data-stu-id="12cbb-119">Writing a Progress Message</span></span>](#Writing-a-Progress-Message)

- [<span data-ttu-id="12cbb-120">Пример кода</span><span class="sxs-lookup"><span data-stu-id="12cbb-120">Code Sample</span></span>](#Code-Sample)

- [<span data-ttu-id="12cbb-121">Определение типов объектов и форматирования</span><span class="sxs-lookup"><span data-stu-id="12cbb-121">Define Object Types and Formatting</span></span>](#Define-Object-Types-and-Formatting)

- [<span data-ttu-id="12cbb-122">Создание командлета</span><span class="sxs-lookup"><span data-stu-id="12cbb-122">Building the Cmdlet</span></span>](#Building-the-Cmdlet)

- [<span data-ttu-id="12cbb-123">Тестирование командлет</span><span class="sxs-lookup"><span data-stu-id="12cbb-123">Testing the Cmdlet</span></span>](#Testing-the-Cmdlet)

## <a name="defining-the-cmdlet"></a><span data-ttu-id="12cbb-124">Определение командлета</span><span class="sxs-lookup"><span data-stu-id="12cbb-124">Defining the Cmdlet</span></span>

<span data-ttu-id="12cbb-125">Первым шагом в создании командлет всегда присвоение имени командлета и объявление класса .NET, который реализует командлет.</span><span class="sxs-lookup"><span data-stu-id="12cbb-125">The first step in cmdlet creation is always naming the cmdlet and declaring the .NET class that implements the cmdlet.</span></span> <span data-ttu-id="12cbb-126">Каких-либо командлета можно написать уведомления для пользователей из входного потока обработки методов. Таким образом как правило, можно назвать этот командлет, используя любой команды, которая указывает, какие изменения системы, командлет выполняет.</span><span class="sxs-lookup"><span data-stu-id="12cbb-126">Any sort of cmdlet can write user notifications from its input processing methods; so, in general, you can name this cmdlet using any verb that indicates what system modifications the cmdlet performs.</span></span> <span data-ttu-id="12cbb-127">Дополнительные сведения о командлет утвержденные глаголы, см. в разделе [имен команд командлет](./approved-verbs-for-windows-powershell-commands.md).</span><span class="sxs-lookup"><span data-stu-id="12cbb-127">For more information about approved cmdlet verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="12cbb-128">Командлет Stop-Proc предназначен для изменения системы. Таким образом [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) объявление класса .NET должен включать `SupportsShouldProcess` атрибута ключевое слово и присвоить `true`.</span><span class="sxs-lookup"><span data-stu-id="12cbb-128">The Stop-Proc cmdlet is designed to modify the system; therefore, the [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) declaration for the .NET class must include the `SupportsShouldProcess` attribute keyword and be set to `true`.</span></span>

<span data-ttu-id="12cbb-129">Ниже приведено определение для этого класса командлет Stop-Proc.</span><span class="sxs-lookup"><span data-stu-id="12cbb-129">The following code is the definition for this Stop-Proc cmdlet class.</span></span> <span data-ttu-id="12cbb-130">Дополнительные сведения о это определение, см. в разделе [Создание командлет, который изменяет система](./creating-a-cmdlet-that-modifies-the-system.md).</span><span class="sxs-lookup"><span data-stu-id="12cbb-130">For more information about this definition, see [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md).</span></span>

```csharp
[Cmdlet(VerbsLifecycle.Stop, "proc",
        SupportsShouldProcess = true)]
public class StopProcCommand : Cmdlet
```

## <a name="defining-parameters-for-system-modification"></a><span data-ttu-id="12cbb-131">Определение параметров для изменения системы</span><span class="sxs-lookup"><span data-stu-id="12cbb-131">Defining Parameters for System Modification</span></span>

<span data-ttu-id="12cbb-132">Командлет Stop-Proc определяет три параметра: `Name`, `Force`, и `PassThru`.</span><span class="sxs-lookup"><span data-stu-id="12cbb-132">The Stop-Proc cmdlet defines three parameters: `Name`, `Force`, and `PassThru`.</span></span> <span data-ttu-id="12cbb-133">Дополнительные сведения об определении этих параметров см. в разделе [Создание командлет, который изменяет система](./creating-a-cmdlet-that-modifies-the-system.md).</span><span class="sxs-lookup"><span data-stu-id="12cbb-133">For more information about defining these parameters, see [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md).</span></span>

<span data-ttu-id="12cbb-134">Ниже приведено объявление параметра для командлета Stop-Proc.</span><span class="sxs-lookup"><span data-stu-id="12cbb-134">Here is the parameter declaration for the Stop-Proc cmdlet.</span></span>

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

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="12cbb-135">Переопределив метод обработки входных данных</span><span class="sxs-lookup"><span data-stu-id="12cbb-135">Overriding an Input Processing Method</span></span>

<span data-ttu-id="12cbb-136">Командлет необходимо переопределить метод обработки входных данных, чаще всего она будет [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord).</span><span class="sxs-lookup"><span data-stu-id="12cbb-136">Your cmdlet must override an input processing method, most often it will be [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord).</span></span> <span data-ttu-id="12cbb-137">Этот командлет Stop-Proc переопределяет [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) метод обработки ввода.</span><span class="sxs-lookup"><span data-stu-id="12cbb-137">This Stop-Proc cmdlet overrides the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) input processing method.</span></span> <span data-ttu-id="12cbb-138">В этой реализации командлет Stop-Proc вызовы выполняются для записи подробных сообщений, сообщения отладки и предупреждающие сообщения.</span><span class="sxs-lookup"><span data-stu-id="12cbb-138">In this implementation of the Stop-Proc cmdlet, calls are made to write verbose messages, debug messages, and warning messages.</span></span>

> [!NOTE]
> <span data-ttu-id="12cbb-139">Дополнительные сведения о том, как этот метод вызывает [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) и [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) методы, см. в разделе [Создание командлет, который изменяет система](./creating-a-cmdlet-that-modifies-the-system.md).</span><span class="sxs-lookup"><span data-stu-id="12cbb-139">For more information about how this method calls the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) methods, see [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md).</span></span>

## <a name="writing-a-verbose-message"></a><span data-ttu-id="12cbb-140">Запись подробных сообщений</span><span class="sxs-lookup"><span data-stu-id="12cbb-140">Writing a Verbose Message</span></span>

<span data-ttu-id="12cbb-141">[System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) метод используется для записи Общие сведения уровня пользователя, который не связан с условия возникновения данной ошибки.</span><span class="sxs-lookup"><span data-stu-id="12cbb-141">The [System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) method is used to write general user-level information that is unrelated to specific error conditions.</span></span> <span data-ttu-id="12cbb-142">Системный администратор затем можно использовать эту информацию, чтобы продолжить обработку других команд.</span><span class="sxs-lookup"><span data-stu-id="12cbb-142">The system administrator can then use that information to continue processing other commands.</span></span> <span data-ttu-id="12cbb-143">Кроме того вся информация, записываемая с помощью этого метода должно быть локализовано, при необходимости.</span><span class="sxs-lookup"><span data-stu-id="12cbb-143">In addition, any information written using this method should be localized as needed.</span></span>

<span data-ttu-id="12cbb-144">В следующем коде из этого командлета Stop-Proc показано два вызова [System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) метода из переопределение метода [System.Management.Automation.Cmdlet.ProcessRecord ](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) метод.</span><span class="sxs-lookup"><span data-stu-id="12cbb-144">The following code from this Stop-Proc cmdlet shows two calls to the [System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) method from the override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span>

```csharp
message = String.Format("Attempting to stop process \"{0}\".", name);
WriteVerbose(message);
```

```csharp
message = String.Format("Stopped process \"{0}\", pid {1}.",
                        processName, process.Id);

WriteVerbose(message);
```

## <a name="writing-a-debug-message"></a><span data-ttu-id="12cbb-145">Запись сообщения отладки</span><span class="sxs-lookup"><span data-stu-id="12cbb-145">Writing a Debug Message</span></span>

<span data-ttu-id="12cbb-146">[System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) метод используется для записи сообщений отладки, которые можно использовать для устранения неполадок в работе командлета.</span><span class="sxs-lookup"><span data-stu-id="12cbb-146">The [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) method is used to write debug messages that can be used to troubleshoot the operation of the cmdlet.</span></span> <span data-ttu-id="12cbb-147">Вызов выполняется из метод обработки входных данных.</span><span class="sxs-lookup"><span data-stu-id="12cbb-147">The call is made from an input processing method.</span></span>

> [!NOTE]
> <span data-ttu-id="12cbb-148">Windows PowerShell также определяет `Debug` параметр, который представляется как verbose и сведений об отладке.</span><span class="sxs-lookup"><span data-stu-id="12cbb-148">Windows PowerShell also defines a `Debug` parameter that presents both verbose and debug information.</span></span> <span data-ttu-id="12cbb-149">Если командлет поддерживает этот параметр, он не требуется вызывать [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) в тот же код, который вызывает [System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) .</span><span class="sxs-lookup"><span data-stu-id="12cbb-149">If your cmdlet supports this parameter, it does not need to call [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) in the same code that calls [System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose).</span></span>

<span data-ttu-id="12cbb-150">Следующих двух разделах кода из командлета Stop-Proc образец Показать вызовы [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) метода из переопределение метода [ System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) метод.</span><span class="sxs-lookup"><span data-stu-id="12cbb-150">The following two sections of code from the sample Stop-Proc cmdlet show calls to the [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) method from the override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span>

<span data-ttu-id="12cbb-151">Это сообщение отладки записывается непосредственно перед [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) вызывается.</span><span class="sxs-lookup"><span data-stu-id="12cbb-151">This debug message is written immediately before [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) is called.</span></span>

```csharp
message =
          String.Format("Acquired name for pid {0} : \"{1}\"",
                       process.Id, processName);
WriteDebug(message);
```

<span data-ttu-id="12cbb-152">Это сообщение отладки записывается непосредственно перед [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) вызывается.</span><span class="sxs-lookup"><span data-stu-id="12cbb-152">This debug message is written immediately before [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) is called.</span></span>

```csharp
message =
         String.Format("Writing process \"{0}\" to pipeline",
         processName);
WriteDebug(message);
WriteObject(process);
```

<span data-ttu-id="12cbb-153">Windows PowerShell автоматически направляет все [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) вызовы инфраструктура трассировки и командлеты.</span><span class="sxs-lookup"><span data-stu-id="12cbb-153">Windows PowerShell automatically routes any [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) calls to the tracing infrastructure and cmdlets.</span></span> <span data-ttu-id="12cbb-154">Это позволяет отследить ведущего приложения, в файл или отладчик не нужно прикладывать усилия дополнительной разработки в данном командлете вызовы методов.</span><span class="sxs-lookup"><span data-stu-id="12cbb-154">This allows the method calls to be traced to the hosting application, a file, or a debugger without your having to do any extra development work within the cmdlet.</span></span> <span data-ttu-id="12cbb-155">Параметр командной строки реализует операции трассировки.</span><span class="sxs-lookup"><span data-stu-id="12cbb-155">The following command-line entry implements a tracing operation.</span></span>

<span data-ttu-id="12cbb-156">**PS > выражение трассировки stop-proc-файл proc.log-команда stop-proc Блокнот**</span><span class="sxs-lookup"><span data-stu-id="12cbb-156">**PS> trace-expression stop-proc -file proc.log -command stop-proc notepad**</span></span>

## <a name="writing-a-warning-message"></a><span data-ttu-id="12cbb-157">Написание предупреждающее сообщение</span><span class="sxs-lookup"><span data-stu-id="12cbb-157">Writing a Warning Message</span></span>

<span data-ttu-id="12cbb-158">[System.Management.Automation.Cmdlet.WriteWarning](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) метод используется для записи предупреждения в случае, когда командлет собирается выполнить операцию, которую может иметь непредвиденный результат, например, перезапись файла только для чтения.</span><span class="sxs-lookup"><span data-stu-id="12cbb-158">The [System.Management.Automation.Cmdlet.WriteWarning](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) method is used to write a warning when the cmdlet is about to perform an operation that might have an unexpected result, for example, overwriting a read-only file.</span></span>

<span data-ttu-id="12cbb-159">В следующем коде из командлета Stop-Proc примера показано вызов [System.Management.Automation.Cmdlet.WriteWarning](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) метода из переопределение метода [ System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) метод.</span><span class="sxs-lookup"><span data-stu-id="12cbb-159">The following code from the sample Stop-Proc cmdlet shows the call to the [System.Management.Automation.Cmdlet.WriteWarning](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) method from the override of the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span>

```csharp
 if (criticalProcess)
 {
   message =
             String.Format("Stopping the critical process \"{0}\".",
                           processName);
   WriteWarning(message);
} // if (criticalProcess...
```

## <a name="writing-a-progress-message"></a><span data-ttu-id="12cbb-160">Запись сообщения о ходе выполнения</span><span class="sxs-lookup"><span data-stu-id="12cbb-160">Writing a Progress Message</span></span>

<span data-ttu-id="12cbb-161">[System.Management.Automation.Cmdlet.WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) используется для записи сообщения о ходе выполнения при операции командлет занять продолжительное время.</span><span class="sxs-lookup"><span data-stu-id="12cbb-161">The [System.Management.Automation.Cmdlet.WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) is used to write progress messages when cmdlet operations take an extended amount of time to complete.</span></span> <span data-ttu-id="12cbb-162">Вызов [System.Management.Automation.Cmdlet.WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) передает [System.Management.Automation.Progressrecord](/dotnet/api/System.Management.Automation.ProgressRecord) объект, который отправляется в приложение для подготовки к просмотру для пользователя.</span><span class="sxs-lookup"><span data-stu-id="12cbb-162">A call to [System.Management.Automation.Cmdlet.WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) passes a [System.Management.Automation.Progressrecord](/dotnet/api/System.Management.Automation.ProgressRecord) object that is sent to the hosting application for rendering to the user.</span></span>

> [!NOTE]
> <span data-ttu-id="12cbb-163">Этот командлет Stop-Proc не включает вызов [System.Management.Automation.Cmdlet.WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) метод.</span><span class="sxs-lookup"><span data-stu-id="12cbb-163">This Stop-Proc cmdlet does not include a call to the [System.Management.Automation.Cmdlet.WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) method.</span></span>

<span data-ttu-id="12cbb-164">Следующий код является примером сообщение о ходе выполнения, написанной командлет, который пытается выполнить копирование элемента.</span><span class="sxs-lookup"><span data-stu-id="12cbb-164">The following code is an example of a progress message written by a cmdlet that is attempting to copy an item.</span></span>

```csharp
int myId = 0;
string myActivity = "Copy-item: Copying *.* to c:\abc";
string myStatus = "Copying file bar.txt";
ProgressRecord pr = new ProgressRecord(myId, myActivity, myStatus);
WriteProgress(pr);

pr.RecordType = ProgressRecordType.Completed;
WriteProgress(pr);
```

## <a name="code-sample"></a><span data-ttu-id="12cbb-165">Пример кода</span><span class="sxs-lookup"><span data-stu-id="12cbb-165">Code Sample</span></span>

<span data-ttu-id="12cbb-166">Для полной C# пример кода, см. в разделе [пример StopProcessSample02](./stopprocesssample02-sample.md).</span><span class="sxs-lookup"><span data-stu-id="12cbb-166">For the complete C# sample code, see [StopProcessSample02 Sample](./stopprocesssample02-sample.md).</span></span>

## <a name="define-object-types-and-formatting"></a><span data-ttu-id="12cbb-167">Определение типов объектов и форматирования</span><span class="sxs-lookup"><span data-stu-id="12cbb-167">Define Object Types and Formatting</span></span>

<span data-ttu-id="12cbb-168">Windows PowerShell передает данные между командлетами, используя объекты .NET.</span><span class="sxs-lookup"><span data-stu-id="12cbb-168">Windows PowerShell passes information between cmdlets using .NET objects.</span></span> <span data-ttu-id="12cbb-169">Следовательно командлета может потребоваться определить его собственного типа, или командлет может потребоваться расширить существующий тип предоставляемые другому командлету.</span><span class="sxs-lookup"><span data-stu-id="12cbb-169">Consequently, a cmdlet might need to define its own type, or the cmdlet might need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="12cbb-170">Дополнительные сведения о определение новых типов или расширения существующих типов, см. в разделе [расширение типов объектов и форматирование](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351).</span><span class="sxs-lookup"><span data-stu-id="12cbb-170">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="12cbb-171">Создание командлета</span><span class="sxs-lookup"><span data-stu-id="12cbb-171">Building the Cmdlet</span></span>

<span data-ttu-id="12cbb-172">После реализации командлета, его необходимо зарегистрировать с помощью Windows PowerShell через оснастку Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="12cbb-172">After implementing a cmdlet, it must be registered with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="12cbb-173">Дополнительные сведения о регистрации командлетов см. в разделе [как регистрация командлетов, поставщиков и ведущих приложений](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).</span><span class="sxs-lookup"><span data-stu-id="12cbb-173">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="12cbb-174">Тестирование командлет</span><span class="sxs-lookup"><span data-stu-id="12cbb-174">Testing the Cmdlet</span></span>

<span data-ttu-id="12cbb-175">При командлета был зарегистрирован с помощью Windows PowerShell, его можно проверить, запустив его в командной строке.</span><span class="sxs-lookup"><span data-stu-id="12cbb-175">When your cmdlet has been registered with Windows PowerShell, you can test it by running it on the command line.</span></span> <span data-ttu-id="12cbb-176">Давайте протестируем командлет Stop-Proc образец.</span><span class="sxs-lookup"><span data-stu-id="12cbb-176">Let's test the sample Stop-Proc cmdlet.</span></span> <span data-ttu-id="12cbb-177">Дополнительные сведения об использовании командлетов из командной строки см. в разделе [Приступая к работе с Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="12cbb-177">For more information about using cmdlets from the command line, see the [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span></span>

- <span data-ttu-id="12cbb-178">Параметр командной строки использует многопроцессорную Stop для остановки процесса с именем «Блокнот», предоставляют подробные уведомления и печать отладочной информации.</span><span class="sxs-lookup"><span data-stu-id="12cbb-178">The following command-line entry uses Stop-Proc to stop the process named "NOTEPAD", provide verbose notifications, and print debug information.</span></span>

    ```powershell
    PS> stop-proc -Name notepad -Verbose -Debug
    ```

<span data-ttu-id="12cbb-179">Появляется следующий результат.</span><span class="sxs-lookup"><span data-stu-id="12cbb-179">The following output appears.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="12cbb-180">См. также</span><span class="sxs-lookup"><span data-stu-id="12cbb-180">See Also</span></span>

[<span data-ttu-id="12cbb-181">Создать командлет, который изменяет системы</span><span class="sxs-lookup"><span data-stu-id="12cbb-181">Create a Cmdlet that Modifies the System</span></span>](./creating-a-cmdlet-that-modifies-the-system.md)

[<span data-ttu-id="12cbb-182">Как создать командлет Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="12cbb-182">How to Create a Windows PowerShell Cmdlet</span></span>](http://msdn.microsoft.com/en-us/0d721742-c849-4d0d-964f-78ddd9cd258c)

[<span data-ttu-id="12cbb-183">Расширение типов объектов и форматирование</span><span class="sxs-lookup"><span data-stu-id="12cbb-183">Extending Object Types and Formatting</span></span>](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[<span data-ttu-id="12cbb-184">Регистрация командлетов, поставщиков и ведущих приложений</span><span class="sxs-lookup"><span data-stu-id="12cbb-184">How to Register Cmdlets, Providers, and Host Applications</span></span>](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[<span data-ttu-id="12cbb-185">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="12cbb-185">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
