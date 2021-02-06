---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/add-member?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-Member
ms.openlocfilehash: 4e9e5ec6d188bec0b4032151fb92e6995d8efbb8
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601088"
---
# <span data-ttu-id="7ea52-102">Add-Member</span><span class="sxs-lookup"><span data-stu-id="7ea52-102">Add-Member</span></span>

## <span data-ttu-id="7ea52-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="7ea52-103">SYNOPSIS</span></span>
<span data-ttu-id="7ea52-104">Добавляет пользовательские свойства и методы в экземпляр объекта PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7ea52-104">Adds custom properties and methods to an instance of a PowerShell object.</span></span>

## <span data-ttu-id="7ea52-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7ea52-105">SYNTAX</span></span>

### <span data-ttu-id="7ea52-106">Имя_типа (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="7ea52-106">TypeNameSet (Default)</span></span>

```
Add-Member -InputObject <PSObject> -TypeName <String> [-PassThru] [<CommonParameters>]
```

### <span data-ttu-id="7ea52-107">нотепропертимултимемберсет</span><span class="sxs-lookup"><span data-stu-id="7ea52-107">NotePropertyMultiMemberSet</span></span>

```
Add-Member -InputObject <PSObject> [-TypeName <String>] [-Force] [-PassThru]
 [-NotePropertyMembers] <IDictionary> [<CommonParameters>]
```

### <span data-ttu-id="7ea52-108">нотепропертисинглемемберсет</span><span class="sxs-lookup"><span data-stu-id="7ea52-108">NotePropertySingleMemberSet</span></span>

```
Add-Member -InputObject <PSObject> [-TypeName <String>] [-Force] [-PassThru] [-NotePropertyName] <String>
 [-NotePropertyValue] <Object> [<CommonParameters>]
```

### <span data-ttu-id="7ea52-109">MemberSet</span><span class="sxs-lookup"><span data-stu-id="7ea52-109">MemberSet</span></span>

```
Add-Member -InputObject <PSObject> [-MemberType] <PSMemberTypes> [-Name] <String> [[-Value] <Object>]
 [[-SecondValue] <Object>] [-TypeName <String>] [-Force] [-PassThru] [<CommonParameters>]
```

## <span data-ttu-id="7ea52-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7ea52-110">DESCRIPTION</span></span>

<span data-ttu-id="7ea52-111">`Add-Member`Командлет позволяет добавлять элементы (свойства и методы) в экземпляр объекта PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7ea52-111">The `Add-Member` cmdlet lets you add members (properties and methods) to an instance of a PowerShell object.</span></span> <span data-ttu-id="7ea52-112">Например, можно добавить элемент NoteProperty, содержащий описание объекта или элемент **ScriptMethod** , который запускает скрипт для изменения объекта.</span><span class="sxs-lookup"><span data-stu-id="7ea52-112">For instance, you can add a NoteProperty member that contains a description of the object or a **ScriptMethod** member that runs a script to change the object.</span></span>

<span data-ttu-id="7ea52-113">Чтобы использовать `Add-Member` , передайте объект в `Add-Member` или используйте параметр **InputObject** для указания объекта.</span><span class="sxs-lookup"><span data-stu-id="7ea52-113">To use `Add-Member`, pipe the object to `Add-Member`, or use the **InputObject** parameter to specify the object.</span></span>

<span data-ttu-id="7ea52-114">Параметр **MemberType** указывает тип добавляемого члена.</span><span class="sxs-lookup"><span data-stu-id="7ea52-114">The **MemberType** parameter indicates the type of member that you want to add.</span></span> <span data-ttu-id="7ea52-115">Параметр **Name** присваивает имя новому элементу, а параметр **value** задает значение элемента.</span><span class="sxs-lookup"><span data-stu-id="7ea52-115">The **Name** parameter assigns a name to the new member, and the **Value** parameter sets the value of the member.</span></span>

<span data-ttu-id="7ea52-116">Свойства и методы добавляются только в определенный экземпляр указанного объекта.</span><span class="sxs-lookup"><span data-stu-id="7ea52-116">The properties and methods that you add are added only to the particular instance of the object that you specify.</span></span> <span data-ttu-id="7ea52-117">`Add-Member` не изменяет тип объекта.</span><span class="sxs-lookup"><span data-stu-id="7ea52-117">`Add-Member` does not change the object type.</span></span> <span data-ttu-id="7ea52-118">Чтобы создать новый тип объекта, используйте `Add-Type` командлет.</span><span class="sxs-lookup"><span data-stu-id="7ea52-118">To create a new object type, use the `Add-Type` cmdlet.</span></span>

<span data-ttu-id="7ea52-119">Можно также использовать `Export-Clixml` командлет для сохранения в файле экземпляра объекта, включая дополнительные элементы.</span><span class="sxs-lookup"><span data-stu-id="7ea52-119">You can also use the `Export-Clixml` cmdlet to save the instance of the object, including the additional members, in a file.</span></span> <span data-ttu-id="7ea52-120">Затем можно использовать `Import-Clixml` командлет для повторного создания экземпляра объекта на основе сведений, хранящихся в экспортированном файле.</span><span class="sxs-lookup"><span data-stu-id="7ea52-120">Then you can use the `Import-Clixml` cmdlet to re-create the instance of the object from the information that is stored in the exported file.</span></span>

