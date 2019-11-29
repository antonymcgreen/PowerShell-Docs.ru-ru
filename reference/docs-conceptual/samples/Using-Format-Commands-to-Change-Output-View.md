---
ms.date: 11/22/2019
keywords: powershell,командлет
title: Использование команд Format для изменения представления вывода
ms.openlocfilehash: f270d5ec5efe5caf506d6a8a45285990996f6ae6
ms.sourcegitcommit: d43f66071f1f33b350d34fa1f46f3a35910c5d24
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74417590"
---
# <a name="using-format-commands-to-change-output-view"></a><span data-ttu-id="d3ef2-103">Использование команд Format для изменения представления вывода</span><span class="sxs-lookup"><span data-stu-id="d3ef2-103">Using Format Commands to Change Output View</span></span>

<span data-ttu-id="d3ef2-104">PowerShell предоставляет набор командлетов, которые позволяют контролировать, какие свойства должны отображаться для определенных объектов.</span><span class="sxs-lookup"><span data-stu-id="d3ef2-104">PowerShell has a set of cmdlets that allow you to control how properties are displayed for particular objects.</span></span> <span data-ttu-id="d3ef2-105">Имена всех этих командлетов начинаются глаголом `Format`.</span><span class="sxs-lookup"><span data-stu-id="d3ef2-105">The names of all the cmdlets begin with the verb `Format`.</span></span> <span data-ttu-id="d3ef2-106">Они позволяют выбрать, какие свойства будут отображаться.</span><span class="sxs-lookup"><span data-stu-id="d3ef2-106">They let you select which properties you want to show.</span></span>

```powershell
Get-Command -Verb Format -Module Microsoft.PowerShell.Utility
```

```Output
CommandType     Name               Version    Source
-----------     ----               -------    ------
Cmdlet          Format-Custom      6.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Format-Hex         6.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Format-List        6.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Format-Table       6.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Format-Wide        6.1.0.0    Microsoft.PowerShell.Utility
```

<span data-ttu-id="d3ef2-107">В этой статье описываются командлеты `Format-Wide`, `Format-List` и `Format-Table`.</span><span class="sxs-lookup"><span data-stu-id="d3ef2-107">This article describes the `Format-Wide`, `Format-List`, and `Format-Table` cmdlets.</span></span>

<span data-ttu-id="d3ef2-108">У каждого типа объектов в PowerShell есть свойства по умолчанию, которые используются, если вы не настроили отображаемые свойства.</span><span class="sxs-lookup"><span data-stu-id="d3ef2-108">Each object type in PowerShell has default properties that are used when you don't specify which properties to display.</span></span> <span data-ttu-id="d3ef2-109">Для указания свойств, которые нужно отобразить, каждый командлет использует один и тот же параметр **Property**.</span><span class="sxs-lookup"><span data-stu-id="d3ef2-109">Each cmdlet also uses the same **Property** parameter to specify which properties you want to display.</span></span> <span data-ttu-id="d3ef2-110">Так как `Format-Wide` отображает только одно свойство, в параметре **Property** он принимает только одно значение, тогда как `Format-List` и `Format-Table` поддерживают списки с именами свойств.</span><span class="sxs-lookup"><span data-stu-id="d3ef2-110">Because `Format-Wide` only shows a single property, its **Property** parameter only takes a single value, but the property parameters of `Format-List` and `Format-Table` accept a list of property names.</span></span>

<span data-ttu-id="d3ef2-111">В этом примере стандартные выходные данные командлета `Get-Process` показывают, что работают два экземпляра Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="d3ef2-111">In this example, the default output of `Get-Process` cmdlet shows that we have two instances of Internet Explorer running.</span></span>

```powershell
Get-Process -Name iexplore
```

<span data-ttu-id="d3ef2-112">Для объектов **Process** по умолчанию применяется формат со следующими свойствами.</span><span class="sxs-lookup"><span data-stu-id="d3ef2-112">The default format for **Process** objects displays the properties shown here:</span></span>

```Output
 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
     32    25.52      10.25      13.11   12808   1 iexplore
     52    11.46      26.46       3.55   21748   1 iexplore
```

## <a name="using-format-wide-for-single-item-output"></a><span data-ttu-id="d3ef2-113">Применение командлета Format-Wide для вывода с одним элементом</span><span class="sxs-lookup"><span data-stu-id="d3ef2-113">Using Format-Wide for Single-Item Output</span></span>

