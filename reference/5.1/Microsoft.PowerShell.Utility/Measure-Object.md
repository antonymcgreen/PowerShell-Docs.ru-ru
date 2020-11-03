---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 5/10/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/measure-object?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Measure-Object;
ms.openlocfilehash: 5d4a27f1a1949056ca63b9b6a2340bf1226592e0
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2020
ms.locfileid: "93230273"
---
# <span data-ttu-id="41054-103">Measure-Object;</span><span class="sxs-lookup"><span data-stu-id="41054-103">Measure-Object</span></span>

## <span data-ttu-id="41054-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="41054-104">SYNOPSIS</span></span>
<span data-ttu-id="41054-105">Рассчитывает числовые свойства объектов, а также количество знаков, слов и строк в строковых объектах, например в текстовых файлах.</span><span class="sxs-lookup"><span data-stu-id="41054-105">Calculates the numeric properties of objects, and the characters, words, and lines in string objects, such as files of text.</span></span>

## <span data-ttu-id="41054-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="41054-106">SYNTAX</span></span>

### <span data-ttu-id="41054-107">Женерикмеасуре (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="41054-107">GenericMeasure (Default)</span></span>

```
Measure-Object [-InputObject <PSObject>] [[-Property] <String[]>] [-Sum] [-Average] [-Maximum] [-Minimum]
 [<CommonParameters>]
```

### <span data-ttu-id="41054-108">текстмеасуре</span><span class="sxs-lookup"><span data-stu-id="41054-108">TextMeasure</span></span>

```
Measure-Object [-InputObject <PSObject>] [[-Property] <String[]>] [-Line] [-Word] [-Character]
 [-IgnoreWhiteSpace] [<CommonParameters>]
```

## <span data-ttu-id="41054-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="41054-109">DESCRIPTION</span></span>

<span data-ttu-id="41054-110">`Measure-Object`Командлет вычисляет значения свойств определенных типов объектов.</span><span class="sxs-lookup"><span data-stu-id="41054-110">The `Measure-Object` cmdlet calculates the property values of certain types of object.</span></span>
<span data-ttu-id="41054-111">`Measure-Object` выполняет три типа измерений в зависимости от параметров в команде.</span><span class="sxs-lookup"><span data-stu-id="41054-111">`Measure-Object` performs three types of measurements, depending on the parameters in the command.</span></span>

<span data-ttu-id="41054-112">`Measure-Object`Командлет выполняет вычисления со значениями свойств объектов.</span><span class="sxs-lookup"><span data-stu-id="41054-112">The `Measure-Object` cmdlet performs calculations on the property values of objects.</span></span> <span data-ttu-id="41054-113">Можно использовать `Measure-Object` для подсчета объектов или количества объектов с указанным **свойством** .</span><span class="sxs-lookup"><span data-stu-id="41054-113">You can use `Measure-Object` to count objects or count objects with a specified **Property** .</span></span> <span data-ttu-id="41054-114">Можно также использовать `Measure-Object` для вычисления **минимального** , **максимального** , **итогового** , **стандартное отклонение** и **среднего** значения числовых значений.</span><span class="sxs-lookup"><span data-stu-id="41054-114">You can also use `Measure-Object` to calculate the **Minimum** , **Maximum** , **Sum** , **StandardDeviation** and **Average** of numeric values.</span></span> <span data-ttu-id="41054-115">Для **строковых** объектов можно также использовать `Measure-Object` для подсчета количества строк, слов и символов.</span><span class="sxs-lookup"><span data-stu-id="41054-115">For **String** objects, you can also use `Measure-Object` to count the number of lines, words, and characters.</span></span>

## <span data-ttu-id="41054-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="41054-116">EXAMPLES</span></span>

### <span data-ttu-id="41054-117">Пример 1. подсчет файлов и папок в каталоге</span><span class="sxs-lookup"><span data-stu-id="41054-117">Example 1: Count the files and folders in a directory</span></span>

<span data-ttu-id="41054-118">Эта команда определяет количество файлов и папок в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="41054-118">This command counts the files and folders in the current directory.</span></span>

```powershell
Get-ChildItem | Measure-Object
```

