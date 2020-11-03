---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 3/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-EventLog
ms.openlocfilehash: ab1a97dc3c78bbfdcc239fd573ef3b1f839e2b21
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "93228398"
---
# <span data-ttu-id="61867-103">Get-EventLog</span><span class="sxs-lookup"><span data-stu-id="61867-103">Get-EventLog</span></span>

## <span data-ttu-id="61867-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="61867-104">SYNOPSIS</span></span>
<span data-ttu-id="61867-105">Возвращает события в журнале событий или список журналов событий на локальном компьютере или на удаленных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="61867-105">Gets the events in an event log, or a list of the event logs, on the local computer or remote computers.</span></span>

## <span data-ttu-id="61867-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="61867-106">SYNTAX</span></span>

### <span data-ttu-id="61867-107">"Автозначение" (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="61867-107">LogName (Default)</span></span>

```
Get-EventLog [-LogName] <String> [-ComputerName <String[]>] [-Newest <Int32>] [-After <DateTime>]
 [-Before <DateTime>] [-UserName <String[]>] [[-InstanceId] <Int64[]>] [-Index <Int32[]>]
 [-EntryType <String[]>] [-Source <String[]>] [-Message <String>] [-AsBaseObject]
 [<CommonParameters>]
```

### <span data-ttu-id="61867-108">Список</span><span class="sxs-lookup"><span data-stu-id="61867-108">List</span></span>

```
Get-EventLog [-ComputerName <String[]>] [-List] [-AsString] [<CommonParameters>]
```

## <span data-ttu-id="61867-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="61867-109">DESCRIPTION</span></span>

<span data-ttu-id="61867-110">`Get-EventLog`Командлет получает события и журналы событий с локальных и удаленных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="61867-110">The `Get-EventLog` cmdlet gets events and event logs from local and remote computers.</span></span> <span data-ttu-id="61867-111">По умолчанию `Get-EventLog` получает журналы с локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="61867-111">By default, `Get-EventLog` gets logs from the local computer.</span></span> <span data-ttu-id="61867-112">Чтобы получить журналы с удаленных компьютеров, используйте параметр **ComputerName** .</span><span class="sxs-lookup"><span data-stu-id="61867-112">To get logs from remote computers, use the **ComputerName** parameter.</span></span>

<span data-ttu-id="61867-113">`Get-EventLog`Для поиска событий можно использовать параметры и значения свойств.</span><span class="sxs-lookup"><span data-stu-id="61867-113">You can use the `Get-EventLog` parameters and property values to search for events.</span></span> <span data-ttu-id="61867-114">Командлет возвращает события, соответствующие указанным значениям свойств.</span><span class="sxs-lookup"><span data-stu-id="61867-114">The cmdlet gets events that match the specified property values.</span></span>

<span data-ttu-id="61867-115">Командлеты PowerShell, которые содержат `EventLog` существительное, работают только с классическими журналами событий Windows, такими как приложение, система или безопасность.</span><span class="sxs-lookup"><span data-stu-id="61867-115">PowerShell cmdlets that contain the `EventLog` noun work only on Windows classic event logs such as Application, System, or Security.</span></span> <span data-ttu-id="61867-116">Для получения журналов, использующих технологию журнала событий Windows в Windows Vista и более поздних версиях Windows, используйте `Get-WinEvent` .</span><span class="sxs-lookup"><span data-stu-id="61867-116">To get logs that use the Windows Event Log technology in Windows Vista and later Windows versions, use `Get-WinEvent`.</span></span>

> [!NOTE]
> <span data-ttu-id="61867-117">`Get-EventLog` использует API Win32, который является устаревшим.</span><span class="sxs-lookup"><span data-stu-id="61867-117">`Get-EventLog` uses a Win32 API that is deprecated.</span></span> <span data-ttu-id="61867-118">Результаты могут быть неточными.</span><span class="sxs-lookup"><span data-stu-id="61867-118">The results may not be accurate.</span></span> <span data-ttu-id="61867-119">`Get-WinEvent`Вместо этого используйте командлет.</span><span class="sxs-lookup"><span data-stu-id="61867-119">Use the `Get-WinEvent` cmdlet instead.</span></span>

## <span data-ttu-id="61867-120">Примеры</span><span class="sxs-lookup"><span data-stu-id="61867-120">EXAMPLES</span></span>

### <span data-ttu-id="61867-121">Пример 1. получение журналов событий на локальном компьютере</span><span class="sxs-lookup"><span data-stu-id="61867-121">Example 1: Get event logs on the local computer</span></span>

<span data-ttu-id="61867-122">В этом примере отображается список журналов событий, доступных на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="61867-122">This example displays the list of event logs that are available on the local computer.</span></span> <span data-ttu-id="61867-123">Имена в столбце log используются с параметром "имя **журнала",** чтобы указать, в каком журнале выполняется поиск событий.</span><span class="sxs-lookup"><span data-stu-id="61867-123">The names in the Log column are used with the **LogName** parameter to specify which log is searched for events.</span></span>

```powershell
Get-EventLog -List
```

```Output
Max(K)   Retain   OverflowAction      Entries  Log
------   ------   --------------      -------  ---
15,168        0   OverwriteAsNeeded   20,792   Application
15,168        0   OverwriteAsNeeded   12,559   System
15,360        0   OverwriteAsNeeded   11,173   Windows PowerShell
```

