---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 05/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/add-history?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-History
ms.openlocfilehash: d2c0abb0e6742de3e316fe964d5945375591ef4d
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605528"
---
# <span data-ttu-id="1c38c-102">Add-History</span><span class="sxs-lookup"><span data-stu-id="1c38c-102">Add-History</span></span>

## <span data-ttu-id="1c38c-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="1c38c-103">SYNOPSIS</span></span>
<span data-ttu-id="1c38c-104">Добавляет записи в журнал сеанса.</span><span class="sxs-lookup"><span data-stu-id="1c38c-104">Appends entries to the session history.</span></span>

## <span data-ttu-id="1c38c-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1c38c-105">SYNTAX</span></span>

```
Add-History [[-InputObject] <PSObject[]>] [-Passthru] [<CommonParameters>]
```

## <span data-ttu-id="1c38c-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1c38c-106">DESCRIPTION</span></span>

<span data-ttu-id="1c38c-107">`Add-History`Командлет добавляет записи в конец журнала сеанса, то есть список команд, введенных во время текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="1c38c-107">The `Add-History` cmdlet adds entries to the end of the session history, that is, the list of commands entered during the current session.</span></span>

<span data-ttu-id="1c38c-108">Журнал сеанса — это список команд, введенных за время сеанса.</span><span class="sxs-lookup"><span data-stu-id="1c38c-108">The session history is a list of the commands entered during the session.</span></span> <span data-ttu-id="1c38c-109">В журнале сеанса представлен порядок выполнения, состояние, время начала и завершения выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="1c38c-109">The session history represents the order of execution, the status, and the start and end times of the command.</span></span> <span data-ttu-id="1c38c-110">По мере ввода каждой команды PowerShell добавляет его в журнал, чтобы его можно было использовать повторно.</span><span class="sxs-lookup"><span data-stu-id="1c38c-110">As you enter each command, PowerShell adds it to the history so that you can reuse it.</span></span> <span data-ttu-id="1c38c-111">Дополнительные сведения о журнале сеанса см. в разделе [about_History](About/about_History.md).</span><span class="sxs-lookup"><span data-stu-id="1c38c-111">For more information about the session history, see [about_History](About/about_History.md).</span></span>

<span data-ttu-id="1c38c-112">Журнал сеанса управляется отдельно от журнала, поддерживаемого модулем **PSReadLine** .</span><span class="sxs-lookup"><span data-stu-id="1c38c-112">The session history is managed separately from the history maintained by the **PSReadLine** module.</span></span>
<span data-ttu-id="1c38c-113">Оба журнала доступны в сеансах, где загружен **PSReadLine** .</span><span class="sxs-lookup"><span data-stu-id="1c38c-113">Both histories are available in sessions where **PSReadLine** is loaded.</span></span> <span data-ttu-id="1c38c-114">Этот командлет работает только с журналом сеанса.</span><span class="sxs-lookup"><span data-stu-id="1c38c-114">This cmdlet only works with the session history.</span></span> <span data-ttu-id="1c38c-115">Дополнительные сведения см. в разделе [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).</span><span class="sxs-lookup"><span data-stu-id="1c38c-115">For more information see, [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).</span></span>

<span data-ttu-id="1c38c-116">Командлет можно использовать `Get-History` для получения команд и передачи их в `Add-History` , либо можно экспортировать команды в CSV-или XML файл, затем импортировать команды и передать импортированный файл в `Add-History` .</span><span class="sxs-lookup"><span data-stu-id="1c38c-116">You can use the `Get-History` cmdlet to get the commands and pass them to `Add-History`, or you can export the commands to a CSV or XML file, then import the commands, and pass the imported file to `Add-History`.</span></span> <span data-ttu-id="1c38c-117">Этот командлет позволяет добавить определенные команды в журнал или создать единый файл журнала, в котором содержатся команды, введенные в течение нескольких сеансов.</span><span class="sxs-lookup"><span data-stu-id="1c38c-117">You can use this cmdlet to add specific commands to the history or to create a single history file that includes commands from more than one session.</span></span>

## <span data-ttu-id="1c38c-118">Примеры</span><span class="sxs-lookup"><span data-stu-id="1c38c-118">EXAMPLES</span></span>

### <span data-ttu-id="1c38c-119">Пример 1. Добавление команд в журнал другого сеанса</span><span class="sxs-lookup"><span data-stu-id="1c38c-119">Example 1: Add commands to the history of a different session</span></span>

