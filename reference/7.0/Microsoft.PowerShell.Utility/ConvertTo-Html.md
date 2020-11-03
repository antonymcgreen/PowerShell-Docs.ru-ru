---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-html?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-Html
ms.openlocfilehash: 21ef51476ccee8efc5c7c13d273ef8a7811f33c4
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2020
ms.locfileid: "93230297"
---
# <span data-ttu-id="7d75d-103">ConvertTo-Html</span><span class="sxs-lookup"><span data-stu-id="7d75d-103">ConvertTo-Html</span></span>

## <span data-ttu-id="7d75d-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="7d75d-104">SYNOPSIS</span></span>
<span data-ttu-id="7d75d-105">Преобразует объекты .NET в код HTML, который может отображаться в веб-браузере.</span><span class="sxs-lookup"><span data-stu-id="7d75d-105">Converts .NET objects into HTML that can be displayed in a Web browser.</span></span>

## <span data-ttu-id="7d75d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7d75d-106">SYNTAX</span></span>

### <span data-ttu-id="7d75d-107">Страница (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="7d75d-107">Page (Default)</span></span>

```
ConvertTo-Html [-InputObject <PSObject>] [[-Property] <Object[]>] [[-Body] <String[]>]
 [[-Head] <String[]>] [[-Title] <String>] [-As <String>] [-CssUri <Uri>] [-PostContent <String[]>]
 [-PreContent <String[]>] [-Meta <Hashtable>] [-Charset <String>] [-Transitional]
 [<CommonParameters>]
```

### <span data-ttu-id="7d75d-108">Fragment</span><span class="sxs-lookup"><span data-stu-id="7d75d-108">Fragment</span></span>

