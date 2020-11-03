---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 01/24/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/measure-command?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Measure-Command
ms.openlocfilehash: 970c72d5661796c25d6beb30eb08b6cd7032ceb1
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93226257"
---
# <span data-ttu-id="d6692-103">Measure-Command</span><span class="sxs-lookup"><span data-stu-id="d6692-103">Measure-Command</span></span>

## <span data-ttu-id="d6692-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="d6692-104">SYNOPSIS</span></span>
<span data-ttu-id="d6692-105">Измеряет время выполнения блоков скриптов и командлетов.</span><span class="sxs-lookup"><span data-stu-id="d6692-105">Measures the time it takes to run script blocks and cmdlets.</span></span>

## <span data-ttu-id="d6692-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d6692-106">SYNTAX</span></span>

```
Measure-Command [-InputObject <PSObject>] [-Expression] <ScriptBlock> [<CommonParameters>]
```

## <span data-ttu-id="d6692-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d6692-107">DESCRIPTION</span></span>

<span data-ttu-id="d6692-108">`Measure-Command`Командлет выполняет блок скрипта или командлет внутренне, время выполнения операции и возвращает время выполнения.</span><span class="sxs-lookup"><span data-stu-id="d6692-108">The `Measure-Command` cmdlet runs a script block or cmdlet internally, times the execution of the operation, and returns the execution time.</span></span>

> [!NOTE]
> <span data-ttu-id="d6692-109">Блоки скриптов, выполняемые, `Measure-Command` выполняются в текущей области, а не в дочерней области.</span><span class="sxs-lookup"><span data-stu-id="d6692-109">Script blocks run by `Measure-Command` run in the current scope, not a child scope.</span></span>

## <span data-ttu-id="d6692-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="d6692-110">EXAMPLES</span></span>

### <span data-ttu-id="d6692-111">Пример 1. Измерение команды</span><span class="sxs-lookup"><span data-stu-id="d6692-111">Example 1: Measure a command</span></span>

<span data-ttu-id="d6692-112">В этом примере измеряется время, затрачиваемое на выполнение `Get-EventLog` команды, получающей события в журнале событий Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d6692-112">This example measures the time it takes to run a `Get-EventLog` command that gets the events in the Windows PowerShell event log.</span></span>

```powershell
Measure-Command { Get-EventLog "windows powershell" }
```

### <span data-ttu-id="d6692-113">Пример 2. Сравнение двух выходных данных из Measure-Command</span><span class="sxs-lookup"><span data-stu-id="d6692-113">Example 2: Compare two outputs from Measure-Command</span></span>

<span data-ttu-id="d6692-114">Первая команда измеряет время, затрачиваемое на обработку рекурсивной `Get-ChildItem` команды, которая использует параметр **path** для получения только `.txt` файлов в `C:\Windows` каталоге и его подкаталогах.</span><span class="sxs-lookup"><span data-stu-id="d6692-114">The first command measures the time it takes to process a recursive `Get-ChildItem` command that uses the **Path** parameter to get only `.txt` files in the `C:\Windows` directory and its subdirectories.</span></span>