<span data-ttu-id="1c38c-120">Этот пример добавляет команды, введенные в один сеанс PowerShell, в журнал другого сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1c38c-120">This example add the commands typed in one PowerShell session to the history of a different PowerShell session.</span></span>

```powershell
Get-History | Export-Csv c:\testing\history.csv -IncludeTypeInformation
Import-Csv c:\testing\history.csv | Add-History
```

<span data-ttu-id="1c38c-121">Первая команда получает объекты, представляющие команды в журнале, и экспортирует их в `History.csv` файл.</span><span class="sxs-lookup"><span data-stu-id="1c38c-121">The first command gets objects representing the commands in the history and exports them to the `History.csv` file.</span></span>

<span data-ttu-id="1c38c-122">Вторая команда должна вводится в командной строке другого сеанса.</span><span class="sxs-lookup"><span data-stu-id="1c38c-122">The second command is typed at the command line of a different session.</span></span> <span data-ttu-id="1c38c-123">Он использует `Import-Csv` командлет для импорта объектов в `History.csv` файл.</span><span class="sxs-lookup"><span data-stu-id="1c38c-123">It uses the `Import-Csv` cmdlet to import the objects in the `History.csv` file.</span></span> <span data-ttu-id="1c38c-124">Оператор конвейера ( `|` ) передает объекты в `Add-History` командлет, который добавляет объекты, представляющие команды в файле, в `History.csv` текущий журнал сеанса.</span><span class="sxs-lookup"><span data-stu-id="1c38c-124">The pipeline operator (`|`) passes the objects to the `Add-History` cmdlet, which adds the objects representing the commands in the `History.csv` file to the current session history.</span></span>

### <span data-ttu-id="1c38c-125">Пример 2. команды Import и Run</span><span class="sxs-lookup"><span data-stu-id="1c38c-125">Example 2: Import and run commands</span></span>

<span data-ttu-id="1c38c-126">Этот пример импортирует команды из `History.xml` файла, добавляет их в текущий журнал сеанса, а затем выполняет команды в объединенном журнале.</span><span class="sxs-lookup"><span data-stu-id="1c38c-126">This example imports commands from the `History.xml` file, adds them to the current session history, and then runs the commands in the combined history.</span></span>

```powershell
Import-Clixml c:\temp\history.xml | Add-History -PassThru | ForEach-Object -Process {Invoke-History}
```

<span data-ttu-id="1c38c-127">Первая команда использует `Import-Clixml` командлет для импорта журнала команд, экспортированного в `History.xml` файл.</span><span class="sxs-lookup"><span data-stu-id="1c38c-127">The first command uses the `Import-Clixml` cmdlet to import a command history that was exported to the `History.xml` file.</span></span> <span data-ttu-id="1c38c-128">Оператор конвейера передает команды в `Add-History` командлет, который добавляет команды в текущий журнал сеанса.</span><span class="sxs-lookup"><span data-stu-id="1c38c-128">The pipeline operator passes the commands to the `Add-History` cmdlet, which adds the commands to the current session history.</span></span> <span data-ttu-id="1c38c-129">Параметр **PassThru** передает объекты, представляющие добавленные команды, в конвейер.</span><span class="sxs-lookup"><span data-stu-id="1c38c-129">The **PassThru** parameter passes the objects representing the added commands down the pipeline.</span></span>

<span data-ttu-id="1c38c-130">Затем команда использует `ForEach-Object` командлет для применения `Invoke-History` команды к каждой из команд в объединенном журнале.</span><span class="sxs-lookup"><span data-stu-id="1c38c-130">The command then uses the `ForEach-Object` cmdlet to apply the `Invoke-History` command to each of the commands in the combined history.</span></span> <span data-ttu-id="1c38c-131">`Invoke-History`Команда форматируется как блок скрипта, заключенный в фигурные скобки ( `{}` ), как это  требуется параметру Process `ForEach-Object` командлета.</span><span class="sxs-lookup"><span data-stu-id="1c38c-131">The `Invoke-History` command is formatted as a script block, enclosed in braces (`{}`), as required by the **Process** parameter of the `ForEach-Object` cmdlet.</span></span>

### <span data-ttu-id="1c38c-132">Пример 3. Добавление команд в журнал в конец журнала</span><span class="sxs-lookup"><span data-stu-id="1c38c-132">Example 3: Add commands in the history to the end of the history</span></span>

