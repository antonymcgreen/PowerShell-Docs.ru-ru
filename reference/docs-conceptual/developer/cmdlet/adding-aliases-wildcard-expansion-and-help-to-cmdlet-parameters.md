---
title: Добавление псевдонимов, расширение подстановочных знаков и Справка по параметрам командлетов | Документация Майкрософт
ms.date: 09/13/2016
ms.openlocfilehash: 244c50c73972c2760e0029c7fa4f4b5764b066da
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774972"
---
# <a name="adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters"></a><span data-ttu-id="41569-102">Добавление псевдонимов, развертывание подстановочных знаков и справка по параметрам командлета</span><span class="sxs-lookup"><span data-stu-id="41569-102">Adding Aliases, Wildcard Expansion, and Help to Cmdlet Parameters</span></span>

<span data-ttu-id="41569-103">В этом разделе описывается, как добавлять псевдонимы, распознавать подстановочные знаки и сообщения справки для параметров командлета "прекращать-proc" (описывается в разделе [Создание командлета, изменяющего систему](./creating-a-cmdlet-that-modifies-the-system.md)).</span><span class="sxs-lookup"><span data-stu-id="41569-103">This section describes how to add aliases, wildcard expansion, and Help messages to the parameters of the Stop-Proc cmdlet (described in [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md)).</span></span>

<span data-ttu-id="41569-104">Этот командлет останавливает процесс пытается прерывать процессы, полученные с помощью командлета Get-proc (описывается в разделе [Создание первого командлета](./creating-a-cmdlet-without-parameters.md)).</span><span class="sxs-lookup"><span data-stu-id="41569-104">This Stop-Proc cmdlet attempts to stop processes that are retrieved using the Get-Proc cmdlet (described in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md)).</span></span>

## <a name="defining-the-cmdlet"></a><span data-ttu-id="41569-105">Определение командлета</span><span class="sxs-lookup"><span data-stu-id="41569-105">Defining the Cmdlet</span></span>

<span data-ttu-id="41569-106">Первым шагом при создании командлета всегда является присвоение имени командлета и объявление класса .NET, реализующего командлет.</span><span class="sxs-lookup"><span data-stu-id="41569-106">The first step in cmdlet creation is always naming the cmdlet and declaring the .NET class that implements the cmdlet.</span></span> <span data-ttu-id="41569-107">Так как вы создаете командлет для изменения системы, ему следует присвоить соответствующие имена.</span><span class="sxs-lookup"><span data-stu-id="41569-107">Because you are writing a cmdlet to change the system, it should be named accordingly.</span></span> <span data-ttu-id="41569-108">Поскольку этот командлет останавливает системные процессы, он использует команду Stop, определенную классом [System. Management. Automation. вербслифецикле](/dotnet/api/System.Management.Automation.VerbsLifeCycle) , с существительным "proc" для обозначения процесса.</span><span class="sxs-lookup"><span data-stu-id="41569-108">Because this cmdlet stops system processes, it uses the verb "Stop", defined by the [System.Management.Automation.Verbslifecycle](/dotnet/api/System.Management.Automation.VerbsLifeCycle) class, with the noun "Proc" to indicate process.</span></span> <span data-ttu-id="41569-109">Дополнительные сведения о утвержденных командах командлетов см. в разделе [имена глаголов командлетов](./approved-verbs-for-windows-powershell-commands.md).</span><span class="sxs-lookup"><span data-stu-id="41569-109">For more information about approved cmdlet verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="41569-110">Следующий код является определением класса для этого командлета "останавливает-proc".</span><span class="sxs-lookup"><span data-stu-id="41569-110">The following code is the class definition for this Stop-Proc cmdlet.</span></span>

```csharp
[Cmdlet(VerbsLifecycle.Stop, "proc",
        SupportsShouldProcess = true)]
public class StopProcCommand : Cmdlet
```

