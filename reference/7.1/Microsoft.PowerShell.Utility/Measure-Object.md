---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/measure-object?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Measure-Object;
ms.openlocfilehash: 88b18a929a1debc85eb7ce65dbdf2d14fc4b89cd
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2020
ms.locfileid: "93230301"
---
# <span data-ttu-id="82a30-103">Measure-Object;</span><span class="sxs-lookup"><span data-stu-id="82a30-103">Measure-Object</span></span>

## <span data-ttu-id="82a30-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="82a30-104">SYNOPSIS</span></span>
<span data-ttu-id="82a30-105">Рассчитывает числовые свойства объектов, а также количество знаков, слов и строк в строковых объектах, например в текстовых файлах.</span><span class="sxs-lookup"><span data-stu-id="82a30-105">Calculates the numeric properties of objects, and the characters, words, and lines in string objects, such as files of text.</span></span>

## <span data-ttu-id="82a30-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="82a30-106">SYNTAX</span></span>

### <span data-ttu-id="82a30-107">Женерикмеасуре (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="82a30-107">GenericMeasure (Default)</span></span>

```
Measure-Object [[-Property] <PSPropertyExpression[]>] [-InputObject <PSObject>] [-StandardDeviation]
 [-Sum] [-AllStats] [-Average] [-Maximum] [-Minimum] [<CommonParameters>]
```

### <span data-ttu-id="82a30-108">текстмеасуре</span><span class="sxs-lookup"><span data-stu-id="82a30-108">TextMeasure</span></span>

```
Measure-Object [[-Property] <PSPropertyExpression[]>] [-InputObject <PSObject>] [-Line] [-Word]
 [-Character] [-IgnoreWhiteSpace] [<CommonParameters>]
```

## <span data-ttu-id="82a30-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="82a30-109">DESCRIPTION</span></span>

<span data-ttu-id="82a30-110">`Measure-Object`Командлет вычисляет значения свойств определенных типов объектов.</span><span class="sxs-lookup"><span data-stu-id="82a30-110">The `Measure-Object` cmdlet calculates the property values of certain types of object.</span></span>
<span data-ttu-id="82a30-111">`Measure-Object` выполняет три типа измерений в зависимости от параметров в команде.</span><span class="sxs-lookup"><span data-stu-id="82a30-111">`Measure-Object` performs three types of measurements, depending on the parameters in the command.</span></span>

<span data-ttu-id="82a30-112">`Measure-Object`Командлет выполняет вычисления со значениями свойств объектов.</span><span class="sxs-lookup"><span data-stu-id="82a30-112">The `Measure-Object` cmdlet performs calculations on the property values of objects.</span></span> <span data-ttu-id="82a30-113">Можно использовать `Measure-Object` для подсчета объектов или количества объектов с указанным **свойством** .</span><span class="sxs-lookup"><span data-stu-id="82a30-113">You can use `Measure-Object` to count objects or count objects with a specified **Property** .</span></span> <span data-ttu-id="82a30-114">Можно также использовать `Measure-Object` для вычисления **минимального** , **максимального** , **итогового** , **стандартное отклонение** и **среднего** значения числовых значений.</span><span class="sxs-lookup"><span data-stu-id="82a30-114">You can also use `Measure-Object` to calculate the **Minimum** , **Maximum** , **Sum** , **StandardDeviation** and **Average** of numeric values.</span></span> <span data-ttu-id="82a30-115">Для **строковых** объектов можно также использовать `Measure-Object` для подсчета количества строк, слов и символов.</span><span class="sxs-lookup"><span data-stu-id="82a30-115">For **String** objects, you can also use `Measure-Object` to count the number of lines, words, and characters.</span></span>

## <span data-ttu-id="82a30-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="82a30-116">EXAMPLES</span></span>

### <span data-ttu-id="82a30-117">Пример 1. подсчет файлов и папок в каталоге</span><span class="sxs-lookup"><span data-stu-id="82a30-117">Example 1: Count the files and folders in a directory</span></span>

<span data-ttu-id="82a30-118">Эта команда определяет количество файлов и папок в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="82a30-118">This command counts the files and folders in the current directory.</span></span>

```powershell
Get-ChildItem | Measure-Object
```

