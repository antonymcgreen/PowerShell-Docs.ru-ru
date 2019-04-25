---
title: Создание командлета без параметров | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- cmdlets [PowerShell Programmers Guide], creating
- cmdlets [PowerShell Programmers Guide], basic cmdlet
ms.assetid: 54236ef3-82db-45f8-9114-1ecb7ff65d3e
caps.latest.revision: 8
ms.openlocfilehash: c380b28570c955de6f41152fd617f5c1b0f9e4bd
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068340"
---
# <a name="creating-a-cmdlet-without-parameters"></a><span data-ttu-id="083a7-102">Создание командлета без параметров</span><span class="sxs-lookup"><span data-stu-id="083a7-102">Creating a Cmdlet without Parameters</span></span>

<span data-ttu-id="083a7-103">В этом разделе описывается, как создать командлет, который извлекает данные из локального компьютера без использования параметров, а затем записывает данные в конвейер.</span><span class="sxs-lookup"><span data-stu-id="083a7-103">This section describes how to create a cmdlet that retrieves information from the local computer without the use of parameters, and then writes the information to the pipeline.</span></span> <span data-ttu-id="083a7-104">Командлет, описанные здесь является командлет Get-Proc, который извлекает сведения о процессах на локальном компьютере, а затем отображает эти сведения в командной строке.</span><span class="sxs-lookup"><span data-stu-id="083a7-104">The cmdlet described here is a Get-Proc cmdlet that retrieves information about the processes of the local computer, and then displays that information at the command line.</span></span>

<span data-ttu-id="083a7-105">Следующие подразделы этого раздела.</span><span class="sxs-lookup"><span data-stu-id="083a7-105">Topics in this section include the following:</span></span>

