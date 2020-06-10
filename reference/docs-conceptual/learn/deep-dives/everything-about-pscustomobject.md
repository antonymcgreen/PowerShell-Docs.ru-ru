---
title: Все, что вы хотели знать о PSCustomObject
description: PSCustomObject — это простое средство для создания структурированных данных.
ms.date: 05/23/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: fbc8b5b6d2cfafaa75fa820f420762a1804074ac
ms.sourcegitcommit: ed4a895d672334c7b02fb7ef6e950dbc2ba4a197
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/28/2020
ms.locfileid: "84149497"
---
# <a name="everything-you-wanted-to-know-about-pscustomobject"></a><span data-ttu-id="c2bf1-103">Все, что вы хотели знать о PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="c2bf1-103">Everything you wanted to know about PSCustomObject</span></span>

<span data-ttu-id="c2bf1-104">Объекты `PSCustomObject` — это отличное средство, которое стоит добавить в набор инструментов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-104">`PSCustomObject`s are a great tool to add into your PowerShell tool belt.</span></span> <span data-ttu-id="c2bf1-105">Начнем с основ, а затем постепенно перейдем к работе с более сложными функциями.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-105">Let's start with the basics and work our way into the more advanced features.</span></span> <span data-ttu-id="c2bf1-106">`PSCustomObject` стоит использовать потому, что это простой способ создания структурированных данных.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-106">The idea behind using a `PSCustomObject` is to have a simple way to create structured data.</span></span> <span data-ttu-id="c2bf1-107">Взгляните на первый пример, и вы получите более наглядное представление о том, что я имею в виду.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-107">Take a look at the first example and you'll have a better idea of what that means.</span></span>

> [!NOTE]
> <span data-ttu-id="c2bf1-108">[Оригинал][] этой статьи впервые был опубликован в блоге автора [@KevinMarquette][].</span><span class="sxs-lookup"><span data-stu-id="c2bf1-108">The [original version][] of this article appeared on the blog written by [@KevinMarquette][].</span></span> <span data-ttu-id="c2bf1-109">Команда разработчиков PowerShell благодарит Кевина за то, что он поделился с нами этим материалом.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-109">The PowerShell team thanks Kevin for sharing this content with us.</span></span> <span data-ttu-id="c2bf1-110">Читайте его блог — [PowerShellExplained.com][].</span><span class="sxs-lookup"><span data-stu-id="c2bf1-110">Please check out his blog at [PowerShellExplained.com][].</span></span>

## <a name="creating-a-pscustomobject"></a><span data-ttu-id="c2bf1-111">Создание PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="c2bf1-111">Creating a PSCustomObject</span></span>

<span data-ttu-id="c2bf1-112">Мне нравится использовать `[PSCustomObject]` в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-112">I love using `[PSCustomObject]` in PowerShell.</span></span> <span data-ttu-id="c2bf1-113">Создать пригодный к использованию объект просто, как никогда.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-113">Creating a usable object has never been easier.</span></span>
<span data-ttu-id="c2bf1-114">Вот почему я опущу все остальные способы создания объекта. Однако обратите внимание, что большинство из этих примеров для PowerShell версии 3.0 и более поздних.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-114">Because of that, I'm going to skip over all the other ways you can create an object but I need to mention that most of these examples are PowerShell v3.0 and newer.</span></span>

```powershell
$myObject = [PSCustomObject]@{
    Name     = 'Kevin'
    Language = 'PowerShell'
    State    = 'Texas'
}
```

<span data-ttu-id="c2bf1-115">Этот метод хорошо мне подходит, поскольку я практически везде использую хэш-таблицы.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-115">This method works well for me because I use hashtables for just about everything.</span></span> <span data-ttu-id="c2bf1-116">Но иногда мне хочется, чтобы в PowerShell работа с хэш-таблицами была больше похожа на работу с объектами.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-116">But there are times when I would like PowerShell to treat hashtables more like an object.</span></span> <span data-ttu-id="c2bf1-117">Первое различие становится заметно, когда вы хотите использовать `Format-Table` или `Export-CSV` и понимаете, что хэш-таблица — это просто коллекция пар "ключ — значение".</span><span class="sxs-lookup"><span data-stu-id="c2bf1-117">The first place you notice the difference is when you want to use `Format-Table` or `Export-CSV` and you realize that a hashtable is just a collection of key/value pairs.</span></span>