<span data-ttu-id="1c38c-133">В этом примере первые пять команд в журнале добавляются в конец списка журнала.</span><span class="sxs-lookup"><span data-stu-id="1c38c-133">This example adds the first five commands in the history to the end of the history list.</span></span>

```powershell
Get-History -Id 5 -Count 5 | Add-History
```

<span data-ttu-id="1c38c-134">`Get-History`Командлет получает пять команд, которые заканчиваются командой 5.</span><span class="sxs-lookup"><span data-stu-id="1c38c-134">The `Get-History` cmdlet gets the five commands ending in command 5.</span></span> <span data-ttu-id="1c38c-135">Оператор конвейера передает их в `Add-History` командлет, который добавляет их к текущему журналу.</span><span class="sxs-lookup"><span data-stu-id="1c38c-135">The pipeline operator passes them to the `Add-History` cmdlet, which appends them to the current history.</span></span> <span data-ttu-id="1c38c-136">`Add-History`Команда не содержит никаких параметров, но PowerShell связывает объекты, переданные через конвейер, с параметром **InputObject** `Add-History` .</span><span class="sxs-lookup"><span data-stu-id="1c38c-136">The `Add-History` command does not include any parameters, but PowerShell associates the objects passed through the pipeline with the **InputObject** parameter of `Add-History`.</span></span>

### <span data-ttu-id="1c38c-137">Пример 4. Добавление команд в CSV-файл к текущему журналу</span><span class="sxs-lookup"><span data-stu-id="1c38c-137">Example 4: Add commands in a .csv file to the current history</span></span>

<span data-ttu-id="1c38c-138">В этом примере команды добавляются в `History.csv` файл в журнал текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="1c38c-138">This example add the commands in the `History.csv` file to the current session history.</span></span>

```powershell
$a = Import-Csv c:\testing\history.csv
Add-History -InputObject $a -PassThru
```

<span data-ttu-id="1c38c-139">`Import-Csv`Командлет импортирует команды в `History.csv` файл и сохраняет его содержимое в переменной `$a` .</span><span class="sxs-lookup"><span data-stu-id="1c38c-139">The `Import-Csv` cmdlet imports the commands in the `History.csv` file and store its contents in the variable `$a`.</span></span>

<span data-ttu-id="1c38c-140">Вторая команда использует `Add-History` командлет для добавления команд из `History.csv` в текущий журнал сеанса.</span><span class="sxs-lookup"><span data-stu-id="1c38c-140">The second command uses the `Add-History` cmdlet to add the commands from `History.csv` to the current session history.</span></span> <span data-ttu-id="1c38c-141">Он использует параметр **InputObject** для указания `$a` переменной, а параметр **PassThru** — для создания объекта, отображаемого в командной строке.</span><span class="sxs-lookup"><span data-stu-id="1c38c-141">It uses the **InputObject** parameter to specify the `$a` variable and the **PassThru** parameter to generate an object to display at the command line.</span></span> <span data-ttu-id="1c38c-142">Без параметра **PassThru** `Add-History` командлет не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="1c38c-142">Without the **PassThru** parameter, the `Add-History` cmdlet does not generate any output.</span></span>

### <span data-ttu-id="1c38c-143">Пример 5. Добавление команд в XML-файл в текущий журнал</span><span class="sxs-lookup"><span data-stu-id="1c38c-143">Example 5: Add commands in an .xml file to the current history</span></span>

<span data-ttu-id="1c38c-144">В этом примере команды добавляются в `history.xml` файл в журнал текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="1c38c-144">This example adds the commands in the `history.xml` file to the current session history.</span></span>

```powershell
Add-History -InputObject (Import-Clixml c:\temp\history.xml)
```

<span data-ttu-id="1c38c-145">Параметр **InputObject** передает результаты команды в круглые скобки в `Add-History` командлет.</span><span class="sxs-lookup"><span data-stu-id="1c38c-145">The **InputObject** parameter passes the results of the command in parentheses to the `Add-History` cmdlet.</span></span> <span data-ttu-id="1c38c-146">Команда в круглых скобках, которая выполняется в первую очередь, импортирует `history.xml` файл в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1c38c-146">The command in parentheses, which is executed first, imports the `history.xml` file into PowerShell.</span></span> <span data-ttu-id="1c38c-147">`Add-History`Затем командлет добавляет команды в файл в журнал сеанса.</span><span class="sxs-lookup"><span data-stu-id="1c38c-147">The `Add-History` cmdlet then adds the commands in the file to the session history.</span></span>

## <span data-ttu-id="1c38c-148">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1c38c-148">PARAMETERS</span></span>

