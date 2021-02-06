---
description: Объясняется, как перенаправлять выходные данные из PowerShell в текстовые файлы.
Locale: en-US
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_redirection?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Redirection
ms.openlocfilehash: 91eb3f524ddeeb729ce53749c9b0ae922ce21f18
ms.sourcegitcommit: b9826dcf402db8a2b6d3eab37edb82c6af113343
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2021
ms.locfileid: "99604665"
---
# <a name="about-redirection"></a><span data-ttu-id="fbf5f-103">О перенаправлении</span><span class="sxs-lookup"><span data-stu-id="fbf5f-103">About Redirection</span></span>

## <a name="short-description"></a><span data-ttu-id="fbf5f-104">Краткое описание</span><span class="sxs-lookup"><span data-stu-id="fbf5f-104">Short description</span></span>
<span data-ttu-id="fbf5f-105">Объясняется, как перенаправлять выходные данные из PowerShell в текстовые файлы.</span><span class="sxs-lookup"><span data-stu-id="fbf5f-105">Explains how to redirect output from PowerShell to text files.</span></span>

## <a name="long-description"></a><span data-ttu-id="fbf5f-106">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="fbf5f-106">Long description</span></span>

<span data-ttu-id="fbf5f-107">По умолчанию PowerShell отправляет выходные данные на узел PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fbf5f-107">By default, PowerShell sends output to the PowerShell host.</span></span> <span data-ttu-id="fbf5f-108">Обычно это консольное приложение.</span><span class="sxs-lookup"><span data-stu-id="fbf5f-108">Usually this is the console application.</span></span> <span data-ttu-id="fbf5f-109">Однако можно направить вывод в текстовый файл, а вывод ошибок можно перенаправить в обычный поток вывода.</span><span class="sxs-lookup"><span data-stu-id="fbf5f-109">However, you can direct the output to a text file, and you can redirect error output to the regular output stream.</span></span>

<span data-ttu-id="fbf5f-110">Для перенаправления выходных данных можно использовать следующие методы:</span><span class="sxs-lookup"><span data-stu-id="fbf5f-110">You can use the following methods to redirect output:</span></span>

- <span data-ttu-id="fbf5f-111">Используйте `Out-File` командлет, который отправляет выходные данные команды в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="fbf5f-111">Use the `Out-File` cmdlet, which sends command output to a text file.</span></span>
  <span data-ttu-id="fbf5f-112">Как правило, командлет используется, `Out-File` когда необходимо использовать параметры, такие как `Encoding` ,, `Force` `Width` или `NoClobber` .</span><span class="sxs-lookup"><span data-stu-id="fbf5f-112">Typically, you use the `Out-File` cmdlet when you need to use its parameters, such as the `Encoding`, `Force`, `Width`, or `NoClobber` parameters.</span></span>

- <span data-ttu-id="fbf5f-113">Используйте `Tee-Object` командлет, который отправляет выходные данные команды в текстовый файл и отправляет его в конвейер.</span><span class="sxs-lookup"><span data-stu-id="fbf5f-113">Use the `Tee-Object` cmdlet, which sends command output to a text file and then sends it to the pipeline.</span></span>

- <span data-ttu-id="fbf5f-114">Используйте операторы перенаправления PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fbf5f-114">Use the PowerShell redirection operators.</span></span> <span data-ttu-id="fbf5f-115">Использование оператора перенаправления с целевым объектом файла функционально эквивалентно конвейеру `Out-File` без дополнительных параметров.</span><span class="sxs-lookup"><span data-stu-id="fbf5f-115">Using the redirection operator with a file target is functionally equivalent to piping to `Out-File` with no extra parameters.</span></span>

<span data-ttu-id="fbf5f-116">Дополнительные сведения о потоках см. в разделе [about_Output_Streams](about_Output_Streams.md).</span><span class="sxs-lookup"><span data-stu-id="fbf5f-116">For more information about streams, see [about_Output_Streams](about_Output_Streams.md).</span></span>

