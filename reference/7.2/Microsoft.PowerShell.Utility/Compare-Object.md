---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/compare-object?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Compare-Object
ms.openlocfilehash: 6bed0e8d13cb834fab97dc0265ef7d46a2caea97
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604670"
---
# <span data-ttu-id="4f4a6-102">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="4f4a6-102">Compare-Object</span></span>

## <span data-ttu-id="4f4a6-103">Краткий обзор</span><span class="sxs-lookup"><span data-stu-id="4f4a6-103">Synopsis</span></span>
<span data-ttu-id="4f4a6-104">Сравнивает два набора объектов.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-104">Compares two sets of objects.</span></span>

## <span data-ttu-id="4f4a6-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4f4a6-105">Syntax</span></span>

```
Compare-Object [-ReferenceObject] <PSObject[]> [-DifferenceObject] <PSObject[]>
 [-SyncWindow <Int32>] [-Property <Object[]>] [-ExcludeDifferent] [-IncludeEqual] [-PassThru]
 [-Culture <String>] [-CaseSensitive] [<CommonParameters>]
```

## <span data-ttu-id="4f4a6-106">Описание</span><span class="sxs-lookup"><span data-stu-id="4f4a6-106">Description</span></span>

<span data-ttu-id="4f4a6-107">`Compare-Object`Командлет сравнивает два набора объектов.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-107">The `Compare-Object` cmdlet compares two sets of objects.</span></span> <span data-ttu-id="4f4a6-108">Одним набором объектов является **ссылка**, а другой набор объектов — это **разница**.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-108">One set of objects is the **reference**, and the other set of objects is the **difference**.</span></span>

<span data-ttu-id="4f4a6-109">`Compare-Object` проверяет наличие доступных методов сравнения целого объекта.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-109">`Compare-Object` checks for available methods of comparing a whole object.</span></span> <span data-ttu-id="4f4a6-110">Если не удается найти подходящий метод, он вызывает методы **ToString ()** входных объектов и сравнивает результаты строки.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-110">If it can't find a suitable method, it calls the **ToString()** methods of the input objects and compares the string results.</span></span> <span data-ttu-id="4f4a6-111">Можно указать одно или несколько свойств, которые будут использоваться для сравнения.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-111">You can provide one or more properties to be used for comparison.</span></span> <span data-ttu-id="4f4a6-112">При указании свойств командлет сравнивает значения только этих свойств.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-112">When properties are provided, the cmdlet compares the values of those properties only.</span></span>

<span data-ttu-id="4f4a6-113">Результат сравнения указывает, отображается ли значение свойства только в объекте **Reference** ( `<=` ) или только в объекте **Difference** ( `=>` ).</span><span class="sxs-lookup"><span data-stu-id="4f4a6-113">The result of the comparison indicates whether a property value appeared only in the **reference** object (`<=`) or only in the **difference** object (`=>`).</span></span> <span data-ttu-id="4f4a6-114">Если используется параметр **инклудикуал** , ( `==` ) указывает, что значение находится в обоих объектах.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-114">If the **IncludeEqual** parameter is used, (`==`) indicates the value is in both objects.</span></span>

<span data-ttu-id="4f4a6-115">Если **ссылка** или объекты **различий** имеют значение null ( `$null` ), `Compare-Object` создает завершающую ошибку.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-115">If the **reference** or the **difference** objects are null (`$null`), `Compare-Object` generates a terminating error.</span></span>

<span data-ttu-id="4f4a6-116">В некоторых примерах Сплаттинг используется для сокращения длины строки примеров кода.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-116">Some examples use splatting to reduce the line length of the code samples.</span></span> <span data-ttu-id="4f4a6-117">Дополнительные сведения см. в разделе [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span><span class="sxs-lookup"><span data-stu-id="4f4a6-117">For more information, see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span></span>

## <span data-ttu-id="4f4a6-118">Примеры</span><span class="sxs-lookup"><span data-stu-id="4f4a6-118">Examples</span></span>

### <span data-ttu-id="4f4a6-119">Пример 1. Сравнение содержимого двух текстовых файлов</span><span class="sxs-lookup"><span data-stu-id="4f4a6-119">Example 1 - Compare the content of two text files</span></span>

