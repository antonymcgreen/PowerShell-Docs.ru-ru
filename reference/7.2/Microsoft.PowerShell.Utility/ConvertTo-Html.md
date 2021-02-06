---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-html?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-Html
ms.openlocfilehash: ffe7fe7c44258435c7ec9ddd2bab9ebeb9f6c465
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601608"
---
# <span data-ttu-id="cdc4e-102">ConvertTo-Html</span><span class="sxs-lookup"><span data-stu-id="cdc4e-102">ConvertTo-Html</span></span>

## <span data-ttu-id="cdc4e-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="cdc4e-103">SYNOPSIS</span></span>
<span data-ttu-id="cdc4e-104">Преобразует объекты .NET в код HTML, который может отображаться в веб-браузере.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-104">Converts .NET objects into HTML that can be displayed in a Web browser.</span></span>

## <span data-ttu-id="cdc4e-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="cdc4e-105">SYNTAX</span></span>

### <span data-ttu-id="cdc4e-106">Страница (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="cdc4e-106">Page (Default)</span></span>

```
ConvertTo-Html [-InputObject <PSObject>] [[-Property] <Object[]>] [[-Body] <String[]>]
 [[-Head] <String[]>] [[-Title] <String>] [-As <String>] [-CssUri <Uri>] [-PostContent <String[]>]
 [-PreContent <String[]>] [-Meta <Hashtable>] [-Charset <String>] [-Transitional]
 [<CommonParameters>]
```

### <span data-ttu-id="cdc4e-107">Fragment</span><span class="sxs-lookup"><span data-stu-id="cdc4e-107">Fragment</span></span>