### <a name="redirectable-output-streams"></a><span data-ttu-id="fbf5f-117">Перенаправляемые выходные потоки</span><span class="sxs-lookup"><span data-stu-id="fbf5f-117">Redirectable output streams</span></span>

<span data-ttu-id="fbf5f-118">PowerShell поддерживает перенаправление следующих выходных потоков.</span><span class="sxs-lookup"><span data-stu-id="fbf5f-118">PowerShell supports redirection of the following output streams.</span></span>

| <span data-ttu-id="fbf5f-119">Вышестоящий #</span><span class="sxs-lookup"><span data-stu-id="fbf5f-119">Stream #</span></span> |      <span data-ttu-id="fbf5f-120">Описание</span><span class="sxs-lookup"><span data-stu-id="fbf5f-120">Description</span></span>       | <span data-ttu-id="fbf5f-121">Введено в</span><span class="sxs-lookup"><span data-stu-id="fbf5f-121">Introduced in</span></span>  |    <span data-ttu-id="fbf5f-122">Записать командлет</span><span class="sxs-lookup"><span data-stu-id="fbf5f-122">Write Cmdlet</span></span>     |
| -------- | ---------------------- | -------------- | ------------------- |
| <span data-ttu-id="fbf5f-123">1</span><span class="sxs-lookup"><span data-stu-id="fbf5f-123">1</span></span>        | <span data-ttu-id="fbf5f-124">**Успешное завершение** Вышестоящий</span><span class="sxs-lookup"><span data-stu-id="fbf5f-124">**Success** Stream</span></span>     | <span data-ttu-id="fbf5f-125">PowerShell 2.0</span><span class="sxs-lookup"><span data-stu-id="fbf5f-125">PowerShell 2.0</span></span> | `Write-Output`      |
| <span data-ttu-id="fbf5f-126">2</span><span class="sxs-lookup"><span data-stu-id="fbf5f-126">2</span></span>        | <span data-ttu-id="fbf5f-127">**Ошибка при** Вышестоящий</span><span class="sxs-lookup"><span data-stu-id="fbf5f-127">**Error** Stream</span></span>       | <span data-ttu-id="fbf5f-128">PowerShell 2.0</span><span class="sxs-lookup"><span data-stu-id="fbf5f-128">PowerShell 2.0</span></span> | `Write-Error`       |
| <span data-ttu-id="fbf5f-129">3</span><span class="sxs-lookup"><span data-stu-id="fbf5f-129">3</span></span>        | <span data-ttu-id="fbf5f-130">**Предупреждение об ошибке** Вышестоящий</span><span class="sxs-lookup"><span data-stu-id="fbf5f-130">**Warning** Stream</span></span>     | <span data-ttu-id="fbf5f-131">PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="fbf5f-131">PowerShell 3.0</span></span> | `Write-Warning`     |
| <span data-ttu-id="fbf5f-132">4</span><span class="sxs-lookup"><span data-stu-id="fbf5f-132">4</span></span>        | <span data-ttu-id="fbf5f-133">**Подробный вывод** Вышестоящий</span><span class="sxs-lookup"><span data-stu-id="fbf5f-133">**Verbose** Stream</span></span>     | <span data-ttu-id="fbf5f-134">PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="fbf5f-134">PowerShell 3.0</span></span> | `Write-Verbose`     |
| <span data-ttu-id="fbf5f-135">5</span><span class="sxs-lookup"><span data-stu-id="fbf5f-135">5</span></span>        | <span data-ttu-id="fbf5f-136">**Отладка** Вышестоящий</span><span class="sxs-lookup"><span data-stu-id="fbf5f-136">**Debug** Stream</span></span>       | <span data-ttu-id="fbf5f-137">PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="fbf5f-137">PowerShell 3.0</span></span> | `Write-Debug`       |
| <span data-ttu-id="fbf5f-138">6</span><span class="sxs-lookup"><span data-stu-id="fbf5f-138">6</span></span>        | <span data-ttu-id="fbf5f-139">**Сведения о** Вышестоящий</span><span class="sxs-lookup"><span data-stu-id="fbf5f-139">**Information** Stream</span></span> | <span data-ttu-id="fbf5f-140">PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="fbf5f-140">PowerShell 5.0</span></span> | `Write-Information` |
| *        | <span data-ttu-id="fbf5f-141">Все потоки</span><span class="sxs-lookup"><span data-stu-id="fbf5f-141">All Streams</span></span>            | <span data-ttu-id="fbf5f-142">PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="fbf5f-142">PowerShell 3.0</span></span> |                     |