<span data-ttu-id="7ea52-121">Начиная с Windows PowerShell 3,0, `Add-Member` содержит новые функции, упрощающие Добавление свойств заметок к объектам.</span><span class="sxs-lookup"><span data-stu-id="7ea52-121">Beginning in Windows PowerShell 3.0, `Add-Member` has new features that make it easier to add note properties to objects.</span></span>
<span data-ttu-id="7ea52-122">С помощью параметров **NotePropertyName** и **NotePropertyValue** можно определить свойство примечания, а с помощью параметра **NotePropertyMembers** — получить хэш-таблицу имен и значений свойств примечаний.</span><span class="sxs-lookup"><span data-stu-id="7ea52-122">You can use the **NotePropertyName** and **NotePropertyValue** parameters to define a note property or use the **NotePropertyMembers** parameter, which takes a hash table of note property names and values.</span></span>

<span data-ttu-id="7ea52-123">Кроме того, начиная с выпуска Windows PowerShell 3.0 параметр **PassThru**, который создает выходной объект, требуется реже.</span><span class="sxs-lookup"><span data-stu-id="7ea52-123">Also, beginning in Windows PowerShell 3.0, the **PassThru** parameter, which generates an output object, is needed less frequently.</span></span> <span data-ttu-id="7ea52-124">`Add-Member` Теперь добавляет новые элементы непосредственно в входной объект большего числа типов.</span><span class="sxs-lookup"><span data-stu-id="7ea52-124">`Add-Member` now adds the new members directly to the input object of more types.</span></span> <span data-ttu-id="7ea52-125">Подробнее см. в описании параметра **PassThru**.</span><span class="sxs-lookup"><span data-stu-id="7ea52-125">For more information, see the **PassThru** parameter description.</span></span>

## <span data-ttu-id="7ea52-126">Примеры</span><span class="sxs-lookup"><span data-stu-id="7ea52-126">EXAMPLES</span></span>

### <span data-ttu-id="7ea52-127">Пример 1. Добавление свойства примечания к PSObject</span><span class="sxs-lookup"><span data-stu-id="7ea52-127">Example 1: Add a note property to a PSObject</span></span>

<span data-ttu-id="7ea52-128">В следующем **примере к объекту** **FileInfo** , представляющему файл, добавляется свойство «Note» со значением «Done» `Test.txt` .</span><span class="sxs-lookup"><span data-stu-id="7ea52-128">The following example adds a **Status** note property with a value of "Done" to the **FileInfo** object that represents the `Test.txt` file.</span></span>

<span data-ttu-id="7ea52-129">Первая команда использует `Get-ChildItem` командлет для получения объекта **FileInfo** , представляющего `Test.txt` файл.</span><span class="sxs-lookup"><span data-stu-id="7ea52-129">The first command uses the `Get-ChildItem` cmdlet to get a **FileInfo** object representing the `Test.txt` file.</span></span> <span data-ttu-id="7ea52-130">Он сохраняется в `$a` переменной.</span><span class="sxs-lookup"><span data-stu-id="7ea52-130">It saves it in the `$a` variable.</span></span>

<span data-ttu-id="7ea52-131">Вторая команда добавляет свойство Note в объект в `$a` .</span><span class="sxs-lookup"><span data-stu-id="7ea52-131">The second command adds the note property to the object in `$a`.</span></span>

<span data-ttu-id="7ea52-132">Третья команда использует точечную нотацию для получения значения свойства **Status** объекта в `$a` .</span><span class="sxs-lookup"><span data-stu-id="7ea52-132">The third command uses dot notation to get the value of the **Status** property of the object in `$a`.</span></span> <span data-ttu-id="7ea52-133">Как видно из выходных данных, значение равно «Done».</span><span class="sxs-lookup"><span data-stu-id="7ea52-133">As the output shows, the value is "Done".</span></span>

```powershell
$A = Get-ChildItem c:\ps-test\test.txt
$A | Add-Member -NotePropertyName Status -NotePropertyValue Done
$A.Status
```

```Output
Done
```

### <span data-ttu-id="7ea52-134">Пример 2. Добавление свойства Alias к PSObject</span><span class="sxs-lookup"><span data-stu-id="7ea52-134">Example 2: Add an alias property to a PSObject</span></span>

<span data-ttu-id="7ea52-135">В следующем примере в объект, представляющий файл, добавляется свойство псевдонима **размера** `Test.txt` .</span><span class="sxs-lookup"><span data-stu-id="7ea52-135">The following example adds a **Size** alias property to the object that represents the `Test.txt` file.</span></span> <span data-ttu-id="7ea52-136">Новое свойство является псевдонимом для свойства **length** .</span><span class="sxs-lookup"><span data-stu-id="7ea52-136">The new property is an alias for the **Length** property.</span></span>

