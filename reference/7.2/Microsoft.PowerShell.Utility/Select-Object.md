---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/25/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/select-object?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Select-Object;
ms.openlocfilehash: 80882d27c9c8fa2d7f9e1c8ca00a02cf73ae94e6
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602696"
---
# <span data-ttu-id="b8f16-102">Select-Object;</span><span class="sxs-lookup"><span data-stu-id="b8f16-102">Select-Object</span></span>

## <span data-ttu-id="b8f16-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="b8f16-103">SYNOPSIS</span></span>
<span data-ttu-id="b8f16-104">Выбирает объекты или свойства объектов.</span><span class="sxs-lookup"><span data-stu-id="b8f16-104">Selects objects or object properties.</span></span>

## <span data-ttu-id="b8f16-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b8f16-105">SYNTAX</span></span>

### <span data-ttu-id="b8f16-106">Дефаултпараметер (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="b8f16-106">DefaultParameter (Default)</span></span>

```
Select-Object [-InputObject <PSObject>] [[-Property] <Object[]>] [-ExcludeProperty <String[]>]
 [-ExpandProperty <String>] [-Unique] [-Last <Int32>] [-First <Int32>] [-Skip <Int32>] [-Wait]
 [<CommonParameters>]
```

### <span data-ttu-id="b8f16-107">скипластпараметер</span><span class="sxs-lookup"><span data-stu-id="b8f16-107">SkipLastParameter</span></span>

```
Select-Object [-InputObject <PSObject>] [[-Property] <Object[]>] [-ExcludeProperty <String[]>]
 [-ExpandProperty <String>] [-Unique] [-SkipLast <Int32>] [<CommonParameters>]
```

### <span data-ttu-id="b8f16-108">индекспараметер</span><span class="sxs-lookup"><span data-stu-id="b8f16-108">IndexParameter</span></span>

```
Select-Object [-InputObject <PSObject>] [-Unique] [-Wait] [-Index <Int32[]>] [<CommonParameters>]
```

### <span data-ttu-id="b8f16-109">скипиндекспараметер</span><span class="sxs-lookup"><span data-stu-id="b8f16-109">SkipIndexParameter</span></span>

```
Select-Object [-InputObject <PSObject>] [-Unique] [-SkipIndex <Int32[]>] [<CommonParameters>]
```

## <span data-ttu-id="b8f16-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b8f16-110">DESCRIPTION</span></span>

<span data-ttu-id="b8f16-111">`Select-Object`Командлет выбирает указанные свойства объекта или набора объектов.</span><span class="sxs-lookup"><span data-stu-id="b8f16-111">The `Select-Object` cmdlet selects specified properties of an object or set of objects.</span></span> <span data-ttu-id="b8f16-112">Он также может выбирать уникальные объекты, указанное число объектов или объекты в указанной позиции в массиве.</span><span class="sxs-lookup"><span data-stu-id="b8f16-112">It can also select unique objects, a specified number of objects, or objects in a specified position in an array.</span></span>

<span data-ttu-id="b8f16-113">Чтобы выбрать объекты из коллекции, используйте параметры **First**, **Last**, **Unique**, **Skip** и **Index**.</span><span class="sxs-lookup"><span data-stu-id="b8f16-113">To select objects from a collection, use the **First**, **Last**, **Unique**, **Skip**, and **Index** parameters.</span></span> <span data-ttu-id="b8f16-114">Чтобы выбрать свойства объектов, используйте параметр **Property**.</span><span class="sxs-lookup"><span data-stu-id="b8f16-114">To select object properties, use the **Property** parameter.</span></span> <span data-ttu-id="b8f16-115">При выборе свойства `Select-Object` возвращает новые объекты, которые имеют только указанные свойства.</span><span class="sxs-lookup"><span data-stu-id="b8f16-115">When you select properties, `Select-Object` returns new objects that have only the specified properties.</span></span>

<span data-ttu-id="b8f16-116">Начиная с Windows PowerShell 3,0, `Select-Object` включает функцию оптимизации, которая предотвращает создание и обработку неиспользуемых объектов командами.</span><span class="sxs-lookup"><span data-stu-id="b8f16-116">Beginning in Windows PowerShell 3.0, `Select-Object` includes an optimization feature that prevents commands from creating and processing objects that are not used.</span></span>

<span data-ttu-id="b8f16-117">При включении `Select-Object` команды с **первым** или **индексными** параметрами в конвейере команд PowerShell останавливает команду, создающую объекты, как только выбранное число объектов будет создано, даже если команда, создающая объекты, появилась перед `Select-Object` командой в конвейере.</span><span class="sxs-lookup"><span data-stu-id="b8f16-117">When you include a `Select-Object` command with the **First** or **Index** parameters in a command pipeline, PowerShell stops the command that generates the objects as soon as the selected number of objects is generated, even when the command that generates the objects appears before the `Select-Object` command in the pipeline.</span></span> <span data-ttu-id="b8f16-118">Чтобы отключить эту функцию оптимизации, используйте параметр **Wait**.</span><span class="sxs-lookup"><span data-stu-id="b8f16-118">To turn off this optimizing behavior, use the **Wait** parameter.</span></span>

## <span data-ttu-id="b8f16-119">Примеры</span><span class="sxs-lookup"><span data-stu-id="b8f16-119">EXAMPLES</span></span>

### <span data-ttu-id="b8f16-120">Пример 1. Выбор объектов по свойству</span><span class="sxs-lookup"><span data-stu-id="b8f16-120">Example 1: Select objects by property</span></span>

