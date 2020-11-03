---
description: Описывает команду языка, которую можно использовать для прохода по всем элементам в коллекции элементов.
keywords: powershell,командлет
Locale: en-US
ms.date: 2/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_foreach?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Foreach
ms.openlocfilehash: b5f09785fbf1fa8c3c14d287efc7cf5fed2d18eb
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "93231478"
---
# <a name="about-foreach"></a><span data-ttu-id="e926f-104">О ForEach</span><span class="sxs-lookup"><span data-stu-id="e926f-104">About ForEach</span></span>

## <a name="short-description"></a><span data-ttu-id="e926f-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="e926f-105">Short description</span></span>
<span data-ttu-id="e926f-106">Описывает команду языка, которую можно использовать для прохода по всем элементам в коллекции элементов.</span><span class="sxs-lookup"><span data-stu-id="e926f-106">Describes a language command you can use to traverse all the items in a collection of items.</span></span>

## <a name="long-description"></a><span data-ttu-id="e926f-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="e926f-107">Long description</span></span>

<span data-ttu-id="e926f-108">`Foreach`Оператор (также называемый `Foreach` циклом) — это языковая конструкция для пошагового выполнения (прохода) ряда значений в коллекции элементов.</span><span class="sxs-lookup"><span data-stu-id="e926f-108">The `Foreach` statement (also known as a `Foreach` loop) is a language construct for stepping through (iterating) a series of values in a collection of items.</span></span>

<span data-ttu-id="e926f-109">Самый простой и типичный тип коллекции для обхода — массив.</span><span class="sxs-lookup"><span data-stu-id="e926f-109">The simplest and most typical type of collection to traverse is an array.</span></span>
<span data-ttu-id="e926f-110">В `Foreach` цикле обычно выполняется одна или несколько команд для каждого элемента в массиве.</span><span class="sxs-lookup"><span data-stu-id="e926f-110">Within a `Foreach` loop, it is common to run one or more commands against each item in an array.</span></span>

## <a name="syntax"></a><span data-ttu-id="e926f-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e926f-111">Syntax</span></span>

<span data-ttu-id="e926f-112">Ниже показан `ForEach` синтаксис.</span><span class="sxs-lookup"><span data-stu-id="e926f-112">The following shows the `ForEach` syntax:</span></span>

```
foreach ($<item> in $<collection>){<statement list>}
```

<span data-ttu-id="e926f-113">Часть `ForEach` оператора, заключенная в скобки, представляет переменную и коллекцию для итерации.</span><span class="sxs-lookup"><span data-stu-id="e926f-113">The part of the `ForEach` statement enclosed in parenthesis represents a variable and a collection to iterate.</span></span> <span data-ttu-id="e926f-114">PowerShell автоматически создает переменную `$<item>` при `Foreach` выполнении цикла.</span><span class="sxs-lookup"><span data-stu-id="e926f-114">PowerShell creates the variable `$<item>` automatically when the `Foreach` loop runs.</span></span> <span data-ttu-id="e926f-115">До каждой итерации в цикле для переменной задается значение в коллекции.</span><span class="sxs-lookup"><span data-stu-id="e926f-115">Prior to each iteration through the loop, the variable is set to a value in the collection.</span></span>
<span data-ttu-id="e926f-116">Блок, следующий за `Foreach` оператором, `{<statement list>}` содержит набор команд для выполнения по отношению к каждому элементу в коллекции.</span><span class="sxs-lookup"><span data-stu-id="e926f-116">The block following a `Foreach` statement `{<statement list>}` contains a set of commands to execute against each item in a collection.</span></span>

### <a name="examples"></a><span data-ttu-id="e926f-117">Примеры</span><span class="sxs-lookup"><span data-stu-id="e926f-117">Examples</span></span>

<span data-ttu-id="e926f-118">Например, `Foreach` цикл в следующем примере отображает значения в `$letterArray` массиве.</span><span class="sxs-lookup"><span data-stu-id="e926f-118">For example, the `Foreach` loop in the following example displays the values in the `$letterArray` array.</span></span>

```powershell
$letterArray = "a","b","c","d"
foreach ($letter in $letterArray)
{
  Write-Host $letter
}
```

