---
description: Объясняется, как перенаправлять выходные данные из PowerShell в текстовые файлы.
keywords: PowerShell, командлет
Locale: en-US
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_redirection?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Redirection
ms.openlocfilehash: 1a532aeacf6347023c95905c82aa1f221835a729
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "93232902"
---
# <a name="about-redirection"></a><span data-ttu-id="abaaf-104">О перенаправлении</span><span class="sxs-lookup"><span data-stu-id="abaaf-104">About Redirection</span></span>

## <a name="short-description"></a><span data-ttu-id="abaaf-105">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="abaaf-105">Short description</span></span>
<span data-ttu-id="abaaf-106">Объясняется, как перенаправлять выходные данные из PowerShell в текстовые файлы.</span><span class="sxs-lookup"><span data-stu-id="abaaf-106">Explains how to redirect output from PowerShell to text files.</span></span>

## <a name="long-description"></a><span data-ttu-id="abaaf-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="abaaf-107">Long description</span></span>

<span data-ttu-id="abaaf-108">По умолчанию PowerShell отправляет выходные данные на узел PowerShell.</span><span class="sxs-lookup"><span data-stu-id="abaaf-108">By default, PowerShell sends output to the PowerShell host.</span></span> <span data-ttu-id="abaaf-109">Обычно это консольное приложение.</span><span class="sxs-lookup"><span data-stu-id="abaaf-109">Usually this is the console application.</span></span> <span data-ttu-id="abaaf-110">Однако можно направить вывод в текстовый файл, а вывод ошибок можно перенаправить в обычный поток вывода.</span><span class="sxs-lookup"><span data-stu-id="abaaf-110">However, you can direct the output to a text file, and you can redirect error output to the regular output stream.</span></span>

<span data-ttu-id="abaaf-111">Для перенаправления выходных данных можно использовать следующие методы:</span><span class="sxs-lookup"><span data-stu-id="abaaf-111">You can use the following methods to redirect output:</span></span>

- <span data-ttu-id="abaaf-112">Используйте `Out-File` командлет, который отправляет выходные данные команды в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="abaaf-112">Use the `Out-File` cmdlet, which sends command output to a text file.</span></span>
  <span data-ttu-id="abaaf-113">Как правило, командлет используется, `Out-File` когда необходимо использовать параметры, такие как `Encoding` ,, `Force` `Width` или `NoClobber` .</span><span class="sxs-lookup"><span data-stu-id="abaaf-113">Typically, you use the `Out-File` cmdlet when you need to use its parameters, such as the `Encoding`, `Force`, `Width`, or `NoClobber` parameters.</span></span>

- <span data-ttu-id="abaaf-114">Используйте `Tee-Object` командлет, который отправляет выходные данные команды в текстовый файл и отправляет его в конвейер.</span><span class="sxs-lookup"><span data-stu-id="abaaf-114">Use the `Tee-Object` cmdlet, which sends command output to a text file and then sends it to the pipeline.</span></span>

- <span data-ttu-id="abaaf-115">Используйте операторы перенаправления PowerShell.</span><span class="sxs-lookup"><span data-stu-id="abaaf-115">Use the PowerShell redirection operators.</span></span> <span data-ttu-id="abaaf-116">Использование оператора перенаправления с целевым объектом файла функционально эквивалентно конвейеру `Out-File` без дополнительных параметров.</span><span class="sxs-lookup"><span data-stu-id="abaaf-116">Using the redirection operator with a file target is functionally equivalent to piping to `Out-File` with no extra parameters.</span></span>

<span data-ttu-id="abaaf-117">Дополнительные сведения о потоках см. в разделе [about_Output_Streams](about_Output_Streams.md).</span><span class="sxs-lookup"><span data-stu-id="abaaf-117">For more information about streams, see [about_Output_Streams](about_Output_Streams.md).</span></span>

### <a name="redirectable-output-streams"></a><span data-ttu-id="abaaf-118">Перенаправляемые выходные потоки</span><span class="sxs-lookup"><span data-stu-id="abaaf-118">Redirectable output streams</span></span>

