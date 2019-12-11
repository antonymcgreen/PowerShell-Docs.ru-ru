---
ms.date: 09/13/2019
title: Создание запросов Get-WinEvent с помощью FilterHashtable
ms.openlocfilehash: 35d18dc894d90e698b38395b79ff4cf395515909
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "73444392"
---
# <a name="creating-get-winevent-queries-with-filterhashtable"></a><span data-ttu-id="a217c-102">Создание запросов Get-WinEvent с помощью FilterHashtable</span><span class="sxs-lookup"><span data-stu-id="a217c-102">Creating Get-WinEvent queries with FilterHashtable</span></span>

<span data-ttu-id="a217c-103">Чтобы прочитать исходную запись блога **специалистов по сценариям** от 3 июня 2014 г., которая называется Use FilterHashTable to Filter Event Log with PowerShell (Использование FilterHashTable для фильтрации журнала событий с помощью PowerShell), перейдите [сюда](https://devblogs.microsoft.com/scripting/use-filterhashtable-to-filter-event-log-with-powershell/).</span><span class="sxs-lookup"><span data-stu-id="a217c-103">To read the original June 3, 2014 **Scripting Guy** blog post, see [Use FilterHashTable to Filter Event Log with PowerShell](https://devblogs.microsoft.com/scripting/use-filterhashtable-to-filter-event-log-with-powershell/).</span></span>

<span data-ttu-id="a217c-104">Эта статья является выдержкой из исходной записи блога. Здесь показано, как использовать параметр **FilterHashtable** командлета `Get-WinEvent` для фильтрации журналов событий.</span><span class="sxs-lookup"><span data-stu-id="a217c-104">This article is an excerpt of the original blog post and explains how to use the `Get-WinEvent` cmdlet's **FilterHashtable** parameter to filter event logs.</span></span> <span data-ttu-id="a217c-105">Использование командлета `Get-WinEvent` PowerShell представляет собой эффективный метод для фильтрации журналов событий и журналов диагностики Windows.</span><span class="sxs-lookup"><span data-stu-id="a217c-105">PowerShell's `Get-WinEvent` cmdlet is a powerful method to filter Windows event and diagnostic logs.</span></span> <span data-ttu-id="a217c-106">Если в запросе `Get-WinEvent` используется параметр **FilterHashtable**, производительность будет более высокой.</span><span class="sxs-lookup"><span data-stu-id="a217c-106">Performance improves when a `Get-WinEvent` query uses the **FilterHashtable** parameter.</span></span>

<span data-ttu-id="a217c-107">При работе с объемными журналами событий отправка объектов по конвейеру команде `Where-Object` не является эффективной.</span><span class="sxs-lookup"><span data-stu-id="a217c-107">When you work with large event logs, it's not efficient to send objects down the pipeline to a `Where-Object` command.</span></span> <span data-ttu-id="a217c-108">До выхода версии PowerShell 6 для получения данных журнала также использовался командлет `Get-EventLog`.</span><span class="sxs-lookup"><span data-stu-id="a217c-108">Prior to PowerShell 6, the `Get-EventLog` cmdlet was another option to get log data.</span></span> <span data-ttu-id="a217c-109">Например, приведенные ниже команды являются неэффективными для фильтрации журналов **Microsoft-Windows-Defrag**:</span><span class="sxs-lookup"><span data-stu-id="a217c-109">For example, the following commands are inefficient to filter the **Microsoft-Windows-Defrag** logs:</span></span>

```powershell
Get-EventLog -LogName Application | Where-Object Source -Match defrag

Get-WinEvent -LogName Application | Where-Object { $_.ProviderName -Match 'defrag' }
```

<span data-ttu-id="a217c-110">В следующей команде используется хэш-таблица, что повышает производительность:</span><span class="sxs-lookup"><span data-stu-id="a217c-110">The following command uses a hash table that improves the performance:</span></span>

```powershell
Get-WinEvent -FilterHashtable @{
   LogName='Application'
   ProviderName='*defrag'
}
```

## <a name="blog-posts-about-enumeration"></a><span data-ttu-id="a217c-111">Записи блога, посвященные перечислению</span><span class="sxs-lookup"><span data-stu-id="a217c-111">Blog posts about enumeration</span></span>

<span data-ttu-id="a217c-112">В этой статье представлены сведения о том, как использовать перечисляемые значения в хэш-таблице.</span><span class="sxs-lookup"><span data-stu-id="a217c-112">This article presents information about how to use enumerated values in a hash table.</span></span> <span data-ttu-id="a217c-113">Дополнительные сведения о перечислении см. в записях блога **специалистов по сценариям**.</span><span class="sxs-lookup"><span data-stu-id="a217c-113">For more information about enumeration, read these **Scripting Guy** blog posts.</span></span> <span data-ttu-id="a217c-114">Сведения для создания функции, возвращающей перечисляемые значения, см. в [этой записи блога](https://devblogs.microsoft.com/scripting/hey-scripting-guy-weekend-scripter-enumerations-and-values).</span><span class="sxs-lookup"><span data-stu-id="a217c-114">To create a function that returns the enumerated values, see [Enumerations and Values](https://devblogs.microsoft.com/scripting/hey-scripting-guy-weekend-scripter-enumerations-and-values).</span></span>
<span data-ttu-id="a217c-115">Дополнительные сведения см. в [ряде записей блога специалистов по сценариям, посвященных перечислению](https://devblogs.microsoft.com/scripting/?s=about+enumeration).</span><span class="sxs-lookup"><span data-stu-id="a217c-115">For more information, see the [Scripting Guy series of blog posts about enumeration](https://devblogs.microsoft.com/scripting/?s=about+enumeration).</span></span>

## <a name="hash-table-key-value-pairs"></a><span data-ttu-id="a217c-116">Пары "ключ — значение" в хэш-таблице</span><span class="sxs-lookup"><span data-stu-id="a217c-116">Hash table key-value pairs</span></span>

<span data-ttu-id="a217c-117">Для создания эффективных запросов используйте командлет `Get-WinEvent` с параметром **FilterHashtable**.</span><span class="sxs-lookup"><span data-stu-id="a217c-117">To build efficient queries, use the `Get-WinEvent` cmdlet with the **FilterHashtable** parameter.</span></span>
<span data-ttu-id="a217c-118">**FilterHashtable** принимает хэш-таблицу в качестве фильтра для получения конкретных сведений из журналов событий Windows.</span><span class="sxs-lookup"><span data-stu-id="a217c-118">**FilterHashtable** accepts a hash table as a filter to get specific information from Windows event logs.</span></span> <span data-ttu-id="a217c-119">Хэш-таблица использует пары **ключ — значение**.</span><span class="sxs-lookup"><span data-stu-id="a217c-119">A hash table uses **key-value** pairs.</span></span> <span data-ttu-id="a217c-120">Дополнительные сведения о хэш-таблицах см. [здесь](/powershell/module/microsoft.powershell.core/about/about_hash_tables).</span><span class="sxs-lookup"><span data-stu-id="a217c-120">For more information about hash tables, see [about_Hash_Tables](/powershell/module/microsoft.powershell.core/about/about_hash_tables).</span></span>

<span data-ttu-id="a217c-121">Если пары **ключ — значение** находятся в одной строке, они должны быть разделены точкой с запятой.</span><span class="sxs-lookup"><span data-stu-id="a217c-121">If the **key-value** pairs are on the same line, they must be separated by a semicolon.</span></span> <span data-ttu-id="a217c-122">Если пары **ключ — значение** находятся в разных строках, точка с запятой не требуется.</span><span class="sxs-lookup"><span data-stu-id="a217c-122">If each **key-value** pair is on a separate line, the semicolon isn't needed.</span></span> <span data-ttu-id="a217c-123">Например, в этой статье пары **ключ — значение** расположены в разных строках и разделены точкой с запятой.</span><span class="sxs-lookup"><span data-stu-id="a217c-123">For example, this article places **key-value** pairs on separate lines and doesn't use semicolons.</span></span>

<span data-ttu-id="a217c-124">В этом примере используется несколько пар **ключ — значение** для параметра **FilterHashtable**.</span><span class="sxs-lookup"><span data-stu-id="a217c-124">This sample uses several of the **FilterHashtable** parameter's **key-value** pairs.</span></span> <span data-ttu-id="a217c-125">Готовый запрос включает в себя значения **LogName**, **ProviderName**, **Keywords**, **ID** и **Level**.</span><span class="sxs-lookup"><span data-stu-id="a217c-125">The completed query includes **LogName**, **ProviderName**, **Keywords**, **ID**, and **Level**.</span></span>

<span data-ttu-id="a217c-126">Допустимые пары **ключ — значение** показаны в следующей таблице и включены в документацию для параметра **FilterHashtable**
командлета [Get-WinEvent](/powershell/module/microsoft.powershell.diagnostics/Get-WinEvent).</span><span class="sxs-lookup"><span data-stu-id="a217c-126">The accepted **key-value** pairs are shown in the following table and are included in the documentation for the [Get-WinEvent](/powershell/module/microsoft.powershell.diagnostics/Get-WinEvent)
**FilterHashtable** parameter.</span></span>

<span data-ttu-id="a217c-127">В следующей таблице приведены имена ключей, типы данных и сведения о том, принимаются ли подстановочные знаки для значения данных.</span><span class="sxs-lookup"><span data-stu-id="a217c-127">The following table displays the key names, data types, and whether wildcard characters are accepted for a data value.</span></span>

|    <span data-ttu-id="a217c-128">Имя ключа</span><span class="sxs-lookup"><span data-stu-id="a217c-128">Key name</span></span>    | <span data-ttu-id="a217c-129">Тип данных значения</span><span class="sxs-lookup"><span data-stu-id="a217c-129">Value data type</span></span> | <span data-ttu-id="a217c-130">Принимает ли подстановочные знаки?</span><span class="sxs-lookup"><span data-stu-id="a217c-130">Accepts wildcard characters?</span></span> |
| -------------- | --------------- | ---------------------------- |
| <span data-ttu-id="a217c-131">LogName</span><span class="sxs-lookup"><span data-stu-id="a217c-131">LogName</span></span>        | `<String[]>`    | <span data-ttu-id="a217c-132">Да</span><span class="sxs-lookup"><span data-stu-id="a217c-132">Yes</span></span>                          |
| <span data-ttu-id="a217c-133">ProviderName</span><span class="sxs-lookup"><span data-stu-id="a217c-133">ProviderName</span></span>   | `<String[]>`    | <span data-ttu-id="a217c-134">Да</span><span class="sxs-lookup"><span data-stu-id="a217c-134">Yes</span></span>                          |
| <span data-ttu-id="a217c-135">путь</span><span class="sxs-lookup"><span data-stu-id="a217c-135">Path</span></span>           | `<String[]>`    | <span data-ttu-id="a217c-136">Нет</span><span class="sxs-lookup"><span data-stu-id="a217c-136">No</span></span>                           |
| <span data-ttu-id="a217c-137">Keywords</span><span class="sxs-lookup"><span data-stu-id="a217c-137">Keywords</span></span>       | `<Long[]>`      | <span data-ttu-id="a217c-138">Нет</span><span class="sxs-lookup"><span data-stu-id="a217c-138">No</span></span>                           |
| <span data-ttu-id="a217c-139">Код</span><span class="sxs-lookup"><span data-stu-id="a217c-139">ID</span></span>             | `<Int32[]>`     | <span data-ttu-id="a217c-140">Нет</span><span class="sxs-lookup"><span data-stu-id="a217c-140">No</span></span>                           |
| <span data-ttu-id="a217c-141">Уровень</span><span class="sxs-lookup"><span data-stu-id="a217c-141">Level</span></span>          | `<Int32[]>`     | <span data-ttu-id="a217c-142">Нет</span><span class="sxs-lookup"><span data-stu-id="a217c-142">No</span></span>                           |
| <span data-ttu-id="a217c-143">StartTime</span><span class="sxs-lookup"><span data-stu-id="a217c-143">StartTime</span></span>      | `<DateTime>`    | <span data-ttu-id="a217c-144">Нет</span><span class="sxs-lookup"><span data-stu-id="a217c-144">No</span></span>                           |
| <span data-ttu-id="a217c-145">EndTime</span><span class="sxs-lookup"><span data-stu-id="a217c-145">EndTime</span></span>        | `<DateTime>`    | <span data-ttu-id="a217c-146">Нет</span><span class="sxs-lookup"><span data-stu-id="a217c-146">No</span></span>                           |
| <span data-ttu-id="a217c-147">UserID</span><span class="sxs-lookup"><span data-stu-id="a217c-147">UserID</span></span>         | `<SID>`         | <span data-ttu-id="a217c-148">Нет</span><span class="sxs-lookup"><span data-stu-id="a217c-148">No</span></span>                           |
| <span data-ttu-id="a217c-149">Данные</span><span class="sxs-lookup"><span data-stu-id="a217c-149">Data</span></span>           | `<String[]>`    | <span data-ttu-id="a217c-150">Нет</span><span class="sxs-lookup"><span data-stu-id="a217c-150">No</span></span>                           |
| `<named-data>` | `<String[]>`    | <span data-ttu-id="a217c-151">Нет</span><span class="sxs-lookup"><span data-stu-id="a217c-151">No</span></span>                           |

<span data-ttu-id="a217c-152">Ключ `<named-data>` представляет именованное поле данных событий.</span><span class="sxs-lookup"><span data-stu-id="a217c-152">The `<named-data>` key represents a named event data field.</span></span> <span data-ttu-id="a217c-153">Например, событие Perflib 1008 может содержать следующие данные о событии:</span><span class="sxs-lookup"><span data-stu-id="a217c-153">For example, the Perflib event 1008 can contain the following event data:</span></span>

```xml
<EventData>
  <Data Name="Service">BITS</Data>
  <Data Name="Library">C:\Windows\System32\bitsperf.dll</Data>
  <Data Name="Win32Error">2</Data>
</EventData>
```

<span data-ttu-id="a217c-154">Эти события можно запросить с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="a217c-154">You can query for these events using the following command:</span></span>

```powershell
Get-WinEvent -FilterHashtable @{LogName='Application'; 'Service'='Bits'}
```

> [!NOTE]
> <span data-ttu-id="a217c-155">Возможность создавать запросы `<named-data>` была добавлена в PowerShell 6.</span><span class="sxs-lookup"><span data-stu-id="a217c-155">The ability to query for `<named-data>` was added in PowerShell 6.</span></span>

## <a name="building-a-query-with-a-hash-table"></a><span data-ttu-id="a217c-156">Создание запроса с использованием хэш-таблицы</span><span class="sxs-lookup"><span data-stu-id="a217c-156">Building a query with a hash table</span></span>

<span data-ttu-id="a217c-157">Для проверки результатов и устранения проблем полезно создавать по одной паре **ключ — значение** для хэш-таблицы за раз.</span><span class="sxs-lookup"><span data-stu-id="a217c-157">To verify results and troubleshoot problems, it helps to build the hash table one **key-value** pair at a time.</span></span> <span data-ttu-id="a217c-158">Запрос получает данные из журнала **Application**.</span><span class="sxs-lookup"><span data-stu-id="a217c-158">The query gets data from the **Application** log.</span></span> <span data-ttu-id="a217c-159">Хэш-таблица создается в результате запроса `Get-WinEvent –LogName Application`.</span><span class="sxs-lookup"><span data-stu-id="a217c-159">The hash table is equivalent to `Get-WinEvent –LogName Application`.</span></span>

<span data-ttu-id="a217c-160">Для начала создайте запрос `Get-WinEvent`.</span><span class="sxs-lookup"><span data-stu-id="a217c-160">To begin, create the `Get-WinEvent` query.</span></span> <span data-ttu-id="a217c-161">Используйте пару **ключ — значение** параметра **FilterHashtable** с ключом **LogName** и значением **Application**.</span><span class="sxs-lookup"><span data-stu-id="a217c-161">Use the **FilterHashtable** parameter's **key-value** pair with the key, **LogName**, and the value, **Application**.</span></span>

```powershell
Get-WinEvent -FilterHashtable @{
   LogName='Application'
}
```

<span data-ttu-id="a217c-162">Продолжайте выполнять сборку хэш-таблицы с использованием ключа **ProviderName**.</span><span class="sxs-lookup"><span data-stu-id="a217c-162">Continue to build the hash table with the **ProviderName** key.</span></span> <span data-ttu-id="a217c-163">**ProviderName** — это имя, отображаемое в поле **источника** в средстве **Просмотра событий Windows**.</span><span class="sxs-lookup"><span data-stu-id="a217c-163">The **ProviderName** is the name that appears in the **Source** field in the **Windows Event Viewer**.</span></span> <span data-ttu-id="a217c-164">Например, **среда выполнения .NET** на следующем снимке экрана:</span><span class="sxs-lookup"><span data-stu-id="a217c-164">For example, **.NET Runtime** in the following screenshot:</span></span>

![Изображение источников в средстве "Просмотр событий Windows".](./media/creating-get-winEvent-queries-with-filterhashtable/providername.png)

<span data-ttu-id="a217c-166">Обновите хэш-таблицу и добавьте пару **ключ — значение** с ключом \*\*ProviderName и значением **.NET Runtime**.</span><span class="sxs-lookup"><span data-stu-id="a217c-166">Update the hash table and include the **key-value** pair with the key, \*\*ProviderName, and the value, **.NET Runtime**.</span></span>

```powershell
Get-WinEvent -FilterHashtable @{
   LogName='Application'
   ProviderName='.NET Runtime'
}
```

<span data-ttu-id="a217c-167">Если запрос должен получить данные из архивных журналов событий, используйте ключ **Path**.</span><span class="sxs-lookup"><span data-stu-id="a217c-167">If your query needs to get data from archived event logs, use the **Path** key.</span></span> <span data-ttu-id="a217c-168">Значение **Path** указывает полный путь к файлу журнала.</span><span class="sxs-lookup"><span data-stu-id="a217c-168">The **Path** value specifies the full path to the log file.</span></span> <span data-ttu-id="a217c-169">Дополнительные сведения см. в записи блога **специалистов по сценариям** [Use PowerShell to Parse Saved Event Logs for Errors](https://devblogs.microsoft.com/scripting/use-powershell-to-parse-saved-event-logs-for-errors) (Анализ сохраненных журналов событий на наличие ошибок с помощью PowerShell).</span><span class="sxs-lookup"><span data-stu-id="a217c-169">For more information, see the **Scripting Guy** blog post, [Use PowerShell to Parse Saved Event Logs for Errors](https://devblogs.microsoft.com/scripting/use-powershell-to-parse-saved-event-logs-for-errors).</span></span>

## <a name="using-enumerated-values-in-a-hash-table"></a><span data-ttu-id="a217c-170">Использование перечисляемых значений в хэш-таблице</span><span class="sxs-lookup"><span data-stu-id="a217c-170">Using enumerated values in a hash table</span></span>

<span data-ttu-id="a217c-171">**Keywords** — следующий ключ в хэш-таблице.</span><span class="sxs-lookup"><span data-stu-id="a217c-171">**Keywords** is the next key in the hash table.</span></span> <span data-ttu-id="a217c-172">Тип данных **Keywords** представляет собой массив типа значения `[long]`, который содержит большое число.</span><span class="sxs-lookup"><span data-stu-id="a217c-172">The **Keywords** data type is an array of the `[long]` value type that holds a large number.</span></span> <span data-ttu-id="a217c-173">Используйте следующую команду, чтобы найти максимальное значение `[long]`:</span><span class="sxs-lookup"><span data-stu-id="a217c-173">Use the following command to find the maximum value of `[long]`:</span></span>

```powershell
[long]::MaxValue
```

```Output
9223372036854775807
```

<span data-ttu-id="a217c-174">Для ключа **Keywords** PowerShell использует число, а не строку, такую как **Security**.</span><span class="sxs-lookup"><span data-stu-id="a217c-174">For the **Keywords** key, PowerShell uses a number, not a string such as **Security**.</span></span> <span data-ttu-id="a217c-175">В средстве **Просмотр событий Windows** значения **Keywords** отображаются в виде строк, но они являются перечисляемыми значениями.</span><span class="sxs-lookup"><span data-stu-id="a217c-175">**Windows Event Viewer** displays the **Keywords** as strings, but they are enumerated values.</span></span> <span data-ttu-id="a217c-176">Если вы используете ключ **Keywords** со строковым значением, в хэш-таблице отображается сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="a217c-176">In the hash table, if you use the **Keywords** key with a string value, an error message is displayed.</span></span>

<span data-ttu-id="a217c-177">Откройте средство **Просмотр событий Windows** и в окне **Действия** щелкните **Фильтровать текущий журнал**.</span><span class="sxs-lookup"><span data-stu-id="a217c-177">Open the **Windows Event Viewer** and from the **Actions** pane, click on **Filter current log**.</span></span>
<span data-ttu-id="a217c-178">В раскрывающемся меню **Ключевые слова** отображаются доступные ключевые слова, как показано на следующем снимке экрана:</span><span class="sxs-lookup"><span data-stu-id="a217c-178">The **Keywords** drop-down menu displays the available keywords, as shown in the following screenshot:</span></span>

![Изображение ключевых слов средства "Просмотр событий Windows".](./media/creating-get-winEvent-queries-with-filterhashtable/keywords.png)

<span data-ttu-id="a217c-180">Используйте следующую команду для отображения имен свойств `StandardEventKeywords`.</span><span class="sxs-lookup"><span data-stu-id="a217c-180">Use the following command to display the `StandardEventKeywords` property names.</span></span>

```powershell
[System.Diagnostics.Eventing.Reader.StandardEventKeywords] | Get-Member -Static -MemberType Property
```

```Output
   TypeName: System.Diagnostics.Eventing.Reader.StandardEventKeywords
Name             MemberType Definition
—-             ———- ———-
AuditFailure     Property   static System.Diagnostics.Eventing.Reader.StandardEventKey…
AuditSuccess     Property   static System.Diagnostics.Eventing.Reader.StandardEventKey…
CorrelationHint  Property   static System.Diagnostics.Eventing.Reader.StandardEventKey…
CorrelationHint2 Property   static System.Diagnostics.Eventing.Reader.StandardEventKey…
EventLogClassic  Property   static System.Diagnostics.Eventing.Reader.StandardEventKey…
None             Property   static System.Diagnostics.Eventing.Reader.StandardEventKey…
ResponseTime     Property   static System.Diagnostics.Eventing.Reader.StandardEventKey…
Sqm              Property   static System.Diagnostics.Eventing.Reader.StandardEventKey…
WdiContext       Property   static System.Diagnostics.Eventing.Reader.StandardEventKey…
WdiDiagnostic    Property   static System.Diagnostics.Eventing.Reader.StandardEventKey…
```

<span data-ttu-id="a217c-181">Перечисляемые значения описаны в **.NET Framework**.</span><span class="sxs-lookup"><span data-stu-id="a217c-181">The enumerated values are documented in the **.NET Framework**.</span></span> <span data-ttu-id="a217c-182">Дополнительные сведения см. в разделе о команде перечисления [StandardEventKeywords](/dotnet/api/system.diagnostics.eventing.reader.standardeventkeywords?redirectedfrom=MSDN&view=netframework-4.7.2).</span><span class="sxs-lookup"><span data-stu-id="a217c-182">For more information, see [StandardEventKeywords Enumeration](/dotnet/api/system.diagnostics.eventing.reader.standardeventkeywords?redirectedfrom=MSDN&view=netframework-4.7.2).</span></span>

<span data-ttu-id="a217c-183">Имена **ключевых слов** и перечисляемые значения выглядят следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a217c-183">The **Keywords** names and enumerated values are as follows:</span></span>

| <span data-ttu-id="a217c-184">Name</span><span class="sxs-lookup"><span data-stu-id="a217c-184">Name</span></span>             |  <span data-ttu-id="a217c-185">Значение</span><span class="sxs-lookup"><span data-stu-id="a217c-185">Value</span></span>            |
| ---------------- | ------------------|
| <span data-ttu-id="a217c-186">AuditFailure</span><span class="sxs-lookup"><span data-stu-id="a217c-186">AuditFailure</span></span>     | <span data-ttu-id="a217c-187">4503599627370496</span><span class="sxs-lookup"><span data-stu-id="a217c-187">4503599627370496</span></span>  |
| <span data-ttu-id="a217c-188">AuditSuccess</span><span class="sxs-lookup"><span data-stu-id="a217c-188">AuditSuccess</span></span>     | <span data-ttu-id="a217c-189">9007199254740992</span><span class="sxs-lookup"><span data-stu-id="a217c-189">9007199254740992</span></span>  |
| <span data-ttu-id="a217c-190">CorrelationHint2</span><span class="sxs-lookup"><span data-stu-id="a217c-190">CorrelationHint2</span></span> | <span data-ttu-id="a217c-191">18014398509481984</span><span class="sxs-lookup"><span data-stu-id="a217c-191">18014398509481984</span></span> |
| <span data-ttu-id="a217c-192">EventLogClassic</span><span class="sxs-lookup"><span data-stu-id="a217c-192">EventLogClassic</span></span>  | <span data-ttu-id="a217c-193">36028797018963968</span><span class="sxs-lookup"><span data-stu-id="a217c-193">36028797018963968</span></span> |
| <span data-ttu-id="a217c-194">Sqm</span><span class="sxs-lookup"><span data-stu-id="a217c-194">Sqm</span></span>              | <span data-ttu-id="a217c-195">2251799813685248</span><span class="sxs-lookup"><span data-stu-id="a217c-195">2251799813685248</span></span>  |
| <span data-ttu-id="a217c-196">WdiDiagnostic</span><span class="sxs-lookup"><span data-stu-id="a217c-196">WdiDiagnostic</span></span>    | <span data-ttu-id="a217c-197">1125899906842624</span><span class="sxs-lookup"><span data-stu-id="a217c-197">1125899906842624</span></span>  |
| <span data-ttu-id="a217c-198">WdiContext</span><span class="sxs-lookup"><span data-stu-id="a217c-198">WdiContext</span></span>       | <span data-ttu-id="a217c-199">562949953421312</span><span class="sxs-lookup"><span data-stu-id="a217c-199">562949953421312</span></span>   |
| <span data-ttu-id="a217c-200">ResponseTime</span><span class="sxs-lookup"><span data-stu-id="a217c-200">ResponseTime</span></span>     | <span data-ttu-id="a217c-201">281474976710656</span><span class="sxs-lookup"><span data-stu-id="a217c-201">281474976710656</span></span>   |
| <span data-ttu-id="a217c-202">Нет</span><span class="sxs-lookup"><span data-stu-id="a217c-202">None</span></span>             | <span data-ttu-id="a217c-203">0</span><span class="sxs-lookup"><span data-stu-id="a217c-203">0</span></span>                 |

<span data-ttu-id="a217c-204">Обновите хэш-таблицу и добавьте пару **ключ — значение** с ключом **Keywords** и значением перечисления **EventLogClassic** **36028797018963968** .</span><span class="sxs-lookup"><span data-stu-id="a217c-204">Update the hash table and include the **key-value** pair with the key, **Keywords**, and the **EventLogClassic** enumeration value, **36028797018963968**.</span></span>

```powershell
Get-WinEvent -FilterHashtable @{
   LogName='Application'
   ProviderName='.NET Runtime'
   Keywords=36028797018963968
}
```

### <a name="keywords-static-property-value-optional"></a><span data-ttu-id="a217c-205">Значение статического свойства Keywords (необязательно)</span><span class="sxs-lookup"><span data-stu-id="a217c-205">Keywords static property value (optional)</span></span>

<span data-ttu-id="a217c-206">Значение ключа **Keywords** перечисляется, но имя статического свойства можно использовать в запросе с хэш-таблицей.</span><span class="sxs-lookup"><span data-stu-id="a217c-206">The **Keywords** key is enumerated, but you can use a static property name in the hash table query.</span></span>
<span data-ttu-id="a217c-207">Вместо того чтобы использовать возвращаемую строку, имя свойства должно преобразовываться в значение с применением свойства **Value__** .</span><span class="sxs-lookup"><span data-stu-id="a217c-207">Rather than using the returned string, the property name must be converted to a value with the **Value__** property.</span></span>

<span data-ttu-id="a217c-208">Например, следующий скрипт использует свойство **Value__** .</span><span class="sxs-lookup"><span data-stu-id="a217c-208">For example, the following script uses the **Value__** property.</span></span>

```powershell
$C = [System.Diagnostics.Eventing.Reader.StandardEventKeywords]::EventLogClassic
Get-WinEvent -FilterHashtable @{
   LogName='Application'
   ProviderName='.NET Runtime'
   Keywords=$C.Value__
}
```

## <a name="filtering-by-event-id"></a><span data-ttu-id="a217c-209">Фильтрация по идентификатору события</span><span class="sxs-lookup"><span data-stu-id="a217c-209">Filtering by Event Id</span></span>

<span data-ttu-id="a217c-210">Для получения более конкретных данных результаты запроса можно отфильтровать по **идентификатору события**. **Идентификатор события** указывается в хэш-таблице как ключ **ID**, а значение соответствует конкретному **идентификатору события**. В средстве **Просмотр событий Windows** отображается **идентификатор события**. В этом примере используется **идентификатор события 1023**.</span><span class="sxs-lookup"><span data-stu-id="a217c-210">To get more specific data, the query's results are filtered by **Event Id**. The **Event Id** is referenced in the hash table as the key **ID** and the value is a specific **Event Id**. The **Windows Event Viewer** displays the **Event Id**. This example uses **Event Id 1023**.</span></span>

<span data-ttu-id="a217c-211">Обновите хэш-таблицу и добавьте пару **ключ — значение** с ключом **ID** и значением **1023**.</span><span class="sxs-lookup"><span data-stu-id="a217c-211">Update the hash table and include the **key-value** pair with the key, **ID** and the value, **1023**.</span></span>

```powershell
Get-WinEvent -FilterHashtable @{
   LogName='Application'
   ProviderName='.NET Runtime'
   Keywords=36028797018963968
   ID=1023
}
```

## <a name="filtering-by-level"></a><span data-ttu-id="a217c-212">Фильтрация по уровню</span><span class="sxs-lookup"><span data-stu-id="a217c-212">Filtering by Level</span></span>

<span data-ttu-id="a217c-213">Чтобы дополнительно уточнить результаты и включить только события, которые являются ошибками, используйте ключ **Level**.</span><span class="sxs-lookup"><span data-stu-id="a217c-213">To further refine the results and include only events that are errors, use the **Level** key.</span></span>
<span data-ttu-id="a217c-214">В средстве **Просмотр событий Windows** значения **Level** отображаются в виде строковых значений, но они являются перечисляемыми значениями.</span><span class="sxs-lookup"><span data-stu-id="a217c-214">**Windows Event Viewer** displays the **Level** as string values, but they are enumerated values.</span></span> <span data-ttu-id="a217c-215">Если вы используете ключ **Level** со строковым значением, в хэш-таблице отображается сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="a217c-215">In the hash table, if you use the **Level** key with a string value, an error message is displayed.</span></span>

<span data-ttu-id="a217c-216">У ключа **Level** есть такие значения, как **Error** (Ошибка), **Warning** (Предупреждение) или **Informational** (Информация).</span><span class="sxs-lookup"><span data-stu-id="a217c-216">**Level** has values such as **Error**, **Warning**, or **Informational**.</span></span> <span data-ttu-id="a217c-217">Используйте следующую команду для отображения имен свойств `StandardEventLevel`.</span><span class="sxs-lookup"><span data-stu-id="a217c-217">Use the following command to display the `StandardEventLevel` property names.</span></span>

```powershell
[System.Diagnostics.Eventing.Reader.StandardEventLevel] | Get-Member -Static -MemberType Property
```

```Output
   TypeName: System.Diagnostics.Eventing.Reader.StandardEventLevel

Name          MemberType Definition
----          ---------- ----------
Critical      Property   static System.Diagnostics.Eventing.Reader.StandardEventLevel Critical {get;}
Error         Property   static System.Diagnostics.Eventing.Reader.StandardEventLevel Error {get;}
Informational Property   static System.Diagnostics.Eventing.Reader.StandardEventLevel Informational {get;}
LogAlways     Property   static System.Diagnostics.Eventing.Reader.StandardEventLevel LogAlways {get;}
Verbose       Property   static System.Diagnostics.Eventing.Reader.StandardEventLevel Verbose {get;}
Warning       Property   static System.Diagnostics.Eventing.Reader.StandardEventLevel Warning {get;}
```

<span data-ttu-id="a217c-218">Перечисляемые значения описаны в **.NET Framework**.</span><span class="sxs-lookup"><span data-stu-id="a217c-218">The enumerated values are documented in the **.NET Framework**.</span></span> <span data-ttu-id="a217c-219">Дополнительные сведения см. в разделе о команде перечисления [StandardEventLevel](/dotnet/api/system.diagnostics.eventing.reader.standardeventlevel?redirectedfrom=MSDN&view=netframework-4.7.2).</span><span class="sxs-lookup"><span data-stu-id="a217c-219">For more information, see [StandardEventLevel Enumeration](/dotnet/api/system.diagnostics.eventing.reader.standardeventlevel?redirectedfrom=MSDN&view=netframework-4.7.2).</span></span>

<span data-ttu-id="a217c-220">Имена ключа **Level** и перечисляемые значения выглядят следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a217c-220">The **Level** key's names and enumerated values are as follows:</span></span>

| <span data-ttu-id="a217c-221">Name</span><span class="sxs-lookup"><span data-stu-id="a217c-221">Name</span></span>           | <span data-ttu-id="a217c-222">Значение</span><span class="sxs-lookup"><span data-stu-id="a217c-222">Value</span></span> |
| -------------- | ----- |
| <span data-ttu-id="a217c-223">Verbose</span><span class="sxs-lookup"><span data-stu-id="a217c-223">Verbose</span></span>        |   <span data-ttu-id="a217c-224">5</span><span class="sxs-lookup"><span data-stu-id="a217c-224">5</span></span>   |
| <span data-ttu-id="a217c-225">Informational</span><span class="sxs-lookup"><span data-stu-id="a217c-225">Informational</span></span>  |   <span data-ttu-id="a217c-226">4</span><span class="sxs-lookup"><span data-stu-id="a217c-226">4</span></span>   |
| <span data-ttu-id="a217c-227">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="a217c-227">Warning</span></span>        |   <span data-ttu-id="a217c-228">3</span><span class="sxs-lookup"><span data-stu-id="a217c-228">3</span></span>   |
| <span data-ttu-id="a217c-229">Ошибка</span><span class="sxs-lookup"><span data-stu-id="a217c-229">Error</span></span>          |   <span data-ttu-id="a217c-230">2</span><span class="sxs-lookup"><span data-stu-id="a217c-230">2</span></span>   |
| <span data-ttu-id="a217c-231">Critical</span><span class="sxs-lookup"><span data-stu-id="a217c-231">Critical</span></span>       |   <span data-ttu-id="a217c-232">1</span><span class="sxs-lookup"><span data-stu-id="a217c-232">1</span></span>   |
| <span data-ttu-id="a217c-233">LogAlways</span><span class="sxs-lookup"><span data-stu-id="a217c-233">LogAlways</span></span>      |   <span data-ttu-id="a217c-234">0</span><span class="sxs-lookup"><span data-stu-id="a217c-234">0</span></span>   |

<span data-ttu-id="a217c-235">Хэш-таблица для готового запроса содержит ключ **Level** и его значение — **2**.</span><span class="sxs-lookup"><span data-stu-id="a217c-235">The hash table for the completed query includes the key, **Level**, and the value, **2**.</span></span>

```powershell
Get-WinEvent -FilterHashtable @{
   LogName='Application'
   ProviderName='.NET Runtime'
   Keywords=36028797018963968
   ID=1023
   Level=2
}
```

### <a name="level-static-property-in-enumeration-optional"></a><span data-ttu-id="a217c-236">Статическое свойство уровня в перечислении (необязательно)</span><span class="sxs-lookup"><span data-stu-id="a217c-236">Level static property in enumeration (optional)</span></span>

<span data-ttu-id="a217c-237">Значение ключа **Level** перечисляется, но имя статического свойства можно использовать в запросе к хэш-таблице.</span><span class="sxs-lookup"><span data-stu-id="a217c-237">The **Level** key is enumerated, but you can use a static property name in the hash table query.</span></span>
<span data-ttu-id="a217c-238">Вместо того чтобы использовать возвращаемую строку, имя свойства должно преобразовываться в значение с применением свойства **Value__** .</span><span class="sxs-lookup"><span data-stu-id="a217c-238">Rather than using the returned string, the property name must be converted to a value with the **Value__** property.</span></span>

<span data-ttu-id="a217c-239">Например, следующий скрипт использует свойство **Value__** .</span><span class="sxs-lookup"><span data-stu-id="a217c-239">For example, the following script uses the **Value__** property.</span></span>

```powershell
$C = [System.Diagnostics.Eventing.Reader.StandardEventLevel]::Informational
Get-WinEvent -FilterHashtable @{
   LogName='Application'
   ProviderName='.NET Runtime'
   Keywords=36028797018963968
   ID=1023
   Level=$C.Value__
}
```