<span data-ttu-id="d6692-115">Вторая команда измеряет время, затрачиваемое на обработку рекурсивной `Get-ChildItem` команды, использующей параметр, зависящий от поставщика.</span><span class="sxs-lookup"><span data-stu-id="d6692-115">The second command measures the time it takes to process a recursive `Get-ChildItem` command that uses the provider-specific \` parameter.</span></span>

<span data-ttu-id="d6692-116">Эти команды показывают значение с помощью фильтра, зависящего от поставщика, в командах PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d6692-116">These commands show the value of using a provider-specific filter in PowerShell commands.</span></span>

```powershell
Measure-Command { Get-ChildItem -Path C:\Windows\*.txt -Recurse }
```

```Output
Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 8
Milliseconds      : 618
Ticks             : 86182763
TotalDays         : 9.9748568287037E-05
TotalHours        : 0.00239396563888889
TotalMinutes      : 0.143637938333333
TotalSeconds      : 8.6182763
TotalMilliseconds : 8618.2763
```

```powershell
Measure-Command {Get-ChildItem C:\Windows -Filter "*.txt" -Recurse}
```

```Output
Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 1
Milliseconds      : 140
Ticks             : 11409189
TotalDays         : 1.32050798611111E-05
TotalHours        : 0.000316921916666667
TotalMinutes      : 0.019015315
TotalSeconds      : 1.1409189
TotalMilliseconds : 1140.9189
```

### <span data-ttu-id="d6692-117">Пример 3. входные данные конвейера в Measure-Command</span><span class="sxs-lookup"><span data-stu-id="d6692-117">Example 3: Piping input to Measure-Command</span></span>

<span data-ttu-id="d6692-118">Объекты, `Measure-Command` передаваемые в, доступны блоку скрипта, который передается в параметр **Expression** .</span><span class="sxs-lookup"><span data-stu-id="d6692-118">Objects that are piped to `Measure-Command` are available to the script block that is passed to the **Expression** parameter.</span></span> <span data-ttu-id="d6692-119">Блок скрипта выполняется один раз для каждого объекта в конвейере.</span><span class="sxs-lookup"><span data-stu-id="d6692-119">The script block is executed once for each object on the pipeline.</span></span>

```powershell
# Perform a simple operation to demonstrate the InputObject parameter
# Note that no output is displayed.
10, 20, 50 | Measure-Command -Expression { for ($i=0; $i -lt $_; $i++) {$i} }
```

```Output
Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 0
Milliseconds      : 12
Ticks             : 122672
TotalDays         : 1.41981481481481E-07
TotalHours        : 3.40755555555556E-06
TotalMinutes      : 0.000204453333333333
TotalSeconds      : 0.0122672
TotalMilliseconds : 12.2672
```

### <span data-ttu-id="d6692-120">Пример 4. Отображение выходных данных команды отсчитывая</span><span class="sxs-lookup"><span data-stu-id="d6692-120">Example 4: Displaying output of measured command</span></span>

<span data-ttu-id="d6692-121">Чтобы отобразить выходные данные выражения в `Measure-Command` , можно использовать канал в `Out-Default` .</span><span class="sxs-lookup"><span data-stu-id="d6692-121">To display output of expression in `Measure-Command` you can use a pipe to `Out-Default`.</span></span>

```powershell
# Perform the same operation as above adding Out-Default to every execution.
# This will show that the ScriptBlock is in fact executing for every item.
10, 20, 50 | Measure-Command -Expression {for ($i=0; $i -lt $_; $i++) {$i}; "$($_)" | Out-Default }
```

```Output
10
20
50


Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 0
Milliseconds      : 11
Ticks             : 113745
TotalDays         : 1.31649305555556E-07
TotalHours        : 3.15958333333333E-06
TotalMinutes      : 0.000189575
TotalSeconds      : 0.0113745
TotalMilliseconds : 11.3745
```

### <span data-ttu-id="d6692-122">Пример 5. измерение выполнения в дочерней области</span><span class="sxs-lookup"><span data-stu-id="d6692-122">Example 5: Measuring execution in a child scope</span></span>

<span data-ttu-id="d6692-123">`Measure-Command` выполняет блок скрипта в текущей области, поэтому блок скрипта может изменять значения в текущей области.</span><span class="sxs-lookup"><span data-stu-id="d6692-123">`Measure-Command` runs the script block in the current scope, so the script block can modify values in the current scope.</span></span> <span data-ttu-id="d6692-124">Чтобы избежать изменений в текущей области, необходимо заключить блок скрипта в фигурные скобки ( `{}` ) и использовать оператор вызова ( `&` ) для выполнения блока в дочерней области.</span><span class="sxs-lookup"><span data-stu-id="d6692-124">To avoid changes to the current scope, you must wrap the script block in braces (`{}`) and use the invocation operator (`&`) to execute the block in a child scope.</span></span>

```powershell
$foo = 'Value 1'
$null = Measure-Command { $foo = 'Value 2' }
$foo
$null = Measure-Command { & { $foo = 'Value 3' } }
$foo
```

```Output
Value 2
Value 2
```

<span data-ttu-id="d6692-125">Дополнительные сведения об операторе вызова см. в разделе [about_Operators](../Microsoft.PowerShell.Core/About/about_Operators.md#call-operator-).</span><span class="sxs-lookup"><span data-stu-id="d6692-125">For more information about the invocation operator, see [about_Operators](../Microsoft.PowerShell.Core/About/about_Operators.md#call-operator-).</span></span>

## <span data-ttu-id="d6692-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d6692-126">PARAMETERS</span></span>

### <span data-ttu-id="d6692-127">-Expression</span><span class="sxs-lookup"><span data-stu-id="d6692-127">-Expression</span></span>

<span data-ttu-id="d6692-128">Определяет выражение, время выполнения которого нужно определить.</span><span class="sxs-lookup"><span data-stu-id="d6692-128">Specifies the expression that is being timed.</span></span> <span data-ttu-id="d6692-129">Заключите выражение в фигурные скобки ( `{}` ).</span><span class="sxs-lookup"><span data-stu-id="d6692-129">Enclose the expression in braces (`{}`).</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d6692-130">-InputObject</span><span class="sxs-lookup"><span data-stu-id="d6692-130">-InputObject</span></span>

<span data-ttu-id="d6692-131">Объекты, привязанные к параметру **InputObject** , являются необязательными входными данными для блока скрипта, передаваемого в параметр **Expression** .</span><span class="sxs-lookup"><span data-stu-id="d6692-131">Objects bound to the **InputObject** parameter are optional input for the script block passed to the **Expression** parameter.</span></span> <span data-ttu-id="d6692-132">Внутри блока script `$_` можно использовать для ссылки на текущий объект в конвейере.</span><span class="sxs-lookup"><span data-stu-id="d6692-132">Inside the script block, `$_` can be used to reference the current object in the pipeline.</span></span>

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

### <span data-ttu-id="d6692-133">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="d6692-133">CommonParameters</span></span>

<span data-ttu-id="d6692-134">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d6692-134">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d6692-135">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d6692-135">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d6692-136">Входные данные</span><span class="sxs-lookup"><span data-stu-id="d6692-136">INPUTS</span></span>

### <span data-ttu-id="d6692-137">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="d6692-137">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="d6692-138">Объект можно передать в `Measure-Command` .</span><span class="sxs-lookup"><span data-stu-id="d6692-138">You can pipe an object to `Measure-Command`.</span></span>

## <span data-ttu-id="d6692-139">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="d6692-139">OUTPUTS</span></span>

### <span data-ttu-id="d6692-140">System.TimeSpan</span><span class="sxs-lookup"><span data-stu-id="d6692-140">System.TimeSpan</span></span>

<span data-ttu-id="d6692-141">`Measure-Command` Возвращает объект интервала времени, представляющий результат.</span><span class="sxs-lookup"><span data-stu-id="d6692-141">`Measure-Command` returns a time span object that represents the result.</span></span>

## <span data-ttu-id="d6692-142">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="d6692-142">NOTES</span></span>

## <span data-ttu-id="d6692-143">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="d6692-143">RELATED LINKS</span></span>

[<span data-ttu-id="d6692-144">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="d6692-144">Invoke-Command</span></span>](../Microsoft.PowerShell.Core/Invoke-Command.md)

[<span data-ttu-id="d6692-145">Trace-Command</span><span class="sxs-lookup"><span data-stu-id="d6692-145">Trace-Command</span></span>](Trace-Command.md)
