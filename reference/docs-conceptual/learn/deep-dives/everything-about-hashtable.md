---
title: Все, что вы хотели знать о хэш-таблицах
description: Хэш-таблицы играют очень важную роль в PowerShell, поэтому будет полезно получить о них полное представление.
ms.date: 05/23/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: 1539cf6444cab718c1108384c640193d66c85daf
ms.sourcegitcommit: 39c2a697228276d5dae39e540995fa479c2b5f39
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2020
ms.locfileid: "93354428"
---
# <a name="everything-you-wanted-to-know-about-hashtables"></a><span data-ttu-id="8a95a-103">Все, что вы хотели знать о хэш-таблицах</span><span class="sxs-lookup"><span data-stu-id="8a95a-103">Everything you wanted to know about hashtables</span></span>

<span data-ttu-id="8a95a-104">Я хочу вернуться на шаг назад и поговорить о [хэш-таблицах][].</span><span class="sxs-lookup"><span data-stu-id="8a95a-104">I want to take a step back and talk about [hashtables][].</span></span> <span data-ttu-id="8a95a-105">Теперь я использую их все время.</span><span class="sxs-lookup"><span data-stu-id="8a95a-105">I use them all the time now.</span></span> <span data-ttu-id="8a95a-106">Вчера вечером я объяснял человеку принцип их работы после встречи с группой пользователей и понял, что я, так же как и мой слушатель, кое-что о них не понимаю.</span><span class="sxs-lookup"><span data-stu-id="8a95a-106">I was teaching someone about them after our user group meeting last night and I realized I had the same confusion about them as he had.</span></span> <span data-ttu-id="8a95a-107">Хэш-таблицы играют очень важную роль в PowerShell, поэтому будет полезно получить о них полное представление.</span><span class="sxs-lookup"><span data-stu-id="8a95a-107">Hashtables are really important in PowerShell so it's good to have a solid understanding of them.</span></span>

> [!NOTE]
> <span data-ttu-id="8a95a-108">[Оригинал][] этой статьи впервые был опубликован в блоге автора [@KevinMarquette][].</span><span class="sxs-lookup"><span data-stu-id="8a95a-108">The [original version][] of this article appeared on the blog written by [@KevinMarquette][].</span></span> <span data-ttu-id="8a95a-109">Группа разработчиков PowerShell благодарит Кевина за то, что он поделился с нами этими материалами.</span><span class="sxs-lookup"><span data-stu-id="8a95a-109">The PowerShell team thanks Kevin for sharing this content with us.</span></span> <span data-ttu-id="8a95a-110">Ознакомьтесь с его блогом на веб-сайте [PowerShellExplained.com][].</span><span class="sxs-lookup"><span data-stu-id="8a95a-110">Please check out his blog at [PowerShellExplained.com][].</span></span>

## <a name="hashtable-as-a-collection-of-things"></a><span data-ttu-id="8a95a-111">Хэш-таблица как коллекция объектов</span><span class="sxs-lookup"><span data-stu-id="8a95a-111">Hashtable as a collection of things</span></span>

<span data-ttu-id="8a95a-112">Я рекомендую рассматривать **хэш-таблицу** как коллекцию в традиционном определении термина хэш-таблицы.</span><span class="sxs-lookup"><span data-stu-id="8a95a-112">I want you to first see a **Hashtable** as a collection in the traditional definition of a hashtable.</span></span> <span data-ttu-id="8a95a-113">Это определение позволяет получить полное понимание их работы в случае последующего расширенного использования.</span><span class="sxs-lookup"><span data-stu-id="8a95a-113">This definition gives you a fundamental understanding of how they work when they get used for more advanced stuff later.</span></span> <span data-ttu-id="8a95a-114">Если изначально не понять этот момент, впоследствии можно запутаться.</span><span class="sxs-lookup"><span data-stu-id="8a95a-114">Skipping this understanding is often a source of confusion.</span></span>

## <a name="what-is-an-array"></a><span data-ttu-id="8a95a-115">Что такое массив?</span><span class="sxs-lookup"><span data-stu-id="8a95a-115">What is an array?</span></span>

<span data-ttu-id="8a95a-116">Прежде чем перейти к определению **хэш-таблицы** , нужно сначала рассказать о [массивах][].</span><span class="sxs-lookup"><span data-stu-id="8a95a-116">Before I jump into what a **Hashtable** is, I need to mention [arrays][] first.</span></span> <span data-ttu-id="8a95a-117">В рамках этого обсуждения массив понимается как список или коллекция значений или объектов.</span><span class="sxs-lookup"><span data-stu-id="8a95a-117">For the purpose of this discussion, an array is a list or collection of values or objects.</span></span>

```powershell
$array = @(1,2,3,5,7,11)
```

<span data-ttu-id="8a95a-118">После передачи элементов в массив можно использовать `foreach` для выполнения итерации по списку или индекс для доступа к отдельным элементам в массиве.</span><span class="sxs-lookup"><span data-stu-id="8a95a-118">Once you have your items into an array, you can either use `foreach` to iterate over the list or use an index to access individual elements in the array.</span></span>

```powershell
foreach($item in $array)
{
    Write-Output $item
}

Write-Output $array[3]
```

<span data-ttu-id="8a95a-119">Точно так же можно обновлять значения с помощью индекса.</span><span class="sxs-lookup"><span data-stu-id="8a95a-119">You can also update values using an index in the same way.</span></span>

```powershell
$array[2] = 13
```

<span data-ttu-id="8a95a-120">Я лишь поверхностно изложил понятие массивов, но при переходе к хэш-таблицам это позволит получить о них правильное представление.</span><span class="sxs-lookup"><span data-stu-id="8a95a-120">I just scratched the surface on arrays but that should put them into the right context as I move onto hashtables.</span></span>

## <a name="what-is-a-hashtable"></a><span data-ttu-id="8a95a-121">Что такое хэш-таблица?</span><span class="sxs-lookup"><span data-stu-id="8a95a-121">What is a hashtable?</span></span>

<span data-ttu-id="8a95a-122">Сначала я приведу основное техническое описание хэш-таблиц, а затем расскажу о других способах их использования в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8a95a-122">I'm going to start with a basic technical description of what hashtables are, in the general sense, before I shift into the other ways PowerShell uses them.</span></span>

<span data-ttu-id="8a95a-123">Хэш-таблица представляет собой структуру данных, во многом похожую на массив, за исключением того, что каждое значение (объект) сохраняется в ней с помощью ключа.</span><span class="sxs-lookup"><span data-stu-id="8a95a-123">A hashtable is a data structure, much like an array, except you store each value (object) using a key.</span></span> <span data-ttu-id="8a95a-124">Это базовое хранилище ключей и значений.</span><span class="sxs-lookup"><span data-stu-id="8a95a-124">It's a basic key/value store.</span></span> <span data-ttu-id="8a95a-125">Сначала мы создаем пустую хэш-таблицу.</span><span class="sxs-lookup"><span data-stu-id="8a95a-125">First, we create an empty hashtable.</span></span>

```powershell
$ageList = @{}
```

<span data-ttu-id="8a95a-126">Обратите внимание, что для определения хэш-таблицы используются фигурные скобки вместо круглых.</span><span class="sxs-lookup"><span data-stu-id="8a95a-126">Notice that braces, instead of parentheses, are used to define a hashtable.</span></span> <span data-ttu-id="8a95a-127">Затем мы добавляем элемент, используя следующий ключ:</span><span class="sxs-lookup"><span data-stu-id="8a95a-127">Then we add an item using a key like this:</span></span>

```powershell
$key = 'Kevin'
$value = 36
$ageList.add( $key, $value )

$ageList.add( 'Alex', 9 )
```

<span data-ttu-id="8a95a-128">Имя пользователя — ключ, а его возраст — это значение, которое я хочу сохранить.</span><span class="sxs-lookup"><span data-stu-id="8a95a-128">The person's name is the key and their age is the value that I want to save.</span></span>

## <a name="using-the-brackets-for-access"></a><span data-ttu-id="8a95a-129">Использование квадратных скобок для доступа</span><span class="sxs-lookup"><span data-stu-id="8a95a-129">Using the brackets for access</span></span>

<span data-ttu-id="8a95a-130">После добавления значений в хэш-таблицу можно перенести их обратно, используя тот же ключ (вместо числового индекса как для массива).</span><span class="sxs-lookup"><span data-stu-id="8a95a-130">Once you add your values to the hashtable, you can pull them back out using that same key (instead of using a numeric index like you would have for an array).</span></span>

```powershell
$ageList['Kevin']
$ageList['Alex']
```

<span data-ttu-id="8a95a-131">Если мне нужно узнать возраст Кевина, я указываю его имя для доступа.</span><span class="sxs-lookup"><span data-stu-id="8a95a-131">When I want Kevin's age, I use his name to access it.</span></span> <span data-ttu-id="8a95a-132">Этот подход также можно использовать для добавления или обновления значений в хэш-таблице.</span><span class="sxs-lookup"><span data-stu-id="8a95a-132">We can use this approach to add or update values into the hashtable too.</span></span> <span data-ttu-id="8a95a-133">Он похож на использование функции `add()`, описанной выше.</span><span class="sxs-lookup"><span data-stu-id="8a95a-133">This is just like using the `add()` function above.</span></span>

```powershell
$ageList = @{}

$key = 'Kevin'
$value = 36
$ageList[$key] = $value

$ageList['Alex'] = 9
```

<span data-ttu-id="8a95a-134">Кроме того, можно использовать для доступа и обновления значений другой синтаксис. Я расскажу о нем в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="8a95a-134">There's another syntax you can use for accessing and updating values that I'll cover in a later section.</span></span> <span data-ttu-id="8a95a-135">Если вы перешли на PowerShell с другого языка, скорее всего, раньше вы использовали хэш-таблицы примерно так же, как показано в этих примерах.</span><span class="sxs-lookup"><span data-stu-id="8a95a-135">If you're coming to PowerShell from another language, these examples should fit in with how you may have used hashtables before.</span></span>

### <a name="creating-hashtables-with-values"></a><span data-ttu-id="8a95a-136">Создание хэш-таблиц со значениями</span><span class="sxs-lookup"><span data-stu-id="8a95a-136">Creating hashtables with values</span></span>

<span data-ttu-id="8a95a-137">Пока я создал пустую хэш-таблицу для этих примеров.</span><span class="sxs-lookup"><span data-stu-id="8a95a-137">So far I've created an empty hashtable for these examples.</span></span> <span data-ttu-id="8a95a-138">При создании таблицы вы можете предварительно внести в нее ключи и значения.</span><span class="sxs-lookup"><span data-stu-id="8a95a-138">You can pre-populate the keys and values when you create them.</span></span>

```powershell
$ageList = @{
    Kevin = 36
    Alex  = 9
}
```

### <a name="as-a-lookup-table"></a><span data-ttu-id="8a95a-139">В качестве таблицы подстановки</span><span class="sxs-lookup"><span data-stu-id="8a95a-139">As a lookup table</span></span>

<span data-ttu-id="8a95a-140">Реальная ценность этого типа хэш-таблиц заключается в том, что их можно использовать в качестве таблиц подстановки.</span><span class="sxs-lookup"><span data-stu-id="8a95a-140">The real value of this type of a hashtable is that you can use them as a lookup table.</span></span> <span data-ttu-id="8a95a-141">Вот простой пример.</span><span class="sxs-lookup"><span data-stu-id="8a95a-141">Here is a simple example.</span></span>