<span data-ttu-id="c2bf1-118">При этом вы можете получать доступ к значениям и использовать их, как в случае с обычным объектом.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-118">You can then access and use the values like you would a normal object.</span></span>

```powershell
$myObject.Name
```

### <a name="converting-a-hashtable"></a><span data-ttu-id="c2bf1-119">Преобразование хэш-таблицы</span><span class="sxs-lookup"><span data-stu-id="c2bf1-119">Converting a hashtable</span></span>

<span data-ttu-id="c2bf1-120">Хотя мне не следует отступать от темы, возможно, не все знают о следующей возможности.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-120">While I am on the topic, did you know you could do this:</span></span>

```powershell
$myHashtable = @{
    Name     = 'Kevin'
    Language = 'PowerShell'
    State    = 'Texas'
}
$myObject = [pscustomobject]$myHashtable
```

<span data-ttu-id="c2bf1-121">Я предпочитаю создавать объект с самого начала, но иногда сначала приходится работать с хэш-таблицей.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-121">I do prefer to create the object from the start but there are times you have to work with a hashtable first.</span></span> <span data-ttu-id="c2bf1-122">Этот пример работает, поскольку конструктор принимает хэш-таблицу в качестве значения свойств объекта.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-122">This example works because the constructor takes a hashtable for the object properties.</span></span> <span data-ttu-id="c2bf1-123">Важно отметить, что хотя этот метод тоже работает, он не является точным эквивалентом.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-123">One important note is that while this method works, it isn't an exact equivalent.</span></span> <span data-ttu-id="c2bf1-124">Самое большое отличие заключается в том, что порядок свойств не сохраняется.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-124">The biggest difference is that the order of the properties isn't preserved.</span></span>

### <a name="legacy-approach"></a><span data-ttu-id="c2bf1-125">Устаревший подход</span><span class="sxs-lookup"><span data-stu-id="c2bf1-125">Legacy approach</span></span>

<span data-ttu-id="c2bf1-126">Возможно, вы видели, что некоторые разработчики используют `New-Object` для создания пользовательских объектов.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-126">You may have seen people use `New-Object` to create custom objects.</span></span>

```powershell
$myHashtable = @{
    Name     = 'Kevin'
    Language = 'PowerShell'
    State    = 'Texas'
}

$myObject = New-Object -TypeName PSObject -Property $myHashtable
```

<span data-ttu-id="c2bf1-127">Этот метод медленнее, но он может оказаться лучшим вариантом для ранних версий PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-127">This way is quite a bit slower but it may be your best option on early versions of PowerShell.</span></span>

### <a name="saving-to-a-file"></a><span data-ttu-id="c2bf1-128">Сохранение в папке</span><span class="sxs-lookup"><span data-stu-id="c2bf1-128">Saving to a file</span></span>

<span data-ttu-id="c2bf1-129">Самый лучший способ сохранить хэш-таблицу в файл — использовать формат JSON.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-129">I find the best way to save a hashtable to a file is to save it as JSON.</span></span> <span data-ttu-id="c2bf1-130">Вы можете импортировать ее обратно в `[PSCusomObject]`.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-130">You can import it back into a `[PSCusomObject]`</span></span>

```powershell
$myObject | ConvertTo-Json -depth 1- | Set-Content -Path $Path
$myObject = Get-Content -Path $Path | ConvertFrom-Json
```

<span data-ttu-id="c2bf1-131">Я рассказываю о других способах сохранения объектов в файл в моей статье о [Множество способов чтения и записи в файлы][].</span><span class="sxs-lookup"><span data-stu-id="c2bf1-131">I cover more ways to save objects to a file in my article on [The many ways to read and write to files][].</span></span>

## <a name="working-with-properties"></a><span data-ttu-id="c2bf1-132">Работа со свойствами</span><span class="sxs-lookup"><span data-stu-id="c2bf1-132">Working with properties</span></span>