<span data-ttu-id="b8f16-121">В этом примере создаются объекты, имеющие свойства **Name**, **ID** и Working Set (**WS**) объектов Process.</span><span class="sxs-lookup"><span data-stu-id="b8f16-121">This example creates objects that have the **Name**, **ID**, and working set (**WS**) properties of process objects.</span></span>

```powershell
Get-Process | Select-Object -Property ProcessName, Id, WS
```

### <span data-ttu-id="b8f16-122">Пример 2. Выбор объектов по свойству и форматирование результатов</span><span class="sxs-lookup"><span data-stu-id="b8f16-122">Example 2: Select objects by property and format the results</span></span>

<span data-ttu-id="b8f16-123">Этот пример возвращает сведения о модулях, используемых процессами на компьютере.</span><span class="sxs-lookup"><span data-stu-id="b8f16-123">This example gets information about the modules used by the processes on the computer.</span></span> <span data-ttu-id="b8f16-124">Он использует `Get-Process` командлет для получения процесса на компьютере.</span><span class="sxs-lookup"><span data-stu-id="b8f16-124">It uses `Get-Process` cmdlet to get the process on the computer.</span></span>

<span data-ttu-id="b8f16-125">Он использует `Select-Object` командлет для вывода массива `[System.Diagnostics.ProcessModule]` экземпляров, содержащихся в свойстве **modules** каждого `System.Diagnostics.Process` экземпляра, с помощью `Get-Process` .</span><span class="sxs-lookup"><span data-stu-id="b8f16-125">It uses the `Select-Object` cmdlet to output an array of `[System.Diagnostics.ProcessModule]` instances as contained in the **Modules** property of each `System.Diagnostics.Process` instance output by `Get-Process`.</span></span>

<span data-ttu-id="b8f16-126">Параметр **Property** `Select-Object` командлета выбирает имена процессов.</span><span class="sxs-lookup"><span data-stu-id="b8f16-126">The **Property** parameter of the `Select-Object` cmdlet selects the process names.</span></span> <span data-ttu-id="b8f16-127">Это добавляет `ProcessName` **NoteProperty** к каждому `[System.Diagnostics.ProcessModule]` экземпляру и заполняет его значением свойства **processName** текущего процесса.</span><span class="sxs-lookup"><span data-stu-id="b8f16-127">This adds a `ProcessName` **NoteProperty** to every `[System.Diagnostics.ProcessModule]` instance and populates it with the value of current process's **ProcessName** property.</span></span>

<span data-ttu-id="b8f16-128">Наконец, `Format-List` командлет используется для вывода имени и модулей каждого процесса в списке.</span><span class="sxs-lookup"><span data-stu-id="b8f16-128">Finally, `Format-List` cmdlet is used to display the name and modules of each process in a list.</span></span>

```powershell
Get-Process Explorer | Select-Object -Property ProcessName -ExpandProperty Modules | Format-List
```

```Output
ProcessName       : explorer
ModuleName        : explorer.exe
FileName          : C:\WINDOWS\explorer.exe
BaseAddress       : 140697278152704
ModuleMemorySize  : 3919872
EntryPointAddress : 140697278841168
FileVersionInfo   : File:             C:\WINDOWS\explorer.exe
                    InternalName:     explorer
                    OriginalFilename: EXPLORER.EXE.MUI
                    FileVersion:      10.0.17134.1 (WinBuild.160101.0800)
                    FileDescription:  Windows Explorer
                    Product:          Microsoft Windows Operating System
                    ProductVersion:   10.0.17134.1
...
```

### <span data-ttu-id="b8f16-129">Пример 3. Выбор процессов с наибольшим объемом памяти</span><span class="sxs-lookup"><span data-stu-id="b8f16-129">Example 3: Select processes using the most memory</span></span>

<span data-ttu-id="b8f16-130">Этот пример получает пять процессов, использующих наибольшую память.</span><span class="sxs-lookup"><span data-stu-id="b8f16-130">This example gets the five processes that are using the most memory.</span></span> <span data-ttu-id="b8f16-131">`Get-Process`Командлет возвращает процессы на компьютере.</span><span class="sxs-lookup"><span data-stu-id="b8f16-131">The `Get-Process` cmdlet gets the processes on the computer.</span></span> <span data-ttu-id="b8f16-132">`Sort-Object`Командлет сортирует процессы в соответствии с использованием памяти (рабочего набора), и `Select-Object` командлет выбирает только последние пять элементов результирующего массива объектов.</span><span class="sxs-lookup"><span data-stu-id="b8f16-132">The `Sort-Object` cmdlet sorts the processes according to memory (working set) usage, and the `Select-Object` cmdlet selects only the last five members of the resulting array of objects.</span></span>

<span data-ttu-id="b8f16-133">Параметр **Wait** не требуется в командах, включающих `Sort-Object` командлет, так как `Sort-Object` обрабатывает все объекты, а затем возвращает коллекцию.</span><span class="sxs-lookup"><span data-stu-id="b8f16-133">The **Wait** parameter is not required in commands that include the `Sort-Object` cmdlet because `Sort-Object` processes all objects and then returns a collection.</span></span> <span data-ttu-id="b8f16-134">`Select-Object`Оптимизация доступна только для команд, которые возвращают объекты по отдельности при их обработке.</span><span class="sxs-lookup"><span data-stu-id="b8f16-134">The `Select-Object` optimization is available only for commands that return objects individually as they are processed.</span></span>

