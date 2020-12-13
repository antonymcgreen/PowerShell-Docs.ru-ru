---
ms.date: 09/13/2016
ms.topic: reference
title: Создание командлета без параметров
description: Создание командлета без параметров
ms.openlocfilehash: 5df27ac4c1f6dfcc3e7596d93f8db0f97aae71c1
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646550"
---
# <a name="creating-a-cmdlet-without-parameters"></a><span data-ttu-id="9b368-103">Создание командлета без параметров</span><span class="sxs-lookup"><span data-stu-id="9b368-103">Creating a Cmdlet without Parameters</span></span>

<span data-ttu-id="9b368-104">В этом разделе описывается создание командлета, который получает сведения с локального компьютера без использования параметров, а затем записывает сведения в конвейер.</span><span class="sxs-lookup"><span data-stu-id="9b368-104">This section describes how to create a cmdlet that retrieves information from the local computer without the use of parameters, and then writes the information to the pipeline.</span></span> <span data-ttu-id="9b368-105">Описываемый здесь командлет является командлетом Get-Proc, который получает сведения о процессах локального компьютера, а затем отображает эти сведения в командной строке.</span><span class="sxs-lookup"><span data-stu-id="9b368-105">The cmdlet described here is a Get-Proc cmdlet that retrieves information about the processes of the local computer, and then displays that information at the command line.</span></span>

> [!NOTE]
> <span data-ttu-id="9b368-106">Имейте в виду, что при написании командлетов ссылочные сборки® Windows PowerShell загружаются на диск (по умолчанию — C:\Program Files\Reference Assemblies\Microsoft\WindowsPowerShell\v1.0).</span><span class="sxs-lookup"><span data-stu-id="9b368-106">Be aware that when writing cmdlets, the Windows PowerShell® reference assemblies are downloaded onto disk (by default at C:\Program Files\Reference Assemblies\Microsoft\WindowsPowerShell\v1.0).</span></span> <span data-ttu-id="9b368-107">Они не устанавливаются в глобальный кэш сборок (GAC).</span><span class="sxs-lookup"><span data-stu-id="9b368-107">They are not installed in the Global Assembly Cache (GAC).</span></span>

## <a name="naming-the-cmdlet"></a><span data-ttu-id="9b368-108">Присвоение имени командлету</span><span class="sxs-lookup"><span data-stu-id="9b368-108">Naming the Cmdlet</span></span>

<span data-ttu-id="9b368-109">Имя командлета состоит из глагола, указывающего действие, которое выполняет командлет, и существительное, которое указывает элементы, с которыми работает командлет.</span><span class="sxs-lookup"><span data-stu-id="9b368-109">A cmdlet name consists of a verb that indicates the action the cmdlet takes and a noun that indicates the items that the cmdlet acts upon.</span></span> <span data-ttu-id="9b368-110">Поскольку этот пример Get-Proc командлет извлекает объекты обработки, он использует команду Get, определенную перечислением [System. Management. Automation. вербскоммон](/dotnet/api/System.Management.Automation.VerbsCommon) , и существительное "proc", чтобы указать, что командлет работает над элементами процесса.</span><span class="sxs-lookup"><span data-stu-id="9b368-110">Because this sample Get-Proc cmdlet retrieves process objects, it uses the verb "Get", defined by the [System.Management.Automation.Verbscommon](/dotnet/api/System.Management.Automation.VerbsCommon) enumeration, and the noun "Proc" to indicate that the cmdlet works on process items.</span></span>

<span data-ttu-id="9b368-111">При именовании командлетов не используйте следующие символы: #, () {} [] &-/\ $;: "" <> &#124; ?</span><span class="sxs-lookup"><span data-stu-id="9b368-111">When naming cmdlets, do not use any of the following characters: # , () {} [] & - /\ $ ; : " '<> &#124; ?</span></span> <span data-ttu-id="9b368-112">@ \` .</span><span class="sxs-lookup"><span data-stu-id="9b368-112">@ \` .</span></span>

