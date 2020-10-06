---
title: Все, что вы хотели знать о массивах
description: Массивы являются основополагающей функцией большинства языков программирования.
ms.date: 07/07/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: 307189bf27d383159d34181eca4dac1f77792e51
ms.sourcegitcommit: c8d1ffeab215e74e87ea1b0af8cd606c1a6a80ab
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91543378"
---
# <a name="everything-you-wanted-to-know-about-arrays"></a><span data-ttu-id="fd62b-103">Все, что вы хотели знать о массивах</span><span class="sxs-lookup"><span data-stu-id="fd62b-103">Everything you wanted to know about arrays</span></span>

<span data-ttu-id="fd62b-104">[Массивы][] являются основополагающей функцией большинства языков программирования.</span><span class="sxs-lookup"><span data-stu-id="fd62b-104">[Arrays][] are a fundamental language feature of most programming languages.</span></span> <span data-ttu-id="fd62b-105">Они представляют собой коллекцию значений или объектов, с которыми вы, скорее всего, рано или поздно обязательно столкнетесь.</span><span class="sxs-lookup"><span data-stu-id="fd62b-105">They're a collection of values or objects that are difficult to avoid.</span></span> <span data-ttu-id="fd62b-106">Давайте рассмотрим массивы и все доступные в них возможности.</span><span class="sxs-lookup"><span data-stu-id="fd62b-106">Let's take a close look at arrays and everything they have to offer.</span></span>

> [!NOTE]
> <span data-ttu-id="fd62b-107">[Оригинал][] этой статьи впервые был опубликован в блоге автора [@KevinMarquette][].</span><span class="sxs-lookup"><span data-stu-id="fd62b-107">The [original version][] of this article appeared on the blog written by [@KevinMarquette][].</span></span> <span data-ttu-id="fd62b-108">Группа разработчиков PowerShell благодарит Кевина за то, что он поделился с нами этими материалами.</span><span class="sxs-lookup"><span data-stu-id="fd62b-108">The PowerShell team thanks Kevin for sharing this content with us.</span></span> <span data-ttu-id="fd62b-109">Ознакомьтесь с его блогом на веб-сайте [PowerShellExplained.com][].</span><span class="sxs-lookup"><span data-stu-id="fd62b-109">Please check out his blog at [PowerShellExplained.com][].</span></span>

## <a name="what-is-an-array"></a><span data-ttu-id="fd62b-110">Что такое массив?</span><span class="sxs-lookup"><span data-stu-id="fd62b-110">What is an array?</span></span>

<span data-ttu-id="fd62b-111">Я начну с основного технического описания массивов и способов их использования в большинстве языков программирования, а затем расскажу о других вариантах их использования в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd62b-111">I'm going to start with a basic technical description of what arrays are and how they are used by most programming languages before I shift into the other ways PowerShell makes use of them.</span></span>

<span data-ttu-id="fd62b-112">Массив представляет собой структуру данных, которая выступает в качестве коллекции из нескольких элементов.</span><span class="sxs-lookup"><span data-stu-id="fd62b-112">An array is a data structure that serves as a collection of multiple items.</span></span> <span data-ttu-id="fd62b-113">Можно выполнить итерацию по массиву или получить доступ к отдельным элементам, используя индекс.</span><span class="sxs-lookup"><span data-stu-id="fd62b-113">You can iterate over the array or access individual items using an index.</span></span> <span data-ttu-id="fd62b-114">Массив создается в виде последовательного фрагмента памяти, где все значения сохраняются непосредственно рядом друг с другом.</span><span class="sxs-lookup"><span data-stu-id="fd62b-114">The array is created as a sequential chunk of memory where each value is stored right next to the other.</span></span>

<span data-ttu-id="fd62b-115">Далее я расскажу обо всем этом подробнее.</span><span class="sxs-lookup"><span data-stu-id="fd62b-115">I'll touch on each of those details as we go.</span></span>

## <a name="basic-usage"></a><span data-ttu-id="fd62b-116">Основное использование</span><span class="sxs-lookup"><span data-stu-id="fd62b-116">Basic usage</span></span>

<span data-ttu-id="fd62b-117">Массивы представляют собой основную функцию PowerShell, поэтому в PowerShell предусмотрен простой синтаксис для работы с ними.</span><span class="sxs-lookup"><span data-stu-id="fd62b-117">Because arrays are such a basic feature of PowerShell, there is a simple syntax for working with them in PowerShell.</span></span>

### <a name="create-an-array"></a><span data-ttu-id="fd62b-118">Создание массива</span><span class="sxs-lookup"><span data-stu-id="fd62b-118">Create an array</span></span>

<span data-ttu-id="fd62b-119">Для создания пустого массива можно использовать `@()`.</span><span class="sxs-lookup"><span data-stu-id="fd62b-119">An empty array can be created by using `@()`</span></span>

```powershell
PS> $data = @()
PS> $data.count
0
```

<span data-ttu-id="fd62b-120">Мы можем создать массив и заполнить его значениями, просто заключив их в скобки `@()`.</span><span class="sxs-lookup"><span data-stu-id="fd62b-120">We can create an array and seed it with values just by placing them in the `@()` parentheses.</span></span>

```powershell
PS> $data = @('Zero','One','Two','Three')
PS> $data.count
4

PS> $data
Zero
One
Two
Three
```

<span data-ttu-id="fd62b-121">В этом массиве 4 элемента.</span><span class="sxs-lookup"><span data-stu-id="fd62b-121">This array has 4 items.</span></span> <span data-ttu-id="fd62b-122">При вызове переменной `$data` отображается список этих элементов.</span><span class="sxs-lookup"><span data-stu-id="fd62b-122">When we call the `$data` variable, we see the list of our items.</span></span> <span data-ttu-id="fd62b-123">Если речь о строковом массиве, в этом случае отображается по одному строковому элементу в строке.</span><span class="sxs-lookup"><span data-stu-id="fd62b-123">If it's an array of strings, then we get one line per string.</span></span>

<span data-ttu-id="fd62b-124">Можно объявить массив для нескольких строковых элементов.</span><span class="sxs-lookup"><span data-stu-id="fd62b-124">We can declare an array on multiple lines.</span></span> <span data-ttu-id="fd62b-125">В этом случае запятая является необязательной и, как правило, пропускается.</span><span class="sxs-lookup"><span data-stu-id="fd62b-125">The comma is optional in this case and generally left out.</span></span>

```powershell
$data = @(
    'Zero'
    'One'
    'Two'
    'Three'
)
```

<span data-ttu-id="fd62b-126">Я предпочитаю объявлять массивы для нескольких строковых элементов вот таким образом.</span><span class="sxs-lookup"><span data-stu-id="fd62b-126">I prefer to declare my arrays on multiple lines like that.</span></span> <span data-ttu-id="fd62b-127">Это не только упрощает чтение при наличии нескольких элементов, но и делает сравнение с предыдущими версиями более легким и удобным, если используется система управления версиями.</span><span class="sxs-lookup"><span data-stu-id="fd62b-127">Not only does it get easier to read when you have multiple items, it also makes it easier to compare to previous versions when using source control.</span></span>

#### <a name="other-syntax"></a><span data-ttu-id="fd62b-128">Другой синтаксис</span><span class="sxs-lookup"><span data-stu-id="fd62b-128">Other syntax</span></span>

<span data-ttu-id="fd62b-129">Известно, что `@()` является синтаксисом для создания массива, однако в большинстве случаев чаще используются списки с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="fd62b-129">It's commonly understood that `@()` is the syntax for creating an array, but comma-separated lists work most of the time.</span></span>

```powershell
$data = 'Zero','One','Two','Three'
```

#### <a name="write-output-to-create-arrays"></a><span data-ttu-id="fd62b-130">Write-Output для создания массивов</span><span class="sxs-lookup"><span data-stu-id="fd62b-130">Write-Output to create arrays</span></span>

<span data-ttu-id="fd62b-131">Один из полезных трюков, о котором следует упомянуть, заключается в использовании `Write-Output` для быстрого создания строк в консоли.</span><span class="sxs-lookup"><span data-stu-id="fd62b-131">One cool little trick worth mentioning is that you can use `Write-Output` to quickly create strings at the console.</span></span>

```powershell
$data = Write-Output Zero One Two Three
```

<span data-ttu-id="fd62b-132">Это очень удобно, поскольку не нужно заключать строки в кавычки, если параметр принимает строки.</span><span class="sxs-lookup"><span data-stu-id="fd62b-132">This is handy because you don't have to put quotes around the strings when the parameter accepts strings.</span></span> <span data-ttu-id="fd62b-133">В сценарии я бы этого не стал делать, но для консоли это вполне приемлемо.</span><span class="sxs-lookup"><span data-stu-id="fd62b-133">I would never do this in a script but it's fair game in the console.</span></span>

### <a name="accessing-items"></a><span data-ttu-id="fd62b-134">Доступ к элементам</span><span class="sxs-lookup"><span data-stu-id="fd62b-134">Accessing items</span></span>

<span data-ttu-id="fd62b-135">Теперь вам нужен доступ к имеющимся массивам с элементами, а также возможность обновлять их.</span><span class="sxs-lookup"><span data-stu-id="fd62b-135">Now that you have an array with items in it, you may want to access and update those items.</span></span>

#### <a name="offset"></a><span data-ttu-id="fd62b-136">Offset</span><span class="sxs-lookup"><span data-stu-id="fd62b-136">Offset</span></span>

<span data-ttu-id="fd62b-137">Для доступа к отдельным элементам используются скобки `[]` со значением смещения не менее 0.</span><span class="sxs-lookup"><span data-stu-id="fd62b-137">To access individual items, we use the brackets `[]` with an offset value starting at 0.</span></span> <span data-ttu-id="fd62b-138">Мы получаем первый элемент в массиве следующим образом.</span><span class="sxs-lookup"><span data-stu-id="fd62b-138">This is how we get the first item in our array:</span></span>

```powershell
PS> $data = 'Zero','One','Two','Three'
PS> $data[0]
Zero
```

<span data-ttu-id="fd62b-139">Причина, по которой мы используем ноль, заключается в том, что первый элемент находится в самом начале списка, поэтому, чтобы его достичь, потребуется смещение на 0 элементов.</span><span class="sxs-lookup"><span data-stu-id="fd62b-139">The reason why we use zero here is because the first item is at the beginning of the list so we use an offset of 0 items to get to it.</span></span> <span data-ttu-id="fd62b-140">Чтобы перейти ко второму элементу, требуется смещение на 1, чтобы пропустить первый элемент.</span><span class="sxs-lookup"><span data-stu-id="fd62b-140">To get to the second item, we would need to use an offset of 1 to skip the first item.</span></span>

```powershell
PS> $data[1]
One
```

<span data-ttu-id="fd62b-141">Это означает, что для последнего элемента используется значение смещения 3.</span><span class="sxs-lookup"><span data-stu-id="fd62b-141">This would mean that the last item is at offset 3.</span></span>

```powershell
PS> $data[3]
Three
```

#### <a name="index"></a><span data-ttu-id="fd62b-142">Индекс</span><span class="sxs-lookup"><span data-stu-id="fd62b-142">Index</span></span>

<span data-ttu-id="fd62b-143">Теперь вы видите, почему я выбрал для примера именно эти значения.</span><span class="sxs-lookup"><span data-stu-id="fd62b-143">Now you can see why I picked the values that I did for this example.</span></span> <span data-ttu-id="fd62b-144">Я представил это как смещение, поскольку это по сути именно оно, однако в данном случае смещение чаще называется индексом.</span><span class="sxs-lookup"><span data-stu-id="fd62b-144">I introduced this as an offset because that is what it really is, but this offset is more commonly referred to as an index.</span></span> <span data-ttu-id="fd62b-145">Это индекс, начинающийся с `0`.</span><span class="sxs-lookup"><span data-stu-id="fd62b-145">An index that starts at `0`.</span></span> <span data-ttu-id="fd62b-146">Далее в этой статье я буду называть смещение индексом.</span><span class="sxs-lookup"><span data-stu-id="fd62b-146">For the rest of this article I will call the offset an index.</span></span>