> [!NOTE]
> <span data-ttu-id="fbf5f-143">В PowerShell также присутствует поток **хода выполнения** , но он не поддерживает перенаправление.</span><span class="sxs-lookup"><span data-stu-id="fbf5f-143">There is also a **Progress** stream in PowerShell, but it does not support redirection.</span></span>

### <a name="powershell-redirection-operators"></a><span data-ttu-id="fbf5f-144">Операторы перенаправления PowerShell</span><span class="sxs-lookup"><span data-stu-id="fbf5f-144">PowerShell redirection operators</span></span>

<span data-ttu-id="fbf5f-145">Ниже приведены операторы перенаправления PowerShell, где `n` представляет номер потока.</span><span class="sxs-lookup"><span data-stu-id="fbf5f-145">The PowerShell redirection operators are as follows, where `n` represents the stream number.</span></span> <span data-ttu-id="fbf5f-146">Если поток не указан, по умолчанию используется поток **Success** ( `1` ).</span><span class="sxs-lookup"><span data-stu-id="fbf5f-146">The **Success** stream ( `1` ) is the default if no stream is specified.</span></span>

| <span data-ttu-id="fbf5f-147">Оператор</span><span class="sxs-lookup"><span data-stu-id="fbf5f-147">Operator</span></span> |                         <span data-ttu-id="fbf5f-148">Описание</span><span class="sxs-lookup"><span data-stu-id="fbf5f-148">Description</span></span>                         | <span data-ttu-id="fbf5f-149">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fbf5f-149">Syntax</span></span> |
| -------- | ----------------------------------------------------------- | ------ |
| `>`      | <span data-ttu-id="fbf5f-150">Отправить указанный поток в файл.</span><span class="sxs-lookup"><span data-stu-id="fbf5f-150">Send specified stream to a file.</span></span>                            | `n>`   |
| `>>`     | <span data-ttu-id="fbf5f-151">**Добавить** указанный поток в файл.</span><span class="sxs-lookup"><span data-stu-id="fbf5f-151">**Append** specified stream to a file.</span></span>                      | `n>>`  |
| `>&1`    | <span data-ttu-id="fbf5f-152">_Перенаправляет_ указанный поток в поток **успешного выполнения** .</span><span class="sxs-lookup"><span data-stu-id="fbf5f-152">_Redirects_ the specified stream to the **Success** stream.</span></span> | `n>&1` |

> [!NOTE]
> <span data-ttu-id="fbf5f-153">В отличие от некоторых оболочек UNIX, другие потоки можно перенаправить только в поток **успешного выполнения** .</span><span class="sxs-lookup"><span data-stu-id="fbf5f-153">Unlike some Unix shells, you can only redirect other streams to the **Success** stream.</span></span>

## <a name="examples"></a><span data-ttu-id="fbf5f-154">Примеры</span><span class="sxs-lookup"><span data-stu-id="fbf5f-154">Examples</span></span>

### <a name="example-1-redirect-errors-and-output-to-a-file"></a><span data-ttu-id="fbf5f-155">Пример 1. ошибки перенаправления и выходные данные в файл</span><span class="sxs-lookup"><span data-stu-id="fbf5f-155">Example 1: Redirect errors and output to a file</span></span>