<span data-ttu-id="abaaf-119">PowerShell поддерживает перенаправление следующих выходных потоков.</span><span class="sxs-lookup"><span data-stu-id="abaaf-119">PowerShell supports redirection of the following output streams.</span></span>

| <span data-ttu-id="abaaf-120">Вышестоящий #</span><span class="sxs-lookup"><span data-stu-id="abaaf-120">Stream #</span></span> |      <span data-ttu-id="abaaf-121">Описание</span><span class="sxs-lookup"><span data-stu-id="abaaf-121">Description</span></span>       | <span data-ttu-id="abaaf-122">Введено в</span><span class="sxs-lookup"><span data-stu-id="abaaf-122">Introduced in</span></span>  |    <span data-ttu-id="abaaf-123">Записать командлет</span><span class="sxs-lookup"><span data-stu-id="abaaf-123">Write Cmdlet</span></span>     |
| -------- | ---------------------- | -------------- | ------------------- |
| <span data-ttu-id="abaaf-124">1</span><span class="sxs-lookup"><span data-stu-id="abaaf-124">1</span></span>        | <span data-ttu-id="abaaf-125">**Успешное завершение** Вышестоящий</span><span class="sxs-lookup"><span data-stu-id="abaaf-125">**Success** Stream</span></span>     | <span data-ttu-id="abaaf-126">PowerShell 2.0</span><span class="sxs-lookup"><span data-stu-id="abaaf-126">PowerShell 2.0</span></span> | `Write-Output`      |
| <span data-ttu-id="abaaf-127">2</span><span class="sxs-lookup"><span data-stu-id="abaaf-127">2</span></span>        | <span data-ttu-id="abaaf-128">**Ошибка при** Вышестоящий</span><span class="sxs-lookup"><span data-stu-id="abaaf-128">**Error** Stream</span></span>       | <span data-ttu-id="abaaf-129">PowerShell 2.0</span><span class="sxs-lookup"><span data-stu-id="abaaf-129">PowerShell 2.0</span></span> | `Write-Error`       |
| <span data-ttu-id="abaaf-130">3</span><span class="sxs-lookup"><span data-stu-id="abaaf-130">3</span></span>        | <span data-ttu-id="abaaf-131">**Предупреждение об ошибке** Вышестоящий</span><span class="sxs-lookup"><span data-stu-id="abaaf-131">**Warning** Stream</span></span>     | <span data-ttu-id="abaaf-132">PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="abaaf-132">PowerShell 3.0</span></span> | `Write-Warning`     |
| <span data-ttu-id="abaaf-133">4</span><span class="sxs-lookup"><span data-stu-id="abaaf-133">4</span></span>        | <span data-ttu-id="abaaf-134">**Подробный вывод** Вышестоящий</span><span class="sxs-lookup"><span data-stu-id="abaaf-134">**Verbose** Stream</span></span>     | <span data-ttu-id="abaaf-135">PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="abaaf-135">PowerShell 3.0</span></span> | `Write-Verbose`     |
| <span data-ttu-id="abaaf-136">5</span><span class="sxs-lookup"><span data-stu-id="abaaf-136">5</span></span>        | <span data-ttu-id="abaaf-137">**Отладка** Вышестоящий</span><span class="sxs-lookup"><span data-stu-id="abaaf-137">**Debug** Stream</span></span>       | <span data-ttu-id="abaaf-138">PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="abaaf-138">PowerShell 3.0</span></span> | `Write-Debug`       |
| <span data-ttu-id="abaaf-139">6</span><span class="sxs-lookup"><span data-stu-id="abaaf-139">6</span></span>        | <span data-ttu-id="abaaf-140">**Сведения о** Вышестоящий</span><span class="sxs-lookup"><span data-stu-id="abaaf-140">**Information** Stream</span></span> | <span data-ttu-id="abaaf-141">PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="abaaf-141">PowerShell 5.0</span></span> | `Write-Information` |
| *        | <span data-ttu-id="abaaf-142">Все потоки</span><span class="sxs-lookup"><span data-stu-id="abaaf-142">All Streams</span></span>            | <span data-ttu-id="abaaf-143">PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="abaaf-143">PowerShell 3.0</span></span> |                     |