## <a name="defining-parameters-for-system-modification"></a><span data-ttu-id="41569-111">Определение параметров для изменения системы</span><span class="sxs-lookup"><span data-stu-id="41569-111">Defining Parameters for System Modification</span></span>

<span data-ttu-id="41569-112">Командлету необходимо определить параметры, которые поддерживают изменения системы и отзывы пользователей.</span><span class="sxs-lookup"><span data-stu-id="41569-112">Your cmdlet needs to define parameters that support system modifications and user feedback.</span></span> <span data-ttu-id="41569-113">Командлет должен определить `Name` параметр или эквивалент, чтобы командлет мог изменять систему с помощью некоторого идентификатора.</span><span class="sxs-lookup"><span data-stu-id="41569-113">The cmdlet should define a `Name` parameter or equivalent so that the cmdlet will be able to modify the system by some sort of identifier.</span></span> <span data-ttu-id="41569-114">Кроме того, командлет должен определить `Force` `PassThru` Параметры и.</span><span class="sxs-lookup"><span data-stu-id="41569-114">In addition, the cmdlet should define the `Force` and `PassThru` parameters.</span></span> <span data-ttu-id="41569-115">Дополнительные сведения об этих параметрах см. в разделе [Создание командлета, изменяющего систему](./creating-a-cmdlet-that-modifies-the-system.md).</span><span class="sxs-lookup"><span data-stu-id="41569-115">For more information about these parameters, see [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md).</span></span>

## <a name="defining-a-parameter-alias"></a><span data-ttu-id="41569-116">Определение псевдонима параметра</span><span class="sxs-lookup"><span data-stu-id="41569-116">Defining a Parameter Alias</span></span>

<span data-ttu-id="41569-117">Псевдонимом параметра может быть альтернативное имя или четко определенное имя в виде одной или двух букв для параметра командлета.</span><span class="sxs-lookup"><span data-stu-id="41569-117">A parameter alias can be an alternate name or a well-defined 1-letter or 2-letter short name for a cmdlet parameter.</span></span> <span data-ttu-id="41569-118">В обоих случаях цель использования псевдонимов — упростить ввод пользователя из командной строки.</span><span class="sxs-lookup"><span data-stu-id="41569-118">In both cases, the goal of using aliases is to simplify user entry from the command line.</span></span> <span data-ttu-id="41569-119">Windows PowerShell поддерживает псевдонимы параметров с помощью атрибута [System. Management. Automation. алиасаттрибуте](/dotnet/api/System.Management.Automation.AliasAttribute) , который использует синтаксис объявления [Alias ()].</span><span class="sxs-lookup"><span data-stu-id="41569-119">Windows PowerShell supports parameter aliases through the [System.Management.Automation.Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute) attribute, which uses the declaration syntax [Alias()].</span></span>

<span data-ttu-id="41569-120">В следующем коде показано, как псевдоним добавляется в `Name` параметр.</span><span class="sxs-lookup"><span data-stu-id="41569-120">The following code shows how an alias is added to the `Name` parameter.</span></span>

```csharp
/// <summary>
/// Specify the mandatory Name parameter used to identify the
/// processes to be stopped.
/// </summary>
[Parameter(
           Position = 0,
           Mandatory = true,
           ValueFromPipeline = true,
           ValueFromPipelineByPropertyName = true,
           HelpMessage = "The name of one or more processes to stop. Wildcards are permitted."
)]
[Alias("ProcessName")]
public string[] Name
{
  get { return processNames; }
  set { processNames = value; }
}
private string[] processNames;
```