### <span data-ttu-id="82a30-119">Пример 2. Измерение файлов в каталоге</span><span class="sxs-lookup"><span data-stu-id="82a30-119">Example 2: Measure the files in a directory</span></span>

<span data-ttu-id="82a30-120">Эта команда отображает **минимальные** , **максимальные** и **суммарные** размеры всех файлов в текущем каталоге, а также средний размер файла в каталоге.</span><span class="sxs-lookup"><span data-stu-id="82a30-120">This command displays the **Minimum** , **Maximum** , and **Sum** of the sizes of all files in the current directory, and the average size of a file in the directory.</span></span>

```powershell
Get-ChildItem | Measure-Object -Property length -Minimum -Maximum -Average
```

### <span data-ttu-id="82a30-121">Пример 3. измерение текста в текстовом файле</span><span class="sxs-lookup"><span data-stu-id="82a30-121">Example 3: Measure text in a text file</span></span>

<span data-ttu-id="82a30-122">Эта команда отображает количество знаков, слов и строк в файле Text.txt.</span><span class="sxs-lookup"><span data-stu-id="82a30-122">This command displays the number of characters, words, and lines in the Text.txt file.</span></span>
<span data-ttu-id="82a30-123">Без параметра **RAW** `Get-Content` выводит файл в виде массива строк.</span><span class="sxs-lookup"><span data-stu-id="82a30-123">Without the **Raw** parameter, `Get-Content` outputs the file as an array of lines.</span></span>

<span data-ttu-id="82a30-124">Первая команда использует `Set-Content` для добавления текста по умолчанию в файл.</span><span class="sxs-lookup"><span data-stu-id="82a30-124">The first command uses `Set-Content` to add some default text to a file.</span></span>

```powershell
"One", "Two", "Three", "Four" | Set-Content -Path C:\Temp\tmp.txt
Get-Content C:\Temp\tmp.txt | Measure-Object -Character -Line -Word
```

```Output
Lines Words Characters Property
----- ----- ---------- --------
    4     4         15
```

### <span data-ttu-id="82a30-125">Пример 4. Измерение объектов, содержащих указанное свойство</span><span class="sxs-lookup"><span data-stu-id="82a30-125">Example 4: Measure objects containing a specified Property</span></span>

<span data-ttu-id="82a30-126">В этом примере подсчитывается количество объектов со свойством **DisplayName** .</span><span class="sxs-lookup"><span data-stu-id="82a30-126">This example counts the number of objects that have a **DisplayName** property.</span></span> <span data-ttu-id="82a30-127">Первые две команды извлекают все службы и процессы на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="82a30-127">The first two commands retrieve all the services and processes on the local machine.</span></span> <span data-ttu-id="82a30-128">Третья команда подсчитывает общее число служб и процессов.</span><span class="sxs-lookup"><span data-stu-id="82a30-128">The third command counts the combined number of services and processes.</span></span> <span data-ttu-id="82a30-129">Последняя команда объединяет две коллекции и передает результат в `Measure-Object` .</span><span class="sxs-lookup"><span data-stu-id="82a30-129">The last command combines the two collections and pipes the result to `Measure-Object`.</span></span>

<span data-ttu-id="82a30-130">Объект **System. Diagnostics. Process** не имеет свойства **DisplayName** и не является окончательным числом.</span><span class="sxs-lookup"><span data-stu-id="82a30-130">The **System.Diagnostics.Process** object does not have a **DisplayName** property, and is left out of the final count.</span></span>

```powershell
$services = Get-Service
$processes = Get-Process
$services + $processes | Measure-Object
$services + $processes | Measure-Object -Property DisplayName
```

```Output
Count    : 682
Average  :
Sum      :
Maximum  :
Minimum  :
Property :

Count    : 290
Average  :
Sum      :
Maximum  :
Minimum  :
Property : DisplayName
```

### <span data-ttu-id="82a30-131">Пример 5. Измерение содержимого CSV-файла</span><span class="sxs-lookup"><span data-stu-id="82a30-131">Example 5: Measure the contents of a CSV file</span></span>