<span data-ttu-id="7ea52-137">Первая команда использует `Get-ChildItem` командлет для получения `Test.txt` объекта **FileInfo** .</span><span class="sxs-lookup"><span data-stu-id="7ea52-137">The first command uses the `Get-ChildItem` cmdlet to get the `Test.txt` **FileInfo** object.</span></span>

<span data-ttu-id="7ea52-138">Вторая команда добавляет свойство псевдонима **size** .</span><span class="sxs-lookup"><span data-stu-id="7ea52-138">The second command adds the **Size** alias property.</span></span>
<span data-ttu-id="7ea52-139">Третья команда использует точечную нотацию для получения значения нового свойства **size** .</span><span class="sxs-lookup"><span data-stu-id="7ea52-139">The third command uses dot notation to get the value of the new **Size** property.</span></span>

```powershell
$A = Get-ChildItem C:\Temp\test.txt
$A | Add-Member -MemberType AliasProperty -Name Size -Value Length
$A.Size
```

```Output
2394
```

### <span data-ttu-id="7ea52-140">Пример 3. Добавление свойства заметки Стрингусе в строку</span><span class="sxs-lookup"><span data-stu-id="7ea52-140">Example 3: Add a StringUse note property to a string</span></span>

<span data-ttu-id="7ea52-141">В этом примере в строку добавляется свойство Note **стрингусе** .</span><span class="sxs-lookup"><span data-stu-id="7ea52-141">This example adds the **StringUse** note property to a string.</span></span>
<span data-ttu-id="7ea52-142">Поскольку `Add-Member` не может добавлять типы к **строковым** входным объектам, можно указать параметр **PassThru** для создания выходного объекта.</span><span class="sxs-lookup"><span data-stu-id="7ea52-142">Because `Add-Member` cannot add types to **String** input objects, you can specify the **PassThru** parameter to generate an output object.</span></span> <span data-ttu-id="7ea52-143">Последняя команда в этом примере выводит новое свойство.</span><span class="sxs-lookup"><span data-stu-id="7ea52-143">The last command in the example displays the new property.</span></span>

<span data-ttu-id="7ea52-144">В этом примере используется параметр **нотепропертимемберс** .</span><span class="sxs-lookup"><span data-stu-id="7ea52-144">This example uses the **NotePropertyMembers** parameter.</span></span> <span data-ttu-id="7ea52-145">Значение параметра **NotePropertyMembers** представляет собой хэш-таблицу.</span><span class="sxs-lookup"><span data-stu-id="7ea52-145">The value of the **NotePropertyMembers** parameter is a hash table.</span></span> <span data-ttu-id="7ea52-146">Ключ — это имя свойства заметки, **стрингусе**, а значение — значение свойства Note, **Отображаемое**.</span><span class="sxs-lookup"><span data-stu-id="7ea52-146">The key is the note property name, **StringUse**, and the value is the note property value, **Display**.</span></span>

```powershell
$A = "A string"
$A = $A | Add-Member -NotePropertyMembers @{StringUse="Display"} -PassThru
$A.StringUse
```

```Output
Display
```

### <span data-ttu-id="7ea52-147">Пример 4. Добавление метода скрипта в объект FileInfo</span><span class="sxs-lookup"><span data-stu-id="7ea52-147">Example 4: Add a script method to a FileInfo object</span></span>

<span data-ttu-id="7ea52-148">В этом примере в объект **FileInfo** добавляется метод скрипта **значение sizeInMB** , который вычисляет размер файла до ближайшего мегабайта.</span><span class="sxs-lookup"><span data-stu-id="7ea52-148">This example adds the **SizeInMB** script method to a **FileInfo** object which calculates the file size to the nearest MegaByte.</span></span> <span data-ttu-id="7ea52-149">Вторая команда создает блок **ScriptBlock** , который использует метод **Round** -static из `[math]` типа для округления размера файла до второго десятичного знака.</span><span class="sxs-lookup"><span data-stu-id="7ea52-149">The second command creates a **ScriptBlock** that uses the **Round** static method from the `[math]` type to round the file size to the second decimal place.</span></span>

<span data-ttu-id="7ea52-150">Параметр **value** также использует `$This` автоматическую переменную, которая представляет текущий объект.</span><span class="sxs-lookup"><span data-stu-id="7ea52-150">The **Value** parameter also uses the `$This` automatic variable, which represents the current object.</span></span> <span data-ttu-id="7ea52-151">`$This`Переменная допустима только в блоках скриптов, которые определяют новые свойства и методы.</span><span class="sxs-lookup"><span data-stu-id="7ea52-151">The `$This` variable is valid only in script blocks that define new properties and methods.</span></span>

<span data-ttu-id="7ea52-152">Последняя команда использует точечную нотацию для вызова нового метода скрипта **значение sizeInMB** для объекта в `$A` переменной.</span><span class="sxs-lookup"><span data-stu-id="7ea52-152">The last command uses dot notation to call the new **SizeInMB** script method on the object in the `$A` variable.</span></span>

```powershell
$A = Get-ChildItem C:\Temp\test.txt
$S = {[math]::Round(($this.Length / 1MB), 2)}
$A | Add-Member -MemberType ScriptMethod -Name "SizeInMB" -Value $S
$A.SizeInMB()
```