### <span data-ttu-id="41054-119">Пример 2. Измерение файлов в каталоге</span><span class="sxs-lookup"><span data-stu-id="41054-119">Example 2: Measure the files in a directory</span></span>

<span data-ttu-id="41054-120">Эта команда отображает **минимальные** , **максимальные** и **суммарные** размеры всех файлов в текущем каталоге, а также средний размер файла в каталоге.</span><span class="sxs-lookup"><span data-stu-id="41054-120">This command displays the **Minimum** , **Maximum** , and **Sum** of the sizes of all files in the current directory, and the average size of a file in the directory.</span></span>

```powershell
Get-ChildItem | Measure-Object -Property length -Minimum -Maximum -Average
```

### <span data-ttu-id="41054-121">Пример 3. измерение текста в текстовом файле</span><span class="sxs-lookup"><span data-stu-id="41054-121">Example 3: Measure text in a text file</span></span>

<span data-ttu-id="41054-122">Эта команда отображает количество знаков, слов и строк в файле Text.txt.</span><span class="sxs-lookup"><span data-stu-id="41054-122">This command displays the number of characters, words, and lines in the Text.txt file.</span></span>
<span data-ttu-id="41054-123">Без параметра **RAW** `Get-Content` выводит файл в виде массива строк.</span><span class="sxs-lookup"><span data-stu-id="41054-123">Without the **Raw** parameter, `Get-Content` outputs the file as an array of lines.</span></span>

<span data-ttu-id="41054-124">Первая команда использует `Set-Content` для добавления текста по умолчанию в файл.</span><span class="sxs-lookup"><span data-stu-id="41054-124">The first command uses `Set-Content` to add some default text to a file.</span></span>

```powershell
"One", "Two", "Three", "Four" | Set-Content -Path C:\Temp\tmp.txt
Get-Content C:\Temp\tmp.txt | Measure-Object -Character -Line -Word
```

```Output
Lines Words Characters Property
----- ----- ---------- --------
    4     4         15
```

### <span data-ttu-id="41054-125">Пример 4. Измерение объектов, содержащих указанное свойство</span><span class="sxs-lookup"><span data-stu-id="41054-125">Example 4: Measure objects containing a specified Property</span></span>

<span data-ttu-id="41054-126">В этом примере подсчитывается количество объектов со свойством **DisplayName** .</span><span class="sxs-lookup"><span data-stu-id="41054-126">This example counts the number of objects that have a **DisplayName** property.</span></span> <span data-ttu-id="41054-127">Первые две команды извлекают все службы и процессы на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="41054-127">The first two commands retrieve all the services and processes on the local machine.</span></span> <span data-ttu-id="41054-128">Третья команда подсчитывает общее число служб и процессов.</span><span class="sxs-lookup"><span data-stu-id="41054-128">The third command counts the combined number of services and processes.</span></span> <span data-ttu-id="41054-129">Последняя команда объединяет две коллекции и передает результат в `Measure-Object` .</span><span class="sxs-lookup"><span data-stu-id="41054-129">The last command combines the two collections and pipes the result to `Measure-Object`.</span></span>

<span data-ttu-id="41054-130">Объект **System. Diagnostics. Process** не имеет свойства **DisplayName** и не является окончательным числом.</span><span class="sxs-lookup"><span data-stu-id="41054-130">The **System.Diagnostics.Process** object does not have a **DisplayName** property, and is left out of the final count.</span></span>

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

### <span data-ttu-id="41054-131">Пример 5. Измерение содержимого CSV-файла</span><span class="sxs-lookup"><span data-stu-id="41054-131">Example 5: Measure the contents of a CSV file</span></span>

<span data-ttu-id="41054-132">Эта команда вычисляет среднее время работы сотрудников в компании.</span><span class="sxs-lookup"><span data-stu-id="41054-132">This command calculates the average years of service of the employees of a company.</span></span>