```
ConvertTo-Html [-InputObject <PSObject>] [[-Property] <Object[]>] [-As <String>] [-Fragment]
 [-PostContent <String[]>] [-PreContent <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="7d75d-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7d75d-109">DESCRIPTION</span></span>

<span data-ttu-id="7d75d-110">`ConvertTo-Html`Командлет преобразует объекты .NET в формат HTML, который может отображаться в веб-браузере.</span><span class="sxs-lookup"><span data-stu-id="7d75d-110">The `ConvertTo-Html` cmdlet converts .NET objects into HTML that can be displayed in a Web browser.</span></span> <span data-ttu-id="7d75d-111">Этот командлет можно использовать для отображения выходных данных команды на веб-странице.</span><span class="sxs-lookup"><span data-stu-id="7d75d-111">You can use this cmdlet to display the output of a command in a Web page.</span></span>

<span data-ttu-id="7d75d-112">С помощью параметров можно `ConvertTo-Html` выбрать свойства объекта, указать формат таблицы или списка, указать заголовок HTML-страницы, добавить текст до и после объекта, а также вернуть только фрагмент таблицы или списка, а не определенную страницу DTD.</span><span class="sxs-lookup"><span data-stu-id="7d75d-112">You can use the parameters of `ConvertTo-Html` to select object properties, to specify a table or list format, to specify the HTML page title, to add text before and after the object, and to return only the table or list fragment, instead of a strict DTD page.</span></span>

<span data-ttu-id="7d75d-113">При отправке нескольких объектов в `ConvertTo-Html` PowerShell создает таблицу (или список) на основе свойств первого отправленного объекта.</span><span class="sxs-lookup"><span data-stu-id="7d75d-113">When you submit multiple objects to `ConvertTo-Html`, PowerShell creates the table (or list) based on the properties of the first object that you submit.</span></span> <span data-ttu-id="7d75d-114">Если у оставшихся объектов нет одного из указанных свойств, значением свойства этого объекта является пустая ячейка.</span><span class="sxs-lookup"><span data-stu-id="7d75d-114">If the remaining objects do not have one of the specified properties, the property value of that object is an empty cell.</span></span> <span data-ttu-id="7d75d-115">Если оставшиеся объекты содержат дополнительные свойства, их значения не включаются в файл.</span><span class="sxs-lookup"><span data-stu-id="7d75d-115">If the remaining objects have additional properties, those property values are not included in the file.</span></span>

## <span data-ttu-id="7d75d-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="7d75d-116">EXAMPLES</span></span>

### <span data-ttu-id="7d75d-117">Пример 1. Создание веб-страницы для вывода даты</span><span class="sxs-lookup"><span data-stu-id="7d75d-117">Example 1: Create a web page to display the date</span></span>

```powershell
ConvertTo-Html -InputObject (Get-Date)
```

<span data-ttu-id="7d75d-118">Эта команда создает HTML-страницу, на которой отображаются свойства текущей даты.</span><span class="sxs-lookup"><span data-stu-id="7d75d-118">This command creates an HTML page that displays the properties of the current date.</span></span> <span data-ttu-id="7d75d-119">Он использует параметр **InputObject** для отправки результатов `Get-Date` команды в `ConvertTo-Html` командлет.</span><span class="sxs-lookup"><span data-stu-id="7d75d-119">It uses the **InputObject** parameter to submit the results of a `Get-Date` command to the `ConvertTo-Html` cmdlet.</span></span>

### <span data-ttu-id="7d75d-120">Пример 2. Создание веб-страницы для вывода псевдонимов PowerShell</span><span class="sxs-lookup"><span data-stu-id="7d75d-120">Example 2: Create a web page to display PowerShell aliases</span></span>

```powershell
Get-Alias | ConvertTo-Html | Out-File aliases.htm
Invoke-Item aliases.htm
```

<span data-ttu-id="7d75d-121">Эта команда создает HTML-страницу, в которой перечислены псевдонимы PowerShell в текущей консоли.</span><span class="sxs-lookup"><span data-stu-id="7d75d-121">This command creates an HTML page that lists the PowerShell aliases in the current console.</span></span>

<span data-ttu-id="7d75d-122">Команда использует `Get-Alias` командлет для получения псевдонимов.</span><span class="sxs-lookup"><span data-stu-id="7d75d-122">The command uses the `Get-Alias` cmdlet to get the aliases.</span></span> <span data-ttu-id="7d75d-123">Он использует оператор конвейера ( `|` ) для отправки псевдонимов в `ConvertTo-Html` командлет, который создает HTML-страницу.</span><span class="sxs-lookup"><span data-stu-id="7d75d-123">It uses the pipeline operator (`|`) to send the aliases to the `ConvertTo-Html` cmdlet, which creates the HTML page.</span></span> <span data-ttu-id="7d75d-124">Команда также использует `Out-File` командлет для отправки HTML-кода в `aliases.htm` файл.</span><span class="sxs-lookup"><span data-stu-id="7d75d-124">The command also uses the `Out-File` cmdlet to send the HTML code to the `aliases.htm` file.</span></span>

### <span data-ttu-id="7d75d-125">Пример 3. Создание веб-страницы для вывода событий PowerShell</span><span class="sxs-lookup"><span data-stu-id="7d75d-125">Example 3: Create a web page to display PowerShell events</span></span>

```powershell
`Get-EventLog` -LogName "Windows PowerShell" | ConvertTo-Html | Out-File pslog.htm
```

<span data-ttu-id="7d75d-126">Эта команда создает HTML-страницу `pslog.htm` с именем, которая отображает события в журнале событий Windows PowerShell на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="7d75d-126">This command creates an HTML page called `pslog.htm` that displays the events in the Windows PowerShell event log on the local computer.</span></span>

<span data-ttu-id="7d75d-127">Он использует `Get-EventLog` командлет для получения событий в журнале Windows PowerShell, а затем использует оператор конвейера ( `|` ) для отправки событий в `ConvertTo-Html` командлет.</span><span class="sxs-lookup"><span data-stu-id="7d75d-127">It uses the `Get-EventLog` cmdlet to get the events in the Windows PowerShell log and then uses the pipeline operator (`|`) to send the events to the `ConvertTo-Html` cmdlet.</span></span> <span data-ttu-id="7d75d-128">Команда также использует `Out-File` командлет для отправки HTML-кода в `pslog.htm` файл.</span><span class="sxs-lookup"><span data-stu-id="7d75d-128">The command also uses the `Out-File` cmdlet to send the HTML code to the `pslog.htm` file.</span></span>

<span data-ttu-id="7d75d-129">Команда также использует `Out-File` командлет для отправки HTML-кода в `pslog.htm` файл.</span><span class="sxs-lookup"><span data-stu-id="7d75d-129">The command also uses the `Out-File` cmdlet to send the HTML code to the `pslog.htm` file.</span></span>

### <span data-ttu-id="7d75d-130">Пример 4. Создание веб-страницы для показа процессов</span><span class="sxs-lookup"><span data-stu-id="7d75d-130">Example 4: Create a web page to display processes</span></span>

```powershell
Get-Process |
  ConvertTo-Html -Property Name, Path, Company -Title "Process Information" |
    Out-File proc.htm