<span data-ttu-id="61867-124">`Get-EventLog`Командлет использует параметр **List** для вывода доступных журналов.</span><span class="sxs-lookup"><span data-stu-id="61867-124">The `Get-EventLog` cmdlet uses the **List** parameter to display the available logs.</span></span>

### <span data-ttu-id="61867-125">Пример 2. Получение последних записей из журнала событий на локальном компьютере</span><span class="sxs-lookup"><span data-stu-id="61867-125">Example 2: Get recent entries from an event log on the local computer</span></span>

<span data-ttu-id="61867-126">Этот пример получает последние записи из журнала системных событий.</span><span class="sxs-lookup"><span data-stu-id="61867-126">This example gets recent entries from the System event log.</span></span>

```powershell
Get-EventLog -LogName System -Newest 5
```

```Output
Index   Time          EntryType    Source              InstanceID   Message
-----   ----          ---------    ------              ----------   -------
13820   Jan 17 19:16  Error        DCOM                     10016   The description for Event...
13819   Jan 17 19:08  Error        DCOM                     10016   The description for Event...
13818   Jan 17 19:06  Information  Service Control...  1073748864   The start type of the Back...
13817   Jan 17 19:05  Error        DCOM                     10016   The description for Event...
13815   Jan 17 19:03  Information  Microsoft-Windows...        35   The time service is now sync...
```

<span data-ttu-id="61867-127">`Get-EventLog`Командлет использует параметр " **/l** " для указания журнала системных событий.</span><span class="sxs-lookup"><span data-stu-id="61867-127">The `Get-EventLog` cmdlet uses the **LogName** parameter to specify the System event log.</span></span> <span data-ttu-id="61867-128">**Последний** параметр возвращает пять последних событий.</span><span class="sxs-lookup"><span data-stu-id="61867-128">The **Newest** parameter returns the five most recent events.</span></span>

### <span data-ttu-id="61867-129">Пример 3. Поиск всех источников для определенного числа записей в журнале событий</span><span class="sxs-lookup"><span data-stu-id="61867-129">Example 3: Find all sources for a specific number of entries in an event log</span></span>

<span data-ttu-id="61867-130">В этом примере показано, как найти все источники, которые включены в 1000 последних записей в журнале системных событий.</span><span class="sxs-lookup"><span data-stu-id="61867-130">This example shows how to find all of the sources that are included in the 1000 most recent entries in the System event log.</span></span>

```powershell
$Events = Get-EventLog -LogName System -Newest 1000
$Events | Group-Object -Property Source -NoElement | Sort-Object -Property Count -Descending
```

```Output
Count   Name
-----   ----
  110   DCOM
   65   Service Control Manager
   51   Microsoft-Windows-Kern...
   14   EventLog
   14   BTHUSB
   13   Win32k
```

