---
title: Добавление параметров, обрабатывающих входные данные командной строки | Документация Майкрософт
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
ms.openlocfilehash: 7db93af33717dc4802ed915793f6cd570cfb48f6
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364633"
---
# <a name="adding-parameters-that-process-command-line-input"></a><span data-ttu-id="db0ff-102">Добавление параметров для обработки входных данных команды</span><span class="sxs-lookup"><span data-stu-id="db0ff-102">Adding Parameters That Process Command-Line Input</span></span>

<span data-ttu-id="db0ff-103">Одним из источников входных данных для командлета является Командная строка.</span><span class="sxs-lookup"><span data-stu-id="db0ff-103">One source of input for a cmdlet is the command line.</span></span> <span data-ttu-id="db0ff-104">В этом разделе описывается добавление параметра в командлет **Get-proc** (описывается в разделе [Создание первого командлета](./creating-a-cmdlet-without-parameters.md)), чтобы командлет мог обрабатывать входные данные с локального компьютера на основе явных объектов, переданных в командлет.</span><span class="sxs-lookup"><span data-stu-id="db0ff-104">This topic describes how to add a parameter to the **Get-Proc** cmdlet (which is described in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md)) so that the cmdlet can process input from the local computer based on explicit objects passed to the cmdlet.</span></span> <span data-ttu-id="db0ff-105">Описанный здесь командлет **Get-proc** извлекает процессы на основе их имен, а затем отображает сведения о процессах в командной строке.</span><span class="sxs-lookup"><span data-stu-id="db0ff-105">The **Get-Proc** cmdlet described here retrieves processes based on their names, and then displays information about the processes at a command prompt.</span></span>

## <a name="defining-the-cmdlet-class"></a><span data-ttu-id="db0ff-106">Определение класса командлета</span><span class="sxs-lookup"><span data-stu-id="db0ff-106">Defining the Cmdlet Class</span></span>

<span data-ttu-id="db0ff-107">Первым шагом при создании командлета является именование командлетов и объявление класса .NET Framework, который реализует командлет.</span><span class="sxs-lookup"><span data-stu-id="db0ff-107">The first step in cmdlet creation is cmdlet naming and the declaration of the .NET Framework class that implements the cmdlet.</span></span> <span data-ttu-id="db0ff-108">Этот командлет извлекает сведения о процессе, поэтому выбранное здесь имя команды — "Get".</span><span class="sxs-lookup"><span data-stu-id="db0ff-108">This cmdlet retrieves process information, so the verb name chosen here is "Get."</span></span> <span data-ttu-id="db0ff-109">(Практически любой командлет, который способен получить информацию, может обрабатывать входные данные командной строки.) Дополнительные сведения о утвержденных командах командлетов см. в разделе [имена глаголов командлетов](./approved-verbs-for-windows-powershell-commands.md).</span><span class="sxs-lookup"><span data-stu-id="db0ff-109">(Almost any sort of cmdlet that is capable of retrieving information can process command-line input.) For more information about approved cmdlet verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="db0ff-110">Ниже приведено объявление класса для командлета **Get-proc** .</span><span class="sxs-lookup"><span data-stu-id="db0ff-110">Here's the class declaration for the **Get-Proc** cmdlet.</span></span> <span data-ttu-id="db0ff-111">Сведения об этом определении приведены в статье [Создание первого командлета](./creating-a-cmdlet-without-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="db0ff-111">Details about this definition are provided in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md).</span></span>

```csharp
[Cmdlet(VerbsCommon.Get, "proc")]
public class GetProcCommand: Cmdlet
```

```vb
<Cmdlet(VerbsCommon.Get, "Proc")> _
Public Class GetProcCommand
    Inherits Cmdlet
```

## <a name="declaring-parameters"></a><span data-ttu-id="db0ff-112">Объявление параметров</span><span class="sxs-lookup"><span data-stu-id="db0ff-112">Declaring Parameters</span></span>

