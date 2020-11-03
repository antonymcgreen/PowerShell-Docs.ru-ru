---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-table?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-Table
ms.openlocfilehash: 06f0573496f04d6790d7899afa5809ede720adee
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2020
ms.locfileid: "93230366"
---
# <span data-ttu-id="6fa78-103">Format-Table</span><span class="sxs-lookup"><span data-stu-id="6fa78-103">Format-Table</span></span>

## <span data-ttu-id="6fa78-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="6fa78-104">SYNOPSIS</span></span>
<span data-ttu-id="6fa78-105">Форматирует выходные данные в виде таблицы.</span><span class="sxs-lookup"><span data-stu-id="6fa78-105">Formats the output as a table.</span></span>

## <span data-ttu-id="6fa78-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6fa78-106">SYNTAX</span></span>

### <span data-ttu-id="6fa78-107">Все</span><span class="sxs-lookup"><span data-stu-id="6fa78-107">All</span></span>

```
Format-Table [-AutoSize] [-RepeatHeader] [-HideTableHeaders] [-Wrap] [[-Property] <Object[]>]
 [-GroupBy <Object>] [-View <String>] [-ShowError] [-DisplayError] [-Force] [-Expand <String>]
 [-InputObject <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="6fa78-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6fa78-108">DESCRIPTION</span></span>

<span data-ttu-id="6fa78-109">`Format-Table`Командлет форматирует выходные данные команды в виде таблицы с выбранными свойствами объекта в каждом столбце.</span><span class="sxs-lookup"><span data-stu-id="6fa78-109">The `Format-Table` cmdlet formats the output of a command as a table with the selected properties of the object in each column.</span></span> <span data-ttu-id="6fa78-110">Тип объекта определяет макет и свойства по умолчанию, отображаемые в каждом столбце.</span><span class="sxs-lookup"><span data-stu-id="6fa78-110">The object type determines the default layout and properties that are displayed in each column.</span></span> <span data-ttu-id="6fa78-111">Для выбора свойств, которые необходимо отобразить, можно использовать параметр **Property** .</span><span class="sxs-lookup"><span data-stu-id="6fa78-111">You can use the **Property** parameter to select the properties that you want to display.</span></span>

<span data-ttu-id="6fa78-112">PowerShell использует модули форматирования по умолчанию для определения способа отображения типов объектов.</span><span class="sxs-lookup"><span data-stu-id="6fa78-112">PowerShell uses default formatters to define how object types are displayed.</span></span> <span data-ttu-id="6fa78-113">Файлы можно использовать `.ps1xml` для создания пользовательских представлений, отображающих выходную таблицу с указанными свойствами.</span><span class="sxs-lookup"><span data-stu-id="6fa78-113">You can use `.ps1xml` files to create custom views that display an output table with specified properties.</span></span> <span data-ttu-id="6fa78-114">После создания пользовательского представления используйте параметр **View** , чтобы отобразить таблицу с пользовательским представлением.</span><span class="sxs-lookup"><span data-stu-id="6fa78-114">After a custom view is created, use the **View** parameter to display the table with your custom view.</span></span> <span data-ttu-id="6fa78-115">Дополнительные сведения о представлениях см. в разделе [about_Format.ps1XML](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).</span><span class="sxs-lookup"><span data-stu-id="6fa78-115">For more information about views, see [about_Format.ps1xml](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).</span></span>

<span data-ttu-id="6fa78-116">Хэш-таблицу можно использовать для добавления вычисляемых свойств к объекту перед его отображением и указаниям заголовков столбцов в таблице.</span><span class="sxs-lookup"><span data-stu-id="6fa78-116">You can use a hash table to add calculated properties to an object before displaying it and to specify the column headings in the table.</span></span> <span data-ttu-id="6fa78-117">Чтобы добавить вычисляемое свойство, используйте параметр **Property** или **GroupBy** .</span><span class="sxs-lookup"><span data-stu-id="6fa78-117">To add a calculated property, use the **Property** or **GroupBy** parameter.</span></span> <span data-ttu-id="6fa78-118">Дополнительные сведения о хэш-таблицах см. [здесь](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md).</span><span class="sxs-lookup"><span data-stu-id="6fa78-118">For more information about hash tables, see [about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md).</span></span>

## <span data-ttu-id="6fa78-119">Примеры</span><span class="sxs-lookup"><span data-stu-id="6fa78-119">EXAMPLES</span></span>

### <span data-ttu-id="6fa78-120">Пример 1. форматирование узла PowerShell</span><span class="sxs-lookup"><span data-stu-id="6fa78-120">Example 1: Format PowerShell host</span></span>

<span data-ttu-id="6fa78-121">В этом примере отображаются сведения о хост-программе для PowerShell в таблице.</span><span class="sxs-lookup"><span data-stu-id="6fa78-121">This example displays information about the host program for PowerShell in a table.</span></span>

```powershell
Get-Host | Format-Table -AutoSize
```

<span data-ttu-id="6fa78-122">`Get-Host`Командлет получает объекты **System. Management. Automation. internal. host. интерналхост** , представляющие узел.</span><span class="sxs-lookup"><span data-stu-id="6fa78-122">The `Get-Host` cmdlet gets **System.Management.Automation.Internal.Host.InternalHost** objects that represent the host.</span></span> <span data-ttu-id="6fa78-123">Объекты отправляются по конвейеру в `Format-Table` и отображаются в таблице.</span><span class="sxs-lookup"><span data-stu-id="6fa78-123">The objects are sent down the pipeline to `Format-Table` and displayed in a table.</span></span> <span data-ttu-id="6fa78-124">Параметр **AutoSize** корректирует ширину столбцов для сокращения усечения.</span><span class="sxs-lookup"><span data-stu-id="6fa78-124">The **AutoSize** parameter adjusts the column widths to minimize truncation.</span></span>

### <span data-ttu-id="6fa78-125">Пример 2. форматирование процессов по Басеприорити</span><span class="sxs-lookup"><span data-stu-id="6fa78-125">Example 2: Format processes by BasePriority</span></span>

<span data-ttu-id="6fa78-126">В этом примере процессы отображаются в группах, имеющих одно и то же свойство **басеприорити** .</span><span class="sxs-lookup"><span data-stu-id="6fa78-126">In this example, processes are displayed in groups that have the same **BasePriority** property.</span></span>

```powershell
Get-Process | Sort-Object -Property BasePriority | Format-Table -GroupBy BasePriority -Wrap
```

<span data-ttu-id="6fa78-127">`Get-Process`Командлет возвращает объекты, представляющие каждый процесс на компьютере, и отправляет их по конвейеру `Sort-Object` .</span><span class="sxs-lookup"><span data-stu-id="6fa78-127">The `Get-Process` cmdlet gets objects that represent each process on the computer and sends them down the pipeline to `Sort-Object`.</span></span> <span data-ttu-id="6fa78-128">Объекты сортируются в порядке их свойства **басеприорити** .</span><span class="sxs-lookup"><span data-stu-id="6fa78-128">The objects are sorted in the order of their **BasePriority** property.</span></span>

<span data-ttu-id="6fa78-129">Отсортированные объекты отправляются по конвейеру в `Format-Table` .</span><span class="sxs-lookup"><span data-stu-id="6fa78-129">The sorted objects are sent down the pipeline to `Format-Table`.</span></span> <span data-ttu-id="6fa78-130">Параметр **GroupBy** упорядочивает данные процесса по группам на основе их значения свойства **басеприорити** .</span><span class="sxs-lookup"><span data-stu-id="6fa78-130">The **GroupBy** parameter arranges the process data into groups based on their **BasePriority** property's value.</span></span> <span data-ttu-id="6fa78-131">Параметр **переноса** гарантирует, что данные не усекаются.</span><span class="sxs-lookup"><span data-stu-id="6fa78-131">The **Wrap** parameter ensures that data isn't truncated.</span></span>

### <span data-ttu-id="6fa78-132">Пример 3. форматирование процессов по дате начала</span><span class="sxs-lookup"><span data-stu-id="6fa78-132">Example 3: Format processes by start date</span></span>

<span data-ttu-id="6fa78-133">В этом примере отображаются сведения о процессах, запущенных на компьютере.</span><span class="sxs-lookup"><span data-stu-id="6fa78-133">This example displays information about the processes running on the computer.</span></span> <span data-ttu-id="6fa78-134">Объекты сортируются и `Format-Table` используют представление для группировки объектов по дате начала.</span><span class="sxs-lookup"><span data-stu-id="6fa78-134">The objects are sorted and `Format-Table` uses a view to group the objects by their start date.</span></span>

```powershell
Get-Process | Sort-Object StartTime | Format-Table -View StartTime
```

<span data-ttu-id="6fa78-135">`Get-Process` Возвращает объекты **System. Diagnostics. Process** , представляющие процессы, запущенные на компьютере.</span><span class="sxs-lookup"><span data-stu-id="6fa78-135">`Get-Process` gets the **System.Diagnostics.Process** objects that represent the processes running on the computer.</span></span> <span data-ttu-id="6fa78-136">Объекты отправляются по конвейеру в `Sort-Object` и сортируются на основе свойства **StartTime** .</span><span class="sxs-lookup"><span data-stu-id="6fa78-136">The objects are sent down the pipeline to `Sort-Object`, and are sorted based on the **StartTime** property.</span></span>

<span data-ttu-id="6fa78-137">Отсортированные объекты отправляются по конвейеру в `Format-Table` .</span><span class="sxs-lookup"><span data-stu-id="6fa78-137">The sorted objects are sent down the pipeline to `Format-Table`.</span></span> <span data-ttu-id="6fa78-138">Параметр **View** указывает представление **StartTime** , определенное в `DotNetTypes.format.ps1xml` файле PowerShell для объектов **System. Diagnostics. Process** .</span><span class="sxs-lookup"><span data-stu-id="6fa78-138">The **View** parameter specifies the **StartTime** view that's defined in the PowerShell `DotNetTypes.format.ps1xml` file for **System.Diagnostics.Process** objects.</span></span> <span data-ttu-id="6fa78-139">Представление **StartTime** преобразует время начала каждого процесса в короткий формат, а затем группирует процессы по дате начала.</span><span class="sxs-lookup"><span data-stu-id="6fa78-139">The **StartTime** view converts each processes start time to a short date and then groups the processes by the start date.</span></span>

<span data-ttu-id="6fa78-140">`DotNetTypes.format.ps1xml`Файл содержит представление с **приоритетом** для процессов.</span><span class="sxs-lookup"><span data-stu-id="6fa78-140">The `DotNetTypes.format.ps1xml` file contains a **Priority** view for processes.</span></span> <span data-ttu-id="6fa78-141">Вы можете создавать собственные `format.ps1xml` файлы с настраиваемыми представлениями.</span><span class="sxs-lookup"><span data-stu-id="6fa78-141">You can create your own `format.ps1xml` files with customized views.</span></span>

### <span data-ttu-id="6fa78-142">Пример 4. Использование пользовательского представления для вывода таблицы</span><span class="sxs-lookup"><span data-stu-id="6fa78-142">Example 4: Use a custom view for table output</span></span>

<span data-ttu-id="6fa78-143">В этом примере в пользовательском представлении отображается содержимое каталога.</span><span class="sxs-lookup"><span data-stu-id="6fa78-143">In this example, a custom view displays a directory's contents.</span></span> <span data-ttu-id="6fa78-144">Пользовательское представление добавляет столбец **CreationTime** в выходные данные таблицы для объектов **System. IO. DirectoryInfo** и **System. IO. FileInfo** , созданных `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="6fa78-144">The custom view adds the **CreationTime** column to the table output for **System.IO.DirectoryInfo** and **System.IO.FileInfo** objects created by `Get-ChildItem`.</span></span>