<span data-ttu-id="41054-133">`ServiceYrs.csv`Файл представляет собой CSV-файл, содержащий номер сотрудника и годы обслуживания каждого сотрудника.</span><span class="sxs-lookup"><span data-stu-id="41054-133">The `ServiceYrs.csv` file is a CSV file that contains the employee number and years of service of each employee.</span></span> <span data-ttu-id="41054-134">Первая строка в таблице представляет собой строку заголовка **емпно** , **years** .</span><span class="sxs-lookup"><span data-stu-id="41054-134">The first row in the table is a header row of **EmpNo** , **Years** .</span></span>

<span data-ttu-id="41054-135">При использовании `Import-Csv` для импорта файла результатом является **PSCustomObject** со свойствами заметок **емпно** и **years** .</span><span class="sxs-lookup"><span data-stu-id="41054-135">When you use `Import-Csv` to import the file, the result is a **PSCustomObject** with note properties of **EmpNo** and **Years** .</span></span>
<span data-ttu-id="41054-136">Можно использовать `Measure-Object` для вычисления значений этих свойств, как и для любого другого свойства объекта.</span><span class="sxs-lookup"><span data-stu-id="41054-136">You can use `Measure-Object` to calculate the values of these properties, just like any other property of an object.</span></span>

```powershell
Import-Csv d:\test\serviceyrs.csv | Measure-Object -Property years -Minimum -Maximum -Average
```

### <span data-ttu-id="41054-137">Пример 6. Измерение логических значений</span><span class="sxs-lookup"><span data-stu-id="41054-137">Example 6: Measure Boolean values</span></span>

<span data-ttu-id="41054-138">В этом примере показано, как `Measure-Object` можно измерять логические значения.</span><span class="sxs-lookup"><span data-stu-id="41054-138">This example demonstrates how the `Measure-Object` can measure Boolean values.</span></span>
<span data-ttu-id="41054-139">В этом случае используется **логическое** свойство **PSIsContainer** , которое измеряет совпадение папок (VS. Files) в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="41054-139">In this case, it uses the **PSIsContainer** **Boolean** property to measure the incidence of folders (vs. files) in the current directory.</span></span>

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

### <span data-ttu-id="41054-140">Пример 7. строки мер</span><span class="sxs-lookup"><span data-stu-id="41054-140">Example 7: Measure strings</span></span>

