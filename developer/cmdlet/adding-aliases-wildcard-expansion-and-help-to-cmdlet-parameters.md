---
title: Добавление псевдонимы, развертывание знаков подстановки, а также помогают параметры командлета | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 931ccace-c565-4a98-8dcc-df00f86394b1
caps.latest.revision: 8
ms.openlocfilehash: 0f025213087e6f308adf8e597fc01c1320251f76
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859330"
---
# <a name="adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters"></a><span data-ttu-id="fc71a-102">Добавление псевдонимов, развертывание подстановочных знаков и справка по параметрам командлета</span><span class="sxs-lookup"><span data-stu-id="fc71a-102">Adding Aliases, Wildcard Expansion, and Help to Cmdlet Parameters</span></span>

<span data-ttu-id="fc71a-103">В этом разделе описывается добавление псевдонимы, развертывание знаков подстановки, и сообщения справки для параметров командлета Stop-Proc (описано в разделе [Создание командлет, который изменяет система](./creating-a-cmdlet-that-modifies-the-system.md)).</span><span class="sxs-lookup"><span data-stu-id="fc71a-103">This section describes how to add aliases, wildcard expansion, and Help messages to the parameters of the Stop-Proc cmdlet (described in [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md)).</span></span>

<span data-ttu-id="fc71a-104">Этот командлет Stop-Proc пытается остановить процессы, которые можно получить с помощью командлета Get-Proc (описано в разделе [Создание свой первый командлет](./creating-a-cmdlet-without-parameters.md)).</span><span class="sxs-lookup"><span data-stu-id="fc71a-104">This Stop-Proc cmdlet attempts to stop processes that are retrieved using the Get-Proc cmdlet (described in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md)).</span></span>

<span data-ttu-id="fc71a-105">Следующие подразделы этого раздела.</span><span class="sxs-lookup"><span data-stu-id="fc71a-105">Topics in this section include the following:</span></span>