```Output
0.43
```

### <span data-ttu-id="7ea52-153">Пример 5. копирование всех свойств объекта в другой</span><span class="sxs-lookup"><span data-stu-id="7ea52-153">Example 5: Copy all properties of an object to another</span></span>

<span data-ttu-id="7ea52-154">Эта функция копирует все свойства одного объекта в другой объект.</span><span class="sxs-lookup"><span data-stu-id="7ea52-154">This function copies all of the properties of one object to another object.</span></span>

<span data-ttu-id="7ea52-155">В `foreach` цикле используется `Get-Member` командлет для получения всех свойств объекта **from** .</span><span class="sxs-lookup"><span data-stu-id="7ea52-155">The `foreach` loop uses the `Get-Member` cmdlet to get each of the properties of the **From** object.</span></span> <span data-ttu-id="7ea52-156">Команды в `foreach` цикле выполняются последовательно в каждом из свойств.</span><span class="sxs-lookup"><span data-stu-id="7ea52-156">The commands within the `foreach` loop are performed in series on each of the properties.</span></span>

<span data-ttu-id="7ea52-157">`Add-Member`Команда добавляет свойство объекта **from** в объект **to** в качестве **NoteProperty**.</span><span class="sxs-lookup"><span data-stu-id="7ea52-157">The `Add-Member` command adds the property of the **From** object to the **To** object as a **NoteProperty**.</span></span> <span data-ttu-id="7ea52-158">Значение копируется с помощью параметра **value** .</span><span class="sxs-lookup"><span data-stu-id="7ea52-158">The value is copied using the **Value** parameter.</span></span> <span data-ttu-id="7ea52-159">Он использует параметр **Force** для добавления членов с одинаковым именем элемента.</span><span class="sxs-lookup"><span data-stu-id="7ea52-159">It uses the **Force** parameter to add members with the same member name.</span></span>

```powershell
function Copy-Property ($From, $To)
{
    $properties = Get-Member -InputObject $From -MemberType Property
    foreach ($p in $properties)
    {
        $To | Add-Member -MemberType NoteProperty -Name $p.Name -Value $From.$($p.Name) -Force
    }
}
```

### <span data-ttu-id="7ea52-160">Пример 6. Создание пользовательского объекта</span><span class="sxs-lookup"><span data-stu-id="7ea52-160">Example 6: Create a custom object</span></span>

<span data-ttu-id="7ea52-161">В этом примере создается настраиваемый объект **ресурса** .</span><span class="sxs-lookup"><span data-stu-id="7ea52-161">This example creates an **Asset** custom object.</span></span>

<span data-ttu-id="7ea52-162">`New-Object`Командлет создает **PSObject**.</span><span class="sxs-lookup"><span data-stu-id="7ea52-162">The `New-Object` cmdlet creates a **PSObject**.</span></span> <span data-ttu-id="7ea52-163">В примере параметр **PSObject** сохраняется в `$Asset` переменной.</span><span class="sxs-lookup"><span data-stu-id="7ea52-163">The example saves the **PSObject** in the `$Asset` variable.</span></span>

<span data-ttu-id="7ea52-164">Вторая команда использует `[ordered]` ускоритель типов для создания упорядоченного словаря имен и значений.</span><span class="sxs-lookup"><span data-stu-id="7ea52-164">The second command uses the `[ordered]` type accelerator to create an ordered dictionary of names and values.</span></span> <span data-ttu-id="7ea52-165">Команда сохраняет результат в `$D` переменной.</span><span class="sxs-lookup"><span data-stu-id="7ea52-165">The command saves the result in the `$D` variable.</span></span>

<span data-ttu-id="7ea52-166">Третья команда использует параметр **нотепропертимемберс** `Add-Member` командлета, чтобы добавить словарь в `$D` переменную в **PSObject**.</span><span class="sxs-lookup"><span data-stu-id="7ea52-166">The third command uses the **NotePropertyMembers** parameter of the `Add-Member` cmdlet to add the dictionary in the `$D` variable to the **PSObject**.</span></span>
<span data-ttu-id="7ea52-167">Свойство **TypeName** присваивает параметру **PSObject** новое имя, **ресурс-контейнер**.</span><span class="sxs-lookup"><span data-stu-id="7ea52-167">The **TypeName** property assigns a new name, **Asset**, to the **PSObject**.</span></span>

<span data-ttu-id="7ea52-168">Последняя команда передает новый объект **Asset** в `Get-Member` командлет.</span><span class="sxs-lookup"><span data-stu-id="7ea52-168">The last command pipes the new **Asset** object to the `Get-Member` cmdlet.</span></span> <span data-ttu-id="7ea52-169">Выходные данные показывают, что объект имеет имя типа **Asset** и свойства примечания, определенные в упорядоченном словаре.</span><span class="sxs-lookup"><span data-stu-id="7ea52-169">The output shows that the object has a type name of **Asset** and the note properties that we defined in the ordered dictionary.</span></span>

