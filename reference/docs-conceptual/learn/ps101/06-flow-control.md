---
title: Управление потоком
description: PowerShell предоставляет методы создания циклов, принятия решений и логического управления потоком кода в скриптах.
ms.date: 06/02/2020
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
ms.openlocfilehash: 74595f8c6a5d4a49b05e72dd6bde1441fd2b464e
ms.sourcegitcommit: df5e6f032ee2d4b556d50406832732d2f7dc2502
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2021
ms.locfileid: "99601475"
---
# <a name="chapter-6---flow-control"></a><span data-ttu-id="daaf0-103">Глава 6. Управление потоком</span><span class="sxs-lookup"><span data-stu-id="daaf0-103">Chapter 6 - Flow control</span></span>

## <a name="scripting"></a><span data-ttu-id="daaf0-104">Написание сценариев</span><span class="sxs-lookup"><span data-stu-id="daaf0-104">Scripting</span></span>

<span data-ttu-id="daaf0-105">Когда вы переходите от написания однострочных элементов кода PowerShell к написанию сценариев, это может показаться намного сложнее, чем есть на самом деле.</span><span class="sxs-lookup"><span data-stu-id="daaf0-105">When you move from writing PowerShell one-liners to writing scripts, it sounds a lot more complicated than it really is.</span></span> <span data-ttu-id="daaf0-106">Сценарий — это всего лишь те же или похожие команды, которые вы можете запускать в интерактивном режиме в консоли PowerShell, если они не сохранены в виде файла `.PS1`.</span><span class="sxs-lookup"><span data-stu-id="daaf0-106">A script is nothing more than the same or similar commands that you would run interactively in the PowerShell console, except they're saved as a `.PS1` file.</span></span> <span data-ttu-id="daaf0-107">Существуют некоторые конструкции написания сценариев, которые вы можете использовать вместо командлета `ForEach-Object`, например цикл `foreach`.</span><span class="sxs-lookup"><span data-stu-id="daaf0-107">There are some scripting constructs that you may use such as a `foreach` loop instead of the `ForEach-Object` cmdlet.</span></span> <span data-ttu-id="daaf0-108">Эти различия могут ввести в заблуждение начинающих пользователей, особенно если они полагают, что `foreach` является конструкцией сценария и псевдонимом для командлета `ForEach-Object`.</span><span class="sxs-lookup"><span data-stu-id="daaf0-108">To beginners, the differences can be confusing especially when you consider that `foreach` is both a scripting construct and an alias for the `ForEach-Object` cmdlet.</span></span>

## <a name="looping"></a><span data-ttu-id="daaf0-109">Выполнение цикла</span><span class="sxs-lookup"><span data-stu-id="daaf0-109">Looping</span></span>

<span data-ttu-id="daaf0-110">Одно из основных преимуществ PowerShell состоит в следующем: если вы определили способ выполнения задачи для одного элемента, вы можете так же легко выполнить ее для нескольких сотен элементов.</span><span class="sxs-lookup"><span data-stu-id="daaf0-110">One of the great things about PowerShell is, once you figure out how to do something for one item, it's almost as easy to do the same task for hundreds of items.</span></span> <span data-ttu-id="daaf0-111">Достаточно пройтись в цикле по этим элементам, используя один из множества различных типов циклов в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="daaf0-111">Simply loop through the items using one of the many different types of loops in PowerShell.</span></span>

### <a name="foreach-object"></a><span data-ttu-id="daaf0-112">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="daaf0-112">ForEach-Object</span></span>

<span data-ttu-id="daaf0-113">`ForEach-Object` — это командлет для прохода по элементам в конвейере, например с помощью однострочных элементов кода PowerShell.</span><span class="sxs-lookup"><span data-stu-id="daaf0-113">`ForEach-Object` is a cmdlet for iterating through items in a pipeline such as with PowerShell one-liners.</span></span> <span data-ttu-id="daaf0-114">`ForEach-Object` осуществляет потоковую передачу объектов по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="daaf0-114">`ForEach-Object` streams the objects through the pipeline.</span></span>