### <a name="adding-properties"></a><span data-ttu-id="c2bf1-133">Добавление свойств</span><span class="sxs-lookup"><span data-stu-id="c2bf1-133">Adding properties</span></span>

<span data-ttu-id="c2bf1-134">Вы по-прежнему можете добавлять новые свойства в объект `PSCustomObject` с помощью `Add-Member`.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-134">You can still add new properties to your `PSCustomObject` with `Add-Member`.</span></span>

```powershell
$myObject | Add-Member -MemberType NoteProperty -Name `ID` -Value 'KevinMarquette'

$myObject.ID
```

### <a name="remove-properties"></a><span data-ttu-id="c2bf1-135">Удаление свойств</span><span class="sxs-lookup"><span data-stu-id="c2bf1-135">Remove properties</span></span>

<span data-ttu-id="c2bf1-136">Вы также можете удалять свойства из объекта.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-136">You can also remove properties off of an object.</span></span>

```powershell
$myObject.psobject.properties.remove('ID')
```

<span data-ttu-id="c2bf1-137">Доступ к метаданным базового объекта можно получить с помощью скрытого свойства `psobject`.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-137">The `psobject` is a hidden property that gives you access to base object metadata.</span></span>

### <a name="enumerating-property-names"></a><span data-ttu-id="c2bf1-138">Перечисление имен свойств</span><span class="sxs-lookup"><span data-stu-id="c2bf1-138">Enumerating property names</span></span>

<span data-ttu-id="c2bf1-139">Иногда требуется список всех имен свойств объекта.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-139">Sometimes you need a list of all the property names on an object.</span></span>

```powershell
$myObject | Get-Member -MemberType NoteProperty | Select -ExpandProperty Name
```

<span data-ttu-id="c2bf1-140">Его можно также получить из свойства `psobject`.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-140">We can get this same list off of the `psobject` property too.</span></span>

```powershell
$myobject.psobject.properties.name
```

### <a name="dynamically-accessing-properties"></a><span data-ttu-id="c2bf1-141">Динамический доступ к свойствам</span><span class="sxs-lookup"><span data-stu-id="c2bf1-141">Dynamically accessing properties</span></span>

<span data-ttu-id="c2bf1-142">Я уже упоминал, что доступ к значениям свойств можно получить напрямую.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-142">I already mentioned that you can access property values directly.</span></span>

```powershell
$myObject.Name
```

<span data-ttu-id="c2bf1-143">В качестве имени свойства можно использовать строку, и это сработает.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-143">You can use a string for the property name and it will still work.</span></span>

```powershell
$myObject.'Name'
```

<span data-ttu-id="c2bf1-144">Можно пойти дальше и использовать в качестве имени свойства переменную.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-144">We can take this one more step and use a variable for the property name.</span></span>

```powershell
$property = 'Name'
$myObject.$property
```

<span data-ttu-id="c2bf1-145">Я знаю, что выглядит это странно, но это работает.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-145">I know that looks strange, but it works.</span></span>

### <a name="convert-pscustomboject-into-a-hashtable"></a><span data-ttu-id="c2bf1-146">Преобразование объекта pscustomboject в хэш-таблицу</span><span class="sxs-lookup"><span data-stu-id="c2bf1-146">Convert pscustomboject into a hashtable</span></span>

<span data-ttu-id="c2bf1-147">В продолжение сделанного в последнем разделе можно динамически проанализировать свойства и создать из них хэш-таблицу.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-147">To continue on from the last section, you can dynamically walk the properties and create a hashtable from them.</span></span>

```powershell
$hashtable = @{}
foreach( $property in $myobject.psobject.properties.name )
{
    $hashtable[$property] = $myObject.$property
}
```

### <a name="testing-for-properties"></a><span data-ttu-id="c2bf1-148">Проверка свойств</span><span class="sxs-lookup"><span data-stu-id="c2bf1-148">Testing for properties</span></span>

<span data-ttu-id="c2bf1-149">Если необходимо узнать, существует ли свойство, можно просто проверить, есть ли у него значение.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-149">If you need to know if a property exists, you could just check for that property to have a value.</span></span>

