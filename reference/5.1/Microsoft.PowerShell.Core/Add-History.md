---
external help file: System.Management.Automation.dll-help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 05/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/add-history?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-History
ms.openlocfilehash: 29f1bbab871a91a9bd77c42f99f9e7f11e18b588
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93226729"
---
# <span data-ttu-id="85e7b-103">Add-History</span><span class="sxs-lookup"><span data-stu-id="85e7b-103">Add-History</span></span>

## <span data-ttu-id="85e7b-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="85e7b-104">SYNOPSIS</span></span>
<span data-ttu-id="85e7b-105">Добавляет записи в журнал сеанса.</span><span class="sxs-lookup"><span data-stu-id="85e7b-105">Appends entries to the session history.</span></span>

## <span data-ttu-id="85e7b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="85e7b-106">SYNTAX</span></span>

```
Add-History [[-InputObject] <PSObject[]>] [-Passthru] [<CommonParameters>]
```

## <span data-ttu-id="85e7b-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="85e7b-107">DESCRIPTION</span></span>

<span data-ttu-id="85e7b-108">`Add-History`Командлет добавляет записи в конец журнала сеанса, то есть список команд, введенных во время текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="85e7b-108">The `Add-History` cmdlet adds entries to the end of the session history, that is, the list of commands entered during the current session.</span></span>

<span data-ttu-id="85e7b-109">Журнал сеанса — это список команд, введенных за время сеанса.</span><span class="sxs-lookup"><span data-stu-id="85e7b-109">The session history is a list of the commands entered during the session.</span></span> <span data-ttu-id="85e7b-110">В журнале сеанса представлен порядок выполнения, состояние, время начала и завершения выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="85e7b-110">The session history represents the order of execution, the status, and the start and end times of the command.</span></span> <span data-ttu-id="85e7b-111">По мере ввода каждой команды PowerShell добавляет его в журнал, чтобы его можно было использовать повторно.</span><span class="sxs-lookup"><span data-stu-id="85e7b-111">As you enter each command, PowerShell adds it to the history so that you can reuse it.</span></span> <span data-ttu-id="85e7b-112">Дополнительные сведения о журнале сеанса см. в разделе [about_History](About/about_History.md).</span><span class="sxs-lookup"><span data-stu-id="85e7b-112">For more information about the session history, see [about_History](About/about_History.md).</span></span>

<span data-ttu-id="85e7b-113">Журнал сеанса управляется отдельно от журнала, поддерживаемого модулем **PSReadLine** .</span><span class="sxs-lookup"><span data-stu-id="85e7b-113">The session history is managed separately from the history maintained by the **PSReadLine** module.</span></span>
<span data-ttu-id="85e7b-114">Оба журнала доступны в сеансах, где загружен **PSReadLine** .</span><span class="sxs-lookup"><span data-stu-id="85e7b-114">Both histories are available in sessions where **PSReadLine** is loaded.</span></span> <span data-ttu-id="85e7b-115">Этот командлет работает только с журналом сеанса.</span><span class="sxs-lookup"><span data-stu-id="85e7b-115">This cmdlet only works with the session history.</span></span> <span data-ttu-id="85e7b-116">Дополнительные сведения см. в разделе [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).</span><span class="sxs-lookup"><span data-stu-id="85e7b-116">For more information see, [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).</span></span>

<span data-ttu-id="85e7b-117">Командлет можно использовать `Get-History` для получения команд и передачи их в `Add-History` , либо можно экспортировать команды в CSV-или XML файл, затем импортировать команды и передать импортированный файл в `Add-History` .</span><span class="sxs-lookup"><span data-stu-id="85e7b-117">You can use the `Get-History` cmdlet to get the commands and pass them to `Add-History`, or you can export the commands to a CSV or XML file, then import the commands, and pass the imported file to `Add-History`.</span></span> <span data-ttu-id="85e7b-118">Этот командлет позволяет добавить определенные команды в журнал или создать единый файл журнала, в котором содержатся команды, введенные в течение нескольких сеансов.</span><span class="sxs-lookup"><span data-stu-id="85e7b-118">You can use this cmdlet to add specific commands to the history or to create a single history file that includes commands from more than one session.</span></span>

## <span data-ttu-id="85e7b-119">Примеры</span><span class="sxs-lookup"><span data-stu-id="85e7b-119">EXAMPLES</span></span>

### <span data-ttu-id="85e7b-120">Пример 1. Добавление команд в журнал другого сеанса</span><span class="sxs-lookup"><span data-stu-id="85e7b-120">Example 1: Add commands to the history of a different session</span></span>

