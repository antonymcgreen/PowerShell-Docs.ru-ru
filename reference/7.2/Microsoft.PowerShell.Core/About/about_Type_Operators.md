---
description: Описывает операторы, работающие с типами Microsoft .NET.
Locale: en-US
ms.date: 10/15/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_type_operators?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Type_Operators
ms.openlocfilehash: 66687a2282cfd321146888daad92fef40ef6cb0a
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604492"
---
# <a name="about-type-operators"></a><span data-ttu-id="ada52-103">Об операторах типов</span><span class="sxs-lookup"><span data-stu-id="ada52-103">About Type Operators</span></span>

## <a name="short-description"></a><span data-ttu-id="ada52-104">КРАТКОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="ada52-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="ada52-105">Описывает операторы, работающие с типами Microsoft .NET.</span><span class="sxs-lookup"><span data-stu-id="ada52-105">Describes the operators that work with Microsoft .NET types.</span></span>

## <a name="long-description"></a><span data-ttu-id="ada52-106">ПОДРОБНОЕ ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="ada52-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="ada52-107">Операторы логического типа ( `-is` и `-isNot` ) сообщают, является ли объект экземпляром указанного типа .NET.</span><span class="sxs-lookup"><span data-stu-id="ada52-107">The Boolean type operators (`-is` and `-isNot`) tell whether an object is an instance of a specified .NET type.</span></span> <span data-ttu-id="ada52-108">`-is`Оператор возвращает значение **true** , если тип соответствует, и значение **false** в противном случае.</span><span class="sxs-lookup"><span data-stu-id="ada52-108">The `-is` operator returns a value of **TRUE** if the type matches and a value of **FALSE** otherwise.</span></span> <span data-ttu-id="ada52-109">`-isNot`Оператор возвращает значение **false** , если тип соответствует, и значение **true** в противном случае.</span><span class="sxs-lookup"><span data-stu-id="ada52-109">The `-isNot` operator returns a value of **FALSE** if the type matches and a value of **TRUE** otherwise.</span></span>

<span data-ttu-id="ada52-110">`-as`Оператор пытается преобразовать входной объект в указанный тип .NET.</span><span class="sxs-lookup"><span data-stu-id="ada52-110">The `-as` operator tries to convert the input object to the specified .NET type.</span></span> <span data-ttu-id="ada52-111">Если он завершается, возвращается преобразованный объект.</span><span class="sxs-lookup"><span data-stu-id="ada52-111">If it succeeds, it returns the converted object.</span></span> <span data-ttu-id="ada52-112">В противном случае возвращается `$null`.</span><span class="sxs-lookup"><span data-stu-id="ada52-112">If it fails, it returns `$null`.</span></span> <span data-ttu-id="ada52-113">Он не возвращает ошибку.</span><span class="sxs-lookup"><span data-stu-id="ada52-113">It does not return an error.</span></span>

<span data-ttu-id="ada52-114">В следующей таблице перечислены операторы типа в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ada52-114">The following table lists the type operators in PowerShell.</span></span>

|<span data-ttu-id="ada52-115">Оператор</span><span class="sxs-lookup"><span data-stu-id="ada52-115">Operator</span></span>|<span data-ttu-id="ada52-116">Описание</span><span class="sxs-lookup"><span data-stu-id="ada52-116">Description</span></span>                |<span data-ttu-id="ada52-117">Пример</span><span class="sxs-lookup"><span data-stu-id="ada52-117">Example</span></span>                          |
|--------|---------------------------|---------------------------------|
|`-is`   |<span data-ttu-id="ada52-118">Возвращает значение TRUE, если входные данные</span><span class="sxs-lookup"><span data-stu-id="ada52-118">Returns TRUE when the input</span></span>|`(get-date) -is [DateTime]`      |
|        |<span data-ttu-id="ada52-119">является экземпляром класса</span><span class="sxs-lookup"><span data-stu-id="ada52-119">is an instance of the</span></span>      |`True`                           |
|        |<span data-ttu-id="ada52-120">указанный тип .NET.</span><span class="sxs-lookup"><span data-stu-id="ada52-120">specified .NET type.</span></span>       |                                 |
|`-isNot`|<span data-ttu-id="ada52-121">Возвращает значение TRUE, если входные данные</span><span class="sxs-lookup"><span data-stu-id="ada52-121">Returns TRUE when the input</span></span>|`(get-date) -isNot [DateTime]`   |
|        |<span data-ttu-id="ada52-122">не является экземпляром</span><span class="sxs-lookup"><span data-stu-id="ada52-122">not an instance of the</span></span>     |`False`                          |
|        |<span data-ttu-id="ada52-123">Тип specified.NET.</span><span class="sxs-lookup"><span data-stu-id="ada52-123">specified.NET type.</span></span>        |                                 |
|`-as`   |<span data-ttu-id="ada52-124">Преобразует входные данные в</span><span class="sxs-lookup"><span data-stu-id="ada52-124">Converts the input to the</span></span>  |`"5/7/07" -as [DateTime]`        |
|        |<span data-ttu-id="ada52-125">указанный тип .NET.</span><span class="sxs-lookup"><span data-stu-id="ada52-125">specified .NET type.</span></span>       |`Monday, May 7, 2007 12:00:00 AM`|