```powershell
Get-Process | Sort-Object -Property WS | Select-Object -Last 5
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VS(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
2866     320       33432      45764   203   222.41   1292 svchost
577      17        23676      50516   265    50.58   4388 WINWORD
826      11        75448      76712   188    19.77   3780 Ps
1367     14        73152      88736   216    61.69    676 Ps
1612     44        66080      92780   380   900.59   6132 INFOPATH
```

### <span data-ttu-id="b8f16-135">Пример 4. выбор уникальных символов из массива</span><span class="sxs-lookup"><span data-stu-id="b8f16-135">Example 4: Select unique characters from an array</span></span>

<span data-ttu-id="b8f16-136">В этом примере  `Select-Object` для получения уникальных символов из массива символов используется параметр Unique объекта.</span><span class="sxs-lookup"><span data-stu-id="b8f16-136">This example uses the **Unique** parameter of `Select-Object` to get unique characters from an array of characters.</span></span>

```powershell
"a","b","c","a","a","a" | Select-Object -Unique
```

```Output
a
b
c
```

### <span data-ttu-id="b8f16-137">Пример 5. Выбор новых и старых событий в журнале событий</span><span class="sxs-lookup"><span data-stu-id="b8f16-137">Example 5: Select newest and oldest events in the event log</span></span>

<span data-ttu-id="b8f16-138">Этот пример получает первые (самые новые) и последние (самые старые) события в журнале событий Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b8f16-138">This example gets the first (newest) and last (oldest) events in the Windows PowerShell event log.</span></span>

<span data-ttu-id="b8f16-139">`Get-EventLog` Возвращает все события в журнале Windows PowerShell и сохраняет их в `$a` переменной.</span><span class="sxs-lookup"><span data-stu-id="b8f16-139">`Get-EventLog` gets all events in the Windows PowerShell log and saves them in the `$a` variable.</span></span>
<span data-ttu-id="b8f16-140">Затем `$a` передается в `Select-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="b8f16-140">Then, `$a` is piped to the `Select-Object` cmdlet.</span></span> <span data-ttu-id="b8f16-141">`Select-Object`Команда использует параметр **index** для выбора событий из массива событий в `$a` переменной.</span><span class="sxs-lookup"><span data-stu-id="b8f16-141">The `Select-Object` command uses the **Index** parameter to select events from the array of events in the `$a` variable.</span></span> <span data-ttu-id="b8f16-142">Индекс первого события равен 0.</span><span class="sxs-lookup"><span data-stu-id="b8f16-142">The index of the first event is 0.</span></span> <span data-ttu-id="b8f16-143">Индекс последнего события — это число элементов за `$a` вычетом 1.</span><span class="sxs-lookup"><span data-stu-id="b8f16-143">The index of the last event is the number of items in `$a` minus 1.</span></span>

```powershell
$a = Get-EventLog -LogName "Windows PowerShell"
$a | Select-Object -Index 0, ($A.count - 1)
```

### <span data-ttu-id="b8f16-144">Пример 6. выделение всех объектов, кроме первого</span><span class="sxs-lookup"><span data-stu-id="b8f16-144">Example 6: Select all but the first object</span></span>

<span data-ttu-id="b8f16-145">В этом примере создается новый сеанс PSSession на каждом из компьютеров, перечисленных в файлах Servers.txt, за исключением первого.</span><span class="sxs-lookup"><span data-stu-id="b8f16-145">This example creates a new PSSession on each of the computers listed in the Servers.txt files, except for the first one.</span></span>

<span data-ttu-id="b8f16-146">`Select-Object` выбирает все компьютеры, кроме первого, в списке имен компьютеров.</span><span class="sxs-lookup"><span data-stu-id="b8f16-146">`Select-Object` selects all but the first computer in a list of computer names.</span></span> <span data-ttu-id="b8f16-147">Результирующий список компьютеров задается в качестве значения параметра **ComputerName** `New-PSSession` командлета.</span><span class="sxs-lookup"><span data-stu-id="b8f16-147">The resulting list of computers is set as the value of the **ComputerName** parameter of the `New-PSSession` cmdlet.</span></span>

```powershell
New-PSSession -ComputerName (Get-Content Servers.txt | Select-Object -Skip 1)
```

### <span data-ttu-id="b8f16-148">Пример 7. Переименование файлов и выбор нескольких для проверки</span><span class="sxs-lookup"><span data-stu-id="b8f16-148">Example 7: Rename files and select several to review</span></span>

<span data-ttu-id="b8f16-149">В этом примере добавляется суффикс "-RO" к базовым именам текстовых файлов с атрибутом "только для чтения", а затем выводятся первые пять файлов, чтобы пользователь мог увидеть образец этого действия.</span><span class="sxs-lookup"><span data-stu-id="b8f16-149">This example adds a "-ro" suffix to the base names of text files that have the read-only attribute and then displays the first five files so the user can see a sample of the effect.</span></span>

<span data-ttu-id="b8f16-150">`Get-ChildItem` использует динамический параметр ReadOnly для получения файлов, доступных только **для** чтения.</span><span class="sxs-lookup"><span data-stu-id="b8f16-150">`Get-ChildItem` uses the **ReadOnly** dynamic parameter to get read-only files.</span></span> <span data-ttu-id="b8f16-151">Результирующие файлы передаются в `Rename-Item` командлет, который переименовывает файл.</span><span class="sxs-lookup"><span data-stu-id="b8f16-151">The resulting files are piped to the `Rename-Item` cmdlet, which renames the file.</span></span> <span data-ttu-id="b8f16-152">Параметр **PassThru** параметра используется `Rename-Item` для отправки переименованных файлов в `Select-Object` командлет, который выбирает первые 5 для экрана.</span><span class="sxs-lookup"><span data-stu-id="b8f16-152">It uses the **Passthru** parameter of `Rename-Item` to send the renamed files to the `Select-Object` cmdlet, which selects the first 5 for display.</span></span>

<span data-ttu-id="b8f16-153">Параметр **Wait** `Select-Object` предотвращает остановку `Get-ChildItem` командлета PowerShell после получения первых пяти текстовых файлов, которые доступны только для чтения.</span><span class="sxs-lookup"><span data-stu-id="b8f16-153">The **Wait** parameter of `Select-Object` prevents PowerShell from stopping the `Get-ChildItem` cmdlet after it gets the first five read-only text files.</span></span> <span data-ttu-id="b8f16-154">Без этого параметра были бы переименованы только первые пять таких файлов.</span><span class="sxs-lookup"><span data-stu-id="b8f16-154">Without this parameter, only the first five read-only files would be renamed.</span></span>

```powershell
Get-ChildItem *.txt -ReadOnly |
    Rename-Item -NewName {$_.BaseName + "-ro.txt"} -PassThru |
    Select-Object -First 5 -Wait