<span data-ttu-id="85e7b-121">Этот пример добавляет команды, введенные в один сеанс PowerShell, в журнал другого сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="85e7b-121">This example add the commands typed in one PowerShell session to the history of a different PowerShell session.</span></span>

```powershell
Get-History | Export-Csv c:\testing\history.csv -IncludeTypeInformation
Import-Csv c:\testing\history.csv | Add-History
```

<span data-ttu-id="85e7b-122">Первая команда получает объекты, представляющие команды в журнале, и экспортирует их в `History.csv` файл.</span><span class="sxs-lookup"><span data-stu-id="85e7b-122">The first command gets objects representing the commands in the history and exports them to the `History.csv` file.</span></span>

<span data-ttu-id="85e7b-123">Вторая команда должна вводится в командной строке другого сеанса.</span><span class="sxs-lookup"><span data-stu-id="85e7b-123">The second command is typed at the command line of a different session.</span></span> <span data-ttu-id="85e7b-124">Он использует `Import-Csv` командлет для импорта объектов в `History.csv` файл.</span><span class="sxs-lookup"><span data-stu-id="85e7b-124">It uses the `Import-Csv` cmdlet to import the objects in the `History.csv` file.</span></span> <span data-ttu-id="85e7b-125">Оператор конвейера ( `|` ) передает объекты в `Add-History` командлет, который добавляет объекты, представляющие команды в файле, в `History.csv` текущий журнал сеанса.</span><span class="sxs-lookup"><span data-stu-id="85e7b-125">The pipeline operator (`|`) passes the objects to the `Add-History` cmdlet, which adds the objects representing the commands in the `History.csv` file to the current session history.</span></span>

### <span data-ttu-id="85e7b-126">Пример 2. команды Import и Run</span><span class="sxs-lookup"><span data-stu-id="85e7b-126">Example 2: Import and run commands</span></span>

<span data-ttu-id="85e7b-127">Этот пример импортирует команды из `History.xml` файла, добавляет их в текущий журнал сеанса, а затем выполняет команды в объединенном журнале.</span><span class="sxs-lookup"><span data-stu-id="85e7b-127">This example imports commands from the `History.xml` file, adds them to the current session history, and then runs the commands in the combined history.</span></span>

```powershell
Import-Clixml c:\temp\history.xml | Add-History -PassThru | ForEach-Object -Process {Invoke-History}
```

<span data-ttu-id="85e7b-128">Первая команда использует `Import-Clixml` командлет для импорта журнала команд, экспортированного в `History.xml` файл.</span><span class="sxs-lookup"><span data-stu-id="85e7b-128">The first command uses the `Import-Clixml` cmdlet to import a command history that was exported to the `History.xml` file.</span></span> <span data-ttu-id="85e7b-129">Оператор конвейера передает команды в `Add-History` командлет, который добавляет команды в текущий журнал сеанса.</span><span class="sxs-lookup"><span data-stu-id="85e7b-129">The pipeline operator passes the commands to the `Add-History` cmdlet, which adds the commands to the current session history.</span></span> <span data-ttu-id="85e7b-130">Параметр **PassThru** передает объекты, представляющие добавленные команды, в конвейер.</span><span class="sxs-lookup"><span data-stu-id="85e7b-130">The **PassThru** parameter passes the objects representing the added commands down the pipeline.</span></span>

<span data-ttu-id="85e7b-131">Затем команда использует `ForEach-Object` командлет для применения `Invoke-History` команды к каждой из команд в объединенном журнале.</span><span class="sxs-lookup"><span data-stu-id="85e7b-131">The command then uses the `ForEach-Object` cmdlet to apply the `Invoke-History` command to each of the commands in the combined history.</span></span> <span data-ttu-id="85e7b-132">`Invoke-History`Команда форматируется как блок скрипта, заключенный в фигурные скобки ( `{}` ), как это **Process** требуется параметру Process `ForEach-Object` командлета.</span><span class="sxs-lookup"><span data-stu-id="85e7b-132">The `Invoke-History` command is formatted as a script block, enclosed in braces (`{}`), as required by the **Process** parameter of the `ForEach-Object` cmdlet.</span></span>

### <span data-ttu-id="85e7b-133">Пример 3. Добавление команд в журнал в конец журнала</span><span class="sxs-lookup"><span data-stu-id="85e7b-133">Example 3: Add commands in the history to the end of the history</span></span>