```powershell
$Asset = New-Object -TypeName PSObject
$d = [ordered]@{Name="Server30";System="Server Core";PSVersion="4.0"}
$Asset | Add-Member -NotePropertyMembers $d -TypeName Asset
$Asset | Get-Member
```

```Output
   TypeName: Asset

Name        MemberType   Definition
----        ----------   ----------
Equals      Method       bool Equals(System.Object obj)
GetHashCode Method       int GetHashCode()
GetType     Method       type GetType()
ToString    Method       string ToString()
Name        NoteProperty System.String Name=Server30
PSVersion   NoteProperty System.String PSVersion=4.0
System      NoteProperty System.String System=Server Core
```

## <span data-ttu-id="7ea52-170">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7ea52-170">PARAMETERS</span></span>

### <span data-ttu-id="7ea52-171">-Force</span><span class="sxs-lookup"><span data-stu-id="7ea52-171">-Force</span></span>

<span data-ttu-id="7ea52-172">Указывает, что этот командлет добавляет новый элемент, даже если он имеет пользовательский элемент с таким же именем.</span><span class="sxs-lookup"><span data-stu-id="7ea52-172">Indicates that this cmdlet adds a new member even the object has a custom member with the same name.</span></span>
<span data-ttu-id="7ea52-173">Нельзя использовать параметр **Force** для замены стандартного члена типа.</span><span class="sxs-lookup"><span data-stu-id="7ea52-173">You cannot use the **Force** parameter to replace a standard member of a type.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: MemberSet, NotePropertySingleMemberSet, NotePropertyMultiMemberSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7ea52-174">-InputObject</span><span class="sxs-lookup"><span data-stu-id="7ea52-174">-InputObject</span></span>

<span data-ttu-id="7ea52-175">Указывает объект, в который добавляется новый член.</span><span class="sxs-lookup"><span data-stu-id="7ea52-175">Specifies the object to which the new member is added.</span></span>
<span data-ttu-id="7ea52-176">Введите переменную, которая содержит объекты, или команду или выражение, которое возвращает объекты.</span><span class="sxs-lookup"><span data-stu-id="7ea52-176">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="7ea52-177">-MemberType</span><span class="sxs-lookup"><span data-stu-id="7ea52-177">-MemberType</span></span>

<span data-ttu-id="7ea52-178">Указывает тип добавляемого элемента.</span><span class="sxs-lookup"><span data-stu-id="7ea52-178">Specifies the type of the member to add.</span></span>
<span data-ttu-id="7ea52-179">Это обязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="7ea52-179">This parameter is required.</span></span>
<span data-ttu-id="7ea52-180">Допустимые значения для этого параметра:</span><span class="sxs-lookup"><span data-stu-id="7ea52-180">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="7ea52-181">NoteProperty</span><span class="sxs-lookup"><span data-stu-id="7ea52-181">NoteProperty</span></span>
- <span data-ttu-id="7ea52-182">AliasProperty</span><span class="sxs-lookup"><span data-stu-id="7ea52-182">AliasProperty</span></span>
- <span data-ttu-id="7ea52-183">ScriptProperty</span><span class="sxs-lookup"><span data-stu-id="7ea52-183">ScriptProperty</span></span>
- <span data-ttu-id="7ea52-184">CodeProperty</span><span class="sxs-lookup"><span data-stu-id="7ea52-184">CodeProperty</span></span>
- <span data-ttu-id="7ea52-185">ScriptMethod</span><span class="sxs-lookup"><span data-stu-id="7ea52-185">ScriptMethod</span></span>
- <span data-ttu-id="7ea52-186">CodeMethod</span><span class="sxs-lookup"><span data-stu-id="7ea52-186">CodeMethod</span></span>

<span data-ttu-id="7ea52-187">Дополнительные сведения об этих значениях см. в разделе [перечисление псмембертипес](/dotnet/api/system.management.automation.psmembertypes) в пакете SDK для PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7ea52-187">For information about these values, see [PSMemberTypes Enumeration](/dotnet/api/system.management.automation.psmembertypes) in the PowerShell SDK.</span></span>

<span data-ttu-id="7ea52-188">Не у всех объектов имеются члены всех типов.</span><span class="sxs-lookup"><span data-stu-id="7ea52-188">Not all objects have every type of member.</span></span>
<span data-ttu-id="7ea52-189">При указании типа элемента, который отсутствует в объекте, PowerShell возвращает ошибку.</span><span class="sxs-lookup"><span data-stu-id="7ea52-189">If you specify a member type that the object does not have, PowerShell returns an error.</span></span>

```yaml
Type: System.Management.Automation.PSMemberTypes
Parameter Sets: MemberSet
Aliases: Type
Accepted values: AliasProperty, CodeProperty, Property, NoteProperty, ScriptProperty, Properties, PropertySet, Method, CodeMethod, ScriptMethod, Methods, ParameterizedProperty, MemberSet, Event, Dynamic, All

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7ea52-190">-Name</span><span class="sxs-lookup"><span data-stu-id="7ea52-190">-Name</span></span>

<span data-ttu-id="7ea52-191">Указывает имя члена, добавляемого этим командлетом.</span><span class="sxs-lookup"><span data-stu-id="7ea52-191">Specifies the name of the member that this cmdlet adds.</span></span>

```yaml
Type: System.String
Parameter Sets: MemberSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7ea52-192">-Нотепропертимемберс</span><span class="sxs-lookup"><span data-stu-id="7ea52-192">-NotePropertyMembers</span></span>

