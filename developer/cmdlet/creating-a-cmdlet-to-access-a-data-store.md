---
title: Создание командлету, чтобы получить доступ к Store данных | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ea15e00e-20dc-4209-9e97-9ffd763e5d97
caps.latest.revision: 8
ms.openlocfilehash: 28d55874960f9a64b986204411d38319ef1d0da7
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "58059530"
---
# <a name="creating-a-cmdlet-to-access-a-data-store"></a><span data-ttu-id="09f6b-102">Создание командлета для доступа к хранилищу данных</span><span class="sxs-lookup"><span data-stu-id="09f6b-102">Creating a Cmdlet to Access a Data Store</span></span>

<span data-ttu-id="09f6b-103">В этом разделе описывается, как создать командлет, который обращается к хранимых данных посредством поставщика Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="09f6b-103">This section describes how to create a cmdlet that accesses stored data by way of a Windows PowerShell provider.</span></span> <span data-ttu-id="09f6b-104">Этот тип командлет использует инфраструктуру поставщика Windows PowerShell среды выполнения Windows PowerShell, и, таким образом, класс командлета должен быть производным от [System.Management.Automation.PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) базового класса.</span><span class="sxs-lookup"><span data-stu-id="09f6b-104">This type of cmdlet uses the Windows PowerShell provider infrastructure of the Windows PowerShell runtime and, therefore, the cmdlet class must derive from the [System.Management.Automation.PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) base class.</span></span>

<span data-ttu-id="09f6b-105">Командлет Select-Str, описанные здесь можно найти и выбрать строки в файл или в объекте.</span><span class="sxs-lookup"><span data-stu-id="09f6b-105">The Select-Str cmdlet described here can locate and select strings in a file or object.</span></span> <span data-ttu-id="09f6b-106">Шаблоны, используемые для определения строки, которые можно задать явным образом с помощью `Path` параметр командлета или неявно через `Script` параметра.</span><span class="sxs-lookup"><span data-stu-id="09f6b-106">The patterns used to identify the string can be specified explicitly through the `Path` parameter of the cmdlet or implicitly through the `Script` parameter.</span></span>