```
ConvertTo-Html [-InputObject <PSObject>] [[-Property] <Object[]>] [-As <String>] [-Fragment]
 [-PostContent <String[]>] [-PreContent <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="cdc4e-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="cdc4e-108">DESCRIPTION</span></span>

<span data-ttu-id="cdc4e-109">`ConvertTo-Html`Командлет преобразует объекты .NET в формат HTML, который может отображаться в веб-браузере.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-109">The `ConvertTo-Html` cmdlet converts .NET objects into HTML that can be displayed in a Web browser.</span></span> <span data-ttu-id="cdc4e-110">Этот командлет можно использовать для отображения выходных данных команды на веб-странице.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-110">You can use this cmdlet to display the output of a command in a Web page.</span></span>

<span data-ttu-id="cdc4e-111">С помощью параметров можно `ConvertTo-Html` выбрать свойства объекта, указать формат таблицы или списка, указать заголовок HTML-страницы, добавить текст до и после объекта, а также вернуть только фрагмент таблицы или списка, а не определенную страницу DTD.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-111">You can use the parameters of `ConvertTo-Html` to select object properties, to specify a table or list format, to specify the HTML page title, to add text before and after the object, and to return only the table or list fragment, instead of a strict DTD page.</span></span>

<span data-ttu-id="cdc4e-112">При отправке нескольких объектов в `ConvertTo-Html` PowerShell создает таблицу (или список) на основе свойств первого отправленного объекта.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-112">When you submit multiple objects to `ConvertTo-Html`, PowerShell creates the table (or list) based on the properties of the first object that you submit.</span></span> <span data-ttu-id="cdc4e-113">Если у оставшихся объектов нет одного из указанных свойств, значением свойства этого объекта является пустая ячейка.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-113">If the remaining objects do not have one of the specified properties, the property value of that object is an empty cell.</span></span> <span data-ttu-id="cdc4e-114">Если оставшиеся объекты содержат дополнительные свойства, их значения не включаются в файл.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-114">If the remaining objects have additional properties, those property values are not included in the file.</span></span>

## <span data-ttu-id="cdc4e-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="cdc4e-115">EXAMPLES</span></span>

### <span data-ttu-id="cdc4e-116">Пример 1. Создание веб-страницы для вывода даты</span><span class="sxs-lookup"><span data-stu-id="cdc4e-116">Example 1: Create a web page to display the date</span></span>

```powershell
ConvertTo-Html -InputObject (Get-Date)
```

<span data-ttu-id="cdc4e-117">Эта команда создает HTML-страницу, на которой отображаются свойства текущей даты.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-117">This command creates an HTML page that displays the properties of the current date.</span></span> <span data-ttu-id="cdc4e-118">Он использует параметр **InputObject** для отправки результатов `Get-Date` команды в `ConvertTo-Html` командлет.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-118">It uses the **InputObject** parameter to submit the results of a `Get-Date` command to the `ConvertTo-Html` cmdlet.</span></span>

### <span data-ttu-id="cdc4e-119">Пример 2. Создание веб-страницы для вывода псевдонимов PowerShell</span><span class="sxs-lookup"><span data-stu-id="cdc4e-119">Example 2: Create a web page to display PowerShell aliases</span></span>

```powershell
Get-Alias | ConvertTo-Html | Out-File aliases.htm
Invoke-Item aliases.htm
```

<span data-ttu-id="cdc4e-120">Эта команда создает HTML-страницу, в которой перечислены псевдонимы PowerShell в текущей консоли.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-120">This command creates an HTML page that lists the PowerShell aliases in the current console.</span></span>

<span data-ttu-id="cdc4e-121">Команда использует `Get-Alias` командлет для получения псевдонимов.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-121">The command uses the `Get-Alias` cmdlet to get the aliases.</span></span> <span data-ttu-id="cdc4e-122">Он использует оператор конвейера ( `|` ) для отправки псевдонимов в `ConvertTo-Html` командлет, который создает HTML-страницу.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-122">It uses the pipeline operator (`|`) to send the aliases to the `ConvertTo-Html` cmdlet, which creates the HTML page.</span></span> <span data-ttu-id="cdc4e-123">Команда также использует `Out-File` командлет для отправки HTML-кода в `aliases.htm` файл.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-123">The command also uses the `Out-File` cmdlet to send the HTML code to the `aliases.htm` file.</span></span>

### <span data-ttu-id="cdc4e-124">Пример 3. Создание веб-страницы для вывода событий PowerShell</span><span class="sxs-lookup"><span data-stu-id="cdc4e-124">Example 3: Create a web page to display PowerShell events</span></span>

```powershell
`Get-EventLog` -LogName "Windows PowerShell" | ConvertTo-Html | Out-File pslog.htm
```

<span data-ttu-id="cdc4e-125">Эта команда создает HTML-страницу `pslog.htm` с именем, которая отображает события в журнале событий Windows PowerShell на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-125">This command creates an HTML page called `pslog.htm` that displays the events in the Windows PowerShell event log on the local computer.</span></span>

<span data-ttu-id="cdc4e-126">Он использует `Get-EventLog` командлет для получения событий в журнале Windows PowerShell, а затем использует оператор конвейера ( `|` ) для отправки событий в `ConvertTo-Html` командлет.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-126">It uses the `Get-EventLog` cmdlet to get the events in the Windows PowerShell log and then uses the pipeline operator (`|`) to send the events to the `ConvertTo-Html` cmdlet.</span></span> <span data-ttu-id="cdc4e-127">Команда также использует `Out-File` командлет для отправки HTML-кода в `pslog.htm` файл.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-127">The command also uses the `Out-File` cmdlet to send the HTML code to the `pslog.htm` file.</span></span>

<span data-ttu-id="cdc4e-128">Команда также использует `Out-File` командлет для отправки HTML-кода в `pslog.htm` файл.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-128">The command also uses the `Out-File` cmdlet to send the HTML code to the `pslog.htm` file.</span></span>

### <span data-ttu-id="cdc4e-129">Пример 4. Создание веб-страницы для показа процессов</span><span class="sxs-lookup"><span data-stu-id="cdc4e-129">Example 4: Create a web page to display processes</span></span>

```powershell
Get-Process |
  ConvertTo-Html -Property Name, Path, Company -Title "Process Information" |
    Out-File proc.htm