<span data-ttu-id="d3ef2-114">По умолчанию командлет `Format-Wide` отображает только свойство по умолчанию для объекта.</span><span class="sxs-lookup"><span data-stu-id="d3ef2-114">The `Format-Wide` cmdlet, by default, displays only the default property of an object.</span></span> <span data-ttu-id="d3ef2-115">Данные, связанные с каждым объектом, отображаются в одном столбце:</span><span class="sxs-lookup"><span data-stu-id="d3ef2-115">The information associated with each object is displayed in a single column:</span></span>

```powershell
Get-Command -Verb Format | Format-Wide
```

```Output
Format-Custom          Format-Hex
Format-List            Format-Table
Format-Wide
```

<span data-ttu-id="d3ef2-116">Можно также задать свойство, отличное от используемого по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="d3ef2-116">You can also specify a non-default property:</span></span>

```powershell
Get-Command -Verb Format | Format-Wide -Property Noun
```

```Output
Custom                 Hex
List                   Table
Wide
```

### <a name="controlling-format-wide-display-with-column"></a><span data-ttu-id="d3ef2-117">Настройка отображения командлета Format-Wide с помощью параметра Column</span><span class="sxs-lookup"><span data-stu-id="d3ef2-117">Controlling Format-Wide Display with Column</span></span>

<span data-ttu-id="d3ef2-118">С помощью командлета `Format-Wide` одновременно можно отобразить только одно свойство.</span><span class="sxs-lookup"><span data-stu-id="d3ef2-118">With the `Format-Wide` cmdlet, you can only display a single property at a time.</span></span> <span data-ttu-id="d3ef2-119">Это удобно для отображения больших списков в нескольких столбцах.</span><span class="sxs-lookup"><span data-stu-id="d3ef2-119">This makes it useful for displaying large lists in multiple columns.</span></span>

```powershell
Get-Command -Verb Format | Format-Wide -Property Noun -Column 3
```

```Output
Custom                 Hex                  List
Table                  Wide

```

## <a name="using-format-list-for-a-list-view"></a><span data-ttu-id="d3ef2-120">Использование командлета Format-List для представления в виде списка</span><span class="sxs-lookup"><span data-stu-id="d3ef2-120">Using Format-List for a List View</span></span>

<span data-ttu-id="d3ef2-121">Командлет `Format-List` показывает объект в виде списка, в котором каждое свойство снабжено меткой и отображается в отдельной строке:</span><span class="sxs-lookup"><span data-stu-id="d3ef2-121">The `Format-List` cmdlet displays an object in the form of a listing, with each property labeled and displayed on a separate line:</span></span>

```powershell
Get-Process -Name iexplore | Format-List
```

```Output
Id      : 12808
Handles : 578
CPU     : 13.140625
SI      : 1
Name    : iexplore

Id      : 21748
Handles : 641
CPU     : 3.59375
SI      : 1
Name    : iexplore
```

<span data-ttu-id="d3ef2-122">Можно указать произвольное число свойств:</span><span class="sxs-lookup"><span data-stu-id="d3ef2-122">You can specify as many properties as you want:</span></span>

```powershell
Get-Process -Name iexplore | Format-List -Property ProcessName,FileVersion,StartTime,Id
```

```Output
ProcessName : iexplore
FileVersion : 11.00.18362.1 (WinBuild.160101.0800)
StartTime   : 10/22/2019 11:23:58 AM
Id          : 12808

ProcessName : iexplore
FileVersion : 11.00.18362.1 (WinBuild.160101.0800)
StartTime   : 10/22/2019 11:23:57 AM
Id          : 21748
```

### <a name="getting-detailed-information-by-using-format-list-with-wildcards"></a><span data-ttu-id="d3ef2-123">Получение подробных сведений с помощью подстановочных знаков в командлете Format-List</span><span class="sxs-lookup"><span data-stu-id="d3ef2-123">Getting Detailed Information by Using Format-List with Wildcards</span></span>

<span data-ttu-id="d3ef2-124">Командлет `Format-List` позволяет использовать подстановочные знаки в качестве значения параметра **Property**.</span><span class="sxs-lookup"><span data-stu-id="d3ef2-124">The `Format-List` cmdlet lets you use a wildcard as the value of its **Property** parameter.</span></span> <span data-ttu-id="d3ef2-125">Это дает возможность отображать подробные сведения.</span><span class="sxs-lookup"><span data-stu-id="d3ef2-125">This lets you display detailed information.</span></span> <span data-ttu-id="d3ef2-126">Часто объекты содержат больше информации, чем необходимо. Поэтому PowerShell по умолчанию выводит значения не всех свойств.</span><span class="sxs-lookup"><span data-stu-id="d3ef2-126">Often, objects include more information than you need, which is why PowerShell doesn't show all property values by default.</span></span> <span data-ttu-id="d3ef2-127">Чтобы вывести список всех свойств объекта, используйте команду `Format-List -Property *`.</span><span class="sxs-lookup"><span data-stu-id="d3ef2-127">To show all of properties of an object, use the `Format-List -Property *` command.</span></span> <span data-ttu-id="d3ef2-128">Следующая команда формирует более 60 строк выходных данных для одного процесса:</span><span class="sxs-lookup"><span data-stu-id="d3ef2-128">The following command generates over 60 lines of output for a single process:</span></span>