<span data-ttu-id="61867-131">`Get-EventLog`Для указания системного журнала командлет использует параметр " **/l** ".</span><span class="sxs-lookup"><span data-stu-id="61867-131">The `Get-EventLog` cmdlet uses the **LogName** parameter to specify the System log.</span></span> <span data-ttu-id="61867-132">Последний **параметр выбирает** 1000 последних событий.</span><span class="sxs-lookup"><span data-stu-id="61867-132">The **Newest** parameter selects the 1000 most recent events.</span></span> <span data-ttu-id="61867-133">Объекты событий хранятся в `$Events` переменной.</span><span class="sxs-lookup"><span data-stu-id="61867-133">The event objects are stored in the `$Events` variable.</span></span> <span data-ttu-id="61867-134">`$Events`Объекты отправляются по конвейеру в `Group-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="61867-134">The `$Events` objects are sent down the pipeline to the `Group-Object` cmdlet.</span></span>
<span data-ttu-id="61867-135">`Group-Object` использует параметр **Property** для группирования объектов по источнику и подсчитывает количество объектов для каждого источника.</span><span class="sxs-lookup"><span data-stu-id="61867-135">`Group-Object` uses the **Property** parameter to group the objects by source and counts the number of objects for each source.</span></span> <span data-ttu-id="61867-136">Параметр **элемента** удаления удаляет члены группы из выходных данных.</span><span class="sxs-lookup"><span data-stu-id="61867-136">The **NoElement** parameter removes the group members from the output.</span></span>
<span data-ttu-id="61867-137">`Sort-Object`Командлет использует параметр **Property** для сортировки по количеству имен источников.</span><span class="sxs-lookup"><span data-stu-id="61867-137">The `Sort-Object` cmdlet uses the **Property** parameter to sort by the count of each source name.</span></span>
<span data-ttu-id="61867-138">Параметр **сортировки** сортирует список в порядке по числу от самого высокого до самого низкого.</span><span class="sxs-lookup"><span data-stu-id="61867-138">The **Descending** parameter sorts the list in order by count from highest to lowest.</span></span>

### <span data-ttu-id="61867-139">Пример 4. получение событий ошибки из определенного журнала событий</span><span class="sxs-lookup"><span data-stu-id="61867-139">Example 4: Get error events from a specific event log</span></span>

<span data-ttu-id="61867-140">Этот пример получает события ошибки из журнала системных событий.</span><span class="sxs-lookup"><span data-stu-id="61867-140">This example gets error events from the System event log.</span></span>

```powershell
Get-EventLog -LogName System -EntryType Error
```

```Output
Index Time          EntryType   Source  InstanceID Message
----- ----          ---------   ------  ---------- -------
13296 Jan 16 13:53  Error       DCOM    10016 The description for Event ID '10016' in Source...
13291 Jan 16 13:51  Error       DCOM    10016 The description for Event ID '10016' in Source...
13245 Jan 16 11:45  Error       DCOM    10016 The description for Event ID '10016' in Source...
13230 Jan 16 11:07  Error       DCOM    10016 The description for Event ID '10016' in Source...
```

<span data-ttu-id="61867-141">`Get-EventLog`Для указания системного журнала командлет использует параметр " **/l** ".</span><span class="sxs-lookup"><span data-stu-id="61867-141">The `Get-EventLog` cmdlet uses the **LogName** parameter to specify the System log.</span></span> <span data-ttu-id="61867-142">Параметр **EntryType** фильтрует события, чтобы отображались только события ошибок.</span><span class="sxs-lookup"><span data-stu-id="61867-142">The **EntryType** parameter filters the events to show only Error events.</span></span>

### <span data-ttu-id="61867-143">Пример 5. получение событий из журнала событий с идентификатором InstanceId и исходным значением</span><span class="sxs-lookup"><span data-stu-id="61867-143">Example 5: Get events from an event log with an InstanceId and Source value</span></span>

<span data-ttu-id="61867-144">Этот пример получает события из системного журнала для конкретного InstanceId и источника.</span><span class="sxs-lookup"><span data-stu-id="61867-144">This example gets events from the System log for a specific InstanceId and Source.</span></span>

```powershell
Get-EventLog -LogName System -InstanceId 10016 -Source DCOM
```

```Output
Index Time          EntryType  Source  InstanceID  Message
----- ----          ---------  ------  ----------  -------
13245 Jan 16 11:45  Error      DCOM         10016  The description for Event ID '10016' in Source...
13230 Jan 16 11:07  Error      DCOM         10016  The description for Event ID '10016' in Source...
13219 Jan 16 10:00  Error      DCOM         10016  The description for Event ID '10016' in Source...
```

<span data-ttu-id="61867-145">`Get-EventLog`Для указания системного журнала командлет использует параметр " **/l** ".</span><span class="sxs-lookup"><span data-stu-id="61867-145">The `Get-EventLog` cmdlet uses the **LogName** parameter to specify the System log.</span></span> <span data-ttu-id="61867-146">Параметр **InstanceId** выбирает события с указанным идентификатором экземпляра.</span><span class="sxs-lookup"><span data-stu-id="61867-146">The **InstanceID** parameter selects the events with the specified Instance ID.</span></span> <span data-ttu-id="61867-147">Параметр **Source** указывает свойство события.</span><span class="sxs-lookup"><span data-stu-id="61867-147">The **Source** parameter specifies the event property.</span></span>

### <span data-ttu-id="61867-148">Пример 6. получение событий с нескольких компьютеров</span><span class="sxs-lookup"><span data-stu-id="61867-148">Example 6: Get events from multiple computers</span></span>

<span data-ttu-id="61867-149">Эта команда получает события из журнала системных событий на трех компьютерах: Server01, Server02 и Server03.</span><span class="sxs-lookup"><span data-stu-id="61867-149">This command gets the events from the System event log on three computers: Server01, Server02, and Server03.</span></span>

```powershell
Get-EventLog -LogName System -ComputerName Server01, Server02, Server03
```

<span data-ttu-id="61867-150">`Get-EventLog`Для указания системного журнала командлет использует параметр " **/l** ".</span><span class="sxs-lookup"><span data-stu-id="61867-150">The `Get-EventLog` cmdlet uses the **LogName** parameter to specify the System log.</span></span> <span data-ttu-id="61867-151">Параметр **ComputerName** использует строку с разделителями-запятыми для перечисления компьютеров, с которых необходимо получить журналы событий.</span><span class="sxs-lookup"><span data-stu-id="61867-151">The **ComputerName** parameter uses a comma-separated string to list the computers from which you want to get the event logs.</span></span>

### <span data-ttu-id="61867-152">Пример 7. получение всех событий, содержащих определенное слово в сообщении</span><span class="sxs-lookup"><span data-stu-id="61867-152">Example 7: Get all events that include a specific word in the message</span></span>

<span data-ttu-id="61867-153">Эта команда возвращает все события в журнале системных событий, содержащие определенное слово в сообщении о событии.</span><span class="sxs-lookup"><span data-stu-id="61867-153">This command gets all the events in the System event log that contain a specific word in the event's message.</span></span> <span data-ttu-id="61867-154">Возможно, значение указанного параметра **сообщения** включено в содержимое сообщения, но не отображается в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="61867-154">It's possible that your specified **Message** parameter's value is included in the message's content but isn't displayed on the PowerShell console.</span></span>

```powershell
Get-EventLog -LogName System -Message *description*
```

```Output
Index Time          EntryType   Source       InstanceID   Message
----- ----          ---------   ------       ----------   -------
13821 Jan 17 19:17  Error       DCOM              10016   The description for Event ID '10016'...
13820 Jan 17 19:16  Error       DCOM              10016   The description for Event ID '10016'...
13819 Jan 17 19:08  Error       DCOM              10016   The description for Event ID '10016'...
```

<span data-ttu-id="61867-155">`Get-EventLog`Командлет использует параметр " **/l** " для указания журнала системных событий.</span><span class="sxs-lookup"><span data-stu-id="61867-155">The `Get-EventLog` cmdlet uses the **LogName** parameter to specify the System event log.</span></span> <span data-ttu-id="61867-156">Параметр **Message** указывает слово для поиска в поле сообщения каждого события.</span><span class="sxs-lookup"><span data-stu-id="61867-156">The **Message** parameter specifies a word to search for in the message field of each event.</span></span>

### <span data-ttu-id="61867-157">Пример 8. Отображение значений свойств события</span><span class="sxs-lookup"><span data-stu-id="61867-157">Example 8: Display the property values of an event</span></span>

<span data-ttu-id="61867-158">В этом примере показано, как отобразить все свойства и значения события.</span><span class="sxs-lookup"><span data-stu-id="61867-158">This example shows how to display all of an event's properties and values.</span></span>

```powershell
$A = Get-EventLog -LogName System -Newest 1
$A | Select-Object -Property *
```

```Output
EventID            : 10016
MachineName        : localhost
Data               : {}
Index              : 13821
Category           : (0)
CategoryNumber     : 0
EntryType          : Error
Message            : The description for Event ID '10016' in Source 'DCOM'...
Source             : DCOM
ReplacementStrings : {Local,...}
InstanceId         : 10016
TimeGenerated      : 1/17/2019 19:17:23
TimeWritten        : 1/17/2019 19:17:23
UserName           : username
Site               :
Container          :
```

<span data-ttu-id="61867-159">`Get-EventLog`Командлет использует параметр " **/l** " для указания журнала системных событий.</span><span class="sxs-lookup"><span data-stu-id="61867-159">The `Get-EventLog` cmdlet uses the **LogName** parameter to specify the System event log.</span></span> <span data-ttu-id="61867-160">Последний **параметр выбирает** самый последний объект события.</span><span class="sxs-lookup"><span data-stu-id="61867-160">The **Newest** parameter selects the most recent event object.</span></span> <span data-ttu-id="61867-161">Объект хранится в `$A` переменной.</span><span class="sxs-lookup"><span data-stu-id="61867-161">The object is stored in the `$A` variable.</span></span> <span data-ttu-id="61867-162">Объект в `$A` переменной отправляется в командлет по конвейеру `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="61867-162">The object in the `$A` variable is sent down the pipeline to the `Select-Object` cmdlet.</span></span>
<span data-ttu-id="61867-163">`Select-Object` использует параметр **Property** со звездочкой ( `*` ) для выбора всех свойств объекта.</span><span class="sxs-lookup"><span data-stu-id="61867-163">`Select-Object` uses the **Property** parameter with an asterisk (`*`) to select all of the object's properties.</span></span>