### <a name="choosing-a-noun"></a><span data-ttu-id="9b368-113">Выбор существительного</span><span class="sxs-lookup"><span data-stu-id="9b368-113">Choosing a Noun</span></span>

<span data-ttu-id="9b368-114">Следует выбрать конкретное существительное.</span><span class="sxs-lookup"><span data-stu-id="9b368-114">You should choose a noun that is specific.</span></span> <span data-ttu-id="9b368-115">Лучше использовать одноименное существительное с сокращенной версией названия продукта.</span><span class="sxs-lookup"><span data-stu-id="9b368-115">It is best to use a singular noun prefixed with a shortened version of the product name.</span></span> <span data-ttu-id="9b368-116">Примером имени командлета этого типа является " `Get-SQLServer` ".</span><span class="sxs-lookup"><span data-stu-id="9b368-116">An example cmdlet name of this type is "`Get-SQLServer`".</span></span>

### <a name="choosing-a-verb"></a><span data-ttu-id="9b368-117">Выбор команды</span><span class="sxs-lookup"><span data-stu-id="9b368-117">Choosing a Verb</span></span>

<span data-ttu-id="9b368-118">Следует использовать глагол из набора утвержденных имен глаголов командлетов.</span><span class="sxs-lookup"><span data-stu-id="9b368-118">You should use a verb from the set of approved cmdlet verb names.</span></span> <span data-ttu-id="9b368-119">Дополнительные сведения о утвержденных командах командлетов см. в разделе [имена глаголов командлетов](./approved-verbs-for-windows-powershell-commands.md).</span><span class="sxs-lookup"><span data-stu-id="9b368-119">For more information about the approved cmdlet verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

## <a name="defining-the-cmdlet-class"></a><span data-ttu-id="9b368-120">Определение класса командлета</span><span class="sxs-lookup"><span data-stu-id="9b368-120">Defining the Cmdlet Class</span></span>

<span data-ttu-id="9b368-121">После выбора имени командлета определите класс .NET для реализации командлета.</span><span class="sxs-lookup"><span data-stu-id="9b368-121">Once you have chosen a cmdlet name, define a .NET class to implement the cmdlet.</span></span> <span data-ttu-id="9b368-122">Ниже приведено определение класса для этого примера Get-Proc командлета:</span><span class="sxs-lookup"><span data-stu-id="9b368-122">Here is the class definition for this sample Get-Proc cmdlet:</span></span>

```csharp
[Cmdlet(VerbsCommon.Get, "Proc")]
  public class GetProcCommand : Cmdlet
```

```vb
<Cmdlet(VerbsCommon.Get, "Proc")> _
Public Class GetProcCommand
    Inherits Cmdlet
```

<span data-ttu-id="9b368-123">Обратите внимание, что предыдущий для определения класса атрибут [System. Management. Automation. CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) с синтаксисом `[Cmdlet(verb, noun, ...)]` используется для определения этого класса в качестве командлета.</span><span class="sxs-lookup"><span data-stu-id="9b368-123">Notice that previous to the class definition, the [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) attribute, with the syntax `[Cmdlet(verb, noun, ...)]`, is used to identify this class as a cmdlet.</span></span> <span data-ttu-id="9b368-124">Это единственный обязательный атрибут для всех командлетов, позволяющий среде выполнения Windows PowerShell правильно вызывать их.</span><span class="sxs-lookup"><span data-stu-id="9b368-124">This is the only required attribute for all cmdlets, and it allows the Windows PowerShell runtime to call them correctly.</span></span> <span data-ttu-id="9b368-125">При необходимости можно задать ключевые слова атрибутов для дальнейшего объявления класса.</span><span class="sxs-lookup"><span data-stu-id="9b368-125">You can set attribute keywords to further declare the class if necessary.</span></span> <span data-ttu-id="9b368-126">Обратите внимание, что объявление атрибута для нашего примера класса Жетпроккомманд объявляет только имена существительных и глаголов для командлета Get-Proc.</span><span class="sxs-lookup"><span data-stu-id="9b368-126">Be aware that the attribute declaration for our sample GetProcCommand class declares only the noun and verb names for the Get-Proc cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="9b368-127">Ключевые слова, которые можно задать для всех классов атрибутов Windows PowerShell, соответствуют свойствам класса Attribute.</span><span class="sxs-lookup"><span data-stu-id="9b368-127">For all Windows PowerShell attribute classes, the keywords that you can set correspond to properties of the attribute class.</span></span>