```powershell
Get-Process -Name iexplore | Format-List -Property *
```

<span data-ttu-id="d3ef2-129">Команда `Format-List` полезна для вывода подробных сведений, но для получения сведений с большим числом элементов обычно удобнее использовать упрощенное табличное представление.</span><span class="sxs-lookup"><span data-stu-id="d3ef2-129">Although the `Format-List` command is useful for showing detail, if you want an overview of output that includes many items, a simpler tabular view is often more useful.</span></span>

## <a name="using-format-table-for-tabular-output"></a><span data-ttu-id="d3ef2-130">Применение командлета Format-Table для табличного вывода</span><span class="sxs-lookup"><span data-stu-id="d3ef2-130">Using Format-Table for Tabular Output</span></span>

<span data-ttu-id="d3ef2-131">Если вызвать командлет `Format-Table` без указания имен свойств для форматирования вывода команды `Get-Process`, вы получите такие же выходные данные, как и без командлета `Format`.</span><span class="sxs-lookup"><span data-stu-id="d3ef2-131">If you use the `Format-Table` cmdlet with no property names specified to format the output of the `Get-Process` command, you get exactly the same output as you do without a `Format` cmdlet.</span></span> <span data-ttu-id="d3ef2-132">По умолчанию PowerShell отображает объекты **Process** в табличном формате.</span><span class="sxs-lookup"><span data-stu-id="d3ef2-132">By default, PowerShell displays **Process** objects in a tabular format.</span></span>

```powershell
Get-Service -Name win* | Format-Table
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  WinDefend          Windows Defender Antivirus Service
Running  WinHttpAutoProx... WinHTTP Web Proxy Auto-Discovery Se...
Running  Winmgmt            Windows Management Instrumentation
Running  WinRM              Windows Remote Management (WS-Manag...
```

### <a name="improving-format-table-output-autosize"></a><span data-ttu-id="d3ef2-133">Улучшение вывода командлета Format-Table (параметр AutoSize)</span><span class="sxs-lookup"><span data-stu-id="d3ef2-133">Improving Format-Table Output (AutoSize)</span></span>

<span data-ttu-id="d3ef2-134">Хотя табличное представление и полезно при выводе большого количества сведений, интерпретация данных может вызвать затруднения, если экран слишком узок и не вмещает все данные.</span><span class="sxs-lookup"><span data-stu-id="d3ef2-134">Although a tabular view is useful for displaying lots of information, it may be difficult to interpret if the display is too narrow for the data.</span></span> <span data-ttu-id="d3ef2-135">В предыдущем примере выходные данные усекаются.</span><span class="sxs-lookup"><span data-stu-id="d3ef2-135">In the previous example, the output is truncated.</span></span> <span data-ttu-id="d3ef2-136">Если указать параметр **AutoSize** при выполнении команды `Format-Table`, PowerShell вычислит ширину столбцов на основе размера отображаемых данных.</span><span class="sxs-lookup"><span data-stu-id="d3ef2-136">If you specify the **AutoSize** parameter when you run the `Format-Table` command, PowerShell calculates column widths based on the actual data displayed.</span></span> <span data-ttu-id="d3ef2-137">Это повышает удобство чтения столбцов.</span><span class="sxs-lookup"><span data-stu-id="d3ef2-137">This makes the columns readable.</span></span>

```powershell
Get-Service -Name win* | Format-Table -AutoSize
```

```Output
Status  Name                DisplayName
------  ----                -----------
Running WinDefend           Windows Defender Antivirus Service
Running WinHttpAutoProxySvc WinHTTP Web Proxy Auto-Discovery Service
Running Winmgmt             Windows Management Instrumentation
Running WinRM               Windows Remote Management (WS-Management)
```