<span data-ttu-id="daaf0-115">Хотя параметр **Module** для `Get-Command` принимает несколько значений в виде строк, он осуществляет это только через входные данные конвейера по имени свойства или через входные данные параметра.</span><span class="sxs-lookup"><span data-stu-id="daaf0-115">Although the **Module** parameter of `Get-Command` accepts multiple values that are strings, it only accepts them via pipeline input by property name or via parameter input.</span></span> <span data-ttu-id="daaf0-116">В следующем сценарии, если мне нужно передать две строки по значению в `Get-Command` для использования с параметром **Module**, я буду использовать командлет `ForEach-Object`.</span><span class="sxs-lookup"><span data-stu-id="daaf0-116">In the following scenario, if I want to pipe two strings by value to `Get-Command` for use with the **Module** parameter, I would need to use the `ForEach-Object` cmdlet.</span></span>

```powershell
'ActiveDirectory', 'SQLServer' |
   ForEach-Object {Get-Command -Module $_} |
     Group-Object -Property ModuleName -NoElement |
         Sort-Object -Property Count -Descending
```

```Output
Count Name
----- ----
  147 ActiveDirectory
   82 SqlServer
```

<span data-ttu-id="daaf0-117">В предыдущем примере текущим объектом является `$_`.</span><span class="sxs-lookup"><span data-stu-id="daaf0-117">In the previous example, `$_` is the current object.</span></span> <span data-ttu-id="daaf0-118">Начиная с PowerShell версии 3.0 `$PSItem` можно использовать вместо `$_`.</span><span class="sxs-lookup"><span data-stu-id="daaf0-118">Beginning with PowerShell version 3.0, `$PSItem` can be used instead of `$_`.</span></span> <span data-ttu-id="daaf0-119">Но я встречаюсь с тем, что самые опытные пользователи PowerShell все еще предпочитают использовать `$_`, так как он обеспечивает обратную и меньшую совместимость.</span><span class="sxs-lookup"><span data-stu-id="daaf0-119">But I find that most experienced PowerShell users still prefer using `$_` since it's backward compatible and less to type.</span></span>

<span data-ttu-id="daaf0-120">При использовании ключевого слова `foreach` вы должны сохранить все элементы в памяти, прежде чем по ним проходить, а это может быть нелегкой задачей, если не знать, с каким количеством элементов вы работаете.</span><span class="sxs-lookup"><span data-stu-id="daaf0-120">When using the `foreach` keyword, you must store all of the items in memory before iterating through them, which could be difficult if you don't know how many items you're working with.</span></span>

```powershell
$ComputerName = 'DC01', 'WEB01'
foreach ($Computer in $ComputerName) {
  Get-ADComputer -Identity $Computer
}
```

```Output
DistinguishedName : CN=DC01,OU=Domain Controllers,DC=mikefrobbins,DC=com
DNSHostName       : dc01.mikefrobbins.com
Enabled           : True
Name              : DC01
ObjectClass       : computer
ObjectGUID        : c38da20c-a484-469d-ba4c-bab3fb71ae8e
SamAccountName    : DC01$
SID               : S-1-5-21-2989741381-570885089-3319121794-1001
UserPrincipalName :

DistinguishedName : CN=WEB01,CN=Computers,DC=mikefrobbins,DC=com
DNSHostName       : web01.mikefrobbins.com
Enabled           : True
Name              : WEB01
ObjectClass       : computer
ObjectGUID        : 33aa530e-1e31-40d8-8c78-76a18b673c33
SamAccountName    : WEB01$
SID               : S-1-5-21-2989741381-570885089-3319121794-1107
UserPrincipalName :
```

<span data-ttu-id="daaf0-121">Цикл `foreach` или `ForEach-Object` нужно обязательно выполнить несколько раз,</span><span class="sxs-lookup"><span data-stu-id="daaf0-121">Many times a loop such as `foreach` or `ForEach-Object` is necessary.</span></span> <span data-ttu-id="daaf0-122">иначе вы получите сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="daaf0-122">Otherwise you'll receive an error message.</span></span>

```powershell
Get-ADComputer -Identity 'DC01', 'WEB01'
```

```Output
Get-ADComputer : Cannot convert 'System.Object[]' to the type
'Microsoft.ActiveDirectory.Management.ADComputer' required by parameter 'Identity'.
Specified method is not supported.
At line:1 char:26
+ Get-ADComputer -Identity 'DC01', 'WEB01'
+                          ```````````````
    + CategoryInfo          : InvalidArgument: (:) [Get-ADComputer], ParameterBindingExc
   eption
    + FullyQualifiedErrorId : CannotConvertArgument,Microsoft.ActiveDirectory.Management
   .Commands.GetADComputer