- [<span data-ttu-id="fc71a-106">Определение командлета</span><span class="sxs-lookup"><span data-stu-id="fc71a-106">Defining the Cmdlet</span></span>](#Defining-the-Cmdlet)

- [<span data-ttu-id="fc71a-107">Определение параметров для изменения системы</span><span class="sxs-lookup"><span data-stu-id="fc71a-107">Defining Parameters for System Modification</span></span>](#Defining-Parameters-for-System-Modification)

- [<span data-ttu-id="fc71a-108">Определение псевдоним параметра</span><span class="sxs-lookup"><span data-stu-id="fc71a-108">Defining a Parameter Alias</span></span>](#Defining-a-Parameter-Alias)

- [<span data-ttu-id="fc71a-109">Создание справки для параметров</span><span class="sxs-lookup"><span data-stu-id="fc71a-109">Creating Help for Parameters</span></span>](#Creating-Help-for-Parameters)

- [<span data-ttu-id="fc71a-110">Переопределив метод обработки входных данных</span><span class="sxs-lookup"><span data-stu-id="fc71a-110">Overriding an Input Processing Method</span></span>](#Overriding-an-Input-Processing-Method)

- [<span data-ttu-id="fc71a-111">Поддержка подстановочных знаков</span><span class="sxs-lookup"><span data-stu-id="fc71a-111">Supporting Wildcard Expansion</span></span>](#Supporting-Wildcard-Expansion)

- [<span data-ttu-id="fc71a-112">Пример кода</span><span class="sxs-lookup"><span data-stu-id="fc71a-112">Code Sample</span></span>](#Defining-a-Parameter-Alias)

- [<span data-ttu-id="fc71a-113">Определение типов объектов и форматирование</span><span class="sxs-lookup"><span data-stu-id="fc71a-113">Defining Object Types and Formatting</span></span>](#Define-Object-Types-and-Formatting)

- [<span data-ttu-id="fc71a-114">Создание командлета</span><span class="sxs-lookup"><span data-stu-id="fc71a-114">Building the Cmdlet</span></span>](#Building-the-Cmdlet)

- [<span data-ttu-id="fc71a-115">Тестирование командлет</span><span class="sxs-lookup"><span data-stu-id="fc71a-115">Testing the Cmdlet</span></span>](#Testing-the-Cmdlet)

## <a name="defining-the-cmdlet"></a><span data-ttu-id="fc71a-116">Определение командлета</span><span class="sxs-lookup"><span data-stu-id="fc71a-116">Defining the Cmdlet</span></span>

<span data-ttu-id="fc71a-117">Первым шагом в создании командлет всегда присвоение имени командлета и объявление класса .NET, который реализует командлет.</span><span class="sxs-lookup"><span data-stu-id="fc71a-117">The first step in cmdlet creation is always naming the cmdlet and declaring the .NET class that implements the cmdlet.</span></span> <span data-ttu-id="fc71a-118">Так как вы записываете командлета для изменения системы, его имя должно соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="fc71a-118">Because you are writing a cmdlet to change the system, it should be named accordingly.</span></span> <span data-ttu-id="fc71a-119">Так как этот командлет останавливает системные процессы, используется команда «Stop», определяемый [System.Management.Automation.Verbslifecycle](/dotnet/api/System.Management.Automation.VerbsLifeCycle) класс с существительным «Proc», чтобы указать процесс.</span><span class="sxs-lookup"><span data-stu-id="fc71a-119">Because this cmdlet stops system processes, it uses the verb "Stop", defined by the [System.Management.Automation.Verbslifecycle](/dotnet/api/System.Management.Automation.VerbsLifeCycle) class, with the noun "Proc" to indicate process.</span></span> <span data-ttu-id="fc71a-120">Дополнительные сведения о командлет утвержденные глаголы, см. в разделе [имен команд командлет](./approved-verbs-for-windows-powershell-commands.md).</span><span class="sxs-lookup"><span data-stu-id="fc71a-120">For more information about approved cmdlet verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="fc71a-121">Следующий код является определение класса для этого командлета Stop-Proc.</span><span class="sxs-lookup"><span data-stu-id="fc71a-121">The following code is the class definition for this Stop-Proc cmdlet.</span></span>

```csharp
[Cmdlet(VerbsLifecycle.Stop, "proc",
        SupportsShouldProcess = true)]
public class StopProcCommand : Cmdlet
```

## <a name="defining-parameters-for-system-modification"></a><span data-ttu-id="fc71a-122">Определение параметров для изменения системы</span><span class="sxs-lookup"><span data-stu-id="fc71a-122">Defining Parameters for System Modification</span></span>

<span data-ttu-id="fc71a-123">Командлет необходимо определить параметры, что изменения системы поддержки и отзывы пользователей.</span><span class="sxs-lookup"><span data-stu-id="fc71a-123">Your cmdlet needs to define parameters that support system modifications and user feedback.</span></span> <span data-ttu-id="fc71a-124">Командлет необходимо определить `Name` параметр или эквивалент, чтобы командлет, смогут изменять параметры системы в каком-то идентификатора.</span><span class="sxs-lookup"><span data-stu-id="fc71a-124">The cmdlet should define a `Name` parameter or equivalent so that the cmdlet will be able to modify the system by some sort of identifier.</span></span> <span data-ttu-id="fc71a-125">Кроме того, следует определить командлет `Force` и `PassThru` параметров.</span><span class="sxs-lookup"><span data-stu-id="fc71a-125">In addition, the cmdlet should define the `Force` and `PassThru` parameters.</span></span> <span data-ttu-id="fc71a-126">Дополнительные сведения об этих параметрах см. в разделе [Создание командлет, который изменяет система](./creating-a-cmdlet-that-modifies-the-system.md).</span><span class="sxs-lookup"><span data-stu-id="fc71a-126">For more information about these parameters, see [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md).</span></span>

## <a name="defining-a-parameter-alias"></a><span data-ttu-id="fc71a-127">Определение псевдоним параметра</span><span class="sxs-lookup"><span data-stu-id="fc71a-127">Defining a Parameter Alias</span></span>

<span data-ttu-id="fc71a-128">Псевдоним параметра может быть альтернативное имя или четко определенных буква 1 или 2-буква короткое имя для параметра командлета.</span><span class="sxs-lookup"><span data-stu-id="fc71a-128">A parameter alias can be an alternate name or a well-defined 1-letter or 2-letter short name for a cmdlet parameter.</span></span> <span data-ttu-id="fc71a-129">В обоих случаях использования псевдонимов призван упростить ввод пользователя из командной строки.</span><span class="sxs-lookup"><span data-stu-id="fc71a-129">In both cases, the goal of using aliases is to simplify user entry from the command line.</span></span> <span data-ttu-id="fc71a-130">Windows PowerShell поддерживает псевдонимы параметра с помощью [System.Management.Automation.Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute) атрибут, который использует синтаксис объявления [Alias()].</span><span class="sxs-lookup"><span data-stu-id="fc71a-130">Windows PowerShell supports parameter aliases through the [System.Management.Automation.Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute) attribute, which uses the declaration syntax [Alias()].</span></span>

<span data-ttu-id="fc71a-131">В следующем коде показано, как добавляется псевдоним `Name` параметра.</span><span class="sxs-lookup"><span data-stu-id="fc71a-131">The following code shows how an alias is added to the `Name` parameter.</span></span>

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

<span data-ttu-id="fc71a-132">Помимо использования [System.Management.Automation.Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute) атрибутов, среда выполнения Windows PowerShell выполняет частичное сопоставление имен, даже если псевдонимы не указаны.</span><span class="sxs-lookup"><span data-stu-id="fc71a-132">In addition to using the [System.Management.Automation.Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute) attribute, the Windows PowerShell runtime performs partial name matching, even if no aliases are specified.</span></span> <span data-ttu-id="fc71a-133">Например, если есть командлет `FileName` параметр и это единственный параметр, который начинается с `F`, пользователь может вводить `Filename`, `Filenam`, `File`, `Fi`, или `F` и по-прежнему распознавания записи в виде `FileName` параметра.</span><span class="sxs-lookup"><span data-stu-id="fc71a-133">For example, if your cmdlet has a `FileName` parameter and that is the only parameter that starts with `F`, the user could enter `Filename`, `Filenam`, `File`, `Fi`, or `F` and still recognize the entry as the `FileName` parameter.</span></span>

## <a name="creating-help-for-parameters"></a><span data-ttu-id="fc71a-134">Создание справки для параметров</span><span class="sxs-lookup"><span data-stu-id="fc71a-134">Creating Help for Parameters</span></span>

<span data-ttu-id="fc71a-135">Windows PowerShell позволяет создать справки для параметров командлета.</span><span class="sxs-lookup"><span data-stu-id="fc71a-135">Windows PowerShell allows you to create Help for cmdlet parameters.</span></span> <span data-ttu-id="fc71a-136">Это необходимо сделайте для любого параметра, используемое для изменения и сбора отзывов системы.</span><span class="sxs-lookup"><span data-stu-id="fc71a-136">Do this for any parameter used for system modification and user feedback.</span></span> <span data-ttu-id="fc71a-137">Для каждого параметра, для поддержки справки, можно задать `HelpMessage` атрибута ключевое слово в [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) объявление атрибута.</span><span class="sxs-lookup"><span data-stu-id="fc71a-137">For each parameter to support Help, you can set the `HelpMessage` attribute keyword in the [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute declaration.</span></span> <span data-ttu-id="fc71a-138">Это ключевое слово определяет текст, отображаемый пользователю для помощи в с помощью параметра.</span><span class="sxs-lookup"><span data-stu-id="fc71a-138">This keyword defines the text to display to the user for assistance in using the parameter.</span></span> <span data-ttu-id="fc71a-139">Можно также задать `HelpMessageBaseName` ключевое слово, чтобы определить базовое имя ресурса будет использоваться для сообщения.</span><span class="sxs-lookup"><span data-stu-id="fc71a-139">You can also set the `HelpMessageBaseName` keyword to identify the base name of a resource to use for the message.</span></span> <span data-ttu-id="fc71a-140">Если это ключевое слово, необходимо также задать `HelpMessageResourceId` ключевое слово, чтобы указать идентификатор ресурса.</span><span class="sxs-lookup"><span data-stu-id="fc71a-140">If you set this keyword, you must also set the `HelpMessageResourceId` keyword to specify the resource identifier.</span></span>

<span data-ttu-id="fc71a-141">Следующий код из этого командлета Stop-Proc определяет `HelpMessage` ключевое слово для атрибута `Name` параметра.</span><span class="sxs-lookup"><span data-stu-id="fc71a-141">The following code from this Stop-Proc cmdlet defines the `HelpMessage` attribute keyword for the `Name` parameter.</span></span>

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

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="fc71a-142">Переопределив метод обработки входных данных</span><span class="sxs-lookup"><span data-stu-id="fc71a-142">Overriding an Input Processing Method</span></span>

<span data-ttu-id="fc71a-143">Командлет необходимо переопределить метод обработки входных данных, чаще всего это будет [System.Management.Automation.Cmdlet.Processrecord\*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord).</span><span class="sxs-lookup"><span data-stu-id="fc71a-143">Your cmdlet must override an input processing method, most often this will be [System.Management.Automation.Cmdlet.Processrecord\*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord).</span></span> <span data-ttu-id="fc71a-144">При изменении в системе, следует вызвать командлет [System.Management.Automation.Cmdlet.Shouldprocess\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) и [System.Management.Automation.Cmdlet.Shouldcontinue\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) методы, позволяющие пользователь, чтобы отправить отзыв, прежде чем изменения.</span><span class="sxs-lookup"><span data-stu-id="fc71a-144">When modifying the system, the cmdlet should call the [System.Management.Automation.Cmdlet.Shouldprocess\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.Shouldcontinue\*](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) methods to allow the user to provide feedback before a change is made.</span></span> <span data-ttu-id="fc71a-145">Дополнительные сведения об этих методах см. в разделе [Создание командлет, который изменяет система](./creating-a-cmdlet-that-modifies-the-system.md).</span><span class="sxs-lookup"><span data-stu-id="fc71a-145">For more information about these methods, see [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md).</span></span>

## <a name="supporting-wildcard-expansion"></a><span data-ttu-id="fc71a-146">Поддержка подстановочных знаков</span><span class="sxs-lookup"><span data-stu-id="fc71a-146">Supporting Wildcard Expansion</span></span>

<span data-ttu-id="fc71a-147">Чтобы разрешить выбор нескольких объектов, можно использовать командлет [System.Management.Automation.Wildcardpattern](/dotnet/api/System.Management.Automation.WildcardPattern) и [System.Management.Automation.Wildcardoptions](/dotnet/api/System.Management.Automation.WildcardOptions) классам предоставлять Поддержка расширения подстановочный знак для входного параметра.</span><span class="sxs-lookup"><span data-stu-id="fc71a-147">To allow the selection of multiple objects, your cmdlet can use the [System.Management.Automation.Wildcardpattern](/dotnet/api/System.Management.Automation.WildcardPattern) and [System.Management.Automation.Wildcardoptions](/dotnet/api/System.Management.Automation.WildcardOptions) classes to provide wildcard expansion support for parameter input.</span></span> <span data-ttu-id="fc71a-148">Примеры шаблонов с подстановочными знаками — lsa \* \*txt и [a-c]\*.</span><span class="sxs-lookup"><span data-stu-id="fc71a-148">Examples of wildcard patterns are lsa\*, \*.txt, and [a-c]\*.</span></span> <span data-ttu-id="fc71a-149">Используйте символ обратной кавычки (') как escape-символ, если шаблон содержит символ, который должен использоваться буквально.</span><span class="sxs-lookup"><span data-stu-id="fc71a-149">Use the back-quote character (\`) as an escape character when the pattern contains a character that should be used literally.</span></span>

<span data-ttu-id="fc71a-150">Подстановочный знак расширения имен файлов и путь приведены примеры распространенных сценариев, где командлета может потребоваться предоставить для входных данных путь к службе технической поддержки при необходимости выделения нескольких объектов.</span><span class="sxs-lookup"><span data-stu-id="fc71a-150">Wildcard expansions of file and path names are examples of common scenarios where the cmdlet may want to allow support for path inputs when the selection of multiple objects is required.</span></span> <span data-ttu-id="fc71a-151">Распространенным вариантом является в файловой системе, где пользователь хочет видеть все файлы, находящиеся в текущей папке.</span><span class="sxs-lookup"><span data-stu-id="fc71a-151">A common case is in the file system, where a user wants to see all files residing in the current folder.</span></span>

<span data-ttu-id="fc71a-152">Реализацию соответствующий шаблон настроенный шаблон нужен лишь изредка.</span><span class="sxs-lookup"><span data-stu-id="fc71a-152">You should need a customized wildcard pattern matching implementation only rarely.</span></span> <span data-ttu-id="fc71a-153">В этом случае командлет должен поддерживать полный 1003.2 POSIX, 3,13 спецификации для подстановочных знаков или Следующий упрощенный набор:</span><span class="sxs-lookup"><span data-stu-id="fc71a-153">In this case, your cmdlet should support either the full POSIX 1003.2, 3.13 specification for wildcard expansion or the following simplified subset:</span></span>

- <span data-ttu-id="fc71a-154">**Вопросительный знак (?).**</span><span class="sxs-lookup"><span data-stu-id="fc71a-154">**Question mark (?).**</span></span> <span data-ttu-id="fc71a-155">Соответствует любому символу в указанном расположении.</span><span class="sxs-lookup"><span data-stu-id="fc71a-155">Matches any character at the specified location.</span></span>

- <span data-ttu-id="fc71a-156">**Звездочка (\*).**</span><span class="sxs-lookup"><span data-stu-id="fc71a-156">**Asterisk (\*).**</span></span> <span data-ttu-id="fc71a-157">Совпадает с нуля или более символов, начиная с указанной позиции.</span><span class="sxs-lookup"><span data-stu-id="fc71a-157">Matches zero or more characters starting at the specified location.</span></span>

- <span data-ttu-id="fc71a-158">**Открывающая скобка ([]).**</span><span class="sxs-lookup"><span data-stu-id="fc71a-158">**Open bracket ([).**</span></span> <span data-ttu-id="fc71a-159">Представляет выражение в квадратных скобках шаблон, содержащий символы или диапазона символов.</span><span class="sxs-lookup"><span data-stu-id="fc71a-159">Introduces a pattern bracket expression that can contain characters or a range of characters.</span></span> <span data-ttu-id="fc71a-160">Если требуется диапазон, дефис (-) используется для указания диапазона.</span><span class="sxs-lookup"><span data-stu-id="fc71a-160">If a range is required, a hyphen (-) is used to indicate the range.</span></span>

- <span data-ttu-id="fc71a-161">**Закрывающая скобка (]).**</span><span class="sxs-lookup"><span data-stu-id="fc71a-161">**Close bracket (]).**</span></span> <span data-ttu-id="fc71a-162">Завершает выражение в квадратных скобках шаблон.</span><span class="sxs-lookup"><span data-stu-id="fc71a-162">Ends a pattern bracket expression.</span></span>

- <span data-ttu-id="fc71a-163">**Обратной кавычки escape-символ (').**</span><span class="sxs-lookup"><span data-stu-id="fc71a-163">**Back-quote escape character (\`).**</span></span> <span data-ttu-id="fc71a-164">Указывает, что следующий символ должен восприниматься буквально.</span><span class="sxs-lookup"><span data-stu-id="fc71a-164">Indicates that the next character should be taken literally.</span></span> <span data-ttu-id="fc71a-165">Имейте в виду, что при указании символ обратной кавычки из командной строки (в отличие от указания программным способом), обратной кавычки escape-символа должно быть указано два раза.</span><span class="sxs-lookup"><span data-stu-id="fc71a-165">Be aware that when specifying the back-quote character from the command line (as opposed to specifying it programmatically), the back-quote escape character must be specified twice.</span></span>

> [!NOTE]
> <span data-ttu-id="fc71a-166">Дополнительные сведения о шаблоны с подстановочными знаками, см. в разделе [Поддержка подстановочных знаков в параметры командлета](./supporting-wildcard-characters-in-cmdlet-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="fc71a-166">For more information about wildcard patterns, see [Supporting Wildcards in Cmdlet Parameters](./supporting-wildcard-characters-in-cmdlet-parameters.md).</span></span>

<span data-ttu-id="fc71a-167">Ниже показано, как настроить параметры шаблонов и определить шаблон подстановочного знака, используемую для разрешения `Name` параметр для этого командлета.</span><span class="sxs-lookup"><span data-stu-id="fc71a-167">The following code shows how to set wildcard options and define the wildcard pattern used for resolving the `Name` parameter for this cmdlet.</span></span>

```csharp
WildcardOptions options = WildcardOptions.IgnoreCase |
                          WildcardOptions.Compiled;
WildcardPattern wildcard = new WildcardPattern(name,options);
```

<span data-ttu-id="fc71a-168">Приведенный ниже показано, как для проверки того, соответствует ли имя процесса определенный шаблон.</span><span class="sxs-lookup"><span data-stu-id="fc71a-168">The following code shows how to test whether the process name matches the defined wildcard pattern.</span></span> <span data-ttu-id="fc71a-169">Обратите внимание на то, что, в этом случае, если имя процесса не соответствует шаблону, командлет продолжает на получить имя следующего процесса.</span><span class="sxs-lookup"><span data-stu-id="fc71a-169">Notice that, in this case, if the process name does not match the pattern, the cmdlet continues on to get the next process name.</span></span>

```csharp
if (!wildcard.IsMatch(processName))
{
  continue;
}
```

## <a name="code-sample"></a><span data-ttu-id="fc71a-170">Пример кода</span><span class="sxs-lookup"><span data-stu-id="fc71a-170">Code Sample</span></span>

<span data-ttu-id="fc71a-171">Для полной C# пример кода, см. в разделе [пример StopProcessSample03](./stopprocesssample03-sample.md).</span><span class="sxs-lookup"><span data-stu-id="fc71a-171">For the complete C# sample code, see [StopProcessSample03 Sample](./stopprocesssample03-sample.md).</span></span>

## <a name="define-object-types-and-formatting"></a><span data-ttu-id="fc71a-172">Определение типов объектов и форматирования</span><span class="sxs-lookup"><span data-stu-id="fc71a-172">Define Object Types and Formatting</span></span>

<span data-ttu-id="fc71a-173">Windows PowerShell передает данные между командлетами, используя объекты .net.</span><span class="sxs-lookup"><span data-stu-id="fc71a-173">Windows PowerShell passes information between cmdlets using .Net objects.</span></span> <span data-ttu-id="fc71a-174">Следовательно командлета может потребоваться определить его собственного типа, или командлет может потребоваться расширить существующий тип предоставляемые другому командлету.</span><span class="sxs-lookup"><span data-stu-id="fc71a-174">Consequently, a cmdlet may need to define its own type, or the cmdlet may need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="fc71a-175">Дополнительные сведения о определение новых типов или расширения существующих типов, см. в разделе [расширение типов объектов и форматирование](https://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351).</span><span class="sxs-lookup"><span data-stu-id="fc71a-175">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](https://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="fc71a-176">Создание командлета</span><span class="sxs-lookup"><span data-stu-id="fc71a-176">Building the Cmdlet</span></span>

<span data-ttu-id="fc71a-177">После реализации командлета, его необходимо зарегистрировать с помощью Windows PowerShell через оснастку Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fc71a-177">After implementing a cmdlet, it must be registered with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="fc71a-178">Дополнительные сведения о регистрации командлетов см. в разделе [как регистрация командлетов, поставщиков и ведущих приложений](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).</span><span class="sxs-lookup"><span data-stu-id="fc71a-178">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="fc71a-179">Тестирование командлет</span><span class="sxs-lookup"><span data-stu-id="fc71a-179">Testing the Cmdlet</span></span>

<span data-ttu-id="fc71a-180">При командлета был зарегистрирован с помощью Windows PowerShell, его можно проверить, запустив его в командной строке.</span><span class="sxs-lookup"><span data-stu-id="fc71a-180">When your cmdlet has been registered with Windows PowerShell, you can test it by running it on the command line.</span></span> <span data-ttu-id="fc71a-181">Давайте протестируем командлет Stop-Proc образец.</span><span class="sxs-lookup"><span data-stu-id="fc71a-181">Let's test the sample Stop-Proc cmdlet.</span></span> <span data-ttu-id="fc71a-182">Дополнительные сведения об использовании командлетов из командной строки см. в разделе [Приступая к работе с Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="fc71a-182">For more information about using cmdlets from the command line, see the [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span></span>

- <span data-ttu-id="fc71a-183">Запустите Windows PowerShell и используйте Stop-Proc остановить процесс, использующий ProcessName псевдоним `Name` параметра.</span><span class="sxs-lookup"><span data-stu-id="fc71a-183">Start Windows PowerShell and use Stop-Proc to stop a process using the ProcessName alias for the `Name` parameter.</span></span>

    ```powershell
    PS> stop-proc -ProcessName notepad
    ```

<span data-ttu-id="fc71a-184">Появляется следующий результат.</span><span class="sxs-lookup"><span data-stu-id="fc71a-184">The following output appears.</span></span>

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (3496)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    ```

- <span data-ttu-id="fc71a-185">Создайте следующую запись в командной строке.</span><span class="sxs-lookup"><span data-stu-id="fc71a-185">Make the following entry on the command line.</span></span> <span data-ttu-id="fc71a-186">Так как параметр Name является обязательным, запросит его.</span><span class="sxs-lookup"><span data-stu-id="fc71a-186">Because the Name parameter is mandatory, you are prompted for it.</span></span> <span data-ttu-id="fc71a-187">Введите «!?»</span><span class="sxs-lookup"><span data-stu-id="fc71a-187">Entering "!?"</span></span> <span data-ttu-id="fc71a-188">появится текст справки, связанный с параметром.</span><span class="sxs-lookup"><span data-stu-id="fc71a-188">brings up the help text associated with the parameter.</span></span>

    ```powershell
    PS> stop-proc
    ```

<span data-ttu-id="fc71a-189">Появляется следующий результат.</span><span class="sxs-lookup"><span data-stu-id="fc71a-189">The following output appears.</span></span>

    ```
    Cmdlet stop-proc at command pipeline position 1
    Supply values for the following parameters:
    (Type !? for Help.)
    Name[0]: !?
    The name of one or more processes to stop. Wildcards are permitted.
    Name[0]: notepad
    ```

- <span data-ttu-id="fc71a-190">Теперь создайте следующую запись, чтобы остановить все процессы, которые соответствуют Шаблон подстановочного знака «\* Примечание\*«.</span><span class="sxs-lookup"><span data-stu-id="fc71a-190">Now make the following entry to stop all processes that match the wildcard pattern "\*note\*".</span></span> <span data-ttu-id="fc71a-191">Вам предлагается перед остановкой каждого процесса, которая соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="fc71a-191">You are prompted before stopping each process that matches the pattern.</span></span>

    ```powershell
    PS> stop-proc -Name *note*
    ```

<span data-ttu-id="fc71a-192">Появляется следующий результат.</span><span class="sxs-lookup"><span data-stu-id="fc71a-192">The following output appears.</span></span>

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (1112)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    ```

<span data-ttu-id="fc71a-193">Появляется следующий результат.</span><span class="sxs-lookup"><span data-stu-id="fc71a-193">The following output appears.</span></span>

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "ONENOTEM (3712)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

<span data-ttu-id="fc71a-194">Появляется следующий результат.</span><span class="sxs-lookup"><span data-stu-id="fc71a-194">The following output appears.</span></span>

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "ONENOTE (3592)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

## <a name="see-also"></a><span data-ttu-id="fc71a-195">См. также</span><span class="sxs-lookup"><span data-stu-id="fc71a-195">See Also</span></span>

[<span data-ttu-id="fc71a-196">Создать командлет, который изменяет системы</span><span class="sxs-lookup"><span data-stu-id="fc71a-196">Create a Cmdlet that Modifies the System</span></span>](./creating-a-cmdlet-that-modifies-the-system.md)

[<span data-ttu-id="fc71a-197">Как создать командлет Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fc71a-197">How to Create a Windows PowerShell Cmdlet</span></span>](https://msdn.microsoft.com/en-us/0d721742-c849-4d0d-964f-78ddd9cd258c)

[<span data-ttu-id="fc71a-198">Расширение типов объектов и форматирование</span><span class="sxs-lookup"><span data-stu-id="fc71a-198">Extending Object Types and Formatting</span></span>](https://msdn.microsoft.com/en-us/da976d91-a3d6-44e8-affa-466b1e2bd351)

[<span data-ttu-id="fc71a-199">Регистрация командлетов, поставщиков и ведущих приложений</span><span class="sxs-lookup"><span data-stu-id="fc71a-199">How to Register Cmdlets, Providers, and Host Applications</span></span>](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[<span data-ttu-id="fc71a-200">Поддержка подстановочных знаков в параметры командлета</span><span class="sxs-lookup"><span data-stu-id="fc71a-200">Supporting Wildcards in Cmdlet Parameters</span></span>](./supporting-wildcard-characters-in-cmdlet-parameters.md)

[<span data-ttu-id="fc71a-201">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fc71a-201">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