> [!NOTE]
> <span data-ttu-id="abaaf-144">В PowerShell также присутствует поток **хода выполнения** , но он не поддерживает перенаправление.</span><span class="sxs-lookup"><span data-stu-id="abaaf-144">There is also a **Progress** stream in PowerShell, but it does not support redirection.</span></span>

### <a name="powershell-redirection-operators"></a><span data-ttu-id="abaaf-145">Операторы перенаправления PowerShell</span><span class="sxs-lookup"><span data-stu-id="abaaf-145">PowerShell redirection operators</span></span>

<span data-ttu-id="abaaf-146">Ниже приведены операторы перенаправления PowerShell, где `n` представляет номер потока.</span><span class="sxs-lookup"><span data-stu-id="abaaf-146">The PowerShell redirection operators are as follows, where `n` represents the stream number.</span></span> <span data-ttu-id="abaaf-147">Если поток не указан, по умолчанию используется поток **Success** ( `1` ).</span><span class="sxs-lookup"><span data-stu-id="abaaf-147">The **Success** stream ( `1` ) is the default if no stream is specified.</span></span>

| <span data-ttu-id="abaaf-148">Оператор</span><span class="sxs-lookup"><span data-stu-id="abaaf-148">Operator</span></span> |                         <span data-ttu-id="abaaf-149">Описание</span><span class="sxs-lookup"><span data-stu-id="abaaf-149">Description</span></span>                         | <span data-ttu-id="abaaf-150">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="abaaf-150">Syntax</span></span> |
| -------- | ----------------------------------------------------------- | ------ |
| `>`      | <span data-ttu-id="abaaf-151">Отправить указанный поток в файл.</span><span class="sxs-lookup"><span data-stu-id="abaaf-151">Send specified stream to a file.</span></span>                            | `n>`   |
| `>>`     | <span data-ttu-id="abaaf-152">**Добавить** указанный поток в файл.</span><span class="sxs-lookup"><span data-stu-id="abaaf-152">**Append** specified stream to a file.</span></span>                      | `n>>`  |
| `>&1`    | <span data-ttu-id="abaaf-153">_Перенаправляет_ указанный поток в поток **успешного выполнения** .</span><span class="sxs-lookup"><span data-stu-id="abaaf-153">_Redirects_ the specified stream to the **Success** stream.</span></span> | `n>&1` |

> [!NOTE]
> <span data-ttu-id="abaaf-154">В отличие от некоторых оболочек UNIX, другие потоки можно перенаправить только в поток **успешного выполнения** .</span><span class="sxs-lookup"><span data-stu-id="abaaf-154">Unlike some Unix shells, you can only redirect other streams to the **Success** stream.</span></span>

## <a name="examples"></a><span data-ttu-id="abaaf-155">Примеры</span><span class="sxs-lookup"><span data-stu-id="abaaf-155">Examples</span></span>

### <a name="example-1-redirect-errors-and-output-to-a-file"></a><span data-ttu-id="abaaf-156">Пример 1. ошибки перенаправления и выходные данные в файл</span><span class="sxs-lookup"><span data-stu-id="abaaf-156">Example 1: Redirect errors and output to a file</span></span>

<span data-ttu-id="abaaf-157">Этот пример выполняется `dir` на одном элементе, который будет выполнен, и один из которых будет иметь ошибку.</span><span class="sxs-lookup"><span data-stu-id="abaaf-157">This example runs `dir` on one item that will succeed, and one that will error.</span></span>

```powershell
dir 'C:\', 'fakepath' 2>&1 > .\dir.log
```

