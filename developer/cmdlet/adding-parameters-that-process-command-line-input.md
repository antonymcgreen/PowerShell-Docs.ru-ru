---
title: Добавление параметров, которые обрабатывают данные в командной строке | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- cmdlets [PowerShell Programmer's Guide], parameters
- Get-Proc cmdlet [PowerShell Programmer's Guide]
- cmdlets [PowerShell Programmer's Guide], command line input
- command line input [PowerShell Programmer's Guide]
- parameters [PowerShell Programmer's Guide]
- cmdlets [PowerShell Programmer's Guide], creating
ms.assetid: da0b32f8-7b51-440e-a061-3177b5759e0e
caps.latest.revision: 9
ms.openlocfilehash: c9ad84c5bcb6826fcf51db9a1f1a578a65a1f275
ms.sourcegitcommit: 01b81317029b28dd9b61d167045fd31f1ec7bc06
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2019
ms.locfileid: "65854952"
---
# <a name="adding-parameters-that-process-command-line-input"></a><span data-ttu-id="73c32-102">Добавление параметров для обработки входных данных команды</span><span class="sxs-lookup"><span data-stu-id="73c32-102">Adding Parameters That Process Command-Line Input</span></span>

<span data-ttu-id="73c32-103">Один источник входных данных для командлета приведен пример командной строки.</span><span class="sxs-lookup"><span data-stu-id="73c32-103">One source of input for a cmdlet is the command line.</span></span> <span data-ttu-id="73c32-104">В этом разделе описывается добавление параметра **Get-Proc** командлет (который описан в [Создание свой первый командлет](./creating-a-cmdlet-without-parameters.md)), чтобы командлет может обрабатывать входные данные с локального компьютера, на основании явных объекты передаются в командлет.</span><span class="sxs-lookup"><span data-stu-id="73c32-104">This topic describes how to add a parameter to the **Get-Proc** cmdlet (which is described in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md)) so that the cmdlet can process input from the local computer based on explicit objects passed to the cmdlet.</span></span> <span data-ttu-id="73c32-105">**Get-Proc** командлет описанные здесь извлекает процессы, на основе их имен и затем отображает сведения о процессах в командной строке.</span><span class="sxs-lookup"><span data-stu-id="73c32-105">The **Get-Proc** cmdlet described here retrieves processes based on their names, and then displays information about the processes at a command prompt.</span></span>

## <a name="defining-the-cmdlet-class"></a><span data-ttu-id="73c32-106">Определение класса командлета</span><span class="sxs-lookup"><span data-stu-id="73c32-106">Defining the Cmdlet Class</span></span>

<span data-ttu-id="73c32-107">Первым этапом создания командлетов является названии командлета и объявление класса .NET Framework, который реализует командлет.</span><span class="sxs-lookup"><span data-stu-id="73c32-107">The first step in cmdlet creation is cmdlet naming and the declaration of the .NET Framework class that implements the cmdlet.</span></span> <span data-ttu-id="73c32-108">Этот командлет извлекает сведения о процессе, чтобы имя команды, выбираем «Get».</span><span class="sxs-lookup"><span data-stu-id="73c32-108">This cmdlet retrieves process information, so the verb name chosen here is "Get."</span></span> <span data-ttu-id="73c32-109">(Почти любого вида командлет, который поддерживает получение сведений о может обрабатывать входные данные командной строки). Дополнительные сведения о командлет утвержденные глаголы, см. в разделе [имен команд командлет](./approved-verbs-for-windows-powershell-commands.md).</span><span class="sxs-lookup"><span data-stu-id="73c32-109">(Almost any sort of cmdlet that is capable of retrieving information can process command-line input.) For more information about approved cmdlet verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="73c32-110">Вот объявление класса для **Get-Proc** командлета.</span><span class="sxs-lookup"><span data-stu-id="73c32-110">Here's the class declaration for the **Get-Proc** cmdlet.</span></span> <span data-ttu-id="73c32-111">Сведения об этом определении приведены в [Создание свой первый командлет](./creating-a-cmdlet-without-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="73c32-111">Details about this definition are provided in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md).</span></span>

```csharp
[Cmdlet(VerbsCommon.Get, "proc")]
public class GetProcCommand: Cmdlet
```

```vb
<Cmdlet(VerbsCommon.Get, "Proc")> _
Public Class GetProcCommand
    Inherits Cmdlet
```

## <a name="declaring-parameters"></a><span data-ttu-id="73c32-112">Объявление параметров</span><span class="sxs-lookup"><span data-stu-id="73c32-112">Declaring Parameters</span></span>

<span data-ttu-id="73c32-113">Параметр командлета позволяет пользователю предоставлять командлету входные данные.</span><span class="sxs-lookup"><span data-stu-id="73c32-113">A cmdlet parameter enables the user to provide input to the cmdlet.</span></span> <span data-ttu-id="73c32-114">В следующем примере **Get-Proc** и `Get-Member` являются именами конвейерных командлеты и `MemberType` является параметром для `Get-Member` командлета.</span><span class="sxs-lookup"><span data-stu-id="73c32-114">In the following example, **Get-Proc** and `Get-Member` are the names of pipelined cmdlets, and `MemberType` is a parameter for the `Get-Member` cmdlet.</span></span> <span data-ttu-id="73c32-115">Он имеет аргумент «свойство».</span><span class="sxs-lookup"><span data-stu-id="73c32-115">The parameter has the argument "property."</span></span>

<span data-ttu-id="73c32-116">**PS> get-proc ; `get-member` -membertype property**</span><span class="sxs-lookup"><span data-stu-id="73c32-116">**PS> get-proc ; `get-member` -membertype property**</span></span>

<span data-ttu-id="73c32-117">Чтобы объявить параметры командлета, необходимо сначала определить свойства, которые представляют параметры.</span><span class="sxs-lookup"><span data-stu-id="73c32-117">To declare parameters for a cmdlet, you must first define the properties that represent the parameters.</span></span> <span data-ttu-id="73c32-118">В **Get-Proc** командлета, единственным параметром является `Name`, который в данном случае представляет имя объекта процесса .NET Framework для извлечения.</span><span class="sxs-lookup"><span data-stu-id="73c32-118">In the **Get-Proc** cmdlet, the only parameter is `Name`, which in this case represents the name of the .NET Framework process object to retrieve.</span></span> <span data-ttu-id="73c32-119">Таким образом в классе командлета определяет свойство строкового типа, чтобы принять массив имен.</span><span class="sxs-lookup"><span data-stu-id="73c32-119">Therefore, the cmdlet class defines a property of type string to accept an array of names.</span></span>

<span data-ttu-id="73c32-120">Ниже приведено объявление параметра для `Name` параметр **Get-Proc** командлета.</span><span class="sxs-lookup"><span data-stu-id="73c32-120">Here's the parameter declaration for the `Name` parameter of the **Get-Proc** cmdlet.</span></span>

```csharp
/// <summary>
/// Specify the cmdlet Name parameter.
/// </summary>
  [Parameter(Position = 0)]
  [ValidateNotNullOrEmpty]
  public string[] Name
  {
    get { return processNames; }
    set { processNames = value; }
  }
  private string[] processNames;

  #endregion Parameters
```

```vb
<Parameter(Position:=0), ValidateNotNullOrEmpty()> _
Public Property Name() As String()
    Get
        Return processNames
    End Get

    Set(ByVal value As String())
        processNames = value
    End Set

End Property
```

<span data-ttu-id="73c32-121">Сообщать среде выполнения Windows PowerShell, это свойство является `Name` параметра [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) атрибут добавляется к определению свойства.</span><span class="sxs-lookup"><span data-stu-id="73c32-121">To inform the Windows PowerShell runtime that this property is the `Name` parameter, a [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute is added to the property definition.</span></span> <span data-ttu-id="73c32-122">Базовый синтаксис для объявления этого атрибута `[Parameter()]`.</span><span class="sxs-lookup"><span data-stu-id="73c32-122">The basic syntax for declaring this attribute is `[Parameter()]`.</span></span>

> [!NOTE]
> <span data-ttu-id="73c32-123">Параметр должен быть явно помечен как общедоступный.</span><span class="sxs-lookup"><span data-stu-id="73c32-123">A parameter must be explicitly marked as public.</span></span> <span data-ttu-id="73c32-124">Параметры, которые не помечены как открытые, по умолчанию внутренний и не найдены средой выполнения Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="73c32-124">Parameters that are not marked as public default to internal and are not found by the Windows PowerShell runtime.</span></span>

<span data-ttu-id="73c32-125">Этот командлет использует массив строк для `Name` параметра.</span><span class="sxs-lookup"><span data-stu-id="73c32-125">This cmdlet uses an array of strings for the `Name` parameter.</span></span> <span data-ttu-id="73c32-126">Если это возможно в командлет необходимо также определить параметры как массив, так как при этом командлет, чтобы принимать более одного элемента.</span><span class="sxs-lookup"><span data-stu-id="73c32-126">If possible, your cmdlet should also define a parameter as an array, because this allows the cmdlet to accept more than one item.</span></span>

#### <a name="things-to-remember-about-parameter-definitions"></a><span data-ttu-id="73c32-127">О чем следует помнить об определениях параметров</span><span class="sxs-lookup"><span data-stu-id="73c32-127">Things to Remember About Parameter Definitions</span></span>

- <span data-ttu-id="73c32-128">Предопределенные Windows PowerShell параметров имена и типы данных следует повторно использовать настолько, насколько возможно обеспечить совместимость с помощью командлетов Windows PowerShell командлет.</span><span class="sxs-lookup"><span data-stu-id="73c32-128">Predefined Windows PowerShell parameter names and data types should be reused as much as possible to ensure that your cmdlet is compatible with Windows PowerShell cmdlets.</span></span> <span data-ttu-id="73c32-129">Например, если все командлеты используют предопределенный `Id` имя параметра для идентификации ресурса, пользователю придется легко понимать значение параметра, независимо от того, какой командлет, они используют.</span><span class="sxs-lookup"><span data-stu-id="73c32-129">For example, if all cmdlets use the predefined `Id` parameter name to identify a resource, user will easily understand the meaning of the parameter, regardless of what cmdlet they are using.</span></span> <span data-ttu-id="73c32-130">По сути параметр имена следуют тем же правилам, которые используются для имен переменных в общеязыковой среде выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="73c32-130">Basically, parameter names follow the same rules as those used for variable names in the common language runtime (CLR).</span></span> <span data-ttu-id="73c32-131">Дополнительные сведения об именах параметров см. в разделе [имена параметров командлета](https://msdn.microsoft.com/en-us/c4500737-0a05-4d01-911b-394424c65bfb).</span><span class="sxs-lookup"><span data-stu-id="73c32-131">For more information about parameter naming, see [Cmdlet Parameter Names](https://msdn.microsoft.com/en-us/c4500737-0a05-4d01-911b-394424c65bfb).</span></span>

- <span data-ttu-id="73c32-132">Windows PowerShell зарезервировано несколько имен параметров для обеспечения согласованного пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="73c32-132">Windows PowerShell reserves a few parameter names to provide a consistent user experience.</span></span> <span data-ttu-id="73c32-133">Не используйте эти имена параметров: `WhatIf`, `Confirm`, `Verbose`, `Debug`, `Warn`, `ErrorAction`, `ErrorVariable`, `OutVariable`, и `OutBuffer`.</span><span class="sxs-lookup"><span data-stu-id="73c32-133">Do not use these parameter names: `WhatIf`, `Confirm`, `Verbose`, `Debug`, `Warn`, `ErrorAction`, `ErrorVariable`, `OutVariable`, and `OutBuffer`.</span></span> <span data-ttu-id="73c32-134">Кроме того, зарезервированы следующие псевдонимы для этих имен параметров: `vb`, `db`, `ea`, `ev`, `ov`, и `ob`.</span><span class="sxs-lookup"><span data-stu-id="73c32-134">Additionally, the following aliases for these parameter names are reserved: `vb`, `db`, `ea`, `ev`, `ov`, and `ob`.</span></span>

- <span data-ttu-id="73c32-135">`Name` — Это имя простых и распространенных параметров, рекомендуется использовать в командлеты.</span><span class="sxs-lookup"><span data-stu-id="73c32-135">`Name` is a simple and common parameter name, recommended for use in your cmdlets.</span></span> <span data-ttu-id="73c32-136">Лучше, можно выбрать любое имя параметра следующим образом, чем сложные имя, которое является уникальным для конкретного командлета и плохо запоминаются.</span><span class="sxs-lookup"><span data-stu-id="73c32-136">It is better to choose a parameter name like this than a complex name that is unique to a specific cmdlet and hard to remember.</span></span>

- <span data-ttu-id="73c32-137">Параметры не учитывается в Windows PowerShell, несмотря на то, что по умолчанию оболочка сохраняет регистр.</span><span class="sxs-lookup"><span data-stu-id="73c32-137">Parameters are case-insensitive in Windows PowerShell, although by default the shell preserves case.</span></span> <span data-ttu-id="73c32-138">Учет регистра в аргументы зависит от работы командлета.</span><span class="sxs-lookup"><span data-stu-id="73c32-138">Case-sensitivity of the arguments depends on the operation of the cmdlet.</span></span> <span data-ttu-id="73c32-139">Аргументы передаются в параметр, как указано в командной строке.</span><span class="sxs-lookup"><span data-stu-id="73c32-139">Arguments are passed to a parameter as specified at the command line.</span></span>

- <span data-ttu-id="73c32-140">Примеры других объявлений параметров, см. в разделе [параметры командлета](./cmdlet-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="73c32-140">For examples of other parameter declarations, see [Cmdlet Parameters](./cmdlet-parameters.md).</span></span>

## <a name="declaring-parameters-as-positional-or-named"></a><span data-ttu-id="73c32-141">Объявление параметров как позиционные или именованные</span><span class="sxs-lookup"><span data-stu-id="73c32-141">Declaring Parameters as Positional or Named</span></span>

<span data-ttu-id="73c32-142">Командлет необходимо задать каждый параметр как позиционные или именованные параметра.</span><span class="sxs-lookup"><span data-stu-id="73c32-142">A cmdlet must set each parameter as either a positional or named parameter.</span></span> <span data-ttu-id="73c32-143">Оба вида параметров аргументов один, несколько аргументов, разделенных запятыми, логические параметры.</span><span class="sxs-lookup"><span data-stu-id="73c32-143">Both kinds of parameters accept single arguments, multiple arguments separated by commas, and Boolean settings.</span></span> <span data-ttu-id="73c32-144">Логический параметр, который также называется *переключения*, обрабатывает только логические параметры.</span><span class="sxs-lookup"><span data-stu-id="73c32-144">A Boolean parameter, also called a *switch*, handles only Boolean settings.</span></span> <span data-ttu-id="73c32-145">Параметр используется для определения наличия параметра.</span><span class="sxs-lookup"><span data-stu-id="73c32-145">The switch is used to determine the presence of the parameter.</span></span> <span data-ttu-id="73c32-146">Рекомендуемое значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="73c32-146">The recommended default is `false`.</span></span>

<span data-ttu-id="73c32-147">Образец **Get-Proc** командлет определяет `Name` параметра в виде позиционным с позиции 0.</span><span class="sxs-lookup"><span data-stu-id="73c32-147">The sample **Get-Proc** cmdlet defines the `Name` parameter as a positional parameter with position 0.</span></span> <span data-ttu-id="73c32-148">Это означает, что для этого параметра автоматически вставляется первый аргумент, который пользователь вводит в командной строке.</span><span class="sxs-lookup"><span data-stu-id="73c32-148">This means that the first argument the user enters on the command line is automatically inserted for this parameter.</span></span> <span data-ttu-id="73c32-149">Если вы хотите определить именованный параметр, который пользователь должен указать имя параметра, из командной строки, оставьте `Position` ключевое слово из объявления атрибута.</span><span class="sxs-lookup"><span data-stu-id="73c32-149">If you want to define a named parameter, for which the user must specify the parameter name from the command line, leave the `Position` keyword out of the attribute declaration.</span></span>

> [!NOTE]
> <span data-ttu-id="73c32-150">Если параметры должны быть именованными, мы не рекомендуем, чтобы пользователям не придется ввести имя параметра сделать позиционные наиболее часто используемые параметры.</span><span class="sxs-lookup"><span data-stu-id="73c32-150">Unless parameters must be named, we recommend that you make the most-used parameters positional so that users will not have to type the parameter name.</span></span>

## <a name="declaring-parameters-as-mandatory-or-optional"></a><span data-ttu-id="73c32-151">Объявление параметров как обязательные или необязательные</span><span class="sxs-lookup"><span data-stu-id="73c32-151">Declaring Parameters as Mandatory or Optional</span></span>

<span data-ttu-id="73c32-152">Командлет необходимо задать каждый параметр как необязательный или обязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="73c32-152">A cmdlet must set each parameter as either an optional or a mandatory parameter.</span></span> <span data-ttu-id="73c32-153">В образце **Get-Proc** командлета, `Name` параметр определен как необязательно, так как `Mandatory` ключевое слово не включен в объявление атрибута.</span><span class="sxs-lookup"><span data-stu-id="73c32-153">In the sample **Get-Proc** cmdlet, the `Name` parameter is defined as optional because the `Mandatory` keyword is not set in the attribute declaration.</span></span>

## <a name="supporting-parameter-validation"></a><span data-ttu-id="73c32-154">Поддержка проверки параметров</span><span class="sxs-lookup"><span data-stu-id="73c32-154">Supporting Parameter Validation</span></span>

<span data-ttu-id="73c32-155">Образец **Get-Proc** командлет добавляет атрибут проверки входных данных, [System.Management.Automation.Validatenotnulloremptyattribute](/dotnet/api/System.Management.Automation.ValidateNotNullOrEmptyAttribute), `Name` параметр для включения проверки, входные данные не является ни `null` или пустым.</span><span class="sxs-lookup"><span data-stu-id="73c32-155">The sample **Get-Proc** cmdlet adds an input validation attribute, [System.Management.Automation.Validatenotnulloremptyattribute](/dotnet/api/System.Management.Automation.ValidateNotNullOrEmptyAttribute), to the `Name` parameter to enable validation that the input is neither `null` nor empty.</span></span> <span data-ttu-id="73c32-156">Этот атрибут является одним из нескольких атрибутов проверки, предоставляемые Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="73c32-156">This attribute is one of several validation attributes provided by Windows PowerShell.</span></span> <span data-ttu-id="73c32-157">Примеры других атрибутов проверки, см. в разделе [проверка ввода параметра](./validating-parameter-input.md).</span><span class="sxs-lookup"><span data-stu-id="73c32-157">For examples of other validation attributes, see [Validating Parameter Input](./validating-parameter-input.md).</span></span>

```
[Parameter(Position = 0)]
[ValidateNotNullOrEmpty]
public string[] Name
```

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="73c32-158">Переопределив метод обработки входных данных</span><span class="sxs-lookup"><span data-stu-id="73c32-158">Overriding an Input Processing Method</span></span>

<span data-ttu-id="73c32-159">Если для обработки командной строки входных данных командлета, его необходимо переопределить соответствующие методы обработки ввода.</span><span class="sxs-lookup"><span data-stu-id="73c32-159">If your cmdlet is to handle command-line input, it must override the appropriate input processing methods.</span></span> <span data-ttu-id="73c32-160">Методы базовую обработку ввода, использованные в [Создание свой первый командлет](./creating-a-cmdlet-without-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="73c32-160">The basic input processing methods are introduced in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md).</span></span>

<span data-ttu-id="73c32-161">**Get-Proc** командлета переопределяет [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) метод для обработки `Name` входные параметры, предоставляемые пользователем или сценарий.</span><span class="sxs-lookup"><span data-stu-id="73c32-161">The **Get-Proc** cmdlet overrides the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method to handle the `Name` parameter input provided by the user or a script.</span></span> <span data-ttu-id="73c32-162">Этот метод возвращает процессы для каждого имени запрошенного процесса или для всех процессов, если имя не указано.</span><span class="sxs-lookup"><span data-stu-id="73c32-162">This method gets the processes for each requested process name, or all for processes if no name is provided.</span></span> <span data-ttu-id="73c32-163">Обратите внимание, что в [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord), вызов [System.Management.Automation.Cmdlet.WriteObject%28System.Object%2CSystem.Boolean%29](/dotnet/api/system.management.automation.cmdlet.writeobject?view=powershellsdk-1.1.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) выходные данные механизм для отправки выходных данных объекты в конвейер.</span><span class="sxs-lookup"><span data-stu-id="73c32-163">Notice that in [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord), the call to [System.Management.Automation.Cmdlet.WriteObject%28System.Object%2CSystem.Boolean%29](/dotnet/api/system.management.automation.cmdlet.writeobject?view=powershellsdk-1.1.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) is the output mechanism for sending output objects to the pipeline.</span></span> <span data-ttu-id="73c32-164">Второй параметр этой вызов `enumerateCollection`, имеет значение `true` сообщать среде выполнения Windows PowerShell для перечисления выходной массив объектов процессов и один процесс записи за раз в командную строку.</span><span class="sxs-lookup"><span data-stu-id="73c32-164">The second parameter of this call, `enumerateCollection`, is set to `true` to inform the Windows PowerShell runtime to enumerate the output array of process objects and write one process at a time to the command line.</span></span>

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
    }
  }
}
```

```vb
Protected Overrides Sub ProcessRecord()

    '/ If no process names are passed to the cmdlet, get all processes.
    If processNames Is Nothing Then
        Dim processes As Process()
        processes = Process.GetProcesses()
    End If

    '/ If process names are specified, write the processes to the
    '/ pipeline to display them or make them available to the next cmdlet.

    For Each name As String In processNames
        '/ The second parameter of this call tells PowerShell to enumerate the
        '/ array, and send one process at a time to the pipeline.
        WriteObject(Process.GetProcessesByName(name), True)
    Next

End Sub 'ProcessRecord
```

## <a name="code-sample"></a><span data-ttu-id="73c32-165">Пример кода</span><span class="sxs-lookup"><span data-stu-id="73c32-165">Code Sample</span></span>

<span data-ttu-id="73c32-166">Для полной C# пример кода, см. в разделе [пример GetProcessSample02](./getprocesssample02-sample.md).</span><span class="sxs-lookup"><span data-stu-id="73c32-166">For the complete C# sample code, see [GetProcessSample02 Sample](./getprocesssample02-sample.md).</span></span>

## <a name="defining-object-types-and-formatting"></a><span data-ttu-id="73c32-167">Определение типов объектов и форматирование</span><span class="sxs-lookup"><span data-stu-id="73c32-167">Defining Object Types and Formatting</span></span>

<span data-ttu-id="73c32-168">Windows PowerShell передает данные между командлетами, используя объекты .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="73c32-168">Windows PowerShell passes information between cmdlets by using .NET Framework objects.</span></span> <span data-ttu-id="73c32-169">Следовательно командлет может потребоваться определить его собственного типа, или командлета может потребоваться расширить существующий тип предоставляемые другому командлету.</span><span class="sxs-lookup"><span data-stu-id="73c32-169">Consequently, a cmdlet might need to define its own type, or a cmdlet might need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="73c32-170">Дополнительные сведения о определение новых типов или расширения существующих типов, см. в разделе [расширение типов объектов и форматирование](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351).</span><span class="sxs-lookup"><span data-stu-id="73c32-170">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="73c32-171">Создание командлета</span><span class="sxs-lookup"><span data-stu-id="73c32-171">Building the Cmdlet</span></span>

<span data-ttu-id="73c32-172">После реализации командлета, необходимо зарегистрировать его с помощью Windows PowerShell с помощью оснастки Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="73c32-172">After you implement a cmdlet, you must register it with Windows PowerShell by using a Windows PowerShell snap-in.</span></span> <span data-ttu-id="73c32-173">Дополнительные сведения о регистрации командлетов см. в разделе [как регистрация командлетов, поставщиков и ведущих приложений](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).</span><span class="sxs-lookup"><span data-stu-id="73c32-173">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="73c32-174">Тестирование командлет</span><span class="sxs-lookup"><span data-stu-id="73c32-174">Testing the Cmdlet</span></span>

<span data-ttu-id="73c32-175">При регистрации командлета Windows PowerShell, его можно проверить, запустив его в командной строке.</span><span class="sxs-lookup"><span data-stu-id="73c32-175">When your cmdlet is registered with Windows PowerShell, you can test it by running it on the command line.</span></span> <span data-ttu-id="73c32-176">Ниже приведены два способа тестировать код для примера командлета.</span><span class="sxs-lookup"><span data-stu-id="73c32-176">Here are two ways to test the code for the sample cmdlet.</span></span> <span data-ttu-id="73c32-177">Дополнительные сведения об использовании командлетов из командной строки см. в разделе [Приступая к работе с Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="73c32-177">For more information about using cmdlets from the command line, see [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span></span>

- <span data-ttu-id="73c32-178">В командной строке Windows PowerShell используйте следующую команду, чтобы получить список процесс Internet Explorer, который называется «IEXPLORE.»</span><span class="sxs-lookup"><span data-stu-id="73c32-178">At the Windows PowerShell prompt, use the following command to list the Internet Explorer process, which is named "IEXPLORE."</span></span>

    ```powershell
    PS> get-proc -name iexplore
    ```

<span data-ttu-id="73c32-179">Появляется следующий результат.</span><span class="sxs-lookup"><span data-stu-id="73c32-179">The following output appears.</span></span>

    ```
    Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)   Id   ProcessName
    -------  ------  -----   -----  -----   ------ --   -----------
        354      11  10036   18992    85   0.67   3284   iexplore
    ```

- <span data-ttu-id="73c32-180">Чтобы получить список процессов Internet Explorer, Outlook и Блокнот, с именем «IEXPLORE», «OUTLOOK» и «Блокнот», используйте следующую команду.</span><span class="sxs-lookup"><span data-stu-id="73c32-180">To list the Internet Explorer, Outlook, and Notepad processes named "IEXPLORE," "OUTLOOK," and "NOTEPAD," use the following command.</span></span> <span data-ttu-id="73c32-181">При наличии нескольких процессов, то они отображаются.</span><span class="sxs-lookup"><span data-stu-id="73c32-181">If there are multiple processes, all of them are displayed.</span></span>

    ```powershell
    PS> get-proc -name iexplore, outlook, notepad
    ```

<span data-ttu-id="73c32-182">Появляется следующий результат.</span><span class="sxs-lookup"><span data-stu-id="73c32-182">The following output appears.</span></span>

    ```
    Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)   Id   ProcessName
    -------  ------  -----   -----  -----  ------   --    -----------
        732      21  24696    5000    138   2.25  2288   iexplore
        715      19  20556   14116    136   1.78  3860   iexplore
       3917      62  74096   58112    468 191.56  1848   OUTLOOK
         39       2   1024    3280     30   0.09  1444   notepad
         39       2   1024     356     30   0.08  3396   notepad
    ```

## <a name="see-also"></a><span data-ttu-id="73c32-183">См. также</span><span class="sxs-lookup"><span data-stu-id="73c32-183">See Also</span></span>

[<span data-ttu-id="73c32-184">Добавление параметров конвейера обработки входных данных</span><span class="sxs-lookup"><span data-stu-id="73c32-184">Adding Parameters that Process Pipeline Input</span></span>](./adding-parameters-that-process-pipeline-input.md)

[<span data-ttu-id="73c32-185">Создайте свой первый командлет</span><span class="sxs-lookup"><span data-stu-id="73c32-185">Creating Your First Cmdlet</span></span>](./creating-a-cmdlet-without-parameters.md)

[<span data-ttu-id="73c32-186">Расширение типов объектов и форматирование</span><span class="sxs-lookup"><span data-stu-id="73c32-186">Extending Object Types and Formatting</span></span>](http://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[<span data-ttu-id="73c32-187">Регистрация командлетов, поставщиков и ведущих приложений</span><span class="sxs-lookup"><span data-stu-id="73c32-187">How to Register Cmdlets, Providers, and Host Applications</span></span>](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[<span data-ttu-id="73c32-188">Справочник по Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="73c32-188">Windows PowerShell Reference</span></span>](../windows-powershell-reference.md)

[<span data-ttu-id="73c32-189">Примеры командлетов</span><span class="sxs-lookup"><span data-stu-id="73c32-189">Cmdlet Samples</span></span>](./cmdlet-samples.md)