<span data-ttu-id="e926f-119">В этом примере `$letterArray` массив создается и инициализируется со строковыми значениями `"a"` ,, `"b"` `"c"` и `"d"` .</span><span class="sxs-lookup"><span data-stu-id="e926f-119">In this example, the `$letterArray` array is created and initialized with the string values `"a"`, `"b"`, `"c"`, and `"d"`.</span></span> <span data-ttu-id="e926f-120">При первом `Foreach` выполнении инструкции ей присваивается `$letter` переменная, равная первому элементу в `$letterArray` ( `"a"` ).</span><span class="sxs-lookup"><span data-stu-id="e926f-120">The first time the `Foreach` statement runs, it sets the `$letter` variable equal to the first item in `$letterArray` (`"a"`).</span></span> <span data-ttu-id="e926f-121">Затем он использует `Write-Host` командлет для вывода буквы a.</span><span class="sxs-lookup"><span data-stu-id="e926f-121">Then, it uses the `Write-Host` cmdlet to display the letter a.</span></span> <span data-ttu-id="e926f-122">В следующий раз в цикле устанавливается `$letter` значение `"b"` и т. д.</span><span class="sxs-lookup"><span data-stu-id="e926f-122">The next time through the loop, `$letter` is set to `"b"`, and so on.</span></span> <span data-ttu-id="e926f-123">После того как в `Foreach` цикле отображается буква d, PowerShell завершает цикл.</span><span class="sxs-lookup"><span data-stu-id="e926f-123">After the `Foreach` loop displays the letter d, PowerShell exits the loop.</span></span>

<span data-ttu-id="e926f-124">Вся `Foreach` инструкция должна находиться в одной строке для выполнения в качестве команды в командной строке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e926f-124">The entire `Foreach` statement must appear on a single line to run it as a command at the PowerShell command prompt.</span></span> <span data-ttu-id="e926f-125">Инструкция целиком `Foreach` не должна отображаться в одной строке, если вместо этого поместить команду в файл скрипта PS1.</span><span class="sxs-lookup"><span data-stu-id="e926f-125">The entire `Foreach` statement does not have to appear on a single line if you place the command in a .ps1 script file instead.</span></span>

<span data-ttu-id="e926f-126">`Foreach` операторы также можно использовать вместе с командлетами, возвращающими коллекцию элементов.</span><span class="sxs-lookup"><span data-stu-id="e926f-126">`Foreach` statements can also be used together with cmdlets that return a collection of items.</span></span> <span data-ttu-id="e926f-127">В следующем примере оператор foreach проходит по списку элементов, возвращаемых `Get-ChildItem` командлетом.</span><span class="sxs-lookup"><span data-stu-id="e926f-127">In the following example, the Foreach statement steps through the list of items that is returned by the `Get-ChildItem` cmdlet.</span></span>

```powershell
foreach ($file in Get-ChildItem)
{
  Write-Host $file
}
```

<span data-ttu-id="e926f-128">Можно уточнить пример с помощью `If` оператора, ограничивающего возвращаемые результаты.</span><span class="sxs-lookup"><span data-stu-id="e926f-128">You can refine the example by using an `If` statement to limit the results that are returned.</span></span> <span data-ttu-id="e926f-129">В следующем примере `Foreach` оператор выполняет ту же операцию цикла, что и предыдущий пример, но добавляет `If` инструкцию для ограничения результатов до файлов размером более 100 КИЛОБАЙТ (КБ):</span><span class="sxs-lookup"><span data-stu-id="e926f-129">In the following example, the `Foreach` statement performs the same looping operation as the previous example, but it adds an `If` statement to limit the results to files that are greater than 100 kilobytes (KB):</span></span>

```powershell
foreach ($file in Get-ChildItem)
{
  if ($file.length -gt 100KB)
  {
    Write-Host $file
  }
}
```