```

### <span data-ttu-id="b8f16-155">Пример 8. Демонстрация тонкостей параметра-Експандпроперти</span><span class="sxs-lookup"><span data-stu-id="b8f16-155">Example 8: Demonstrate the intricacies of the -ExpandProperty parameter</span></span>

<span data-ttu-id="b8f16-156">В этом примере демонстрируются сложности параметра **експандпроперти** .</span><span class="sxs-lookup"><span data-stu-id="b8f16-156">This example demonstrates the intricacies of the **ExpandProperty** parameter.</span></span>

<span data-ttu-id="b8f16-157">Обратите внимание, что создаваемые выходные данные были массивом `[System.Int32]` экземпляров.</span><span class="sxs-lookup"><span data-stu-id="b8f16-157">Note that the output generated was an array of `[System.Int32]` instances.</span></span> <span data-ttu-id="b8f16-158">Экземпляры соответствуют стандартным правилам форматирования **представления вывода**.</span><span class="sxs-lookup"><span data-stu-id="b8f16-158">The instances conform to standard formatting rules of the **Output View**.</span></span> <span data-ttu-id="b8f16-159">Это справедливо для всех *развернутых* свойств.</span><span class="sxs-lookup"><span data-stu-id="b8f16-159">This is true for any *Expanded* properties.</span></span> <span data-ttu-id="b8f16-160">Если выводимые объекты имеют конкретный стандартный формат, то развернутое свойство может быть невидимым.</span><span class="sxs-lookup"><span data-stu-id="b8f16-160">If the outputted objects have a specific standard format, the expanded property might not be visible.</span></span>

```powershell
# Create a custom object to use for the Select-Object example.
$object = [pscustomobject]@{Name="CustomObject";Expand=@(1,2,3,4,5)}
# Use the ExpandProperty parameter to Expand the property.
$object | Select-Object -ExpandProperty Expand -Property Name
```

```Output
1
2
3
4
5
```

```powershell
# The output did not contain the Name property, but it was added successfully.
# Use Get-Member to confirm the Name property was added and populated.
$object | Select-Object -ExpandProperty Expand -Property Name | Get-Member
```

```Output
   TypeName: System.Int32