<span data-ttu-id="41569-121">Помимо использования атрибута [System. Management. Automation. алиасаттрибуте](/dotnet/api/System.Management.Automation.AliasAttribute) , среда выполнения Windows PowerShell выполняет частичное совпадение имен, даже если псевдонимы не указаны.</span><span class="sxs-lookup"><span data-stu-id="41569-121">In addition to using the [System.Management.Automation.Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute) attribute, the Windows PowerShell runtime performs partial name matching, even if no aliases are specified.</span></span> <span data-ttu-id="41569-122">Например, если у командлета есть `FileName` параметр, который является единственным параметром, начинающимся с `F` , пользователь может ввести `Filename` , `Filenam` , `File` , `Fi` или `F` и по-прежнему распознать запись в качестве `FileName` параметра.</span><span class="sxs-lookup"><span data-stu-id="41569-122">For example, if your cmdlet has a `FileName` parameter and that is the only parameter that starts with `F`, the user could enter `Filename`, `Filenam`, `File`, `Fi`, or `F` and still recognize the entry as the `FileName` parameter.</span></span>

## <a name="creating-help-for-parameters"></a><span data-ttu-id="41569-123">Создание справки для параметров</span><span class="sxs-lookup"><span data-stu-id="41569-123">Creating Help for Parameters</span></span>

<span data-ttu-id="41569-124">Windows PowerShell позволяет создавать справку для параметров командлета.</span><span class="sxs-lookup"><span data-stu-id="41569-124">Windows PowerShell allows you to create Help for cmdlet parameters.</span></span> <span data-ttu-id="41569-125">Это можно сделать для любого параметра, используемого для изменения системы и отзывов пользователей.</span><span class="sxs-lookup"><span data-stu-id="41569-125">Do this for any parameter used for system modification and user feedback.</span></span> <span data-ttu-id="41569-126">Для каждого параметра, поддерживающего справку, можно задать `HelpMessage` ключевое слово Attribute в объявлении атрибута [System. Management. Automation. параметераттрибуте](/dotnet/api/System.Management.Automation.ParameterAttribute) .</span><span class="sxs-lookup"><span data-stu-id="41569-126">For each parameter to support Help, you can set the `HelpMessage` attribute keyword in the [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute declaration.</span></span> <span data-ttu-id="41569-127">Это ключевое слово определяет текст, отображаемый пользователю для помощи в использовании параметра.</span><span class="sxs-lookup"><span data-stu-id="41569-127">This keyword defines the text to display to the user for assistance in using the parameter.</span></span> <span data-ttu-id="41569-128">Можно также задать `HelpMessageBaseName` ключевое слово, чтобы определить базовое имя ресурса, используемого для сообщения.</span><span class="sxs-lookup"><span data-stu-id="41569-128">You can also set the `HelpMessageBaseName` keyword to identify the base name of a resource to use for the message.</span></span> <span data-ttu-id="41569-129">Если задать это ключевое слово, необходимо также задать `HelpMessageResourceId` ключевое слово, чтобы указать идентификатор ресурса.</span><span class="sxs-lookup"><span data-stu-id="41569-129">If you set this keyword, you must also set the `HelpMessageResourceId` keyword to specify the resource identifier.</span></span>

<span data-ttu-id="41569-130">Следующий код из командлета «The-proc» определяет `HelpMessage` ключевое слово атрибута для `Name` параметра.</span><span class="sxs-lookup"><span data-stu-id="41569-130">The following code from this Stop-Proc cmdlet defines the `HelpMessage` attribute keyword for the `Name` parameter.</span></span>

```csharp
/// <summary>
/// Specify the mandatory Name parameter used to identify the
/// processes to be stopped.
/// </summary>
[Parameter(
           Position = 0,
           Mandatory = true,
           ValueFromPipeline = true,
           ValueFromPipelineByPropertyName = true,
           HelpMessage = "The name of one or more processes to stop. Wildcards are permitted."
)]
```

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="41569-131">Переопределение метода обработки входных данных</span><span class="sxs-lookup"><span data-stu-id="41569-131">Overriding an Input Processing Method</span></span>

<span data-ttu-id="41569-132">Командлет должен переопределять метод обработки ввода, чаще всего это будет [System. Management. Automation. командлет. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord).</span><span class="sxs-lookup"><span data-stu-id="41569-132">Your cmdlet must override an input processing method, most often this will be [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord).</span></span> <span data-ttu-id="41569-133">При изменении системы командлет должен вызвать методы [System. Management. Automation. командлет. ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) и [System. Management. Automation. командлет. ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) , чтобы разрешить пользователю оставлять отзывы до внесения изменений.</span><span class="sxs-lookup"><span data-stu-id="41569-133">When modifying the system, the cmdlet should call the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) methods to allow the user to provide feedback before a change is made.</span></span> <span data-ttu-id="41569-134">Дополнительные сведения об этих методах см. в разделе [Создание командлета, изменяющего систему](./creating-a-cmdlet-that-modifies-the-system.md).</span><span class="sxs-lookup"><span data-stu-id="41569-134">For more information about these methods, see [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md).</span></span>