<span data-ttu-id="d3ef2-138">Командлет `Format-Table` и в этом случае может усекать данные, но теперь только на правой границе экрана.</span><span class="sxs-lookup"><span data-stu-id="d3ef2-138">The `Format-Table` cmdlet might still truncate data, but it only truncates at the end of the screen.</span></span> <span data-ttu-id="d3ef2-139">Свойствам, за исключением последнего отображаемого, выделяется столько места, сколько нужно для корректного вывода самого длинного элемента данных.</span><span class="sxs-lookup"><span data-stu-id="d3ef2-139">Properties, other than the last one displayed, are given as much size as they need for their longest data element to display correctly.</span></span>

```powershell
Get-Service -Name win* | Format-Table -Property Name,Status,StartType,DisplayName,DependentServices -AutoSize
```

```Output
Name                 Status StartType DisplayName                               DependentServi
                                                                                ces
----                 ------ --------- -----------                               --------------
WinDefend           Running Automatic Windows Defender Antivirus Service        {}
WinHttpAutoProxySvc Running    Manual WinHTTP Web Proxy Auto-Discovery Service  {NcaSvc, iphl…
Winmgmt             Running Automatic Windows Management Instrumentation        {vmms, TPHKLO…
WinRM               Running Automatic Windows Remote Management (WS-Management) {}
```

<span data-ttu-id="d3ef2-140">Команда `Format-Table` предполагает, что свойства перечислены в порядке важности.</span><span class="sxs-lookup"><span data-stu-id="d3ef2-140">The `Format-Table` command assumes that properties are listed in order of importance.</span></span> <span data-ttu-id="d3ef2-141">Поэтому она пытается полностью отобразить значения свойств, которые указаны в начале списка.</span><span class="sxs-lookup"><span data-stu-id="d3ef2-141">So it attempts to fully display the properties nearest the beginning.</span></span> <span data-ttu-id="d3ef2-142">Если команда `Format-Table` не может отобразить все свойства, она удаляет из представления некоторые столбцы.</span><span class="sxs-lookup"><span data-stu-id="d3ef2-142">If the `Format-Table` command can't display all the properties, it removes some columns from the display.</span></span> <span data-ttu-id="d3ef2-143">Это поведение можно увидеть в предыдущем примере для свойства **DependentServices**.</span><span class="sxs-lookup"><span data-stu-id="d3ef2-143">You can see this behavior in the **DependentServices** property previous example.</span></span>

### <a name="wrapping-format-table-output-in-columns-wrap"></a><span data-ttu-id="d3ef2-144">Перенос на следующую строку вывода командлета Format-Table в столбцах (параметр Wrap)</span><span class="sxs-lookup"><span data-stu-id="d3ef2-144">Wrapping Format-Table Output in Columns (Wrap)</span></span>

<span data-ttu-id="d3ef2-145">Длинные данные командлета `Format-Table` можно принудительно переносить на несколько строк в пределах столбца с помощью параметра **Wrap**.</span><span class="sxs-lookup"><span data-stu-id="d3ef2-145">You can force lengthy `Format-Table` data to wrap within its display column by using the **Wrap** parameter.</span></span> <span data-ttu-id="d3ef2-146">Использование параметра **Wrap** не всегда приводит к ожидаемому результату, так как без параметра **AutoSize** он применяет параметры по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="d3ef2-146">Using the **Wrap** parameter may not do what you expect, since it uses default settings if you don't also specify **AutoSize**:</span></span>

```powershell
Get-Service -Name win* | Format-Table -Property Name,Status,StartType,DisplayName,DependentServices -Wrap
```

```Output
Name                 Status StartType DisplayName                               DependentServi
                                                                                ces
----                 ------ --------- -----------                               --------------
WinDefend           Running Automatic Windows Defender Antivirus Service        {}
WinHttpAutoProxySvc Running    Manual WinHTTP Web Proxy Auto-Discovery Service  {NcaSvc,
                                                                                iphlpsvc}
Winmgmt             Running Automatic Windows Management Instrumentation        {vmms,
                                                                                TPHKLOAD,
                                                                                SUService,
                                                                                smstsmgr…}
WinRM               Running Automatic Windows Remote Management (WS-Management) {}
```

<span data-ttu-id="d3ef2-147">Использование параметра **Wrap** без других параметров не очень замедляет обработку.</span><span class="sxs-lookup"><span data-stu-id="d3ef2-147">Using the **Wrap** parameter by itself doesn't slow down processing very much.</span></span> <span data-ttu-id="d3ef2-148">Но применение параметра **AutoSize** к рекурсивному выводу списка файлов в каталоге со сложной структурой может потребовать значительного времени и потреблять много памяти.</span><span class="sxs-lookup"><span data-stu-id="d3ef2-148">However, using **AutoSize** to format a recursive file listing of a large directory structure can take a long time and use lots of memory before displaying the first output items.</span></span>

