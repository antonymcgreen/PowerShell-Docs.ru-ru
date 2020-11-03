---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,командлет
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Where-Object
ms.openlocfilehash: 0d9101c751e9ebc0b0c6fe80564bb76524de8bb6
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2020
ms.locfileid: "93225578"
---
# <span data-ttu-id="598fc-103">Where-Object</span><span class="sxs-lookup"><span data-stu-id="598fc-103">Where-Object</span></span>

## <span data-ttu-id="598fc-104">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="598fc-104">SYNOPSIS</span></span>
<span data-ttu-id="598fc-105">Выбирает объекты из коллекции на основании значения их свойств.</span><span class="sxs-lookup"><span data-stu-id="598fc-105">Selects objects from a collection based on their property values.</span></span>

## <span data-ttu-id="598fc-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="598fc-106">SYNTAX</span></span>

### <span data-ttu-id="598fc-107">Equals (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="598fc-107">EqualSet (Default)</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] [-EQ]
 [<CommonParameters>]
```

### <span data-ttu-id="598fc-108">скриптблокксет</span><span class="sxs-lookup"><span data-stu-id="598fc-108">ScriptBlockSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-FilterScript] <ScriptBlock> [<CommonParameters>]
```

### <span data-ttu-id="598fc-109">Match</span><span class="sxs-lookup"><span data-stu-id="598fc-109">MatchSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -Match
 [<CommonParameters>]
```

### <span data-ttu-id="598fc-110">касесенситивикуалсет</span><span class="sxs-lookup"><span data-stu-id="598fc-110">CaseSensitiveEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CEQ
 [<CommonParameters>]
```

### <span data-ttu-id="598fc-111">нотекуалсет</span><span class="sxs-lookup"><span data-stu-id="598fc-111">NotEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NE
 [<CommonParameters>]
```

### <span data-ttu-id="598fc-112">касесенситивенотекуалсет</span><span class="sxs-lookup"><span data-stu-id="598fc-112">CaseSensitiveNotEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNE
 [<CommonParameters>]
```

### <span data-ttu-id="598fc-113">греатерсансет</span><span class="sxs-lookup"><span data-stu-id="598fc-113">GreaterThanSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -GT
 [<CommonParameters>]
```

### <span data-ttu-id="598fc-114">касесенситивегреатерсансет</span><span class="sxs-lookup"><span data-stu-id="598fc-114">CaseSensitiveGreaterThanSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CGT
 [<CommonParameters>]
```

### <span data-ttu-id="598fc-115">лесссансет</span><span class="sxs-lookup"><span data-stu-id="598fc-115">LessThanSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -LT
 [<CommonParameters>]
```

### <span data-ttu-id="598fc-116">касесенситивелесссансет</span><span class="sxs-lookup"><span data-stu-id="598fc-116">CaseSensitiveLessThanSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CLT
 [<CommonParameters>]
```

### <span data-ttu-id="598fc-117">греатерорекуалсет</span><span class="sxs-lookup"><span data-stu-id="598fc-117">GreaterOrEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -GE
 [<CommonParameters>]
```

### <span data-ttu-id="598fc-118">касесенситивегреатерорекуалсет</span><span class="sxs-lookup"><span data-stu-id="598fc-118">CaseSensitiveGreaterOrEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CGE
 [<CommonParameters>]
```

### <span data-ttu-id="598fc-119">лессорекуалсет</span><span class="sxs-lookup"><span data-stu-id="598fc-119">LessOrEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -LE
 [<CommonParameters>]
```

### <span data-ttu-id="598fc-120">касесенситивелессорекуалсет</span><span class="sxs-lookup"><span data-stu-id="598fc-120">CaseSensitiveLessOrEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CLE
 [<CommonParameters>]
```

### <span data-ttu-id="598fc-121">Аналогичный</span><span class="sxs-lookup"><span data-stu-id="598fc-121">LikeSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -Like
 [<CommonParameters>]
```

### <span data-ttu-id="598fc-122">касесенситивеликесет</span><span class="sxs-lookup"><span data-stu-id="598fc-122">CaseSensitiveLikeSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CLike
 [<CommonParameters>]
```

### <span data-ttu-id="598fc-123">нотликесет</span><span class="sxs-lookup"><span data-stu-id="598fc-123">NotLikeSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NotLike
 [<CommonParameters>]
```

### <span data-ttu-id="598fc-124">касесенситивенотликесет</span><span class="sxs-lookup"><span data-stu-id="598fc-124">CaseSensitiveNotLikeSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNotLike
 [<CommonParameters>]
```

### <span data-ttu-id="598fc-125">касесенситивематчсет</span><span class="sxs-lookup"><span data-stu-id="598fc-125">CaseSensitiveMatchSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CMatch
 [<CommonParameters>]
```

### <span data-ttu-id="598fc-126">нотматчсет</span><span class="sxs-lookup"><span data-stu-id="598fc-126">NotMatchSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NotMatch
 [<CommonParameters>]
```

### <span data-ttu-id="598fc-127">касесенситивенотматчсет</span><span class="sxs-lookup"><span data-stu-id="598fc-127">CaseSensitiveNotMatchSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNotMatch
 [<CommonParameters>]
```

### <span data-ttu-id="598fc-128">Contains</span><span class="sxs-lookup"><span data-stu-id="598fc-128">ContainsSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -Contains
 [<CommonParameters>]
```

### <span data-ttu-id="598fc-129">касесенситивеконтаинссет</span><span class="sxs-lookup"><span data-stu-id="598fc-129">CaseSensitiveContainsSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CContains
 [<CommonParameters>]
```

### <span data-ttu-id="598fc-130">нотконтаинссет</span><span class="sxs-lookup"><span data-stu-id="598fc-130">NotContainsSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NotContains
 [<CommonParameters>]
```

### <span data-ttu-id="598fc-131">касесенситивенотконтаинссет</span><span class="sxs-lookup"><span data-stu-id="598fc-131">CaseSensitiveNotContainsSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNotContains
 [<CommonParameters>]
```

### <span data-ttu-id="598fc-132">Вставка</span><span class="sxs-lookup"><span data-stu-id="598fc-132">InSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -In
 [<CommonParameters>]
```

### <span data-ttu-id="598fc-133">касесенситивеинсет</span><span class="sxs-lookup"><span data-stu-id="598fc-133">CaseSensitiveInSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CIn
 [<CommonParameters>]
```

### <span data-ttu-id="598fc-134">нотинсет</span><span class="sxs-lookup"><span data-stu-id="598fc-134">NotInSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NotIn
 [<CommonParameters>]
```

### <span data-ttu-id="598fc-135">касесенситивенотинсет</span><span class="sxs-lookup"><span data-stu-id="598fc-135">CaseSensitiveNotInSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNotIn
 [<CommonParameters>]
```

### <span data-ttu-id="598fc-136">иссет</span><span class="sxs-lookup"><span data-stu-id="598fc-136">IsSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -Is
 [<CommonParameters>]
```

### <span data-ttu-id="598fc-137">иснотсет</span><span class="sxs-lookup"><span data-stu-id="598fc-137">IsNotSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -IsNot
 [<CommonParameters>]
```

### <span data-ttu-id="598fc-138">Not</span><span class="sxs-lookup"><span data-stu-id="598fc-138">Not</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> -Not [<CommonParameters>]
```

## <span data-ttu-id="598fc-139">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="598fc-139">DESCRIPTION</span></span>

<span data-ttu-id="598fc-140">`Where-Object`Командлет выбирает объекты, имеющие определенные значения свойств, из коллекции объектов, которые передаются в него.</span><span class="sxs-lookup"><span data-stu-id="598fc-140">The `Where-Object` cmdlet selects objects that have particular property values from the collection of objects that are passed to it.</span></span> <span data-ttu-id="598fc-141">Например, командлет можно использовать `Where-Object` для выбора файлов, созданных после определенной даты, событий с определенным идентификатором, или компьютеров, использующих определенную версию Windows.</span><span class="sxs-lookup"><span data-stu-id="598fc-141">For example, you can use the `Where-Object` cmdlet to select files that were created after a certain date, events with a particular ID, or computers that use a particular version of Windows.</span></span>