Invoke-Item proc.htm
```

<span data-ttu-id="7d75d-131">Эти команды создают и открывают HTML-страницу, содержащую имя, путь и компанию для процессов на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="7d75d-131">These commands create and open an HTML page that lists the name, path, and company of the processes on the local computer.</span></span>

<span data-ttu-id="7d75d-132">Первая команда использует `Get-Process` командлет для получения объектов, представляющих процессы, запущенные на компьютере.</span><span class="sxs-lookup"><span data-stu-id="7d75d-132">The first command uses the `Get-Process` cmdlet to get objects that represent the processes running on the computer.</span></span> <span data-ttu-id="7d75d-133">Команда использует оператор конвейера ( `|` ) для отправки объектов процесса в `ConvertTo-Html` командлет.</span><span class="sxs-lookup"><span data-stu-id="7d75d-133">The command uses the pipeline operator (`|`) to send the process objects to the `ConvertTo-Html` cmdlet.</span></span>

<span data-ttu-id="7d75d-134">Команда использует параметр **Property** для выбора трех свойств объектов процесса, которые должны быть добавлены в таблицу.</span><span class="sxs-lookup"><span data-stu-id="7d75d-134">The command uses the **Property** parameter to select three properties of the process objects to be included in the table.</span></span> <span data-ttu-id="7d75d-135">Команда использует параметр **Title** для указания заголовка HTML-страницы.</span><span class="sxs-lookup"><span data-stu-id="7d75d-135">The command uses the **Title** parameter to specify a title for the HTML page.</span></span> <span data-ttu-id="7d75d-136">Команда также использует `Out-File` командлет для отправки полученного HTML-кода в файл с именем Proc.htm.</span><span class="sxs-lookup"><span data-stu-id="7d75d-136">The command also uses the `Out-File` cmdlet to send the resulting HTML to a file named Proc.htm.</span></span>

<span data-ttu-id="7d75d-137">Вторая команда использует `Invoke-Item` командлет для открытия в `Proc.htm` браузере по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7d75d-137">The second command uses the `Invoke-Item` cmdlet to open the `Proc.htm` in the default browser.</span></span>

### <span data-ttu-id="7d75d-138">Пример 5. Создание веб-страницы для вывода объектов службы</span><span class="sxs-lookup"><span data-stu-id="7d75d-138">Example 5: Create a web page to display service objects</span></span>

```powershell
Get-Service | ConvertTo-Html -CssUri "test.css"
```

```Output
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN"  "https://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">
<html>
<head>
<title>HTML TABLE</title>
<link rel="stylesheet" type="text/css" href="test.css" />
...
```

<span data-ttu-id="7d75d-139">Эта команда создает HTML-страницу объектов службы, `Get-Service` возвращаемых командлетом.</span><span class="sxs-lookup"><span data-stu-id="7d75d-139">This command creates an HTML page of the service objects that the `Get-Service` cmdlet returns.</span></span> <span data-ttu-id="7d75d-140">Команда использует параметр **кссури** для указания каскадной таблицы стилей для HTML-страницы.</span><span class="sxs-lookup"><span data-stu-id="7d75d-140">The command uses the **CssUri** parameter to specify a cascading style sheet for the HTML page.</span></span>

<span data-ttu-id="7d75d-141">Параметр **кссури** добавляет дополнительный `<link rel="stylesheet" type="text/css" href="test.css">` тег в результирующий HTML-код.</span><span class="sxs-lookup"><span data-stu-id="7d75d-141">The **CssUri** parameter adds an additional `<link rel="stylesheet" type="text/css" href="test.css">` tag to the resulting HTML.</span></span> <span data-ttu-id="7d75d-142">Атрибут HREF в теге содержит имя таблицы стилей.</span><span class="sxs-lookup"><span data-stu-id="7d75d-142">The HREF attribute in the tag contains the name of the style sheet.</span></span>

### <span data-ttu-id="7d75d-143">Пример 6. Создание веб-страницы для вывода объектов службы</span><span class="sxs-lookup"><span data-stu-id="7d75d-143">Example 6: Create a web page to display service objects</span></span>

```powershell
Get-Service | ConvertTo-Html -As LIST | Out-File services.htm
```

<span data-ttu-id="7d75d-144">Эта команда создает HTML-страницу объектов службы, `Get-Service` возвращаемых командлетом.</span><span class="sxs-lookup"><span data-stu-id="7d75d-144">This command creates an HTML page of the service objects that the `Get-Service` cmdlet returns.</span></span> <span data-ttu-id="7d75d-145">Команда использует параметр **as** для задания формата списка.</span><span class="sxs-lookup"><span data-stu-id="7d75d-145">The command uses the **As** parameter to specify a list format.</span></span> <span data-ttu-id="7d75d-146">Командлет `Out-File` отправляет полученный HTML-код в `Services.htm` файл.</span><span class="sxs-lookup"><span data-stu-id="7d75d-146">The cmdlet `Out-File` sends the resulting HTML to the `Services.htm` file.</span></span>

### <span data-ttu-id="7d75d-147">Пример 7. Создание веб-таблицы для текущей даты</span><span class="sxs-lookup"><span data-stu-id="7d75d-147">Example 7: Create a web table for the current date</span></span>

```powershell
Get-Date | ConvertTo-Html -Fragment
```

```Output
<table>
<colgroup>...</colgroup>
<tr><th>DisplayHint</th><th>DateTime</th><th>Date</th><th>Day</th><th>DayOfWeek</th><th>DayOfYear</th><th>Hour</th>
<th>Kind</th><th>Millisecond</th><th>Minute</th><th>Month</th><th>Second</th><th>Ticks</th><th>TimeOfDay</th><th>Year</th></tr>
<tr><td>DateTime</td><td>Monday, May 05, 2008 10:40:04 AM</td><td>5/5/2008 12:00:00 AM</td><td>5</td><td>Monday</td>
<td>126</td><td>10</td><td>Local</td><td>123</td><td>40</td><td>5</td><td>4</td><td>633455808041237213</td><td>10:40:04.12
37213</td><td>2008</td></tr>
</table>
```

<span data-ttu-id="7d75d-148">Эта команда использует `ConvertTo-Html` для создания HTML-таблицы текущей даты.</span><span class="sxs-lookup"><span data-stu-id="7d75d-148">This command uses `ConvertTo-Html` to generate an HTML table of the current date.</span></span> <span data-ttu-id="7d75d-149">Команда использует `Get-Date` командлет для получения текущей даты.</span><span class="sxs-lookup"><span data-stu-id="7d75d-149">The command uses the `Get-Date` cmdlet to get the current date.</span></span> <span data-ttu-id="7d75d-150">Для отправки результатов в командлет используется оператор конвейера (|) `ConvertTo-Html` .</span><span class="sxs-lookup"><span data-stu-id="7d75d-150">It uses a pipeline operator (|) to send the results to the `ConvertTo-Html` cmdlet.</span></span>

<span data-ttu-id="7d75d-151">`ConvertTo-Html`Команда включает параметр **Fragment** , который ограничивает выходные данные HTML-таблицей.</span><span class="sxs-lookup"><span data-stu-id="7d75d-151">The `ConvertTo-Html` command includes the **Fragment** parameter, which limits the output to an HTML table.</span></span> <span data-ttu-id="7d75d-152">В результате другие элементы HTML-страницы, например теги `<HEAD>` и `<BODY>`, пропускаются.</span><span class="sxs-lookup"><span data-stu-id="7d75d-152">As a result, the other elements of an HTML page, such as the `<HEAD>` and `<BODY>` tags, are omitted.</span></span>

### <span data-ttu-id="7d75d-153">Пример 8. Создание веб-страницы для вывода событий PowerShell</span><span class="sxs-lookup"><span data-stu-id="7d75d-153">Example 8: Create a web page to display PowerShell events</span></span>

```powershell
Get-EventLog -Log "Windows PowerShell" | ConvertTo-Html -Property id, level, task
```

<span data-ttu-id="7d75d-154">Эта команда использует `Get-EventLog` командлет для получения событий из журнала событий Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7d75d-154">This command uses the `Get-EventLog` cmdlet to get events from the Windows PowerShell event log.</span></span>

<span data-ttu-id="7d75d-155">Он использует оператор конвейера ( `|` ) для отправки событий в `ConvertTo-Html` командлет, который преобразует события в формат HTML.</span><span class="sxs-lookup"><span data-stu-id="7d75d-155">It uses a pipeline operator (`|`) to send the events to the `ConvertTo-Html` cmdlet, which converts the events to HTML format.</span></span>

<span data-ttu-id="7d75d-156">`ConvertTo-Html`Команда использует параметр **Property** для выбора только свойств **ID** , **Level** и **Task** события.</span><span class="sxs-lookup"><span data-stu-id="7d75d-156">The `ConvertTo-Html` command uses the **Property** parameter to select only the **ID** , **Level** , and **Task** properties of the event.</span></span>

### <span data-ttu-id="7d75d-157">Пример 9. Создание веб-страницы для показа указанных служб</span><span class="sxs-lookup"><span data-stu-id="7d75d-157">Example 9: Create a web page to display specified services</span></span>

```powershell
$htmlParams = @{
  Title = "Windows Services: Server01"
  Body = Get-Date
  PreContent = "<P>Generated by Corporate IT</P>"
  PostContent = "For details, contact Corporate IT."
}
Get-Service A* |
  ConvertTo-Html @htmlParams |
    Out-File Services.htm