Name        MemberType   Definition
----        ----------   ----------
CompareTo   Method       int CompareTo(System.Object value), int CompareTo(int value), int IComparable.CompareTo(System.Object obj)...
Equals      Method       bool Equals(System.Object obj), bool Equals(int obj), bool IEquatable[int].Equals(int other)
GetHashCode Method       int GetHashCode()
GetType     Method       type GetType()
GetTypeCode Method       System.TypeCode GetTypeCode(), System.TypeCode IConvertible.GetTypeCode()
ToBoolean   Method       bool IConvertible.ToBoolean(System.IFormatProvider provider)
ToByte      Method       byte IConvertible.ToByte(System.IFormatProvider provider)
ToChar      Method       char IConvertible.ToChar(System.IFormatProvider provider)
ToDateTime  Method       datetime IConvertible.ToDateTime(System.IFormatProvider provider)
ToDecimal   Method       decimal IConvertible.ToDecimal(System.IFormatProvider provider)
ToDouble    Method       double IConvertible.ToDouble(System.IFormatProvider provider)
ToInt16     Method       int16 IConvertible.ToInt16(System.IFormatProvider provider)
ToInt32     Method       int IConvertible.ToInt32(System.IFormatProvider provider)
ToInt64     Method       long IConvertible.ToInt64(System.IFormatProvider provider)
ToSByte     Method       sbyte IConvertible.ToSByte(System.IFormatProvider provider)
ToSingle    Method       float IConvertible.ToSingle(System.IFormatProvider provider)
ToString    Method       string ToString(), string ToString(string format), string ToString(System.IFormatProvider provider)...
ToType      Method       System.Object IConvertible.ToType(type conversionType, System.IFormatProvider provider)
ToUInt16    Method       uint16 IConvertible.ToUInt16(System.IFormatProvider provider)
ToUInt32    Method       uint32 IConvertible.ToUInt32(System.IFormatProvider provider)
ToUInt64    Method       uint64 IConvertible.ToUInt64(System.IFormatProvider provider)
Name        NoteProperty string Name=CustomObject
```

### <span data-ttu-id="b8f16-161">Пример 9. Создание пользовательских свойств для объектов</span><span class="sxs-lookup"><span data-stu-id="b8f16-161">Example 9: Create custom properties on objects</span></span>

<span data-ttu-id="b8f16-162">В следующем примере демонстрируется использование `Select-Object` для добавления пользовательского свойства в любой объект.</span><span class="sxs-lookup"><span data-stu-id="b8f16-162">The following example demonstrates using `Select-Object` to add a custom property to any object.</span></span>
<span data-ttu-id="b8f16-163">При указании несуществующего имени свойства `Select-Object` создает это свойство как **NoteProperty** для каждого переданного объекта.</span><span class="sxs-lookup"><span data-stu-id="b8f16-163">When you specify a property name that does not exist, `Select-Object` creates that property as a **NoteProperty** on each object passed.</span></span>

```powershell
$customObject = 1 | Select-Object -Property MyCustomProperty
$customObject.MyCustomProperty = "New Custom Property"
$customObject
```

```Output
MyCustomProperty
----------------
New Custom Property
```

### <span data-ttu-id="b8f16-164">Пример 10. Создание вычисляемых свойств для каждого InputObject</span><span class="sxs-lookup"><span data-stu-id="b8f16-164">Example 10: Create calculated properties for each InputObject</span></span>

<span data-ttu-id="b8f16-165">В этом примере демонстрируется использование `Select-Object` для добавления вычисляемых свойств к входным данным.</span><span class="sxs-lookup"><span data-stu-id="b8f16-165">This example demonstrates using `Select-Object` to add calculated properties to your input.</span></span> <span data-ttu-id="b8f16-166">Передача параметра **ScriptBlock** в параметр **Property** приводит `Select-Object` к вычислению выражения для каждого переданного объекта и добавлению результатов в выходные данные.</span><span class="sxs-lookup"><span data-stu-id="b8f16-166">Passing a **ScriptBlock** to the **Property** parameter causes `Select-Object` to evaluate the expression on each object passed and add the results to the output.</span></span> <span data-ttu-id="b8f16-167">В блоке **сценария** можно использовать `$_` переменную для ссылки на текущий объект в конвейере.</span><span class="sxs-lookup"><span data-stu-id="b8f16-167">Within the **ScriptBlock**, you can use the `$_` variable to reference the current object in the pipeline.</span></span>

<span data-ttu-id="b8f16-168">По умолчанию в `Select-Object` качестве имени свойства будет использоваться строка **ScriptBlock** .</span><span class="sxs-lookup"><span data-stu-id="b8f16-168">By default, `Select-Object` will use the **ScriptBlock** string as the name of the property.</span></span> <span data-ttu-id="b8f16-169">С помощью **хэш-таблицы** можно пометить выходные данные **ScriptBlock** как пользовательское свойство, добавляемое к каждому объекту.</span><span class="sxs-lookup"><span data-stu-id="b8f16-169">Using a **Hashtable**, you can label the output of your **ScriptBlock** as a custom property added to each object.</span></span> <span data-ttu-id="b8f16-170">К каждому объекту, переданному в, можно добавить несколько вычисляемых свойств `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="b8f16-170">You can add multiple calculated properties to each object passed to `Select-Object`.</span></span>

```powershell
# Create a calculated property called $_.StartTime.DayOfWeek
Get-Process | Select-Object -Property ProcessName,{$_.StartTime.DayOfWeek}
```

```Output
ProcessName  $_.StartTime.DayOfWeek
----         ----------------------
alg                       Wednesday
ati2evxx                  Wednesday
ati2evxx                   Thursday
...
```

```powershell
# Add a custom property to calculate the size in KiloBytes of each FileInfo object you pass in.
# Use the pipeline variable to divide each file's length by 1 KiloBytes
$size = @{label="Size(KB)";expression={$_.length/1KB}}
# Create an additional calculated property with the number of Days since the file was last accessed.
# You can also shorten the key names to be 'l', and 'e', or use Name instead of Label.
$days = @{l="Days";e={((Get-Date) - $_.LastAccessTime).Days}}
# You can also shorten the name of your label key to 'l' and your expression key to 'e'.
Get-ChildItem $PSHOME -File | Select-Object Name, $size, $days
```

```Output
Name                        Size(KB)        Days
----                        --------        ----
Certificate.format.ps1xml   12.5244140625   223
Diagnostics.Format.ps1xml   4.955078125     223
DotNetTypes.format.ps1xml   134.9833984375  223
```

## <span data-ttu-id="b8f16-171">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b8f16-171">PARAMETERS</span></span>

### <span data-ttu-id="b8f16-172">-ExcludeProperty командлета</span><span class="sxs-lookup"><span data-stu-id="b8f16-172">-ExcludeProperty</span></span>

<span data-ttu-id="b8f16-173">Указывает свойства, которые этот командлет исключает из операции.</span><span class="sxs-lookup"><span data-stu-id="b8f16-173">Specifies the properties that this cmdlet excludes from the operation.</span></span> <span data-ttu-id="b8f16-174">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="b8f16-174">Wildcards are permitted.</span></span>