```powershell
if( $null -ne $myObject.ID )
```

<span data-ttu-id="c2bf1-150">Но если это значение может быть равным `$null`, а вам все равно нужно проверить его наличие, можно проверить для него `psobject.properties`.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-150">But if the value could be `$null` and you still need to check for it, you can check the `psobject.properties` for it.</span></span>

```powershell
if( $myobject.psobject.properties.match('ID') )
```

## <a name="adding-object-methods"></a><span data-ttu-id="c2bf1-151">Добавление методов объектов</span><span class="sxs-lookup"><span data-stu-id="c2bf1-151">Adding object methods</span></span>

<span data-ttu-id="c2bf1-152">Если в объект необходимо добавить метод скрипта, это можно сделать с помощью `Add-Member` и `ScriptBlock`.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-152">If you need to add a script method to an object, you can do it with `Add-Member` and a `ScriptBlock`.</span></span> <span data-ttu-id="c2bf1-153">При этом необходимо использовать автоматическую переменную `this`, ссылающуюся на текущий объект.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-153">You have to use the `this` automatic variable reference the current object.</span></span> <span data-ttu-id="c2bf1-154">Ниже приведен блок `scriptblock` для преобразования объекта в хэш-таблицу.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-154">Here is a `scriptblock` to turn an object into a hashtable.</span></span> <span data-ttu-id="c2bf1-155">(Это тот же код, что и в последнем примере.)</span><span class="sxs-lookup"><span data-stu-id="c2bf1-155">(same code form the last example)</span></span>

```powershell
$ScriptBlock = {
    $hashtable = @{}
    foreach( $property in $this.psobject.properties.name )
    {
        $hashtable[$property] = $this.$property
    }
    return $hashtable
}
```

<span data-ttu-id="c2bf1-156">Затем мы добавим его к нашему объекту в качестве свойства скрипта.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-156">Then we add it to our object as a script property.</span></span>

```powershell
$memberParam = @{
    MemberType = "ScriptMethod"
    InputObject = $myobject
    Name = "ToHashtable"
    Value = $scriptBlock
}
Add-Member @memberParam
```

<span data-ttu-id="c2bf1-157">Теперь мы можем вызвать нашу функцию следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c2bf1-157">Then we can call our function like this:</span></span>

```powershell
$myObject.ToHashtable()
```

### <a name="objects-vs-value-types"></a><span data-ttu-id="c2bf1-158">Объекты и типы значений</span><span class="sxs-lookup"><span data-stu-id="c2bf1-158">Objects vs Value types</span></span>

<span data-ttu-id="c2bf1-159">Объекты и типы значений обрабатывают назначения переменных по-разному.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-159">Objects and value types don't handle variable assignments the same way.</span></span> <span data-ttu-id="c2bf1-160">Если типы значений присваиваются друг другу, в новую переменную копируется только значение.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-160">If you assign value types to each other, only the value get copied to the new variable.</span></span>

```powershell
$first = 1
$second = $first
$second = 2
```

<span data-ttu-id="c2bf1-161">В этом случае `$first` равно 1, а `$second` — 2.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-161">In this case, `$first` is 1 and `$second` is 2.</span></span>

<span data-ttu-id="c2bf1-162">Объектные переменные содержат ссылку на фактический объект.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-162">Object variables hold a reference to the actual object.</span></span> <span data-ttu-id="c2bf1-163">При назначении одного объекта новой переменной они по-прежнему ссылаются на один и тот же объект.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-163">When you assign one object to a new variable, they still reference the same object.</span></span>

```powershell
$third = [PSCustomObject]@{Key=3}
$fourth = $third
$fourth.Key = 4
```

<span data-ttu-id="c2bf1-164">Поскольку `$third` и `$fourth` ссылаются на один и тот же экземпляр объекта, значение `$third.key` и `$fourth.Key` равно 4.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-164">Because `$third` and `$fourth` reference the same instance of an object, both `$third.key` and `$fourth.Key` are 4.</span></span>

### <a name="psobjectcopy"></a><span data-ttu-id="c2bf1-165">psobject.copy()</span><span class="sxs-lookup"><span data-stu-id="c2bf1-165">psobject.copy()</span></span>