#### <a name="special-index-tricks"></a><span data-ttu-id="fd62b-147">Специальные возможности использования индекса</span><span class="sxs-lookup"><span data-stu-id="fd62b-147">Special index tricks</span></span>

<span data-ttu-id="fd62b-148">В большинстве языков можно указать только одно число в качестве индекса, и в ответ вы получаете один элемент.</span><span class="sxs-lookup"><span data-stu-id="fd62b-148">In most languages, you can only specify a single number as the index and you get a single item back.</span></span>
<span data-ttu-id="fd62b-149">PowerShell дает гораздо большую гибкость.</span><span class="sxs-lookup"><span data-stu-id="fd62b-149">PowerShell is much more flexible.</span></span> <span data-ttu-id="fd62b-150">Можно использовать несколько индексов одновременно.</span><span class="sxs-lookup"><span data-stu-id="fd62b-150">You can use multiple indexes at once.</span></span> <span data-ttu-id="fd62b-151">Благодаря списку индексов можно выбрать несколько элементов.</span><span class="sxs-lookup"><span data-stu-id="fd62b-151">By providing a list of indexes, we can select several items.</span></span>

```powershell
PS> $data[0,2,3]
Zero
Two
Three
```

<span data-ttu-id="fd62b-152">Элементы возвращаются с учетом порядка предоставляемых индексов.</span><span class="sxs-lookup"><span data-stu-id="fd62b-152">The items are returned based on the order of the indexes provided.</span></span> <span data-ttu-id="fd62b-153">Если индекс дублируется, то в обоих случаях вы получите именно этот элемент.</span><span class="sxs-lookup"><span data-stu-id="fd62b-153">If you duplicate an index, you get that item both times.</span></span>

```powershell
PS> $data[3,0,3]
Three
Zero
Three
```

<span data-ttu-id="fd62b-154">Чтобы указать последовательность чисел, можно использовать встроенный оператор `..`.</span><span class="sxs-lookup"><span data-stu-id="fd62b-154">We can specify a sequence of numbers with the built-in `..` operator.</span></span>

```powershell
PS> $data[1..3]
One
Two
Three
```

<span data-ttu-id="fd62b-155">Это работает и в обратном порядке.</span><span class="sxs-lookup"><span data-stu-id="fd62b-155">This works in reverse too.</span></span>

```powershell
PS> $data[3..1]
Three
Two
One
```

<span data-ttu-id="fd62b-156">Для смещения с конца можно указать отрицательные значения индекса.</span><span class="sxs-lookup"><span data-stu-id="fd62b-156">You can use negative index values to offset from the end.</span></span> <span data-ttu-id="fd62b-157">Поэтому, если требуется последний элемент в списке, можно использовать `-1`.</span><span class="sxs-lookup"><span data-stu-id="fd62b-157">So if you need the last item in the list, you can use `-1`.</span></span>

```powershell
PS> $data[-1]
Three
```

<span data-ttu-id="fd62b-158">При работе с оператором `..` необходимо учитывать следующее.</span><span class="sxs-lookup"><span data-stu-id="fd62b-158">One word of caution here with the `..` operator.</span></span> <span data-ttu-id="fd62b-159">Последовательности `0..-1` и `-1..0` вычислены со значениями `0,-1` и `-1,0`.</span><span class="sxs-lookup"><span data-stu-id="fd62b-159">The sequence `0..-1` and `-1..0` evaluate to the values `0,-1` and `-1,0`.</span></span> <span data-ttu-id="fd62b-160">Легко увидеть `$data[0..-1]` и предположить, что там будут перечислены все элементы, если забыть об этой детали.</span><span class="sxs-lookup"><span data-stu-id="fd62b-160">It's easy to see `$data[0..-1]` and think it would enumerate all items if you forget this detail.</span></span> <span data-ttu-id="fd62b-161">`$data[0..-1]` дает то же значение, что и `$data[0,-1]`, предоставляя первый и последний элементы в массиве (и ни одного из остальных значений).</span><span class="sxs-lookup"><span data-stu-id="fd62b-161">`$data[0..-1]` gives you the same value as `$data[0,-1]` by giving you the first and last item in the array (and none of the other values).</span></span>

#### <a name="out-of-bounds"></a><span data-ttu-id="fd62b-162">Вне допустимого диапазона</span><span class="sxs-lookup"><span data-stu-id="fd62b-162">Out of bounds</span></span>

<span data-ttu-id="fd62b-163">В большинстве языков при попытке доступа к индексу элемента, который находится дальше, чем конец массива, возникает ошибка или исключение.</span><span class="sxs-lookup"><span data-stu-id="fd62b-163">In most languages, if you try to access an index of an item that is past the end of the array, you would get some type of error or an exception.</span></span> <span data-ttu-id="fd62b-164">PowerShell просто не возвращает ничего.</span><span class="sxs-lookup"><span data-stu-id="fd62b-164">PowerShell silently returns nothing.</span></span>

```powershell
PS> $null -eq $data[9000]
True
```

#### <a name="cannot-index-into-a-null-array"></a><span data-ttu-id="fd62b-165">Индексирование в массив значений null невозможно</span><span class="sxs-lookup"><span data-stu-id="fd62b-165">Cannot index into a null array</span></span>

<span data-ttu-id="fd62b-166">Если используется переменная `$null` и вы пытаетесь индексировать ее как массив, выводится исключение `System.Management.Automation.RuntimeException` с сообщением `Cannot index into a null array`.</span><span class="sxs-lookup"><span data-stu-id="fd62b-166">If your variable is `$null` and you try to index it like an array, you get a `System.Management.Automation.RuntimeException` exception with the message `Cannot index into a null array`.</span></span>

```powershell
PS> $empty = $null
SP> $empty[0]
Error: Cannot index into a null array.
```

<span data-ttu-id="fd62b-167">Убедитесь, что массивы не являются `$null`, прежде чем пытаться получить доступ к элементам внутри них.</span><span class="sxs-lookup"><span data-stu-id="fd62b-167">So make sure your arrays are not `$null` before you try to access elements inside them.</span></span>

#### <a name="count"></a><span data-ttu-id="fd62b-168">Count</span><span class="sxs-lookup"><span data-stu-id="fd62b-168">Count</span></span>

<span data-ttu-id="fd62b-169">Массивы и другие коллекции содержат свойство Count, которое показывает количество элементов в массиве.</span><span class="sxs-lookup"><span data-stu-id="fd62b-169">Arrays and other collections have a count property that tells you how many items are in the array.</span></span>

```powershell
PS> $data.count
4
```

<span data-ttu-id="fd62b-170">В PowerShell 3.0 в большинство объектов добавляется свойство Count.</span><span class="sxs-lookup"><span data-stu-id="fd62b-170">PowerShell 3.0 added a count property to most objects.</span></span> <span data-ttu-id="fd62b-171">У вас может быть один объект, который должен сообщать свойство Count, равное `1`.</span><span class="sxs-lookup"><span data-stu-id="fd62b-171">you can have a single object and it should give you a count of `1`.</span></span>

```powershell
PS> $date = Get-Date
PS> $date.count
1
```

<span data-ttu-id="fd62b-172">Даже `$null` имеет свойство Count, только оно возвращает `0`.</span><span class="sxs-lookup"><span data-stu-id="fd62b-172">Even `$null` has a count property except it returns `0`.</span></span>

```powershell
PS> $null.count
0
```

<span data-ttu-id="fd62b-173">Однако в этом случае есть ряд сложностей, о которых я расскажу подробнее, когда буду говорить о проверке на наличие `$null` или пустых массивов далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="fd62b-173">There are some traps here that I will revisit when I cover checking for `$null` or empty arrays later on in this article.</span></span>

#### <a name="off-by-one-errors"></a><span data-ttu-id="fd62b-174">Ошибка завышения или занижения на единицу</span><span class="sxs-lookup"><span data-stu-id="fd62b-174">Off-by-one errors</span></span>

<span data-ttu-id="fd62b-175">Общая ошибка программирования возникает потому, что массивы начинаются с индекса 0.</span><span class="sxs-lookup"><span data-stu-id="fd62b-175">A common programming error is created because arrays start at index 0.</span></span> <span data-ttu-id="fd62b-176">Ошибки завышения/занижения на единицу можно представить двумя способами.</span><span class="sxs-lookup"><span data-stu-id="fd62b-176">Off-by-one errors can be introduced in two ways.</span></span>

<span data-ttu-id="fd62b-177">Первый — просто думать, что вам нужен второй элемент, использовать индекс `2` и действительно получить третий элемент.</span><span class="sxs-lookup"><span data-stu-id="fd62b-177">The first is by mentally thinking you want the second item and using an index of `2` and really getting the third item.</span></span> <span data-ttu-id="fd62b-178">Можно также думать, что у вас четыре элемента и вам нужен последний из них, и использовать свойство Count для доступа к последнему элементу.</span><span class="sxs-lookup"><span data-stu-id="fd62b-178">Or by thinking that you have four items and you want last item, so you use the count to access the last item.</span></span>

```powershell
$data[ $data.count ]
```

<span data-ttu-id="fd62b-179">В PowerShell вполне достаточно сделать это и указать, какой элемент существует в индексе 4: `$null`.</span><span class="sxs-lookup"><span data-stu-id="fd62b-179">PowerShell is perfectly happy to let you do that and give you exactly what item exists at index 4: `$null`.</span></span> <span data-ttu-id="fd62b-180">Следует использовать `$data.count - 1` или `-1`, о которых мы говорили выше.</span><span class="sxs-lookup"><span data-stu-id="fd62b-180">You should be using `$data.count - 1` or the `-1` that we learned about above.</span></span>

```powershell
PS> $data[ $data.count - 1 ]
Three
```

<span data-ttu-id="fd62b-181">В этом случае получить последний элемент можно с помощью индекса `-1`.</span><span class="sxs-lookup"><span data-stu-id="fd62b-181">This is where you can use the `-1` index to get the last element.</span></span>

```powershell
PS> $data[ -1 ]
Three
```

<span data-ttu-id="fd62b-182">Ли Дейли также подсказал, что мы можем использовать `$data.GetUpperBound(0)` для получения максимального номера индекса.</span><span class="sxs-lookup"><span data-stu-id="fd62b-182">Lee Dailey also pointed out to me that we can use `$data.GetUpperBound(0)` to get the max index number.</span></span>

```powershell
PS> $data.GetUpperBound(0)
3
PS> $data[ $data.GetUpperBound(0) ]
Three
```

<span data-ttu-id="fd62b-183">Второй наиболее распространенный способ — если вы выполняете итерацию по списку и не останавливаетесь в нужный момент.</span><span class="sxs-lookup"><span data-stu-id="fd62b-183">The second most common way is when iterating the list and not stopping at the right time.</span></span> <span data-ttu-id="fd62b-184">Я об этом расскажу подробнее, когда мы будем говорить об использовании цикла `for`.</span><span class="sxs-lookup"><span data-stu-id="fd62b-184">I'll revisit this when we talk about using the `for` loop.</span></span>

### <a name="updating-items"></a><span data-ttu-id="fd62b-185">Обновление элементов</span><span class="sxs-lookup"><span data-stu-id="fd62b-185">Updating items</span></span>

<span data-ttu-id="fd62b-186">Для обновления существующих элементов в массиве можно использовать тот же индекс.</span><span class="sxs-lookup"><span data-stu-id="fd62b-186">We can use the same index to update existing items in the array.</span></span> <span data-ttu-id="fd62b-187">Это позволяет напрямую обновлять отдельные элементы.</span><span class="sxs-lookup"><span data-stu-id="fd62b-187">This gives us direct access to update individual items.</span></span>

```powershell
$data[2] = 'dos'
$data[3] = 'tres'
```