<span data-ttu-id="fbf5f-156">Этот пример выполняется `dir` на одном элементе, который будет выполнен, и один из которых будет иметь ошибку.</span><span class="sxs-lookup"><span data-stu-id="fbf5f-156">This example runs `dir` on one item that will succeed, and one that will error.</span></span>

```powershell
dir 'C:\', 'fakepath' 2>&1 > .\dir.log
```

<span data-ttu-id="fbf5f-157">Он использует `2>&1` для перенаправления потока **ошибок** в поток **успешного** выполнения и `>` отправки результирующего потока **успешного выполнения** в файл с именем. `dir.log`</span><span class="sxs-lookup"><span data-stu-id="fbf5f-157">It uses `2>&1` to redirect the **Error** stream to the **Success** stream, and `>` to send the resultant **Success** stream to a file called `dir.log`</span></span>

### <a name="example-2-send-all-success-stream-data-to-a-file"></a><span data-ttu-id="fbf5f-158">Пример 2. Отправка всех успешных данных потока в файл</span><span class="sxs-lookup"><span data-stu-id="fbf5f-158">Example 2: Send all Success stream data to a file</span></span>

<span data-ttu-id="fbf5f-159">В этом примере все **успешные** потоковые данные отправляются в файл с именем `script.log` .</span><span class="sxs-lookup"><span data-stu-id="fbf5f-159">This example sends all **Success** stream data to a file called `script.log`.</span></span>

```powershell
.\script.ps1 > script.log
```

### <a name="example-3-send-success-warning-and-error-streams-to-a-file"></a><span data-ttu-id="fbf5f-160">Пример 3. Передача в файл успешных, предупреждающих и ошибочных потоков</span><span class="sxs-lookup"><span data-stu-id="fbf5f-160">Example 3: Send Success, Warning, and Error streams to a file</span></span>

<span data-ttu-id="fbf5f-161">В этом примере показано, как можно комбинировать операторы перенаправления для достижения желаемого результата.</span><span class="sxs-lookup"><span data-stu-id="fbf5f-161">This example shows how you can combine redirection operators to achieve a desired result.</span></span>

```powershell
&{
   Write-Warning "hello"
   Write-Error "hello"
   Write-Output "hi"
} 3>&1 2>&1 > C:\Temp\redirection.log
```

- <span data-ttu-id="fbf5f-162">`3>&1` перенаправляет поток **предупреждений** в поток **успешного выполнения** .</span><span class="sxs-lookup"><span data-stu-id="fbf5f-162">`3>&1` redirects the **Warning** stream to the **Success** stream.</span></span>
- <span data-ttu-id="fbf5f-163">`2>&1` перенаправляет поток **ошибок** в поток **успешного выполнения** (который также включает все данные потока **предупреждений** ).</span><span class="sxs-lookup"><span data-stu-id="fbf5f-163">`2>&1` redirects the **Error** stream to the **Success** stream (which also now includes all **Warning** stream data)</span></span>
- <span data-ttu-id="fbf5f-164">`>` перенаправляет поток **успешного выполнения** (который теперь содержит потоки **предупреждений** и **ошибок** ) в файл с именем `C:\temp\redirection.log` ).</span><span class="sxs-lookup"><span data-stu-id="fbf5f-164">`>` redirects the **Success** stream (which now contains both **Warning** and **Error** streams) to a file called `C:\temp\redirection.log`)</span></span>

### <a name="example-4-redirect-all-streams-to-a-file"></a><span data-ttu-id="fbf5f-165">Пример 4. перенаправление всех потоков в файл</span><span class="sxs-lookup"><span data-stu-id="fbf5f-165">Example 4: Redirect all streams to a file</span></span>