<span data-ttu-id="c2bf1-166">Если вам нужна копия объекта, его можно клонировать.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-166">If you need a true copy of an object, you can clone it.</span></span>

```powershell
$third = [PSCustomObject]@{Key=3}
$fourth = $third.psobject.copy()
$fourth.Key = 4
```

<span data-ttu-id="c2bf1-167">При клонировании создается неполная копия объекта.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-167">Clone creates a shallow copy of the object.</span></span> <span data-ttu-id="c2bf1-168">Теперь экземпляры разные, и в этом примере `$third.key` равно 3, а `$fourth.Key` — 4.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-168">They have different instances now and `$third.key` is 3 and `$fourth.Key` is 4 in this example.</span></span>

<span data-ttu-id="c2bf1-169">Я называю это неполной копией, так как при наличии вложенных объектов</span><span class="sxs-lookup"><span data-stu-id="c2bf1-169">I call this a shallow copy because if you have nested objects.</span></span> <span data-ttu-id="c2bf1-170">(когда свойства содержат другие объекты)</span><span class="sxs-lookup"><span data-stu-id="c2bf1-170">(where the properties contain other objects).</span></span> <span data-ttu-id="c2bf1-171">копируются только значения верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-171">Only the top-level values are copied.</span></span> <span data-ttu-id="c2bf1-172">Дочерние объекты будут ссылаться друг на друга.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-172">The child objects will reference each other.</span></span>

### <a name="pstypename-for-custom-object-types"></a><span data-ttu-id="c2bf1-173">PSTypeName для пользовательских типов объектов</span><span class="sxs-lookup"><span data-stu-id="c2bf1-173">PSTypeName for custom object types</span></span>

<span data-ttu-id="c2bf1-174">Теперь, когда у нас есть объект, мы можем выполнить с ним еще несколько действий, которые могут быть не так очевидны.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-174">Now that we have an object, there are a few more things we can do with it that may not be nearly as obvious.</span></span> <span data-ttu-id="c2bf1-175">Прежде всего необходимо присвоить ему `PSTypeName`.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-175">First thing we need to do is give it a `PSTypeName`.</span></span> <span data-ttu-id="c2bf1-176">Это, насколько я знаю, наиболее распространенный способ.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-176">This is the most common way I see people do it:</span></span>

```powershell
$myObject.PSObject.TypeNames.Insert(0,"My.Object")
```

<span data-ttu-id="c2bf1-177">Недавно я обнаружил, что это можно сделать другим способом. Узнал я о нем здесь из [публикации /u/markekraus][].</span><span class="sxs-lookup"><span data-stu-id="c2bf1-177">I recently discovered another way to do this from this [post by /u/markekraus][].</span></span> <span data-ttu-id="c2bf1-178">Я изучил этот вопрос глубже и сделал несколько публикаций об идее [Адам Бертрам][] и [Майк Шепард][], где излагаю их мнение об этом подходе, который позволяет создавать встроенные определения.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-178">I did a little digging and more posts about the idea from [Adam Bertram][] and [Mike Shepard][] where they talk about this approach that allows you to define it inline.</span></span>

```powershell
$myObject = [PSCustomObject]@{
    PSTypeName = 'My.Object'
    Name       = 'Kevin'
    Language   = 'PowerShell'
    State      = 'Texas'
}
```

<span data-ttu-id="c2bf1-179">Мне нравится то, как хорошо он соответствует языку.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-179">I love how nicely this just fits into the language.</span></span> <span data-ttu-id="c2bf1-180">Теперь, когда у нас есть объект с правильным именем типа, мы можем сделать кое-что еще.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-180">Now that we have an object with a proper type name, we can do some more things.</span></span>

## <a name="using-defaultpropertyset-the-long-way"></a><span data-ttu-id="c2bf1-181">Использование DefaultPropertySet (длинный способ)</span><span class="sxs-lookup"><span data-stu-id="c2bf1-181">Using DefaultPropertySet (the long way)</span></span>