<span data-ttu-id="41054-141">В следующем примере измеряется количество строк, сначала одна строка, а затем несколько строк.</span><span class="sxs-lookup"><span data-stu-id="41054-141">The following example measures the number of lines, first a single string, then across several strings.</span></span> <span data-ttu-id="41054-142">Символ новой строки <code>\`n</code> разделяет строки на несколько строк.</span><span class="sxs-lookup"><span data-stu-id="41054-142">The newline character <code>\`n</code> separates strings into multiple lines.</span></span>

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

## <span data-ttu-id="41054-143">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="41054-143">PARAMETERS</span></span>

### <span data-ttu-id="41054-144">— Среднее значение</span><span class="sxs-lookup"><span data-stu-id="41054-144">-Average</span></span>

<span data-ttu-id="41054-145">Указывает, что командлет отображает среднее значение указанных свойств.</span><span class="sxs-lookup"><span data-stu-id="41054-145">Indicates that the cmdlet displays the average value of the specified properties.</span></span>

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

### <span data-ttu-id="41054-146">— Символ</span><span class="sxs-lookup"><span data-stu-id="41054-146">-Character</span></span>

<span data-ttu-id="41054-147">Указывает, что командлет подсчитывает количество символов во входных объектах.</span><span class="sxs-lookup"><span data-stu-id="41054-147">Indicates that the cmdlet counts the number of characters in the input objects.</span></span>

> [!NOTE]
> <span data-ttu-id="41054-148">**Слова** , **char** и **line** переключаются *внутри* каждого входного объекта, а также *во* входных объектах.</span><span class="sxs-lookup"><span data-stu-id="41054-148">The **Word** , **Char** and **Line** switches count *inside* each input object, as well as *across* input objects.</span></span> <span data-ttu-id="41054-149">См. Пример 7.</span><span class="sxs-lookup"><span data-stu-id="41054-149">See Example 7.</span></span>

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

### <span data-ttu-id="41054-150">-Игноревхитеспаце</span><span class="sxs-lookup"><span data-stu-id="41054-150">-IgnoreWhiteSpace</span></span>

<span data-ttu-id="41054-151">Указывает, что командлет игнорирует пробелы в количестве символов.</span><span class="sxs-lookup"><span data-stu-id="41054-151">Indicates that the cmdlet ignores white space in character counts.</span></span>
<span data-ttu-id="41054-152">По умолчанию пробелы учитываются.</span><span class="sxs-lookup"><span data-stu-id="41054-152">By default, white space is not ignored.</span></span>

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

### <span data-ttu-id="41054-153">-InputObject</span><span class="sxs-lookup"><span data-stu-id="41054-153">-InputObject</span></span>

<span data-ttu-id="41054-154">Указывает, какие объекты нужно измерять.</span><span class="sxs-lookup"><span data-stu-id="41054-154">Specifies the objects to be measured.</span></span>
<span data-ttu-id="41054-155">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="41054-155">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

<span data-ttu-id="41054-156">При использовании параметра **InputObject** с параметром `Measure-Object` , а не с результатами команды трубопроводов в `Measure-Object` значение **InputObject** рассматривается как один объект.</span><span class="sxs-lookup"><span data-stu-id="41054-156">When you use the **InputObject** parameter with `Measure-Object`, instead of piping command results to `Measure-Object`, the **InputObject** value is treated as a single object.</span></span>

<span data-ttu-id="41054-157">Рекомендуется использовать `Measure-Object` в конвейере, если необходимо измерять коллекцию объектов в зависимости от того, имеют ли объекты определенные значения в определенных свойствах.</span><span class="sxs-lookup"><span data-stu-id="41054-157">It is recommended that you use `Measure-Object` in the pipeline if you want to measure a collection of objects based on whether the objects have specific values in defined properties.</span></span>

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

### <span data-ttu-id="41054-158">-Line</span><span class="sxs-lookup"><span data-stu-id="41054-158">-Line</span></span>

<span data-ttu-id="41054-159">Указывает, что командлет подсчитывает количество строк во входных объектах.</span><span class="sxs-lookup"><span data-stu-id="41054-159">Indicates that the cmdlet counts the number of lines in the input objects.</span></span>

> [!NOTE]
> <span data-ttu-id="41054-160">**Слова** , **char** и **line** переключаются *внутри* каждого входного объекта, а также *во* входных объектах.</span><span class="sxs-lookup"><span data-stu-id="41054-160">The **Word** , **Char** and **Line** switches count *inside* each input object, as well as *across* input objects.</span></span> <span data-ttu-id="41054-161">См. Пример 7.</span><span class="sxs-lookup"><span data-stu-id="41054-161">See Example 7.</span></span>

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

### <span data-ttu-id="41054-162">— Максимум</span><span class="sxs-lookup"><span data-stu-id="41054-162">-Maximum</span></span>

<span data-ttu-id="41054-163">Указывает, что командлет отображает максимальное значение указанных свойств.</span><span class="sxs-lookup"><span data-stu-id="41054-163">Indicates that the cmdlet displays the maximum value of the specified properties.</span></span>

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

### <span data-ttu-id="41054-164">— Минимум</span><span class="sxs-lookup"><span data-stu-id="41054-164">-Minimum</span></span>

<span data-ttu-id="41054-165">Указывает, что командлет отображает минимальное значение указанных свойств.</span><span class="sxs-lookup"><span data-stu-id="41054-165">Indicates that the cmdlet displays the minimum value of the specified properties.</span></span>

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

### <span data-ttu-id="41054-166">-Property</span><span class="sxs-lookup"><span data-stu-id="41054-166">-Property</span></span>

<span data-ttu-id="41054-167">Указывает одно или несколько свойств для измерения.</span><span class="sxs-lookup"><span data-stu-id="41054-167">Specifies one or more properties to measure.</span></span> <span data-ttu-id="41054-168">Если не указать другие меры, `Measure-Object` подсчитывает количество объектов, которые имеют указанные свойства.</span><span class="sxs-lookup"><span data-stu-id="41054-168">If you do not specify any other measures, `Measure-Object` counts the objects that have the properties you specify.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="41054-169">-Sum</span><span class="sxs-lookup"><span data-stu-id="41054-169">-Sum</span></span>

<span data-ttu-id="41054-170">Указывает, что командлет отображает сумму значений указанных свойств.</span><span class="sxs-lookup"><span data-stu-id="41054-170">Indicates that the cmdlet displays the sum of the values of the specified properties.</span></span>

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

### <span data-ttu-id="41054-171">-Слово</span><span class="sxs-lookup"><span data-stu-id="41054-171">-Word</span></span>

<span data-ttu-id="41054-172">Указывает, что командлет подсчитывает количество слов во входных объектах.</span><span class="sxs-lookup"><span data-stu-id="41054-172">Indicates that the cmdlet counts the number of words in the input objects.</span></span>

> [!NOTE]
> <span data-ttu-id="41054-173">**Слова** , **char** и **line** переключаются *внутри* каждого входного объекта, а также *во* входных объектах.</span><span class="sxs-lookup"><span data-stu-id="41054-173">The **Word** , **Char** and **Line** switches count *inside* each input object, as well as *across* input objects.</span></span> <span data-ttu-id="41054-174">См. Пример 7.</span><span class="sxs-lookup"><span data-stu-id="41054-174">See Example 7.</span></span>

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

### <span data-ttu-id="41054-175">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="41054-175">CommonParameters</span></span>

<span data-ttu-id="41054-176">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="41054-176">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="41054-177">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="41054-177">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="41054-178">Входные данные</span><span class="sxs-lookup"><span data-stu-id="41054-178">INPUTS</span></span>

### <span data-ttu-id="41054-179">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="41054-179">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="41054-180">Вы можете передать объекты в `Measure-Object` .</span><span class="sxs-lookup"><span data-stu-id="41054-180">You can pipe objects to `Measure-Object`.</span></span>

## <span data-ttu-id="41054-181">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="41054-181">OUTPUTS</span></span>

### <span data-ttu-id="41054-182">Microsoft. PowerShell. Commands. Женерикмеасуреинфо</span><span class="sxs-lookup"><span data-stu-id="41054-182">Microsoft.PowerShell.Commands.GenericMeasureInfo</span></span>

### <span data-ttu-id="41054-183">Microsoft. PowerShell. Commands. Текстмеасуреинфо</span><span class="sxs-lookup"><span data-stu-id="41054-183">Microsoft.PowerShell.Commands.TextMeasureInfo</span></span>

<span data-ttu-id="41054-184">При использовании параметра **Word** `Measure-Object` возвращает объект **текстмеасуреинфо** .</span><span class="sxs-lookup"><span data-stu-id="41054-184">If you use the **Word** parameter, `Measure-Object` returns a **TextMeasureInfo** object.</span></span>
<span data-ttu-id="41054-185">В противном случае возвращается объект **женерикмеасуреинфо** .</span><span class="sxs-lookup"><span data-stu-id="41054-185">Otherwise, it returns a **GenericMeasureInfo** object.</span></span>

## <span data-ttu-id="41054-186">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="41054-186">NOTES</span></span>

## <span data-ttu-id="41054-187">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="41054-187">RELATED LINKS</span></span>

[<span data-ttu-id="41054-188">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="41054-188">Compare-Object</span></span>](Compare-Object.md)

[<span data-ttu-id="41054-189">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="41054-189">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="41054-190">Group-Object</span><span class="sxs-lookup"><span data-stu-id="41054-190">Group-Object</span></span>](Group-Object.md)

[<span data-ttu-id="41054-191">New-Object</span><span class="sxs-lookup"><span data-stu-id="41054-191">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="41054-192">Select-Object</span><span class="sxs-lookup"><span data-stu-id="41054-192">Select-Object</span></span>](Select-Object.md)

[<span data-ttu-id="41054-193">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="41054-193">Sort-Object</span></span>](Sort-Object.md)

[<span data-ttu-id="41054-194">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="41054-194">Tee-Object</span></span>](Tee-Object.md)

[<span data-ttu-id="41054-195">Where-Object</span><span class="sxs-lookup"><span data-stu-id="41054-195">Where-Object</span></span>](../Microsoft.PowerShell.Core/Where-Object.md)