```powershell
$environments = @{
    Prod = 'SrvProd05'
    QA   = 'SrvQA02'
    Dev  = 'SrvDev12'
}

$server = $environments[$env]
```

<span data-ttu-id="8a95a-142">В этом примере мы указываем среду для переменной `$env` и выбираем правильный сервер.</span><span class="sxs-lookup"><span data-stu-id="8a95a-142">In this example, you specify an environment for the `$env` variable and it will pick the correct server.</span></span> <span data-ttu-id="8a95a-143">Можно использовать `switch($env){...}` для такого выбора, однако хэш-таблица является не менее удобным способом.</span><span class="sxs-lookup"><span data-stu-id="8a95a-143">You could use a `switch($env){...}` for a selection like this but a hashtable is a nice option.</span></span>

<span data-ttu-id="8a95a-144">Она становится еще удобнее, если выполняется динамическое построение таблицы подстановки для последующего использования.</span><span class="sxs-lookup"><span data-stu-id="8a95a-144">This gets even better when you dynamically build the lookup table to use it later.</span></span> <span data-ttu-id="8a95a-145">То есть такой подход рекомендуется выбирать, если требуется создать перекрестную ссылку.</span><span class="sxs-lookup"><span data-stu-id="8a95a-145">So think about using this approach when you need to cross reference something.</span></span> <span data-ttu-id="8a95a-146">Я думаю, это было бы даже более очевидным, если бы PowerShell не обеспечивал настолько эффективную фильтрацию в канале за счет `Where-Object`.</span><span class="sxs-lookup"><span data-stu-id="8a95a-146">I think we would see this even more if PowerShell wasn't so good at filtering on the pipe with `Where-Object`.</span></span> <span data-ttu-id="8a95a-147">Этот подход стоит рассматривать, если для вас имеет значение производительность.</span><span class="sxs-lookup"><span data-stu-id="8a95a-147">If you're ever in a situation where performance matters, this approach needs to be considered.</span></span>

<span data-ttu-id="8a95a-148">Я бы не сказал, что это будет быстрее, однако указанный способ обеспечивает соответствие правилу [Если имеет значение производительность, протестируйте ее][].</span><span class="sxs-lookup"><span data-stu-id="8a95a-148">I won't say that it's faster, but it does fit into the rule of [If performance matters, test it][].</span></span>

#### <a name="multiselection"></a><span data-ttu-id="8a95a-149">Множественный выбор</span><span class="sxs-lookup"><span data-stu-id="8a95a-149">Multiselection</span></span>

<span data-ttu-id="8a95a-150">Обычно хэш-таблица рассматривается как пара "ключ-значение", где вы указываете один ключ и получаете одно значение.</span><span class="sxs-lookup"><span data-stu-id="8a95a-150">Generally, you think of a hashtable as a key/value pair, where you provide one key and get one value.</span></span> <span data-ttu-id="8a95a-151">PowerShell позволяет предоставить массив ключей, чтобы получить несколько значений.</span><span class="sxs-lookup"><span data-stu-id="8a95a-151">PowerShell allows you to provide an array of keys to get multiple values.</span></span>

```powershell
$environments[@('QA','DEV')]
$environments[('QA','DEV')]
$environments['QA','DEV']
```

<span data-ttu-id="8a95a-152">В этом примере я использую вышеописанную хэш-таблицу подстановки и указываю три различных стиля массива для получения совпадений.</span><span class="sxs-lookup"><span data-stu-id="8a95a-152">In this example, I use the same lookup hashtable from above and provide three different array styles to get the matches.</span></span> <span data-ttu-id="8a95a-153">Это скрытое преимущество PowerShell, о котором большинство пользователей не знает.</span><span class="sxs-lookup"><span data-stu-id="8a95a-153">This is a hidden gem in PowerShell that most people aren't aware of.</span></span>

## <a name="iterating-hashtables"></a><span data-ttu-id="8a95a-154">Итерация хэш-таблиц</span><span class="sxs-lookup"><span data-stu-id="8a95a-154">Iterating hashtables</span></span>

<span data-ttu-id="8a95a-155">Поскольку хэш-таблица представляет собой коллекцию пар "ключ-значение", итерация для них выполняется иначе, чем для массива или обычного списка элементов.</span><span class="sxs-lookup"><span data-stu-id="8a95a-155">Because a hashtable is a collection of key/value pairs, you iterate over it differently than you do for an array or a normal list of items.</span></span>

<span data-ttu-id="8a95a-156">Первое, что следует заметить, — при передаче хэш-таблицы по каналу он обрабатывает ее как один объект,</span><span class="sxs-lookup"><span data-stu-id="8a95a-156">The first thing to notice is that if you pipe your hashtable, the pipe treats it like one object.</span></span>

```powershell
PS> $ageList | Measure-Object
count : 1
```

<span data-ttu-id="8a95a-157">хотя при этом свойство `.count` сообщает, сколько значений он содержит.</span><span class="sxs-lookup"><span data-stu-id="8a95a-157">Even though the `.count` property tells you how many values it contains.</span></span>

```powershell
PS> $ageList.count
2
```

<span data-ttu-id="8a95a-158">Эту ошибку можно устранить с помощью свойства `.values`, если вам нужны только значения.</span><span class="sxs-lookup"><span data-stu-id="8a95a-158">You get around this issue by using the `.values` property if all you need is just the values.</span></span>

```powershell
PS> $ageList.values | Measure-Object -Average
Count   : 2
Average : 22.5
```

<span data-ttu-id="8a95a-159">Зачастую удобнее перечислить ключи и использовать их для доступа к значениям.</span><span class="sxs-lookup"><span data-stu-id="8a95a-159">It's often more useful to enumerate the keys and use them to access the values.</span></span>

```powershell
PS> $ageList.keys | ForEach-Object{
    $message = '{0} is {1} years old!' -f $_, $ageList[$_]
    Write-Output $message
}
Kevin is 36 years old
Alex is 9 years old
```

<span data-ttu-id="8a95a-160">Далее приведен тот же пример, в котором используется цикл `foreach(){...}`.</span><span class="sxs-lookup"><span data-stu-id="8a95a-160">Here is the same example with a `foreach(){...}` loop.</span></span>

```powershell
foreach($key in $ageList.keys)
{
    $message = '{0} is {1} years old' -f $key, $ageList[$key]
    Write-Output $message
}
```

<span data-ttu-id="8a95a-161">Мы выполняем обход всех ключей в хэш-таблице и используем их для доступа к значениям.</span><span class="sxs-lookup"><span data-stu-id="8a95a-161">We are walking each key in the hashtable and then using it to access the value.</span></span> <span data-ttu-id="8a95a-162">Это общий шаблон, используемый при работе с хэш-таблицами как с коллекциями.</span><span class="sxs-lookup"><span data-stu-id="8a95a-162">This is a common pattern when working with hashtables as a collection.</span></span>

### <a name="getenumerator"></a><span data-ttu-id="8a95a-163">GetEnumerator()</span><span class="sxs-lookup"><span data-stu-id="8a95a-163">GetEnumerator()</span></span>

<span data-ttu-id="8a95a-164">Таким образом, мы приходим к использованию `GetEnumerator()` для выполнения итерации нашей хэш-таблицы.</span><span class="sxs-lookup"><span data-stu-id="8a95a-164">That brings us to `GetEnumerator()` for iterating over our hashtable.</span></span>

```powershell
$ageList.GetEnumerator() | ForEach-Object{
    $message = '{0} is {1} years old!' -f $_.key, $_.value
    Write-Output $message
}
```