<span data-ttu-id="09f6b-107">Командлет предназначен для использования любым поставщиком Windows PowerShell, который является производным от [System.Management.Automation.Provider.Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider).</span><span class="sxs-lookup"><span data-stu-id="09f6b-107">The cmdlet is designed to use any Windows PowerShell provider that derives from [System.Management.Automation.Provider.Icontentcmdletprovider](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider).</span></span> <span data-ttu-id="09f6b-108">Например командлет можно указать поставщика FileSystem или поставщик Variable, предоставляемый Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="09f6b-108">For example, the cmdlet can specify the FileSystem provider or the Variable provider that is provided by Windows PowerShell.</span></span> <span data-ttu-id="09f6b-109">Дополнительные сведения о aboutWindows поставщики PowerShell, см. в разделе [поставщика проектирование Your Windows PowerShell](../prog-guide/designing-your-windows-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="09f6b-109">For more information aboutWindows PowerShell providers, see [Designing Your Windows PowerShell provider](../prog-guide/designing-your-windows-powershell-provider.md).</span></span>

<span data-ttu-id="09f6b-110">Следующие подразделы этого раздела.</span><span class="sxs-lookup"><span data-stu-id="09f6b-110">Topics in this section include the following:</span></span>

- [<span data-ttu-id="09f6b-111">Определение класса командлета</span><span class="sxs-lookup"><span data-stu-id="09f6b-111">Defining the Cmdlet Class</span></span>](#Defining-the-Cmdlet-Class)

- [<span data-ttu-id="09f6b-112">Определение параметров для доступа к данным</span><span class="sxs-lookup"><span data-stu-id="09f6b-112">Defining Parameters for Data Access</span></span>](#Declaring-the-Path-Parameter)

- [<span data-ttu-id="09f6b-113">Переопределяя методы обработки ввода</span><span class="sxs-lookup"><span data-stu-id="09f6b-113">Overriding Input Processing Methods</span></span>](#Overriding-Input-Processing-Methods)

- [<span data-ttu-id="09f6b-114">Доступ к содержимому</span><span class="sxs-lookup"><span data-stu-id="09f6b-114">Accessing Content</span></span>](#Accessing-Content)

- [<span data-ttu-id="09f6b-115">Пример кода</span><span class="sxs-lookup"><span data-stu-id="09f6b-115">Code Sample</span></span>](#Code-Sample)

- [<span data-ttu-id="09f6b-116">Определение типов объектов и форматирование</span><span class="sxs-lookup"><span data-stu-id="09f6b-116">Defining Object Types and Formatting</span></span>](#Declaring-Search-Support-Parameters)

- [<span data-ttu-id="09f6b-117">Создание командлета</span><span class="sxs-lookup"><span data-stu-id="09f6b-117">Building the Cmdlet</span></span>](#Building-the-Cmdlet)

- [<span data-ttu-id="09f6b-118">Тестирование командлет</span><span class="sxs-lookup"><span data-stu-id="09f6b-118">Testing the Cmdlet</span></span>](#Testing-the-Cmdlet)

## <a name="defining-the-cmdlet-class"></a><span data-ttu-id="09f6b-119">Определение класса командлета</span><span class="sxs-lookup"><span data-stu-id="09f6b-119">Defining the Cmdlet Class</span></span>

<span data-ttu-id="09f6b-120">Первым шагом в создании командлет всегда присвоение имени командлета и объявление класса .NET, который реализует командлет.</span><span class="sxs-lookup"><span data-stu-id="09f6b-120">The first step in cmdlet creation is always naming the cmdlet and declaring the .NET class that implements the cmdlet.</span></span> <span data-ttu-id="09f6b-121">Этот командлет обнаруживает определенные строки, поэтому имя команды, выбираем — «Выбрать», определяемый [System.Management.Automation.Verbscommon](/dotnet/api/System.Management.Automation.VerbsCommon) класса.</span><span class="sxs-lookup"><span data-stu-id="09f6b-121">This cmdlet detects certain strings, so the verb name chosen here is "Select", defined by the [System.Management.Automation.Verbscommon](/dotnet/api/System.Management.Automation.VerbsCommon) class.</span></span> <span data-ttu-id="09f6b-122">Имя существительное «Str» используется в том случае, так как командлет обрабатывает строки.</span><span class="sxs-lookup"><span data-stu-id="09f6b-122">The noun name "Str" is used because the cmdlet acts upon strings.</span></span> <span data-ttu-id="09f6b-123">В приведенном ниже объявлении Обратите внимание, что имя командлета глагол и существительное, отражаются в имени класса cmdlet.</span><span class="sxs-lookup"><span data-stu-id="09f6b-123">In the declaration below, note that the cmdlet verb and noun name are reflected in the name of the cmdlet class.</span></span> <span data-ttu-id="09f6b-124">Дополнительные сведения о командлет утвержденные глаголы, см. в разделе [имен команд командлет](./approved-verbs-for-windows-powershell-commands.md).</span><span class="sxs-lookup"><span data-stu-id="09f6b-124">For more information about approved cmdlet verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="09f6b-125">Для этого командлета класс .NET должен быть производным от [System.Management.Automation.PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) базового класса, в том случае, так как он поддерживает необходимый средой выполнения Windows PowerShell для предоставления поставщика Windows PowerShell инфраструктура.</span><span class="sxs-lookup"><span data-stu-id="09f6b-125">The .NET class for this cmdlet must derive from the [System.Management.Automation.PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) base class, because it provides the support needed by the Windows PowerShell runtime to expose the Windows PowerShell provider infrastructure.</span></span> <span data-ttu-id="09f6b-126">Обратите внимание, что этот командлет также позволяет использовать классов регулярных выражений .NET Framework, такие как [System.Text.Regularexpressions.Regex](/dotnet/api/System.Text.RegularExpressions.Regex).</span><span class="sxs-lookup"><span data-stu-id="09f6b-126">Note that this cmdlet also makes use of the .NET Framework regular expressions classes, such as [System.Text.Regularexpressions.Regex](/dotnet/api/System.Text.RegularExpressions.Regex).</span></span>

<span data-ttu-id="09f6b-127">Следующий код является определение класса для этого командлета Select-Str.</span><span class="sxs-lookup"><span data-stu-id="09f6b-127">The following code is the class definition for this Select-Str cmdlet.</span></span>

```csharp
[Cmdlet(VerbsCommon.Select, "Str", DefaultParameterSetName="PatternParameterSet")]
public class SelectStringCommand : PSCmdlet
```

<span data-ttu-id="09f6b-128">Этот командлет определяет параметр по умолчанию задается путем добавления `DefaultParameterSetName` атрибута ключевое слово к объявлению класса.</span><span class="sxs-lookup"><span data-stu-id="09f6b-128">This cmdlet defines a default parameter set by adding the `DefaultParameterSetName` attribute keyword to the class declaration.</span></span> <span data-ttu-id="09f6b-129">Набор параметров по умолчанию `PatternParameterSet` используется, если `Script` параметр не указан.</span><span class="sxs-lookup"><span data-stu-id="09f6b-129">The default parameter set `PatternParameterSet` is used when the `Script` parameter is not specified.</span></span> <span data-ttu-id="09f6b-130">Дополнительные сведения о этот набор параметров, см. в разделе `Pattern` и `Script` обсуждение параметр в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="09f6b-130">For more information about this parameter set, see the `Pattern` and `Script` parameter discussion in the following section.</span></span>

## <a name="defining-parameters-for-data-access"></a><span data-ttu-id="09f6b-131">Определение параметров для доступа к данным</span><span class="sxs-lookup"><span data-stu-id="09f6b-131">Defining Parameters for Data Access</span></span>

<span data-ttu-id="09f6b-132">Этот командлет определяет несколько параметров, которые пользователи могут проверить хранимых данных.</span><span class="sxs-lookup"><span data-stu-id="09f6b-132">This cmdlet defines several parameters that allow the user to access and examine stored data.</span></span> <span data-ttu-id="09f6b-133">Эти параметры включают в себя `Path` параметр, который указывает расположение хранилища данных, `Pattern` параметра, которое указывает шаблон, используемый при поиске и несколько других параметров, которые поддерживают как выполняется поиск.</span><span class="sxs-lookup"><span data-stu-id="09f6b-133">These parameters include a `Path` parameter that indicates the location of the data store, a `Pattern` parameter that specifies the pattern to be used in the search, and several other parameters that support how the search is performed.</span></span>

> [!NOTE]
> <span data-ttu-id="09f6b-134">Дополнительные сведения об основах определение параметров, см. в разделе [Добавление параметров командной строки этого процесса входа](./adding-parameters-that-process-command-line-input.md).</span><span class="sxs-lookup"><span data-stu-id="09f6b-134">For more information about the basics of defining parameters, see [Adding Parameters that Process Command Line Input](./adding-parameters-that-process-command-line-input.md).</span></span>

### <a name="declaring-the-path-parameter"></a><span data-ttu-id="09f6b-135">Объявление параметра Path</span><span class="sxs-lookup"><span data-stu-id="09f6b-135">Declaring the Path Parameter</span></span>

<span data-ttu-id="09f6b-136">Чтобы найти хранилище данных, этот командлет следует использовать путь Windows PowerShell для идентификации поставщика Windows PowerShell, предназначенный для доступа к хранилищу данных.</span><span class="sxs-lookup"><span data-stu-id="09f6b-136">To locate the data store, this cmdlet must use a Windows PowerShell path to identify the Windows PowerShell provider that is designed to access the data store.</span></span> <span data-ttu-id="09f6b-137">Таким образом, он определяет `Path` параметр типа массив строк, чтобы указать расположение поставщика.</span><span class="sxs-lookup"><span data-stu-id="09f6b-137">Therefore, it defines a `Path` parameter of type string array to indicate the location of the provider.</span></span>

```csharp
[Parameter(
           Position = 0,
           ParameterSetName = "ScriptParameterSet",
           Mandatory = true)]
[Parameter(
           Position = 0,
           ParameterSetName = "PatternParameterSet",
           ValueFromPipeline = true,
           Mandatory = true)]
           [Alias("PSPath")]
public string[] Path
{
  get { return paths; }
  set { paths = value; }
}
private string[] paths;
```

<span data-ttu-id="09f6b-138">Обратите внимание, что этот параметр относится к два разных набора параметров, содержащий псевдоним.</span><span class="sxs-lookup"><span data-stu-id="09f6b-138">Note that this parameter belongs to two different parameter sets and that it has an alias.</span></span>

<span data-ttu-id="09f6b-139">Два [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) атрибуты объявляют, `Path` параметр относится к `ScriptParameterSet` и `PatternParameterSet`.</span><span class="sxs-lookup"><span data-stu-id="09f6b-139">Two [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attributes declare that the `Path` parameter belongs to the `ScriptParameterSet` and the `PatternParameterSet`.</span></span> <span data-ttu-id="09f6b-140">Дополнительные сведения о наборах параметров см. в разделе [добавление наборов параметров для командлета](./adding-parameter-sets-to-a-cmdlet.md).</span><span class="sxs-lookup"><span data-stu-id="09f6b-140">For more information about parameter sets, see [Adding Parameter Sets to a Cmdlet](./adding-parameter-sets-to-a-cmdlet.md).</span></span>

<span data-ttu-id="09f6b-141">[System.Management.Automation.Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute) объявляет атрибут `PSPath` псевдоним для `Path` параметра.</span><span class="sxs-lookup"><span data-stu-id="09f6b-141">The [System.Management.Automation.Aliasattribute](/dotnet/api/System.Management.Automation.AliasAttribute) attribute declares a `PSPath` alias for the `Path` parameter.</span></span> <span data-ttu-id="09f6b-142">Объявление этот псевдоним, настоятельно рекомендуется для обеспечения согласованности с другими командлетами, получить доступ к поставщикам Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="09f6b-142">Declaring this alias is strongly recommended for consistency with other cmdlets that access Windows PowerShell providers.</span></span> <span data-ttu-id="09f6b-143">Дополнительные сведения о aboutWindows путей PowerShell, см. в разделе «Основные понятия путь PowerShell» в [как Windows PowerShell работает](https://msdn.microsoft.com/en-us/ced30e23-10af-4700-8933-49873bd84d58).</span><span class="sxs-lookup"><span data-stu-id="09f6b-143">For more information aboutWindows PowerShell paths, see "PowerShell Path Concepts" in [How Windows PowerShell Works](https://msdn.microsoft.com/en-us/ced30e23-10af-4700-8933-49873bd84d58).</span></span>

### <a name="declaring-the-pattern-parameter"></a><span data-ttu-id="09f6b-144">Объявление параметров шаблона</span><span class="sxs-lookup"><span data-stu-id="09f6b-144">Declaring the Pattern Parameter</span></span>

<span data-ttu-id="09f6b-145">Чтобы указать для шаблонов поиска, объявляет этот командлет `Pattern` параметр, который представляет собой массив строк.</span><span class="sxs-lookup"><span data-stu-id="09f6b-145">To specify the patterns to search for, this cmdlet declares a `Pattern` parameter that is an array of strings.</span></span> <span data-ttu-id="09f6b-146">Положительный результат возвращается в том случае, если любой из шаблонов находятся в хранилище данных.</span><span class="sxs-lookup"><span data-stu-id="09f6b-146">A positive result is returned when any of the patterns are found in the data store.</span></span> <span data-ttu-id="09f6b-147">Обратите внимание на то, что эти шаблоны можно скомпилировать в массив скомпилированные регулярные выражения или массив используется для поиска литерала шаблонов с подстановочными знаками.</span><span class="sxs-lookup"><span data-stu-id="09f6b-147">Note that these patterns can be compiled into an array of compiled regular expressions or an array of wildcard patterns used for literal searches.</span></span>

```csharp
[Parameter(
           Position = 1,
           ParameterSetName = "PatternParameterSet",
           Mandatory = true)]
public string[] Pattern
{
  get { return patterns; }
  set { patterns = value; }
}
private string[] patterns;
private Regex[] regexPattern;
private WildcardPattern[] wildcardPattern;
```

<span data-ttu-id="09f6b-148">Если этот параметр указан, командлет использует набор параметров по умолчанию `PatternParameterSet`.</span><span class="sxs-lookup"><span data-stu-id="09f6b-148">When this parameter is specified, the cmdlet uses the default parameter set `PatternParameterSet`.</span></span> <span data-ttu-id="09f6b-149">В этом случае командлет использует шаблоны, указанные здесь, чтобы выбрать строки.</span><span class="sxs-lookup"><span data-stu-id="09f6b-149">In this case, the cmdlet uses the patterns specified here to select strings.</span></span> <span data-ttu-id="09f6b-150">Напротив `Script` параметр может также использоваться для предоставления сценария, содержащего шаблоны.</span><span class="sxs-lookup"><span data-stu-id="09f6b-150">In contrast, the `Script` parameter could also be used to provide a script that contains the patterns.</span></span> <span data-ttu-id="09f6b-151">`Script` И `Pattern` параметры определяют две различные наборы параметров, поэтому они являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="09f6b-151">The `Script` and `Pattern` parameters define two separate parameter sets, so they are mutually exclusive.</span></span>

### <a name="declaring-search-support-parameters"></a><span data-ttu-id="09f6b-152">Объявление параметров поддержка поиска</span><span class="sxs-lookup"><span data-stu-id="09f6b-152">Declaring Search Support Parameters</span></span>

<span data-ttu-id="09f6b-153">Этот командлет определяет следующие параметры поддержки, которые могут использоваться для изменения возможности поиска в командлет.</span><span class="sxs-lookup"><span data-stu-id="09f6b-153">This cmdlet defines the following support parameters that can be used to modify the search capabilities of the cmdlet.</span></span>

<span data-ttu-id="09f6b-154">`Script` Параметр указывает блок скрипта, который может использоваться для предоставления механизма поиска альтернативного для командлета.</span><span class="sxs-lookup"><span data-stu-id="09f6b-154">The `Script` parameter specifies a script block that can be used to provide an alternate search mechanism for the cmdlet.</span></span> <span data-ttu-id="09f6b-155">Сценарий должен содержать шаблоны, используемые для сопоставления и вернуть [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) объекта.</span><span class="sxs-lookup"><span data-stu-id="09f6b-155">The script must contain the patterns used for matching and return a [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) object.</span></span> <span data-ttu-id="09f6b-156">Обратите внимание, что этот параметр также используется параметр unique командлета, определяющий `ScriptParameterSet` набор параметров.</span><span class="sxs-lookup"><span data-stu-id="09f6b-156">Note that this parameter is also the unique parameter that identifies the `ScriptParameterSet` parameter set.</span></span> <span data-ttu-id="09f6b-157">Когда среда выполнения Windows PowerShell обнаруживает этот параметр, он использует только те параметры, которые принадлежат `ScriptParameterSet` набор параметров.</span><span class="sxs-lookup"><span data-stu-id="09f6b-157">When the Windows PowerShell runtime sees this parameter, it uses only parameters that belong to the `ScriptParameterSet` parameter set.</span></span>

```csharp
[Parameter(
           Position = 1,
           ParameterSetName = "ScriptParameterSet",
           Mandatory = true)]
public ScriptBlock Script
{
  set { script = value; }
  get { return script; }
}
ScriptBlock script;
```

<span data-ttu-id="09f6b-158">`SimpleMatch` Параметр параметр-переключатель, указывающее, будет ли командлет явным образом соответствуют шаблонам, как они предоставляются.</span><span class="sxs-lookup"><span data-stu-id="09f6b-158">The `SimpleMatch` parameter is a switch parameter that indicates whether the cmdlet is to explicitly match the patterns as they are supplied.</span></span> <span data-ttu-id="09f6b-159">Когда пользователь задает параметр командной строки (`true`), командлет использует шаблоны, как они предоставляются.</span><span class="sxs-lookup"><span data-stu-id="09f6b-159">When the user specifies the parameter at the command line (`true`), the cmdlet uses the patterns as they are supplied.</span></span> <span data-ttu-id="09f6b-160">Если этот параметр не указан (`false`), командлет будет использовать регулярные выражения.</span><span class="sxs-lookup"><span data-stu-id="09f6b-160">If the parameter is not specified (`false`), the cmdlet uses regular expressions.</span></span> <span data-ttu-id="09f6b-161">Значение по умолчанию для этого параметра — `false`.</span><span class="sxs-lookup"><span data-stu-id="09f6b-161">The default for this parameter is `false`.</span></span>

```csharp
[Parameter]
public SwitchParameter SimpleMatch
{
  get { return simpleMatch; }
  set { simpleMatch = value; }
}
private bool simpleMatch;
```

<span data-ttu-id="09f6b-162">`CaseSensitive` Параметр параметр-переключатель, указывающее, выполняется ли поиск с учетом регистра.</span><span class="sxs-lookup"><span data-stu-id="09f6b-162">The `CaseSensitive` parameter is a switch parameter that indicates whether a case-sensitive search is performed.</span></span> <span data-ttu-id="09f6b-163">Когда пользователь задает параметр командной строки (`true`), командлет проверяет наличие прописных и строчных символов при сравнении шаблонов.</span><span class="sxs-lookup"><span data-stu-id="09f6b-163">When the user specifies the parameter at the command line (`true`), the cmdlet checks for the uppercase and lowercase of characters when comparing patterns.</span></span> <span data-ttu-id="09f6b-164">Если этот параметр не указан (`false`), командлет не различает верхнего и нижнего регистра.</span><span class="sxs-lookup"><span data-stu-id="09f6b-164">If the parameter is not specified (`false`), the cmdlet does not distinguish between uppercase and lowercase.</span></span> <span data-ttu-id="09f6b-165">Например «MyFile» и «myfile» оба возвращаются в виде положительного попаданий.</span><span class="sxs-lookup"><span data-stu-id="09f6b-165">For example "MyFile" and "myfile" would both be returned as positive hits.</span></span> <span data-ttu-id="09f6b-166">Значение по умолчанию для этого параметра — `false`.</span><span class="sxs-lookup"><span data-stu-id="09f6b-166">The default for this parameter is `false`.</span></span>

```csharp
[Parameter]
public SwitchParameter CaseSensitive
{
  get { return caseSensitive; }
  set { caseSensitive = value; }
}
private bool caseSensitive;
```

<span data-ttu-id="09f6b-167">`Exclude` И `Include` параметры определяют элементы, явно исключить из или включить в поиск.</span><span class="sxs-lookup"><span data-stu-id="09f6b-167">The `Exclude` and `Include` parameters identify items that are explicitly excluded from or included in the search.</span></span> <span data-ttu-id="09f6b-168">По умолчанию командлет выполняет поиск всех элементов в хранилище данных.</span><span class="sxs-lookup"><span data-stu-id="09f6b-168">By default, the cmdlet will search all items in the data store.</span></span> <span data-ttu-id="09f6b-169">Тем не менее чтобы ограничить поиск с помощью командлета, эти параметры можно использовать чтобы явно указать элементы, включаемые в поиск или опустить.</span><span class="sxs-lookup"><span data-stu-id="09f6b-169">However, to limit the search performed by the cmdlet, these parameters can be used to explicitly indicate items to be included in the search or omitted.</span></span>

```csharp
[Parameter]
public SwitchParameter CaseSensitive
{
  get { return caseSensitive; }
  set { caseSensitive = value; }
}
private bool caseSensitive;
```

```csharp
[Parameter]
[ValidateNotNullOrEmpty]
public string[] Include
{
  get
  {
    return includeStrings;
  }
  set
  {
    includeStrings = value;

    this.include = new WildcardPattern[includeStrings.Length];
    for (int i = 0; i < includeStrings.Length; i++)
    {
      this.include[i] = new WildcardPattern(includeStrings[i], WildcardOptions.IgnoreCase);
    }
  }
}

internal string[] includeStrings = null;
internal WildcardPattern[] include = null;
```

### <a name="declaring-parameter-sets"></a><span data-ttu-id="09f6b-170">Объявление наборов параметров</span><span class="sxs-lookup"><span data-stu-id="09f6b-170">Declaring Parameter Sets</span></span>

<span data-ttu-id="09f6b-171">Этот командлет использует два набора параметров (`ScriptParameterSet` и `PatternParameterSet`, который используется по умолчанию) вместо имен два набора параметров, используемых в доступ к данным.</span><span class="sxs-lookup"><span data-stu-id="09f6b-171">This cmdlet uses two parameter sets (`ScriptParameterSet` and `PatternParameterSet`, which is the default) as the names of two parameter sets used in data access.</span></span> <span data-ttu-id="09f6b-172">`PatternParameterSet` набор параметров по умолчанию, используемый, когда `Pattern` указан параметр.</span><span class="sxs-lookup"><span data-stu-id="09f6b-172">`PatternParameterSet` is the default parameter set and is used when the `Pattern` parameter is specified.</span></span> <span data-ttu-id="09f6b-173">`ScriptParameterSet` используется, когда пользователь указывает механизм поиска альтернативного через `Script` параметра.</span><span class="sxs-lookup"><span data-stu-id="09f6b-173">`ScriptParameterSet` is used when the user specifies an alternate search mechanism through the `Script` parameter.</span></span> <span data-ttu-id="09f6b-174">Дополнительные сведения о наборах параметров см. в разделе [добавление наборов параметров для командлета](./adding-parameter-sets-to-a-cmdlet.md).</span><span class="sxs-lookup"><span data-stu-id="09f6b-174">For more information about parameter sets, see [Adding Parameter Sets to a Cmdlet](./adding-parameter-sets-to-a-cmdlet.md).</span></span>

## <a name="overriding-input-processing-methods"></a><span data-ttu-id="09f6b-175">Переопределяя методы обработки ввода</span><span class="sxs-lookup"><span data-stu-id="09f6b-175">Overriding Input Processing Methods</span></span>

<span data-ttu-id="09f6b-176">Командлеты необходимо переопределить некоторые методы для обработки ввода [System.Management.Automation.PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) класса.</span><span class="sxs-lookup"><span data-stu-id="09f6b-176">Cmdlets must override one or more of the input processing methods for the [System.Management.Automation.PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) class.</span></span> <span data-ttu-id="09f6b-177">Дополнительные сведения о методы обработки входных данных, см. в разделе [Создание свой первый командлет](./creating-a-cmdlet-without-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="09f6b-177">For more information about the input processing methods, see [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md).</span></span>

<span data-ttu-id="09f6b-178">Этот командлет переопределяет [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) метод для создания массива скомпилированные регулярные выражения при запуске.</span><span class="sxs-lookup"><span data-stu-id="09f6b-178">This cmdlet overrides the [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method to build an array of compiled regular expressions at startup.</span></span> <span data-ttu-id="09f6b-179">Это увеличивает производительность при поиске по журналу, которые не используют простых совпадений.</span><span class="sxs-lookup"><span data-stu-id="09f6b-179">This increases performance during searches that do not use simple matching.</span></span>

```csharp
protected override void BeginProcessing()
{
  WriteDebug("Validating patterns.");
  if (patterns != null)
  {
    foreach(string pattern in patterns)
    {
      if (pattern == null)
      ThrowTerminatingError(new ErrorRecord(
                            new ArgumentNullException(
                            "Search pattern cannot be null."),
                            "NullSearchPattern",
                            ErrorCategory.InvalidArgument,
                            pattern)
                            );
    }

    WriteVerbose("Search pattern(s) are valid.");

    // If a simple match is not specified, then
    // compile the regular expressions once.
    if (!simpleMatch)
    {
      WriteDebug("Compiling search regular expressions.");

      RegexOptions regexOptions = RegexOptions.Compiled;
      if (!caseSensitive)
         regexOptions |= RegexOptions.Compiled;
      regexPattern = new Regex[patterns.Length];

      for (int i = 0; i < patterns.Length; i++)
      {
        try
        {
          regexPattern[i] = new Regex(patterns[i], regexOptions);
        }
        catch (ArgumentException ex)
        {
          ThrowTerminatingError(new ErrorRecord(
                        ex,
                        "InvalidRegularExpression",
                        ErrorCategory.InvalidArgument,
                        patterns[i]
                     ));
        }
      } //Loop through patterns to create RegEx objects.

      WriteVerbose("Pattern(s) compiled into regular expressions.");
    }// If not a simple match.

    // If a simple match is specified, then compile the
    // wildcard patterns once.
    else
    {
      WriteDebug("Compiling search wildcards.");

      WildcardOptions wildcardOptions = WildcardOptions.Compiled;

      if (!caseSensitive)
      {
        wildcardOptions |= WildcardOptions.IgnoreCase;
      }

      wildcardPattern = new WildcardPattern[patterns.Length];
      for (int i = 0; i < patterns.Length; i++)
      {
        wildcardPattern[i] =
                     new WildcardPattern(patterns[i], wildcardOptions);
      }

      WriteVerbose("Pattern(s) compiled into wildcard expressions.");
    }// If match is a simple match.
  }// If valid patterns are available.
}// End of function BeginProcessing().
```

<span data-ttu-id="09f6b-180">Этот командлет также переопределяет [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) метод для обработки строки, выбранные пользователем в командной строке.</span><span class="sxs-lookup"><span data-stu-id="09f6b-180">This cmdlet also overrides the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method to process the string selections that the user makes on the command line.</span></span> <span data-ttu-id="09f6b-181">Записывает результаты выбора строки в виде пользовательского объекта путем вызова закрытого **MatchString** метод.</span><span class="sxs-lookup"><span data-stu-id="09f6b-181">It writes the results of string selection in the form of a custom object by calling a private **MatchString** method.</span></span>

```csharp
protected override void ProcessRecord()
{
  UInt64 lineNumber = 0;
  MatchInfo result;
  ArrayList nonMatches = new ArrayList();

  // Walk the list of paths and search the contents for
  // any of the specified patterns.
  foreach (string psPath in paths)
  {
    // Once the filepaths are expanded, we may have more than one
    // path, so process all referenced paths.
    foreach(PathInfo path in
            SessionState.Path.GetResolvedPSPathFromPSPath(psPath)
           )
    {
      WriteVerbose("Processing path " + path.Path);

      // Check if the path represents one of the items to be
      // excluded. If so, continue to next path.
      if (!MeetsIncludeExcludeCriteria(path.ProviderPath))
         continue;

      // Get the content reader for the item(s) at the
      // specified path.
      Collection<IContentReader> readerCollection = null;
      try
      {
        readerCollection =
                    this.InvokeProvider.Content.GetReader(path.Path);
      }
      catch (PSNotSupportedException ex)
      {
        WriteError(new ErrorRecord(ex,
                   "ContentAccessNotSupported",
                    ErrorCategory.NotImplemented,
                    path.Path)
                   );
        return;
      }

      foreach(IContentReader reader in readerCollection)
      {
        // Reset the line number for this path.
        lineNumber = 0;

        // Read in a single block (line in case of a file)
        // from the object.
        IList items = reader.Read(1);

        // Read and process one block(line) at a time until
        // no more blocks(lines) exist.
        while (items != null && items.Count == 1)
        {
          // Increment the line number each time a line is
          // processed.
          lineNumber++;

          String message = String.Format("Testing line {0} : {1}",
                                        lineNumber, items[0]);

          WriteDebug(message);

          result = SelectString(items[0]);

          if (result != null)
          {
            result.Path = path.Path;
            result.LineNumber = lineNumber;

            WriteObject(result);
          }
          else
          {
            // Add the block(line) that did not match to the
            // collection of non matches , which will be stored
            // in the SessionState variable $NonMatches
            nonMatches.Add(items[0]);
          }

          // Get the next line from the object.
          items = reader.Read(1);

        }// While loop for reading one line at a time.
      }// Foreach loop for reader collection.
    }// Foreach loop for processing referenced paths.
  }// Foreach loop for walking of path list.

  // Store the list of non-matches in the
  // session state variable $NonMatches.
  try
  {
    this.SessionState.PSVariable.Set("NonMatches", nonMatches);
  }
  catch (SessionStateUnauthorizedAccessException ex)
  {
    WriteError(new ErrorRecord(ex,
               "CannotWriteVariableNonMatches",
               ErrorCategory.InvalidOperation,
               nonMatches)
              );
  }

}// End of protected override void ProcessRecord().
```

## <a name="accessing-content"></a><span data-ttu-id="09f6b-182">Доступ к содержимому</span><span class="sxs-lookup"><span data-stu-id="09f6b-182">Accessing Content</span></span>

<span data-ttu-id="09f6b-183">Командлет необходимо открыть поставщика, определяется путем Windows PowerShell, позволяя получать доступ к данным.</span><span class="sxs-lookup"><span data-stu-id="09f6b-183">Your cmdlet must open the provider indicated by the Windows PowerShell path so that it can access the data.</span></span> <span data-ttu-id="09f6b-184">[System.Management.Automation.Sessionstate](/dotnet/api/System.Management.Automation.SessionState) объект для пространства выполнения используется для доступа к поставщику, тогда как [System.Management.Automation.PSCmdlet.Invokeprovider\*](/dotnet/api/System.Management.Automation.PSCmdlet.InvokeProvider) свойство командлет используется для открытия поставщика.</span><span class="sxs-lookup"><span data-stu-id="09f6b-184">The [System.Management.Automation.Sessionstate](/dotnet/api/System.Management.Automation.SessionState) object for the runspace is used for access to the provider, while the [System.Management.Automation.PSCmdlet.Invokeprovider\*](/dotnet/api/System.Management.Automation.PSCmdlet.InvokeProvider) property of the cmdlet is used to open the provider.</span></span> <span data-ttu-id="09f6b-185">Доступ к содержимому обеспечивается получение [System.Management.Automation.Providerintrinsics](/dotnet/api/System.Management.Automation.ProviderIntrinsics) открыть объект для поставщика.</span><span class="sxs-lookup"><span data-stu-id="09f6b-185">Access to content is provided by retrieval of the [System.Management.Automation.Providerintrinsics](/dotnet/api/System.Management.Automation.ProviderIntrinsics) object for the provider opened.</span></span>

<span data-ttu-id="09f6b-186">Этот командлет Select-Str образец использует [System.Management.Automation.Providerintrinsics.Content\*](/dotnet/api/System.Management.Automation.ProviderIntrinsics.Content) свойство для предоставления содержимого для сканирования.</span><span class="sxs-lookup"><span data-stu-id="09f6b-186">This sample Select-Str cmdlet uses the [System.Management.Automation.Providerintrinsics.Content\*](/dotnet/api/System.Management.Automation.ProviderIntrinsics.Content) property to expose the content to scan.</span></span> <span data-ttu-id="09f6b-187">Затем можно вызвать [System.Management.Automation.Contentcmdletproviderintrinsics.Getreader\*](/dotnet/api/System.Management.Automation.ContentCmdletProviderIntrinsics.GetReader) , передавая необходимый путь Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="09f6b-187">It can then call the [System.Management.Automation.Contentcmdletproviderintrinsics.Getreader\*](/dotnet/api/System.Management.Automation.ContentCmdletProviderIntrinsics.GetReader) method, passing the required Windows PowerShell path.</span></span>

## <a name="code-sample"></a><span data-ttu-id="09f6b-188">Пример кода</span><span class="sxs-lookup"><span data-stu-id="09f6b-188">Code Sample</span></span>

<span data-ttu-id="09f6b-189">Следующий код показывает реализацию этой версии этот командлет Select-Str.</span><span class="sxs-lookup"><span data-stu-id="09f6b-189">The following code shows the implementation of this version of this Select-Str cmdlet.</span></span> <span data-ttu-id="09f6b-190">Обратите внимание на то, что этот код включает класс командлета, закрытые методы, используемые с помощью командлета и Windows PowerShell – – оснастка код, используемый для регистрации командлета.</span><span class="sxs-lookup"><span data-stu-id="09f6b-190">Note that this code includes the cmdlet class, private methods used by the cmdlet, and the Windows PowerShell snap-in code used to register the cmdlet.</span></span> <span data-ttu-id="09f6b-191">Дополнительные сведения о регистрации командлета см. в разделе [построение командлет](#Building-the-Cmdlet).</span><span class="sxs-lookup"><span data-stu-id="09f6b-191">For more information about registering the cmdlet, see [Building the Cmdlet](#Building-the-Cmdlet).</span></span>

```csharp
//
// Copyright (c) 2006 Microsoft Corporation. All rights reserved.
//
// THIS CODE AND INFORMATION IS PROVIDED "AS IS" WITHOUT WARRANTY OF
// ANY KIND, EITHER EXPRESSED OR IMPLIED, INCLUDING BUT NOT LIMITED TO
// THE IMPLIED WARRANTIES OF MERCHANTABILITY AND/OR FITNESS FOR A
// PARTICULAR PURPOSE.
//
using System;
using System.Text.RegularExpressions;
using System.Collections;
using System.Collections.ObjectModel;
using System.Management.Automation;
using System.Management.Automation.Provider;
using System.ComponentModel;

namespace Microsoft.Samples.PowerShell.Commands
{
  #region SelectStringCommand
  /// <summary>
  /// This cmdlet searches through PSObjects for particular patterns.
  /// </summary>
  /// <remarks>
  /// This cmdlet can be used to search any object, such as a file or a
  /// variable, whose provider exposes methods for reading and writing
  /// content.
  /// </remarks>
  [Cmdlet(VerbsCommon.Select, "Str", DefaultParameterSetName="PatternParameterSet")]
  public class SelectStringCommand : PSCmdlet
  {
    #region Parameters
    /// <summary>
    /// Declare a Path parameter that specifies where the data is stored.
    /// This parameter must specify a PowerShell that indicates the
    /// PowerShell provider that is used to access the objects to be
    /// searched for matching patterns. This parameter should also have
    /// a PSPath alias to provide consistency with other cmdlets that use
    /// PowerShell providers.
    /// </summary>
    /// <value>Path of the object(s) to search.</value>
    [Parameter(
               Position = 0,
               ParameterSetName = "ScriptParameterSet",
               Mandatory = true)]
    [Parameter(
               Position = 0,
               ParameterSetName = "PatternParameterSet",
               ValueFromPipeline = true,
               Mandatory = true)]
               [Alias("PSPath")]
    public string[] Path
    {
      get { return paths; }
      set { paths = value; }
    }
    private string[] paths;

    /// <summary>
    /// Declare a Pattern parameter that specifies the pattern(s)
    /// used to find matching patterns in the string representation
    /// of the objects. A positive result will be returned
    /// if any of the patterns are found in the objects.
    /// </summary>
    /// <remarks>
    /// The patterns will be compiled into an array of wildcard
    /// patterns for a simple match (literal string matching),
    /// or the patterns will be converted into an array of compiled
    /// regular expressions.
    /// </remarks>
    /// <value>Array of patterns to search.</value>
    [Parameter(
               Position = 1,
               ParameterSetName = "PatternParameterSet",
               Mandatory = true)]
    public string[] Pattern
    {
      get { return patterns; }
      set { patterns = value; }
    }
    private string[] patterns;
    private Regex[] regexPattern;
    private WildcardPattern[] wildcardPattern;

    /// <summary>
    /// Declare a Script parameter that specifies a script block
    /// that is called to perform the matching operations
    /// instead of the matching performed by the cmdlet.
    /// </summary>
    /// <value>Script block that will be called for matching</value>
    [Parameter(
               Position = 1,
               ParameterSetName = "ScriptParameterSet",
               Mandatory = true)]
    public ScriptBlock Script
    {
      set { script = value; }
      get { return script; }
    }
    ScriptBlock script;

    /// <summary>
    /// Declare a switch parameter that specifies if the pattern(s) are used
    /// literally. If not (default), searching is
    /// done using regular expressions.
    /// </summary>
    /// <value>If True, a literal pattern is used.</value>
    [Parameter]
    public SwitchParameter SimpleMatch
    {
      get { return simpleMatch; }
      set { simpleMatch = value; }
    }
    private bool simpleMatch;

    /// <summary>
    /// Declare a switch parameter that specifies if a case-sensitive
    /// search is performed.  If not (default), a case-insensitive search
    /// is performed.
    /// </summary>
    /// <value>If True, a case-sensitive search is made.</value>
    [Parameter]
    public SwitchParameter CaseSensitive
    {
      get { return caseSensitive; }
      set { caseSensitive = value; }
    }
    private bool caseSensitive;

    /// <summary>
    /// Declare an Include parameter that species which
    /// specific items are searched.  When this parameter
    /// is used, items that are not listed here are omitted
    /// from the search.
    /// </summary>
    [Parameter]
    [ValidateNotNullOrEmpty]
    public string[] Include
    {
      get
      {
        return includeStrings;
      }
      set
      {
        includeStrings = value;

        this.include = new WildcardPattern[includeStrings.Length];
        for (int i = 0; i < includeStrings.Length; i++)
        {
          this.include[i] = new WildcardPattern(includeStrings[i], WildcardOptions.IgnoreCase);
        }
      }
    }

    internal string[] includeStrings = null;
    internal WildcardPattern[] include = null;

    /// <summary>
    /// Declare an Exclude parameter that species which
    /// specific items are omitted from the search.
    /// </summary>
    ///
    [Parameter]
    [ValidateNotNullOrEmpty]
    public string[] Exclude
    {
      get
      {
        return excludeStrings;
      }
      set
      {
        excludeStrings = value;

        this.exclude = new WildcardPattern[excludeStrings.Length];
        for (int i = 0; i < excludeStrings.Length; i++)
        {
          this.exclude[i] = new WildcardPattern(excludeStrings[i], WildcardOptions.IgnoreCase);
        }
      }
    }
    internal string[] excludeStrings;
    internal WildcardPattern[] exclude;

    #endregion Parameters

    #region Overrides
    /// <summary>
    /// If regular expressions are used for pattern matching,
    /// then build an array of compiled regular expressions
    /// at startup. This increases performance during scanning
    /// operations when simple matching is not used.
    /// </summary>
    protected override void BeginProcessing()
    {
      WriteDebug("Validating patterns.");
      if (patterns != null)
      {
        foreach(string pattern in patterns)
        {
          if (pattern == null)
          ThrowTerminatingError(new ErrorRecord(
                                new ArgumentNullException(
                                "Search pattern cannot be null."),
                                "NullSearchPattern",
                                ErrorCategory.InvalidArgument,
                                pattern)
                                );
        }

        WriteVerbose("Search pattern(s) are valid.");

        // If a simple match is not specified, then
        // compile the regular expressions once.
        if (!simpleMatch)
        {
          WriteDebug("Compiling search regular expressions.");

          RegexOptions regexOptions = RegexOptions.Compiled;
          if (!caseSensitive)
             regexOptions |= RegexOptions.Compiled;
          regexPattern = new Regex[patterns.Length];

          for (int i = 0; i < patterns.Length; i++)
          {
            try
            {
              regexPattern[i] = new Regex(patterns[i], regexOptions);
            }
            catch (ArgumentException ex)
            {
              ThrowTerminatingError(new ErrorRecord(
                            ex,
                            "InvalidRegularExpression",
                            ErrorCategory.InvalidArgument,
                            patterns[i]
                         ));
            }
          } //Loop through patterns to create RegEx objects.

          WriteVerbose("Pattern(s) compiled into regular expressions.");
        }// If not a simple match.

        // If a simple match is specified, then compile the
        // wildcard patterns once.
        else
        {
          WriteDebug("Compiling search wildcards.");

          WildcardOptions wildcardOptions = WildcardOptions.Compiled;

          if (!caseSensitive)
          {
            wildcardOptions |= WildcardOptions.IgnoreCase;
          }

          wildcardPattern = new WildcardPattern[patterns.Length];
          for (int i = 0; i < patterns.Length; i++)
          {
            wildcardPattern[i] =
                         new WildcardPattern(patterns[i], wildcardOptions);
          }

          WriteVerbose("Pattern(s) compiled into wildcard expressions.");
        }// If match is a simple match.
      }// If valid patterns are available.
    }// End of function BeginProcessing().

    /// <summary>
    /// Process the input and search for the specified patterns.
    /// </summary>
    protected override void ProcessRecord()
    {
      UInt64 lineNumber = 0;
      MatchInfo result;
      ArrayList nonMatches = new ArrayList();

      // Walk the list of paths and search the contents for
      // any of the specified patterns.
      foreach (string psPath in paths)
      {
        // Once the filepaths are expanded, we may have more than one
        // path, so process all referenced paths.
        foreach(PathInfo path in
                SessionState.Path.GetResolvedPSPathFromPSPath(psPath)
               )
        {
          WriteVerbose("Processing path " + path.Path);

          // Check if the path represents one of the items to be
          // excluded. If so, continue to next path.
          if (!MeetsIncludeExcludeCriteria(path.ProviderPath))
             continue;

          // Get the content reader for the item(s) at the
          // specified path.
          Collection<IContentReader> readerCollection = null;
          try
          {
            readerCollection =
                        this.InvokeProvider.Content.GetReader(path.Path);
          }
          catch (PSNotSupportedException ex)
          {
            WriteError(new ErrorRecord(ex,
                       "ContentAccessNotSupported",
                        ErrorCategory.NotImplemented,
                        path.Path)
                       );
            return;
          }

          foreach(IContentReader reader in readerCollection)
          {
            // Reset the line number for this path.
            lineNumber = 0;

            // Read in a single block (line in case of a file)
            // from the object.
            IList items = reader.Read(1);

            // Read and process one block(line) at a time until
            // no more blocks(lines) exist.
            while (items != null && items.Count == 1)
            {
              // Increment the line number each time a line is
              // processed.
              lineNumber++;

              String message = String.Format("Testing line {0} : {1}",
                                            lineNumber, items[0]);

              WriteDebug(message);

              result = SelectString(items[0]);

              if (result != null)
              {
                result.Path = path.Path;
                result.LineNumber = lineNumber;

                WriteObject(result);
              }
              else
              {
                // Add the block(line) that did not match to the
                // collection of non matches , which will be stored
                // in the SessionState variable $NonMatches
                nonMatches.Add(items[0]);
              }

              // Get the next line from the object.
              items = reader.Read(1);

            }// While loop for reading one line at a time.
          }// Foreach loop for reader collection.
        }// Foreach loop for processing referenced paths.
      }// Foreach loop for walking of path list.

      // Store the list of non-matches in the
      // session state variable $NonMatches.
      try
      {
        this.SessionState.PSVariable.Set("NonMatches", nonMatches);
      }
      catch (SessionStateUnauthorizedAccessException ex)
      {
        WriteError(new ErrorRecord(ex,
                   "CannotWriteVariableNonMatches",
                   ErrorCategory.InvalidOperation,
                   nonMatches)
                  );
      }

    }// End of protected override void ProcessRecord().
    #endregion Overrides

    #region PrivateMethods
    /// <summary>
    /// Check for a match using the input string and the pattern(s)
    /// specified.
    /// </summary>
    /// <param name="input">The string to test.</param>
    /// <returns>MatchInfo object containing information about
    /// result of a match</returns>
    private MatchInfo SelectString(object input)
    {
      string line = null;

      try
      {
        // Convert the object to a string type
        // safely using language support methods
        line = (string)LanguagePrimitives.ConvertTo(
                                                    input,
                                                    typeof(string)
                                                    );
        line = line.Trim(' ','\t');
      }
      catch (PSInvalidCastException ex)
      {
        WriteError(new ErrorRecord(
                   ex,
                   "CannotCastObjectToString",
                   ErrorCategory.InvalidOperation,
                   input)
                   );

        return null;
      }

      MatchInfo result = null;

      // If a scriptblock has been specified, call it
      // with the path for processing.  It will return
      // one object.
      if (script != null)
      {
        WriteDebug("Executing script block.");

        Collection<PSObject> psObjects =
                             script.Invoke(
                                           line,
                                           simpleMatch,
                                           caseSensitive
                                          );

        foreach (PSObject psObject in psObjects)
        {
          if (LanguagePrimitives.IsTrue(psObject))
          {
            result = new MatchInfo();
            result.Line = line;
            result.IgnoreCase = !caseSensitive;

            break;
          } //End of If.
        } //End ForEach loop.
      } // End of If if script exists.

      // If script block exists, see if this line matches any
      // of the match patterns.
      else
      {
        int patternIndex = 0;

        while (patternIndex < patterns.Length)
        {
          if ((simpleMatch &&
              wildcardPattern[patternIndex].IsMatch(line))
              || (regexPattern != null
              && regexPattern[patternIndex].IsMatch(line))
             )
          {
            result = new MatchInfo();
            result.IgnoreCase = !caseSensitive;
            result.Line = line;
            result.Pattern = patterns[patternIndex];

            break;
          }

          patternIndex++;

        }// While loop through patterns.
      }// Else for no script block specified.

      return result;

    }// End of SelectString

    /// <summary>
    /// Check whether the supplied name meets the include/exclude criteria.
    /// That is - it's on the include list if the include list was
    /// specified, and not on the exclude list if the exclude list was specified.
    /// </summary>
    /// <param name="path">path to validate</param>
    /// <returns>True if the path is acceptable.</returns>
    private bool MeetsIncludeExcludeCriteria(string path)
    {
      bool ok = false;

      // See if the file is on the include list.
      if (this.include != null)
      {
        foreach (WildcardPattern patternItem in this.include)
        {
          if (patternItem.IsMatch(path))
          {
            ok = true;
            break;
          }
        }
      }
      else
      {
        ok = true;
      }

      if (!ok)
         return false;

      // See if the file is on the exclude list.
      if (this.exclude != null)
      {
        foreach (WildcardPattern patternItem in this.exclude)
        {
          if (patternItem.IsMatch(path))
          {
            ok = false;
            break;
          }
        }
      }

      return ok;
    } //MeetsIncludeExcludeCriteria
    #endregion Private Methods

  }// class SelectStringCommand

  #endregion SelectStringCommand

  #region MatchInfo

  /// <summary>
  /// Class representing the result of a pattern/literal match
  /// that is passed through the pipeline by the Select-Str cmdlet.
  /// </summary>
  public class MatchInfo
  {
    /// <summary>
    /// Indicates if the match was done ignoring case.
    /// </summary>
    /// <value>True if case was ignored.</value>
    public bool IgnoreCase
    {
      get { return ignoreCase; }
      set { ignoreCase = value; }
    }
    private bool ignoreCase;

    /// <summary>
    /// Specifies the number of the matching line.
    /// </summary>
    /// <value>The number of the matching line.</value>
    public UInt64 LineNumber
    {
      get { return lineNumber; }
      set { lineNumber = value; }
    }
    private UInt64 lineNumber;

    /// <summary>
    /// Specifies the text of the matching line.
    /// </summary>
    /// <value>The text of the matching line.</value>
    public string Line
    {
      get { return line; }
      set { line = value; }
    }
    private string line;

    /// <summary>
    /// Specifies the full path of the object(file) containing the
    /// matching line.
    /// </summary>
    /// <remarks>
    /// It will be "inputStream" if the object came from the input
    /// stream.
    /// </remarks>
    /// <value>The path name</value>
    public string Path
    {
      get { return path; }
      set
      {
        pathSet = true;
        path = value;
      }
    }
    private string path;
    private bool pathSet;

    /// <summary>
    /// Specifies the pattern that was used in the match.
    /// </summary>
    /// <value>The pattern string</value>
    public string Pattern
    {
      get { return pattern; }
      set { pattern = value; }
    }
    private string pattern;

    private const string MatchFormat = "{0}:{1}:{2}";

    /// <summary>
    /// Returns the string representation of this object. The format
    /// depends on whether a path has been set for this object or
    /// not.
    /// </summary>
    /// <remarks>
    /// If the path component is set, as would be the case when
    /// matching in a file, ToString() returns the path, line
    /// number and line text.  If path is not set, then just the
    /// line text is presented.
    /// </remarks>
    /// <returns>The string representation of the match object.</returns>
    public override string ToString()
    {
      if (pathSet)
         return String.Format(
         System.Threading.Thread.CurrentThread.CurrentCulture,
         MatchFormat,
         this.path,
         this.lineNumber,
         this.line
         );
      else
         return this.line;
    }
  }// End class MatchInfo

  #endregion

  #region PowerShell snap-in

  /// <summary>
  /// Create a PowerShell snap-in for the Select-Str cmdlet.
  /// </summary>
  [RunInstaller(true)]
  public class SelectStringPSSnapIn : PSSnapIn
  {
    /// <summary>
    /// Create an instance of the SelectStrPSSnapin class.
    /// </summary>
    public SelectStringPSSnapIn()
           : base()
    {
    }

    /// <summary>
    /// Specify the name of the PowerShell snap-in.
    /// </summary>
    public override string Name
    {
      get
      {
        return "SelectStrPSSnapIn";
      }
    }

    /// <summary>
    /// Specify the vendor of the PowerShell snap-in.
    /// </summary>
    public override string Vendor
    {
      get
      {
        return "Microsoft";
      }
    }

    /// <summary>
    /// Specify the localization resource information for the vendor.
    /// Use the format: SnapinName,VendorName.
    /// </summary>
    public override string VendorResource
    {
      get
      {
        return "SelectStrSnapIn,Microsoft";
      }
    }

    /// <summary>
    /// Specify the description of the PowerShell snap-in.
    /// </summary>
    public override string Description
    {
      get
        {
          return "This is a PowerShell snap-in for the Select-Str cmdlet.";
        }
    }

    /// <summary>
    /// Specify the localization resource information for the description.
    /// Use the format: SnapinName,Description.

    /// </summary>
    public override string DescriptionResource
    {
      get
      {
          return "SelectStrSnapIn,This is a PowerShell snap-in for the Select-Str cmdlet.";
      }
    }
  }
  #endregion PowerShell snap-in

} //namespace Microsoft.Samples.PowerShell.Commands;
```

## <a name="building-the-cmdlet"></a><span data-ttu-id="09f6b-192">Создание командлета</span><span class="sxs-lookup"><span data-stu-id="09f6b-192">Building the Cmdlet</span></span>

<span data-ttu-id="09f6b-193">После реализации командлета, необходимо зарегистрировать его с помощью Windows PowerShell через оснастку Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="09f6b-193">After implementing a cmdlet, you must register it with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="09f6b-194">Дополнительные сведения о регистрации командлетов см. в разделе [как регистрация командлетов, поставщиков и ведущих приложений](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).</span><span class="sxs-lookup"><span data-stu-id="09f6b-194">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="09f6b-195">Тестирование командлет</span><span class="sxs-lookup"><span data-stu-id="09f6b-195">Testing the Cmdlet</span></span>

<span data-ttu-id="09f6b-196">При командлета был зарегистрирован с помощью Windows PowerShell, его можно проверить, запустив его в командной строке.</span><span class="sxs-lookup"><span data-stu-id="09f6b-196">When your cmdlet has been registered with Windows PowerShell, you can test it by running it on the command line.</span></span> <span data-ttu-id="09f6b-197">Следующую процедуру можно использовать для тестирования командлет Select-Str образец.</span><span class="sxs-lookup"><span data-stu-id="09f6b-197">The following procedure can be used to test the sample Select-Str cmdlet.</span></span>

1. <span data-ttu-id="09f6b-198">Запустите Windows PowerShell и найдите файл заметки для строк с выражением «.NET».</span><span class="sxs-lookup"><span data-stu-id="09f6b-198">Start Windows PowerShell, and search the Notes file for occurrences of lines with the expression ".NET".</span></span> <span data-ttu-id="09f6b-199">Обратите внимание на то, что имя пути в кавычки требуются, только в том случае, если путь состоит из нескольких слов.</span><span class="sxs-lookup"><span data-stu-id="09f6b-199">Note that the quotation marks around the name of the path are required only if the path consists of more than one word.</span></span>

    ```powershell
    select-str -Path "notes" -Pattern ".NET" -SimpleMatch=$false
    ```

    <span data-ttu-id="09f6b-200">Появляется следующий результат.</span><span class="sxs-lookup"><span data-stu-id="09f6b-200">The following output appears.</span></span>

    ```output
    IgnoreCase   : True
    LineNumber   : 8
    Line         : Because Windows PowerShell works directly with .NET objects, there is often a .NET object
    Path         : C:\PowerShell-Progs\workspace\Samples\SelectStr\notes
    Pattern      : .NET
    IgnoreCase   : True
    LineNumber   : 21
    Line         : You should normally define the class for a cmdlet in a .NET namespace
    Path         : C:\PowerShell-Progs\workspace\Samples\SelectStr\notes
    Pattern      : .NET
    ```

2. <span data-ttu-id="09f6b-201">Найдите файл заметки для строк со словом «по», следуют любой другой текст.</span><span class="sxs-lookup"><span data-stu-id="09f6b-201">Search the Notes file for occurrences of lines with the word "over", followed by any other text.</span></span> <span data-ttu-id="09f6b-202">`SimpleMatch` Параметра используется значение по умолчанию `false`.</span><span class="sxs-lookup"><span data-stu-id="09f6b-202">The `SimpleMatch` parameter is using the default value of `false`.</span></span> <span data-ttu-id="09f6b-203">Поиск выполняется без учета регистра поскольку `CaseSensitive` параметр имеет значение `false`.</span><span class="sxs-lookup"><span data-stu-id="09f6b-203">The search is case-insensitive because the `CaseSensitive` parameter is set to `false`.</span></span>

    ```powershell
    select-str -Path notes -Pattern "over*" -SimpleMatch -CaseSensitive:$false
    ```

    <span data-ttu-id="09f6b-204">Появляется следующий результат.</span><span class="sxs-lookup"><span data-stu-id="09f6b-204">The following output appears.</span></span>

    ```output
    IgnoreCase   : True
    LineNumber   : 45
    Line         : Override StopProcessing
    Path         : C:\PowerShell-Progs\workspace\Samples\SelectStr\notes
    Pattern      : over*
    IgnoreCase   : True
    LineNumber   : 49
    Line         : overriding the StopProcessing method
    Path         : C:\PowerShell-Progs\workspace\Samples\SelectStr\notes
    Pattern      : over*
    ```

3. <span data-ttu-id="09f6b-205">Найдите в файле заметки, используя регулярное выражение в качестве шаблона.</span><span class="sxs-lookup"><span data-stu-id="09f6b-205">Search the Notes file using a regular expression as the pattern.</span></span> <span data-ttu-id="09f6b-206">Командлет ищет буквенные символы и пробелы, заключенные в круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="09f6b-206">The cmdlet searches for alphabetical characters and blank spaces enclosed in parentheses.</span></span>

    ```powershell
    select-str -Path notes -Pattern "\([A-Za-z:blank:]" -SimpleMatch:$false
    ```

    <span data-ttu-id="09f6b-207">Появляется следующий результат.</span><span class="sxs-lookup"><span data-stu-id="09f6b-207">The following output appears.</span></span>

    ```output
    IgnoreCase   : True
    LineNumber   : 1
    Line         : Advisory Guidelines (Consider Following)
    Path         : C:\PowerShell-Progs\workspace\Samples\SelectStr\notes
    Pattern      : \([A-Za-z:blank:]
    IgnoreCase   : True
    LineNumber   : 53
    Line         : If your cmdlet has objects that are not disposed of (written to the pipeline)
    Path         : C:\PowerShell-Progs\workspace\Samples\SelectStr\notes
    Pattern      : \([A-Za-z:blank:]
    ```

4. <span data-ttu-id="09f6b-208">Учитывать регистр при поиске файла заметки для вхождения слова «Параметр».</span><span class="sxs-lookup"><span data-stu-id="09f6b-208">Perform a case-sensitive search of the Notes file for occurrences of the word "Parameter".</span></span>

    ```powershell
    select-str -Path notes -Pattern Parameter -CaseSensitive
    ```

    <span data-ttu-id="09f6b-209">Появляется следующий результат.</span><span class="sxs-lookup"><span data-stu-id="09f6b-209">The following output appears.</span></span>

    ```output
    IgnoreCase   : False
    LineNumber   : 6
    Line         : Support an InputObject Parameter
    Path         : C:\PowerShell-Progs\workspace\Samples\SelectStr\notes
    Pattern      : Parameter
    IgnoreCase   : False
    LineNumber   : 30
    Line         : Support Force Parameter
    Path         : C:\PowerShell-Progs\workspace\Samples\SelectStr\notes
    Pattern      : Parameter
    ```

5. <span data-ttu-id="09f6b-210">Поставщик variable поиска, поставляемых с Windows PowerShell для переменных, имеющих числовые значения от 0 до 9.</span><span class="sxs-lookup"><span data-stu-id="09f6b-210">Search the variable provider shipped with Windows PowerShell for variables that have numerical values from 0 through 9.</span></span>

    ```powershell
    select-str -Path * -Pattern "[0-9]"
    ```

    <span data-ttu-id="09f6b-211">Появляется следующий результат.</span><span class="sxs-lookup"><span data-stu-id="09f6b-211">The following output appears.</span></span>

    ```output
    IgnoreCase   : True
    LineNumber   : 1
    Line         : 64
    Path         : Variable:\MaximumHistoryCount
    Pattern      : [0-9]
    ```

6. <span data-ttu-id="09f6b-212">Используйте блок сценария для поиска файла SelectStrCommandSample.cs для строки «Pos».</span><span class="sxs-lookup"><span data-stu-id="09f6b-212">Use a script block to search the file SelectStrCommandSample.cs for the string "Pos".</span></span> <span data-ttu-id="09f6b-213">**Cmatch** функция, сценарий выполняет сопоставление без учета регистра шаблона.</span><span class="sxs-lookup"><span data-stu-id="09f6b-213">The **cmatch** function for the script performs a case-insensitive pattern match.</span></span>

    ```powershell
    select-str -Path "SelectStrCommandSample.cs" -Script { if ($args[0] -cmatch "Pos"){ return $true } return $false }
    ```

    <span data-ttu-id="09f6b-214">Появляется следующий результат.</span><span class="sxs-lookup"><span data-stu-id="09f6b-214">The following output appears.</span></span>

    ```output
    IgnoreCase   : True
    LineNumber   : 37
    Line         :    Position = 0.
    Path         : C:\PowerShell-Progs\workspace\Samples\SelectStr\SelectStrCommandSample.cs
    Pattern      :
    ```

## <a name="see-also"></a><span data-ttu-id="09f6b-215">См. также</span><span class="sxs-lookup"><span data-stu-id="09f6b-215">See Also</span></span>

[<span data-ttu-id="09f6b-216">Как создать командлет Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="09f6b-216">How to Create a Windows PowerShell Cmdlet</span></span>](https://msdn.microsoft.com/en-us/0d721742-c849-4d0d-964f-78ddd9cd258c)

[<span data-ttu-id="09f6b-217">Создайте свой первый командлет</span><span class="sxs-lookup"><span data-stu-id="09f6b-217">Creating Your First Cmdlet</span></span>](./creating-a-cmdlet-without-parameters.md)

[<span data-ttu-id="09f6b-218">Создание командлета, который изменяет системы</span><span class="sxs-lookup"><span data-stu-id="09f6b-218">Creating a Cmdlet that Modifies the System</span></span>](./creating-a-cmdlet-that-modifies-the-system.md)

[<span data-ttu-id="09f6b-219">Разработка поставщика Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="09f6b-219">Design Your Windows PowerShell Provider</span></span>](../prog-guide/designing-your-windows-powershell-provider.md)

[<span data-ttu-id="09f6b-220">Как работает Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="09f6b-220">How Windows PowerShell Works</span></span>](https://msdn.microsoft.com/en-us/ced30e23-10af-4700-8933-49873bd84d58)

[<span data-ttu-id="09f6b-221">Регистрация командлетов, поставщиков и ведущих приложений</span><span class="sxs-lookup"><span data-stu-id="09f6b-221">How to Register Cmdlets, Providers, and Host Applications</span></span>](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[<span data-ttu-id="09f6b-222">Пакет SDK для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="09f6b-222">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