```

<span data-ttu-id="daaf0-123">В других случаях вы можете получить те же результаты, одновременно удаляя цикл.</span><span class="sxs-lookup"><span data-stu-id="daaf0-123">Other times, you can get the same results while eliminating the loop altogether.</span></span> <span data-ttu-id="daaf0-124">Чтобы разобраться с параметрами, сверьтесь со справкой по командлетам.</span><span class="sxs-lookup"><span data-stu-id="daaf0-124">Consult the cmdlet help to understand your options.</span></span>

```powershell
'DC01', 'WEB01' | Get-ADComputer
```

```Output
DistinguishedName : CN=DC01,OU=Domain Controllers,DC=mikefrobbins,DC=com
DNSHostName       : dc01.mikefrobbins.com
Enabled           : True
Name              : DC01
ObjectClass       : computer
ObjectGUID        : c38da20c-a484-469d-ba4c-bab3fb71ae8e
SamAccountName    : DC01$
SID               : S-1-5-21-2989741381-570885089-3319121794-1001
UserPrincipalName :

DistinguishedName : CN=WEB01,CN=Computers,DC=mikefrobbins,DC=com
DNSHostName       : web01.mikefrobbins.com
Enabled           : True
Name              : WEB01
ObjectClass       : computer
ObjectGUID        : 33aa530e-1e31-40d8-8c78-76a18b673c33
SamAccountName    : WEB01$
SID               : S-1-5-21-2989741381-570885089-3319121794-1107
UserPrincipalName :
```

<span data-ttu-id="daaf0-125">Как вы видите в предыдущих примерах, параметр **Identity** для `Get-ADComputer` принимает только одно значение, если оно предоставлено с помощью входных параметров, и при этом позволяет получить несколько элементов, если входные данные предоставляются через входные данные конвейера.</span><span class="sxs-lookup"><span data-stu-id="daaf0-125">As you can see in the previous examples, the **Identity** parameter for `Get-ADComputer` only accepts a single value when provided via parameter input, but it allows for multiple items when the input is provided via pipeline input.</span></span>

### <a name="for"></a><span data-ttu-id="daaf0-126">Для</span><span class="sxs-lookup"><span data-stu-id="daaf0-126">For</span></span>

<span data-ttu-id="daaf0-127">Цикл `for` выполняет итерацию до тех пор, пока заданное условие имеет значение "Истина".</span><span class="sxs-lookup"><span data-stu-id="daaf0-127">A `for` loop iterates while a specified condition is true.</span></span> <span data-ttu-id="daaf0-128">Цикл `for` я использую редко, но все же использую.</span><span class="sxs-lookup"><span data-stu-id="daaf0-128">The `for` loop is not something that I use often, but it does have its uses.</span></span>

```powershell
for ($i = 1; $i -lt 5; $i++) {
  Write-Output "Sleeping for $i seconds"
  Start-Sleep -Seconds $i
}
```

```Output
Sleeping for 1 seconds
Sleeping for 2 seconds
Sleeping for 3 seconds
Sleeping for 4 seconds
```

<span data-ttu-id="daaf0-129">В предыдущем примере цикл будет повторяться четыре раза, начиная с числа 1, и продолжит выполняться до тех пор, пока переменная счетчика `$i` не составит значение менее 5.</span><span class="sxs-lookup"><span data-stu-id="daaf0-129">In the previous example, the loop will iterate four times by starting off with the number one and continue as long as the counter variable `$i` is less than 5.</span></span> <span data-ttu-id="daaf0-130">Этот цикл будет бездействовать в течение всего 10 секунд.</span><span class="sxs-lookup"><span data-stu-id="daaf0-130">It will sleep for a total of 10 seconds.</span></span>

### <a name="do"></a><span data-ttu-id="daaf0-131">Как нужно</span><span class="sxs-lookup"><span data-stu-id="daaf0-131">Do</span></span>

<span data-ttu-id="daaf0-132">В PowerShell существуют два разных цикла `do`.</span><span class="sxs-lookup"><span data-stu-id="daaf0-132">There are two different `do` loops in PowerShell.</span></span> <span data-ttu-id="daaf0-133">Цикл `Do Until` выполняется до тех пор, пока заданное условие имеет значение "Ложь".</span><span class="sxs-lookup"><span data-stu-id="daaf0-133">`Do Until` runs while the specified condition is false.</span></span>

```powershell
$number = Get-Random -Minimum 1 -Maximum 10
do {
  $guess = Read-Host -Prompt "What's your guess?"
  if ($guess -lt $number) {
    Write-Output 'Too low!'
  }
  elseif ($guess -gt $number) {
    Write-Output 'Too high!'
  }
}
until ($guess -eq $number)
```

```Output
What's your guess?: 1
Too low!
What's your guess?: 2
Too low!
What's your guess?: 3
```

<span data-ttu-id="daaf0-134">В предыдущем примере показана игра с цифрами, которая будет продолжаться до тех пор, пока значение, которое вы выдаете, не будет равняться тому же числу, которое было создано командлетом `Get-Random`.</span><span class="sxs-lookup"><span data-stu-id="daaf0-134">The previous example is a numbers game that continues until the value you guess equals the same number that the `Get-Random` cmdlet generated.</span></span>

<span data-ttu-id="daaf0-135">Цикл `Do While` — полная противоположность.</span><span class="sxs-lookup"><span data-stu-id="daaf0-135">`Do While` is just the opposite.</span></span> <span data-ttu-id="daaf0-136">Он выполняется до тех пор, пока заданное условие не примет значение "Истина".</span><span class="sxs-lookup"><span data-stu-id="daaf0-136">It runs as long as the specified condition evaluates to true.</span></span>

```powershell
$number = Get-Random -Minimum 1 -Maximum 10
do {
  $guess = Read-Host -Prompt "What's your guess?"
  if ($guess -lt $number) {
    Write-Output 'Too low!'
  } elseif ($guess -gt $number) {
    Write-Output 'Too high!'
  }
}
while ($guess -ne $number)
```

```Output
What's your guess?: 1
Too low!
What's your guess?: 2
Too low!
What's your guess?: 3
Too low!
What's your guess?: 4
```

<span data-ttu-id="daaf0-137">Аналогичные результаты можно получить с помощью цикла `Do While`, изменив условие проверки на значение "Не равно".</span><span class="sxs-lookup"><span data-stu-id="daaf0-137">The same results are achieved with a `Do While` loop by reversing the test condition to not equals.</span></span>

<span data-ttu-id="daaf0-138">Циклы `Do` всегда выполняются не менее одного раза, так как заданное условие вычисляется в конце цикла.</span><span class="sxs-lookup"><span data-stu-id="daaf0-138">`Do` loops always run at least once because the condition is evaluated at the end of the loop.</span></span>

### <a name="while"></a><span data-ttu-id="daaf0-139">While</span><span class="sxs-lookup"><span data-stu-id="daaf0-139">While</span></span>

<span data-ttu-id="daaf0-140">Цикл `Do While`, как и цикл `While`, выполняется до тех пор, пока заданное условие имеет значение "Истина".</span><span class="sxs-lookup"><span data-stu-id="daaf0-140">Similar to the `Do While` loop, a `While` loop runs as long as the specified condition is true.</span></span> <span data-ttu-id="daaf0-141">При этом различие состоит в том, что цикл `While` принимает условие в верхней части цикла перед выполнением любого кода.</span><span class="sxs-lookup"><span data-stu-id="daaf0-141">The difference however, is that a `While` loop evaluates the condition at the top of the loop before any code is run.</span></span> <span data-ttu-id="daaf0-142">Поэтому этот цикл не выполняется, если условие принимает значение "Ложь".</span><span class="sxs-lookup"><span data-stu-id="daaf0-142">So it doesn't run if the condition evaluates to false.</span></span>

```powershell
$date = Get-Date -Date 'November 22'
while ($date.DayOfWeek -ne 'Thursday') {
  $date = $date.AddDays(1)
}
Write-Output $date
```

```Output
Thursday, November 23, 2017 12:00:00 AM
```

<span data-ttu-id="daaf0-143">В предыдущем примере вычисляется, на какой день недели приходится День благодарения в США.</span><span class="sxs-lookup"><span data-stu-id="daaf0-143">The previous example calculates what day Thanksgiving Day is on in the United States.</span></span> <span data-ttu-id="daaf0-144">Этот день всегда приходится на четвертый четверг ноября.</span><span class="sxs-lookup"><span data-stu-id="daaf0-144">It's always on the fourth Thursday of November.</span></span> <span data-ttu-id="daaf0-145">Поэтому цикл начинается с 22-го дня ноября и добавляет один день, когда день недели не равен четвергу.</span><span class="sxs-lookup"><span data-stu-id="daaf0-145">So the loop starts with the 22nd day of November and adds a day while the day of the week isn't equal to Thursday.</span></span> <span data-ttu-id="daaf0-146">Если на 22-е число выпадает четверг, цикл не выполняется.</span><span class="sxs-lookup"><span data-stu-id="daaf0-146">If the 22nd is a Thursday, the loop doesn't run at all.</span></span>

## <a name="break-continue-and-return"></a><span data-ttu-id="daaf0-147">Инструкции "Прервать", "Продолжить" и "Вернуть"</span><span class="sxs-lookup"><span data-stu-id="daaf0-147">Break, Continue, and Return</span></span>

<span data-ttu-id="daaf0-148">Инструкция `Break` используется для прерывания цикла.</span><span class="sxs-lookup"><span data-stu-id="daaf0-148">`Break` is designed to break out of a loop.</span></span> <span data-ttu-id="daaf0-149">Кроме того, она часто используется с инструкцией `switch`.</span><span class="sxs-lookup"><span data-stu-id="daaf0-149">It's also commonly used with the `switch` statement.</span></span>

```powershell
for ($i = 1; $i -lt 5; $i++) {
  Write-Output "Sleeping for $i seconds"
  Start-Sleep -Seconds $i
  break
}
```

```Output
Sleeping for 1 seconds
```

<span data-ttu-id="daaf0-150">Инструкция `break`, показанная в предыдущем примере, приводит к выходу цикла в первой итерации.</span><span class="sxs-lookup"><span data-stu-id="daaf0-150">The `break` statement shown in the previous example causes the loop to exit on the first iteration.</span></span>

<span data-ttu-id="daaf0-151">Инструкция "Продолжить" позволяет перейти к следующей итерации цикла.</span><span class="sxs-lookup"><span data-stu-id="daaf0-151">Continue is designed to skip to the next iteration of a loop.</span></span>

```powershell
while ($i -lt 5) {
  $i += 1
  if ($i -eq 3) {
    continue
  }
  Write-Output $i
}
```

```Output
1
2
4
5
```

<span data-ttu-id="daaf0-152">В предыдущем примере выводятся числа 1, 2, 4 и 5.</span><span class="sxs-lookup"><span data-stu-id="daaf0-152">The previous example will output the numbers 1, 2, 4, and 5.</span></span> <span data-ttu-id="daaf0-153">В нем исключается число 3 и выполняется переход к следующей итерации цикла.</span><span class="sxs-lookup"><span data-stu-id="daaf0-153">It skips number 3 and continues with the next iteration of the loop.</span></span> <span data-ttu-id="daaf0-154">Инструкция `break`, как и `continue`, прерывает цикл, только если это не текущая итерация.</span><span class="sxs-lookup"><span data-stu-id="daaf0-154">Similar to `break`, `continue` breaks out of the loop except only for the current iteration.</span></span> <span data-ttu-id="daaf0-155">Затем процесс переходит к следующей итерации, а не к прерыванию и остановке цикла.</span><span class="sxs-lookup"><span data-stu-id="daaf0-155">Execution continues with the next iteration instead of breaking out of the loop and stopping.</span></span>

<span data-ttu-id="daaf0-156">Инструкция "Вернуть" позволяет выйти из существующей области.</span><span class="sxs-lookup"><span data-stu-id="daaf0-156">Return is designed to exit out of the existing scope.</span></span>

```powershell
$number = 1..10
foreach ($n in $number) {
  if ($n -ge 4) {
    Return $n
  }
}
```

```Output
4
```

<span data-ttu-id="daaf0-157">Заметьте, что в предыдущем примере при возврате выводится первый результат, а затем выполняется выход из цикла.</span><span class="sxs-lookup"><span data-stu-id="daaf0-157">Notice that in the previous example, return outputs the first result and then exists out of the loop.</span></span> <span data-ttu-id="daaf0-158">Более подробное описание инструкции о результатах можно найти в одной из моих статей блога. [The PowerShell return keyword][]</span><span class="sxs-lookup"><span data-stu-id="daaf0-158">A more thorough explanation of the result statement can be found in one of my blog articles: ["The PowerShell return keyword"][].</span></span>

## <a name="summary"></a><span data-ttu-id="daaf0-159">Сводка</span><span class="sxs-lookup"><span data-stu-id="daaf0-159">Summary</span></span>

<span data-ttu-id="daaf0-160">В этой главе вы узнали о разных типах циклов, существующих в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="daaf0-160">In this chapter, you've learned about the different types of loops that exist in PowerShell.</span></span>

## <a name="review"></a><span data-ttu-id="daaf0-161">Просмотр</span><span class="sxs-lookup"><span data-stu-id="daaf0-161">Review</span></span>

1. <span data-ttu-id="daaf0-162">Чем отличается командлет `ForEach-Object` от конструкции сценариев foreach?</span><span class="sxs-lookup"><span data-stu-id="daaf0-162">What is the difference in the `ForEach-Object` cmdlet and the foreach scripting construct?</span></span>
1. <span data-ttu-id="daaf0-163">В чем основное преимущество использования цикла While от цикла Do while или Do Until?</span><span class="sxs-lookup"><span data-stu-id="daaf0-163">What is the primary advantage of using a While loop instead of a Do While or Do Until loop.</span></span>
1. <span data-ttu-id="daaf0-164">Как различаются инструкции "Прервать" и "Продолжить"?</span><span class="sxs-lookup"><span data-stu-id="daaf0-164">How do the break and continue statements differ?</span></span>

## <a name="recommended-reading"></a><span data-ttu-id="daaf0-165">Рекомендуем прочесть</span><span class="sxs-lookup"><span data-stu-id="daaf0-165">Recommended Reading</span></span>

- <span data-ttu-id="daaf0-166">[ForEach-Object][]</span><span class="sxs-lookup"><span data-stu-id="daaf0-166">[ForEach-Object][]</span></span>
- <span data-ttu-id="daaf0-167">[about_ForEach][]</span><span class="sxs-lookup"><span data-stu-id="daaf0-167">[about_ForEach][]</span></span>
- <span data-ttu-id="daaf0-168">[about_For][]</span><span class="sxs-lookup"><span data-stu-id="daaf0-168">[about_For][]</span></span>
- <span data-ttu-id="daaf0-169">[about_Do][]</span><span class="sxs-lookup"><span data-stu-id="daaf0-169">[about_Do][]</span></span>
- <span data-ttu-id="daaf0-170">[about_While][]</span><span class="sxs-lookup"><span data-stu-id="daaf0-170">[about_While][]</span></span>
- <span data-ttu-id="daaf0-171">[about_Break][]</span><span class="sxs-lookup"><span data-stu-id="daaf0-171">[about_Break][]</span></span>
- <span data-ttu-id="daaf0-172">[about_Continue][]</span><span class="sxs-lookup"><span data-stu-id="daaf0-172">[about_Continue][]</span></span>
- <span data-ttu-id="daaf0-173">[about_Return][]</span><span class="sxs-lookup"><span data-stu-id="daaf0-173">[about_Return][]</span></span>

<!-- link references -->
[ForEach-Object]: /powershell/module/microsoft.powershell.core/foreach-object
[about_ForEach]: /powershell/module/microsoft.powershell.core/about/about_foreach
[about_For]: /powershell/module/microsoft.powershell.core/about/about_for
[about_Do]: /powershell/module/microsoft.powershell.core/about/about_do
[about_While]: /powershell/module/microsoft.powershell.core/about/about_while
[about_Break]: /powershell/module/microsoft.powershell.core/about/about_break
[about_Continue]: /powershell/module/microsoft.powershell.core/about/about_continue
[about_Return]: /powershell/module/microsoft.powershell.core/about/about_return
[The PowerShell return keyword]: https://mikefrobbins.com/2015/07/23/the-powershell-return-keyword/
["The PowerShell return keyword"]: https://mikefrobbins.com/2015/07/23/the-powershell-return-keyword/