<span data-ttu-id="6fa78-145">Пользовательское представление в этом примере было создано из представления, определенного в исходном коде PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6fa78-145">The custom view in this example was created from the view defined in PowerShell source code.</span></span> <span data-ttu-id="6fa78-146">Дополнительные сведения о представлениях и коде, используемом для создания представления этого примера, см. в разделе [about_Format.ps1XML](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md#sample-xml-for-a-format-table-custom-view).</span><span class="sxs-lookup"><span data-stu-id="6fa78-146">For more information about views and the code used to create this example's view, see [about_Format.ps1xml](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md#sample-xml-for-a-format-table-custom-view).</span></span>

```powershell
Get-ChildItem  -Path C:\Test | Format-Table -View mygciview
```

```Output
    Directory: C:\Test

Mode                LastWriteTime              CreationTime         Length Name
----                -------------              ------------         ------ ----
d-----        11/4/2019     15:54       9/24/2019     15:54                Archives
d-----        8/27/2019     14:22       8/27/2019     14:22                Drawings
d-----       10/23/2019     09:38       2/25/2019     09:38                Files
-a----        11/7/2019     11:07       11/7/2019     11:07          11345 Alias.txt
-a----        2/27/2019     15:15       2/27/2019     15:15            258 alias_out.txt
-a----        2/27/2019     15:16       2/27/2019     15:16            258 alias_out2.txt
```