<span data-ttu-id="85e7b-134">В этом примере первые пять команд в журнале добавляются в конец списка журнала.</span><span class="sxs-lookup"><span data-stu-id="85e7b-134">This example adds the first five commands in the history to the end of the history list.</span></span>

```powershell
Get-History -Id 5 -Count 5 | Add-History
```

<span data-ttu-id="85e7b-135">`Get-History`Командлет получает пять команд, которые заканчиваются командой 5.</span><span class="sxs-lookup"><span data-stu-id="85e7b-135">The `Get-History` cmdlet gets the five commands ending in command 5.</span></span> <span data-ttu-id="85e7b-136">Оператор конвейера передает их в `Add-History` командлет, который добавляет их к текущему журналу.</span><span class="sxs-lookup"><span data-stu-id="85e7b-136">The pipeline operator passes them to the `Add-History` cmdlet, which appends them to the current history.</span></span> <span data-ttu-id="85e7b-137">`Add-History`Команда не содержит никаких параметров, но PowerShell связывает объекты, переданные через конвейер, с параметром **InputObject** `Add-History` .</span><span class="sxs-lookup"><span data-stu-id="85e7b-137">The `Add-History` command does not include any parameters, but PowerShell associates the objects passed through the pipeline with the **InputObject** parameter of `Add-History`.</span></span>

### <span data-ttu-id="85e7b-138">Пример 4. Добавление команд в CSV-файл к текущему журналу</span><span class="sxs-lookup"><span data-stu-id="85e7b-138">Example 4: Add commands in a .csv file to the current history</span></span>

<span data-ttu-id="85e7b-139">В этом примере команды добавляются в `History.csv` файл в журнал текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="85e7b-139">This example add the commands in the `History.csv` file to the current session history.</span></span>

```powershell
$a = Import-Csv c:\testing\history.csv
Add-History -InputObject $a -PassThru
```

<span data-ttu-id="85e7b-140">`Import-Csv`Командлет импортирует команды в `History.csv` файл и сохраняет его содержимое в переменной `$a` .</span><span class="sxs-lookup"><span data-stu-id="85e7b-140">The `Import-Csv` cmdlet imports the commands in the `History.csv` file and store its contents in the variable `$a`.</span></span>

<span data-ttu-id="85e7b-141">Вторая команда использует `Add-History` командлет для добавления команд из `History.csv` в текущий журнал сеанса.</span><span class="sxs-lookup"><span data-stu-id="85e7b-141">The second command uses the `Add-History` cmdlet to add the commands from `History.csv` to the current session history.</span></span> <span data-ttu-id="85e7b-142">Он использует параметр **InputObject** для указания `$a` переменной, а параметр **PassThru** — для создания объекта, отображаемого в командной строке.</span><span class="sxs-lookup"><span data-stu-id="85e7b-142">It uses the **InputObject** parameter to specify the `$a` variable and the **PassThru** parameter to generate an object to display at the command line.</span></span> <span data-ttu-id="85e7b-143">Без параметра **PassThru** `Add-History` командлет не создает никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="85e7b-143">Without the **PassThru** parameter, the `Add-History` cmdlet does not generate any output.</span></span>

### <span data-ttu-id="85e7b-144">Пример 5. Добавление команд в XML-файл в текущий журнал</span><span class="sxs-lookup"><span data-stu-id="85e7b-144">Example 5: Add commands in an .xml file to the current history</span></span>

<span data-ttu-id="85e7b-145">В этом примере команды добавляются в `history.xml` файл в журнал текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="85e7b-145">This example adds the commands in the `history.xml` file to the current session history.</span></span>

```powershell
Add-History -InputObject (Import-Clixml c:\temp\history.xml)
```

<span data-ttu-id="85e7b-146">Параметр **InputObject** передает результаты команды в круглые скобки в `Add-History` командлет.</span><span class="sxs-lookup"><span data-stu-id="85e7b-146">The **InputObject** parameter passes the results of the command in parentheses to the `Add-History` cmdlet.</span></span> <span data-ttu-id="85e7b-147">Команда в круглых скобках, которая выполняется в первую очередь, импортирует `history.xml` файл в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="85e7b-147">The command in parentheses, which is executed first, imports the `history.xml` file into PowerShell.</span></span> <span data-ttu-id="85e7b-148">`Add-History`Затем командлет добавляет команды в файл в журнал сеанса.</span><span class="sxs-lookup"><span data-stu-id="85e7b-148">The `Add-History` cmdlet then adds the commands in the file to the session history.</span></span>