<span data-ttu-id="b8f16-175">Начиная с PowerShell 6, больше не требуется включать параметр **Property** для **ExcludeProperty командлета** в работу.</span><span class="sxs-lookup"><span data-stu-id="b8f16-175">Beginning in PowerShell 6, it is no longer required to include the **Property** parameter for **ExcludeProperty** to work.</span></span>

```yaml
Type: System.String[]
Parameter Sets: DefaultParameter, SkipLastParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="b8f16-176">-Експандпроперти</span><span class="sxs-lookup"><span data-stu-id="b8f16-176">-ExpandProperty</span></span>

<span data-ttu-id="b8f16-177">Задает свойство, которое нужно выбрать, и указывает, что нужно попытаться расширить его.</span><span class="sxs-lookup"><span data-stu-id="b8f16-177">Specifies a property to select, and indicates that an attempt should be made to expand that property.</span></span>

- <span data-ttu-id="b8f16-178">Если указанное свойство является массивом, каждое значение массива включается в выход.</span><span class="sxs-lookup"><span data-stu-id="b8f16-178">If the specified property is an array, each value of the array is included in the output.</span></span>
- <span data-ttu-id="b8f16-179">Если указанное свойство является объектом, то свойства объектов разворачиваются для каждого объекта **InputObject** .</span><span class="sxs-lookup"><span data-stu-id="b8f16-179">If the specified property is an object, the objects properties are expanded for every **InputObject**</span></span>

<span data-ttu-id="b8f16-180">В любом случае **тип** выходных данных объектов будет соответствовать **типу** развернутого свойства.</span><span class="sxs-lookup"><span data-stu-id="b8f16-180">In either case, the **Type** of objects output will match the **Type** of the expanded property.</span></span>

<span data-ttu-id="b8f16-181">Если указан параметр **Property** , `Select-Object` попытается добавить каждое выбранное свойство как **NoteProperty** в каждый выведенный объект.</span><span class="sxs-lookup"><span data-stu-id="b8f16-181">If the **Property** parameter is specified, `Select-Object` will attempt to add each selected property as a **NoteProperty** to every outputted object.</span></span>

> [!WARNING]
> <span data-ttu-id="b8f16-182">Если возникает ошибка: SELECT: свойство не может быть обработано, так как свойство `<PropertyName>` уже существует, учтите следующее.</span><span class="sxs-lookup"><span data-stu-id="b8f16-182">If you receive the error: Select : Property cannot be processed because property `<PropertyName>` already exists, consider the following.</span></span>
> <span data-ttu-id="b8f16-183">Обратите внимание, что при использовании `-ExpandProperty` `Select-Object` не может заменить существующее свойство.</span><span class="sxs-lookup"><span data-stu-id="b8f16-183">Note that when using `-ExpandProperty`, `Select-Object` can not replace an existing property.</span></span>
> <span data-ttu-id="b8f16-184">Это означает следующее:</span><span class="sxs-lookup"><span data-stu-id="b8f16-184">This means:</span></span>
>
> - <span data-ttu-id="b8f16-185">Если развернутый объект имеет свойство с тем же именем, возникнет ошибка.</span><span class="sxs-lookup"><span data-stu-id="b8f16-185">If the expanded object has a property of the same name, an error will occur.</span></span>
> - <span data-ttu-id="b8f16-186">Если у *выбранного* объекта есть свойство с тем же именем, что и у *развернутого* свойства объектов, возникнет ошибка.</span><span class="sxs-lookup"><span data-stu-id="b8f16-186">If the *Selected* object has a property of the same name as an *Expanded* objects property, an error will occur.</span></span>

```yaml
Type: System.String
Parameter Sets: DefaultParameter, SkipLastParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b8f16-187">-First</span><span class="sxs-lookup"><span data-stu-id="b8f16-187">-First</span></span>

<span data-ttu-id="b8f16-188">Указывает число объектов, которое нужно выбрать с начала массива входных объектов.</span><span class="sxs-lookup"><span data-stu-id="b8f16-188">Specifies the number of objects to select from the beginning of an array of input objects.</span></span>

```yaml
Type: System.Int32
Parameter Sets: DefaultParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b8f16-189">-Index</span><span class="sxs-lookup"><span data-stu-id="b8f16-189">-Index</span></span>

<span data-ttu-id="b8f16-190">Выбирает объекты из массива в соответствии со значениями индекса.</span><span class="sxs-lookup"><span data-stu-id="b8f16-190">Selects objects from an array based on their index values.</span></span> <span data-ttu-id="b8f16-191">Введите индексы в виде разделенного запятыми списка.</span><span class="sxs-lookup"><span data-stu-id="b8f16-191">Enter the indexes in a comma-separated list.</span></span> <span data-ttu-id="b8f16-192">Индексы массива начинаются с нуля, то есть 0 представляет первое значение, а (n-1) — последнее значение.</span><span class="sxs-lookup"><span data-stu-id="b8f16-192">Indexes in an array begin with 0, where 0 represents the first value and (n-1) represents the last value.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: IndexParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b8f16-193">-InputObject</span><span class="sxs-lookup"><span data-stu-id="b8f16-193">-InputObject</span></span>

<span data-ttu-id="b8f16-194">Указывает объекты, которые необходимо передать в командлет по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="b8f16-194">Specifies objects to send to the cmdlet through the pipeline.</span></span> <span data-ttu-id="b8f16-195">Этот параметр позволяет передавать объекты в `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="b8f16-195">This parameter enables you to pipe objects to `Select-Object`.</span></span>