<span data-ttu-id="e926f-130">В этом примере `Foreach` цикл использует свойство `$file` переменной для выполнения операции сравнения ( `$file.length -gt 100KB` ).</span><span class="sxs-lookup"><span data-stu-id="e926f-130">In this example, the `Foreach` loop uses a property of the `$file` variable to perform a comparison operation (`$file.length -gt 100KB`).</span></span> <span data-ttu-id="e926f-131">`$file`Переменная содержит все свойства объекта, возвращаемые `Get-ChildItem` командлетом.</span><span class="sxs-lookup"><span data-stu-id="e926f-131">The `$file` variable contains all the properties in the object that is returned by the `Get-ChildItem` cmdlet.</span></span> <span data-ttu-id="e926f-132">Таким образом, можно вернуть не только имя файла.</span><span class="sxs-lookup"><span data-stu-id="e926f-132">Therefore, you can return more than just a file name.</span></span>
<span data-ttu-id="e926f-133">В следующем примере PowerShell возвращает длину и последнее время доступа в списке инструкций:</span><span class="sxs-lookup"><span data-stu-id="e926f-133">In the next example, PowerShell returns the length and the last access time inside the statement list:</span></span>

```powershell
foreach ($file in Get-ChildItem)
{
  if ($file.length -gt 100KB)
  {
    Write-Host $file
    Write-Host $file.length
    Write-Host $file.lastaccesstime
  }
}
```

<span data-ttu-id="e926f-134">В этом примере вы не ограничены выполнением одной команды в списке инструкций.</span><span class="sxs-lookup"><span data-stu-id="e926f-134">In this example, you are not limited to running a single command in a statement list.</span></span>

<span data-ttu-id="e926f-135">Можно также использовать переменную за пределами `Foreach` цикла и увеличить переменную внутри цикла.</span><span class="sxs-lookup"><span data-stu-id="e926f-135">You can also use a variable outside a `Foreach` loop and increment the variable inside the loop.</span></span> <span data-ttu-id="e926f-136">В следующем примере подсчитывается размер файлов свыше 100 КБ:</span><span class="sxs-lookup"><span data-stu-id="e926f-136">The following example counts files over 100 KB in size:</span></span>

```powershell
$i = 0
foreach ($file in Get-ChildItem) {
  if ($file.length -gt 100KB) {
    Write-Host $file "file size:" ($file.length / 1024).ToString("F0") KB
    $i = $i + 1
  }
}

if ($i -ne 0) {
  Write-Host
  Write-Host $i " file(s) over 100 KB in the current directory."
}
else {
  Write-Host "No files greater than 100 KB in the current directory."
}
```

<span data-ttu-id="e926f-137">В предыдущем примере переменной присваивается `$i` значение `0` вне цикла, а переменная увеличивается в цикле для каждого найденного файла, размер которого ПРЕВЫШАЕТ 100 КБ.</span><span class="sxs-lookup"><span data-stu-id="e926f-137">In the preceding example, the `$i` variable is set to `0` outside the loop, and the variable is incremented inside the loop for each file that is found that is larger than 100 KB.</span></span> <span data-ttu-id="e926f-138">Когда цикл завершает работу, `If` оператор вычисляет значение, `$i` чтобы отобразить количество всех файлов свыше 100 КБ.</span><span class="sxs-lookup"><span data-stu-id="e926f-138">When the loop exits, an `If` statement evaluates the value of `$i` to display a count of all the files over 100 KB.</span></span> <span data-ttu-id="e926f-139">Или отображается сообщение о том, что не найдены файлы размером свыше 100 КБ.</span><span class="sxs-lookup"><span data-stu-id="e926f-139">Or, it displays a message stating that no files over 100 KB were found.</span></span>

<span data-ttu-id="e926f-140">В предыдущем примере также показано, как форматировать результаты размера файла:</span><span class="sxs-lookup"><span data-stu-id="e926f-140">The previous example also demonstrates how to format the file length results:</span></span>

```powershell
($file.length / 1024).ToString("F0")
```