<span data-ttu-id="fbf5f-166">Этот пример отправляет все выходные данные из скрипта, вызываемого `script.ps1` в файл с именем `script.log`</span><span class="sxs-lookup"><span data-stu-id="fbf5f-166">This example sends all streams output from a script called `script.ps1` to a file called `script.log`</span></span>

```powershell
.\script.ps1 *> script.log
```

### <a name="example-5-suppress-all-write-host-and-information-stream-data"></a><span data-ttu-id="fbf5f-167">Пример 5. Отключение всех данных Write-Host и информационных потоков</span><span class="sxs-lookup"><span data-stu-id="fbf5f-167">Example 5: Suppress all Write-Host and Information stream data</span></span>

<span data-ttu-id="fbf5f-168">В этом примере подавляются все данные потока информации.</span><span class="sxs-lookup"><span data-stu-id="fbf5f-168">This example suppresses all information stream data.</span></span> <span data-ttu-id="fbf5f-169">Дополнительные сведения о командлетах **информационного** потока см. в статье [Write-Host](xref:Microsoft.PowerShell.Utility.Write-Host) и [Write-Information](xref:Microsoft.PowerShell.Utility.Write-Information) .</span><span class="sxs-lookup"><span data-stu-id="fbf5f-169">To read more about **Information** stream cmdlets, see [Write-Host](xref:Microsoft.PowerShell.Utility.Write-Host) and [Write-Information](xref:Microsoft.PowerShell.Utility.Write-Information)</span></span>

```powershell
&{
   Write-Host "Hello"
   Write-Information "Hello" -InformationAction Continue
} 6> $null
```

### <a name="example-6-show-the-effect-of-action-preferences"></a><span data-ttu-id="fbf5f-170">Пример 6. Отображение влияния настроек действий</span><span class="sxs-lookup"><span data-stu-id="fbf5f-170">Example 6: Show the effect of Action Preferences</span></span>

<span data-ttu-id="fbf5f-171">Переменные и параметры настройки действия могут изменять содержимое, записываемое в определенный поток.</span><span class="sxs-lookup"><span data-stu-id="fbf5f-171">Action Preference variables and parameters can change what gets written to a particular stream.</span></span> <span data-ttu-id="fbf5f-172">Скрипт в этом примере показывает, как значение влияет на то, `$ErrorActionPreference` что записывается в поток **ошибок** .</span><span class="sxs-lookup"><span data-stu-id="fbf5f-172">The script in this example shows how the value of `$ErrorActionPreference` affects what gets written to the **Error** stream.</span></span>

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

<span data-ttu-id="fbf5f-173">При выполнении этого скрипта выводится запрос, когда `$ErrorActionPreference` для параметра задано значение `Inquire` .</span><span class="sxs-lookup"><span data-stu-id="fbf5f-173">When we run this script we get prompted when `$ErrorActionPreference` is set to `Inquire`.</span></span>

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

<span data-ttu-id="fbf5f-174">При изучении файла журнала мы увидим следующее:</span><span class="sxs-lookup"><span data-stu-id="fbf5f-174">When we examine the log file we see the following:</span></span>

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

## <a name="notes"></a><span data-ttu-id="fbf5f-175">Примечания</span><span class="sxs-lookup"><span data-stu-id="fbf5f-175">Notes</span></span>

<span data-ttu-id="fbf5f-176">Операторы перенаправления, которые не добавляют данные ( `>` и `n>` ) перезаписывают текущее содержимое указанного файла без предупреждения.</span><span class="sxs-lookup"><span data-stu-id="fbf5f-176">The redirection operators that do not append data (`>` and `n>`) overwrite the current contents of the specified file without warning.</span></span>