<span data-ttu-id="4f4a6-120">В этом примере сравнивается содержимое двух текстовых файлов.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-120">This example compares the contents of two text files.</span></span> <span data-ttu-id="4f4a6-121">В примере используются два текстовых файла, каждый из которых имеет значение в отдельной строке.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-121">The example uses the following two text files, with each value on a separate line.</span></span>

- <span data-ttu-id="4f4a6-122">`Testfile1.txt` содержит значения: Dog, squirrel и высоты.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-122">`Testfile1.txt` contains the values: dog, squirrel, and bird.</span></span>
- <span data-ttu-id="4f4a6-123">`Testfile2.txt` содержит значения: Cat, высоты и Ракун.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-123">`Testfile2.txt` contains the values: cat, bird, and racoon.</span></span>

<span data-ttu-id="4f4a6-124">В выходных данных отображаются только те строки, которые отличаются от файлов.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-124">The output displays only the lines that are different between the files.</span></span> <span data-ttu-id="4f4a6-125">`Testfile1.txt` Объект **Reference** ( `<=` ) и `Testfile2.txt` является объектом **Difference** ( `=>` ).</span><span class="sxs-lookup"><span data-stu-id="4f4a6-125">`Testfile1.txt` is the **reference** object (`<=`) and `Testfile2.txt`is the **difference** object (`=>`).</span></span> <span data-ttu-id="4f4a6-126">Строки с содержимым, которое отображается в обоих файлах, не отображаются.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-126">Lines with content that appear in both files aren't displayed.</span></span>

```powershell
Compare-Object -ReferenceObject (Get-Content -Path C:\Test\Testfile1.txt) -DifferenceObject (Get-Content -Path C:\Test\Testfile2.txt)
```

```Output
InputObject SideIndicator
----------- -------------
cat         =>
racoon      =>
dog         <=
squirrel    <=
```

### <span data-ttu-id="4f4a6-127">Пример 2. сравнение каждой строки содержимого и исключение различий</span><span class="sxs-lookup"><span data-stu-id="4f4a6-127">Example 2 - Compare each line of content and exclude the differences</span></span>

<span data-ttu-id="4f4a6-128">В этом примере используется параметр **ексклудедифферент** для сравнения каждой строки содержимого в двух текстовых файлах.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-128">This example uses the **ExcludeDifferent** parameter to compare each line of content in two text files.</span></span>

<span data-ttu-id="4f4a6-129">В PowerShell 7,1 при использовании параметра **ексклудедифферент** выводится **инклудикуал** , а выходные данные содержат только строки, содержащиеся в обоих файлах, как показано в **сидеиндикатор** ( `==` ).</span><span class="sxs-lookup"><span data-stu-id="4f4a6-129">As of PowerShell 7.1, when using the **ExcludeDifferent** parameter, **IncludeEqual** is inferred and the output only contains lines contained in both files, as shown by the **SideIndicator** (`==`).</span></span>

```powershell
$objects = @{
  ReferenceObject = (Get-Content -Path C:\Test\Testfile1.txt)
  DifferenceObject = (Get-Content -Path C:\Test\Testfile2.txt)
}
Compare-Object @objects -ExcludeDifferent
```

```Output
InputObject SideIndicator
----------- -------------
bird        ==
```

<a id="ex3" />

### <span data-ttu-id="4f4a6-130">Пример 3. Отображение разницы при использовании параметра PassThru</span><span class="sxs-lookup"><span data-stu-id="4f4a6-130">Example 3 - Show the difference when using the PassThru parameter</span></span>

<span data-ttu-id="4f4a6-131">Обычно `Compare-Object` возвращает тип **PSCustomObject** со следующими свойствами:</span><span class="sxs-lookup"><span data-stu-id="4f4a6-131">Normally, `Compare-Object` returns a **PSCustomObject** type with the following properties:</span></span>

- <span data-ttu-id="4f4a6-132">Сравниваемый объект **InputObject**</span><span class="sxs-lookup"><span data-stu-id="4f4a6-132">The **InputObject** being compared</span></span>
- <span data-ttu-id="4f4a6-133">Свойство **сидеиндикатор** , показывающее входной объект, которому принадлежат выходные данные</span><span class="sxs-lookup"><span data-stu-id="4f4a6-133">The **SideIndicator** property showing which input object the output belongs to</span></span>