<span data-ttu-id="ada52-126">Синтаксис операторов типа выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ada52-126">The syntax of the type operators is as follows:</span></span>

```powershell
<input> <operator> [.NET type]
```

<span data-ttu-id="ada52-127">Можно также использовать следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="ada52-127">You can also use the following syntax:</span></span>

```powershell
<input> <operator> ".NET type"
```

<span data-ttu-id="ada52-128">Тип .NET можно записать в виде имени типа в квадратных скобках или в виде строки, например `[DateTime]` или `"DateTime"` для **System. DateTime**.</span><span class="sxs-lookup"><span data-stu-id="ada52-128">The .NET type can be written as a type name in brackets or a string, such as `[DateTime]` or `"DateTime"` for **System.DateTime**.</span></span> <span data-ttu-id="ada52-129">Если тип не находится в корне пространства имен System, укажите полное имя типа объекта.</span><span class="sxs-lookup"><span data-stu-id="ada52-129">If the type is not at the root of the system namespace, specify the full name of the object type.</span></span> <span data-ttu-id="ada52-130">Можно опустить "System.".</span><span class="sxs-lookup"><span data-stu-id="ada52-130">You can omit "System.".</span></span> <span data-ttu-id="ada52-131">Например, чтобы указать **System. Diagnostics. Process**, введите `[System.Diagnostics.Process]` , `[Diagnostics.Process]` или `"Diagnostics.Process"` .</span><span class="sxs-lookup"><span data-stu-id="ada52-131">For example, to specify **System.Diagnostics.Process**, enter `[System.Diagnostics.Process]`, `[Diagnostics.Process]`, or `"Diagnostics.Process"`.</span></span>

<span data-ttu-id="ada52-132">Операторы типа всегда работают с входным объектом в целом.</span><span class="sxs-lookup"><span data-stu-id="ada52-132">The type operators always operate on the input object as a whole.</span></span> <span data-ttu-id="ada52-133">То есть, если входной объект является коллекцией, то это проверяемый тип _коллекции_ , а не типы _элементов_ коллекции.</span><span class="sxs-lookup"><span data-stu-id="ada52-133">That is, if the input object is a collection, it is the _collection_ type that is tested, not the types of the collection's _elements_.</span></span>

### <a name="-isisnot-operators"></a><span data-ttu-id="ada52-134">операторы-OR/isNot</span><span class="sxs-lookup"><span data-stu-id="ada52-134">-is/isNot operators</span></span>

<span data-ttu-id="ada52-135">Операторы **логического** типа ( `-is` и `-isNot` ) всегда возвращают **логическое** значение, даже если входные данные являются коллекцией объектов.</span><span class="sxs-lookup"><span data-stu-id="ada52-135">The **Boolean** type operators (`-is` and `-isNot`) always return a **Boolean** value, even if the input is a collection of objects.</span></span>

<span data-ttu-id="ada52-136">Если `<input>` — это тип, который совпадает с типом или является _производным_ от типа .NET, `-is` оператор возвращает `$True` .</span><span class="sxs-lookup"><span data-stu-id="ada52-136">If `<input>` is a type that is the same as or is _derived_ from the .NET Type, the `-is` operator returns `$True`.</span></span>

<span data-ttu-id="ada52-137">Например, тип **DirectoryInfo** является производным от типа **филесистеминфо** .</span><span class="sxs-lookup"><span data-stu-id="ada52-137">For example, the **DirectoryInfo** type is derived from the **FileSystemInfo** type.</span></span> <span data-ttu-id="ada52-138">Поэтому оба этих примера возвращают **значение true**.</span><span class="sxs-lookup"><span data-stu-id="ada52-138">Therefore, both of these examples return **True**.</span></span>