### <span data-ttu-id="61867-164">Пример 9. получение событий из журнала событий с помощью источника и идентификатора события</span><span class="sxs-lookup"><span data-stu-id="61867-164">Example 9: Get events from an event log using a source and event ID</span></span>

<span data-ttu-id="61867-165">Этот пример получает события для указанного источника и идентификатора события.</span><span class="sxs-lookup"><span data-stu-id="61867-165">This example gets events for a specified Source and Event ID.</span></span>

```powershell
Get-EventLog -LogName Application -Source Outlook | Where-Object {$_.EventID -eq 63} |
              Select-Object -Property Source, EventID, InstanceId, Message
```

```Output
Source   EventID   InstanceId   Message
------   -------   ----------   -------
Outlook       63   1073741887   The Exchange web service request succeeded.
Outlook       63   1073741887   Outlook detected a change notification.
Outlook       63   1073741887   The Exchange web service request succeeded.
```

<span data-ttu-id="61867-166">`Get-EventLog`Командлет использует параметр " **/l** " для указания журнала событий приложения.</span><span class="sxs-lookup"><span data-stu-id="61867-166">The `Get-EventLog` cmdlet uses the **LogName** parameter to specify the Application event log.</span></span> <span data-ttu-id="61867-167">Параметр **Source** указывает имя приложения, Outlook.</span><span class="sxs-lookup"><span data-stu-id="61867-167">The **Source** parameter specifies the application name, Outlook.</span></span> <span data-ttu-id="61867-168">Объекты отправляются по конвейеру в `Where-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="61867-168">The objects are sent down the pipeline to the `Where-Object` cmdlet.</span></span> <span data-ttu-id="61867-169">Для каждого объекта в конвейере `Where-Object` командлет использует переменную `$_.EventID` для сравнения свойства идентификатора события с указанным значением.</span><span class="sxs-lookup"><span data-stu-id="61867-169">For each object in the pipeline, the `Where-Object` cmdlet uses the variable `$_.EventID` to compare the Event ID property to the specified value.</span></span> <span data-ttu-id="61867-170">Объекты отправляются по конвейеру в `Select-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="61867-170">The objects are sent down the pipeline to the `Select-Object` cmdlet.</span></span> <span data-ttu-id="61867-171">`Select-Object` использует параметр **Property** для выбора свойств, отображаемых в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="61867-171">`Select-Object` uses the **Property** parameter to select the properties to display in the PowerShell console.</span></span>