<span data-ttu-id="4f4a6-134">При использовании параметра **PassThru** **тип** объекта не изменяется, но возвращаемый экземпляр объекта имеет добавленный **NoteProperty** с именем **сидеиндикатор**.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-134">When you use the **PassThru** parameter, the **Type** of the object is not changed but the instance of the object returned has an added **NoteProperty** named **SideIndicator**.</span></span> <span data-ttu-id="4f4a6-135">**Сидеиндикатор** показывает, к какому объекту данных принадлежит выход.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-135">**SideIndicator** shows which input object the output belongs to.</span></span>

<span data-ttu-id="4f4a6-136">В следующих примерах показаны различные типы выходных данных.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-136">The following examples shows the different output types.</span></span>

```powershell
$a = $True
Compare-Object -IncludeEqual $a $a
(Compare-Object -IncludeEqual $a $a) | Get-Member
```

```Output
InputObject SideIndicator
----------- -------------
       True ==

   TypeName: System.Management.Automation.PSCustomObject
Name          MemberType   Definition
----          ----------   ----------
Equals        Method       bool Equals(System.Object obj)
GetHashCode   Method       int GetHashCode()
GetType       Method       type GetType()
ToString      Method       string ToString()
InputObject   NoteProperty System.Boolean InputObject=True
SideIndicator NoteProperty string SideIndicator===
```

```powershell
Compare-Object -IncludeEqual $a $a -PassThru
(Compare-Object -IncludeEqual $a $a -PassThru) | Get-Member
```

```Output
True

   TypeName: System.Boolean
Name          MemberType   Definition
----          ----------   ----------
CompareTo     Method       int CompareTo(System.Object obj), int CompareTo(bool value), int IComparable.CompareTo(Syst
Equals        Method       bool Equals(System.Object obj), bool Equals(bool obj), bool IEquatable[bool].Equals(bool ot
GetHashCode   Method       int GetHashCode()
GetType       Method       type GetType()
GetTypeCode   Method       System.TypeCode GetTypeCode(), System.TypeCode IConvertible.GetTypeCode()
ToBoolean     Method       bool IConvertible.ToBoolean(System.IFormatProvider provider)
ToByte        Method       byte IConvertible.ToByte(System.IFormatProvider provider)
ToChar        Method       char IConvertible.ToChar(System.IFormatProvider provider)
ToDateTime    Method       datetime IConvertible.ToDateTime(System.IFormatProvider provider)
ToDecimal     Method       decimal IConvertible.ToDecimal(System.IFormatProvider provider)
ToDouble      Method       double IConvertible.ToDouble(System.IFormatProvider provider)
ToInt16       Method       short IConvertible.ToInt16(System.IFormatProvider provider)
ToInt32       Method       int IConvertible.ToInt32(System.IFormatProvider provider)
ToInt64       Method       long IConvertible.ToInt64(System.IFormatProvider provider)
ToSByte       Method       sbyte IConvertible.ToSByte(System.IFormatProvider provider)
ToSingle      Method       float IConvertible.ToSingle(System.IFormatProvider provider)
ToString      Method       string ToString(), string ToString(System.IFormatProvider provider), string IConvertible.To
ToType        Method       System.Object IConvertible.ToType(type conversionType, System.IFormatProvider provider)
ToUInt16      Method       ushort IConvertible.ToUInt16(System.IFormatProvider provider)
ToUInt32      Method       uint IConvertible.ToUInt32(System.IFormatProvider provider)
ToUInt64      Method       ulong IConvertible.ToUInt64(System.IFormatProvider provider)
TryFormat     Method       bool TryFormat(System.Span[char] destination, [ref] int charsWritten)
SideIndicator NoteProperty string SideIndicator===
```