<span data-ttu-id="6fa78-147">`Get-ChildItem` Возвращает содержимое текущего каталога, `C:\Test` .</span><span class="sxs-lookup"><span data-stu-id="6fa78-147">`Get-ChildItem` gets the contents of the current directory, `C:\Test`.</span></span> <span data-ttu-id="6fa78-148">Объекты **System. IO. DirectoryInfo** и **System. IO. FileInfo** отправляются по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="6fa78-148">The **System.IO.DirectoryInfo** and **System.IO.FileInfo** objects are sent down the pipeline.</span></span>
<span data-ttu-id="6fa78-149">`Format-Table` использует параметр **View** для указания пользовательского представления **мигЦивиев** , включающего столбец **CreationTime** .</span><span class="sxs-lookup"><span data-stu-id="6fa78-149">`Format-Table` uses the **View** parameter to specify the custom view **mygciview** that includes the **CreationTime** column.</span></span>

<span data-ttu-id="6fa78-150">Выход по умолчанию `Format-Table` для `Get-ChildItem` не включает столбец **CreationTime** .</span><span class="sxs-lookup"><span data-stu-id="6fa78-150">The default `Format-Table` output for `Get-ChildItem` doesn't include the **CreationTime** column.</span></span>

### <span data-ttu-id="6fa78-151">Пример 5. Использование свойств для вывода таблицы</span><span class="sxs-lookup"><span data-stu-id="6fa78-151">Example 5: Use properties for table output</span></span>

<span data-ttu-id="6fa78-152">В этом примере используется параметр **Property** для отображения всех служб компьютера в таблице из двух столбцов, в которой показаны свойства **Name** и **DependentServices** .</span><span class="sxs-lookup"><span data-stu-id="6fa78-152">This example uses the **Property** parameter to display all the computer's services in a two-column table that shows the properties **Name** and **DependentServices** .</span></span>

```powershell
Get-Service | Format-Table -Property Name, DependentServices
```

<span data-ttu-id="6fa78-153">`Get-Service` Получает все службы на компьютере и отправляет объекты **System. ServiceProcess. ServiceController** по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="6fa78-153">`Get-Service` gets all the services on the computer and sends the **System.ServiceProcess.ServiceController** objects down the pipeline.</span></span> <span data-ttu-id="6fa78-154">`Format-Table` использует параметр **Property** , чтобы указать, что свойства **Name** и **DependentServices** отображаются в таблице.</span><span class="sxs-lookup"><span data-stu-id="6fa78-154">`Format-Table` uses the **Property** parameter to specify that the **Name** and **DependentServices** properties are displayed in the table.</span></span>

<span data-ttu-id="6fa78-155">**Name** и **DependentServices** — это два свойства типа объекта.</span><span class="sxs-lookup"><span data-stu-id="6fa78-155">**Name** and **DependentServices** are two of the object type's properties.</span></span> <span data-ttu-id="6fa78-156">Для просмотра всех свойств: `Get-Service | Get-Member -MemberType Properties` .</span><span class="sxs-lookup"><span data-stu-id="6fa78-156">To view all the properties: `Get-Service | Get-Member -MemberType Properties`.</span></span>