<span data-ttu-id="db0ff-113">Параметр командлета позволяет пользователю предоставлять входные данные для командлета.</span><span class="sxs-lookup"><span data-stu-id="db0ff-113">A cmdlet parameter enables the user to provide input to the cmdlet.</span></span> <span data-ttu-id="db0ff-114">В следующем примере **Get-proc** и `Get-Member` являются именами конвейерных командлетов, а `MemberType` — параметром для командлета `Get-Member`.</span><span class="sxs-lookup"><span data-stu-id="db0ff-114">In the following example, **Get-Proc** and `Get-Member` are the names of pipelined cmdlets, and `MemberType` is a parameter for the `Get-Member` cmdlet.</span></span> <span data-ttu-id="db0ff-115">Параметр имеет аргумент "свойство".</span><span class="sxs-lookup"><span data-stu-id="db0ff-115">The parameter has the argument "property."</span></span>

<span data-ttu-id="db0ff-116">**PS > Get-proc; `get-member` — свойство MemberType**</span><span class="sxs-lookup"><span data-stu-id="db0ff-116">**PS> get-proc ; `get-member` -membertype property**</span></span>

<span data-ttu-id="db0ff-117">Чтобы объявить параметры для командлета, необходимо сначала определить свойства, представляющие параметры.</span><span class="sxs-lookup"><span data-stu-id="db0ff-117">To declare parameters for a cmdlet, you must first define the properties that represent the parameters.</span></span> <span data-ttu-id="db0ff-118">В командлете **Get-proc** единственным параметром является `Name`, который в данном случае представляет имя объекта .NET Framework процесса для извлечения.</span><span class="sxs-lookup"><span data-stu-id="db0ff-118">In the **Get-Proc** cmdlet, the only parameter is `Name`, which in this case represents the name of the .NET Framework process object to retrieve.</span></span> <span data-ttu-id="db0ff-119">Поэтому класс командлета определяет свойство типа String, которое принимает массив имен.</span><span class="sxs-lookup"><span data-stu-id="db0ff-119">Therefore, the cmdlet class defines a property of type string to accept an array of names.</span></span>

<span data-ttu-id="db0ff-120">Ниже приведено объявление параметра для параметра `Name` командлета **Get-proc** .</span><span class="sxs-lookup"><span data-stu-id="db0ff-120">Here's the parameter declaration for the `Name` parameter of the **Get-Proc** cmdlet.</span></span>

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