<span data-ttu-id="fbf5f-177">Однако если файл доступен только для чтения, является скрытым или системным файлом, перенаправление **завершается ошибкой**.</span><span class="sxs-lookup"><span data-stu-id="fbf5f-177">However, if the file is a read-only, hidden, or system file, the redirection **fails**.</span></span> <span data-ttu-id="fbf5f-178">Операторы добавления перенаправления ( `>>` и `n>>` ) не записывают в файл, доступный только для чтения, но добавляют содержимое в системный или скрытый файл.</span><span class="sxs-lookup"><span data-stu-id="fbf5f-178">The append redirection operators (`>>` and `n>>`) do not write to a read-only file, but they append content to a system or hidden file.</span></span>

<span data-ttu-id="fbf5f-179">Для принудительного перенаправления содержимого в скрытый или системный файл только для чтения используйте `Out-File` командлет со своим `Force` параметром.</span><span class="sxs-lookup"><span data-stu-id="fbf5f-179">To force the redirection of content to a read-only, hidden, or system file, use the `Out-File` cmdlet with its `Force` parameter.</span></span>

<span data-ttu-id="fbf5f-180">При записи в файлы операторы перенаправления используют `UTF8NoBOM` кодировку.</span><span class="sxs-lookup"><span data-stu-id="fbf5f-180">When you are writing to files, the redirection operators use `UTF8NoBOM` encoding.</span></span> <span data-ttu-id="fbf5f-181">Если файл имеет другую кодировку, выходные данные могут быть неправильно отформатированы.</span><span class="sxs-lookup"><span data-stu-id="fbf5f-181">If the file has a different encoding, the output might not be formatted correctly.</span></span> <span data-ttu-id="fbf5f-182">Для записи в файлы с другой кодировкой используйте `Out-File` командлет с его `Encoding` параметром.</span><span class="sxs-lookup"><span data-stu-id="fbf5f-182">To write to files with a different encoding, use the `Out-File` cmdlet with its `Encoding` parameter.</span></span>

### <a name="potential-confusion-with-comparison-operators"></a><span data-ttu-id="fbf5f-183">Потенциальная путаница с операторами сравнения</span><span class="sxs-lookup"><span data-stu-id="fbf5f-183">Potential confusion with comparison operators</span></span>