<span data-ttu-id="82a30-132">Эта команда вычисляет среднее время работы сотрудников в компании.</span><span class="sxs-lookup"><span data-stu-id="82a30-132">This command calculates the average years of service of the employees of a company.</span></span>

<span data-ttu-id="82a30-133">`ServiceYrs.csv`Файл представляет собой CSV-файл, содержащий номер сотрудника и годы обслуживания каждого сотрудника.</span><span class="sxs-lookup"><span data-stu-id="82a30-133">The `ServiceYrs.csv` file is a CSV file that contains the employee number and years of service of each employee.</span></span> <span data-ttu-id="82a30-134">Первая строка в таблице представляет собой строку заголовка **емпно** , **years** .</span><span class="sxs-lookup"><span data-stu-id="82a30-134">The first row in the table is a header row of **EmpNo** , **Years** .</span></span>

<span data-ttu-id="82a30-135">При использовании `Import-Csv` для импорта файла результатом является **PSCustomObject** со свойствами заметок **емпно** и **years** .</span><span class="sxs-lookup"><span data-stu-id="82a30-135">When you use `Import-Csv` to import the file, the result is a **PSCustomObject** with note properties of **EmpNo** and **Years** .</span></span>
<span data-ttu-id="82a30-136">Можно использовать `Measure-Object` для вычисления значений этих свойств, как и для любого другого свойства объекта.</span><span class="sxs-lookup"><span data-stu-id="82a30-136">You can use `Measure-Object` to calculate the values of these properties, just like any other property of an object.</span></span>

```powershell
Import-Csv d:\test\serviceyrs.csv | Measure-Object -Property years -Minimum -Maximum -Average
```

### <span data-ttu-id="82a30-137">Пример 6. Измерение логических значений</span><span class="sxs-lookup"><span data-stu-id="82a30-137">Example 6: Measure Boolean values</span></span>

<span data-ttu-id="82a30-138">В этом примере показано, как `Measure-Object` можно измерять логические значения.</span><span class="sxs-lookup"><span data-stu-id="82a30-138">This example demonstrates how the `Measure-Object` can measure Boolean values.</span></span>
<span data-ttu-id="82a30-139">В этом случае используется **логическое** свойство **PSIsContainer** , которое измеряет совпадение папок (VS. Files) в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="82a30-139">In this case, it uses the **PSIsContainer** **Boolean** property to measure the incidence of folders (vs. files) in the current directory.</span></span>

```powershell
Get-ChildItem | Measure-Object -Property psiscontainer -Maximum -Sum -Minimum -Average
```

```Output
Count             : 126
Average           : 0.0634920634920635
Sum               : 8
Maximum           : 1
Minimum           : 0
StandardDeviation :
Property          : PSIsContainer
```

### <span data-ttu-id="82a30-140">Пример 7. строки мер</span><span class="sxs-lookup"><span data-stu-id="82a30-140">Example 7: Measure strings</span></span>

<span data-ttu-id="82a30-141">В следующем примере измеряется количество строк, сначала одна строка, а затем несколько строк.</span><span class="sxs-lookup"><span data-stu-id="82a30-141">The following example measures the number of lines, first a single string, then across several strings.</span></span> <span data-ttu-id="82a30-142">Символ новой строки <code>\`n</code> разделяет строки на несколько строк.</span><span class="sxs-lookup"><span data-stu-id="82a30-142">The newline character <code>\`n</code> separates strings into multiple lines.</span></span>

```powershell
# The newline character `n separates the string into separate lines, as shown in the output.
"One`nTwo`nThree"
"One`nTwo`nThree" | Measure-Object -Line
```

```Output
One
Two
Three


Lines Words Characters Property
----- ----- ---------- --------
    3
```

```powershell
# The first string counts as a single line.
# The second string is separated into two lines by the newline character.
"One", "Two`nThree" | Measure-Object -Line
```

```Output
Lines Words Characters Property
----- ----- ---------- --------
    3
```

```powershell
# The Word switch counts the number of words in each InputObject
# Each InputObject is treated as a single line.
"One, Two", "Three", "Four Five" | Measure-Object -Word -Line
```

```Output
Lines Words Characters Property
----- ----- ---------- --------
    3     5