<span data-ttu-id="4f4a6-137">При использовании функции **PassThru** возвращается исходный тип объекта (**System. Boolean**).</span><span class="sxs-lookup"><span data-stu-id="4f4a6-137">When using **PassThru**, the original object type (**System.Boolean**) is returned.</span></span> <span data-ttu-id="4f4a6-138">Обратите внимание, что в выходных данных, отображаемых в формате по умолчанию для объектов **System. Boolean** , не отображалось свойство **сидеиндикатор** .</span><span class="sxs-lookup"><span data-stu-id="4f4a6-138">Note how the output displayed by the default format for **System.Boolean** objects didn't display the **SideIndicator** property.</span></span> <span data-ttu-id="4f4a6-139">Однако возвращенный объект **System. Boolean** имеет добавленный **NoteProperty**.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-139">However, the returned **System.Boolean** object has the added **NoteProperty**.</span></span>

### <span data-ttu-id="4f4a6-140">Пример 4. Сравнение двух простых объектов с помощью свойств</span><span class="sxs-lookup"><span data-stu-id="4f4a6-140">Example 4 - Compare two simple objects using properties</span></span>

<span data-ttu-id="4f4a6-141">В этом примере мы сравниваем две различные строки, имеющие одинаковую длину.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-141">In this example, we compare two different string that have the same length.</span></span>

```powershell
Compare-Object -ReferenceObject 'abc' -DifferenceObject 'xyz' -Property Length -IncludeEqual
```

```Output
Length SideIndicator
------ -------------
     3 ==
```

### <span data-ttu-id="4f4a6-142">Пример 5. Сравнение сложных объектов с помощью свойств</span><span class="sxs-lookup"><span data-stu-id="4f4a6-142">Example 5 - Comparing complex objects using properties</span></span>

<span data-ttu-id="4f4a6-143">В этом примере показано поведение при сравнении сложных объектов.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-143">This example shows the behavior when comparing complex objects.</span></span> <span data-ttu-id="4f4a6-144">В этом примере мы сохраняем два различных объекта процесса для разных экземпляров PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-144">In this example we store two different process objects for different instances of PowerShell.</span></span> <span data-ttu-id="4f4a6-145">Обе переменные содержат объекты Process с одинаковыми именами.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-145">Both variables contain process objects with the same name.</span></span> <span data-ttu-id="4f4a6-146">При сравнении объектов без указания параметра **Свойства** командлет считает объекты одинаковыми.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-146">When the objects are compared without specifying the **Property** parameter, the cmdlet considers the objects to be equal.</span></span> <span data-ttu-id="4f4a6-147">Обратите внимание, что значение **InputObject** совпадает с результатом метода **ToString ()** .</span><span class="sxs-lookup"><span data-stu-id="4f4a6-147">Notice that the value of the **InputObject** is the same as the result of the **ToString()** method.</span></span> <span data-ttu-id="4f4a6-148">Поскольку класс **System. Diagnostics. Process** не имеет интерфейса **IComparable** , командлет преобразует объекты в строки, а затем сравнивает результаты.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-148">Since the **System.Diagnostics.Process** class does not have the **IComparable** interface, the cmdlet converts the objects to strings then compares the results.</span></span>

```powershell
PS> Get-Process pwsh

 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
    101   123.32     139.10      35.81   11168   1 pwsh
     89   107.55      66.97      11.44   17600   1 pwsh

PS> $a = Get-Process -Id 11168
PS> $b = Get-Process -Id 17600
PS> $a.ToString()
System.Diagnostics.Process (pwsh)
PS> $b.ToString()
System.Diagnostics.Process (pwsh)
PS> Compare-Object $a $b -IncludeEqual

InputObject                       SideIndicator
-----------                       -------------
System.Diagnostics.Process (pwsh) ==

PS> Compare-Object $a $b -Property ProcessName, Id, CPU

ProcessName    Id       CPU SideIndicator
-----------    --       --- -------------
pwsh        17600   11.4375 =>
pwsh        11168 36.203125 <=
```

<span data-ttu-id="4f4a6-149">При указании сравниваемых свойств командлет показывает различия.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-149">When you specify properties to be compared, the cmdlet shows the differences.</span></span>

### <span data-ttu-id="4f4a6-150">Пример 6. Сравнение сложных объектов, реализующих интерфейс IComparable</span><span class="sxs-lookup"><span data-stu-id="4f4a6-150">Example 6 - Comparing complex objects that implement IComparable</span></span>

