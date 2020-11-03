---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-unique?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Unique
ms.openlocfilehash: 15a3905359a14b26dc98ad7462cc40420e111981
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93225633"
---
# <span data-ttu-id="af02a-103">Get-Unique</span><span class="sxs-lookup"><span data-stu-id="af02a-103">Get-Unique</span></span>

## <span data-ttu-id="af02a-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="af02a-104">SYNOPSIS</span></span>
<span data-ttu-id="af02a-105">Возвращает уникальные элементы из сортированного списка.</span><span class="sxs-lookup"><span data-stu-id="af02a-105">Returns unique items from a sorted list.</span></span>

## <span data-ttu-id="af02a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="af02a-106">SYNTAX</span></span>

### <span data-ttu-id="af02a-107">AsString (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="af02a-107">AsString (Default)</span></span>

```
Get-Unique [-InputObject <PSObject>] [-AsString] [<CommonParameters>]
```

### <span data-ttu-id="af02a-108">уникуебитипе</span><span class="sxs-lookup"><span data-stu-id="af02a-108">UniqueByType</span></span>

```
Get-Unique [-InputObject <PSObject>] [-OnType] [<CommonParameters>]
```

## <span data-ttu-id="af02a-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="af02a-109">DESCRIPTION</span></span>

<span data-ttu-id="af02a-110">`Get-Unique`Командлет сравнивает каждый элемент отсортированного списка со следующим элементом, удаляет дубликаты и возвращает только один экземпляр каждого элемента.</span><span class="sxs-lookup"><span data-stu-id="af02a-110">The `Get-Unique` cmdlet compares each item in a sorted list to the next item, eliminates duplicates, and returns only one instance of each item.</span></span> <span data-ttu-id="af02a-111">Чтобы командлет работал правильно, список должен быть отсортирован.</span><span class="sxs-lookup"><span data-stu-id="af02a-111">The list must be sorted for the cmdlet to work properly.</span></span>

<span data-ttu-id="af02a-112">`Get-Unique` учитывает регистр.</span><span class="sxs-lookup"><span data-stu-id="af02a-112">`Get-Unique` is case-sensitive.</span></span> <span data-ttu-id="af02a-113">Поэтому строки, которые отличаются только регистром символов, считаются уникальными.</span><span class="sxs-lookup"><span data-stu-id="af02a-113">As a result, strings that differ only in character casing are considered to be unique.</span></span>

## <span data-ttu-id="af02a-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="af02a-114">EXAMPLES</span></span>

### <span data-ttu-id="af02a-115">Пример 1. получение уникальных слов в текстовом файле</span><span class="sxs-lookup"><span data-stu-id="af02a-115">Example 1: Get unique words in a text file</span></span>

<span data-ttu-id="af02a-116">Эти команды определяют число уникальных слов в текстовом файле.</span><span class="sxs-lookup"><span data-stu-id="af02a-116">These commands find the number of unique words in a text file.</span></span>

```powershell
$A = $( foreach ($line in Get-Content C:\Test1\File1.txt) {
    $line.tolower().split(" ")
  }) | Sort-Object | Get-Unique
$A.count
```

<span data-ttu-id="af02a-117">Первая команда возвращает содержимое файла File.txt.</span><span class="sxs-lookup"><span data-stu-id="af02a-117">The first command gets the content of the File.txt file.</span></span> <span data-ttu-id="af02a-118">Она преобразует каждую строку текста в строчные буквы, а затем выделяет каждое слово, отделенное пробелом (" "), в отдельную строку.</span><span class="sxs-lookup"><span data-stu-id="af02a-118">It converts each line of text to lowercase letters and then splits each word onto a separate line at the space (" ").</span></span> <span data-ttu-id="af02a-119">Затем он сортирует полученный список в алфавитном порядке (по умолчанию) и использует `Get-Unique` командлет для удаления повторяющихся слов.</span><span class="sxs-lookup"><span data-stu-id="af02a-119">Then, it sorts the resulting list alphabetically (the default) and uses the `Get-Unique` cmdlet to eliminate any duplicate words.</span></span> <span data-ttu-id="af02a-120">Результаты хранятся в `$A` переменной.</span><span class="sxs-lookup"><span data-stu-id="af02a-120">The results are stored in the `$A` variable.</span></span>

<span data-ttu-id="af02a-121">Вторая команда использует свойство **Count** коллекции строк в `$A` для определения количества элементов в `$A` .</span><span class="sxs-lookup"><span data-stu-id="af02a-121">The second command uses the **Count** property of the collection of strings in `$A` to determine how many items are in `$A`.</span></span>

### <span data-ttu-id="af02a-122">Пример 2. получение уникальных целых чисел в массиве</span><span class="sxs-lookup"><span data-stu-id="af02a-122">Example 2: Get unique integers in an array</span></span>

<span data-ttu-id="af02a-123">Эта команда находит уникальные члены во множестве целых чисел.</span><span class="sxs-lookup"><span data-stu-id="af02a-123">This command finds the unique members of the set of integers.</span></span>