## <a name="supporting-wildcard-expansion"></a><span data-ttu-id="41569-135">Поддержка расширения подстановочных знаков</span><span class="sxs-lookup"><span data-stu-id="41569-135">Supporting Wildcard Expansion</span></span>

<span data-ttu-id="41569-136">Чтобы разрешить выбор нескольких объектов, командлет может использовать классы [System. Management. Automation. вилдкардпаттерн](/dotnet/api/System.Management.Automation.WildcardPattern) и [System. Management. Automation. вилдкардоптионс](/dotnet/api/System.Management.Automation.WildcardOptions) для предоставления поддержки расширения подстановочных знаков для ввода параметров.</span><span class="sxs-lookup"><span data-stu-id="41569-136">To allow the selection of multiple objects, your cmdlet can use the [System.Management.Automation.Wildcardpattern](/dotnet/api/System.Management.Automation.WildcardPattern) and [System.Management.Automation.Wildcardoptions](/dotnet/api/System.Management.Automation.WildcardOptions) classes to provide wildcard expansion support for parameter input.</span></span> <span data-ttu-id="41569-137">Примеры шаблонов с подстановочными знаками: LSA \*, \* . txt и [a-c] \* .</span><span class="sxs-lookup"><span data-stu-id="41569-137">Examples of wildcard patterns are lsa\*, \*.txt, and [a-c]\*.</span></span> <span data-ttu-id="41569-138">Используйте символ обратной кавычки (') в качестве escape-символа, если шаблон содержит символ, который следует использовать буквально.</span><span class="sxs-lookup"><span data-stu-id="41569-138">Use the back-quote character (\`) as an escape character when the pattern contains a character that should be used literally.</span></span>

<span data-ttu-id="41569-139">Расширения с подстановочными знаками имен файлов и путей — это примеры распространенных сценариев, в которых командлет может разрешить ввод пути, если требуется выбрать несколько объектов.</span><span class="sxs-lookup"><span data-stu-id="41569-139">Wildcard expansions of file and path names are examples of common scenarios where the cmdlet may want to allow support for path inputs when the selection of multiple objects is required.</span></span> <span data-ttu-id="41569-140">Общий случай — в файловой системе, где пользователь хочет просмотреть все файлы, находящиеся в текущей папке.</span><span class="sxs-lookup"><span data-stu-id="41569-140">A common case is in the file system, where a user wants to see all files residing in the current folder.</span></span>

<span data-ttu-id="41569-141">Необходимо использовать специальную реализацию шаблона с подстановочным знаком только в редких случаях.</span><span class="sxs-lookup"><span data-stu-id="41569-141">You should need a customized wildcard pattern matching implementation only rarely.</span></span> <span data-ttu-id="41569-142">В этом случае командлет должен поддерживать полную спецификацию POSIX 1003,2, 3,13 для расширения с подстановочными знаками или следующее упрощенное подмножество:</span><span class="sxs-lookup"><span data-stu-id="41569-142">In this case, your cmdlet should support either the full POSIX 1003.2, 3.13 specification for wildcard expansion or the following simplified subset:</span></span>

- <span data-ttu-id="41569-143">**Вопросительный знак (?).**</span><span class="sxs-lookup"><span data-stu-id="41569-143">**Question mark (?).**</span></span> <span data-ttu-id="41569-144">Соответствует любому символу в указанном расположении.</span><span class="sxs-lookup"><span data-stu-id="41569-144">Matches any character at the specified location.</span></span>

- <span data-ttu-id="41569-145">**Звездочка ( \* ).**</span><span class="sxs-lookup"><span data-stu-id="41569-145">**Asterisk (\*).**</span></span> <span data-ttu-id="41569-146">Соответствует нулю или большему числу символов, начиная с указанного места.</span><span class="sxs-lookup"><span data-stu-id="41569-146">Matches zero or more characters starting at the specified location.</span></span>

- <span data-ttu-id="41569-147">**Открывающая скобка ([).**</span><span class="sxs-lookup"><span data-stu-id="41569-147">**Open bracket ([).**</span></span> <span data-ttu-id="41569-148">Представляет выражение шаблонной скобки, которое может содержать символы или диапазон символов.</span><span class="sxs-lookup"><span data-stu-id="41569-148">Introduces a pattern bracket expression that can contain characters or a range of characters.</span></span> <span data-ttu-id="41569-149">Если диапазон является обязательным, для обозначения диапазона используется дефис (-).</span><span class="sxs-lookup"><span data-stu-id="41569-149">If a range is required, a hyphen (-) is used to indicate the range.</span></span>

- <span data-ttu-id="41569-150">**Закрывающая квадратная скобка (]).**</span><span class="sxs-lookup"><span data-stu-id="41569-150">**Close bracket (]).**</span></span> <span data-ttu-id="41569-151">Завершает выражение шаблонной скобки.</span><span class="sxs-lookup"><span data-stu-id="41569-151">Ends a pattern bracket expression.</span></span>

- <span data-ttu-id="41569-152">**Escape-символ обратной кавычки (').**</span><span class="sxs-lookup"><span data-stu-id="41569-152">**Back-quote escape character (\`).**</span></span> <span data-ttu-id="41569-153">Указывает, что следующий символ должен использоваться буквально.</span><span class="sxs-lookup"><span data-stu-id="41569-153">Indicates that the next character should be taken literally.</span></span> <span data-ttu-id="41569-154">Имейте в виду, что при указании символа обратной кавычки из командной строки (в отличие от программного указания) escape-символ обратной кавычки должен быть указан дважды.</span><span class="sxs-lookup"><span data-stu-id="41569-154">Be aware that when specifying the back-quote character from the command line (as opposed to specifying it programmatically), the back-quote escape character must be specified twice.</span></span>

> [!NOTE]
> <span data-ttu-id="41569-155">Дополнительные сведения о шаблонах с подстановочными знаками см. [в разделе Поддержка подстановочных знаков в параметрах командлета](./supporting-wildcard-characters-in-cmdlet-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="41569-155">For more information about wildcard patterns, see [Supporting Wildcards in Cmdlet Parameters](./supporting-wildcard-characters-in-cmdlet-parameters.md).</span></span>

<span data-ttu-id="41569-156">В следующем коде показано, как задать подстановочные знаки и определить шаблон, используемый для разрешения `Name` параметра для этого командлета.</span><span class="sxs-lookup"><span data-stu-id="41569-156">The following code shows how to set wildcard options and define the wildcard pattern used for resolving the `Name` parameter for this cmdlet.</span></span>

```csharp
WildcardOptions options = WildcardOptions.IgnoreCase |
                          WildcardOptions.Compiled;
WildcardPattern wildcard = new WildcardPattern(name,options);
```

<span data-ttu-id="41569-157">В следующем коде показано, как проверить, соответствует ли имя процесса определенному шаблону шаблона.</span><span class="sxs-lookup"><span data-stu-id="41569-157">The following code shows how to test whether the process name matches the defined wildcard pattern.</span></span> <span data-ttu-id="41569-158">Обратите внимание, что в этом случае, если имя процесса не соответствует шаблону, командлет продолжит процедуру, чтобы получить имя следующего процесса.</span><span class="sxs-lookup"><span data-stu-id="41569-158">Notice that, in this case, if the process name does not match the pattern, the cmdlet continues on to get the next process name.</span></span>

```csharp
if (!wildcard.IsMatch(processName))
{
  continue;
}
```

## <a name="code-sample"></a><span data-ttu-id="41569-159">Образец кода</span><span class="sxs-lookup"><span data-stu-id="41569-159">Code Sample</span></span>

<span data-ttu-id="41569-160">Полный пример кода на C# см. в разделе [StopProcessSample03 Sample](./stopprocesssample03-sample.md).</span><span class="sxs-lookup"><span data-stu-id="41569-160">For the complete C# sample code, see [StopProcessSample03 Sample](./stopprocesssample03-sample.md).</span></span>

## <a name="define-object-types-and-formatting"></a><span data-ttu-id="41569-161">Определение типов объектов и форматирование</span><span class="sxs-lookup"><span data-stu-id="41569-161">Define Object Types and Formatting</span></span>

<span data-ttu-id="41569-162">Windows PowerShell передает сведения между командлетами с помощью объектов .NET.</span><span class="sxs-lookup"><span data-stu-id="41569-162">Windows PowerShell passes information between cmdlets using .Net objects.</span></span> <span data-ttu-id="41569-163">Следовательно, командлету может потребоваться определить собственный тип, или командлету может потребоваться расширить существующий тип, предоставленный другим командлетом.</span><span class="sxs-lookup"><span data-stu-id="41569-163">Consequently, a cmdlet may need to define its own type, or the cmdlet may need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="41569-164">Дополнительные сведения об определении новых типов или расширении существующих типов см. в разделе [расширение типов объектов и форматирование](/previous-versions//ms714665(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="41569-164">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85)).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="41569-165">Создание командлета</span><span class="sxs-lookup"><span data-stu-id="41569-165">Building the Cmdlet</span></span>

<span data-ttu-id="41569-166">После реализации командлета его необходимо зарегистрировать в Windows PowerShell с помощью оснастки Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="41569-166">After implementing a cmdlet, it must be registered with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="41569-167">Дополнительные сведения о регистрации командлетов см. [в разделе Регистрация командлетов, поставщиков и ведущих приложений](/previous-versions//ms714644(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="41569-167">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85)).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="41569-168">Тестирование командлета</span><span class="sxs-lookup"><span data-stu-id="41569-168">Testing the Cmdlet</span></span>

<span data-ttu-id="41569-169">Если командлет зарегистрирован в Windows PowerShell, его можно проверить, запустив его в командной строке.</span><span class="sxs-lookup"><span data-stu-id="41569-169">When your cmdlet has been registered with Windows PowerShell, you can test it by running it on the command line.</span></span> <span data-ttu-id="41569-170">Давайте протестируем пример командлета "останавливает-proc".</span><span class="sxs-lookup"><span data-stu-id="41569-170">Let's test the sample Stop-Proc cmdlet.</span></span> <span data-ttu-id="41569-171">Дополнительные сведения об использовании командлетов из командной строки см. в [Начало работы с помощью Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="41569-171">For more information about using cmdlets from the command line, see the [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span></span>

- <span data-ttu-id="41569-172">Запустите Windows PowerShell и используйте командлет "останавливает-обработать", чтобы прерывать процесс с помощью псевдонима ProcessName для `Name` параметра.</span><span class="sxs-lookup"><span data-stu-id="41569-172">Start Windows PowerShell and use Stop-Proc to stop a process using the ProcessName alias for the `Name` parameter.</span></span>

    ```powershell
    PS> stop-proc -ProcessName notepad
    ```

    <span data-ttu-id="41569-173">Появится следующий результат.</span><span class="sxs-lookup"><span data-stu-id="41569-173">The following output appears.</span></span>

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (3496)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    ```

- <span data-ttu-id="41569-174">В командной строке выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="41569-174">Make the following entry on the command line.</span></span> <span data-ttu-id="41569-175">Так как параметр name является обязательным, вам будет предложено ввести его.</span><span class="sxs-lookup"><span data-stu-id="41569-175">Because the Name parameter is mandatory, you are prompted for it.</span></span> <span data-ttu-id="41569-176">Ввод "!?"</span><span class="sxs-lookup"><span data-stu-id="41569-176">Entering "!?"</span></span> <span data-ttu-id="41569-177">выводит текст справки, связанный с параметром.</span><span class="sxs-lookup"><span data-stu-id="41569-177">brings up the help text associated with the parameter.</span></span>

    ```powershell
    PS> stop-proc
    ```

    <span data-ttu-id="41569-178">Появится следующий результат.</span><span class="sxs-lookup"><span data-stu-id="41569-178">The following output appears.</span></span>

    ```
    Cmdlet stop-proc at command pipeline position 1
    Supply values for the following parameters:
    (Type !? for Help.)
    Name[0]: !?
    The name of one or more processes to stop. Wildcards are permitted.
    Name[0]: notepad
    ```

- <span data-ttu-id="41569-179">Теперь выполните следующую запись, чтобы отключить все процессы, соответствующие шаблону подстановочного знака "\* Note \* ".</span><span class="sxs-lookup"><span data-stu-id="41569-179">Now make the following entry to stop all processes that match the wildcard pattern "\*note\*".</span></span> <span data-ttu-id="41569-180">Перед остановкой каждого процесса, соответствующего шаблону, выводится запрос.</span><span class="sxs-lookup"><span data-stu-id="41569-180">You are prompted before stopping each process that matches the pattern.</span></span>

    ```powershell
    PS> stop-proc -Name *note*
    ```

    <span data-ttu-id="41569-181">Появится следующий результат.</span><span class="sxs-lookup"><span data-stu-id="41569-181">The following output appears.</span></span>

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (1112)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    ```

    <span data-ttu-id="41569-182">Появится следующий результат.</span><span class="sxs-lookup"><span data-stu-id="41569-182">The following output appears.</span></span>

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "ONENOTEM (3712)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

    <span data-ttu-id="41569-183">Появится следующий результат.</span><span class="sxs-lookup"><span data-stu-id="41569-183">The following output appears.</span></span>

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "ONENOTE (3592)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

## <a name="see-also"></a><span data-ttu-id="41569-184">См. также</span><span class="sxs-lookup"><span data-stu-id="41569-184">See Also</span></span>

[<span data-ttu-id="41569-185">Создание командлета, изменяющего систему</span><span class="sxs-lookup"><span data-stu-id="41569-185">Create a Cmdlet that Modifies the System</span></span>](./creating-a-cmdlet-that-modifies-the-system.md)

[<span data-ttu-id="41569-186">Создание командлета Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="41569-186">How to Create a Windows PowerShell Cmdlet</span></span>](/powershell/scripting/developer/cmdlet/writing-a-windows-powershell-cmdlet)

<span data-ttu-id="41569-187">[Расширение типов объектов и форматирование](/previous-versions//ms714665(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="41569-187">[Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85))</span></span>

<span data-ttu-id="41569-188">[Регистрация командлетов, поставщиков и ведущих приложений](/previous-versions//ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="41569-188">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85))</span></span>

[<span data-ttu-id="41569-189">Поддержка подстановочных знаков в параметрах командлета</span><span class="sxs-lookup"><span data-stu-id="41569-189">Supporting Wildcards in Cmdlet Parameters</span></span>](./supporting-wildcard-characters-in-cmdlet-parameters.md)

[<span data-ttu-id="41569-190">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="41569-190">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