<span data-ttu-id="abaaf-158">Он использует `2>&1` для перенаправления потока **ошибок** в поток **успешного** выполнения и `>` отправки результирующего потока **успешного выполнения** в файл с именем. `dir.log`</span><span class="sxs-lookup"><span data-stu-id="abaaf-158">It uses `2>&1` to redirect the **Error** stream to the **Success** stream, and `>` to send the resultant **Success** stream to a file called `dir.log`</span></span>

### <a name="example-2-send-all-success-stream-data-to-a-file"></a><span data-ttu-id="abaaf-159">Пример 2. Отправка всех успешных данных потока в файл</span><span class="sxs-lookup"><span data-stu-id="abaaf-159">Example 2: Send all Success stream data to a file</span></span>

<span data-ttu-id="abaaf-160">В этом примере все **успешные** потоковые данные отправляются в файл с именем `script.log` .</span><span class="sxs-lookup"><span data-stu-id="abaaf-160">This example sends all **Success** stream data to a file called `script.log`.</span></span>

```powershell
.\script.ps1 > script.log
```

### <a name="example-3-send-success-warning-and-error-streams-to-a-file"></a><span data-ttu-id="abaaf-161">Пример 3. Передача в файл успешных, предупреждающих и ошибочных потоков</span><span class="sxs-lookup"><span data-stu-id="abaaf-161">Example 3: Send Success, Warning, and Error streams to a file</span></span>

<span data-ttu-id="abaaf-162">В этом примере показано, как можно комбинировать операторы перенаправления для достижения желаемого результата.</span><span class="sxs-lookup"><span data-stu-id="abaaf-162">This example shows how you can combine redirection operators to achieve a desired result.</span></span>

```powershell
&{
   Write-Warning "hello"
   Write-Error "hello"
   Write-Output "hi"
} 3>&1 2>&1 > P:\Temp\redirection.log
```

- <span data-ttu-id="abaaf-163">`3>&1` перенаправляет поток **предупреждений** в поток **успешного выполнения** .</span><span class="sxs-lookup"><span data-stu-id="abaaf-163">`3>&1` redirects the **Warning** stream to the **Success** stream.</span></span>
- <span data-ttu-id="abaaf-164">`2>&1` перенаправляет поток **ошибок** в поток **успешного выполнения** (который также включает все данные потока **предупреждений** ).</span><span class="sxs-lookup"><span data-stu-id="abaaf-164">`2>&1` redirects the **Error** stream to the **Success** stream (which also now includes all **Warning** stream data)</span></span>
- <span data-ttu-id="abaaf-165">`>` перенаправляет поток **успешного выполнения** (который теперь содержит потоки **предупреждений** и **ошибок** ) в файл с именем `C:\temp\redirection.log` ).</span><span class="sxs-lookup"><span data-stu-id="abaaf-165">`>` redirects the **Success** stream (which now contains both **Warning** and **Error** streams) to a file called `C:\temp\redirection.log`)</span></span>

### <a name="example-4-redirect-all-streams-to-a-file"></a><span data-ttu-id="abaaf-166">Пример 4. перенаправление всех потоков в файл</span><span class="sxs-lookup"><span data-stu-id="abaaf-166">Example 4: Redirect all streams to a file</span></span>

<span data-ttu-id="abaaf-167">Этот пример отправляет все выходные данные из скрипта, вызываемого `script.ps1` в файл с именем `script.log`</span><span class="sxs-lookup"><span data-stu-id="abaaf-167">This example sends all streams output from a script called `script.ps1` to a file called `script.log`</span></span>

```powershell
.\script.ps1 *> script.log
```

### <a name="example-5-suppress-all-write-host-and-information-stream-data"></a><span data-ttu-id="abaaf-168">Пример 5. Отключение всех данных Write-Host и информационных потоков</span><span class="sxs-lookup"><span data-stu-id="abaaf-168">Example 5: Suppress all Write-Host and Information stream data</span></span>