<span data-ttu-id="b8f16-196">При передаче объектов в параметр **InputObject** вместо использования конвейера `Select-Object` обрабатывает **InputObject** как отдельный объект, даже если это значение является коллекцией.</span><span class="sxs-lookup"><span data-stu-id="b8f16-196">When you pass objects to the **InputObject** parameter, instead of using the pipeline, `Select-Object` treats the **InputObject** as a single object, even if the value is a collection.</span></span> <span data-ttu-id="b8f16-197">Рекомендуется использовать конвейер при передаче коллекций в `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="b8f16-197">It is recommended that you use the pipeline when passing collections to `Select-Object`.</span></span>

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

### <span data-ttu-id="b8f16-198">-Last</span><span class="sxs-lookup"><span data-stu-id="b8f16-198">-Last</span></span>

<span data-ttu-id="b8f16-199">Указывает число объектов, которое нужно выбрать с конца массива входных объектов.</span><span class="sxs-lookup"><span data-stu-id="b8f16-199">Specifies the number of objects to select from the end of an array of input objects.</span></span>

```yaml
Type: System.Int32
Parameter Sets: DefaultParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b8f16-200">-Property</span><span class="sxs-lookup"><span data-stu-id="b8f16-200">-Property</span></span>

<span data-ttu-id="b8f16-201">Указывает свойства, которые нужно выбрать.</span><span class="sxs-lookup"><span data-stu-id="b8f16-201">Specifies the properties to select.</span></span> <span data-ttu-id="b8f16-202">Эти свойства добавляются в выходные объекты в качестве элементов **NoteProperty** .</span><span class="sxs-lookup"><span data-stu-id="b8f16-202">These properties are added as **NoteProperty** members to the output objects.</span></span> <span data-ttu-id="b8f16-203">Разрешено использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="b8f16-203">Wildcards are permitted.</span></span>

<span data-ttu-id="b8f16-204">Значением параметра **Property** может быть новое вычисляемое свойство.</span><span class="sxs-lookup"><span data-stu-id="b8f16-204">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="b8f16-205">Чтобы создать вычисляемое свойство, используйте хэш-таблицу.</span><span class="sxs-lookup"><span data-stu-id="b8f16-205">To create a calculated, property, use a hash table.</span></span>

<span data-ttu-id="b8f16-206">Допустимые разделы следующие:</span><span class="sxs-lookup"><span data-stu-id="b8f16-206">Valid keys are:</span></span>

- <span data-ttu-id="b8f16-207">Имя (или метка) — `<string>`</span><span class="sxs-lookup"><span data-stu-id="b8f16-207">Name (or Label) - `<string>`</span></span>
- <span data-ttu-id="b8f16-208">Выражение — `<string>` или `<script block>`</span><span class="sxs-lookup"><span data-stu-id="b8f16-208">Expression - `<string>` or `<script block>`</span></span>