<span data-ttu-id="fd62b-188">При попытке обновить элемент, который находится за последним элементом, возникает ошибка `Index was outside the bounds of the array.`.</span><span class="sxs-lookup"><span data-stu-id="fd62b-188">If we try to update an item that is past the last element, then we get an `Index was outside the bounds of the array.` error.</span></span>

```powershell
PS> $data[4] = 'four'
Index was outside the bounds of the array.
At line:1 char:1
+ $data[4] = 'four'
+ ~~~~~~~~~~~~~
+ CategoryInfo          : OperationStopped: (:) [], IndexOutOfRangeException
+ FullyQualifiedErrorId : System.IndexOutOfRangeException
```

<span data-ttu-id="fd62b-189">Я расскажу об этом позже, когда буду говорить об увеличении массива.</span><span class="sxs-lookup"><span data-stu-id="fd62b-189">I'll revisit this later when I talk about how to make an array larger.</span></span>

### <a name="iteration"></a><span data-ttu-id="fd62b-190">Итерация</span><span class="sxs-lookup"><span data-stu-id="fd62b-190">Iteration</span></span>

<span data-ttu-id="fd62b-191">В какой-то момент вам может потребоваться выполнить обход или итерацию по всему списку и применить действия к каждому элементу в массиве.</span><span class="sxs-lookup"><span data-stu-id="fd62b-191">At some point, you might need to walk or iterate the entire list and perform some action for each item in the array.</span></span>

#### <a name="pipeline"></a><span data-ttu-id="fd62b-192">Pipeline</span><span class="sxs-lookup"><span data-stu-id="fd62b-192">Pipeline</span></span>

<span data-ttu-id="fd62b-193">Предполагается, что массивы и конвейер PowerShell должны использоваться совместно.</span><span class="sxs-lookup"><span data-stu-id="fd62b-193">Arrays and the PowerShell pipeline are meant for each other.</span></span> <span data-ttu-id="fd62b-194">Это один из самых простых способов обработки этих значений.</span><span class="sxs-lookup"><span data-stu-id="fd62b-194">This is one of the simplest ways to process over those values.</span></span> <span data-ttu-id="fd62b-195">При передаче массива в конвейер каждый элемент внутри массива обрабатывается по отдельности.</span><span class="sxs-lookup"><span data-stu-id="fd62b-195">When you pass an array to a pipeline, each item inside the array is processed individually.</span></span>

```powershell
PS> $data = 'Zero','One','Two','Three'
PS> $data | ForEach-Object {"Item: [$PSItem]"}
Item: [Zero]
Item: [One]
Item: [Two]
Item: [Three]
```

<span data-ttu-id="fd62b-196">Если вы еще не видели `$PSItem`, просто помните, что это то же самое, что и `$_`.</span><span class="sxs-lookup"><span data-stu-id="fd62b-196">If you have not seen `$PSItem` before, just know that it's the same thing as `$_`.</span></span> <span data-ttu-id="fd62b-197">Можно использовать любой из них, так как оба этих элемента представляют текущий объект в конвейере.</span><span class="sxs-lookup"><span data-stu-id="fd62b-197">You can use either one because they both represent the current object in the pipeline.</span></span>

#### <a name="foreach-loop"></a><span data-ttu-id="fd62b-198">Цикл ForEach</span><span class="sxs-lookup"><span data-stu-id="fd62b-198">ForEach loop</span></span>

<span data-ttu-id="fd62b-199">Цикл `ForEach` эффективно работает с коллекциями.</span><span class="sxs-lookup"><span data-stu-id="fd62b-199">The `ForEach` loop works well with collections.</span></span> <span data-ttu-id="fd62b-200">Используется следующий синтаксис: `foreach ( <variable> in <collection> )`</span><span class="sxs-lookup"><span data-stu-id="fd62b-200">Using the syntax: `foreach ( <variable> in <collection> )`</span></span>

```powershell
foreach ( $node in $data )
{
    "Item: [$node]"
}
```

#### <a name="foreach-method"></a><span data-ttu-id="fd62b-201">Метод ForEach</span><span class="sxs-lookup"><span data-stu-id="fd62b-201">ForEach method</span></span>

<span data-ttu-id="fd62b-202">Я часто забываю о нем, однако этот метод эффективен для простых операций.</span><span class="sxs-lookup"><span data-stu-id="fd62b-202">I tend to forget about this one but it works well for simple operations.</span></span> <span data-ttu-id="fd62b-203">PowerShell позволяет вызывать `.ForEach()` для коллекции.</span><span class="sxs-lookup"><span data-stu-id="fd62b-203">PowerShell allows you to call `.ForEach()` on a collection.</span></span>

```powershell
PS> $data.foreach({"Item [$PSItem]"})
Item [Zero]
Item [One]
Item [Two]
Item [Three]
```

<span data-ttu-id="fd62b-204">`.foreach()` принимает параметр, который является блоком сценария.</span><span class="sxs-lookup"><span data-stu-id="fd62b-204">The `.foreach()` takes a parameter that is a script block.</span></span> <span data-ttu-id="fd62b-205">Можно удалить круглые скобки и просто указать блок сценария.</span><span class="sxs-lookup"><span data-stu-id="fd62b-205">You can drop the parentheses and just provide the script block.</span></span>

```powershell
$data.foreach{"Item [$PSItem]"}
```

<span data-ttu-id="fd62b-206">Такой синтаксис менее популярен, но он работает точно так же.</span><span class="sxs-lookup"><span data-stu-id="fd62b-206">This is a lesser known syntax but it works just the same.</span></span> <span data-ttu-id="fd62b-207">Метод `foreach` добавлен в PowerShell 4.0.</span><span class="sxs-lookup"><span data-stu-id="fd62b-207">This `foreach` method was added in PowerShell 4.0.</span></span>

#### <a name="for-loop"></a><span data-ttu-id="fd62b-208">Цикл For</span><span class="sxs-lookup"><span data-stu-id="fd62b-208">For loop</span></span>

<span data-ttu-id="fd62b-209">Цикл `for` активно используется в большинстве других языков, но в PowerShell он применяется редко.</span><span class="sxs-lookup"><span data-stu-id="fd62b-209">The `for` loop is used heavily in most other languages but you don't see it much in PowerShell.</span></span> <span data-ttu-id="fd62b-210">Однако если он все же используется, то зачастую это происходит в контексте обхода массива.</span><span class="sxs-lookup"><span data-stu-id="fd62b-210">When you do see it, it's often in the context of walking an array.</span></span>

```powershell
for ( $index = 0; $index -lt $data.count; $index++)
{
    "Item: [{0}]" -f $data[$index]
}
```

<span data-ttu-id="fd62b-211">В первую очередь мы инициализируем `$index` для `0`.</span><span class="sxs-lookup"><span data-stu-id="fd62b-211">The first thing we do is initialize an `$index` to `0`.</span></span> <span data-ttu-id="fd62b-212">Затем мы добавляем условие, что `$index` должно быть меньше `$data.count`.</span><span class="sxs-lookup"><span data-stu-id="fd62b-212">Then we add the condition that `$index` must be less than `$data.count`.</span></span> <span data-ttu-id="fd62b-213">Наконец, мы указываем, что при каждой обработке цикла необходимо увеличивать индекс на `1`.</span><span class="sxs-lookup"><span data-stu-id="fd62b-213">Finally, we specify that every time we loop that me must increase the index by `1`.</span></span> <span data-ttu-id="fd62b-214">В этом случае `$index++` расшифровывается как `$index = $index + 1`.</span><span class="sxs-lookup"><span data-stu-id="fd62b-214">In this case `$index++` is short for `$index = $index + 1`.</span></span>

<span data-ttu-id="fd62b-215">При каждом использовании цикла `for` следует обращать особое внимание на условие.</span><span class="sxs-lookup"><span data-stu-id="fd62b-215">Whenever you're using a `for` loop, pay special attention to the condition.</span></span> <span data-ttu-id="fd62b-216">Здесь я использовал `$index -lt $data.count`.</span><span class="sxs-lookup"><span data-stu-id="fd62b-216">I used `$index -lt $data.count` here.</span></span> <span data-ttu-id="fd62b-217">При этом довольно легко получить слегка неверное условие и в результате получить в логике ошибку завышения/занижения на единицу.</span><span class="sxs-lookup"><span data-stu-id="fd62b-217">It's easy to get the condition slightly wrong to get an off-by-one error in your logic.</span></span> <span data-ttu-id="fd62b-218">При использовании `$index -le $data.count` или `$index -lt ($data.count - 1)` всегда получается слегка неверное условие.</span><span class="sxs-lookup"><span data-stu-id="fd62b-218">Using `$index -le $data.count` or `$index -lt ($data.count - 1)` are ever so slightly wrong.</span></span> <span data-ttu-id="fd62b-219">Это может привести к тому, что в вашем результате будет обрабатываться слишком много или слишком мало элементов.</span><span class="sxs-lookup"><span data-stu-id="fd62b-219">That would cause your result to process too many or too few items.</span></span> <span data-ttu-id="fd62b-220">Это классическая ошибка завышения/занижения на единицу.</span><span class="sxs-lookup"><span data-stu-id="fd62b-220">This is the classic off-by-one error.</span></span>

#### <a name="switch-loop"></a><span data-ttu-id="fd62b-221">Цикл Switch</span><span class="sxs-lookup"><span data-stu-id="fd62b-221">Switch loop</span></span>

<span data-ttu-id="fd62b-222">Эту ошибку легко упустить из виду.</span><span class="sxs-lookup"><span data-stu-id="fd62b-222">This is one that is easy to overlook.</span></span> <span data-ttu-id="fd62b-223">Если вы укажете массив для [Оператор switch][], он проверит каждый элемент в массиве.</span><span class="sxs-lookup"><span data-stu-id="fd62b-223">If you provide an array to a [switch statement][], it checks each item in the array.</span></span>

```powershell
$data = 'Zero','One','Two','Three'
switch( $data )
{
    'One'
    {
        'Tock'
    }
    'Three'
    {
        'Tock'
    }
    Default
    {
        'Tick'
    }
}
```

```Output
Tick
Tock
Tick
Tock
```

<span data-ttu-id="fd62b-224">С помощью оператора switch можно выполнить массу полезных действий.</span><span class="sxs-lookup"><span data-stu-id="fd62b-224">There are a lot of cool things that we can do with the switch statement.</span></span> <span data-ttu-id="fd62b-225">Об этом я подробно рассказываю в другой статье.</span><span class="sxs-lookup"><span data-stu-id="fd62b-225">I have another article dedicated to this.</span></span>

- <span data-ttu-id="fd62b-226">[Все, чем вам нужно знать об операторе switch][оператор switch]</span><span class="sxs-lookup"><span data-stu-id="fd62b-226">[Everything you ever wanted to know about the switch statement][switch statement]</span></span>

#### <a name="updating-values"></a><span data-ttu-id="fd62b-227">Обновление значений</span><span class="sxs-lookup"><span data-stu-id="fd62b-227">Updating values</span></span>

<span data-ttu-id="fd62b-228">Если массив является коллекцией строковых или целочисленных значений, в отдельных случаях требуется обновление значений в массиве в процессе их циклической обработки.</span><span class="sxs-lookup"><span data-stu-id="fd62b-228">When your array is a collection of string or integers (value types), sometimes you may want to update the values in the array as you loop over them.</span></span> <span data-ttu-id="fd62b-229">В большинстве циклов, описанных выше, используется переменная в цикле, которая содержит копию значения.</span><span class="sxs-lookup"><span data-stu-id="fd62b-229">Most of the loops above use a variable in the loop that holds a copy of the value.</span></span> <span data-ttu-id="fd62b-230">При обновлении этой переменной исходное значение в массиве не обновляется.</span><span class="sxs-lookup"><span data-stu-id="fd62b-230">If you update that variable, the original value in the array is not updated.</span></span>