Invoke-Item proc.htm
```

<span data-ttu-id="cdc4e-130">Эти команды создают и открывают HTML-страницу, содержащую имя, путь и компанию для процессов на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-130">These commands create and open an HTML page that lists the name, path, and company of the processes on the local computer.</span></span>

<span data-ttu-id="cdc4e-131">Первая команда использует `Get-Process` командлет для получения объектов, представляющих процессы, запущенные на компьютере.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-131">The first command uses the `Get-Process` cmdlet to get objects that represent the processes running on the computer.</span></span> <span data-ttu-id="cdc4e-132">Команда использует оператор конвейера ( `|` ) для отправки объектов процесса в `ConvertTo-Html` командлет.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-132">The command uses the pipeline operator (`|`) to send the process objects to the `ConvertTo-Html` cmdlet.</span></span>

<span data-ttu-id="cdc4e-133">Команда использует параметр **Property** для выбора трех свойств объектов процесса, которые должны быть добавлены в таблицу.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-133">The command uses the **Property** parameter to select three properties of the process objects to be included in the table.</span></span> <span data-ttu-id="cdc4e-134">Команда использует параметр **Title** для указания заголовка HTML-страницы.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-134">The command uses the **Title** parameter to specify a title for the HTML page.</span></span> <span data-ttu-id="cdc4e-135">Команда также использует `Out-File` командлет для отправки полученного HTML-кода в файл с именем Proc.htm.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-135">The command also uses the `Out-File` cmdlet to send the resulting HTML to a file named Proc.htm.</span></span>

<span data-ttu-id="cdc4e-136">Вторая команда использует `Invoke-Item` командлет для открытия в `Proc.htm` браузере по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-136">The second command uses the `Invoke-Item` cmdlet to open the `Proc.htm` in the default browser.</span></span>

### <span data-ttu-id="cdc4e-137">Пример 5. Создание веб-страницы для вывода объектов службы</span><span class="sxs-lookup"><span data-stu-id="cdc4e-137">Example 5: Create a web page to display service objects</span></span>

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

<span data-ttu-id="cdc4e-138">Эта команда создает HTML-страницу объектов службы, `Get-Service` возвращаемых командлетом.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-138">This command creates an HTML page of the service objects that the `Get-Service` cmdlet returns.</span></span> <span data-ttu-id="cdc4e-139">Команда использует параметр **кссури** для указания каскадной таблицы стилей для HTML-страницы.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-139">The command uses the **CssUri** parameter to specify a cascading style sheet for the HTML page.</span></span>

<span data-ttu-id="cdc4e-140">Параметр **кссури** добавляет дополнительный `<link rel="stylesheet" type="text/css" href="test.css">` тег в результирующий HTML-код.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-140">The **CssUri** parameter adds an additional `<link rel="stylesheet" type="text/css" href="test.css">` tag to the resulting HTML.</span></span> <span data-ttu-id="cdc4e-141">Атрибут HREF в теге содержит имя таблицы стилей.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-141">The HREF attribute in the tag contains the name of the style sheet.</span></span>

### <span data-ttu-id="cdc4e-142">Пример 6. Создание веб-страницы для вывода объектов службы</span><span class="sxs-lookup"><span data-stu-id="cdc4e-142">Example 6: Create a web page to display service objects</span></span>

```powershell
Get-Service | ConvertTo-Html -As LIST | Out-File services.htm
```

<span data-ttu-id="cdc4e-143">Эта команда создает HTML-страницу объектов службы, `Get-Service` возвращаемых командлетом.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-143">This command creates an HTML page of the service objects that the `Get-Service` cmdlet returns.</span></span> <span data-ttu-id="cdc4e-144">Команда использует параметр **as** для задания формата списка.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-144">The command uses the **As** parameter to specify a list format.</span></span> <span data-ttu-id="cdc4e-145">Командлет `Out-File` отправляет полученный HTML-код в `Services.htm` файл.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-145">The cmdlet `Out-File` sends the resulting HTML to the `Services.htm` file.</span></span>

### <span data-ttu-id="cdc4e-146">Пример 7. Создание веб-таблицы для текущей даты</span><span class="sxs-lookup"><span data-stu-id="cdc4e-146">Example 7: Create a web table for the current date</span></span>

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

<span data-ttu-id="cdc4e-147">Эта команда использует `ConvertTo-Html` для создания HTML-таблицы текущей даты.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-147">This command uses `ConvertTo-Html` to generate an HTML table of the current date.</span></span> <span data-ttu-id="cdc4e-148">Команда использует `Get-Date` командлет для получения текущей даты.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-148">The command uses the `Get-Date` cmdlet to get the current date.</span></span> <span data-ttu-id="cdc4e-149">Для отправки результатов в командлет используется оператор конвейера (|) `ConvertTo-Html` .</span><span class="sxs-lookup"><span data-stu-id="cdc4e-149">It uses a pipeline operator (|) to send the results to the `ConvertTo-Html` cmdlet.</span></span>

<span data-ttu-id="cdc4e-150">`ConvertTo-Html`Команда включает параметр **Fragment** , который ограничивает выходные данные HTML-таблицей.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-150">The `ConvertTo-Html` command includes the **Fragment** parameter, which limits the output to an HTML table.</span></span> <span data-ttu-id="cdc4e-151">В результате другие элементы HTML-страницы, например теги `<HEAD>` и `<BODY>`, пропускаются.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-151">As a result, the other elements of an HTML page, such as the `<HEAD>` and `<BODY>` tags, are omitted.</span></span>

### <span data-ttu-id="cdc4e-152">Пример 8. Создание веб-страницы для вывода событий PowerShell</span><span class="sxs-lookup"><span data-stu-id="cdc4e-152">Example 8: Create a web page to display PowerShell events</span></span>

```powershell
Get-EventLog -Log "Windows PowerShell" | ConvertTo-Html -Property id, level, task
```

<span data-ttu-id="cdc4e-153">Эта команда использует `Get-EventLog` командлет для получения событий из журнала событий Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-153">This command uses the `Get-EventLog` cmdlet to get events from the Windows PowerShell event log.</span></span>

<span data-ttu-id="cdc4e-154">Он использует оператор конвейера ( `|` ) для отправки событий в `ConvertTo-Html` командлет, который преобразует события в формат HTML.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-154">It uses a pipeline operator (`|`) to send the events to the `ConvertTo-Html` cmdlet, which converts the events to HTML format.</span></span>

<span data-ttu-id="cdc4e-155">`ConvertTo-Html`Команда использует параметр **Property** для выбора только свойств **ID**, **Level** и **Task** события.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-155">The `ConvertTo-Html` command uses the **Property** parameter to select only the **ID**, **Level**, and **Task** properties of the event.</span></span>

### <span data-ttu-id="cdc4e-156">Пример 9. Создание веб-страницы для показа указанных служб</span><span class="sxs-lookup"><span data-stu-id="cdc4e-156">Example 9: Create a web page to display specified services</span></span>

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

<span data-ttu-id="cdc4e-157">Эта команда создает и открывает веб-страницу, в которой отображаются службы на компьютере, начинающиеся с. Для настройки выходных данных в нем используются параметры **Title**, **Body**, for **Content** и My **Content** `ConvertTo-Html` .</span><span class="sxs-lookup"><span data-stu-id="cdc4e-157">This command creates and opens a Web page that displays the services on the computer that begin with A. It uses the **Title**, **Body**, **PreContent**, and **PostContent** parameters of `ConvertTo-Html` to customize the output.</span></span>

<span data-ttu-id="cdc4e-158">Первая часть команды использует `Get-Service` командлет для получения служб на компьютере, который начинается с. Команда использует оператор конвейера ( `|` ) для отправки результатов в `ConvertTo-Html` командлет.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-158">The first part of the command uses the `Get-Service` cmdlet to get the services on the computer that begin with A. The command uses a pipeline operator (`|`) to send the results to the `ConvertTo-Html` cmdlet.</span></span> <span data-ttu-id="cdc4e-159">Команда также использует `Out-File` командлет для отправки выходных данных в файл Services.htm.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-159">The command also uses the `Out-File` cmdlet to send the output to the Services.htm file.</span></span>

<span data-ttu-id="cdc4e-160">Точка с запятой ( `;` ) завершает первую команду и запускает вторую команду, которая использует `Invoke-Item` командлет для открытия `Services.htm` файла в браузере по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-160">A semicolon (`;`) ends the first command and starts a second command, which uses the `Invoke-Item` cmdlet to open the `Services.htm` file in the default browser.</span></span>

### <span data-ttu-id="cdc4e-161">Пример 10. Задание свойств meta и charset HTML</span><span class="sxs-lookup"><span data-stu-id="cdc4e-161">Example 10: Set the Meta properties and Charset of the HTML</span></span>

```powershell
Get-Service | ConvertTo-HTML -Meta @{
  refresh=10
  author="Author's Name"
  keywords="PowerShell, HTML, ConvertTo-HTML"
} -Charset "UTF-8"
```

<span data-ttu-id="cdc4e-162">Эта команда создает HTML для веб-страницы с тегами meta для обновления, создания и ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-162">This command creates the HTML for a webpage with the meta tags for refresh, author, and keywords.</span></span>
<span data-ttu-id="cdc4e-163">Кодировка для страницы равна UTF-8</span><span class="sxs-lookup"><span data-stu-id="cdc4e-163">The charset for the page is set to UTF-8</span></span>

### <span data-ttu-id="cdc4e-164">Пример 11. Настройка переходного формата HTML в формат XHTML</span><span class="sxs-lookup"><span data-stu-id="cdc4e-164">Example 11: Set the HTML to XHTML Transitional DTD</span></span>

```powershell
Get-Service | ConvertTo-HTML -Transitional
```

<span data-ttu-id="cdc4e-165">Эта команда устанавливает DOCTYPE возвращаемого HTML-кода в XHTML Transitional DTD</span><span class="sxs-lookup"><span data-stu-id="cdc4e-165">This command sets the DOCTYPE of the returned HTML to XHTML Transitional DTD</span></span>

## <span data-ttu-id="cdc4e-166">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="cdc4e-166">PARAMETERS</span></span>

### <span data-ttu-id="cdc4e-167">— Как</span><span class="sxs-lookup"><span data-stu-id="cdc4e-167">-As</span></span>

<span data-ttu-id="cdc4e-168">Определяет, форматируется ли объект как таблица или список.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-168">Determines whether the object is formatted as a table or a list.</span></span> <span data-ttu-id="cdc4e-169">Допустимые значения: **Table** и **List**.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-169">Valid values are **Table** and **List**.</span></span> <span data-ttu-id="cdc4e-170">Значение по умолчанию — **Table**.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-170">The default value is **Table**.</span></span>

<span data-ttu-id="cdc4e-171">**Табличное** значение создает таблицу HTML, похожую на формат таблицы PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-171">The **Table** value generates an HTML table that resembles the PowerShell table format.</span></span> <span data-ttu-id="cdc4e-172">В строке заголовка отображаются имена свойств.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-172">The header row displays the property names.</span></span> <span data-ttu-id="cdc4e-173">Каждая строка таблицы представляет объект и отображает значения объекта для каждого свойства.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-173">Each table row represents an object and displays the object's values for each property.</span></span>

<span data-ttu-id="cdc4e-174">Значение **списка** создает таблицу HTML с двумя столбцами для каждого объекта, который напоминает формат списка PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-174">The **List** value generates a two-column HTML table for each object that resembles the PowerShell list format.</span></span> <span data-ttu-id="cdc4e-175">В первом столбце отображается имя свойства.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-175">The first column displays the property name.</span></span> <span data-ttu-id="cdc4e-176">Во втором столбце отображается значение свойства.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-176">The second column displays the property value.</span></span>

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

### <span data-ttu-id="cdc4e-177">-Body</span><span class="sxs-lookup"><span data-stu-id="cdc4e-177">-Body</span></span>

<span data-ttu-id="cdc4e-178">Задает текст, добавляемый после открывающего тега `<BODY>`.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-178">Specifies the text to add after the opening `<BODY>` tag.</span></span> <span data-ttu-id="cdc4e-179">По умолчанию текст в этой позиции отсутствует.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-179">By default, there is no text in that position.</span></span>

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

### <span data-ttu-id="cdc4e-180">-Charset</span><span class="sxs-lookup"><span data-stu-id="cdc4e-180">-Charset</span></span>

<span data-ttu-id="cdc4e-181">Задает текст, добавляемый в открывающий `<charset>` тег.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-181">Specifies text to add to the opening `<charset>` tag.</span></span> <span data-ttu-id="cdc4e-182">По умолчанию текст в этой позиции отсутствует.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-182">By default, there is no text in that position.</span></span>

<span data-ttu-id="cdc4e-183">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-183">This parameter was introduced in PowerShell 6.0.</span></span>

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

### <span data-ttu-id="cdc4e-184">-Кссури</span><span class="sxs-lookup"><span data-stu-id="cdc4e-184">-CssUri</span></span>

<span data-ttu-id="cdc4e-185">Указывает идентификатор URI таблицы каскадных стилей (CSS), применяемый к HTML-файлу.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-185">Specifies the Uniform Resource Identifier (URI) of the cascading style sheet (CSS) that is applied to the HTML file.</span></span> <span data-ttu-id="cdc4e-186">Этот URI включается в ссылку таблицы стилей в выходных данных.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-186">The URI is included in a style sheet link in the output.</span></span>

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

### <span data-ttu-id="cdc4e-187">-Fragment</span><span class="sxs-lookup"><span data-stu-id="cdc4e-187">-Fragment</span></span>

<span data-ttu-id="cdc4e-188">Создает только HTML-таблицу.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-188">Generates only an HTML table.</span></span> <span data-ttu-id="cdc4e-189">Теги HTML, HEAD, TITLE и BODY пропускаются.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-189">The HTML, HEAD, TITLE, and BODY tags are omitted.</span></span>

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

### <span data-ttu-id="cdc4e-190">-Head</span><span class="sxs-lookup"><span data-stu-id="cdc4e-190">-Head</span></span>

<span data-ttu-id="cdc4e-191">Задает содержимое тега `<HEAD>`.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-191">Specifies the content of the `<HEAD>` tag.</span></span> <span data-ttu-id="cdc4e-192">Значение по умолчанию — `<title\>HTML TABLE</title>`.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-192">The default is `<title\>HTML TABLE</title>`.</span></span> <span data-ttu-id="cdc4e-193">При использовании параметра **head** параметр **Title** игнорируется.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-193">If you use the **Head** parameter, the **Title** parameter is ignored.</span></span>

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

### <span data-ttu-id="cdc4e-194">-InputObject</span><span class="sxs-lookup"><span data-stu-id="cdc4e-194">-InputObject</span></span>

<span data-ttu-id="cdc4e-195">Указывает объекты, которые должны быть представлены в формате HTML.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-195">Specifies the objects to be represented in HTML.</span></span> <span data-ttu-id="cdc4e-196">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-196">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span>

<span data-ttu-id="cdc4e-197">Если этот параметр используется для отправки нескольких объектов, таких как все службы на компьютере, `ConvertTo-Html` создает таблицу, отображающую свойства коллекции или массива объектов.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-197">If you use this parameter to submit multiple objects, such as all of the services on a computer, `ConvertTo-Html` creates a table that displays the properties of a collection or of an array of objects.</span></span> <span data-ttu-id="cdc4e-198">Чтобы создать таблицу отдельных объектов, используйте оператор конвейера, чтобы передать объекты в `ConvertTo-Html` .</span><span class="sxs-lookup"><span data-stu-id="cdc4e-198">To create a table of the individual objects, use the pipeline operator to pipe the objects to `ConvertTo-Html`.</span></span>

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

### <span data-ttu-id="cdc4e-199">-Meta</span><span class="sxs-lookup"><span data-stu-id="cdc4e-199">-Meta</span></span>

<span data-ttu-id="cdc4e-200">Задает текст, добавляемый в открывающий `<meta>` тег.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-200">Specifies text to add to the opening `<meta>` tag.</span></span> <span data-ttu-id="cdc4e-201">По умолчанию текст в этой позиции отсутствует.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-201">By default, there is no text in that position.</span></span>

<span data-ttu-id="cdc4e-202">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-202">This parameter was introduced in PowerShell 6.0.</span></span>

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

### <span data-ttu-id="cdc4e-203">-Содержимое</span><span class="sxs-lookup"><span data-stu-id="cdc4e-203">-PostContent</span></span>

<span data-ttu-id="cdc4e-204">Задает текст, добавляемый после закрывающего тега `</TABLE>`.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-204">Specifies text to add after the closing `</TABLE>` tag.</span></span> <span data-ttu-id="cdc4e-205">По умолчанию текст в этой позиции отсутствует.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-205">By default, there is no text in that position.</span></span>

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

### <span data-ttu-id="cdc4e-206">— Предварительное содержимое</span><span class="sxs-lookup"><span data-stu-id="cdc4e-206">-PreContent</span></span>

<span data-ttu-id="cdc4e-207">Задает текст, добавляемый перед открывающим тегом `<TABLE>`.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-207">Specifies text to add before the opening `<TABLE>` tag.</span></span> <span data-ttu-id="cdc4e-208">По умолчанию текст в этой позиции отсутствует.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-208">By default, there is no text in that position.</span></span>

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

### <span data-ttu-id="cdc4e-209">-Property</span><span class="sxs-lookup"><span data-stu-id="cdc4e-209">-Property</span></span>

<span data-ttu-id="cdc4e-210">Включает указанные свойства объектов в HTML.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-210">Includes the specified properties of the objects in the HTML.</span></span> <span data-ttu-id="cdc4e-211">Значением параметра **Property** может быть новое вычисляемое свойство.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-211">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="cdc4e-212">Вычисляемое свойство может быть блоком скрипта или хэш-таблицей.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-212">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="cdc4e-213">Допустимые пары "ключ-значение":</span><span class="sxs-lookup"><span data-stu-id="cdc4e-213">Valid key-value pairs are:</span></span>

- <span data-ttu-id="cdc4e-214">Имя (или метка) — `<string>` (добавляется в PowerShell 6. x)</span><span class="sxs-lookup"><span data-stu-id="cdc4e-214">Name (or label) - `<string>` (added in PowerShell 6.x)</span></span>
- <span data-ttu-id="cdc4e-215">Выражение — `<string>` или `<script block>`</span><span class="sxs-lookup"><span data-stu-id="cdc4e-215">Expression - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="cdc4e-216">FormatString `<string>`</span><span class="sxs-lookup"><span data-stu-id="cdc4e-216">FormatString - `<string>`</span></span>
- <span data-ttu-id="cdc4e-217">Ширина- `<int32>` -должен быть больше `0`</span><span class="sxs-lookup"><span data-stu-id="cdc4e-217">Width - `<int32>` - must be greater than `0`</span></span>
- <span data-ttu-id="cdc4e-218">Alignment — значение может быть `Left` , `Center` или `Right`</span><span class="sxs-lookup"><span data-stu-id="cdc4e-218">Alignment - value can be `Left`, `Center`, or `Right`</span></span>

<span data-ttu-id="cdc4e-219">Дополнительные сведения см. в разделе [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="cdc4e-219">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

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

### <span data-ttu-id="cdc4e-220">-Title</span><span class="sxs-lookup"><span data-stu-id="cdc4e-220">-Title</span></span>

<span data-ttu-id="cdc4e-221">Указывает заголовок HTML-файл, т. е. текст, расположенный между тегами `<TITLE>`.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-221">Specifies a title for the HTML file, that is, the text that appears between the `<TITLE>` tags.</span></span>

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

### <span data-ttu-id="cdc4e-222">— Переход</span><span class="sxs-lookup"><span data-stu-id="cdc4e-222">-Transitional</span></span>

<span data-ttu-id="cdc4e-223">Изменяет тип **DOCTYPE** на **XHTML transitioned DTD**, по умолчанию **DOCTYPE** — **XHTML**.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-223">Changes the **DOCTYPE** to **XHTML Transitional DTD**, Default **DOCTYPE** is **XHTML Strict DTD**.</span></span>

<span data-ttu-id="cdc4e-224">Этот параметр появился в PowerShell 6,0.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-224">This parameter was introduced in PowerShell 6.0.</span></span>

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

### <span data-ttu-id="cdc4e-225">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="cdc4e-225">CommonParameters</span></span>

<span data-ttu-id="cdc4e-226">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-226">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="cdc4e-227">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="cdc4e-227">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="cdc4e-228">Входные данные</span><span class="sxs-lookup"><span data-stu-id="cdc4e-228">INPUTS</span></span>

### <span data-ttu-id="cdc4e-229">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="cdc4e-229">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="cdc4e-230">Любой объект .NET можно передать в конвейер `ConvertTo-Html` .</span><span class="sxs-lookup"><span data-stu-id="cdc4e-230">You can pipe any .NET object to `ConvertTo-Html`.</span></span>

## <span data-ttu-id="cdc4e-231">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="cdc4e-231">OUTPUTS</span></span>

### <span data-ttu-id="cdc4e-232">System. String или System.Xml.Xmlдокумент</span><span class="sxs-lookup"><span data-stu-id="cdc4e-232">System.String or System.Xml.XmlDocument</span></span>

<span data-ttu-id="cdc4e-233">`ConvertTo-Html` Возвращает ряд строк, составляющих допустимый HTML-код.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-233">`ConvertTo-Html` returns series of strings that comprise valid HTML.</span></span>

## <span data-ttu-id="cdc4e-234">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="cdc4e-234">NOTES</span></span>

<span data-ttu-id="cdc4e-235">Чтобы использовать этот командлет, необходимо передать один или несколько объектов в командлет или использовать параметр **InputObject** для указания объекта.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-235">To use this cmdlet, pipe one or more objects to the cmdlet or use the **InputObject** parameter to specify the object.</span></span> <span data-ttu-id="cdc4e-236">Если входные данные состоят из нескольких объектов, выходные данные этих двух методов отличаются.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-236">When the input consists of multiple objects, the output of these two methods is quite different.</span></span>

- <span data-ttu-id="cdc4e-237">При передаче нескольких объектов в командлет PowerShell посылает объекты в командлет по одному за раз.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-237">When you pipe multiple objects to a cmdlet, PowerShell sends the objects to the cmdlet one at a time.</span></span> <span data-ttu-id="cdc4e-238">В результате `ConvertTo-Html` создается таблица, в которой отображаются отдельные объекты.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-238">As a result, `ConvertTo-Html` creates a table that displays the individual objects.</span></span> <span data-ttu-id="cdc4e-239">Например, если передать процессы на компьютере в `ConvertTo-Html` , в результирующей таблице отобразятся все процессы.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-239">For example, if you pipe the processes on a computer to `ConvertTo-Html`, the resulting table displays all of the processes.</span></span>

- <span data-ttu-id="cdc4e-240">При использовании параметра **InputObject** для отправки нескольких объектов `ConvertTo-Html` получает эти объекты как коллекцию или как массив.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-240">When you use the **InputObject** parameter to submit multiple objects, `ConvertTo-Html` receives these objects as a collection or as an array.</span></span> <span data-ttu-id="cdc4e-241">В результате создается таблица, отображающая массива и его свойства, а не элементы в массиве.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-241">As a result, it creates a table that displays the array and its properties, not the items in the array.</span></span> <span data-ttu-id="cdc4e-242">Например, при использовании **InputObject** для отправки процессов на компьютер в `ConvertTo-Html` результирующая таблица отображает массив объектов и его свойства.</span><span class="sxs-lookup"><span data-stu-id="cdc4e-242">For example, if you use **InputObject** to submit the processes on a computer to `ConvertTo-Html`, the resulting table displays an object array and its properties.</span></span>

  <span data-ttu-id="cdc4e-243">Чтобы обеспечить соответствие стандарту XHTML-DTD, тег DOCTYPE изменяется соответствующим образом:</span><span class="sxs-lookup"><span data-stu-id="cdc4e-243">To comply with the XHTML Strict DTD, the DOCTYPE tag is modified accordingly:</span></span>

   `<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN"   "https://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd"\>`

## <span data-ttu-id="cdc4e-244">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="cdc4e-244">RELATED LINKS</span></span>

[<span data-ttu-id="cdc4e-245">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="cdc4e-245">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="cdc4e-246">ConvertTo-Csv</span><span class="sxs-lookup"><span data-stu-id="cdc4e-246">ConvertTo-Csv</span></span>](ConvertTo-Csv.md)

[<span data-ttu-id="cdc4e-247">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="cdc4e-247">ConvertTo-Json</span></span>](ConvertTo-Json.md)

[<span data-ttu-id="cdc4e-248">ConvertTo-Xml</span><span class="sxs-lookup"><span data-stu-id="cdc4e-248">ConvertTo-Xml</span></span>](ConvertTo-Xml.md)

[<span data-ttu-id="cdc4e-249">Export-Clixml</span><span class="sxs-lookup"><span data-stu-id="cdc4e-249">Export-Clixml</span></span>](Export-Clixml.md)

[<span data-ttu-id="cdc4e-250">Import-Clixml</span><span class="sxs-lookup"><span data-stu-id="cdc4e-250">Import-Clixml</span></span>](Import-Clixml.md)