### <span data-ttu-id="6fa78-157">Пример 6. форматирование процесса и вычисление его времени выполнения</span><span class="sxs-lookup"><span data-stu-id="6fa78-157">Example 6: Format a process and calculate its running time</span></span>

<span data-ttu-id="6fa78-158">В этом примере отображается таблица с именем процесса и общим временем выполнения для процессов **блокнота** локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="6fa78-158">This example displays a table with the process name and total running time for the local computer's **notepad** processes.</span></span> <span data-ttu-id="6fa78-159">Общее время выполнения рассчитывается для каждого процесса путем вычитания времени начала из текущего времени.</span><span class="sxs-lookup"><span data-stu-id="6fa78-159">The total running time is calculated by subtracting the start time of each process from the current time.</span></span>

```powershell
Get-Process notepad |
  Format-Table ProcessName, @{Label="TotalRunningTime"; Expression={(Get-Date) - $_.StartTime}}
```

```Output
ProcessName TotalRunningTime
----------- ----------------
notepad     03:20:00.2751767
notepad     00:00:16.7710520
```

<span data-ttu-id="6fa78-160">`Get-Process` Получает все процессы в **блокноте** локального компьютера и отправляет объекты по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="6fa78-160">`Get-Process` gets all the local computer's **notepad** processes and sends the objects down the pipeline.</span></span> <span data-ttu-id="6fa78-161">`Format-Table` Отображает таблицу с двумя столбцами: **processName** , `Get-Process` свойство и **тоталруннингтиме** , вычисляемое свойство.</span><span class="sxs-lookup"><span data-stu-id="6fa78-161">`Format-Table` displays a table with two columns: **ProcessName** , a `Get-Process` property, and **TotalRunningTime** , a calculated property.</span></span>

<span data-ttu-id="6fa78-162">Свойство **тоталруннингтиме** задается хэш-таблицей с двумя ключами, **меткой** и **выражением** .</span><span class="sxs-lookup"><span data-stu-id="6fa78-162">The **TotalRunningTime** property is specified by a hash table with two keys, **Label** and **Expression** .</span></span> <span data-ttu-id="6fa78-163">Ключ **метки** указывает имя свойства.</span><span class="sxs-lookup"><span data-stu-id="6fa78-163">The **Label** key specifies the property name.</span></span> <span data-ttu-id="6fa78-164">Ключ **выражения** задает вычисление.</span><span class="sxs-lookup"><span data-stu-id="6fa78-164">The **Expression** key specifies the calculation.</span></span> <span data-ttu-id="6fa78-165">Выражение получает свойство **StartTime** каждого объекта Process и вычитает его из результата выполнения `Get-Date` команды, которая получает текущие дату и время.</span><span class="sxs-lookup"><span data-stu-id="6fa78-165">The expression gets the **StartTime** property of each process object and subtracts it from the result of a `Get-Date` command, which gets the current date and time.</span></span>

### <span data-ttu-id="6fa78-166">Пример 7. форматирование процессов в блокноте</span><span class="sxs-lookup"><span data-stu-id="6fa78-166">Example 7: Format Notepad processes</span></span>

<span data-ttu-id="6fa78-167">В этом примере используется `Get-CimInstance` для получения времени выполнения всех процессов **Notepad** на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="6fa78-167">This example uses `Get-CimInstance` to get the running time for all **notepad** processes on the local computer.</span></span> <span data-ttu-id="6fa78-168">`Get-CimInstance`С помощью параметра **ComputerName** можно получить сведения с удаленных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="6fa78-168">You can use `Get-CimInstance` with the **ComputerName** parameter to get information from remote computers.</span></span>

```powershell
$Processes = Get-CimInstance -Class win32_process -Filter "name='notepad.exe'"
$Processes | Format-Table ProcessName, @{ Label = "Total Running Time"; Expression={(Get-Date) - $_.CreationDate}}
```

```Output
ProcessName Total Running Time
----------- ------------------
notepad.exe 03:39:39.6260693
notepad.exe 00:19:56.1376922
```

<span data-ttu-id="6fa78-169">`Get-CimInstance` Возвращает экземпляры класса **WIN32_PROCESS** WMI, описывающие все процессы локального компьютера с именем **notepad.exe** .</span><span class="sxs-lookup"><span data-stu-id="6fa78-169">`Get-CimInstance` gets instances of the WMI **Win32_Process** class that describes all the local computer's processes named **notepad.exe** .</span></span> <span data-ttu-id="6fa78-170">Объекты процесса хранятся в `$Processes` переменной.</span><span class="sxs-lookup"><span data-stu-id="6fa78-170">The process objects are stored in the `$Processes` variable.</span></span>

<span data-ttu-id="6fa78-171">Объекты процесса в `$Processes` переменной отправляются по конвейеру в `Format-Table` , который отображает свойство **processName** и новое вычисляемое свойство, **Общее время выполнения** .</span><span class="sxs-lookup"><span data-stu-id="6fa78-171">The process objects in the `$Processes` variable are sent down the pipeline to `Format-Table`, which displays the **ProcessName** property and a new calculated property, **Total Running Time** .</span></span>