### <span data-ttu-id="1c38c-149">-InputObject</span><span class="sxs-lookup"><span data-stu-id="1c38c-149">-InputObject</span></span>

<span data-ttu-id="1c38c-150">Указывает массив записей для добавления в журнал в качестве объекта **хисторинфо** в журнал сеанса.</span><span class="sxs-lookup"><span data-stu-id="1c38c-150">Specifies an array of entries to add to the history as **HistoryInfo** object to the session history.</span></span>
<span data-ttu-id="1c38c-151">Этот параметр можно использовать для отправки объекта **хисторинфо** , например, тех, которые возвращаются `Get-History` `Import-Clixml` `Import-Csv` командлетами, или, в `Add-History` .</span><span class="sxs-lookup"><span data-stu-id="1c38c-151">You can use this parameter to submit a **HistoryInfo** object, such as the ones that are returned by the `Get-History`, `Import-Clixml`, or `Import-Csv` cmdlets, to `Add-History`.</span></span>

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="1c38c-152">-PassThru</span><span class="sxs-lookup"><span data-stu-id="1c38c-152">-Passthru</span></span>

<span data-ttu-id="1c38c-153">Указывает, что этот командлет возвращает объект **хисторинфо** для каждой записи журнала.</span><span class="sxs-lookup"><span data-stu-id="1c38c-153">Indicates that this cmdlet returns a **HistoryInfo** object for each history entry.</span></span> <span data-ttu-id="1c38c-154">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="1c38c-154">By default, this cmdlet does not generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1c38c-155">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="1c38c-155">CommonParameters</span></span>

<span data-ttu-id="1c38c-156">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1c38c-156">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1c38c-157">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1c38c-157">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1c38c-158">Входные данные</span><span class="sxs-lookup"><span data-stu-id="1c38c-158">INPUTS</span></span>

### <span data-ttu-id="1c38c-159">Microsoft. PowerShell. Commands. Хисторинфо</span><span class="sxs-lookup"><span data-stu-id="1c38c-159">Microsoft.PowerShell.Commands.HistoryInfo</span></span>

<span data-ttu-id="1c38c-160">Объект **хисторинфо** можно передать в этот командлет по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="1c38c-160">You can pipe a **HistoryInfo** object to this cmdlet.</span></span>

## <span data-ttu-id="1c38c-161">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="1c38c-161">OUTPUTS</span></span>

### <span data-ttu-id="1c38c-162">Нет или Microsoft. PowerShell. Commands. Хисторинфо</span><span class="sxs-lookup"><span data-stu-id="1c38c-162">None or Microsoft.PowerShell.Commands.HistoryInfo</span></span>

<span data-ttu-id="1c38c-163">Этот командлет возвращает объект **хисторинфо** , если указан параметр **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="1c38c-163">This cmdlet returns a **HistoryInfo** object if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="1c38c-164">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="1c38c-164">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="1c38c-165">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="1c38c-165">NOTES</span></span>

<span data-ttu-id="1c38c-166">Журнал сеанса — это список команд, вводимых в сеансе вместе с ИДЕНТИФИКАТОРом.</span><span class="sxs-lookup"><span data-stu-id="1c38c-166">The session history is a list of the commands entered during the session together with the ID.</span></span> <span data-ttu-id="1c38c-167">В журнале сеанса представлен порядок выполнения, состояние, время начала и завершения выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="1c38c-167">The session history represents the order of execution, the status, and the start and end times of the command.</span></span> <span data-ttu-id="1c38c-168">По мере ввода каждой команды PowerShell добавляет его в журнал, чтобы его можно было использовать повторно.</span><span class="sxs-lookup"><span data-stu-id="1c38c-168">As you enter each command, PowerShell adds it to the history so that you can reuse it.</span></span> <span data-ttu-id="1c38c-169">Дополнительные сведения о журнале сеанса см. в разделе [about_History](About/about_History.md).</span><span class="sxs-lookup"><span data-stu-id="1c38c-169">For more information about the session history, see [about_History](About/about_History.md).</span></span>