```powershell
PS> (Get-Item /) -is [System.IO.DirectoryInfo]
True
PS> (Get-Item /) -is [System.IO.FileSystemInfo]
True
```

<span data-ttu-id="ada52-139">`-is`Оператор также может сопоставлять интерфейсы, если объект `<input>` реализует интерфейс в сравнении.</span><span class="sxs-lookup"><span data-stu-id="ada52-139">The `-is` operator can also match interfaces if the `<input>` implements the interface in the comparison.</span></span> <span data-ttu-id="ada52-140">В этом примере входными данными является массив.</span><span class="sxs-lookup"><span data-stu-id="ada52-140">In this example, the input is an array.</span></span> <span data-ttu-id="ada52-141">Массивы реализуют интерфейс **System. Collections. IList** .</span><span class="sxs-lookup"><span data-stu-id="ada52-141">Arrays implement the **System.Collections.IList** interface.</span></span>

```powershell
PS> 1, 2 -is [System.Collections.IList]
True
```

### <a name="-as-operator"></a><span data-ttu-id="ada52-142">Оператор-as</span><span class="sxs-lookup"><span data-stu-id="ada52-142">-as operator</span></span>

<span data-ttu-id="ada52-143">`-as`Оператор пытается преобразовать входной объект в указанный тип .NET.</span><span class="sxs-lookup"><span data-stu-id="ada52-143">The `-as` operator tries to convert the input object to the specified .NET type.</span></span> <span data-ttu-id="ada52-144">Если он завершается, возвращается преобразованный объект.</span><span class="sxs-lookup"><span data-stu-id="ada52-144">If it succeeds, it returns the converted object.</span></span> <span data-ttu-id="ada52-145">При сбое он возвращает `$null` .</span><span class="sxs-lookup"><span data-stu-id="ada52-145">It if fails, it returns `$null`.</span></span> <span data-ttu-id="ada52-146">Он не возвращает ошибку.</span><span class="sxs-lookup"><span data-stu-id="ada52-146">It does not return an error.</span></span>

<span data-ttu-id="ada52-147">Если `<input>` — это тип, _производный_ от типа .NET, `-as` _передается посредством_ возвращения входного объекта без изменений.</span><span class="sxs-lookup"><span data-stu-id="ada52-147">If the `<input>` is a type that is _derived_ from the .NET Type `-as` _passes through_ returns input object unchanged.</span></span> <span data-ttu-id="ada52-148">Например, тип **DirectoryInfo** является производным от типа **филесистеминфо** .</span><span class="sxs-lookup"><span data-stu-id="ada52-148">For example, the **DirectoryInfo** type is derived from the **FileSystemInfo** type.</span></span> <span data-ttu-id="ada52-149">Таким образом, тип объекта не изменяется в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="ada52-149">Therefore, the object type is unchanged in the following example:</span></span>

```powershell
PS> $fsroot = (Get-Item /) -as [System.IO.FileSystemInfo]
PS> $fsroot.GetType().FullName
System.IO.DirectoryInfo
```

#### <a name="converting-the-datetime-type-is-culture-sensitive"></a><span data-ttu-id="ada52-150">Преобразование типа DateTime зависит от языка и региональных параметров</span><span class="sxs-lookup"><span data-stu-id="ada52-150">Converting the DateTime type is culture-sensitive</span></span>

<span data-ttu-id="ada52-151">В отличие от приведения типов, преобразование в `[DateTime]` тип с помощью `-as` оператора работает только со строками, отформатированными в соответствии с правилами текущего языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="ada52-151">Unlike type casting, converting to `[DateTime]` type using the `-as` operator only works with strings that are formatted according to the rules of the current culture.</span></span>

```powershell
PS> [cultureinfo]::CurrentCulture = 'fr-FR'
PS> '13/5/20' -as [datetime]

mercredi 13 mai 2020 00:00:00

PS> '05/13/20' -as [datetime]
PS> [datetime]'05/13/20'

mercredi 13 mai 2020 00:00:00

PS> [datetime]'13/05/20'
InvalidArgument: Cannot convert value "13/05/20" to type "System.DateTime".
Error: "String '13/05/20' was not recognized as a valid DateTime."
```