<span data-ttu-id="598fc-142">Начиная с Windows PowerShell 3,0 существует два разных способа создания `Where-Object` команды.</span><span class="sxs-lookup"><span data-stu-id="598fc-142">Starting in Windows PowerShell 3.0, there are two different ways to construct a `Where-Object` command.</span></span>

- <span data-ttu-id="598fc-143">**Блок скрипта**.</span><span class="sxs-lookup"><span data-stu-id="598fc-143">**Script block**.</span></span> <span data-ttu-id="598fc-144">Для указания имени свойства, оператора сравнения и значения свойства можно использовать блок сценария.</span><span class="sxs-lookup"><span data-stu-id="598fc-144">You can use a script block to specify the property name, a comparison operator, and a property value.</span></span> <span data-ttu-id="598fc-145">`Where-Object` Возвращает все объекты, для которых инструкция блока скрипта имеет значение true.</span><span class="sxs-lookup"><span data-stu-id="598fc-145">`Where-Object` returns all objects for which the script block statement is true.</span></span>

  <span data-ttu-id="598fc-146">Например, следующая команда получает процессы в классе с нормальным приоритетом, то есть обрабатывает, где значение свойства **PriorityClass значение** равно "Обычная".</span><span class="sxs-lookup"><span data-stu-id="598fc-146">For example, the following command gets processes in the Normal priority class, that is, processes where the value of the **PriorityClass** property equals Normal.</span></span>

  `Get-Process | Where-Object {$_.PriorityClass -eq "Normal"}`

  <span data-ttu-id="598fc-147">Все операторы сравнения PowerShell допустимы в формате блока сценария.</span><span class="sxs-lookup"><span data-stu-id="598fc-147">All PowerShell comparison operators are valid in the script block format.</span></span> <span data-ttu-id="598fc-148">Дополнительные сведения об операторах сравнения см. в разделе [about_Comparison_Operators](./About/about_Comparison_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="598fc-148">For more information about comparison operators, see [about_Comparison_Operators](./About/about_Comparison_Operators.md).</span></span>

- <span data-ttu-id="598fc-149">**Оператор сравнения**.</span><span class="sxs-lookup"><span data-stu-id="598fc-149">**Comparison statement**.</span></span> <span data-ttu-id="598fc-150">Можно также написать оператор сравнения, который больше похож на естественный язык.</span><span class="sxs-lookup"><span data-stu-id="598fc-150">You can also write a comparison statement, which is much more like natural language.</span></span> <span data-ttu-id="598fc-151">Операторы сравнения были представлены в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="598fc-151">Comparison statements were introduced in Windows PowerShell 3.0.</span></span>

  <span data-ttu-id="598fc-152">Например, следующие команды также получают процессы, имеющие класс приоритета "Обычная".</span><span class="sxs-lookup"><span data-stu-id="598fc-152">For example, the following commands also get processes that have a priority class of Normal.</span></span> <span data-ttu-id="598fc-153">Эти команды эквивалентны и взаимозаменяемы.</span><span class="sxs-lookup"><span data-stu-id="598fc-153">These commands are equivalent and can be used interchangeably.</span></span>

  `Get-Process | Where-Object -Property PriorityClass -eq -Value "Normal"`

  `Get-Process | Where-Object PriorityClass -eq "Normal"`

  <span data-ttu-id="598fc-154">Начиная с Windows PowerShell 3,0, `Where-Object` в команде добавляются операторы сравнения в качестве параметров `Where-Object` .</span><span class="sxs-lookup"><span data-stu-id="598fc-154">Starting in Windows PowerShell 3.0, `Where-Object` adds comparison operators as parameters in a `Where-Object` command.</span></span> <span data-ttu-id="598fc-155">Если не указано иначе, все операторы вводятся без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="598fc-155">Unless specified, all operators are case-insensitive.</span></span> <span data-ttu-id="598fc-156">До Windows PowerShell 3,0 операторы сравнения в языке PowerShell можно использовать только в блоках сценариев.</span><span class="sxs-lookup"><span data-stu-id="598fc-156">Prior to Windows PowerShell 3.0, the comparison operators in the PowerShell language could be used only in script blocks.</span></span>

<span data-ttu-id="598fc-157">При предоставлении одного **Свойства** в `Where-Object` значение свойства обрабатывается как логическое выражение.</span><span class="sxs-lookup"><span data-stu-id="598fc-157">When you provide a single **Property** to `Where-Object`, the value of the property is treated as a boolean expression.</span></span> <span data-ttu-id="598fc-158">Если значение **length** не равно нулю, выражение принимает **значение true**.</span><span class="sxs-lookup"><span data-stu-id="598fc-158">When the value of **Length** is not zero, the expression evaluates to **True**.</span></span> <span data-ttu-id="598fc-159">Пример: `('hi', '', 'there') | Where-Object Length`</span><span class="sxs-lookup"><span data-stu-id="598fc-159">For example: `('hi', '', 'there') | Where-Object Length`</span></span>

<span data-ttu-id="598fc-160">Предыдущий пример функционально эквивалентен:</span><span class="sxs-lookup"><span data-stu-id="598fc-160">The previous example is functionally equivalent to:</span></span>

- `('hi', '', 'there') | Where-Object Length -GT 0`
- `('hi', '', 'there') | Where-Object {$_.Length -gt 0}`

## <span data-ttu-id="598fc-161">Примеры</span><span class="sxs-lookup"><span data-stu-id="598fc-161">EXAMPLES</span></span>

### <span data-ttu-id="598fc-162">Пример 1. получение остановленных служб</span><span class="sxs-lookup"><span data-stu-id="598fc-162">Example 1: Get stopped services</span></span>

<span data-ttu-id="598fc-163">Эти команды получают список всех служб, остановленных в данный момент.</span><span class="sxs-lookup"><span data-stu-id="598fc-163">These commands get a list of all services that are currently stopped.</span></span> <span data-ttu-id="598fc-164">`$_`Автоматическая переменная представляет каждый объект, передаваемый в `Where-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="598fc-164">The `$_` automatic variable represents each object that is passed to the `Where-Object` cmdlet.</span></span>

<span data-ttu-id="598fc-165">Первая команда использует формат блока сценария, вторая команда использует формат инструкции сравнения.</span><span class="sxs-lookup"><span data-stu-id="598fc-165">The first command uses the script block format, the second command uses the comparison statement format.</span></span> <span data-ttu-id="598fc-166">Команды эквивалентны и взаимозаменяемы.</span><span class="sxs-lookup"><span data-stu-id="598fc-166">The commands are equivalent and can be used interchangeably.</span></span>

```powershell
Get-Service | Where-Object {$_.Status -eq "Stopped"}
Get-Service | where Status -eq "Stopped"
```

### <span data-ttu-id="598fc-167">Пример 2. получение процессов на основе рабочего набора</span><span class="sxs-lookup"><span data-stu-id="598fc-167">Example 2: Get processes based on working set</span></span>

<span data-ttu-id="598fc-168">Эти команды содержат список процессов, имеющих рабочий набор, превышающий 250 мегабайт (КБ).</span><span class="sxs-lookup"><span data-stu-id="598fc-168">These commands list processes that have a working set greater than 250 megabytes (KB).</span></span> <span data-ttu-id="598fc-169">Синтаксис ScriptBlock и инструкции эквивалентен и может использоваться взаимозаменяемым.</span><span class="sxs-lookup"><span data-stu-id="598fc-169">The scriptblock and statement syntax are equivalent and can be used interchangeably.</span></span>

```powershell
Get-Process | Where-Object {$_.WorkingSet -GT 250MB}
Get-Process | Where-Object WorkingSet -GT (250MB)
```

### <span data-ttu-id="598fc-170">Пример 3. получение процессов на основе имени процесса</span><span class="sxs-lookup"><span data-stu-id="598fc-170">Example 3: Get processes based on process name</span></span>

<span data-ttu-id="598fc-171">Эти команды получают процессы со значением свойства **processName** , которое начинается с буквы `p` .</span><span class="sxs-lookup"><span data-stu-id="598fc-171">These commands get the processes that have a **ProcessName** property value that begins with the letter `p`.</span></span> <span data-ttu-id="598fc-172">Оператор **Match** позволяет использовать совпадения регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="598fc-172">The **Match** operator lets you use regular expression matches.</span></span>

<span data-ttu-id="598fc-173">Синтаксис ScriptBlock и инструкции эквивалентен и может использоваться взаимозаменяемым.</span><span class="sxs-lookup"><span data-stu-id="598fc-173">The scriptblock and statement syntax are equivalent and can be used interchangeably.</span></span>

```powershell
Get-Process | Where-Object {$_.ProcessName -Match "^p.*"}
Get-Process | Where-Object ProcessName -Match "^p.*"
```

### <span data-ttu-id="598fc-174">Пример 4. Использование формата инструкции сравнения</span><span class="sxs-lookup"><span data-stu-id="598fc-174">Example 4: Use the comparison statement format</span></span>

<span data-ttu-id="598fc-175">В этом примере показано, как использовать новый формат инструкции сравнения `Where-Object` командлета.</span><span class="sxs-lookup"><span data-stu-id="598fc-175">This example shows how to use the new comparison statement format of the `Where-Object` cmdlet.</span></span>

<span data-ttu-id="598fc-176">Вторая команда использует формат оператора сравнения.</span><span class="sxs-lookup"><span data-stu-id="598fc-176">The first command uses the comparison statement format.</span></span>
<span data-ttu-id="598fc-177">В этой команде не используются псевдонимы, и все параметры включают имя параметра.</span><span class="sxs-lookup"><span data-stu-id="598fc-177">In this command, no aliases are used and all parameters include the parameter name.</span></span>

<span data-ttu-id="598fc-178">Вторая команда является более естественным способом использованием формата команды сравнения.</span><span class="sxs-lookup"><span data-stu-id="598fc-178">The second command is the more natural use of the comparison command format.</span></span> <span data-ttu-id="598fc-179">`where`Псевдоним заменяется `Where-Object` именем командлета, а все необязательные имена параметров опускаются.</span><span class="sxs-lookup"><span data-stu-id="598fc-179">The `where` alias is substituted for the `Where-Object` cmdlet name and all optional parameter names are omitted.</span></span>

```powershell
Get-Process | Where-Object -Property Handles -GE -Value 1000
Get-Process | where Handles -GE 1000
```

### <span data-ttu-id="598fc-180">Пример 5. получение команд на основе свойств</span><span class="sxs-lookup"><span data-stu-id="598fc-180">Example 5: Get commands based on properties</span></span>

<span data-ttu-id="598fc-181">В этом примере показано, как написать команды, которые возвращают элементы, имеющие значения true или false или любые значения для указанного свойства.</span><span class="sxs-lookup"><span data-stu-id="598fc-181">This example shows how to write commands that return items that are true or false or have any value for a specified property.</span></span> <span data-ttu-id="598fc-182">В каждом примере показаны форматы блока скрипта и инструкции сравнения для команды.</span><span class="sxs-lookup"><span data-stu-id="598fc-182">Each example shows both the script block and comparison statement formats for the command.</span></span>

```powershell
# Use Where-Object to get commands that have any value for the OutputType property of the command.
# This omits commands that do not have an OutputType property and those that have an OutputType property, but no property value.
Get-Command | where OutputType
Get-Command | where {$_.OutputType}
```

```powershell
# Use Where-Object to get objects that are containers.
# This gets objects that have the **PSIsContainer** property with a value of $True and excludes all others.
Get-ChildItem | where PSIsContainer
Get-ChildItem | where {$_.PSIsContainer}
```

```powershell
# Finally, use the Not operator (!) to get objects that are not containers.
# This gets objects that do have the **PSIsContainer** property and those that have a value of $False for the **PSIsContainer** property.
Get-ChildItem | where {!$_.PSIsContainer}
# You cannot use the Not operator (!) in the comparison statement format of the command.
Get-ChildItem | where PSIsContainer -eq $False
```

### <span data-ttu-id="598fc-183">Пример 6. Использование нескольких условий</span><span class="sxs-lookup"><span data-stu-id="598fc-183">Example 6: Use multiple conditions</span></span>

```powershell
Get-Module -ListAvailable | where {($_.Name -notlike "Microsoft*" -and $_.Name -notlike "PS*") -and $_.HelpInfoUri}
```

<span data-ttu-id="598fc-184">В этом примере показано, как создать `Where-Object` команду с несколькими условиями.</span><span class="sxs-lookup"><span data-stu-id="598fc-184">This example shows how to create a `Where-Object` command with multiple conditions.</span></span>

<span data-ttu-id="598fc-185">Эта команда получает вспомогательные модули, которые поддерживают функцию обновляемой справки.</span><span class="sxs-lookup"><span data-stu-id="598fc-185">This command gets non-core modules that support the Updatable Help feature.</span></span> <span data-ttu-id="598fc-186">Команда использует параметр **ListAvailable** `Get-Module` командлета для получения всех модулей на компьютере.</span><span class="sxs-lookup"><span data-stu-id="598fc-186">The command uses the **ListAvailable** parameter of the `Get-Module` cmdlet to get all modules on the computer.</span></span> <span data-ttu-id="598fc-187">Оператор конвейера ( `|` ) отправляет модули в `Where-Object` командлет, который получает модули, имена которых не начинаются с Microsoft или PS, и имеют значение для свойства **HelpInfoURI** , которое сообщает PowerShell, где найти обновленные файлы справки для модуля.</span><span class="sxs-lookup"><span data-stu-id="598fc-187">A pipeline operator (`|`) sends the modules to the `Where-Object` cmdlet, which gets modules whose names do not begin with Microsoft or PS, and have a value for the **HelpInfoURI** property, which tells PowerShell where to find updated help files for the module.</span></span> <span data-ttu-id="598fc-188">Операторы сравнения соединены логическим оператором **и** .</span><span class="sxs-lookup"><span data-stu-id="598fc-188">The comparison statements are connected by the **And** logical operator.</span></span>

<span data-ttu-id="598fc-189">В примере используется формат команды блока сценария.</span><span class="sxs-lookup"><span data-stu-id="598fc-189">The example uses the script block command format.</span></span> <span data-ttu-id="598fc-190">Логические операторы, такие как **и** и **или** , допустимы только в блоках скриптов.</span><span class="sxs-lookup"><span data-stu-id="598fc-190">Logical operators, such as **And** and **Or** , are valid only in script blocks.</span></span> <span data-ttu-id="598fc-191">Их нельзя использовать в формате инструкции сравнения `Where-Object` команды.</span><span class="sxs-lookup"><span data-stu-id="598fc-191">You cannot use them in the comparison statement format of a `Where-Object` command.</span></span>

- <span data-ttu-id="598fc-192">Дополнительные сведения о логических операторах PowerShell см. в разделе [about_Logical_Operators](./About/about_logical_operators.md).</span><span class="sxs-lookup"><span data-stu-id="598fc-192">For more information about PowerShell logical operators, see [about_Logical_Operators](./About/about_logical_operators.md).</span></span>
- <span data-ttu-id="598fc-193">Дополнительные сведения о функции обновляемой справки см. в разделе [about_Updatable_Help](./About/about_Updatable_Help.md).</span><span class="sxs-lookup"><span data-stu-id="598fc-193">For more information about the Updatable Help feature, see [about_Updatable_Help](./About/about_Updatable_Help.md).</span></span>

## <span data-ttu-id="598fc-194">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="598fc-194">PARAMETERS</span></span>

### <span data-ttu-id="598fc-195">-Кконтаинс</span><span class="sxs-lookup"><span data-stu-id="598fc-195">-CContains</span></span>

<span data-ttu-id="598fc-196">Указывает, что этот командлет получает объекты из коллекции, если значение свойства объекта является точным соответствием для указанного значения.</span><span class="sxs-lookup"><span data-stu-id="598fc-196">Indicates that this cmdlet gets objects from a collection if the property value of the object is an exact match for the specified value.</span></span> <span data-ttu-id="598fc-197">В этой операции учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="598fc-197">This operation is case-sensitive.</span></span>

<span data-ttu-id="598fc-198">Пример: `Get-Process | where ProcessName -CContains "svchost"`</span><span class="sxs-lookup"><span data-stu-id="598fc-198">For example: `Get-Process | where ProcessName -CContains "svchost"`</span></span>

<span data-ttu-id="598fc-199">**Кконтаинс** ссылается на коллекцию значений и имеет значение true, если коллекция содержит элемент, который является точным соответствием для указанного значения.</span><span class="sxs-lookup"><span data-stu-id="598fc-199">**CContains** refers to a collection of values and is true if the collection contains an item that is an exact match for the specified value.</span></span> <span data-ttu-id="598fc-200">Если входные данные являются одним объектом, PowerShell преобразует его в коллекцию одного объекта.</span><span class="sxs-lookup"><span data-stu-id="598fc-200">If the input is a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="598fc-201">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="598fc-201">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveContainsSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="598fc-202">-ЦЕК</span><span class="sxs-lookup"><span data-stu-id="598fc-202">-CEQ</span></span>

<span data-ttu-id="598fc-203">Указывает, что этот командлет получает объекты, если значение свойства совпадает с указанным значением.</span><span class="sxs-lookup"><span data-stu-id="598fc-203">Indicates that this cmdlet gets objects if the property value is the same as the specified value.</span></span>
<span data-ttu-id="598fc-204">В этой операции учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="598fc-204">This operation is case-sensitive.</span></span>

<span data-ttu-id="598fc-205">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="598fc-205">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveEqualSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="598fc-206">-CGE</span><span class="sxs-lookup"><span data-stu-id="598fc-206">-CGE</span></span>

<span data-ttu-id="598fc-207">Указывает, что этот командлет получает объекты, если значение свойства больше или равно указанному значению.</span><span class="sxs-lookup"><span data-stu-id="598fc-207">Indicates that this cmdlet gets objects if the property value is greater than or equal to the specified value.</span></span> <span data-ttu-id="598fc-208">В этой операции учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="598fc-208">This operation is case-sensitive.</span></span>

<span data-ttu-id="598fc-209">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="598fc-209">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveGreaterOrEqualSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="598fc-210">-КГТ</span><span class="sxs-lookup"><span data-stu-id="598fc-210">-CGT</span></span>

<span data-ttu-id="598fc-211">Указывает, что этот командлет получает объекты, если значение свойства больше указанного значения.</span><span class="sxs-lookup"><span data-stu-id="598fc-211">Indicates that this cmdlet gets objects if the property value is greater than the specified value.</span></span>
<span data-ttu-id="598fc-212">В этой операции учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="598fc-212">This operation is case-sensitive.</span></span>

<span data-ttu-id="598fc-213">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="598fc-213">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveGreaterThanSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="598fc-214">-CIn</span><span class="sxs-lookup"><span data-stu-id="598fc-214">-CIn</span></span>

<span data-ttu-id="598fc-215">Указывает, что этот командлет получает объекты, если значение свойства включает указанное значение.</span><span class="sxs-lookup"><span data-stu-id="598fc-215">Indicates that this cmdlet gets objects if the property value includes the specified value.</span></span> <span data-ttu-id="598fc-216">В этой операции учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="598fc-216">This operation is case-sensitive.</span></span>

<span data-ttu-id="598fc-217">Пример: `Get-Process | where -Value "svchost" -CIn ProcessName`</span><span class="sxs-lookup"><span data-stu-id="598fc-217">For example: `Get-Process | where -Value "svchost" -CIn ProcessName`</span></span>

<span data-ttu-id="598fc-218">**CIn** напоминает **кконтаинс** , за исключением того, что позиции свойства и значения реверсируются.</span><span class="sxs-lookup"><span data-stu-id="598fc-218">**CIn** resembles **CContains** , except that the property and value positions are reversed.</span></span> <span data-ttu-id="598fc-219">Например обе следующие инструкции верны.</span><span class="sxs-lookup"><span data-stu-id="598fc-219">For example, the following statements are both true.</span></span>

`"abc", "def" -CContains "abc"`

`"abc" -CIn "abc", "def"`

<span data-ttu-id="598fc-220">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="598fc-220">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveInSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="598fc-221">-CLE</span><span class="sxs-lookup"><span data-stu-id="598fc-221">-CLE</span></span>

<span data-ttu-id="598fc-222">Указывает, что этот командлет получает объекты, если значение свойства меньше или равно указанному значению.</span><span class="sxs-lookup"><span data-stu-id="598fc-222">Indicates that this cmdlet gets objects if the property value is less-than or equal to the specified value.</span></span> <span data-ttu-id="598fc-223">В этой операции учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="598fc-223">This operation is case-sensitive.</span></span>

<span data-ttu-id="598fc-224">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="598fc-224">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveLessOrEqualSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="598fc-225">-Клике</span><span class="sxs-lookup"><span data-stu-id="598fc-225">-CLike</span></span>

<span data-ttu-id="598fc-226">Указывает, что этот командлет получает объекты, если значение свойства соответствует значению, включающему символы-шаблоны.</span><span class="sxs-lookup"><span data-stu-id="598fc-226">Indicates that this cmdlet gets objects if the property value matches a value that includes wildcard characters.</span></span> <span data-ttu-id="598fc-227">В этой операции учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="598fc-227">This operation is case-sensitive.</span></span>

<span data-ttu-id="598fc-228">Пример: `Get-Process | where ProcessName -CLike "*host"`</span><span class="sxs-lookup"><span data-stu-id="598fc-228">For example: `Get-Process | where ProcessName -CLike "*host"`</span></span>

<span data-ttu-id="598fc-229">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="598fc-229">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveLikeSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="598fc-230">— Средство регистрации звонков</span><span class="sxs-lookup"><span data-stu-id="598fc-230">-CLT</span></span>

<span data-ttu-id="598fc-231">Указывает, что этот командлет получает объекты, если значение свойства меньше указанного значения.</span><span class="sxs-lookup"><span data-stu-id="598fc-231">Indicates that this cmdlet gets objects if the property value is less-than the specified value.</span></span> <span data-ttu-id="598fc-232">В этой операции учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="598fc-232">This operation is case-sensitive.</span></span>

<span data-ttu-id="598fc-233">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="598fc-233">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveLessThanSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="598fc-234">-CMatch</span><span class="sxs-lookup"><span data-stu-id="598fc-234">-CMatch</span></span>

<span data-ttu-id="598fc-235">Указывает, что этот командлет получает объекты, если значение свойства соответствует указанному регулярному выражению.</span><span class="sxs-lookup"><span data-stu-id="598fc-235">Indicates that this cmdlet gets objects if the property value matches the specified regular expression.</span></span> <span data-ttu-id="598fc-236">В этой операции учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="598fc-236">This operation is case-sensitive.</span></span> <span data-ttu-id="598fc-237">Если входные данные скалярны, сопоставленное значение сохраняется в `$Matches` автоматической переменной.</span><span class="sxs-lookup"><span data-stu-id="598fc-237">When the input is scalar, the matched value is saved in `$Matches` automatic variable.</span></span>

<span data-ttu-id="598fc-238">Пример: `Get-Process | where ProcessName -CMatch "Shell"`</span><span class="sxs-lookup"><span data-stu-id="598fc-238">For example: `Get-Process | where ProcessName -CMatch "Shell"`</span></span>

<span data-ttu-id="598fc-239">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="598fc-239">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveMatchSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="598fc-240">-CNE</span><span class="sxs-lookup"><span data-stu-id="598fc-240">-CNE</span></span>

<span data-ttu-id="598fc-241">Указывает, что этот командлет получает объекты, если значение свойства отличается от указанного значения.</span><span class="sxs-lookup"><span data-stu-id="598fc-241">Indicates that this cmdlet gets objects if the property value is different than the specified value.</span></span>
<span data-ttu-id="598fc-242">В этой операции учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="598fc-242">This operation is case-sensitive.</span></span>

<span data-ttu-id="598fc-243">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="598fc-243">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveNotEqualSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="598fc-244">-Кнотконтаинс</span><span class="sxs-lookup"><span data-stu-id="598fc-244">-CNotContains</span></span>

<span data-ttu-id="598fc-245">Указывает, что этот командлет получает объекты, если значение свойства объекта не является точным соответствием для указанного значения.</span><span class="sxs-lookup"><span data-stu-id="598fc-245">Indicates that this cmdlet gets objects if the property value of the object is not an exact match for the specified value.</span></span> <span data-ttu-id="598fc-246">В этой операции учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="598fc-246">This operation is case-sensitive.</span></span>

<span data-ttu-id="598fc-247">Пример: `Get-Process | where ProcessName -CNotContains "svchost"`</span><span class="sxs-lookup"><span data-stu-id="598fc-247">For example: `Get-Process | where ProcessName -CNotContains "svchost"`</span></span>

<span data-ttu-id="598fc-248">**NotContains** и **кнотконтаинс** ссылаются на коллекцию значений и имеют значение true, если коллекция не содержит элементов, которые точно соответствуют заданному значению.</span><span class="sxs-lookup"><span data-stu-id="598fc-248">**NotContains** and **CNotContains** refer to a collection of values and are true when the collection does not contains any items that are an exact match for the specified value.</span></span> <span data-ttu-id="598fc-249">Если входные данные являются одним объектом, PowerShell преобразует его в коллекцию одного объекта.</span><span class="sxs-lookup"><span data-stu-id="598fc-249">If the input is a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="598fc-250">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="598fc-250">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveNotContainsSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="598fc-251">-Кнотин</span><span class="sxs-lookup"><span data-stu-id="598fc-251">-CNotIn</span></span>

<span data-ttu-id="598fc-252">Указывает, что этот командлет получает объекты, если значение свойства не является точным соответствием для указанного значения.</span><span class="sxs-lookup"><span data-stu-id="598fc-252">Indicates that this cmdlet gets objects if the property value is not an exact match for the specified value.</span></span> <span data-ttu-id="598fc-253">В этой операции учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="598fc-253">This operation is case-sensitive.</span></span>

<span data-ttu-id="598fc-254">Пример: `Get-Process | where -Value "svchost" -CNotIn -Property ProcessName`</span><span class="sxs-lookup"><span data-stu-id="598fc-254">For example: `Get-Process | where -Value "svchost" -CNotIn -Property ProcessName`</span></span>

<span data-ttu-id="598fc-255">Операторы **NotIn** и **Кнотин** похожи на **NotContains** и **кнотконтаинс** , за исключением того, что позиции свойств и значений реверсируются.</span><span class="sxs-lookup"><span data-stu-id="598fc-255">**NotIn** and **CNotIn** operators resemble **NotContains** and **CNotContains** , except that the property and value positions are reversed.</span></span> <span data-ttu-id="598fc-256">Например, обе следующие инструкции верны.</span><span class="sxs-lookup"><span data-stu-id="598fc-256">For example, the following statements are true.</span></span>

`"abc", "def" -CNotContains "Abc"`

`"abc" -CNotIn "Abc", "def"`

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveNotInSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="598fc-257">-Кнотлике</span><span class="sxs-lookup"><span data-stu-id="598fc-257">-CNotLike</span></span>

<span data-ttu-id="598fc-258">Указывает, что этот командлет получает объекты, если значение свойства не соответствует значению, включающему символы-шаблоны.</span><span class="sxs-lookup"><span data-stu-id="598fc-258">Indicates that this cmdlet gets objects if the property value does not match a value that includes wildcard characters.</span></span> <span data-ttu-id="598fc-259">В этой операции учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="598fc-259">This operation is case-sensitive.</span></span>

<span data-ttu-id="598fc-260">Пример: `Get-Process | where ProcessName -CNotLike "*host"`</span><span class="sxs-lookup"><span data-stu-id="598fc-260">For example: `Get-Process | where ProcessName -CNotLike "*host"`</span></span>

<span data-ttu-id="598fc-261">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="598fc-261">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveNotLikeSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="598fc-262">-Кнотматч</span><span class="sxs-lookup"><span data-stu-id="598fc-262">-CNotMatch</span></span>

<span data-ttu-id="598fc-263">Указывает, что этот командлет получает объекты, если значение свойства не совпадает с указанным регулярным выражением.</span><span class="sxs-lookup"><span data-stu-id="598fc-263">Indicates that this cmdlet gets objects if the property value does not match the specified regular expression.</span></span> <span data-ttu-id="598fc-264">В этой операции учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="598fc-264">This operation is case-sensitive.</span></span> <span data-ttu-id="598fc-265">Если входные данные скалярны, сопоставленное значение сохраняется в `$Matches` автоматической переменной.</span><span class="sxs-lookup"><span data-stu-id="598fc-265">When the input is scalar, the matched value is saved in `$Matches` automatic variable.</span></span>

<span data-ttu-id="598fc-266">Пример: `Get-Process | where ProcessName -CNotMatch "Shell"`</span><span class="sxs-lookup"><span data-stu-id="598fc-266">For example: `Get-Process | where ProcessName -CNotMatch "Shell"`</span></span>

<span data-ttu-id="598fc-267">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="598fc-267">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: CaseSensitiveNotMatchSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="598fc-268">— Содержит</span><span class="sxs-lookup"><span data-stu-id="598fc-268">-Contains</span></span>

<span data-ttu-id="598fc-269">Указывает, что этот командлет получает объекты, если какой-либо элемент в значении свойства объекта является точным соответствием для указанного значения.</span><span class="sxs-lookup"><span data-stu-id="598fc-269">Indicates that this cmdlet gets objects if any item in the property value of the object is an exact match for the specified value.</span></span>

<span data-ttu-id="598fc-270">Пример: `Get-Process | where ProcessName -Contains "Svchost"`</span><span class="sxs-lookup"><span data-stu-id="598fc-270">For example: `Get-Process | where ProcessName -Contains "Svchost"`</span></span>

<span data-ttu-id="598fc-271">Если значение свойства содержит один объект, PowerShell преобразует его в коллекцию одного объекта.</span><span class="sxs-lookup"><span data-stu-id="598fc-271">If the property value contains a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="598fc-272">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="598fc-272">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ContainsSet
Aliases: IContains

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="598fc-273">-EQ</span><span class="sxs-lookup"><span data-stu-id="598fc-273">-EQ</span></span>

<span data-ttu-id="598fc-274">Указывает, что этот командлет получает объекты, если значение свойства совпадает с указанным значением.</span><span class="sxs-lookup"><span data-stu-id="598fc-274">Indicates that this cmdlet gets objects if the property value is the same as the specified value.</span></span>

<span data-ttu-id="598fc-275">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="598fc-275">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: EqualSet
Aliases: IEQ

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="598fc-276">-FilterScript представляет собой</span><span class="sxs-lookup"><span data-stu-id="598fc-276">-FilterScript</span></span>

<span data-ttu-id="598fc-277">Задает блок сценария, который используется для фильтрации объектов.</span><span class="sxs-lookup"><span data-stu-id="598fc-277">Specifies the script block that is used to filter the objects.</span></span> <span data-ttu-id="598fc-278">Заключите блок скрипта в фигурные скобки ( `{}` ).</span><span class="sxs-lookup"><span data-stu-id="598fc-278">Enclose the script block in braces (`{}`).</span></span>

<span data-ttu-id="598fc-279">Имя параметра, **FilterScript представляет собой** , является необязательным.</span><span class="sxs-lookup"><span data-stu-id="598fc-279">The parameter name, **FilterScript** , is optional.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlockSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="598fc-280">-GE</span><span class="sxs-lookup"><span data-stu-id="598fc-280">-GE</span></span>

<span data-ttu-id="598fc-281">Указывает, что этот командлет получает объекты, если значение свойства больше или равно указанному значению.</span><span class="sxs-lookup"><span data-stu-id="598fc-281">Indicates that this cmdlet gets objects if the property value is greater than or equal to the specified value.</span></span>

<span data-ttu-id="598fc-282">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="598fc-282">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GreaterOrEqualSet
Aliases: IGE

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="598fc-283">-GT</span><span class="sxs-lookup"><span data-stu-id="598fc-283">-GT</span></span>

<span data-ttu-id="598fc-284">Указывает, что этот командлет получает объекты, если значение свойства больше указанного значения.</span><span class="sxs-lookup"><span data-stu-id="598fc-284">Indicates that this cmdlet gets objects if the property value is greater than the specified value.</span></span>

<span data-ttu-id="598fc-285">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="598fc-285">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GreaterThanSet
Aliases: IGT

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="598fc-286">— В</span><span class="sxs-lookup"><span data-stu-id="598fc-286">-In</span></span>

<span data-ttu-id="598fc-287">Указывает, что этот командлет получает объекты, если значение свойства совпадает с любым из указанных значений.</span><span class="sxs-lookup"><span data-stu-id="598fc-287">Indicates that this cmdlet gets objects if the property value matches any of the specified values.</span></span>
<span data-ttu-id="598fc-288">Пример:</span><span class="sxs-lookup"><span data-stu-id="598fc-288">For example:</span></span>

`Get-Process | where -Property ProcessName -in -Value "Svchost", "TaskHost", "WsmProvHost"`

<span data-ttu-id="598fc-289">Если значение параметра **value** является одним объектом, PowerShell преобразует его в коллекцию одного объекта.</span><span class="sxs-lookup"><span data-stu-id="598fc-289">If the value of the **Value** parameter is a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="598fc-290">Если значение свойства объекта является массивом, PowerShell использует ссылочное равенство для определения совпадения.</span><span class="sxs-lookup"><span data-stu-id="598fc-290">If the property value of an object is an array, PowerShell uses reference equality to determine a match.</span></span> <span data-ttu-id="598fc-291">`Where-Object` Возвращает объект только в том случае, если значение параметра **Property** и любое значение **value** являются одним и тем же экземпляром объекта.</span><span class="sxs-lookup"><span data-stu-id="598fc-291">`Where-Object` returns the object only if the value of the **Property** parameter and any value of **Value** are the same instance of an object.</span></span>

<span data-ttu-id="598fc-292">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="598fc-292">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: InSet
Aliases: IIn

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="598fc-293">-InputObject</span><span class="sxs-lookup"><span data-stu-id="598fc-293">-InputObject</span></span>

<span data-ttu-id="598fc-294">Задает объекты для фильтрации.</span><span class="sxs-lookup"><span data-stu-id="598fc-294">Specifies the objects to be filtered.</span></span> <span data-ttu-id="598fc-295">Также можно передать объекты в `Where-Object` .</span><span class="sxs-lookup"><span data-stu-id="598fc-295">You can also pipe the objects to `Where-Object`.</span></span>

<span data-ttu-id="598fc-296">При использовании параметра **InputObject** с параметром `Where-Object` , а не с результатами команды трубопроводов в `Where-Object` значение **InputObject** рассматривается как один объект.</span><span class="sxs-lookup"><span data-stu-id="598fc-296">When you use the **InputObject** parameter with `Where-Object`, instead of piping command results to `Where-Object`, the **InputObject** value is treated as a single object.</span></span> <span data-ttu-id="598fc-297">Это справедливо, даже если значением является коллекция, которая является результатом команды, например `-InputObject (Get-Process)` .</span><span class="sxs-lookup"><span data-stu-id="598fc-297">This is true even if the value is a collection that is the result of a command, such as `-InputObject (Get-Process)`.</span></span> <span data-ttu-id="598fc-298">Поскольку **InputObject** не может возвращать отдельные свойства из массива или коллекции объектов, рекомендуется `Where-Object` использовать для фильтрации коллекции объектов для объектов, имеющих определенные значения в определенных свойствах, `Where-Object` в конвейере, как показано в примерах этого раздела.</span><span class="sxs-lookup"><span data-stu-id="598fc-298">Because **InputObject** cannot return individual properties from an array or collection of objects, we recommend that, if you use `Where-Object` to filter a collection of objects for those objects that have specific values in defined properties, you use `Where-Object` in the pipeline, as shown in the examples in this topic.</span></span>

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

### <span data-ttu-id="598fc-299">— Имеет</span><span class="sxs-lookup"><span data-stu-id="598fc-299">-Is</span></span>

<span data-ttu-id="598fc-300">Указывает, что этот командлет получает объекты, если значение свойства является экземпляром указанного типа .NET.</span><span class="sxs-lookup"><span data-stu-id="598fc-300">Indicates that this cmdlet gets objects if the property value is an instance of the specified .NET type.</span></span> <span data-ttu-id="598fc-301">Заключите имя типа в квадратные скобки.</span><span class="sxs-lookup"><span data-stu-id="598fc-301">Enclose the type name in square brackets.</span></span>

<span data-ttu-id="598fc-302">Например `Get-Process | where StartTime -Is [DateTime]`.</span><span class="sxs-lookup"><span data-stu-id="598fc-302">For example, `Get-Process | where StartTime -Is [DateTime]`</span></span>

<span data-ttu-id="598fc-303">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="598fc-303">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: IsSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="598fc-304">-IsNot</span><span class="sxs-lookup"><span data-stu-id="598fc-304">-IsNot</span></span>

<span data-ttu-id="598fc-305">Указывает, что этот командлет получает объекты, если значение свойства не является экземпляром указанного типа .NET.</span><span class="sxs-lookup"><span data-stu-id="598fc-305">Indicates that this cmdlet gets objects if the property value is not an instance of the specified .NET type.</span></span>

<span data-ttu-id="598fc-306">Например `Get-Process | where StartTime -IsNot [DateTime]`.</span><span class="sxs-lookup"><span data-stu-id="598fc-306">For example, `Get-Process | where StartTime -IsNot [DateTime]`</span></span>

<span data-ttu-id="598fc-307">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="598fc-307">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: IsNotSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="598fc-308">-LE</span><span class="sxs-lookup"><span data-stu-id="598fc-308">-LE</span></span>

<span data-ttu-id="598fc-309">Указывает, что этот командлет получает объекты, если значение свойства меньше или равно указанному значению.</span><span class="sxs-lookup"><span data-stu-id="598fc-309">Indicates that this cmdlet gets objects if the property value is less than or equal to the specified value.</span></span>

<span data-ttu-id="598fc-310">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="598fc-310">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LessOrEqualSet
Aliases: ILE

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="598fc-311">-Like</span><span class="sxs-lookup"><span data-stu-id="598fc-311">-Like</span></span>

<span data-ttu-id="598fc-312">Указывает, что этот командлет получает объекты, если значение свойства соответствует значению, включающему символы-шаблоны.</span><span class="sxs-lookup"><span data-stu-id="598fc-312">Indicates that this cmdlet gets objects if the property value matches a value that includes wildcard characters.</span></span>

<span data-ttu-id="598fc-313">Пример: `Get-Process | where ProcessName -Like "*host"`</span><span class="sxs-lookup"><span data-stu-id="598fc-313">For example: `Get-Process | where ProcessName -Like "*host"`</span></span>

<span data-ttu-id="598fc-314">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="598fc-314">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LikeSet
Aliases: ILike

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="598fc-315">-LT</span><span class="sxs-lookup"><span data-stu-id="598fc-315">-LT</span></span>

<span data-ttu-id="598fc-316">Указывает, что этот командлет получает объекты, если значение свойства меньше указанного значения.</span><span class="sxs-lookup"><span data-stu-id="598fc-316">Indicates that this cmdlet gets objects if the property value is less than the specified value.</span></span>

<span data-ttu-id="598fc-317">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="598fc-317">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LessThanSet
Aliases: ILT

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="598fc-318">-Match</span><span class="sxs-lookup"><span data-stu-id="598fc-318">-Match</span></span>

<span data-ttu-id="598fc-319">Указывает, что этот командлет получает объекты, если значение свойства соответствует указанному регулярному выражению.</span><span class="sxs-lookup"><span data-stu-id="598fc-319">Indicates that this cmdlet gets objects if the property value matches the specified regular expression.</span></span> <span data-ttu-id="598fc-320">Если входные данные скалярны, сопоставленное значение сохраняется в `$Matches` автоматической переменной.</span><span class="sxs-lookup"><span data-stu-id="598fc-320">When the input is scalar, the matched value is saved in `$Matches` automatic variable.</span></span>

<span data-ttu-id="598fc-321">Пример: `Get-Process | where ProcessName -Match "shell"`</span><span class="sxs-lookup"><span data-stu-id="598fc-321">For example: `Get-Process | where ProcessName -Match "shell"`</span></span>

<span data-ttu-id="598fc-322">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="598fc-322">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: MatchSet
Aliases: IMatch

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="598fc-323">-NE</span><span class="sxs-lookup"><span data-stu-id="598fc-323">-NE</span></span>

<span data-ttu-id="598fc-324">Указывает, что этот командлет получает объекты, если значение свойства отличается от указанного значения.</span><span class="sxs-lookup"><span data-stu-id="598fc-324">Indicates that this cmdlet gets objects if the property value is different than the specified value.</span></span>

<span data-ttu-id="598fc-325">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="598fc-325">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NotEqualSet
Aliases: INE

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="598fc-326">— Не</span><span class="sxs-lookup"><span data-stu-id="598fc-326">-Not</span></span>

<span data-ttu-id="598fc-327">Указывает, что этот командлет получает объекты, если свойство не существует или имеет значение null или false.</span><span class="sxs-lookup"><span data-stu-id="598fc-327">Indicates that this cmdlet gets objects if the property does not exist or has a value of null or false.</span></span>

<span data-ttu-id="598fc-328">Пример: `Get-Service | where -Not "DependentServices"`</span><span class="sxs-lookup"><span data-stu-id="598fc-328">For example: `Get-Service | where -Not "DependentServices"`</span></span>

<span data-ttu-id="598fc-329">Этот параметр появился в Windows PowerShell 6,1.</span><span class="sxs-lookup"><span data-stu-id="598fc-329">This parameter was introduced in Windows PowerShell 6.1.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Not
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="598fc-330">-NotContains</span><span class="sxs-lookup"><span data-stu-id="598fc-330">-NotContains</span></span>

<span data-ttu-id="598fc-331">Указывает, что этот командлет получает объекты, если ни один из элементов в значении свойства не является точным соответствием для указанного значения.</span><span class="sxs-lookup"><span data-stu-id="598fc-331">Indicates that this cmdlet gets objects if none of the items in the property value is an exact match for the specified value.</span></span>

<span data-ttu-id="598fc-332">Пример: `Get-Process | where ProcessName -NotContains "Svchost"`</span><span class="sxs-lookup"><span data-stu-id="598fc-332">For example: `Get-Process | where ProcessName -NotContains "Svchost"`</span></span>

<span data-ttu-id="598fc-333">**NotContains** ссылается на коллекцию значений и имеет значение true, если коллекция не содержит элементов, которые точно совпадают с указанным значением.</span><span class="sxs-lookup"><span data-stu-id="598fc-333">**NotContains** refers to a collection of values and is true if the collection does not contain any items that are an exact match for the specified value.</span></span> <span data-ttu-id="598fc-334">Если входные данные являются одним объектом, PowerShell преобразует его в коллекцию одного объекта.</span><span class="sxs-lookup"><span data-stu-id="598fc-334">If the input is a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="598fc-335">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="598fc-335">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NotContainsSet
Aliases: INotContains

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="598fc-336">-NotIn</span><span class="sxs-lookup"><span data-stu-id="598fc-336">-NotIn</span></span>

<span data-ttu-id="598fc-337">Указывает, что этот командлет получает объекты, если значение свойства не является точным соответствием для любого из указанных значений.</span><span class="sxs-lookup"><span data-stu-id="598fc-337">Indicates that this cmdlet gets objects if the property value is not an exact match for any of the specified values.</span></span>

<span data-ttu-id="598fc-338">Пример: `Get-Process | where -Value "svchost" -NotIn -Property ProcessName`</span><span class="sxs-lookup"><span data-stu-id="598fc-338">For example: `Get-Process | where -Value "svchost" -NotIn -Property ProcessName`</span></span>

<span data-ttu-id="598fc-339">Если значение **value** является одним объектом, PowerShell преобразует его в коллекцию одного объекта.</span><span class="sxs-lookup"><span data-stu-id="598fc-339">If the value of **Value** is a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="598fc-340">Если значение свойства объекта является массивом, PowerShell использует ссылочное равенство для определения совпадения.</span><span class="sxs-lookup"><span data-stu-id="598fc-340">If the property value of an object is an array, PowerShell uses reference equality to determine a match.</span></span> <span data-ttu-id="598fc-341">`Where-Object` Возвращает объект только в том случае, если значение **Свойства** и любое значение **значения** не являются одним и тем же экземпляром объекта.</span><span class="sxs-lookup"><span data-stu-id="598fc-341">`Where-Object` returns the object only if the value of **Property** and any value of **Value** are not the same instance of an object.</span></span>

<span data-ttu-id="598fc-342">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="598fc-342">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NotInSet
Aliases: INotIn

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="598fc-343">-NotLike</span><span class="sxs-lookup"><span data-stu-id="598fc-343">-NotLike</span></span>

<span data-ttu-id="598fc-344">Указывает, что этот командлет получает объекты, если значение свойства не соответствует значению, включающему символы-шаблоны.</span><span class="sxs-lookup"><span data-stu-id="598fc-344">Indicates that this cmdlet gets objects if the property value does not match a value that includes wildcard characters.</span></span>

<span data-ttu-id="598fc-345">Пример: `Get-Process | where ProcessName -NotLike "*host"`</span><span class="sxs-lookup"><span data-stu-id="598fc-345">For example: `Get-Process | where ProcessName -NotLike "*host"`</span></span>

<span data-ttu-id="598fc-346">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="598fc-346">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NotLikeSet
Aliases: INotLike

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="598fc-347">-NotMatch</span><span class="sxs-lookup"><span data-stu-id="598fc-347">-NotMatch</span></span>

<span data-ttu-id="598fc-348">Указывает, что этот командлет получает объекты, если значение свойства не совпадает с указанным регулярным выражением.</span><span class="sxs-lookup"><span data-stu-id="598fc-348">Indicates that this cmdlet gets objects when the property value does not match the specified regular expression.</span></span> <span data-ttu-id="598fc-349">Если входные данные скалярны, сопоставленное значение сохраняется в `$Matches` автоматической переменной.</span><span class="sxs-lookup"><span data-stu-id="598fc-349">When the input is scalar, the matched value is saved in `$Matches` automatic variable.</span></span>

<span data-ttu-id="598fc-350">Пример: `Get-Process | where ProcessName -NotMatch "PowerShell"`</span><span class="sxs-lookup"><span data-stu-id="598fc-350">For example: `Get-Process | where ProcessName -NotMatch "PowerShell"`</span></span>

<span data-ttu-id="598fc-351">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="598fc-351">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NotMatchSet
Aliases: INotMatch

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="598fc-352">-Property</span><span class="sxs-lookup"><span data-stu-id="598fc-352">-Property</span></span>

<span data-ttu-id="598fc-353">Задает имя свойства объекта.</span><span class="sxs-lookup"><span data-stu-id="598fc-353">Specifies the name of an object property.</span></span> <span data-ttu-id="598fc-354">Имя параметра, **свойство** , является необязательным.</span><span class="sxs-lookup"><span data-stu-id="598fc-354">The parameter name, **Property** , is optional.</span></span>

<span data-ttu-id="598fc-355">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="598fc-355">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: EqualSet, CaseSensitiveNotLikeSet, CaseSensitiveEqualSet, NotEqualSet, CaseSensitiveNotEqualSet, GreaterThanSet, CaseSensitiveGreaterThanSet, LessThanSet, CaseSensitiveLessThanSet, GreaterOrEqualSet, CaseSensitiveGreaterOrEqualSet, LessOrEqualSet, CaseSensitiveLessOrEqualSet, LikeSet, CaseSensitiveLikeSet, NotLikeSet, MatchSet, CaseSensitiveMatchSet, NotMatchSet, CaseSensitiveNotMatchSet, ContainsSet, CaseSensitiveContainsSet, NotContainsSet, CaseSensitiveNotContainsSet, InSet, CaseSensitiveInSet, NotInSet, CaseSensitiveNotInSet, IsSet, IsNotSet, Not
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="598fc-356">-Value</span><span class="sxs-lookup"><span data-stu-id="598fc-356">-Value</span></span>

<span data-ttu-id="598fc-357">Задает значение свойства.</span><span class="sxs-lookup"><span data-stu-id="598fc-357">Specifies a property value.</span></span> <span data-ttu-id="598fc-358">Имя параметра, **значение** является необязательным.</span><span class="sxs-lookup"><span data-stu-id="598fc-358">The parameter name, **Value** , is optional.</span></span> <span data-ttu-id="598fc-359">Этот параметр принимает подстановочные знаки при использовании со следующими параметрами сравнения:</span><span class="sxs-lookup"><span data-stu-id="598fc-359">This parameter accepts wildcard characters when used with the following comparison parameters:</span></span>

- <span data-ttu-id="598fc-360">**клике**</span><span class="sxs-lookup"><span data-stu-id="598fc-360">**CLike**</span></span>
- <span data-ttu-id="598fc-361">**кнотлике**</span><span class="sxs-lookup"><span data-stu-id="598fc-361">**CNotLike**</span></span>
- <span data-ttu-id="598fc-362">**Например**</span><span class="sxs-lookup"><span data-stu-id="598fc-362">**Like**</span></span>
- <span data-ttu-id="598fc-363">**NotLike**</span><span class="sxs-lookup"><span data-stu-id="598fc-363">**NotLike**</span></span>

<span data-ttu-id="598fc-364">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="598fc-364">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: Object
Parameter Sets: EqualSet, CaseSensitiveGreaterOrEqualSet, CaseSensitiveEqualSet, NotEqualSet, CaseSensitiveNotEqualSet, GreaterThanSet, CaseSensitiveGreaterThanSet, LessThanSet, CaseSensitiveLessThanSet, GreaterOrEqualSet, LessOrEqualSet, CaseSensitiveLessOrEqualSet, LikeSet, CaseSensitiveLikeSet, NotLikeSet, CaseSensitiveNotLikeSet, MatchSet, CaseSensitiveMatchSet, NotMatchSet, CaseSensitiveNotMatchSet, ContainsSet, CaseSensitiveContainsSet, NotContainsSet, CaseSensitiveNotContainsSet, InSet, CaseSensitiveInSet, NotInSet, CaseSensitiveNotInSet, IsSet, IsNotSet
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="598fc-365">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="598fc-365">CommonParameters</span></span>

<span data-ttu-id="598fc-366">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="598fc-366">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="598fc-367">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="598fc-367">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="598fc-368">Входные данные</span><span class="sxs-lookup"><span data-stu-id="598fc-368">INPUTS</span></span>

### <span data-ttu-id="598fc-369">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="598fc-369">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="598fc-370">Объекты можно передать в этот командлет по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="598fc-370">You can pipe the objects to this cmdlet.</span></span>

## <span data-ttu-id="598fc-371">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="598fc-371">OUTPUTS</span></span>

### <span data-ttu-id="598fc-372">Объект</span><span class="sxs-lookup"><span data-stu-id="598fc-372">Object</span></span>

<span data-ttu-id="598fc-373">Этот командлет возвращает выбранные элементы из набора входных объектов.</span><span class="sxs-lookup"><span data-stu-id="598fc-373">This cmdlet returns selected items from the input object set.</span></span>

## <span data-ttu-id="598fc-374">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="598fc-374">NOTES</span></span>

<span data-ttu-id="598fc-375">Начиная с Windows PowerShell 4,0, `Where` `ForEach` методы были добавлены для использования с коллекциями.</span><span class="sxs-lookup"><span data-stu-id="598fc-375">Starting in Windows PowerShell 4.0, `Where` and `ForEach` methods were added for use with collections.</span></span>

<span data-ttu-id="598fc-376">Дополнительные сведения об этих новых методах можно узнать здесь [about_arrays](./About/about_Arrays.md)</span><span class="sxs-lookup"><span data-stu-id="598fc-376">You can read more about these new methods here [about_arrays](./About/about_Arrays.md)</span></span>

## <span data-ttu-id="598fc-377">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="598fc-377">RELATED LINKS</span></span>

[<span data-ttu-id="598fc-378">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="598fc-378">Compare-Object</span></span>](../Microsoft.PowerShell.Utility/Compare-Object.md)

[<span data-ttu-id="598fc-379">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="598fc-379">ForEach-Object</span></span>](ForEach-Object.md)

[<span data-ttu-id="598fc-380">Group-Object</span><span class="sxs-lookup"><span data-stu-id="598fc-380">Group-Object</span></span>](../Microsoft.PowerShell.Utility/Group-Object.md)

[<span data-ttu-id="598fc-381">Measure-Object;</span><span class="sxs-lookup"><span data-stu-id="598fc-381">Measure-Object</span></span>](../Microsoft.PowerShell.Utility/Measure-Object.md)

[<span data-ttu-id="598fc-382">New-Object</span><span class="sxs-lookup"><span data-stu-id="598fc-382">New-Object</span></span>](../Microsoft.PowerShell.Utility/New-Object.md)

[<span data-ttu-id="598fc-383">Select-Object</span><span class="sxs-lookup"><span data-stu-id="598fc-383">Select-Object</span></span>](../Microsoft.PowerShell.Utility/Select-Object.md)

[<span data-ttu-id="598fc-384">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="598fc-384">Sort-Object</span></span>](../Microsoft.PowerShell.Utility/Sort-Object.md)

[<span data-ttu-id="598fc-385">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="598fc-385">Tee-Object</span></span>](../Microsoft.PowerShell.Utility/Tee-Object.md)