```

### <span data-ttu-id="82a30-143">Пример 8. Измерение всех значений</span><span class="sxs-lookup"><span data-stu-id="82a30-143">Example 8: Measure all the values</span></span>

<span data-ttu-id="82a30-144">Начиная с PowerShell 6, параметр **аллстатс** параметра `Measure-Object` позволяет измерять всю статистику вместе.</span><span class="sxs-lookup"><span data-stu-id="82a30-144">Beginning in PowerShell 6, the **AllStats** parameter of `Measure-Object` allows you to measure all the statistics together.</span></span>

```powershell
1..5 | Measure-Object -AllStats
```

```output
Count             : 5
Average           : 3
Sum               : 15
Maximum           : 5
Minimum           : 1
StandardDeviation : 1.58113883008419
Property          :
```

### <span data-ttu-id="82a30-145">Пример 9. мера с использованием свойств ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="82a30-145">Example 9: Measure using scriptblock properties</span></span>

<span data-ttu-id="82a30-146">Начиная с PowerShell 6, `Measure-Object` поддерживает свойства **ScriptBlock** .</span><span class="sxs-lookup"><span data-stu-id="82a30-146">Beginning in PowerShell 6, `Measure-Object` supports **ScriptBlock** properties.</span></span> <span data-ttu-id="82a30-147">В следующем примере показано, как использовать свойство **ScriptBlock** для определения размера всех файлов в каталоге (в мегабайтах).</span><span class="sxs-lookup"><span data-stu-id="82a30-147">The following example demonstrates how to use a **ScriptBlock** property to determine the size, in MegaBytes, of all the files in a directory.</span></span>

```powershell
Get-ChildItem | Measure-Object -Sum {$_.Length/1MB}
```

### <span data-ttu-id="82a30-148">Пример 10. хэш-таблицы мер</span><span class="sxs-lookup"><span data-stu-id="82a30-148">Example 10: Measure hashtables</span></span>

<span data-ttu-id="82a30-149">Начиная с PowerShell 6, `Measure-Object` поддерживает измерение входных **хэш-таблиц** .</span><span class="sxs-lookup"><span data-stu-id="82a30-149">Beginning in PowerShell 6, `Measure-Object` supports measurement of **hashtable** input.</span></span> <span data-ttu-id="82a30-150">В следующем примере определяется максимальное значение `num` ключа из трех объектов **Hashtable** .</span><span class="sxs-lookup"><span data-stu-id="82a30-150">The following example determines the largest value for the `num` key of 3 **hashtable** objects.</span></span>

```powershell
@{num=3}, @{num=4}, @{num=5} | Measure-Object -Maximum Num
```

```output
Count             : 3
Average           :
Sum               :
Maximum           : 5
Minimum           :
StandardDeviation :
Property          : num
```

### <span data-ttu-id="82a30-151">Пример 11. измерение стандартного отклонения</span><span class="sxs-lookup"><span data-stu-id="82a30-151">Example 11: Measure the Standard Deviation</span></span>

<span data-ttu-id="82a30-152">Начиная с PowerShell 6, `Measure-Object` поддерживает `-StandardDeviation` параметр.</span><span class="sxs-lookup"><span data-stu-id="82a30-152">Beginning in PowerShell 6, `Measure-Object` supports the `-StandardDeviation` parameter.</span></span> <span data-ttu-id="82a30-153">В следующем примере определяется *стандартное отклонение* для ЦП, используемого всеми процессами.</span><span class="sxs-lookup"><span data-stu-id="82a30-153">The following example determines the *standard deviation* for the CPU used by all processes.</span></span> <span data-ttu-id="82a30-154">Большое отклонение указывает на небольшое количество процессов, которые потребляют больше всего ресурсов ЦП.</span><span class="sxs-lookup"><span data-stu-id="82a30-154">A large deviation would indicate a small number of processes consuming the most CPU.</span></span>

```powershell
Get-Process | Measure-Object -Average -StandardDeviation CPU
```

```output
Count             : 303
Average           : 163.032384488449
Sum               :
Maximum           :
Minimum           :
StandardDeviation : 859.444048419069
Property          : CPU
```

### <span data-ttu-id="82a30-155">Пример 12. мера с использованием подстановочных знаков</span><span class="sxs-lookup"><span data-stu-id="82a30-155">Example 12: Measure using wildcards</span></span>

<span data-ttu-id="82a30-156">Начиная с PowerShell 6, `Measure-Object` поддерживает измерение объектов с помощью подстановочных знаков в именах свойств.</span><span class="sxs-lookup"><span data-stu-id="82a30-156">Beginning in PowerShell 6, `Measure-Object` supports measurement of objects by using wildcards in property names.</span></span> <span data-ttu-id="82a30-157">В приведенном ниже примере определяется максимальное использование страничной памяти любого типа в наборе процессов.</span><span class="sxs-lookup"><span data-stu-id="82a30-157">The following example determines the maximum of any type of paged memory usage among a set of processes.</span></span>

```powershell
Get-Process | Measure-Object -Maximum *paged*memory*size
```

```output
Count             : 303
Average           :
Sum               :
Maximum           : 735784
Minimum           :
StandardDeviation :
Property          : NonpagedSystemMemorySize