<span data-ttu-id="c2bf1-182">PowerShell автоматически выбирает отображаемые свойства по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-182">PowerShell decides for us what properties to display by default.</span></span> <span data-ttu-id="c2bf1-183">У многих собственных команд имеется [файл форматирования ][] `.ps1xml`, который выполняет всю тяжелую работу.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-183">A lot of the native commands have a `.ps1xml` [formatting file][] that does all the heavy lifting.</span></span> <span data-ttu-id="c2bf1-184">В [публикация Бо Прокса][] предложен еще один способ сделать это с пользовательским объектом, используя только PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-184">From this [post by Boe Prox][], there's another way for us to do this on our custom object using just PowerShell.</span></span> <span data-ttu-id="c2bf1-185">Ему можно присвоить `MemberSet` для использования.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-185">We can give it a `MemberSet` for it to use.</span></span>

```powershell
$defaultDisplaySet = 'Name','Language'
$defaultDisplayPropertySet = New-Object System.Management.Automation.PSPropertySet(‘DefaultDisplayPropertySet’,[string[]]$defaultDisplaySet)
$PSStandardMembers = [System.Management.Automation.PSMemberInfo[]]@($defaultDisplayPropertySet)
$MyObject | Add-Member MemberSet PSStandardMembers $PSStandardMembers
```

<span data-ttu-id="c2bf1-186">Теперь, когда объект оказался в оболочке, для него по умолчанию будут отображаться только эти свойства.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-186">Now when my object just falls to the shell, it will only show those properties by default.</span></span>

### <a name="update-typedata-with-defaultpropertyset"></a><span data-ttu-id="c2bf1-187">Update-TypeData с DefaultPropertySet</span><span class="sxs-lookup"><span data-stu-id="c2bf1-187">Update-TypeData with DefaultPropertySet</span></span>

<span data-ttu-id="c2bf1-188">Это удобный способ, но недавно при просмотре видео [PowerShell 2016 без подключения с Джеффри Сновером и Доном Джонсом][psunplugged] я узнал, что есть еще удобнее.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-188">This is nice but I recently saw a better way when watching [PowerShell unplugged 2016 with Jeffrey Snover & Don Jones][psunplugged].</span></span> <span data-ttu-id="c2bf1-189">Чтобы указать свойства по умолчанию, Джеффри использовал [Update-TypeData][].</span><span class="sxs-lookup"><span data-stu-id="c2bf1-189">Jeffrey was using [Update-TypeData][] to specify the default properties.</span></span>

```powershell
$TypeData = @{
    TypeName = 'My.Object'
    DefaultDisplayPropertySet = 'Name','Language'
}
Update-TypeData @TypeData
```

<span data-ttu-id="c2bf1-190">Это так просто, что я бы даже запомнил этот способ, если бы у меня не было под рукой этой публикации для справки.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-190">That is simple enough that I could almost remember it if I didn't have this post as a quick reference.</span></span> <span data-ttu-id="c2bf1-191">Теперь я могу легко создавать объекты с большим количеством свойств, которые будут выглядеть все так же аккуратно и понятно при просмотре из оболочки.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-191">Now I can easily create objects with lots of properties and still give it a nice clean view when looking at it from the shell.</span></span> <span data-ttu-id="c2bf1-192">Если мне нужно получить доступ к другим свойствам или просмотреть их, они всегда под рукой.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-192">If I need to access or see those other properties, they're still there.</span></span>

```powershell
$myObject | Format-List *
```

### <a name="update-typedata-with-scriptproperty"></a><span data-ttu-id="c2bf1-193">Update-TypeData со ScriptProperty</span><span class="sxs-lookup"><span data-stu-id="c2bf1-193">Update-TypeData with ScriptProperty</span></span>

<span data-ttu-id="c2bf1-194">Из этого видео я также узнал, как создавать свойства скрипта для объектов.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-194">Something else I got out of that video was creating script properties for your objects.</span></span> <span data-ttu-id="c2bf1-195">Стоит отметить, что этот подход работает и для имеющихся объектов.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-195">This would be a good time to point out that this works for existing objects too.</span></span>

```powershell
$TypeData = @{
    TypeName = 'My.Object'
    MemberType = 'ScriptProperty'
    MemberName = 'UpperCaseName'
    Value = {$this.Name.toUpper()}
}
Update-TypeData @TypeData
```

