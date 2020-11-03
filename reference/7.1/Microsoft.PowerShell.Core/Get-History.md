---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 10/06/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-history?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-History
ms.openlocfilehash: 0c5e55d3f1bcc6d988b54a8747173d88acbdec35
ms.sourcegitcommit: 1695df0d241c0390cac71a7401e61198fc6ff756
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/06/2020
ms.locfileid: "93230741"
---
# <span data-ttu-id="f0277-103">Get-History</span><span class="sxs-lookup"><span data-stu-id="f0277-103">Get-History</span></span>

## <span data-ttu-id="f0277-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="f0277-104">SYNOPSIS</span></span>
<span data-ttu-id="f0277-105">Возвращает список команд, введенных во время текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="f0277-105">Gets a list of the commands entered during the current session.</span></span>

## <span data-ttu-id="f0277-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f0277-106">SYNTAX</span></span>

```
Get-History [[-Id] <Int64[]>] [[-Count] <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="f0277-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f0277-107">DESCRIPTION</span></span>

<span data-ttu-id="f0277-108">`Get-History`Командлет возвращает журнал сеанса, то есть список команд, вводимых в текущем сеансе.</span><span class="sxs-lookup"><span data-stu-id="f0277-108">The `Get-History` cmdlet gets the session history, that is, the list of commands entered during the current session.</span></span>

<span data-ttu-id="f0277-109">PowerShell автоматически поддерживает журнал каждого сеанса.</span><span class="sxs-lookup"><span data-stu-id="f0277-109">PowerShell automatically maintains a history of each session.</span></span> <span data-ttu-id="f0277-110">Число записей в журнале сеанса определяется значением `$MaximumHistoryCount` привилегированной переменной.</span><span class="sxs-lookup"><span data-stu-id="f0277-110">The number of entries in the session history is determined by the value of the `$MaximumHistoryCount` preference variable.</span></span> <span data-ttu-id="f0277-111">Начиная с Windows PowerShell 3,0, значение по умолчанию — `4096` .</span><span class="sxs-lookup"><span data-stu-id="f0277-111">Beginning in Windows PowerShell 3.0, the default value is `4096`.</span></span> <span data-ttu-id="f0277-112">По умолчанию файлы журнала сохраняются в домашнем каталоге, но вы можете сохранить файл в любом месте.</span><span class="sxs-lookup"><span data-stu-id="f0277-112">By default, history files are saved in the home directory, but you can save the file in any location.</span></span> <span data-ttu-id="f0277-113">Дополнительные сведения о функциях журнала в PowerShell см. в разделе [about_History](About/about_History.md).</span><span class="sxs-lookup"><span data-stu-id="f0277-113">For more information about the history features in PowerShell, see [about_History](About/about_History.md).</span></span>

<span data-ttu-id="f0277-114">Журнал сеанса управляется отдельно от журнала, поддерживаемого модулем **PSReadLine** .</span><span class="sxs-lookup"><span data-stu-id="f0277-114">The session history is managed separately from the history maintained by the **PSReadLine** module.</span></span>
<span data-ttu-id="f0277-115">Оба журнала доступны в сеансах, где загружен **PSReadLine** .</span><span class="sxs-lookup"><span data-stu-id="f0277-115">Both histories are available in sessions where **PSReadLine** is loaded.</span></span> <span data-ttu-id="f0277-116">Этот командлет работает только с журналом сеанса.</span><span class="sxs-lookup"><span data-stu-id="f0277-116">This cmdlet only works with the session history.</span></span> <span data-ttu-id="f0277-117">Дополнительные сведения см. в разделе [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).</span><span class="sxs-lookup"><span data-stu-id="f0277-117">For more information see, [about_PSReadLine](../PSReadLine/About/about_PSReadLine.md).</span></span>

## <span data-ttu-id="f0277-118">Примеры</span><span class="sxs-lookup"><span data-stu-id="f0277-118">EXAMPLES</span></span>

### <span data-ttu-id="f0277-119">Пример 1. Получение журнала сеанса</span><span class="sxs-lookup"><span data-stu-id="f0277-119">Example 1: Get the session history</span></span>

<span data-ttu-id="f0277-120">Этот пример возвращает записи в журнале сеанса.</span><span class="sxs-lookup"><span data-stu-id="f0277-120">This example gets the entries in the session history.</span></span> <span data-ttu-id="f0277-121">По умолчанию отображается каждая команда и ее идентификатор, который указывает порядок их запуска.</span><span class="sxs-lookup"><span data-stu-id="f0277-121">The default display shows each command and its ID, which indicates the order in which they ran.</span></span>

```powershell
Get-History
```

### <span data-ttu-id="f0277-122">Пример 2. получение записей, содержащих строку</span><span class="sxs-lookup"><span data-stu-id="f0277-122">Example 2: Get entries that include a string</span></span>

<span data-ttu-id="f0277-123">Этот пример получает записи в журнале команд, которые включают в себя службу String.</span><span class="sxs-lookup"><span data-stu-id="f0277-123">This example gets entries in the command history that include the string service.</span></span> <span data-ttu-id="f0277-124">Первая команда возвращает все записи из журнала сеанса.</span><span class="sxs-lookup"><span data-stu-id="f0277-124">The first command gets all entries in the session history.</span></span> <span data-ttu-id="f0277-125">Оператор конвейера ( `|` ) передает результаты в `Where-Object` командлет, который выбирает только команды, включающие службу.</span><span class="sxs-lookup"><span data-stu-id="f0277-125">The pipeline operator (`|`) passes the results to the `Where-Object` cmdlet, which selects only the commands that include service.</span></span>

```powershell
Get-History | Where-Object {$_.CommandLine -like "*Service*"}
```

### <span data-ttu-id="f0277-126">Пример 3. Экспорт записей журнала по указанному ИДЕНТИФИКАТОРу</span><span class="sxs-lookup"><span data-stu-id="f0277-126">Example 3: Export history entries up to a specific ID</span></span>

<span data-ttu-id="f0277-127">Этот пример получает пять последних записей журнала, оканчивающихся записью 7.</span><span class="sxs-lookup"><span data-stu-id="f0277-127">This example gets the five most recent history entries ending with entry 7.</span></span> <span data-ttu-id="f0277-128">Оператор конвейера передает результат в `Export-Csv` командлет, который форматирует журнал в виде текста с разделителями-запятыми и сохраняет его в файле History.csv.</span><span class="sxs-lookup"><span data-stu-id="f0277-128">The pipeline operator passes the result to the `Export-Csv` cmdlet, which formats the history as comma-separated text and saves it in the History.csv file.</span></span> <span data-ttu-id="f0277-129">Файл содержит данные, которые отображаются при форматировании журнала в виде списка.</span><span class="sxs-lookup"><span data-stu-id="f0277-129">The file includes the data that is displayed when you format the history as a list.</span></span> <span data-ttu-id="f0277-130">Сюда входят состояние и время начала и окончания выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="f0277-130">This includes the status and start and end times of the command.</span></span>

```powershell
Get-History -ID 7 -Count 5 | Export-Csv History.csv
```

### <span data-ttu-id="f0277-131">Пример 4. Отображение последней команды</span><span class="sxs-lookup"><span data-stu-id="f0277-131">Example 4: Display the most recent command</span></span>

<span data-ttu-id="f0277-132">В этом примере возвращается последняя команда в журнале команд.</span><span class="sxs-lookup"><span data-stu-id="f0277-132">This example gets the last command in the command history.</span></span> <span data-ttu-id="f0277-133">Последняя команда является самой последней командой.</span><span class="sxs-lookup"><span data-stu-id="f0277-133">The last command is the most recently entered command.</span></span> <span data-ttu-id="f0277-134">Эта команда использует параметр **Count** для вывода всего одной команды.</span><span class="sxs-lookup"><span data-stu-id="f0277-134">This command uses the **Count** parameter to display just one command.</span></span> <span data-ttu-id="f0277-135">По умолчанию `Get-History` возвращает самые последние команды.</span><span class="sxs-lookup"><span data-stu-id="f0277-135">By default, `Get-History` gets the most recent commands.</span></span> <span data-ttu-id="f0277-136">Эту команду можно сократить до "h -c 1", и она эквивалентна нажатию клавиши со стрелкой вверх.</span><span class="sxs-lookup"><span data-stu-id="f0277-136">This command can be abbreviated to "h -c 1" and is equivalent to pressing the up-arrow key.</span></span>

```powershell
Get-History -Count 1
```

### <span data-ttu-id="f0277-137">Пример 5. Отображение всех свойств записей в журнале</span><span class="sxs-lookup"><span data-stu-id="f0277-137">Example 5: Display all the properties of the entries in the history</span></span>

<span data-ttu-id="f0277-138">В этом примере отображаются все свойства записей в журнале сеанса.</span><span class="sxs-lookup"><span data-stu-id="f0277-138">This example displays all of the properties of entries in the session history.</span></span> <span data-ttu-id="f0277-139">Оператор конвейера передает результаты `Get-History` команды в `Format-List` командлет, который отображает все свойства каждой записи журнала.</span><span class="sxs-lookup"><span data-stu-id="f0277-139">The pipeline operator passes the results of a `Get-History` command to the `Format-List` cmdlet, which displays all of the properties of each history entry.</span></span> <span data-ttu-id="f0277-140">Сюда входят идентификатор, состояние и время начала и окончания команды.</span><span class="sxs-lookup"><span data-stu-id="f0277-140">This includes the ID, status, and start and end times of the command.</span></span>

```powershell
Get-History | Format-List -Property *
```

## <span data-ttu-id="f0277-141">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f0277-141">PARAMETERS</span></span>

### <span data-ttu-id="f0277-142">— Количество</span><span class="sxs-lookup"><span data-stu-id="f0277-142">-Count</span></span>

<span data-ttu-id="f0277-143">Указывает количество последних записей журнала, которые получает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="f0277-143">Specifies the number of the most recent history entries that this cmdlet gets.</span></span> <span data-ttu-id="f0277-144">По умолчанию `Get-History` получает все записи в журнале сеанса.</span><span class="sxs-lookup"><span data-stu-id="f0277-144">By, default, `Get-History` gets all entries in the session history.</span></span> <span data-ttu-id="f0277-145">Если в команде используются оба параметра **Count** и **Id** , последней выводится команда, указанная в параметре **Id** .</span><span class="sxs-lookup"><span data-stu-id="f0277-145">If you use both the **Count** and **Id** parameters in a command, the display ends with the command that is specified by the **Id** parameter.</span></span>

<span data-ttu-id="f0277-146">В Windows PowerShell 2,0 по умолчанию `Get-History` возвращает 32 последних записей.</span><span class="sxs-lookup"><span data-stu-id="f0277-146">In Windows PowerShell 2.0, by default, `Get-History` gets the 32 most recent entries.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f0277-147">-Id</span><span class="sxs-lookup"><span data-stu-id="f0277-147">-Id</span></span>

<span data-ttu-id="f0277-148">Указывает массив идентификаторов записей в журнале сеанса.</span><span class="sxs-lookup"><span data-stu-id="f0277-148">Specifies an array of the IDs of entries in the session history.</span></span> <span data-ttu-id="f0277-149">`Get-History` Возвращает только указанные записи.</span><span class="sxs-lookup"><span data-stu-id="f0277-149">`Get-History` gets only specified entries.</span></span> <span data-ttu-id="f0277-150">Если в команде используются оба параметра **ID** и **Count** , `Get-History` получает последние записи, которые заканчиваются записью, заданной параметром **ID** .</span><span class="sxs-lookup"><span data-stu-id="f0277-150">If you use both the **Id** and **Count** parameters in a command, `Get-History` gets the most recent entries ending with the entry specified by the **Id** parameter.</span></span>

```yaml
Type: System.Int64[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="f0277-151">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="f0277-151">CommonParameters</span></span>

<span data-ttu-id="f0277-152">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f0277-152">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f0277-153">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f0277-153">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f0277-154">Входные данные</span><span class="sxs-lookup"><span data-stu-id="f0277-154">INPUTS</span></span>

### <span data-ttu-id="f0277-155">System.Int64</span><span class="sxs-lookup"><span data-stu-id="f0277-155">System.Int64</span></span>

<span data-ttu-id="f0277-156">ИДЕНТИФИКАТОР журнала можно передать в этот командлет по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="f0277-156">You can pipe a history ID to this cmdlet.</span></span>

## <span data-ttu-id="f0277-157">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="f0277-157">OUTPUTS</span></span>

### <span data-ttu-id="f0277-158">Microsoft. PowerShell. Commands. Хисторинфо</span><span class="sxs-lookup"><span data-stu-id="f0277-158">Microsoft.PowerShell.Commands.HistoryInfo</span></span>

<span data-ttu-id="f0277-159">Этот командлет возвращает объект журнала для каждого элемента журнала, который он получает.</span><span class="sxs-lookup"><span data-stu-id="f0277-159">This cmdlet returns a history object for each history item that it gets.</span></span>

## <span data-ttu-id="f0277-160">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="f0277-160">NOTES</span></span>

<span data-ttu-id="f0277-161">Журнал сеанса — это список команд, введенных за время сеанса.</span><span class="sxs-lookup"><span data-stu-id="f0277-161">The session history is a list of the commands entered during the session.</span></span> <span data-ttu-id="f0277-162">Журнал сеанса представляет собой порядок выполнения, состояние и время начала и окончания команды.</span><span class="sxs-lookup"><span data-stu-id="f0277-162">The session history represents the run order, the status, and the start and end times of the command.</span></span> <span data-ttu-id="f0277-163">По мере ввода каждой команды PowerShell добавляет его в журнал, чтобы его можно было использовать повторно.</span><span class="sxs-lookup"><span data-stu-id="f0277-163">As you enter each command, PowerShell adds it to the history so that you can reuse it.</span></span> <span data-ttu-id="f0277-164">Дополнительные сведения о журнале команд см. в разделе [about_History](About/about_History.md).</span><span class="sxs-lookup"><span data-stu-id="f0277-164">For more information about the command history, see [about_History](About/about_History.md).</span></span>

<span data-ttu-id="f0277-165">Начиная с Windows PowerShell 3,0, значением по умолчанию для `$MaximumHistoryCount` привилегированной переменной является `4096` .</span><span class="sxs-lookup"><span data-stu-id="f0277-165">Starting in Windows PowerShell 3.0, the default value of the `$MaximumHistoryCount` preference variable is `4096`.</span></span> <span data-ttu-id="f0277-166">В Windows PowerShell 2,0 значение по умолчанию — `64` .</span><span class="sxs-lookup"><span data-stu-id="f0277-166">In Windows PowerShell 2.0, the default value is `64`.</span></span> <span data-ttu-id="f0277-167">Дополнительные сведения о `$MaximumHistoryCount` переменной см. в разделе [about_Preference_Variables](About/about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="f0277-167">For more information about the `$MaximumHistoryCount` variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

## <span data-ttu-id="f0277-168">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="f0277-168">RELATED LINKS</span></span>

[<span data-ttu-id="f0277-169">Add-History</span><span class="sxs-lookup"><span data-stu-id="f0277-169">Add-History</span></span>](Add-History.md)

[<span data-ttu-id="f0277-170">Clear-History</span><span class="sxs-lookup"><span data-stu-id="f0277-170">Clear-History</span></span>](Clear-History.md)

[<span data-ttu-id="f0277-171">Invoke-History</span><span class="sxs-lookup"><span data-stu-id="f0277-171">Invoke-History</span></span>](Invoke-History.md)

[<span data-ttu-id="f0277-172">about_History</span><span class="sxs-lookup"><span data-stu-id="f0277-172">about_History</span></span>](About/about_History.md)