Invoke-Item Services.htm
```

<span data-ttu-id="7d75d-158">Эта команда создает и открывает веб-страницу, в которой отображаются службы на компьютере, начинающиеся с. Для настройки выходных данных в нем используются параметры **Title** , **Body** , for **Content** и My **Content** `ConvertTo-Html` .</span><span class="sxs-lookup"><span data-stu-id="7d75d-158">This command creates and opens a Web page that displays the services on the computer that begin with A. It uses the **Title** , **Body** , **PreContent** , and **PostContent** parameters of `ConvertTo-Html` to customize the output.</span></span>

<span data-ttu-id="7d75d-159">Первая часть команды использует `Get-Service` командлет для получения служб на компьютере, который начинается с. Команда использует оператор конвейера ( `|` ) для отправки результатов в `ConvertTo-Html` командлет.</span><span class="sxs-lookup"><span data-stu-id="7d75d-159">The first part of the command uses the `Get-Service` cmdlet to get the services on the computer that begin with A. The command uses a pipeline operator (`|`) to send the results to the `ConvertTo-Html` cmdlet.</span></span> <span data-ttu-id="7d75d-160">Команда также использует `Out-File` командлет для отправки выходных данных в файл Services.htm.</span><span class="sxs-lookup"><span data-stu-id="7d75d-160">The command also uses the `Out-File` cmdlet to send the output to the Services.htm file.</span></span>

<span data-ttu-id="7d75d-161">Точка с запятой ( `;` ) завершает первую команду и запускает вторую команду, которая использует `Invoke-Item` командлет для открытия `Services.htm` файла в браузере по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7d75d-161">A semicolon (`;`) ends the first command and starts a second command, which uses the `Invoke-Item` cmdlet to open the `Services.htm` file in the default browser.</span></span>

### <span data-ttu-id="7d75d-162">Пример 10. Задание свойств meta и charset HTML</span><span class="sxs-lookup"><span data-stu-id="7d75d-162">Example 10: Set the Meta properties and Charset of the HTML</span></span>

```powershell
Get-Service | ConvertTo-HTML -Meta @{
  refresh=10
  author="Author's Name"
  keywords="PowerShell, HTML, ConvertTo-HTML"
} -Charset "UTF-8"
```

<span data-ttu-id="7d75d-163">Эта команда создает HTML для веб-страницы с тегами meta для обновления, создания и ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="7d75d-163">This command creates the HTML for a webpage with the meta tags for refresh, author, and keywords.</span></span>
<span data-ttu-id="7d75d-164">Кодировка для страницы равна UTF-8</span><span class="sxs-lookup"><span data-stu-id="7d75d-164">The charset for the page is set to UTF-8</span></span>

### <span data-ttu-id="7d75d-165">Пример 11. Настройка переходного формата HTML в формат XHTML</span><span class="sxs-lookup"><span data-stu-id="7d75d-165">Example 11: Set the HTML to XHTML Transitional DTD</span></span>

```powershell
Get-Service | ConvertTo-HTML -Transitional
```

<span data-ttu-id="7d75d-166">Эта команда устанавливает DOCTYPE возвращаемого HTML-кода в XHTML Transitional DTD</span><span class="sxs-lookup"><span data-stu-id="7d75d-166">This command sets the DOCTYPE of the returned HTML to XHTML Transitional DTD</span></span>

## <span data-ttu-id="7d75d-167">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7d75d-167">PARAMETERS</span></span>

### <span data-ttu-id="7d75d-168">— Как</span><span class="sxs-lookup"><span data-stu-id="7d75d-168">-As</span></span>

<span data-ttu-id="7d75d-169">Определяет, форматируется ли объект как таблица или список.</span><span class="sxs-lookup"><span data-stu-id="7d75d-169">Determines whether the object is formatted as a table or a list.</span></span> <span data-ttu-id="7d75d-170">Допустимые значения: **Table** и **List** .</span><span class="sxs-lookup"><span data-stu-id="7d75d-170">Valid values are **Table** and **List** .</span></span> <span data-ttu-id="7d75d-171">Значение по умолчанию — **Table** .</span><span class="sxs-lookup"><span data-stu-id="7d75d-171">The default value is **Table** .</span></span>

<span data-ttu-id="7d75d-172">**Табличное** значение создает таблицу HTML, похожую на формат таблицы PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7d75d-172">The **Table** value generates an HTML table that resembles the PowerShell table format.</span></span> <span data-ttu-id="7d75d-173">В строке заголовка отображаются имена свойств.</span><span class="sxs-lookup"><span data-stu-id="7d75d-173">The header row displays the property names.</span></span> <span data-ttu-id="7d75d-174">Каждая строка таблицы представляет объект и отображает значения объекта для каждого свойства.</span><span class="sxs-lookup"><span data-stu-id="7d75d-174">Each table row represents an object and displays the object's values for each property.</span></span>

<span data-ttu-id="7d75d-175">Значение **списка** создает таблицу HTML с двумя столбцами для каждого объекта, который напоминает формат списка PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7d75d-175">The **List** value generates a two-column HTML table for each object that resembles the PowerShell list format.</span></span> <span data-ttu-id="7d75d-176">В первом столбце отображается имя свойства.</span><span class="sxs-lookup"><span data-stu-id="7d75d-176">The first column displays the property name.</span></span> <span data-ttu-id="7d75d-177">Во втором столбце отображается значение свойства.</span><span class="sxs-lookup"><span data-stu-id="7d75d-177">The second column displays the property value.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Table, List

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7d75d-178">-Body</span><span class="sxs-lookup"><span data-stu-id="7d75d-178">-Body</span></span>

<span data-ttu-id="7d75d-179">Задает текст, добавляемый после открывающего тега `<BODY>`.</span><span class="sxs-lookup"><span data-stu-id="7d75d-179">Specifies the text to add after the opening `<BODY>` tag.</span></span> <span data-ttu-id="7d75d-180">По умолчанию текст в этой позиции отсутствует.</span><span class="sxs-lookup"><span data-stu-id="7d75d-180">By default, there is no text in that position.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Page
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7d75d-181">-Charset</span><span class="sxs-lookup"><span data-stu-id="7d75d-181">-Charset</span></span>

<span data-ttu-id="7d75d-182">Задает текст, добавляемый в открывающий `<charset>` тег.</span><span class="sxs-lookup"><span data-stu-id="7d75d-182">Specifies text to add to the opening `<charset>` tag.</span></span> <span data-ttu-id="7d75d-183">По умолчанию текст в этой позиции отсутствует.</span><span class="sxs-lookup"><span data-stu-id="7d75d-183">By default, there is no text in that position.</span></span>

<span data-ttu-id="7d75d-184">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="7d75d-184">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.String
Parameter Sets: Page
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7d75d-185">-Кссури</span><span class="sxs-lookup"><span data-stu-id="7d75d-185">-CssUri</span></span>

<span data-ttu-id="7d75d-186">Указывает идентификатор URI таблицы каскадных стилей (CSS), применяемый к HTML-файлу.</span><span class="sxs-lookup"><span data-stu-id="7d75d-186">Specifies the Uniform Resource Identifier (URI) of the cascading style sheet (CSS) that is applied to the HTML file.</span></span> <span data-ttu-id="7d75d-187">Этот URI включается в ссылку таблицы стилей в выходных данных.</span><span class="sxs-lookup"><span data-stu-id="7d75d-187">The URI is included in a style sheet link in the output.</span></span>

```yaml
Type: System.Uri
Parameter Sets: Page
Aliases: cu, uri

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7d75d-188">-Fragment</span><span class="sxs-lookup"><span data-stu-id="7d75d-188">-Fragment</span></span>