<span data-ttu-id="abaaf-169">В этом примере подавляются все данные потока информации.</span><span class="sxs-lookup"><span data-stu-id="abaaf-169">This example suppresses all information stream data.</span></span> <span data-ttu-id="abaaf-170">Дополнительные сведения о командлетах **информационного** потока см. в статье [Write-Host](xref:Microsoft.PowerShell.Utility.Write-Host) и [Write-Information](xref:Microsoft.PowerShell.Utility.Write-Information) .</span><span class="sxs-lookup"><span data-stu-id="abaaf-170">To read more about **Information** stream cmdlets, see [Write-Host](xref:Microsoft.PowerShell.Utility.Write-Host) and [Write-Information](xref:Microsoft.PowerShell.Utility.Write-Information)</span></span>

```powershell
&{
   Write-Host "Hello"
   Write-Information "Hello" -InformationAction Continue
} 6> $null
```

### <a name="example-6-show-the-effect-of-action-preferences"></a><span data-ttu-id="abaaf-171">Пример 6. Отображение влияния настроек действий</span><span class="sxs-lookup"><span data-stu-id="abaaf-171">Example 6: Show the effect of Action Preferences</span></span>

<span data-ttu-id="abaaf-172">Переменные и параметры настройки действия могут изменять содержимое, записываемое в определенный поток.</span><span class="sxs-lookup"><span data-stu-id="abaaf-172">Action Preference variables and parameters can change what gets written to a particular stream.</span></span> <span data-ttu-id="abaaf-173">Скрипт в этом примере показывает, как значение влияет на то, `$ErrorActionPreference` что записывается в поток **ошибок** .</span><span class="sxs-lookup"><span data-stu-id="abaaf-173">The script in this example shows how the value of `$ErrorActionPreference` affects what gets written to the **Error** stream.</span></span>

```powershell
$ErrorActionPreference = 'Continue'
$ErrorActionPreference > log.txt
get-item /not-here 2>&1 >> log.txt

$ErrorActionPreference = 'SilentlyContinue'
$ErrorActionPreference >> log.txt
get-item /not-here 2>&1 >> log.txt

$ErrorActionPreference = 'Stop'
$ErrorActionPreference >> log.txt
Try {
    get-item /not-here 2>&1 >> log.txt
}
catch {
    "`tError caught!" >> log.txt
}
$ErrorActionPreference = 'Ignore'
$ErrorActionPreference >> log.txt
get-item /not-here 2>&1 >> log.txt

$ErrorActionPreference = 'Inquire'
$ErrorActionPreference >> log.txt
get-item /not-here 2>&1 >> log.txt

$ErrorActionPreference = 'Continue'
```

<span data-ttu-id="abaaf-174">При выполнении этого скрипта выводится запрос, когда `$ErrorActionPreference` для параметра задано значение `Inquire` .</span><span class="sxs-lookup"><span data-stu-id="abaaf-174">When we run this script we get prompted when `$ErrorActionPreference` is set to `Inquire`.</span></span>

```powershell
PS C:\temp> .\test.ps1

Confirm
Cannot find path 'C:\not-here' because it does not exist.
[Y] Yes  [A] Yes to All  [H] Halt Command  [S] Suspend  [?] Help (default is "Y"): H
Get-Item: C:\temp\test.ps1:23
Line |
  23 |  get-item /not-here 2>&1 >> log.txt
     |  ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
     | The running command stopped because the user selected the Stop option.
```

<span data-ttu-id="abaaf-175">При изучении файла журнала мы увидим следующее:</span><span class="sxs-lookup"><span data-stu-id="abaaf-175">When we examine the log file we see the following:</span></span>

```
PS C:\temp> Get-Content .\log.txt
Continue

Get-Item: C:\temp\test.ps1:3
Line |
   3 |  get-item /not-here 2>&1 >> log.txt
     |  ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
     | Cannot find path 'C:\not-here' because it does not exist.

SilentlyContinue
Stop
    Error caught!