<span data-ttu-id="4f4a6-151">Если объект реализует интерфейс **IComparable**, командлет ищет способы сравнения объектов. Если объекты имеют разные типы, то объект **различий** преобразуется в тип **референцеобжект** , который затем сравнивается.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-151">If the object implements **IComparable**, the cmdlet searches for ways to compare the objects.If the objects are different types, the **Difference** object is converted to the type of the **ReferenceObject** then compared.</span></span>

<span data-ttu-id="4f4a6-152">В этом примере выполняется сравнение строки с объектом **TimeSpan** .</span><span class="sxs-lookup"><span data-stu-id="4f4a6-152">In this example, we are comparing a string to a **TimeSpan** object.</span></span> <span data-ttu-id="4f4a6-153">В первом случае строка преобразуется в **интервал** времени, поэтому объекты равны.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-153">In the first case, the string is converted to a **TimeSpan** so the objects are equal.</span></span>

```powershell
Compare-Object ([TimeSpan]"0:0:1") "0:0:1" -IncludeEqual
```

```Output
InputObject SideIndicator
----------- -------------
00:00:01    ==
```

```powershell
Compare-Object "0:0:1" ([TimeSpan]"0:0:1")
```

```Output
InputObject SideIndicator
----------- -------------
00:00:01    =>
0:0:1       <=
```

<span data-ttu-id="4f4a6-154">Во втором случае **TimeSpan** преобразуется в строку, чтобы объект отличался.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-154">In the second case, the **TimeSpan** is converted to a string so the object are different.</span></span>

## <span data-ttu-id="4f4a6-155">Параметры</span><span class="sxs-lookup"><span data-stu-id="4f4a6-155">Parameters</span></span>

### <span data-ttu-id="4f4a6-156">-CaseSensitive</span><span class="sxs-lookup"><span data-stu-id="4f4a6-156">-CaseSensitive</span></span>

<span data-ttu-id="4f4a6-157">Указывает, что сравнение выполняется с учетом регистра.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-157">Indicates that comparisons should be case-sensitive.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4f4a6-158">-Culture</span><span class="sxs-lookup"><span data-stu-id="4f4a6-158">-Culture</span></span>

<span data-ttu-id="4f4a6-159">Указывает язык, используемый для сравнения.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-159">Specifies the culture to use for comparisons.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4f4a6-160">-Дифференцеобжект</span><span class="sxs-lookup"><span data-stu-id="4f4a6-160">-DifferenceObject</span></span>

<span data-ttu-id="4f4a6-161">Указывает объекты, сравниваемые с **ссылочными** объектами.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-161">Specifies the objects that are compared to the **reference** objects.</span></span>

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="4f4a6-162">-Ексклудедифферент</span><span class="sxs-lookup"><span data-stu-id="4f4a6-162">-ExcludeDifferent</span></span>

<span data-ttu-id="4f4a6-163">Указывает, что этот командлет отображает только характеристики сравниваемых объектов, которые равны.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-163">Indicates that this cmdlet displays only the characteristics of compared objects that are equal.</span></span> <span data-ttu-id="4f4a6-164">Различия между объектами отбрасываются.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-164">The differences between the objects are discarded.</span></span>

<span data-ttu-id="4f4a6-165">Используйте **ексклудедифферент** с **инклудикуал** , чтобы отобразить только те строки, которые соответствуют объектам **ссылки** и **различий** .</span><span class="sxs-lookup"><span data-stu-id="4f4a6-165">Use **ExcludeDifferent** with **IncludeEqual** to display only the lines that match between the **reference** and **difference** objects.</span></span>

<span data-ttu-id="4f4a6-166">Если **ексклудедифферент** указан без **инклудикуал**, выходные данные отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-166">If **ExcludeDifferent** is specified without **IncludeEqual**, there's no output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4f4a6-167">-Инклудикуал</span><span class="sxs-lookup"><span data-stu-id="4f4a6-167">-IncludeEqual</span></span>

<span data-ttu-id="4f4a6-168">**Инклудикуал** отображает совпадения между объектами **ссылки** и **различий** .</span><span class="sxs-lookup"><span data-stu-id="4f4a6-168">**IncludeEqual** displays the matches between the **reference** and **difference** objects.</span></span>

