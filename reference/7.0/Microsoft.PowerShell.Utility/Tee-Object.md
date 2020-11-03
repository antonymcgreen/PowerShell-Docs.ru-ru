---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/tee-object?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Tee-Object
ms.openlocfilehash: 47c1eb6b31f762e3950c07f9edec81a081ce616e
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93226377"
---
# <span data-ttu-id="27929-103">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="27929-103">Tee-Object</span></span>

## <span data-ttu-id="27929-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="27929-104">SYNOPSIS</span></span>
<span data-ttu-id="27929-105">Сохраняет выходные данные команды в файле или переменной, а также отправляет их в конвейер.</span><span class="sxs-lookup"><span data-stu-id="27929-105">Saves command output in a file or variable and also sends it down the pipeline.</span></span>

## <span data-ttu-id="27929-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="27929-106">SYNTAX</span></span>

### <span data-ttu-id="27929-107">Файл (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="27929-107">File (Default)</span></span>

```
Tee-Object [-InputObject <PSObject>] [-FilePath] <String> [-Append] [<CommonParameters>]
```

### <span data-ttu-id="27929-108">литералфиле</span><span class="sxs-lookup"><span data-stu-id="27929-108">LiteralFile</span></span>

```
Tee-Object [-InputObject <PSObject>] -LiteralPath <String> [<CommonParameters>]
```

### <span data-ttu-id="27929-109">Переменная</span><span class="sxs-lookup"><span data-stu-id="27929-109">Variable</span></span>

```
Tee-Object [-InputObject <PSObject>] -Variable <String> [<CommonParameters>]
```

## <span data-ttu-id="27929-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="27929-110">DESCRIPTION</span></span>

<span data-ttu-id="27929-111">`Tee-Object`Командлет перенаправляет выходные данные, то есть отправляет выходные данные команды в двух направлениях (например, букве T).</span><span class="sxs-lookup"><span data-stu-id="27929-111">The `Tee-Object` cmdlet redirects output, that is, it sends the output of a command in two directions (like the letter T).</span></span> <span data-ttu-id="27929-112">Она сохраняет выходные данные команды в файле или переменной, а также отправляет их в конвейер.</span><span class="sxs-lookup"><span data-stu-id="27929-112">It stores the output in a file or variable and also sends it down the pipeline.</span></span> <span data-ttu-id="27929-113">Если `Tee-Object` — Последняя команда в конвейере, выходные данные команды отображаются в командной строке.</span><span class="sxs-lookup"><span data-stu-id="27929-113">If `Tee-Object` is the last command in the pipeline, the command output is displayed at the prompt.</span></span>

## <span data-ttu-id="27929-114">Примеры</span><span class="sxs-lookup"><span data-stu-id="27929-114">EXAMPLES</span></span>

### <span data-ttu-id="27929-115">Пример 1. вывод процессов в файл и в консоль</span><span class="sxs-lookup"><span data-stu-id="27929-115">Example 1: Output processes to a file and to the console</span></span>

<span data-ttu-id="27929-116">В этом примере возвращается список процессов, запущенных на компьютере, и результат отправляется в файл.</span><span class="sxs-lookup"><span data-stu-id="27929-116">This example gets a list of the processes running on the computer and sends the result to a file.</span></span>
<span data-ttu-id="27929-117">Так как второй путь не указан, процессы также отображаются в консоли.</span><span class="sxs-lookup"><span data-stu-id="27929-117">Because a second path is not specified, the processes are also displayed in the console.</span></span>

```powershell
Get-Process | Tee-Object -FilePath "C:\Test1\testfile2.txt"
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)    Id ProcessName
-------  ------    -----      ----- -----   ------    -- -----------
83       4     2300       4520    39     0.30    4032 00THotkey
272      6     1400       3944    34     0.06    3088 alg
81       3      804       3284    21     2.45     148 ApntEx
81       4     2008       5808    38     0.75    3684 Apoint
...
```

### <span data-ttu-id="27929-118">Пример 2. вывод процессов в переменную и `Select-Object`</span><span class="sxs-lookup"><span data-stu-id="27929-118">Example 2: Output processes to a variable and `Select-Object`</span></span>