<span data-ttu-id="6fa78-172">Команда присваивает имя нового вычисляемого свойства, **общего времени выполнения** , с ключом **метки** .</span><span class="sxs-lookup"><span data-stu-id="6fa78-172">The command assigns the name of the new calculated property, **Total Running Time** , to the **Label** key.</span></span> <span data-ttu-id="6fa78-173">Блок сценария ключа **выражения** вычисляет время выполнения процесса путем вычитания даты создания процессов из текущей даты.</span><span class="sxs-lookup"><span data-stu-id="6fa78-173">The **Expression** key's script block calculates how long the process has been running by subtracting the processes creation date from the current date.</span></span> <span data-ttu-id="6fa78-174">`Get-Date`Командлет возвращает текущую дату.</span><span class="sxs-lookup"><span data-stu-id="6fa78-174">The `Get-Date` cmdlet gets the current date.</span></span> <span data-ttu-id="6fa78-175">Дата создания вычитается из текущей даты.</span><span class="sxs-lookup"><span data-stu-id="6fa78-175">The creation date is subtracted from the current date.</span></span> <span data-ttu-id="6fa78-176">Результатом является значение **общего времени выполнения** .</span><span class="sxs-lookup"><span data-stu-id="6fa78-176">The result is the value of **Total Running Time** .</span></span>

### <span data-ttu-id="6fa78-177">Пример 8. Устранение ошибок формата</span><span class="sxs-lookup"><span data-stu-id="6fa78-177">Example 8: Troubleshooting format errors</span></span>

<span data-ttu-id="6fa78-178">В следующих примерах показаны результаты добавления параметров **DisplayError** или **ShowError** в выражение.</span><span class="sxs-lookup"><span data-stu-id="6fa78-178">The following examples show the results of adding the **DisplayError** or **ShowError** parameters with an expression.</span></span>

```powershell
Get-Date | Format-Table DayOfWeek,{ $_ / $null } -DisplayError
```

```Output
DayOfWeek  $_ / $null
--------- ------------
Wednesday #ERR
```

```powershell
Get-Date | Format-Table DayOfWeek,{ $_ / $null } -ShowError
```

```Output
DayOfWeek  $_ / $null
--------- ------------
Wednesday
Failed to evaluate expression " $_ / $null ".
+ CategoryInfo          : InvalidArgument: (11/27/2019 12:52:38:PSObject) [], RuntimeException
+ FullyQualifiedErrorId : PSPropertyExpressionError
```

## <span data-ttu-id="6fa78-179">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6fa78-179">PARAMETERS</span></span>

### <span data-ttu-id="6fa78-180">-AutoSize</span><span class="sxs-lookup"><span data-stu-id="6fa78-180">-AutoSize</span></span>

<span data-ttu-id="6fa78-181">Указывает, что командлет корректирует размер столбца и число столбцов в зависимости от ширины данных.</span><span class="sxs-lookup"><span data-stu-id="6fa78-181">Indicates that the cmdlet adjusts the column size and number of columns based on the width of the data.</span></span> <span data-ttu-id="6fa78-182">По умолчанию размер и количество столбцов определяются представлением.</span><span class="sxs-lookup"><span data-stu-id="6fa78-182">By default, the column size and number are determined by the view.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6fa78-183">-DisplayError</span><span class="sxs-lookup"><span data-stu-id="6fa78-183">-DisplayError</span></span>

<span data-ttu-id="6fa78-184">Указывает, что командлет отображает ошибки в командной строке.</span><span class="sxs-lookup"><span data-stu-id="6fa78-184">Indicates that the cmdlet displays errors on the command line.</span></span> <span data-ttu-id="6fa78-185">Этот параметр может использоваться в качестве вспомогательного средства отладки при форматировании выражений в `Format-Table` команде и необходимости в устранении неполадок выражений.</span><span class="sxs-lookup"><span data-stu-id="6fa78-185">This parameter can be used as a debugging aid when you're formatting expressions in a `Format-Table` command and need to troubleshoot the expressions.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6fa78-186">-Expand</span><span class="sxs-lookup"><span data-stu-id="6fa78-186">-Expand</span></span>

<span data-ttu-id="6fa78-187">Задает формат объекта коллекции и объектов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="6fa78-187">Specifies the format of the collection object and the objects in the collection.</span></span> <span data-ttu-id="6fa78-188">Этот параметр предназначен для форматирования объектов, поддерживающих интерфейс [ICollection](/dotnet/api/system.collections.icollection) ([System. Collections](/dotnet/api/system.collections)).</span><span class="sxs-lookup"><span data-stu-id="6fa78-188">This parameter is designed to format objects that support the [ICollection](/dotnet/api/system.collections.icollection) ([System.Collections](/dotnet/api/system.collections)) interface.</span></span> <span data-ttu-id="6fa78-189">Значение по умолчанию — **енумонли** .</span><span class="sxs-lookup"><span data-stu-id="6fa78-189">The default value is **EnumOnly** .</span></span>
<span data-ttu-id="6fa78-190">Для этого параметра допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="6fa78-190">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="6fa78-191">**Енумонли** : отображает свойства объектов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="6fa78-191">**EnumOnly** : Displays the properties of the objects in the collection.</span></span>
- <span data-ttu-id="6fa78-192">**Кореонли** : отображает свойства объекта коллекции.</span><span class="sxs-lookup"><span data-stu-id="6fa78-192">**CoreOnly** : Displays the properties of the collection object.</span></span>
- <span data-ttu-id="6fa78-193">**Оба** : отображает свойства объекта коллекции и свойства объектов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="6fa78-193">**Both** : Displays the properties of the collection object and the properties of objects in the collection.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: CoreOnly, EnumOnly, Both

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6fa78-194">-Force</span><span class="sxs-lookup"><span data-stu-id="6fa78-194">-Force</span></span>