<span data-ttu-id="e926f-141">Значение делится на 1 024 для отображения результатов в килобайтах, а не в байтах, а полученное значение затем форматируется с помощью описателя формата с фиксированной точкой, чтобы удалить из результата все десятичные значения.</span><span class="sxs-lookup"><span data-stu-id="e926f-141">The value is divided by 1,024 to show the results in kilobytes rather than bytes, and the resulting value is then formatted using the fixed-point format specifier to remove any decimal values from the result.</span></span> <span data-ttu-id="e926f-142">Значение 0 указывает, что описатель формата не отображает десятичные разряды.</span><span class="sxs-lookup"><span data-stu-id="e926f-142">The 0 makes the format specifier show no decimal places.</span></span>

<span data-ttu-id="e926f-143">В следующем примере определенная функция анализирует скрипты PowerShell и модули скриптов и возвращает расположение функций, содержащихся в.</span><span class="sxs-lookup"><span data-stu-id="e926f-143">In the following example, the function defined parses PowerShell scripts and script modules and returns the location of functions contained within.</span></span> <span data-ttu-id="e926f-144">В примере показано, как использовать `MoveNext` метод (который работает аналогично `skip X` `For` циклу) и `Current` свойство `$foreach` переменной внутри блока скрипта foreach.</span><span class="sxs-lookup"><span data-stu-id="e926f-144">The example demonstrates how to use the `MoveNext` method (which works similarly to `skip X` on a `For` loop) and the `Current` property of the `$foreach` variable inside of a foreach script block.</span></span> <span data-ttu-id="e926f-145">Функция example может находить функции в скрипте даже в том случае, если обнаружены неоднородные или непротиворечивые определения функций, охватывающие несколько строк.</span><span class="sxs-lookup"><span data-stu-id="e926f-145">The example function can find functions in a script even if there are unusually- or inconsistently-spaced function definitions that span multiple lines.</span></span>

<span data-ttu-id="e926f-146">Дополнительные сведения см. [в разделе Использование перечислителей](about_Automatic_Variables.md#using-enumerators).</span><span class="sxs-lookup"><span data-stu-id="e926f-146">For more information, see [Using Enumerators](about_Automatic_Variables.md#using-enumerators).</span></span>

```powershell
function Get-FunctionPosition {
  [CmdletBinding()]
  [OutputType('FunctionPosition')]
  param(
    [Parameter(Position = 0, Mandatory,
      ValueFromPipeline, ValueFromPipelineByPropertyName)]
    [ValidateNotNullOrEmpty()]
    [Alias('PSPath')]
    [System.String[]]
    $Path
  )

  process {
    try {
      $filesToProcess = if ($_ -is [System.IO.FileSystemInfo]) {
        $_
      } else {
        $filesToProcess = Get-Item -Path $Path
      }
      $parser = [System.Management.Automation.Language.Parser]
      foreach ($item in $filesToProcess) {
        if ($item.PSIsContainer -or
            $item.Extension -notin @('.ps1', '.psm1')) {
          continue
        }
        $tokens = $errors = $null
        $ast = $parser::ParseFile($item.FullName, ([REF]$tokens),
          ([REF]$errors))
        if ($errors) {
          $msg = "File '{0}' has {1} parser errors." -f $item.FullName,
            $errors.Count
          Write-Warning $msg
        }
        :tokenLoop foreach ($token in $tokens) {
          if ($token.Kind -ne 'Function') {
            continue
          }
          $position = $token.Extent.StartLineNumber
          do {
            if (-not $foreach.MoveNext()) {
              break tokenLoop
            }
            $token = $foreach.Current
          } until ($token.Kind -in @('Generic', 'Identifier'))
          $functionPosition = [pscustomobject]@{
            Name       = $token.Text
            LineNumber = $position
            Path       = $item.FullName
          }
          Add-Member -InputObject $functionPosition `
            -TypeName FunctionPosition -PassThru
        }
      }
    }
    catch {
      throw
    }
  }
}
```

## <a name="see-also"></a><span data-ttu-id="e926f-147">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="e926f-147">SEE ALSO</span></span>

[<span data-ttu-id="e926f-148">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="e926f-148">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="e926f-149">about_If</span><span class="sxs-lookup"><span data-stu-id="e926f-149">about_If</span></span>](about_If.md)

[<span data-ttu-id="e926f-150">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="e926f-150">ForEach-Object</span></span>](xref:Microsoft.PowerShell.Core.ForEach-Object)