<span data-ttu-id="7ea52-193">Задает хэш-таблицу или упорядоченный словарь имен и значений свойств примечаний.</span><span class="sxs-lookup"><span data-stu-id="7ea52-193">Specifies a hash table or ordered dictionary of note property names and values.</span></span>
<span data-ttu-id="7ea52-194">Введите хэш-таблицу или словарь, в котором ключи представляют имена свойств примечаний, а значения — значения этих свойств.</span><span class="sxs-lookup"><span data-stu-id="7ea52-194">Type a hash table or dictionary in which the keys are note property names and the values are note property values.</span></span>

<span data-ttu-id="7ea52-195">Дополнительные сведения о хэш-таблицах и упорядоченных словарях в PowerShell см. в разделе [about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md).</span><span class="sxs-lookup"><span data-stu-id="7ea52-195">For more information about hash tables and ordered dictionaries in PowerShell, see [about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md).</span></span>

<span data-ttu-id="7ea52-196">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="7ea52-196">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Collections.IDictionary
Parameter Sets: NotePropertyMultiMemberSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7ea52-197">-Нотепропертинаме</span><span class="sxs-lookup"><span data-stu-id="7ea52-197">-NotePropertyName</span></span>

<span data-ttu-id="7ea52-198">Указывает имя свойства заметки.</span><span class="sxs-lookup"><span data-stu-id="7ea52-198">Specifies the note property name.</span></span>

<span data-ttu-id="7ea52-199">Используйте этот параметр с параметром **NotePropertyValue**.</span><span class="sxs-lookup"><span data-stu-id="7ea52-199">Use this parameter with the **NotePropertyValue** parameter.</span></span>
<span data-ttu-id="7ea52-200">Этот параметр является необязательным.</span><span class="sxs-lookup"><span data-stu-id="7ea52-200">This parameter is optional.</span></span>

<span data-ttu-id="7ea52-201">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="7ea52-201">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: NotePropertySingleMemberSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7ea52-202">-Нотепропертивалуе</span><span class="sxs-lookup"><span data-stu-id="7ea52-202">-NotePropertyValue</span></span>

<span data-ttu-id="7ea52-203">Задает значение свойства Note.</span><span class="sxs-lookup"><span data-stu-id="7ea52-203">Specifies the note property value.</span></span>

<span data-ttu-id="7ea52-204">Используйте этот параметр с параметром **нотепропертинаме** .</span><span class="sxs-lookup"><span data-stu-id="7ea52-204">Use this parameter with the **NotePropertyName** parameter.</span></span>
<span data-ttu-id="7ea52-205">Этот параметр является необязательным.</span><span class="sxs-lookup"><span data-stu-id="7ea52-205">This parameter is optional.</span></span>

<span data-ttu-id="7ea52-206">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="7ea52-206">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Object
Parameter Sets: NotePropertySingleMemberSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7ea52-207">-PassThru</span><span class="sxs-lookup"><span data-stu-id="7ea52-207">-PassThru</span></span>

<span data-ttu-id="7ea52-208">Возвращает объект, представляющий элемент, с которым вы работаете.</span><span class="sxs-lookup"><span data-stu-id="7ea52-208">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="7ea52-209">По умолчанию этот командлет не создает выходные данные.</span><span class="sxs-lookup"><span data-stu-id="7ea52-209">By default, this cmdlet does not generate any output.</span></span>

<span data-ttu-id="7ea52-210">Для большинства объектов `Add-Member` добавляет новые элементы в входной объект.</span><span class="sxs-lookup"><span data-stu-id="7ea52-210">For most objects, `Add-Member` adds the new members to the input object.</span></span>
<span data-ttu-id="7ea52-211">Однако если входной объект является строкой, то `Add-Member` не может добавить элемент в входной объект.</span><span class="sxs-lookup"><span data-stu-id="7ea52-211">However, when the input object is a string, `Add-Member` cannot add the member to the input object.</span></span>
<span data-ttu-id="7ea52-212">В случае с такими объектами используйте параметр **PassThru** для создания выходного объекта.</span><span class="sxs-lookup"><span data-stu-id="7ea52-212">For these objects, use the **PassThru** parameter to create an output object.</span></span>

<span data-ttu-id="7ea52-213">В Windows PowerShell 2,0 `Add-Member` добавлены элементы только в оболочку **PSObject** объектов, а не в объект.</span><span class="sxs-lookup"><span data-stu-id="7ea52-213">In Windows PowerShell 2.0, `Add-Member` added members only to the **PSObject** wrapper of objects, not to the object.</span></span>
<span data-ttu-id="7ea52-214">Используйте параметр **PassThru** , чтобы создать выходной объект для любого объекта, имеющего обертку **PSObject** .</span><span class="sxs-lookup"><span data-stu-id="7ea52-214">Use the **PassThru** parameter to create an output object for any object that has a **PSObject** wrapper.</span></span>

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