<span data-ttu-id="27929-119">Этот пример возвращает список процессов, запущенных на компьютере, сохраняет их в `$proc` переменную и передает их в `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="27929-119">This example gets a list of the processes running on the computer, saves them to the `$proc` variable, and pipes them to `Select-Object`.</span></span>

```powershell
Get-Process notepad | Tee-Object -Variable proc | Select-Object processname,handles
```

```Output
ProcessName                              Handles
-----------                              -------
notepad                                  43
notepad                                  37
notepad                                  38
notepad                                  38
```

<span data-ttu-id="27929-120">`Select-Object`Командлет выбирает **processName** и **обрабатывает** свойства.</span><span class="sxs-lookup"><span data-stu-id="27929-120">The `Select-Object` cmdlet selects the **ProcessName** and **Handles** properties.</span></span> <span data-ttu-id="27929-121">Обратите внимание, что `$proc` Переменная включает сведения по умолчанию, возвращаемые `Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="27929-121">Note that the `$proc` variable includes the default information returned by `Get-Process`.</span></span>

### <span data-ttu-id="27929-122">Пример 3. вывод системных файлов в два файла журнала</span><span class="sxs-lookup"><span data-stu-id="27929-122">Example 3: Output system files to two log files</span></span>

<span data-ttu-id="27929-123">В этом примере список системных файлов сохраняется в двух файлах журнала, в совокупном файле и в текущем файле.</span><span class="sxs-lookup"><span data-stu-id="27929-123">This example saves a list of system files in a two log files, a cumulative file and a current file.</span></span>

```powershell
Get-ChildItem -Path D: -File -System -Recurse |
  Tee-Object -FilePath "c:\test\AllSystemFiles.txt" -Append |
    Out-File c:\test\NewSystemFiles.txt
```

<span data-ttu-id="27929-124">Команда использует `Get-ChildItem` командлет для рекурсивного поиска системных файлов на диске D:.</span><span class="sxs-lookup"><span data-stu-id="27929-124">The command uses the `Get-ChildItem` cmdlet to do a recursive search for system files on the D: drive.</span></span> <span data-ttu-id="27929-125">Оператор конвейера (|) отправляет список в `Tee-Object` , который добавляет список в файл AllSystemFiles.txt и передает список по конвейеру в `Out-File` командлет, который сохраняет список в файле NewSystemFiles.txt.</span><span class="sxs-lookup"><span data-stu-id="27929-125">A pipeline operator (|) sends the list to `Tee-Object`, which appends the list to the AllSystemFiles.txt file and passes the list down the pipeline to the `Out-File` cmdlet, which saves the list in the NewSystemFiles.txt file.</span></span>

## <span data-ttu-id="27929-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="27929-126">PARAMETERS</span></span>

### <span data-ttu-id="27929-127">— Добавление</span><span class="sxs-lookup"><span data-stu-id="27929-127">-Append</span></span>

<span data-ttu-id="27929-128">Указывает, что командлет добавляет выходные данные в указанный файл.</span><span class="sxs-lookup"><span data-stu-id="27929-128">Indicates that the cmdlet appends the output to the specified file.</span></span> <span data-ttu-id="27929-129">Без этого параметра новое содержимое заменяет все существующее содержимое файла без предупреждения.</span><span class="sxs-lookup"><span data-stu-id="27929-129">Without this parameter, the new content replaces any existing content in the file without warning.</span></span>

<span data-ttu-id="27929-130">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="27929-130">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: File
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="27929-131">-FilePath</span><span class="sxs-lookup"><span data-stu-id="27929-131">-FilePath</span></span>

<span data-ttu-id="27929-132">Указывает файл, который этот командлет сохраняет в подстановочных знаках, но должен разрешаться в один файл.</span><span class="sxs-lookup"><span data-stu-id="27929-132">Specifies a file that this cmdlet saves the object to Wildcard characters are permitted, but must resolve to a single file.</span></span>