### <span data-ttu-id="61867-172">Пример 10. получение событий и группировка по свойству</span><span class="sxs-lookup"><span data-stu-id="61867-172">Example 10: Get events and group by a property</span></span>

```powershell
Get-EventLog -LogName System -UserName NT* | Group-Object -Property UserName -NoElement |
              Select-Object -Property Count, Name
```

```Output
Count  Name
-----  ----
6031   NT AUTHORITY\SYSTEM
  42   NT AUTHORITY\LOCAL SERVICE
   4   NT AUTHORITY\NETWORK SERVICE
```

<span data-ttu-id="61867-173">`Get-EventLog`Для указания системного журнала командлет использует параметр " **/l** ".</span><span class="sxs-lookup"><span data-stu-id="61867-173">The `Get-EventLog` cmdlet uses the **LogName** parameter to specify the System log.</span></span> <span data-ttu-id="61867-174">Параметр **username** содержит `*` подстановочный знак звездочки () для указания части имени пользователя.</span><span class="sxs-lookup"><span data-stu-id="61867-174">The **UserName** parameter includes the asterisk (`*`) wildcard to specify a portion of the user name.</span></span> <span data-ttu-id="61867-175">Объекты событий отправляются по конвейеру в `Group-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="61867-175">The event objects are sent down the pipeline to the `Group-Object` cmdlet.</span></span> <span data-ttu-id="61867-176">`Group-Object` использует параметр **Property** , чтобы указать, что свойство **username** используется для группирования объектов и подсчитывает количество объектов для каждого имени пользователя.</span><span class="sxs-lookup"><span data-stu-id="61867-176">`Group-Object` uses the **Property** parameter to specify that the **UserName** property is used to group the objects and count the number of objects for each user name.</span></span> <span data-ttu-id="61867-177">Параметр **элемента** удаления удаляет члены группы из выходных данных.</span><span class="sxs-lookup"><span data-stu-id="61867-177">The **NoElement** parameter removes the group members from the output.</span></span> <span data-ttu-id="61867-178">Объекты отправляются по конвейеру в `Select-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="61867-178">The objects are sent down the pipeline to the `Select-Object` cmdlet.</span></span>
<span data-ttu-id="61867-179">`Select-Object` использует параметр **Property** для выбора свойств, отображаемых в консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="61867-179">`Select-Object` uses the **Property** parameter to select the properties to display in the PowerShell console.</span></span>

### <span data-ttu-id="61867-180">Пример 11. получение событий, произошедших в указанный диапазон дат и времени</span><span class="sxs-lookup"><span data-stu-id="61867-180">Example 11: Get events that occurred during a specific date and time range</span></span>

<span data-ttu-id="61867-181">Этот пример возвращает события ошибки из журнала системных событий для указанного диапазона даты и времени.</span><span class="sxs-lookup"><span data-stu-id="61867-181">This example gets Error events from the System event log for a specified date and time range.</span></span> <span data-ttu-id="61867-182">Параметры **Before** и **After** задают диапазон дат и времени, но исключаются из выходных данных.</span><span class="sxs-lookup"><span data-stu-id="61867-182">The **Before** and **After** parameters set the date and time range but are excluded from the output.</span></span>

```powershell
$Begin = Get-Date -Date '1/17/2019 08:00:00'
$End = Get-Date -Date '1/17/2019 17:00:00'
Get-EventLog -LogName System -EntryType Error -After $Begin -Before $End
```

```Output
Index Time          EntryType   Source   InstanceID  Message
----- ----          ---------   ------   ----------  -------
13821 Jan 17 13:40  Error       DCOM          10016  The description for Event ID...
13820 Jan 17 13:11  Error       DCOM          10016  The description for Event ID...
...
12372 Jan 17 10:08  Error       DCOM          10016  The description for Event ID...
12371 Jan 17 09:04  Error       DCOM          10016  The description for Event ID...
```

<span data-ttu-id="61867-183">`Get-Date`Командлет использует параметр **Date** для указания даты и времени.</span><span class="sxs-lookup"><span data-stu-id="61867-183">The `Get-Date` cmdlet uses the **Date** parameter to specify a date and time.</span></span> <span data-ttu-id="61867-184">Объекты **DateTime** хранятся в `$Begin` `$End` переменных и.</span><span class="sxs-lookup"><span data-stu-id="61867-184">The **DateTime** objects are stored in the `$Begin` and `$End` variables.</span></span> <span data-ttu-id="61867-185">`Get-EventLog`Для указания системного журнала командлет использует параметр " **/l** ".</span><span class="sxs-lookup"><span data-stu-id="61867-185">The `Get-EventLog` cmdlet uses the **LogName** parameter to specify the System log.</span></span> <span data-ttu-id="61867-186">Параметр **EntryType** указывает тип события ошибки.</span><span class="sxs-lookup"><span data-stu-id="61867-186">The **EntryType** parameter specifies the Error event type.</span></span> <span data-ttu-id="61867-187">Диапазон дат и времени задается параметром **After** и `$Begin` переменной и параметром **Before** и `$End` переменной.</span><span class="sxs-lookup"><span data-stu-id="61867-187">The date and time range is set by the **After** parameter and `$Begin` variable and the **Before** parameter and `$End` variable.</span></span>