<span data-ttu-id="db0ff-121">Чтобы сообщить среде выполнения Windows PowerShell, что это свойство является параметром `Name`, в определение свойства добавляется атрибут [System. Management. Automation. параметераттрибуте](/dotnet/api/System.Management.Automation.ParameterAttribute) .</span><span class="sxs-lookup"><span data-stu-id="db0ff-121">To inform the Windows PowerShell runtime that this property is the `Name` parameter, a [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute is added to the property definition.</span></span> <span data-ttu-id="db0ff-122">Базовый синтаксис для объявления этого атрибута — `[Parameter()]`.</span><span class="sxs-lookup"><span data-stu-id="db0ff-122">The basic syntax for declaring this attribute is `[Parameter()]`.</span></span>

> [!NOTE]
> <span data-ttu-id="db0ff-123">Параметр должен быть явно помечен как public.</span><span class="sxs-lookup"><span data-stu-id="db0ff-123">A parameter must be explicitly marked as public.</span></span> <span data-ttu-id="db0ff-124">Параметры, которые не помечены как открытые по умолчанию, являются внутренними и не обнаруживаются средой выполнения Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db0ff-124">Parameters that are not marked as public default to internal and are not found by the Windows PowerShell runtime.</span></span>

<span data-ttu-id="db0ff-125">Этот командлет использует массив строк для параметра `Name`.</span><span class="sxs-lookup"><span data-stu-id="db0ff-125">This cmdlet uses an array of strings for the `Name` parameter.</span></span> <span data-ttu-id="db0ff-126">Если это возможно, командлет также должен определить параметр как массив, так как это позволяет командлету принимать более одного элемента.</span><span class="sxs-lookup"><span data-stu-id="db0ff-126">If possible, your cmdlet should also define a parameter as an array, because this allows the cmdlet to accept more than one item.</span></span>

#### <a name="things-to-remember-about-parameter-definitions"></a><span data-ttu-id="db0ff-127">Вопросы, которые следует помнить об определениях параметров</span><span class="sxs-lookup"><span data-stu-id="db0ff-127">Things to Remember About Parameter Definitions</span></span>

- <span data-ttu-id="db0ff-128">Предопределенные имена параметров Windows PowerShell и типы данных следует использовать повторно, чтобы обеспечить совместимость командлета с командлетами Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db0ff-128">Predefined Windows PowerShell parameter names and data types should be reused as much as possible to ensure that your cmdlet is compatible with Windows PowerShell cmdlets.</span></span> <span data-ttu-id="db0ff-129">Например, если все командлеты используют предопределенное имя параметра `Id` для определения ресурса, пользователь сможет легко понять значение параметра, независимо от того, какой командлет используется.</span><span class="sxs-lookup"><span data-stu-id="db0ff-129">For example, if all cmdlets use the predefined `Id` parameter name to identify a resource, user will easily understand the meaning of the parameter, regardless of what cmdlet they are using.</span></span> <span data-ttu-id="db0ff-130">В сущности, имена параметров соответствуют тем же правилам, которые используются для имен переменных в общеязыковой среде выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="db0ff-130">Basically, parameter names follow the same rules as those used for variable names in the common language runtime (CLR).</span></span> <span data-ttu-id="db0ff-131">Дополнительные сведения об именовании параметров см. в разделе [имена параметров командлета](https://msdn.microsoft.com/en-us/c4500737-0a05-4d01-911b-394424c65bfb).</span><span class="sxs-lookup"><span data-stu-id="db0ff-131">For more information about parameter naming, see [Cmdlet Parameter Names](https://msdn.microsoft.com/en-us/c4500737-0a05-4d01-911b-394424c65bfb).</span></span>

- <span data-ttu-id="db0ff-132">Windows PowerShell резервирует несколько имен параметров для обеспечения единообразного взаимодействия с пользователем.</span><span class="sxs-lookup"><span data-stu-id="db0ff-132">Windows PowerShell reserves a few parameter names to provide a consistent user experience.</span></span> <span data-ttu-id="db0ff-133">Не используйте следующие имена параметров: `WhatIf`, `Confirm`, `Verbose`, `Debug`, `Warn`, `ErrorAction`, `ErrorVariable`, `OutVariable` и `OutBuffer`.</span><span class="sxs-lookup"><span data-stu-id="db0ff-133">Do not use these parameter names: `WhatIf`, `Confirm`, `Verbose`, `Debug`, `Warn`, `ErrorAction`, `ErrorVariable`, `OutVariable`, and `OutBuffer`.</span></span> <span data-ttu-id="db0ff-134">Кроме того, следующие псевдонимы для этих имен параметров зарезервированы: `vb`, `db`, `ea`, `ev`, `ov` и `ob`.</span><span class="sxs-lookup"><span data-stu-id="db0ff-134">Additionally, the following aliases for these parameter names are reserved: `vb`, `db`, `ea`, `ev`, `ov`, and `ob`.</span></span>

- <span data-ttu-id="db0ff-135">`Name` — это простое и общее имя параметра, рекомендуемое для использования в командлетах.</span><span class="sxs-lookup"><span data-stu-id="db0ff-135">`Name` is a simple and common parameter name, recommended for use in your cmdlets.</span></span> <span data-ttu-id="db0ff-136">Лучше выбрать имя параметра, которое отличается от сложного имени, уникального для конкретного командлета, и трудно запомнить.</span><span class="sxs-lookup"><span data-stu-id="db0ff-136">It is better to choose a parameter name like this than a complex name that is unique to a specific cmdlet and hard to remember.</span></span>

- <span data-ttu-id="db0ff-137">В Windows PowerShell параметры не учитывают регистр, хотя по умолчанию оболочка сохраняет регистр.</span><span class="sxs-lookup"><span data-stu-id="db0ff-137">Parameters are case-insensitive in Windows PowerShell, although by default the shell preserves case.</span></span> <span data-ttu-id="db0ff-138">Чувствительность к регистру аргументов зависит от операции командлета.</span><span class="sxs-lookup"><span data-stu-id="db0ff-138">Case-sensitivity of the arguments depends on the operation of the cmdlet.</span></span> <span data-ttu-id="db0ff-139">Аргументы передаются в параметр, как указано в командной строке.</span><span class="sxs-lookup"><span data-stu-id="db0ff-139">Arguments are passed to a parameter as specified at the command line.</span></span>

- <span data-ttu-id="db0ff-140">Примеры других объявлений параметров см. в разделе [параметры командлета](./cmdlet-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="db0ff-140">For examples of other parameter declarations, see [Cmdlet Parameters](./cmdlet-parameters.md).</span></span>

## <a name="declaring-parameters-as-positional-or-named"></a><span data-ttu-id="db0ff-141">Объявление параметров как позиционированного или именованного</span><span class="sxs-lookup"><span data-stu-id="db0ff-141">Declaring Parameters as Positional or Named</span></span>

<span data-ttu-id="db0ff-142">Командлет должен задавать каждый параметр как либо Позиционированный, либо именованный параметр.</span><span class="sxs-lookup"><span data-stu-id="db0ff-142">A cmdlet must set each parameter as either a positional or named parameter.</span></span> <span data-ttu-id="db0ff-143">Оба типа параметров принимают одиночные аргументы, несколько аргументов, разделенных запятыми, и логические параметры.</span><span class="sxs-lookup"><span data-stu-id="db0ff-143">Both kinds of parameters accept single arguments, multiple arguments separated by commas, and Boolean settings.</span></span> <span data-ttu-id="db0ff-144">Логический параметр, также называемый *параметром, обрабатывает*только логические параметры.</span><span class="sxs-lookup"><span data-stu-id="db0ff-144">A Boolean parameter, also called a *switch*, handles only Boolean settings.</span></span> <span data-ttu-id="db0ff-145">Параметр используется для определения наличия параметра.</span><span class="sxs-lookup"><span data-stu-id="db0ff-145">The switch is used to determine the presence of the parameter.</span></span> <span data-ttu-id="db0ff-146">Рекомендуемое значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="db0ff-146">The recommended default is `false`.</span></span>

<span data-ttu-id="db0ff-147">Пример командлета **Get-proc** определяет параметр `Name` как параметр с положением 0.</span><span class="sxs-lookup"><span data-stu-id="db0ff-147">The sample **Get-Proc** cmdlet defines the `Name` parameter as a positional parameter with position 0.</span></span> <span data-ttu-id="db0ff-148">Это означает, что первый аргумент, вводимый пользователем в командной строке, автоматически вставляется для этого параметра.</span><span class="sxs-lookup"><span data-stu-id="db0ff-148">This means that the first argument the user enters on the command line is automatically inserted for this parameter.</span></span> <span data-ttu-id="db0ff-149">Если необходимо определить именованный параметр, для которого пользователь должен указать имя параметра из командной строки, оставьте ключевое слово `Position` за пределами объявления атрибута.</span><span class="sxs-lookup"><span data-stu-id="db0ff-149">If you want to define a named parameter, for which the user must specify the parameter name from the command line, leave the `Position` keyword out of the attribute declaration.</span></span>

> [!NOTE]
> <span data-ttu-id="db0ff-150">Если параметры не должны быть именованы, рекомендуется использовать наиболее часто используемые параметры, чтобы пользователи не могли вводить имя параметра.</span><span class="sxs-lookup"><span data-stu-id="db0ff-150">Unless parameters must be named, we recommend that you make the most-used parameters positional so that users will not have to type the parameter name.</span></span>

## <a name="declaring-parameters-as-mandatory-or-optional"></a><span data-ttu-id="db0ff-151">Объявление параметров как обязательных или необязательных</span><span class="sxs-lookup"><span data-stu-id="db0ff-151">Declaring Parameters as Mandatory or Optional</span></span>

<span data-ttu-id="db0ff-152">Командлет должен задавать каждый параметр как необязательный или обязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="db0ff-152">A cmdlet must set each parameter as either an optional or a mandatory parameter.</span></span> <span data-ttu-id="db0ff-153">В примере командлета **Get-proc** параметр `Name` определен как необязательный, поскольку в объявлении атрибута не задано ключевое слово `Mandatory`.</span><span class="sxs-lookup"><span data-stu-id="db0ff-153">In the sample **Get-Proc** cmdlet, the `Name` parameter is defined as optional because the `Mandatory` keyword is not set in the attribute declaration.</span></span>

## <a name="supporting-parameter-validation"></a><span data-ttu-id="db0ff-154">Поддержка проверки параметров</span><span class="sxs-lookup"><span data-stu-id="db0ff-154">Supporting Parameter Validation</span></span>

<span data-ttu-id="db0ff-155">Пример командлета **Get-proc** добавляет атрибут проверки входных данных [System. Management. Automation. валидатенотнуллоремптяттрибуте](/dotnet/api/System.Management.Automation.ValidateNotNullOrEmptyAttribute)к параметру `Name`, чтобы обеспечить проверку того, что входные данные не `null` или пусты.</span><span class="sxs-lookup"><span data-stu-id="db0ff-155">The sample **Get-Proc** cmdlet adds an input validation attribute, [System.Management.Automation.Validatenotnulloremptyattribute](/dotnet/api/System.Management.Automation.ValidateNotNullOrEmptyAttribute), to the `Name` parameter to enable validation that the input is neither `null` nor empty.</span></span> <span data-ttu-id="db0ff-156">Этот атрибут является одним из нескольких атрибутов проверки, предоставляемых Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db0ff-156">This attribute is one of several validation attributes provided by Windows PowerShell.</span></span> <span data-ttu-id="db0ff-157">Примеры других атрибутов проверки см. в разделе [Проверка входных параметров](./validating-parameter-input.md).</span><span class="sxs-lookup"><span data-stu-id="db0ff-157">For examples of other validation attributes, see [Validating Parameter Input](./validating-parameter-input.md).</span></span>

```
[Parameter(Position = 0)]
[ValidateNotNullOrEmpty]
public string[] Name
```

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="db0ff-158">Переопределение метода обработки входных данных</span><span class="sxs-lookup"><span data-stu-id="db0ff-158">Overriding an Input Processing Method</span></span>

<span data-ttu-id="db0ff-159">Если командлет обрабатывает входные данные командной строки, он должен переопределять соответствующие методы обработки входных данных.</span><span class="sxs-lookup"><span data-stu-id="db0ff-159">If your cmdlet is to handle command-line input, it must override the appropriate input processing methods.</span></span> <span data-ttu-id="db0ff-160">Основные методы обработки ввода представлены при [создании первого командлета](./creating-a-cmdlet-without-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="db0ff-160">The basic input processing methods are introduced in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md).</span></span>

<span data-ttu-id="db0ff-161">Командлет **Get-proc** переопределяет метод [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) для управления входными параметрами `Name`, предоставленными пользователем или сценарием.</span><span class="sxs-lookup"><span data-stu-id="db0ff-161">The **Get-Proc** cmdlet overrides the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method to handle the `Name` parameter input provided by the user or a script.</span></span> <span data-ttu-id="db0ff-162">Этот метод получает процессы для каждого запрошенного имени процесса или все для процессов, если имя не указано.</span><span class="sxs-lookup"><span data-stu-id="db0ff-162">This method gets the processes for each requested process name, or all for processes if no name is provided.</span></span> <span data-ttu-id="db0ff-163">Обратите внимание, что в [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)вызов [System. Management. Automation. командлет. WriteObject% 28System. Object% 2CSystem. Boolean %29](/dotnet/api/system.management.automation.cmdlet.writeobject?view=powershellsdk-1.1.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) является механизмом вывода для отправки выходных объектов в надстройк.</span><span class="sxs-lookup"><span data-stu-id="db0ff-163">Notice that in [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord), the call to [System.Management.Automation.Cmdlet.WriteObject%28System.Object%2CSystem.Boolean%29](/dotnet/api/system.management.automation.cmdlet.writeobject?view=powershellsdk-1.1.0#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) is the output mechanism for sending output objects to the pipeline.</span></span> <span data-ttu-id="db0ff-164">Второй параметр этого вызова, `enumerateCollection`, имеет значение `true`, чтобы информировать среду выполнения Windows PowerShell о перечислении выходного массива объектов процессов и записи одного процесса в командную строку.</span><span class="sxs-lookup"><span data-stu-id="db0ff-164">The second parameter of this call, `enumerateCollection`, is set to `true` to inform the Windows PowerShell runtime to enumerate the output array of process objects and write one process at a time to the command line.</span></span>

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

## <a name="code-sample"></a><span data-ttu-id="db0ff-165">Пример кода</span><span class="sxs-lookup"><span data-stu-id="db0ff-165">Code Sample</span></span>

<span data-ttu-id="db0ff-166">Полный C# пример кода см. в разделе [GetProcessSample02 Sample](./getprocesssample02-sample.md).</span><span class="sxs-lookup"><span data-stu-id="db0ff-166">For the complete C# sample code, see [GetProcessSample02 Sample](./getprocesssample02-sample.md).</span></span>

## <a name="defining-object-types-and-formatting"></a><span data-ttu-id="db0ff-167">Определение типов объектов и форматирование</span><span class="sxs-lookup"><span data-stu-id="db0ff-167">Defining Object Types and Formatting</span></span>

<span data-ttu-id="db0ff-168">Windows PowerShell передает сведения между командлетами с помощью .NET Framework объектов.</span><span class="sxs-lookup"><span data-stu-id="db0ff-168">Windows PowerShell passes information between cmdlets by using .NET Framework objects.</span></span> <span data-ttu-id="db0ff-169">Следовательно, командлету может потребоваться определить собственный тип, или командлету может потребоваться расширить существующий тип, предоставленный другим командлетом.</span><span class="sxs-lookup"><span data-stu-id="db0ff-169">Consequently, a cmdlet might need to define its own type, or a cmdlet might need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="db0ff-170">Дополнительные сведения об определении новых типов или расширении существующих типов см. в разделе [расширение типов объектов и форматирование](https://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351).</span><span class="sxs-lookup"><span data-stu-id="db0ff-170">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](https://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="db0ff-171">Создание командлета</span><span class="sxs-lookup"><span data-stu-id="db0ff-171">Building the Cmdlet</span></span>

<span data-ttu-id="db0ff-172">После реализации командлета его необходимо зарегистрировать в Windows PowerShell с помощью оснастки Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db0ff-172">After you implement a cmdlet, you must register it with Windows PowerShell by using a Windows PowerShell snap-in.</span></span> <span data-ttu-id="db0ff-173">Дополнительные сведения о регистрации командлетов см. [в разделе Регистрация командлетов, поставщиков и ведущих приложений](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).</span><span class="sxs-lookup"><span data-stu-id="db0ff-173">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="db0ff-174">Тестирование командлета</span><span class="sxs-lookup"><span data-stu-id="db0ff-174">Testing the Cmdlet</span></span>

<span data-ttu-id="db0ff-175">Если командлет зарегистрирован в Windows PowerShell, его можно проверить, запустив его в командной строке.</span><span class="sxs-lookup"><span data-stu-id="db0ff-175">When your cmdlet is registered with Windows PowerShell, you can test it by running it on the command line.</span></span> <span data-ttu-id="db0ff-176">Ниже приведены два способа проверки кода для примера командлета.</span><span class="sxs-lookup"><span data-stu-id="db0ff-176">Here are two ways to test the code for the sample cmdlet.</span></span> <span data-ttu-id="db0ff-177">Дополнительные сведения об использовании командлетов из командной строки см. в разделе [Начало работы with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="db0ff-177">For more information about using cmdlets from the command line, see [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span></span>

- <span data-ttu-id="db0ff-178">В командной строке Windows PowerShell используйте следующую команду, чтобы получить список процессов Internet Explorer с именем IEXPLORE.</span><span class="sxs-lookup"><span data-stu-id="db0ff-178">At the Windows PowerShell prompt, use the following command to list the Internet Explorer process, which is named "IEXPLORE."</span></span>

    ```powershell
    PS> get-proc -name iexplore
    ```

<span data-ttu-id="db0ff-179">Отобразятся следующие выходные данные.</span><span class="sxs-lookup"><span data-stu-id="db0ff-179">The following output appears.</span></span>

    ```
    Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)   Id   ProcessName
    -------  ------  -----   -----  -----   ------ --   -----------
        354      11  10036   18992    85   0.67   3284   iexplore
    ```

- <span data-ttu-id="db0ff-180">Чтобы получить список браузеров Internet Explorer, Outlook и Notepad с именами «IEXPLORE», «OUTLOOK» и «NOTEPAD», используйте следующую команду.</span><span class="sxs-lookup"><span data-stu-id="db0ff-180">To list the Internet Explorer, Outlook, and Notepad processes named "IEXPLORE," "OUTLOOK," and "NOTEPAD," use the following command.</span></span> <span data-ttu-id="db0ff-181">При наличии нескольких процессов отображаются все они.</span><span class="sxs-lookup"><span data-stu-id="db0ff-181">If there are multiple processes, all of them are displayed.</span></span>

    ```powershell
    PS> get-proc -name iexplore, outlook, notepad
    ```

<span data-ttu-id="db0ff-182">Отобразятся следующие выходные данные.</span><span class="sxs-lookup"><span data-stu-id="db0ff-182">The following output appears.</span></span>

    ```
    Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)   Id   ProcessName
    -------  ------  -----   -----  -----  ------   --    -----------
        732      21  24696    5000    138   2.25  2288   iexplore
        715      19  20556   14116    136   1.78  3860   iexplore
       3917      62  74096   58112    468 191.56  1848   OUTLOOK
         39       2   1024    3280     30   0.09  1444   notepad
         39       2   1024     356     30   0.08  3396   notepad
    ```

## <a name="see-also"></a><span data-ttu-id="db0ff-183">См. также:</span><span class="sxs-lookup"><span data-stu-id="db0ff-183">See Also</span></span>

[<span data-ttu-id="db0ff-184">Добавление параметров, обрабатывающих входные данные конвейера</span><span class="sxs-lookup"><span data-stu-id="db0ff-184">Adding Parameters that Process Pipeline Input</span></span>](./adding-parameters-that-process-pipeline-input.md)

[<span data-ttu-id="db0ff-185">Создание первого командлета</span><span class="sxs-lookup"><span data-stu-id="db0ff-185">Creating Your First Cmdlet</span></span>](./creating-a-cmdlet-without-parameters.md)

[<span data-ttu-id="db0ff-186">Расширение типов объектов и форматирование</span><span class="sxs-lookup"><span data-stu-id="db0ff-186">Extending Object Types and Formatting</span></span>](https://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[<span data-ttu-id="db0ff-187">Регистрация командлетов, поставщиков и ведущих приложений</span><span class="sxs-lookup"><span data-stu-id="db0ff-187">How to Register Cmdlets, Providers, and Host Applications</span></span>](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[<span data-ttu-id="db0ff-188">Справочник по Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="db0ff-188">Windows PowerShell Reference</span></span>](../windows-powershell-reference.md)

[<span data-ttu-id="db0ff-189">Примеры командлетов</span><span class="sxs-lookup"><span data-stu-id="db0ff-189">Cmdlet Samples</span></span>](./cmdlet-samples.md)