Ignore
Inquire
```

## <a name="notes"></a><span data-ttu-id="abaaf-176">Примечания</span><span class="sxs-lookup"><span data-stu-id="abaaf-176">Notes</span></span>

<span data-ttu-id="abaaf-177">Операторы перенаправления, которые не добавляют данные ( `>` и `n>` ) перезаписывают текущее содержимое указанного файла без предупреждения.</span><span class="sxs-lookup"><span data-stu-id="abaaf-177">The redirection operators that do not append data (`>` and `n>`) overwrite the current contents of the specified file without warning.</span></span>

<span data-ttu-id="abaaf-178">Однако если файл доступен только для чтения, является скрытым или системным файлом, перенаправление **завершается ошибкой**.</span><span class="sxs-lookup"><span data-stu-id="abaaf-178">However, if the file is a read-only, hidden, or system file, the redirection **fails**.</span></span> <span data-ttu-id="abaaf-179">Операторы добавления перенаправления ( `>>` и `n>>` ) не записывают в файл, доступный только для чтения, но добавляют содержимое в системный или скрытый файл.</span><span class="sxs-lookup"><span data-stu-id="abaaf-179">The append redirection operators (`>>` and `n>>`) do not write to a read-only file, but they append content to a system or hidden file.</span></span>

<span data-ttu-id="abaaf-180">Для принудительного перенаправления содержимого в скрытый или системный файл только для чтения используйте `Out-File` командлет со своим `Force` параметром.</span><span class="sxs-lookup"><span data-stu-id="abaaf-180">To force the redirection of content to a read-only, hidden, or system file, use the `Out-File` cmdlet with its `Force` parameter.</span></span>

<span data-ttu-id="abaaf-181">При записи в файлы операторы перенаправления используют `UTF8NoBOM` кодировку.</span><span class="sxs-lookup"><span data-stu-id="abaaf-181">When you are writing to files, the redirection operators use `UTF8NoBOM` encoding.</span></span> <span data-ttu-id="abaaf-182">Если файл имеет другую кодировку, выходные данные могут быть неправильно отформатированы.</span><span class="sxs-lookup"><span data-stu-id="abaaf-182">If the file has a different encoding, the output might not be formatted correctly.</span></span> <span data-ttu-id="abaaf-183">Для записи в файлы с другой кодировкой используйте `Out-File` командлет с его `Encoding` параметром.</span><span class="sxs-lookup"><span data-stu-id="abaaf-183">To write to files with a different encoding, use the `Out-File` cmdlet with its `Encoding` parameter.</span></span>

### <a name="potential-confusion-with-comparison-operators"></a><span data-ttu-id="abaaf-184">Потенциальная путаница с операторами сравнения</span><span class="sxs-lookup"><span data-stu-id="abaaf-184">Potential confusion with comparison operators</span></span>

<span data-ttu-id="abaaf-185">`>`Оператор не следует путать с оператором сравнения " [больше](about_Comparison_Operators.md#-gt) " (часто обозначается как `>` в других языках программирования).</span><span class="sxs-lookup"><span data-stu-id="abaaf-185">The `>` operator is not to be confused with the [Greater-than](about_Comparison_Operators.md#-gt) comparison operator (often denoted as `>` in other programming languages).</span></span>

<span data-ttu-id="abaaf-186">В зависимости от сравниваемых объектов выходные данные `>` могут выглядеть правильными (поскольку 36 не превышает 42).</span><span class="sxs-lookup"><span data-stu-id="abaaf-186">Depending on the objects being compared, the output using `>` can appear to be correct (because 36 is not greater than 42).</span></span>

```powershell
PS> if (36 > 42) { "true" } else { "false" }
false
```

<span data-ttu-id="abaaf-187">Однако проверка локальной файловой системы может видеть, что файл `42` с именем был записан с содержимым `36` .</span><span class="sxs-lookup"><span data-stu-id="abaaf-187">However, a check of the local filesystem can see that a file called `42` was written, with the contents `36`.</span></span>

```powershell
PS> dir

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
------          1/02/20  10:10 am              3 42