## <span data-ttu-id="85e7b-149">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="85e7b-149">PARAMETERS</span></span>

### <span data-ttu-id="85e7b-150">-InputObject</span><span class="sxs-lookup"><span data-stu-id="85e7b-150">-InputObject</span></span>

<span data-ttu-id="85e7b-151">Указывает массив записей для добавления в журнал в качестве объекта **хисторинфо** в журнал сеанса.</span><span class="sxs-lookup"><span data-stu-id="85e7b-151">Specifies an array of entries to add to the history as **HistoryInfo** object to the session history.</span></span>
<span data-ttu-id="85e7b-152">Этот параметр можно использовать для отправки объекта **хисторинфо** , например, тех, которые возвращаются `Get-History` `Import-Clixml` `Import-Csv` командлетами, или, в `Add-History` .</span><span class="sxs-lookup"><span data-stu-id="85e7b-152">You can use this parameter to submit a **HistoryInfo** object, such as the ones that are returned by the `Get-History`, `Import-Clixml`, or `Import-Csv` cmdlets, to `Add-History`.</span></span>

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

### <span data-ttu-id="85e7b-153">-PassThru</span><span class="sxs-lookup"><span data-stu-id="85e7b-153">-Passthru</span></span>

<span data-ttu-id="85e7b-154">Указывает, что этот командлет возвращает объект **хисторинфо** для каждой записи журнала.</span><span class="sxs-lookup"><span data-stu-id="85e7b-154">Indicates that this cmdlet returns a **HistoryInfo** object for each history entry.</span></span> <span data-ttu-id="85e7b-155">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="85e7b-155">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="85e7b-156">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="85e7b-156">CommonParameters</span></span>

<span data-ttu-id="85e7b-157">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="85e7b-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="85e7b-158">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="85e7b-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="85e7b-159">Входные данные</span><span class="sxs-lookup"><span data-stu-id="85e7b-159">INPUTS</span></span>

### <span data-ttu-id="85e7b-160">Microsoft. PowerShell. Commands. Хисторинфо</span><span class="sxs-lookup"><span data-stu-id="85e7b-160">Microsoft.PowerShell.Commands.HistoryInfo</span></span>

<span data-ttu-id="85e7b-161">Объект **хисторинфо** можно передать в этот командлет по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="85e7b-161">You can pipe a **HistoryInfo** object to this cmdlet.</span></span>

## <span data-ttu-id="85e7b-162">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="85e7b-162">OUTPUTS</span></span>

### <span data-ttu-id="85e7b-163">Нет или Microsoft. PowerShell. Commands. Хисторинфо</span><span class="sxs-lookup"><span data-stu-id="85e7b-163">None or Microsoft.PowerShell.Commands.HistoryInfo</span></span>

<span data-ttu-id="85e7b-164">Этот командлет возвращает объект **хисторинфо** , если указан параметр **PassThru** .</span><span class="sxs-lookup"><span data-stu-id="85e7b-164">This cmdlet returns a **HistoryInfo** object if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="85e7b-165">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="85e7b-165">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="85e7b-166">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="85e7b-166">NOTES</span></span>

<span data-ttu-id="85e7b-167">Журнал сеанса — это список команд, вводимых в сеансе вместе с ИДЕНТИФИКАТОРом.</span><span class="sxs-lookup"><span data-stu-id="85e7b-167">The session history is a list of the commands entered during the session together with the ID.</span></span> <span data-ttu-id="85e7b-168">В журнале сеанса представлен порядок выполнения, состояние, время начала и завершения выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="85e7b-168">The session history represents the order of execution, the status, and the start and end times of the command.</span></span> <span data-ttu-id="85e7b-169">По мере ввода каждой команды PowerShell добавляет его в журнал, чтобы его можно было использовать повторно.</span><span class="sxs-lookup"><span data-stu-id="85e7b-169">As you enter each command, PowerShell adds it to the history so that you can reuse it.</span></span> <span data-ttu-id="85e7b-170">Дополнительные сведения о журнале сеанса см. в разделе [about_History](About/about_History.md).</span><span class="sxs-lookup"><span data-stu-id="85e7b-170">For more information about the session history, see [about_History](About/about_History.md).</span></span>