### <span data-ttu-id="7ea52-215">-SecondValue</span><span class="sxs-lookup"><span data-stu-id="7ea52-215">-SecondValue</span></span>

<span data-ttu-id="7ea52-216">Указывает дополнительные сведения о членах **AliasProperty**, **ScriptProperty**, **CodeProperty** или **CodeMethod**.</span><span class="sxs-lookup"><span data-stu-id="7ea52-216">Specifies optional additional information about **AliasProperty**, **ScriptProperty**, **CodeProperty**, or **CodeMethod** members.</span></span>

<span data-ttu-id="7ea52-217">Если используется при добавлении **AliasProperty**, этот параметр должен иметь тип данных.</span><span class="sxs-lookup"><span data-stu-id="7ea52-217">If used when adding an **AliasProperty**, this parameter must be a data type.</span></span>
<span data-ttu-id="7ea52-218">Преобразование к указанному типу данных добавляется к значению **AliasProperty**.</span><span class="sxs-lookup"><span data-stu-id="7ea52-218">A conversion to the specified data type is added to the value of the **AliasProperty**.</span></span>

<span data-ttu-id="7ea52-219">Например, если добавить **AliasProperty** , предоставляющий альтернативное имя для строкового свойства, можно также указать параметр **SecondValue** в **System. Int32** , чтобы указать, что значение этого свойства строки должно быть преобразовано в целое при доступе с помощью соответствующего **AliasProperty**.</span><span class="sxs-lookup"><span data-stu-id="7ea52-219">For example, if you add an **AliasProperty** that provides an alternate name for a string property, you can also specify a **SecondValue** parameter of **System.Int32** to indicate that the value of that string property should be converted to an integer when accessed by using the corresponding **AliasProperty**.</span></span>

<span data-ttu-id="7ea52-220">Параметр **SecondValue** можно использовать для указания дополнительного **сценария ScriptBlock** при добавлении элемента **ScriptProperty** .</span><span class="sxs-lookup"><span data-stu-id="7ea52-220">You can use the **SecondValue** parameter to specify an additional **ScriptBlock** when adding a **ScriptProperty** member.</span></span> <span data-ttu-id="7ea52-221">Первый блок **ScriptBlock**, указанный в параметре **value** , используется для получения значения переменной.</span><span class="sxs-lookup"><span data-stu-id="7ea52-221">The first **ScriptBlock**, specified in the **Value** parameter, is used to get the value of a variable.</span></span> <span data-ttu-id="7ea52-222">Второй блок **ScriptBlock**, указанный в параметре **SecondValue** , используется для задания значения переменной.</span><span class="sxs-lookup"><span data-stu-id="7ea52-222">The second **ScriptBlock**, specified in the **SecondValue** parameter, is used to set the value of a variable.</span></span>

```yaml
Type: System.Object
Parameter Sets: MemberSet
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7ea52-223">-Value</span><span class="sxs-lookup"><span data-stu-id="7ea52-223">-Value</span></span>

<span data-ttu-id="7ea52-224">Задает исходное значение добавленного члена.</span><span class="sxs-lookup"><span data-stu-id="7ea52-224">Specifies the initial value of the added member.</span></span>
<span data-ttu-id="7ea52-225">При добавлении члена **AliasProperty**, **CodeProperty**, **ScriptProperty** или **CodeMethod** можно указать дополнительные дополнительные сведения с помощью параметра **SecondValue** .</span><span class="sxs-lookup"><span data-stu-id="7ea52-225">If you add an **AliasProperty**, **CodeProperty**, **ScriptProperty** or **CodeMethod** member, you can supply optional, additional information by using the **SecondValue** parameter.</span></span>

```yaml
Type: System.Object
Parameter Sets: MemberSet
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7ea52-226">-TypeName</span><span class="sxs-lookup"><span data-stu-id="7ea52-226">-TypeName</span></span>

<span data-ttu-id="7ea52-227">Указывает имя типа.</span><span class="sxs-lookup"><span data-stu-id="7ea52-227">Specifies a name for the type.</span></span>

<span data-ttu-id="7ea52-228">Если тип является классом в пространстве имен **System** или типом, имеющим ускоритель типа, можно ввести короткое имя типа.</span><span class="sxs-lookup"><span data-stu-id="7ea52-228">When the type is a class in the **System** namespace or a type that has a type accelerator, you can enter the short name of the type.</span></span> <span data-ttu-id="7ea52-229">В остальных случаях требуется полное имя типа.</span><span class="sxs-lookup"><span data-stu-id="7ea52-229">Otherwise, the full type name is required.</span></span>
<span data-ttu-id="7ea52-230">Этот параметр эффективен, только если **InputObject** является **PSObject**.</span><span class="sxs-lookup"><span data-stu-id="7ea52-230">This parameter is effective only when the **InputObject** is a **PSObject**.</span></span>

<span data-ttu-id="7ea52-231">Этот параметр впервые появился в Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="7ea52-231">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: TypeNameSet, NotePropertyMultiMemberSet, NotePropertySingleMemberSet, MemberSet
Aliases:

Required: True (TypeNameSet), False (NotePropertyMultiMemberSet, NotePropertySingleMemberSet, MemberSet)
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7ea52-232">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="7ea52-232">CommonParameters</span></span>

<span data-ttu-id="7ea52-233">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="7ea52-233">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7ea52-234">См. сведения в разделе [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="7ea52-234">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="7ea52-235">Входные данные</span><span class="sxs-lookup"><span data-stu-id="7ea52-235">INPUTS</span></span>

### <span data-ttu-id="7ea52-236">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="7ea52-236">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="7ea52-237">В этот командлет можно передать по конвейеру любой тип объекта.</span><span class="sxs-lookup"><span data-stu-id="7ea52-237">You can pipe any object type to this cmdlet.</span></span>

## <span data-ttu-id="7ea52-238">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="7ea52-238">OUTPUTS</span></span>

### <span data-ttu-id="7ea52-239">Нет или системный. Object</span><span class="sxs-lookup"><span data-stu-id="7ea52-239">None or System.Object</span></span>

<span data-ttu-id="7ea52-240">При использовании параметра **PassThru** этот командлет возвращает новый расширенный объект.</span><span class="sxs-lookup"><span data-stu-id="7ea52-240">When you use the **PassThru** parameter, this cmdlet returns the newly-extended object.</span></span>
<span data-ttu-id="7ea52-241">В противном случае командлет не формирует никаких выходных данных.</span><span class="sxs-lookup"><span data-stu-id="7ea52-241">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="7ea52-242">ПРИМЕЧАНИЯ</span><span class="sxs-lookup"><span data-stu-id="7ea52-242">NOTES</span></span>

<span data-ttu-id="7ea52-243">Элементы можно добавлять только в объекты **PSObject** .</span><span class="sxs-lookup"><span data-stu-id="7ea52-243">You can add members only to **PSObject** objects.</span></span> <span data-ttu-id="7ea52-244">Чтобы определить, является ли объект объектом **PSObject** , используйте `-is` оператор.</span><span class="sxs-lookup"><span data-stu-id="7ea52-244">To determine whether an object is a **PSObject** object, use the `-is` operator.</span></span>

<span data-ttu-id="7ea52-245">Например, чтобы проверить объект, хранящийся в `$obj` переменной, введите `$obj -is [PSObject]` .</span><span class="sxs-lookup"><span data-stu-id="7ea52-245">For instance, to test an object stored in the `$obj` variable, type `$obj -is [PSObject]`.</span></span>

<span data-ttu-id="7ea52-246">Имена параметров **MemberType**, **Name**, **value** и **SecondValue** являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="7ea52-246">The names of the **MemberType**, **Name**, **Value**, and **SecondValue** parameters are optional.</span></span>
<span data-ttu-id="7ea52-247">Если имена параметров не заданы, то значения неименованных параметров должны отображаться в следующем порядке: **MemberType**, **Name**, **value** и **SecondValue**.</span><span class="sxs-lookup"><span data-stu-id="7ea52-247">If you omit the parameter names, the unnamed parameter values must appear in this order: **MemberType**, **Name**, **Value**, and **SecondValue**.</span></span>

<span data-ttu-id="7ea52-248">При указании имен параметры могут следовать в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="7ea52-248">If you include the parameter names, the parameters can appear in any order.</span></span>

<span data-ttu-id="7ea52-249">В `$this` блоках сценариев можно использовать автоматическую переменную, определяющую значения новых свойств и методов.</span><span class="sxs-lookup"><span data-stu-id="7ea52-249">You can use the `$this` automatic variable in script blocks that define the values of new properties and methods.</span></span>
<span data-ttu-id="7ea52-250">`$this`Переменная ссылается на экземпляр объекта, к которому добавляются свойства и методы.</span><span class="sxs-lookup"><span data-stu-id="7ea52-250">The `$this` variable refers to the instance of the object to which the properties and methods are being added.</span></span> <span data-ttu-id="7ea52-251">Дополнительные сведения о `$this` переменной см. в разделе [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="7ea52-251">For more information about the `$this` variable, see [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span></span>

## <span data-ttu-id="7ea52-252">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="7ea52-252">RELATED LINKS</span></span>

[<span data-ttu-id="7ea52-253">Export-Clixml</span><span class="sxs-lookup"><span data-stu-id="7ea52-253">Export-Clixml</span></span>](Export-Clixml.md)

[<span data-ttu-id="7ea52-254">Get-Member</span><span class="sxs-lookup"><span data-stu-id="7ea52-254">Get-Member</span></span>](Get-Member.md)

[<span data-ttu-id="7ea52-255">Import-Clixml</span><span class="sxs-lookup"><span data-stu-id="7ea52-255">Import-Clixml</span></span>](Import-Clixml.md)

[<span data-ttu-id="7ea52-256">New-Object</span><span class="sxs-lookup"><span data-stu-id="7ea52-256">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="7ea52-257">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="7ea52-257">about_Automatic_Variables</span></span>](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