## <span data-ttu-id="61867-188">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="61867-188">PARAMETERS</span></span>

### <span data-ttu-id="61867-189">-After</span><span class="sxs-lookup"><span data-stu-id="61867-189">-After</span></span>

<span data-ttu-id="61867-190">Возвращает события, произошедшие после указанной даты и времени.</span><span class="sxs-lookup"><span data-stu-id="61867-190">Gets events that occurred after a specified date and time.</span></span> <span data-ttu-id="61867-191">Дата и время параметра **After** исключаются из выходных данных.</span><span class="sxs-lookup"><span data-stu-id="61867-191">The **After** parameter date and time are excluded from the output.</span></span> <span data-ttu-id="61867-192">Введите объект **DateTime** , например значение, возвращаемое `Get-Date` командлетом.</span><span class="sxs-lookup"><span data-stu-id="61867-192">Enter a **DateTime** object, such as the value returned by the `Get-Date` cmdlet.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="61867-193">-Асбасеобжект</span><span class="sxs-lookup"><span data-stu-id="61867-193">-AsBaseObject</span></span>

<span data-ttu-id="61867-194">Указывает, что этот командлет возвращает стандартный объект **System. Diagnostics. EventLogEntry** для каждого события.</span><span class="sxs-lookup"><span data-stu-id="61867-194">Indicates that this cmdlet returns a standard **System.Diagnostics.EventLogEntry** object for each event.</span></span> <span data-ttu-id="61867-195">Без этого параметра `Get-EventLog` возвращает расширенный объект **PSObject** с дополнительными свойствами **EventLogName** , **Source** и **InstanceId** .</span><span class="sxs-lookup"><span data-stu-id="61867-195">Without this parameter, `Get-EventLog` returns an extended **PSObject** object with additional **EventLogName** , **Source** , and **InstanceId** properties.</span></span>

<span data-ttu-id="61867-196">Чтобы увидеть результат этого параметра, передаем события в `Get-Member` командлет и изучите значение **TypeName** в результате.</span><span class="sxs-lookup"><span data-stu-id="61867-196">To see the effect of this parameter, pipe the events to the `Get-Member` cmdlet and examine the **TypeName** value in the result.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="61867-197">-AsString</span><span class="sxs-lookup"><span data-stu-id="61867-197">-AsString</span></span>

<span data-ttu-id="61867-198">Указывает, что этот командлет возвращает выходные данные в виде строк, а не объектов.</span><span class="sxs-lookup"><span data-stu-id="61867-198">Indicates that this cmdlet returns the output as strings, instead of objects.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: List
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="61867-199">— До</span><span class="sxs-lookup"><span data-stu-id="61867-199">-Before</span></span>

<span data-ttu-id="61867-200">Возвращает события, произошедшие до указанной даты и времени.</span><span class="sxs-lookup"><span data-stu-id="61867-200">Gets events that occurred before a specified date and time.</span></span> <span data-ttu-id="61867-201">Дата и время, указанные в параметре **Before** , исключаются из выходных данных.</span><span class="sxs-lookup"><span data-stu-id="61867-201">The **Before** parameter date and time are excluded from the output.</span></span> <span data-ttu-id="61867-202">Введите объект **DateTime** , например значение, возвращаемое `Get-Date` командлетом.</span><span class="sxs-lookup"><span data-stu-id="61867-202">Enter a **DateTime** object, such as the value returned by the `Get-Date` cmdlet.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="61867-203">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="61867-203">-ComputerName</span></span>

<span data-ttu-id="61867-204">Этот параметр указывает имя NetBIOS удаленного компьютера, IP-адрес или полное доменное имя (FQDN).</span><span class="sxs-lookup"><span data-stu-id="61867-204">This parameter specifies a remote computer's NetBIOS name, Internet Protocol (IP) address, or a fully qualified domain name (FQDN).</span></span>

<span data-ttu-id="61867-205">Если параметр **ComputerName** не указан, `Get-EventLog` по умолчанию используется локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="61867-205">If the **ComputerName** parameter isn't specified, `Get-EventLog` defaults to the local computer.</span></span> <span data-ttu-id="61867-206">Параметр также принимает точку (), `.` чтобы указать локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="61867-206">The parameter also accepts a dot (`.`) to specify the local computer.</span></span>

<span data-ttu-id="61867-207">Параметр **ComputerName** не зависит от удаленного взаимодействия Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="61867-207">The **ComputerName** parameter doesn't rely on Windows PowerShell remoting.</span></span> <span data-ttu-id="61867-208">Можно использовать `Get-EventLog` с параметром **ComputerName** , даже если компьютер не настроен для выполнения удаленных команд.</span><span class="sxs-lookup"><span data-stu-id="61867-208">You can use `Get-EventLog` with the **ComputerName** parameter even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="61867-209">-EntryType</span><span class="sxs-lookup"><span data-stu-id="61867-209">-EntryType</span></span>

<span data-ttu-id="61867-210">Указывает тип записи для событий, которые получает этот командлет, в виде массива строк.</span><span class="sxs-lookup"><span data-stu-id="61867-210">Specifies, as a string array, the entry type of the events that this cmdlet gets.</span></span>