<span data-ttu-id="6fa78-195">Указывает, что командлет направляет командлет для вывода всех сведений об ошибке.</span><span class="sxs-lookup"><span data-stu-id="6fa78-195">Indicates that the cmdlet directs the cmdlet to display all the error information.</span></span> <span data-ttu-id="6fa78-196">Используйте с параметром **DisplayError** или **ShowError** .</span><span class="sxs-lookup"><span data-stu-id="6fa78-196">Use with the **DisplayError** or **ShowError** parameter.</span></span> <span data-ttu-id="6fa78-197">По умолчанию при записи объекта ошибки в поток ошибок или поток отображения отображаются только некоторые сведения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="6fa78-197">By default, when an error object is written to the error or display streams, only some of the error information is displayed.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6fa78-198">-GroupBy</span><span class="sxs-lookup"><span data-stu-id="6fa78-198">-GroupBy</span></span>

<span data-ttu-id="6fa78-199">Указывает отсортированные выходные данные в отдельных таблицах на основе значения свойства.</span><span class="sxs-lookup"><span data-stu-id="6fa78-199">Specifies sorted output in separate tables based on a property value.</span></span> <span data-ttu-id="6fa78-200">Например, с помощью **GroupBy** можно перечислить службы в отдельных таблицах на основе их состояния.</span><span class="sxs-lookup"><span data-stu-id="6fa78-200">For example, you can use **GroupBy** to list services in separate tables based on their status.</span></span>

<span data-ttu-id="6fa78-201">Введите выражение или свойство.</span><span class="sxs-lookup"><span data-stu-id="6fa78-201">Enter an expression or a property.</span></span> <span data-ttu-id="6fa78-202">Параметр **GroupBy** ждет, что объекты сортируются.</span><span class="sxs-lookup"><span data-stu-id="6fa78-202">The **GroupBy** parameter expects that the objects are sorted.</span></span>
<span data-ttu-id="6fa78-203">Используйте `Sort-Object` командлет перед использованием `Format-Table` для группирования объектов.</span><span class="sxs-lookup"><span data-stu-id="6fa78-203">Use the `Sort-Object` cmdlet before using `Format-Table` to group the objects.</span></span>

<span data-ttu-id="6fa78-204">Значением параметра **GroupBy** может быть новое вычисляемое свойство.</span><span class="sxs-lookup"><span data-stu-id="6fa78-204">The value of the **GroupBy** parameter can be a new calculated property.</span></span> <span data-ttu-id="6fa78-205">Вычисляемое свойство может быть блоком скрипта или хэш-таблицей.</span><span class="sxs-lookup"><span data-stu-id="6fa78-205">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="6fa78-206">Допустимые пары "ключ-значение":</span><span class="sxs-lookup"><span data-stu-id="6fa78-206">Valid key-value pairs are:</span></span>

- <span data-ttu-id="6fa78-207">Имя (или метка) — `<string>`</span><span class="sxs-lookup"><span data-stu-id="6fa78-207">Name (or Label) - `<string>`</span></span>
- <span data-ttu-id="6fa78-208">Выражение — `<string>` или `<script block>`</span><span class="sxs-lookup"><span data-stu-id="6fa78-208">Expression - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="6fa78-209">FormatString `<string>`</span><span class="sxs-lookup"><span data-stu-id="6fa78-209">FormatString - `<string>`</span></span>