<span data-ttu-id="c2bf1-196">Его можно применить как до создания объекта, так и после, и все равно все получится.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-196">You can do this before your object is created or after and it will still work.</span></span> <span data-ttu-id="c2bf1-197">Этим данный подход и отличается от использования `Add-Member` со свойством скрипта.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-197">This is what makes this different then using `Add-Member` with a script property.</span></span> <span data-ttu-id="c2bf1-198">При использовании `Add-Member` (этот способ я описал ранее) свойство существует только в данном конкретном экземпляре объекта.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-198">When you use `Add-Member` the way I referenced earlier, it only exists on that specific instance of the object.</span></span> <span data-ttu-id="c2bf1-199">Это относится ко всем объектам с таким значением `TypeName`.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-199">This one applies to all objects with this `TypeName`.</span></span>

## <a name="function-parameters"></a><span data-ttu-id="c2bf1-200">Параметры функции</span><span class="sxs-lookup"><span data-stu-id="c2bf1-200">Function parameters</span></span>

<span data-ttu-id="c2bf1-201">Теперь эти пользовательские типы можно применять для параметров в функциях и скриптах.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-201">You can now use these custom types for parameters in your functions and scripts.</span></span> <span data-ttu-id="c2bf1-202">Одна функция может создать эти пользовательские объекты и передать их в другие функции.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-202">You can have one function create these custom objects and then pass them into other functions.</span></span>

```powershell
param( [PSTypeName('My.Object')]$Data )
```

<span data-ttu-id="c2bf1-203">В PowerShell требуется, чтобы объект принадлежал к указанному типу.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-203">PowerShell requires that the object is the type you specified.</span></span> <span data-ttu-id="c2bf1-204">Если при автоматической проверке обнаруживается несоответствие типов, выводится сообщение об ошибке проверки, чтобы вам не пришлось делать лишний шаг при тестировании.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-204">It throws a validation error if the type doesn't match automatically to save you the step of testing for it in your code.</span></span> <span data-ttu-id="c2bf1-205">Это отличный пример того, как оптимально использовать преимущества PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-205">A great example of letting PowerShell do what it does best.</span></span>

### <a name="function-outputtype"></a><span data-ttu-id="c2bf1-206">Тип OutputType функции</span><span class="sxs-lookup"><span data-stu-id="c2bf1-206">Function OutputType</span></span>

<span data-ttu-id="c2bf1-207">Вы можете также определить `OutputType` для расширенных функций.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-207">You can also define an `OutputType` for your advanced functions.</span></span>

```powershell
function Get-MyObject
{
    [OutputType('My.Object')]
    [CmdletBinding()]
        param
        (
            ...
```

<span data-ttu-id="c2bf1-208">Значение атрибута **OutputType** предназначено только для документации.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-208">The **OutputType** attribute value is only a documentation note.</span></span> <span data-ttu-id="c2bf1-209">Он не является производным от кода функции и не сравнивается с ее фактическими выходными данными.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-209">It isn't derived from the function code or compared to the actual function output.</span></span>

<span data-ttu-id="c2bf1-210">Основная причина использования выходного типа заключается в том, что метаданные, относящиеся к вашей функции, должны отражать ваши намерения.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-210">The main reason you would use an output type is so that meta information about your function reflects your intentions.</span></span> <span data-ttu-id="c2bf1-211">Это могут быть `Get-Command` и `Get-Help`, преимущества которых можно использовать в среде разработки.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-211">Things like `Get-Command` and `Get-Help` that your development environment can take advantage of.</span></span> <span data-ttu-id="c2bf1-212">Дополнительные сведения см. в справке: [about_Functions_OutputTypeAttribute][].</span><span class="sxs-lookup"><span data-stu-id="c2bf1-212">If you want more information, then take a look at the help for it: [about_Functions_OutputTypeAttribute][].</span></span>