<span data-ttu-id="4f4a6-169">По умолчанию выходные данные также содержат различия между объектами **ссылок** и **различий** .</span><span class="sxs-lookup"><span data-stu-id="4f4a6-169">By default, the output also includes the differences between the **reference** and **difference** objects.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4f4a6-170">-PassThru</span><span class="sxs-lookup"><span data-stu-id="4f4a6-170">-PassThru</span></span>

<span data-ttu-id="4f4a6-171">При использовании параметра **PassThru** `Compare-Object` опускает оболочку **PSCustomObject** вокруг сравниваемых объектов и возвращает отличающиеся объекты без изменений.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-171">When you use the **PassThru** parameter, `Compare-Object` omits the **PSCustomObject** wrapper around the compared objects and returns the differing objects, unchanged.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4f4a6-172">-Property</span><span class="sxs-lookup"><span data-stu-id="4f4a6-172">-Property</span></span>

<span data-ttu-id="4f4a6-173">Указывает массив свойств **ссылки** и сравниваемых объектов. </span><span class="sxs-lookup"><span data-stu-id="4f4a6-173">Specifies an array of properties of the **reference** and **difference** objects to compare.</span></span>

<span data-ttu-id="4f4a6-174">Значением параметра **Property** может быть новое вычисляемое свойство.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-174">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="4f4a6-175">Вычисляемое свойство может быть блоком скрипта или хэш-таблицей.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-175">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="4f4a6-176">Допустимые пары "ключ-значение":</span><span class="sxs-lookup"><span data-stu-id="4f4a6-176">Valid key-value pairs are:</span></span>

- <span data-ttu-id="4f4a6-177">Выражение — `<string>` или `<script block>`</span><span class="sxs-lookup"><span data-stu-id="4f4a6-177">Expression - `<string>` or `<script block>`</span></span>

