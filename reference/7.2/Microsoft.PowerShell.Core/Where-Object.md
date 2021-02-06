---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Where-Object
ms.openlocfilehash: 667a503d67ac9a9a0f41187cbac079d946247618
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601483"
---
# <span data-ttu-id="c53eb-102">Where-Object</span><span class="sxs-lookup"><span data-stu-id="c53eb-102">Where-Object</span></span>

## <span data-ttu-id="c53eb-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="c53eb-103">SYNOPSIS</span></span>
<span data-ttu-id="c53eb-104">Выбирает объекты из коллекции на основании значения их свойств.</span><span class="sxs-lookup"><span data-stu-id="c53eb-104">Selects objects from a collection based on their property values.</span></span>

## <span data-ttu-id="c53eb-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c53eb-105">SYNTAX</span></span>

### <span data-ttu-id="c53eb-106">Equals (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="c53eb-106">EqualSet (Default)</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] [-EQ]
 [<CommonParameters>]
```

### <span data-ttu-id="c53eb-107">скриптблокксет</span><span class="sxs-lookup"><span data-stu-id="c53eb-107">ScriptBlockSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-FilterScript] <ScriptBlock> [<CommonParameters>]
```

### <span data-ttu-id="c53eb-108">Match</span><span class="sxs-lookup"><span data-stu-id="c53eb-108">MatchSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -Match
 [<CommonParameters>]
```

### <span data-ttu-id="c53eb-109">касесенситивикуалсет</span><span class="sxs-lookup"><span data-stu-id="c53eb-109">CaseSensitiveEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CEQ
 [<CommonParameters>]
```

### <span data-ttu-id="c53eb-110">нотекуалсет</span><span class="sxs-lookup"><span data-stu-id="c53eb-110">NotEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NE
 [<CommonParameters>]
```

### <span data-ttu-id="c53eb-111">касесенситивенотекуалсет</span><span class="sxs-lookup"><span data-stu-id="c53eb-111">CaseSensitiveNotEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNE
 [<CommonParameters>]
```

### <span data-ttu-id="c53eb-112">греатерсансет</span><span class="sxs-lookup"><span data-stu-id="c53eb-112">GreaterThanSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -GT
 [<CommonParameters>]
```

### <span data-ttu-id="c53eb-113">касесенситивегреатерсансет</span><span class="sxs-lookup"><span data-stu-id="c53eb-113">CaseSensitiveGreaterThanSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CGT
 [<CommonParameters>]
```

### <span data-ttu-id="c53eb-114">лесссансет</span><span class="sxs-lookup"><span data-stu-id="c53eb-114">LessThanSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -LT
 [<CommonParameters>]
```

### <span data-ttu-id="c53eb-115">касесенситивелесссансет</span><span class="sxs-lookup"><span data-stu-id="c53eb-115">CaseSensitiveLessThanSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CLT
 [<CommonParameters>]
```

### <span data-ttu-id="c53eb-116">греатерорекуалсет</span><span class="sxs-lookup"><span data-stu-id="c53eb-116">GreaterOrEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -GE
 [<CommonParameters>]
```

### <span data-ttu-id="c53eb-117">касесенситивегреатерорекуалсет</span><span class="sxs-lookup"><span data-stu-id="c53eb-117">CaseSensitiveGreaterOrEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CGE
 [<CommonParameters>]
```

### <span data-ttu-id="c53eb-118">лессорекуалсет</span><span class="sxs-lookup"><span data-stu-id="c53eb-118">LessOrEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -LE
 [<CommonParameters>]
```

### <span data-ttu-id="c53eb-119">касесенситивелессорекуалсет</span><span class="sxs-lookup"><span data-stu-id="c53eb-119">CaseSensitiveLessOrEqualSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CLE
 [<CommonParameters>]
```

### <span data-ttu-id="c53eb-120">Аналогичный</span><span class="sxs-lookup"><span data-stu-id="c53eb-120">LikeSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -Like
 [<CommonParameters>]
```

### <span data-ttu-id="c53eb-121">касесенситивеликесет</span><span class="sxs-lookup"><span data-stu-id="c53eb-121">CaseSensitiveLikeSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CLike
 [<CommonParameters>]
```

### <span data-ttu-id="c53eb-122">нотликесет</span><span class="sxs-lookup"><span data-stu-id="c53eb-122">NotLikeSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NotLike
 [<CommonParameters>]
```

### <span data-ttu-id="c53eb-123">касесенситивенотликесет</span><span class="sxs-lookup"><span data-stu-id="c53eb-123">CaseSensitiveNotLikeSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNotLike
 [<CommonParameters>]
```

### <span data-ttu-id="c53eb-124">касесенситивематчсет</span><span class="sxs-lookup"><span data-stu-id="c53eb-124">CaseSensitiveMatchSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CMatch
 [<CommonParameters>]
```

### <span data-ttu-id="c53eb-125">нотматчсет</span><span class="sxs-lookup"><span data-stu-id="c53eb-125">NotMatchSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NotMatch
 [<CommonParameters>]
```

### <span data-ttu-id="c53eb-126">касесенситивенотматчсет</span><span class="sxs-lookup"><span data-stu-id="c53eb-126">CaseSensitiveNotMatchSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNotMatch
 [<CommonParameters>]
```

### <span data-ttu-id="c53eb-127">Contains</span><span class="sxs-lookup"><span data-stu-id="c53eb-127">ContainsSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -Contains
 [<CommonParameters>]
```

### <span data-ttu-id="c53eb-128">касесенситивеконтаинссет</span><span class="sxs-lookup"><span data-stu-id="c53eb-128">CaseSensitiveContainsSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CContains
 [<CommonParameters>]
```

### <span data-ttu-id="c53eb-129">нотконтаинссет</span><span class="sxs-lookup"><span data-stu-id="c53eb-129">NotContainsSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NotContains
 [<CommonParameters>]
```

### <span data-ttu-id="c53eb-130">касесенситивенотконтаинссет</span><span class="sxs-lookup"><span data-stu-id="c53eb-130">CaseSensitiveNotContainsSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNotContains
 [<CommonParameters>]
```

### <span data-ttu-id="c53eb-131">Вставка</span><span class="sxs-lookup"><span data-stu-id="c53eb-131">InSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -In
 [<CommonParameters>]
```

### <span data-ttu-id="c53eb-132">касесенситивеинсет</span><span class="sxs-lookup"><span data-stu-id="c53eb-132">CaseSensitiveInSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CIn
 [<CommonParameters>]
```

### <span data-ttu-id="c53eb-133">нотинсет</span><span class="sxs-lookup"><span data-stu-id="c53eb-133">NotInSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -NotIn
 [<CommonParameters>]
```

### <span data-ttu-id="c53eb-134">касесенситивенотинсет</span><span class="sxs-lookup"><span data-stu-id="c53eb-134">CaseSensitiveNotInSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -CNotIn
 [<CommonParameters>]
```

### <span data-ttu-id="c53eb-135">иссет</span><span class="sxs-lookup"><span data-stu-id="c53eb-135">IsSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -Is
 [<CommonParameters>]
```

### <span data-ttu-id="c53eb-136">иснотсет</span><span class="sxs-lookup"><span data-stu-id="c53eb-136">IsNotSet</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> [[-Value] <Object>] -IsNot
 [<CommonParameters>]