<span data-ttu-id="1c38c-170">Чтобы указать команды, которые нужно добавить в журнал, используйте параметр **InputObject**.</span><span class="sxs-lookup"><span data-stu-id="1c38c-170">To specify the commands to add to the history, use the **InputObject** parameter.</span></span> <span data-ttu-id="1c38c-171">`Add-History`Команда принимает только объекты **хисторинфо** , например, возвращаемые командлетом для каждой команды `Get-History` .</span><span class="sxs-lookup"><span data-stu-id="1c38c-171">The `Add-History` command accepts only **HistoryInfo** objects, such as those returned for each command by the `Get-History` cmdlet.</span></span> <span data-ttu-id="1c38c-172">Передать путь и имя файла или список команд по конвейеру нельзя.</span><span class="sxs-lookup"><span data-stu-id="1c38c-172">You cannot pass it a path and file name or a list of commands.</span></span>

<span data-ttu-id="1c38c-173">Параметр **InputObject** можно использовать для передачи файла **хисторинфо** объектов в `Add-History` .</span><span class="sxs-lookup"><span data-stu-id="1c38c-173">You can use the **InputObject** parameter to pass a file of **HistoryInfo** objects to `Add-History`.</span></span> <span data-ttu-id="1c38c-174">Для этого экспортируйте результаты `Get-History` команды в файл с помощью `Export-Csv` `Export-Clixml` командлета или, а затем импортируйте файл с помощью `Import-Csv` `Import-Clixml` командлетов или.</span><span class="sxs-lookup"><span data-stu-id="1c38c-174">To do so, export the results of a `Get-History` command to a file by using the `Export-Csv` or `Export-Clixml` cmdlet and then import the file by using the `Import-Csv` or `Import-Clixml` cmdlets.</span></span> <span data-ttu-id="1c38c-175">Затем можно передать файл импортированных объектов **хисторинфо** в `Add-History` конвейер или в переменную.</span><span class="sxs-lookup"><span data-stu-id="1c38c-175">You can then pass the file of imported **HistoryInfo** objects to `Add-History` through a pipeline or in a variable.</span></span> <span data-ttu-id="1c38c-176">Дополнительные сведения см. в примерах.</span><span class="sxs-lookup"><span data-stu-id="1c38c-176">For more information, see the examples.</span></span>

<span data-ttu-id="1c38c-177">Файл объектов **хисторинфо** , передаваемый в `Add-History` командлет, должен включать сведения о типе, заголовки столбцов и все свойства объектов **хисторинфо** .</span><span class="sxs-lookup"><span data-stu-id="1c38c-177">The file of **HistoryInfo** objects that you pass to the `Add-History` cmdlet must include the type information, column headings, and all of the properties of the **HistoryInfo** objects.</span></span> <span data-ttu-id="1c38c-178">Если предполагается передать объекты обратно `Add-History` , не используйте параметр **NoTypeInformation** `Export-Csv` командлета и не удаляйте сведения о типе, заголовки столбцов или поля в файле.</span><span class="sxs-lookup"><span data-stu-id="1c38c-178">If you intend to pass the objects back to `Add-History`, do not use the **NoTypeInformation** parameter of the `Export-Csv` cmdlet and do not delete the type information, column headings, or any fields in the file.</span></span>

<span data-ttu-id="1c38c-179">Чтобы изменить журнал сеанса, экспортируйте сеанс в файл CSV или XML, измените файл, импортируйте файл и используйте `Add-History` , чтобы добавить его в текущий журнал сеанса.</span><span class="sxs-lookup"><span data-stu-id="1c38c-179">To modify the session history, export the session to a CSV or XML file, modify the file, import the file, and use `Add-History` to append it to the current session history.</span></span>

## <span data-ttu-id="1c38c-180">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="1c38c-180">RELATED LINKS</span></span>

[<span data-ttu-id="1c38c-181">Clear-History</span><span class="sxs-lookup"><span data-stu-id="1c38c-181">Clear-History</span></span>](Clear-History.md)

[<span data-ttu-id="1c38c-182">Get-History</span><span class="sxs-lookup"><span data-stu-id="1c38c-182">Get-History</span></span>](Get-History.md)

[<span data-ttu-id="1c38c-183">Invoke-History</span><span class="sxs-lookup"><span data-stu-id="1c38c-183">Invoke-History</span></span>](Invoke-History.md)

[<span data-ttu-id="1c38c-184">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="1c38c-184">about_PSReadLine</span></span>](../PSReadLine/About/about_PSReadLine.md)

[<span data-ttu-id="1c38c-185">Get-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="1c38c-185">Get-PSReadLineOption</span></span>](/powershell/module/psreadline/get-psreadlineoption)

[<span data-ttu-id="1c38c-186">Set-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="1c38c-186">Set-PSReadLineOption</span></span>](/powershell/module/psreadline/set-psreadlineoption)