```powershell
1,1,1,1,12,23,4,5,4643,5,3,3,3,3,3,3,3 | Sort-Object | Get-Unique
```

```Output
1
3
4
5
12
23
4643
```

<span data-ttu-id="af02a-124">Первая команда принимает массив целых чисел, введенный в командной строке, передает их в командлет, который `Sort-Object` должен быть отсортирован, а затем передает их в `Get-Unique` , что устраняет дублирование записей.</span><span class="sxs-lookup"><span data-stu-id="af02a-124">The first command takes an array of integers typed at the command line, pipes them to the `Sort-Object` cmdlet to be sorted, and then pipes them to `Get-Unique`, which eliminates duplicate entries.</span></span>

### <span data-ttu-id="af02a-125">Пример 3. получение уникальных типов объектов в каталоге</span><span class="sxs-lookup"><span data-stu-id="af02a-125">Example 3: Get unique object types in a directory</span></span>

<span data-ttu-id="af02a-126">Эта команда использует `Get-ChildItem` командлет для получения содержимого локального каталога, включающего файлы и каталоги.</span><span class="sxs-lookup"><span data-stu-id="af02a-126">This command uses the `Get-ChildItem` cmdlet to retrieve the contents of the local directory, which includes files and directories.</span></span>

```powershell
Get-ChildItem | Sort-Object {$_.GetType()} | Get-Unique -OnType
```