<span data-ttu-id="fd62b-231">Исключением для этого оператора является цикл `for`.</span><span class="sxs-lookup"><span data-stu-id="fd62b-231">The exception to that statement is the `for` loop.</span></span> <span data-ttu-id="fd62b-232">Если вам требуется обход массива и обновление значений в нем, вам нужен цикл `for`.</span><span class="sxs-lookup"><span data-stu-id="fd62b-232">If you want to walk an array and update values inside it, then the `for` loop is what you're looking for.</span></span>

```powershell
for ( $index = 0; $index -lt $data.count; $index++ )
{
    $data[$index] = "Item: [{0}]" -f $data[$index]
}
```

<span data-ttu-id="fd62b-233">В этом примере принимается значение по индексу, вносится ряд изменений, а затем тот же индекс используется, чтобы назначить значение обратно.</span><span class="sxs-lookup"><span data-stu-id="fd62b-233">This example takes a value by index, makes a few changes, and then uses that same index to assign it back.</span></span>

## <a name="arrays-of-objects"></a><span data-ttu-id="fd62b-234">Массивы объектов</span><span class="sxs-lookup"><span data-stu-id="fd62b-234">Arrays of Objects</span></span>

<span data-ttu-id="fd62b-235">До сих пор мы помещали в массив только тип значения, однако массивы также могут содержать и объекты.</span><span class="sxs-lookup"><span data-stu-id="fd62b-235">So far, the only thing we've placed in an array is a value type, but arrays can also contain objects.</span></span>

```powershell
$data = @(
    [pscustomobject]@{FirstName='Kevin';LastName='Marquette'}
    [pscustomobject]@{FirstName='John'; LastName='Doe'}
)
```

<span data-ttu-id="fd62b-236">Многие командлеты возвращают коллекции объектов в виде массивов, когда они назначаются переменной.</span><span class="sxs-lookup"><span data-stu-id="fd62b-236">Many cmdlets return collections of objects as arrays when you assign them to a variable.</span></span>

```powershell
$processList = Get-Process
```

<span data-ttu-id="fd62b-237">Все основные функции, о которых мы говорили, по-прежнему применяются для массивов объектов с некоторыми оговорками.</span><span class="sxs-lookup"><span data-stu-id="fd62b-237">All of the basic features we already talked about still apply to arrays of objects with a few details worth pointing out.</span></span>

### <a name="accessing-properties"></a><span data-ttu-id="fd62b-238">Доступ к свойствам</span><span class="sxs-lookup"><span data-stu-id="fd62b-238">Accessing properties</span></span>

<span data-ttu-id="fd62b-239">Можно использовать индекс для доступа к отдельному элементу в коллекции, как и в случае с типами значений.</span><span class="sxs-lookup"><span data-stu-id="fd62b-239">We can use an index to access an individual item in a collection just like with value types.</span></span>

```powershell
PS> $data[0]

FirstName LastName
-----     ----
Kevin     Marquette
```

<span data-ttu-id="fd62b-240">Мы можем напрямую получать доступ к свойствам и обновлять их.</span><span class="sxs-lookup"><span data-stu-id="fd62b-240">We can access and update properties directly.</span></span>

```powershell
PS> $data[0].FirstName

Kevin

PS> $data[0].FirstName = 'Jay'
PS> $data[0]

FirstName LastName
-----     ----
Jay       Marquette
```

#### <a name="array-properties"></a><span data-ttu-id="fd62b-241">Свойства массива</span><span class="sxs-lookup"><span data-stu-id="fd62b-241">Array properties</span></span>

<span data-ttu-id="fd62b-242">Обычно для доступа ко всем свойствам необходимо перечислить весь список следующим образом:</span><span class="sxs-lookup"><span data-stu-id="fd62b-242">Normally you would have to enumerate the whole list like this to access all the properties:</span></span>

```powershell
PS> $data | ForEach-Object {$_.LastName}

Marquette
Doe
```

<span data-ttu-id="fd62b-243">Кроме того, можно использовать командлет `Select-Object -ExpandProperty`.</span><span class="sxs-lookup"><span data-stu-id="fd62b-243">Or by using the `Select-Object -ExpandProperty` cmdlet.</span></span>

```powershell
PS> $data | Select-Object -ExpandProperty LastName

Marquette
Doe
```

<span data-ttu-id="fd62b-244">Однако PowerShell дает возможность запрашивать `LastName` напрямую.</span><span class="sxs-lookup"><span data-stu-id="fd62b-244">But PowerShell offers us the ability to request `LastName` directly.</span></span> <span data-ttu-id="fd62b-245">PowerShell самостоятельно перечисляет все эти данные и возвращает пустой список.</span><span class="sxs-lookup"><span data-stu-id="fd62b-245">PowerShell enumerates them all for us and returns a clean list.</span></span>

```powershell
PS> $data.LastName

Marquette
Doe
```

<span data-ttu-id="fd62b-246">Перечисление выполняется в обычном порядке, но мы избавлены от всех связанных с этим сложностей.</span><span class="sxs-lookup"><span data-stu-id="fd62b-246">The enumeration still happens but we don't see the complexity behind it.</span></span>

### <a name="where-object-filtering"></a><span data-ttu-id="fd62b-247">Фильтрация Where-Object</span><span class="sxs-lookup"><span data-stu-id="fd62b-247">Where-Object filtering</span></span>

<span data-ttu-id="fd62b-248">Именно здесь в игру вступает `Where-Object`, поэтому мы можем отфильтровать и выбрать объекты, которые следует исключить из массива, с учетом их свойств.</span><span class="sxs-lookup"><span data-stu-id="fd62b-248">This is where `Where-Object` comes in so we can filter and select what we want out of the array based on the properties of the object.</span></span>

```powershell
PS> $data | Where-Object {$_.FirstName -eq 'Kevin'}

FirstName LastName
-----     ----
Kevin     Marquette
```

<span data-ttu-id="fd62b-249">Можно написать тот же запрос, чтобы получить искомый `FirstName`.</span><span class="sxs-lookup"><span data-stu-id="fd62b-249">We can write that same query to get the `FirstName` we are looking for.</span></span>

```powershell
$data | Where FirstName -eq Kevin
```

#### <a name="where"></a><span data-ttu-id="fd62b-250">Where()</span><span class="sxs-lookup"><span data-stu-id="fd62b-250">Where()</span></span>

<span data-ttu-id="fd62b-251">В массивах доступен метод `Where()`, который позволяет указать `scriptblock` для фильтра.</span><span class="sxs-lookup"><span data-stu-id="fd62b-251">Arrays have a `Where()` method on them that allows you to specify a `scriptblock` for the filter.</span></span>

```powershell
$data.Where({$_.FirstName -eq 'Kevin'})
```

<span data-ttu-id="fd62b-252">Эта функция добавлена в PowerShell 4.0.</span><span class="sxs-lookup"><span data-stu-id="fd62b-252">This feature was added in PowerShell 4.0.</span></span>

### <a name="updating-objects-in-loops"></a><span data-ttu-id="fd62b-253">Обновление объектов в циклах</span><span class="sxs-lookup"><span data-stu-id="fd62b-253">Updating objects in loops</span></span>

<span data-ttu-id="fd62b-254">Если применяются типы значений, единственным способом обновить массив является использование цикла, поскольку нам нужно знать индекс, чтобы заменить значение.</span><span class="sxs-lookup"><span data-stu-id="fd62b-254">With value types, the only way to update the array is to use a for loop because we need to know the index to replace the value.</span></span> <span data-ttu-id="fd62b-255">Для объектов предусмотрено больше возможностей, поскольку они относятся к ссылочным типам.</span><span class="sxs-lookup"><span data-stu-id="fd62b-255">We have more options with objects because they are reference types.</span></span> <span data-ttu-id="fd62b-256">Приведем краткий пример:</span><span class="sxs-lookup"><span data-stu-id="fd62b-256">Here is a quick example:</span></span>

```powershell
foreach($person in $data)
{
    $person.FirstName = 'Kevin'
}
```

<span data-ttu-id="fd62b-257">Этот цикл обходит каждый объект в массиве `$data`.</span><span class="sxs-lookup"><span data-stu-id="fd62b-257">This loop is walking every object in the `$data` array.</span></span> <span data-ttu-id="fd62b-258">Поскольку объекты являются ссылочными типами, переменная `$person` ссылается на тот же объект, который находится в массиве.</span><span class="sxs-lookup"><span data-stu-id="fd62b-258">Because objects are reference types, the `$person` variable references the exact same object that is in the array.</span></span> <span data-ttu-id="fd62b-259">Таким образом, обновления для свойств применяются к исходным свойствам.</span><span class="sxs-lookup"><span data-stu-id="fd62b-259">So updates to its properties do update the original.</span></span>

<span data-ttu-id="fd62b-260">Этот способ по-прежнему не позволяет заменить весь объект.</span><span class="sxs-lookup"><span data-stu-id="fd62b-260">You still can't replace the whole object this way.</span></span> <span data-ttu-id="fd62b-261">При попытке назначить новый объект переменной `$person` ссылка на переменную обновляется на другой элемент, который больше не указывает на исходный объект в массиве.</span><span class="sxs-lookup"><span data-stu-id="fd62b-261">If you try to assign a new object to the `$person` variable, you're updating the variable reference to something else that no longer points to the original object in the array.</span></span> <span data-ttu-id="fd62b-262">То есть это работает не так, как вы ожидали:</span><span class="sxs-lookup"><span data-stu-id="fd62b-262">This doesn't work like you would expect:</span></span>

```powershell
foreach($person in $data)
{
    $person = [pscustomobject]@{
        FirstName='Kevin'
        LastName='Marquette'
    }
}
```

## <a name="operators"></a><span data-ttu-id="fd62b-263">Операторы</span><span class="sxs-lookup"><span data-stu-id="fd62b-263">Operators</span></span>

<span data-ttu-id="fd62b-264">Операторы в PowerShell также эффективны для массивов.</span><span class="sxs-lookup"><span data-stu-id="fd62b-264">The operators in PowerShell also work on arrays.</span></span> <span data-ttu-id="fd62b-265">Некоторые из них работают несколько иначе.</span><span class="sxs-lookup"><span data-stu-id="fd62b-265">Some of them work slightly differently.</span></span>

### <a name="-join"></a><span data-ttu-id="fd62b-266">-join</span><span class="sxs-lookup"><span data-stu-id="fd62b-266">-join</span></span>

<span data-ttu-id="fd62b-267">Оператор `-join` является самым очевидным примером, поэтому давайте рассмотрим его первым.</span><span class="sxs-lookup"><span data-stu-id="fd62b-267">The `-join` operator is the most obvious one so let's look at it first.</span></span> <span data-ttu-id="fd62b-268">Мне нравится оператор `-join`, я его часто использую.</span><span class="sxs-lookup"><span data-stu-id="fd62b-268">I like the `-join` operator and use it often.</span></span> <span data-ttu-id="fd62b-269">Он объединяет все элементы в массиве с помощью заданного символа или строки.</span><span class="sxs-lookup"><span data-stu-id="fd62b-269">It joins all elements in the array with the character or string that you specify.</span></span>

```powershell
PS> $data = @(1,2,3,4)
PS> $data -join '-'
1-2-3-4
PS> $data -join ','
1,2,3,4
```

<span data-ttu-id="fd62b-270">В операторе `-join` мне особенно нравится то, что он обрабатывает единичные элементы.</span><span class="sxs-lookup"><span data-stu-id="fd62b-270">One of the features that I like about the `-join` operator is that it handles single items.</span></span>

```powershell
PS> 1 -join '-'
1
```

<span data-ttu-id="fd62b-271">Я использую его для ведения журнала и подробных сообщений.</span><span class="sxs-lookup"><span data-stu-id="fd62b-271">I use this inside logging and verbose messages.</span></span>

```powershell
PS> $data = @(1,2,3,4)
PS> "Data is $($data -join ',')."
Data is 1,2,3,4.
```