<span data-ttu-id="fbf5f-184">`>`Оператор не следует путать с оператором сравнения " [больше](about_Comparison_Operators.md#-gt--ge--lt-and--le) " (часто обозначается как `>` в других языках программирования).</span><span class="sxs-lookup"><span data-stu-id="fbf5f-184">The `>` operator is not to be confused with the [Greater-than](about_Comparison_Operators.md#-gt--ge--lt-and--le) comparison operator (often denoted as `>` in other programming languages).</span></span>

<span data-ttu-id="fbf5f-185">В зависимости от сравниваемых объектов выходные данные `>` могут выглядеть правильными (поскольку 36 не превышает 42).</span><span class="sxs-lookup"><span data-stu-id="fbf5f-185">Depending on the objects being compared, the output using `>` can appear to be correct (because 36 is not greater than 42).</span></span>

```powershell
PS> if (36 > 42) { "true" } else { "false" }
false
```

<span data-ttu-id="fbf5f-186">Однако проверка локальной файловой системы может видеть, что файл `42` с именем был записан с содержимым `36` .</span><span class="sxs-lookup"><span data-stu-id="fbf5f-186">However, a check of the local filesystem can see that a file called `42` was written, with the contents `36`.</span></span>

```powershell
PS> dir

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
------          1/02/20  10:10 am              3 42

PS> cat 42
36
```

<span data-ttu-id="fbf5f-187">Попытка использовать обратные сравнения `<` (меньше) приводит к системной ошибке:</span><span class="sxs-lookup"><span data-stu-id="fbf5f-187">Attempting to use the reverse comparison `<` (less than), yields a system error:</span></span>

```powershell
PS> if (36 < 42) { "true" } else { "false" }
At line:1 char:8
+ if (36 < 42) { "true" } else { "false" }
+        ~
The '<' operator is reserved for future use.
    + CategoryInfo          : ParserError: (:) [], ParentContainsErrorRecordException
    + FullyQualifiedErrorId : RedirectionNotSupported
```

<span data-ttu-id="fbf5f-188">Значение, если числовое сравнение является обязательной операцией `-lt` и `-gt` должно использоваться.</span><span class="sxs-lookup"><span data-stu-id="fbf5f-188">If numeric comparison is the required operation, `-lt` and `-gt` should be used.</span></span> <span data-ttu-id="fbf5f-189">Дополнительные сведения см. в описании `-gt` оператора в [about_Comparison_Operators](about_Comparison_Operators.md#-gt--ge--lt-and--le).</span><span class="sxs-lookup"><span data-stu-id="fbf5f-189">For more information, see the `-gt` operator in [about_Comparison_Operators](about_Comparison_Operators.md#-gt--ge--lt-and--le).</span></span>

## <a name="see-also"></a><span data-ttu-id="fbf5f-190">См. также</span><span class="sxs-lookup"><span data-stu-id="fbf5f-190">See also</span></span>

- [<span data-ttu-id="fbf5f-191">Out-File</span><span class="sxs-lookup"><span data-stu-id="fbf5f-191">Out-File</span></span>](xref:Microsoft.PowerShell.Utility.Out-File)
- [<span data-ttu-id="fbf5f-192">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="fbf5f-192">Tee-Object</span></span>](xref:Microsoft.PowerShell.Utility.Tee-Object)
- [<span data-ttu-id="fbf5f-193">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="fbf5f-193">Write-Debug</span></span>](xref:Microsoft.PowerShell.Utility.Write-Debug)
- [<span data-ttu-id="fbf5f-194">Write-Error</span><span class="sxs-lookup"><span data-stu-id="fbf5f-194">Write-Error</span></span>](xref:Microsoft.PowerShell.Utility.Write-Error)
- [<span data-ttu-id="fbf5f-195">Write-Host</span><span class="sxs-lookup"><span data-stu-id="fbf5f-195">Write-Host</span></span>](xref:Microsoft.PowerShell.Utility.Write-Host)
- [<span data-ttu-id="fbf5f-196">Write-Information</span><span class="sxs-lookup"><span data-stu-id="fbf5f-196">Write-Information</span></span>](xref:Microsoft.PowerShell.Utility.Write-Information)
- [<span data-ttu-id="fbf5f-197">Write-Output</span><span class="sxs-lookup"><span data-stu-id="fbf5f-197">Write-Output</span></span>](xref:Microsoft.PowerShell.Utility.Write-Output)
- [<span data-ttu-id="fbf5f-198">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="fbf5f-198">Write-Progress</span></span>](xref:Microsoft.PowerShell.Utility.Write-Progress)
- [<span data-ttu-id="fbf5f-199">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="fbf5f-199">Write-Verbose</span></span>](xref:Microsoft.PowerShell.Utility.Write-Verbose)
- [<span data-ttu-id="fbf5f-200">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="fbf5f-200">Write-Warning</span></span>](xref:Microsoft.PowerShell.Utility.Write-Warning)
- [<span data-ttu-id="fbf5f-201">О потоках вывода</span><span class="sxs-lookup"><span data-stu-id="fbf5f-201">about_Output_Streams</span></span>](about_Output_Streams.md)
- [<span data-ttu-id="fbf5f-202">about_Operators</span><span class="sxs-lookup"><span data-stu-id="fbf5f-202">about_Operators</span></span>](about_Operators.md)
- [<span data-ttu-id="fbf5f-203">about_Command_Syntax</span><span class="sxs-lookup"><span data-stu-id="fbf5f-203">about_Command_Syntax</span></span>](about_Command_Syntax.md)
- [<span data-ttu-id="fbf5f-204">about_Path_Syntax</span><span class="sxs-lookup"><span data-stu-id="fbf5f-204">about_Path_Syntax</span></span>](about_Path_Syntax.md)