<span data-ttu-id="85e7b-171">Чтобы указать команды, которые нужно добавить в журнал, используйте параметр **InputObject**.</span><span class="sxs-lookup"><span data-stu-id="85e7b-171">To specify the commands to add to the history, use the **InputObject** parameter.</span></span> <span data-ttu-id="85e7b-172">`Add-History`Команда принимает только объекты **хисторинфо** , например, возвращаемые командлетом для каждой команды `Get-History` .</span><span class="sxs-lookup"><span data-stu-id="85e7b-172">The `Add-History` command accepts only **HistoryInfo** objects, such as those returned for each command by the `Get-History` cmdlet.</span></span> <span data-ttu-id="85e7b-173">Передать путь и имя файла или список команд по конвейеру нельзя.</span><span class="sxs-lookup"><span data-stu-id="85e7b-173">You cannot pass it a path and file name or a list of commands.</span></span>

<span data-ttu-id="85e7b-174">Параметр **InputObject** можно использовать для передачи файла **хисторинфо** объектов в `Add-History` .</span><span class="sxs-lookup"><span data-stu-id="85e7b-174">You can use the **InputObject** parameter to pass a file of **HistoryInfo** objects to `Add-History`.</span></span> <span data-ttu-id="85e7b-175">Для этого экспортируйте результаты `Get-History` команды в файл с помощью `Export-Csv` `Export-Clixml` командлета или, а затем импортируйте файл с помощью `Import-Csv` `Import-Clixml` командлетов или.</span><span class="sxs-lookup"><span data-stu-id="85e7b-175">To do so, export the results of a `Get-History` command to a file by using the `Export-Csv` or `Export-Clixml` cmdlet and then import the file by using the `Import-Csv` or `Import-Clixml` cmdlets.</span></span> <span data-ttu-id="85e7b-176">Затем можно передать файл импортированных объектов **хисторинфо** в `Add-History` конвейер или в переменную.</span><span class="sxs-lookup"><span data-stu-id="85e7b-176">You can then pass the file of imported **HistoryInfo** objects to `Add-History` through a pipeline or in a variable.</span></span> <span data-ttu-id="85e7b-177">Дополнительные сведения см. в примерах.</span><span class="sxs-lookup"><span data-stu-id="85e7b-177">For more information, see the examples.</span></span>

<span data-ttu-id="85e7b-178">Файл объектов **хисторинфо** , передаваемый в `Add-History` командлет, должен включать сведения о типе, заголовки столбцов и все свойства объектов **хисторинфо** .</span><span class="sxs-lookup"><span data-stu-id="85e7b-178">The file of **HistoryInfo** objects that you pass to the `Add-History` cmdlet must include the type information, column headings, and all of the properties of the **HistoryInfo** objects.</span></span> <span data-ttu-id="85e7b-179">Если предполагается передать объекты обратно `Add-History` , не используйте параметр **NoTypeInformation** `Export-Csv` командлета и не удаляйте сведения о типе, заголовки столбцов или поля в файле.</span><span class="sxs-lookup"><span data-stu-id="85e7b-179">If you intend to pass the objects back to `Add-History`, do not use the **NoTypeInformation** parameter of the `Export-Csv` cmdlet and do not delete the type information, column headings, or any fields in the file.</span></span>

<span data-ttu-id="85e7b-180">Чтобы изменить журнал сеанса, экспортируйте сеанс в файл CSV или XML, измените файл, импортируйте файл и используйте `Add-History` , чтобы добавить его в текущий журнал сеанса.</span><span class="sxs-lookup"><span data-stu-id="85e7b-180">To modify the session history, export the session to a CSV or XML file, modify the file, import the file, and use `Add-History` to append it to the current session history.</span></span>

## <span data-ttu-id="85e7b-181">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="85e7b-181">RELATED LINKS</span></span>

[<span data-ttu-id="85e7b-182">Clear-History</span><span class="sxs-lookup"><span data-stu-id="85e7b-182">Clear-History</span></span>](Clear-History.md)

[<span data-ttu-id="85e7b-183">Get-History</span><span class="sxs-lookup"><span data-stu-id="85e7b-183">Get-History</span></span>](Get-History.md)

[<span data-ttu-id="85e7b-184">Invoke-History</span><span class="sxs-lookup"><span data-stu-id="85e7b-184">Invoke-History</span></span>](Invoke-History.md)

[<span data-ttu-id="85e7b-185">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="85e7b-185">about_PSReadLine</span></span>](../PSReadLine/About/about_PSReadLine.md)

[<span data-ttu-id="85e7b-186">Get-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="85e7b-186">Get-PSReadLineOption</span></span>](/powershell/module/psreadline/get-psreadlineoption)

[<span data-ttu-id="85e7b-187">Set-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="85e7b-187">Set-PSReadLineOption</span></span>](/powershell/module/psreadline/set-psreadlineoption)