<span data-ttu-id="af02a-127">Оператор конвейера (|) отправляет результаты в `Sort-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="af02a-127">The pipeline operator (|) sends the results to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="af02a-128">`$_.GetType()`Оператор применяет метод **GetType** к каждому файлу или каталогу.</span><span class="sxs-lookup"><span data-stu-id="af02a-128">The `$_.GetType()` statement applies the **GetType** method to each file or directory.</span></span> <span data-ttu-id="af02a-129">Затем `Sort-Object` сортирует элементы по типу.</span><span class="sxs-lookup"><span data-stu-id="af02a-129">Then, `Sort-Object` sorts the items by type.</span></span> <span data-ttu-id="af02a-130">Другой конвейерный оператор отправляет результаты в `Get-Unique` .</span><span class="sxs-lookup"><span data-stu-id="af02a-130">Another pipeline operator sends the results to `Get-Unique`.</span></span> <span data-ttu-id="af02a-131">Параметр **OnType** направляет `Get-Unique` возврат только одного объекта каждого типа.</span><span class="sxs-lookup"><span data-stu-id="af02a-131">The **OnType** parameter directs `Get-Unique` to return only one object of each type.</span></span>

### <span data-ttu-id="af02a-132">Пример 4. получение уникальных процессов</span><span class="sxs-lookup"><span data-stu-id="af02a-132">Example 4: Get unique processes</span></span>

<span data-ttu-id="af02a-133">Эта команда возвращает имена запущенных на компьютере процессов без повторяющихся имен.</span><span class="sxs-lookup"><span data-stu-id="af02a-133">This command gets the names of processes running on the computer with duplicates eliminated.</span></span>

```powershell
Get-Process | Sort-Object | Select-Object processname | Get-Unique -AsString
```

<span data-ttu-id="af02a-134">`Get-Process`Команда получает все процессы на компьютере.</span><span class="sxs-lookup"><span data-stu-id="af02a-134">The `Get-Process` command gets all of the processes on the computer.</span></span> <span data-ttu-id="af02a-135">Оператор конвейера (|) передает результат в `Sort-Object` , который по умолчанию сортирует процессы в алфавитном порядке по ProcessName.</span><span class="sxs-lookup"><span data-stu-id="af02a-135">The pipeline operator (|) passes the result to `Sort-Object`, which, by default, sorts the processes alphabetically by ProcessName.</span></span> <span data-ttu-id="af02a-136">Результаты передаются в `Select-Object` командлет, который выбирает только значения свойства ProcessName каждого объекта.</span><span class="sxs-lookup"><span data-stu-id="af02a-136">The results are piped to the `Select-Object` cmdlet, which selects only the values of the ProcessName property of each object.</span></span> <span data-ttu-id="af02a-137">Затем результаты передаются в, чтобы `Get-Unique` исключить дубликаты.</span><span class="sxs-lookup"><span data-stu-id="af02a-137">The results are then piped to `Get-Unique` to eliminate duplicates.</span></span>

<span data-ttu-id="af02a-138">Параметр **AsString** указывает `Get-Unique` , что значения **processName** должны обрабатываться как строки.</span><span class="sxs-lookup"><span data-stu-id="af02a-138">The **AsString** parameter tells `Get-Unique` to treat the **ProcessName** values as strings.</span></span>
<span data-ttu-id="af02a-139">Без этого параметра `Get-Unique` обрабатывает значения **processName** как объекты и возвращает только один экземпляр объекта, то есть имя первого процесса в списке.</span><span class="sxs-lookup"><span data-stu-id="af02a-139">Without this parameter, `Get-Unique` treats the **ProcessName** values as objects and returns only one instance of the object, that is, the first process name in the list.</span></span>

## <span data-ttu-id="af02a-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="af02a-140">PARAMETERS</span></span>

### <span data-ttu-id="af02a-141">-AsString</span><span class="sxs-lookup"><span data-stu-id="af02a-141">-AsString</span></span>

<span data-ttu-id="af02a-142">Указывает, что этот командлет использует данные в качестве строки.</span><span class="sxs-lookup"><span data-stu-id="af02a-142">Indicates that this cmdlet uses the data as a string.</span></span> <span data-ttu-id="af02a-143">Без этого параметра данные обрабатываются как объект, поэтому при отправке коллекции объектов одного типа в `Get-Unique` , например коллекции файлов, возвращается только один (первый).</span><span class="sxs-lookup"><span data-stu-id="af02a-143">Without this parameter, data is treated as an object, so when you submit a collection of objects of the same type to `Get-Unique`, such as a collection of files, it returns just one (the first).</span></span> <span data-ttu-id="af02a-144">С помощью этого параметра можно находить уникальные значения свойств объектов, например имена файлов.</span><span class="sxs-lookup"><span data-stu-id="af02a-144">You can use this parameter to find the unique values of object properties, such as the file names.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AsString
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="af02a-145">-InputObject</span><span class="sxs-lookup"><span data-stu-id="af02a-145">-InputObject</span></span>

<span data-ttu-id="af02a-146">Задает входные данные для `Get-Unique` .</span><span class="sxs-lookup"><span data-stu-id="af02a-146">Specifies input for `Get-Unique`.</span></span> <span data-ttu-id="af02a-147">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="af02a-147">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span>

<span data-ttu-id="af02a-148">Этот командлет рассматривает входные данные, отправленные с помощью **InputObject** , в качестве коллекции.</span><span class="sxs-lookup"><span data-stu-id="af02a-148">This cmdlet treats the input submitted by using **InputObject** as a collection.</span></span> <span data-ttu-id="af02a-149">Он не перечисляет отдельные элементы в коллекции.</span><span class="sxs-lookup"><span data-stu-id="af02a-149">it does not enumerate individual items in the collection.</span></span> <span data-ttu-id="af02a-150">Поскольку коллекция является одним элементом, входные данные, отправленные с помощью **InputObject** , всегда возвращаются без изменений.</span><span class="sxs-lookup"><span data-stu-id="af02a-150">Because the collection is a single item, input submitted by using **InputObject** is always returned unchanged.</span></span>

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

### <span data-ttu-id="af02a-151">-OnType</span><span class="sxs-lookup"><span data-stu-id="af02a-151">-OnType</span></span>

<span data-ttu-id="af02a-152">Указывает, что этот командлет возвращает только один объект каждого типа.</span><span class="sxs-lookup"><span data-stu-id="af02a-152">Indicates that this cmdlet returns only one object of each type.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: UniqueByType
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="af02a-153">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="af02a-153">CommonParameters</span></span>

<span data-ttu-id="af02a-154">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="af02a-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="af02a-155">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="af02a-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="af02a-156">Входные данные</span><span class="sxs-lookup"><span data-stu-id="af02a-156">INPUTS</span></span>

### <span data-ttu-id="af02a-157">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="af02a-157">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="af02a-158">Можно передать объект любого типа в `Get-Unique` .</span><span class="sxs-lookup"><span data-stu-id="af02a-158">You can pipe any type of object to `Get-Unique`.</span></span>

## <span data-ttu-id="af02a-159">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="af02a-159">OUTPUTS</span></span>

### <span data-ttu-id="af02a-160">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="af02a-160">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="af02a-161">Тип `Get-Unique` возвращаемого объекта определяется входными данными.</span><span class="sxs-lookup"><span data-stu-id="af02a-161">The type of object that `Get-Unique` returns is determined by the input.</span></span>

## <span data-ttu-id="af02a-162">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="af02a-162">NOTES</span></span>

<span data-ttu-id="af02a-163">Также можно ссылаться `Get-Unique` по встроенному псевдониму `gu` .</span><span class="sxs-lookup"><span data-stu-id="af02a-163">You can also refer to `Get-Unique` by its built-in alias, `gu`.</span></span> <span data-ttu-id="af02a-164">Дополнительные сведения см. в разделе [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="af02a-164">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="af02a-165">Чтобы отсортировать список, используйте командлет Sort-Object.</span><span class="sxs-lookup"><span data-stu-id="af02a-165">To sort a list, use Sort-Object.</span></span> <span data-ttu-id="af02a-166">**Unique** `Sort-Object` Для поиска уникальных элементов в списке можно также использовать уникальный параметр.</span><span class="sxs-lookup"><span data-stu-id="af02a-166">You can also use the **Unique** parameter of `Sort-Object` to find the unique items in a list.</span></span>

## <span data-ttu-id="af02a-167">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="af02a-167">RELATED LINKS</span></span>

[<span data-ttu-id="af02a-168">Select-Object</span><span class="sxs-lookup"><span data-stu-id="af02a-168">Select-Object</span></span>](Select-Object.md)

[<span data-ttu-id="af02a-169">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="af02a-169">Sort-Object</span></span>](Sort-Object.md)