<span data-ttu-id="9b368-128">При именовании класса командлета рекомендуется отразить имя командлета в имени класса.</span><span class="sxs-lookup"><span data-stu-id="9b368-128">When naming the class of the cmdlet, it is a good practice to reflect the cmdlet name in the class name.</span></span> <span data-ttu-id="9b368-129">Для этого используйте форму "Вербнаункомманд" и замените "verb" и "существительное" на глагол и существительное, используемые в имени командлета.</span><span class="sxs-lookup"><span data-stu-id="9b368-129">To do this, use the form "VerbNounCommand" and replace "Verb" and "Noun" with the verb and noun used in the cmdlet name.</span></span> <span data-ttu-id="9b368-130">Как показано в предыдущем определении класса, командлет Sample Get-Proc определяет класс с именем Жетпроккомманд, который является производным от базового класса [System. Management. Automation. командлет](/dotnet/api/System.Management.Automation.Cmdlet) .</span><span class="sxs-lookup"><span data-stu-id="9b368-130">As is shown in the previous class definition, the sample Get-Proc cmdlet defines a class called GetProcCommand, which derives from the [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) base class.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9b368-131">Если вы хотите определить командлет, который напрямую обращается к среде выполнения Windows PowerShell, класс .NET должен быть производным от базового класса [System. Management. Automation. PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) .</span><span class="sxs-lookup"><span data-stu-id="9b368-131">If you want to define a cmdlet that accesses the Windows PowerShell runtime directly, your .NET class should derive from the [System.Management.Automation.PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) base class.</span></span> <span data-ttu-id="9b368-132">Дополнительные сведения об этом классе см. [в разделе Создание командлета, определяющего наборы параметров](./adding-parameter-sets-to-a-cmdlet.md).</span><span class="sxs-lookup"><span data-stu-id="9b368-132">For more information about this class, see [Creating a Cmdlet that Defines Parameter Sets](./adding-parameter-sets-to-a-cmdlet.md).</span></span>

> [!NOTE]
> <span data-ttu-id="9b368-133">Класс для командлета должен быть явно помечен как открытый.</span><span class="sxs-lookup"><span data-stu-id="9b368-133">The class for a cmdlet must be explicitly marked as public.</span></span> <span data-ttu-id="9b368-134">Классы, которые не помечены как открытые, по умолчанию будут внутренними и не будут найдены средой выполнения Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9b368-134">Classes that are not marked as public will default to internal and will not be found by the Windows PowerShell runtime.</span></span>

<span data-ttu-id="9b368-135">Windows PowerShell использует пространство имен [Microsoft. PowerShell. Commands](/dotnet/api/Microsoft.PowerShell.Commands) для своих классов командлетов.</span><span class="sxs-lookup"><span data-stu-id="9b368-135">Windows PowerShell uses the [Microsoft.PowerShell.Commands](/dotnet/api/Microsoft.PowerShell.Commands) namespace for its cmdlet classes.</span></span> <span data-ttu-id="9b368-136">Рекомендуется размещать классы командлетов в пространстве имен Commands пространства имен API, например XXX. PS. Commands.</span><span class="sxs-lookup"><span data-stu-id="9b368-136">It is recommended to place your cmdlet classes in a Commands namespace of your API namespace, for example, xxx.PS.Commands.</span></span>

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="9b368-137">Переопределение метода обработки входных данных</span><span class="sxs-lookup"><span data-stu-id="9b368-137">Overriding an Input Processing Method</span></span>