#### <a name="-join-array"></a><span data-ttu-id="fd62b-272">-join $array</span><span class="sxs-lookup"><span data-stu-id="fd62b-272">-join $array</span></span>

<span data-ttu-id="fd62b-273">Вот еще один полезный прием, о котором мне рассказал Ли Дейли.</span><span class="sxs-lookup"><span data-stu-id="fd62b-273">Here is a clever trick that Lee Dailey pointed out to me.</span></span> <span data-ttu-id="fd62b-274">Если нужно объединить все без использования разделителя, вместо этого:</span><span class="sxs-lookup"><span data-stu-id="fd62b-274">If you ever want to join everything without a delimiter, instead of doing this:</span></span>

```powershell
PS> $data = @(1,2,3,4)
PS> $data -join $null
1234
```

<span data-ttu-id="fd62b-275">Можно использовать `-join` с массивом в качестве параметра без префикса.</span><span class="sxs-lookup"><span data-stu-id="fd62b-275">You can use `-join` with the array as the parameter with no prefix.</span></span> <span data-ttu-id="fd62b-276">Этот пример наглядно демонстрирует то, о чем я говорил.</span><span class="sxs-lookup"><span data-stu-id="fd62b-276">Take a look at this example to see that I'm talking about.</span></span>

```powershell
PS> $data = @(1,2,3,4)
PS> -join $data
1234
```

### <a name="-replace-and--split"></a><span data-ttu-id="fd62b-277">-replace и -split</span><span class="sxs-lookup"><span data-stu-id="fd62b-277">-replace and -split</span></span>

<span data-ttu-id="fd62b-278">Другие операторы, такие как `-replace` и `-split`, выполняются для каждого элемента в массиве.</span><span class="sxs-lookup"><span data-stu-id="fd62b-278">The other operators like `-replace` and `-split` execute on each item in the array.</span></span> <span data-ttu-id="fd62b-279">Не скажу, что я их когда-нибудь таким образом использовал, но вот пример этого.</span><span class="sxs-lookup"><span data-stu-id="fd62b-279">I can't say that I have ever used them this way but here is an example.</span></span>

```powershell
PS> $data = @('ATX-SQL-01','ATX-SQL-02','ATX-SQL-03')
PS> $data -replace 'ATX','LAX'
LAX-SQL-01
LAX-SQL-02
LAX-SQL-03
```

### <a name="-contains"></a><span data-ttu-id="fd62b-280">-contains</span><span class="sxs-lookup"><span data-stu-id="fd62b-280">-contains</span></span>

<span data-ttu-id="fd62b-281">Оператор `-contains` позволяет проверить массив значений, чтобы определить, содержит ли он указанное значение.</span><span class="sxs-lookup"><span data-stu-id="fd62b-281">The `-contains` operator allows you to check an array of values to see if it contains a specified value.</span></span>

```powershell
PS> $data = @('red','green','blue')
PS> $data -contains 'green'
True
```

### <a name="-in"></a><span data-ttu-id="fd62b-282">-in</span><span class="sxs-lookup"><span data-stu-id="fd62b-282">-in</span></span>

<span data-ttu-id="fd62b-283">Если одно значение, которое вам нужно проверить, совпадает с одним или несколькими значениями, можно использовать оператор `-in`.</span><span class="sxs-lookup"><span data-stu-id="fd62b-283">When you have a single value that you would like to verify matches one of several values, you can use the `-in` operator.</span></span> <span data-ttu-id="fd62b-284">Значение должно быть в левой, а массив — в правой части оператора.</span><span class="sxs-lookup"><span data-stu-id="fd62b-284">The value would be on the left and the array on the right-hand side of the operator.</span></span>

```powershell
PS> $data = @('red','green','blue')
PS> 'green' -in $data
True
```

<span data-ttu-id="fd62b-285">Такой способ может оказаться дорогостоящим, если список достаточно велик.</span><span class="sxs-lookup"><span data-stu-id="fd62b-285">This can get expensive if the list is large.</span></span> <span data-ttu-id="fd62b-286">Я часто использую шаблон регулярного выражения, если проверяется большое количество значений.</span><span class="sxs-lookup"><span data-stu-id="fd62b-286">I often use a regex pattern if I'm checking more than a few values.</span></span>

```powershell
PS> $data = @('red','green','blue')
PS> $pattern = "^({0})$" -f ($data -join '|')
PS> $pattern
^(red|green|blue)$

PS> 'green' -match $pattern
True
```

### <a name="-eq-and--ne"></a><span data-ttu-id="fd62b-287">-eq и -ne</span><span class="sxs-lookup"><span data-stu-id="fd62b-287">-eq and -ne</span></span>

<span data-ttu-id="fd62b-288">Равенство и массивы могут оказаться достаточно сложными.</span><span class="sxs-lookup"><span data-stu-id="fd62b-288">Equality and arrays can get complicated.</span></span> <span data-ttu-id="fd62b-289">Если массив располагается в левой части, выполняется сравнение всех элементов.</span><span class="sxs-lookup"><span data-stu-id="fd62b-289">When the array is on the left side, every item gets compared.</span></span> <span data-ttu-id="fd62b-290">Вместо возврата `True` возвращается совпадающий объект.</span><span class="sxs-lookup"><span data-stu-id="fd62b-290">Instead of returning `True`, it returns the object that matches.</span></span>

```powershell
PS> $data = @('red','green','blue')
PS> $data -eq 'green'
green
```

<span data-ttu-id="fd62b-291">Если используется оператор `-ne`, вы получаете все значения, которые не равны имеющемуся.</span><span class="sxs-lookup"><span data-stu-id="fd62b-291">When you use the `-ne` operator, we get all the values that are not equal to our value.</span></span>

```powershell
PS> $data = @('red','green','blue')
PS> $data -ne 'green'
red
blue
```

<span data-ttu-id="fd62b-292">При использовании в операторе `if()` возвращается значение `True`.</span><span class="sxs-lookup"><span data-stu-id="fd62b-292">When you use this in an `if()` statement, a value that is returned is a `True` value.</span></span> <span data-ttu-id="fd62b-293">Если значение не возвращается, то речь о значении `False`.</span><span class="sxs-lookup"><span data-stu-id="fd62b-293">If no value is returned, then it's a `False` value.</span></span> <span data-ttu-id="fd62b-294">Оба этих оператора оцениваются как `True`.</span><span class="sxs-lookup"><span data-stu-id="fd62b-294">Both of these next statements evaluate to `True`.</span></span>

```powershell
$data = @('red','green','blue')
if ( $data -eq 'green' )
{
    'Green was found'
}
if ( $data -ne 'green' )
{
    'And green was not found'
}
```

<span data-ttu-id="fd62b-295">Я еще вернусь к этому вопросу позднее, когда мы будем говорить о тестировании `$null`.</span><span class="sxs-lookup"><span data-stu-id="fd62b-295">I'll revisit this in a moment when we talk about testing for `$null`.</span></span>

### <a name="-match"></a><span data-ttu-id="fd62b-296">-match</span><span class="sxs-lookup"><span data-stu-id="fd62b-296">-match</span></span>

<span data-ttu-id="fd62b-297">Оператор `-match` пытается сопоставить все элементы в коллекции.</span><span class="sxs-lookup"><span data-stu-id="fd62b-297">The `-match` operator tries to match each item in the collection.</span></span>

```powershell
PS> $servers = @(
    'LAX-SQL-01'
    'LAX-API-01'
    'ATX-SQL-01'
    'ATX-API-01'
)
PS> $servers -match 'SQL'
LAX-SQL-01
ATX-SQL-01
```

<span data-ttu-id="fd62b-298">При использовании `-match` с одним значением специальная переменная `$Matches` заполняется сведениями о соответствии.</span><span class="sxs-lookup"><span data-stu-id="fd62b-298">When you use `-match` with a single value, a special variable `$Matches` gets populated with match info.</span></span> <span data-ttu-id="fd62b-299">Этого не происходит, если массив обрабатывается таким образом.</span><span class="sxs-lookup"><span data-stu-id="fd62b-299">This isn't the case when an array is processed this way.</span></span>

<span data-ttu-id="fd62b-300">Этот же подход можно использовать в случае с `Select-String`.</span><span class="sxs-lookup"><span data-stu-id="fd62b-300">We can take the same approach with `Select-String`.</span></span>

```powershell
$servers | Select-String SQL
```

<span data-ttu-id="fd62b-301">Я подробно расскажу о переменных `Select-String`, `-match` и `$matches` в другой публикации под названием [Множество способов использования регулярных выражений][] (Множество способов использования регулярных выражений).</span><span class="sxs-lookup"><span data-stu-id="fd62b-301">I take a closer look at `Select-String`,`-match` and the `$matches` variable in another post called [The many ways to use regex][].</span></span>

### <a name="null-or-empty"></a><span data-ttu-id="fd62b-302">$null или empty</span><span class="sxs-lookup"><span data-stu-id="fd62b-302">$null or empty</span></span>

<span data-ttu-id="fd62b-303">Проверка на наличие `$null` или пустых массивов может быть непростой задачей.</span><span class="sxs-lookup"><span data-stu-id="fd62b-303">Testing for `$null` or empty arrays can be tricky.</span></span> <span data-ttu-id="fd62b-304">Далее описаны самые распространенные проблемы, связанные с массивами.</span><span class="sxs-lookup"><span data-stu-id="fd62b-304">Here are the common traps with arrays.</span></span>

<span data-ttu-id="fd62b-305">На первый взгляд этот оператор выглядит вполне работоспособным.</span><span class="sxs-lookup"><span data-stu-id="fd62b-305">At a glance, this statement looks like it should work.</span></span>

```powershell
if ( $array -eq $null)
{
    'Array is $null'
}
```

<span data-ttu-id="fd62b-306">Однако я только что рассказал, как `-eq` проверяет каждый элемент в массиве.</span><span class="sxs-lookup"><span data-stu-id="fd62b-306">But I just went over how `-eq` checks each item in the array.</span></span> <span data-ttu-id="fd62b-307">Таким образом, у нас может быть массив из нескольких элементов с одним значением $null и результатом вычисления будет `$true`</span><span class="sxs-lookup"><span data-stu-id="fd62b-307">So we can have an array of several items with a single $null value and it would evaluate to `$true`</span></span>

```powershell
$array = @('one',$null,'three')
if ( $array -eq $null)
{
    'I think Array is $null, but I would be wrong'
}
```

<span data-ttu-id="fd62b-308">Именно поэтому рекомендуется размещать `$null` в левой части оператора.</span><span class="sxs-lookup"><span data-stu-id="fd62b-308">This is why it's a best practice to place the `$null` on the left side of the operator.</span></span> <span data-ttu-id="fd62b-309">Благодаря этому сценарий выполняется без проблем.</span><span class="sxs-lookup"><span data-stu-id="fd62b-309">This makes this scenario a non-issue.</span></span>

```powershell
if ( $null -eq $array )
{
    'Array actually is $null'
}
```

<span data-ttu-id="fd62b-310">Массив `$null` не равен пустому массиву.</span><span class="sxs-lookup"><span data-stu-id="fd62b-310">A `$null` array isn't the same thing as an empty array.</span></span> <span data-ttu-id="fd62b-311">Если вы уверены, что у вас есть массив, проверьте количество объектов в нем.</span><span class="sxs-lookup"><span data-stu-id="fd62b-311">If you know you have an array, check the count of objects in it.</span></span> <span data-ttu-id="fd62b-312">Если это массив `$null`, число объектов равно `0`.</span><span class="sxs-lookup"><span data-stu-id="fd62b-312">If the array is `$null`, the count is `0`.</span></span>

```powershell
if ( $array.count -gt 0 )
{
    'Array isn't empty'
}
```