<span data-ttu-id="b8f16-209">Дополнительные сведения см. в разделе [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="b8f16-209">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: DefaultParameter, SkipLastParameter
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="b8f16-210">-Skip</span><span class="sxs-lookup"><span data-stu-id="b8f16-210">-Skip</span></span>

<span data-ttu-id="b8f16-211">Пропускает (не выбирает) указанное число элементов.</span><span class="sxs-lookup"><span data-stu-id="b8f16-211">Skips (does not select) the specified number of items.</span></span> <span data-ttu-id="b8f16-212">По умолчанию параметр **Skip** подсчитывает число с начала массива или списка объектов, но если команда использует **последний** параметр, она подсчитывается из конца списка или массива.</span><span class="sxs-lookup"><span data-stu-id="b8f16-212">By default, the **Skip** parameter counts from the beginning of the array or list of objects, but if the command uses the **Last** parameter, it counts from the end of the list or array.</span></span>

<span data-ttu-id="b8f16-213">В отличие от параметра **Index**, значение которого отсчитывается от 0, параметр **Skip** начинается с единицы.</span><span class="sxs-lookup"><span data-stu-id="b8f16-213">Unlike the **Index** parameter, which starts counting at 0, the **Skip** parameter begins at 1.</span></span>

```yaml
Type: System.Int32
Parameter Sets: DefaultParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b8f16-214">-Скипласт</span><span class="sxs-lookup"><span data-stu-id="b8f16-214">-SkipLast</span></span>

<span data-ttu-id="b8f16-215">Пропускает (не выбирает) указанное число элементов из конца списка или массива.</span><span class="sxs-lookup"><span data-stu-id="b8f16-215">Skips (does not select) the specified number of items from the end of the list or array.</span></span> <span data-ttu-id="b8f16-216">Работает так же, как при использовании функции **Skip** вместе с **последним** параметром.</span><span class="sxs-lookup"><span data-stu-id="b8f16-216">Works in the same way as using **Skip** together with **Last** parameter.</span></span>

<span data-ttu-id="b8f16-217">В отличие от параметра **index** , при котором отсчет начинается с 0, параметр **скипласт** начинается с 1.</span><span class="sxs-lookup"><span data-stu-id="b8f16-217">Unlike the **Index** parameter, which starts counting at 0, the **SkipLast** parameter begins at 1.</span></span>

```yaml
Type: System.Int32
Parameter Sets: SkipLastParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b8f16-218">— Уникальный</span><span class="sxs-lookup"><span data-stu-id="b8f16-218">-Unique</span></span>

<span data-ttu-id="b8f16-219">Указывает, что, если подмножество входных объектов имеет идентичные свойства и значения, выбран будет только один член подмножества.</span><span class="sxs-lookup"><span data-stu-id="b8f16-219">Specifies that if a subset of the input objects has identical properties and values, only a single member of the subset will be selected.</span></span>

<span data-ttu-id="b8f16-220">Этот параметр чувствителен к регистру.</span><span class="sxs-lookup"><span data-stu-id="b8f16-220">This parameter is case-sensitive.</span></span> <span data-ttu-id="b8f16-221">Поэтому строки, которые отличаются только регистром символов, считаются уникальными.</span><span class="sxs-lookup"><span data-stu-id="b8f16-221">As a result, strings that differ only in character casing are considered to be unique.</span></span>

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

### <span data-ttu-id="b8f16-222">-Wait</span><span class="sxs-lookup"><span data-stu-id="b8f16-222">-Wait</span></span>

<span data-ttu-id="b8f16-223">Указывает, что командлет отключает оптимизацию.</span><span class="sxs-lookup"><span data-stu-id="b8f16-223">Indicates that the cmdlet turns off optimization.</span></span> <span data-ttu-id="b8f16-224">PowerShell выполняет команды в том порядке, в котором они отображаются в конвейере команд, и позволяет им создавать все объекты.</span><span class="sxs-lookup"><span data-stu-id="b8f16-224">PowerShell runs commands in the order that they appear in the command pipeline and lets them generate all objects.</span></span> <span data-ttu-id="b8f16-225">По умолчанию при включении `Select-Object` команды с **первым** или **индексным** параметром в конвейере команд PowerShell останавливает команду, создающую объекты, как только выбранное число объектов будет создано.</span><span class="sxs-lookup"><span data-stu-id="b8f16-225">By default, if you include a `Select-Object` command with the **First** or **Index** parameters in a command pipeline, PowerShell stops the command that generates the objects as soon as the selected number of objects is generated.</span></span>

<span data-ttu-id="b8f16-226">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="b8f16-226">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DefaultParameter, IndexParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b8f16-227">-Скипиндекс</span><span class="sxs-lookup"><span data-stu-id="b8f16-227">-SkipIndex</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: SkipIndexParameter
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b8f16-228">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="b8f16-228">CommonParameters</span></span>

<span data-ttu-id="b8f16-229">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b8f16-229">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b8f16-230">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="b8f16-230">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="b8f16-231">Входные данные</span><span class="sxs-lookup"><span data-stu-id="b8f16-231">INPUTS</span></span>

### <span data-ttu-id="b8f16-232">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="b8f16-232">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="b8f16-233">Любой объект можно передать по конвейеру в `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="b8f16-233">You can pipe any object to `Select-Object`.</span></span>

## <span data-ttu-id="b8f16-234">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="b8f16-234">OUTPUTS</span></span>

### <span data-ttu-id="b8f16-235">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="b8f16-235">System.Management.Automation.PSObject</span></span>

## <span data-ttu-id="b8f16-236">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="b8f16-236">NOTES</span></span>

- <span data-ttu-id="b8f16-237">Также можно ссылаться на `Select-Object` командлет по его встроенному псевдониму `select` .</span><span class="sxs-lookup"><span data-stu-id="b8f16-237">You can also refer to the `Select-Object` cmdlet by its built-in alias, `select`.</span></span> <span data-ttu-id="b8f16-238">Дополнительные сведения см. в разделе [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="b8f16-238">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

- <span data-ttu-id="b8f16-239">Функция оптимизации `Select-Object` доступна только для команд, которые записывают объекты в конвейер по мере их обработки.</span><span class="sxs-lookup"><span data-stu-id="b8f16-239">The optimization feature of `Select-Object` is available only for commands that write objects to the pipeline as they are processed.</span></span> <span data-ttu-id="b8f16-240">Она не действует для команд, которые буферизуют обработанные объекты и записывают их в виде коллекции.</span><span class="sxs-lookup"><span data-stu-id="b8f16-240">It has no effect on commands that buffer processed objects and write them as a collection.</span></span> <span data-ttu-id="b8f16-241">При разработке командлетов рекомендуется немедленно записывать объекты.</span><span class="sxs-lookup"><span data-stu-id="b8f16-241">Writing objects immediately is a cmdlet design best practice.</span></span> <span data-ttu-id="b8f16-242">Дополнительные сведения см. в статье _Создание отдельных записей в конвейере_ в [строго рекомендуемых рекомендациях по разработке](/powershell/scripting/developer/windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="b8f16-242">For more information, see _Write Single Records to the Pipeline_ in [Strongly Encouraged Development Guidelines](/powershell/scripting/developer/windows-powershell).</span></span>

## <span data-ttu-id="b8f16-243">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="b8f16-243">RELATED LINKS</span></span>

[<span data-ttu-id="b8f16-244">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="b8f16-244">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="b8f16-245">Group-Object</span><span class="sxs-lookup"><span data-stu-id="b8f16-245">Group-Object</span></span>](Group-Object.md)

[<span data-ttu-id="b8f16-246">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="b8f16-246">Sort-Object</span></span>](Sort-Object.md)

[<span data-ttu-id="b8f16-247">Where-Object</span><span class="sxs-lookup"><span data-stu-id="b8f16-247">Where-Object</span></span>](../Microsoft.PowerShell.Core/Where-Object.md)