<span data-ttu-id="7d75d-189">Создает только HTML-таблицу.</span><span class="sxs-lookup"><span data-stu-id="7d75d-189">Generates only an HTML table.</span></span> <span data-ttu-id="7d75d-190">Теги HTML, HEAD, TITLE и BODY пропускаются.</span><span class="sxs-lookup"><span data-stu-id="7d75d-190">The HTML, HEAD, TITLE, and BODY tags are omitted.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Fragment
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7d75d-191">-Head</span><span class="sxs-lookup"><span data-stu-id="7d75d-191">-Head</span></span>

<span data-ttu-id="7d75d-192">Задает содержимое тега `<HEAD>`.</span><span class="sxs-lookup"><span data-stu-id="7d75d-192">Specifies the content of the `<HEAD>` tag.</span></span> <span data-ttu-id="7d75d-193">Значение по умолчанию — `<title\>HTML TABLE</title>`.</span><span class="sxs-lookup"><span data-stu-id="7d75d-193">The default is `<title\>HTML TABLE</title>`.</span></span> <span data-ttu-id="7d75d-194">При использовании параметра **head** параметр **Title** игнорируется.</span><span class="sxs-lookup"><span data-stu-id="7d75d-194">If you use the **Head** parameter, the **Title** parameter is ignored.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Page
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7d75d-195">-InputObject</span><span class="sxs-lookup"><span data-stu-id="7d75d-195">-InputObject</span></span>