<span data-ttu-id="d3ef2-149">Если загрузка системы для вашего сценария не критична, параметр **AutoSize** хорошо сочетается с параметром **Wrap**.</span><span class="sxs-lookup"><span data-stu-id="d3ef2-149">If you aren't concerned about system load, then **AutoSize** works well with the **Wrap** parameter.</span></span>
<span data-ttu-id="d3ef2-150">В этом случае ширина первых столбцов также позволяет выводить элементы в одной строке, а последний столбец при необходимости разбивается на несколько строк.</span><span class="sxs-lookup"><span data-stu-id="d3ef2-150">The initial columns still use as much width as needed to display items on one line, but the final column is wrapped, if necessary.</span></span>

> [!NOTE]
> <span data-ttu-id="d3ef2-151">Возможно, некоторые столбцы не попадут в представление, если первым будет указан самый широкий столбец.</span><span class="sxs-lookup"><span data-stu-id="d3ef2-151">Some columns may not be displayed when you specify the widest columns first.</span></span> <span data-ttu-id="d3ef2-152">Для получения лучших результатов выводите первыми элементы данных наименьшего объема.</span><span class="sxs-lookup"><span data-stu-id="d3ef2-152">For best results, specify the smallest data elements first.</span></span>

<span data-ttu-id="d3ef2-153">В следующем примере первыми указаны наибольшие по размеру свойства.</span><span class="sxs-lookup"><span data-stu-id="d3ef2-153">In the following example, we specify the widest properties first.</span></span>

```powershell
Get-Process -Name iexplore | Format-Table -Wrap -AutoSize -Property FileVersion,Path,Name,Id
```

<span data-ttu-id="d3ef2-154">Даже при использовании переноса строк столбец **Id** пришлось исключить:</span><span class="sxs-lookup"><span data-stu-id="d3ef2-154">Even with wrapping, the final **Id** column is omitted:</span></span>

```Output
FileVersion                          Path                                                  Nam
                                                                                           e
-----------                          ----                                                  ---
11.00.18362.1 (WinBuild.160101.0800) C:\Program Files (x86)\Internet Explorer\IEXPLORE.EXE iex
                                                                                           plo
                                                                                           re
11.00.18362.1 (WinBuild.160101.0800) C:\Program Files\Internet Explorer\iexplore.exe       iex
                                                                                           plo
                                                                                           re
```

### <a name="organizing-table-output--groupby"></a><span data-ttu-id="d3ef2-155">Организация табличного вывода (параметр -GroupBy)</span><span class="sxs-lookup"><span data-stu-id="d3ef2-155">Organizing Table Output (-GroupBy)</span></span>

<span data-ttu-id="d3ef2-156">Другим полезным параметром управления табличным выводом является **GroupBy**.</span><span class="sxs-lookup"><span data-stu-id="d3ef2-156">Another useful parameter for tabular output control is **GroupBy**.</span></span> <span data-ttu-id="d3ef2-157">Длинные табличные списки особенно тяжелы для сравнения.</span><span class="sxs-lookup"><span data-stu-id="d3ef2-157">Longer tabular listings in particular may be hard to compare.</span></span> <span data-ttu-id="d3ef2-158">Параметр **GroupBy** группирует выходные данные в соответствии со значением свойства.</span><span class="sxs-lookup"><span data-stu-id="d3ef2-158">The **GroupBy** parameter groups output based on a property value.</span></span> <span data-ttu-id="d3ef2-159">Например, можно сгруппировать службы по параметру **StartType**, чтобы упростить проверку, но исключить значение **StartType** из списка отображаемых свойств:</span><span class="sxs-lookup"><span data-stu-id="d3ef2-159">For example, we can group services by **StartType** for easier inspection, omitting the **StartType** value from the property listing:</span></span>

```powershell
Get-Service -Name win* | Sort-Object StartType | Format-Table -GroupBy StartType
```

```Output
   StartType: Automatic
Status   Name               DisplayName
------   ----               -----------
Running  WinDefend          Windows Defender Antivirus Service
Running  Winmgmt            Windows Management Instrumentation
Running  WinRM              Windows Remote Management (WS-Managem…

   StartType: Manual
Status   Name               DisplayName
------   ----               -----------
Running  WinHttpAutoProxyS… WinHTTP Web Proxy Auto-Discovery Serv…
```