<span data-ttu-id="8a95a-165">Перечислитель выдает каждую пару "ключ-значение" по очереди.</span><span class="sxs-lookup"><span data-stu-id="8a95a-165">The enumerator gives you each key/value pair one after another.</span></span> <span data-ttu-id="8a95a-166">Он специально разработан для такого варианта использования.</span><span class="sxs-lookup"><span data-stu-id="8a95a-166">It was designed specifically for this use case.</span></span> <span data-ttu-id="8a95a-167">Спасибо [Марку Краусу](https://get-PowerShellblog.blogspot.com) за то, что напомнил мне об этом.</span><span class="sxs-lookup"><span data-stu-id="8a95a-167">Thank you to [Mark Kraus](https://get-PowerShellblog.blogspot.com) for reminding me of this one.</span></span>

### <a name="badenumeration"></a><span data-ttu-id="8a95a-168">BadEnumeration</span><span class="sxs-lookup"><span data-stu-id="8a95a-168">BadEnumeration</span></span>

<span data-ttu-id="8a95a-169">Важный момент: вы можете изменить хэш-таблицу в ходе ее перечисления.</span><span class="sxs-lookup"><span data-stu-id="8a95a-169">One important detail is that you can't modify a hashtable while it's being enumerated.</span></span> <span data-ttu-id="8a95a-170">Если начать с нашего основного примера `$environments`:</span><span class="sxs-lookup"><span data-stu-id="8a95a-170">If we start with our basic `$environments` example:</span></span>

```powershell
$environments = @{
    Prod = 'SrvProd05'
    QA   = 'SrvQA02'
    Dev  = 'SrvDev12'
}
```

<span data-ttu-id="8a95a-171">Попытка задать для каждого ключа одно и то же значение сервера завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="8a95a-171">And trying to set every key to the same server value fails.</span></span>

```powershell
$environments.Keys | ForEach-Object {
    $environments[$_] = 'SrvDev03'
}

An error occurred while enumerating through a collection: Collection was modified; enumeration operation may not execute.
+ CategoryInfo          : InvalidOperation: tableEnumerator:HashtableEnumerator) [], RuntimeException
+ FullyQualifiedErrorId : BadEnumeration
```

<span data-ttu-id="8a95a-172">Это также приведет к сбою, даже если на первый взгляд все выглядит корректно:</span><span class="sxs-lookup"><span data-stu-id="8a95a-172">This will also fail even though it looks like it should also be fine:</span></span>

```powershell
foreach($key in $environments.keys) {
    $environments[$key] = 'SrvDev03'
}

Collection was modified; enumeration operation may not execute.
    + CategoryInfo          : OperationStopped: (:) [], InvalidOperationException
    + FullyQualifiedErrorId : System.InvalidOperationException
```

<span data-ttu-id="8a95a-173">в этой ситуации хитрость заключается в клонировании ключей до выполнения перечисления.</span><span class="sxs-lookup"><span data-stu-id="8a95a-173">The trick to this situation is to clone the keys before doing the enumeration.</span></span>

```powershell
$environments.Keys.Clone() | ForEach-Object {
    $environments[$_] = 'SrvDev03'
}
```

## <a name="hashtable-as-a-collection-of-properties"></a><span data-ttu-id="8a95a-174">Хэш-таблица как коллекция свойств</span><span class="sxs-lookup"><span data-stu-id="8a95a-174">Hashtable as a collection of properties</span></span>

<span data-ttu-id="8a95a-175">Пока что в нашу хэш-таблицу помещались объекты одинакового типа.</span><span class="sxs-lookup"><span data-stu-id="8a95a-175">So far the type of objects we placed in our hashtable were all the same type of object.</span></span> <span data-ttu-id="8a95a-176">Я использовал данные о возрасте во всех этих примерах, а в качестве ключа использовалось имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="8a95a-176">I used ages in all those examples and the key was the person's name.</span></span> <span data-ttu-id="8a95a-177">Это отличный способ изучения данных, если в коллекции объектов у каждого объекта есть имя.</span><span class="sxs-lookup"><span data-stu-id="8a95a-177">This is a great way to look at it when your collection of objects each have a name.</span></span> <span data-ttu-id="8a95a-178">Еще один распространенный способ использования хэш-таблиц в PowerShell — хранение коллекции свойств, где ключом является имя свойства.</span><span class="sxs-lookup"><span data-stu-id="8a95a-178">Another common way to use hashtables in PowerShell is to hold a collection of properties where the key is the name of the property.</span></span> <span data-ttu-id="8a95a-179">В следующем примере я расскажу об этом подробнее.</span><span class="sxs-lookup"><span data-stu-id="8a95a-179">I'll step into that idea in this next example.</span></span>

### <a name="property-based-access"></a><span data-ttu-id="8a95a-180">Доступ на основе свойств</span><span class="sxs-lookup"><span data-stu-id="8a95a-180">Property-based access</span></span>

<span data-ttu-id="8a95a-181">Использование доступа на основе свойств меняет динамику хэш-таблиц и способ их использования в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8a95a-181">The use of property-based access changes the dynamics of hashtables and how you can use them in PowerShell.</span></span> <span data-ttu-id="8a95a-182">Вот типичный пример, в котором ключи обрабатываются как свойства.</span><span class="sxs-lookup"><span data-stu-id="8a95a-182">Here is our usual example from above treating the keys as properties.</span></span>

```powershell
$ageList = @{}
$ageList.Kevin = 35
$ageList.Alex = 9
```

<span data-ttu-id="8a95a-183">Как и в примерах выше, в этом примере такие ключи добавляются, если только они еще не существуют в хэш-таблице.</span><span class="sxs-lookup"><span data-stu-id="8a95a-183">Just like the examples above, this example adds those keys if they don't exist in the hashtable already.</span></span> <span data-ttu-id="8a95a-184">В зависимости от того, как определены ключи и какие используются значения, такой способ либо выглядит немного странным, либо идеально решает задачу.</span><span class="sxs-lookup"><span data-stu-id="8a95a-184">Depending on how you defined your keys and what your values are, this is either a little strange or a perfect fit.</span></span> <span data-ttu-id="8a95a-185">До этого момента пример списка данных о возрасте отлично подходил.</span><span class="sxs-lookup"><span data-stu-id="8a95a-185">The age list example has worked great up until this point.</span></span> <span data-ttu-id="8a95a-186">Теперь нам нужен новый пример.</span><span class="sxs-lookup"><span data-stu-id="8a95a-186">We need a new example for this to feel right going forward.</span></span>

```powershell
$person = @{
    name = 'Kevin'
    age  = 36
}
```

<span data-ttu-id="8a95a-187">Кроме того, мы можем добавлять атрибуты в `$person` и обращаться к ним следующим образом.</span><span class="sxs-lookup"><span data-stu-id="8a95a-187">And we can add and access attributes on the `$person` like this.</span></span>

```powershell
$person.city = 'Austin'
$person.state = 'TX'
```

<span data-ttu-id="8a95a-188">Внезапно оказывается, что эта хэш-таблица начинает работать как объект.</span><span class="sxs-lookup"><span data-stu-id="8a95a-188">All of a sudden this hashtable starts to feel and act like an object.</span></span> <span data-ttu-id="8a95a-189">Это все еще коллекция, так что все примеры по-прежнему применимы.</span><span class="sxs-lookup"><span data-stu-id="8a95a-189">It's still a collection of things, so all the examples above still apply.</span></span> <span data-ttu-id="8a95a-190">Мы просто рассматриваем ее с другой точки зрения.</span><span class="sxs-lookup"><span data-stu-id="8a95a-190">We just approach it from a different point of view.</span></span>

### <a name="checking-for-keys-and-values"></a><span data-ttu-id="8a95a-191">Проверка ключей и значений</span><span class="sxs-lookup"><span data-stu-id="8a95a-191">Checking for keys and values</span></span>

<span data-ttu-id="8a95a-192">В большинстве случаев можно протестировать значение примерно таким способом:</span><span class="sxs-lookup"><span data-stu-id="8a95a-192">In most cases, you can just test for the value with something like this:</span></span>

```powershell
if( $person.age ){...}
```

<span data-ttu-id="8a95a-193">Это довольно просто, но для меня оказалось чревато множеством ошибок, потому что я в своей логике не учитывал один важный момент.</span><span class="sxs-lookup"><span data-stu-id="8a95a-193">It's simple but has been the source of many bugs for me because I was overlooking one important detail in my logic.</span></span> <span data-ttu-id="8a95a-194">Я использовал этот метод для тестирования, если был доступен ключ.</span><span class="sxs-lookup"><span data-stu-id="8a95a-194">I started to use it to test if a key was present.</span></span> <span data-ttu-id="8a95a-195">Если значение равнялось `$false` или нулю, этот оператор неожиданно возвращал `$false`.</span><span class="sxs-lookup"><span data-stu-id="8a95a-195">When the value was `$false` or zero, that statement would return `$false` unexpectedly.</span></span>

```powershell
if( $person.age -ne $null ){...}
```

<span data-ttu-id="8a95a-196">Это позволяет решить проблему для нулевых значений, но не сравнивает $null с несуществующими ключами.</span><span class="sxs-lookup"><span data-stu-id="8a95a-196">This works around that issue for zero values but not $null vs non-existent keys.</span></span> <span data-ttu-id="8a95a-197">В большинстве случаев это одно и то же, но для некоторых функций такая процедура необходима.</span><span class="sxs-lookup"><span data-stu-id="8a95a-197">Most of the time you don't need to make that distinction but there are functions for when you do.</span></span>

```powershell
if( $person.ContainsKey('age') ){...}
```

<span data-ttu-id="8a95a-198">Кроме того, мы используем `ContainsValue()` в ситуациях, когда требуется проверить значение, не имея данных о ключе, или выполнить итерацию для всей коллекции.</span><span class="sxs-lookup"><span data-stu-id="8a95a-198">We also have a `ContainsValue()` for the situation where you need to test for a value without knowing the key or iterating the whole collection.</span></span>

### <a name="removing-and-clearing-keys"></a><span data-ttu-id="8a95a-199">Удаление и очистка ключей</span><span class="sxs-lookup"><span data-stu-id="8a95a-199">Removing and clearing keys</span></span>

<span data-ttu-id="8a95a-200">Ключи можно удалить с помощью функции `.Remove()`.</span><span class="sxs-lookup"><span data-stu-id="8a95a-200">You can remove keys with the `.Remove()` function.</span></span>

```powershell
$person.remove('age')
```

<span data-ttu-id="8a95a-201">Если присвоить им значение `$null`, просто получится ключ со значением `$null`.</span><span class="sxs-lookup"><span data-stu-id="8a95a-201">Assigning them a `$null` value just leaves you with a key that has a `$null` value.</span></span>

<span data-ttu-id="8a95a-202">Для очистки хэш-таблицы чаще всего используется ее инициализация как пустой хэш-таблицы.</span><span class="sxs-lookup"><span data-stu-id="8a95a-202">A common way to clear a hashtable is to just initialize it to an empty hashtable.</span></span>

```powershell
$person = @{}
```

<span data-ttu-id="8a95a-203">Хотя это вполне рабочий способ, все же рекомендуется вместо него попробовать функцию `clear()`.</span><span class="sxs-lookup"><span data-stu-id="8a95a-203">While that does work, try to use the `clear()` function instead.</span></span>

```powershell
$person.clear()
```

<span data-ttu-id="8a95a-204">Это один из тех случаев, когда использование функции создает самодокументируемый код, цель которого предельно ясна и понятна.</span><span class="sxs-lookup"><span data-stu-id="8a95a-204">This is one of those instances where using the function creates self-documenting code and it makes the intentions of the code very clean.</span></span>

## <a name="all-the-fun-stuff"></a><span data-ttu-id="8a95a-205">Все занятные вещи</span><span class="sxs-lookup"><span data-stu-id="8a95a-205">All the fun stuff</span></span>

### <a name="ordered-hashtables"></a><span data-ttu-id="8a95a-206">Упорядоченные хэш-таблицы</span><span class="sxs-lookup"><span data-stu-id="8a95a-206">Ordered hashtables</span></span>

<span data-ttu-id="8a95a-207">По умолчанию хэш-таблицы не упорядочиваются (не сортируются).</span><span class="sxs-lookup"><span data-stu-id="8a95a-207">By default, hashtables aren't ordered (or sorted).</span></span> <span data-ttu-id="8a95a-208">В традиционном контексте порядок не имеет значения, если для доступа к значениям всегда используется ключ.</span><span class="sxs-lookup"><span data-stu-id="8a95a-208">In the traditional context, the order doesn't matter when you always use a key to access values.</span></span> <span data-ttu-id="8a95a-209">Возможно, вам потребуется сохранить ранее определенный порядок свойств.</span><span class="sxs-lookup"><span data-stu-id="8a95a-209">You may find that you want the properties to stay in the order that you define them.</span></span> <span data-ttu-id="8a95a-210">К счастью, это можно сделать с использованием ключевого слова `ordered`.</span><span class="sxs-lookup"><span data-stu-id="8a95a-210">Thankfully, there's a way to do that with the `ordered` keyword.</span></span>

```powershell
$person = [ordered]@{
    name = 'Kevin'
    age  = 36
}
```

<span data-ttu-id="8a95a-211">Теперь при перечислении ключи и значения сохраняют этот порядок.</span><span class="sxs-lookup"><span data-stu-id="8a95a-211">Now when you enumerate the keys and values, they stay in that order.</span></span>

### <a name="inline-hashtables"></a><span data-ttu-id="8a95a-212">Строковые хэш-таблицы</span><span class="sxs-lookup"><span data-stu-id="8a95a-212">Inline hashtables</span></span>

<span data-ttu-id="8a95a-213">При определении хэш-таблицы в одной строке можно разделять пары "ключ-значение" точкой с запятой.</span><span class="sxs-lookup"><span data-stu-id="8a95a-213">When you're defining a hashtable on one line, you can separate the key/value pairs with a semicolon.</span></span>

```powershell
$person = @{ name = 'kevin'; age = 36; }
```

<span data-ttu-id="8a95a-214">Это удобно, если вы создаете их в канале.</span><span class="sxs-lookup"><span data-stu-id="8a95a-214">This will come in handy if you're creating them on the pipe.</span></span>

### <a name="custom-expressions-in-common-pipeline-commands"></a><span data-ttu-id="8a95a-215">Настраиваемые выражения в общих командах конвейера</span><span class="sxs-lookup"><span data-stu-id="8a95a-215">Custom expressions in common pipeline commands</span></span>

<span data-ttu-id="8a95a-216">Существует несколько командлетов, которые поддерживают использование хэш-таблиц для создания настраиваемых или вычисляемых свойств.</span><span class="sxs-lookup"><span data-stu-id="8a95a-216">There are a few cmdlets that support the use of hashtables to create custom or calculated properties.</span></span> <span data-ttu-id="8a95a-217">Как правило, они используются в `Select-Object` и `Format-Table`.</span><span class="sxs-lookup"><span data-stu-id="8a95a-217">You commonly see this with `Select-Object` and `Format-Table`.</span></span> <span data-ttu-id="8a95a-218">Хэш-таблицы используют специальный синтаксис, который в развернутом виде выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="8a95a-218">The hashtables have a special syntax that looks like this when fully expanded.</span></span>

```powershell
$property = @{
    name = 'totalSpaceGB'
    expression = { ($_.used + $_.free) / 1GB }
}
```

<span data-ttu-id="8a95a-219">Командлет помечает этот столбец как `name`.</span><span class="sxs-lookup"><span data-stu-id="8a95a-219">The `name` is what the cmdlet would label that column.</span></span> <span data-ttu-id="8a95a-220">`expression` — это блок выполняемого сценария, где `$_` представляет значение объекта в канале.</span><span class="sxs-lookup"><span data-stu-id="8a95a-220">The `expression` is a script block that is executed where `$_` is the value of the object on the pipe.</span></span> <span data-ttu-id="8a95a-221">Далее рассматривается действие сценария.</span><span class="sxs-lookup"><span data-stu-id="8a95a-221">Here is that script in action:</span></span>

```powershell
$drives = Get-PSDrive | Where Used
$drives | Select-Object -Properties name, $property

Name     totalSpaceGB
----     ------------
C    238.472652435303
```

<span data-ttu-id="8a95a-222">Я поместил его в переменную, однако его можно определить как строковый и сократить `name` до `n` и `expression` до `e` в процессе работы над ним.</span><span class="sxs-lookup"><span data-stu-id="8a95a-222">I placed that in a variable but it could easily be defined inline and you can shorten `name` to `n` and `expression` to `e` while you're at it.</span></span>

```powershell
$drives | Select-Object -properties name, @{n='totalSpaceGB';e={($_.used + $_.free) / 1GB}}
```

<span data-ttu-id="8a95a-223">Лично мне не нравится, что команды выполняются долго, и зачастую проявляются нежелательные последствия.</span><span class="sxs-lookup"><span data-stu-id="8a95a-223">I personally don't like how long that makes commands and it often promotes some bad behaviors that I won't get into.</span></span> <span data-ttu-id="8a95a-224">Лучше я создам новую хэш-таблицу или `pscustomobject` со всеми нужными полями и свойствами вместо того, чтобы использовать этот метод со сценариями.</span><span class="sxs-lookup"><span data-stu-id="8a95a-224">I'm more likely to create a new hashtable or `pscustomobject` with all the fields and properties that I want instead of using this approach in scripts.</span></span> <span data-ttu-id="8a95a-225">Однако там содержится большой объем кода, который выполняет эти задачи, и вам следует помнить об этом.</span><span class="sxs-lookup"><span data-stu-id="8a95a-225">But there's a lot of code out there that does this so I wanted you to be aware of it.</span></span> <span data-ttu-id="8a95a-226">Я имею в виду последующее создание `pscustomobject`.</span><span class="sxs-lookup"><span data-stu-id="8a95a-226">I talk about creating a `pscustomobject` later on.</span></span>

### <a name="custom-sort-expression"></a><span data-ttu-id="8a95a-227">Настраиваемое выражение сортировки</span><span class="sxs-lookup"><span data-stu-id="8a95a-227">Custom sort expression</span></span>

<span data-ttu-id="8a95a-228">Можно легко отсортировать коллекцию, если объекты содержат данные, которые вы хотите использовать как критерий сортировки.</span><span class="sxs-lookup"><span data-stu-id="8a95a-228">It's easy to sort a collection if the objects have the data that you want to sort on.</span></span> <span data-ttu-id="8a95a-229">Можно либо добавить данные в объект перед сортировкой, либо создать настраиваемое выражение для `Sort-Object`.</span><span class="sxs-lookup"><span data-stu-id="8a95a-229">You can either add the data to the object before you sort it or create a custom expression for `Sort-Object`.</span></span>

```powershell
Get-ADUser | Sort-Object -Parameter @{ e={ Get-TotalSales $_.Name } }
```

<span data-ttu-id="8a95a-230">В этом примере я выберу список пользователей и использую специальный командлет, чтобы получить дополнительную информацию исключительно в целях сортировки.</span><span class="sxs-lookup"><span data-stu-id="8a95a-230">In this example I'm taking a list of users and using some custom cmdlet to get additional information just for the sort.</span></span>

#### <a name="sort-a-list-of-hashtables"></a><span data-ttu-id="8a95a-231">Сортировка списка хэш-таблиц</span><span class="sxs-lookup"><span data-stu-id="8a95a-231">Sort a list of Hashtables</span></span>

<span data-ttu-id="8a95a-232">При наличии списка хэш-таблиц, которые нужно отсортировать, выясняется, что `Sort-Object` не обрабатывает ключи как свойства.</span><span class="sxs-lookup"><span data-stu-id="8a95a-232">If you have a list of hashtables that you want to sort, you'll find that the `Sort-Object` doesn't treat your keys as properties.</span></span> <span data-ttu-id="8a95a-233">Эту проблему можно решить с помощью настраиваемых выражений сортировки.</span><span class="sxs-lookup"><span data-stu-id="8a95a-233">We can get a round that by using a custom sort expression.</span></span>

```powershell
$data = @(
    @{name='a'}
    @{name='c'}
    @{name='e'}
    @{name='f'}
    @{name='d'}
    @{name='b'}
)

$data | Sort-Object -Property @{e={$_.name}}
```

## <a name="splatting-hashtables-at-cmdlets"></a><span data-ttu-id="8a95a-234">Сплаттинг хэш-таблиц в командлетах</span><span class="sxs-lookup"><span data-stu-id="8a95a-234">Splatting hashtables at cmdlets</span></span>

<span data-ttu-id="8a95a-235">Именно это мне больше всего нравится в хэш-таблицах, однако многие об этом до сих пор не знают.</span><span class="sxs-lookup"><span data-stu-id="8a95a-235">This is one of my favorite things about hashtables that many people don't discover early on.</span></span>
<span data-ttu-id="8a95a-236">Идея в том, чтобы вместо указания всех свойств в одной строке командлета сначала упаковать их в хэш-таблицу.</span><span class="sxs-lookup"><span data-stu-id="8a95a-236">The idea is that instead of providing all the properties to a cmdlet on one line, you can instead pack them into a hashtable first.</span></span> <span data-ttu-id="8a95a-237">После этого можно специально присвоить хэш-таблицу функции.</span><span class="sxs-lookup"><span data-stu-id="8a95a-237">Then you can give the hashtable to the function in a special way.</span></span>
<span data-ttu-id="8a95a-238">Ниже приведен пример создания области DHCP обычным способом.</span><span class="sxs-lookup"><span data-stu-id="8a95a-238">Here is an example of creating a DHCP scope the normal way.</span></span>

```powershell
Add-DhcpServerv4Scope -Name 'TestNetwork' -StartRange'10.0.0.2' -EndRange '10.0.0.254' -SubnetMask '255.255.255.0' -Description 'Network for testlab A' -LeaseDuration (New-TimeSpan -Days 8) -Type "Both"
```

<span data-ttu-id="8a95a-239">Если [сплаттинг][] не используется, все это необходимо определять в одной строке.</span><span class="sxs-lookup"><span data-stu-id="8a95a-239">Without using [splatting][], all those things need to be defined on a single line.</span></span> <span data-ttu-id="8a95a-240">При этом либо приходится прокручивать экран, либо строка разворачивается в произвольном месте.</span><span class="sxs-lookup"><span data-stu-id="8a95a-240">It either scrolls off the screen or will wrap where ever it feels like.</span></span> <span data-ttu-id="8a95a-241">А теперь сравним это с командой, которая использует сплаттинг.</span><span class="sxs-lookup"><span data-stu-id="8a95a-241">Now compare that to a command that uses splatting.</span></span>

```powershell
$DHCPScope = @{
    Name        = 'TestNetwork'
    StartRange  = '10.0.0.2'
    EndRange    = '10.0.0.254'
    SubnetMask  = '255.255.255.0'
    Description = 'Network for testlab A'
    LeaseDuration = (New-TimeSpan -Days 8)
    Type = "Both"
}
Add-DhcpServerv4Scope @DHCPScope
```

<span data-ttu-id="8a95a-242">При использовании символа `@` вместо `$` вызывается операция сплаттинга.</span><span class="sxs-lookup"><span data-stu-id="8a95a-242">The use of the `@` sign instead of the `$` is what invokes the splat operation.</span></span>

<span data-ttu-id="8a95a-243">Просто подумайте, насколько легко читать данные в таком примере.</span><span class="sxs-lookup"><span data-stu-id="8a95a-243">Just take a moment to appreciate how easy that example is to read.</span></span> <span data-ttu-id="8a95a-244">Это абсолютно та же команда с теми же значениями.</span><span class="sxs-lookup"><span data-stu-id="8a95a-244">They are the exact same command with all the same values.</span></span> <span data-ttu-id="8a95a-245">Второй вариант гораздо проще для понимания и использования в дальнейшей работе.</span><span class="sxs-lookup"><span data-stu-id="8a95a-245">The second one is easier to understand and maintain going forward.</span></span>

<span data-ttu-id="8a95a-246">Я всегда использую сплаттинг, если команда становится слишком длинной.</span><span class="sxs-lookup"><span data-stu-id="8a95a-246">I use splatting anytime the command gets too long.</span></span> <span data-ttu-id="8a95a-247">Когда я говорю "слишком длинной", я имею в виду, что мне приходится прокручивать экран вправо.</span><span class="sxs-lookup"><span data-stu-id="8a95a-247">I define too long as causing my window to scroll right.</span></span> <span data-ttu-id="8a95a-248">Если я выбираю три свойства для функции, велика вероятность, что мне придется переписывать их с использованием хэш-таблицы со сплаттингом.</span><span class="sxs-lookup"><span data-stu-id="8a95a-248">If I hit three properties for a function, odds are that I'll rewrite it using a splatted hashtable.</span></span>

### <a name="splatting-for-optional-parameters"></a><span data-ttu-id="8a95a-249">Сплаттинг для дополнительных параметров</span><span class="sxs-lookup"><span data-stu-id="8a95a-249">Splatting for optional parameters</span></span>

<span data-ttu-id="8a95a-250">Чаще всего я использую сплаттинг для работы с дополнительными параметрами, которые добавляю в свой сценарий из других источников.</span><span class="sxs-lookup"><span data-stu-id="8a95a-250">One of the most common ways I use splatting is to deal with optional parameters that come from some place else in my script.</span></span> <span data-ttu-id="8a95a-251">Предположим, у меня есть функция, которая переносит вызов `Get-CIMInstance`, содержащий дополнительный аргумент `$Credential`.</span><span class="sxs-lookup"><span data-stu-id="8a95a-251">Let's say I have a function that wraps a `Get-CIMInstance` call that has an optional `$Credential` argument.</span></span>

```powershell
$CIMParams = @{
    ClassName = 'Win32_Bios'
    ComputerName = $ComputerName
}

if($Credential)
{
    $CIMParams.Credential = $Credential
}

Get-CIMInstance @CIMParams
```

<span data-ttu-id="8a95a-252">Для начала я создаю хэш-таблицу с общими параметрами.</span><span class="sxs-lookup"><span data-stu-id="8a95a-252">I start by creating my hashtable with common parameters.</span></span> <span data-ttu-id="8a95a-253">Потом я добавляю `$Credential`, если он существует.</span><span class="sxs-lookup"><span data-stu-id="8a95a-253">Then I add the `$Credential` if it exists.</span></span>
<span data-ttu-id="8a95a-254">Поскольку я использую здесь сплаттинг, мне нужно просто один раз вызвать `Get-CIMInstance` в коде.</span><span class="sxs-lookup"><span data-stu-id="8a95a-254">Because I'm using splatting here, I only need to have the call to `Get-CIMInstance` in my code once.</span></span> <span data-ttu-id="8a95a-255">Этот конструктивный шаблон абсолютно прозрачен и способен легко обрабатывать множество дополнительных параметров.</span><span class="sxs-lookup"><span data-stu-id="8a95a-255">This design pattern is very clean and can handle lots of optional parameters easily.</span></span>

<span data-ttu-id="8a95a-256">Правда, можно просто написать команды так, чтобы разрешить значения `$null` для параметров.</span><span class="sxs-lookup"><span data-stu-id="8a95a-256">To be fair, you could write your commands to allow `$null` values for parameters.</span></span> <span data-ttu-id="8a95a-257">На самом деле вы просто не всегда контролируете остальные вызываемые команды.</span><span class="sxs-lookup"><span data-stu-id="8a95a-257">You just don't always have control over the other commands you're calling.</span></span>

### <a name="multiple-splats"></a><span data-ttu-id="8a95a-258">Несколько операций сплаттинга</span><span class="sxs-lookup"><span data-stu-id="8a95a-258">Multiple splats</span></span>

<span data-ttu-id="8a95a-259">Можно выполнить сплаттинг нескольких хэш-таблиц в один командлет.</span><span class="sxs-lookup"><span data-stu-id="8a95a-259">You can splat multiple hashtables to the same cmdlet.</span></span> <span data-ttu-id="8a95a-260">Если вернуться к первоначальному примеру сплаттинга:</span><span class="sxs-lookup"><span data-stu-id="8a95a-260">If we revisit our original splatting example:</span></span>

```powershell
$Common = @{
    SubnetMask  = '255.255.255.0'
    LeaseDuration = (New-TimeSpan -Days 8)
    Type = "Both"
}

$DHCPScope = @{
    Name        = 'TestNetwork'
    StartRange  = '10.0.0.2'
    EndRange    = '10.0.0.254'
    Description = 'Network for testlab A'
}

Add-DhcpServerv4Scope @DHCPScope @Common
```

<span data-ttu-id="8a95a-261">Я использую этот метод, когда у меня будет общий набор параметров, который передается во многие команды.</span><span class="sxs-lookup"><span data-stu-id="8a95a-261">I'll use this method when I have a common set of parameters that I'm passing to lots of commands.</span></span>

### <a name="splatting-for-clean-code"></a><span data-ttu-id="8a95a-262">Сплаттинг для чистого кода</span><span class="sxs-lookup"><span data-stu-id="8a95a-262">Splatting for clean code</span></span>

<span data-ttu-id="8a95a-263">В сплаттинге одного параметра нет ничего плохого, если это помогает очистить код.</span><span class="sxs-lookup"><span data-stu-id="8a95a-263">There's nothing wrong with splatting a single parameter if makes you code cleaner.</span></span>

```powershell
$log = @{Path = '.\logfile.log'}
Add-Content "logging this command" @log
```

### <a name="splatting-executables"></a><span data-ttu-id="8a95a-264">Сплаттинг исполняемых файлов</span><span class="sxs-lookup"><span data-stu-id="8a95a-264">Splatting executables</span></span>

<span data-ttu-id="8a95a-265">Сплаттинг также эффективен для некоторых исполняемых файлов, использующих синтаксис `/param:value`.</span><span class="sxs-lookup"><span data-stu-id="8a95a-265">Splatting also works on some executables that use a `/param:value` syntax.</span></span> <span data-ttu-id="8a95a-266">`Robocopy.exe`, например, содержит отдельные такие параметры.</span><span class="sxs-lookup"><span data-stu-id="8a95a-266">`Robocopy.exe`, for example, has some parameters like this.</span></span>

```powershell
$robo = @{R=1;W=1;MT=8}
robocopy source destination @robo
```

<span data-ttu-id="8a95a-267">Не знаю, действительно ли все это имеет практическую пользу, но, по-моему, это очень интересно.</span><span class="sxs-lookup"><span data-stu-id="8a95a-267">I don't know that this is all that useful, but I found it interesting.</span></span>

## <a name="adding-hashtables"></a><span data-ttu-id="8a95a-268">Добавление хэш-таблиц</span><span class="sxs-lookup"><span data-stu-id="8a95a-268">Adding hashtables</span></span>

<span data-ttu-id="8a95a-269">Хэш-таблицы поддерживают оператор сложения для объединения двух хэш-таблиц.</span><span class="sxs-lookup"><span data-stu-id="8a95a-269">Hashtables support the addition operator to combine two hashtables.</span></span>

```powershell
$person += @{Zip = '78701'}
```

<span data-ttu-id="8a95a-270">Это эффективно только в том случае, если две хэш-таблицы не имеют общего ключа.</span><span class="sxs-lookup"><span data-stu-id="8a95a-270">This only works if the two hashtables don't share a key.</span></span>

## <a name="nested-hashtables"></a><span data-ttu-id="8a95a-271">Вложенные хэш-таблицы</span><span class="sxs-lookup"><span data-stu-id="8a95a-271">Nested hashtables</span></span>

<span data-ttu-id="8a95a-272">Хэш-таблицы можно использовать в качестве значений в хэш-таблице.</span><span class="sxs-lookup"><span data-stu-id="8a95a-272">We can use hashtables as values inside a hashtable.</span></span>

```powershell
$person = @{
    name = 'Kevin'
    age  = 36
}
$person.location = @{}
$person.location.city = 'Austin'
$person.location.state = 'TX'
```

<span data-ttu-id="8a95a-273">Я начал с базовой хэш-таблицы, которая содержит два ключа.</span><span class="sxs-lookup"><span data-stu-id="8a95a-273">I started with a basic hashtable containing two keys.</span></span> <span data-ttu-id="8a95a-274">Я добавил ключ `location` с пустой хэш-таблицей.</span><span class="sxs-lookup"><span data-stu-id="8a95a-274">I added a key called `location` with an empty hashtable.</span></span> <span data-ttu-id="8a95a-275">Затем я добавил два последних элемента в эту хэш-таблицу `location`.</span><span class="sxs-lookup"><span data-stu-id="8a95a-275">Then I added the last two items to that `location` hashtable.</span></span> <span data-ttu-id="8a95a-276">Все это также можно сделать в строке.</span><span class="sxs-lookup"><span data-stu-id="8a95a-276">We can do this all inline too.</span></span>

```powershell
$person = @{
    name = 'Kevin'
    age  = 36
    location = @{
        city  = 'Austin'
        state = 'TX'
    }
}
```

<span data-ttu-id="8a95a-277">Это создает ту же хэш-таблицу, которая описывалась выше, и обеспечивает доступ к свойствам таким же образом.</span><span class="sxs-lookup"><span data-stu-id="8a95a-277">This creates the same hashtable that we saw above and can access the properties the same way.</span></span>

```powershell
$person.location.city
Austin
```

<span data-ttu-id="8a95a-278">Существует множество способов реализации структуры объектов.</span><span class="sxs-lookup"><span data-stu-id="8a95a-278">There are many ways to approach the structure of your objects.</span></span> <span data-ttu-id="8a95a-279">Ниже показан другой вариант представления вложенной хэш-таблицы.</span><span class="sxs-lookup"><span data-stu-id="8a95a-279">Here is a second way to look at a nested hashtable.</span></span>

```powershell
$people = @{
    Kevin = @{
        age  = 36
        city = 'Austin'
    }
    Alex = @{
        age  = 9
        city = 'Austin'
    }
}
```

<span data-ttu-id="8a95a-280">В результате можно использовать хэш-таблицы как в качестве коллекции объектов, так и в качестве коллекции свойств.</span><span class="sxs-lookup"><span data-stu-id="8a95a-280">This mixes the concept of using hashtables as a collection of objects and a collection of properties.</span></span> <span data-ttu-id="8a95a-281">Доступ к значениям по-прежнему легко получить, даже если они вложены любым выбранным методом.</span><span class="sxs-lookup"><span data-stu-id="8a95a-281">The values are still easy to access even when they're nested using whatever approach you prefer.</span></span>

```powershell
PS> $people.kevin.age
36
PS> $people.kevin['city']
Austin
PS> $people['Alex'].age
9
PS> $people['Alex']['City']
Austin
```

<span data-ttu-id="8a95a-282">Я обычно использую свойство Dot, когда рассматриваю хэш-таблицу как свойство.</span><span class="sxs-lookup"><span data-stu-id="8a95a-282">I tend to use the dot property when I'm treating it like a property.</span></span> <span data-ttu-id="8a95a-283">Обычно в моем коде они определяются статически, и я знаю их чисто интуитивно.</span><span class="sxs-lookup"><span data-stu-id="8a95a-283">Those are generally things I've defined statically in my code and I know them off the top of my head.</span></span> <span data-ttu-id="8a95a-284">Если нужно обойти список или программно получить доступ к ключам, я использую квадратные скобки для ввода имени ключа.</span><span class="sxs-lookup"><span data-stu-id="8a95a-284">If I need to walk the list or programmatically access the keys, I use the brackets to provide the key name.</span></span>

```powershell
foreach($name in $people.keys)
{
    $person = $people[$name]
    '{0}, age {1}, is in {2}' -f $name, $person.age, $person.city
}
```

<span data-ttu-id="8a95a-285">Возможность вкладывать хэш-таблицы обеспечивает большую гибкость и дополнительные возможности.</span><span class="sxs-lookup"><span data-stu-id="8a95a-285">Having the ability to nest hashtables gives you a lot of flexibility and options.</span></span>

### <a name="looking-at-nested-hashtables"></a><span data-ttu-id="8a95a-286">Просмотр вложенных хэш-таблиц</span><span class="sxs-lookup"><span data-stu-id="8a95a-286">Looking at nested hashtables</span></span>

<span data-ttu-id="8a95a-287">Как только вы начнете вкладывать хэш-таблицы друг в друга, вам потребуются простые способы их просмотра из консоли.</span><span class="sxs-lookup"><span data-stu-id="8a95a-287">As soon as you start nesting hashtables, you're going to need an easy way to look at them from the console.</span></span> <span data-ttu-id="8a95a-288">Если я возьму эту последнюю хэш-таблицу, я получу выходные данные, которые будут выглядеть следующим образом, поскольку это максимальная глубина просмотра:</span><span class="sxs-lookup"><span data-stu-id="8a95a-288">If I take that last hashtable, I get an output that looks like this and it only goes so deep:</span></span>

```powershell
PS> $people
Name                           Value
----                           -----
Kevin                          {age, city}
Alex                           {age, city}
```

<span data-ttu-id="8a95a-289">Для поиска этих элементов я использую команду `ConvertTo-JSON`, так как она очень прозрачная, и я часто использую JSON для других задач.</span><span class="sxs-lookup"><span data-stu-id="8a95a-289">My go to command for looking at these things is `ConvertTo-JSON` because it's very clean and I frequently use JSON on other things.</span></span>

```powershell
PS> $people | ConvertTo-Json
{
    "Kevin":  {
                "age":  36,
                "city":  "Austin"
            },
    "Alex":  {
                "age":  9,
                "city":  "Austin"
            }
}
```

<span data-ttu-id="8a95a-290">Даже если вы не знакомы с JSON, вы сможете просмотреть то, что искали.</span><span class="sxs-lookup"><span data-stu-id="8a95a-290">Even if you don't know JSON, you should be able to see what you're looking for.</span></span> <span data-ttu-id="8a95a-291">Существует команда `Format-Custom` для таких структурированных данных, но мне все-таки больше нравится просмотр в JSON.</span><span class="sxs-lookup"><span data-stu-id="8a95a-291">There's a `Format-Custom` command for structured data like this but I still like the JSON view better.</span></span>

## <a name="creating-objects"></a><span data-ttu-id="8a95a-292">Создание объектов</span><span class="sxs-lookup"><span data-stu-id="8a95a-292">Creating objects</span></span>

<span data-ttu-id="8a95a-293">В отдельных случаях требуется только наличие объекта, а использование хэш-таблицы для хранения свойств не решает задачу.</span><span class="sxs-lookup"><span data-stu-id="8a95a-293">Sometimes you just need to have an object and using a hashtable to hold properties just isn't getting the job done.</span></span> <span data-ttu-id="8a95a-294">Чаще всего требуется просмотр ключей как имен столбцов.</span><span class="sxs-lookup"><span data-stu-id="8a95a-294">Most commonly you want to see the keys as column names.</span></span> <span data-ttu-id="8a95a-295">`pscustomobject` упрощает эту задачу.</span><span class="sxs-lookup"><span data-stu-id="8a95a-295">A `pscustomobject` makes that easy.</span></span>

```powershell
$person = [pscustomobject]@{
    name = 'Kevin'
    age  = 36
}

$person

name  age
----  ---
Kevin  36
```

<span data-ttu-id="8a95a-296">Даже если вы изначально не создаете его как `pscustomobject`, вы всегда можете выполнить его приведение позже при необходимости.</span><span class="sxs-lookup"><span data-stu-id="8a95a-296">Even if you don't create it as a `pscustomobject` initially, you can always cast it later when needed.</span></span>

```powershell
$person = @{
    name = 'Kevin'
    age  = 36
}

[pscustomobject]$person

name  age
----  ---
Kevin  36
```

<span data-ttu-id="8a95a-297">У меня уже есть подробная статья о [PCSCustomObject][], которую я рекомендую прочесть после этого.</span><span class="sxs-lookup"><span data-stu-id="8a95a-297">I already have detailed write-up for [pscustomobject][] that you should go read after this one.</span></span> <span data-ttu-id="8a95a-298">Она основана на большом объеме данных, которые мы получили отсюда.</span><span class="sxs-lookup"><span data-stu-id="8a95a-298">It builds on a lot of the things learned here.</span></span>

## <a name="reading-and-writing-hashtables-to-file"></a><span data-ttu-id="8a95a-299">Чтение и запись хэш-таблиц в файл</span><span class="sxs-lookup"><span data-stu-id="8a95a-299">Reading and writing hashtables to file</span></span>

### <a name="saving-to-csv"></a><span data-ttu-id="8a95a-300">Сохранение в CSV-файл</span><span class="sxs-lookup"><span data-stu-id="8a95a-300">Saving to CSV</span></span>

<span data-ttu-id="8a95a-301">Выше я говорил, в частности, о трудностях с получением хэш-таблицы для сохранения в CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="8a95a-301">Struggling with getting a hashtable to save to a CSV is one of the difficulties that I was referring to above.</span></span> <span data-ttu-id="8a95a-302">Преобразуйте хэш-таблицу в `pscustomobject`, чтобы правильно сохранить ее в CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="8a95a-302">Convert your hashtable to a `pscustomobject` and it will save correctly to CSV.</span></span> <span data-ttu-id="8a95a-303">Это полезно в начале работы с `pscustomobject`, поэтому порядок столбцов сохраняется.</span><span class="sxs-lookup"><span data-stu-id="8a95a-303">It helps if you start with a `pscustomobject` so the column order is preserved.</span></span> <span data-ttu-id="8a95a-304">Однако при необходимости его можно привести к `pscustomobject` в строке.</span><span class="sxs-lookup"><span data-stu-id="8a95a-304">But you can cast it to a `pscustomobject` inline if needed.</span></span>

```powershell
$person | ForEach-Object{ [pscustomobject]$_ } | Export-CSV -Path $path
```

<span data-ttu-id="8a95a-305">Опять же, рекомендую ознакомиться с моей публикацией по использованию [PCSCustomObject][].</span><span class="sxs-lookup"><span data-stu-id="8a95a-305">Again, check out my write-up on using a [pscustomobject][].</span></span>

### <a name="saving-a-nested-hashtable-to-file"></a><span data-ttu-id="8a95a-306">Сохранение вложенной хэш-таблицы в файл</span><span class="sxs-lookup"><span data-stu-id="8a95a-306">Saving a nested hashtable to file</span></span>

<span data-ttu-id="8a95a-307">Если нужно сохранить вложенную хэш-таблицу в файл, а затем повторно прочитать ее, я использую для этого командлеты JSON.</span><span class="sxs-lookup"><span data-stu-id="8a95a-307">If I need to save a nested hashtable to a file and then read it back in again, I use the JSON cmdlets to do it.</span></span>

```powershell
$people | ConvertTo-JSON | Set-Content -Path $path
$people = Get-Content -Path $path -Raw | ConvertFrom-JSON
```

<span data-ttu-id="8a95a-308">В отношении этого метода можно отметить следующие два момента.</span><span class="sxs-lookup"><span data-stu-id="8a95a-308">There are two important points about this method.</span></span> <span data-ttu-id="8a95a-309">Сначала JSON записывается в многострочном формате, поэтому мне нужно использовать параметр `-Raw`, чтобы считать его обратно в одну строку.</span><span class="sxs-lookup"><span data-stu-id="8a95a-309">First is that the JSON is written out multiline so I need to use the `-Raw` option to read it back into a single string.</span></span> <span data-ttu-id="8a95a-310">Второй способ заключается в том, что импортированный объект больше не является `[hashtable]`.</span><span class="sxs-lookup"><span data-stu-id="8a95a-310">The Second is that the imported object is no longer a `[hashtable]`.</span></span> <span data-ttu-id="8a95a-311">Теперь он является `[pscustomobject]`, и это может стать проблемой, если вы этого не ожидали.</span><span class="sxs-lookup"><span data-stu-id="8a95a-311">It's now a `[pscustomobject]` and that can cause issues if you don't expect it.</span></span>

<span data-ttu-id="8a95a-312">Обращайте внимание на хэш-таблицы с глубоким уровнем вложенности.</span><span class="sxs-lookup"><span data-stu-id="8a95a-312">Watch for deeply-nested hashtables.</span></span> <span data-ttu-id="8a95a-313">Преобразование в формат JSON может привести к непредвиденным результатам.</span><span class="sxs-lookup"><span data-stu-id="8a95a-313">When you convert it to JSON you might not get the results you expect.</span></span>

```powershell
@{ a = @{ b = @{ c = @{ d = "e" }}}} | ConvertTo-Json

{
  "a": {
    "b": {
      "c": "System.Collections.Hashtable"
    }
  }
}
```

<span data-ttu-id="8a95a-314">Используйте параметр **Depth** , чтобы обеспечить развертывание всех вложенных хэш-таблиц.</span><span class="sxs-lookup"><span data-stu-id="8a95a-314">Use **Depth** parameter to ensure that you have expanded all the nested hashtables.</span></span>

```powershell
@{ a = @{ b = @{ c = @{ d = "e" }}}} | ConvertTo-Json -Depth 3

{
  "a": {
    "b": {
      "c": {
        "d": "e"
      }
    }
  }
}
```

<span data-ttu-id="8a95a-315">Если вы хотите, чтобы при импорте это был `[hashtable]`, в этом случае вам придется использовать команды `Export-CliXml` и `Import-CliXml`.</span><span class="sxs-lookup"><span data-stu-id="8a95a-315">If you need it to be a `[hashtable]` on import, then you need to use the `Export-CliXml` and `Import-CliXml` commands.</span></span>

### <a name="converting-json-to-hashtable"></a><span data-ttu-id="8a95a-316">Преобразование JSON в хэш-таблицу</span><span class="sxs-lookup"><span data-stu-id="8a95a-316">Converting JSON to Hashtable</span></span>

<span data-ttu-id="8a95a-317">Если необходимо преобразовать JSON в `[hashtable]`, это можно сделать с помощью [JavaScriptSerializer][] в .NET.</span><span class="sxs-lookup"><span data-stu-id="8a95a-317">If you need to convert JSON to a `[hashtable]`, there's one way that I know of to do it with the [JavaScriptSerializer][] in .NET.</span></span>

```powershell
[Reflection.Assembly]::LoadWithPartialName("System.Web.Script.Serialization")
$JSSerializer = [System.Web.Script.Serialization.JavaScriptSerializer]::new()
$JSSerializer.Deserialize($json,'Hashtable')
```

<span data-ttu-id="8a95a-318">Начиная с PowerShell версии 6, для поддержки JSON используется NewtonSoft JSON.NET, а также добавлена поддержка хэш-таблиц.</span><span class="sxs-lookup"><span data-stu-id="8a95a-318">Beginning in PowerShell v6, JSON support uses the NewtonSoft JSON.NET and adds hashtable support.</span></span>

```powershell
'{ "a": "b" }' | ConvertFrom-Json -AsHashtable

Name      Value
----      -----
a         b
```

<span data-ttu-id="8a95a-319">В PowerShell 6.2 добавлен параметр **Depth** для `ConvertFrom-Json`.</span><span class="sxs-lookup"><span data-stu-id="8a95a-319">PowerShell 6.2 added the **Depth** parameter to `ConvertFrom-Json`.</span></span> <span data-ttu-id="8a95a-320">Значение по умолчанию для параметра **Depth**  — 1024.</span><span class="sxs-lookup"><span data-stu-id="8a95a-320">The default **Depth** is 1024.</span></span>

### <a name="reading-directly-from-a-file"></a><span data-ttu-id="8a95a-321">Чтение непосредственно из файла</span><span class="sxs-lookup"><span data-stu-id="8a95a-321">Reading directly from a file</span></span>

<span data-ttu-id="8a95a-322">Если у вас есть файл, который содержит хэш-таблицу, использующую синтаксис PowerShell, есть способ импортировать его напрямую.</span><span class="sxs-lookup"><span data-stu-id="8a95a-322">If you have a file that contains a hashtable using PowerShell syntax, there's a way to import it directly.</span></span>

```powershell
$content = Get-Content -Path $Path -Raw -ErrorAction Stop
$scriptBlock = [scriptblock]::Create( $content )
$scriptBlock.CheckRestrictedLanguage( $allowedCommands, $allowedVariables, $true )
$hashtable = ( & $scriptBlock )
```

<span data-ttu-id="8a95a-323">Он импортирует содержимое файла в `scriptblock`, а затем проверяет, чтобы перед его выполнением в нем не было других команд PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8a95a-323">It imports the contents of the file into a `scriptblock`, then checks to make sure it doesn't have any other PowerShell commands in it before it executes it.</span></span>

<span data-ttu-id="8a95a-324">Знаете ли вы, что манифест модуля (файл PSD1) является просто хэш-таблицей?</span><span class="sxs-lookup"><span data-stu-id="8a95a-324">On that note, did you know that a module manifest (the psd1 file) is just a hashtable?</span></span>

## <a name="keys-can-be-any-object"></a><span data-ttu-id="8a95a-325">Ключом может быть любой объект.</span><span class="sxs-lookup"><span data-stu-id="8a95a-325">Keys can be any object</span></span>

<span data-ttu-id="8a95a-326">Как правило, ключи — это просто строки.</span><span class="sxs-lookup"><span data-stu-id="8a95a-326">Most of the time, the keys are just strings.</span></span> <span data-ttu-id="8a95a-327">Таким образом, мы можем заключить в кавычки все, что угодно, и сделать это ключом.</span><span class="sxs-lookup"><span data-stu-id="8a95a-327">So we can put quotes around anything and make it a key.</span></span>

```powershell
$person = @{
    'full name' = 'Kevin Marquette'
    '#' = 3978
}
$person['full name']
```

<span data-ttu-id="8a95a-328">Вы можете выполнить практически любые задачи, даже если раньше не знали, что это вообще возможно.</span><span class="sxs-lookup"><span data-stu-id="8a95a-328">You can do some odd things that you may not have realized you could do.</span></span>

```powershell
$person.'full name'

$key = 'full name'
$person.$key
```

<span data-ttu-id="8a95a-329">Однако тот факт, что вы можете что-то сделать, вовсе не значит, что это нужно делать.</span><span class="sxs-lookup"><span data-stu-id="8a95a-329">Just because you can do something, it doesn't mean that you should.</span></span> <span data-ttu-id="8a95a-330">Последний вариант выглядит так, как будто ошибка в нем неминуема, и его неправильно поймет любой, кто читает ваш код.</span><span class="sxs-lookup"><span data-stu-id="8a95a-330">That last one just looks like a bug waiting to happen and would be easily misunderstood by anyone reading your code.</span></span>

<span data-ttu-id="8a95a-331">Технически ваш ключ необязательно должен быть строкой, однако его проще воспринимать, если используются только строки.</span><span class="sxs-lookup"><span data-stu-id="8a95a-331">Technically your key doesn't have to be a string but they're easier to think about if you only use strings.</span></span> <span data-ttu-id="8a95a-332">Но индексирование не будет нормально выполняться со сложными ключами.</span><span class="sxs-lookup"><span data-stu-id="8a95a-332">However, indexing doesn't work well with the complex keys.</span></span>

```powershell
$ht = @{ @(1,2,3) = "a" }
$ht

Name                           Value
----                           -----
{1, 2, 3}                      a
```

<span data-ttu-id="8a95a-333">Доступ к значению в хэш-таблице по ключу не всегда работает.</span><span class="sxs-lookup"><span data-stu-id="8a95a-333">Accessing a value in the hashtable by its key doesn't always work.</span></span> <span data-ttu-id="8a95a-334">Пример:</span><span class="sxs-lookup"><span data-stu-id="8a95a-334">For example:</span></span>

```powershell
$key = $ht.keys[0]
$ht.$($key)
a
$ht[$key]
a
```

<span data-ttu-id="8a95a-335">Если ключ является массивом, необходимо заключить переменную `$key` в часть выражения, чтобы ее можно было использовать с нотацией доступа к членам (`.`).</span><span class="sxs-lookup"><span data-stu-id="8a95a-335">When the key is an array, you must wrap the `$key` variable in a subexpression so that it can be used with member access (`.`) notation.</span></span> <span data-ttu-id="8a95a-336">Или можно использовать нотацию индекса массива (`[]`).</span><span class="sxs-lookup"><span data-stu-id="8a95a-336">Or, you can use array index (`[]`) notation.</span></span>

## <a name="use-in-automatic-variables"></a><span data-ttu-id="8a95a-337">Использование в автоматических переменных</span><span class="sxs-lookup"><span data-stu-id="8a95a-337">Use in automatic variables</span></span>

### <a name="psboundparameters"></a><span data-ttu-id="8a95a-338">$PSBoundParameters</span><span class="sxs-lookup"><span data-stu-id="8a95a-338">$PSBoundParameters</span></span>

<span data-ttu-id="8a95a-339">[$PSBoundParameters] [] — это автоматическая переменная, которая существует только в контексте функции.</span><span class="sxs-lookup"><span data-stu-id="8a95a-339">[$PSBoundParameters][] is an automatic variable that only exists inside the context of a function.</span></span>
<span data-ttu-id="8a95a-340">Она содержит все параметры, с которыми вызывалась функция.</span><span class="sxs-lookup"><span data-stu-id="8a95a-340">It contains all the parameters that the function was called with.</span></span> <span data-ttu-id="8a95a-341">Это не совсем хэш-таблица, но достаточно близка к тому, чтобы ее можно было обрабатывать как хэш-таблицу.</span><span class="sxs-lookup"><span data-stu-id="8a95a-341">This isn't exactly a hashtable but close enough that you can treat it like one.</span></span>

<span data-ttu-id="8a95a-342">Это предполагает удаление ключей и ее сплаттинг в другие функции.</span><span class="sxs-lookup"><span data-stu-id="8a95a-342">That includes removing keys and splatting it to other functions.</span></span> <span data-ttu-id="8a95a-343">Если вы намерены писать функции прокси-сервера, ознакомьтесь со следующими сведениями.</span><span class="sxs-lookup"><span data-stu-id="8a95a-343">If you find yourself writing proxy functions, take a closer look at this one.</span></span>

<span data-ttu-id="8a95a-344">Дополнительные сведения см. в разделе [about_Automatic_Variables][].</span><span class="sxs-lookup"><span data-stu-id="8a95a-344">See [about_Automatic_Variables][] for more details.</span></span>

### <a name="psboundparameters-gotcha"></a><span data-ttu-id="8a95a-345">Проблема с PSBoundParameters</span><span class="sxs-lookup"><span data-stu-id="8a95a-345">PSBoundParameters gotcha</span></span>

<span data-ttu-id="8a95a-346">Важно помнить, что он включает только значения, передаваемые в качестве параметров.</span><span class="sxs-lookup"><span data-stu-id="8a95a-346">One important thing to remember is that this only includes the values that are passed in as parameters.</span></span> <span data-ttu-id="8a95a-347">Если у вас также есть параметры со значениями по умолчанию, но они не передаются вызывающей стороной, `$PSBoundParameters` не содержит этих значений.</span><span class="sxs-lookup"><span data-stu-id="8a95a-347">If you also have parameters with default values but aren't passed in by the caller, `$PSBoundParameters` doesn't contain those values.</span></span> <span data-ttu-id="8a95a-348">Обычно этот момент упускается из вида.</span><span class="sxs-lookup"><span data-stu-id="8a95a-348">This is commonly overlooked.</span></span>

### <a name="psdefaultparametervalues"></a><span data-ttu-id="8a95a-349">$PSDefaultParameterValues</span><span class="sxs-lookup"><span data-stu-id="8a95a-349">$PSDefaultParameterValues</span></span>

<span data-ttu-id="8a95a-350">Эта автоматическая переменная позволяет назначить значения по умолчанию любому командлету, не изменяя его.</span><span class="sxs-lookup"><span data-stu-id="8a95a-350">This automatic variable lets you assign default values to any cmdlet without changing the cmdlet.</span></span>
<span data-ttu-id="8a95a-351">Взгляните на этот пример.</span><span class="sxs-lookup"><span data-stu-id="8a95a-351">Take a look at this example.</span></span>

```powershell
$PSDefaultParameterValues["Out-File:Encoding"] = "UTF8"
```

<span data-ttu-id="8a95a-352">При этом в хэш-таблицу `$PSDefaultParameterValues` добавляется запись, которая задает `UTF8` в качестве значения по умолчанию для параметра `Out-File -Encoding`.</span><span class="sxs-lookup"><span data-stu-id="8a95a-352">This adds an entry to the `$PSDefaultParameterValues` hashtable that sets `UTF8` as the default value for the `Out-File -Encoding` parameter.</span></span> <span data-ttu-id="8a95a-353">Это зависит от сеанса, поэтому его следует поместить в `$profile`.</span><span class="sxs-lookup"><span data-stu-id="8a95a-353">This is session-specific so you should place it in your `$profile`.</span></span>

<span data-ttu-id="8a95a-354">Я часто использую этот способ для предварительного присвоения значений, которые я часто ввожу.</span><span class="sxs-lookup"><span data-stu-id="8a95a-354">I use this often to pre-assign values that I type quite often.</span></span>

```powershell
$PSDefaultParameterValues[ "Connect-VIServer:Server" ] = 'VCENTER01.contoso.local'
```

<span data-ttu-id="8a95a-355">Это также позволяет использовать подстановочные знаки для группового указания значений.</span><span class="sxs-lookup"><span data-stu-id="8a95a-355">This also accepts wildcards so you can set values in bulk.</span></span> <span data-ttu-id="8a95a-356">Далее описывается несколько способов использования этой операции:</span><span class="sxs-lookup"><span data-stu-id="8a95a-356">Here are some ways you can use that:</span></span>

```powershell
$PSDefaultParameterValues[ "Get-*:Verbose" ] = $true
$PSDefaultParameterValues[ "*:Credential" ] = Get-Credential
```

<span data-ttu-id="8a95a-357">Более подробно это рассматривается в отличной статье об [Автоматические значения по умолчанию][], написанной [Майкл Соренс][].</span><span class="sxs-lookup"><span data-stu-id="8a95a-357">For a more in-depth breakdown, see this great article on [Automatic Defaults][] by [Michael Sorens][].</span></span>

## <a name="regex-matches"></a><span data-ttu-id="8a95a-358">Регулярное выражение $Matches</span><span class="sxs-lookup"><span data-stu-id="8a95a-358">Regex $Matches</span></span>

<span data-ttu-id="8a95a-359">При использовании оператора `-match` создается автоматическая переменная с именем `$matches`, которая содержит результаты сопоставления.</span><span class="sxs-lookup"><span data-stu-id="8a95a-359">When you use the `-match` operator, an automatic variable called `$matches` is created with the results of the match.</span></span> <span data-ttu-id="8a95a-360">Если в регулярном выражении есть какие-либо подвыражения, то в список также включаются соответствующие части совпадений.</span><span class="sxs-lookup"><span data-stu-id="8a95a-360">If you have any sub expressions in your regex, those sub matches are also listed.</span></span>

```powershell
$message = 'My SSN is 123-45-6789.'

$message -match 'My SSN is (.+)\.'
$Matches[0]
$Matches[1]
```

### <a name="named-matches"></a><span data-ttu-id="8a95a-361">Именованные совпадения</span><span class="sxs-lookup"><span data-stu-id="8a95a-361">Named matches</span></span>

<span data-ttu-id="8a95a-362">Это одна из моих любимых функций, о которой большинство пользователей не знает.</span><span class="sxs-lookup"><span data-stu-id="8a95a-362">This is one of my favorite features that most people don't know about.</span></span> <span data-ttu-id="8a95a-363">Если используется именованное совпадение регулярного выражения, доступ к совпадению осуществляется по имени в совпадениях.</span><span class="sxs-lookup"><span data-stu-id="8a95a-363">If you use a named regex match, then you can access that match by name on the matches.</span></span>

```powershell
$message = 'My Name is Kevin and my SSN is 123-45-6789.'

if($message -match 'My Name is (?<Name>.+) and my SSN is (?<SSN>.+)\.')
{
    $Matches.Name
    $Matches.SSN
}
```

<span data-ttu-id="8a95a-364">В приведенном выше примере `(?<Name>.*)` является именованной частью выражения.</span><span class="sxs-lookup"><span data-stu-id="8a95a-364">In the example above, the `(?<Name>.*)` is a named sub expression.</span></span> <span data-ttu-id="8a95a-365">Это значение затем помещается в свойство `$Matches.Name`.</span><span class="sxs-lookup"><span data-stu-id="8a95a-365">This value is then placed in the `$Matches.Name` property.</span></span>

## <a name="group-object--ashashtable"></a><span data-ttu-id="8a95a-366">Group-Object -AsHashtable</span><span class="sxs-lookup"><span data-stu-id="8a95a-366">Group-Object -AsHashtable</span></span>

<span data-ttu-id="8a95a-367">Одна из малоизвестных возможностей в `Group-Object` — возможность преобразовать некоторые наборы данных в хэш-таблицу.</span><span class="sxs-lookup"><span data-stu-id="8a95a-367">One little known feature of `Group-Object` is that it can turn some datasets into a hashtable for you.</span></span>

```powershell
Import-CSV $Path | Group-Object -AsHashtable -Property email
```

<span data-ttu-id="8a95a-368">Таким образом, в хэш-таблицу добавляются все строки, и указанное свойство используется как ключ для доступа к ним.</span><span class="sxs-lookup"><span data-stu-id="8a95a-368">This will add each row into a hashtable and use the specified property as the key to access it.</span></span>

## <a name="copying-hashtables"></a><span data-ttu-id="8a95a-369">Копирование хэш-таблиц</span><span class="sxs-lookup"><span data-stu-id="8a95a-369">Copying Hashtables</span></span>

<span data-ttu-id="8a95a-370">Важно помнить, что хэш-таблицы являются объектами.</span><span class="sxs-lookup"><span data-stu-id="8a95a-370">One important thing to know is that hashtables are objects.</span></span> <span data-ttu-id="8a95a-371">А каждая переменная — это просто ссылка на объект.</span><span class="sxs-lookup"><span data-stu-id="8a95a-371">And each variable is just a reference to an object.</span></span> <span data-ttu-id="8a95a-372">Это означает, что создание допустимой копии хэш-таблицы потребует больших усилий.</span><span class="sxs-lookup"><span data-stu-id="8a95a-372">This means that it takes more work to make a valid copy of a hashtable.</span></span>

### <a name="assigning-reference-types"></a><span data-ttu-id="8a95a-373">Присвоение ссылочных типов</span><span class="sxs-lookup"><span data-stu-id="8a95a-373">Assigning reference types</span></span>

<span data-ttu-id="8a95a-374">Если есть одна хэш-таблица и она присвоена второй переменной, обе переменные указывают на одну и ту же хэш-таблицу.</span><span class="sxs-lookup"><span data-stu-id="8a95a-374">When you have one hashtable and assign it to a second variable, both variables point to the same hashtable.</span></span>

```powershell
PS> $orig = @{name='orig'}
PS> $copy = $orig
PS> $copy.name = 'copy'
PS> 'Copy: [{0}]' -f $copy.name
PS> 'Orig: [{0}]' -f $orig.name

Copy: [copy]
Orig: [copy]
```

<span data-ttu-id="8a95a-375">Это подчеркивает, что они одинаковые, так как при изменении значений в одной из них также меняются значения в другой.</span><span class="sxs-lookup"><span data-stu-id="8a95a-375">This highlights that they're the same because altering the values in one will also alter the values in the other.</span></span> <span data-ttu-id="8a95a-376">Данное правило также применимо при передаче хэш-таблиц в другие функции.</span><span class="sxs-lookup"><span data-stu-id="8a95a-376">This also applies when passing hashtables into other functions.</span></span> <span data-ttu-id="8a95a-377">Если эти функции вносят изменения в данную хэш-таблицу, то оригинал также изменится.</span><span class="sxs-lookup"><span data-stu-id="8a95a-377">If those functions make changes to that hashtable, your original is also altered.</span></span>

### <a name="shallow-copies-single-level"></a><span data-ttu-id="8a95a-378">Неполные копии, одноуровневые</span><span class="sxs-lookup"><span data-stu-id="8a95a-378">Shallow copies, single level</span></span>

<span data-ttu-id="8a95a-379">Если есть простая хэш-таблица, как в нашем примере выше, можно использовать `.Clone()` для создания неполной копии.</span><span class="sxs-lookup"><span data-stu-id="8a95a-379">If we have a simple hashtable like our example above, we can use `.Clone()` to make a shallow copy.</span></span>

```powershell
PS> $orig = @{name='orig'}
PS> $copy = $orig.Clone()
PS> $copy.name = 'copy'
PS> 'Copy: [{0}]' -f $copy.name
PS> 'Orig: [{0}]' -f $orig.name

Copy: [copy]
Orig: [orig]
```

<span data-ttu-id="8a95a-380">Это позволит нам вносить базовые изменения в одни данные, и эти изменения не повлияют на другие данные.</span><span class="sxs-lookup"><span data-stu-id="8a95a-380">This will allow us to make some basic changes to one that don't impact the other.</span></span>

### <a name="shallow-copies-nested"></a><span data-ttu-id="8a95a-381">Неполные копии, вложенные</span><span class="sxs-lookup"><span data-stu-id="8a95a-381">Shallow copies, nested</span></span>

<span data-ttu-id="8a95a-382">Такая копия называется неполной, поскольку в нее добавляются только свойства базового уровня.</span><span class="sxs-lookup"><span data-stu-id="8a95a-382">The reason why it's called a shallow copy is because it only copies the base level properties.</span></span> <span data-ttu-id="8a95a-383">Если одно из этих свойств является ссылочным типом (например, другой хэш-таблицей), то эти вложенные объекты по-прежнему будут указывать друг на друга.</span><span class="sxs-lookup"><span data-stu-id="8a95a-383">If one of those properties is a reference type (like another hashtable), then those nested objects will still point to each other.</span></span>

```powershell
PS> $orig = @{
        person=@{
            name='orig'
        }
    }
PS> $copy = $orig.Clone()
PS> $copy.person.name = 'copy'
PS> 'Copy: [{0}]' -f $copy.person.name
PS> 'Orig: [{0}]' -f $orig.person.name

Copy: [copy]
Orig: [copy]
```

<span data-ttu-id="8a95a-384">Итак, вы видите, что, несмотря на то, что я клонировал хэш-таблицу, ссылка на `person` не была клонирована.</span><span class="sxs-lookup"><span data-stu-id="8a95a-384">So you can see that even though I cloned the hashtable, the reference to `person` wasn't cloned.</span></span> <span data-ttu-id="8a95a-385">Чтобы получить вторую хэш-таблицу, которая не связана с первой, необходимо создать полную копию.</span><span class="sxs-lookup"><span data-stu-id="8a95a-385">We need to make a deep copy to truly have a second hashtable that isn't linked to the first.</span></span>

### <a name="deep-copies"></a><span data-ttu-id="8a95a-386">Полные копии</span><span class="sxs-lookup"><span data-stu-id="8a95a-386">Deep copies</span></span>

<span data-ttu-id="8a95a-387">На момент написания этой статьи мне неизвестно о каких-либо эффективных способах создания полной копии хэш-таблицы (и сохранения ее в виде хэш-таблицы).</span><span class="sxs-lookup"><span data-stu-id="8a95a-387">At the time of writing this, I'm not aware of any clever ways to just make a deep copy of a hashtable (and keep it as a hashtable).</span></span> <span data-ttu-id="8a95a-388">Это как раз та вещь, о которой кому-нибудь стоит написать.</span><span class="sxs-lookup"><span data-stu-id="8a95a-388">That's just one of those things that someone needs to write.</span></span>
<span data-ttu-id="8a95a-389">Вот как это можно быстро сделать.</span><span class="sxs-lookup"><span data-stu-id="8a95a-389">Here is a quick method to do that.</span></span>

```powershell
function Get-DeepClone
{
    [CmdletBinding()]
    param(
        $InputObject
    )
    process
    {
        if($InputObject -is [hashtable]) {
            $clone = @{}
            foreach($key in $InputObject.keys)
            {
                $clone[$key] = Get-DeepClone $InputObject[$key]
            }
            return $clone
        } else {
            return $InputObject
        }
    }
}
```

<span data-ttu-id="8a95a-390">При этом не обрабатываются любые другие ссылочные типы или массивы, но это хорошая отправная точка.</span><span class="sxs-lookup"><span data-stu-id="8a95a-390">It doesn't handle any other reference types or arrays, but it's a good starting point.</span></span>

## <a name="anything-else"></a><span data-ttu-id="8a95a-391">Что-нибудь еще?</span><span class="sxs-lookup"><span data-stu-id="8a95a-391">Anything else?</span></span>

<span data-ttu-id="8a95a-392">Я кратко охватил большое количество вопросов.</span><span class="sxs-lookup"><span data-stu-id="8a95a-392">I covered a lot of ground quickly.</span></span> <span data-ttu-id="8a95a-393">Надеюсь, что при каждом прочтении вы будете находить для себя что-то новое.</span><span class="sxs-lookup"><span data-stu-id="8a95a-393">My hope is that you walk away leaning something new or understanding it better every time you read this.</span></span> <span data-ttu-id="8a95a-394">Хотя я рассмотрел весь спектр возможностей этой функции, есть все-таки несколько аспектов, которые в настоящее время могут быть неприменимы.</span><span class="sxs-lookup"><span data-stu-id="8a95a-394">Because I covered the full spectrum of this feature, there are aspects that just may not apply to you right now.</span></span> <span data-ttu-id="8a95a-395">Это вполне приемлемо и ожидаемо. Все зависит от того, насколько активно вы используете PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8a95a-395">That is perfectly OK and is kind of expected depending on how much you work with PowerShell.</span></span>

<!-- link references -->
[Оригинал]: https://powershellexplained.com/2016-11-06-powershell-hashtable-everything-you-wanted-to-know-about/
[original version]: https://powershellexplained.com/2016-11-06-powershell-hashtable-everything-you-wanted-to-know-about/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[хэш-таблицах]: /powershell/module/microsoft.powershell.core/about/about_hash_tables
[hashtables]: /powershell/module/microsoft.powershell.core/about/about_hash_tables
[массивах]: /powershell/module/microsoft.powershell.core/about/about_arrays
[arrays]: /powershell/module/microsoft.powershell.core/about/about_arrays
[Если имеет значение производительность, протестируйте ее]: https://github.com/PoshCode/PowerShellPracticeAndStyle/blob/master/Best-Practices/Performance.md
[If performance matters, test it]: https://github.com/PoshCode/PowerShellPracticeAndStyle/blob/master/Best-Practices/Performance.md
[сплаттинг]: /powershell/module/microsoft.powershell.core/about/about_splatting
[splatting]: /powershell/module/microsoft.powershell.core/about/about_splatting
[PCSCustomObject]: everything-about-pscustomobject.md
[pscustomobject]: everything-about-pscustomobject.md
[JavaScriptSerializer]: /dotnet/api/system.web.script.serialization.javascriptserializer?view=netframework-4.8&preserve-view=true
[PSBoundParameters]: https://tommymaynard.com/the-psboundparameters-automatic-variable-2016/
[about_Automatic_Variables]: /powershell/module/microsoft.powershell.core/about/about_automatic_variables
[Автоматические значения по умолчанию]: https://www.simple-talk.com/sysadmin/PowerShell/PowerShell-time-saver-automatic-defaults/
[Automatic Defaults]: https://www.simple-talk.com/sysadmin/PowerShell/PowerShell-time-saver-automatic-defaults/
[Майкл Соренс]: http://cleancode.sourceforge.net/wwwdoc/about.html
[Michael Sorens]: http://cleancode.sourceforge.net/wwwdoc/about.html