<span data-ttu-id="9b368-138">Класс [System. Management. Automation. командлет](/dotnet/api/System.Management.Automation.Cmdlet) предоставляет три основных метода обработки ввода, по крайней мере один из которых должен переопределяться командлетом.</span><span class="sxs-lookup"><span data-stu-id="9b368-138">The [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) class provides three main input processing methods, at least one of which your cmdlet must override.</span></span> <span data-ttu-id="9b368-139">Дополнительные сведения о том, как Windows PowerShell обрабатывает записи, см. в разделе [как работает Windows PowerShell](/previous-versions//ms714658(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="9b368-139">For more information about how Windows PowerShell processes records, see [How Windows PowerShell Works](/previous-versions//ms714658(v=vs.85)).</span></span>

<span data-ttu-id="9b368-140">Для всех типов входных данных среда выполнения Windows PowerShell вызывает [System. Management. Automation. командлет. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) для включения обработки.</span><span class="sxs-lookup"><span data-stu-id="9b368-140">For all types of input, the Windows PowerShell runtime calls [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) to enable processing.</span></span> <span data-ttu-id="9b368-141">Если командлет должен выполнить некоторую предварительную обработку или установку, это можно сделать, переопределив этот метод.</span><span class="sxs-lookup"><span data-stu-id="9b368-141">If your cmdlet must perform some preprocessing or setup, it can do this by overriding this method.</span></span>

> [!NOTE]
> <span data-ttu-id="9b368-142">Windows PowerShell использует термин "запись" для описания набора значений параметров, предоставляемых при вызове командлета.</span><span class="sxs-lookup"><span data-stu-id="9b368-142">Windows PowerShell uses the term "record" to describe the set of parameter values supplied when a cmdlet is called.</span></span>

<span data-ttu-id="9b368-143">Если командлет принимает входные данные конвейера, он должен переопределить метод [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) и, при необходимости, метод [System. Management. Automation. командлет. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) .</span><span class="sxs-lookup"><span data-stu-id="9b368-143">If your cmdlet accepts pipeline input, it must override the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method, and optionally the [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method.</span></span> <span data-ttu-id="9b368-144">Например, командлет может переопределить оба метода, если он собирает все входные данные с помощью [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) , а затем использует входные данные как единое целое, а не как один элемент за раз, как это `Sort-Object` делает командлет.</span><span class="sxs-lookup"><span data-stu-id="9b368-144">For example, a cmdlet might override both methods if it gathers all input using [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) and then operates on the input as a whole rather than one element at a time, as the `Sort-Object` cmdlet does.</span></span>

<span data-ttu-id="9b368-145">Если командлет не принимает входные данные конвейера, он должен переопределить метод [System. Management. Automation. командлет. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) .</span><span class="sxs-lookup"><span data-stu-id="9b368-145">If your cmdlet does not take pipeline input, it should override the [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method.</span></span> <span data-ttu-id="9b368-146">Имейте в виду, что этот метод часто используется вместо [System. Management. Automation. командлет. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) , если командлет не может работать с одним элементом за раз, как в случае с командлетом Sort.</span><span class="sxs-lookup"><span data-stu-id="9b368-146">Be aware that this method is frequently used in place of [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) when the cmdlet cannot operate on one element at a time, as is the case for a sorting cmdlet.</span></span>

<span data-ttu-id="9b368-147">Поскольку этот пример Get-Proc командлет должен получить входные данные конвейера, он переопределяет метод [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) и использует реализации по умолчанию для [System. Management. Automation. командлета. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) и [System. Management. Automation. командлет. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing).</span><span class="sxs-lookup"><span data-stu-id="9b368-147">Because this sample Get-Proc cmdlet must receive pipeline input, it overrides the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method and uses the default implementations for [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) and [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing).</span></span> <span data-ttu-id="9b368-148">Переопределение [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) извлекает процессы и записывает их в командную строку с помощью метода [System. Management. Automation. командлета. WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) .</span><span class="sxs-lookup"><span data-stu-id="9b368-148">The [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) override retrieves processes and writes them to the command line using the [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) method.</span></span>

```csharp
protected override void ProcessRecord()
{
  // Get the current processes
  Process[] processes = Process.GetProcesses();

  // Write the processes to the pipeline making them available
  // to the next cmdlet. The second parameter of this call tells
  // PowerShell to enumerate the array, and send one process at a
  // time to the pipeline.
  WriteObject(processes, true);
}
```

```vb
Protected Overrides Sub ProcessRecord()

    '/ Get the current processes.
    Dim processes As Process()
    processes = Process.GetProcesses()

    '/ Write the processes to the pipeline making them available
    '/ to the next cmdlet. The second parameter of this call tells
    '/ PowerShell to enumerate the array, and send one process at a
    '/ time to the pipeline.
    WriteObject(processes, True)

End Sub 'ProcessRecord
```

#### <a name="things-to-remember-about-input-processing"></a><span data-ttu-id="9b368-149">Вопросы, которые следует учитывать при обработке входных данных</span><span class="sxs-lookup"><span data-stu-id="9b368-149">Things to Remember About Input Processing</span></span>

- <span data-ttu-id="9b368-150">Источником по умолчанию для входных данных является явный объект (например, строка), предоставленный пользователем в командной строке.</span><span class="sxs-lookup"><span data-stu-id="9b368-150">The default source for input is an explicit object (for example, a string) provided by the user on the command line.</span></span> <span data-ttu-id="9b368-151">Дополнительные сведения см. в разделе [Создание командлета для обработки входных данных командной строки](./adding-parameters-that-process-command-line-input.md).</span><span class="sxs-lookup"><span data-stu-id="9b368-151">For more information, see [Creating a Cmdlet to Process Command Line Input](./adding-parameters-that-process-command-line-input.md).</span></span>

- <span data-ttu-id="9b368-152">Метод обработки входных данных также может принимать входные данные из выходного объекта вышестоящего командлета в конвейере.</span><span class="sxs-lookup"><span data-stu-id="9b368-152">An input processing method can also receive input from the output object of an upstream cmdlet on the pipeline.</span></span> <span data-ttu-id="9b368-153">Дополнительные сведения см. в разделе [Создание командлета для обработки входных данных конвейера](./adding-parameters-that-process-pipeline-input.md).</span><span class="sxs-lookup"><span data-stu-id="9b368-153">For more information, see [Creating a Cmdlet to Process Pipeline Input](./adding-parameters-that-process-pipeline-input.md).</span></span> <span data-ttu-id="9b368-154">Имейте в виду, что командлет может получать входные данные из сочетания источников командной строки и конвейера.</span><span class="sxs-lookup"><span data-stu-id="9b368-154">Be aware that your cmdlet can receive input from a combination of command-line and pipeline sources.</span></span>

- <span data-ttu-id="9b368-155">Нисходящий командлет может не возвращаться в течение длительного времени, а не вообще.</span><span class="sxs-lookup"><span data-stu-id="9b368-155">The downstream cmdlet might not return for a long time, or not at all.</span></span> <span data-ttu-id="9b368-156">По этой причине метод обработки ввода в командлете не должен удерживать блокировки во время вызовов [System. Management. Automation. командлет. WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject), особенно блокировок, для которых область выходит за пределы экземпляра командлета.</span><span class="sxs-lookup"><span data-stu-id="9b368-156">For that reason, the input processing method in your cmdlet should not hold locks during calls to [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject), especially locks for which the scope extends beyond the cmdlet instance.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9b368-157">Командлеты никогда не должны вызывать [System. Console. WriteLine \*](/dotnet/api/System.Console.WriteLine) или его эквивалент.</span><span class="sxs-lookup"><span data-stu-id="9b368-157">Cmdlets should never call [System.Console.Writeline\*](/dotnet/api/System.Console.WriteLine) or its equivalent.</span></span>

- <span data-ttu-id="9b368-158">Командлет может иметь переменные объекта для очистки после завершения обработки (например, если он открывает обработчик файла в методе [System. Management. Automation. командлет. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) и сохраняет открытый обработчик для использования [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)).</span><span class="sxs-lookup"><span data-stu-id="9b368-158">Your cmdlet might have object variables to clean up when it is finished processing (for example, if it opens a file handle in the [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method and keeps the handle open for use by [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)).</span></span> <span data-ttu-id="9b368-159">Важно помнить, что среда выполнения Windows PowerShell не всегда вызывает метод [System. Management. Automation. командлет. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) , который должен выполнять очистку объектов.</span><span class="sxs-lookup"><span data-stu-id="9b368-159">It is important to remember that the Windows PowerShell runtime does not always call the [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method, which should perform object cleanup.</span></span>

<span data-ttu-id="9b368-160">Например, [System. Management. Automation. командлет. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) может не вызываться, если в командлете отменено значение Мидуэй или если в какой-либо части командлета возникла неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="9b368-160">For example, [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) might not be called if the cmdlet is canceled midway or if a terminating error occurs in any part of the cmdlet.</span></span> <span data-ttu-id="9b368-161">Таким образом, командлет, требующий очистки объектов, должен реализовать полный шаблон [System. IDisposable](/dotnet/api/System.IDisposable) , включая метод завершения, чтобы среда выполнения могла вызывать как [System. Management. Automation. командлет. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) , так и [System. IDisposable. Dispose \*](/dotnet/api/System.IDisposable.Dispose) в конце обработки.</span><span class="sxs-lookup"><span data-stu-id="9b368-161">Therefore, a cmdlet that requires object cleanup should implement the complete [System.IDisposable](/dotnet/api/System.IDisposable) pattern, including the finalizer, so that the runtime can call both [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) and [System.IDisposable.Dispose\*](/dotnet/api/System.IDisposable.Dispose) at the end of processing.</span></span>

## <a name="code-sample"></a><span data-ttu-id="9b368-162">Образец кода</span><span class="sxs-lookup"><span data-stu-id="9b368-162">Code Sample</span></span>

<span data-ttu-id="9b368-163">Полный пример кода на C# см. в разделе [GetProcessSample01 Sample](./getprocesssample01-sample.md).</span><span class="sxs-lookup"><span data-stu-id="9b368-163">For the complete C# sample code, see [GetProcessSample01 Sample](./getprocesssample01-sample.md).</span></span>

## <a name="defining-object-types-and-formatting"></a><span data-ttu-id="9b368-164">Определение типов объектов и форматирование</span><span class="sxs-lookup"><span data-stu-id="9b368-164">Defining Object Types and Formatting</span></span>

<span data-ttu-id="9b368-165">Windows PowerShell передает сведения между командлетами с помощью объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="9b368-165">Windows PowerShell passes information between cmdlets using .NET objects.</span></span> <span data-ttu-id="9b368-166">Следовательно, командлету может потребоваться определить собственный тип, или командлету может потребоваться расширить существующий тип, предоставленный другим командлетом.</span><span class="sxs-lookup"><span data-stu-id="9b368-166">Consequently, a cmdlet might need to define its own type, or the cmdlet might need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="9b368-167">Дополнительные сведения об определении новых типов или расширении существующих типов см. в разделе [расширение типов объектов и форматирование](/previous-versions//ms714665(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="9b368-167">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85)).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="9b368-168">Создание командлета</span><span class="sxs-lookup"><span data-stu-id="9b368-168">Building the Cmdlet</span></span>

<span data-ttu-id="9b368-169">После реализации командлета необходимо зарегистрировать его в Windows PowerShell с помощью оснастки Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9b368-169">After implementing a cmdlet, you must register it with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="9b368-170">Дополнительные сведения о регистрации командлетов см. [в разделе Регистрация командлетов, поставщиков и ведущих приложений](/previous-versions//ms714644(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="9b368-170">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85)).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="9b368-171">Тестирование командлета</span><span class="sxs-lookup"><span data-stu-id="9b368-171">Testing the Cmdlet</span></span>

<span data-ttu-id="9b368-172">Если командлет зарегистрирован в Windows PowerShell, его можно проверить, запустив его в командной строке.</span><span class="sxs-lookup"><span data-stu-id="9b368-172">When your cmdlet has been registered with Windows PowerShell, you can test it by running it on the command line.</span></span> <span data-ttu-id="9b368-173">Код для нашего примера командлета Get-Proc небольшой, но он по-прежнему использует среду выполнения Windows PowerShell и существующий объект .NET, что достаточно для того, чтобы сделать его полезным.</span><span class="sxs-lookup"><span data-stu-id="9b368-173">The code for our sample Get-Proc cmdlet is small, but it still uses the Windows PowerShell runtime and an existing .NET object, which is enough to make it useful.</span></span> <span data-ttu-id="9b368-174">Давайте протестируем ее, чтобы лучше понять, что может сделать Get-Proc и как можно использовать его выходные данные.</span><span class="sxs-lookup"><span data-stu-id="9b368-174">Let's test it to better understand what Get-Proc can do and how its output can be used.</span></span> <span data-ttu-id="9b368-175">Дополнительные сведения об использовании командлетов из командной строки см. в [Начало работы с помощью Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="9b368-175">For more information about using cmdlets from the command line, see the [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span></span>

1. <span data-ttu-id="9b368-176">Запустите Windows PowerShell и получите текущие процессы, запущенные на компьютере.</span><span class="sxs-lookup"><span data-stu-id="9b368-176">Start Windows PowerShell, and get the current processes running on the computer.</span></span>

    ```powershell
    get-proc
    ```

    <span data-ttu-id="9b368-177">Появится следующий результат.</span><span class="sxs-lookup"><span data-stu-id="9b368-177">The following output appears.</span></span>

    ```output
    Handles  NPM(K)  PM(K)  WS(K)  VS(M)  CPU(s)  Id   ProcessName
    -------  ------  -----  -----  -----  ------  --   ----------
    254      7       7664   12048  66     173.75  1200  QCTRAY
    32       2       1372   2628   31       0.04  1860  DLG
    271      6       1216   3688   33       0.03  3816  lg
    27       2       560    1920   24       0.01  1768  TpScrex
    ...
    ```

2. <span data-ttu-id="9b368-178">Назначьте переменную для результатов командлета, чтобы упростить манипуляцию.</span><span class="sxs-lookup"><span data-stu-id="9b368-178">Assign a variable to the cmdlet results for easier manipulation.</span></span>

    ```powershell
    $p=get-proc
    ```

3. <span data-ttu-id="9b368-179">Возвращает количество процессов.</span><span class="sxs-lookup"><span data-stu-id="9b368-179">Get the number of processes.</span></span>

    ```powershell
    $p.length
    ```

    <span data-ttu-id="9b368-180">Появится следующий результат.</span><span class="sxs-lookup"><span data-stu-id="9b368-180">The following output appears.</span></span>

    ```output
    63
    ```

4. <span data-ttu-id="9b368-181">Получение определенного процесса.</span><span class="sxs-lookup"><span data-stu-id="9b368-181">Retrieve a specific process.</span></span>

    ```powershell
    $p[6]
    ```

    <span data-ttu-id="9b368-182">Появится следующий результат.</span><span class="sxs-lookup"><span data-stu-id="9b368-182">The following output appears.</span></span>

    ```output
    Handles  NPM(K)  PM(K)  WS(K)  VS(M)  CPU(s)  Id    ProcessName
    -------  ------  -----  -----  -----  ------  --    -----------
    1033     3       2400   3336   35     0.53    1588  rundll32
    ```

5. <span data-ttu-id="9b368-183">Получение времени начала этого процесса.</span><span class="sxs-lookup"><span data-stu-id="9b368-183">Get the start time of this process.</span></span>

    ```powershell
    $p[6].starttime
    ```

    <span data-ttu-id="9b368-184">Появится следующий результат.</span><span class="sxs-lookup"><span data-stu-id="9b368-184">The following output appears.</span></span>

    ```output
    Tuesday, July 26, 2005 9:34:15 AM
    ```

    ```powershell
    $p[6].starttime.dayofyear
    ```

    ```output
    207
    ```

6. <span data-ttu-id="9b368-185">Получите процессы, для которых количество маркеров превышает 500, и отсортируйте результат.</span><span class="sxs-lookup"><span data-stu-id="9b368-185">Get the processes for which the handle count is greater than 500, and sort the result.</span></span>

    ```powershell
    $p | Where-Object {$_.HandleCount -gt 500 } | Sort-Object HandleCount
    ```

    <span data-ttu-id="9b368-186">Появится следующий результат.</span><span class="sxs-lookup"><span data-stu-id="9b368-186">The following output appears.</span></span>

    ```output
    Handles  NPM(K)  PM(K)  WS(K)  VS(M)  CPU(s)  Id   ProcessName
    -------  ------  -----  -----  -----  ------  --   ----------
    568      14      2164   4972   39     5.55    824  svchost
    716       7      2080   5332   28    25.38    468  csrss
    761      21      33060  56608  440  393.56    3300 WINWORD
    791      71      7412   4540   59     3.31    492  winlogon
    ...
    ```

7. <span data-ttu-id="9b368-187">Используйте `Get-Member` командлет, чтобы получить список свойств, доступных для каждого процесса.</span><span class="sxs-lookup"><span data-stu-id="9b368-187">Use the `Get-Member` cmdlet to list the properties available for each process.</span></span>

    ```powershell
    $p | Get-Member -MemberType property
    ```

    ```output
        TypeName: System.Diagnostics.Process
    ```

    <span data-ttu-id="9b368-188">Появится следующий результат.</span><span class="sxs-lookup"><span data-stu-id="9b368-188">The following output appears.</span></span>

    ```output
    Name                     MemberType Definition
    ----                     ---------- ----------
    BasePriority             Property   System.Int32 BasePriority {get;}
    Container                Property   System.ComponentModel.IContainer Conta...
    EnableRaisingEvents      Property   System.Boolean EnableRaisingEvents {ge...
    ...
    ```

## <a name="see-also"></a><span data-ttu-id="9b368-189">См. также:</span><span class="sxs-lookup"><span data-stu-id="9b368-189">See Also</span></span>

[<span data-ttu-id="9b368-190">Создание командлета для обработки входных данных командной строки</span><span class="sxs-lookup"><span data-stu-id="9b368-190">Creating a Cmdlet to Process Command Line Input</span></span>](./adding-parameters-that-process-command-line-input.md)

[<span data-ttu-id="9b368-191">Создание командлета для обработки входных данных конвейера</span><span class="sxs-lookup"><span data-stu-id="9b368-191">Creating a Cmdlet to Process Pipeline Input</span></span>](./adding-parameters-that-process-pipeline-input.md)

[<span data-ttu-id="9b368-192">Создание командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9b368-192">How to Create a Windows PowerShell Cmdlet</span></span>](/powershell/scripting/developer/cmdlet/writing-a-windows-powershell-cmdlet)

<span data-ttu-id="9b368-193">[Расширение типов объектов и форматирование](/previous-versions//ms714665(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="9b368-193">[Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85))</span></span>

<span data-ttu-id="9b368-194">[Как работает Windows PowerShell](/previous-versions//ms714658(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="9b368-194">[How Windows PowerShell Works](/previous-versions//ms714658(v=vs.85))</span></span>

<span data-ttu-id="9b368-195">[Регистрация командлетов, поставщиков и ведущих приложений](/previous-versions//ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="9b368-195">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85))</span></span>

[<span data-ttu-id="9b368-196">Справочник по Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9b368-196">Windows PowerShell Reference</span></span>](../windows-powershell-reference.md)

[<span data-ttu-id="9b368-197">Примеры командлетов</span><span class="sxs-lookup"><span data-stu-id="9b368-197">Cmdlet Samples</span></span>](./cmdlet-samples.md)