<span data-ttu-id="c2bf1-213">При этом, если вы используете Pester для модульного тестирования функций, неплохо было бы убедиться, что выходные объекты соответствуют типу **OutputType**.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-213">With that said, if you're using Pester to unit test your functions then it would be a good idea to validate the output objects match your **OutputType**.</span></span> <span data-ttu-id="c2bf1-214">Это позволит перехватить переменные, которые попадают в канал, в котором их быть не должно.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-214">This could catch variables that just fall to the pipe when they shouldn't.</span></span>

## <a name="closing-thoughts"></a><span data-ttu-id="c2bf1-215">Выводы</span><span class="sxs-lookup"><span data-stu-id="c2bf1-215">Closing thoughts</span></span>

<span data-ttu-id="c2bf1-216">Эта статья посвящена `[PSCustomObject]`, но многие из этих сведений относятся к объектам в целом.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-216">The context of this was all about `[PSCustomObject]`, but a lot of this information applies to objects in general.</span></span>

<span data-ttu-id="c2bf1-217">Я уже встречал сведения об этих возможностях ранее, но никогда не видел, чтобы они были собраны в единый документ по `PSCustomObject`.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-217">I have seen most of these features in passing before but never saw them presented as a collection of information on `PSCustomObject`.</span></span> <span data-ttu-id="c2bf1-218">Буквально на прошлой неделе я наткнулся на такую информацию и был удивлен, что никогда ранее ее не встречал.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-218">Just this last week I stumbled upon another one and was surprised that I had not seen it before.</span></span> <span data-ttu-id="c2bf1-219">Я хотел объединить все эти идеи, чтобы вы могли увидеть более полную картину и знали о том, что такие возможности существуют, когда они вам понадобятся.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-219">I wanted to pull all these ideas together so you can hopefully see the bigger picture and be aware of them when you have an opportunity to use them.</span></span> <span data-ttu-id="c2bf1-220">Надеюсь, что вы чему-то научились и сможете применить эти знания на практике в своих сценариях.</span><span class="sxs-lookup"><span data-stu-id="c2bf1-220">I hope you learned something and can find a way to work this into your scripts.</span></span>

<!-- link references -->
[Оригинал]: https://powershellexplained.com/2016-10-28-powershell-everything-you-wanted-to-know-about-pscustomobject/
[original version]: https://powershellexplained.com/2016-10-28-powershell-everything-you-wanted-to-know-about-pscustomobject/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[публикация Бо Прокса]: https://learn-PowerShell.net/2013/08/03/quick-hits-set-the-default-property-display-in-PowerShell-on-custom-objects/
[post by Boe Prox]: https://learn-PowerShell.net/2013/08/03/quick-hits-set-the-default-property-display-in-PowerShell-on-custom-objects/
[файл форматирования ]: https://mcpmag.com/articles/2014/05/13/PowerShell-properties-part-3.aspx
[formatting file]: https://mcpmag.com/articles/2014/05/13/PowerShell-properties-part-3.aspx
[about_Functions_OutputTypeAttribute]: /powershell/module/microsoft.powershell.core/about/about_functions_outputtypeattribute
[Множество способов чтения и записи в файлы]: https://powershellexplained.com/2017-03-18-Powershell-reading-and-saving-data-to-files
[The many ways to read and write to files]: https://powershellexplained.com/2017-03-18-Powershell-reading-and-saving-data-to-files
[публикации /u/markekraus]: https://www.reddit.com/r/PowerShell/comments/590awc/is_it_possible_to_initialize_a_pscustoobject_with/
[post by /u/markekraus]: https://www.reddit.com/r/PowerShell/comments/590awc/is_it_possible_to_initialize_a_pscustoobject_with/
[Адам Бертрам]: http://www.adamtheautomator.com/building-custom-object-types-PowerShell-pstypename/
[Adam Bertram]: http://www.adamtheautomator.com/building-custom-object-types-PowerShell-pstypename/
[Майк Шепард]: https://powershellstation.com/2016/05/22/custom-objects-and-pstypename/
[Mike Shepard]: https://powershellstation.com/2016/05/22/custom-objects-and-pstypename/
[psunplugged]: https://www.youtube.com/watch?v=Ab46gHXNm8Q
[Update-TypeData]: /powershell/module/microsoft.powershell.utility/update-typedata