<span data-ttu-id="61867-211">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="61867-211">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="61867-212">Ошибка</span><span class="sxs-lookup"><span data-stu-id="61867-212">Error</span></span>
- <span data-ttu-id="61867-213">Сведения</span><span class="sxs-lookup"><span data-stu-id="61867-213">Information</span></span>
- <span data-ttu-id="61867-214">FailureAudit</span><span class="sxs-lookup"><span data-stu-id="61867-214">FailureAudit</span></span>
- <span data-ttu-id="61867-215">SuccessAudit</span><span class="sxs-lookup"><span data-stu-id="61867-215">SuccessAudit</span></span>
- <span data-ttu-id="61867-216">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="61867-216">Warning</span></span>

```yaml
Type: System.String[]
Parameter Sets: LogName
Aliases: ET
Accepted values: Error, Information, FailureAudit, SuccessAudit, Warning

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="61867-217">-Index</span><span class="sxs-lookup"><span data-stu-id="61867-217">-Index</span></span>

<span data-ttu-id="61867-218">Указывает значения индекса, которые необходимо получить из журнала событий.</span><span class="sxs-lookup"><span data-stu-id="61867-218">Specifies the index values to get from the event log.</span></span> <span data-ttu-id="61867-219">Параметр принимает строку значений с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="61867-219">The parameter accepts a comma-separated string of values.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="61867-220">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="61867-220">-InstanceId</span></span>

<span data-ttu-id="61867-221">Указывает идентификаторы экземпляров, которые необходимо получить из журнала событий.</span><span class="sxs-lookup"><span data-stu-id="61867-221">Specifies the Instance IDs to get from the event log.</span></span> <span data-ttu-id="61867-222">Параметр принимает строку значений с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="61867-222">The parameter accepts a comma-separated string of values.</span></span>

```yaml
Type: System.Int64[]
Parameter Sets: LogName
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="61867-223">-List</span><span class="sxs-lookup"><span data-stu-id="61867-223">-List</span></span>

<span data-ttu-id="61867-224">Отображает список журналов событий на компьютере.</span><span class="sxs-lookup"><span data-stu-id="61867-224">Displays the list of event logs on the computer.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: List
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="61867-225">-LogName</span><span class="sxs-lookup"><span data-stu-id="61867-225">-LogName</span></span>

<span data-ttu-id="61867-226">Указывает имя одного журнала событий.</span><span class="sxs-lookup"><span data-stu-id="61867-226">Specifies the name of one event log.</span></span> <span data-ttu-id="61867-227">Чтобы найти имена журналов, используйте `Get-EventLog -List` .</span><span class="sxs-lookup"><span data-stu-id="61867-227">To find the log names use `Get-EventLog -List`.</span></span> <span data-ttu-id="61867-228">Можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="61867-228">Wildcard characters are permitted.</span></span> <span data-ttu-id="61867-229">Этот параметр обязателен.</span><span class="sxs-lookup"><span data-stu-id="61867-229">This parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: LogName
Aliases: LN

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="61867-230">-Message</span><span class="sxs-lookup"><span data-stu-id="61867-230">-Message</span></span>

<span data-ttu-id="61867-231">Указывает строку в сообщении о событии.</span><span class="sxs-lookup"><span data-stu-id="61867-231">Specifies a string in the event message.</span></span> <span data-ttu-id="61867-232">Этот параметр можно использовать для поиска сообщений, содержащих определенные слова или фразы.</span><span class="sxs-lookup"><span data-stu-id="61867-232">You can use this parameter to search for messages that contain certain words or phrases.</span></span> <span data-ttu-id="61867-233">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="61867-233">Wildcards are permitted.</span></span>

```yaml
Type: System.String
Parameter Sets: LogName
Aliases: MSG

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="61867-234">— Самый новый</span><span class="sxs-lookup"><span data-stu-id="61867-234">-Newest</span></span>

<span data-ttu-id="61867-235">Начинается с самых новых событий и получает указанное число событий.</span><span class="sxs-lookup"><span data-stu-id="61867-235">Begins with the newest events and gets the specified number of events.</span></span> <span data-ttu-id="61867-236">Например, требуется указать количество событий `-Newest 100` .</span><span class="sxs-lookup"><span data-stu-id="61867-236">The number of events is required, for example `-Newest 100`.</span></span> <span data-ttu-id="61867-237">Указывает максимальное число возвращаемых событий.</span><span class="sxs-lookup"><span data-stu-id="61867-237">Specifies the maximum number of events that are returned.</span></span>

```yaml
Type: System.Int32
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="61867-238">-Source</span><span class="sxs-lookup"><span data-stu-id="61867-238">-Source</span></span>

<span data-ttu-id="61867-239">Указывает в виде массива строк источники, записанные в журнал, который получает этот командлет.</span><span class="sxs-lookup"><span data-stu-id="61867-239">Specifies, as a string array, sources that were written to the log that this cmdlet gets.</span></span> <span data-ttu-id="61867-240">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="61867-240">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LogName
Aliases: ABO

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="61867-241">-UserName</span><span class="sxs-lookup"><span data-stu-id="61867-241">-UserName</span></span>