<span data-ttu-id="4f4a6-178">Дополнительные сведения см. в разделе [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="4f4a6-178">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4f4a6-179">-Референцеобжект</span><span class="sxs-lookup"><span data-stu-id="4f4a6-179">-ReferenceObject</span></span>

<span data-ttu-id="4f4a6-180">Задает массив объектов, используемых в качестве ссылки для сравнения.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-180">Specifies an array of objects used as a reference for comparison.</span></span>

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4f4a6-181">-Синквиндов</span><span class="sxs-lookup"><span data-stu-id="4f4a6-181">-SyncWindow</span></span>

<span data-ttu-id="4f4a6-182">Указывает количество смежных объектов, `Compare-Object` проверяемых при поиске совпадения в коллекции объектов.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-182">Specifies the number of adjacent objects that `Compare-Object` inspects while looking for a match in a collection of objects.</span></span> <span data-ttu-id="4f4a6-183">`Compare-Object` проверяет смежные объекты, если он не находит объект в том же положении в коллекции.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-183">`Compare-Object` examines adjacent objects when it doesn't find the object in the same position in a collection.</span></span> <span data-ttu-id="4f4a6-184">Значение по умолчанию — `[Int32]::MaxValue` , то есть `Compare-Object` проверяет всю коллекцию объектов.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-184">The default value is `[Int32]::MaxValue`, which means that `Compare-Object` examines the entire object collection.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: [Int32]::MaxValue
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4f4a6-185">Общие параметры</span><span class="sxs-lookup"><span data-stu-id="4f4a6-185">CommonParameters</span></span>

<span data-ttu-id="4f4a6-186">Этот командлет поддерживает общие параметры: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction и -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-186">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4f4a6-187">См. сведения в разделе [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4f4a6-187">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4f4a6-188">Входные данные</span><span class="sxs-lookup"><span data-stu-id="4f4a6-188">Inputs</span></span>

### <span data-ttu-id="4f4a6-189">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="4f4a6-189">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="4f4a6-190">Вы можете отправить объект по конвейеру в параметр **дифференцеобжект** .</span><span class="sxs-lookup"><span data-stu-id="4f4a6-190">You can send an object down the pipeline to the **DifferenceObject** parameter.</span></span>

## <span data-ttu-id="4f4a6-191">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="4f4a6-191">Outputs</span></span>

### <span data-ttu-id="4f4a6-192">None</span><span class="sxs-lookup"><span data-stu-id="4f4a6-192">None</span></span>

<span data-ttu-id="4f4a6-193">Если **ссылочный** объект и объект **различий** одинаковы, выходные данные отсутствуют, если не используется параметр **инклудикуал** .</span><span class="sxs-lookup"><span data-stu-id="4f4a6-193">If the **reference** object and the **difference** object are the same, there's no output, unless you use the **IncludeEqual** parameter.</span></span>

### <span data-ttu-id="4f4a6-194">System. Management. Automation. PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="4f4a6-194">System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="4f4a6-195">Если объекты отличаются, заключает различные `Compare-Object` объекты в `PSCustomObject` оболочке со свойством **сидеиндикатор** для ссылки на различия.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-195">If the objects are different, `Compare-Object` wraps the differing objects in a `PSCustomObject` wrapper with a **SideIndicator** property to reference the differences.</span></span>

<span data-ttu-id="4f4a6-196">При использовании параметра **PassThru** **тип** объекта не изменяется, но возвращаемый экземпляр объекта имеет добавленный **NoteProperty** с именем **сидеиндикатор**.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-196">When you use the **PassThru** parameter, the **Type** of the object is not changed but the instance of the object returned has an added **NoteProperty** named **SideIndicator**.</span></span> <span data-ttu-id="4f4a6-197">**Сидеиндикатор** показывает, к какому объекту данных принадлежит выход.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-197">**SideIndicator** shows which input object the output belongs to.</span></span>

## <span data-ttu-id="4f4a6-198">Примечания</span><span class="sxs-lookup"><span data-stu-id="4f4a6-198">Notes</span></span>

<span data-ttu-id="4f4a6-199">При использовании параметра **PassThru** выходные данные, отображаемые в консоли, могут не включать свойство **сидеиндикатор** .</span><span class="sxs-lookup"><span data-stu-id="4f4a6-199">When using the **PassThru** parameter, the output displayed in the console may not include the **SideIndicator** property.</span></span> <span data-ttu-id="4f4a6-200">Представление формата по умолчанию для типа выходных данных объекта не `Compare-Object` включает свойство **сидеиндикатор** .</span><span class="sxs-lookup"><span data-stu-id="4f4a6-200">The default format view of the for the object type output by `Compare-Object` does not include the **SideIndicator** property.</span></span> <span data-ttu-id="4f4a6-201">Дополнительные сведения см. в [примере 3](#ex3) в этой статье.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-201">For more information see [Example 3](#ex3) in this article.</span></span>

## <span data-ttu-id="4f4a6-202">Связанные ссылки</span><span class="sxs-lookup"><span data-stu-id="4f4a6-202">Related links</span></span>

[<span data-ttu-id="4f4a6-203">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="4f4a6-203">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="4f4a6-204">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="4f4a6-204">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="4f4a6-205">Group-Object</span><span class="sxs-lookup"><span data-stu-id="4f4a6-205">Group-Object</span></span>](Group-Object.md)

[<span data-ttu-id="4f4a6-206">Measure-Object;</span><span class="sxs-lookup"><span data-stu-id="4f4a6-206">Measure-Object</span></span>](Measure-Object.md)

[<span data-ttu-id="4f4a6-207">New-Object</span><span class="sxs-lookup"><span data-stu-id="4f4a6-207">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="4f4a6-208">Select-Object</span><span class="sxs-lookup"><span data-stu-id="4f4a6-208">Select-Object</span></span>](Select-Object.md)

[<span data-ttu-id="4f4a6-209">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="4f4a6-209">Sort-Object</span></span>](Sort-Object.md)

[<span data-ttu-id="4f4a6-210">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="4f4a6-210">Tee-Object</span></span>](Tee-Object.md)

[<span data-ttu-id="4f4a6-211">Where-Object</span><span class="sxs-lookup"><span data-stu-id="4f4a6-211">Where-Object</span></span>](../Microsoft.PowerShell.Core/Where-Object.md)

[<span data-ttu-id="4f4a6-212">Get-Process</span><span class="sxs-lookup"><span data-stu-id="4f4a6-212">Get-Process</span></span>](../Microsoft.PowerShell.Management/Get-Process.md)