<span data-ttu-id="7d75d-196">Указывает объекты, которые должны быть представлены в формате HTML.</span><span class="sxs-lookup"><span data-stu-id="7d75d-196">Specifies the objects to be represented in HTML.</span></span> <span data-ttu-id="7d75d-197">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="7d75d-197">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span>

<span data-ttu-id="7d75d-198">Если этот параметр используется для отправки нескольких объектов, таких как все службы на компьютере, `ConvertTo-Html` создает таблицу, отображающую свойства коллекции или массива объектов.</span><span class="sxs-lookup"><span data-stu-id="7d75d-198">If you use this parameter to submit multiple objects, such as all of the services on a computer, `ConvertTo-Html` creates a table that displays the properties of a collection or of an array of objects.</span></span> <span data-ttu-id="7d75d-199">Чтобы создать таблицу отдельных объектов, используйте оператор конвейера, чтобы передать объекты в `ConvertTo-Html` .</span><span class="sxs-lookup"><span data-stu-id="7d75d-199">To create a table of the individual objects, use the pipeline operator to pipe the objects to `ConvertTo-Html`.</span></span>

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

### <span data-ttu-id="7d75d-200">-Meta</span><span class="sxs-lookup"><span data-stu-id="7d75d-200">-Meta</span></span>

<span data-ttu-id="7d75d-201">Задает текст, добавляемый в открывающий `<meta>` тег.</span><span class="sxs-lookup"><span data-stu-id="7d75d-201">Specifies text to add to the opening `<meta>` tag.</span></span> <span data-ttu-id="7d75d-202">По умолчанию текст в этой позиции отсутствует.</span><span class="sxs-lookup"><span data-stu-id="7d75d-202">By default, there is no text in that position.</span></span>

<span data-ttu-id="7d75d-203">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="7d75d-203">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: Page
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7d75d-204">-Содержимое</span><span class="sxs-lookup"><span data-stu-id="7d75d-204">-PostContent</span></span>