<span data-ttu-id="6fa78-210">Дополнительные сведения см. в разделе [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="6fa78-210">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6fa78-211">-Хидетаблехеадерс</span><span class="sxs-lookup"><span data-stu-id="6fa78-211">-HideTableHeaders</span></span>

<span data-ttu-id="6fa78-212">Исключает из таблицы заголовки столбцов.</span><span class="sxs-lookup"><span data-stu-id="6fa78-212">Omits the column headings from the table.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6fa78-213">-InputObject</span><span class="sxs-lookup"><span data-stu-id="6fa78-213">-InputObject</span></span>

<span data-ttu-id="6fa78-214">Задает объекты для форматирования.</span><span class="sxs-lookup"><span data-stu-id="6fa78-214">Specifies the objects to format.</span></span> <span data-ttu-id="6fa78-215">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="6fa78-215">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="6fa78-216">-Property</span><span class="sxs-lookup"><span data-stu-id="6fa78-216">-Property</span></span>

<span data-ttu-id="6fa78-217">Задает свойства объекта, которые будут включены в вывод, и порядок их вывода.</span><span class="sxs-lookup"><span data-stu-id="6fa78-217">Specifies the object properties that appear in the display and the order in which they appear.</span></span> <span data-ttu-id="6fa78-218">Введите одно или несколько имен свойств, разделенных запятыми, или используйте хэш-таблицу для вывода вычисляемого свойства.</span><span class="sxs-lookup"><span data-stu-id="6fa78-218">Type one or more property names, separated by commas, or use a hash table to display a calculated property.</span></span> <span data-ttu-id="6fa78-219">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="6fa78-219">Wildcards are permitted.</span></span>

<span data-ttu-id="6fa78-220">Если этот параметр не задан, свойства, отображаемые на экране, зависят от свойств первого объекта.</span><span class="sxs-lookup"><span data-stu-id="6fa78-220">If you omit this parameter, the properties that appear in the display depend on the first object's properties.</span></span> <span data-ttu-id="6fa78-221">Например, если первый объект имеет **свойство** a и **пропертиб** , но последующие объекты имеют **свойство** a, **пропертиб** и **пропертик** , то будут отображены только заголовки **Property** a и **пропертиб** .</span><span class="sxs-lookup"><span data-stu-id="6fa78-221">For example, if the first object has **PropertyA** and **PropertyB** but subsequent objects have **PropertyA** , **PropertyB** , and **PropertyC** , then only the **PropertyA** and **PropertyB** headers will display.</span></span>

<span data-ttu-id="6fa78-222">Параметр **Property** является необязательным.</span><span class="sxs-lookup"><span data-stu-id="6fa78-222">The **Property** parameter is optional.</span></span> <span data-ttu-id="6fa78-223">Нельзя использовать **Свойства** и параметры **представления** в одной команде.</span><span class="sxs-lookup"><span data-stu-id="6fa78-223">You can't use the **Property** and **View** parameters in the same command.</span></span>

<span data-ttu-id="6fa78-224">Значением параметра **Property** может быть новое вычисляемое свойство.</span><span class="sxs-lookup"><span data-stu-id="6fa78-224">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="6fa78-225">Вычисляемое свойство может быть блоком скрипта или хэш-таблицей.</span><span class="sxs-lookup"><span data-stu-id="6fa78-225">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="6fa78-226">Допустимые пары "ключ-значение":</span><span class="sxs-lookup"><span data-stu-id="6fa78-226">Valid key-value pairs are:</span></span>

- <span data-ttu-id="6fa78-227">Имя (или метка) `<string>`</span><span class="sxs-lookup"><span data-stu-id="6fa78-227">Name (or Label) `<string>`</span></span>
- <span data-ttu-id="6fa78-228">Выражение — `<string>` или `<script block>`</span><span class="sxs-lookup"><span data-stu-id="6fa78-228">Expression - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="6fa78-229">FormatString `<string>`</span><span class="sxs-lookup"><span data-stu-id="6fa78-229">FormatString - `<string>`</span></span>
- <span data-ttu-id="6fa78-230">Ширина- `<int32>` -должен быть больше `0`</span><span class="sxs-lookup"><span data-stu-id="6fa78-230">Width - `<int32>` - must be greater than `0`</span></span>
- <span data-ttu-id="6fa78-231">Alignment — значение может быть `Left` , `Center` или `Right`</span><span class="sxs-lookup"><span data-stu-id="6fa78-231">Alignment - value can be `Left`, `Center`, or `Right`</span></span>

<span data-ttu-id="6fa78-232">Дополнительные сведения см. в разделе [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="6fa78-232">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="6fa78-233">-Репеасеадер</span><span class="sxs-lookup"><span data-stu-id="6fa78-233">-RepeatHeader</span></span>

<span data-ttu-id="6fa78-234">Повторяет отображение заголовка таблицы после заполнения каждого экрана.</span><span class="sxs-lookup"><span data-stu-id="6fa78-234">Repeats displaying the header of a table after every screen full.</span></span> <span data-ttu-id="6fa78-235">Повторяющийся заголовок полезен, когда выходные данные передаются на пейджер, например `less` или в `more` подкачку с помощью средства чтения с экрана.</span><span class="sxs-lookup"><span data-stu-id="6fa78-235">The repeated header is useful when the output is piped to a pager such as `less` or `more` or paging with a screen reader.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6fa78-236">-ShowError</span><span class="sxs-lookup"><span data-stu-id="6fa78-236">-ShowError</span></span>

<span data-ttu-id="6fa78-237">Этот параметр отправляет ошибки через конвейер.</span><span class="sxs-lookup"><span data-stu-id="6fa78-237">This parameter sends errors through the pipeline.</span></span> <span data-ttu-id="6fa78-238">Этот параметр может использоваться в качестве вспомогательного средства отладки при форматировании выражений в `Format-Table` команде и необходимости в устранении неполадок выражений.</span><span class="sxs-lookup"><span data-stu-id="6fa78-238">This parameter can be used as a debugging aid when you're formatting expressions in a `Format-Table` command and need to troubleshoot the expressions.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6fa78-239">-View</span><span class="sxs-lookup"><span data-stu-id="6fa78-239">-View</span></span>

<span data-ttu-id="6fa78-240">Начиная с PowerShell 6, представления по умолчанию определяются в `C#` исходном коде PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6fa78-240">Beginning in PowerShell 6, the default views are defined in PowerShell `C#` source code.</span></span> <span data-ttu-id="6fa78-241">`*.format.ps1xml`Файлы из powershell 5,1 и более ранних версий не существуют в PowerShell 6 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="6fa78-241">The `*.format.ps1xml` files from PowerShell 5.1 and earlier versions don't exist in PowerShell 6 and later versions.</span></span>

<span data-ttu-id="6fa78-242">Параметр **View** позволяет указать альтернативный формат или пользовательское представление для таблицы.</span><span class="sxs-lookup"><span data-stu-id="6fa78-242">The **View** parameter lets you specify an alternate format or custom view for the table.</span></span> <span data-ttu-id="6fa78-243">Можно использовать представления PowerShell по умолчанию или создать пользовательские представления.</span><span class="sxs-lookup"><span data-stu-id="6fa78-243">You can use the default PowerShell views or create custom views.</span></span> <span data-ttu-id="6fa78-244">Дополнительные сведения о создании пользовательского представления см. в разделе [about_Format.ps1XML](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).</span><span class="sxs-lookup"><span data-stu-id="6fa78-244">For more information about how to create a custom view, see [about_Format.ps1xml](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).</span></span>

<span data-ttu-id="6fa78-245">Альтернативное и пользовательское представления для параметра **представления** должны использовать формат таблицы, в противном случае — `Format-Table` сбой.</span><span class="sxs-lookup"><span data-stu-id="6fa78-245">The alternate and custom views for the **View** parameter must use the table format, otherwise, `Format-Table` fails.</span></span> <span data-ttu-id="6fa78-246">Если альтернативное представление является списком, используйте `Format-List` командлет.</span><span class="sxs-lookup"><span data-stu-id="6fa78-246">If the alternate view is a list, use the `Format-List` cmdlet.</span></span> <span data-ttu-id="6fa78-247">Если альтернативное представление не является списком или таблицей, используйте `Format-Custom` командлет.</span><span class="sxs-lookup"><span data-stu-id="6fa78-247">If the alternate view isn't a list or a table, use the `Format-Custom` cmdlet.</span></span>

<span data-ttu-id="6fa78-248">Нельзя использовать **Свойства** и параметры **представления** в одной команде.</span><span class="sxs-lookup"><span data-stu-id="6fa78-248">You can't use the **Property** and **View** parameters in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6fa78-249">-Wrap</span><span class="sxs-lookup"><span data-stu-id="6fa78-249">-Wrap</span></span>

<span data-ttu-id="6fa78-250">Переносит текст, не помещающийся по ширине столбца, на следующую строку.</span><span class="sxs-lookup"><span data-stu-id="6fa78-250">Displays text that exceeds the column width on the next line.</span></span> <span data-ttu-id="6fa78-251">По умолчанию текст, не уместившийся по ширине столбца, усекается.</span><span class="sxs-lookup"><span data-stu-id="6fa78-251">By default, text that exceeds the column width is truncated.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6fa78-252">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="6fa78-252">CommonParameters</span></span>

<span data-ttu-id="6fa78-253">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="6fa78-253">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6fa78-254">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="6fa78-254">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6fa78-255">Входные данные</span><span class="sxs-lookup"><span data-stu-id="6fa78-255">INPUTS</span></span>

### <span data-ttu-id="6fa78-256">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="6fa78-256">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="6fa78-257">Вы можете отправить любой объект, расположенный по конвейеру, в `Format-Table` .</span><span class="sxs-lookup"><span data-stu-id="6fa78-257">You can send any object down the pipeline to `Format-Table`.</span></span>

## <span data-ttu-id="6fa78-258">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="6fa78-258">OUTPUTS</span></span>

### <span data-ttu-id="6fa78-259">Microsoft.PowerShell.Commands.Internal.Format</span><span class="sxs-lookup"><span data-stu-id="6fa78-259">Microsoft.PowerShell.Commands.Internal.Format</span></span>

<span data-ttu-id="6fa78-260">`Format-Table` Возвращает объекты форматирования, представляющие таблицу.</span><span class="sxs-lookup"><span data-stu-id="6fa78-260">`Format-Table` returns format objects that represent the table.</span></span>

## <span data-ttu-id="6fa78-261">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="6fa78-261">NOTES</span></span>

## <span data-ttu-id="6fa78-262">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="6fa78-262">RELATED LINKS</span></span>

[<span data-ttu-id="6fa78-263">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="6fa78-263">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="6fa78-264">about_Format.ps1xml</span><span class="sxs-lookup"><span data-stu-id="6fa78-264">about_Format.ps1xml</span></span>](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md)

[<span data-ttu-id="6fa78-265">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="6fa78-265">about_Hash_Tables</span></span>](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md)

[<span data-ttu-id="6fa78-266">Export-FormatData</span><span class="sxs-lookup"><span data-stu-id="6fa78-266">Export-FormatData</span></span>](Export-FormatData.md)

[<span data-ttu-id="6fa78-267">Format-Custom</span><span class="sxs-lookup"><span data-stu-id="6fa78-267">Format-Custom</span></span>](Format-Custom.md)

[<span data-ttu-id="6fa78-268">Format-Hex</span><span class="sxs-lookup"><span data-stu-id="6fa78-268">Format-Hex</span></span>](Format-Hex.md)

[<span data-ttu-id="6fa78-269">Format-List</span><span class="sxs-lookup"><span data-stu-id="6fa78-269">Format-List</span></span>](Format-List.md)

[<span data-ttu-id="6fa78-270">Format-Wide</span><span class="sxs-lookup"><span data-stu-id="6fa78-270">Format-Wide</span></span>](Format-Wide.md)

[<span data-ttu-id="6fa78-271">Get-FormatData;</span><span class="sxs-lookup"><span data-stu-id="6fa78-271">Get-FormatData</span></span>](Get-FormatData.md)

[<span data-ttu-id="6fa78-272">Get-Member</span><span class="sxs-lookup"><span data-stu-id="6fa78-272">Get-Member</span></span>](Get-Member.md)

[<span data-ttu-id="6fa78-273">Get-CimInstance</span><span class="sxs-lookup"><span data-stu-id="6fa78-273">Get-CimInstance</span></span>](../CimCmdlets/Get-CimInstance.md)

[<span data-ttu-id="6fa78-274">Update-FormatData</span><span class="sxs-lookup"><span data-stu-id="6fa78-274">Update-FormatData</span></span>](Update-FormatData.md)