```yaml
Type: System.String
Parameter Sets: File
Aliases: Path

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="27929-133">-InputObject</span><span class="sxs-lookup"><span data-stu-id="27929-133">-InputObject</span></span>

<span data-ttu-id="27929-134">Указывает объект, который необходимо показать и сохранить.</span><span class="sxs-lookup"><span data-stu-id="27929-134">Specifies the object to be saved and displayed.</span></span> <span data-ttu-id="27929-135">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="27929-135">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span> <span data-ttu-id="27929-136">Также можно передать объект в `Tee-Object` .</span><span class="sxs-lookup"><span data-stu-id="27929-136">You can also pipe an object to `Tee-Object`.</span></span>

<span data-ttu-id="27929-137">При использовании параметра **InputObject** с параметром `Tee-Object` , а не с результатами команды трубопроводов в `Tee-Object` значение **InputObject** рассматривается как один объект, даже если значение является коллекцией.</span><span class="sxs-lookup"><span data-stu-id="27929-137">When you use the **InputObject** parameter with `Tee-Object`, instead of piping command results to `Tee-Object`, the **InputObject** value is treated as a single object even if the value is a collection.</span></span>

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

### <span data-ttu-id="27929-138">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="27929-138">-LiteralPath</span></span>

<span data-ttu-id="27929-139">Указывает файл, в который этот командлет сохраняет объект.</span><span class="sxs-lookup"><span data-stu-id="27929-139">Specifies a file that this cmdlet saves the object to.</span></span> <span data-ttu-id="27929-140">В отличие от **FilePath** значение параметра **LiteralPath** используется именно в том виде, в котором оно вводится.</span><span class="sxs-lookup"><span data-stu-id="27929-140">Unlike **FilePath** , the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="27929-141">Никакие символы не интерпретируются как знаки подстановки.</span><span class="sxs-lookup"><span data-stu-id="27929-141">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="27929-142">Если путь содержит escape-символы, заключите его в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="27929-142">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="27929-143">Одинарные кавычки указывают PowerShell не интерпретировать какие-либо символы как escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="27929-143">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: LiteralFile
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="27929-144">-Variable</span><span class="sxs-lookup"><span data-stu-id="27929-144">-Variable</span></span>

<span data-ttu-id="27929-145">Указывает переменную, в которую командлет сохраняет объект.</span><span class="sxs-lookup"><span data-stu-id="27929-145">Specifies a variable that the cmdlet saves the object to.</span></span> <span data-ttu-id="27929-146">Введите имя переменной без предшествующего знака доллара ( `$` ).</span><span class="sxs-lookup"><span data-stu-id="27929-146">Enter a variable name without the preceding dollar sign (`$`).</span></span>

```yaml
Type: System.String
Parameter Sets: Variable
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="27929-147">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="27929-147">CommonParameters</span></span>

<span data-ttu-id="27929-148">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="27929-148">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="27929-149">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="27929-149">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="27929-150">Входные данные</span><span class="sxs-lookup"><span data-stu-id="27929-150">INPUTS</span></span>

### <span data-ttu-id="27929-151">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="27929-151">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="27929-152">Вы можете передать объекты в `Tee-Object` .</span><span class="sxs-lookup"><span data-stu-id="27929-152">You can pipe objects to `Tee-Object`.</span></span>

## <span data-ttu-id="27929-153">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="27929-153">OUTPUTS</span></span>

### <span data-ttu-id="27929-154">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="27929-154">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="27929-155">`Tee-Object` Возвращает перенаправляемый объект.</span><span class="sxs-lookup"><span data-stu-id="27929-155">`Tee-Object` returns the object that it redirects.</span></span>

## <span data-ttu-id="27929-156">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="27929-156">NOTES</span></span>

<span data-ttu-id="27929-157">Можно также использовать `Out-File` командлет или оператор перенаправления, оба из которых сохраняют выходные данные в файле, но не отправляют их по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="27929-157">You can also use the `Out-File` cmdlet or the redirection operator, both of which save the output in a file but do not send it down the pipeline.</span></span>

<span data-ttu-id="27929-158">Начиная с PowerShell 6, `Tee-Object` при записи в файлы использует кодировку UTF-8 без спецификации.</span><span class="sxs-lookup"><span data-stu-id="27929-158">Beginning in PowerShell 6, `Tee-Object` uses BOM-less UTF-8 encoding when it writes to files.</span></span> <span data-ttu-id="27929-159">Если требуется другая кодировка, используйте `Out-File` командлет с параметром **Encoding** .</span><span class="sxs-lookup"><span data-stu-id="27929-159">If you need a different encoding, use the `Out-File` cmdlet with the **Encoding** parameter.</span></span>

## <span data-ttu-id="27929-160">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="27929-160">RELATED LINKS</span></span>

[<span data-ttu-id="27929-161">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="27929-161">Compare-Object</span></span>](Compare-Object.md)

[<span data-ttu-id="27929-162">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="27929-162">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="27929-163">Group-Object</span><span class="sxs-lookup"><span data-stu-id="27929-163">Group-Object</span></span>](Group-Object.md)

[<span data-ttu-id="27929-164">Measure-Object;</span><span class="sxs-lookup"><span data-stu-id="27929-164">Measure-Object</span></span>](Measure-Object.md)

[<span data-ttu-id="27929-165">New-Object</span><span class="sxs-lookup"><span data-stu-id="27929-165">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="27929-166">Select-Object</span><span class="sxs-lookup"><span data-stu-id="27929-166">Select-Object</span></span>](Select-Object.md)

[<span data-ttu-id="27929-167">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="27929-167">Sort-Object</span></span>](Sort-Object.md)

[<span data-ttu-id="27929-168">Where-Object</span><span class="sxs-lookup"><span data-stu-id="27929-168">Where-Object</span></span>](../Microsoft.PowerShell.Core/Where-Object.md)

[<span data-ttu-id="27929-169">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="27929-169">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)