<span data-ttu-id="7d75d-205">Задает текст, добавляемый после закрывающего тега `</TABLE>`.</span><span class="sxs-lookup"><span data-stu-id="7d75d-205">Specifies text to add after the closing `</TABLE>` tag.</span></span> <span data-ttu-id="7d75d-206">По умолчанию текст в этой позиции отсутствует.</span><span class="sxs-lookup"><span data-stu-id="7d75d-206">By default, there is no text in that position.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7d75d-207">— Предварительное содержимое</span><span class="sxs-lookup"><span data-stu-id="7d75d-207">-PreContent</span></span>

<span data-ttu-id="7d75d-208">Задает текст, добавляемый перед открывающим тегом `<TABLE>`.</span><span class="sxs-lookup"><span data-stu-id="7d75d-208">Specifies text to add before the opening `<TABLE>` tag.</span></span> <span data-ttu-id="7d75d-209">По умолчанию текст в этой позиции отсутствует.</span><span class="sxs-lookup"><span data-stu-id="7d75d-209">By default, there is no text in that position.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7d75d-210">-Property</span><span class="sxs-lookup"><span data-stu-id="7d75d-210">-Property</span></span>

<span data-ttu-id="7d75d-211">Включает указанные свойства объектов в HTML.</span><span class="sxs-lookup"><span data-stu-id="7d75d-211">Includes the specified properties of the objects in the HTML.</span></span> <span data-ttu-id="7d75d-212">Значением параметра **Property** может быть новое вычисляемое свойство.</span><span class="sxs-lookup"><span data-stu-id="7d75d-212">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="7d75d-213">Вычисляемое свойство может быть блоком скрипта или хэш-таблицей.</span><span class="sxs-lookup"><span data-stu-id="7d75d-213">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="7d75d-214">Допустимые пары "ключ-значение":</span><span class="sxs-lookup"><span data-stu-id="7d75d-214">Valid key-value pairs are:</span></span>

- <span data-ttu-id="7d75d-215">Имя (или метка) — `<string>` (добавляется в PowerShell 6. x)</span><span class="sxs-lookup"><span data-stu-id="7d75d-215">Name (or label) - `<string>` (added in PowerShell 6.x)</span></span>
- <span data-ttu-id="7d75d-216">Выражение — `<string>` или `<script block>`</span><span class="sxs-lookup"><span data-stu-id="7d75d-216">Expression - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="7d75d-217">FormatString `<string>`</span><span class="sxs-lookup"><span data-stu-id="7d75d-217">FormatString - `<string>`</span></span>
- <span data-ttu-id="7d75d-218">Ширина- `<int32>` -должен быть больше `0`</span><span class="sxs-lookup"><span data-stu-id="7d75d-218">Width - `<int32>` - must be greater than `0`</span></span>
- <span data-ttu-id="7d75d-219">Alignment — значение может быть `Left` , `Center` или `Right`</span><span class="sxs-lookup"><span data-stu-id="7d75d-219">Alignment - value can be `Left`, `Center`, or `Right`</span></span>