<span data-ttu-id="fd62b-313">Однако есть еще одна сложность, которую нужно учитывать в этом случае.</span><span class="sxs-lookup"><span data-stu-id="fd62b-313">There is one more trap to watch out for here.</span></span> <span data-ttu-id="fd62b-314">Можно использовать `count` даже при наличии одного объекта, если только этот объект не является `PSCustomObject`.</span><span class="sxs-lookup"><span data-stu-id="fd62b-314">You can use the `count` even if you have a single object, unless that object is a `PSCustomObject`.</span></span> <span data-ttu-id="fd62b-315">Эта ошибка исправлена в PowerShell 6.1.</span><span class="sxs-lookup"><span data-stu-id="fd62b-315">This is a bug that is fixed in PowerShell 6.1.</span></span>
<span data-ttu-id="fd62b-316">Это хорошая новость, однако многие люди по-прежнему используют версию 5.1, так что им стоит иметь в виду указанную ошибку.</span><span class="sxs-lookup"><span data-stu-id="fd62b-316">That's good news, but a lot of people are still on 5.1 and need to watch out for it.</span></span>

```powershell
PS> $object = [PSCustomObject]@{Name='TestObject'}
PS> $object.count
$null
```

<span data-ttu-id="fd62b-317">Если вы по-прежнему используете PowerShell 5.1, можно перенести объект в массив перед проверкой количества объектов, чтобы получить точное число.</span><span class="sxs-lookup"><span data-stu-id="fd62b-317">If you're still on PowerShell 5.1, you can wrap the object in an array before checking the count to get an accurate count.</span></span>

```powershell
if ( @($array).count -gt 0 )
{
    'Array isn't empty'
}
```

<span data-ttu-id="fd62b-318">Чтобы безопасно воспроизвести этот сценарий, проверьте `$null`, а затем проверьте число объектов.</span><span class="sxs-lookup"><span data-stu-id="fd62b-318">To fully play it safe, check for `$null`, then check the count.</span></span>

```powershell
if ( $null -ne $array -and @($array).count -gt 0 )
{
    'Array isn't empty'
}
```

### <a name="all--eq"></a><span data-ttu-id="fd62b-319">All -eq</span><span class="sxs-lookup"><span data-stu-id="fd62b-319">All -eq</span></span>

<span data-ttu-id="fd62b-320">Недавно кто-то спрашивал, [как проверить, соответствует ли каждое значение в массиве заданному значению][].</span><span class="sxs-lookup"><span data-stu-id="fd62b-320">I recently saw someone ask [how to verify that every value in an array matches a given value][].</span></span>
<span data-ttu-id="fd62b-321">Пользователь Reddit **/u/bis** предложил это разумное [решение][], которое проверяет наличие некорректных значений, а затем инвертирует результат.</span><span class="sxs-lookup"><span data-stu-id="fd62b-321">Reddit user **/u/bis** had this clever [solution][] that checks for any incorrect values and then flips the result.</span></span>

```powershell
$results = Test-Something
if ( -not ( $results -ne 'Passed') )
{
    'All results a Passed'
}
```

## <a name="adding-to-arrays"></a><span data-ttu-id="fd62b-322">Добавление в массивы</span><span class="sxs-lookup"><span data-stu-id="fd62b-322">Adding to arrays</span></span>

<span data-ttu-id="fd62b-323">На этом этапе вас начинает интересовать, как добавить элементы в массив.</span><span class="sxs-lookup"><span data-stu-id="fd62b-323">At this point, you're starting to wonder how to add items to an array.</span></span> <span data-ttu-id="fd62b-324">Собственно говоря, никак.</span><span class="sxs-lookup"><span data-stu-id="fd62b-324">The quick answer is that you can't.</span></span> <span data-ttu-id="fd62b-325">Массив имеет фиксированный размер в памяти.</span><span class="sxs-lookup"><span data-stu-id="fd62b-325">An array is a fixed size in memory.</span></span> <span data-ttu-id="fd62b-326">Если необходимо увеличить массив или добавить в него один элемент, то в этом случае необходимо создать новый массив и скопировать в него все значения из старого.</span><span class="sxs-lookup"><span data-stu-id="fd62b-326">If you need to grow it or add a single item to it, then you need to create a new array and copy all the values over from the old array.</span></span> <span data-ttu-id="fd62b-327">На первый взгляд это требует значительных усилий, однако PowerShell значительно упрощает создание нового массива.</span><span class="sxs-lookup"><span data-stu-id="fd62b-327">This sounds like a lot of work, however, PowerShell hides the complexity of creating the new array.</span></span> <span data-ttu-id="fd62b-328">В PowerShell реализован оператор сложения (`+`) для массивов.</span><span class="sxs-lookup"><span data-stu-id="fd62b-328">PowerShell implements the addition operator (`+`) for arrays.</span></span>