Count             : 303
Average           :
Sum               :
Maximum           : 352104448
Minimum           :
StandardDeviation :
Property          : PagedMemorySize

Count             : 303
Average           :
Sum               :
Maximum           : 2201968
Minimum           :
StandardDeviation :
Property          : PagedSystemMemorySize

Count             : 303
Average           :
Sum               :
Maximum           : 719032320
Minimum           :
StandardDeviation :
Property          : PeakPagedMemorySize
```

## <span data-ttu-id="82a30-158">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="82a30-158">PARAMETERS</span></span>

### <span data-ttu-id="82a30-159">— Среднее значение</span><span class="sxs-lookup"><span data-stu-id="82a30-159">-Average</span></span>

<span data-ttu-id="82a30-160">Указывает, что командлет отображает среднее значение указанных свойств.</span><span class="sxs-lookup"><span data-stu-id="82a30-160">Indicates that the cmdlet displays the average value of the specified properties.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GenericMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="82a30-161">— Символ</span><span class="sxs-lookup"><span data-stu-id="82a30-161">-Character</span></span>

<span data-ttu-id="82a30-162">Указывает, что командлет подсчитывает количество символов во входных объектах.</span><span class="sxs-lookup"><span data-stu-id="82a30-162">Indicates that the cmdlet counts the number of characters in the input objects.</span></span>

> [!NOTE]
> <span data-ttu-id="82a30-163">**Слова** , **char** и **line** переключаются *внутри* каждого входного объекта, а также *во* входных объектах.</span><span class="sxs-lookup"><span data-stu-id="82a30-163">The **Word** , **Char** and **Line** switches count *inside* each input object, as well as *across* input objects.</span></span> <span data-ttu-id="82a30-164">См. Пример 7.</span><span class="sxs-lookup"><span data-stu-id="82a30-164">See Example 7.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TextMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="82a30-165">-Игноревхитеспаце</span><span class="sxs-lookup"><span data-stu-id="82a30-165">-IgnoreWhiteSpace</span></span>

<span data-ttu-id="82a30-166">Указывает, что командлет игнорирует пробелы в количестве символов.</span><span class="sxs-lookup"><span data-stu-id="82a30-166">Indicates that the cmdlet ignores white space in character counts.</span></span>
<span data-ttu-id="82a30-167">По умолчанию пробелы учитываются.</span><span class="sxs-lookup"><span data-stu-id="82a30-167">By default, white space is not ignored.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TextMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="82a30-168">-InputObject</span><span class="sxs-lookup"><span data-stu-id="82a30-168">-InputObject</span></span>

<span data-ttu-id="82a30-169">Указывает, какие объекты нужно измерять.</span><span class="sxs-lookup"><span data-stu-id="82a30-169">Specifies the objects to be measured.</span></span>
<span data-ttu-id="82a30-170">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="82a30-170">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

<span data-ttu-id="82a30-171">При использовании параметра **InputObject** с параметром `Measure-Object` , а не с результатами команды трубопроводов в `Measure-Object` значение **InputObject** рассматривается как один объект.</span><span class="sxs-lookup"><span data-stu-id="82a30-171">When you use the **InputObject** parameter with `Measure-Object`, instead of piping command results to `Measure-Object`, the **InputObject** value is treated as a single object.</span></span>

<span data-ttu-id="82a30-172">Рекомендуется использовать `Measure-Object` в конвейере, если необходимо измерять коллекцию объектов в зависимости от того, имеют ли объекты определенные значения в определенных свойствах.</span><span class="sxs-lookup"><span data-stu-id="82a30-172">It is recommended that you use `Measure-Object` in the pipeline if you want to measure a collection of objects based on whether the objects have specific values in defined properties.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="82a30-173">-Line</span><span class="sxs-lookup"><span data-stu-id="82a30-173">-Line</span></span>

<span data-ttu-id="82a30-174">Указывает, что командлет подсчитывает количество строк во входных объектах.</span><span class="sxs-lookup"><span data-stu-id="82a30-174">Indicates that the cmdlet counts the number of lines in the input objects.</span></span>

> [!NOTE]
> <span data-ttu-id="82a30-175">**Слова** , **char** и **line** переключаются *внутри* каждого входного объекта, а также *во* входных объектах.</span><span class="sxs-lookup"><span data-stu-id="82a30-175">The **Word** , **Char** and **Line** switches count *inside* each input object, as well as *across* input objects.</span></span> <span data-ttu-id="82a30-176">См. Пример 7.</span><span class="sxs-lookup"><span data-stu-id="82a30-176">See Example 7.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TextMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="82a30-177">— Максимум</span><span class="sxs-lookup"><span data-stu-id="82a30-177">-Maximum</span></span>

<span data-ttu-id="82a30-178">Указывает, что командлет отображает максимальное значение указанных свойств.</span><span class="sxs-lookup"><span data-stu-id="82a30-178">Indicates that the cmdlet displays the maximum value of the specified properties.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GenericMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="82a30-179">— Минимум</span><span class="sxs-lookup"><span data-stu-id="82a30-179">-Minimum</span></span>

<span data-ttu-id="82a30-180">Указывает, что командлет отображает минимальное значение указанных свойств.</span><span class="sxs-lookup"><span data-stu-id="82a30-180">Indicates that the cmdlet displays the minimum value of the specified properties.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GenericMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="82a30-181">-Property</span><span class="sxs-lookup"><span data-stu-id="82a30-181">-Property</span></span>

<span data-ttu-id="82a30-182">Указывает одно или несколько свойств для измерения.</span><span class="sxs-lookup"><span data-stu-id="82a30-182">Specifies one or more properties to measure.</span></span> <span data-ttu-id="82a30-183">Если не указать другие меры, `Measure-Object` подсчитывает количество объектов, которые имеют указанные свойства.</span><span class="sxs-lookup"><span data-stu-id="82a30-183">If you do not specify any other measures, `Measure-Object` counts the objects that have the properties you specify.</span></span>

<span data-ttu-id="82a30-184">Значением параметра **Property** может быть новое вычисляемое свойство.</span><span class="sxs-lookup"><span data-stu-id="82a30-184">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="82a30-185">Вычисляемое свойство должно быть блоком скрипта.</span><span class="sxs-lookup"><span data-stu-id="82a30-185">The calculated property must be a script block.</span></span> <span data-ttu-id="82a30-186">Дополнительные сведения см. в разделе [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="82a30-186">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.PSPropertyExpression[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="82a30-187">-Стандартное отклонение</span><span class="sxs-lookup"><span data-stu-id="82a30-187">-StandardDeviation</span></span>

<span data-ttu-id="82a30-188">Указывает, что командлет отображает стандартное отклонение значений указанных свойств.</span><span class="sxs-lookup"><span data-stu-id="82a30-188">Indicates that the cmdlet displays the standard deviation of the values of the specified properties.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GenericMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="82a30-189">-Sum</span><span class="sxs-lookup"><span data-stu-id="82a30-189">-Sum</span></span>

<span data-ttu-id="82a30-190">Указывает, что командлет отображает сумму значений указанных свойств.</span><span class="sxs-lookup"><span data-stu-id="82a30-190">Indicates that the cmdlet displays the sum of the values of the specified properties.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GenericMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="82a30-191">-Аллстатс</span><span class="sxs-lookup"><span data-stu-id="82a30-191">-AllStats</span></span>

<span data-ttu-id="82a30-192">Указывает, что командлет отображает всю статистику указанных свойств.</span><span class="sxs-lookup"><span data-stu-id="82a30-192">Indicates that the cmdlet displays all the statistics of the specified properties.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GenericMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="82a30-193">-Слово</span><span class="sxs-lookup"><span data-stu-id="82a30-193">-Word</span></span>

<span data-ttu-id="82a30-194">Указывает, что командлет подсчитывает количество слов во входных объектах.</span><span class="sxs-lookup"><span data-stu-id="82a30-194">Indicates that the cmdlet counts the number of words in the input objects.</span></span>

> [!NOTE]
> <span data-ttu-id="82a30-195">**Слова** , **char** и **line** переключаются *внутри* каждого входного объекта, а также *во* входных объектах.</span><span class="sxs-lookup"><span data-stu-id="82a30-195">The **Word** , **Char** and **Line** switches count *inside* each input object, as well as *across* input objects.</span></span> <span data-ttu-id="82a30-196">См. Пример 7.</span><span class="sxs-lookup"><span data-stu-id="82a30-196">See Example 7.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: TextMeasure
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="82a30-197">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="82a30-197">CommonParameters</span></span>

<span data-ttu-id="82a30-198">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="82a30-198">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="82a30-199">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="82a30-199">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="82a30-200">Входные данные</span><span class="sxs-lookup"><span data-stu-id="82a30-200">INPUTS</span></span>

### <span data-ttu-id="82a30-201">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="82a30-201">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="82a30-202">Вы можете передать объекты в `Measure-Object` .</span><span class="sxs-lookup"><span data-stu-id="82a30-202">You can pipe objects to `Measure-Object`.</span></span>

## <span data-ttu-id="82a30-203">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="82a30-203">OUTPUTS</span></span>

### <span data-ttu-id="82a30-204">Microsoft. PowerShell. Commands. Женерикмеасуреинфо</span><span class="sxs-lookup"><span data-stu-id="82a30-204">Microsoft.PowerShell.Commands.GenericMeasureInfo</span></span>

### <span data-ttu-id="82a30-205">Microsoft. PowerShell. Commands. Текстмеасуреинфо</span><span class="sxs-lookup"><span data-stu-id="82a30-205">Microsoft.PowerShell.Commands.TextMeasureInfo</span></span>

<span data-ttu-id="82a30-206">При использовании параметра **Word** `Measure-Object` возвращает объект **текстмеасуреинфо** .</span><span class="sxs-lookup"><span data-stu-id="82a30-206">If you use the **Word** parameter, `Measure-Object` returns a **TextMeasureInfo** object.</span></span>
<span data-ttu-id="82a30-207">В противном случае возвращается объект **женерикмеасуреинфо** .</span><span class="sxs-lookup"><span data-stu-id="82a30-207">Otherwise, it returns a **GenericMeasureInfo** object.</span></span>

## <span data-ttu-id="82a30-208">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="82a30-208">NOTES</span></span>

## <span data-ttu-id="82a30-209">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="82a30-209">RELATED LINKS</span></span>

[<span data-ttu-id="82a30-210">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="82a30-210">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="82a30-211">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="82a30-211">Compare-Object</span></span>](Compare-Object.md)

[<span data-ttu-id="82a30-212">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="82a30-212">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="82a30-213">Group-Object</span><span class="sxs-lookup"><span data-stu-id="82a30-213">Group-Object</span></span>](Group-Object.md)

[<span data-ttu-id="82a30-214">New-Object</span><span class="sxs-lookup"><span data-stu-id="82a30-214">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="82a30-215">Select-Object</span><span class="sxs-lookup"><span data-stu-id="82a30-215">Select-Object</span></span>](Select-Object.md)

[<span data-ttu-id="82a30-216">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="82a30-216">Sort-Object</span></span>](Sort-Object.md)

[<span data-ttu-id="82a30-217">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="82a30-217">Tee-Object</span></span>](Tee-Object.md)

[<span data-ttu-id="82a30-218">Where-Object</span><span class="sxs-lookup"><span data-stu-id="82a30-218">Where-Object</span></span>](../Microsoft.PowerShell.Core/Where-Object.md)