PS> cat 42
36
```

<span data-ttu-id="abaaf-188">Попытка использовать обратные сравнения `<` (меньше) приводит к системной ошибке:</span><span class="sxs-lookup"><span data-stu-id="abaaf-188">Attempting to use the reverse comparison `<` (less than), yields a system error:</span></span>

```powershell
PS> if (36 < 42) { "true" } else { "false" }
At line:1 char:8
+ if (36 < 42) { "true" } else { "false" }
+        ~
The '<' operator is reserved for future use.
+ CategoryInfo          : ParserError: (:) [], ParentContainsErrorRecordException
+ FullyQualifiedErrorId : RedirectionNotSupported
```

<span data-ttu-id="abaaf-189">Значение, если числовое сравнение является обязательной операцией `-lt` и `-gt` должно использоваться.</span><span class="sxs-lookup"><span data-stu-id="abaaf-189">If numeric comparison is the required operation, `-lt` and `-gt` should be used.</span></span> <span data-ttu-id="abaaf-190">См. раздел [ `-gt` оператор сравнения](about_Comparison_Operators.md#-gt) .</span><span class="sxs-lookup"><span data-stu-id="abaaf-190">See: [`-gt` Comparison Operator](about_Comparison_Operators.md#-gt)</span></span>

## <a name="see-also"></a><span data-ttu-id="abaaf-191">См. также статью</span><span class="sxs-lookup"><span data-stu-id="abaaf-191">See also</span></span>

- [<span data-ttu-id="abaaf-192">Out-File</span><span class="sxs-lookup"><span data-stu-id="abaaf-192">Out-File</span></span>](xref:Microsoft.PowerShell.Utility.Out-File)
- [<span data-ttu-id="abaaf-193">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="abaaf-193">Tee-Object</span></span>](xref:Microsoft.PowerShell.Utility.Tee-Object)
- [<span data-ttu-id="abaaf-194">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="abaaf-194">Write-Debug</span></span>](xref:Microsoft.PowerShell.Utility.Write-Debug)
- [<span data-ttu-id="abaaf-195">Ошибка записи</span><span class="sxs-lookup"><span data-stu-id="abaaf-195">Write-Error</span></span>](xref:Microsoft.PowerShell.Utility.Write-Error)
- [<span data-ttu-id="abaaf-196">Write-Host</span><span class="sxs-lookup"><span data-stu-id="abaaf-196">Write-Host</span></span>](xref:Microsoft.PowerShell.Utility.Write-Host)
- [<span data-ttu-id="abaaf-197">Write-Information</span><span class="sxs-lookup"><span data-stu-id="abaaf-197">Write-Information</span></span>](xref:Microsoft.PowerShell.Utility.Write-Information)
- [<span data-ttu-id="abaaf-198">Write-Output</span><span class="sxs-lookup"><span data-stu-id="abaaf-198">Write-Output</span></span>](xref:Microsoft.PowerShell.Utility.Write-Output)
- [<span data-ttu-id="abaaf-199">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="abaaf-199">Write-Progress</span></span>](xref:Microsoft.PowerShell.Utility.Write-Progress)
- [<span data-ttu-id="abaaf-200">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="abaaf-200">Write-Verbose</span></span>](xref:Microsoft.PowerShell.Utility.Write-Verbose)
- [<span data-ttu-id="abaaf-201">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="abaaf-201">Write-Warning</span></span>](xref:Microsoft.PowerShell.Utility.Write-Warning)
- [<span data-ttu-id="abaaf-202">about_Output_Streams</span><span class="sxs-lookup"><span data-stu-id="abaaf-202">about_Output_Streams</span></span>](about_Output_Streams.md)
- [<span data-ttu-id="abaaf-203">about_Operators</span><span class="sxs-lookup"><span data-stu-id="abaaf-203">about_Operators</span></span>](about_Operators.md)
- [<span data-ttu-id="abaaf-204">about_Command_Syntax</span><span class="sxs-lookup"><span data-stu-id="abaaf-204">about_Command_Syntax</span></span>](about_Command_Syntax.md)
- [<span data-ttu-id="abaaf-205">about_Path_Syntax</span><span class="sxs-lookup"><span data-stu-id="abaaf-205">about_Path_Syntax</span></span>](about_Path_Syntax.md)