<span data-ttu-id="7d75d-220">Дополнительные сведения см. в разделе [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="7d75d-220">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7d75d-221">-Title</span><span class="sxs-lookup"><span data-stu-id="7d75d-221">-Title</span></span>

<span data-ttu-id="7d75d-222">Указывает заголовок HTML-файл, т. е. текст, расположенный между тегами `<TITLE>`.</span><span class="sxs-lookup"><span data-stu-id="7d75d-222">Specifies a title for the HTML file, that is, the text that appears between the `<TITLE>` tags.</span></span>

```yaml
Type: System.String
Parameter Sets: Page
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7d75d-223">— Переход</span><span class="sxs-lookup"><span data-stu-id="7d75d-223">-Transitional</span></span>

<span data-ttu-id="7d75d-224">Изменяет тип **DOCTYPE** на **XHTML transitioned DTD** , по умолчанию **DOCTYPE** — **XHTML** .</span><span class="sxs-lookup"><span data-stu-id="7d75d-224">Changes the **DOCTYPE** to **XHTML Transitional DTD** , Default **DOCTYPE** is **XHTML Strict DTD** .</span></span>

<span data-ttu-id="7d75d-225">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="7d75d-225">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Page
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7d75d-226">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="7d75d-226">CommonParameters</span></span>

<span data-ttu-id="7d75d-227">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7d75d-227">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7d75d-228">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="7d75d-228">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7d75d-229">Входные данные</span><span class="sxs-lookup"><span data-stu-id="7d75d-229">INPUTS</span></span>

### <span data-ttu-id="7d75d-230">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="7d75d-230">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="7d75d-231">Любой объект .NET можно передать в конвейер `ConvertTo-Html` .</span><span class="sxs-lookup"><span data-stu-id="7d75d-231">You can pipe any .NET object to `ConvertTo-Html`.</span></span>

## <span data-ttu-id="7d75d-232">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="7d75d-232">OUTPUTS</span></span>

### <span data-ttu-id="7d75d-233">System. String или System.Xml.Xmlдокумент</span><span class="sxs-lookup"><span data-stu-id="7d75d-233">System.String or System.Xml.XmlDocument</span></span>

<span data-ttu-id="7d75d-234">`ConvertTo-Html` Возвращает ряд строк, составляющих допустимый HTML-код.</span><span class="sxs-lookup"><span data-stu-id="7d75d-234">`ConvertTo-Html` returns series of strings that comprise valid HTML.</span></span>

## <span data-ttu-id="7d75d-235">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="7d75d-235">NOTES</span></span>

<span data-ttu-id="7d75d-236">Чтобы использовать этот командлет, необходимо передать один или несколько объектов в командлет или использовать параметр **InputObject** для указания объекта.</span><span class="sxs-lookup"><span data-stu-id="7d75d-236">To use this cmdlet, pipe one or more objects to the cmdlet or use the **InputObject** parameter to specify the object.</span></span> <span data-ttu-id="7d75d-237">Если входные данные состоят из нескольких объектов, выходные данные этих двух методов отличаются.</span><span class="sxs-lookup"><span data-stu-id="7d75d-237">When the input consists of multiple objects, the output of these two methods is quite different.</span></span>

- <span data-ttu-id="7d75d-238">При передаче нескольких объектов в командлет PowerShell посылает объекты в командлет по одному за раз.</span><span class="sxs-lookup"><span data-stu-id="7d75d-238">When you pipe multiple objects to a cmdlet, PowerShell sends the objects to the cmdlet one at a time.</span></span> <span data-ttu-id="7d75d-239">В результате `ConvertTo-Html` создается таблица, в которой отображаются отдельные объекты.</span><span class="sxs-lookup"><span data-stu-id="7d75d-239">As a result, `ConvertTo-Html` creates a table that displays the individual objects.</span></span> <span data-ttu-id="7d75d-240">Например, если передать процессы на компьютере в `ConvertTo-Html` , в результирующей таблице отобразятся все процессы.</span><span class="sxs-lookup"><span data-stu-id="7d75d-240">For example, if you pipe the processes on a computer to `ConvertTo-Html`, the resulting table displays all of the processes.</span></span>

- <span data-ttu-id="7d75d-241">При использовании параметра **InputObject** для отправки нескольких объектов `ConvertTo-Html` получает эти объекты как коллекцию или как массив.</span><span class="sxs-lookup"><span data-stu-id="7d75d-241">When you use the **InputObject** parameter to submit multiple objects, `ConvertTo-Html` receives these objects as a collection or as an array.</span></span> <span data-ttu-id="7d75d-242">В результате создается таблица, отображающая массива и его свойства, а не элементы в массиве.</span><span class="sxs-lookup"><span data-stu-id="7d75d-242">As a result, it creates a table that displays the array and its properties, not the items in the array.</span></span> <span data-ttu-id="7d75d-243">Например, при использовании **InputObject** для отправки процессов на компьютер в `ConvertTo-Html` результирующая таблица отображает массив объектов и его свойства.</span><span class="sxs-lookup"><span data-stu-id="7d75d-243">For example, if you use **InputObject** to submit the processes on a computer to `ConvertTo-Html`, the resulting table displays an object array and its properties.</span></span>

  <span data-ttu-id="7d75d-244">Чтобы обеспечить соответствие стандарту XHTML-DTD, тег DOCTYPE изменяется соответствующим образом:</span><span class="sxs-lookup"><span data-stu-id="7d75d-244">To comply with the XHTML Strict DTD, the DOCTYPE tag is modified accordingly:</span></span>

   `<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN"   "https://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd"\>`

## <span data-ttu-id="7d75d-245">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="7d75d-245">RELATED LINKS</span></span>

[<span data-ttu-id="7d75d-246">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="7d75d-246">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="7d75d-247">ConvertTo-Csv</span><span class="sxs-lookup"><span data-stu-id="7d75d-247">ConvertTo-Csv</span></span>](ConvertTo-Csv.md)

[<span data-ttu-id="7d75d-248">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="7d75d-248">ConvertTo-Json</span></span>](ConvertTo-Json.md)

[<span data-ttu-id="7d75d-249">ConvertTo-Xml</span><span class="sxs-lookup"><span data-stu-id="7d75d-249">ConvertTo-Xml</span></span>](ConvertTo-Xml.md)

[<span data-ttu-id="7d75d-250">Export-Clixml</span><span class="sxs-lookup"><span data-stu-id="7d75d-250">Export-Clixml</span></span>](Export-Clixml.md)

[<span data-ttu-id="7d75d-251">Import-Clixml</span><span class="sxs-lookup"><span data-stu-id="7d75d-251">Import-Clixml</span></span>](Import-Clixml.md)