> [!NOTE]
> <span data-ttu-id="fd62b-329">В PowerShell не реализована операция вычитания.</span><span class="sxs-lookup"><span data-stu-id="fd62b-329">PowerShell does not implement a subtraction operation.</span></span> <span data-ttu-id="fd62b-330">Если требуется гибкая альтернатива массиву, необходимо использовать [универсальный объект `List`](#generic-list).</span><span class="sxs-lookup"><span data-stu-id="fd62b-330">If you want a flexible alternative to an array, you need to use a [generic `List`](#generic-list) object.</span></span>

### <a name="array-addition"></a><span data-ttu-id="fd62b-331">Сложение массивов</span><span class="sxs-lookup"><span data-stu-id="fd62b-331">Array addition</span></span>

<span data-ttu-id="fd62b-332">Для создания нового массива можно использовать оператор сложения.</span><span class="sxs-lookup"><span data-stu-id="fd62b-332">We can use the addition operator with arrays to create a new array.</span></span> <span data-ttu-id="fd62b-333">Итак, дано два массива:</span><span class="sxs-lookup"><span data-stu-id="fd62b-333">So given these two arrays:</span></span>

```powershell
$first = @(
    'Zero'
    'One'
)
$second = @(
    'Two'
    'Three'
)
```

<span data-ttu-id="fd62b-334">Мы можем сложить их вместе, чтобы получить новый массив.</span><span class="sxs-lookup"><span data-stu-id="fd62b-334">We can add them together to get a new array.</span></span>

```powershell
PS> $first + $second

Zero
One
Two
Three
```

### <a name="plus-equals-"></a><span data-ttu-id="fd62b-335">Плюс равно (+=)</span><span class="sxs-lookup"><span data-stu-id="fd62b-335">Plus equals +=</span></span>

<span data-ttu-id="fd62b-336">Мы можем создать новый массив и добавить в него элемент следующим образом:</span><span class="sxs-lookup"><span data-stu-id="fd62b-336">We can create a new array in place and add an item to it like this:</span></span>

```powershell
$data = @(
    'Zero'
    'One'
    'Two'
    'Three'
)
$data += 'four'
```

<span data-ttu-id="fd62b-337">Просто помните, что каждый раз, когда вы используете `+=`, выполняется дублирование и создание нового массива.</span><span class="sxs-lookup"><span data-stu-id="fd62b-337">Just remember that every time you use `+=` that you're duplicating and creating a new array.</span></span> <span data-ttu-id="fd62b-338">Это не проблема, если речь идет о небольших наборах данных, но масштабирование в этом случае выполняется очень ограниченно.</span><span class="sxs-lookup"><span data-stu-id="fd62b-338">This is a not an issue for small datasets but it scales extremely poorly.</span></span>

### <a name="pipeline-assignment"></a><span data-ttu-id="fd62b-339">Назначение конвейера</span><span class="sxs-lookup"><span data-stu-id="fd62b-339">Pipeline assignment</span></span>

<span data-ttu-id="fd62b-340">Можно назначить результаты любого конвейера для добавления в любую переменную.</span><span class="sxs-lookup"><span data-stu-id="fd62b-340">You can assign the results of any pipeline into a variable.</span></span> <span data-ttu-id="fd62b-341">Она будет считаться массивом, если содержит несколько элементов.</span><span class="sxs-lookup"><span data-stu-id="fd62b-341">It's an array if it contains multiple items.</span></span>

```powershell
$array = 1..5 | ForEach-Object {
    "ATX-SQL-$PSItem"
}
```

<span data-ttu-id="fd62b-342">Обычно если мы говорим об использовании конвейера, мы подразумеваем типичные однострочные сценарии PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd62b-342">Normally when we think of using the pipeline, we think of the typical PowerShell one-liners.</span></span> <span data-ttu-id="fd62b-343">Можно использовать конвейер с операторами `foreach()` и другими циклами.</span><span class="sxs-lookup"><span data-stu-id="fd62b-343">We can leverage the pipeline with `foreach()` statements and other loops.</span></span> <span data-ttu-id="fd62b-344">Таким образом, вместо добавления элементов в массив в цикле можно поместить элементы в конвейер.</span><span class="sxs-lookup"><span data-stu-id="fd62b-344">So instead of adding items to an array in a loop, we can drop items onto the pipeline.</span></span>

```powershell
$array = foreach ( $node in (1..5))
{
    "ATX-SQL-$node"
}
```

## <a name="array-types"></a><span data-ttu-id="fd62b-345">Типы массивов</span><span class="sxs-lookup"><span data-stu-id="fd62b-345">Array Types</span></span>

<span data-ttu-id="fd62b-346">По умолчанию массив в PowerShell создается как тип `[PSObject[]]`.</span><span class="sxs-lookup"><span data-stu-id="fd62b-346">By default, an array in PowerShell is created as a `[PSObject[]]` type.</span></span> <span data-ttu-id="fd62b-347">Благодаря этому он может содержать любые типы объектов и значений.</span><span class="sxs-lookup"><span data-stu-id="fd62b-347">This allows it to contain any type of object or value.</span></span> <span data-ttu-id="fd62b-348">Это возможно, поскольку все наследуется из типа `PSObject`.</span><span class="sxs-lookup"><span data-stu-id="fd62b-348">This works because everything is inherited from the `PSObject` type.</span></span>

### <a name="strongly-typed-arrays"></a><span data-ttu-id="fd62b-349">Строго типизированные массивы</span><span class="sxs-lookup"><span data-stu-id="fd62b-349">Strongly typed arrays</span></span>

<span data-ttu-id="fd62b-350">Массив любого типа можно создать с помощью сходного синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="fd62b-350">You can create an array of any type using a similar syntax.</span></span> <span data-ttu-id="fd62b-351">Если вы создаете строго типизированный массив, он может содержать только значения или объекты заданного типа.</span><span class="sxs-lookup"><span data-stu-id="fd62b-351">When you create a strongly typed array, it can only contain values or objects the specified type.</span></span>

```powershell
PS> [int[]] $numbers = 1,2,3
PS> [int[]] $numbers2 = 'one','two','three'
ERROR: Cannot convert value "one" to type "System.Int32". Input string was not in a correct format."

PS> [string[]] $strings = 'one','two','three'
```

### <a name="arraylist"></a><span data-ttu-id="fd62b-352">ArrayList</span><span class="sxs-lookup"><span data-stu-id="fd62b-352">ArrayList</span></span>

<span data-ttu-id="fd62b-353">Добавление элементов в массив накладывает самые серьезные ограничения, однако существует ряд других коллекций, которые можно использовать для решения этой проблемы.</span><span class="sxs-lookup"><span data-stu-id="fd62b-353">Adding items to an array is one of its biggest limitations, but there are a few other collections that we can turn to that solve this problem.</span></span>

<span data-ttu-id="fd62b-354">Как правило, если нам нужен массив, поддерживающий более быструю работу, мы в первую очередь вспоминаем о `ArrayList`.</span><span class="sxs-lookup"><span data-stu-id="fd62b-354">The `ArrayList` is commonly one of the first things that we think of when we need an array that is faster to work with.</span></span> <span data-ttu-id="fd62b-355">Он выступает в качестве массива объектов везде, где это необходимо, и при этом поддерживает быстрое добавление элементов.</span><span class="sxs-lookup"><span data-stu-id="fd62b-355">It acts like an object array every place that we need it, but it handles adding items quickly.</span></span>

<span data-ttu-id="fd62b-356">Мы создаем `ArrayList` и добавляем в него элементы следующим образом.</span><span class="sxs-lookup"><span data-stu-id="fd62b-356">Here is how we create an `ArrayList` and add items to it.</span></span>

```powershell
$myarray = [System.Collections.ArrayList]::new()
[void]$myArray.Add('Value')
```

<span data-ttu-id="fd62b-357">Для получения этого типа вызывается .NET.</span><span class="sxs-lookup"><span data-stu-id="fd62b-357">We are calling into .NET to get this type.</span></span> <span data-ttu-id="fd62b-358">В этом случае для его создания используется конструктор по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fd62b-358">In this case, we are using the default constructor to create it.</span></span> <span data-ttu-id="fd62b-359">Затем вызывается метод `Add`, чтобы добавить в него элемент.</span><span class="sxs-lookup"><span data-stu-id="fd62b-359">Then we call the `Add` method to add an item to it.</span></span>

<span data-ttu-id="fd62b-360">Причина, по которой я использую `[void]` в начале строки, заключается в подавлении кода возврата.</span><span class="sxs-lookup"><span data-stu-id="fd62b-360">The reason I'm using `[void]` at the beginning of the line is to suppress the return code.</span></span> <span data-ttu-id="fd62b-361">Некоторые вызовы .NET выполняют такую функцию, и в результате могут быт получены неожиданные выходные данные.</span><span class="sxs-lookup"><span data-stu-id="fd62b-361">Some .NET calls do this and can create unexpected output.</span></span>

<span data-ttu-id="fd62b-362">Если единственными данными в массиве являются строки, ознакомьтесь также с использованием [StringBuilder][].</span><span class="sxs-lookup"><span data-stu-id="fd62b-362">If the only data that you have in your array is strings, then also take a look at using [StringBuilder][].</span></span> <span data-ttu-id="fd62b-363">Это практически то же самое, но некоторые методы предназначены только для работы со строками.</span><span class="sxs-lookup"><span data-stu-id="fd62b-363">It's almost the same thing but has some methods that are just for dealing with strings.</span></span> <span data-ttu-id="fd62b-364">`StringBuilder` специально предназначен для повышения производительности.</span><span class="sxs-lookup"><span data-stu-id="fd62b-364">The `StringBuilder` is specially designed for performance.</span></span>

<span data-ttu-id="fd62b-365">Обычно пользователи переходят на `ArrayList` с массивов.</span><span class="sxs-lookup"><span data-stu-id="fd62b-365">It's common to see people move to `ArrayList` from arrays.</span></span> <span data-ttu-id="fd62b-366">Однако это наследие тех времен, когда в C# еще не была предусмотрена универсальная поддержка.</span><span class="sxs-lookup"><span data-stu-id="fd62b-366">But it comes from a time where C# didn't have generic support.</span></span> <span data-ttu-id="fd62b-367">От `ArrayList` отказываются в пользу универсального `List[]`</span><span class="sxs-lookup"><span data-stu-id="fd62b-367">The `ArrayList` is deprecated in support for the generic `List[]`</span></span>

### <a name="generic-list"></a><span data-ttu-id="fd62b-368">Универсальный список</span><span class="sxs-lookup"><span data-stu-id="fd62b-368">Generic List</span></span>

<span data-ttu-id="fd62b-369">Универсальный тип — это особый тип в C#, который определяет обобщенный класс, при этом пользователь указывает типы данных, которые используются в процессе создания.</span><span class="sxs-lookup"><span data-stu-id="fd62b-369">A generic type is a special type in C# that defines a generalized class and the user specifies the data types it uses when created.</span></span> <span data-ttu-id="fd62b-370">Поэтому если требуется список чисел или строк, необходимо определить, что требуется список типов `int` или `string`.</span><span class="sxs-lookup"><span data-stu-id="fd62b-370">So if you want a list of numbers or strings, you would define that you want list of `int` or `string` types.</span></span>

<span data-ttu-id="fd62b-371">Список для строк создается следующим образом.</span><span class="sxs-lookup"><span data-stu-id="fd62b-371">Here is how you create a List for strings.</span></span>

```powershell
$mylist = [System.Collections.Generic.List[string]]::new()
```

<span data-ttu-id="fd62b-372">Так же создается список чисел.</span><span class="sxs-lookup"><span data-stu-id="fd62b-372">Or a list for numbers.</span></span>

```powershell
$mylist = [System.Collections.Generic.List[int]]::new()
```

<span data-ttu-id="fd62b-373">Можно привести существующий массив к списку следующим образом, не создавая сначала объект:</span><span class="sxs-lookup"><span data-stu-id="fd62b-373">We can cast an existing array to a list like this without creating the object first:</span></span>

```powershell
$mylist = [System.Collections.Generic.List[int]]@(1,2,3)
```

<span data-ttu-id="fd62b-374">Синтаксис можно сократить с помощью оператора `using namespace` в PowerShell 5 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="fd62b-374">We can shorten the syntax with the `using namespace` statement in PowerShell 5 and newer.</span></span> <span data-ttu-id="fd62b-375">Оператор `using` должен быть первой строкой сценария.</span><span class="sxs-lookup"><span data-stu-id="fd62b-375">The `using` statement needs to be the first line of your script.</span></span> <span data-ttu-id="fd62b-376">Объявляя пространство имен, PowerShell позволяет исключить из него типы данных при ссылке на них.</span><span class="sxs-lookup"><span data-stu-id="fd62b-376">By declaring a namespace, PowerShell lets you leave it off of the data types when you reference them.</span></span>

```powershell
using namespace System.Collections.Generic
$myList = [List[int]]@(1,2,3)
```

<span data-ttu-id="fd62b-377">Это позволяет сделать `List` гораздо более удобным.</span><span class="sxs-lookup"><span data-stu-id="fd62b-377">This makes the `List` much more usable.</span></span>

<span data-ttu-id="fd62b-378">Вам доступен аналогичный метод `Add`.</span><span class="sxs-lookup"><span data-stu-id="fd62b-378">You have a similar `Add` method available to you.</span></span> <span data-ttu-id="fd62b-379">В отличие от ArrayList метод `Add` не возвращает значение, поэтому для него не нужно выполнять `void`.</span><span class="sxs-lookup"><span data-stu-id="fd62b-379">Unlike the ArrayList, there is no return value on the `Add` method so we don't have to `void` it.</span></span>

```powershell
$myList.Add(10)
```

<span data-ttu-id="fd62b-380">Кроме того, мы по-прежнему можем получить доступ к таким элементам, как другие массивы.</span><span class="sxs-lookup"><span data-stu-id="fd62b-380">And we can still access the elements like other arrays.</span></span>

```powershell
PS> $myList[-1]
10
```

#### <a name="listpsobject"></a><span data-ttu-id="fd62b-381">List[PSObject]</span><span class="sxs-lookup"><span data-stu-id="fd62b-381">List[PSObject]</span></span>

<span data-ttu-id="fd62b-382">Можно получить список любого типа, но, если вам неизвестен тип объектов, в качестве контейнера для них можно использовать `[List[PSObject]]`.</span><span class="sxs-lookup"><span data-stu-id="fd62b-382">You can have a list of any type, but when you don't know the type of objects, you can use `[List[PSObject]]` to contain them.</span></span>

```powershell
$list = [List[PSObject]]::new()
```

#### <a name="remove"></a><span data-ttu-id="fd62b-383">Remove()</span><span class="sxs-lookup"><span data-stu-id="fd62b-383">Remove()</span></span>

<span data-ttu-id="fd62b-384">Как `ArrayList`, так и универсальные `List[]` поддерживают удаление элементов из коллекции.</span><span class="sxs-lookup"><span data-stu-id="fd62b-384">The `ArrayList` and the generic `List[]` both support removing items from the collection.</span></span>

```powershell
using namespace System.Collections.Generic
$myList = [List[string]]@('Zero','One','Two','Three')
[void]$myList.Remove("Two")
Zero
One
Three
```

<span data-ttu-id="fd62b-385">При работе с типами значений из списка удаляется первый из типов.</span><span class="sxs-lookup"><span data-stu-id="fd62b-385">When working with value types, it removes the first one from the list.</span></span> <span data-ttu-id="fd62b-386">Его можно вызвать снова, чтобы еще раз удалить это значение.</span><span class="sxs-lookup"><span data-stu-id="fd62b-386">You can call it over and over again to keep removing that value.</span></span> <span data-ttu-id="fd62b-387">Если используются ссылочные типы, необходимо предоставить объект, который требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="fd62b-387">If you have reference types, you have to provide the object that you want removed.</span></span>

```powershell
[list[System.Management.Automation.PSDriveInfo]]$drives = Get-PSDrive
$drives.remove($drives[2])
```

```powershell
$delete = $drives[2]
$drives.remove($delete)
```

<span data-ttu-id="fd62b-388">Метод Remove возвращает `true`, если удалось найти и удалить элемент из коллекции.</span><span class="sxs-lookup"><span data-stu-id="fd62b-388">The remove method returns `true` if it was able to find and remove the item from the collection.</span></span>

### <a name="more-collections"></a><span data-ttu-id="fd62b-389">Другие коллекции</span><span class="sxs-lookup"><span data-stu-id="fd62b-389">More collections</span></span>

<span data-ttu-id="fd62b-390">Можно использовать также множество других коллекций, однако эти оптимальны в качестве замены массивам.</span><span class="sxs-lookup"><span data-stu-id="fd62b-390">There are many other collections that can be used but these are the good generic array replacements.</span></span>
<span data-ttu-id="fd62b-391">Если вам интересно узнать больше о других вариантах, взгляните на [Gist](https://gist.github.com/kevinblumenfeld/4a698dbc90272a336ed9367b11d91f1c), собранный [Марком Краусом](https://get-powershellblog.blogspot.com/2016/11/about-mark-kraus.html).</span><span class="sxs-lookup"><span data-stu-id="fd62b-391">If you're interested in learning about more of these options, take a look at this [Gist](https://gist.github.com/kevinblumenfeld/4a698dbc90272a336ed9367b11d91f1c) that [Mark Kraus](https://get-powershellblog.blogspot.com/2016/11/about-mark-kraus.html) put together.</span></span>

## <a name="other-nuances"></a><span data-ttu-id="fd62b-392">Другие особенности</span><span class="sxs-lookup"><span data-stu-id="fd62b-392">Other nuances</span></span>

<span data-ttu-id="fd62b-393">Итак, мы рассмотрели все основные функции, и вот еще кое-что, о чем я хотел рассказать, прежде чем мы закончим.</span><span class="sxs-lookup"><span data-stu-id="fd62b-393">Now that I have covered all the major functionality, here are a few more things that I wanted to mention before I wrap this up.</span></span>

### <a name="pre-sized-arrays"></a><span data-ttu-id="fd62b-394">Массивы с предварительно заданным размером</span><span class="sxs-lookup"><span data-stu-id="fd62b-394">Pre-sized arrays</span></span>

<span data-ttu-id="fd62b-395">Я уже говорил, что вы не сможете изменить размер массива после того, как он создан.</span><span class="sxs-lookup"><span data-stu-id="fd62b-395">I mentioned that you can't change the size of an array once it's created.</span></span> <span data-ttu-id="fd62b-396">Можно создать массив с предварительно заданным размером, вызвав его с помощью конструктора `new($size)`.</span><span class="sxs-lookup"><span data-stu-id="fd62b-396">We can create an array of a pre-determined size by calling it with the `new($size)` constructor.</span></span>

```powershell
$data = [Object[]]::new(4)
$data.count
4
```

### <a name="multiplying-arrays"></a><span data-ttu-id="fd62b-397">Умножение массивов</span><span class="sxs-lookup"><span data-stu-id="fd62b-397">Multiplying arrays</span></span>

<span data-ttu-id="fd62b-398">Еще один интересный прием — массив можно умножить на целое число.</span><span class="sxs-lookup"><span data-stu-id="fd62b-398">An interesting little trick is that you can multiply an array by an integer.</span></span>

```powershell
PS> $data = @('red','green','blue')
PS> $data * 3
red
green
blue
red
green
blue
red
green
blue
```

### <a name="initialize-with-0"></a><span data-ttu-id="fd62b-399">Инициализация с нулевыми значениями</span><span class="sxs-lookup"><span data-stu-id="fd62b-399">Initialize with 0</span></span>

<span data-ttu-id="fd62b-400">Один из распространенных сценариев предполагает создание массива, заполненного нулевыми значениями.</span><span class="sxs-lookup"><span data-stu-id="fd62b-400">A common scenario is that you want to create an array with all zeros.</span></span> <span data-ttu-id="fd62b-401">Если планируется использовать только целые числа, строго типизированный массив целых чисел по умолчанию принимает все значения равными нулю.</span><span class="sxs-lookup"><span data-stu-id="fd62b-401">If you're only going to have integers, a strongly typed array of integers defaults to all zeros.</span></span>

```powershell
PS> [int[]]::new(4)
0
0
0
0
```

<span data-ttu-id="fd62b-402">Для этого также можно использовать умножение.</span><span class="sxs-lookup"><span data-stu-id="fd62b-402">We can use the multiplying trick to do this too.</span></span>

```powershell
PS> $data = @(0) * 4
PS> $data
0
0
0
0
```

<span data-ttu-id="fd62b-403">Особенно полезно в умножении то, что можно использовать любое значение.</span><span class="sxs-lookup"><span data-stu-id="fd62b-403">The nice thing about the multiplying trick is that you can use any value.</span></span> <span data-ttu-id="fd62b-404">Поэтому если планируется по умолчанию использовать значение `255`, это будет хорошим вариантом.</span><span class="sxs-lookup"><span data-stu-id="fd62b-404">So if you would rather have `255` as your default value, this would be a good way to do it.</span></span>

```powershell
PS> $data = @(255) * 4
PS> $data
255
255
255
255
```

### <a name="nested-arrays"></a><span data-ttu-id="fd62b-405">Вложенные массивы</span><span class="sxs-lookup"><span data-stu-id="fd62b-405">Nested arrays</span></span>

<span data-ttu-id="fd62b-406">Массив внутри массива называется вложенным массивом.</span><span class="sxs-lookup"><span data-stu-id="fd62b-406">An array inside an array is called a nested array.</span></span> <span data-ttu-id="fd62b-407">Я не использую их в PowerShell, но часто использовал в других языках.</span><span class="sxs-lookup"><span data-stu-id="fd62b-407">I don't use these much in PowerShell but I have used them more in other languages.</span></span> <span data-ttu-id="fd62b-408">Использовать массив массивов рекомендуется, если данные вписываются в шаблон типа сетки.</span><span class="sxs-lookup"><span data-stu-id="fd62b-408">Consider using an array of arrays when your data fits in a grid like pattern.</span></span>

<span data-ttu-id="fd62b-409">Существует два способа создания двумерного массива.</span><span class="sxs-lookup"><span data-stu-id="fd62b-409">Here are two ways we can create a two-dimensional array.</span></span>

```powershell
$data = @(@(1,2,3),@(4,5,6),@(7,8,9))

$data2 = @(
    @(1,2,3),
    @(4,5,6),
    @(7,8,9)
)
```

<span data-ttu-id="fd62b-410">В этих примерах очень важно использовать запятую.</span><span class="sxs-lookup"><span data-stu-id="fd62b-410">The comma is very important in those examples.</span></span> <span data-ttu-id="fd62b-411">Ранее я приводил пример обычного массива из нескольких строк, где использование запятой не было обязательным.</span><span class="sxs-lookup"><span data-stu-id="fd62b-411">I gave an earlier example of a normal array on multiple lines where the comma was optional.</span></span> <span data-ttu-id="fd62b-412">В случае с многомерным массивом все иначе.</span><span class="sxs-lookup"><span data-stu-id="fd62b-412">That isn't the case with a multi-dimensional array.</span></span>

<span data-ttu-id="fd62b-413">Для вложенного массива нотация индексов имеет некоторые изменения.</span><span class="sxs-lookup"><span data-stu-id="fd62b-413">The way we use the index notation changes slightly now that we've a nested array.</span></span> <span data-ttu-id="fd62b-414">Мы получаем значение 3, используя `$data` выше.</span><span class="sxs-lookup"><span data-stu-id="fd62b-414">Using the `$data` above, this is how we would access the value 3.</span></span>

```powershell
PS> $outside = 0
PS> $inside = 2
PS> $data[$outside][$inside]
3
```

<span data-ttu-id="fd62b-415">Добавьте набор скобок для каждого уровня вложенности массива.</span><span class="sxs-lookup"><span data-stu-id="fd62b-415">Add a set of bracket for each level of array nesting.</span></span> <span data-ttu-id="fd62b-416">Первый набор квадратных скобок предназначен для внешнего массива, а после этого можно работать уже из него.</span><span class="sxs-lookup"><span data-stu-id="fd62b-416">The first set of brackets is for the outer most array and then you work your way in from there.</span></span>

### <a name="write-output--noenumerate"></a><span data-ttu-id="fd62b-417">Write-Output -NoEnumerate</span><span class="sxs-lookup"><span data-stu-id="fd62b-417">Write-Output -NoEnumerate</span></span>

<span data-ttu-id="fd62b-418">В PowerShell часто используется перечисление массивов и их разворачивание.</span><span class="sxs-lookup"><span data-stu-id="fd62b-418">PowerShell likes to unwrap or enumerate arrays.</span></span> <span data-ttu-id="fd62b-419">Это ключевой момент в использовании конвейера в PowerShell, однако бывают случаи, когда это нежелательно.</span><span class="sxs-lookup"><span data-stu-id="fd62b-419">This is a core aspect of the way PowerShell uses the pipeline but there are times that you don't want that to happen.</span></span>

<span data-ttu-id="fd62b-420">Обычно я передаю объекты в `Get-Member`, чтобы получить дополнительные сведения о них.</span><span class="sxs-lookup"><span data-stu-id="fd62b-420">I commonly pipe objects to `Get-Member` to learn more about them.</span></span> <span data-ttu-id="fd62b-421">Когда я передаю туда массив, выполняется его разворачивание, и Get-Member видит элементы массива, а не фактический массив.</span><span class="sxs-lookup"><span data-stu-id="fd62b-421">When I pipe an array to it, it gets unwrapped and Get-Member sees the members of the array and not the actual array.</span></span>

```powershell
PS> $data = @('red','green','blue')
PS> $data | Get-Member
TypeName: System.String
...
```

<span data-ttu-id="fd62b-422">Чтобы запретить разворачивание массива, можно использовать `Write-Object -NoEnumerate`.</span><span class="sxs-lookup"><span data-stu-id="fd62b-422">To prevent that unwrap of the array, you can use `Write-Object -NoEnumerate`.</span></span>

```powershell
PS> Write-Output -NoEnumerate $data | Get-Member
TypeName: System.Object[]
...
```

<span data-ttu-id="fd62b-423">Есть еще один способ, который больше напоминает взлом (а я пытаюсь избежать таких взломов).</span><span class="sxs-lookup"><span data-stu-id="fd62b-423">I have a second way that's more of a hack (and I try to avoid hacks like this).</span></span> <span data-ttu-id="fd62b-424">Перед передачей массива можно поставить запятую в его начале.</span><span class="sxs-lookup"><span data-stu-id="fd62b-424">You can place a comma in front of the array before you pipe it.</span></span>

```powershell
PS> ,$data | Get-Member
TypeName: System.Object[]
...
```

### <a name="return-an-array"></a><span data-ttu-id="fd62b-425">Возврат массива</span><span class="sxs-lookup"><span data-stu-id="fd62b-425">Return an array</span></span>

<span data-ttu-id="fd62b-426">Такое разворачивание массивов также выполняется при выводе или возврате значений из функции.</span><span class="sxs-lookup"><span data-stu-id="fd62b-426">This unwrapping of arrays also happens when you output or return values from a function.</span></span> <span data-ttu-id="fd62b-427">Для получения массива по-прежнему можно присвоить выходные данные переменной, что обычно не вызывает проблем.</span><span class="sxs-lookup"><span data-stu-id="fd62b-427">You can still get an array if you assign the output to a variable so this isn't commonly an issue.</span></span>

<span data-ttu-id="fd62b-428">Хитрость в том, что создается новый массив.</span><span class="sxs-lookup"><span data-stu-id="fd62b-428">The catch is that you have a new array.</span></span> <span data-ttu-id="fd62b-429">Если это проблематично, можно решить проблему с помощью `Write-Output -NoEnumerate $array` или `return ,$array`.</span><span class="sxs-lookup"><span data-stu-id="fd62b-429">If that is ever a problem, you can use `Write-Output -NoEnumerate $array` or `return ,$array` to work around it.</span></span>

## <a name="anything-else"></a><span data-ttu-id="fd62b-430">Что-нибудь еще?</span><span class="sxs-lookup"><span data-stu-id="fd62b-430">Anything else?</span></span>

<span data-ttu-id="fd62b-431">Я знаю, что придется усвоить довольно большой объем информации.</span><span class="sxs-lookup"><span data-stu-id="fd62b-431">I know this is all a lot to take in.</span></span> <span data-ttu-id="fd62b-432">Но я надеюсь, что при каждом прочтении этой статьи вы будете узнавать что-то новое и эти знания окажутся полезными в долгосрочной перспективе.</span><span class="sxs-lookup"><span data-stu-id="fd62b-432">My hope is that you learn something from this article every time you read it and that it turns out to be a good reference for you for a long time to come.</span></span> <span data-ttu-id="fd62b-433">Если для вас эта статья была полезна, поделитесь ею с коллегами, которым она также может быть интересна.</span><span class="sxs-lookup"><span data-stu-id="fd62b-433">If you found this to be helpful, please share it with others you think may get value out of it.</span></span>

<span data-ttu-id="fd62b-434">Здесь, кстати, я рекомендую ознакомиться с похожей публикацией, посвященной [хэш-таблицам][].</span><span class="sxs-lookup"><span data-stu-id="fd62b-434">From here, I would recommend you check out a similar post that I wrote about [hashtables][].</span></span>

<!-- link references -->
[Оригинал]: https://powershellexplained.com/2018-10-15-Powershell-arrays-Everything-you-wanted-to-know/
[original version]: https://powershellexplained.com/2018-10-15-Powershell-arrays-Everything-you-wanted-to-know/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[Массивы]: /powershell/module/microsoft.powershell.core/about/about_arrays
[Arrays]: /powershell/module/microsoft.powershell.core/about/about_arrays
[Оператор switch]: everything-about-switch.md
[switch statement]: everything-about-switch.md
[хэш-таблицам]: everything-about-hashtable.md
[hashtables]: everything-about-hashtable.md
[Множество способов использования регулярных выражений]: https://powershellexplained.com/2017-07-31-Powershell-regex-regular-expression/
[The many ways to use regex]: https://powershellexplained.com/2017-07-31-Powershell-regex-regular-expression/
[как проверить, соответствует ли каждое значение в массиве заданному значению]: https://www.reddit.com/r/PowerShell/comments/9mzo09/if_statement_multiple_variables_but_1_condition
[how to verify that every value in an array matches a given value]: https://www.reddit.com/r/PowerShell/comments/9mzo09/if_statement_multiple_variables_but_1_condition
[решение]: https://www.reddit.com/r/PowerShell/comments/9mzo09/if_statement_multiple_variables_but_1_condition/e7iizca
[solution]: https://www.reddit.com/r/PowerShell/comments/9mzo09/if_statement_multiple_variables_but_1_condition/e7iizca
[StringBuilder]: https://powershellexplained.com/2017-11-20-Powershell-StringBuilder/