```

### <span data-ttu-id="c53eb-137">Not</span><span class="sxs-lookup"><span data-stu-id="c53eb-137">Not</span></span>

```
Where-Object [-InputObject <PSObject>] [-Property] <String> -Not [<CommonParameters>]
```

## <span data-ttu-id="c53eb-138">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c53eb-138">DESCRIPTION</span></span>

<span data-ttu-id="c53eb-139">`Where-Object`Командлет выбирает объекты, имеющие определенные значения свойств, из коллекции объектов, которые передаются в него.</span><span class="sxs-lookup"><span data-stu-id="c53eb-139">The `Where-Object` cmdlet selects objects that have particular property values from the collection of objects that are passed to it.</span></span> <span data-ttu-id="c53eb-140">Например, командлет можно использовать `Where-Object` для выбора файлов, созданных после определенной даты, событий с определенным идентификатором, или компьютеров, использующих определенную версию Windows.</span><span class="sxs-lookup"><span data-stu-id="c53eb-140">For example, you can use the `Where-Object` cmdlet to select files that were created after a certain date, events with a particular ID, or computers that use a particular version of Windows.</span></span>

<span data-ttu-id="c53eb-141">Начиная с Windows PowerShell 3,0 существует два разных способа создания `Where-Object` команды.</span><span class="sxs-lookup"><span data-stu-id="c53eb-141">Starting in Windows PowerShell 3.0, there are two different ways to construct a `Where-Object` command.</span></span>

- <span data-ttu-id="c53eb-142">**Блок скрипта**.</span><span class="sxs-lookup"><span data-stu-id="c53eb-142">**Script block**.</span></span> <span data-ttu-id="c53eb-143">Для указания имени свойства, оператора сравнения и значения свойства можно использовать блок сценария.</span><span class="sxs-lookup"><span data-stu-id="c53eb-143">You can use a script block to specify the property name, a comparison operator, and a property value.</span></span> <span data-ttu-id="c53eb-144">`Where-Object` Возвращает все объекты, для которых инструкция блока скрипта имеет значение true.</span><span class="sxs-lookup"><span data-stu-id="c53eb-144">`Where-Object` returns all objects for which the script block statement is true.</span></span>

  <span data-ttu-id="c53eb-145">Например, следующая команда получает процессы в классе с нормальным приоритетом, то есть обрабатывает, где значение свойства **PriorityClass значение** равно "Обычная".</span><span class="sxs-lookup"><span data-stu-id="c53eb-145">For example, the following command gets processes in the Normal priority class, that is, processes where the value of the **PriorityClass** property equals Normal.</span></span>

  `Get-Process | Where-Object {$_.PriorityClass -eq "Normal"}`

  <span data-ttu-id="c53eb-146">Все операторы сравнения PowerShell допустимы в формате блока сценария.</span><span class="sxs-lookup"><span data-stu-id="c53eb-146">All PowerShell comparison operators are valid in the script block format.</span></span> <span data-ttu-id="c53eb-147">Дополнительные сведения об операторах сравнения см. в разделе [about_Comparison_Operators](./About/about_Comparison_Operators.md).</span><span class="sxs-lookup"><span data-stu-id="c53eb-147">For more information about comparison operators, see [about_Comparison_Operators](./About/about_Comparison_Operators.md).</span></span>

- <span data-ttu-id="c53eb-148">**Оператор сравнения**.</span><span class="sxs-lookup"><span data-stu-id="c53eb-148">**Comparison statement**.</span></span> <span data-ttu-id="c53eb-149">Можно также написать оператор сравнения, который больше похож на естественный язык.</span><span class="sxs-lookup"><span data-stu-id="c53eb-149">You can also write a comparison statement, which is much more like natural language.</span></span> <span data-ttu-id="c53eb-150">Операторы сравнения были представлены в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="c53eb-150">Comparison statements were introduced in Windows PowerShell 3.0.</span></span>

  <span data-ttu-id="c53eb-151">Например, следующие команды также получают процессы, имеющие класс приоритета "Обычная".</span><span class="sxs-lookup"><span data-stu-id="c53eb-151">For example, the following commands also get processes that have a priority class of Normal.</span></span> <span data-ttu-id="c53eb-152">Эти команды эквивалентны и взаимозаменяемы.</span><span class="sxs-lookup"><span data-stu-id="c53eb-152">These commands are equivalent and can be used interchangeably.</span></span>

  `Get-Process | Where-Object -Property PriorityClass -eq -Value "Normal"`

  `Get-Process | Where-Object PriorityClass -eq "Normal"`

  <span data-ttu-id="c53eb-153">Начиная с Windows PowerShell 3,0, `Where-Object` в команде добавляются операторы сравнения в качестве параметров `Where-Object` .</span><span class="sxs-lookup"><span data-stu-id="c53eb-153">Starting in Windows PowerShell 3.0, `Where-Object` adds comparison operators as parameters in a `Where-Object` command.</span></span> <span data-ttu-id="c53eb-154">Если не указано иначе, все операторы вводятся без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="c53eb-154">Unless specified, all operators are case-insensitive.</span></span> <span data-ttu-id="c53eb-155">До Windows PowerShell 3,0 операторы сравнения в языке PowerShell можно использовать только в блоках сценариев.</span><span class="sxs-lookup"><span data-stu-id="c53eb-155">Prior to Windows PowerShell 3.0, the comparison operators in the PowerShell language could be used only in script blocks.</span></span>

<span data-ttu-id="c53eb-156">При предоставлении одного **Свойства** в `Where-Object` значение свойства обрабатывается как логическое выражение.</span><span class="sxs-lookup"><span data-stu-id="c53eb-156">When you provide a single **Property** to `Where-Object`, the value of the property is treated as a boolean expression.</span></span> <span data-ttu-id="c53eb-157">Если значение **length** не равно нулю, выражение принимает **значение true**.</span><span class="sxs-lookup"><span data-stu-id="c53eb-157">When the value of **Length** is not zero, the expression evaluates to **True**.</span></span> <span data-ttu-id="c53eb-158">Пример: `('hi', '', 'there') | Where-Object Length`</span><span class="sxs-lookup"><span data-stu-id="c53eb-158">For example: `('hi', '', 'there') | Where-Object Length`</span></span>

<span data-ttu-id="c53eb-159">Предыдущий пример функционально эквивалентен:</span><span class="sxs-lookup"><span data-stu-id="c53eb-159">The previous example is functionally equivalent to:</span></span>

- `('hi', '', 'there') | Where-Object Length -GT 0`
- `('hi', '', 'there') | Where-Object {$_.Length -gt 0}`

## <span data-ttu-id="c53eb-160">Примеры</span><span class="sxs-lookup"><span data-stu-id="c53eb-160">EXAMPLES</span></span>

### <span data-ttu-id="c53eb-161">Пример 1. получение остановленных служб</span><span class="sxs-lookup"><span data-stu-id="c53eb-161">Example 1: Get stopped services</span></span>

<span data-ttu-id="c53eb-162">Эти команды получают список всех служб, остановленных в данный момент.</span><span class="sxs-lookup"><span data-stu-id="c53eb-162">These commands get a list of all services that are currently stopped.</span></span> <span data-ttu-id="c53eb-163">`$_`Автоматическая переменная представляет каждый объект, передаваемый в `Where-Object` командлет.</span><span class="sxs-lookup"><span data-stu-id="c53eb-163">The `$_` automatic variable represents each object that is passed to the `Where-Object` cmdlet.</span></span>

<span data-ttu-id="c53eb-164">Первая команда использует формат блока сценария, вторая команда использует формат инструкции сравнения.</span><span class="sxs-lookup"><span data-stu-id="c53eb-164">The first command uses the script block format, the second command uses the comparison statement format.</span></span> <span data-ttu-id="c53eb-165">Команды эквивалентны и взаимозаменяемы.</span><span class="sxs-lookup"><span data-stu-id="c53eb-165">The commands are equivalent and can be used interchangeably.</span></span>

```powershell
Get-Service | Where-Object {$_.Status -eq "Stopped"}
Get-Service | where Status -eq "Stopped"
```

### <span data-ttu-id="c53eb-166">Пример 2. получение процессов на основе рабочего набора</span><span class="sxs-lookup"><span data-stu-id="c53eb-166">Example 2: Get processes based on working set</span></span>

<span data-ttu-id="c53eb-167">Эти команды содержат список процессов, имеющих рабочий набор, превышающий 250 мегабайт (КБ).</span><span class="sxs-lookup"><span data-stu-id="c53eb-167">These commands list processes that have a working set greater than 250 megabytes (KB).</span></span> <span data-ttu-id="c53eb-168">Синтаксис ScriptBlock и инструкции эквивалентен и может использоваться взаимозаменяемым.</span><span class="sxs-lookup"><span data-stu-id="c53eb-168">The scriptblock and statement syntax are equivalent and can be used interchangeably.</span></span>

```powershell
Get-Process | Where-Object {$_.WorkingSet -GT 250MB}
Get-Process | Where-Object WorkingSet -GT (250MB)
```

### <span data-ttu-id="c53eb-169">Пример 3. получение процессов на основе имени процесса</span><span class="sxs-lookup"><span data-stu-id="c53eb-169">Example 3: Get processes based on process name</span></span>

<span data-ttu-id="c53eb-170">Эти команды получают процессы со значением свойства **processName** , которое начинается с буквы `p` .</span><span class="sxs-lookup"><span data-stu-id="c53eb-170">These commands get the processes that have a **ProcessName** property value that begins with the letter `p`.</span></span> <span data-ttu-id="c53eb-171">Оператор **Match** позволяет использовать совпадения регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="c53eb-171">The **Match** operator lets you use regular expression matches.</span></span>

<span data-ttu-id="c53eb-172">Синтаксис ScriptBlock и инструкции эквивалентен и может использоваться взаимозаменяемым.</span><span class="sxs-lookup"><span data-stu-id="c53eb-172">The scriptblock and statement syntax are equivalent and can be used interchangeably.</span></span>

```powershell
Get-Process | Where-Object {$_.ProcessName -Match "^p.*"}
Get-Process | Where-Object ProcessName -Match "^p.*"
```

### <span data-ttu-id="c53eb-173">Пример 4. Использование формата инструкции сравнения</span><span class="sxs-lookup"><span data-stu-id="c53eb-173">Example 4: Use the comparison statement format</span></span>

<span data-ttu-id="c53eb-174">В этом примере показано, как использовать новый формат инструкции сравнения `Where-Object` командлета.</span><span class="sxs-lookup"><span data-stu-id="c53eb-174">This example shows how to use the new comparison statement format of the `Where-Object` cmdlet.</span></span>

<span data-ttu-id="c53eb-175">Вторая команда использует формат оператора сравнения.</span><span class="sxs-lookup"><span data-stu-id="c53eb-175">The first command uses the comparison statement format.</span></span>
<span data-ttu-id="c53eb-176">В этой команде не используются псевдонимы, и все параметры включают имя параметра.</span><span class="sxs-lookup"><span data-stu-id="c53eb-176">In this command, no aliases are used and all parameters include the parameter name.</span></span>

<span data-ttu-id="c53eb-177">Вторая команда является более естественным способом использованием формата команды сравнения.</span><span class="sxs-lookup"><span data-stu-id="c53eb-177">The second command is the more natural use of the comparison command format.</span></span> <span data-ttu-id="c53eb-178">`where`Псевдоним заменяется `Where-Object` именем командлета, а все необязательные имена параметров опускаются.</span><span class="sxs-lookup"><span data-stu-id="c53eb-178">The `where` alias is substituted for the `Where-Object` cmdlet name and all optional parameter names are omitted.</span></span>

```powershell
Get-Process | Where-Object -Property Handles -GE -Value 1000
Get-Process | where Handles -GE 1000
```

### <span data-ttu-id="c53eb-179">Пример 5. получение команд на основе свойств</span><span class="sxs-lookup"><span data-stu-id="c53eb-179">Example 5: Get commands based on properties</span></span>

<span data-ttu-id="c53eb-180">В этом примере показано, как написать команды, которые возвращают элементы, имеющие значения true или false или любые значения для указанного свойства.</span><span class="sxs-lookup"><span data-stu-id="c53eb-180">This example shows how to write commands that return items that are true or false or have any value for a specified property.</span></span> <span data-ttu-id="c53eb-181">В каждом примере показаны форматы блока скрипта и инструкции сравнения для команды.</span><span class="sxs-lookup"><span data-stu-id="c53eb-181">Each example shows both the script block and comparison statement formats for the command.</span></span>

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

### <span data-ttu-id="c53eb-182">Пример 6. Использование нескольких условий</span><span class="sxs-lookup"><span data-stu-id="c53eb-182">Example 6: Use multiple conditions</span></span>

```powershell
Get-Module -ListAvailable | where {($_.Name -notlike "Microsoft*" -and $_.Name -notlike "PS*") -and $_.HelpInfoUri}
```

<span data-ttu-id="c53eb-183">В этом примере показано, как создать `Where-Object` команду с несколькими условиями.</span><span class="sxs-lookup"><span data-stu-id="c53eb-183">This example shows how to create a `Where-Object` command with multiple conditions.</span></span>

<span data-ttu-id="c53eb-184">Эта команда получает вспомогательные модули, которые поддерживают функцию обновляемой справки.</span><span class="sxs-lookup"><span data-stu-id="c53eb-184">This command gets non-core modules that support the Updatable Help feature.</span></span> <span data-ttu-id="c53eb-185">Команда использует параметр **ListAvailable** `Get-Module` командлета для получения всех модулей на компьютере.</span><span class="sxs-lookup"><span data-stu-id="c53eb-185">The command uses the **ListAvailable** parameter of the `Get-Module` cmdlet to get all modules on the computer.</span></span> <span data-ttu-id="c53eb-186">Оператор конвейера ( `|` ) отправляет модули в `Where-Object` командлет, который получает модули, имена которых не начинаются с Microsoft или PS, и имеют значение для свойства **HelpInfoURI** , которое сообщает PowerShell, где найти обновленные файлы справки для модуля.</span><span class="sxs-lookup"><span data-stu-id="c53eb-186">A pipeline operator (`|`) sends the modules to the `Where-Object` cmdlet, which gets modules whose names do not begin with Microsoft or PS, and have a value for the **HelpInfoURI** property, which tells PowerShell where to find updated help files for the module.</span></span> <span data-ttu-id="c53eb-187">Операторы сравнения соединены логическим оператором **и** .</span><span class="sxs-lookup"><span data-stu-id="c53eb-187">The comparison statements are connected by the **And** logical operator.</span></span>

<span data-ttu-id="c53eb-188">В примере используется формат команды блока сценария.</span><span class="sxs-lookup"><span data-stu-id="c53eb-188">The example uses the script block command format.</span></span> <span data-ttu-id="c53eb-189">Логические операторы, такие как **и** и **или**, допустимы только в блоках скриптов.</span><span class="sxs-lookup"><span data-stu-id="c53eb-189">Logical operators, such as **And** and **Or**, are valid only in script blocks.</span></span> <span data-ttu-id="c53eb-190">Их нельзя использовать в формате инструкции сравнения `Where-Object` команды.</span><span class="sxs-lookup"><span data-stu-id="c53eb-190">You cannot use them in the comparison statement format of a `Where-Object` command.</span></span>

- <span data-ttu-id="c53eb-191">Дополнительные сведения о логических операторах PowerShell см. в разделе [about_Logical_Operators](./About/about_logical_operators.md).</span><span class="sxs-lookup"><span data-stu-id="c53eb-191">For more information about PowerShell logical operators, see [about_Logical_Operators](./About/about_logical_operators.md).</span></span>
- <span data-ttu-id="c53eb-192">Дополнительные сведения о функции обновляемой справки см. в разделе [about_Updatable_Help](./About/about_Updatable_Help.md).</span><span class="sxs-lookup"><span data-stu-id="c53eb-192">For more information about the Updatable Help feature, see [about_Updatable_Help](./About/about_Updatable_Help.md).</span></span>

## <span data-ttu-id="c53eb-193">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c53eb-193">PARAMETERS</span></span>

### <span data-ttu-id="c53eb-194">-Кконтаинс</span><span class="sxs-lookup"><span data-stu-id="c53eb-194">-CContains</span></span>

<span data-ttu-id="c53eb-195">Указывает, что этот командлет получает объекты из коллекции, если значение свойства объекта является точным соответствием для указанного значения.</span><span class="sxs-lookup"><span data-stu-id="c53eb-195">Indicates that this cmdlet gets objects from a collection if the property value of the object is an exact match for the specified value.</span></span> <span data-ttu-id="c53eb-196">В этой операции учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="c53eb-196">This operation is case-sensitive.</span></span>

<span data-ttu-id="c53eb-197">Пример: `Get-Process | where ProcessName -CContains "svchost"`</span><span class="sxs-lookup"><span data-stu-id="c53eb-197">For example: `Get-Process | where ProcessName -CContains "svchost"`</span></span>

<span data-ttu-id="c53eb-198">**Кконтаинс** ссылается на коллекцию значений и имеет значение true, если коллекция содержит элемент, который является точным соответствием для указанного значения.</span><span class="sxs-lookup"><span data-stu-id="c53eb-198">**CContains** refers to a collection of values and is true if the collection contains an item that is an exact match for the specified value.</span></span> <span data-ttu-id="c53eb-199">Если входные данные являются одним объектом, PowerShell преобразует его в коллекцию одного объекта.</span><span class="sxs-lookup"><span data-stu-id="c53eb-199">If the input is a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="c53eb-200">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="c53eb-200">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="c53eb-201">-ЦЕК</span><span class="sxs-lookup"><span data-stu-id="c53eb-201">-CEQ</span></span>

<span data-ttu-id="c53eb-202">Указывает, что этот командлет получает объекты, если значение свойства совпадает с указанным значением.</span><span class="sxs-lookup"><span data-stu-id="c53eb-202">Indicates that this cmdlet gets objects if the property value is the same as the specified value.</span></span>
<span data-ttu-id="c53eb-203">В этой операции учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="c53eb-203">This operation is case-sensitive.</span></span>

<span data-ttu-id="c53eb-204">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="c53eb-204">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="c53eb-205">-CGE</span><span class="sxs-lookup"><span data-stu-id="c53eb-205">-CGE</span></span>

<span data-ttu-id="c53eb-206">Указывает, что этот командлет получает объекты, если значение свойства больше или равно указанному значению.</span><span class="sxs-lookup"><span data-stu-id="c53eb-206">Indicates that this cmdlet gets objects if the property value is greater than or equal to the specified value.</span></span> <span data-ttu-id="c53eb-207">В этой операции учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="c53eb-207">This operation is case-sensitive.</span></span>

<span data-ttu-id="c53eb-208">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="c53eb-208">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="c53eb-209">-КГТ</span><span class="sxs-lookup"><span data-stu-id="c53eb-209">-CGT</span></span>

<span data-ttu-id="c53eb-210">Указывает, что этот командлет получает объекты, если значение свойства больше указанного значения.</span><span class="sxs-lookup"><span data-stu-id="c53eb-210">Indicates that this cmdlet gets objects if the property value is greater than the specified value.</span></span>
<span data-ttu-id="c53eb-211">В этой операции учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="c53eb-211">This operation is case-sensitive.</span></span>

<span data-ttu-id="c53eb-212">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="c53eb-212">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="c53eb-213">-CIn</span><span class="sxs-lookup"><span data-stu-id="c53eb-213">-CIn</span></span>

<span data-ttu-id="c53eb-214">Указывает, что этот командлет получает объекты, если значение свойства включает указанное значение.</span><span class="sxs-lookup"><span data-stu-id="c53eb-214">Indicates that this cmdlet gets objects if the property value includes the specified value.</span></span> <span data-ttu-id="c53eb-215">В этой операции учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="c53eb-215">This operation is case-sensitive.</span></span>

<span data-ttu-id="c53eb-216">Пример: `Get-Process | where -Value "svchost" -CIn ProcessName`</span><span class="sxs-lookup"><span data-stu-id="c53eb-216">For example: `Get-Process | where -Value "svchost" -CIn ProcessName`</span></span>

<span data-ttu-id="c53eb-217">**CIn** напоминает **кконтаинс**, за исключением того, что позиции свойства и значения реверсируются.</span><span class="sxs-lookup"><span data-stu-id="c53eb-217">**CIn** resembles **CContains**, except that the property and value positions are reversed.</span></span> <span data-ttu-id="c53eb-218">Например обе следующие инструкции верны.</span><span class="sxs-lookup"><span data-stu-id="c53eb-218">For example, the following statements are both true.</span></span>

`"abc", "def" -CContains "abc"`

`"abc" -CIn "abc", "def"`

<span data-ttu-id="c53eb-219">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="c53eb-219">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="c53eb-220">-CLE</span><span class="sxs-lookup"><span data-stu-id="c53eb-220">-CLE</span></span>

<span data-ttu-id="c53eb-221">Указывает, что этот командлет получает объекты, если значение свойства меньше или равно указанному значению.</span><span class="sxs-lookup"><span data-stu-id="c53eb-221">Indicates that this cmdlet gets objects if the property value is less-than or equal to the specified value.</span></span> <span data-ttu-id="c53eb-222">В этой операции учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="c53eb-222">This operation is case-sensitive.</span></span>

<span data-ttu-id="c53eb-223">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="c53eb-223">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="c53eb-224">-Клике</span><span class="sxs-lookup"><span data-stu-id="c53eb-224">-CLike</span></span>

<span data-ttu-id="c53eb-225">Указывает, что этот командлет получает объекты, если значение свойства соответствует значению, включающему символы-шаблоны.</span><span class="sxs-lookup"><span data-stu-id="c53eb-225">Indicates that this cmdlet gets objects if the property value matches a value that includes wildcard characters.</span></span> <span data-ttu-id="c53eb-226">В этой операции учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="c53eb-226">This operation is case-sensitive.</span></span>

<span data-ttu-id="c53eb-227">Пример: `Get-Process | where ProcessName -CLike "*host"`</span><span class="sxs-lookup"><span data-stu-id="c53eb-227">For example: `Get-Process | where ProcessName -CLike "*host"`</span></span>

<span data-ttu-id="c53eb-228">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="c53eb-228">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="c53eb-229">— Средство регистрации звонков</span><span class="sxs-lookup"><span data-stu-id="c53eb-229">-CLT</span></span>

<span data-ttu-id="c53eb-230">Указывает, что этот командлет получает объекты, если значение свойства меньше указанного значения.</span><span class="sxs-lookup"><span data-stu-id="c53eb-230">Indicates that this cmdlet gets objects if the property value is less-than the specified value.</span></span> <span data-ttu-id="c53eb-231">В этой операции учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="c53eb-231">This operation is case-sensitive.</span></span>

<span data-ttu-id="c53eb-232">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="c53eb-232">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="c53eb-233">-CMatch</span><span class="sxs-lookup"><span data-stu-id="c53eb-233">-CMatch</span></span>

<span data-ttu-id="c53eb-234">Указывает, что этот командлет получает объекты, если значение свойства соответствует указанному регулярному выражению.</span><span class="sxs-lookup"><span data-stu-id="c53eb-234">Indicates that this cmdlet gets objects if the property value matches the specified regular expression.</span></span> <span data-ttu-id="c53eb-235">В этой операции учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="c53eb-235">This operation is case-sensitive.</span></span> <span data-ttu-id="c53eb-236">Если входные данные скалярны, сопоставленное значение сохраняется в `$Matches` автоматической переменной.</span><span class="sxs-lookup"><span data-stu-id="c53eb-236">When the input is scalar, the matched value is saved in `$Matches` automatic variable.</span></span>

<span data-ttu-id="c53eb-237">Пример: `Get-Process | where ProcessName -CMatch "Shell"`</span><span class="sxs-lookup"><span data-stu-id="c53eb-237">For example: `Get-Process | where ProcessName -CMatch "Shell"`</span></span>

<span data-ttu-id="c53eb-238">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="c53eb-238">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="c53eb-239">-CNE</span><span class="sxs-lookup"><span data-stu-id="c53eb-239">-CNE</span></span>

<span data-ttu-id="c53eb-240">Указывает, что этот командлет получает объекты, если значение свойства отличается от указанного значения.</span><span class="sxs-lookup"><span data-stu-id="c53eb-240">Indicates that this cmdlet gets objects if the property value is different than the specified value.</span></span>
<span data-ttu-id="c53eb-241">В этой операции учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="c53eb-241">This operation is case-sensitive.</span></span>

<span data-ttu-id="c53eb-242">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="c53eb-242">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="c53eb-243">-Кнотконтаинс</span><span class="sxs-lookup"><span data-stu-id="c53eb-243">-CNotContains</span></span>

<span data-ttu-id="c53eb-244">Указывает, что этот командлет получает объекты, если значение свойства объекта не является точным соответствием для указанного значения.</span><span class="sxs-lookup"><span data-stu-id="c53eb-244">Indicates that this cmdlet gets objects if the property value of the object is not an exact match for the specified value.</span></span> <span data-ttu-id="c53eb-245">В этой операции учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="c53eb-245">This operation is case-sensitive.</span></span>

<span data-ttu-id="c53eb-246">Пример: `Get-Process | where ProcessName -CNotContains "svchost"`</span><span class="sxs-lookup"><span data-stu-id="c53eb-246">For example: `Get-Process | where ProcessName -CNotContains "svchost"`</span></span>

<span data-ttu-id="c53eb-247">**NotContains** и **кнотконтаинс** ссылаются на коллекцию значений и имеют значение true, если коллекция не содержит элементов, которые точно соответствуют заданному значению.</span><span class="sxs-lookup"><span data-stu-id="c53eb-247">**NotContains** and **CNotContains** refer to a collection of values and are true when the collection does not contains any items that are an exact match for the specified value.</span></span> <span data-ttu-id="c53eb-248">Если входные данные являются одним объектом, PowerShell преобразует его в коллекцию одного объекта.</span><span class="sxs-lookup"><span data-stu-id="c53eb-248">If the input is a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="c53eb-249">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="c53eb-249">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="c53eb-250">-Кнотин</span><span class="sxs-lookup"><span data-stu-id="c53eb-250">-CNotIn</span></span>

<span data-ttu-id="c53eb-251">Указывает, что этот командлет получает объекты, если значение свойства не является точным соответствием для указанного значения.</span><span class="sxs-lookup"><span data-stu-id="c53eb-251">Indicates that this cmdlet gets objects if the property value is not an exact match for the specified value.</span></span> <span data-ttu-id="c53eb-252">В этой операции учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="c53eb-252">This operation is case-sensitive.</span></span>

<span data-ttu-id="c53eb-253">Пример: `Get-Process | where -Value "svchost" -CNotIn -Property ProcessName`</span><span class="sxs-lookup"><span data-stu-id="c53eb-253">For example: `Get-Process | where -Value "svchost" -CNotIn -Property ProcessName`</span></span>

<span data-ttu-id="c53eb-254">Операторы **NotIn** и **Кнотин** похожи на **NotContains** и **кнотконтаинс**, за исключением того, что позиции свойств и значений реверсируются.</span><span class="sxs-lookup"><span data-stu-id="c53eb-254">**NotIn** and **CNotIn** operators resemble **NotContains** and **CNotContains**, except that the property and value positions are reversed.</span></span> <span data-ttu-id="c53eb-255">Например, обе следующие инструкции верны.</span><span class="sxs-lookup"><span data-stu-id="c53eb-255">For example, the following statements are true.</span></span>

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

### <span data-ttu-id="c53eb-256">-Кнотлике</span><span class="sxs-lookup"><span data-stu-id="c53eb-256">-CNotLike</span></span>

<span data-ttu-id="c53eb-257">Указывает, что этот командлет получает объекты, если значение свойства не соответствует значению, включающему символы-шаблоны.</span><span class="sxs-lookup"><span data-stu-id="c53eb-257">Indicates that this cmdlet gets objects if the property value does not match a value that includes wildcard characters.</span></span> <span data-ttu-id="c53eb-258">В этой операции учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="c53eb-258">This operation is case-sensitive.</span></span>

<span data-ttu-id="c53eb-259">Пример: `Get-Process | where ProcessName -CNotLike "*host"`</span><span class="sxs-lookup"><span data-stu-id="c53eb-259">For example: `Get-Process | where ProcessName -CNotLike "*host"`</span></span>

<span data-ttu-id="c53eb-260">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="c53eb-260">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="c53eb-261">-Кнотматч</span><span class="sxs-lookup"><span data-stu-id="c53eb-261">-CNotMatch</span></span>

<span data-ttu-id="c53eb-262">Указывает, что этот командлет получает объекты, если значение свойства не совпадает с указанным регулярным выражением.</span><span class="sxs-lookup"><span data-stu-id="c53eb-262">Indicates that this cmdlet gets objects if the property value does not match the specified regular expression.</span></span> <span data-ttu-id="c53eb-263">В этой операции учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="c53eb-263">This operation is case-sensitive.</span></span> <span data-ttu-id="c53eb-264">Если входные данные скалярны, сопоставленное значение сохраняется в `$Matches` автоматической переменной.</span><span class="sxs-lookup"><span data-stu-id="c53eb-264">When the input is scalar, the matched value is saved in `$Matches` automatic variable.</span></span>

<span data-ttu-id="c53eb-265">Пример: `Get-Process | where ProcessName -CNotMatch "Shell"`</span><span class="sxs-lookup"><span data-stu-id="c53eb-265">For example: `Get-Process | where ProcessName -CNotMatch "Shell"`</span></span>

<span data-ttu-id="c53eb-266">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="c53eb-266">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="c53eb-267">— Содержит</span><span class="sxs-lookup"><span data-stu-id="c53eb-267">-Contains</span></span>

<span data-ttu-id="c53eb-268">Указывает, что этот командлет получает объекты, если какой-либо элемент в значении свойства объекта является точным соответствием для указанного значения.</span><span class="sxs-lookup"><span data-stu-id="c53eb-268">Indicates that this cmdlet gets objects if any item in the property value of the object is an exact match for the specified value.</span></span>

<span data-ttu-id="c53eb-269">Пример: `Get-Process | where ProcessName -Contains "Svchost"`</span><span class="sxs-lookup"><span data-stu-id="c53eb-269">For example: `Get-Process | where ProcessName -Contains "Svchost"`</span></span>

<span data-ttu-id="c53eb-270">Если значение свойства содержит один объект, PowerShell преобразует его в коллекцию одного объекта.</span><span class="sxs-lookup"><span data-stu-id="c53eb-270">If the property value contains a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="c53eb-271">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="c53eb-271">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="c53eb-272">-EQ</span><span class="sxs-lookup"><span data-stu-id="c53eb-272">-EQ</span></span>

<span data-ttu-id="c53eb-273">Указывает, что этот командлет получает объекты, если значение свойства совпадает с указанным значением.</span><span class="sxs-lookup"><span data-stu-id="c53eb-273">Indicates that this cmdlet gets objects if the property value is the same as the specified value.</span></span>

<span data-ttu-id="c53eb-274">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="c53eb-274">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="c53eb-275">-FilterScript представляет собой</span><span class="sxs-lookup"><span data-stu-id="c53eb-275">-FilterScript</span></span>

<span data-ttu-id="c53eb-276">Задает блок сценария, который используется для фильтрации объектов.</span><span class="sxs-lookup"><span data-stu-id="c53eb-276">Specifies the script block that is used to filter the objects.</span></span> <span data-ttu-id="c53eb-277">Заключите блок скрипта в фигурные скобки ( `{}` ).</span><span class="sxs-lookup"><span data-stu-id="c53eb-277">Enclose the script block in braces (`{}`).</span></span>

<span data-ttu-id="c53eb-278">Имя параметра, **FilterScript представляет собой**, является необязательным.</span><span class="sxs-lookup"><span data-stu-id="c53eb-278">The parameter name, **FilterScript**, is optional.</span></span>

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

### <span data-ttu-id="c53eb-279">-GE</span><span class="sxs-lookup"><span data-stu-id="c53eb-279">-GE</span></span>

<span data-ttu-id="c53eb-280">Указывает, что этот командлет получает объекты, если значение свойства больше или равно указанному значению.</span><span class="sxs-lookup"><span data-stu-id="c53eb-280">Indicates that this cmdlet gets objects if the property value is greater than or equal to the specified value.</span></span>

<span data-ttu-id="c53eb-281">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="c53eb-281">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="c53eb-282">-GT</span><span class="sxs-lookup"><span data-stu-id="c53eb-282">-GT</span></span>

<span data-ttu-id="c53eb-283">Указывает, что этот командлет получает объекты, если значение свойства больше указанного значения.</span><span class="sxs-lookup"><span data-stu-id="c53eb-283">Indicates that this cmdlet gets objects if the property value is greater than the specified value.</span></span>

<span data-ttu-id="c53eb-284">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="c53eb-284">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="c53eb-285">— В</span><span class="sxs-lookup"><span data-stu-id="c53eb-285">-In</span></span>

<span data-ttu-id="c53eb-286">Указывает, что этот командлет получает объекты, если значение свойства совпадает с любым из указанных значений.</span><span class="sxs-lookup"><span data-stu-id="c53eb-286">Indicates that this cmdlet gets objects if the property value matches any of the specified values.</span></span>
<span data-ttu-id="c53eb-287">Пример:</span><span class="sxs-lookup"><span data-stu-id="c53eb-287">For example:</span></span>

`Get-Process | where -Property ProcessName -in -Value "Svchost", "TaskHost", "WsmProvHost"`

<span data-ttu-id="c53eb-288">Если значение параметра **value** является одним объектом, PowerShell преобразует его в коллекцию одного объекта.</span><span class="sxs-lookup"><span data-stu-id="c53eb-288">If the value of the **Value** parameter is a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="c53eb-289">Если значение свойства объекта является массивом, PowerShell использует ссылочное равенство для определения совпадения.</span><span class="sxs-lookup"><span data-stu-id="c53eb-289">If the property value of an object is an array, PowerShell uses reference equality to determine a match.</span></span> <span data-ttu-id="c53eb-290">`Where-Object` Возвращает объект только в том случае, если значение параметра **Property** и любое значение **value** являются одним и тем же экземпляром объекта.</span><span class="sxs-lookup"><span data-stu-id="c53eb-290">`Where-Object` returns the object only if the value of the **Property** parameter and any value of **Value** are the same instance of an object.</span></span>

<span data-ttu-id="c53eb-291">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="c53eb-291">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="c53eb-292">-InputObject</span><span class="sxs-lookup"><span data-stu-id="c53eb-292">-InputObject</span></span>

<span data-ttu-id="c53eb-293">Задает объекты для фильтрации.</span><span class="sxs-lookup"><span data-stu-id="c53eb-293">Specifies the objects to be filtered.</span></span> <span data-ttu-id="c53eb-294">Также можно передать объекты в `Where-Object` .</span><span class="sxs-lookup"><span data-stu-id="c53eb-294">You can also pipe the objects to `Where-Object`.</span></span>

<span data-ttu-id="c53eb-295">При использовании параметра **InputObject** с параметром `Where-Object` , а не с результатами команды трубопроводов в `Where-Object` значение **InputObject** рассматривается как один объект.</span><span class="sxs-lookup"><span data-stu-id="c53eb-295">When you use the **InputObject** parameter with `Where-Object`, instead of piping command results to `Where-Object`, the **InputObject** value is treated as a single object.</span></span> <span data-ttu-id="c53eb-296">Это справедливо, даже если значением является коллекция, которая является результатом команды, например `-InputObject (Get-Process)` .</span><span class="sxs-lookup"><span data-stu-id="c53eb-296">This is true even if the value is a collection that is the result of a command, such as `-InputObject (Get-Process)`.</span></span> <span data-ttu-id="c53eb-297">Поскольку **InputObject** не может возвращать отдельные свойства из массива или коллекции объектов, рекомендуется `Where-Object` использовать для фильтрации коллекции объектов для объектов, имеющих определенные значения в определенных свойствах, `Where-Object` в конвейере, как показано в примерах этого раздела.</span><span class="sxs-lookup"><span data-stu-id="c53eb-297">Because **InputObject** cannot return individual properties from an array or collection of objects, we recommend that, if you use `Where-Object` to filter a collection of objects for those objects that have specific values in defined properties, you use `Where-Object` in the pipeline, as shown in the examples in this topic.</span></span>

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

### <span data-ttu-id="c53eb-298">— Имеет</span><span class="sxs-lookup"><span data-stu-id="c53eb-298">-Is</span></span>

<span data-ttu-id="c53eb-299">Указывает, что этот командлет получает объекты, если значение свойства является экземпляром указанного типа .NET.</span><span class="sxs-lookup"><span data-stu-id="c53eb-299">Indicates that this cmdlet gets objects if the property value is an instance of the specified .NET type.</span></span> <span data-ttu-id="c53eb-300">Заключите имя типа в квадратные скобки.</span><span class="sxs-lookup"><span data-stu-id="c53eb-300">Enclose the type name in square brackets.</span></span>

<span data-ttu-id="c53eb-301">Например: `Get-Process | where StartTime -Is [DateTime]`</span><span class="sxs-lookup"><span data-stu-id="c53eb-301">For example, `Get-Process | where StartTime -Is [DateTime]`</span></span>

<span data-ttu-id="c53eb-302">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="c53eb-302">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="c53eb-303">-IsNot</span><span class="sxs-lookup"><span data-stu-id="c53eb-303">-IsNot</span></span>

<span data-ttu-id="c53eb-304">Указывает, что этот командлет получает объекты, если значение свойства не является экземпляром указанного типа .NET.</span><span class="sxs-lookup"><span data-stu-id="c53eb-304">Indicates that this cmdlet gets objects if the property value is not an instance of the specified .NET type.</span></span>

<span data-ttu-id="c53eb-305">Например: `Get-Process | where StartTime -IsNot [DateTime]`</span><span class="sxs-lookup"><span data-stu-id="c53eb-305">For example, `Get-Process | where StartTime -IsNot [DateTime]`</span></span>

<span data-ttu-id="c53eb-306">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="c53eb-306">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="c53eb-307">-LE</span><span class="sxs-lookup"><span data-stu-id="c53eb-307">-LE</span></span>

<span data-ttu-id="c53eb-308">Указывает, что этот командлет получает объекты, если значение свойства меньше или равно указанному значению.</span><span class="sxs-lookup"><span data-stu-id="c53eb-308">Indicates that this cmdlet gets objects if the property value is less than or equal to the specified value.</span></span>

<span data-ttu-id="c53eb-309">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="c53eb-309">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="c53eb-310">-Like</span><span class="sxs-lookup"><span data-stu-id="c53eb-310">-Like</span></span>

<span data-ttu-id="c53eb-311">Указывает, что этот командлет получает объекты, если значение свойства соответствует значению, включающему символы-шаблоны.</span><span class="sxs-lookup"><span data-stu-id="c53eb-311">Indicates that this cmdlet gets objects if the property value matches a value that includes wildcard characters.</span></span>

<span data-ttu-id="c53eb-312">Пример: `Get-Process | where ProcessName -Like "*host"`</span><span class="sxs-lookup"><span data-stu-id="c53eb-312">For example: `Get-Process | where ProcessName -Like "*host"`</span></span>

<span data-ttu-id="c53eb-313">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="c53eb-313">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="c53eb-314">-LT</span><span class="sxs-lookup"><span data-stu-id="c53eb-314">-LT</span></span>

<span data-ttu-id="c53eb-315">Указывает, что этот командлет получает объекты, если значение свойства меньше указанного значения.</span><span class="sxs-lookup"><span data-stu-id="c53eb-315">Indicates that this cmdlet gets objects if the property value is less than the specified value.</span></span>

<span data-ttu-id="c53eb-316">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="c53eb-316">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="c53eb-317">-Match</span><span class="sxs-lookup"><span data-stu-id="c53eb-317">-Match</span></span>

<span data-ttu-id="c53eb-318">Указывает, что этот командлет получает объекты, если значение свойства соответствует указанному регулярному выражению.</span><span class="sxs-lookup"><span data-stu-id="c53eb-318">Indicates that this cmdlet gets objects if the property value matches the specified regular expression.</span></span> <span data-ttu-id="c53eb-319">Если входные данные скалярны, сопоставленное значение сохраняется в `$Matches` автоматической переменной.</span><span class="sxs-lookup"><span data-stu-id="c53eb-319">When the input is scalar, the matched value is saved in `$Matches` automatic variable.</span></span>

<span data-ttu-id="c53eb-320">Пример: `Get-Process | where ProcessName -Match "shell"`</span><span class="sxs-lookup"><span data-stu-id="c53eb-320">For example: `Get-Process | where ProcessName -Match "shell"`</span></span>

<span data-ttu-id="c53eb-321">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="c53eb-321">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="c53eb-322">-NE</span><span class="sxs-lookup"><span data-stu-id="c53eb-322">-NE</span></span>

<span data-ttu-id="c53eb-323">Указывает, что этот командлет получает объекты, если значение свойства отличается от указанного значения.</span><span class="sxs-lookup"><span data-stu-id="c53eb-323">Indicates that this cmdlet gets objects if the property value is different than the specified value.</span></span>

<span data-ttu-id="c53eb-324">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="c53eb-324">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="c53eb-325">— Не</span><span class="sxs-lookup"><span data-stu-id="c53eb-325">-Not</span></span>

<span data-ttu-id="c53eb-326">Указывает, что этот командлет получает объекты, если свойство не существует или имеет значение null или false.</span><span class="sxs-lookup"><span data-stu-id="c53eb-326">Indicates that this cmdlet gets objects if the property does not exist or has a value of null or false.</span></span>

<span data-ttu-id="c53eb-327">Пример: `Get-Service | where -Not "DependentServices"`</span><span class="sxs-lookup"><span data-stu-id="c53eb-327">For example: `Get-Service | where -Not "DependentServices"`</span></span>

<span data-ttu-id="c53eb-328">Этот параметр появился в Windows PowerShell 6,1.</span><span class="sxs-lookup"><span data-stu-id="c53eb-328">This parameter was introduced in Windows PowerShell 6.1.</span></span>

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

### <span data-ttu-id="c53eb-329">-NotContains</span><span class="sxs-lookup"><span data-stu-id="c53eb-329">-NotContains</span></span>

<span data-ttu-id="c53eb-330">Указывает, что этот командлет получает объекты, если ни один из элементов в значении свойства не является точным соответствием для указанного значения.</span><span class="sxs-lookup"><span data-stu-id="c53eb-330">Indicates that this cmdlet gets objects if none of the items in the property value is an exact match for the specified value.</span></span>

<span data-ttu-id="c53eb-331">Пример: `Get-Process | where ProcessName -NotContains "Svchost"`</span><span class="sxs-lookup"><span data-stu-id="c53eb-331">For example: `Get-Process | where ProcessName -NotContains "Svchost"`</span></span>

<span data-ttu-id="c53eb-332">**NotContains** ссылается на коллекцию значений и имеет значение true, если коллекция не содержит элементов, которые точно совпадают с указанным значением.</span><span class="sxs-lookup"><span data-stu-id="c53eb-332">**NotContains** refers to a collection of values and is true if the collection does not contain any items that are an exact match for the specified value.</span></span> <span data-ttu-id="c53eb-333">Если входные данные являются одним объектом, PowerShell преобразует его в коллекцию одного объекта.</span><span class="sxs-lookup"><span data-stu-id="c53eb-333">If the input is a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="c53eb-334">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="c53eb-334">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="c53eb-335">-NotIn</span><span class="sxs-lookup"><span data-stu-id="c53eb-335">-NotIn</span></span>

<span data-ttu-id="c53eb-336">Указывает, что этот командлет получает объекты, если значение свойства не является точным соответствием для любого из указанных значений.</span><span class="sxs-lookup"><span data-stu-id="c53eb-336">Indicates that this cmdlet gets objects if the property value is not an exact match for any of the specified values.</span></span>

<span data-ttu-id="c53eb-337">Пример: `Get-Process | where -Value "svchost" -NotIn -Property ProcessName`</span><span class="sxs-lookup"><span data-stu-id="c53eb-337">For example: `Get-Process | where -Value "svchost" -NotIn -Property ProcessName`</span></span>

<span data-ttu-id="c53eb-338">Если значение **value** является одним объектом, PowerShell преобразует его в коллекцию одного объекта.</span><span class="sxs-lookup"><span data-stu-id="c53eb-338">If the value of **Value** is a single object, PowerShell converts it to a collection of one object.</span></span>

<span data-ttu-id="c53eb-339">Если значение свойства объекта является массивом, PowerShell использует ссылочное равенство для определения совпадения.</span><span class="sxs-lookup"><span data-stu-id="c53eb-339">If the property value of an object is an array, PowerShell uses reference equality to determine a match.</span></span> <span data-ttu-id="c53eb-340">`Where-Object` Возвращает объект только в том случае, если значение **Свойства** и любое значение **значения** не являются одним и тем же экземпляром объекта.</span><span class="sxs-lookup"><span data-stu-id="c53eb-340">`Where-Object` returns the object only if the value of **Property** and any value of **Value** are not the same instance of an object.</span></span>

<span data-ttu-id="c53eb-341">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="c53eb-341">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="c53eb-342">-NotLike</span><span class="sxs-lookup"><span data-stu-id="c53eb-342">-NotLike</span></span>

<span data-ttu-id="c53eb-343">Указывает, что этот командлет получает объекты, если значение свойства не соответствует значению, включающему символы-шаблоны.</span><span class="sxs-lookup"><span data-stu-id="c53eb-343">Indicates that this cmdlet gets objects if the property value does not match a value that includes wildcard characters.</span></span>

<span data-ttu-id="c53eb-344">Пример: `Get-Process | where ProcessName -NotLike "*host"`</span><span class="sxs-lookup"><span data-stu-id="c53eb-344">For example: `Get-Process | where ProcessName -NotLike "*host"`</span></span>

<span data-ttu-id="c53eb-345">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="c53eb-345">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="c53eb-346">-NotMatch</span><span class="sxs-lookup"><span data-stu-id="c53eb-346">-NotMatch</span></span>

<span data-ttu-id="c53eb-347">Указывает, что этот командлет получает объекты, если значение свойства не совпадает с указанным регулярным выражением.</span><span class="sxs-lookup"><span data-stu-id="c53eb-347">Indicates that this cmdlet gets objects when the property value does not match the specified regular expression.</span></span> <span data-ttu-id="c53eb-348">Если входные данные скалярны, сопоставленное значение сохраняется в `$Matches` автоматической переменной.</span><span class="sxs-lookup"><span data-stu-id="c53eb-348">When the input is scalar, the matched value is saved in `$Matches` automatic variable.</span></span>

<span data-ttu-id="c53eb-349">Пример: `Get-Process | where ProcessName -NotMatch "PowerShell"`</span><span class="sxs-lookup"><span data-stu-id="c53eb-349">For example: `Get-Process | where ProcessName -NotMatch "PowerShell"`</span></span>

<span data-ttu-id="c53eb-350">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="c53eb-350">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="c53eb-351">-Property</span><span class="sxs-lookup"><span data-stu-id="c53eb-351">-Property</span></span>

<span data-ttu-id="c53eb-352">Задает имя свойства объекта.</span><span class="sxs-lookup"><span data-stu-id="c53eb-352">Specifies the name of an object property.</span></span> <span data-ttu-id="c53eb-353">Имя параметра, **свойство**, является необязательным.</span><span class="sxs-lookup"><span data-stu-id="c53eb-353">The parameter name, **Property**, is optional.</span></span>

<span data-ttu-id="c53eb-354">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="c53eb-354">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: EqualSet, LessOrEqualSet, CaseSensitiveEqualSet, NotEqualSet, CaseSensitiveNotEqualSet, GreaterThanSet, CaseSensitiveGreaterThanSet, LessThanSet, CaseSensitiveLessThanSet, GreaterOrEqualSet, CaseSensitiveGreaterOrEqualSet, CaseSensitiveLessOrEqualSet, LikeSet, CaseSensitiveLikeSet, NotLikeSet, CaseSensitiveNotLikeSet, MatchSet, CaseSensitiveMatchSet, NotMatchSet, CaseSensitiveNotMatchSet, ContainsSet, CaseSensitiveContainsSet, NotContainsSet, CaseSensitiveNotContainsSet, InSet, CaseSensitiveInSet, NotInSet, CaseSensitiveNotInSet, IsSet, IsNotSet, Not
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c53eb-355">-Value</span><span class="sxs-lookup"><span data-stu-id="c53eb-355">-Value</span></span>

<span data-ttu-id="c53eb-356">Задает значение свойства.</span><span class="sxs-lookup"><span data-stu-id="c53eb-356">Specifies a property value.</span></span> <span data-ttu-id="c53eb-357">Имя параметра, **значение** является необязательным.</span><span class="sxs-lookup"><span data-stu-id="c53eb-357">The parameter name, **Value**, is optional.</span></span> <span data-ttu-id="c53eb-358">Этот параметр принимает подстановочные знаки при использовании со следующими параметрами сравнения:</span><span class="sxs-lookup"><span data-stu-id="c53eb-358">This parameter accepts wildcard characters when used with the following comparison parameters:</span></span>

- <span data-ttu-id="c53eb-359">**клике**</span><span class="sxs-lookup"><span data-stu-id="c53eb-359">**CLike**</span></span>
- <span data-ttu-id="c53eb-360">**кнотлике**</span><span class="sxs-lookup"><span data-stu-id="c53eb-360">**CNotLike**</span></span>
- <span data-ttu-id="c53eb-361">**Например**</span><span class="sxs-lookup"><span data-stu-id="c53eb-361">**Like**</span></span>
- <span data-ttu-id="c53eb-362">**NotLike**</span><span class="sxs-lookup"><span data-stu-id="c53eb-362">**NotLike**</span></span>

<span data-ttu-id="c53eb-363">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="c53eb-363">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Object
Parameter Sets: EqualSet, LessOrEqualSet, CaseSensitiveEqualSet, NotEqualSet, CaseSensitiveNotEqualSet, GreaterThanSet, CaseSensitiveGreaterThanSet, LessThanSet, CaseSensitiveLessThanSet, GreaterOrEqualSet, CaseSensitiveGreaterOrEqualSet, CaseSensitiveLessOrEqualSet, LikeSet, CaseSensitiveLikeSet, NotLikeSet, CaseSensitiveNotLikeSet, MatchSet, CaseSensitiveMatchSet, NotMatchSet, CaseSensitiveNotMatchSet, ContainsSet, CaseSensitiveContainsSet, NotContainsSet, CaseSensitiveNotContainsSet, InSet, CaseSensitiveInSet, NotInSet, CaseSensitiveNotInSet, IsSet, IsNotSet
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="c53eb-364">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="c53eb-364">CommonParameters</span></span>

<span data-ttu-id="c53eb-365">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c53eb-365">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c53eb-366">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c53eb-366">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c53eb-367">Входные данные</span><span class="sxs-lookup"><span data-stu-id="c53eb-367">INPUTS</span></span>

### <span data-ttu-id="c53eb-368">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="c53eb-368">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="c53eb-369">Объекты можно передать в этот командлет по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="c53eb-369">You can pipe the objects to this cmdlet.</span></span>

## <span data-ttu-id="c53eb-370">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="c53eb-370">OUTPUTS</span></span>

### <span data-ttu-id="c53eb-371">Объект</span><span class="sxs-lookup"><span data-stu-id="c53eb-371">Object</span></span>

<span data-ttu-id="c53eb-372">Этот командлет возвращает выбранные элементы из набора входных объектов.</span><span class="sxs-lookup"><span data-stu-id="c53eb-372">This cmdlet returns selected items from the input object set.</span></span>

## <span data-ttu-id="c53eb-373">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="c53eb-373">NOTES</span></span>

<span data-ttu-id="c53eb-374">Начиная с Windows PowerShell 4,0, `Where` `ForEach` методы были добавлены для использования с коллекциями.</span><span class="sxs-lookup"><span data-stu-id="c53eb-374">Starting in Windows PowerShell 4.0, `Where` and `ForEach` methods were added for use with collections.</span></span>

<span data-ttu-id="c53eb-375">Дополнительные сведения об этих новых методах можно узнать здесь [about_arrays](./About/about_Arrays.md)</span><span class="sxs-lookup"><span data-stu-id="c53eb-375">You can read more about these new methods here [about_arrays](./About/about_Arrays.md)</span></span>

## <span data-ttu-id="c53eb-376">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="c53eb-376">RELATED LINKS</span></span>

[<span data-ttu-id="c53eb-377">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="c53eb-377">Compare-Object</span></span>](../Microsoft.PowerShell.Utility/Compare-Object.md)

[<span data-ttu-id="c53eb-378">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="c53eb-378">ForEach-Object</span></span>](ForEach-Object.md)

[<span data-ttu-id="c53eb-379">Group-Object</span><span class="sxs-lookup"><span data-stu-id="c53eb-379">Group-Object</span></span>](../Microsoft.PowerShell.Utility/Group-Object.md)

[<span data-ttu-id="c53eb-380">Measure-Object;</span><span class="sxs-lookup"><span data-stu-id="c53eb-380">Measure-Object</span></span>](../Microsoft.PowerShell.Utility/Measure-Object.md)

[<span data-ttu-id="c53eb-381">New-Object</span><span class="sxs-lookup"><span data-stu-id="c53eb-381">New-Object</span></span>](../Microsoft.PowerShell.Utility/New-Object.md)

[<span data-ttu-id="c53eb-382">Select-Object</span><span class="sxs-lookup"><span data-stu-id="c53eb-382">Select-Object</span></span>](../Microsoft.PowerShell.Utility/Select-Object.md)

[<span data-ttu-id="c53eb-383">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="c53eb-383">Sort-Object</span></span>](../Microsoft.PowerShell.Utility/Sort-Object.md)

[<span data-ttu-id="c53eb-384">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="c53eb-384">Tee-Object</span></span>](../Microsoft.PowerShell.Utility/Tee-Object.md)