<span data-ttu-id="61867-242">Указывает в виде строкового массива имена пользователей, связанные с событиями.</span><span class="sxs-lookup"><span data-stu-id="61867-242">Specifies, as a string array, user names that are associated with events.</span></span> <span data-ttu-id="61867-243">Введите имена или шаблоны имен, например `User01` , `User*` или `Domain01\User*` .</span><span class="sxs-lookup"><span data-stu-id="61867-243">Enter names or name patterns, such as `User01`, `User*`, or `Domain01\User*`.</span></span> <span data-ttu-id="61867-244">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="61867-244">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="61867-245">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="61867-245">CommonParameters</span></span>

<span data-ttu-id="61867-246">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="61867-246">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="61867-247">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="61867-247">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="61867-248">Входные данные</span><span class="sxs-lookup"><span data-stu-id="61867-248">INPUTS</span></span>

### <span data-ttu-id="61867-249">Нет</span><span class="sxs-lookup"><span data-stu-id="61867-249">None</span></span>

<span data-ttu-id="61867-250">Вы не можете передать входные данные в `Get-EventLog` .</span><span class="sxs-lookup"><span data-stu-id="61867-250">You cannot pipe input to `Get-EventLog`.</span></span>

## <span data-ttu-id="61867-251">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="61867-251">OUTPUTS</span></span>

### <span data-ttu-id="61867-252">System. Diagnostics. EventLogEntry.</span><span class="sxs-lookup"><span data-stu-id="61867-252">System.Diagnostics.EventLogEntry.</span></span> <span data-ttu-id="61867-253">System. Diagnostics. EventLog.</span><span class="sxs-lookup"><span data-stu-id="61867-253">System.Diagnostics.EventLog.</span></span> <span data-ttu-id="61867-254">System.String</span><span class="sxs-lookup"><span data-stu-id="61867-254">System.String</span></span>

<span data-ttu-id="61867-255">Если указан параметр " **/l** ", выходные данные представляют собой коллекцию объектов **System. Diagnostics. EventLogEntry** .</span><span class="sxs-lookup"><span data-stu-id="61867-255">If the **LogName** parameter is specified, the output is a collection of **System.Diagnostics.EventLogEntry** objects.</span></span>

<span data-ttu-id="61867-256">Если указан только параметр **List** , то выходные данные представляют собой коллекцию объектов **System. Diagnostics. EventLog** .</span><span class="sxs-lookup"><span data-stu-id="61867-256">If only the **List** parameter is specified, the output is a collection of **System.Diagnostics.EventLog** objects.</span></span>

<span data-ttu-id="61867-257">Если указаны оба параметра **List** и **AsString** , то выходные данные представляют собой коллекцию объектов **System. String** .</span><span class="sxs-lookup"><span data-stu-id="61867-257">If both the **List** and **AsString** parameters are specified, the output is a collection of **System.String** objects.</span></span>

## <span data-ttu-id="61867-258">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="61867-258">NOTES</span></span>

<span data-ttu-id="61867-259">Командлеты `Get-EventLog` и `Get-WinEvent` не поддерживаются в среда предустановки Windows (Windows PE).</span><span class="sxs-lookup"><span data-stu-id="61867-259">The cmdlets `Get-EventLog` and `Get-WinEvent` are not supported in the Windows Preinstallation Environment (Windows PE).</span></span>

## <span data-ttu-id="61867-260">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="61867-260">RELATED LINKS</span></span>

[<span data-ttu-id="61867-261">Clear-EventLog</span><span class="sxs-lookup"><span data-stu-id="61867-261">Clear-EventLog</span></span>](Clear-EventLog.md)

[<span data-ttu-id="61867-262">Get-WinEvent</span><span class="sxs-lookup"><span data-stu-id="61867-262">Get-WinEvent</span></span>](../Microsoft.PowerShell.Diagnostics/Get-WinEvent.md)

[<span data-ttu-id="61867-263">Group-Object</span><span class="sxs-lookup"><span data-stu-id="61867-263">Group-Object</span></span>](../Microsoft.PowerShell.Utility/Group-Object.md)

[<span data-ttu-id="61867-264">Limit-EventLog</span><span class="sxs-lookup"><span data-stu-id="61867-264">Limit-EventLog</span></span>](Limit-EventLog.md)

[<span data-ttu-id="61867-265">New-EventLog</span><span class="sxs-lookup"><span data-stu-id="61867-265">New-EventLog</span></span>](New-EventLog.md)

[<span data-ttu-id="61867-266">Remove-EventLog</span><span class="sxs-lookup"><span data-stu-id="61867-266">Remove-EventLog</span></span>](Remove-EventLog.md)

[<span data-ttu-id="61867-267">Select-Object</span><span class="sxs-lookup"><span data-stu-id="61867-267">Select-Object</span></span>](../Microsoft.PowerShell.Utility/Select-Object.md)

[<span data-ttu-id="61867-268">Show-EventLog</span><span class="sxs-lookup"><span data-stu-id="61867-268">Show-EventLog</span></span>](Show-EventLog.md)

[<span data-ttu-id="61867-269">Write-EventLog</span><span class="sxs-lookup"><span data-stu-id="61867-269">Write-EventLog</span></span>](Write-EventLog.md)