- [<span data-ttu-id="083a7-106">Именование командлет</span><span class="sxs-lookup"><span data-stu-id="083a7-106">Naming the Cmdlet</span></span>](#Naming-the-Cmdlet)

- [<span data-ttu-id="083a7-107">Определение класса командлета</span><span class="sxs-lookup"><span data-stu-id="083a7-107">Defining the Cmdlet Class</span></span>](#Defining-the-Cmdlet-Class)

- [<span data-ttu-id="083a7-108">Переопределив метод обработки входных данных</span><span class="sxs-lookup"><span data-stu-id="083a7-108">Overriding an Input Processing Method</span></span>](#Overriding-an-Input-Processing-Method)

- [<span data-ttu-id="083a7-109">Пример кода</span><span class="sxs-lookup"><span data-stu-id="083a7-109">Code Sample</span></span>](#Code-Sample)

- [<span data-ttu-id="083a7-110">Определение типов объектов и форматирование</span><span class="sxs-lookup"><span data-stu-id="083a7-110">Defining Object Types and Formatting</span></span>](#Defining-Object-Types-and-Formatting)

- [<span data-ttu-id="083a7-111">Создание командлета</span><span class="sxs-lookup"><span data-stu-id="083a7-111">Building the Cmdlet</span></span>](#Building-the-Cmdlet)

- [<span data-ttu-id="083a7-112">Тестирование командлет</span><span class="sxs-lookup"><span data-stu-id="083a7-112">Testing the Cmdlet</span></span>](#Testing-the-Cmdlet)

> [!NOTE]
> <span data-ttu-id="083a7-113">Имейте в виду, что при написании командлетов, Windows PowerShell® ссылочные сборки загружаются на диск (по умолчанию в C:\Program Files\Reference Assemblies\Microsoft\WindowsPowerShell\v1.0). Они не установлены в глобальный кэш сборок (GAC).</span><span class="sxs-lookup"><span data-stu-id="083a7-113">Be aware that when writing cmdlets, the Windows PowerShell® reference assemblies are downloaded onto disk (by default at C:\Program Files\Reference Assemblies\Microsoft\WindowsPowerShell\v1.0).They are not installed in the Global Assembly Cache (GAC).</span></span>

## <a name="naming-the-cmdlet"></a><span data-ttu-id="083a7-114">Именование командлет</span><span class="sxs-lookup"><span data-stu-id="083a7-114">Naming the Cmdlet</span></span>

<span data-ttu-id="083a7-115">Имя командлета состоит из команды, которая указывает, что принимает действие командлета и существительное, который указывает элементы, которые обрабатывают командлет.</span><span class="sxs-lookup"><span data-stu-id="083a7-115">A cmdlet name consists of a verb that indicates the action the cmdlet takes and a noun that indicates the items that the cmdlet acts upon.</span></span> <span data-ttu-id="083a7-116">Так как этот командлет Get-Proc пример извлекает объекты процессов, используется команда «Get», определяемый [System.Management.Automation.Verbscommon](/dotnet/api/System.Management.Automation.VerbsCommon) перечисления и термин «Proc», чтобы указать, что командлет работает с элементами процесса.</span><span class="sxs-lookup"><span data-stu-id="083a7-116">Because this sample Get-Proc cmdlet retrieves process objects, it uses the verb "Get", defined by the [System.Management.Automation.Verbscommon](/dotnet/api/System.Management.Automation.VerbsCommon) enumeration, and the noun "Proc" to indicate that the cmdlet works on process items.</span></span>

<span data-ttu-id="083a7-117">При именовании командлетов, не используйте следующие символы: #, () {} [] & - / \ $;: "" <> &#124; ?</span><span class="sxs-lookup"><span data-stu-id="083a7-117">When naming cmdlets, do not use any of the following characters: # , () {} [] & - /\ $ ; : " '<> &#124; ?</span></span> <span data-ttu-id="083a7-118">@ \` .</span><span class="sxs-lookup"><span data-stu-id="083a7-118">@ \` .</span></span>

### <a name="choosing-a-noun"></a><span data-ttu-id="083a7-119">Выбор существительное</span><span class="sxs-lookup"><span data-stu-id="083a7-119">Choosing a Noun</span></span>

<span data-ttu-id="083a7-120">Следует выбрать существительное, характерное.</span><span class="sxs-lookup"><span data-stu-id="083a7-120">You should choose a noun that is specific.</span></span> <span data-ttu-id="083a7-121">Лучше всего использовать существительное единственном числе, префикс сокращенную версию имя продукта.</span><span class="sxs-lookup"><span data-stu-id="083a7-121">It is best to use a singular noun prefixed with a shortened version of the product name.</span></span> <span data-ttu-id="083a7-122">Пример командлета этот тип называется "`Get-SQLServer`«.</span><span class="sxs-lookup"><span data-stu-id="083a7-122">An example cmdlet name of this type is "`Get-SQLServer`".</span></span>

### <a name="choosing-a-verb"></a><span data-ttu-id="083a7-123">Выбор команды</span><span class="sxs-lookup"><span data-stu-id="083a7-123">Choosing a Verb</span></span>

<span data-ttu-id="083a7-124">Следует использовать команды из списка утвержденных командлет имен команд.</span><span class="sxs-lookup"><span data-stu-id="083a7-124">You should use a verb from the set of approved cmdlet verb names.</span></span> <span data-ttu-id="083a7-125">Дополнительные сведения о утвержденных командлета, см. в разделе [имен команд командлет](./approved-verbs-for-windows-powershell-commands.md).</span><span class="sxs-lookup"><span data-stu-id="083a7-125">For more information about the approved cmdlet verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

## <a name="defining-the-cmdlet-class"></a><span data-ttu-id="083a7-126">Определение класса командлета</span><span class="sxs-lookup"><span data-stu-id="083a7-126">Defining the Cmdlet Class</span></span>

<span data-ttu-id="083a7-127">После выбора имени командлета, определите класс .NET для реализации командлет.</span><span class="sxs-lookup"><span data-stu-id="083a7-127">Once you have chosen a cmdlet name, define a .NET class to implement the cmdlet.</span></span> <span data-ttu-id="083a7-128">Вот определение класса для этого командлета Get-Proc образца:</span><span class="sxs-lookup"><span data-stu-id="083a7-128">Here is the class definition for this sample Get-Proc cmdlet:</span></span>

```csharp
[Cmdlet(VerbsCommon.Get, "Proc")]
  public class GetProcCommand : Cmdlet
```

```vb
<Cmdlet(VerbsCommon.Get, "Proc")> _
Public Class GetProcCommand
    Inherits Cmdlet
```

<span data-ttu-id="083a7-129">Обратите внимание, что перед определением класса [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) атрибут, с помощью синтаксиса `[Cmdlet(verb, noun, ...)]`, используемое для идентификации этого класса, как командлет.</span><span class="sxs-lookup"><span data-stu-id="083a7-129">Notice that previous to the class definition, the [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) attribute, with the syntax `[Cmdlet(verb, noun, ...)]`, is used to identify this class as a cmdlet.</span></span> <span data-ttu-id="083a7-130">Это единственный обязательный атрибут для всех командлетов, и он позволяет среде выполнения Windows PowerShell для корректного вызова.</span><span class="sxs-lookup"><span data-stu-id="083a7-130">This is the only required attribute for all cmdlets, and it allows the Windows PowerShell runtime to call them correctly.</span></span> <span data-ttu-id="083a7-131">Можно задать атрибут ключевые слова для дальнейшего объявления класса, при необходимости.</span><span class="sxs-lookup"><span data-stu-id="083a7-131">You can set attribute keywords to further declare the class if necessary.</span></span> <span data-ttu-id="083a7-132">Имейте в виду, что объявление атрибута для нашего примера GetProcCommand класса объявляются только имя существительное и команда имена для командлета Get-Proc.</span><span class="sxs-lookup"><span data-stu-id="083a7-132">Be aware that the attribute declaration for our sample GetProcCommand class declares only the noun and verb names for the Get-Proc cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="083a7-133">Для всех классов атрибутов Windows PowerShell ключевые слова, которые можно задать соответствуют свойствам класса атрибута.</span><span class="sxs-lookup"><span data-stu-id="083a7-133">For all Windows PowerShell attribute classes, the keywords that you can set correspond to properties of the attribute class.</span></span>

<span data-ttu-id="083a7-134">При присвоении имени класса командлета, рекомендуется в соответствии с именем командлета в имени класса.</span><span class="sxs-lookup"><span data-stu-id="083a7-134">When naming the class of the cmdlet, it is a good practice to reflect the cmdlet name in the class name.</span></span> <span data-ttu-id="083a7-135">Чтобы сделать это, используйте форму «VerbNounCommand» и замените глагол и существительное, используемый в имени командлета «Глагол» и «Существительное».</span><span class="sxs-lookup"><span data-stu-id="083a7-135">To do this, use the form "VerbNounCommand" and replace "Verb" and "Noun" with the verb and noun used in the cmdlet name.</span></span> <span data-ttu-id="083a7-136">Как показано в предыдущем определение класса, командлет Get-Proc примере определяется класс с именем GetProcCommand, который является производным от [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) базового класса.</span><span class="sxs-lookup"><span data-stu-id="083a7-136">As is shown in the previous class definition, the sample Get-Proc cmdlet defines a class called GetProcCommand, which derives from the [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) base class.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="083a7-137">Если вы хотите определить командлет, который напрямую обращается к среде выполнения Windows PowerShell, класс .NET должен быть производным от [System.Management.Automation.PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) базового класса.</span><span class="sxs-lookup"><span data-stu-id="083a7-137">If you want to define a cmdlet that accesses the Windows PowerShell runtime directly, your .NET class should derive from the [System.Management.Automation.PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) base class.</span></span> <span data-ttu-id="083a7-138">Дополнительные сведения об этом классе см. в разделе [Создание командлета, определяет параметр наборов](./adding-parameter-sets-to-a-cmdlet.md).</span><span class="sxs-lookup"><span data-stu-id="083a7-138">For more information about this class, see [Creating a Cmdlet that Defines Parameter Sets](./adding-parameter-sets-to-a-cmdlet.md).</span></span>

> [!NOTE]
> <span data-ttu-id="083a7-139">Класс для командлета должны быть помечены как открытые.</span><span class="sxs-lookup"><span data-stu-id="083a7-139">The class for a cmdlet must be explicitly marked as public.</span></span> <span data-ttu-id="083a7-140">Классы, которые не помечены как открытые по умолчанию к внутренним и не будет найдена средой выполнения Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="083a7-140">Classes that are not marked as public will default to internal and will not be found by the Windows PowerShell runtime.</span></span>

<span data-ttu-id="083a7-141">Windows PowerShell использует [Microsoft.PowerShell.Commands](/dotnet/api/Microsoft.PowerShell.Commands) пространство имен для классов его командлет.</span><span class="sxs-lookup"><span data-stu-id="083a7-141">Windows PowerShell uses the [Microsoft.PowerShell.Commands](/dotnet/api/Microsoft.PowerShell.Commands) namespace for its cmdlet classes.</span></span> <span data-ttu-id="083a7-142">Рекомендуется поместить командлет классы в пространстве имен команд API пространства имен, например, xxx.PS.Commands.</span><span class="sxs-lookup"><span data-stu-id="083a7-142">It is recommended to place your cmdlet classes in a Commands namespace of your API namespace, for example, xxx.PS.Commands.</span></span>

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="083a7-143">Переопределив метод обработки входных данных</span><span class="sxs-lookup"><span data-stu-id="083a7-143">Overriding an Input Processing Method</span></span>

<span data-ttu-id="083a7-144">[System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) класс предоставляет три метода основной обработки ввода, по крайней мере один из которых необходимо переопределить командлета.</span><span class="sxs-lookup"><span data-stu-id="083a7-144">The [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) class provides three main input processing methods, at least one of which your cmdlet must override.</span></span> <span data-ttu-id="083a7-145">Дополнительные сведения об обработке записей с помощью Windows PowerShell см. в разделе [как Windows PowerShell работает](https://msdn.microsoft.com/en-us/ced30e23-10af-4700-8933-49873bd84d58).</span><span class="sxs-lookup"><span data-stu-id="083a7-145">For more information about how Windows PowerShell processes records, see [How Windows PowerShell Works](https://msdn.microsoft.com/en-us/ced30e23-10af-4700-8933-49873bd84d58).</span></span>

<span data-ttu-id="083a7-146">Для всех типов входных данных среда выполнения Windows PowerShell вызывает [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) , чтобы включить обработку.</span><span class="sxs-lookup"><span data-stu-id="083a7-146">For all types of input, the Windows PowerShell runtime calls [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) to enable processing.</span></span> <span data-ttu-id="083a7-147">Если в командлете необходимо выполнить предварительную обработку или установки, его можно сделать путем переопределения этого метода.</span><span class="sxs-lookup"><span data-stu-id="083a7-147">If your cmdlet must perform some preprocessing or setup, it can do this by overriding this method.</span></span>

> [!NOTE]
> <span data-ttu-id="083a7-148">Windows PowerShell используется термин «запись» для описания набора значений параметров, при выполнении командлета указано.</span><span class="sxs-lookup"><span data-stu-id="083a7-148">Windows PowerShell uses the term "record" to describe the set of parameter values supplied when a cmdlet is called.</span></span>

<span data-ttu-id="083a7-149">Если командлет принимает входные данные конвейера, необходимо переопределить [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) метод и при необходимости [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)метод.</span><span class="sxs-lookup"><span data-stu-id="083a7-149">If your cmdlet accepts pipeline input, it must override the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method, and optionally the [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method.</span></span> <span data-ttu-id="083a7-150">Например, командлет может переопределить оба метода, если он собирает все входные данные с помощью [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) и затем обрабатывает входные данные как единое целое, а не одного элемента за раз, как `Sort-Object` командлет не.</span><span class="sxs-lookup"><span data-stu-id="083a7-150">For example, a cmdlet might override both methods if it gathers all input using [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) and then operates on the input as a whole rather than one element at a time, as the `Sort-Object` cmdlet does.</span></span>

<span data-ttu-id="083a7-151">Если командлет не принимает входные данные конвейера, следует переопределить [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) метод.</span><span class="sxs-lookup"><span data-stu-id="083a7-151">If your cmdlet does not take pipeline input, it should override the [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method.</span></span> <span data-ttu-id="083a7-152">Имейте в виду, что этот метод часто используется вместо [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) когда командлет не может работать с одного элемента за раз, как в случае для сортировки командлета.</span><span class="sxs-lookup"><span data-stu-id="083a7-152">Be aware that this method is frequently used in place of [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) when the cmdlet cannot operate on one element at a time, as is the case for a sorting cmdlet.</span></span>

<span data-ttu-id="083a7-153">Так как этот пример командлета Get-Proc должен получить входные данные конвейера, он переопределяет [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) метода и использует реализации по умолчанию для [ System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) и [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing).</span><span class="sxs-lookup"><span data-stu-id="083a7-153">Because this sample Get-Proc cmdlet must receive pipeline input, it overrides the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method and uses the default implementations for [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) and [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing).</span></span> <span data-ttu-id="083a7-154">[System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) переопределения извлекает процессы и записывает их в командной строке с помощью [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) метод.</span><span class="sxs-lookup"><span data-stu-id="083a7-154">The [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) override retrieves processes and writes them to the command line using the [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) method.</span></span>

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

#### <a name="things-to-remember-about-input-processing"></a><span data-ttu-id="083a7-155">О чем следует помнить о обработки ввода</span><span class="sxs-lookup"><span data-stu-id="083a7-155">Things to Remember About Input Processing</span></span>

- <span data-ttu-id="083a7-156">Источник по умолчанию для входных данных — явные объект (например, строка), указанное пользователем в командной строке.</span><span class="sxs-lookup"><span data-stu-id="083a7-156">The default source for input is an explicit object (for example, a string) provided by the user on the command line.</span></span> <span data-ttu-id="083a7-157">Дополнительные сведения см. в разделе [Создание командлету входные данные командной строки процесс](./adding-parameters-that-process-command-line-input.md).</span><span class="sxs-lookup"><span data-stu-id="083a7-157">For more information, see [Creating a Cmdlet to Process Command Line Input](./adding-parameters-that-process-command-line-input.md).</span></span>

- <span data-ttu-id="083a7-158">Метод обработки входных данных можно также вводить данные из объекта выходных данных вышестоящего командлета в конвейере.</span><span class="sxs-lookup"><span data-stu-id="083a7-158">An input processing method can also receive input from the output object of an upstream cmdlet on the pipeline.</span></span> <span data-ttu-id="083a7-159">Дополнительные сведения см. в разделе [Создание командлету входные данные конвейера процесс](./adding-parameters-that-process-pipeline-input.md).</span><span class="sxs-lookup"><span data-stu-id="083a7-159">For more information, see [Creating a Cmdlet to Process Pipeline Input](./adding-parameters-that-process-pipeline-input.md).</span></span> <span data-ttu-id="083a7-160">Имейте в виду, что командлета можно получать входные данные на основе сочетания командной строки и конвейера источников.</span><span class="sxs-lookup"><span data-stu-id="083a7-160">Be aware that your cmdlet can receive input from a combination of command-line and pipeline sources.</span></span>

- <span data-ttu-id="083a7-161">Командлет подчиненных могут не возвращать в течение длительного времени или вообще не.</span><span class="sxs-lookup"><span data-stu-id="083a7-161">The downstream cmdlet might not return for a long time, or not at all.</span></span> <span data-ttu-id="083a7-162">По этой причине метод командлета обработки входных данных не следует удерживать блокировки во время вызовов [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject), особенно блокировок, для которых область расширяется за пределы экземпляра командлет.</span><span class="sxs-lookup"><span data-stu-id="083a7-162">For that reason, the input processing method in your cmdlet should not hold locks during calls to [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject), especially locks for which the scope extends beyond the cmdlet instance.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="083a7-163">Никогда не должен вызывать командлеты [System.Console.Writeline\*](/dotnet/api/System.Console.WriteLine) или его эквивалент.</span><span class="sxs-lookup"><span data-stu-id="083a7-163">Cmdlets should never call [System.Console.Writeline\*](/dotnet/api/System.Console.WriteLine) or its equivalent.</span></span>

- <span data-ttu-id="083a7-164">Командлет может быть объектные переменные для очистки после завершения обработки (например, в том случае, если он открывает дескриптор файла в [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) метод и сохраняет дескриптор откройте для использования, [ System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)).</span><span class="sxs-lookup"><span data-stu-id="083a7-164">Your cmdlet might have object variables to clean up when it is finished processing (for example, if it opens a file handle in the [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method and keeps the handle open for use by [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)).</span></span> <span data-ttu-id="083a7-165">Важно помнить, что среда выполнения Windows PowerShell не всегда вызывает [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) метод, который следует выполнить очистку объекта.</span><span class="sxs-lookup"><span data-stu-id="083a7-165">It is important to remember that the Windows PowerShell runtime does not always call the [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method, which should perform object cleanup.</span></span>

<span data-ttu-id="083a7-166">Например [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) не может вызываться, если командлет отменяется в середине или если завершающей в любой части командлета возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="083a7-166">For example, [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) might not be called if the cmdlet is canceled midway or if a terminating error occurs in any part of the cmdlet.</span></span> <span data-ttu-id="083a7-167">Таким образом, следует реализовать полный командлет, который требует очистки объектов [System.IDisposable](/dotnet/api/System.IDisposable) шаблону, в том числе метод завершения, таким образом, чтобы среда выполнения может вызвать оба [ System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) и [System.IDisposable.Dispose\*](/dotnet/api/System.IDisposable.Dispose) в конце обработки.</span><span class="sxs-lookup"><span data-stu-id="083a7-167">Therefore, a cmdlet that requires object cleanup should implement the complete [System.IDisposable](/dotnet/api/System.IDisposable) pattern, including the finalizer, so that the runtime can call both [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) and [System.IDisposable.Dispose\*](/dotnet/api/System.IDisposable.Dispose) at the end of processing.</span></span>

## <a name="code-sample"></a><span data-ttu-id="083a7-168">Пример кода</span><span class="sxs-lookup"><span data-stu-id="083a7-168">Code Sample</span></span>

<span data-ttu-id="083a7-169">Для полной C# пример кода, см. в разделе [пример GetProcessSample01](./getprocesssample01-sample.md).</span><span class="sxs-lookup"><span data-stu-id="083a7-169">For the complete C# sample code, see [GetProcessSample01 Sample](./getprocesssample01-sample.md).</span></span>

## <a name="defining-object-types-and-formatting"></a><span data-ttu-id="083a7-170">Определение типов объектов и форматирование</span><span class="sxs-lookup"><span data-stu-id="083a7-170">Defining Object Types and Formatting</span></span>

<span data-ttu-id="083a7-171">Windows PowerShell передает данные между командлетами, используя объекты .NET.</span><span class="sxs-lookup"><span data-stu-id="083a7-171">Windows PowerShell passes information between cmdlets using .NET objects.</span></span> <span data-ttu-id="083a7-172">Следовательно командлета может потребоваться определить его собственного типа, или командлет может потребоваться расширить существующий тип предоставляемые другому командлету.</span><span class="sxs-lookup"><span data-stu-id="083a7-172">Consequently, a cmdlet might need to define its own type, or the cmdlet might need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="083a7-173">Дополнительные сведения о определение новых типов или расширения существующих типов, см. в разделе [расширение типов объектов и форматирование](https://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351).</span><span class="sxs-lookup"><span data-stu-id="083a7-173">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](https://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="083a7-174">Создание командлета</span><span class="sxs-lookup"><span data-stu-id="083a7-174">Building the Cmdlet</span></span>

<span data-ttu-id="083a7-175">После реализации командлета, необходимо зарегистрировать его с помощью Windows PowerShell через оснастку Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="083a7-175">After implementing a cmdlet, you must register it with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="083a7-176">Дополнительные сведения о регистрации командлетов см. в разделе [как регистрация командлетов, поставщиков и ведущих приложений](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).</span><span class="sxs-lookup"><span data-stu-id="083a7-176">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="083a7-177">Тестирование командлет</span><span class="sxs-lookup"><span data-stu-id="083a7-177">Testing the Cmdlet</span></span>

<span data-ttu-id="083a7-178">При командлета был зарегистрирован с помощью Windows PowerShell, его можно проверить, запустив его в командной строке.</span><span class="sxs-lookup"><span data-stu-id="083a7-178">When your cmdlet has been registered with Windows PowerShell, you can test it by running it on the command line.</span></span> <span data-ttu-id="083a7-179">Код для командлета Get-Proc наш пример невелика, но по-прежнему использует среда выполнения Windows PowerShell и существующий объект .NET, который достаточно, чтобы сделать его полезным.</span><span class="sxs-lookup"><span data-stu-id="083a7-179">The code for our sample Get-Proc cmdlet is small, but it still uses the Windows PowerShell runtime and an existing .NET object, which is enough to make it useful.</span></span> <span data-ttu-id="083a7-180">Давайте протестируем его, чтобы лучше понять возможности Get-Proc и использования его выходные данные.</span><span class="sxs-lookup"><span data-stu-id="083a7-180">Let's test it to better understand what Get-Proc can do and how its output can be used.</span></span> <span data-ttu-id="083a7-181">Дополнительные сведения об использовании командлетов из командной строки см. в разделе [Приступая к работе с Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="083a7-181">For more information about using cmdlets from the command line, see the [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span></span>

1. <span data-ttu-id="083a7-182">Запустите Windows PowerShell и получение текущих процессов, запущенных на компьютере.</span><span class="sxs-lookup"><span data-stu-id="083a7-182">Start Windows PowerShell, and get the current processes running on the computer.</span></span>

    ```powershell
    get-proc
    ```

    <span data-ttu-id="083a7-183">Появляется следующий результат.</span><span class="sxs-lookup"><span data-stu-id="083a7-183">The following output appears.</span></span>

    ```output
    Handles  NPM(K)  PM(K)  WS(K)  VS(M)  CPU(s)  Id   ProcessName
    -------  ------  -----  -----  -----  ------  --   ----------
    254      7       7664   12048  66     173.75  1200  QCTRAY
    32       2       1372   2628   31       0.04  1860  DLG
    271      6       1216   3688   33       0.03  3816  lg
    27       2       560    1920   24       0.01  1768  TpScrex
    ...
    ```

2. <span data-ttu-id="083a7-184">Присвоить переменной результаты для простоты управления.</span><span class="sxs-lookup"><span data-stu-id="083a7-184">Assign a variable to the cmdlet results for easier manipulation.</span></span>

    ```powershell
    $p=get-proc
    ```

3. <span data-ttu-id="083a7-185">Получите число процессов.</span><span class="sxs-lookup"><span data-stu-id="083a7-185">Get the number of processes.</span></span>

    ```powershell
    $p.length
    ```

    <span data-ttu-id="083a7-186">Появляется следующий результат.</span><span class="sxs-lookup"><span data-stu-id="083a7-186">The following output appears.</span></span>

    ```output
    63
    ```

4. <span data-ttu-id="083a7-187">Получение определенного процесса.</span><span class="sxs-lookup"><span data-stu-id="083a7-187">Retrieve a specific process.</span></span>

    ```powershell
    $p[6]
    ```

    <span data-ttu-id="083a7-188">Появляется следующий результат.</span><span class="sxs-lookup"><span data-stu-id="083a7-188">The following output appears.</span></span>

    ```output
    Handles  NPM(K)  PM(K)  WS(K)  VS(M)  CPU(s)  Id    ProcessName
    -------  ------  -----  -----  -----  ------  --    -----------
    1033     3       2400   3336   35     0.53    1588  rundll32
    ```

5. <span data-ttu-id="083a7-189">Получите время начала этого процесса.</span><span class="sxs-lookup"><span data-stu-id="083a7-189">Get the start time of this process.</span></span>

    ```powershell
    $p[6].starttime
    ```

    <span data-ttu-id="083a7-190">Появляется следующий результат.</span><span class="sxs-lookup"><span data-stu-id="083a7-190">The following output appears.</span></span>

    ```output
    Tuesday, July 26, 2005 9:34:15 AM
    ```

    ```powershell
    $p[6].starttime.dayofyear
    ```

    ```output
    207
    ```

6. <span data-ttu-id="083a7-191">Возвращает процессы, для которых значение счетчика дескрипторов больше 500 и отсортировать результаты.</span><span class="sxs-lookup"><span data-stu-id="083a7-191">Get the processes for which the handle count is greater than 500, and sort the result.</span></span>

    ```powershell
    $p | Where-Object {$_.HandleCount -gt 500 } | Sort-Object HandleCount
    ```

    <span data-ttu-id="083a7-192">Появляется следующий результат.</span><span class="sxs-lookup"><span data-stu-id="083a7-192">The following output appears.</span></span>

    ```output
    Handles  NPM(K)  PM(K)  WS(K)  VS(M)  CPU(s)  Id   ProcessName
    -------  ------  -----  -----  -----  ------  --   ----------
    568      14      2164   4972   39     5.55    824  svchost
    716       7      2080   5332   28    25.38    468  csrss
    761      21      33060  56608  440  393.56    3300 WINWORD
    791      71      7412   4540   59     3.31    492  winlogon
    ...
    ```

7. <span data-ttu-id="083a7-193">Используйте `Get-Member` командлет, чтобы получить список свойств, доступных для каждого процесса.</span><span class="sxs-lookup"><span data-stu-id="083a7-193">Use the `Get-Member` cmdlet to list the properties available for each process.</span></span>

    ```powershell
    $p | Get-Member -MemberType property
    ```

    ```output
        TypeName: System.Diagnostics.Process
    ```

    <span data-ttu-id="083a7-194">Появляется следующий результат.</span><span class="sxs-lookup"><span data-stu-id="083a7-194">The following output appears.</span></span>

    ```output
    Name                     MemberType Definition
    ----                     ---------- ----------
    BasePriority             Property   System.Int32 BasePriority {get;}
    Container                Property   System.ComponentModel.IContainer Conta...
    EnableRaisingEvents      Property   System.Boolean EnableRaisingEvents {ge...
    ...
    ```

## <a name="see-also"></a><span data-ttu-id="083a7-195">См. также</span><span class="sxs-lookup"><span data-stu-id="083a7-195">See Also</span></span>

[<span data-ttu-id="083a7-196">Создание командлета для обработки входных данных командной строки</span><span class="sxs-lookup"><span data-stu-id="083a7-196">Creating a Cmdlet to Process Command Line Input</span></span>](./adding-parameters-that-process-command-line-input.md)

[<span data-ttu-id="083a7-197">Создание командлета для обработки входных данных конвейера</span><span class="sxs-lookup"><span data-stu-id="083a7-197">Creating a Cmdlet to Process Pipeline Input</span></span>](./adding-parameters-that-process-pipeline-input.md)

[<span data-ttu-id="083a7-198">Как создать командлет Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="083a7-198">How to Create a Windows PowerShell Cmdlet</span></span>](https://msdn.microsoft.com/en-us/0d721742-c849-4d0d-964f-78ddd9cd258c)

[<span data-ttu-id="083a7-199">Расширение типов объектов и форматирование</span><span class="sxs-lookup"><span data-stu-id="083a7-199">Extending Object Types and Formatting</span></span>](https://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[<span data-ttu-id="083a7-200">Как работает Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="083a7-200">How Windows PowerShell Works</span></span>](https://msdn.microsoft.com/en-us/ced30e23-10af-4700-8933-49873bd84d58)

[<span data-ttu-id="083a7-201">Регистрация командлетов, поставщиков и ведущих приложений</span><span class="sxs-lookup"><span data-stu-id="083a7-201">How to Register Cmdlets, Providers, and Host Applications</span></span>](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[<span data-ttu-id="083a7-202">Справочник по Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="083a7-202">Windows PowerShell Reference</span></span>](../windows-powershell-reference.md)

[<span data-ttu-id="083a7-203">Примеры командлетов</span><span class="sxs-lookup"><span data-stu-id="083a7-203">Cmdlet Samples</span></span>](./cmdlet-samples.md)