<span data-ttu-id="ada52-152">Чтобы найти тип .NET объекта, используйте `Get-Member` командлет.</span><span class="sxs-lookup"><span data-stu-id="ada52-152">To find the .NET type of an object, use the `Get-Member` cmdlet.</span></span> <span data-ttu-id="ada52-153">Или используйте метод **GetType** всех объектов вместе со свойством **FullName** этого метода.</span><span class="sxs-lookup"><span data-stu-id="ada52-153">Or, use the **GetType** method of all the objects together with the **FullName** property of this method.</span></span> <span data-ttu-id="ada52-154">Например, следующая инструкция возвращает тип возвращаемого значения `Get-Culture` команды:</span><span class="sxs-lookup"><span data-stu-id="ada52-154">For example, the following statement gets the type of the return value of a `Get-Culture` command:</span></span>

```powershell
PS> (Get-Culture).GetType().FullName
System.Globalization.CultureInfo
```

## <a name="examples"></a><span data-ttu-id="ada52-155">Примеры</span><span class="sxs-lookup"><span data-stu-id="ada52-155">EXAMPLES</span></span>

<span data-ttu-id="ada52-156">В следующих примерах показаны некоторые способы использования операторов типов:</span><span class="sxs-lookup"><span data-stu-id="ada52-156">The following examples show some uses of the Type operators:</span></span>

```powershell
PS> 32 -is [Float]
False

PS> 32 -is "int"
True

PS> (get-date) -is [DateTime]
True

PS> "12/31/2007" -is [DateTime]
False

PS> "12/31/2007" -is [String]
True

PS> (get-process PowerShell)[0] -is [System.Diagnostics.Process]
True

PS> (get-command get-member) -is [System.Management.Automation.CmdletInfo]
True
```

<span data-ttu-id="ada52-157">В следующем примере показано, что если входные данные представляют собой коллекцию объектов, соответствующий тип является типом .NET коллекции, а не типом отдельных объектов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="ada52-157">The following example shows that when the input is a collection of objects, the matching type is the .NET type of the collection, not the type of the individual objects in the collection.</span></span>

<span data-ttu-id="ada52-158">В этом примере несмотря на то, `Get-Culture` что `Get-UICulture` командлеты и возвращают объекты **System. Globalization. CultureInfo** , коллекция этих объектов является массивом System. Object.</span><span class="sxs-lookup"><span data-stu-id="ada52-158">In this example, although both the `Get-Culture` and `Get-UICulture` cmdlets return **System.Globalization.CultureInfo** objects, a collection of these objects is a System.Object array.</span></span>

```powershell
PS> (get-culture) -is [System.Globalization.CultureInfo]
True

PS> (get-uiculture) -is [System.Globalization.CultureInfo]
True

PS> (get-culture), (get-uiculture) -is [System.Globalization.CultureInfo]
False

PS> (get-culture), (get-uiculture) -is [Array]
True

PS> (get-culture), (get-uiculture) | foreach {
  $_ -is [System.Globalization.CultureInfo])
}
True
True

PS> (get-culture), (get-uiculture) -is [Object]
True
```

<span data-ttu-id="ada52-159">В следующих примерах показано, как использовать `-as` оператор.</span><span class="sxs-lookup"><span data-stu-id="ada52-159">The following examples show how to use the `-as` operator.</span></span>

```powershell
PS> "12/31/07" -is [DateTime]
False

PS> "12/31/07" -as [DateTime]
Monday, December 31, 2007 12:00:00 AM

PS> $date = "12/31/07" -as [DateTime]

C:\PS>$a -is [DateTime]
True

PS> 1031 -as [System.Globalization.CultureInfo]

LCID      Name      DisplayName
----      ----      -----------
1031      de-DE     German (Germany)
```

<span data-ttu-id="ada52-160">В следующем примере показано, что если `-as` оператор не может преобразовать входной объект в тип .NET, возвращается значение `$null` .</span><span class="sxs-lookup"><span data-stu-id="ada52-160">The following example shows that when the `-as` operator cannot convert the input object to the .NET type, it returns `$null`.</span></span>

```powershell
PS> 1031 -as [System.Diagnostics.Process]
PS>
```

## <a name="see-also"></a><span data-ttu-id="ada52-161">СМ. ТАКЖЕ</span><span class="sxs-lookup"><span data-stu-id="ada52-161">SEE ALSO</span></span>

[<span data-ttu-id="ada52-162">about_Operators</span><span class="sxs-lookup"><span data-stu-id="ada52-162">about_Operators</span></span>](about_Operators.md)
